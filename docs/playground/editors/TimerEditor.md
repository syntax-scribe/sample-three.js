[⬅️ Back to Table of Contents](../../index.md)

# 📄 `TimerEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/TimerEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NumberInput` | `flow` |
| `LabelElement` | `flow` |
| `Element` | `flow` |
| `ButtonInput` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `timerLocal` | `three/tsl` |


---

## Functions

### `updateField(): void`

**Returns:** `void`

**Calls:**

- `field.setValue`
- `node.value.toFixed`

<details><summary>Code</summary>

```typescript
() => {

			field.setValue( node.value.toFixed( 3 ) );

		}
```
</details>


---

## Classes

### `TimerEditor`

<details><summary>Class Code</summary>

```ts
export class TimerEditor extends BaseNodeEditor {

	constructor() {

		const node = timerLocal();

		super( 'Timer', node, 200 );

		this.title.setIcon( 'ti ti-clock' );

		const updateField = () => {

			field.setValue( node.value.toFixed( 3 ) );

		};

		const field = new NumberInput().onChange( () => {

			node.value = field.getValue();

		} );

		const scaleField = new NumberInput( 1 ).onChange( () => {

			node.scale = scaleField.getValue();

		} );

		const moreElement = new Element().add( new ButtonInput( 'Reset' ).onClick( () => {

			node.value = 0;

			updateField();

		} ) ).setSerializable( false );

		this.add( new Element().add( field ).setSerializable( false ) )
			.add( new LabelElement( 'Speed' ).add( scaleField ) )
			.add( moreElement );

		// extends node

		node._update = node.update;
		node.update = function ( ...params ) {

			this._update( ...params );

			updateField();

		};

	}

}
```
</details>


---