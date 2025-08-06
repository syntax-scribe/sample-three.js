[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TSLEncoder.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 18 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 49 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/transpiler/TSLEncoder.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `REVISION` | `three/webgpu` |
| `VariableDeclaration` | `./AST.js` |
| `Accessor` | `./AST.js` |
| `isExpression` | `./TranspilerUtils.js` |
| `isPrimitive` | `./TranspilerUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `opLib` | `{ '=': string; '+': string; '-': stri...` | let/var | `{ '=': 'assign', '+': 'add', '-': 'sub', '*': 'mul', '/': 'div', '%': 'remain...` | ✗ |
| `unaryLib` | `{ '+': string; '-': string; '~': stri...` | let/var | `{ '+': '', // positive '-': 'negate', '~': 'bitNot', '!': 'not', '++': 'incre...` | ✗ |
| `textureLookupFunctions` | `string[]` | let/var | `[ 'texture', 'texture2D', 'texture3D', 'textureCube', 'textureLod', 'texelFet...` | ✗ |
| `code` | `string` | let/var | ``const ${ node.name } = `` | ✗ |
| `code` | `any` | let/var | `*not shown*` | ✗ |
| `opFn` | `any` | let/var | `opLib[ node.type ] \|\| node.type` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `paramsStr` | `string` | let/var | `params.length > 0 ? ' ' + params.join( ', ' ) + ' ' : ''` | ✗ |
| `type` | `any` | let/var | `unaryLib[ node.type ]` | ✗ |
| `code` | `string` | let/var | `''` | ✗ |
| `ifStr` | `any` | let/var | ``If( ${ condStr }, () => { ${ bodyStr } ${ this.tab }} )`` | ✗ |
| `current` | `any` | let/var | `node` | ✗ |
| `name` | `any` | let/var | `node.initialization.name` | ✗ |
| `type` | `any` | let/var | `node.initialization.type` | ✗ |
| `condition` | `any` | let/var | `node.condition.type` | ✗ |
| `nameParam` | `string` | let/var | `name !== 'i' ? `, name: '${ name }'` : ''` | ✗ |
| `typeParam` | `string` | let/var | `type !== 'int' ? `, type: '${ type }'` : ''` | ✗ |
| `conditionParam` | `string` | let/var | `condition !== '<' ? `, condition: '${ condition }'` : ''` | ✗ |
| `updateParam` | `string` | let/var | `''` | ✗ |
| `loopStr` | `any` | let/var | ``Loop( { start: ${ start }, end: ${ end + nameParam + typeParam + conditionPa...` | ✗ |
| `switchString` | `any` | let/var | ``Switch( ${ discriminantString } )\n${ this.tab }`` | ✗ |
| `previousBlock` | `any` | let/var | `this.block` | ✗ |
| `caseBodyString` | `any` | let/var | `*not shown*` | ✗ |
| `caseConditions` | `any[]` | let/var | `[ ]` | ✗ |
| `forStr` | `any` | let/var | `'{\n\n' + this.tab + initialization + ';\n\n'` | ✗ |
| `whileStr` | `any` | let/var | ``Loop( ${ condition }, () => {\n\n`` | ✗ |
| `varStr` | `string` | let/var | `isRoot ? 'const ' : ''` | ✗ |
| `prefix` | `"" \| "export "` | let/var | `this.iife === false ? 'export ' : ''` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `inputs` | `any[]` | let/var | `[]` | ✗ |
| `mutableParams` | `any[]` | let/var | `[]` | ✗ |
| `hasPointer` | `boolean` | let/var | `false` | ✗ |
| `name` | `any` | let/var | `param.name` | ✗ |
| `mutableParam` | `VariableDeclaration` | let/var | `new VariableDeclaration( param.type, param.name, new Accessor( param.name + '...` | ✗ |
| `paramsStr` | `string` | let/var | `params.length > 0 ? ' [ ' + params.join( ', ' ) + ' ] ' : ''` | ✗ |
| `fnName` | `any` | let/var | `name` | ✗ |
| `overloadingNodes` | `any` | let/var | `null` | ✗ |
| `prefix` | `"" \| "export "` | let/var | `this.iife === false ? 'export ' : ''` | ✗ |
| `funcStr` | `string` | let/var | ``${ prefix }const ${ fnName } = /*@__PURE__*/ Fn( (${ paramsStr }) => { ${ bo...` | ✗ |
| `previous` | `any` | let/var | `body[ index - 1 ]` | ✗ |
| `next` | `any` | let/var | `body[ index + 1 ]` | ✗ |
| `output` | `string` | let/var | `''` | ✗ |
| `previous` | `any` | let/var | `body[ index - 1 ]` | ✗ |
| `code` | `string` | let/var | `'\n'` | ✗ |
| `overloadings` | `Map<any, any>` | let/var | `this.overloadings` | ✗ |
| `imports` | `any[]` | let/var | `[ ...this.imports ]` | ✗ |
| `exports` | `any[]` | let/var | `[ ...this.global ]` | ✗ |
| `header` | `string` | let/var | `'// Three.js Transpiler r' + REVISION + '\n\n'` | ✗ |
| `footer` | `string` | let/var | `''` | ✗ |


---

## Functions

### `TSLEncoder.addImport(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

**Calls:**

- `name.split`
- `this.global.has`
- `this.imports.add`

**Internal Comments:**
```
// import only if it's a node (x3)
```

<details><summary>Code</summary>

```typescript
addImport( name ) {

		// import only if it's a node

		name = name.split( '.' )[ 0 ];

		if ( TSL[ name ] !== undefined && this.global.has( name ) === false ) {

			this.imports.add( name );

		}

	}
```
</details>

### `TSLEncoder.emitUniform(node: any): string`

**Parameters:**

- **`node`** `any`

**Returns:** `string`

**Calls:**

- `this.global.add`
- `this.addImport`

**Internal Comments:**
```
//code += `reference( '${ node.name }', '${ node.type }', uniforms )`; (x3)
// legacy (x3)
// default uniform (x4)
```

<details><summary>Code</summary>

```typescript
emitUniform( node ) {

		let code = `const ${ node.name } = `;
		this.global.add( node.name );

		if ( this.reference === true ) {

			this.addImport( 'reference' );

			//code += `reference( '${ node.name }', '${ node.type }', uniforms )`;

			// legacy
			code += `reference( 'value', '${ node.type }', uniforms[ '${ node.name }' ] )`;

		} else {

			if ( node.type === 'texture' ) {

				this.addImport( 'texture' );

				code += 'texture( /* <THREE.Texture> */ )';

			} else if ( node.type === 'cubeTexture' ) {

				this.addImport( 'cubeTexture' );

				code += 'cubeTexture( /* <THREE.CubeTexture> */ )';

			} else if ( node.type === 'texture3D' ) {

				this.addImport( 'texture3D' );

				code += 'texture3D( /* <THREE.Data3DTexture> */ )';

			} else {

				// default uniform

				this.addImport( 'uniform' );

				code += `uniform( '${ node.type }' )`;

			}

		}

		return code;

	}
```
</details>

### `TSLEncoder.emitExpression(node: any, output: any): any`

**Parameters:**

- **`node`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.addImport`
- `this.emitExpression`
- `isPrimitive (from ./TranspilerUtils.js)`
- `params.push`
- `textureLookupFunctions.includes`
- `params.join`
- `this.emitFor`
- `this.emitWhile`
- `this.emitSwitch`
- `this.emitVariables`
- `this.emitUniform`
- `this.emitVarying`
- `this.emitTernary`
- `this.emitConditional`
- `console.warn`

**Internal Comments:**
```
// handle texture lookup function calls in separate branch
```

<details><summary>Code</summary>

```typescript
emitExpression( node, output = null ) {

		let code;

		if ( node.isAccessor ) {

			if ( node.linker.reference === null ) {

				this.addImport( node.property );

			}

			code = node.property;

		} else if ( node.isNumber ) {

			code = node.value;

		} else if ( node.isString ) {

			code = '\'' + node.value + '\'';

		} else if ( node.isOperator ) {

			const opFn = opLib[ node.type ] || node.type;

			const left = this.emitExpression( node.left, output );
			const right = this.emitExpression( node.right, output );

			if ( node.isNumericExpression ) {

				return left + ' ' + node.type + ' ' + right;

			}

			if ( isPrimitive( left ) ) {

				code = opFn + '( ' + left + ', ' + right + ' )';

				this.addImport( opFn );

			} else if ( opFn === '.' ) {

				code = left + opFn + right;

			} else {

				code = left + '.' + opFn + '( ' + right + ' )';

			}

		} else if ( node.isFunctionCall ) {

			const params = [];

			for ( const parameter of node.params ) {

				params.push( this.emitExpression( parameter ) );

			}

			// handle texture lookup function calls in separate branch

			if ( textureLookupFunctions.includes( node.name ) ) {

				code = `${ params[ 0 ] }.sample( ${ params[ 1 ] } )`;

				if ( node.name === 'texture' || node.name === 'texture2D' || node.name === 'texture3D' || node.name === 'textureCube' ) {

					if ( params.length === 3 ) {

						code += `.bias( ${ params[ 2 ] } )`;

					}

				} else if ( node.name === 'textureLod' ) {

					code += `.level( ${ params[ 2 ] } )`;

				} else if ( node.name === 'textureGrad' ) {

					code += `.grad( ${ params[ 2 ] }, ${ params[ 3 ] } )`;

				} else if ( node.name === 'texelFetch' ) {

					code += '.setSampler( false )';

				}

			} else {

				this.addImport( node.name );

				const paramsStr = params.length > 0 ? ' ' + params.join( ', ' ) + ' ' : '';

				code = `${ node.name }(${ paramsStr })`;

			}

		} else if ( node.isReturn ) {

			code = 'return';

			if ( node.value ) {

				code += ' ' + this.emitExpression( node.value );

			}

		} else if ( node.isDiscard ) {

			this.addImport( 'Discard' );

			code = 'Discard()';

		} else if ( node.isBreak ) {

			this.addImport( 'Break' );

			code = 'Break()';

		} else if ( node.isContinue ) {

			this.addImport( 'Continue' );

			code = 'Continue()';

		} else if ( node.isAccessorElements ) {

			code = this.emitExpression( node.object );

			for ( const element of node.elements ) {

				if ( element.isStaticElement ) {

					code += '.' + this.emitExpression( element.value );

				} else if ( element.isDynamicElement ) {

					const value = this.emitExpression( element.value );

					if ( isPrimitive( value ) ) {

						code += `[ ${ value } ]`;

					} else {

						code += `.element( ${ value } )`;

					}

				}

			}

		} else if ( node.isDynamicElement ) {

			code = this.emitExpression( node.value );

		} else if ( node.isStaticElement ) {

			code = this.emitExpression( node.value );

		} else if ( node.isFor ) {

			code = this.emitFor( node );

		} else if ( node.isWhile ) {

			code = this.emitWhile( node );

		} else if ( node.isSwitch ) {

			code = this.emitSwitch( node );

		} else if ( node.isVariableDeclaration ) {

			code = this.emitVariables( node );

		} else if ( node.isUniform ) {

			code = this.emitUniform( node );

		} else if ( node.isVarying ) {

			code = this.emitVarying( node );

		} else if ( node.isTernary ) {

			code = this.emitTernary( node );

		} else if ( node.isConditional ) {

			code = this.emitConditional( node );

		} else if ( node.isUnary && node.expression.isNumber && node.type === '-' ) {

			code = '- ' + node.expression.value;

			if ( node.expression.type !== 'float' ) {

				code = node.expression.type + '( ' + code + ' )';

				this.addImport( node.expression.type );

			}

		} else if ( node.isUnary ) {

			let type = unaryLib[ node.type ];

			if ( node.hasAssignment ) {

				if ( node.after === false ) {

					type += 'Before';

				}

			}

			const exp = this.emitExpression( node.expression );

			if ( isPrimitive( exp ) ) {

				this.addImport( type );

				code = type + '( ' + exp + ' )';

			} else {

				code = exp + '.' + type + '()';

			}

		} else {

			console.warn( 'Unknown node type', node );

		}

		if ( ! code ) code = '/* unknown statement */';

		return code;

	}
```
</details>

### `TSLEncoder.emitBody(body: any): string`

**Parameters:**

- **`body`** `any`

**Returns:** `string`

**Calls:**

- `this.emitExtraLine`
- `this.emitComment`
- `this.emitExpression`
- `code.slice`
- `this.tab.slice`

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

			if ( this.block && this.block.isSwitchCase ) {

				if ( statement.isBreak ) continue; // skip break statements in switch cases

			}

			code += this.tab + this.emitExpression( statement );

			if ( code.slice( - 1 ) !== '}' ) code += ';';

			code += '\n';

		}

		code = code.slice( 0, - 1 ); // remove the last extra line

		this.tab = this.tab.slice( 0, - 1 );

		return code;


	}
```
</details>

### `TSLEncoder.emitTernary(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `this.addImport`

<details><summary>Code</summary>

```typescript
emitTernary( node ) {

		const condStr = this.emitExpression( node.cond );
		const leftStr = this.emitExpression( node.left );
		const rightStr = this.emitExpression( node.right );

		this.addImport( 'select' );

		return `select( ${ condStr }, ${ leftStr }, ${ rightStr } )`;

	}
```
</details>

### `TSLEncoder.emitConditional(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `this.emitBody`
- `this.imports.add`

<details><summary>Code</summary>

```typescript
emitConditional( node ) {

		const condStr = this.emitExpression( node.cond );
		const bodyStr = this.emitBody( node.body );

		let ifStr = `If( ${ condStr }, () => {

${ bodyStr }

${ this.tab }} )`;

		let current = node;

		while ( current.elseConditional ) {

			const elseBodyStr = this.emitBody( current.elseConditional.body );

			if ( current.elseConditional.cond ) {

				const elseCondStr = this.emitExpression( current.elseConditional.cond );

				ifStr += `.ElseIf( ${ elseCondStr }, () => {

${ elseBodyStr }

${ this.tab }} )`;

			} else {

				ifStr += `.Else( () => {

${ elseBodyStr }

${ this.tab }} )`;

			}

			current = current.elseConditional;


		}

		this.imports.add( 'If' );

		return ifStr;

	}
```
</details>

### `TSLEncoder.emitLoop(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `this.emitBody`
- `this.imports.add`

<details><summary>Code</summary>

```typescript
emitLoop( node ) {

		const start = this.emitExpression( node.initialization.value );
		const end = this.emitExpression( node.condition.right );

		const name = node.initialization.name;
		const type = node.initialization.type;
		const condition = node.condition.type;

		const nameParam = name !== 'i' ? `, name: '${ name }'` : '';
		const typeParam = type !== 'int' ? `, type: '${ type }'` : '';
		const conditionParam = condition !== '<' ? `, condition: '${ condition }'` : '';

		let updateParam = '';

		if ( node.afterthought.isUnary ) {

			if ( node.afterthought.type !== '++' ) {

				updateParam = `, update: '${ node.afterthought.type }'`;

			}

		} else if ( node.afterthought.isOperator ) {

			if ( node.afterthought.right.isAccessor || node.afterthought.right.isNumber ) {

				updateParam = `, update: ${ this.emitExpression( node.afterthought.right ) }`;

			} else {

				updateParam = `, update: ( { i } ) => ${ this.emitExpression( node.afterthought ) }`;

			}

		}

		let loopStr = `Loop( { start: ${ start }, end: ${ end + nameParam + typeParam + conditionParam + updateParam } }, ( { ${ name } } ) => {\n\n`;

		loopStr += this.emitBody( node.body ) + '\n\n';

		loopStr += this.tab + '} )';

		this.imports.add( 'Loop' );

		return loopStr;

	}
```
</details>

### `TSLEncoder.emitSwitch(switchNode: any): any`

**Parameters:**

- **`switchNode`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `caseConditions.push`
- `this.emitBody`
- `caseConditions.join`
- `this.tab.slice`
- `this.imports.add`

<details><summary>Code</summary>

```typescript
emitSwitch( switchNode ) {

		const discriminantString = this.emitExpression( switchNode.discriminant );

		this.tab += '\t';

		let switchString = `Switch( ${ discriminantString } )\n${ this.tab }`;

		const previousBlock = this.block;

		for ( const switchCase of switchNode.cases ) {

			this.block = switchCase;

			let caseBodyString;

			if ( ! switchCase.isDefault ) {

				const caseConditions = [ ];

				for ( const condition of switchCase.conditions ) {

					caseConditions.push( this.emitExpression( condition ) );

				}

				caseBodyString = this.emitBody( switchCase.body );

				switchString += `.Case( ${ caseConditions.join( ', ' ) }, `;

			} else {

				caseBodyString = this.emitBody( switchCase.body );

				switchString += '.Default( ';

			}

			switchString += `() => {

${ caseBodyString }

${ this.tab }} )`;

		}

		this.block = previousBlock;

		this.tab = this.tab.slice( 0, - 1 );

		this.imports.add( 'Switch' );

		return switchString;

	}
```
</details>

### `TSLEncoder.emitFor(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitLoop`
- `this.emitForWhile`

<details><summary>Code</summary>

```typescript
emitFor( node ) {

		const { initialization, condition, afterthought } = node;

		if ( ( initialization && initialization.isVariableDeclaration && initialization.next === null ) &&
			( condition && condition.left.isAccessor && condition.left.property === initialization.name ) &&
			( afterthought && (
				( afterthought.isUnary && ( initialization.name === afterthought.expression.property ) ) ||
				( afterthought.isOperator && ( initialization.name === afterthought.left.property ) )
			) )
		) {

			return this.emitLoop( node );

		}

		return this.emitForWhile( node );

	}
```
</details>

### `TSLEncoder.emitForWhile(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `this.emitBody`
- `this.tab.slice`
- `this.imports.add`

<details><summary>Code</summary>

```typescript
emitForWhile( node ) {

		const initialization = this.emitExpression( node.initialization );
		const condition = this.emitExpression( node.condition );
		const afterthought = this.emitExpression( node.afterthought );

		this.tab += '\t';

		let forStr = '{\n\n' + this.tab + initialization + ';\n\n';
		forStr += `${ this.tab }Loop( ${ condition }, () => {\n\n`;

		forStr += this.emitBody( node.body ) + '\n\n';

		forStr += this.tab + '\t' + afterthought + ';\n\n';

		forStr += this.tab + '} )\n\n';

		this.tab = this.tab.slice( 0, - 1 );

		forStr += this.tab + '}';

		this.imports.add( 'Loop' );

		return forStr;

	}
```
</details>

### `TSLEncoder.emitWhile(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `this.emitExpression`
- `this.emitBody`
- `this.imports.add`

<details><summary>Code</summary>

```typescript
emitWhile( node ) {

		const condition = this.emitExpression( node.condition );

		let whileStr = `Loop( ${ condition }, () => {\n\n`;

		whileStr += this.emitBody( node.body ) + '\n\n';

		whileStr += this.tab + '} )';

		this.imports.add( 'Loop' );

		return whileStr;

	}
```
</details>

### `TSLEncoder.emitVariables(node: any, isRoot: boolean): string`

**Parameters:**

- **`node`** `any`
- **`isRoot`** `boolean`

**Returns:** `string`

**Calls:**

- `this.emitExpression`
- `this.addImport`
- `this.emitVariables`

**Internal Comments:**
```
// convert JS primitive to node (x3)
```

<details><summary>Code</summary>

```typescript
emitVariables( node, isRoot = true ) {

		const { name, type, value, next } = node;

		let varStr = isRoot ? 'const ' : '';
		varStr += name;

		if ( value ) {

			let valueStr = this.emitExpression( value );

			if ( value.isNumericExpression ) {

				// convert JS primitive to node

				valueStr = `${ type }( ${ valueStr } )`;

				this.addImport( type );

			}

			if ( node.linker.assignments.length > 0 ) {

				varStr += ' = ' + valueStr + '.toVar()';

			} else {

				varStr += ' = ' + valueStr;

			}

		} else {

			varStr += ` = property( '${ type }' )`;

			this.addImport( 'property' );

		}

		if ( next ) {

			varStr += ', ' + this.emitVariables( next, false );

		}

		return varStr;

	}
```
</details>

### `TSLEncoder.emitVarying(node: any): string`

**Parameters:**

- **`node`** `any`

**Returns:** `string`

**Calls:**

- `this.addImport`

<details><summary>Code</summary>

```typescript
emitVarying( node ) {

		const { name, type } = node;

		this.addImport( 'varying' );
		this.addImport( type );

		return `const ${ name } = varying( ${ type }(), '${ name }' )`;

	}
```
</details>

### `TSLEncoder.emitOverloadingFunction(nodes: any): string`

**Parameters:**

- **`nodes`** `any`

**Returns:** `string`

**Calls:**

- `this.addImport`
- `nodes.map( node => node.name + '_' + nodes.indexOf( node ) ).join`

<details><summary>Code</summary>

```typescript
emitOverloadingFunction( nodes ) {

		const { name } = nodes[ 0 ];

		this.addImport( 'overloadingFn' );

		const prefix = this.iife === false ? 'export ' : '';

		return `${ prefix }const ${ name } = /*@__PURE__*/ overloadingFn( [ ${ nodes.map( node => node.name + '_' + nodes.indexOf( node ) ).join( ', ' ) } ] );\n`;

	}
```
</details>

### `TSLEncoder.emitFunction(node: any): string`

**Parameters:**

- **`node`** `any`

**Returns:** `string`

**Calls:**

- `mutableParams.push`
- `inputs.push`
- `params.push`
- `mutableParam.linker.assignments.push`
- `node.body.unshift`
- `params.join`
- `this.emitBody`
- `this.overloadings.has`
- `this.overloadings.get`
- `overloadings.indexOf`
- `inputs.join`
- `this.imports.add`
- `this.global.add`
- `this.emitOverloadingFunction`

<details><summary>Code</summary>

```typescript
emitFunction( node ) {

		const { name, type } = node;

		const params = [];
		const inputs = [];
		const mutableParams = [];

		let hasPointer = false;

		for ( const param of node.params ) {

			let name = param.name;

			if ( param.linker.assignments.length > 0 ) {

				name = name + '_immutable';

				mutableParams.push( param );

			}

			if ( param.qualifier ) {

				if ( param.qualifier === 'inout' || param.qualifier === 'out' ) {

					hasPointer = true;

				}

			}

			inputs.push( param.name + ': \'' + param.type + '\'' );
			params.push( name );

		}

		for ( const param of mutableParams ) {

			const mutableParam = new VariableDeclaration( param.type, param.name, new Accessor( param.name + '_immutable' ), null, true );
			mutableParam.parent = param.parent; // link to the original node
			mutableParam.linker.assignments.push( mutableParam );

			node.body.unshift( mutableParam );

		}

		const paramsStr = params.length > 0 ? ' [ ' + params.join( ', ' ) + ' ] ' : '';
		const bodyStr = this.emitBody( node.body );

		let fnName = name;
		let overloadingNodes = null;

		if ( this.overloadings.has( name ) ) {

			const overloadings = this.overloadings.get( name );

			if ( overloadings.length > 1 ) {

				const index = overloadings.indexOf( node );

				fnName += '_' + index;

				if ( index === overloadings.length - 1 ) {

					overloadingNodes = overloadings;

				}

			}

		}

		const prefix = this.iife === false ? 'export ' : '';

		let funcStr = `${ prefix }const ${ fnName } = /*@__PURE__*/ Fn( (${ paramsStr }) => {

${ bodyStr }

${ this.tab }}`;

		if ( node.layout !== false && hasPointer === false ) {

			funcStr += ', { ' + inputs.join( ', ' ) + ', return: \'' + type + '\' }';

		}

		funcStr += ' );\n';

		this.imports.add( 'Fn' );

		this.global.add( node.name );

		if ( overloadingNodes !== null ) {

			funcStr += '\n' + this.emitOverloadingFunction( overloadingNodes );

		}

		return funcStr;

	}
```
</details>

### `TSLEncoder.emitComment(statement: any, body: any): string`

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

### `TSLEncoder.emitExtraLine(statement: any, body: any): "" | "\n"`

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

### `TSLEncoder.emit(ast: any): string`

**Parameters:**

- **`ast`** `any`

**Returns:** `string`

**Calls:**

- `overloadings.has`
- `overloadings.set`
- `overloadings.get( statement.name ).push`
- `this.emitExtraLine`
- `this.emitComment`
- `this.emitFunction`
- `this.emitExpression`
- `imports.join`
- `exports.join`

<details><summary>Code</summary>

```typescript
emit( ast ) {

		let code = '\n';

		if ( this.iife ) this.tab += '\t';

		const overloadings = this.overloadings;

		for ( const statement of ast.body ) {

			if ( statement.isFunctionDeclaration ) {

				if ( overloadings.has( statement.name ) === false ) {

					overloadings.set( statement.name, [] );

				}

				overloadings.get( statement.name ).push( statement );

			}

		}

		for ( const statement of ast.body ) {

			code += this.emitExtraLine( statement, ast.body );

			if ( statement.isComment ) {

				code += this.emitComment( statement, ast.body );

				continue;

			}

			if ( statement.isFunctionDeclaration ) {

				code += this.tab + this.emitFunction( statement );

			} else {

				code += this.tab + this.emitExpression( statement ) + ';\n';

			}

		}

		const imports = [ ...this.imports ];
		const exports = [ ...this.global ];

		let header = '// Three.js Transpiler r' + REVISION + '\n\n';
		let footer = '';

		if ( this.iife ) {

			header += '( function ( TSL, uniforms ) {\n\n';

			header += imports.length > 0 ? '\tconst { ' + imports.join( ', ' ) + ' } = TSL;\n' : '';
			footer += exports.length > 0 ? '\treturn { ' + exports.join( ', ' ) + ' };\n' : '';

			footer += '\n} );';

		} else {

			header += imports.length > 0 ? 'import { ' + imports.join( ', ' ) + ' } from \'three/tsl\';\n' : '';

		}

		return header + code + footer;

	}
```
</details>


---

## Classes

### `TSLEncoder`

<details><summary>Class Code</summary>

```ts
class TSLEncoder {

	constructor() {

		this.tab = '';
		this.imports = new Set();
		this.global = new Set();
		this.overloadings = new Map();
		this.iife = false;
		this.reference = false;

		this.block = null;

	}

	addImport( name ) {

		// import only if it's a node

		name = name.split( '.' )[ 0 ];

		if ( TSL[ name ] !== undefined && this.global.has( name ) === false ) {

			this.imports.add( name );

		}

	}

	emitUniform( node ) {

		let code = `const ${ node.name } = `;
		this.global.add( node.name );

		if ( this.reference === true ) {

			this.addImport( 'reference' );

			//code += `reference( '${ node.name }', '${ node.type }', uniforms )`;

			// legacy
			code += `reference( 'value', '${ node.type }', uniforms[ '${ node.name }' ] )`;

		} else {

			if ( node.type === 'texture' ) {

				this.addImport( 'texture' );

				code += 'texture( /* <THREE.Texture> */ )';

			} else if ( node.type === 'cubeTexture' ) {

				this.addImport( 'cubeTexture' );

				code += 'cubeTexture( /* <THREE.CubeTexture> */ )';

			} else if ( node.type === 'texture3D' ) {

				this.addImport( 'texture3D' );

				code += 'texture3D( /* <THREE.Data3DTexture> */ )';

			} else {

				// default uniform

				this.addImport( 'uniform' );

				code += `uniform( '${ node.type }' )`;

			}

		}

		return code;

	}

	emitExpression( node, output = null ) {

		let code;

		if ( node.isAccessor ) {

			if ( node.linker.reference === null ) {

				this.addImport( node.property );

			}

			code = node.property;

		} else if ( node.isNumber ) {

			code = node.value;

		} else if ( node.isString ) {

			code = '\'' + node.value + '\'';

		} else if ( node.isOperator ) {

			const opFn = opLib[ node.type ] || node.type;

			const left = this.emitExpression( node.left, output );
			const right = this.emitExpression( node.right, output );

			if ( node.isNumericExpression ) {

				return left + ' ' + node.type + ' ' + right;

			}

			if ( isPrimitive( left ) ) {

				code = opFn + '( ' + left + ', ' + right + ' )';

				this.addImport( opFn );

			} else if ( opFn === '.' ) {

				code = left + opFn + right;

			} else {

				code = left + '.' + opFn + '( ' + right + ' )';

			}

		} else if ( node.isFunctionCall ) {

			const params = [];

			for ( const parameter of node.params ) {

				params.push( this.emitExpression( parameter ) );

			}

			// handle texture lookup function calls in separate branch

			if ( textureLookupFunctions.includes( node.name ) ) {

				code = `${ params[ 0 ] }.sample( ${ params[ 1 ] } )`;

				if ( node.name === 'texture' || node.name === 'texture2D' || node.name === 'texture3D' || node.name === 'textureCube' ) {

					if ( params.length === 3 ) {

						code += `.bias( ${ params[ 2 ] } )`;

					}

				} else if ( node.name === 'textureLod' ) {

					code += `.level( ${ params[ 2 ] } )`;

				} else if ( node.name === 'textureGrad' ) {

					code += `.grad( ${ params[ 2 ] }, ${ params[ 3 ] } )`;

				} else if ( node.name === 'texelFetch' ) {

					code += '.setSampler( false )';

				}

			} else {

				this.addImport( node.name );

				const paramsStr = params.length > 0 ? ' ' + params.join( ', ' ) + ' ' : '';

				code = `${ node.name }(${ paramsStr })`;

			}

		} else if ( node.isReturn ) {

			code = 'return';

			if ( node.value ) {

				code += ' ' + this.emitExpression( node.value );

			}

		} else if ( node.isDiscard ) {

			this.addImport( 'Discard' );

			code = 'Discard()';

		} else if ( node.isBreak ) {

			this.addImport( 'Break' );

			code = 'Break()';

		} else if ( node.isContinue ) {

			this.addImport( 'Continue' );

			code = 'Continue()';

		} else if ( node.isAccessorElements ) {

			code = this.emitExpression( node.object );

			for ( const element of node.elements ) {

				if ( element.isStaticElement ) {

					code += '.' + this.emitExpression( element.value );

				} else if ( element.isDynamicElement ) {

					const value = this.emitExpression( element.value );

					if ( isPrimitive( value ) ) {

						code += `[ ${ value } ]`;

					} else {

						code += `.element( ${ value } )`;

					}

				}

			}

		} else if ( node.isDynamicElement ) {

			code = this.emitExpression( node.value );

		} else if ( node.isStaticElement ) {

			code = this.emitExpression( node.value );

		} else if ( node.isFor ) {

			code = this.emitFor( node );

		} else if ( node.isWhile ) {

			code = this.emitWhile( node );

		} else if ( node.isSwitch ) {

			code = this.emitSwitch( node );

		} else if ( node.isVariableDeclaration ) {

			code = this.emitVariables( node );

		} else if ( node.isUniform ) {

			code = this.emitUniform( node );

		} else if ( node.isVarying ) {

			code = this.emitVarying( node );

		} else if ( node.isTernary ) {

			code = this.emitTernary( node );

		} else if ( node.isConditional ) {

			code = this.emitConditional( node );

		} else if ( node.isUnary && node.expression.isNumber && node.type === '-' ) {

			code = '- ' + node.expression.value;

			if ( node.expression.type !== 'float' ) {

				code = node.expression.type + '( ' + code + ' )';

				this.addImport( node.expression.type );

			}

		} else if ( node.isUnary ) {

			let type = unaryLib[ node.type ];

			if ( node.hasAssignment ) {

				if ( node.after === false ) {

					type += 'Before';

				}

			}

			const exp = this.emitExpression( node.expression );

			if ( isPrimitive( exp ) ) {

				this.addImport( type );

				code = type + '( ' + exp + ' )';

			} else {

				code = exp + '.' + type + '()';

			}

		} else {

			console.warn( 'Unknown node type', node );

		}

		if ( ! code ) code = '/* unknown statement */';

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

			if ( this.block && this.block.isSwitchCase ) {

				if ( statement.isBreak ) continue; // skip break statements in switch cases

			}

			code += this.tab + this.emitExpression( statement );

			if ( code.slice( - 1 ) !== '}' ) code += ';';

			code += '\n';

		}

		code = code.slice( 0, - 1 ); // remove the last extra line

		this.tab = this.tab.slice( 0, - 1 );

		return code;


	}

	emitTernary( node ) {

		const condStr = this.emitExpression( node.cond );
		const leftStr = this.emitExpression( node.left );
		const rightStr = this.emitExpression( node.right );

		this.addImport( 'select' );

		return `select( ${ condStr }, ${ leftStr }, ${ rightStr } )`;

	}

	emitConditional( node ) {

		const condStr = this.emitExpression( node.cond );
		const bodyStr = this.emitBody( node.body );

		let ifStr = `If( ${ condStr }, () => {

${ bodyStr }

${ this.tab }} )`;

		let current = node;

		while ( current.elseConditional ) {

			const elseBodyStr = this.emitBody( current.elseConditional.body );

			if ( current.elseConditional.cond ) {

				const elseCondStr = this.emitExpression( current.elseConditional.cond );

				ifStr += `.ElseIf( ${ elseCondStr }, () => {

${ elseBodyStr }

${ this.tab }} )`;

			} else {

				ifStr += `.Else( () => {

${ elseBodyStr }

${ this.tab }} )`;

			}

			current = current.elseConditional;


		}

		this.imports.add( 'If' );

		return ifStr;

	}

	emitLoop( node ) {

		const start = this.emitExpression( node.initialization.value );
		const end = this.emitExpression( node.condition.right );

		const name = node.initialization.name;
		const type = node.initialization.type;
		const condition = node.condition.type;

		const nameParam = name !== 'i' ? `, name: '${ name }'` : '';
		const typeParam = type !== 'int' ? `, type: '${ type }'` : '';
		const conditionParam = condition !== '<' ? `, condition: '${ condition }'` : '';

		let updateParam = '';

		if ( node.afterthought.isUnary ) {

			if ( node.afterthought.type !== '++' ) {

				updateParam = `, update: '${ node.afterthought.type }'`;

			}

		} else if ( node.afterthought.isOperator ) {

			if ( node.afterthought.right.isAccessor || node.afterthought.right.isNumber ) {

				updateParam = `, update: ${ this.emitExpression( node.afterthought.right ) }`;

			} else {

				updateParam = `, update: ( { i } ) => ${ this.emitExpression( node.afterthought ) }`;

			}

		}

		let loopStr = `Loop( { start: ${ start }, end: ${ end + nameParam + typeParam + conditionParam + updateParam } }, ( { ${ name } } ) => {\n\n`;

		loopStr += this.emitBody( node.body ) + '\n\n';

		loopStr += this.tab + '} )';

		this.imports.add( 'Loop' );

		return loopStr;

	}


	emitSwitch( switchNode ) {

		const discriminantString = this.emitExpression( switchNode.discriminant );

		this.tab += '\t';

		let switchString = `Switch( ${ discriminantString } )\n${ this.tab }`;

		const previousBlock = this.block;

		for ( const switchCase of switchNode.cases ) {

			this.block = switchCase;

			let caseBodyString;

			if ( ! switchCase.isDefault ) {

				const caseConditions = [ ];

				for ( const condition of switchCase.conditions ) {

					caseConditions.push( this.emitExpression( condition ) );

				}

				caseBodyString = this.emitBody( switchCase.body );

				switchString += `.Case( ${ caseConditions.join( ', ' ) }, `;

			} else {

				caseBodyString = this.emitBody( switchCase.body );

				switchString += '.Default( ';

			}

			switchString += `() => {

${ caseBodyString }

${ this.tab }} )`;

		}

		this.block = previousBlock;

		this.tab = this.tab.slice( 0, - 1 );

		this.imports.add( 'Switch' );

		return switchString;

	}

	emitFor( node ) {

		const { initialization, condition, afterthought } = node;

		if ( ( initialization && initialization.isVariableDeclaration && initialization.next === null ) &&
			( condition && condition.left.isAccessor && condition.left.property === initialization.name ) &&
			( afterthought && (
				( afterthought.isUnary && ( initialization.name === afterthought.expression.property ) ) ||
				( afterthought.isOperator && ( initialization.name === afterthought.left.property ) )
			) )
		) {

			return this.emitLoop( node );

		}

		return this.emitForWhile( node );

	}

	emitForWhile( node ) {

		const initialization = this.emitExpression( node.initialization );
		const condition = this.emitExpression( node.condition );
		const afterthought = this.emitExpression( node.afterthought );

		this.tab += '\t';

		let forStr = '{\n\n' + this.tab + initialization + ';\n\n';
		forStr += `${ this.tab }Loop( ${ condition }, () => {\n\n`;

		forStr += this.emitBody( node.body ) + '\n\n';

		forStr += this.tab + '\t' + afterthought + ';\n\n';

		forStr += this.tab + '} )\n\n';

		this.tab = this.tab.slice( 0, - 1 );

		forStr += this.tab + '}';

		this.imports.add( 'Loop' );

		return forStr;

	}

	emitWhile( node ) {

		const condition = this.emitExpression( node.condition );

		let whileStr = `Loop( ${ condition }, () => {\n\n`;

		whileStr += this.emitBody( node.body ) + '\n\n';

		whileStr += this.tab + '} )';

		this.imports.add( 'Loop' );

		return whileStr;

	}

	emitVariables( node, isRoot = true ) {

		const { name, type, value, next } = node;

		let varStr = isRoot ? 'const ' : '';
		varStr += name;

		if ( value ) {

			let valueStr = this.emitExpression( value );

			if ( value.isNumericExpression ) {

				// convert JS primitive to node

				valueStr = `${ type }( ${ valueStr } )`;

				this.addImport( type );

			}

			if ( node.linker.assignments.length > 0 ) {

				varStr += ' = ' + valueStr + '.toVar()';

			} else {

				varStr += ' = ' + valueStr;

			}

		} else {

			varStr += ` = property( '${ type }' )`;

			this.addImport( 'property' );

		}

		if ( next ) {

			varStr += ', ' + this.emitVariables( next, false );

		}

		return varStr;

	}

	emitVarying( node ) {

		const { name, type } = node;

		this.addImport( 'varying' );
		this.addImport( type );

		return `const ${ name } = varying( ${ type }(), '${ name }' )`;

	}

	emitOverloadingFunction( nodes ) {

		const { name } = nodes[ 0 ];

		this.addImport( 'overloadingFn' );

		const prefix = this.iife === false ? 'export ' : '';

		return `${ prefix }const ${ name } = /*@__PURE__*/ overloadingFn( [ ${ nodes.map( node => node.name + '_' + nodes.indexOf( node ) ).join( ', ' ) } ] );\n`;

	}

	emitFunction( node ) {

		const { name, type } = node;

		const params = [];
		const inputs = [];
		const mutableParams = [];

		let hasPointer = false;

		for ( const param of node.params ) {

			let name = param.name;

			if ( param.linker.assignments.length > 0 ) {

				name = name + '_immutable';

				mutableParams.push( param );

			}

			if ( param.qualifier ) {

				if ( param.qualifier === 'inout' || param.qualifier === 'out' ) {

					hasPointer = true;

				}

			}

			inputs.push( param.name + ': \'' + param.type + '\'' );
			params.push( name );

		}

		for ( const param of mutableParams ) {

			const mutableParam = new VariableDeclaration( param.type, param.name, new Accessor( param.name + '_immutable' ), null, true );
			mutableParam.parent = param.parent; // link to the original node
			mutableParam.linker.assignments.push( mutableParam );

			node.body.unshift( mutableParam );

		}

		const paramsStr = params.length > 0 ? ' [ ' + params.join( ', ' ) + ' ] ' : '';
		const bodyStr = this.emitBody( node.body );

		let fnName = name;
		let overloadingNodes = null;

		if ( this.overloadings.has( name ) ) {

			const overloadings = this.overloadings.get( name );

			if ( overloadings.length > 1 ) {

				const index = overloadings.indexOf( node );

				fnName += '_' + index;

				if ( index === overloadings.length - 1 ) {

					overloadingNodes = overloadings;

				}

			}

		}

		const prefix = this.iife === false ? 'export ' : '';

		let funcStr = `${ prefix }const ${ fnName } = /*@__PURE__*/ Fn( (${ paramsStr }) => {

${ bodyStr }

${ this.tab }}`;

		if ( node.layout !== false && hasPointer === false ) {

			funcStr += ', { ' + inputs.join( ', ' ) + ', return: \'' + type + '\' }';

		}

		funcStr += ' );\n';

		this.imports.add( 'Fn' );

		this.global.add( node.name );

		if ( overloadingNodes !== null ) {

			funcStr += '\n' + this.emitOverloadingFunction( overloadingNodes );

		}

		return funcStr;

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

		let code = '\n';

		if ( this.iife ) this.tab += '\t';

		const overloadings = this.overloadings;

		for ( const statement of ast.body ) {

			if ( statement.isFunctionDeclaration ) {

				if ( overloadings.has( statement.name ) === false ) {

					overloadings.set( statement.name, [] );

				}

				overloadings.get( statement.name ).push( statement );

			}

		}

		for ( const statement of ast.body ) {

			code += this.emitExtraLine( statement, ast.body );

			if ( statement.isComment ) {

				code += this.emitComment( statement, ast.body );

				continue;

			}

			if ( statement.isFunctionDeclaration ) {

				code += this.tab + this.emitFunction( statement );

			} else {

				code += this.tab + this.emitExpression( statement ) + ';\n';

			}

		}

		const imports = [ ...this.imports ];
		const exports = [ ...this.global ];

		let header = '// Three.js Transpiler r' + REVISION + '\n\n';
		let footer = '';

		if ( this.iife ) {

			header += '( function ( TSL, uniforms ) {\n\n';

			header += imports.length > 0 ? '\tconst { ' + imports.join( ', ' ) + ' } = TSL;\n' : '';
			footer += exports.length > 0 ? '\treturn { ' + exports.join( ', ' ) + ' };\n' : '';

			footer += '\n} );';

		} else {

			header += imports.length > 0 ? 'import { ' + imports.join( ', ' ) + ' } from \'three/tsl\';\n' : '';

		}

		return header + code + footer;

	}

}
```
</details>

#### Methods

##### `addImport(name: any): void`

<details><summary>Code</summary>

```ts
addImport( name ) {

		// import only if it's a node

		name = name.split( '.' )[ 0 ];

		if ( TSL[ name ] !== undefined && this.global.has( name ) === false ) {

			this.imports.add( name );

		}

	}
```
</details>

##### `emitUniform(node: any): string`

<details><summary>Code</summary>

```ts
emitUniform( node ) {

		let code = `const ${ node.name } = `;
		this.global.add( node.name );

		if ( this.reference === true ) {

			this.addImport( 'reference' );

			//code += `reference( '${ node.name }', '${ node.type }', uniforms )`;

			// legacy
			code += `reference( 'value', '${ node.type }', uniforms[ '${ node.name }' ] )`;

		} else {

			if ( node.type === 'texture' ) {

				this.addImport( 'texture' );

				code += 'texture( /* <THREE.Texture> */ )';

			} else if ( node.type === 'cubeTexture' ) {

				this.addImport( 'cubeTexture' );

				code += 'cubeTexture( /* <THREE.CubeTexture> */ )';

			} else if ( node.type === 'texture3D' ) {

				this.addImport( 'texture3D' );

				code += 'texture3D( /* <THREE.Data3DTexture> */ )';

			} else {

				// default uniform

				this.addImport( 'uniform' );

				code += `uniform( '${ node.type }' )`;

			}

		}

		return code;

	}
```
</details>

##### `emitExpression(node: any, output: any): any`

<details><summary>Code</summary>

```ts
emitExpression( node, output = null ) {

		let code;

		if ( node.isAccessor ) {

			if ( node.linker.reference === null ) {

				this.addImport( node.property );

			}

			code = node.property;

		} else if ( node.isNumber ) {

			code = node.value;

		} else if ( node.isString ) {

			code = '\'' + node.value + '\'';

		} else if ( node.isOperator ) {

			const opFn = opLib[ node.type ] || node.type;

			const left = this.emitExpression( node.left, output );
			const right = this.emitExpression( node.right, output );

			if ( node.isNumericExpression ) {

				return left + ' ' + node.type + ' ' + right;

			}

			if ( isPrimitive( left ) ) {

				code = opFn + '( ' + left + ', ' + right + ' )';

				this.addImport( opFn );

			} else if ( opFn === '.' ) {

				code = left + opFn + right;

			} else {

				code = left + '.' + opFn + '( ' + right + ' )';

			}

		} else if ( node.isFunctionCall ) {

			const params = [];

			for ( const parameter of node.params ) {

				params.push( this.emitExpression( parameter ) );

			}

			// handle texture lookup function calls in separate branch

			if ( textureLookupFunctions.includes( node.name ) ) {

				code = `${ params[ 0 ] }.sample( ${ params[ 1 ] } )`;

				if ( node.name === 'texture' || node.name === 'texture2D' || node.name === 'texture3D' || node.name === 'textureCube' ) {

					if ( params.length === 3 ) {

						code += `.bias( ${ params[ 2 ] } )`;

					}

				} else if ( node.name === 'textureLod' ) {

					code += `.level( ${ params[ 2 ] } )`;

				} else if ( node.name === 'textureGrad' ) {

					code += `.grad( ${ params[ 2 ] }, ${ params[ 3 ] } )`;

				} else if ( node.name === 'texelFetch' ) {

					code += '.setSampler( false )';

				}

			} else {

				this.addImport( node.name );

				const paramsStr = params.length > 0 ? ' ' + params.join( ', ' ) + ' ' : '';

				code = `${ node.name }(${ paramsStr })`;

			}

		} else if ( node.isReturn ) {

			code = 'return';

			if ( node.value ) {

				code += ' ' + this.emitExpression( node.value );

			}

		} else if ( node.isDiscard ) {

			this.addImport( 'Discard' );

			code = 'Discard()';

		} else if ( node.isBreak ) {

			this.addImport( 'Break' );

			code = 'Break()';

		} else if ( node.isContinue ) {

			this.addImport( 'Continue' );

			code = 'Continue()';

		} else if ( node.isAccessorElements ) {

			code = this.emitExpression( node.object );

			for ( const element of node.elements ) {

				if ( element.isStaticElement ) {

					code += '.' + this.emitExpression( element.value );

				} else if ( element.isDynamicElement ) {

					const value = this.emitExpression( element.value );

					if ( isPrimitive( value ) ) {

						code += `[ ${ value } ]`;

					} else {

						code += `.element( ${ value } )`;

					}

				}

			}

		} else if ( node.isDynamicElement ) {

			code = this.emitExpression( node.value );

		} else if ( node.isStaticElement ) {

			code = this.emitExpression( node.value );

		} else if ( node.isFor ) {

			code = this.emitFor( node );

		} else if ( node.isWhile ) {

			code = this.emitWhile( node );

		} else if ( node.isSwitch ) {

			code = this.emitSwitch( node );

		} else if ( node.isVariableDeclaration ) {

			code = this.emitVariables( node );

		} else if ( node.isUniform ) {

			code = this.emitUniform( node );

		} else if ( node.isVarying ) {

			code = this.emitVarying( node );

		} else if ( node.isTernary ) {

			code = this.emitTernary( node );

		} else if ( node.isConditional ) {

			code = this.emitConditional( node );

		} else if ( node.isUnary && node.expression.isNumber && node.type === '-' ) {

			code = '- ' + node.expression.value;

			if ( node.expression.type !== 'float' ) {

				code = node.expression.type + '( ' + code + ' )';

				this.addImport( node.expression.type );

			}

		} else if ( node.isUnary ) {

			let type = unaryLib[ node.type ];

			if ( node.hasAssignment ) {

				if ( node.after === false ) {

					type += 'Before';

				}

			}

			const exp = this.emitExpression( node.expression );

			if ( isPrimitive( exp ) ) {

				this.addImport( type );

				code = type + '( ' + exp + ' )';

			} else {

				code = exp + '.' + type + '()';

			}

		} else {

			console.warn( 'Unknown node type', node );

		}

		if ( ! code ) code = '/* unknown statement */';

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

			if ( this.block && this.block.isSwitchCase ) {

				if ( statement.isBreak ) continue; // skip break statements in switch cases

			}

			code += this.tab + this.emitExpression( statement );

			if ( code.slice( - 1 ) !== '}' ) code += ';';

			code += '\n';

		}

		code = code.slice( 0, - 1 ); // remove the last extra line

		this.tab = this.tab.slice( 0, - 1 );

		return code;


	}
```
</details>

##### `emitTernary(node: any): any`

<details><summary>Code</summary>

```ts
emitTernary( node ) {

		const condStr = this.emitExpression( node.cond );
		const leftStr = this.emitExpression( node.left );
		const rightStr = this.emitExpression( node.right );

		this.addImport( 'select' );

		return `select( ${ condStr }, ${ leftStr }, ${ rightStr } )`;

	}
```
</details>

##### `emitConditional(node: any): any`

<details><summary>Code</summary>

```ts
emitConditional( node ) {

		const condStr = this.emitExpression( node.cond );
		const bodyStr = this.emitBody( node.body );

		let ifStr = `If( ${ condStr }, () => {

${ bodyStr }

${ this.tab }} )`;

		let current = node;

		while ( current.elseConditional ) {

			const elseBodyStr = this.emitBody( current.elseConditional.body );

			if ( current.elseConditional.cond ) {

				const elseCondStr = this.emitExpression( current.elseConditional.cond );

				ifStr += `.ElseIf( ${ elseCondStr }, () => {

${ elseBodyStr }

${ this.tab }} )`;

			} else {

				ifStr += `.Else( () => {

${ elseBodyStr }

${ this.tab }} )`;

			}

			current = current.elseConditional;


		}

		this.imports.add( 'If' );

		return ifStr;

	}
```
</details>

##### `emitLoop(node: any): any`

<details><summary>Code</summary>

```ts
emitLoop( node ) {

		const start = this.emitExpression( node.initialization.value );
		const end = this.emitExpression( node.condition.right );

		const name = node.initialization.name;
		const type = node.initialization.type;
		const condition = node.condition.type;

		const nameParam = name !== 'i' ? `, name: '${ name }'` : '';
		const typeParam = type !== 'int' ? `, type: '${ type }'` : '';
		const conditionParam = condition !== '<' ? `, condition: '${ condition }'` : '';

		let updateParam = '';

		if ( node.afterthought.isUnary ) {

			if ( node.afterthought.type !== '++' ) {

				updateParam = `, update: '${ node.afterthought.type }'`;

			}

		} else if ( node.afterthought.isOperator ) {

			if ( node.afterthought.right.isAccessor || node.afterthought.right.isNumber ) {

				updateParam = `, update: ${ this.emitExpression( node.afterthought.right ) }`;

			} else {

				updateParam = `, update: ( { i } ) => ${ this.emitExpression( node.afterthought ) }`;

			}

		}

		let loopStr = `Loop( { start: ${ start }, end: ${ end + nameParam + typeParam + conditionParam + updateParam } }, ( { ${ name } } ) => {\n\n`;

		loopStr += this.emitBody( node.body ) + '\n\n';

		loopStr += this.tab + '} )';

		this.imports.add( 'Loop' );

		return loopStr;

	}
```
</details>

##### `emitSwitch(switchNode: any): any`

<details><summary>Code</summary>

```ts
emitSwitch( switchNode ) {

		const discriminantString = this.emitExpression( switchNode.discriminant );

		this.tab += '\t';

		let switchString = `Switch( ${ discriminantString } )\n${ this.tab }`;

		const previousBlock = this.block;

		for ( const switchCase of switchNode.cases ) {

			this.block = switchCase;

			let caseBodyString;

			if ( ! switchCase.isDefault ) {

				const caseConditions = [ ];

				for ( const condition of switchCase.conditions ) {

					caseConditions.push( this.emitExpression( condition ) );

				}

				caseBodyString = this.emitBody( switchCase.body );

				switchString += `.Case( ${ caseConditions.join( ', ' ) }, `;

			} else {

				caseBodyString = this.emitBody( switchCase.body );

				switchString += '.Default( ';

			}

			switchString += `() => {

${ caseBodyString }

${ this.tab }} )`;

		}

		this.block = previousBlock;

		this.tab = this.tab.slice( 0, - 1 );

		this.imports.add( 'Switch' );

		return switchString;

	}
```
</details>

##### `emitFor(node: any): any`

<details><summary>Code</summary>

```ts
emitFor( node ) {

		const { initialization, condition, afterthought } = node;

		if ( ( initialization && initialization.isVariableDeclaration && initialization.next === null ) &&
			( condition && condition.left.isAccessor && condition.left.property === initialization.name ) &&
			( afterthought && (
				( afterthought.isUnary && ( initialization.name === afterthought.expression.property ) ) ||
				( afterthought.isOperator && ( initialization.name === afterthought.left.property ) )
			) )
		) {

			return this.emitLoop( node );

		}

		return this.emitForWhile( node );

	}
```
</details>

##### `emitForWhile(node: any): any`

<details><summary>Code</summary>

```ts
emitForWhile( node ) {

		const initialization = this.emitExpression( node.initialization );
		const condition = this.emitExpression( node.condition );
		const afterthought = this.emitExpression( node.afterthought );

		this.tab += '\t';

		let forStr = '{\n\n' + this.tab + initialization + ';\n\n';
		forStr += `${ this.tab }Loop( ${ condition }, () => {\n\n`;

		forStr += this.emitBody( node.body ) + '\n\n';

		forStr += this.tab + '\t' + afterthought + ';\n\n';

		forStr += this.tab + '} )\n\n';

		this.tab = this.tab.slice( 0, - 1 );

		forStr += this.tab + '}';

		this.imports.add( 'Loop' );

		return forStr;

	}
```
</details>

##### `emitWhile(node: any): any`

<details><summary>Code</summary>

```ts
emitWhile( node ) {

		const condition = this.emitExpression( node.condition );

		let whileStr = `Loop( ${ condition }, () => {\n\n`;

		whileStr += this.emitBody( node.body ) + '\n\n';

		whileStr += this.tab + '} )';

		this.imports.add( 'Loop' );

		return whileStr;

	}
```
</details>

##### `emitVariables(node: any, isRoot: boolean): string`

<details><summary>Code</summary>

```ts
emitVariables( node, isRoot = true ) {

		const { name, type, value, next } = node;

		let varStr = isRoot ? 'const ' : '';
		varStr += name;

		if ( value ) {

			let valueStr = this.emitExpression( value );

			if ( value.isNumericExpression ) {

				// convert JS primitive to node

				valueStr = `${ type }( ${ valueStr } )`;

				this.addImport( type );

			}

			if ( node.linker.assignments.length > 0 ) {

				varStr += ' = ' + valueStr + '.toVar()';

			} else {

				varStr += ' = ' + valueStr;

			}

		} else {

			varStr += ` = property( '${ type }' )`;

			this.addImport( 'property' );

		}

		if ( next ) {

			varStr += ', ' + this.emitVariables( next, false );

		}

		return varStr;

	}
```
</details>

##### `emitVarying(node: any): string`

<details><summary>Code</summary>

```ts
emitVarying( node ) {

		const { name, type } = node;

		this.addImport( 'varying' );
		this.addImport( type );

		return `const ${ name } = varying( ${ type }(), '${ name }' )`;

	}
```
</details>

##### `emitOverloadingFunction(nodes: any): string`

<details><summary>Code</summary>

```ts
emitOverloadingFunction( nodes ) {

		const { name } = nodes[ 0 ];

		this.addImport( 'overloadingFn' );

		const prefix = this.iife === false ? 'export ' : '';

		return `${ prefix }const ${ name } = /*@__PURE__*/ overloadingFn( [ ${ nodes.map( node => node.name + '_' + nodes.indexOf( node ) ).join( ', ' ) } ] );\n`;

	}
```
</details>

##### `emitFunction(node: any): string`

<details><summary>Code</summary>

```ts
emitFunction( node ) {

		const { name, type } = node;

		const params = [];
		const inputs = [];
		const mutableParams = [];

		let hasPointer = false;

		for ( const param of node.params ) {

			let name = param.name;

			if ( param.linker.assignments.length > 0 ) {

				name = name + '_immutable';

				mutableParams.push( param );

			}

			if ( param.qualifier ) {

				if ( param.qualifier === 'inout' || param.qualifier === 'out' ) {

					hasPointer = true;

				}

			}

			inputs.push( param.name + ': \'' + param.type + '\'' );
			params.push( name );

		}

		for ( const param of mutableParams ) {

			const mutableParam = new VariableDeclaration( param.type, param.name, new Accessor( param.name + '_immutable' ), null, true );
			mutableParam.parent = param.parent; // link to the original node
			mutableParam.linker.assignments.push( mutableParam );

			node.body.unshift( mutableParam );

		}

		const paramsStr = params.length > 0 ? ' [ ' + params.join( ', ' ) + ' ] ' : '';
		const bodyStr = this.emitBody( node.body );

		let fnName = name;
		let overloadingNodes = null;

		if ( this.overloadings.has( name ) ) {

			const overloadings = this.overloadings.get( name );

			if ( overloadings.length > 1 ) {

				const index = overloadings.indexOf( node );

				fnName += '_' + index;

				if ( index === overloadings.length - 1 ) {

					overloadingNodes = overloadings;

				}

			}

		}

		const prefix = this.iife === false ? 'export ' : '';

		let funcStr = `${ prefix }const ${ fnName } = /*@__PURE__*/ Fn( (${ paramsStr }) => {

${ bodyStr }

${ this.tab }}`;

		if ( node.layout !== false && hasPointer === false ) {

			funcStr += ', { ' + inputs.join( ', ' ) + ', return: \'' + type + '\' }';

		}

		funcStr += ' );\n';

		this.imports.add( 'Fn' );

		this.global.add( node.name );

		if ( overloadingNodes !== null ) {

			funcStr += '\n' + this.emitOverloadingFunction( overloadingNodes );

		}

		return funcStr;

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

		let code = '\n';

		if ( this.iife ) this.tab += '\t';

		const overloadings = this.overloadings;

		for ( const statement of ast.body ) {

			if ( statement.isFunctionDeclaration ) {

				if ( overloadings.has( statement.name ) === false ) {

					overloadings.set( statement.name, [] );

				}

				overloadings.get( statement.name ).push( statement );

			}

		}

		for ( const statement of ast.body ) {

			code += this.emitExtraLine( statement, ast.body );

			if ( statement.isComment ) {

				code += this.emitComment( statement, ast.body );

				continue;

			}

			if ( statement.isFunctionDeclaration ) {

				code += this.tab + this.emitFunction( statement );

			} else {

				code += this.tab + this.emitExpression( statement ) + ';\n';

			}

		}

		const imports = [ ...this.imports ];
		const exports = [ ...this.global ];

		let header = '// Three.js Transpiler r' + REVISION + '\n\n';
		let footer = '';

		if ( this.iife ) {

			header += '( function ( TSL, uniforms ) {\n\n';

			header += imports.length > 0 ? '\tconst { ' + imports.join( ', ' ) + ' } = TSL;\n' : '';
			footer += exports.length > 0 ? '\treturn { ' + exports.join( ', ' ) + ' };\n' : '';

			footer += '\n} );';

		} else {

			header += imports.length > 0 ? 'import { ' + imports.join( ', ' ) + ' } from \'three/tsl\';\n' : '';

		}

		return header + code + footer;

	}
```
</details>


---