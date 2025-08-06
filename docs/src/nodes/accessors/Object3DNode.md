[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Object3DNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/Object3DNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `UniformNode` | `../core/UniformNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `Vector3` | `../../math/Vector3.js` |
| `Sphere` | `../../math/Sphere.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `scope` | `"position" \| "scale" \| "direction" ...` | let/var | `this.scope` | ✗ |
| `object` | `Object3D` | let/var | `this.object3d` | ✗ |
| `uniformNode` | `UniformNode` | let/var | `this.uniformNode` | ✗ |
| `scope` | `"position" \| "scale" \| "direction" ...` | let/var | `this.scope` | ✗ |
| `camera` | `any` | let/var | `frame.camera` | ✗ |
| `geometry` | `any` | let/var | `frame.object.geometry` | ✗ |
| `scope` | `"position" \| "scale" \| "direction" ...` | let/var | `this.scope` | ✗ |


---

## Functions

### `Object3DNode.getNodeType(): string`

**JSDoc:**
```typescript
/**
	 * Overwritten since the node type is inferred from the scope.
	 *
	 * @return {string} The node type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getNodeType() {

		const scope = this.scope;

		if ( scope === Object3DNode.WORLD_MATRIX ) {

			return 'mat4';

		} else if ( scope === Object3DNode.POSITION || scope === Object3DNode.VIEW_POSITION || scope === Object3DNode.DIRECTION || scope === Object3DNode.SCALE ) {

			return 'vec3';

		} else if ( scope === Object3DNode.RADIUS ) {

			return 'float';

		}

	}
```
</details>

### `Object3DNode.update(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Updates the uniform value depending on the scope.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `uniformNode.value.setFromMatrixPosition`
- `uniformNode.value.setFromMatrixScale`
- `object.getWorldDirection`
- `uniformNode.value.applyMatrix4`
- `geometry.computeBoundingSphere`
- `_sphere.copy( geometry.boundingSphere ).applyMatrix4`

<details><summary>Code</summary>

```typescript
update( frame ) {

		const object = this.object3d;
		const uniformNode = this.uniformNode;
		const scope = this.scope;

		if ( scope === Object3DNode.WORLD_MATRIX ) {

			uniformNode.value = object.matrixWorld;

		} else if ( scope === Object3DNode.POSITION ) {

			uniformNode.value = uniformNode.value || new Vector3();

			uniformNode.value.setFromMatrixPosition( object.matrixWorld );

		} else if ( scope === Object3DNode.SCALE ) {

			uniformNode.value = uniformNode.value || new Vector3();

			uniformNode.value.setFromMatrixScale( object.matrixWorld );

		} else if ( scope === Object3DNode.DIRECTION ) {

			uniformNode.value = uniformNode.value || new Vector3();

			object.getWorldDirection( uniformNode.value );

		} else if ( scope === Object3DNode.VIEW_POSITION ) {

			const camera = frame.camera;

			uniformNode.value = uniformNode.value || new Vector3();
			uniformNode.value.setFromMatrixPosition( object.matrixWorld );

			uniformNode.value.applyMatrix4( camera.matrixWorldInverse );

		} else if ( scope === Object3DNode.RADIUS ) {

			const geometry = frame.object.geometry;

			if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

			_sphere.copy( geometry.boundingSphere ).applyMatrix4( object.matrixWorld );

			uniformNode.value = _sphere.radius;

		}

	}
```
</details>

### `Object3DNode.generate(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Generates the code snippet of the uniform node. The node type of the uniform
	 * node also depends on the selected scope.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated code snippet.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.uniformNode.build`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const scope = this.scope;

		if ( scope === Object3DNode.WORLD_MATRIX ) {

			this.uniformNode.nodeType = 'mat4';

		} else if ( scope === Object3DNode.POSITION || scope === Object3DNode.VIEW_POSITION || scope === Object3DNode.DIRECTION || scope === Object3DNode.SCALE ) {

			this.uniformNode.nodeType = 'vec3';

		} else if ( scope === Object3DNode.RADIUS ) {

			this.uniformNode.nodeType = 'float';

		}

		return this.uniformNode.build( builder );

	}
```
</details>

### `Object3DNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.scope = this.scope;

	}
```
</details>

### `Object3DNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.scope = data.scope;

	}
```
</details>


---

## Classes

### `Object3DNode`

<details><summary>Class Code</summary>

```ts
class Object3DNode extends Node {

	static get type() {

		return 'Object3DNode';

	}

	/**
	 * Constructs a new object 3D node.
	 *
	 * @param {('position'|'viewPosition'|'direction'|'scale'|'worldMatrix')} scope - The node represents a different type of transformation depending on the scope.
	 * @param {?Object3D} [object3d=null] - The 3D object.
	 */
	constructor( scope, object3d = null ) {

		super();

		/**
		 * The node reports a different type of transformation depending on the scope.
		 *
		 * @type {('position'|'viewPosition'|'direction'|'scale'|'worldMatrix')}
		 */
		this.scope = scope;

		/**
		 * The 3D object.
		 *
		 * @type {?Object3D}
		 * @default null
		 */
		this.object3d = object3d;

		/**
		 * Overwritten since this type of node is updated per object.
		 *
		 * @type {string}
		 * @default 'object'
		 */
		this.updateType = NodeUpdateType.OBJECT;

		/**
		 * Holds the value of the node as a uniform.
		 *
		 * @type {UniformNode}
		 */
		this.uniformNode = new UniformNode( null );

	}

