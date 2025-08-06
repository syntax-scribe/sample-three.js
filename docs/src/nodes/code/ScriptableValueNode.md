[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ScriptableValueNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/code/ScriptableValueNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `arrayBufferToBase64` | `../core/NodeUtils.js` |
| `base64ToArrayBuffer` | `../core/NodeUtils.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `EventDispatcher` | `../../core/EventDispatcher.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `value` | `any` | let/var | `this.value` | ✗ |
| `value` | `any` | let/var | `null` | ✗ |


---

## Functions

### `ScriptableValueNode.refresh(): void`

**JSDoc:**
```typescript
/**
	 * Dispatches the `refresh` event.
	 */
```

**Returns:** `void`

**Calls:**

- `this.events.dispatchEvent`

<details><summary>Code</summary>

```typescript
refresh() {

		this.events.dispatchEvent( { type: 'refresh' } );

	}
```
</details>

### `ScriptableValueNode.getValue(): any`

**JSDoc:**
```typescript
/**
	 * The `value` property usually represents a node or even binary data in form of array buffers.
	 * In this case, this method tries to return the actual value behind the complex type.
	 *
	 * @return {any} The value.
	 */
```

**Returns:** `any`

**Calls:**

- `URL.createObjectURL`

<details><summary>Code</summary>

```typescript
getValue() {

		const value = this.value;

		if ( value && this._cache === null && this.inputType === 'URL' && value.value instanceof ArrayBuffer ) {

			this._cache = URL.createObjectURL( new Blob( [ value.value ] ) );

		} else if ( value && value.value !== null && value.value !== undefined && (
			( ( this.inputType === 'URL' || this.inputType === 'String' ) && typeof value.value === 'string' ) ||
			( this.inputType === 'Number' && typeof value.value === 'number' ) ||
			( this.inputType === 'Vector2' && value.value.isVector2 ) ||
			( this.inputType === 'Vector3' && value.value.isVector3 ) ||
			( this.inputType === 'Vector4' && value.value.isVector4 ) ||
			( this.inputType === 'Color' && value.value.isColor ) ||
			( this.inputType === 'Matrix3' && value.value.isMatrix3 ) ||
			( this.inputType === 'Matrix4' && value.value.isMatrix4 )
		) ) {

			return value.value;

		}

		return this._cache || value;

	}
```
</details>

### `ScriptableValueNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Overwritten since the node type is inferred from the value.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.value.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.value && this.value.isNode ? this.value.getNodeType( builder ) : 'float';

	}
```
</details>

### `ScriptableValueNode.setup(): any`

**Returns:** `any`

**Calls:**

- `float (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
setup() {

		return this.value && this.value.isNode ? this.value : float();

	}
```
</details>

### `ScriptableValueNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`
- `arrayBufferToBase64 (from ../core/NodeUtils.js)`
- `this.value.toJSON`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		if ( this.value !== null ) {

			if ( this.inputType === 'ArrayBuffer' ) {

				data.value = arrayBufferToBase64( this.value );

			} else {

				data.value = this.value ? this.value.toJSON( data.meta ).uuid : null;

			}

		} else {

			data.value = null;

		}

		data.inputType = this.inputType;
		data.outputType = this.outputType;

	}
```
</details>

### `ScriptableValueNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`
- `base64ToArrayBuffer (from ../core/NodeUtils.js)`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		let value = null;

		if ( data.value !== null ) {

			if ( data.inputType === 'ArrayBuffer' ) {

				value = base64ToArrayBuffer( data.value );

			} else if ( data.inputType === 'Texture' ) {

				value = data.meta.textures[ data.value ];

			} else {

				value = data.meta.nodes[ data.value ] || null;

			}

		}

		this.value = value;

		this.inputType = data.inputType;
		this.outputType = data.outputType;

	}
```
</details>


---

## Classes

### `ScriptableValueNode`

<details><summary>Class Code</summary>

```ts
class ScriptableValueNode extends Node {

	static get type() {

		return 'ScriptableValueNode';

	}

	/**
	 * Constructs a new scriptable node.
	 *
	 * @param {any} [value=null] - The value.
	 */
	constructor( value = null ) {

		super();

		/**
		 * A reference to the value.
		 *
		 * @private
		 * @default null
		 */
		this._value = value;

		/**
		 * Depending on the type of `_value`, this property might cache parsed data.
		 *
		 * @private
		 * @default null
		 */
		this._cache = null;

		/**
		 * If this node represents an input, this property represents the input type.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.inputType = null;

		/**
		 * If this node represents an output, this property represents the output type.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.outputType = null;

		/**
		 * An event dispatcher for managing events.
		 *
		 * @type {EventDispatcher}
		 */
		this.events = new EventDispatcher();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isScriptableValueNode = true;

	}

	/**
	 * Whether this node represents an output or not.
	 *
	 * @type {boolean}
	 * @readonly
	 * @default true
	 */
	get isScriptableOutputNode() {

		return this.outputType !== null;

	}

