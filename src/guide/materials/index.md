# Materials

You can easily create the following materials:

- `BasicMaterial` ([source](https://github.com/troisjs/trois/blob/master/src/materials/Material.ts), [three.js doc](https://threejs.org/docs/index.html#api/en/materials/MeshBasicMaterial))
- `LambertMaterial` ([source](https://github.com/troisjs/trois/blob/master/src/materials/Material.ts), [three.js doc](https://threejs.org/docs/index.html#api/en/materials/MeshLambertMaterial))
- `MatcapMaterial` ([source](https://github.com/troisjs/trois/blob/master/src/materials/MatcapMaterial.ts), [three.js doc](https://threejs.org/docs/index.html#api/en/materials/MeshMatcapMaterial))
- `PhongMaterial` ([source](https://github.com/troisjs/trois/blob/master/src/materials/Material.ts), [three.js doc](https://threejs.org/docs/index.html#api/en/materials/MeshPhongMaterial))
- `PhysicalMaterial` ([source](https://github.com/troisjs/trois/blob/master/src/materials/Material.ts), [three.js doc](https://threejs.org/docs/index.html#api/en/materials/MeshPhysicalMaterial))
- `ShaderMaterial` ([source](https://github.com/troisjs/trois/blob/master/src/materials/ShaderMaterial.ts), [three.js doc](https://threejs.org/docs/index.html#api/en/materials/ShaderMaterial))
- `StandardMaterial` ([source](https://github.com/troisjs/trois/blob/master/src/materials/Material.ts), [three.js doc](https://threejs.org/docs/index.html#api/en/materials/MeshStandardMaterial))
- `SubSurfaceMaterial` ([source](https://github.com/troisjs/trois/blob/master/src/materials/SubSurfaceMaterial.ts), [three.js example](https://github.com/mrdoob/three.js/blob/master/examples/webgl_materials_subsurface_scattering.html))
- `ToonMaterial` ([source](https://github.com/troisjs/trois/blob/master/src/materials/Material.ts), [three.js doc](https://threejs.org/docs/index.html#api/en/materials/MeshToonMaterial))

Example:

```html
<Box>
  <PhongMaterial color="#ffffff" />
</Box>
```

### Props (v0.3)

<table>
<tbody>
  <tr>
    <th>Name</th>
    <th>Description</th>
    <th>Type</th>
    <th>Default</th>
  </tr>
  <tr><td><code>color</code></td><td>Color</td><td>String, Number</td><td>#ffffff</td></tr>
  <tr><td><code>props</code></td><td>Properties to apply to material, these properties will be <em>watched</em></td><td>Object</td><td>{}</td></tr>
</tbody>
</table>

You can use `props` to easily customize three.js material, e.g.:

```html
<Box>
  <PhongMaterial color="#ffffff" :props="{ transparent: true, opacity: 0.5 }" />
</Box>
```

Here is an incomplete list of threejs material properties (to get the complete list please read https://threejs.org/docs/#api/en/materials/Material):

<table>
<tbody>
  <tr>
    <th>Name</th>
    <th>Description</th>
    <th>Type</th>
    <th>Default</th>
  </tr>
  <tr><td><code>color</code></td><td>Color</td><td>String, Number</td><td>#ffffff</td></tr>
  <tr><td><code>depthTest</code></td><td>Whether to have depth test enabled when rendering this material.</td><td>Boolean</td><td>true</td></tr>
  <tr><td><code>depthWrite</code></td><td>Whether rendering this material has any effect on the depth buffer.</td><td>Boolean</td><td>true</td></tr>
  <tr><td><code>flatShading</code></td><td>Define whether the material is rendered with flat shading.</td><td>Boolean</td><td>false</td></tr>
  <tr><td><code>fog</code></td><td>Whether the material is affected by fog.</td><td>Boolean</td><td>true</td></tr>
  <tr><td><code>opacity</code></td><td>Float in the range of 0.0 - 1.0 indicating how transparent the material is.</td><td>Number</td><td>1</td></tr>
  <tr><td><code>side</code></td><td>Defines which side of faces will be rendered - front, back or both.</td><td>Number</td><td>THREE.FrontSide</td></tr>
  <tr><td><code>transparent</code></td><td>Defines whether this material is transparent.</td><td>Boolean</td><td>false</td></tr>
  <tr><td><code>vertexColors</code></td><td>Defines whether vertex coloring is used.</td><td>Boolean</td><td>false</td></tr>
</tbody>
</table>

### Access three.js material

You should set a *ref* on your material:

```html
<PhongMaterial ref="material" />
```

You can then access three.js material in your component script:

```js
const material = this.$ref.material.material;
```
