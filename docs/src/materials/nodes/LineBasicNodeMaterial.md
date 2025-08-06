[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LineBasicNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/LineBasicNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `LineBasicMaterial` | `../LineBasicMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `LineBasicMaterial` | let/var | `new LineBasicMaterial()` | ✗ |


---

## Classes

### `LineBasicNodeMaterial`

<details><summary>Class Code</summary>

```ts
class LineBasicNodeMaterial extends NodeMaterial {

	static get type() {

		return 'LineBasicNodeMaterial';

	}

	/**
	 * Constructs a new line basic node material.
	 *
	 * @param {Object} [parameters] - The configuration parameter.
	 */
	constructor( parameters ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLineBasicNodeMaterial = true;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

}
```
</details>


---