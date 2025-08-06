[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Node.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 35 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/Node.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeUpdateType` | `./constants.js` |
| `getNodeChildren` | `./NodeUtils.js` |
| `getCacheKey` | `./NodeUtils.js` |
| `hash` | `./NodeUtils.js` |
| `EventDispatcher` | `../../core/EventDispatcher.js` |
| `MathUtils` | `../../math/MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_parentBuildStage` | `{ analyze: string; generate: string; }` | let/var | `{ analyze: 'setup', generate: 'analyze' }` | ✗ |
| `_nodeId` | `number` | let/var | `0` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `parentBuildStage` | `any` | let/var | `_parentBuildStage[ builder.buildStage ]` | ✗ |
| `result` | `any` | let/var | `null` | ✗ |
| `isGenerateOnce` | `boolean` | let/var | `this.generate.length === 1` | ✗ |
| `inputNodes` | `{}` | let/var | `{}` | ✗ |
| `nodes` | `any` | let/var | `json.meta.nodes` | ✗ |
| `inputArray` | `any[]` | let/var | `[]` | ✗ |
| `inputObject` | `{}` | let/var | `{}` | ✗ |
| `uuid` | `any` | let/var | `json.inputNodes[ property ][ subProperty ]` | ✗ |
| `uuid` | `any` | let/var | `json.inputNodes[ property ]` | ✗ |
| `isRoot` | `boolean` | let/var | `( meta === undefined \|\| typeof meta === 'string' )` | ✗ |
| `data` | `any` | let/var | `meta.nodes[ uuid ]` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `data` | `any` | let/var | `cache[ key ]` | ✗ |


---

## Functions

### `Node.onUpdate(callback: Function, updateType: string): Node`

**JSDoc:**
```typescript
/**
	 * Convenient method for defining {@link Node#update}.
	 *
	 * @param {Function} callback - The update method.
	 * @param {string} updateType - The update type.
	 * @return {Node} A reference to this node.
	 */
```

**Parameters:**

- **`callback`** `Function`
- **`updateType`** `string`

**Returns:** `Node`

**Calls:**

- `callback.bind`
- `this.getSelf`

<details><summary>Code</summary>

```typescript
onUpdate( callback, updateType ) {

		this.updateType = updateType;
		this.update = callback.bind( this.getSelf() );

		return this;

	}
```
</details>

### `Node.onFrameUpdate(callback: Function): Node`

**JSDoc:**
```typescript
/**
	 * Convenient method for defining {@link Node#update}. Similar to {@link Node#onUpdate}, but
	 * this method automatically sets the update type to `FRAME`.
	 *
	 * @param {Function} callback - The update method.
	 * @return {Node} A reference to this node.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `Node`

**Calls:**

- `this.onUpdate`

<details><summary>Code</summary>

```typescript
onFrameUpdate( callback ) {

		return this.onUpdate( callback, NodeUpdateType.FRAME );

	}
```
</details>

### `Node.onRenderUpdate(callback: Function): Node`

**JSDoc:**
```typescript
/**
	 * Convenient method for defining {@link Node#update}. Similar to {@link Node#onUpdate}, but
	 * this method automatically sets the update type to `RENDER`.
	 *
	 * @param {Function} callback - The update method.
	 * @return {Node} A reference to this node.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `Node`

**Calls:**

- `this.onUpdate`

<details><summary>Code</summary>

```typescript
onRenderUpdate( callback ) {

		return this.onUpdate( callback, NodeUpdateType.RENDER );

	}
```
</details>

### `Node.onObjectUpdate(callback: Function): Node`

**JSDoc:**
```typescript
/**
	 * Convenient method for defining {@link Node#update}. Similar to {@link Node#onUpdate}, but
	 * this method automatically sets the update type to `OBJECT`.
	 *
	 * @param {Function} callback - The update method.
	 * @return {Node} A reference to this node.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `Node`

**Calls:**

- `this.onUpdate`

<details><summary>Code</summary>

```typescript
onObjectUpdate( callback ) {

		return this.onUpdate( callback, NodeUpdateType.OBJECT );

	}
```
</details>

### `Node.onReference(callback: Function): Node`

**JSDoc:**
```typescript
/**
	 * Convenient method for defining {@link Node#updateReference}.
	 *
	 * @param {Function} callback - The update method.
	 * @return {Node} A reference to this node.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `Node`

**Calls:**

- `callback.bind`
- `this.getSelf`

<details><summary>Code</summary>

```typescript
onReference( callback ) {

		this.updateReference = callback.bind( this.getSelf() );

		return this;

	}
```
</details>

### `Node.getSelf(): Node`

**JSDoc:**
```typescript
/**
	 * The `this` reference might point to a Proxy so this method can be used
	 * to get the reference to the actual node instance.
	 *
	 * @return {Node} A reference to the node.
	 */
```

**Returns:** `Node`

**Internal Comments:**
```
// Returns non-node object.
```

<details><summary>Code</summary>

```typescript
getSelf() {

		// Returns non-node object.

		return this.self || this;

	}
```
</details>

### `Node.updateReference(): any`

**JSDoc:**
```typescript
/**
	 * Nodes might refer to other objects like materials. This method allows to dynamically update the reference
	 * to such objects based on a given state (e.g. the current node frame or builder).
	 *
	 * @param {any} state - This method can be invocated in different contexts so `state` can refer to any object type.
	 * @return {any} The updated reference.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
updateReference( /*state*/ ) {

		return this;

	}
```
</details>

### `Node.isGlobal(): boolean`

**JSDoc:**
```typescript
/**
	 * By default this method returns the value of the {@link Node#global} flag. This method
	 * can be overwritten in derived classes if an analytical way is required to determine the
	 * global cache referring to the current shader-stage.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {boolean} Whether this node is global or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isGlobal( /*builder*/ ) {

		return this.global;

	}
```
</details>

### `Node.getChildren(): Generator<any, void, unknown>`

**JSDoc:**
```typescript
/**
	 * Generator function that can be used to iterate over the child nodes.
	 *
	 * @generator
	 * @yields {Node} A child node.
	 */
```

**Returns:** `Generator<any, void, unknown>`

**Calls:**

- `getNodeChildren (from ./NodeUtils.js)`

<details><summary>Code</summary>

```typescript
* getChildren() {

		for ( const { childNode } of getNodeChildren( this ) ) {

			yield childNode;

		}

	}
```
</details>

### `Node.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Calling this method dispatches the `dispose` event. This event can be used
	 * to register event listeners for clean up tasks.
	 */
```

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}
```
</details>

### `Node.traverse(callback: traverseCallback): void`

**JSDoc:**
```typescript
/**
	 * Can be used to traverse through the node's hierarchy.
	 *
	 * @param {traverseCallback} callback - A callback that is executed per node.
	 */
```

**Parameters:**

- **`callback`** `traverseCallback`

**Returns:** `void`

**Calls:**

- `callback`
- `this.getChildren`
- `childNode.traverse`

<details><summary>Code</summary>

```typescript
traverse( callback ) {

		callback( this );

		for ( const childNode of this.getChildren() ) {

			childNode.traverse( callback );

		}

	}
```
</details>

### `Node.getCacheKey(force: boolean): number`

