[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ui.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 71 |
| 🧱 Classes | 21 |
| 📊 Variables & Constants | 40 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/libs/ui.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `argument` | `any` | let/var | `arguments[ i ]` | ✗ |
| `argument` | `any` | let/var | `arguments[ i ]` | ✗ |
| `properties` | `string[]` | let/var | `[ 'position', 'left', 'top', 'right', 'bottom', 'width', 'height', 'display',...` | ✗ |
| `method` | `string` | let/var | `'set' + property.substring( 0, 1 ).toUpperCase() + property.substring( 1 )` | ✗ |
| `events` | `string[]` | let/var | `[ 'KeyUp', 'KeyDown', 'MouseOver', 'MouseOut', 'Click', 'DblClick', 'Change',...` | ✗ |
| `method` | `string` | let/var | `'on' + event` | ✗ |
| `cursor` | `undefined` | let/var | `this.selectionStart` | ✗ |
| `selected` | `any` | let/var | `this.dom.value` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `changeEvent` | `Event` | let/var | `new Event( 'change', { bubbles: true, cancelable: true } )` | ✗ |
| `distance` | `number` | let/var | `0` | ✗ |
| `onMouseDownValue` | `number` | let/var | `0` | ✗ |
| `pointer` | `{ x: number; y: number; }` | let/var | `{ x: 0, y: 0 }` | ✗ |
| `prevPointer` | `{ x: number; y: number; }` | let/var | `{ x: 0, y: 0 }` | ✗ |
| `currentValue` | `number` | let/var | `scope.value` | ✗ |
| `value` | `number` | let/var | `onMouseDownValue + ( distance / ( event.shiftKey ? 5 : 50 ) ) * scope.step` | ✗ |
| `currentValue` | `number` | let/var | `scope.value` | ✗ |
| `value` | `number` | let/var | `onMouseDownValue + ( distance / ( event.shiftKey ? 5 : 50 ) ) * scope.step` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `changeEvent` | `Event` | let/var | `new Event( 'change', { bubbles: true, cancelable: true } )` | ✗ |
| `distance` | `number` | let/var | `0` | ✗ |
| `onMouseDownValue` | `number` | let/var | `0` | ✗ |
| `pointer` | `{ x: number; y: number; }` | let/var | `{ x: 0, y: 0 }` | ✗ |
| `prevPointer` | `{ x: number; y: number; }` | let/var | `{ x: 0, y: 0 }` | ✗ |
| `currentValue` | `number` | let/var | `scope.value` | ✗ |
| `value` | `number` | let/var | `onMouseDownValue + ( distance / ( event.shiftKey ? 5 : 50 ) ) * scope.step` | ✗ |
| `tab` | `any` | let/var | `*not shown*` | ✗ |
| `panel` | `any` | let/var | `*not shown*` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `tabOffsetRight` | `any` | let/var | `tab.dom.offsetLeft + tab.dom.offsetWidth` | ✗ |
| `containerWidth` | `any` | let/var | `this.tabsDiv.dom.getBoundingClientRect().width` | ✗ |
| `tab` | `UITab` | let/var | `new UITab( label, this )` | ✗ |
| `panel` | `UIDiv` | let/var | `new UIDiv()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `item` | `any` | let/var | `this.listitems[ 0 ]` | ✗ |
| `item` | `any` | let/var | `this.items[ i ]` | ✗ |
| `listitem` | `ListboxItem` | let/var | `new ListboxItem( this )` | ✗ |
| `element` | `any` | let/var | `this.listitems[ i ]` | ✗ |
| `changeEvent` | `Event` | let/var | `new Event( 'change', { bubbles: true, cancelable: true } )` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |


---

## Functions

### `UIElement.add(): this`

**Returns:** `this`

**Calls:**

- `this.dom.appendChild`
- `console.error`

<details><summary>Code</summary>

```typescript
add() {

		for ( let i = 0; i < arguments.length; i ++ ) {

			const argument = arguments[ i ];

			if ( argument instanceof UIElement ) {

				this.dom.appendChild( argument.dom );

			} else {

				console.error( 'UIElement:', argument, 'is not an instance of UIElement.' );

			}

		}

		return this;

	}
```
</details>

### `UIElement.remove(): this`

**Returns:** `this`

**Calls:**

- `this.dom.removeChild`
- `console.error`

<details><summary>Code</summary>

```typescript
remove() {

		for ( let i = 0; i < arguments.length; i ++ ) {

			const argument = arguments[ i ];

			if ( argument instanceof UIElement ) {

				this.dom.removeChild( argument.dom );

			} else {

				console.error( 'UIElement:', argument, 'is not an instance of UIElement.' );

			}

		}

		return this;

	}
```
</details>

### `UIElement.clear(): void`

**Returns:** `void`

**Calls:**

- `this.dom.removeChild`

<details><summary>Code</summary>

```typescript
clear() {

		while ( this.dom.children.length ) {

			this.dom.removeChild( this.dom.lastChild );

		}

	}
```
</details>

### `UIElement.setId(id: any): this`

**Parameters:**

- **`id`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setId( id ) {

		this.dom.id = id;

		return this;

	}
```
</details>

### `UIElement.getId(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getId() {

		return this.dom.id;

	}
```
</details>

### `UIElement.setClass(name: any): this`

**Parameters:**

- **`name`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setClass( name ) {

		this.dom.className = name;

		return this;

	}
```
</details>

### `UIElement.addClass(name: any): this`

**Parameters:**

- **`name`** `any`

**Returns:** `this`

**Calls:**

- `this.dom.classList.add`

<details><summary>Code</summary>

```typescript
addClass( name ) {

		this.dom.classList.add( name );

		return this;

	}
```
</details>

### `UIElement.removeClass(name: any): this`

**Parameters:**

- **`name`** `any`

**Returns:** `this`

**Calls:**

- `this.dom.classList.remove`

<details><summary>Code</summary>

```typescript
removeClass( name ) {

		this.dom.classList.remove( name );

		return this;

	}
```
</details>

### `UIElement.toggleClass(name: any, toggle: any): this`

**Parameters:**

- **`name`** `any`
- **`toggle`** `any`

**Returns:** `this`

**Calls:**

- `this.dom.classList.toggle`

<details><summary>Code</summary>

```typescript
toggleClass( name, toggle ) {

		this.dom.classList.toggle( name, toggle );

		return this;

	}
```
</details>

### `UIElement.setStyle(style: any, array: any): this`

**Parameters:**

- **`style`** `any`
- **`array`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setStyle( style, array ) {

		for ( let i = 0; i < array.length; i ++ ) {

			this.dom.style[ style ] = array[ i ];

		}

		return this;

	}
```
</details>

### `UIElement.setHidden(isHidden: any): this`

**Parameters:**

- **`isHidden`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setHidden( isHidden ) {

		this.dom.hidden = isHidden;

		return this;

	}
```
</details>

### `UIElement.isHidden(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
isHidden() {

		return this.dom.hidden;

	}
```
</details>

### `UIElement.setDisabled(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setDisabled( value ) {

		this.dom.disabled = value;

		return this;

	}
```
</details>

### `UIElement.setTextContent(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setTextContent( value ) {

		this.dom.textContent = value;

		return this;

	}
```
</details>

### `UIElement.setInnerHTML(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setInnerHTML( value ) {

		this.dom.innerHTML = value;

	}
```
</details>

### `UIElement.getIndexOfChild(element: any): any`

**Parameters:**

- **`element`** `any`

**Returns:** `any`

**Calls:**

- `Array.prototype.indexOf.call`

<details><summary>Code</summary>

```typescript
getIndexOfChild( element ) {

		return Array.prototype.indexOf.call( this.dom.children, element.dom );

	}
```
</details>

### `UIText.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.dom.textContent;

	}
```
</details>

### `UIText.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		if ( value !== undefined ) {

			this.dom.textContent = value;

		}

		return this;

	}
```
</details>

### `UIInput.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.dom.value;

	}
