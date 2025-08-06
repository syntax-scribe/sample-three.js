[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ColorEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/ColorEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ColorInput` | `flow` |
| `StringInput` | `flow` |
| `NumberInput` | `flow` |
| `LabelElement` | `flow` |
| `Element` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `Color` | `three` |
| `UniformNode` | `three/webgpu` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `v` | `any` | let/var | `new Color()` | ✗ |
| `node` | `any` | let/var | `new UniformNode( v )` | ✗ |
| `value` | `any` | let/var | `node.value` | ✗ |


---

## Functions

### `updateFields(editing: any): void`

**Parameters:**

- **`editing`** `any`

**Returns:** `void`

**Calls:**

- `value.getHex`
- `hexValue.toString( 16 ).toUpperCase().padStart`
- `field.setValue`
- `hexField.setValue`
- `fieldR.setValue`
- `value.r.toFixed`
- `fieldG.setValue`
- `value.g.toFixed`
- `fieldB.setValue`
- `value.b.toFixed`
- `fieldR.setTagColor`
- `hexString.slice`
- `fieldG.setTagColor`
- `fieldB.setTagColor`
- `this.invalidate`

<details><summary>Code</summary>

```typescript
( editing ) => {

			const value = node.value;
			const hexValue = value.getHex();
			const hexString = hexValue.toString( 16 ).toUpperCase().padStart( 6, '0' );

			if ( editing !== 'color' ) {

				field.setValue( hexValue, false );

			}

			if ( editing !== 'hex' ) {

				hexField.setValue( '#' + hexString, false );

			}

			if ( editing !== 'rgb' ) {

				fieldR.setValue( value.r.toFixed( 3 ), false );
				fieldG.setValue( value.g.toFixed( 3 ), false );
				fieldB.setValue( value.b.toFixed( 3 ), false );

			}

			fieldR.setTagColor( `#${hexString.slice( 0, 2 )}0000` );
			fieldG.setTagColor( `#00${hexString.slice( 2, 4 )}00` );
			fieldB.setTagColor( `#0000${hexString.slice( 4, 6 )}` );

			this.invalidate(); // it's important to scriptable nodes ( cpu nodes needs update )

		}
```
</details>

### `onChangeRGB(): void`

**Returns:** `void`

**Calls:**

- `node.value.setRGB`
- `fieldR.getValue`
- `fieldG.getValue`
- `fieldB.getValue`
- `updateFields`

<details><summary>Code</summary>

```typescript
() => {

			node.value.setRGB( fieldR.getValue(), fieldG.getValue(), fieldB.getValue() );

			updateFields( 'rgb' );

		}
```
</details>


---

## Classes

### `ColorEditor`

<details><summary>Class Code</summary>

```ts
export class ColorEditor extends BaseNodeEditor {

	constructor() {

		const v = new Color();
		const node = new UniformNode( v );

		super( 'Color', node );

		const updateFields = ( editing ) => {

			const value = node.value;
			const hexValue = value.getHex();
			const hexString = hexValue.toString( 16 ).toUpperCase().padStart( 6, '0' );

			if ( editing !== 'color' ) {

				field.setValue( hexValue, false );

			}

			if ( editing !== 'hex' ) {

				hexField.setValue( '#' + hexString, false );

			}

			if ( editing !== 'rgb' ) {

				fieldR.setValue( value.r.toFixed( 3 ), false );
				fieldG.setValue( value.g.toFixed( 3 ), false );
				fieldB.setValue( value.b.toFixed( 3 ), false );

			}

			fieldR.setTagColor( `#${hexString.slice( 0, 2 )}0000` );
			fieldG.setTagColor( `#00${hexString.slice( 2, 4 )}00` );
			fieldB.setTagColor( `#0000${hexString.slice( 4, 6 )}` );

			this.invalidate(); // it's important to scriptable nodes ( cpu nodes needs update )

		};

		const field = new ColorInput( 0xFFFFFF ).onChange( () => {

			node.value.setHex( field.getValue() );

			updateFields( 'picker' );

		} );

		const hexField = new StringInput().onChange( () => {

			const value = hexField.getValue();

			if ( value.indexOf( '#' ) === 0 ) {

				const hexStr = value.slice( 1 ).padEnd( 6, '0' );

				node.value.setHex( parseInt( hexStr, 16 ) );

				updateFields( 'hex' );

			}

		} );

		hexField.addEventListener( 'blur', () => {

			updateFields();

		} );

		const onChangeRGB = () => {

			node.value.setRGB( fieldR.getValue(), fieldG.getValue(), fieldB.getValue() );

			updateFields( 'rgb' );

		};

		const fieldR = new NumberInput( 1, 0, 1 ).setTagColor( 'red' ).onChange( onChangeRGB );
		const fieldG = new NumberInput( 1, 0, 1 ).setTagColor( 'green' ).onChange( onChangeRGB );
		const fieldB = new NumberInput( 1, 0, 1 ).setTagColor( 'blue' ).onChange( onChangeRGB );

		this.add( new Element().add( field ).setSerializable( false ) )
			.add( new LabelElement( 'Hex' ).add( hexField ).setSerializable( false ) )
			.add( new LabelElement( 'RGB' ).add( fieldR ).add( fieldG ).add( fieldB ) );

		updateFields();

	}

}
```
</details>


---