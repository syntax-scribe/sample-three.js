[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ProjectorLight.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/lights/webgpu/ProjectorLight.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `SpotLight` | `../SpotLight.js` |


---

## Functions

### `ProjectorLight.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.aspect = source.aspect;

		return this;

	}
```
</details>


---

## Classes

### `ProjectorLight`

<details><summary>Class Code</summary>

```ts
class ProjectorLight extends SpotLight {

	/**
	 * Constructs a new projector light.
	 *
	 * @param {(number|Color|string)} [color=0xffffff] - The light's color.
	 * @param {number} [intensity=1] - The light's strength/intensity measured in candela (cd).
	 * @param {number} [distance=0] - Maximum range of the light. `0` means no limit.
	 * @param {number} [angle=Math.PI/3] - Maximum angle of light dispersion from its direction whose upper bound is `Math.PI/2`.
	 * @param {number} [penumbra=0] - Percent of the spotlight cone that is attenuated due to penumbra. Value range is `[0,1]`.
	 * @param {number} [decay=2] - The amount the light dims along the distance of the light.
	 */
	constructor( color, intensity, distance, angle, penumbra, decay ) {

		super( color, intensity, distance, angle, penumbra, decay );

		/**
		 * Aspect ratio of the light. Set to `null` to use the texture aspect ratio.
		 *
		 * @type {number}
		 * @default null
		 */
		this.aspect = null;

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.aspect = source.aspect;

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

		this.aspect = source.aspect;

		return this;

	}
```
</details>


---