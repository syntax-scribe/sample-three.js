[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Line2.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/lines/Line2.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LineSegments2` | `../lines/LineSegments2.js` |
| `LineGeometry` | `../lines/LineGeometry.js` |
| `LineMaterial` | `../lines/LineMaterial.js` |


---

## Classes

### `Line2`

<details><summary>Class Code</summary>

```ts
class Line2 extends LineSegments2 {

	/**
	 * Constructs a new wide line.
	 *
	 * @param {LineGeometry} [geometry] - The line geometry.
	 * @param {LineMaterial} [material] - The line material.
	 */
	constructor( geometry = new LineGeometry(), material = new LineMaterial( { color: Math.random() * 0xffffff } ) ) {

		super( geometry, material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLine2 = true;

		this.type = 'Line2';

	}

}
```
</details>


---