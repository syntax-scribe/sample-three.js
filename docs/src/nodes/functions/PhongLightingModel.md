[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PhongLightingModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/functions/PhongLightingModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BasicLightingModel` | `./BasicLightingModel.js` |
| `F_Schlick` | `./BSDF/F_Schlick.js` |
| `BRDF_Lambert` | `./BSDF/BRDF_Lambert.js` |
| `diffuseColor` | `../core/PropertyNode.js` |
| `shininess` | `../core/PropertyNode.js` |
| `specularColor` | `../core/PropertyNode.js` |
| `normalView` | `../accessors/Normal.js` |
| `materialSpecularStrength` | `../accessors/MaterialNode.js` |
| `positionViewDirection` | `../accessors/Position.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |


---

## Functions

### `G_BlinnPhong_Implicit(): any`

**Returns:** `any`

**Calls:**

- `float (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
() => float( 0.25 )
```
</details>

### `PhongLightingModel.direct({ lightDirection, lightColor, reflectedLight }: any): void`

**JSDoc:**
```typescript
/**
	 * Implements the direct lighting. The specular portion is optional an can be controlled
	 * with the {@link PhongLightingModel#specular} flag.
	 *
	 * @param {Object} lightData - The light data.
	 */
```

**Parameters:**

- **`{ lightDirection, lightColor, reflectedLight }`** `any`

**Returns:** `void`

**Calls:**

- `normalView.dot( lightDirection ).clamp`
- `dotNL.mul`
- `reflectedLight.directDiffuse.addAssign`
- `irradiance.mul`
- `BRDF_Lambert (from ./BSDF/BRDF_Lambert.js)`
- `reflectedLight.directSpecular.addAssign`
- `irradiance.mul( BRDF_BlinnPhong( { lightDirection } ) ).mul`

<details><summary>Code</summary>

```typescript
direct( { lightDirection, lightColor, reflectedLight } ) {

		const dotNL = normalView.dot( lightDirection ).clamp();
		const irradiance = dotNL.mul( lightColor );

		reflectedLight.directDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor: diffuseColor.rgb } ) ) );

		if ( this.specular === true ) {

			reflectedLight.directSpecular.addAssign( irradiance.mul( BRDF_BlinnPhong( { lightDirection } ) ).mul( materialSpecularStrength ) );

		}

	}
```
</details>

### `PhongLightingModel.indirect(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Implements the indirect lighting.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `reflectedLight.indirectDiffuse.addAssign`
- `irradiance.mul`
- `BRDF_Lambert (from ./BSDF/BRDF_Lambert.js)`
- `reflectedLight.indirectDiffuse.mulAssign`

<details><summary>Code</summary>

```typescript
indirect( builder ) {

		const { ambientOcclusion, irradiance, reflectedLight } = builder.context;

		reflectedLight.indirectDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor } ) ) );

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );

	}
```
</details>


---

## Classes

### `PhongLightingModel`

<details><summary>Class Code</summary>

```ts
class PhongLightingModel extends BasicLightingModel {

	/**
	 * Constructs a new phong lighting model.
	 *
	 * @param {boolean} [specular=true] - Whether specular is supported or not.
	 */
	constructor( specular = true ) {

		super();

		/**
		 * Whether specular is supported or not. Set this to `false` if you are
		 * looking for a Lambert-like material meaning a material for non-shiny
		 * surfaces, without specular highlights.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.specular = specular;

	}

	/**
	 * Implements the direct lighting. The specular portion is optional an can be controlled
	 * with the {@link PhongLightingModel#specular} flag.
	 *
	 * @param {Object} lightData - The light data.
	 */
	direct( { lightDirection, lightColor, reflectedLight } ) {

		const dotNL = normalView.dot( lightDirection ).clamp();
		const irradiance = dotNL.mul( lightColor );

		reflectedLight.directDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor: diffuseColor.rgb } ) ) );

		if ( this.specular === true ) {

			reflectedLight.directSpecular.addAssign( irradiance.mul( BRDF_BlinnPhong( { lightDirection } ) ).mul( materialSpecularStrength ) );

		}

	}

	/**
	 * Implements the indirect lighting.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	indirect( builder ) {

		const { ambientOcclusion, irradiance, reflectedLight } = builder.context;

		reflectedLight.indirectDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor } ) ) );

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );

	}

}
```
</details>

#### Methods

##### `direct({ lightDirection, lightColor, reflectedLight }: any): void`

<details><summary>Code</summary>

```ts
direct( { lightDirection, lightColor, reflectedLight } ) {

		const dotNL = normalView.dot( lightDirection ).clamp();
		const irradiance = dotNL.mul( lightColor );

		reflectedLight.directDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor: diffuseColor.rgb } ) ) );

		if ( this.specular === true ) {

			reflectedLight.directSpecular.addAssign( irradiance.mul( BRDF_BlinnPhong( { lightDirection } ) ).mul( materialSpecularStrength ) );

		}

	}
```
</details>

##### `indirect(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
indirect( builder ) {

		const { ambientOcclusion, irradiance, reflectedLight } = builder.context;

		reflectedLight.indirectDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor } ) ) );

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );

	}
```
</details>


---