# 3D Geometry nodes

Read the linked JSON for exact ports and properties. Prefer visible replacements for new flows.

- **Boolean / Combine** — Free. [JSON](../nodes/node-geometry-boolean-combine.json) · `node:geometry:boolean:combine`. Add two or more geometries without affecting the meshes.
- **Boolean / Convex Hull** — Free. [JSON](../nodes/node-geometry-boolean-convexHull.json) · `node:geometry:boolean:convexHull`. Derive a convex hull of two or more geometries.
- **Boolean / Difference** — Free. [JSON](../nodes/node-geometry-boolean-difference.json) · `node:geometry:boolean:difference`. Derive the difference of two or more geometries.
- **Boolean / Intersection** — Free. [JSON](../nodes/node-geometry-boolean-intersection.json) · `node:geometry:boolean:intersection`. Intersect two or more geometries.
- **Boolean / Stencil** — Free. [JSON](../nodes/node-geometry-boolean-stencil.json) · `node:geometry:boolean:stencil`. Derive a stencil of two or more geometries.
- **Boolean / Symmetric Difference** — Free. [JSON](../nodes/node-geometry-boolean-symmetricDifference.json) · `node:geometry:boolean:symmetricDifference`. Derive the symmetric difference of two or more geometries. This is a mesh reprenting only the volume exclusively occupied by one shape or the other, but not both.
- **Boolean / Union** — Free. [JSON](../nodes/node-geometry-boolean-union.json) · `node:geometry:boolean:union`. Add two or more geometries by merging the meshes.
- **Info / Bounding Box** — Free. [JSON](../nodes/node-geometry-info-boundingBox.json) · `node:geometry:info:boundingBox`. Measure the bounding frame of a Geometry.
- **Info / Bounding Box** — Free; deprecated; replacement node:geometry:info:boundingBox. [JSON](../nodes/node-geometry-info-relay.json) · `node:geometry:info:relay`. Measure the bounding frame of a Geometry.
- **Info / Components** — Free. [JSON](../nodes/node-geometry-info-components.json) · `node:geometry:info:components`. Polygons from a Geometry mesh.
- **Material / Simple** — Free; deprecated; replacement node:spatial:material:simple. [JSON](../nodes/node-geometry-material-simple.json) · `node:geometry:material:simple`. Apply a simple material to a geometry.
- **Material / Unlit** — Free; deprecated; replacement node:spatial:material:unlit. [JSON](../nodes/node-geometry-material-unlit.json) · `node:geometry:material:unlit`. Apply an unlit material to a geometry. This material has no lighting effects. It simply shows the constant color or texture on the geometry.
- **Modifier / Extrude** — Free. [JSON](../nodes/node-geometry-modifier-extrude.json) · `node:geometry:modifier:extrude`. Extrude a vector path into a 3D geometry.
- **Modifier / Lathe** — Free. [JSON](../nodes/node-geometry-modifier-lathe.json) · `node:geometry:modifier:lathe`. Create a rotationally symmetrical 3D geometry by revolving a vector path around the Y axis.
- **Modifier / Poly Reduce** — Pro. [JSON](../nodes/node-geometry-modifier-polyReduce.json) · `node:geometry:modifier:polyReduce`. Reduce mesh triangle count with QEM edge collapses while preserving key features.
- **Modifier / Relay** — Free. [JSON](../nodes/node-geometry-modifier-relay.json) · `node:geometry:modifier:relay`. Relay a Geometry. This node has no effect. Tho useful to define a type when wiring to generics.
- **Modifier / Transform** — Free. [JSON](../nodes/node-geometry-modifier-transform.json) · `node:geometry:modifier:transform`. Moves, scales, and rotates a geometry.
- **Modifier / UV Project** — Pro. [JSON](../nodes/node-geometry-modifier-uvProject.json) · `node:geometry:modifier:uvProject`. Project new texture coordinates onto a geometry, so a texture can be mapped onto any shape. The projection is calculated per polygon, from the shape of a sphere, a cylinder or a cube.
- **Resource / Clones** — Free; deprecated; replacement node:spatial:entity:cloneTransform. [JSON](../nodes/node-geometry-resource-clones.json) · `node:geometry:resource:clones`. Clone a geometry with transforms.
- **Resource / Construct** — Free. [JSON](../nodes/node-geometry-resource-construct.json) · `node:geometry:resource:construct`. Construct a Geometry mesh from polygons.
- **Resource / State** — Free. [JSON](../nodes/node-geometry-resource-state.json) · `node:geometry:resource:state`. Store a geometry.
- **Shape / Cone** — Free. [JSON](../nodes/node-geometry-shape-cone.json) · `node:geometry:shape:cone`. 
- **Shape / Cube** — Free; deprecated; replacement node:geometry:shape:cube2. [JSON](../nodes/node-geometry-shape-cube.json) · `node:geometry:shape:cube`. 
- **Shape / Cube** — Free. [JSON](../nodes/node-geometry-shape-cube2.json) · `node:geometry:shape:cube2`. A cube with calculated normals, chamfer or truly round spherical corners. Cube map (cross, 4x3 atlas) UVs are used when corner radius is zero.
- **Shape / Cylinder** — Free. [JSON](../nodes/node-geometry-shape-cylinder.json) · `node:geometry:shape:cylinder`. 
- **Shape / Icosahedron** — Free. [JSON](../nodes/node-geometry-shape-icosahedron.json) · `node:geometry:shape:icosahedron`. An icosahedron is one of the Platonic solids, meaning all faces are the same size, and it has perfect symmetry.
- **Shape / Plane** — Free. [JSON](../nodes/node-geometry-shape-plane.json) · `node:geometry:shape:plane`. A positioned plane with a configurable size and perpendicular axis.
- **Shape / Sphere** — Free. [JSON](../nodes/node-geometry-shape-sphere.json) · `node:geometry:shape:sphere`. A sphere.
- **Shape / Torus** — Free. [JSON](../nodes/node-geometry-shape-torus.json) · `node:geometry:shape:torus`. A torus.
