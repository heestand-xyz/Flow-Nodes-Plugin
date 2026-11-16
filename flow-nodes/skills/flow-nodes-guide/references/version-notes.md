# Version and source notes

The generated [snapshot metadata](snapshot.json) records the documentation date, app version, counts, and checksums of bundled references. The documented app version is **27.5.0**. This is a repository/documentation snapshot, not an assertion that this exact version is available in every App Store region.

All 34 manifest-listed Space articles are included in full text. Image/video links describe source media; binaries and example `.flow` archives are not bundled. Article text can refer to screenshots that the assistant has not viewed. Do not infer details from a caption alone. Use the exact node records for wiring.

The node snapshot contains **665 records: 628 visible nodes and 37 deprecated predecessors** at initial packaging. The generated index is authoritative if the counts change. It includes static ports, documented properties and defaults, platform declarations, Pro status, introduction versions, and replacement relationships. It does not enumerate runtime dynamic ports or prove all conversion pairs are supported. Internal `bindingItem` property records are removed, matching the website's public-property projection.

The exported node schema is version 2. The newer articles discuss Variable Arrays in 27.5.0; the schema-2 snapshot does not itself describe a representative Variable Array consumer. Use the articles for that API and do not fabricate new node properties in JSON.

Starting with plugin 0.2.0, the same 665 records are stored in 95 parent files at `nodes/<family>/<parent>.json`. The node catalog and snapshot use schema version 2; each parent file uses wrapper schema version 1 with `familyName`, `parentName`, and a `nodes` array sorted by `typePath`. The catalog's `reference` points to that parent file. Select the exact `typePath` inside it, including when resolving a deprecated node's replacement. This changes reference storage, not the node records or app behavior.

## Differences that matter

- The FAQ and older Video Guide sometimes name `node:video:resource:sample`. It is replaced by `sample2`. The new Sample has **Seek Mode**, **Seek Time**, **Seek Frame Index**, and **Seek Fraction**. The fractional recipe is simpler for new flows. Player's explicit Seek action is not part of Sample.
- Older 3D Clones examples use `geometry:resource:clones`; current workflows use `spatial:entity:cloneTransform` and may have different input types. Inspect the replacement record.
- Older Graphic Color, Gradient and Noise, Cube, Edit, gesture, and other variants have replacements. Resolve the entire chain and use the final node's actual ports.
- Operation's prose calls it a math operation on two values. Its exact signature has a generic **Leading** inlet and a Float **Trailing** inlet. The property displayed as **Value** supplies Trailing. Prefer these definitions over a shorthand interpretation of the prose.
- AI availability depends on device, OS, enabled features, and downloaded models. The app articles mention on-device Apple Intelligence and additional OS-dependent models. Ask the actual version and verify current official information before promising model availability.
- App Pro entitlements and legacy bundle names are distinct from this plugin. The plugin has no purchases. Use `isPro` for the bundled node classification; do not quote historical bundle pricing as current.

## Public links

Use [Flow Nodes](https://flownodes.app) for the app website. Treat source routes as documentation identities until a live check confirms the specific page is available. When browsing is unavailable, cite the bundled article title or node identity instead.

## Capability boundary

The packaged skill can read its references and guide users. It cannot inspect the active canvas, determine a user's Pro entitlement, render a Graphic, mutate a graph, or execute Flow's compatibility engine. A user can separately enable the app's macOS MCP or use its built-in AI Chat. Do not imply that installing this plugin enables either one automatically.
