[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MapControls.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/controls/MapControls.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `MOUSE` | `three` |
| `TOUCH` | `three` |
| `OrbitControls` | `./OrbitControls.js` |


---

## Classes

### `MapControls`

<details><summary>Class Code</summary>

```ts
class MapControls extends OrbitControls {

	constructor( object, domElement ) {

		super( object, domElement );

		/**
		 * Overwritten and set to `false` to pan orthogonal to world-space direction `camera.up`.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.screenSpacePanning = false;

		/**
		 * This object contains references to the mouse actions used by the controls.
		 *
		 * ```js
		 * controls.mouseButtons = {
		 * 	LEFT: THREE.MOUSE.PAN,
		 * 	MIDDLE: THREE.MOUSE.DOLLY,
		 * 	RIGHT: THREE.MOUSE.ROTATE
		 * }
		 * ```
		 * @type {Object}
		 */
		this.mouseButtons = { LEFT: MOUSE.PAN, MIDDLE: MOUSE.DOLLY, RIGHT: MOUSE.ROTATE };

		/**
		 * This object contains references to the touch actions used by the controls.
		 *
		 * ```js
		 * controls.mouseButtons = {
		 * 	ONE: THREE.TOUCH.PAN,
		 * 	TWO: THREE.TOUCH.DOLLY_ROTATE
		 * }
		 * ```
		 * @type {Object}
		 */
		this.touches = { ONE: TOUCH.PAN, TWO: TOUCH.DOLLY_ROTATE };

	}

}
```
</details>


---