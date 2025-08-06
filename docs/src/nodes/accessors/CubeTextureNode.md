[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CubeTextureNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/CubeTextureNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TextureNode` | `./TextureNode.js` |
| `reflectVector` | `./ReflectVector.js` |
| `refractVector` | `./ReflectVector.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `CubeReflectionMapping` | `../../constants.js` |
| `CubeRefractionMapping` | `../../constants.js` |
| `WebGPUCoordinateSystem` | `../../constants.js` |
| `materialEnvRotation` | `./MaterialProperties.js` |
| `CubeTexture` | `../../textures/CubeTexture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `EmptyTexture` | `CubeTexture` | let/var | `new CubeTexture()` | ✗ |
| `texture` | `Texture` | let/var | `this.value` | ✗ |
| `texture` | `Texture` | let/var | `this.value` | ✗ |
| `textureNode` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `CubeTextureNode.getInputType(): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return a fixed value `'cubeTexture'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getInputType( /*builder*/ ) {

		return 'cubeTexture';

	}
```
</details>

### `CubeTextureNode.getDefaultUV(): any`

**JSDoc:**
```typescript
/**
	 * Returns a default uvs based on the mapping type of the cube texture.
	 *
	 * @return {Node<vec3>} The default uv attribute.
	 */
```

**Returns:** `any`

**Calls:**

- `console.error`
- `vec3 (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
getDefaultUV() {

		const texture = this.value;

		if ( texture.mapping === CubeReflectionMapping ) {

			return reflectVector;

		} else if ( texture.mapping === CubeRefractionMapping ) {

			return refractVector;

		} else {

			console.error( 'THREE.CubeTextureNode: Mapping "%s" not supported.', texture.mapping );

			return vec3( 0, 0, 0 );

		}

	}
```
</details>

### `CubeTextureNode.setUpdateMatrix(): void`

**JSDoc:**
```typescript
/**
	 * Overwritten with an empty implementation since the `updateMatrix` flag is ignored
	 * for cube textures. The uv transformation matrix is not applied to cube textures.
	 *
	 * @param {boolean} value - The update toggle.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setUpdateMatrix( /*updateMatrix*/ ) { }
```
</details>

### `CubeTextureNode.setupUV(builder: NodeBuilder, uvNode: Node): Node`

**JSDoc:**
```typescript
/**
	 * Setups the uv node. Depending on the backend as well as the texture type, it might be necessary
	 * to modify the uv node for correct sampling.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to setup.
	 * @return {Node} The updated uv node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`uvNode`** `Node`

**Returns:** `Node`

**Calls:**

- `vec3 (from ../tsl/TSLBase.js)`
- `uvNode.x.negate`
- `materialEnvRotation.mul`

<details><summary>Code</summary>

```typescript
setupUV( builder, uvNode ) {

		const texture = this.value;

		if ( builder.renderer.coordinateSystem === WebGPUCoordinateSystem || ! texture.isRenderTargetTexture ) {

			uvNode = vec3( uvNode.x.negate(), uvNode.yz );

		}

		return materialEnvRotation.mul( uvNode );

	}
```
</details>

### `CubeTextureNode.generateUV(builder: NodeBuilder, cubeUV: Node): string`

**JSDoc:**
```typescript
/**
	 * Generates the uv code snippet.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} cubeUV - The uv node to generate code for.
	 * @return {string} The generated code snippet.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`cubeUV`** `Node`

**Returns:** `string`

**Calls:**

- `cubeUV.build`

<details><summary>Code</summary>

```typescript
generateUV( builder, cubeUV ) {

		return cubeUV.build( builder, 'vec3' );

	}
```
</details>

### `cubeTexture(value: CubeTexture | CubeTextureNode, uvNode: any, levelNode: any, biasNode: any): CubeTextureNode`

**Parameters:**

- **`value`** `CubeTexture | CubeTextureNode`
- **`uvNode`** `any`
- **`levelNode`** `any`
- **`biasNode`** `any`

**Returns:** `CubeTextureNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`
- `value.clone`
- `value.getSelf`
- `cubeTextureBase`

<details><summary>Code</summary>

```typescript
( value = EmptyTexture, uvNode = null, levelNode = null, biasNode = null ) => {

	let textureNode;

	if ( value && value.isCubeTextureNode === true ) {

		textureNode = nodeObject( value.clone() );
		textureNode.referenceNode = value.getSelf(); // Ensure the reference is set to the original node

		if ( uvNode !== null ) textureNode.uvNode = nodeObject( uvNode );
		if ( levelNode !== null ) textureNode.levelNode = nodeObject( levelNode );
		if ( biasNode !== null ) textureNode.biasNode = nodeObject( biasNode );

	} else {

		textureNode = cubeTextureBase( value, uvNode, levelNode, biasNode );

	}

	return textureNode;

}
```
</details>

### `uniformCubeTexture(value: CubeTexture): CubeTextureNode`

**Parameters:**

- **`value`** `CubeTexture`

**Returns:** `CubeTextureNode`

**Calls:**

- `cubeTextureBase`

<details><summary>Code</summary>

```typescript
( value = EmptyTexture ) => cubeTextureBase( value )
```
</details>


---

## Classes

### `CubeTextureNode`

<details><summary>Class Code</summary>

```ts
class CubeTextureNode extends TextureNode {

	static get type() {

		return 'CubeTextureNode';

	}

	/**
	 * Constructs a new cube texture node.
	 *
	 * @param {CubeTexture} value - The cube texture.
	 * @param {?Node<vec3>} [uvNode=null] - The uv node.
	 * @param {?Node<int>} [levelNode=null] - The level node.
	 * @param {?Node<float>} [biasNode=null] - The bias node.
	 */
	constructor( value, uvNode = null, levelNode = null, biasNode = null ) {

		super( value, uvNode, levelNode, biasNode );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCubeTextureNode = true;

	}

	/**
	 * Overwrites the default implementation to return a fixed value `'cubeTexture'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( /*builder*/ ) {

		return 'cubeTexture';

	}

	/**
	 * Returns a default uvs based on the mapping type of the cube texture.
	 *
	 * @return {Node<vec3>} The default uv attribute.
	 */
	getDefaultUV() {

		const texture = this.value;

		if ( texture.mapping === CubeReflectionMapping ) {

			return reflectVector;

		} else if ( texture.mapping === CubeRefractionMapping ) {

			return refractVector;

		} else {

			console.error( 'THREE.CubeTextureNode: Mapping "%s" not supported.', texture.mapping );

			return vec3( 0, 0, 0 );

		}

	}

	/**
	 * Overwritten with an empty implementation since the `updateMatrix` flag is ignored
	 * for cube textures. The uv transformation matrix is not applied to cube textures.
	 *
	 * @param {boolean} value - The update toggle.
	 */
	setUpdateMatrix( /*updateMatrix*/ ) { } // Ignore .updateMatrix for CubeTextureNode

	/**
	 * Setups the uv node. Depending on the backend as well as the texture type, it might be necessary
	 * to modify the uv node for correct sampling.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to setup.
	 * @return {Node} The updated uv node.
	 */
	setupUV( builder, uvNode ) {

		const texture = this.value;

		if ( builder.renderer.coordinateSystem === WebGPUCoordinateSystem || ! texture.isRenderTargetTexture ) {

			uvNode = vec3( uvNode.x.negate(), uvNode.yz );

		}

		return materialEnvRotation.mul( uvNode );

	}

	/**
	 * Generates the uv code snippet.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} cubeUV - The uv node to generate code for.
	 * @return {string} The generated code snippet.
	 */
	generateUV( builder, cubeUV ) {

		return cubeUV.build( builder, 'vec3' );

	}

}
```
</details>

#### Methods

##### `getInputType(): string`

<details><summary>Code</summary>

```ts
getInputType( /*builder*/ ) {

		return 'cubeTexture';

	}