**JSDoc:**
```typescript
/**
	 * Returns the cache key for this node.
	 *
	 * @param {boolean} [force=false] - When set to `true`, a recomputation of the cache key is forced.
	 * @return {number} The cache key of the node.
	 */
```

**Parameters:**

- **`force`** `boolean`

**Returns:** `number`

**Calls:**

- `hash (from ./NodeUtils.js)`
- `getCacheKey (from ./NodeUtils.js)`
- `this.customCacheKey`

<details><summary>Code</summary>

```typescript
getCacheKey( force = false ) {

		force = force || this.version !== this._cacheKeyVersion;

		if ( force === true || this._cacheKey === null ) {

			this._cacheKey = hash( getCacheKey( this, force ), this.customCacheKey() );
			this._cacheKeyVersion = this.version;

		}

		return this._cacheKey;

	}
```
</details>

### `Node.customCacheKey(): number`

**JSDoc:**
```typescript
/**
	 * Generate a custom cache key for this node.
	 *
	 * @return {number} The cache key of the node.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
customCacheKey() {

		return 0;

	}
```
</details>

### `Node.getScope(): Node`

**JSDoc:**
```typescript
/**
	 * Returns the references to this node which is by default `this`.
	 *
	 * @return {Node} A reference to this node.
	 */
```

**Returns:** `Node`

<details><summary>Code</summary>

```typescript
getScope() {

		return this;

	}
```
</details>

### `Node.getHash(): string`

**JSDoc:**
```typescript
/**
	 * Returns the hash of the node which is used to identify the node. By default it's
	 * the {@link Node#uuid} however derived node classes might have to overwrite this method
	 * depending on their implementation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The hash.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getHash( /*builder*/ ) {

		return this.uuid;

	}
```
</details>

### `Node.getUpdateType(): { NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

**JSDoc:**
```typescript
/**
	 * Returns the update type of {@link Node#update}.
	 *
	 * @return {NodeUpdateType} The update type.
	 */
```

**Returns:** `{ NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

<details><summary>Code</summary>

```typescript
getUpdateType() {

		return this.updateType;

	}
```
</details>

### `Node.getUpdateBeforeType(): { NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

**JSDoc:**
```typescript
/**
	 * Returns the update type of {@link Node#updateBefore}.
	 *
	 * @return {NodeUpdateType} The update type.
	 */
```

**Returns:** `{ NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

<details><summary>Code</summary>

```typescript
getUpdateBeforeType() {

		return this.updateBeforeType;

	}
```
</details>

### `Node.getUpdateAfterType(): { NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

**JSDoc:**
```typescript
/**
	 * Returns the update type of {@link Node#updateAfter}.
	 *
	 * @return {NodeUpdateType} The update type.
	 */
```

**Returns:** `{ NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

<details><summary>Code</summary>

```typescript
getUpdateAfterType() {

		return this.updateAfterType;

	}
```
</details>

### `Node.getElementType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Certain types are composed of multiple elements. For example a `vec3`
	 * is composed of three `float` values. This method returns the type of
	 * these elements.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The type of the node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getNodeType`
- `builder.getElementType`

<details><summary>Code</summary>

```typescript
getElementType( builder ) {

		const type = this.getNodeType( builder );
		const elementType = builder.getElementType( type );

		return elementType;

	}
```
</details>

### `Node.getMemberType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the node member type for the given name.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} name - The name of the member.
	 * @return {string} The type of the node.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getMemberType( /*builder, name*/ ) {

		return 'void';

	}
```
</details>

### `Node.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Returns the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The type of the node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.getNodeProperties`
- `nodeProperties.outputNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		const nodeProperties = builder.getNodeProperties( this );

		if ( nodeProperties.outputNode ) {

			return nodeProperties.outputNode.getNodeType( builder );

		}

		return this.nodeType;

	}
```
</details>

### `Node.getShared(builder: NodeBuilder): Node`

**JSDoc:**
```typescript
/**
	 * This method is used during the build process of a node and ensures
	 * equal nodes are not built multiple times but just once. For example if
	 * `attribute( 'uv' )` is used multiple times by the user, the build
	 * process makes sure to process just the first node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The shared node if possible. Otherwise `this` is returned.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `Node`

**Calls:**

- `this.getHash`
- `builder.getNodeFromHash`

<details><summary>Code</summary>

```typescript
getShared( builder ) {

		const hash = this.getHash( builder );
		const nodeFromHash = builder.getNodeFromHash( hash );

		return nodeFromHash || this;

	}
```
</details>

### `Node.getArrayCount(): number`

**JSDoc:**
```typescript
/**
	 * Returns the number of elements in the node array.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?number} The number of elements in the node array.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getArrayCount( /*builder*/ ) {

		return null;

	}
```
</details>

### `Node.setup(builder: NodeBuilder): Node`

**JSDoc:**
```typescript
/**
	 * Represents the setup stage which is the first step of the build process, see {@link Node#build} method.
	 * This method is often overwritten in derived modules to prepare the node which is used as a node's output/result.
	 * If an output node is prepared, then it must be returned in the `return` statement of the derived module's setup function.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?Node} The output node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `Node`

**Calls:**

- `builder.getNodeProperties`
- `this.getChildren`

**Internal Comments:**
```
// return a outputNode if exists or null
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const nodeProperties = builder.getNodeProperties( this );

		let index = 0;

		for ( const childNode of this.getChildren() ) {

			nodeProperties[ 'node' + index ++ ] = childNode;

		}

		// return a outputNode if exists or null

		return nodeProperties.outputNode || null;

	}
```
</details>

### `Node.analyze(builder: NodeBuilder, output: Node): void`

**JSDoc:**
```typescript
/**
	 * Represents the analyze stage which is the second step of the build process, see {@link Node#build} method.
	 * This stage analyzes the node hierarchy and ensures descendent nodes are built.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {?Node} output - The target output node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`output`** `Node`

**Returns:** `void`

**Calls:**

- `builder.increaseUsage`
- `builder.getDataFromNode`
- `nodeData.stages[ builder.shaderStage ].push`
- `builder.getNodeProperties`
- `Object.values`
- `childNode.build`

**Internal Comments:**
```
// node flow children (x2)
```

<details><summary>Code</summary>

```typescript
analyze( builder, output = null ) {

		const usageCount = builder.increaseUsage( this );

		if ( this.parents === true ) {

			const nodeData = builder.getDataFromNode( this, 'any' );
			nodeData.stages = nodeData.stages || {};
			nodeData.stages[ builder.shaderStage ] = nodeData.stages[ builder.shaderStage ] || [];
			nodeData.stages[ builder.shaderStage ].push( output );

		}

		if ( usageCount === 1 ) {

			// node flow children

			const nodeProperties = builder.getNodeProperties( this );

			for ( const childNode of Object.values( nodeProperties ) ) {

				if ( childNode && childNode.isNode === true ) {

					childNode.build( builder, this );

				}

			}

		}

	}
```
</details>

### `Node.generate(builder: NodeBuilder, output: string): string`

**JSDoc:**
```typescript
/**
	 * Represents the generate stage which is the third step of the build process, see {@link Node#build} method.
	 * This state builds the output node and returns the resulting shader string.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {?string} output - Can be used to define the output type.
	 * @return {?string} The generated shader string.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`output`** `string`

**Returns:** `string`

**Calls:**

- `builder.getNodeProperties`
- `outputNode.build`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const { outputNode } = builder.getNodeProperties( this );

		if ( outputNode && outputNode.isNode === true ) {

			return outputNode.build( builder, output );

		}

	}
```
</details>

### `Node.updateBefore(): boolean`

**JSDoc:**
```typescript
/**
	 * The method can be implemented to update the node's internal state before it is used to render an object.
	 * The {@link Node#updateBeforeType} property defines how often the update is executed.
	 *
	 * @abstract
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 * @return {?boolean} An optional bool that indicates whether the implementation actually performed an update or not (e.g. due to caching).
	 */
