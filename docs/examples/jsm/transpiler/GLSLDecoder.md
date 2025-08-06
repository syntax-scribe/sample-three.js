[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `GLSLDecoder.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 33 |
| 🧱 Classes | 3 |
| 📦 Imports | 27 |
| 📊 Variables & Constants | 76 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/transpiler/GLSLDecoder.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Program` | `./AST.js` |
| `FunctionDeclaration` | `./AST.js` |
| `Switch` | `./AST.js` |
| `For` | `./AST.js` |
| `AccessorElements` | `./AST.js` |
| `Ternary` | `./AST.js` |
| `Varying` | `./AST.js` |
| `DynamicElement` | `./AST.js` |
| `StaticElement` | `./AST.js` |
| `FunctionParameter` | `./AST.js` |
| `Unary` | `./AST.js` |
| `Conditional` | `./AST.js` |
| `VariableDeclaration` | `./AST.js` |
| `Operator` | `./AST.js` |
| `Number` | `./AST.js` |
| `String` | `./AST.js` |
| `FunctionCall` | `./AST.js` |
| `Return` | `./AST.js` |
| `Accessor` | `./AST.js` |
| `Uniform` | `./AST.js` |
| `Discard` | `./AST.js` |
| `SwitchCase` | `./AST.js` |
| `Continue` | `./AST.js` |
| `Break` | `./AST.js` |
| `While` | `./AST.js` |
| `Comment` | `./AST.js` |
| `isType` | `./TranspilerUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `unaryOperators` | `string[]` | let/var | `[ '+', '-', '~', '!', '++', '--' ]` | ✗ |
| `arithmeticOperators` | `string[]` | let/var | `[ '*', '/', '%', '+', '-', '<<', '>>' ]` | ✗ |
| `associativityRightToLeft` | `string[]` | let/var | `[ '=', '+=', '-=', '*=', '/=', '%=', '^=', '&=', '\|=', '<<=', '>>=', ',', '?...` | ✗ |
| `glslToTSL` | `{ inversesqrt: string; }` | let/var | `{ inversesqrt: 'inverseSqrt' }` | ✗ |
| `samplers` | `string[]` | let/var | `[ 'sampler1D', 'sampler2D', 'sampler2DArray', 'sampler2DShadow', 'sampler2DAr...` | ✗ |
| `samplersCube` | `string[]` | let/var | `[ 'samplerCube', 'samplerCubeShadow', 'usamplerCube', 'isamplerCube' ]` | ✗ |
| `samplers3D` | `string[]` | let/var | `[ 'sampler3D', 'isampler3D', 'usampler3D' ]` | ✗ |
| `spaceRegExp` | `RegExp` | let/var | `/^((\t\| )\n*)+/` | ✗ |
| `lineRegExp` | `RegExp` | let/var | `/^\n+/` | ✗ |
| `commentRegExp` | `RegExp` | let/var | `/^\/\*[\s\S]*?\*\//` | ✗ |
| `inlineCommentRegExp` | `RegExp` | let/var | `/^\/\/.*?(?=\n\|$)/` | ✗ |
| `numberRegExp` | `RegExp` | let/var | `/^((0x\w+)\|(\.?\d+\.?\d*((e-?\d+)\|\w)?))/` | ✗ |
| `stringDoubleRegExp` | `RegExp` | let/var | `/^(\"((?:[^"\\]\|\\.)*)\")/` | ✗ |
| `stringSingleRegExp` | `RegExp` | let/var | `/^(\'((?:[^'\\]\|\\.)*)\')/` | ✗ |
| `literalRegExp` | `RegExp` | let/var | `/^[A-Za-z](\w\|\.)*/` | ✗ |
| `operatorsRegExp` | `RegExp` | let/var | `new RegExp( '^(\\' + [ '<<=', '>>=', '++', '--', '<<', '>>', '+=', '-=', '*='...` | ✗ |
| `TokenParserList` | `({ type: string; regexp: RegExp; isTa...` | let/var | `[ { type: Token.LINE, regexp: lineRegExp, isTag: true }, { type: Token.COMMEN...` | ✗ |
| `i` | `number` | let/var | `params.length` | ✗ |
| `skipLength` | `any` | let/var | `skip ? skip[ 0 ].length : 0` | ✗ |
| `parser` | `{ type: string; regexp: RegExp; isTag...` | let/var | `TokenParserList[ i ]` | ✗ |
| `token` | `Token` | let/var | `new Token( this, parser.type, result[ parser.group \|\| 0 ], this.position )` | ✗ |
| `tags` | `any[]` | let/var | `[]` | ✗ |
| `output` | `any[]` | let/var | `[]` | ✗ |
| `groupIndex` | `number` | let/var | `0` | ✗ |
| `token` | `any` | let/var | `tokens[ i ]` | ✗ |
| `firstToken` | `any` | let/var | `tokens[ 0 ]` | ✗ |
| `lastToken` | `any` | let/var | `tokens[ tokens.length - 1 ]` | ✗ |
| `groupIndex` | `number` | let/var | `0` | ✗ |
| `token` | `any` | let/var | `tokens[ i ]` | ✗ |
| `operator` | `any` | let/var | `tokens[ leftTokens.length ]` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `secondToken` | `any` | let/var | `tokens[ 1 ]` | ✗ |
| `functionCall` | `any` | let/var | `new FunctionCall( getFunctionName( firstToken.str ), paramsTokens )` | ✗ |
| `elements` | `any[]` | let/var | `[]` | ✗ |
| `currentTokens` | `any` | let/var | `tokens` | ✗ |
| `token` | `any` | let/var | `currentTokens[ 0 ]` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `current` | `any` | let/var | `expression` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `immutable` | `boolean` | let/var | `tokens[ i ].str === 'const'` | ✗ |
| `qualifier` | `any` | let/var | `tokens[ i ].str` | ✗ |
| `type` | `any` | let/var | `tokens[ i ++ ].str` | ✗ |
| `name` | `any` | let/var | `tokens[ i ++ ].str` | ✗ |
| `type` | `any` | let/var | `this.readToken().str` | ✗ |
| `name` | `any` | let/var | `this.readToken().str` | ✗ |
| `func` | `any` | let/var | `new FunctionDeclaration( type, name, params, body )` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `immutable` | `boolean` | let/var | `tokens[ 0 ].str === 'const'` | ✗ |
| `name` | `any` | let/var | `tokens[ index ++ ].str` | ✗ |
| `token` | `any` | let/var | `tokens[ index ]` | ✗ |
| `init` | `any` | let/var | `null` | ✗ |
| `next` | `any` | let/var | `null` | ✗ |
| `variable` | `any` | let/var | `new VariableDeclaration( type, name, init, next, immutable )` | ✗ |
| `type` | `any` | let/var | `tokens[ 1 ].str` | ✗ |
| `name` | `any` | let/var | `tokens[ 2 ].str` | ✗ |
| `type` | `any` | let/var | `tokens[ 1 ].str` | ✗ |
| `name` | `any` | let/var | `tokens[ 2 ].str` | ✗ |
| `body` | `any` | let/var | `*not shown*` | ✗ |
| `statement` | `any` | let/var | `new While( condition, body )` | ✗ |
| `initialization` | `any` | let/var | `*not shown*` | ✗ |
| `body` | `any` | let/var | `*not shown*` | ✗ |
| `statement` | `any` | let/var | `new For( initialization, condition, afterthought, body )` | ✗ |
| `switchStatement` | `any` | let/var | `new Switch( discriminant, cases )` | ✗ |
| `cases` | `any[]` | let/var | `[]` | ✗ |
| `conditions` | `any` | let/var | `null` | ✗ |
| `body` | `any` | let/var | `*not shown*` | ✗ |
| `conditional` | `any` | let/var | `new Conditional( parseIfExpression(), parseIfBlock() )` | ✗ |
| `current` | `any` | let/var | `conditional` | ✗ |
| `previous` | `any` | let/var | `current` | ✗ |
| `expression` | `any` | let/var | `null` | ✗ |
| `body` | `any[]` | let/var | `[]` | ✗ |
| `groupIndex` | `number` | let/var | `0` | ✗ |
| `statement` | `any` | let/var | `null` | ✗ |
| `lastStatement` | `any` | let/var | `null` | ✗ |
| `polyfill` | `string` | let/var | `''` | ✗ |
| `program` | `Program` | let/var | `new Program( body )` | ✗ |


---

## Functions

### `getFunctionName(str: any): any`

**Parameters:**

- **`str`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getFunctionName( str ) {

	return glslToTSL[ str ] || str;

}
```
</details>

### `getGroupDelta(str: any): 1 | 0 | -1`

**Parameters:**

- **`str`** `any`

**Returns:** `1 | 0 | -1`

<details><summary>Code</summary>

```typescript
function getGroupDelta( str ) {

	if ( str === '(' || str === '[' || str === '{' ) return 1;
	if ( str === ')' || str === ']' || str === '}' ) return - 1;

	return 0;

}
```
</details>

### `Tokenizer.tokenize(): this`

**Returns:** `this`

**Calls:**

- `this.readToken`
- `this.tokens.push`

<details><summary>Code</summary>

```typescript
tokenize() {

		let token = this.readToken();

		while ( token ) {

			this.tokens.push( token );

			token = this.readToken();

		}

		return this;

	}
```
</details>

### `Tokenizer.skip(params: any[]): any`

**Parameters:**

- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `this.source.substr`
- `params[ i ].exec`

**Internal Comments:**
```
// re-skip, new remainingCode is generated (x3)
// maybe exist previous regexp non detected (x3)
```

<details><summary>Code</summary>

```typescript
skip( ...params ) {

		let remainingCode = this.source.substr( this.position );
		let i = params.length;

		while ( i -- ) {

			const skip = params[ i ].exec( remainingCode );
			const skipLength = skip ? skip[ 0 ].length : 0;

			if ( skipLength > 0 ) {

				this.position += skipLength;

				remainingCode = this.source.substr( this.position );

				// re-skip, new remainingCode is generated
				// maybe exist previous regexp non detected
				i = params.length;

			}

		}

		return remainingCode;

	}
```
</details>

### `Tokenizer.nextToken(): Token`

**Returns:** `Token`

**Calls:**

- `this.skip`
- `parser.regexp.exec`

<details><summary>Code</summary>

```typescript
nextToken() {

		const remainingCode = this.skip( spaceRegExp );

		for ( var i = 0; i < TokenParserList.length; i ++ ) {

			const parser = TokenParserList[ i ];
			const result = parser.regexp.exec( remainingCode );

			if ( result ) {

				const token = new Token( this, parser.type, result[ parser.group || 0 ], this.position );
				token.isTag = parser.isTag;

				this.position += result[ 0 ].length;

				return token;

			}

		}

	}
```
</details>

### `Tokenizer.readToken(): Token`

**Returns:** `Token`

**Calls:**

- `this.nextToken`
- `tags.push`

<details><summary>Code</summary>

```typescript
readToken() {

		let token = this.nextToken();

		if ( token && token.isTag ) {

			const tags = [];

			while ( token.isTag ) {

				tags.push( token );

				token = this.nextToken();

				if ( ! token ) return;

			}

			token.tags = tags;

		}

		return token;

	}
```
</details>

### `GLSLDecoder.addPolyfill(name: any, polyfill: any): this`

**Parameters:**

- **`name`** `any`
- **`polyfill`** `any`

**Returns:** `this`

**Calls:**

- `this.keywords.push`

<details><summary>Code</summary>

```typescript
addPolyfill( name, polyfill ) {

		this.keywords.push( { name, polyfill } );

		return this;

	}
```
</details>

### `GLSLDecoder.readToken(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
readToken() {

		return this.tokens[ this.index ++ ];

	}
```
</details>

### `GLSLDecoder.getToken(offset: number): any`

**Parameters:**

- **`offset`** `number`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getToken( offset = 0 ) {

		return this.tokens[ this.index + offset ];

	}
```
</details>

### `GLSLDecoder.getTokensUntil(str: any, tokens: any, offset: number): any[]`

**Parameters:**

- **`str`** `any`
- **`tokens`** `any`
- **`offset`** `number`

**Returns:** `any[]`

**Calls:**

- `getGroupDelta`
- `output.push`

<details><summary>Code</summary>

```typescript
getTokensUntil( str, tokens, offset = 0 ) {

		const output = [];

		let groupIndex = 0;

		for ( let i = offset; i < tokens.length; i ++ ) {

			const token = tokens[ i ];

			groupIndex += getGroupDelta( token.str );

			output.push( token );

			if ( groupIndex === 0 && token.str === str ) {

				break;

			}

		}

		return output;

	}
```
</details>

### `GLSLDecoder.readTokensUntil(str: any): any[]`

**Parameters:**

- **`str`** `any`

**Returns:** `any[]`

**Calls:**

- `this.getTokensUntil`

<details><summary>Code</summary>

```typescript
readTokensUntil( str ) {

		const tokens = this.getTokensUntil( str, this.tokens, this.index );

		this.index += tokens.length;

		return tokens;

	}
```
</details>

### `GLSLDecoder.parseExpressionFromTokens(tokens: any): any`

**Parameters:**

- **`tokens`** `any`

**Returns:** `any`

**Calls:**

- `getGroupDelta`
- `arithmeticOperators.includes`
- `tokens.slice`
- `this.getTokensUntil( ':', tokens, i + 1 ).slice`
- `this.parseExpressionFromTokens`
- `associativityRightToLeft.includes`
- `parseToken`
- `this.getTokensUntil`
- `leftTokens.slice`
- `/^(0x)/.test`
- `/u$|U$/.test`
- `/f|e|\./.test`
- `firstToken.str.replace`
- `str.replace`
- `this.getTokensUntil( ')', tokens, 1 ).slice`
- `this.parseFunctionParametersFromTokens`
- `getFunctionName`
- `this.parseAccessorElementsFromTokens`

**Internal Comments:**
```
// precedence operators (x2)
// important for negate operator after arithmetic operator: a * -1, a * -( b )
// unary operators (before)
// unary operators (after)
// groups
// primitives and accessors
// function call (x2)
// array accessor (x2)
```

<details><summary>Code</summary>

```typescript
parseExpressionFromTokens( tokens ) {

		if ( tokens.length === 0 ) return null;

		const firstToken = tokens[ 0 ];
		const lastToken = tokens[ tokens.length - 1 ];

		// precedence operators

		let groupIndex = 0;

		for ( const operator of precedenceOperators ) {

			const parseToken = ( i, inverse = false ) => {

				const token = tokens[ i ];

				groupIndex += getGroupDelta( token.str );

				if ( ! token.isOperator || i === 0 || i === tokens.length - 1 ) return;

				// important for negate operator after arithmetic operator: a * -1, a * -( b )
				if ( inverse && arithmeticOperators.includes( tokens[ i - 1 ].str ) ) {

					return;

				}

				if ( groupIndex === 0 && token.str === operator ) {

					if ( operator === '?' ) {

						const conditionTokens = tokens.slice( 0, i );
						const leftTokens = this.getTokensUntil( ':', tokens, i + 1 ).slice( 0, - 1 );
						const rightTokens = tokens.slice( i + leftTokens.length + 2 );

						const condition = this.parseExpressionFromTokens( conditionTokens );
						const left = this.parseExpressionFromTokens( leftTokens );
						const right = this.parseExpressionFromTokens( rightTokens );

						return new Ternary( condition, left, right );

					} else {

						const left = this.parseExpressionFromTokens( tokens.slice( 0, i ) );
						const right = this.parseExpressionFromTokens( tokens.slice( i + 1, tokens.length ) );

						return new Operator( operator, left, right );

					}

				}

				if ( inverse ) {

					if ( groupIndex > 0 ) {

						return this.parseExpressionFromTokens( tokens.slice( i ) );

					}

				} else {

					if ( groupIndex < 0 ) {

						return this.parseExpressionFromTokens( tokens.slice( 0, i ) );

					}

				}

			};

			if ( associativityRightToLeft.includes( operator ) ) {

				for ( let i = 0; i < tokens.length; i ++ ) {

					const result = parseToken( i );

					if ( result ) return result;

				}

			} else {

				for ( let i = tokens.length - 1; i >= 0; i -- ) {

					const result = parseToken( i, true );

					if ( result ) return result;

				}

			}

		}

		// unary operators (before)

		if ( firstToken.isOperator ) {

			for ( const operator of unaryOperators ) {

				if ( firstToken.str === operator ) {

					const right = this.parseExpressionFromTokens( tokens.slice( 1 ) );

					return new Unary( operator, right );

				}

			}

		}

		// unary operators (after)

		if ( lastToken.isOperator ) {

			for ( const operator of unaryOperators ) {

				if ( lastToken.str === operator ) {

					const left = this.parseExpressionFromTokens( tokens.slice( 0, tokens.length - 1 ) );

					return new Unary( operator, left, true );

				}

			}

		}

		// groups

		if ( firstToken.str === '(' ) {

			const leftTokens = this.getTokensUntil( ')', tokens );

			const left = this.parseExpressionFromTokens( leftTokens.slice( 1, leftTokens.length - 1 ) );

			const operator = tokens[ leftTokens.length ];

			if ( operator ) {

				const rightTokens = tokens.slice( leftTokens.length + 1 );
				const right = this.parseExpressionFromTokens( rightTokens );

				return new Operator( operator.str, left, right );

			}

			return left;

		}

		// primitives and accessors

		if ( firstToken.isNumber ) {

			let type;

			const isHex = /^(0x)/.test( firstToken.str );

			if ( isHex ) type = 'int';
			else if ( /u$|U$/.test( firstToken.str ) ) type = 'uint';
			else if ( /f|e|\./.test( firstToken.str ) ) type = 'float';
			else type = 'int';

			let str = firstToken.str.replace( /u|U|i$/, '' );

			if ( isHex === false ) {

				str = str.replace( /f$/, '' );

			}

			return new Number( str, type );

		} else if ( firstToken.isString ) {

			return new String( firstToken.str );

		} else if ( firstToken.isLiteral ) {

			if ( firstToken.str === 'return' ) {

				return new Return( this.parseExpressionFromTokens( tokens.slice( 1 ) ) );

			} else if ( firstToken.str === 'discard' ) {

				return new Discard();

			} else if ( firstToken.str === 'continue' ) {

				return new Continue();

			} else if ( firstToken.str === 'break' ) {

				return new Break();

			}

			const secondToken = tokens[ 1 ];

			if ( secondToken ) {

				if ( secondToken.str === '(' ) {

					// function call

					const internalTokens = this.getTokensUntil( ')', tokens, 1 ).slice( 1, - 1 );

					const paramsTokens = this.parseFunctionParametersFromTokens( internalTokens );

					const functionCall = new FunctionCall( getFunctionName( firstToken.str ), paramsTokens );

					const accessTokens = tokens.slice( 3 + internalTokens.length );

					if ( accessTokens.length > 0 ) {

						const elements = this.parseAccessorElementsFromTokens( accessTokens );

						return new AccessorElements( functionCall, elements );

					}

					return functionCall;

				} else if ( secondToken.str === '[' ) {

					// array accessor

					const elements = this.parseAccessorElementsFromTokens( tokens.slice( 1 ) );

					return new AccessorElements( new Accessor( firstToken.str ), elements );

				}

			}

			return new Accessor( firstToken.str );

		}

	}
```
</details>

### `GLSLDecoder.parseAccessorElementsFromTokens(tokens: any): any`

**Parameters:**

- **`tokens`** `any`

**Returns:** `any`

**Calls:**

- `this.getTokensUntil`
- `this.parseExpressionFromTokens`
- `accessorTokens.slice`
- `currentTokens.slice`
- `elements.push`
- `console.error`

<details><summary>Code</summary>

```typescript
parseAccessorElementsFromTokens( tokens ) {

		const elements = [];

		let currentTokens = tokens;

		while ( currentTokens.length > 0 ) {

			const token = currentTokens[ 0 ];

			if ( token.str === '[' ) {

				const accessorTokens = this.getTokensUntil( ']', currentTokens );

				const element = this.parseExpressionFromTokens( accessorTokens.slice( 1, accessorTokens.length - 1 ) );

				currentTokens = currentTokens.slice( accessorTokens.length );

				elements.push( new DynamicElement( element ) );

			} else if ( token.str === '.' ) {

				const accessorTokens = currentTokens.slice( 1, 2 );

				const element = this.parseExpressionFromTokens( accessorTokens );

				currentTokens = currentTokens.slice( 2 );

				elements.push( new StaticElement( element ) );

			} else {

				console.error( 'Unknown accessor expression', token );

				break;

			}

		}

		return elements;

	}
```
</details>

### `GLSLDecoder.parseFunctionParametersFromTokens(tokens: any): any`

**Parameters:**

- **`tokens`** `any`

**Returns:** `any`

**Calls:**

- `this.parseExpressionFromTokens`
- `params.push`

<details><summary>Code</summary>

```typescript
parseFunctionParametersFromTokens( tokens ) {

		if ( tokens.length === 0 ) return [];

		const expression = this.parseExpressionFromTokens( tokens );
		const params = [];

		let current = expression;

		while ( current.type === ',' ) {

			params.push( current.left );

			current = current.right;

		}

		params.push( current );

		return params;

	}
```
</details>

### `GLSLDecoder.parseExpression(): any`

**Returns:** `any`

**Calls:**

- `this.readTokensUntil`
- `this.parseExpressionFromTokens`
- `tokens.slice`

<details><summary>Code</summary>

```typescript
parseExpression() {

		const tokens = this.readTokensUntil( ';' );

		const exp = this.parseExpressionFromTokens( tokens.slice( 0, tokens.length - 1 ) );

		return exp;

	}
```
</details>

### `GLSLDecoder.parseFunctionParams(tokens: any): FunctionParameter[]`

**Parameters:**

- **`tokens`** `any`

**Returns:** `FunctionParameter[]`

**Calls:**

- `/^(in|out|inout)$/.test`
- `params.push`

<details><summary>Code</summary>

```typescript
parseFunctionParams( tokens ) {

		const params = [];

		for ( let i = 0; i < tokens.length; i ++ ) {

			const immutable = tokens[ i ].str === 'const';
			if ( immutable ) i ++;

			let qualifier = tokens[ i ].str;

			if ( /^(in|out|inout)$/.test( qualifier ) ) {

				i ++;

			} else {

				qualifier = null;

			}

			const type = tokens[ i ++ ].str;
			const name = tokens[ i ++ ].str;

			params.push( new FunctionParameter( type, name, qualifier, immutable ) );

			if ( tokens[ i ] && tokens[ i ].str !== ',' ) throw new Error( 'Expected ","' );

		}

		return params;

	}
```
</details>

### `GLSLDecoder.parseFunction(): any`

**Returns:** `any`

**Calls:**

- `this.readToken`
- `this.readTokensUntil`
- `this.parseFunctionParams`
- `paramsTokens.slice`
- `this.parseBlock`

<details><summary>Code</summary>

```typescript
parseFunction() {

		const type = this.readToken().str;
		const name = this.readToken().str;

		const paramsTokens = this.readTokensUntil( ')' );

		const params = this.parseFunctionParams( paramsTokens.slice( 1, paramsTokens.length - 1 ) );
		const body = this.parseBlock();

		const func = new FunctionDeclaration( type, name, params, body );

		return func;

	}
```
</details>

### `GLSLDecoder.parseVariablesFromToken(tokens: any, type: any): any`

**Parameters:**

- **`tokens`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `this.getTokensUntil`
- `initTokens.slice`
- `expressionTokens.pop`
- `this.parseExpressionFromTokens`
- `tokens.slice`
- `this.parseVariablesFromToken`
- `nextTokens.slice`

<details><summary>Code</summary>

```typescript
parseVariablesFromToken( tokens, type ) {

		let index = 0;
		const immutable = tokens[ 0 ].str === 'const';

		if ( immutable ) index ++;

		type = type || tokens[ index ++ ].str;
		const name = tokens[ index ++ ].str;

		const token = tokens[ index ];

		let init = null;
		let next = null;

		if ( token ) {

			const initTokens = this.getTokensUntil( ',', tokens, index );

			if ( initTokens[ 0 ].str === '=' ) {

				const expressionTokens = initTokens.slice( 1 );
				if ( expressionTokens[ expressionTokens.length - 1 ].str === ',' ) expressionTokens.pop();

				init = this.parseExpressionFromTokens( expressionTokens );

			}

			const nextTokens = tokens.slice( initTokens.length + ( index - 1 ) );

			if ( nextTokens[ 0 ] && nextTokens[ 0 ].str === ',' ) {

				next = this.parseVariablesFromToken( nextTokens.slice( 1 ), type );

			}

		}

		const variable = new VariableDeclaration( type, name, init, next, immutable );

		return variable;

	}
```
</details>

### `GLSLDecoder.parseVariables(): any`

**Returns:** `any`

**Calls:**

- `this.readTokensUntil`
- `this.parseVariablesFromToken`
- `tokens.slice`

<details><summary>Code</summary>

```typescript
parseVariables() {

		const tokens = this.readTokensUntil( ';' );

		return this.parseVariablesFromToken( tokens.slice( 0, tokens.length - 1 ) );

	}
```
</details>

### `GLSLDecoder.parseUniform(): Uniform`

**Returns:** `Uniform`

**Calls:**

- `this.readTokensUntil`
- `samplers.includes`
- `samplersCube.includes`
- `samplers3D.includes`

**Internal Comments:**
```
// GLSL to TSL types
```

<details><summary>Code</summary>

```typescript
parseUniform() {

		const tokens = this.readTokensUntil( ';' );

		let type = tokens[ 1 ].str;
		const name = tokens[ 2 ].str;

		// GLSL to TSL types

		if ( samplers.includes( type ) ) type = 'texture';
		else if ( samplersCube.includes( type ) ) type = 'cubeTexture';
		else if ( samplers3D.includes( type ) ) type = 'texture3D';

		return new Uniform( type, name );

	}
```
</details>

### `GLSLDecoder.parseVarying(): Varying`

**Returns:** `Varying`

**Calls:**

- `this.readTokensUntil`

<details><summary>Code</summary>

```typescript
parseVarying() {

		const tokens = this.readTokensUntil( ';' );

		const type = tokens[ 1 ].str;
		const name = tokens[ 2 ].str;

		return new Varying( type, name );

	}
```
</details>

### `GLSLDecoder.parseReturn(): Return`

**Returns:** `Return`

**Calls:**

- `this.readToken`
- `this.parseExpression`

<details><summary>Code</summary>

```typescript
parseReturn() {

		this.readToken(); // skip 'return'

		const expression = this.parseExpression();

		return new Return( expression );

	}
```
</details>

### `GLSLDecoder.parseWhile(): any`

**Returns:** `any`

**Calls:**

- `this.readToken`
- `this.readTokensUntil( ')' ).slice`
- `this.parseExpressionFromTokens`
- `this.getToken`
- `this.parseBlock`
- `this.parseExpression`

<details><summary>Code</summary>

```typescript
parseWhile() {

		this.readToken(); // skip 'while'

		const conditionTokens = this.readTokensUntil( ')' ).slice( 1, - 1 );
		const condition = this.parseExpressionFromTokens( conditionTokens );

		let body;

		if ( this.getToken().str === '{' ) {

			body = this.parseBlock();

		} else {

			body = [ this.parseExpression() ];

		}

		const statement = new While( condition, body );

		return statement;

	}
```
</details>

### `GLSLDecoder.parseFor(): any`

**Returns:** `any`

**Calls:**

- `this.readToken`
- `this.readTokensUntil( ')' ).slice`
- `this.getTokensUntil( ';', forTokens, 0 ).slice`
- `this.getTokensUntil( ';', forTokens, initializationTokens.length + 1 ).slice`
- `forTokens.slice`
- `isType (from ./TranspilerUtils.js)`
- `this.parseVariablesFromToken`
- `this.parseExpressionFromTokens`
- `this.getToken`
- `this.parseBlock`
- `this.parseExpression`

<details><summary>Code</summary>

```typescript
parseFor() {

		this.readToken(); // skip 'for'

		const forTokens = this.readTokensUntil( ')' ).slice( 1, - 1 );

		const initializationTokens = this.getTokensUntil( ';', forTokens, 0 ).slice( 0, - 1 );
		const conditionTokens = this.getTokensUntil( ';', forTokens, initializationTokens.length + 1 ).slice( 0, - 1 );
		const afterthoughtTokens = forTokens.slice( initializationTokens.length + conditionTokens.length + 2 );

		let initialization;

		if ( initializationTokens[ 0 ] && isType( initializationTokens[ 0 ].str ) ) {

			initialization = this.parseVariablesFromToken( initializationTokens );

		} else {

			initialization = this.parseExpressionFromTokens( initializationTokens );

		}

		const condition = this.parseExpressionFromTokens( conditionTokens );
		const afterthought = this.parseExpressionFromTokens( afterthoughtTokens );

		let body;

		if ( this.getToken().str === '{' ) {

			body = this.parseBlock();

		} else {

			body = [ this.parseExpression() ];

		}

		const statement = new For( initialization, condition, afterthought, body );

		return statement;

	}
```
</details>

### `GLSLDecoder.parseSwitch(): any`

**Returns:** `any`

**Calls:**

- `this.readToken`
- `this.readTokensUntil`
- `this.parseExpressionFromTokens`
- `switchDeterminantTokens.slice`
- `this.getToken`
- `this.parseSwitchCases`

**Internal Comments:**
```
// Parse expression between parentheses. Index 1: char after '('. Index -1: char before ')' (x2)
// Validate curly braces
```

<details><summary>Code</summary>

```typescript
parseSwitch() {

		this.readToken(); // Skip 'switch'

		const switchDeterminantTokens = this.readTokensUntil( ')' );

		// Parse expression between parentheses. Index 1: char after '('. Index -1: char before ')'
		const discriminant = this.parseExpressionFromTokens( switchDeterminantTokens.slice( 1, - 1 ) );

		// Validate curly braces
		if ( this.getToken().str !== '{' ) {

			throw new Error( 'Expected \'{\' after switch(...) ' );

		}

		this.readToken(); // Skip '{'

		const cases = this.parseSwitchCases();

		const switchStatement = new Switch( discriminant, cases );

		return switchStatement;

	}
```
</details>

### `GLSLDecoder.parseSwitchCases(): any`

**Returns:** `any`

**Calls:**

- `this.getToken`
- `isCase`
- `this.readToken`
- `this.readTokensUntil`
- `this.parseExpressionFromTokens`
- `caseTokens.slice`
- `conditions.push`
- `cases.push`
- `this.parseBlock`

**Internal Comments:**
```
// If the next token is another case/default, continue parsing
```

<details><summary>Code</summary>

```typescript
parseSwitchCases() {

		const cases = [];

		let token = this.getToken();
		let conditions = null;

		const isCase = ( token ) => token.str === 'case' || token.str === 'default';

		while ( isCase( token ) ) {

			this.readToken(); // Skip 'case' or 'default'

			if ( token.str === 'case' ) {

				const caseTokens = this.readTokensUntil( ':' );
				const caseStatement = this.parseExpressionFromTokens( caseTokens.slice( 0, - 1 ) );

				conditions = conditions || [];
				conditions.push( caseStatement );

			} else {

				this.readTokensUntil( ':' ); // Skip 'default:'

				conditions = null;

			}

			token = this.getToken();

			if ( isCase( token ) ) {

				// If the next token is another case/default, continue parsing
				continue;

			}

			cases.push( new SwitchCase( this.parseBlock(), conditions ) );

			token = this.getToken();

			conditions = null;

		}

		return cases;

	}
```
</details>

### `GLSLDecoder.parseIf(): any`

**Returns:** `any`

**Calls:**

- `this.readToken`
- `this.readTokensUntil`
- `this.parseExpressionFromTokens`
- `condTokens.slice`
- `this.getToken`
- `this.parseBlock`
- `this.parseExpression`
- `parseIfExpression`
- `parseIfBlock`

**Internal Comments:**
```
// (x4)
// Parse the first if statement (x2)
// Assign the current if/else statement as the previous within the chain of conditionals (x2)
// If an 'else if' statement, parse the conditional within the if
// Current conditional now equal to next conditional in the chain (x3)
// n - 1 conditional's else statement assigned to new if/else statement (x4)
```

<details><summary>Code</summary>

```typescript
parseIf() {

		const parseIfExpression = () => {

			this.readToken(); // skip 'if'

			const condTokens = this.readTokensUntil( ')' );

			return this.parseExpressionFromTokens( condTokens.slice( 1, condTokens.length - 1 ) );

		};

		const parseIfBlock = () => {

			let body;

			if ( this.getToken().str === '{' ) {

				body = this.parseBlock();

			} else {

				body = [ this.parseExpression() ];

			}

			return body;

		};

		//

		// Parse the first if statement
		const conditional = new Conditional( parseIfExpression(), parseIfBlock() );

		//

		let current = conditional;

		while ( this.getToken() && this.getToken().str === 'else' ) {

			this.readToken(); // skip 'else'

			// Assign the current if/else statement as the previous within the chain of conditionals
			const previous = current;

			let expression = null;

			// If an 'else if' statement, parse the conditional within the if
			if ( this.getToken().str === 'if' ) {

				// Current conditional now equal to next conditional in the chain
				expression = parseIfExpression();

			}

			current = new Conditional( expression, parseIfBlock() );
			current.parent = previous;

			// n - 1 conditional's else statement assigned to new if/else statement
			previous.elseConditional = current;

		}

		return conditional;

	}
```
</details>

### `GLSLDecoder.parseBlock(): any`

**Returns:** `any`

**Calls:**

- `this.getToken`
- `this.readToken`
- `getGroupDelta`
- `tag.str.replace`
- `body.push`
- `this.parseVariables`
- `this.parseUniform`
- `this.parseVarying`
- `isType (from ./TranspilerUtils.js)`
- `this.parseFunction`
- `this.parseReturn`
- `this.parseIf`
- `this.parseFor`
- `this.parseWhile`
- `this.parseSwitch`
- `this.parseExpression`

**Internal Comments:**
```
//
```

<details><summary>Code</summary>

```typescript
parseBlock() {

		const body = [];

		const firstToken = this.getToken();

		if ( firstToken.str === '{' ) {

			this.readToken(); // skip '{'

		}

		let groupIndex = 0;

		while ( this.index < this.tokens.length ) {

			const token = this.getToken();

			let statement = null;

			groupIndex += getGroupDelta( token.str );

			if ( groupIndex === 0 && ( token.str === 'case' || token.str === 'default' ) ) {

				return body; // switch case or default statement, return body

			} else if ( groupIndex < 0 ) {

				this.readToken(); // skip '}'

				return body;

			}

			//

			if ( token.tags ) {

				let lastStatement = null;

				for ( const tag of token.tags ) {

					if ( tag.type === Token.COMMENT ) {

						const str = tag.str.replace( /\t/g, '' );

						if ( ! lastStatement || lastStatement.isComment !== true ) {

							lastStatement = new Comment( str );
							body.push( lastStatement );

						} else {

							lastStatement.comment += '\n' + str;

						}

					}

				}

			}

			if ( token.isLiteral || token.isOperator ) {

				if ( token.str === 'const' ) {

					statement = this.parseVariables();

				} else if ( token.str === 'uniform' ) {

					statement = this.parseUniform();

				} else if ( token.str === 'varying' ) {

					statement = this.parseVarying();

				} else if ( isType( token.str ) ) {

					if ( this.getToken( 2 ).str === '(' ) {

						statement = this.parseFunction();

					} else {

						statement = this.parseVariables();

					}

				} else if ( token.str === 'return' ) {

					statement = this.parseReturn();

				} else if ( token.str === 'if' ) {

					statement = this.parseIf();

				} else if ( token.str === 'for' ) {

					statement = this.parseFor();

				} else if ( token.str === 'while' ) {

					statement = this.parseWhile();

				} else if ( token.str === 'switch' ) {

					statement = this.parseSwitch();

				} else {

					statement = this.parseExpression();

				}

			}

			if ( statement ) {

				body.push( statement );

			} else {

				this.index ++;

			}

		}

		return body;

	}
```
</details>

### `GLSLDecoder.parse(source: any): Program`

**Parameters:**

- **`source`** `any`

**Returns:** `Program`

**Calls:**

- `new RegExp( `(^|\\b)${ keyword.name }($|\\b)`, 'gm' ).test`
- `new Tokenizer( polyfill + source ).tokenize`
- `this.parseBlock`

<details><summary>Code</summary>

```typescript
parse( source ) {

		let polyfill = '';

		for ( const keyword of this.keywords ) {

			if ( new RegExp( `(^|\\b)${ keyword.name }($|\\b)`, 'gm' ).test( source ) ) {

				polyfill += keyword.polyfill + '\n';

			}

		}

		if ( polyfill ) {

			polyfill = '// Polyfills\n\n' + polyfill + '\n';

		}

		this.index = 0;
		this.tokenizer = new Tokenizer( polyfill + source ).tokenize();

		const body = this.parseBlock();
		const program = new Program( body );

		return program;


	}
```
</details>

### `parseToken(i: any, inverse: boolean): any`

**Parameters:**

- **`i`** `any`
- **`inverse`** `boolean`

**Returns:** `any`

**Calls:**

- `getGroupDelta`
- `arithmeticOperators.includes`
- `tokens.slice`
- `this.getTokensUntil( ':', tokens, i + 1 ).slice`
- `this.parseExpressionFromTokens`

**Internal Comments:**
```
// important for negate operator after arithmetic operator: a * -1, a * -( b )
```

<details><summary>Code</summary>

```typescript
( i, inverse = false ) => {

				const token = tokens[ i ];

				groupIndex += getGroupDelta( token.str );

				if ( ! token.isOperator || i === 0 || i === tokens.length - 1 ) return;

				// important for negate operator after arithmetic operator: a * -1, a * -( b )
				if ( inverse && arithmeticOperators.includes( tokens[ i - 1 ].str ) ) {

					return;

				}

				if ( groupIndex === 0 && token.str === operator ) {

					if ( operator === '?' ) {

						const conditionTokens = tokens.slice( 0, i );
						const leftTokens = this.getTokensUntil( ':', tokens, i + 1 ).slice( 0, - 1 );
						const rightTokens = tokens.slice( i + leftTokens.length + 2 );

						const condition = this.parseExpressionFromTokens( conditionTokens );
						const left = this.parseExpressionFromTokens( leftTokens );
						const right = this.parseExpressionFromTokens( rightTokens );

						return new Ternary( condition, left, right );

					} else {

						const left = this.parseExpressionFromTokens( tokens.slice( 0, i ) );
						const right = this.parseExpressionFromTokens( tokens.slice( i + 1, tokens.length ) );

						return new Operator( operator, left, right );

					}

				}

				if ( inverse ) {

					if ( groupIndex > 0 ) {

						return this.parseExpressionFromTokens( tokens.slice( i ) );

					}

				} else {

					if ( groupIndex < 0 ) {

						return this.parseExpressionFromTokens( tokens.slice( 0, i ) );

					}

				}

			}
```
</details>

### `isCase(token: any): boolean`

**Parameters:**

- **`token`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
( token ) => token.str === 'case' || token.str === 'default'
```
</details>

### `parseIfExpression(): any`

**Returns:** `any`

**Calls:**

- `this.readToken`
- `this.readTokensUntil`
- `this.parseExpressionFromTokens`
- `condTokens.slice`

<details><summary>Code</summary>

```typescript
() => {

			this.readToken(); // skip 'if'

			const condTokens = this.readTokensUntil( ')' );

			return this.parseExpressionFromTokens( condTokens.slice( 1, condTokens.length - 1 ) );

		}
```
</details>

### `parseIfBlock(): any`

**Returns:** `any`

**Calls:**

- `this.getToken`
- `this.parseBlock`
- `this.parseExpression`

<details><summary>Code</summary>

```typescript
() => {

			let body;

			if ( this.getToken().str === '{' ) {

				body = this.parseBlock();

			} else {

				body = [ this.parseExpression() ];

			}

			return body;

		}
```
</details>


---

## Classes

### `Token`

<details><summary>Class Code</summary>

```ts
class Token {

	constructor( tokenizer, type, str, pos ) {

		this.tokenizer = tokenizer;

		this.type = type;

		this.str = str;
		this.pos = pos;

		this.isTag = false;

		this.tags = null;

	}

	get endPos() {

		return this.pos + this.str.length;

	}

	get isNumber() {

		return this.type === Token.NUMBER;

	}

	get isString() {

		return this.type === Token.STRING;

	}

	get isLiteral() {

		return this.type === Token.LITERAL;

	}

	get isOperator() {

		return this.type === Token.OPERATOR;

	}

}
```
</details>

### `Tokenizer`

<details><summary>Class Code</summary>

```ts
class Tokenizer {

	constructor( source ) {

		this.source = source;
		this.position = 0;

		this.tokens = [];

	}

	tokenize() {

		let token = this.readToken();

		while ( token ) {

			this.tokens.push( token );

			token = this.readToken();

		}

		return this;

	}

	skip( ...params ) {

		let remainingCode = this.source.substr( this.position );
		let i = params.length;

		while ( i -- ) {

			const skip = params[ i ].exec( remainingCode );
			const skipLength = skip ? skip[ 0 ].length : 0;

			if ( skipLength > 0 ) {

				this.position += skipLength;

				remainingCode = this.source.substr( this.position );

				// re-skip, new remainingCode is generated
				// maybe exist previous regexp non detected
				i = params.length;

			}

		}

		return remainingCode;

	}

	nextToken() {

		const remainingCode = this.skip( spaceRegExp );

		for ( var i = 0; i < TokenParserList.length; i ++ ) {

			const parser = TokenParserList[ i ];
			const result = parser.regexp.exec( remainingCode );

			if ( result ) {

				const token = new Token( this, parser.type, result[ parser.group || 0 ], this.position );
				token.isTag = parser.isTag;

				this.position += result[ 0 ].length;

				return token;

			}

		}

	}

	readToken() {

		let token = this.nextToken();

		if ( token && token.isTag ) {

			const tags = [];

			while ( token.isTag ) {

				tags.push( token );

				token = this.nextToken();

				if ( ! token ) return;

			}

			token.tags = tags;

		}

		return token;

	}

}
```
</details>

#### Methods

##### `tokenize(): this`

<details><summary>Code</summary>

```ts
tokenize() {

		let token = this.readToken();

		while ( token ) {

			this.tokens.push( token );

			token = this.readToken();

		}

		return this;

	}
```
</details>

##### `skip(params: any[]): any`

<details><summary>Code</summary>

```ts
skip( ...params ) {

		let remainingCode = this.source.substr( this.position );
		let i = params.length;

		while ( i -- ) {

			const skip = params[ i ].exec( remainingCode );
			const skipLength = skip ? skip[ 0 ].length : 0;

			if ( skipLength > 0 ) {

				this.position += skipLength;

				remainingCode = this.source.substr( this.position );

				// re-skip, new remainingCode is generated
				// maybe exist previous regexp non detected
				i = params.length;

			}

		}

		return remainingCode;

	}
```
</details>

##### `nextToken(): Token`

<details><summary>Code</summary>

```ts
nextToken() {

		const remainingCode = this.skip( spaceRegExp );

		for ( var i = 0; i < TokenParserList.length; i ++ ) {

			const parser = TokenParserList[ i ];
			const result = parser.regexp.exec( remainingCode );

			if ( result ) {

				const token = new Token( this, parser.type, result[ parser.group || 0 ], this.position );
				token.isTag = parser.isTag;

				this.position += result[ 0 ].length;

				return token;

			}

		}

	}
```
</details>

##### `readToken(): Token`

<details><summary>Code</summary>

```ts
readToken() {

		let token = this.nextToken();

		if ( token && token.isTag ) {

			const tags = [];

			while ( token.isTag ) {

				tags.push( token );

				token = this.nextToken();

				if ( ! token ) return;

			}

			token.tags = tags;

		}

		return token;

	}
```
</details>

### `GLSLDecoder`

<details><summary>Class Code</summary>

```ts
class GLSLDecoder {

	constructor() {

		this.index = 0;
		this.tokenizer = null;
		this.keywords = [];

		this.addPolyfill( 'gl_FragCoord', 'vec3 gl_FragCoord = vec3( screenCoordinate.x, screenCoordinate.y.oneMinus(), screenCoordinate.z );' );

	}

	addPolyfill( name, polyfill ) {

		this.keywords.push( { name, polyfill } );

		return this;

	}

	get tokens() {

		return this.tokenizer.tokens;

	}

	readToken() {

		return this.tokens[ this.index ++ ];

	}

	getToken( offset = 0 ) {

		return this.tokens[ this.index + offset ];

	}

	getTokensUntil( str, tokens, offset = 0 ) {

		const output = [];

		let groupIndex = 0;

		for ( let i = offset; i < tokens.length; i ++ ) {

			const token = tokens[ i ];

			groupIndex += getGroupDelta( token.str );

			output.push( token );

			if ( groupIndex === 0 && token.str === str ) {

				break;

			}

		}

		return output;

	}

	readTokensUntil( str ) {

		const tokens = this.getTokensUntil( str, this.tokens, this.index );

		this.index += tokens.length;

		return tokens;

	}

	parseExpressionFromTokens( tokens ) {

		if ( tokens.length === 0 ) return null;

		const firstToken = tokens[ 0 ];
		const lastToken = tokens[ tokens.length - 1 ];

		// precedence operators

		let groupIndex = 0;

		for ( const operator of precedenceOperators ) {

			const parseToken = ( i, inverse = false ) => {

				const token = tokens[ i ];

				groupIndex += getGroupDelta( token.str );

				if ( ! token.isOperator || i === 0 || i === tokens.length - 1 ) return;

				// important for negate operator after arithmetic operator: a * -1, a * -( b )
				if ( inverse && arithmeticOperators.includes( tokens[ i - 1 ].str ) ) {

					return;

				}

				if ( groupIndex === 0 && token.str === operator ) {

					if ( operator === '?' ) {

						const conditionTokens = tokens.slice( 0, i );
						const leftTokens = this.getTokensUntil( ':', tokens, i + 1 ).slice( 0, - 1 );
						const rightTokens = tokens.slice( i + leftTokens.length + 2 );

						const condition = this.parseExpressionFromTokens( conditionTokens );
						const left = this.parseExpressionFromTokens( leftTokens );
						const right = this.parseExpressionFromTokens( rightTokens );

						return new Ternary( condition, left, right );

					} else {

						const left = this.parseExpressionFromTokens( tokens.slice( 0, i ) );
						const right = this.parseExpressionFromTokens( tokens.slice( i + 1, tokens.length ) );

						return new Operator( operator, left, right );

					}

				}

				if ( inverse ) {

					if ( groupIndex > 0 ) {

						return this.parseExpressionFromTokens( tokens.slice( i ) );

					}

				} else {

					if ( groupIndex < 0 ) {

						return this.parseExpressionFromTokens( tokens.slice( 0, i ) );

					}

				}

			};

			if ( associativityRightToLeft.includes( operator ) ) {

				for ( let i = 0; i < tokens.length; i ++ ) {

					const result = parseToken( i );

					if ( result ) return result;

				}

			} else {

				for ( let i = tokens.length - 1; i >= 0; i -- ) {

					const result = parseToken( i, true );

					if ( result ) return result;

				}

			}

		}

		// unary operators (before)

		if ( firstToken.isOperator ) {

			for ( const operator of unaryOperators ) {

				if ( firstToken.str === operator ) {

					const right = this.parseExpressionFromTokens( tokens.slice( 1 ) );

					return new Unary( operator, right );

				}

			}

		}

		// unary operators (after)

		if ( lastToken.isOperator ) {

			for ( const operator of unaryOperators ) {

				if ( lastToken.str === operator ) {

					const left = this.parseExpressionFromTokens( tokens.slice( 0, tokens.length - 1 ) );

					return new Unary( operator, left, true );

				}

			}

		}

		// groups

		if ( firstToken.str === '(' ) {

			const leftTokens = this.getTokensUntil( ')', tokens );

			const left = this.parseExpressionFromTokens( leftTokens.slice( 1, leftTokens.length - 1 ) );

			const operator = tokens[ leftTokens.length ];

			if ( operator ) {

				const rightTokens = tokens.slice( leftTokens.length + 1 );
				const right = this.parseExpressionFromTokens( rightTokens );

				return new Operator( operator.str, left, right );

			}

			return left;

		}

		// primitives and accessors

		if ( firstToken.isNumber ) {

			let type;

			const isHex = /^(0x)/.test( firstToken.str );

			if ( isHex ) type = 'int';
			else if ( /u$|U$/.test( firstToken.str ) ) type = 'uint';
			else if ( /f|e|\./.test( firstToken.str ) ) type = 'float';
			else type = 'int';

			let str = firstToken.str.replace( /u|U|i$/, '' );

			if ( isHex === false ) {

				str = str.replace( /f$/, '' );

			}

			return new Number( str, type );

		} else if ( firstToken.isString ) {

			return new String( firstToken.str );

		} else if ( firstToken.isLiteral ) {

			if ( firstToken.str === 'return' ) {

				return new Return( this.parseExpressionFromTokens( tokens.slice( 1 ) ) );

			} else if ( firstToken.str === 'discard' ) {

				return new Discard();

			} else if ( firstToken.str === 'continue' ) {

				return new Continue();

			} else if ( firstToken.str === 'break' ) {

				return new Break();

			}

			const secondToken = tokens[ 1 ];

			if ( secondToken ) {

				if ( secondToken.str === '(' ) {

					// function call

					const internalTokens = this.getTokensUntil( ')', tokens, 1 ).slice( 1, - 1 );

					const paramsTokens = this.parseFunctionParametersFromTokens( internalTokens );

					const functionCall = new FunctionCall( getFunctionName( firstToken.str ), paramsTokens );

					const accessTokens = tokens.slice( 3 + internalTokens.length );

					if ( accessTokens.length > 0 ) {

						const elements = this.parseAccessorElementsFromTokens( accessTokens );

						return new AccessorElements( functionCall, elements );

					}

					return functionCall;

				} else if ( secondToken.str === '[' ) {

					// array accessor

					const elements = this.parseAccessorElementsFromTokens( tokens.slice( 1 ) );

					return new AccessorElements( new Accessor( firstToken.str ), elements );

				}

			}

			return new Accessor( firstToken.str );

		}

	}

	parseAccessorElementsFromTokens( tokens ) {

		const elements = [];

		let currentTokens = tokens;

		while ( currentTokens.length > 0 ) {

			const token = currentTokens[ 0 ];

			if ( token.str === '[' ) {

				const accessorTokens = this.getTokensUntil( ']', currentTokens );

				const element = this.parseExpressionFromTokens( accessorTokens.slice( 1, accessorTokens.length - 1 ) );

				currentTokens = currentTokens.slice( accessorTokens.length );

				elements.push( new DynamicElement( element ) );

			} else if ( token.str === '.' ) {

				const accessorTokens = currentTokens.slice( 1, 2 );

				const element = this.parseExpressionFromTokens( accessorTokens );

				currentTokens = currentTokens.slice( 2 );

				elements.push( new StaticElement( element ) );

			} else {

				console.error( 'Unknown accessor expression', token );

				break;

			}

		}

		return elements;

	}

	parseFunctionParametersFromTokens( tokens ) {

		if ( tokens.length === 0 ) return [];

		const expression = this.parseExpressionFromTokens( tokens );
		const params = [];

		let current = expression;

		while ( current.type === ',' ) {

			params.push( current.left );

			current = current.right;

		}

		params.push( current );

		return params;

	}

	parseExpression() {

		const tokens = this.readTokensUntil( ';' );

		const exp = this.parseExpressionFromTokens( tokens.slice( 0, tokens.length - 1 ) );

		return exp;

	}

	parseFunctionParams( tokens ) {

		const params = [];

		for ( let i = 0; i < tokens.length; i ++ ) {

			const immutable = tokens[ i ].str === 'const';
			if ( immutable ) i ++;

			let qualifier = tokens[ i ].str;

			if ( /^(in|out|inout)$/.test( qualifier ) ) {

				i ++;

			} else {

				qualifier = null;

			}

			const type = tokens[ i ++ ].str;
			const name = tokens[ i ++ ].str;

			params.push( new FunctionParameter( type, name, qualifier, immutable ) );

			if ( tokens[ i ] && tokens[ i ].str !== ',' ) throw new Error( 'Expected ","' );

		}

		return params;

	}

	parseFunction() {

		const type = this.readToken().str;
		const name = this.readToken().str;

		const paramsTokens = this.readTokensUntil( ')' );

		const params = this.parseFunctionParams( paramsTokens.slice( 1, paramsTokens.length - 1 ) );
		const body = this.parseBlock();

		const func = new FunctionDeclaration( type, name, params, body );

		return func;

	}

	parseVariablesFromToken( tokens, type ) {

		let index = 0;
		const immutable = tokens[ 0 ].str === 'const';

		if ( immutable ) index ++;

		type = type || tokens[ index ++ ].str;
		const name = tokens[ index ++ ].str;

		const token = tokens[ index ];

		let init = null;
		let next = null;

		if ( token ) {

			const initTokens = this.getTokensUntil( ',', tokens, index );

			if ( initTokens[ 0 ].str === '=' ) {

				const expressionTokens = initTokens.slice( 1 );
				if ( expressionTokens[ expressionTokens.length - 1 ].str === ',' ) expressionTokens.pop();

				init = this.parseExpressionFromTokens( expressionTokens );

			}

			const nextTokens = tokens.slice( initTokens.length + ( index - 1 ) );

			if ( nextTokens[ 0 ] && nextTokens[ 0 ].str === ',' ) {

				next = this.parseVariablesFromToken( nextTokens.slice( 1 ), type );

			}

		}

		const variable = new VariableDeclaration( type, name, init, next, immutable );

		return variable;

	}

	parseVariables() {

		const tokens = this.readTokensUntil( ';' );

		return this.parseVariablesFromToken( tokens.slice( 0, tokens.length - 1 ) );

	}

	parseUniform() {

		const tokens = this.readTokensUntil( ';' );

		let type = tokens[ 1 ].str;
		const name = tokens[ 2 ].str;

		// GLSL to TSL types

		if ( samplers.includes( type ) ) type = 'texture';
		else if ( samplersCube.includes( type ) ) type = 'cubeTexture';
		else if ( samplers3D.includes( type ) ) type = 'texture3D';

		return new Uniform( type, name );

	}

	parseVarying() {

		const tokens = this.readTokensUntil( ';' );

		const type = tokens[ 1 ].str;
		const name = tokens[ 2 ].str;

		return new Varying( type, name );

	}

	parseReturn() {

		this.readToken(); // skip 'return'

		const expression = this.parseExpression();

		return new Return( expression );

	}

	parseWhile() {

		this.readToken(); // skip 'while'

		const conditionTokens = this.readTokensUntil( ')' ).slice( 1, - 1 );
		const condition = this.parseExpressionFromTokens( conditionTokens );

		let body;

		if ( this.getToken().str === '{' ) {

			body = this.parseBlock();

		} else {

			body = [ this.parseExpression() ];

		}

		const statement = new While( condition, body );

		return statement;

	}

	parseFor() {

		this.readToken(); // skip 'for'

		const forTokens = this.readTokensUntil( ')' ).slice( 1, - 1 );

		const initializationTokens = this.getTokensUntil( ';', forTokens, 0 ).slice( 0, - 1 );
		const conditionTokens = this.getTokensUntil( ';', forTokens, initializationTokens.length + 1 ).slice( 0, - 1 );
		const afterthoughtTokens = forTokens.slice( initializationTokens.length + conditionTokens.length + 2 );

		let initialization;

		if ( initializationTokens[ 0 ] && isType( initializationTokens[ 0 ].str ) ) {

			initialization = this.parseVariablesFromToken( initializationTokens );

		} else {

			initialization = this.parseExpressionFromTokens( initializationTokens );

		}

		const condition = this.parseExpressionFromTokens( conditionTokens );
		const afterthought = this.parseExpressionFromTokens( afterthoughtTokens );

		let body;

		if ( this.getToken().str === '{' ) {

			body = this.parseBlock();

		} else {

			body = [ this.parseExpression() ];

		}

		const statement = new For( initialization, condition, afterthought, body );

		return statement;

	}

	parseSwitch() {

		this.readToken(); // Skip 'switch'

		const switchDeterminantTokens = this.readTokensUntil( ')' );

		// Parse expression between parentheses. Index 1: char after '('. Index -1: char before ')'
		const discriminant = this.parseExpressionFromTokens( switchDeterminantTokens.slice( 1, - 1 ) );

		// Validate curly braces
		if ( this.getToken().str !== '{' ) {

			throw new Error( 'Expected \'{\' after switch(...) ' );

		}

		this.readToken(); // Skip '{'

		const cases = this.parseSwitchCases();

		const switchStatement = new Switch( discriminant, cases );

		return switchStatement;

	}

	parseSwitchCases() {

		const cases = [];

		let token = this.getToken();
		let conditions = null;

		const isCase = ( token ) => token.str === 'case' || token.str === 'default';

		while ( isCase( token ) ) {

			this.readToken(); // Skip 'case' or 'default'

			if ( token.str === 'case' ) {

				const caseTokens = this.readTokensUntil( ':' );
				const caseStatement = this.parseExpressionFromTokens( caseTokens.slice( 0, - 1 ) );

				conditions = conditions || [];
				conditions.push( caseStatement );

			} else {

				this.readTokensUntil( ':' ); // Skip 'default:'

				conditions = null;

			}

			token = this.getToken();

			if ( isCase( token ) ) {

				// If the next token is another case/default, continue parsing
				continue;

			}

			cases.push( new SwitchCase( this.parseBlock(), conditions ) );

			token = this.getToken();

			conditions = null;

		}

		return cases;

	}

	parseIf() {

		const parseIfExpression = () => {

			this.readToken(); // skip 'if'

			const condTokens = this.readTokensUntil( ')' );

			return this.parseExpressionFromTokens( condTokens.slice( 1, condTokens.length - 1 ) );

		};

		const parseIfBlock = () => {

			let body;

			if ( this.getToken().str === '{' ) {

				body = this.parseBlock();

			} else {

				body = [ this.parseExpression() ];

			}

			return body;

		};

		//

		// Parse the first if statement
		const conditional = new Conditional( parseIfExpression(), parseIfBlock() );

		//

		let current = conditional;

		while ( this.getToken() && this.getToken().str === 'else' ) {

			this.readToken(); // skip 'else'

			// Assign the current if/else statement as the previous within the chain of conditionals
			const previous = current;

			let expression = null;

			// If an 'else if' statement, parse the conditional within the if
			if ( this.getToken().str === 'if' ) {

				// Current conditional now equal to next conditional in the chain
				expression = parseIfExpression();

			}

			current = new Conditional( expression, parseIfBlock() );
			current.parent = previous;

			// n - 1 conditional's else statement assigned to new if/else statement
			previous.elseConditional = current;

		}

		return conditional;

	}

	parseBlock() {

		const body = [];

		const firstToken = this.getToken();

		if ( firstToken.str === '{' ) {

			this.readToken(); // skip '{'

		}

		let groupIndex = 0;

		while ( this.index < this.tokens.length ) {

			const token = this.getToken();

			let statement = null;

			groupIndex += getGroupDelta( token.str );

			if ( groupIndex === 0 && ( token.str === 'case' || token.str === 'default' ) ) {

				return body; // switch case or default statement, return body

			} else if ( groupIndex < 0 ) {

				this.readToken(); // skip '}'

				return body;

			}

			//

			if ( token.tags ) {

				let lastStatement = null;

				for ( const tag of token.tags ) {

					if ( tag.type === Token.COMMENT ) {

						const str = tag.str.replace( /\t/g, '' );

						if ( ! lastStatement || lastStatement.isComment !== true ) {

							lastStatement = new Comment( str );
							body.push( lastStatement );

						} else {

							lastStatement.comment += '\n' + str;

						}

					}

				}

			}

			if ( token.isLiteral || token.isOperator ) {

				if ( token.str === 'const' ) {

					statement = this.parseVariables();

				} else if ( token.str === 'uniform' ) {

					statement = this.parseUniform();

				} else if ( token.str === 'varying' ) {

					statement = this.parseVarying();

				} else if ( isType( token.str ) ) {

					if ( this.getToken( 2 ).str === '(' ) {

						statement = this.parseFunction();

					} else {

						statement = this.parseVariables();

					}

				} else if ( token.str === 'return' ) {

					statement = this.parseReturn();

				} else if ( token.str === 'if' ) {

					statement = this.parseIf();

				} else if ( token.str === 'for' ) {

					statement = this.parseFor();

				} else if ( token.str === 'while' ) {

					statement = this.parseWhile();

				} else if ( token.str === 'switch' ) {

					statement = this.parseSwitch();

				} else {

					statement = this.parseExpression();

				}

			}

			if ( statement ) {

				body.push( statement );

			} else {

				this.index ++;

			}

		}

		return body;

	}

	parse( source ) {

		let polyfill = '';

		for ( const keyword of this.keywords ) {

			if ( new RegExp( `(^|\\b)${ keyword.name }($|\\b)`, 'gm' ).test( source ) ) {

				polyfill += keyword.polyfill + '\n';

			}

		}

		if ( polyfill ) {

			polyfill = '// Polyfills\n\n' + polyfill + '\n';

		}

		this.index = 0;
		this.tokenizer = new Tokenizer( polyfill + source ).tokenize();

		const body = this.parseBlock();
		const program = new Program( body );

		return program;


	}

}
```
</details>

#### Methods

##### `addPolyfill(name: any, polyfill: any): this`

<details><summary>Code</summary>

```ts
addPolyfill( name, polyfill ) {

		this.keywords.push( { name, polyfill } );

		return this;

	}
```
</details>

##### `readToken(): any`

<details><summary>Code</summary>

```ts
readToken() {

		return this.tokens[ this.index ++ ];

	}
```
</details>

##### `getToken(offset: number): any`

<details><summary>Code</summary>

```ts
getToken( offset = 0 ) {

		return this.tokens[ this.index + offset ];

	}
```
</details>

##### `getTokensUntil(str: any, tokens: any, offset: number): any[]`

<details><summary>Code</summary>

```ts
getTokensUntil( str, tokens, offset = 0 ) {

		const output = [];

		let groupIndex = 0;

		for ( let i = offset; i < tokens.length; i ++ ) {

			const token = tokens[ i ];

			groupIndex += getGroupDelta( token.str );

			output.push( token );

			if ( groupIndex === 0 && token.str === str ) {

				break;

			}

		}

		return output;

	}
```
</details>

##### `readTokensUntil(str: any): any[]`

<details><summary>Code</summary>

```ts
readTokensUntil( str ) {

		const tokens = this.getTokensUntil( str, this.tokens, this.index );

		this.index += tokens.length;

		return tokens;

	}
```
</details>

##### `parseExpressionFromTokens(tokens: any): any`

<details><summary>Code</summary>

```ts
parseExpressionFromTokens( tokens ) {

		if ( tokens.length === 0 ) return null;

		const firstToken = tokens[ 0 ];
		const lastToken = tokens[ tokens.length - 1 ];

		// precedence operators

		let groupIndex = 0;

		for ( const operator of precedenceOperators ) {

			const parseToken = ( i, inverse = false ) => {

				const token = tokens[ i ];

				groupIndex += getGroupDelta( token.str );

				if ( ! token.isOperator || i === 0 || i === tokens.length - 1 ) return;

				// important for negate operator after arithmetic operator: a * -1, a * -( b )
				if ( inverse && arithmeticOperators.includes( tokens[ i - 1 ].str ) ) {

					return;

				}

				if ( groupIndex === 0 && token.str === operator ) {

					if ( operator === '?' ) {

						const conditionTokens = tokens.slice( 0, i );
						const leftTokens = this.getTokensUntil( ':', tokens, i + 1 ).slice( 0, - 1 );
						const rightTokens = tokens.slice( i + leftTokens.length + 2 );

						const condition = this.parseExpressionFromTokens( conditionTokens );
						const left = this.parseExpressionFromTokens( leftTokens );
						const right = this.parseExpressionFromTokens( rightTokens );

						return new Ternary( condition, left, right );

					} else {

						const left = this.parseExpressionFromTokens( tokens.slice( 0, i ) );
						const right = this.parseExpressionFromTokens( tokens.slice( i + 1, tokens.length ) );

						return new Operator( operator, left, right );

					}

				}

				if ( inverse ) {

					if ( groupIndex > 0 ) {

						return this.parseExpressionFromTokens( tokens.slice( i ) );

					}

				} else {

					if ( groupIndex < 0 ) {

						return this.parseExpressionFromTokens( tokens.slice( 0, i ) );

					}

				}

			};

			if ( associativityRightToLeft.includes( operator ) ) {

				for ( let i = 0; i < tokens.length; i ++ ) {

					const result = parseToken( i );

					if ( result ) return result;

				}

			} else {

				for ( let i = tokens.length - 1; i >= 0; i -- ) {

					const result = parseToken( i, true );

					if ( result ) return result;

				}

			}

		}

		// unary operators (before)

		if ( firstToken.isOperator ) {

			for ( const operator of unaryOperators ) {

				if ( firstToken.str === operator ) {

					const right = this.parseExpressionFromTokens( tokens.slice( 1 ) );

					return new Unary( operator, right );

				}

			}

		}

		// unary operators (after)

		if ( lastToken.isOperator ) {

			for ( const operator of unaryOperators ) {

				if ( lastToken.str === operator ) {

					const left = this.parseExpressionFromTokens( tokens.slice( 0, tokens.length - 1 ) );

					return new Unary( operator, left, true );

				}

			}

		}

		// groups

		if ( firstToken.str === '(' ) {

			const leftTokens = this.getTokensUntil( ')', tokens );

			const left = this.parseExpressionFromTokens( leftTokens.slice( 1, leftTokens.length - 1 ) );

			const operator = tokens[ leftTokens.length ];

			if ( operator ) {

				const rightTokens = tokens.slice( leftTokens.length + 1 );
				const right = this.parseExpressionFromTokens( rightTokens );

				return new Operator( operator.str, left, right );

			}

			return left;

		}

		// primitives and accessors

		if ( firstToken.isNumber ) {

			let type;

			const isHex = /^(0x)/.test( firstToken.str );

			if ( isHex ) type = 'int';
			else if ( /u$|U$/.test( firstToken.str ) ) type = 'uint';
			else if ( /f|e|\./.test( firstToken.str ) ) type = 'float';
			else type = 'int';

			let str = firstToken.str.replace( /u|U|i$/, '' );

			if ( isHex === false ) {

				str = str.replace( /f$/, '' );

			}

			return new Number( str, type );

		} else if ( firstToken.isString ) {

			return new String( firstToken.str );

		} else if ( firstToken.isLiteral ) {

			if ( firstToken.str === 'return' ) {

				return new Return( this.parseExpressionFromTokens( tokens.slice( 1 ) ) );

			} else if ( firstToken.str === 'discard' ) {

				return new Discard();

			} else if ( firstToken.str === 'continue' ) {

				return new Continue();

			} else if ( firstToken.str === 'break' ) {

				return new Break();

			}

			const secondToken = tokens[ 1 ];

			if ( secondToken ) {

				if ( secondToken.str === '(' ) {

					// function call

					const internalTokens = this.getTokensUntil( ')', tokens, 1 ).slice( 1, - 1 );

					const paramsTokens = this.parseFunctionParametersFromTokens( internalTokens );

					const functionCall = new FunctionCall( getFunctionName( firstToken.str ), paramsTokens );

					const accessTokens = tokens.slice( 3 + internalTokens.length );

					if ( accessTokens.length > 0 ) {

						const elements = this.parseAccessorElementsFromTokens( accessTokens );

						return new AccessorElements( functionCall, elements );

					}

					return functionCall;

				} else if ( secondToken.str === '[' ) {

					// array accessor

					const elements = this.parseAccessorElementsFromTokens( tokens.slice( 1 ) );

					return new AccessorElements( new Accessor( firstToken.str ), elements );

				}

			}

			return new Accessor( firstToken.str );

		}

	}
```
</details>

##### `parseAccessorElementsFromTokens(tokens: any): any`

<details><summary>Code</summary>

```ts
parseAccessorElementsFromTokens( tokens ) {

		const elements = [];

		let currentTokens = tokens;

		while ( currentTokens.length > 0 ) {

			const token = currentTokens[ 0 ];

			if ( token.str === '[' ) {

				const accessorTokens = this.getTokensUntil( ']', currentTokens );

				const element = this.parseExpressionFromTokens( accessorTokens.slice( 1, accessorTokens.length - 1 ) );

				currentTokens = currentTokens.slice( accessorTokens.length );

				elements.push( new DynamicElement( element ) );

			} else if ( token.str === '.' ) {

				const accessorTokens = currentTokens.slice( 1, 2 );

				const element = this.parseExpressionFromTokens( accessorTokens );

				currentTokens = currentTokens.slice( 2 );

				elements.push( new StaticElement( element ) );

			} else {

				console.error( 'Unknown accessor expression', token );

				break;

			}

		}

		return elements;

	}
```
</details>

##### `parseFunctionParametersFromTokens(tokens: any): any`

<details><summary>Code</summary>

```ts
parseFunctionParametersFromTokens( tokens ) {

		if ( tokens.length === 0 ) return [];

		const expression = this.parseExpressionFromTokens( tokens );
		const params = [];

		let current = expression;

		while ( current.type === ',' ) {

			params.push( current.left );

			current = current.right;

		}

		params.push( current );

		return params;

	}
```
</details>

##### `parseExpression(): any`

<details><summary>Code</summary>

```ts
parseExpression() {

		const tokens = this.readTokensUntil( ';' );

		const exp = this.parseExpressionFromTokens( tokens.slice( 0, tokens.length - 1 ) );

		return exp;

	}
```
</details>

##### `parseFunctionParams(tokens: any): FunctionParameter[]`

<details><summary>Code</summary>

```ts
parseFunctionParams( tokens ) {

		const params = [];

		for ( let i = 0; i < tokens.length; i ++ ) {

			const immutable = tokens[ i ].str === 'const';
			if ( immutable ) i ++;

			let qualifier = tokens[ i ].str;

			if ( /^(in|out|inout)$/.test( qualifier ) ) {

				i ++;

			} else {

				qualifier = null;

			}

			const type = tokens[ i ++ ].str;
			const name = tokens[ i ++ ].str;

			params.push( new FunctionParameter( type, name, qualifier, immutable ) );

			if ( tokens[ i ] && tokens[ i ].str !== ',' ) throw new Error( 'Expected ","' );

		}

		return params;

	}
```
</details>

##### `parseFunction(): any`

<details><summary>Code</summary>

```ts
parseFunction() {

		const type = this.readToken().str;
		const name = this.readToken().str;

		const paramsTokens = this.readTokensUntil( ')' );

		const params = this.parseFunctionParams( paramsTokens.slice( 1, paramsTokens.length - 1 ) );
		const body = this.parseBlock();

		const func = new FunctionDeclaration( type, name, params, body );

		return func;

	}
```
</details>

##### `parseVariablesFromToken(tokens: any, type: any): any`

<details><summary>Code</summary>

```ts
parseVariablesFromToken( tokens, type ) {

		let index = 0;
		const immutable = tokens[ 0 ].str === 'const';

		if ( immutable ) index ++;

		type = type || tokens[ index ++ ].str;
		const name = tokens[ index ++ ].str;

		const token = tokens[ index ];

		let init = null;
		let next = null;

		if ( token ) {

			const initTokens = this.getTokensUntil( ',', tokens, index );

			if ( initTokens[ 0 ].str === '=' ) {

				const expressionTokens = initTokens.slice( 1 );
				if ( expressionTokens[ expressionTokens.length - 1 ].str === ',' ) expressionTokens.pop();

				init = this.parseExpressionFromTokens( expressionTokens );

			}

			const nextTokens = tokens.slice( initTokens.length + ( index - 1 ) );

			if ( nextTokens[ 0 ] && nextTokens[ 0 ].str === ',' ) {

				next = this.parseVariablesFromToken( nextTokens.slice( 1 ), type );

			}

		}

		const variable = new VariableDeclaration( type, name, init, next, immutable );

		return variable;

	}
```
</details>

##### `parseVariables(): any`

<details><summary>Code</summary>

```ts
parseVariables() {

		const tokens = this.readTokensUntil( ';' );

		return this.parseVariablesFromToken( tokens.slice( 0, tokens.length - 1 ) );

	}
```
</details>

##### `parseUniform(): Uniform`

<details><summary>Code</summary>

```ts
parseUniform() {

		const tokens = this.readTokensUntil( ';' );

		let type = tokens[ 1 ].str;
		const name = tokens[ 2 ].str;

		// GLSL to TSL types

		if ( samplers.includes( type ) ) type = 'texture';
		else if ( samplersCube.includes( type ) ) type = 'cubeTexture';
		else if ( samplers3D.includes( type ) ) type = 'texture3D';

		return new Uniform( type, name );

	}
```
</details>

##### `parseVarying(): Varying`

<details><summary>Code</summary>

```ts
parseVarying() {

		const tokens = this.readTokensUntil( ';' );

		const type = tokens[ 1 ].str;
		const name = tokens[ 2 ].str;

		return new Varying( type, name );

	}
```
</details>

##### `parseReturn(): Return`

<details><summary>Code</summary>

```ts
parseReturn() {

		this.readToken(); // skip 'return'

		const expression = this.parseExpression();

		return new Return( expression );

	}
```
</details>

##### `parseWhile(): any`

<details><summary>Code</summary>

```ts
parseWhile() {

		this.readToken(); // skip 'while'

		const conditionTokens = this.readTokensUntil( ')' ).slice( 1, - 1 );
		const condition = this.parseExpressionFromTokens( conditionTokens );

		let body;

		if ( this.getToken().str === '{' ) {

			body = this.parseBlock();

		} else {

			body = [ this.parseExpression() ];

		}

		const statement = new While( condition, body );

		return statement;

	}
```
</details>

##### `parseFor(): any`

<details><summary>Code</summary>

```ts
parseFor() {

		this.readToken(); // skip 'for'

		const forTokens = this.readTokensUntil( ')' ).slice( 1, - 1 );

		const initializationTokens = this.getTokensUntil( ';', forTokens, 0 ).slice( 0, - 1 );
		const conditionTokens = this.getTokensUntil( ';', forTokens, initializationTokens.length + 1 ).slice( 0, - 1 );
		const afterthoughtTokens = forTokens.slice( initializationTokens.length + conditionTokens.length + 2 );

		let initialization;

		if ( initializationTokens[ 0 ] && isType( initializationTokens[ 0 ].str ) ) {

			initialization = this.parseVariablesFromToken( initializationTokens );

		} else {

			initialization = this.parseExpressionFromTokens( initializationTokens );

		}

		const condition = this.parseExpressionFromTokens( conditionTokens );
		const afterthought = this.parseExpressionFromTokens( afterthoughtTokens );

		let body;

		if ( this.getToken().str === '{' ) {

			body = this.parseBlock();

		} else {

			body = [ this.parseExpression() ];

		}

		const statement = new For( initialization, condition, afterthought, body );

		return statement;

	}
```
</details>

##### `parseSwitch(): any`

<details><summary>Code</summary>

```ts
parseSwitch() {

		this.readToken(); // Skip 'switch'

		const switchDeterminantTokens = this.readTokensUntil( ')' );

		// Parse expression between parentheses. Index 1: char after '('. Index -1: char before ')'
		const discriminant = this.parseExpressionFromTokens( switchDeterminantTokens.slice( 1, - 1 ) );

		// Validate curly braces
		if ( this.getToken().str !== '{' ) {

			throw new Error( 'Expected \'{\' after switch(...) ' );

		}

		this.readToken(); // Skip '{'

		const cases = this.parseSwitchCases();

		const switchStatement = new Switch( discriminant, cases );

		return switchStatement;

	}
```
</details>

##### `parseSwitchCases(): any`

<details><summary>Code</summary>

```ts
parseSwitchCases() {

		const cases = [];

		let token = this.getToken();
		let conditions = null;

		const isCase = ( token ) => token.str === 'case' || token.str === 'default';

		while ( isCase( token ) ) {

			this.readToken(); // Skip 'case' or 'default'

			if ( token.str === 'case' ) {

				const caseTokens = this.readTokensUntil( ':' );
				const caseStatement = this.parseExpressionFromTokens( caseTokens.slice( 0, - 1 ) );

				conditions = conditions || [];
				conditions.push( caseStatement );

			} else {

				this.readTokensUntil( ':' ); // Skip 'default:'

				conditions = null;

			}

			token = this.getToken();

			if ( isCase( token ) ) {

				// If the next token is another case/default, continue parsing
				continue;

			}

			cases.push( new SwitchCase( this.parseBlock(), conditions ) );

			token = this.getToken();

			conditions = null;

		}

		return cases;

	}
```
</details>

##### `parseIf(): any`

<details><summary>Code</summary>

```ts
parseIf() {

		const parseIfExpression = () => {

			this.readToken(); // skip 'if'

			const condTokens = this.readTokensUntil( ')' );

			return this.parseExpressionFromTokens( condTokens.slice( 1, condTokens.length - 1 ) );

		};

		const parseIfBlock = () => {

			let body;

			if ( this.getToken().str === '{' ) {

				body = this.parseBlock();

			} else {

				body = [ this.parseExpression() ];

			}

			return body;

		};

		//

		// Parse the first if statement
		const conditional = new Conditional( parseIfExpression(), parseIfBlock() );

		//

		let current = conditional;

		while ( this.getToken() && this.getToken().str === 'else' ) {

			this.readToken(); // skip 'else'

			// Assign the current if/else statement as the previous within the chain of conditionals
			const previous = current;

			let expression = null;

			// If an 'else if' statement, parse the conditional within the if
			if ( this.getToken().str === 'if' ) {

				// Current conditional now equal to next conditional in the chain
				expression = parseIfExpression();

			}

			current = new Conditional( expression, parseIfBlock() );
			current.parent = previous;

			// n - 1 conditional's else statement assigned to new if/else statement
			previous.elseConditional = current;

		}

		return conditional;

	}
```
</details>

##### `parseBlock(): any`

<details><summary>Code</summary>

```ts
parseBlock() {

		const body = [];

		const firstToken = this.getToken();

		if ( firstToken.str === '{' ) {

			this.readToken(); // skip '{'

		}

		let groupIndex = 0;

		while ( this.index < this.tokens.length ) {

			const token = this.getToken();

			let statement = null;

			groupIndex += getGroupDelta( token.str );

			if ( groupIndex === 0 && ( token.str === 'case' || token.str === 'default' ) ) {

				return body; // switch case or default statement, return body

			} else if ( groupIndex < 0 ) {

				this.readToken(); // skip '}'

				return body;

			}

			//

			if ( token.tags ) {

				let lastStatement = null;

				for ( const tag of token.tags ) {

					if ( tag.type === Token.COMMENT ) {

						const str = tag.str.replace( /\t/g, '' );

						if ( ! lastStatement || lastStatement.isComment !== true ) {

							lastStatement = new Comment( str );
							body.push( lastStatement );

						} else {

							lastStatement.comment += '\n' + str;

						}

					}

				}

			}

			if ( token.isLiteral || token.isOperator ) {

				if ( token.str === 'const' ) {

					statement = this.parseVariables();

				} else if ( token.str === 'uniform' ) {

					statement = this.parseUniform();

				} else if ( token.str === 'varying' ) {

					statement = this.parseVarying();

				} else if ( isType( token.str ) ) {

					if ( this.getToken( 2 ).str === '(' ) {

						statement = this.parseFunction();

					} else {

						statement = this.parseVariables();

					}

				} else if ( token.str === 'return' ) {

					statement = this.parseReturn();

				} else if ( token.str === 'if' ) {

					statement = this.parseIf();

				} else if ( token.str === 'for' ) {

					statement = this.parseFor();

				} else if ( token.str === 'while' ) {

					statement = this.parseWhile();

				} else if ( token.str === 'switch' ) {

					statement = this.parseSwitch();

				} else {

					statement = this.parseExpression();

				}

			}

			if ( statement ) {

				body.push( statement );

			} else {

				this.index ++;

			}

		}

		return body;

	}
```
</details>

##### `parse(source: any): Program`

<details><summary>Code</summary>

```ts
parse( source ) {

		let polyfill = '';

		for ( const keyword of this.keywords ) {

			if ( new RegExp( `(^|\\b)${ keyword.name }($|\\b)`, 'gm' ).test( source ) ) {

				polyfill += keyword.polyfill + '\n';

			}

		}

		if ( polyfill ) {

			polyfill = '// Polyfills\n\n' + polyfill + '\n';

		}

		this.index = 0;
		this.tokenizer = new Tokenizer( polyfill + source ).tokenize();

		const body = this.parseBlock();
		const program = new Program( body );

		return program;


	}
```
</details>


---