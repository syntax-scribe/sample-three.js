[⬅️ Back to Table of Contents](../../index.md)

# 📄 `FogExp2.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/scenes/FogExp2.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `../math/Color.js` |


---

## Functions

### `FogExp2.clone(): FogExp2`

**JSDoc:**
```typescript
/**
	 * Returns a new fog with copied values from this instance.
	 *
	 * @return {FogExp2} A clone of this instance.
	 */
```

**Returns:** `FogExp2`

<details><summary>Code</summary>

```typescript
clone() {

		return new FogExp2( this.color, this.density );

	}
```
</details>

### `FogExp2.toJSON(): any`

**JSDoc:**
```typescript
/**
	 * Serializes the fog into JSON.
	 *
	 * @param {?(Object|string)} meta - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized fog
	 */
```

**Returns:** `any`

**Calls:**

- `this.color.getHex`

<details><summary>Code</summary>

```typescript
toJSON( /* meta */ ) {

		return {
			type: 'FogExp2',
			name: this.name,
			color: this.color.getHex(),
			density: this.density
		};

	}
```
</details>


---

## Classes

### `FogExp2`

<details><summary>Class Code</summary>

```ts
class FogExp2 {

	/**
	 * Constructs a new fog.
	 *
	 * @param {number|Color} color - The fog's color.
	 * @param {number} [density=0.00025] - Defines how fast the fog will grow dense.
	 */
	constructor( color, density = 0.00025 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isFogExp2 = true;

		/**
		 * The name of the fog.
		 *
		 * @type {string}
		 */
		this.name = '';

		/**
		 * The fog's color.
		 *
		 * @type {Color}
		 */
		this.color = new Color( color );

		/**
		 *  Defines how fast the fog will grow dense.
		 *
		 * @type {number}
		 * @default 0.00025
		 */
		this.density = density;

	}

	/**
	 * Returns a new fog with copied values from this instance.
	 *
	 * @return {FogExp2} A clone of this instance.
	 */
	clone() {

		return new FogExp2( this.color, this.density );

	}

	/**
	 * Serializes the fog into JSON.
	 *
	 * @param {?(Object|string)} meta - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized fog
	 */
	toJSON( /* meta */ ) {

		return {
			type: 'FogExp2',
			name: this.name,
			color: this.color.getHex(),
			density: this.density
		};

	}

}
```
</details>

#### Methods

##### `clone(): FogExp2`

<details><summary>Code</summary>

```ts
clone() {

		return new FogExp2( this.color, this.density );

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON( /* meta */ ) {

		return {
			type: 'FogExp2',
			name: this.name,
			color: this.color.getHex(),
			density: this.density
		};

	}
```
</details>


---