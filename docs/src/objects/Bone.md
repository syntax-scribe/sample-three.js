[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Bone.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/Bone.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Object3D` | `../core/Object3D.js` |


---

## Classes

### `Bone`

<details><summary>Class Code</summary>

```ts
class Bone extends Object3D {

	/**
	 * Constructs a new bone.
	 */
	constructor() {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isBone = true;

		this.type = 'Bone';

	}

}
```
</details>


---