```

**Returns:** `boolean`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
updateBefore( /*frame*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `Node.updateAfter(): boolean`

**JSDoc:**
```typescript
/**
	 * The method can be implemented to update the node's internal state after it was used to render an object.
	 * The {@link Node#updateAfterType} property defines how often the update is executed.
	 *
	 * @abstract
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 * @return {?boolean} An optional bool that indicates whether the implementation actually performed an update or not (e.g. due to caching).
	 */
```

**Returns:** `boolean`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
updateAfter( /*frame*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `Node.update(): boolean`

**JSDoc:**
```typescript
/**
	 * The method can be implemented to update the node's internal state when it is used to render an object.
	 * The {@link Node#updateType} property defines how often the update is executed.
	 *
	 * @abstract
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 * @return {?boolean} An optional bool that indicates whether the implementation actually performed an update or not (e.g. due to caching).
	 */
```

**Returns:** `boolean`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
update( /*frame*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `Node.build(builder: NodeBuilder, output: string | Node): string | Node`

**JSDoc:**
```typescript
/**
	 * This method performs the build of a node. The behavior and return value depend on the current build stage:
	 * - **setup**: Prepares the node and its children for the build process. This process can also create new nodes. Returns the node itself or a variant.
	 * - **analyze**: Analyzes the node hierarchy for optimizations in the code generation stage. Returns `null`.
	 * - **generate**: Generates the shader code for the node. Returns the generated shader string.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string|Node|null} [output=null] - Can be used to define the output type.
	 * @return {Node|string|null} The result of the build process, depending on the build stage.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`output`** `string | Node`

**Returns:** `string | Node`

**Calls:**

- `this.getShared`
- `refNode.build`
- `builder.getDataFromNode`
- `builder.getBuildStage`
- `builder.setBuildStage`
- `this.build`
- `builder.addNode`
- `builder.addChain`
- `this.updateReference`
- `builder.getNodeProperties`
- `this.setup`
- `Object.values`
- `childProperties.parents.push`
- `childNode.build`
- `this.analyze`
- `this.getNodeType`
- `this.generate`
- `console.warn`
- `builder.addFlowCodeHierarchy`
- `builder.format`
- `console.error`
- `builder.generateConst`
- `builder.removeChain`
- `builder.addSequentialNode`

**Internal Comments:**
```
// (x6)
// force parent build stage (setup or analyze) (x2)
/* Build stages expected results:
			- "setup"		-> Node
			- "analyze"		-> null
			- "generate"	-> String
		*/ (x2)
//const stackNodesBeforeSetup = builder.stack.nodes.length; (x4)
/*if ( isNodeOutput && builder.stack.nodes.length !== stackNodesBeforeSetup ) {

					// !! no outputNode !!
					//outputNode = builder.stack;

				}*/
// if no snippet is generated, return a default value (x4)
```

<details><summary>Code</summary>

```typescript
build( builder, output = null ) {

		const refNode = this.getShared( builder );

		if ( this !== refNode ) {

			return refNode.build( builder, output );

		}

		//

		const nodeData = builder.getDataFromNode( this );
		nodeData.buildStages = nodeData.buildStages || {};
		nodeData.buildStages[ builder.buildStage ] = true;

		const parentBuildStage = _parentBuildStage[ builder.buildStage ];

		if ( parentBuildStage && nodeData.buildStages[ parentBuildStage ] !== true ) {

			// force parent build stage (setup or analyze)

			const previousBuildStage = builder.getBuildStage();

			builder.setBuildStage( parentBuildStage );

			this.build( builder );

			builder.setBuildStage( previousBuildStage );

		}

		//

		builder.addNode( this );
		builder.addChain( this );

		/* Build stages expected results:
			- "setup"		-> Node
			- "analyze"		-> null
			- "generate"	-> String
		*/
		let result = null;

		const buildStage = builder.getBuildStage();

		if ( buildStage === 'setup' ) {

			this.updateReference( builder );

			const properties = builder.getNodeProperties( this );

			if ( properties.initialized !== true ) {

				//const stackNodesBeforeSetup = builder.stack.nodes.length;

				properties.initialized = true;
				properties.outputNode = this.setup( builder ) || properties.outputNode || null;

				/*if ( isNodeOutput && builder.stack.nodes.length !== stackNodesBeforeSetup ) {

					// !! no outputNode !!
					//outputNode = builder.stack;

				}*/

				for ( const childNode of Object.values( properties ) ) {

					if ( childNode && childNode.isNode === true ) {

						if ( childNode.parents === true ) {

							const childProperties = builder.getNodeProperties( childNode );
							childProperties.parents = childProperties.parents || [];
							childProperties.parents.push( this );

						}

						childNode.build( builder );

					}

				}

			}

			result = properties.outputNode;

		} else if ( buildStage === 'analyze' ) {

			this.analyze( builder, output );

		} else if ( buildStage === 'generate' ) {

			const isGenerateOnce = this.generate.length === 1;

			if ( isGenerateOnce ) {

				const type = this.getNodeType( builder );
				const nodeData = builder.getDataFromNode( this );

				result = nodeData.snippet;

				if ( result === undefined ) {

					if ( nodeData.generated === undefined ) {

						nodeData.generated = true;

						result = this.generate( builder ) || '';

						nodeData.snippet = result;

					} else {

						console.warn( 'THREE.Node: Recursion detected.', this );

						result = '/* Recursion detected. */';

					}

				} else if ( nodeData.flowCodes !== undefined && builder.context.nodeBlock !== undefined ) {

					builder.addFlowCodeHierarchy( this, builder.context.nodeBlock );

				}

				result = builder.format( result, type, output );

			} else {

				result = this.generate( builder, output ) || '';

			}

			if ( result === '' && output !== null && output !== 'void' && output !== 'OutputType' ) {

				// if no snippet is generated, return a default value

				console.error( `THREE.TSL: Invalid generated code, expected a "${ output }".` );

				result = builder.generateConst( output );

			}

		}

		builder.removeChain( this );
		builder.addSequentialNode( this );

		return result;

	}
```
</details>

### `Node.getSerializeChildren(): any[]`

**JSDoc:**
```typescript
/**
	 * Returns the child nodes as a JSON object.
	 *
	 * @return {Array<Object>} An iterable list of serialized child objects as JSON.
	 */
```

**Returns:** `any[]`

**Calls:**

- `getNodeChildren (from ./NodeUtils.js)`

<details><summary>Code</summary>

```typescript
getSerializeChildren() {

		return getNodeChildren( this );

	}
```
</details>

### `Node.serialize(json: any): void`

**JSDoc:**
```typescript
/**
	 * Serializes the node to JSON.
	 *
	 * @param {Object} json - The output JSON object.
	 */
