[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RendererUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/common/RendererUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `../../math/Color.js` |


---

## Functions

### `saveRendererState(renderer: Renderer, state: any): any`

**JSDoc:**
```typescript
/**
 * Saves the state of the given renderer and stores it into the given state object.
 *
 * If not state object is provided, the function creates one.
 *
 * @function
 * @param {Renderer} renderer - The renderer.
 * @param {Object} [state={}] - The state.
 * @return {Object} The state.
 */
```

**Parameters:**

- **`renderer`** `Renderer`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `renderer.getRenderTarget`
- `renderer.getActiveCubeFace`
- `renderer.getActiveMipmapLevel`
- `renderer.getRenderObjectFunction`
- `renderer.getPixelRatio`
- `renderer.getMRT`
- `renderer.getClearColor`
- `renderer.getClearAlpha`
- `renderer.getScissorTest`

<details><summary>Code</summary>

```typescript
export function saveRendererState( renderer, state = {} ) {

	state.toneMapping = renderer.toneMapping;
	state.toneMappingExposure = renderer.toneMappingExposure;
	state.outputColorSpace = renderer.outputColorSpace;
	state.renderTarget = renderer.getRenderTarget();
	state.activeCubeFace = renderer.getActiveCubeFace();
	state.activeMipmapLevel = renderer.getActiveMipmapLevel();
	state.renderObjectFunction = renderer.getRenderObjectFunction();
	state.pixelRatio = renderer.getPixelRatio();
	state.mrt = renderer.getMRT();
	state.clearColor = renderer.getClearColor( state.clearColor || new Color() );
	state.clearAlpha = renderer.getClearAlpha();
	state.autoClear = renderer.autoClear;
	state.scissorTest = renderer.getScissorTest();

	return state;

}
```
</details>

### `resetRendererState(renderer: Renderer, state: any): any`

**JSDoc:**
```typescript
/**
 * Saves the state of the given renderer and stores it into the given state object.
 * Besides, the function also resets the state of the renderer to its default values.
 *
 * If not state object is provided, the function creates one.
 *
 * @function
 * @param {Renderer} renderer - The renderer.
 * @param {Object} [state={}] - The state.
 * @return {Object} The state.
 */
```

**Parameters:**

- **`renderer`** `Renderer`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `saveRendererState`
- `renderer.setMRT`
- `renderer.setRenderObjectFunction`
- `renderer.setClearColor`

<details><summary>Code</summary>

```typescript
export function resetRendererState( renderer, state ) {

	state = saveRendererState( renderer, state );

	renderer.setMRT( null );
	renderer.setRenderObjectFunction( null );
	renderer.setClearColor( 0x000000, 1 );
	renderer.autoClear = true;

	return state;

}
```
</details>

### `restoreRendererState(renderer: Renderer, state: any): void`

**JSDoc:**
```typescript
/**
 * Restores the state of the given renderer from the given state object.
 *
 * @function
 * @param {Renderer} renderer - The renderer.
 * @param {Object} state - The state to restore.
 */
```

**Parameters:**

- **`renderer`** `Renderer`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `renderer.setRenderTarget`
- `renderer.setRenderObjectFunction`
- `renderer.setPixelRatio`
- `renderer.setMRT`
- `renderer.setClearColor`
- `renderer.setScissorTest`

<details><summary>Code</summary>

```typescript
export function restoreRendererState( renderer, state ) {

	renderer.toneMapping = state.toneMapping;
	renderer.toneMappingExposure = state.toneMappingExposure;
	renderer.outputColorSpace = state.outputColorSpace;
	renderer.setRenderTarget( state.renderTarget, state.activeCubeFace, state.activeMipmapLevel );
	renderer.setRenderObjectFunction( state.renderObjectFunction );
	renderer.setPixelRatio( state.pixelRatio );
	renderer.setMRT( state.mrt );
	renderer.setClearColor( state.clearColor, state.clearAlpha );
	renderer.autoClear = state.autoClear;
	renderer.setScissorTest( state.scissorTest );

}
```
</details>

### `saveSceneState(scene: Scene, state: any): any`

**JSDoc:**
```typescript
/**
 * Saves the state of the given scene and stores it into the given state object.
 *
 * If not state object is provided, the function creates one.
 *
 * @function
 * @param {Scene} scene - The scene.
 * @param {Object} [state={}] - The state.
 * @return {Object} The state.
 */
```

**Parameters:**

- **`scene`** `Scene`
- **`state`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
export function saveSceneState( scene, state = {} ) {

	state.background = scene.background;
	state.backgroundNode = scene.backgroundNode;
	state.overrideMaterial = scene.overrideMaterial;

	return state;

}
```
</details>

### `resetSceneState(scene: Scene, state: any): any`

**JSDoc:**
```typescript
/**
 * Saves the state of the given scene and stores it into the given state object.
 * Besides, the function also resets the state of the scene to its default values.
 *
 * If not state object is provided, the function creates one.
 *
 * @function
 * @param {Scene} scene - The scene.
 * @param {Object} [state={}] - The state.
 * @return {Object} The state.
 */
```

**Parameters:**

- **`scene`** `Scene`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `saveSceneState`

<details><summary>Code</summary>

```typescript
export function resetSceneState( scene, state ) {

	state = saveSceneState( scene, state );

	scene.background = null;
	scene.backgroundNode = null;
	scene.overrideMaterial = null;

	return state;

}
```
</details>

### `restoreSceneState(scene: Scene, state: any): void`

**JSDoc:**
```typescript
/**
 * Restores the state of the given scene from the given state object.
 *
 * @function
 * @param {Scene} scene - The scene.
 * @param {Object} state - The state to restore.
 */
```

**Parameters:**

- **`scene`** `Scene`
- **`state`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
export function restoreSceneState( scene, state ) {

	scene.background = state.background;
	scene.backgroundNode = state.backgroundNode;
	scene.overrideMaterial = state.overrideMaterial;

}
```
</details>

### `saveRendererAndSceneState(renderer: Renderer, scene: Scene, state: any): any`

**JSDoc:**
```typescript
/**
 * Saves the state of the given renderer and scene and stores it into the given state object.
 *
 * If not state object is provided, the function creates one.
 *
 * @function
 * @param {Renderer} renderer - The renderer.
 * @param {Scene} scene - The scene.
 * @param {Object} [state={}] - The state.
 * @return {Object} The state.
 */
```

**Parameters:**

- **`renderer`** `Renderer`
- **`scene`** `Scene`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `saveRendererState`
- `saveSceneState`

<details><summary>Code</summary>

```typescript
export function saveRendererAndSceneState( renderer, scene, state = {} ) {

	state = saveRendererState( renderer, state );
	state = saveSceneState( scene, state );

	return state;

}
```
</details>

### `resetRendererAndSceneState(renderer: Renderer, scene: Scene, state: any): any`

**JSDoc:**
```typescript
/**
 * Saves the state of the given renderer and scene and stores it into the given state object.
 * Besides, the function also resets the state of the renderer and scene to its default values.
 *
 * If not state object is provided, the function creates one.
 *
 * @function
 * @param {Renderer} renderer - The renderer.
 * @param {Scene} scene - The scene.
 * @param {Object} [state={}] - The state.
 * @return {Object} The state.
 */
```

**Parameters:**

- **`renderer`** `Renderer`
- **`scene`** `Scene`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `resetRendererState`
- `resetSceneState`

<details><summary>Code</summary>

```typescript
export function resetRendererAndSceneState( renderer, scene, state ) {

	state = resetRendererState( renderer, state );
	state = resetSceneState( scene, state );

	return state;

}
```
</details>

### `restoreRendererAndSceneState(renderer: Renderer, scene: Scene, state: any): void`

**JSDoc:**
```typescript
/**
 * Restores the state of the given renderer and scene from the given state object.
 *
 * @function
 * @param {Renderer} renderer - The renderer.
 * @param {Scene} scene - The scene.
 * @param {Object} state - The state to restore.
 */
```

**Parameters:**

- **`renderer`** `Renderer`
- **`scene`** `Scene`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `restoreRendererState`
- `restoreSceneState`

<details><summary>Code</summary>

```typescript
export function restoreRendererAndSceneState( renderer, scene, state ) {

	restoreRendererState( renderer, state );
	restoreSceneState( scene, state );

}
```
</details>


---