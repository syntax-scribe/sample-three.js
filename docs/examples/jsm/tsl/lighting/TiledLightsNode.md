[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `TiledLightsNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 🧱 Classes | 1 |
| 📦 Imports | 25 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/lighting/TiledLightsNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataTexture` | `three/webgpu` |
| `FloatType` | `three/webgpu` |
| `RGBAFormat` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `Vector3` | `three/webgpu` |
| `LightsNode` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `attributeArray` | `three/tsl` |
| `nodeProxy` | `three/tsl` |
| `int` | `three/tsl` |
| `float` | `three/tsl` |
| `vec2` | `three/tsl` |
| `ivec2` | `three/tsl` |
| `ivec4` | `three/tsl` |
| `uniform` | `three/tsl` |
| `Break` | `three/tsl` |
| `Loop` | `three/tsl` |
| `positionView` | `three/tsl` |
| `Fn` | `three/tsl` |
| `If` | `three/tsl` |
| `Return` | `three/tsl` |
| `textureLoad` | `three/tsl` |
| `instanceIndex` | `three/tsl` |
| `screenCoordinate` | `three/tsl` |
| `directPointLight` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector3` | `any` | let/var | `new Vector3()` | ✗ |
| `_size` | `any` | let/var | `new Vector2()` | ✗ |
| `data` | `any` | let/var | `lightsTexture.image.data` | ✗ |
| `lineSize` | `number` | let/var | `lightsTexture.image.width * 4` | ✗ |
| `light` | `any` | let/var | `tiledLights[ i ]` | ✗ |
| `offset` | `number` | let/var | `i * 4` | ✗ |
| `materialindex` | `number` | let/var | `0` | ✗ |
| `tiledIndex` | `number` | let/var | `0` | ✗ |
| `position` | `any` | let/var | `dataA.xyz` | ✗ |
| `distance` | `any` | let/var | `dataA.w` | ✗ |
| `color` | `any` | let/var | `dataB.rgb` | ✗ |
| `decay` | `any` | let/var | `dataB.w` | ✗ |
| `lightingModel` | `any` | let/var | `builder.context.reflectedLight` | ✗ |
| `multiple` | `number` | let/var | `this.tileSize` | ✗ |
| `bufferSize` | `any` | let/var | `new Vector2( width, height )` | ✗ |
| `lightsData` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( maxLights * 4 * 2 )` | ✗ |
| `lightsTexture` | `any` | let/var | `new DataTexture( lightsData, lightsData.length / 8, 2, RGBAFormat, FloatType )` | ✗ |
| `lightIndexesArray` | `Int32Array<ArrayBuffer>` | let/var | `new Int32Array( count * 4 * 2 )` | ✗ |
| `minBounds` | `any` | let/var | `tileScreen` | ✗ |
| `distanceFromCamera` | `any` | let/var | `viewPosition.z` | ✗ |


---

## Functions

### `TiledLightsNode.customCacheKey(): any`

**Returns:** `any`

**Calls:**

- `this._compute.getCacheKey`
- `super.customCacheKey`

<details><summary>Code</summary>

```typescript
customCacheKey() {

		return this._compute.getCacheKey() + super.customCacheKey();

	}
```
</details>

### `TiledLightsNode.updateLightsTexture(): void`

**Returns:** `void`

**Calls:**

- `_vector3.setFromMatrixPosition`

**Internal Comments:**
```
// world position (x4)
// store data (x2)
```

<details><summary>Code</summary>

```typescript
updateLightsTexture() {

		const { _lightsTexture: lightsTexture, tiledLights } = this;

		const data = lightsTexture.image.data;
		const lineSize = lightsTexture.image.width * 4;

		this._lightsCount.value = tiledLights.length;

		for ( let i = 0; i < tiledLights.length; i ++ ) {

			const light = tiledLights[ i ];

			// world position

			_vector3.setFromMatrixPosition( light.matrixWorld );

			// store data

			const offset = i * 4;

			data[ offset + 0 ] = _vector3.x;
			data[ offset + 1 ] = _vector3.y;
			data[ offset + 2 ] = _vector3.z;
			data[ offset + 3 ] = light.distance;

			data[ lineSize + offset + 0 ] = light.color.r * light.intensity;
			data[ lineSize + offset + 1 ] = light.color.g * light.intensity;
			data[ lineSize + offset + 2 ] = light.color.b * light.intensity;
			data[ lineSize + offset + 3 ] = light.decay;

		}

		lightsTexture.needsUpdate = true;

	}
```
</details>

### `TiledLightsNode.updateBefore(frame: any): void`

**Parameters:**

- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `this.updateProgram`
- `this.updateLightsTexture`
- `renderer.getDrawingBufferSize`
- `this._screenSize.value.copy`
- `renderer.compute`

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer, camera } = frame;

		this.updateProgram( renderer );

		this.updateLightsTexture( camera );

		this._cameraProjectionMatrix.value = camera.projectionMatrix;
		this._cameraViewMatrix.value = camera.matrixWorldInverse;

		renderer.getDrawingBufferSize( _size );
		this._screenSize.value.copy( _size );

		renderer.compute( this._compute );

	}
