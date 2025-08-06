[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Linker.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/transpiler/Linker.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `value` | `any` | let/var | `this.properties[ name ]` | ✗ |
| `property` | `string` | let/var | `''` | ✗ |
| `current` | `any` | let/var | `node` | ✗ |


---

## Functions

### `Block.setProperty(name: any, value: any): void`

**Parameters:**

- **`name`** `any`
- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setProperty( name, value ) {

		this.properties[ name ] = value;

	}
```
</details>

### `Block.getProperty(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.parent.getProperty`

<details><summary>Code</summary>

```typescript
getProperty( name ) {

		let value = this.properties[ name ];

		if ( value === undefined && this.parent !== null ) {

			value = this.parent.getProperty( name );

		}

		return value;

	}
```
</details>

### `Linker.addBlock(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
addBlock( node ) {

		this.block = new Block( node, this.block );

	}
```
</details>

### `Linker.removeBlock(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
removeBlock( node ) {

		if ( this.block === null || this.block.node !== node ) {

			throw new Error( 'No block to remove or block mismatch.' );

		}

		this.block = this.block.parent;

	}
```
</details>

### `Linker.processVariables(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.block.setProperty`
- `this.processExpression`

<details><summary>Code</summary>

```typescript
processVariables( node ) {

		this.block.setProperty( node.name, node );

		if ( node.value ) {

			this.processExpression( node.value );

		}

	}
```
</details>

### `Linker.processUniform(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.block.setProperty`

<details><summary>Code</summary>

```typescript
processUniform( node ) {

		this.block.setProperty( node.name, node );

	}
```
</details>

### `Linker.processVarying(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.block.setProperty`

<details><summary>Code</summary>

```typescript
processVarying( node ) {

		this.block.setProperty( node.name, node );

	}
```
</details>

### `Linker.evalProperty(node: any): string`

**Parameters:**

- **`node`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
evalProperty( node ) {

		let property = '';

		if ( node.isAccessor ) {

			property += node.property;

		}

		return property;

	}
```
</details>

### `Linker.processExpression(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.block.getProperty`
- `this.evalProperty`
- `property.linker.accesses.push`
- `this.processExpression`
- `property.linker.assignments.push`
- `this.processForWhile`
- `this.processSwitch`
- `this.processVariables`
- `this.processUniform`
- `this.processVarying`
- `this.processConditional`

**Internal Comments:**
```
// optimize increment/decrement operator (x4)
// to avoid creating a new variable (x4)
```

<details><summary>Code</summary>

```typescript
processExpression( node ) {

		if ( node.isAccessor ) {

			const property = this.block.getProperty( this.evalProperty( node ) );

			if ( property ) {

				node.linker.reference = property;

				property.linker.accesses.push( node );

			}

		} else if ( node.isNumber || node.isString ) {

			// Process primitive values

		} else if ( node.isOperator ) {

			this.processExpression( node.left );
			this.processExpression( node.right );

			if ( node.isAssignment ) {

				const property = this.block.getProperty( this.evalProperty( node.left ) );

				if ( property ) {

					property.linker.assignments.push( node );

				}

			}

		} else if ( node.isFunctionCall ) {

			for ( const param of node.params ) {

				this.processExpression( param );

			}

		} else if ( node.isReturn ) {

			if ( node.value ) this.processExpression( node.value );

		} else if ( node.isDiscard || node.isBreak || node.isContinue ) {

			// Process control flow

		} else if ( node.isAccessorElements ) {

			this.processExpression( node.object );

			for ( const element of node.elements ) {

				this.processExpression( element.value );

			}

		} else if ( node.isDynamicElement || node.isStaticElement ) {

			this.processExpression( node.value );

		} else if ( node.isFor || node.isWhile ) {

			this.processForWhile( node );

		} else if ( node.isSwitch ) {

			this.processSwitch( node );

		} else if ( node.isVariableDeclaration ) {

			this.processVariables( node );

		} else if ( node.isUniform ) {

			this.processUniform( node );

		} else if ( node.isVarying ) {

			this.processVarying( node );

		} else if ( node.isTernary ) {

			this.processExpression( node.cond );
			this.processExpression( node.left );
			this.processExpression( node.right );

		} else if ( node.isConditional ) {

			this.processConditional( node );

		} else if ( node.isUnary ) {

			this.processExpression( node.expression );

			if ( node.isAssignment ) {

				if ( node.parent.hasAssignment !== true ) {

					// optimize increment/decrement operator
					// to avoid creating a new variable

					node.after = false;

				}

				const property = this.block.getProperty( this.evalProperty( node.expression ) );

				if ( property ) {

					property.linker.assignments.push( node );

				}

			}

		}

	}
```
</details>

### `Linker.processBody(body: any): void`

**Parameters:**

- **`body`** `any`

**Returns:** `void`

**Calls:**

- `this.processExpression`

<details><summary>Code</summary>

```typescript
processBody( body ) {

		for ( const statement of body ) {

			this.processExpression( statement );

		}

	}
```
</details>

### `Linker.processConditional(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.processExpression`
- `this.processBody`

<details><summary>Code</summary>

```typescript
processConditional( node ) {

		this.processExpression( node.cond );
		this.processBody( node.body );

		let current = node;

		while ( current.elseConditional ) {

			if ( current.elseConditional.cond ) {

				this.processExpression( current.elseConditional.cond );

			}

			this.processBody( current.elseConditional.body );

			current = current.elseConditional;

		}

	}
```
</details>

### `Linker.processForWhile(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.processExpression`
- `this.processBody`

<details><summary>Code</summary>

```typescript
processForWhile( node ) {

		if ( node.initialization ) this.processExpression( node.initialization );
		if ( node.condition ) this.processExpression( node.condition );
		if ( node.afterthought ) this.processExpression( node.afterthought );

		this.processBody( node.body );

	}
```
</details>

### `Linker.processSwitch(switchNode: any): void`

**Parameters:**

- **`switchNode`** `any`

**Returns:** `void`

**Calls:**

- `this.processExpression`
- `this.processBody`

<details><summary>Code</summary>

```typescript
processSwitch( switchNode ) {

		this.processExpression( switchNode.discriminant );

		for ( const switchCase of switchNode.cases ) {

			if ( switchCase.isDefault !== true ) {

				for ( const condition of switchCase.conditions ) {

					this.processExpression( condition );

				}

			}

			this.processBody( switchCase.body );

		}

	}
```
</details>

### `Linker.processFunction(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.addBlock`
- `this.block.setProperty`
- `this.processBody`
- `this.removeBlock`

<details><summary>Code</summary>

```typescript
processFunction( node ) {

		this.addBlock( node );

		for ( const param of node.params ) {

			this.block.setProperty( param.name, param );

		}

		this.processBody( node.body );

		this.removeBlock( node );

	}
```
</details>

### `Linker.process(ast: any): void`

**Parameters:**

- **`ast`** `any`

**Returns:** `void`

**Calls:**

- `this.addBlock`
- `this.processFunction`
- `this.processExpression`
- `this.removeBlock`

<details><summary>Code</summary>

```typescript
process( ast ) {

		this.addBlock( ast );

		for ( const statement of ast.body ) {

			if ( statement.isFunctionDeclaration ) {

				this.processFunction( statement );

			} else {

				this.processExpression( statement );

			}

		}

		this.removeBlock( ast );

	}
```
</details>


---

## Classes

### `Block`

<details><summary>Class Code</summary>

```ts
class Block {

	constructor( node, parent = null ) {

		this.node = node;
		this.parent = parent;

		this.properties = {};

	}

	setProperty( name, value ) {

		this.properties[ name ] = value;

	}

	getProperty( name ) {

		let value = this.properties[ name ];

		if ( value === undefined && this.parent !== null ) {

			value = this.parent.getProperty( name );

		}

		return value;

	}

}
```
</details>

#### Methods

##### `setProperty(name: any, value: any): void`

<details><summary>Code</summary>

```ts
setProperty( name, value ) {

		this.properties[ name ] = value;

	}
```
</details>

##### `getProperty(name: any): any`

<details><summary>Code</summary>

```ts
getProperty( name ) {

		let value = this.properties[ name ];

		if ( value === undefined && this.parent !== null ) {

			value = this.parent.getProperty( name );

		}

		return value;

	}
```
</details>

### `Linker`

<details><summary>Class Code</summary>

```ts
class Linker {

	constructor() {

		this.block = null;

	}

	addBlock( node ) {

		this.block = new Block( node, this.block );

	}

	removeBlock( node ) {

		if ( this.block === null || this.block.node !== node ) {

			throw new Error( 'No block to remove or block mismatch.' );

		}

		this.block = this.block.parent;

	}

	processVariables( node ) {

		this.block.setProperty( node.name, node );

		if ( node.value ) {

			this.processExpression( node.value );

		}

	}

	processUniform( node ) {

		this.block.setProperty( node.name, node );

	}

	processVarying( node ) {

		this.block.setProperty( node.name, node );

	}

	evalProperty( node ) {

		let property = '';

		if ( node.isAccessor ) {

			property += node.property;

		}

		return property;

	}

	processExpression( node ) {

		if ( node.isAccessor ) {

			const property = this.block.getProperty( this.evalProperty( node ) );

			if ( property ) {

				node.linker.reference = property;

				property.linker.accesses.push( node );

			}

		} else if ( node.isNumber || node.isString ) {

			// Process primitive values

		} else if ( node.isOperator ) {

			this.processExpression( node.left );
			this.processExpression( node.right );

			if ( node.isAssignment ) {

				const property = this.block.getProperty( this.evalProperty( node.left ) );

				if ( property ) {

					property.linker.assignments.push( node );

				}

			}

		} else if ( node.isFunctionCall ) {

			for ( const param of node.params ) {

				this.processExpression( param );

			}

		} else if ( node.isReturn ) {

			if ( node.value ) this.processExpression( node.value );

		} else if ( node.isDiscard || node.isBreak || node.isContinue ) {

			// Process control flow

		} else if ( node.isAccessorElements ) {

			this.processExpression( node.object );

			for ( const element of node.elements ) {

				this.processExpression( element.value );

			}

		} else if ( node.isDynamicElement || node.isStaticElement ) {

			this.processExpression( node.value );

		} else if ( node.isFor || node.isWhile ) {

			this.processForWhile( node );

		} else if ( node.isSwitch ) {

			this.processSwitch( node );

		} else if ( node.isVariableDeclaration ) {

			this.processVariables( node );

		} else if ( node.isUniform ) {

			this.processUniform( node );

		} else if ( node.isVarying ) {

			this.processVarying( node );

		} else if ( node.isTernary ) {

			this.processExpression( node.cond );
			this.processExpression( node.left );
			this.processExpression( node.right );

		} else if ( node.isConditional ) {

			this.processConditional( node );

		} else if ( node.isUnary ) {

			this.processExpression( node.expression );

			if ( node.isAssignment ) {

				if ( node.parent.hasAssignment !== true ) {

					// optimize increment/decrement operator
					// to avoid creating a new variable

					node.after = false;

				}

				const property = this.block.getProperty( this.evalProperty( node.expression ) );

				if ( property ) {

					property.linker.assignments.push( node );

				}

			}

		}

	}

	processBody( body ) {

		for ( const statement of body ) {

			this.processExpression( statement );

		}

	}

	processConditional( node ) {

		this.processExpression( node.cond );
		this.processBody( node.body );

		let current = node;

		while ( current.elseConditional ) {

			if ( current.elseConditional.cond ) {

				this.processExpression( current.elseConditional.cond );

			}

			this.processBody( current.elseConditional.body );

			current = current.elseConditional;

		}

	}

	processForWhile( node ) {

		if ( node.initialization ) this.processExpression( node.initialization );
		if ( node.condition ) this.processExpression( node.condition );
		if ( node.afterthought ) this.processExpression( node.afterthought );

		this.processBody( node.body );

	}

	processSwitch( switchNode ) {

		this.processExpression( switchNode.discriminant );

		for ( const switchCase of switchNode.cases ) {

			if ( switchCase.isDefault !== true ) {

				for ( const condition of switchCase.conditions ) {

					this.processExpression( condition );

				}

			}

			this.processBody( switchCase.body );

		}

	}

	processFunction( node ) {

		this.addBlock( node );

		for ( const param of node.params ) {

			this.block.setProperty( param.name, param );

		}

		this.processBody( node.body );

		this.removeBlock( node );

	}

	process( ast ) {

		this.addBlock( ast );

		for ( const statement of ast.body ) {

			if ( statement.isFunctionDeclaration ) {

				this.processFunction( statement );

			} else {

				this.processExpression( statement );

			}

		}

		this.removeBlock( ast );

	}

}
```
</details>

#### Methods

##### `addBlock(node: any): void`

<details><summary>Code</summary>

```ts
addBlock( node ) {

		this.block = new Block( node, this.block );

	}
```
</details>

##### `removeBlock(node: any): void`

<details><summary>Code</summary>

```ts
removeBlock( node ) {

		if ( this.block === null || this.block.node !== node ) {

			throw new Error( 'No block to remove or block mismatch.' );

		}

		this.block = this.block.parent;

	}
```
</details>

##### `processVariables(node: any): void`

<details><summary>Code</summary>

```ts
processVariables( node ) {

		this.block.setProperty( node.name, node );

		if ( node.value ) {

			this.processExpression( node.value );

		}

	}
```
</details>

##### `processUniform(node: any): void`

<details><summary>Code</summary>

```ts
processUniform( node ) {

		this.block.setProperty( node.name, node );

	}
```
</details>

##### `processVarying(node: any): void`

<details><summary>Code</summary>

```ts
processVarying( node ) {

		this.block.setProperty( node.name, node );

	}
```
</details>

##### `evalProperty(node: any): string`

<details><summary>Code</summary>

```ts
evalProperty( node ) {

		let property = '';

		if ( node.isAccessor ) {

			property += node.property;

		}

		return property;

	}
```
</details>

##### `processExpression(node: any): void`

<details><summary>Code</summary>

```ts
processExpression( node ) {

		if ( node.isAccessor ) {

			const property = this.block.getProperty( this.evalProperty( node ) );

			if ( property ) {

				node.linker.reference = property;

				property.linker.accesses.push( node );

			}

		} else if ( node.isNumber || node.isString ) {

			// Process primitive values

		} else if ( node.isOperator ) {

			this.processExpression( node.left );
			this.processExpression( node.right );

			if ( node.isAssignment ) {

				const property = this.block.getProperty( this.evalProperty( node.left ) );

				if ( property ) {

					property.linker.assignments.push( node );

				}

			}

		} else if ( node.isFunctionCall ) {

			for ( const param of node.params ) {

				this.processExpression( param );

			}

		} else if ( node.isReturn ) {

			if ( node.value ) this.processExpression( node.value );

		} else if ( node.isDiscard || node.isBreak || node.isContinue ) {

			// Process control flow

		} else if ( node.isAccessorElements ) {

			this.processExpression( node.object );

			for ( const element of node.elements ) {

				this.processExpression( element.value );

			}

		} else if ( node.isDynamicElement || node.isStaticElement ) {

			this.processExpression( node.value );

		} else if ( node.isFor || node.isWhile ) {

			this.processForWhile( node );

		} else if ( node.isSwitch ) {

			this.processSwitch( node );

		} else if ( node.isVariableDeclaration ) {

			this.processVariables( node );

		} else if ( node.isUniform ) {

			this.processUniform( node );

		} else if ( node.isVarying ) {

			this.processVarying( node );

		} else if ( node.isTernary ) {

			this.processExpression( node.cond );
			this.processExpression( node.left );
			this.processExpression( node.right );

		} else if ( node.isConditional ) {

			this.processConditional( node );

		} else if ( node.isUnary ) {

			this.processExpression( node.expression );

			if ( node.isAssignment ) {

				if ( node.parent.hasAssignment !== true ) {

					// optimize increment/decrement operator
					// to avoid creating a new variable

					node.after = false;

				}

				const property = this.block.getProperty( this.evalProperty( node.expression ) );

				if ( property ) {

					property.linker.assignments.push( node );

				}

			}

		}

	}
```
</details>

##### `processBody(body: any): void`

<details><summary>Code</summary>

```ts
processBody( body ) {

		for ( const statement of body ) {

			this.processExpression( statement );

		}

	}
```
</details>

##### `processConditional(node: any): void`

<details><summary>Code</summary>

```ts
processConditional( node ) {

		this.processExpression( node.cond );
		this.processBody( node.body );

		let current = node;

		while ( current.elseConditional ) {

			if ( current.elseConditional.cond ) {

				this.processExpression( current.elseConditional.cond );

			}

			this.processBody( current.elseConditional.body );

			current = current.elseConditional;

		}

	}
```
</details>

##### `processForWhile(node: any): void`

<details><summary>Code</summary>

```ts
processForWhile( node ) {

		if ( node.initialization ) this.processExpression( node.initialization );
		if ( node.condition ) this.processExpression( node.condition );
		if ( node.afterthought ) this.processExpression( node.afterthought );

		this.processBody( node.body );

	}
```
</details>

##### `processSwitch(switchNode: any): void`

<details><summary>Code</summary>

```ts
processSwitch( switchNode ) {

		this.processExpression( switchNode.discriminant );

		for ( const switchCase of switchNode.cases ) {

			if ( switchCase.isDefault !== true ) {

				for ( const condition of switchCase.conditions ) {

					this.processExpression( condition );

				}

			}

			this.processBody( switchCase.body );

		}

	}
```
</details>

##### `processFunction(node: any): void`

<details><summary>Code</summary>

```ts
processFunction( node ) {

		this.addBlock( node );

		for ( const param of node.params ) {

			this.block.setProperty( param.name, param );

		}

		this.processBody( node.body );

		this.removeBlock( node );

	}
```
</details>

##### `process(ast: any): void`

<details><summary>Code</summary>

```ts
process( ast ) {

		this.addBlock( ast );

		for ( const statement of ast.body ) {

			if ( statement.isFunctionDeclaration ) {

				this.processFunction( statement );

			} else {

				this.processExpression( statement );

			}

		}

		this.removeBlock( ast );

	}
```
</details>


---