```

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `this.getSerializeChildren`
- `Number.isInteger`
- `childNode.toJSON`
- `Object.keys`

<details><summary>Code</summary>

```typescript
serialize( json ) {

		const nodeChildren = this.getSerializeChildren();

		const inputNodes = {};

		for ( const { property, index, childNode } of nodeChildren ) {

			if ( index !== undefined ) {

				if ( inputNodes[ property ] === undefined ) {

					inputNodes[ property ] = Number.isInteger( index ) ? [] : {};

				}

				inputNodes[ property ][ index ] = childNode.toJSON( json.meta ).uuid;

			} else {

				inputNodes[ property ] = childNode.toJSON( json.meta ).uuid;

			}

		}

		if ( Object.keys( inputNodes ).length > 0 ) {

			json.inputNodes = inputNodes;

		}

	}
```
</details>

### `Node.deserialize(json: any): void`

**JSDoc:**
```typescript
/**
	 * Deserializes the node from the given JSON.
	 *
	 * @param {Object} json - The JSON object.
	 */
```

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `inputArray.push`

<details><summary>Code</summary>

```typescript
deserialize( json ) {

		if ( json.inputNodes !== undefined ) {

			const nodes = json.meta.nodes;

			for ( const property in json.inputNodes ) {

				if ( Array.isArray( json.inputNodes[ property ] ) ) {

					const inputArray = [];

					for ( const uuid of json.inputNodes[ property ] ) {

						inputArray.push( nodes[ uuid ] );

					}

					this[ property ] = inputArray;

				} else if ( typeof json.inputNodes[ property ] === 'object' ) {

					const inputObject = {};

					for ( const subProperty in json.inputNodes[ property ] ) {

						const uuid = json.inputNodes[ property ][ subProperty ];

						inputObject[ subProperty ] = nodes[ uuid ];

					}

					this[ property ] = inputObject;

				} else {

					const uuid = json.inputNodes[ property ];

					this[ property ] = nodes[ uuid ];

				}

			}

		}

	}
```
</details>

### `Node.toJSON(meta: any): any`

**JSDoc:**
```typescript
/**
	 * Serializes the node into the three.js JSON Object/Scene format.
	 *
	 * @param {?Object} meta - An optional JSON object that already holds serialized data from other scene objects.
	 * @return {Object} The serialized node.
	 */
```

**Parameters:**

- **`meta`** `any`

**Returns:** `any`

**Calls:**

- `this.serialize`
- `values.push`
- `extractFromCache`

**Internal Comments:**
```
// serialize (x2)
// TODO: Copied from Object3D.toJSON
```

<details><summary>Code</summary>

```typescript
toJSON( meta ) {

		const { uuid, type } = this;
		const isRoot = ( meta === undefined || typeof meta === 'string' );

		if ( isRoot ) {

			meta = {
				textures: {},
				images: {},
				nodes: {}
			};

		}

		// serialize

		let data = meta.nodes[ uuid ];

		if ( data === undefined ) {

			data = {
				uuid,
				type,
				meta,
				metadata: {
					version: 4.7,
					type: 'Node',
					generator: 'Node.toJSON'
				}
			};

			if ( isRoot !== true ) meta.nodes[ data.uuid ] = data;

			this.serialize( data );

			delete data.meta;

		}

		// TODO: Copied from Object3D.toJSON

		function extractFromCache( cache ) {

			const values = [];

			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}

		if ( isRoot ) {

			const textures = extractFromCache( meta.textures );
			const images = extractFromCache( meta.images );
			const nodes = extractFromCache( meta.nodes );

			if ( textures.length > 0 ) data.textures = textures;
			if ( images.length > 0 ) data.images = images;
			if ( nodes.length > 0 ) data.nodes = nodes;

		}

		return data;

	}
```
</details>

### `extractFromCache(cache: any): any[]`

**Parameters:**

- **`cache`** `any`

**Returns:** `any[]`

**Calls:**

- `values.push`

<details><summary>Code</summary>

```typescript
function extractFromCache( cache ) {

			const values = [];

			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}
```
</details>


---

## Classes

### `Node`

<details><summary>Class Code</summary>

```ts
class Node extends EventDispatcher {

	static get type() {

		return 'Node';

	}

	/**
	 * Constructs a new node.
	 *
	 * @param {?string} nodeType - The node type.
	 */
	constructor( nodeType = null ) {

		super();

		/**
		 * The node type. This represents the result type of the node (e.g. `float` or `vec3`).
		 *
		 * @type {?string}
		 * @default null
		 */
		this.nodeType = nodeType;

		/**
		 * The update type of the node's {@link Node#update} method. Possible values are listed in {@link NodeUpdateType}.
		 *
		 * @type {string}
		 * @default 'none'
		 */
		this.updateType = NodeUpdateType.NONE;

		/**
		 * The update type of the node's {@link Node#updateBefore} method. Possible values are listed in {@link NodeUpdateType}.
		 *
		 * @type {string}
		 * @default 'none'
		 */
		this.updateBeforeType = NodeUpdateType.NONE;

		/**
		 * The update type of the node's {@link Node#updateAfter} method. Possible values are listed in {@link NodeUpdateType}.
		 *
		 * @type {string}
		 * @default 'none'
		 */
		this.updateAfterType = NodeUpdateType.NONE;

		/**
		 * The UUID of the node.
		 *
		 * @type {string}
		 * @readonly
		 */
		this.uuid = MathUtils.generateUUID();

		/**
		 * The version of the node. The version automatically is increased when {@link Node#needsUpdate} is set to `true`.
		 *
		 * @type {number}
		 * @readonly
		 * @default 0
		 */
		this.version = 0;

		/**
		 * Whether this node is global or not. This property is relevant for the internal
		 * node caching system. All nodes which should be declared just once should
		 * set this flag to `true` (a typical example is {@link AttributeNode}).
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.global = false;

		/**
		 * Create a list of parents for this node during the build process.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.parents = false;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isNode = true;

		// private

		/**
		 * The cache key of this node.
		 *
		 * @private
		 * @type {?number}
		 * @default null
		 */
		this._cacheKey = null;

		/**
		 * The cache key 's version.
		 *
		 * @private
		 * @type {number}
		 * @default 0
		 */
		this._cacheKeyVersion = 0;

		Object.defineProperty( this, 'id', { value: _nodeId ++ } );

	}

	/**
	 * Set this property to `true` when the node should be regenerated.
	 *
	 * @type {boolean}
	 * @default false
	 * @param {boolean} value
	 */
	set needsUpdate( value ) {

		if ( value === true ) {

			this.version ++;

		}

	}

	/**
	 * The type of the class. The value is usually the constructor name.
	 *
	 * @type {string}
 	 * @readonly
	 */
	get type() {

		return this.constructor.type;

	}

	/**
	 * Convenient method for defining {@link Node#update}.
	 *
	 * @param {Function} callback - The update method.
	 * @param {string} updateType - The update type.
	 * @return {Node} A reference to this node.
	 */
	onUpdate( callback, updateType ) {

		this.updateType = updateType;
		this.update = callback.bind( this.getSelf() );

		return this;

	}

