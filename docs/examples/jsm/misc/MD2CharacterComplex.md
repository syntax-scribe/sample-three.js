[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MD2CharacterComplex.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 18 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/misc/MD2CharacterComplex.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box3` | `three` |
| `MathUtils` | `three` |
| `MeshLambertMaterial` | `three` |
| `Object3D` | `three` |
| `TextureLoader` | `three` |
| `UVMapping` | `three` |
| `SRGBColorSpace` | `three` |
| `MD2Loader` | `../loaders/MD2Loader.js` |
| `MorphBlendMesh` | `../misc/MorphBlendMesh.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `textureLoader` | `any` | let/var | `new TextureLoader()` | ✗ |
| `textures` | `any[]` | let/var | `[]` | ✗ |
| `weaponsTextures` | `any[]` | let/var | `[]` | ✗ |
| `loader` | `MD2Loader` | let/var | `new MD2Loader()` | ✗ |
| `boundingBox` | `any` | let/var | `new Box3()` | ✗ |
| `activeWeapon` | `Mesh` | let/var | `this.weapons[ index ]` | ✗ |
| `mix` | `number` | let/var | `1` | ✗ |
| `controls` | `any` | let/var | `this.controls` | ✗ |
| `animations` | `{}` | let/var | `this.animations` | ✗ |
| `moveAnimation` | `any` | let/var | `*not shown*` | ✗ |
| `idleAnimation` | `any` | let/var | `*not shown*` | ✗ |
| `controls` | `any` | let/var | `this.controls` | ✗ |
| `dir` | `1` | let/var | `1` | ✗ |
| `forwardDelta` | `number` | let/var | `this.speed * delta` | ✗ |
| `materialWireframe` | `any` | let/var | `new MeshLambertMaterial( { color: 0xffaa00, wireframe: true } )` | ✗ |
| `materialTexture` | `any` | let/var | `new MeshLambertMaterial( { color: 0xffffff, wireframe: false, map: skinMap } )` | ✗ |
| `mesh` | `MorphBlendMesh` | let/var | `new MorphBlendMesh( geometry, materialTexture )` | ✗ |


---

## Functions

### `MD2CharacterComplex.enableShadows(enable: boolean): void`

**JSDoc:**
```typescript
/**
	 * Toggles shadow casting and receiving on the character's meshes.
	 *
	 * @param {boolean} enable - Whether to enable shadows or not.
	 */
```

**Parameters:**

- **`enable`** `boolean`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
enableShadows( enable ) {

		for ( let i = 0; i < this.meshes.length; i ++ ) {

			this.meshes[ i ].castShadow = enable;
			this.meshes[ i ].receiveShadow = enable;

		}

	}
```
</details>

### `MD2CharacterComplex.setVisible(enable: boolean): void`

**JSDoc:**
```typescript
/**
	 * Toggles visibility on the character's meshes.
	 *
	 * @param {boolean} enable - Whether the character is visible or not.
	 */
```

**Parameters:**

- **`enable`** `boolean`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setVisible( enable ) {

		for ( let i = 0; i < this.meshes.length; i ++ ) {

			this.meshes[ i ].visible = enable;
			this.meshes[ i ].visible = enable;

		}

	}
```
</details>

### `MD2CharacterComplex.shareParts(original: MD2CharacterComplex): void`

**JSDoc:**
```typescript
/**
	 * Shares certain resources from a different character model.
	 *
	 * @param {MD2CharacterComplex} original - The original MD2 character.
	 */
```

**Parameters:**

- **`original`** `MD2CharacterComplex`

**Returns:** `void`

**Calls:**

- `this._createPart`
- `mesh.scale.set`
- `this.root.add`
- `this.meshes.push`
- `meshWeapon.scale.set`

**Internal Comments:**
```
// BODY (x2)
// WEAPONS
```

<details><summary>Code</summary>

```typescript
shareParts( original ) {

		this.animations = original.animations;
		this.walkSpeed = original.walkSpeed;
		this.crouchSpeed = original.crouchSpeed;

		this.skinsBody = original.skinsBody;
		this.skinsWeapon = original.skinsWeapon;

		// BODY

		const mesh = this._createPart( original.meshBody.geometry, this.skinsBody[ 0 ] );
		mesh.scale.set( this.scale, this.scale, this.scale );

		this.root.position.y = original.root.position.y;
		this.root.add( mesh );

		this.meshBody = mesh;

		this.meshes.push( mesh );

		// WEAPONS

		for ( let i = 0; i < original.weapons.length; i ++ ) {

			const meshWeapon = this._createPart( original.weapons[ i ].geometry, this.skinsWeapon[ i ] );
			meshWeapon.scale.set( this.scale, this.scale, this.scale );
			meshWeapon.visible = false;

			meshWeapon.name = original.weapons[ i ].name;

			this.root.add( meshWeapon );

			this.weapons[ i ] = meshWeapon;
			this.meshWeapon = meshWeapon;

			this.meshes.push( meshWeapon );

		}

	}
```
</details>

### `MD2CharacterComplex.loadParts(config: any): void`

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
- `scope._createPart`
- `mesh.scale.set`
- `scope.root.add`
- `scope.meshes.push`
- `checkLoadingComplete`
- `generateCallback`

**Internal Comments:**
```
// SKINS (x4)
// BODY (x2)
// WEAPONS (x2)
```

<details><summary>Code</summary>

```typescript
loadParts( config ) {

		const scope = this;

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
			if ( scope.loadCounter === 0 ) 	scope.onLoadComplete();

		}

		this.animations = config.animations;
		this.walkSpeed = config.walkSpeed;
		this.crouchSpeed = config.crouchSpeed;

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

			const mesh = scope._createPart( geo, scope.skinsBody[ 0 ] );
			mesh.scale.set( scope.scale, scope.scale, scope.scale );

			scope.root.add( mesh );

			scope.meshBody = mesh;
			scope.meshes.push( mesh );

			checkLoadingComplete();

		} );

		// WEAPONS

		const generateCallback = function ( index, name ) {

			return function ( geo ) {

				const mesh = scope._createPart( geo, scope.skinsWeapon[ index ] );
				mesh.scale.set( scope.scale, scope.scale, scope.scale );
				mesh.visible = false;

				mesh.name = name;

				scope.root.add( mesh );

				scope.weapons[ index ] = mesh;
				scope.meshWeapon = mesh;
				scope.meshes.push( mesh );

				checkLoadingComplete();

			};

		};

		for ( let i = 0; i < config.weapons.length; i ++ ) {

			loader.load( config.baseUrl + config.weapons[ i ][ 0 ], generateCallback( i, config.weapons[ i ][ 0 ] ) );

		}

	}
```
</details>

### `MD2CharacterComplex.setPlaybackRate(rate: number): void`

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

		if ( this.meshBody ) this.meshBody.duration = this.meshBody.baseDuration / rate;
		if ( this.meshWeapon ) this.meshWeapon.duration = this.meshWeapon.baseDuration / rate;

	}
