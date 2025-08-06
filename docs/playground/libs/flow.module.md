[⬅️ Back to Table of Contents](../../index.md)

# 📄 `flow.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 225 |
| 🧱 Classes | 26 |
| 📊 Variables & Constants | 148 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/libs/flow.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `REVISION` | `"3"` | let/var | `'3'` | ✗ |
| `_id` | `number` | let/var | `0` | ✗ |
| `object` | `any` | let/var | `null` | ✗ |
| `id` | `number` | let/var | `this.id` | ✗ |
| `objects` | `any` | let/var | `data.objects` | ✗ |
| `event` | `any` | let/var | `e.touches ? e.touches[ 0 ] : e` | ✗ |
| `dragData` | `any` | let/var | `null` | ✗ |
| `zoomDOM` | `any` | let/var | `dom` | ✗ |
| `zoom` | `any` | let/var | `zoomDOM.style.zoom` | ✗ |
| `event` | `any` | let/var | `e.touches ? e.touches[ 0 ] : e` | ✗ |
| `event` | `any` | let/var | `e.touches ? e.touches[ 0 ] : e` | ✗ |
| `e` | `Event` | let/var | `dom` | ✗ |
| `selected` | `any` | let/var | `null` | ✗ |
| `element` | `this` | let/var | `this` | ✗ |
| `touch` | `any` | let/var | `e.changedTouches[ 0 ]` | ✗ |
| `type` | `any` | let/var | `e.type` | ✗ |
| `dom` | `HTMLElement` | let/var | `this.dom` | ✗ |
| `dom` | `HTMLElement` | let/var | `this.dom` | ✗ |
| `link` | `Link` | let/var | `new Link( this, element )` | ✗ |
| `inputs` | `any[]` | let/var | `[]` | ✗ |
| `properties` | `any[]` | let/var | `[]` | ✗ |
| `links` | `any[]` | let/var | `[]` | ✗ |
| `id` | `any` | let/var | `input.toJSON( data ).id` | ✗ |
| `inputs` | `any[]` | let/var | `this.inputs` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `nodeDOM` | `any` | let/var | `this.node.dom` | ✗ |
| `defaultOutput` | `"lio" \| "rio"` | let/var | `Link.InputDirection === 'left' ? 'lio' : 'rio'` | ✗ |
| `link` | `Link` | let/var | `type === defaultOutput ? new Link( this ) : new Link( null, this )` | ✗ |
| `previewLink` | `Link` | let/var | `new Link( link.inputElement, link.outputElement )` | ✗ |
| `isInvalid` | `boolean` | let/var | `previewLink.inputElement !== null && previewLink.outputElement !== null && pr...` | ✗ |
| `canvas` | `any` | let/var | `this.canvas` | ✗ |
| `dom` | `HTMLElement` | let/var | `this.dom` | ✗ |
| `style` | `CSSStyleDeclaration` | let/var | `dom.style` | ✗ |
| `dom` | `HTMLElement` | let/var | `this.dom` | ✗ |
| `dom` | `HTMLElement` | let/var | `this.dom` | ✗ |
| `dom` | `HTMLElement` | let/var | `this.dom` | ✗ |
| `canvas` | `any` | let/var | `this.canvas` | ✗ |
| `links` | `any[]` | let/var | `[]` | ✗ |
| `element` | `any` | let/var | `this.elements[ this.elements.length - 1 ]` | ✗ |
| `elements` | `any[]` | let/var | `[]` | ✗ |
| `elements` | `any[]` | let/var | `this.elements` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `dx` | `number` | let/var | `p2x - p1x` | ✗ |
| `dy` | `number` | let/var | `p2y - p1y` | ✗ |
| `offset` | `number` | let/var | `Math.sqrt( ( dx * dx ) + ( dy * dy ) ) * ( invert ? - .3 : .3 )` | ✗ |
| `colors` | `string[]` | let/var | `[ '#ff4444', '#44ff44', '#4444ff' ]` | ✗ |
| `touchData` | `any` | let/var | `null` | ✗ |
| `delta` | `number` | let/var | `e.deltaY * .003` | ✗ |
| `clientX` | `number` | let/var | `( e.touches[ 0 ].clientX + e.touches[ 1 ].clientX ) / 2` | ✗ |
| `clientY` | `number` | let/var | `( e.touches[ 0 ].clientY + e.touches[ 1 ].clientY ) / 2` | ✗ |
| `delta` | `number` | let/var | `( touchData.distance - distance ) * .003` | ✗ |
| `clientX` | `any` | let/var | `e.touches[ 0 ].clientX` | ✗ |
| `clientY` | `any` | let/var | `e.touches[ 0 ].clientY` | ✗ |
| `zoom` | `number` | let/var | `this.zoom` | ✗ |
| `dropEnterCount` | `number` | let/var | `0` | ✗ |
| `centerNodeX` | `number` | let/var | `dropNode.getWidth() / 2` | ✗ |
| `zoom` | `number` | let/var | `this.zoom` | ✗ |
| `clientMapX` | `number` | let/var | `data.client.x - rect.left` | ✗ |
| `clientMapY` | `number` | let/var | `data.client.y - rect.top` | ✗ |
| `overMapScreen` | `boolean` | let/var | `clientMapX > screen.x && clientMapY > screen.y && clientMapX < screen.x + scr...` | ✗ |
| `scaleX` | `number` | let/var | `this._mapInfo.width / this.mapCanvas.width` | ✗ |
| `scrollLeft` | `number` | let/var | `- this._mapInfo.left - ( clientMapX * scaleX )` | ✗ |
| `scrollTop` | `number` | let/var | `- this._mapInfo.top - ( clientMapY * ( this._mapInfo.height / this.mapCanvas....` | ✗ |
| `event` | `any` | let/var | `e.touches ? e.touches[ 0 ] : e` | ✗ |
| `rectClientX` | `number` | let/var | `( this.clientX - rect.left ) / zoom` | ✗ |
| `rectClientY` | `number` | let/var | `( this.clientY - rect.top ) / zoom` | ✗ |
| `bounds` | `{ x: number; y: number; width: number...` | let/var | `{ x: Infinity, y: Infinity, width: - Infinity, height: - Infinity }` | ✗ |
| `classList` | `DOMTokenList` | let/var | `this.dom.classList` | ✗ |
| `userAgent` | `string` | let/var | `navigator.userAgent` | ✗ |
| `isSafari` | `boolean` | let/var | `/Safari/.test( userAgent ) && ! /Chrome/.test( userAgent )` | ✗ |
| `nodes` | `any[]` | let/var | `this.nodes` | ✗ |
| `nodes` | `any[]` | let/var | `this.nodes` | ✗ |
| `links` | `any[]` | let/var | `[]` | ✗ |
| `previousNode` | `any` | let/var | `this.selected` | ✗ |
| `boundsWidth` | `number` | let/var | `- bounds.x + bounds.width` | ✗ |
| `boundsHeight` | `number` | let/var | `- bounds.y + bounds.height` | ✗ |
| `mapScale` | `number` | let/var | `Math.min( mapCanvas.width / boundsWidth, mapCanvas.height / boundsHeight ) * .5` | ✗ |
| `boundsMapWidth` | `number` | let/var | `boundsWidth * mapScale` | ✗ |
| `boundsMapHeight` | `number` | let/var | `boundsHeight * mapScale` | ✗ |
| `boundsOffsetX` | `number` | let/var | `( mapCanvas.width / 2 ) - ( boundsMapWidth / 2 )` | ✗ |
| `boundsOffsetY` | `number` | let/var | `( mapCanvas.height / 2 ) - ( boundsMapHeight / 2 )` | ✗ |
| `selectedNode` | `any` | let/var | `null` | ✗ |
| `screenMapX` | `number` | let/var | `( - ( scrollLeft + bounds.x ) * mapScale ) + boundsOffsetX` | ✗ |
| `screenMapY` | `number` | let/var | `( - ( scrollTop + bounds.y ) * mapScale ) + boundsOffsetY` | ✗ |
| `screenMapWidth` | `number` | let/var | `( canvas.width * mapScale ) / zoom` | ✗ |
| `screenMapHeight` | `number` | let/var | `( canvas.height * mapScale ) / zoom` | ✗ |
| `domRect` | `DOMRect` | let/var | `this.rect` | ✗ |
| `aPos` | `{ x: number; y: number; }` | let/var | `{ x: 0, y: 0 }` | ✗ |
| `bPos` | `{ x: number; y: number; }` | let/var | `{ x: 0, y: 0 }` | ✗ |
| `offsetIORadius` | `10` | let/var | `10` | ✗ |
| `dragging` | `string` | let/var | `''` | ✗ |
| `draggingLink` | `string` | let/var | `''` | ✗ |
| `length` | `number` | let/var | `0` | ✗ |
| `drawContext` | `CanvasRenderingContext2D` | let/var | `draggingLink ? frontContext : context` | ✗ |
| `colorA` | `any` | let/var | `null` | ✗ |
| `colorB` | `any` | let/var | `null` | ✗ |
| `color` | `string` | let/var | `colors[ i ] \|\| '#ffffff'` | ✗ |
| `marginY` | `4` | let/var | `4` | ✗ |
| `colorA` | `any` | let/var | `lioElement.getRIOColor() \|\| color` | ✗ |
| `colorB` | `any` | let/var | `rioElement.getLIOColor() \|\| color` | ✗ |
| `aCenterY` | `number` | let/var | `( ( rioLength * marginY ) * .5 ) - ( marginY / 2 )` | ✗ |
| `bCenterY` | `number` | let/var | `( ( lioLength * marginY ) * .5 ) - ( marginY / 2 )` | ✗ |
| `aPosY` | `number` | let/var | `( aIndex * marginY ) - 1` | ✗ |
| `bPosY` | `number` | let/var | `( bIndex * marginY ) - 1` | ✗ |
| `nodes` | `any[]` | let/var | `[]` | ✗ |
| `dom` | `HTMLElement` | let/var | `this.dom` | ✗ |
| `lastContext` | `any` | let/var | `null` | ✗ |
| `button` | `any` | let/var | `e ? e.target : null` | ✗ |
| `button` | `any` | let/var | `e.target` | ✗ |
| `dom` | `HTMLElement` | let/var | `this.dom` | ✗ |
| `filter` | `boolean` | let/var | `true` | ✗ |
| `filterNeedUpdate` | `boolean` | let/var | `true` | ✗ |
| `key` | `string` | let/var | `e.key` | ✗ |
| `index` | `number` | let/var | `this.filteredIndex` | ✗ |
| `index` | `number` | let/var | `this.filteredIndex` | ✗ |
| `filteredItem` | `any` | let/var | `this.filtered[ index ]` | ✗ |
| `tags` | `WeakMap<WeakKey, any>` | let/var | `this.tags` | ✗ |
| `filtered` | `any[]` | let/var | `[]` | ✗ |
| `buttonTags` | `string` | let/var | `tags.has( button ) ? ' ' + tags.get( button ) : ''` | ✗ |
| `score` | `number` | let/var | `text.length / label.length` | ✗ |
| `button` | `any` | let/var | `this.filtered[ i ].button` | ✗ |
| `diff` | `number` | let/var | `delta.x - delta.y` | ✗ |
| `value` | `any` | let/var | `data.value + ( diff * this.step )` | ✗ |
| `fract` | `number` | let/var | `this.step % 1` | ✗ |
| `dom` | `any` | let/var | `this.dom` | ✗ |
| `defaultValue` | `any` | let/var | `dom.value` | ✗ |
| `containsDefaultValue` | `boolean` | let/var | `false` | ✗ |
| `opt` | `any` | let/var | `options[ index ]` | ✗ |
| `currentOptions` | `any` | let/var | `this.options` | ✗ |
| `sensibility` | `0.001` | let/var | `.001` | ✗ |
| `field` | `NumberInput` | let/var | `new NumberInput( value, min, max, step )` | ✗ |
| `keyDownStr` | `string` | let/var | `''` | ✗ |
| `dom` | `any` | let/var | `this._datalistDOM` | ✗ |
| `datalistId` | `string` | let/var | `'input-dt-' + this.id` | ✗ |
| `dom` | `any` | let/var | `this._buttonsDOM` | ✗ |
| `childrenDOM` | `any` | let/var | `this.childrenDOM` | ✗ |
| `dom` | `HTMLElement` | let/var | `this.dom` | ✗ |
| `LoaderLib` | `{}` | let/var | `{}` | ✗ |
| `parseType` | `string` | let/var | `this.parseType` | ✗ |
| `type` | `any` | let/var | `json.type` | ✗ |
| `flowClass` | `any` | let/var | `lib[ type ] ? lib[ type ] : ( LoaderLib[ type ] \|\| Flow[ type ] )` | ✗ |
| `flowObj` | `any` | let/var | `new flowClass()` | ✗ |
| `objects` | `{}` | let/var | `{}` | ✗ |
| `obj` | `any` | let/var | `json.objects[ id ]` | ✗ |
| `type` | `any` | let/var | `obj.type` | ✗ |
| `flowClass` | `any` | let/var | `lib[ type ] ? lib[ type ] : ( LoaderLib[ type ] \|\| Flow[ type ] )` | ✗ |
| `ref` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `newObject` | `any` | let/var | `objects[ id ]` | ✗ |


---

## Functions

### `__flow__addCSS(css: any): void`

**JSDoc:**
```typescript
/**
 * https://github.com/sunag/flow
 */
```

**Parameters:**

- **`css`** `any`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `style.setAttribute`
- `document.head.appendChild`

<details><summary>Code</summary>

```typescript
function __flow__addCSS( css ) {

	try {

		const style = document.createElement( 'style' );

		style.setAttribute( 'type', 'text/css' );
		style.innerHTML = css;
		document.head.appendChild( style );

	} catch ( e ) {}

}
```
</details>

### `Serializer.setSerializable(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setSerializable( value ) {

		this._serializable = value;

		return this;

	}