	/**
	 * Convenient method for defining {@link Node#update}. Similar to {@link Node#onUpdate}, but
	 * this method automatically sets the update type to `FRAME`.
	 *
	 * @param {Function} callback - The update method.
	 * @return {Node} A reference to this node.
	 */
	onFrameUpdate( callback ) {

		return this.onUpdate( callback, NodeUpdateType.FRAME );

	}

	/**
	 * Convenient method for defining {@link Node#update}. Similar to {@link Node#onUpdate}, but
	 * this method automatically sets the update type to `RENDER`.
	 *
	 * @param {Function} callback - The update method.
	 * @return {Node} A reference to this node.
	 */
	onRenderUpdate( callback ) {

		return this.onUpdate( callback, NodeUpdateType.RENDER );

	}

	/**
	 * Convenient method for defining {@link Node#update}. Similar to {@link Node#onUpdate}, but
	 * this method automatically sets the update type to `OBJECT`.
	 *
	 * @param {Function} callback - The update method.
	 * @return {Node} A reference to this node.
	 */
	onObjectUpdate( callback ) {

		return this.onUpdate( callback, NodeUpdateType.OBJECT );

	}

	/**
	 * Convenient method for defining {@link Node#updateReference}.
	 *
	 * @param {Function} callback - The update method.
	 * @return {Node} A reference to this node.
	 */
	onReference( callback ) {

		this.updateReference = callback.bind( this.getSelf() );

		return this;

	}

	/**
	 * The `this` reference might point to a Proxy so this method can be used
	 * to get the reference to the actual node instance.
	 *
	 * @return {Node} A reference to the node.
	 */
	getSelf() {

		// Returns non-node object.

		return this.self || this;

	}

	/**
	 * Nodes might refer to other objects like materials. This method allows to dynamically update the reference
	 * to such objects based on a given state (e.g. the current node frame or builder).
	 *
	 * @param {any} state - This method can be invocated in different contexts so `state` can refer to any object type.
	 * @return {any} The updated reference.
	 */
	updateReference( /*state*/ ) {

		return this;

	}

	/**
	 * By default this method returns the value of the {@link Node#global} flag. This method
	 * can be overwritten in derived classes if an analytical way is required to determine the
	 * global cache referring to the current shader-stage.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {boolean} Whether this node is global or not.
	 */
	isGlobal( /*builder*/ ) {

		return this.global;

	}

	/**
	 * Generator function that can be used to iterate over the child nodes.
	 *
	 * @generator
	 * @yields {Node} A child node.
	 */
	* getChildren() {

		for ( const { childNode } of getNodeChildren( this ) ) {

			yield childNode;

		}

	}

