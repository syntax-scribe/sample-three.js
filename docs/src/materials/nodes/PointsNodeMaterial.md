[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PointsNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/PointsNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `SpriteNodeMaterial` | `./SpriteNodeMaterial.js` |
| `viewport` | `../../nodes/display/ScreenNode.js` |
| `positionGeometry` | `../../nodes/accessors/Position.js` |
| `positionLocal` | `../../nodes/accessors/Position.js` |
| `positionView` | `../../nodes/accessors/Position.js` |
| `modelViewMatrix` | `../../nodes/accessors/ModelNode.js` |
| `materialPointSize` | `../../nodes/accessors/MaterialNode.js` |
| `rotate` | `../../nodes/utils/RotateNode.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `vec2` | `../../nodes/tsl/TSLBase.js` |
| `vec3` | `../../nodes/tsl/TSLBase.js` |
| `vec4` | `../../nodes/tsl/TSLBase.js` |
| `PointsMaterial` | `../PointsMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `PointsMaterial` | let/var | `new PointsMaterial()` | ✗ |
| `pointSize` | `any` | let/var | `sizeNode !== null ? vec2( sizeNode ) : materialPointSize` | ✗ |


---

## Functions

### `PointsNodeMaterial.setupPositionView(): any`

**Returns:** `any`

**Calls:**

- `modelViewMatrix.mul`
- `vec3 (from ../../nodes/tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
setupPositionView() {

		const { positionNode } = this;

		return modelViewMatrix.mul( vec3( positionNode || positionLocal ) ).xyz;

	}
```
</details>

### `PointsNodeMaterial.setupVertex(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `super.setupVertex`
- `positionGeometry.xy.toVar`
- `viewport.z.div`
- `float (from ../../nodes/tsl/TSLBase.js)`
- `alignedPosition.assign`
- `rotate (from ../../nodes/utils/RotateNode.js)`
- `vec2 (from ../../nodes/tsl/TSLBase.js)`
- `pointSize.mul`
- `pointSize.div`
- `positionView.z.negate`
- `alignedPosition.mulAssign`
- `alignedPosition.div`
- `alignedPosition.y.assign`
- `alignedPosition.y.mul`
- `alignedPosition.mul`
- `mvp.addAssign`
- `vec4 (from ../../nodes/tsl/TSLBase.js)`

**Internal Comments:**
```
// skip further processing if the material is not a node material
// ndc space (x2)
// rotation
// point size (x2)
// scale
// back to clip space (x4)
//clipPos.xy += offset; (x4)
```

<details><summary>Code</summary>

```typescript
setupVertex( builder ) {

		const mvp = super.setupVertex( builder );

		// skip further processing if the material is not a node material

		if ( builder.material.isNodeMaterial !== true ) {

			return mvp;

		}

		// ndc space

		const { rotationNode, scaleNode, sizeNode } = this;

		const alignedPosition = positionGeometry.xy.toVar();
		const aspect = viewport.z.div( viewport.w );

		// rotation

		if ( rotationNode && rotationNode.isNode ) {

			const rotation = float( rotationNode );

			alignedPosition.assign( rotate( alignedPosition, rotation ) );

		}

		// point size

		let pointSize = sizeNode !== null ? vec2( sizeNode ) : materialPointSize;

		if ( this.sizeAttenuation === true ) {

			pointSize = pointSize.mul( pointSize.div( positionView.z.negate() ) );

		}

		// scale

		if ( scaleNode && scaleNode.isNode ) {

			pointSize = pointSize.mul( vec2( scaleNode ) );

		}

		alignedPosition.mulAssign( pointSize.mul( 2 ) );

		alignedPosition.assign( alignedPosition.div( viewport.z ) );
		alignedPosition.y.assign( alignedPosition.y.mul( aspect ) );

		// back to clip space
		alignedPosition.assign( alignedPosition.mul( mvp.w ) );

		//clipPos.xy += offset;
		mvp.addAssign( vec4( alignedPosition, 0, 0 ) );

		return mvp;

	}
```
</details>


---

## Classes

### `PointsNodeMaterial`

<details><summary>Class Code</summary>

```ts
class PointsNodeMaterial extends SpriteNodeMaterial {

	static get type() {

		return 'PointsNodeMaterial';

	}

	/**
	 * Constructs a new points node material.
	 *
	 * @param {Object} [parameters] - The configuration parameter.
	 */
	constructor( parameters ) {

		super();

		/**
		 * This node property provides an additional way to set the point size.
		 *
		 * Note that WebGPU only supports point primitives with 1 pixel size. Consequently,
		 * this node has no effect when the material is used with {@link Points} and a WebGPU
		 * backend. If an application wants to render points with a size larger than 1 pixel,
		 * the material should be used with {@link Sprite} and instancing.
		 *
		 * @type {?Node<vec2>}
		 * @default null
		 */
		this.sizeNode = null;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isPointsNodeMaterial = true;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	setupPositionView() {

		const { positionNode } = this;

		return modelViewMatrix.mul( vec3( positionNode || positionLocal ) ).xyz;

	}

	setupVertex( builder ) {

		const mvp = super.setupVertex( builder );

		// skip further processing if the material is not a node material

		if ( builder.material.isNodeMaterial !== true ) {

			return mvp;

		}

		// ndc space

		const { rotationNode, scaleNode, sizeNode } = this;

		const alignedPosition = positionGeometry.xy.toVar();
		const aspect = viewport.z.div( viewport.w );

		// rotation

		if ( rotationNode && rotationNode.isNode ) {

			const rotation = float( rotationNode );

			alignedPosition.assign( rotate( alignedPosition, rotation ) );

		}

		// point size

		let pointSize = sizeNode !== null ? vec2( sizeNode ) : materialPointSize;

		if ( this.sizeAttenuation === true ) {

			pointSize = pointSize.mul( pointSize.div( positionView.z.negate() ) );

		}

		// scale

		if ( scaleNode && scaleNode.isNode ) {

			pointSize = pointSize.mul( vec2( scaleNode ) );

		}

		alignedPosition.mulAssign( pointSize.mul( 2 ) );

		alignedPosition.assign( alignedPosition.div( viewport.z ) );
		alignedPosition.y.assign( alignedPosition.y.mul( aspect ) );

		// back to clip space
		alignedPosition.assign( alignedPosition.mul( mvp.w ) );

		//clipPos.xy += offset;
		mvp.addAssign( vec4( alignedPosition, 0, 0 ) );

		return mvp;

	}

	/**
	 * Whether alpha to coverage should be used or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get alphaToCoverage() {

		return this._useAlphaToCoverage;

	}

	set alphaToCoverage( value ) {

		if ( this._useAlphaToCoverage !== value ) {

			this._useAlphaToCoverage = value;
			this.needsUpdate = true;

		}

	}

}
```
</details>

#### Methods

##### `setupPositionView(): any`

<details><summary>Code</summary>

```ts
setupPositionView() {

		const { positionNode } = this;

		return modelViewMatrix.mul( vec3( positionNode || positionLocal ) ).xyz;

	}
```
</details>

##### `setupVertex(builder: any): any`

<details><summary>Code</summary>

```ts
setupVertex( builder ) {

		const mvp = super.setupVertex( builder );

		// skip further processing if the material is not a node material

		if ( builder.material.isNodeMaterial !== true ) {

			return mvp;

		}

		// ndc space

		const { rotationNode, scaleNode, sizeNode } = this;

		const alignedPosition = positionGeometry.xy.toVar();
		const aspect = viewport.z.div( viewport.w );

		// rotation

		if ( rotationNode && rotationNode.isNode ) {

			const rotation = float( rotationNode );

			alignedPosition.assign( rotate( alignedPosition, rotation ) );

		}

		// point size

		let pointSize = sizeNode !== null ? vec2( sizeNode ) : materialPointSize;

		if ( this.sizeAttenuation === true ) {

			pointSize = pointSize.mul( pointSize.div( positionView.z.negate() ) );

		}

		// scale

		if ( scaleNode && scaleNode.isNode ) {

			pointSize = pointSize.mul( vec2( scaleNode ) );

		}

		alignedPosition.mulAssign( pointSize.mul( 2 ) );

		alignedPosition.assign( alignedPosition.div( viewport.z ) );
		alignedPosition.y.assign( alignedPosition.y.mul( aspect ) );

		// back to clip space
		alignedPosition.assign( alignedPosition.mul( mvp.w ) );

		//clipPos.xy += offset;
		mvp.addAssign( vec4( alignedPosition, 0, 0 ) );

		return mvp;

	}
```
</details>


---