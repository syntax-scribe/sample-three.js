[⬅️ Back to Table of Contents](../../index.md)

# 📄 `HemisphereLight.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/lights/HemisphereLight.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Light` | `./Light.js` |
| `Color` | `../math/Color.js` |
| `Object3D` | `../core/Object3D.js` |


---

## Functions

### `HemisphereLight.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.groundColor.copy`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.groundColor.copy( source.groundColor );

		return this;

	}
```
</details>


---

## Classes

### `HemisphereLight`

<details><summary>Class Code</summary>

```ts
class HemisphereLight extends Light {

	/**
	 * Constructs a new hemisphere light.
	 *
	 * @param {(number|Color|string)} [skyColor=0xffffff] - The light's sky color.
	 * @param {(number|Color|string)} [groundColor=0xffffff] - The light's ground color.
	 * @param {number} [intensity=1] - The light's strength/intensity.
	 */
	constructor( skyColor, groundColor, intensity ) {

		super( skyColor, intensity );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isHemisphereLight = true;

		this.type = 'HemisphereLight';

		this.position.copy( Object3D.DEFAULT_UP );
		this.updateMatrix();

		/**
		 * The light's ground color.
		 *
		 * @type {Color}
		 */
		this.groundColor = new Color( groundColor );

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.groundColor.copy( source.groundColor );

		return this;

	}

}
```
</details>

#### Methods

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		this.groundColor.copy( source.groundColor );

		return this;

	}
```
</details>


---