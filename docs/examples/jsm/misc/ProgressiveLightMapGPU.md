[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ProgressiveLightMapGPU.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 20 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/misc/ProgressiveLightMapGPU.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DoubleSide` | `three/webgpu` |
| `FloatType` | `three/webgpu` |
| `HalfFloatType` | `three/webgpu` |
| `PlaneGeometry` | `three/webgpu` |
| `Mesh` | `three/webgpu` |
| `RenderTarget` | `three/webgpu` |
| `Scene` | `three/webgpu` |
| `MeshPhongNodeMaterial` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `add` | `three/tsl` |
| `float` | `three/tsl` |
| `mix` | `three/tsl` |
| `output` | `three/tsl` |
| `sub` | `three/tsl` |
| `texture` | `three/tsl` |
| `uniform` | `three/tsl` |
| `uv` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec4` | `three/tsl` |
| `potpack` | `../libs/potpack.module.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `type` | `any` | let/var | `/(Android\|iPad\|iPhone\|iPod)/g.test( navigator.userAgent ) ? HalfFloatType ...` | ✗ |
| `uv_boxes` | `any[]` | let/var | `[]` | ✗ |
| `padding` | `number` | let/var | `3 / this.resolution` | ✗ |
| `object` | `Object3D` | let/var | `objects[ ob ]` | ✗ |
| `activeMap` | `any` | let/var | `this._buffer1Active ? this._progressiveLightMap1 : this._progressiveLightMap2` | ✗ |
| `inactiveMap` | `any` | let/var | `this._buffer1Active ? this._progressiveLightMap2 : this._progressiveLightMap1` | ✗ |
| `labelMaterial` | `any` | let/var | `new NodeMaterial()` | ✗ |
| `labelGeometry` | `any` | let/var | `new PlaneGeometry( 100, 100 )` | ✗ |
| `blurMaterial` | `any` | let/var | `new NodeMaterial()` | ✗ |


---

## Functions

### `ProgressiveLightMap.addObjectsToLightMap(objects: Object3D[]): void`

**JSDoc:**
```typescript
/**
	 * Sets these objects' materials' lightmaps and modifies their uv1's.
	 *
	 * @param {Array<Object3D>} objects - An array of objects and lights to set up your lightmap.
	 */
```

**Parameters:**

- **`objects`** `Object3D[]`

**Returns:** `void`

**Calls:**

- `this._scene.attach`
- `object.geometry.hasAttribute`
- `console.warn`
- `this._initializeBlurPlane`
- `uv_boxes.push`
- `this._lightMapContainers.push`
- `potpack (from ../libs/potpack.module.js)`
- `uv_boxes.forEach`
- `objects[ box.index ].geometry.getAttribute( 'uv' ).clone`
- `objects[ box.index ].geometry.setAttribute`
- `objects[ box.index ].geometry.getAttribute`

**Internal Comments:**
```
// Prepare list of UV bounding boxes for packing later... (x2)
// If this object is a light, simply add it to the internal scene
// Apply the lightmap to the object (x5)
// Prepare UV boxes for potpack (potpack will update x and y) (x4)
// TODO: Size these by object surface area (x4)
// Pack the objects' lightmap UVs into the same global space (x2)
```

<details><summary>Code</summary>

```typescript
addObjectsToLightMap( objects ) {

		// Prepare list of UV bounding boxes for packing later...
		const uv_boxes = [];

		const padding = 3 / this.resolution;

		for ( let ob = 0; ob < objects.length; ob ++ ) {

			const object = objects[ ob ];

			// If this object is a light, simply add it to the internal scene
			if ( object.isLight ) {

				this._scene.attach( object ); continue;

			}

			if ( object.geometry.hasAttribute( 'uv' ) === false ) {

				console.warn( 'THREE.ProgressiveLightMap: All lightmap objects need uvs.' ); continue;

			}

			if ( this._blurringPlane === null ) {

				this._initializeBlurPlane();

			}

			// Apply the lightmap to the object
			object.material.lightMap = this._progressiveLightMap2.texture;
			object.material.dithering = true;
			object.castShadow = true;
			object.receiveShadow = true;
			object.renderOrder = 1000 + ob;

			// Prepare UV boxes for potpack (potpack will update x and y)
			// TODO: Size these by object surface area
			uv_boxes.push( { w: 1 + ( padding * 2 ), h: 1 + ( padding * 2 ), index: ob, x: 0, y: 0 } );

			this._lightMapContainers.push( { basicMat: object.material, object: object } );

		}

		// Pack the objects' lightmap UVs into the same global space
		const dimensions = potpack( uv_boxes );
		uv_boxes.forEach( ( box ) => {

			const uv1 = objects[ box.index ].geometry.getAttribute( 'uv' ).clone();
			for ( let i = 0; i < uv1.array.length; i += uv1.itemSize ) {

				uv1.array[ i ] = ( uv1.array[ i ] + box.x + padding ) / dimensions.w;
				uv1.array[ i + 1 ] = 1 - ( ( uv1.array[ i + 1 ] + box.y + padding ) / dimensions.h );

			}

			objects[ box.index ].geometry.setAttribute( 'uv1', uv1 );
			objects[ box.index ].geometry.getAttribute( 'uv1' ).needsUpdate = true;

		} );

	}
```
</details>

### `ProgressiveLightMap.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees all internal resources.
	 */
```

**Returns:** `void`

**Calls:**

- `this._progressiveLightMap1.dispose`
- `this._progressiveLightMap2.dispose`
- `this._uvMat.dispose`
- `this._blurringPlane.geometry.dispose`
- `this._blurringPlane.material.dispose`
- `this._labelMesh.geometry.dispose`
- `this._labelMesh.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._progressiveLightMap1.dispose();
		this._progressiveLightMap2.dispose();

		this._uvMat.dispose();

		if ( this._blurringPlane !== null ) {

			this._blurringPlane.geometry.dispose();
			this._blurringPlane.material.dispose();

		}

		if ( this._labelMesh !== null ) {

			this._labelMesh.geometry.dispose();
			this._labelMesh.material.dispose();

		}

	}