```
</details>

### `TiledLightsNode.setLights(lights: any): any`

**Parameters:**

- **`lights`** `any`

**Returns:** `any`

**Calls:**

- `super.setLights`

<details><summary>Code</summary>

```typescript
setLights( lights ) {

		const { tiledLights, materialLights } = this;

		let materialindex = 0;
		let tiledIndex = 0;

		for ( const light of lights ) {

			if ( light.isPointLight === true ) {

				tiledLights[ tiledIndex ++ ] = light;

			} else {

				materialLights[ materialindex ++ ] = light;

			}

		}

		materialLights.length = materialindex;
		tiledLights.length = tiledIndex;

		return super.setLights( materialLights );

	}
```
</details>

### `TiledLightsNode.getBlock(block: number): any`

**Parameters:**

- **`block`** `number`

**Returns:** `any`

**Calls:**

- `this._lightIndexes.element`
- `this._screenTileIndex.mul`
- `int( 2 ).add`
- `int (from three/tsl)`

<details><summary>Code</summary>

```typescript
getBlock( block = 0 ) {

		return this._lightIndexes.element( this._screenTileIndex.mul( int( 2 ).add( int( block ) ) ) );

	}
```
</details>

### `TiledLightsNode.getTile(element: any): any`

**Parameters:**

- **`element`** `any`

**Returns:** `any`

**Calls:**

- `int (from three/tsl)`
- `element.div`
- `this._screenTileIndex.mul( int( 2 ) ).add`
- `this._lightIndexes.element( tileIndex ).element`
- `element.mod`

<details><summary>Code</summary>

```typescript
getTile( element ) {

		element = int( element );

		const stride = int( 4 );
		const tileOffset = element.div( stride );
		const tileIndex = this._screenTileIndex.mul( int( 2 ) ).add( tileOffset );

		return this._lightIndexes.element( tileIndex ).element( element.mod( stride ) );

	}
```
</details>

### `TiledLightsNode.getLightData(index: any): { position: any; viewPosition: any; distance: any; color: any; decay: any; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ position: any; viewPosition: any; distance: any; color: any; decay: any; }`

**Calls:**

- `int (from three/tsl)`
- `textureLoad (from three/tsl)`
- `ivec2 (from three/tsl)`
- `this._cameraViewMatrix.mul`

<details><summary>Code</summary>

```typescript
getLightData( index ) {

		index = int( index );

		const dataA = textureLoad( this._lightsTexture, ivec2( index, 0 ) );
		const dataB = textureLoad( this._lightsTexture, ivec2( index, 1 ) );

		const position = dataA.xyz;
		const viewPosition = this._cameraViewMatrix.mul( position );
		const distance = dataA.w;
		const color = dataB.rgb;
		const decay = dataB.w;

		return {
			position,
			viewPosition,
			distance,
			color,
			decay
		};

	}
```
</details>

### `TiledLightsNode.setupLights(builder: any, lightNodes: any): void`

**Parameters:**

- **`builder`** `any`
- **`lightNodes`** `any`

**Returns:** `void`

**Calls:**

- `this.updateProgram`
- `lightingModel.directDiffuse.toStack`
- `lightingModel.directSpecular.toStack`
- `super.setupLights`
- `complex_call_5670`

**Internal Comments:**
```
// (x2)
// force declaration order, before of the loop (x5)
```

<details><summary>Code</summary>

```typescript
setupLights( builder, lightNodes ) {

		this.updateProgram( builder.renderer );

		//

		const lightingModel = builder.context.reflectedLight;

		// force declaration order, before of the loop
		lightingModel.directDiffuse.toStack();
		lightingModel.directSpecular.toStack();

		super.setupLights( builder, lightNodes );

		Fn( () => {

			Loop( this._tileLightCount, ( { i } ) => {

				const lightIndex = this.getTile( i );

				If( lightIndex.equal( int( 0 ) ), () => {

					Break();

				} );

				const { color, decay, viewPosition, distance } = this.getLightData( lightIndex.sub( 1 ) );

				builder.lightsNode.setupDirectLight( builder, this, directPointLight( {
					color,
					lightVector: viewPosition.sub( positionView ),
					cutoffDistance: distance,
					decayExponent: decay
				} ) );

			} );

		}, 'void' )();

	}
