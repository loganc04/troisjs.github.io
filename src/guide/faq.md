# FAQ

### Is it really useful?

Building a scene with TroisJS is really handy, especially with VueJS and ViteJS HMR.

Using template tags, or custom components, make your code easier to re-use.

And you can easily handle events on meshes, use a physics engine, or add postprocessing effects...

### Are there any limitations?

No, you have access to three.js renderer, scene, etc...

### What about performance?

TroisJS is just a wrapper. Therefore, it is not slower than three.js (except if you use *reactivity* too much).

### How do you *dispose* of three.js objects?

You don't have to (except if you have created the objects yourself). TroisJS will automatically *dispose* geometries, materials, textures, renderer, effect passes, etc...

Why it is important: https://threejs.org/docs/#manual/en/introduction/How-to-dispose-of-objects