```
</details>

### `ProgressiveLightMap.update(camera: Camera, blendWindow: number, blurEdges: boolean): void`

**JSDoc:**
```typescript
/**
	 * This function renders each mesh one at a time into their respective surface maps.
	 *
	 * @param {Camera} camera - The camera the scene is rendered with.
	 * @param {number} [blendWindow=100] - When >1, samples will accumulate over time.
	 * @param {boolean} [blurEdges=true] - Whether to fix UV Edges via blurring.
	 */
```

**Parameters:**

- **`camera`** `Camera`
- **`blendWindow`** `number`
- **`blurEdges`** `boolean`

**Returns:** `void`

**Calls:**

- `this.renderer.getRenderTarget`
- `this._scene.attach`
- `this.renderer.setRenderTarget`
- `this.renderer.render`
- `this._lightMapContainers[ l ].object.oldScene.attach`

**Internal Comments:**
```
// Store the original Render Target (x2)
// The blurring plane applies blur to the seams of the lightmap (x5)
// Steal the Object3D from the real world to our special dimension
// Set each object's material to the UV Unwrapped Surface Mapping Version
// Ping-pong two surface buffers for reading/writing (x2)
// Render the object's surface maps (x5)
// Restore the object's Real-time Material and add it back to the original world
// Restore the original Render Target (x5)
```

<details><summary>Code</summary>

```typescript
update( camera, blendWindow = 100, blurEdges = true ) {

		if ( this._blurringPlane === null ) {

			return;

		}

		// Store the original Render Target
		const currentRenderTarget = this.renderer.getRenderTarget();

		// The blurring plane applies blur to the seams of the lightmap
		this._blurringPlane.visible = blurEdges;

		// Steal the Object3D from the real world to our special dimension
		for ( let l = 0; l < this._lightMapContainers.length; l ++ ) {

			this._lightMapContainers[ l ].object.oldScene = this._lightMapContainers[ l ].object.parent;
			this._scene.attach( this._lightMapContainers[ l ].object );

		}

		// Set each object's material to the UV Unwrapped Surface Mapping Version
		for ( let l = 0; l < this._lightMapContainers.length; l ++ ) {

			this._averagingWindow.value = blendWindow;
			this._lightMapContainers[ l ].object.material = this._uvMat;
			this._lightMapContainers[ l ].object.oldFrustumCulled = this._lightMapContainers[ l ].object.frustumCulled;
			this._lightMapContainers[ l ].object.frustumCulled = false;

		}

		// Ping-pong two surface buffers for reading/writing
		const activeMap = this._buffer1Active ? this._progressiveLightMap1 : this._progressiveLightMap2;
		const inactiveMap = this._buffer1Active ? this._progressiveLightMap2 : this._progressiveLightMap1;

		// Render the object's surface maps
		this.renderer.setRenderTarget( activeMap );
		this._previousShadowMap.value = inactiveMap.texture;

		this._buffer1Active = ! this._buffer1Active;
		this.renderer.render( this._scene, camera );

		// Restore the object's Real-time Material and add it back to the original world
		for ( let l = 0; l < this._lightMapContainers.length; l ++ ) {

			this._lightMapContainers[ l ].object.frustumCulled = this._lightMapContainers[ l ].object.oldFrustumCulled;
			this._lightMapContainers[ l ].object.material = this._lightMapContainers[ l ].basicMat;
			this._lightMapContainers[ l ].object.oldScene.attach( this._lightMapContainers[ l ].object );

		}

		// Restore the original Render Target
		this.renderer.setRenderTarget( currentRenderTarget );

	}
