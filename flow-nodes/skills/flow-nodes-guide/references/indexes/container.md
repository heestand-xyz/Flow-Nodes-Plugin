# Container nodes

Each linked JSON file contains a parent group. Select the entry in `nodes` with the exact listed `typePath` for ports and properties. Prefer visible replacements for new flows.

- **Map / All Satisfy** — Free. [JSON](../nodes/container/map.json) · `node:container:map:allSatisfy`. Check if all the values in the list inlet satisfy some condition. Only when all of the inner value inlets are true, the final outlet will be true.
- **Map / Contains** — Free. [JSON](../nodes/container/map.json) · `node:container:map:contains`. Check if the list inlet contains some value. If one of the inner values inlet is true, the final outlet will also be true.
- **Map / Edit** — Free; deprecated; replacement node:container:map:edit2. [JSON](../nodes/container/map.json) · `node:container:map:edit`. Edit each element in the list inlet.
- **Map / Edit** — Free. [JSON](../nodes/container/map.json) · `node:container:map:edit2`. Edit each element in the list inlet. Includes an internal Index outlet for the current element index.
- **Map / Feedback** — Free. [JSON](../nodes/container/map.json) · `node:container:map:feedback`. Run values through a feedback loop over time.
- **Map / Filter** — Free. [JSON](../nodes/container/map.json) · `node:container:map:filter`. Filter values in a list. If the condition is true, the value will be included in the final list.
- **Map / First** — Free. [JSON](../nodes/container/map.json) · `node:container:map:first`. Find the first value in a list that matches a condition.
- **Map / First Index** — Free. [JSON](../nodes/container/map.json) · `node:container:map:firstIndex`. Find the first index of a value in a list that matches a condition.
- **Map / Group** — Free. [JSON](../nodes/container/map.json) · `node:container:map:group`. Group nodes together for organization.
- **Map / Keyed Edit** — Free. [JSON](../nodes/container/map.json) · `node:container:map:keyedEdit`. Edit key and value in keyed list.
- **Map / Keyed Reduce** — Free. [JSON](../nodes/container/map.json) · `node:container:map:keyedReduce`. Reduce a keyed list to one value in sorted key order. Combine Key, Element, and Previous Result inside the loop, then connect the result to Next Result. Initial supplies the first Previous Result and is returned when the keyed list is empty.
- **Map / Leading Keyed Edit** — Free. [JSON](../nodes/container/map.json) · `node:container:map:leadingKeyedEdit`. Edit the values of a keyed list and output them as a list.
- **Map / Loop** — Free. [JSON](../nodes/container/map.json) · `node:container:map:loop`. Loop through a flow.
- **Map / Reduce** — Free. [JSON](../nodes/container/map.json) · `node:container:map:reduce`. Reduce a list inlet down to one value outlet. Combine the two values in the reduce loop. Note that the initial value is used as the previous result in the first run of the loop.
- **Map / Slice Edit** — Free. [JSON](../nodes/container/map.json) · `node:container:map:sliceEdit`. Edit a slice of elements in the list inlet. The slice count defines how many elements to edit.
- **Map / Sort** — Free. [JSON](../nodes/container/map.json) · `node:container:map:sort`. Sort an array by comparing pairs of elements inside the map. Provide a Leading First decision to determine ordering, with optional order reversal.
- **Map / Tool** — Free. [JSON](../nodes/container/map.json) · `node:container:map:tool`. Build a tool that can be used in chat intelligence node.
- **Map / Trailing Keyed Edit** — Free. [JSON](../nodes/container/map.json) · `node:container:map:trailingKeyedEdit`. Edit a list while assigning keys and output it as a keyed list.
- **Map / Tree** — Free. [JSON](../nodes/container/map.json) · `node:container:map:tree`. Recursively create a tree structure.
- **Map / UV Edit** — Free. [JSON](../nodes/container/map.json) · `node:container:map:uvEdit`. Edit a graphic by modifying unit UV coordinates. The final external outlet remaps the external inlet with the internal inlet's colors. The red channel is x and the green channel is y. Black color is the top left pixel and yellow color is the bottom right pixel.
- **Map / Video Edit** — Pro. [JSON](../nodes/container/map.json) · `node:container:map:videoEdit`. Edit each frame in a video.
- **Map / Video Record** — Free. [JSON](../nodes/container/map.json) · `node:container:map:videoRecord`. Record a video frame by frame with graphics. The speed at which the video is recorded is not the same as the final output. The recording graphics might be faster or slower depending on how heavy the mapped nodes are, this node records as fast as possible. The final video will have the specified frame rate. The destination inlet is used to save the final video. Typically wire in an empty state video node.
- **Map / Zip Edit** — Free. [JSON](../nodes/container/map.json) · `node:container:map:zipEdit`. Combine two lists to one list.
- **Patch / Folder** — Free. [JSON](../nodes/container/patch.json) · `node:container:patch:folder`. A folder is a patch that contains its own flow. Auto create in and outlets by wiring to a folder.