```
</details>

### `MD2CharacterComplex.setWireframe(wireframeEnabled: boolean): void`

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

### `MD2CharacterComplex.setSkin(index: number): void`

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
			this.currentSkin = index;

		}

	}
```
</details>

### `MD2CharacterComplex.setWeapon(index: number): void`

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

- `activeWeapon.playAnimation`
- `this.meshWeapon.setAnimationTime`
- `this.meshBody.getAnimationTime`

<details><summary>Code</summary>

```typescript
setWeapon( index ) {

		for ( let i = 0; i < this.weapons.length; i ++ ) this.weapons[ i ].visible = false;

		const activeWeapon = this.weapons[ index ];

		if ( activeWeapon ) {

			activeWeapon.visible = true;
			this.meshWeapon = activeWeapon;

			if ( this.activeAnimation ) {

				activeWeapon.playAnimation( this.activeAnimation );
				this.meshWeapon.setAnimationTime( this.activeAnimation, this.meshBody.getAnimationTime( this.activeAnimation ) );

			}

		}

	}
```
</details>

### `MD2CharacterComplex.setAnimation(animationName: string): void`

**JSDoc:**
```typescript
/**
	 * Sets the defined animation clip as the active animation.
	 *
	 * @param {string} animationName - The name of the animation clip.
	 */
```

**Parameters:**

- **`animationName`** `string`

**Returns:** `void`

**Calls:**

- `this.meshBody.setAnimationWeight`
- `this.meshBody.playAnimation`
- `this.meshWeapon.setAnimationWeight`
- `this.meshWeapon.playAnimation`

<details><summary>Code</summary>

```typescript
setAnimation( animationName ) {

		if ( animationName === this.activeAnimation || ! animationName ) return;

		if ( this.meshBody ) {

			this.meshBody.setAnimationWeight( animationName, 0 );
			this.meshBody.playAnimation( animationName );

			this.oldAnimation = this.activeAnimation;
			this.activeAnimation = animationName;

			this.blendCounter = this.transitionFrames;

		}

		if ( this.meshWeapon ) {

			this.meshWeapon.setAnimationWeight( animationName, 0 );
			this.meshWeapon.playAnimation( animationName );

		}


	}
```
</details>

### `MD2CharacterComplex.update(delta: any): void`

**Parameters:**

- **`delta`** `any`

**Returns:** `void`

**Calls:**

- `this.updateMovementModel`
- `this.updateBehaviors`
- `this.updateAnimations`

<details><summary>Code</summary>

```typescript
update( delta ) {

		if ( this.controls ) this.updateMovementModel( delta );

		if ( this.animations ) {

			this.updateBehaviors();
			this.updateAnimations( delta );

		}

	}
```
</details>

### `MD2CharacterComplex.updateAnimations(delta: number): void`

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

- `this.meshBody.update`
- `this.meshBody.setAnimationWeight`
- `this.meshWeapon.update`
- `this.meshWeapon.setAnimationWeight`

<details><summary>Code</summary>

```typescript
updateAnimations( delta ) {

		let mix = 1;

		if ( this.blendCounter > 0 ) {

			mix = ( this.transitionFrames - this.blendCounter ) / this.transitionFrames;
			this.blendCounter -= 1;

		}

		if ( this.meshBody ) {

			this.meshBody.update( delta );

			this.meshBody.setAnimationWeight( this.activeAnimation, mix );
			this.meshBody.setAnimationWeight( this.oldAnimation, 1 - mix );

		}

		if ( this.meshWeapon ) {

			this.meshWeapon.update( delta );

			this.meshWeapon.setAnimationWeight( this.activeAnimation, mix );
			this.meshWeapon.setAnimationWeight( this.oldAnimation, 1 - mix );

		}

	}
```
</details>