	set value( val ) {

		if ( this._value === val ) return;

		if ( this._cache && this.inputType === 'URL' && this.value.value instanceof ArrayBuffer ) {

			URL.revokeObjectURL( this._cache );

			this._cache = null;

		}

		this._value = val;

		this.events.dispatchEvent( { type: 'change' } );

		this.refresh();

	}

	/**
	 * The node's value.
	 *
	 * @type {any}
	 */
	get value() {

		return this._value;

	}

	/**
	 * Dispatches the `refresh` event.
	 */
	refresh() {

		this.events.dispatchEvent( { type: 'refresh' } );

	}

	/**
	 * The `value` property usually represents a node or even binary data in form of array buffers.
	 * In this case, this method tries to return the actual value behind the complex type.
	 *
	 * @return {any} The value.
	 */
	getValue() {

		const value = this.value;

		if ( value && this._cache === null && this.inputType === 'URL' && value.value instanceof ArrayBuffer ) {

			this._cache = URL.createObjectURL( new Blob( [ value.value ] ) );

		} else if ( value && value.value !== null && value.value !== undefined && (
			( ( this.inputType === 'URL' || this.inputType === 'String' ) && typeof value.value === 'string' ) ||
			( this.inputType === 'Number' && typeof value.value === 'number' ) ||
			( this.inputType === 'Vector2' && value.value.isVector2 ) ||
			( this.inputType === 'Vector3' && value.value.isVector3 ) ||
			( this.inputType === 'Vector4' && value.value.isVector4 ) ||
			( this.inputType === 'Color' && value.value.isColor ) ||
			( this.inputType === 'Matrix3' && value.value.isMatrix3 ) ||
			( this.inputType === 'Matrix4' && value.value.isMatrix4 )
		) ) {

			return value.value;

		}

		return this._cache || value;

	}

	/**
	 * Overwritten since the node type is inferred from the value.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		return this.value && this.value.isNode ? this.value.getNodeType( builder ) : 'float';

	}

	setup() {

		return this.value && this.value.isNode ? this.value : float();

	}

	serialize( data ) {

		super.serialize( data );

		if ( this.value !== null ) {

			if ( this.inputType === 'ArrayBuffer' ) {

				data.value = arrayBufferToBase64( this.value );

			} else {

				data.value = this.value ? this.value.toJSON( data.meta ).uuid : null;

			}

		} else {

			data.value = null;

		}

		data.inputType = this.inputType;
		data.outputType = this.outputType;

	}

	deserialize( data ) {

		super.deserialize( data );

		let value = null;

		if ( data.value !== null ) {

			if ( data.inputType === 'ArrayBuffer' ) {

				value = base64ToArrayBuffer( data.value );

			} else if ( data.inputType === 'Texture' ) {

				value = data.meta.textures[ data.value ];

			} else {

				value = data.meta.nodes[ data.value ] || null;

			}

		}

		this.value = value;

		this.inputType = data.inputType;
		this.outputType = data.outputType;

	}

}
```
</details>

#### Methods

##### `refresh(): void`

<details><summary>Code</summary>

```ts
refresh() {

		this.events.dispatchEvent( { type: 'refresh' } );

	}
```
</details>

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		const value = this.value;

		if ( value && this._cache === null && this.inputType === 'URL' && value.value instanceof ArrayBuffer ) {

			this._cache = URL.createObjectURL( new Blob( [ value.value ] ) );

		} else if ( value && value.value !== null && value.value !== undefined && (
			( ( this.inputType === 'URL' || this.inputType === 'String' ) && typeof value.value === 'string' ) ||
			( this.inputType === 'Number' && typeof value.value === 'number' ) ||
			( this.inputType === 'Vector2' && value.value.isVector2 ) ||
			( this.inputType === 'Vector3' && value.value.isVector3 ) ||
			( this.inputType === 'Vector4' && value.value.isVector4 ) ||
			( this.inputType === 'Color' && value.value.isColor ) ||
			( this.inputType === 'Matrix3' && value.value.isMatrix3 ) ||
			( this.inputType === 'Matrix4' && value.value.isMatrix4 )
		) ) {

			return value.value;

		}

		return this._cache || value;

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.value && this.value.isNode ? this.value.getNodeType( builder ) : 'float';

	}
```
</details>

##### `setup(): any`

<details><summary>Code</summary>

```ts
setup() {

		return this.value && this.value.isNode ? this.value : float();

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		if ( this.value !== null ) {

			if ( this.inputType === 'ArrayBuffer' ) {

				data.value = arrayBufferToBase64( this.value );

			} else {

				data.value = this.value ? this.value.toJSON( data.meta ).uuid : null;

			}

		} else {

			data.value = null;

		}

		data.inputType = this.inputType;
		data.outputType = this.outputType;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		let value = null;

		if ( data.value !== null ) {

			if ( data.inputType === 'ArrayBuffer' ) {

				value = base64ToArrayBuffer( data.value );

			} else if ( data.inputType === 'Texture' ) {

				value = data.meta.textures[ data.value ];

			} else {

				value = data.meta.nodes[ data.value ] || null;

			}

		}

		this.value = value;

		this.inputType = data.inputType;
		this.outputType = data.outputType;

	}
```
</details>


---