[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DiscreteInterpolant.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/interpolants/DiscreteInterpolant.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Interpolant` | `../Interpolant.js` |


---

## Functions

### `DiscreteInterpolant.interpolate_(i1: any): TypedArray`

**Parameters:**

- **`i1`** `any`

**Returns:** `TypedArray`

**Calls:**

- `this.copySampleValue_`

<details><summary>Code</summary>

```typescript
interpolate_( i1 /*, t0, t, t1 */ ) {

		return this.copySampleValue_( i1 - 1 );

	}
```
</details>


---

## Classes

### `DiscreteInterpolant`

<details><summary>Class Code</summary>

```ts
class DiscreteInterpolant extends Interpolant {

	/**
	 * Constructs a new discrete interpolant.
	 *
	 * @param {TypedArray} parameterPositions - The parameter positions hold the interpolation factors.
	 * @param {TypedArray} sampleValues - The sample values.
	 * @param {number} sampleSize - The sample size
	 * @param {TypedArray} [resultBuffer] - The result buffer.
	 */
	constructor( parameterPositions, sampleValues, sampleSize, resultBuffer ) {

		super( parameterPositions, sampleValues, sampleSize, resultBuffer );

	}

	interpolate_( i1 /*, t0, t, t1 */ ) {

		return this.copySampleValue_( i1 - 1 );

	}

}
```
</details>

#### Methods

##### `interpolate_(i1: any): TypedArray`

<details><summary>Code</summary>

```ts
interpolate_( i1 /*, t0, t, t1 */ ) {

		return this.copySampleValue_( i1 - 1 );

	}
```
</details>


---