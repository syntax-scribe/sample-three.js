[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RectAreaLightNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/RectAreaLightNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnalyticLightNode` | `./AnalyticLightNode.js` |
| `texture` | `../accessors/TextureNode.js` |
| `uniform` | `../core/UniformNode.js` |
| `lightViewPosition` | `../accessors/Lights.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `Matrix4` | `../../math/Matrix4.js` |
| `Vector3` | `../../math/Vector3.js` |
| `NodeUpdateType` | `../core/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_matrix41` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_matrix42` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_ltcLib` | `any` | let/var | `null` | ✗ |
| `viewMatrix` | `any` | let/var | `frame.camera.matrixWorldInverse` | ✗ |
| `ltc_1` | `any` | let/var | `*not shown*` | ✗ |
| `ltc_2` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `RectAreaLightNode.update(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Overwritten to updated rect area light specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `super.update`
- `_matrix42.identity`
- `_matrix41.copy`
- `_matrix41.premultiply`
- `_matrix42.extractRotation`
- `this.halfWidth.value.set`
- `this.halfHeight.value.set`
- `this.halfWidth.value.applyMatrix4`
- `this.halfHeight.value.applyMatrix4`

<details><summary>Code</summary>

```typescript
update( frame ) {

		super.update( frame );

		const { light } = this;

		const viewMatrix = frame.camera.matrixWorldInverse;

		_matrix42.identity();
		_matrix41.copy( light.matrixWorld );
		_matrix41.premultiply( viewMatrix );
		_matrix42.extractRotation( _matrix41 );

		this.halfWidth.value.set( light.width * 0.5, 0.0, 0.0 );
		this.halfHeight.value.set( 0.0, light.height * 0.5, 0.0 );

		this.halfWidth.value.applyMatrix4( _matrix42 );
		this.halfHeight.value.applyMatrix4( _matrix42 );

	}
```
</details>

### `RectAreaLightNode.setupDirectRectArea(builder: any): { lightColor: Node; lightPosition: UniformNode<vec3>; halfWidth: UniformNode<vec3>; halfHeight: UniformNode<vec3>; ltc_1: TextureNode; ltc_2: TextureNode; }`

**Parameters:**

- **`builder`** `any`

**Returns:** `{ lightColor: Node; lightPosition: UniformNode<vec3>; halfWidth: UniformNode<vec3>; halfHeight: UniformNode<vec3>; ltc_1: TextureNode; ltc_2: TextureNode; }`

**Calls:**

- `builder.isAvailable`
- `texture (from ../accessors/TextureNode.js)`
- `lightViewPosition (from ../accessors/Lights.js)`

<details><summary>Code</summary>

```typescript
setupDirectRectArea( builder ) {

		let ltc_1, ltc_2;

		if ( builder.isAvailable( 'float32Filterable' ) ) {

			ltc_1 = texture( _ltcLib.LTC_FLOAT_1 );
			ltc_2 = texture( _ltcLib.LTC_FLOAT_2 );

		} else {

			ltc_1 = texture( _ltcLib.LTC_HALF_1 );
			ltc_2 = texture( _ltcLib.LTC_HALF_2 );

		}

		const { colorNode, light } = this;

		const lightPosition = lightViewPosition( light );

		return {
			lightColor: colorNode,
			lightPosition,
			halfWidth: this.halfWidth,
			halfHeight: this.halfHeight,
			ltc_1,
			ltc_2
		};

	}
```
</details>

### `RectAreaLightNode.setLTC(ltc: RectAreaLightTexturesLib): void`

**JSDoc:**
```typescript
/**
	 * Used to configure the internal BRDF approximation texture data.
	 *
	 * @param {RectAreaLightTexturesLib} ltc - The BRDF approximation texture data.
	 */
```

**Parameters:**

- **`ltc`** `RectAreaLightTexturesLib`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
static setLTC( ltc ) {

		_ltcLib = ltc;

	}
```
</details>


---

## Classes

### `RectAreaLightNode`

<details><summary>Class Code</summary>

```ts
class RectAreaLightNode extends AnalyticLightNode {

	static get type() {

		return 'RectAreaLightNode';

	}

	/**
	 * Constructs a new rect area light node.
	 *
	 * @param {?RectAreaLight} [light=null] - The rect area light source.
	 */
	constructor( light = null ) {

		super( light );

		/**
		 * Uniform node representing the half height of the are light.
		 *
		 * @type {UniformNode<vec3>}
		 */
		this.halfHeight = uniform( new Vector3() ).setGroup( renderGroup );

		/**
		 * Uniform node representing the half width of the are light.
		 *
		 * @type {UniformNode<vec3>}
		 */
		this.halfWidth = uniform( new Vector3() ).setGroup( renderGroup );

		/**
		 * The `updateType` is set to `NodeUpdateType.RENDER` since the light
		 * relies on `viewMatrix` which might vary per render call.
		 *
		 * @type {string}
		 * @default 'render'
		 */
		this.updateType = NodeUpdateType.RENDER;

	}

	/**
	 * Overwritten to updated rect area light specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( frame ) {

		super.update( frame );

		const { light } = this;

		const viewMatrix = frame.camera.matrixWorldInverse;

		_matrix42.identity();
		_matrix41.copy( light.matrixWorld );
		_matrix41.premultiply( viewMatrix );
		_matrix42.extractRotation( _matrix41 );

		this.halfWidth.value.set( light.width * 0.5, 0.0, 0.0 );
		this.halfHeight.value.set( 0.0, light.height * 0.5, 0.0 );

		this.halfWidth.value.applyMatrix4( _matrix42 );
		this.halfHeight.value.applyMatrix4( _matrix42 );

	}

	setupDirectRectArea( builder ) {

		let ltc_1, ltc_2;

		if ( builder.isAvailable( 'float32Filterable' ) ) {

			ltc_1 = texture( _ltcLib.LTC_FLOAT_1 );
			ltc_2 = texture( _ltcLib.LTC_FLOAT_2 );

		} else {

			ltc_1 = texture( _ltcLib.LTC_HALF_1 );
			ltc_2 = texture( _ltcLib.LTC_HALF_2 );

		}

		const { colorNode, light } = this;

		const lightPosition = lightViewPosition( light );

		return {
			lightColor: colorNode,
			lightPosition,
			halfWidth: this.halfWidth,
			halfHeight: this.halfHeight,
			ltc_1,
			ltc_2
		};

	}

	/**
	 * Used to configure the internal BRDF approximation texture data.
	 *
	 * @param {RectAreaLightTexturesLib} ltc - The BRDF approximation texture data.
	 */
	static setLTC( ltc ) {

		_ltcLib = ltc;

	}

}
```
</details>

#### Methods

##### `update(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
update( frame ) {

		super.update( frame );

		const { light } = this;

		const viewMatrix = frame.camera.matrixWorldInverse;

		_matrix42.identity();
		_matrix41.copy( light.matrixWorld );
		_matrix41.premultiply( viewMatrix );
		_matrix42.extractRotation( _matrix41 );

		this.halfWidth.value.set( light.width * 0.5, 0.0, 0.0 );
		this.halfHeight.value.set( 0.0, light.height * 0.5, 0.0 );

		this.halfWidth.value.applyMatrix4( _matrix42 );
		this.halfHeight.value.applyMatrix4( _matrix42 );

	}
```
</details>

##### `setupDirectRectArea(builder: any): { lightColor: Node; lightPosition: UniformNode<vec3>; halfWidth: UniformNode<vec3>; halfHeight: UniformNode<vec3>; ltc_1: TextureNode; ltc_2: TextureNode; }`

<details><summary>Code</summary>

```ts
setupDirectRectArea( builder ) {

		let ltc_1, ltc_2;

		if ( builder.isAvailable( 'float32Filterable' ) ) {

			ltc_1 = texture( _ltcLib.LTC_FLOAT_1 );
			ltc_2 = texture( _ltcLib.LTC_FLOAT_2 );

		} else {

			ltc_1 = texture( _ltcLib.LTC_HALF_1 );
			ltc_2 = texture( _ltcLib.LTC_HALF_2 );

		}

		const { colorNode, light } = this;

		const lightPosition = lightViewPosition( light );

		return {
			lightColor: colorNode,
			lightPosition,
			halfWidth: this.halfWidth,
			halfHeight: this.halfHeight,
			ltc_1,
			ltc_2
		};

	}
```
</details>

##### `setLTC(ltc: RectAreaLightTexturesLib): void`

<details><summary>Code</summary>

```ts
static setLTC( ltc ) {

		_ltcLib = ltc;

	}
```
</details>


---