[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ScreenNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/ScreenNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `uniform` | `../core/UniformNode.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `nodeImmutable` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector4` | `../../math/Vector4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `screenSizeVec` | `any` | let/var | `*not shown*` | ✗ |
| `viewportVec` | `any` | let/var | `*not shown*` | ✗ |
| `updateType` | `string` | let/var | `NodeUpdateType.NONE` | ✗ |
| `scope` | `"uv" \| "viewport" \| "coordinate" \|...` | let/var | `this.scope` | ✗ |
| `output` | `any` | let/var | `null` | ✗ |
| `viewportSize` | `any` | let/var | `viewport.zw` | ✓ |


---

## Functions

### `ScreenNode.getNodeType(): "vec4" | "vec2"`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type depends on the selected scope.
	 *
	 * @return {('vec2'|'vec4')} The node type.
	 */
```

**Returns:** `"vec4" | "vec2"`

<details><summary>Code</summary>

```typescript
getNodeType() {

		if ( this.scope === ScreenNode.VIEWPORT ) return 'vec4';
		else return 'vec2';

	}
```
</details>

### `ScreenNode.getUpdateType(): { NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node's update type depends on the selected scope.
	 *
	 * @return {NodeUpdateType} The update type.
	 */
```

**Returns:** `{ NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

<details><summary>Code</summary>

```typescript
getUpdateType() {

		let updateType = NodeUpdateType.NONE;

		if ( this.scope === ScreenNode.SIZE || this.scope === ScreenNode.VIEWPORT ) {

			updateType = NodeUpdateType.RENDER;

		}

		this.updateType = updateType;

		return updateType;

	}
```
</details>

### `ScreenNode.update({ renderer }: any): void`

**JSDoc:**
```typescript
/**
	 * `ScreenNode` implements {@link Node#update} to retrieve viewport and size information
	 * from the current renderer.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`{ renderer }`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getRenderTarget`
- `viewportVec.copy`
- `renderer.getViewport`
- `viewportVec.multiplyScalar`
- `renderer.getPixelRatio`
- `renderer.getDrawingBufferSize`

<details><summary>Code</summary>

```typescript
update( { renderer } ) {

		const renderTarget = renderer.getRenderTarget();

		if ( this.scope === ScreenNode.VIEWPORT ) {

			if ( renderTarget !== null ) {

				viewportVec.copy( renderTarget.viewport );

			} else {

				renderer.getViewport( viewportVec );

				viewportVec.multiplyScalar( renderer.getPixelRatio() );

			}

		} else {

			if ( renderTarget !== null ) {

				screenSizeVec.width = renderTarget.width;
				screenSizeVec.height = renderTarget.height;

			} else {

				renderer.getDrawingBufferSize( screenSizeVec );

			}

		}

	}
```
</details>

### `ScreenNode.setup(): any`

**Returns:** `any`

**Calls:**

- `uniform (from ../core/UniformNode.js)`
- `vec2 (from ../tsl/TSLBase.js)`
- `screenCoordinate.div`

<details><summary>Code</summary>

```typescript
setup( /*builder*/ ) {

		const scope = this.scope;

		let output = null;

		if ( scope === ScreenNode.SIZE ) {

			output = uniform( screenSizeVec || ( screenSizeVec = new Vector2() ) );

		} else if ( scope === ScreenNode.VIEWPORT ) {

			output = uniform( viewportVec || ( viewportVec = new Vector4() ) );

		} else {

			output = vec2( screenCoordinate.div( screenSize ) );

		}

		return output;

	}
```
</details>

### `ScreenNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getFragCoord`
- `builder.isFlipY`
- `builder.getNodeProperties( screenSize ).outputNode.build`
- `builder.getType`
- `super.generate`

**Internal Comments:**
```
// follow webgpu standards (x2)
```

<details><summary>Code</summary>

```typescript
generate( builder ) {

		if ( this.scope === ScreenNode.COORDINATE ) {

			let coord = builder.getFragCoord();

			if ( builder.isFlipY() ) {

				// follow webgpu standards

				const size = builder.getNodeProperties( screenSize ).outputNode.build( builder );

				coord = `${ builder.getType( 'vec2' ) }( ${ coord }.x, ${ size }.y - ${ coord }.y )`;

			}

			return coord;

		}

		return super.generate( builder );

	}
```
</details>


---

## Classes

### `ScreenNode`

<details><summary>Class Code</summary>

```ts
class ScreenNode extends Node {

	static get type() {

		return 'ScreenNode';

	}

	/**
	 * Constructs a new screen node.
	 *
	 * @param {('coordinate'|'viewport'|'size'|'uv')} scope - The node's scope.
	 */
	constructor( scope ) {

		super();

		/**
		 * The node represents different metric depending on which scope is selected.
		 *
		 * - `ScreenNode.COORDINATE`: Window-relative coordinates of the current fragment according to WebGPU standards.
		 * - `ScreenNode.VIEWPORT`: The current viewport defined as a four-dimensional vector.
		 * - `ScreenNode.SIZE`: The dimensions of the current bound framebuffer.
		 * - `ScreenNode.UV`: Normalized coordinates.
		 *
		 * @type {('coordinate'|'viewport'|'size'|'uv')}
		 */
		this.scope = scope;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isViewportNode = true;

	}

	/**
	 * This method is overwritten since the node type depends on the selected scope.
	 *
	 * @return {('vec2'|'vec4')} The node type.
	 */
	getNodeType() {

		if ( this.scope === ScreenNode.VIEWPORT ) return 'vec4';
		else return 'vec2';

	}

	/**
	 * This method is overwritten since the node's update type depends on the selected scope.
	 *
	 * @return {NodeUpdateType} The update type.
	 */
	getUpdateType() {

		let updateType = NodeUpdateType.NONE;

		if ( this.scope === ScreenNode.SIZE || this.scope === ScreenNode.VIEWPORT ) {

			updateType = NodeUpdateType.RENDER;

		}

		this.updateType = updateType;

		return updateType;

	}

	/**
	 * `ScreenNode` implements {@link Node#update} to retrieve viewport and size information
	 * from the current renderer.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( { renderer } ) {

		const renderTarget = renderer.getRenderTarget();

		if ( this.scope === ScreenNode.VIEWPORT ) {

			if ( renderTarget !== null ) {

				viewportVec.copy( renderTarget.viewport );

			} else {

				renderer.getViewport( viewportVec );

				viewportVec.multiplyScalar( renderer.getPixelRatio() );

			}

		} else {

			if ( renderTarget !== null ) {

				screenSizeVec.width = renderTarget.width;
				screenSizeVec.height = renderTarget.height;

			} else {

				renderer.getDrawingBufferSize( screenSizeVec );

			}

		}

	}

	setup( /*builder*/ ) {

		const scope = this.scope;

		let output = null;

		if ( scope === ScreenNode.SIZE ) {

			output = uniform( screenSizeVec || ( screenSizeVec = new Vector2() ) );

		} else if ( scope === ScreenNode.VIEWPORT ) {

			output = uniform( viewportVec || ( viewportVec = new Vector4() ) );

		} else {

			output = vec2( screenCoordinate.div( screenSize ) );

		}

		return output;

	}

	generate( builder ) {

		if ( this.scope === ScreenNode.COORDINATE ) {

			let coord = builder.getFragCoord();

			if ( builder.isFlipY() ) {

				// follow webgpu standards

				const size = builder.getNodeProperties( screenSize ).outputNode.build( builder );

				coord = `${ builder.getType( 'vec2' ) }( ${ coord }.x, ${ size }.y - ${ coord }.y )`;

			}

			return coord;

		}

		return super.generate( builder );

	}

}
```
</details>

#### Methods

##### `getNodeType(): "vec4" | "vec2"`

<details><summary>Code</summary>

```ts
getNodeType() {

		if ( this.scope === ScreenNode.VIEWPORT ) return 'vec4';
		else return 'vec2';

	}
```
</details>

##### `getUpdateType(): { NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

<details><summary>Code</summary>

```ts
getUpdateType() {

		let updateType = NodeUpdateType.NONE;

		if ( this.scope === ScreenNode.SIZE || this.scope === ScreenNode.VIEWPORT ) {

			updateType = NodeUpdateType.RENDER;

		}

		this.updateType = updateType;

		return updateType;

	}
```
</details>

##### `update({ renderer }: any): void`

<details><summary>Code</summary>

```ts
update( { renderer } ) {

		const renderTarget = renderer.getRenderTarget();

		if ( this.scope === ScreenNode.VIEWPORT ) {

			if ( renderTarget !== null ) {

				viewportVec.copy( renderTarget.viewport );

			} else {

				renderer.getViewport( viewportVec );

				viewportVec.multiplyScalar( renderer.getPixelRatio() );

			}

		} else {

			if ( renderTarget !== null ) {

				screenSizeVec.width = renderTarget.width;
				screenSizeVec.height = renderTarget.height;

			} else {

				renderer.getDrawingBufferSize( screenSizeVec );

			}

		}

	}
```
</details>

##### `setup(): any`

<details><summary>Code</summary>

```ts
setup( /*builder*/ ) {

		const scope = this.scope;

		let output = null;

		if ( scope === ScreenNode.SIZE ) {

			output = uniform( screenSizeVec || ( screenSizeVec = new Vector2() ) );

		} else if ( scope === ScreenNode.VIEWPORT ) {

			output = uniform( viewportVec || ( viewportVec = new Vector4() ) );

		} else {

			output = vec2( screenCoordinate.div( screenSize ) );

		}

		return output;

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		if ( this.scope === ScreenNode.COORDINATE ) {

			let coord = builder.getFragCoord();

			if ( builder.isFlipY() ) {

				// follow webgpu standards

				const size = builder.getNodeProperties( screenSize ).outputNode.build( builder );

				coord = `${ builder.getType( 'vec2' ) }( ${ coord }.x, ${ size }.y - ${ coord }.y )`;

			}

			return coord;

		}

		return super.generate( builder );

	}
```
</details>


---