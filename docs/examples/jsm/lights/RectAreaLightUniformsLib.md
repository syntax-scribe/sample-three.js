[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RectAreaLightUniformsLib.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/lights/RectAreaLightUniformsLib.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UniformsLib` | `three` |
| `RectAreaLightTexturesLib` | `./RectAreaLightTexturesLib.js` |


---

## Functions

### `RectAreaLightUniformsLib.init(): void`

**JSDoc:**
```typescript
/**
	 * Inits the uniform library required when using rect area lights.
	 */
```

**Returns:** `void`

**Calls:**

- `RectAreaLightTexturesLib.init`

**Internal Comments:**
```
// data textures (x4)
```

<details><summary>Code</summary>

```typescript
static init() {

		RectAreaLightTexturesLib.init();

		const { LTC_FLOAT_1, LTC_FLOAT_2, LTC_HALF_1, LTC_HALF_2 } = RectAreaLightTexturesLib;

		// data textures

		UniformsLib.LTC_FLOAT_1 = LTC_FLOAT_1;
		UniformsLib.LTC_FLOAT_2 = LTC_FLOAT_2;

		UniformsLib.LTC_HALF_1 = LTC_HALF_1;
		UniformsLib.LTC_HALF_2 = LTC_HALF_2;

	}
```
</details>


---

## Classes

### `RectAreaLightUniformsLib`

<details><summary>Class Code</summary>

```ts
class RectAreaLightUniformsLib {

	/**
	 * Inits the uniform library required when using rect area lights.
	 */
	static init() {

		RectAreaLightTexturesLib.init();

		const { LTC_FLOAT_1, LTC_FLOAT_2, LTC_HALF_1, LTC_HALF_2 } = RectAreaLightTexturesLib;

		// data textures

		UniformsLib.LTC_FLOAT_1 = LTC_FLOAT_1;
		UniformsLib.LTC_FLOAT_2 = LTC_FLOAT_2;

		UniformsLib.LTC_HALF_1 = LTC_HALF_1;
		UniformsLib.LTC_HALF_2 = LTC_HALF_2;

	}

}
```
</details>

#### Methods

##### `init(): void`

<details><summary>Code</summary>

```ts
static init() {

		RectAreaLightTexturesLib.init();

		const { LTC_FLOAT_1, LTC_FLOAT_2, LTC_HALF_1, LTC_HALF_2 } = RectAreaLightTexturesLib;

		// data textures

		UniformsLib.LTC_FLOAT_1 = LTC_FLOAT_1;
		UniformsLib.LTC_FLOAT_2 = LTC_FLOAT_2;

		UniformsLib.LTC_HALF_1 = LTC_HALF_1;
		UniformsLib.LTC_HALF_2 = LTC_HALF_2;

	}
```
</details>


---