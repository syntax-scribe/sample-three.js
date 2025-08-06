[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AnimationClipCreator.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 29 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/animation/AnimationClipCreator.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationClip` | `three` |
| `BooleanKeyframeTrack` | `three` |
| `ColorKeyframeTrack` | `three` |
| `NumberKeyframeTrack` | `three` |
| `Vector3` | `three` |
| `VectorKeyframeTrack` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `times` | `number[]` | let/var | `[ 0, period ]` | ✗ |
| `values` | `number[]` | let/var | `[ 0, 360 ]` | ✗ |
| `trackName` | `string` | let/var | `'.rotation[' + axis + ']'` | ✗ |
| `track` | `any` | let/var | `new NumberKeyframeTrack( trackName, times, values )` | ✗ |
| `times` | `number[]` | let/var | `[ 0, period ]` | ✗ |
| `values` | `number[]` | let/var | `[ 0, 1 ]` | ✗ |
| `trackName` | `string` | let/var | `'.scale[' + axis + ']'` | ✗ |
| `track` | `any` | let/var | `new NumberKeyframeTrack( trackName, times, values )` | ✗ |
| `times` | `any[]` | let/var | `[]` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `tmp` | `any` | let/var | `new Vector3()` | ✗ |
| `trackName` | `".position"` | let/var | `'.position'` | ✗ |
| `track` | `any` | let/var | `new VectorKeyframeTrack( trackName, times, values )` | ✗ |
| `times` | `any[]` | let/var | `[]` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `tmp` | `any` | let/var | `new Vector3()` | ✗ |
| `scaleFactor` | `number` | let/var | `Math.random() * pulseScale` | ✗ |
| `trackName` | `".scale"` | let/var | `'.scale'` | ✗ |
| `track` | `any` | let/var | `new VectorKeyframeTrack( trackName, times, values )` | ✗ |
| `times` | `number[]` | let/var | `[ 0, duration / 2, duration ]` | ✗ |
| `values` | `boolean[]` | let/var | `[ true, false, true ]` | ✗ |
| `trackName` | `".visible"` | let/var | `'.visible'` | ✗ |
| `track` | `any` | let/var | `new BooleanKeyframeTrack( trackName, times, values )` | ✗ |
| `times` | `any[]` | let/var | `[]` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `timeStep` | `number` | let/var | `( colors.length > 1 ) ? duration / ( colors.length - 1 ) : 0` | ✗ |
| `color` | `Color` | let/var | `colors[ i ]` | ✗ |
| `trackName` | `".material.color"` | let/var | `'.material.color'` | ✗ |
| `track` | `any` | let/var | `new ColorKeyframeTrack( trackName, times, values )` | ✗ |


---

## Functions

### `AnimationClipCreator.CreateRotationAnimation(period: number, axis: "x" | "y" | "z"): AnimationClip`

**JSDoc:**
```typescript
/**
	 * Creates an animation clip that rotates a 3D object 360 degrees
	 * in the given period of time around the given axis.
	 *
	 * @param {number} period - The duration of the animation.
	 * @param {('x'|'y'|'z')} [axis='x'] - The axis of rotation.
	 * @return {AnimationClip} The created animation clip.
	 */
```

**Parameters:**

- **`period`** `number`
- **`axis`** `"x" | "y" | "z"`

**Returns:** `AnimationClip`

<details><summary>Code</summary>

```typescript
static CreateRotationAnimation( period, axis = 'x' ) {

		const times = [ 0, period ], values = [ 0, 360 ];

		const trackName = '.rotation[' + axis + ']';

		const track = new NumberKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', period, [ track ] );

	}
```
</details>

### `AnimationClipCreator.CreateScaleAxisAnimation(period: number, axis: "x" | "y" | "z"): AnimationClip`

**JSDoc:**
```typescript
/**
	 * Creates an animation clip that scales a 3D object from `0` to `1`
	 * in the given period of time along the given axis.
	 *
	 * @param {number} period - The duration of the animation.
	 * @param {('x'|'y'|'z')} [axis='x'] - The axis to scale the 3D object along.
	 * @return {AnimationClip} The created animation clip.
	 */
```

**Parameters:**

- **`period`** `number`
- **`axis`** `"x" | "y" | "z"`

**Returns:** `AnimationClip`

<details><summary>Code</summary>

```typescript
static CreateScaleAxisAnimation( period, axis = 'x' ) {

		const times = [ 0, period ], values = [ 0, 1 ];

		const trackName = '.scale[' + axis + ']';

		const track = new NumberKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', period, [ track ] );

	}
```
</details>

### `AnimationClipCreator.CreateShakeAnimation(duration: number, shakeScale: Vector3): AnimationClip`

**JSDoc:**
```typescript
/**
	 * Creates an animation clip that translates a 3D object in a shake pattern
	 * in the given period.
	 *
	 * @param {number} duration - The duration of the animation.
	 * @param {Vector3} shakeScale - The scale of the shake.
	 * @return {AnimationClip} The created animation clip.
	 */
```

**Parameters:**

- **`duration`** `number`
- **`shakeScale`** `Vector3`

**Returns:** `AnimationClip`

**Calls:**

- `times.push`
- `tmp.set( Math.random() * 2.0 - 1.0, Math.random() * 2.0 - 1.0, Math.random() * 2.0 - 1.0 ).
				multiply( shakeScale ).
				toArray`

<details><summary>Code</summary>

```typescript
static CreateShakeAnimation( duration, shakeScale ) {

		const times = [], values = [], tmp = new Vector3();

		for ( let i = 0; i < duration * 10; i ++ ) {

			times.push( i / 10 );

			tmp.set( Math.random() * 2.0 - 1.0, Math.random() * 2.0 - 1.0, Math.random() * 2.0 - 1.0 ).
				multiply( shakeScale ).
				toArray( values, values.length );

		}

		const trackName = '.position';

		const track = new VectorKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}
```
</details>

### `AnimationClipCreator.CreatePulsationAnimation(duration: number, pulseScale: number): AnimationClip`

**JSDoc:**
```typescript
/**
	 * Creates an animation clip that scales a 3D object in a pulse pattern
	 * in the given period.
	 *
	 * @param {number} duration - The duration of the animation.
	 * @param {number} pulseScale - The scale of the pulse.
	 * @return {AnimationClip} The created animation clip.
	 */
```

**Parameters:**

- **`duration`** `number`
- **`pulseScale`** `number`

**Returns:** `AnimationClip`

**Calls:**

- `times.push`
- `Math.random`
- `tmp.set( scaleFactor, scaleFactor, scaleFactor ).
				toArray`

<details><summary>Code</summary>

```typescript
static CreatePulsationAnimation( duration, pulseScale ) {

		const times = [], values = [], tmp = new Vector3();

		for ( let i = 0; i < duration * 10; i ++ ) {

			times.push( i / 10 );

			const scaleFactor = Math.random() * pulseScale;
			tmp.set( scaleFactor, scaleFactor, scaleFactor ).
				toArray( values, values.length );

		}

		const trackName = '.scale';

		const track = new VectorKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}
```
</details>

### `AnimationClipCreator.CreateVisibilityAnimation(duration: number): AnimationClip`

**JSDoc:**
```typescript
/**
	 * Creates an animation clip that toggles the visibility of a 3D object.
	 *
	 * @param {number} duration - The duration of the animation.
	 * @return {AnimationClip} The created animation clip.
	 */
```

**Parameters:**

- **`duration`** `number`

**Returns:** `AnimationClip`

<details><summary>Code</summary>

```typescript
static CreateVisibilityAnimation( duration ) {

		const times = [ 0, duration / 2, duration ], values = [ true, false, true ];

		const trackName = '.visible';

		const track = new BooleanKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}
```
</details>

### `AnimationClipCreator.CreateMaterialColorAnimation(duration: number, colors: Color[]): AnimationClip`

**JSDoc:**
```typescript
/**
	 * Creates an animation clip that animates the `color` property of a 3D object's
	 * material.
	 *
	 * @param {number} duration - The duration of the animation.
	 * @param {Array<Color>} colors - An array of colors that should be sequentially animated.
	 * @return {AnimationClip} The created animation clip.
	 */
```

**Parameters:**

- **`duration`** `number`
- **`colors`** `Color[]`

**Returns:** `AnimationClip`

**Calls:**

- `times.push`
- `values.push`

<details><summary>Code</summary>

```typescript
static CreateMaterialColorAnimation( duration, colors ) {

		const times = [], values = [],
			timeStep = ( colors.length > 1 ) ? duration / ( colors.length - 1 ) : 0;

		for ( let i = 0; i < colors.length; i ++ ) {

			times.push( i * timeStep );

			const color = colors[ i ];
			values.push( color.r, color.g, color.b );

		}

		const trackName = '.material.color';

		const track = new ColorKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}
```
</details>


---

## Classes

### `AnimationClipCreator`

<details><summary>Class Code</summary>

```ts
class AnimationClipCreator {

	/**
	 * Creates an animation clip that rotates a 3D object 360 degrees
	 * in the given period of time around the given axis.
	 *
	 * @param {number} period - The duration of the animation.
	 * @param {('x'|'y'|'z')} [axis='x'] - The axis of rotation.
	 * @return {AnimationClip} The created animation clip.
	 */
	static CreateRotationAnimation( period, axis = 'x' ) {

		const times = [ 0, period ], values = [ 0, 360 ];

		const trackName = '.rotation[' + axis + ']';

		const track = new NumberKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', period, [ track ] );

	}

	/**
	 * Creates an animation clip that scales a 3D object from `0` to `1`
	 * in the given period of time along the given axis.
	 *
	 * @param {number} period - The duration of the animation.
	 * @param {('x'|'y'|'z')} [axis='x'] - The axis to scale the 3D object along.
	 * @return {AnimationClip} The created animation clip.
	 */
	static CreateScaleAxisAnimation( period, axis = 'x' ) {

		const times = [ 0, period ], values = [ 0, 1 ];

		const trackName = '.scale[' + axis + ']';

		const track = new NumberKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', period, [ track ] );

	}

	/**
	 * Creates an animation clip that translates a 3D object in a shake pattern
	 * in the given period.
	 *
	 * @param {number} duration - The duration of the animation.
	 * @param {Vector3} shakeScale - The scale of the shake.
	 * @return {AnimationClip} The created animation clip.
	 */
	static CreateShakeAnimation( duration, shakeScale ) {

		const times = [], values = [], tmp = new Vector3();

		for ( let i = 0; i < duration * 10; i ++ ) {

			times.push( i / 10 );

			tmp.set( Math.random() * 2.0 - 1.0, Math.random() * 2.0 - 1.0, Math.random() * 2.0 - 1.0 ).
				multiply( shakeScale ).
				toArray( values, values.length );

		}

		const trackName = '.position';

		const track = new VectorKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}

	/**
	 * Creates an animation clip that scales a 3D object in a pulse pattern
	 * in the given period.
	 *
	 * @param {number} duration - The duration of the animation.
	 * @param {number} pulseScale - The scale of the pulse.
	 * @return {AnimationClip} The created animation clip.
	 */
	static CreatePulsationAnimation( duration, pulseScale ) {

		const times = [], values = [], tmp = new Vector3();

		for ( let i = 0; i < duration * 10; i ++ ) {

			times.push( i / 10 );

			const scaleFactor = Math.random() * pulseScale;
			tmp.set( scaleFactor, scaleFactor, scaleFactor ).
				toArray( values, values.length );

		}

		const trackName = '.scale';

		const track = new VectorKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}

	/**
	 * Creates an animation clip that toggles the visibility of a 3D object.
	 *
	 * @param {number} duration - The duration of the animation.
	 * @return {AnimationClip} The created animation clip.
	 */
	static CreateVisibilityAnimation( duration ) {

		const times = [ 0, duration / 2, duration ], values = [ true, false, true ];

		const trackName = '.visible';

		const track = new BooleanKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}

	/**
	 * Creates an animation clip that animates the `color` property of a 3D object's
	 * material.
	 *
	 * @param {number} duration - The duration of the animation.
	 * @param {Array<Color>} colors - An array of colors that should be sequentially animated.
	 * @return {AnimationClip} The created animation clip.
	 */
	static CreateMaterialColorAnimation( duration, colors ) {

		const times = [], values = [],
			timeStep = ( colors.length > 1 ) ? duration / ( colors.length - 1 ) : 0;

		for ( let i = 0; i < colors.length; i ++ ) {

			times.push( i * timeStep );

			const color = colors[ i ];
			values.push( color.r, color.g, color.b );

		}

		const trackName = '.material.color';

		const track = new ColorKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}

}
```
</details>

#### Methods

##### `CreateRotationAnimation(period: number, axis: "x" | "y" | "z"): AnimationClip`

<details><summary>Code</summary>

```ts
static CreateRotationAnimation( period, axis = 'x' ) {

		const times = [ 0, period ], values = [ 0, 360 ];

		const trackName = '.rotation[' + axis + ']';

		const track = new NumberKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', period, [ track ] );

	}
```
</details>

##### `CreateScaleAxisAnimation(period: number, axis: "x" | "y" | "z"): AnimationClip`

<details><summary>Code</summary>

```ts
static CreateScaleAxisAnimation( period, axis = 'x' ) {

		const times = [ 0, period ], values = [ 0, 1 ];

		const trackName = '.scale[' + axis + ']';

		const track = new NumberKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', period, [ track ] );

	}
```
</details>

##### `CreateShakeAnimation(duration: number, shakeScale: Vector3): AnimationClip`

<details><summary>Code</summary>

```ts
static CreateShakeAnimation( duration, shakeScale ) {

		const times = [], values = [], tmp = new Vector3();

		for ( let i = 0; i < duration * 10; i ++ ) {

			times.push( i / 10 );

			tmp.set( Math.random() * 2.0 - 1.0, Math.random() * 2.0 - 1.0, Math.random() * 2.0 - 1.0 ).
				multiply( shakeScale ).
				toArray( values, values.length );

		}

		const trackName = '.position';

		const track = new VectorKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}
```
</details>

##### `CreatePulsationAnimation(duration: number, pulseScale: number): AnimationClip`

<details><summary>Code</summary>

```ts
static CreatePulsationAnimation( duration, pulseScale ) {

		const times = [], values = [], tmp = new Vector3();

		for ( let i = 0; i < duration * 10; i ++ ) {

			times.push( i / 10 );

			const scaleFactor = Math.random() * pulseScale;
			tmp.set( scaleFactor, scaleFactor, scaleFactor ).
				toArray( values, values.length );

		}

		const trackName = '.scale';

		const track = new VectorKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}
```
</details>

##### `CreateVisibilityAnimation(duration: number): AnimationClip`

<details><summary>Code</summary>

```ts
static CreateVisibilityAnimation( duration ) {

		const times = [ 0, duration / 2, duration ], values = [ true, false, true ];

		const trackName = '.visible';

		const track = new BooleanKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}
```
</details>

##### `CreateMaterialColorAnimation(duration: number, colors: Color[]): AnimationClip`

<details><summary>Code</summary>

```ts
static CreateMaterialColorAnimation( duration, colors ) {

		const times = [], values = [],
			timeStep = ( colors.length > 1 ) ? duration / ( colors.length - 1 ) : 0;

		for ( let i = 0; i < colors.length; i ++ ) {

			times.push( i * timeStep );

			const color = colors[ i ];
			values.push( color.r, color.g, color.b );

		}

		const trackName = '.material.color';

		const track = new ColorKeyframeTrack( trackName, times, values );

		return new AnimationClip( '', duration, [ track ] );

	}
```
</details>


---