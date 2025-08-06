[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshPostProcessingMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/materials/MeshPostProcessingMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `MeshPhysicalMaterial` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `aoPassMap` | `any` | let/var | `parameters.aoPassMap` | ✗ |
| `aoPassMapScale` | `any` | let/var | `parameters.aoPassMapScale \|\| 1.0` | ✗ |
| `aomap_pars_fragment_replace...` | `"\n#ifdef USE_AOMAP\n\n\tuniform samp...` | let/var | `` #ifdef USE_AOMAP uniform sampler2D aoMap; uniform float aoMapIntensity; #en...` | ✗ |
| `aomap_fragment_replacement` | `"\n#ifndef AOPASSMAP_SWIZZLE\n\t#defi...` | let/var | `` #ifndef AOPASSMAP_SWIZZLE #define AOPASSMAP_SWIZZLE r #endif float ambientO...` | ✗ |


---

## Functions

### `MeshPostProcessingMaterial._customProgramCacheKey(): "" | "aoPassMap"`

**Returns:** `"" | "aoPassMap"`

<details><summary>Code</summary>

```typescript
_customProgramCacheKey() {

		return this._aoPassMap !== undefined && this._aoPassMap !== null ? 'aoPassMap' : '';

	}
```
</details>

### `MeshPostProcessingMaterial._onBeforeCompile(shader: any): void`

**Parameters:**

- **`shader`** `any`

**Returns:** `void`

**Calls:**

- `shader.fragmentShader.replace`
- `this._setUniforms`

<details><summary>Code</summary>

```typescript
_onBeforeCompile( shader ) {

		this._shader = shader;

		if ( this._aoPassMap !== undefined && this._aoPassMap !== null ) {

			shader.fragmentShader = shader.fragmentShader.replace(
				'#include <aomap_pars_fragment>',
				aomap_pars_fragment_replacement
			);
			shader.fragmentShader = shader.fragmentShader.replace(
				'#include <aomap_fragment>',
				aomap_fragment_replacement
			);

		}

		this._setUniforms();

	}
```
</details>

### `MeshPostProcessingMaterial._setUniforms(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setUniforms() {

		if ( this._shader ) {

			this._shader.uniforms.tAoPassMap = { value: this._aoPassMap };
			this._shader.uniforms.aoPassMapScale = { value: this.aoPassMapScale };

		}

	}
```
</details>


---

## Classes

### `MeshPostProcessingMaterial`

<details><summary>Class Code</summary>

```ts
class MeshPostProcessingMaterial extends MeshPhysicalMaterial {

	/**
	 * Constructs a new conditional line material.
	 *
	 * @param {Object} [parameters] - An object with one or more properties
	 * defining the material's appearance. Any property of the material
	 * (including any property from inherited materials) can be passed
	 * in here. Color values can be passed any type of value accepted
	 * by {@link Color#set}.
	 */
	constructor( parameters ) {

		const aoPassMap = parameters.aoPassMap;
		const aoPassMapScale = parameters.aoPassMapScale || 1.0;
		delete parameters.aoPassMap;
		delete parameters.aoPassMapScale;

		super( parameters );

		this.onBeforeCompile = this._onBeforeCompile;
		this.customProgramCacheKey = this._customProgramCacheKey;
		this._aoPassMap = aoPassMap;

		/**
		 * The scale of the AO pass.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.aoPassMapScale = aoPassMapScale;
		this._shader = null;

	}

	/**
	 * A texture representing the AO pass.
	 *
	 * @type {Texture}
	 */
	get aoPassMap() {

		return this._aoPassMap;

	}

	set aoPassMap( aoPassMap ) {

		this._aoPassMap = aoPassMap;
		this.needsUpdate = true;
		this._setUniforms();

	}

	_customProgramCacheKey() {

		return this._aoPassMap !== undefined && this._aoPassMap !== null ? 'aoPassMap' : '';

	}

	_onBeforeCompile( shader ) {

		this._shader = shader;

		if ( this._aoPassMap !== undefined && this._aoPassMap !== null ) {

			shader.fragmentShader = shader.fragmentShader.replace(
				'#include <aomap_pars_fragment>',
				aomap_pars_fragment_replacement
			);
			shader.fragmentShader = shader.fragmentShader.replace(
				'#include <aomap_fragment>',
				aomap_fragment_replacement
			);

		}

		this._setUniforms();

	}

	_setUniforms() {

		if ( this._shader ) {

			this._shader.uniforms.tAoPassMap = { value: this._aoPassMap };
			this._shader.uniforms.aoPassMapScale = { value: this.aoPassMapScale };

		}

	}

}
```
</details>

#### Methods

##### `_customProgramCacheKey(): "" | "aoPassMap"`

<details><summary>Code</summary>

```ts
_customProgramCacheKey() {

		return this._aoPassMap !== undefined && this._aoPassMap !== null ? 'aoPassMap' : '';

	}
```
</details>

##### `_onBeforeCompile(shader: any): void`

<details><summary>Code</summary>

```ts
_onBeforeCompile( shader ) {

		this._shader = shader;

		if ( this._aoPassMap !== undefined && this._aoPassMap !== null ) {

			shader.fragmentShader = shader.fragmentShader.replace(
				'#include <aomap_pars_fragment>',
				aomap_pars_fragment_replacement
			);
			shader.fragmentShader = shader.fragmentShader.replace(
				'#include <aomap_fragment>',
				aomap_fragment_replacement
			);

		}

		this._setUniforms();

	}
```
</details>

##### `_setUniforms(): void`

<details><summary>Code</summary>

```ts
_setUniforms() {

		if ( this._shader ) {

			this._shader.uniforms.tAoPassMap = { value: this._aoPassMap };
			this._shader.uniforms.aoPassMapScale = { value: this.aoPassMapScale };

		}

	}
```
</details>


---