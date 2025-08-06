[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TSLCore.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 53 |
| 🧱 Classes | 3 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 61 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/tsl/TSLCore.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `ArrayElementNode` | `../utils/ArrayElementNode.js` |
| `ConvertNode` | `../utils/ConvertNode.js` |
| `JoinNode` | `../utils/JoinNode.js` |
| `SplitNode` | `../utils/SplitNode.js` |
| `SetNode` | `../utils/SetNode.js` |
| `FlipNode` | `../utils/FlipNode.js` |
| `ConstNode` | `../core/ConstNode.js` |
| `MemberNode` | `../utils/MemberNode.js` |
| `getValueFromType` | `../core/NodeUtils.js` |
| `getValueType` | `../core/NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `currentStack` | `any` | let/var | `null` | ✗ |
| `NodeElements` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `shaderNodeHandler` | `{ setup(NodeClosure: any, params: any...` | let/var | `{ setup( NodeClosure, params ) { const inputs = params.shift(); return NodeCl...` | ✗ |
| `nodeObjectsCacheMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `nodeBuilderFunctionsCacheMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `len` | `any` | let/var | `array.length` | ✗ |
| `fn` | `any` | let/var | `*not shown*` | ✗ |
| `name` | `any` | let/var | `scope` | ✗ |
| `minParams` | `any` | let/var | `*not shown*` | ✗ |
| `maxParams` | `any` | let/var | `*not shown*` | ✗ |
| `tslName` | `any` | let/var | `*not shown*` | ✗ |
| `subBuild` | `any` | let/var | `builder.getClosestSubBuild( shaderNode.subBuilds ) \|\| ''` | ✗ |
| `subBuildProperty` | `any` | let/var | `subBuild \|\| 'default'` | ✗ |
| `previousSubBuildFn` | `any` | let/var | `builder.subBuildFn` | ✗ |
| `result` | `any` | let/var | `null` | ✗ |
| `inputs` | `any` | let/var | `inputNodes` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `secureNodeBuilder` | `any` | let/var | `new Proxy( builder, { get: ( target, property, receiver ) => { let value; if ...` | ✗ |
| `jsFunc` | `any` | let/var | `shaderNode.jsFunc` | ✗ |
| `outputNode` | `any` | let/var | `inputs !== null \|\| jsFunc.length > 1 ? jsFunc( inputs \|\| [], secureNodeBu...` | ✗ |
| `result` | `any` | let/var | `null` | ✗ |
| `bools` | `boolean[]` | let/var | `[ false, true ]` | ✗ |
| `uints` | `number[]` | let/var | `[ 0, 1, 2, 3 ]` | ✗ |
| `ints` | `number[]` | let/var | `[ - 1, - 2 ]` | ✗ |
| `floats` | `number[]` | let/var | `[ 0.5, 1.5, 1 / 3, 1e-6, 1e6, Math.PI, Math.PI * 2, 1 / Math.PI, 2 / Math.PI,...` | ✗ |
| `boolsCacheMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `uintsCacheMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `intsCacheMap` | `Map<any, any>` | let/var | `new Map( [ ...uintsCacheMap ].map( el => new ConstNode( el.value, 'int' ) ) )` | ✗ |
| `floatsCacheMap` | `Map<any, any>` | let/var | `new Map( [ ...intsCacheMap ].map( el => new ConstNode( el.value ) ) )` | ✗ |
| `cacheMaps` | `{ bool: Map<any, any>; uint: Map<any,...` | let/var | `{ bool: boolsCacheMap, uint: uintsCacheMap, ints: intsCacheMap, float: floats...` | ✗ |
| `constNodesCacheMap` | `Map<any, any>` | let/var | `new Map( [ ...boolsCacheMap, ...floatsCacheMap ] )` | ✗ |
| `paramType` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof param` | ✗ |
| `fnId` | `number` | let/var | `0` | ✗ |
| `nodeType` | `any` | let/var | `null` | ✗ |
| `nodeType` | `any` | let/var | `this.shaderNode.nodeType` | ✗ |
| `fullLayout` | `{ name: string; type: any; inputs: an...` | let/var | `{ name: 'fn' + fnId ++, type: nodeType, inputs: [] }` | ✗ |
| `inputs` | `any` | let/var | `*not shown*` | ✗ |
| `isArrayAsParameter` | `any` | let/var | `params[ 0 ] && ( params[ 0 ].isNode \|\| Object.getPrototypeOf( params[ 0 ] )...` | ✗ |
| `instance` | `FnNode` | let/var | `new FnNode( jsFunc, layout )` | ✗ |
| `color` | `any` | let/var | `new ConvertType( 'color' )` | ✓ |
| `float` | `any` | let/var | `new ConvertType( 'float', cacheMaps.float )` | ✓ |
| `int` | `any` | let/var | `new ConvertType( 'int', cacheMaps.ints )` | ✓ |
| `uint` | `any` | let/var | `new ConvertType( 'uint', cacheMaps.uint )` | ✓ |
| `bool` | `any` | let/var | `new ConvertType( 'bool', cacheMaps.bool )` | ✓ |
| `vec2` | `any` | let/var | `new ConvertType( 'vec2' )` | ✓ |
| `ivec2` | `any` | let/var | `new ConvertType( 'ivec2' )` | ✓ |
| `uvec2` | `any` | let/var | `new ConvertType( 'uvec2' )` | ✓ |
| `bvec2` | `any` | let/var | `new ConvertType( 'bvec2' )` | ✓ |
| `vec3` | `any` | let/var | `new ConvertType( 'vec3' )` | ✓ |
| `ivec3` | `any` | let/var | `new ConvertType( 'ivec3' )` | ✓ |
| `uvec3` | `any` | let/var | `new ConvertType( 'uvec3' )` | ✓ |
| `bvec3` | `any` | let/var | `new ConvertType( 'bvec3' )` | ✓ |
| `vec4` | `any` | let/var | `new ConvertType( 'vec4' )` | ✓ |
| `ivec4` | `any` | let/var | `new ConvertType( 'ivec4' )` | ✓ |
| `uvec4` | `any` | let/var | `new ConvertType( 'uvec4' )` | ✓ |
| `bvec4` | `any` | let/var | `new ConvertType( 'bvec4' )` | ✓ |
| `mat2` | `any` | let/var | `new ConvertType( 'mat2' )` | ✓ |
| `mat3` | `any` | let/var | `new ConvertType( 'mat3' )` | ✓ |
| `mat4` | `any` | let/var | `new ConvertType( 'mat4' )` | ✓ |


---

## Functions

### `addMethodChaining(name: any, nodeElement: any): void`

**Parameters:**

- **`name`** `any`
- **`nodeElement`** `any`

**Returns:** `void`

**Calls:**

- `NodeElements.has`
- `console.warn`
- `NodeElements.set`

<details><summary>Code</summary>

```typescript
export function addMethodChaining( name, nodeElement ) {

	if ( NodeElements.has( name ) ) {

		console.warn( `THREE.TSL: Redefinition of method chaining '${ name }'.` );
		return;

	}

	if ( typeof nodeElement !== 'function' ) throw new Error( `THREE.TSL: Node element ${ name } is not a function` );

	NodeElements.set( name, nodeElement );

}
```
</details>

### `parseSwizzle(props: any): any`

**Parameters:**

- **`props`** `any`

**Returns:** `any`

**Calls:**

- `props.replace( /r|s/g, 'x' ).replace( /g|t/g, 'y' ).replace( /b|p/g, 'z' ).replace`

<details><summary>Code</summary>

```typescript
( props ) => props.replace( /r|s/g, 'x' ).replace( /g|t/g, 'y' ).replace( /b|p/g, 'z' ).replace( /a|q/g, 'w' )
```
</details>

### `parseSwizzleAndSort(props: any): any`

**Parameters:**

- **`props`** `any`

**Returns:** `any`

**Calls:**

- `parseSwizzle( props ).split( '' ).sort().join`

<details><summary>Code</summary>

```typescript
( props ) => parseSwizzle( props ).split( '' ).sort().join( '' )
```
</details>

### `ShaderNodeObject(obj: any, altType: any): any`

**Parameters:**

- **`obj`** `any`
- **`altType`** `any`

**Returns:** `any`

**Calls:**

- `getValueType (from ../core/NodeUtils.js)`
- `nodeObjectsCacheMap.get`
- `nodeObjectsCacheMap.set`
- `nodeObject`
- `getConstNode`
- `Fn`

<details><summary>Code</summary>

```typescript
function ( obj, altType = null ) {

	const type = getValueType( obj );

	if ( type === 'node' ) {

		let nodeObject = nodeObjectsCacheMap.get( obj );

		if ( nodeObject === undefined ) {

			nodeObject = new Proxy( obj, shaderNodeHandler );

			nodeObjectsCacheMap.set( obj, nodeObject );
			nodeObjectsCacheMap.set( nodeObject, nodeObject );

		}

		return nodeObject;

	} else if ( ( altType === null && ( type === 'float' || type === 'boolean' ) ) || ( type && type !== 'shader' && type !== 'string' ) ) {

		return nodeObject( getConstNode( obj, altType ) );

	} else if ( type === 'shader' ) {

		return obj.isFn ? obj : Fn( obj );

	}

	return obj;

}
```
</details>

### `ShaderNodeObjects(objects: any, altType: any): any`

**Parameters:**

- **`objects`** `any`
- **`altType`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject`

<details><summary>Code</summary>

```typescript
function ( objects, altType = null ) {

	for ( const name in objects ) {

		objects[ name ] = nodeObject( objects[ name ], altType );

	}

	return objects;

}
```
</details>

### `ShaderNodeArray(array: any, altType: any): any`

**Parameters:**

- **`array`** `any`
- **`altType`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject`

<details><summary>Code</summary>

```typescript
function ( array, altType = null ) {

	const len = array.length;

	for ( let i = 0; i < len; i ++ ) {

		array[ i ] = nodeObject( array[ i ], altType );

	}

	return array;

}
```
</details>

### `ShaderNodeProxy(NodeClass: any, scope: any, factor: any, settings: any): (...params: any[]) => any`

**Parameters:**

- **`NodeClass`** `any`
- **`scope`** `any`
- **`factor`** `any`
- **`settings`** `any`

**Returns:** `(...params: any[]) => any`

**Calls:**

- `nodeObject`
- `Object.assign`
- `node.toVarIntent`
- `/[a-z]/i.test`
- `console.error`
- `params.concat`
- `new Array( minParams - params.length ).fill`
- `params.slice`
- `assignNode`
- `nodeArray`
- `verifyParamsLimit`

<details><summary>Code</summary>

```typescript
function ( NodeClass, scope = null, factor = null, settings = null ) {

	function assignNode( node ) {

		if ( settings !== null ) {

			node = nodeObject( Object.assign( node, settings ) );

			if ( settings.intent === true ) {

				node = node.toVarIntent();

			}

		} else {

			node = nodeObject( node );

		}

		return node;


	}

	let fn, name = scope, minParams, maxParams;

	function verifyParamsLimit( params ) {

		let tslName;

		if ( name ) tslName = /[a-z]/i.test( name ) ? name + '()' : name;
		else tslName = NodeClass.type;

		if ( minParams !== undefined && params.length < minParams ) {

			console.error( `THREE.TSL: "${ tslName }" parameter length is less than minimum required.` );

			return params.concat( new Array( minParams - params.length ).fill( 0 ) );

		} else if ( maxParams !== undefined && params.length > maxParams ) {

			console.error( `THREE.TSL: "${ tslName }" parameter length exceeds limit.` );

			return params.slice( 0, maxParams );

		}

		return params;

	}

	if ( scope === null ) {

		fn = ( ...params ) => {

			return assignNode( new NodeClass( ...nodeArray( verifyParamsLimit( params ) ) ) );

		};

	} else if ( factor !== null ) {

		factor = nodeObject( factor );

		fn = ( ...params ) => {

			return assignNode( new NodeClass( scope, ...nodeArray( verifyParamsLimit( params ) ), factor ) );

		};

	} else {

		fn = ( ...params ) => {

			return assignNode( new NodeClass( scope, ...nodeArray( verifyParamsLimit( params ) ) ) );

		};

	}

	fn.setParameterLength = ( ...params ) => {

		if ( params.length === 1 ) minParams = maxParams = params[ 0 ];
		else if ( params.length === 2 ) [ minParams, maxParams ] = params;

		return fn;

	};

	fn.setName = ( value ) => {

		name = value;

		return fn;

	};

	return fn;

}
```
</details>

### `assignNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject`
- `Object.assign`
- `node.toVarIntent`

<details><summary>Code</summary>

```typescript
function assignNode( node ) {

		if ( settings !== null ) {

			node = nodeObject( Object.assign( node, settings ) );

			if ( settings.intent === true ) {

				node = node.toVarIntent();

			}

		} else {

			node = nodeObject( node );

		}

		return node;


	}
```
</details>

### `verifyParamsLimit(params: any): any`

**Parameters:**

- **`params`** `any`

**Returns:** `any`

**Calls:**

- `/[a-z]/i.test`
- `console.error`
- `params.concat`
- `new Array( minParams - params.length ).fill`
- `params.slice`

<details><summary>Code</summary>

```typescript
function verifyParamsLimit( params ) {

		let tslName;

		if ( name ) tslName = /[a-z]/i.test( name ) ? name + '()' : name;
		else tslName = NodeClass.type;

		if ( minParams !== undefined && params.length < minParams ) {

			console.error( `THREE.TSL: "${ tslName }" parameter length is less than minimum required.` );

			return params.concat( new Array( minParams - params.length ).fill( 0 ) );

		} else if ( maxParams !== undefined && params.length > maxParams ) {

			console.error( `THREE.TSL: "${ tslName }" parameter length exceeds limit.` );

			return params.slice( 0, maxParams );

		}

		return params;

	}
```
</details>

### `ShaderNodeImmutable(NodeClass: any, params: any[]): any`

**Parameters:**

- **`NodeClass`** `any`
- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `nodeObject`
- `nodeArray`

<details><summary>Code</summary>

```typescript
function ( NodeClass, ...params ) {

	return nodeObject( new NodeClass( ...nodeArray( params ) ) );

}
```
</details>

### `ShaderCallNodeInternal.getNodeType(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getOutputNode( builder ).getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.shaderNode.nodeType || this.getOutputNode( builder ).getNodeType( builder );

	}
```
</details>

### `ShaderCallNodeInternal.getMemberType(builder: any, name: any): any`

**Parameters:**

- **`builder`** `any`
- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.getOutputNode( builder ).getMemberType`

<details><summary>Code</summary>

```typescript
getMemberType( builder, name ) {

		return this.getOutputNode( builder ).getMemberType( builder, name );

	}
```
</details>

### `ShaderCallNodeInternal.call(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `builder.getClosestSubBuild`
- `nodeBuilderFunctionsCacheMap.get`
- `nodeBuilderFunctionsCacheMap.set`
- `functionNodesCacheMap.get`
- `nodeObject`
- `builder.buildFunctionNode`
- `functionNodesCacheMap.set`
- `builder.addInclude`
- `functionNode.call`
- `Array.isArray`
- `Reflect.get`
- `jsFunc`

**Internal Comments:**
```
// (x2)
// If inputs is an array, we need to convert it to a Proxy (x2)
// so we can call TSL functions using the syntax `Fn( ( { r, g, b } ) => { ... } )` (x2)
// and call through `fn( 0, 1, 0 )` or `fn( { r: 0, g: 1, b: 0 } )` (x2)
```

<details><summary>Code</summary>

```typescript
call( builder ) {

		const { shaderNode, inputNodes } = this;

		const properties = builder.getNodeProperties( shaderNode );

		const subBuild = builder.getClosestSubBuild( shaderNode.subBuilds ) || '';
		const subBuildProperty = subBuild || 'default';

		if ( properties[ subBuildProperty ] ) {

			return properties[ subBuildProperty ];

		}

		//

		const previousSubBuildFn = builder.subBuildFn;

		builder.subBuildFn = subBuild;

		let result = null;

		if ( shaderNode.layout ) {

			let functionNodesCacheMap = nodeBuilderFunctionsCacheMap.get( builder.constructor );

			if ( functionNodesCacheMap === undefined ) {

				functionNodesCacheMap = new WeakMap();

				nodeBuilderFunctionsCacheMap.set( builder.constructor, functionNodesCacheMap );

			}

			let functionNode = functionNodesCacheMap.get( shaderNode );

			if ( functionNode === undefined ) {

				functionNode = nodeObject( builder.buildFunctionNode( shaderNode ) );

				functionNodesCacheMap.set( shaderNode, functionNode );

			}

			builder.addInclude( functionNode );

			result = nodeObject( functionNode.call( inputNodes ) );

		} else {

			let inputs = inputNodes;

			if ( Array.isArray( inputs ) ) {

				// If inputs is an array, we need to convert it to a Proxy
				// so we can call TSL functions using the syntax `Fn( ( { r, g, b } ) => { ... } )`
				// and call through `fn( 0, 1, 0 )` or `fn( { r: 0, g: 1, b: 0 } )`

				let index = 0;

				inputs = new Proxy( inputs, {

					get: ( target, property, receiver ) => {

						let value;

						if ( target[ property ] === undefined ) {

							value = target[ index ++ ];

						} else {

							value = Reflect.get( target, property, receiver );

						}

						return value;

					}

				} );

			}

			const secureNodeBuilder = new Proxy( builder, {

				get: ( target, property, receiver ) => {

					let value;

					if ( Symbol.iterator === property ) {

						value = function* () {

							yield undefined;

						};

					} else {

						value = Reflect.get( target, property, receiver );

					}

					return value;

				}

			} );

			const jsFunc = shaderNode.jsFunc;
			const outputNode = inputs !== null || jsFunc.length > 1 ? jsFunc( inputs || [], secureNodeBuilder ) : jsFunc( secureNodeBuilder );

			result = nodeObject( outputNode );

		}

		builder.subBuildFn = previousSubBuildFn;

		if ( shaderNode.once ) {

			properties[ subBuildProperty ] = result;

		}

		return result;

	}
```
</details>

### `ShaderCallNodeInternal.setupOutput(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.addStack`
- `this.call`
- `builder.removeStack`

<details><summary>Code</summary>

```typescript
setupOutput( builder ) {

		builder.addStack();

		builder.stack.outputNode = this.call( builder );

		return builder.removeStack();

	}
```
</details>

### `ShaderCallNodeInternal.getOutputNode(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `builder.getSubBuildOutput`
- `this.setupOutput`
- `builder.getClosestSubBuild`

<details><summary>Code</summary>

```typescript
getOutputNode( builder ) {

		const properties = builder.getNodeProperties( this );
		const subBuildOutput = builder.getSubBuildOutput( this );

		properties[ subBuildOutput ] = properties[ subBuildOutput ] || this.setupOutput( builder );
		properties[ subBuildOutput ].subBuild = builder.getClosestSubBuild( this );

		return properties[ subBuildOutput ];

	}
```
</details>

### `ShaderCallNodeInternal.build(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `builder.getBuildStage`
- `builder.getNodeProperties`
- `builder.getSubBuildOutput`
- `this.getOutputNode`
- `builder.getSubBuildProperty`
- `properties[ subBuildOutput ].build`
- `builder.getDataFromNode`
- `nodeData.subBuilds.add`
- `outputNode.build`

**Internal Comments:**
```
// If the shaderNode has subBuilds, add them to the chaining nodes
// so they can be built later in the build process.
```

<details><summary>Code</summary>

```typescript
build( builder, output = null ) {

		let result = null;

		const buildStage = builder.getBuildStage();
		const properties = builder.getNodeProperties( this );

		const subBuildOutput = builder.getSubBuildOutput( this );
		const outputNode = this.getOutputNode( builder );

		if ( buildStage === 'setup' ) {

			const subBuildInitialized = builder.getSubBuildProperty( 'initialized', this );

			if ( properties[ subBuildInitialized ] !== true ) {

				properties[ subBuildInitialized ] = true;

				properties[ subBuildOutput ] = this.getOutputNode( builder );
				properties[ subBuildOutput ].build( builder );

				// If the shaderNode has subBuilds, add them to the chaining nodes
				// so they can be built later in the build process.

				if ( this.shaderNode.subBuilds ) {

					for ( const node of builder.chaining ) {

						const nodeData = builder.getDataFromNode( node, 'any' );
						nodeData.subBuilds = nodeData.subBuilds || new Set();

						for ( const subBuild of this.shaderNode.subBuilds ) {

							nodeData.subBuilds.add( subBuild );

						}

						//builder.getDataFromNode( node ).subBuilds = nodeData.subBuilds;

					}

				}

			}

			result = properties[ subBuildOutput ];

		} else if ( buildStage === 'analyze' ) {

			outputNode.build( builder, output );

		} else if ( buildStage === 'generate' ) {

			result = outputNode.build( builder, output ) || '';

		}

		return result;

	}
```
</details>

### `get(target: any[], property: string | symbol, receiver: any): any`

**Parameters:**

- **`target`** `any[]`
- **`property`** `string | symbol`
- **`receiver`** `any`

**Returns:** `any`

**Calls:**

- `Reflect.get`

<details><summary>Code</summary>

```typescript
( target, property, receiver ) => {

						let value;

						if ( target[ property ] === undefined ) {

							value = target[ index ++ ];

						} else {

							value = Reflect.get( target, property, receiver );

						}

						return value;

					}
```
</details>

### `get(target: any[], property: string | symbol, receiver: any): any`

**Parameters:**

- **`target`** `any[]`
- **`property`** `string | symbol`
- **`receiver`** `any`

**Returns:** `any`

**Calls:**

- `Reflect.get`

<details><summary>Code</summary>

```typescript
( target, property, receiver ) => {

						let value;

						if ( target[ property ] === undefined ) {

							value = target[ index ++ ];

						} else {

							value = Reflect.get( target, property, receiver );

						}

						return value;

					}
```
</details>

### `get(target: any, property: string | symbol, receiver: any): any`

**Parameters:**

- **`target`** `any`
- **`property`** `string | symbol`
- **`receiver`** `any`

**Returns:** `any`

**Calls:**

- `Reflect.get`

<details><summary>Code</summary>

```typescript
( target, property, receiver ) => {

					let value;

					if ( Symbol.iterator === property ) {

						value = function* () {

							yield undefined;

						};

					} else {

						value = Reflect.get( target, property, receiver );

					}

					return value;

				}
```
</details>

### `get(target: any, property: string | symbol, receiver: any): any`

**Parameters:**

- **`target`** `any`
- **`property`** `string | symbol`
- **`receiver`** `any`

**Returns:** `any`

**Calls:**

- `Reflect.get`

<details><summary>Code</summary>

```typescript
( target, property, receiver ) => {

					let value;

					if ( Symbol.iterator === property ) {

						value = function* () {

							yield undefined;

						};

					} else {

						value = Reflect.get( target, property, receiver );

					}

					return value;

				}
```
</details>

### `get(target: any, property: string | symbol, receiver: any): any`

**Parameters:**

- **`target`** `any`
- **`property`** `string | symbol`
- **`receiver`** `any`

**Returns:** `any`

**Calls:**

- `Reflect.get`

<details><summary>Code</summary>

```typescript
( target, property, receiver ) => {

					let value;

					if ( Symbol.iterator === property ) {

						value = function* () {

							yield undefined;

						};

					} else {

						value = Reflect.get( target, property, receiver );

					}

					return value;

				}
```
</details>

### `get(target: any, property: string | symbol, receiver: any): any`

**Parameters:**

- **`target`** `any`
- **`property`** `string | symbol`
- **`receiver`** `any`

**Returns:** `any`

**Calls:**

- `Reflect.get`

<details><summary>Code</summary>

```typescript
( target, property, receiver ) => {

					let value;

					if ( Symbol.iterator === property ) {

						value = function* () {

							yield undefined;

						};

					} else {

						value = Reflect.get( target, property, receiver );

					}

					return value;

				}
```
</details>

### `ShaderNodeInternal.setLayout(layout: any): this`

**Parameters:**

- **`layout`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setLayout( layout ) {

		this.layout = layout;

		return this;

	}
```
</details>

### `ShaderNodeInternal.call(inputs: any): any`

**Parameters:**

- **`inputs`** `any`

**Returns:** `any`

**Calls:**

- `nodeObjects`
- `nodeObject`

<details><summary>Code</summary>

```typescript
call( inputs = null ) {

		nodeObjects( inputs );

		return nodeObject( new ShaderCallNodeInternal( this, inputs ) );

	}
```
</details>

### `ShaderNodeInternal.setup(): any`

**Returns:** `any`

**Calls:**

- `this.call`

<details><summary>Code</summary>

```typescript
setup() {

		return this.call();

	}
```
</details>

### `getConstNode(value: any, type: any): any`

**Parameters:**

- **`value`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `constNodesCacheMap.has`
- `constNodesCacheMap.get`

<details><summary>Code</summary>

```typescript
( value, type ) => {

	if ( constNodesCacheMap.has( value ) ) {

		return constNodesCacheMap.get( value );

	} else if ( value.isNode === true ) {

		return value;

	} else {

		return new ConstNode( value, type );

	}

}
```
</details>

### `ConvertType(type: any, cacheMap: any): (...params: any[]) => any`

**Parameters:**

- **`type`** `any`
- **`cacheMap`** `any`

**Returns:** `(...params: any[]) => any`

**Calls:**

- `console.error`
- `nodeObject`
- `[ 'bool', 'float', 'int', 'uint' ].includes`
- `params.every`
- `getValueFromType (from ../core/NodeUtils.js)`
- `cacheMap.has`
- `nodeObjectIntent`
- `cacheMap.get`
- `getConstNode`
- `params.map`

<details><summary>Code</summary>

```typescript
function ( type, cacheMap = null ) {

	return ( ...params ) => {

		for ( const param of params ) {

			if ( param === undefined ) {

				console.error( `THREE.TSL: Invalid parameter for the type "${ type }".` );

				return nodeObject( new ConstNode( 0, type ) );

			}

		}

		if ( params.length === 0 || ( ! [ 'bool', 'float', 'int', 'uint' ].includes( type ) && params.every( param => {

			const paramType = typeof param;

			return paramType !== 'object' && paramType !== 'function';

		} ) ) ) {

			params = [ getValueFromType( type, ...params ) ];

		}

		if ( params.length === 1 && cacheMap !== null && cacheMap.has( params[ 0 ] ) ) {

			return nodeObjectIntent( cacheMap.get( params[ 0 ] ) );

		}

		if ( params.length === 1 ) {

			const node = getConstNode( params[ 0 ], type );
			if ( node.nodeType === type ) return nodeObjectIntent( node );
			return nodeObjectIntent( new ConvertNode( node, type ) );

		}

		const nodes = params.map( param => getConstNode( param ) );
		return nodeObjectIntent( new JoinNode( nodes, type ) );

	};

}
```
</details>

### `defined(v: any): any`

**Parameters:**

- **`v`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( v ) => typeof v === 'object' && v !== null ? v.value : v
```
</details>

### `getConstNodeType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( value ) => ( value !== undefined && value !== null ) ? ( value.nodeType || value.convertTo || ( typeof value === 'string' ? value : null ) ) : null
```
</details>

### `ShaderNode(jsFunc: any, nodeType: any): any`

**Parameters:**

- **`jsFunc`** `any`
- **`nodeType`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
export function ShaderNode( jsFunc, nodeType ) {

	return new Proxy( new ShaderNodeInternal( jsFunc, nodeType ), shaderNodeHandler );

}
```
</details>

### `nodeObject(val: any, altType: any): any`

**Parameters:**

- **`val`** `any`
- **`altType`** `any`

**Returns:** `any`

**Calls:**

- `ShaderNodeObject`

<details><summary>Code</summary>

```typescript
( val, altType = null ) => /* new */ ShaderNodeObject( val, altType )
```
</details>

### `nodeObjectIntent(val: any, altType: any): any`

**Parameters:**

- **`val`** `any`
- **`altType`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject( val, altType ).toVarIntent`

<details><summary>Code</summary>

```typescript
( val, altType = null ) => /* new */ nodeObject( val, altType ).toVarIntent()
```
</details>

### `nodeObjects(val: any, altType: any): any`

**Parameters:**

- **`val`** `any`
- **`altType`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( val, altType = null ) => new ShaderNodeObjects( val, altType )
```
</details>

### `nodeArray(val: any, altType: any): any`

**Parameters:**

- **`val`** `any`
- **`altType`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( val, altType = null ) => new ShaderNodeArray( val, altType )
```
</details>

### `nodeProxy(NodeClass: any, scope: any, factor: any, settings: any): any`

**Parameters:**

- **`NodeClass`** `any`
- **`scope`** `any`
- **`factor`** `any`
- **`settings`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( NodeClass, scope = null, factor = null, settings = null ) => new ShaderNodeProxy( NodeClass, scope, factor, settings )
```
</details>

### `nodeImmutable(NodeClass: any, params: any[]): any`

**Parameters:**

- **`NodeClass`** `any`
- **`params`** `any[]`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( NodeClass, ...params ) => new ShaderNodeImmutable( NodeClass, ...params )
```
</details>

### `nodeProxyIntent(NodeClass: any, scope: any, factor: any, settings: {}): any`

**Parameters:**

- **`NodeClass`** `any`
- **`scope`** `any`
- **`factor`** `any`
- **`settings`** `{}`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( NodeClass, scope = null, factor = null, settings = {} ) => new ShaderNodeProxy( NodeClass, scope, factor, { intent: true, ...settings } )
```
</details>

### `FnNode.setLayout(layout: any): this`

**Parameters:**

- **`layout`** `any`

**Returns:** `this`

**Calls:**

- `fullLayout.inputs.push`
- `this.shaderNode.setLayout`

<details><summary>Code</summary>

```typescript
setLayout( layout ) {

		const nodeType = this.shaderNode.nodeType;

		if ( typeof layout.inputs !== 'object' ) {

			const fullLayout = {
				name: 'fn' + fnId ++,
				type: nodeType,
				inputs: []
			};

			for ( const name in layout ) {

				if ( name === 'return' ) continue;

				fullLayout.inputs.push( {
					name: name,
					type: layout[ name ]
				} );

			}

			layout = fullLayout;

		}

		this.shaderNode.setLayout( layout );

		return this;

	}
```
</details>

### `FnNode.getNodeType(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.shaderNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.shaderNode.getNodeType( builder ) || 'float';

	}
```
</details>

### `FnNode.call(params: any[]): any`

**Parameters:**

- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `nodeObjects`
- `Object.getPrototypeOf`
- `this.shaderNode.call`
- `fnCall.toStack`
- `fnCall.toVarIntent`

<details><summary>Code</summary>

```typescript
call( ...params ) {

		let inputs;

		nodeObjects( params );

		const isArrayAsParameter = params[ 0 ] && ( params[ 0 ].isNode || Object.getPrototypeOf( params[ 0 ] ) !== Object.prototype );

		if ( isArrayAsParameter ) {

			inputs = [ ...params ];

		} else {

			inputs = params[ 0 ];

		}

		const fnCall = this.shaderNode.call( inputs );

		if ( this.shaderNode.nodeType === 'void' ) fnCall.toStack();

		return fnCall.toVarIntent();

	}
```
</details>

### `FnNode.once(subBuilds: any): this`

**Parameters:**

- **`subBuilds`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
once( subBuilds = null ) {

		this.shaderNode.once = true;
		this.shaderNode.subBuilds = subBuilds;

		return this;

	}
```
</details>

### `FnNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`
- `console.error`
- `builder.generateConst`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const type = this.getNodeType( builder );

		console.error( 'THREE.TSL: "Fn()" was declared but not invoked. Try calling it like "Fn()( ...params )".' );

		return builder.generateConst( type );

	}
```
</details>

### `Fn(jsFunc: any, layout: any): () => void`

**Parameters:**

- **`jsFunc`** `any`
- **`layout`** `any`

**Returns:** `() => void`

**Calls:**

- `instance.call`
- `Reflect.get`
- `Reflect.set`

<details><summary>Code</summary>

```typescript
export function Fn( jsFunc, layout = null ) {

	const instance = new FnNode( jsFunc, layout );

	return new Proxy( () => {}, {

		apply( target, thisArg, params ) {

			return instance.call( ...params );

		},

		get( target, prop, receiver ) {

			return Reflect.get( instance, prop, receiver );

		},

		set( target, prop, value, receiver ) {

			return Reflect.set( instance, prop, value, receiver );

		}

	} );

}
```
</details>

### `setCurrentStack(stack: any): void`

**Parameters:**

- **`stack`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
( stack ) => {

	if ( currentStack === stack ) {

		//throw new Error( 'Stack already defined.' );

	}

	currentStack = stack;

}
```
</details>

### `getCurrentStack(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => currentStack
```
</details>

### `If(params: any[]): StackNode`

**Parameters:**

- **`params`** `any[]`

**Returns:** `StackNode`

**Calls:**

- `currentStack.If`

<details><summary>Code</summary>

```typescript
( ...params ) => currentStack.If( ...params )
```
</details>

### `Switch(params: any[]): StackNode`

**Parameters:**

- **`params`** `any[]`

**Returns:** `StackNode`

**Calls:**

- `currentStack.Switch`

<details><summary>Code</summary>

```typescript
( ...params ) => currentStack.Switch( ...params )
```
</details>

### `Stack(node: Node): Node`

**JSDoc:**
```typescript
/**
 * Add the given node to the current stack.
 *
 * @param {Node} node - The node to add.
 * @returns {Node} The node that was added to the stack.
 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `Node`

**Calls:**

- `currentStack.add`

<details><summary>Code</summary>

```typescript
export function Stack( node ) {

	if ( currentStack ) currentStack.add( node );

	return node;

}
```
</details>

### `string(value: string): any`

**Parameters:**

- **`value`** `string`

**Returns:** `any`

**Calls:**

- `nodeObject`

<details><summary>Code</summary>

```typescript
( value = '' ) => nodeObject( new ConstNode( value, 'string' ) )
```
</details>

### `arrayBuffer(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject`

<details><summary>Code</summary>

```typescript
( value ) => nodeObject( new ConstNode( value, 'ArrayBuffer' ) )
```
</details>

### `convert(node: any, types: any): any`

**Parameters:**

- **`node`** `any`
- **`types`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject`

<details><summary>Code</summary>

```typescript
( node, types ) => nodeObject( new ConvertNode( nodeObject( node ), types ) )
```
</details>

### `split(node: any, channels: any): any`

**Parameters:**

- **`node`** `any`
- **`channels`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject`

<details><summary>Code</summary>

```typescript
( node, channels ) => nodeObject( new SplitNode( nodeObject( node ), channels ) )
```
</details>

### `append(node: Node): Function`

**Parameters:**

- **`node`** `Node`

**Returns:** `Function`

**Calls:**

- `console.warn`
- `Stack`

<details><summary>Code</summary>

```typescript
( node ) => { // @deprecated, r176

	console.warn( 'THREE.TSL: append() has been renamed to Stack().' );
	return Stack( node );

}
```
</details>


---

## Classes

### `ShaderCallNodeInternal`

<details><summary>Class Code</summary>

```ts
class ShaderCallNodeInternal extends Node {

	constructor( shaderNode, inputNodes ) {

		super();

		this.shaderNode = shaderNode;
		this.inputNodes = inputNodes;

		this.isShaderCallNodeInternal = true;

	}

	getNodeType( builder ) {

		return this.shaderNode.nodeType || this.getOutputNode( builder ).getNodeType( builder );

	}

	getMemberType( builder, name ) {

		return this.getOutputNode( builder ).getMemberType( builder, name );

	}

	call( builder ) {

		const { shaderNode, inputNodes } = this;

		const properties = builder.getNodeProperties( shaderNode );

		const subBuild = builder.getClosestSubBuild( shaderNode.subBuilds ) || '';
		const subBuildProperty = subBuild || 'default';

		if ( properties[ subBuildProperty ] ) {

			return properties[ subBuildProperty ];

		}

		//

		const previousSubBuildFn = builder.subBuildFn;

		builder.subBuildFn = subBuild;

		let result = null;

		if ( shaderNode.layout ) {

			let functionNodesCacheMap = nodeBuilderFunctionsCacheMap.get( builder.constructor );

			if ( functionNodesCacheMap === undefined ) {

				functionNodesCacheMap = new WeakMap();

				nodeBuilderFunctionsCacheMap.set( builder.constructor, functionNodesCacheMap );

			}

			let functionNode = functionNodesCacheMap.get( shaderNode );

			if ( functionNode === undefined ) {

				functionNode = nodeObject( builder.buildFunctionNode( shaderNode ) );

				functionNodesCacheMap.set( shaderNode, functionNode );

			}

			builder.addInclude( functionNode );

			result = nodeObject( functionNode.call( inputNodes ) );

		} else {

			let inputs = inputNodes;

			if ( Array.isArray( inputs ) ) {

				// If inputs is an array, we need to convert it to a Proxy
				// so we can call TSL functions using the syntax `Fn( ( { r, g, b } ) => { ... } )`
				// and call through `fn( 0, 1, 0 )` or `fn( { r: 0, g: 1, b: 0 } )`

				let index = 0;

				inputs = new Proxy( inputs, {

					get: ( target, property, receiver ) => {

						let value;

						if ( target[ property ] === undefined ) {

							value = target[ index ++ ];

						} else {

							value = Reflect.get( target, property, receiver );

						}

						return value;

					}

				} );

			}

			const secureNodeBuilder = new Proxy( builder, {

				get: ( target, property, receiver ) => {

					let value;

					if ( Symbol.iterator === property ) {

						value = function* () {

							yield undefined;

						};

					} else {

						value = Reflect.get( target, property, receiver );

					}

					return value;

				}

			} );

			const jsFunc = shaderNode.jsFunc;
			const outputNode = inputs !== null || jsFunc.length > 1 ? jsFunc( inputs || [], secureNodeBuilder ) : jsFunc( secureNodeBuilder );

			result = nodeObject( outputNode );

		}

		builder.subBuildFn = previousSubBuildFn;

		if ( shaderNode.once ) {

			properties[ subBuildProperty ] = result;

		}

		return result;

	}

	setupOutput( builder ) {

		builder.addStack();

		builder.stack.outputNode = this.call( builder );

		return builder.removeStack();

	}

	getOutputNode( builder ) {

		const properties = builder.getNodeProperties( this );
		const subBuildOutput = builder.getSubBuildOutput( this );

		properties[ subBuildOutput ] = properties[ subBuildOutput ] || this.setupOutput( builder );
		properties[ subBuildOutput ].subBuild = builder.getClosestSubBuild( this );

		return properties[ subBuildOutput ];

	}

	build( builder, output = null ) {

		let result = null;

		const buildStage = builder.getBuildStage();
		const properties = builder.getNodeProperties( this );

		const subBuildOutput = builder.getSubBuildOutput( this );
		const outputNode = this.getOutputNode( builder );

		if ( buildStage === 'setup' ) {

			const subBuildInitialized = builder.getSubBuildProperty( 'initialized', this );

			if ( properties[ subBuildInitialized ] !== true ) {

				properties[ subBuildInitialized ] = true;

				properties[ subBuildOutput ] = this.getOutputNode( builder );
				properties[ subBuildOutput ].build( builder );

				// If the shaderNode has subBuilds, add them to the chaining nodes
				// so they can be built later in the build process.

				if ( this.shaderNode.subBuilds ) {

					for ( const node of builder.chaining ) {

						const nodeData = builder.getDataFromNode( node, 'any' );
						nodeData.subBuilds = nodeData.subBuilds || new Set();

						for ( const subBuild of this.shaderNode.subBuilds ) {

							nodeData.subBuilds.add( subBuild );

						}

						//builder.getDataFromNode( node ).subBuilds = nodeData.subBuilds;

					}

				}

			}

			result = properties[ subBuildOutput ];

		} else if ( buildStage === 'analyze' ) {

			outputNode.build( builder, output );

		} else if ( buildStage === 'generate' ) {

			result = outputNode.build( builder, output ) || '';

		}

		return result;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): any`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.shaderNode.nodeType || this.getOutputNode( builder ).getNodeType( builder );

	}
```
</details>

##### `getMemberType(builder: any, name: any): any`

<details><summary>Code</summary>

```ts
getMemberType( builder, name ) {

		return this.getOutputNode( builder ).getMemberType( builder, name );

	}
```
</details>

##### `call(builder: any): any`

<details><summary>Code</summary>

```ts
call( builder ) {

		const { shaderNode, inputNodes } = this;

		const properties = builder.getNodeProperties( shaderNode );

		const subBuild = builder.getClosestSubBuild( shaderNode.subBuilds ) || '';
		const subBuildProperty = subBuild || 'default';

		if ( properties[ subBuildProperty ] ) {

			return properties[ subBuildProperty ];

		}

		//

		const previousSubBuildFn = builder.subBuildFn;

		builder.subBuildFn = subBuild;

		let result = null;

		if ( shaderNode.layout ) {

			let functionNodesCacheMap = nodeBuilderFunctionsCacheMap.get( builder.constructor );

			if ( functionNodesCacheMap === undefined ) {

				functionNodesCacheMap = new WeakMap();

				nodeBuilderFunctionsCacheMap.set( builder.constructor, functionNodesCacheMap );

			}

			let functionNode = functionNodesCacheMap.get( shaderNode );

			if ( functionNode === undefined ) {

				functionNode = nodeObject( builder.buildFunctionNode( shaderNode ) );

				functionNodesCacheMap.set( shaderNode, functionNode );

			}

			builder.addInclude( functionNode );

			result = nodeObject( functionNode.call( inputNodes ) );

		} else {

			let inputs = inputNodes;

			if ( Array.isArray( inputs ) ) {

				// If inputs is an array, we need to convert it to a Proxy
				// so we can call TSL functions using the syntax `Fn( ( { r, g, b } ) => { ... } )`
				// and call through `fn( 0, 1, 0 )` or `fn( { r: 0, g: 1, b: 0 } )`

				let index = 0;

				inputs = new Proxy( inputs, {

					get: ( target, property, receiver ) => {

						let value;

						if ( target[ property ] === undefined ) {

							value = target[ index ++ ];

						} else {

							value = Reflect.get( target, property, receiver );

						}

						return value;

					}

				} );

			}

			const secureNodeBuilder = new Proxy( builder, {

				get: ( target, property, receiver ) => {

					let value;

					if ( Symbol.iterator === property ) {

						value = function* () {

							yield undefined;

						};

					} else {

						value = Reflect.get( target, property, receiver );

					}

					return value;

				}

			} );

			const jsFunc = shaderNode.jsFunc;
			const outputNode = inputs !== null || jsFunc.length > 1 ? jsFunc( inputs || [], secureNodeBuilder ) : jsFunc( secureNodeBuilder );

			result = nodeObject( outputNode );

		}

		builder.subBuildFn = previousSubBuildFn;

		if ( shaderNode.once ) {

			properties[ subBuildProperty ] = result;

		}

		return result;

	}
```
</details>

##### `setupOutput(builder: any): any`

<details><summary>Code</summary>

```ts
setupOutput( builder ) {

		builder.addStack();

		builder.stack.outputNode = this.call( builder );

		return builder.removeStack();

	}
```
</details>

##### `getOutputNode(builder: any): any`

<details><summary>Code</summary>

```ts
getOutputNode( builder ) {

		const properties = builder.getNodeProperties( this );
		const subBuildOutput = builder.getSubBuildOutput( this );

		properties[ subBuildOutput ] = properties[ subBuildOutput ] || this.setupOutput( builder );
		properties[ subBuildOutput ].subBuild = builder.getClosestSubBuild( this );

		return properties[ subBuildOutput ];

	}
```
</details>

##### `build(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
build( builder, output = null ) {

		let result = null;

		const buildStage = builder.getBuildStage();
		const properties = builder.getNodeProperties( this );

		const subBuildOutput = builder.getSubBuildOutput( this );
		const outputNode = this.getOutputNode( builder );

		if ( buildStage === 'setup' ) {

			const subBuildInitialized = builder.getSubBuildProperty( 'initialized', this );

			if ( properties[ subBuildInitialized ] !== true ) {

				properties[ subBuildInitialized ] = true;

				properties[ subBuildOutput ] = this.getOutputNode( builder );
				properties[ subBuildOutput ].build( builder );

				// If the shaderNode has subBuilds, add them to the chaining nodes
				// so they can be built later in the build process.

				if ( this.shaderNode.subBuilds ) {

					for ( const node of builder.chaining ) {

						const nodeData = builder.getDataFromNode( node, 'any' );
						nodeData.subBuilds = nodeData.subBuilds || new Set();

						for ( const subBuild of this.shaderNode.subBuilds ) {

							nodeData.subBuilds.add( subBuild );

						}

						//builder.getDataFromNode( node ).subBuilds = nodeData.subBuilds;

					}

				}

			}

			result = properties[ subBuildOutput ];

		} else if ( buildStage === 'analyze' ) {

			outputNode.build( builder, output );

		} else if ( buildStage === 'generate' ) {

			result = outputNode.build( builder, output ) || '';

		}

		return result;

	}
```
</details>

### `ShaderNodeInternal`

<details><summary>Class Code</summary>

```ts
class ShaderNodeInternal extends Node {

	constructor( jsFunc, nodeType ) {

		super( nodeType );

		this.jsFunc = jsFunc;
		this.layout = null;

		this.global = true;

		this.once = false;

	}

	setLayout( layout ) {

		this.layout = layout;

		return this;

	}

	call( inputs = null ) {

		nodeObjects( inputs );

		return nodeObject( new ShaderCallNodeInternal( this, inputs ) );

	}

	setup() {

		return this.call();

	}

}
```
</details>

#### Methods

##### `setLayout(layout: any): this`

<details><summary>Code</summary>

```ts
setLayout( layout ) {

		this.layout = layout;

		return this;

	}
```
</details>

##### `call(inputs: any): any`

<details><summary>Code</summary>

```ts
call( inputs = null ) {

		nodeObjects( inputs );

		return nodeObject( new ShaderCallNodeInternal( this, inputs ) );

	}
```
</details>

##### `setup(): any`

<details><summary>Code</summary>

```ts
setup() {

		return this.call();

	}
```
</details>

### `FnNode`

<details><summary>Class Code</summary>

```ts
class FnNode extends Node {

	constructor( jsFunc, layout = null ) {

		super();

		let nodeType = null;

		if ( layout !== null ) {

			if ( typeof layout === 'object' ) {

				nodeType = layout.return;

			} else {

				if ( typeof layout === 'string' ) {

					nodeType = layout;

				} else {

					console.error( 'THREE.TSL: Invalid layout type.' );

				}

				layout = null;

			}

		}

		this.shaderNode = new ShaderNode( jsFunc, nodeType );

		if ( layout !== null ) {

			this.setLayout( layout );

		}

		this.isFn = true;

	}

	setLayout( layout ) {

		const nodeType = this.shaderNode.nodeType;

		if ( typeof layout.inputs !== 'object' ) {

			const fullLayout = {
				name: 'fn' + fnId ++,
				type: nodeType,
				inputs: []
			};

			for ( const name in layout ) {

				if ( name === 'return' ) continue;

				fullLayout.inputs.push( {
					name: name,
					type: layout[ name ]
				} );

			}

			layout = fullLayout;

		}

		this.shaderNode.setLayout( layout );

		return this;

	}

	getNodeType( builder ) {

		return this.shaderNode.getNodeType( builder ) || 'float';

	}

	call( ...params ) {

		let inputs;

		nodeObjects( params );

		const isArrayAsParameter = params[ 0 ] && ( params[ 0 ].isNode || Object.getPrototypeOf( params[ 0 ] ) !== Object.prototype );

		if ( isArrayAsParameter ) {

			inputs = [ ...params ];

		} else {

			inputs = params[ 0 ];

		}

		const fnCall = this.shaderNode.call( inputs );

		if ( this.shaderNode.nodeType === 'void' ) fnCall.toStack();

		return fnCall.toVarIntent();

	}

	once( subBuilds = null ) {

		this.shaderNode.once = true;
		this.shaderNode.subBuilds = subBuilds;

		return this;

	}

	generate( builder ) {

		const type = this.getNodeType( builder );

		console.error( 'THREE.TSL: "Fn()" was declared but not invoked. Try calling it like "Fn()( ...params )".' );

		return builder.generateConst( type );

	}

}
```
</details>

#### Methods

##### `setLayout(layout: any): this`

<details><summary>Code</summary>

```ts
setLayout( layout ) {

		const nodeType = this.shaderNode.nodeType;

		if ( typeof layout.inputs !== 'object' ) {

			const fullLayout = {
				name: 'fn' + fnId ++,
				type: nodeType,
				inputs: []
			};

			for ( const name in layout ) {

				if ( name === 'return' ) continue;

				fullLayout.inputs.push( {
					name: name,
					type: layout[ name ]
				} );

			}

			layout = fullLayout;

		}

		this.shaderNode.setLayout( layout );

		return this;

	}
```
</details>

##### `getNodeType(builder: any): any`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.shaderNode.getNodeType( builder ) || 'float';

	}
```
</details>

##### `call(params: any[]): any`

<details><summary>Code</summary>

```ts
call( ...params ) {

		let inputs;

		nodeObjects( params );

		const isArrayAsParameter = params[ 0 ] && ( params[ 0 ].isNode || Object.getPrototypeOf( params[ 0 ] ) !== Object.prototype );

		if ( isArrayAsParameter ) {

			inputs = [ ...params ];

		} else {

			inputs = params[ 0 ];

		}

		const fnCall = this.shaderNode.call( inputs );

		if ( this.shaderNode.nodeType === 'void' ) fnCall.toStack();

		return fnCall.toVarIntent();

	}
```
</details>

##### `once(subBuilds: any): this`

<details><summary>Code</summary>

```ts
once( subBuilds = null ) {

		this.shaderNode.once = true;
		this.shaderNode.subBuilds = subBuilds;

		return this;

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const type = this.getNodeType( builder );

		console.error( 'THREE.TSL: "Fn()" was declared but not invoked. Try calling it like "Fn()( ...params )".' );

		return builder.generateConst( type );

	}
```
</details>


---