	/**
	 * Calling this method dispatches the `dispose` event. This event can be used
	 * to register event listeners for clean up tasks.
	 */
	dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}

	/**
	 * Callback for {@link Node#traverse}.
	 *
	 * @callback traverseCallback
	 * @param {Node} node - The current node.
	 */

	/**
	 * Can be used to traverse through the node's hierarchy.
	 *
	 * @param {traverseCallback} callback - A callback that is executed per node.
	 */
	traverse( callback ) {

		callback( this );

		for ( const childNode of this.getChildren() ) {

			childNode.traverse( callback );

		}

	}

	/**
	 * Returns the cache key for this node.
	 *
	 * @param {boolean} [force=false] - When set to `true`, a recomputation of the cache key is forced.
	 * @return {number} The cache key of the node.
	 */
	getCacheKey( force = false ) {

		force = force || this.version !== this._cacheKeyVersion;

		if ( force === true || this._cacheKey === null ) {

			this._cacheKey = hash( getCacheKey( this, force ), this.customCacheKey() );
			this._cacheKeyVersion = this.version;

		}

		return this._cacheKey;

	}

	/**
	 * Generate a custom cache key for this node.
	 *
	 * @return {number} The cache key of the node.
	 */
	customCacheKey() {

		return 0;

	}

	/**
	 * Returns the references to this node which is by default `this`.
	 *
	 * @return {Node} A reference to this node.
	 */
	getScope() {

		return this;

	}

	/**
	 * Returns the hash of the node which is used to identify the node. By default it's
	 * the {@link Node#uuid} however derived node classes might have to overwrite this method
	 * depending on their implementation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The hash.
	 */
	getHash( /*builder*/ ) {

		return this.uuid;

	}

	/**
	 * Returns the update type of {@link Node#update}.
	 *
	 * @return {NodeUpdateType} The update type.
	 */
	getUpdateType() {

		return this.updateType;

	}

	/**
	 * Returns the update type of {@link Node#updateBefore}.
	 *
	 * @return {NodeUpdateType} The update type.
	 */
	getUpdateBeforeType() {

		return this.updateBeforeType;

	}

	/**
	 * Returns the update type of {@link Node#updateAfter}.
	 *
	 * @return {NodeUpdateType} The update type.
	 */
	getUpdateAfterType() {

		return this.updateAfterType;

	}

	/**
	 * Certain types are composed of multiple elements. For example a `vec3`
	 * is composed of three `float` values. This method returns the type of
	 * these elements.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The type of the node.
	 */
	getElementType( builder ) {

		const type = this.getNodeType( builder );
		const elementType = builder.getElementType( type );

		return elementType;

	}

	/**
	 * Returns the node member type for the given name.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} name - The name of the member.
	 * @return {string} The type of the node.
	 */
	getMemberType( /*builder, name*/ ) {

		return 'void';

	}

	/**
	 * Returns the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The type of the node.
	 */
	getNodeType( builder ) {

		const nodeProperties = builder.getNodeProperties( this );

		if ( nodeProperties.outputNode ) {

			return nodeProperties.outputNode.getNodeType( builder );

		}

		return this.nodeType;

	}

	/**
	 * This method is used during the build process of a node and ensures
	 * equal nodes are not built multiple times but just once. For example if
	 * `attribute( 'uv' )` is used multiple times by the user, the build
	 * process makes sure to process just the first node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The shared node if possible. Otherwise `this` is returned.
	 */
	getShared( builder ) {

		const hash = this.getHash( builder );
		const nodeFromHash = builder.getNodeFromHash( hash );

		return nodeFromHash || this;

	}

	/**
	 * Returns the number of elements in the node array.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?number} The number of elements in the node array.
	 */
	getArrayCount( /*builder*/ ) {

		return null;

	}

	/**
	 * Represents the setup stage which is the first step of the build process, see {@link Node#build} method.
	 * This method is often overwritten in derived modules to prepare the node which is used as a node's output/result.
	 * If an output node is prepared, then it must be returned in the `return` statement of the derived module's setup function.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?Node} The output node.
	 */
	setup( builder ) {

		const nodeProperties = builder.getNodeProperties( this );

		let index = 0;

		for ( const childNode of this.getChildren() ) {

			nodeProperties[ 'node' + index ++ ] = childNode;

		}

		// return a outputNode if exists or null

		return nodeProperties.outputNode || null;

	}

	/**
	 * Represents the analyze stage which is the second step of the build process, see {@link Node#build} method.
	 * This stage analyzes the node hierarchy and ensures descendent nodes are built.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {?Node} output - The target output node.
	 */
	analyze( builder, output = null ) {

		const usageCount = builder.increaseUsage( this );

		if ( this.parents === true ) {

			const nodeData = builder.getDataFromNode( this, 'any' );
			nodeData.stages = nodeData.stages || {};
			nodeData.stages[ builder.shaderStage ] = nodeData.stages[ builder.shaderStage ] || [];
			nodeData.stages[ builder.shaderStage ].push( output );

		}

		if ( usageCount === 1 ) {

			// node flow children

			const nodeProperties = builder.getNodeProperties( this );

			for ( const childNode of Object.values( nodeProperties ) ) {

				if ( childNode && childNode.isNode === true ) {

					childNode.build( builder, this );

				}

			}

		}

	}

	/**
	 * Represents the generate stage which is the third step of the build process, see {@link Node#build} method.
	 * This state builds the output node and returns the resulting shader string.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {?string} output - Can be used to define the output type.
	 * @return {?string} The generated shader string.
	 */
	generate( builder, output ) {

		const { outputNode } = builder.getNodeProperties( this );

		if ( outputNode && outputNode.isNode === true ) {

			return outputNode.build( builder, output );

		}

	}

	/**
	 * The method can be implemented to update the node's internal state before it is used to render an object.
	 * The {@link Node#updateBeforeType} property defines how often the update is executed.
	 *
	 * @abstract
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 * @return {?boolean} An optional bool that indicates whether the implementation actually performed an update or not (e.g. due to caching).
	 */
	updateBefore( /*frame*/ ) {

		console.warn( 'Abstract function.' );

	}

	/**
	 * The method can be implemented to update the node's internal state after it was used to render an object.
	 * The {@link Node#updateAfterType} property defines how often the update is executed.
	 *
	 * @abstract
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 * @return {?boolean} An optional bool that indicates whether the implementation actually performed an update or not (e.g. due to caching).
	 */
	updateAfter( /*frame*/ ) {

		console.warn( 'Abstract function.' );

	}

	/**
	 * The method can be implemented to update the node's internal state when it is used to render an object.
	 * The {@link Node#updateType} property defines how often the update is executed.
	 *
	 * @abstract
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 * @return {?boolean} An optional bool that indicates whether the implementation actually performed an update or not (e.g. due to caching).
	 */
	update( /*frame*/ ) {

		console.warn( 'Abstract function.' );

	}

	/**
	 * This method performs the build of a node. The behavior and return value depend on the current build stage:
	 * - **setup**: Prepares the node and its children for the build process. This process can also create new nodes. Returns the node itself or a variant.
	 * - **analyze**: Analyzes the node hierarchy for optimizations in the code generation stage. Returns `null`.
	 * - **generate**: Generates the shader code for the node. Returns the generated shader string.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string|Node|null} [output=null] - Can be used to define the output type.
	 * @return {Node|string|null} The result of the build process, depending on the build stage.
	 */
	build( builder, output = null ) {

		const refNode = this.getShared( builder );

		if ( this !== refNode ) {

			return refNode.build( builder, output );

		}

		//

		const nodeData = builder.getDataFromNode( this );
		nodeData.buildStages = nodeData.buildStages || {};
		nodeData.buildStages[ builder.buildStage ] = true;

		const parentBuildStage = _parentBuildStage[ builder.buildStage ];

		if ( parentBuildStage && nodeData.buildStages[ parentBuildStage ] !== true ) {

			// force parent build stage (setup or analyze)

			const previousBuildStage = builder.getBuildStage();

			builder.setBuildStage( parentBuildStage );

			this.build( builder );

			builder.setBuildStage( previousBuildStage );

		}

		//

		builder.addNode( this );
		builder.addChain( this );

		/* Build stages expected results:
			- "setup"		-> Node
			- "analyze"		-> null
			- "generate"	-> String
		*/
		let result = null;

		const buildStage = builder.getBuildStage();

		if ( buildStage === 'setup' ) {

			this.updateReference( builder );

			const properties = builder.getNodeProperties( this );

			if ( properties.initialized !== true ) {

				//const stackNodesBeforeSetup = builder.stack.nodes.length;

				properties.initialized = true;
				properties.outputNode = this.setup( builder ) || properties.outputNode || null;

				/*if ( isNodeOutput && builder.stack.nodes.length !== stackNodesBeforeSetup ) {

					// !! no outputNode !!
					//outputNode = builder.stack;

				}*/

				for ( const childNode of Object.values( properties ) ) {

					if ( childNode && childNode.isNode === true ) {

						if ( childNode.parents === true ) {

							const childProperties = builder.getNodeProperties( childNode );
							childProperties.parents = childProperties.parents || [];
							childProperties.parents.push( this );

						}

						childNode.build( builder );

					}

				}

			}

			result = properties.outputNode;

		} else if ( buildStage === 'analyze' ) {

			this.analyze( builder, output );

		} else if ( buildStage === 'generate' ) {

			const isGenerateOnce = this.generate.length === 1;

			if ( isGenerateOnce ) {

				const type = this.getNodeType( builder );
				const nodeData = builder.getDataFromNode( this );

				result = nodeData.snippet;

				if ( result === undefined ) {

					if ( nodeData.generated === undefined ) {

						nodeData.generated = true;

						result = this.generate( builder ) || '';

						nodeData.snippet = result;

					} else {

						console.warn( 'THREE.Node: Recursion detected.', this );

						result = '/* Recursion detected. */';

					}

				} else if ( nodeData.flowCodes !== undefined && builder.context.nodeBlock !== undefined ) {

					builder.addFlowCodeHierarchy( this, builder.context.nodeBlock );

				}

				result = builder.format( result, type, output );

			} else {

				result = this.generate( builder, output ) || '';

			}

			if ( result === '' && output !== null && output !== 'void' && output !== 'OutputType' ) {

				// if no snippet is generated, return a default value

				console.error( `THREE.TSL: Invalid generated code, expected a "${ output }".` );

				result = builder.generateConst( output );

			}

		}

		builder.removeChain( this );
		builder.addSequentialNode( this );

		return result;

	}

	/**
	 * Returns the child nodes as a JSON object.
	 *
	 * @return {Array<Object>} An iterable list of serialized child objects as JSON.
	 */
	getSerializeChildren() {

		return getNodeChildren( this );

	}

	/**
	 * Serializes the node to JSON.
	 *
	 * @param {Object} json - The output JSON object.
	 */
	serialize( json ) {

		const nodeChildren = this.getSerializeChildren();

		const inputNodes = {};

		for ( const { property, index, childNode } of nodeChildren ) {

			if ( index !== undefined ) {

				if ( inputNodes[ property ] === undefined ) {

					inputNodes[ property ] = Number.isInteger( index ) ? [] : {};

				}

				inputNodes[ property ][ index ] = childNode.toJSON( json.meta ).uuid;

			} else {

				inputNodes[ property ] = childNode.toJSON( json.meta ).uuid;

			}

		}

		if ( Object.keys( inputNodes ).length > 0 ) {

			json.inputNodes = inputNodes;

		}

	}

	/**
	 * Deserializes the node from the given JSON.
	 *
	 * @param {Object} json - The JSON object.
	 */
	deserialize( json ) {

		if ( json.inputNodes !== undefined ) {

			const nodes = json.meta.nodes;

			for ( const property in json.inputNodes ) {

				if ( Array.isArray( json.inputNodes[ property ] ) ) {

					const inputArray = [];

					for ( const uuid of json.inputNodes[ property ] ) {

						inputArray.push( nodes[ uuid ] );

					}

					this[ property ] = inputArray;

				} else if ( typeof json.inputNodes[ property ] === 'object' ) {

					const inputObject = {};

					for ( const subProperty in json.inputNodes[ property ] ) {

						const uuid = json.inputNodes[ property ][ subProperty ];

						inputObject[ subProperty ] = nodes[ uuid ];

					}

					this[ property ] = inputObject;

				} else {

					const uuid = json.inputNodes[ property ];

					this[ property ] = nodes[ uuid ];

				}

			}

		}

	}

	/**
	 * Serializes the node into the three.js JSON Object/Scene format.
	 *
	 * @param {?Object} meta - An optional JSON object that already holds serialized data from other scene objects.
	 * @return {Object} The serialized node.
	 */
	toJSON( meta ) {

		const { uuid, type } = this;
		const isRoot = ( meta === undefined || typeof meta === 'string' );

		if ( isRoot ) {

			meta = {
				textures: {},
				images: {},
				nodes: {}
			};

		}

		// serialize

		let data = meta.nodes[ uuid ];

		if ( data === undefined ) {

			data = {
				uuid,
				type,
				meta,
				metadata: {
					version: 4.7,
					type: 'Node',
					generator: 'Node.toJSON'
				}
			};

			if ( isRoot !== true ) meta.nodes[ data.uuid ] = data;

			this.serialize( data );

			delete data.meta;

		}

		// TODO: Copied from Object3D.toJSON

		function extractFromCache( cache ) {

			const values = [];

			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}

		if ( isRoot ) {

			const textures = extractFromCache( meta.textures );
			const images = extractFromCache( meta.images );
			const nodes = extractFromCache( meta.nodes );

			if ( textures.length > 0 ) data.textures = textures;
			if ( images.length > 0 ) data.images = images;
			if ( nodes.length > 0 ) data.nodes = nodes;

		}

		return data;

	}

}
```
</details>

#### Methods

##### `onUpdate(callback: Function, updateType: string): Node`

<details><summary>Code</summary>

```ts
onUpdate( callback, updateType ) {

		this.updateType = updateType;
		this.update = callback.bind( this.getSelf() );

		return this;

	}
