[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DepthLimitedBlurShader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 19 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/shaders/DepthLimitedBlurShader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `DepthLimitedBlurShader` | `ShaderMaterial` | let/var | `{ name: 'DepthLimitedBlurShader', defines: { 'KERNEL_RADIUS': 4, 'DEPTH_PACKI...` | ✗ |
| `weights` | `any[]` | let/var | `[]` | ✗ |
| `offsets` | `any[]` | let/var | `[]` | ✗ |
| `BlurShaderUtils` | `{ createSampleWeights: (kernelRadius:...` | let/var | `{ createSampleWeights: function ( kernelRadius, stdDev ) { const weights = []...` | ✗ |


---

## Functions

### `createSampleWeights(kernelRadius: any, stdDev: any): number[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`stdDev`** `any`

**Returns:** `number[]`

**Calls:**

- `weights.push`
- `gaussian`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, stdDev ) {

		const weights = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			weights.push( gaussian( i, stdDev ) );

		}

		return weights;

	}
```
</details>

### `createSampleOffsets(kernelRadius: any, uvIncrement: any): any[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`uvIncrement`** `any`

**Returns:** `any[]`

**Calls:**

- `offsets.push`
- `uvIncrement.clone().multiplyScalar`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, uvIncrement ) {

		const offsets = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			offsets.push( uvIncrement.clone().multiplyScalar( i ) );

		}

		return offsets;

	}
```
</details>

### `configure(material: any, kernelRadius: any, stdDev: any, uvIncrement: any): void`

**Parameters:**

- **`material`** `any`
- **`kernelRadius`** `any`
- **`stdDev`** `any`
- **`uvIncrement`** `any`

**Returns:** `void`

**Calls:**

- `BlurShaderUtils.createSampleOffsets`
- `BlurShaderUtils.createSampleWeights`

<details><summary>Code</summary>

```typescript
function ( material, kernelRadius, stdDev, uvIncrement ) {

		material.defines[ 'KERNEL_RADIUS' ] = kernelRadius;
		material.uniforms[ 'sampleUvOffsets' ].value = BlurShaderUtils.createSampleOffsets( kernelRadius, uvIncrement );
		material.uniforms[ 'sampleWeights' ].value = BlurShaderUtils.createSampleWeights( kernelRadius, stdDev );
		material.needsUpdate = true;

	}
```
</details>

### `createSampleWeights(kernelRadius: any, stdDev: any): number[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`stdDev`** `any`

**Returns:** `number[]`

**Calls:**

- `weights.push`
- `gaussian`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, stdDev ) {

		const weights = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			weights.push( gaussian( i, stdDev ) );

		}

		return weights;

	}
```
</details>

### `createSampleOffsets(kernelRadius: any, uvIncrement: any): any[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`uvIncrement`** `any`

**Returns:** `any[]`

**Calls:**

- `offsets.push`
- `uvIncrement.clone().multiplyScalar`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, uvIncrement ) {

		const offsets = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			offsets.push( uvIncrement.clone().multiplyScalar( i ) );

		}

		return offsets;

	}
```
</details>

### `configure(material: any, kernelRadius: any, stdDev: any, uvIncrement: any): void`

**Parameters:**

- **`material`** `any`
- **`kernelRadius`** `any`
- **`stdDev`** `any`
- **`uvIncrement`** `any`

**Returns:** `void`

**Calls:**

- `BlurShaderUtils.createSampleOffsets`
- `BlurShaderUtils.createSampleWeights`

<details><summary>Code</summary>

```typescript
function ( material, kernelRadius, stdDev, uvIncrement ) {

		material.defines[ 'KERNEL_RADIUS' ] = kernelRadius;
		material.uniforms[ 'sampleUvOffsets' ].value = BlurShaderUtils.createSampleOffsets( kernelRadius, uvIncrement );
		material.uniforms[ 'sampleWeights' ].value = BlurShaderUtils.createSampleWeights( kernelRadius, stdDev );
		material.needsUpdate = true;

	}
```
</details>

### `createSampleWeights(kernelRadius: any, stdDev: any): number[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`stdDev`** `any`

**Returns:** `number[]`

**Calls:**

- `weights.push`
- `gaussian`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, stdDev ) {

		const weights = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			weights.push( gaussian( i, stdDev ) );

		}

		return weights;

	}
```
</details>

### `createSampleOffsets(kernelRadius: any, uvIncrement: any): any[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`uvIncrement`** `any`

**Returns:** `any[]`

**Calls:**

- `offsets.push`
- `uvIncrement.clone().multiplyScalar`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, uvIncrement ) {

		const offsets = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			offsets.push( uvIncrement.clone().multiplyScalar( i ) );

		}

		return offsets;

	}
```
</details>

### `configure(material: any, kernelRadius: any, stdDev: any, uvIncrement: any): void`

**Parameters:**

- **`material`** `any`
- **`kernelRadius`** `any`
- **`stdDev`** `any`
- **`uvIncrement`** `any`

**Returns:** `void`

**Calls:**

- `BlurShaderUtils.createSampleOffsets`
- `BlurShaderUtils.createSampleWeights`

<details><summary>Code</summary>

```typescript
function ( material, kernelRadius, stdDev, uvIncrement ) {

		material.defines[ 'KERNEL_RADIUS' ] = kernelRadius;
		material.uniforms[ 'sampleUvOffsets' ].value = BlurShaderUtils.createSampleOffsets( kernelRadius, uvIncrement );
		material.uniforms[ 'sampleWeights' ].value = BlurShaderUtils.createSampleWeights( kernelRadius, stdDev );
		material.needsUpdate = true;

	}
