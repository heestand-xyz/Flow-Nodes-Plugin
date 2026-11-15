# 3D Reference

Source route: `/docs/references/3d`. Media is not bundled; public route availability must be verified.

There are different 3D nodes and types.

This is a breakdown of their differences and how to use them.

> **Tip**
>
> Fields and Entities are added in Flow Nodes 4

# 3D Nodes

## Geometry

Geometry nodes are run on the CPU and are used for creating new 3D shapes and modifications.

## Field

Field nodes are run on the GPU and are essentially particles with support for indices a mesh. Fields are faster then geometries and are recommended to use for realtime rendering.

> **Tip**
>
> Geometry nodes can directly wire to Field nodes.

## 3D Graphic

3D graphic nodes are run on the GPU and are represented by a volume of voxels. The 3D graphic nodes are very similar to the graphic nodes, just adding the third dimension.

## Material

A color or graphic with a simple or unlit lighting mode.

[Simple](../nodes/node-spatial-material-simple.json)

[Unlit](../nodes/node-spatial-material-unlit.json)

## Camera

A perspective or orthographic camera (or a mix).

[Perspective](../nodes/node-spatial-camera-perspective.json)

[Orthographic](../nodes/node-spatial-camera-orthographic.json)

There is a calibration node to find a camera based on 6 2D and 3D points.

[Calibration](../nodes/node-spatial-camera-calibration.json)

## Light

A point, directional, or ambient light.

[Point](../nodes/node-spatial-light-point.json)

[Directional](../nodes/node-spatial-light-directional.json)

[Ambient](../nodes/node-spatial-light-ambient.json)

## Projector

A virtual projector, created by combining a camera and a graphic.

[Projector](../nodes/node-spatial-camera-projector.json)

## Entity

Entity nodes are a structural representation of the all 3D types. It is used to group, texture and clone transform geometry, fields, 3d graphics, cameras, lights and projectors. 

[Group](../nodes/node-spatial-entity-group.json)

[Texture](../nodes/node-spatial-entity-texture.json)

[Clone Transform](../nodes/node-spatial-entity-cloneTransform.json)

> **Tip**
>
> All 3D nodes can directly wire to Entity nodes.

# 3D Render

The 3D Render nodes has an entities multi inlet and a graphic mono outlet.

[3D Render](../nodes/node-graphic-engine-kagamiRender.json)

*Required at least one camera.*

# Credit

**Geometry** nodes are powered **Euclid** by Nick Lockwood

[Euclid](https://github.com/nicklockwood/Euclid)

**3D Graphic** nodes are powered by **AsyncGraphics** by Anton Heestand

[AsyncGraphics](https://github.com/heestand-xyz/AsyncGraphics)
