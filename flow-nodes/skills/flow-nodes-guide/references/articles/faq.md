# FAQ

Source route: `/docs/faq`. Media is not bundled; public route availability must be verified.

- What **platforms** are supported?
  - The app is built with Swift and Metal for Apple platforms, and use a lot of platform specific APIs. Flow Nodes is made for iPhone, iPad, Mac and Vision Pro.
- What is the minimum required **OS version**?
  - iOS 26, macOS 26 or visionOS 26 or newer.
- What are the **in-app-purchases**?
  - Most nodes are free to use, tho some **Pro** **Nodes** require a subscription.
  - There is also a **Lifetime** unlock of **Pro Nodes** available.
  - In Flow Nodes 3, there were some node bundles available, they are still valid if previously purchased.
- How to go fully **offline** without **iCloud** and keep flows?
  - Flows made with iCloud active are connected to your iCloud account, once iCloud is disabled they still stay in iCloud but are removed from the local app
  - To go fully offline follow these steps:
    - Export flows to Files
    - Remove flows in app (optional)
    - Disable iCloud in Settings app
    - Import flows from Files
- Is there any device **performance** **requirements**?
  - Flow Nodes is a performance intensive app and a newer Apple device are recommended for a smoother experience. Tho there is not a fixed performance requirement, it depends on what nodes are in the flow (a node graph project).
- Some nodes are **deprecated**, what does that mean?
  - This means that the node has stopped being supported, this usually means a new node has been created to replace the old node.
  - It’s recommended to replace the old deprecated node with the new node.
  - Tho the old node will still continue to work, but it might not have the latest features.
- Is there a way to **export flows** as backups?
  - Yes, you can export a flow in it’s context menu in home, or in the toolbar context menu there is an option to export all flows.
- Is there a way to **import flows**?
  - Yes, share a flow with the app, drag and drop or use the import option in the toolbar context menu.
- What **AI** is powering the **chat**?
  - Apple’s Foundation Models. Offline on-device by default and Apple’s Private Cloud Compute model is available on OS 27 or newer.
- What is the **requirements** to use the **AI** chat and nodes?
  - The device needs to have support for Apple Intelligence.
- How to **play** a **video**?
  - Use the new [Player](../nodes/video/resource.json) (`node:video:resource:player`) node by wiring in a [State](../nodes/video/resource.json) (`node:video:resource:state`) node.
- How to **edit** a **video**?
  - To edit each frame with the same graphic effect, use the [Video Edit](../nodes/container/map.json) (`node:container:map:videoEdit`) node.
- How to *manually* **seek** a **video**?
  - Use the [Sample](../nodes/video/resource.json) (`node:video:resource:sample`) node. It takes a frame index as input. Find the frame count with the [Metadata](../nodes/video/resource.json) (`node:video:resource:metadata`) node. Use a [Slider](../nodes/interface/control.json) (`node:interface:control:slider`) node along with a math [Operation](../nodes/general/math.json) (`node:general:math:operation`) node to calculate the frame index.
    [Video Guide](guides-video.md)
- How to **record** a **video**?
  - Use the record video node action on graphic nodes, or the [Record](../nodes/video/resource.json) (`node:video:resource:record`) node to create a video from a live stream of Graphics.
- How to **import** an **image**?
  - Drag and drop an image onto the canvas or import at the top of the node creation panel.
- When importing, what is **State node** asset vs file **Link node**?
  - The **state nodes** store it’s file as an **asset** in the flow and syncs across iCloud.
  - The **file link** **node** only reference the file from your file system, it does not copy over your file into the flow.
    - Updating a file node upstream can override your file if writing is enabled on the node in properties.
- How to **export** an **image**?
  - Open the node context menu by tapping the title or the three dots icon on iOS & visionOS, or right click on macOS, then export to Photos or Files.
- How do I blend two images with a **blending mode**?
  - Two Graphics can be blended with the [Blend](../nodes/graphic/modifierEffect.json) (`node:graphic:modifierEffect:blend`) node.
