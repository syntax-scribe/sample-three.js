[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `EnvironmentNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 19 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/EnvironmentNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingNode` | `./LightingNode.js` |
| `cache` | `../core/CacheNode.js` |
| `roughness` | `../core/PropertyNode.js` |
| `clearcoatRoughness` | `../core/PropertyNode.js` |
| `cameraViewMatrix` | `../accessors/Camera.js` |
| `normalView` | `../accessors/Normal.js` |
| `clearcoatNormalView` | `../accessors/Normal.js` |
| `normalWorld` | `../accessors/Normal.js` |
| `positionViewDirection` | `../accessors/Position.js` |
| `float` | `../tsl/TSLBase.js` |
| `bentNormalView` | `../accessors/AccessorsUtils.js` |
| `pmremTexture` | `../pmrem/PMREMNode.js` |
| `materialEnvIntensity` | `../accessors/MaterialProperties.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_envNodeCache` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `envNode` | `Node` | let/var | `this.envNode` | ✗ |
| `value` | `any` | let/var | `( envNode.isTextureNode ) ? envNode.value : material[ envNode.property ]` | ✗ |
| `useAnisotropy` | `boolean` | let/var | `material.useAnisotropy === true \|\| material.anisotropy > 0` | ✗ |
| `radianceNormalView` | `any` | let/var | `useAnisotropy ? bentNormalView : normalView` | ✗ |
| `clearcoatRadiance` | `any` | let/var | `builder.context.lightingModel.clearcoatRadiance` | ✗ |
| `reflectVec` | `any` | let/var | `null` | ✗ |


---

## Functions

### `EnvironmentNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `_envNodeCache.get`
- `pmremTexture (from ../pmrem/PMREMNode.js)`
- `_envNodeCache.set`
- `envNode.context( createRadianceContext( roughness, radianceNormalView ) ).mul`
- `envNode.context( createIrradianceContext( normalWorld ) ).mul( Math.PI ).mul`
- `cache (from ../core/CacheNode.js)`
- `builder.context.radiance.addAssign`
- `builder.context.iblIrradiance.addAssign`
- `envNode.context( createRadianceContext( clearcoatRoughness, clearcoatNormalView ) ).mul`
- `clearcoatRadiance.addAssign`

**Internal Comments:**
```
// (x10)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const { material } = builder;

		let envNode = this.envNode;

		if ( envNode.isTextureNode || envNode.isMaterialReferenceNode ) {

			const value = ( envNode.isTextureNode ) ? envNode.value : material[ envNode.property ];

			let cacheEnvNode = _envNodeCache.get( value );

			if ( cacheEnvNode === undefined ) {

				cacheEnvNode = pmremTexture( value );

				_envNodeCache.set( value, cacheEnvNode );

			}

			envNode	= cacheEnvNode;

		}

		//

		const useAnisotropy = material.useAnisotropy === true || material.anisotropy > 0;
		const radianceNormalView = useAnisotropy ? bentNormalView : normalView;

		const radiance = envNode.context( createRadianceContext( roughness, radianceNormalView ) ).mul( materialEnvIntensity );
		const irradiance = envNode.context( createIrradianceContext( normalWorld ) ).mul( Math.PI ).mul( materialEnvIntensity );

		const isolateRadiance = cache( radiance );
		const isolateIrradiance = cache( irradiance );

		//

		builder.context.radiance.addAssign( isolateRadiance );

		builder.context.iblIrradiance.addAssign( isolateIrradiance );

		//

		const clearcoatRadiance = builder.context.lightingModel.clearcoatRadiance;

		if ( clearcoatRadiance ) {

			const clearcoatRadianceContext = envNode.context( createRadianceContext( clearcoatRoughness, clearcoatNormalView ) ).mul( materialEnvIntensity );
			const isolateClearcoatRadiance = cache( clearcoatRadianceContext );

			clearcoatRadiance.addAssign( isolateClearcoatRadiance );

		}

	}
```
</details>

### `createRadianceContext(roughnessNode: any, normalViewNode: any): { getUV: () => any; getTextureLevel: () => any; }`

**Parameters:**

- **`roughnessNode`** `any`
- **`normalViewNode`** `any`

**Returns:** `{ getUV: () => any; getTextureLevel: () => any; }`

**Calls:**

- `positionViewDirection.negate().reflect`
- `roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize`
- `reflectVec.transformDirection`

**Internal Comments:**
```
// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane. (x3)
```

<details><summary>Code</summary>

```typescript
( roughnessNode, normalViewNode ) => {

	let reflectVec = null;

	return {
		getUV: () => {

			if ( reflectVec === null ) {

				reflectVec = positionViewDirection.negate().reflect( normalViewNode );

				// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane.
				reflectVec = roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize();

				reflectVec = reflectVec.transformDirection( cameraViewMatrix );

			}

			return reflectVec;

		},
		getTextureLevel: () => {

			return roughnessNode;

		}
	};

}
```
</details>

### `getUV(): any`

**Returns:** `any`

**Calls:**

- `positionViewDirection.negate().reflect`
- `roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize`
- `reflectVec.transformDirection`

**Internal Comments:**
```
// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane. (x3)
```

<details><summary>Code</summary>

```typescript
() => {

			if ( reflectVec === null ) {

				reflectVec = positionViewDirection.negate().reflect( normalViewNode );

				// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane.
				reflectVec = roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize();

				reflectVec = reflectVec.transformDirection( cameraViewMatrix );

			}

			return reflectVec;

		}
```
</details>

### `getTextureLevel(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => {

			return roughnessNode;

		}
