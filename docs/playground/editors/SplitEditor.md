[⬅️ Back to Table of Contents](../../index.md)

# 📄 `SplitEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/SplitEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LabelElement` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `nodeObject` | `three/tsl` |
| `float` | `three/tsl` |
| `setInputAestheticsFromType` | `../DataTypeLib.js` |
| `setOutputAestheticsFromType` | `../DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `node` | `any` | let/var | `null` | ✗ |


---

## Classes

### `SplitEditor`

<details><summary>Class Code</summary>

```ts
export class SplitEditor extends BaseNodeEditor {

	constructor() {

		super( 'Split', null, 175 );

		let node = null;

		const inputElement = setInputAestheticsFromType( new LabelElement( 'Input' ), 'node' ).onConnect( () => {

			node = inputElement.getLinkedObject();

			if ( node !== null ) {

				xElement.setObject( nodeObject( node ).x );
				yElement.setObject( nodeObject( node ).y );
				zElement.setObject( nodeObject( node ).z );
				wElement.setObject( nodeObject( node ).w );

			} else {

				xElement.setObject( float() );
				yElement.setObject( float() );
				zElement.setObject( float() );
				wElement.setObject( float() );

			}

		} );

		const xElement = setOutputAestheticsFromType( new LabelElement( 'x | r' ), 'Number' ).setObject( float() );
		const yElement = setOutputAestheticsFromType( new LabelElement( 'y | g' ), 'Number' ).setObject( float() );
		const zElement = setOutputAestheticsFromType( new LabelElement( 'z | b' ), 'Number' ).setObject( float() );
		const wElement = setOutputAestheticsFromType( new LabelElement( 'w | a' ), 'Number' ).setObject( float() );

		this.add( inputElement )
			.add( xElement )
			.add( yElement )
			.add( zElement )
			.add( wElement );

	}

}
```
</details>


---