[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ParametricFunctions.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/geometries/ParametricFunctions.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `z` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `number` | let/var | `- 2 * ( 1 - Math.cos( u ) / 2 ) * Math.sin( v )` | ✗ |
| `v` | `number` | let/var | `2 * Math.PI * t` | ✗ |
| `a` | `2` | let/var | `2` | ✗ |
| `x` | `number` | let/var | `Math.cos( v ) * ( a + u * Math.cos( v / 2 ) )` | ✗ |
| `y` | `number` | let/var | `Math.sin( v ) * ( a + u * Math.cos( v / 2 ) )` | ✗ |
| `z` | `number` | let/var | `u * Math.sin( v / 2 )` | ✗ |
| `phi` | `number` | let/var | `u / 2` | ✗ |
| `major` | `2.25` | let/var | `2.25` | ✗ |
| `a` | `0.125` | let/var | `0.125` | ✗ |
| `b` | `0.65` | let/var | `0.65` | ✗ |
| `x` | `number` | let/var | `a * Math.cos( t ) * Math.cos( phi ) - b * Math.sin( t ) * Math.sin( phi )` | ✗ |
| `z` | `number` | let/var | `a * Math.cos( t ) * Math.sin( phi ) + b * Math.sin( t ) * Math.cos( phi )` | ✗ |
| `y` | `number` | let/var | `( major + x ) * Math.sin( u )` | ✗ |


---

## Functions

### `klein(v: number, u: number, target: Vector3): void`

**JSDoc:**
```typescript
/**
 * A parametric function representing the Klein bottle.
 *
 * @param {number} v - The `v` coordinate on the surface in the range `[0,1]`.
 * @param {number} u - The `u` coordinate on the surface in the range `[0,1]`.
 * @param {Vector3} target - The target vector that is used to store the method's result.
 */
```

**Parameters:**

- **`v`** `number`
- **`u`** `number`
- **`target`** `Vector3`

**Returns:** `void`

**Calls:**

- `Math.cos`
- `Math.sin`
- `target.set`

<details><summary>Code</summary>

```typescript
function klein( v, u, target ) {

	u *= Math.PI;
	v *= 2 * Math.PI;

	u = u * 2;
	let x, z;
	if ( u < Math.PI ) {

		x = 3 * Math.cos( u ) * ( 1 + Math.sin( u ) ) + ( 2 * ( 1 - Math.cos( u ) / 2 ) ) * Math.cos( u ) * Math.cos( v );
		z = - 8 * Math.sin( u ) - 2 * ( 1 - Math.cos( u ) / 2 ) * Math.sin( u ) * Math.cos( v );

	} else {

		x = 3 * Math.cos( u ) * ( 1 + Math.sin( u ) ) + ( 2 * ( 1 - Math.cos( u ) / 2 ) ) * Math.cos( v + Math.PI );
		z = - 8 * Math.sin( u );

	}

	const y = - 2 * ( 1 - Math.cos( u ) / 2 ) * Math.sin( v );

	target.set( x, y, z );

}
```
</details>

### `plane(u: number, v: number, target: Vector3): void`

**JSDoc:**
```typescript
/**
 * A parametric function representing a flat plane.
 *
 * @param {number} u - The `u` coordinate on the surface in the range `[0,1]`.
 * @param {number} v - The `v` coordinate on the surface in the range `[0,1]`.
 * @param {Vector3} target - The target vector that is used to store the method's result.
 */
```

**Parameters:**

- **`u`** `number`
- **`v`** `number`
- **`target`** `Vector3`

**Returns:** `void`

**Calls:**

- `target.set`

<details><summary>Code</summary>

```typescript
function plane( u, v, target ) {

	target.set( u, 0, v );

}
```
</details>

### `mobius(u: number, t: number, target: Vector3): void`

**JSDoc:**
```typescript
/**
 * A parametric function representing a flat mobius strip.
 *
 * @param {number} u - The `u` coordinate on the surface in the range `[0,1]`.
 * @param {number} t - The `v` coordinate on the surface in the range `[0,1]`.
 * @param {Vector3} target - The target vector that is used to store the method's result.
 */
```

**Parameters:**

- **`u`** `number`
- **`t`** `number`
- **`target`** `Vector3`

**Returns:** `void`

**Calls:**

- `Math.cos`
- `Math.sin`
- `target.set`

**Internal Comments:**
```
// http://www.wolframalpha.com/input/?i=M%C3%B6bius+strip+parametric+equations&lk=1&a=ClashPrefs_*Surface.MoebiusStrip.SurfaceProperty.ParametricEquations- (x3)
```

<details><summary>Code</summary>

```typescript
function mobius( u, t, target ) {

	// http://www.wolframalpha.com/input/?i=M%C3%B6bius+strip+parametric+equations&lk=1&a=ClashPrefs_*Surface.MoebiusStrip.SurfaceProperty.ParametricEquations-
	u = u - 0.5;
	const v = 2 * Math.PI * t;

	const a = 2;

	const x = Math.cos( v ) * ( a + u * Math.cos( v / 2 ) );
	const y = Math.sin( v ) * ( a + u * Math.cos( v / 2 ) );
	const z = u * Math.sin( v / 2 );

	target.set( x, y, z );

}
```
</details>

### `mobius3d(u: number, t: number, target: Vector3): void`

**JSDoc:**
```typescript
/**
 * A parametric function representing a volumetric mobius strip.
 *
 * @param {number} u - The `u` coordinate on the surface in the range `[0,1]`.
 * @param {number} t - The `v` coordinate on the surface in the range `[0,1]`.
 * @param {Vector3} target - The target vector that is used to store the method's result.
 */
```

**Parameters:**

- **`u`** `number`
- **`t`** `number`
- **`target`** `Vector3`

**Returns:** `void`

**Calls:**

- `Math.cos`
- `Math.sin`
- `target.set`

<details><summary>Code</summary>

```typescript
function mobius3d( u, t, target ) {

	u *= Math.PI;
	t *= 2 * Math.PI;

	u = u * 2;
	const phi = u / 2;
	const major = 2.25, a = 0.125, b = 0.65;

	let x = a * Math.cos( t ) * Math.cos( phi ) - b * Math.sin( t ) * Math.sin( phi );
	const z = a * Math.cos( t ) * Math.sin( phi ) + b * Math.sin( t ) * Math.cos( phi );
	const y = ( major + x ) * Math.sin( u );
	x = ( major + x ) * Math.cos( u );

	target.set( x, y, z );

}
```
</details>


---