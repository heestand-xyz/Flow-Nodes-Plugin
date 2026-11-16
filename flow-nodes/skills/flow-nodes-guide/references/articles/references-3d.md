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

[Simple](../nodes/spatial/material.json) (`node:spatial:material:simple`)

[Unlit](../nodes/spatial/material.json) (`node:spatial:material:unlit`)

## Camera

A perspective or orthographic camera (or a mix).

[Perspective](../nodes/spatial/camera.json) (`node:spatial:camera:perspective`)

[Orthographic](../nodes/spatial/camera.json) (`node:spatial:camera:orthographic`)

There is a calibration node to find a camera based on 6 2D and 3D points.

[Calibration](../nodes/spatial/camera.json) (`node:spatial:camera:calibration`)

## Light

A point, directional, or ambient light.

[Point](../nodes/spatial/light.json) (`node:spatial:light:point`)

[Directional](../nodes/spatial/light.json) (`node:spatial:light:directional`)

[Ambient](../nodes/spatial/light.json) (`node:spatial:light:ambient`)

## Projector

A virtual projector, created by combining a camera and a graphic.

[Projector](../nodes/spatial/camera.json) (`node:spatial:camera:projector`)

## Entity

Entity nodes are a structural representation of the all 3D types. It is used to group, texture and clone transform geometry, fields, 3d graphics, cameras, lights and projectors.

[Group](../nodes/spatial/entity.json) (`node:spatial:entity:group`)

[Texture](../nodes/spatial/entity.json) (`node:spatial:entity:texture`)

[Clone Transform](../nodes/spatial/entity.json) (`node:spatial:entity:cloneTransform`)

> **Tip**
>
> All 3D nodes can directly wire to Entity nodes.

# 3D Render

The 3D Render nodes has an entities multi inlet and a graphic mono outlet.

[3D Render](../nodes/graphic/engine.json) (`node:graphic:engine:kagamiRender`)

*Required at least one camera.*

# Credit

**Geometry** nodes are powered **Euclid** by Nick Lockwood

[Euclid](https://github.com/nicklockwood/Euclid)

**3D Graphic** nodes are powered by **AsyncGraphics** by Anton Heestand

[AsyncGraphics](https://github.com/heestand-xyz/AsyncGraphics)
