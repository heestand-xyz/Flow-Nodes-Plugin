# Tabs and Split Views

Source route: `/docs/ui/tabs-and-split-views`. Media is not bundled; public route availability must be verified.

Tabs and Split Views let you work with several views of a flow in the same window. Use tabs to switch between views, or splits to see multiple views at the same time.

Each view keeps its own Canvas position, zoom, folder path, and selection. Changes to the flow still appear everywhere the same flow is shown.

## Create and use tabs

Open **Section Options** and select **New Tab**. When more than one tab is open, the tab bar appears above the current view.

- Select a tab to activate it.
- Select the plus button in the tab bar to create another tab.
- Select the close button on a tab to remove that view.
- Scroll the tab bar horizontally when there are too many tabs to fit.

A tab title can show its folder path and selected node. If several nodes are selected, it shows the number of selected nodes instead.

Closing a tab only closes that view. It does not delete the flow or its nodes.

## Create a Split View

Open **Section Options** and select **Split**. On a regular-width screen, choose **Horizontally** or **Vertically**. On a compact screen, Flow Nodes chooses the direction that best fits the available space.

The new section is focused after the split is created. A subtle highlight identifies the focused section when several sections are visible.

Splitting can be repeated until the layout reaches the supported nesting limit. When no additional split can fit in a direction, that option is no longer offered.

## Resize and arrange a split

Drag the divider or its handle to give one side more room. Each side keeps at least one quarter of the available space.

Controls on the divider let you:

- **Center Split View** to return both sides to equal size.
- **Swap Split View Axis** to change between a side-by-side and stacked layout.
- **Swap Split View Content** to exchange the two sides.

Some compact layouts use a dynamic split direction. In that case, the layout follows the screen and the axis controls are not shown.

## Close a section

Open **Section Options** and select **Close** to remove the focused section. Close is available only when another section will remain.

Closing a section removes the view, not the flow content shown inside it. If you only want to work elsewhere temporarily, create or activate a tab instead.

## Accessibility

Section Options, tabs, close buttons, split dividers, drag handles, and arrangement controls have accessibility labels. The focused section is also indicated without relying only on the position of its controls.
