[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeVarying.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/NodeVarying.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeVar` | `./NodeVar.js` |


---

## Classes

### `NodeVarying`

<details><summary>Class Code</summary>

```ts
class NodeVarying extends NodeVar {

	/**
	 * Constructs a new node varying.
	 *
	 * @param {string} name - The name of the varying.
	 * @param {string} type - The type of the varying.
	 * @param {?string} interpolationType - The interpolation type of the varying.
	 * @param {?string} interpolationSampling - The interpolation sampling type of the varying.
	 */
	constructor( name, type, interpolationType = null, interpolationSampling = null ) {

		super( name, type );

		/**
		 * Whether this varying requires interpolation or not. This property can be used
		 * to check if the varying can be optimized for a variable.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.needsInterpolation = false;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isNodeVarying = true;

		/**
		 * The interpolation type of the varying data.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.interpolationType = interpolationType;

		/**
		 * The interpolation sampling type of varying data.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.interpolationSampling = interpolationSampling;

	}

}
```
</details>


---