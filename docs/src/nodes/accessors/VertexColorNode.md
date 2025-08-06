[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `VertexColorNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/VertexColorNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AttributeNode` | `../core/AttributeNode.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `Vector4` | `../../math/Vector4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `index` | `number` | let/var | `this.index` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `VertexColorNode.getAttributeName(): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation by honoring the attribute index.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The attribute name.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getAttributeName( /*builder*/ ) {

		const index = this.index;

		return 'color' + ( index > 0 ? index : '' );

	}
```
</details>

### `VertexColorNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getAttributeName`
- `builder.hasGeometryAttribute`
- `super.generate`
- `builder.generateConst`

**Internal Comments:**
```
// Vertex color fallback should be white (x3)
```

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const attributeName = this.getAttributeName( builder );
		const geometryAttribute = builder.hasGeometryAttribute( attributeName );

		let result;

		if ( geometryAttribute === true ) {

			result = super.generate( builder );

		} else {

			// Vertex color fallback should be white
			result = builder.generateConst( this.nodeType, new Vector4( 1, 1, 1, 1 ) );

		}

		return result;

	}
```
</details>

### `VertexColorNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.index = this.index;

	}
```
</details>

### `VertexColorNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.index = data.index;

	}
```
</details>

### `vertexColor(index: number): VertexColorNode`

**Parameters:**

- **`index`** `number`

**Returns:** `VertexColorNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( index = 0 ) => nodeObject( new VertexColorNode( index ) )
```
</details>


---

## Classes

### `VertexColorNode`

<details><summary>Class Code</summary>

```ts
class VertexColorNode extends AttributeNode {

	static get type() {

		return 'VertexColorNode';

	}

	/**
	 * Constructs a new vertex color node.
	 *
	 * @param {number} index - The attribute index.
	 */
	constructor( index ) {

		super( null, 'vec4' );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isVertexColorNode = true;

		/**
		 * The attribute index to enable more than one sets of vertex colors.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.index = index;

	}

	/**
	 * Overwrites the default implementation by honoring the attribute index.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The attribute name.
	 */
	getAttributeName( /*builder*/ ) {

		const index = this.index;

		return 'color' + ( index > 0 ? index : '' );

	}

	generate( builder ) {

		const attributeName = this.getAttributeName( builder );
		const geometryAttribute = builder.hasGeometryAttribute( attributeName );

		let result;

		if ( geometryAttribute === true ) {

			result = super.generate( builder );

		} else {

			// Vertex color fallback should be white
			result = builder.generateConst( this.nodeType, new Vector4( 1, 1, 1, 1 ) );

		}

		return result;

	}

	serialize( data ) {

		super.serialize( data );

		data.index = this.index;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.index = data.index;

	}

}
```
</details>

#### Methods

##### `getAttributeName(): string`

<details><summary>Code</summary>

```ts
getAttributeName( /*builder*/ ) {

		const index = this.index;

		return 'color' + ( index > 0 ? index : '' );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const attributeName = this.getAttributeName( builder );
		const geometryAttribute = builder.hasGeometryAttribute( attributeName );

		let result;

		if ( geometryAttribute === true ) {

			result = super.generate( builder );

		} else {

			// Vertex color fallback should be white
			result = builder.generateConst( this.nodeType, new Vector4( 1, 1, 1, 1 ) );

		}

		return result;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.index = this.index;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.index = data.index;

	}
```
</details>


---