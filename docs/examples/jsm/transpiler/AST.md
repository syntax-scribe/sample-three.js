[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AST.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 28 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/transpiler/AST.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `toFloatType` | `./TranspilerUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `array` | `this[Extract<keyof this, string>] & a...` | let/var | `this[ key ]` | ✗ |


---

## Functions

### `ASTNode.getType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getType() {

		return this.type || null;

	}
```
</details>

### `ASTNode.getParent(parents: any[]): any`

**Parameters:**

- **`parents`** `any[]`

**Returns:** `any`

**Calls:**

- `parents.push`
- `this.parent.getParent`

<details><summary>Code</summary>

```typescript
getParent( parents = [] ) {

		if ( this.parent === null ) {

			return parents;

		}

		parents.push( this.parent );

		return this.parent.getParent( parents );

	}
```
</details>

### `ASTNode.initialize(): void`

**Returns:** `void`

**Calls:**

- `Array.isArray`

<details><summary>Code</summary>

```typescript
initialize() {

		for ( const key in this ) {

			if ( this[ key ] && this[ key ].isASTNode ) {

				this[ key ].parent = this;

			} else if ( Array.isArray( this[ key ] ) ) {

				const array = this[ key ];

				for ( const item of array ) {

					if ( item && item.isASTNode ) {

						item.parent = this;

					}

				}

			}

		}

	}
```
</details>

### `Operator.getType(): any`

**Returns:** `any`

**Calls:**

- `this.left.getType`
- `this.right.getType`
- `toFloatType (from ./TranspilerUtils.js)`

<details><summary>Code</summary>

```typescript
getType() {

		const leftType = this.left.getType();
		const rightType = this.right.getType();

		if ( leftType === rightType ) {

			return leftType;

		} else if ( toFloatType( leftType ) === toFloatType( rightType ) ) {

			return toFloatType( leftType );

		}

		return null;

	}
```
</details>

### `Accessor.getType(): any`

**Returns:** `any`

**Calls:**

- `this.linker.reference.getType`
- `super.getType`

<details><summary>Code</summary>

```typescript
getType() {

		if ( this.linker.reference ) {

			return this.linker.reference.getType();

		}

		return super.getType();

	}
```
</details>


---

## Classes

### `ASTNode`

<details><summary>Class Code</summary>

```ts
export class ASTNode {

	constructor() {

		this.isASTNode = true;

		this.linker = {
			reference: null,
			accesses: [],
			assignments: []
		};

		this.parent = null;

	}

	get isNumericExpression() {

		return false;

	}

	get hasAssignment() {

		if ( this.isAssignment === true ) {

			return true;

		}

		if ( this.parent === null ) {

			return false;

		}

		return this.parent.hasAssignment;

	}

	getType() {

		return this.type || null;

	}

	getParent( parents = [] ) {

		if ( this.parent === null ) {

			return parents;

		}

		parents.push( this.parent );

		return this.parent.getParent( parents );

	}

	initialize() {

		for ( const key in this ) {

			if ( this[ key ] && this[ key ].isASTNode ) {

				this[ key ].parent = this;

			} else if ( Array.isArray( this[ key ] ) ) {

				const array = this[ key ];

				for ( const item of array ) {

					if ( item && item.isASTNode ) {

						item.parent = this;

					}

				}

			}

		}

	}

}
```
</details>

#### Methods

##### `getType(): any`

<details><summary>Code</summary>

```ts
getType() {

		return this.type || null;

	}
```
</details>

##### `getParent(parents: any[]): any`

<details><summary>Code</summary>

```ts
getParent( parents = [] ) {

		if ( this.parent === null ) {

			return parents;

		}

		parents.push( this.parent );

		return this.parent.getParent( parents );

	}
```
</details>

##### `initialize(): void`

<details><summary>Code</summary>

```ts
initialize() {

		for ( const key in this ) {

			if ( this[ key ] && this[ key ].isASTNode ) {

				this[ key ].parent = this;

			} else if ( Array.isArray( this[ key ] ) ) {

				const array = this[ key ];

				for ( const item of array ) {

					if ( item && item.isASTNode ) {

						item.parent = this;

					}

				}

			}

		}

	}
```
</details>

### `Comment`

<details><summary>Class Code</summary>

```ts
export class Comment extends ASTNode {

	constructor( comment ) {

		super();

		this.comment = comment;

		this.isComment = true;

		this.initialize();

	}

}
```
</details>

### `Program`

<details><summary>Class Code</summary>

```ts
export class Program extends ASTNode {

	constructor( body = [] ) {

		super();

		this.body = body;

		this.isProgram = true;

		this.initialize();

	}

}
```
</details>

### `VariableDeclaration`

<details><summary>Class Code</summary>

```ts
export class VariableDeclaration extends ASTNode {

	constructor( type, name, value = null, next = null, immutable = false ) {

		super();

		this.type = type;
		this.name = name;
		this.value = value;
		this.next = next;

		this.immutable = immutable;

		this.isVariableDeclaration = true;

		this.initialize();

	}

	get isAssignment() {

		return this.value !== null;

	}

}
```
</details>

### `Uniform`

<details><summary>Class Code</summary>

```ts
export class Uniform extends ASTNode {

	constructor( type, name ) {

		super();

		this.type = type;
		this.name = name;

		this.isUniform = true;

		this.initialize();

	}

}
```
</details>

### `Varying`

<details><summary>Class Code</summary>

```ts
export class Varying extends ASTNode {

	constructor( type, name ) {

		super();

		this.type = type;
		this.name = name;

		this.isVarying = true;

		this.initialize();

	}

}
```
</details>

### `FunctionParameter`

<details><summary>Class Code</summary>

```ts
export class FunctionParameter extends ASTNode {

	constructor( type, name, qualifier = null, immutable = true ) {

		super();

		this.type = type;
		this.name = name;
		this.qualifier = qualifier;
		this.immutable = immutable;

		this.isFunctionParameter = true;

		this.initialize();

	}

}
```
</details>

### `FunctionDeclaration`

<details><summary>Class Code</summary>

```ts
export class FunctionDeclaration extends ASTNode {

	constructor( type, name, params = [], body = [] ) {

		super();

		this.type = type;
		this.name = name;
		this.params = params;
		this.body = body;

		this.isFunctionDeclaration = true;

		this.initialize();

	}

}
```
</details>

### `Expression`

<details><summary>Class Code</summary>

```ts
export class Expression extends ASTNode {

	constructor( expression ) {

		super();

		this.expression = expression;

		this.isExpression = true;

		this.initialize();

	}

}
```
</details>

### `Ternary`

<details><summary>Class Code</summary>

```ts
export class Ternary extends ASTNode {

	constructor( cond, left, right ) {

		super();

		this.cond = cond;
		this.left = left;
		this.right = right;

		this.isTernary = true;

		this.initialize();

	}

}
```
</details>

### `Operator`

<details><summary>Class Code</summary>

```ts
export class Operator extends ASTNode {

	constructor( type, left, right ) {

		super();

		this.type = type;
		this.left = left;
		this.right = right;

		this.isOperator = true;

		this.initialize();

	}

	get isAssignment() {

		return /^(=|\+=|-=|\*=|\/=|%=|<<=|>>=|>>>=|&=|\^=|\|=)$/.test( this.type );

	}

	get isNumericExpression() {

		if ( this.left.isNumericExpression && this.right.isNumericExpression ) {

			return true;

		}

		return false;

	}

	getType() {

		const leftType = this.left.getType();
		const rightType = this.right.getType();

		if ( leftType === rightType ) {

			return leftType;

		} else if ( toFloatType( leftType ) === toFloatType( rightType ) ) {

			return toFloatType( leftType );

		}

		return null;

	}

}
```
</details>

#### Methods

##### `getType(): any`

<details><summary>Code</summary>

```ts
getType() {

		const leftType = this.left.getType();
		const rightType = this.right.getType();

		if ( leftType === rightType ) {

			return leftType;

		} else if ( toFloatType( leftType ) === toFloatType( rightType ) ) {

			return toFloatType( leftType );

		}

		return null;

	}
```
</details>

### `Unary`

<details><summary>Class Code</summary>

```ts
export class Unary extends ASTNode {

	constructor( type, expression, after = false ) {

		super();

		this.type = type;
		this.expression = expression;
		this.after = after;

		this.isUnary = true;

		this.initialize();

	}

	get isAssignment() {

		return /^(\+\+|--)$/.test( this.type );

	}

	get isNumericExpression() {

		if ( this.expression.isNumber ) {

			return true;

		}

		return false;

	}

}
```
</details>

### `Number`

<details><summary>Class Code</summary>

```ts
export class Number extends ASTNode {

	constructor( value, type = 'float' ) {

		super();

		this.type = type;
		this.value = value;

		this.isNumber = true;

		this.initialize();

	}

	get isNumericExpression() {

		return true;

	}

}
```
</details>

### `String`

<details><summary>Class Code</summary>

```ts
export class String extends ASTNode {

	constructor( value ) {

		super();

		this.value = value;

		this.isString = true;

		this.initialize();

	}

}
```
</details>

### `Conditional`

<details><summary>Class Code</summary>

```ts
export class Conditional extends ASTNode {

	constructor( cond = null, body = [] ) {

		super();

		this.cond = cond;
		this.body = body;
		this.elseConditional = null;

		this.isConditional = true;

		this.initialize();

	}

}
```
</details>

### `FunctionCall`

<details><summary>Class Code</summary>

```ts
export class FunctionCall extends ASTNode {

	constructor( name, params = [] ) {

		super();

		this.name = name;
		this.params = params;

		this.isFunctionCall = true;

		this.initialize();

	}

}
```
</details>

### `Return`

<details><summary>Class Code</summary>

```ts
export class Return extends ASTNode {

	constructor( value ) {

		super();

		this.value = value;

		this.isReturn = true;

		this.initialize();

	}

}
```
</details>

### `Discard`

<details><summary>Class Code</summary>

```ts
export class Discard extends ASTNode {

	constructor() {

		super();

		this.isDiscard = true;

		this.initialize();

	}

}
```
</details>

### `Continue`

<details><summary>Class Code</summary>

```ts
export class Continue extends ASTNode {

	constructor() {

		super();

		this.isContinue = true;

		this.initialize();

	}

}
```
</details>

### `Break`

<details><summary>Class Code</summary>

```ts
export class Break extends ASTNode {

	constructor() {

		super();

		this.isBreak = true;

		this.initialize();

	}

}
```
</details>

### `Accessor`

<details><summary>Class Code</summary>

```ts
export class Accessor extends ASTNode {

	constructor( property ) {

		super();

		this.property = property;

		this.isAccessor = true;

		this.initialize();

	}

	getType() {

		if ( this.linker.reference ) {

			return this.linker.reference.getType();

		}

		return super.getType();

	}

}
```
</details>

#### Methods

##### `getType(): any`

<details><summary>Code</summary>

```ts
getType() {

		if ( this.linker.reference ) {

			return this.linker.reference.getType();

		}

		return super.getType();

	}
```
</details>

### `StaticElement`

<details><summary>Class Code</summary>

```ts
export class StaticElement extends ASTNode {

	constructor( value ) {

		super();

		this.value = value;

		this.isStaticElement = true;

		this.initialize();

	}

}
```
</details>

### `DynamicElement`

<details><summary>Class Code</summary>

```ts
export class DynamicElement extends ASTNode {

	constructor( value ) {

		super();

		this.value = value;

		this.isDynamicElement = true;

		this.initialize();

	}

}
```
</details>

### `AccessorElements`

<details><summary>Class Code</summary>

```ts
export class AccessorElements extends ASTNode {

	constructor( object, elements = [] ) {

		super();

		this.object = object;
		this.elements = elements;

		this.isAccessorElements = true;

		this.initialize();

	}

}
```
</details>

### `For`

<details><summary>Class Code</summary>

```ts
export class For extends ASTNode {

	constructor( initialization, condition, afterthought, body = [] ) {

		super();

		this.initialization = initialization;
		this.condition = condition;
		this.afterthought = afterthought;
		this.body = body;

		this.isFor = true;

		this.initialize();

	}

}
```
</details>

### `While`

<details><summary>Class Code</summary>

```ts
export class While extends ASTNode {

	constructor( condition, body = [] ) {

		super();

		this.condition = condition;
		this.body = body;

		this.isWhile = true;

		this.initialize();

	}

}
```
</details>

### `Switch`

<details><summary>Class Code</summary>

```ts
export class Switch extends ASTNode {

	constructor( discriminant, cases ) {

		super();

		this.discriminant = discriminant;
		this.cases = cases;

		this.isSwitch = true;

		this.initialize();

	}

}
```
</details>

### `SwitchCase`

<details><summary>Class Code</summary>

```ts
export class SwitchCase extends ASTNode {

	constructor( body, conditions = null ) {

		super();

		this.body = body;
		this.conditions = conditions;

		this.isDefault = conditions === null ? true : false;
		this.isSwitchCase = true;

		this.initialize();

	}

}
```
</details>


---