[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderContexts.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/RenderContexts.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ChainMap` | `./ChainMap.js` |
| `RenderContext` | `./RenderContext.js` |
| `Scene` | `../../scenes/Scene.js` |
| `Camera` | `../../cameras/Camera.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_chainKeys` | `any[]` | let/var | `[]` | ✗ |
| `_defaultScene` | `Scene` | let/var | `new Scene()` | ✗ |
| `_defaultCamera` | `Camera` | let/var | `new Camera()` | ✗ |
| `attachmentState` | `any` | let/var | `*not shown*` | ✗ |
| `format` | `any` | let/var | `renderTarget.texture.format` | ✗ |
| `count` | `any` | let/var | `renderTarget.textures.length` | ✗ |


---

## Functions

### `RenderContexts.get(scene: Scene, camera: Camera, renderTarget: RenderTarget): RenderContext`

**JSDoc:**
```typescript
/**
	 * Returns a render context for the given scene, camera and render target.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {?RenderTarget} [renderTarget=null] - The active render target.
	 * @return {RenderContext} The render context.
	 */
```

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`
- **`renderTarget`** `RenderTarget`

**Returns:** `RenderContext`

**Calls:**

- `this._getChainMap`
- `chainMap.get`
- `chainMap.set`

<details><summary>Code</summary>

```typescript
get( scene, camera, renderTarget = null ) {

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = camera;

		let attachmentState;

		if ( renderTarget === null ) {

			attachmentState = 'default';

		} else {

			const format = renderTarget.texture.format;
			const count = renderTarget.textures.length;

			attachmentState = `${ count }:${ format }:${ renderTarget.samples }:${ renderTarget.depthBuffer }:${ renderTarget.stencilBuffer }`;

		}

		const chainMap = this._getChainMap( attachmentState );

		let renderState = chainMap.get( _chainKeys );

		if ( renderState === undefined ) {

			renderState = new RenderContext();

			chainMap.set( _chainKeys, renderState );

		}

		_chainKeys.length = 0;

		if ( renderTarget !== null ) renderState.sampleCount = renderTarget.samples === 0 ? 1 : renderTarget.samples;

		return renderState;

	}
```
</details>

### `RenderContexts.getForClear(renderTarget: RenderTarget): RenderContext`

**JSDoc:**
```typescript
/**
	 * Returns a render context intended for clear operations.
	 *
	 * @param {?RenderTarget} [renderTarget=null] - The active render target.
	 * @return {RenderContext} The render context.
	 */
```

**Parameters:**

- **`renderTarget`** `RenderTarget`

**Returns:** `RenderContext`

**Calls:**

- `this.get`

<details><summary>Code</summary>

```typescript
getForClear( renderTarget = null ) {

		return this.get( _defaultScene, _defaultCamera, renderTarget );

	}
```
</details>

### `RenderContexts._getChainMap(attachmentState: string): ChainMap`

**JSDoc:**
```typescript
/**
	 * Returns a chain map for the given attachment state.
	 *
	 * @private
	 * @param {string} attachmentState - The attachment state.
	 * @return {ChainMap} The chain map.
	 */
```

**Parameters:**

- **`attachmentState`** `string`

**Returns:** `ChainMap`

<details><summary>Code</summary>

```typescript
_getChainMap( attachmentState ) {

		return this.chainMaps[ attachmentState ] || ( this.chainMaps[ attachmentState ] = new ChainMap() );

	}
```
</details>

### `RenderContexts.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
dispose() {

		this.chainMaps = {};

	}
```
</details>


---

## Classes

### `RenderContexts`

<details><summary>Class Code</summary>

```ts
class RenderContexts {

	/**
	 * Constructs a new render context management component.
	 */
	constructor() {

		/**
		 * A dictionary that manages render contexts in chain maps
		 * for each attachment state.
		 *
		 * @type {Object<string,ChainMap>}
		 */
		this.chainMaps = {};

	}

	/**
	 * Returns a render context for the given scene, camera and render target.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {?RenderTarget} [renderTarget=null] - The active render target.
	 * @return {RenderContext} The render context.
	 */
	get( scene, camera, renderTarget = null ) {

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = camera;

		let attachmentState;

		if ( renderTarget === null ) {

			attachmentState = 'default';

		} else {

			const format = renderTarget.texture.format;
			const count = renderTarget.textures.length;

			attachmentState = `${ count }:${ format }:${ renderTarget.samples }:${ renderTarget.depthBuffer }:${ renderTarget.stencilBuffer }`;

		}

		const chainMap = this._getChainMap( attachmentState );

		let renderState = chainMap.get( _chainKeys );

		if ( renderState === undefined ) {

			renderState = new RenderContext();

			chainMap.set( _chainKeys, renderState );

		}

		_chainKeys.length = 0;

		if ( renderTarget !== null ) renderState.sampleCount = renderTarget.samples === 0 ? 1 : renderTarget.samples;

		return renderState;

	}

	/**
	 * Returns a render context intended for clear operations.
	 *
	 * @param {?RenderTarget} [renderTarget=null] - The active render target.
	 * @return {RenderContext} The render context.
	 */
	getForClear( renderTarget = null ) {

		return this.get( _defaultScene, _defaultCamera, renderTarget );

	}

	/**
	 * Returns a chain map for the given attachment state.
	 *
	 * @private
	 * @param {string} attachmentState - The attachment state.
	 * @return {ChainMap} The chain map.
	 */
	_getChainMap( attachmentState ) {

		return this.chainMaps[ attachmentState ] || ( this.chainMaps[ attachmentState ] = new ChainMap() );

	}

	/**
	 * Frees internal resources.
	 */
	dispose() {

		this.chainMaps = {};

	}

}
```
</details>

#### Methods

##### `get(scene: Scene, camera: Camera, renderTarget: RenderTarget): RenderContext`

<details><summary>Code</summary>

```ts
get( scene, camera, renderTarget = null ) {

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = camera;

		let attachmentState;

		if ( renderTarget === null ) {

			attachmentState = 'default';

		} else {

			const format = renderTarget.texture.format;
			const count = renderTarget.textures.length;

			attachmentState = `${ count }:${ format }:${ renderTarget.samples }:${ renderTarget.depthBuffer }:${ renderTarget.stencilBuffer }`;

		}

		const chainMap = this._getChainMap( attachmentState );

		let renderState = chainMap.get( _chainKeys );

		if ( renderState === undefined ) {

			renderState = new RenderContext();

			chainMap.set( _chainKeys, renderState );

		}

		_chainKeys.length = 0;

		if ( renderTarget !== null ) renderState.sampleCount = renderTarget.samples === 0 ? 1 : renderTarget.samples;

		return renderState;

	}
```
</details>

##### `getForClear(renderTarget: RenderTarget): RenderContext`

<details><summary>Code</summary>

```ts
getForClear( renderTarget = null ) {

		return this.get( _defaultScene, _defaultCamera, renderTarget );

	}
```
</details>

##### `_getChainMap(attachmentState: string): ChainMap`

<details><summary>Code</summary>

```ts
_getChainMap( attachmentState ) {

		return this.chainMaps[ attachmentState ] || ( this.chainMaps[ attachmentState ] = new ChainMap() );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.chainMaps = {};

	}
```
</details>


---