```
</details>

### `TiledLightsNode.getBufferFitSize(value: any): number`

**Parameters:**

- **`value`** `any`

**Returns:** `number`

**Calls:**

- `Math.ceil`

<details><summary>Code</summary>

```typescript
getBufferFitSize( value ) {

		const multiple = this.tileSize;

		return Math.ceil( value / multiple ) * multiple;

	}
```
</details>

### `TiledLightsNode.setSize(width: any, height: any): this`

**Parameters:**

- **`width`** `any`
- **`height`** `any`

**Returns:** `this`

**Calls:**

- `this.getBufferFitSize`
- `this.create`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		width = this.getBufferFitSize( width );
		height = this.getBufferFitSize( height );

		if ( ! this._bufferSize || this._bufferSize.width !== width || this._bufferSize.height !== height ) {

			this.create( width, height );

		}

		return this;

	}
```
</details>

### `TiledLightsNode.updateProgram(renderer: any): void`

**Parameters:**

- **`renderer`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getDrawingBufferSize`
- `this.getBufferFitSize`
- `this.create`

<details><summary>Code</summary>

```typescript
updateProgram( renderer ) {

		renderer.getDrawingBufferSize( _size );

		const width = this.getBufferFitSize( _size.width );
		const height = this.getBufferFitSize( _size.height );

		if ( this._bufferSize === null ) {

			this.create( width, height );

		} else if ( this._bufferSize.width !== width || this._bufferSize.height !== height ) {

			this.create( width, height );

		}

	}