```
</details>

##### `onFrameUpdate(callback: Function): Node`

<details><summary>Code</summary>

```ts
onFrameUpdate( callback ) {

		return this.onUpdate( callback, NodeUpdateType.FRAME );

	}
```
</details>

##### `onRenderUpdate(callback: Function): Node`

<details><summary>Code</summary>

```ts
onRenderUpdate( callback ) {

		return this.onUpdate( callback, NodeUpdateType.RENDER );

	}
```
</details>

##### `onObjectUpdate(callback: Function): Node`

<details><summary>Code</summary>

```ts
onObjectUpdate( callback ) {

		return this.onUpdate( callback, NodeUpdateType.OBJECT );

	}
```
</details>

##### `onReference(callback: Function): Node`

<details><summary>Code</summary>

```ts
onReference( callback ) {

		this.updateReference = callback.bind( this.getSelf() );

		return this;

	}
```
</details>

##### `getSelf(): Node`

<details><summary>Code</summary>

```ts
getSelf() {

		// Returns non-node object.

		return this.self || this;

	}
```
</details>

##### `updateReference(): any`

<details><summary>Code</summary>

```ts
updateReference( /*state*/ ) {

		return this;

	}
```
</details>

##### `isGlobal(): boolean`

<details><summary>Code</summary>

```ts
isGlobal( /*builder*/ ) {

		return this.global;

	}
```
</details>

##### `getChildren(): Generator<any, void, unknown>`

<details><summary>Code</summary>

```ts
* getChildren() {

		for ( const { childNode } of getNodeChildren( this ) ) {

			yield childNode;

		}

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}
```
</details>

##### `traverse(callback: traverseCallback): void`

<details><summary>Code</summary>

```ts
traverse( callback ) {

		callback( this );

		for ( const childNode of this.getChildren() ) {

			childNode.traverse( callback );

		}

	}
```
</details>

##### `getCacheKey(force: boolean): number`

<details><summary>Code</summary>

```ts
getCacheKey( force = false ) {

		force = force || this.version !== this._cacheKeyVersion;

		if ( force === true || this._cacheKey === null ) {

			this._cacheKey = hash( getCacheKey( this, force ), this.customCacheKey() );
			this._cacheKeyVersion = this.version;

		}

		return this._cacheKey;

	}
```
</details>

##### `customCacheKey(): number`

<details><summary>Code</summary>

```ts
customCacheKey() {

		return 0;

	}
```
</details>

##### `getScope(): Node`

<details><summary>Code</summary>

```ts
getScope() {

		return this;

	}
```
</details>

##### `getHash(): string`

<details><summary>Code</summary>

```ts
getHash( /*builder*/ ) {

		return this.uuid;

	}
```
</details>

##### `getUpdateType(): { NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

<details><summary>Code</summary>

```ts
getUpdateType() {

		return this.updateType;

	}
```
</details>

##### `getUpdateBeforeType(): { NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

<details><summary>Code</summary>

```ts
getUpdateBeforeType() {

		return this.updateBeforeType;

	}
```
</details>

##### `getUpdateAfterType(): { NONE: string; FRAME: string; RENDER: string; OBJECT: string; }`

<details><summary>Code</summary>

```ts
getUpdateAfterType() {

		return this.updateAfterType;

	}
```
</details>

##### `getElementType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getElementType( builder ) {

		const type = this.getNodeType( builder );
		const elementType = builder.getElementType( type );

		return elementType;

	}
```
</details>

##### `getMemberType(): string`

<details><summary>Code</summary>

```ts
getMemberType( /*builder, name*/ ) {

		return 'void';

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		const nodeProperties = builder.getNodeProperties( this );

		if ( nodeProperties.outputNode ) {

			return nodeProperties.outputNode.getNodeType( builder );

		}

		return this.nodeType;

	}
```
</details>

##### `getShared(builder: NodeBuilder): Node`

<details><summary>Code</summary>

```ts
getShared( builder ) {

		const hash = this.getHash( builder );
		const nodeFromHash = builder.getNodeFromHash( hash );

		return nodeFromHash || this;

	}
```
</details>

##### `getArrayCount(): number`

<details><summary>Code</summary>

```ts
getArrayCount( /*builder*/ ) {

		return null;

	}
```
</details>

##### `setup(builder: NodeBuilder): Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const nodeProperties = builder.getNodeProperties( this );

		let index = 0;

		for ( const childNode of this.getChildren() ) {

			nodeProperties[ 'node' + index ++ ] = childNode;

		}

		// return a outputNode if exists or null

		return nodeProperties.outputNode || null;

	}
```
</details>

##### `analyze(builder: NodeBuilder, output: Node): void`

<details><summary>Code</summary>

```ts
analyze( builder, output = null ) {

		const usageCount = builder.increaseUsage( this );

		if ( this.parents === true ) {

			const nodeData = builder.getDataFromNode( this, 'any' );
			nodeData.stages = nodeData.stages || {};
			nodeData.stages[ builder.shaderStage ] = nodeData.stages[ builder.shaderStage ] || [];
			nodeData.stages[ builder.shaderStage ].push( output );

		}

		if ( usageCount === 1 ) {

			// node flow children

			const nodeProperties = builder.getNodeProperties( this );

			for ( const childNode of Object.values( nodeProperties ) ) {

				if ( childNode && childNode.isNode === true ) {

					childNode.build( builder, this );

				}

			}

		}

	}