- How to **animate** inlets and properties?
  - Use the [Stopwatch](../nodes/general/time.json) (`node:general:time:stopwatch2`) node or the `time()` script.
- How to do **math** operations?
  - Use the [Operation](../nodes/general/math.json) (`node:general:math:operation`) or [List Operation](../nodes/general/math.json) (`node:general:math:listOperation`) nodes.
- What are the keyboard shortcuts to play and pause time?
  - Play `Cmd + I`
  - Pause `Cmd + O`
- What **language** are **scripts** written in?
  - JavaScript

    [Script Guide](scripts-guide.md)

    [Script Reference](scripts-reference.md)
- What **language** are **shaders** written in?
  - Metal
    [Shader Guide](shaders-guide.md)

    [Shader Reference](shaders-reference.md)
- What are **bits** in **Graphics**?
  - Bits is the color depth. `8 bit` is default and render colors in `256` steps, between `0` and `255`. `16 bit` allows for more accurate colors, and are defined as a floating point between `0.0` and `1.0`, tho also allow channel values below `0.0` and above `1.0`. This allows for XDR colors on supported displays. `32 bit` have even more accuracy.
- What is the difference between **instancing** and **copying** a **flow** into another flow?
  - Copy will re create all nodes in a new folder with the same node content and properties.
  - Instance will reference the flow as a linked instance “folder”.
    - Edits to the source flow through an instance (indicated by a green color) affect the original flow. Promoted property overrides on an instance apply only to that instance.
- What does the **Restore All Demos** button do?
  - Demos can be edited, and if nodes are removed or changed, this option will reset the demos to their original setup. A tip is to duplicate a demo before editing it.
- What is the **Show Flow Assets** setting?
  - All assets (images, videos, etc) in a flow will appear as a thumbnail on the top left of the flow thumbnail in the home view.
- What is the **Show Flow Outputs** setting?
  - All content from the top level outlets in a flow will appear as a thumbnail on the top right of the flow thumbnail in the home view.
- What is the **Patch Node Preview** setting?
  - This will display a mini abstract representation of the nodes in a folder node.
- What is the **Node Speedometer** setting?
  - This will show an indicator on the node if it’s content takes a long time to load.
- What is the **Pause Time on Flow Open** setting?
  - Use this to recover heavy projects that have a node with time. *(Default off)*
- What is the **Dynamic Graphic Resolution** setting?
  - This enables relative graphic render resolutions based on canvas zoom for graphics content views. This does not affect exported resolutions. Also this is auto disabled if the view resolution is higher than or equal to the content resolution, so it should not affect fullscreen presentations. Only disable this if your render requires fixed resolutions though the full pipeline. *(Default on)*
- How to force update the **MCP** on macOS?
  - If previously installed, new versions should update on restart of agent app.
  - For a force update, first remove it from Codex / Claude, then simply re-add it.

    - Instructions and commands are in the Flow Nodes MCP settings panel.
- If the app is **crashing on launch**, what to do?
  - There was a bug that cased crashes in versions from 4.0.0 to 4.2.0, in version 4.3.0 some bugs were fixed and in 4.4.0 some more. Tho for users who have not updated the app in a while, it might still crash on launch. The first thing to try is to update to the latest version on App Store. If that does not help, the only way is unfortunately to remove the app and download it again. If iCloud syncing was enabled, flows might recover, tho this is not guaranteed.
  - If running on macOS, the flow database is stored outside the app, so removing the app might not solve the issue.
    - The database folder is located in one of these folders, depending on app version:
      - `~/Library/Containers/xyz.heestand.flow/Data/Library/Application\ Support/`
      - `~/Library/Group Containers/group.xyz.heestand.flow/Library/Application Support/`
    - The database files are:
      - `default.store`
      - `default.store-shm`
      - `default.store-wal`
    - Remove them only as a last resort to recover the app on macOS.

      > **Warning**
      >
      > Removing database files deletes local flow data. Quit the app and back up the database folder first. iCloud recovery is not guaranteed.
