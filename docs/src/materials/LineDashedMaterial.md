[⬅️ Back to Table of Contents](../../index.md)

# 📄 `LineDashedMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/LineDashedMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LineBasicMaterial` | `./LineBasicMaterial.js` |


---

## Functions

### `LineDashedMaterial.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.scale = source.scale;
		this.dashSize = source.dashSize;
		this.gapSize = source.gapSize;

		return this;

	}
```
</details>


---

## Classes

### `LineDashedMaterial`

<details><summary>Class Code</summary>

```ts
class LineDashedMaterial extends LineBasicMaterial {

	/**
	 * Constructs a new line dashed material.
	 *
	 * @param {Object} [parameters] - An object with one or more properties
	 * defining the material's appearance. Any property of the material
	 * (including any property from inherited materials) can be passed
	 * in here. Color values can be passed any type of value accepted
	 * by {@link Color#set}.
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
		this.isLineDashedMaterial = true;
		this.type = 'LineDashedMaterial';

		/**
		 * The scale of the dashed part of a line.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.scale = 1;

		/**
		 * The size of the dash. This is both the gap with the stroke.
		 *
		 * @type {number}
		 * @default 3
		 */
		this.dashSize = 3;

		/**
		 * The size of the gap.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.gapSize = 1;

		this.setValues( parameters );

	}

	copy( source ) {

		super.copy( source );

		this.scale = source.scale;
		this.dashSize = source.dashSize;
		this.gapSize = source.gapSize;

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

		this.scale = source.scale;
		this.dashSize = source.dashSize;
		this.gapSize = source.gapSize;

		return this;

	}
```
</details>


---