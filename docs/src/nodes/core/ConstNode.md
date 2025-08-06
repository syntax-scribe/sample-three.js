[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ConstNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/ConstNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InputNode` | `./InputNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_regNum` | `RegExp` | let/var | `/float\|u?int/` | ✗ |


---

## Functions

### `ConstNode.generateConst(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Generates the shader string of the value with the current node builder.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated value as a shader string.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.generateConst`
- `this.getNodeType`

<details><summary>Code</summary>

```typescript
generateConst( builder ) {

		return builder.generateConst( this.getNodeType( builder ), this.value );

	}
```
</details>

### `ConstNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`
- `_regNum.test`
- `builder.generateConst`
- `builder.format`
- `this.generateConst`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const type = this.getNodeType( builder );

		if ( _regNum.test( type ) && _regNum.test( output ) ) {

			return builder.generateConst( output, this.value );

		}

		return builder.format( this.generateConst( builder ), type, output );

	}
```
</details>


---

## Classes

### `ConstNode`

<details><summary>Class Code</summary>

```ts
class ConstNode extends InputNode {

	static get type() {

		return 'ConstNode';

	}

	/**
	 * Constructs a new input node.
	 *
	 * @param {any} value - The value of this node. Usually a JS primitive or three.js object (vector, matrix, color).
	 * @param {?string} nodeType - The node type. If no explicit type is defined, the node tries to derive the type from its value.
	 */
	constructor( value, nodeType = null ) {

		super( value, nodeType );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isConstNode = true;

	}

	/**
	 * Generates the shader string of the value with the current node builder.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated value as a shader string.
	 */
	generateConst( builder ) {

		return builder.generateConst( this.getNodeType( builder ), this.value );

	}

	generate( builder, output ) {

		const type = this.getNodeType( builder );

		if ( _regNum.test( type ) && _regNum.test( output ) ) {

			return builder.generateConst( output, this.value );

		}

		return builder.format( this.generateConst( builder ), type, output );

	}

}
```
</details>

#### Methods

##### `generateConst(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
generateConst( builder ) {

		return builder.generateConst( this.getNodeType( builder ), this.value );

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const type = this.getNodeType( builder );

		if ( _regNum.test( type ) && _regNum.test( output ) ) {

			return builder.generateConst( output, this.value );

		}

		return builder.format( this.generateConst( builder ), type, output );

	}
```
</details>


---