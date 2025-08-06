[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshGouraudMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/materials/MeshGouraudMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UniformsUtils` | `three` |
| `UniformsLib` | `three` |
| `ShaderMaterial` | `three` |
| `Color` | `three` |
| `MultiplyOperation` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `GouraudShader` | `{ name: string; uniforms: any; vertex...` | let/var | `{ name: 'GouraudShader', uniforms: UniformsUtils.merge( [ UniformsLib.common,...` | ✗ |
| `shader` | `{ name: string; uniforms: any; vertex...` | let/var | `GouraudShader` | ✗ |
| `exposePropertyNames` | `string[]` | let/var | `[ 'map', 'lightMap', 'lightMapIntensity', 'aoMap', 'aoMapIntensity', 'emissiv...` | ✗ |


---

## Functions

### `MeshGouraudMaterial.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.color.copy`
- `this.emissive.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.color.copy( source.color );

		this.map = source.map;

		this.lightMap = source.lightMap;
		this.lightMapIntensity = source.lightMapIntensity;

		this.aoMap = source.aoMap;
		this.aoMapIntensity = source.aoMapIntensity;

		this.emissive.copy( source.emissive );
		this.emissiveMap = source.emissiveMap;
		this.emissiveIntensity = source.emissiveIntensity;

		this.specularMap = source.specularMap;

		this.alphaMap = source.alphaMap;

		this.envMap = source.envMap;
		this.combine = source.combine;
		this.reflectivity = source.reflectivity;
		this.refractionRatio = source.refractionRatio;

		this.wireframe = source.wireframe;
		this.wireframeLinewidth = source.wireframeLinewidth;
		this.wireframeLinecap = source.wireframeLinecap;
		this.wireframeLinejoin = source.wireframeLinejoin;

		this.fog = source.fog;

		return this;

	}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms[ propertyName ].value;

				}
```
</details>

### `set(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( value ) {

					this.uniforms[ propertyName ].value = value;

				}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms[ propertyName ].value;

				}
```
</details>

### `set(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( value ) {

					this.uniforms[ propertyName ].value = value;

				}
```
</details>


---

## Classes

### `MeshGouraudMaterial`

<details><summary>Class Code</summary>

```ts
class MeshGouraudMaterial extends ShaderMaterial {

	constructor( parameters ) {

		super();

		console.warn( 'THREE.MeshGouraudMaterial: MeshGouraudMaterial has been deprecated and will be removed with r183. Use THREE.MeshLambertMaterial instead.' ); // @deprecated r173

		this.isMeshGouraudMaterial = true;

		this.type = 'MeshGouraudMaterial';

		//this.color = new THREE.Color( 0xffffff ); // diffuse

		//this.map = null;

		//this.lightMap = null;
		//this.lightMapIntensity = 1.0;

		//this.aoMap = null;
		//this.aoMapIntensity = 1.0;

		//this.emissive = new THREE.Color( 0x000000 );
		//this.emissiveIntensity = 1.0;
		//this.emissiveMap = null;

		//this.specularMap = null;

		//this.alphaMap = null;

		//this.envMap = null;
		this.combine = MultiplyOperation; // combine has no uniform
		//this.reflectivity = 1;
		//this.refractionRatio = 0.98;

		this.fog = false; // set to use scene fog
		this.lights = true; // set to use scene lights
		this.clipping = false; // set to use user-defined clipping planes

		const shader = GouraudShader;

		this.defines = Object.assign( {}, shader.defines );
		this.uniforms = UniformsUtils.clone( shader.uniforms );
		this.vertexShader = shader.vertexShader;
		this.fragmentShader = shader.fragmentShader;

		const exposePropertyNames = [
			'map', 'lightMap', 'lightMapIntensity', 'aoMap', 'aoMapIntensity',
			'emissive', 'emissiveIntensity', 'emissiveMap', 'specularMap', 'alphaMap',
			'envMap', 'reflectivity', 'refractionRatio', 'opacity', 'diffuse'
		];

		for ( const propertyName of exposePropertyNames ) {

			Object.defineProperty( this, propertyName, {

				get: function () {

					return this.uniforms[ propertyName ].value;

				},

				set: function ( value ) {

					this.uniforms[ propertyName ].value = value;

				}

			} );

		}

		Object.defineProperty( this, 'color', Object.getOwnPropertyDescriptor( this, 'diffuse' ) );

		this.setValues( parameters );

	}

	copy( source ) {

		super.copy( source );

		this.color.copy( source.color );

		this.map = source.map;

		this.lightMap = source.lightMap;
		this.lightMapIntensity = source.lightMapIntensity;

		this.aoMap = source.aoMap;
		this.aoMapIntensity = source.aoMapIntensity;

		this.emissive.copy( source.emissive );
		this.emissiveMap = source.emissiveMap;
		this.emissiveIntensity = source.emissiveIntensity;

		this.specularMap = source.specularMap;

		this.alphaMap = source.alphaMap;

		this.envMap = source.envMap;
		this.combine = source.combine;
		this.reflectivity = source.reflectivity;
		this.refractionRatio = source.refractionRatio;

		this.wireframe = source.wireframe;
		this.wireframeLinewidth = source.wireframeLinewidth;
		this.wireframeLinecap = source.wireframeLinecap;
		this.wireframeLinejoin = source.wireframeLinejoin;

		this.fog = source.fog;

		return this;

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.color.copy( source.color );

		this.map = source.map;

		this.lightMap = source.lightMap;
		this.lightMapIntensity = source.lightMapIntensity;

		this.aoMap = source.aoMap;
		this.aoMapIntensity = source.aoMapIntensity;

		this.emissive.copy( source.emissive );
		this.emissiveMap = source.emissiveMap;
		this.emissiveIntensity = source.emissiveIntensity;

		this.specularMap = source.specularMap;

		this.alphaMap = source.alphaMap;

		this.envMap = source.envMap;
		this.combine = source.combine;
		this.reflectivity = source.reflectivity;
		this.refractionRatio = source.refractionRatio;

		this.wireframe = source.wireframe;
		this.wireframeLinewidth = source.wireframeLinewidth;
		this.wireframeLinecap = source.wireframeLinecap;
		this.wireframeLinejoin = source.wireframeLinejoin;

		this.fog = source.fog;

		return this;

	}
```
</details>


---