### `MD2CharacterComplex.updateBehaviors(): void`

**JSDoc:**
```typescript
/**
	 * Updates the animation state based on the control inputs.
	 */
```

**Returns:** `void`

**Calls:**

- `this.setAnimation`
- `Math.abs`
- `this.meshBody.setAnimationDirectionForward`
- `this.meshWeapon.setAnimationDirectionForward`
- `this.meshBody.setAnimationDirectionBackward`
- `this.meshWeapon.setAnimationDirectionBackward`

**Internal Comments:**
```
// crouch vs stand
// actions
// set animations
// set animation direction
```

<details><summary>Code</summary>

```typescript
updateBehaviors() {

		const controls = this.controls;
		const animations = this.animations;

		let moveAnimation, idleAnimation;

		// crouch vs stand

		if ( controls.crouch ) {

			moveAnimation = animations[ 'crouchMove' ];
			idleAnimation = animations[ 'crouchIdle' ];

		} else {

			moveAnimation = animations[ 'move' ];
			idleAnimation = animations[ 'idle' ];

		}

		// actions

		if ( controls.jump ) {

			moveAnimation = animations[ 'jump' ];
			idleAnimation = animations[ 'jump' ];

		}

		if ( controls.attack ) {

			if ( controls.crouch ) {

				moveAnimation = animations[ 'crouchAttack' ];
				idleAnimation = animations[ 'crouchAttack' ];

			} else {

				moveAnimation = animations[ 'attack' ];
				idleAnimation = animations[ 'attack' ];

			}

		}

		// set animations

		if ( controls.moveForward || controls.moveBackward || controls.moveLeft || controls.moveRight ) {

			if ( this.activeAnimation !== moveAnimation ) {

				this.setAnimation( moveAnimation );

			}

		}


		if ( Math.abs( this.speed ) < 0.2 * this.maxSpeed && ! ( controls.moveLeft || controls.moveRight || controls.moveForward || controls.moveBackward ) ) {

			if ( this.activeAnimation !== idleAnimation ) {

				this.setAnimation( idleAnimation );

			}

		}

		// set animation direction

		if ( controls.moveForward ) {

			if ( this.meshBody ) {

				this.meshBody.setAnimationDirectionForward( this.activeAnimation );
				this.meshBody.setAnimationDirectionForward( this.oldAnimation );

			}

			if ( this.meshWeapon ) {

				this.meshWeapon.setAnimationDirectionForward( this.activeAnimation );
				this.meshWeapon.setAnimationDirectionForward( this.oldAnimation );

			}

		}

		if ( controls.moveBackward ) {

			if ( this.meshBody ) {

				this.meshBody.setAnimationDirectionBackward( this.activeAnimation );
				this.meshBody.setAnimationDirectionBackward( this.oldAnimation );

			}

			if ( this.meshWeapon ) {

				this.meshWeapon.setAnimationDirectionBackward( this.activeAnimation );
				this.meshWeapon.setAnimationDirectionBackward( this.oldAnimation );

			}

		}

	}
```
</details>

### `MD2CharacterComplex.updateMovementModel(delta: number): void`

**JSDoc:**
```typescript
/**
	 * Transforms the character model based on the control input.
	 *
	 * @param {number} delta - The delta time in seconds.
	 */
```

**Parameters:**

- **`delta`** `number`

**Returns:** `void`

**Calls:**

- `Math.pow`
- `MathUtils.clamp`
- `exponentialEaseOut`
- `Math.sin`
- `Math.cos`

**Internal Comments:**
```
// speed based on controls
// orientation based on controls (x2)
// (don't just stand while turning) (x2)
// speed decay
// displacement (x2)
// steering (x6)
```

<details><summary>Code</summary>

```typescript
updateMovementModel( delta ) {

		function exponentialEaseOut( k ) {

			return k === 1 ? 1 : - Math.pow( 2, - 10 * k ) + 1;

		}

		const controls = this.controls;

		// speed based on controls

		if ( controls.crouch ) 	this.maxSpeed = this.crouchSpeed;
		else this.maxSpeed = this.walkSpeed;

		this.maxReverseSpeed = - this.maxSpeed;

		if ( controls.moveForward ) this.speed = MathUtils.clamp( this.speed + delta * this.frontAcceleration, this.maxReverseSpeed, this.maxSpeed );
		if ( controls.moveBackward ) this.speed = MathUtils.clamp( this.speed - delta * this.backAcceleration, this.maxReverseSpeed, this.maxSpeed );

		// orientation based on controls
		// (don't just stand while turning)

		const dir = 1;

		if ( controls.moveLeft ) {

			this.bodyOrientation += delta * this.angularSpeed;
			this.speed = MathUtils.clamp( this.speed + dir * delta * this.frontAcceleration, this.maxReverseSpeed, this.maxSpeed );

		}

		if ( controls.moveRight ) {

			this.bodyOrientation -= delta * this.angularSpeed;
			this.speed = MathUtils.clamp( this.speed + dir * delta * this.frontAcceleration, this.maxReverseSpeed, this.maxSpeed );

		}

		// speed decay

		if ( ! ( controls.moveForward || controls.moveBackward ) ) {

			if ( this.speed > 0 ) {

				const k = exponentialEaseOut( this.speed / this.maxSpeed );
				this.speed = MathUtils.clamp( this.speed - k * delta * this.frontDeceleration, 0, this.maxSpeed );

			} else {

				const k = exponentialEaseOut( this.speed / this.maxReverseSpeed );
				this.speed = MathUtils.clamp( this.speed + k * delta * this.backAcceleration, this.maxReverseSpeed, 0 );

			}

		}

		// displacement

		const forwardDelta = this.speed * delta;

		this.root.position.x += Math.sin( this.bodyOrientation ) * forwardDelta;
		this.root.position.z += Math.cos( this.bodyOrientation ) * forwardDelta;

		// steering

		this.root.rotation.y = this.bodyOrientation;

	}
```
</details>

