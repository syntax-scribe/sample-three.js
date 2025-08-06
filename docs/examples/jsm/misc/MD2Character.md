[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MD2Character.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/misc/MD2Character.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationMixer` | `three` |
| `Box3` | `three` |
| `Mesh` | `three` |
| `MeshLambertMaterial` | `three` |
| `Object3D` | `three` |
| `TextureLoader` | `three` |
| `UVMapping` | `three` |
| `SRGBColorSpace` | `three` |
| `MD2Loader` | `../loaders/MD2Loader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `materialWireframe` | `any` | let/var | `new MeshLambertMaterial( { color: 0xffaa00, wireframe: true } )` | ✗ |
| `materialTexture` | `any` | let/var | `new MeshLambertMaterial( { color: 0xffffff, wireframe: false, map: skinMap } )` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( geometry, materialTexture )` | ✗ |
| `textureLoader` | `any` | let/var | `new TextureLoader()` | ✗ |
| `textures` | `any[]` | let/var | `[]` | ✗ |
| `weaponsTextures` | `any[]` | let/var | `[]` | ✗ |
| `loader` | `MD2Loader` | let/var | `new MD2Loader()` | ✗ |
| `boundingBox` | `any` | let/var | `new Box3()` | ✗ |
| `activeWeapon` | `Mesh` | let/var | `this.weapons[ index ]` | ✗ |
| `clipName` | `string` | let/var | `this.activeClipName` | ✗ |


---

## Functions

### `MD2Character.loadParts(config: any): void`

**JSDoc:**
```typescript
/**
	 * Loads the character model for the given config.
	 *
	 * @param {Object} config - The config which defines the model and textures paths.
	 */
```

**Parameters:**

- **`config`** `any`

**Returns:** `void`

**Calls:**

- `textureLoader.load`
- `scope.onLoadComplete`
- `loadTextures`
- `loader.load`
- `boundingBox.setFromBufferAttribute`
- `createPart`
- `mesh.scale.set`
- `scope.root.add`
- `checkLoadingComplete`
- `generateCallback`

**Internal Comments:**
```
// (x6)
// SKINS (x4)
// BODY (x2)
// WEAPONS (x2)
```

<details><summary>Code</summary>

```typescript
loadParts( config ) {

		const scope = this;

		function createPart( geometry, skinMap ) {

			const materialWireframe = new MeshLambertMaterial( { color: 0xffaa00, wireframe: true } );
			const materialTexture = new MeshLambertMaterial( { color: 0xffffff, wireframe: false, map: skinMap } );

			//

			const mesh = new Mesh( geometry, materialTexture );
			mesh.rotation.y = - Math.PI / 2;

			mesh.castShadow = true;
			mesh.receiveShadow = true;

			//

			mesh.materialTexture = materialTexture;
			mesh.materialWireframe = materialWireframe;

			return mesh;

		}

		function loadTextures( baseUrl, textureUrls ) {

			const textureLoader = new TextureLoader();
			const textures = [];

			for ( let i = 0; i < textureUrls.length; i ++ ) {

				textures[ i ] = textureLoader.load( baseUrl + textureUrls[ i ], checkLoadingComplete );
				textures[ i ].mapping = UVMapping;
				textures[ i ].name = textureUrls[ i ];
				textures[ i ].colorSpace = SRGBColorSpace;

			}

			return textures;

		}

		function checkLoadingComplete() {

			scope.loadCounter -= 1;

			if ( scope.loadCounter === 0 ) scope.onLoadComplete();

		}

		this.loadCounter = config.weapons.length * 2 + config.skins.length + 1;

		const weaponsTextures = [];
		for ( let i = 0; i < config.weapons.length; i ++ ) weaponsTextures[ i ] = config.weapons[ i ][ 1 ];
		// SKINS

		this.skinsBody = loadTextures( config.baseUrl + 'skins/', config.skins );
		this.skinsWeapon = loadTextures( config.baseUrl + 'skins/', weaponsTextures );

		// BODY

		const loader = new MD2Loader();

		loader.load( config.baseUrl + config.body, function ( geo ) {

			const boundingBox = new Box3();
			boundingBox.setFromBufferAttribute( geo.attributes.position );

			scope.root.position.y = - scope.scale * boundingBox.min.y;

			const mesh = createPart( geo, scope.skinsBody[ 0 ] );
			mesh.scale.set( scope.scale, scope.scale, scope.scale );

			scope.root.add( mesh );

			scope.meshBody = mesh;

			scope.meshBody.clipOffset = 0;
			scope.activeAnimationClipName = mesh.geometry.animations[ 0 ].name;

			scope.mixer = new AnimationMixer( mesh );

			checkLoadingComplete();

		} );

		// WEAPONS

		const generateCallback = function ( index, name ) {

			return function ( geo ) {

				const mesh = createPart( geo, scope.skinsWeapon[ index ] );
				mesh.scale.set( scope.scale, scope.scale, scope.scale );
				mesh.visible = false;

				mesh.name = name;

				scope.root.add( mesh );

				scope.weapons[ index ] = mesh;
				scope.meshWeapon = mesh;

				checkLoadingComplete();

			};

		};

		for ( let i = 0; i < config.weapons.length; i ++ ) {

			loader.load( config.baseUrl + config.weapons[ i ][ 0 ], generateCallback( i, config.weapons[ i ][ 0 ] ) );

		}

	}
```
</details>

### `MD2Character.setPlaybackRate(rate: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the animation playback rate.
	 *
	 * @param {number} rate - The playback rate to set.
	 */
```

**Parameters:**

- **`rate`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setPlaybackRate( rate ) {

		if ( rate !== 0 ) {

			this.mixer.timeScale = 1 / rate;

		} else {

			this.mixer.timeScale = 0;

		}

	}
```
</details>

### `MD2Character.setWireframe(wireframeEnabled: boolean): void`

**JSDoc:**
```typescript
/**
	 * Sets the wireframe material flag.
	 *
	 * @param {boolean} wireframeEnabled - Whether to enable wireframe rendering or not.
	 */
```

**Parameters:**

- **`wireframeEnabled`** `boolean`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setWireframe( wireframeEnabled ) {

		if ( wireframeEnabled ) {

			if ( this.meshBody ) this.meshBody.material = this.meshBody.materialWireframe;
			if ( this.meshWeapon ) this.meshWeapon.material = this.meshWeapon.materialWireframe;

		} else {

			if ( this.meshBody ) this.meshBody.material = this.meshBody.materialTexture;
			if ( this.meshWeapon ) this.meshWeapon.material = this.meshWeapon.materialTexture;

		}

	}
```
</details>

### `MD2Character.setSkin(index: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the skin defined by the given skin index. This will result in a different texture
	 * for the body mesh.
	 *
	 * @param {number} index - The skin index.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setSkin( index ) {

		if ( this.meshBody && this.meshBody.material.wireframe === false ) {

			this.meshBody.material.map = this.skinsBody[ index ];

		}

	}
```
</details>

### `MD2Character.setWeapon(index: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the weapon defined by the given weapon index. This will result in a different weapon
	 * hold by the character.
	 *
	 * @param {number} index - The weapon index.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `void`

**Calls:**

- `this.syncWeaponAnimation`

<details><summary>Code</summary>

```typescript
setWeapon( index ) {

		for ( let i = 0; i < this.weapons.length; i ++ ) this.weapons[ i ].visible = false;

		const activeWeapon = this.weapons[ index ];

		if ( activeWeapon ) {

			activeWeapon.visible = true;
			this.meshWeapon = activeWeapon;

			this.syncWeaponAnimation();

		}

	}
```
</details>

### `MD2Character.setAnimation(clipName: string): void`

**JSDoc:**
```typescript
/**
	 * Sets the defined animation clip as the active animation.
	 *
	 * @param {string} clipName - The name of the animation clip.
	 */
```

**Parameters:**

- **`clipName`** `string`

**Returns:** `void`

**Calls:**

- `this.meshBody.activeAction.stop`
- `this.mixer.clipAction`
- `action.play`
- `this.syncWeaponAnimation`

<details><summary>Code</summary>

```typescript
setAnimation( clipName ) {

		if ( this.meshBody ) {

			if ( this.meshBody.activeAction ) {

				this.meshBody.activeAction.stop();
				this.meshBody.activeAction = null;

			}

			const action = this.mixer.clipAction( clipName, this.meshBody );

			if ( action ) {

				this.meshBody.activeAction = action.play();

			}

		}

		this.activeClipName = clipName;

		this.syncWeaponAnimation();

	}
```
</details>

### `MD2Character.syncWeaponAnimation(): void`

**JSDoc:**
```typescript
/**
	 * Synchronizes the weapon with the body animation.
	 */
```

**Returns:** `void`

**Calls:**

- `this.meshWeapon.activeAction.stop`
- `this.mixer.clipAction`
- `action.syncWith( this.meshBody.activeAction ).play`

<details><summary>Code</summary>

```typescript
syncWeaponAnimation() {

		const clipName = this.activeClipName;

		if ( this.meshWeapon ) {

			if ( this.meshWeapon.activeAction ) {

				this.meshWeapon.activeAction.stop();
				this.meshWeapon.activeAction = null;

			}

			const action = this.mixer.clipAction( clipName, this.meshWeapon );

			if ( action ) {

				this.meshWeapon.activeAction = action.syncWith( this.meshBody.activeAction ).play();

			}

		}

	}
```
</details>

### `MD2Character.update(delta: number): void`

**JSDoc:**
```typescript
/**
	 * Updates the animations of the mesh. Must be called inside the animation loop.
	 *
	 * @param {number} delta - The delta time in seconds.
	 */
```

**Parameters:**

- **`delta`** `number`

**Returns:** `void`

**Calls:**

- `this.mixer.update`

<details><summary>Code</summary>

```typescript
update( delta ) {

		if ( this.mixer ) this.mixer.update( delta );

	}
```
</details>

### `createPart(geometry: any, skinMap: any): any`

**Parameters:**

- **`geometry`** `any`
- **`skinMap`** `any`

**Returns:** `any`

**Internal Comments:**
```
// (x6)
```

<details><summary>Code</summary>

```typescript
function createPart( geometry, skinMap ) {

			const materialWireframe = new MeshLambertMaterial( { color: 0xffaa00, wireframe: true } );
			const materialTexture = new MeshLambertMaterial( { color: 0xffffff, wireframe: false, map: skinMap } );

			//

			const mesh = new Mesh( geometry, materialTexture );
			mesh.rotation.y = - Math.PI / 2;

			mesh.castShadow = true;
			mesh.receiveShadow = true;

			//

			mesh.materialTexture = materialTexture;
			mesh.materialWireframe = materialWireframe;

			return mesh;

		}
```
</details>

### `loadTextures(baseUrl: any, textureUrls: any): any[]`

**Parameters:**

- **`baseUrl`** `any`
- **`textureUrls`** `any`

**Returns:** `any[]`

**Calls:**

- `textureLoader.load`

<details><summary>Code</summary>

```typescript
function loadTextures( baseUrl, textureUrls ) {

			const textureLoader = new TextureLoader();
			const textures = [];

			for ( let i = 0; i < textureUrls.length; i ++ ) {

				textures[ i ] = textureLoader.load( baseUrl + textureUrls[ i ], checkLoadingComplete );
				textures[ i ].mapping = UVMapping;
				textures[ i ].name = textureUrls[ i ];
				textures[ i ].colorSpace = SRGBColorSpace;

			}

			return textures;

		}
```
</details>

### `checkLoadingComplete(): void`

**Returns:** `void`

**Calls:**

- `scope.onLoadComplete`

<details><summary>Code</summary>

```typescript
function checkLoadingComplete() {

			scope.loadCounter -= 1;

			if ( scope.loadCounter === 0 ) scope.onLoadComplete();

		}
```
</details>

### `generateCallback(index: any, name: any): (geo: any) => void`

**Parameters:**

- **`index`** `any`
- **`name`** `any`

**Returns:** `(geo: any) => void`

**Calls:**

- `createPart`
- `mesh.scale.set`
- `scope.root.add`
- `checkLoadingComplete`

<details><summary>Code</summary>

```typescript
function ( index, name ) {

			return function ( geo ) {

				const mesh = createPart( geo, scope.skinsWeapon[ index ] );
				mesh.scale.set( scope.scale, scope.scale, scope.scale );
				mesh.visible = false;

				mesh.name = name;

				scope.root.add( mesh );

				scope.weapons[ index ] = mesh;
				scope.meshWeapon = mesh;

				checkLoadingComplete();

			};

		}
```
</details>


---

## Classes

### `MD2Character`

<details><summary>Class Code</summary>

```ts
class MD2Character {

	/**
	 * Constructs a new MD2 character.
	 */
	constructor() {

		/**
		 * The mesh scale.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.scale = 1;

		/**
		 * The FPS
		 *
		 * @type {number}
		 * @default 6
		 */
		this.animationFPS = 6;

		/**
		 * The root 3D object
		 *
		 * @type {Object3D}
		 */
		this.root = new Object3D();

		/**
		 * The body mesh.
		 *
		 * @type {?Mesh}
		 * @default null
		 */
		this.meshBody = null;

		/**
		 * The weapon mesh.
		 *
		 * @type {?Mesh}
		 * @default null
		 */
		this.meshWeapon = null;

		/**
		 * The body skins.
		 *
		 * @type {Array<Texture>}
		 */
		this.skinsBody = [];

		/**
		 * The weapon skins.
		 *
		 * @type {Array<Texture>}
		 */
		this.skinsWeapon = [];

		/**
		 * The weapon meshes.
		 *
		 * @type {Array<Mesh>}
		 */
		this.weapons = [];

		/**
		 * The name of the active animation clip.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.activeAnimationClipName = null;

		/**
		 * The animation mixer.
		 *
		 * @type {?AnimationMixer}
		 * @default null
		 */
		this.mixer = null;

		/**
		 * The `onLoad` callback function.
		 *
		 * @type {Function}
		 */
		this.onLoadComplete = function () {};

		// internal

		this.loadCounter = 0;

	}

	/**
	 * Loads the character model for the given config.
	 *
	 * @param {Object} config - The config which defines the model and textures paths.
	 */
	loadParts( config ) {

		const scope = this;

		function createPart( geometry, skinMap ) {

			const materialWireframe = new MeshLambertMaterial( { color: 0xffaa00, wireframe: true } );
			const materialTexture = new MeshLambertMaterial( { color: 0xffffff, wireframe: false, map: skinMap } );

			//

			const mesh = new Mesh( geometry, materialTexture );
			mesh.rotation.y = - Math.PI / 2;

			mesh.castShadow = true;
			mesh.receiveShadow = true;

			//

			mesh.materialTexture = materialTexture;
			mesh.materialWireframe = materialWireframe;

			return mesh;

		}

		function loadTextures( baseUrl, textureUrls ) {

			const textureLoader = new TextureLoader();
			const textures = [];

			for ( let i = 0; i < textureUrls.length; i ++ ) {

				textures[ i ] = textureLoader.load( baseUrl + textureUrls[ i ], checkLoadingComplete );
				textures[ i ].mapping = UVMapping;
				textures[ i ].name = textureUrls[ i ];
				textures[ i ].colorSpace = SRGBColorSpace;

			}

			return textures;

		}

		function checkLoadingComplete() {

			scope.loadCounter -= 1;

			if ( scope.loadCounter === 0 ) scope.onLoadComplete();

		}

		this.loadCounter = config.weapons.length * 2 + config.skins.length + 1;

		const weaponsTextures = [];
		for ( let i = 0; i < config.weapons.length; i ++ ) weaponsTextures[ i ] = config.weapons[ i ][ 1 ];
		// SKINS

		this.skinsBody = loadTextures( config.baseUrl + 'skins/', config.skins );
		this.skinsWeapon = loadTextures( config.baseUrl + 'skins/', weaponsTextures );

		// BODY

		const loader = new MD2Loader();

		loader.load( config.baseUrl + config.body, function ( geo ) {

			const boundingBox = new Box3();
			boundingBox.setFromBufferAttribute( geo.attributes.position );

			scope.root.position.y = - scope.scale * boundingBox.min.y;

			const mesh = createPart( geo, scope.skinsBody[ 0 ] );
			mesh.scale.set( scope.scale, scope.scale, scope.scale );

			scope.root.add( mesh );

			scope.meshBody = mesh;

			scope.meshBody.clipOffset = 0;
			scope.activeAnimationClipName = mesh.geometry.animations[ 0 ].name;

			scope.mixer = new AnimationMixer( mesh );

			checkLoadingComplete();

		} );

		// WEAPONS

		const generateCallback = function ( index, name ) {

			return function ( geo ) {

				const mesh = createPart( geo, scope.skinsWeapon[ index ] );
				mesh.scale.set( scope.scale, scope.scale, scope.scale );
				mesh.visible = false;

				mesh.name = name;

				scope.root.add( mesh );

				scope.weapons[ index ] = mesh;
				scope.meshWeapon = mesh;

				checkLoadingComplete();

			};

		};

		for ( let i = 0; i < config.weapons.length; i ++ ) {

			loader.load( config.baseUrl + config.weapons[ i ][ 0 ], generateCallback( i, config.weapons[ i ][ 0 ] ) );

		}

	}

	/**
	 * Sets the animation playback rate.
	 *
	 * @param {number} rate - The playback rate to set.
	 */
	setPlaybackRate( rate ) {

		if ( rate !== 0 ) {

			this.mixer.timeScale = 1 / rate;

		} else {

			this.mixer.timeScale = 0;

		}

	}

	/**
	 * Sets the wireframe material flag.
	 *
	 * @param {boolean} wireframeEnabled - Whether to enable wireframe rendering or not.
	 */
	setWireframe( wireframeEnabled ) {

		if ( wireframeEnabled ) {

			if ( this.meshBody ) this.meshBody.material = this.meshBody.materialWireframe;
			if ( this.meshWeapon ) this.meshWeapon.material = this.meshWeapon.materialWireframe;

		} else {

			if ( this.meshBody ) this.meshBody.material = this.meshBody.materialTexture;
			if ( this.meshWeapon ) this.meshWeapon.material = this.meshWeapon.materialTexture;

		}

	}

	/**
	 * Sets the skin defined by the given skin index. This will result in a different texture
	 * for the body mesh.
	 *
	 * @param {number} index - The skin index.
	 */
	setSkin( index ) {

		if ( this.meshBody && this.meshBody.material.wireframe === false ) {

			this.meshBody.material.map = this.skinsBody[ index ];

		}

	}

	/**
	 * Sets the weapon defined by the given weapon index. This will result in a different weapon
	 * hold by the character.
	 *
	 * @param {number} index - The weapon index.
	 */
	setWeapon( index ) {

		for ( let i = 0; i < this.weapons.length; i ++ ) this.weapons[ i ].visible = false;

		const activeWeapon = this.weapons[ index ];

		if ( activeWeapon ) {

			activeWeapon.visible = true;
			this.meshWeapon = activeWeapon;

			this.syncWeaponAnimation();

		}

	}

	/**
	 * Sets the defined animation clip as the active animation.
	 *
	 * @param {string} clipName - The name of the animation clip.
	 */
	setAnimation( clipName ) {

		if ( this.meshBody ) {

			if ( this.meshBody.activeAction ) {

				this.meshBody.activeAction.stop();
				this.meshBody.activeAction = null;

			}

			const action = this.mixer.clipAction( clipName, this.meshBody );

			if ( action ) {

				this.meshBody.activeAction = action.play();

			}

		}

		this.activeClipName = clipName;

		this.syncWeaponAnimation();

	}

	/**
	 * Synchronizes the weapon with the body animation.
	 */
	syncWeaponAnimation() {

		const clipName = this.activeClipName;

		if ( this.meshWeapon ) {

			if ( this.meshWeapon.activeAction ) {

				this.meshWeapon.activeAction.stop();
				this.meshWeapon.activeAction = null;

			}

			const action = this.mixer.clipAction( clipName, this.meshWeapon );

			if ( action ) {

				this.meshWeapon.activeAction = action.syncWith( this.meshBody.activeAction ).play();

			}

		}

	}

	/**
	 * Updates the animations of the mesh. Must be called inside the animation loop.
	 *
	 * @param {number} delta - The delta time in seconds.
	 */
	update( delta ) {

		if ( this.mixer ) this.mixer.update( delta );

	}

}
```
</details>

#### Methods

##### `loadParts(config: any): void`

<details><summary>Code</summary>

```ts
loadParts( config ) {

		const scope = this;

		function createPart( geometry, skinMap ) {

			const materialWireframe = new MeshLambertMaterial( { color: 0xffaa00, wireframe: true } );
			const materialTexture = new MeshLambertMaterial( { color: 0xffffff, wireframe: false, map: skinMap } );

			//

			const mesh = new Mesh( geometry, materialTexture );
			mesh.rotation.y = - Math.PI / 2;

			mesh.castShadow = true;
			mesh.receiveShadow = true;

			//

			mesh.materialTexture = materialTexture;
			mesh.materialWireframe = materialWireframe;

			return mesh;

		}

		function loadTextures( baseUrl, textureUrls ) {

			const textureLoader = new TextureLoader();
			const textures = [];

			for ( let i = 0; i < textureUrls.length; i ++ ) {

				textures[ i ] = textureLoader.load( baseUrl + textureUrls[ i ], checkLoadingComplete );
				textures[ i ].mapping = UVMapping;
				textures[ i ].name = textureUrls[ i ];
				textures[ i ].colorSpace = SRGBColorSpace;

			}

			return textures;

		}

		function checkLoadingComplete() {

			scope.loadCounter -= 1;

			if ( scope.loadCounter === 0 ) scope.onLoadComplete();

		}

		this.loadCounter = config.weapons.length * 2 + config.skins.length + 1;

		const weaponsTextures = [];
		for ( let i = 0; i < config.weapons.length; i ++ ) weaponsTextures[ i ] = config.weapons[ i ][ 1 ];
		// SKINS

		this.skinsBody = loadTextures( config.baseUrl + 'skins/', config.skins );
		this.skinsWeapon = loadTextures( config.baseUrl + 'skins/', weaponsTextures );

		// BODY

		const loader = new MD2Loader();

		loader.load( config.baseUrl + config.body, function ( geo ) {

			const boundingBox = new Box3();
			boundingBox.setFromBufferAttribute( geo.attributes.position );

			scope.root.position.y = - scope.scale * boundingBox.min.y;

			const mesh = createPart( geo, scope.skinsBody[ 0 ] );
			mesh.scale.set( scope.scale, scope.scale, scope.scale );

			scope.root.add( mesh );

			scope.meshBody = mesh;

			scope.meshBody.clipOffset = 0;
			scope.activeAnimationClipName = mesh.geometry.animations[ 0 ].name;

			scope.mixer = new AnimationMixer( mesh );

			checkLoadingComplete();

		} );

		// WEAPONS

		const generateCallback = function ( index, name ) {

			return function ( geo ) {

				const mesh = createPart( geo, scope.skinsWeapon[ index ] );
				mesh.scale.set( scope.scale, scope.scale, scope.scale );
				mesh.visible = false;

				mesh.name = name;

				scope.root.add( mesh );

				scope.weapons[ index ] = mesh;
				scope.meshWeapon = mesh;

				checkLoadingComplete();

			};

		};

		for ( let i = 0; i < config.weapons.length; i ++ ) {

			loader.load( config.baseUrl + config.weapons[ i ][ 0 ], generateCallback( i, config.weapons[ i ][ 0 ] ) );

		}

	}
```
</details>

##### `setPlaybackRate(rate: number): void`

<details><summary>Code</summary>

```ts
setPlaybackRate( rate ) {

		if ( rate !== 0 ) {

			this.mixer.timeScale = 1 / rate;

		} else {

			this.mixer.timeScale = 0;

		}

	}
```
</details>

##### `setWireframe(wireframeEnabled: boolean): void`

<details><summary>Code</summary>

```ts
setWireframe( wireframeEnabled ) {

		if ( wireframeEnabled ) {

			if ( this.meshBody ) this.meshBody.material = this.meshBody.materialWireframe;
			if ( this.meshWeapon ) this.meshWeapon.material = this.meshWeapon.materialWireframe;

		} else {

			if ( this.meshBody ) this.meshBody.material = this.meshBody.materialTexture;
			if ( this.meshWeapon ) this.meshWeapon.material = this.meshWeapon.materialTexture;

		}

	}
```
</details>

##### `setSkin(index: number): void`

<details><summary>Code</summary>

```ts
setSkin( index ) {

		if ( this.meshBody && this.meshBody.material.wireframe === false ) {

			this.meshBody.material.map = this.skinsBody[ index ];

		}

	}
```
</details>

##### `setWeapon(index: number): void`

<details><summary>Code</summary>

```ts
setWeapon( index ) {

		for ( let i = 0; i < this.weapons.length; i ++ ) this.weapons[ i ].visible = false;

		const activeWeapon = this.weapons[ index ];

		if ( activeWeapon ) {

			activeWeapon.visible = true;
			this.meshWeapon = activeWeapon;

			this.syncWeaponAnimation();

		}

	}
```
</details>

##### `setAnimation(clipName: string): void`

<details><summary>Code</summary>

```ts
setAnimation( clipName ) {

		if ( this.meshBody ) {

			if ( this.meshBody.activeAction ) {

				this.meshBody.activeAction.stop();
				this.meshBody.activeAction = null;

			}

			const action = this.mixer.clipAction( clipName, this.meshBody );

			if ( action ) {

				this.meshBody.activeAction = action.play();

			}

		}

		this.activeClipName = clipName;

		this.syncWeaponAnimation();

	}
```
</details>

##### `syncWeaponAnimation(): void`

<details><summary>Code</summary>

```ts
syncWeaponAnimation() {

		const clipName = this.activeClipName;

		if ( this.meshWeapon ) {

			if ( this.meshWeapon.activeAction ) {

				this.meshWeapon.activeAction.stop();
				this.meshWeapon.activeAction = null;

			}

			const action = this.mixer.clipAction( clipName, this.meshWeapon );

			if ( action ) {

				this.meshWeapon.activeAction = action.syncWith( this.meshBody.activeAction ).play();

			}

		}

	}
```
</details>

##### `update(delta: number): void`

<details><summary>Code</summary>

```ts
update( delta ) {

		if ( this.mixer ) this.mixer.update( delta );

	}
```
</details>


---