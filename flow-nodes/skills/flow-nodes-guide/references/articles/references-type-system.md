# Type System

Source route: `/docs/references/type-system`. Media is not bundled; public route availability must be verified.

In Flow Nodes, data is strictly typed, meaning values have a specific type. Auto conversion wires are supported between a lot of types.

## Raw Types

Heavy-weight types.

- **Graphic**
  - A 2D image with a resolution and color depth.
  - Default 1000x1000 pixels.
- **3D Graphic**
  - A 3D image with a resolution and color depth.
  - Default 100x100x100 voxels.
- **Vector**
  - A 2D path or shape.
- **3D Vector**
  - A 3D path.
- **Video**
  - A link to a video file on disk.
- **View**
  - A UI element used to build interactive interfaces.
- **Entity**
  - A 3D combination type, used to group different 3d types together.
- **Geometry**
  - A 3D mesh, made up of polygons. Geometry operations are done on the CPU.
- **Polygon**
  - A component of a geometry, consisting of usually 3 vertices.
- **Field**
  - A particle field with support for mesh representation.
  - Now with Gaussian Splat support.
- **Material**
  - A color or graphic on a 3d mesh.
- **Projector**
  - A camera and graphic combined.
- **Lookup**
  - LUTs - Import and export `.cube` files
- **Tool**
  - Used in AI nodes.
- **Action**
  - A downstream signal.
  - Used to trigger events in nodes.

## Core Types

Light-weight types.

- **Float**
  - A number with decimals.
- **Int**
  - A number without decimals.
- **Bool**
  - An on / off state.
- **String**
  - Text
- **Angle** & **3D Angle**
  - A rotation.
  - The 3D angle is 3 regular angles, in `x`, `y` and `z` axis.
- **Point** & **3D Point**
  - A position in space.
- **Vector Point & 3D Vector Point**
  - A bezier curve component.
- **Size** & **3D Size**
  - A size.
- **Rect** & **3D Rect**
  - A point and size combined.
- **Transform** & **3D Transform**
  - A position, scale and rotation combined.
- **Quaternion**
  - A complex 3D rotation. Useful when animating rotations.
- **Vertex**
  - A position and normal (direction of the point).
- **Color**
  - Red, green, blue and alpha components.
- **Date**
  - Date and time. Year, month, day, hour, minute, second, millisecond.
- **Duration**
  - Time duration.
- **Keyframe**
  - A time (duration) along with easing.
- **Camera**
  - A perspective or orthographic camera (or a mix).
- **Light**
  - A point, direction or ambient light.

*Under the hood, core types are also raw types (core type is a subtype of raw type).*

# Auto Conversion

When wiring from one outlet with a specific type to another inlet with another type, if possible a auto conversion wire will be created to convert the value. There is also a manual [Convert](../nodes/general/generic.json) (`node:general:generic:manualConvert`). For some conversion a specific node is created, example: Convert from Vector to Graphic.

> **Tip**
>
> Use the **Encode** and **Decode** nodes for core type with **JSON**.

# Generics

Some in and outlets are generic, meaning they can take any value, as long as both ends of the wire are of the same type.

When a wire is connected to a generic in or outlet, all the chained wires become defined or “locked” to that type.

Relay nodes are useful when working with generic in and outlets. They can be used to define a type constraint.
