[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SpriteNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/SpriteNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `cameraProjectionMatrix` | `../../nodes/accessors/Camera.js` |
| `materialRotation` | `../../nodes/accessors/MaterialNode.js` |
| `modelViewMatrix` | `../../nodes/accessors/ModelNode.js` |
| `modelWorldMatrix` | `../../nodes/accessors/ModelNode.js` |
| `positionGeometry` | `../../nodes/accessors/Position.js` |
| `rotate` | `../../nodes/utils/RotateNode.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `vec2` | `../../nodes/tsl/TSLBase.js` |
| `vec3` | `../../nodes/tsl/TSLBase.js` |
| `vec4` | `../../nodes/tsl/TSLBase.js` |
| `SpriteMaterial` | `../SpriteMaterial.js` |
| `reference` | `../../nodes/accessors/ReferenceBaseNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `SpriteMaterial` | let/var | `new SpriteMaterial()` | ✗ |
| `sizeAttenuation` | `boolean` | let/var | `this.sizeAttenuation` | ✗ |
| `alignedPosition` | `any` | let/var | `positionGeometry.xy` | ✗ |


---

## Functions

### `SpriteNodeMaterial.setupPositionView(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * Setups the position node in view space. This method implements
	 * the sprite specific vertex shader.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node<vec3>} The position in view space.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

**Calls:**

- `modelViewMatrix.mul`
- `vec3 (from ../../nodes/tsl/TSLBase.js)`
- `vec2 (from ../../nodes/tsl/TSLBase.js)`
- `modelWorldMatrix[ 0 ].xyz.length`
- `modelWorldMatrix[ 1 ].xyz.length`
- `scale.mul`
- `mvPosition.z.negate`
- `float( 2.0 ).div`
- `cameraProjectionMatrix.element( 1 ).element`
- `orthoScale.mul`
- `reference (from ../../nodes/accessors/ReferenceBaseNode.js)`
- `alignedPosition.sub`
- `center.sub`
- `alignedPosition.mul`
- `float (from ../../nodes/tsl/TSLBase.js)`
- `rotate (from ../../nodes/utils/RotateNode.js)`
- `vec4 (from ../../nodes/tsl/TSLBase.js)`
- `mvPosition.xy.add`

<details><summary>Code</summary>

```typescript
setupPositionView( builder ) {

		const { object, camera } = builder;

		const sizeAttenuation = this.sizeAttenuation;

		const { positionNode, rotationNode, scaleNode } = this;

		const mvPosition = modelViewMatrix.mul( vec3( positionNode || 0 ) );

		let scale = vec2( modelWorldMatrix[ 0 ].xyz.length(), modelWorldMatrix[ 1 ].xyz.length() );

		if ( scaleNode !== null ) {

			scale = scale.mul( vec2( scaleNode ) );

		}

		if ( sizeAttenuation === false ) {

			if ( camera.isPerspectiveCamera ) {

				scale = scale.mul( mvPosition.z.negate() );

			} else {

				const orthoScale = float( 2.0 ).div( cameraProjectionMatrix.element( 1 ).element( 1 ) );
				scale = scale.mul( orthoScale.mul( 2 ) );

			}

		}

		let alignedPosition = positionGeometry.xy;

		if ( object.center && object.center.isVector2 === true ) {

			const center = reference( 'center', 'vec2', object );

			alignedPosition = alignedPosition.sub( center.sub( 0.5 ) );

		}

		alignedPosition = alignedPosition.mul( scale );

		const rotation = float( rotationNode || materialRotation );

		const rotatedPosition = rotate( alignedPosition, rotation );

		return vec4( mvPosition.xy.add( rotatedPosition ), mvPosition.zw );

	}
```
</details>

### `SpriteNodeMaterial.copy(source: any): NodeMaterial`

**Parameters:**

- **`source`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		this.positionNode = source.positionNode;
		this.rotationNode = source.rotationNode;
		this.scaleNode = source.scaleNode;

		return super.copy( source );

	}
```
</details>


---

## Classes

### `SpriteNodeMaterial`

<details><summary>Class Code</summary>

```ts
class SpriteNodeMaterial extends NodeMaterial {

	static get type() {

		return 'SpriteNodeMaterial';

	}

