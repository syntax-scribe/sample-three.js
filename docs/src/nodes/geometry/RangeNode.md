[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RangeNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/geometry/RangeNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `getValueType` | `../core/NodeUtils.js` |
| `buffer` | `../accessors/BufferNode.js` |
| `instancedBufferAttribute` | `../accessors/BufferAttributeNode.js` |
| `instanceIndex` | `../core/IndexNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `Vector4` | `../../math/Vector4.js` |
| `MathUtils` | `../../math/MathUtils.js` |
| `InstancedBufferAttribute` | `../../core/InstancedBufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `min` | `any` | let/var | `null` | ✗ |
| `max` | `any` | let/var | `null` | ✗ |
| `object` | `any` | let/var | `builder.object` | ✗ |
| `output` | `any` | let/var | `null` | ✗ |
| `minValue` | `any` | let/var | `this.minNode.value` | ✗ |
| `maxValue` | `any` | let/var | `this.maxNode.value` | ✗ |
| `stride` | `4` | let/var | `4` | ✗ |
| `length` | `number` | let/var | `stride * object.count` | ✗ |
| `array` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( length )` | ✗ |
| `index` | `number` | let/var | `i % stride` | ✗ |
| `bufferAttribute` | `InstancedBufferAttribute` | let/var | `new InstancedBufferAttribute( array, 4 )` | ✗ |


---

## Functions

### `RangeNode.getVectorLength(builder: NodeBuilder): number`

**JSDoc:**
```typescript
/**
	 * Returns the vector length which is computed based on the range definition.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {number} The vector length.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `number`

**Calls:**

- `builder.getTypeLength`
- `getValueType (from ../core/NodeUtils.js)`

<details><summary>Code</summary>

```typescript
getVectorLength( builder ) {

		const minLength = builder.getTypeLength( getValueType( this.minNode.value ) );
		const maxLength = builder.getTypeLength( getValueType( this.maxNode.value ) );

		return minLength > maxLength ? minLength : maxLength;

	}
```
</details>

### `RangeNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from range definition.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.getTypeFromLength`
- `this.getVectorLength`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return builder.object.count > 1 ? builder.getTypeFromLength( this.getVectorLength( builder ) ) : 'float';

	}
```
</details>

### `RangeNode.setup(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getTypeLength`
- `getValueType (from ../core/NodeUtils.js)`
- `min.setScalar`
- `max.setScalar`
- `min.set`
- `max.set`
- `min.getComponent`
- `max.getComponent`
- `MathUtils.lerp`
- `Math.random`
- `this.getNodeType`
- `buffer( array, 'vec4', object.count ).element( instanceIndex ).convert`
- `builder.geometry.setAttribute`
- `instancedBufferAttribute( bufferAttribute ).convert`
- `float (from ../tsl/TSLBase.js)`

**Internal Comments:**
```
// TODO: Improve anonymous buffer attribute creation removing this part (x2)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const object = builder.object;

		let output = null;

		if ( object.count > 1 ) {

			const minValue = this.minNode.value;
			const maxValue = this.maxNode.value;

			const minLength = builder.getTypeLength( getValueType( minValue ) );
			const maxLength = builder.getTypeLength( getValueType( maxValue ) );

			min = min || new Vector4();
			max = max || new Vector4();

			min.setScalar( 0 );
			max.setScalar( 0 );

			if ( minLength === 1 ) min.setScalar( minValue );
			else if ( minValue.isColor ) min.set( minValue.r, minValue.g, minValue.b, 1 );
			else min.set( minValue.x, minValue.y, minValue.z || 0, minValue.w || 0 );

			if ( maxLength === 1 ) max.setScalar( maxValue );
			else if ( maxValue.isColor ) max.set( maxValue.r, maxValue.g, maxValue.b, 1 );
			else max.set( maxValue.x, maxValue.y, maxValue.z || 0, maxValue.w || 0 );

			const stride = 4;

			const length = stride * object.count;
			const array = new Float32Array( length );

			for ( let i = 0; i < length; i ++ ) {

				const index = i % stride;

				const minElementValue = min.getComponent( index );
				const maxElementValue = max.getComponent( index );

				array[ i ] = MathUtils.lerp( minElementValue, maxElementValue, Math.random() );

			}

			const nodeType = this.getNodeType( builder );

			if ( object.count <= 4096 ) {

				output = buffer( array, 'vec4', object.count ).element( instanceIndex ).convert( nodeType );

			} else {

				// TODO: Improve anonymous buffer attribute creation removing this part
				const bufferAttribute = new InstancedBufferAttribute( array, 4 );
				builder.geometry.setAttribute( '__range' + this.id, bufferAttribute );

				output = instancedBufferAttribute( bufferAttribute ).convert( nodeType );

			}

		} else {

			output = float( 0 );

		}

		return output;

	}
```
</details>


---

## Classes

### `RangeNode`

<details><summary>Class Code</summary>

```ts
class RangeNode extends Node {

	static get type() {

		return 'RangeNode';

	}

	/**
	 * Constructs a new range node.
	 *
	 * @param {Node<any>} [minNode=float()] - A node defining the lower bound of the range.
	 * @param {Node<any>} [maxNode=float()] - A node defining the upper bound of the range.
	 */
	constructor( minNode = float(), maxNode = float() ) {

		super();

		/**
		 *  A node defining the lower bound of the range.
		 *
		 * @type {Node<any>}
		 * @default float()
		 */
		this.minNode = minNode;

		/**
		 *  A node defining the upper bound of the range.
		 *
		 * @type {Node<any>}
		 * @default float()
		 */
		this.maxNode = maxNode;

	}

	/**
	 * Returns the vector length which is computed based on the range definition.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {number} The vector length.
	 */
	getVectorLength( builder ) {

		const minLength = builder.getTypeLength( getValueType( this.minNode.value ) );
		const maxLength = builder.getTypeLength( getValueType( this.maxNode.value ) );

		return minLength > maxLength ? minLength : maxLength;

	}

	/**
	 * This method is overwritten since the node type is inferred from range definition.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		return builder.object.count > 1 ? builder.getTypeFromLength( this.getVectorLength( builder ) ) : 'float';

	}

	setup( builder ) {

		const object = builder.object;

		let output = null;

		if ( object.count > 1 ) {

			const minValue = this.minNode.value;
			const maxValue = this.maxNode.value;

			const minLength = builder.getTypeLength( getValueType( minValue ) );
			const maxLength = builder.getTypeLength( getValueType( maxValue ) );

			min = min || new Vector4();
			max = max || new Vector4();

			min.setScalar( 0 );
			max.setScalar( 0 );

			if ( minLength === 1 ) min.setScalar( minValue );
			else if ( minValue.isColor ) min.set( minValue.r, minValue.g, minValue.b, 1 );
			else min.set( minValue.x, minValue.y, minValue.z || 0, minValue.w || 0 );

			if ( maxLength === 1 ) max.setScalar( maxValue );
			else if ( maxValue.isColor ) max.set( maxValue.r, maxValue.g, maxValue.b, 1 );
			else max.set( maxValue.x, maxValue.y, maxValue.z || 0, maxValue.w || 0 );

			const stride = 4;

			const length = stride * object.count;
			const array = new Float32Array( length );

			for ( let i = 0; i < length; i ++ ) {

				const index = i % stride;

				const minElementValue = min.getComponent( index );
				const maxElementValue = max.getComponent( index );

				array[ i ] = MathUtils.lerp( minElementValue, maxElementValue, Math.random() );

			}

			const nodeType = this.getNodeType( builder );

			if ( object.count <= 4096 ) {

				output = buffer( array, 'vec4', object.count ).element( instanceIndex ).convert( nodeType );

			} else {

				// TODO: Improve anonymous buffer attribute creation removing this part
				const bufferAttribute = new InstancedBufferAttribute( array, 4 );
				builder.geometry.setAttribute( '__range' + this.id, bufferAttribute );

				output = instancedBufferAttribute( bufferAttribute ).convert( nodeType );

			}

		} else {

			output = float( 0 );

		}

		return output;

	}

}
```
</details>

#### Methods

##### `getVectorLength(builder: NodeBuilder): number`

<details><summary>Code</summary>

```ts
getVectorLength( builder ) {

		const minLength = builder.getTypeLength( getValueType( this.minNode.value ) );
		const maxLength = builder.getTypeLength( getValueType( this.maxNode.value ) );

		return minLength > maxLength ? minLength : maxLength;

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return builder.object.count > 1 ? builder.getTypeFromLength( this.getVectorLength( builder ) ) : 'float';

	}
```
</details>

##### `setup(builder: any): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const object = builder.object;

		let output = null;

		if ( object.count > 1 ) {

			const minValue = this.minNode.value;
			const maxValue = this.maxNode.value;

			const minLength = builder.getTypeLength( getValueType( minValue ) );
			const maxLength = builder.getTypeLength( getValueType( maxValue ) );

			min = min || new Vector4();
			max = max || new Vector4();

			min.setScalar( 0 );
			max.setScalar( 0 );

			if ( minLength === 1 ) min.setScalar( minValue );
			else if ( minValue.isColor ) min.set( minValue.r, minValue.g, minValue.b, 1 );
			else min.set( minValue.x, minValue.y, minValue.z || 0, minValue.w || 0 );

			if ( maxLength === 1 ) max.setScalar( maxValue );
			else if ( maxValue.isColor ) max.set( maxValue.r, maxValue.g, maxValue.b, 1 );
			else max.set( maxValue.x, maxValue.y, maxValue.z || 0, maxValue.w || 0 );

			const stride = 4;

			const length = stride * object.count;
			const array = new Float32Array( length );

			for ( let i = 0; i < length; i ++ ) {

				const index = i % stride;

				const minElementValue = min.getComponent( index );
				const maxElementValue = max.getComponent( index );

				array[ i ] = MathUtils.lerp( minElementValue, maxElementValue, Math.random() );

			}

			const nodeType = this.getNodeType( builder );

			if ( object.count <= 4096 ) {

				output = buffer( array, 'vec4', object.count ).element( instanceIndex ).convert( nodeType );

			} else {

				// TODO: Improve anonymous buffer attribute creation removing this part
				const bufferAttribute = new InstancedBufferAttribute( array, 4 );
				builder.geometry.setAttribute( '__range' + this.id, bufferAttribute );

				output = instancedBufferAttribute( bufferAttribute ).convert( nodeType );

			}

		} else {

			output = float( 0 );

		}

		return output;

	}
```
</details>


---