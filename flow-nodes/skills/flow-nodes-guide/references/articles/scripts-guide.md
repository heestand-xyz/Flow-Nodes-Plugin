# Script Guide

Source route: `/docs/guides/script`. Media is not bundled; public route availability must be verified.

Scripts are written in **JavaScript**

There are two ways to write scripts. There is the **script node** and then there are **variable property scripts**.

A Script node automatically wires connections to get the values referenced by the script, then returns values through an automatically created outlet of the returned type.

![Script node with code and console](https://flownodes.app/docs/media/scripts-guide/script-7-dark.png)

The Script node can be triggered to **Run** manually or set to **Live** mode, where it runs when one of its connected input wires updates.

> **Note**
> Live mode alone does not run on a loop. It responds to input and code changes. A script that calls `time()` also receives frame-driven updates while Live is enabled.

## Main Script

```javascript
async function main() {
    console.log("Hello, World!")
    return 123
}
```

This script is composed of an async main function. The script first prints (logs to the console) `"Hello, World!"`, then returns a number. Keep the `async function main()` entry point with no parameters.

> **Note**
> Numbers are represented with the `Float` type in the script node, even if it does not have decimals.

## Variable Property Scripts

![Switching a variable property to script mode](https://flownodes.app/docs/media/scripts-guide/script-3-dark.png)

![Editing a variable property expression](https://flownodes.app/docs/media/scripts-guide/script-2-dark.png)

There is a script button on all variable properties. When in script mode, code can be written to calculate values.

> **Note**
> Variable properties have both a property and an inlet.

## Array Properties

In Flow Nodes 27.5.0, distinguish three uses of arrays:

- An ordinary **Value Array** stores a list. Read it with `await property.values()` and replace it with `await property.setValues(values)`.
- A **Variable Array** evaluates its list in its current shared mode. Read it with `await property.values()`. Replace its list with `await property.setValues(values)` only while it is in constant mode; spatial, connection, and script modes reject the write without switching modes or changing wiring.
- A **Script node** can return an array through its outlet, as in the Loops example below. Returning an array does not replace another node's property.

For example, name an Int List State node `Numbers`, then use a Script node to replace its Values property:

```javascript
async function main() {
    const values = node("Numbers").property("Values")
    await values.setValues([1, 2, 3])
    return await values.values()
}
```

`setValues` replaces the complete list, preserving order. Use `[]` to clear a supported array property. Await the setter before reading the changed property. Its completion includes ordinary source-model persistence and publication of value/count signals, but does not wait for every downstream evaluation to finish.

The same setter works for a Variable Array in constant mode. If it is spatial, connected, or scripted, the Promise rejects with an error; choose constant mode explicitly before trying to replace its list. Even `[]` does not bypass this restriction.

The returned array is a snapshot. Editing it with `push`, `map`, or index assignment does not edit the property; write the complete result back explicitly:

```javascript
async function main() {
    const values = node("Numbers").property("Values")
    const snapshot = await values.values()
    snapshot.push(4)
    await values.setValues(snapshot)
    return await values.values()
}
```

Each normal execution of this second example appends another value. Avoid calling it from a Live script whose input depends on the same Values property: a write can trigger the script again.

All incoming elements must match the property's type. For example, a Point array accepts `[new Point(1, 2), new Point(3, 4)]`; an Int array accepts only safe whole JavaScript numbers, not fractions, Boolean values, or numeric strings. An invalid element rejects the Promise without replacing any of the list. Catch errors with normal JavaScript `try`/`catch`. See the [array-property reference](scripts-reference.md) for supported types and validation rules.

> **Note**
> Direct property reads are snapshots and do not create automatic dependency wires. Use `await wire("Numbers", "Values")` for a reactive list read instead. Flow also runs scripts to discover their wire dependencies; during that discovery, `setValues` validates its arguments but does not write. Reads after a discovery-only setter still see the existing list, so do not rely on that setter to choose which wires the script discovers.

See [Variable Properties](info-variable-properties.md) for the distinction between ordinary and evaluated arrays.

## Auto Wire Connections

![Property script with an automatic wire](https://flownodes.app/docs/media/scripts-guide/script-1-dark.png)

![Connected property value](https://flownodes.app/docs/media/scripts-guide/script-5-dark.png)

With the use of the `wire("Node", "Outlet")` function, connections are automatically made. The first argument is the node name and the second argument is the outlet name.

![Reading a point component in a property script](https://flownodes.app/docs/media/scripts-guide/script-4-dark.png)

```javascript
(await wire("State 1", "Value")).x * 2.0
```

To get component values, like x or y from a Point, first await the wire value.

## Script Node

![Automatic wire into the Script node](https://flownodes.app/docs/media/scripts-guide/script-8-dark.png)

![Script result connected downstream](https://flownodes.app/docs/media/scripts-guide/script-9-dark.png)

```javascript
async function main() {
    console.log("Hello, World!")
    return wire("State 1", "Value")
}
```

Wires are automatically connected with the `wire()` function.

## Values

![Script returning a Point](https://flownodes.app/docs/media/scripts-guide/script-11-dark.png)

```javascript
async function main() {
    console.log("Hello, World!")
    return new Point(1.0, 1.0)
}
```

Points and other types can be created and returned.

## Loops

![Grid of points generated by nested loops](https://flownodes.app/docs/media/scripts-guide/script-12-dark.png)

```javascript
async function main() {
    var points = []
    for (let x = 0; x < 5; x++) {
        for (let y = 0; y < 5; y++) {
            let point = new Point(x, y)
            points.push(point)
        }
    }
    return points
}
```

Nested loops can be used to collect values to return. Here a bunch of `Point` types are created in a loop.

See the [Script Reference](scripts-reference.md) for the node API and value types.
