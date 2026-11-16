# 3D Guide

Source route: `/docs/guides/3d`. Media is not bundled; public route availability must be verified.

To render 3D objects in Flow Nodes, the general pipeline is:  
**Geometry → Fields → Entities → Render → Graphic  
**In this guide we’ll go through these various 3D node types.

[3D Reference](references-3d.md)

This guide will show you how to render, animate and post process some cloned cubes.

> **Note**
>
> Note that this guide makes use of pro nodes and requires Pro access (a subscription or Lifetime unlock).

![3D — step 1](https://flownodes.app/docs/media/guides-3d/media-01.png)

## Create a Cube

![3D — step 2](https://flownodes.app/docs/media/guides-3d/media-02.png)

Start by creating a Cube geometry node.

[Cube](../nodes/geometry/shape.json) (`node:geometry:shape:cube2`)

## Clone the Cube

![3D — step 3](https://flownodes.app/docs/media/guides-3d/media-03.png)

Next add a Grid node (3D Point).

Set the count to 3x3x3 and set the center to 0.0 on all axis.

Then create a Clone Transform node.

And finally connect the nodes.

> **Note**
>
> Clone Transform is pro node and requires Pro access (a subscription or Lifetime unlock).

[Grid](../nodes/data/point3D.json) (`node:data:point3D:grid`)

[Clone Transform](../nodes/spatial/entity.json) (`node:spatial:entity:cloneTransform`)

## Render the Cubes

![3D — step 4](https://flownodes.app/docs/media/guides-3d/media-04.png)

In this step we add the 3D Render node and connect the cloned cubes. The render node requires a camera, so add a perspective camera and a directional light.

[3D Render](../nodes/graphic/engine.json) (`node:graphic:engine:kagamiRender`)

[Perspective](../nodes/spatial/camera.json) (`node:spatial:camera:perspective`)

[Directional](../nodes/spatial/light.json) (`node:spatial:light:directional`)

## Post Processing

![3D — step 5](https://flownodes.app/docs/media/guides-3d/media-05.png)

Add a Levels node and invert the graphic, and adjust brightness and contrast as needed.

[Levels](../nodes/graphic/colorEffect.json) (`node:graphic:colorEffect:levels`)

## Animate the Camera

![3D — step 6](https://flownodes.app/docs/media/guides-3d/media-06.png)

To animate the camera we can use a Wave node (X axis), along with a float state (Z axis), that we can connect to a Construct 3D Point node.

[Wave](../nodes/realtime/modulator.json) (`node:realtime:modulator:wave`)

Then we can use that 3D point as position for the camera and make use of a Look At node to orient the camera towards the center. (Make sure connect the 3D point to Eye and set the Target to 0.0 the Z axis).

[Look At](../nodes/data/quaternion.json) (`node:data:quaternion:lookAt`)

## Final Render

![3D — step 7](https://flownodes.app/docs/media/guides-3d/media-07.png)

The final flow should look something like this.

[3D — video 8](https://flownodes.app/docs/media/guides-3d/media-08.mp4)

## Final Flow File

Here’s the final flow file used to create this guide.

[3D_Cubes.flow](https://flownodes.app/docs/media/guides-3d/media-09.flow)
