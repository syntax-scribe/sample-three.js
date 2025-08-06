[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PositionalAudio.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/audio/PositionalAudio.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `Quaternion` | `../math/Quaternion.js` |
| `Audio` | `./Audio.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_position` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_quaternion` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `_scale` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_orientation` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `panner` | `PannerNode` | let/var | `this.panner` | ✗ |
| `endTime` | `any` | let/var | `this.context.currentTime + this.listener.timeDelta` | ✗ |


---

## Functions

### `PositionalAudio.connect(): this`

**Returns:** `this`

**Calls:**

- `super.connect`
- `this.panner.connect`

<details><summary>Code</summary>

```typescript
connect() {

		super.connect();

		this.panner.connect( this.gain );

		return this;

	}
```
</details>

### `PositionalAudio.disconnect(): this`

**Returns:** `this`

**Calls:**

- `super.disconnect`
- `this.panner.disconnect`

<details><summary>Code</summary>

```typescript
disconnect() {

		super.disconnect();

		this.panner.disconnect( this.gain );

		return this;

	}
```
</details>

### `PositionalAudio.getOutput(): PannerNode`

**Returns:** `PannerNode`

<details><summary>Code</summary>

```typescript
getOutput() {

		return this.panner;

	}
```
</details>

### `PositionalAudio.getRefDistance(): number`

**JSDoc:**
```typescript
/**
	 * Returns the current reference distance.
	 *
	 * @return {number} The reference distance.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getRefDistance() {

		return this.panner.refDistance;

	}
```
</details>

### `PositionalAudio.setRefDistance(value: number): PositionalAudio`

**JSDoc:**
```typescript
/**
	 * Defines the reference distance for reducing volume as the audio source moves
	 * further from the listener – i.e. the distance at which the volume reduction
	 * starts taking effect.
	 *
	 * @param {number} value - The reference distance to set.
	 * @return {PositionalAudio} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `PositionalAudio`

<details><summary>Code</summary>

```typescript
setRefDistance( value ) {

		this.panner.refDistance = value;

		return this;

	}
```
</details>

### `PositionalAudio.getRolloffFactor(): number`

**JSDoc:**
```typescript
/**
	 * Returns the current rolloff factor.
	 *
	 * @return {number} The rolloff factor.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getRolloffFactor() {

		return this.panner.rolloffFactor;

	}
```
</details>

### `PositionalAudio.setRolloffFactor(value: number): PositionalAudio`

**JSDoc:**
```typescript
/**
	 * Defines how quickly the volume is reduced as the source moves away from the listener.
	 *
	 * @param {number} value - The rolloff factor.
	 * @return {PositionalAudio} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `PositionalAudio`

<details><summary>Code</summary>

```typescript
setRolloffFactor( value ) {

		this.panner.rolloffFactor = value;

		return this;

	}
```
</details>

### `PositionalAudio.getDistanceModel(): "linear" | "inverse" | "exponential"`

**JSDoc:**
```typescript
/**
	 * Returns the current distance model.
	 *
	 * @return {('linear'|'inverse'|'exponential')} The distance model.
	 */
```

**Returns:** `"linear" | "inverse" | "exponential"`

<details><summary>Code</summary>

```typescript
getDistanceModel() {

		return this.panner.distanceModel;

	}
```
</details>

### `PositionalAudio.setDistanceModel(value: "linear" | "inverse" | "exponential"): PositionalAudio`

**JSDoc:**
```typescript
/**
	 * Defines which algorithm to use to reduce the volume of the audio source
	 * as it moves away from the listener.
	 *
	 * Read [the spec]{@link https://www.w3.org/TR/webaudio-1.1/#enumdef-distancemodeltype}
	 * for more details.
	 *
	 * @param {('linear'|'inverse'|'exponential')} value - The distance model to set.
	 * @return {PositionalAudio} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `"linear" | "inverse" | "exponential"`

**Returns:** `PositionalAudio`

<details><summary>Code</summary>

```typescript
setDistanceModel( value ) {

		this.panner.distanceModel = value;

		return this;

	}
```
</details>

### `PositionalAudio.getMaxDistance(): number`

**JSDoc:**
```typescript
/**
	 * Returns the current max distance.
	 *
	 * @return {number} The max distance.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getMaxDistance() {

		return this.panner.maxDistance;

	}
```
</details>

### `PositionalAudio.setMaxDistance(value: number): PositionalAudio`

**JSDoc:**
```typescript
/**
	 * Defines the maximum distance between the audio source and the listener,
	 * after which the volume is not reduced any further.
	 *
	 * This value is used only by the `linear` distance model.
	 *
	 * @param {number} value - The max distance.
	 * @return {PositionalAudio} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `PositionalAudio`

<details><summary>Code</summary>

```typescript
setMaxDistance( value ) {

		this.panner.maxDistance = value;

		return this;

	}
```
</details>

### `PositionalAudio.setDirectionalCone(coneInnerAngle: number, coneOuterAngle: number, coneOuterGain: number): PositionalAudio`

**JSDoc:**
```typescript
/**
	 * Sets the directional cone in which the audio can be listened.
	 *
	 * @param {number} coneInnerAngle - An angle, in degrees, of a cone inside of which there will be no volume reduction.
	 * @param {number} coneOuterAngle - An angle, in degrees, of a cone outside of which the volume will be reduced by a constant value, defined by the `coneOuterGain` parameter.
	 * @param {number} coneOuterGain - The amount of volume reduction outside the cone defined by the `coneOuterAngle`. When set to `0`, no sound can be heard.
	 * @return {PositionalAudio} A reference to this instance.
	 */
```

**Parameters:**

- **`coneInnerAngle`** `number`
- **`coneOuterAngle`** `number`
- **`coneOuterGain`** `number`

**Returns:** `PositionalAudio`

<details><summary>Code</summary>

```typescript
setDirectionalCone( coneInnerAngle, coneOuterAngle, coneOuterGain ) {

		this.panner.coneInnerAngle = coneInnerAngle;
		this.panner.coneOuterAngle = coneOuterAngle;
		this.panner.coneOuterGain = coneOuterGain;

		return this;

	}
```
</details>

### `PositionalAudio.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `super.updateMatrixWorld`
- `this.matrixWorld.decompose`
- `_orientation.set( 0, 0, 1 ).applyQuaternion`
- `panner.positionX.linearRampToValueAtTime`
- `panner.positionY.linearRampToValueAtTime`
- `panner.positionZ.linearRampToValueAtTime`
- `panner.orientationX.linearRampToValueAtTime`
- `panner.orientationY.linearRampToValueAtTime`
- `panner.orientationZ.linearRampToValueAtTime`
- `panner.setPosition`
- `panner.setOrientation`

**Internal Comments:**
```
// code path for Chrome and Firefox (see #14393) (x2)
```

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( this.hasPlaybackControl === true && this.isPlaying === false ) return;

		this.matrixWorld.decompose( _position, _quaternion, _scale );

		_orientation.set( 0, 0, 1 ).applyQuaternion( _quaternion );

		const panner = this.panner;

		if ( panner.positionX ) {

			// code path for Chrome and Firefox (see #14393)

			const endTime = this.context.currentTime + this.listener.timeDelta;

			panner.positionX.linearRampToValueAtTime( _position.x, endTime );
			panner.positionY.linearRampToValueAtTime( _position.y, endTime );
			panner.positionZ.linearRampToValueAtTime( _position.z, endTime );
			panner.orientationX.linearRampToValueAtTime( _orientation.x, endTime );
			panner.orientationY.linearRampToValueAtTime( _orientation.y, endTime );
			panner.orientationZ.linearRampToValueAtTime( _orientation.z, endTime );

		} else {

			panner.setPosition( _position.x, _position.y, _position.z );
			panner.setOrientation( _orientation.x, _orientation.y, _orientation.z );

		}

	}