	/**
	 * Overwritten since the node type is inferred from the scope.
	 *
	 * @return {string} The node type.
	 */
	getNodeType() {

		const scope = this.scope;

		if ( scope === Object3DNode.WORLD_MATRIX ) {

			return 'mat4';

		} else if ( scope === Object3DNode.POSITION || scope === Object3DNode.VIEW_POSITION || scope === Object3DNode.DIRECTION || scope === Object3DNode.SCALE ) {

			return 'vec3';

		} else if ( scope === Object3DNode.RADIUS ) {

			return 'float';

		}

	}

	/**
	 * Updates the uniform value depending on the scope.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	update( frame ) {

		const object = this.object3d;
		const uniformNode = this.uniformNode;
		const scope = this.scope;

		if ( scope === Object3DNode.WORLD_MATRIX ) {

			uniformNode.value = object.matrixWorld;

		} else if ( scope === Object3DNode.POSITION ) {

			uniformNode.value = uniformNode.value || new Vector3();

			uniformNode.value.setFromMatrixPosition( object.matrixWorld );

		} else if ( scope === Object3DNode.SCALE ) {

			uniformNode.value = uniformNode.value || new Vector3();

			uniformNode.value.setFromMatrixScale( object.matrixWorld );

		} else if ( scope === Object3DNode.DIRECTION ) {

			uniformNode.value = uniformNode.value || new Vector3();

			object.getWorldDirection( uniformNode.value );

		} else if ( scope === Object3DNode.VIEW_POSITION ) {

			const camera = frame.camera;

			uniformNode.value = uniformNode.value || new Vector3();
			uniformNode.value.setFromMatrixPosition( object.matrixWorld );

			uniformNode.value.applyMatrix4( camera.matrixWorldInverse );

		} else if ( scope === Object3DNode.RADIUS ) {

			const geometry = frame.object.geometry;

			if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

			_sphere.copy( geometry.boundingSphere ).applyMatrix4( object.matrixWorld );

			uniformNode.value = _sphere.radius;

		}

	}

	/**
	 * Generates the code snippet of the uniform node. The node type of the uniform
	 * node also depends on the selected scope.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated code snippet.
	 */
	generate( builder ) {

		const scope = this.scope;

		if ( scope === Object3DNode.WORLD_MATRIX ) {

			this.uniformNode.nodeType = 'mat4';

		} else if ( scope === Object3DNode.POSITION || scope === Object3DNode.VIEW_POSITION || scope === Object3DNode.DIRECTION || scope === Object3DNode.SCALE ) {

			this.uniformNode.nodeType = 'vec3';

		} else if ( scope === Object3DNode.RADIUS ) {

			this.uniformNode.nodeType = 'float';

		}

		return this.uniformNode.build( builder );

	}

	serialize( data ) {

		super.serialize( data );

		data.scope = this.scope;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.scope = data.scope;

	}

}
```
</details>

#### Methods

##### `getNodeType(): string`

<details><summary>Code</summary>

```ts
getNodeType() {

		const scope = this.scope;

		if ( scope === Object3DNode.WORLD_MATRIX ) {

			return 'mat4';

		} else if ( scope === Object3DNode.POSITION || scope === Object3DNode.VIEW_POSITION || scope === Object3DNode.DIRECTION || scope === Object3DNode.SCALE ) {

			return 'vec3';

		} else if ( scope === Object3DNode.RADIUS ) {

			return 'float';

		}

	}
```
</details>

##### `update(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
update( frame ) {

		const object = this.object3d;
		const uniformNode = this.uniformNode;
		const scope = this.scope;

		if ( scope === Object3DNode.WORLD_MATRIX ) {

			uniformNode.value = object.matrixWorld;

		} else if ( scope === Object3DNode.POSITION ) {

			uniformNode.value = uniformNode.value || new Vector3();

			uniformNode.value.setFromMatrixPosition( object.matrixWorld );

		} else if ( scope === Object3DNode.SCALE ) {

			uniformNode.value = uniformNode.value || new Vector3();

			uniformNode.value.setFromMatrixScale( object.matrixWorld );

		} else if ( scope === Object3DNode.DIRECTION ) {

			uniformNode.value = uniformNode.value || new Vector3();

			object.getWorldDirection( uniformNode.value );

		} else if ( scope === Object3DNode.VIEW_POSITION ) {

			const camera = frame.camera;

			uniformNode.value = uniformNode.value || new Vector3();
			uniformNode.value.setFromMatrixPosition( object.matrixWorld );

			uniformNode.value.applyMatrix4( camera.matrixWorldInverse );

		} else if ( scope === Object3DNode.RADIUS ) {

			const geometry = frame.object.geometry;

			if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

			_sphere.copy( geometry.boundingSphere ).applyMatrix4( object.matrixWorld );

			uniformNode.value = _sphere.radius;

		}

	}
```
</details>

##### `generate(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const scope = this.scope;

		if ( scope === Object3DNode.WORLD_MATRIX ) {

			this.uniformNode.nodeType = 'mat4';

		} else if ( scope === Object3DNode.POSITION || scope === Object3DNode.VIEW_POSITION || scope === Object3DNode.DIRECTION || scope === Object3DNode.SCALE ) {

			this.uniformNode.nodeType = 'vec3';

		} else if ( scope === Object3DNode.RADIUS ) {

			this.uniformNode.nodeType = 'float';

		}

		return this.uniformNode.build( builder );

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.scope = this.scope;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.scope = data.scope;

	}
```
</details>


---