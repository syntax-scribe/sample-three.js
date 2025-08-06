[⬅️ Back to Table of Contents](../../index.md)

# 📄 `LightProbe.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/lights/LightProbe.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `SphericalHarmonics3` | `../math/SphericalHarmonics3.js` |
| `Light` | `./Light.js` |


---

## Functions

### `LightProbe.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.sh.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.sh.copy( source.sh );

		return this;

	}
```
</details>

### `LightProbe.fromJSON(json: any): LightProbe`

**JSDoc:**
```typescript
/**
	 * Deserializes the light prove from the given JSON.
	 *
	 * @param {Object} json - The JSON holding the serialized light probe.
	 * @return {LightProbe} A reference to this light probe.
	 */
```

**Parameters:**

- **`json`** `any`

**Returns:** `LightProbe`

**Calls:**

- `this.sh.fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		this.intensity = json.intensity; // TODO: Move this bit to Light.fromJSON();
		this.sh.fromArray( json.sh );

		return this;

	}
```
</details>

### `LightProbe.toJSON(meta: any): any`

**Parameters:**

- **`meta`** `any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `this.sh.toArray`

<details><summary>Code</summary>

```typescript
toJSON( meta ) {

		const data = super.toJSON( meta );

		data.object.sh = this.sh.toArray();

		return data;

	}
```
</details>


---

## Classes

### `LightProbe`

<details><summary>Class Code</summary>

```ts
class LightProbe extends Light {

	/**
	 * Constructs a new light probe.
	 *
	 * @param {SphericalHarmonics3} sh - The spherical harmonics which represents encoded lighting information.
	 * @param {number} [intensity=1] - The light's strength/intensity.
	 */
	constructor( sh = new SphericalHarmonics3(), intensity = 1 ) {

		super( undefined, intensity );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLightProbe = true;

		/**
		 * A light probe uses spherical harmonics to encode lighting information.
		 *
		 * @type {SphericalHarmonics3}
		 */
		this.sh = sh;

	}

	copy( source ) {

		super.copy( source );

		this.sh.copy( source.sh );

		return this;

	}

	/**
	 * Deserializes the light prove from the given JSON.
	 *
	 * @param {Object} json - The JSON holding the serialized light probe.
	 * @return {LightProbe} A reference to this light probe.
	 */
	fromJSON( json ) {

		this.intensity = json.intensity; // TODO: Move this bit to Light.fromJSON();
		this.sh.fromArray( json.sh );

		return this;

	}

	toJSON( meta ) {

		const data = super.toJSON( meta );

		data.object.sh = this.sh.toArray();

		return data;

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.sh.copy( source.sh );

		return this;

	}
```
</details>

##### `fromJSON(json: any): LightProbe`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		this.intensity = json.intensity; // TODO: Move this bit to Light.fromJSON();
		this.sh.fromArray( json.sh );

		return this;

	}
```
</details>

##### `toJSON(meta: any): any`

<details><summary>Code</summary>

```ts
toJSON( meta ) {

		const data = super.toJSON( meta );

		data.object.sh = this.sh.toArray();

		return data;

	}
```
</details>


---