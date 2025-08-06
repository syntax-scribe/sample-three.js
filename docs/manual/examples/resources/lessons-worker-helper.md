[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `lessons-worker-helper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/examples/resources/lessons-worker-helper.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `lessonSettings` | `{}` | let/var | `self.lessonSettings \|\| {}` | ✗ |
| `origConsole` | `{}` | let/var | `{}` | ✗ |
| `msg` | `any` | let/var | `e.message \|\| e.error` | ✗ |
| `url` | `string` | let/var | `e.filename` | ✗ |
| `lineNo` | `number` | let/var | `e.lineno \|\| 1` | ✗ |
| `colNo` | `number` | let/var | `e.colno \|\| 1` | ✗ |
| `isWebGLRE` | `RegExp` | let/var | `/^(webgl\|webgl2\|experimental-webgl)$/i` | ✗ |
| `type` | `any` | let/var | `arguments[ 0 ]` | ✗ |
| `numArgs` | `any` | let/var | `args.length` | ✗ |
| `error` | `Error` | let/var | `new Error()` | ✗ |


---

## Functions

### `isInEditor(): boolean`

**Returns:** `boolean`

**Calls:**

- `self.location.href.substring`

<details><summary>Code</summary>

```typescript
function isInEditor() {

		return self.location.href.substring( 0, 4 ) === 'blob';

	}
```
</details>

### `sendMessage(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `self.postMessage`

<details><summary>Code</summary>

```typescript
function sendMessage( data ) {

		self.postMessage( {
			type: '__editor__',
			data,
		} );

	}
```
</details>

### `setupConsole(): void`

**Returns:** `void`

**Calls:**

- `obj[ logType ].bind`
- `origFunc`
- `sendMessage`
- `[ ...args ].join`
- `wrapFunc`

<details><summary>Code</summary>

```typescript
function setupConsole() {

		function wrapFunc( obj, logType ) {

			const origFunc = obj[ logType ].bind( obj );
			origConsole[ logType ] = origFunc;
			return function ( ...args ) {

				origFunc( ...args );
				sendMessage( {
					type: 'log',
					logType,
					msg: [ ...args ].join( ' ' ),
				} );

			};

		}

		self.console.log = wrapFunc( self.console, 'log' );
		self.console.warn = wrapFunc( self.console, 'warn' );
		self.console.error = wrapFunc( self.console, 'error' );

	}
```
</details>

### `wrapFunc(obj: any, logType: any): (...args: any[]) => void`

**Parameters:**

- **`obj`** `any`
- **`logType`** `any`

**Returns:** `(...args: any[]) => void`

**Calls:**

- `obj[ logType ].bind`
- `origFunc`
- `sendMessage`
- `[ ...args ].join`

<details><summary>Code</summary>

```typescript
function wrapFunc( obj, logType ) {

			const origFunc = obj[ logType ].bind( obj );
			origConsole[ logType ] = origFunc;
			return function ( ...args ) {

				origFunc( ...args );
				sendMessage( {
					type: 'log',
					logType,
					msg: [ ...args ].join( ' ' ),
				} );

			};

		}
```
</details>

### `setupLesson(canvas: OffscreenCanvas): void`

**Parameters:**

- **`canvas`** `OffscreenCanvas`

**Returns:** `void`

**Calls:**

- `canvas.addEventListener`
- `sendMessage`

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
				sendMessage( {
					type: 'lostContext',
				} );

			} );

		}

	}
```
</details>

### `captureJSErrors(): void`

**Returns:** `void`

**Calls:**

- `self.addEventListener`
- `sendMessage`

**Internal Comments:**
```
// capture JavaScript Errors (x4)
```

<details><summary>Code</summary>

```typescript
function captureJSErrors() {

		// capture JavaScript Errors
		self.addEventListener( 'error', function ( e ) {

			const msg = e.message || e.error;
			const url = e.filename;
			const lineNo = e.lineno || 1;
			const colNo = e.colno || 1;
			sendMessage( {
				type: 'jsError',
				lineNo,
				colNo,
				url,
				msg,
			} );

		} );

	}
```
</details>

### `installWebGLLessonSetup(): void`

**Returns:** `void`

**Calls:**

- `complex_call_3537`
- `isWebGLRE.test`
- `setupLesson`
- `[].slice.apply`
- `oldFn.apply`

<details><summary>Code</summary>

```typescript
function installWebGLLessonSetup() {

		OffscreenCanvas.prototype.getContext = ( function ( oldFn ) { // eslint-disable-line compat/compat

			return function () {

				const type = arguments[ 0 ];
				const isWebGL = isWebGLRE.test( type );
				if ( isWebGL ) {

					setupLesson( this );

				}

				const args = [].slice.apply( arguments );
				args[ 1 ] = {
					powerPreference: 'low-power',
					...args[ 1 ],
				};
				return oldFn.apply( this, args );

			};

		}( OffscreenCanvas.prototype.getContext ) ); // eslint-disable-line compat/compat

	}
```
</details>

### `installWebGLDebugContextCreator(): void`

**Returns:** `void`

**Calls:**

- `complex_call_4286`
- `oldFn.apply`
- `makeDebugContext`
- `[].map.call`
- `glFunctionArgToString`
- `str.substring`
- `sendMessage`
- `glEnumToString`
- `enumedArgs.join`

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
		OffscreenCanvas.prototype.getContext = ( function ( oldFn ) { // eslint-disable-line compat/compat

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

							{

								const error = new Error();
								sendMessage( {
									type: 'jsErrorWithStack',
									stack: error.stack,
									msg: `${glEnumToString( err )} in ${funcName}(${enumedArgs.join( ', ' )})`,
								} );

							}

						},
					} );

				}

				return ctx;

			};

		}( OffscreenCanvas.prototype.getContext ) ); // eslint-disable-line compat/compat

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
- `sendMessage`
- `glEnumToString`
- `enumedArgs.join`

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

							{

								const error = new Error();
								sendMessage( {
									type: 'jsErrorWithStack',
									stack: error.stack,
									msg: `${glEnumToString( err )} in ${funcName}(${enumedArgs.join( ', ' )})`,
								} );

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
- `sendMessage`
- `glEnumToString`
- `enumedArgs.join`

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

							{

								const error = new Error();
								sendMessage( {
									type: 'jsErrorWithStack',
									stack: error.stack,
									msg: `${glEnumToString( err )} in ${funcName}(${enumedArgs.join( ', ' )})`,
								} );

							}

						}
```
</details>


---