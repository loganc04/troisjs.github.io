# Using Geometries

Instead of using predefined meshes, you can create meshes with geometry like this:

```html
<Mesh>
  <BoxGeometry />
  <BasicMaterial />
</Mesh>
```

TroisJS includes all buffer geometries from three.js:

- `BoxGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/BoxGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/BoxBufferGeometry))
- `CircleGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/CircleGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/CircleBufferGeometry))
- `ConeGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/ConeGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/ConeBufferGeometry))
- `CylinderGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/CylinderGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/CylinderBufferGeometry))
- `DodecahedronGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/DodecahedronGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/DodecahedronBufferGeometry))
- `IcosahedronGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/IcosahedronGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/IcosahedronBufferGeometry))
- `LatheGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/LatheGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/LatheBufferGeometry))
- `OctahedronGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/OctahedronGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/OctahedronBufferGeometry))
- `PlaneGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/PlaneGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/PlaneBufferGeometry))
- `PolyhedronGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/PolyhedronGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/PolyhedronBufferGeometry))
- `RingGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/RingGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/RingBufferGeometry))
- `SphereGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/SphereGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/SphereBufferGeometry))
- `TetrahedronGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/TetrahedronGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/TetrahedronBufferGeometry))
- `TorusGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/TorusGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/TorusBufferGeometry))
- `TorusKnotGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/TorusKnotGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/TorusKnotBufferGeometry))
- `TubeGeometry` ([source](https://github.com/troisjs/trois/blob/master/src/geometries/TubeGeometry.ts), [three.js doc](https://threejs.org/docs/#api/en/geometries/TubeBufferGeometry))
