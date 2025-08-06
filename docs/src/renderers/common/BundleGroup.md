[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BundleGroup.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/BundleGroup.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Group` | `../../objects/Group.js` |


---

## Classes

### `BundleGroup`

<details><summary>Class Code</summary>

```ts
class BundleGroup extends Group {

	/**
	 * Constructs a new bundle group.
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
		this.isBundleGroup = true;

		/**
		 * This property is only relevant for detecting types
		 * during serialization/deserialization. It should always
		 * match the class name.
		 *
		 * @type {string}
		 * @readonly
		 * @default 'BundleGroup'
		 */
		this.type = 'BundleGroup';

		/**
		 * Whether the bundle is static or not. When set to `true`, the structure
		 * is assumed to be static and does not change. E.g. no new objects are
		 * added to the group
		 *
		 * If a change is required, an update can still be forced by setting the
		 * `needsUpdate` flag to `true`.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.static = true;

		/**
		 * The bundle group's version.
		 *
		 * @type {number}
		 * @readonly
		 * @default 0
		 */
		this.version = 0;

	}

	/**
	 * Set this property to `true` when the bundle group has changed.
	 *
	 * @type {boolean}
	 * @default false
	 * @param {boolean} value
	 */
	set needsUpdate( value ) {

		if ( value === true ) this.version ++;

	}

}
```
</details>


---