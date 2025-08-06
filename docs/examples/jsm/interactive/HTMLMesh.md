[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `HTMLMesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 17 |
| 🧱 Classes | 2 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 38 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/interactive/HTMLMesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CanvasTexture` | `three` |
| `LinearFilter` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `PlaneGeometry` | `three` |
| `SRGBColorSpace` | `three` |
| `Color` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `texture` | `HTMLTexture` | let/var | `new HTMLTexture( dom )` | ✗ |
| `geometry` | `any` | let/var | `new PlaneGeometry( texture.image.width * 0.001, texture.image.height * 0.001 )` | ✗ |
| `material` | `any` | let/var | `new MeshBasicMaterial( { map: texture, toneMapped: false, transparent: true } )` | ✗ |
| `observer` | `MutationObserver` | let/var | `new MutationObserver( () => { if ( ! this.scheduleUpdate ) { // ideally shoul...` | ✗ |
| `config` | `{ attributes: boolean; childList: boo...` | let/var | `{ attributes: true, childList: true, subtree: true, characterData: true }` | ✗ |
| `canvases` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `clips` | `any[]` | let/var | `[]` | ✗ |
| `isClipping` | `boolean` | let/var | `false` | ✗ |
| `minX` | `number` | let/var | `- Infinity` | ✗ |
| `minY` | `number` | let/var | `- Infinity` | ✗ |
| `maxX` | `number` | let/var | `Infinity` | ✗ |
| `maxY` | `number` | let/var | `Infinity` | ✗ |
| `clip` | `any` | let/var | `clips[ i ]` | ✗ |
| `borderWidth` | `any` | let/var | `style[ which + 'Width' ]` | ✗ |
| `borderStyle` | `any` | let/var | `style[ which + 'Style' ]` | ✗ |
| `borderColor` | `any` | let/var | `style[ which + 'Color' ]` | ✗ |
| `x` | `number` | let/var | `0` | ✗ |
| `y` | `number` | let/var | `0` | ✗ |
| `width` | `number` | let/var | `0` | ✗ |
| `height` | `number` | let/var | `0` | ✗ |
| `dpr` | `number` | let/var | `window.devicePixelRatio` | ✗ |
| `backgroundColor` | `any` | let/var | `style.backgroundColor` | ✗ |
| `borders` | `string[]` | let/var | `[ 'borderTop', 'borderLeft', 'borderBottom', 'borderRight' ]` | ✗ |
| `match` | `boolean` | let/var | `true` | ✗ |
| `prevBorder` | `any` | let/var | `null` | ✗ |
| `accentColor` | `any` | let/var | `style.accentColor` | ✗ |
| `accentTextColor` | `"white" \| "#111111"` | let/var | `luminance < 0.5 ? 'white' : '#111111'` | ✗ |
| `currentTextAlign` | `any` | let/var | `context.textAlign` | ✗ |
| `properties` | `{ color: string; fontFamily: any; fon...` | let/var | `{ color: accentTextColor, fontFamily: style.fontFamily, fontSize: height + 'p...` | ✗ |
| `position` | `number` | let/var | `( ( value - min ) / ( max - min ) ) * ( width - height )` | ✗ |
| `displayValue` | `string` | let/var | `element.type === 'password' ? '*'.repeat( element.value.length ) : element.value` | ✗ |
| `isClipping` | `boolean` | let/var | `style.overflow === 'auto' \|\| style.overflow === 'hidden'` | ✗ |
| `clipper` | `any` | let/var | `new Clipper( context )` | ✗ |
| `mouseEventInit` | `{ clientX: any; clientY: any; view: a...` | let/var | `{ clientX: ( x * element.offsetWidth ) + element.offsetLeft, clientY: ( y * e...` | ✗ |
| `width` | `any` | let/var | `rect.width` | ✗ |
| `offsetX` | `number` | let/var | `x - rect.x` | ✗ |
| `proportion` | `number` | let/var | `offsetX / width` | ✗ |


---

## Functions

### `onEvent(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `material.map.dispatchDOMEvent`

<details><summary>Code</summary>

```typescript
function onEvent( event ) {

			material.map.dispatchDOMEvent( event );

		}
```
</details>

### `HTMLTexture.dispatchDOMEvent(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `htmlevent`

<details><summary>Code</summary>

```typescript
dispatchDOMEvent( event ) {

		if ( event.data ) {

			htmlevent( this.dom, event.type, event.data.x, event.data.y );

		}

	}
```
</details>

### `HTMLTexture.update(): void`

**Returns:** `void`

**Calls:**

- `html2canvas`

<details><summary>Code</summary>

```typescript
update() {

		this.image = html2canvas( this.dom );
		this.needsUpdate = true;

		this.scheduleUpdate = null;

	}
```
</details>

### `HTMLTexture.dispose(): void`

**Returns:** `void`

**Calls:**

- `this.observer.disconnect`
- `clearTimeout`
- `super.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		if ( this.observer ) {

			this.observer.disconnect();

		}

		this.scheduleUpdate = clearTimeout( this.scheduleUpdate );

		super.dispose();

	}
```
</details>

### `html2canvas(element: any): any`

**Parameters:**

- **`element`** `any`

**Returns:** `any`

**Calls:**

- `document.createRange`
- `context.restore`
- `Math.max`
- `Math.min`
- `context.save`
- `context.beginPath`
- `context.rect`
- `context.clip`
- `clips.push`
- `doClip`
- `clips.pop`
- `string.toUpperCase`
- `context.fillText`
- `parseFloat`
- `context.moveTo`
- `context.arcTo`
- `context.closePath`
- `context.lineTo`
- `context.stroke`
- `range.selectNode`
- `range.getBoundingClientRect`
- `drawText`
- `element.nodeValue.trim`
- `element.getBoundingClientRect`
- `context.scale`
- `context.drawImage`
- `window.getComputedStyle`
- `buildRectPath`
- `context.fill`
- `drawBorder`
- `color.set`
- `Math.sqrt`
- `[ 'min', 'max', 'value' ].map`
- `clipper.add`
- `'*'.repeat`
- `parseInt`
- `clipper.remove`
- `drawElement`
- `canvases.get`
- `document.createElement`
- `canvases.set`
- `canvas.getContext`
- `context.clearRect`

**Internal Comments:**
```
// Do not render invisible elements, comments and scripts.
// text (x4)
// Canvas element (x2)
// Get the border of the element used for fill and border (x3)
// If all the borders match then stroke the round rectangle (x2)
// They all match so stroke the rectangle from before allows for border-radius (x2)
// Otherwise draw individual borders (x3)
/*
		// debug
		context.strokeStyle = '#' + Math.random().toString( 16 ).slice( - 3 );
		context.strokeRect( x - 0.5, y - 0.5, width + 1, height + 1 );
		*/ (x2)
// console.time( 'drawElement' ); (x4)
// console.timeEnd( 'drawElement' );
```

<details><summary>Code</summary>

```typescript
function html2canvas( element ) {

	const range = document.createRange();
	const color = new Color();

	function Clipper( context ) {

		const clips = [];
		let isClipping = false;

		function doClip() {

			if ( isClipping ) {

				isClipping = false;
				context.restore();

			}

			if ( clips.length === 0 ) return;

			let minX = - Infinity, minY = - Infinity;
			let maxX = Infinity, maxY = Infinity;

			for ( let i = 0; i < clips.length; i ++ ) {

				const clip = clips[ i ];

				minX = Math.max( minX, clip.x );
				minY = Math.max( minY, clip.y );
				maxX = Math.min( maxX, clip.x + clip.width );
				maxY = Math.min( maxY, clip.y + clip.height );

			}

			context.save();
			context.beginPath();
			context.rect( minX, minY, maxX - minX, maxY - minY );
			context.clip();

			isClipping = true;

		}

		return {

			add: function ( clip ) {

				clips.push( clip );
				doClip();

			},

			remove: function () {

				clips.pop();
				doClip();

			}

		};

	}

	function drawText( style, x, y, string ) {

		if ( string !== '' ) {

			if ( style.textTransform === 'uppercase' ) {

				string = string.toUpperCase();

			}

			context.font = style.fontWeight + ' ' + style.fontSize + ' ' + style.fontFamily;
			context.textBaseline = 'top';
			context.fillStyle = style.color;
			context.fillText( string, x, y + parseFloat( style.fontSize ) * 0.1 );

		}

	}

	function buildRectPath( x, y, w, h, r ) {

		if ( w < 2 * r ) r = w / 2;
		if ( h < 2 * r ) r = h / 2;

		context.beginPath();
		context.moveTo( x + r, y );
		context.arcTo( x + w, y, x + w, y + h, r );
		context.arcTo( x + w, y + h, x, y + h, r );
		context.arcTo( x, y + h, x, y, r );
		context.arcTo( x, y, x + w, y, r );
		context.closePath();

	}

	function drawBorder( style, which, x, y, width, height ) {

		const borderWidth = style[ which + 'Width' ];
		const borderStyle = style[ which + 'Style' ];
		const borderColor = style[ which + 'Color' ];

		if ( borderWidth !== '0px' && borderStyle !== 'none' && borderColor !== 'transparent' && borderColor !== 'rgba(0, 0, 0, 0)' ) {

			context.strokeStyle = borderColor;
			context.lineWidth = parseFloat( borderWidth );
			context.beginPath();
			context.moveTo( x, y );
			context.lineTo( x + width, y + height );
			context.stroke();

		}

	}

	function drawElement( element, style ) {

		// Do not render invisible elements, comments and scripts.
		if ( element.nodeType === Node.COMMENT_NODE || element.nodeName === 'SCRIPT' || ( element.style && element.style.display === 'none' ) ) {

			return;

		}

		let x = 0, y = 0, width = 0, height = 0;

		if ( element.nodeType === Node.TEXT_NODE ) {

			// text

			range.selectNode( element );

			const rect = range.getBoundingClientRect();

			x = rect.left - offset.left - 0.5;
			y = rect.top - offset.top - 0.5;
			width = rect.width;
			height = rect.height;

			drawText( style, x, y, element.nodeValue.trim() );

		} else if ( element instanceof HTMLCanvasElement ) {

			// Canvas element

			const rect = element.getBoundingClientRect();

			x = rect.left - offset.left - 0.5;
			y = rect.top - offset.top - 0.5;

		        context.save();
			const dpr = window.devicePixelRatio;
			context.scale( 1 / dpr, 1 / dpr );
			context.drawImage( element, x, y );
			context.restore();

		} else if ( element instanceof HTMLImageElement ) {

			const rect = element.getBoundingClientRect();

			x = rect.left - offset.left - 0.5;
			y = rect.top - offset.top - 0.5;
			width = rect.width;
			height = rect.height;

			context.drawImage( element, x, y, width, height );

		} else {

			const rect = element.getBoundingClientRect();

			x = rect.left - offset.left - 0.5;
			y = rect.top - offset.top - 0.5;
			width = rect.width;
			height = rect.height;

			style = window.getComputedStyle( element );

			// Get the border of the element used for fill and border

			buildRectPath( x, y, width, height, parseFloat( style.borderRadius ) );

			const backgroundColor = style.backgroundColor;

			if ( backgroundColor !== 'transparent' && backgroundColor !== 'rgba(0, 0, 0, 0)' ) {

				context.fillStyle = backgroundColor;
				context.fill();

			}

			// If all the borders match then stroke the round rectangle

			const borders = [ 'borderTop', 'borderLeft', 'borderBottom', 'borderRight' ];

			let match = true;
			let prevBorder = null;

			for ( const border of borders ) {

				if ( prevBorder !== null ) {

					match = ( style[ border + 'Width' ] === style[ prevBorder + 'Width' ] ) &&
					( style[ border + 'Color' ] === style[ prevBorder + 'Color' ] ) &&
					( style[ border + 'Style' ] === style[ prevBorder + 'Style' ] );

				}

				if ( match === false ) break;

				prevBorder = border;

			}

			if ( match === true ) {

				// They all match so stroke the rectangle from before allows for border-radius

				const width = parseFloat( style.borderTopWidth );

				if ( style.borderTopWidth !== '0px' && style.borderTopStyle !== 'none' && style.borderTopColor !== 'transparent' && style.borderTopColor !== 'rgba(0, 0, 0, 0)' ) {

					context.strokeStyle = style.borderTopColor;
					context.lineWidth = width;
					context.stroke();

				}

			} else {

				// Otherwise draw individual borders

				drawBorder( style, 'borderTop', x, y, width, 0 );
				drawBorder( style, 'borderLeft', x, y, 0, height );
				drawBorder( style, 'borderBottom', x, y + height, width, 0 );
				drawBorder( style, 'borderRight', x + width, y, 0, height );

			}

			if ( element instanceof HTMLInputElement ) {

				let accentColor = style.accentColor;

				if ( accentColor === undefined || accentColor === 'auto' ) accentColor = style.color;

				color.set( accentColor );

				const luminance = Math.sqrt( 0.299 * ( color.r ** 2 ) + 0.587 * ( color.g ** 2 ) + 0.114 * ( color.b ** 2 ) );
				const accentTextColor = luminance < 0.5 ? 'white' : '#111111';

				if ( element.type === 'radio' ) {

					buildRectPath( x, y, width, height, height );

					context.fillStyle = 'white';
					context.strokeStyle = accentColor;
					context.lineWidth = 1;
					context.fill();
					context.stroke();

					if ( element.checked ) {

						buildRectPath( x + 2, y + 2, width - 4, height - 4, height );

						context.fillStyle = accentColor;
						context.strokeStyle = accentTextColor;
						context.lineWidth = 2;
						context.fill();
						context.stroke();

					}

				}

				if ( element.type === 'checkbox' ) {

					buildRectPath( x, y, width, height, 2 );

					context.fillStyle = element.checked ? accentColor : 'white';
					context.strokeStyle = element.checked ? accentTextColor : accentColor;
					context.lineWidth = 1;
					context.stroke();
					context.fill();

					if ( element.checked ) {

						const currentTextAlign = context.textAlign;

						context.textAlign = 'center';

						const properties = {
							color: accentTextColor,
							fontFamily: style.fontFamily,
							fontSize: height + 'px',
							fontWeight: 'bold'
						};

						drawText( properties, x + ( width / 2 ), y, '✔' );

						context.textAlign = currentTextAlign;

					}

				}

				if ( element.type === 'range' ) {

					const [ min, max, value ] = [ 'min', 'max', 'value' ].map( property => parseFloat( element[ property ] ) );
					const position = ( ( value - min ) / ( max - min ) ) * ( width - height );

					buildRectPath( x, y + ( height / 4 ), width, height / 2, height / 4 );
					context.fillStyle = accentTextColor;
					context.strokeStyle = accentColor;
					context.lineWidth = 1;
					context.fill();
					context.stroke();

					buildRectPath( x, y + ( height / 4 ), position + ( height / 2 ), height / 2, height / 4 );
					context.fillStyle = accentColor;
					context.fill();

					buildRectPath( x + position, y, height, height, height / 2 );
					context.fillStyle = accentColor;
					context.fill();

				}

				if ( element.type === 'color' || element.type === 'text' || element.type === 'number' || element.type === 'email' || element.type === 'password' ) {

					clipper.add( { x: x, y: y, width: width, height: height } );

					const displayValue = element.type === 'password' ? '*'.repeat( element.value.length ) : element.value;

					drawText( style, x + parseInt( style.paddingLeft ), y + parseInt( style.paddingTop ), displayValue );

					clipper.remove();

				}

			}

		}

		/*
		// debug
		context.strokeStyle = '#' + Math.random().toString( 16 ).slice( - 3 );
		context.strokeRect( x - 0.5, y - 0.5, width + 1, height + 1 );
		*/

		const isClipping = style.overflow === 'auto' || style.overflow === 'hidden';

		if ( isClipping ) clipper.add( { x: x, y: y, width: width, height: height } );

		for ( let i = 0; i < element.childNodes.length; i ++ ) {

			drawElement( element.childNodes[ i ], style );

		}

		if ( isClipping ) clipper.remove();

	}

	const offset = element.getBoundingClientRect();

	let canvas = canvases.get( element );

	if ( canvas === undefined ) {

		canvas = document.createElement( 'canvas' );
		canvas.width = offset.width;
		canvas.height = offset.height;
		canvases.set( element, canvas );

	}

	const context = canvas.getContext( '2d'/*, { alpha: false }*/ );

	const clipper = new Clipper( context );

	// console.time( 'drawElement' );

	context.clearRect( 0, 0, canvas.width, canvas.height );

	drawElement( element );

	// console.timeEnd( 'drawElement' );

	return canvas;

}
```
</details>

### `Clipper(context: any): { add: (clip: any) => void; remove: () => void; }`

**Parameters:**

- **`context`** `any`

**Returns:** `{ add: (clip: any) => void; remove: () => void; }`

**Calls:**

- `context.restore`
- `Math.max`
- `Math.min`
- `context.save`
- `context.beginPath`
- `context.rect`
- `context.clip`
- `clips.push`
- `doClip`
- `clips.pop`

<details><summary>Code</summary>

```typescript
function Clipper( context ) {

		const clips = [];
		let isClipping = false;

		function doClip() {

			if ( isClipping ) {

				isClipping = false;
				context.restore();

			}

			if ( clips.length === 0 ) return;

			let minX = - Infinity, minY = - Infinity;
			let maxX = Infinity, maxY = Infinity;

			for ( let i = 0; i < clips.length; i ++ ) {

				const clip = clips[ i ];

				minX = Math.max( minX, clip.x );
				minY = Math.max( minY, clip.y );
				maxX = Math.min( maxX, clip.x + clip.width );
				maxY = Math.min( maxY, clip.y + clip.height );

			}

			context.save();
			context.beginPath();
			context.rect( minX, minY, maxX - minX, maxY - minY );
			context.clip();

			isClipping = true;

		}

		return {

			add: function ( clip ) {

				clips.push( clip );
				doClip();

			},

			remove: function () {

				clips.pop();
				doClip();

			}

		};

	}
```
</details>

### `doClip(): void`

**Returns:** `void`

**Calls:**

- `context.restore`
- `Math.max`
- `Math.min`
- `context.save`
- `context.beginPath`
- `context.rect`
- `context.clip`

<details><summary>Code</summary>

```typescript
function doClip() {

			if ( isClipping ) {

				isClipping = false;
				context.restore();

			}

			if ( clips.length === 0 ) return;

			let minX = - Infinity, minY = - Infinity;
			let maxX = Infinity, maxY = Infinity;

			for ( let i = 0; i < clips.length; i ++ ) {

				const clip = clips[ i ];

				minX = Math.max( minX, clip.x );
				minY = Math.max( minY, clip.y );
				maxX = Math.min( maxX, clip.x + clip.width );
				maxY = Math.min( maxY, clip.y + clip.height );

			}

			context.save();
			context.beginPath();
			context.rect( minX, minY, maxX - minX, maxY - minY );
			context.clip();

			isClipping = true;

		}
```
</details>

### `add(clip: any): void`

**Parameters:**

- **`clip`** `any`

**Returns:** `void`

**Calls:**

- `clips.push`
- `doClip`

<details><summary>Code</summary>

```typescript
function ( clip ) {

				clips.push( clip );
				doClip();

			}
```
</details>

### `remove(): void`

**Returns:** `void`

**Calls:**

- `clips.pop`
- `doClip`

<details><summary>Code</summary>

```typescript
function () {

				clips.pop();
				doClip();

			}
```
</details>

### `add(clip: any): void`

**Parameters:**

- **`clip`** `any`

**Returns:** `void`

**Calls:**

- `clips.push`
- `doClip`

<details><summary>Code</summary>

```typescript
function ( clip ) {

				clips.push( clip );
				doClip();

			}
```
</details>

### `remove(): void`

**Returns:** `void`

**Calls:**

- `clips.pop`
- `doClip`

<details><summary>Code</summary>

```typescript
function () {

				clips.pop();
				doClip();

			}
```
</details>

### `drawText(style: any, x: any, y: any, string: any): void`

**Parameters:**

- **`style`** `any`
- **`x`** `any`
- **`y`** `any`
- **`string`** `any`

**Returns:** `void`

**Calls:**

- `string.toUpperCase`
- `context.fillText`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function drawText( style, x, y, string ) {

		if ( string !== '' ) {

			if ( style.textTransform === 'uppercase' ) {

				string = string.toUpperCase();

			}

			context.font = style.fontWeight + ' ' + style.fontSize + ' ' + style.fontFamily;
			context.textBaseline = 'top';
			context.fillStyle = style.color;
			context.fillText( string, x, y + parseFloat( style.fontSize ) * 0.1 );

		}

	}
```
</details>

### `buildRectPath(x: any, y: any, w: any, h: any, r: any): void`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`w`** `any`
- **`h`** `any`
- **`r`** `any`

**Returns:** `void`

**Calls:**

- `context.beginPath`
- `context.moveTo`
- `context.arcTo`
- `context.closePath`

<details><summary>Code</summary>

```typescript
function buildRectPath( x, y, w, h, r ) {

		if ( w < 2 * r ) r = w / 2;
		if ( h < 2 * r ) r = h / 2;

		context.beginPath();
		context.moveTo( x + r, y );
		context.arcTo( x + w, y, x + w, y + h, r );
		context.arcTo( x + w, y + h, x, y + h, r );
		context.arcTo( x, y + h, x, y, r );
		context.arcTo( x, y, x + w, y, r );
		context.closePath();

	}
```
</details>

### `drawBorder(style: any, which: any, x: any, y: any, width: any, height: any): void`

**Parameters:**

- **`style`** `any`
- **`which`** `any`
- **`x`** `any`
- **`y`** `any`
- **`width`** `any`
- **`height`** `any`

**Returns:** `void`

**Calls:**

- `parseFloat`
- `context.beginPath`
- `context.moveTo`
- `context.lineTo`
- `context.stroke`

<details><summary>Code</summary>

```typescript
function drawBorder( style, which, x, y, width, height ) {

		const borderWidth = style[ which + 'Width' ];
		const borderStyle = style[ which + 'Style' ];
		const borderColor = style[ which + 'Color' ];

		if ( borderWidth !== '0px' && borderStyle !== 'none' && borderColor !== 'transparent' && borderColor !== 'rgba(0, 0, 0, 0)' ) {

			context.strokeStyle = borderColor;
			context.lineWidth = parseFloat( borderWidth );
			context.beginPath();
			context.moveTo( x, y );
			context.lineTo( x + width, y + height );
			context.stroke();

		}

	}
```
</details>

### `drawElement(element: any, style: any): void`

**Parameters:**

- **`element`** `any`
- **`style`** `any`

**Returns:** `void`

**Calls:**

- `range.selectNode`
- `range.getBoundingClientRect`
- `drawText`
- `element.nodeValue.trim`
- `element.getBoundingClientRect`
- `context.save`
- `context.scale`
- `context.drawImage`
- `context.restore`
- `window.getComputedStyle`
- `buildRectPath`
- `parseFloat`
- `context.fill`
- `context.stroke`
- `drawBorder`
- `color.set`
- `Math.sqrt`
- `[ 'min', 'max', 'value' ].map`
- `clipper.add`
- `'*'.repeat`
- `parseInt`
- `clipper.remove`
- `drawElement`

**Internal Comments:**
```
// Do not render invisible elements, comments and scripts.
// text (x4)
// Canvas element (x2)
// Get the border of the element used for fill and border (x3)
// If all the borders match then stroke the round rectangle (x2)
// They all match so stroke the rectangle from before allows for border-radius (x2)
// Otherwise draw individual borders (x3)
/*
		// debug
		context.strokeStyle = '#' + Math.random().toString( 16 ).slice( - 3 );
		context.strokeRect( x - 0.5, y - 0.5, width + 1, height + 1 );
		*/ (x2)
```

<details><summary>Code</summary>

```typescript
function drawElement( element, style ) {

		// Do not render invisible elements, comments and scripts.
		if ( element.nodeType === Node.COMMENT_NODE || element.nodeName === 'SCRIPT' || ( element.style && element.style.display === 'none' ) ) {

			return;

		}

		let x = 0, y = 0, width = 0, height = 0;

		if ( element.nodeType === Node.TEXT_NODE ) {

			// text

			range.selectNode( element );

			const rect = range.getBoundingClientRect();

			x = rect.left - offset.left - 0.5;
			y = rect.top - offset.top - 0.5;
			width = rect.width;
			height = rect.height;

			drawText( style, x, y, element.nodeValue.trim() );

		} else if ( element instanceof HTMLCanvasElement ) {

			// Canvas element

			const rect = element.getBoundingClientRect();

			x = rect.left - offset.left - 0.5;
			y = rect.top - offset.top - 0.5;

		        context.save();
			const dpr = window.devicePixelRatio;
			context.scale( 1 / dpr, 1 / dpr );
			context.drawImage( element, x, y );
			context.restore();

		} else if ( element instanceof HTMLImageElement ) {

			const rect = element.getBoundingClientRect();

			x = rect.left - offset.left - 0.5;
			y = rect.top - offset.top - 0.5;
			width = rect.width;
			height = rect.height;

			context.drawImage( element, x, y, width, height );

		} else {

			const rect = element.getBoundingClientRect();

			x = rect.left - offset.left - 0.5;
			y = rect.top - offset.top - 0.5;
			width = rect.width;
			height = rect.height;

			style = window.getComputedStyle( element );

			// Get the border of the element used for fill and border

			buildRectPath( x, y, width, height, parseFloat( style.borderRadius ) );

			const backgroundColor = style.backgroundColor;

			if ( backgroundColor !== 'transparent' && backgroundColor !== 'rgba(0, 0, 0, 0)' ) {

				context.fillStyle = backgroundColor;
				context.fill();

			}

			// If all the borders match then stroke the round rectangle

			const borders = [ 'borderTop', 'borderLeft', 'borderBottom', 'borderRight' ];

			let match = true;
			let prevBorder = null;

			for ( const border of borders ) {

				if ( prevBorder !== null ) {

					match = ( style[ border + 'Width' ] === style[ prevBorder + 'Width' ] ) &&
					( style[ border + 'Color' ] === style[ prevBorder + 'Color' ] ) &&
					( style[ border + 'Style' ] === style[ prevBorder + 'Style' ] );

				}

				if ( match === false ) break;

				prevBorder = border;

			}

			if ( match === true ) {

				// They all match so stroke the rectangle from before allows for border-radius

				const width = parseFloat( style.borderTopWidth );

				if ( style.borderTopWidth !== '0px' && style.borderTopStyle !== 'none' && style.borderTopColor !== 'transparent' && style.borderTopColor !== 'rgba(0, 0, 0, 0)' ) {

					context.strokeStyle = style.borderTopColor;
					context.lineWidth = width;
					context.stroke();

				}

			} else {

				// Otherwise draw individual borders

				drawBorder( style, 'borderTop', x, y, width, 0 );
				drawBorder( style, 'borderLeft', x, y, 0, height );
				drawBorder( style, 'borderBottom', x, y + height, width, 0 );
				drawBorder( style, 'borderRight', x + width, y, 0, height );

			}

			if ( element instanceof HTMLInputElement ) {

				let accentColor = style.accentColor;

				if ( accentColor === undefined || accentColor === 'auto' ) accentColor = style.color;

				color.set( accentColor );

				const luminance = Math.sqrt( 0.299 * ( color.r ** 2 ) + 0.587 * ( color.g ** 2 ) + 0.114 * ( color.b ** 2 ) );
				const accentTextColor = luminance < 0.5 ? 'white' : '#111111';

				if ( element.type === 'radio' ) {

					buildRectPath( x, y, width, height, height );

					context.fillStyle = 'white';
					context.strokeStyle = accentColor;
					context.lineWidth = 1;
					context.fill();
					context.stroke();

					if ( element.checked ) {

						buildRectPath( x + 2, y + 2, width - 4, height - 4, height );

						context.fillStyle = accentColor;
						context.strokeStyle = accentTextColor;
						context.lineWidth = 2;
						context.fill();
						context.stroke();

					}

				}

				if ( element.type === 'checkbox' ) {

					buildRectPath( x, y, width, height, 2 );

					context.fillStyle = element.checked ? accentColor : 'white';
					context.strokeStyle = element.checked ? accentTextColor : accentColor;
					context.lineWidth = 1;
					context.stroke();
					context.fill();

					if ( element.checked ) {

						const currentTextAlign = context.textAlign;

						context.textAlign = 'center';

						const properties = {
							color: accentTextColor,
							fontFamily: style.fontFamily,
							fontSize: height + 'px',
							fontWeight: 'bold'
						};

						drawText( properties, x + ( width / 2 ), y, '✔' );

						context.textAlign = currentTextAlign;

					}

				}

				if ( element.type === 'range' ) {

					const [ min, max, value ] = [ 'min', 'max', 'value' ].map( property => parseFloat( element[ property ] ) );
					const position = ( ( value - min ) / ( max - min ) ) * ( width - height );

					buildRectPath( x, y + ( height / 4 ), width, height / 2, height / 4 );
					context.fillStyle = accentTextColor;
					context.strokeStyle = accentColor;
					context.lineWidth = 1;
					context.fill();
					context.stroke();

					buildRectPath( x, y + ( height / 4 ), position + ( height / 2 ), height / 2, height / 4 );
					context.fillStyle = accentColor;
					context.fill();

					buildRectPath( x + position, y, height, height, height / 2 );
					context.fillStyle = accentColor;
					context.fill();

				}

				if ( element.type === 'color' || element.type === 'text' || element.type === 'number' || element.type === 'email' || element.type === 'password' ) {

					clipper.add( { x: x, y: y, width: width, height: height } );

					const displayValue = element.type === 'password' ? '*'.repeat( element.value.length ) : element.value;

					drawText( style, x + parseInt( style.paddingLeft ), y + parseInt( style.paddingTop ), displayValue );

					clipper.remove();

				}

			}

		}

		/*
		// debug
		context.strokeStyle = '#' + Math.random().toString( 16 ).slice( - 3 );
		context.strokeRect( x - 0.5, y - 0.5, width + 1, height + 1 );
		*/

		const isClipping = style.overflow === 'auto' || style.overflow === 'hidden';

		if ( isClipping ) clipper.add( { x: x, y: y, width: width, height: height } );

		for ( let i = 0; i < element.childNodes.length; i ++ ) {

			drawElement( element.childNodes[ i ], style );

		}

		if ( isClipping ) clipper.remove();

	}
```
</details>

### `htmlevent(element: any, event: any, x: any, y: any): void`

**Parameters:**

- **`element`** `any`
- **`event`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `void`

**Calls:**

- `window.dispatchEvent`
- `element.getBoundingClientRect`
- `element.dispatchEvent`
- `[ 'min', 'max' ].map`
- `parseFloat`
- `element.focus`
- `traverse`

<details><summary>Code</summary>

```typescript
function htmlevent( element, event, x, y ) {

	const mouseEventInit = {
		clientX: ( x * element.offsetWidth ) + element.offsetLeft,
		clientY: ( y * element.offsetHeight ) + element.offsetTop,
		view: element.ownerDocument.defaultView
	};

	window.dispatchEvent( new MouseEvent( event, mouseEventInit ) );

	const rect = element.getBoundingClientRect();

	x = x * rect.width + rect.left;
	y = y * rect.height + rect.top;

	function traverse( element ) {

		if ( element.nodeType !== Node.TEXT_NODE && element.nodeType !== Node.COMMENT_NODE ) {

			const rect = element.getBoundingClientRect();

			if ( x > rect.left && x < rect.right && y > rect.top && y < rect.bottom ) {

				element.dispatchEvent( new MouseEvent( event, mouseEventInit ) );

				if ( element instanceof HTMLInputElement && element.type === 'range' && ( event === 'mousedown' || event === 'click' ) ) {

					const [ min, max ] = [ 'min', 'max' ].map( property => parseFloat( element[ property ] ) );

					const width = rect.width;
					const offsetX = x - rect.x;
					const proportion = offsetX / width;
					element.value = min + ( max - min ) * proportion;
					element.dispatchEvent( new InputEvent( 'input', { bubbles: true } ) );

				}

				if ( element instanceof HTMLInputElement && ( element.type === 'text' || element.type === 'number' || element.type === 'email' || element.type === 'password' ) && ( event === 'mousedown' || event === 'click' ) ) {

					element.focus();

				}

			}

			for ( let i = 0; i < element.childNodes.length; i ++ ) {

				traverse( element.childNodes[ i ] );

			}

		}

	}

	traverse( element );

}
```
</details>

### `traverse(element: any): void`

**Parameters:**

- **`element`** `any`

**Returns:** `void`

**Calls:**

- `element.getBoundingClientRect`
- `element.dispatchEvent`
- `[ 'min', 'max' ].map`
- `parseFloat`
- `element.focus`
- `traverse`

<details><summary>Code</summary>

```typescript
function traverse( element ) {

		if ( element.nodeType !== Node.TEXT_NODE && element.nodeType !== Node.COMMENT_NODE ) {

			const rect = element.getBoundingClientRect();

			if ( x > rect.left && x < rect.right && y > rect.top && y < rect.bottom ) {

				element.dispatchEvent( new MouseEvent( event, mouseEventInit ) );

				if ( element instanceof HTMLInputElement && element.type === 'range' && ( event === 'mousedown' || event === 'click' ) ) {

					const [ min, max ] = [ 'min', 'max' ].map( property => parseFloat( element[ property ] ) );

					const width = rect.width;
					const offsetX = x - rect.x;
					const proportion = offsetX / width;
					element.value = min + ( max - min ) * proportion;
					element.dispatchEvent( new InputEvent( 'input', { bubbles: true } ) );

				}

				if ( element instanceof HTMLInputElement && ( element.type === 'text' || element.type === 'number' || element.type === 'email' || element.type === 'password' ) && ( event === 'mousedown' || event === 'click' ) ) {

					element.focus();

				}

			}

			for ( let i = 0; i < element.childNodes.length; i ++ ) {

				traverse( element.childNodes[ i ] );

			}

		}

	}
```
</details>


---

## Classes

### `HTMLMesh`

<details><summary>Class Code</summary>

```ts
class HTMLMesh extends Mesh {

	/**
	 * Constructs a new HTML mesh.
	 *
	 * @param {HTMLElement} dom - The DOM element to display as a plane mesh.
	 */
	constructor( dom ) {

		const texture = new HTMLTexture( dom );

		const geometry = new PlaneGeometry( texture.image.width * 0.001, texture.image.height * 0.001 );
		const material = new MeshBasicMaterial( { map: texture, toneMapped: false, transparent: true } );

		super( geometry, material );

		function onEvent( event ) {

			material.map.dispatchDOMEvent( event );

		}

		this.addEventListener( 'mousedown', onEvent );
		this.addEventListener( 'mousemove', onEvent );
		this.addEventListener( 'mouseup', onEvent );
		this.addEventListener( 'click', onEvent );

		/**
		 * Frees the GPU-related resources allocated by this instance and removes all event listeners.
		 * Call this method whenever this instance is no longer used in your app.
		 */
		this.dispose = function () {

			geometry.dispose();
			material.dispose();

			material.map.dispose();

			canvases.delete( dom );

			this.removeEventListener( 'mousedown', onEvent );
			this.removeEventListener( 'mousemove', onEvent );
			this.removeEventListener( 'mouseup', onEvent );
			this.removeEventListener( 'click', onEvent );

		};

	}

}
```
</details>

### `HTMLTexture`

<details><summary>Class Code</summary>

```ts
class HTMLTexture extends CanvasTexture {

	constructor( dom ) {

		super( html2canvas( dom ) );

		this.dom = dom;

		this.anisotropy = 16;
		this.colorSpace = SRGBColorSpace;
		this.minFilter = LinearFilter;
		this.magFilter = LinearFilter;
		this.generateMipmaps = false;

		// Create an observer on the DOM, and run html2canvas update in the next loop
		const observer = new MutationObserver( () => {

			if ( ! this.scheduleUpdate ) {

				// ideally should use xr.requestAnimationFrame, here setTimeout to avoid passing the renderer
				this.scheduleUpdate = setTimeout( () => this.update(), 16 );

			}

		} );

		const config = { attributes: true, childList: true, subtree: true, characterData: true };
		observer.observe( dom, config );

		this.observer = observer;

	}

	dispatchDOMEvent( event ) {

		if ( event.data ) {

			htmlevent( this.dom, event.type, event.data.x, event.data.y );

		}

	}

	update() {

		this.image = html2canvas( this.dom );
		this.needsUpdate = true;

		this.scheduleUpdate = null;

	}

	dispose() {

		if ( this.observer ) {

			this.observer.disconnect();

		}

		this.scheduleUpdate = clearTimeout( this.scheduleUpdate );

		super.dispose();

	}

}
```
</details>

#### Methods

##### `dispatchDOMEvent(event: any): void`

<details><summary>Code</summary>

```ts
dispatchDOMEvent( event ) {

		if ( event.data ) {

			htmlevent( this.dom, event.type, event.data.x, event.data.y );

		}

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		this.image = html2canvas( this.dom );
		this.needsUpdate = true;

		this.scheduleUpdate = null;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		if ( this.observer ) {

			this.observer.disconnect();

		}

		this.scheduleUpdate = clearTimeout( this.scheduleUpdate );

		super.dispose();

	}
```
</details>


---