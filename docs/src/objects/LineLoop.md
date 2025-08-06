[⬅️ Back to Table of Contents](../../index.md)

# 📄 `LineLoop.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/LineLoop.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Line` | `./Line.js` |


---

## Classes

### `LineLoop`

<details><summary>Class Code</summary>

```ts
class LineLoop extends Line {

	/**
	 * Constructs a new line loop.
	 *
	 * @param {BufferGeometry} [geometry] - The line geometry.
	 * @param {Material|Array<Material>} [material] - The line material.
	 */
	constructor( geometry, material ) {

		super( geometry, material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLineLoop = true;

		this.type = 'LineLoop';

	}

}
```
</details>


---