```
</details>

### `TiledLightsNode.create(width: any, height: any): void`

**Parameters:**

- **`width`** `any`
- **`height`** `any`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `attributeArray( lightIndexesArray, 'ivec4' ).setName`
- `instanceIndex.mul( int( 2 ) ).add`
- `int (from three/tsl)`
- `lightIndexes.element`
- `elementIndex.div`
- `lightIndexes.element( tileIndex ).element`
- `elementIndex.mod`
- `Fn( () => {

			const { _cameraProjectionMatrix: cameraProjectionMatrix, _bufferSize: bufferSize, _screenSize: screenSize } = this;

			const tiledBufferSize = bufferSize.clone().divideScalar( tileSize ).floor();

			const tileScreen = vec2(
				instanceIndex.mod( tiledBufferSize.width ),
				instanceIndex.div( tiledBufferSize.width )
			).mul( tileSize ).div( screenSize );

			const blockSize = float( tileSize ).div( screenSize );
			const minBounds = tileScreen;
			const maxBounds = minBounds.add( blockSize );

			const index = int( 0 ).toVar();

			getBlock( 0 ).assign( ivec4( 0 ) );
			getBlock( 1 ).assign( ivec4( 0 ) );

			Loop( this.maxLights, ( { i } ) => {

				If( index.greaterThanEqual( this._tileLightCount ).or( int( i ).greaterThanEqual( int( this._lightsCount ) ) ), () => {

					Return();

				} );

				const { viewPosition, distance } = this.getLightData( i );

				const projectedPosition = cameraProjectionMatrix.mul( viewPosition );
				const ndc = projectedPosition.div( projectedPosition.w );
				const screenPosition = ndc.xy.mul( 0.5 ).add( 0.5 ).flipY();

				const distanceFromCamera = viewPosition.z;
				const pointRadius = distance.div( distanceFromCamera );

				If( circleIntersectsAABB( screenPosition, pointRadius, minBounds, maxBounds ), () => {

					getTile( index ).assign( i.add( int( 1 ) ) );
					index.addAssign( int( 1 ) );

				} );

			} );

		} )().compute`
- `screenCoordinate.div( tileSize ).floor().toVar`
- `screenTile.x.add`
- `screenTile.y.mul`

**Internal Comments:**
```
// buffers (x2)
// compute (x2)
// screen coordinate lighting indexes (x2)
// assigns (x4)
```

<details><summary>Code</summary>

```typescript
create( width, height ) {

		const { tileSize, maxLights } = this;

		const bufferSize = new Vector2( width, height );
		const lineSize = Math.floor( bufferSize.width / tileSize );
		const count = Math.floor( ( bufferSize.width * bufferSize.height ) / tileSize );

		// buffers

		const lightsData = new Float32Array( maxLights * 4 * 2 ); // 2048 lights, 4 elements(rgba), 2 components, 1 component per line (position, distance, color, decay)
		const lightsTexture = new DataTexture( lightsData, lightsData.length / 8, 2, RGBAFormat, FloatType );

		const lightIndexesArray = new Int32Array( count * 4 * 2 );
		const lightIndexes = attributeArray( lightIndexesArray, 'ivec4' ).setName( 'lightIndexes' );

		// compute

		const getBlock = ( index ) => {

			const tileIndex = instanceIndex.mul( int( 2 ) ).add( int( index ) );

			return lightIndexes.element( tileIndex );

		};

		const getTile = ( elementIndex ) => {

			elementIndex = int( elementIndex );

			const stride = int( 4 );
			const tileOffset = elementIndex.div( stride );
			const tileIndex = instanceIndex.mul( int( 2 ) ).add( tileOffset );

			return lightIndexes.element( tileIndex ).element( elementIndex.mod( stride ) );

		};

		const compute = Fn( () => {

			const { _cameraProjectionMatrix: cameraProjectionMatrix, _bufferSize: bufferSize, _screenSize: screenSize } = this;

			const tiledBufferSize = bufferSize.clone().divideScalar( tileSize ).floor();

			const tileScreen = vec2(
				instanceIndex.mod( tiledBufferSize.width ),
				instanceIndex.div( tiledBufferSize.width )
			).mul( tileSize ).div( screenSize );

			const blockSize = float( tileSize ).div( screenSize );
			const minBounds = tileScreen;
			const maxBounds = minBounds.add( blockSize );

			const index = int( 0 ).toVar();

			getBlock( 0 ).assign( ivec4( 0 ) );
			getBlock( 1 ).assign( ivec4( 0 ) );

			Loop( this.maxLights, ( { i } ) => {

				If( index.greaterThanEqual( this._tileLightCount ).or( int( i ).greaterThanEqual( int( this._lightsCount ) ) ), () => {

					Return();

				} );

				const { viewPosition, distance } = this.getLightData( i );

				const projectedPosition = cameraProjectionMatrix.mul( viewPosition );
				const ndc = projectedPosition.div( projectedPosition.w );
				const screenPosition = ndc.xy.mul( 0.5 ).add( 0.5 ).flipY();

				const distanceFromCamera = viewPosition.z;
				const pointRadius = distance.div( distanceFromCamera );

				If( circleIntersectsAABB( screenPosition, pointRadius, minBounds, maxBounds ), () => {

					getTile( index ).assign( i.add( int( 1 ) ) );
					index.addAssign( int( 1 ) );

				} );

			} );

		} )().compute( count );

		// screen coordinate lighting indexes

		const screenTile = screenCoordinate.div( tileSize ).floor().toVar();
		const screenTileIndex = screenTile.x.add( screenTile.y.mul( lineSize ) );

		// assigns

		this._bufferSize = bufferSize;
		this._lightIndexes = lightIndexes;
		this._screenTileIndex = screenTileIndex;
		this._compute = compute;
		this._lightsTexture = lightsTexture;

	}
```
</details>

### `getBlock(index: any): any`

**Parameters:**

- **`index`** `any`

**Returns:** `any`

**Calls:**

- `instanceIndex.mul( int( 2 ) ).add`
- `int (from three/tsl)`
- `lightIndexes.element`

<details><summary>Code</summary>

```typescript
( index ) => {

			const tileIndex = instanceIndex.mul( int( 2 ) ).add( int( index ) );

			return lightIndexes.element( tileIndex );

		}
```
</details>

### `getTile(elementIndex: any): any`

**Parameters:**

- **`elementIndex`** `any`

**Returns:** `any`

**Calls:**

- `int (from three/tsl)`
- `elementIndex.div`
- `instanceIndex.mul( int( 2 ) ).add`
- `lightIndexes.element( tileIndex ).element`
- `elementIndex.mod`

<details><summary>Code</summary>

```typescript
( elementIndex ) => {

			elementIndex = int( elementIndex );

			const stride = int( 4 );
			const tileOffset = elementIndex.div( stride );
			const tileIndex = instanceIndex.mul( int( 2 ) ).add( tileOffset );

			return lightIndexes.element( tileIndex ).element( elementIndex.mod( stride ) );

		}
```
</details>


---

## Classes

### `TiledLightsNode`

<details><summary>Class Code</summary>

```ts
class TiledLightsNode extends LightsNode {

	static get type() {

		return 'TiledLightsNode';

	}

