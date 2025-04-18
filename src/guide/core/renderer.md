# Renderer

See [Renderer.ts](https://github.com/troisjs/trois/blob/master/src/core/Renderer.ts) and [THREE.WebGLRenderer](https://threejs.org/docs/#api/en/renderers/WebGLRenderer).

## Props from `THREE.WebGLRenderer`

<table>
  <tbody>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Type</th>
      <th>Default</th>
    </tr>
    <tr>
      <td><code>alpha</code></td>
      <td>Whether the canvas contains an alpha (transparency) buffer or not.</td>
      <td>Boolean</td>
      <td>false</td>
    </tr>
    <tr>
      <td><code>antialias</code></td>
      <td>Whether to perform antialiasing.</td>
      <td>Boolean</td>
      <td>false</td>
    </tr>
    <tr>
      <td><code>autoClear</code></td>
      <td>Defines whether the renderer should automatically clear its output before rendering a frame.</td>
      <td>Boolean</td>
      <td>true</td>
    </tr>
  </tbody>
</table>

## Custom Props

<table>
  <tbody>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Type</th>
      <th>Default</th>
    </tr>
    <tr>
      <td><code>orbitCtrl</code></td>
      <td>Enable/disable OrbitControls. If the value is an Object, it will be used to configure [OrbitControls](#access-threejs-orbitcontrols).</td>
      <td>Boolean, Object</td>
      <td>false</td>
    </tr>
    <tr>
      <td><code>pointer</code></td>
      <td>
        Listen for pointer events to track mouse or touch positions (2D and 3D). Use <code>renderer.three.pointer</code> to get:
        <ul>
          <li><code>position</code>: 2D position.</li>
          <li><code>positionN</code>: nomalized position, can be used for raycasting.</li>
          <li><code>'positionV3'</code>: 3D position.</li>
        </ul>
      </td>
      <td>Boolean, Object</td>
      <td>false</td>
    </tr>
    <tr>
      <td><code>resize</code></td>
      <td>
        Resize canvas on window resize.
        <ul>
          <li><code>false</code>: disabled</li>
          <li><code>true</code>: parent size</li>
          <li><code>'window'</code>: window size</li>
        </ul>
        To directly set the size of the renderer, you can call the built in three.js function:
        <code>this.$refs.renderer.three.setSize(width, height)</code>
      </td>
      <td>Boolean, String</td>
      <td>false</td>
    </tr>
    <tr>
      <td><code>shadow</code></td>
      <td>Use shadow or not.</td>
      <td>Boolean</td>
      <td>false</td>
    </tr>
    <tr>
      <td><code>width</code></td>
      <td>Fixed width</td>
      <td>Number</td>
      <td></td>
    </tr>
    <tr>
      <td><code>height</code></td>
      <td>Fixed height</td>
      <td>Number</td>
      <td></td>
    </tr>
  </tbody>
</table>

## Events API (v0.3)

You can use the following functions to add/remove event listeners on Renderer components:

<table>
  <tbody>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Event </th>
    </tr>
    <tr>
      <td><code>onInit</code></td>
      <td>Add <em>init</em> listener</td>
      <td><code>{ type: 'init', renderer }</code></td>
    </tr>
    <tr>
      <td><code>onMounted</code></td>
      <td>Add <em>mounted</em> listener</td>
      <td><code>{ type: 'mounted', renderer }</code></td>
    </tr>
    <tr>
      <td><code>onResize</code></td>
      <td>Add <em>resize</em> listener</td>
      <td><code>{ type: 'init', renderer, size }</code></td>
    </tr>
    <tr>
      <td><code>onBeforeRender</code></td>
      <td>Add <em>beforerender</em> listener</td>
      <td><code>{ type: 'beforerender', renderer, time }</code></td>
    </tr>
    <tr>
      <td><code>offBeforeRender</code></td>
      <td>Remove <em>beforerender</em> listener</td>
      <td></td>
    </tr>
    <tr>
      <td><code>onAfterRender</code></td>
      <td>Add <em>afterrender</em> listener</td>
      <td><code>{ type: 'afterrender', renderer, time }</code></td>
    </tr>
    <tr>
      <td><code>offAfterRender</code></td>
      <td>Remove <em>afterrender</em> listener</td>
      <td></td>
    </tr>
  </tbody>
</table>


You can also use:

<table>
  <tbody>
    <tr>
      <th>Name</th>
      <th>Description</th>
    </tr>
    <tr>
      <td><code>addListener(type, callback)</code></td>
      <td>Add event listener</td>
    </tr>
    <tr>
      <td><code>removeListener(type, callback)</code></td>
      <td>Remove event listener</td>
    </tr>
  </tbody>
</table>

## Custom render function

You can use a custom render function:

```js
const renderer = this.$refs.renderer
renderer.onInit(() => {
  renderer.renderFn = () => {
    // do what you want
  }
})
```

## Access three.js renderer

You should set a *ref* on the renderer:

```html
<Renderer ref="renderer">
  ...
</Renderer>
```

You can then access three.js renderer in your component script:

```js
const renderer = this.$refs.renderer.renderer;
```

## Access three.js OrbitControls

In the same fashion you can access the renderer's `three` object which contains different functions to control the scene, amongst which is `cameraCtrl`, handling the three.js `OrbitControls` settings

```js
const orbitCtrl = this.$refs.renderer.three.cameraCtrl;
```

### Events

To use events, apply an event listener in `mounted()` section of your App.

```js

orbitCtrl.addEventListener('change', () => {
      // Do something when the camera has been transformed by the controls.
    })

orbitCtrl.addEventListener('start', () => {
      // Do something when an interaction was initiated.
    })

orbitCtrl.addEventListener('end', () => {
      // Do something when an interaction has finished.
    })

```


### Properties, Methods
You can apply all properties and methods in the same way as listed in the official [three.js docs](https://threejs.org/docs/?q=orbit#examples/en/controls/OrbitControls)

Example:

```js
orbitCtrl.enablePan = false
```
