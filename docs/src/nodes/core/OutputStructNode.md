[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `OutputStructNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/OutputStructNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `members` | `Node[]` | let/var | `this.members` | ✗ |
| `membersLayout` | `any[]` | let/var | `[]` | ✗ |
| `name` | `string` | let/var | `'m' + i` | ✗ |
| `members` | `Node[]` | let/var | `this.members` | ✗ |
| `structPrefix` | `string` | let/var | `propertyName !== '' ? propertyName + '.' : ''` | ✗ |


---

## Functions

### `OutputStructNode.getNodeType(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `members[ i ].getNodeType`
- `membersLayout.push`
- `builder.getOutputStructTypeFromNode`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		const properties = builder.getNodeProperties( this );

		if ( properties.membersLayout === undefined ) {

			const members = this.members;
			const membersLayout = [];

			for ( let i = 0; i < members.length; i ++ ) {

				const name = 'm' + i;
				const type = members[ i ].getNodeType( builder );

				membersLayout.push( { name, type, index: i } );

			}

			properties.membersLayout = membersLayout;
			properties.structType = builder.getOutputStructTypeFromNode( this, properties.membersLayout );

		}

		return properties.structType.name;

	}
```
</details>

### `OutputStructNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getOutputStructName`
- `members[ i ].build`
- `builder.addLineFlowCode`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const propertyName = builder.getOutputStructName();
		const members = this.members;

		const structPrefix = propertyName !== '' ? propertyName + '.' : '';

		for ( let i = 0; i < members.length; i ++ ) {

			const snippet = members[ i ].build( builder );

			builder.addLineFlowCode( `${ structPrefix }m${ i } = ${ snippet }`, this );

		}

		return propertyName;

	}
```
</details>


---

## Classes

### `OutputStructNode`

<details><summary>Class Code</summary>

```ts
class OutputStructNode extends Node {

	static get type() {

		return 'OutputStructNode';

	}

	/**
	 * Constructs a new output struct node. The constructor can be invoked with an
	 * arbitrary number of nodes representing the members.
	 *
	 * @param {...Node} members - A parameter list of nodes.
	 */
	constructor( ...members ) {

		super();

		/**
		 * An array of nodes which defines the output.
		 *
		 * @type {Array<Node>}
		 */
		this.members = members;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isOutputStructNode = true;

	}

	getNodeType( builder ) {

		const properties = builder.getNodeProperties( this );

		if ( properties.membersLayout === undefined ) {

			const members = this.members;
			const membersLayout = [];

			for ( let i = 0; i < members.length; i ++ ) {

				const name = 'm' + i;
				const type = members[ i ].getNodeType( builder );

				membersLayout.push( { name, type, index: i } );

			}

			properties.membersLayout = membersLayout;
			properties.structType = builder.getOutputStructTypeFromNode( this, properties.membersLayout );

		}

		return properties.structType.name;

	}

	generate( builder ) {

		const propertyName = builder.getOutputStructName();
		const members = this.members;

		const structPrefix = propertyName !== '' ? propertyName + '.' : '';

		for ( let i = 0; i < members.length; i ++ ) {

			const snippet = members[ i ].build( builder );

			builder.addLineFlowCode( `${ structPrefix }m${ i } = ${ snippet }`, this );

		}

		return propertyName;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): any`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		const properties = builder.getNodeProperties( this );

		if ( properties.membersLayout === undefined ) {

			const members = this.members;
			const membersLayout = [];

			for ( let i = 0; i < members.length; i ++ ) {

				const name = 'm' + i;
				const type = members[ i ].getNodeType( builder );

				membersLayout.push( { name, type, index: i } );

			}

			properties.membersLayout = membersLayout;
			properties.structType = builder.getOutputStructTypeFromNode( this, properties.membersLayout );

		}

		return properties.structType.name;

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const propertyName = builder.getOutputStructName();
		const members = this.members;

		const structPrefix = propertyName !== '' ? propertyName + '.' : '';

		for ( let i = 0; i < members.length; i ++ ) {

			const snippet = members[ i ].build( builder );

			builder.addLineFlowCode( `${ structPrefix }m${ i } = ${ snippet }`, this );

		}

		return propertyName;

	}
```
</details>


---