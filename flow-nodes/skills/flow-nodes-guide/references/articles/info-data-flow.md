# Data Flow

Source route: `/docs/info/data-flow`. Media is not bundled; public route availability must be verified.

Data can flow both downstream (left to right) and upstream (right to left) in wires.

By default all wires flow downstream, tho in connections indicated by a double wire, a binding is created, data can flow in both directions.

This binding let’s you easily edit data, stored in a state node.

State nodes are always on the far left side. This is place for the *source of truth* of the data. All nodes to the right of state nodes are just edits of that data.
