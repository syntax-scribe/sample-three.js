[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderBundles.js`

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
📂 **`src/renderers/common/RenderBundles.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ChainMap` | `./ChainMap.js` |
| `RenderBundle` | `./RenderBundle.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_chainKeys` | `any[]` | let/var | `[]` | ✗ |
| `bundles` | `ChainMap` | let/var | `this.bundles` | ✗ |


---

## Functions

### `RenderBundles.get(bundleGroup: BundleGroup, camera: Camera): RenderBundle`

**JSDoc:**
```typescript
/**
	 * Returns a render bundle for the given bundle group and camera.
	 *
	 * @param {BundleGroup} bundleGroup - The bundle group.
	 * @param {Camera} camera - The camera the bundle group is rendered with.
	 * @return {RenderBundle} The render bundle.
	 */
```

**Parameters:**

- **`bundleGroup`** `BundleGroup`
- **`camera`** `Camera`

**Returns:** `RenderBundle`

**Calls:**

- `bundles.get`
- `bundles.set`

<details><summary>Code</summary>

```typescript
get( bundleGroup, camera ) {

		const bundles = this.bundles;

		_chainKeys[ 0 ] = bundleGroup;
		_chainKeys[ 1 ] = camera;

		let bundle = bundles.get( _chainKeys );

		if ( bundle === undefined ) {

			bundle = new RenderBundle( bundleGroup, camera );
			bundles.set( _chainKeys, bundle );

		}

		_chainKeys.length = 0;

		return bundle;

	}
```
</details>

### `RenderBundles.dispose(): void`

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

		this.bundles = new ChainMap();

	}
```
</details>


---

## Classes

### `RenderBundles`

<details><summary>Class Code</summary>

```ts
class RenderBundles {

	/**
	 * Constructs a new render bundle management component.
	 */
	constructor() {

		/**
		 * A chain map for maintaining the render bundles.
		 *
		 * @type {ChainMap}
		 */
		this.bundles = new ChainMap();

	}

	/**
	 * Returns a render bundle for the given bundle group and camera.
	 *
	 * @param {BundleGroup} bundleGroup - The bundle group.
	 * @param {Camera} camera - The camera the bundle group is rendered with.
	 * @return {RenderBundle} The render bundle.
	 */
	get( bundleGroup, camera ) {

		const bundles = this.bundles;

		_chainKeys[ 0 ] = bundleGroup;
		_chainKeys[ 1 ] = camera;

		let bundle = bundles.get( _chainKeys );

		if ( bundle === undefined ) {

			bundle = new RenderBundle( bundleGroup, camera );
			bundles.set( _chainKeys, bundle );

		}

		_chainKeys.length = 0;

		return bundle;

	}

	/**
	 * Frees all internal resources.
	 */
	dispose() {

		this.bundles = new ChainMap();

	}

}
```
</details>

#### Methods

##### `get(bundleGroup: BundleGroup, camera: Camera): RenderBundle`

<details><summary>Code</summary>

```ts
get( bundleGroup, camera ) {

		const bundles = this.bundles;

		_chainKeys[ 0 ] = bundleGroup;
		_chainKeys[ 1 ] = camera;

		let bundle = bundles.get( _chainKeys );

		if ( bundle === undefined ) {

			bundle = new RenderBundle( bundleGroup, camera );
			bundles.set( _chainKeys, bundle );

		}

		_chainKeys.length = 0;

		return bundle;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.bundles = new ChainMap();

	}
```
</details>


---