```
</details>

### `ProgressiveLightMap.showDebugLightmap(visible: boolean, position: Vector3): void`

**JSDoc:**
```typescript
/**
	 * Draws the lightmap in the main scene. Call this after adding the objects to it.
	 *
	 * @param {boolean} visible - Whether the debug plane should be visible
	 * @param {Vector3} [position] - Where the debug plane should be drawn
	*/
```

**Parameters:**

- **`visible`** `boolean`
- **`position`** `Vector3`

**Returns:** `void`

**Calls:**

- `console.warn`
- `texture( this._progressiveLightMap1.texture ).sample`
- `uv().flipY`
- `this._lightMapContainers[ 0 ].object.parent.add`
- `this._labelMesh.position.copy`

<details><summary>Code</summary>

```typescript
showDebugLightmap( visible, position = null ) {

		if ( this._lightMapContainers.length === 0 ) {

			console.warn( 'THREE.ProgressiveLightMap: Call .showDebugLightmap() after adding the objects.' );

			return;

		}

		if ( this._labelMesh === null ) {

			const labelMaterial = new NodeMaterial();
			labelMaterial.colorNode = texture( this._progressiveLightMap1.texture ).sample( uv().flipY() );
			labelMaterial.side = DoubleSide;

			const labelGeometry = new PlaneGeometry( 100, 100 );

			this._labelMesh = new Mesh( labelGeometry, labelMaterial );
			this._labelMesh.position.y = 250;

			this._lightMapContainers[ 0 ].object.parent.add( this._labelMesh );

		}

		if ( position !== null ) {

			this._labelMesh.position.copy( position );

		}

		this._labelMesh.visible = visible;

	}
