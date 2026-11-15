# Performance Statistics

Source route: `/docs/ui/performance-statistics`. Media is not bundled; public route availability must be verified.

Performance Statistics displays the current frame rate while you work in a flow. Use it to check how smoothly Flow Nodes is drawing the interface and animated content.

## Show the frame rate

1. Open **Settings**.
2. Select **Time**.
3. Turn on **Frame Rate Indicator**.

An indicator appears over the flow and reports the measured rate in frames per second, shown as **fps**. Turn off **Frame Rate Indicator** to hide it.

## Read the indicator

The number estimates how many frames Flow Nodes is displaying each second. A higher and steadier number generally produces smoother motion. The indicator averages recent frames so it is easier to read and does not react to every individual frame.

Frame rate can change while you:

- Play animated or time-based flows.
- Display complex graphics, video, or 3D content.
- Show many nodes, previews, or visible sections at once.
- Resize the window or move between devices and displays.

The achievable rate depends on the flow, display, device, and other work currently running.

The fps meter does not guarantee that all nodes content is rendering at the fps, as multiple threads may have different performance. A lot of nodes use background threading.  

## Node Time

When enabled in settings, a *cook bar inspired,* request duration indicator shows next to each node title on nodes that are slow.
