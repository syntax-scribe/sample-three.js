[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `GLSLNodeFunction.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/parsers/GLSLNodeFunction.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeFunction` | `../core/NodeFunction.js` |
| `NodeFunctionInput` | `../core/NodeFunctionInput.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `declarationRegexp` | `RegExp` | let/var | `/^\s*(highp\|mediump\|lowp)?\s*([a-z_0-9]+)\s*([a-z_0-9]+)?\s*\(([\s\S]*?)\)/i` | ✗ |
| `propertiesRegexp` | `RegExp` | let/var | `/[a-z_0-9]+/ig` | ✗ |
| `pragmaMain` | `"#pragma main"` | let/var | `'#pragma main'` | ✗ |
| `mainCode` | `any` | let/var | `pragmaMainIndex !== - 1 ? source.slice( pragmaMainIndex + pragmaMain.length )...` | ✗ |
| `inputsCode` | `any` | let/var | `declaration[ 4 ]` | ✗ |
| `propsMatches` | `any[]` | let/var | `[]` | ✗ |
| `nameMatch` | `any` | let/var | `null` | ✗ |
| `inputs` | `any[]` | let/var | `[]` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `isConst` | `boolean` | let/var | `propsMatches[ i ][ 0 ] === 'const'` | ✗ |
| `qualifier` | `string` | let/var | `propsMatches[ i ][ 0 ]` | ✗ |
| `type` | `string` | let/var | `propsMatches[ i ++ ][ 0 ]` | ✗ |
| `name` | `string` | let/var | `propsMatches[ i ++ ][ 0 ]` | ✗ |
| `name` | `any` | let/var | `declaration[ 3 ] !== undefined ? declaration[ 3 ] : ''` | ✗ |
| `type` | `any` | let/var | `declaration[ 2 ]` | ✗ |
| `precision` | `any` | let/var | `declaration[ 1 ] !== undefined ? declaration[ 1 ] : ''` | ✗ |
| `headerCode` | `any` | let/var | `pragmaMainIndex !== - 1 ? source.slice( 0, pragmaMainIndex ) : ''` | ✗ |
| `code` | `any` | let/var | `*not shown*` | ✗ |
| `blockCode` | `any` | let/var | `this.blockCode` | ✗ |
| `declarationCode` | `string` | let/var | ``${ type } ${ name } ( ${ inputsCode.trim() } )`` | ✗ |


---

## Functions

### `parse(source: any): { type: any; inputs: NodeFunctionInput[]; name: any; precision: any; inputsCode: any; blockCode: any; headerCode: any; }`

**Parameters:**

- **`source`** `any`

**Returns:** `{ type: any; inputs: NodeFunctionInput[]; name: any; precision: any; inputsCode: any; blockCode: any; headerCode: any; }`

**Calls:**

- `source.trim`
- `source.indexOf`
- `source.slice`
- `mainCode.match`
- `propertiesRegexp.exec`
- `propsMatches.push`
- `Number.parseInt`
- `Number.isNaN`
- `inputs.push`
- `mainCode.substring`

**Internal Comments:**
```
// tokenizer (x2)
// parser (x2)
// (x2)
```

<details><summary>Code</summary>

```typescript
( source ) => {

	source = source.trim();

	const pragmaMainIndex = source.indexOf( pragmaMain );

	const mainCode = pragmaMainIndex !== - 1 ? source.slice( pragmaMainIndex + pragmaMain.length ) : source;

	const declaration = mainCode.match( declarationRegexp );

	if ( declaration !== null && declaration.length === 5 ) {

		// tokenizer

		const inputsCode = declaration[ 4 ];
		const propsMatches = [];

		let nameMatch = null;

		while ( ( nameMatch = propertiesRegexp.exec( inputsCode ) ) !== null ) {

			propsMatches.push( nameMatch );

		}

		// parser

		const inputs = [];

		let i = 0;

		while ( i < propsMatches.length ) {

			const isConst = propsMatches[ i ][ 0 ] === 'const';

			if ( isConst === true ) {

				i ++;

			}

			let qualifier = propsMatches[ i ][ 0 ];

			if ( qualifier === 'in' || qualifier === 'out' || qualifier === 'inout' ) {

				i ++;

			} else {

				qualifier = '';

			}

			const type = propsMatches[ i ++ ][ 0 ];

			let count = Number.parseInt( propsMatches[ i ][ 0 ] );

			if ( Number.isNaN( count ) === false ) i ++;
			else count = null;

			const name = propsMatches[ i ++ ][ 0 ];

			inputs.push( new NodeFunctionInput( type, name, count, qualifier, isConst ) );

		}

		//

		const blockCode = mainCode.substring( declaration[ 0 ].length );

		const name = declaration[ 3 ] !== undefined ? declaration[ 3 ] : '';
		const type = declaration[ 2 ];

		const precision = declaration[ 1 ] !== undefined ? declaration[ 1 ] : '';

		const headerCode = pragmaMainIndex !== - 1 ? source.slice( 0, pragmaMainIndex ) : '';

		return {
			type,
			inputs,
			name,
			precision,
			inputsCode,
			blockCode,
			headerCode
		};

	} else {

		throw new Error( 'FunctionNode: Function is not a GLSL code.' );

	}

}
```
</details>

### `GLSLNodeFunction.getCode(name: string): string`

**JSDoc:**
```typescript
/**
	 * This method returns the GLSL code of the node function.
	 *
	 * @param {string} [name=this.name] - The function's name.
	 * @return {string} The shader code.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `string`

**Calls:**

- `inputsCode.trim`

**Internal Comments:**
```
// interface function (x3)
```

<details><summary>Code</summary>

```typescript
getCode( name = this.name ) {

		let code;

		const blockCode = this.blockCode;

		if ( blockCode !== '' ) {

			const { type, inputsCode, headerCode, precision } = this;

			let declarationCode = `${ type } ${ name } ( ${ inputsCode.trim() } )`;

			if ( precision !== '' ) {

				declarationCode = `${ precision } ${ declarationCode }`;

			}

			code = headerCode + declarationCode + blockCode;

		} else {

			// interface function

			code = '';

		}

		return code;

	}
```
</details>


---

## Classes

### `GLSLNodeFunction`

<details><summary>Class Code</summary>

```ts
class GLSLNodeFunction extends NodeFunction {

	/**
	 * Constructs a new GLSL node function.
	 *
	 * @param {string} source - The GLSL source.
	 */
	constructor( source ) {

		const { type, inputs, name, precision, inputsCode, blockCode, headerCode } = parse( source );

		super( type, inputs, name, precision );

		this.inputsCode = inputsCode;
		this.blockCode = blockCode;
		this.headerCode = headerCode;

	}

	/**
	 * This method returns the GLSL code of the node function.
	 *
	 * @param {string} [name=this.name] - The function's name.
	 * @return {string} The shader code.
	 */
	getCode( name = this.name ) {

		let code;

		const blockCode = this.blockCode;

		if ( blockCode !== '' ) {

			const { type, inputsCode, headerCode, precision } = this;

			let declarationCode = `${ type } ${ name } ( ${ inputsCode.trim() } )`;

			if ( precision !== '' ) {

				declarationCode = `${ precision } ${ declarationCode }`;

			}

			code = headerCode + declarationCode + blockCode;

		} else {

			// interface function

			code = '';

		}

		return code;

	}

}
```
</details>

#### Methods

##### `getCode(name: string): string`

<details><summary>Code</summary>

```ts
getCode( name = this.name ) {

		let code;

		const blockCode = this.blockCode;

		if ( blockCode !== '' ) {

			const { type, inputsCode, headerCode, precision } = this;

			let declarationCode = `${ type } ${ name } ( ${ inputsCode.trim() } )`;

			if ( precision !== '' ) {

				declarationCode = `${ precision } ${ declarationCode }`;

			}

			code = headerCode + declarationCode + blockCode;

		} else {

			// interface function

			code = '';

		}

		return code;

	}
```
</details>


---