```
</details>

### `UIInput.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		this.dom.value = value;

		return this;

	}
```
</details>

### `UITextArea.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.dom.value;

	}
```
</details>

### `UITextArea.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		this.dom.value = value;

		return this;

	}
```
</details>

### `UISelect.setMultiple(boolean: any): this`

**Parameters:**

- **`boolean`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setMultiple( boolean ) {

		this.dom.multiple = boolean;

		return this;

	}
```
</details>

### `UISelect.setOptions(options: any): this`

**Parameters:**

- **`options`** `any`

**Returns:** `this`

**Calls:**

- `this.dom.removeChild`
- `document.createElement`
- `this.dom.appendChild`

<details><summary>Code</summary>

```typescript
setOptions( options ) {

		const selected = this.dom.value;

		while ( this.dom.children.length > 0 ) {

			this.dom.removeChild( this.dom.firstChild );

		}

		for ( const key in options ) {

			const option = document.createElement( 'option' );
			option.value = key;
			option.innerHTML = options[ key ];
			this.dom.appendChild( option );

		}

		this.dom.value = selected;

		return this;

	}
```
</details>

### `UISelect.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.dom.value;

	}
```
</details>

### `UISelect.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `String`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		value = String( value );

		if ( this.dom.value !== value ) {

			this.dom.value = value;

		}

		return this;

	}
```
</details>

### `UICheckbox.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.dom.checked;

	}
```
</details>

### `UICheckbox.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		if ( value !== undefined ) {

			this.dom.checked = value;

		}

		return this;

	}
```
</details>

### `UIColor.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.dom.value;

	}
```
</details>

### `UIColor.getHexValue(): number`

**Returns:** `number`

**Calls:**

- `parseInt`
- `this.dom.value.substring`

<details><summary>Code</summary>

```typescript
getHexValue() {

		return parseInt( this.dom.value.substring( 1 ), 16 );

	}
```
</details>

### `UIColor.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		this.dom.value = value;

		return this;

	}
```
</details>

### `UIColor.setHexValue(hex: any): this`

**Parameters:**

- **`hex`** `any`

**Returns:** `this`

**Calls:**

- `( '000000' + hex.toString( 16 ) ).slice`
- `hex.toString`

<details><summary>Code</summary>

```typescript
setHexValue( hex ) {

		this.dom.value = '#' + ( '000000' + hex.toString( 16 ) ).slice( - 6 );

		return this;

	}
```
</details>

### `UINumber.getValue(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.value;

	}
```
</details>

### `UINumber.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `parseFloat`
- `value.toFixed`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		if ( value !== undefined ) {

			value = parseFloat( value );

			if ( value < this.min ) value = this.min;
			if ( value > this.max ) value = this.max;

			this.value = value;
			this.dom.value = value.toFixed( this.precision );

			if ( this.unit !== '' ) this.dom.value += ' ' + this.unit;

		}

		return this;

	}
```
</details>

### `UINumber.setPrecision(precision: any): this`

**Parameters:**

- **`precision`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setPrecision( precision ) {

		this.precision = precision;

		return this;

	}
```
</details>

### `UINumber.setStep(step: any): this`

**Parameters:**

- **`step`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setStep( step ) {

		this.step = step;

		return this;

	}
```
</details>

### `UINumber.setNudge(nudge: any): this`

**Parameters:**

- **`nudge`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setNudge( nudge ) {

		this.nudge = nudge;

		return this;

	}
```
</details>

### `UINumber.setRange(min: any, max: any): this`

**Parameters:**

- **`min`** `any`
- **`max`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setRange( min, max ) {

		this.min = min;
		this.max = max;

		return this;

	}
```
</details>

### `UINumber.setUnit(unit: any): this`

**Parameters:**

- **`unit`** `any`

**Returns:** `this`

**Calls:**

- `this.setValue`

<details><summary>Code</summary>

```typescript
setUnit( unit ) {

		this.unit = unit;

		this.setValue( this.value );

		return this;

	}
```
</details>

### `onMouseDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.preventDefault`
- `document.addEventListener`

<details><summary>Code</summary>

```typescript
function onMouseDown( event ) {

			if ( document.activeElement === scope.dom ) return;

			event.preventDefault();

			distance = 0;

			onMouseDownValue = scope.value;

			prevPointer.x = event.clientX;
			prevPointer.y = event.clientY;

			document.addEventListener( 'mousemove', onMouseMove );
			document.addEventListener( 'mouseup', onMouseUp );

		}
```
</details>

### `onMouseMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`
- `Math.max`
- `scope.setValue`
- `scope.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onMouseMove( event ) {

			const currentValue = scope.value;

			pointer.x = event.clientX;
			pointer.y = event.clientY;

			distance += ( pointer.x - prevPointer.x ) - ( pointer.y - prevPointer.y );

			let value = onMouseDownValue + ( distance / ( event.shiftKey ? 5 : 50 ) ) * scope.step;
			value = Math.min( scope.max, Math.max( scope.min, value ) );

			if ( currentValue !== value ) {

				scope.setValue( value );
				scope.dom.dispatchEvent( changeEvent );

			}

			prevPointer.x = event.clientX;
			prevPointer.y = event.clientY;

		}
```
</details>

### `onMouseUp(): void`

**Returns:** `void`

**Calls:**

- `document.removeEventListener`
- `Math.abs`
- `scope.dom.focus`
- `scope.dom.select`

<details><summary>Code</summary>

```typescript
function onMouseUp() {

			document.removeEventListener( 'mousemove', onMouseMove );
			document.removeEventListener( 'mouseup', onMouseUp );

			if ( Math.abs( distance ) < 2 ) {

				scope.dom.focus();
				scope.dom.select();

			}

		}
```
</details>

### `onTouchStart(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `document.addEventListener`

<details><summary>Code</summary>

```typescript
function onTouchStart( event ) {

			if ( event.touches.length === 1 ) {

				distance = 0;

				onMouseDownValue = scope.value;

				prevPointer.x = event.touches[ 0 ].pageX;
				prevPointer.y = event.touches[ 0 ].pageY;

				document.addEventListener( 'touchmove', onTouchMove, { passive: false } );
				document.addEventListener( 'touchend', onTouchEnd );

			}

		}
```
</details>

### `onTouchMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.preventDefault`
- `Math.min`
- `Math.max`
- `scope.setValue`
- `scope.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onTouchMove( event ) {

			event.preventDefault();

			const currentValue = scope.value;

			pointer.x = event.touches[ 0 ].pageX;
			pointer.y = event.touches[ 0 ].pageY;

			distance += ( pointer.x - prevPointer.x ) - ( pointer.y - prevPointer.y );

			let value = onMouseDownValue + ( distance / ( event.shiftKey ? 5 : 50 ) ) * scope.step;
			value = Math.min( scope.max, Math.max( scope.min, value ) );

			if ( currentValue !== value ) {

				scope.setValue( value );
				scope.dom.dispatchEvent( changeEvent );

			}

			prevPointer.x = event.touches[ 0 ].pageX;
			prevPointer.y = event.touches[ 0 ].pageY;

		}
```
</details>

### `onTouchEnd(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `document.removeEventListener`

<details><summary>Code</summary>

```typescript
function onTouchEnd( event ) {

			if ( event.touches.length === 0 ) {

				document.removeEventListener( 'touchmove', onTouchMove );
				document.removeEventListener( 'touchend', onTouchEnd );

			}

		}
```
</details>

### `onChange(): void`

**Returns:** `void`

**Calls:**

- `scope.setValue`

<details><summary>Code</summary>

```typescript
function onChange() {

			scope.setValue( scope.dom.value );

		}
```
</details>

### `onFocus(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function onFocus() {

			scope.dom.style.backgroundColor = '';
			scope.dom.style.cursor = '';

		}
