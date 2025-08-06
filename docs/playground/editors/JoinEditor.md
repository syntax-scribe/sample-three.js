[⬅️ Back to Table of Contents](../../index.md)

# 📄 `JoinEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/JoinEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LabelElement` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `JoinNode` | `three/webgpu` |
| `UniformNode` | `three/webgpu` |
| `float` | `three/tsl` |
| `setInputAestheticsFromType` | `../DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `NULL_VALUE` | `any` | let/var | `new UniformNode( 0 )` | ✗ |
| `node` | `any` | let/var | `new JoinNode()` | ✗ |
| `values` | `any[]` | let/var | `[ xElement.getLinkedObject(), yElement.getLinkedObject(), zElement.getLinkedO...` | ✗ |
| `length` | `number` | let/var | `1` | ✗ |
| `nodes` | `any[]` | let/var | `[]` | ✗ |


---

## Functions

### `update(): void`

**Returns:** `void`

**Calls:**

- `xElement.getLinkedObject`
- `yElement.getLinkedObject`
- `zElement.getLinkedObject`
- `wElement.getLinkedObject`
- `nodes.push`
- `float (from three/tsl)`
- `this.invalidate`
- `this.title.setOutput`

<details><summary>Code</summary>

```typescript
() => {

			const values = [
				xElement.getLinkedObject(),
				yElement.getLinkedObject(),
				zElement.getLinkedObject(),
				wElement.getLinkedObject()
			];

			let length = 1;

			if ( values[ 3 ] !== null ) length = 4;
			else if ( values[ 2 ] !== null ) length = 3;
			else if ( values[ 1 ] !== null ) length = 2;

			const nodes = [];

			for ( let i = 0; i < length; i ++ ) {

				nodes.push( float( values[ i ] || NULL_VALUE ) );

			}

			node.nodes = nodes;

			this.invalidate();

			this.title.setOutput( length );

		}
```
</details>


---

## Classes

### `JoinEditor`

<details><summary>Class Code</summary>

```ts
export class JoinEditor extends BaseNodeEditor {

	constructor() {

		const node = new JoinNode();

		super( 'Join', node, 175 );

		const update = () => {

			const values = [
				xElement.getLinkedObject(),
				yElement.getLinkedObject(),
				zElement.getLinkedObject(),
				wElement.getLinkedObject()
			];

			let length = 1;

			if ( values[ 3 ] !== null ) length = 4;
			else if ( values[ 2 ] !== null ) length = 3;
			else if ( values[ 1 ] !== null ) length = 2;

			const nodes = [];

			for ( let i = 0; i < length; i ++ ) {

				nodes.push( float( values[ i ] || NULL_VALUE ) );

			}

			node.nodes = nodes;

			this.invalidate();

			this.title.setOutput( length );

		};

		const xElement = setInputAestheticsFromType( new LabelElement( 'x | r' ), 'Number' ).onConnect( update );
		const yElement = setInputAestheticsFromType( new LabelElement( 'y | g' ), 'Number' ).onConnect( update );
		const zElement = setInputAestheticsFromType( new LabelElement( 'z | b' ), 'Number' ).onConnect( update );
		const wElement = setInputAestheticsFromType( new LabelElement( 'w | a' ), 'Number' ).onConnect( update );

		this.add( xElement )
			.add( yElement )
			.add( zElement )
			.add( wElement );

		update();

	}

}
```
</details>


---