[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AttributeNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/AttributeNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `varying` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `nodeType` | `string` | let/var | `this.nodeType` | ✗ |


---

## Functions

### `AttributeNode.getHash(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.getAttributeName`

<details><summary>Code</summary>

```typescript
getHash( builder ) {

		return this.getAttributeName( builder );

	}
```
</details>

### `AttributeNode.getNodeType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.getAttributeName`
- `builder.hasGeometryAttribute`
- `builder.geometry.getAttribute`
- `builder.getTypeFromAttribute`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		let nodeType = this.nodeType;

		if ( nodeType === null ) {

			const attributeName = this.getAttributeName( builder );

			if ( builder.hasGeometryAttribute( attributeName ) ) {

				const attribute = builder.geometry.getAttribute( attributeName );

				nodeType = builder.getTypeFromAttribute( attribute );

			} else {

				nodeType = 'float';

			}

		}

		return nodeType;

	}
```
</details>

### `AttributeNode.setAttributeName(attributeName: string): AttributeNode`

**JSDoc:**
```typescript
/**
	 * Sets the attribute name to the given value. The method can be
	 * overwritten in derived classes if the final name must be computed
	 * analytically.
	 *
	 * @param {string} attributeName - The name of the attribute.
	 * @return {AttributeNode} A reference to this node.
	 */
```

**Parameters:**

- **`attributeName`** `string`

**Returns:** `AttributeNode`

<details><summary>Code</summary>

```typescript
setAttributeName( attributeName ) {

		this._attributeName = attributeName;

		return this;

	}
```
</details>

### `AttributeNode.getAttributeName(): string`

**JSDoc:**
```typescript
/**
	 * Returns the attribute name of this node. The method can be
	 * overwritten in derived classes if the final name must be computed
	 * analytically.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The attribute name.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getAttributeName( /*builder*/ ) {

		return this._attributeName;

	}
```
</details>

### `AttributeNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getAttributeName`
- `this.getNodeType`
- `builder.hasGeometryAttribute`
- `builder.geometry.getAttribute`
- `builder.getTypeFromAttribute`
- `builder.getAttribute`
- `builder.format`
- `varying (from ../tsl/TSLBase.js)`
- `nodeVarying.build`
- `console.warn`
- `builder.generateConst`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const attributeName = this.getAttributeName( builder );
		const nodeType = this.getNodeType( builder );
		const geometryAttribute = builder.hasGeometryAttribute( attributeName );

		if ( geometryAttribute === true ) {

			const attribute = builder.geometry.getAttribute( attributeName );
			const attributeType = builder.getTypeFromAttribute( attribute );

			const nodeAttribute = builder.getAttribute( attributeName, attributeType );

			if ( builder.shaderStage === 'vertex' ) {

				return builder.format( nodeAttribute.name, attributeType, nodeType );

			} else {

				const nodeVarying = varying( this );

				return nodeVarying.build( builder, nodeType );

			}

		} else {

			console.warn( `AttributeNode: Vertex attribute "${ attributeName }" not found on geometry.` );

			return builder.generateConst( nodeType );

		}

	}
```
</details>

### `AttributeNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.global = this.global;
		data._attributeName = this._attributeName;

	}
```
</details>

### `AttributeNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.global = data.global;
		this._attributeName = data._attributeName;

	}
```
</details>

### `attribute(name: string, nodeType: string): AttributeNode`

**Parameters:**

- **`name`** `string`
- **`nodeType`** `string`

**Returns:** `AttributeNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( name, nodeType = null ) => nodeObject( new AttributeNode( name, nodeType ) )
```
</details>


---

## Classes

### `AttributeNode`

<details><summary>Class Code</summary>

```ts
class AttributeNode extends Node {

	static get type() {

		return 'AttributeNode';

	}

