# Script Reference

Source route: `/docs/references/script`. Media is not bundled; public route availability must be verified.

Scripts in Flow Nodes are written in JavaScript

There are two places to write scripts:

- Properties
- [Script Node](../nodes/general/code.json) (`node:general:code:script`)

## Node

Nodes can be accessed via the node function: `node("Circle 1")` (in the current node folder)

To access all nodes in the root of the flow write: `self.rootNode.nodes`, or for the nodes in the current folder: `self.parentNode.nodes`.

On a node you can access or edit the **name** via `node.name`.

There is also a type path to know exactly what node it is: `node.typePath`.

To access **wire** **connections** there is `node.inlets`  and `node.outlets`. There are also functions to access an inlet or outlet like this: `node.inlet("Value")` or `node.outlet("Value")`.

To access **properties** there is `node.properties`. There is also a function to access a property like this: `node.property("Property")`.

## Let

*Inlet or outlet.*

To access the name of a let write: `inlet.name` or `outlet.name`

To check if it’s connected to any wires write: `inlet.isConnected` or `outlet.isConnected`

### Inlet

On an inlet you can access the connected outlets (via the wires upstream) like this: `inlet.connectedOutLets`

### Outlet

On an outlet you can access the connected inlets (via the wires downstream) like this: `outlet.connectedInLets`

Outlets also have **value access**; this is how to get the value of a node.

## Values

There are two types of value access:

- Mono value: `await outlet.value()`
- Multi values: `await outlet.values()`

*The `await` keyword is there because the values are fetched asynchronously.*

To check what type the outlet is, use this. *(Not needed for most cases)*

- **Mono**: `outlet.toString().includes("FLWJSMonoOutLet")`
- **Multi**: `outlet.toString().includes("FLWJSMultiOutLet")`
- **Lex** (keyed list) is not yet supported.

## Property

Once you have a property, the name can be accessed like this `property.name`.

On **value** properties you can access the value with `property.value`.

To update a value, set the variable like this `property.value = 1.0`.

### Value Array Property

Available in Flow Nodes 27.5.0. An ordinary Value Array property has two methods:

- `await property.values()` returns a typed JavaScript array snapshot.
- `await property.setValues(values)` replaces the complete list and resolves when the mutation is complete.

Both `node("Example").property("Values")` and the same property in `node("Example").properties` expose these methods. They are methods, not a writable `.values` field. Scalar `.value` and enum access remain separate APIs.

```javascript
async function main() {
    const values = node("Numbers").property("Values")
    await values.setValues([3, 1, 2])
    const snapshot = await values.values()
    return snapshot
}
```

For this example, `Numbers` is an Int List State node. Choose an existing property with the matching element type; JavaScript does not change the property's type.

**Supported element types**

- Bool: JavaScript `true` and `false` only.
- Int: integral JavaScript numbers in the safe-integer range, from `-9007199254740991` through `9007199254740991`. Fractions are rejected rather than truncated. Stored integers outside this range also cannot be read as a lossless JavaScript snapshot.
- Float and Duration: finite JavaScript numbers. Duration values are in seconds.
- String: JavaScript strings, including escaped quotes, newlines, and Unicode.
- Date: valid JavaScript `Date` objects, not strings or epoch numbers. Snapshots use JavaScript's millisecond precision; stored dates outside its range of ±8.64 × 10¹⁵ milliseconds from the Unix epoch are rejected.
- Point, Point3D, Size, Size3D, Rect, Rect3D, Angle, Angle3D, and Color: the corresponding constructors listed below. All numeric components must be finite.

Other element types, including types without a JavaScript representation, reject reads and writes explicitly. An empty list does not make an unsupported property type writable.

**Validation and completion**

The setter validates and converts the entire list before mutation. `[]` is valid for a supported element type. Null, undefined, non-array payloads, sparse arrays, inherited or accessor-based elements, invalid elements, incompatible mixtures, non-finite numbers, and out-of-range integers reject the Promise. Use ordinary array entries, not getters, for each element. Values are not silently dropped or coerced from Boolean values or strings to numbers. An invalid replacement leaves the original list unchanged.

Ordinary source writes are persisted to the model before the Promise resolves, and value/count signals have been published. This does not wait for all asynchronous downstream evaluations. When an active promoted-property override is being edited, the setter updates that override and notifies its existing observer instead of changing canonical source storage. These are runtime scripting writes, not FlowEdit commands; they do not create UI undo entries.

Unavailable or destroyed properties reject rather than exposing invalid storage. Handle failures with `try`/`catch` around the awaited call.

**Snapshots and execution phases**

Changing a returned array or its value objects does not update the property. Call `setValues` with the complete replacement to persist edits.

Direct property reads do not create automatic dependency wires. For reactive reads, use `await wire("Numbers", "Values")` instead. Avoid writing a property from a Live script that also depends on that property's output, since the write may trigger another evaluation.

