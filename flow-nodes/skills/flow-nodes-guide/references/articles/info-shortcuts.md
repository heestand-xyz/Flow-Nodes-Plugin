# Shortcuts

Source route: `/docs/info/shortcuts`. Media is not bundled; public route availability must be verified.

![Shortcuts — step 1](https://flownodes.app/docs/media/info-shortcuts/media-01.png)

[Shortcuts](https://apps.apple.com/us/app/shortcuts/id1462947752) by Apple

### Open a Flow

To open a flow from a shortcut add the “Open Flow” shortcut and select your flow:

![Shortcuts — step 2](https://flownodes.app/docs/media/info-shortcuts/media-02.png)

Optionally open the flow in fullscreen. *(The first top level connected outlet will be presented)*

### Run a Flow

There are multiple Flow Nodes shortcuts, these use the top level inlets and outlets of a flow to run a shortcut. They are hardcoded to take a specific input and output type. Tho there is a JSON shortcut for providing multiple inputs or outputs of different core types.

How to use the **JSON** shortcut?

- The input values gets extracted from the JSON and their keys need to match the names of the nodes the inlet wires are connected to at the top level of the flow.
- The output can be JSON or a Graphic.
- To allow the shortcut to differentiate between wires, it’s recommended to use renamed Relay nodes for the top level inputs and outputs.

> **Note**
>
> A flow-listing issue in some shortcuts was fixed in [Flow Nodes 4.0.0](https://flownodes.app/docs/versions/4.0.0). Update the app if you are using an older version.

### Run from Terminal

Shortcuts can also be run from the terminal like this:

```bash
shortcuts run "My Flow Shortcut"
```
