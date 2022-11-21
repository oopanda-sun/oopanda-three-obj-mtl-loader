# obj-mtl-loader-three
[THREE.OBJLoader](https://threejs.org/examples/js/loaders/OBJLoader.js) repackaged as a node module
Threejs newest obj&amp;mtl loader with npm dev

## install

`npm i --save oopanda-three-obj-mtl-loader`


## usage

```js

import * as THREE from 'three'
import {MTLLoader, OBJLoader} from 'oopanda-three-obj-mtl-loader'

let scene = new THREE.Scene()

let mtlLoader = new MTLLoader();

let objLoader = new OBJLoader();

mtlLoader.load('./test.mtl', (materials) => {
  materials.preload()
  objLoader.setMaterials(materials)
  objLoader.load('./test.obj', (object) => {
    scene.add(object)
  })
})

```