```
</details>

### `onBlur(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function onBlur() {

			scope.dom.style.backgroundColor = 'transparent';
			scope.dom.style.cursor = 'ns-resize';

		}
```
</details>

### `onKeyDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.stopPropagation`
- `scope.dom.blur`
- `event.preventDefault`
- `scope.setValue`
- `scope.getValue`
- `scope.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onKeyDown( event ) {

			event.stopPropagation();

			switch ( event.code ) {

				case 'Enter':
					scope.dom.blur();
					break;

				case 'ArrowUp':
					event.preventDefault();
					scope.setValue( scope.getValue() + scope.nudge );
					scope.dom.dispatchEvent( changeEvent );
					break;

				case 'ArrowDown':
					event.preventDefault();
					scope.setValue( scope.getValue() - scope.nudge );
					scope.dom.dispatchEvent( changeEvent );
					break;

			}

		}
```
</details>

### `UIInteger.getValue(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.value;

	}
```
</details>

### `UIInteger.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		if ( value !== undefined ) {

			value = parseInt( value );

			this.value = value;
			this.dom.value = value;

		}

		return this;

	}
```
</details>

### `UIInteger.setStep(step: any): this`

**Parameters:**

- **`step`** `any`

**Returns:** `this`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
setStep( step ) {

		this.step = parseInt( step );

		return this;

	}
```
</details>

### `UIInteger.setNudge(nudge: any): this`

**Parameters:**

- **`nudge`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setNudge( nudge ) {

		this.nudge = nudge;

		return this;

	}
```
</details>

### `UIInteger.setRange(min: any, max: any): this`

**Parameters:**

- **`min`** `any`
- **`max`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setRange( min, max ) {

		this.min = min;
		this.max = max;

		return this;

	}
```
</details>

### `onMouseDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.preventDefault`
- `document.addEventListener`

<details><summary>Code</summary>

```typescript
function onMouseDown( event ) {

			if ( document.activeElement === scope.dom ) return;

			event.preventDefault();

			distance = 0;

			onMouseDownValue = scope.value;

			prevPointer.x = event.clientX;
			prevPointer.y = event.clientY;

			document.addEventListener( 'mousemove', onMouseMove );
			document.addEventListener( 'mouseup', onMouseUp );

		}
```
</details>

### `onMouseMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`
- `Math.max`
- `scope.setValue`
- `scope.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onMouseMove( event ) {

			const currentValue = scope.value;

			pointer.x = event.clientX;
			pointer.y = event.clientY;

			distance += ( pointer.x - prevPointer.x ) - ( pointer.y - prevPointer.y );

			let value = onMouseDownValue + ( distance / ( event.shiftKey ? 5 : 50 ) ) * scope.step;
			value = Math.min( scope.max, Math.max( scope.min, value ) ) | 0;

			if ( currentValue !== value ) {

				scope.setValue( value );
				scope.dom.dispatchEvent( changeEvent );

			}

			prevPointer.x = event.clientX;
			prevPointer.y = event.clientY;

		}
```
</details>

### `onMouseUp(): void`

**Returns:** `void`

**Calls:**

- `document.removeEventListener`
- `Math.abs`
- `scope.dom.focus`
- `scope.dom.select`

<details><summary>Code</summary>

```typescript
function onMouseUp() {

			document.removeEventListener( 'mousemove', onMouseMove );
			document.removeEventListener( 'mouseup', onMouseUp );

			if ( Math.abs( distance ) < 2 ) {

				scope.dom.focus();
				scope.dom.select();

			}

		}
```
</details>

### `onChange(): void`

**Returns:** `void`

**Calls:**

- `scope.setValue`

<details><summary>Code</summary>

```typescript
function onChange() {

			scope.setValue( scope.dom.value );

		}
```
</details>

### `onFocus(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function onFocus() {

			scope.dom.style.backgroundColor = '';
			scope.dom.style.cursor = '';

		}
```
</details>

### `onBlur(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function onBlur() {

			scope.dom.style.backgroundColor = 'transparent';
			scope.dom.style.cursor = 'ns-resize';

		}
```
</details>

### `onKeyDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.stopPropagation`
- `scope.dom.blur`
- `event.preventDefault`
- `scope.setValue`
- `scope.getValue`
- `scope.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onKeyDown( event ) {

			event.stopPropagation();

			switch ( event.code ) {

				case 'Enter':
					scope.dom.blur();
					break;

				case 'ArrowUp':
					event.preventDefault();
					scope.setValue( scope.getValue() + scope.nudge );
					scope.dom.dispatchEvent( changeEvent );
					break;

				case 'ArrowDown':
					event.preventDefault();
					scope.setValue( scope.getValue() - scope.nudge );
					scope.dom.dispatchEvent( changeEvent );
					break;

			}

		}
```
</details>

### `UIProgress.setValue(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		this.dom.value = value;

	}
```
</details>

### `UITabbedPanel.select(id: any): this`

**Parameters:**

- **`id`** `any`

**Returns:** `this`

**Calls:**

- `this.tabs.find`
- `this.panels.find`
- `tab.removeClass`
- `panel.setDisplay`
- `tab.addClass`
- `this.tabsDiv.dom.getBoundingClientRect`
- `this.tabsDiv.dom.scrollTo`

**Internal Comments:**
```
// Deselect current selection
// Scrolls to tab
```

<details><summary>Code</summary>

```typescript
select( id ) {

		let tab;
		let panel;
		const scope = this;

		// Deselect current selection
		if ( this.selected && this.selected.length ) {

			tab = this.tabs.find( function ( item ) {

				return item.dom.id === scope.selected;

			} );
			panel = this.panels.find( function ( item ) {

				return item.dom.id === scope.selected;

			} );

			if ( tab ) {

				tab.removeClass( 'selected' );

			}

			if ( panel ) {

				panel.setDisplay( 'none' );

			}

		}

		tab = this.tabs.find( function ( item ) {

			return item.dom.id === id;

		} );
		panel = this.panels.find( function ( item ) {

			return item.dom.id === id;

		} );

		if ( tab ) {

			tab.addClass( 'selected' );

		}

		if ( panel ) {

			panel.setDisplay( '' );

		}

		this.selected = id;

		// Scrolls to tab
		if ( tab ) {

			const tabOffsetRight = tab.dom.offsetLeft + tab.dom.offsetWidth;
			const containerWidth = this.tabsDiv.dom.getBoundingClientRect().width;

			if ( tabOffsetRight > containerWidth ) {

				this.tabsDiv.dom.scrollTo( { left: tabOffsetRight - containerWidth, behavior: 'smooth' } );

			}

			if ( tab.dom.offsetLeft < this.tabsDiv.dom.scrollLeft ) {

				this.tabsDiv.dom.scrollTo( { left: 0, behavior: 'smooth' } );

			}

		}

		return this;

	}
```
</details>

### `UITabbedPanel.addTab(id: any, label: any, items: any): void`

**Parameters:**

- **`id`** `any`
- **`label`** `any`
- **`items`** `any`

**Returns:** `void`

**Calls:**

- `tab.setId`
- `this.tabs.push`
- `this.tabsDiv.add`
- `panel.setId`
- `panel.add`
- `panel.setDisplay`
- `this.panels.push`
- `this.panelsDiv.add`
- `this.select`

<details><summary>Code</summary>

```typescript
addTab( id, label, items ) {

		const tab = new UITab( label, this );
		tab.setId( id );
		this.tabs.push( tab );
		this.tabsDiv.add( tab );

		const panel = new UIDiv();
		panel.setId( id );
		panel.add( items );
		panel.setDisplay( 'none' );
		this.panels.push( panel );
		this.panelsDiv.add( panel );

		this.select( id );

	}
```
</details>

### `UIListbox.setItems(items: any): void`

**Parameters:**

- **`items`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `this.render`

<details><summary>Code</summary>

```typescript
setItems( items ) {

		if ( Array.isArray( items ) ) {

			this.items = items;

		}

		this.render();

	}
```
</details>

### `UIListbox.render(): void`

**Returns:** `void`

**Calls:**

- `item.dom.remove`
- `this.listitems.splice`
- `listitem.setId`
- `listitem.setTextContent`
- `this.add`

<details><summary>Code</summary>

```typescript
render( ) {

		while ( this.listitems.length ) {

			const item = this.listitems[ 0 ];

			item.dom.remove();

			this.listitems.splice( 0, 1 );

		}

		for ( let i = 0; i < this.items.length; i ++ ) {

			const item = this.items[ i ];

			const listitem = new ListboxItem( this );
			listitem.setId( item.id || `Listbox-${i}` );
			listitem.setTextContent( item.name || item.type );
			this.add( listitem );

		}

	}
```
</details>

### `UIListbox.add(): void`

**Returns:** `void`

**Calls:**

- `Array.from`
- `this.listitems.concat`
- `UIElement.prototype.add.apply`

<details><summary>Code</summary>

```typescript
add() {

		const items = Array.from( arguments );

		this.listitems = this.listitems.concat( items );

		UIElement.prototype.add.apply( this, items );

	}
```
</details>

### `UIListbox.selectIndex(index: any): void`

**Parameters:**

- **`index`** `any`

**Returns:** `void`

**Calls:**

- `this.setValue`
- `this.listitems[ index ].getId`

<details><summary>Code</summary>

```typescript
selectIndex( index ) {

		if ( index >= 0 && index < this.items.length ) {

			this.setValue( this.listitems[ index ].getId() );

		}

		this.selectedIndex = index;

	}
```
</details>

### `UIListbox.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.selectedValue;

	}
