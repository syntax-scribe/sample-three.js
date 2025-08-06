[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PoissonDenoiseShader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/shaders/PoissonDenoiseShader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix4` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `PoissonDenoiseShader` | `ShaderMaterial` | let/var | `{ name: 'PoissonDenoiseShader', defines: { 'SAMPLES': 16, 'SAMPLE_VECTORS': g...` | ✗ |
| `glslCode` | `string` | let/var | `'vec3[SAMPLES]('` | ✗ |
| `sample` | `any` | let/var | `poissonDisk[ i ]` | ✗ |
| `samples` | `any[]` | let/var | `[]` | ✗ |
| `angle` | `number` | let/var | `2 * Math.PI * numRings * i / numSamples` | ✗ |


---

## Functions

### `generatePdSamplePointInitializer(samples: any, rings: any, radiusExponent: any): string`

**Parameters:**

- **`samples`** `any`
- **`rings`** `any`
- **`radiusExponent`** `any`

**Returns:** `string`

**Calls:**

- `generateDenoiseSamples`

<details><summary>Code</summary>

```typescript
function generatePdSamplePointInitializer( samples, rings, radiusExponent ) {

	const poissonDisk = generateDenoiseSamples(
		samples,
		rings,
		radiusExponent,
	);

	let glslCode = 'vec3[SAMPLES](';

	for ( let i = 0; i < samples; i ++ ) {

		const sample = poissonDisk[ i ];
		glslCode += `vec3(${sample.x}, ${sample.y}, ${sample.z})${( i < samples - 1 ) ? ',' : ')'}`;

	}

	return glslCode;

}
```
</details>

### `generateDenoiseSamples(numSamples: any, numRings: any, radiusExponent: any): any[]`

**Parameters:**

- **`numSamples`** `any`
- **`numRings`** `any`
- **`radiusExponent`** `any`

**Returns:** `any[]`

**Calls:**

- `Math.pow`
- `samples.push`
- `Math.cos`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function generateDenoiseSamples( numSamples, numRings, radiusExponent ) {

	const samples = [];

	for ( let i = 0; i < numSamples; i ++ ) {

		const angle = 2 * Math.PI * numRings * i / numSamples;
		const radius = Math.pow( i / ( numSamples - 1 ), radiusExponent );
		samples.push( new Vector3( Math.cos( angle ), Math.sin( angle ), radius ) );

	}

	return samples;

}
```
</details>


---