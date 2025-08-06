[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StructNode.js`

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
📂 **`src/nodes/core/StructNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `StructTypeNode` | `./StructTypeNode.js` |
| `nodeObject` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `structType` | `any` | let/var | `nodeVar.type` | ✗ |
| `structLayout` | `StructTypeNode` | let/var | `new StructTypeNode( membersLayout, name )` | ✗ |
| `values` | `any` | let/var | `null` | ✗ |


---

## Functions

### `StructNode.getNodeType(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.structLayoutNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.structLayoutNode.getNodeType( builder );

	}
```
</details>

### `StructNode.getMemberType(builder: any, name: any): any`

**Parameters:**

- **`builder`** `any`
- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.structLayoutNode.getMemberType`

<details><summary>Code</summary>

```typescript
getMemberType( builder, name ) {

		return this.structLayoutNode.getMemberType( builder, name );

	}
```
</details>

### `StructNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getVarFromNode`
- `builder.getPropertyName`
- `builder.addLineFlowCode`
- `builder.generateStruct`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const nodeVar = builder.getVarFromNode( this );
		const structType = nodeVar.type;
		const propertyName = builder.getPropertyName( nodeVar );

		builder.addLineFlowCode( `${ propertyName } = ${ builder.generateStruct( structType, this.structLayoutNode.membersLayout, this.values ) }`, this );

		return nodeVar.name;

	}
```
</details>

### `struct(membersLayout: any, name: string): Function`

**Parameters:**

- **`membersLayout`** `any`
- **`name`** `string`

**Returns:** `Function`

**Calls:**

- `Object.keys`
- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( membersLayout, name = null ) => {

	const structLayout = new StructTypeNode( membersLayout, name );

	const struct = ( ...params ) => {

		let values = null;

		if ( params.length > 0 ) {

			if ( params[ 0 ].isNode ) {

				values = {};

				const names = Object.keys( membersLayout );

				for ( let i = 0; i < params.length; i ++ ) {

					values[ names[ i ] ] = params[ i ];

				}

			} else {

				values = params[ 0 ];

			}

		}

		return nodeObject( new StructNode( structLayout, values ) );

	};

	struct.layout = structLayout;
	struct.isStruct = true;

	return struct;

}
```
</details>

### `struct(params: any[]): any`

**Parameters:**

- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `Object.keys`
- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( ...params ) => {

		let values = null;

		if ( params.length > 0 ) {

			if ( params[ 0 ].isNode ) {

				values = {};

				const names = Object.keys( membersLayout );

				for ( let i = 0; i < params.length; i ++ ) {

					values[ names[ i ] ] = params[ i ];

				}

			} else {

				values = params[ 0 ];

			}

		}

		return nodeObject( new StructNode( structLayout, values ) );

	}
```
</details>


---

## Classes

### `StructNode`

<details><summary>Class Code</summary>

```ts
class StructNode extends Node {

	static get type() {

		return 'StructNode';

	}

	constructor( structLayoutNode, values ) {

		super( 'vec3' );

		this.structLayoutNode = structLayoutNode;
		this.values = values;

		this.isStructNode = true;

	}

	getNodeType( builder ) {

		return this.structLayoutNode.getNodeType( builder );

	}

	getMemberType( builder, name ) {

		return this.structLayoutNode.getMemberType( builder, name );

	}

	generate( builder ) {

		const nodeVar = builder.getVarFromNode( this );
		const structType = nodeVar.type;
		const propertyName = builder.getPropertyName( nodeVar );

		builder.addLineFlowCode( `${ propertyName } = ${ builder.generateStruct( structType, this.structLayoutNode.membersLayout, this.values ) }`, this );

		return nodeVar.name;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): any`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.structLayoutNode.getNodeType( builder );

	}
```
</details>

##### `getMemberType(builder: any, name: any): any`

<details><summary>Code</summary>

```ts
getMemberType( builder, name ) {

		return this.structLayoutNode.getMemberType( builder, name );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const nodeVar = builder.getVarFromNode( this );
		const structType = nodeVar.type;
		const propertyName = builder.getPropertyName( nodeVar );

		builder.addLineFlowCode( `${ propertyName } = ${ builder.generateStruct( structType, this.structLayoutNode.membersLayout, this.values ) }`, this );

		return nodeVar.name;

	}
```
</details>


---