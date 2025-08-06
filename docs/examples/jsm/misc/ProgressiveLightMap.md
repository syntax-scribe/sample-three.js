[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ProgressiveLightMap.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/misc/ProgressiveLightMap.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DoubleSide` | `three` |
| `FloatType` | `three` |
| `HalfFloatType` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `MeshPhongMaterial` | `three` |
| `PlaneGeometry` | `three` |
| `Scene` | `three` |
| `WebGLRenderTarget` | `three` |
| `potpack` | `../libs/potpack.module.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `format` | `any` | let/var | `/(Android\|iPad\|iPhone\|iPod)/g.test( navigator.userAgent ) ? HalfFloatType ...` | ✗ |
| `padding` | `number` | let/var | `3 / this.res` | ✗ |
| `object` | `Object3D` | let/var | `objects[ ob ]` | ✗ |
| `activeMap` | `any` | let/var | `this.buffer1Active ? this.progressiveLightMap1 : this.progressiveLightMap2` | ✗ |
| `inactiveMap` | `any` | let/var | `this.buffer1Active ? this.progressiveLightMap2 : this.progressiveLightMap1` | ✗ |
| `labelMaterial` | `any` | let/var | `new MeshBasicMaterial( { map: this.progressiveLightMap1.texture, side: Double...` | ✗ |
| `labelGeometry` | `any` | let/var | `new PlaneGeometry( 100, 100 )` | ✗ |
| `blurMaterial` | `any` | let/var | `new MeshBasicMaterial()` | ✗ |


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

- `this.scene.attach`
- `object.geometry.hasAttribute`
- `console.warn`
- `this._initializeBlurPlane`
- `this.uv_boxes.push`
- `this.lightMapContainers.push`
- `potpack (from ../libs/potpack.module.js)`
- `this.uv_boxes.forEach`
- `objects[ box.index ].geometry.getAttribute( 'uv' ).clone`
- `objects[ box.index ].geometry.setAttribute`
- `objects[ box.index ].geometry.getAttribute`

**Internal Comments:**
```
// Prepare list of UV bounding boxes for packing later... (x4)
// If this object is a light, simply add it to the internal scene
// Apply the lightmap to the object (x5)
// Prepare UV boxes for potpack (x5)
// TODO: Size these by object surface area (x5)
// Pack the objects' lightmap UVs into the same global space (x2)
```

<details><summary>Code</summary>

```typescript
addObjectsToLightMap( objects ) {

		// Prepare list of UV bounding boxes for packing later...
		this.uv_boxes = []; const padding = 3 / this.res;

		for ( let ob = 0; ob < objects.length; ob ++ ) {

			const object = objects[ ob ];

			// If this object is a light, simply add it to the internal scene
			if ( object.isLight ) {

				this.scene.attach( object ); continue;

			}

			if ( object.geometry.hasAttribute( 'uv' ) === false ) {

				console.warn( 'THREE.ProgressiveLightMap: All lightmap objects need uvs.' ); continue;

			}

			if ( this.blurringPlane === null ) {

				this._initializeBlurPlane( this.res, this.progressiveLightMap1 );

			}

			// Apply the lightmap to the object
			object.material.lightMap = this.progressiveLightMap2.texture;
			object.material.dithering = true;
			object.castShadow = true;
			object.receiveShadow = true;
			object.renderOrder = 1000 + ob;

			// Prepare UV boxes for potpack
			// TODO: Size these by object surface area
			this.uv_boxes.push( { w: 1 + ( padding * 2 ),
								  h: 1 + ( padding * 2 ), index: ob } );

			this.lightMapContainers.push( { basicMat: object.material, object: object } );

		}

		// Pack the objects' lightmap UVs into the same global space
		const dimensions = potpack( this.uv_boxes );
		this.uv_boxes.forEach( ( box ) => {

			const uv1 = objects[ box.index ].geometry.getAttribute( 'uv' ).clone();
			for ( let i = 0; i < uv1.array.length; i += uv1.itemSize ) {

				uv1.array[ i ] = ( uv1.array[ i ] + box.x + padding ) / dimensions.w;
				uv1.array[ i + 1 ] = ( uv1.array[ i + 1 ] + box.y + padding ) / dimensions.h;

			}

			objects[ box.index ].geometry.setAttribute( 'uv1', uv1 );
			objects[ box.index ].geometry.getAttribute( 'uv1' ).needsUpdate = true;

		} );

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
- `this.scene.attach`
- `this.renderer.compile`
- `this.renderer.setRenderTarget`
- `this.renderer.render`
- `this.lightMapContainers[ l ].object.oldScene.attach`

**Internal Comments:**
```
// Store the original Render Target (x2)
// The blurring plane applies blur to the seams of the lightmap (x5)
// Steal the Object3D from the real world to our special dimension
// Initialize everything
// Set each object's material to the UV Unwrapped Surface Mapping Version
// Ping-pong two surface buffers for reading/writing (x2)
// Render the object's surface maps (x5)
// Restore the object's Real-time Material and add it back to the original world
// Restore the original Render Target (x5)
```

<details><summary>Code</summary>

```typescript
update( camera, blendWindow = 100, blurEdges = true ) {

		if ( this.blurringPlane === null ) {

			return;

		}

		// Store the original Render Target
		const oldTarget = this.renderer.getRenderTarget();

		// The blurring plane applies blur to the seams of the lightmap
		this.blurringPlane.visible = blurEdges;

		// Steal the Object3D from the real world to our special dimension
		for ( let l = 0; l < this.lightMapContainers.length; l ++ ) {

			this.lightMapContainers[ l ].object.oldScene =
				this.lightMapContainers[ l ].object.parent;
			this.scene.attach( this.lightMapContainers[ l ].object );

		}

		// Initialize everything
		if ( this.firstUpdate === true ) {

			this.renderer.compile( this.scene, camera );
			this.firstUpdate = false;

		}

		// Set each object's material to the UV Unwrapped Surface Mapping Version
		for ( let l = 0; l < this.lightMapContainers.length; l ++ ) {

			this.uvMat.uniforms.averagingWindow = { value: blendWindow };
			this.lightMapContainers[ l ].object.material = this.uvMat;
			this.lightMapContainers[ l ].object.oldFrustumCulled =
				this.lightMapContainers[ l ].object.frustumCulled;
			this.lightMapContainers[ l ].object.frustumCulled = false;

		}

		// Ping-pong two surface buffers for reading/writing
		const activeMap = this.buffer1Active ? this.progressiveLightMap1 : this.progressiveLightMap2;
		const inactiveMap = this.buffer1Active ? this.progressiveLightMap2 : this.progressiveLightMap1;

		// Render the object's surface maps
		this.renderer.setRenderTarget( activeMap );
		this.uvMat.uniforms.previousShadowMap = { value: inactiveMap.texture };
		this.blurringPlane.material.uniforms.previousShadowMap = { value: inactiveMap.texture };
		this.buffer1Active = ! this.buffer1Active;
		this.renderer.render( this.scene, camera );

		// Restore the object's Real-time Material and add it back to the original world
		for ( let l = 0; l < this.lightMapContainers.length; l ++ ) {

			this.lightMapContainers[ l ].object.frustumCulled =
				this.lightMapContainers[ l ].object.oldFrustumCulled;
			this.lightMapContainers[ l ].object.material = this.lightMapContainers[ l ].basicMat;
			this.lightMapContainers[ l ].object.oldScene.attach( this.lightMapContainers[ l ].object );

		}

		// Restore the original Render Target
		this.renderer.setRenderTarget( oldTarget );

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
- `this.lightMapContainers[ 0 ].object.parent.add`
- `this.labelMesh.position.copy`

<details><summary>Code</summary>

```typescript
showDebugLightmap( visible, position = undefined ) {

		if ( this.lightMapContainers.length === 0 ) {

			console.warn( 'THREE.ProgressiveLightMap: Call .showDebugLightmap() after adding the objects.' );

			return;

		}

		if ( this.labelMesh === null ) {

			const labelMaterial = new MeshBasicMaterial( { map: this.progressiveLightMap1.texture, side: DoubleSide } );
			const labelGeometry = new PlaneGeometry( 100, 100 );
			this.labelMesh = new Mesh( labelGeometry, labelMaterial );
			this.labelMesh.position.y = 250;
			this.lightMapContainers[ 0 ].object.parent.add( this.labelMesh );

		}

		if ( position !== undefined ) {

			this.labelMesh.position.copy( position );

		}

		this.labelMesh.visible = visible;

	}
```
</details>

### `ProgressiveLightMap._initializeBlurPlane(res: number, lightMap: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Creates the Blurring Plane.
	 *
	 * @private
	 * @param {number} res - The square resolution of this object's lightMap.
	 * @param {WebGLRenderTarget} [lightMap] - The lightmap to initialize the plane with.
	 */
```

**Parameters:**

- **`res`** `number`
- **`lightMap`** `WebGLRenderTarget`

**Returns:** `void`

**Calls:**

- `shader.vertexShader.slice`
- `shader.fragmentShader.indexOf`
- `shader.fragmentShader.slice`
- `this.scene.add`

**Internal Comments:**
```
// Vertex Shader: Set Vertex Positions to the Unwrapped UV Positions (x4)
// Fragment Shader: Set Pixels to 9-tap box blur the current frame's Shadows (x2)
// Set the LightMap Accumulation Buffer (x5)
// Set the new Shader to this (x5)
```

<details><summary>Code</summary>

```typescript
_initializeBlurPlane( res, lightMap = null ) {

		const blurMaterial = new MeshBasicMaterial();
		blurMaterial.uniforms = { previousShadowMap: { value: null },
								  pixelOffset: { value: 1.0 / res },
								  polygonOffset: true, polygonOffsetFactor: - 1, polygonOffsetUnits: 3.0 };
		blurMaterial.onBeforeCompile = ( shader ) => {

			// Vertex Shader: Set Vertex Positions to the Unwrapped UV Positions
			shader.vertexShader =
				'#define USE_UV\n' +
				shader.vertexShader.slice( 0, - 1 ) +
				'	gl_Position = vec4((uv - 0.5) * 2.0, 1.0, 1.0); }';

			// Fragment Shader: Set Pixels to 9-tap box blur the current frame's Shadows
			const bodyStart	= shader.fragmentShader.indexOf( 'void main() {' );
			shader.fragmentShader =
				'#define USE_UV\n' +
				shader.fragmentShader.slice( 0, bodyStart ) +
				'	uniform sampler2D previousShadowMap;\n	uniform float pixelOffset;\n' +
				shader.fragmentShader.slice( bodyStart - 1, - 1 ) +
					`	gl_FragColor.rgb = (
									texture2D(previousShadowMap, vUv + vec2( pixelOffset,  0.0        )).rgb +
									texture2D(previousShadowMap, vUv + vec2( 0.0        ,  pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2( 0.0        , -pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2(-pixelOffset,  0.0        )).rgb +
									texture2D(previousShadowMap, vUv + vec2( pixelOffset,  pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2(-pixelOffset,  pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2( pixelOffset, -pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2(-pixelOffset, -pixelOffset)).rgb)/8.0;
				}`;

			// Set the LightMap Accumulation Buffer
			shader.uniforms.previousShadowMap = { value: lightMap.texture };
			shader.uniforms.pixelOffset = { value: 0.5 / res };
			blurMaterial.uniforms = shader.uniforms;

			// Set the new Shader to this
			blurMaterial.userData.shader = shader;

		};

		this.blurringPlane = new Mesh( new PlaneGeometry( 1, 1 ), blurMaterial );
		this.blurringPlane.name = 'Blurring Plane';
		this.blurringPlane.frustumCulled = false;
		this.blurringPlane.renderOrder = 0;
		this.blurringPlane.material.depthWrite = false;
		this.scene.add( this.blurringPlane );

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

- `this.progressiveLightMap1.dispose`
- `this.progressiveLightMap2.dispose`
- `this.uvMat.dispose`
- `this.blurringPlane.geometry.dispose`
- `this.blurringPlane.material.dispose`
- `this.labelMesh.geometry.dispose`
- `this.labelMesh.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.progressiveLightMap1.dispose();
		this.progressiveLightMap2.dispose();

		this.uvMat.dispose();

		if ( this.blurringPlane !== null ) {

			this.blurringPlane.geometry.dispose();
			this.blurringPlane.material.dispose();

		}

		if ( this.labelMesh !== null ) {

			this.labelMesh.geometry.dispose();
			this.labelMesh.material.dispose();

		}

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
	 * Constructs a new progressive light map.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
 	 * @param {number} [res=1024] - The side-long dimension of the total lightmap.
	 */
	constructor( renderer, res = 1024 ) {

		/**
		 * The renderer.
		 *
		 * @type {WebGLRenderer}
		 */
		this.renderer = renderer;

		/**
		 * The side-long dimension of the total lightmap.
		 *
		 * @type {number}
		 * @default 1024
		 */
		this.res = res;

		// internals

		this.lightMapContainers = [];
		this.scene = new Scene();
		this.buffer1Active = false;
		this.firstUpdate = true;
		this.labelMesh = null;
		this.blurringPlane = null;

		// Create the Progressive LightMap Texture
		const format = /(Android|iPad|iPhone|iPod)/g.test( navigator.userAgent ) ? HalfFloatType : FloatType;
		this.progressiveLightMap1 = new WebGLRenderTarget( this.res, this.res, { type: format } );
		this.progressiveLightMap2 = new WebGLRenderTarget( this.res, this.res, { type: format } );
		this.progressiveLightMap2.texture.channel = 1;

		// Inject some spicy new logic into a standard phong material
		this.uvMat = new MeshPhongMaterial();
		this.uvMat.uniforms = {};
		this.uvMat.onBeforeCompile = ( shader ) => {

			// Vertex Shader: Set Vertex Positions to the Unwrapped UV Positions
			shader.vertexShader =
				'attribute vec2 uv1;\n' +
				'#define USE_LIGHTMAP\n' +
				'#define LIGHTMAP_UV uv1\n' +
				shader.vertexShader.slice( 0, - 1 ) +
				'	gl_Position = vec4((LIGHTMAP_UV - 0.5) * 2.0, 1.0, 1.0); }';

			// Fragment Shader: Set Pixels to average in the Previous frame's Shadows
			const bodyStart = shader.fragmentShader.indexOf( 'void main() {' );
			shader.fragmentShader =
				'#define USE_LIGHTMAP\n' +
				shader.fragmentShader.slice( 0, bodyStart ) +
				'	uniform sampler2D previousShadowMap;\n	uniform float averagingWindow;\n' +
				shader.fragmentShader.slice( bodyStart - 1, - 1 ) +
				`\nvec3 texelOld = texture2D(previousShadowMap, vLightMapUv).rgb;
				gl_FragColor.rgb = mix(texelOld, gl_FragColor.rgb, 1.0/averagingWindow);
			}`;

			// Set the Previous Frame's Texture Buffer and Averaging Window
			shader.uniforms.previousShadowMap = { value: this.progressiveLightMap1.texture };
			shader.uniforms.averagingWindow = { value: 100 };

			this.uvMat.uniforms = shader.uniforms;

			// Set the new Shader to this
			this.uvMat.userData.shader = shader;

		};

	}

	/**
	 * Sets these objects' materials' lightmaps and modifies their uv1's.
	 *
	 * @param {Array<Object3D>} objects - An array of objects and lights to set up your lightmap.
	 */
	addObjectsToLightMap( objects ) {

		// Prepare list of UV bounding boxes for packing later...
		this.uv_boxes = []; const padding = 3 / this.res;

		for ( let ob = 0; ob < objects.length; ob ++ ) {

			const object = objects[ ob ];

			// If this object is a light, simply add it to the internal scene
			if ( object.isLight ) {

				this.scene.attach( object ); continue;

			}

			if ( object.geometry.hasAttribute( 'uv' ) === false ) {

				console.warn( 'THREE.ProgressiveLightMap: All lightmap objects need uvs.' ); continue;

			}

			if ( this.blurringPlane === null ) {

				this._initializeBlurPlane( this.res, this.progressiveLightMap1 );

			}

			// Apply the lightmap to the object
			object.material.lightMap = this.progressiveLightMap2.texture;
			object.material.dithering = true;
			object.castShadow = true;
			object.receiveShadow = true;
			object.renderOrder = 1000 + ob;

			// Prepare UV boxes for potpack
			// TODO: Size these by object surface area
			this.uv_boxes.push( { w: 1 + ( padding * 2 ),
								  h: 1 + ( padding * 2 ), index: ob } );

			this.lightMapContainers.push( { basicMat: object.material, object: object } );

		}

		// Pack the objects' lightmap UVs into the same global space
		const dimensions = potpack( this.uv_boxes );
		this.uv_boxes.forEach( ( box ) => {

			const uv1 = objects[ box.index ].geometry.getAttribute( 'uv' ).clone();
			for ( let i = 0; i < uv1.array.length; i += uv1.itemSize ) {

				uv1.array[ i ] = ( uv1.array[ i ] + box.x + padding ) / dimensions.w;
				uv1.array[ i + 1 ] = ( uv1.array[ i + 1 ] + box.y + padding ) / dimensions.h;

			}

			objects[ box.index ].geometry.setAttribute( 'uv1', uv1 );
			objects[ box.index ].geometry.getAttribute( 'uv1' ).needsUpdate = true;

		} );

	}

	/**
	 * This function renders each mesh one at a time into their respective surface maps.
	 *
	 * @param {Camera} camera - The camera the scene is rendered with.
	 * @param {number} [blendWindow=100] - When >1, samples will accumulate over time.
	 * @param {boolean} [blurEdges=true] - Whether to fix UV Edges via blurring.
	 */
	update( camera, blendWindow = 100, blurEdges = true ) {

		if ( this.blurringPlane === null ) {

			return;

		}

		// Store the original Render Target
		const oldTarget = this.renderer.getRenderTarget();

		// The blurring plane applies blur to the seams of the lightmap
		this.blurringPlane.visible = blurEdges;

		// Steal the Object3D from the real world to our special dimension
		for ( let l = 0; l < this.lightMapContainers.length; l ++ ) {

			this.lightMapContainers[ l ].object.oldScene =
				this.lightMapContainers[ l ].object.parent;
			this.scene.attach( this.lightMapContainers[ l ].object );

		}

		// Initialize everything
		if ( this.firstUpdate === true ) {

			this.renderer.compile( this.scene, camera );
			this.firstUpdate = false;

		}

		// Set each object's material to the UV Unwrapped Surface Mapping Version
		for ( let l = 0; l < this.lightMapContainers.length; l ++ ) {

			this.uvMat.uniforms.averagingWindow = { value: blendWindow };
			this.lightMapContainers[ l ].object.material = this.uvMat;
			this.lightMapContainers[ l ].object.oldFrustumCulled =
				this.lightMapContainers[ l ].object.frustumCulled;
			this.lightMapContainers[ l ].object.frustumCulled = false;

		}

		// Ping-pong two surface buffers for reading/writing
		const activeMap = this.buffer1Active ? this.progressiveLightMap1 : this.progressiveLightMap2;
		const inactiveMap = this.buffer1Active ? this.progressiveLightMap2 : this.progressiveLightMap1;

		// Render the object's surface maps
		this.renderer.setRenderTarget( activeMap );
		this.uvMat.uniforms.previousShadowMap = { value: inactiveMap.texture };
		this.blurringPlane.material.uniforms.previousShadowMap = { value: inactiveMap.texture };
		this.buffer1Active = ! this.buffer1Active;
		this.renderer.render( this.scene, camera );

		// Restore the object's Real-time Material and add it back to the original world
		for ( let l = 0; l < this.lightMapContainers.length; l ++ ) {

			this.lightMapContainers[ l ].object.frustumCulled =
				this.lightMapContainers[ l ].object.oldFrustumCulled;
			this.lightMapContainers[ l ].object.material = this.lightMapContainers[ l ].basicMat;
			this.lightMapContainers[ l ].object.oldScene.attach( this.lightMapContainers[ l ].object );

		}

		// Restore the original Render Target
		this.renderer.setRenderTarget( oldTarget );

	}

	/**
	 * Draws the lightmap in the main scene. Call this after adding the objects to it.
	 *
	 * @param {boolean} visible - Whether the debug plane should be visible
	 * @param {Vector3} [position] - Where the debug plane should be drawn
	*/
	showDebugLightmap( visible, position = undefined ) {

		if ( this.lightMapContainers.length === 0 ) {

			console.warn( 'THREE.ProgressiveLightMap: Call .showDebugLightmap() after adding the objects.' );

			return;

		}

		if ( this.labelMesh === null ) {

			const labelMaterial = new MeshBasicMaterial( { map: this.progressiveLightMap1.texture, side: DoubleSide } );
			const labelGeometry = new PlaneGeometry( 100, 100 );
			this.labelMesh = new Mesh( labelGeometry, labelMaterial );
			this.labelMesh.position.y = 250;
			this.lightMapContainers[ 0 ].object.parent.add( this.labelMesh );

		}

		if ( position !== undefined ) {

			this.labelMesh.position.copy( position );

		}

		this.labelMesh.visible = visible;

	}

	/**
	 * Creates the Blurring Plane.
	 *
	 * @private
	 * @param {number} res - The square resolution of this object's lightMap.
	 * @param {WebGLRenderTarget} [lightMap] - The lightmap to initialize the plane with.
	 */
	_initializeBlurPlane( res, lightMap = null ) {

		const blurMaterial = new MeshBasicMaterial();
		blurMaterial.uniforms = { previousShadowMap: { value: null },
								  pixelOffset: { value: 1.0 / res },
								  polygonOffset: true, polygonOffsetFactor: - 1, polygonOffsetUnits: 3.0 };
		blurMaterial.onBeforeCompile = ( shader ) => {

			// Vertex Shader: Set Vertex Positions to the Unwrapped UV Positions
			shader.vertexShader =
				'#define USE_UV\n' +
				shader.vertexShader.slice( 0, - 1 ) +
				'	gl_Position = vec4((uv - 0.5) * 2.0, 1.0, 1.0); }';

			// Fragment Shader: Set Pixels to 9-tap box blur the current frame's Shadows
			const bodyStart	= shader.fragmentShader.indexOf( 'void main() {' );
			shader.fragmentShader =
				'#define USE_UV\n' +
				shader.fragmentShader.slice( 0, bodyStart ) +
				'	uniform sampler2D previousShadowMap;\n	uniform float pixelOffset;\n' +
				shader.fragmentShader.slice( bodyStart - 1, - 1 ) +
					`	gl_FragColor.rgb = (
									texture2D(previousShadowMap, vUv + vec2( pixelOffset,  0.0        )).rgb +
									texture2D(previousShadowMap, vUv + vec2( 0.0        ,  pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2( 0.0        , -pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2(-pixelOffset,  0.0        )).rgb +
									texture2D(previousShadowMap, vUv + vec2( pixelOffset,  pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2(-pixelOffset,  pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2( pixelOffset, -pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2(-pixelOffset, -pixelOffset)).rgb)/8.0;
				}`;

			// Set the LightMap Accumulation Buffer
			shader.uniforms.previousShadowMap = { value: lightMap.texture };
			shader.uniforms.pixelOffset = { value: 0.5 / res };
			blurMaterial.uniforms = shader.uniforms;

			// Set the new Shader to this
			blurMaterial.userData.shader = shader;

		};

		this.blurringPlane = new Mesh( new PlaneGeometry( 1, 1 ), blurMaterial );
		this.blurringPlane.name = 'Blurring Plane';
		this.blurringPlane.frustumCulled = false;
		this.blurringPlane.renderOrder = 0;
		this.blurringPlane.material.depthWrite = false;
		this.scene.add( this.blurringPlane );

	}

	/**
	 * Frees all internal resources.
	 */
	dispose() {

		this.progressiveLightMap1.dispose();
		this.progressiveLightMap2.dispose();

		this.uvMat.dispose();

		if ( this.blurringPlane !== null ) {

			this.blurringPlane.geometry.dispose();
			this.blurringPlane.material.dispose();

		}

		if ( this.labelMesh !== null ) {

			this.labelMesh.geometry.dispose();
			this.labelMesh.material.dispose();

		}

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
		this.uv_boxes = []; const padding = 3 / this.res;

		for ( let ob = 0; ob < objects.length; ob ++ ) {

			const object = objects[ ob ];

			// If this object is a light, simply add it to the internal scene
			if ( object.isLight ) {

				this.scene.attach( object ); continue;

			}

			if ( object.geometry.hasAttribute( 'uv' ) === false ) {

				console.warn( 'THREE.ProgressiveLightMap: All lightmap objects need uvs.' ); continue;

			}

			if ( this.blurringPlane === null ) {

				this._initializeBlurPlane( this.res, this.progressiveLightMap1 );

			}

			// Apply the lightmap to the object
			object.material.lightMap = this.progressiveLightMap2.texture;
			object.material.dithering = true;
			object.castShadow = true;
			object.receiveShadow = true;
			object.renderOrder = 1000 + ob;

			// Prepare UV boxes for potpack
			// TODO: Size these by object surface area
			this.uv_boxes.push( { w: 1 + ( padding * 2 ),
								  h: 1 + ( padding * 2 ), index: ob } );

			this.lightMapContainers.push( { basicMat: object.material, object: object } );

		}

		// Pack the objects' lightmap UVs into the same global space
		const dimensions = potpack( this.uv_boxes );
		this.uv_boxes.forEach( ( box ) => {

			const uv1 = objects[ box.index ].geometry.getAttribute( 'uv' ).clone();
			for ( let i = 0; i < uv1.array.length; i += uv1.itemSize ) {

				uv1.array[ i ] = ( uv1.array[ i ] + box.x + padding ) / dimensions.w;
				uv1.array[ i + 1 ] = ( uv1.array[ i + 1 ] + box.y + padding ) / dimensions.h;

			}

			objects[ box.index ].geometry.setAttribute( 'uv1', uv1 );
			objects[ box.index ].geometry.getAttribute( 'uv1' ).needsUpdate = true;

		} );

	}
```
</details>

##### `update(camera: Camera, blendWindow: number, blurEdges: boolean): void`

<details><summary>Code</summary>

```ts
update( camera, blendWindow = 100, blurEdges = true ) {

		if ( this.blurringPlane === null ) {

			return;

		}

		// Store the original Render Target
		const oldTarget = this.renderer.getRenderTarget();

		// The blurring plane applies blur to the seams of the lightmap
		this.blurringPlane.visible = blurEdges;

		// Steal the Object3D from the real world to our special dimension
		for ( let l = 0; l < this.lightMapContainers.length; l ++ ) {

			this.lightMapContainers[ l ].object.oldScene =
				this.lightMapContainers[ l ].object.parent;
			this.scene.attach( this.lightMapContainers[ l ].object );

		}

		// Initialize everything
		if ( this.firstUpdate === true ) {

			this.renderer.compile( this.scene, camera );
			this.firstUpdate = false;

		}

		// Set each object's material to the UV Unwrapped Surface Mapping Version
		for ( let l = 0; l < this.lightMapContainers.length; l ++ ) {

			this.uvMat.uniforms.averagingWindow = { value: blendWindow };
			this.lightMapContainers[ l ].object.material = this.uvMat;
			this.lightMapContainers[ l ].object.oldFrustumCulled =
				this.lightMapContainers[ l ].object.frustumCulled;
			this.lightMapContainers[ l ].object.frustumCulled = false;

		}

		// Ping-pong two surface buffers for reading/writing
		const activeMap = this.buffer1Active ? this.progressiveLightMap1 : this.progressiveLightMap2;
		const inactiveMap = this.buffer1Active ? this.progressiveLightMap2 : this.progressiveLightMap1;

		// Render the object's surface maps
		this.renderer.setRenderTarget( activeMap );
		this.uvMat.uniforms.previousShadowMap = { value: inactiveMap.texture };
		this.blurringPlane.material.uniforms.previousShadowMap = { value: inactiveMap.texture };
		this.buffer1Active = ! this.buffer1Active;
		this.renderer.render( this.scene, camera );

		// Restore the object's Real-time Material and add it back to the original world
		for ( let l = 0; l < this.lightMapContainers.length; l ++ ) {

			this.lightMapContainers[ l ].object.frustumCulled =
				this.lightMapContainers[ l ].object.oldFrustumCulled;
			this.lightMapContainers[ l ].object.material = this.lightMapContainers[ l ].basicMat;
			this.lightMapContainers[ l ].object.oldScene.attach( this.lightMapContainers[ l ].object );

		}

		// Restore the original Render Target
		this.renderer.setRenderTarget( oldTarget );

	}
```
</details>

##### `showDebugLightmap(visible: boolean, position: Vector3): void`

<details><summary>Code</summary>

```ts
showDebugLightmap( visible, position = undefined ) {

		if ( this.lightMapContainers.length === 0 ) {

			console.warn( 'THREE.ProgressiveLightMap: Call .showDebugLightmap() after adding the objects.' );

			return;

		}

		if ( this.labelMesh === null ) {

			const labelMaterial = new MeshBasicMaterial( { map: this.progressiveLightMap1.texture, side: DoubleSide } );
			const labelGeometry = new PlaneGeometry( 100, 100 );
			this.labelMesh = new Mesh( labelGeometry, labelMaterial );
			this.labelMesh.position.y = 250;
			this.lightMapContainers[ 0 ].object.parent.add( this.labelMesh );

		}

		if ( position !== undefined ) {

			this.labelMesh.position.copy( position );

		}

		this.labelMesh.visible = visible;

	}
```
</details>

##### `_initializeBlurPlane(res: number, lightMap: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
_initializeBlurPlane( res, lightMap = null ) {

		const blurMaterial = new MeshBasicMaterial();
		blurMaterial.uniforms = { previousShadowMap: { value: null },
								  pixelOffset: { value: 1.0 / res },
								  polygonOffset: true, polygonOffsetFactor: - 1, polygonOffsetUnits: 3.0 };
		blurMaterial.onBeforeCompile = ( shader ) => {

			// Vertex Shader: Set Vertex Positions to the Unwrapped UV Positions
			shader.vertexShader =
				'#define USE_UV\n' +
				shader.vertexShader.slice( 0, - 1 ) +
				'	gl_Position = vec4((uv - 0.5) * 2.0, 1.0, 1.0); }';

			// Fragment Shader: Set Pixels to 9-tap box blur the current frame's Shadows
			const bodyStart	= shader.fragmentShader.indexOf( 'void main() {' );
			shader.fragmentShader =
				'#define USE_UV\n' +
				shader.fragmentShader.slice( 0, bodyStart ) +
				'	uniform sampler2D previousShadowMap;\n	uniform float pixelOffset;\n' +
				shader.fragmentShader.slice( bodyStart - 1, - 1 ) +
					`	gl_FragColor.rgb = (
									texture2D(previousShadowMap, vUv + vec2( pixelOffset,  0.0        )).rgb +
									texture2D(previousShadowMap, vUv + vec2( 0.0        ,  pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2( 0.0        , -pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2(-pixelOffset,  0.0        )).rgb +
									texture2D(previousShadowMap, vUv + vec2( pixelOffset,  pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2(-pixelOffset,  pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2( pixelOffset, -pixelOffset)).rgb +
									texture2D(previousShadowMap, vUv + vec2(-pixelOffset, -pixelOffset)).rgb)/8.0;
				}`;

			// Set the LightMap Accumulation Buffer
			shader.uniforms.previousShadowMap = { value: lightMap.texture };
			shader.uniforms.pixelOffset = { value: 0.5 / res };
			blurMaterial.uniforms = shader.uniforms;

			// Set the new Shader to this
			blurMaterial.userData.shader = shader;

		};

		this.blurringPlane = new Mesh( new PlaneGeometry( 1, 1 ), blurMaterial );
		this.blurringPlane.name = 'Blurring Plane';
		this.blurringPlane.frustumCulled = false;
		this.blurringPlane.renderOrder = 0;
		this.blurringPlane.material.depthWrite = false;
		this.scene.add( this.blurringPlane );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.progressiveLightMap1.dispose();
		this.progressiveLightMap2.dispose();

		this.uvMat.dispose();

		if ( this.blurringPlane !== null ) {

			this.blurringPlane.geometry.dispose();
			this.blurringPlane.material.dispose();

		}

		if ( this.labelMesh !== null ) {

			this.labelMesh.geometry.dispose();
			this.labelMesh.material.dispose();

		}

	}
```
</details>


---