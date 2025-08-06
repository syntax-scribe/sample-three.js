[⬅️ Back to Table of Contents](../../index.md)

# 📄 `DirectionalLightShadow.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/lights/DirectionalLightShadow.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightShadow` | `./LightShadow.js` |
| `OrthographicCamera` | `../cameras/OrthographicCamera.js` |


---

## Classes

### `DirectionalLightShadow`

<details><summary>Class Code</summary>

```ts
class DirectionalLightShadow extends LightShadow {

	/**
	 * Constructs a new directional light shadow.
	 */
	constructor() {

		super( new OrthographicCamera( - 5, 5, 5, - 5, 0.5, 500 ) );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isDirectionalLightShadow = true;

	}

}
```
</details>


---