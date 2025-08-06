[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `lessons-helper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 29 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 39 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`manual/examples/resources/lessons-helper.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `lessonSettings` | `{}` | let/var | `window.lessonSettings \|\| {}` | ✗ |
| `topWindow` | `any` | let/var | `this` | ✗ |
| `doc` | `any` | let/var | `canvas.ownerDocument` | ✗ |
| `origConsole` | `{}` | let/var | `{}` | ✗ |
| `show` | `boolean` | let/var | `false` | ✗ |
| `maxLines` | `100` | let/var | `100` | ✗ |
| `lines` | `any[]` | let/var | `[]` | ✗ |
| `added` | `boolean` | let/var | `false` | ✗ |
| `threePukeRE` | `RegExp` | let/var | `/WebGLRenderer.*?extension not supported/` | ✗ |
| `oldFn` | `any` | let/var | `obj[ funcName ]` | ✗ |
| `lineNdx` | `any` | let/var | `*not shown*` | ✗ |
| `matcher` | `any` | let/var | `*not shown*` | ✗ |
| `userFnName` | `string` | let/var | `m[ 1 ]` | ✗ |
| `url` | `string` | let/var | `m[ 2 ]` | ✗ |
| `url` | `string` | let/var | `m[ 1 ]` | ✗ |
| `handlers` | `{ log: (data: any) => void; lostConte...` | let/var | `{ log, lostContext, jsError, jsErrorWithStack, }` | ✗ |
| `OrigWorker` | `{ new (scriptURL: string \| URL, opti...` | let/var | `self.Worker` | ✗ |
| `listener` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `any` | let/var | `e.data.data` | ✗ |
| `fn` | `any` | let/var | `handlers[ data.type ]` | ✗ |
| `nextFakeRAFId` | `number` | let/var | `1` | ✗ |
| `fakeRAFIdToCallbackMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `rafRequestId` | `any` | let/var | `*not shown*` | ✗ |
| `isBodyOnScreen` | `any` | let/var | `*not shown*` | ✗ |
| `ids` | `any[]` | let/var | `[ ...fakeRAFIdToCallbackMap.keys() ]` | ✗ |
| `intersectionObserver` | `IntersectionObserver` | let/var | `new IntersectionObserver( ( entries ) => { entries.forEach( entry => { isBody...` | ✗ |
| `fakeRAFId` | `number` | let/var | `nextFakeRAFId ++` | ✗ |
| `msg` | `any` | let/var | `e.message \|\| e.error` | ✗ |
| `url` | `string` | let/var | `e.filename` | ✗ |
| `lineNo` | `number` | let/var | `e.lineno \|\| 1` | ✗ |
| `colNo` | `number` | let/var | `e.colno \|\| 1` | ✗ |
| `userAgent` | `string` | let/var | `navigator.userAgent` | ✗ |
| `m` | `[] \| RegExpMatchArray` | let/var | `userAgent.match( /(opera\|chrome\|safari\|firefox\|msie\|trident(?=\/))\/?\s*...` | ✗ |
| `canvasesToTimeoutMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `isWebGLRE` | `RegExp` | let/var | `/^(webgl\|webgl2\|experimental-webgl)$/i` | ✗ |
| `isWebGL2RE` | `RegExp` | let/var | `/^webgl2$/i` | ✗ |
| `type` | `any` | let/var | `arguments[ 0 ]` | ✗ |
| `numArgs` | `any` | let/var | `args.length` | ✗ |
| `errorMsg` | `string` | let/var | ``WebGL error ${glEnumToString( err )} in ${funcName}(${enumedArgs.join( ', ' ...` | ✗ |


---

## Functions

### `isInIFrame(w: any): boolean`

**JSDoc:**
```typescript
/**
   * Check if the page is embedded.
   * @param {Window?) w window to check
   * @return {boolean} True of we are in an iframe
   */
```

**Parameters:**

- **`w`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isInIFrame( w ) {

		w = w || topWindow;
		return w !== w.top;

	}
```
</details>

### `updateCSSIfInIFrame(): void`

**Returns:** `void`

**Calls:**

- `isInIFrame`
- `document.getElementsByTagName`

<details><summary>Code</summary>

```typescript
function updateCSSIfInIFrame() {

		if ( isInIFrame() ) {

			try {

				document.getElementsByTagName( 'html' )[ 0 ].className = 'iframe';

			} catch ( e ) {
        // eslint-disable-line
			}

			try {

				document.body.className = 'iframe';

			} catch ( e ) {
        // eslint-disable-line
			}

		}

	}
```
</details>

### `isInEditor(): boolean`

**Returns:** `boolean`

**Calls:**

- `window.location.href.substring`

<details><summary>Code</summary>

```typescript
function isInEditor() {

		return window.location.href.substring( 0, 4 ) === 'blob';

	}
```
</details>

### `showNeedWebGL(canvas: any): WebGLRenderingContext`

**JSDoc:**
```typescript
/**
   * Creates a webgl context. If creation fails it will
   * change the contents of the container of the <canvas>
   * tag to an error message with the correct links for WebGL.
   * @param {HTMLCanvasElement} canvas. The canvas element to
   *     create a context from.
   * @param {WebGLContextCreationAttributes} opt_attribs Any
   *     creation attributes you want to pass in.
   * @return {WebGLRenderingContext} The created context.
   * @memberOf module:webgl-utils
   */
```

**Parameters:**

- **`canvas`** `any`

**Returns:** `WebGLRenderingContext`

**Calls:**

- `doc.createElement`
- `temp.querySelector`
- `doc.body.appendChild`

<details><summary>Code</summary>

```typescript
function showNeedWebGL( canvas ) {

		const doc = canvas.ownerDocument;
		if ( doc ) {

			const temp = doc.createElement( 'div' );
			temp.innerHTML = `
        <div style="
          position: absolute;
          left: 0;
          top: 0;
          background-color: #DEF;
          width: 100%;
          height: 100%;
          display: flex;
          flex-flow: column;
          justify-content: center;
          align-content: center;
          align-items: center;
        ">
          <div style="text-align: center;">
            It doesn't appear your browser supports WebGL.<br/>
            <a href="http://get.webgl.org" target="_blank">Click here for more information.</a>
          </div>
        </div>
      `;
			const div = temp.querySelector( 'div' );
			doc.body.appendChild( div );

		}

	}
```
</details>

### `setupConsole(): void`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `Object.assign`
- `toggle.addEventListener`
- `showHideConsole`
- `parent.appendChild`
- `lines.push`
- `document.body.appendChild`
- `lines.shift`
- `div.parentNode.removeChild`
- `addLine`
- `oldFn.bind`
- `[ ...args ].join`
- `threePukeRE.test`
- `addLines`
- `oldFn.apply`
- `wrapFunc`

**Internal Comments:**
```
// three.js pukes all over so filter here (x2)
```

<details><summary>Code</summary>

```typescript
function setupConsole() {

		const style = document.createElement( 'style' );
		style.innerText = `
    .console {
      font-family: monospace;
      font-size: medium;
      max-height: 50%;
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      overflow: auto;
      background: rgba(221, 221, 221, 0.9);
    }
    .console .console-line {
      white-space: pre-line;
    }
    .console .log .warn {
      color: black;
    }
    .console .error {
      color: red;
    }
    `;
		const parent = document.createElement( 'div' );
		parent.className = 'console';
		const toggle = document.createElement( 'div' );
		let show = false;
		Object.assign( toggle.style, {
			position: 'absolute',
			right: 0,
			bottom: 0,
			background: '#EEE',
			'font-size': 'smaller',
			cursor: 'pointer',
		} );
		toggle.addEventListener( 'click', showHideConsole );

		function showHideConsole() {

			show = ! show;
			toggle.textContent = show ? '☒' : '☐';
			parent.style.display = show ? '' : 'none';

		}

		showHideConsole();

		const maxLines = 100;
		const lines = [];
		let added = false;

		function addLine( type, str, prefix ) {

			const div = document.createElement( 'div' );
			div.textContent = ( prefix + str ) || ' ';
			div.className = `console-line ${type}`;
			parent.appendChild( div );
			lines.push( div );
			if ( ! added ) {

				added = true;
				document.body.appendChild( style );
				document.body.appendChild( parent );
				document.body.appendChild( toggle );

			}
			// scrollIntoView only works in Chrome
			// In Firefox and Safari scrollIntoView inside an iframe moves
			// that element into the view. It should arguably only move that
			// element inside the iframe itself, otherwise that's giving
			// any random iframe control to bring itself into view against
			// the parent's wishes.
			//
			// note that even if we used a solution (which is to manually set
			// scrollTop) there's a UI issue that if the user manually scrolls
			// we want to stop scrolling automatically and if they move back
			// to the bottom we want to pick up scrolling automatically.
			// Kind of a PITA so TBD
			//
			// div.scrollIntoView();

		}

		function addLines( type, str, prefix ) {

			while ( lines.length > maxLines ) {

				const div = lines.shift();
				div.parentNode.removeChild( div );

			}

			addLine( type, str, prefix );

		}

		const threePukeRE = /WebGLRenderer.*?extension not supported/;
		function wrapFunc( obj, funcName, prefix ) {

			const oldFn = obj[ funcName ];
			origConsole[ funcName ] = oldFn.bind( obj );
			return function ( ...args ) {

				// three.js pukes all over so filter here
				const src = [ ...args ].join( ' ' );
				if ( ! threePukeRE.test( src ) ) {

					addLines( funcName, src, prefix );

				}

				oldFn.apply( obj, arguments );

			};

		}

		window.console.log = wrapFunc( window.console, 'log', '' );
		window.console.warn = wrapFunc( window.console, 'warn', '⚠' );
		window.console.error = wrapFunc( window.console, 'error', '❌' );

	}
```
</details>

### `showHideConsole(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function showHideConsole() {

			show = ! show;
			toggle.textContent = show ? '☒' : '☐';
			parent.style.display = show ? '' : 'none';

		}
```
</details>

### `addLine(type: any, str: any, prefix: any): void`

**Parameters:**

- **`type`** `any`
- **`str`** `any`
- **`prefix`** `any`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `parent.appendChild`
- `lines.push`
- `document.body.appendChild`

<details><summary>Code</summary>

```typescript
function addLine( type, str, prefix ) {

			const div = document.createElement( 'div' );
			div.textContent = ( prefix + str ) || ' ';
			div.className = `console-line ${type}`;
			parent.appendChild( div );
			lines.push( div );
			if ( ! added ) {

				added = true;
				document.body.appendChild( style );
				document.body.appendChild( parent );
				document.body.appendChild( toggle );

			}
			// scrollIntoView only works in Chrome
			// In Firefox and Safari scrollIntoView inside an iframe moves
			// that element into the view. It should arguably only move that
			// element inside the iframe itself, otherwise that's giving
			// any random iframe control to bring itself into view against
			// the parent's wishes.
			//
			// note that even if we used a solution (which is to manually set
			// scrollTop) there's a UI issue that if the user manually scrolls
			// we want to stop scrolling automatically and if they move back
			// to the bottom we want to pick up scrolling automatically.
			// Kind of a PITA so TBD
			//
			// div.scrollIntoView();

		}
```
</details>

### `addLines(type: any, str: any, prefix: any): void`

**Parameters:**

- **`type`** `any`
- **`str`** `any`
- **`prefix`** `any`

**Returns:** `void`

**Calls:**

- `lines.shift`
- `div.parentNode.removeChild`
- `addLine`

<details><summary>Code</summary>

```typescript
function addLines( type, str, prefix ) {

			while ( lines.length > maxLines ) {

				const div = lines.shift();
				div.parentNode.removeChild( div );

			}

			addLine( type, str, prefix );

		}
```
</details>

### `wrapFunc(obj: any, funcName: any, prefix: any): (...args: any[]) => void`

**Parameters:**

- **`obj`** `any`
- **`funcName`** `any`
- **`prefix`** `any`

**Returns:** `(...args: any[]) => void`

**Calls:**

- `oldFn.bind`
- `[ ...args ].join`
- `threePukeRE.test`
- `addLines`
- `oldFn.apply`

**Internal Comments:**
```
// three.js pukes all over so filter here (x2)
```

<details><summary>Code</summary>

```typescript
function wrapFunc( obj, funcName, prefix ) {

			const oldFn = obj[ funcName ];
			origConsole[ funcName ] = oldFn.bind( obj );
			return function ( ...args ) {

				// three.js pukes all over so filter here
				const src = [ ...args ].join( ' ' );
				if ( ! threePukeRE.test( src ) ) {

					addLines( funcName, src, prefix );

				}

				oldFn.apply( obj, arguments );

			};

		}
```
</details>

### `reportJSError(url: any, lineNo: any, colNo: any, msg: any): void`

**Parameters:**

- **`url`** `any`
- **`lineNo`** `any`
- **`colNo`** `any`
- **`msg`** `any`

**Returns:** `void`

**Calls:**

- `window.parent.getActualLineNumberAndMoveTo`
- `origConsole.error`
- `console.error`

<details><summary>Code</summary>

```typescript
function reportJSError( url, lineNo, colNo, msg ) {

		try {

			const { origUrl, actualLineNo } = window.parent.getActualLineNumberAndMoveTo( url, lineNo, colNo );
			url = origUrl;
			lineNo = actualLineNo;

		} catch ( ex ) {

			origConsole.error( ex );

		}
    console.error(url, "line:", lineNo, ":", msg);  // eslint-disable-line
	}
```
</details>

### `setupWorkerSupport(): void`

**Returns:** `void`

**Calls:**

- `complex_call_9237`
- `addContextLostHTML`
- `reportJSError`
- `parseStack`
- `console.error`
- `complex_call_10020`
- `listener`
- `e.stopImmediatePropagation`
- `origConsole.error`
- `fn`
- `Object.defineProperty`

<details><summary>Code</summary>

```typescript
function setupWorkerSupport() {

		function log( data ) {

			const { logType, msg } = data;
			console[ logType ]( '[Worker]', msg ); /* eslint-disable-line no-console */

		}

		function lostContext( /* data */ ) {

			addContextLostHTML();

		}

		function jsError( data ) {

			const { url, lineNo, colNo, msg } = data;
			reportJSError( url, lineNo, colNo, msg );

		}

		function jsErrorWithStack( data ) {

			const { url, stack, msg } = data;
			const errorInfo = parseStack( stack );
			if ( errorInfo ) {

				reportJSError( errorInfo.url || url, errorInfo.lineNo, errorInfo.colNo, msg );

			} else {

        console.error(errorMsg)  // eslint-disable-line
			}

		}

		const handlers = {
			log,
			lostContext,
			jsError,
			jsErrorWithStack,
		};
		const OrigWorker = self.Worker;
		class WrappedWorker extends OrigWorker {

			constructor( url, ...args ) {

				super( url, ...args );
				let listener;
				this.onmessage = function ( e ) {

					if ( ! e || ! e.data || e.data.type !== '___editor___' ) {

						if ( listener ) {

							listener( e );

						}

						return;

					}

					e.stopImmediatePropagation();
					const data = e.data.data;
					const fn = handlers[ data.type ];
					if ( typeof fn !== 'function' ) {

						origConsole.error( 'unknown editor msg:', data.type );

					} else {

						fn( data );

					}

					return;

				};

				Object.defineProperty( this, 'onmessage', {
					get() {

						return listener;

					},
					set( fn ) {

						listener = fn;

					},
				} );

			}

		}
		self.Worker = WrappedWorker;

	}
```
</details>

### `log(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_9237`

<details><summary>Code</summary>

```typescript
function log( data ) {

			const { logType, msg } = data;
			console[ logType ]( '[Worker]', msg ); /* eslint-disable-line no-console */

		}
```
</details>

### `lostContext(): void`

**Returns:** `void`

**Calls:**

- `addContextLostHTML`

<details><summary>Code</summary>

```typescript
function lostContext( /* data */ ) {

			addContextLostHTML();

		}
```
</details>

### `jsError(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `reportJSError`

<details><summary>Code</summary>

```typescript
function jsError( data ) {

			const { url, lineNo, colNo, msg } = data;
			reportJSError( url, lineNo, colNo, msg );

		}
```
</details>

### `jsErrorWithStack(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `parseStack`
- `reportJSError`
- `console.error`

<details><summary>Code</summary>

```typescript
function jsErrorWithStack( data ) {

			const { url, stack, msg } = data;
			const errorInfo = parseStack( stack );
			if ( errorInfo ) {

				reportJSError( errorInfo.url || url, errorInfo.lineNo, errorInfo.colNo, msg );

			} else {

        console.error(errorMsg)  // eslint-disable-line
			}

		}
```
</details>

### `addContextLostHTML(): void`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `div.addEventListener`
- `window.location.reload`
- `document.body.appendChild`

<details><summary>Code</summary>

```typescript
function addContextLostHTML() {

		const div = document.createElement( 'div' );
		div.className = 'contextlost';
		div.innerHTML = '<div>Context Lost: Click To Reload</div>';
		div.addEventListener( 'click', function () {

			window.location.reload();

		} );
		document.body.appendChild( div );

	}
```
</details>

### `setupLesson(canvas: HTMLCanvasElement): void`

**Parameters:**

- **`canvas`** `HTMLCanvasElement`

**Returns:** `void`

**Calls:**

- `canvas.addEventListener`
- `addContextLostHTML`
- `isInIFrame`
- `updateCSSIfInIFrame`

**Internal Comments:**
```
// only once (x3)
// the default is to do nothing. Preventing the default (x3)
// means allowing context to be restored (x3)
// e.preventDefault();  // can't do this because firefox bug - https://bugzilla.mozilla.org/show_bug.cgi?id=1633280 (x3)
```

<details><summary>Code</summary>

```typescript
function ( canvas ) {

		// only once
		setupLesson = function () {};

		if ( canvas ) {

			canvas.addEventListener( 'webglcontextlost', function () {

				// the default is to do nothing. Preventing the default
				// means allowing context to be restored
				// e.preventDefault();  // can't do this because firefox bug - https://bugzilla.mozilla.org/show_bug.cgi?id=1633280
				addContextLostHTML();

			} );
			/* can't do this because firefox bug - https://bugzilla.mozilla.org/show_bug.cgi?id=1633280
      canvas.addEventListener('webglcontextrestored', function() {
          // just reload the page. Easiest.
          window.location.reload();
      });
      */

		}

		if ( isInIFrame() ) {

			updateCSSIfInIFrame();

		}

	}
```
</details>

### `rAFHandler(time: any): void`

**Parameters:**

- **`time`** `any`

**Returns:** `void`

**Calls:**

- `fakeRAFIdToCallbackMap.keys`
- `fakeRAFIdToCallbackMap.get`
- `fakeRAFIdToCallbackMap.delete`
- `callback`

<details><summary>Code</summary>

```typescript
function rAFHandler( time ) {

				rafRequestId = undefined;
				const ids = [ ...fakeRAFIdToCallbackMap.keys() ]; // WTF! Map.keys() iterates over live keys!
				for ( const id of ids ) {

					const callback = fakeRAFIdToCallbackMap.get( id );
					fakeRAFIdToCallbackMap.delete( id );
					if ( callback ) {

						callback( time );

					}

				}

			}
```
</details>

### `startRAFIfIntersectingAndNeeded(): void`

**Returns:** `void`

**Calls:**

- `oldRAF`

<details><summary>Code</summary>

```typescript
function startRAFIfIntersectingAndNeeded() {

				if ( ! rafRequestId && isBodyOnScreen && fakeRAFIdToCallbackMap.size > 0 ) {

					rafRequestId = oldRAF( rAFHandler );

				}

			}
```
</details>

### `stopRAF(): void`

**Returns:** `void`

**Calls:**

- `oldCancelRAF`

<details><summary>Code</summary>

```typescript
function stopRAF() {

				if ( rafRequestId ) {

					oldCancelRAF( rafRequestId );
					rafRequestId = undefined;

				}

			}
```
</details>

### `initIntersectionObserver(): void`

**Returns:** `void`

**Calls:**

- `entries.forEach`
- `startRAFIfIntersectingAndNeeded`
- `stopRAF`
- `intersectionObserver.observe`

<details><summary>Code</summary>

```typescript
function initIntersectionObserver() {

				const intersectionObserver = new IntersectionObserver( ( entries ) => {

					entries.forEach( entry => {

						isBodyOnScreen = entry.isIntersecting;

					} );
					if ( isBodyOnScreen ) {

						startRAFIfIntersectingAndNeeded();

					} else {

						stopRAF();

					}

				} );
				intersectionObserver.observe( document.body );

			}
```
</details>

### `betterRAF(callback: any): number`

**Parameters:**

- **`callback`** `any`

**Returns:** `number`

**Calls:**

- `fakeRAFIdToCallbackMap.set`
- `startRAFIfIntersectingAndNeeded`

<details><summary>Code</summary>

```typescript
function betterRAF( callback ) {

				const fakeRAFId = nextFakeRAFId ++;
				fakeRAFIdToCallbackMap.set( fakeRAFId, callback );
				startRAFIfIntersectingAndNeeded();
				return fakeRAFId;

			}
```
</details>

### `betterCancelRAF(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `fakeRAFIdToCallbackMap.delete`

<details><summary>Code</summary>

```typescript
function betterCancelRAF( id ) {

				fakeRAFIdToCallbackMap.delete( id );

			}
```
</details>

### `captureJSErrors(): void`

**Returns:** `void`

**Calls:**

- `window.addEventListener`
- `reportJSError`
- `origConsole.error`

**Internal Comments:**
```
// capture JavaScript Errors (x4)
```

<details><summary>Code</summary>

```typescript
function captureJSErrors() {

		// capture JavaScript Errors
		window.addEventListener( 'error', function ( e ) {

			const msg = e.message || e.error;
			const url = e.filename;
			const lineNo = e.lineno || 1;
			const colNo = e.colno || 1;
			reportJSError( url, lineNo, colNo, msg );
			origConsole.error( e.error );

		} );

	}
```
</details>

### `getBrowser(): { name: string; version: string; }`

**Returns:** `{ name: string; version: string; }`

**Calls:**

- `userAgent.match`
- `/trident/i.test`
- `/\brv[ :]+(\d+)/g.exec`
- `temp[ 1 ].replace`
- `m.splice`

<details><summary>Code</summary>

```typescript
function getBrowser() {

		const userAgent = navigator.userAgent;
		let m = userAgent.match( /(opera|chrome|safari|firefox|msie|trident(?=\/))\/?\s*(\d+)/i ) || [];
		if ( /trident/i.test( m[ 1 ] ) ) {

			m = /\brv[ :]+(\d+)/g.exec( userAgent ) || [];
			return {
				name: 'IE',
				version: m[ 1 ],
			};

		}

		if ( m[ 1 ] === 'Chrome' ) {

			const temp = userAgent.match( /\b(OPR|Edge)\/(\d+)/ );
			if ( temp ) {

				return {
					name: temp[ 1 ].replace( 'OPR', 'Opera' ),
					version: temp[ 2 ],
				};

			}

		}

		m = m[ 2 ] ? [ m[ 1 ], m[ 2 ] ] : [ navigator.appName, navigator.appVersion, '-?' ];
		const version = userAgent.match( /version\/(\d+)/i );
		if ( version ) {

			m.splice( 1, 1, version[ 1 ] );

		}

		return {
			name: m[ 0 ],
			version: m[ 1 ],
		};

	}
```
</details>

### `installWebGLLessonSetup(): void`

**Returns:** `void`

**Calls:**

- `complex_call_15835`
- `canvasesToTimeoutMap.get`
- `clearTimeout`
- `isWebGLRE.test`
- `isWebGL2RE.test`
- `setupLesson`
- `[].slice.apply`
- `oldFn.apply`
- `canvasesToTimeoutMap.set`
- `setTimeout`
- `canvasesToTimeoutMap.delete`
- `showNeedWebGL`

**Internal Comments:**
```
// three tries webgl2 then webgl1 (x4)
// so wait 1/2 a second before showing the failure (x4)
// message. If we get success on the same canvas (x4)
// we'll cancel this. (x4)
```

<details><summary>Code</summary>

```typescript
function installWebGLLessonSetup() {

		HTMLCanvasElement.prototype.getContext = ( function ( oldFn ) {

			return function () {

				const timeoutId = canvasesToTimeoutMap.get( this );
				if ( timeoutId ) {

					clearTimeout( timeoutId );

				}

				const type = arguments[ 0 ];
				const isWebGL1or2 = isWebGLRE.test( type );
				const isWebGL2 = isWebGL2RE.test( type );
				if ( isWebGL1or2 ) {

					setupLesson( this );

				}

				const args = [].slice.apply( arguments );
				args[ 1 ] = {
					powerPreference: 'low-power',
					...args[ 1 ],
				};
				const ctx = oldFn.apply( this, args );
				if ( ! ctx ) {

					if ( isWebGL2 ) {

						// three tries webgl2 then webgl1
						// so wait 1/2 a second before showing the failure
						// message. If we get success on the same canvas
						// we'll cancel this.
						canvasesToTimeoutMap.set( this, setTimeout( () => {

							canvasesToTimeoutMap.delete( this );
							showNeedWebGL( this );

						}, 500 ) );

					} else {

						showNeedWebGL( this );

					}

				}

				return ctx;

			};

		}( HTMLCanvasElement.prototype.getContext ) );

	}
```
</details>

### `installWebGLDebugContextCreator(): void`

**Returns:** `void`

**Calls:**

- `complex_call_17146`
- `oldFn.apply`
- `makeDebugContext`
- `[].map.call`
- `glFunctionArgToString`
- `str.substring`
- `glEnumToString`
- `enumedArgs.join`
- `parseStack`
- `reportJSError`
- `console.error`

**Internal Comments:**
```
// capture GL errors (x5)
// Using bindTexture to see if it's WebGL. Could check for instanceof WebGLRenderingContext
// but that might fail if wrapped by debugging extension
// shorten because of long arrays
```

<details><summary>Code</summary>

```typescript
function installWebGLDebugContextCreator() {

		if ( ! self.webglDebugHelper ) {

			return;

		}

		const {
			makeDebugContext,
			glFunctionArgToString,
			glEnumToString,
		} = self.webglDebugHelper;

		// capture GL errors
		HTMLCanvasElement.prototype.getContext = ( function ( oldFn ) {

			return function () {

				let ctx = oldFn.apply( this, arguments );
				// Using bindTexture to see if it's WebGL. Could check for instanceof WebGLRenderingContext
				// but that might fail if wrapped by debugging extension
				if ( ctx && ctx.bindTexture ) {

					ctx = makeDebugContext( ctx, {
						maxDrawCalls: 100,
						errorFunc: function ( err, funcName, args ) {

							const numArgs = args.length;
							const enumedArgs = [].map.call( args, function ( arg, ndx ) {

								let str = glFunctionArgToString( funcName, numArgs, ndx, arg );
								// shorten because of long arrays
								if ( str.length > 200 ) {

									str = str.substring( 0, 200 ) + '...';

								}

								return str;

							} );
							const errorMsg = `WebGL error ${glEnumToString( err )} in ${funcName}(${enumedArgs.join( ', ' )})`;
							const errorInfo = parseStack( ( new Error() ).stack );
							if ( errorInfo ) {

								reportJSError( errorInfo.url, errorInfo.lineNo, errorInfo.colNo, errorMsg );

							} else {

                console.error(errorMsg)  // eslint-disable-line
							}

						},
					} );

				}

				return ctx;

			};

		}( HTMLCanvasElement.prototype.getContext ) );

	}
```
</details>

### `errorFunc(err: any, funcName: any, args: any): void`

**Parameters:**

- **`err`** `any`
- **`funcName`** `any`
- **`args`** `any`

**Returns:** `void`

**Calls:**

- `[].map.call`
- `glFunctionArgToString`
- `str.substring`
- `glEnumToString`
- `enumedArgs.join`
- `parseStack`
- `reportJSError`
- `console.error`

**Internal Comments:**
```
// shorten because of long arrays
```

<details><summary>Code</summary>

```typescript
function ( err, funcName, args ) {

							const numArgs = args.length;
							const enumedArgs = [].map.call( args, function ( arg, ndx ) {

								let str = glFunctionArgToString( funcName, numArgs, ndx, arg );
								// shorten because of long arrays
								if ( str.length > 200 ) {

									str = str.substring( 0, 200 ) + '...';

								}

								return str;

							} );
							const errorMsg = `WebGL error ${glEnumToString( err )} in ${funcName}(${enumedArgs.join( ', ' )})`;
							const errorInfo = parseStack( ( new Error() ).stack );
							if ( errorInfo ) {

								reportJSError( errorInfo.url, errorInfo.lineNo, errorInfo.colNo, errorMsg );

							} else {

                console.error(errorMsg)  // eslint-disable-line
							}

						}
```
</details>

### `errorFunc(err: any, funcName: any, args: any): void`

**Parameters:**

- **`err`** `any`
- **`funcName`** `any`
- **`args`** `any`

**Returns:** `void`

**Calls:**

- `[].map.call`
- `glFunctionArgToString`
- `str.substring`
- `glEnumToString`
- `enumedArgs.join`
- `parseStack`
- `reportJSError`
- `console.error`

**Internal Comments:**
```
// shorten because of long arrays
```

<details><summary>Code</summary>

```typescript
function ( err, funcName, args ) {

							const numArgs = args.length;
							const enumedArgs = [].map.call( args, function ( arg, ndx ) {

								let str = glFunctionArgToString( funcName, numArgs, ndx, arg );
								// shorten because of long arrays
								if ( str.length > 200 ) {

									str = str.substring( 0, 200 ) + '...';

								}

								return str;

							} );
							const errorMsg = `WebGL error ${glEnumToString( err )} in ${funcName}(${enumedArgs.join( ', ' )})`;
							const errorInfo = parseStack( ( new Error() ).stack );
							if ( errorInfo ) {

								reportJSError( errorInfo.url, errorInfo.lineNo, errorInfo.colNo, errorMsg );

							} else {

                console.error(errorMsg)  // eslint-disable-line
							}

						}
```
</details>


---

## Classes

### `WrappedWorker`

<details><summary>Class Code</summary>

```ts
class WrappedWorker extends OrigWorker {

			constructor( url, ...args ) {

				super( url, ...args );
				let listener;
				this.onmessage = function ( e ) {

					if ( ! e || ! e.data || e.data.type !== '___editor___' ) {

						if ( listener ) {

							listener( e );

						}

						return;

					}

					e.stopImmediatePropagation();
					const data = e.data.data;
					const fn = handlers[ data.type ];
					if ( typeof fn !== 'function' ) {

						origConsole.error( 'unknown editor msg:', data.type );

					} else {

						fn( data );

					}

					return;

				};

				Object.defineProperty( this, 'onmessage', {
					get() {

						return listener;

					},
					set( fn ) {

						listener = fn;

					},
				} );

			}

		}
```
</details>


---