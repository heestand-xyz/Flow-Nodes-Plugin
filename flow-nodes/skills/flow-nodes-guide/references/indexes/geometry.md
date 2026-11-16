# 3D Geometry nodes

Each linked JSON file contains a parent group. Select the entry in `nodes` with the exact listed `typePath` for ports and properties. Prefer visible replacements for new flows.

- **Boolean / Combine** — Free. [JSON](../nodes/geometry/boolean.json) · `node:geometry:boolean:combine`. Add two or more geometries without affecting the meshes.
- **Boolean / Convex Hull** — Free. [JSON](../nodes/geometry/boolean.json) · `node:geometry:boolean:convexHull`. Derive a convex hull of two or more geometries.
- **Boolean / Difference** — Free. [JSON](../nodes/geometry/boolean.json) · `node:geometry:boolean:difference`. Derive the difference of two or more geometries.
- **Boolean / Intersection** — Free. [JSON](../nodes/geometry/boolean.json) · `node:geometry:boolean:intersection`. Intersect two or more geometries.
- **Boolean / Stencil** — Free. [JSON](../nodes/geometry/boolean.json) · `node:geometry:boolean:stencil`. Derive a stencil of two or more geometries.
- **Boolean / Symmetric Difference** — Free. [JSON](../nodes/geometry/boolean.json) · `node:geometry:boolean:symmetricDifference`. Derive the symmetric difference of two or more geometries. This is a mesh reprenting only the volume exclusively occupied by one shape or the other, but not both.
- **Boolean / Union** — Free. [JSON](../nodes/geometry/boolean.json) · `node:geometry:boolean:union`. Add two or more geometries by merging the meshes.
- **Info / Bounding Box** — Free. [JSON](../nodes/geometry/info.json) · `node:geometry:info:boundingBox`. Measure the bounding frame of a Geometry.
- **Info / Bounding Box** — Free; deprecated; replacement node:geometry:info:boundingBox. [JSON](../nodes/geometry/info.json) · `node:geometry:info:relay`. Measure the bounding frame of a Geometry.
- **Info / Components** — Free. [JSON](../nodes/geometry/info.json) · `node:geometry:info:components`. Polygons from a Geometry mesh.
- **Material / Simple** — Free; deprecated; replacement node:spatial:material:simple. [JSON](../nodes/geometry/material.json) · `node:geometry:material:simple`. Apply a simple material to a geometry.
- **Material / Unlit** — Free; deprecated; replacement node:spatial:material:unlit. [JSON](../nodes/geometry/material.json) · `node:geometry:material:unlit`. Apply an unlit material to a geometry. This material has no lighting effects. It simply shows the constant color or texture on the geometry.
- **Modifier / Extrude** — Free. [JSON](../nodes/geometry/modifier.json) · `node:geometry:modifier:extrude`. Extrude a vector path into a 3D geometry.
- **Modifier / Lathe** — Free. [JSON](../nodes/geometry/modifier.json) · `node:geometry:modifier:lathe`. Create a rotationally symmetrical 3D geometry by revolving a vector path around the Y axis.
- **Modifier / Poly Reduce** — Pro. [JSON](../nodes/geometry/modifier.json) · `node:geometry:modifier:polyReduce`. Reduce mesh triangle count with QEM edge collapses while preserving key features.
- **Modifier / Relay** — Free. [JSON](../nodes/geometry/modifier.json) · `node:geometry:modifier:relay`. Relay a Geometry. This node has no effect. Tho useful to define a type when wiring to generics.
- **Modifier / Transform** — Free. [JSON](../nodes/geometry/modifier.json) · `node:geometry:modifier:transform`. Moves, scales, and rotates a geometry.
- **Modifier / UV Project** — Pro. [JSON](../nodes/geometry/modifier.json) · `node:geometry:modifier:uvProject`. Project new texture coordinates onto a geometry, so a texture can be mapped onto any shape. The projection is calculated per polygon, from the shape of a sphere, a cylinder or a cube.
- **Resource / Clones** — Free; deprecated; replacement node:spatial:entity:cloneTransform. [JSON](../nodes/geometry/resource.json) · `node:geometry:resource:clones`. Clone a geometry with transforms.
- **Resource / Construct** — Free. [JSON](../nodes/geometry/resource.json) · `node:geometry:resource:construct`. Construct a Geometry mesh from polygons.
- **Resource / State** — Free. [JSON](../nodes/geometry/resource.json) · `node:geometry:resource:state`. Store a geometry.
- **Shape / Cone** — Free. [JSON](../nodes/geometry/shape.json) · `node:geometry:shape:cone`.
- **Shape / Cube** — Free; deprecated; replacement node:geometry:shape:cube2. [JSON](../nodes/geometry/shape.json) · `node:geometry:shape:cube`.
- **Shape / Cube** — Free. [JSON](../nodes/geometry/shape.json) · `node:geometry:shape:cube2`. A cube with calculated normals, chamfer or truly round spherical corners. Cube map (cross, 4x3 atlas) UVs are used when corner radius is zero.
- **Shape / Cylinder** — Free. [JSON](../nodes/geometry/shape.json) · `node:geometry:shape:cylinder`.
- **Shape / Icosahedron** — Free. [JSON](../nodes/geometry/shape.json) · `node:geometry:shape:icosahedron`. An icosahedron is one of the Platonic solids, meaning all faces are the same size, and it has perfect symmetry.
- **Shape / Plane** — Free. [JSON](../nodes/geometry/shape.json) · `node:geometry:shape:plane`. A positioned plane with a configurable size and perpendicular axis.
- **Shape / Sphere** — Free. [JSON](../nodes/geometry/shape.json) · `node:geometry:shape:sphere`. A sphere.
- **Shape / Torus** — Free. [JSON](../nodes/geometry/shape.json) · `node:geometry:shape:torus`. A torus.
