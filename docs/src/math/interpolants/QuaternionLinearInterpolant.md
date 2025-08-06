[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `QuaternionLinearInterpolant.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/interpolants/QuaternionLinearInterpolant.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Interpolant` | `../Interpolant.js` |
| `Quaternion` | `../Quaternion.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `result` | `TypedArray` | let/var | `this.resultBuffer` | ✗ |
| `values` | `TypedArray` | let/var | `this.sampleValues` | ✗ |
| `stride` | `TypedArray` | let/var | `this.valueSize` | ✗ |
| `alpha` | `number` | let/var | `( t - t0 ) / ( t1 - t0 )` | ✗ |
| `offset` | `number` | let/var | `i1 * stride` | ✗ |


---

## Functions

### `QuaternionLinearInterpolant.interpolate_(i1: any, t0: any, t: any, t1: any): TypedArray`

**Parameters:**

- **`i1`** `any`
- **`t0`** `any`
- **`t`** `any`
- **`t1`** `any`

**Returns:** `TypedArray`

**Calls:**

- `Quaternion.slerpFlat`

<details><summary>Code</summary>

```typescript
interpolate_( i1, t0, t, t1 ) {

		const result = this.resultBuffer,
			values = this.sampleValues,
			stride = this.valueSize,

			alpha = ( t - t0 ) / ( t1 - t0 );

		let offset = i1 * stride;

		for ( let end = offset + stride; offset !== end; offset += 4 ) {

			Quaternion.slerpFlat( result, 0, values, offset - stride, values, offset, alpha );

		}

		return result;

	}
```
</details>


---

## Classes

### `QuaternionLinearInterpolant`

<details><summary>Class Code</summary>

```ts
class QuaternionLinearInterpolant extends Interpolant {

	/**
	 * Constructs a new SLERP interpolant.
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

			alpha = ( t - t0 ) / ( t1 - t0 );

		let offset = i1 * stride;

		for ( let end = offset + stride; offset !== end; offset += 4 ) {

			Quaternion.slerpFlat( result, 0, values, offset - stride, values, offset, alpha );

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

			alpha = ( t - t0 ) / ( t1 - t0 );

		let offset = i1 * stride;

		for ( let end = offset + stride; offset !== end; offset += 4 ) {

			Quaternion.slerpFlat( result, 0, values, offset - stride, values, offset, alpha );

		}

		return result;

	}
```
</details>


---