[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TextureBicubic.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/accessors/TextureBicubic.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `add` | `../math/OperatorNode.js` |
| `mul` | `../math/OperatorNode.js` |
| `div` | `../math/OperatorNode.js` |
| `floor` | `../math/MathNode.js` |
| `ceil` | `../math/MathNode.js` |
| `fract` | `../math/MathNode.js` |
| `pow` | `../math/MathNode.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |
| `int` | `../tsl/TSLBase.js` |
| `maxMipLevel` | `../utils/MaxMipLevelNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `bC` | `number` | let/var | `1.0 / 6.0` | ✗ |
| `uv` | `any` | let/var | `textureNode.uvNode` | ✗ |


---

## Functions

### `w0(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `mul (from ../math/OperatorNode.js)`

<details><summary>Code</summary>

```typescript
( a ) => mul( bC, mul( a, mul( a, a.negate().add( 3.0 ) ).sub( 3.0 ) ).add( 1.0 ) )
```
</details>

### `w1(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `mul (from ../math/OperatorNode.js)`

<details><summary>Code</summary>

```typescript
( a ) => mul( bC, mul( a, mul( a, mul( 3.0, a ).sub( 6.0 ) ) ).add( 4.0 ) )
```
</details>

### `w2(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `mul (from ../math/OperatorNode.js)`

<details><summary>Code</summary>

```typescript
( a ) => mul( bC, mul( a, mul( a, mul( - 3.0, a ).add( 3.0 ) ).add( 3.0 ) ).add( 1.0 ) )
```
</details>

### `w3(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `mul (from ../math/OperatorNode.js)`

<details><summary>Code</summary>

```typescript
( a ) => mul( bC, pow( a, 3 ) )
```
</details>

### `g0(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `w0( a ).add`

<details><summary>Code</summary>

```typescript
( a ) => w0( a ).add( w1( a ) )
```
</details>

### `g1(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `w2( a ).add`

<details><summary>Code</summary>

```typescript
( a ) => w2( a ).add( w3( a ) )
```
</details>

### `h0(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `add (from ../math/OperatorNode.js)`

<details><summary>Code</summary>

```typescript
( a ) => add( - 1.0, w1( a ).div( w0( a ).add( w1( a ) ) ) )
```
</details>

### `h1(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `add (from ../math/OperatorNode.js)`

<details><summary>Code</summary>

```typescript
( a ) => add( 1.0, w3( a ).div( w2( a ).add( w3( a ) ) ) )
```
</details>

### `bicubic(textureNode: any, texelSize: any, lod: any): any`

**Parameters:**

- **`textureNode`** `any`
- **`texelSize`** `any`
- **`lod`** `any`

**Returns:** `any`

**Calls:**

- `mul( uv, texelSize.zw ).add`
- `floor (from ../math/MathNode.js)`
- `fract (from ../math/MathNode.js)`
- `g0`
- `g1`
- `h0`
- `h1`
- `vec2( iuv.x.add( h0x ), iuv.y.add( h0y ) ).sub( 0.5 ).mul`
- `vec2( iuv.x.add( h1x ), iuv.y.add( h0y ) ).sub( 0.5 ).mul`
- `vec2( iuv.x.add( h0x ), iuv.y.add( h1y ) ).sub( 0.5 ).mul`
- `vec2( iuv.x.add( h1x ), iuv.y.add( h1y ) ).sub( 0.5 ).mul`
- `g0( fuv.y ).mul`
- `add (from ../math/OperatorNode.js)`
- `g0x.mul`
- `textureNode.sample( p0 ).level`
- `g1x.mul`
- `textureNode.sample( p1 ).level`
- `g1( fuv.y ).mul`
- `textureNode.sample( p2 ).level`
- `textureNode.sample( p3 ).level`
- `a.add`

<details><summary>Code</summary>

```typescript
( textureNode, texelSize, lod ) => {

	const uv = textureNode.uvNode;
	const uvScaled = mul( uv, texelSize.zw ).add( 0.5 );

	const iuv = floor( uvScaled );
	const fuv = fract( uvScaled );

	const g0x = g0( fuv.x );
	const g1x = g1( fuv.x );
	const h0x = h0( fuv.x );
	const h1x = h1( fuv.x );
	const h0y = h0( fuv.y );
	const h1y = h1( fuv.y );

	const p0 = vec2( iuv.x.add( h0x ), iuv.y.add( h0y ) ).sub( 0.5 ).mul( texelSize.xy );
	const p1 = vec2( iuv.x.add( h1x ), iuv.y.add( h0y ) ).sub( 0.5 ).mul( texelSize.xy );
	const p2 = vec2( iuv.x.add( h0x ), iuv.y.add( h1y ) ).sub( 0.5 ).mul( texelSize.xy );
	const p3 = vec2( iuv.x.add( h1x ), iuv.y.add( h1y ) ).sub( 0.5 ).mul( texelSize.xy );

	const a = g0( fuv.y ).mul( add( g0x.mul( textureNode.sample( p0 ).level( lod ) ), g1x.mul( textureNode.sample( p1 ).level( lod ) ) ) );
	const b = g1( fuv.y ).mul( add( g0x.mul( textureNode.sample( p2 ).level( lod ) ), g1x.mul( textureNode.sample( p3 ).level( lod ) ) ) );

	return a.add( b );

}
```
</details>


---