Scripts also run during dependency discovery. In this phase, `setValues` validates but does not mutate; only normal evaluation commits writes. A read following a discovery-only setter sees the existing property, so wire discovery must not depend on the uncommitted result. This is separate from the existing scalar setter behavior.

### Variable Array Property

`await property.values()` returns a Variable Array's **evaluated** values in the current `multiIndex` context. It preserves the array's shared constant, spatial, connection, or script mode. The evaluated read is unchanged by the setter described below; assigning a field or editing the returned snapshot does not replace the authored array or its mode.

`await property.setValues(values)` replaces a Variable Array's complete list **only in constant mode**. The setter rejects spatial, connection, and script modes with a clear error, including when the replacement is `[]`. It does not switch the mode, disconnect sources, or overwrite spatial or script data. Change the mode explicitly through the normal property controls before writing a constant list.

The setter uses the same supported element types and strict whole-list validation as ordinary Value Arrays above. Invalid input leaves the original list unchanged. Awaited completion, source-model persistence and signal publication, active promoted-override routing, and the absence of UI undo entries follow the same rules. During dependency discovery it validates the mode and values but does not write. Only normal evaluation commits the replacement.

This evaluated read differs from an ordinary Value Array snapshot and from reading a Multi outlet. Direct Variable Array property reads also do not create automatic dependency wires. Use `wire()` when the script needs a reactive dependency on a node's output.

See the [Script Guide](scripts-guide.md) for examples and [Variable Properties](info-variable-properties.md) for the shared-mode model.

### Enum Property

On **enum** properties the value returned is an enum case, with two properties: `property.value.name` and `property.value.typeName`, the type name is used to identify the enum case option.

The enum property also has access to all cases with `property.allCases`, this is an array of enum cases. Only these cases are supported to be set.

Update an enum property dynamically like this: `property.value = new EnumCase("typeName", "Name")`
Or simply use one of the cases like this: `property.value = property.allCases[0]`

## Types

There are various types that can be created or returned by outlets.

### Bool

```javascript
let bool = true
```

### Int

```javascript
let int = 1
```

JavaScript uses the same Number type for integers and decimals. A number returned by a Script node becomes a Flow Float.

### Float

```javascript
let float = 1.5
```

### String

```javascript
let string = "Hello"
```

### Date

```javascript
let date = new Date()
```

`new Date()` creates a date object. `Date.now()` returns milliseconds since the Unix epoch.

### Point

```javascript
let point = new Point(0.0, 0.0)
```
 *(x, y)*

Properties

- `point.x`
- `point.y`

### Point3D

```javascript
let point3d = new Point3D(0.0, 0.0, 0.0)
```
 *(x, y, z)*

Properties

- `point3d.x`
- `point3d.y`
- `point3d.z`

### Size

```javascript
let size = new Size(1.0, 1.0)
```
 *(width, height)*

Properties

- `size.width`
- `size.height`

### Size3D

```javascript
let size3d = new Size3D(1.0, 1.0, 1.0)
```
 *(width, height, depth)*

Properties

- `size3d.width`
- `size3d.height`
- `size3d.depth`

### Rect

```javascript
let rect = new Rect(0.0, 0.0, 1.0, 1.0)
```
 *(x, y, width, height)*

Properties

- `rect.x`
- `rect.y`
- `rect.width`
- `rect.height`
- `rect.origin` *(top, left)*
- `rect.center`
- `rect.size`

### Rect3D

```javascript
let rect3d = new Rect3D(0.0, 0.0, 0.0, 1.0, 1.0, 1.0)
```
 *(x, y, z, width, height, depth)*

Properties

- `rect3d.x`
- `rect3d.y`
- `rect3d.z`
- `rect3d.width`
- `rect3d.height`
- `rect3d.depth`
- `rect3d.origin` *(top, left, far)*
- `rect3d.center`
- `rect3d.size`

### Angle

```javascript
let angle = new Angle(360)
```
  *(degrees)*

Properties

- `angle.degrees`
- `angle.radians`
- `angle.fraction`

### Angle3D

```javascript
let angle3d = new Angle3D(new Angle(90), new Angle(90), new Angle(90))
```
 *(x, y, z)*

Properties

- `angle3d.x`
- `angle3d.y`
- `angle3d.z`

### Color

```javascript
let color = new Color(1.0, 1.0, 1.0, 0.5)
```
 *(red, green, blue, alpha)*

Properties

- `color.red`
- `color.green`
- `color.blue`
- `color.alpha`
- `color.hexCode`

## Time

There is a global function called `time()`; it returns seconds since app launch. A Script node using it updates with the frame loop when Live is enabled. Variable property scripts using it update without a separate Live switch.

## Index

`index` is the first component of the current evaluation index, or `0`. `multiIndex` contains the complete index array.

See the [Script Guide](scripts-guide.md) for examples with screenshots.
