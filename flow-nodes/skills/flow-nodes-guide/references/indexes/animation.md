# Animation nodes

Each linked JSON file contains a parent group. Select the entry in `nodes` with the exact listed `typePath` for ports and properties. Prefer visible replacements for new flows.

- **Resource / Keyframe** — Free. [JSON](../nodes/animation/resource.json) · `node:animation:resource:keyframe`. A keyframe time and easing.
- **Resource / Keyframes State** — Free. [JSON](../nodes/animation/resource.json) · `node:animation:resource:keyframesState`. Stored keyframes with values of a type.
- **Resource / Timeline** — Pro. [JSON](../nodes/animation/resource.json) · `node:animation:resource:interpolate`. Interpolate keyframes over time.
- **Resource / Waveform** — Free. [JSON](../nodes/animation/resource.json) · `node:animation:resource:waveform`. A waveform is represented by a keyed list of keyframes with Float values. Combine multiple waveforms to create a complex wave. Animatable with the Interpolate node.
