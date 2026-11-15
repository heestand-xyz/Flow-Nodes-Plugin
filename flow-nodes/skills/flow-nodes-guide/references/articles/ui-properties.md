# Properties

Source route: `/docs/ui/properties`. Media is not bundled; public route availability must be verified.

Properties is where you inspect and edit the selected node or nodes. Select a node on the Canvas to show its name, description, values, and available actions.

## Inspect a node

The top of Properties identifies the selected node. Depending on the node, the panel can include:

- The node's name, type, and icon.
- A description of what the node does.
- Editable properties and actions.
- Links to related information.
- Instance or deprecation information.
- Controls for assets, scripts, files, or other node-specific features.

The properties can be hidden when you want more room for the Canvas.

## Rename nodes

Select the rename button next to the node title, enter a new name, and finish editing to save it.

When several nodes are selected, Properties can show and update their names together. Numbered names remain coordinated where possible.

## Edit values

Each property uses a control suited to its value. Controls can include toggles, text fields, number fields, sliders, color controls, dates, durations, angles, points, sizes, rectangles, transforms, gradients, resolutions, lists, menus, and keyframes.

Some properties can receive their value in different ways:

- **Constant** uses the value entered in Properties.
- **Spatial** changes the value across a 2D or 3D area.
- **Connection** receives the value from another node.
- **Script** calculates the value from an expression.

The available modes depend on the node and property.

## Edit multiple nodes

When you select compatible nodes, Properties shows the settings they share. Changing a shared setting applies it to every selected node.

If the selected nodes currently use different values, the control shows a mixed state, aligning the values allows for edit, the edits apply to all selected nodes.

## Promoted properties and instances

A folder can promote an internal property so it can be edited from outside the folder. An instance can inherit that promoted value or use a local override. Properties indicates when an override is active so you know whether an edit affects the shared source or only the selected instance.
