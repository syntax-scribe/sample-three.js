[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `GTAOShader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/shaders/GTAOShader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataTexture` | `three` |
| `Matrix4` | `three` |
| `RepeatWrapping` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `GTAOShader` | `ShaderMaterial` | let/var | `{ name: 'GTAOShader', defines: { PERSPECTIVE_CAMERA: 1, SAMPLES: 16, NORMAL_V...` | ✗ |
| `GTAODepthShader` | `any` | let/var | `{ name: 'GTAODepthShader', defines: { PERSPECTIVE_CAMERA: 1 }, uniforms: { tD...` | ✗ |
| `GTAOBlendShader` | `any` | let/var | `{ name: 'GTAOBlendShader', uniforms: { tDiffuse: { value: null }, intensity: ...` | ✗ |
| `noiseSize` | `number` | let/var | `Math.floor( size ) % 2 === 0 ? Math.floor( size ) + 1 : Math.floor( size )` | ✗ |
| `noiseSquareSize` | `number` | let/var | `magicSquare.length` | ✗ |
| `data` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( noiseSquareSize * 4 )` | ✗ |
| `iAng` | `any` | let/var | `magicSquare[ inx ]` | ✗ |
| `angle` | `number` | let/var | `( 2 * Math.PI * iAng ) / noiseSquareSize` | ✗ |
| `noiseTexture` | `any` | let/var | `new DataTexture( data, noiseSize, noiseSize )` | ✗ |
| `noiseSize` | `number` | let/var | `Math.floor( size ) % 2 === 0 ? Math.floor( size ) + 1 : Math.floor( size )` | ✗ |
| `noiseSquareSize` | `number` | let/var | `noiseSize * noiseSize` | ✗ |
| `j` | `number` | let/var | `noiseSize - 1` | ✗ |


---

## Functions

### `generateMagicSquareNoise(size: number): any`

**Parameters:**

- **`size`** `number`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `generateMagicSquare`
- `new Vector3(
			Math.cos( angle ),
			Math.sin( angle ),
			0
		).normalize`
- `Math.cos`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function generateMagicSquareNoise( size = 5 ) {

	const noiseSize = Math.floor( size ) % 2 === 0 ? Math.floor( size ) + 1 : Math.floor( size );
	const magicSquare = generateMagicSquare( noiseSize );
	const noiseSquareSize = magicSquare.length;
	const data = new Uint8Array( noiseSquareSize * 4 );

	for ( let inx = 0; inx < noiseSquareSize; ++ inx ) {

		const iAng = magicSquare[ inx ];
		const angle = ( 2 * Math.PI * iAng ) / noiseSquareSize;
		const randomVec = new Vector3(
			Math.cos( angle ),
			Math.sin( angle ),
			0
		).normalize();
		data[ inx * 4 ] = ( randomVec.x * 0.5 + 0.5 ) * 255;
		data[ inx * 4 + 1 ] = ( randomVec.y * 0.5 + 0.5 ) * 255;
		data[ inx * 4 + 2 ] = 127;
		data[ inx * 4 + 3 ] = 255;

	}

	const noiseTexture = new DataTexture( data, noiseSize, noiseSize );
	noiseTexture.wrapS = RepeatWrapping;
	noiseTexture.wrapT = RepeatWrapping;
	noiseTexture.needsUpdate = true;

	return noiseTexture;

}
```
</details>

### `generateMagicSquare(size: any): any[]`

**Parameters:**

- **`size`** `any`

**Returns:** `any[]`

**Calls:**

- `Math.floor`
- `Array( noiseSquareSize ).fill`

<details><summary>Code</summary>

```typescript
function generateMagicSquare( size ) {

	const noiseSize = Math.floor( size ) % 2 === 0 ? Math.floor( size ) + 1 : Math.floor( size );
	const noiseSquareSize = noiseSize * noiseSize;
	const magicSquare = Array( noiseSquareSize ).fill( 0 );
	let i = Math.floor( noiseSize / 2 );
	let j = noiseSize - 1;

	for ( let num = 1; num <= noiseSquareSize; ) {

		if ( i === - 1 && j === noiseSize ) {

			j = noiseSize - 2;
			i = 0;

		} else {

			if ( j === noiseSize ) {

				j = 0;

			}

			if ( i < 0 ) {

				i = noiseSize - 1;

			}

		}

		if ( magicSquare[ i * noiseSize + j ] !== 0 ) {

			j -= 2;
			i ++;
			continue;

		} else {

			magicSquare[ i * noiseSize + j ] = num ++;

		}

		j ++;
		i --;

	}

	return magicSquare;

}
```
</details>


---