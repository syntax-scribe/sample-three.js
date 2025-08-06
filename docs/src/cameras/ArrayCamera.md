[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ArrayCamera.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/cameras/ArrayCamera.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `PerspectiveCamera` | `./PerspectiveCamera.js` |


---

## Classes

### `ArrayCamera`

<details><summary>Class Code</summary>

```ts
class ArrayCamera extends PerspectiveCamera {

	/**
	 * Constructs a new array camera.
	 *
	 * @param {Array<PerspectiveCamera>} [array=[]] - An array of perspective sub cameras.
	 */
	constructor( array = [] ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isArrayCamera = true;

		/**
		 * Whether this camera is used with multiview rendering or not.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default false
		 */
		this.isMultiViewCamera = false;

		/**
		 * An array of perspective sub cameras.
		 *
		 * @type {Array<PerspectiveCamera>}
		 */
		this.cameras = array;

	}

}
```
</details>


---