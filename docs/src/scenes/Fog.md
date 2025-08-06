[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Fog.js`

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
📂 **`src/scenes/Fog.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `../math/Color.js` |


---

## Functions

### `Fog.clone(): Fog`

**JSDoc:**
```typescript
/**
	 * Returns a new fog with copied values from this instance.
	 *
	 * @return {Fog} A clone of this instance.
	 */
```

**Returns:** `Fog`

<details><summary>Code</summary>

```typescript
clone() {

		return new Fog( this.color, this.near, this.far );

	}
```
</details>

### `Fog.toJSON(): any`

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
			type: 'Fog',
			name: this.name,
			color: this.color.getHex(),
			near: this.near,
			far: this.far
		};

	}
```
</details>


---

## Classes

### `Fog`

<details><summary>Class Code</summary>

```ts
class Fog {

	/**
	 * Constructs a new fog.
	 *
	 * @param {number|Color} color - The fog's color.
	 * @param {number} [near=1] - The minimum distance to start applying fog.
	 * @param {number} [far=1000] - The maximum distance at which fog stops being calculated and applied.
	 */
	constructor( color, near = 1, far = 1000 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isFog = true;

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
		 * The minimum distance to start applying fog. Objects that are less than
		 * `near` units from the active camera won't be affected by fog.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.near = near;

		/**
		 * The maximum distance at which fog stops being calculated and applied.
		 * Objects that are more than `far` units away from the active camera won't
		 * be affected by fog.
		 *
		 * @type {number}
		 * @default 1000
		 */
		this.far = far;

	}

	/**
	 * Returns a new fog with copied values from this instance.
	 *
	 * @return {Fog} A clone of this instance.
	 */
	clone() {

		return new Fog( this.color, this.near, this.far );

	}

	/**
	 * Serializes the fog into JSON.
	 *
	 * @param {?(Object|string)} meta - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized fog
	 */
	toJSON( /* meta */ ) {

		return {
			type: 'Fog',
			name: this.name,
			color: this.color.getHex(),
			near: this.near,
			far: this.far
		};

	}

}
```
</details>

#### Methods

##### `clone(): Fog`

<details><summary>Code</summary>

```ts
clone() {

		return new Fog( this.color, this.near, this.far );

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON( /* meta */ ) {

		return {
			type: 'Fog',
			name: this.name,
			color: this.color.getHex(),
			near: this.near,
			far: this.far
		};

	}
```
</details>


---