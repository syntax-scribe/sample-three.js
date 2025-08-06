[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PostProcessing.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/PostProcessing.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `../../materials/nodes/NodeMaterial.js` |
| `ColorManagement` | `../../math/ColorManagement.js` |
| `vec4` | `../../nodes/TSL.js` |
| `renderOutput` | `../../nodes/TSL.js` |
| `NoToneMapping` | `../../constants.js` |
| `QuadMesh` | `../../renderers/common/QuadMesh.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `NodeMaterial` | let/var | `new NodeMaterial()` | ✗ |
| `renderer` | `Renderer` | let/var | `this.renderer` | ✗ |
| `toneMapping` | `any` | let/var | `renderer.toneMapping` | ✗ |
| `outputColorSpace` | `any` | let/var | `renderer.outputColorSpace` | ✗ |
| `currentXR` | `any` | let/var | `renderer.xr.enabled` | ✗ |
| `renderer` | `Renderer` | let/var | `this.renderer` | ✗ |
| `toneMapping` | `any` | let/var | `renderer.toneMapping` | ✗ |
| `outputColorSpace` | `any` | let/var | `renderer.outputColorSpace` | ✗ |
| `context` | `{ postProcessing: this; onBeforePostP...` | let/var | `{ postProcessing: this, onBeforePostProcessing: null, onAfterPostProcessing: ...` | ✗ |
| `outputNode` | `any` | let/var | `this.outputNode` | ✗ |
| `renderer` | `Renderer` | let/var | `this.renderer` | ✗ |
| `toneMapping` | `any` | let/var | `renderer.toneMapping` | ✗ |
| `outputColorSpace` | `any` | let/var | `renderer.outputColorSpace` | ✗ |
| `currentXR` | `any` | let/var | `renderer.xr.enabled` | ✗ |


---

## Functions

### `PostProcessing.render(): void`

**JSDoc:**
```typescript
/**
	 * When `PostProcessing` is used to apply post processing effects,
	 * the application must use this version of `render()` inside
	 * its animation loop (not the one from the renderer).
	 */
```

**Returns:** `void`

**Calls:**

- `this._update`
- `this._context.onBeforePostProcessing`
- `this._quadMesh.render`
- `this._context.onAfterPostProcessing`

**Internal Comments:**
```
// (x6)
```

<details><summary>Code</summary>

```typescript
render() {

		const renderer = this.renderer;

		this._update();

		if ( this._context.onBeforePostProcessing !== null ) this._context.onBeforePostProcessing();

		const toneMapping = renderer.toneMapping;
		const outputColorSpace = renderer.outputColorSpace;

		renderer.toneMapping = NoToneMapping;
		renderer.outputColorSpace = ColorManagement.workingColorSpace;

		//

		const currentXR = renderer.xr.enabled;
		renderer.xr.enabled = false;

		this._quadMesh.render( renderer );

		renderer.xr.enabled = currentXR;

		//

		renderer.toneMapping = toneMapping;
		renderer.outputColorSpace = outputColorSpace;

		if ( this._context.onAfterPostProcessing !== null ) this._context.onAfterPostProcessing();

	}
```
</details>

### `PostProcessing.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources.
	 */
```

**Returns:** `void`

**Calls:**

- `this._quadMesh.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._quadMesh.material.dispose();

	}
```
</details>

### `PostProcessing._update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the state of the module.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `outputNode.context`
- `renderOutput (from ../../nodes/TSL.js)`

<details><summary>Code</summary>

```typescript
_update() {

		if ( this.needsUpdate === true ) {

			const renderer = this.renderer;

			const toneMapping = renderer.toneMapping;
			const outputColorSpace = renderer.outputColorSpace;

			const context = {
				postProcessing: this,
				onBeforePostProcessing: null,
				onAfterPostProcessing: null
			};

			let outputNode = this.outputNode;

			if ( this.outputColorTransform === true ) {

				outputNode = outputNode.context( context );

				outputNode = renderOutput( outputNode, toneMapping, outputColorSpace );

			} else {

				context.toneMapping = toneMapping;
				context.outputColorSpace = outputColorSpace;

				outputNode = outputNode.context( context );

			}

			this._context = context;

			this._quadMesh.material.fragmentNode = outputNode;
			this._quadMesh.material.needsUpdate = true;

			this.needsUpdate = false;

		}

	}
```
</details>

### `PostProcessing.renderAsync(): Promise<any>`

**JSDoc:**
```typescript
/**
	 * When `PostProcessing` is used to apply post processing effects,
	 * the application must use this version of `renderAsync()` inside
	 * its animation loop (not the one from the renderer).
	 *
	 * @async
	 * @return {Promise} A Promise that resolves when the render has been finished.
	 */
```

**Returns:** `Promise<any>`

**Calls:**

- `this._update`
- `this._context.onBeforePostProcessing`
- `this._quadMesh.renderAsync`
- `this._context.onAfterPostProcessing`

**Internal Comments:**
```
// (x6)
```

<details><summary>Code</summary>

```typescript
async renderAsync() {

		this._update();

		if ( this._context.onBeforePostProcessing !== null ) this._context.onBeforePostProcessing();

		const renderer = this.renderer;

		const toneMapping = renderer.toneMapping;
		const outputColorSpace = renderer.outputColorSpace;

		renderer.toneMapping = NoToneMapping;
		renderer.outputColorSpace = ColorManagement.workingColorSpace;

		//

		const currentXR = renderer.xr.enabled;
		renderer.xr.enabled = false;

		await this._quadMesh.renderAsync( renderer );

		renderer.xr.enabled = currentXR;

		//

		renderer.toneMapping = toneMapping;
		renderer.outputColorSpace = outputColorSpace;

		if ( this._context.onAfterPostProcessing !== null ) this._context.onAfterPostProcessing();

	}
```
</details>


---

## Classes

### `PostProcessing`

<details><summary>Class Code</summary>

```ts
class PostProcessing {

	/**
	 * Constructs a new post processing management module.
	 *
	 * @param {Renderer} renderer - A reference to the renderer.
	 * @param {Node<vec4>} outputNode - An optional output node.
	 */
	constructor( renderer, outputNode = vec4( 0, 0, 1, 1 ) ) {

		/**
		 * A reference to the renderer.
		 *
		 * @type {Renderer}
		 */
		this.renderer = renderer;

		/**
		 * A node which defines the final output of the post
		 * processing. This is usually the last node in a chain
		 * of effect nodes.
		 *
		 * @type {Node<vec4>}
		 */
		this.outputNode = outputNode;

		/**
		 * Whether the default output tone mapping and color
		 * space transformation should be enabled or not.
		 *
		 * It is enabled by default by it must be disabled when
		 * effects must be executed after tone mapping and color
		 * space conversion. A typical example is FXAA which
		 * requires sRGB input.
		 *
		 * When set to `false`, the app must control the output
		 * transformation with `RenderOutputNode`.
		 *
		 * ```js
		 * const outputPass = renderOutput( scenePass );
		 * ```
		 *
		 * @type {boolean}
		 */
		this.outputColorTransform = true;

		/**
		 * Must be set to `true` when the output node changes.
		 *
		 * @type {Node<vec4>}
		 */
		this.needsUpdate = true;

		const material = new NodeMaterial();
		material.name = 'PostProcessing';

		/**
		 * The full screen quad that is used to render
		 * the effects.
		 *
		 * @private
		 * @type {QuadMesh}
		 */
		this._quadMesh = new QuadMesh( material );

		/**
		 * The context of the post processing stack.
		 *
		 * @private
		 * @type {?Object}
		 * @default null
		 */
		this._context = null;

	}

	/**
	 * When `PostProcessing` is used to apply post processing effects,
	 * the application must use this version of `render()` inside
	 * its animation loop (not the one from the renderer).
	 */
	render() {

		const renderer = this.renderer;

		this._update();

		if ( this._context.onBeforePostProcessing !== null ) this._context.onBeforePostProcessing();

		const toneMapping = renderer.toneMapping;
		const outputColorSpace = renderer.outputColorSpace;

		renderer.toneMapping = NoToneMapping;
		renderer.outputColorSpace = ColorManagement.workingColorSpace;

		//

		const currentXR = renderer.xr.enabled;
		renderer.xr.enabled = false;

		this._quadMesh.render( renderer );

		renderer.xr.enabled = currentXR;

		//

		renderer.toneMapping = toneMapping;
		renderer.outputColorSpace = outputColorSpace;

		if ( this._context.onAfterPostProcessing !== null ) this._context.onAfterPostProcessing();

	}

	/**
	 * Returns the current context of the post processing stack.
	 *
	 * @readonly
	 * @type {?Object}
	 */
	get context() {

		return this._context;

	}

	/**
	 * Frees internal resources.
	 */
	dispose() {

		this._quadMesh.material.dispose();

	}

	/**
	 * Updates the state of the module.
	 *
	 * @private
	 */
	_update() {

		if ( this.needsUpdate === true ) {

			const renderer = this.renderer;

			const toneMapping = renderer.toneMapping;
			const outputColorSpace = renderer.outputColorSpace;

			const context = {
				postProcessing: this,
				onBeforePostProcessing: null,
				onAfterPostProcessing: null
			};

			let outputNode = this.outputNode;

			if ( this.outputColorTransform === true ) {

				outputNode = outputNode.context( context );

				outputNode = renderOutput( outputNode, toneMapping, outputColorSpace );

			} else {

				context.toneMapping = toneMapping;
				context.outputColorSpace = outputColorSpace;

				outputNode = outputNode.context( context );

			}

			this._context = context;

			this._quadMesh.material.fragmentNode = outputNode;
			this._quadMesh.material.needsUpdate = true;

			this.needsUpdate = false;

		}

	}

	/**
	 * When `PostProcessing` is used to apply post processing effects,
	 * the application must use this version of `renderAsync()` inside
	 * its animation loop (not the one from the renderer).
	 *
	 * @async
	 * @return {Promise} A Promise that resolves when the render has been finished.
	 */
	async renderAsync() {

		this._update();

		if ( this._context.onBeforePostProcessing !== null ) this._context.onBeforePostProcessing();

		const renderer = this.renderer;

		const toneMapping = renderer.toneMapping;
		const outputColorSpace = renderer.outputColorSpace;

		renderer.toneMapping = NoToneMapping;
		renderer.outputColorSpace = ColorManagement.workingColorSpace;

		//

		const currentXR = renderer.xr.enabled;
		renderer.xr.enabled = false;

		await this._quadMesh.renderAsync( renderer );

		renderer.xr.enabled = currentXR;

		//

		renderer.toneMapping = toneMapping;
		renderer.outputColorSpace = outputColorSpace;

		if ( this._context.onAfterPostProcessing !== null ) this._context.onAfterPostProcessing();

	}

}
```
</details>

#### Methods

##### `render(): void`

<details><summary>Code</summary>

```ts
render() {

		const renderer = this.renderer;

		this._update();

		if ( this._context.onBeforePostProcessing !== null ) this._context.onBeforePostProcessing();

		const toneMapping = renderer.toneMapping;
		const outputColorSpace = renderer.outputColorSpace;

		renderer.toneMapping = NoToneMapping;
		renderer.outputColorSpace = ColorManagement.workingColorSpace;

		//

		const currentXR = renderer.xr.enabled;
		renderer.xr.enabled = false;

		this._quadMesh.render( renderer );

		renderer.xr.enabled = currentXR;

		//

		renderer.toneMapping = toneMapping;
		renderer.outputColorSpace = outputColorSpace;

		if ( this._context.onAfterPostProcessing !== null ) this._context.onAfterPostProcessing();

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._quadMesh.material.dispose();

	}
```
</details>

##### `_update(): void`

<details><summary>Code</summary>

```ts
_update() {

		if ( this.needsUpdate === true ) {

			const renderer = this.renderer;

			const toneMapping = renderer.toneMapping;
			const outputColorSpace = renderer.outputColorSpace;

			const context = {
				postProcessing: this,
				onBeforePostProcessing: null,
				onAfterPostProcessing: null
			};

			let outputNode = this.outputNode;

			if ( this.outputColorTransform === true ) {

				outputNode = outputNode.context( context );

				outputNode = renderOutput( outputNode, toneMapping, outputColorSpace );

			} else {

				context.toneMapping = toneMapping;
				context.outputColorSpace = outputColorSpace;

				outputNode = outputNode.context( context );

			}

			this._context = context;

			this._quadMesh.material.fragmentNode = outputNode;
			this._quadMesh.material.needsUpdate = true;

			this.needsUpdate = false;

		}

	}
```
</details>

##### `renderAsync(): Promise<any>`

<details><summary>Code</summary>

```ts
async renderAsync() {

		this._update();

		if ( this._context.onBeforePostProcessing !== null ) this._context.onBeforePostProcessing();

		const renderer = this.renderer;

		const toneMapping = renderer.toneMapping;
		const outputColorSpace = renderer.outputColorSpace;

		renderer.toneMapping = NoToneMapping;
		renderer.outputColorSpace = ColorManagement.workingColorSpace;

		//

		const currentXR = renderer.xr.enabled;
		renderer.xr.enabled = false;

		await this._quadMesh.renderAsync( renderer );

		renderer.xr.enabled = currentXR;

		//

		renderer.toneMapping = toneMapping;
		renderer.outputColorSpace = outputColorSpace;

		if ( this._context.onAfterPostProcessing !== null ) this._context.onAfterPostProcessing();

	}
```
</details>


---