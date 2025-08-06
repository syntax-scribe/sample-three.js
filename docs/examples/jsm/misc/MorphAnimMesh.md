[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MorphAnimMesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/misc/MorphAnimMesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationClip` | `three` |
| `AnimationMixer` | `three` |
| `Mesh` | `three` |


---

## Functions

### `MorphAnimMesh.setDirectionForward(): void`

**JSDoc:**
```typescript
/**
	 * Sets the animation playback direction to "forward".
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setDirectionForward() {

		this.mixer.timeScale = 1.0;

	}
```
</details>

### `MorphAnimMesh.setDirectionBackward(): void`

**JSDoc:**
```typescript
/**
	 * Sets the animation playback direction to "backward".
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setDirectionBackward() {

		this.mixer.timeScale = - 1.0;

	}
```
</details>

### `MorphAnimMesh.playAnimation(label: string, fps: number): void`

**JSDoc:**
```typescript
/**
	 * Plays the defined animation clip. The implementation assumes the animation
	 * clips are stored in {@link Object3D#animations} or the geometry.
	 *
	 * @param {string} label - The name of the animation clip.
	 * @param {number} fps - The FPS of the animation clip.
	 */
```

**Parameters:**

- **`label`** `string`
- **`fps`** `number`

**Returns:** `void`

**Calls:**

- `this.activeAction.stop`
- `AnimationClip.findByName`
- `this.mixer.clipAction`
- `action.play`

<details><summary>Code</summary>

```typescript
playAnimation( label, fps ) {

		if ( this.activeAction ) {

			this.activeAction.stop();
			this.activeAction = null;

		}

		const clip = AnimationClip.findByName( this, label );

		if ( clip ) {

			const action = this.mixer.clipAction( clip );
			action.timeScale = ( clip.tracks.length * fps ) / clip.duration;
			this.activeAction = action.play();

		} else {

			throw new Error( 'THREE.MorphAnimMesh: animations[' + label + '] undefined in .playAnimation()' );

		}

	}
```
</details>

### `MorphAnimMesh.updateAnimation(delta: number): void`

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
updateAnimation( delta ) {

		this.mixer.update( delta );

	}
```
</details>

### `MorphAnimMesh.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.mixer = new AnimationMixer( this );

		return this;

	}
```
</details>


---

## Classes

### `MorphAnimMesh`

<details><summary>Class Code</summary>

```ts
class MorphAnimMesh extends Mesh {

	/**
	 * Constructs a new morph anim mesh.
	 *
	 * @param {BufferGeometry} [geometry] - The mesh geometry.
	 * @param {Material|Array<Material>} [material] - The mesh material.
	 */
	constructor( geometry, material ) {

		super( geometry, material );

		this.type = 'MorphAnimMesh';

		/**
		 * The internal animation mixer.
		 *
		 * @type {AnimationMixer}
		 */
		this.mixer = new AnimationMixer( this );

		/**
		 * The current active animation action.
		 *
		 * @type {?AnimationAction}
		 * @default null
		 */
		this.activeAction = null;

	}

	/**
	 * Sets the animation playback direction to "forward".
	 */
	setDirectionForward() {

		this.mixer.timeScale = 1.0;

	}

	/**
	 * Sets the animation playback direction to "backward".
	 */
	setDirectionBackward() {

		this.mixer.timeScale = - 1.0;

	}

	/**
	 * Plays the defined animation clip. The implementation assumes the animation
	 * clips are stored in {@link Object3D#animations} or the geometry.
	 *
	 * @param {string} label - The name of the animation clip.
	 * @param {number} fps - The FPS of the animation clip.
	 */
	playAnimation( label, fps ) {

		if ( this.activeAction ) {

			this.activeAction.stop();
			this.activeAction = null;

		}

		const clip = AnimationClip.findByName( this, label );

		if ( clip ) {

			const action = this.mixer.clipAction( clip );
			action.timeScale = ( clip.tracks.length * fps ) / clip.duration;
			this.activeAction = action.play();

		} else {

			throw new Error( 'THREE.MorphAnimMesh: animations[' + label + '] undefined in .playAnimation()' );

		}

	}

	/**
	 * Updates the animations of the mesh. Must be called inside the animation loop.
	 *
	 * @param {number} delta - The delta time in seconds.
	 */
	updateAnimation( delta ) {

		this.mixer.update( delta );

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.mixer = new AnimationMixer( this );

		return this;

	}

}
```
</details>

#### Methods

##### `setDirectionForward(): void`

<details><summary>Code</summary>

```ts
setDirectionForward() {

		this.mixer.timeScale = 1.0;

	}
```
</details>

##### `setDirectionBackward(): void`

<details><summary>Code</summary>

```ts
setDirectionBackward() {

		this.mixer.timeScale = - 1.0;

	}
```
</details>

##### `playAnimation(label: string, fps: number): void`

<details><summary>Code</summary>

```ts
playAnimation( label, fps ) {

		if ( this.activeAction ) {

			this.activeAction.stop();
			this.activeAction = null;

		}

		const clip = AnimationClip.findByName( this, label );

		if ( clip ) {

			const action = this.mixer.clipAction( clip );
			action.timeScale = ( clip.tracks.length * fps ) / clip.duration;
			this.activeAction = action.play();

		} else {

			throw new Error( 'THREE.MorphAnimMesh: animations[' + label + '] undefined in .playAnimation()' );

		}

	}
```
</details>

##### `updateAnimation(delta: number): void`

<details><summary>Code</summary>

```ts
updateAnimation( delta ) {

		this.mixer.update( delta );

	}
```
</details>

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		this.mixer = new AnimationMixer( this );

		return this;

	}
```
</details>


---