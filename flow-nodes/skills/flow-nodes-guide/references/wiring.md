# Wiring rules

These rules combine the Space articles **Data Flow**, **Wire Connections**, **Type System**, and **Variable Properties** with the app's connection UI and Flow's connection implementation. They describe the bundled source snapshot, not a promise about every older app release.

## Read a port record

| Field | Meaning |
| --- | --- |
| `name` | The user-facing inlet or outlet name; use this in instructions. |
| `typeName` | Stable port identifier for tools and precise disambiguation. Do not use it as a display label. |
| `way` | `in` receives from an outlet; `out` supplies an inlet. |
| `valueType` | Raw/core type or `generic`. `raw:core:float` is Float, `raw:graphic` is Graphic, `raw:view` is View. |
| `capacity` | `mono`: one value; `multi`: ordered list; `lex`: keyed list/dictionary, also inspect `keyType`. |
| `direction` | `direct`: downstream reads; `binding`: participates in upstream writes when the complete route supports them. |
| `level` | `external`: outside a container; `internal`: inside its mapped graph. |

The snapshot describes static definitions. Folder boundaries, Script outputs, Shader inputs, selected generic types, runtime availability, and active properties can change with the graph. An empty static port list is not proof that the node cannot have dynamic ports. An inlet with a property may have a valid default and need no wire; do not require wiring every inlet.

## Values and stored state

Ordinary wires carry values downstream. A double wire indicates binding, which permits write-back along a supported route. The destination of a write must ultimately store the value, commonly in State. A double wire is one connection with read/write behavior, not a reverse pair of wires.

For a Slider, connect a Float State's **Value** outlet to its **Value** inlet. Then branch the State's same outlet to the numeric control target. Slider's **View** outlet is its interface. Other controls may have different ports: inspect them individually.

Save has **Destination** (binding), **Source** (direct), and **Save** (Action) inlets and no output. The State outlet connects to Destination even though the update travels upstream when Save fires. Do not swap Source and Destination.

## Capacity and conversions

In the inspected implementation, ordinary direct connection shapes include Mono→Mono, Mono→Multi, Multi→Multi, and Lex→Lex, subject to type and direction checks. This does not make every pair in those shapes compatible. A normal Multi→Mono connection is not included: select a value, reduce the list, or use an explicitly supported conversion according to the desired meaning. A keyed-list attachment can separately supply keys or values; a dictionary is not interchangeable with an unkeyed list.

Different value types may need a direct conversion or a specialized/manual conversion node. A read conversion does not imply a writable reverse conversion. The app shows both direct and indirectly connectable targets; a highlighted target can cause an intermediate conversion to be inserted. A multicolored wire can indicate conversion. Never infer support for an arbitrary conversion merely because the types seem mathematically related.

Generic streams resolve from the graph. A generic node connected elsewhere may already be constrained. Conflicting constraints or an unsupported raw type can prevent a connection even when the two visible labels appear generic. For ordinary workflows, prefer explicitly typed State/Relay nodes to make the intended type clear.

## Containers

An Edit map's external **Array In** accepts the list. Inside, **Element Out** supplies the current element, **Index** supplies its index, and **Element In** receives the edited result. The external **Array Out** supplies the resulting list. Do not connect the external array port where an internal per-element port is required.

A Reduce map receives external **Array** and **Initial**. Inside, combine **Previous Result** and **Element**, and send the result to **Next Result**. External **Reduced** gives the final accumulated value. The initial value is the previous result on the first iteration.

Video Edit has internal **Frame** output and internal **Frame** input, as well as external progress outputs. It writes the resulting video through its external **Destination** binding; it does not have a Video result outlet. Use a separate Video State for the destination.

Folders contain another graph. Dragging a wire near a folder side can create a corresponding boundary inlet/outlet. Map nodes group nodes into an evaluation scope; Folder and Group are not substitutes for list iteration. Instance nodes reference another saved flow. Source edits affect every use, while promoted-property overrides can be local to an instance.

## When nothing happens

Confirm the exact current node variant and port, then type/capacity, scope, writable State, loaded data, permissions, playback, node-local Playing/Running/Live controls, and action triggers. Time and Live are different controls. Global pause can stop time-driven work. A View must be shown to interact with its controls. A 3D Render needs at least one camera among its Entities input.

Ordinary cycles can be rejected. Use the documented Feedback/Loop/map workflow for the intended operation instead of trying to force an arbitrary cycle. Direct compatibility checks are only part of graph validation.
