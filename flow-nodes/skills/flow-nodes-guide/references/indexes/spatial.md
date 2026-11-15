# 3D Spatial nodes

Read the linked JSON for exact ports and properties. Prefer visible replacements for new flows.

- **Camera / Calibration** — Pro. [JSON](../nodes/node-spatial-camera-calibration.json) · `node:spatial:camera:calibration`. Calibrate a perspective camera from matching 3D and 2D points and live-write updates to a connected camera binding while optimization is running.
- **Camera / Fisheye** — Pro. [JSON](../nodes/node-spatial-camera-fisheye.json) · `node:spatial:camera:fisheye`. A fisheye camera with spherical curvature.
- **Camera / Orthographic** — Pro. [JSON](../nodes/node-spatial-camera-orthographic.json) · `node:spatial:camera:orthographic`. A orthographic camera for an isometric view.
- **Camera / Perspective** — Free. [JSON](../nodes/node-spatial-camera-perspective.json) · `node:spatial:camera:perspective`. A standard camera with perspective.
- **Camera / Projector** — Pro. [JSON](../nodes/node-spatial-camera-projector.json) · `node:spatial:camera:projector`. Creates a projector from a camera and graphic, with adjustable intensity.
- **Camera / State** — Free. [JSON](../nodes/node-spatial-camera-state.json) · `node:spatial:camera:state`. Store a camera value and expose it as a binding output.
- **Entity / Clone Transform** — Pro. [JSON](../nodes/node-spatial-entity-cloneTransform.json) · `node:spatial:entity:cloneTransform`. Clone a spatial entity using multiple 3D transforms.
- **Entity / Group** — Free. [JSON](../nodes/node-spatial-entity-group.json) · `node:spatial:entity:group`. Group together spatial entities.
- **Entity / Texture** — Free. [JSON](../nodes/node-spatial-entity-texture.json) · `node:spatial:entity:texture`. Apply a material to a spatial entity, such as a geometry or mesh field.
- **Entity / Transform** — Free. [JSON](../nodes/node-spatial-entity-transform.json) · `node:spatial:entity:transform`. Transform a spatial entity in 3D space. This can be a geometry, camera or any 3D entity.
- **Field / Color Displace** — Free. [JSON](../nodes/node-spatial-field-colorDisplace.json) · `node:spatial:field:colorDisplace`. Displace a field with a sampled color from a 3D graphic.
- **Field / Connect Lines** — Free. [JSON](../nodes/node-spatial-field-connectLines.json) · `node:spatial:field:connectLines`. Connect matching particles from two fields into line mesh particles. Each source particle pair becomes one line with two points.
- **Field / Constant** — Free. [JSON](../nodes/node-spatial-field-constant.json) · `node:spatial:field:constant`. Define a field with a repeating constant number.
- **Field / Convert from 3D Graphic** — Free. [JSON](../nodes/node-spatial-field-convertFromGraphic3D.json) · `node:spatial:field:convertFromGraphic3D`. Convert a 3D Graphic to a Field with colored particles.
- **Field / Convert to Particles** — Free. [JSON](../nodes/node-spatial-field-convertToParticles.json) · `node:spatial:field:convertToParticles`. Convert a geometry or mesh-backed field to particles.
- **Field / Fraction Grid** — Free. [JSON](../nodes/node-spatial-field-fractionGrid.json) · `node:spatial:field:fractionGrid`. A grid of positions in a field based on spacing and offset.
- **Field / Grid** — Free. [JSON](../nodes/node-spatial-field-grid.json) · `node:spatial:field:grid`. A grid of positions in a field.
- **Field / Lines** — Free. [JSON](../nodes/node-spatial-field-lines.json) · `node:spatial:field:lines`. Combine two tags from a field into a single position tag, creating lines between them. Outputs mesh particles with line index pairs.
- **Field / List Operation** — Free. [JSON](../nodes/node-spatial-field-listOperation.json) · `node:spatial:field:listOperation`. Apply a list operation between two field tags.
- **Field / Noise Displace** — Free. [JSON](../nodes/node-spatial-field-noiseDisplace.json) · `node:spatial:field:noiseDisplace`. Displace a field with noise.
- **Field / Normals** — Free. [JSON](../nodes/node-spatial-field-normals.json) · `node:spatial:field:normals`. Compute normals of a mesh field.
- **Field / Operation** — Free. [JSON](../nodes/node-spatial-field-operation.json) · `node:spatial:field:operation`. Apply a math operation on a tag in a field.
- **Field / Particles from Points** — Free. [JSON](../nodes/node-spatial-field-particlesFromPoints.json) · `node:spatial:field:particlesFromPoints`. Create a particle field from a list of 3D points.
- **Field / Proximity** — Free. [JSON](../nodes/node-spatial-field-proximity.json) · `node:spatial:field:proximity`. Find the nearest distance in each particle in the field. A proximity and distance tag will be added to a new field. This node can be used to create the plexus effect when combined with the Lines Field node.
- **Field / Reassign** — Free. [JSON](../nodes/node-spatial-field-reassign.json) · `node:spatial:field:reassign`. Copy a tag from a source field into a target field. Requires matching particle count.
- **Field / Source Noise** — Free. [JSON](../nodes/node-spatial-field-noise.json) · `node:spatial:field:noise`. Apply noise to a tag in a field.
- **Field / State** — Free. [JSON](../nodes/node-spatial-field-state.json) · `node:spatial:field:state`. Store a field.
- **Field / Transform** — Free. [JSON](../nodes/node-spatial-field-transform.json) · `node:spatial:field:transform`. Transform a field in 3D space.
- **Field / Wireframe** — Free. [JSON](../nodes/node-spatial-field-wireframe.json) · `node:spatial:field:wireframe`. Creates line mesh particles from a geometry by connecting each polygon vertex to the next vertex and closing the final edge.
- **Light / Ambient** — Free. [JSON](../nodes/node-spatial-light-ambient.json) · `node:spatial:light:ambient`. An ambient light that evenly affects all surfaces.
- **Light / Directional** — Free. [JSON](../nodes/node-spatial-light-directional.json) · `node:spatial:light:directional`. A directional light with a direction vector, color, intensity, and diffuse wrap.
- **Light / Point** — Free. [JSON](../nodes/node-spatial-light-point.json) · `node:spatial:light:point`. A point light positioned in 3D space with radius, falloff, color, and intensity.
- **Material / Simple** — Free. [JSON](../nodes/node-spatial-material-simple.json) · `node:spatial:material:simple`. Creates a simple material based on a tint color and an optional graphic.
- **Material / Unlit** — Free. [JSON](../nodes/node-spatial-material-unlit.json) · `node:spatial:material:unlit`. Creates an unlit material based on a tint color and an optional graphic. An unlit material does not use lighting, it has its own constant light.
