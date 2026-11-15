# User Interface Nodes

Source route: `/docs/info/user-interface-nodes`. Media is not bundled; public route availability must be verified.

There are several nodes to create custom UI. The type that flows in these wires is called **View**.

The View type is a bit different from other value types, it’s interactive, and can change based on user input.

# Control Nodes

![User Interface Nodes — step 1](https://flownodes.app/docs/media/info-user-interface-nodes/media-01.png)

## [Button](../nodes/node-interface-control-button.json) Node

The [Button](../nodes/node-interface-control-button.json) node has one inlet and two outlets. The inlet is the label view for the button, this can be a text [Label](../nodes/node-interface-text-label.json) or any view. The outlets are the button view itself and an action, that is triggered on button release.

![User Interface Nodes — step 2](https://flownodes.app/docs/media/info-user-interface-nodes/media-02.png)

![User Interface Nodes — step 3](https://flownodes.app/docs/media/info-user-interface-nodes/media-03.png)

## [Slider](../nodes/node-interface-control-slider.json) Node

The [Slider](../nodes/node-interface-control-slider.json) node has one main inlet for the slider value, and a minimum and maximum inlet for the range of values. The Value inlet is a binding inlet, meaning it can *get* and *set* values, it can update values upstream.

It’s recommended to connect the Slider’s Value inlet to a [State](../nodes/node-data-float-state.json) Float node, to then pass the value downstream.

# Layout Nodes

![User Interface Nodes — step 4](https://flownodes.app/docs/media/info-user-interface-nodes/media-04.png)

## [Vertical](../nodes/node-interface-stack-vertical.json) & [Horizontal](../nodes/node-interface-stack-horizontal.json) Nodes

The [Vertical](../nodes/node-interface-stack-vertical.json) and [Horizontal](../nodes/node-interface-stack-horizontal.json) nodes allow stacking views next to each other.

![User Interface Nodes — step 5](https://flownodes.app/docs/media/info-user-interface-nodes/media-05.png)

## [Layers](../nodes/node-interface-stack-layers.json) Node

The [Layers](../nodes/node-interface-stack-layers.json) node allow depth stacking views in the Z axis.

# Vector and Graphics

![User Interface Nodes — step 6](https://flownodes.app/docs/media/info-user-interface-nodes/media-06.png)

The [Clip Vector](../nodes/node-interface-modifier-clipVector.json) node allows to clip a view with a vector shape. In this example we’re converting a Graphic node to a interface compatible view type.

![User Interface Nodes — step 7](https://flownodes.app/docs/media/info-user-interface-nodes/media-07.png)

Note that the [Capsule](../nodes/node-vector-shape-capsule.json) node’s size is 100% flex in both width and height. This allows the [Clip Vector](../nodes/node-interface-modifier-clipVector.json) node to derive it’s shape size based on the aspect ratio from the image.

# Gestures

Gesture nodes need a view to perform the gesture on, so it’s recommended that the first thing to do is to wire in a view on which the gesture will be recognized on.

![User Interface Nodes — step 8](https://flownodes.app/docs/media/info-user-interface-nodes/media-08.png)

## [Tap](../nodes/node-interface-gesture-tap.json) Node

The [Tap](../nodes/node-interface-gesture-tap.json) gesture node will send an action on tap along with the location.

> **Tip**
>
> Wire in a [Color](../nodes/node-interface-control-color.json) control interface node to test tapping.

![User Interface Nodes — step 9](https://flownodes.app/docs/media/info-user-interface-nodes/media-09.png)

## [Drag](../nodes/node-interface-gesture-drag.json) Node

The [Drag](../nodes/node-interface-gesture-drag.json) gesture node allow interaction on a view.

> **Tip**
>
> Use the [Save](../nodes/node-general-generic-save.json) node to update a [State](../nodes/node-data-point-state.json) node with the location.

![User Interface Nodes — step 10](https://flownodes.app/docs/media/info-user-interface-nodes/media-10.png)

## [Key Press](../nodes/node-interface-gesture-keyPress.json) Node

The [Key Press](../nodes/node-interface-gesture-keyPress.json) node detects key presses.

It’s required that a view in the hierarchy is in focus to detect key presses.

Here’s what the focus indicators look like:

![User Interface Nodes — step 11](https://flownodes.app/docs/media/info-user-interface-nodes/media-11.png)

![User Interface Nodes — step 12](https://flownodes.app/docs/media/info-user-interface-nodes/media-12.png)
