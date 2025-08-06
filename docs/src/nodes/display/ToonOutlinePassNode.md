[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ToonOutlinePassNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/ToonOutlinePassNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `float` | `../tsl/TSLBase.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `normalize` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |
| `Color` | `../../math/Color.js` |
| `NodeMaterial` | `../../materials/nodes/NodeMaterial.js` |
| `cameraProjectionMatrix` | `../../nodes/accessors/Camera.js` |
| `modelViewMatrix` | `../../nodes/accessors/ModelNode.js` |
| `positionLocal` | `../../nodes/accessors/Position.js` |
| `normalLocal` | `../../nodes/accessors/Normal.js` |
| `BackSide` | `../../constants.js` |
| `PassNode` | `./PassNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `NodeMaterial` | let/var | `new NodeMaterial()` | ✗ |


---

## Functions

### `ToonOutlinePassNode.updateBefore(frame: any): void`

**Parameters:**

- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getRenderObjectFunction`
- `renderer.setRenderObjectFunction`
- `this._getOutlineMaterial`
- `renderer.renderObject`
- `super.updateBefore`

**Internal Comments:**
```
// only render outline for supported materials
// default (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;

		const currentRenderObjectFunction = renderer.getRenderObjectFunction();

		renderer.setRenderObjectFunction( ( object, scene, camera, geometry, material, group, lightsNode, clippingContext ) => {

			// only render outline for supported materials

			if ( material.isMeshToonMaterial || material.isMeshToonNodeMaterial ) {

				if ( material.wireframe === false ) {

					const outlineMaterial = this._getOutlineMaterial( material );
					renderer.renderObject( object, scene, camera, geometry, outlineMaterial, group, lightsNode, clippingContext );

				}

			}

			// default

			renderer.renderObject( object, scene, camera, geometry, material, group, lightsNode, clippingContext );

		} );

		super.updateBefore( frame );

		renderer.setRenderObjectFunction( currentRenderObjectFunction );

	}
```
</details>

### `ToonOutlinePassNode._createMaterial(): NodeMaterial`

**JSDoc:**
```typescript
/**
	 * Creates the material used for outline rendering.
	 *
	 * @private
	 * @return {NodeMaterial} The outline material.
	 */
```

**Returns:** `NodeMaterial`

**Calls:**

- `normalLocal.negate`
- `cameraProjectionMatrix.mul`
- `float (from ../tsl/TSLBase.js)`
- `mvp.mul`
- `vec4 (from ../tsl/TSLBase.js)`
- `positionLocal.add`
- `normalize (from ../tsl/TSLBase.js)`
- `pos.sub`
- `pos.add`
- `norm.mul( this.thicknessNode ).mul( pos.w ).mul`

**Internal Comments:**
```
// vertex node (x2)
// color node (x4)
```

<details><summary>Code</summary>

```typescript
_createMaterial() {

		const material = new NodeMaterial();
		material.isMeshToonOutlineMaterial = true;
		material.name = 'Toon_Outline';
		material.side = BackSide;

		// vertex node

		const outlineNormal = normalLocal.negate();
		const mvp = cameraProjectionMatrix.mul( modelViewMatrix );

		const ratio = float( 1.0 ); // TODO: support outline thickness ratio for each vertex
		const pos = mvp.mul( vec4( positionLocal, 1.0 ) );
		const pos2 = mvp.mul( vec4( positionLocal.add( outlineNormal ), 1.0 ) );
		const norm = normalize( pos.sub( pos2 ) ); // NOTE: subtract pos2 from pos because BackSide objectNormal is negative

		material.vertexNode = pos.add( norm.mul( this.thicknessNode ).mul( pos.w ).mul( ratio ) );

		// color node

		material.colorNode = vec4( this.colorNode, this.alphaNode );

		return material;

	}
```
</details>

### `ToonOutlinePassNode._getOutlineMaterial(originalMaterial: any): NodeMaterial`

**JSDoc:**
```typescript
/**
	 * For the given toon material, this method returns a corresponding
	 * outline material.
	 *
	 * @private
	 * @param {(MeshToonMaterial|MeshToonNodeMaterial)} originalMaterial - The toon material.
	 * @return {NodeMaterial} The outline material.
	 */
```

**Parameters:**

- **`originalMaterial`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `this._materialCache.get`
- `this._createMaterial`
- `this._materialCache.set`

<details><summary>Code</summary>

```typescript
_getOutlineMaterial( originalMaterial ) {

		let outlineMaterial = this._materialCache.get( originalMaterial );

		if ( outlineMaterial === undefined ) {

			outlineMaterial = this._createMaterial();

			this._materialCache.set( originalMaterial, outlineMaterial );

		}

		return outlineMaterial;

	}
```
</details>

### `toonOutlinePass(scene: Scene, camera: Camera, color: Color, thickness: number, alpha: number): ToonOutlinePassNode`

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`
- **`color`** `Color`
- **`thickness`** `number`
- **`alpha`** `number`

**Returns:** `ToonOutlinePassNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( scene, camera, color = new Color( 0, 0, 0 ), thickness = 0.003, alpha = 1 ) => nodeObject( new ToonOutlinePassNode( scene, camera, nodeObject( color ), nodeObject( thickness ), nodeObject( alpha ) ) )
```
</details>


---

## Classes

### `ToonOutlinePassNode`

<details><summary>Class Code</summary>

