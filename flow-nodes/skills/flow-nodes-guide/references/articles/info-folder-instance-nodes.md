# Folder & Instance Nodes

Source route: `/docs/info/folder-instance-nodes`. Media is not bundled; public route availability must be verified.

A flow is actually just a folder node. This makes is possible to instance a flow, inside another flow.

![Folder & Instance Nodes — step 1](https://flownodes.app/docs/media/info-folder-instance-nodes/media-01.png)

Tap this button in the toolbar to add a flow to the current flow.

Then choose between adding as a copy or as an instance.

### Folder Node

![Folder & Instance Nodes — step 2](https://flownodes.app/docs/media/info-folder-instance-nodes/media-02.png)

A folder node can contain nodes and can connect to the outside via the leading or trailing side.

Drag a new wire close to a side to create a new folder in or outlet. The new connection will be available both inside and outside the folder node.

### Instance Node

![Folder & Instance Nodes — step 3](https://flownodes.app/docs/media/info-folder-instance-nodes/media-03.png)

An instance node is a link to another flow. Editing the source flow through an instance affects that flow everywhere it is used. Promoted property overrides on an instance apply only to that instance.

There are node context menu options to convert a folder node to a instance node and a instance node to a folder node. When converting a folder node to an instance node a new flow will be created.

### Promoted Properties

![Folder & Instance Nodes — step 4](https://flownodes.app/docs/media/info-folder-instance-nodes/media-04.png)

Use the promote control on an eligible property to make it available on the containing folder. The screenshots below use the earlier “publish” terminology.

A promoted property is available on the folder node. This allows for more quick edits.

Properties can be promoted multiple folder levels up.
