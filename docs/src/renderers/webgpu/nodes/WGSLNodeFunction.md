[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WGSLNodeFunction.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/nodes/WGSLNodeFunction.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeFunction` | `../../../nodes/core/NodeFunction.js` |
| `NodeFunctionInput` | `../../../nodes/core/NodeFunctionInput.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `declarationRegexp` | `RegExp` | let/var | `/^[fn]*\s*([a-z_0-9]+)?\s*\(([\s\S]*?)\)\s*[\-\>]*\s*([a-z_0-9]+(?:<[\s\S]+?>...` | ✗ |
| `propertiesRegexp` | `RegExp` | let/var | `/([a-z_0-9]+)\s*:\s*([a-z_0-9]+(?:<[\s\S]+?>)?)/ig` | ✗ |
| `wgslTypeLib` | `{ f32: string; i32: string; u32: stri...` | let/var | `{ 'f32': 'float', 'i32': 'int', 'u32': 'uint', 'bool': 'bool', 'vec2<f32>': '...` | ✗ |
| `inputsCode` | `any` | let/var | `declaration[ 2 ]` | ✗ |
| `propsMatches` | `any[]` | let/var | `[]` | ✗ |
| `match` | `any` | let/var | `null` | ✗ |
| `inputs` | `any[]` | let/var | `[]` | ✗ |
| `resolvedType` | `string` | let/var | `type` | ✗ |
| `outputType` | `any` | let/var | `declaration[ 3 ] \|\| 'void'` | ✗ |
| `name` | `any` | let/var | `declaration[ 1 ] !== undefined ? declaration[ 1 ] : ''` | ✗ |
| `type` | `any` | let/var | `wgslTypeLib[ outputType ] \|\| outputType` | ✗ |
| `outputType` | `string` | let/var | `this.outputType !== 'void' ? '-> ' + this.outputType : ''` | ✗ |


---

## Functions

### `parse(source: any): { type: any; inputs: NodeFunctionInput[]; name: any; inputsCode: any; blockCode: any; outputType: any; }`

**Parameters:**

- **`source`** `any`

**Returns:** `{ type: any; inputs: NodeFunctionInput[]; name: any; inputsCode: any; blockCode: any; outputType: any; }`

**Calls:**

- `source.trim`
- `source.match`
- `propertiesRegexp.exec`
- `propsMatches.push`
- `resolvedType.startsWith`
- `type.split`
- `inputs.push`
- `source.substring`

**Internal Comments:**
```
// Process matches to correctly pair names and types (x2)
```

<details><summary>Code</summary>

```typescript
( source ) => {

	source = source.trim();

	const declaration = source.match( declarationRegexp );

	if ( declaration !== null && declaration.length === 4 ) {

		const inputsCode = declaration[ 2 ];
		const propsMatches = [];
		let match = null;

		while ( ( match = propertiesRegexp.exec( inputsCode ) ) !== null ) {

			propsMatches.push( { name: match[ 1 ], type: match[ 2 ] } );

		}

		// Process matches to correctly pair names and types
		const inputs = [];
		for ( let i = 0; i < propsMatches.length; i ++ ) {

			const { name, type } = propsMatches[ i ];

			let resolvedType = type;

			if ( resolvedType.startsWith( 'ptr' ) ) {

				resolvedType = 'pointer';

			} else {

				if ( resolvedType.startsWith( 'texture' ) ) {

					resolvedType = type.split( '<' )[ 0 ];

				}

				resolvedType = wgslTypeLib[ resolvedType ];

			}

			inputs.push( new NodeFunctionInput( resolvedType, name ) );

		}

		const blockCode = source.substring( declaration[ 0 ].length );
		const outputType = declaration[ 3 ] || 'void';

		const name = declaration[ 1 ] !== undefined ? declaration[ 1 ] : '';
		const type = wgslTypeLib[ outputType ] || outputType;

		return {
			type,
			inputs,
			name,
			inputsCode,
			blockCode,
			outputType
		};

	} else {

		throw new Error( 'FunctionNode: Function is not a WGSL code.' );

	}

}
```
</details>

### `WGSLNodeFunction.getCode(name: string): string`

**JSDoc:**
```typescript
/**
	 * This method returns the WGSL code of the node function.
	 *
	 * @param {string} [name=this.name] - The function's name.
	 * @return {string} The shader code.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `string`

**Calls:**

- `this.inputsCode.trim`

<details><summary>Code</summary>

```typescript
getCode( name = this.name ) {

		const outputType = this.outputType !== 'void' ? '-> ' + this.outputType : '';

		return `fn ${ name } ( ${ this.inputsCode.trim() } ) ${ outputType }` + this.blockCode;

	}
```
</details>


---

## Classes

### `WGSLNodeFunction`

<details><summary>Class Code</summary>

```ts
class WGSLNodeFunction extends NodeFunction {

	/**
	 * Constructs a new WGSL node function.
	 *
	 * @param {string} source - The WGSL source.
	 */
	constructor( source ) {

		const { type, inputs, name, inputsCode, blockCode, outputType } = parse( source );

		super( type, inputs, name );

		this.inputsCode = inputsCode;
		this.blockCode = blockCode;
		this.outputType = outputType;

	}

	/**
	 * This method returns the WGSL code of the node function.
	 *
	 * @param {string} [name=this.name] - The function's name.
	 * @return {string} The shader code.
	 */
	getCode( name = this.name ) {

		const outputType = this.outputType !== 'void' ? '-> ' + this.outputType : '';

		return `fn ${ name } ( ${ this.inputsCode.trim() } ) ${ outputType }` + this.blockCode;

	}

}
```
</details>

#### Methods

##### `getCode(name: string): string`

<details><summary>Code</summary>

```ts
getCode( name = this.name ) {

		const outputType = this.outputType !== 'void' ? '-> ' + this.outputType : '';

		return `fn ${ name } ( ${ this.inputsCode.trim() } ) ${ outputType }` + this.blockCode;

	}
```
</details>


---