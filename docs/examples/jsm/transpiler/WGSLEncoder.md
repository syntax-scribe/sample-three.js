[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WGSLEncoder.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 39 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/transpiler/WGSLEncoder.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `REVISION` | `three/webgpu` |
| `VariableDeclaration` | `./AST.js` |
| `Accessor` | `./AST.js` |
| `isExpression` | `./TranspilerUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `typeMap` | `{ float: string; int: string; uint: s...` | let/var | `{ 'float': 'f32', 'int': 'i32', 'uint': 'u32', 'bool': 'bool', 'vec2': 'vec2f...` | ✗ |
| `wgslLib` | `{ abs: string; acos: string; asin: st...` | let/var | `{ 'abs': 'abs', 'acos': 'acos', 'asin': 'asin', 'atan': 'atan', 'atan2': 'ata...` | ✗ |
| `code` | `any` | let/var | `*not shown*` | ✗ |
| `fnName` | `any` | let/var | `wgslLib[ node.name ] \|\| node.name` | ✗ |
| `modFnName` | `string` | let/var | `'mod_' + types.join( '_' )` | ✗ |
| `op` | `"-" \| "+"` | let/var | `node.type === '++' ? '+' : '-'` | ✗ |
| `wgslFn` | `any` | let/var | `wgslLib[ node.name ]` | ✗ |
| `samplerName` | `string` | let/var | ``${textureName}_sampler`` | ✗ |
| `code` | `any` | let/var | `*not shown*` | ✗ |
| `lodFetch` | `any` | let/var | `node.params.length > 2 ? this.emitExpression( node.params[ 2 ] ) : '0'` | ✗ |
| `code` | `string` | let/var | `''` | ✗ |
| `ifStr` | `any` | let/var | ``if ( ${ condStr } ) {\n\n${ bodyStr }\n\n${ this.tab }}`` | ✗ |
| `current` | `any` | let/var | `node` | ✗ |
| `switchStr` | `any` | let/var | ``switch ( ${ discriminant } ) {\n\n`` | ✗ |
| `declarations` | `any[]` | let/var | `[]` | ✗ |
| `current` | `any` | let/var | `node` | ✗ |
| `valueStr` | `string` | let/var | `''` | ✗ |
| `keyword` | `any` | let/var | `*not shown*` | ✗ |
| `name` | `any` | let/var | `node.name` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `body` | `any[]` | let/var | `[ ...node.body ]` | ✗ |
| `paramName` | `any` | let/var | `param.name` | ✗ |
| `immutableParamName` | `string` | let/var | ``${paramName}_in`` | ✗ |
| `immutableAccessor` | `Accessor` | let/var | `new Accessor( immutableParamName )` | ✗ |
| `mutableVar` | `VariableDeclaration` | let/var | `new VariableDeclaration( param.type, param.name, immutableAccessor )` | ✗ |
| `paramsStr` | `string` | let/var | `params.length > 0 ? ' ' + params.join( ', ' ) + ' ' : ''` | ✗ |
| `returnStr` | `string` | let/var | `( returnType && returnType !== 'void' ) ? ` -> ${returnType}` : ''` | ✗ |
| `previous` | `any` | let/var | `body[ index - 1 ]` | ✗ |
| `next` | `any` | let/var | `body[ index + 1 ]` | ✗ |
| `output` | `string` | let/var | `''` | ✗ |
| `previous` | `any` | let/var | `body[ index - 1 ]` | ✗ |
| `header` | `string` | let/var | `'// Three.js Transpiler r' + REVISION + '\n\n'` | ✗ |
| `globals` | `string` | let/var | `''` | ✗ |
| `functions` | `string` | let/var | `''` | ✗ |
| `dependencies` | `string` | let/var | `''` | ✗ |
| `bindingIndex` | `number` | let/var | `0` | ✗ |
| `uniformStructMembers` | `any[]` | let/var | `[]` | ✗ |
| `textureGlobals` | `any[]` | let/var | `[]` | ✗ |
| `location` | `number` | let/var | `0` | ✗ |


---

## Functions

### `WGSLEncoder.getWgslType(type: any): any`

**Parameters:**

- **`type`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getWgslType( type ) {

		return typeMap[ type ] || type;

	}
```
</details>

### `WGSLEncoder.emitExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.uniforms.find`
- `uniform.type.includes`
- `code.includes`
- `this.emitExpression`
- `node.params.map`
- `p.getType`
- `types.join`
- `this.polyfills.has`
- `this.polyfills.set`
- `this.getWgslType`
- `snippets.join`
- `fnName.startsWith`
- `this.emitTextureAccess`
- `params.join`
- `this.emitFor`
- `this.emitWhile`
- `this.emitSwitch`
- `this.emitVariables`
- `this.uniforms.push`
- `this.varyings.push`
- `this.emitConditional`
- `console.warn`

**Internal Comments:**
```
// Check if this accessor is part of a uniform struct (x2)
// WGSL requires floating point numbers to have a decimal
// Handle texture functions separately due to sampler handling (x3)
// Handle type constructors like vec3(...) (x3)
// WGSL's equivalent to the ternary operator is select(false_val, true_val, condition) (x3)
```

<details><summary>Code</summary>

```typescript
emitExpression( node ) {

		if ( ! node ) return '';

		let code;

		if ( node.isAccessor ) {

			// Check if this accessor is part of a uniform struct
			const uniform = this.uniforms.find( u => u.name === node.property );

			if ( uniform && ! uniform.type.includes( 'texture' ) ) {

				return `uniforms.${node.property}`;

			}

			code = node.property;

		} else if ( node.isNumber ) {

			code = node.value;

			// WGSL requires floating point numbers to have a decimal
			if ( node.type === 'float' && ! code.includes( '.' ) ) {

				code += '.0';

			}

		} else if ( node.isOperator ) {

			const left = this.emitExpression( node.left );
			const right = this.emitExpression( node.right );

			code = `${ left } ${ node.type } ${ right }`;

			if ( node.parent.isAssignment !== true && node.parent.isOperator ) {

				code = `( ${ code } )`;

			}

		} else if ( node.isFunctionCall ) {

			const fnName = wgslLib[ node.name ] || node.name;

			if ( fnName === 'mod' ) {

				const snippets = node.params.map( p => this.emitExpression( p ) );
				const types = node.params.map( p => p.getType() );

				const modFnName = 'mod_' + types.join( '_' );

				if ( this.polyfills.has( modFnName ) === false ) {

					this.polyfills.set( modFnName, `fn ${ modFnName }( x: ${ this.getWgslType( types[ 0 ] ) }, y: ${ this.getWgslType( types[ 1 ] ) } ) -> ${ this.getWgslType( types[ 0 ] ) } {

	return x - y * floor( x / y );

}` );

				}

				code = `${ modFnName }( ${ snippets.join( ', ' ) } )`;

			} else if ( fnName.startsWith( 'texture' ) ) {

				// Handle texture functions separately due to sampler handling

				code = this.emitTextureAccess( node );

			} else {

				const params = node.params.map( p => this.emitExpression( p ) );

				if ( typeMap[ fnName ] ) {

					// Handle type constructors like vec3(...)

					code = this.getWgslType( fnName );

				} else {

					code = fnName;

				}

				if ( params.length > 0 ) {

					code += '( ' + params.join( ', ' ) + ' )';

				} else {

					code += '()';

				}

			}

		} else if ( node.isReturn ) {

			code = 'return';

			if ( node.value ) {

				code += ' ' + this.emitExpression( node.value );

			}

		} else if ( node.isDiscard ) {

			code = 'discard';

		} else if ( node.isBreak ) {

			if ( node.parent.isSwitchCase !== true ) {

				code = 'break';

			}

		} else if ( node.isContinue ) {

			code = 'continue';

		} else if ( node.isAccessorElements ) {

			code = this.emitExpression( node.object );

			for ( const element of node.elements ) {

				const value = this.emitExpression( element.value );

				if ( element.isStaticElement ) {

					code += '.' + value;

				} else if ( element.isDynamicElement ) {

					code += `[${value}]`;

				}

			}

		} else if ( node.isFor ) {

			code = this.emitFor( node );

		} else if ( node.isWhile ) {

			code = this.emitWhile( node );

		} else if ( node.isSwitch ) {

			code = this.emitSwitch( node );

		} else if ( node.isVariableDeclaration ) {

			code = this.emitVariables( node );

		} else if ( node.isUniform ) {

			this.uniforms.push( node );
			return ''; // Defer emission to the header

		} else if ( node.isVarying ) {

			this.varyings.push( node );
			return ''; // Defer emission to the header

		} else if ( node.isTernary ) {

			const cond = this.emitExpression( node.cond );
			const left = this.emitExpression( node.left );
			const right = this.emitExpression( node.right );

			// WGSL's equivalent to the ternary operator is select(false_val, true_val, condition)
			code = `select( ${ right }, ${ left }, ${ cond } )`;

		} else if ( node.isConditional ) {

			code = this.emitConditional( node );

		} else if ( node.isUnary ) {

			const expr = this.emitExpression( node.expression );

			if ( node.type === '++' || node.type === '--' ) {

				const op = node.type === '++' ? '+' : '-';

				code = `${ expr } = ${ expr } ${ op } 1`;

			} else {

				code = `${ node.type }${ expr }`;

			}

		} else {

			console.warn( 'Unknown node type in WGSL Encoder:', node );

			code = `/* unknown node: ${ node.constructor.name } */`;

		}

		return code;

	}
```
</details>

### `WGSLEncoder.emitTextureAccess(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`

**Internal Comments:**
```
// WGSL requires explicit samplers. We assume a naming convention. (x2)
// format: textureSample(texture, sampler, coords, [offset]) (x3)
// Handle optional bias parameter (note: WGSL uses textureSampleBias)
// format: textureSampleLevel(texture, sampler, coords, level) (x2)
// format: textureSampleGrad(texture, sampler, coords, ddx, ddy) (x2)
// format: textureLoad(texture, coords, [level]) (x2)
```

<details><summary>Code</summary>

```typescript
emitTextureAccess( node ) {

		const wgslFn = wgslLib[ node.name ];
		const textureName = this.emitExpression( node.params[ 0 ] );
		const uv = this.emitExpression( node.params[ 1 ] );

		// WGSL requires explicit samplers. We assume a naming convention.
		const samplerName = `${textureName}_sampler`;

		let code;

		switch ( node.name ) {

			case 'texture':
			case 'texture2D':
			case 'texture3D':
			case 'textureCube':
				// format: textureSample(texture, sampler, coords, [offset])
				code = `${wgslFn}(${textureName}, ${samplerName}, ${uv}`;
				// Handle optional bias parameter (note: WGSL uses textureSampleBias)
				if ( node.params.length === 3 ) {

					const bias = this.emitExpression( node.params[ 2 ] );
					code = `textureSampleBias(${textureName}, ${samplerName}, ${uv}, ${bias})`;

				} else {

					code += ')';

				}

				break;

			case 'textureLod':
				// format: textureSampleLevel(texture, sampler, coords, level)
				const lod = this.emitExpression( node.params[ 2 ] );
				code = `${wgslFn}(${textureName}, ${samplerName}, ${uv}, ${lod})`;
				break;

			case 'textureGrad':
				// format: textureSampleGrad(texture, sampler, coords, ddx, ddy)
				const ddx = this.emitExpression( node.params[ 2 ] );
				const ddy = this.emitExpression( node.params[ 3 ] );
				code = `${wgslFn}(${textureName}, ${samplerName}, ${uv}, ${ddx}, ${ddy})`;
				break;

			case 'texelFetch':
				// format: textureLoad(texture, coords, [level])
				const coords = this.emitExpression( node.params[ 1 ] ); // should be ivec
				const lodFetch = node.params.length > 2 ? this.emitExpression( node.params[ 2 ] ) : '0';
				code = `${wgslFn}(${textureName}, ${coords}, ${lodFetch})`;
				break;

			default:
				code = `/* unsupported texture op: ${node.name} */`;

		}

		return code;

	}
```
</details>

### `WGSLEncoder.emitBody(body: any): string`

**Parameters:**

- **`body`** `any`

**Returns:** `string`

**Calls:**

- `this.emitExtraLine`
- `this.emitComment`
- `this.emitExpression`
- `statementCode.endsWith`
- `this.tab.slice`
- `code.slice`

<details><summary>Code</summary>

```typescript
emitBody( body ) {

		let code = '';
		this.tab += '\t';

		for ( const statement of body ) {

			code += this.emitExtraLine( statement, body );

			if ( statement.isComment ) {

				code += this.emitComment( statement, body );
				continue;

			}

			const statementCode = this.emitExpression( statement );

			if ( statementCode ) {

				code += this.tab + statementCode;

				if ( ! statementCode.endsWith( '}' ) && ! statementCode.endsWith( '{' ) ) {

					code += ';';

				}

				code += '\n';

			}

		}

		this.tab = this.tab.slice( 0, - 1 );
		return code.slice( 0, - 1 ); // remove the last extra line

	}
```
</details>

### `WGSLEncoder.emitConditional(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `this.emitBody`

<details><summary>Code</summary>

```typescript
emitConditional( node ) {

		const condStr = this.emitExpression( node.cond );
		const bodyStr = this.emitBody( node.body );

		let ifStr = `if ( ${ condStr } ) {\n\n${ bodyStr }\n\n${ this.tab }}`;

		let current = node;

		while ( current.elseConditional ) {

			current = current.elseConditional;
			const elseBodyStr = this.emitBody( current.body );

			if ( current.cond ) { // This is an 'else if'

				const elseCondStr = this.emitExpression( current.cond );

				ifStr += ` else if ( ${ elseCondStr } ) {\n\n${ elseBodyStr }\n\n${ this.tab }}`;

			} else { // This is an 'else'

				ifStr += ` else {\n\n${ elseBodyStr }\n\n${ this.tab }}`;

			}

		}

		return ifStr;

	}
```
</details>

### `WGSLEncoder.emitFor(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `this.emitBody`

<details><summary>Code</summary>

```typescript
emitFor( node ) {

		const init = this.emitExpression( node.initialization );
		const cond = this.emitExpression( node.condition );
		const after = this.emitExpression( node.afterthought );
		const body = this.emitBody( node.body );

		return `for ( ${ init }; ${ cond }; ${ after } ) {\n\n${ body }\n\n${ this.tab }}`;

	}
```
</details>

### `WGSLEncoder.emitWhile(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `this.emitBody`

<details><summary>Code</summary>

```typescript
emitWhile( node ) {

		const cond = this.emitExpression( node.condition );
		const body = this.emitBody( node.body );

		return `while ( ${ cond } ) {\n\n${ body }\n\n${ this.tab }}`;

	}
```
</details>

### `WGSLEncoder.emitSwitch(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `this.emitBody`
- `switchCase.conditions.map( c => this.emitExpression( c ) ).join`
- `this.tab.slice`

<details><summary>Code</summary>

```typescript
emitSwitch( node ) {

		const discriminant = this.emitExpression( node.discriminant );

		let switchStr = `switch ( ${ discriminant } ) {\n\n`;

		this.tab += '\t';

		for ( const switchCase of node.cases ) {

			const body = this.emitBody( switchCase.body );

			if ( switchCase.isDefault ) {

				switchStr += `${ this.tab }default: {\n\n${ body }\n\n${ this.tab }}\n\n`;

			} else {

				const cases = switchCase.conditions.map( c => this.emitExpression( c ) ).join( ', ' );

				switchStr += `${ this.tab }case ${ cases }: {\n\n${ body }\n\n${ this.tab }}\n\n`;

			}

		}

		this.tab = this.tab.slice( 0, - 1 );

		switchStr += `${this.tab}}`;

		return switchStr;

	}
```
</details>

### `WGSLEncoder.emitVariables(node: any): string`

**Parameters:**

- **`node`** `any`

**Returns:** `string`

**Calls:**

- `this.getWgslType`
- `this.emitExpression`
- `declarations.push`
- `declarations.join`

**Internal Comments:**
```
// The AST linker tracks if a variable is ever reassigned. (x2)
// If so, use 'var'; otherwise, use 'let'. (x2)
// In WGSL, multiple declarations in one line are not supported, so join with semicolons.
```

<details><summary>Code</summary>

```typescript
emitVariables( node ) {

		const declarations = [];

		let current = node;

		while ( current ) {

			const type = this.getWgslType( current.type );

			let valueStr = '';

			if ( current.value ) {

				valueStr = ` = ${this.emitExpression( current.value )}`;

			}

			// The AST linker tracks if a variable is ever reassigned.
			// If so, use 'var'; otherwise, use 'let'.

			let keyword;

			if ( current.linker ) {

				if ( current.linker.assignments.length > 0 ) {

					keyword = 'var'; // Reassigned variable

				} else {

					if ( current.value && current.value.isNumericExpression ) {

						keyword = 'const'; // Immutable numeric expression

					} else {

						keyword = 'let'; // Immutable variable

					}

				}

			}

			declarations.push( `${ keyword } ${ current.name }: ${ type }${ valueStr }` );

			current = current.next;

		}

		// In WGSL, multiple declarations in one line are not supported, so join with semicolons.
		return declarations.join( ';\n' + this.tab );

	}
```
</details>

### `WGSLEncoder.emitFunction(node: any): string`

**Parameters:**

- **`node`** `any`

**Returns:** `string`

**Calls:**

- `this.getWgslType`
- `params.push`
- `body.unshift`
- `params.join`
- `this.emitBody`

**Internal Comments:**
```
// We will prepend to a copy of the body, not the original AST node. (x2)
// Handle 'inout' and 'out' qualifiers using pointers. They are already mutable.
// If the parameter is reassigned within the function, we need to
// create a local, mutable variable that shadows the parameter's name.
// 1. Rename the incoming parameter to avoid name collision. (x2)
// 2. Create a new Accessor node for the renamed immutable parameter. (x2)
// 3. Create a new VariableDeclaration node for the mutable local variable. (x2)
// This new variable will have the original parameter's name. (x2)
// 4. Mark this new variable as mutable so `emitVariables` uses `var`. (x4)
// 5. Prepend this new declaration to the function's body. (x4)
// This parameter is not reassigned, so treat it as a normal immutable parameter. (x4)
// Emit the function body, which now includes our injected variable declarations. (x2)
```

<details><summary>Code</summary>

```typescript
emitFunction( node ) {

		const name = node.name;
		const returnType = this.getWgslType( node.type );

		const params = [];
		// We will prepend to a copy of the body, not the original AST node.
		const body = [ ...node.body ];

		for ( const param of node.params ) {

			const paramName = param.name;
			let paramType = this.getWgslType( param.type );

			// Handle 'inout' and 'out' qualifiers using pointers. They are already mutable.
			if ( param.qualifier === 'inout' || param.qualifier === 'out' ) {

				paramType = `ptr<function, ${paramType}>`;
				params.push( `${paramName}: ${paramType}` );
				continue;

			}

			// If the parameter is reassigned within the function, we need to
			// create a local, mutable variable that shadows the parameter's name.
			if ( param.linker && param.linker.assignments.length > 0 ) {

				// 1. Rename the incoming parameter to avoid name collision.
				const immutableParamName = `${paramName}_in`;
				params.push( `${immutableParamName}: ${paramType}` );

				// 2. Create a new Accessor node for the renamed immutable parameter.
				const immutableAccessor = new Accessor( immutableParamName );
				immutableAccessor.isAccessor = true;
				immutableAccessor.property = immutableParamName;

				// 3. Create a new VariableDeclaration node for the mutable local variable.
				// This new variable will have the original parameter's name.
				const mutableVar = new VariableDeclaration( param.type, param.name, immutableAccessor );

				// 4. Mark this new variable as mutable so `emitVariables` uses `var`.
				mutableVar.linker = { assignments: [ true ] };

				// 5. Prepend this new declaration to the function's body.
				body.unshift( mutableVar );

			} else {

				// This parameter is not reassigned, so treat it as a normal immutable parameter.
				params.push( `${paramName}: ${paramType}` );

			}

		}

		const paramsStr = params.length > 0 ? ' ' + params.join( ', ' ) + ' ' : '';
		const returnStr = ( returnType && returnType !== 'void' ) ? ` -> ${returnType}` : '';

		// Emit the function body, which now includes our injected variable declarations.
		const bodyStr = this.emitBody( body );

		return `fn ${name}(${paramsStr})${returnStr} {\n\n${bodyStr}\n\n${this.tab}}`;

	}
```
</details>

### `WGSLEncoder.emitComment(statement: any, body: any): string`

**Parameters:**

- **`statement`** `any`
- **`body`** `any`

**Returns:** `string`

**Calls:**

- `body.indexOf`
- `isExpression (from ./TranspilerUtils.js)`
- `statement.comment.replace`

<details><summary>Code</summary>

```typescript
emitComment( statement, body ) {

		const index = body.indexOf( statement );
		const previous = body[ index - 1 ];
		const next = body[ index + 1 ];

		let output = '';

		if ( previous && isExpression( previous ) ) {

			output += '\n';

		}

		output += this.tab + statement.comment.replace( /\n/g, '\n' + this.tab ) + '\n';

		if ( next && isExpression( next ) ) {

			output += '\n';

		}

		return output;

	}
```
</details>

### `WGSLEncoder.emitExtraLine(statement: any, body: any): "" | "\n"`

**Parameters:**

- **`statement`** `any`
- **`body`** `any`

**Returns:** `"" | "\n"`

**Calls:**

- `body.indexOf`
- `isExpression (from ./TranspilerUtils.js)`

<details><summary>Code</summary>

```typescript
emitExtraLine( statement, body ) {

		const index = body.indexOf( statement );
		const previous = body[ index - 1 ];

		if ( previous === undefined ) return '';

		if ( statement.isReturn ) return '\n';

		const lastExp = isExpression( previous );
		const currExp = isExpression( statement );

		if ( lastExp !== currExp || ( ! lastExp && ! currExp ) ) return '\n';

		return '';

	}
```
</details>

### `WGSLEncoder.emit(ast: any): string`

**Parameters:**

- **`ast`** `any`

**Returns:** `string`

**Calls:**

- `this.functions.set`
- `this.uniforms.push`
- `this.varyings.push`
- `uniform.type.includes`
- `textureGlobals.push`
- `this.getWgslType`
- `uniformStructMembers.push`
- `uniformStructMembers.join`
- `textureGlobals.join`
- `this.emitExtraLine`
- `this.emitFunction`
- `this.emitComment`
- `this.emitExpression`
- `this.polyfills.values`
- `functions.trimEnd`

**Internal Comments:**
```
// 1. Pre-process to find all global declarations
// 2. Build resource bindings (uniforms, textures, samplers)
// Textures are declared as separate global variables, not in the UBO
// Create a UBO struct if there are any non-texture uniforms
// Add the texture and sampler globals (x3)
// 3. Build varying structs for stage I/O
// This is a simplification; a full implementation would need to know the shader stage.
// 4. Emit all functions and other global statements
// Handle other top-level statements like 'const' (x3)
// 4. Build dependencies
```

<details><summary>Code</summary>

```typescript
emit( ast ) {

		const header = '// Three.js Transpiler r' + REVISION + '\n\n';

		let globals = '';
		let functions = '';
		let dependencies = '';

		// 1. Pre-process to find all global declarations
		for ( const statement of ast.body ) {

			if ( statement.isFunctionDeclaration ) {

				this.functions.set( statement.name, statement );

			} else if ( statement.isUniform ) {

				this.uniforms.push( statement );

			} else if ( statement.isVarying ) {

				this.varyings.push( statement );

			}

		}

		// 2. Build resource bindings (uniforms, textures, samplers)
		if ( this.uniforms.length > 0 ) {

			let bindingIndex = 0;
			const uniformStructMembers = [];
			const textureGlobals = [];

			for ( const uniform of this.uniforms ) {

				// Textures are declared as separate global variables, not in the UBO
				if ( uniform.type.includes( 'texture' ) ) {

					textureGlobals.push( `@group(${this.groupIndex}) @binding(${bindingIndex ++}) var ${uniform.name}: ${this.getWgslType( uniform.type )};` );
					textureGlobals.push( `@group(${this.groupIndex}) @binding(${bindingIndex ++}) var ${uniform.name}_sampler: sampler;` );

				} else {

					uniformStructMembers.push( `\t${uniform.name}: ${this.getWgslType( uniform.type )},` );

				}

			}

			// Create a UBO struct if there are any non-texture uniforms
			if ( uniformStructMembers.length > 0 ) {

				globals += 'struct Uniforms {\n';
				globals += uniformStructMembers.join( '\n' );
				globals += '\n};\n';
				globals += `@group(${this.groupIndex}) @binding(${bindingIndex ++}) var<uniform> uniforms: Uniforms;\n\n`;

			}

			// Add the texture and sampler globals
			globals += textureGlobals.join( '\n' ) + '\n\n';

		}

		// 3. Build varying structs for stage I/O
		// This is a simplification; a full implementation would need to know the shader stage.
		if ( this.varyings.length > 0 ) {

			globals += 'struct Varyings {\n';
			let location = 0;
			for ( const varying of this.varyings ) {

				globals += `\t@location(${location ++}) ${varying.name}: ${this.getWgslType( varying.type )},\n`;

			}

			globals += '};\n\n';

		}

		// 4. Emit all functions and other global statements
		for ( const statement of ast.body ) {

			functions += this.emitExtraLine( statement, ast.body );

			if ( statement.isFunctionDeclaration ) {

				functions += this.emitFunction( statement ) + '\n';

			} else if ( statement.isComment ) {

				functions += this.emitComment( statement, ast.body );

			} else if ( ! statement.isUniform && ! statement.isVarying ) {

				// Handle other top-level statements like 'const'
				functions += this.emitExpression( statement ) + ';\n';

			}

		}

		// 4. Build dependencies
		for ( const value of this.polyfills.values() ) {

			dependencies = `${ value }\n\n`;

		}

		return header + dependencies + globals + functions.trimEnd() + '\n';

	}
```
</details>


---

## Classes

### `WGSLEncoder`

<details><summary>Class Code</summary>

```ts
class WGSLEncoder {

	constructor() {

		this.tab = '';
		this.functions = new Map();
		this.uniforms = [];
		this.varyings = [];
		this.structs = new Map();
		this.polyfills = new Map();

		// Assume a single group for simplicity
		this.groupIndex = 0;

	}

	getWgslType( type ) {

		return typeMap[ type ] || type;

	}

	emitExpression( node ) {

		if ( ! node ) return '';

		let code;

		if ( node.isAccessor ) {

			// Check if this accessor is part of a uniform struct
			const uniform = this.uniforms.find( u => u.name === node.property );

			if ( uniform && ! uniform.type.includes( 'texture' ) ) {

				return `uniforms.${node.property}`;

			}

			code = node.property;

		} else if ( node.isNumber ) {

			code = node.value;

			// WGSL requires floating point numbers to have a decimal
			if ( node.type === 'float' && ! code.includes( '.' ) ) {

				code += '.0';

			}

		} else if ( node.isOperator ) {

			const left = this.emitExpression( node.left );
			const right = this.emitExpression( node.right );

			code = `${ left } ${ node.type } ${ right }`;

			if ( node.parent.isAssignment !== true && node.parent.isOperator ) {

				code = `( ${ code } )`;

			}

		} else if ( node.isFunctionCall ) {

			const fnName = wgslLib[ node.name ] || node.name;

			if ( fnName === 'mod' ) {

				const snippets = node.params.map( p => this.emitExpression( p ) );
				const types = node.params.map( p => p.getType() );

				const modFnName = 'mod_' + types.join( '_' );

				if ( this.polyfills.has( modFnName ) === false ) {

					this.polyfills.set( modFnName, `fn ${ modFnName }( x: ${ this.getWgslType( types[ 0 ] ) }, y: ${ this.getWgslType( types[ 1 ] ) } ) -> ${ this.getWgslType( types[ 0 ] ) } {

	return x - y * floor( x / y );

}` );

				}

				code = `${ modFnName }( ${ snippets.join( ', ' ) } )`;

			} else if ( fnName.startsWith( 'texture' ) ) {

				// Handle texture functions separately due to sampler handling

				code = this.emitTextureAccess( node );

			} else {

				const params = node.params.map( p => this.emitExpression( p ) );

				if ( typeMap[ fnName ] ) {

					// Handle type constructors like vec3(...)

					code = this.getWgslType( fnName );

				} else {

					code = fnName;

				}

				if ( params.length > 0 ) {

					code += '( ' + params.join( ', ' ) + ' )';

				} else {

					code += '()';

				}

			}

		} else if ( node.isReturn ) {

			code = 'return';

			if ( node.value ) {

				code += ' ' + this.emitExpression( node.value );

			}

		} else if ( node.isDiscard ) {

			code = 'discard';

		} else if ( node.isBreak ) {

			if ( node.parent.isSwitchCase !== true ) {

				code = 'break';

			}

		} else if ( node.isContinue ) {

			code = 'continue';

		} else if ( node.isAccessorElements ) {

			code = this.emitExpression( node.object );

			for ( const element of node.elements ) {

				const value = this.emitExpression( element.value );

				if ( element.isStaticElement ) {

					code += '.' + value;

				} else if ( element.isDynamicElement ) {

					code += `[${value}]`;

				}

			}

		} else if ( node.isFor ) {

			code = this.emitFor( node );

		} else if ( node.isWhile ) {

			code = this.emitWhile( node );

		} else if ( node.isSwitch ) {

			code = this.emitSwitch( node );

		} else if ( node.isVariableDeclaration ) {

			code = this.emitVariables( node );

		} else if ( node.isUniform ) {

			this.uniforms.push( node );
			return ''; // Defer emission to the header

		} else if ( node.isVarying ) {

			this.varyings.push( node );
			return ''; // Defer emission to the header

		} else if ( node.isTernary ) {

			const cond = this.emitExpression( node.cond );
			const left = this.emitExpression( node.left );
			const right = this.emitExpression( node.right );

			// WGSL's equivalent to the ternary operator is select(false_val, true_val, condition)
			code = `select( ${ right }, ${ left }, ${ cond } )`;

		} else if ( node.isConditional ) {

			code = this.emitConditional( node );

		} else if ( node.isUnary ) {

			const expr = this.emitExpression( node.expression );

			if ( node.type === '++' || node.type === '--' ) {

				const op = node.type === '++' ? '+' : '-';

				code = `${ expr } = ${ expr } ${ op } 1`;

			} else {

				code = `${ node.type }${ expr }`;

			}

		} else {

			console.warn( 'Unknown node type in WGSL Encoder:', node );

			code = `/* unknown node: ${ node.constructor.name } */`;

		}

		return code;

	}

	emitTextureAccess( node ) {

		const wgslFn = wgslLib[ node.name ];
		const textureName = this.emitExpression( node.params[ 0 ] );
		const uv = this.emitExpression( node.params[ 1 ] );

		// WGSL requires explicit samplers. We assume a naming convention.
		const samplerName = `${textureName}_sampler`;

		let code;

		switch ( node.name ) {

			case 'texture':
			case 'texture2D':
			case 'texture3D':
			case 'textureCube':
				// format: textureSample(texture, sampler, coords, [offset])
				code = `${wgslFn}(${textureName}, ${samplerName}, ${uv}`;
				// Handle optional bias parameter (note: WGSL uses textureSampleBias)
				if ( node.params.length === 3 ) {

					const bias = this.emitExpression( node.params[ 2 ] );
					code = `textureSampleBias(${textureName}, ${samplerName}, ${uv}, ${bias})`;

				} else {

					code += ')';

				}

				break;

			case 'textureLod':
				// format: textureSampleLevel(texture, sampler, coords, level)
				const lod = this.emitExpression( node.params[ 2 ] );
				code = `${wgslFn}(${textureName}, ${samplerName}, ${uv}, ${lod})`;
				break;

			case 'textureGrad':
				// format: textureSampleGrad(texture, sampler, coords, ddx, ddy)
				const ddx = this.emitExpression( node.params[ 2 ] );
				const ddy = this.emitExpression( node.params[ 3 ] );
				code = `${wgslFn}(${textureName}, ${samplerName}, ${uv}, ${ddx}, ${ddy})`;
				break;

			case 'texelFetch':
				// format: textureLoad(texture, coords, [level])
				const coords = this.emitExpression( node.params[ 1 ] ); // should be ivec
				const lodFetch = node.params.length > 2 ? this.emitExpression( node.params[ 2 ] ) : '0';
				code = `${wgslFn}(${textureName}, ${coords}, ${lodFetch})`;
				break;

			default:
				code = `/* unsupported texture op: ${node.name} */`;

		}

		return code;

	}

	emitBody( body ) {

		let code = '';
		this.tab += '\t';

		for ( const statement of body ) {

			code += this.emitExtraLine( statement, body );

			if ( statement.isComment ) {

				code += this.emitComment( statement, body );
				continue;

			}

			const statementCode = this.emitExpression( statement );

			if ( statementCode ) {

				code += this.tab + statementCode;

				if ( ! statementCode.endsWith( '}' ) && ! statementCode.endsWith( '{' ) ) {

					code += ';';

				}

				code += '\n';

			}

		}

		this.tab = this.tab.slice( 0, - 1 );
		return code.slice( 0, - 1 ); // remove the last extra line

	}

	emitConditional( node ) {

		const condStr = this.emitExpression( node.cond );
		const bodyStr = this.emitBody( node.body );

		let ifStr = `if ( ${ condStr } ) {\n\n${ bodyStr }\n\n${ this.tab }}`;

		let current = node;

		while ( current.elseConditional ) {

			current = current.elseConditional;
			const elseBodyStr = this.emitBody( current.body );

			if ( current.cond ) { // This is an 'else if'

				const elseCondStr = this.emitExpression( current.cond );

				ifStr += ` else if ( ${ elseCondStr } ) {\n\n${ elseBodyStr }\n\n${ this.tab }}`;

			} else { // This is an 'else'

				ifStr += ` else {\n\n${ elseBodyStr }\n\n${ this.tab }}`;

			}

		}

		return ifStr;

	}

	emitFor( node ) {

		const init = this.emitExpression( node.initialization );
		const cond = this.emitExpression( node.condition );
		const after = this.emitExpression( node.afterthought );
		const body = this.emitBody( node.body );

		return `for ( ${ init }; ${ cond }; ${ after } ) {\n\n${ body }\n\n${ this.tab }}`;

	}

	emitWhile( node ) {

		const cond = this.emitExpression( node.condition );
		const body = this.emitBody( node.body );

		return `while ( ${ cond } ) {\n\n${ body }\n\n${ this.tab }}`;

	}

	emitSwitch( node ) {

		const discriminant = this.emitExpression( node.discriminant );

		let switchStr = `switch ( ${ discriminant } ) {\n\n`;

		this.tab += '\t';

		for ( const switchCase of node.cases ) {

			const body = this.emitBody( switchCase.body );

			if ( switchCase.isDefault ) {

				switchStr += `${ this.tab }default: {\n\n${ body }\n\n${ this.tab }}\n\n`;

			} else {

				const cases = switchCase.conditions.map( c => this.emitExpression( c ) ).join( ', ' );

				switchStr += `${ this.tab }case ${ cases }: {\n\n${ body }\n\n${ this.tab }}\n\n`;

			}

		}

		this.tab = this.tab.slice( 0, - 1 );

		switchStr += `${this.tab}}`;

		return switchStr;

	}

	emitVariables( node ) {

		const declarations = [];

		let current = node;

		while ( current ) {

			const type = this.getWgslType( current.type );

			let valueStr = '';

			if ( current.value ) {

				valueStr = ` = ${this.emitExpression( current.value )}`;

			}

			// The AST linker tracks if a variable is ever reassigned.
			// If so, use 'var'; otherwise, use 'let'.

			let keyword;

			if ( current.linker ) {

				if ( current.linker.assignments.length > 0 ) {

					keyword = 'var'; // Reassigned variable

				} else {

					if ( current.value && current.value.isNumericExpression ) {

						keyword = 'const'; // Immutable numeric expression

					} else {

						keyword = 'let'; // Immutable variable

					}

				}

			}

			declarations.push( `${ keyword } ${ current.name }: ${ type }${ valueStr }` );

			current = current.next;

		}

		// In WGSL, multiple declarations in one line are not supported, so join with semicolons.
		return declarations.join( ';\n' + this.tab );

	}

	emitFunction( node ) {

		const name = node.name;
		const returnType = this.getWgslType( node.type );

		const params = [];
		// We will prepend to a copy of the body, not the original AST node.
		const body = [ ...node.body ];

		for ( const param of node.params ) {

			const paramName = param.name;
			let paramType = this.getWgslType( param.type );

			// Handle 'inout' and 'out' qualifiers using pointers. They are already mutable.
			if ( param.qualifier === 'inout' || param.qualifier === 'out' ) {

				paramType = `ptr<function, ${paramType}>`;
				params.push( `${paramName}: ${paramType}` );
				continue;

			}

			// If the parameter is reassigned within the function, we need to
			// create a local, mutable variable that shadows the parameter's name.
			if ( param.linker && param.linker.assignments.length > 0 ) {

				// 1. Rename the incoming parameter to avoid name collision.
				const immutableParamName = `${paramName}_in`;
				params.push( `${immutableParamName}: ${paramType}` );

				// 2. Create a new Accessor node for the renamed immutable parameter.
				const immutableAccessor = new Accessor( immutableParamName );
				immutableAccessor.isAccessor = true;
				immutableAccessor.property = immutableParamName;

				// 3. Create a new VariableDeclaration node for the mutable local variable.
				// This new variable will have the original parameter's name.
				const mutableVar = new VariableDeclaration( param.type, param.name, immutableAccessor );

				// 4. Mark this new variable as mutable so `emitVariables` uses `var`.
				mutableVar.linker = { assignments: [ true ] };

				// 5. Prepend this new declaration to the function's body.
				body.unshift( mutableVar );

			} else {

				// This parameter is not reassigned, so treat it as a normal immutable parameter.
				params.push( `${paramName}: ${paramType}` );

			}

		}

		const paramsStr = params.length > 0 ? ' ' + params.join( ', ' ) + ' ' : '';
		const returnStr = ( returnType && returnType !== 'void' ) ? ` -> ${returnType}` : '';

		// Emit the function body, which now includes our injected variable declarations.
		const bodyStr = this.emitBody( body );

		return `fn ${name}(${paramsStr})${returnStr} {\n\n${bodyStr}\n\n${this.tab}}`;

	}

	emitComment( statement, body ) {

		const index = body.indexOf( statement );
		const previous = body[ index - 1 ];
		const next = body[ index + 1 ];

		let output = '';

		if ( previous && isExpression( previous ) ) {

			output += '\n';

		}

		output += this.tab + statement.comment.replace( /\n/g, '\n' + this.tab ) + '\n';

		if ( next && isExpression( next ) ) {

			output += '\n';

		}

		return output;

	}

	emitExtraLine( statement, body ) {

		const index = body.indexOf( statement );
		const previous = body[ index - 1 ];

		if ( previous === undefined ) return '';

		if ( statement.isReturn ) return '\n';

		const lastExp = isExpression( previous );
		const currExp = isExpression( statement );

		if ( lastExp !== currExp || ( ! lastExp && ! currExp ) ) return '\n';

		return '';

	}

	emit( ast ) {

		const header = '// Three.js Transpiler r' + REVISION + '\n\n';

		let globals = '';
		let functions = '';
		let dependencies = '';

		// 1. Pre-process to find all global declarations
		for ( const statement of ast.body ) {

			if ( statement.isFunctionDeclaration ) {

				this.functions.set( statement.name, statement );

			} else if ( statement.isUniform ) {

				this.uniforms.push( statement );

			} else if ( statement.isVarying ) {

				this.varyings.push( statement );

			}

		}

		// 2. Build resource bindings (uniforms, textures, samplers)
		if ( this.uniforms.length > 0 ) {

			let bindingIndex = 0;
			const uniformStructMembers = [];
			const textureGlobals = [];

			for ( const uniform of this.uniforms ) {

				// Textures are declared as separate global variables, not in the UBO
				if ( uniform.type.includes( 'texture' ) ) {

					textureGlobals.push( `@group(${this.groupIndex}) @binding(${bindingIndex ++}) var ${uniform.name}: ${this.getWgslType( uniform.type )};` );
					textureGlobals.push( `@group(${this.groupIndex}) @binding(${bindingIndex ++}) var ${uniform.name}_sampler: sampler;` );

				} else {

					uniformStructMembers.push( `\t${uniform.name}: ${this.getWgslType( uniform.type )},` );

				}

			}

			// Create a UBO struct if there are any non-texture uniforms
			if ( uniformStructMembers.length > 0 ) {

				globals += 'struct Uniforms {\n';
				globals += uniformStructMembers.join( '\n' );
				globals += '\n};\n';
				globals += `@group(${this.groupIndex}) @binding(${bindingIndex ++}) var<uniform> uniforms: Uniforms;\n\n`;

			}

			// Add the texture and sampler globals
			globals += textureGlobals.join( '\n' ) + '\n\n';

		}

		// 3. Build varying structs for stage I/O
		// This is a simplification; a full implementation would need to know the shader stage.
		if ( this.varyings.length > 0 ) {

			globals += 'struct Varyings {\n';
			let location = 0;
			for ( const varying of this.varyings ) {

				globals += `\t@location(${location ++}) ${varying.name}: ${this.getWgslType( varying.type )},\n`;

			}

			globals += '};\n\n';

		}

		// 4. Emit all functions and other global statements
		for ( const statement of ast.body ) {

			functions += this.emitExtraLine( statement, ast.body );

			if ( statement.isFunctionDeclaration ) {

				functions += this.emitFunction( statement ) + '\n';

			} else if ( statement.isComment ) {

				functions += this.emitComment( statement, ast.body );

			} else if ( ! statement.isUniform && ! statement.isVarying ) {

				// Handle other top-level statements like 'const'
				functions += this.emitExpression( statement ) + ';\n';

			}

		}

		// 4. Build dependencies
		for ( const value of this.polyfills.values() ) {

			dependencies = `${ value }\n\n`;

		}

		return header + dependencies + globals + functions.trimEnd() + '\n';

	}

}
```
</details>

#### Methods

##### `getWgslType(type: any): any`

<details><summary>Code</summary>

```ts
getWgslType( type ) {

		return typeMap[ type ] || type;

	}
```
</details>

##### `emitExpression(node: any): any`

<details><summary>Code</summary>

```ts
emitExpression( node ) {

		if ( ! node ) return '';

		let code;

		if ( node.isAccessor ) {

			// Check if this accessor is part of a uniform struct
			const uniform = this.uniforms.find( u => u.name === node.property );

			if ( uniform && ! uniform.type.includes( 'texture' ) ) {

				return `uniforms.${node.property}`;

			}

			code = node.property;

		} else if ( node.isNumber ) {

			code = node.value;

			// WGSL requires floating point numbers to have a decimal
			if ( node.type === 'float' && ! code.includes( '.' ) ) {

				code += '.0';

			}

		} else if ( node.isOperator ) {

			const left = this.emitExpression( node.left );
			const right = this.emitExpression( node.right );

			code = `${ left } ${ node.type } ${ right }`;

			if ( node.parent.isAssignment !== true && node.parent.isOperator ) {

				code = `( ${ code } )`;

			}

		} else if ( node.isFunctionCall ) {

			const fnName = wgslLib[ node.name ] || node.name;

			if ( fnName === 'mod' ) {

				const snippets = node.params.map( p => this.emitExpression( p ) );
				const types = node.params.map( p => p.getType() );

				const modFnName = 'mod_' + types.join( '_' );

				if ( this.polyfills.has( modFnName ) === false ) {

					this.polyfills.set( modFnName, `fn ${ modFnName }( x: ${ this.getWgslType( types[ 0 ] ) }, y: ${ this.getWgslType( types[ 1 ] ) } ) -> ${ this.getWgslType( types[ 0 ] ) } {

	return x - y * floor( x / y );

}` );

				}

				code = `${ modFnName }( ${ snippets.join( ', ' ) } )`;

			} else if ( fnName.startsWith( 'texture' ) ) {

				// Handle texture functions separately due to sampler handling

				code = this.emitTextureAccess( node );

			} else {

				const params = node.params.map( p => this.emitExpression( p ) );

				if ( typeMap[ fnName ] ) {

					// Handle type constructors like vec3(...)

					code = this.getWgslType( fnName );

				} else {

					code = fnName;

				}

				if ( params.length > 0 ) {

					code += '( ' + params.join( ', ' ) + ' )';

				} else {

					code += '()';

				}

			}

		} else if ( node.isReturn ) {

			code = 'return';

			if ( node.value ) {

				code += ' ' + this.emitExpression( node.value );

			}

		} else if ( node.isDiscard ) {

			code = 'discard';

		} else if ( node.isBreak ) {

			if ( node.parent.isSwitchCase !== true ) {

				code = 'break';

			}

		} else if ( node.isContinue ) {

			code = 'continue';

		} else if ( node.isAccessorElements ) {

			code = this.emitExpression( node.object );

			for ( const element of node.elements ) {

				const value = this.emitExpression( element.value );

				if ( element.isStaticElement ) {

					code += '.' + value;

				} else if ( element.isDynamicElement ) {

					code += `[${value}]`;

				}

			}

		} else if ( node.isFor ) {

			code = this.emitFor( node );

		} else if ( node.isWhile ) {

			code = this.emitWhile( node );

		} else if ( node.isSwitch ) {

			code = this.emitSwitch( node );

		} else if ( node.isVariableDeclaration ) {

			code = this.emitVariables( node );

		} else if ( node.isUniform ) {

			this.uniforms.push( node );
			return ''; // Defer emission to the header

		} else if ( node.isVarying ) {

			this.varyings.push( node );
			return ''; // Defer emission to the header

		} else if ( node.isTernary ) {

			const cond = this.emitExpression( node.cond );
			const left = this.emitExpression( node.left );
			const right = this.emitExpression( node.right );

			// WGSL's equivalent to the ternary operator is select(false_val, true_val, condition)
			code = `select( ${ right }, ${ left }, ${ cond } )`;

		} else if ( node.isConditional ) {

			code = this.emitConditional( node );

		} else if ( node.isUnary ) {

			const expr = this.emitExpression( node.expression );

			if ( node.type === '++' || node.type === '--' ) {

				const op = node.type === '++' ? '+' : '-';

				code = `${ expr } = ${ expr } ${ op } 1`;

			} else {

				code = `${ node.type }${ expr }`;

			}

		} else {

			console.warn( 'Unknown node type in WGSL Encoder:', node );

			code = `/* unknown node: ${ node.constructor.name } */`;

		}

		return code;

	}
```
</details>

##### `emitTextureAccess(node: any): any`

<details><summary>Code</summary>

```ts
emitTextureAccess( node ) {

		const wgslFn = wgslLib[ node.name ];
		const textureName = this.emitExpression( node.params[ 0 ] );
		const uv = this.emitExpression( node.params[ 1 ] );

		// WGSL requires explicit samplers. We assume a naming convention.
		const samplerName = `${textureName}_sampler`;

		let code;

		switch ( node.name ) {

			case 'texture':
			case 'texture2D':
			case 'texture3D':
			case 'textureCube':
				// format: textureSample(texture, sampler, coords, [offset])
				code = `${wgslFn}(${textureName}, ${samplerName}, ${uv}`;
				// Handle optional bias parameter (note: WGSL uses textureSampleBias)
				if ( node.params.length === 3 ) {

					const bias = this.emitExpression( node.params[ 2 ] );
					code = `textureSampleBias(${textureName}, ${samplerName}, ${uv}, ${bias})`;

				} else {

					code += ')';

				}

				break;

			case 'textureLod':
				// format: textureSampleLevel(texture, sampler, coords, level)
				const lod = this.emitExpression( node.params[ 2 ] );
				code = `${wgslFn}(${textureName}, ${samplerName}, ${uv}, ${lod})`;
				break;

			case 'textureGrad':
				// format: textureSampleGrad(texture, sampler, coords, ddx, ddy)
				const ddx = this.emitExpression( node.params[ 2 ] );
				const ddy = this.emitExpression( node.params[ 3 ] );
				code = `${wgslFn}(${textureName}, ${samplerName}, ${uv}, ${ddx}, ${ddy})`;
				break;

			case 'texelFetch':
				// format: textureLoad(texture, coords, [level])
				const coords = this.emitExpression( node.params[ 1 ] ); // should be ivec
				const lodFetch = node.params.length > 2 ? this.emitExpression( node.params[ 2 ] ) : '0';
				code = `${wgslFn}(${textureName}, ${coords}, ${lodFetch})`;
				break;

			default:
				code = `/* unsupported texture op: ${node.name} */`;

		}

		return code;

	}
```
</details>

##### `emitBody(body: any): string`

<details><summary>Code</summary>

```ts
emitBody( body ) {

		let code = '';
		this.tab += '\t';

		for ( const statement of body ) {

			code += this.emitExtraLine( statement, body );

			if ( statement.isComment ) {

				code += this.emitComment( statement, body );
				continue;

			}

			const statementCode = this.emitExpression( statement );

			if ( statementCode ) {

				code += this.tab + statementCode;

				if ( ! statementCode.endsWith( '}' ) && ! statementCode.endsWith( '{' ) ) {

					code += ';';

				}

				code += '\n';

			}

		}

		this.tab = this.tab.slice( 0, - 1 );
		return code.slice( 0, - 1 ); // remove the last extra line

	}
```
</details>

##### `emitConditional(node: any): any`

<details><summary>Code</summary>

```ts
emitConditional( node ) {

		const condStr = this.emitExpression( node.cond );
		const bodyStr = this.emitBody( node.body );

		let ifStr = `if ( ${ condStr } ) {\n\n${ bodyStr }\n\n${ this.tab }}`;

		let current = node;

		while ( current.elseConditional ) {

			current = current.elseConditional;
			const elseBodyStr = this.emitBody( current.body );

			if ( current.cond ) { // This is an 'else if'

				const elseCondStr = this.emitExpression( current.cond );

				ifStr += ` else if ( ${ elseCondStr } ) {\n\n${ elseBodyStr }\n\n${ this.tab }}`;

			} else { // This is an 'else'

				ifStr += ` else {\n\n${ elseBodyStr }\n\n${ this.tab }}`;

			}

		}

		return ifStr;

	}
```
</details>

##### `emitFor(node: any): any`

<details><summary>Code</summary>

```ts
emitFor( node ) {

		const init = this.emitExpression( node.initialization );
		const cond = this.emitExpression( node.condition );
		const after = this.emitExpression( node.afterthought );
		const body = this.emitBody( node.body );

		return `for ( ${ init }; ${ cond }; ${ after } ) {\n\n${ body }\n\n${ this.tab }}`;

	}
```
</details>

##### `emitWhile(node: any): any`

<details><summary>Code</summary>

```ts
emitWhile( node ) {

		const cond = this.emitExpression( node.condition );
		const body = this.emitBody( node.body );

		return `while ( ${ cond } ) {\n\n${ body }\n\n${ this.tab }}`;

	}
```
</details>

##### `emitSwitch(node: any): any`

<details><summary>Code</summary>

```ts
emitSwitch( node ) {

		const discriminant = this.emitExpression( node.discriminant );

		let switchStr = `switch ( ${ discriminant } ) {\n\n`;

		this.tab += '\t';

		for ( const switchCase of node.cases ) {

			const body = this.emitBody( switchCase.body );

			if ( switchCase.isDefault ) {

				switchStr += `${ this.tab }default: {\n\n${ body }\n\n${ this.tab }}\n\n`;

			} else {

				const cases = switchCase.conditions.map( c => this.emitExpression( c ) ).join( ', ' );

				switchStr += `${ this.tab }case ${ cases }: {\n\n${ body }\n\n${ this.tab }}\n\n`;

			}

		}

		this.tab = this.tab.slice( 0, - 1 );

		switchStr += `${this.tab}}`;

		return switchStr;

	}
```
</details>

##### `emitVariables(node: any): string`

<details><summary>Code</summary>

```ts
emitVariables( node ) {

		const declarations = [];

		let current = node;

		while ( current ) {

			const type = this.getWgslType( current.type );

			let valueStr = '';

			if ( current.value ) {

				valueStr = ` = ${this.emitExpression( current.value )}`;

			}

			// The AST linker tracks if a variable is ever reassigned.
			// If so, use 'var'; otherwise, use 'let'.

			let keyword;

			if ( current.linker ) {

				if ( current.linker.assignments.length > 0 ) {

					keyword = 'var'; // Reassigned variable

				} else {

					if ( current.value && current.value.isNumericExpression ) {

						keyword = 'const'; // Immutable numeric expression

					} else {

						keyword = 'let'; // Immutable variable

					}

				}

			}

			declarations.push( `${ keyword } ${ current.name }: ${ type }${ valueStr }` );

			current = current.next;

		}

		// In WGSL, multiple declarations in one line are not supported, so join with semicolons.
		return declarations.join( ';\n' + this.tab );

	}
```
</details>

##### `emitFunction(node: any): string`

<details><summary>Code</summary>

```ts
emitFunction( node ) {

		const name = node.name;
		const returnType = this.getWgslType( node.type );

		const params = [];
		// We will prepend to a copy of the body, not the original AST node.
		const body = [ ...node.body ];

		for ( const param of node.params ) {

			const paramName = param.name;
			let paramType = this.getWgslType( param.type );

			// Handle 'inout' and 'out' qualifiers using pointers. They are already mutable.
			if ( param.qualifier === 'inout' || param.qualifier === 'out' ) {

				paramType = `ptr<function, ${paramType}>`;
				params.push( `${paramName}: ${paramType}` );
				continue;

			}

			// If the parameter is reassigned within the function, we need to
			// create a local, mutable variable that shadows the parameter's name.
			if ( param.linker && param.linker.assignments.length > 0 ) {

				// 1. Rename the incoming parameter to avoid name collision.
				const immutableParamName = `${paramName}_in`;
				params.push( `${immutableParamName}: ${paramType}` );

				// 2. Create a new Accessor node for the renamed immutable parameter.
				const immutableAccessor = new Accessor( immutableParamName );
				immutableAccessor.isAccessor = true;
				immutableAccessor.property = immutableParamName;

				// 3. Create a new VariableDeclaration node for the mutable local variable.
				// This new variable will have the original parameter's name.
				const mutableVar = new VariableDeclaration( param.type, param.name, immutableAccessor );

				// 4. Mark this new variable as mutable so `emitVariables` uses `var`.
				mutableVar.linker = { assignments: [ true ] };

				// 5. Prepend this new declaration to the function's body.
				body.unshift( mutableVar );

			} else {

				// This parameter is not reassigned, so treat it as a normal immutable parameter.
				params.push( `${paramName}: ${paramType}` );

			}

		}

		const paramsStr = params.length > 0 ? ' ' + params.join( ', ' ) + ' ' : '';
		const returnStr = ( returnType && returnType !== 'void' ) ? ` -> ${returnType}` : '';

		// Emit the function body, which now includes our injected variable declarations.
		const bodyStr = this.emitBody( body );

		return `fn ${name}(${paramsStr})${returnStr} {\n\n${bodyStr}\n\n${this.tab}}`;

	}
```
</details>

##### `emitComment(statement: any, body: any): string`

<details><summary>Code</summary>

```ts
emitComment( statement, body ) {

		const index = body.indexOf( statement );
		const previous = body[ index - 1 ];
		const next = body[ index + 1 ];

		let output = '';

		if ( previous && isExpression( previous ) ) {

			output += '\n';

		}

		output += this.tab + statement.comment.replace( /\n/g, '\n' + this.tab ) + '\n';

		if ( next && isExpression( next ) ) {

			output += '\n';

		}

		return output;

	}
```
</details>

##### `emitExtraLine(statement: any, body: any): "" | "\n"`

<details><summary>Code</summary>

```ts
emitExtraLine( statement, body ) {

		const index = body.indexOf( statement );
		const previous = body[ index - 1 ];

		if ( previous === undefined ) return '';

		if ( statement.isReturn ) return '\n';

		const lastExp = isExpression( previous );
		const currExp = isExpression( statement );

		if ( lastExp !== currExp || ( ! lastExp && ! currExp ) ) return '\n';

		return '';

	}
```
</details>

##### `emit(ast: any): string`

<details><summary>Code</summary>

```ts
emit( ast ) {

		const header = '// Three.js Transpiler r' + REVISION + '\n\n';

		let globals = '';
		let functions = '';
		let dependencies = '';

		// 1. Pre-process to find all global declarations
		for ( const statement of ast.body ) {

			if ( statement.isFunctionDeclaration ) {

				this.functions.set( statement.name, statement );

			} else if ( statement.isUniform ) {

				this.uniforms.push( statement );

			} else if ( statement.isVarying ) {

				this.varyings.push( statement );

			}

		}

		// 2. Build resource bindings (uniforms, textures, samplers)
		if ( this.uniforms.length > 0 ) {

			let bindingIndex = 0;
			const uniformStructMembers = [];
			const textureGlobals = [];

			for ( const uniform of this.uniforms ) {

				// Textures are declared as separate global variables, not in the UBO
				if ( uniform.type.includes( 'texture' ) ) {

					textureGlobals.push( `@group(${this.groupIndex}) @binding(${bindingIndex ++}) var ${uniform.name}: ${this.getWgslType( uniform.type )};` );
					textureGlobals.push( `@group(${this.groupIndex}) @binding(${bindingIndex ++}) var ${uniform.name}_sampler: sampler;` );

				} else {

					uniformStructMembers.push( `\t${uniform.name}: ${this.getWgslType( uniform.type )},` );

				}

			}

			// Create a UBO struct if there are any non-texture uniforms
			if ( uniformStructMembers.length > 0 ) {

				globals += 'struct Uniforms {\n';
				globals += uniformStructMembers.join( '\n' );
				globals += '\n};\n';
				globals += `@group(${this.groupIndex}) @binding(${bindingIndex ++}) var<uniform> uniforms: Uniforms;\n\n`;

			}

			// Add the texture and sampler globals
			globals += textureGlobals.join( '\n' ) + '\n\n';

		}

		// 3. Build varying structs for stage I/O
		// This is a simplification; a full implementation would need to know the shader stage.
		if ( this.varyings.length > 0 ) {

			globals += 'struct Varyings {\n';
			let location = 0;
			for ( const varying of this.varyings ) {

				globals += `\t@location(${location ++}) ${varying.name}: ${this.getWgslType( varying.type )},\n`;

			}

			globals += '};\n\n';

		}

		// 4. Emit all functions and other global statements
		for ( const statement of ast.body ) {

			functions += this.emitExtraLine( statement, ast.body );

			if ( statement.isFunctionDeclaration ) {

				functions += this.emitFunction( statement ) + '\n';

			} else if ( statement.isComment ) {

				functions += this.emitComment( statement, ast.body );

			} else if ( ! statement.isUniform && ! statement.isVarying ) {

				// Handle other top-level statements like 'const'
				functions += this.emitExpression( statement ) + ';\n';

			}

		}

		// 4. Build dependencies
		for ( const value of this.polyfills.values() ) {

			dependencies = `${ value }\n\n`;

		}

		return header + dependencies + globals + functions.trimEnd() + '\n';

	}
```
</details>


---