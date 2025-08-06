[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FXAAPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/FXAAPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FXAAShader` | `../shaders/FXAAShader.js` |
| `ShaderPass` | `./ShaderPass.js` |


---

## Functions

### `FXAAPass.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this.material.uniforms[ 'resolution' ].value.set`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this.material.uniforms[ 'resolution' ].value.set( 1 / width, 1 / height );

	}
```
</details>


---

## Classes

### `FXAAPass`

<details><summary>Class Code</summary>

```ts
class FXAAPass extends ShaderPass {

	/**
	 * Constructs a new FXAA pass.
	 */
	constructor() {

		super( FXAAShader );

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( width, height ) {

		this.material.uniforms[ 'resolution' ].value.set( 1 / width, 1 / height );

	}

}
```
</details>

#### Methods

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this.material.uniforms[ 'resolution' ].value.set( 1 / width, 1 / height );

	}
```
</details>


---