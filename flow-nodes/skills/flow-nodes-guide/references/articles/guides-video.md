# Video Guide

Source route: `/docs/guides/video`. Media is not bundled; public route availability must be verified.

Flow Nodes have two 2D visual types represented by pixels; video and graphic (an image).

## Playing

To play a video, add the new **Player** node.

[Player](../nodes/video/resource.json) (`node:video:resource:player`)

This node takes video in and returns graphic out.

The new node is available in Flow Nodes 4.

## **Sampling**

To sample a video frame into a graphic, use the Sample node.

[Sample](../nodes/video/resource.json) (`node:video:resource:sample2`)

Once you got the video frame, you can apply any graphic effect to it.

> **Tip**
>
> To get the frame count and fps of a video, use the video Metadata node.
>
> [Metadata](../nodes/video/resource.json) (`node:video:resource:metadata`)

## **Editing**

To edit every frame in a video, a [Video Edit](../nodes/container/map.json) (`node:container:map:videoEdit`) node is required. It will loop through every frame in the video and apply the edit you specify. This map node takes two video inputs, the source and destination. Destination can be an empty video [State](../nodes/video/resource.json) (`node:video:resource:state`) node.

[Video Edit](../nodes/container/map.json) (`node:container:map:videoEdit`)

## **Seeking**

![Video — step 1](https://flownodes.app/docs/media/guides-video/media-01.png)

If you want to seek the video with a slider, see the demo in the app or follow this guide:

1. Add a video [State](../nodes/video/resource.json) (`node:video:resource:state`) node and load in your video.
   1. Alternatively long press in iOS or right click on macOS, and import the video from the context menu or import it from the node creation panel.
2. Add a video [Metadata](../nodes/video/resource.json) (`node:video:resource:metadata`) node, this node can read the resolution along with the frame count.
   1. Wire the video outlet on the video state node to the metadata node.
   2. The frame count will be needed to calculate the frame index.
3. Add a [Slider](../nodes/interface/control.json) (`node:interface:control:slider`) node.
   1. This node takes a binding to a float value as it’s input, a binding (a double wire).
   2. To get the value we will need to wire upstream (left) to a state.
4. Add a float [State](../nodes/data/float.json) (`node:data:float:state`) node, this will be the “source of truth” of the seek value.
   1. Wire it to the slider node.
5. Add two math [Operation](../nodes/general/math.json) (`node:general:math:operation`) nodes, these will be used to map the sliders float value between `0.0` and `1.0` to the frame index.
   1. Wire the frame count from the metadata node to the first operation node.
   2. Set the first operation node to subtract `1` from the frame count. As the last frame index (zero based) is frame count minus one.
   3. Next wire the first operation node to the leading inlet of the second operation node and the float state to the trailing inlet. And set the node to multiply.
6. Finally add a [Sample](../nodes/video/resource.json) (`node:video:resource:sample`) node and wire the second operation outlet to the frame index and the wire in the video.
7. Now you should be able to seek the video with the slider.
