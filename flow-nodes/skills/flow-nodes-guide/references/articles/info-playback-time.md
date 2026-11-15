# Playback Time

Source route: `/docs/info/playback-time`. Media is not bundled; public route availability must be verified.

Some nodes are time based, like the [Clock](../nodes/node-general-time-clock.json) node, [Delay](../nodes/node-general-time-delay.json) node, [Stopwatch](../nodes/node-general-time-stopwatch2.json) node and even the [Camera](../nodes/node-graphic-resource-camera.json) node. When these nodes are added to a flow, a playback button will appear. This allows you to pause and play all the nodes with a time component.

![Playing](https://flownodes.app/docs/media/info-playback-time/media-01.png)

![Paused](https://flownodes.app/docs/media/info-playback-time/media-02.png)

> **Tip**
>
> Keyboard shortcuts: **Play**: Command + I, **Pause**: Command + O.

Time based nodes can be heavy, so keep an eye out for the memory warning. If you get a memory warning, time will automatically pause to avoid a crash of running out of memory. (This can be disabled in the settings)

## Time in Scripts

When writing a script in a property or the [Script](../nodes/node-general-code-script.json) node, there is a function called `time()`. This will return a float value with seconds since the app was launched.

[Script Guide](scripts-guide.md)

[Script Reference](scripts-reference.md)