```
</details>

### `UIListbox.setValue(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `element.getId`
- `element.addClass`
- `element.removeClass`
- `this.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		for ( let i = 0; i < this.listitems.length; i ++ ) {

			const element = this.listitems[ i ];

			if ( element.getId() === value ) {

				element.addClass( 'active' );

			} else {

				element.removeClass( 'active' );

			}

		}

		this.selectedValue = value;

		const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
		this.dom.dispatchEvent( changeEvent );

	}
```
</details>

### `onClick(): void`

**Returns:** `void`

**Calls:**

- `scope.parent.setValue`
- `scope.getId`

<details><summary>Code</summary>

```typescript
function onClick() {

			if ( scope.parent ) {

				scope.parent.setValue( scope.getId( ) );

			}

		}
```
</details>


---

## Classes

### `UIElement`

<details><summary>Class Code</summary>

```ts
class UIElement {

	constructor( dom ) {

		this.dom = dom;

	}

	add() {

		for ( let i = 0; i < arguments.length; i ++ ) {

			const argument = arguments[ i ];

			if ( argument instanceof UIElement ) {

				this.dom.appendChild( argument.dom );

			} else {

				console.error( 'UIElement:', argument, 'is not an instance of UIElement.' );

			}

		}

		return this;

	}

	remove() {

		for ( let i = 0; i < arguments.length; i ++ ) {

			const argument = arguments[ i ];

			if ( argument instanceof UIElement ) {

				this.dom.removeChild( argument.dom );

			} else {

				console.error( 'UIElement:', argument, 'is not an instance of UIElement.' );

			}

		}

		return this;

	}

	clear() {

		while ( this.dom.children.length ) {

			this.dom.removeChild( this.dom.lastChild );

		}

	}

	setId( id ) {

		this.dom.id = id;

		return this;

	}

	getId() {

		return this.dom.id;

	}

	setClass( name ) {

		this.dom.className = name;

		return this;

	}

	addClass( name ) {

		this.dom.classList.add( name );

		return this;

	}

	removeClass( name ) {

		this.dom.classList.remove( name );

		return this;

	}

	toggleClass( name, toggle ) {

		this.dom.classList.toggle( name, toggle );

		return this;

	}

	setStyle( style, array ) {

		for ( let i = 0; i < array.length; i ++ ) {

			this.dom.style[ style ] = array[ i ];

		}

		return this;

	}

	setHidden( isHidden ) {

		this.dom.hidden = isHidden;

		return this;

	}

	isHidden() {

		return this.dom.hidden;

	}

	setDisabled( value ) {

		this.dom.disabled = value;

		return this;

	}

	setTextContent( value ) {

		this.dom.textContent = value;

		return this;

	}

	setInnerHTML( value ) {

		this.dom.innerHTML = value;

	}

	getIndexOfChild( element ) {

		return Array.prototype.indexOf.call( this.dom.children, element.dom );

	}

}
```
</details>

#### Methods

##### `add(): this`

<details><summary>Code</summary>

```ts
add() {

		for ( let i = 0; i < arguments.length; i ++ ) {

			const argument = arguments[ i ];

			if ( argument instanceof UIElement ) {

				this.dom.appendChild( argument.dom );

			} else {

				console.error( 'UIElement:', argument, 'is not an instance of UIElement.' );

			}

		}

		return this;

	}
```
</details>

##### `remove(): this`

<details><summary>Code</summary>

```ts
remove() {

		for ( let i = 0; i < arguments.length; i ++ ) {

			const argument = arguments[ i ];

			if ( argument instanceof UIElement ) {

				this.dom.removeChild( argument.dom );

			} else {

				console.error( 'UIElement:', argument, 'is not an instance of UIElement.' );

			}

		}

		return this;

	}
```
</details>

##### `clear(): void`

<details><summary>Code</summary>

```ts
clear() {

		while ( this.dom.children.length ) {

			this.dom.removeChild( this.dom.lastChild );

		}

	}
```
</details>

##### `setId(id: any): this`

<details><summary>Code</summary>

```ts
setId( id ) {

		this.dom.id = id;

		return this;

	}
```
</details>

##### `getId(): any`

<details><summary>Code</summary>

```ts
getId() {

		return this.dom.id;

	}
```
</details>

##### `setClass(name: any): this`

<details><summary>Code</summary>

```ts
setClass( name ) {

		this.dom.className = name;

		return this;

	}
```
</details>

##### `addClass(name: any): this`

<details><summary>Code</summary>

```ts
addClass( name ) {

		this.dom.classList.add( name );

		return this;

	}
```
</details>

##### `removeClass(name: any): this`

<details><summary>Code</summary>

```ts
removeClass( name ) {

		this.dom.classList.remove( name );

		return this;

	}
```
</details>

##### `toggleClass(name: any, toggle: any): this`

<details><summary>Code</summary>

```ts
toggleClass( name, toggle ) {

		this.dom.classList.toggle( name, toggle );

		return this;

	}
```
</details>

##### `setStyle(style: any, array: any): this`

<details><summary>Code</summary>

```ts
setStyle( style, array ) {

		for ( let i = 0; i < array.length; i ++ ) {

			this.dom.style[ style ] = array[ i ];

		}

		return this;

	}
```
</details>

##### `setHidden(isHidden: any): this`

<details><summary>Code</summary>

```ts
setHidden( isHidden ) {

		this.dom.hidden = isHidden;

		return this;

	}
```
</details>

##### `isHidden(): any`

<details><summary>Code</summary>

```ts
isHidden() {

		return this.dom.hidden;

	}
```
</details>

##### `setDisabled(value: any): this`

<details><summary>Code</summary>

```ts
setDisabled( value ) {

		this.dom.disabled = value;

		return this;

	}
```
</details>

##### `setTextContent(value: any): this`

<details><summary>Code</summary>

```ts
setTextContent( value ) {

		this.dom.textContent = value;

		return this;

	}
```
</details>

##### `setInnerHTML(value: any): void`

<details><summary>Code</summary>

```ts
setInnerHTML( value ) {

		this.dom.innerHTML = value;

	}
```
</details>

##### `getIndexOfChild(element: any): any`

<details><summary>Code</summary>

```ts
getIndexOfChild( element ) {

		return Array.prototype.indexOf.call( this.dom.children, element.dom );

	}
```
</details>

### `UISpan`

<details><summary>Class Code</summary>

```ts
class UISpan extends UIElement {

	constructor() {

		super( document.createElement( 'span' ) );

	}

}
```
</details>

### `UIDiv`

<details><summary>Class Code</summary>

```ts
class UIDiv extends UIElement {

	constructor() {

		super( document.createElement( 'div' ) );

	}

}
```
</details>

### `UIRow`

<details><summary>Class Code</summary>

```ts
class UIRow extends UIDiv {

	constructor() {

		super();

		this.dom.className = 'Row';

	}

}
```
</details>

### `UIPanel`

<details><summary>Class Code</summary>

```ts
class UIPanel extends UIDiv {

	constructor() {

		super();

		this.dom.className = 'Panel';

	}

}
```
</details>

### `UIText`

<details><summary>Class Code</summary>

```ts
class UIText extends UISpan {

	constructor( text ) {

		super();

		this.dom.className = 'Text';
		this.dom.style.cursor = 'default';
		this.dom.style.display = 'inline-block';

		this.setValue( text );

	}

	getValue() {

		return this.dom.textContent;

	}

	setValue( value ) {

		if ( value !== undefined ) {

			this.dom.textContent = value;

		}

		return this;

	}

}
```
</details>

#### Methods

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.dom.textContent;

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		if ( value !== undefined ) {

			this.dom.textContent = value;

		}

		return this;

	}