```
</details>


---

## Classes

### `PositionalAudio`

<details><summary>Class Code</summary>

```ts
class PositionalAudio extends Audio {

	/**
	 * Constructs a positional audio.
	 *
	 * @param {AudioListener} listener - The global audio listener.
	 */
	constructor( listener ) {

		super( listener );

		/**
		 * The panner node represents the location, direction, and behavior of an audio
		 * source in 3D space.
		 *
		 * @type {PannerNode}
		 * @readonly
		 */
		this.panner = this.context.createPanner();
		this.panner.panningModel = 'HRTF';
		this.panner.connect( this.gain );

	}

	connect() {

		super.connect();

		this.panner.connect( this.gain );

		return this;

	}

	disconnect() {

		super.disconnect();

		this.panner.disconnect( this.gain );

		return this;

	}

	getOutput() {

		return this.panner;

	}

	/**
	 * Returns the current reference distance.
	 *
	 * @return {number} The reference distance.
	 */
	getRefDistance() {

		return this.panner.refDistance;

	}

	/**
	 * Defines the reference distance for reducing volume as the audio source moves
	 * further from the listener – i.e. the distance at which the volume reduction
	 * starts taking effect.
	 *
	 * @param {number} value - The reference distance to set.
	 * @return {PositionalAudio} A reference to this instance.
	 */
	setRefDistance( value ) {

		this.panner.refDistance = value;

		return this;

	}

