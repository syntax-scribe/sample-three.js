[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PointShadowNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 19 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/PointShadowNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ShadowNode` | `./ShadowNode.js` |
| `uniform` | `../core/UniformNode.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |
| `If` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `reference` | `../accessors/ReferenceNode.js` |
| `texture` | `../accessors/TextureNode.js` |
| `max` | `../math/MathNode.js` |
| `abs` | `../math/MathNode.js` |
| `sign` | `../math/MathNode.js` |
| `sub` | `../math/OperatorNode.js` |
| `div` | `../math/OperatorNode.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector4` | `../../math/Vector4.js` |
| `Color` | `../../math/Color.js` |
| `BasicShadowMap` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_clearColor` | `Color` | let/var | `new Color()` | ✗ |
| `_viewport` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `_viewportSize` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_shadowMapSize` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `previousAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `x` | `number` | let/var | `_viewportSize.x * viewport.x` | ✗ |
| `y` | `number` | let/var | `_shadowMapSize.y - _viewportSize.y - ( _viewportSize.y * viewport.y )` | ✗ |


---

## Functions

### `PointShadowNode.getShadowFilterFn(type: number): Function`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return point light shadow specific
	 * filtering functions.
	 *
	 * @param {number} type - The shadow type.
	 * @return {Function} The filtering function.
	 */
```

**Parameters:**

- **`type`** `number`

**Returns:** `Function`

<details><summary>Code</summary>

```typescript
getShadowFilterFn( type ) {

		return type === BasicShadowMap ? BasicPointShadowFilter : PointShadowFilter;

	}
```
</details>

### `PointShadowNode.setupShadowCoord(builder: NodeBuilder, shadowPosition: any): any`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation so the unaltered shadow position is used.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Node<vec3>} shadowPosition - A node representing the shadow position.
	 * @return {Node<vec3>} The shadow coordinates.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`shadowPosition`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
setupShadowCoord( builder, shadowPosition ) {

		return shadowPosition;

	}
```
</details>

### `PointShadowNode.setupShadowFilter(builder: NodeBuilder, { filterFn, shadowTexture, depthTexture, shadowCoord, shadow }: any): any`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to only use point light specific
	 * shadow filter functions.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Object} inputs - A configuration object that defines the shadow filtering.
	 * @param {Function} inputs.filterFn - This function defines the filtering type of the shadow map e.g. PCF.
	 * @param {Texture} inputs.shadowTexture - A reference to the shadow map's texture.
	 * @param {DepthTexture} inputs.depthTexture - A reference to the shadow map's texture data.
	 * @param {Node<vec3>} inputs.shadowCoord - Shadow coordinates which are used to sample from the shadow map.
	 * @param {LightShadow} inputs.shadow - The light shadow.
	 * @return {Node<float>} The result node of the shadow filtering.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`{ filterFn, shadowTexture, depthTexture, shadowCoord, shadow }`** `any`

**Returns:** `any`

**Calls:**

- `pointShadowFilter`

<details><summary>Code</summary>

```typescript
setupShadowFilter( builder, { filterFn, shadowTexture, depthTexture, shadowCoord, shadow } ) {

		return pointShadowFilter( { filterFn, shadowTexture, depthTexture, shadowCoord, shadow } );

	}
```
</details>

### `PointShadowNode.renderShadow(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation with point light specific
	 * rendering code.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `shadow.getFrameExtents`
- `_shadowMapSize.copy`
- `_shadowMapSize.multiply`
- `shadowMap.setSize`
- `_viewportSize.copy`
- `renderer.getClearColor`
- `renderer.getClearAlpha`
- `renderer.setClearColor`
- `renderer.clear`
- `shadow.getViewportCount`
- `shadow.getViewport`
- `_viewport.set`
- `shadowMap.viewport.copy`
- `shadow.updateMatrices`
- `renderer.render`

**Internal Comments:**
```
// (x6)
```

<details><summary>Code</summary>

```typescript
renderShadow( frame ) {

		const { shadow, shadowMap, light } = this;
		const { renderer, scene } = frame;

		const shadowFrameExtents = shadow.getFrameExtents();

		_shadowMapSize.copy( shadow.mapSize );
		_shadowMapSize.multiply( shadowFrameExtents );

		shadowMap.setSize( _shadowMapSize.width, _shadowMapSize.height );

		_viewportSize.copy( shadow.mapSize );

		//

		const previousAutoClear = renderer.autoClear;

		const previousClearColor = renderer.getClearColor( _clearColor );
		const previousClearAlpha = renderer.getClearAlpha();

		renderer.autoClear = false;
		renderer.setClearColor( shadow.clearColor, shadow.clearAlpha );
		renderer.clear();

		const viewportCount = shadow.getViewportCount();

		for ( let vp = 0; vp < viewportCount; vp ++ ) {

			const viewport = shadow.getViewport( vp );

			const x = _viewportSize.x * viewport.x;
			const y = _shadowMapSize.y - _viewportSize.y - ( _viewportSize.y * viewport.y );

			_viewport.set(
				x,
				y,
				_viewportSize.x * viewport.z,
				_viewportSize.y * viewport.w
			);

			shadowMap.viewport.copy( _viewport );

			shadow.updateMatrices( light, vp );

			renderer.render( scene, shadow.camera );

		}

		//

		renderer.autoClear = previousAutoClear;
		renderer.setClearColor( previousClearColor, previousClearAlpha );

	}
```
</details>

### `pointShadow(light: PointLight, shadow: PointLightShadow): PointShadowNode`

**Parameters:**

- **`light`** `PointLight`
- **`shadow`** `PointLightShadow`

**Returns:** `PointShadowNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( light, shadow ) => nodeObject( new PointShadowNode( light, shadow ) )
```
</details>


---

## Classes

### `PointShadowNode`

<details><summary>Class Code</summary>

```ts
class PointShadowNode extends ShadowNode {

	static get type() {

		return 'PointShadowNode';

	}

	/**
	 * Constructs a new point shadow node.
	 *
	 * @param {PointLight} light - The shadow casting point light.
	 * @param {?PointLightShadow} [shadow=null] - An optional point light shadow.
	 */
	constructor( light, shadow = null ) {

		super( light, shadow );

	}

	/**
	 * Overwrites the default implementation to return point light shadow specific
	 * filtering functions.
	 *
	 * @param {number} type - The shadow type.
	 * @return {Function} The filtering function.
	 */
	getShadowFilterFn( type ) {

		return type === BasicShadowMap ? BasicPointShadowFilter : PointShadowFilter;

	}

	/**
	 * Overwrites the default implementation so the unaltered shadow position is used.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Node<vec3>} shadowPosition - A node representing the shadow position.
	 * @return {Node<vec3>} The shadow coordinates.
	 */
	setupShadowCoord( builder, shadowPosition ) {

		return shadowPosition;

	}

	/**
	 * Overwrites the default implementation to only use point light specific
	 * shadow filter functions.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Object} inputs - A configuration object that defines the shadow filtering.
	 * @param {Function} inputs.filterFn - This function defines the filtering type of the shadow map e.g. PCF.
	 * @param {Texture} inputs.shadowTexture - A reference to the shadow map's texture.
	 * @param {DepthTexture} inputs.depthTexture - A reference to the shadow map's texture data.
	 * @param {Node<vec3>} inputs.shadowCoord - Shadow coordinates which are used to sample from the shadow map.
	 * @param {LightShadow} inputs.shadow - The light shadow.
	 * @return {Node<float>} The result node of the shadow filtering.
	 */
	setupShadowFilter( builder, { filterFn, shadowTexture, depthTexture, shadowCoord, shadow } ) {

		return pointShadowFilter( { filterFn, shadowTexture, depthTexture, shadowCoord, shadow } );

	}

	/**
	 * Overwrites the default implementation with point light specific
	 * rendering code.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	renderShadow( frame ) {

		const { shadow, shadowMap, light } = this;
		const { renderer, scene } = frame;

		const shadowFrameExtents = shadow.getFrameExtents();

		_shadowMapSize.copy( shadow.mapSize );
		_shadowMapSize.multiply( shadowFrameExtents );

		shadowMap.setSize( _shadowMapSize.width, _shadowMapSize.height );

		_viewportSize.copy( shadow.mapSize );

		//

		const previousAutoClear = renderer.autoClear;

		const previousClearColor = renderer.getClearColor( _clearColor );
		const previousClearAlpha = renderer.getClearAlpha();

		renderer.autoClear = false;
		renderer.setClearColor( shadow.clearColor, shadow.clearAlpha );
		renderer.clear();

		const viewportCount = shadow.getViewportCount();

		for ( let vp = 0; vp < viewportCount; vp ++ ) {

			const viewport = shadow.getViewport( vp );

			const x = _viewportSize.x * viewport.x;
			const y = _shadowMapSize.y - _viewportSize.y - ( _viewportSize.y * viewport.y );

			_viewport.set(
				x,
				y,
				_viewportSize.x * viewport.z,
				_viewportSize.y * viewport.w
			);

			shadowMap.viewport.copy( _viewport );

			shadow.updateMatrices( light, vp );

			renderer.render( scene, shadow.camera );

		}

		//

		renderer.autoClear = previousAutoClear;
		renderer.setClearColor( previousClearColor, previousClearAlpha );

	}

}
```
</details>

#### Methods

##### `getShadowFilterFn(type: number): Function`

<details><summary>Code</summary>

```ts
getShadowFilterFn( type ) {

		return type === BasicShadowMap ? BasicPointShadowFilter : PointShadowFilter;

	}
```
</details>

##### `setupShadowCoord(builder: NodeBuilder, shadowPosition: any): any`

<details><summary>Code</summary>

```ts
setupShadowCoord( builder, shadowPosition ) {

		return shadowPosition;

	}
```
</details>

##### `setupShadowFilter(builder: NodeBuilder, { filterFn, shadowTexture, depthTexture, shadowCoord, shadow }: any): any`

<details><summary>Code</summary>

```ts
setupShadowFilter( builder, { filterFn, shadowTexture, depthTexture, shadowCoord, shadow } ) {

		return pointShadowFilter( { filterFn, shadowTexture, depthTexture, shadowCoord, shadow } );

	}
```
</details>

##### `renderShadow(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
renderShadow( frame ) {

		const { shadow, shadowMap, light } = this;
		const { renderer, scene } = frame;

		const shadowFrameExtents = shadow.getFrameExtents();

		_shadowMapSize.copy( shadow.mapSize );
		_shadowMapSize.multiply( shadowFrameExtents );

		shadowMap.setSize( _shadowMapSize.width, _shadowMapSize.height );

		_viewportSize.copy( shadow.mapSize );

		//

		const previousAutoClear = renderer.autoClear;

		const previousClearColor = renderer.getClearColor( _clearColor );
		const previousClearAlpha = renderer.getClearAlpha();

		renderer.autoClear = false;
		renderer.setClearColor( shadow.clearColor, shadow.clearAlpha );
		renderer.clear();

		const viewportCount = shadow.getViewportCount();

		for ( let vp = 0; vp < viewportCount; vp ++ ) {

			const viewport = shadow.getViewport( vp );

			const x = _viewportSize.x * viewport.x;
			const y = _shadowMapSize.y - _viewportSize.y - ( _viewportSize.y * viewport.y );

			_viewport.set(
				x,
				y,
				_viewportSize.x * viewport.z,
				_viewportSize.y * viewport.w
			);

			shadowMap.viewport.copy( _viewport );

			shadow.updateMatrices( light, vp );

			renderer.render( scene, shadow.camera );

		}

		//

		renderer.autoClear = previousAutoClear;
		renderer.setClearColor( previousClearColor, previousClearAlpha );

	}
```
</details>


---