### `MD2CharacterComplex._createPart(geometry: any, skinMap: any): MorphBlendMesh`

**Parameters:**

- **`geometry`** `any`
- **`skinMap`** `any`

**Returns:** `MorphBlendMesh`

**Calls:**

- `mesh.autoCreateAnimations`

**Internal Comments:**
```
// (x10)
```

<details><summary>Code</summary>

```typescript
_createPart( geometry, skinMap ) {

		const materialWireframe = new MeshLambertMaterial( { color: 0xffaa00, wireframe: true } );
		const materialTexture = new MeshLambertMaterial( { color: 0xffffff, wireframe: false, map: skinMap } );

		//

		const mesh = new MorphBlendMesh( geometry, materialTexture );
		mesh.rotation.y = - Math.PI / 2;

		//

		mesh.materialTexture = materialTexture;
		mesh.materialWireframe = materialWireframe;

		//

		mesh.autoCreateAnimations( this.animationFPS );

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
			if ( scope.loadCounter === 0 ) 	scope.onLoadComplete();

		}
```
</details>

### `generateCallback(index: any, name: any): (geo: any) => void`

**Parameters:**

- **`index`** `any`
- **`name`** `any`

**Returns:** `(geo: any) => void`

**Calls:**

- `scope._createPart`
- `mesh.scale.set`
- `scope.root.add`
- `scope.meshes.push`
- `checkLoadingComplete`

<details><summary>Code</summary>

```typescript
function ( index, name ) {

			return function ( geo ) {

				const mesh = scope._createPart( geo, scope.skinsWeapon[ index ] );
				mesh.scale.set( scope.scale, scope.scale, scope.scale );
				mesh.visible = false;

				mesh.name = name;

				scope.root.add( mesh );

				scope.weapons[ index ] = mesh;
				scope.meshWeapon = mesh;
				scope.meshes.push( mesh );

				checkLoadingComplete();

			};

		}
```
</details>

### `exponentialEaseOut(k: any): number`

**Parameters:**

- **`k`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function exponentialEaseOut( k ) {

			return k === 1 ? 1 : - Math.pow( 2, - 10 * k ) + 1;

		}
```
</details>


---

## Classes

### `MD2CharacterComplex`

<details><summary>Class Code</summary>

```ts
class MD2CharacterComplex {

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
		 * The transition frames.
		 *
		 * @type {number}
		 * @default 15
		 */
		this.transitionFrames = 15;

		/**
		 * The character's maximum speed.
		 *
		 * @type {number}
		 * @default 275
		 */
		this.maxSpeed = 275;

		/**
		 * The character's maximum reverse speed.
		 *
		 * @type {number}
		 * @default - 275
		 */
		this.maxReverseSpeed = - 275;

		/**
		 * The character's front acceleration.
		 *
		 * @type {number}
		 * @default 600
		 */
		this.frontAcceleration = 600;

		/**
		 * The character's back acceleration.
		 *
		 * @type {number}
		 * @default 600
		 */
		this.backAcceleration = 600;

		/**
		 * The character's front deceleration.
		 *
		 * @type {number}
		 * @default 600
		 */
		this.frontDeceleration = 600;

		/**
		 * The character's angular speed.
		 *
		 * @type {number}
		 * @default 2.5
		 */
		this.angularSpeed = 2.5;

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
		 * The movement controls.
		 *
		 * @type {Object}
		 * @default null
		 */
		this.controls = null;

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
		 * The current skin.
		 *
		 * @type {Texture}
		 * @default undefined
		 */
		this.currentSkin = undefined;

		//

		this.onLoadComplete = function () {};

		// internals

		this.meshes = [];
		this.animations = {};

		this.loadCounter = 0;

		// internal movement control variables

		this.speed = 0;
		this.bodyOrientation = 0;

		this.walkSpeed = this.maxSpeed;
		this.crouchSpeed = this.maxSpeed * 0.5;

		// internal animation parameters

		this.activeAnimation = null;
		this.oldAnimation = null;

