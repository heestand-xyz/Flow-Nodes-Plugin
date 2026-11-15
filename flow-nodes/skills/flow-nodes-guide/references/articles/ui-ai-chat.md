# AI Chat

Source route: `/docs/ui/ai-chat`. Media is not bundled; public route availability must be verified.

AI Chat lets you ask questions about the active flow and request changes in conversational language. It uses an on-device Apple Intelligence model.

## Availability

AI Chat requires an eligible device, Apple Intelligence, and a downloaded model that is ready to use.

If AI Chat is unavailable, the panel explains why. You may see:

- **Device not eligible.**
- **Apple Intelligence not enabled.**
- **Model not ready yet.**

Follow the displayed guidance or check the device's Apple Intelligence settings before trying again.

## Start a conversation

When AI Chat opens, it may first summarize your flow. Wait for **Summarizing flow...** to disappear (optional in settings), then enter a request in the prompt area.

You can ask AI Chat to explain the flow, find nodes, inspect connections and values, or make supported edits. For example, it can help you:

- Find an appropriate node.
- Create, remove, move, layout, or rename nodes.
- Connect or disconnect nodes.
- Inspect inlets, outlets, and connections.
- Read an outlet value.
- Inspect or update supported properties.
- Explain a node using its documentation.

Submit the prompt to begin. A progress indicator appears while AI Chat is responding. Select cancel if you want to stop the current response.

## Review the conversation

Messages appear in chronological order, and the conversation scrolls to the newest message automatically. Review any described changes on the Canvas and in Properties.

AI Chat uses specific editing actions rather than directly replacing the entire flow. A requested action may still be unavailable when it is not supported by the selected node, property, model, or current flow state.

## Start over or change models

Select the plus button to begin a new conversation.

If the model selector is visible, choose one of the available models at the top of the panel. **Pending model switch** means the new model will be used in the next chat.

*An MCP is also available on macOS.*