	/**
	 * Constructs a new tiled lights node.
	 *
	 * @param {number} [maxLights=1024] - The maximum number of lights.
	 * @param {number} [tileSize=32] - The tile size.
	 */
	constructor( maxLights = 1024, tileSize = 32 ) {

		super();

		this.materialLights = [];
		this.tiledLights = [];

		/**
		 * The maximum number of lights.
		 *
		 * @type {number}
		 * @default 1024
		 */
		this.maxLights = maxLights;

		/**
		 * The tile size.
		 *
		 * @type {number}
		 * @default 32
		 */
		this.tileSize = tileSize;

		this._bufferSize = null;
		this._lightIndexes = null;
		this._screenTileIndex = null;
		this._compute = null;
		this._lightsTexture = null;

		this._lightsCount = uniform( 0, 'int' );
		this._tileLightCount = 8;
		this._screenSize = uniform( new Vector2() );
		this._cameraProjectionMatrix = uniform( 'mat4' );
		this._cameraViewMatrix = uniform( 'mat4' );

		this.updateBeforeType = NodeUpdateType.RENDER;

	}

	customCacheKey() {

		return this._compute.getCacheKey() + super.customCacheKey();

	}

	updateLightsTexture() {

		const { _lightsTexture: lightsTexture, tiledLights } = this;

		const data = lightsTexture.image.data;
		const lineSize = lightsTexture.image.width * 4;

		this._lightsCount.value = tiledLights.length;

		for ( let i = 0; i < tiledLights.length; i ++ ) {

			const light = tiledLights[ i ];

			// world position

			_vector3.setFromMatrixPosition( light.matrixWorld );

			// store data

			const offset = i * 4;

			data[ offset + 0 ] = _vector3.x;
			data[ offset + 1 ] = _vector3.y;
			data[ offset + 2 ] = _vector3.z;
			data[ offset + 3 ] = light.distance;

			data[ lineSize + offset + 0 ] = light.color.r * light.intensity;
			data[ lineSize + offset + 1 ] = light.color.g * light.intensity;
			data[ lineSize + offset + 2 ] = light.color.b * light.intensity;
			data[ lineSize + offset + 3 ] = light.decay;

		}

		lightsTexture.needsUpdate = true;

	}

	updateBefore( frame ) {

		const { renderer, camera } = frame;

		this.updateProgram( renderer );

		this.updateLightsTexture( camera );

		this._cameraProjectionMatrix.value = camera.projectionMatrix;
		this._cameraViewMatrix.value = camera.matrixWorldInverse;

		renderer.getDrawingBufferSize( _size );
		this._screenSize.value.copy( _size );

		renderer.compute( this._compute );

	}

	setLights( lights ) {

		const { tiledLights, materialLights } = this;

		let materialindex = 0;
		let tiledIndex = 0;

		for ( const light of lights ) {

			if ( light.isPointLight === true ) {

				tiledLights[ tiledIndex ++ ] = light;

			} else {

				materialLights[ materialindex ++ ] = light;

			}

		}

		materialLights.length = materialindex;
		tiledLights.length = tiledIndex;

		return super.setLights( materialLights );

	}

	getBlock( block = 0 ) {

		return this._lightIndexes.element( this._screenTileIndex.mul( int( 2 ).add( int( block ) ) ) );

	}

	getTile( element ) {

		element = int( element );

		const stride = int( 4 );
		const tileOffset = element.div( stride );
		const tileIndex = this._screenTileIndex.mul( int( 2 ) ).add( tileOffset );

		return this._lightIndexes.element( tileIndex ).element( element.mod( stride ) );

	}

	getLightData( index ) {

		index = int( index );

		const dataA = textureLoad( this._lightsTexture, ivec2( index, 0 ) );
		const dataB = textureLoad( this._lightsTexture, ivec2( index, 1 ) );

		const position = dataA.xyz;
		const viewPosition = this._cameraViewMatrix.mul( position );
		const distance = dataA.w;
		const color = dataB.rgb;
		const decay = dataB.w;

		return {
			position,
			viewPosition,
			distance,
			color,
			decay
		};

	}

	setupLights( builder, lightNodes ) {

		this.updateProgram( builder.renderer );

		//

		const lightingModel = builder.context.reflectedLight;

		// force declaration order, before of the loop
		lightingModel.directDiffuse.toStack();
		lightingModel.directSpecular.toStack();

		super.setupLights( builder, lightNodes );

		Fn( () => {

			Loop( this._tileLightCount, ( { i } ) => {

				const lightIndex = this.getTile( i );

				If( lightIndex.equal( int( 0 ) ), () => {

					Break();

				} );

				const { color, decay, viewPosition, distance } = this.getLightData( lightIndex.sub( 1 ) );

				builder.lightsNode.setupDirectLight( builder, this, directPointLight( {
					color,
					lightVector: viewPosition.sub( positionView ),
					cutoffDistance: distance,
					decayExponent: decay
				} ) );

			} );

		}, 'void' )();

	}