```
</details>

### `UIInput`

<details><summary>Class Code</summary>

```ts
class UIInput extends UIElement {

	constructor( text ) {

		super( document.createElement( 'input' ) );

		this.dom.className = 'Input';
		this.dom.style.padding = '2px';
		this.dom.style.border = '1px solid transparent';

		this.dom.setAttribute( 'autocomplete', 'off' );

		this.dom.addEventListener( 'keydown', function ( event ) {

			event.stopPropagation();

		} );

		this.setValue( text );

	}

	getValue() {

		return this.dom.value;

	}

	setValue( value ) {

		this.dom.value = value;

		return this;

	}

}
```
</details>

#### Methods

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.dom.value;

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		this.dom.value = value;

		return this;

	}
```
</details>

### `UITextArea`

<details><summary>Class Code</summary>

```ts
class UITextArea extends UIElement {

	constructor() {

		super( document.createElement( 'textarea' ) );

		this.dom.className = 'TextArea';
		this.dom.style.padding = '2px';
		this.dom.spellcheck = false;

		this.dom.setAttribute( 'autocomplete', 'off' );

		this.dom.addEventListener( 'keydown', function ( event ) {

			event.stopPropagation();

			if ( event.code === 'Tab' ) {

				event.preventDefault();

				const cursor = this.selectionStart;

				this.value = this.value.substring( 0, cursor ) + '\t' + this.value.substring( cursor );
				this.selectionStart = cursor + 1;
				this.selectionEnd = this.selectionStart;

			}

		} );

	}

	getValue() {

		return this.dom.value;

	}

	setValue( value ) {

		this.dom.value = value;

		return this;

	}

}
```
</details>

#### Methods

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.dom.value;

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		this.dom.value = value;

		return this;

	}
```
</details>

### `UISelect`

<details><summary>Class Code</summary>

```ts
class UISelect extends UIElement {

	constructor() {

		super( document.createElement( 'select' ) );

		this.dom.className = 'Select';
		this.dom.style.padding = '2px';

		this.dom.setAttribute( 'autocomplete', 'off' );

		this.dom.addEventListener( 'pointerdown', function ( event ) {

			event.stopPropagation();

		} );

	}

	setMultiple( boolean ) {

		this.dom.multiple = boolean;

		return this;

	}

	setOptions( options ) {

		const selected = this.dom.value;

		while ( this.dom.children.length > 0 ) {

			this.dom.removeChild( this.dom.firstChild );

		}

		for ( const key in options ) {

			const option = document.createElement( 'option' );
			option.value = key;
			option.innerHTML = options[ key ];
			this.dom.appendChild( option );

		}

		this.dom.value = selected;

		return this;

	}

	getValue() {

		return this.dom.value;

	}

	setValue( value ) {

		value = String( value );

		if ( this.dom.value !== value ) {

			this.dom.value = value;

		}

		return this;

	}

}
```
</details>

#### Methods

##### `setMultiple(boolean: any): this`

<details><summary>Code</summary>

```ts
setMultiple( boolean ) {

		this.dom.multiple = boolean;

		return this;

	}
```
</details>

##### `setOptions(options: any): this`

<details><summary>Code</summary>

```ts
setOptions( options ) {

		const selected = this.dom.value;

		while ( this.dom.children.length > 0 ) {

			this.dom.removeChild( this.dom.firstChild );

		}

		for ( const key in options ) {

			const option = document.createElement( 'option' );
			option.value = key;
			option.innerHTML = options[ key ];
			this.dom.appendChild( option );

		}

		this.dom.value = selected;

		return this;

	}
```
</details>

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.dom.value;

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		value = String( value );

		if ( this.dom.value !== value ) {

			this.dom.value = value;

		}

		return this;

	}
```
</details>

### `UICheckbox`

<details><summary>Class Code</summary>

```ts
class UICheckbox extends UIElement {

	constructor( boolean ) {

		super( document.createElement( 'input' ) );

		this.dom.className = 'Checkbox';
		this.dom.type = 'checkbox';

		this.dom.addEventListener( 'pointerdown', function ( event ) {

			// Workaround for TransformControls blocking events in Viewport.Controls checkboxes

			event.stopPropagation();

		} );

		this.setValue( boolean );

	}

	getValue() {

		return this.dom.checked;

	}

	setValue( value ) {

		if ( value !== undefined ) {

			this.dom.checked = value;

		}

		return this;

	}

}
```
</details>

#### Methods

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.dom.checked;

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		if ( value !== undefined ) {

			this.dom.checked = value;

		}

		return this;

	}
```
</details>

### `UIColor`

<details><summary>Class Code</summary>

```ts
class UIColor extends UIElement {

