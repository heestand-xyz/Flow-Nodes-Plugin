# 3D Clones Guide

Source route: `/docs/guides/3d-clones`. Media is not bundled; public route availability must be verified.

Create a grid of cubes rotated with a look at quaternion (3D rotation).

> **Note**
>
> Flow Nodes version 3 or newer is required for this guide.

> **Note**
>
> Flow Nodes version 4 has new Clone Transform nodes, that use GPU instancing.
>
> [Clone Transform](../nodes/spatial/entity.json) (`node:spatial:entity:cloneTransform`)

![3D Clones — step 1](https://flownodes.app/docs/media/guides-3d-clones/media-01.png)

Start with a new flow:

![3D Clones — step 2](https://flownodes.app/docs/media/guides-3d-clones/media-02.png)

## Cube

Add a [Cube](../nodes/geometry/shape.json) (`node:geometry:shape:cube`) node:

![3D Clones — step 3](https://flownodes.app/docs/media/guides-3d-clones/media-03.png)

Set it’s size to `0.1` in all axis:

![3D Clones — step 4](https://flownodes.app/docs/media/guides-3d-clones/media-04.png)

## Grid

Add a 3D Point [Grid](../nodes/data/point3D.json) (`node:data:point3D:grid`) node, and set it’s origin to `-0.5` in all axis and set the count to `5` in all axis.

![3D Clones — step 5](https://flownodes.app/docs/media/guides-3d-clones/media-05.png)

## Clones

Add a [Clones](../nodes/geometry/resource.json) (`node:geometry:resource:clones`) Geometry node and connect the cube and the grid:

![3D Clones — step 6](https://flownodes.app/docs/media/guides-3d-clones/media-06.png)

This is a basic grid with the position Point 3D list being auto converted to a Transform 3D list.

## Edit

Add an Edit map node and wire in the grid 3D points:

![3D Clones — step 7](https://flownodes.app/docs/media/guides-3d-clones/media-07.png)

Add a [Look At](../nodes/data/quaternion.json) (`node:data:quaternion:lookAt`) node and connect the Point 3D wire to the target:

![3D Clones — step 8](https://flownodes.app/docs/media/guides-3d-clones/media-08.png)

Combine the new Quaternion (3D rotation) with the Position in a Construct 3D Transform node:

![3D Clones — step 9](https://flownodes.app/docs/media/guides-3d-clones/media-09.png)

Wire out the 3D Transform on the right side of the Edit node:

![3D Clones — step 10](https://flownodes.app/docs/media/guides-3d-clones/media-10.png)

Connect the Edit outlet to the Clones Transform inlet node:

![3D Clones — step 11](https://flownodes.app/docs/media/guides-3d-clones/media-11.png)

Here’s the final flow:

![3D Clones — step 12](https://flownodes.app/docs/media/guides-3d-clones/media-12.png)

Here’s the final 3D Geometry:

![3D Clones — step 13](https://flownodes.app/docs/media/guides-3d-clones/media-13.png)

![3D Clones — step 14](https://flownodes.app/docs/media/guides-3d-clones/media-14.png)

> **Tip**
>
> **Tip:** If you want to animate the 3d rotation, use the [Mix](../nodes/general/math.json) (`node:general:math:mix`) node, it will use Spherical Linear Interpolation (slerp) to cross fade two Quaternions.

Here’s the final flow file:

[3D_Clones.flow](https://flownodes.app/docs/media/guides-3d-clones/media-15.flow)