		// API

	}

	/**
	 * Toggles shadow casting and receiving on the character's meshes.
	 *
	 * @param {boolean} enable - Whether to enable shadows or not.
	 */
	enableShadows( enable ) {

		for ( let i = 0; i < this.meshes.length; i ++ ) {

			this.meshes[ i ].castShadow = enable;
			this.meshes[ i ].receiveShadow = enable;

		}

	}

	/**
	 * Toggles visibility on the character's meshes.
	 *
	 * @param {boolean} enable - Whether the character is visible or not.
	 */
	setVisible( enable ) {

		for ( let i = 0; i < this.meshes.length; i ++ ) {

			this.meshes[ i ].visible = enable;
			this.meshes[ i ].visible = enable;

		}

	}

	/**
	 * Shares certain resources from a different character model.
	 *
	 * @param {MD2CharacterComplex} original - The original MD2 character.
	 */
	shareParts( original ) {

		this.animations = original.animations;
		this.walkSpeed = original.walkSpeed;
		this.crouchSpeed = original.crouchSpeed;

		this.skinsBody = original.skinsBody;
		this.skinsWeapon = original.skinsWeapon;

		// BODY

		const mesh = this._createPart( original.meshBody.geometry, this.skinsBody[ 0 ] );
		mesh.scale.set( this.scale, this.scale, this.scale );

		this.root.position.y = original.root.position.y;
		this.root.add( mesh );

		this.meshBody = mesh;

		this.meshes.push( mesh );

		// WEAPONS

		for ( let i = 0; i < original.weapons.length; i ++ ) {

			const meshWeapon = this._createPart( original.weapons[ i ].geometry, this.skinsWeapon[ i ] );
			meshWeapon.scale.set( this.scale, this.scale, this.scale );
			meshWeapon.visible = false;

			meshWeapon.name = original.weapons[ i ].name;

			this.root.add( meshWeapon );

			this.weapons[ i ] = meshWeapon;
			this.meshWeapon = meshWeapon;

			this.meshes.push( meshWeapon );

		}

	}

	/**
	 * Loads the character model for the given config.
	 *
	 * @param {Object} config - The config which defines the model and textures paths.
	 */
	loadParts( config ) {

		const scope = this;

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
			if ( scope.loadCounter === 0 ) 	scope.onLoadComplete();

		}

		this.animations = config.animations;
		this.walkSpeed = config.walkSpeed;
		this.crouchSpeed = config.crouchSpeed;

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

			const mesh = scope._createPart( geo, scope.skinsBody[ 0 ] );
			mesh.scale.set( scope.scale, scope.scale, scope.scale );

			scope.root.add( mesh );

			scope.meshBody = mesh;
			scope.meshes.push( mesh );

			checkLoadingComplete();

		} );

		// WEAPONS

		const generateCallback = function ( index, name ) {

			return function ( geo ) {

				const mesh = scope._createPart( geo, scope.skinsWeapon[ index ] );
				mesh.scale.set( scope.scale, scope.scale, scope.scale );
				mesh.visible = false;

				mesh.name = name;

				scope.root.add( mesh );

				scope.weapons[ index ] = mesh;
				scope.meshWeapon = mesh;
				scope.meshes.push( mesh );

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

		if ( this.meshBody ) this.meshBody.duration = this.meshBody.baseDuration / rate;
		if ( this.meshWeapon ) this.meshWeapon.duration = this.meshWeapon.baseDuration / rate;

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
			this.currentSkin = index;

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

			if ( this.activeAnimation ) {

				activeWeapon.playAnimation( this.activeAnimation );
				this.meshWeapon.setAnimationTime( this.activeAnimation, this.meshBody.getAnimationTime( this.activeAnimation ) );

			}

		}

	}

	/**
	 * Sets the defined animation clip as the active animation.
	 *
	 * @param {string} animationName - The name of the animation clip.
	 */
	setAnimation( animationName ) {

		if ( animationName === this.activeAnimation || ! animationName ) return;

		if ( this.meshBody ) {

			this.meshBody.setAnimationWeight( animationName, 0 );
			this.meshBody.playAnimation( animationName );

			this.oldAnimation = this.activeAnimation;
			this.activeAnimation = animationName;

			this.blendCounter = this.transitionFrames;

		}

		if ( this.meshWeapon ) {

			this.meshWeapon.setAnimationWeight( animationName, 0 );
			this.meshWeapon.playAnimation( animationName );

		}


	}

	update( delta ) {

		if ( this.controls ) this.updateMovementModel( delta );

		if ( this.animations ) {

			this.updateBehaviors();
			this.updateAnimations( delta );

		}

	}

	/**
	 * Updates the animations of the mesh. Must be called inside the animation loop.
	 *
	 * @param {number} delta - The delta time in seconds.
	 */
	updateAnimations( delta ) {

		let mix = 1;

		if ( this.blendCounter > 0 ) {

			mix = ( this.transitionFrames - this.blendCounter ) / this.transitionFrames;
			this.blendCounter -= 1;

		}

		if ( this.meshBody ) {

			this.meshBody.update( delta );

			this.meshBody.setAnimationWeight( this.activeAnimation, mix );
			this.meshBody.setAnimationWeight( this.oldAnimation, 1 - mix );

		}

		if ( this.meshWeapon ) {

			this.meshWeapon.update( delta );

			this.meshWeapon.setAnimationWeight( this.activeAnimation, mix );
			this.meshWeapon.setAnimationWeight( this.oldAnimation, 1 - mix );

		}

	}

	/**
	 * Updates the animation state based on the control inputs.
	 */
	updateBehaviors() {

		const controls = this.controls;
		const animations = this.animations;

		let moveAnimation, idleAnimation;

		// crouch vs stand

		if ( controls.crouch ) {

			moveAnimation = animations[ 'crouchMove' ];
			idleAnimation = animations[ 'crouchIdle' ];

		} else {

			moveAnimation = animations[ 'move' ];
			idleAnimation = animations[ 'idle' ];

		}

		// actions

		if ( controls.jump ) {

			moveAnimation = animations[ 'jump' ];
			idleAnimation = animations[ 'jump' ];

		}

		if ( controls.attack ) {

			if ( controls.crouch ) {

				moveAnimation = animations[ 'crouchAttack' ];
				idleAnimation = animations[ 'crouchAttack' ];

			} else {

				moveAnimation = animations[ 'attack' ];
				idleAnimation = animations[ 'attack' ];

			}

		}

		// set animations

		if ( controls.moveForward || controls.moveBackward || controls.moveLeft || controls.moveRight ) {

			if ( this.activeAnimation !== moveAnimation ) {

				this.setAnimation( moveAnimation );

			}

		}


		if ( Math.abs( this.speed ) < 0.2 * this.maxSpeed && ! ( controls.moveLeft || controls.moveRight || controls.moveForward || controls.moveBackward ) ) {

			if ( this.activeAnimation !== idleAnimation ) {

				this.setAnimation( idleAnimation );

			}

		}

		// set animation direction

		if ( controls.moveForward ) {

			if ( this.meshBody ) {

				this.meshBody.setAnimationDirectionForward( this.activeAnimation );
				this.meshBody.setAnimationDirectionForward( this.oldAnimation );

			}

			if ( this.meshWeapon ) {

				this.meshWeapon.setAnimationDirectionForward( this.activeAnimation );
				this.meshWeapon.setAnimationDirectionForward( this.oldAnimation );

			}

		}

		if ( controls.moveBackward ) {

			if ( this.meshBody ) {

				this.meshBody.setAnimationDirectionBackward( this.activeAnimation );
				this.meshBody.setAnimationDirectionBackward( this.oldAnimation );

			}

			if ( this.meshWeapon ) {

				this.meshWeapon.setAnimationDirectionBackward( this.activeAnimation );
				this.meshWeapon.setAnimationDirectionBackward( this.oldAnimation );

			}

		}

	}

	/**
	 * Transforms the character model based on the control input.
	 *
	 * @param {number} delta - The delta time in seconds.
	 */
	updateMovementModel( delta ) {

		function exponentialEaseOut( k ) {

			return k === 1 ? 1 : - Math.pow( 2, - 10 * k ) + 1;

		}

		const controls = this.controls;

		// speed based on controls

		if ( controls.crouch ) 	this.maxSpeed = this.crouchSpeed;
		else this.maxSpeed = this.walkSpeed;

		this.maxReverseSpeed = - this.maxSpeed;

		if ( controls.moveForward ) this.speed = MathUtils.clamp( this.speed + delta * this.frontAcceleration, this.maxReverseSpeed, this.maxSpeed );
		if ( controls.moveBackward ) this.speed = MathUtils.clamp( this.speed - delta * this.backAcceleration, this.maxReverseSpeed, this.maxSpeed );

		// orientation based on controls
		// (don't just stand while turning)

		const dir = 1;

		if ( controls.moveLeft ) {

			this.bodyOrientation += delta * this.angularSpeed;
			this.speed = MathUtils.clamp( this.speed + dir * delta * this.frontAcceleration, this.maxReverseSpeed, this.maxSpeed );

		}

		if ( controls.moveRight ) {

			this.bodyOrientation -= delta * this.angularSpeed;
			this.speed = MathUtils.clamp( this.speed + dir * delta * this.frontAcceleration, this.maxReverseSpeed, this.maxSpeed );

		}

		// speed decay

		if ( ! ( controls.moveForward || controls.moveBackward ) ) {

			if ( this.speed > 0 ) {

				const k = exponentialEaseOut( this.speed / this.maxSpeed );
				this.speed = MathUtils.clamp( this.speed - k * delta * this.frontDeceleration, 0, this.maxSpeed );

			} else {

				const k = exponentialEaseOut( this.speed / this.maxReverseSpeed );
				this.speed = MathUtils.clamp( this.speed + k * delta * this.backAcceleration, this.maxReverseSpeed, 0 );

			}

		}

		// displacement

		const forwardDelta = this.speed * delta;

		this.root.position.x += Math.sin( this.bodyOrientation ) * forwardDelta;
		this.root.position.z += Math.cos( this.bodyOrientation ) * forwardDelta;

		// steering

		this.root.rotation.y = this.bodyOrientation;

	}

	// internal

	_createPart( geometry, skinMap ) {

		const materialWireframe = new MeshLambertMaterial( { color: 0xffaa00, wireframe: true } );
		const materialTexture = new MeshLambertMaterial( { color: 0xffffff, wireframe: false, map: skinMap } );

		//

		const mesh = new MorphBlendMesh( geometry, materialTexture );
		mesh.rotation.y = - Math.PI / 2;

		//

		mesh.materialTexture = materialTexture;
		mesh.materialWireframe = materialWireframe;

		//

		mesh.autoCreateAnimations( this.animationFPS );

		return mesh;

	}

}
```
</details>

#### Methods

##### `enableShadows(enable: boolean): void`

<details><summary>Code</summary>

```ts
enableShadows( enable ) {

		for ( let i = 0; i < this.meshes.length; i ++ ) {

			this.meshes[ i ].castShadow = enable;
			this.meshes[ i ].receiveShadow = enable;

		}

	}
