# Wire Connections

Source route: `/docs/info/wire-connections`. Media is not bundled; public route availability must be verified.

There are different types of wires in Flow Nodes, in **thin wires** only **one value** can flow downstream (towards the right), tho in **double wires** data can flow **both down and up stream**. 

There are also **thicker wires**, they can send more than one value at a time in an **array**. Finally there is the **lexicon wire**, it can send a **dictionary** of keyed values.

> **Tip**
>
> Copying or duplicating connected nodes will re-create connection for the new nodes.

> **Tip**
>
> To select multiple nodes on iOS, use the node context menu option “Select”.

Wires are connected to a node via it’s in and outlets.

Selecting a node, will show all of it’s in and outlets, and dragging a wire will show compatible in and outlets on other nodes.