```ts
class ToonOutlinePassNode extends PassNode {

	static get type() {

		return 'ToonOutlinePassNode';

	}

	/**
	 * Constructs a new outline pass node.
	 *
	 * @param {Scene} scene - A reference to the scene.
	 * @param {Camera} camera - A reference to the camera.
	 * @param {Node} colorNode - Defines the outline's color.
	 * @param {Node} thicknessNode - Defines the outline's thickness.
	 * @param {Node} alphaNode - Defines the outline's alpha.
	 */
	constructor( scene, camera, colorNode, thicknessNode, alphaNode ) {

		super( PassNode.COLOR, scene, camera );

		/**
		 * Defines the outline's color.
		 *
		 * @type {Node}
		 */
		this.colorNode = colorNode;

		/**
		 * Defines the outline's thickness.
		 *
		 * @type {Node}
		 */
		this.thicknessNode = thicknessNode;

		/**
		 * Defines the outline's alpha.
		 *
		 * @type {Node}
		 */
		this.alphaNode = alphaNode;

		/**
		 * An internal material cache.
		 *
		 * @private
		 * @type {WeakMap<Material, NodeMaterial>}
		 */
		this._materialCache = new WeakMap();

	}

	updateBefore( frame ) {

		const { renderer } = frame;

		const currentRenderObjectFunction = renderer.getRenderObjectFunction();

		renderer.setRenderObjectFunction( ( object, scene, camera, geometry, material, group, lightsNode, clippingContext ) => {

			// only render outline for supported materials

			if ( material.isMeshToonMaterial || material.isMeshToonNodeMaterial ) {

				if ( material.wireframe === false ) {

					const outlineMaterial = this._getOutlineMaterial( material );
					renderer.renderObject( object, scene, camera, geometry, outlineMaterial, group, lightsNode, clippingContext );

				}

			}

			// default

			renderer.renderObject( object, scene, camera, geometry, material, group, lightsNode, clippingContext );

		} );

		super.updateBefore( frame );

		renderer.setRenderObjectFunction( currentRenderObjectFunction );

	}

	/**
	 * Creates the material used for outline rendering.
	 *
	 * @private
	 * @return {NodeMaterial} The outline material.
	 */
	_createMaterial() {

		const material = new NodeMaterial();
		material.isMeshToonOutlineMaterial = true;
		material.name = 'Toon_Outline';
		material.side = BackSide;

		// vertex node

		const outlineNormal = normalLocal.negate();
		const mvp = cameraProjectionMatrix.mul( modelViewMatrix );

		const ratio = float( 1.0 ); // TODO: support outline thickness ratio for each vertex
		const pos = mvp.mul( vec4( positionLocal, 1.0 ) );
		const pos2 = mvp.mul( vec4( positionLocal.add( outlineNormal ), 1.0 ) );
		const norm = normalize( pos.sub( pos2 ) ); // NOTE: subtract pos2 from pos because BackSide objectNormal is negative

		material.vertexNode = pos.add( norm.mul( this.thicknessNode ).mul( pos.w ).mul( ratio ) );

		// color node

		material.colorNode = vec4( this.colorNode, this.alphaNode );

		return material;

	}

	/**
	 * For the given toon material, this method returns a corresponding
	 * outline material.
	 *
	 * @private
	 * @param {(MeshToonMaterial|MeshToonNodeMaterial)} originalMaterial - The toon material.
	 * @return {NodeMaterial} The outline material.
	 */
	_getOutlineMaterial( originalMaterial ) {

		let outlineMaterial = this._materialCache.get( originalMaterial );

		if ( outlineMaterial === undefined ) {

			outlineMaterial = this._createMaterial();

			this._materialCache.set( originalMaterial, outlineMaterial );

		}

		return outlineMaterial;

	}

}
```
</details>

#### Methods

##### `updateBefore(frame: any): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;

		const currentRenderObjectFunction = renderer.getRenderObjectFunction();

		renderer.setRenderObjectFunction( ( object, scene, camera, geometry, material, group, lightsNode, clippingContext ) => {

			// only render outline for supported materials

			if ( material.isMeshToonMaterial || material.isMeshToonNodeMaterial ) {

				if ( material.wireframe === false ) {

					const outlineMaterial = this._getOutlineMaterial( material );
					renderer.renderObject( object, scene, camera, geometry, outlineMaterial, group, lightsNode, clippingContext );

				}

			}

			// default

			renderer.renderObject( object, scene, camera, geometry, material, group, lightsNode, clippingContext );

		} );

		super.updateBefore( frame );

		renderer.setRenderObjectFunction( currentRenderObjectFunction );

	}
```
</details>

##### `_createMaterial(): NodeMaterial`

<details><summary>Code</summary>

```ts
_createMaterial() {

		const material = new NodeMaterial();
		material.isMeshToonOutlineMaterial = true;
		material.name = 'Toon_Outline';
		material.side = BackSide;

		// vertex node

		const outlineNormal = normalLocal.negate();
		const mvp = cameraProjectionMatrix.mul( modelViewMatrix );

		const ratio = float( 1.0 ); // TODO: support outline thickness ratio for each vertex
		const pos = mvp.mul( vec4( positionLocal, 1.0 ) );
		const pos2 = mvp.mul( vec4( positionLocal.add( outlineNormal ), 1.0 ) );
		const norm = normalize( pos.sub( pos2 ) ); // NOTE: subtract pos2 from pos because BackSide objectNormal is negative

		material.vertexNode = pos.add( norm.mul( this.thicknessNode ).mul( pos.w ).mul( ratio ) );

		// color node

		material.colorNode = vec4( this.colorNode, this.alphaNode );

		return material;

	}
```
</details>

##### `_getOutlineMaterial(originalMaterial: any): NodeMaterial`

<details><summary>Code</summary>

```ts
_getOutlineMaterial( originalMaterial ) {

		let outlineMaterial = this._materialCache.get( originalMaterial );

		if ( outlineMaterial === undefined ) {

			outlineMaterial = this._createMaterial();

			this._materialCache.set( originalMaterial, outlineMaterial );

		}

		return outlineMaterial;

	}
```
</details>


---