```
</details>

### `Serializer.getSerializable(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
getSerializable() {

		return this._serializable;

	}
```
</details>

### `Serializer.serialize(): void`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
serialize( /*data*/ ) {

		console.warn( 'Serializer: Abstract function.' );

	}
```
</details>

### `Serializer.deserialize(): void`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
deserialize( /*data*/ ) {

		console.warn( 'Serializer: Abstract function.' );

	}
```
</details>

### `Serializer.deserializeLib(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
deserializeLib( /*data, lib*/ ) {

		// Abstract function.

	}
```
</details>

### `Serializer.toJSON(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `this.serialize`

<details><summary>Code</summary>

```typescript
toJSON( data = null ) {

		let object = null;

		const id = this.id;

		if ( data !== null ) {

			const objects = data.objects;

			object = objects[ id ];

			if ( object === undefined ) {

				object = { objects };

				this.serialize( object );

				delete object.objects;

				objects[ id ] = object;

			}

		} else {

			object = { objects: {} };

			this.serialize( object );

		}

		object.id = id;
		object.type = this.className;

		return object;

	}
```
</details>

### `PointerMonitor.start(): this`

**Returns:** `this`

**Calls:**

- `window.addEventListener`

<details><summary>Code</summary>

```typescript
start() {

		if ( this.started ) return;

		this.started = true;

		window.addEventListener( 'wheel', this._onMoveEvent, true );

		window.addEventListener( 'mousedown', this._onMoveEvent, true );
		window.addEventListener( 'touchstart', this._onMoveEvent, true );

		window.addEventListener( 'mousemove', this._onMoveEvent, true );
		window.addEventListener( 'touchmove', this._onMoveEvent, true );

		window.addEventListener( 'dragover', this._onMoveEvent, true );

		return this;

	}
```
</details>

### `draggableDOM(dom: any, callback: any, settings: {}): void`

**Parameters:**

- **`dom`** `any`
- **`callback`** `any`
- **`settings`** `{}`

**Returns:** `void`

**Calls:**

- `Object.assign`
- `Number`
- `e.stopImmediatePropagation`
- `callback`
- `window.addEventListener`
- `getZoom`
- `Math.abs`
- `dom.classList.add`
- `document.body.classList.add`
- `className.split`
- `dom.classList.remove`
- `document.body.classList.remove`
- `window.removeEventListener`
- `dom.removeEventListener`
- `onMouseDown`
- `dom.addEventListener`

<details><summary>Code</summary>

```typescript
( dom, callback = null, settings = {} ) => {

	settings = Object.assign( {
		className: 'dragging',
		click: false,
		bypass: false
	}, settings );

	let dragData = null;

	const { className, click, bypass } = settings;

	const getZoom = () => {

		let zoomDOM = dom;

		while ( zoomDOM && zoomDOM !== document ) {

			const zoom = zoomDOM.style.zoom;

			if ( zoom ) {

				return Number( zoom );

			}

			zoomDOM = zoomDOM.parentNode;

		}

		return 1;

	};

	const onMouseDown = ( e ) => {

		const event = e.touches ? e.touches[ 0 ] : e;

		if ( bypass === false ) e.stopImmediatePropagation();

		dragData = {
			client: { x: event.clientX, y: event.clientY },
			delta: { x: 0, y: 0 },
			start: { x: dom.offsetLeft, y: dom.offsetTop },
			frame: 0,
			isDown: true,
			dragging: false,
			isTouch: !! e.touches
		};

		if ( click === true ) {

			callback( dragData );

			dragData.frame ++;

		}

		window.addEventListener( 'mousemove', onGlobalMouseMove );
		window.addEventListener( 'mouseup', onGlobalMouseUp );

		window.addEventListener( 'touchmove', onGlobalMouseMove );
		window.addEventListener( 'touchend', onGlobalMouseUp );

	};

	const onGlobalMouseMove = ( e ) => {

		const { start, delta, client } = dragData;

		const event = e.touches ? e.touches[ 0 ] : e;

		const zoom = getZoom();

		delta.x = ( event.clientX - client.x ) / zoom;
		delta.y = ( event.clientY - client.y ) / zoom;

		dragData.x = start.x + delta.x;
		dragData.y = start.y + delta.y;

		if ( dragData.dragging === true ) {

			if ( callback !== null ) {

				callback( dragData );

				dragData.frame ++;

			} else {

				dom.style.cssText += `; left: ${ dragData.x }px; top: ${ dragData.y }px;`;

			}

			if ( bypass === false ) e.stopImmediatePropagation();

		} else {

			if ( Math.abs( delta.x ) > 2 || Math.abs( delta.y ) > 2 ) {

				dragData.dragging = true;

				dom.classList.add( 'drag' );

				if ( className ) document.body.classList.add( ...className.split( ' ' ) );

				if ( bypass === false ) e.stopImmediatePropagation();

			}

		}

	};

	const onGlobalMouseUp = ( e ) => {

		if ( bypass === false ) e.stopImmediatePropagation();

		dom.classList.remove( 'drag' );

		if ( className ) document.body.classList.remove( ...className.split( ' ' ) );

		window.removeEventListener( 'mousemove', onGlobalMouseMove );
		window.removeEventListener( 'mouseup', onGlobalMouseUp );

		window.removeEventListener( 'touchmove', onGlobalMouseMove );
		window.removeEventListener( 'touchend', onGlobalMouseUp );

		if ( callback === null ) {

			dom.removeEventListener( 'mousedown', onMouseDown );
			dom.removeEventListener( 'touchstart', onMouseDown );

		}

		dragData.dragging = false;
		dragData.isDown = false;

		if ( callback !== null ) {

			callback( dragData );

			dragData.frame ++;

		}

	};

	if ( dom instanceof Event ) {

		const e = dom;
		dom = e.target;

		onMouseDown( e );

	} else {

		dom.addEventListener( 'mousedown', onMouseDown );
		dom.addEventListener( 'touchstart', onMouseDown );

	}

}
```
</details>

### `getZoom(): number`

**Returns:** `number`

**Calls:**

- `Number`

<details><summary>Code</summary>

```typescript
() => {

		let zoomDOM = dom;

		while ( zoomDOM && zoomDOM !== document ) {

			const zoom = zoomDOM.style.zoom;

			if ( zoom ) {

				return Number( zoom );

			}

			zoomDOM = zoomDOM.parentNode;

		}

		return 1;

	}
```
</details>

### `onMouseDown(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.stopImmediatePropagation`
- `callback`
- `window.addEventListener`

<details><summary>Code</summary>

```typescript
( e ) => {

		const event = e.touches ? e.touches[ 0 ] : e;

		if ( bypass === false ) e.stopImmediatePropagation();

		dragData = {
			client: { x: event.clientX, y: event.clientY },
			delta: { x: 0, y: 0 },
			start: { x: dom.offsetLeft, y: dom.offsetTop },
			frame: 0,
			isDown: true,
			dragging: false,
			isTouch: !! e.touches
		};

		if ( click === true ) {

			callback( dragData );

			dragData.frame ++;

		}

		window.addEventListener( 'mousemove', onGlobalMouseMove );
		window.addEventListener( 'mouseup', onGlobalMouseUp );

		window.addEventListener( 'touchmove', onGlobalMouseMove );
		window.addEventListener( 'touchend', onGlobalMouseUp );

	}
```
</details>

### `onGlobalMouseMove(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `getZoom`
- `callback`
- `e.stopImmediatePropagation`
- `Math.abs`
- `dom.classList.add`
- `document.body.classList.add`
- `className.split`

<details><summary>Code</summary>

```typescript
( e ) => {

		const { start, delta, client } = dragData;

		const event = e.touches ? e.touches[ 0 ] : e;

		const zoom = getZoom();

		delta.x = ( event.clientX - client.x ) / zoom;
		delta.y = ( event.clientY - client.y ) / zoom;

		dragData.x = start.x + delta.x;
		dragData.y = start.y + delta.y;

		if ( dragData.dragging === true ) {

			if ( callback !== null ) {

				callback( dragData );

				dragData.frame ++;

			} else {

				dom.style.cssText += `; left: ${ dragData.x }px; top: ${ dragData.y }px;`;

			}

			if ( bypass === false ) e.stopImmediatePropagation();

		} else {

			if ( Math.abs( delta.x ) > 2 || Math.abs( delta.y ) > 2 ) {

				dragData.dragging = true;

				dom.classList.add( 'drag' );

				if ( className ) document.body.classList.add( ...className.split( ' ' ) );

				if ( bypass === false ) e.stopImmediatePropagation();

			}

		}

	}
```
</details>

### `onGlobalMouseUp(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.stopImmediatePropagation`
- `dom.classList.remove`
- `document.body.classList.remove`
- `className.split`
- `window.removeEventListener`
- `dom.removeEventListener`
- `callback`

<details><summary>Code</summary>

```typescript
( e ) => {

		if ( bypass === false ) e.stopImmediatePropagation();

		dom.classList.remove( 'drag' );

		if ( className ) document.body.classList.remove( ...className.split( ' ' ) );

		window.removeEventListener( 'mousemove', onGlobalMouseMove );
		window.removeEventListener( 'mouseup', onGlobalMouseUp );

		window.removeEventListener( 'touchmove', onGlobalMouseMove );
		window.removeEventListener( 'touchend', onGlobalMouseUp );

		if ( callback === null ) {

			dom.removeEventListener( 'mousedown', onMouseDown );
			dom.removeEventListener( 'touchstart', onMouseDown );

		}

		dragData.dragging = false;
		dragData.isDown = false;

		if ( callback !== null ) {

			callback( dragData );

			dragData.frame ++;

		}

	}
```
</details>

### `dispatchEventList(list: any, params: any[]): boolean`

**Parameters:**

- **`list`** `any`
- **`params`** `any[]`

**Returns:** `boolean`

**Calls:**

- `callback`

<details><summary>Code</summary>

```typescript
( list, ...params ) => {

	for ( const callback of list ) {

		if ( callback( ...params ) === false ) {

			return false;

		}

	}

	return true;

}
```
</details>

### `numberToPX(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

**Calls:**

- `isNaN`

<details><summary>Code</summary>

```typescript
( val ) => {

	if ( isNaN( val ) === false ) {

		val = `${ val }px`;

	}

	return val;

}
```
</details>

### `numberToHex(val: any): any`

**Parameters:**

- **`val`** `any`

**Returns:** `any`

**Calls:**

- `isNaN`
- `val.toString( 16 ).padStart`

<details><summary>Code</summary>

```typescript
( val ) => {

	if ( isNaN( val ) === false ) {

		val = `#${ val.toString( 16 ).padStart( 6, '0' ) }`;

	}

	return val;

}
```
</details>

### `rgbaToArray(rgba: any): any`

**Parameters:**

- **`rgba`** `any`

**Returns:** `any`

**Calls:**

- `rgba.substring( rgba.indexOf( '(' ) + 1, rgba.indexOf( ')' ) )
		.split( ',' )
		.map`
- `parseInt`
- `num.trim`

<details><summary>Code</summary>

```typescript
( rgba ) => {

	const values = rgba.substring( rgba.indexOf( '(' ) + 1, rgba.indexOf( ')' ) )
		.split( ',' )
		.map( num => parseInt( num.trim() ) );

	return values;

}
```
</details>

### `removeDOMClass(dom: any, classList: any): void`

**Parameters:**

- **`dom`** `any`
- **`classList`** `any`

**Returns:** `void`

**Calls:**

- `classList.split( ' ' ).forEach`
- `dom.classList.remove`

<details><summary>Code</summary>

```typescript
( dom, classList ) => {

	if ( classList ) classList.split( ' ' ).forEach( alignClass => dom.classList.remove( alignClass ) );

}
```
</details>

### `addDOMClass(dom: any, classList: any): void`

**Parameters:**

- **`dom`** `any`
- **`classList`** `any`

**Returns:** `void`

**Calls:**

- `classList.split( ' ' ).forEach`
- `dom.classList.add`

<details><summary>Code</summary>

```typescript
( dom, classList ) => {

	if ( classList ) classList.split( ' ' ).forEach( alignClass => dom.classList.add( alignClass ) );

}
```
</details>

### `Element.setAttribute(name: any, value: any): this`

**Parameters:**

- **`name`** `any`
- **`value`** `any`

**Returns:** `this`

**Calls:**

- `this.dom.setAttribute`

<details><summary>Code</summary>

```typescript
setAttribute( name, value ) {

		this.dom.setAttribute( name, value );

		return this;

	}
```
</details>

### `Element.onValid(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.valid.push`

<details><summary>Code</summary>

```typescript
onValid( callback ) {

		this.events.valid.push( callback );

		return this;

	}
```
</details>

### `Element.onConnect(callback: any, childrens: boolean): this`

**Parameters:**

- **`callback`** `any`
- **`childrens`** `boolean`

**Returns:** `this`

**Calls:**

- `this.events.connect.push`
- `this.events.connectChildren.push`

<details><summary>Code</summary>

```typescript
onConnect( callback, childrens = false ) {

		this.events.connect.push( callback );

		if ( childrens ) {

			this.events.connectChildren.push( callback );

		}

		return this;

	}
```
</details>

### `Element.setObjectCallback(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setObjectCallback( callback ) {

		this.objectCallback = callback;

		return this;

	}
```
</details>

### `Element.setObject(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setObject( value ) {

		this.object = value;

		return this;

	}
```
</details>

### `Element.getObject(output: any): any`

**Parameters:**

- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.objectCallback`

<details><summary>Code</summary>

```typescript
getObject( output = null ) {

		return this.objectCallback ? this.objectCallback( output ) : this.object;

	}
```
</details>

### `Element.setVisible(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setVisible( value ) {

		this.visible = value;

		this.dom.style.display = value ? '' : 'none';

		return this;

	}
```
</details>

### `Element.getVisible(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
getVisible() {

		return this.visible;

	}
```
</details>

### `Element.setEnabledInputs(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `dom.classList.remove`
- `dom.classList.add`

<details><summary>Code</summary>

```typescript
setEnabledInputs( value ) {

		const dom = this.dom;

		if ( ! this.enabledInputs ) dom.classList.remove( 'inputs-disable' );

		if ( ! value ) dom.classList.add( 'inputs-disable' );

		this.enabledInputs = value;

		return this;

	}
```
</details>

### `Element.getEnabledInputs(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
getEnabledInputs() {

		return this.enabledInputs;

	}
```
</details>

### `Element.setColor(color: any): this`

**Parameters:**

- **`color`** `any`

**Returns:** `this`

**Calls:**

- `numberToHex`

<details><summary>Code</summary>

```typescript
setColor( color ) {

		this.dom.style[ 'background-color' ] = numberToHex( color );
		this.color = null;

		return this;

	}
```
</details>

### `Element.getColor(): string`

**Returns:** `string`

**Calls:**

- `window.getComputedStyle`
- `css.getPropertyValue`

<details><summary>Code</summary>

```typescript
getColor() {

		if ( this.color === null ) {

			const css = window.getComputedStyle( this.dom );

			this.color = css.getPropertyValue( 'background-color' );

		}

		return this.color;

	}
```
</details>

### `Element.setStyle(style: any): this`

**Parameters:**

- **`style`** `any`

**Returns:** `this`

**Calls:**

- `dom.classList.remove`
- `dom.classList.add`

<details><summary>Code</summary>

```typescript
setStyle( style ) {

		const dom = this.dom;

		if ( this.style ) dom.classList.remove( this.style );

		if ( style ) dom.classList.add( style );

		this.style = style;
		this.color = null;

		return this;

	}
```
</details>

### `Element.setInput(length: any): this`

**Parameters:**

- **`length`** `any`

**Returns:** `this`

**Calls:**

- `this.setLIO`
- `this.setRIO`

<details><summary>Code</summary>

```typescript
setInput( length ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setLIO( length );

		} else {

			return this.setRIO( length );

		}

	}
```
</details>

### `Element.setInputColor(color: any): this`

**Parameters:**

- **`color`** `any`

**Returns:** `this`

**Calls:**

- `this.setLIOColor`
- `this.setRIOColor`

<details><summary>Code</summary>

```typescript
setInputColor( color ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setLIOColor( color );

		} else {

			return this.setRIOColor( color );

		}

	}
```
</details>

### `Element.setOutput(length: any): this`

**Parameters:**

- **`length`** `any`

**Returns:** `this`

**Calls:**

- `this.setRIO`
- `this.setLIO`

<details><summary>Code</summary>

```typescript
setOutput( length ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setRIO( length );

		} else {

			return this.setLIO( length );

		}

	}
```
</details>

### `Element.setOutputColor(color: any): this`

**Parameters:**

- **`color`** `any`

**Returns:** `this`

**Calls:**

- `this.setRIOColor`
- `this.setLIOColor`

<details><summary>Code</summary>

```typescript
setOutputColor( color ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setRIOColor( color );

		} else {

			return this.setLIOColor( color );

		}

	}
```
</details>

### `Element.setLIOColor(color: any): this`

**Parameters:**

- **`color`** `any`

**Returns:** `this`

**Calls:**

- `numberToHex`

<details><summary>Code</summary>

```typescript
setLIOColor( color ) {

		this.lioDOM.style[ 'border-color' ] = numberToHex( color );

		return this;

	}
```
</details>

### `Element.setLIO(length: any): this`

**Parameters:**

- **`length`** `any`

**Returns:** `this`

**Calls:**

- `this.dom.classList.add`
- `this.dom.prepend`
- `this.dom.classList.remove`
- `this.lioDOM.remove`

<details><summary>Code</summary>

```typescript
setLIO( length ) {

		this.lioLength = length;

		this.lioDOM.style.visibility = length > 0 ? '' : 'hidden';

		if ( length > 0 ) {

			this.dom.classList.add( 'lio' );
			this.dom.prepend( this.lioDOM );

		} else {

			this.dom.classList.remove( 'lio' );
			this.lioDOM.remove();

		}

		return this;

	}
```
</details>

### `Element.getLIOColor(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getLIOColor() {

		return this.lioDOM.style[ 'border-color' ];

	}
```
</details>

### `Element.setRIOColor(color: any): this`

**Parameters:**

- **`color`** `any`

**Returns:** `this`

**Calls:**

- `numberToHex`

<details><summary>Code</summary>

```typescript
setRIOColor( color ) {

		this.rioDOM.style[ 'border-color' ] = numberToHex( color );

		return this;

	}
```
</details>

### `Element.getRIOColor(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getRIOColor() {

		return this.rioDOM.style[ 'border-color' ];

	}
```
</details>

### `Element.setRIO(length: any): this`

**Parameters:**

- **`length`** `any`

**Returns:** `this`

**Calls:**

- `this.dom.classList.add`
- `this.dom.prepend`
- `this.dom.classList.remove`
- `this.rioDOM.remove`

<details><summary>Code</summary>

```typescript
setRIO( length ) {

		this.rioLength = length;

		this.rioDOM.style.visibility = length > 0 ? '' : 'hidden';

		if ( length > 0 ) {

			this.dom.classList.add( 'rio' );
			this.dom.prepend( this.rioDOM );

		} else {

			this.dom.classList.remove( 'rio' );
			this.rioDOM.remove();

		}

		return this;

	}
```
</details>

### `Element.add(input: any): this`

**Parameters:**

- **`input`** `any`

**Returns:** `this`

**Calls:**

- `this.inputs.push`
- `this.inputsDOM.append`

<details><summary>Code</summary>

```typescript
add( input ) {

		this.inputs.push( input );

		input.element = this;

		this.inputsDOM.append( input.dom );

		return this;

	}
```
</details>

### `Element.setHeight(val: any): this`

**Parameters:**

- **`val`** `any`

**Returns:** `this`

**Calls:**

- `numberToPX`

<details><summary>Code</summary>

```typescript
setHeight( val ) {

		this.dom.style.height = numberToPX( val );

		return this;

	}
```
</details>

### `Element.getHeight(): number`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
getHeight() {

		return parseInt( this.dom.style.height );

	}
```
</details>

### `Element.connect(element: any): boolean`

**Parameters:**

- **`element`** `any`

**Returns:** `boolean`

**Calls:**

- `this.disconnectDOM.dispatchEvent`
- `dispatchEventList`
- `this.links.push`
- `document.createElement`
- `this.dom.append`
- `this.dom.removeChild`
- `this.disconnectDOM.removeEventListener`
- `element.removeEventListener`
- `this.dispatchEvent`
- `this.connect`
- `e.stopPropagation`
- `this.disconnectDOM.addEventListener`
- `element.addEventListener`

**Internal Comments:**
```
// remove the current input (x5)
```

<details><summary>Code</summary>

```typescript
connect( element = null ) {

		if ( this.disconnectDOM !== null ) {

			// remove the current input

			this.disconnectDOM.dispatchEvent( new Event( 'disconnect' ) );

		}

		if ( element !== null ) {

			element = element.baseElement || element;

			if ( dispatchEventList( this.events.valid, this, element, 'connect' ) === false ) {

				return false;

			}

			const link = new Link( this, element );

			this.links.push( link );

			if ( this.disconnectDOM === null ) {

				this.disconnectDOM = document.createElement( 'f-disconnect' );
				this.disconnectDOM.innerHTML = Element.icons.unlink ? `<i class='${ Element.icons.unlink }'></i>` : '✖';

				this.dom.append( this.disconnectDOM );

				const onDisconnect = () => {

					this.links = [];
					this.dom.removeChild( this.disconnectDOM );

					this.disconnectDOM.removeEventListener( 'mousedown', onClick, true );
					this.disconnectDOM.removeEventListener( 'touchstart', onClick, true );
					this.disconnectDOM.removeEventListener( 'disconnect', onDisconnect, true );

					element.removeEventListener( 'connect', onConnect );
					element.removeEventListener( 'connectChildren', onConnect );
					element.removeEventListener( 'nodeConnect', onConnect );
					element.removeEventListener( 'nodeConnectChildren', onConnect );
					element.removeEventListener( 'dispose', onDispose );

					this.disconnectDOM = null;

				};

				const onConnect = () => {

					this.dispatchEvent( new Event( 'connectChildren' ) );

				};

				const onDispose = () => {

					this.connect();

				};

				const onClick = ( e ) => {

					e.stopPropagation();

					this.connect();

				};

				this.disconnectDOM.addEventListener( 'mousedown', onClick, true );
				this.disconnectDOM.addEventListener( 'touchstart', onClick, true );
				this.disconnectDOM.addEventListener( 'disconnect', onDisconnect, true );

				element.addEventListener( 'connect', onConnect );
				element.addEventListener( 'connectChildren', onConnect );
				element.addEventListener( 'nodeConnect', onConnect );
				element.addEventListener( 'nodeConnectChildren', onConnect );
				element.addEventListener( 'dispose', onDispose );

			}

		}

		this.dispatchEvent( new Event( 'connect' ) );

		return true;

	}
```
</details>

### `Element.dispose(): void`

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
dispose() {

		this.dispatchEvent( new Event( 'dispose' ) );

	}
```
</details>

### `Element.getInputByProperty(property: any): any`

**Parameters:**

- **`property`** `any`

**Returns:** `any`

**Calls:**

- `input.getProperty`

<details><summary>Code</summary>

```typescript
getInputByProperty( property ) {

		for ( const input of this.inputs ) {

			if ( input.getProperty() === property ) {

				return input;

			}

		}

	}
```
</details>

### `Element.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `input.toJSON`
- `input.getProperty`
- `inputs.push`
- `properties.push`
- `links.push`
- `link.outputElement.toJSON`
- `this.getHeight`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		const inputs = [];
		const properties = [];
		const links = [];

		for ( const input of this.inputs ) {

			const id = input.toJSON( data ).id;
			const property = input.getProperty();

			inputs.push( id );

			if ( property !== null ) {

				properties.push( { property, id } );

			}

		}

		for ( const link of this.links ) {

			if ( link.inputElement !== null && link.outputElement !== null ) {

				links.push( link.outputElement.toJSON( data ).id );

			}

		}

		if ( this.inputLength > 0 ) data.inputLength = this.inputLength;
		if ( this.outputLength > 0 ) data.outputLength = this.outputLength;

		if ( inputs.length > 0 ) data.inputs = inputs;
		if ( properties.length > 0 ) data.properties = properties;
		if ( links.length > 0 ) data.links = links;

		if ( this.style !== '' ) {

			data.style = this.style;

		}

		data.height = this.getHeight();

	}
```
</details>

### `Element.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.setInput`
- `this.setOutput`
- `this.getInputByProperty`
- `this.add`
- `this.connect`
- `this.setStyle`
- `this.setHeight`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		if ( data.inputLength !== undefined ) this.setInput( data.inputLength );
		if ( data.outputLength !== undefined ) this.setOutput( data.outputLength );

		if ( data.properties !== undefined ) {

			for ( const { id, property } of data.properties ) {

				data.objects[ id ] = this.getInputByProperty( property );

			}

		} else if ( data.inputs !== undefined ) {

			const inputs = this.inputs;

			if ( inputs.length > 0 ) {

				let index = 0;

				for ( const id of data.inputs ) {

					data.objects[ id ] = inputs[ index ++ ];

				}

			} else {

				for ( const id of data.inputs ) {

					this.add( data.objects[ id ] );

				}

			}

		}

		if ( data.links !== undefined ) {

			for ( const id of data.links ) {

				this.connect( data.objects[ id ] );

			}

		}

		if ( data.style !== undefined ) {

			this.setStyle( data.style );

		}

		if ( data.height !== undefined ) {

			this.setHeight( data.height );

		}

	}
```
</details>

### `Element.getLinkedObject(output: any): any`

**Parameters:**

- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.getLinkedElement`
- `linkedElement.getObject`

<details><summary>Code</summary>

```typescript
getLinkedObject( output = null ) {

		const linkedElement = this.getLinkedElement();

		return linkedElement ? linkedElement.getObject( output ) : null;

	}
```
</details>

### `Element.getLinkedElement(): any`

**Returns:** `any`

**Calls:**

- `this.getLink`

<details><summary>Code</summary>

```typescript
getLinkedElement() {

		const link = this.getLink();

		return link ? link.outputElement : null;

	}
```
</details>

### `Element.getLink(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getLink() {

		return this.links[ 0 ];

	}
```
</details>

### `Element._createIO(type: any): HTMLElement`

**Parameters:**

- **`type`** `any`

**Returns:** `HTMLElement`

**Calls:**

- `document.createElement`
- `e.preventDefault`
- `e.stopPropagation`
- `nodeDOM.classList.add`
- `ioDOM.classList.add`
- `dom.classList.add`
- `this.links.push`
- `draggableDOM`
- `previewLink.outputElement.dom.classList.remove`
- `previewLink.inputElement.dom.classList.remove`
- `dispatchEventList`
- `previewLink.outputElement.dom.classList.add`
- `previewLink.inputElement.dom.classList.add`
- `nodeDOM.classList.remove`
- `ioDOM.classList.remove`
- `dom.classList.remove`
- `this.links.splice`
- `this.links.indexOf`
- `link.outputElement.node.isCircular`
- `link.inputElement.connect`
- `ioDOM.addEventListener`

**Internal Comments:**
```
// check if is an is circular link
//
```

<details><summary>Code</summary>

```typescript
_createIO( type ) {

		const { dom } = this;

		const ioDOM = document.createElement( 'f-io' );
		ioDOM.style.visibility = 'hidden';
		ioDOM.className = type;

		const onConnectEvent = ( e ) => {

			e.preventDefault();

			e.stopPropagation();

			selected = null;

			const nodeDOM = this.node.dom;

			nodeDOM.classList.add( 'io-connect' );

			ioDOM.classList.add( 'connect' );
			dom.classList.add( 'select' );

			const defaultOutput = Link.InputDirection === 'left' ? 'lio' : 'rio';

			const link = type === defaultOutput ? new Link( this ) : new Link( null, this );
			const previewLink = new Link( link.inputElement, link.outputElement );

			this.links.push( link );

			draggableDOM( e, ( data ) => {

				if ( previewLink.outputElement )
					previewLink.outputElement.dom.classList.remove( 'invalid' );

				if ( previewLink.inputElement )
					previewLink.inputElement.dom.classList.remove( 'invalid' );

				previewLink.inputElement = link.inputElement;
				previewLink.outputElement = link.outputElement;

				if ( type === defaultOutput ) {

					previewLink.outputElement = selected;

				} else {

					previewLink.inputElement = selected;

				}

				const isInvalid = previewLink.inputElement !== null && previewLink.outputElement !== null &&
					previewLink.inputElement.inputLength > 0 && previewLink.outputElement.outputLength > 0 &&
					dispatchEventList( previewLink.inputElement.events.valid, previewLink.inputElement, previewLink.outputElement, data.dragging ? 'dragging' : 'dragged' ) === false;

				if ( data.dragging && isInvalid ) {

					if ( type === defaultOutput ) {

						if ( previewLink.outputElement )
							previewLink.outputElement.dom.classList.add( 'invalid' );

					} else {

						if ( previewLink.inputElement )
							previewLink.inputElement.dom.classList.add( 'invalid' );

					}

					return;

				}

				if ( ! data.dragging ) {

					nodeDOM.classList.remove( 'io-connect' );

					ioDOM.classList.remove( 'connect' );
					dom.classList.remove( 'select' );

					this.links.splice( this.links.indexOf( link ), 1 );

					if ( selected !== null && ! isInvalid ) {

						link.inputElement = previewLink.inputElement;
						link.outputElement = previewLink.outputElement;

						// check if is an is circular link

						if ( link.outputElement.node.isCircular( link.inputElement.node ) ) {

							return;

						}

						//

						if ( link.inputElement.inputLength > 0 && link.outputElement.outputLength > 0 ) {

							link.inputElement.connect( link.outputElement );

						}

					}

				}

			}, { className: 'connecting' } );

		};

		ioDOM.addEventListener( 'mousedown', onConnectEvent, true );
		ioDOM.addEventListener( 'touchstart', onConnectEvent, true );

		return ioDOM;

	}
```
</details>

### `onSelect(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `document.elementFromPoint`

<details><summary>Code</summary>

```typescript
( e ) => {

			let element = this;

			if ( e.changedTouches && e.changedTouches.length > 0 ) {

				const touch = e.changedTouches[ 0 ];

				let overDOM = document.elementFromPoint( touch.clientX, touch.clientY );

				while ( overDOM && ( ! overDOM.element || ! overDOM.element.isElement ) ) {

					overDOM = overDOM.parentNode;

				}

				element = overDOM ? overDOM.element : null;

			}

			const type = e.type;

			if ( ( type === 'mouseout' ) && selected === element ) {

				selected = null;

			} else {

				selected = element;

			}

		}
```
</details>

### `onDisconnect(): void`

**Returns:** `void`

**Calls:**

- `this.dom.removeChild`
- `this.disconnectDOM.removeEventListener`
- `element.removeEventListener`

<details><summary>Code</summary>

```typescript
() => {

					this.links = [];
					this.dom.removeChild( this.disconnectDOM );

					this.disconnectDOM.removeEventListener( 'mousedown', onClick, true );
					this.disconnectDOM.removeEventListener( 'touchstart', onClick, true );
					this.disconnectDOM.removeEventListener( 'disconnect', onDisconnect, true );

					element.removeEventListener( 'connect', onConnect );
					element.removeEventListener( 'connectChildren', onConnect );
					element.removeEventListener( 'nodeConnect', onConnect );
					element.removeEventListener( 'nodeConnectChildren', onConnect );
					element.removeEventListener( 'dispose', onDispose );

					this.disconnectDOM = null;

				}
```
</details>

### `onConnect(): void`

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
() => {

					this.dispatchEvent( new Event( 'connectChildren' ) );

				}
```
</details>

### `onDispose(): void`

**Returns:** `void`

**Calls:**

- `this.connect`

<details><summary>Code</summary>

```typescript
() => {

					this.connect();

				}
```
</details>

### `onClick(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.stopPropagation`
- `this.connect`

<details><summary>Code</summary>

```typescript
( e ) => {

					e.stopPropagation();

					this.connect();

				}
```
</details>

### `onConnectEvent(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.preventDefault`
- `e.stopPropagation`
- `nodeDOM.classList.add`
- `ioDOM.classList.add`
- `dom.classList.add`
- `this.links.push`
- `draggableDOM`
- `previewLink.outputElement.dom.classList.remove`
- `previewLink.inputElement.dom.classList.remove`
- `dispatchEventList`
- `previewLink.outputElement.dom.classList.add`
- `previewLink.inputElement.dom.classList.add`
- `nodeDOM.classList.remove`
- `ioDOM.classList.remove`
- `dom.classList.remove`
- `this.links.splice`
- `this.links.indexOf`
- `link.outputElement.node.isCircular`
- `link.inputElement.connect`

**Internal Comments:**
```
// check if is an is circular link
//
```

<details><summary>Code</summary>

```typescript
( e ) => {

			e.preventDefault();

			e.stopPropagation();

			selected = null;

			const nodeDOM = this.node.dom;

			nodeDOM.classList.add( 'io-connect' );

			ioDOM.classList.add( 'connect' );
			dom.classList.add( 'select' );

			const defaultOutput = Link.InputDirection === 'left' ? 'lio' : 'rio';

			const link = type === defaultOutput ? new Link( this ) : new Link( null, this );
			const previewLink = new Link( link.inputElement, link.outputElement );

			this.links.push( link );

			draggableDOM( e, ( data ) => {

				if ( previewLink.outputElement )
					previewLink.outputElement.dom.classList.remove( 'invalid' );

				if ( previewLink.inputElement )
					previewLink.inputElement.dom.classList.remove( 'invalid' );

				previewLink.inputElement = link.inputElement;
				previewLink.outputElement = link.outputElement;

				if ( type === defaultOutput ) {

					previewLink.outputElement = selected;

				} else {

					previewLink.inputElement = selected;

				}

				const isInvalid = previewLink.inputElement !== null && previewLink.outputElement !== null &&
					previewLink.inputElement.inputLength > 0 && previewLink.outputElement.outputLength > 0 &&
					dispatchEventList( previewLink.inputElement.events.valid, previewLink.inputElement, previewLink.outputElement, data.dragging ? 'dragging' : 'dragged' ) === false;

				if ( data.dragging && isInvalid ) {

					if ( type === defaultOutput ) {

						if ( previewLink.outputElement )
							previewLink.outputElement.dom.classList.add( 'invalid' );

					} else {

						if ( previewLink.inputElement )
							previewLink.inputElement.dom.classList.add( 'invalid' );

					}

					return;

				}

				if ( ! data.dragging ) {

					nodeDOM.classList.remove( 'io-connect' );

					ioDOM.classList.remove( 'connect' );
					dom.classList.remove( 'select' );

					this.links.splice( this.links.indexOf( link ), 1 );

					if ( selected !== null && ! isInvalid ) {

						link.inputElement = previewLink.inputElement;
						link.outputElement = previewLink.outputElement;

						// check if is an is circular link

						if ( link.outputElement.node.isCircular( link.inputElement.node ) ) {

							return;

						}

						//

						if ( link.inputElement.inputLength > 0 && link.outputElement.outputLength > 0 ) {

							link.inputElement.connect( link.outputElement );

						}

					}

				}

			}, { className: 'connecting' } );

		}
```
</details>

### `Input.setExtra(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setExtra( value ) {

		this.extra = value;

		return this;

	}
```
</details>

### `Input.getExtra(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getExtra() {

		return this.extra;

	}
```
</details>

### `Input.setProperty(name: any): this`

**Parameters:**

- **`name`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setProperty( name ) {

		this.property = name;

		return this;

	}
```
</details>

### `Input.getProperty(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getProperty() {

		return this.property;

	}
```
</details>

### `Input.setTagColor(color: any): this`

**Parameters:**

- **`color`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setTagColor( color ) {

		this.tagColor = color;

		this.dom.style[ 'border-left' ] = `2px solid ${color}`;

		return this;

	}
```
</details>

### `Input.getTagColor(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getTagColor() {

		return this.tagColor;

	}
```
</details>

### `Input.setToolTip(text: any): this`

**Parameters:**

- **`text`** `any`

**Returns:** `this`

**Calls:**

- `document.createElement`
- `this.dom.append`

<details><summary>Code</summary>

```typescript
setToolTip( text ) {

		const div = document.createElement( 'f-tooltip' );
		div.innerText = text;

		this.dom.append( div );

		return this;

	}
```
</details>

### `Input.onChange(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.change.push`

<details><summary>Code</summary>

```typescript
onChange( callback ) {

		this.events.change.push( callback );

		return this;

	}
```
</details>

### `Input.onClick(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.click.push`

<details><summary>Code</summary>

```typescript
onClick( callback ) {

		this.events.click.push( callback );

		return this;

	}
```
</details>

### `Input.setReadOnly(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `this.getInput`

<details><summary>Code</summary>

```typescript
setReadOnly( value ) {

		this.getInput().readOnly = value;

		return this;

	}
```
</details>

### `Input.getReadOnly(): any`

**Returns:** `any`

**Calls:**

- `this.getInput`

<details><summary>Code</summary>

```typescript
getReadOnly() {

		return this.getInput().readOnly;

	}
```
</details>

### `Input.setValue(value: any, dispatch: boolean): this`

**Parameters:**

- **`value`** `any`
- **`dispatch`** `boolean`

**Returns:** `this`

**Calls:**

- `this.getInput`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
setValue( value, dispatch = true ) {

		this.getInput().value = value;

		if ( dispatch ) this.dispatchEvent( new Event( 'change' ) );

		return this;

	}
```
</details>

### `Input.getValue(): any`

**Returns:** `any`

**Calls:**

- `this.getInput`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.getInput().value;

	}
```
</details>

### `Input.getInput(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getInput() {

		return this.dom;

	}
```
</details>

### `Input.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.getValue`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		data.value = this.getValue();

	}
```
</details>

### `Input.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.setValue`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		this.setValue( data.value );

	}
```
</details>

### `Node.setAlign(align: any): this`

**Parameters:**

- **`align`** `any`

**Returns:** `this`

**Calls:**

- `dom.classList.add`

<details><summary>Code</summary>

```typescript
setAlign( align ) {

		const dom = this.dom;
		const style = dom.style;

		style.left = '';
		style.top = '';
		style.animation = 'none';

		if ( typeof align === 'string' ) {

			dom.classList.add( align );

		} else if ( align ) {

			for ( const name in align ) {

				style[ name ] = align[ name ];

			}

		}

		return this;

	}
```
</details>

### `Node.setResizable(val: any): this`

**Parameters:**

- **`val`** `any`

**Returns:** `this`

**Calls:**

- `this.dom.classList.add`
- `this.dom.classList.remove`
- `this.updateSize`

<details><summary>Code</summary>

```typescript
setResizable( val ) {

		this.resizable = val === true;

		if ( this.resizable ) {

			this.dom.classList.add( 'resizable' );

		} else {

			this.dom.classList.remove( 'resizable' );

		}

		this.updateSize();

		return this;

	}
```
</details>

### `Node.onFocus(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.focus.push`

<details><summary>Code</summary>

```typescript
onFocus( callback ) {

		this.events.focus.push( callback );

		return this;

	}
```
</details>

### `Node.onBlur(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.blur.push`

<details><summary>Code</summary>

```typescript
onBlur( callback ) {

		this.events.blur.push( callback );

		return this;

	}
```
</details>

### `Node.setStyle(style: any): this`

**Parameters:**

- **`style`** `any`

**Returns:** `this`

**Calls:**

- `dom.classList.remove`
- `dom.classList.add`

<details><summary>Code</summary>

```typescript
setStyle( style ) {

		const dom = this.dom;

		if ( this.style ) dom.classList.remove( this.style );

		if ( style ) dom.classList.add( style );

		this.style = style;

		return this;

	}
```
</details>

### `Node.setPosition(x: any, y: any): this`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `this`

**Calls:**

- `numberToPX`

<details><summary>Code</summary>

```typescript
setPosition( x, y ) {

		const dom = this.dom;

		dom.style.left = numberToPX( x );
		dom.style.top = numberToPX( y );

		return this;

	}
```
</details>

### `Node.getPosition(): { x: number; y: number; }`

**Returns:** `{ x: number; y: number; }`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
getPosition() {

		const dom = this.dom;

		return {
			x: parseInt( dom.style.left ),
			y: parseInt( dom.style.top )
		};

	}
```
</details>

### `Node.setWidth(val: any): this`

**Parameters:**

- **`val`** `any`

**Returns:** `this`

**Calls:**

- `numberToPX`
- `this.updateSize`

<details><summary>Code</summary>

```typescript
setWidth( val ) {

		this.dom.style.width = numberToPX( val );

		this.updateSize();

		return this;

	}
```
</details>

### `Node.getWidth(): number`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
getWidth() {

		return parseInt( this.dom.style.width );

	}
```
</details>

### `Node.getHeight(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getHeight() {

		return this.dom.offsetHeight;

	}
```
</details>

### `Node.getBound(): { x: number; y: number; width: number; height: number; }`

**Returns:** `{ x: number; y: number; width: number; height: number; }`

**Calls:**

- `this.getPosition`
- `this.dom.getBoundingClientRect`

<details><summary>Code</summary>

```typescript
getBound() {

		const { x, y } = this.getPosition();
		const { width, height } = this.dom.getBoundingClientRect();

		return { x, y, width, height };

	}
```
</details>

### `Node.add(element: any): this`

**Parameters:**

- **`element`** `any`

**Returns:** `this`

**Calls:**

- `this.elements.push`
- `element.addEventListener`
- `this.dom.append`
- `this.updateSize`

<details><summary>Code</summary>

```typescript
add( element ) {

		this.elements.push( element );

		element.node = this;
		element.addEventListener( 'connect', this._onConnect );
		element.addEventListener( 'connectChildren', this._onConnectChildren );

		this.dom.append( element.dom );

		this.updateSize();

		return this;

	}
```
</details>

### `Node.remove(element: any): this`

**Parameters:**

- **`element`** `any`

**Returns:** `this`

**Calls:**

- `this.elements.splice`
- `this.elements.indexOf`
- `element.removeEventListener`
- `this.dom.removeChild`
- `this.updateSize`

<details><summary>Code</summary>

```typescript
remove( element ) {

		this.elements.splice( this.elements.indexOf( element ), 1 );

		element.node = null;
		element.removeEventListener( 'connect', this._onConnect );
		element.removeEventListener( 'connectChildren', this._onConnectChildren );

		this.dom.removeChild( element.dom );

		this.updateSize();

		return this;

	}
```
</details>

### `Node.dispose(): void`

**Returns:** `void`

**Calls:**

- `canvas.remove`
- `element.dispose`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
dispose() {

		const canvas = this.canvas;

		if ( canvas !== null ) canvas.remove( this );

		for ( const element of this.elements ) {

			element.dispose();

		}

		this.dispatchEvent( new Event( 'dispose' ) );

	}
```
</details>

### `Node.isCircular(node: any): boolean`

**Parameters:**

- **`node`** `any`

**Returns:** `boolean`

**Calls:**

- `this.getLinks`
- `link.outputElement.node.isCircular`

<details><summary>Code</summary>

```typescript
isCircular( node ) {

		if ( node === this ) return true;

		const links = this.getLinks();

		for ( const link of links ) {

			if ( link.outputElement.node.isCircular( node ) ) {

				return true;

			}

		}

		return false;

	}
```
</details>

### `Node.getLinks(): any[]`

**Returns:** `any[]`

**Calls:**

- `links.push`

<details><summary>Code</summary>

```typescript
getLinks() {

		const links = [];

		for ( const element of this.elements ) {

			links.push( ...element.links );

		}

		return links;

	}
```
</details>

### `Node.getColor(): any`

**Returns:** `any`

**Calls:**

- `this.elements[ 0 ].getColor`

<details><summary>Code</summary>

```typescript
getColor() {

		return this.elements.length > 0 ? this.elements[ 0 ].getColor() : null;

	}
```
</details>

### `Node.updateSize(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateSize() {

		for ( const element of this.elements ) {

			element.dom.style.width = '';

		}

		if ( this.resizable === true ) {

			const element = this.elements[ this.elements.length - 1 ];

			if ( element !== undefined ) {

				element.dom.style.width = this.dom.style.width;

			}

		}

	}
```
</details>

### `Node.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.getPosition`
- `elements.push`
- `element.toJSON`
- `this.getWidth`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		const { x, y } = this.getPosition();

		const elements = [];

		for ( const element of this.elements ) {

			elements.push( element.toJSON( data ).id );

		}

		data.x = x;
		data.y = y;
		data.width = this.getWidth();
		data.elements = elements;
		data.autoResize = this.resizable;

		if ( this.style !== '' ) {

			data.style = this.style;

		}

	}
```
</details>

### `Node.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.setPosition`
- `this.setWidth`
- `this.setResizable`
- `this.setStyle`
- `this.add`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		this.setPosition( data.x, data.y );
		this.setWidth( data.width );
		this.setResizable( data.autoResize );

		if ( data.style !== undefined ) {

			this.setStyle( data.style );

		}

		const elements = this.elements;

		if ( elements.length > 0 ) {

			let index = 0;

			for ( const id of data.elements ) {

				data.objects[ id ] = elements[ index ++ ];

			}

		} else {

			for ( const id of data.elements ) {

				this.add( data.objects[ id ] );

			}

		}

	}
```
</details>

### `onDown(): void`

**Returns:** `void`

**Calls:**

- `canvas.select`

<details><summary>Code</summary>

```typescript
() => {

			const canvas = this.canvas;

			if ( canvas !== null ) {

				canvas.select( this );

			}

		}
```
</details>

### `onDrag(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.preventDefault`
- `draggableDOM`

<details><summary>Code</summary>

```typescript
( e ) => {

			e.preventDefault();

			if ( this.draggable === true ) {

				draggableDOM( this.node.dom, null, { className: 'dragging node' } );

			}

		}
```
</details>

### `TitleElement.setIcon(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setIcon( value ) {

		this.iconDOM.className = value;

		return this;

	}
```
</details>

### `TitleElement.getIcon(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getIcon() {

		return this.iconDOM.className;

	}
```
</details>

### `TitleElement.setTitle(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setTitle( value ) {

		this.titleDOM.innerText = value;

		return this;

	}
```
</details>

### `TitleElement.getTitle(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getTitle() {

		return this.titleDOM.innerText;

	}
```
</details>

### `TitleElement.addButton(button: any): this`

**Parameters:**

- **`button`** `any`

**Returns:** `this`

**Calls:**

- `this.buttons.push`
- `this.toolbarDOM.append`

<details><summary>Code</summary>

```typescript
addButton( button ) {

		this.buttons.push( button );

		this.toolbarDOM.append( button.dom );

		return this;

	}
```
</details>

### `TitleElement.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`
- `this.getTitle`
- `this.getIcon`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		const title = this.getTitle();
		const icon = this.getIcon();

		data.title = title;

		if ( icon !== '' ) {

			data.icon = icon;

		}

	}
```
</details>

### `TitleElement.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`
- `this.setTitle`
- `this.setIcon`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.setTitle( data.title );

		if ( data.icon !== undefined ) {

			this.setIcon( data.icon );

		}

	}
```
</details>

### `dbClick(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {

			this.node.canvas.focusSelected = ! this.node.canvas.focusSelected;

		}
```
</details>

### `drawLine(p1x: any, p1y: any, p2x: any, p2y: any, invert: any, size: any, colorA: any, ctx: any, colorB: any): void`

**Parameters:**

- **`p1x`** `any`
- **`p1y`** `any`
- **`p2x`** `any`
- **`p2y`** `any`
- **`invert`** `any`
- **`size`** `any`
- **`colorA`** `any`
- **`ctx`** `any`
- **`colorB`** `any`

**Returns:** `void`

**Calls:**

- `Math.sqrt`
- `ctx.beginPath`
- `ctx.moveTo`
- `ctx.bezierCurveTo`
- `ctx.createLinearGradient`
- `gradient.addColorStop`
- `ctx.stroke`

<details><summary>Code</summary>

```typescript
( p1x, p1y, p2x, p2y, invert, size, colorA, ctx, colorB = null ) => {

	const dx = p2x - p1x;
	const dy = p2y - p1y;
	const offset = Math.sqrt( ( dx * dx ) + ( dy * dy ) ) * ( invert ? - .3 : .3 );

	ctx.beginPath();

	ctx.moveTo( p1x, p1y );

	ctx.bezierCurveTo(
		p1x + offset, p1y,
		p2x - offset, p2y,
		p2x, p2y
	);

	if ( colorB !== null && colorA !== colorB ) {

		const gradient = ctx.createLinearGradient( p1x, p1y, p2x, p2y );
		gradient.addColorStop( 0, colorA );
		gradient.addColorStop( 1, colorB );

		ctx.strokeStyle = gradient;

	} else {

		ctx.strokeStyle = colorA;

	}

	ctx.lineWidth = size;
	ctx.stroke();

}
```
</details>

### `Canvas.getBounds(): { x: number; y: number; width: number; height: number; }`

**Returns:** `{ x: number; y: number; width: number; height: number; }`

**Calls:**

- `node.getBound`
- `Math.min`
- `Math.max`
- `Math.round`

<details><summary>Code</summary>

```typescript
getBounds() {

		const bounds = { x: Infinity, y: Infinity, width: - Infinity, height: - Infinity };

		for ( const node of this.nodes ) {

			const { x, y, width, height } = node.getBound();

			bounds.x = Math.min( bounds.x, x );
			bounds.y = Math.min( bounds.y, y );
			bounds.width = Math.max( bounds.width, x + width );
			bounds.height = Math.max( bounds.height, y + height );

		}

		bounds.x = Math.round( bounds.x );
		bounds.y = Math.round( bounds.y );
		bounds.width = Math.round( bounds.width );
		bounds.height = Math.round( bounds.height );

		return bounds;

	}
```
</details>

### `Canvas.updateMozTransform(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateMozTransform() {

		if ( this.useTransform === false ) return;

		this.contentDOM.style[ '-moz-transform' ] = 'scale(' + this.zoom + ')';
		this.contentDOM.style[ '-moz-transform-origin' ] = '-' + this.contentDOM.style.left + ' -' + this.contentDOM.style.top;

	}
```
</details>

### `Canvas.onDrop(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.drop.push`

<details><summary>Code</summary>

```typescript
onDrop( callback ) {

		this.events.drop.push( callback );

		return this;

	}
```
</details>

### `Canvas.start(): void`

**Returns:** `void`

**Calls:**

- `document.addEventListener`
- `requestAnimationFrame`

<details><summary>Code</summary>

```typescript
start() {

		this.updating = true;

		document.addEventListener( 'wheel', this._onMoveEvent, true );

		document.addEventListener( 'mousedown', this._onMoveEvent, true );
		document.addEventListener( 'touchstart', this._onMoveEvent, true );

		document.addEventListener( 'mousemove', this._onMoveEvent, true );
		document.addEventListener( 'touchmove', this._onMoveEvent, true );

		document.addEventListener( 'dragover', this._onMoveEvent, true );

		requestAnimationFrame( this._onUpdate );

	}
```
</details>

### `Canvas.stop(): void`

**Returns:** `void`

**Calls:**

- `document.removeEventListener`

<details><summary>Code</summary>

```typescript
stop() {

		this.updating = false;

		document.removeEventListener( 'wheel', this._onMoveEvent, true );

		document.removeEventListener( 'mousedown', this._onMoveEvent, true );
		document.removeEventListener( 'touchstart', this._onMoveEvent, true );

		document.removeEventListener( 'mousemove', this._onMoveEvent, true );
		document.removeEventListener( 'touchmove', this._onMoveEvent, true );

		document.removeEventListener( 'dragover', this._onMoveEvent, true );

	}
```
</details>

### `Canvas.add(node: any): this`

**Parameters:**

- **`node`** `any`

**Returns:** `this`

**Calls:**

- `this.nodes.push`
- `this.contentDOM.append`

<details><summary>Code</summary>

```typescript
add( node ) {

		if ( node.canvas === this ) return;

		this.nodes.push( node );

		node.canvas = this;

		this.contentDOM.append( node.dom );

		return this;

	}
```
</details>

### `Canvas.remove(node: any): this`

**Parameters:**

- **`node`** `any`

**Returns:** `this`

**Calls:**

- `this.select`
- `this.unlink`
- `nodes.splice`
- `nodes.indexOf`
- `this.contentDOM.removeChild`
- `node.dispatchEvent`

<details><summary>Code</summary>

```typescript
remove( node ) {

		if ( node === this.selected ) {

			this.select();

		}

		this.unlink( node );

		const nodes = this.nodes;

		nodes.splice( nodes.indexOf( node ), 1 );

		node.canvas = null;

		this.contentDOM.removeChild( node.dom );

		node.dispatchEvent( new Event( 'remove' ) );

		return this;

	}
```
</details>

### `Canvas.clear(): this`

**Returns:** `this`

**Calls:**

- `this.remove`

<details><summary>Code</summary>

```typescript
clear() {

		const nodes = this.nodes;

		while ( nodes.length > 0 ) {

			this.remove( nodes[ 0 ] );

		}

		return this;

	}
```
</details>

### `Canvas.unlink(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.getLinks`
- `link.inputElement.connect`

<details><summary>Code</summary>

```typescript
unlink( node ) {

		const links = this.getLinks();

		for ( const link of links ) {

			if ( link.inputElement && link.outputElement ) {

				if ( link.inputElement.node === node ) {

					link.inputElement.connect();

				} else if ( link.outputElement.node === node ) {

					link.inputElement.connect();

				}

			}

		}

	}
```
</details>

### `Canvas.getLinks(): any[]`

**Returns:** `any[]`

**Calls:**

- `links.push`
- `node.getLinks`

<details><summary>Code</summary>

```typescript
getLinks() {

		const links = [];

		for ( const node of this.nodes ) {

			links.push( ...node.getLinks() );

		}

		return links;

	}
```
</details>

### `Canvas.centralize(): this`

**Returns:** `this`

**Calls:**

- `this.getBounds`

<details><summary>Code</summary>

```typescript
centralize() {

		const bounds = this.getBounds();

		this.scrollLeft = ( this.canvas.width / 2 ) - ( ( - bounds.x + bounds.width ) / 2 );
		this.scrollTop = ( this.canvas.height / 2 ) - ( ( - bounds.y + bounds.height ) / 2 );

		return this;

	}
```
</details>

### `Canvas.setSize(width: any, height: any): this`

**Parameters:**

- **`width`** `any`
- **`height`** `any`

**Returns:** `this`

**Calls:**

- `this.update`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._width = width;
		this._height = height;

		this.update();

		return this;

	}
```
</details>

### `Canvas.select(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `previousNode.dom.classList.remove`
- `dispatchEventList`
- `node.dom.classList.add`

<details><summary>Code</summary>

```typescript
select( node = null ) {

		if ( node === this.selected ) return;

		const previousNode = this.selected;

		if ( previousNode !== null ) {

			this.focusSelected = false;

			previousNode.dom.classList.remove( 'selected' );

			this.selected = null;

			dispatchEventList( previousNode.events.blur, previousNode );

		}

		if ( node !== null ) {

			node.dom.classList.add( 'selected' );

			this.selected = node;

			dispatchEventList( node.events.focus, node );

		}

	}
```
</details>

### `Canvas.updateMap(): void`

**Returns:** `void`

**Calls:**

- `this.getBounds`
- `mapContext.clearRect`
- `mapContext.fillRect`
- `Math.min`
- `node.getBound`
- `node.getColor`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
updateMap() {

		const { nodes, mapCanvas, mapContext, scrollLeft, scrollTop, canvas, zoom, _mapInfo } = this;

		const bounds = this.getBounds();

		mapCanvas.width = 300;
		mapCanvas.height = 200;

		mapContext.clearRect( 0, 0, mapCanvas.width, mapCanvas.height );

		mapContext.fillStyle = 'rgba( 0, 0, 0, 0 )';
		mapContext.fillRect( 0, 0, mapCanvas.width, mapCanvas.height );

		const boundsWidth = - bounds.x + bounds.width;
		const boundsHeight = - bounds.y + bounds.height;

		const mapScale = Math.min( mapCanvas.width / boundsWidth, mapCanvas.height / boundsHeight ) * .5;

		const boundsMapWidth = boundsWidth * mapScale;
		const boundsMapHeight = boundsHeight * mapScale;

		const boundsOffsetX = ( mapCanvas.width / 2 ) - ( boundsMapWidth / 2 );
		const boundsOffsetY = ( mapCanvas.height / 2 ) - ( boundsMapHeight / 2 );

		let selectedNode = null;

		for ( const node of nodes ) {

			const nodeBound = node.getBound();
			const nodeColor = node.getColor();

			nodeBound.x += - bounds.x;
			nodeBound.y += - bounds.y;

			nodeBound.x *= mapScale;
			nodeBound.y *= mapScale;
			nodeBound.width *= mapScale;
			nodeBound.height *= mapScale;

			nodeBound.x += boundsOffsetX;
			nodeBound.y += boundsOffsetY;

			if ( node !== this.selected ) {

				mapContext.fillStyle = nodeColor;
				mapContext.fillRect( nodeBound.x, nodeBound.y, nodeBound.width, nodeBound.height );

			} else {

				selectedNode = {
					nodeBound,
					nodeColor
				};

			}

		}

		if ( selectedNode !== null ) {

			const { nodeBound, nodeColor } = selectedNode;

			mapContext.fillStyle = nodeColor;
			mapContext.fillRect( nodeBound.x, nodeBound.y, nodeBound.width, nodeBound.height );

		}

		const screenMapX = ( - ( scrollLeft + bounds.x ) * mapScale ) + boundsOffsetX;
		const screenMapY = ( - ( scrollTop + bounds.y ) * mapScale ) + boundsOffsetY;
		const screenMapWidth = ( canvas.width * mapScale ) / zoom;
		const screenMapHeight = ( canvas.height * mapScale ) / zoom;

		mapContext.fillStyle = 'rgba( 200, 200, 200, 0.1 )';
		mapContext.fillRect( screenMapX, screenMapY, screenMapWidth, screenMapHeight );

		//

		_mapInfo.scale = mapScale;
		_mapInfo.left = ( - boundsOffsetX / mapScale ) + bounds.x;
		_mapInfo.top = ( - boundsOffsetY / mapScale ) + bounds.y;
		_mapInfo.width = mapCanvas.width / mapScale;
		_mapInfo.height = mapCanvas.height / mapScale;
		_mapInfo.screen.x = screenMapX;
		_mapInfo.screen.y = screenMapY;
		_mapInfo.screen.width = screenMapWidth;
		_mapInfo.screen.height = screenMapHeight;

	}
```
</details>

### `Canvas.updateLines(): void`

**Returns:** `void`

**Calls:**

- `context.clearRect`
- `frontContext.clearRect`
- `this.getLinks`
- `lioElement.dom.getBoundingClientRect`
- `Math.max`
- `rioElement.dom.getBoundingClientRect`
- `lioElement.getRIOColor`
- `rioElement.getLIOColor`
- `drawLine`
- `Math.min`
- `context.fillRect`
- `dom.classList.add`
- `dom.classList.remove`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
updateLines() {

		const { dom, zoom, canvas, frontCanvas, frontContext, context, _width, _height, useTransform } = this;

		const domRect = this.rect;

		if ( canvas.width !== _width || canvas.height !== _height ) {

			canvas.width = _width;
			canvas.height = _height;

			frontCanvas.width = _width;
			frontCanvas.height = _height;

		}

		context.clearRect( 0, 0, _width, _height );
		frontContext.clearRect( 0, 0, _width, _height );

		//

		context.globalCompositeOperation = 'lighter';
		frontContext.globalCompositeOperation = 'source-over';

		const links = this.getLinks();

		const aPos = { x: 0, y: 0 };
		const bPos = { x: 0, y: 0 };

		const offsetIORadius = 10;

		let dragging = '';

		for ( const link of links ) {

			const { lioElement, rioElement } = link;

			let draggingLink = '';
			let length = 0;

			if ( lioElement !== null ) {

				const rect = lioElement.dom.getBoundingClientRect();

				length = Math.max( length, lioElement.rioLength );

				aPos.x = rect.x + rect.width;
				aPos.y = rect.y + ( rect.height / 2 );

				if ( useTransform ) {

					aPos.x /= zoom;
					aPos.y /= zoom;

				}

			} else {

				aPos.x = this.clientX;
				aPos.y = this.clientY;

				draggingLink = 'lio';

			}

			if ( rioElement !== null ) {

				const rect = rioElement.dom.getBoundingClientRect();

				length = Math.max( length, rioElement.lioLength );

				bPos.x = rect.x;
				bPos.y = rect.y + ( rect.height / 2 );

				if ( useTransform ) {

					bPos.x /= zoom;
					bPos.y /= zoom;

				}

			} else {

				bPos.x = this.clientX;
				bPos.y = this.clientY;

				draggingLink = 'rio';

			}

			dragging = dragging || draggingLink;

			const drawContext = draggingLink ? frontContext : context;

			if ( draggingLink || length === 1 ) {

				let colorA = null,
					colorB = null;

				if ( draggingLink === 'rio' ) {

					colorA = colorB = lioElement.getRIOColor();

					aPos.x += offsetIORadius;
					bPos.x /= zoom;
					bPos.y /= zoom;

				} else if ( draggingLink === 'lio' ) {

					colorA = colorB = rioElement.getLIOColor();

					bPos.x -= offsetIORadius;
					aPos.x /= zoom;
					aPos.y /= zoom;

				} else {

					colorA = lioElement.getRIOColor();
					colorB = rioElement.getLIOColor();

				}

				drawLine(
					aPos.x * zoom, aPos.y * zoom,
					bPos.x * zoom, bPos.y * zoom,
					false, 2, colorA || '#ffffff', drawContext, colorB || '#ffffff'
				);

			} else {

				length = Math.min( length, 4 );

				for ( let i = 0; i < length; i ++ ) {

					const color = colors[ i ] || '#ffffff';

					const marginY = 4;

					const rioLength = Math.min( lioElement.rioLength, length );
					const lioLength = Math.min( rioElement.lioLength, length );

					const colorA = lioElement.getRIOColor() || color;
					const colorB = rioElement.getLIOColor() || color;

					const aCenterY = ( ( rioLength * marginY ) * .5 ) - ( marginY / 2 );
					const bCenterY = ( ( lioLength * marginY ) * .5 ) - ( marginY / 2 );

					const aIndex = Math.min( i, rioLength - 1 );
					const bIndex = Math.min( i, lioLength - 1 );

					const aPosY = ( aIndex * marginY ) - 1;
					const bPosY = ( bIndex * marginY ) - 1;

					drawLine(
						aPos.x * zoom, ( ( aPos.y + aPosY ) - aCenterY ) * zoom,
						bPos.x * zoom, ( ( bPos.y + bPosY ) - bCenterY ) * zoom,
						false, 2, colorA, drawContext, colorB
					);

				}

			}

		}

		context.globalCompositeOperation = 'destination-in';

		context.fillRect( domRect.x, domRect.y, domRect.width, domRect.height );

		if ( dragging !== '' ) {

			dom.classList.add( 'dragging-' + dragging );

		} else {

			dom.classList.remove( 'dragging-lio' );
			dom.classList.remove( 'dragging-rio' );

		}

	}
```
</details>

### `Canvas.update(): void`

**Returns:** `void`

**Calls:**

- `requestAnimationFrame`
- `this.updateLines`
- `this.updateMap`

<details><summary>Code</summary>

```typescript
update() {

		if ( this.updating === false ) return;

		requestAnimationFrame( this._onUpdate );

		this.updateLines();
		this.updateMap();

	}
```
</details>

### `Canvas.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.nodes.sort`
- `nodes.push`
- `node.toJSON`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		const nodes = [];
		const serializeNodes = this.nodes.sort( ( a, b ) => a.serializePriority > b.serializePriority ? - 1 : 1 );

		for ( const node of serializeNodes ) {

			nodes.push( node.toJSON( data ).id );

		}

		data.nodes = nodes;

	}
```
</details>

### `Canvas.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.add`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		for ( const id of data.nodes ) {

			this.add( data.objects[ id ] );

		}

	}
```
</details>

### `zoomTo(zoom: any, clientX: number, clientY: number): void`

**Parameters:**

- **`zoom`** `any`
- **`clientX`** `number`
- **`clientY`** `number`

**Returns:** `void`

**Calls:**

- `Math.min`
- `Math.max`

<details><summary>Code</summary>

```typescript
( zoom, clientX = this.clientX, clientY = this.clientY ) => {

			zoom = Math.min( Math.max( zoom, .2 ), 1 );

			this.scrollLeft -= ( clientX / this.zoom ) - ( clientX / zoom );
			this.scrollTop -= ( clientY / this.zoom ) - ( clientY / zoom );
			this.zoom = zoom;

		}
```
</details>

### `onTouchStart(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {

			touchData = null;

		}
```
</details>

### `classInElements(element: any, className: any): boolean`

**Parameters:**

- **`element`** `any`
- **`className`** `any`

**Returns:** `boolean`

**Calls:**

- `element.classList.contains`

<details><summary>Code</summary>

```typescript
( element, className ) => {

			do {

				if ( element.classList ? element.classList.contains( className ) : false ) {

					return true;

				}

			} while ( ( element = element.parentElement ) && element !== dom );

			return false;

		}
```
</details>

### `onMouseZoom(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `classInElements`
- `e.preventDefault`
- `e.stopImmediatePropagation`
- `zoomTo`

<details><summary>Code</summary>

```typescript
( e ) => {

			if ( classInElements( e.srcElement, 'f-scroll' ) ) return;

			e.preventDefault();

			e.stopImmediatePropagation();

			const delta = e.deltaY * .003;

			zoomTo( this.zoom - delta );

		}
```
</details>

### `onTouchZoom(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.preventDefault`
- `e.stopImmediatePropagation`
- `Math.hypot`
- `zoomTo`

<details><summary>Code</summary>

```typescript
( e ) => {

			if ( e.touches && e.touches.length === 2 ) {

				e.preventDefault();

				e.stopImmediatePropagation();

				const clientX = ( e.touches[ 0 ].clientX + e.touches[ 1 ].clientX ) / 2;
				const clientY = ( e.touches[ 0 ].clientY + e.touches[ 1 ].clientY ) / 2;

				const distance = Math.hypot(
					e.touches[ 0 ].clientX - e.touches[ 1 ].clientX,
					e.touches[ 0 ].clientY - e.touches[ 1 ].clientY
				);

				if ( touchData === null ) {

					touchData = {
						distance
					};

				}

				const delta = ( touchData.distance - distance ) * .003;
				touchData.distance = distance;

				zoomTo( this.zoom - delta, clientX, clientY );

			}

		}
```
</details>

### `onTouchMove(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.preventDefault`
- `e.stopImmediatePropagation`

<details><summary>Code</summary>

```typescript
( e ) => {

			if ( e.touches && e.touches.length === 1 ) {

				e.preventDefault();

				e.stopImmediatePropagation();

				const clientX = e.touches[ 0 ].clientX;
				const clientY = e.touches[ 0 ].clientY;

				if ( touchData === null ) {

					const { scrollLeft, scrollTop } = this;

					touchData = {
						scrollLeft,
						scrollTop,
						clientX,
						clientY
					};

				}

				const zoom = this.zoom;

				this.scrollLeft = touchData.scrollLeft + ( ( clientX - touchData.clientX ) / zoom );
				this.scrollTop = touchData.scrollTop + ( ( clientY - touchData.clientY ) / zoom );

			}

		}
```
</details>

### `dragState(enter: any): void`

**Parameters:**

- **`enter`** `any`

**Returns:** `void`

**Calls:**

- `dropDOM.classList.add`
- `this.add`
- `dropDOM.classList.remove`
- `this.remove`

<details><summary>Code</summary>

```typescript
( enter ) => {

			if ( enter ) {

				if ( dropEnterCount ++ === 0 ) {

					this.droppedItems = [];

					dropDOM.classList.add( 'visible' );

					this.add( dropNode );

				}

			} else if ( -- dropEnterCount === 0 ) {

				dropDOM.classList.remove( 'visible' );

				this.remove( dropNode );

			}

		}
```
</details>

### `Menu.onContext(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.context.push`

<details><summary>Code</summary>

```typescript
onContext( callback ) {

		this.events.context.push( callback );

		return this;

	}
```
</details>

### `Menu.setAlign(align: any): this`

**Parameters:**

- **`align`** `any`

**Returns:** `this`

**Calls:**

- `removeDOMClass`
- `addDOMClass`

<details><summary>Code</summary>

```typescript
setAlign( align ) {

		const dom = this.dom;

		removeDOMClass( dom, this.align );
		addDOMClass( dom, align );

		this.align = align;

		return this;

	}
```
</details>

### `Menu.getAlign(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getAlign() {

		return this.align;

	}
```
</details>

### `Menu.show(): this`

**Returns:** `this`

**Calls:**

- `this.dom.classList.remove`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
show() {

		this.dom.classList.remove( 'hidden' );

		this.visible = true;

		this.dispatchEvent( new Event( 'show' ) );

		return this;

	}
```
</details>

### `Menu.hide(): void`

**Returns:** `void`

**Calls:**

- `this.dom.classList.add`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
hide() {

		this.dom.classList.add( 'hidden' );

		this.dispatchEvent( new Event( 'hide' ) );

		this.visible = false;

	}
```
</details>

### `Menu.add(button: any, submenu: any): this`

**Parameters:**

- **`button`** `any`
- **`submenu`** `any`

**Returns:** `this`

**Calls:**

- `document.createElement`
- `liDOM.classList.add`
- `liDOM.append`
- `this.subMenus.set`
- `button.dom.addEventListener`
- `submenu.show`
- `submenu.hide`
- `this.buttons.push`
- `this.listDOM.append`
- `this.domButtons.set`

<details><summary>Code</summary>

```typescript
add( button, submenu = null ) {

		const liDOM = document.createElement( 'f-item' );

		if ( submenu !== null ) {

			liDOM.classList.add( 'submenu' );

			liDOM.append( submenu.dom );

			this.subMenus.set( button, submenu );

			button.dom.addEventListener( 'mouseover', () => submenu.show() );
			button.dom.addEventListener( 'mouseout', () => submenu.hide() );

		}

		liDOM.append( button.dom );

		this.buttons.push( button );

		this.listDOM.append( liDOM );

		this.domButtons.set( button, liDOM );

		return this;

	}
```
</details>

### `Menu.clear(): void`

**Returns:** `void`

**Calls:**

- `this.listDOM.firstChild.remove`

<details><summary>Code</summary>

```typescript
clear() {

		this.buttons = [];

		this.subMenus = new WeakMap();
		this.domButtons = new WeakMap();

		while ( this.listDOM.firstChild ) {

			this.listDOM.firstChild.remove();

		}

	}
```
</details>

### `onCloseLastContext(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.target.closest`
- `lastContext.hide`

<details><summary>Code</summary>

```typescript
( e ) => {

	if ( lastContext && lastContext.visible === true && e.target.closest( 'f-menu.context' ) === null ) {

		lastContext.hide();

	}

}
```
</details>

### `ContextMenu.openFrom(dom: any): this`

**Parameters:**

- **`dom`** `any`

**Returns:** `this`

**Calls:**

- `dom.getBoundingClientRect`
- `this.open`

<details><summary>Code</summary>

```typescript
openFrom( dom ) {

		const rect = dom.getBoundingClientRect();

		return this.open( rect.x + ( rect.width / 2 ), rect.y + ( rect.height / 2 ) );

	}
```
</details>

### `ContextMenu.open(x: number, y: number): this`

**Parameters:**

- **`x`** `number`
- **`y`** `number`

**Returns:** `this`

**Calls:**

- `lastContext.hide`
- `this.setPosition`
- `document.body.append`
- `this.show`

<details><summary>Code</summary>

```typescript
open( x = pointer.x, y = pointer.y ) {

		if ( lastContext !== null ) {

			lastContext.hide();

		}

		lastContext = this;

		this.setPosition( x, y );

		document.body.append( this.dom );

		return this.show();

	}
```
</details>

### `ContextMenu.setWidth(width: any): this`

**Parameters:**

- **`width`** `any`

**Returns:** `this`

**Calls:**

- `numberToPX`

<details><summary>Code</summary>

```typescript
setWidth( width ) {

		this.dom.style.width = numberToPX( width );

		return this;

	}
```
</details>

### `ContextMenu.setPosition(x: any, y: any): this`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `this`

**Calls:**

- `numberToPX`

<details><summary>Code</summary>

```typescript
setPosition( x, y ) {

		const dom = this.dom;

		dom.style.left = numberToPX( x );
		dom.style.top = numberToPX( y );

		return this;

	}
```
</details>

### `ContextMenu.setTarget(target: any): this`

**Parameters:**

- **`target`** `any`

**Returns:** `this`

**Calls:**

- `e.preventDefault`
- `this.dispatchEvent`
- `this.open`
- `target.addEventListener`

<details><summary>Code</summary>

```typescript
setTarget( target = null ) {

		if ( target !== null ) {

			const onContextMenu = ( e ) => {

				e.preventDefault();

				if ( e.pointerType !== 'mouse' || ( e.pageX === 0 && e.pageY === 0 ) ) return;

				this.dispatchEvent( new Event( 'context' ) );

				this.open();

			};

			this.target = target;

			target.addEventListener( 'contextmenu', onContextMenu, false );

		}

		return this;

	}
```
</details>

### `ContextMenu.show(): this`

**Returns:** `this`

**Calls:**

- `this.dom.getBoundingClientRect`
- `Math.min`
- `this.setPosition`
- `super.show`

**Internal Comments:**
```
// flip submenus
```

<details><summary>Code</summary>

```typescript
show() {

		if ( ! this.opened ) {

			this.dom.style.left = '';
			this.dom.style.transform = '';

		}

		const domRect = this.dom.getBoundingClientRect();

		let offsetX = Math.min( window.innerWidth - ( domRect.x + domRect.width + 10 ), 0 );
		let offsetY = Math.min( window.innerHeight - ( domRect.y + domRect.height + 10 ), 0 );

		if ( this.opened ) {

			if ( offsetX < 0 ) offsetX = - domRect.width;
			if ( offsetY < 0 ) offsetY = - domRect.height;

			this.setPosition( domRect.x + offsetX, domRect.y + offsetY );

		} else {

			// flip submenus

			if ( offsetX < 0 ) this.dom.style.left = '-100%';
			if ( offsetY < 0 ) this.dom.style.transform = 'translateY( calc( 32px - 100% ) )';

		}

		return super.show();

	}
```
</details>

### `ContextMenu.hide(): void`

**Returns:** `void`

**Calls:**

- `super.hide`

<details><summary>Code</summary>

```typescript
hide() {

		if ( this.opened ) {

			lastContext = null;

		}

		return super.hide();

	}
```
</details>

### `ContextMenu.add(button: any, submenu: any): this`

**Parameters:**

- **`button`** `any`
- **`submenu`** `any`

**Returns:** `this`

**Calls:**

- `button.addEventListener`
- `super.add`

<details><summary>Code</summary>

```typescript
add( button, submenu = null ) {

		button.addEventListener( 'click', this._onButtonClick );
		button.addEventListener( 'mouseover', this._onButtonMouseOver );

		return super.add( button, submenu );

	}
```
</details>

### `onContextMenu(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.preventDefault`
- `this.dispatchEvent`
- `this.open`

<details><summary>Code</summary>

```typescript
( e ) => {

				e.preventDefault();

				if ( e.pointerType !== 'mouse' || ( e.pageX === 0 && e.pageY === 0 ) ) return;

				this.dispatchEvent( new Event( 'context' ) );

				this.open();

			}
```
</details>

### `Tips.message(str: any): this`

**Parameters:**

- **`str`** `any`

**Returns:** `this`

**Calls:**

- `this.tip`

<details><summary>Code</summary>

```typescript
message( str ) {

		return this.tip( str );

	}
```
</details>

### `Tips.error(str: any): this`

**Parameters:**

- **`str`** `any`

**Returns:** `this`

**Calls:**

- `this.tip`

<details><summary>Code</summary>

```typescript
error( str ) {

		return this.tip( str, 'error' );

	}
```
</details>

### `Tips.tip(html: any, className: string): this`

**Parameters:**

- **`html`** `any`
- **`className`** `string`

**Returns:** `this`

**Calls:**

- `document.createElement`
- `this.dom.prepend`
- `Math.min`
- `setTimeout`
- `Math.max`
- `dom.remove`

**Internal Comments:**
```
//requestAnimationFrame( () => dom.style.opacity = 1 ); (x4)
```

<details><summary>Code</summary>

```typescript
tip( html, className = '' ) {

		const dom = document.createElement( 'f-tip' );
		dom.className = className;
		dom.innerHTML = html;

		this.dom.prepend( dom );

		//requestAnimationFrame( () => dom.style.opacity = 1 );

		this.time = Math.min( this.time + this.duration, this.duration );

		setTimeout( () => {

			this.time = Math.max( this.time - this.duration, 0 );

			dom.style.opacity = 0;

			setTimeout( () => dom.remove(), 250 );

		}, this.time );

		return this;

	}
```
</details>

### `filterString(str: any): any`

**Parameters:**

- **`str`** `any`

**Returns:** `any`

**Calls:**

- `str.trim().toLowerCase().replace`

<details><summary>Code</summary>

```typescript
( str ) => {

	return str.trim().toLowerCase().replace( /\s\s+/g, ' ' );

}
```
</details>

### `Search.submit(): this`

**Returns:** `this`

**Calls:**

- `this.dispatchEvent`
- `this.setValue`

<details><summary>Code</summary>

```typescript
submit() {

		this.dispatchEvent( new Event( 'submit' ) );

		return this.setValue( '' );

	}
```
</details>

### `Search.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `this.filter`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		this.inputDOM.value = value;

		this.filter( value );

		return this;

	}
```
</details>

### `Search.getValue(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.value;

	}
```
</details>

### `Search.onFilter(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.filter.push`

<details><summary>Code</summary>

```typescript
onFilter( callback ) {

		this.events.filter.push( callback );

		return this;

	}
```
</details>

### `Search.onSubmit(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.submit.push`

<details><summary>Code</summary>

```typescript
onSubmit( callback ) {

		this.events.submit.push( callback );

		return this;

	}
```
</details>

### `Search.getFilterByButton(button: any): any`

**Parameters:**

- **`button`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getFilterByButton( button ) {

		for ( const filter of this.filtered ) {

			if ( filter.button === button ) {

				return filter;

			}

		}

		return null;

	}
```
</details>

### `Search.add(button: any): this`

**Parameters:**

- **`button`** `any`

**Returns:** `this`

**Calls:**

- `super.add`
- `this.getFilterByButton`
- `this.filtered.indexOf`
- `button.getValue`
- `this.submit`
- `button.dom.addEventListener`
- `this.domButtons.get( button ).remove`

<details><summary>Code</summary>

```typescript
add( button ) {

		super.add( button );

		const onDown = () => {

			const filter = this.getFilterByButton( button );

			this.filteredIndex = this.filtered.indexOf( filter );
			this.value = button.getValue();

			this.submit();

		};

		button.dom.addEventListener( 'mousedown', onDown );
		button.dom.addEventListener( 'touchstart', onDown );

		this.domButtons.get( button ).remove();

		return this;

	}
```
</details>

### `Search.setTag(button: any, tags: any): void`

**Parameters:**

- **`button`** `any`
- **`tags`** `any`

**Returns:** `void`

**Calls:**

- `this.tags.set`

<details><summary>Code</summary>

```typescript
setTag( button, tags ) {

		this.tags.set( button, tags );

	}
```
</details>

### `Search.filter(text: any): void`

**Parameters:**

- **`text`** `any`

**Returns:** `void`

**Calls:**

- `filterString`
- `this.domButtons.get`
- `buttonDOM.remove`
- `tags.has`
- `tags.get`
- `button.getValue`
- `label.includes`
- `filtered.push`
- `filtered.sort`

<details><summary>Code</summary>

```typescript
filter( text ) {

		text = filterString( text );

		const tags = this.tags;
		const filtered = [];

		for ( const button of this.buttons ) {

			const buttonDOM = this.domButtons.get( button );

			buttonDOM.remove();

			const buttonTags = tags.has( button ) ? ' ' + tags.get( button ) : '';

			const label = filterString( button.getValue() + buttonTags );

			if ( text && label.includes( text ) === true ) {

				const score = text.length / label.length;

				filtered.push( {
					button,
					score
				} );

			}

		}

		filtered.sort( ( a, b ) => b.score - a.score );

		this.filtered = filtered;
		this.filteredIndex = this.forceAutoComplete ? 0 : null;

	}
```
</details>

### `Search.updateFilter(): void`

**Returns:** `void`

**Calls:**

- `Math.min`
- `this.domButtons.get`
- `buttonDOM.remove`
- `this.listDOM.append`

<details><summary>Code</summary>

```typescript
updateFilter() {

		const filteredIndex = Math.min( this.filteredIndex, this.filteredIndex - 3 );

		for ( let i = 0; i < this.filtered.length; i ++ ) {

			const button = this.filtered[ i ].button;
			const buttonDOM = this.domButtons.get( button );

			buttonDOM.remove();

			if ( i >= filteredIndex ) {

				this.listDOM.append( buttonDOM );

			}

		}

	}
```
</details>

### `onDown(): void`

**Returns:** `void`

**Calls:**

- `this.getFilterByButton`
- `this.filtered.indexOf`
- `button.getValue`
- `this.submit`

<details><summary>Code</summary>

```typescript
() => {

			const filter = this.getFilterByButton( button );

			this.filteredIndex = this.filtered.indexOf( filter );
			this.value = button.getValue();

			this.submit();

		}
```
</details>

### `LabelElement.setIcon(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `document.createElement`
- `this.labelDOM.prepend`
- `this.iconDOM.remove`

<details><summary>Code</summary>

```typescript
setIcon( value ) {

		this.iconDOM = this.iconDOM || document.createElement( 'i' );
		this.iconDOM.className = value;

		if ( value ) this.labelDOM.prepend( this.iconDOM );
		else this.iconDOM.remove();

		return this;

	}
```
</details>

### `LabelElement.getIcon(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getIcon() {

		return this.iconDOM ? this.iconDOM.className : null;

	}
```
</details>

### `LabelElement.setAlign(align: any): void`

**Parameters:**

- **`align`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setAlign( align ) {

		this.labelDOM.className = align;

	}
```
</details>

### `LabelElement.setLabel(val: any): void`

**Parameters:**

- **`val`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setLabel( val ) {

		this.spanDOM.innerText = val;

	}
```
</details>

### `LabelElement.getLabel(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getLabel() {

		return this.spanDOM.innerText;

	}
```
</details>

### `LabelElement.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`
- `this.getLabel`
- `this.getIcon`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		if ( this.serializeLabel ) {

			const label = this.getLabel();
			const icon = this.getIcon();

			data.label = label;

			if ( icon !== '' ) {

				data.icon = icon;

			}

		}

	}
```
</details>

### `LabelElement.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`
- `this.setLabel`
- `this.setIcon`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		if ( this.serializeLabel ) {

			this.setLabel( data.label );

			if ( data.icon !== undefined ) {

				this.setIcon( data.icon );

			}

		}

	}
```
</details>

### `ButtonInput.setIcon(className: any): this`

**Parameters:**

- **`className`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setIcon( className ) {

		this.iconDOM.className = className;

		return this;

	}
```
</details>

### `ButtonInput.getIcon(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getIcon() {

		return this.iconDOM.className;

	}
```
</details>

### `ButtonInput.setValue(val: any): this`

**Parameters:**

- **`val`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setValue( val ) {

		this.spanDOM.innerText = val;

		return this;

	}
```
</details>

### `ButtonInput.getValue(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.spanDOM.innerText;

	}
```
</details>

### `ColorInput.setValue(value: any, dispatch: boolean): this`

**Parameters:**

- **`value`** `any`
- **`dispatch`** `boolean`

**Returns:** `this`

**Calls:**

- `super.setValue`
- `numberToHex`

<details><summary>Code</summary>

```typescript
setValue( value, dispatch = true ) {

		return super.setValue( numberToHex( value ), dispatch );

	}
```
</details>

### `ColorInput.getValue(): number`

**Returns:** `number`

**Calls:**

- `parseInt`
- `super.getValue().substr`

<details><summary>Code</summary>

```typescript
getValue() {

		return parseInt( super.getValue().substr( 1 ), 16 );

	}
```
</details>

### `NumberInput.setStep(step: any): this`

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

### `NumberInput.setRange(min: any, max: any, step: any): this`

**Parameters:**

- **`min`** `any`
- **`max`** `any`
- **`step`** `any`

**Returns:** `this`

**Calls:**

- `this.dispatchEvent`
- `this.setValue`
- `this.getValue`

<details><summary>Code</summary>

```typescript
setRange( min, max, step ) {

		this.min = min;
		this.max = max;
		this.step = step;

		this.dispatchEvent( new Event( 'range' ) );

		return this.setValue( this.getValue() );

	}
```
</details>

### `NumberInput.setInterger(bool: any): this`

**Parameters:**

- **`bool`** `any`

**Returns:** `this`

**Calls:**

- `this.setValue`
- `this.getValue`

<details><summary>Code</summary>

```typescript
setInterger( bool ) {

		this.integer = bool;
		this.step = .1;

		return this.setValue( this.getValue() );

	}
```
</details>

### `NumberInput.setValue(val: any, dispatch: boolean): this`

**Parameters:**

- **`val`** `any`
- **`dispatch`** `boolean`

**Returns:** `this`

**Calls:**

- `super.setValue`
- `this._getString`

<details><summary>Code</summary>

```typescript
setValue( val, dispatch = true ) {

		return super.setValue( this._getString( val ), dispatch );

	}
```
</details>

### `NumberInput.getValue(): number`

**Returns:** `number`

**Calls:**

- `Number`

<details><summary>Code</summary>

```typescript
getValue() {

		return Number( this.dom.value );

	}
```
</details>

### `NumberInput.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		const { min, max } = this;

		if ( min !== - Infinity && max !== Infinity ) {

			data.min = this.min;
			data.max = this.max;
			data.step = this.step;

		}

		super.serialize( data );

	}
```
</details>

### `NumberInput.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.setRange`
- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		if ( data.min !== undefined ) {

			const { min, max, step } = this;

			this.setRange( min, max, step );

		}

		super.deserialize( data );

	}
```
</details>

### `NumberInput._getString(value: any): string | number`

**Parameters:**

- **`value`** `any`

**Returns:** `string | number`

**Calls:**

- `Math.min`
- `Math.max`
- `Number`
- `Math.floor`

<details><summary>Code</summary>

```typescript
_getString( value ) {

		const num = Math.min( Math.max( Number( value ), this.min ), this.max );

		if ( this.integer === true ) {

			return Math.floor( num );

		} else {

			return num + ( num % 1 ? '' : '.0' );

		}

	}
```
</details>

### `SelectInput.setOptions(options: any, value: any): this`

**Parameters:**

- **`options`** `any`
- **`value`** `any`

**Returns:** `this`

**Calls:**

- `document.createElement`
- `dom.append`

<details><summary>Code</summary>

```typescript
setOptions( options, value = null ) {

		const dom = this.dom;
		const defaultValue = dom.value;

		let containsDefaultValue = false;

		this.options = options;
		dom.innerHTML = '';

		for ( let index = 0; index < options.length; index ++ ) {

			let opt = options[ index ];

			if ( typeof opt === 'string' ) {

				opt = { name: opt, value: index };

			}

			const option = document.createElement( 'option' );
			option.innerText = opt.name;
			option.value = opt.value;

			if ( containsDefaultValue === false && defaultValue === opt.value ) {

				containsDefaultValue = true;

			}

			dom.append( option );

		}

		dom.value = value !== null ? value : containsDefaultValue ? defaultValue : '';

		return this;

	}
```
</details>

### `SelectInput.getOptions(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getOptions() {

		return this._options;

	}
```
</details>

### `SelectInput.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		data.options = [ ...this.options ];

		super.serialize( data );

	}
```
</details>

### `SelectInput.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.setOptions`
- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		const currentOptions = this.options;

		if ( currentOptions.length === 0 ) {

			this.setOptions( data.options );

		}

		super.deserialize( data );

	}
```
</details>

### `getStep(min: any, max: any): number`

**Parameters:**

- **`min`** `any`
- **`max`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
( min, max ) => {

	const sensibility = .001;

	return ( max - min ) * sensibility;

}
```
</details>

### `SliderInput.setRange(min: any, max: any): this`

**Parameters:**

- **`min`** `any`
- **`max`** `any`

**Returns:** `this`

**Calls:**

- `this.field.setRange`
- `getStep`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
setRange( min, max ) {

		this.field.setRange( min, max, getStep( min, max ) );

		this.dispatchEvent( new Event( 'range' ) );
		this.dispatchEvent( new Event( 'change' ) );

		return this;

	}
```
</details>

### `SliderInput.setValue(val: any, dispatch: boolean): this`

**Parameters:**

- **`val`** `any`
- **`dispatch`** `boolean`

**Returns:** `this`

**Calls:**

- `this.field.setValue`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
setValue( val, dispatch = true ) {

		this.field.setValue( val );
		this.rangeDOM.value = val;

		if ( dispatch ) this.dispatchEvent( new Event( 'change' ) );

		return this;

	}
```
</details>

### `SliderInput.getValue(): number`

**Returns:** `number`

**Calls:**

- `this.field.getValue`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.field.getValue();

	}
```
</details>

### `SliderInput.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		data.min = this.min;
		data.max = this.max;

		super.serialize( data );

	}
```
</details>

### `SliderInput.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.setRange`
- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		const { min, max } = data;

		this.setRange( min, max );

		super.deserialize( data );

	}
```
</details>

### `updateRangeValue(): void`

**Returns:** `void`

**Calls:**

- `Number`
- `this.field.setValue`

**Internal Comments:**
```
// fix not end range fraction (x4)
```

<details><summary>Code</summary>

```typescript
() => {

			let value = Number( rangeDOM.value );

			if ( value !== this.max && value + this.step >= this.max ) {

				// fix not end range fraction

				rangeDOM.value = value = this.max;

			}

			this.field.setValue( value );

		}
```
</details>

### `StringInput.setPlaceHolder(text: any): this`

**Parameters:**

- **`text`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setPlaceHolder( text ) {

		this.inputDOM.placeholder = text;

		return this;

	}
```
</details>

### `StringInput.setIcon(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `document.createElement`
- `this.iconDOM.setAttribute`
- `this.dom.prepend`
- `this.iconDOM.remove`

<details><summary>Code</summary>

```typescript
setIcon( value ) {

		this.iconDOM = this.iconDOM || document.createElement( 'i' );
		this.iconDOM.setAttribute( 'type', 'icon' );
		this.iconDOM.className = value;

		if ( value ) this.dom.prepend( this.iconDOM );
		else this.iconDOM.remove();

		return this;

	}
```
</details>

### `StringInput.getIcon(): any`

**Returns:** `any`

**Calls:**

- `this.iconInput.getIcon`

<details><summary>Code</summary>

```typescript
getIcon() {

		return this.iconInput ? this.iconInput.getIcon() : '';

	}
```
</details>

### `StringInput.addButton(button: any): this`

**Parameters:**

- **`button`** `any`

**Returns:** `this`

**Calls:**

- `this.buttonsDOM.prepend`
- `this.buttons.push`

<details><summary>Code</summary>

```typescript
addButton( button ) {

		this.buttonsDOM.prepend( button.iconDOM );

		this.buttons.push( button );

		return this;

	}
```
</details>

### `StringInput.addOption(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `document.createElement`
- `this.datalistDOM.append`

<details><summary>Code</summary>

```typescript
addOption( value ) {

		const option = document.createElement( 'option' );
		option.value = value;

		this.datalistDOM.append( option );

		return this;

	}
```
</details>

### `StringInput.clearOptions(): void`

**Returns:** `void`

**Calls:**

- `this.datalistDOM.remove`

<details><summary>Code</summary>

```typescript
clearOptions() {

		this.datalistDOM.remove();

	}
```
</details>

### `StringInput.getInput(): HTMLInputElement`

**Returns:** `HTMLInputElement`

<details><summary>Code</summary>

```typescript
getInput() {

		return this.inputDOM;

	}
```
</details>

### `ToggleInput.setValue(val: any): this`

**Parameters:**

- **`val`** `any`

**Returns:** `this`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
setValue( val ) {

		this.dom.checked = val;

		this.dispatchEvent( new Event( 'change' ) );

		return this;

	}
```
</details>

### `ToggleInput.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.dom.checked;

	}
```
</details>

### `TreeViewNode.setLabel(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setLabel( value ) {

		this.labelSpam.innerText = value;

		return this;

	}
```
</details>

### `TreeViewNode.getLabel(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getLabel() {

		return this.labelSpam.innerText;

	}
```
</details>

### `TreeViewNode.add(node: any): this`

**Parameters:**

- **`node`** `any`

**Returns:** `this`

**Calls:**

- `document.createElement`
- `dom.append`
- `this.children.push`
- `childrenDOM.append`

<details><summary>Code</summary>

```typescript
add( node ) {

		let childrenDOM = this.childrenDOM;

		if ( this.childrenDOM === null ) {

			const dom = this.dom;

			const arrowDOM = document.createElement( 'f-arrow' );
			childrenDOM = document.createElement( 'f-treeview-children' );

			dom.append( arrowDOM );
			dom.append( childrenDOM );

			this.childrenDOM = childrenDOM;

		}

		this.children.push( node );
		childrenDOM.append( node.dom );

		node.parent = this;

		return this;

	}
```
</details>

### `TreeViewNode.setOpened(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setOpened( value ) {

		this.inputDOM.checked = value;

		return this;

	}
```
</details>

### `TreeViewNode.getOpened(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getOpened() {

		return this.inputDOM.checkbox;

	}
```
</details>

### `TreeViewNode.setIcon(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `document.createElement`
- `this.labelDOM.prepend`
- `this.iconDOM.remove`

<details><summary>Code</summary>

```typescript
setIcon( value ) {

		this.iconDOM = this.iconDOM || document.createElement( 'i' );
		this.iconDOM.className = value;

		if ( value ) this.labelDOM.prepend( this.iconDOM );
		else this.iconDOM.remove();

		return this;

	}
```
</details>

### `TreeViewNode.getIcon(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getIcon() {

		return this.iconDOM ? this.iconDOM.className : null;

	}
```
</details>

### `TreeViewNode.setVisible(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setVisible( value ) {

		this.dom.style.display = value ? '' : 'none';

		return this;

	}
```
</details>

### `TreeViewNode.setSelected(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `this.dom.classList.add`
- `this.dom.classList.remove`

<details><summary>Code</summary>

```typescript
setSelected( value ) {

		if ( this.selected === value ) return this;

		if ( value ) this.dom.classList.add( 'selected' );
		else this.dom.classList.remove( 'selected' );

		this.selected = value;

		return this;

	}
```
</details>

### `TreeViewNode.onClick(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.click.push`

<details><summary>Code</summary>

```typescript
onClick( callback ) {

		this.events.click.push( callback );

		return this;

	}
```
</details>

### `TreeViewInput.add(node: any): this`

**Parameters:**

- **`node`** `any`

**Returns:** `this`

**Calls:**

- `this.children.push`
- `this.childrenDOM.append`

<details><summary>Code</summary>

```typescript
add( node ) {

		this.children.push( node );
		this.childrenDOM.append( node.dom );

		return this;

	}
```
</details>

### `TreeViewInput.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

**Internal Comments:**
```
//data.options = [ ...this.options ]; (x4)
```

<details><summary>Code</summary>

```typescript
serialize( data ) {

		//data.options = [ ...this.options ];

		super.serialize( data );

	}
```
</details>

### `TreeViewInput.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

**Internal Comments:**
```
/*const currentOptions = this.options;

		if ( currentOptions.length === 0 ) {

			this.setOptions( data.options );

		}*/ (x4)
```

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		/*const currentOptions = this.options;

		if ( currentOptions.length === 0 ) {

			this.setOptions( data.options );

		}*/

		super.deserialize( data );

	}
```
</details>

### `Loader.setParseType(type: any): this`

**Parameters:**

- **`type`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setParseType( type ) {

		this.parseType = type;

		return this;

	}
```
</details>

### `Loader.getParseType(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getParseType() {

		return this.parseType;

	}
```
</details>

### `Loader.onLoad(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.events.load.push`

<details><summary>Code</summary>

```typescript
onLoad( callback ) {

		this.events.load.push( callback );

		return this;

	}
```
</details>

### `Loader.load(url: any, lib: {}): Promise<any>`

**Parameters:**

- **`url`** `any`
- **`lib`** `{}`

**Returns:** `Promise<any>`

**Calls:**

- `fetch( url )
			.then( response => response.json() )
			.then( result => {

				this.data = this.parse( result, lib );

				dispatchEventList( this.events.load, this );

				return this.data;

			} )
			.catch`
- `console.error`

<details><summary>Code</summary>

```typescript
async load( url, lib = {} ) {

		return await fetch( url )
			.then( response => response.json() )
			.then( result => {

				this.data = this.parse( result, lib );

				dispatchEventList( this.events.load, this );

				return this.data;

			} )
			.catch( err => {

				console.error( 'Loader:', err );

			} );

	}
```
</details>

### `Loader.parse(json: any, lib: {}): any`

**Parameters:**

- **`json`** `any`
- **`lib`** `{}`

**Returns:** `any`

**Calls:**

- `this._parseObjects`
- `flowObj.getSerializable`
- `flowObj.deserialize`

<details><summary>Code</summary>

```typescript
parse( json, lib = {} ) {

		json = this._parseObjects( json, lib );

		const parseType = this.parseType;

		if ( parseType === Loader.DEFAULT ) {

			const type = json.type;

			const flowClass = lib[ type ] ? lib[ type ] : ( LoaderLib[ type ] || Flow[ type ] );
			const flowObj = new flowClass();

			if ( flowObj.getSerializable() ) {

				flowObj.deserialize( json );

			}

			return flowObj;

		} else if ( parseType === Loader.OBJECTS ) {

			return json;

		}

	}
```
</details>

### `Loader._parseObjects(json: any, lib: {}): any`

**Parameters:**

- **`json`** `any`
- **`lib`** `{}`

**Returns:** `any`

**Calls:**

- `console.error`
- `objects[ id ].deserializeLib`
- `ref.has`
- `ref.set`
- `newObject.getSerializable`
- `newObject.deserialize`
- `deserializePass`

<details><summary>Code</summary>

```typescript
_parseObjects( json, lib = {} ) {

		json = { ...json };

		const objects = {};

		for ( const id in json.objects ) {

			const obj = json.objects[ id ];
			obj.objects = objects;

			const type = obj.type;
			const flowClass = lib[ type ] ? lib[ type ] : ( LoaderLib[ type ] || Flow[ type ] );

			if ( ! flowClass ) {

				console.error( `Class "${ type }" not found!` );

			}

			objects[ id ] = new flowClass();
			objects[ id ].deserializeLib( json.objects[ id ], lib );

		}

		const ref = new Map();

		const deserializePass = ( prop = null ) => {

			for ( const id in json.objects ) {

				const newObject = objects[ id ];

				if ( ref.has( newObject ) === false && ( prop === null || newObject[ prop ] === true ) ) {

					ref.set( newObject, true );

					if ( newObject.getSerializable() ) {

						newObject.deserialize( json.objects[ id ] );

					}

				}

			}

		};

		deserializePass( 'isNode' );
		deserializePass( 'isElement' );
		deserializePass( 'isInput' );
		deserializePass();

		json.objects = objects;

		return json;

	}
```
</details>

### `deserializePass(prop: any): void`

**Parameters:**

- **`prop`** `any`

**Returns:** `void`

**Calls:**

- `ref.has`
- `ref.set`
- `newObject.getSerializable`
- `newObject.deserialize`

<details><summary>Code</summary>

```typescript
( prop = null ) => {

			for ( const id in json.objects ) {

				const newObject = objects[ id ];

				if ( ref.has( newObject ) === false && ( prop === null || newObject[ prop ] === true ) ) {

					ref.set( newObject, true );

					if ( newObject.getSerializable() ) {

						newObject.deserialize( json.objects[ id ] );

					}

				}

			}

		}
```
</details>


---

## Classes

### `Serializer`

<details><summary>Class Code</summary>

```ts
class Serializer extends EventTarget {

	static get type() {

		return 'Serializer';

	}

	constructor() {

		super();

		this._id = _id ++;

		this._serializable = true;

	}

	get id() {

		return this._id;

	}

	setSerializable( value ) {

		this._serializable = value;

		return this;

	}

	getSerializable() {

		return this._serializable;

	}

	serialize( /*data*/ ) {

		console.warn( 'Serializer: Abstract function.' );

	}

	deserialize( /*data*/ ) {

		console.warn( 'Serializer: Abstract function.' );

	}

	deserializeLib( /*data, lib*/ ) {

		// Abstract function.

	}

	get className() {

		return this.constructor.type || this.constructor.name;

	}

	toJSON( data = null ) {

		let object = null;

		const id = this.id;

		if ( data !== null ) {

			const objects = data.objects;

			object = objects[ id ];

			if ( object === undefined ) {

				object = { objects };

				this.serialize( object );

				delete object.objects;

				objects[ id ] = object;

			}

		} else {

			object = { objects: {} };

			this.serialize( object );

		}

		object.id = id;
		object.type = this.className;

		return object;

	}

}
```
</details>

#### Methods

##### `setSerializable(value: any): this`

<details><summary>Code</summary>

```ts
setSerializable( value ) {

		this._serializable = value;

		return this;

	}
```
</details>

##### `getSerializable(): boolean`

<details><summary>Code</summary>

```ts
getSerializable() {

		return this._serializable;

	}
```
</details>

##### `serialize(): void`

<details><summary>Code</summary>

```ts
serialize( /*data*/ ) {

		console.warn( 'Serializer: Abstract function.' );

	}
```
</details>

##### `deserialize(): void`

<details><summary>Code</summary>

```ts
deserialize( /*data*/ ) {

		console.warn( 'Serializer: Abstract function.' );

	}
```
</details>

##### `deserializeLib(): void`

<details><summary>Code</summary>

```ts
deserializeLib( /*data, lib*/ ) {

		// Abstract function.

	}
```
</details>

##### `toJSON(data: any): any`

<details><summary>Code</summary>

```ts
toJSON( data = null ) {

		let object = null;

		const id = this.id;

		if ( data !== null ) {

			const objects = data.objects;

			object = objects[ id ];

			if ( object === undefined ) {

				object = { objects };

				this.serialize( object );

				delete object.objects;

				objects[ id ] = object;

			}

		} else {

			object = { objects: {} };

			this.serialize( object );

		}

		object.id = id;
		object.type = this.className;

		return object;

	}
```
</details>

### `PointerMonitor`

<details><summary>Class Code</summary>

```ts
class PointerMonitor {

	constructor() {

		this.x = 0;
		this.y = 0;
		this.started = false;

		this._onMoveEvent = ( e ) => {

			const event = e.touches ? e.touches[ 0 ] : e;

			this.x = event.clientX;
			this.y = event.clientY;

		};

	}

	start() {

		if ( this.started ) return;

		this.started = true;

		window.addEventListener( 'wheel', this._onMoveEvent, true );

		window.addEventListener( 'mousedown', this._onMoveEvent, true );
		window.addEventListener( 'touchstart', this._onMoveEvent, true );

		window.addEventListener( 'mousemove', this._onMoveEvent, true );
		window.addEventListener( 'touchmove', this._onMoveEvent, true );

		window.addEventListener( 'dragover', this._onMoveEvent, true );

		return this;

	}

}
```
</details>

#### Methods

##### `start(): this`

<details><summary>Code</summary>

```ts
start() {

		if ( this.started ) return;

		this.started = true;

		window.addEventListener( 'wheel', this._onMoveEvent, true );

		window.addEventListener( 'mousedown', this._onMoveEvent, true );
		window.addEventListener( 'touchstart', this._onMoveEvent, true );

		window.addEventListener( 'mousemove', this._onMoveEvent, true );
		window.addEventListener( 'touchmove', this._onMoveEvent, true );

		window.addEventListener( 'dragover', this._onMoveEvent, true );

		return this;

	}
```
</details>

### `Link`

<details><summary>Class Code</summary>

```ts
class Link {

	constructor( inputElement = null, outputElement = null ) {

		this.inputElement = inputElement;
		this.outputElement = outputElement;

	}

	get lioElement() {

		if ( Link.InputDirection === 'left' ) {

			return this.outputElement;

		} else {

			return this.inputElement;

		}

	}

	get rioElement() {

		if ( Link.InputDirection === 'left' ) {

			return this.inputElement;

		} else {

			return this.outputElement;

		}

	}

}
```
</details>

### `Element`

<details><summary>Class Code</summary>

```ts
class Element extends Serializer {

	static get type() {

		return 'Element';

	}

	constructor( draggable = false ) {

		super();

		this.isElement = true;

		const dom = document.createElement( 'f-element' );
		dom.element = this;

		const onSelect = ( e ) => {

			let element = this;

			if ( e.changedTouches && e.changedTouches.length > 0 ) {

				const touch = e.changedTouches[ 0 ];

				let overDOM = document.elementFromPoint( touch.clientX, touch.clientY );

				while ( overDOM && ( ! overDOM.element || ! overDOM.element.isElement ) ) {

					overDOM = overDOM.parentNode;

				}

				element = overDOM ? overDOM.element : null;

			}

			const type = e.type;

			if ( ( type === 'mouseout' ) && selected === element ) {

				selected = null;

			} else {

				selected = element;

			}

		};

		if ( draggable === false ) {

			dom.ontouchstart = dom.onmousedown = ( e ) => {

				e.stopPropagation();

			};

		}

		dom.addEventListener( 'mouseup', onSelect, true );
		dom.addEventListener( 'mouseover', onSelect );
		dom.addEventListener( 'mouseout', onSelect );
		dom.addEventListener( 'touchmove', onSelect );
		dom.addEventListener( 'touchend', onSelect );

		this.inputs = [];

		this.links = [];

		this.dom = dom;

		this.lioLength = 0;
		this.rioLength = 0;

		this.events = {
			'connect': [],
			'connectChildren': [],
			'valid': []
		};

		this.node = null;

		this.style = '';
		this.color = null;

		this.object = null;
		this.objectCallback = null;

		this.enabledInputs = true;

		this.visible = true;

		this.inputsDOM = dom;

		this.disconnectDOM = null;

		this.lioDOM = this._createIO( 'lio' );
		this.rioDOM = this._createIO( 'rio' );

		this.dom.classList.add( `input-${ Link.InputDirection }` );

		this.addEventListener( 'connect', ( ) => {

			dispatchEventList( this.events.connect, this );

		} );

		this.addEventListener( 'connectChildren', ( ) => {

			dispatchEventList( this.events.connectChildren, this );

		} );

	}

	setAttribute( name, value ) {

		this.dom.setAttribute( name, value );

		return this;

	}

	onValid( callback ) {

		this.events.valid.push( callback );

		return this;

	}

	onConnect( callback, childrens = false ) {

		this.events.connect.push( callback );

		if ( childrens ) {

			this.events.connectChildren.push( callback );

		}

		return this;

	}

	setObjectCallback( callback ) {

		this.objectCallback = callback;

		return this;

	}

	setObject( value ) {

		this.object = value;

		return this;

	}

	getObject( output = null ) {

		return this.objectCallback ? this.objectCallback( output ) : this.object;

	}

	setVisible( value ) {

		this.visible = value;

		this.dom.style.display = value ? '' : 'none';

		return this;

	}

	getVisible() {

		return this.visible;

	}

	setEnabledInputs( value ) {

		const dom = this.dom;

		if ( ! this.enabledInputs ) dom.classList.remove( 'inputs-disable' );

		if ( ! value ) dom.classList.add( 'inputs-disable' );

		this.enabledInputs = value;

		return this;

	}

	getEnabledInputs() {

		return this.enabledInputs;

	}

	setColor( color ) {

		this.dom.style[ 'background-color' ] = numberToHex( color );
		this.color = null;

		return this;

	}

	getColor() {

		if ( this.color === null ) {

			const css = window.getComputedStyle( this.dom );

			this.color = css.getPropertyValue( 'background-color' );

		}

		return this.color;

	}

	setStyle( style ) {

		const dom = this.dom;

		if ( this.style ) dom.classList.remove( this.style );

		if ( style ) dom.classList.add( style );

		this.style = style;
		this.color = null;

		return this;

	}

	setInput( length ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setLIO( length );

		} else {

			return this.setRIO( length );

		}

	}

	setInputColor( color ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setLIOColor( color );

		} else {

			return this.setRIOColor( color );

		}

	}

	setOutput( length ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setRIO( length );

		} else {

			return this.setLIO( length );

		}

	}

	setOutputColor( color ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setRIOColor( color );

		} else {

			return this.setLIOColor( color );

		}

	}

	get inputLength() {

		if ( Link.InputDirection === 'left' ) {

			return this.lioLength;

		} else {

			return this.rioLength;

		}

	}

	get outputLength() {

		if ( Link.InputDirection === 'left' ) {

			return this.rioLength;

		} else {

			return this.lioLength;

		}

	}

	setLIOColor( color ) {

		this.lioDOM.style[ 'border-color' ] = numberToHex( color );

		return this;

	}

	setLIO( length ) {

		this.lioLength = length;

		this.lioDOM.style.visibility = length > 0 ? '' : 'hidden';

		if ( length > 0 ) {

			this.dom.classList.add( 'lio' );
			this.dom.prepend( this.lioDOM );

		} else {

			this.dom.classList.remove( 'lio' );
			this.lioDOM.remove();

		}

		return this;

	}

	getLIOColor() {

		return this.lioDOM.style[ 'border-color' ];

	}

	setRIOColor( color ) {

		this.rioDOM.style[ 'border-color' ] = numberToHex( color );

		return this;

	}

	getRIOColor() {

		return this.rioDOM.style[ 'border-color' ];

	}

	setRIO( length ) {

		this.rioLength = length;

		this.rioDOM.style.visibility = length > 0 ? '' : 'hidden';

		if ( length > 0 ) {

			this.dom.classList.add( 'rio' );
			this.dom.prepend( this.rioDOM );

		} else {

			this.dom.classList.remove( 'rio' );
			this.rioDOM.remove();

		}

		return this;

	}

	add( input ) {

		this.inputs.push( input );

		input.element = this;

		this.inputsDOM.append( input.dom );

		return this;

	}

	setHeight( val ) {

		this.dom.style.height = numberToPX( val );

		return this;

	}

	getHeight() {

		return parseInt( this.dom.style.height );

	}

	connect( element = null ) {

		if ( this.disconnectDOM !== null ) {

			// remove the current input

			this.disconnectDOM.dispatchEvent( new Event( 'disconnect' ) );

		}

		if ( element !== null ) {

			element = element.baseElement || element;

			if ( dispatchEventList( this.events.valid, this, element, 'connect' ) === false ) {

				return false;

			}

			const link = new Link( this, element );

			this.links.push( link );

			if ( this.disconnectDOM === null ) {

				this.disconnectDOM = document.createElement( 'f-disconnect' );
				this.disconnectDOM.innerHTML = Element.icons.unlink ? `<i class='${ Element.icons.unlink }'></i>` : '✖';

				this.dom.append( this.disconnectDOM );

				const onDisconnect = () => {

					this.links = [];
					this.dom.removeChild( this.disconnectDOM );

					this.disconnectDOM.removeEventListener( 'mousedown', onClick, true );
					this.disconnectDOM.removeEventListener( 'touchstart', onClick, true );
					this.disconnectDOM.removeEventListener( 'disconnect', onDisconnect, true );

					element.removeEventListener( 'connect', onConnect );
					element.removeEventListener( 'connectChildren', onConnect );
					element.removeEventListener( 'nodeConnect', onConnect );
					element.removeEventListener( 'nodeConnectChildren', onConnect );
					element.removeEventListener( 'dispose', onDispose );

					this.disconnectDOM = null;

				};

				const onConnect = () => {

					this.dispatchEvent( new Event( 'connectChildren' ) );

				};

				const onDispose = () => {

					this.connect();

				};

				const onClick = ( e ) => {

					e.stopPropagation();

					this.connect();

				};

				this.disconnectDOM.addEventListener( 'mousedown', onClick, true );
				this.disconnectDOM.addEventListener( 'touchstart', onClick, true );
				this.disconnectDOM.addEventListener( 'disconnect', onDisconnect, true );

				element.addEventListener( 'connect', onConnect );
				element.addEventListener( 'connectChildren', onConnect );
				element.addEventListener( 'nodeConnect', onConnect );
				element.addEventListener( 'nodeConnectChildren', onConnect );
				element.addEventListener( 'dispose', onDispose );

			}

		}

		this.dispatchEvent( new Event( 'connect' ) );

		return true;

	}

	dispose() {

		this.dispatchEvent( new Event( 'dispose' ) );

	}

	getInputByProperty( property ) {

		for ( const input of this.inputs ) {

			if ( input.getProperty() === property ) {

				return input;

			}

		}

	}

	serialize( data ) {

		const inputs = [];
		const properties = [];
		const links = [];

		for ( const input of this.inputs ) {

			const id = input.toJSON( data ).id;
			const property = input.getProperty();

			inputs.push( id );

			if ( property !== null ) {

				properties.push( { property, id } );

			}

		}

		for ( const link of this.links ) {

			if ( link.inputElement !== null && link.outputElement !== null ) {

				links.push( link.outputElement.toJSON( data ).id );

			}

		}

		if ( this.inputLength > 0 ) data.inputLength = this.inputLength;
		if ( this.outputLength > 0 ) data.outputLength = this.outputLength;

		if ( inputs.length > 0 ) data.inputs = inputs;
		if ( properties.length > 0 ) data.properties = properties;
		if ( links.length > 0 ) data.links = links;

		if ( this.style !== '' ) {

			data.style = this.style;

		}

		data.height = this.getHeight();

	}

	deserialize( data ) {

		if ( data.inputLength !== undefined ) this.setInput( data.inputLength );
		if ( data.outputLength !== undefined ) this.setOutput( data.outputLength );

		if ( data.properties !== undefined ) {

			for ( const { id, property } of data.properties ) {

				data.objects[ id ] = this.getInputByProperty( property );

			}

		} else if ( data.inputs !== undefined ) {

			const inputs = this.inputs;

			if ( inputs.length > 0 ) {

				let index = 0;

				for ( const id of data.inputs ) {

					data.objects[ id ] = inputs[ index ++ ];

				}

			} else {

				for ( const id of data.inputs ) {

					this.add( data.objects[ id ] );

				}

			}

		}

		if ( data.links !== undefined ) {

			for ( const id of data.links ) {

				this.connect( data.objects[ id ] );

			}

		}

		if ( data.style !== undefined ) {

			this.setStyle( data.style );

		}

		if ( data.height !== undefined ) {

			this.setHeight( data.height );

		}

	}

	getLinkedObject( output = null ) {

		const linkedElement = this.getLinkedElement();

		return linkedElement ? linkedElement.getObject( output ) : null;

	}

	getLinkedElement() {

		const link = this.getLink();

		return link ? link.outputElement : null;

	}

	getLink() {

		return this.links[ 0 ];

	}

	_createIO( type ) {

		const { dom } = this;

		const ioDOM = document.createElement( 'f-io' );
		ioDOM.style.visibility = 'hidden';
		ioDOM.className = type;

		const onConnectEvent = ( e ) => {

			e.preventDefault();

			e.stopPropagation();

			selected = null;

			const nodeDOM = this.node.dom;

			nodeDOM.classList.add( 'io-connect' );

			ioDOM.classList.add( 'connect' );
			dom.classList.add( 'select' );

			const defaultOutput = Link.InputDirection === 'left' ? 'lio' : 'rio';

			const link = type === defaultOutput ? new Link( this ) : new Link( null, this );
			const previewLink = new Link( link.inputElement, link.outputElement );

			this.links.push( link );

			draggableDOM( e, ( data ) => {

				if ( previewLink.outputElement )
					previewLink.outputElement.dom.classList.remove( 'invalid' );

				if ( previewLink.inputElement )
					previewLink.inputElement.dom.classList.remove( 'invalid' );

				previewLink.inputElement = link.inputElement;
				previewLink.outputElement = link.outputElement;

				if ( type === defaultOutput ) {

					previewLink.outputElement = selected;

				} else {

					previewLink.inputElement = selected;

				}

				const isInvalid = previewLink.inputElement !== null && previewLink.outputElement !== null &&
					previewLink.inputElement.inputLength > 0 && previewLink.outputElement.outputLength > 0 &&
					dispatchEventList( previewLink.inputElement.events.valid, previewLink.inputElement, previewLink.outputElement, data.dragging ? 'dragging' : 'dragged' ) === false;

				if ( data.dragging && isInvalid ) {

					if ( type === defaultOutput ) {

						if ( previewLink.outputElement )
							previewLink.outputElement.dom.classList.add( 'invalid' );

					} else {

						if ( previewLink.inputElement )
							previewLink.inputElement.dom.classList.add( 'invalid' );

					}

					return;

				}

				if ( ! data.dragging ) {

					nodeDOM.classList.remove( 'io-connect' );

					ioDOM.classList.remove( 'connect' );
					dom.classList.remove( 'select' );

					this.links.splice( this.links.indexOf( link ), 1 );

					if ( selected !== null && ! isInvalid ) {

						link.inputElement = previewLink.inputElement;
						link.outputElement = previewLink.outputElement;

						// check if is an is circular link

						if ( link.outputElement.node.isCircular( link.inputElement.node ) ) {

							return;

						}

						//

						if ( link.inputElement.inputLength > 0 && link.outputElement.outputLength > 0 ) {

							link.inputElement.connect( link.outputElement );

						}

					}

				}

			}, { className: 'connecting' } );

		};

		ioDOM.addEventListener( 'mousedown', onConnectEvent, true );
		ioDOM.addEventListener( 'touchstart', onConnectEvent, true );

		return ioDOM;

	}

}
```
</details>

#### Methods

##### `setAttribute(name: any, value: any): this`

<details><summary>Code</summary>

```ts
setAttribute( name, value ) {

		this.dom.setAttribute( name, value );

		return this;

	}
```
</details>

##### `onValid(callback: any): this`

<details><summary>Code</summary>

```ts
onValid( callback ) {

		this.events.valid.push( callback );

		return this;

	}
```
</details>

##### `onConnect(callback: any, childrens: boolean): this`

<details><summary>Code</summary>

```ts
onConnect( callback, childrens = false ) {

		this.events.connect.push( callback );

		if ( childrens ) {

			this.events.connectChildren.push( callback );

		}

		return this;

	}
```
</details>

##### `setObjectCallback(callback: any): this`

<details><summary>Code</summary>

```ts
setObjectCallback( callback ) {

		this.objectCallback = callback;

		return this;

	}
```
</details>

##### `setObject(value: any): this`

<details><summary>Code</summary>

```ts
setObject( value ) {

		this.object = value;

		return this;

	}
```
</details>

##### `getObject(output: any): any`

<details><summary>Code</summary>

```ts
getObject( output = null ) {

		return this.objectCallback ? this.objectCallback( output ) : this.object;

	}
```
</details>

##### `setVisible(value: any): this`

<details><summary>Code</summary>

```ts
setVisible( value ) {

		this.visible = value;

		this.dom.style.display = value ? '' : 'none';

		return this;

	}
```
</details>

##### `getVisible(): boolean`

<details><summary>Code</summary>

```ts
getVisible() {

		return this.visible;

	}
```
</details>

##### `setEnabledInputs(value: any): this`

<details><summary>Code</summary>

```ts
setEnabledInputs( value ) {

		const dom = this.dom;

		if ( ! this.enabledInputs ) dom.classList.remove( 'inputs-disable' );

		if ( ! value ) dom.classList.add( 'inputs-disable' );

		this.enabledInputs = value;

		return this;

	}
```
</details>

##### `getEnabledInputs(): boolean`

<details><summary>Code</summary>

```ts
getEnabledInputs() {

		return this.enabledInputs;

	}
```
</details>

##### `setColor(color: any): this`

<details><summary>Code</summary>

```ts
setColor( color ) {

		this.dom.style[ 'background-color' ] = numberToHex( color );
		this.color = null;

		return this;

	}
```
</details>

##### `getColor(): string`

<details><summary>Code</summary>

```ts
getColor() {

		if ( this.color === null ) {

			const css = window.getComputedStyle( this.dom );

			this.color = css.getPropertyValue( 'background-color' );

		}

		return this.color;

	}
```
</details>

##### `setStyle(style: any): this`

<details><summary>Code</summary>

```ts
setStyle( style ) {

		const dom = this.dom;

		if ( this.style ) dom.classList.remove( this.style );

		if ( style ) dom.classList.add( style );

		this.style = style;
		this.color = null;

		return this;

	}
```
</details>

##### `setInput(length: any): this`

<details><summary>Code</summary>

```ts
setInput( length ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setLIO( length );

		} else {

			return this.setRIO( length );

		}

	}
```
</details>

##### `setInputColor(color: any): this`

<details><summary>Code</summary>

```ts
setInputColor( color ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setLIOColor( color );

		} else {

			return this.setRIOColor( color );

		}

	}
```
</details>

##### `setOutput(length: any): this`

<details><summary>Code</summary>

```ts
setOutput( length ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setRIO( length );

		} else {

			return this.setLIO( length );

		}

	}
```
</details>

##### `setOutputColor(color: any): this`

<details><summary>Code</summary>

```ts
setOutputColor( color ) {

		if ( Link.InputDirection === 'left' ) {

			return this.setRIOColor( color );

		} else {

			return this.setLIOColor( color );

		}

	}
```
</details>

##### `setLIOColor(color: any): this`

<details><summary>Code</summary>

```ts
setLIOColor( color ) {

		this.lioDOM.style[ 'border-color' ] = numberToHex( color );

		return this;

	}
```
</details>

##### `setLIO(length: any): this`

<details><summary>Code</summary>

```ts
setLIO( length ) {

		this.lioLength = length;

		this.lioDOM.style.visibility = length > 0 ? '' : 'hidden';

		if ( length > 0 ) {

			this.dom.classList.add( 'lio' );
			this.dom.prepend( this.lioDOM );

		} else {

			this.dom.classList.remove( 'lio' );
			this.lioDOM.remove();

		}

		return this;

	}
```
</details>

##### `getLIOColor(): any`

<details><summary>Code</summary>

```ts
getLIOColor() {

		return this.lioDOM.style[ 'border-color' ];

	}
```
</details>

##### `setRIOColor(color: any): this`

<details><summary>Code</summary>

```ts
setRIOColor( color ) {

		this.rioDOM.style[ 'border-color' ] = numberToHex( color );

		return this;

	}
```
</details>

##### `getRIOColor(): any`

<details><summary>Code</summary>

```ts
getRIOColor() {

		return this.rioDOM.style[ 'border-color' ];

	}
```
</details>

##### `setRIO(length: any): this`

<details><summary>Code</summary>

```ts
setRIO( length ) {

		this.rioLength = length;

		this.rioDOM.style.visibility = length > 0 ? '' : 'hidden';

		if ( length > 0 ) {

			this.dom.classList.add( 'rio' );
			this.dom.prepend( this.rioDOM );

		} else {

			this.dom.classList.remove( 'rio' );
			this.rioDOM.remove();

		}

		return this;

	}
```
</details>

##### `add(input: any): this`

<details><summary>Code</summary>

```ts
add( input ) {

		this.inputs.push( input );

		input.element = this;

		this.inputsDOM.append( input.dom );

		return this;

	}
```
</details>

##### `setHeight(val: any): this`

<details><summary>Code</summary>

```ts
setHeight( val ) {

		this.dom.style.height = numberToPX( val );

		return this;

	}
```
</details>

##### `getHeight(): number`

<details><summary>Code</summary>

```ts
getHeight() {

		return parseInt( this.dom.style.height );

	}
```
</details>

##### `connect(element: any): boolean`

<details><summary>Code</summary>

```ts
connect( element = null ) {

		if ( this.disconnectDOM !== null ) {

			// remove the current input

			this.disconnectDOM.dispatchEvent( new Event( 'disconnect' ) );

		}

		if ( element !== null ) {

			element = element.baseElement || element;

			if ( dispatchEventList( this.events.valid, this, element, 'connect' ) === false ) {

				return false;

			}

			const link = new Link( this, element );

			this.links.push( link );

			if ( this.disconnectDOM === null ) {

				this.disconnectDOM = document.createElement( 'f-disconnect' );
				this.disconnectDOM.innerHTML = Element.icons.unlink ? `<i class='${ Element.icons.unlink }'></i>` : '✖';

				this.dom.append( this.disconnectDOM );

				const onDisconnect = () => {

					this.links = [];
					this.dom.removeChild( this.disconnectDOM );

					this.disconnectDOM.removeEventListener( 'mousedown', onClick, true );
					this.disconnectDOM.removeEventListener( 'touchstart', onClick, true );
					this.disconnectDOM.removeEventListener( 'disconnect', onDisconnect, true );

					element.removeEventListener( 'connect', onConnect );
					element.removeEventListener( 'connectChildren', onConnect );
					element.removeEventListener( 'nodeConnect', onConnect );
					element.removeEventListener( 'nodeConnectChildren', onConnect );
					element.removeEventListener( 'dispose', onDispose );

					this.disconnectDOM = null;

				};

				const onConnect = () => {

					this.dispatchEvent( new Event( 'connectChildren' ) );

				};

				const onDispose = () => {

					this.connect();

				};

				const onClick = ( e ) => {

					e.stopPropagation();

					this.connect();

				};

				this.disconnectDOM.addEventListener( 'mousedown', onClick, true );
				this.disconnectDOM.addEventListener( 'touchstart', onClick, true );
				this.disconnectDOM.addEventListener( 'disconnect', onDisconnect, true );

				element.addEventListener( 'connect', onConnect );
				element.addEventListener( 'connectChildren', onConnect );
				element.addEventListener( 'nodeConnect', onConnect );
				element.addEventListener( 'nodeConnectChildren', onConnect );
				element.addEventListener( 'dispose', onDispose );

			}

		}

		this.dispatchEvent( new Event( 'connect' ) );

		return true;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.dispatchEvent( new Event( 'dispose' ) );

	}
```
</details>

##### `getInputByProperty(property: any): any`

<details><summary>Code</summary>

```ts
getInputByProperty( property ) {

		for ( const input of this.inputs ) {

			if ( input.getProperty() === property ) {

				return input;

			}

		}

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		const inputs = [];
		const properties = [];
		const links = [];

		for ( const input of this.inputs ) {

			const id = input.toJSON( data ).id;
			const property = input.getProperty();

			inputs.push( id );

			if ( property !== null ) {

				properties.push( { property, id } );

			}

		}

		for ( const link of this.links ) {

			if ( link.inputElement !== null && link.outputElement !== null ) {

				links.push( link.outputElement.toJSON( data ).id );

			}

		}

		if ( this.inputLength > 0 ) data.inputLength = this.inputLength;
		if ( this.outputLength > 0 ) data.outputLength = this.outputLength;

		if ( inputs.length > 0 ) data.inputs = inputs;
		if ( properties.length > 0 ) data.properties = properties;
		if ( links.length > 0 ) data.links = links;

		if ( this.style !== '' ) {

			data.style = this.style;

		}

		data.height = this.getHeight();

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		if ( data.inputLength !== undefined ) this.setInput( data.inputLength );
		if ( data.outputLength !== undefined ) this.setOutput( data.outputLength );

		if ( data.properties !== undefined ) {

			for ( const { id, property } of data.properties ) {

				data.objects[ id ] = this.getInputByProperty( property );

			}

		} else if ( data.inputs !== undefined ) {

			const inputs = this.inputs;

			if ( inputs.length > 0 ) {

				let index = 0;

				for ( const id of data.inputs ) {

					data.objects[ id ] = inputs[ index ++ ];

				}

			} else {

				for ( const id of data.inputs ) {

					this.add( data.objects[ id ] );

				}

			}

		}

		if ( data.links !== undefined ) {

			for ( const id of data.links ) {

				this.connect( data.objects[ id ] );

			}

		}

		if ( data.style !== undefined ) {

			this.setStyle( data.style );

		}

		if ( data.height !== undefined ) {

			this.setHeight( data.height );

		}

	}
```
</details>

##### `getLinkedObject(output: any): any`

<details><summary>Code</summary>

```ts
getLinkedObject( output = null ) {

		const linkedElement = this.getLinkedElement();

		return linkedElement ? linkedElement.getObject( output ) : null;

	}
```
</details>

##### `getLinkedElement(): any`

<details><summary>Code</summary>

```ts
getLinkedElement() {

		const link = this.getLink();

		return link ? link.outputElement : null;

	}
```
</details>

##### `getLink(): any`

<details><summary>Code</summary>

```ts
getLink() {

		return this.links[ 0 ];

	}
```
</details>

##### `_createIO(type: any): HTMLElement`

<details><summary>Code</summary>

```ts
_createIO( type ) {

		const { dom } = this;

		const ioDOM = document.createElement( 'f-io' );
		ioDOM.style.visibility = 'hidden';
		ioDOM.className = type;

		const onConnectEvent = ( e ) => {

			e.preventDefault();

			e.stopPropagation();

			selected = null;

			const nodeDOM = this.node.dom;

			nodeDOM.classList.add( 'io-connect' );

			ioDOM.classList.add( 'connect' );
			dom.classList.add( 'select' );

			const defaultOutput = Link.InputDirection === 'left' ? 'lio' : 'rio';

			const link = type === defaultOutput ? new Link( this ) : new Link( null, this );
			const previewLink = new Link( link.inputElement, link.outputElement );

			this.links.push( link );

			draggableDOM( e, ( data ) => {

				if ( previewLink.outputElement )
					previewLink.outputElement.dom.classList.remove( 'invalid' );

				if ( previewLink.inputElement )
					previewLink.inputElement.dom.classList.remove( 'invalid' );

				previewLink.inputElement = link.inputElement;
				previewLink.outputElement = link.outputElement;

				if ( type === defaultOutput ) {

					previewLink.outputElement = selected;

				} else {

					previewLink.inputElement = selected;

				}

				const isInvalid = previewLink.inputElement !== null && previewLink.outputElement !== null &&
					previewLink.inputElement.inputLength > 0 && previewLink.outputElement.outputLength > 0 &&
					dispatchEventList( previewLink.inputElement.events.valid, previewLink.inputElement, previewLink.outputElement, data.dragging ? 'dragging' : 'dragged' ) === false;

				if ( data.dragging && isInvalid ) {

					if ( type === defaultOutput ) {

						if ( previewLink.outputElement )
							previewLink.outputElement.dom.classList.add( 'invalid' );

					} else {

						if ( previewLink.inputElement )
							previewLink.inputElement.dom.classList.add( 'invalid' );

					}

					return;

				}

				if ( ! data.dragging ) {

					nodeDOM.classList.remove( 'io-connect' );

					ioDOM.classList.remove( 'connect' );
					dom.classList.remove( 'select' );

					this.links.splice( this.links.indexOf( link ), 1 );

					if ( selected !== null && ! isInvalid ) {

						link.inputElement = previewLink.inputElement;
						link.outputElement = previewLink.outputElement;

						// check if is an is circular link

						if ( link.outputElement.node.isCircular( link.inputElement.node ) ) {

							return;

						}

						//

						if ( link.inputElement.inputLength > 0 && link.outputElement.outputLength > 0 ) {

							link.inputElement.connect( link.outputElement );

						}

					}

				}

			}, { className: 'connecting' } );

		};

		ioDOM.addEventListener( 'mousedown', onConnectEvent, true );
		ioDOM.addEventListener( 'touchstart', onConnectEvent, true );

		return ioDOM;

	}
```
</details>

### `Input`

<details><summary>Class Code</summary>

```ts
class Input extends Serializer {

	static get type() {

		return 'Input';

	}

	constructor( dom ) {

		super();

		this.dom = dom;

		this.element = null;

		this.extra = null;

		this.tagColor = null;

		this.property = null;

		this.events = {
			'change': [],
			'click': []
		};

		this.addEventListener( 'change', ( ) => {

			dispatchEventList( this.events.change, this );

		} );

		this.addEventListener( 'click', ( ) => {

			dispatchEventList( this.events.click, this );

		} );

	}

	setExtra( value ) {

		this.extra = value;

		return this;

	}

	getExtra() {

		return this.extra;

	}

	setProperty( name ) {

		this.property = name;

		return this;

	}

	getProperty() {

		return this.property;

	}

	setTagColor( color ) {

		this.tagColor = color;

		this.dom.style[ 'border-left' ] = `2px solid ${color}`;

		return this;

	}

	getTagColor() {

		return this.tagColor;

	}

	setToolTip( text ) {

		const div = document.createElement( 'f-tooltip' );
		div.innerText = text;

		this.dom.append( div );

		return this;

	}

	onChange( callback ) {

		this.events.change.push( callback );

		return this;

	}

	onClick( callback ) {

		this.events.click.push( callback );

		return this;

	}

	setReadOnly( value ) {

		this.getInput().readOnly = value;

		return this;

	}

	getReadOnly() {

		return this.getInput().readOnly;

	}

	setValue( value, dispatch = true ) {

		this.getInput().value = value;

		if ( dispatch ) this.dispatchEvent( new Event( 'change' ) );

		return this;

	}

	getValue() {

		return this.getInput().value;

	}

	getInput() {

		return this.dom;

	}

	serialize( data ) {

		data.value = this.getValue();

	}

	deserialize( data ) {

		this.setValue( data.value );

	}

}
```
</details>

#### Methods

##### `setExtra(value: any): this`

<details><summary>Code</summary>

```ts
setExtra( value ) {

		this.extra = value;

		return this;

	}
```
</details>

##### `getExtra(): any`

<details><summary>Code</summary>

```ts
getExtra() {

		return this.extra;

	}
```
</details>

##### `setProperty(name: any): this`

<details><summary>Code</summary>

```ts
setProperty( name ) {

		this.property = name;

		return this;

	}
```
</details>

##### `getProperty(): any`

<details><summary>Code</summary>

```ts
getProperty() {

		return this.property;

	}
```
</details>

##### `setTagColor(color: any): this`

<details><summary>Code</summary>

```ts
setTagColor( color ) {

		this.tagColor = color;

		this.dom.style[ 'border-left' ] = `2px solid ${color}`;

		return this;

	}
```
</details>

##### `getTagColor(): any`

<details><summary>Code</summary>

```ts
getTagColor() {

		return this.tagColor;

	}
```
</details>

##### `setToolTip(text: any): this`

<details><summary>Code</summary>

```ts
setToolTip( text ) {

		const div = document.createElement( 'f-tooltip' );
		div.innerText = text;

		this.dom.append( div );

		return this;

	}
```
</details>

##### `onChange(callback: any): this`

<details><summary>Code</summary>

```ts
onChange( callback ) {

		this.events.change.push( callback );

		return this;

	}
```
</details>

##### `onClick(callback: any): this`

<details><summary>Code</summary>

```ts
onClick( callback ) {

		this.events.click.push( callback );

		return this;

	}
```
</details>

##### `setReadOnly(value: any): this`

<details><summary>Code</summary>

```ts
setReadOnly( value ) {

		this.getInput().readOnly = value;

		return this;

	}
```
</details>

##### `getReadOnly(): any`

<details><summary>Code</summary>

```ts
getReadOnly() {

		return this.getInput().readOnly;

	}
```
</details>

##### `setValue(value: any, dispatch: boolean): this`

<details><summary>Code</summary>

```ts
setValue( value, dispatch = true ) {

		this.getInput().value = value;

		if ( dispatch ) this.dispatchEvent( new Event( 'change' ) );

		return this;

	}
```
</details>

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.getInput().value;

	}
```
</details>

##### `getInput(): any`

<details><summary>Code</summary>

```ts
getInput() {

		return this.dom;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		data.value = this.getValue();

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		this.setValue( data.value );

	}
```
</details>

### `Node`

<details><summary>Class Code</summary>

```ts
class Node extends Serializer {

	static get type() {

		return 'Node';

	}

	constructor() {

		super();

		const dom = document.createElement( 'f-node' );

		const onDown = () => {

			const canvas = this.canvas;

			if ( canvas !== null ) {

				canvas.select( this );

			}

		};

		dom.addEventListener( 'mousedown', onDown, true );
		dom.addEventListener( 'touchstart', onDown, true );

		this._onConnect = ( e ) => {

			const { target } = e;

			for ( const element of this.elements ) {

				if ( element !== target ) {

					element.dispatchEvent( new Event( 'nodeConnect' ) );

				}

			}

		};

		this._onConnectChildren = ( e ) => {

			const { target } = e;

			for ( const element of this.elements ) {

				if ( element !== target ) {

					element.dispatchEvent( new Event( 'nodeConnectChildren' ) );

				}

			}

		};

		this.dom = dom;

		this.style = '';

		this.canvas = null;
		this.resizable = false;
		this.serializePriority = 0;

		this.elements = [];

		this.events = {
			'focus': [],
			'blur': []
		};

		this.setWidth( 300 ).setPosition( 0, 0 );

	}

	get baseElement() {

		return this.elements[ 0 ];

	}

	setAlign( align ) {

		const dom = this.dom;
		const style = dom.style;

		style.left = '';
		style.top = '';
		style.animation = 'none';

		if ( typeof align === 'string' ) {

			dom.classList.add( align );

		} else if ( align ) {

			for ( const name in align ) {

				style[ name ] = align[ name ];

			}

		}

		return this;

	}

	setResizable( val ) {

		this.resizable = val === true;

		if ( this.resizable ) {

			this.dom.classList.add( 'resizable' );

		} else {

			this.dom.classList.remove( 'resizable' );

		}

		this.updateSize();

		return this;

	}

	onFocus( callback ) {

		this.events.focus.push( callback );

		return this;

	}

	onBlur( callback ) {

		this.events.blur.push( callback );

		return this;

	}

	setStyle( style ) {

		const dom = this.dom;

		if ( this.style ) dom.classList.remove( this.style );

		if ( style ) dom.classList.add( style );

		this.style = style;

		return this;

	}

	setPosition( x, y ) {

		const dom = this.dom;

		dom.style.left = numberToPX( x );
		dom.style.top = numberToPX( y );

		return this;

	}

	getPosition() {

		const dom = this.dom;

		return {
			x: parseInt( dom.style.left ),
			y: parseInt( dom.style.top )
		};

	}

	setWidth( val ) {

		this.dom.style.width = numberToPX( val );

		this.updateSize();

		return this;

	}

	getWidth() {

		return parseInt( this.dom.style.width );

	}

	getHeight() {

		return this.dom.offsetHeight;

	}

	getBound() {

		const { x, y } = this.getPosition();
		const { width, height } = this.dom.getBoundingClientRect();

		return { x, y, width, height };

	}

	add( element ) {

		this.elements.push( element );

		element.node = this;
		element.addEventListener( 'connect', this._onConnect );
		element.addEventListener( 'connectChildren', this._onConnectChildren );

		this.dom.append( element.dom );

		this.updateSize();

		return this;

	}

	remove( element ) {

		this.elements.splice( this.elements.indexOf( element ), 1 );

		element.node = null;
		element.removeEventListener( 'connect', this._onConnect );
		element.removeEventListener( 'connectChildren', this._onConnectChildren );

		this.dom.removeChild( element.dom );

		this.updateSize();

		return this;

	}

	dispose() {

		const canvas = this.canvas;

		if ( canvas !== null ) canvas.remove( this );

		for ( const element of this.elements ) {

			element.dispose();

		}

		this.dispatchEvent( new Event( 'dispose' ) );

	}

	isCircular( node ) {

		if ( node === this ) return true;

		const links = this.getLinks();

		for ( const link of links ) {

			if ( link.outputElement.node.isCircular( node ) ) {

				return true;

			}

		}

		return false;

	}

	getLinks() {

		const links = [];

		for ( const element of this.elements ) {

			links.push( ...element.links );

		}

		return links;

	}

	getColor() {

		return this.elements.length > 0 ? this.elements[ 0 ].getColor() : null;

	}

	updateSize() {

		for ( const element of this.elements ) {

			element.dom.style.width = '';

		}

		if ( this.resizable === true ) {

			const element = this.elements[ this.elements.length - 1 ];

			if ( element !== undefined ) {

				element.dom.style.width = this.dom.style.width;

			}

		}

	}

	serialize( data ) {

		const { x, y } = this.getPosition();

		const elements = [];

		for ( const element of this.elements ) {

			elements.push( element.toJSON( data ).id );

		}

		data.x = x;
		data.y = y;
		data.width = this.getWidth();
		data.elements = elements;
		data.autoResize = this.resizable;

		if ( this.style !== '' ) {

			data.style = this.style;

		}

	}

	deserialize( data ) {

		this.setPosition( data.x, data.y );
		this.setWidth( data.width );
		this.setResizable( data.autoResize );

		if ( data.style !== undefined ) {

			this.setStyle( data.style );

		}

		const elements = this.elements;

		if ( elements.length > 0 ) {

			let index = 0;

			for ( const id of data.elements ) {

				data.objects[ id ] = elements[ index ++ ];

			}

		} else {

			for ( const id of data.elements ) {

				this.add( data.objects[ id ] );

			}

		}

	}

}
```
</details>

#### Methods

##### `setAlign(align: any): this`

<details><summary>Code</summary>

```ts
setAlign( align ) {

		const dom = this.dom;
		const style = dom.style;

		style.left = '';
		style.top = '';
		style.animation = 'none';

		if ( typeof align === 'string' ) {

			dom.classList.add( align );

		} else if ( align ) {

			for ( const name in align ) {

				style[ name ] = align[ name ];

			}

		}

		return this;

	}
```
</details>

##### `setResizable(val: any): this`

<details><summary>Code</summary>

```ts
setResizable( val ) {

		this.resizable = val === true;

		if ( this.resizable ) {

			this.dom.classList.add( 'resizable' );

		} else {

			this.dom.classList.remove( 'resizable' );

		}

		this.updateSize();

		return this;

	}
```
</details>

##### `onFocus(callback: any): this`

<details><summary>Code</summary>

```ts
onFocus( callback ) {

		this.events.focus.push( callback );

		return this;

	}
```
</details>

##### `onBlur(callback: any): this`

<details><summary>Code</summary>

```ts
onBlur( callback ) {

		this.events.blur.push( callback );

		return this;

	}
```
</details>

##### `setStyle(style: any): this`

<details><summary>Code</summary>

```ts
setStyle( style ) {

		const dom = this.dom;

		if ( this.style ) dom.classList.remove( this.style );

		if ( style ) dom.classList.add( style );

		this.style = style;

		return this;

	}
```
</details>

##### `setPosition(x: any, y: any): this`

<details><summary>Code</summary>

```ts
setPosition( x, y ) {

		const dom = this.dom;

		dom.style.left = numberToPX( x );
		dom.style.top = numberToPX( y );

		return this;

	}
```
</details>

##### `getPosition(): { x: number; y: number; }`

<details><summary>Code</summary>

```ts
getPosition() {

		const dom = this.dom;

		return {
			x: parseInt( dom.style.left ),
			y: parseInt( dom.style.top )
		};

	}
```
</details>

##### `setWidth(val: any): this`

<details><summary>Code</summary>

```ts
setWidth( val ) {

		this.dom.style.width = numberToPX( val );

		this.updateSize();

		return this;

	}
```
</details>

##### `getWidth(): number`

<details><summary>Code</summary>

```ts
getWidth() {

		return parseInt( this.dom.style.width );

	}
```
</details>

##### `getHeight(): number`

<details><summary>Code</summary>

```ts
getHeight() {

		return this.dom.offsetHeight;

	}
```
</details>

##### `getBound(): { x: number; y: number; width: number; height: number; }`

<details><summary>Code</summary>

```ts
getBound() {

		const { x, y } = this.getPosition();
		const { width, height } = this.dom.getBoundingClientRect();

		return { x, y, width, height };

	}
```
</details>

##### `add(element: any): this`

<details><summary>Code</summary>

```ts
add( element ) {

		this.elements.push( element );

		element.node = this;
		element.addEventListener( 'connect', this._onConnect );
		element.addEventListener( 'connectChildren', this._onConnectChildren );

		this.dom.append( element.dom );

		this.updateSize();

		return this;

	}
```
</details>

##### `remove(element: any): this`

<details><summary>Code</summary>

```ts
remove( element ) {

		this.elements.splice( this.elements.indexOf( element ), 1 );

		element.node = null;
		element.removeEventListener( 'connect', this._onConnect );
		element.removeEventListener( 'connectChildren', this._onConnectChildren );

		this.dom.removeChild( element.dom );

		this.updateSize();

		return this;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		const canvas = this.canvas;

		if ( canvas !== null ) canvas.remove( this );

		for ( const element of this.elements ) {

			element.dispose();

		}

		this.dispatchEvent( new Event( 'dispose' ) );

	}
```
</details>

##### `isCircular(node: any): boolean`

<details><summary>Code</summary>

```ts
isCircular( node ) {

		if ( node === this ) return true;

		const links = this.getLinks();

		for ( const link of links ) {

			if ( link.outputElement.node.isCircular( node ) ) {

				return true;

			}

		}

		return false;

	}
```
</details>

##### `getLinks(): any[]`

<details><summary>Code</summary>

```ts
getLinks() {

		const links = [];

		for ( const element of this.elements ) {

			links.push( ...element.links );

		}

		return links;

	}
```
</details>

##### `getColor(): any`

<details><summary>Code</summary>

```ts
getColor() {

		return this.elements.length > 0 ? this.elements[ 0 ].getColor() : null;

	}
```
</details>

##### `updateSize(): void`

<details><summary>Code</summary>

```ts
updateSize() {

		for ( const element of this.elements ) {

			element.dom.style.width = '';

		}

		if ( this.resizable === true ) {

			const element = this.elements[ this.elements.length - 1 ];

			if ( element !== undefined ) {

				element.dom.style.width = this.dom.style.width;

			}

		}

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		const { x, y } = this.getPosition();

		const elements = [];

		for ( const element of this.elements ) {

			elements.push( element.toJSON( data ).id );

		}

		data.x = x;
		data.y = y;
		data.width = this.getWidth();
		data.elements = elements;
		data.autoResize = this.resizable;

		if ( this.style !== '' ) {

			data.style = this.style;

		}

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		this.setPosition( data.x, data.y );
		this.setWidth( data.width );
		this.setResizable( data.autoResize );

		if ( data.style !== undefined ) {

			this.setStyle( data.style );

		}

		const elements = this.elements;

		if ( elements.length > 0 ) {

			let index = 0;

			for ( const id of data.elements ) {

				data.objects[ id ] = elements[ index ++ ];

			}

		} else {

			for ( const id of data.elements ) {

				this.add( data.objects[ id ] );

			}

		}

	}
```
</details>

### `DraggableElement`

<details><summary>Class Code</summary>

```ts
class DraggableElement extends Element {

	static get type() {

		return 'DraggableElement';

	}

	constructor( draggable = true ) {

		super( true );

		this.draggable = draggable;

		const onDrag = ( e ) => {

			e.preventDefault();

			if ( this.draggable === true ) {

				draggableDOM( this.node.dom, null, { className: 'dragging node' } );

			}

		};

		const { dom } = this;

		dom.addEventListener( 'mousedown', onDrag, true );
		dom.addEventListener( 'touchstart', onDrag, true );

	}

}
```
</details>

### `TitleElement`

<details><summary>Class Code</summary>

```ts
class TitleElement extends DraggableElement {

	static get type() {

		return 'TitleElement';

	}

	constructor( title, draggable = true ) {

		super( draggable );

		const { dom } = this;

		dom.classList.add( 'title' );

		const dbClick = () => {

			this.node.canvas.focusSelected = ! this.node.canvas.focusSelected;

		};

		dom.addEventListener( 'dblclick', dbClick );

		const titleDOM = document.createElement( 'f-title' );
		titleDOM.innerText = title;

		const iconDOM = document.createElement( 'i' );

		const toolbarDOM = document.createElement( 'f-toolbar' );

		this.buttons = [];

		this.titleDOM = titleDOM;
		this.iconDOM = iconDOM;
		this.toolbarDOM = toolbarDOM;

		dom.append( titleDOM );
		dom.append( iconDOM );
		dom.append( toolbarDOM );

	}

	setIcon( value ) {

		this.iconDOM.className = value;

		return this;

	}

	getIcon() {

		return this.iconDOM.className;

	}

	setTitle( value ) {

		this.titleDOM.innerText = value;

		return this;

	}

	getTitle() {

		return this.titleDOM.innerText;

	}

	addButton( button ) {

		this.buttons.push( button );

		this.toolbarDOM.append( button.dom );

		return this;

	}

	serialize( data ) {

		super.serialize( data );

		const title = this.getTitle();
		const icon = this.getIcon();

		data.title = title;

		if ( icon !== '' ) {

			data.icon = icon;

		}

	}

	deserialize( data ) {

		super.deserialize( data );

		this.setTitle( data.title );

		if ( data.icon !== undefined ) {

			this.setIcon( data.icon );

		}

	}

}
```
</details>

#### Methods

##### `setIcon(value: any): this`

<details><summary>Code</summary>

```ts
setIcon( value ) {

		this.iconDOM.className = value;

		return this;

	}
```
</details>

##### `getIcon(): string`

<details><summary>Code</summary>

```ts
getIcon() {

		return this.iconDOM.className;

	}
```
</details>

##### `setTitle(value: any): this`

<details><summary>Code</summary>

```ts
setTitle( value ) {

		this.titleDOM.innerText = value;

		return this;

	}
```
</details>

##### `getTitle(): string`

<details><summary>Code</summary>

```ts
getTitle() {

		return this.titleDOM.innerText;

	}
```
</details>

##### `addButton(button: any): this`

<details><summary>Code</summary>

```ts
addButton( button ) {

		this.buttons.push( button );

		this.toolbarDOM.append( button.dom );

		return this;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		const title = this.getTitle();
		const icon = this.getIcon();

		data.title = title;

		if ( icon !== '' ) {

			data.icon = icon;

		}

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.setTitle( data.title );

		if ( data.icon !== undefined ) {

			this.setIcon( data.icon );

		}

	}
```
</details>

### `Canvas`

<details><summary>Class Code</summary>

```ts
class Canvas extends Serializer {

	static get type() {

		return 'Canvas';

	}

	constructor() {

		super();

		const dom = document.createElement( 'f-canvas' );
		const contentDOM = document.createElement( 'f-content' );
		const areaDOM = document.createElement( 'f-area' );
		const dropDOM = document.createElement( 'f-drop' );

		const canvas = document.createElement( 'canvas' );
		const frontCanvas = document.createElement( 'canvas' );
		const mapCanvas = document.createElement( 'canvas' );

		const context = canvas.getContext( '2d' );
		const frontContext = frontCanvas.getContext( '2d' );
		const mapContext = mapCanvas.getContext( '2d' );

		this.dom = dom;

		this.contentDOM = contentDOM;
		this.areaDOM = areaDOM;
		this.dropDOM = dropDOM;

		this.canvas = canvas;
		this.frontCanvas = frontCanvas;
		this.mapCanvas = mapCanvas;

		this.context = context;
		this.frontContext = frontContext;
		this.mapContext = mapContext;

		this.clientX = 0;
		this.clientY = 0;

		this.relativeClientX = 0;
		this.relativeClientY = 0;

		this.nodes = [];

		this.selected = null;

		this.updating = false;

		this.droppedItems = [];

		this.events = {
			'drop': []
		};

		this._scrollLeft = 0;
		this._scrollTop = 0;
		this._zoom = 1;
		this._width = 0;
		this._height = 0;
		this._focusSelected = false;
		this._mapInfo = {
			scale: 1,
			screen: {}
		};

		canvas.className = 'background';
		frontCanvas.className = 'frontground';
		mapCanvas.className = 'map';

		dropDOM.innerHTML = '<span>drop your file</span>';

		dom.append( dropDOM );
		dom.append( canvas );
		dom.append( frontCanvas );
		dom.append( contentDOM );
		dom.append( areaDOM );
		dom.append( mapCanvas );

		const zoomTo = ( zoom, clientX = this.clientX, clientY = this.clientY ) => {

			zoom = Math.min( Math.max( zoom, .2 ), 1 );

			this.scrollLeft -= ( clientX / this.zoom ) - ( clientX / zoom );
			this.scrollTop -= ( clientY / this.zoom ) - ( clientY / zoom );
			this.zoom = zoom;

		};

		let touchData = null;

		const onTouchStart = () => {

			touchData = null;

		};

		const classInElements = ( element, className ) => {

			do {

				if ( element.classList ? element.classList.contains( className ) : false ) {

					return true;

				}

			} while ( ( element = element.parentElement ) && element !== dom );

			return false;

		};

		const onMouseZoom = ( e ) => {

			if ( classInElements( e.srcElement, 'f-scroll' ) ) return;

			e.preventDefault();

			e.stopImmediatePropagation();

			const delta = e.deltaY * .003;

			zoomTo( this.zoom - delta );

		};

		const onTouchZoom = ( e ) => {

			if ( e.touches && e.touches.length === 2 ) {

				e.preventDefault();

				e.stopImmediatePropagation();

				const clientX = ( e.touches[ 0 ].clientX + e.touches[ 1 ].clientX ) / 2;
				const clientY = ( e.touches[ 0 ].clientY + e.touches[ 1 ].clientY ) / 2;

				const distance = Math.hypot(
					e.touches[ 0 ].clientX - e.touches[ 1 ].clientX,
					e.touches[ 0 ].clientY - e.touches[ 1 ].clientY
				);

				if ( touchData === null ) {

					touchData = {
						distance
					};

				}

				const delta = ( touchData.distance - distance ) * .003;
				touchData.distance = distance;

				zoomTo( this.zoom - delta, clientX, clientY );

			}

		};

		const onTouchMove = ( e ) => {

			if ( e.touches && e.touches.length === 1 ) {

				e.preventDefault();

				e.stopImmediatePropagation();

				const clientX = e.touches[ 0 ].clientX;
				const clientY = e.touches[ 0 ].clientY;

				if ( touchData === null ) {

					const { scrollLeft, scrollTop } = this;

					touchData = {
						scrollLeft,
						scrollTop,
						clientX,
						clientY
					};

				}

				const zoom = this.zoom;

				this.scrollLeft = touchData.scrollLeft + ( ( clientX - touchData.clientX ) / zoom );
				this.scrollTop = touchData.scrollTop + ( ( clientY - touchData.clientY ) / zoom );

			}

		};

		dom.addEventListener( 'wheel', onMouseZoom );
		dom.addEventListener( 'touchmove', onTouchZoom );
		dom.addEventListener( 'touchstart', onTouchStart );
		canvas.addEventListener( 'touchmove', onTouchMove );

		let dropEnterCount = 0;

		const dragState = ( enter ) => {

			if ( enter ) {

				if ( dropEnterCount ++ === 0 ) {

					this.droppedItems = [];

					dropDOM.classList.add( 'visible' );

					this.add( dropNode );

				}

			} else if ( -- dropEnterCount === 0 ) {

				dropDOM.classList.remove( 'visible' );

				this.remove( dropNode );

			}

		};

		dom.addEventListener( 'dragenter', () => {

 			dragState( true );

		} );

		dom.addEventListener( 'dragleave', () => {

			dragState( false );

		} );

		dom.addEventListener( 'dragover', ( e ) => {

			e.preventDefault();

			const { relativeClientX, relativeClientY } = this;

			const centerNodeX = dropNode.getWidth() / 2;

			dropNode.setPosition( relativeClientX - centerNodeX, relativeClientY - 20 );

		} );

		dom.addEventListener( 'drop', ( e ) => {

			e.preventDefault();

			dragState( false );

			this.droppedItems = e.dataTransfer.items;

			dispatchEventList( this.events.drop, this );

		} );

		draggableDOM( dom, ( data ) => {

			const { delta, isTouch } = data;

			if ( ! isTouch ) {

				if ( data.scrollTop === undefined ) {

					data.scrollLeft = this.scrollLeft;
					data.scrollTop = this.scrollTop;

				}

				const zoom = this.zoom;

				this.scrollLeft = data.scrollLeft + ( delta.x / zoom );
				this.scrollTop = data.scrollTop + ( delta.y / zoom );

			}

			if ( data.dragging ) {

				dom.classList.add( 'grabbing' );

			} else {

				dom.classList.remove( 'grabbing' );

			}

		}, { className: 'dragging-canvas' } );


		draggableDOM( mapCanvas, ( data ) => {

			const { scale, screen } = this._mapInfo;

			if ( data.scrollLeft === undefined ) {

				const rect = this.mapCanvas.getBoundingClientRect();

				const clientMapX = data.client.x - rect.left;
				const clientMapY = data.client.y - rect.top;

				const overMapScreen =
					clientMapX > screen.x && clientMapY > screen.y &&
					clientMapX < screen.x + screen.width && clientMapY < screen.y + screen.height;

				if ( overMapScreen === false ) {

					const scaleX = this._mapInfo.width / this.mapCanvas.width;

					let scrollLeft = - this._mapInfo.left - ( clientMapX * scaleX );
					let scrollTop = - this._mapInfo.top - ( clientMapY * ( this._mapInfo.height / this.mapCanvas.height ) );

					scrollLeft += ( screen.width / 2 ) / scale;
					scrollTop += ( screen.height / 2 ) / scale;

					this.scrollLeft = scrollLeft;
					this.scrollTop = scrollTop;

				}

				data.scrollLeft = this.scrollLeft;
				data.scrollTop = this.scrollTop;

			}

			this.scrollLeft = data.scrollLeft - ( data.delta.x / scale );
			this.scrollTop = data.scrollTop - ( data.delta.y / scale );

		}, { click: true } );

		this._onMoveEvent = ( e ) => {

			const event = e.touches ? e.touches[ 0 ] : e;
			const { zoom, rect } = this;

			this.clientX = event.clientX;
			this.clientY = event.clientY;

			const rectClientX = ( this.clientX - rect.left ) / zoom;
			const rectClientY = ( this.clientY - rect.top ) / zoom;

			this.relativeClientX = rectClientX - this.scrollLeft;
			this.relativeClientY = rectClientY - this.scrollTop;

		};

		this._onUpdate = () => {

			this.update();

		};

		this.start();

	}

	getBounds() {

		const bounds = { x: Infinity, y: Infinity, width: - Infinity, height: - Infinity };

		for ( const node of this.nodes ) {

			const { x, y, width, height } = node.getBound();

			bounds.x = Math.min( bounds.x, x );
			bounds.y = Math.min( bounds.y, y );
			bounds.width = Math.max( bounds.width, x + width );
			bounds.height = Math.max( bounds.height, y + height );

		}

		bounds.x = Math.round( bounds.x );
		bounds.y = Math.round( bounds.y );
		bounds.width = Math.round( bounds.width );
		bounds.height = Math.round( bounds.height );

		return bounds;

	}

	get width() {

		return this._width;

	}

	get height() {

		return this._height;

	}

	get rect() {

		return this.dom.getBoundingClientRect();

	}

	get zoom() {

		return this._zoom;

	}

	set zoom( val ) {

		this._zoom = val;
		this.contentDOM.style.zoom = val;

		val === 1 ? this.dom.classList.remove( 'zoom' ) : this.dom.classList.add( 'zoom' );

		this.updateMozTransform();

	}

	set scrollLeft( val ) {

		this._scrollLeft = val;
		this.contentDOM.style.left = numberToPX( val );

		this.updateMozTransform();

	}

	get scrollLeft() {

		return this._scrollLeft;

	}

	set scrollTop( val ) {

		this._scrollTop = val;
		this.contentDOM.style.top = numberToPX( val );

		this.updateMozTransform();

	}

	get scrollTop() {

		return this._scrollTop;

	}

	set focusSelected( value ) {

		if ( this._focusSelected === value ) return;

		const classList = this.dom.classList;

		this._focusSelected = value;

		if ( value ) {

			classList.add( 'focusing' );

		} else {

			classList.remove( 'focusing' );

		}

	}

	get focusSelected() {

		return this._focusSelected;

	}

	get useTransform() {

		const userAgent = navigator.userAgent;
		const isSafari = /Safari/.test( userAgent ) && ! /Chrome/.test( userAgent );

		return ! isSafari;

	}

	updateMozTransform() {

		if ( this.useTransform === false ) return;

		this.contentDOM.style[ '-moz-transform' ] = 'scale(' + this.zoom + ')';
		this.contentDOM.style[ '-moz-transform-origin' ] = '-' + this.contentDOM.style.left + ' -' + this.contentDOM.style.top;

	}

	onDrop( callback ) {

		this.events.drop.push( callback );

		return this;

	}

	start() {

		this.updating = true;

		document.addEventListener( 'wheel', this._onMoveEvent, true );

		document.addEventListener( 'mousedown', this._onMoveEvent, true );
		document.addEventListener( 'touchstart', this._onMoveEvent, true );

		document.addEventListener( 'mousemove', this._onMoveEvent, true );
		document.addEventListener( 'touchmove', this._onMoveEvent, true );

		document.addEventListener( 'dragover', this._onMoveEvent, true );

		requestAnimationFrame( this._onUpdate );

	}

	stop() {

		this.updating = false;

		document.removeEventListener( 'wheel', this._onMoveEvent, true );

		document.removeEventListener( 'mousedown', this._onMoveEvent, true );
		document.removeEventListener( 'touchstart', this._onMoveEvent, true );

		document.removeEventListener( 'mousemove', this._onMoveEvent, true );
		document.removeEventListener( 'touchmove', this._onMoveEvent, true );

		document.removeEventListener( 'dragover', this._onMoveEvent, true );

	}

	add( node ) {

		if ( node.canvas === this ) return;

		this.nodes.push( node );

		node.canvas = this;

		this.contentDOM.append( node.dom );

		return this;

	}

	remove( node ) {

		if ( node === this.selected ) {

			this.select();

		}

		this.unlink( node );

		const nodes = this.nodes;

		nodes.splice( nodes.indexOf( node ), 1 );

		node.canvas = null;

		this.contentDOM.removeChild( node.dom );

		node.dispatchEvent( new Event( 'remove' ) );

		return this;

	}

	clear() {

		const nodes = this.nodes;

		while ( nodes.length > 0 ) {

			this.remove( nodes[ 0 ] );

		}

		return this;

	}

	unlink( node ) {

		const links = this.getLinks();

		for ( const link of links ) {

			if ( link.inputElement && link.outputElement ) {

				if ( link.inputElement.node === node ) {

					link.inputElement.connect();

				} else if ( link.outputElement.node === node ) {

					link.inputElement.connect();

				}

			}

		}

	}

	getLinks() {

		const links = [];

		for ( const node of this.nodes ) {

			links.push( ...node.getLinks() );

		}

		return links;

	}

	centralize() {

		const bounds = this.getBounds();

		this.scrollLeft = ( this.canvas.width / 2 ) - ( ( - bounds.x + bounds.width ) / 2 );
		this.scrollTop = ( this.canvas.height / 2 ) - ( ( - bounds.y + bounds.height ) / 2 );

		return this;

	}

	setSize( width, height ) {

		this._width = width;
		this._height = height;

		this.update();

		return this;

	}

	select( node = null ) {

		if ( node === this.selected ) return;

		const previousNode = this.selected;

		if ( previousNode !== null ) {

			this.focusSelected = false;

			previousNode.dom.classList.remove( 'selected' );

			this.selected = null;

			dispatchEventList( previousNode.events.blur, previousNode );

		}

		if ( node !== null ) {

			node.dom.classList.add( 'selected' );

			this.selected = node;

			dispatchEventList( node.events.focus, node );

		}

	}

	updateMap() {

		const { nodes, mapCanvas, mapContext, scrollLeft, scrollTop, canvas, zoom, _mapInfo } = this;

		const bounds = this.getBounds();

		mapCanvas.width = 300;
		mapCanvas.height = 200;

		mapContext.clearRect( 0, 0, mapCanvas.width, mapCanvas.height );

		mapContext.fillStyle = 'rgba( 0, 0, 0, 0 )';
		mapContext.fillRect( 0, 0, mapCanvas.width, mapCanvas.height );

		const boundsWidth = - bounds.x + bounds.width;
		const boundsHeight = - bounds.y + bounds.height;

		const mapScale = Math.min( mapCanvas.width / boundsWidth, mapCanvas.height / boundsHeight ) * .5;

		const boundsMapWidth = boundsWidth * mapScale;
		const boundsMapHeight = boundsHeight * mapScale;

		const boundsOffsetX = ( mapCanvas.width / 2 ) - ( boundsMapWidth / 2 );
		const boundsOffsetY = ( mapCanvas.height / 2 ) - ( boundsMapHeight / 2 );

		let selectedNode = null;

		for ( const node of nodes ) {

			const nodeBound = node.getBound();
			const nodeColor = node.getColor();

			nodeBound.x += - bounds.x;
			nodeBound.y += - bounds.y;

			nodeBound.x *= mapScale;
			nodeBound.y *= mapScale;
			nodeBound.width *= mapScale;
			nodeBound.height *= mapScale;

			nodeBound.x += boundsOffsetX;
			nodeBound.y += boundsOffsetY;

			if ( node !== this.selected ) {

				mapContext.fillStyle = nodeColor;
				mapContext.fillRect( nodeBound.x, nodeBound.y, nodeBound.width, nodeBound.height );

			} else {

				selectedNode = {
					nodeBound,
					nodeColor
				};

			}

		}

		if ( selectedNode !== null ) {

			const { nodeBound, nodeColor } = selectedNode;

			mapContext.fillStyle = nodeColor;
			mapContext.fillRect( nodeBound.x, nodeBound.y, nodeBound.width, nodeBound.height );

		}

		const screenMapX = ( - ( scrollLeft + bounds.x ) * mapScale ) + boundsOffsetX;
		const screenMapY = ( - ( scrollTop + bounds.y ) * mapScale ) + boundsOffsetY;
		const screenMapWidth = ( canvas.width * mapScale ) / zoom;
		const screenMapHeight = ( canvas.height * mapScale ) / zoom;

		mapContext.fillStyle = 'rgba( 200, 200, 200, 0.1 )';
		mapContext.fillRect( screenMapX, screenMapY, screenMapWidth, screenMapHeight );

		//

		_mapInfo.scale = mapScale;
		_mapInfo.left = ( - boundsOffsetX / mapScale ) + bounds.x;
		_mapInfo.top = ( - boundsOffsetY / mapScale ) + bounds.y;
		_mapInfo.width = mapCanvas.width / mapScale;
		_mapInfo.height = mapCanvas.height / mapScale;
		_mapInfo.screen.x = screenMapX;
		_mapInfo.screen.y = screenMapY;
		_mapInfo.screen.width = screenMapWidth;
		_mapInfo.screen.height = screenMapHeight;

	}

	updateLines() {

		const { dom, zoom, canvas, frontCanvas, frontContext, context, _width, _height, useTransform } = this;

		const domRect = this.rect;

		if ( canvas.width !== _width || canvas.height !== _height ) {

			canvas.width = _width;
			canvas.height = _height;

			frontCanvas.width = _width;
			frontCanvas.height = _height;

		}

		context.clearRect( 0, 0, _width, _height );
		frontContext.clearRect( 0, 0, _width, _height );

		//

		context.globalCompositeOperation = 'lighter';
		frontContext.globalCompositeOperation = 'source-over';

		const links = this.getLinks();

		const aPos = { x: 0, y: 0 };
		const bPos = { x: 0, y: 0 };

		const offsetIORadius = 10;

		let dragging = '';

		for ( const link of links ) {

			const { lioElement, rioElement } = link;

			let draggingLink = '';
			let length = 0;

			if ( lioElement !== null ) {

				const rect = lioElement.dom.getBoundingClientRect();

				length = Math.max( length, lioElement.rioLength );

				aPos.x = rect.x + rect.width;
				aPos.y = rect.y + ( rect.height / 2 );

				if ( useTransform ) {

					aPos.x /= zoom;
					aPos.y /= zoom;

				}

			} else {

				aPos.x = this.clientX;
				aPos.y = this.clientY;

				draggingLink = 'lio';

			}

			if ( rioElement !== null ) {

				const rect = rioElement.dom.getBoundingClientRect();

				length = Math.max( length, rioElement.lioLength );

				bPos.x = rect.x;
				bPos.y = rect.y + ( rect.height / 2 );

				if ( useTransform ) {

					bPos.x /= zoom;
					bPos.y /= zoom;

				}

			} else {

				bPos.x = this.clientX;
				bPos.y = this.clientY;

				draggingLink = 'rio';

			}

			dragging = dragging || draggingLink;

			const drawContext = draggingLink ? frontContext : context;

			if ( draggingLink || length === 1 ) {

				let colorA = null,
					colorB = null;

				if ( draggingLink === 'rio' ) {

					colorA = colorB = lioElement.getRIOColor();

					aPos.x += offsetIORadius;
					bPos.x /= zoom;
					bPos.y /= zoom;

				} else if ( draggingLink === 'lio' ) {

					colorA = colorB = rioElement.getLIOColor();

					bPos.x -= offsetIORadius;
					aPos.x /= zoom;
					aPos.y /= zoom;

				} else {

					colorA = lioElement.getRIOColor();
					colorB = rioElement.getLIOColor();

				}

				drawLine(
					aPos.x * zoom, aPos.y * zoom,
					bPos.x * zoom, bPos.y * zoom,
					false, 2, colorA || '#ffffff', drawContext, colorB || '#ffffff'
				);

			} else {

				length = Math.min( length, 4 );

				for ( let i = 0; i < length; i ++ ) {

					const color = colors[ i ] || '#ffffff';

					const marginY = 4;

					const rioLength = Math.min( lioElement.rioLength, length );
					const lioLength = Math.min( rioElement.lioLength, length );

					const colorA = lioElement.getRIOColor() || color;
					const colorB = rioElement.getLIOColor() || color;

					const aCenterY = ( ( rioLength * marginY ) * .5 ) - ( marginY / 2 );
					const bCenterY = ( ( lioLength * marginY ) * .5 ) - ( marginY / 2 );

					const aIndex = Math.min( i, rioLength - 1 );
					const bIndex = Math.min( i, lioLength - 1 );

					const aPosY = ( aIndex * marginY ) - 1;
					const bPosY = ( bIndex * marginY ) - 1;

					drawLine(
						aPos.x * zoom, ( ( aPos.y + aPosY ) - aCenterY ) * zoom,
						bPos.x * zoom, ( ( bPos.y + bPosY ) - bCenterY ) * zoom,
						false, 2, colorA, drawContext, colorB
					);

				}

			}

		}

		context.globalCompositeOperation = 'destination-in';

		context.fillRect( domRect.x, domRect.y, domRect.width, domRect.height );

		if ( dragging !== '' ) {

			dom.classList.add( 'dragging-' + dragging );

		} else {

			dom.classList.remove( 'dragging-lio' );
			dom.classList.remove( 'dragging-rio' );

		}

	}

	update() {

		if ( this.updating === false ) return;

		requestAnimationFrame( this._onUpdate );

		this.updateLines();
		this.updateMap();

	}

	serialize( data ) {

		const nodes = [];
		const serializeNodes = this.nodes.sort( ( a, b ) => a.serializePriority > b.serializePriority ? - 1 : 1 );

		for ( const node of serializeNodes ) {

			nodes.push( node.toJSON( data ).id );

		}

		data.nodes = nodes;

	}

	deserialize( data ) {

		for ( const id of data.nodes ) {

			this.add( data.objects[ id ] );

		}

	}

}
```
</details>

#### Methods

##### `getBounds(): { x: number; y: number; width: number; height: number; }`

<details><summary>Code</summary>

```ts
getBounds() {

		const bounds = { x: Infinity, y: Infinity, width: - Infinity, height: - Infinity };

		for ( const node of this.nodes ) {

			const { x, y, width, height } = node.getBound();

			bounds.x = Math.min( bounds.x, x );
			bounds.y = Math.min( bounds.y, y );
			bounds.width = Math.max( bounds.width, x + width );
			bounds.height = Math.max( bounds.height, y + height );

		}

		bounds.x = Math.round( bounds.x );
		bounds.y = Math.round( bounds.y );
		bounds.width = Math.round( bounds.width );
		bounds.height = Math.round( bounds.height );

		return bounds;

	}
```
</details>

##### `updateMozTransform(): void`

<details><summary>Code</summary>

```ts
updateMozTransform() {

		if ( this.useTransform === false ) return;

		this.contentDOM.style[ '-moz-transform' ] = 'scale(' + this.zoom + ')';
		this.contentDOM.style[ '-moz-transform-origin' ] = '-' + this.contentDOM.style.left + ' -' + this.contentDOM.style.top;

	}
```
</details>

##### `onDrop(callback: any): this`

<details><summary>Code</summary>

```ts
onDrop( callback ) {

		this.events.drop.push( callback );

		return this;

	}
```
</details>

##### `start(): void`

<details><summary>Code</summary>

```ts
start() {

		this.updating = true;

		document.addEventListener( 'wheel', this._onMoveEvent, true );

		document.addEventListener( 'mousedown', this._onMoveEvent, true );
		document.addEventListener( 'touchstart', this._onMoveEvent, true );

		document.addEventListener( 'mousemove', this._onMoveEvent, true );
		document.addEventListener( 'touchmove', this._onMoveEvent, true );

		document.addEventListener( 'dragover', this._onMoveEvent, true );

		requestAnimationFrame( this._onUpdate );

	}
```
</details>

##### `stop(): void`

<details><summary>Code</summary>

```ts
stop() {

		this.updating = false;

		document.removeEventListener( 'wheel', this._onMoveEvent, true );

		document.removeEventListener( 'mousedown', this._onMoveEvent, true );
		document.removeEventListener( 'touchstart', this._onMoveEvent, true );

		document.removeEventListener( 'mousemove', this._onMoveEvent, true );
		document.removeEventListener( 'touchmove', this._onMoveEvent, true );

		document.removeEventListener( 'dragover', this._onMoveEvent, true );

	}
```
</details>

##### `add(node: any): this`

<details><summary>Code</summary>

```ts
add( node ) {

		if ( node.canvas === this ) return;

		this.nodes.push( node );

		node.canvas = this;

		this.contentDOM.append( node.dom );

		return this;

	}
```
</details>

##### `remove(node: any): this`

<details><summary>Code</summary>

```ts
remove( node ) {

		if ( node === this.selected ) {

			this.select();

		}

		this.unlink( node );

		const nodes = this.nodes;

		nodes.splice( nodes.indexOf( node ), 1 );

		node.canvas = null;

		this.contentDOM.removeChild( node.dom );

		node.dispatchEvent( new Event( 'remove' ) );

		return this;

	}
```
</details>

##### `clear(): this`

<details><summary>Code</summary>

```ts
clear() {

		const nodes = this.nodes;

		while ( nodes.length > 0 ) {

			this.remove( nodes[ 0 ] );

		}

		return this;

	}
```
</details>

##### `unlink(node: any): void`

<details><summary>Code</summary>

```ts
unlink( node ) {

		const links = this.getLinks();

		for ( const link of links ) {

			if ( link.inputElement && link.outputElement ) {

				if ( link.inputElement.node === node ) {

					link.inputElement.connect();

				} else if ( link.outputElement.node === node ) {

					link.inputElement.connect();

				}

			}

		}

	}
```
</details>

##### `getLinks(): any[]`

<details><summary>Code</summary>

```ts
getLinks() {

		const links = [];

		for ( const node of this.nodes ) {

			links.push( ...node.getLinks() );

		}

		return links;

	}
```
</details>

##### `centralize(): this`

<details><summary>Code</summary>

```ts
centralize() {

		const bounds = this.getBounds();

		this.scrollLeft = ( this.canvas.width / 2 ) - ( ( - bounds.x + bounds.width ) / 2 );
		this.scrollTop = ( this.canvas.height / 2 ) - ( ( - bounds.y + bounds.height ) / 2 );

		return this;

	}
```
</details>

##### `setSize(width: any, height: any): this`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this._width = width;
		this._height = height;

		this.update();

		return this;

	}
```
</details>

##### `select(node: any): void`

<details><summary>Code</summary>

```ts
select( node = null ) {

		if ( node === this.selected ) return;

		const previousNode = this.selected;

		if ( previousNode !== null ) {

			this.focusSelected = false;

			previousNode.dom.classList.remove( 'selected' );

			this.selected = null;

			dispatchEventList( previousNode.events.blur, previousNode );

		}

		if ( node !== null ) {

			node.dom.classList.add( 'selected' );

			this.selected = node;

			dispatchEventList( node.events.focus, node );

		}

	}
```
</details>

##### `updateMap(): void`

<details><summary>Code</summary>

```ts
updateMap() {

		const { nodes, mapCanvas, mapContext, scrollLeft, scrollTop, canvas, zoom, _mapInfo } = this;

		const bounds = this.getBounds();

		mapCanvas.width = 300;
		mapCanvas.height = 200;

		mapContext.clearRect( 0, 0, mapCanvas.width, mapCanvas.height );

		mapContext.fillStyle = 'rgba( 0, 0, 0, 0 )';
		mapContext.fillRect( 0, 0, mapCanvas.width, mapCanvas.height );

		const boundsWidth = - bounds.x + bounds.width;
		const boundsHeight = - bounds.y + bounds.height;

		const mapScale = Math.min( mapCanvas.width / boundsWidth, mapCanvas.height / boundsHeight ) * .5;

		const boundsMapWidth = boundsWidth * mapScale;
		const boundsMapHeight = boundsHeight * mapScale;

		const boundsOffsetX = ( mapCanvas.width / 2 ) - ( boundsMapWidth / 2 );
		const boundsOffsetY = ( mapCanvas.height / 2 ) - ( boundsMapHeight / 2 );

		let selectedNode = null;

		for ( const node of nodes ) {

			const nodeBound = node.getBound();
			const nodeColor = node.getColor();

			nodeBound.x += - bounds.x;
			nodeBound.y += - bounds.y;

			nodeBound.x *= mapScale;
			nodeBound.y *= mapScale;
			nodeBound.width *= mapScale;
			nodeBound.height *= mapScale;

			nodeBound.x += boundsOffsetX;
			nodeBound.y += boundsOffsetY;

			if ( node !== this.selected ) {

				mapContext.fillStyle = nodeColor;
				mapContext.fillRect( nodeBound.x, nodeBound.y, nodeBound.width, nodeBound.height );

			} else {

				selectedNode = {
					nodeBound,
					nodeColor
				};

			}

		}

		if ( selectedNode !== null ) {

			const { nodeBound, nodeColor } = selectedNode;

			mapContext.fillStyle = nodeColor;
			mapContext.fillRect( nodeBound.x, nodeBound.y, nodeBound.width, nodeBound.height );

		}

		const screenMapX = ( - ( scrollLeft + bounds.x ) * mapScale ) + boundsOffsetX;
		const screenMapY = ( - ( scrollTop + bounds.y ) * mapScale ) + boundsOffsetY;
		const screenMapWidth = ( canvas.width * mapScale ) / zoom;
		const screenMapHeight = ( canvas.height * mapScale ) / zoom;

		mapContext.fillStyle = 'rgba( 200, 200, 200, 0.1 )';
		mapContext.fillRect( screenMapX, screenMapY, screenMapWidth, screenMapHeight );

		//

		_mapInfo.scale = mapScale;
		_mapInfo.left = ( - boundsOffsetX / mapScale ) + bounds.x;
		_mapInfo.top = ( - boundsOffsetY / mapScale ) + bounds.y;
		_mapInfo.width = mapCanvas.width / mapScale;
		_mapInfo.height = mapCanvas.height / mapScale;
		_mapInfo.screen.x = screenMapX;
		_mapInfo.screen.y = screenMapY;
		_mapInfo.screen.width = screenMapWidth;
		_mapInfo.screen.height = screenMapHeight;

	}
```
</details>

##### `updateLines(): void`

<details><summary>Code</summary>

```ts
updateLines() {

		const { dom, zoom, canvas, frontCanvas, frontContext, context, _width, _height, useTransform } = this;

		const domRect = this.rect;

		if ( canvas.width !== _width || canvas.height !== _height ) {

			canvas.width = _width;
			canvas.height = _height;

			frontCanvas.width = _width;
			frontCanvas.height = _height;

		}

		context.clearRect( 0, 0, _width, _height );
		frontContext.clearRect( 0, 0, _width, _height );

		//

		context.globalCompositeOperation = 'lighter';
		frontContext.globalCompositeOperation = 'source-over';

		const links = this.getLinks();

		const aPos = { x: 0, y: 0 };
		const bPos = { x: 0, y: 0 };

		const offsetIORadius = 10;

		let dragging = '';

		for ( const link of links ) {

			const { lioElement, rioElement } = link;

			let draggingLink = '';
			let length = 0;

			if ( lioElement !== null ) {

				const rect = lioElement.dom.getBoundingClientRect();

				length = Math.max( length, lioElement.rioLength );

				aPos.x = rect.x + rect.width;
				aPos.y = rect.y + ( rect.height / 2 );

				if ( useTransform ) {

					aPos.x /= zoom;
					aPos.y /= zoom;

				}

			} else {

				aPos.x = this.clientX;
				aPos.y = this.clientY;

				draggingLink = 'lio';

			}

			if ( rioElement !== null ) {

				const rect = rioElement.dom.getBoundingClientRect();

				length = Math.max( length, rioElement.lioLength );

				bPos.x = rect.x;
				bPos.y = rect.y + ( rect.height / 2 );

				if ( useTransform ) {

					bPos.x /= zoom;
					bPos.y /= zoom;

				}

			} else {

				bPos.x = this.clientX;
				bPos.y = this.clientY;

				draggingLink = 'rio';

			}

			dragging = dragging || draggingLink;

			const drawContext = draggingLink ? frontContext : context;

			if ( draggingLink || length === 1 ) {

				let colorA = null,
					colorB = null;

				if ( draggingLink === 'rio' ) {

					colorA = colorB = lioElement.getRIOColor();

					aPos.x += offsetIORadius;
					bPos.x /= zoom;
					bPos.y /= zoom;

				} else if ( draggingLink === 'lio' ) {

					colorA = colorB = rioElement.getLIOColor();

					bPos.x -= offsetIORadius;
					aPos.x /= zoom;
					aPos.y /= zoom;

				} else {

					colorA = lioElement.getRIOColor();
					colorB = rioElement.getLIOColor();

				}

				drawLine(
					aPos.x * zoom, aPos.y * zoom,
					bPos.x * zoom, bPos.y * zoom,
					false, 2, colorA || '#ffffff', drawContext, colorB || '#ffffff'
				);

			} else {

				length = Math.min( length, 4 );

				for ( let i = 0; i < length; i ++ ) {

					const color = colors[ i ] || '#ffffff';

					const marginY = 4;

					const rioLength = Math.min( lioElement.rioLength, length );
					const lioLength = Math.min( rioElement.lioLength, length );

					const colorA = lioElement.getRIOColor() || color;
					const colorB = rioElement.getLIOColor() || color;

					const aCenterY = ( ( rioLength * marginY ) * .5 ) - ( marginY / 2 );
					const bCenterY = ( ( lioLength * marginY ) * .5 ) - ( marginY / 2 );

					const aIndex = Math.min( i, rioLength - 1 );
					const bIndex = Math.min( i, lioLength - 1 );

					const aPosY = ( aIndex * marginY ) - 1;
					const bPosY = ( bIndex * marginY ) - 1;

					drawLine(
						aPos.x * zoom, ( ( aPos.y + aPosY ) - aCenterY ) * zoom,
						bPos.x * zoom, ( ( bPos.y + bPosY ) - bCenterY ) * zoom,
						false, 2, colorA, drawContext, colorB
					);

				}

			}

		}

		context.globalCompositeOperation = 'destination-in';

		context.fillRect( domRect.x, domRect.y, domRect.width, domRect.height );

		if ( dragging !== '' ) {

			dom.classList.add( 'dragging-' + dragging );

		} else {

			dom.classList.remove( 'dragging-lio' );
			dom.classList.remove( 'dragging-rio' );

		}

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		if ( this.updating === false ) return;

		requestAnimationFrame( this._onUpdate );

		this.updateLines();
		this.updateMap();

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		const nodes = [];
		const serializeNodes = this.nodes.sort( ( a, b ) => a.serializePriority > b.serializePriority ? - 1 : 1 );

		for ( const node of serializeNodes ) {

			nodes.push( node.toJSON( data ).id );

		}

		data.nodes = nodes;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		for ( const id of data.nodes ) {

			this.add( data.objects[ id ] );

		}

	}
```
</details>

### `Menu`

<details><summary>Class Code</summary>

```ts
class Menu extends EventTarget {

	constructor( className ) {

		super();

		const dom = document.createElement( 'f-menu' );
		dom.className = className + ' bottom left hidden';

		const listDOM = document.createElement( 'f-list' );

		dom.append( listDOM );

		this.dom = dom;
		this.listDOM = listDOM;

		this.visible = false;

		this.align = 'bottom left';

		this.subMenus = new WeakMap();
		this.domButtons = new WeakMap();

		this.buttons = [];

		this.events = {};

	}

	onContext( callback ) {

		this.events.context.push( callback );

		return this;

	}

	setAlign( align ) {

		const dom = this.dom;

		removeDOMClass( dom, this.align );
		addDOMClass( dom, align );

		this.align = align;

		return this;

	}

	getAlign() {

		return this.align;

	}

	show() {

		this.dom.classList.remove( 'hidden' );

		this.visible = true;

		this.dispatchEvent( new Event( 'show' ) );

		return this;

	}

	hide() {

		this.dom.classList.add( 'hidden' );

		this.dispatchEvent( new Event( 'hide' ) );

		this.visible = false;

	}

	add( button, submenu = null ) {

		const liDOM = document.createElement( 'f-item' );

		if ( submenu !== null ) {

			liDOM.classList.add( 'submenu' );

			liDOM.append( submenu.dom );

			this.subMenus.set( button, submenu );

			button.dom.addEventListener( 'mouseover', () => submenu.show() );
			button.dom.addEventListener( 'mouseout', () => submenu.hide() );

		}

		liDOM.append( button.dom );

		this.buttons.push( button );

		this.listDOM.append( liDOM );

		this.domButtons.set( button, liDOM );

		return this;

	}

	clear() {

		this.buttons = [];

		this.subMenus = new WeakMap();
		this.domButtons = new WeakMap();

		while ( this.listDOM.firstChild ) {

			this.listDOM.firstChild.remove();

		}

	}

}
```
</details>

#### Methods

##### `onContext(callback: any): this`

<details><summary>Code</summary>

```ts
onContext( callback ) {

		this.events.context.push( callback );

		return this;

	}
```
</details>

##### `setAlign(align: any): this`

<details><summary>Code</summary>

```ts
setAlign( align ) {

		const dom = this.dom;

		removeDOMClass( dom, this.align );
		addDOMClass( dom, align );

		this.align = align;

		return this;

	}
```
</details>

##### `getAlign(): string`

<details><summary>Code</summary>

```ts
getAlign() {

		return this.align;

	}
```
</details>

##### `show(): this`

<details><summary>Code</summary>

```ts
show() {

		this.dom.classList.remove( 'hidden' );

		this.visible = true;

		this.dispatchEvent( new Event( 'show' ) );

		return this;

	}
```
</details>

##### `hide(): void`

<details><summary>Code</summary>

```ts
hide() {

		this.dom.classList.add( 'hidden' );

		this.dispatchEvent( new Event( 'hide' ) );

		this.visible = false;

	}
```
</details>

##### `add(button: any, submenu: any): this`

<details><summary>Code</summary>

```ts
add( button, submenu = null ) {

		const liDOM = document.createElement( 'f-item' );

		if ( submenu !== null ) {

			liDOM.classList.add( 'submenu' );

			liDOM.append( submenu.dom );

			this.subMenus.set( button, submenu );

			button.dom.addEventListener( 'mouseover', () => submenu.show() );
			button.dom.addEventListener( 'mouseout', () => submenu.hide() );

		}

		liDOM.append( button.dom );

		this.buttons.push( button );

		this.listDOM.append( liDOM );

		this.domButtons.set( button, liDOM );

		return this;

	}
```
</details>

##### `clear(): void`

<details><summary>Code</summary>

```ts
clear() {

		this.buttons = [];

		this.subMenus = new WeakMap();
		this.domButtons = new WeakMap();

		while ( this.listDOM.firstChild ) {

			this.listDOM.firstChild.remove();

		}

	}
```
</details>

### `ContextMenu`

<details><summary>Class Code</summary>

```ts
class ContextMenu extends Menu {

	constructor( target = null ) {

		super( 'context' );

		this.events.context = [];

		this._lastButtonClick = null;

		this._onButtonClick = ( e = null ) => {

			const button = e ? e.target : null;

			if ( this._lastButtonClick ) {

				this._lastButtonClick.dom.parentElement.classList.remove( 'active' );

			}

			this._lastButtonClick = button;

			if ( button ) {

				if ( this.subMenus.has( button ) ) {

					this.subMenus.get( button )._onButtonClick();

				}

				button.dom.parentElement.classList.add( 'active' );

			}

		};

		this._onButtonMouseOver = ( e ) => {

			const button = e.target;

			if ( this.subMenus.has( button ) && this._lastButtonClick !== button ) {

				this._onButtonClick();

			}

		};

		this.addEventListener( 'context', ( ) => {

			dispatchEventList( this.events.context, this );

		} );

		this.setTarget( target );

	}

	openFrom( dom ) {

		const rect = dom.getBoundingClientRect();

		return this.open( rect.x + ( rect.width / 2 ), rect.y + ( rect.height / 2 ) );

	}

	open( x = pointer.x, y = pointer.y ) {

		if ( lastContext !== null ) {

			lastContext.hide();

		}

		lastContext = this;

		this.setPosition( x, y );

		document.body.append( this.dom );

		return this.show();

	}

	setWidth( width ) {

		this.dom.style.width = numberToPX( width );

		return this;

	}

	setPosition( x, y ) {

		const dom = this.dom;

		dom.style.left = numberToPX( x );
		dom.style.top = numberToPX( y );

		return this;

	}

	setTarget( target = null ) {

		if ( target !== null ) {

			const onContextMenu = ( e ) => {

				e.preventDefault();

				if ( e.pointerType !== 'mouse' || ( e.pageX === 0 && e.pageY === 0 ) ) return;

				this.dispatchEvent( new Event( 'context' ) );

				this.open();

			};

			this.target = target;

			target.addEventListener( 'contextmenu', onContextMenu, false );

		}

		return this;

	}

	show() {

		if ( ! this.opened ) {

			this.dom.style.left = '';
			this.dom.style.transform = '';

		}

		const domRect = this.dom.getBoundingClientRect();

		let offsetX = Math.min( window.innerWidth - ( domRect.x + domRect.width + 10 ), 0 );
		let offsetY = Math.min( window.innerHeight - ( domRect.y + domRect.height + 10 ), 0 );

		if ( this.opened ) {

			if ( offsetX < 0 ) offsetX = - domRect.width;
			if ( offsetY < 0 ) offsetY = - domRect.height;

			this.setPosition( domRect.x + offsetX, domRect.y + offsetY );

		} else {

			// flip submenus

			if ( offsetX < 0 ) this.dom.style.left = '-100%';
			if ( offsetY < 0 ) this.dom.style.transform = 'translateY( calc( 32px - 100% ) )';

		}

		return super.show();

	}

	hide() {

		if ( this.opened ) {

			lastContext = null;

		}

		return super.hide();

	}

	add( button, submenu = null ) {

		button.addEventListener( 'click', this._onButtonClick );
		button.addEventListener( 'mouseover', this._onButtonMouseOver );

		return super.add( button, submenu );

	}

	get opened() {

		return lastContext === this;

	}

}
```
</details>

#### Methods

##### `openFrom(dom: any): this`

<details><summary>Code</summary>

```ts
openFrom( dom ) {

		const rect = dom.getBoundingClientRect();

		return this.open( rect.x + ( rect.width / 2 ), rect.y + ( rect.height / 2 ) );

	}
```
</details>

##### `open(x: number, y: number): this`

<details><summary>Code</summary>

```ts
open( x = pointer.x, y = pointer.y ) {

		if ( lastContext !== null ) {

			lastContext.hide();

		}

		lastContext = this;

		this.setPosition( x, y );

		document.body.append( this.dom );

		return this.show();

	}
```
</details>

##### `setWidth(width: any): this`

<details><summary>Code</summary>

```ts
setWidth( width ) {

		this.dom.style.width = numberToPX( width );

		return this;

	}
```
</details>

##### `setPosition(x: any, y: any): this`

<details><summary>Code</summary>

```ts
setPosition( x, y ) {

		const dom = this.dom;

		dom.style.left = numberToPX( x );
		dom.style.top = numberToPX( y );

		return this;

	}
```
</details>

##### `setTarget(target: any): this`

<details><summary>Code</summary>

```ts
setTarget( target = null ) {

		if ( target !== null ) {

			const onContextMenu = ( e ) => {

				e.preventDefault();

				if ( e.pointerType !== 'mouse' || ( e.pageX === 0 && e.pageY === 0 ) ) return;

				this.dispatchEvent( new Event( 'context' ) );

				this.open();

			};

			this.target = target;

			target.addEventListener( 'contextmenu', onContextMenu, false );

		}

		return this;

	}
```
</details>

##### `show(): this`

<details><summary>Code</summary>

```ts
show() {

		if ( ! this.opened ) {

			this.dom.style.left = '';
			this.dom.style.transform = '';

		}

		const domRect = this.dom.getBoundingClientRect();

		let offsetX = Math.min( window.innerWidth - ( domRect.x + domRect.width + 10 ), 0 );
		let offsetY = Math.min( window.innerHeight - ( domRect.y + domRect.height + 10 ), 0 );

		if ( this.opened ) {

			if ( offsetX < 0 ) offsetX = - domRect.width;
			if ( offsetY < 0 ) offsetY = - domRect.height;

			this.setPosition( domRect.x + offsetX, domRect.y + offsetY );

		} else {

			// flip submenus

			if ( offsetX < 0 ) this.dom.style.left = '-100%';
			if ( offsetY < 0 ) this.dom.style.transform = 'translateY( calc( 32px - 100% ) )';

		}

		return super.show();

	}
```
</details>

##### `hide(): void`

<details><summary>Code</summary>

```ts
hide() {

		if ( this.opened ) {

			lastContext = null;

		}

		return super.hide();

	}
```
</details>

##### `add(button: any, submenu: any): this`

<details><summary>Code</summary>

```ts
add( button, submenu = null ) {

		button.addEventListener( 'click', this._onButtonClick );
		button.addEventListener( 'mouseover', this._onButtonMouseOver );

		return super.add( button, submenu );

	}
```
</details>

### `CircleMenu`

<details><summary>Class Code</summary>

```ts
class CircleMenu extends Menu {

	constructor() {

		super( 'circle' );

	}

}
```
</details>

### `Tips`

<details><summary>Class Code</summary>

```ts
class Tips extends EventTarget {

	constructor() {

		super();

		const dom = document.createElement( 'f-tips' );

		this.dom = dom;

		this.time = 0;
		this.duration = 3000;

	}

	message( str ) {

		return this.tip( str );

	}

	error( str ) {

		return this.tip( str, 'error' );

	}

	tip( html, className = '' ) {

		const dom = document.createElement( 'f-tip' );
		dom.className = className;
		dom.innerHTML = html;

		this.dom.prepend( dom );

		//requestAnimationFrame( () => dom.style.opacity = 1 );

		this.time = Math.min( this.time + this.duration, this.duration );

		setTimeout( () => {

			this.time = Math.max( this.time - this.duration, 0 );

			dom.style.opacity = 0;

			setTimeout( () => dom.remove(), 250 );

		}, this.time );

		return this;

	}

}
```
</details>

#### Methods

##### `message(str: any): this`

<details><summary>Code</summary>

```ts
message( str ) {

		return this.tip( str );

	}
```
</details>

##### `error(str: any): this`

<details><summary>Code</summary>

```ts
error( str ) {

		return this.tip( str, 'error' );

	}
```
</details>

##### `tip(html: any, className: string): this`

<details><summary>Code</summary>

```ts
tip( html, className = '' ) {

		const dom = document.createElement( 'f-tip' );
		dom.className = className;
		dom.innerHTML = html;

		this.dom.prepend( dom );

		//requestAnimationFrame( () => dom.style.opacity = 1 );

		this.time = Math.min( this.time + this.duration, this.duration );

		setTimeout( () => {

			this.time = Math.max( this.time - this.duration, 0 );

			dom.style.opacity = 0;

			setTimeout( () => dom.remove(), 250 );

		}, this.time );

		return this;

	}
```
</details>

### `Search`

<details><summary>Class Code</summary>

```ts
class Search extends Menu {

	constructor() {

		super( 'search' );

		this.events.submit = [];
		this.events.filter = [];

		this.tags = new WeakMap();

		const inputDOM = document.createElement( 'input' );
		inputDOM.placeholder = 'Type here';

		let filter = true;
		let filterNeedUpdate = true;

		inputDOM.addEventListener( 'focusout', () => {

			filterNeedUpdate = true;

			this.setValue( '' );

		} );

		inputDOM.onkeydown = ( e ) => {

			const key = e.key;

			if ( key === 'ArrowUp' ) {

				const index = this.filteredIndex;

				if ( this.forceAutoComplete ) {

					this.filteredIndex = index !== null ? ( index + 1 ) % ( this.filtered.length || 1 ) : 0;

				} else {

					this.filteredIndex = index !== null ? Math.min( index + 1, this.filtered.length - 1 ) : 0;

				}

				e.preventDefault();

				filter = false;

			} else if ( key === 'ArrowDown' ) {

				const index = this.filteredIndex;

				if ( this.forceAutoComplete ) {

					this.filteredIndex = index - 1;

					if ( this.filteredIndex === null ) this.filteredIndex = this.filtered.length - 1;

				} else {

					this.filteredIndex = index !== null ? index - 1 : null;

				}

				e.preventDefault();

				filter = false;

			} else if ( key === 'Enter' ) {

				this.value = this.currentFiltered ? this.currentFiltered.button.getValue() : inputDOM.value;

				this.submit();

				e.preventDefault();

				filter = false;

			} else {

				filter = true;

			}

		};

		inputDOM.onkeyup = () => {

			if ( filter ) {

				if ( filterNeedUpdate ) {

					this.dispatchEvent( new Event( 'filter' ) );

					filterNeedUpdate = false;

				}

				this.filter( inputDOM.value );

			}

		};

		this.filtered = [];
		this.currentFiltered = null;

		this.value = '';

		this.forceAutoComplete = false;

		this.dom.append( inputDOM );

		this.inputDOM = inputDOM;

		this.addEventListener( 'filter', ( ) => {

			dispatchEventList( this.events.filter, this );

		} );

		this.addEventListener( 'submit', ( ) => {

			dispatchEventList( this.events.submit, this );

		} );

	}

	submit() {

		this.dispatchEvent( new Event( 'submit' ) );

		return this.setValue( '' );

	}

	setValue( value ) {

		this.inputDOM.value = value;

		this.filter( value );

		return this;

	}

	getValue() {

		return this.value;

	}

	onFilter( callback ) {

		this.events.filter.push( callback );

		return this;

	}

	onSubmit( callback ) {

		this.events.submit.push( callback );

		return this;

	}

	getFilterByButton( button ) {

		for ( const filter of this.filtered ) {

			if ( filter.button === button ) {

				return filter;

			}

		}

		return null;

	}

	add( button ) {

		super.add( button );

		const onDown = () => {

			const filter = this.getFilterByButton( button );

			this.filteredIndex = this.filtered.indexOf( filter );
			this.value = button.getValue();

			this.submit();

		};

		button.dom.addEventListener( 'mousedown', onDown );
		button.dom.addEventListener( 'touchstart', onDown );

		this.domButtons.get( button ).remove();

		return this;

	}

	set filteredIndex( index ) {

		if ( this.currentFiltered ) {

			const buttonDOM = this.domButtons.get( this.currentFiltered.button );

			buttonDOM.classList.remove( 'active' );

			this.currentFiltered = null;

		}

		const filteredItem = this.filtered[ index ];

		if ( filteredItem ) {

			const buttonDOM = this.domButtons.get( filteredItem.button );

			buttonDOM.classList.add( 'active' );

			this.currentFiltered = filteredItem;

		}

		this.updateFilter();

	}

	get filteredIndex() {

		return this.currentFiltered ? this.filtered.indexOf( this.currentFiltered ) : null;

	}

	setTag( button, tags ) {

		this.tags.set( button, tags );

	}

	filter( text ) {

		text = filterString( text );

		const tags = this.tags;
		const filtered = [];

		for ( const button of this.buttons ) {

			const buttonDOM = this.domButtons.get( button );

			buttonDOM.remove();

			const buttonTags = tags.has( button ) ? ' ' + tags.get( button ) : '';

			const label = filterString( button.getValue() + buttonTags );

			if ( text && label.includes( text ) === true ) {

				const score = text.length / label.length;

				filtered.push( {
					button,
					score
				} );

			}

		}

		filtered.sort( ( a, b ) => b.score - a.score );

		this.filtered = filtered;
		this.filteredIndex = this.forceAutoComplete ? 0 : null;

	}

	updateFilter() {

		const filteredIndex = Math.min( this.filteredIndex, this.filteredIndex - 3 );

		for ( let i = 0; i < this.filtered.length; i ++ ) {

			const button = this.filtered[ i ].button;
			const buttonDOM = this.domButtons.get( button );

			buttonDOM.remove();

			if ( i >= filteredIndex ) {

				this.listDOM.append( buttonDOM );

			}

		}

	}

}
```
</details>

#### Methods

##### `submit(): this`

<details><summary>Code</summary>

```ts
submit() {

		this.dispatchEvent( new Event( 'submit' ) );

		return this.setValue( '' );

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		this.inputDOM.value = value;

		this.filter( value );

		return this;

	}
```
</details>

##### `getValue(): string`

<details><summary>Code</summary>

```ts
getValue() {

		return this.value;

	}
```
</details>

##### `onFilter(callback: any): this`

<details><summary>Code</summary>

```ts
onFilter( callback ) {

		this.events.filter.push( callback );

		return this;

	}
```
</details>

##### `onSubmit(callback: any): this`

<details><summary>Code</summary>

```ts
onSubmit( callback ) {

		this.events.submit.push( callback );

		return this;

	}
```
</details>

##### `getFilterByButton(button: any): any`

<details><summary>Code</summary>

```ts
getFilterByButton( button ) {

		for ( const filter of this.filtered ) {

			if ( filter.button === button ) {

				return filter;

			}

		}

		return null;

	}
```
</details>

##### `add(button: any): this`

<details><summary>Code</summary>

```ts
add( button ) {

		super.add( button );

		const onDown = () => {

			const filter = this.getFilterByButton( button );

			this.filteredIndex = this.filtered.indexOf( filter );
			this.value = button.getValue();

			this.submit();

		};

		button.dom.addEventListener( 'mousedown', onDown );
		button.dom.addEventListener( 'touchstart', onDown );

		this.domButtons.get( button ).remove();

		return this;

	}
```
</details>

##### `setTag(button: any, tags: any): void`

<details><summary>Code</summary>

```ts
setTag( button, tags ) {

		this.tags.set( button, tags );

	}
```
</details>

##### `filter(text: any): void`

<details><summary>Code</summary>

```ts
filter( text ) {

		text = filterString( text );

		const tags = this.tags;
		const filtered = [];

		for ( const button of this.buttons ) {

			const buttonDOM = this.domButtons.get( button );

			buttonDOM.remove();

			const buttonTags = tags.has( button ) ? ' ' + tags.get( button ) : '';

			const label = filterString( button.getValue() + buttonTags );

			if ( text && label.includes( text ) === true ) {

				const score = text.length / label.length;

				filtered.push( {
					button,
					score
				} );

			}

		}

		filtered.sort( ( a, b ) => b.score - a.score );

		this.filtered = filtered;
		this.filteredIndex = this.forceAutoComplete ? 0 : null;

	}
```
</details>

##### `updateFilter(): void`

<details><summary>Code</summary>

```ts
updateFilter() {

		const filteredIndex = Math.min( this.filteredIndex, this.filteredIndex - 3 );

		for ( let i = 0; i < this.filtered.length; i ++ ) {

			const button = this.filtered[ i ].button;
			const buttonDOM = this.domButtons.get( button );

			buttonDOM.remove();

			if ( i >= filteredIndex ) {

				this.listDOM.append( buttonDOM );

			}

		}

	}
```
</details>

### `LabelElement`

<details><summary>Class Code</summary>

```ts
class LabelElement extends Element {

	static get type() {

		return 'LabelElement';

	}

	constructor( label = '', align = '' ) {

		super();

		this.labelDOM = document.createElement( 'f-label' );
		this.inputsDOM = document.createElement( 'f-inputs' );

		const spanDOM = document.createElement( 'span' );

		this.spanDOM = spanDOM;
		this.iconDOM = null;

		this.labelDOM.append( spanDOM );

		this.dom.append( this.labelDOM );
		this.dom.append( this.inputsDOM );

		this.serializeLabel = false;

		this.setLabel( label );
		this.setAlign( align );

	}

	setIcon( value ) {

		this.iconDOM = this.iconDOM || document.createElement( 'i' );
		this.iconDOM.className = value;

		if ( value ) this.labelDOM.prepend( this.iconDOM );
		else this.iconDOM.remove();

		return this;

	}

	getIcon() {

		return this.iconDOM ? this.iconDOM.className : null;

	}

	setAlign( align ) {

		this.labelDOM.className = align;

	}

	setLabel( val ) {

		this.spanDOM.innerText = val;

	}

	getLabel() {

		return this.spanDOM.innerText;

	}

	serialize( data ) {

		super.serialize( data );

		if ( this.serializeLabel ) {

			const label = this.getLabel();
			const icon = this.getIcon();

			data.label = label;

			if ( icon !== '' ) {

				data.icon = icon;

			}

		}

	}

	deserialize( data ) {

		super.deserialize( data );

		if ( this.serializeLabel ) {

			this.setLabel( data.label );

			if ( data.icon !== undefined ) {

				this.setIcon( data.icon );

			}

		}

	}

}
```
</details>

#### Methods

##### `setIcon(value: any): this`

<details><summary>Code</summary>

```ts
setIcon( value ) {

		this.iconDOM = this.iconDOM || document.createElement( 'i' );
		this.iconDOM.className = value;

		if ( value ) this.labelDOM.prepend( this.iconDOM );
		else this.iconDOM.remove();

		return this;

	}
```
</details>

##### `getIcon(): any`

<details><summary>Code</summary>

```ts
getIcon() {

		return this.iconDOM ? this.iconDOM.className : null;

	}
```
</details>

##### `setAlign(align: any): void`

<details><summary>Code</summary>

```ts
setAlign( align ) {

		this.labelDOM.className = align;

	}
```
</details>

##### `setLabel(val: any): void`

<details><summary>Code</summary>

```ts
setLabel( val ) {

		this.spanDOM.innerText = val;

	}
```
</details>

##### `getLabel(): string`

<details><summary>Code</summary>

```ts
getLabel() {

		return this.spanDOM.innerText;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		if ( this.serializeLabel ) {

			const label = this.getLabel();
			const icon = this.getIcon();

			data.label = label;

			if ( icon !== '' ) {

				data.icon = icon;

			}

		}

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		if ( this.serializeLabel ) {

			this.setLabel( data.label );

			if ( data.icon !== undefined ) {

				this.setIcon( data.icon );

			}

		}

	}
```
</details>

### `ButtonInput`

<details><summary>Class Code</summary>

```ts
class ButtonInput extends Input {

	static get type() {

		return 'ButtonInput';

	}

	constructor( innterText = '' ) {

		const dom = document.createElement( 'button' );

		const spanDOM = document.createElement( 'span' );
		dom.append( spanDOM );

		const iconDOM = document.createElement( 'i' );
		dom.append( iconDOM );

		super( dom );

		this.spanDOM = spanDOM;
		this.iconDOM = iconDOM;

		spanDOM.innerText = innterText;

		dom.onmouseover = () => {

			this.dispatchEvent( new Event( 'mouseover' ) );

		};

		dom.onclick = dom.ontouchstart =
		iconDOM.onclick = iconDOM.ontouchstart = ( e ) => {

			e.preventDefault();

			e.stopPropagation();

			this.dispatchEvent( new Event( 'click' ) );

		};

	}

	setIcon( className ) {

		this.iconDOM.className = className;

		return this;

	}

	getIcon() {

		return this.iconDOM.className;

	}

	setValue( val ) {

		this.spanDOM.innerText = val;

		return this;

	}

	getValue() {

		return this.spanDOM.innerText;

	}

}
```
</details>

#### Methods

##### `setIcon(className: any): this`

<details><summary>Code</summary>

```ts
setIcon( className ) {

		this.iconDOM.className = className;

		return this;

	}
```
</details>

##### `getIcon(): string`

<details><summary>Code</summary>

```ts
getIcon() {

		return this.iconDOM.className;

	}
```
</details>

##### `setValue(val: any): this`

<details><summary>Code</summary>

```ts
setValue( val ) {

		this.spanDOM.innerText = val;

		return this;

	}
```
</details>

##### `getValue(): string`

<details><summary>Code</summary>

```ts
getValue() {

		return this.spanDOM.innerText;

	}
```
</details>

### `ColorInput`

<details><summary>Class Code</summary>

```ts
class ColorInput extends Input {

	static get type() {

		return 'ColorInput';

	}

	constructor( value = 0x0099ff ) {

		const dom = document.createElement( 'input' );
		super( dom );

		dom.type = 'color';
		dom.value = numberToHex( value );

		dom.oninput = () => {

			this.dispatchEvent( new Event( 'change' ) );

		};

	}

	setValue( value, dispatch = true ) {

		return super.setValue( numberToHex( value ), dispatch );

	}

	getValue() {

		return parseInt( super.getValue().substr( 1 ), 16 );

	}

}
```
</details>

#### Methods

##### `setValue(value: any, dispatch: boolean): this`

<details><summary>Code</summary>

```ts
setValue( value, dispatch = true ) {

		return super.setValue( numberToHex( value ), dispatch );

	}
```
</details>

##### `getValue(): number`

<details><summary>Code</summary>

```ts
getValue() {

		return parseInt( super.getValue().substr( 1 ), 16 );

	}
```
</details>

### `NumberInput`

<details><summary>Class Code</summary>

```ts
class NumberInput extends Input {

	static get type() {

		return 'NumberInput';

	}

	constructor( value = 0, min = - Infinity, max = Infinity, step = .01 ) {

		const dom = document.createElement( 'input' );
		super( dom );

		this.min = min;
		this.max = max;
		this.step = step;

		this.integer = false;

		dom.type = 'text';
		dom.className = 'number';
		dom.value = this._getString( value );
		dom.spellcheck = false;
		dom.autocomplete = 'off';

		dom.ondragstart = dom.oncontextmenu = ( e ) => {

			e.preventDefault();

			e.stopPropagation();

		};

		dom.onfocus = dom.onclick = () => {

			dom.select();

		};

		dom.onblur = () => {

			this.dom.value = this._getString( this.dom.value );

			this.dispatchEvent( new Event( 'blur' ) );

		};

		dom.onchange = () => {

			this.dispatchEvent( new Event( 'change' ) );

		};

		dom.onkeydown = ( e ) => {

			if ( e.key.length === 1 && /\d|\.|\-/.test( e.key ) !== true ) {

				return false;

			}

			if ( e.key === 'Enter' ) {

				e.target.blur();

			}

			e.stopPropagation();

		};

		draggableDOM( dom, ( data ) => {

			const { delta } = data;

			if ( dom.readOnly === true ) return;

			if ( data.value === undefined ) {

				data.value = this.getValue();

			}

			const diff = delta.x - delta.y;

			const value = data.value + ( diff * this.step );

			dom.value = this._getString( value.toFixed( this.precision ) );

			this.dispatchEvent( new Event( 'change' ) );

		} );

	}

	setStep( step ) {

		this.step = step;

		return this;

	}

	setRange( min, max, step ) {

		this.min = min;
		this.max = max;
		this.step = step;

		this.dispatchEvent( new Event( 'range' ) );

		return this.setValue( this.getValue() );

	}

	setInterger( bool ) {

		this.integer = bool;
		this.step = .1;

		return this.setValue( this.getValue() );

	}

	get precision() {

		if ( this.integer === true ) return 0;

		const fract = this.step % 1;

		return fract !== 0 ? fract.toString().split( '.' )[ 1 ].length : 1;

	}

	setValue( val, dispatch = true ) {

		return super.setValue( this._getString( val ), dispatch );

	}

	getValue() {

		return Number( this.dom.value );

	}

	serialize( data ) {

		const { min, max } = this;

		if ( min !== - Infinity && max !== Infinity ) {

			data.min = this.min;
			data.max = this.max;
			data.step = this.step;

		}

		super.serialize( data );

	}

	deserialize( data ) {

		if ( data.min !== undefined ) {

			const { min, max, step } = this;

			this.setRange( min, max, step );

		}

		super.deserialize( data );

	}

	_getString( value ) {

		const num = Math.min( Math.max( Number( value ), this.min ), this.max );

		if ( this.integer === true ) {

			return Math.floor( num );

		} else {

			return num + ( num % 1 ? '' : '.0' );

		}

	}

}
```
</details>

#### Methods

##### `setStep(step: any): this`

<details><summary>Code</summary>

```ts
setStep( step ) {

		this.step = step;

		return this;

	}
```
</details>

##### `setRange(min: any, max: any, step: any): this`

<details><summary>Code</summary>

```ts
setRange( min, max, step ) {

		this.min = min;
		this.max = max;
		this.step = step;

		this.dispatchEvent( new Event( 'range' ) );

		return this.setValue( this.getValue() );

	}
```
</details>

##### `setInterger(bool: any): this`

<details><summary>Code</summary>

```ts
setInterger( bool ) {

		this.integer = bool;
		this.step = .1;

		return this.setValue( this.getValue() );

	}
```
</details>

##### `setValue(val: any, dispatch: boolean): this`

<details><summary>Code</summary>

```ts
setValue( val, dispatch = true ) {

		return super.setValue( this._getString( val ), dispatch );

	}
```
</details>

##### `getValue(): number`

<details><summary>Code</summary>

```ts
getValue() {

		return Number( this.dom.value );

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		const { min, max } = this;

		if ( min !== - Infinity && max !== Infinity ) {

			data.min = this.min;
			data.max = this.max;
			data.step = this.step;

		}

		super.serialize( data );

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		if ( data.min !== undefined ) {

			const { min, max, step } = this;

			this.setRange( min, max, step );

		}

		super.deserialize( data );

	}
```
</details>

##### `_getString(value: any): string | number`

<details><summary>Code</summary>

```ts
_getString( value ) {

		const num = Math.min( Math.max( Number( value ), this.min ), this.max );

		if ( this.integer === true ) {

			return Math.floor( num );

		} else {

			return num + ( num % 1 ? '' : '.0' );

		}

	}
```
</details>

### `SelectInput`

<details><summary>Class Code</summary>

```ts
class SelectInput extends Input {

	static get type() {

		return 'SelectInput';

	}

	constructor( options = [], value = null ) {

		const dom = document.createElement( 'select' );
		super( dom );

		dom.onchange = () => {

			this.dispatchEvent( new Event( 'change' ) );

		};

		dom.onmousedown = dom.ontouchstart = () => {

			this.dispatchEvent( new Event( 'click' ) );

		};

		this.setOptions( options, value );

	}

	setOptions( options, value = null ) {

		const dom = this.dom;
		const defaultValue = dom.value;

		let containsDefaultValue = false;

		this.options = options;
		dom.innerHTML = '';

		for ( let index = 0; index < options.length; index ++ ) {

			let opt = options[ index ];

			if ( typeof opt === 'string' ) {

				opt = { name: opt, value: index };

			}

			const option = document.createElement( 'option' );
			option.innerText = opt.name;
			option.value = opt.value;

			if ( containsDefaultValue === false && defaultValue === opt.value ) {

				containsDefaultValue = true;

			}

			dom.append( option );

		}

		dom.value = value !== null ? value : containsDefaultValue ? defaultValue : '';

		return this;

	}

	getOptions() {

		return this._options;

	}

	serialize( data ) {

		data.options = [ ...this.options ];

		super.serialize( data );

	}

	deserialize( data ) {

		const currentOptions = this.options;

		if ( currentOptions.length === 0 ) {

			this.setOptions( data.options );

		}

		super.deserialize( data );

	}

}
```
</details>

#### Methods

##### `setOptions(options: any, value: any): this`

<details><summary>Code</summary>

```ts
setOptions( options, value = null ) {

		const dom = this.dom;
		const defaultValue = dom.value;

		let containsDefaultValue = false;

		this.options = options;
		dom.innerHTML = '';

		for ( let index = 0; index < options.length; index ++ ) {

			let opt = options[ index ];

			if ( typeof opt === 'string' ) {

				opt = { name: opt, value: index };

			}

			const option = document.createElement( 'option' );
			option.innerText = opt.name;
			option.value = opt.value;

			if ( containsDefaultValue === false && defaultValue === opt.value ) {

				containsDefaultValue = true;

			}

			dom.append( option );

		}

		dom.value = value !== null ? value : containsDefaultValue ? defaultValue : '';

		return this;

	}
```
</details>

##### `getOptions(): any`

<details><summary>Code</summary>

```ts
getOptions() {

		return this._options;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		data.options = [ ...this.options ];

		super.serialize( data );

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		const currentOptions = this.options;

		if ( currentOptions.length === 0 ) {

			this.setOptions( data.options );

		}

		super.deserialize( data );

	}
```
</details>

### `SliderInput`

<details><summary>Class Code</summary>

```ts
class SliderInput extends Input {

	static get type() {

		return 'SliderInput';

	}

	constructor( value = 0, min = 0, max = 100 ) {

		const dom = document.createElement( 'f-subinputs' );
		super( dom );

		value = Math.min( Math.max( value, min ), max );

		const step = getStep( min, max );

		const rangeDOM = document.createElement( 'input' );
		rangeDOM.type = 'range';
		rangeDOM.min = min;
		rangeDOM.max = max;
		rangeDOM.step = step;
		rangeDOM.value = value;

		const field = new NumberInput( value, min, max, step );
		field.dom.className = 'range-value';
		field.onChange( () => {

			rangeDOM.value = field.getValue();

			this.dispatchEvent( new Event( 'change' ) );

		} );

		field.addEventListener( 'range', () => {

			rangeDOM.min = field.min;
			rangeDOM.max = field.max;
			rangeDOM.step = field.step;
			rangeDOM.value = field.getValue();

		} );

		dom.append( rangeDOM );
		dom.append( field.dom );

		this.rangeDOM = rangeDOM;
		this.field = field;

		const updateRangeValue = () => {

			let value = Number( rangeDOM.value );

			if ( value !== this.max && value + this.step >= this.max ) {

				// fix not end range fraction

				rangeDOM.value = value = this.max;

			}

			this.field.setValue( value );

		};

		draggableDOM( rangeDOM, () => {

			updateRangeValue();

			this.dispatchEvent( new Event( 'change' ) );

		}, { className: '' } );

	}

	get min() {

		return this.field.min;

	}

	get max() {

		return this.field.max;

	}

	get step() {

		return this.field.step;

	}

	setRange( min, max ) {

		this.field.setRange( min, max, getStep( min, max ) );

		this.dispatchEvent( new Event( 'range' ) );
		this.dispatchEvent( new Event( 'change' ) );

		return this;

	}

	setValue( val, dispatch = true ) {

		this.field.setValue( val );
		this.rangeDOM.value = val;

		if ( dispatch ) this.dispatchEvent( new Event( 'change' ) );

		return this;

	}

	getValue() {

		return this.field.getValue();

	}

	serialize( data ) {

		data.min = this.min;
		data.max = this.max;

		super.serialize( data );

	}

	deserialize( data ) {

		const { min, max } = data;

		this.setRange( min, max );

		super.deserialize( data );

	}

}
```
</details>

#### Methods

##### `setRange(min: any, max: any): this`

<details><summary>Code</summary>

```ts
setRange( min, max ) {

		this.field.setRange( min, max, getStep( min, max ) );

		this.dispatchEvent( new Event( 'range' ) );
		this.dispatchEvent( new Event( 'change' ) );

		return this;

	}
```
</details>

##### `setValue(val: any, dispatch: boolean): this`

<details><summary>Code</summary>

```ts
setValue( val, dispatch = true ) {

		this.field.setValue( val );
		this.rangeDOM.value = val;

		if ( dispatch ) this.dispatchEvent( new Event( 'change' ) );

		return this;

	}
```
</details>

##### `getValue(): number`

<details><summary>Code</summary>

```ts
getValue() {

		return this.field.getValue();

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		data.min = this.min;
		data.max = this.max;

		super.serialize( data );

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		const { min, max } = data;

		this.setRange( min, max );

		super.deserialize( data );

	}
```
</details>

### `StringInput`

<details><summary>Class Code</summary>

```ts
class StringInput extends Input {

	static get type() {

		return 'StringInput';

	}

	constructor( value = '' ) {

		const dom = document.createElement( 'f-string' );
		super( dom );

		const inputDOM = document.createElement( 'input' );

		dom.append( inputDOM );

		inputDOM.type = 'text';
		inputDOM.value = value;
		inputDOM.spellcheck = false;
		inputDOM.autocomplete = 'off';

		this._buttonsDOM = null;
		this._datalistDOM = null;

		this.iconDOM = null;
		this.inputDOM = inputDOM;

		this.buttons = [];

		inputDOM.onblur = () => {

			this.dispatchEvent( new Event( 'blur' ) );

		};

		inputDOM.onchange = () => {

			this.dispatchEvent( new Event( 'change' ) );

		};

		let keyDownStr = '';

		inputDOM.onkeydown = () => keyDownStr = inputDOM.value;

		inputDOM.onkeyup = ( e ) => {

			if ( e.key === 'Enter' ) {

				e.target.blur();

			}

			e.stopPropagation();

			if ( keyDownStr !== inputDOM.value ) {

				this.dispatchEvent( new Event( 'change' ) );

			}

		};

	}

	setPlaceHolder( text ) {

		this.inputDOM.placeholder = text;

		return this;

	}

	setIcon( value ) {

		this.iconDOM = this.iconDOM || document.createElement( 'i' );
		this.iconDOM.setAttribute( 'type', 'icon' );
		this.iconDOM.className = value;

		if ( value ) this.dom.prepend( this.iconDOM );
		else this.iconDOM.remove();

		return this;

	}

	getIcon() {

		return this.iconInput ? this.iconInput.getIcon() : '';

	}

	addButton( button ) {

		this.buttonsDOM.prepend( button.iconDOM );

		this.buttons.push( button );

		return this;

	}

	addOption( value ) {

		const option = document.createElement( 'option' );
		option.value = value;

		this.datalistDOM.append( option );

		return this;

	}

	clearOptions() {

		this.datalistDOM.remove();

	}

	get datalistDOM() {

		let dom = this._datalistDOM;

		if ( dom === null ) {

			const datalistId = 'input-dt-' + this.id;

			dom = document.createElement( 'datalist' );
			dom.id = datalistId;

			this._datalistDOM = dom;

			this.inputDOM.autocomplete = 'on';
			this.inputDOM.setAttribute( 'list', datalistId );

			this.dom.prepend( dom );

		}

		return dom;

	}

	get buttonsDOM() {

		let dom = this._buttonsDOM;

		if ( dom === null ) {

			dom = document.createElement( 'f-buttons' );

			this._buttonsDOM = dom;

			this.dom.prepend( dom );

		}

		return dom;

	}

	getInput() {

		return this.inputDOM;

	}

}
```
</details>

#### Methods

##### `setPlaceHolder(text: any): this`

<details><summary>Code</summary>

```ts
setPlaceHolder( text ) {

		this.inputDOM.placeholder = text;

		return this;

	}
```
</details>

##### `setIcon(value: any): this`

<details><summary>Code</summary>

```ts
setIcon( value ) {

		this.iconDOM = this.iconDOM || document.createElement( 'i' );
		this.iconDOM.setAttribute( 'type', 'icon' );
		this.iconDOM.className = value;

		if ( value ) this.dom.prepend( this.iconDOM );
		else this.iconDOM.remove();

		return this;

	}
```
</details>

##### `getIcon(): any`

<details><summary>Code</summary>

```ts
getIcon() {

		return this.iconInput ? this.iconInput.getIcon() : '';

	}
```
</details>

##### `addButton(button: any): this`

<details><summary>Code</summary>

```ts
addButton( button ) {

		this.buttonsDOM.prepend( button.iconDOM );

		this.buttons.push( button );

		return this;

	}
```
</details>

##### `addOption(value: any): this`

<details><summary>Code</summary>

```ts
addOption( value ) {

		const option = document.createElement( 'option' );
		option.value = value;

		this.datalistDOM.append( option );

		return this;

	}
```
</details>

##### `clearOptions(): void`

<details><summary>Code</summary>

```ts
clearOptions() {

		this.datalistDOM.remove();

	}
```
</details>

##### `getInput(): HTMLInputElement`

<details><summary>Code</summary>

```ts
getInput() {

		return this.inputDOM;

	}
```
</details>

### `TextInput`

<details><summary>Class Code</summary>

```ts
class TextInput extends Input {

	static get type() {

		return 'TextInput';

	}

	constructor( innerText = '' ) {

		const dom = document.createElement( 'textarea' );
		super( dom );

		dom.innerText = innerText;

		dom.classList.add( 'f-scroll' );

		dom.onblur = () => {

			this.dispatchEvent( new Event( 'blur' ) );

		};

		dom.onchange = () => {

			this.dispatchEvent( new Event( 'change' ) );

		};

		dom.onkeyup = ( e ) => {

			if ( e.key === 'Enter' ) {

				e.target.blur();

			}

			e.stopPropagation();

			this.dispatchEvent( new Event( 'change' ) );

		};

	}

}
```
</details>

### `ToggleInput`

<details><summary>Class Code</summary>

```ts
class ToggleInput extends Input {

	static get type() {

		return 'ToggleInput';

	}

	constructor( value = false ) {

		const dom = document.createElement( 'input' );
		super( dom );

		dom.type = 'checkbox';
		dom.className = 'toggle';
		dom.checked = value;

		dom.onclick = () => this.dispatchEvent( new Event( 'click' ) );
		dom.onchange = () => this.dispatchEvent( new Event( 'change' ) );

	}

	setValue( val ) {

		this.dom.checked = val;

		this.dispatchEvent( new Event( 'change' ) );

		return this;

	}

	getValue() {

		return this.dom.checked;

	}

}
```
</details>

#### Methods

##### `setValue(val: any): this`

<details><summary>Code</summary>

```ts
setValue( val ) {

		this.dom.checked = val;

		this.dispatchEvent( new Event( 'change' ) );

		return this;

	}
```
</details>

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.dom.checked;

	}
```
</details>

### `TreeViewNode`

<details><summary>Class Code</summary>

```ts
class TreeViewNode {

	constructor( name = '' ) {

		const dom = document.createElement( 'f-treeview-node' );
		const labelDOM = document.createElement( 'f-treeview-label' );
		const inputDOM = document.createElement( 'input' );

		const labelSpam = document.createElement( 'spam' );
		labelDOM.append( labelSpam );

		labelSpam.innerText = name;

		inputDOM.type = 'checkbox';

		dom.append( inputDOM );
		dom.append( labelDOM );

		this.dom = dom;
		this.childrenDOM = null;
		this.labelSpam = labelSpam;
		this.labelDOM = labelDOM;
		this.inputDOM = inputDOM;
		this.iconDOM = null;

		this.parent = null;
		this.children = [];

		this.selected = false;

		this.events = {
			'change': [],
			'click': []
		};

		dom.addEventListener( 'click', ( ) => {

			dispatchEventList( this.events.click, this );

		} );

	}

	setLabel( value ) {

		this.labelSpam.innerText = value;

		return this;

	}

	getLabel() {

		return this.labelSpam.innerText;

	}

	add( node ) {

		let childrenDOM = this.childrenDOM;

		if ( this.childrenDOM === null ) {

			const dom = this.dom;

			const arrowDOM = document.createElement( 'f-arrow' );
			childrenDOM = document.createElement( 'f-treeview-children' );

			dom.append( arrowDOM );
			dom.append( childrenDOM );

			this.childrenDOM = childrenDOM;

		}

		this.children.push( node );
		childrenDOM.append( node.dom );

		node.parent = this;

		return this;

	}

	setOpened( value ) {

		this.inputDOM.checked = value;

		return this;

	}

	getOpened() {

		return this.inputDOM.checkbox;

	}

	setIcon( value ) {

		this.iconDOM = this.iconDOM || document.createElement( 'i' );
		this.iconDOM.className = value;

		if ( value ) this.labelDOM.prepend( this.iconDOM );
		else this.iconDOM.remove();

		return this;

	}

	getIcon() {

		return this.iconDOM ? this.iconDOM.className : null;

	}

	setVisible( value ) {

		this.dom.style.display = value ? '' : 'none';

		return this;

	}

	setSelected( value ) {

		if ( this.selected === value ) return this;

		if ( value ) this.dom.classList.add( 'selected' );
		else this.dom.classList.remove( 'selected' );

		this.selected = value;

		return this;

	}

	onClick( callback ) {

		this.events.click.push( callback );

		return this;

	}

}
```
</details>

#### Methods

##### `setLabel(value: any): this`

<details><summary>Code</summary>

```ts
setLabel( value ) {

		this.labelSpam.innerText = value;

		return this;

	}
```
</details>

##### `getLabel(): string`

<details><summary>Code</summary>

```ts
getLabel() {

		return this.labelSpam.innerText;

	}
```
</details>

##### `add(node: any): this`

<details><summary>Code</summary>

```ts
add( node ) {

		let childrenDOM = this.childrenDOM;

		if ( this.childrenDOM === null ) {

			const dom = this.dom;

			const arrowDOM = document.createElement( 'f-arrow' );
			childrenDOM = document.createElement( 'f-treeview-children' );

			dom.append( arrowDOM );
			dom.append( childrenDOM );

			this.childrenDOM = childrenDOM;

		}

		this.children.push( node );
		childrenDOM.append( node.dom );

		node.parent = this;

		return this;

	}
```
</details>

##### `setOpened(value: any): this`

<details><summary>Code</summary>

```ts
setOpened( value ) {

		this.inputDOM.checked = value;

		return this;

	}
```
</details>

##### `getOpened(): any`

<details><summary>Code</summary>

```ts
getOpened() {

		return this.inputDOM.checkbox;

	}
```
</details>

##### `setIcon(value: any): this`

<details><summary>Code</summary>

```ts
setIcon( value ) {

		this.iconDOM = this.iconDOM || document.createElement( 'i' );
		this.iconDOM.className = value;

		if ( value ) this.labelDOM.prepend( this.iconDOM );
		else this.iconDOM.remove();

		return this;

	}
```
</details>

##### `getIcon(): any`

<details><summary>Code</summary>

```ts
getIcon() {

		return this.iconDOM ? this.iconDOM.className : null;

	}
```
</details>

##### `setVisible(value: any): this`

<details><summary>Code</summary>

```ts
setVisible( value ) {

		this.dom.style.display = value ? '' : 'none';

		return this;

	}
```
</details>

##### `setSelected(value: any): this`

<details><summary>Code</summary>

```ts
setSelected( value ) {

		if ( this.selected === value ) return this;

		if ( value ) this.dom.classList.add( 'selected' );
		else this.dom.classList.remove( 'selected' );

		this.selected = value;

		return this;

	}
```
</details>

##### `onClick(callback: any): this`

<details><summary>Code</summary>

```ts
onClick( callback ) {

		this.events.click.push( callback );

		return this;

	}
```
</details>

### `TreeViewInput`

<details><summary>Class Code</summary>

```ts
class TreeViewInput extends Input {

	static get type() {

		return 'TreeViewInput';

	}

	constructor( options = [] ) {

		const dom = document.createElement( 'f-treeview' );
		super( dom );

		const childrenDOM = document.createElement( 'f-treeview-children' );
		dom.append( childrenDOM );

		dom.setAttribute( 'type', 'tree' );

		this.childrenDOM = childrenDOM;

		this.children = [];

	}

	add( node ) {

		this.children.push( node );
		this.childrenDOM.append( node.dom );

		return this;

	}

	serialize( data ) {

		//data.options = [ ...this.options ];

		super.serialize( data );

	}

	deserialize( data ) {

		/*const currentOptions = this.options;

		if ( currentOptions.length === 0 ) {

			this.setOptions( data.options );

		}*/

		super.deserialize( data );

	}

}
```
</details>

#### Methods

##### `add(node: any): this`

<details><summary>Code</summary>

```ts
add( node ) {

		this.children.push( node );
		this.childrenDOM.append( node.dom );

		return this;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		//data.options = [ ...this.options ];

		super.serialize( data );

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		/*const currentOptions = this.options;

		if ( currentOptions.length === 0 ) {

			this.setOptions( data.options );

		}*/

		super.deserialize( data );

	}
```
</details>

### `Loader`

<details><summary>Class Code</summary>

```ts
class Loader extends EventTarget {

	static get type() {

		return 'Loader';

	}

	constructor( parseType = Loader.DEFAULT ) {

		super();

		this.parseType = parseType;

		this.events = {
			'load': []
		};

	}

	setParseType( type ) {

		this.parseType = type;

		return this;

	}

	getParseType() {

		return this.parseType;

	}

	onLoad( callback ) {

		this.events.load.push( callback );

		return this;

	}

	async load( url, lib = {} ) {

		return await fetch( url )
			.then( response => response.json() )
			.then( result => {

				this.data = this.parse( result, lib );

				dispatchEventList( this.events.load, this );

				return this.data;

			} )
			.catch( err => {

				console.error( 'Loader:', err );

			} );

	}

	parse( json, lib = {} ) {

		json = this._parseObjects( json, lib );

		const parseType = this.parseType;

		if ( parseType === Loader.DEFAULT ) {

			const type = json.type;

			const flowClass = lib[ type ] ? lib[ type ] : ( LoaderLib[ type ] || Flow[ type ] );
			const flowObj = new flowClass();

			if ( flowObj.getSerializable() ) {

				flowObj.deserialize( json );

			}

			return flowObj;

		} else if ( parseType === Loader.OBJECTS ) {

			return json;

		}

	}

	_parseObjects( json, lib = {} ) {

		json = { ...json };

		const objects = {};

		for ( const id in json.objects ) {

			const obj = json.objects[ id ];
			obj.objects = objects;

			const type = obj.type;
			const flowClass = lib[ type ] ? lib[ type ] : ( LoaderLib[ type ] || Flow[ type ] );

			if ( ! flowClass ) {

				console.error( `Class "${ type }" not found!` );

			}

			objects[ id ] = new flowClass();
			objects[ id ].deserializeLib( json.objects[ id ], lib );

		}

		const ref = new Map();

		const deserializePass = ( prop = null ) => {

			for ( const id in json.objects ) {

				const newObject = objects[ id ];

				if ( ref.has( newObject ) === false && ( prop === null || newObject[ prop ] === true ) ) {

					ref.set( newObject, true );

					if ( newObject.getSerializable() ) {

						newObject.deserialize( json.objects[ id ] );

					}

				}

			}

		};

		deserializePass( 'isNode' );
		deserializePass( 'isElement' );
		deserializePass( 'isInput' );
		deserializePass();

		json.objects = objects;

		return json;

	}

}
```
</details>

#### Methods

##### `setParseType(type: any): this`

<details><summary>Code</summary>

```ts
setParseType( type ) {

		this.parseType = type;

		return this;

	}
```
</details>

##### `getParseType(): string`

<details><summary>Code</summary>

```ts
getParseType() {

		return this.parseType;

	}
```
</details>

##### `onLoad(callback: any): this`

<details><summary>Code</summary>

```ts
onLoad( callback ) {

		this.events.load.push( callback );

		return this;

	}
```
</details>

##### `load(url: any, lib: {}): Promise<any>`

<details><summary>Code</summary>

```ts
async load( url, lib = {} ) {

		return await fetch( url )
			.then( response => response.json() )
			.then( result => {

				this.data = this.parse( result, lib );

				dispatchEventList( this.events.load, this );

				return this.data;

			} )
			.catch( err => {

				console.error( 'Loader:', err );

			} );

	}
```
</details>

##### `parse(json: any, lib: {}): any`

<details><summary>Code</summary>

```ts
parse( json, lib = {} ) {

		json = this._parseObjects( json, lib );

		const parseType = this.parseType;

		if ( parseType === Loader.DEFAULT ) {

			const type = json.type;

			const flowClass = lib[ type ] ? lib[ type ] : ( LoaderLib[ type ] || Flow[ type ] );
			const flowObj = new flowClass();

			if ( flowObj.getSerializable() ) {

				flowObj.deserialize( json );

			}

			return flowObj;

		} else if ( parseType === Loader.OBJECTS ) {

			return json;

		}

	}
```
</details>

##### `_parseObjects(json: any, lib: {}): any`

<details><summary>Code</summary>

```ts
_parseObjects( json, lib = {} ) {

		json = { ...json };

		const objects = {};

		for ( const id in json.objects ) {

			const obj = json.objects[ id ];
			obj.objects = objects;

			const type = obj.type;
			const flowClass = lib[ type ] ? lib[ type ] : ( LoaderLib[ type ] || Flow[ type ] );

			if ( ! flowClass ) {

				console.error( `Class "${ type }" not found!` );

			}

			objects[ id ] = new flowClass();
			objects[ id ].deserializeLib( json.objects[ id ], lib );

		}

		const ref = new Map();

		const deserializePass = ( prop = null ) => {

			for ( const id in json.objects ) {

				const newObject = objects[ id ];

				if ( ref.has( newObject ) === false && ( prop === null || newObject[ prop ] === true ) ) {

					ref.set( newObject, true );

					if ( newObject.getSerializable() ) {

						newObject.deserialize( json.objects[ id ] );

					}

				}

			}

		};

		deserializePass( 'isNode' );
		deserializePass( 'isElement' );
		deserializePass( 'isInput' );
		deserializePass();

		json.objects = objects;

		return json;

	}
```
</details>


---