```
</details>

### `ProgressiveLightMap._initializeBlurPlane(): void`

**JSDoc:**
```typescript
/**
	 * Creates the Blurring Plane.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `vec4 (from three/tsl)`
- `sub( uv(), vec2( 0.5 ) ).mul`
- `uv().flipY().toVar`
- `float( 0.5 ).div( float( this.resolution ) ).toVar`
- `add(
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, 0 ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( 0, pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( 0, pixelOffset.negate() ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), 0 ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, pixelOffset.negate() ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), pixelOffset.negate() ) ) ),
		).div`
- `this._scene.add`

<details><summary>Code</summary>

```typescript
_initializeBlurPlane() {

		const blurMaterial = new NodeMaterial();
		blurMaterial.polygonOffset = true;
		blurMaterial.polygonOffsetFactor = - 1;
		blurMaterial.polygonOffsetUnits = 3;

		blurMaterial.vertexNode = vec4( sub( uv(), vec2( 0.5 ) ).mul( 2 ), 1, 1 );

		const uvNode = uv().flipY().toVar();
		const pixelOffset = float( 0.5 ).div( float( this.resolution ) ).toVar();

		const color = add(
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, 0 ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( 0, pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( 0, pixelOffset.negate() ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), 0 ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, pixelOffset.negate() ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), pixelOffset.negate() ) ) ),
		).div( 8 );

		blurMaterial.fragmentNode = color;

		this._blurringPlane = new Mesh( new PlaneGeometry( 1, 1 ), blurMaterial );
		this._blurringPlane.name = 'Blurring Plane';
		this._blurringPlane.frustumCulled = false;
		this._blurringPlane.renderOrder = 0;
		this._blurringPlane.material.depthWrite = false;
		this._scene.add( this._blurringPlane );

	}
```
</details>


---

## Classes

### `ProgressiveLightMap`

<details><summary>Class Code</summary>

```ts
class ProgressiveLightMap {

	/**
	 * @param {WebGPURenderer} renderer - The renderer.
	 * @param {number} [resolution=1024] - The side-long dimension of the total lightmap.
	 */
	constructor( renderer, resolution = 1024 ) {

		/**
		 * The renderer.
		 *
		 * @type {WebGPURenderer}
		 */
		this.renderer = renderer;

		/**
		 * The side-long dimension of the total lightmap.
		 *
		 * @type {number}
		 * @default 1024
		 */
		this.resolution = resolution;

		this._lightMapContainers = [];
		this._scene = new Scene();
		this._buffer1Active = false;
		this._labelMesh = null;
		this._blurringPlane = null;

		// Create the Progressive LightMap Texture

		const type = /(Android|iPad|iPhone|iPod)/g.test( navigator.userAgent ) ? HalfFloatType : FloatType;
		this._progressiveLightMap1 = new RenderTarget( this.resolution, this.resolution, { type: type } );
		this._progressiveLightMap2 = new RenderTarget( this.resolution, this.resolution, { type: type } );
		this._progressiveLightMap2.texture.channel = 1;

		// uniforms

		this._averagingWindow = uniform( 100 );
		this._previousShadowMap = texture( this._progressiveLightMap1.texture );

		// materials

		const uvNode = uv( 1 ).flipY();

		this._uvMat = new MeshPhongNodeMaterial();
		this._uvMat.vertexNode = vec4( sub( uvNode, vec2( 0.5 ) ).mul( 2 ), 1, 1 );
		this._uvMat.outputNode = vec4( mix( this._previousShadowMap.sample( uv( 1 ) ), output, float( 1 ).div( this._averagingWindow ) ) );

	}

	/**
	 * Sets these objects' materials' lightmaps and modifies their uv1's.
	 *
	 * @param {Array<Object3D>} objects - An array of objects and lights to set up your lightmap.
	 */
	addObjectsToLightMap( objects ) {

		// Prepare list of UV bounding boxes for packing later...
		const uv_boxes = [];

		const padding = 3 / this.resolution;

		for ( let ob = 0; ob < objects.length; ob ++ ) {

			const object = objects[ ob ];

			// If this object is a light, simply add it to the internal scene
			if ( object.isLight ) {

				this._scene.attach( object ); continue;

			}

			if ( object.geometry.hasAttribute( 'uv' ) === false ) {

				console.warn( 'THREE.ProgressiveLightMap: All lightmap objects need uvs.' ); continue;

			}

			if ( this._blurringPlane === null ) {

				this._initializeBlurPlane();

			}

			// Apply the lightmap to the object
			object.material.lightMap = this._progressiveLightMap2.texture;
			object.material.dithering = true;
			object.castShadow = true;
			object.receiveShadow = true;
			object.renderOrder = 1000 + ob;

			// Prepare UV boxes for potpack (potpack will update x and y)
			// TODO: Size these by object surface area
			uv_boxes.push( { w: 1 + ( padding * 2 ), h: 1 + ( padding * 2 ), index: ob, x: 0, y: 0 } );

			this._lightMapContainers.push( { basicMat: object.material, object: object } );

		}

		// Pack the objects' lightmap UVs into the same global space
		const dimensions = potpack( uv_boxes );
		uv_boxes.forEach( ( box ) => {

			const uv1 = objects[ box.index ].geometry.getAttribute( 'uv' ).clone();
			for ( let i = 0; i < uv1.array.length; i += uv1.itemSize ) {

				uv1.array[ i ] = ( uv1.array[ i ] + box.x + padding ) / dimensions.w;
				uv1.array[ i + 1 ] = 1 - ( ( uv1.array[ i + 1 ] + box.y + padding ) / dimensions.h );

			}

			objects[ box.index ].geometry.setAttribute( 'uv1', uv1 );
			objects[ box.index ].geometry.getAttribute( 'uv1' ).needsUpdate = true;

		} );

	}

	/**
	 * Frees all internal resources.
	 */
	dispose() {

		this._progressiveLightMap1.dispose();
		this._progressiveLightMap2.dispose();

		this._uvMat.dispose();

		if ( this._blurringPlane !== null ) {

			this._blurringPlane.geometry.dispose();
			this._blurringPlane.material.dispose();

		}

		if ( this._labelMesh !== null ) {

			this._labelMesh.geometry.dispose();
			this._labelMesh.material.dispose();

		}

	}

	/**
	 * This function renders each mesh one at a time into their respective surface maps.
	 *
	 * @param {Camera} camera - The camera the scene is rendered with.
	 * @param {number} [blendWindow=100] - When >1, samples will accumulate over time.
	 * @param {boolean} [blurEdges=true] - Whether to fix UV Edges via blurring.
	 */
	update( camera, blendWindow = 100, blurEdges = true ) {

		if ( this._blurringPlane === null ) {

			return;

		}

		// Store the original Render Target
		const currentRenderTarget = this.renderer.getRenderTarget();

		// The blurring plane applies blur to the seams of the lightmap
		this._blurringPlane.visible = blurEdges;

		// Steal the Object3D from the real world to our special dimension
		for ( let l = 0; l < this._lightMapContainers.length; l ++ ) {

			this._lightMapContainers[ l ].object.oldScene = this._lightMapContainers[ l ].object.parent;
			this._scene.attach( this._lightMapContainers[ l ].object );

		}

		// Set each object's material to the UV Unwrapped Surface Mapping Version
		for ( let l = 0; l < this._lightMapContainers.length; l ++ ) {

			this._averagingWindow.value = blendWindow;
			this._lightMapContainers[ l ].object.material = this._uvMat;
			this._lightMapContainers[ l ].object.oldFrustumCulled = this._lightMapContainers[ l ].object.frustumCulled;
			this._lightMapContainers[ l ].object.frustumCulled = false;

		}

		// Ping-pong two surface buffers for reading/writing
		const activeMap = this._buffer1Active ? this._progressiveLightMap1 : this._progressiveLightMap2;
		const inactiveMap = this._buffer1Active ? this._progressiveLightMap2 : this._progressiveLightMap1;

		// Render the object's surface maps
		this.renderer.setRenderTarget( activeMap );
		this._previousShadowMap.value = inactiveMap.texture;

		this._buffer1Active = ! this._buffer1Active;
		this.renderer.render( this._scene, camera );

		// Restore the object's Real-time Material and add it back to the original world
		for ( let l = 0; l < this._lightMapContainers.length; l ++ ) {

			this._lightMapContainers[ l ].object.frustumCulled = this._lightMapContainers[ l ].object.oldFrustumCulled;
			this._lightMapContainers[ l ].object.material = this._lightMapContainers[ l ].basicMat;
			this._lightMapContainers[ l ].object.oldScene.attach( this._lightMapContainers[ l ].object );

		}

		// Restore the original Render Target
		this.renderer.setRenderTarget( currentRenderTarget );

	}

	/**
	 * Draws the lightmap in the main scene. Call this after adding the objects to it.
	 *
	 * @param {boolean} visible - Whether the debug plane should be visible
	 * @param {Vector3} [position] - Where the debug plane should be drawn
	*/
	showDebugLightmap( visible, position = null ) {

		if ( this._lightMapContainers.length === 0 ) {

			console.warn( 'THREE.ProgressiveLightMap: Call .showDebugLightmap() after adding the objects.' );

			return;

		}

		if ( this._labelMesh === null ) {

			const labelMaterial = new NodeMaterial();
			labelMaterial.colorNode = texture( this._progressiveLightMap1.texture ).sample( uv().flipY() );
			labelMaterial.side = DoubleSide;

			const labelGeometry = new PlaneGeometry( 100, 100 );

			this._labelMesh = new Mesh( labelGeometry, labelMaterial );
			this._labelMesh.position.y = 250;

			this._lightMapContainers[ 0 ].object.parent.add( this._labelMesh );

		}

		if ( position !== null ) {

			this._labelMesh.position.copy( position );

		}

		this._labelMesh.visible = visible;

	}

	/**
	 * Creates the Blurring Plane.
	 *
	 * @private
	 */
	_initializeBlurPlane() {

		const blurMaterial = new NodeMaterial();
		blurMaterial.polygonOffset = true;
		blurMaterial.polygonOffsetFactor = - 1;
		blurMaterial.polygonOffsetUnits = 3;

		blurMaterial.vertexNode = vec4( sub( uv(), vec2( 0.5 ) ).mul( 2 ), 1, 1 );

		const uvNode = uv().flipY().toVar();
		const pixelOffset = float( 0.5 ).div( float( this.resolution ) ).toVar();

		const color = add(
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, 0 ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( 0, pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( 0, pixelOffset.negate() ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), 0 ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, pixelOffset.negate() ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), pixelOffset.negate() ) ) ),
		).div( 8 );

		blurMaterial.fragmentNode = color;

		this._blurringPlane = new Mesh( new PlaneGeometry( 1, 1 ), blurMaterial );
		this._blurringPlane.name = 'Blurring Plane';
		this._blurringPlane.frustumCulled = false;
		this._blurringPlane.renderOrder = 0;
		this._blurringPlane.material.depthWrite = false;
		this._scene.add( this._blurringPlane );

	}

}
```
</details>

#### Methods

##### `addObjectsToLightMap(objects: Object3D[]): void`

<details><summary>Code</summary>

```ts
addObjectsToLightMap( objects ) {

		// Prepare list of UV bounding boxes for packing later...
		const uv_boxes = [];

		const padding = 3 / this.resolution;

		for ( let ob = 0; ob < objects.length; ob ++ ) {

			const object = objects[ ob ];

			// If this object is a light, simply add it to the internal scene
			if ( object.isLight ) {

				this._scene.attach( object ); continue;

			}

			if ( object.geometry.hasAttribute( 'uv' ) === false ) {

				console.warn( 'THREE.ProgressiveLightMap: All lightmap objects need uvs.' ); continue;

			}

			if ( this._blurringPlane === null ) {

				this._initializeBlurPlane();

			}

			// Apply the lightmap to the object
			object.material.lightMap = this._progressiveLightMap2.texture;
			object.material.dithering = true;
			object.castShadow = true;
			object.receiveShadow = true;
			object.renderOrder = 1000 + ob;

			// Prepare UV boxes for potpack (potpack will update x and y)
			// TODO: Size these by object surface area
			uv_boxes.push( { w: 1 + ( padding * 2 ), h: 1 + ( padding * 2 ), index: ob, x: 0, y: 0 } );

			this._lightMapContainers.push( { basicMat: object.material, object: object } );

		}

		// Pack the objects' lightmap UVs into the same global space
		const dimensions = potpack( uv_boxes );
		uv_boxes.forEach( ( box ) => {

			const uv1 = objects[ box.index ].geometry.getAttribute( 'uv' ).clone();
			for ( let i = 0; i < uv1.array.length; i += uv1.itemSize ) {

				uv1.array[ i ] = ( uv1.array[ i ] + box.x + padding ) / dimensions.w;
				uv1.array[ i + 1 ] = 1 - ( ( uv1.array[ i + 1 ] + box.y + padding ) / dimensions.h );

			}

			objects[ box.index ].geometry.setAttribute( 'uv1', uv1 );
			objects[ box.index ].geometry.getAttribute( 'uv1' ).needsUpdate = true;

		} );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._progressiveLightMap1.dispose();
		this._progressiveLightMap2.dispose();

		this._uvMat.dispose();

		if ( this._blurringPlane !== null ) {

			this._blurringPlane.geometry.dispose();
			this._blurringPlane.material.dispose();

		}

		if ( this._labelMesh !== null ) {

			this._labelMesh.geometry.dispose();
			this._labelMesh.material.dispose();

		}

	}
