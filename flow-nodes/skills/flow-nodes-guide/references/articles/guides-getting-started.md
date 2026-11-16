# Getting Started Guide

Source route: `/docs/guides/getting-started`. Media is not bundled; public route availability must be verified.

Flow Nodes is a made up of a set of tools, called nodes.

These nodes are created in a project, called a flow.

![Getting Started — step 1](https://flownodes.app/docs/media/guides-getting-started/media-01.png)

## Direction

The general direction of data flow is downstream, left to right. Tho in “double wires” data can also flow upstream, right to left. The main purpose of data flowing both ways is to allow binding of state, to save and update values.

![Getting Started — step 2](https://flownodes.app/docs/media/guides-getting-started/media-02.png)

## State

Value or data is stored in State nodes. When editing properties in some nodes, the input double wires update upstream. In this case a State node is needed to store the value. Use the [Save](../nodes/general/generic.json) (`node:general:generic:save`) node to update a value on demand.

![Getting Started — step 3](https://flownodes.app/docs/media/guides-getting-started/media-03.png)

## List State

Values can also be stored in List State nodes. To dynamically edit a list there are nodes like [List Save](../nodes/general/generic.json) (`node:general:generic:listSave`), [Insert](../nodes/general/list.json) (`node:general:list:insert`), [Append](../nodes/general/list.json) (`node:general:list:append`), [Remove](../nodes/general/list.json) (`node:general:list:remove`) and [Remove All](../nodes/general/list.json) (`node:general:list:removeAll`).

![Getting Started — step 4](https://flownodes.app/docs/media/guides-getting-started/media-04.png)

## Convert

When connecting from an outlet of a specific type, to an inlet of another type, sometimes a hidden auto-convert node is created, represented with a multi colored wire. There is also a manual [Convert](../nodes/general/generic.json) (`node:general:generic:manualConvert`) node, to “hard code” the conversion type.

![Getting Started — step 5](https://flownodes.app/docs/media/guides-getting-started/media-05.png)

## Auto Save

Flows auto save when you create nodes, edit properties and move nodes. There should generally not be any need to save manually.

![Getting Started — step 6](https://flownodes.app/docs/media/guides-getting-started/media-06.png)

## Sync

All flows (projects) are synced via iCloud (if enabled). Sync indicator will show if a recent flow was created or modified on another device.

![Getting Started — step 7](https://flownodes.app/docs/media/guides-getting-started/media-07.png)

## Properties

Most nodes have properties, these can be edited manually, in batch by selecting multiple nodes (long press on iOS), or via scripts.

![Getting Started — step 8](https://flownodes.app/docs/media/guides-getting-started/media-08.png)

## Intelligence

AI can be used on compatible devices in Chat and Nodes Suggestions. There are also AI nodes. Powered by Apple’s Foundation Models. The on-device model runs offline. Apple’s Private Cloud Compute model is also available on OS 27 or newer on supported devices.

![Getting Started — step 9](https://flownodes.app/docs/media/guides-getting-started/media-09.png)

## Scripts

In most properties there is a script button, when enabled JavaScript can be written to derive the value.

![Getting Started — step 10](https://flownodes.app/docs/media/guides-getting-started/media-10.png)

## Shaders

In the Code node bundle there is a Shader node. It allows to write shaders in Metal.
