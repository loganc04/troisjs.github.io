# Scene

See [Scene.ts](https://github.com/troisjs/trois/blob/master/src/core/Scene.ts) and [THREE.Scene](https://threejs.org/docs/#api/en/scenes/Scene).

<table>
  <tbody>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Type</th>
      <th>Default</th>
    </tr>
    <tr>
      <td><code>background</code></td>
      <td>Background color.</td>
      <td>String, Number</td>
      <td></td>
    </tr>
  </tbody>
</table>

::: tip
If you need a transparent renderer, you should use `alpha` on the [renderer](renderer).
:::

### Access three.js scene

You should set a *ref* on the scene :

```html
<Scene ref="scene">
  ...
</Scene>
```

You can then access three.js scene in your component script :

```js
const scene = this.$refs.scene.scene;
```
