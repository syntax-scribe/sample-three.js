[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PropertyNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/PropertyNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `nodeImmutable` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `nodeVar` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `PropertyNode.getHash(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `super.getHash`

<details><summary>Code</summary>

```typescript
getHash( builder ) {

		return this.name || super.getHash( builder );

	}
```
</details>

### `PropertyNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getVaryingFromNode`
- `builder.getVarFromNode`
- `builder.getPropertyName`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		let nodeVar;

		if ( this.varying === true ) {

			nodeVar = builder.getVaryingFromNode( this, this.name );
			nodeVar.needsInterpolation = true;

		} else {

			nodeVar = builder.getVarFromNode( this, this.name );

		}

		return builder.getPropertyName( nodeVar );

	}
```
</details>

### `property(type: string, name: string): PropertyNode`

**Parameters:**

- **`type`** `string`
- **`name`** `string`

**Returns:** `PropertyNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( type, name ) => nodeObject( new PropertyNode( type, name ) )
```
</details>

### `varyingProperty(type: string, name: string): PropertyNode`

**Parameters:**

- **`type`** `string`
- **`name`** `string`

**Returns:** `PropertyNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( type, name ) => nodeObject( new PropertyNode( type, name, true ) )
```
</details>


---

## Classes

### `PropertyNode`

<details><summary>Class Code</summary>

```ts
class PropertyNode extends Node {

	static get type() {

		return 'PropertyNode';

	}

	/**
	 * Constructs a new property node.
	 *
	 * @param {string} nodeType - The type of the node.
	 * @param {?string} [name=null] - The name of the property in the shader.
	 * @param {boolean} [varying=false] - Whether this property is a varying or not.
	 */
	constructor( nodeType, name = null, varying = false ) {

		super( nodeType );

		/**
		 * The name of the property in the shader. If no name is defined,
		 * the node system auto-generates one.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.name = name;

		/**
		 * Whether this property is a varying or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.varying = varying;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isPropertyNode = true;

		/**
		 * This flag is used for global cache.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

	}

	getHash( builder ) {

		return this.name || super.getHash( builder );

	}

	generate( builder ) {

		let nodeVar;

		if ( this.varying === true ) {

			nodeVar = builder.getVaryingFromNode( this, this.name );
			nodeVar.needsInterpolation = true;

		} else {

			nodeVar = builder.getVarFromNode( this, this.name );

		}

		return builder.getPropertyName( nodeVar );

	}

}
```
</details>

#### Methods

##### `getHash(builder: any): string`

<details><summary>Code</summary>

```ts
getHash( builder ) {

		return this.name || super.getHash( builder );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		let nodeVar;

		if ( this.varying === true ) {

			nodeVar = builder.getVaryingFromNode( this, this.name );
			nodeVar.needsInterpolation = true;

		} else {

			nodeVar = builder.getVarFromNode( this, this.name );

		}

		return builder.getPropertyName( nodeVar );

	}
```
</details>


---