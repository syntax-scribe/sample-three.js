[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CodeNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/code/CodeNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |


---

## Functions

### `CodeNode.setIncludes(includes: Node[]): CodeNode`

**JSDoc:**
```typescript
/**
	 * Sets the includes of this code node.
	 *
	 * @param {Array<Node>} includes - The includes to set.
	 * @return {CodeNode} A reference to this node.
	 */
```

**Parameters:**

- **`includes`** `Node[]`

**Returns:** `CodeNode`

<details><summary>Code</summary>

```typescript
setIncludes( includes ) {

		this.includes = includes;

		return this;

	}
```
</details>

### `CodeNode.getIncludes(): Node[]`

**JSDoc:**
```typescript
/**
	 * Returns the includes of this code node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Array<Node>} The includes.
	 */
```

**Returns:** `Node[]`

<details><summary>Code</summary>

```typescript
getIncludes( /*builder*/ ) {

		return this.includes;

	}
```
</details>

### `CodeNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getIncludes`
- `include.build`
- `builder.getCodeFromNode`
- `this.getNodeType`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const includes = this.getIncludes( builder );

		for ( const include of includes ) {

			include.build( builder );

		}

		const nodeCode = builder.getCodeFromNode( this, this.getNodeType( builder ) );
		nodeCode.code = this.code;

		return nodeCode.code;

	}
```
</details>

### `CodeNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.code = this.code;
		data.language = this.language;

	}
```
</details>

### `CodeNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.code = data.code;
		this.language = data.language;

	}
```
</details>

### `js(src: string, includes: Node[]): CodeNode`

**Parameters:**

- **`src`** `string`
- **`includes`** `Node[]`

**Returns:** `CodeNode`

**Calls:**

- `code`

<details><summary>Code</summary>

```typescript
( src, includes ) => code( src, includes, 'js' )
```
</details>

### `wgsl(src: string, includes: Node[]): CodeNode`

**Parameters:**

- **`src`** `string`
- **`includes`** `Node[]`

**Returns:** `CodeNode`

**Calls:**

- `code`

<details><summary>Code</summary>

```typescript
( src, includes ) => code( src, includes, 'wgsl' )
```
</details>

### `glsl(src: string, includes: Node[]): CodeNode`

**Parameters:**

- **`src`** `string`
- **`includes`** `Node[]`

**Returns:** `CodeNode`

**Calls:**

- `code`

<details><summary>Code</summary>

```typescript
( src, includes ) => code( src, includes, 'glsl' )
```
</details>


---

## Classes

### `CodeNode`

<details><summary>Class Code</summary>

```ts
class CodeNode extends Node {

	static get type() {

		return 'CodeNode';

	}

	/**
	 * Constructs a new code node.
	 *
	 * @param {string} [code=''] - The native code.
	 * @param {Array<Node>} [includes=[]] - An array of includes.
	 * @param {('js'|'wgsl'|'glsl')} [language=''] - The used language.
	 */
	constructor( code = '', includes = [], language = '' ) {

		super( 'code' );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCodeNode = true;

		/**
		 * This flag is used for global cache.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

		/**
		 * The native code.
		 *
		 * @type {string}
		 * @default ''
		 */
		this.code = code;

		/**
		 * An array of includes
		 *
		 * @type {Array<Node>}
		 * @default []
		 */
		this.includes = includes;

		/**
		 * The used language.
		 *
		 * @type {('js'|'wgsl'|'glsl')}
		 * @default ''
		 */
		this.language = language;

	}

	/**
	 * Sets the includes of this code node.
	 *
	 * @param {Array<Node>} includes - The includes to set.
	 * @return {CodeNode} A reference to this node.
	 */
	setIncludes( includes ) {

		this.includes = includes;

		return this;

	}

	/**
	 * Returns the includes of this code node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Array<Node>} The includes.
	 */
	getIncludes( /*builder*/ ) {

		return this.includes;

	}

	generate( builder ) {

		const includes = this.getIncludes( builder );

		for ( const include of includes ) {

			include.build( builder );

		}

		const nodeCode = builder.getCodeFromNode( this, this.getNodeType( builder ) );
		nodeCode.code = this.code;

		return nodeCode.code;

	}

	serialize( data ) {

		super.serialize( data );

		data.code = this.code;
		data.language = this.language;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.code = data.code;
		this.language = data.language;

	}

}
```
</details>

#### Methods

##### `setIncludes(includes: Node[]): CodeNode`

<details><summary>Code</summary>

```ts
setIncludes( includes ) {

		this.includes = includes;

		return this;

	}
```
</details>

##### `getIncludes(): Node[]`

<details><summary>Code</summary>

```ts
getIncludes( /*builder*/ ) {

		return this.includes;

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const includes = this.getIncludes( builder );

		for ( const include of includes ) {

			include.build( builder );

		}

		const nodeCode = builder.getCodeFromNode( this, this.getNodeType( builder ) );
		nodeCode.code = this.code;

		return nodeCode.code;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.code = this.code;
		data.language = this.language;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.code = data.code;
		this.language = data.language;

	}
```
</details>


---