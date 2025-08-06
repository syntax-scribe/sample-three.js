[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CSMShadowNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 🧱 Classes | 2 |
| 📦 Imports | 21 |
| 📊 Variables & Constants | 43 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/csm/CSMShadowNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `three/webgpu` |
| `Vector3` | `three/webgpu` |
| `MathUtils` | `three/webgpu` |
| `Matrix4` | `three/webgpu` |
| `Box3` | `three/webgpu` |
| `Object3D` | `three/webgpu` |
| `WebGLCoordinateSystem` | `three/webgpu` |
| `ShadowBaseNode` | `three/webgpu` |
| `CSMFrustum` | `./CSMFrustum.js` |
| `viewZToOrthographicDepth` | `three/tsl` |
| `reference` | `three/tsl` |
| `uniform` | `three/tsl` |
| `float` | `three/tsl` |
| `vec4` | `three/tsl` |
| `vec2` | `three/tsl` |
| `If` | `three/tsl` |
| `Fn` | `three/tsl` |
| `min` | `three/tsl` |
| `renderGroup` | `three/tsl` |
| `positionView` | `three/tsl` |
| `shadow` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_cameraToLightMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_lightSpaceFrustum` | `CSMFrustum` | let/var | `new CSMFrustum()` | ✗ |
| `_center` | `any` | let/var | `new Vector3()` | ✗ |
| `_bbox` | `any` | let/var | `new Box3()` | ✗ |
| `_uniformArray` | `any[]` | let/var | `[]` | ✗ |
| `_logArray` | `any[]` | let/var | `[]` | ✗ |
| `_lightDirection` | `any` | let/var | `new Vector3()` | ✗ |
| `_lightOrientationMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_lightOrientationMatrixInverse` | `any` | let/var | `new Matrix4()` | ✗ |
| `_up` | `any` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `data` | `{ webGL: boolean; }` | let/var | `{ webGL: renderer.coordinateSystem === WebGLCoordinateSystem }` | ✗ |
| `light` | `any` | let/var | `this.light` | ✗ |
| `lwLight` | `LwLight` | let/var | `new LwLight()` | ✗ |
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `amount` | `number` | let/var | `this.breaks[ i ]` | ✗ |
| `prev` | `number` | let/var | `this.breaks[ i - 1 ] \|\| 0` | ✗ |
| `frustums` | `CSMFrustum[]` | let/var | `this.frustums` | ✗ |
| `shadowCam` | `any` | let/var | `this.lights[ i ].shadow.camera` | ✗ |
| `frustum` | `CSMFrustum` | let/var | `this.frustums[ i ]` | ✗ |
| `nearVerts` | `any` | let/var | `frustum.vertices.near` | ✗ |
| `farVerts` | `any` | let/var | `frustum.vertices.far` | ✗ |
| `point1` | `any` | let/var | `farVerts[ 0 ]` | ✗ |
| `point2` | `any` | let/var | `*not shown*` | ✗ |
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `linearDepth` | `number` | let/var | `frustum.vertices.far[ 0 ].z / ( far - camera.near )` | ✗ |
| `margin` | `number` | let/var | `0.25 * Math.pow( linearDepth, 2.0 ) * ( far - camera.near )` | ✗ |
| `lastCascade` | `number` | let/var | `this.cascades - 1` | ✗ |
| `isLastCascade` | `boolean` | let/var | `i === lastCascade` | ✗ |
| `light` | `any` | let/var | `this.light` | ✗ |
| `parent` | `any` | let/var | `light.parent` | ✗ |
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `frustums` | `CSMFrustum[]` | let/var | `this.frustums` | ✗ |
| `lwLight` | `DirectionalLight` | let/var | `this.lights[ i ]` | ✗ |
| `lwLight` | `DirectionalLight` | let/var | `this.lights[ i ]` | ✗ |
| `shadow` | `any` | let/var | `lwLight.shadow` | ✗ |
| `shadowCam` | `any` | let/var | `shadow.camera` | ✗ |
| `texelWidth` | `number` | let/var | `( shadowCam.right - shadowCam.left ) / shadow.mapSize.width` | ✗ |
| `texelHeight` | `number` | let/var | `( shadowCam.top - shadowCam.bottom ) / shadow.mapSize.height` | ✗ |
| `nearVerts` | `any` | let/var | `_lightSpaceFrustum.vertices.near` | ✗ |
| `farVerts` | `any` | let/var | `_lightSpaceFrustum.vertices.far` | ✗ |
| `light` | `DirectionalLight` | let/var | `this.lights[ i ]` | ✗ |
| `parent` | `any` | let/var | `light.parent` | ✗ |


---

## Functions

### `CSMShadowNode._init({ camera, renderer }: any): void`

**JSDoc:**
```typescript
/**
	 * Inits the CSM shadow node.
	 *
	 * @private
	 * @param {NodeBuilder} builder - The node builder.
	 */
```

**Parameters:**

- **`{ camera, renderer }`** `any`

**Returns:** `void`

**Calls:**

- `light.shadow.clone`
- `this.lights.push`
- `this._shadowNodes.push`
- `shadow (from three/tsl)`
- `this._cascades.push`
- `this.updateFrustums`

<details><summary>Code</summary>

```typescript
_init( { camera, renderer } ) {

		this.camera = camera;

		const data = { webGL: renderer.coordinateSystem === WebGLCoordinateSystem };
		this.mainFrustum = new CSMFrustum( data );

		const light = this.light;

		for ( let i = 0; i < this.cascades; i ++ ) {

			const lwLight = new LwLight();
			lwLight.castShadow = true;

			const lShadow = light.shadow.clone();
			lShadow.bias = lShadow.bias * ( i + 1 );

			this.lights.push( lwLight );

			lwLight.shadow = lShadow;

			this._shadowNodes.push( shadow( lwLight, lShadow ) );

			this._cascades.push( new Vector2() );

		}

		this.updateFrustums();

	}
```
</details>

### `CSMShadowNode._initCascades(): void`

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

### `CSMShadowNode._getBreaks(): void`

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

### `CSMShadowNode._setLightBreaks(): void`

**JSDoc:**
```typescript
/**
	 * Sets the light breaks.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `this._cascades[ i ].set`

<details><summary>Code</summary>

```typescript
_setLightBreaks() {

		for ( let i = 0, l = this.cascades; i < l; i ++ ) {

			const amount = this.breaks[ i ];
			const prev = this.breaks[ i - 1 ] || 0;

			this._cascades[ i ].set( prev, amount );

		}

	}
```
</details>

### `CSMShadowNode._updateShadowBounds(): void`

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

			const shadowCam = this.lights[ i ].shadow.camera;
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

### `CSMShadowNode.updateFrustums(): void`

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
- `this._setLightBreaks`

<details><summary>Code</summary>

```typescript
updateFrustums() {

		this._getBreaks();
		this._initCascades();
		this._updateShadowBounds();
		this._setLightBreaks();

	}
```
</details>

### `CSMShadowNode._setupFade(): ShaderCallNodeInternal`

**JSDoc:**
```typescript
/**
	 * Setups the TSL when using fading.
	 *
	 * @private
	 * @return {ShaderCallNodeInternal}
	 */
```

**Returns:** `ShaderCallNodeInternal`

**Calls:**

- `reference( 'camera.near', 'float', this ).setGroup`
- `reference( '_cascades', 'vec2', this ).setGroup( renderGroup ).setName`
- `uniform( 'float' ).setGroup( renderGroup ).setName( 'shadowFar' )
			.onRenderUpdate`
- `Math.min`
- `viewZToOrthographicDepth( positionView.z, cameraNear, shadowFar ).toVar`
- `complex_call_8218`

**Internal Comments:**
```
// don't fade at nearest edge (x3)
```

<details><summary>Code</summary>

```typescript
_setupFade() {

		const cameraNear = reference( 'camera.near', 'float', this ).setGroup( renderGroup );
		const cascades = reference( '_cascades', 'vec2', this ).setGroup( renderGroup ).setName( 'cascades' );

		const shadowFar = uniform( 'float' ).setGroup( renderGroup ).setName( 'shadowFar' )
			.onRenderUpdate( () => Math.min( this.maxFar, this.camera.far ) );

		const linearDepth = viewZToOrthographicDepth( positionView.z, cameraNear, shadowFar ).toVar( 'linearDepth' );
		const lastCascade = this.cascades - 1;

		return Fn( ( builder ) => {

			this.setupShadowPosition( builder );

			const ret = vec4( 1, 1, 1, 1 ).toVar( 'shadowValue' );

			const cascade = vec2().toVar( 'cascade' );
			const cascadeCenter = float().toVar( 'cascadeCenter' );

			const margin = float().toVar( 'margin' );

			const csmX = float().toVar( 'csmX' );
			const csmY = float().toVar( 'csmY' );

			for ( let i = 0; i < this.cascades; i ++ ) {

				const isLastCascade = i === lastCascade;

				cascade.assign( cascades.element( i ) );

				cascadeCenter.assign( cascade.x.add( cascade.y ).div( 2.0 ) );

				const closestEdge = linearDepth.lessThan( cascadeCenter ).select( cascade.x, cascade.y );

				margin.assign( float( 0.25 ).mul( closestEdge.pow( 2.0 ) ) );

				csmX.assign( cascade.x.sub( margin.div( 2.0 ) ) );

				if ( isLastCascade ) {

					csmY.assign( cascade.y );

				} else {

					csmY.assign( cascade.y.add( margin.div( 2.0 ) ) );

				}

				const inRange = linearDepth.greaterThanEqual( csmX ).and( linearDepth.lessThanEqual( csmY ) );

				If( inRange, () => {

					const dist = min( linearDepth.sub( csmX ), csmY.sub( linearDepth ) ).toVar();

					let ratio = dist.div( margin ).clamp( 0.0, 1.0 );

					if ( i === 0 ) {

						// don't fade at nearest edge
						ratio = linearDepth.greaterThan( cascadeCenter ).select( ratio, 1 );

					}

					ret.subAssign( this._shadowNodes[ i ].oneMinus().mul( ratio ) );

				} );

			}

			return ret;

		} )();

	}
```
</details>

### `CSMShadowNode._setupStandard(): ShaderCallNodeInternal`

**JSDoc:**
```typescript
/**
	 * Setups the TSL when no fading (default).
	 *
	 * @private
	 * @return {ShaderCallNodeInternal}
	 */
```

**Returns:** `ShaderCallNodeInternal`

**Calls:**

- `reference( 'camera.near', 'float', this ).setGroup`
- `reference( '_cascades', 'vec2', this ).setGroup( renderGroup ).setName`
- `uniform( 'float' ).setGroup( renderGroup ).setName( 'shadowFar' )
			.onRenderUpdate`
- `Math.min`
- `viewZToOrthographicDepth( positionView.z, cameraNear, shadowFar ).toVar`
- `complex_call_10269`

<details><summary>Code</summary>

```typescript
_setupStandard() {

		const cameraNear = reference( 'camera.near', 'float', this ).setGroup( renderGroup );
		const cascades = reference( '_cascades', 'vec2', this ).setGroup( renderGroup ).setName( 'cascades' );

		const shadowFar = uniform( 'float' ).setGroup( renderGroup ).setName( 'shadowFar' )
			.onRenderUpdate( () => Math.min( this.maxFar, this.camera.far ) );

		const linearDepth = viewZToOrthographicDepth( positionView.z, cameraNear, shadowFar ).toVar( 'linearDepth' );

		return Fn( ( builder ) => {

			this.setupShadowPosition( builder );

			const ret = vec4( 1, 1, 1, 1 ).toVar( 'shadowValue' );
			const cascade = vec2().toVar( 'cascade' );

			for ( let i = 0; i < this.cascades; i ++ ) {

				cascade.assign( cascades.element( i ) );

				If( linearDepth.greaterThanEqual( cascade.x ).and( linearDepth.lessThanEqual( cascade.y ) ), () => {

					ret.assign( this._shadowNodes[ i ] );

				} );

			}

			return ret;

		} )();

	}
```
</details>

### `CSMShadowNode.setup(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this._init`
- `this._setupFade`
- `this._setupStandard`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		if ( this.camera === null ) this._init( builder );

		return this.fade === true ? this._setupFade() : this._setupStandard();

	}
```
</details>

### `CSMShadowNode.updateBefore(): void`

**Returns:** `void`

**Calls:**

- `parent.add`
- `_lightDirection.subVectors( light.target.position, light.position ).normalize`
- `_lightOrientationMatrix.lookAt`
- `_lightOrientationMatrixInverse.copy( _lightOrientationMatrix ).invert`
- `_cameraToLightMatrix.multiplyMatrices`
- `frustums[ i ].toSpace`
- `_bbox.makeEmpty`
- `_bbox.expandByPoint`
- `_bbox.getCenter`
- `Math.floor`
- `_center.applyMatrix4`
- `lwLight.position.copy`
- `lwLight.target.position.copy`
- `lwLight.target.position.add`

**Internal Comments:**
```
// make sure the placeholder light objects which represent the
// multiple cascade shadow casters are part of the scene graph
// for each frustum we need to find its min-max box aligned with the light orientation (x4)
// the position in _lightOrientationMatrix does not matter, as we transform there and back (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( /*builder*/ ) {

		const light = this.light;
		const parent = light.parent;
		const camera = this.camera;
		const frustums = this.frustums;

		// make sure the placeholder light objects which represent the
		// multiple cascade shadow casters are part of the scene graph

		for ( let i = 0; i < this.lights.length; i ++ ) {

			const lwLight = this.lights[ i ];

			if ( lwLight.parent === null ) {

				parent.add( lwLight.target );
				parent.add( lwLight );

			}

		}

		_lightDirection.subVectors( light.target.position, light.position ).normalize();

		// for each frustum we need to find its min-max box aligned with the light orientation
		// the position in _lightOrientationMatrix does not matter, as we transform there and back
		_lightOrientationMatrix.lookAt( light.position, light.target.position, _up );
		_lightOrientationMatrixInverse.copy( _lightOrientationMatrix ).invert();

		for ( let i = 0; i < frustums.length; i ++ ) {

			const lwLight = this.lights[ i ];
			const shadow = lwLight.shadow;
			const shadowCam = shadow.camera;
			const texelWidth = ( shadowCam.right - shadowCam.left ) / shadow.mapSize.width;
			const texelHeight = ( shadowCam.top - shadowCam.bottom ) / shadow.mapSize.height;

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

			lwLight.position.copy( _center );
			lwLight.target.position.copy( _center );
			lwLight.target.position.add( _lightDirection );

		}

	}
```
</details>

### `CSMShadowNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `parent.remove`
- `super.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		for ( let i = 0; i < this.lights.length; i ++ ) {

			const light = this.lights[ i ];
			const parent = light.parent;

			parent.remove( light.target );
			parent.remove( light );

		}

		super.dispose();

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

### `LwLight`

<details><summary>Class Code</summary>

```ts
class LwLight extends Object3D {

	constructor() {

		super();

		this.target = new Object3D();

	}

}
```
</details>

### `CSMShadowNode`

<details><summary>Class Code</summary>

```ts
class CSMShadowNode extends ShadowBaseNode {

	/**
	 * Constructs a new CSM shadow node.
	 *
	 * @param {DirectionalLight} light - The CSM light.
	 * @param {CSMShadowNode~Data} [data={}] - The CSM data.
	 */
	constructor( light, data = {} ) {

		super( light );

		/**
		 * The scene's camera.
		 *
		 * @type {?Camera}
		 * @default null
		 */
		this.camera = null;

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
		 * An array of numbers in the range `[0,1]` the defines how the
		 * mainCSM frustum should be split up.
		 *
		 * @type {Array<number>}
		 */
		this.breaks = [];

		this._cascades = [];

		/**
		 * The main frustum.
		 *
		 * @type {?CSMFrustum}
		 * @default null
		 */
		this.mainFrustum = null;

		/**
		 * An array of frustums representing the cascades.
		 *
		 * @type {Array<CSMFrustum>}
		 */
		this.frustums = [];

		/**
		 * An array of directional lights which cast the shadows for
		 * the different cascades. There is one directional light for each
		 * cascade.
		 *
		 * @type {Array<DirectionalLight>}
		 */
		this.lights = [];

		this._shadowNodes = [];

	}

	/**
	 * Inits the CSM shadow node.
	 *
	 * @private
	 * @param {NodeBuilder} builder - The node builder.
	 */
	_init( { camera, renderer } ) {

		this.camera = camera;

		const data = { webGL: renderer.coordinateSystem === WebGLCoordinateSystem };
		this.mainFrustum = new CSMFrustum( data );

		const light = this.light;

		for ( let i = 0; i < this.cascades; i ++ ) {

			const lwLight = new LwLight();
			lwLight.castShadow = true;

			const lShadow = light.shadow.clone();
			lShadow.bias = lShadow.bias * ( i + 1 );

			this.lights.push( lwLight );

			lwLight.shadow = lShadow;

			this._shadowNodes.push( shadow( lwLight, lShadow ) );

			this._cascades.push( new Vector2() );

		}

		this.updateFrustums();

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
	 * Sets the light breaks.
	 *
	 * @private
	 */
	_setLightBreaks() {

		for ( let i = 0, l = this.cascades; i < l; i ++ ) {

			const amount = this.breaks[ i ];
			const prev = this.breaks[ i - 1 ] || 0;

			this._cascades[ i ].set( prev, amount );

		}

	}

	/**
	 * Updates the shadow bounds of this CSM instance.
	 *
	 * @private
	 */
	_updateShadowBounds() {

		const frustums = this.frustums;

		for ( let i = 0; i < frustums.length; i ++ ) {

			const shadowCam = this.lights[ i ].shadow.camera;
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
	 * Applications must call this method every time they change camera or CSM settings.
	 */
	updateFrustums() {

		this._getBreaks();
		this._initCascades();
		this._updateShadowBounds();
		this._setLightBreaks();

	}

	/**
	 * Setups the TSL when using fading.
	 *
	 * @private
	 * @return {ShaderCallNodeInternal}
	 */
	_setupFade() {

		const cameraNear = reference( 'camera.near', 'float', this ).setGroup( renderGroup );
		const cascades = reference( '_cascades', 'vec2', this ).setGroup( renderGroup ).setName( 'cascades' );

		const shadowFar = uniform( 'float' ).setGroup( renderGroup ).setName( 'shadowFar' )
			.onRenderUpdate( () => Math.min( this.maxFar, this.camera.far ) );

		const linearDepth = viewZToOrthographicDepth( positionView.z, cameraNear, shadowFar ).toVar( 'linearDepth' );
		const lastCascade = this.cascades - 1;

		return Fn( ( builder ) => {

			this.setupShadowPosition( builder );

			const ret = vec4( 1, 1, 1, 1 ).toVar( 'shadowValue' );

			const cascade = vec2().toVar( 'cascade' );
			const cascadeCenter = float().toVar( 'cascadeCenter' );

			const margin = float().toVar( 'margin' );

			const csmX = float().toVar( 'csmX' );
			const csmY = float().toVar( 'csmY' );

			for ( let i = 0; i < this.cascades; i ++ ) {

				const isLastCascade = i === lastCascade;

				cascade.assign( cascades.element( i ) );

				cascadeCenter.assign( cascade.x.add( cascade.y ).div( 2.0 ) );

				const closestEdge = linearDepth.lessThan( cascadeCenter ).select( cascade.x, cascade.y );

				margin.assign( float( 0.25 ).mul( closestEdge.pow( 2.0 ) ) );

				csmX.assign( cascade.x.sub( margin.div( 2.0 ) ) );

				if ( isLastCascade ) {

					csmY.assign( cascade.y );

				} else {

					csmY.assign( cascade.y.add( margin.div( 2.0 ) ) );

				}

				const inRange = linearDepth.greaterThanEqual( csmX ).and( linearDepth.lessThanEqual( csmY ) );

				If( inRange, () => {

					const dist = min( linearDepth.sub( csmX ), csmY.sub( linearDepth ) ).toVar();

					let ratio = dist.div( margin ).clamp( 0.0, 1.0 );

					if ( i === 0 ) {

						// don't fade at nearest edge
						ratio = linearDepth.greaterThan( cascadeCenter ).select( ratio, 1 );

					}

					ret.subAssign( this._shadowNodes[ i ].oneMinus().mul( ratio ) );

				} );

			}

			return ret;

		} )();

	}

	/**
	 * Setups the TSL when no fading (default).
	 *
	 * @private
	 * @return {ShaderCallNodeInternal}
	 */
	_setupStandard() {

		const cameraNear = reference( 'camera.near', 'float', this ).setGroup( renderGroup );
		const cascades = reference( '_cascades', 'vec2', this ).setGroup( renderGroup ).setName( 'cascades' );

		const shadowFar = uniform( 'float' ).setGroup( renderGroup ).setName( 'shadowFar' )
			.onRenderUpdate( () => Math.min( this.maxFar, this.camera.far ) );

		const linearDepth = viewZToOrthographicDepth( positionView.z, cameraNear, shadowFar ).toVar( 'linearDepth' );

		return Fn( ( builder ) => {

			this.setupShadowPosition( builder );

			const ret = vec4( 1, 1, 1, 1 ).toVar( 'shadowValue' );
			const cascade = vec2().toVar( 'cascade' );

			for ( let i = 0; i < this.cascades; i ++ ) {

				cascade.assign( cascades.element( i ) );

				If( linearDepth.greaterThanEqual( cascade.x ).and( linearDepth.lessThanEqual( cascade.y ) ), () => {

					ret.assign( this._shadowNodes[ i ] );

				} );

			}

			return ret;

		} )();

	}

	setup( builder ) {

		if ( this.camera === null ) this._init( builder );

		return this.fade === true ? this._setupFade() : this._setupStandard();

	}

	updateBefore( /*builder*/ ) {

		const light = this.light;
		const parent = light.parent;
		const camera = this.camera;
		const frustums = this.frustums;

		// make sure the placeholder light objects which represent the
		// multiple cascade shadow casters are part of the scene graph

		for ( let i = 0; i < this.lights.length; i ++ ) {

			const lwLight = this.lights[ i ];

			if ( lwLight.parent === null ) {

				parent.add( lwLight.target );
				parent.add( lwLight );

			}

		}

		_lightDirection.subVectors( light.target.position, light.position ).normalize();

		// for each frustum we need to find its min-max box aligned with the light orientation
		// the position in _lightOrientationMatrix does not matter, as we transform there and back
		_lightOrientationMatrix.lookAt( light.position, light.target.position, _up );
		_lightOrientationMatrixInverse.copy( _lightOrientationMatrix ).invert();

		for ( let i = 0; i < frustums.length; i ++ ) {

			const lwLight = this.lights[ i ];
			const shadow = lwLight.shadow;
			const shadowCam = shadow.camera;
			const texelWidth = ( shadowCam.right - shadowCam.left ) / shadow.mapSize.width;
			const texelHeight = ( shadowCam.top - shadowCam.bottom ) / shadow.mapSize.height;

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

			lwLight.position.copy( _center );
			lwLight.target.position.copy( _center );
			lwLight.target.position.add( _lightDirection );

		}

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		for ( let i = 0; i < this.lights.length; i ++ ) {

			const light = this.lights[ i ];
			const parent = light.parent;

			parent.remove( light.target );
			parent.remove( light );

		}

		super.dispose();

	}

}
```
</details>

#### Methods

##### `_init({ camera, renderer }: any): void`

<details><summary>Code</summary>

```ts
_init( { camera, renderer } ) {

		this.camera = camera;

		const data = { webGL: renderer.coordinateSystem === WebGLCoordinateSystem };
		this.mainFrustum = new CSMFrustum( data );

		const light = this.light;

		for ( let i = 0; i < this.cascades; i ++ ) {

			const lwLight = new LwLight();
			lwLight.castShadow = true;

			const lShadow = light.shadow.clone();
			lShadow.bias = lShadow.bias * ( i + 1 );

			this.lights.push( lwLight );

			lwLight.shadow = lShadow;

			this._shadowNodes.push( shadow( lwLight, lShadow ) );

			this._cascades.push( new Vector2() );

		}

		this.updateFrustums();

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

##### `_setLightBreaks(): void`

<details><summary>Code</summary>

```ts
_setLightBreaks() {

		for ( let i = 0, l = this.cascades; i < l; i ++ ) {

			const amount = this.breaks[ i ];
			const prev = this.breaks[ i - 1 ] || 0;

			this._cascades[ i ].set( prev, amount );

		}

	}
```
</details>

##### `_updateShadowBounds(): void`

<details><summary>Code</summary>

```ts
_updateShadowBounds() {

		const frustums = this.frustums;

		for ( let i = 0; i < frustums.length; i ++ ) {

			const shadowCam = this.lights[ i ].shadow.camera;
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

##### `updateFrustums(): void`

<details><summary>Code</summary>

```ts
updateFrustums() {

		this._getBreaks();
		this._initCascades();
		this._updateShadowBounds();
		this._setLightBreaks();

	}
```
</details>

##### `_setupFade(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
_setupFade() {

		const cameraNear = reference( 'camera.near', 'float', this ).setGroup( renderGroup );
		const cascades = reference( '_cascades', 'vec2', this ).setGroup( renderGroup ).setName( 'cascades' );

		const shadowFar = uniform( 'float' ).setGroup( renderGroup ).setName( 'shadowFar' )
			.onRenderUpdate( () => Math.min( this.maxFar, this.camera.far ) );

		const linearDepth = viewZToOrthographicDepth( positionView.z, cameraNear, shadowFar ).toVar( 'linearDepth' );
		const lastCascade = this.cascades - 1;

		return Fn( ( builder ) => {

			this.setupShadowPosition( builder );

			const ret = vec4( 1, 1, 1, 1 ).toVar( 'shadowValue' );

			const cascade = vec2().toVar( 'cascade' );
			const cascadeCenter = float().toVar( 'cascadeCenter' );

			const margin = float().toVar( 'margin' );

			const csmX = float().toVar( 'csmX' );
			const csmY = float().toVar( 'csmY' );

			for ( let i = 0; i < this.cascades; i ++ ) {

				const isLastCascade = i === lastCascade;

				cascade.assign( cascades.element( i ) );

				cascadeCenter.assign( cascade.x.add( cascade.y ).div( 2.0 ) );

				const closestEdge = linearDepth.lessThan( cascadeCenter ).select( cascade.x, cascade.y );

				margin.assign( float( 0.25 ).mul( closestEdge.pow( 2.0 ) ) );

				csmX.assign( cascade.x.sub( margin.div( 2.0 ) ) );

				if ( isLastCascade ) {

					csmY.assign( cascade.y );

				} else {

					csmY.assign( cascade.y.add( margin.div( 2.0 ) ) );

				}

				const inRange = linearDepth.greaterThanEqual( csmX ).and( linearDepth.lessThanEqual( csmY ) );

				If( inRange, () => {

					const dist = min( linearDepth.sub( csmX ), csmY.sub( linearDepth ) ).toVar();

					let ratio = dist.div( margin ).clamp( 0.0, 1.0 );

					if ( i === 0 ) {

						// don't fade at nearest edge
						ratio = linearDepth.greaterThan( cascadeCenter ).select( ratio, 1 );

					}

					ret.subAssign( this._shadowNodes[ i ].oneMinus().mul( ratio ) );

				} );

			}

			return ret;

		} )();

	}
```
</details>

##### `_setupStandard(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
_setupStandard() {

		const cameraNear = reference( 'camera.near', 'float', this ).setGroup( renderGroup );
		const cascades = reference( '_cascades', 'vec2', this ).setGroup( renderGroup ).setName( 'cascades' );

		const shadowFar = uniform( 'float' ).setGroup( renderGroup ).setName( 'shadowFar' )
			.onRenderUpdate( () => Math.min( this.maxFar, this.camera.far ) );

		const linearDepth = viewZToOrthographicDepth( positionView.z, cameraNear, shadowFar ).toVar( 'linearDepth' );

		return Fn( ( builder ) => {

			this.setupShadowPosition( builder );

			const ret = vec4( 1, 1, 1, 1 ).toVar( 'shadowValue' );
			const cascade = vec2().toVar( 'cascade' );

			for ( let i = 0; i < this.cascades; i ++ ) {

				cascade.assign( cascades.element( i ) );

				If( linearDepth.greaterThanEqual( cascade.x ).and( linearDepth.lessThanEqual( cascade.y ) ), () => {

					ret.assign( this._shadowNodes[ i ] );

				} );

			}

			return ret;

		} )();

	}
```
</details>

##### `setup(builder: any): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		if ( this.camera === null ) this._init( builder );

		return this.fade === true ? this._setupFade() : this._setupStandard();

	}
```
</details>

##### `updateBefore(): void`

<details><summary>Code</summary>

```ts
updateBefore( /*builder*/ ) {

		const light = this.light;
		const parent = light.parent;
		const camera = this.camera;
		const frustums = this.frustums;

		// make sure the placeholder light objects which represent the
		// multiple cascade shadow casters are part of the scene graph

		for ( let i = 0; i < this.lights.length; i ++ ) {

			const lwLight = this.lights[ i ];

			if ( lwLight.parent === null ) {

				parent.add( lwLight.target );
				parent.add( lwLight );

			}

		}

		_lightDirection.subVectors( light.target.position, light.position ).normalize();

		// for each frustum we need to find its min-max box aligned with the light orientation
		// the position in _lightOrientationMatrix does not matter, as we transform there and back
		_lightOrientationMatrix.lookAt( light.position, light.target.position, _up );
		_lightOrientationMatrixInverse.copy( _lightOrientationMatrix ).invert();

		for ( let i = 0; i < frustums.length; i ++ ) {

			const lwLight = this.lights[ i ];
			const shadow = lwLight.shadow;
			const shadowCam = shadow.camera;
			const texelWidth = ( shadowCam.right - shadowCam.left ) / shadow.mapSize.width;
			const texelHeight = ( shadowCam.top - shadowCam.bottom ) / shadow.mapSize.height;

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

			lwLight.position.copy( _center );
			lwLight.target.position.copy( _center );
			lwLight.target.position.add( _lightDirection );

		}

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		for ( let i = 0; i < this.lights.length; i ++ ) {

			const light = this.lights[ i ];
			const parent = light.parent;

			parent.remove( light.target );
			parent.remove( light );

		}

		super.dispose();

	}
```
</details>


---