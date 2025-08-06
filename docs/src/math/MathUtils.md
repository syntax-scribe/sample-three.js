[⬅️ Back to Table of Contents](../../index.md)

# 📄 `MathUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 22 |
| 📊 Variables & Constants | 13 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/math/MathUtils.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_lut` | `string[]` | let/var | `[ '00', '01', '02', '03', '04', '05', '06', '07', '08', '09', '0a', '0b', '0c...` | ✗ |
| `_seed` | `number` | let/var | `1234567` | ✗ |
| `DEG2RAD` | `number` | let/var | `Math.PI / 180` | ✗ |
| `RAD2DEG` | `number` | let/var | `180 / Math.PI` | ✗ |
| `d0` | `number` | let/var | `Math.random() * 0xffffffff \| 0` | ✗ |
| `d1` | `number` | let/var | `Math.random() * 0xffffffff \| 0` | ✗ |
| `d2` | `number` | let/var | `Math.random() * 0xffffffff \| 0` | ✗ |
| `d3` | `number` | let/var | `Math.random() * 0xffffffff \| 0` | ✗ |
| `uuid` | `string` | let/var | `_lut[ d0 & 0xff ] + _lut[ d0 >> 8 & 0xff ] + _lut[ d0 >> 16 & 0xff ] + _lut[ ...` | ✗ |
| `t` | `number` | let/var | `_seed += 0x6D2B79F5` | ✗ |
| `cos` | `(x: number) => number` | let/var | `Math.cos` | ✗ |
| `sin` | `(x: number) => number` | let/var | `Math.sin` | ✗ |
| `MathUtils` | `{ DEG2RAD: number; RAD2DEG: number; g...` | let/var | `{ DEG2RAD: DEG2RAD, RAD2DEG: RAD2DEG, /** * Generate a [UUID]{@link https://e...` | ✗ |


---

## Functions

### `generateUUID(): string`

**JSDoc:**
```typescript
/**
 * Generate a [UUID]{@link https://en.wikipedia.org/wiki/Universally_unique_identifier}
 * (universally unique identifier).
 *
 * @return {string} The UUID.
 */
```

**Returns:** `string`

**Calls:**

- `Math.random`
- `uuid.toLowerCase`

**Internal Comments:**
```
// http://stackoverflow.com/questions/105034/how-to-create-a-guid-uuid-in-javascript/21963136#21963136 (x2)
// .toLowerCase() here flattens concatenated strings to save heap memory space.
```

<details><summary>Code</summary>

```typescript
function generateUUID() {

	// http://stackoverflow.com/questions/105034/how-to-create-a-guid-uuid-in-javascript/21963136#21963136

	const d0 = Math.random() * 0xffffffff | 0;
	const d1 = Math.random() * 0xffffffff | 0;
	const d2 = Math.random() * 0xffffffff | 0;
	const d3 = Math.random() * 0xffffffff | 0;
	const uuid = _lut[ d0 & 0xff ] + _lut[ d0 >> 8 & 0xff ] + _lut[ d0 >> 16 & 0xff ] + _lut[ d0 >> 24 & 0xff ] + '-' +
			_lut[ d1 & 0xff ] + _lut[ d1 >> 8 & 0xff ] + '-' + _lut[ d1 >> 16 & 0x0f | 0x40 ] + _lut[ d1 >> 24 & 0xff ] + '-' +
			_lut[ d2 & 0x3f | 0x80 ] + _lut[ d2 >> 8 & 0xff ] + '-' + _lut[ d2 >> 16 & 0xff ] + _lut[ d2 >> 24 & 0xff ] +
			_lut[ d3 & 0xff ] + _lut[ d3 >> 8 & 0xff ] + _lut[ d3 >> 16 & 0xff ] + _lut[ d3 >> 24 & 0xff ];

	// .toLowerCase() here flattens concatenated strings to save heap memory space.
	return uuid.toLowerCase();

}
```
</details>

### `clamp(value: number, min: number, max: number): number`

**JSDoc:**
```typescript
/**
 * Clamps the given value between min and max.
 *
 * @param {number} value - The value to clamp.
 * @param {number} min - The min value.
 * @param {number} max - The max value.
 * @return {number} The clamped value.
 */
```

**Parameters:**

- **`value`** `number`
- **`min`** `number`
- **`max`** `number`

**Returns:** `number`

**Calls:**

- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function clamp( value, min, max ) {

	return Math.max( min, Math.min( max, value ) );

}
```
</details>

### `euclideanModulo(n: number, m: number): number`

**JSDoc:**
```typescript
/**
 * Computes the Euclidean modulo of the given parameters that
 * is `( ( n % m ) + m ) % m`.
 *
 * @param {number} n - The first parameter.
 * @param {number} m - The second parameter.
 * @return {number} The Euclidean modulo.
 */
```

**Parameters:**

- **`n`** `number`
- **`m`** `number`

**Returns:** `number`

**Internal Comments:**
```
// https://en.wikipedia.org/wiki/Modulo_operation
```

<details><summary>Code</summary>

```typescript
function euclideanModulo( n, m ) {

	// https://en.wikipedia.org/wiki/Modulo_operation

	return ( ( n % m ) + m ) % m;

}
```
</details>

### `mapLinear(x: number, a1: number, a2: number, b1: number, b2: number): number`

**JSDoc:**
```typescript
/**
 * Performs a linear mapping from range `<a1, a2>` to range `<b1, b2>`
 * for the given value.
 *
 * @param {number} x - The value to be mapped.
 * @param {number} a1 - Minimum value for range A.
 * @param {number} a2 - Maximum value for range A.
 * @param {number} b1 - Minimum value for range B.
 * @param {number} b2 - Maximum value for range B.
 * @return {number} The mapped value.
 */
```

**Parameters:**

- **`x`** `number`
- **`a1`** `number`
- **`a2`** `number`
- **`b1`** `number`
- **`b2`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function mapLinear( x, a1, a2, b1, b2 ) {

	return b1 + ( x - a1 ) * ( b2 - b1 ) / ( a2 - a1 );

}
```
</details>

### `inverseLerp(x: number, y: number, value: number): number`

**JSDoc:**
```typescript
/**
 * Returns the percentage in the closed interval `[0, 1]` of the given value
 * between the start and end point.
 *
 * @param {number} x - The start point
 * @param {number} y - The end point.
 * @param {number} value - A value between start and end.
 * @return {number} The interpolation factor.
 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`value`** `number`

**Returns:** `number`

**Internal Comments:**
```
// https://www.gamedev.net/tutorials/programming/general-and-gameplay-programming/inverse-lerp-a-super-useful-yet-often-overlooked-function-r5230/
```

<details><summary>Code</summary>

```typescript
function inverseLerp( x, y, value ) {

	// https://www.gamedev.net/tutorials/programming/general-and-gameplay-programming/inverse-lerp-a-super-useful-yet-often-overlooked-function-r5230/

	if ( x !== y ) {

		return ( value - x ) / ( y - x );

	} else {

		return 0;

	}

}
```
</details>

### `lerp(x: number, y: number, t: number): number`

**JSDoc:**
```typescript
/**
 * Returns a value linearly interpolated from two known points based on the given interval -
 * `t = 0` will return `x` and `t = 1` will return `y`.
 *
 * @param {number} x - The start point
 * @param {number} y - The end point.
 * @param {number} t - The interpolation factor in the closed interval `[0, 1]`.
 * @return {number} The interpolated value.
 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`t`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function lerp( x, y, t ) {

	return ( 1 - t ) * x + t * y;

}
```
</details>

### `damp(x: number, y: number, lambda: number, dt: number): number`

**JSDoc:**
```typescript
/**
 * Smoothly interpolate a number from `x` to `y` in  a spring-like manner using a delta
 * time to maintain frame rate independent movement. For details, see
 * [Frame rate independent damping using lerp]{@link http://www.rorydriscoll.com/2016/03/07/frame-rate-independent-damping-using-lerp/}.
 *
 * @param {number} x - The current point.
 * @param {number} y - The target point.
 * @param {number} lambda - A higher lambda value will make the movement more sudden,
 * and a lower value will make the movement more gradual.
 * @param {number} dt - Delta time in seconds.
 * @return {number} The interpolated value.
 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`lambda`** `number`
- **`dt`** `number`

**Returns:** `number`

**Calls:**

- `lerp`
- `Math.exp`

<details><summary>Code</summary>

```typescript
function damp( x, y, lambda, dt ) {

	return lerp( x, y, 1 - Math.exp( - lambda * dt ) );

}
```
</details>

### `pingpong(x: number, length: number): number`

**JSDoc:**
```typescript
/**
 * Returns a value that alternates between `0` and the given `length` parameter.
 *
 * @param {number} x - The value to pingpong.
 * @param {number} [length=1] - The positive value the function will pingpong to.
 * @return {number} The alternated value.
 */
```

**Parameters:**

- **`x`** `number`
- **`length`** `number`

**Returns:** `number`

**Calls:**

- `Math.abs`
- `euclideanModulo`

**Internal Comments:**
```
// https://www.desmos.com/calculator/vcsjnyz7x4
```

<details><summary>Code</summary>

```typescript
function pingpong( x, length = 1 ) {

	// https://www.desmos.com/calculator/vcsjnyz7x4

	return length - Math.abs( euclideanModulo( x, length * 2 ) - length );

}
```
</details>

### `smoothstep(x: number, min: number, max: number): number`

**JSDoc:**
```typescript
/**
 * Returns a value in the range `[0,1]` that represents the percentage that `x` has
 * moved between `min` and `max`, but smoothed or slowed down the closer `x` is to
 * the `min` and `max`.
 *
 * See [Smoothstep]{@link http://en.wikipedia.org/wiki/Smoothstep} for more details.
 *
 * @param {number} x - The value to evaluate based on its position between min and max.
 * @param {number} min - The min value. Any x value below min will be `0`.
 * @param {number} max - The max value. Any x value above max will be `1`.
 * @return {number} The alternated value.
 */
```

**Parameters:**

- **`x`** `number`
- **`min`** `number`
- **`max`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function smoothstep( x, min, max ) {

	if ( x <= min ) return 0;
	if ( x >= max ) return 1;

	x = ( x - min ) / ( max - min );

	return x * x * ( 3 - 2 * x );

}
```
</details>

### `smootherstep(x: number, min: number, max: number): number`

**JSDoc:**
```typescript
/**
 * A [variation on smoothstep]{@link https://en.wikipedia.org/wiki/Smoothstep#Variations}
 * that has zero 1st and 2nd order derivatives at x=0 and x=1.
 *
 * @param {number} x - The value to evaluate based on its position between min and max.
 * @param {number} min - The min value. Any x value below min will be `0`.
 * @param {number} max - The max value. Any x value above max will be `1`.
 * @return {number} The alternated value.
 */
```

**Parameters:**

- **`x`** `number`
- **`min`** `number`
- **`max`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function smootherstep( x, min, max ) {

	if ( x <= min ) return 0;
	if ( x >= max ) return 1;

	x = ( x - min ) / ( max - min );

	return x * x * x * ( x * ( x * 6 - 15 ) + 10 );

}
```
</details>

### `randInt(low: number, high: number): number`

**JSDoc:**
```typescript
/**
 * Returns a random integer from `<low, high>` interval.
 *
 * @param {number} low - The lower value boundary.
 * @param {number} high - The upper value boundary
 * @return {number} A random integer.
 */
```

**Parameters:**

- **`low`** `number`
- **`high`** `number`

**Returns:** `number`

**Calls:**

- `Math.floor`
- `Math.random`

<details><summary>Code</summary>

```typescript
function randInt( low, high ) {

	return low + Math.floor( Math.random() * ( high - low + 1 ) );

}
```
</details>

### `randFloat(low: number, high: number): number`

**JSDoc:**
```typescript
/**
 * Returns a random float from `<low, high>` interval.
 *
 * @param {number} low - The lower value boundary.
 * @param {number} high - The upper value boundary
 * @return {number} A random float.
 */
```

**Parameters:**

- **`low`** `number`
- **`high`** `number`

**Returns:** `number`

**Calls:**

- `Math.random`

<details><summary>Code</summary>

```typescript
function randFloat( low, high ) {

	return low + Math.random() * ( high - low );

}
```
</details>

### `randFloatSpread(range: number): number`

**JSDoc:**
```typescript
/**
 * Returns a random integer from `<-range/2, range/2>` interval.
 *
 * @param {number} range - Defines the value range.
 * @return {number} A random float.
 */
```

**Parameters:**

- **`range`** `number`

**Returns:** `number`

**Calls:**

- `Math.random`

<details><summary>Code</summary>

```typescript
function randFloatSpread( range ) {

	return range * ( 0.5 - Math.random() );

}
```
</details>

### `seededRandom(s: number): number`

**JSDoc:**
```typescript
/**
 * Returns a deterministic pseudo-random float in the interval `[0, 1]`.
 *
 * @param {number} [s] - The integer seed.
 * @return {number} A random float.
 */
```

**Parameters:**

- **`s`** `number`

**Returns:** `number`

**Calls:**

- `Math.imul`

**Internal Comments:**
```
// Mulberry32 generator (x2)
```

<details><summary>Code</summary>

```typescript
function seededRandom( s ) {

	if ( s !== undefined ) _seed = s;

	// Mulberry32 generator

	let t = _seed += 0x6D2B79F5;

	t = Math.imul( t ^ t >>> 15, t | 1 );

	t ^= t + Math.imul( t ^ t >>> 7, t | 61 );

	return ( ( t ^ t >>> 14 ) >>> 0 ) / 4294967296;

}
```
</details>

### `degToRad(degrees: number): number`

**JSDoc:**
```typescript
/**
 * Converts degrees to radians.
 *
 * @param {number} degrees - A value in degrees.
 * @return {number} The converted value in radians.
 */
```

**Parameters:**

- **`degrees`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function degToRad( degrees ) {

	return degrees * DEG2RAD;

}
```
</details>

### `radToDeg(radians: number): number`

**JSDoc:**
```typescript
/**
 * Converts radians to degrees.
 *
 * @param {number} radians - A value in radians.
 * @return {number} The converted value in degrees.
 */
```

**Parameters:**

- **`radians`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function radToDeg( radians ) {

	return radians * RAD2DEG;

}
```
</details>

### `isPowerOfTwo(value: number): boolean`

**JSDoc:**
```typescript
/**
 * Returns `true` if the given number is a power of two.
 *
 * @param {number} value - The value to check.
 * @return {boolean} Whether the given number is a power of two or not.
 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isPowerOfTwo( value ) {

	return ( value & ( value - 1 ) ) === 0 && value !== 0;

}
```
</details>

### `ceilPowerOfTwo(value: number): number`

**JSDoc:**
```typescript
/**
 * Returns the smallest power of two that is greater than or equal to the given number.
 *
 * @param {number} value - The value to find a POT for.
 * @return {number} The smallest power of two that is greater than or equal to the given number.
 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.ceil`
- `Math.log`

<details><summary>Code</summary>

```typescript
function ceilPowerOfTwo( value ) {

	return Math.pow( 2, Math.ceil( Math.log( value ) / Math.LN2 ) );

}
```
</details>

### `floorPowerOfTwo(value: number): number`

**JSDoc:**
```typescript
/**
 * Returns the largest power of two that is less than or equal to the given number.
 *
 * @param {number} value - The value to find a POT for.
 * @return {number} The largest power of two that is less than or equal to the given number.
 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.floor`
- `Math.log`

<details><summary>Code</summary>

```typescript
function floorPowerOfTwo( value ) {

	return Math.pow( 2, Math.floor( Math.log( value ) / Math.LN2 ) );

}
```
</details>

### `setQuaternionFromProperEuler(q: Quaternion, a: number, b: number, c: number, order: "XYX" | "XZX" | "YXY" | "YZY" | "ZXZ" | "ZYZ"): void`

**JSDoc:**
```typescript
/**
 * Sets the given quaternion from the [Intrinsic Proper Euler Angles]{@link https://en.wikipedia.org/wiki/Euler_angles}
 * defined by the given angles and order.
 *
 * Rotations are applied to the axes in the order specified by order:
 * rotation by angle `a` is applied first, then by angle `b`, then by angle `c`.
 *
 * @param {Quaternion} q - The quaternion to set.
 * @param {number} a - The rotation applied to the first axis, in radians.
 * @param {number} b - The rotation applied to the second axis, in radians.
 * @param {number} c - The rotation applied to the third axis, in radians.
 * @param {('XYX'|'XZX'|'YXY'|'YZY'|'ZXZ'|'ZYZ')} order - A string specifying the axes order.
 */
```

**Parameters:**

- **`q`** `Quaternion`
- **`a`** `number`
- **`b`** `number`
- **`c`** `number`
- **`order`** `"XYX" | "XZX" | "YXY" | "YZY" | "ZXZ" | "ZYZ"`

**Returns:** `void`

**Calls:**

- `cos`
- `sin`
- `q.set`
- `console.warn`

<details><summary>Code</summary>

```typescript
function setQuaternionFromProperEuler( q, a, b, c, order ) {

	const cos = Math.cos;
	const sin = Math.sin;

	const c2 = cos( b / 2 );
	const s2 = sin( b / 2 );

	const c13 = cos( ( a + c ) / 2 );
	const s13 = sin( ( a + c ) / 2 );

	const c1_3 = cos( ( a - c ) / 2 );
	const s1_3 = sin( ( a - c ) / 2 );

	const c3_1 = cos( ( c - a ) / 2 );
	const s3_1 = sin( ( c - a ) / 2 );

	switch ( order ) {

		case 'XYX':
			q.set( c2 * s13, s2 * c1_3, s2 * s1_3, c2 * c13 );
			break;

		case 'YZY':
			q.set( s2 * s1_3, c2 * s13, s2 * c1_3, c2 * c13 );
			break;

		case 'ZXZ':
			q.set( s2 * c1_3, s2 * s1_3, c2 * s13, c2 * c13 );
			break;

		case 'XZX':
			q.set( c2 * s13, s2 * s3_1, s2 * c3_1, c2 * c13 );
			break;

		case 'YXY':
			q.set( s2 * c3_1, c2 * s13, s2 * s3_1, c2 * c13 );
			break;

		case 'ZYZ':
			q.set( s2 * s3_1, s2 * c3_1, c2 * s13, c2 * c13 );
			break;

		default:
			console.warn( 'THREE.MathUtils: .setQuaternionFromProperEuler() encountered an unknown order: ' + order );

	}

}
```
</details>

### `denormalize(value: number, array: TypedArray): number`

**JSDoc:**
```typescript
/**
 * Denormalizes the given value according to the given typed array.
 *
 * @param {number} value - The value to denormalize.
 * @param {TypedArray} array - The typed array that defines the data type of the value.
 * @return {number} The denormalize (float) value in the range `[0,1]`.
 */
```

**Parameters:**

- **`value`** `number`
- **`array`** `TypedArray`

**Returns:** `number`

**Calls:**

- `Math.max`

<details><summary>Code</summary>

```typescript
function denormalize( value, array ) {

	switch ( array.constructor ) {

		case Float32Array:

			return value;

		case Uint32Array:

			return value / 4294967295.0;

		case Uint16Array:

			return value / 65535.0;

		case Uint8Array:

			return value / 255.0;

		case Int32Array:

			return Math.max( value / 2147483647.0, - 1.0 );

		case Int16Array:

			return Math.max( value / 32767.0, - 1.0 );

		case Int8Array:

			return Math.max( value / 127.0, - 1.0 );

		default:

			throw new Error( 'Invalid component type.' );

	}

}
```
</details>

### `normalize(value: number, array: TypedArray): number`

**JSDoc:**
```typescript
/**
 * Normalizes the given value according to the given typed array.
 *
 * @param {number} value - The float value in the range `[0,1]` to normalize.
 * @param {TypedArray} array - The typed array that defines the data type of the value.
 * @return {number} The normalize value.
 */
```

**Parameters:**

- **`value`** `number`
- **`array`** `TypedArray`

**Returns:** `number`

**Calls:**

- `Math.round`

<details><summary>Code</summary>

```typescript
function normalize( value, array ) {

	switch ( array.constructor ) {

		case Float32Array:

			return value;

		case Uint32Array:

			return Math.round( value * 4294967295.0 );

		case Uint16Array:

			return Math.round( value * 65535.0 );

		case Uint8Array:

			return Math.round( value * 255.0 );

		case Int32Array:

			return Math.round( value * 2147483647.0 );

		case Int16Array:

			return Math.round( value * 32767.0 );

		case Int8Array:

			return Math.round( value * 127.0 );

		default:

			throw new Error( 'Invalid component type.' );

	}

}
```
</details>


---