```
</details>

### `createSampleWeights(kernelRadius: any, stdDev: any): number[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`stdDev`** `any`

**Returns:** `number[]`

**Calls:**

- `weights.push`
- `gaussian`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, stdDev ) {

		const weights = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			weights.push( gaussian( i, stdDev ) );

		}

		return weights;

	}
```
</details>

### `createSampleOffsets(kernelRadius: any, uvIncrement: any): any[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`uvIncrement`** `any`

**Returns:** `any[]`

**Calls:**

- `offsets.push`
- `uvIncrement.clone().multiplyScalar`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, uvIncrement ) {

		const offsets = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			offsets.push( uvIncrement.clone().multiplyScalar( i ) );

		}

		return offsets;

	}
```
</details>

### `configure(material: any, kernelRadius: any, stdDev: any, uvIncrement: any): void`

**Parameters:**

- **`material`** `any`
- **`kernelRadius`** `any`
- **`stdDev`** `any`
- **`uvIncrement`** `any`

**Returns:** `void`

**Calls:**

- `BlurShaderUtils.createSampleOffsets`
- `BlurShaderUtils.createSampleWeights`

<details><summary>Code</summary>

```typescript
function ( material, kernelRadius, stdDev, uvIncrement ) {

		material.defines[ 'KERNEL_RADIUS' ] = kernelRadius;
		material.uniforms[ 'sampleUvOffsets' ].value = BlurShaderUtils.createSampleOffsets( kernelRadius, uvIncrement );
		material.uniforms[ 'sampleWeights' ].value = BlurShaderUtils.createSampleWeights( kernelRadius, stdDev );
		material.needsUpdate = true;

	}
```
</details>

### `createSampleWeights(kernelRadius: any, stdDev: any): number[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`stdDev`** `any`

**Returns:** `number[]`

**Calls:**

- `weights.push`
- `gaussian`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, stdDev ) {

		const weights = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			weights.push( gaussian( i, stdDev ) );

		}

		return weights;

	}
```
</details>

### `createSampleOffsets(kernelRadius: any, uvIncrement: any): any[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`uvIncrement`** `any`

**Returns:** `any[]`

**Calls:**

- `offsets.push`
- `uvIncrement.clone().multiplyScalar`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, uvIncrement ) {

		const offsets = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			offsets.push( uvIncrement.clone().multiplyScalar( i ) );

		}

		return offsets;

	}
```
</details>

### `configure(material: any, kernelRadius: any, stdDev: any, uvIncrement: any): void`

**Parameters:**

- **`material`** `any`
- **`kernelRadius`** `any`
- **`stdDev`** `any`
- **`uvIncrement`** `any`

**Returns:** `void`

**Calls:**

- `BlurShaderUtils.createSampleOffsets`
- `BlurShaderUtils.createSampleWeights`

<details><summary>Code</summary>

```typescript
function ( material, kernelRadius, stdDev, uvIncrement ) {

		material.defines[ 'KERNEL_RADIUS' ] = kernelRadius;
		material.uniforms[ 'sampleUvOffsets' ].value = BlurShaderUtils.createSampleOffsets( kernelRadius, uvIncrement );
		material.uniforms[ 'sampleWeights' ].value = BlurShaderUtils.createSampleWeights( kernelRadius, stdDev );
		material.needsUpdate = true;

	}
```
</details>

### `createSampleWeights(kernelRadius: any, stdDev: any): number[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`stdDev`** `any`

**Returns:** `number[]`

**Calls:**

- `weights.push`
- `gaussian`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, stdDev ) {

		const weights = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			weights.push( gaussian( i, stdDev ) );

		}

		return weights;

	}
```
</details>

### `createSampleOffsets(kernelRadius: any, uvIncrement: any): any[]`

**Parameters:**

- **`kernelRadius`** `any`
- **`uvIncrement`** `any`

**Returns:** `any[]`

**Calls:**

- `offsets.push`
- `uvIncrement.clone().multiplyScalar`

<details><summary>Code</summary>

```typescript
function ( kernelRadius, uvIncrement ) {

		const offsets = [];

		for ( let i = 0; i <= kernelRadius; i ++ ) {

			offsets.push( uvIncrement.clone().multiplyScalar( i ) );

		}

		return offsets;

	}
```
</details>

### `configure(material: any, kernelRadius: any, stdDev: any, uvIncrement: any): void`

**Parameters:**

- **`material`** `any`
- **`kernelRadius`** `any`
- **`stdDev`** `any`
- **`uvIncrement`** `any`

**Returns:** `void`

**Calls:**

- `BlurShaderUtils.createSampleOffsets`
- `BlurShaderUtils.createSampleWeights`

<details><summary>Code</summary>

```typescript
function ( material, kernelRadius, stdDev, uvIncrement ) {

		material.defines[ 'KERNEL_RADIUS' ] = kernelRadius;
		material.uniforms[ 'sampleUvOffsets' ].value = BlurShaderUtils.createSampleOffsets( kernelRadius, uvIncrement );
		material.uniforms[ 'sampleWeights' ].value = BlurShaderUtils.createSampleWeights( kernelRadius, stdDev );
		material.needsUpdate = true;

	}
```
</details>

### `gaussian(x: any, stdDev: any): number`

**Parameters:**

- **`x`** `any`
- **`stdDev`** `any`

**Returns:** `number`

**Calls:**

- `Math.exp`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function gaussian( x, stdDev ) {

	return Math.exp( - ( x * x ) / ( 2.0 * ( stdDev * stdDev ) ) ) / ( Math.sqrt( 2.0 * Math.PI ) * stdDev );

}
```
</details>


---