```
</details>

### `getUV(): any`

**Returns:** `any`

**Calls:**

- `positionViewDirection.negate().reflect`
- `roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize`
- `reflectVec.transformDirection`

**Internal Comments:**
```
// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane. (x3)
```

<details><summary>Code</summary>

```typescript
() => {

			if ( reflectVec === null ) {

				reflectVec = positionViewDirection.negate().reflect( normalViewNode );

				// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane.
				reflectVec = roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize();

				reflectVec = reflectVec.transformDirection( cameraViewMatrix );

			}

			return reflectVec;

		}
```
</details>

### `getTextureLevel(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => {

			return roughnessNode;

		}
```
</details>

### `getUV(): any`

**Returns:** `any`

**Calls:**

- `positionViewDirection.negate().reflect`
- `roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize`
- `reflectVec.transformDirection`

**Internal Comments:**
```
// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane. (x3)
```

<details><summary>Code</summary>

```typescript
() => {

			if ( reflectVec === null ) {

				reflectVec = positionViewDirection.negate().reflect( normalViewNode );

				// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane.
				reflectVec = roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize();

				reflectVec = reflectVec.transformDirection( cameraViewMatrix );

			}

			return reflectVec;

		}
```
</details>

### `getTextureLevel(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => {

			return roughnessNode;

		}
```
</details>

### `getUV(): any`

**Returns:** `any`

**Calls:**

- `positionViewDirection.negate().reflect`
- `roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize`
- `reflectVec.transformDirection`

**Internal Comments:**
```
// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane. (x3)
```

<details><summary>Code</summary>

```typescript
() => {

			if ( reflectVec === null ) {

				reflectVec = positionViewDirection.negate().reflect( normalViewNode );

				// Mixing the reflection with the normal is more accurate and keeps rough objects from gathering light from behind their tangent plane.
				reflectVec = roughnessNode.mul( roughnessNode ).mix( reflectVec, normalViewNode ).normalize();

				reflectVec = reflectVec.transformDirection( cameraViewMatrix );

			}

			return reflectVec;

		}
```
</details>

### `getTextureLevel(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => {

			return roughnessNode;

		}
```
</details>

### `createIrradianceContext(normalWorldNode: any): { getUV: () => any; getTextureLevel: () => any; }`

**Parameters:**

- **`normalWorldNode`** `any`

**Returns:** `{ getUV: () => any; getTextureLevel: () => any; }`

**Calls:**

- `float (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( normalWorldNode ) => {

	return {
		getUV: () => {

			return normalWorldNode;

		},
		getTextureLevel: () => {

			return float( 1.0 );

		}
	};

}
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => {

			return normalWorldNode;

		}
```
</details>

### `getTextureLevel(): any`

**Returns:** `any`

**Calls:**

- `float (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
() => {

			return float( 1.0 );

		}
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => {

			return normalWorldNode;

		}
```
</details>

### `getTextureLevel(): any`

**Returns:** `any`

**Calls:**

- `float (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
() => {

			return float( 1.0 );

		}
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => {

			return normalWorldNode;

		}
```
</details>

### `getTextureLevel(): any`

**Returns:** `any`

**Calls:**

- `float (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
() => {

			return float( 1.0 );

		}
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => {

			return normalWorldNode;

		}
```
</details>

### `getTextureLevel(): any`

**Returns:** `any`

**Calls:**

- `float (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
() => {

			return float( 1.0 );

		}
```
</details>


---

## Classes

### `EnvironmentNode`

<details><summary>Class Code</summary>

```ts
class EnvironmentNode extends LightingNode {

	static get type() {

		return 'EnvironmentNode';

	}

	/**
	 * Constructs a new environment node.
	 *
	 * @param {Node} [envNode=null] - A node representing the environment.
	 */
	constructor( envNode = null ) {

		super();

		/**
		 * A node representing the environment.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.envNode = envNode;

	}

	setup( builder ) {

		const { material } = builder;

		let envNode = this.envNode;

		if ( envNode.isTextureNode || envNode.isMaterialReferenceNode ) {

			const value = ( envNode.isTextureNode ) ? envNode.value : material[ envNode.property ];

			let cacheEnvNode = _envNodeCache.get( value );

			if ( cacheEnvNode === undefined ) {

				cacheEnvNode = pmremTexture( value );

				_envNodeCache.set( value, cacheEnvNode );

			}

			envNode	= cacheEnvNode;

		}

		//

		const useAnisotropy = material.useAnisotropy === true || material.anisotropy > 0;
		const radianceNormalView = useAnisotropy ? bentNormalView : normalView;

		const radiance = envNode.context( createRadianceContext( roughness, radianceNormalView ) ).mul( materialEnvIntensity );
		const irradiance = envNode.context( createIrradianceContext( normalWorld ) ).mul( Math.PI ).mul( materialEnvIntensity );

		const isolateRadiance = cache( radiance );
		const isolateIrradiance = cache( irradiance );

		//

		builder.context.radiance.addAssign( isolateRadiance );

		builder.context.iblIrradiance.addAssign( isolateIrradiance );

		//

		const clearcoatRadiance = builder.context.lightingModel.clearcoatRadiance;

		if ( clearcoatRadiance ) {

			const clearcoatRadianceContext = envNode.context( createRadianceContext( clearcoatRoughness, clearcoatNormalView ) ).mul( materialEnvIntensity );
			const isolateClearcoatRadiance = cache( clearcoatRadianceContext );

			clearcoatRadiance.addAssign( isolateClearcoatRadiance );

		}

	}

}
```
</details>

#### Methods

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const { material } = builder;

		let envNode = this.envNode;

		if ( envNode.isTextureNode || envNode.isMaterialReferenceNode ) {

			const value = ( envNode.isTextureNode ) ? envNode.value : material[ envNode.property ];

			let cacheEnvNode = _envNodeCache.get( value );

			if ( cacheEnvNode === undefined ) {

				cacheEnvNode = pmremTexture( value );

				_envNodeCache.set( value, cacheEnvNode );

			}

			envNode	= cacheEnvNode;

		}

		//

		const useAnisotropy = material.useAnisotropy === true || material.anisotropy > 0;
		const radianceNormalView = useAnisotropy ? bentNormalView : normalView;

		const radiance = envNode.context( createRadianceContext( roughness, radianceNormalView ) ).mul( materialEnvIntensity );
		const irradiance = envNode.context( createIrradianceContext( normalWorld ) ).mul( Math.PI ).mul( materialEnvIntensity );

		const isolateRadiance = cache( radiance );
		const isolateIrradiance = cache( irradiance );

		//

		builder.context.radiance.addAssign( isolateRadiance );

		builder.context.iblIrradiance.addAssign( isolateIrradiance );

		//

		const clearcoatRadiance = builder.context.lightingModel.clearcoatRadiance;

		if ( clearcoatRadiance ) {

			const clearcoatRadianceContext = envNode.context( createRadianceContext( clearcoatRoughness, clearcoatNormalView ) ).mul( materialEnvIntensity );
			const isolateClearcoatRadiance = cache( clearcoatRadianceContext );

			clearcoatRadiance.addAssign( isolateClearcoatRadiance );

		}

	}
```
</details>


---