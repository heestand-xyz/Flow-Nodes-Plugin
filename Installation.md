# Installation options

Use the [installation instructions](README.md) for Codex and Claude Code. To install from GitHub, use `heestand-xyz/Flow-Nodes-Plugin` in place of `.` in the marketplace-add command.

When a [release](https://github.com/heestand-xyz/Flow-Nodes-Plugin/releases) provides ZIP downloads, choose the package for your host:

| ZIP | Use |
| --- | --- |
| `flow-nodes-<version>.zip` | Portable plugin package for ChatGPT/Codex. For GitHub installation, follow the README. |
| `flow-nodes-<version>-claude-code.zip` | Claude Code plugin. Extract it, then run `claude --plugin-dir ./flow-nodes` from the extracted parent folder. |
| `flow-nodes-guide-<version>.zip` | Skill upload for Claude chat. |

For **Claude chat**, download the skill ZIP and upload it through **Customize → Skills**, with code execution enabled. See the [custom skill upload instructions](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

All packages contain the same Flow Nodes guidance. Try: “Show me exactly how to wire a slider to control an image's blur.”

See the [changelog](Changelog.md) for updates.
