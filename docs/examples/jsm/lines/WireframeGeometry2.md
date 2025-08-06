[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WireframeGeometry2.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/lines/WireframeGeometry2.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WireframeGeometry` | `three` |
| `LineSegmentsGeometry` | `../lines/LineSegmentsGeometry.js` |


---

## Classes

### `WireframeGeometry2`

<details><summary>Class Code</summary>

```ts
class WireframeGeometry2 extends LineSegmentsGeometry {

	/**
	 * Constructs a new wireframe geometry.
	 *
	 * @param {BufferGeometry} [geometry] - The geometry to render the wireframe for.
	 */
	constructor( geometry ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWireframeGeometry2 = true;

		this.type = 'WireframeGeometry2';

		this.fromWireframeGeometry( new WireframeGeometry( geometry ) );

		// set colors, maybe

	}

}
```
</details>


---