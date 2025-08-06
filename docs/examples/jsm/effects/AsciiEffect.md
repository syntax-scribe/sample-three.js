[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AsciiEffect.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 29 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/effects/AsciiEffect.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `fResolution` | `any` | let/var | `options[ 'resolution' ] \|\| 0.15` | ✗ |
| `iScale` | `any` | let/var | `options[ 'scale' ] \|\| 1` | ✗ |
| `bColor` | `any` | let/var | `options[ 'color' ] \|\| false` | ✗ |
| `bAlpha` | `any` | let/var | `options[ 'alpha' ] \|\| false` | ✗ |
| `bBlock` | `any` | let/var | `options[ 'block' ] \|\| false` | ✗ |
| `bInvert` | `any` | let/var | `options[ 'invert' ] \|\| false` | ✗ |
| `strResolution` | `any` | let/var | `options[ 'strResolution' ] \|\| 'low'` | ✗ |
| `width` | `any` | let/var | `*not shown*` | ✗ |
| `height` | `any` | let/var | `*not shown*` | ✗ |
| `iWidth` | `any` | let/var | `*not shown*` | ✗ |
| `iHeight` | `any` | let/var | `*not shown*` | ✗ |
| `oImg` | `any` | let/var | `*not shown*` | ✗ |
| `oStyle` | `CSSStyleDeclaration` | let/var | `oAscii.style` | ✗ |
| `strFont` | `"courier new, monospace"` | let/var | `'courier new, monospace'` | ✗ |
| `oCanvasImg` | `any` | let/var | `renderer.domElement` | ✗ |
| `aCharList` | `any` | let/var | `*not shown*` | ✗ |
| `fFontSize` | `number` | let/var | `( 2 / fResolution ) * iScale` | ✗ |
| `fLineHeight` | `number` | let/var | `( 2 / fResolution ) * iScale` | ✗ |
| `fLetterSpacing` | `number` | let/var | `0` | ✗ |
| `oImgData` | `Uint8ClampedArray<ArrayBufferLike>` | let/var | `oCtx.getImageData( 0, 0, iWidth, iHeight ).data` | ✗ |
| `strChars` | `string` | let/var | `''` | ✗ |
| `iOffset` | `number` | let/var | `( y * iWidth + x ) * 4` | ✗ |
| `iRed` | `number` | let/var | `oImgData[ iOffset ]` | ✗ |
| `iGreen` | `number` | let/var | `oImgData[ iOffset + 1 ]` | ✗ |
| `iBlue` | `number` | let/var | `oImgData[ iOffset + 2 ]` | ✗ |
| `iAlpha` | `number` | let/var | `oImgData[ iOffset + 3 ]` | ✗ |
| `iCharIdx` | `any` | let/var | `*not shown*` | ✗ |
| `fBrightness` | `any` | let/var | `*not shown*` | ✗ |
| `strThisChar` | `any` | let/var | `aCharList[ iCharIdx ]` | ✗ |


---

## Functions

### `initAsciiSize(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`

**Internal Comments:**
```
// oCanvas.style.display = "none"; (x3)
// oCanvas.style.width = iWidth; (x3)
// oCanvas.style.height = iHeight; (x3)
```

<details><summary>Code</summary>

```typescript
function initAsciiSize() {

			iWidth = Math.floor( width * fResolution );
			iHeight = Math.floor( height * fResolution );

			oCanvas.width = iWidth;
			oCanvas.height = iHeight;
			// oCanvas.style.display = "none";
			// oCanvas.style.width = iWidth;
			// oCanvas.style.height = iHeight;

			oImg = renderer.domElement;

			if ( oImg.style.backgroundColor ) {

				oAscii.rows[ 0 ].cells[ 0 ].style.backgroundColor = oImg.style.backgroundColor;
				oAscii.rows[ 0 ].cells[ 0 ].style.color = oImg.style.color;

			}

			oAscii.cellSpacing = '0';
			oAscii.cellPadding = '0';

			const oStyle = oAscii.style;
			oStyle.whiteSpace = 'pre';
			oStyle.margin = '0px';
			oStyle.padding = '0px';
			oStyle.letterSpacing = fLetterSpacing + 'px';
			oStyle.fontFamily = strFont;
			oStyle.fontSize = fFontSize + 'px';
			oStyle.lineHeight = fLineHeight + 'px';
			oStyle.textAlign = 'left';
			oStyle.textDecoration = 'none';

		}
```
</details>

### `asciifyImage(oAscii: any): void`

**Parameters:**

- **`oAscii`** `any`

**Returns:** `void`

**Calls:**

- `oCtx.clearRect`
- `oCtx.drawImage`
- `oCtx.getImageData`
- `Math.floor`

**Internal Comments:**
```
// Coloring loop starts now (x2)
// console.time('rendering');
// fBrightness = (0.3*iRed + 0.5*iGreen + 0.3*iBlue) / 255;
// should calculate alpha instead, but quick hack :) (x3)
//fBrightness *= (iAlpha / 255); (x3)
// good for debugging (x2)
//fBrightness = Math.floor(fBrightness * 10); (x2)
//strThisChar = fBrightness; (x2)
```

<details><summary>Code</summary>

```typescript
function asciifyImage( oAscii ) {

			oCtx.clearRect( 0, 0, iWidth, iHeight );
			oCtx.drawImage( oCanvasImg, 0, 0, iWidth, iHeight );
			const oImgData = oCtx.getImageData( 0, 0, iWidth, iHeight ).data;

			// Coloring loop starts now
			let strChars = '';

			// console.time('rendering');

			for ( let y = 0; y < iHeight; y += 2 ) {

				for ( let x = 0; x < iWidth; x ++ ) {

					const iOffset = ( y * iWidth + x ) * 4;

					const iRed = oImgData[ iOffset ];
					const iGreen = oImgData[ iOffset + 1 ];
					const iBlue = oImgData[ iOffset + 2 ];
					const iAlpha = oImgData[ iOffset + 3 ];
					let iCharIdx;

					let fBrightness;

					fBrightness = ( 0.3 * iRed + 0.59 * iGreen + 0.11 * iBlue ) / 255;
					// fBrightness = (0.3*iRed + 0.5*iGreen + 0.3*iBlue) / 255;

					if ( iAlpha == 0 ) {

						// should calculate alpha instead, but quick hack :)
						//fBrightness *= (iAlpha / 255);
						fBrightness = 1;

					}

					iCharIdx = Math.floor( ( 1 - fBrightness ) * ( aCharList.length - 1 ) );

					if ( bInvert ) {

						iCharIdx = aCharList.length - iCharIdx - 1;

					}

					// good for debugging
					//fBrightness = Math.floor(fBrightness * 10);
					//strThisChar = fBrightness;

					let strThisChar = aCharList[ iCharIdx ];

					if ( strThisChar === undefined || strThisChar == ' ' )
						strThisChar = '&nbsp;';

					if ( bColor ) {

						strChars += '<span style=\''
							+ 'color:rgb(' + iRed + ',' + iGreen + ',' + iBlue + ');'
							+ ( bBlock ? 'background-color:rgb(' + iRed + ',' + iGreen + ',' + iBlue + ');' : '' )
							+ ( bAlpha ? 'opacity:' + ( iAlpha / 255 ) + ';' : '' )
							+ '\'>' + strThisChar + '</span>';

					} else {

						strChars += strThisChar;

					}

				}

				strChars += '<br/>';

			}

			oAscii.innerHTML = `<tr><td style="display:block;width:${width}px;height:${height}px;overflow:hidden">${strChars}</td></tr>`;

			// console.timeEnd('rendering');

			// return oAscii;

		}
```
</details>


---

## Classes

### `AsciiEffect`

<details><summary>Class Code</summary>

```ts
class AsciiEffect {

	/**
	 * Constructs a new ASCII effect.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {string} [charSet=' .:-=+*#%@'] - The char set.
	 * @param {AsciiEffect~Options} [options] - The configuration parameter.
	 */
	constructor( renderer, charSet = ' .:-=+*#%@', options = {} ) {

		// ' .,:;=|iI+hHOE#`$';
		// darker bolder character set from https://github.com/saw/Canvas-ASCII-Art/
		// ' .\'`^",:;Il!i~+_-?][}{1)(|/tfjrxnuvczXYUJCLQ0OZmwqpdbkhao*#MW&8%B@$'.split('');

		// Some ASCII settings

		const fResolution = options[ 'resolution' ] || 0.15;
		const iScale = options[ 'scale' ] || 1;
		const bColor = options[ 'color' ] || false;
		const bAlpha = options[ 'alpha' ] || false;
		const bBlock = options[ 'block' ] || false;
		const bInvert = options[ 'invert' ] || false;
		const strResolution = options[ 'strResolution' ] || 'low';

		let width, height;

		const domElement = document.createElement( 'div' );
		domElement.style.cursor = 'default';

		const oAscii = document.createElement( 'table' );
		domElement.appendChild( oAscii );

		let iWidth, iHeight;
		let oImg;

		/**
		 * Resizes the effect.
		 *
		 * @param {number} w - The width of the effect in logical pixels.
		 * @param {number} h - The height of the effect in logical pixels.
		 */
		this.setSize = function ( w, h ) {

			width = w;
			height = h;

			renderer.setSize( w, h );

			initAsciiSize();

		};

		/**
		 * When using this effect, this method should be called instead of the
		 * default {@link WebGLRenderer#render}.
		 *
		 * @param {Object3D} scene - The scene to render.
		 * @param {Camera} camera - The camera.
		 */
		this.render = function ( scene, camera ) {

			renderer.render( scene, camera );
			asciifyImage( oAscii );

		};

		/**
		 * The DOM element of the effect. This element must be used instead of the
		 * default {@link WebGLRenderer#domElement}.
		 *
		 * @type {HTMLDivElement}
		 */
		this.domElement = domElement;


		// Throw in ascii library from https://github.com/hassadee/jsascii/blob/master/jsascii.js (MIT License)

		function initAsciiSize() {

			iWidth = Math.floor( width * fResolution );
			iHeight = Math.floor( height * fResolution );

			oCanvas.width = iWidth;
			oCanvas.height = iHeight;
			// oCanvas.style.display = "none";
			// oCanvas.style.width = iWidth;
			// oCanvas.style.height = iHeight;

			oImg = renderer.domElement;

			if ( oImg.style.backgroundColor ) {

				oAscii.rows[ 0 ].cells[ 0 ].style.backgroundColor = oImg.style.backgroundColor;
				oAscii.rows[ 0 ].cells[ 0 ].style.color = oImg.style.color;

			}

			oAscii.cellSpacing = '0';
			oAscii.cellPadding = '0';

			const oStyle = oAscii.style;
			oStyle.whiteSpace = 'pre';
			oStyle.margin = '0px';
			oStyle.padding = '0px';
			oStyle.letterSpacing = fLetterSpacing + 'px';
			oStyle.fontFamily = strFont;
			oStyle.fontSize = fFontSize + 'px';
			oStyle.lineHeight = fLineHeight + 'px';
			oStyle.textAlign = 'left';
			oStyle.textDecoration = 'none';

		}


		const strFont = 'courier new, monospace';

		const oCanvasImg = renderer.domElement;

		const oCanvas = document.createElement( 'canvas' );
		if ( ! oCanvas.getContext ) {

			return;

		}

		const oCtx = oCanvas.getContext( '2d' );
		if ( ! oCtx.getImageData ) {

			return;

		}

		let aCharList;
		if ( charSet ) {

			aCharList = ( charSet ).split( '' );

		} else {

			const aDefaultCharList = ( ' .,:;i1tfLCG08@' ).split( '' );
			const aDefaultColorCharList = ( ' CGO08@' ).split( '' );
			aCharList = ( bColor ? aDefaultColorCharList : aDefaultCharList );

		}


		// Setup dom

		const fFontSize = ( 2 / fResolution ) * iScale;
		const fLineHeight = ( 2 / fResolution ) * iScale;

		// adjust letter-spacing for all combinations of scale and resolution to get it to fit the image width.

		let fLetterSpacing = 0;

		if ( strResolution == 'low' ) {

			switch ( iScale ) {

				case 1 : fLetterSpacing = - 1; break;
				case 2 :
				case 3 : fLetterSpacing = - 2.1; break;
				case 4 : fLetterSpacing = - 3.1; break;
				case 5 : fLetterSpacing = - 4.15; break;

			}

		}

		if ( strResolution == 'medium' ) {

			switch ( iScale ) {

				case 1 : fLetterSpacing = 0; break;
				case 2 : fLetterSpacing = - 1; break;
				case 3 : fLetterSpacing = - 1.04; break;
				case 4 :
				case 5 : fLetterSpacing = - 2.1; break;

			}

		}

		if ( strResolution == 'high' ) {

			switch ( iScale ) {

				case 1 :
				case 2 : fLetterSpacing = 0; break;
				case 3 :
				case 4 :
				case 5 : fLetterSpacing = - 1; break;

			}

		}


		// can't get a span or div to flow like an img element, but a table works?


		// convert img element to ascii

		function asciifyImage( oAscii ) {

			oCtx.clearRect( 0, 0, iWidth, iHeight );
			oCtx.drawImage( oCanvasImg, 0, 0, iWidth, iHeight );
			const oImgData = oCtx.getImageData( 0, 0, iWidth, iHeight ).data;

			// Coloring loop starts now
			let strChars = '';

			// console.time('rendering');

			for ( let y = 0; y < iHeight; y += 2 ) {

				for ( let x = 0; x < iWidth; x ++ ) {

					const iOffset = ( y * iWidth + x ) * 4;

					const iRed = oImgData[ iOffset ];
					const iGreen = oImgData[ iOffset + 1 ];
					const iBlue = oImgData[ iOffset + 2 ];
					const iAlpha = oImgData[ iOffset + 3 ];
					let iCharIdx;

					let fBrightness;

					fBrightness = ( 0.3 * iRed + 0.59 * iGreen + 0.11 * iBlue ) / 255;
					// fBrightness = (0.3*iRed + 0.5*iGreen + 0.3*iBlue) / 255;

					if ( iAlpha == 0 ) {

						// should calculate alpha instead, but quick hack :)
						//fBrightness *= (iAlpha / 255);
						fBrightness = 1;

					}

					iCharIdx = Math.floor( ( 1 - fBrightness ) * ( aCharList.length - 1 ) );

					if ( bInvert ) {

						iCharIdx = aCharList.length - iCharIdx - 1;

					}

					// good for debugging
					//fBrightness = Math.floor(fBrightness * 10);
					//strThisChar = fBrightness;

					let strThisChar = aCharList[ iCharIdx ];

					if ( strThisChar === undefined || strThisChar == ' ' )
						strThisChar = '&nbsp;';

					if ( bColor ) {

						strChars += '<span style=\''
							+ 'color:rgb(' + iRed + ',' + iGreen + ',' + iBlue + ');'
							+ ( bBlock ? 'background-color:rgb(' + iRed + ',' + iGreen + ',' + iBlue + ');' : '' )
							+ ( bAlpha ? 'opacity:' + ( iAlpha / 255 ) + ';' : '' )
							+ '\'>' + strThisChar + '</span>';

					} else {

						strChars += strThisChar;

					}

				}

				strChars += '<br/>';

			}

			oAscii.innerHTML = `<tr><td style="display:block;width:${width}px;height:${height}px;overflow:hidden">${strChars}</td></tr>`;

			// console.timeEnd('rendering');

			// return oAscii;

		}

	}

}
```
</details>


---