	getBufferFitSize( value ) {

		const multiple = this.tileSize;

		return Math.ceil( value / multiple ) * multiple;

	}

	setSize( width, height ) {

		width = this.getBufferFitSize( width );
		height = this.getBufferFitSize( height );

		if ( ! this._bufferSize || this._bufferSize.width !== width || this._bufferSize.height !== height ) {

			this.create( width, height );

		}

		return this;

	}

	updateProgram( renderer ) {

		renderer.getDrawingBufferSize( _size );

		const width = this.getBufferFitSize( _size.width );
		const height = this.getBufferFitSize( _size.height );

		if ( this._bufferSize === null ) {

			this.create( width, height );

		} else if ( this._bufferSize.width !== width || this._bufferSize.height !== height ) {

			this.create( width, height );

		}

	}

	create( width, height ) {

		const { tileSize, maxLights } = this;

		const bufferSize = new Vector2( width, height );
		const lineSize = Math.floor( bufferSize.width / tileSize );
		const count = Math.floor( ( bufferSize.width * bufferSize.height ) / tileSize );

		// buffers

		const lightsData = new Float32Array( maxLights * 4 * 2 ); // 2048 lights, 4 elements(rgba), 2 components, 1 component per line (position, distance, color, decay)
		const lightsTexture = new DataTexture( lightsData, lightsData.length / 8, 2, RGBAFormat, FloatType );

		const lightIndexesArray = new Int32Array( count * 4 * 2 );
		const lightIndexes = attributeArray( lightIndexesArray, 'ivec4' ).setName( 'lightIndexes' );

		// compute

		const getBlock = ( index ) => {

			const tileIndex = instanceIndex.mul( int( 2 ) ).add( int( index ) );

			return lightIndexes.element( tileIndex );

		};

		const getTile = ( elementIndex ) => {

			elementIndex = int( elementIndex );

			const stride = int( 4 );
			const tileOffset = elementIndex.div( stride );
			const tileIndex = instanceIndex.mul( int( 2 ) ).add( tileOffset );

			return lightIndexes.element( tileIndex ).element( elementIndex.mod( stride ) );

		};

		const compute = Fn( () => {

			const { _cameraProjectionMatrix: cameraProjectionMatrix, _bufferSize: bufferSize, _screenSize: screenSize } = this;

			const tiledBufferSize = bufferSize.clone().divideScalar( tileSize ).floor();

			const tileScreen = vec2(
				instanceIndex.mod( tiledBufferSize.width ),
				instanceIndex.div( tiledBufferSize.width )
			).mul( tileSize ).div( screenSize );

			const blockSize = float( tileSize ).div( screenSize );
			const minBounds = tileScreen;
			const maxBounds = minBounds.add( blockSize );

			const index = int( 0 ).toVar();

			getBlock( 0 ).assign( ivec4( 0 ) );
			getBlock( 1 ).assign( ivec4( 0 ) );

			Loop( this.maxLights, ( { i } ) => {

				If( index.greaterThanEqual( this._tileLightCount ).or( int( i ).greaterThanEqual( int( this._lightsCount ) ) ), () => {

					Return();

				} );

				const { viewPosition, distance } = this.getLightData( i );

				const projectedPosition = cameraProjectionMatrix.mul( viewPosition );
				const ndc = projectedPosition.div( projectedPosition.w );
				const screenPosition = ndc.xy.mul( 0.5 ).add( 0.5 ).flipY();

				const distanceFromCamera = viewPosition.z;
				const pointRadius = distance.div( distanceFromCamera );

				If( circleIntersectsAABB( screenPosition, pointRadius, minBounds, maxBounds ), () => {

					getTile( index ).assign( i.add( int( 1 ) ) );
					index.addAssign( int( 1 ) );

				} );

			} );

		} )().compute( count );

		// screen coordinate lighting indexes

		const screenTile = screenCoordinate.div( tileSize ).floor().toVar();
		const screenTileIndex = screenTile.x.add( screenTile.y.mul( lineSize ) );

		// assigns

		this._bufferSize = bufferSize;
		this._lightIndexes = lightIndexes;
		this._screenTileIndex = screenTileIndex;
		this._compute = compute;
		this._lightsTexture = lightsTexture;

	}

