# User Interface Nodes

Source route: `/docs/info/user-interface-nodes`. Media is not bundled; public route availability must be verified.

There are several nodes to create custom UI. The type that flows in these wires is called **View**.

The View type is a bit different from other value types, it’s interactive, and can change based on user input.

# Control Nodes

![User Interface Nodes — step 1](https://flownodes.app/docs/media/info-user-interface-nodes/media-01.png)

## [Button](../nodes/interface/control.json) (`node:interface:control:button`) Node

The [Button](../nodes/interface/control.json) (`node:interface:control:button`) node has one inlet and two outlets. The inlet is the label view for the button, this can be a text [Label](../nodes/interface/text.json) (`node:interface:text:label`) or any view. The outlets are the button view itself and an action, that is triggered on button release.

![User Interface Nodes — step 2](https://flownodes.app/docs/media/info-user-interface-nodes/media-02.png)

![User Interface Nodes — step 3](https://flownodes.app/docs/media/info-user-interface-nodes/media-03.png)

## [Slider](../nodes/interface/control.json) (`node:interface:control:slider`) Node

The [Slider](../nodes/interface/control.json) (`node:interface:control:slider`) node has one main inlet for the slider value, and a minimum and maximum inlet for the range of values. The Value inlet is a binding inlet, meaning it can *get* and *set* values, it can update values upstream.

It’s recommended to connect the Slider’s Value inlet to a [State](../nodes/data/float.json) (`node:data:float:state`) Float node, to then pass the value downstream.

# Layout Nodes

![User Interface Nodes — step 4](https://flownodes.app/docs/media/info-user-interface-nodes/media-04.png)

## [Vertical](../nodes/interface/stack.json) (`node:interface:stack:vertical`) & [Horizontal](../nodes/interface/stack.json) (`node:interface:stack:horizontal`) Nodes

The [Vertical](../nodes/interface/stack.json) (`node:interface:stack:vertical`) and [Horizontal](../nodes/interface/stack.json) (`node:interface:stack:horizontal`) nodes allow stacking views next to each other.

![User Interface Nodes — step 5](https://flownodes.app/docs/media/info-user-interface-nodes/media-05.png)

## [Layers](../nodes/interface/stack.json) (`node:interface:stack:layers`) Node

The [Layers](../nodes/interface/stack.json) (`node:interface:stack:layers`) node allow depth stacking views in the Z axis.

# Vector and Graphics

![User Interface Nodes — step 6](https://flownodes.app/docs/media/info-user-interface-nodes/media-06.png)

The [Clip Vector](../nodes/interface/modifier.json) (`node:interface:modifier:clipVector`) node allows to clip a view with a vector shape. In this example we’re converting a Graphic node to a interface compatible view type.

![User Interface Nodes — step 7](https://flownodes.app/docs/media/info-user-interface-nodes/media-07.png)

Note that the [Capsule](../nodes/vector/shape.json) (`node:vector:shape:capsule`) node’s size is 100% flex in both width and height. This allows the [Clip Vector](../nodes/interface/modifier.json) (`node:interface:modifier:clipVector`) node to derive it’s shape size based on the aspect ratio from the image.

# Gestures

Gesture nodes need a view to perform the gesture on, so it’s recommended that the first thing to do is to wire in a view on which the gesture will be recognized on.

![User Interface Nodes — step 8](https://flownodes.app/docs/media/info-user-interface-nodes/media-08.png)

## [Tap](../nodes/interface/gesture.json) (`node:interface:gesture:tap`) Node

The [Tap](../nodes/interface/gesture.json) (`node:interface:gesture:tap`) gesture node will send an action on tap along with the location.

> **Tip**
>
> Wire in a [Color](../nodes/interface/control.json) (`node:interface:control:color`) control interface node to test tapping.

![User Interface Nodes — step 9](https://flownodes.app/docs/media/info-user-interface-nodes/media-09.png)

## [Drag](../nodes/interface/gesture.json) (`node:interface:gesture:drag`) Node

The [Drag](../nodes/interface/gesture.json) (`node:interface:gesture:drag`) gesture node allow interaction on a view.

> **Tip**
>
> Use the [Save](../nodes/general/generic.json) (`node:general:generic:save`) node to update a [State](../nodes/data/point.json) (`node:data:point:state`) node with the location.

![User Interface Nodes — step 10](https://flownodes.app/docs/media/info-user-interface-nodes/media-10.png)

## [Key Press](../nodes/interface/gesture.json) (`node:interface:gesture:keyPress`) Node

The [Key Press](../nodes/interface/gesture.json) (`node:interface:gesture:keyPress`) node detects key presses.

It’s required that a view in the hierarchy is in focus to detect key presses.

Here’s what the focus indicators look like:

![User Interface Nodes — step 11](https://flownodes.app/docs/media/info-user-interface-nodes/media-11.png)

![User Interface Nodes — step 12](https://flownodes.app/docs/media/info-user-interface-nodes/media-12.png)
