[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DebugNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/DebugNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `callback` | `any` | let/var | `this.callback` | ✗ |
| `title` | `string` | let/var | `'--- TSL debug - ' + builder.shaderStage + ' shader ---'` | ✗ |
| `code` | `string` | let/var | `''` | ✗ |


---

## Functions

### `DebugNode.getNodeType(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.node.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.node.getNodeType( builder );

	}
```
</details>

### `DebugNode.setup(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.node.build`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		return this.node.build( builder );

	}
```
</details>

### `DebugNode.analyze(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.node.build`

<details><summary>Code</summary>

```typescript
analyze( builder ) {

		return this.node.build( builder );

	}
```
</details>

### `DebugNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.node.build`
- `'-'.repeat`
- `builder.flow.code.replace`
- `callback`
- `console.log`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const callback = this.callback;
		const snippet = this.node.build( builder );

		const title = '--- TSL debug - ' + builder.shaderStage + ' shader ---';
		const border = '-'.repeat( title.length );

		let code = '';
		code += '// #' + title + '#\n';
		code += builder.flow.code.replace( /^\t/mg, '' ) + '\n';
		code += '/* ... */ ' + snippet + ' /* ... */\n';
		code += '// #' + border + '#\n';

		if ( callback !== null ) {

			callback( builder, code );

		} else {

			console.log( code );

		}

		return snippet;

	}
```
</details>

### `debug(node: Node, callback: Function): DebugNode`

**Parameters:**

- **`node`** `Node`
- **`callback`** `Function`

**Returns:** `DebugNode`

**Calls:**

- `nodeObject( new DebugNode( nodeObject( node ), callback ) ).toStack`

<details><summary>Code</summary>

```typescript
( node, callback = null ) => nodeObject( new DebugNode( nodeObject( node ), callback ) ).toStack()
```
</details>


---

## Classes

### `DebugNode`

<details><summary>Class Code</summary>

```ts
class DebugNode extends TempNode {

	static get type() {

		return 'DebugNode';

	}

	constructor( node, callback = null ) {

		super();

		this.node = node;
		this.callback = callback;

	}

	getNodeType( builder ) {

		return this.node.getNodeType( builder );

	}

	setup( builder ) {

		return this.node.build( builder );

	}

	analyze( builder ) {

		return this.node.build( builder );

	}

	generate( builder ) {

		const callback = this.callback;
		const snippet = this.node.build( builder );

		const title = '--- TSL debug - ' + builder.shaderStage + ' shader ---';
		const border = '-'.repeat( title.length );

		let code = '';
		code += '// #' + title + '#\n';
		code += builder.flow.code.replace( /^\t/mg, '' ) + '\n';
		code += '/* ... */ ' + snippet + ' /* ... */\n';
		code += '// #' + border + '#\n';

		if ( callback !== null ) {

			callback( builder, code );

		} else {

			console.log( code );

		}

		return snippet;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): any`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.node.getNodeType( builder );

	}
```
</details>

##### `setup(builder: any): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		return this.node.build( builder );

	}
```
</details>

##### `analyze(builder: any): any`

<details><summary>Code</summary>

```ts
analyze( builder ) {

		return this.node.build( builder );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const callback = this.callback;
		const snippet = this.node.build( builder );

		const title = '--- TSL debug - ' + builder.shaderStage + ' shader ---';
		const border = '-'.repeat( title.length );

		let code = '';
		code += '// #' + title + '#\n';
		code += builder.flow.code.replace( /^\t/mg, '' ) + '\n';
		code += '/* ... */ ' + snippet + ' /* ... */\n';
		code += '// #' + border + '#\n';

		if ( callback !== null ) {

			callback( builder, code );

		} else {

			console.log( code );

		}

		return snippet;

	}
```
</details>


---