	constructor() {

		super( document.createElement( 'input' ) );

		this.dom.className = 'Color';
		this.dom.style.width = '32px';
		this.dom.style.height = '16px';
		this.dom.style.border = '0px';
		this.dom.style.padding = '2px';
		this.dom.style.backgroundColor = 'transparent';

		this.dom.setAttribute( 'autocomplete', 'off' );

		try {

			this.dom.type = 'color';
			this.dom.value = '#ffffff';

		} catch ( exception ) {}

	}

	getValue() {

		return this.dom.value;

	}

	getHexValue() {

		return parseInt( this.dom.value.substring( 1 ), 16 );

	}

	setValue( value ) {

		this.dom.value = value;

		return this;

	}

	setHexValue( hex ) {

		this.dom.value = '#' + ( '000000' + hex.toString( 16 ) ).slice( - 6 );

		return this;

	}

}
```
</details>

#### Methods

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.dom.value;

	}
```
</details>

##### `getHexValue(): number`

<details><summary>Code</summary>

```ts
getHexValue() {

		return parseInt( this.dom.value.substring( 1 ), 16 );

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		this.dom.value = value;

		return this;

	}
```
</details>

##### `setHexValue(hex: any): this`

<details><summary>Code</summary>

```ts
setHexValue( hex ) {

		this.dom.value = '#' + ( '000000' + hex.toString( 16 ) ).slice( - 6 );

		return this;

	}
```
</details>

### `UINumber`

<details><summary>Class Code</summary>

```ts
class UINumber extends UIElement {

	constructor( number ) {

		super( document.createElement( 'input' ) );

		this.dom.style.cursor = 'ns-resize';
		this.dom.className = 'Number';
		this.dom.value = '0.00';

		this.dom.setAttribute( 'autocomplete', 'off' );

		this.value = 0;

		this.min = - Infinity;
		this.max = Infinity;

		this.precision = 2;
		this.step = 1;
		this.unit = '';
		this.nudge = 0.01;

		this.setValue( number );

		const scope = this;

		const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );

		let distance = 0;
		let onMouseDownValue = 0;

		const pointer = { x: 0, y: 0 };
		const prevPointer = { x: 0, y: 0 };

		function onMouseDown( event ) {

			if ( document.activeElement === scope.dom ) return;

			event.preventDefault();

			distance = 0;

			onMouseDownValue = scope.value;

			prevPointer.x = event.clientX;
			prevPointer.y = event.clientY;

			document.addEventListener( 'mousemove', onMouseMove );
			document.addEventListener( 'mouseup', onMouseUp );

		}

		function onMouseMove( event ) {

			const currentValue = scope.value;

			pointer.x = event.clientX;
			pointer.y = event.clientY;

			distance += ( pointer.x - prevPointer.x ) - ( pointer.y - prevPointer.y );

			let value = onMouseDownValue + ( distance / ( event.shiftKey ? 5 : 50 ) ) * scope.step;
			value = Math.min( scope.max, Math.max( scope.min, value ) );

			if ( currentValue !== value ) {

				scope.setValue( value );
				scope.dom.dispatchEvent( changeEvent );

			}

			prevPointer.x = event.clientX;
			prevPointer.y = event.clientY;

		}

		function onMouseUp() {

			document.removeEventListener( 'mousemove', onMouseMove );
			document.removeEventListener( 'mouseup', onMouseUp );

			if ( Math.abs( distance ) < 2 ) {

				scope.dom.focus();
				scope.dom.select();

			}

		}

		function onTouchStart( event ) {

			if ( event.touches.length === 1 ) {

				distance = 0;

				onMouseDownValue = scope.value;

				prevPointer.x = event.touches[ 0 ].pageX;
				prevPointer.y = event.touches[ 0 ].pageY;

				document.addEventListener( 'touchmove', onTouchMove, { passive: false } );
				document.addEventListener( 'touchend', onTouchEnd );

			}

		}

		function onTouchMove( event ) {

			event.preventDefault();

			const currentValue = scope.value;

			pointer.x = event.touches[ 0 ].pageX;
			pointer.y = event.touches[ 0 ].pageY;

			distance += ( pointer.x - prevPointer.x ) - ( pointer.y - prevPointer.y );

			let value = onMouseDownValue + ( distance / ( event.shiftKey ? 5 : 50 ) ) * scope.step;
			value = Math.min( scope.max, Math.max( scope.min, value ) );

			if ( currentValue !== value ) {

				scope.setValue( value );
				scope.dom.dispatchEvent( changeEvent );

			}

			prevPointer.x = event.touches[ 0 ].pageX;
			prevPointer.y = event.touches[ 0 ].pageY;

		}

		function onTouchEnd( event ) {

			if ( event.touches.length === 0 ) {

				document.removeEventListener( 'touchmove', onTouchMove );
				document.removeEventListener( 'touchend', onTouchEnd );

			}

		}

		function onChange() {

			scope.setValue( scope.dom.value );

		}

		function onFocus() {

			scope.dom.style.backgroundColor = '';
			scope.dom.style.cursor = '';

		}

		function onBlur() {

			scope.dom.style.backgroundColor = 'transparent';
			scope.dom.style.cursor = 'ns-resize';

		}

		function onKeyDown( event ) {

			event.stopPropagation();

			switch ( event.code ) {

				case 'Enter':
					scope.dom.blur();
					break;

				case 'ArrowUp':
					event.preventDefault();
					scope.setValue( scope.getValue() + scope.nudge );
					scope.dom.dispatchEvent( changeEvent );
					break;

				case 'ArrowDown':
					event.preventDefault();
					scope.setValue( scope.getValue() - scope.nudge );
					scope.dom.dispatchEvent( changeEvent );
					break;

			}

		}

		onBlur();

		this.dom.addEventListener( 'keydown', onKeyDown );
		this.dom.addEventListener( 'mousedown', onMouseDown );
		this.dom.addEventListener( 'touchstart', onTouchStart, { passive: false } );
		this.dom.addEventListener( 'change', onChange );
		this.dom.addEventListener( 'focus', onFocus );
		this.dom.addEventListener( 'blur', onBlur );

	}

	getValue() {

		return this.value;

	}

	setValue( value ) {

		if ( value !== undefined ) {

			value = parseFloat( value );

			if ( value < this.min ) value = this.min;
			if ( value > this.max ) value = this.max;

			this.value = value;
			this.dom.value = value.toFixed( this.precision );

			if ( this.unit !== '' ) this.dom.value += ' ' + this.unit;

		}

		return this;

	}

	setPrecision( precision ) {

		this.precision = precision;

		return this;

	}

	setStep( step ) {

		this.step = step;

		return this;

	}

	setNudge( nudge ) {

		this.nudge = nudge;

		return this;

	}

	setRange( min, max ) {

		this.min = min;
		this.max = max;

		return this;

	}

	setUnit( unit ) {

		this.unit = unit;

		this.setValue( this.value );

		return this;

	}

}
```
</details>

#### Methods

##### `getValue(): number`

<details><summary>Code</summary>

```ts
getValue() {

		return this.value;

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		if ( value !== undefined ) {

			value = parseFloat( value );

			if ( value < this.min ) value = this.min;
			if ( value > this.max ) value = this.max;

			this.value = value;
			this.dom.value = value.toFixed( this.precision );

			if ( this.unit !== '' ) this.dom.value += ' ' + this.unit;

		}

		return this;

	}
```
</details>

##### `setPrecision(precision: any): this`

<details><summary>Code</summary>

```ts
setPrecision( precision ) {

		this.precision = precision;

		return this;

	}
```
</details>

##### `setStep(step: any): this`

