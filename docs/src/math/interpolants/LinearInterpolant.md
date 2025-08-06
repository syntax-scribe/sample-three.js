[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LinearInterpolant.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/interpolants/LinearInterpolant.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Interpolant` | `../Interpolant.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `result` | `TypedArray` | let/var | `this.resultBuffer` | ✗ |
| `values` | `TypedArray` | let/var | `this.sampleValues` | ✗ |
| `stride` | `TypedArray` | let/var | `this.valueSize` | ✗ |
| `offset1` | `number` | let/var | `i1 * stride` | ✗ |
| `offset0` | `number` | let/var | `offset1 - stride` | ✗ |
| `weight1` | `number` | let/var | `( t - t0 ) / ( t1 - t0 )` | ✗ |
| `weight0` | `number` | let/var | `1 - weight1` | ✗ |


---

## Functions

### `LinearInterpolant.interpolate_(i1: any, t0: any, t: any, t1: any): TypedArray`

**Parameters:**

- **`i1`** `any`
- **`t0`** `any`
- **`t`** `any`
- **`t1`** `any`

**Returns:** `TypedArray`

<details><summary>Code</summary>

```typescript
interpolate_( i1, t0, t, t1 ) {

		const result = this.resultBuffer,
			values = this.sampleValues,
			stride = this.valueSize,

			offset1 = i1 * stride,
			offset0 = offset1 - stride,

			weight1 = ( t - t0 ) / ( t1 - t0 ),
			weight0 = 1 - weight1;

		for ( let i = 0; i !== stride; ++ i ) {

			result[ i ] =
					values[ offset0 + i ] * weight0 +
					values[ offset1 + i ] * weight1;

		}

		return result;

	}
```
</details>


---

## Classes

### `LinearInterpolant`

<details><summary>Class Code</summary>

```ts
class LinearInterpolant extends Interpolant {

	/**
	 * Constructs a new linear interpolant.
	 *
	 * @param {TypedArray} parameterPositions - The parameter positions hold the interpolation factors.
	 * @param {TypedArray} sampleValues - The sample values.
	 * @param {number} sampleSize - The sample size
	 * @param {TypedArray} [resultBuffer] - The result buffer.
	 */
	constructor( parameterPositions, sampleValues, sampleSize, resultBuffer ) {

		super( parameterPositions, sampleValues, sampleSize, resultBuffer );

	}

	interpolate_( i1, t0, t, t1 ) {

		const result = this.resultBuffer,
			values = this.sampleValues,
			stride = this.valueSize,

			offset1 = i1 * stride,
			offset0 = offset1 - stride,

			weight1 = ( t - t0 ) / ( t1 - t0 ),
			weight0 = 1 - weight1;

		for ( let i = 0; i !== stride; ++ i ) {

			result[ i ] =
					values[ offset0 + i ] * weight0 +
					values[ offset1 + i ] * weight1;

		}

		return result;

	}

}
```
</details>

#### Methods

##### `interpolate_(i1: any, t0: any, t: any, t1: any): TypedArray`

<details><summary>Code</summary>

```ts
interpolate_( i1, t0, t, t1 ) {

		const result = this.resultBuffer,
			values = this.sampleValues,
			stride = this.valueSize,

			offset1 = i1 * stride,
			offset0 = offset1 - stride,

			weight1 = ( t - t0 ) / ( t1 - t0 ),
			weight0 = 1 - weight1;

		for ( let i = 0; i !== stride; ++ i ) {

			result[ i ] =
					values[ offset0 + i ] * weight0 +
					values[ offset1 + i ] * weight1;

		}

		return result;

	}
```
</details>


---