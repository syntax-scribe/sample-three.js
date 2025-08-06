[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Interpolations.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/extras/core/Interpolations.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `v0` | `number` | let/var | `( p2 - p0 ) * 0.5` | ✗ |
| `v1` | `number` | let/var | `( p3 - p1 ) * 0.5` | ✗ |
| `t2` | `number` | let/var | `t * t` | ✗ |
| `t3` | `number` | let/var | `t * t2` | ✗ |
| `k` | `number` | let/var | `1 - t` | ✗ |
| `k` | `number` | let/var | `1 - t` | ✗ |
| `k` | `number` | let/var | `1 - t` | ✗ |


---

## Functions

### `CatmullRom(t: number, p0: number, p1: number, p2: number, p3: number): number`

**JSDoc:**
```typescript
/**
 * Computes a point on a Catmull-Rom spline.
 *
 * @param {number} t - The interpolation factor.
 * @param {number} p0 - The first control point.
 * @param {number} p1 - The second control point.
 * @param {number} p2 - The third control point.
 * @param {number} p3 - The fourth control point.
 * @return {number} The calculated point on a Catmull-Rom spline.
 */
```

**Parameters:**

- **`t`** `number`
- **`p0`** `number`
- **`p1`** `number`
- **`p2`** `number`
- **`p3`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function CatmullRom( t, p0, p1, p2, p3 ) {

	const v0 = ( p2 - p0 ) * 0.5;
	const v1 = ( p3 - p1 ) * 0.5;
	const t2 = t * t;
	const t3 = t * t2;
	return ( 2 * p1 - 2 * p2 + v0 + v1 ) * t3 + ( - 3 * p1 + 3 * p2 - 2 * v0 - v1 ) * t2 + v0 * t + p1;

}
```
</details>

### `QuadraticBezierP0(t: any, p: any): number`

**Parameters:**

- **`t`** `any`
- **`p`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function QuadraticBezierP0( t, p ) {

	const k = 1 - t;
	return k * k * p;

}
```
</details>

### `QuadraticBezierP1(t: any, p: any): number`

**Parameters:**

- **`t`** `any`
- **`p`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function QuadraticBezierP1( t, p ) {

	return 2 * ( 1 - t ) * t * p;

}
```
</details>

### `QuadraticBezierP2(t: any, p: any): number`

**Parameters:**

- **`t`** `any`
- **`p`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function QuadraticBezierP2( t, p ) {

	return t * t * p;

}
```
</details>

### `QuadraticBezier(t: number, p0: number, p1: number, p2: number): number`

**JSDoc:**
```typescript
/**
 * Computes a point on a Quadratic Bezier curve.
 *
 * @param {number} t - The interpolation factor.
 * @param {number} p0 - The first control point.
 * @param {number} p1 - The second control point.
 * @param {number} p2 - The third control point.
 * @return {number} The calculated point on a Quadratic Bezier curve.
 */
```

**Parameters:**

- **`t`** `number`
- **`p0`** `number`
- **`p1`** `number`
- **`p2`** `number`

**Returns:** `number`

**Calls:**

- `QuadraticBezierP0`
- `QuadraticBezierP1`
- `QuadraticBezierP2`

<details><summary>Code</summary>

```typescript
function QuadraticBezier( t, p0, p1, p2 ) {

	return QuadraticBezierP0( t, p0 ) + QuadraticBezierP1( t, p1 ) +
		QuadraticBezierP2( t, p2 );

}
```
</details>

### `CubicBezierP0(t: any, p: any): number`

**Parameters:**

- **`t`** `any`
- **`p`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function CubicBezierP0( t, p ) {

	const k = 1 - t;
	return k * k * k * p;

}
```
</details>

### `CubicBezierP1(t: any, p: any): number`

**Parameters:**

- **`t`** `any`
- **`p`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function CubicBezierP1( t, p ) {

	const k = 1 - t;
	return 3 * k * k * t * p;

}
```
</details>

### `CubicBezierP2(t: any, p: any): number`

**Parameters:**

- **`t`** `any`
- **`p`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function CubicBezierP2( t, p ) {

	return 3 * ( 1 - t ) * t * t * p;

}
```
</details>

### `CubicBezierP3(t: any, p: any): number`

**Parameters:**

- **`t`** `any`
- **`p`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function CubicBezierP3( t, p ) {

	return t * t * t * p;

}
```
</details>

### `CubicBezier(t: number, p0: number, p1: number, p2: number, p3: number): number`

**JSDoc:**
```typescript
/**
 * Computes a point on a Cubic Bezier curve.
 *
 * @param {number} t - The interpolation factor.
 * @param {number} p0 - The first control point.
 * @param {number} p1 - The second control point.
 * @param {number} p2 - The third control point.
 * @param {number} p3 - The fourth control point.
 * @return {number} The calculated point on a Cubic Bezier curve.
 */
```

**Parameters:**

- **`t`** `number`
- **`p0`** `number`
- **`p1`** `number`
- **`p2`** `number`
- **`p3`** `number`

**Returns:** `number`

**Calls:**

- `CubicBezierP0`
- `CubicBezierP1`
- `CubicBezierP2`
- `CubicBezierP3`

<details><summary>Code</summary>

```typescript
function CubicBezier( t, p0, p1, p2, p3 ) {

	return CubicBezierP0( t, p0 ) + CubicBezierP1( t, p1 ) + CubicBezierP2( t, p2 ) +
		CubicBezierP3( t, p3 );

}
```
</details>


---