	/**
	 * Returns the current rolloff factor.
	 *
	 * @return {number} The rolloff factor.
	 */
	getRolloffFactor() {

		return this.panner.rolloffFactor;

	}

	/**
	 * Defines how quickly the volume is reduced as the source moves away from the listener.
	 *
	 * @param {number} value - The rolloff factor.
	 * @return {PositionalAudio} A reference to this instance.
	 */
	setRolloffFactor( value ) {

		this.panner.rolloffFactor = value;

		return this;

	}

	/**
	 * Returns the current distance model.
	 *
	 * @return {('linear'|'inverse'|'exponential')} The distance model.
	 */
	getDistanceModel() {

		return this.panner.distanceModel;

	}

	/**
	 * Defines which algorithm to use to reduce the volume of the audio source
	 * as it moves away from the listener.
	 *
	 * Read [the spec]{@link https://www.w3.org/TR/webaudio-1.1/#enumdef-distancemodeltype}
	 * for more details.
	 *
	 * @param {('linear'|'inverse'|'exponential')} value - The distance model to set.
	 * @return {PositionalAudio} A reference to this instance.
	 */
	setDistanceModel( value ) {

		this.panner.distanceModel = value;

		return this;

	}

	/**
	 * Returns the current max distance.
	 *
	 * @return {number} The max distance.
	 */
	getMaxDistance() {

		return this.panner.maxDistance;

	}

	/**
	 * Defines the maximum distance between the audio source and the listener,
	 * after which the volume is not reduced any further.
	 *
	 * This value is used only by the `linear` distance model.
	 *
	 * @param {number} value - The max distance.
	 * @return {PositionalAudio} A reference to this instance.
	 */
	setMaxDistance( value ) {

		this.panner.maxDistance = value;

		return this;

	}

	/**
	 * Sets the directional cone in which the audio can be listened.
	 *
	 * @param {number} coneInnerAngle - An angle, in degrees, of a cone inside of which there will be no volume reduction.
	 * @param {number} coneOuterAngle - An angle, in degrees, of a cone outside of which the volume will be reduced by a constant value, defined by the `coneOuterGain` parameter.
	 * @param {number} coneOuterGain - The amount of volume reduction outside the cone defined by the `coneOuterAngle`. When set to `0`, no sound can be heard.
	 * @return {PositionalAudio} A reference to this instance.
	 */
	setDirectionalCone( coneInnerAngle, coneOuterAngle, coneOuterGain ) {

		this.panner.coneInnerAngle = coneInnerAngle;
		this.panner.coneOuterAngle = coneOuterAngle;
		this.panner.coneOuterGain = coneOuterGain;

		return this;

	}

	updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( this.hasPlaybackControl === true && this.isPlaying === false ) return;

		this.matrixWorld.decompose( _position, _quaternion, _scale );

		_orientation.set( 0, 0, 1 ).applyQuaternion( _quaternion );

		const panner = this.panner;

