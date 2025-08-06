[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BasicLightingModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/functions/BasicLightingModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingModel` | `../core/LightingModel.js` |
| `diffuseColor` | `../core/PropertyNode.js` |
| `MultiplyOperation` | `../../constants.js` |
| `MixOperation` | `../../constants.js` |
| `AddOperation` | `../../constants.js` |
| `materialSpecularStrength` | `../accessors/MaterialNode.js` |
| `materialReflectivity` | `../accessors/MaterialNode.js` |
| `mix` | `../math/MathNode.js` |
| `vec4` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `ambientOcclusion` | `any` | let/var | `context.ambientOcclusion` | ✗ |
| `reflectedLight` | `any` | let/var | `context.reflectedLight` | ✗ |
| `irradianceLightMap` | `any` | let/var | `context.irradianceLightMap` | ✗ |
| `outgoingLight` | `any` | let/var | `context.outgoingLight` | ✗ |
| `envNode` | `any` | let/var | `builder.context.environment` | ✗ |


---

## Functions

### `BasicLightingModel.indirect({ context }: any): void`

**JSDoc:**
```typescript
/**
	 * Implements the baked indirect lighting with its modulation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`{ context }`** `any`

**Returns:** `void`

**Calls:**

- `reflectedLight.indirectDiffuse.assign`
- `vec4 (from ../tsl/TSLBase.js)`
- `reflectedLight.indirectDiffuse.addAssign`
- `reflectedLight.indirectDiffuse.mulAssign`

**Internal Comments:**
```
// accumulation (baked indirect lighting only)
// modulation (x5)
```

<details><summary>Code</summary>

```typescript
indirect( { context } ) {

		const ambientOcclusion = context.ambientOcclusion;
		const reflectedLight = context.reflectedLight;
		const irradianceLightMap = context.irradianceLightMap;

		reflectedLight.indirectDiffuse.assign( vec4( 0.0 ) );

		// accumulation (baked indirect lighting only)

		if ( irradianceLightMap ) {

			reflectedLight.indirectDiffuse.addAssign( irradianceLightMap );

		} else {

			reflectedLight.indirectDiffuse.addAssign( vec4( 1.0, 1.0, 1.0, 0.0 ) );

		}

		// modulation

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );

		reflectedLight.indirectDiffuse.mulAssign( diffuseColor.rgb );

	}
```
</details>

### `BasicLightingModel.finish(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Implements the environment mapping.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `outgoingLight.rgb.assign`
- `mix (from ../math/MathNode.js)`
- `outgoingLight.rgb.mul`
- `materialSpecularStrength.mul`
- `outgoingLight.rgb.addAssign`
- `envNode.rgb.mul`
- `console.warn`

<details><summary>Code</summary>

```typescript
finish( builder ) {

		const { material, context } = builder;

		const outgoingLight = context.outgoingLight;
		const envNode = builder.context.environment;

		if ( envNode ) {

			switch ( material.combine ) {

				case MultiplyOperation:
					outgoingLight.rgb.assign( mix( outgoingLight.rgb, outgoingLight.rgb.mul( envNode.rgb ), materialSpecularStrength.mul( materialReflectivity ) ) );
					break;

				case MixOperation:
					outgoingLight.rgb.assign( mix( outgoingLight.rgb, envNode.rgb, materialSpecularStrength.mul( materialReflectivity ) ) );
					break;

				case AddOperation:
					outgoingLight.rgb.addAssign( envNode.rgb.mul( materialSpecularStrength.mul( materialReflectivity ) ) );
					break;

				default:
					console.warn( 'THREE.BasicLightingModel: Unsupported .combine value:', material.combine );
					break;

			}

		}

	}
```
</details>


---

## Classes

### `BasicLightingModel`

<details><summary>Class Code</summary>

```ts
class BasicLightingModel extends LightingModel {

	/**
	 * Constructs a new basic lighting model.
	 */
	constructor() {

		super();

	}

	/**
	 * Implements the baked indirect lighting with its modulation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	indirect( { context } ) {

		const ambientOcclusion = context.ambientOcclusion;
		const reflectedLight = context.reflectedLight;
		const irradianceLightMap = context.irradianceLightMap;

		reflectedLight.indirectDiffuse.assign( vec4( 0.0 ) );

		// accumulation (baked indirect lighting only)

		if ( irradianceLightMap ) {

			reflectedLight.indirectDiffuse.addAssign( irradianceLightMap );

		} else {

			reflectedLight.indirectDiffuse.addAssign( vec4( 1.0, 1.0, 1.0, 0.0 ) );

		}

		// modulation

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );

		reflectedLight.indirectDiffuse.mulAssign( diffuseColor.rgb );

	}

	/**
	 * Implements the environment mapping.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	finish( builder ) {

		const { material, context } = builder;

		const outgoingLight = context.outgoingLight;
		const envNode = builder.context.environment;

		if ( envNode ) {

			switch ( material.combine ) {

				case MultiplyOperation:
					outgoingLight.rgb.assign( mix( outgoingLight.rgb, outgoingLight.rgb.mul( envNode.rgb ), materialSpecularStrength.mul( materialReflectivity ) ) );
					break;

				case MixOperation:
					outgoingLight.rgb.assign( mix( outgoingLight.rgb, envNode.rgb, materialSpecularStrength.mul( materialReflectivity ) ) );
					break;

				case AddOperation:
					outgoingLight.rgb.addAssign( envNode.rgb.mul( materialSpecularStrength.mul( materialReflectivity ) ) );
					break;

				default:
					console.warn( 'THREE.BasicLightingModel: Unsupported .combine value:', material.combine );
					break;

			}

		}

	}

}
```
</details>

#### Methods

##### `indirect({ context }: any): void`

<details><summary>Code</summary>

```ts
indirect( { context } ) {

		const ambientOcclusion = context.ambientOcclusion;
		const reflectedLight = context.reflectedLight;
		const irradianceLightMap = context.irradianceLightMap;

		reflectedLight.indirectDiffuse.assign( vec4( 0.0 ) );

		// accumulation (baked indirect lighting only)

		if ( irradianceLightMap ) {

			reflectedLight.indirectDiffuse.addAssign( irradianceLightMap );

		} else {

			reflectedLight.indirectDiffuse.addAssign( vec4( 1.0, 1.0, 1.0, 0.0 ) );

		}

		// modulation

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );

		reflectedLight.indirectDiffuse.mulAssign( diffuseColor.rgb );

	}
```
</details>

##### `finish(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
finish( builder ) {

		const { material, context } = builder;

		const outgoingLight = context.outgoingLight;
		const envNode = builder.context.environment;

		if ( envNode ) {

			switch ( material.combine ) {

				case MultiplyOperation:
					outgoingLight.rgb.assign( mix( outgoingLight.rgb, outgoingLight.rgb.mul( envNode.rgb ), materialSpecularStrength.mul( materialReflectivity ) ) );
					break;

				case MixOperation:
					outgoingLight.rgb.assign( mix( outgoingLight.rgb, envNode.rgb, materialSpecularStrength.mul( materialReflectivity ) ) );
					break;

				case AddOperation:
					outgoingLight.rgb.addAssign( envNode.rgb.mul( materialSpecularStrength.mul( materialReflectivity ) ) );
					break;

				default:
					console.warn( 'THREE.BasicLightingModel: Unsupported .combine value:', material.combine );
					break;

			}

		}

	}
```
</details>


---