```
</details>

##### `getDefaultUV(): any`

<details><summary>Code</summary>

```ts
getDefaultUV() {

		const texture = this.value;

		if ( texture.mapping === CubeReflectionMapping ) {

			return reflectVector;

		} else if ( texture.mapping === CubeRefractionMapping ) {

			return refractVector;

		} else {

			console.error( 'THREE.CubeTextureNode: Mapping "%s" not supported.', texture.mapping );

			return vec3( 0, 0, 0 );

		}

	}
```
</details>

##### `setUpdateMatrix(): void`

<details><summary>Code</summary>

```ts
setUpdateMatrix( /*updateMatrix*/ ) { }
```
</details>

##### `setupUV(builder: NodeBuilder, uvNode: Node): Node`

<details><summary>Code</summary>

```ts
setupUV( builder, uvNode ) {

		const texture = this.value;

		if ( builder.renderer.coordinateSystem === WebGPUCoordinateSystem || ! texture.isRenderTargetTexture ) {

			uvNode = vec3( uvNode.x.negate(), uvNode.yz );

		}

		return materialEnvRotation.mul( uvNode );

	}
```
</details>

##### `generateUV(builder: NodeBuilder, cubeUV: Node): string`

<details><summary>Code</summary>

```ts
generateUV( builder, cubeUV ) {

		return cubeUV.build( builder, 'vec3' );

	}
```
</details>


---