[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ImprovedNoise.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/math/ImprovedNoise.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `MathUtils` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_p` | `number[]` | let/var | `[ 151, 160, 137, 91, 90, 15, 131, 13, 201, 95, 96, 53, 194, 233, 7, 225, 140,...` | ✗ |
| `h` | `number` | let/var | `hash & 15` | ✗ |
| `u` | `any` | let/var | `h < 8 ? x : y` | ✗ |
| `v` | `any` | let/var | `h < 4 ? y : h == 12 \|\| h == 14 ? x : z` | ✗ |
| `X` | `number` | let/var | `floorX & 255` | ✗ |
| `Y` | `number` | let/var | `floorY & 255` | ✗ |
| `Z` | `number` | let/var | `floorZ & 255` | ✗ |
| `xMinus1` | `number` | let/var | `x - 1` | ✗ |
| `yMinus1` | `number` | let/var | `y - 1` | ✗ |
| `zMinus1` | `number` | let/var | `z - 1` | ✗ |
| `A` | `number` | let/var | `_p[ X ] + Y` | ✗ |
| `AA` | `number` | let/var | `_p[ A ] + Z` | ✗ |
| `AB` | `number` | let/var | `_p[ A + 1 ] + Z` | ✗ |
| `B` | `number` | let/var | `_p[ X + 1 ] + Y` | ✗ |
| `BA` | `number` | let/var | `_p[ B ] + Z` | ✗ |
| `BB` | `number` | let/var | `_p[ B + 1 ] + Z` | ✗ |


---

## Functions

### `fade(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function fade( t ) {

	return t * t * t * ( t * ( t * 6 - 15 ) + 10 );

}
```
</details>

### `grad(hash: any, x: any, y: any, z: any): any`

**Parameters:**

- **`hash`** `any`
- **`x`** `any`
- **`y`** `any`
- **`z`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function grad( hash, x, y, z ) {

	const h = hash & 15;
	const u = h < 8 ? x : y, v = h < 4 ? y : h == 12 || h == 14 ? x : z;
	return ( ( h & 1 ) == 0 ? u : - u ) + ( ( h & 2 ) == 0 ? v : - v );

}
```
</details>

### `ImprovedNoise.noise(x: number, y: number, z: number): number`

**JSDoc:**
```typescript
/**
	 * Returns a noise value for the given parameters.
	 *
	 * @param {number} x - The x coordinate.
	 * @param {number} y - The y coordinate.
	 * @param {number} z - The z coordinate.
	 * @return {number} The noise value.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`z`** `number`

**Returns:** `number`

**Calls:**

- `Math.floor`
- `fade`
- `lerp`
- `grad`

<details><summary>Code</summary>

```typescript
noise( x, y, z ) {

		const floorX = Math.floor( x ), floorY = Math.floor( y ), floorZ = Math.floor( z );

		const X = floorX & 255, Y = floorY & 255, Z = floorZ & 255;

		x -= floorX;
		y -= floorY;
		z -= floorZ;

		const xMinus1 = x - 1, yMinus1 = y - 1, zMinus1 = z - 1;

		const u = fade( x ), v = fade( y ), w = fade( z );

		const A = _p[ X ] + Y, AA = _p[ A ] + Z, AB = _p[ A + 1 ] + Z, B = _p[ X + 1 ] + Y, BA = _p[ B ] + Z, BB = _p[ B + 1 ] + Z;

		return lerp(
			lerp(
				lerp( grad( _p[ AA ], x, y, z ), grad( _p[ BA ], xMinus1, y, z ), u ),
				lerp( grad( _p[ AB ], x, yMinus1, z ), grad( _p[ BB ], xMinus1, yMinus1, z ), u ),
				v
			),
			lerp(
				lerp( grad( _p[ AA + 1 ], x, y, zMinus1 ), grad( _p[ BA + 1 ], xMinus1, y, zMinus1 ), u ),
				lerp( grad( _p[ AB + 1 ], x, yMinus1, zMinus1 ), grad( _p[ BB + 1 ], xMinus1, yMinus1, zMinus1 ), u ),
				v
			),
			w
		);

	}
```
</details>


---

## Classes

### `ImprovedNoise`

<details><summary>Class Code</summary>

```ts
class ImprovedNoise {

	/**
	 * Returns a noise value for the given parameters.
	 *
	 * @param {number} x - The x coordinate.
	 * @param {number} y - The y coordinate.
	 * @param {number} z - The z coordinate.
	 * @return {number} The noise value.
	 */
	noise( x, y, z ) {

		const floorX = Math.floor( x ), floorY = Math.floor( y ), floorZ = Math.floor( z );

		const X = floorX & 255, Y = floorY & 255, Z = floorZ & 255;

		x -= floorX;
		y -= floorY;
		z -= floorZ;

		const xMinus1 = x - 1, yMinus1 = y - 1, zMinus1 = z - 1;

		const u = fade( x ), v = fade( y ), w = fade( z );

		const A = _p[ X ] + Y, AA = _p[ A ] + Z, AB = _p[ A + 1 ] + Z, B = _p[ X + 1 ] + Y, BA = _p[ B ] + Z, BB = _p[ B + 1 ] + Z;

		return lerp(
			lerp(
				lerp( grad( _p[ AA ], x, y, z ), grad( _p[ BA ], xMinus1, y, z ), u ),
				lerp( grad( _p[ AB ], x, yMinus1, z ), grad( _p[ BB ], xMinus1, yMinus1, z ), u ),
				v
			),
			lerp(
				lerp( grad( _p[ AA + 1 ], x, y, zMinus1 ), grad( _p[ BA + 1 ], xMinus1, y, zMinus1 ), u ),
				lerp( grad( _p[ AB + 1 ], x, yMinus1, zMinus1 ), grad( _p[ BB + 1 ], xMinus1, yMinus1, zMinus1 ), u ),
				v
			),
			w
		);

	}

}
```
</details>

#### Methods

##### `noise(x: number, y: number, z: number): number`

<details><summary>Code</summary>

```ts
noise( x, y, z ) {

		const floorX = Math.floor( x ), floorY = Math.floor( y ), floorZ = Math.floor( z );

		const X = floorX & 255, Y = floorY & 255, Z = floorZ & 255;

		x -= floorX;
		y -= floorY;
		z -= floorZ;

		const xMinus1 = x - 1, yMinus1 = y - 1, zMinus1 = z - 1;

		const u = fade( x ), v = fade( y ), w = fade( z );

		const A = _p[ X ] + Y, AA = _p[ A ] + Z, AB = _p[ A + 1 ] + Z, B = _p[ X + 1 ] + Y, BA = _p[ B ] + Z, BB = _p[ B + 1 ] + Z;

		return lerp(
			lerp(
				lerp( grad( _p[ AA ], x, y, z ), grad( _p[ BA ], xMinus1, y, z ), u ),
				lerp( grad( _p[ AB ], x, yMinus1, z ), grad( _p[ BB ], xMinus1, yMinus1, z ), u ),
				v
			),
			lerp(
				lerp( grad( _p[ AA + 1 ], x, y, zMinus1 ), grad( _p[ BA + 1 ], xMinus1, y, zMinus1 ), u ),
				lerp( grad( _p[ AB + 1 ], x, yMinus1, zMinus1 ), grad( _p[ BB + 1 ], xMinus1, yMinus1, zMinus1 ), u ),
				v
			),
			w
		);

	}
```
</details>


---