	get hasLights() {

		return super.hasLights || this.tiledLights.length > 0;

	}

}
```
</details>

#### Methods

##### `customCacheKey(): any`

<details><summary>Code</summary>

```ts
customCacheKey() {

		return this._compute.getCacheKey() + super.customCacheKey();

	}
```
</details>

##### `updateLightsTexture(): void`

<details><summary>Code</summary>

```ts
updateLightsTexture() {

		const { _lightsTexture: lightsTexture, tiledLights } = this;

		const data = lightsTexture.image.data;
		const lineSize = lightsTexture.image.width * 4;

		this._lightsCount.value = tiledLights.length;

		for ( let i = 0; i < tiledLights.length; i ++ ) {

			const light = tiledLights[ i ];

			// world position

			_vector3.setFromMatrixPosition( light.matrixWorld );

			// store data

			const offset = i * 4;

			data[ offset + 0 ] = _vector3.x;
			data[ offset + 1 ] = _vector3.y;
			data[ offset + 2 ] = _vector3.z;
			data[ offset + 3 ] = light.distance;

			data[ lineSize + offset + 0 ] = light.color.r * light.intensity;
			data[ lineSize + offset + 1 ] = light.color.g * light.intensity;
			data[ lineSize + offset + 2 ] = light.color.b * light.intensity;
			data[ lineSize + offset + 3 ] = light.decay;

		}

		lightsTexture.needsUpdate = true;

	}
```
</details>

##### `updateBefore(frame: any): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer, camera } = frame;

		this.updateProgram( renderer );

		this.updateLightsTexture( camera );

		this._cameraProjectionMatrix.value = camera.projectionMatrix;
		this._cameraViewMatrix.value = camera.matrixWorldInverse;

		renderer.getDrawingBufferSize( _size );
		this._screenSize.value.copy( _size );

		renderer.compute( this._compute );

	}
```
</details>

##### `setLights(lights: any): any`

<details><summary>Code</summary>

```ts
setLights( lights ) {

		const { tiledLights, materialLights } = this;

		let materialindex = 0;
		let tiledIndex = 0;

		for ( const light of lights ) {

			if ( light.isPointLight === true ) {

				tiledLights[ tiledIndex ++ ] = light;

			} else {

				materialLights[ materialindex ++ ] = light;

			}

		}

		materialLights.length = materialindex;
		tiledLights.length = tiledIndex;

		return super.setLights( materialLights );

	}
```
</details>

##### `getBlock(block: number): any`

<details><summary>Code</summary>

```ts
getBlock( block = 0 ) {

		return this._lightIndexes.element( this._screenTileIndex.mul( int( 2 ).add( int( block ) ) ) );

	}
```
</details>

##### `getTile(element: any): any`

<details><summary>Code</summary>

```ts
getTile( element ) {

		element = int( element );

		const stride = int( 4 );
		const tileOffset = element.div( stride );
		const tileIndex = this._screenTileIndex.mul( int( 2 ) ).add( tileOffset );

		return this._lightIndexes.element( tileIndex ).element( element.mod( stride ) );

	}
```
</details>

##### `getLightData(index: any): { position: any; viewPosition: any; distance: any; color: any; decay: any; }`

<details><summary>Code</summary>

```ts
getLightData( index ) {

		index = int( index );

		const dataA = textureLoad( this._lightsTexture, ivec2( index, 0 ) );
		const dataB = textureLoad( this._lightsTexture, ivec2( index, 1 ) );

		const position = dataA.xyz;
		const viewPosition = this._cameraViewMatrix.mul( position );
		const distance = dataA.w;
		const color = dataB.rgb;
		const decay = dataB.w;

		return {
			position,
			viewPosition,
			distance,
			color,
			decay
		};

	}
```
</details>

##### `setupLights(builder: any, lightNodes: any): void`

<details><summary>Code</summary>

```ts
setupLights( builder, lightNodes ) {

		this.updateProgram( builder.renderer );

		//

		const lightingModel = builder.context.reflectedLight;

		// force declaration order, before of the loop
		lightingModel.directDiffuse.toStack();
		lightingModel.directSpecular.toStack();

		super.setupLights( builder, lightNodes );

		Fn( () => {

			Loop( this._tileLightCount, ( { i } ) => {

				const lightIndex = this.getTile( i );

				If( lightIndex.equal( int( 0 ) ), () => {

					Break();

				} );

				const { color, decay, viewPosition, distance } = this.getLightData( lightIndex.sub( 1 ) );

				builder.lightsNode.setupDirectLight( builder, this, directPointLight( {
					color,
					lightVector: viewPosition.sub( positionView ),
					cutoffDistance: distance,
					decayExponent: decay
				} ) );

			} );

		}, 'void' )();

	}
