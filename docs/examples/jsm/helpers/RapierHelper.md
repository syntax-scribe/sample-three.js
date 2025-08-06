[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RapierHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/RapierHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LineSegments` | `three` |
| `LineBasicMaterial` | `three` |
| `BufferAttribute` | `three` |


---

## Functions

### `RapierHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Call this in the render loop to update the outlines.
	 */
```

**Returns:** `void`

**Calls:**

- `this.world.debugRender`
- `this.geometry.deleteAttribute`
- `this.geometry.setAttribute`

<details><summary>Code</summary>

```typescript
update() {

		const { vertices, colors } = this.world.debugRender();

		this.geometry.deleteAttribute( 'position' );
		this.geometry.deleteAttribute( 'color' );

		this.geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );
		this.geometry.setAttribute( 'color', new BufferAttribute( colors, 4 ) );

	}
```
</details>

### `RapierHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.geometry.dispose`
- `this.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>


---

## Classes

### `RapierHelper`

<details><summary>Class Code</summary>

```ts
class RapierHelper extends LineSegments {

	/**
	 * Constructs a new Rapier debug helper.
	 *
	 * @param {RAPIER.world} world - The Rapier world to visualize.
	 */
	constructor( world ) {

		super();

		/**
		 * The Rapier world to visualize.
		 *
		 * @type {RAPIER.world}
		 */
		this.world = world;

		this.material = new LineBasicMaterial( { vertexColors: true } );
		this.frustumCulled = false;

	}

	/**
	 * Call this in the render loop to update the outlines.
	 */
	update() {

		const { vertices, colors } = this.world.debugRender();

		this.geometry.deleteAttribute( 'position' );
		this.geometry.deleteAttribute( 'color' );

		this.geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );
		this.geometry.setAttribute( 'color', new BufferAttribute( colors, 4 ) );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}

}
```
</details>

#### Methods

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const { vertices, colors } = this.world.debugRender();

		this.geometry.deleteAttribute( 'position' );
		this.geometry.deleteAttribute( 'color' );

		this.geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );
		this.geometry.setAttribute( 'color', new BufferAttribute( colors, 4 ) );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>


---