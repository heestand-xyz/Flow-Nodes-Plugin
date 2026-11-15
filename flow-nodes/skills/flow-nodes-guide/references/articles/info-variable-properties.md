# Variable Properties

Source route: `/docs/info/variable-properties`. Media is not bundled; public route availability must be verified.

There are a couple different ways to control a variable property value.

- Constant *(default)*
  - Modes
    - Fixed
      - A constant value.
    - Flex
      - A relative “flexible” percentage based value.
      - This resulting final value from a flexible value is based on downstream info.
        - This means that this property can result in different final values, based on where the node used.
        - Example: If a capsule with `100%` width and height is used downstream in a view, it might appear as a circle if the view’s aspect ratio is `1.0`.
  - Controls
    - Number Text Field
    - Slider
    - Circle Slider
      - Hold in, drag out, then rotate.
- Spatial
  - Spatial properties support fixed and flexible values per component.
- Script (JavaScript)
  - Write a one-line script to edit the value.
  - Scripts can also make wire connections.

  [Script Guide](scripts-guide.md)

  [Script Reference](scripts-reference.md)
- Wire connection
  - Connect a wire to the associated inlet to control the property.

## Variable Arrays

In Flow Nodes 27.5.0, a Variable Array has one shared constant, spatial, connection, or script mode for its complete list, and one Multi inlet. Its elements do not each have independent modes. An ordinary Value Array is a stored list without that shared evaluation mode.

From JavaScript, `await node("Example").property("Values").values()` reads a Variable Array's evaluated values in the current index context. Use `await property.setValues(values)` to replace the complete list only in constant mode. Spatial, connection, and script modes reject the write without changing the mode or wiring. Ordinary Value Arrays support snapshot reads and awaited whole-list replacement without this shared-mode restriction. Both setters validate the complete replacement before mutation; use explicit write-back rather than editing the returned snapshot.

Neither read creates an automatic dependency wire. Use `wire()` to read a node's output reactively. See the [Script Guide](scripts-guide.md) and [Script Reference](scripts-reference.md) for explicit write-back, supported element types, and validation rules.
