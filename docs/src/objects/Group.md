[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Group.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/Group.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Object3D` | `../core/Object3D.js` |


---

## Classes

### `Group`

<details><summary>Class Code</summary>

```ts
class Group extends Object3D {

	constructor() {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isGroup = true;

		this.type = 'Group';

	}

}
```
</details>


---