[⬅️ Back to Table of Contents](../../index.md)

# 📄 `SliderEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/SliderEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ButtonInput` | `flow` |
| `SliderInput` | `flow` |
| `NumberInput` | `flow` |
| `LabelElement` | `flow` |
| `Element` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `float` | `three/tsl` |


---

## Functions

### `updateRange(): void`

**Returns:** `void`

**Calls:**

- `minInput.getValue`
- `maxInput.getValue`
- `field.setRange`
- `maxInput.setValue`

<details><summary>Code</summary>

```typescript
() => {

			const min = minInput.getValue();
			const max = maxInput.getValue();

			if ( min <= max ) {

				field.setRange( min, max );

			} else {

				maxInput.setValue( min );

			}

		}
```
</details>


---

## Classes

### `SliderEditor`

<details><summary>Class Code</summary>

```ts
export class SliderEditor extends BaseNodeEditor {

	constructor() {

		const node = float( 0 );

		super( 'Slider', node );

		this.collapse = true;

		const field = new SliderInput( 0, 0, 1 ).onChange( () => {

			node.value = field.getValue();

		} );

		const updateRange = () => {

			const min = minInput.getValue();
			const max = maxInput.getValue();

			if ( min <= max ) {

				field.setRange( min, max );

			} else {

				maxInput.setValue( min );

			}

		};

		const minInput = new NumberInput().onChange( updateRange );
		const maxInput = new NumberInput( 1 ).onChange( updateRange );

		const minElement = new LabelElement( 'Min.' ).add( minInput ).setVisible( false );
		const maxElement = new LabelElement( 'Max.' ).add( maxInput ).setVisible( false );

		const moreElement = new Element().add( new ButtonInput( 'More' ).onClick( () => {

			minElement.setVisible( true );
			maxElement.setVisible( true );
			moreElement.setVisible( false );

		} ) ).setSerializable( false );

		this.add( new Element().add( field ) )
			.add( minElement )
			.add( maxElement )
			.add( moreElement );

		this.onBlur( () => {

			minElement.setVisible( false );
			maxElement.setVisible( false );
			moreElement.setVisible( true );

		} );

	}

}
```
</details>


---