```
</details>

##### `setVisible(enable: boolean): void`

<details><summary>Code</summary>

```ts
setVisible( enable ) {

		for ( let i = 0; i < this.meshes.length; i ++ ) {

			this.meshes[ i ].visible = enable;
			this.meshes[ i ].visible = enable;

		}

	}
```
</details>

##### `shareParts(original: MD2CharacterComplex): void`

<details><summary>Code</summary>

```ts
shareParts( original ) {

		this.animations = original.animations;
		this.walkSpeed = original.walkSpeed;
		this.crouchSpeed = original.crouchSpeed;

		this.skinsBody = original.skinsBody;
		this.skinsWeapon = original.skinsWeapon;

		// BODY

		const mesh = this._createPart( original.meshBody.geometry, this.skinsBody[ 0 ] );
		mesh.scale.set( this.scale, this.scale, this.scale );

		this.root.position.y = original.root.position.y;
		this.root.add( mesh );

		this.meshBody = mesh;

		this.meshes.push( mesh );

		// WEAPONS

		for ( let i = 0; i < original.weapons.length; i ++ ) {

			const meshWeapon = this._createPart( original.weapons[ i ].geometry, this.skinsWeapon[ i ] );
			meshWeapon.scale.set( this.scale, this.scale, this.scale );
			meshWeapon.visible = false;

			meshWeapon.name = original.weapons[ i ].name;

			this.root.add( meshWeapon );

			this.weapons[ i ] = meshWeapon;
			this.meshWeapon = meshWeapon;

			this.meshes.push( meshWeapon );

		}

	}