```
</details>

##### `getBufferFitSize(value: any): number`

<details><summary>Code</summary>

```ts
getBufferFitSize( value ) {

		const multiple = this.tileSize;

		return Math.ceil( value / multiple ) * multiple;

	}
```
</details>

##### `setSize(width: any, height: any): this`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		width = this.getBufferFitSize( width );
		height = this.getBufferFitSize( height );

		if ( ! this._bufferSize || this._bufferSize.width !== width || this._bufferSize.height !== height ) {

			this.create( width, height );

		}

		return this;

	}
```
</details>

##### `updateProgram(renderer: any): void`

<details><summary>Code</summary>

```ts
updateProgram( renderer ) {

		renderer.getDrawingBufferSize( _size );

		const width = this.getBufferFitSize( _size.width );
		const height = this.getBufferFitSize( _size.height );

		if ( this._bufferSize === null ) {

			this.create( width, height );

		} else if ( this._bufferSize.width !== width || this._bufferSize.height !== height ) {

			this.create( width, height );

		}

	}
```
</details>

##### `create(width: any, height: any): void`

<details><summary>Code</summary>

```ts
create( width, height ) {

		const { tileSize, maxLights } = this;

		const bufferSize = new Vector2( width, height );
		const lineSize = Math.floor( bufferSize.width / tileSize );
		const count = Math.floor( ( bufferSize.width * bufferSize.height ) / tileSize );

		// buffers

		const lightsData = new Float32Array( maxLights * 4 * 2 ); // 2048 lights, 4 elements(rgba), 2 components, 1 component per line (position, distance, color, decay)
		const lightsTexture = new DataTexture( lightsData, lightsData.length / 8, 2, RGBAFormat, FloatType );

		const lightIndexesArray = new Int32Array( count * 4 * 2 );
		const lightIndexes = attributeArray( lightIndexesArray, 'ivec4' ).setName( 'lightIndexes' );

		// compute

		const getBlock = ( index ) => {

			const tileIndex = instanceIndex.mul( int( 2 ) ).add( int( index ) );

			return lightIndexes.element( tileIndex );

		};

		const getTile = ( elementIndex ) => {

			elementIndex = int( elementIndex );

			const stride = int( 4 );
			const tileOffset = elementIndex.div( stride );
			const tileIndex = instanceIndex.mul( int( 2 ) ).add( tileOffset );

			return lightIndexes.element( tileIndex ).element( elementIndex.mod( stride ) );

		};

		const compute = Fn( () => {

			const { _cameraProjectionMatrix: cameraProjectionMatrix, _bufferSize: bufferSize, _screenSize: screenSize } = this;

			const tiledBufferSize = bufferSize.clone().divideScalar( tileSize ).floor();

			const tileScreen = vec2(
				instanceIndex.mod( tiledBufferSize.width ),
				instanceIndex.div( tiledBufferSize.width )
			).mul( tileSize ).div( screenSize );

			const blockSize = float( tileSize ).div( screenSize );
			const minBounds = tileScreen;
			const maxBounds = minBounds.add( blockSize );

			const index = int( 0 ).toVar();

			getBlock( 0 ).assign( ivec4( 0 ) );
			getBlock( 1 ).assign( ivec4( 0 ) );

			Loop( this.maxLights, ( { i } ) => {

				If( index.greaterThanEqual( this._tileLightCount ).or( int( i ).greaterThanEqual( int( this._lightsCount ) ) ), () => {

					Return();

				} );

				const { viewPosition, distance } = this.getLightData( i );

				const projectedPosition = cameraProjectionMatrix.mul( viewPosition );
				const ndc = projectedPosition.div( projectedPosition.w );
				const screenPosition = ndc.xy.mul( 0.5 ).add( 0.5 ).flipY();

				const distanceFromCamera = viewPosition.z;
				const pointRadius = distance.div( distanceFromCamera );

				If( circleIntersectsAABB( screenPosition, pointRadius, minBounds, maxBounds ), () => {

					getTile( index ).assign( i.add( int( 1 ) ) );
					index.addAssign( int( 1 ) );

				} );

			} );

		} )().compute( count );

		// screen coordinate lighting indexes

		const screenTile = screenCoordinate.div( tileSize ).floor().toVar();
		const screenTileIndex = screenTile.x.add( screenTile.y.mul( lineSize ) );

		// assigns

		this._bufferSize = bufferSize;
		this._lightIndexes = lightIndexes;
		this._screenTileIndex = screenTileIndex;
		this._compute = compute;
		this._lightsTexture = lightsTexture;

	}
```
</details>


---