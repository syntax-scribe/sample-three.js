[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `TileShadowNodeHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 15 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/shadows/TileShadowNodeHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Group` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `Mesh` | `three/webgpu` |
| `PlaneGeometry` | `three/webgpu` |
| `DoubleSide` | `three/webgpu` |
| `CameraHelper` | `three/webgpu` |
| `Fn` | `three/tsl` |
| `vec4` | `three/tsl` |
| `vec3` | `three/tsl` |
| `texture` | `three/tsl` |
| `uv` | `three/tsl` |
| `positionLocal` | `three/tsl` |
| `vec2` | `three/tsl` |
| `float` | `three/tsl` |
| `screenSize` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `tilesX` | `any` | let/var | `this.config.tilesX` | ✗ |
| `tilesY` | `any` | let/var | `this.config.tilesY` | ✗ |
| `display` | `any` | let/var | `new Mesh( new PlaneGeometry( 1, 1 ), new NodeMaterial() )` | ✗ |
| `col` | `number` | let/var | `i % tilesX` | ✗ |
| `camHelper` | `any` | let/var | `new CameraHelper( this.tileShadowNode._shadowNodes[ i ].shadow.camera )` | ✗ |


---

## Functions

### `TileShadowNodeHelper.init(): void`

**JSDoc:**
```typescript
/**
	 * Initializes the debug displays (planes and camera helpers).
	 * Should be called after TileShadowNode has initialized its lights and shadow nodes.
	 */
```

**Returns:** `void`

**Calls:**

- `console.error`
- `this.dispose`
- `Math.floor`
- `complex_call_2097`
- `complex_call_3082`
- `this.add`
- `this._debugMeshes.push`
- `this._shadowCamHelpers.push`
- `console.warn`

**Internal Comments:**
```
// Clear previous helpers if any (e.g., during a re-init) (x4)
// Create a display for each shadow map tile
// Create display plane (x2)
// Vertex shader logic for positioning the debug quad (x5)
// Position tiles left-to-right, top-to-bottom (x2)
// Ensure shadowMap and depthTexture are available
// Simple tint based on index for visual distinction (x2)
```

<details><summary>Code</summary>

```typescript
init() {

		if ( this.tileShadowNode._shadowNodes.length !== this.tiles.length ) {

			console.error( 'Cannot initialize TileShadowNodeHelper: Shadow nodes not ready or mismatch count.' );
			return;

		}

		const tilesX = this.config.tilesX;
		const tilesY = this.config.tilesY;

		// Clear previous helpers if any (e.g., during a re-init)
		this.dispose();

		// Create a display for each shadow map tile
		for ( let i = 0; i < this.tiles.length; i ++ ) {

			// Create display plane
			const display = new Mesh( new PlaneGeometry( 1, 1 ), new NodeMaterial() );
			display.renderOrder = 9999999; // Ensure they appear on top
			display.material.transparent = true;
			display.frustumCulled = false;
			display.side = DoubleSide;
			display.material.depthTest = false; // Disable depth testing
			display.material.depthWrite = false; // Disable depth writing

			const col = i % tilesX;
			const row = Math.floor( i / tilesX );

			// Vertex shader logic for positioning the debug quad
			display.material.vertexNode = Fn( () => {

				const aspectRatio = screenSize.x.div( screenSize.y );
				const maxTiles = Math.max( tilesX, tilesY );
				const displaySize = float( 0.8 / maxTiles ); // Size adapts to number of tiles
				const margin = float( 0.01 );
				const cornerOffset = float( 0.05 );

				// Position tiles left-to-right, top-to-bottom
				const xBase = float( - 1.0 ).add( cornerOffset ).add(
					displaySize.div( 2 ).div( aspectRatio )
				).add( float( col ).mul( displaySize.div( aspectRatio ).add( margin ) ) );

				const yBase = float( 1.0 ).sub( cornerOffset ).sub(
					displaySize.div( 2 )
				).sub( float( row ).mul( displaySize.add( margin ) ) );

				const scaledPos = vec2(
					positionLocal.x.mul( displaySize.div( aspectRatio ) ),
					positionLocal.y.mul( displaySize )
				);

				const finalPos = vec2(
					scaledPos.x.add( xBase ),
					scaledPos.y.add( yBase )
				);

				return vec4( finalPos.x, finalPos.y, 0.0, 1.0 );

			} )();

			display.material.outputNode = Fn( () => {

				// Ensure shadowMap and depthTexture are available
				if ( ! this.tileShadowNode.shadowMap || ! this.tileShadowNode.shadowMap.depthTexture ) {

					return vec4( 1, 0, 1, 1 ); // Magenta error color

				}

				const sampledDepth = texture( this.tileShadowNode.shadowMap.depthTexture )
					.sample( uv().flipY() )
					.depth( float( i ) ) // Sample correct layer
					.compare( 0.9 ); // Example comparison value

				// Simple tint based on index for visual distinction
				const r = float( 0.5 + ( i % 3 ) * 0.16 );
				const g = float( 0.5 + ( i % 2 ) * 0.25 );
				const b = float( 0.7 + ( i % 4 ) * 0.075 );

				return vec4(
					vec3( r, g, b )
						.mul( sampledDepth )
						.saturate()
						.rgb,
					1.0
				);

			} )();

			this.add( display );
			this._debugMeshes.push( display );

			if ( this.tileShadowNode._shadowNodes[ i ] && this.tileShadowNode._shadowNodes[ i ].shadow ) {

				const camHelper = new CameraHelper( this.tileShadowNode._shadowNodes[ i ].shadow.camera );
				camHelper.fog = false;
				this.add( camHelper );
				this._shadowCamHelpers.push( camHelper );

			} else {

				console.warn( `TileShadowNodeHelper: Could not create CameraHelper for tile index ${i}. Shadow node or camera missing.` );
				this._shadowCamHelpers.push( null );

			}

		}

		this.initialized = true;

	}
```
</details>

### `TileShadowNodeHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the debug visuals (specifically camera helpers).
	 * Should be called within TileShadowNode's update method.
	 */
```

**Returns:** `void`

**Calls:**

- `this.init`
- `helper.update`
- `helper.updateMatrixWorld`

<details><summary>Code</summary>

```typescript
update() {

		if ( this.initialized === false ) {

			this.init();

		}

		for ( const helper of this._shadowCamHelpers ) {

			if ( helper ) {

				helper.update(); // Update CameraHelper matrices
				helper.updateMatrixWorld( true ); // Ensure world matrix is current

			}

		}

	}
```
</details>

### `TileShadowNodeHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Removes all debug objects (planes and helpers) from the scene.
	 */
```

**Returns:** `void`

**Calls:**

- `mesh.geometry.dispose`
- `mesh.material.dispose`
- `this.scene.remove`

<details><summary>Code</summary>

```typescript
dispose() {

		if ( this.scene ) {

			for ( const mesh of this._debugMeshes ) {

				mesh.geometry.dispose();
				mesh.material.dispose();
				this.scene.remove( mesh );

			}

			for ( const helper of this._shadowCamHelpers ) {

				if ( helper ) {

					this.scene.remove( helper );

				}

			}

		}

		this._debugMeshes = [];
		this._shadowCamHelpers = [];

	}
```
</details>


---

## Classes

### `TileShadowNodeHelper`

<details><summary>Class Code</summary>

```ts
class TileShadowNodeHelper extends Group {

	/**
	 * @param {TileShadowNode} tileShadowNode The TileShadowNode instance to debug.
	 */
	constructor( tileShadowNode ) {

		super();

		if ( ! tileShadowNode ) {

			throw new Error( 'TileShadowNode instance is required for TileShadowNodeHelper.' );

		}

		this.tileShadowNode = tileShadowNode;
		this.config = tileShadowNode.config;
		this.tiles = tileShadowNode.tiles;
		this._debugMeshes = [];
		this._shadowCamHelpers = [];

		this.initialized = false;

	}

	/**
	 * Initializes the debug displays (planes and camera helpers).
	 * Should be called after TileShadowNode has initialized its lights and shadow nodes.
	 */
	init() {

		if ( this.tileShadowNode._shadowNodes.length !== this.tiles.length ) {

			console.error( 'Cannot initialize TileShadowNodeHelper: Shadow nodes not ready or mismatch count.' );
			return;

		}

		const tilesX = this.config.tilesX;
		const tilesY = this.config.tilesY;

		// Clear previous helpers if any (e.g., during a re-init)
		this.dispose();

		// Create a display for each shadow map tile
		for ( let i = 0; i < this.tiles.length; i ++ ) {

			// Create display plane
			const display = new Mesh( new PlaneGeometry( 1, 1 ), new NodeMaterial() );
			display.renderOrder = 9999999; // Ensure they appear on top
			display.material.transparent = true;
			display.frustumCulled = false;
			display.side = DoubleSide;
			display.material.depthTest = false; // Disable depth testing
			display.material.depthWrite = false; // Disable depth writing

			const col = i % tilesX;
			const row = Math.floor( i / tilesX );

			// Vertex shader logic for positioning the debug quad
			display.material.vertexNode = Fn( () => {

				const aspectRatio = screenSize.x.div( screenSize.y );
				const maxTiles = Math.max( tilesX, tilesY );
				const displaySize = float( 0.8 / maxTiles ); // Size adapts to number of tiles
				const margin = float( 0.01 );
				const cornerOffset = float( 0.05 );

				// Position tiles left-to-right, top-to-bottom
				const xBase = float( - 1.0 ).add( cornerOffset ).add(
					displaySize.div( 2 ).div( aspectRatio )
				).add( float( col ).mul( displaySize.div( aspectRatio ).add( margin ) ) );

				const yBase = float( 1.0 ).sub( cornerOffset ).sub(
					displaySize.div( 2 )
				).sub( float( row ).mul( displaySize.add( margin ) ) );

				const scaledPos = vec2(
					positionLocal.x.mul( displaySize.div( aspectRatio ) ),
					positionLocal.y.mul( displaySize )
				);

				const finalPos = vec2(
					scaledPos.x.add( xBase ),
					scaledPos.y.add( yBase )
				);

				return vec4( finalPos.x, finalPos.y, 0.0, 1.0 );

			} )();

			display.material.outputNode = Fn( () => {

				// Ensure shadowMap and depthTexture are available
				if ( ! this.tileShadowNode.shadowMap || ! this.tileShadowNode.shadowMap.depthTexture ) {

					return vec4( 1, 0, 1, 1 ); // Magenta error color

				}

				const sampledDepth = texture( this.tileShadowNode.shadowMap.depthTexture )
					.sample( uv().flipY() )
					.depth( float( i ) ) // Sample correct layer
					.compare( 0.9 ); // Example comparison value

				// Simple tint based on index for visual distinction
				const r = float( 0.5 + ( i % 3 ) * 0.16 );
				const g = float( 0.5 + ( i % 2 ) * 0.25 );
				const b = float( 0.7 + ( i % 4 ) * 0.075 );

				return vec4(
					vec3( r, g, b )
						.mul( sampledDepth )
						.saturate()
						.rgb,
					1.0
				);

			} )();

			this.add( display );
			this._debugMeshes.push( display );

			if ( this.tileShadowNode._shadowNodes[ i ] && this.tileShadowNode._shadowNodes[ i ].shadow ) {

				const camHelper = new CameraHelper( this.tileShadowNode._shadowNodes[ i ].shadow.camera );
				camHelper.fog = false;
				this.add( camHelper );
				this._shadowCamHelpers.push( camHelper );

			} else {

				console.warn( `TileShadowNodeHelper: Could not create CameraHelper for tile index ${i}. Shadow node or camera missing.` );
				this._shadowCamHelpers.push( null );

			}

		}

		this.initialized = true;

	}

	/**
	 * Updates the debug visuals (specifically camera helpers).
	 * Should be called within TileShadowNode's update method.
	 */
	update() {

		if ( this.initialized === false ) {

			this.init();

		}

		for ( const helper of this._shadowCamHelpers ) {

			if ( helper ) {

				helper.update(); // Update CameraHelper matrices
				helper.updateMatrixWorld( true ); // Ensure world matrix is current

			}

		}

	}

	/**
	 * Removes all debug objects (planes and helpers) from the scene.
	 */
	dispose() {

		if ( this.scene ) {

			for ( const mesh of this._debugMeshes ) {

				mesh.geometry.dispose();
				mesh.material.dispose();
				this.scene.remove( mesh );

			}

			for ( const helper of this._shadowCamHelpers ) {

				if ( helper ) {

					this.scene.remove( helper );

				}

			}

		}

		this._debugMeshes = [];
		this._shadowCamHelpers = [];

	}

}
```
</details>

#### Methods

##### `init(): void`

<details><summary>Code</summary>

```ts
init() {

		if ( this.tileShadowNode._shadowNodes.length !== this.tiles.length ) {

			console.error( 'Cannot initialize TileShadowNodeHelper: Shadow nodes not ready or mismatch count.' );
			return;

		}

		const tilesX = this.config.tilesX;
		const tilesY = this.config.tilesY;

		// Clear previous helpers if any (e.g., during a re-init)
		this.dispose();

		// Create a display for each shadow map tile
		for ( let i = 0; i < this.tiles.length; i ++ ) {

			// Create display plane
			const display = new Mesh( new PlaneGeometry( 1, 1 ), new NodeMaterial() );
			display.renderOrder = 9999999; // Ensure they appear on top
			display.material.transparent = true;
			display.frustumCulled = false;
			display.side = DoubleSide;
			display.material.depthTest = false; // Disable depth testing
			display.material.depthWrite = false; // Disable depth writing

			const col = i % tilesX;
			const row = Math.floor( i / tilesX );

			// Vertex shader logic for positioning the debug quad
			display.material.vertexNode = Fn( () => {

				const aspectRatio = screenSize.x.div( screenSize.y );
				const maxTiles = Math.max( tilesX, tilesY );
				const displaySize = float( 0.8 / maxTiles ); // Size adapts to number of tiles
				const margin = float( 0.01 );
				const cornerOffset = float( 0.05 );

				// Position tiles left-to-right, top-to-bottom
				const xBase = float( - 1.0 ).add( cornerOffset ).add(
					displaySize.div( 2 ).div( aspectRatio )
				).add( float( col ).mul( displaySize.div( aspectRatio ).add( margin ) ) );

				const yBase = float( 1.0 ).sub( cornerOffset ).sub(
					displaySize.div( 2 )
				).sub( float( row ).mul( displaySize.add( margin ) ) );

				const scaledPos = vec2(
					positionLocal.x.mul( displaySize.div( aspectRatio ) ),
					positionLocal.y.mul( displaySize )
				);

				const finalPos = vec2(
					scaledPos.x.add( xBase ),
					scaledPos.y.add( yBase )
				);

				return vec4( finalPos.x, finalPos.y, 0.0, 1.0 );

			} )();

			display.material.outputNode = Fn( () => {

				// Ensure shadowMap and depthTexture are available
				if ( ! this.tileShadowNode.shadowMap || ! this.tileShadowNode.shadowMap.depthTexture ) {

					return vec4( 1, 0, 1, 1 ); // Magenta error color

				}

				const sampledDepth = texture( this.tileShadowNode.shadowMap.depthTexture )
					.sample( uv().flipY() )
					.depth( float( i ) ) // Sample correct layer
					.compare( 0.9 ); // Example comparison value

				// Simple tint based on index for visual distinction
				const r = float( 0.5 + ( i % 3 ) * 0.16 );
				const g = float( 0.5 + ( i % 2 ) * 0.25 );
				const b = float( 0.7 + ( i % 4 ) * 0.075 );

				return vec4(
					vec3( r, g, b )
						.mul( sampledDepth )
						.saturate()
						.rgb,
					1.0
				);

			} )();

			this.add( display );
			this._debugMeshes.push( display );

			if ( this.tileShadowNode._shadowNodes[ i ] && this.tileShadowNode._shadowNodes[ i ].shadow ) {

				const camHelper = new CameraHelper( this.tileShadowNode._shadowNodes[ i ].shadow.camera );
				camHelper.fog = false;
				this.add( camHelper );
				this._shadowCamHelpers.push( camHelper );

			} else {

				console.warn( `TileShadowNodeHelper: Could not create CameraHelper for tile index ${i}. Shadow node or camera missing.` );
				this._shadowCamHelpers.push( null );

			}

		}

		this.initialized = true;

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		if ( this.initialized === false ) {

			this.init();

		}

		for ( const helper of this._shadowCamHelpers ) {

			if ( helper ) {

				helper.update(); // Update CameraHelper matrices
				helper.updateMatrixWorld( true ); // Ensure world matrix is current

			}

		}

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		if ( this.scene ) {

			for ( const mesh of this._debugMeshes ) {

				mesh.geometry.dispose();
				mesh.material.dispose();
				this.scene.remove( mesh );

			}

			for ( const helper of this._shadowCamHelpers ) {

				if ( helper ) {

					this.scene.remove( helper );

				}

			}

		}

		this._debugMeshes = [];
		this._shadowCamHelpers = [];

	}
```
</details>


---