```
</details>

##### `loadParts(config: any): void`

<details><summary>Code</summary>

```ts
loadParts( config ) {

		const scope = this;

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
			if ( scope.loadCounter === 0 ) 	scope.onLoadComplete();

		}

		this.animations = config.animations;
		this.walkSpeed = config.walkSpeed;
		this.crouchSpeed = config.crouchSpeed;

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

			const mesh = scope._createPart( geo, scope.skinsBody[ 0 ] );
			mesh.scale.set( scope.scale, scope.scale, scope.scale );

			scope.root.add( mesh );

			scope.meshBody = mesh;
			scope.meshes.push( mesh );

			checkLoadingComplete();

		} );

		// WEAPONS

		const generateCallback = function ( index, name ) {

			return function ( geo ) {

				const mesh = scope._createPart( geo, scope.skinsWeapon[ index ] );
				mesh.scale.set( scope.scale, scope.scale, scope.scale );
				mesh.visible = false;

				mesh.name = name;

				scope.root.add( mesh );

				scope.weapons[ index ] = mesh;
				scope.meshWeapon = mesh;
				scope.meshes.push( mesh );

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

		if ( this.meshBody ) this.meshBody.duration = this.meshBody.baseDuration / rate;
		if ( this.meshWeapon ) this.meshWeapon.duration = this.meshWeapon.baseDuration / rate;

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
			this.currentSkin = index;

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

			if ( this.activeAnimation ) {

				activeWeapon.playAnimation( this.activeAnimation );
				this.meshWeapon.setAnimationTime( this.activeAnimation, this.meshBody.getAnimationTime( this.activeAnimation ) );

			}

		}

	}
```
</details>

##### `setAnimation(animationName: string): void`

<details><summary>Code</summary>

```ts
setAnimation( animationName ) {

		if ( animationName === this.activeAnimation || ! animationName ) return;

		if ( this.meshBody ) {

			this.meshBody.setAnimationWeight( animationName, 0 );
			this.meshBody.playAnimation( animationName );

			this.oldAnimation = this.activeAnimation;
			this.activeAnimation = animationName;

			this.blendCounter = this.transitionFrames;

		}

		if ( this.meshWeapon ) {

			this.meshWeapon.setAnimationWeight( animationName, 0 );
			this.meshWeapon.playAnimation( animationName );

		}


	}
```
</details>

##### `update(delta: any): void`

<details><summary>Code</summary>

```ts
update( delta ) {

		if ( this.controls ) this.updateMovementModel( delta );

		if ( this.animations ) {

			this.updateBehaviors();
			this.updateAnimations( delta );

		}

	}
```
</details>

##### `updateAnimations(delta: number): void`

<details><summary>Code</summary>

```ts
updateAnimations( delta ) {

		let mix = 1;

		if ( this.blendCounter > 0 ) {

			mix = ( this.transitionFrames - this.blendCounter ) / this.transitionFrames;
			this.blendCounter -= 1;

		}

		if ( this.meshBody ) {

			this.meshBody.update( delta );

			this.meshBody.setAnimationWeight( this.activeAnimation, mix );
			this.meshBody.setAnimationWeight( this.oldAnimation, 1 - mix );

		}

		if ( this.meshWeapon ) {

			this.meshWeapon.update( delta );

			this.meshWeapon.setAnimationWeight( this.activeAnimation, mix );
			this.meshWeapon.setAnimationWeight( this.oldAnimation, 1 - mix );

		}

	}