<details><summary>Code</summary>

```ts
setStep( step ) {

		this.step = step;

		return this;

	}
```
</details>

##### `setNudge(nudge: any): this`

<details><summary>Code</summary>

```ts
setNudge( nudge ) {

		this.nudge = nudge;

		return this;

	}
```
</details>

##### `setRange(min: any, max: any): this`

<details><summary>Code</summary>

```ts
setRange( min, max ) {

		this.min = min;
		this.max = max;

		return this;

	}
```
</details>

##### `setUnit(unit: any): this`

<details><summary>Code</summary>

```ts
setUnit( unit ) {

		this.unit = unit;

		this.setValue( this.value );

		return this;

	}
```
</details>

### `UIInteger`

<details><summary>Class Code</summary>

```ts
class UIInteger extends UIElement {

	constructor( number ) {

		super( document.createElement( 'input' ) );

		this.dom.style.cursor = 'ns-resize';
		this.dom.className = 'Number';
		this.dom.value = '0';

		this.dom.setAttribute( 'autocomplete', 'off' );

		this.value = 0;

		this.min = - Infinity;
		this.max = Infinity;

		this.step = 1;
		this.nudge = 1;

		this.setValue( number );

		const scope = this;

		const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );

		let distance = 0;
		let onMouseDownValue = 0;

		const pointer = { x: 0, y: 0 };
		const prevPointer = { x: 0, y: 0 };

		function onMouseDown( event ) {

			if ( document.activeElement === scope.dom ) return;

			event.preventDefault();

			distance = 0;

			onMouseDownValue = scope.value;

			prevPointer.x = event.clientX;
			prevPointer.y = event.clientY;

			document.addEventListener( 'mousemove', onMouseMove );
			document.addEventListener( 'mouseup', onMouseUp );

		}

		function onMouseMove( event ) {

			const currentValue = scope.value;

			pointer.x = event.clientX;
			pointer.y = event.clientY;

			distance += ( pointer.x - prevPointer.x ) - ( pointer.y - prevPointer.y );

			let value = onMouseDownValue + ( distance / ( event.shiftKey ? 5 : 50 ) ) * scope.step;
			value = Math.min( scope.max, Math.max( scope.min, value ) ) | 0;

			if ( currentValue !== value ) {

				scope.setValue( value );
				scope.dom.dispatchEvent( changeEvent );

			}

			prevPointer.x = event.clientX;
			prevPointer.y = event.clientY;

		}

		function onMouseUp() {

			document.removeEventListener( 'mousemove', onMouseMove );
			document.removeEventListener( 'mouseup', onMouseUp );

			if ( Math.abs( distance ) < 2 ) {

				scope.dom.focus();
				scope.dom.select();

			}

		}

		function onChange() {

			scope.setValue( scope.dom.value );

		}

		function onFocus() {

			scope.dom.style.backgroundColor = '';
			scope.dom.style.cursor = '';

		}

		function onBlur() {

			scope.dom.style.backgroundColor = 'transparent';
			scope.dom.style.cursor = 'ns-resize';

		}

		function onKeyDown( event ) {

			event.stopPropagation();

			switch ( event.code ) {

				case 'Enter':
					scope.dom.blur();
					break;

				case 'ArrowUp':
					event.preventDefault();
					scope.setValue( scope.getValue() + scope.nudge );
					scope.dom.dispatchEvent( changeEvent );
					break;

				case 'ArrowDown':
					event.preventDefault();
					scope.setValue( scope.getValue() - scope.nudge );
					scope.dom.dispatchEvent( changeEvent );
					break;

			}

		}

		onBlur();

		this.dom.addEventListener( 'keydown', onKeyDown );
		this.dom.addEventListener( 'mousedown', onMouseDown );
		this.dom.addEventListener( 'change', onChange );
		this.dom.addEventListener( 'focus', onFocus );
		this.dom.addEventListener( 'blur', onBlur );

	}

	getValue() {

		return this.value;

	}

	setValue( value ) {

		if ( value !== undefined ) {

			value = parseInt( value );

			this.value = value;
			this.dom.value = value;

		}

		return this;

	}

	setStep( step ) {

		this.step = parseInt( step );

		return this;

	}

	setNudge( nudge ) {

		this.nudge = nudge;

		return this;

	}

	setRange( min, max ) {

		this.min = min;
		this.max = max;

		return this;

	}

}
```
</details>

#### Methods

##### `getValue(): number`

<details><summary>Code</summary>

```ts
getValue() {

		return this.value;

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		if ( value !== undefined ) {

			value = parseInt( value );

			this.value = value;
			this.dom.value = value;

		}

		return this;

	}
```
</details>

##### `setStep(step: any): this`

<details><summary>Code</summary>

```ts
setStep( step ) {

		this.step = parseInt( step );

		return this;

	}
```
</details>

##### `setNudge(nudge: any): this`

<details><summary>Code</summary>

```ts
setNudge( nudge ) {

		this.nudge = nudge;

		return this;

	}
```
</details>

##### `setRange(min: any, max: any): this`

<details><summary>Code</summary>

```ts
setRange( min, max ) {

		this.min = min;
		this.max = max;

		return this;

	}
```
</details>

### `UIBreak`

<details><summary>Class Code</summary>

```ts
class UIBreak extends UIElement {

	constructor() {

		super( document.createElement( 'br' ) );

		this.dom.className = 'Break';

	}

}
```
</details>

### `UIHorizontalRule`

<details><summary>Class Code</summary>

```ts
class UIHorizontalRule extends UIElement {

	constructor() {

		super( document.createElement( 'hr' ) );

		this.dom.className = 'HorizontalRule';

	}

}
```
</details>

### `UIButton`

<details><summary>Class Code</summary>

```ts
class UIButton extends UIElement {

	constructor( value ) {

		super( document.createElement( 'button' ) );

		this.dom.className = 'Button';
		this.dom.textContent = value;

	}

}
```
</details>

### `UIProgress`

<details><summary>Class Code</summary>

```ts
class UIProgress extends UIElement {

	constructor( value ) {

		super( document.createElement( 'progress' ) );

		this.dom.value = value;

	}

	setValue( value ) {

		this.dom.value = value;

	}

}
```
</details>

#### Methods

##### `setValue(value: any): void`

<details><summary>Code</summary>

```ts
setValue( value ) {

		this.dom.value = value;

	}
```
</details>

### `UITabbedPanel`

<details><summary>Class Code</summary>

