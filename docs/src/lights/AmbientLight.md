[⬅️ Back to Table of Contents](../../index.md)

# 📄 `AmbientLight.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/lights/AmbientLight.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Light` | `./Light.js` |


---

## Classes

### `AmbientLight`

<details><summary>Class Code</summary>

```ts
class AmbientLight extends Light {

	/**
	 * Constructs a new ambient light.
	 *
	 * @param {(number|Color|string)} [color=0xffffff] - The light's color.
	 * @param {number} [intensity=1] - The light's strength/intensity.
	 */
	constructor( color, intensity ) {

		super( color, intensity );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isAmbientLight = true;

		this.type = 'AmbientLight';

	}

}
```
</details>


---