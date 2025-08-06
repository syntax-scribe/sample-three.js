[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SubBuildNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/SubBuildNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `nodeObject` | `../tsl/TSLCore.js` |


---

## Functions

### `SubBuildNode.getNodeType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `builder.addSubBuild`
- `this.node.getNodeType`
- `builder.removeSubBuild`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		if ( this.nodeType !== null ) return this.nodeType;

		builder.addSubBuild( this.name );

		const nodeType = this.node.getNodeType( builder );

		builder.removeSubBuild();

		return nodeType;

	}
```
</details>

### `SubBuildNode.build(builder: any, params: any[]): string | Node`

**Parameters:**

- **`builder`** `any`
- **`params`** `any[]`

**Returns:** `string | Node`

**Calls:**

- `builder.addSubBuild`
- `this.node.build`
- `builder.removeSubBuild`

<details><summary>Code</summary>

```typescript
build( builder, ...params ) {

		builder.addSubBuild( this.name );

		const data = this.node.build( builder, ...params );

		builder.removeSubBuild();

		return data;

	}
```
</details>

### `subBuild(node: Node, name: string, type: string): Node`

**Parameters:**

- **`node`** `Node`
- **`name`** `string`
- **`type`** `string`

**Returns:** `Node`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( node, name, type = null ) => nodeObject( new SubBuildNode( nodeObject( node ), name, type ) )
```
</details>


---

## Classes

### `SubBuildNode`

<details><summary>Class Code</summary>

```ts
class SubBuildNode extends Node {

	static get type() {

		return 'SubBuild';

	}

	constructor( node, name, nodeType = null ) {

		super( nodeType );

		/**
		 * The node to be built in the sub-build.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * The name of the sub-build.
		 *
		 * @type {string}
		 */
		this.name = name;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSubBuildNode = true;

	}

	getNodeType( builder ) {

		if ( this.nodeType !== null ) return this.nodeType;

		builder.addSubBuild( this.name );

		const nodeType = this.node.getNodeType( builder );

		builder.removeSubBuild();

		return nodeType;

	}

	build( builder, ...params ) {

		builder.addSubBuild( this.name );

		const data = this.node.build( builder, ...params );

		builder.removeSubBuild();

		return data;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		if ( this.nodeType !== null ) return this.nodeType;

		builder.addSubBuild( this.name );

		const nodeType = this.node.getNodeType( builder );

		builder.removeSubBuild();

		return nodeType;

	}
```
</details>

##### `build(builder: any, params: any[]): string | Node`

<details><summary>Code</summary>

```ts
build( builder, ...params ) {

		builder.addSubBuild( this.name );

		const data = this.node.build( builder, ...params );

		builder.removeSubBuild();

		return data;

	}
```
</details>


---