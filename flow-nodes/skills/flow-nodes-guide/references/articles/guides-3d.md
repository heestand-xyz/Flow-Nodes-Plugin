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

[Cube](../nodes/node-geometry-shape-cube2.json)

## Clone the Cube

![3D — step 3](https://flownodes.app/docs/media/guides-3d/media-03.png)

Next add a Grid node (3D Point).

Set the count to 3x3x3 and set the center to 0.0 on all axis.

Then create a Clone Transform node.

And finally connect the nodes.

> **Note**
>
> Clone Transform is pro node and requires Pro access (a subscription or Lifetime unlock).

[Grid](../nodes/node-data-point3D-grid.json)

[Clone Transform](../nodes/node-spatial-entity-cloneTransform.json)

## Render the Cubes

![3D — step 4](https://flownodes.app/docs/media/guides-3d/media-04.png)

In this step we add the 3D Render node and connect the cloned cubes. The render node requires a camera, so add a perspective camera and a directional light.

[3D Render](../nodes/node-graphic-engine-kagamiRender.json)

[Perspective](../nodes/node-spatial-camera-perspective.json)

[Directional](../nodes/node-spatial-light-directional.json)

## Post Processing

![3D — step 5](https://flownodes.app/docs/media/guides-3d/media-05.png)

Add a Levels node and invert the graphic, and adjust brightness and contrast as needed.

[Levels](../nodes/node-graphic-colorEffect-levels.json)

## Animate the Camera

![3D — step 6](https://flownodes.app/docs/media/guides-3d/media-06.png)

To animate the camera we can use a Wave node (X axis), along with a float state (Z axis), that we can connect to a Construct 3D Point node.

[Wave](../nodes/node-realtime-modulator-wave.json)

Then we can use that 3D point as position for the camera and make use of a Look At node to orient the camera towards the center. (Make sure connect the 3D point to Eye and set the Target to 0.0 the Z axis).

[Look At](../nodes/node-data-quaternion-lookAt.json)

## Final Render

![3D — step 7](https://flownodes.app/docs/media/guides-3d/media-07.png)

The final flow should look something like this.

[3D — video 8](https://flownodes.app/docs/media/guides-3d/media-08.mp4)

## Final Flow File

Here’s the final flow file used to create this guide.

[3D_Cubes.flow](https://flownodes.app/docs/media/guides-3d/media-09.flow)
