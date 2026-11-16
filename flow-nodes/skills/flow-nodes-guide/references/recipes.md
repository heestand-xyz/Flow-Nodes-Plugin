# Worked wiring recipes

These plans were checked against the bundled node definitions and selected implementation code. They have not been executed in the app as part of plugin creation. Read each selected node's JSON before adapting the recipe. Verify device/version and existing Pro access when relevant.

Each record link opens a parent JSON file. Select the entry in its `nodes` array with the exact linked `typePath`; several nodes, including deprecated variants, share the same file.

## A slider controls image blur

Create **State — Graphic / Resource**, **State — Data / Float**, **Slider — Interface / Control**, and **Blur — Graphic / Space Effect**. Import an image into Graphic State. Set Float State Value to 10; set Slider Minimum to 0 and Maximum to 50 as example values. These slider settings are a useful chosen range, not catalog defaults. Choose Gaussian blur for a simple starting point.

| From · outlet | To · inlet | Meaning |
| --- | --- | --- |
| Graphic State · Graphic | Blur · Graphic | Image to process. |
| Float State · Value | Slider · Value | Writable Float binding. |
| Float State · Value | Blur · Radius | The same stored Float drives the radius. |

Show the Slider's View and Blur's Graphic. Moving the slider updates the Float State and changes the blur. Do not wire Slider View into Blur Radius.

Records: [`node:graphic:resource:state`](nodes/graphic/resource.json), [`node:data:float:state`](nodes/data/float.json), [`node:interface:control:slider`](nodes/interface/control.json), [`node:graphic:spaceEffect:blur`](nodes/graphic/spaceEffect.json).

## Scrub a video with a slider

Use **State — Video / Resource**, **State — Data / Float**, **Slider**, and the current **Sample — Video / Resource** (`sample2`). Import the video. Set the Slider range to 0…1, Float State to 0, and Sample **Seek Mode** to **Fraction**.

| From · outlet | To · inlet | Meaning |
| --- | --- | --- |
| Video State · Video | Sample · Video | Source video. |
| Float State · Value | Slider · Value | Writable position. |
| Float State · Value | Sample · Seek Fraction | Normalized video position. |

Show Slider View and Sample Graphic. The current Sample evaluates its selected position; it has no Seek action inlet. The Player node is a different node and has a Seek action. Do not mix their signatures.

The older Video Guide uses Frame Count minus one multiplied by the slider fraction, followed by frame-index sampling. Use that when explaining an older saved graph; for a new current flow, fraction sampling avoids those math nodes. If using Frame Index, select that Seek Mode and use **Seek Frame Index** on the current node.

Records: [`node:video:resource:state`](nodes/video/resource.json), [`node:video:resource:sample2`](nodes/video/resource.json), [`node:video:resource:player`](nodes/video/resource.json), [`node:data:float:state`](nodes/data/float.json), [`node:interface:control:slider`](nodes/interface/control.json).

## Apply an effect to every video frame

Create a source Video State, a separate empty destination Video State, **Video Edit — Container / Map**, and Blur inside the Video Edit map. Video Edit requires Pro access in this snapshot.

| From · outlet | To · inlet | Scope |
| --- | --- | --- |
| Source Video State · Video | Video Edit · Source | External. |
| Destination Video State · Video | Video Edit · Destination | External writable binding. |
| Video Edit · Frame | Blur · Graphic | Internal output into the map body. |
| Blur · Graphic | Video Edit · Frame | Body result into the internal input. |

Set Blur Radius. Trigger Video Edit **Start Render**, or connect an Action to its external **Render** inlet. Observe rendering progress. After completion, the destination State stores the edited video; connect that State's Video to a Player for playback. Do not look for a Video Edit Video output; none is defined.

Records: [`node:video:resource:state`](nodes/video/resource.json), [`node:container:map:videoEdit`](nodes/container/map.json), [`node:graphic:spaceEffect:blur`](nodes/graphic/spaceEffect.json), [`node:video:resource:player`](nodes/video/resource.json).

## Multiply each Float in a list

Create **List State — Data / Float**, current **Edit — Container / Map** (`edit2`), and **Operation — General / Math** inside the map. Enter example list values 1, 2, 3. Set Operation **Operation** to Multiply and its **Value** property to 2 (this property supplies the Trailing inlet).

| From · outlet | To · inlet | Scope |
| --- | --- | --- |
| Float List State · Values | Edit · Array In | External Multi. |
| Edit · Element Out | Operation · Leading | Internal current Float. |
| Operation · Value | Edit · Element In | Internal transformed Float. |

Read the external **Array Out**; it should contain 2, 4, 6. **Index** is an optional internal Int output, not the current element. Keep the type Float throughout this example.

Records: [`node:data:float:listState`](nodes/data/float.json), [`node:container:map:edit2`](nodes/container/map.json), [`node:general:math:operation`](nodes/general/math.json).

## Save a value when a button is pressed

Create two Float States named Source and Saved, **Save — General / Generic**, **Button — Interface / Control**, and **Label — Interface / Text**. Set the Label's text to an appropriate title using its documented property and connect its View to Button View.

| From · outlet | To · inlet | Meaning |
| --- | --- | --- |
| Source · Value | Save · Source | Value to copy. |
| Saved · Value | Save · Destination | Writable storage. |
| Button · Action | Save · Save | Trigger the copy. |

Display Button View and press the button. Saved receives the Source value. Save has no outlet and does not automatically run just because Source changes.

Records: [`node:data:float:state`](nodes/data/float.json), [`node:general:generic:save`](nodes/general/generic.json), [`node:interface:control:button`](nodes/interface/control.json), [`node:interface:text:label`](nodes/interface/text.json).

## Render a cube

Create current **Cube — 3D Geometry / Shape** (`cube2`), **Perspective — 3D Spatial / Camera**, **Directional — 3D Spatial / Light**, and **3D Render — Graphic / Engine** (`kagamiRender`). Use the camera and geometry defaults as a starting point and adjust framing if needed.

The Render node has one Multi **Entities** input. The cube, camera, and light feed that input through the supported 3D-to-Entity conversions described in the 3D Reference. There is no separate Camera inlet on this Render node. Inspect the producer JSON for its exact outlet name before presenting the final wiring table. Display Render **Graphic**.

For clones, add **Clone Transform — 3D Spatial / Entity**, which requires Pro access, and a list of 3D transforms, for example the 3D Point Grid used with conversion in the 3D Guide. Feed the cube into Clone Transform **Entity**, transforms into **Transforms**, and its Entity output into Render **Entities** alongside the camera and light. Do not mix this with the deprecated Geometry Clones signature.

Records: [`node:geometry:shape:cube2`](nodes/geometry/shape.json), [`node:spatial:camera:perspective`](nodes/spatial/camera.json), [`node:spatial:light:directional`](nodes/spatial/light.json), [`node:graphic:engine:kagamiRender`](nodes/graphic/engine.json), [`node:spatial:entity:cloneTransform`](nodes/spatial/entity.json), [`node:data:point3D:grid`](nodes/data/point3D.json).
