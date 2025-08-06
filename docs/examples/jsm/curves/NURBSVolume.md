[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NURBSVolume.js`

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
📂 **`examples/jsm/curves/NURBSVolume.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector4` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `len1` | `number` | let/var | `knots1.length - degree1 - 1` | ✗ |
| `len2` | `number` | let/var | `knots2.length - degree2 - 1` | ✗ |
| `len3` | `number` | let/var | `knots3.length - degree3 - 1` | ✗ |
| `point` | `any` | let/var | `controlPoints[ i ][ j ][ k ]` | ✗ |
| `u` | `number` | let/var | `this.knots1[ 0 ] + t1 * ( this.knots1[ this.knots1.length - 1 ] - this.knots1...` | ✗ |
| `v` | `number` | let/var | `this.knots2[ 0 ] + t2 * ( this.knots2[ this.knots2.length - 1 ] - this.knots2...` | ✗ |
| `w` | `number` | let/var | `this.knots3[ 0 ] + t3 * ( this.knots3[ this.knots3.length - 1 ] - this.knots3...` | ✗ |


---

## Functions

### `NURBSVolume.getPoint(t1: number, t2: number, t3: number, target: Vector3): void`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor. This vector lies within the NURBS volume.
	 *
	 * @param {number} t1 - The first interpolation factor representing the `u` position within the volume. Must be in the range `[0,1]`.
	 * @param {number} t2 - The second interpolation factor representing the `v` position within the volume. Must be in the range `[0,1]`.
	 * @param {number} t3 - The third interpolation factor representing the `w` position within the volume. Must be in the range `[0,1]`.
	 * @param {Vector3} target - The target vector the result is written to.
	 */
```

**Parameters:**

- **`t1`** `number`
- **`t2`** `number`
- **`t3`** `number`
- **`target`** `Vector3`

**Returns:** `void`

**Calls:**

- `NURBSUtils.calcVolumePoint`

<details><summary>Code</summary>

```typescript
getPoint( t1, t2, t3, target ) {

		const u = this.knots1[ 0 ] + t1 * ( this.knots1[ this.knots1.length - 1 ] - this.knots1[ 0 ] ); // linear mapping t1->u
		const v = this.knots2[ 0 ] + t2 * ( this.knots2[ this.knots2.length - 1 ] - this.knots2[ 0 ] ); // linear mapping t2->v
		const w = this.knots3[ 0 ] + t3 * ( this.knots3[ this.knots3.length - 1 ] - this.knots3[ 0 ] ); // linear mapping t3->w

		NURBSUtils.calcVolumePoint( this.degree1, this.degree2, this.degree3, this.knots1, this.knots2, this.knots3, this.controlPoints, u, v, w, target );

	}
```
</details>


---

## Classes

### `NURBSVolume`

<details><summary>Class Code</summary>

```ts
class NURBSVolume {

	/**
	 * Constructs a new NURBS surface.
	 *
	 * @param {number} degree1 - The first NURBS degree.
	 * @param {number} degree2 - The second NURBS degree.
	 * @param {number} degree3 - The third NURBS degree.
	 * @param {Array<number>} knots1 - The first knots as a flat array of numbers.
	 * @param {Array<number>} knots2 - The second knots as a flat array of numbers.
	 * @param {Array<number>} knots3 - The third knots as a flat array of numbers.
	 * @param {Array<Array<Array<Vector2|Vector3|Vector4>>>} controlPoints - An array^3 holding control points.
	 */
	constructor( degree1, degree2, degree3, knots1, knots2, knots3 /* arrays of reals */, controlPoints /* array^3 of Vector(2|3|4) */ ) {

		this.degree1 = degree1;
		this.degree2 = degree2;
		this.degree3 = degree3;
		this.knots1 = knots1;
		this.knots2 = knots2;
		this.knots3 = knots3;
		this.controlPoints = [];

		const len1 = knots1.length - degree1 - 1;
		const len2 = knots2.length - degree2 - 1;
		const len3 = knots3.length - degree3 - 1;

		// ensure Vector4 for control points
		for ( let i = 0; i < len1; ++ i ) {

			this.controlPoints[ i ] = [];

			for ( let j = 0; j < len2; ++ j ) {

				this.controlPoints[ i ][ j ] = [];

				for ( let k = 0; k < len3; ++ k ) {

					const point = controlPoints[ i ][ j ][ k ];
					this.controlPoints[ i ][ j ][ k ] = new Vector4( point.x, point.y, point.z, point.w );

				}

			}

		}

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor. This vector lies within the NURBS volume.
	 *
	 * @param {number} t1 - The first interpolation factor representing the `u` position within the volume. Must be in the range `[0,1]`.
	 * @param {number} t2 - The second interpolation factor representing the `v` position within the volume. Must be in the range `[0,1]`.
	 * @param {number} t3 - The third interpolation factor representing the `w` position within the volume. Must be in the range `[0,1]`.
	 * @param {Vector3} target - The target vector the result is written to.
	 */
	getPoint( t1, t2, t3, target ) {

		const u = this.knots1[ 0 ] + t1 * ( this.knots1[ this.knots1.length - 1 ] - this.knots1[ 0 ] ); // linear mapping t1->u
		const v = this.knots2[ 0 ] + t2 * ( this.knots2[ this.knots2.length - 1 ] - this.knots2[ 0 ] ); // linear mapping t2->v
		const w = this.knots3[ 0 ] + t3 * ( this.knots3[ this.knots3.length - 1 ] - this.knots3[ 0 ] ); // linear mapping t3->w

		NURBSUtils.calcVolumePoint( this.degree1, this.degree2, this.degree3, this.knots1, this.knots2, this.knots3, this.controlPoints, u, v, w, target );

	}

}
```
</details>

#### Methods

##### `getPoint(t1: number, t2: number, t3: number, target: Vector3): void`

<details><summary>Code</summary>

```ts
getPoint( t1, t2, t3, target ) {

		const u = this.knots1[ 0 ] + t1 * ( this.knots1[ this.knots1.length - 1 ] - this.knots1[ 0 ] ); // linear mapping t1->u
		const v = this.knots2[ 0 ] + t2 * ( this.knots2[ this.knots2.length - 1 ] - this.knots2[ 0 ] ); // linear mapping t2->v
		const w = this.knots3[ 0 ] + t3 * ( this.knots3[ this.knots3.length - 1 ] - this.knots3[ 0 ] ); // linear mapping t3->w

		NURBSUtils.calcVolumePoint( this.degree1, this.degree2, this.degree3, this.knots1, this.knots2, this.knots3, this.controlPoints, u, v, w, target );

	}
```
</details>


---