```ts
class UITabbedPanel extends UIDiv {

	constructor() {

		super();

		this.dom.className = 'TabbedPanel';

		this.tabs = [];
		this.panels = [];

		this.tabsDiv = new UIDiv();
		this.tabsDiv.setClass( 'Tabs' );

		this.panelsDiv = new UIDiv();
		this.panelsDiv.setClass( 'Panels' );

		this.add( this.tabsDiv );
		this.add( this.panelsDiv );

		this.selected = '';

	}

	select( id ) {

		let tab;
		let panel;
		const scope = this;

		// Deselect current selection
		if ( this.selected && this.selected.length ) {

			tab = this.tabs.find( function ( item ) {

				return item.dom.id === scope.selected;

			} );
			panel = this.panels.find( function ( item ) {

				return item.dom.id === scope.selected;

			} );

			if ( tab ) {

				tab.removeClass( 'selected' );

			}

			if ( panel ) {

				panel.setDisplay( 'none' );

			}

		}

		tab = this.tabs.find( function ( item ) {

			return item.dom.id === id;

		} );
		panel = this.panels.find( function ( item ) {

			return item.dom.id === id;

		} );

		if ( tab ) {

			tab.addClass( 'selected' );

		}

		if ( panel ) {

			panel.setDisplay( '' );

		}

		this.selected = id;

		// Scrolls to tab
		if ( tab ) {

			const tabOffsetRight = tab.dom.offsetLeft + tab.dom.offsetWidth;
			const containerWidth = this.tabsDiv.dom.getBoundingClientRect().width;

			if ( tabOffsetRight > containerWidth ) {

				this.tabsDiv.dom.scrollTo( { left: tabOffsetRight - containerWidth, behavior: 'smooth' } );

			}

			if ( tab.dom.offsetLeft < this.tabsDiv.dom.scrollLeft ) {

				this.tabsDiv.dom.scrollTo( { left: 0, behavior: 'smooth' } );

			}

		}

		return this;

	}

	addTab( id, label, items ) {

		const tab = new UITab( label, this );
		tab.setId( id );
		this.tabs.push( tab );
		this.tabsDiv.add( tab );

		const panel = new UIDiv();
		panel.setId( id );
		panel.add( items );
		panel.setDisplay( 'none' );
		this.panels.push( panel );
		this.panelsDiv.add( panel );

		this.select( id );

	}

}
```
</details>

#### Methods

##### `select(id: any): this`

<details><summary>Code</summary>

```ts
select( id ) {

		let tab;
		let panel;
		const scope = this;

		// Deselect current selection
		if ( this.selected && this.selected.length ) {

			tab = this.tabs.find( function ( item ) {

				return item.dom.id === scope.selected;

			} );
			panel = this.panels.find( function ( item ) {

				return item.dom.id === scope.selected;

			} );

			if ( tab ) {

				tab.removeClass( 'selected' );

			}

			if ( panel ) {

				panel.setDisplay( 'none' );

			}

		}

		tab = this.tabs.find( function ( item ) {

			return item.dom.id === id;

		} );
		panel = this.panels.find( function ( item ) {

			return item.dom.id === id;

		} );

		if ( tab ) {

			tab.addClass( 'selected' );

		}

		if ( panel ) {

			panel.setDisplay( '' );

		}

		this.selected = id;

		// Scrolls to tab
		if ( tab ) {

			const tabOffsetRight = tab.dom.offsetLeft + tab.dom.offsetWidth;
			const containerWidth = this.tabsDiv.dom.getBoundingClientRect().width;

			if ( tabOffsetRight > containerWidth ) {

				this.tabsDiv.dom.scrollTo( { left: tabOffsetRight - containerWidth, behavior: 'smooth' } );

			}

			if ( tab.dom.offsetLeft < this.tabsDiv.dom.scrollLeft ) {

				this.tabsDiv.dom.scrollTo( { left: 0, behavior: 'smooth' } );

			}

		}

		return this;

	}
```
</details>

##### `addTab(id: any, label: any, items: any): void`

<details><summary>Code</summary>

```ts
addTab( id, label, items ) {

		const tab = new UITab( label, this );
		tab.setId( id );
		this.tabs.push( tab );
		this.tabsDiv.add( tab );

		const panel = new UIDiv();
		panel.setId( id );
		panel.add( items );
		panel.setDisplay( 'none' );
		this.panels.push( panel );
		this.panelsDiv.add( panel );

		this.select( id );

	}
```
</details>

### `UITab`

<details><summary>Class Code</summary>

```ts
class UITab extends UIText {

	constructor( text, parent ) {

		super( text );

		this.dom.className = 'Tab';

		this.parent = parent;

		const scope = this;

		this.dom.addEventListener( 'click', function () {

			scope.parent.select( scope.dom.id );

		} );

	}

}
```
</details>

### `UIListbox`

<details><summary>Class Code</summary>

```ts
class UIListbox extends UIDiv {

	constructor() {

		super();

		this.dom.className = 'Listbox';
		this.dom.tabIndex = 0;

		this.items = [];
		this.listitems = [];
		this.selectedIndex = 0;
		this.selectedValue = null;

	}

	setItems( items ) {

		if ( Array.isArray( items ) ) {

			this.items = items;

		}

		this.render();

	}

	render( ) {

		while ( this.listitems.length ) {

			const item = this.listitems[ 0 ];

			item.dom.remove();

			this.listitems.splice( 0, 1 );

		}

		for ( let i = 0; i < this.items.length; i ++ ) {

			const item = this.items[ i ];

			const listitem = new ListboxItem( this );
			listitem.setId( item.id || `Listbox-${i}` );
			listitem.setTextContent( item.name || item.type );
			this.add( listitem );

		}

	}

	add() {

		const items = Array.from( arguments );

		this.listitems = this.listitems.concat( items );

		UIElement.prototype.add.apply( this, items );

	}

	selectIndex( index ) {

		if ( index >= 0 && index < this.items.length ) {

			this.setValue( this.listitems[ index ].getId() );

		}

		this.selectedIndex = index;

	}

	getValue() {

		return this.selectedValue;

	}

	setValue( value ) {

		for ( let i = 0; i < this.listitems.length; i ++ ) {

			const element = this.listitems[ i ];

			if ( element.getId() === value ) {

				element.addClass( 'active' );

			} else {

				element.removeClass( 'active' );

			}

		}

		this.selectedValue = value;

		const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
		this.dom.dispatchEvent( changeEvent );

	}

}
```
</details>

#### Methods

##### `setItems(items: any): void`

<details><summary>Code</summary>

```ts
setItems( items ) {

		if ( Array.isArray( items ) ) {

			this.items = items;

		}

		this.render();

	}
```
</details>

##### `render(): void`

<details><summary>Code</summary>

```ts
render( ) {

		while ( this.listitems.length ) {

			const item = this.listitems[ 0 ];

			item.dom.remove();

			this.listitems.splice( 0, 1 );

		}

		for ( let i = 0; i < this.items.length; i ++ ) {

			const item = this.items[ i ];

			const listitem = new ListboxItem( this );
			listitem.setId( item.id || `Listbox-${i}` );
			listitem.setTextContent( item.name || item.type );
			this.add( listitem );

		}

	}
```
</details>

##### `add(): void`

<details><summary>Code</summary>

```ts
add() {

		const items = Array.from( arguments );

		this.listitems = this.listitems.concat( items );

		UIElement.prototype.add.apply( this, items );

	}
```
</details>

##### `selectIndex(index: any): void`

<details><summary>Code</summary>

```ts
selectIndex( index ) {

		if ( index >= 0 && index < this.items.length ) {

			this.setValue( this.listitems[ index ].getId() );

		}

		this.selectedIndex = index;

	}
```
</details>

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.selectedValue;

	}
```
</details>

##### `setValue(value: any): void`

<details><summary>Code</summary>

```ts
setValue( value ) {

		for ( let i = 0; i < this.listitems.length; i ++ ) {

			const element = this.listitems[ i ];

			if ( element.getId() === value ) {

				element.addClass( 'active' );

			} else {

				element.removeClass( 'active' );

			}

		}

		this.selectedValue = value;

		const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
		this.dom.dispatchEvent( changeEvent );

	}
```
</details>

### `ListboxItem`

<details><summary>Class Code</summary>

```ts
class ListboxItem extends UIDiv {

	constructor( parent ) {

		super();

		this.dom.className = 'ListboxItem';

		this.parent = parent;

		const scope = this;

		function onClick() {

			if ( scope.parent ) {

				scope.parent.setValue( scope.getId( ) );

			}

		}

		this.dom.addEventListener( 'click', onClick );

	}

}
```
</details>


---