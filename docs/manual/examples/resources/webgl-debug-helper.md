[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `webgl-debug-helper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 📊 Variables & Constants | 27 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/examples/resources/webgl-debug-helper.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `mappedContextTypes` | `{}` | let/var | `{}` | ✗ |
| `glEnums` | `any` | let/var | `{}` | ✗ |
| `enumStringToValue` | `any` | let/var | `{}` | ✗ |
| `enumStrings` | `any[]` | let/var | `[]` | ✗ |
| `orResult` | `number` | let/var | `0` | ✗ |
| `orEnums` | `any[]` | let/var | `[]` | ✗ |
| `enumValue` | `any` | let/var | `enumStringToValue[ enums[ i ] ]` | ✗ |
| `glValidEnumContexts` | `{ [x: number]: Function \| { [x: numb...` | let/var | `{ // Generic setters and getters 'enable': { 1: { 0: true } }, 'disable': { 1...` | ✗ |
| `name` | `any` | let/var | `glEnums[ value ]` | ✗ |
| `funcInfos` | `any` | let/var | `glValidEnumContexts[ functionName ]` | ✗ |
| `funcInfo` | `any` | let/var | `funcInfos[ numArgs ]` | ✗ |
| `argType` | `any` | let/var | `funcInfo[ argumentIndex ]` | ✗ |
| `argStrs` | `any[]` | let/var | `[]` | ✗ |
| `numArgs` | `any` | let/var | `args.length` | ✗ |
| `errCtx` | `any` | let/var | `options.errCtx \|\| ctx` | ✗ |
| `onFunc` | `any` | let/var | `options.funcFunc` | ✗ |
| `sharedState` | `any` | let/var | `options.sharedState \|\| { numDrawCallsRemaining: options.maxDrawCalls \|\| -...` | ✗ |
| `errorFunc` | `any` | let/var | `options.errorFunc \|\| function ( err, functionName, args ) { console.error( ...` | ✗ |
| `glErrorShadow` | `{}` | let/var | `{ }` | ✗ |
| `wrapper` | `{ getError(): string \| 0; }` | let/var | `{}` | ✗ |
| `pair` | `any` | let/var | `sharedState.wrappers[ name ]` | ✗ |
| `wrapper` | `any` | let/var | `pair.wrapper` | ✗ |
| `orig` | `any` | let/var | `pair.orig` | ✗ |
| `check` | `() => void` | let/var | `functionName.substring( 0, 4 ) === 'draw' ? checkMaxDrawCalls : noop` | ✗ |
| `extensionName` | `any` | let/var | `arguments[ 0 ]` | ✗ |
| `ext` | `any` | let/var | `sharedState.wrappers[ extensionName ]` | ✗ |
| `origExt` | `any` | let/var | `ext` | ✗ |


---

## Functions

### `addEnumsForContext(ctx: WebGLRenderingContext, type: any): void`

**JSDoc:**
```typescript
/**
   * Initializes this module. Safe to call more than once.
   * @param {!WebGLRenderingContext} ctx A WebGL context. If
   *    you have more than one context it doesn't matter which one
   *    you pass in, it is only used to pull out constants.
   */
```

**Parameters:**

- **`ctx`** `WebGLRenderingContext`
- **`type`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function addEnumsForContext( ctx, type ) {

		if ( ! mappedContextTypes[ type ] ) {

			mappedContextTypes[ type ] = true;
			for ( const propertyName in ctx ) {

				if ( typeof ctx[ propertyName ] === 'number' ) {

					glEnums[ ctx[ propertyName ] ] = propertyName;
					enumStringToValue[ propertyName ] = ctx[ propertyName ];

				}

			}

		}

	}
```
</details>

### `enumArrayToString(enums: any): string`

**Parameters:**

- **`enums`** `any`

**Returns:** `string`

**Calls:**

- `enums.push`
- `glEnumToString`
- `enumStrings.join`
- `enumStrings.toString`

<details><summary>Code</summary>

```typescript
function enumArrayToString( enums ) {

		const enumStrings = [];
		if ( enums.length ) {

			for ( let i = 0; i < enums.length; ++ i ) {

        enums.push(glEnumToString(enums[i]));  // eslint-disable-line
			}

			return '[' + enumStrings.join( ', ' ) + ']';

		}

		return enumStrings.toString();

	}
```
</details>

### `makeBitFieldToStringFunc(enums: any): (value: any) => string`

**Parameters:**

- **`enums`** `any`

**Returns:** `(value: any) => string`

**Calls:**

- `orEnums.push`
- `glEnumToString`
- `orEnums.join`

<details><summary>Code</summary>

```typescript
function makeBitFieldToStringFunc( enums ) {

		return function ( value ) {

			let orResult = 0;
			const orEnums = [];
			for ( let i = 0; i < enums.length; ++ i ) {

				const enumValue = enumStringToValue[ enums[ i ] ];
				if ( ( value & enumValue ) !== 0 ) {

					orResult |= enumValue;
          orEnums.push(glEnumToString(enumValue));  // eslint-disable-line
				}

			}

			if ( orResult === value ) {

				return orEnums.join( ' | ' );

			} else {

        return glEnumToString(value);  // eslint-disable-line
			}

		};

	}
```
</details>

### `glEnumToString(value: number): string`

**JSDoc:**
```typescript
/**
   * Gets an string version of an WebGL enum.
   *
   * Example:
   *   var str = WebGLDebugUtil.glEnumToString(ctx.getError());
   *
   * @param {number} value Value to return an enum for
   * @return {string} The string version of the enum.
   */
```

**Parameters:**

- **`value`** `number`

**Returns:** `string`

**Calls:**

- `value.toString`

<details><summary>Code</summary>

```typescript
function glEnumToString( value ) {

		const name = glEnums[ value ];
		return ( name !== undefined )
			? `gl.${name}`
			: `/*UNKNOWN WebGL ENUM*/ 0x${value.toString( 16 )}`;

	}
```
</details>

### `glFunctionArgToString(functionName: string, numArgs: number, argumentIndex: any, value: any): string`

**JSDoc:**
```typescript
/**
   * Returns the string version of a WebGL argument.
   * Attempts to convert enum arguments to strings.
   * @param {string} functionName the name of the WebGL function.
   * @param {number} numArgs the number of arguments passed to the function.
   * @param {number} argumentIndx the index of the argument.
   * @param {*} value The value of the argument.
   * @return {string} The value as a string.
   */
```

**Parameters:**

- **`functionName`** `string`
- **`numArgs`** `number`
- **`argumentIndex`** `any`
- **`value`** `any`

**Returns:** `string`

**Calls:**

- `argType`
- `glEnumToString`
- `value.toString`

<details><summary>Code</summary>

```typescript
function glFunctionArgToString( functionName, numArgs, argumentIndex, value ) {

		const funcInfos = glValidEnumContexts[ functionName ];
		if ( funcInfos !== undefined ) {

			const funcInfo = funcInfos[ numArgs ];
			if ( funcInfo !== undefined ) {

				const argType = funcInfo[ argumentIndex ];
				if ( argType ) {

					if ( typeof argType === 'function' ) {

						return argType( value );

					} else {

						return glEnumToString( value );

					}

				}

			}

		}

		if ( value === null ) {

			return 'null';

		} else if ( value === undefined ) {

			return 'undefined';

		} else {

			return value.toString();

		}

	}
```
</details>

### `glFunctionArgsToString(functionName: string, args: number): string`

**JSDoc:**
```typescript
/**
   * Converts the arguments of a WebGL function to a string.
   * Attempts to convert enum arguments to strings.
   *
   * @param {string} functionName the name of the WebGL function.
   * @param {number} args The arguments.
   * @return {string} The arguments as a string.
   */
```

**Parameters:**

- **`functionName`** `string`
- **`args`** `number`

**Returns:** `string`

**Calls:**

- `argStrs.push`
- `glFunctionArgToString`
- `argStrs.join`

**Internal Comments:**
```
// apparently we can't do args.join(","); (x2)
```

<details><summary>Code</summary>

```typescript
function glFunctionArgsToString( functionName, args ) {

		// apparently we can't do args.join(",");
		const argStrs = [];
		const numArgs = args.length;
		for ( let ii = 0; ii < numArgs; ++ ii ) {

			argStrs.push( glFunctionArgToString( functionName, numArgs, ii, args[ ii ] ) );

		}

		return argStrs.join( ', ' );

	}
```
</details>

### `makePropertyWrapper(wrapper: any, original: any, propertyName: any): void`

**Parameters:**

- **`wrapper`** `any`
- **`original`** `any`
- **`propertyName`** `any`

**Returns:** `void`

**Calls:**

- `wrapper.__defineGetter__`
- `wrapper.__defineSetter__`

**Internal Comments:**
```
// TODO(gmane): this needs to handle properties that take more than (x4)
// one value? (x4)
```

<details><summary>Code</summary>

```typescript
function makePropertyWrapper( wrapper, original, propertyName ) {

    wrapper.__defineGetter__(propertyName, function() {  // eslint-disable-line
			return original[ propertyName ];

		} );
		// TODO(gmane): this needs to handle properties that take more than
		// one value?
    wrapper.__defineSetter__(propertyName, function(value) {  // eslint-disable-line
			original[ propertyName ] = value;

		} );

	}
```
</details>

### `makeDebugContext(ctx: WebGLRenderingContext, options: any): { getError(): string | 0; }`

**JSDoc:**
```typescript
/**
   * Given a WebGL context returns a wrapped context that calls
   * gl.getError after every command and calls a function if the
   * result is not gl.NO_ERROR.
   *
   * @param {!WebGLRenderingContext} ctx The webgl context to
   *        wrap.
   * @param {!function(err, funcName, args): void} opt_onErrorFunc
   *        The function to call when gl.getError returns an
   *        error. If not specified the default function calls
   *        console.log with a message.
   * @param {!function(funcName, args): void} opt_onFunc The
   *        function to call when each webgl function is called.
   *        You can use this to log all calls for example.
   * @param {!WebGLRenderingContext} opt_err_ctx The webgl context
   *        to call getError on if different than ctx.
   */
```

**Parameters:**

- **`ctx`** `WebGLRenderingContext`
- **`options`** `any`

**Returns:** `{ getError(): string | 0; }`

**Calls:**

- `console.error`
- `glEnumToString`
- `glFunctionArgsToString`
- `Object.keys( sharedState.wrappers ).forEach`
- `orig[ propertyName ].bind`
- `removeChecks`
- `functionName.substring`
- `onFunc`
- `ctx[ functionName ].apply`
- `errCtx.getError`
- `errorFunc`
- `check`
- `wrapped.apply`
- `makeDebugContext`
- `addEnumsForContext`
- `makeErrorWrapper`
- `makeGetExtensionWrapper`
- `makePropertyWrapper`
- `Object.keys`

**Internal Comments:**
```
// Holds booleans for each GL error so after we get the error ourselves (x2)
// we can still return it to the client app. (x2)
// Makes a function that calls a WebGL function and then calls getError.
// Make an object that has a copy of every property of the WebGL context
// but wraps all functions.
// Override the getError function with one that returns our saved results.
```

<details><summary>Code</summary>

```typescript
function makeDebugContext( ctx, options ) {

		options = options || {};
		const errCtx = options.errCtx || ctx;
		const onFunc = options.funcFunc;
		const sharedState = options.sharedState || {
			numDrawCallsRemaining: options.maxDrawCalls || - 1,
			wrappers: {},
		};
		options.sharedState = sharedState;

		const errorFunc = options.errorFunc || function ( err, functionName, args ) {

			console.error( `WebGL error ${glEnumToString( err )} in ${functionName}(${glFunctionArgsToString( functionName, args )})` ); /* eslint-disable-line no-console */

		};

		// Holds booleans for each GL error so after we get the error ourselves
		// we can still return it to the client app.
		const glErrorShadow = { };
		const wrapper = {};

		function removeChecks() {

			Object.keys( sharedState.wrappers ).forEach( function ( name ) {

				const pair = sharedState.wrappers[ name ];
				const wrapper = pair.wrapper;
				const orig = pair.orig;
				for ( const propertyName in wrapper ) {

					if ( typeof wrapper[ propertyName ] === 'function' ) {

						wrapper[ propertyName ] = orig[ propertyName ].bind( orig );

					}

				}

			} );

		}

		function checkMaxDrawCalls() {

			if ( sharedState.numDrawCallsRemaining === 0 ) {

				removeChecks();

			}

			-- sharedState.numDrawCallsRemaining;

		}

		function noop() {
		}

		// Makes a function that calls a WebGL function and then calls getError.
		function makeErrorWrapper( ctx, functionName ) {

			const check = functionName.substring( 0, 4 ) === 'draw' ? checkMaxDrawCalls : noop;
			return function () {

				if ( onFunc ) {

					onFunc( functionName, arguments );

				}

				const result = ctx[ functionName ].apply( ctx, arguments );
				const err = errCtx.getError();
				if ( err !== 0 ) {

					glErrorShadow[ err ] = true;
					errorFunc( err, functionName, arguments );

				}

				check();
				return result;

			};

		}

		function makeGetExtensionWrapper( ctx, wrapped ) {

			return function () {

				const extensionName = arguments[ 0 ];
				let ext = sharedState.wrappers[ extensionName ];
				if ( ! ext ) {

					ext = wrapped.apply( ctx, arguments );
					if ( ext ) {

						const origExt = ext;
						ext = makeDebugContext( ext, { ...options, errCtx: ctx } );
						sharedState.wrappers[ extensionName ] = { wrapper: ext, orig: origExt };
						addEnumsForContext( origExt, extensionName );

					}

				}

				return ext;

			};

		}

		// Make an object that has a copy of every property of the WebGL context
		// but wraps all functions.
		for ( const propertyName in ctx ) {

			if ( typeof ctx[ propertyName ] === 'function' ) {

				if ( propertyName !== 'getExtension' ) {

					wrapper[ propertyName ] = makeErrorWrapper( ctx, propertyName );

				} else {

					const wrapped = makeErrorWrapper( ctx, propertyName );
					wrapper[ propertyName ] = makeGetExtensionWrapper( ctx, wrapped );

				}

			} else {

				makePropertyWrapper( wrapper, ctx, propertyName );

			}

		}

		// Override the getError function with one that returns our saved results.
		if ( wrapper.getError ) {

			wrapper.getError = function () {

				for ( const err of Object.keys( glErrorShadow ) ) {

					if ( glErrorShadow[ err ] ) {

						glErrorShadow[ err ] = false;
						return err;

					}

				}

				return ctx.NO_ERROR;

			};

		}

		if ( wrapper.bindBuffer ) {

			sharedState.wrappers[ 'webgl' ] = { wrapper: wrapper, orig: ctx };
			addEnumsForContext( ctx, ctx.bindBufferBase ? 'WebGL2' : 'WebGL' );

		}

		return wrapper;

	}
```
</details>

### `removeChecks(): void`

**Returns:** `void`

**Calls:**

- `Object.keys( sharedState.wrappers ).forEach`
- `orig[ propertyName ].bind`

<details><summary>Code</summary>

```typescript
function removeChecks() {

			Object.keys( sharedState.wrappers ).forEach( function ( name ) {

				const pair = sharedState.wrappers[ name ];
				const wrapper = pair.wrapper;
				const orig = pair.orig;
				for ( const propertyName in wrapper ) {

					if ( typeof wrapper[ propertyName ] === 'function' ) {

						wrapper[ propertyName ] = orig[ propertyName ].bind( orig );

					}

				}

			} );

		}
```
</details>

### `checkMaxDrawCalls(): void`

**Returns:** `void`

**Calls:**

- `removeChecks`

<details><summary>Code</summary>

```typescript
function checkMaxDrawCalls() {

			if ( sharedState.numDrawCallsRemaining === 0 ) {

				removeChecks();

			}

			-- sharedState.numDrawCallsRemaining;

		}
```
</details>

### `noop(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function noop() {
		}
```
</details>

### `makeErrorWrapper(ctx: any, functionName: any): (...args: any[]) => any`

**Parameters:**

- **`ctx`** `any`
- **`functionName`** `any`

**Returns:** `(...args: any[]) => any`

**Calls:**

- `functionName.substring`
- `onFunc`
- `ctx[ functionName ].apply`
- `errCtx.getError`
- `errorFunc`
- `check`

<details><summary>Code</summary>

```typescript
function makeErrorWrapper( ctx, functionName ) {

			const check = functionName.substring( 0, 4 ) === 'draw' ? checkMaxDrawCalls : noop;
			return function () {

				if ( onFunc ) {

					onFunc( functionName, arguments );

				}

				const result = ctx[ functionName ].apply( ctx, arguments );
				const err = errCtx.getError();
				if ( err !== 0 ) {

					glErrorShadow[ err ] = true;
					errorFunc( err, functionName, arguments );

				}

				check();
				return result;

			};

		}
```
</details>

### `makeGetExtensionWrapper(ctx: any, wrapped: any): (...args: any[]) => any`

**Parameters:**

- **`ctx`** `any`
- **`wrapped`** `any`

**Returns:** `(...args: any[]) => any`

**Calls:**

- `wrapped.apply`
- `makeDebugContext`
- `addEnumsForContext`

<details><summary>Code</summary>

```typescript
function makeGetExtensionWrapper( ctx, wrapped ) {

			return function () {

				const extensionName = arguments[ 0 ];
				let ext = sharedState.wrappers[ extensionName ];
				if ( ! ext ) {

					ext = wrapped.apply( ctx, arguments );
					if ( ext ) {

						const origExt = ext;
						ext = makeDebugContext( ext, { ...options, errCtx: ctx } );
						sharedState.wrappers[ extensionName ] = { wrapper: ext, orig: origExt };
						addEnumsForContext( origExt, extensionName );

					}

				}

				return ext;

			};

		}
```
</details>


---