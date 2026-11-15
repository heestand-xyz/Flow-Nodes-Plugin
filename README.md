# Flow Nodes

Plugin with skills for agents to help with creating a flow of nodes and wires in Flow Nodes app for iPhone, iPad, Mac and Vision Pro.

## Install

Catalogs point to `./flow-nodes`, which holds one shared skill and reference bundle.

For **Codex**, run these commands from this folder with a CLI that supports `codex plugin`:

```sh
codex plugin marketplace add .
codex plugin add flow-nodes@flow-nodes
```

Start a new session and select Flow Nodes. Supported desktop clients can also install it from the registered marketplace.

For **Claude Code**, load the plugin for a local trial:

```sh
claude --plugin-dir ./flow-nodes
```

Then invoke `/flow-nodes:flow-nodes-guide`, or ask a Flow Nodes question. To install through the repository marketplace instead:

```sh
claude plugin marketplace add .
claude plugin install flow-nodes@flow-nodes
```

For ZIP downloads and chat uploads, see the [installation guide](Installation.md).