	/**
	 * Constructs a new attribute node.
	 *
	 * @param {string} attributeName - The name of the attribute.
	 * @param {?string} nodeType - The node type.
	 */
	constructor( attributeName, nodeType = null ) {

		super( nodeType );

		/**
		 * `AttributeNode` sets this property to `true` by default.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

		this._attributeName = attributeName;

	}

	getHash( builder ) {

		return this.getAttributeName( builder );

	}

	getNodeType( builder ) {

		let nodeType = this.nodeType;

		if ( nodeType === null ) {

			const attributeName = this.getAttributeName( builder );

			if ( builder.hasGeometryAttribute( attributeName ) ) {

				const attribute = builder.geometry.getAttribute( attributeName );

				nodeType = builder.getTypeFromAttribute( attribute );

			} else {

				nodeType = 'float';

			}

		}

		return nodeType;

	}

	/**
	 * Sets the attribute name to the given value. The method can be
	 * overwritten in derived classes if the final name must be computed
	 * analytically.
	 *
	 * @param {string} attributeName - The name of the attribute.
	 * @return {AttributeNode} A reference to this node.
	 */
	setAttributeName( attributeName ) {

		this._attributeName = attributeName;

		return this;

	}

	/**
	 * Returns the attribute name of this node. The method can be
	 * overwritten in derived classes if the final name must be computed
	 * analytically.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The attribute name.
	 */
	getAttributeName( /*builder*/ ) {

		return this._attributeName;

	}

	generate( builder ) {

		const attributeName = this.getAttributeName( builder );
		const nodeType = this.getNodeType( builder );
		const geometryAttribute = builder.hasGeometryAttribute( attributeName );

		if ( geometryAttribute === true ) {

			const attribute = builder.geometry.getAttribute( attributeName );
			const attributeType = builder.getTypeFromAttribute( attribute );

			const nodeAttribute = builder.getAttribute( attributeName, attributeType );

			if ( builder.shaderStage === 'vertex' ) {

				return builder.format( nodeAttribute.name, attributeType, nodeType );

			} else {

				const nodeVarying = varying( this );

				return nodeVarying.build( builder, nodeType );

			}

		} else {

			console.warn( `AttributeNode: Vertex attribute "${ attributeName }" not found on geometry.` );

			return builder.generateConst( nodeType );

		}

	}

	serialize( data ) {

		super.serialize( data );

		data.global = this.global;
		data._attributeName = this._attributeName;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.global = data.global;
		this._attributeName = data._attributeName;

	}

}
```
</details>

#### Methods

##### `getHash(builder: any): string`

<details><summary>Code</summary>

```ts
getHash( builder ) {

		return this.getAttributeName( builder );

	}
```
</details>

##### `getNodeType(builder: any): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		let nodeType = this.nodeType;

		if ( nodeType === null ) {

			const attributeName = this.getAttributeName( builder );

			if ( builder.hasGeometryAttribute( attributeName ) ) {

				const attribute = builder.geometry.getAttribute( attributeName );

				nodeType = builder.getTypeFromAttribute( attribute );

			} else {

				nodeType = 'float';

			}

		}

		return nodeType;

	}
```
</details>

##### `setAttributeName(attributeName: string): AttributeNode`

<details><summary>Code</summary>

```ts
setAttributeName( attributeName ) {

		this._attributeName = attributeName;

		return this;

	}
```
</details>

##### `getAttributeName(): string`

<details><summary>Code</summary>

```ts
getAttributeName( /*builder*/ ) {

		return this._attributeName;

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const attributeName = this.getAttributeName( builder );
		const nodeType = this.getNodeType( builder );
		const geometryAttribute = builder.hasGeometryAttribute( attributeName );

		if ( geometryAttribute === true ) {

			const attribute = builder.geometry.getAttribute( attributeName );
			const attributeType = builder.getTypeFromAttribute( attribute );

			const nodeAttribute = builder.getAttribute( attributeName, attributeType );

			if ( builder.shaderStage === 'vertex' ) {

				return builder.format( nodeAttribute.name, attributeType, nodeType );

			} else {

				const nodeVarying = varying( this );

				return nodeVarying.build( builder, nodeType );

			}

		} else {

			console.warn( `AttributeNode: Vertex attribute "${ attributeName }" not found on geometry.` );

			return builder.generateConst( nodeType );

		}

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.global = this.global;
		data._attributeName = this._attributeName;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.global = data.global;
		this._attributeName = data._attributeName;

	}
```
</details>


---