```
</details>

##### `update(camera: Camera, blendWindow: number, blurEdges: boolean): void`

<details><summary>Code</summary>

```ts
update( camera, blendWindow = 100, blurEdges = true ) {

		if ( this._blurringPlane === null ) {

			return;

		}

		// Store the original Render Target
		const currentRenderTarget = this.renderer.getRenderTarget();

		// The blurring plane applies blur to the seams of the lightmap
		this._blurringPlane.visible = blurEdges;

		// Steal the Object3D from the real world to our special dimension
		for ( let l = 0; l < this._lightMapContainers.length; l ++ ) {

			this._lightMapContainers[ l ].object.oldScene = this._lightMapContainers[ l ].object.parent;
			this._scene.attach( this._lightMapContainers[ l ].object );

		}

		// Set each object's material to the UV Unwrapped Surface Mapping Version
		for ( let l = 0; l < this._lightMapContainers.length; l ++ ) {

			this._averagingWindow.value = blendWindow;
			this._lightMapContainers[ l ].object.material = this._uvMat;
			this._lightMapContainers[ l ].object.oldFrustumCulled = this._lightMapContainers[ l ].object.frustumCulled;
			this._lightMapContainers[ l ].object.frustumCulled = false;

		}

		// Ping-pong two surface buffers for reading/writing
		const activeMap = this._buffer1Active ? this._progressiveLightMap1 : this._progressiveLightMap2;
		const inactiveMap = this._buffer1Active ? this._progressiveLightMap2 : this._progressiveLightMap1;

		// Render the object's surface maps
		this.renderer.setRenderTarget( activeMap );
		this._previousShadowMap.value = inactiveMap.texture;

		this._buffer1Active = ! this._buffer1Active;
		this.renderer.render( this._scene, camera );

		// Restore the object's Real-time Material and add it back to the original world
		for ( let l = 0; l < this._lightMapContainers.length; l ++ ) {

			this._lightMapContainers[ l ].object.frustumCulled = this._lightMapContainers[ l ].object.oldFrustumCulled;
			this._lightMapContainers[ l ].object.material = this._lightMapContainers[ l ].basicMat;
			this._lightMapContainers[ l ].object.oldScene.attach( this._lightMapContainers[ l ].object );

		}

		// Restore the original Render Target
		this.renderer.setRenderTarget( currentRenderTarget );

	}
