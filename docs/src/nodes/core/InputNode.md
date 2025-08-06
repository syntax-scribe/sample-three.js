[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `InputNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/InputNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `getValueType` | `./NodeUtils.js` |
| `getValueFromType` | `./NodeUtils.js` |
| `arrayBufferToBase64` | `./NodeUtils.js` |


---

## Functions

### `InputNode.getNodeType(): string`

**Returns:** `string`

**Calls:**

- `getValueType (from ./NodeUtils.js)`

<details><summary>Code</summary>

```typescript
getNodeType( /*builder*/ ) {

		if ( this.nodeType === null ) {

			return getValueType( this.value );

		}

		return this.nodeType;

	}
```
</details>

### `InputNode.getInputType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Returns the input type of the node which is by default the node type. Derived modules
	 * might overwrite this method and use a fixed type or compute one analytically.
	 *
	 * A typical example for different input and node types are textures. The input type of a
	 * normal RGBA texture is `texture` whereas its node type is `vec4`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getNodeType`

<details><summary>Code</summary>

```typescript
getInputType( builder ) {

		return this.getNodeType( builder );

	}
```
</details>

### `InputNode.setPrecision(precision: "high" | "low" | "medium"): InputNode`

**JSDoc:**
```typescript
/**
	 * Sets the precision to the given value. The method can be
	 * overwritten in derived classes if the final precision must be computed
	 * analytically.
	 *
	 * @param {('low'|'medium'|'high')} precision - The precision of the input value in the shader.
	 * @return {InputNode} A reference to this node.
	 */
```

**Parameters:**

- **`precision`** `"high" | "low" | "medium"`

**Returns:** `InputNode`

<details><summary>Code</summary>

```typescript
setPrecision( precision ) {

		this.precision = precision;

		return this;

	}
```
</details>

### `InputNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`
- `this.value.toArray`
- `getValueType (from ./NodeUtils.js)`
- `arrayBufferToBase64 (from ./NodeUtils.js)`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.value = this.value;

		if ( this.value && this.value.toArray ) data.value = this.value.toArray();

		data.valueType = getValueType( this.value );
		data.nodeType = this.nodeType;

		if ( data.valueType === 'ArrayBuffer' ) data.value = arrayBufferToBase64( data.value );

		data.precision = this.precision;

	}
```
</details>

### `InputNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`
- `Array.isArray`
- `getValueFromType (from ./NodeUtils.js)`
- `this.value.fromArray`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.nodeType = data.nodeType;
		this.value = Array.isArray( data.value ) ? getValueFromType( data.valueType, ...data.value ) : data.value;

		this.precision = data.precision || null;

		if ( this.value && this.value.fromArray ) this.value = this.value.fromArray( data.value );

	}
```
</details>

### `InputNode.generate(): void`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
generate( /*builder, output*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>


---

## Classes

### `InputNode`

<details><summary>Class Code</summary>

```ts
class InputNode extends Node {

	static get type() {

		return 'InputNode';

	}

	/**
	 * Constructs a new input node.
	 *
	 * @param {any} value - The value of this node. This can be any JS primitive, functions, array buffers or even three.js objects (vector, matrices, colors).
	 * @param {?string} nodeType - The node type. If no explicit type is defined, the node tries to derive the type from its value.
	 */
	constructor( value, nodeType = null ) {

		super( nodeType );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isInputNode = true;

		/**
		 * The value of this node. This can be any JS primitive, functions, array buffers or even three.js objects (vector, matrices, colors).
		 *
		 * @type {any}
		 */
		this.value = value;

		/**
		 * The precision of the value in the shader.
		 *
		 * @type {?('low'|'medium'|'high')}
		 * @default null
		 */
		this.precision = null;

	}

	getNodeType( /*builder*/ ) {

		if ( this.nodeType === null ) {

			return getValueType( this.value );

		}

		return this.nodeType;

	}

	/**
	 * Returns the input type of the node which is by default the node type. Derived modules
	 * might overwrite this method and use a fixed type or compute one analytically.
	 *
	 * A typical example for different input and node types are textures. The input type of a
	 * normal RGBA texture is `texture` whereas its node type is `vec4`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( builder ) {

		return this.getNodeType( builder );

	}

	/**
	 * Sets the precision to the given value. The method can be
	 * overwritten in derived classes if the final precision must be computed
	 * analytically.
	 *
	 * @param {('low'|'medium'|'high')} precision - The precision of the input value in the shader.
	 * @return {InputNode} A reference to this node.
	 */
	setPrecision( precision ) {

		this.precision = precision;

		return this;

	}

	serialize( data ) {

		super.serialize( data );

		data.value = this.value;

		if ( this.value && this.value.toArray ) data.value = this.value.toArray();

		data.valueType = getValueType( this.value );
		data.nodeType = this.nodeType;

		if ( data.valueType === 'ArrayBuffer' ) data.value = arrayBufferToBase64( data.value );

		data.precision = this.precision;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.nodeType = data.nodeType;
		this.value = Array.isArray( data.value ) ? getValueFromType( data.valueType, ...data.value ) : data.value;

		this.precision = data.precision || null;

		if ( this.value && this.value.fromArray ) this.value = this.value.fromArray( data.value );

	}

	generate( /*builder, output*/ ) {

		console.warn( 'Abstract function.' );

	}

}
```
</details>

#### Methods

##### `getNodeType(): string`

<details><summary>Code</summary>

```ts
getNodeType( /*builder*/ ) {

		if ( this.nodeType === null ) {

			return getValueType( this.value );

		}

		return this.nodeType;

	}
```
</details>

##### `getInputType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getInputType( builder ) {

		return this.getNodeType( builder );

	}
```
</details>

##### `setPrecision(precision: "high" | "low" | "medium"): InputNode`

<details><summary>Code</summary>

```ts
setPrecision( precision ) {

		this.precision = precision;

		return this;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.value = this.value;

		if ( this.value && this.value.toArray ) data.value = this.value.toArray();

		data.valueType = getValueType( this.value );
		data.nodeType = this.nodeType;

		if ( data.valueType === 'ArrayBuffer' ) data.value = arrayBufferToBase64( data.value );

		data.precision = this.precision;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.nodeType = data.nodeType;
		this.value = Array.isArray( data.value ) ? getValueFromType( data.valueType, ...data.value ) : data.value;

		this.precision = data.precision || null;

		if ( this.value && this.value.fromArray ) this.value = this.value.fromArray( data.value );

	}
```
</details>

##### `generate(): void`

<details><summary>Code</summary>

```ts
generate( /*builder, output*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>


---