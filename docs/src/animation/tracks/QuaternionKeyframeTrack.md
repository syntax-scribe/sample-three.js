[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `QuaternionKeyframeTrack.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/animation/tracks/QuaternionKeyframeTrack.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `KeyframeTrack` | `../KeyframeTrack.js` |
| `QuaternionLinearInterpolant` | `../../math/interpolants/QuaternionLinearInterpolant.js` |


---

## Functions

### `QuaternionKeyframeTrack.InterpolantFactoryMethodLinear(result: TypedArray): QuaternionLinearInterpolant`

**JSDoc:**
```typescript
/**
	 * Overwritten so the method returns Quaternion based interpolant.
	 *
	 * @static
	 * @param {TypedArray} [result] - The result buffer.
	 * @return {QuaternionLinearInterpolant} The new interpolant.
	 */
```

**Parameters:**

- **`result`** `TypedArray`

**Returns:** `QuaternionLinearInterpolant`

**Calls:**

- `this.getValueSize`

<details><summary>Code</summary>

```typescript
InterpolantFactoryMethodLinear( result ) {

		return new QuaternionLinearInterpolant( this.times, this.values, this.getValueSize(), result );

	}
```
</details>


---

## Classes

### `QuaternionKeyframeTrack`

<details><summary>Class Code</summary>

```ts
class QuaternionKeyframeTrack extends KeyframeTrack {

	/**
	 * Constructs a new Quaternion keyframe track.
	 *
	 * @param {string} name - The keyframe track's name.
	 * @param {Array<number>} times - A list of keyframe times.
	 * @param {Array<number>} values - A list of keyframe values.
	 * @param {(InterpolateLinear|InterpolateDiscrete|InterpolateSmooth)} [interpolation] - The interpolation type.
	 */
	constructor( name, times, values, interpolation ) {

		super( name, times, values, interpolation );

	}

	/**
	 * Overwritten so the method returns Quaternion based interpolant.
	 *
	 * @static
	 * @param {TypedArray} [result] - The result buffer.
	 * @return {QuaternionLinearInterpolant} The new interpolant.
	 */
	InterpolantFactoryMethodLinear( result ) {

		return new QuaternionLinearInterpolant( this.times, this.values, this.getValueSize(), result );

	}

}
```
</details>

#### Methods

##### `InterpolantFactoryMethodLinear(result: TypedArray): QuaternionLinearInterpolant`

<details><summary>Code</summary>

```ts
InterpolantFactoryMethodLinear( result ) {

		return new QuaternionLinearInterpolant( this.times, this.values, this.getValueSize(), result );

	}
```
</details>


---