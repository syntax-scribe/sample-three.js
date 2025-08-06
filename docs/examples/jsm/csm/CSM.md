[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CSM.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 39 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/csm/CSM.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `three` |
| `Vector3` | `three` |
| `DirectionalLight` | `three` |
| `MathUtils` | `three` |
| `ShaderChunk` | `three` |
| `Matrix4` | `three` |
| `Box3` | `three` |
| `CSMFrustum` | `./CSMFrustum.js` |
| `CSMShader` | `./CSMShader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_cameraToLightMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_lightSpaceFrustum` | `CSMFrustum` | let/var | `new CSMFrustum( { webGL: true } )` | ✗ |
| `_center` | `any` | let/var | `new Vector3()` | ✗ |
| `_bbox` | `any` | let/var | `new Box3()` | ✗ |
| `_uniformArray` | `any[]` | let/var | `[]` | ✗ |
| `_logArray` | `any[]` | let/var | `[]` | ✗ |
| `_lightOrientationMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_lightOrientationMatrixInverse` | `any` | let/var | `new Matrix4()` | ✗ |
| `_up` | `any` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `light` | `any` | let/var | `new DirectionalLight( 0xffffff, this.lightIntensity )` | ✗ |
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `frustums` | `CSMFrustum[]` | let/var | `this.frustums` | ✗ |
| `light` | `DirectionalLight` | let/var | `this.lights[ i ]` | ✗ |
| `shadowCam` | `any` | let/var | `light.shadow.camera` | ✗ |
| `frustum` | `CSMFrustum` | let/var | `this.frustums[ i ]` | ✗ |
| `nearVerts` | `any` | let/var | `frustum.vertices.near` | ✗ |
| `farVerts` | `any` | let/var | `frustum.vertices.far` | ✗ |
| `point1` | `any` | let/var | `farVerts[ 0 ]` | ✗ |
| `point2` | `any` | let/var | `*not shown*` | ✗ |
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `linearDepth` | `number` | let/var | `frustum.vertices.far[ 0 ].z / ( far - camera.near )` | ✗ |
| `margin` | `number` | let/var | `0.25 * Math.pow( linearDepth, 2.0 ) * ( far - camera.near )` | ✗ |
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `frustums` | `CSMFrustum[]` | let/var | `this.frustums` | ✗ |
| `light` | `DirectionalLight` | let/var | `this.lights[ i ]` | ✗ |
| `shadowCam` | `any` | let/var | `light.shadow.camera` | ✗ |
| `texelWidth` | `number` | let/var | `( shadowCam.right - shadowCam.left ) / this.shadowMapSize` | ✗ |
| `texelHeight` | `number` | let/var | `( shadowCam.top - shadowCam.bottom ) / this.shadowMapSize` | ✗ |
| `nearVerts` | `any` | let/var | `_lightSpaceFrustum.vertices.near` | ✗ |
| `farVerts` | `any` | let/var | `_lightSpaceFrustum.vertices.far` | ✗ |
| `breaksVec2` | `any[]` | let/var | `[]` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `shaders` | `Map<Material, any>` | let/var | `this.shaders` | ✗ |
| `shaders` | `Map<Material, any>` | let/var | `this.shaders` | ✗ |
| `uniforms` | `any` | let/var | `shader.uniforms` | ✗ |
| `amount` | `number` | let/var | `this.breaks[ i ]` | ✗ |
| `prev` | `number` | let/var | `this.breaks[ i - 1 ] \|\| 0` | ✗ |
| `shaders` | `Map<Material, any>` | let/var | `this.shaders` | ✗ |


---

## Functions

### `CSM._createLights(): void`

**JSDoc:**
```typescript
/**
	 * Creates the directional lights of this CSM instance.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `this.parent.add`
- `this.lights.push`

<details><summary>Code</summary>

```typescript
_createLights() {

		for ( let i = 0; i < this.cascades; i ++ ) {

			const light = new DirectionalLight( 0xffffff, this.lightIntensity );
			light.castShadow = true;
			light.shadow.mapSize.width = this.shadowMapSize;
			light.shadow.mapSize.height = this.shadowMapSize;

			light.shadow.camera.near = this.lightNear;
			light.shadow.camera.far = this.lightFar;
			light.shadow.bias = this.shadowBias;

			this.parent.add( light );
			this.parent.add( light.target );
			this.lights.push( light );

		}

	}
```
</details>

### `CSM._initCascades(): void`

**JSDoc:**
```typescript
/**
	 * Inits the cascades according to the scene's camera and breaks configuration.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `camera.updateProjectionMatrix`
- `this.mainFrustum.setFromProjectionMatrix`
- `this.mainFrustum.split`

<details><summary>Code</summary>

```typescript
_initCascades() {

		const camera = this.camera;
		camera.updateProjectionMatrix();
		this.mainFrustum.setFromProjectionMatrix( camera.projectionMatrix, this.maxFar );
		this.mainFrustum.split( this.breaks, this.frustums );

	}
```
</details>

### `CSM._updateShadowBounds(): void`

**JSDoc:**
```typescript
/**
	 * Updates the shadow bounds of this CSM instance.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `point1.distanceTo`
- `Math.max`
- `Math.pow`
- `shadowCam.updateProjectionMatrix`

**Internal Comments:**
```
// Get the two points that represent that furthest points on the frustum assuming (x2)
// that's either the diagonal across the far plane or the diagonal across the whole (x2)
// frustum itself. (x2)
// expand the shadow extents by the fade margin if fade is enabled. (x2)
```

<details><summary>Code</summary>

```typescript
_updateShadowBounds() {

		const frustums = this.frustums;
		for ( let i = 0; i < frustums.length; i ++ ) {

			const light = this.lights[ i ];
			const shadowCam = light.shadow.camera;
			const frustum = this.frustums[ i ];

			// Get the two points that represent that furthest points on the frustum assuming
			// that's either the diagonal across the far plane or the diagonal across the whole
			// frustum itself.
			const nearVerts = frustum.vertices.near;
			const farVerts = frustum.vertices.far;
			const point1 = farVerts[ 0 ];
			let point2;
			if ( point1.distanceTo( farVerts[ 2 ] ) > point1.distanceTo( nearVerts[ 2 ] ) ) {

				point2 = farVerts[ 2 ];

			} else {

				point2 = nearVerts[ 2 ];

			}

			let squaredBBWidth = point1.distanceTo( point2 );
			if ( this.fade ) {

				// expand the shadow extents by the fade margin if fade is enabled.
				const camera = this.camera;
				const far = Math.max( camera.far, this.maxFar );
				const linearDepth = frustum.vertices.far[ 0 ].z / ( far - camera.near );
				const margin = 0.25 * Math.pow( linearDepth, 2.0 ) * ( far - camera.near );

				squaredBBWidth += margin;

			}

			shadowCam.left = - squaredBBWidth / 2;
			shadowCam.right = squaredBBWidth / 2;
			shadowCam.top = squaredBBWidth / 2;
			shadowCam.bottom = - squaredBBWidth / 2;
			shadowCam.updateProjectionMatrix();

		}

	}
```
</details>

### `CSM._getBreaks(): void`

**JSDoc:**
```typescript
/**
	 * Computes the breaks of this CSM instance based on the scene's camera, number of cascades
	 * and the selected split mode.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `Math.min`
- `uniformSplit`
- `logarithmicSplit`
- `practicalSplit`
- `console.error`
- `this.customSplitsCallback`
- `target.push`
- `MathUtils.lerp`

<details><summary>Code</summary>

```typescript
_getBreaks() {

		const camera = this.camera;
		const far = Math.min( camera.far, this.maxFar );
		this.breaks.length = 0;

		switch ( this.mode ) {

			case 'uniform':
				uniformSplit( this.cascades, camera.near, far, this.breaks );
				break;
			case 'logarithmic':
				logarithmicSplit( this.cascades, camera.near, far, this.breaks );
				break;
			case 'practical':
				practicalSplit( this.cascades, camera.near, far, 0.5, this.breaks );
				break;
			case 'custom':
				if ( this.customSplitsCallback === undefined ) console.error( 'CSM: Custom split scheme callback not defined.' );
				this.customSplitsCallback( this.cascades, camera.near, far, this.breaks );
				break;

		}

		function uniformSplit( amount, near, far, target ) {

			for ( let i = 1; i < amount; i ++ ) {

				target.push( ( near + ( far - near ) * i / amount ) / far );

			}

			target.push( 1 );

		}

		function logarithmicSplit( amount, near, far, target ) {

			for ( let i = 1; i < amount; i ++ ) {

				target.push( ( near * ( far / near ) ** ( i / amount ) ) / far );

			}

			target.push( 1 );

		}

		function practicalSplit( amount, near, far, lambda, target ) {

			_uniformArray.length = 0;
			_logArray.length = 0;
			logarithmicSplit( amount, near, far, _logArray );
			uniformSplit( amount, near, far, _uniformArray );

			for ( let i = 1; i < amount; i ++ ) {

				target.push( MathUtils.lerp( _uniformArray[ i - 1 ], _logArray[ i - 1 ], lambda ) );

			}

			target.push( 1 );

		}

	}
```
</details>

### `CSM.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the CSM. This method must be called in your animation loop before
	 * calling `renderer.render()`.
	 */
```

**Returns:** `void`

**Calls:**

- `_lightOrientationMatrix.lookAt`
- `_lightOrientationMatrixInverse.copy( _lightOrientationMatrix ).invert`
- `_cameraToLightMatrix.multiplyMatrices`
- `frustums[ i ].toSpace`
- `_bbox.makeEmpty`
- `_bbox.expandByPoint`
- `_bbox.getCenter`
- `Math.floor`
- `_center.applyMatrix4`
- `light.position.copy`
- `light.target.position.copy`

**Internal Comments:**
```
// for each frustum we need to find its min-max box aligned with the light orientation (x4)
// the position in _lightOrientationMatrix does not matter, as we transform there and back (x4)
```

<details><summary>Code</summary>

```typescript
update() {

		const camera = this.camera;
		const frustums = this.frustums;

		// for each frustum we need to find its min-max box aligned with the light orientation
		// the position in _lightOrientationMatrix does not matter, as we transform there and back
		_lightOrientationMatrix.lookAt( new Vector3(), this.lightDirection, _up );
		_lightOrientationMatrixInverse.copy( _lightOrientationMatrix ).invert();

		for ( let i = 0; i < frustums.length; i ++ ) {

			const light = this.lights[ i ];
			const shadowCam = light.shadow.camera;
			const texelWidth = ( shadowCam.right - shadowCam.left ) / this.shadowMapSize;
			const texelHeight = ( shadowCam.top - shadowCam.bottom ) / this.shadowMapSize;
			_cameraToLightMatrix.multiplyMatrices( _lightOrientationMatrixInverse, camera.matrixWorld );
			frustums[ i ].toSpace( _cameraToLightMatrix, _lightSpaceFrustum );

			const nearVerts = _lightSpaceFrustum.vertices.near;
			const farVerts = _lightSpaceFrustum.vertices.far;
			_bbox.makeEmpty();
			for ( let j = 0; j < 4; j ++ ) {

				_bbox.expandByPoint( nearVerts[ j ] );
				_bbox.expandByPoint( farVerts[ j ] );

			}

			_bbox.getCenter( _center );
			_center.z = _bbox.max.z + this.lightMargin;
			_center.x = Math.floor( _center.x / texelWidth ) * texelWidth;
			_center.y = Math.floor( _center.y / texelHeight ) * texelHeight;
			_center.applyMatrix4( _lightOrientationMatrix );

			light.position.copy( _center );
			light.target.position.copy( _center );

			light.target.position.x += this.lightDirection.x;
			light.target.position.y += this.lightDirection.y;
			light.target.position.z += this.lightDirection.z;

		}

	}
```
</details>

### `CSM._injectInclude(): void`

**JSDoc:**
```typescript
/**
	 * Injects the CSM shader enhancements into the built-in materials.
	 *
	 * @private
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_injectInclude() {

		ShaderChunk.lights_fragment_begin = CSMShader.lights_fragment_begin;
		ShaderChunk.lights_pars_begin = CSMShader.lights_pars_begin;

	}
```
</details>

### `CSM.setupMaterial(material: Material): void`

**JSDoc:**
```typescript
/**
	 * Applications must call this method for all materials that should be affected by CSM.
	 *
	 * @param {Material} material - The material to setup for CSM support.
	 */
```

**Parameters:**

- **`material`** `Material`

**Returns:** `void`

**Calls:**

- `Math.min`
- `scope._getExtendedBreaks`
- `shaders.set`

<details><summary>Code</summary>

```typescript
setupMaterial( material ) {

		material.defines = material.defines || {};
		material.defines.USE_CSM = 1;
		material.defines.CSM_CASCADES = this.cascades;

		if ( this.fade ) {

			material.defines.CSM_FADE = '';

		}

		const breaksVec2 = [];
		const scope = this;
		const shaders = this.shaders;

		material.onBeforeCompile = function ( shader ) {

			const far = Math.min( scope.camera.far, scope.maxFar );
			scope._getExtendedBreaks( breaksVec2 );

			shader.uniforms.CSM_cascades = { value: breaksVec2 };
			shader.uniforms.cameraNear = { value: scope.camera.near };
			shader.uniforms.shadowFar = { value: far };

			shaders.set( material, shader );

		};

		shaders.set( material, null );

	}
```
</details>

### `CSM._updateUniforms(): void`

**JSDoc:**
```typescript
/**
	 * Updates the CSM uniforms.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `Math.min`
- `shaders.forEach`
- `this._getExtendedBreaks`

<details><summary>Code</summary>

```typescript
_updateUniforms() {

		const far = Math.min( this.camera.far, this.maxFar );
		const shaders = this.shaders;

		shaders.forEach( function ( shader, material ) {

			if ( shader !== null ) {

				const uniforms = shader.uniforms;
				this._getExtendedBreaks( uniforms.CSM_cascades.value );
				uniforms.cameraNear.value = this.camera.near;
				uniforms.shadowFar.value = far;

			}

			if ( ! this.fade && 'CSM_FADE' in material.defines ) {

				delete material.defines.CSM_FADE;
				material.needsUpdate = true;

			} else if ( this.fade && ! ( 'CSM_FADE' in material.defines ) ) {

				material.defines.CSM_FADE = '';
				material.needsUpdate = true;

			}

		}, this );

	}
```
</details>

### `CSM._getExtendedBreaks(target: Vector2[]): void`

**JSDoc:**
```typescript
/**
	 * Computes the extended breaks for the CSM uniforms.
	 *
	 * @private
	 * @param {Array<Vector2>} target - The target array that holds the extended breaks.
	 */
```

**Parameters:**

- **`target`** `Vector2[]`

**Returns:** `void`

**Calls:**

- `target.push`

<details><summary>Code</summary>

```typescript
_getExtendedBreaks( target ) {

		while ( target.length < this.breaks.length ) {

			target.push( new Vector2() );

		}

		target.length = this.breaks.length;

		for ( let i = 0; i < this.cascades; i ++ ) {

			const amount = this.breaks[ i ];
			const prev = this.breaks[ i - 1 ] || 0;
			target[ i ].x = prev;
			target[ i ].y = amount;

		}

	}
```
</details>

### `CSM.updateFrustums(): void`

**JSDoc:**
```typescript
/**
	 * Applications must call this method every time they change camera or CSM settings.
	 */
```

**Returns:** `void`

**Calls:**

- `this._getBreaks`
- `this._initCascades`
- `this._updateShadowBounds`
- `this._updateUniforms`

<details><summary>Code</summary>

```typescript
updateFrustums() {

		this._getBreaks();
		this._initCascades();
		this._updateShadowBounds();
		this._updateUniforms();

	}
```
</details>

### `CSM.remove(): void`

**JSDoc:**
```typescript
/**
	 * Applications must call this method when they remove the CSM usage from their scene.
	 */
```

**Returns:** `void`

**Calls:**

- `this.parent.remove`

<details><summary>Code</summary>

```typescript
remove() {

		for ( let i = 0; i < this.lights.length; i ++ ) {

			this.parent.remove( this.lights[ i ].target );
			this.parent.remove( this.lights[ i ] );

		}

	}
```
</details>

### `CSM.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `shaders.forEach`
- `shaders.clear`

<details><summary>Code</summary>

```typescript
dispose() {

		const shaders = this.shaders;
		shaders.forEach( function ( shader, material ) {

			delete material.onBeforeCompile;
			delete material.defines.USE_CSM;
			delete material.defines.CSM_CASCADES;
			delete material.defines.CSM_FADE;

			if ( shader !== null ) {

				delete shader.uniforms.CSM_cascades;
				delete shader.uniforms.cameraNear;
				delete shader.uniforms.shadowFar;

			}

			material.needsUpdate = true;

		} );
		shaders.clear();

	}
```
</details>

### `uniformSplit(amount: any, near: any, far: any, target: any): void`

**Parameters:**

- **`amount`** `any`
- **`near`** `any`
- **`far`** `any`
- **`target`** `any`

**Returns:** `void`

**Calls:**

- `target.push`

<details><summary>Code</summary>

```typescript
function uniformSplit( amount, near, far, target ) {

			for ( let i = 1; i < amount; i ++ ) {

				target.push( ( near + ( far - near ) * i / amount ) / far );

			}

			target.push( 1 );

		}
```
</details>

### `logarithmicSplit(amount: any, near: any, far: any, target: any): void`

**Parameters:**

- **`amount`** `any`
- **`near`** `any`
- **`far`** `any`
- **`target`** `any`

**Returns:** `void`

**Calls:**

- `target.push`

<details><summary>Code</summary>

```typescript
function logarithmicSplit( amount, near, far, target ) {

			for ( let i = 1; i < amount; i ++ ) {

				target.push( ( near * ( far / near ) ** ( i / amount ) ) / far );

			}

			target.push( 1 );

		}
```
</details>

### `practicalSplit(amount: any, near: any, far: any, lambda: any, target: any): void`

**Parameters:**

- **`amount`** `any`
- **`near`** `any`
- **`far`** `any`
- **`lambda`** `any`
- **`target`** `any`

**Returns:** `void`

**Calls:**

- `logarithmicSplit`
- `uniformSplit`
- `target.push`
- `MathUtils.lerp`

<details><summary>Code</summary>

```typescript
function practicalSplit( amount, near, far, lambda, target ) {

			_uniformArray.length = 0;
			_logArray.length = 0;
			logarithmicSplit( amount, near, far, _logArray );
			uniformSplit( amount, near, far, _uniformArray );

			for ( let i = 1; i < amount; i ++ ) {

				target.push( MathUtils.lerp( _uniformArray[ i - 1 ], _logArray[ i - 1 ], lambda ) );

			}

			target.push( 1 );

		}
```
</details>


---

## Classes

### `CSM`

<details><summary>Class Code</summary>

```ts
export class CSM {

	/**
	 * Constructs a new CSM instance.
	 *
	 * @param {CSM~Data} data - The CSM data.
	 */
	constructor( data ) {

		/**
		 * The scene's camera.
		 *
		 * @type {Camera}
		 */
		this.camera = data.camera;

		/**
		 * The parent object, usually the scene.
		 *
		 * @type {Object3D}
		 */
		this.parent = data.parent;

		/**
		 * The number of cascades.
		 *
		 * @type {number}
		 * @default 3
		 */
		this.cascades = data.cascades || 3;

		/**
		 * The maximum far value.
		 *
		 * @type {number}
		 * @default 100000
		 */
		this.maxFar = data.maxFar || 100000;

		/**
		 * The frustum split mode.
		 *
		 * @type {('practical'|'uniform'|'logarithmic'|'custom')}
		 * @default 'practical'
		 */
		this.mode = data.mode || 'practical';

		/**
		 * The shadow map size.
		 *
		 * @type {number}
		 * @default 2048
		 */
		this.shadowMapSize = data.shadowMapSize || 2048;

		/**
		 * The shadow bias.
		 *
		 * @type {number}
		 * @default 0.000001
		 */
		this.shadowBias = data.shadowBias || 0.000001;

		/**
		 * The light direction.
		 *
		 * @type {Vector3}
		 */
		this.lightDirection = data.lightDirection || new Vector3( 1, - 1, 1 ).normalize();

		/**
		 * The light intensity.
		 *
		 * @type {number}
		 * @default 3
		 */
		this.lightIntensity = data.lightIntensity || 3;

		/**
		 * The light near value.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.lightNear = data.lightNear || 1;

		/**
		 * The light far value.
		 *
		 * @type {number}
		 * @default 2000
		 */
		this.lightFar = data.lightFar || 2000;

		/**
		 * The light margin.
		 *
		 * @type {number}
		 * @default 200
		 */
		this.lightMargin = data.lightMargin || 200;

		/**
		 * Custom split callback when using `mode='custom'`.
		 *
		 * @type {Function}
		 */
		this.customSplitsCallback = data.customSplitsCallback;

		/**
		 * Whether to fade between cascades or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.fade = false;

		/**
		 * The main frustum.
		 *
		 * @type {CSMFrustum}
		 */
		this.mainFrustum = new CSMFrustum( { webGL: true } );

		/**
		 * An array of frustums representing the cascades.
		 *
		 * @type {Array<CSMFrustum>}
		 */
		this.frustums = [];

		/**
		 * An array of numbers in the range `[0,1]` the defines how the
		 * mainCSM frustum should be split up.
		 *
		 * @type {Array<number>}
		 */
		this.breaks = [];

		/**
		 * An array of directional lights which cast the shadows for
		 * the different cascades. There is one directional light for each
		 * cascade.
		 *
		 * @type {Array<DirectionalLight>}
		 */
		this.lights = [];

		/**
		 * A Map holding enhanced material shaders.
		 *
		 * @type {Map<Material,Object>}
		 */
		this.shaders = new Map();

		this._createLights();
		this.updateFrustums();
		this._injectInclude();

	}

	/**
	 * Creates the directional lights of this CSM instance.
	 *
	 * @private
	 */
	_createLights() {

		for ( let i = 0; i < this.cascades; i ++ ) {

			const light = new DirectionalLight( 0xffffff, this.lightIntensity );
			light.castShadow = true;
			light.shadow.mapSize.width = this.shadowMapSize;
			light.shadow.mapSize.height = this.shadowMapSize;

			light.shadow.camera.near = this.lightNear;
			light.shadow.camera.far = this.lightFar;
			light.shadow.bias = this.shadowBias;

			this.parent.add( light );
			this.parent.add( light.target );
			this.lights.push( light );

		}

	}

	/**
	 * Inits the cascades according to the scene's camera and breaks configuration.
	 *
	 * @private
	 */
	_initCascades() {

		const camera = this.camera;
		camera.updateProjectionMatrix();
		this.mainFrustum.setFromProjectionMatrix( camera.projectionMatrix, this.maxFar );
		this.mainFrustum.split( this.breaks, this.frustums );

	}

	/**
	 * Updates the shadow bounds of this CSM instance.
	 *
	 * @private
	 */
	_updateShadowBounds() {

		const frustums = this.frustums;
		for ( let i = 0; i < frustums.length; i ++ ) {

			const light = this.lights[ i ];
			const shadowCam = light.shadow.camera;
			const frustum = this.frustums[ i ];

			// Get the two points that represent that furthest points on the frustum assuming
			// that's either the diagonal across the far plane or the diagonal across the whole
			// frustum itself.
			const nearVerts = frustum.vertices.near;
			const farVerts = frustum.vertices.far;
			const point1 = farVerts[ 0 ];
			let point2;
			if ( point1.distanceTo( farVerts[ 2 ] ) > point1.distanceTo( nearVerts[ 2 ] ) ) {

				point2 = farVerts[ 2 ];

			} else {

				point2 = nearVerts[ 2 ];

			}

			let squaredBBWidth = point1.distanceTo( point2 );
			if ( this.fade ) {

				// expand the shadow extents by the fade margin if fade is enabled.
				const camera = this.camera;
				const far = Math.max( camera.far, this.maxFar );
				const linearDepth = frustum.vertices.far[ 0 ].z / ( far - camera.near );
				const margin = 0.25 * Math.pow( linearDepth, 2.0 ) * ( far - camera.near );

				squaredBBWidth += margin;

			}

			shadowCam.left = - squaredBBWidth / 2;
			shadowCam.right = squaredBBWidth / 2;
			shadowCam.top = squaredBBWidth / 2;
			shadowCam.bottom = - squaredBBWidth / 2;
			shadowCam.updateProjectionMatrix();

		}

	}

	/**
	 * Computes the breaks of this CSM instance based on the scene's camera, number of cascades
	 * and the selected split mode.
	 *
	 * @private
	 */
	_getBreaks() {

		const camera = this.camera;
		const far = Math.min( camera.far, this.maxFar );
		this.breaks.length = 0;

		switch ( this.mode ) {

			case 'uniform':
				uniformSplit( this.cascades, camera.near, far, this.breaks );
				break;
			case 'logarithmic':
				logarithmicSplit( this.cascades, camera.near, far, this.breaks );
				break;
			case 'practical':
				practicalSplit( this.cascades, camera.near, far, 0.5, this.breaks );
				break;
			case 'custom':
				if ( this.customSplitsCallback === undefined ) console.error( 'CSM: Custom split scheme callback not defined.' );
				this.customSplitsCallback( this.cascades, camera.near, far, this.breaks );
				break;

		}

		function uniformSplit( amount, near, far, target ) {

			for ( let i = 1; i < amount; i ++ ) {

				target.push( ( near + ( far - near ) * i / amount ) / far );

			}

			target.push( 1 );

		}

		function logarithmicSplit( amount, near, far, target ) {

			for ( let i = 1; i < amount; i ++ ) {

				target.push( ( near * ( far / near ) ** ( i / amount ) ) / far );

			}

			target.push( 1 );

		}

		function practicalSplit( amount, near, far, lambda, target ) {

			_uniformArray.length = 0;
			_logArray.length = 0;
			logarithmicSplit( amount, near, far, _logArray );
			uniformSplit( amount, near, far, _uniformArray );

			for ( let i = 1; i < amount; i ++ ) {

				target.push( MathUtils.lerp( _uniformArray[ i - 1 ], _logArray[ i - 1 ], lambda ) );

			}

			target.push( 1 );

		}

	}

	/**
	 * Updates the CSM. This method must be called in your animation loop before
	 * calling `renderer.render()`.
	 */
	update() {

		const camera = this.camera;
		const frustums = this.frustums;

		// for each frustum we need to find its min-max box aligned with the light orientation
		// the position in _lightOrientationMatrix does not matter, as we transform there and back
		_lightOrientationMatrix.lookAt( new Vector3(), this.lightDirection, _up );
		_lightOrientationMatrixInverse.copy( _lightOrientationMatrix ).invert();

		for ( let i = 0; i < frustums.length; i ++ ) {

			const light = this.lights[ i ];
			const shadowCam = light.shadow.camera;
			const texelWidth = ( shadowCam.right - shadowCam.left ) / this.shadowMapSize;
			const texelHeight = ( shadowCam.top - shadowCam.bottom ) / this.shadowMapSize;
			_cameraToLightMatrix.multiplyMatrices( _lightOrientationMatrixInverse, camera.matrixWorld );
			frustums[ i ].toSpace( _cameraToLightMatrix, _lightSpaceFrustum );

			const nearVerts = _lightSpaceFrustum.vertices.near;
			const farVerts = _lightSpaceFrustum.vertices.far;
			_bbox.makeEmpty();
			for ( let j = 0; j < 4; j ++ ) {

				_bbox.expandByPoint( nearVerts[ j ] );
				_bbox.expandByPoint( farVerts[ j ] );

			}

			_bbox.getCenter( _center );
			_center.z = _bbox.max.z + this.lightMargin;
			_center.x = Math.floor( _center.x / texelWidth ) * texelWidth;
			_center.y = Math.floor( _center.y / texelHeight ) * texelHeight;
			_center.applyMatrix4( _lightOrientationMatrix );

			light.position.copy( _center );
			light.target.position.copy( _center );

			light.target.position.x += this.lightDirection.x;
			light.target.position.y += this.lightDirection.y;
			light.target.position.z += this.lightDirection.z;

		}

	}

	/**
	 * Injects the CSM shader enhancements into the built-in materials.
	 *
	 * @private
	 */
	_injectInclude() {

		ShaderChunk.lights_fragment_begin = CSMShader.lights_fragment_begin;
		ShaderChunk.lights_pars_begin = CSMShader.lights_pars_begin;

	}

	/**
	 * Applications must call this method for all materials that should be affected by CSM.
	 *
	 * @param {Material} material - The material to setup for CSM support.
	 */
	setupMaterial( material ) {

		material.defines = material.defines || {};
		material.defines.USE_CSM = 1;
		material.defines.CSM_CASCADES = this.cascades;

		if ( this.fade ) {

			material.defines.CSM_FADE = '';

		}

		const breaksVec2 = [];
		const scope = this;
		const shaders = this.shaders;

		material.onBeforeCompile = function ( shader ) {

			const far = Math.min( scope.camera.far, scope.maxFar );
			scope._getExtendedBreaks( breaksVec2 );

			shader.uniforms.CSM_cascades = { value: breaksVec2 };
			shader.uniforms.cameraNear = { value: scope.camera.near };
			shader.uniforms.shadowFar = { value: far };

			shaders.set( material, shader );

		};

		shaders.set( material, null );

	}

	/**
	 * Updates the CSM uniforms.
	 *
	 * @private
	 */
	_updateUniforms() {

		const far = Math.min( this.camera.far, this.maxFar );
		const shaders = this.shaders;

		shaders.forEach( function ( shader, material ) {

			if ( shader !== null ) {

				const uniforms = shader.uniforms;
				this._getExtendedBreaks( uniforms.CSM_cascades.value );
				uniforms.cameraNear.value = this.camera.near;
				uniforms.shadowFar.value = far;

			}

			if ( ! this.fade && 'CSM_FADE' in material.defines ) {

				delete material.defines.CSM_FADE;
				material.needsUpdate = true;

			} else if ( this.fade && ! ( 'CSM_FADE' in material.defines ) ) {

				material.defines.CSM_FADE = '';
				material.needsUpdate = true;

			}

		}, this );

	}

	/**
	 * Computes the extended breaks for the CSM uniforms.
	 *
	 * @private
	 * @param {Array<Vector2>} target - The target array that holds the extended breaks.
	 */
	_getExtendedBreaks( target ) {

		while ( target.length < this.breaks.length ) {

			target.push( new Vector2() );

		}

		target.length = this.breaks.length;

		for ( let i = 0; i < this.cascades; i ++ ) {

			const amount = this.breaks[ i ];
			const prev = this.breaks[ i - 1 ] || 0;
			target[ i ].x = prev;
			target[ i ].y = amount;

		}

	}

	/**
	 * Applications must call this method every time they change camera or CSM settings.
	 */
	updateFrustums() {

		this._getBreaks();
		this._initCascades();
		this._updateShadowBounds();
		this._updateUniforms();

	}

	/**
	 * Applications must call this method when they remove the CSM usage from their scene.
	 */
	remove() {

		for ( let i = 0; i < this.lights.length; i ++ ) {

			this.parent.remove( this.lights[ i ].target );
			this.parent.remove( this.lights[ i ] );

		}

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		const shaders = this.shaders;
		shaders.forEach( function ( shader, material ) {

			delete material.onBeforeCompile;
			delete material.defines.USE_CSM;
			delete material.defines.CSM_CASCADES;
			delete material.defines.CSM_FADE;

			if ( shader !== null ) {

				delete shader.uniforms.CSM_cascades;
				delete shader.uniforms.cameraNear;
				delete shader.uniforms.shadowFar;

			}

			material.needsUpdate = true;

		} );
		shaders.clear();

	}

}
```
</details>

#### Methods

##### `_createLights(): void`

<details><summary>Code</summary>

```ts
_createLights() {

		for ( let i = 0; i < this.cascades; i ++ ) {

			const light = new DirectionalLight( 0xffffff, this.lightIntensity );
			light.castShadow = true;
			light.shadow.mapSize.width = this.shadowMapSize;
			light.shadow.mapSize.height = this.shadowMapSize;

			light.shadow.camera.near = this.lightNear;
			light.shadow.camera.far = this.lightFar;
			light.shadow.bias = this.shadowBias;

			this.parent.add( light );
			this.parent.add( light.target );
			this.lights.push( light );

		}

	}
```
</details>

##### `_initCascades(): void`

<details><summary>Code</summary>

```ts
_initCascades() {

		const camera = this.camera;
		camera.updateProjectionMatrix();
		this.mainFrustum.setFromProjectionMatrix( camera.projectionMatrix, this.maxFar );
		this.mainFrustum.split( this.breaks, this.frustums );

	}
```
</details>

##### `_updateShadowBounds(): void`

<details><summary>Code</summary>

```ts
_updateShadowBounds() {

		const frustums = this.frustums;
		for ( let i = 0; i < frustums.length; i ++ ) {

			const light = this.lights[ i ];
			const shadowCam = light.shadow.camera;
			const frustum = this.frustums[ i ];

			// Get the two points that represent that furthest points on the frustum assuming
			// that's either the diagonal across the far plane or the diagonal across the whole
			// frustum itself.
			const nearVerts = frustum.vertices.near;
			const farVerts = frustum.vertices.far;
			const point1 = farVerts[ 0 ];
			let point2;
			if ( point1.distanceTo( farVerts[ 2 ] ) > point1.distanceTo( nearVerts[ 2 ] ) ) {

				point2 = farVerts[ 2 ];

			} else {

				point2 = nearVerts[ 2 ];

			}

			let squaredBBWidth = point1.distanceTo( point2 );
			if ( this.fade ) {

				// expand the shadow extents by the fade margin if fade is enabled.
				const camera = this.camera;
				const far = Math.max( camera.far, this.maxFar );
				const linearDepth = frustum.vertices.far[ 0 ].z / ( far - camera.near );
				const margin = 0.25 * Math.pow( linearDepth, 2.0 ) * ( far - camera.near );

				squaredBBWidth += margin;

			}

			shadowCam.left = - squaredBBWidth / 2;
			shadowCam.right = squaredBBWidth / 2;
			shadowCam.top = squaredBBWidth / 2;
			shadowCam.bottom = - squaredBBWidth / 2;
			shadowCam.updateProjectionMatrix();

		}

	}
```
</details>

##### `_getBreaks(): void`

<details><summary>Code</summary>

```ts
_getBreaks() {

		const camera = this.camera;
		const far = Math.min( camera.far, this.maxFar );
		this.breaks.length = 0;

		switch ( this.mode ) {

			case 'uniform':
				uniformSplit( this.cascades, camera.near, far, this.breaks );
				break;
			case 'logarithmic':
				logarithmicSplit( this.cascades, camera.near, far, this.breaks );
				break;
			case 'practical':
				practicalSplit( this.cascades, camera.near, far, 0.5, this.breaks );
				break;
			case 'custom':
				if ( this.customSplitsCallback === undefined ) console.error( 'CSM: Custom split scheme callback not defined.' );
				this.customSplitsCallback( this.cascades, camera.near, far, this.breaks );
				break;

		}

		function uniformSplit( amount, near, far, target ) {

			for ( let i = 1; i < amount; i ++ ) {

				target.push( ( near + ( far - near ) * i / amount ) / far );

			}

			target.push( 1 );

		}

		function logarithmicSplit( amount, near, far, target ) {

			for ( let i = 1; i < amount; i ++ ) {

				target.push( ( near * ( far / near ) ** ( i / amount ) ) / far );

			}

			target.push( 1 );

		}

		function practicalSplit( amount, near, far, lambda, target ) {

			_uniformArray.length = 0;
			_logArray.length = 0;
			logarithmicSplit( amount, near, far, _logArray );
			uniformSplit( amount, near, far, _uniformArray );

			for ( let i = 1; i < amount; i ++ ) {

				target.push( MathUtils.lerp( _uniformArray[ i - 1 ], _logArray[ i - 1 ], lambda ) );

			}

			target.push( 1 );

		}

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const camera = this.camera;
		const frustums = this.frustums;

		// for each frustum we need to find its min-max box aligned with the light orientation
		// the position in _lightOrientationMatrix does not matter, as we transform there and back
		_lightOrientationMatrix.lookAt( new Vector3(), this.lightDirection, _up );
		_lightOrientationMatrixInverse.copy( _lightOrientationMatrix ).invert();

		for ( let i = 0; i < frustums.length; i ++ ) {

			const light = this.lights[ i ];
			const shadowCam = light.shadow.camera;
			const texelWidth = ( shadowCam.right - shadowCam.left ) / this.shadowMapSize;
			const texelHeight = ( shadowCam.top - shadowCam.bottom ) / this.shadowMapSize;
			_cameraToLightMatrix.multiplyMatrices( _lightOrientationMatrixInverse, camera.matrixWorld );
			frustums[ i ].toSpace( _cameraToLightMatrix, _lightSpaceFrustum );

			const nearVerts = _lightSpaceFrustum.vertices.near;
			const farVerts = _lightSpaceFrustum.vertices.far;
			_bbox.makeEmpty();
			for ( let j = 0; j < 4; j ++ ) {

				_bbox.expandByPoint( nearVerts[ j ] );
				_bbox.expandByPoint( farVerts[ j ] );

			}

			_bbox.getCenter( _center );
			_center.z = _bbox.max.z + this.lightMargin;
			_center.x = Math.floor( _center.x / texelWidth ) * texelWidth;
			_center.y = Math.floor( _center.y / texelHeight ) * texelHeight;
			_center.applyMatrix4( _lightOrientationMatrix );

			light.position.copy( _center );
			light.target.position.copy( _center );

			light.target.position.x += this.lightDirection.x;
			light.target.position.y += this.lightDirection.y;
			light.target.position.z += this.lightDirection.z;

		}

	}
```
</details>

##### `_injectInclude(): void`

<details><summary>Code</summary>

```ts
_injectInclude() {

		ShaderChunk.lights_fragment_begin = CSMShader.lights_fragment_begin;
		ShaderChunk.lights_pars_begin = CSMShader.lights_pars_begin;

	}
```
</details>

##### `setupMaterial(material: Material): void`

<details><summary>Code</summary>

```ts
setupMaterial( material ) {

		material.defines = material.defines || {};
		material.defines.USE_CSM = 1;
		material.defines.CSM_CASCADES = this.cascades;

		if ( this.fade ) {

			material.defines.CSM_FADE = '';

		}

		const breaksVec2 = [];
		const scope = this;
		const shaders = this.shaders;

		material.onBeforeCompile = function ( shader ) {

			const far = Math.min( scope.camera.far, scope.maxFar );
			scope._getExtendedBreaks( breaksVec2 );

			shader.uniforms.CSM_cascades = { value: breaksVec2 };
			shader.uniforms.cameraNear = { value: scope.camera.near };
			shader.uniforms.shadowFar = { value: far };

			shaders.set( material, shader );

		};

		shaders.set( material, null );

	}
```
</details>

##### `_updateUniforms(): void`

<details><summary>Code</summary>

```ts
_updateUniforms() {

		const far = Math.min( this.camera.far, this.maxFar );
		const shaders = this.shaders;

		shaders.forEach( function ( shader, material ) {

			if ( shader !== null ) {

				const uniforms = shader.uniforms;
				this._getExtendedBreaks( uniforms.CSM_cascades.value );
				uniforms.cameraNear.value = this.camera.near;
				uniforms.shadowFar.value = far;

			}

			if ( ! this.fade && 'CSM_FADE' in material.defines ) {

				delete material.defines.CSM_FADE;
				material.needsUpdate = true;

			} else if ( this.fade && ! ( 'CSM_FADE' in material.defines ) ) {

				material.defines.CSM_FADE = '';
				material.needsUpdate = true;

			}

		}, this );

	}
```
</details>

##### `_getExtendedBreaks(target: Vector2[]): void`

<details><summary>Code</summary>

```ts
_getExtendedBreaks( target ) {

		while ( target.length < this.breaks.length ) {

			target.push( new Vector2() );

		}

		target.length = this.breaks.length;

		for ( let i = 0; i < this.cascades; i ++ ) {

			const amount = this.breaks[ i ];
			const prev = this.breaks[ i - 1 ] || 0;
			target[ i ].x = prev;
			target[ i ].y = amount;

		}

	}
```
</details>

##### `updateFrustums(): void`

<details><summary>Code</summary>

```ts
updateFrustums() {

		this._getBreaks();
		this._initCascades();
		this._updateShadowBounds();
		this._updateUniforms();

	}
```
</details>

##### `remove(): void`

<details><summary>Code</summary>

```ts
remove() {

		for ( let i = 0; i < this.lights.length; i ++ ) {

			this.parent.remove( this.lights[ i ].target );
			this.parent.remove( this.lights[ i ] );

		}

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		const shaders = this.shaders;
		shaders.forEach( function ( shader, material ) {

			delete material.onBeforeCompile;
			delete material.defines.USE_CSM;
			delete material.defines.CSM_CASCADES;
			delete material.defines.CSM_FADE;

			if ( shader !== null ) {

				delete shader.uniforms.CSM_cascades;
				delete shader.uniforms.cameraNear;
				delete shader.uniforms.shadowFar;

			}

			material.needsUpdate = true;

		} );
		shaders.clear();

	}
```
</details>


---