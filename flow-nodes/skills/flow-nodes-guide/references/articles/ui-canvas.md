# Canvas

Source route: `/docs/ui/canvas`. Media is not bundled; public route availability must be verified.

The Canvas is where you build and edit a flow. Nodes hold values or perform operations, and wires carry values between their outlets and inlets.

## Move around the Canvas

- Drag empty space to pan across the flow. (Scroll on trackpad or secondary click and drag)
- Pinch or scroll to zoom in and out. Pinching over nodes will also zoom the canvas.
- Drag near an edge while moving nodes to continue panning beyond the visible area.

Each tab or split section keeps its own Canvas position and zoom, so you can view different parts of the same flow at once.

## Select and move nodes

Select a node to see it’s shortcuts, like inspecting it’s Properties. Select multiple nodes when you want to move or edit them together. If the nodes have the same properties, tho they have different values, there is an option to align the values.

Drag a selected node to reposition it. If dropped overlapping with another node, it will move away, not to overlap. When snapping is enabled in Settings, guides appear to help align nodes.

## Add and connect nodes

Open the Node Creator (tip: double tap on canvas) to add a node at a location on the Canvas. You can also begin a connection from an inlet or outlet, release the wire where you want the node to appear, the wire actions will appear, and then use Node Creator (plus button) to find a compatible node.

To make a connection, drag between a node's outlet and a compatible inlet. While you drag, Flow Nodes previews the wire and shows valid connection targets.

Use a node, let, wire, or Canvas context menu for additional actions when available. These actions can include duplicating, grouping, converting, disconnecting, or removing nodes.

## Open a folder node

A folder node can contain another graph. Open it to work with the nodes inside. The path controls above the Canvas show your current location and let you return to a parent folder.

Zoom in on a folder node to enter it, and once inside, zoom out of the canvas to exit it.

## Input methods

The Canvas supports the input methods available on your device, including touch, mouse, trackpad, and keyboard. Nodes and their inlets and outlets provide accessible controls in addition to their visual connection points.
