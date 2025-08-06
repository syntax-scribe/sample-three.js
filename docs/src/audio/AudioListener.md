[⬅️ Back to Table of Contents](../../index.md)

# 📄 `AudioListener.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/audio/AudioListener.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `Quaternion` | `../math/Quaternion.js` |
| `Clock` | `../core/Clock.js` |
| `Object3D` | `../core/Object3D.js` |
| `AudioContext` | `./AudioContext.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_position` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_quaternion` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `_scale` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_forward` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_up` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `listener` | `any` | let/var | `this.context.listener` | ✗ |
| `endTime` | `any` | let/var | `this.context.currentTime + this.timeDelta` | ✗ |


---

## Functions

### `AudioListener.getInput(): GainNode`

**JSDoc:**
```typescript
/**
	 * Returns the listener's input node.
	 *
	 * This method is used by other audio nodes to connect to this listener.
	 *
	 * @return {GainNode} The input node.
	 */
```

**Returns:** `GainNode`

<details><summary>Code</summary>

```typescript
getInput() {

		return this.gain;

	}
```
</details>

### `AudioListener.removeFilter(): AudioListener`

**JSDoc:**
```typescript
/**
	 * Removes the current filter from this listener.
	 *
	 * @return {AudioListener} A reference to this listener.
	 */
```

**Returns:** `AudioListener`

**Calls:**

- `this.gain.disconnect`
- `this.filter.disconnect`
- `this.gain.connect`

<details><summary>Code</summary>

```typescript
removeFilter() {

		if ( this.filter !== null ) {

			this.gain.disconnect( this.filter );
			this.filter.disconnect( this.context.destination );
			this.gain.connect( this.context.destination );
			this.filter = null;

		}

		return this;

	}
```
</details>

### `AudioListener.getFilter(): AudioNode`

**JSDoc:**
```typescript
/**
	 * Returns the current set filter.
	 *
	 * @return {?AudioNode} The filter.
	 */
```

**Returns:** `AudioNode`

<details><summary>Code</summary>

```typescript
getFilter() {

		return this.filter;

	}
```
</details>

### `AudioListener.setFilter(value: AudioNode): AudioListener`

**JSDoc:**
```typescript
/**
	 * Sets the given filter to this listener.
	 *
	 * @param {AudioNode} value - The filter to set.
	 * @return {AudioListener} A reference to this listener.
	 */
```

**Parameters:**

- **`value`** `AudioNode`

**Returns:** `AudioListener`

**Calls:**

- `this.gain.disconnect`
- `this.filter.disconnect`
- `this.gain.connect`
- `this.filter.connect`

<details><summary>Code</summary>

```typescript
setFilter( value ) {

		if ( this.filter !== null ) {

			this.gain.disconnect( this.filter );
			this.filter.disconnect( this.context.destination );

		} else {

			this.gain.disconnect( this.context.destination );

		}

		this.filter = value;
		this.gain.connect( this.filter );
		this.filter.connect( this.context.destination );

		return this;

	}
