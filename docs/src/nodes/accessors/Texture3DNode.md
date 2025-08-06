[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Texture3DNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/Texture3DNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TextureNode` | `./TextureNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `If` | `../tsl/TSLBase.js` |
| `int` | `../tsl/TSLBase.js` |
| `textureSize` | `./TextureSizeNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `epsilon` | `0.0001` | let/var | `0.0001` | ✗ |
| `step` | `0.01` | let/var | `0.01` | ✗ |
| `texture` | `Texture` | let/var | `this.value` | ✗ |


---

## Functions

### `Texture3DNode.getInputType(): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return a fixed value `'texture3D'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getInputType( /*builder*/ ) {

		return 'texture3D';

	}
```
</details>

### `Texture3DNode.getDefaultUV(): any`

**JSDoc:**
```typescript
/**
	 * Returns a default uv node which is in context of 3D textures a three-dimensional
	 * uv node.
	 *
	 * @return {Node<vec3>} The default uv node.
	 */
```

**Returns:** `any`

**Calls:**

- `vec3 (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
getDefaultUV() {

		return vec3( 0.5, 0.5, 0.5 );

	}
```
</details>

### `Texture3DNode.setUpdateMatrix(): void`

**JSDoc:**
```typescript
/**
	 * Overwritten with an empty implementation since the `updateMatrix` flag is ignored
	 * for 3D textures. The uv transformation matrix is not applied to 3D textures.
	 *
	 * @param {boolean} value - The update toggle.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setUpdateMatrix( /*value*/ ) { }
```
</details>

### `Texture3DNode.setupUV(builder: NodeBuilder, uvNode: Node): Node`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return the unmodified uv node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to setup.
	 * @return {Node} The unmodified uv node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`uvNode`** `Node`

**Returns:** `Node`

**Calls:**

- `builder.isFlipY`
- `uvNode.flipY`
- `uvNode.setY`
- `int( textureSize( this, this.levelNode ).y ).sub( uvNode.y ).sub`

<details><summary>Code</summary>

```typescript
setupUV( builder, uvNode ) {

		const texture = this.value;

		if ( builder.isFlipY() && ( texture.isRenderTargetTexture === true || texture.isFramebufferTexture === true ) ) {

			if ( this.sampler ) {

				uvNode = uvNode.flipY();

			} else {

				uvNode = uvNode.setY( int( textureSize( this, this.levelNode ).y ).sub( uvNode.y ).sub( 1 ) );

			}

		}

		return uvNode;

	}
```
</details>

### `Texture3DNode.generateUV(builder: NodeBuilder, uvNode: Node): string`

**JSDoc:**
```typescript
/**
	 * Generates the uv code snippet.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to generate code for.
	 * @return {string} The generated code snippet.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`uvNode`** `Node`

**Returns:** `string`

**Calls:**

- `uvNode.build`

<details><summary>Code</summary>

```typescript
generateUV( builder, uvNode ) {

		return uvNode.build( builder, 'vec3' );

	}
```
</details>

### `Texture3DNode.normal(uvNode: any): any`

**JSDoc:**
```typescript
/**
	 * TODO.
	 *
	 * @param {Node<vec3>} uvNode - The uv node .
	 * @return {Node<vec3>} TODO.
	 */
```

**Parameters:**

- **`uvNode`** `any`

**Returns:** `any`

**Calls:**

- `normal`

<details><summary>Code</summary>

```typescript
normal( uvNode ) {

		return normal( { texture: this, uv: uvNode } );

	}
```
</details>


---

## Classes

### `Texture3DNode`

<details><summary>Class Code</summary>

```ts
class Texture3DNode extends TextureNode {

	static get type() {

		return 'Texture3DNode';

	}

	/**
	 * Constructs a new 3D texture node.
	 *
	 * @param {Data3DTexture} value - The 3D texture.
	 * @param {?Node<vec2|vec3>} [uvNode=null] - The uv node.
	 * @param {?Node<int>} [levelNode=null] - The level node.
	 */
	constructor( value, uvNode = null, levelNode = null ) {

		super( value, uvNode, levelNode );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isTexture3DNode = true;

	}

	/**
	 * Overwrites the default implementation to return a fixed value `'texture3D'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( /*builder*/ ) {

		return 'texture3D';

	}

	/**
	 * Returns a default uv node which is in context of 3D textures a three-dimensional
	 * uv node.
	 *
	 * @return {Node<vec3>} The default uv node.
	 */
	getDefaultUV() {

		return vec3( 0.5, 0.5, 0.5 );

	}

	/**
	 * Overwritten with an empty implementation since the `updateMatrix` flag is ignored
	 * for 3D textures. The uv transformation matrix is not applied to 3D textures.
	 *
	 * @param {boolean} value - The update toggle.
	 */
	setUpdateMatrix( /*value*/ ) { } // Ignore .updateMatrix for 3d TextureNode

	/**
	 * Overwrites the default implementation to return the unmodified uv node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to setup.
	 * @return {Node} The unmodified uv node.
	 */
	setupUV( builder, uvNode ) {

		const texture = this.value;

		if ( builder.isFlipY() && ( texture.isRenderTargetTexture === true || texture.isFramebufferTexture === true ) ) {

			if ( this.sampler ) {

				uvNode = uvNode.flipY();

			} else {

				uvNode = uvNode.setY( int( textureSize( this, this.levelNode ).y ).sub( uvNode.y ).sub( 1 ) );

			}

		}

		return uvNode;

	}

	/**
	 * Generates the uv code snippet.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to generate code for.
	 * @return {string} The generated code snippet.
	 */
	generateUV( builder, uvNode ) {

		return uvNode.build( builder, 'vec3' );

	}

	/**
	 * TODO.
	 *
	 * @param {Node<vec3>} uvNode - The uv node .
	 * @return {Node<vec3>} TODO.
	 */
	normal( uvNode ) {

		return normal( { texture: this, uv: uvNode } );

	}

}
```
</details>

#### Methods

##### `getInputType(): string`

<details><summary>Code</summary>

```ts
getInputType( /*builder*/ ) {

		return 'texture3D';

	}
```
</details>

##### `getDefaultUV(): any`

<details><summary>Code</summary>

```ts
getDefaultUV() {

		return vec3( 0.5, 0.5, 0.5 );

	}
```
</details>

##### `setUpdateMatrix(): void`

<details><summary>Code</summary>

```ts
setUpdateMatrix( /*value*/ ) { }
```
</details>

##### `setupUV(builder: NodeBuilder, uvNode: Node): Node`

<details><summary>Code</summary>

```ts
setupUV( builder, uvNode ) {

		const texture = this.value;

		if ( builder.isFlipY() && ( texture.isRenderTargetTexture === true || texture.isFramebufferTexture === true ) ) {

			if ( this.sampler ) {

				uvNode = uvNode.flipY();

			} else {

				uvNode = uvNode.setY( int( textureSize( this, this.levelNode ).y ).sub( uvNode.y ).sub( 1 ) );

			}

		}

		return uvNode;

	}
```
</details>

##### `generateUV(builder: NodeBuilder, uvNode: Node): string`

<details><summary>Code</summary>

```ts
generateUV( builder, uvNode ) {

		return uvNode.build( builder, 'vec3' );

	}
```
</details>

##### `normal(uvNode: any): any`

<details><summary>Code</summary>

```ts
normal( uvNode ) {

		return normal( { texture: this, uv: uvNode } );

	}
```
</details>


---