	/**
	 * Constructs a new sprite node material.
	 *
	 * @param {Object} [parameters] - The configuration parameter.
	 */
	constructor( parameters ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSpriteNodeMaterial = true;

		this._useSizeAttenuation = true;

		/**
		 * This property makes it possible to define the position of the sprite with a
		 * node. That can be useful when the material is used with instanced rendering
		 * and node data are defined with an instanced attribute node:
		 * ```js
		 * const positionAttribute = new InstancedBufferAttribute( new Float32Array( positions ), 3 );
		 * material.positionNode = instancedBufferAttribute( positionAttribute );
		 * ```
		 * Another possibility is to compute the instanced data with a compute shader:
		 * ```js
		 * const positionBuffer = instancedArray( particleCount, 'vec3' );
		 * particleMaterial.positionNode = positionBuffer.toAttribute();
		 * ```
		 *
		 * @type {?Node<vec2>}
		 * @default null
		 */
		this.positionNode = null;

		/**
		 * The rotation of sprite materials is by default inferred from the `rotation`,
		 * property. This node property allows to overwrite the default and define
		 * the rotation with a node instead.
		 *
		 * If you don't want to overwrite the rotation but modify the existing
		 * value instead, use {@link materialRotation}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.rotationNode = null;

		/**
		 * This node property provides an additional way to scale sprites next to
		 * `Object3D.scale`. The scale transformation based in `Object3D.scale`
		 * is multiplied with the scale value of this node in the vertex shader.
		 *
		 * @type {?Node<vec2>}
		 * @default null
		 */
		this.scaleNode = null;

		/**
		 * In Sprites, the transparent property is enabled by default.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.transparent = true;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	/**
	 * Setups the position node in view space. This method implements
	 * the sprite specific vertex shader.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node<vec3>} The position in view space.
	 */
	setupPositionView( builder ) {

		const { object, camera } = builder;

		const sizeAttenuation = this.sizeAttenuation;

		const { positionNode, rotationNode, scaleNode } = this;

		const mvPosition = modelViewMatrix.mul( vec3( positionNode || 0 ) );

		let scale = vec2( modelWorldMatrix[ 0 ].xyz.length(), modelWorldMatrix[ 1 ].xyz.length() );

		if ( scaleNode !== null ) {

			scale = scale.mul( vec2( scaleNode ) );

		}

		if ( sizeAttenuation === false ) {

			if ( camera.isPerspectiveCamera ) {

				scale = scale.mul( mvPosition.z.negate() );

			} else {

				const orthoScale = float( 2.0 ).div( cameraProjectionMatrix.element( 1 ).element( 1 ) );
				scale = scale.mul( orthoScale.mul( 2 ) );

			}

		}

		let alignedPosition = positionGeometry.xy;

		if ( object.center && object.center.isVector2 === true ) {

			const center = reference( 'center', 'vec2', object );

			alignedPosition = alignedPosition.sub( center.sub( 0.5 ) );

		}

		alignedPosition = alignedPosition.mul( scale );

		const rotation = float( rotationNode || materialRotation );

		const rotatedPosition = rotate( alignedPosition, rotation );

		return vec4( mvPosition.xy.add( rotatedPosition ), mvPosition.zw );

	}

	copy( source ) {

		this.positionNode = source.positionNode;
		this.rotationNode = source.rotationNode;
		this.scaleNode = source.scaleNode;

		return super.copy( source );

	}

	/**
	 * Whether to use size attenuation or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get sizeAttenuation() {

		return this._useSizeAttenuation;

	}

	set sizeAttenuation( value ) {

		if ( this._useSizeAttenuation !== value ) {

			this._useSizeAttenuation = value;
			this.needsUpdate = true;

		}

	}

}
```
</details>

#### Methods

##### `setupPositionView(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
setupPositionView( builder ) {

		const { object, camera } = builder;

		const sizeAttenuation = this.sizeAttenuation;

		const { positionNode, rotationNode, scaleNode } = this;

		const mvPosition = modelViewMatrix.mul( vec3( positionNode || 0 ) );

		let scale = vec2( modelWorldMatrix[ 0 ].xyz.length(), modelWorldMatrix[ 1 ].xyz.length() );

		if ( scaleNode !== null ) {

			scale = scale.mul( vec2( scaleNode ) );

		}

		if ( sizeAttenuation === false ) {

			if ( camera.isPerspectiveCamera ) {

				scale = scale.mul( mvPosition.z.negate() );

			} else {

				const orthoScale = float( 2.0 ).div( cameraProjectionMatrix.element( 1 ).element( 1 ) );
				scale = scale.mul( orthoScale.mul( 2 ) );

			}

		}

		let alignedPosition = positionGeometry.xy;

		if ( object.center && object.center.isVector2 === true ) {

			const center = reference( 'center', 'vec2', object );

			alignedPosition = alignedPosition.sub( center.sub( 0.5 ) );

		}

		alignedPosition = alignedPosition.mul( scale );

		const rotation = float( rotationNode || materialRotation );

		const rotatedPosition = rotate( alignedPosition, rotation );

		return vec4( mvPosition.xy.add( rotatedPosition ), mvPosition.zw );

	}
```
</details>

##### `copy(source: any): NodeMaterial`

<details><summary>Code</summary>

```ts
copy( source ) {

		this.positionNode = source.positionNode;
		this.rotationNode = source.rotationNode;
		this.scaleNode = source.scaleNode;

		return super.copy( source );

	}
```
</details>


---