```
</details>

### `AudioListener.getMasterVolume(): number`

**JSDoc:**
```typescript
/**
	 * Returns the applications master volume.
	 *
	 * @return {number} The master volume.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getMasterVolume() {

		return this.gain.gain.value;

	}
```
</details>

### `AudioListener.setMasterVolume(value: number): AudioListener`

**JSDoc:**
```typescript
/**
	 * Sets the applications master volume. This volume setting affects
	 * all audio nodes in the scene.
	 *
	 * @param {number} value - The master volume to set.
	 * @return {AudioListener} A reference to this listener.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `AudioListener`

**Calls:**

- `this.gain.gain.setTargetAtTime`

<details><summary>Code</summary>

```typescript
setMasterVolume( value ) {

		this.gain.gain.setTargetAtTime( value, this.context.currentTime, 0.01 );

		return this;

	}
```
</details>

### `AudioListener.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `super.updateMatrixWorld`
- `this._clock.getDelta`
- `this.matrixWorld.decompose`
- `_forward.set( 0, 0, - 1 ).applyQuaternion`
- `_up.set( 0, 1, 0 ).applyQuaternion`
- `listener.positionX.linearRampToValueAtTime`
- `listener.positionY.linearRampToValueAtTime`
- `listener.positionZ.linearRampToValueAtTime`
- `listener.forwardX.linearRampToValueAtTime`
- `listener.forwardY.linearRampToValueAtTime`
- `listener.forwardZ.linearRampToValueAtTime`
- `listener.upX.linearRampToValueAtTime`
- `listener.upY.linearRampToValueAtTime`
- `listener.upZ.linearRampToValueAtTime`
- `listener.setPosition`
- `listener.setOrientation`

**Internal Comments:**
```
// the initial forward and up directions must be orthogonal (x6)
// code path for Chrome (see #14393) (x2)
```

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		const listener = this.context.listener;

		this.timeDelta = this._clock.getDelta();

		this.matrixWorld.decompose( _position, _quaternion, _scale );

		// the initial forward and up directions must be orthogonal
		_forward.set( 0, 0, - 1 ).applyQuaternion( _quaternion );
		_up.set( 0, 1, 0 ).applyQuaternion( _quaternion );

		if ( listener.positionX ) {

			// code path for Chrome (see #14393)

			const endTime = this.context.currentTime + this.timeDelta;

			listener.positionX.linearRampToValueAtTime( _position.x, endTime );
			listener.positionY.linearRampToValueAtTime( _position.y, endTime );
			listener.positionZ.linearRampToValueAtTime( _position.z, endTime );
			listener.forwardX.linearRampToValueAtTime( _forward.x, endTime );
			listener.forwardY.linearRampToValueAtTime( _forward.y, endTime );
			listener.forwardZ.linearRampToValueAtTime( _forward.z, endTime );
			listener.upX.linearRampToValueAtTime( _up.x, endTime );
			listener.upY.linearRampToValueAtTime( _up.y, endTime );
			listener.upZ.linearRampToValueAtTime( _up.z, endTime );

		} else {

			listener.setPosition( _position.x, _position.y, _position.z );
			listener.setOrientation( _forward.x, _forward.y, _forward.z, _up.x, _up.y, _up.z );

		}

	}
```
</details>


---

## Classes

### `AudioListener`

<details><summary>Class Code</summary>

```ts
class AudioListener extends Object3D {

	/**
	 * Constructs a new audio listener.
	 */
	constructor() {

		super();

		this.type = 'AudioListener';

		/**
		 * The native audio context.
		 *
		 * @type {AudioContext}
		 * @readonly
		 */
		this.context = AudioContext.getContext();

		/**
		 * The gain node used for volume control.
		 *
		 * @type {GainNode}
		 * @readonly
		 */
		this.gain = this.context.createGain();
		this.gain.connect( this.context.destination );

		/**
		 * An optional filter.
		 *
		 * Defined via {@link AudioListener#setFilter}.
		 *
		 * @type {?AudioNode}
		 * @default null
		 * @readonly
		 */
		this.filter = null;

		/**
		 * Time delta values required for `linearRampToValueAtTime()` usage.
		 *
		 * @type {number}
		 * @default 0
		 * @readonly
		 */
		this.timeDelta = 0;

		// private

		this._clock = new Clock();

	}

	/**
	 * Returns the listener's input node.
	 *
	 * This method is used by other audio nodes to connect to this listener.
	 *
	 * @return {GainNode} The input node.
	 */
	getInput() {

		return this.gain;

	}

	/**
	 * Removes the current filter from this listener.
	 *
	 * @return {AudioListener} A reference to this listener.
	 */
	removeFilter() {

		if ( this.filter !== null ) {

			this.gain.disconnect( this.filter );
			this.filter.disconnect( this.context.destination );
			this.gain.connect( this.context.destination );
			this.filter = null;

		}

		return this;

	}

	/**
	 * Returns the current set filter.
	 *
	 * @return {?AudioNode} The filter.
	 */
	getFilter() {

		return this.filter;

	}

	/**
	 * Sets the given filter to this listener.
	 *
	 * @param {AudioNode} value - The filter to set.
	 * @return {AudioListener} A reference to this listener.
	 */
	setFilter( value ) {

		if ( this.filter !== null ) {

			this.gain.disconnect( this.filter );
			this.filter.disconnect( this.context.destination );

		} else {

			this.gain.disconnect( this.context.destination );

		}

		this.filter = value;
		this.gain.connect( this.filter );
		this.filter.connect( this.context.destination );

		return this;

	}

	/**
	 * Returns the applications master volume.
	 *
	 * @return {number} The master volume.
	 */
	getMasterVolume() {

		return this.gain.gain.value;

	}

	/**
	 * Sets the applications master volume. This volume setting affects
	 * all audio nodes in the scene.
	 *
	 * @param {number} value - The master volume to set.
	 * @return {AudioListener} A reference to this listener.
	 */
	setMasterVolume( value ) {

		this.gain.gain.setTargetAtTime( value, this.context.currentTime, 0.01 );

		return this;

	}

	updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		const listener = this.context.listener;

		this.timeDelta = this._clock.getDelta();

		this.matrixWorld.decompose( _position, _quaternion, _scale );

		// the initial forward and up directions must be orthogonal
		_forward.set( 0, 0, - 1 ).applyQuaternion( _quaternion );
		_up.set( 0, 1, 0 ).applyQuaternion( _quaternion );

		if ( listener.positionX ) {

			// code path for Chrome (see #14393)

			const endTime = this.context.currentTime + this.timeDelta;

			listener.positionX.linearRampToValueAtTime( _position.x, endTime );
			listener.positionY.linearRampToValueAtTime( _position.y, endTime );
			listener.positionZ.linearRampToValueAtTime( _position.z, endTime );
			listener.forwardX.linearRampToValueAtTime( _forward.x, endTime );
			listener.forwardY.linearRampToValueAtTime( _forward.y, endTime );
			listener.forwardZ.linearRampToValueAtTime( _forward.z, endTime );
			listener.upX.linearRampToValueAtTime( _up.x, endTime );
			listener.upY.linearRampToValueAtTime( _up.y, endTime );
			listener.upZ.linearRampToValueAtTime( _up.z, endTime );

		} else {

			listener.setPosition( _position.x, _position.y, _position.z );
			listener.setOrientation( _forward.x, _forward.y, _forward.z, _up.x, _up.y, _up.z );

		}

	}

}
```
</details>

#### Methods

##### `getInput(): GainNode`

<details><summary>Code</summary>

```ts
getInput() {

		return this.gain;

	}
