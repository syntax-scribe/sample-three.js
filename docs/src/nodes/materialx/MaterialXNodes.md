[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MaterialXNodes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 42 |
| 📦 Imports | 34 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/materialx/MaterialXNodes.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `mx_perlin_noise_float` | `./lib/mx_noise.js` |
| `mx_perlin_noise_vec3` | `./lib/mx_noise.js` |
| `worley_noise_float` | `./lib/mx_noise.js` |
| `worley_noise_vec2` | `./lib/mx_noise.js` |
| `worley_noise_vec3` | `./lib/mx_noise.js` |
| `cell_noise_float` | `./lib/mx_noise.js` |
| `unifiednoise2d` | `./lib/mx_noise.js` |
| `unifiednoise3d` | `./lib/mx_noise.js` |
| `fractal_noise_float` | `./lib/mx_noise.js` |
| `fractal_noise_vec2` | `./lib/mx_noise.js` |
| `fractal_noise_vec3` | `./lib/mx_noise.js` |
| `fractal_noise_vec4` | `./lib/mx_noise.js` |
| `mx_hsvtorgb` | `./lib/mx_hsv.js` |
| `mx_rgbtohsv` | `./lib/mx_hsv.js` |
| `mx_srgb_texture_to_lin_rec709` | `./lib/mx_transform_color.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |
| `int` | `../tsl/TSLBase.js` |
| `add` | `../tsl/TSLBase.js` |
| `sub` | `../tsl/TSLBase.js` |
| `mul` | `../tsl/TSLBase.js` |
| `div` | `../tsl/TSLBase.js` |
| `mod` | `../tsl/TSLBase.js` |
| `atan` | `../tsl/TSLBase.js` |
| `mix` | `../tsl/TSLBase.js` |
| `pow` | `../tsl/TSLBase.js` |
| `smoothstep` | `../tsl/TSLBase.js` |
| `uv` | `../accessors/UV.js` |
| `bumpMap` | `../display/BumpMapNode.js` |
| `rotate` | `../utils/RotateNode.js` |
| `frameId` | `../utils/Timer.js` |
| `time` | `../utils/Timer.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `map` | `{ x: number; r: number; y: number; g:...` | let/var | `{ x: 0, r: 0, y: 1, g: 1, z: 2, b: 2, w: 3, a: 3 }` | ✗ |
| `map` | `{ x: number; r: number; y: number; g:...` | let/var | `{ x: 0, r: 0, y: 1, g: 1, z: 2, b: 2, w: 3, a: 3 }` | ✗ |
| `uv` | `any` | let/var | `texcoord` | ✗ |


---

## Functions

### `mx_aastep(threshold: any, value: any): any`

**Parameters:**

- **`threshold`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `float (from ../tsl/TSLBase.js)`
- `vec2( value.dFdx(), value.dFdy() ).length().mul`
- `smoothstep (from ../tsl/TSLBase.js)`
- `threshold.sub`
- `threshold.add`

<details><summary>Code</summary>

```typescript
( threshold, value ) => {

	threshold = float( threshold );
	value = float( value );

	const afwidth = vec2( value.dFdx(), value.dFdy() ).length().mul( 0.70710678118654757 );

	return smoothstep( threshold.sub( afwidth ), threshold.add( afwidth ), value );

}
```
</details>

### `_ramp(a: any, b: any, uv: any, p: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`uv`** `any`
- **`p`** `any`

**Returns:** `any`

**Calls:**

- `mix (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( a, b, uv, p ) => mix( a, b, uv[ p ].clamp() )
```
</details>

### `mx_ramplr(valuel: any, valuer: any, texcoord: AttributeNode<vec2>): any`

**Parameters:**

- **`valuel`** `any`
- **`valuer`** `any`
- **`texcoord`** `AttributeNode<vec2>`

**Returns:** `any`

**Calls:**

- `_ramp`

<details><summary>Code</summary>

```typescript
( valuel, valuer, texcoord = uv() ) => _ramp( valuel, valuer, texcoord, 'x' )
```
</details>

### `mx_ramptb(valuet: any, valueb: any, texcoord: AttributeNode<vec2>): any`

**Parameters:**

- **`valuet`** `any`
- **`valueb`** `any`
- **`texcoord`** `AttributeNode<vec2>`

**Returns:** `any`

**Calls:**

- `_ramp`

<details><summary>Code</summary>

```typescript
( valuet, valueb, texcoord = uv() ) => _ramp( valuet, valueb, texcoord, 'y' )
```
</details>

### `mx_ramp4(valuetl: any, valuetr: any, valuebl: any, valuebr: any, texcoord: AttributeNode<vec2>): any`

**Parameters:**

- **`valuetl`** `any`
- **`valuetr`** `any`
- **`valuebl`** `any`
- **`valuebr`** `any`
- **`texcoord`** `AttributeNode<vec2>`

**Returns:** `any`

**Calls:**

- `texcoord.x.clamp`
- `texcoord.y.clamp`
- `mix (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
(
	valuetl, valuetr, valuebl, valuebr, texcoord = uv()
) => {

	const u = texcoord.x.clamp();
	const v = texcoord.y.clamp();
	const top = mix( valuetl, valuetr, u );
	const bottom = mix( valuebl, valuebr, u );
	return mix( top, bottom, v );

}
```
</details>

### `_split(a: any, b: any, center: any, uv: any, p: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`center`** `any`
- **`uv`** `any`
- **`p`** `any`

**Returns:** `any`

**Calls:**

- `mix (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( a, b, center, uv, p ) => mix( a, b, mx_aastep( center, uv[ p ] ) )
```
</details>

### `mx_splitlr(valuel: any, valuer: any, center: any, texcoord: AttributeNode<vec2>): any`

**Parameters:**

- **`valuel`** `any`
- **`valuer`** `any`
- **`center`** `any`
- **`texcoord`** `AttributeNode<vec2>`

**Returns:** `any`

**Calls:**

- `_split`

<details><summary>Code</summary>

```typescript
( valuel, valuer, center, texcoord = uv() ) => _split( valuel, valuer, center, texcoord, 'x' )
```
</details>

### `mx_splittb(valuet: any, valueb: any, center: any, texcoord: AttributeNode<vec2>): any`

**Parameters:**

- **`valuet`** `any`
- **`valueb`** `any`
- **`center`** `any`
- **`texcoord`** `AttributeNode<vec2>`

**Returns:** `any`

**Calls:**

- `_split`

<details><summary>Code</summary>

```typescript
( valuet, valueb, center, texcoord = uv() ) => _split( valuet, valueb, center, texcoord, 'y' )
```
</details>

### `mx_transform_uv(uv_scale: number, uv_offset: number, uv_geo: AttributeNode<vec2>): any`

**Parameters:**

- **`uv_scale`** `number`
- **`uv_offset`** `number`
- **`uv_geo`** `AttributeNode<vec2>`

**Returns:** `any`

**Calls:**

- `uv_geo.mul( uv_scale ).add`

<details><summary>Code</summary>

```typescript
( uv_scale = 1, uv_offset = 0, uv_geo = uv() ) => uv_geo.mul( uv_scale ).add( uv_offset )
```
</details>

### `mx_safepower(in1: any, in2: number): any`

**Parameters:**

- **`in1`** `any`
- **`in2`** `number`

**Returns:** `any`

**Calls:**

- `float (from ../tsl/TSLBase.js)`
- `in1.abs().pow( in2 ).mul`
- `in1.sign`

<details><summary>Code</summary>

```typescript
( in1, in2 = 1 ) => {

	in1 = float( in1 );

	return in1.abs().pow( in2 ).mul( in1.sign() );

}
```
</details>

### `mx_contrast(input: any, amount: number, pivot: number): any`

**Parameters:**

- **`input`** `any`
- **`amount`** `number`
- **`pivot`** `number`

**Returns:** `any`

**Calls:**

- `float( input ).sub( pivot ).mul( amount ).add`

<details><summary>Code</summary>

```typescript
( input, amount = 1, pivot = .5 ) => float( input ).sub( pivot ).mul( amount ).add( pivot )
```
</details>

### `mx_noise_float(texcoord: AttributeNode<vec2>, amplitude: number, pivot: number): any`

**Parameters:**

- **`texcoord`** `AttributeNode<vec2>`
- **`amplitude`** `number`
- **`pivot`** `number`

**Returns:** `any`

**Calls:**

- `mx_perlin_noise_float( texcoord.convert( 'vec2|vec3' ) ).mul( amplitude ).add`

<details><summary>Code</summary>

```typescript
( texcoord = uv(), amplitude = 1, pivot = 0 ) => mx_perlin_noise_float( texcoord.convert( 'vec2|vec3' ) ).mul( amplitude ).add( pivot )
```
</details>

### `mx_noise_vec3(texcoord: AttributeNode<vec2>, amplitude: number, pivot: number): any`

**Parameters:**

- **`texcoord`** `AttributeNode<vec2>`
- **`amplitude`** `number`
- **`pivot`** `number`

**Returns:** `any`

**Calls:**

- `mx_perlin_noise_vec3( texcoord.convert( 'vec2|vec3' ) ).mul( amplitude ).add`

<details><summary>Code</summary>

```typescript
( texcoord = uv(), amplitude = 1, pivot = 0 ) => mx_perlin_noise_vec3( texcoord.convert( 'vec2|vec3' ) ).mul( amplitude ).add( pivot )
```
</details>

### `mx_noise_vec4(texcoord: AttributeNode<vec2>, amplitude: number, pivot: number): any`

**Parameters:**

- **`texcoord`** `AttributeNode<vec2>`
- **`amplitude`** `number`
- **`pivot`** `number`

**Returns:** `any`

**Calls:**

- `texcoord.convert`
- `vec4 (from ../tsl/TSLBase.js)`
- `mx_perlin_noise_vec3 (from ./lib/mx_noise.js)`
- `mx_perlin_noise_float (from ./lib/mx_noise.js)`
- `texcoord.add`
- `vec2 (from ../tsl/TSLBase.js)`
- `noise_vec4.mul( amplitude ).add`

<details><summary>Code</summary>

```typescript
( texcoord = uv(), amplitude = 1, pivot = 0 ) => {

	texcoord = texcoord.convert( 'vec2|vec3' ); // overloading type

	const noise_vec4 = vec4( mx_perlin_noise_vec3( texcoord ), mx_perlin_noise_float( texcoord.add( vec2( 19, 73 ) ) ) );

	return noise_vec4.mul( amplitude ).add( pivot );

}
```
</details>

### `mx_unifiednoise2d(noiseType: any, texcoord: AttributeNode<vec2>, freq: any, offset: any, jitter: number, outmin: number, outmax: number, clampoutput: boolean, octaves: number, lacunarity: number, diminish: number): any`

**Parameters:**

- **`noiseType`** `any`
- **`texcoord`** `AttributeNode<vec2>`
- **`freq`** `any`
- **`offset`** `any`
- **`jitter`** `number`
- **`outmin`** `number`
- **`outmax`** `number`
- **`clampoutput`** `boolean`
- **`octaves`** `number`
- **`lacunarity`** `number`
- **`diminish`** `number`

**Returns:** `any`

**Calls:**

- `unifiednoise2d (from ./lib/mx_noise.js)`

<details><summary>Code</summary>

```typescript
( noiseType, texcoord = uv(), freq = vec2( 1, 1 ), offset = vec2( 0, 0 ), jitter = 1, outmin = 0, outmax = 1, clampoutput = false, octaves = 1, lacunarity = 2, diminish = .5 ) => unifiednoise2d( noiseType, texcoord.convert( 'vec2|vec3' ), freq, offset, jitter, outmin, outmax, clampoutput, octaves, lacunarity, diminish )
```
</details>

### `mx_unifiednoise3d(noiseType: any, texcoord: AttributeNode<vec2>, freq: any, offset: any, jitter: number, outmin: number, outmax: number, clampoutput: boolean, octaves: number, lacunarity: number, diminish: number): any`

**Parameters:**

- **`noiseType`** `any`
- **`texcoord`** `AttributeNode<vec2>`
- **`freq`** `any`
- **`offset`** `any`
- **`jitter`** `number`
- **`outmin`** `number`
- **`outmax`** `number`
- **`clampoutput`** `boolean`
- **`octaves`** `number`
- **`lacunarity`** `number`
- **`diminish`** `number`

**Returns:** `any`

**Calls:**

- `unifiednoise3d (from ./lib/mx_noise.js)`

<details><summary>Code</summary>

```typescript
( noiseType, texcoord = uv(), freq = vec2( 1, 1 ), offset = vec2( 0, 0 ), jitter = 1, outmin = 0, outmax = 1, clampoutput = false, octaves = 1, lacunarity = 2, diminish = .5 ) => unifiednoise3d( noiseType, texcoord.convert( 'vec2|vec3' ), freq, offset, jitter, outmin, outmax, clampoutput, octaves, lacunarity, diminish )
```
</details>

### `mx_worley_noise_float(texcoord: AttributeNode<vec2>, jitter: number): any`

**Parameters:**

- **`texcoord`** `AttributeNode<vec2>`
- **`jitter`** `number`

**Returns:** `any`

**Calls:**

- `worley_noise_float (from ./lib/mx_noise.js)`

<details><summary>Code</summary>

```typescript
( texcoord = uv(), jitter = 1 ) => worley_noise_float( texcoord.convert( 'vec2|vec3' ), jitter, int( 1 ) )
```
</details>

### `mx_worley_noise_vec2(texcoord: AttributeNode<vec2>, jitter: number): any`

**Parameters:**

- **`texcoord`** `AttributeNode<vec2>`
- **`jitter`** `number`

**Returns:** `any`

**Calls:**

- `worley_noise_vec2 (from ./lib/mx_noise.js)`

<details><summary>Code</summary>

```typescript
( texcoord = uv(), jitter = 1 ) => worley_noise_vec2( texcoord.convert( 'vec2|vec3' ), jitter, int( 1 ) )
```
</details>

### `mx_worley_noise_vec3(texcoord: AttributeNode<vec2>, jitter: number): any`

**Parameters:**

- **`texcoord`** `AttributeNode<vec2>`
- **`jitter`** `number`

**Returns:** `any`

**Calls:**

- `worley_noise_vec3 (from ./lib/mx_noise.js)`

<details><summary>Code</summary>

```typescript
( texcoord = uv(), jitter = 1 ) => worley_noise_vec3( texcoord.convert( 'vec2|vec3' ), jitter, int( 1 ) )
```
</details>

### `mx_cell_noise_float(texcoord: AttributeNode<vec2>): any`

**Parameters:**

- **`texcoord`** `AttributeNode<vec2>`

**Returns:** `any`

**Calls:**

- `cell_noise_float (from ./lib/mx_noise.js)`

<details><summary>Code</summary>

```typescript
( texcoord = uv() ) => cell_noise_float( texcoord.convert( 'vec2|vec3' ) )
```
</details>

### `mx_fractal_noise_float(position: AttributeNode<vec2>, octaves: number, lacunarity: number, diminish: number, amplitude: number): any`

**Parameters:**

- **`position`** `AttributeNode<vec2>`
- **`octaves`** `number`
- **`lacunarity`** `number`
- **`diminish`** `number`
- **`amplitude`** `number`

**Returns:** `any`

**Calls:**

- `fractal_noise_float( position, int( octaves ), lacunarity, diminish ).mul`

<details><summary>Code</summary>

```typescript
( position = uv(), octaves = 3, lacunarity = 2, diminish = .5, amplitude = 1 ) => fractal_noise_float( position, int( octaves ), lacunarity, diminish ).mul( amplitude )
```
</details>

### `mx_fractal_noise_vec2(position: AttributeNode<vec2>, octaves: number, lacunarity: number, diminish: number, amplitude: number): any`

**Parameters:**

- **`position`** `AttributeNode<vec2>`
- **`octaves`** `number`
- **`lacunarity`** `number`
- **`diminish`** `number`
- **`amplitude`** `number`

**Returns:** `any`

**Calls:**

- `fractal_noise_vec2( position, int( octaves ), lacunarity, diminish ).mul`

<details><summary>Code</summary>

```typescript
( position = uv(), octaves = 3, lacunarity = 2, diminish = .5, amplitude = 1 ) => fractal_noise_vec2( position, int( octaves ), lacunarity, diminish ).mul( amplitude )
```
</details>

### `mx_fractal_noise_vec3(position: AttributeNode<vec2>, octaves: number, lacunarity: number, diminish: number, amplitude: number): any`

**Parameters:**

- **`position`** `AttributeNode<vec2>`
- **`octaves`** `number`
- **`lacunarity`** `number`
- **`diminish`** `number`
- **`amplitude`** `number`

**Returns:** `any`

**Calls:**

- `fractal_noise_vec3( position, int( octaves ), lacunarity, diminish ).mul`

<details><summary>Code</summary>

```typescript
( position = uv(), octaves = 3, lacunarity = 2, diminish = .5, amplitude = 1 ) => fractal_noise_vec3( position, int( octaves ), lacunarity, diminish ).mul( amplitude )
```
</details>

### `mx_fractal_noise_vec4(position: AttributeNode<vec2>, octaves: number, lacunarity: number, diminish: number, amplitude: number): any`

**Parameters:**

- **`position`** `AttributeNode<vec2>`
- **`octaves`** `number`
- **`lacunarity`** `number`
- **`diminish`** `number`
- **`amplitude`** `number`

**Returns:** `any`

**Calls:**

- `fractal_noise_vec4( position, int( octaves ), lacunarity, diminish ).mul`

<details><summary>Code</summary>

```typescript
( position = uv(), octaves = 3, lacunarity = 2, diminish = .5, amplitude = 1 ) => fractal_noise_vec4( position, int( octaves ), lacunarity, diminish ).mul( amplitude )
```
</details>

### `mx_add(in1: any, in2: any): any`

**Parameters:**

- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `add (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( in1, in2 = float( 0 ) ) => add( in1, in2 )
```
</details>

### `mx_subtract(in1: any, in2: any): any`

**Parameters:**

- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `sub (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( in1, in2 = float( 0 ) ) => sub( in1, in2 )
```
</details>

### `mx_multiply(in1: any, in2: any): any`

**Parameters:**

- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `mul (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( in1, in2 = float( 1 ) ) => mul( in1, in2 )
```
</details>

### `mx_divide(in1: any, in2: any): any`

**Parameters:**

- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `div (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( in1, in2 = float( 1 ) ) => div( in1, in2 )
```
</details>

### `mx_modulo(in1: any, in2: any): any`

**Parameters:**

- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `mod (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( in1, in2 = float( 1 ) ) => mod( in1, in2 )
```
</details>

### `mx_power(in1: any, in2: any): any`

**Parameters:**

- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `pow (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( in1, in2 = float( 1 ) ) => pow( in1, in2 )
```
</details>

### `mx_atan2(in1: any, in2: any): any`

**Parameters:**

- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `atan (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( in1 = float( 0 ), in2 = float( 1 ) ) => atan( in1, in2 )
```
</details>

### `mx_timer(): UniformNode<float>`

**Returns:** `UniformNode<float>`

<details><summary>Code</summary>

```typescript
() => time
```
</details>

### `mx_frame(): UniformNode<uint>`

**Returns:** `UniformNode<uint>`

<details><summary>Code</summary>

```typescript
() => frameId
```
</details>

### `mx_invert(in1: any, amount: any): any`

**Parameters:**

- **`in1`** `any`
- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `sub (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( in1, amount = float( 1 ) ) => sub( amount, in1 )
```
</details>

### `mx_ifgreater(value1: any, value2: any, in1: any, in2: any): any`

**Parameters:**

- **`value1`** `any`
- **`value2`** `any`
- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `value1.greaterThan( value2 ).mix`

<details><summary>Code</summary>

```typescript
( value1, value2, in1, in2 ) => value1.greaterThan( value2 ).mix( in1, in2 )
```
</details>

### `mx_ifgreatereq(value1: any, value2: any, in1: any, in2: any): any`

**Parameters:**

- **`value1`** `any`
- **`value2`** `any`
- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `value1.greaterThanEqual( value2 ).mix`

<details><summary>Code</summary>

```typescript
( value1, value2, in1, in2 ) => value1.greaterThanEqual( value2 ).mix( in1, in2 )
```
</details>

### `mx_ifequal(value1: any, value2: any, in1: any, in2: any): any`

**Parameters:**

- **`value1`** `any`
- **`value2`** `any`
- **`in1`** `any`
- **`in2`** `any`

**Returns:** `any`

**Calls:**

- `value1.equal( value2 ).mix`

<details><summary>Code</summary>

```typescript
( value1, value2, in1, in2 ) => value1.equal( value2 ).mix( in1, in2 )
```
</details>

### `mx_separate(in1: any, channelOrOut: any): any`

**Parameters:**

- **`in1`** `any`
- **`channelOrOut`** `any`

**Returns:** `any`

**Calls:**

- `channelOrOut.replace( /^out/, '' ).toLowerCase`
- `in1.element`

<details><summary>Code</summary>

```typescript
( in1, channelOrOut = null ) => {

	if ( typeof channelOrOut === 'string' ) {

		const map = { x: 0, r: 0, y: 1, g: 1, z: 2, b: 2, w: 3, a: 3 };
		const c = channelOrOut.replace( /^out/, '' ).toLowerCase();
		if ( map[ c ] !== undefined ) return in1.element( map[ c ] );

	}

	if ( typeof channelOrOut === 'number' ) {

		return in1.element( channelOrOut );

	}

	if ( typeof channelOrOut === 'string' && channelOrOut.length === 1 ) {

		const map = { x: 0, r: 0, y: 1, g: 1, z: 2, b: 2, w: 3, a: 3 };
		if ( map[ channelOrOut ] !== undefined ) return in1.element( map[ channelOrOut ] );

	}

	return in1;

}
```
</details>

### `mx_place2d(texcoord: any, pivot: any, scale: any, rotate: any, offset: any): any`

**Parameters:**

- **`texcoord`** `any`
- **`pivot`** `any`
- **`scale`** `any`
- **`rotate`** `any`
- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `uv.sub`
- `uv.mul`
- `rotate.mul`
- `rad.cos`
- `rad.sin`
- `vec2 (from ../tsl/TSLBase.js)`
- `uv.x.mul( cosR ).sub`
- `uv.y.mul`
- `uv.x.mul( sinR ).add`
- `uv.add`

<details><summary>Code</summary>

```typescript
(
	texcoord, pivot = vec2( 0.5, 0.5 ), scale = vec2( 1, 1 ), rotate = float( 0 ), offset = vec2( 0, 0 )/*, operationorder = int( 0 )*/
) => {

	let uv = texcoord;
	if ( pivot ) uv = uv.sub( pivot );
	if ( scale ) uv = uv.mul( scale );
	if ( rotate ) {

		const rad = rotate.mul( Math.PI / 180.0 );
		const cosR = rad.cos();
		const sinR = rad.sin();
		uv = vec2(
			uv.x.mul( cosR ).sub( uv.y.mul( sinR ) ),
			uv.x.mul( sinR ).add( uv.y.mul( cosR ) )
		);

	}

	if ( pivot ) uv = uv.add( pivot );
	if ( offset ) uv = uv.add( offset );
	return uv;

}
```
</details>

### `mx_rotate2d(input: any, amount: any): any`

**Parameters:**

- **`input`** `any`
- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `vec2 (from ../tsl/TSLBase.js)`
- `float (from ../tsl/TSLBase.js)`
- `amount.mul`
- `rotate (from ../utils/RotateNode.js)`

<details><summary>Code</summary>

```typescript
( input, amount ) => {

	input = vec2( input );
	amount = float( amount );

	const radians = amount.mul( Math.PI / 180.0 );
	return rotate( input, radians );

}
```
</details>

### `mx_rotate3d(input: any, amount: any, axis: any): any`

**Parameters:**

- **`input`** `any`
- **`amount`** `any`
- **`axis`** `any`

**Returns:** `any`

**Calls:**

- `vec3 (from ../tsl/TSLBase.js)`
- `float (from ../tsl/TSLBase.js)`
- `amount.mul`
- `axis.normalize`
- `radians.cos`
- `radians.sin`
- `float( 1 ).sub`
- `input.mul( cosA )
			.add( nAxis.cross( input ).mul( sinA ) )
			.add`
- `nAxis.mul( nAxis.dot( input ) ).mul`

<details><summary>Code</summary>

```typescript
( input, amount, axis ) => {

	input = vec3( input );
	amount = float( amount );
	axis = vec3( axis );


	const radians = amount.mul( Math.PI / 180.0 );
	const nAxis = axis.normalize();
	const cosA = radians.cos();
	const sinA = radians.sin();
	const oneMinusCosA = float( 1 ).sub( cosA );
	const rot =
		input.mul( cosA )
			.add( nAxis.cross( input ).mul( sinA ) )
			.add( nAxis.mul( nAxis.dot( input ) ).mul( oneMinusCosA ) );
	return rot;

}
```
</details>

### `mx_heighttonormal(input: any, scale: any): any`

**Parameters:**

- **`input`** `any`
- **`scale`** `any`

**Returns:** `any`

**Calls:**

- `vec3 (from ../tsl/TSLBase.js)`
- `float (from ../tsl/TSLBase.js)`
- `bumpMap (from ../display/BumpMapNode.js)`

<details><summary>Code</summary>

```typescript
( input, scale/*, texcoord*/ ) => {

	input = vec3( input );
	scale = float( scale );

	return bumpMap( input, scale );

}
```
</details>


---