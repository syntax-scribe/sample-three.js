[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NURBSUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 48 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/curves/NURBSUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `three` |
| `Vector4` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `n` | `number` | let/var | `U.length - p - 1` | ✗ |
| `low` | `number` | let/var | `p` | ✗ |
| `high` | `number` | let/var | `n` | ✗ |
| `N` | `any[]` | let/var | `[]` | ✗ |
| `left` | `any[]` | let/var | `[]` | ✗ |
| `right` | `any[]` | let/var | `[]` | ✗ |
| `saved` | `number` | let/var | `0.0` | ✗ |
| `rv` | `number` | let/var | `right[ r + 1 ]` | ✗ |
| `lv` | `number` | let/var | `left[ j - r ]` | ✗ |
| `temp` | `any` | let/var | `N[ r ] / ( rv + lv )` | ✗ |
| `C` | `any` | let/var | `new Vector4( 0, 0, 0, 0 )` | ✗ |
| `point` | `Vector4` | let/var | `P[ span - p + j ]` | ✗ |
| `Nj` | `number` | let/var | `N[ j ]` | ✗ |
| `wNj` | `number` | let/var | `point.w * Nj` | ✗ |
| `zeroArr` | `any[]` | let/var | `[]` | ✗ |
| `ders` | `any[]` | let/var | `[]` | ✗ |
| `ndu` | `any[]` | let/var | `[]` | ✗ |
| `saved` | `number` | let/var | `0.0` | ✗ |
| `rv` | `number` | let/var | `right[ r + 1 ]` | ✗ |
| `lv` | `number` | let/var | `left[ j - r ]` | ✗ |
| `temp` | `number` | let/var | `ndu[ r ][ j - 1 ] / ndu[ j ][ r ]` | ✗ |
| `s1` | `number` | let/var | `0` | ✗ |
| `s2` | `number` | let/var | `1` | ✗ |
| `a` | `any[]` | let/var | `[]` | ✗ |
| `d` | `number` | let/var | `0.0` | ✗ |
| `rk` | `number` | let/var | `r - k` | ✗ |
| `pk` | `number` | let/var | `p - k` | ✗ |
| `j1` | `number` | let/var | `( rk >= - 1 ) ? 1 : - rk` | ✗ |
| `j2` | `number` | let/var | `( r - 1 <= pk ) ? k - 1 : p - r` | ✗ |
| `j` | `number` | let/var | `s1` | ✗ |
| `r` | `number` | let/var | `p` | ✗ |
| `du` | `number` | let/var | `nd < p ? nd : p` | ✗ |
| `CK` | `any[]` | let/var | `[]` | ✗ |
| `Pw` | `any[]` | let/var | `[]` | ✗ |
| `w` | `any` | let/var | `point.w` | ✗ |
| `nom` | `number` | let/var | `1` | ✗ |
| `denom` | `number` | let/var | `1` | ✗ |
| `nd` | `number` | let/var | `Pders.length` | ✗ |
| `Aders` | `any[]` | let/var | `[]` | ✗ |
| `wders` | `any[]` | let/var | `[]` | ✗ |
| `point` | `Vector4` | let/var | `Pders[ i ]` | ✗ |
| `CK` | `any[]` | let/var | `[]` | ✗ |
| `temp` | `any[]` | let/var | `[]` | ✗ |
| `w` | `any` | let/var | `point.w` | ✗ |
| `Sw` | `any` | let/var | `new Vector4( 0, 0, 0, 0 )` | ✗ |
| `temp` | `any[]` | let/var | `[]` | ✗ |
| `w` | `any` | let/var | `point.w` | ✗ |
| `Sw` | `any` | let/var | `new Vector4( 0, 0, 0, 0 )` | ✗ |


---

## Functions

### `findSpan(p: number, u: number, U: number[]): number`

**JSDoc:**
```typescript
/**
 * Finds knot vector span.
 *
 * @param {number} p - The degree.
 * @param {number} u - The parametric value.
 * @param {Array<number>} U - The knot vector.
 * @return {number} The span.
 */
```

**Parameters:**

- **`p`** `number`
- **`u`** `number`
- **`U`** `number[]`

**Returns:** `number`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
function findSpan( p, u, U ) {

	const n = U.length - p - 1;

	if ( u >= U[ n ] ) {

		return n - 1;

	}

	if ( u <= U[ p ] ) {

		return p;

	}

	let low = p;
	let high = n;
	let mid = Math.floor( ( low + high ) / 2 );

	while ( u < U[ mid ] || u >= U[ mid + 1 ] ) {

		if ( u < U[ mid ] ) {

			high = mid;

		} else {

			low = mid;

		}

		mid = Math.floor( ( low + high ) / 2 );

	}

	return mid;

}
```
</details>

### `calcBasisFunctions(span: number, u: number, p: number, U: number[]): number[]`

**JSDoc:**
```typescript
/**
 * Calculates basis functions. See The NURBS Book, page 70, algorithm A2.2.
 *
 * @param {number} span - The span in which `u` lies.
 * @param {number} u - The parametric value.
 * @param {number} p - The degree.
 * @param {Array<number>} U - The knot vector.
 * @return {Array<number>} Array[p+1] with basis functions values.
 */
```

**Parameters:**

- **`span`** `number`
- **`u`** `number`
- **`p`** `number`
- **`U`** `number[]`

**Returns:** `number[]`

<details><summary>Code</summary>

```typescript
function calcBasisFunctions( span, u, p, U ) {

	const N = [];
	const left = [];
	const right = [];
	N[ 0 ] = 1.0;

	for ( let j = 1; j <= p; ++ j ) {

		left[ j ] = u - U[ span + 1 - j ];
		right[ j ] = U[ span + j ] - u;

		let saved = 0.0;

		for ( let r = 0; r < j; ++ r ) {

			const rv = right[ r + 1 ];
			const lv = left[ j - r ];
			const temp = N[ r ] / ( rv + lv );
			N[ r ] = saved + rv * temp;
			saved = lv * temp;

		}

		N[ j ] = saved;

	}

	return N;

}
```
</details>

### `calcBSplinePoint(p: number, U: number[], P: Vector4[], u: number): Vector4`

**JSDoc:**
```typescript
/**
 * Calculates B-Spline curve points. See The NURBS Book, page 82, algorithm A3.1.
 *
 * @param {number} p - The degree of the B-Spline.
 * @param {Array<number>} U - The knot vector.
 * @param {Array<Vector4>} P - The control points
 * @param {number} u - The parametric point.
 * @return {Vector4} The point for given `u`.
 */
```

**Parameters:**

- **`p`** `number`
- **`U`** `number[]`
- **`P`** `Vector4[]`
- **`u`** `number`

**Returns:** `Vector4`

**Calls:**

- `findSpan`
- `calcBasisFunctions`

<details><summary>Code</summary>

```typescript
function calcBSplinePoint( p, U, P, u ) {

	const span = findSpan( p, u, U );
	const N = calcBasisFunctions( span, u, p, U );
	const C = new Vector4( 0, 0, 0, 0 );

	for ( let j = 0; j <= p; ++ j ) {

		const point = P[ span - p + j ];
		const Nj = N[ j ];
		const wNj = point.w * Nj;
		C.x += point.x * wNj;
		C.y += point.y * wNj;
		C.z += point.z * wNj;
		C.w += point.w * Nj;

	}

	return C;

}
```
</details>

### `calcBasisFunctionDerivatives(span: number, u: number, p: number, n: number, U: number[]): number[][]`

**JSDoc:**
```typescript
/**
 * Calculates basis functions derivatives. See The NURBS Book, page 72, algorithm A2.3.
 *
 * @param {number} span - The span in which `u` lies.
 * @param {number} u - The parametric point.
 * @param {number} p - The degree.
 * @param {number} n - number of derivatives to calculate
 * @param {Array<number>} U - The knot vector.
 * @return {Array<Array<number>>} An array[n+1][p+1] with basis functions derivatives.
 */
```

**Parameters:**

- **`span`** `number`
- **`u`** `number`
- **`p`** `number`
- **`n`** `number`
- **`U`** `number[]`

**Returns:** `number[][]`

**Calls:**

- `zeroArr.slice`

<details><summary>Code</summary>

```typescript
function calcBasisFunctionDerivatives( span, u, p, n, U ) {

	const zeroArr = [];
	for ( let i = 0; i <= p; ++ i )
		zeroArr[ i ] = 0.0;

	const ders = [];

	for ( let i = 0; i <= n; ++ i )
		ders[ i ] = zeroArr.slice( 0 );

	const ndu = [];

	for ( let i = 0; i <= p; ++ i )
		ndu[ i ] = zeroArr.slice( 0 );

	ndu[ 0 ][ 0 ] = 1.0;

	const left = zeroArr.slice( 0 );
	const right = zeroArr.slice( 0 );

	for ( let j = 1; j <= p; ++ j ) {

		left[ j ] = u - U[ span + 1 - j ];
		right[ j ] = U[ span + j ] - u;

		let saved = 0.0;

		for ( let r = 0; r < j; ++ r ) {

			const rv = right[ r + 1 ];
			const lv = left[ j - r ];
			ndu[ j ][ r ] = rv + lv;

			const temp = ndu[ r ][ j - 1 ] / ndu[ j ][ r ];
			ndu[ r ][ j ] = saved + rv * temp;
			saved = lv * temp;

		}

		ndu[ j ][ j ] = saved;

	}

	for ( let j = 0; j <= p; ++ j ) {

		ders[ 0 ][ j ] = ndu[ j ][ p ];

	}

	for ( let r = 0; r <= p; ++ r ) {

		let s1 = 0;
		let s2 = 1;

		const a = [];
		for ( let i = 0; i <= p; ++ i ) {

			a[ i ] = zeroArr.slice( 0 );

		}

		a[ 0 ][ 0 ] = 1.0;

		for ( let k = 1; k <= n; ++ k ) {

			let d = 0.0;
			const rk = r - k;
			const pk = p - k;

			if ( r >= k ) {

				a[ s2 ][ 0 ] = a[ s1 ][ 0 ] / ndu[ pk + 1 ][ rk ];
				d = a[ s2 ][ 0 ] * ndu[ rk ][ pk ];

			}

			const j1 = ( rk >= - 1 ) ? 1 : - rk;
			const j2 = ( r - 1 <= pk ) ? k - 1 : p - r;

			for ( let j = j1; j <= j2; ++ j ) {

				a[ s2 ][ j ] = ( a[ s1 ][ j ] - a[ s1 ][ j - 1 ] ) / ndu[ pk + 1 ][ rk + j ];
				d += a[ s2 ][ j ] * ndu[ rk + j ][ pk ];

			}

			if ( r <= pk ) {

				a[ s2 ][ k ] = - a[ s1 ][ k - 1 ] / ndu[ pk + 1 ][ r ];
				d += a[ s2 ][ k ] * ndu[ r ][ pk ];

			}

			ders[ k ][ r ] = d;

			const j = s1;
			s1 = s2;
			s2 = j;

		}

	}

	let r = p;

	for ( let k = 1; k <= n; ++ k ) {

		for ( let j = 0; j <= p; ++ j ) {

			ders[ k ][ j ] *= r;

		}

		r *= p - k;

	}

	return ders;

}
```
</details>

### `calcBSplineDerivatives(p: number, U: number[], P: Vector4[], u: number, nd: number): Vector4[]`

**JSDoc:**
```typescript
/**
 * Calculates derivatives of a B-Spline. See The NURBS Book, page 93, algorithm A3.2.
 *
 * @param {number} p - The degree.
 * @param {Array<number>} U - The knot vector.
 * @param {Array<Vector4>} P - The control points
 * @param {number} u - The parametric point.
 * @param {number} nd - The number of derivatives.
 * @return {Array<Vector4>} An array[d+1] with derivatives.
 */
```

**Parameters:**

- **`p`** `number`
- **`U`** `number[]`
- **`P`** `Vector4[]`
- **`u`** `number`
- **`nd`** `number`

**Returns:** `Vector4[]`

**Calls:**

- `findSpan`
- `calcBasisFunctionDerivatives`
- `P[ i ].clone`
- `Pw[ span - p ].clone().multiplyScalar`
- `point.add`
- `Pw[ span - p + j ].clone().multiplyScalar`

<details><summary>Code</summary>

```typescript
function calcBSplineDerivatives( p, U, P, u, nd ) {

	const du = nd < p ? nd : p;
	const CK = [];
	const span = findSpan( p, u, U );
	const nders = calcBasisFunctionDerivatives( span, u, p, du, U );
	const Pw = [];

	for ( let i = 0; i < P.length; ++ i ) {

		const point = P[ i ].clone();
		const w = point.w;

		point.x *= w;
		point.y *= w;
		point.z *= w;

		Pw[ i ] = point;

	}

	for ( let k = 0; k <= du; ++ k ) {

		const point = Pw[ span - p ].clone().multiplyScalar( nders[ k ][ 0 ] );

		for ( let j = 1; j <= p; ++ j ) {

			point.add( Pw[ span - p + j ].clone().multiplyScalar( nders[ k ][ j ] ) );

		}

		CK[ k ] = point;

	}

	for ( let k = du + 1; k <= nd + 1; ++ k ) {

		CK[ k ] = new Vector4( 0, 0, 0 );

	}

	return CK;

}
```
</details>

### `calcKoverI(k: number, i: number): number`

**JSDoc:**
```typescript
/**
 * Calculates "K over I".
 *
 * @param {number} k - The K value.
 * @param {number} i - The I value.
 * @return {number} k!/(i!(k-i)!)
 */
```

**Parameters:**

- **`k`** `number`
- **`i`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function calcKoverI( k, i ) {

	let nom = 1;

	for ( let j = 2; j <= k; ++ j ) {

		nom *= j;

	}

	let denom = 1;

	for ( let j = 2; j <= i; ++ j ) {

		denom *= j;

	}

	for ( let j = 2; j <= k - i; ++ j ) {

		denom *= j;

	}

	return nom / denom;

}
```
</details>

### `calcRationalCurveDerivatives(Pders: Vector4[]): Vector3[]`

**JSDoc:**
```typescript
/**
 * Calculates derivatives (0-nd) of rational curve. See The NURBS Book, page 127, algorithm A4.2.
 *
 * @param {Array<Vector4>} Pders - Array with derivatives.
 * @return {Array<Vector3>} An array with derivatives for rational curve.
 */
```

**Parameters:**

- **`Pders`** `Vector4[]`

**Returns:** `Vector3[]`

**Calls:**

- `Aders[ k ].clone`
- `v.sub`
- `CK[ k - i ].clone().multiplyScalar`
- `calcKoverI`
- `v.divideScalar`

<details><summary>Code</summary>

```typescript
function calcRationalCurveDerivatives( Pders ) {

	const nd = Pders.length;
	const Aders = [];
	const wders = [];

	for ( let i = 0; i < nd; ++ i ) {

		const point = Pders[ i ];
		Aders[ i ] = new Vector3( point.x, point.y, point.z );
		wders[ i ] = point.w;

	}

	const CK = [];

	for ( let k = 0; k < nd; ++ k ) {

		const v = Aders[ k ].clone();

		for ( let i = 1; i <= k; ++ i ) {

			v.sub( CK[ k - i ].clone().multiplyScalar( calcKoverI( k, i ) * wders[ i ] ) );

		}

		CK[ k ] = v.divideScalar( wders[ 0 ] );

	}

	return CK;

}
```
</details>

### `calcNURBSDerivatives(p: number, U: number[], P: Vector4[], u: number, nd: number): Vector3[]`

**JSDoc:**
```typescript
/**
 * Calculates NURBS curve derivatives. See The NURBS Book, page 127, algorithm A4.2.
 *
 * @param {number} p - The degree.
 * @param {Array<number>} U - The knot vector.
 * @param {Array<Vector4>} P - The control points in homogeneous space.
 * @param {number} u - The parametric point.
 * @param {number} nd - The number of derivatives.
 * @return {Array<Vector3>} array with derivatives for rational curve.
 */
```

**Parameters:**

- **`p`** `number`
- **`U`** `number[]`
- **`P`** `Vector4[]`
- **`u`** `number`
- **`nd`** `number`

**Returns:** `Vector3[]`

**Calls:**

- `calcBSplineDerivatives`
- `calcRationalCurveDerivatives`

<details><summary>Code</summary>

```typescript
function calcNURBSDerivatives( p, U, P, u, nd ) {

	const Pders = calcBSplineDerivatives( p, U, P, u, nd );
	return calcRationalCurveDerivatives( Pders );

}
```
</details>

### `calcSurfacePoint(p: number, q: number, U: number[], V: number[], P: Vector4[][], u: number, v: number, target: Vector3): void`

**JSDoc:**
```typescript
/**
 * Calculates a rational B-Spline surface point. See The NURBS Book, page 134, algorithm A4.3.
 *
 * @param {number} p - The first degree of B-Spline surface.
 * @param {number} q - The second degree of B-Spline surface.
 * @param {Array<number>} U - The first knot vector.
 * @param {Array<number>} V - The second knot vector.
 * @param {Array<Array<Vector4>>} P - The control points in homogeneous space.
 * @param {number} u - The first parametric point.
 * @param {number} v - The second parametric point.
 * @param {Vector3} target - The target vector.
 */
```

**Parameters:**

- **`p`** `number`
- **`q`** `number`
- **`U`** `number[]`
- **`V`** `number[]`
- **`P`** `Vector4[][]`
- **`u`** `number`
- **`v`** `number`
- **`target`** `Vector3`

**Returns:** `void`

**Calls:**

- `findSpan`
- `calcBasisFunctions`
- `P[ uspan - p + k ][ vspan - q + l ].clone`
- `temp[ l ].add`
- `point.multiplyScalar`
- `Sw.add`
- `temp[ l ].multiplyScalar`
- `Sw.divideScalar`
- `target.set`

<details><summary>Code</summary>

```typescript
function calcSurfacePoint( p, q, U, V, P, u, v, target ) {

	const uspan = findSpan( p, u, U );
	const vspan = findSpan( q, v, V );
	const Nu = calcBasisFunctions( uspan, u, p, U );
	const Nv = calcBasisFunctions( vspan, v, q, V );
	const temp = [];

	for ( let l = 0; l <= q; ++ l ) {

		temp[ l ] = new Vector4( 0, 0, 0, 0 );
		for ( let k = 0; k <= p; ++ k ) {

			const point = P[ uspan - p + k ][ vspan - q + l ].clone();
			const w = point.w;
			point.x *= w;
			point.y *= w;
			point.z *= w;
			temp[ l ].add( point.multiplyScalar( Nu[ k ] ) );

		}

	}

	const Sw = new Vector4( 0, 0, 0, 0 );
	for ( let l = 0; l <= q; ++ l ) {

		Sw.add( temp[ l ].multiplyScalar( Nv[ l ] ) );

	}

	Sw.divideScalar( Sw.w );
	target.set( Sw.x, Sw.y, Sw.z );

}
```
</details>

### `calcVolumePoint(p: number, q: number, r: number, U: number[], V: number[], W: number[], P: Vector4[][][], u: number, v: number, w: number, target: Vector3): void`

**JSDoc:**
```typescript
/**
 * Calculates a rational B-Spline volume point. See The NURBS Book, page 134, algorithm A4.3.
 *
 * @param {number} p - The first degree of B-Spline surface.
 * @param {number} q - The second degree of B-Spline surface.
 * @param {number} r - The third degree of B-Spline surface.
 * @param {Array<number>} U - The first knot vector.
 * @param {Array<number>} V - The second knot vector.
 * @param {Array<number>} W - The third knot vector.
 * @param {Array<Array<Array<Vector4>>>} P - The control points in homogeneous space.
 * @param {number} u - The first parametric point.
 * @param {number} v - The second parametric point.
 * @param {number} w - The third parametric point.
 * @param {Vector3} target - The target vector.
 */
```

**Parameters:**

- **`p`** `number`
- **`q`** `number`
- **`r`** `number`
- **`U`** `number[]`
- **`V`** `number[]`
- **`W`** `number[]`
- **`P`** `Vector4[][][]`
- **`u`** `number`
- **`v`** `number`
- **`w`** `number`
- **`target`** `Vector3`

**Returns:** `void`

**Calls:**

- `findSpan`
- `calcBasisFunctions`
- `P[ uspan - p + k ][ vspan - q + l ][ wspan - r + m ].clone`
- `temp[ m ][ l ].add`
- `point.multiplyScalar`
- `Sw.add`
- `temp[ m ][ l ].multiplyScalar( Nw[ m ] ).multiplyScalar`
- `Sw.divideScalar`
- `target.set`

<details><summary>Code</summary>

```typescript
function calcVolumePoint( p, q, r, U, V, W, P, u, v, w, target ) {

	const uspan = findSpan( p, u, U );
	const vspan = findSpan( q, v, V );
	const wspan = findSpan( r, w, W );
	const Nu = calcBasisFunctions( uspan, u, p, U );
	const Nv = calcBasisFunctions( vspan, v, q, V );
	const Nw = calcBasisFunctions( wspan, w, r, W );
	const temp = [];

	for ( let m = 0; m <= r; ++ m ) {

		temp[ m ] = [];

		for ( let l = 0; l <= q; ++ l ) {

			temp[ m ][ l ] = new Vector4( 0, 0, 0, 0 );
			for ( let k = 0; k <= p; ++ k ) {

				const point = P[ uspan - p + k ][ vspan - q + l ][ wspan - r + m ].clone();
				const w = point.w;
				point.x *= w;
				point.y *= w;
				point.z *= w;
				temp[ m ][ l ].add( point.multiplyScalar( Nu[ k ] ) );

			}

		}

	}

	const Sw = new Vector4( 0, 0, 0, 0 );
	for ( let m = 0; m <= r; ++ m ) {

		for ( let l = 0; l <= q; ++ l ) {

			Sw.add( temp[ m ][ l ].multiplyScalar( Nw[ m ] ).multiplyScalar( Nv[ l ] ) );

		}

	}

	Sw.divideScalar( Sw.w );
	target.set( Sw.x, Sw.y, Sw.z );

}
```
</details>


---