```
</details>

##### `removeFilter(): AudioListener`

<details><summary>Code</summary>

```ts
removeFilter() {

		if ( this.filter !== null ) {

			this.gain.disconnect( this.filter );
			this.filter.disconnect( this.context.destination );
			this.gain.connect( this.context.destination );
			this.filter = null;

		}

		return this;

	}
```
</details>

##### `getFilter(): AudioNode`

<details><summary>Code</summary>

```ts
getFilter() {

		return this.filter;

	}
```
</details>

##### `setFilter(value: AudioNode): AudioListener`

<details><summary>Code</summary>

```ts
setFilter( value ) {

		if ( this.filter !== null ) {

			this.gain.disconnect( this.filter );
			this.filter.disconnect( this.context.destination );

		} else {

			this.gain.disconnect( this.context.destination );

		}

		this.filter = value;
		this.gain.connect( this.filter );
		this.filter.connect( this.context.destination );

		return this;

	}
```
</details>

##### `getMasterVolume(): number`

<details><summary>Code</summary>

```ts
getMasterVolume() {

		return this.gain.gain.value;

	}
```
</details>

##### `setMasterVolume(value: number): AudioListener`

<details><summary>Code</summary>

```ts
setMasterVolume( value ) {

		this.gain.gain.setTargetAtTime( value, this.context.currentTime, 0.01 );

		return this;

	}
```
</details>

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		const listener = this.context.listener;

		this.timeDelta = this._clock.getDelta();

		this.matrixWorld.decompose( _position, _quaternion, _scale );

		// the initial forward and up directions must be orthogonal
		_forward.set( 0, 0, - 1 ).applyQuaternion( _quaternion );
		_up.set( 0, 1, 0 ).applyQuaternion( _quaternion );

		if ( listener.positionX ) {

			// code path for Chrome (see #14393)

			const endTime = this.context.currentTime + this.timeDelta;

			listener.positionX.linearRampToValueAtTime( _position.x, endTime );
			listener.positionY.linearRampToValueAtTime( _position.y, endTime );
			listener.positionZ.linearRampToValueAtTime( _position.z, endTime );
			listener.forwardX.linearRampToValueAtTime( _forward.x, endTime );
			listener.forwardY.linearRampToValueAtTime( _forward.y, endTime );
			listener.forwardZ.linearRampToValueAtTime( _forward.z, endTime );
			listener.upX.linearRampToValueAtTime( _up.x, endTime );
			listener.upY.linearRampToValueAtTime( _up.y, endTime );
			listener.upZ.linearRampToValueAtTime( _up.z, endTime );

		} else {

			listener.setPosition( _position.x, _position.y, _position.z );
			listener.setOrientation( _forward.x, _forward.y, _forward.z, _up.x, _up.y, _up.z );

		}

	}
```
</details>


---