[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderLists.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/RenderLists.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ChainMap` | `./ChainMap.js` |
| `RenderList` | `./RenderList.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_chainKeys` | `any[]` | let/var | `[]` | ✗ |
| `lists` | `ChainMap` | let/var | `this.lists` | ✗ |


---

## Functions

### `RenderLists.get(scene: Scene, camera: Camera): RenderList`

**JSDoc:**
```typescript
/**
	 * Returns a render list for the given scene and camera.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {Camera} camera - The camera.
	 * @return {RenderList} The render list.
	 */
```

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`

**Returns:** `RenderList`

**Calls:**

- `lists.get`
- `lists.set`

<details><summary>Code</summary>

```typescript
get( scene, camera ) {

		const lists = this.lists;

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = camera;

		let list = lists.get( _chainKeys );

		if ( list === undefined ) {

			list = new RenderList( this.lighting, scene, camera );
			lists.set( _chainKeys, list );

		}

		_chainKeys.length = 0;

		return list;

	}
```
</details>

### `RenderLists.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees all internal resources.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
dispose() {

		this.lists = new ChainMap();

	}
```
</details>


---

## Classes

### `RenderLists`

<details><summary>Class Code</summary>

```ts
class RenderLists {

	/**
	 * Constructs a render lists management component.
	 *
	 * @param {Lighting} lighting - The lighting management component.
	 */
	constructor( lighting ) {

		/**
		 * The lighting management component.
		 *
		 * @type {Lighting}
		 */
		this.lighting = lighting;

		/**
		 * The internal chain map which holds the render lists.
		 *
		 * @type {ChainMap}
		 */
		this.lists = new ChainMap();

	}

	/**
	 * Returns a render list for the given scene and camera.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {Camera} camera - The camera.
	 * @return {RenderList} The render list.
	 */
	get( scene, camera ) {

		const lists = this.lists;

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = camera;

		let list = lists.get( _chainKeys );

		if ( list === undefined ) {

			list = new RenderList( this.lighting, scene, camera );
			lists.set( _chainKeys, list );

		}

		_chainKeys.length = 0;

		return list;

	}

	/**
	 * Frees all internal resources.
	 */
	dispose() {

		this.lists = new ChainMap();

	}

}
```
</details>

#### Methods

##### `get(scene: Scene, camera: Camera): RenderList`

<details><summary>Code</summary>

```ts
get( scene, camera ) {

		const lists = this.lists;

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = camera;

		let list = lists.get( _chainKeys );

		if ( list === undefined ) {

			list = new RenderList( this.lighting, scene, camera );
			lists.set( _chainKeys, list );

		}

		_chainKeys.length = 0;

		return list;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.lists = new ChainMap();

	}
```
</details>


---