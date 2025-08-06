[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CurveExtras.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 14 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 67 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/curves/CurveExtras.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Curve` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `x` | `number` | let/var | `- 0.22 * Math.cos( t ) - 1.28 * Math.sin( t ) - 0.44 * Math.cos( 3 * t ) - 0....` | ✗ |
| `y` | `number` | let/var | `- 0.1 * Math.cos( 2 * t ) - 0.27 * Math.sin( 2 * t ) + 0.38 * Math.cos( 4 * t...` | ✗ |
| `z` | `number` | let/var | `0.7 * Math.cos( 3 * t ) - 0.4 * Math.sin( 3 * t )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `x` | `number` | let/var | `16 * Math.pow( Math.sin( t ), 3 )` | ✗ |
| `y` | `number` | let/var | `13 * Math.cos( t ) - 5 * Math.cos( 2 * t ) - 2 * Math.cos( 3 * t ) - Math.cos...` | ✗ |
| `z` | `0` | let/var | `0` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `a` | `number` | let/var | `this.scale / 2` | ✗ |
| `x` | `number` | let/var | `a * ( 1 + Math.cos( t ) )` | ✗ |
| `y` | `number` | let/var | `a * Math.sin( t )` | ✗ |
| `z` | `number` | let/var | `2 * a * Math.sin( t / 2 )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `R` | `10` | let/var | `10` | ✗ |
| `s` | `50` | let/var | `50` | ✗ |
| `x` | `number` | let/var | `s * Math.sin( t )` | ✗ |
| `y` | `number` | let/var | `Math.cos( t ) * ( R + s * Math.cos( t ) )` | ✗ |
| `z` | `number` | let/var | `Math.sin( t ) * ( R + s * Math.cos( t ) )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `a` | `30` | let/var | `30` | ✗ |
| `b` | `150` | let/var | `150` | ✗ |
| `t2` | `number` | let/var | `2 * Math.PI * t * b / 30` | ✗ |
| `x` | `number` | let/var | `Math.cos( t2 ) * a` | ✗ |
| `y` | `number` | let/var | `Math.sin( t2 ) * a` | ✗ |
| `z` | `number` | let/var | `b * t` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `x` | `number` | let/var | `( 2 + Math.cos( 3 * t ) ) * Math.cos( 2 * t )` | ✗ |
| `y` | `number` | let/var | `( 2 + Math.cos( 3 * t ) ) * Math.sin( 2 * t )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `p` | `3` | let/var | `3` | ✗ |
| `q` | `4` | let/var | `4` | ✗ |
| `x` | `number` | let/var | `( 2 + Math.cos( q * t ) ) * Math.cos( p * t )` | ✗ |
| `y` | `number` | let/var | `( 2 + Math.cos( q * t ) ) * Math.sin( p * t )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `p` | `2` | let/var | `2` | ✗ |
| `q` | `5` | let/var | `5` | ✗ |
| `x` | `number` | let/var | `( 2 + Math.cos( q * t ) ) * Math.cos( p * t )` | ✗ |
| `y` | `number` | let/var | `( 2 + Math.cos( q * t ) ) * Math.sin( p * t )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `x` | `number` | let/var | `Math.pow( t, 3 ) - 3 * t` | ✗ |
| `y` | `number` | let/var | `Math.pow( t, 4 ) - 4 * t * t` | ✗ |
| `z` | `number` | let/var | `1 / 5 * Math.pow( t, 5 ) - 2 * t` | ✗ |
| `r` | `number` | let/var | `y - x` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `x` | `number` | let/var | `2 / 5 * t * ( t * t - 7 ) * ( t * t - 10 )` | ✗ |
| `y` | `number` | let/var | `Math.pow( t, 4 ) - 13 * t * t` | ✗ |
| `z` | `number` | let/var | `1 / 10 * t * ( t * t - 4 ) * ( t * t - 9 ) * ( t * t - 12 )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `x` | `number` | let/var | `Math.cos( 2 * t ) * ( 1 + 0.6 * ( Math.cos( 5 * t ) + 0.75 * Math.cos( 10 * t...` | ✗ |
| `y` | `number` | let/var | `Math.sin( 2 * t ) * ( 1 + 0.6 * ( Math.cos( 5 * t ) + 0.75 * Math.cos( 10 * t...` | ✗ |
| `z` | `number` | let/var | `0.35 * Math.sin( 5 * t )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `fi` | `number` | let/var | `t * Math.PI * 2` | ✗ |
| `x` | `number` | let/var | `Math.cos( 2 * fi ) * ( 1 + 0.45 * Math.cos( 3 * fi ) + 0.4 * Math.cos( 9 * fi...` | ✗ |
| `y` | `number` | let/var | `Math.sin( 2 * fi ) * ( 1 + 0.45 * Math.cos( 3 * fi ) + 0.4 * Math.cos( 9 * fi...` | ✗ |
| `z` | `number` | let/var | `0.2 * Math.sin( 9 * fi )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `fi` | `number` | let/var | `t * Math.PI * 2` | ✗ |
| `x` | `number` | let/var | `Math.cos( 3 * fi ) * ( 1 + 0.3 * Math.cos( 5 * fi ) + 0.5 * Math.cos( 10 * fi...` | ✗ |
| `y` | `number` | let/var | `Math.sin( 3 * fi ) * ( 1 + 0.3 * Math.cos( 5 * fi ) + 0.5 * Math.cos( 10 * fi...` | ✗ |
| `z` | `number` | let/var | `0.2 * Math.sin( 20 * fi )` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `fi` | `number` | let/var | `t * Math.PI * 2` | ✗ |
| `x` | `number` | let/var | `Math.cos( 4 * fi ) * ( 1 + 0.5 * ( Math.cos( 5 * fi ) + 0.4 * Math.cos( 20 * ...` | ✗ |
| `y` | `number` | let/var | `Math.sin( 4 * fi ) * ( 1 + 0.5 * ( Math.cos( 5 * fi ) + 0.4 * Math.cos( 20 * ...` | ✗ |
| `z` | `number` | let/var | `0.35 * Math.sin( 15 * fi )` | ✗ |


---

## Functions

### `GrannyKnot.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = 2 * Math.PI * t;

		const x = - 0.22 * Math.cos( t ) - 1.28 * Math.sin( t ) - 0.44 * Math.cos( 3 * t ) - 0.78 * Math.sin( 3 * t );
		const y = - 0.1 * Math.cos( 2 * t ) - 0.27 * Math.sin( 2 * t ) + 0.38 * Math.cos( 4 * t ) + 0.46 * Math.sin( 4 * t );
		const z = 0.7 * Math.cos( 3 * t ) - 0.4 * Math.sin( 3 * t );

		return point.set( x, y, z ).multiplyScalar( 20 );

	}
```
</details>

### `HeartCurve.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.pow`
- `Math.sin`
- `Math.cos`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= 2 * Math.PI;

		const x = 16 * Math.pow( Math.sin( t ), 3 );
		const y = 13 * Math.cos( t ) - 5 * Math.cos( 2 * t ) - 2 * Math.cos( 3 * t ) - Math.cos( 4 * t );
		const z = 0;

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `VivianiCurve.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = t * 4 * Math.PI; // normalized to 0..1
		const a = this.scale / 2;

		const x = a * ( 1 + Math.cos( t ) );
		const y = a * Math.sin( t );
		const z = 2 * a * Math.sin( t / 2 );

		return point.set( x, y, z );

	}
```
</details>

### `KnotCurve.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.sin`
- `Math.cos`
- `point.set`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= 2 * Math.PI;

		const R = 10;
		const s = 50;

		const x = s * Math.sin( t );
		const y = Math.cos( t ) * ( R + s * Math.cos( t ) );
		const z = Math.sin( t ) * ( R + s * Math.cos( t ) );

		return point.set( x, y, z );

	}
```
</details>

### `HelixCurve.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const a = 30; // radius
		const b = 150; // height

		const t2 = 2 * Math.PI * t * b / 30;

		const x = Math.cos( t2 ) * a;
		const y = Math.sin( t2 ) * a;
		const z = b * t;

		return point.set( x, y, z );

	}
```
</details>

### `TrefoilKnot.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= Math.PI * 2;

		const x = ( 2 + Math.cos( 3 * t ) ) * Math.cos( 2 * t );
		const y = ( 2 + Math.cos( 3 * t ) ) * Math.sin( 2 * t );
		const z = Math.sin( 3 * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `TorusKnot.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const p = 3;
		const q = 4;

		t *= Math.PI * 2;

		const x = ( 2 + Math.cos( q * t ) ) * Math.cos( p * t );
		const y = ( 2 + Math.cos( q * t ) ) * Math.sin( p * t );
		const z = Math.sin( q * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `CinquefoilKnot.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const p = 2;
		const q = 5;

		t *= Math.PI * 2;

		const x = ( 2 + Math.cos( q * t ) ) * Math.cos( p * t );
		const y = ( 2 + Math.cos( q * t ) ) * Math.sin( p * t );
		const z = Math.sin( q * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `TrefoilPolynomialKnot.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.pow`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = t * 4 - 2;

		const x = Math.pow( t, 3 ) - 3 * t;
		const y = Math.pow( t, 4 ) - 4 * t * t;
		const z = 1 / 5 * Math.pow( t, 5 ) - 2 * t;

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `scaleTo(x: any, y: any, t: any): any`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function scaleTo( x, y, t ) {

	const r = y - x;
	return t * r + x;

}
```
</details>

### `FigureEightPolynomialKnot.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `scaleTo`
- `Math.pow`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = scaleTo( - 4, 4, t );

		const x = 2 / 5 * t * ( t * t - 7 ) * ( t * t - 10 );
		const y = Math.pow( t, 4 ) - 13 * t * t;
		const z = 1 / 10 * t * ( t * t - 4 ) * ( t * t - 9 ) * ( t * t - 12 );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `DecoratedTorusKnot4a.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= Math.PI * 2;

		const x = Math.cos( 2 * t ) * ( 1 + 0.6 * ( Math.cos( 5 * t ) + 0.75 * Math.cos( 10 * t ) ) );
		const y = Math.sin( 2 * t ) * ( 1 + 0.6 * ( Math.cos( 5 * t ) + 0.75 * Math.cos( 10 * t ) ) );
		const z = 0.35 * Math.sin( 5 * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `DecoratedTorusKnot4b.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const fi = t * Math.PI * 2;

		const x = Math.cos( 2 * fi ) * ( 1 + 0.45 * Math.cos( 3 * fi ) + 0.4 * Math.cos( 9 * fi ) );
		const y = Math.sin( 2 * fi ) * ( 1 + 0.45 * Math.cos( 3 * fi ) + 0.4 * Math.cos( 9 * fi ) );
		const z = 0.2 * Math.sin( 9 * fi );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `DecoratedTorusKnot5a.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const fi = t * Math.PI * 2;

		const x = Math.cos( 3 * fi ) * ( 1 + 0.3 * Math.cos( 5 * fi ) + 0.5 * Math.cos( 10 * fi ) );
		const y = Math.sin( 3 * fi ) * ( 1 + 0.3 * Math.cos( 5 * fi ) + 0.5 * Math.cos( 10 * fi ) );
		const z = 0.2 * Math.sin( 20 * fi );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `DecoratedTorusKnot5c.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `point.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const fi = t * Math.PI * 2;

		const x = Math.cos( 4 * fi ) * ( 1 + 0.5 * ( Math.cos( 5 * fi ) + 0.4 * Math.cos( 20 * fi ) ) );
		const y = Math.sin( 4 * fi ) * ( 1 + 0.5 * ( Math.cos( 5 * fi ) + 0.4 * Math.cos( 20 * fi ) ) );
		const z = 0.35 * Math.sin( 15 * fi );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>


---

## Classes

### `GrannyKnot`

<details><summary>Class Code</summary>

```ts
class GrannyKnot extends Curve {

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = 2 * Math.PI * t;

		const x = - 0.22 * Math.cos( t ) - 1.28 * Math.sin( t ) - 0.44 * Math.cos( 3 * t ) - 0.78 * Math.sin( 3 * t );
		const y = - 0.1 * Math.cos( 2 * t ) - 0.27 * Math.sin( 2 * t ) + 0.38 * Math.cos( 4 * t ) + 0.46 * Math.sin( 4 * t );
		const z = 0.7 * Math.cos( 3 * t ) - 0.4 * Math.sin( 3 * t );

		return point.set( x, y, z ).multiplyScalar( 20 );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = 2 * Math.PI * t;

		const x = - 0.22 * Math.cos( t ) - 1.28 * Math.sin( t ) - 0.44 * Math.cos( 3 * t ) - 0.78 * Math.sin( 3 * t );
		const y = - 0.1 * Math.cos( 2 * t ) - 0.27 * Math.sin( 2 * t ) + 0.38 * Math.cos( 4 * t ) + 0.46 * Math.sin( 4 * t );
		const z = 0.7 * Math.cos( 3 * t ) - 0.4 * Math.sin( 3 * t );

		return point.set( x, y, z ).multiplyScalar( 20 );

	}
```
</details>

### `HeartCurve`

<details><summary>Class Code</summary>

```ts
class HeartCurve extends Curve {

	/**
	 * Constructs a new heart curve.
	 *
	 * @param {number} [scale=5] - The curve's scale.
	 */
	constructor( scale = 5 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 5
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= 2 * Math.PI;

		const x = 16 * Math.pow( Math.sin( t ), 3 );
		const y = 13 * Math.cos( t ) - 5 * Math.cos( 2 * t ) - 2 * Math.cos( 3 * t ) - Math.cos( 4 * t );
		const z = 0;

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= 2 * Math.PI;

		const x = 16 * Math.pow( Math.sin( t ), 3 );
		const y = 13 * Math.cos( t ) - 5 * Math.cos( 2 * t ) - 2 * Math.cos( 3 * t ) - Math.cos( 4 * t );
		const z = 0;

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `VivianiCurve`

<details><summary>Class Code</summary>

```ts
class VivianiCurve extends Curve {

	/**
	 * Constructs a new Viviani curve.
	 *
	 * @param {number} [scale=70] - The curve's scale.
	 */
	constructor( scale = 70 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 70
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = t * 4 * Math.PI; // normalized to 0..1
		const a = this.scale / 2;

		const x = a * ( 1 + Math.cos( t ) );
		const y = a * Math.sin( t );
		const z = 2 * a * Math.sin( t / 2 );

		return point.set( x, y, z );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = t * 4 * Math.PI; // normalized to 0..1
		const a = this.scale / 2;

		const x = a * ( 1 + Math.cos( t ) );
		const y = a * Math.sin( t );
		const z = 2 * a * Math.sin( t / 2 );

		return point.set( x, y, z );

	}
```
</details>

### `KnotCurve`

<details><summary>Class Code</summary>

```ts
class KnotCurve extends Curve {

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= 2 * Math.PI;

		const R = 10;
		const s = 50;

		const x = s * Math.sin( t );
		const y = Math.cos( t ) * ( R + s * Math.cos( t ) );
		const z = Math.sin( t ) * ( R + s * Math.cos( t ) );

		return point.set( x, y, z );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= 2 * Math.PI;

		const R = 10;
		const s = 50;

		const x = s * Math.sin( t );
		const y = Math.cos( t ) * ( R + s * Math.cos( t ) );
		const z = Math.sin( t ) * ( R + s * Math.cos( t ) );

		return point.set( x, y, z );

	}
```
</details>

### `HelixCurve`

<details><summary>Class Code</summary>

```ts
class HelixCurve extends Curve {

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const a = 30; // radius
		const b = 150; // height

		const t2 = 2 * Math.PI * t * b / 30;

		const x = Math.cos( t2 ) * a;
		const y = Math.sin( t2 ) * a;
		const z = b * t;

		return point.set( x, y, z );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const a = 30; // radius
		const b = 150; // height

		const t2 = 2 * Math.PI * t * b / 30;

		const x = Math.cos( t2 ) * a;
		const y = Math.sin( t2 ) * a;
		const z = b * t;

		return point.set( x, y, z );

	}
```
</details>

### `TrefoilKnot`

<details><summary>Class Code</summary>

```ts
class TrefoilKnot extends Curve {

	/**
	 * Constructs a new Trefoil Knot.
	 *
	 * @param {number} [scale=10] - The curve's scale.
	 */
	constructor( scale = 10 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 10
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= Math.PI * 2;

		const x = ( 2 + Math.cos( 3 * t ) ) * Math.cos( 2 * t );
		const y = ( 2 + Math.cos( 3 * t ) ) * Math.sin( 2 * t );
		const z = Math.sin( 3 * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= Math.PI * 2;

		const x = ( 2 + Math.cos( 3 * t ) ) * Math.cos( 2 * t );
		const y = ( 2 + Math.cos( 3 * t ) ) * Math.sin( 2 * t );
		const z = Math.sin( 3 * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `TorusKnot`

<details><summary>Class Code</summary>

```ts
class TorusKnot extends Curve {

	/**
	 * Constructs a new torus knot.
	 *
	 * @param {number} [scale=10] - The curve's scale.
	 */
	constructor( scale = 10 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 10
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const p = 3;
		const q = 4;

		t *= Math.PI * 2;

		const x = ( 2 + Math.cos( q * t ) ) * Math.cos( p * t );
		const y = ( 2 + Math.cos( q * t ) ) * Math.sin( p * t );
		const z = Math.sin( q * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const p = 3;
		const q = 4;

		t *= Math.PI * 2;

		const x = ( 2 + Math.cos( q * t ) ) * Math.cos( p * t );
		const y = ( 2 + Math.cos( q * t ) ) * Math.sin( p * t );
		const z = Math.sin( q * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `CinquefoilKnot`

<details><summary>Class Code</summary>

```ts
class CinquefoilKnot extends Curve {

	/**
	 * Constructs a new Cinquefoil Knot.
	 *
	 * @param {number} [scale=10] - The curve's scale.
	 */
	constructor( scale = 10 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 10
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const p = 2;
		const q = 5;

		t *= Math.PI * 2;

		const x = ( 2 + Math.cos( q * t ) ) * Math.cos( p * t );
		const y = ( 2 + Math.cos( q * t ) ) * Math.sin( p * t );
		const z = Math.sin( q * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const p = 2;
		const q = 5;

		t *= Math.PI * 2;

		const x = ( 2 + Math.cos( q * t ) ) * Math.cos( p * t );
		const y = ( 2 + Math.cos( q * t ) ) * Math.sin( p * t );
		const z = Math.sin( q * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `TrefoilPolynomialKnot`

<details><summary>Class Code</summary>

```ts
class TrefoilPolynomialKnot extends Curve {

	/**
	 * Constructs a new Trefoil Polynomial Knot.
	 *
	 * @param {number} [scale=10] - The curve's scale.
	 */
	constructor( scale = 10 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 10
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = t * 4 - 2;

		const x = Math.pow( t, 3 ) - 3 * t;
		const y = Math.pow( t, 4 ) - 4 * t * t;
		const z = 1 / 5 * Math.pow( t, 5 ) - 2 * t;

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = t * 4 - 2;

		const x = Math.pow( t, 3 ) - 3 * t;
		const y = Math.pow( t, 4 ) - 4 * t * t;
		const z = 1 / 5 * Math.pow( t, 5 ) - 2 * t;

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `FigureEightPolynomialKnot`

<details><summary>Class Code</summary>

```ts
class FigureEightPolynomialKnot extends Curve {

	/**
	 * Constructs a new Figure Eight Polynomial Knot.
	 *
	 * @param {number} [scale=1] - The curve's scale.
	 */
	constructor( scale = 1 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = scaleTo( - 4, 4, t );

		const x = 2 / 5 * t * ( t * t - 7 ) * ( t * t - 10 );
		const y = Math.pow( t, 4 ) - 13 * t * t;
		const z = 1 / 10 * t * ( t * t - 4 ) * ( t * t - 9 ) * ( t * t - 12 );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t = scaleTo( - 4, 4, t );

		const x = 2 / 5 * t * ( t * t - 7 ) * ( t * t - 10 );
		const y = Math.pow( t, 4 ) - 13 * t * t;
		const z = 1 / 10 * t * ( t * t - 4 ) * ( t * t - 9 ) * ( t * t - 12 );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `DecoratedTorusKnot4a`

<details><summary>Class Code</summary>

```ts
class DecoratedTorusKnot4a extends Curve {

	/**
	 * Constructs a new Decorated Torus Knot 4a.
	 *
	 * @param {number} [scale=1] - The curve's scale.
	 */
	constructor( scale = 40 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 40
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= Math.PI * 2;

		const x = Math.cos( 2 * t ) * ( 1 + 0.6 * ( Math.cos( 5 * t ) + 0.75 * Math.cos( 10 * t ) ) );
		const y = Math.sin( 2 * t ) * ( 1 + 0.6 * ( Math.cos( 5 * t ) + 0.75 * Math.cos( 10 * t ) ) );
		const z = 0.35 * Math.sin( 5 * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		t *= Math.PI * 2;

		const x = Math.cos( 2 * t ) * ( 1 + 0.6 * ( Math.cos( 5 * t ) + 0.75 * Math.cos( 10 * t ) ) );
		const y = Math.sin( 2 * t ) * ( 1 + 0.6 * ( Math.cos( 5 * t ) + 0.75 * Math.cos( 10 * t ) ) );
		const z = 0.35 * Math.sin( 5 * t );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `DecoratedTorusKnot4b`

<details><summary>Class Code</summary>

```ts
class DecoratedTorusKnot4b extends Curve {

	/**
	 * Constructs a new Decorated Torus Knot 4b.
	 *
	 * @param {number} [scale=1] - The curve's scale.
	 */
	constructor( scale = 40 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 40
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const fi = t * Math.PI * 2;

		const x = Math.cos( 2 * fi ) * ( 1 + 0.45 * Math.cos( 3 * fi ) + 0.4 * Math.cos( 9 * fi ) );
		const y = Math.sin( 2 * fi ) * ( 1 + 0.45 * Math.cos( 3 * fi ) + 0.4 * Math.cos( 9 * fi ) );
		const z = 0.2 * Math.sin( 9 * fi );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const fi = t * Math.PI * 2;

		const x = Math.cos( 2 * fi ) * ( 1 + 0.45 * Math.cos( 3 * fi ) + 0.4 * Math.cos( 9 * fi ) );
		const y = Math.sin( 2 * fi ) * ( 1 + 0.45 * Math.cos( 3 * fi ) + 0.4 * Math.cos( 9 * fi ) );
		const z = 0.2 * Math.sin( 9 * fi );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `DecoratedTorusKnot5a`

<details><summary>Class Code</summary>

```ts
class DecoratedTorusKnot5a extends Curve {

	/**
	 * Constructs a new Decorated Torus Knot 5a.
	 *
	 * @param {number} [scale=1] - The curve's scale.
	 */
	constructor( scale = 40 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 40
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const fi = t * Math.PI * 2;

		const x = Math.cos( 3 * fi ) * ( 1 + 0.3 * Math.cos( 5 * fi ) + 0.5 * Math.cos( 10 * fi ) );
		const y = Math.sin( 3 * fi ) * ( 1 + 0.3 * Math.cos( 5 * fi ) + 0.5 * Math.cos( 10 * fi ) );
		const z = 0.2 * Math.sin( 20 * fi );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const fi = t * Math.PI * 2;

		const x = Math.cos( 3 * fi ) * ( 1 + 0.3 * Math.cos( 5 * fi ) + 0.5 * Math.cos( 10 * fi ) );
		const y = Math.sin( 3 * fi ) * ( 1 + 0.3 * Math.cos( 5 * fi ) + 0.5 * Math.cos( 10 * fi ) );
		const z = 0.2 * Math.sin( 20 * fi );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>

### `DecoratedTorusKnot5c`

<details><summary>Class Code</summary>

```ts
class DecoratedTorusKnot5c extends Curve {

	/**
	 * Constructs a new Decorated Torus Knot 5c.
	 *
	 * @param {number} [scale=1] - The curve's scale.
	 */
	constructor( scale = 40 ) {

		super();

		/**
		 * The curve's scale.
		 *
		 * @type {number}
		 * @default 40
		 */
		this.scale = scale;

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const fi = t * Math.PI * 2;

		const x = Math.cos( 4 * fi ) * ( 1 + 0.5 * ( Math.cos( 5 * fi ) + 0.4 * Math.cos( 20 * fi ) ) );
		const y = Math.sin( 4 * fi ) * ( 1 + 0.5 * ( Math.cos( 5 * fi ) + 0.4 * Math.cos( 20 * fi ) ) );
		const z = 0.35 * Math.sin( 15 * fi );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const fi = t * Math.PI * 2;

		const x = Math.cos( 4 * fi ) * ( 1 + 0.5 * ( Math.cos( 5 * fi ) + 0.4 * Math.cos( 20 * fi ) ) );
		const y = Math.sin( 4 * fi ) * ( 1 + 0.5 * ( Math.cos( 5 * fi ) + 0.4 * Math.cos( 20 * fi ) ) );
		const z = 0.35 * Math.sin( 15 * fi );

		return point.set( x, y, z ).multiplyScalar( this.scale );

	}
```
</details>


---