```
</details>

##### `updateBehaviors(): void`

<details><summary>Code</summary>

```ts
updateBehaviors() {

		const controls = this.controls;
		const animations = this.animations;

		let moveAnimation, idleAnimation;

		// crouch vs stand

		if ( controls.crouch ) {

			moveAnimation = animations[ 'crouchMove' ];
			idleAnimation = animations[ 'crouchIdle' ];

		} else {

			moveAnimation = animations[ 'move' ];
			idleAnimation = animations[ 'idle' ];

		}

		// actions

		if ( controls.jump ) {

			moveAnimation = animations[ 'jump' ];
			idleAnimation = animations[ 'jump' ];

		}

		if ( controls.attack ) {

			if ( controls.crouch ) {

				moveAnimation = animations[ 'crouchAttack' ];
				idleAnimation = animations[ 'crouchAttack' ];

			} else {

				moveAnimation = animations[ 'attack' ];
				idleAnimation = animations[ 'attack' ];

			}

		}

		// set animations

		if ( controls.moveForward || controls.moveBackward || controls.moveLeft || controls.moveRight ) {

			if ( this.activeAnimation !== moveAnimation ) {

				this.setAnimation( moveAnimation );

			}

		}


		if ( Math.abs( this.speed ) < 0.2 * this.maxSpeed && ! ( controls.moveLeft || controls.moveRight || controls.moveForward || controls.moveBackward ) ) {

			if ( this.activeAnimation !== idleAnimation ) {

				this.setAnimation( idleAnimation );

			}

		}

		// set animation direction

		if ( controls.moveForward ) {

			if ( this.meshBody ) {

				this.meshBody.setAnimationDirectionForward( this.activeAnimation );
				this.meshBody.setAnimationDirectionForward( this.oldAnimation );

			}

			if ( this.meshWeapon ) {

				this.meshWeapon.setAnimationDirectionForward( this.activeAnimation );
				this.meshWeapon.setAnimationDirectionForward( this.oldAnimation );

			}

		}

		if ( controls.moveBackward ) {

			if ( this.meshBody ) {

				this.meshBody.setAnimationDirectionBackward( this.activeAnimation );
				this.meshBody.setAnimationDirectionBackward( this.oldAnimation );

			}

			if ( this.meshWeapon ) {

				this.meshWeapon.setAnimationDirectionBackward( this.activeAnimation );
				this.meshWeapon.setAnimationDirectionBackward( this.oldAnimation );

			}

		}

	}
```
</details>

##### `updateMovementModel(delta: number): void`

<details><summary>Code</summary>

```ts
updateMovementModel( delta ) {

		function exponentialEaseOut( k ) {

			return k === 1 ? 1 : - Math.pow( 2, - 10 * k ) + 1;

		}

		const controls = this.controls;

		// speed based on controls

		if ( controls.crouch ) 	this.maxSpeed = this.crouchSpeed;
		else this.maxSpeed = this.walkSpeed;

		this.maxReverseSpeed = - this.maxSpeed;

		if ( controls.moveForward ) this.speed = MathUtils.clamp( this.speed + delta * this.frontAcceleration, this.maxReverseSpeed, this.maxSpeed );
		if ( controls.moveBackward ) this.speed = MathUtils.clamp( this.speed - delta * this.backAcceleration, this.maxReverseSpeed, this.maxSpeed );

		// orientation based on controls
		// (don't just stand while turning)

		const dir = 1;

		if ( controls.moveLeft ) {

			this.bodyOrientation += delta * this.angularSpeed;
			this.speed = MathUtils.clamp( this.speed + dir * delta * this.frontAcceleration, this.maxReverseSpeed, this.maxSpeed );

		}

		if ( controls.moveRight ) {

			this.bodyOrientation -= delta * this.angularSpeed;
			this.speed = MathUtils.clamp( this.speed + dir * delta * this.frontAcceleration, this.maxReverseSpeed, this.maxSpeed );

		}

		// speed decay

		if ( ! ( controls.moveForward || controls.moveBackward ) ) {

			if ( this.speed > 0 ) {

				const k = exponentialEaseOut( this.speed / this.maxSpeed );
				this.speed = MathUtils.clamp( this.speed - k * delta * this.frontDeceleration, 0, this.maxSpeed );

			} else {

				const k = exponentialEaseOut( this.speed / this.maxReverseSpeed );
				this.speed = MathUtils.clamp( this.speed + k * delta * this.backAcceleration, this.maxReverseSpeed, 0 );

			}

		}

		// displacement

		const forwardDelta = this.speed * delta;

		this.root.position.x += Math.sin( this.bodyOrientation ) * forwardDelta;
		this.root.position.z += Math.cos( this.bodyOrientation ) * forwardDelta;

		// steering

		this.root.rotation.y = this.bodyOrientation;

	}
```
</details>

##### `_createPart(geometry: any, skinMap: any): MorphBlendMesh`

<details><summary>Code</summary>

```ts
_createPart( geometry, skinMap ) {

		const materialWireframe = new MeshLambertMaterial( { color: 0xffaa00, wireframe: true } );
		const materialTexture = new MeshLambertMaterial( { color: 0xffffff, wireframe: false, map: skinMap } );

		//

		const mesh = new MorphBlendMesh( geometry, materialTexture );
		mesh.rotation.y = - Math.PI / 2;

		//

		mesh.materialTexture = materialTexture;
		mesh.materialWireframe = materialWireframe;

		//

		mesh.autoCreateAnimations( this.animationFPS );

		return mesh;

	}
```
</details>


---