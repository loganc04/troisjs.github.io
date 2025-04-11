# Events (v0.3.2)

You can easily handle mouse or touch events on your meshes.

::: tip
To be able to handle events on three.js objects, TroisJS uses *raycasting*. 

Read more : https://threejs.org/docs/#api/en/core/Raycaster
:::

## Mesh Events

You can use the following props to handle events on a *Mesh* or *InstancedMesh*:

<table>
  <tbody>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Event type</th>
      <th>Parameters</th>
    </tr>
    <tr>
      <td><code>onPointerEnter</code></td>
      <td>When the pointer enters a mesh</td>
      <td><code>pointerenter</code></td>
      <td><code>{ type, over: true, component, intersect }</code></td>
    </tr>
    <tr>
      <td><code>onPointerOver</code></td>
      <td>When the pointer enters or leaves a mesh</td>
      <td><code>pointerover</code></td>
      <td><code>{ type, over, component, intersect? }</code></td>
    </tr>
    <tr>
      <td><code>onPointerMove</code></td>
      <td>When the pointer moves over a mesh</td>
      <td><code>pointermove</code></td>
      <td><code>{ type, component, intersect }</code></td>
    </tr>
    <tr>
      <td><code>onPointerLeave</code></td>
      <td>When the pointer leaves a mesh</td>
      <td><code>pointerleave</code></td>
      <td><code>{ type, over: false, component }</code></td>
    </tr>
    <tr>
      <td><code>onClick</code></td>
      <td>When the pointer clicks on a mesh</td>
      <td><code>click</code></td>
      <td><code>{ type, component, intersect }</code></td>
    </tr>
  </tbody>
</table>

Example :

```vue
<template>
  <Renderer antialias resize="window">
    <Camera :position="{ z: 10 }" />
    <Scene>
      <PointLight :position="{ y: 10, z: 10 }" />
      <Box
        @pointerEnter="onPointerEvent"
        @pointerOver="onPointerOver"
        @pointerMove="onPointerEvent"
        @pointerLeave="onPointerEvent"
        @click="onPointerEvent"
      >
        <LambertMaterial />
      </Box>
    </Scene>
  </Renderer>
</template>

<script>
export default {
  methods: {
    onPointerEvent(event) {
      console.log(event);
    },
    onPointerOver(event) {
      event.component.mesh.material.color.set(event.over ? 0xff0000 : 0xffffff);
    },
  },
};
</script>
```

## Raycaster Component

If you need to easily handle pointer events on all your scene's meshes, you can use `Raycaster` component :

```vue
<template>
  <Renderer antialias resize="window">
    <Camera :position="{ z: 10 }" />
    <Raycaster
      @pointerEnter="onPointerEvent"
      @pointerOver="onPointerOver"
      @pointerMove="onPointerEvent"
      @pointerLeave="onPointerEvent"
      @click="onPointerEvent"
    />
    <Scene>
      <PointLight :position="{ y: 10, z: 10 }" />
      <Box v-for="i in 5" :position="{ x: -6 + i * 2 }">
        <LambertMaterial />
      </Box>
    </Scene>
  </Renderer>
</template>

<script>
export default {
  methods: {
    onPointerEvent(event) {
      console.log(event);
    },
    onPointerOver(event) {
      event.component.mesh.material.color.set(event.over ? 0xff0000 : 0xffffff);
    },
  },
};
</script>
```

### `intersectMode`

By default, raycasting will be made on pointer move, but it can be useful to do the same on every frame.

If using mesh events, you should set `pointer` prop on `Renderer` :

```html
<Renderer :pointer="{ intersectMode: 'frame' }">
  ...
</Renderer>
```

If using `Raycaster` component, you should set `intersect-mode` prop :

```html
<Raycaster intersect-mode="frame" />
```

### `intersectRecursive`

If present (=`true`), it also checks all descendants. Otherwise it only checks intersection with the object.

Default is `false`.

```html
<Raycaster intersect-recursive />
```

Starting in v0.3.2 GLTF-models accept raycasting events as well. To make use of this **you have to** set `intersectRecursive` to `true` depending on your implementation:

1. `Mesh` based events (each mesh reports needs its own interaction events)
```html
<Renderer :pointer="{ intersectRecursive: true }">
  <Camera :position="{ z: 1 }" />
  <Scene>
    <GltfModel @click="onClick" src="..." />
  </Scene>
</Renderer>
```

2. `Raycaster` based implementation (one event fires no matter which object reports a collision)
```html
<Renderer>
  <Camera :position="{ z: 1 }" />
  <Scene>
    <Raycaster intersect-recursive @click="onClick" />
    <GltfModel src="..." />
  </Scene>
</Renderer>
```