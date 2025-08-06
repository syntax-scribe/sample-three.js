[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ClippingGroup.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/ClippingGroup.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Group` | `./Group.js` |


---

## Classes

### `ClippingGroup`

<details><summary>Class Code</summary>

```ts
class ClippingGroup extends Group {

	/**
	 * Constructs a new clipping group.
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
		this.isClippingGroup = true;

		/**
		 * An array with clipping planes.
		 *
		 * @type {Array<Plane>}
		 */
		this.clippingPlanes = [];

		/**
		 * Whether clipping should be enabled or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.enabled = true;

		/**
		 * Whether the intersection of the clipping planes is used to clip objects, rather than their union.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.clipIntersection = false;

		/**
		 * Whether shadows should be clipped or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.clipShadows = false;

	}

}
```
</details>


---