```
</details>

##### `generate(builder: NodeBuilder, output: string): string`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const { outputNode } = builder.getNodeProperties( this );

		if ( outputNode && outputNode.isNode === true ) {

			return outputNode.build( builder, output );

		}

	}
```
</details>

##### `updateBefore(): boolean`

<details><summary>Code</summary>

```ts
updateBefore( /*frame*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `updateAfter(): boolean`

<details><summary>Code</summary>

```ts
updateAfter( /*frame*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `update(): boolean`

<details><summary>Code</summary>

```ts
update( /*frame*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `build(builder: NodeBuilder, output: string | Node): string | Node`

<details><summary>Code</summary>

```ts
build( builder, output = null ) {

		const refNode = this.getShared( builder );

		if ( this !== refNode ) {

			return refNode.build( builder, output );

		}

		//

		const nodeData = builder.getDataFromNode( this );
		nodeData.buildStages = nodeData.buildStages || {};
		nodeData.buildStages[ builder.buildStage ] = true;

		const parentBuildStage = _parentBuildStage[ builder.buildStage ];

		if ( parentBuildStage && nodeData.buildStages[ parentBuildStage ] !== true ) {

			// force parent build stage (setup or analyze)

			const previousBuildStage = builder.getBuildStage();

			builder.setBuildStage( parentBuildStage );

			this.build( builder );

			builder.setBuildStage( previousBuildStage );

		}

		//

		builder.addNode( this );
		builder.addChain( this );

		/* Build stages expected results:
			- "setup"		-> Node
			- "analyze"		-> null
			- "generate"	-> String
		*/
		let result = null;

		const buildStage = builder.getBuildStage();

		if ( buildStage === 'setup' ) {

			this.updateReference( builder );

			const properties = builder.getNodeProperties( this );

			if ( properties.initialized !== true ) {

				//const stackNodesBeforeSetup = builder.stack.nodes.length;

				properties.initialized = true;
				properties.outputNode = this.setup( builder ) || properties.outputNode || null;

				/*if ( isNodeOutput && builder.stack.nodes.length !== stackNodesBeforeSetup ) {

					// !! no outputNode !!
					//outputNode = builder.stack;

				}*/

				for ( const childNode of Object.values( properties ) ) {

					if ( childNode && childNode.isNode === true ) {

						if ( childNode.parents === true ) {

							const childProperties = builder.getNodeProperties( childNode );
							childProperties.parents = childProperties.parents || [];
							childProperties.parents.push( this );

						}

						childNode.build( builder );

					}

				}

			}

			result = properties.outputNode;

		} else if ( buildStage === 'analyze' ) {

			this.analyze( builder, output );

		} else if ( buildStage === 'generate' ) {

			const isGenerateOnce = this.generate.length === 1;

			if ( isGenerateOnce ) {

				const type = this.getNodeType( builder );
				const nodeData = builder.getDataFromNode( this );

				result = nodeData.snippet;

				if ( result === undefined ) {

					if ( nodeData.generated === undefined ) {

						nodeData.generated = true;

						result = this.generate( builder ) || '';

						nodeData.snippet = result;

					} else {

						console.warn( 'THREE.Node: Recursion detected.', this );

						result = '/* Recursion detected. */';

					}

				} else if ( nodeData.flowCodes !== undefined && builder.context.nodeBlock !== undefined ) {

					builder.addFlowCodeHierarchy( this, builder.context.nodeBlock );

				}

				result = builder.format( result, type, output );

			} else {

				result = this.generate( builder, output ) || '';

			}

			if ( result === '' && output !== null && output !== 'void' && output !== 'OutputType' ) {

				// if no snippet is generated, return a default value

				console.error( `THREE.TSL: Invalid generated code, expected a "${ output }".` );

				result = builder.generateConst( output );

			}

		}

		builder.removeChain( this );
		builder.addSequentialNode( this );

		return result;

	}
```
</details>

##### `getSerializeChildren(): any[]`

<details><summary>Code</summary>

```ts
getSerializeChildren() {

		return getNodeChildren( this );

	}
```
</details>

##### `serialize(json: any): void`

<details><summary>Code</summary>

```ts
serialize( json ) {

		const nodeChildren = this.getSerializeChildren();

		const inputNodes = {};

		for ( const { property, index, childNode } of nodeChildren ) {

			if ( index !== undefined ) {

				if ( inputNodes[ property ] === undefined ) {

					inputNodes[ property ] = Number.isInteger( index ) ? [] : {};

				}

				inputNodes[ property ][ index ] = childNode.toJSON( json.meta ).uuid;

			} else {

				inputNodes[ property ] = childNode.toJSON( json.meta ).uuid;

			}

		}

		if ( Object.keys( inputNodes ).length > 0 ) {

			json.inputNodes = inputNodes;

		}

	}
```
</details>

##### `deserialize(json: any): void`

<details><summary>Code</summary>

```ts
deserialize( json ) {

		if ( json.inputNodes !== undefined ) {

			const nodes = json.meta.nodes;

			for ( const property in json.inputNodes ) {

				if ( Array.isArray( json.inputNodes[ property ] ) ) {

					const inputArray = [];

					for ( const uuid of json.inputNodes[ property ] ) {

						inputArray.push( nodes[ uuid ] );

					}

					this[ property ] = inputArray;

				} else if ( typeof json.inputNodes[ property ] === 'object' ) {

					const inputObject = {};

					for ( const subProperty in json.inputNodes[ property ] ) {

						const uuid = json.inputNodes[ property ][ subProperty ];

						inputObject[ subProperty ] = nodes[ uuid ];

					}

					this[ property ] = inputObject;

				} else {

					const uuid = json.inputNodes[ property ];

					this[ property ] = nodes[ uuid ];

				}

			}

		}

	}
```
</details>

##### `toJSON(meta: any): any`

<details><summary>Code</summary>

```ts
toJSON( meta ) {

		const { uuid, type } = this;
		const isRoot = ( meta === undefined || typeof meta === 'string' );

		if ( isRoot ) {

			meta = {
				textures: {},
				images: {},
				nodes: {}
			};

		}

		// serialize

		let data = meta.nodes[ uuid ];

		if ( data === undefined ) {

			data = {
				uuid,
				type,
				meta,
				metadata: {
					version: 4.7,
					type: 'Node',
					generator: 'Node.toJSON'
				}
			};

			if ( isRoot !== true ) meta.nodes[ data.uuid ] = data;

			this.serialize( data );

			delete data.meta;

		}

		// TODO: Copied from Object3D.toJSON

		function extractFromCache( cache ) {

			const values = [];

			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}

		if ( isRoot ) {

			const textures = extractFromCache( meta.textures );
			const images = extractFromCache( meta.images );
			const nodes = extractFromCache( meta.nodes );

			if ( textures.length > 0 ) data.textures = textures;
			if ( images.length > 0 ) data.images = images;
			if ( nodes.length > 0 ) data.nodes = nodes;

		}

		return data;

	}
```
</details>


---