		if ( panner.positionX ) {

			// code path for Chrome and Firefox (see #14393)

			const endTime = this.context.currentTime + this.listener.timeDelta;

			panner.positionX.linearRampToValueAtTime( _position.x, endTime );
			panner.positionY.linearRampToValueAtTime( _position.y, endTime );
			panner.positionZ.linearRampToValueAtTime( _position.z, endTime );
			panner.orientationX.linearRampToValueAtTime( _orientation.x, endTime );
			panner.orientationY.linearRampToValueAtTime( _orientation.y, endTime );
			panner.orientationZ.linearRampToValueAtTime( _orientation.z, endTime );

		} else {

			panner.setPosition( _position.x, _position.y, _position.z );
			panner.setOrientation( _orientation.x, _orientation.y, _orientation.z );

		}

	}

}
```
</details>

#### Methods

##### `connect(): this`

<details><summary>Code</summary>

```ts
connect() {

		super.connect();

		this.panner.connect( this.gain );

		return this;

	}
```
</details>

##### `disconnect(): this`

<details><summary>Code</summary>

```ts
disconnect() {

		super.disconnect();

		this.panner.disconnect( this.gain );

		return this;

	}
```
</details>

##### `getOutput(): PannerNode`

<details><summary>Code</summary>

```ts
getOutput() {

		return this.panner;

	}
```
</details>

##### `getRefDistance(): number`

<details><summary>Code</summary>

```ts
getRefDistance() {

		return this.panner.refDistance;

	}
```
</details>

##### `setRefDistance(value: number): PositionalAudio`

<details><summary>Code</summary>

```ts
setRefDistance( value ) {

		this.panner.refDistance = value;

		return this;

	}
```
</details>

##### `getRolloffFactor(): number`

<details><summary>Code</summary>

```ts
getRolloffFactor() {

		return this.panner.rolloffFactor;

	}
```
</details>

##### `setRolloffFactor(value: number): PositionalAudio`

<details><summary>Code</summary>

```ts
setRolloffFactor( value ) {

		this.panner.rolloffFactor = value;

		return this;

	}
```
</details>

##### `getDistanceModel(): "linear" | "inverse" | "exponential"`

<details><summary>Code</summary>

```ts
getDistanceModel() {

		return this.panner.distanceModel;

	}
```
</details>

##### `setDistanceModel(value: "linear" | "inverse" | "exponential"): PositionalAudio`

<details><summary>Code</summary>

```ts
setDistanceModel( value ) {

		this.panner.distanceModel = value;

		return this;

	}
```
</details>

##### `getMaxDistance(): number`

<details><summary>Code</summary>

```ts
getMaxDistance() {

		return this.panner.maxDistance;

	}
```
</details>

##### `setMaxDistance(value: number): PositionalAudio`

<details><summary>Code</summary>

```ts
setMaxDistance( value ) {

		this.panner.maxDistance = value;

		return this;

	}
```
</details>

##### `setDirectionalCone(coneInnerAngle: number, coneOuterAngle: number, coneOuterGain: number): PositionalAudio`

<details><summary>Code</summary>

```ts
setDirectionalCone( coneInnerAngle, coneOuterAngle, coneOuterGain ) {

		this.panner.coneInnerAngle = coneInnerAngle;
		this.panner.coneOuterAngle = coneOuterAngle;
		this.panner.coneOuterGain = coneOuterGain;

		return this;

	}
```
</details>

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( this.hasPlaybackControl === true && this.isPlaying === false ) return;

		this.matrixWorld.decompose( _position, _quaternion, _scale );

		_orientation.set( 0, 0, 1 ).applyQuaternion( _quaternion );

		const panner = this.panner;

		if ( panner.positionX ) {

			// code path for Chrome and Firefox (see #14393)

			const endTime = this.context.currentTime + this.listener.timeDelta;

			panner.positionX.linearRampToValueAtTime( _position.x, endTime );
			panner.positionY.linearRampToValueAtTime( _position.y, endTime );
			panner.positionZ.linearRampToValueAtTime( _position.z, endTime );
			panner.orientationX.linearRampToValueAtTime( _orientation.x, endTime );
			panner.orientationY.linearRampToValueAtTime( _orientation.y, endTime );
			panner.orientationZ.linearRampToValueAtTime( _orientation.z, endTime );

		} else {

			panner.setPosition( _position.x, _position.y, _position.z );
			panner.setOrientation( _orientation.x, _orientation.y, _orientation.z );

		}

	}
```
</details>


---