```
</details>

##### `showDebugLightmap(visible: boolean, position: Vector3): void`

<details><summary>Code</summary>

```ts
showDebugLightmap( visible, position = null ) {

		if ( this._lightMapContainers.length === 0 ) {

			console.warn( 'THREE.ProgressiveLightMap: Call .showDebugLightmap() after adding the objects.' );

			return;

		}

		if ( this._labelMesh === null ) {

			const labelMaterial = new NodeMaterial();
			labelMaterial.colorNode = texture( this._progressiveLightMap1.texture ).sample( uv().flipY() );
			labelMaterial.side = DoubleSide;

			const labelGeometry = new PlaneGeometry( 100, 100 );

			this._labelMesh = new Mesh( labelGeometry, labelMaterial );
			this._labelMesh.position.y = 250;

			this._lightMapContainers[ 0 ].object.parent.add( this._labelMesh );

		}

		if ( position !== null ) {

			this._labelMesh.position.copy( position );

		}

		this._labelMesh.visible = visible;

	}
```
</details>

##### `_initializeBlurPlane(): void`

<details><summary>Code</summary>

```ts
_initializeBlurPlane() {

		const blurMaterial = new NodeMaterial();
		blurMaterial.polygonOffset = true;
		blurMaterial.polygonOffsetFactor = - 1;
		blurMaterial.polygonOffsetUnits = 3;

		blurMaterial.vertexNode = vec4( sub( uv(), vec2( 0.5 ) ).mul( 2 ), 1, 1 );

		const uvNode = uv().flipY().toVar();
		const pixelOffset = float( 0.5 ).div( float( this.resolution ) ).toVar();

		const color = add(
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, 0 ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( 0, pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( 0, pixelOffset.negate() ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), 0 ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), pixelOffset ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset, pixelOffset.negate() ) ) ),
			this._previousShadowMap.sample( uvNode.add( vec2( pixelOffset.negate(), pixelOffset.negate() ) ) ),
		).div( 8 );

		blurMaterial.fragmentNode = color;

		this._blurringPlane = new Mesh( new PlaneGeometry( 1, 1 ), blurMaterial );
		this._blurringPlane.name = 'Blurring Plane';
		this._blurringPlane.frustumCulled = false;
		this._blurringPlane.renderOrder = 0;
		this._blurringPlane.material.depthWrite = false;
		this._scene.add( this._blurringPlane );

	}
```
</details>


---