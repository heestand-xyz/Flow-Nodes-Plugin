# Video nodes

Read the linked JSON for exact ports and properties. Prefer visible replacements for new flows.

- **Modifier / List Relay** — Free. [JSON](../nodes/node-video-modifier-listRelay.json) · `node:video:modifier:listRelay`. Relay a list of videos. This node has no effect. Tho useful to define a type when wiring to generics.
- **Modifier / Relay** — Free. [JSON](../nodes/node-video-modifier-relay.json) · `node:video:modifier:relay`. Relay a video. This node has no effect. Tho useful to define a type when wiring to generics.
- **Resource / List State** — Free. [JSON](../nodes/node-video-resource-listState.json) · `node:video:resource:listState`. Store a list of videos.
- **Resource / Metadata** — Free. [JSON](../nodes/node-video-resource-metadata.json) · `node:video:resource:metadata`. Information about details of a video.
- **Resource / Player** — Free. [JSON](../nodes/node-video-resource-player.json) · `node:video:resource:player`. Play a video stream of graphics.
- **Resource / Record** — Free. [JSON](../nodes/node-video-resource-record.json) · `node:video:resource:record`. Record live graphics to a video.
- **Resource / Sample** — Free; deprecated; replacement node:video:resource:sample2. [JSON](../nodes/node-video-resource-sample.json) · `node:video:resource:sample`. Sample a graphic from a video at a specific frame index. This can be used to seek in a video.
- **Resource / Sample** — Free. [JSON](../nodes/node-video-resource-sample2.json) · `node:video:resource:sample2`. Sample a graphic from a video using seek time, frame index, or a progress (0.0 to 1.0).
- **Resource / Save Graphics** — Free. [JSON](../nodes/node-video-resource-saveGraphics.json) · `node:video:resource:saveGraphics`. Save graphics to a video. Connect the destination inlet to a State Video Node. All graphics are required to have the same resolution.
- **Resource / State** — Free. [JSON](../nodes/node-video-resource-state.json) · `node:video:resource:state`. Store a video.
