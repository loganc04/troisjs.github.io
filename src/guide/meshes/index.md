# Meshes

You can easily create mesh :

```html
<Box :size="1" :position="{ x: 10, y: 0, z: 0 }">
  <BasicMaterial />
</Box>
```

You can use the following meshes :

- `Box` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Box.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/BoxBufferGeometry))
- `Circle` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Circle.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/CircleBufferGeometry))
- `Cone` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Cone.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/ConeBufferGeometry))
- `Cylinder` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Cylinder.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/CylinderBufferGeometry))
- `Dodecahedron` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Dodecahedron.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/DodecahedronBufferGeometry))
- `Icosahedron` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Icosahedron.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/IcosahedronBufferGeometry))
- `Lathe` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Lathe.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/LatheBufferGeometry))
- `Octahedron` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Octahedron.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/OctahedronBufferGeometry))
- `Plane` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Plane.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/PlaneBufferGeometry))
- `Polyhedron` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Polyhedron.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/PolyhedronBufferGeometry))
- `Ring` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Ring.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/RingBufferGeometry))
- `Sphere` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Sphere.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/SphereBufferGeometry))
- `Tetrahedron` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Tetrahedron.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/TetrahedronBufferGeometry))
- `Torus` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Torus.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/TorusBufferGeometry))
- `TorusKnot` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/TorusKnot.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/TorusKnotBufferGeometry))
- `Tube` ([source](https://github.com/troisjs/trois/blob/master/src/meshes/Tube.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/TubeBufferGeometry))

# Common Props (see [Mesh.ts](https://github.com/troisjs/trois/blob/master/src/meshes/Mesh.ts))

<table>
<tbody>
  <tr>
    <th>Name</th>
    <th>Description</th>
    <th>Type</th>
    <th>Default</th>
  </tr>
  <!-- <tr><td><code>materialId</code></td><td>Material ID</td><td>String</td><td></td></tr> -->
  <tr><td><code>position</code></td><td>Position</td><td>Object</td><td>{ x: 0, y: 0, z: 0 }</td></tr>
  <tr><td><code>rotation</code></td><td>Rotation</td><td>Object</td><td>{ x: 0, y: 0, z: 0 }</td></tr>
  <tr><td><code>scale</code></td><td>Scale</td><td>Object</td><td>{ x: 1, y: 1, z: 1 }</td></tr>
  <tr><td><code>castShadow</code></td><td>Cast shadow ?</td><td>Boolean</td><td>false</td></tr>
  <tr><td><code>receiveShadow</code></td><td>Receive shadow ?</td><td>Boolean</td><td>false</td></tr>
</tbody>
</table>

To enable shadows, please read [Shadows](../shadows).

### Example :

```html
<Box
  :position="{ x: 0, y: 0, z: 0 }"
  :rotation="{ x: 0, y: 0, z: 0 }"
  :scale="{ x: 1, y: 1, z: 1 }"
  :cast-shadow="false"
  :receive-shadow="false"
>
  <BasicMaterial />
</Box>
```

### Access three.js mesh

You should set a *ref* on your mesh :

```html
<Box ref="box" />
```

You can then access three.js mesh in your component script :

```js
const mesh = this.$ref.box.mesh;
```