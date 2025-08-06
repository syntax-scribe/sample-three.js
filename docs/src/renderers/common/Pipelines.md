[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Pipelines.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Pipelines.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataMap` | `./DataMap.js` |
| `RenderPipeline` | `./RenderPipeline.js` |
| `ComputePipeline` | `./ComputePipeline.js` |
| `ProgrammableStage` | `./ProgrammableStage.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `previousPipeline` | `any` | let/var | `data.pipeline` | ✗ |
| `previousPipeline` | `any` | let/var | `data.pipeline` | ✗ |
| `name` | `any` | let/var | `renderObject.material ? renderObject.material.name : ''` | ✗ |
| `pipeline` | `any` | let/var | `this.get( object ).pipeline` | ✗ |
| `code` | `any` | let/var | `program.code` | ✗ |
| `stage` | `any` | let/var | `program.stage` | ✗ |


---

## Functions

### `Pipelines.getForCompute(computeNode: Node, bindings: BindGroup[]): ComputePipeline`

**JSDoc:**
```typescript
/**
	 * Returns a compute pipeline for the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @return {ComputePipeline} The compute pipeline.
	 */
```

**Parameters:**

- **`computeNode`** `Node`
- **`bindings`** `BindGroup[]`

**Returns:** `ComputePipeline`

**Calls:**

- `this.get`
- `this._needsComputeUpdate`
- `this.nodes.getForCompute`
- `this.programs.compute.get`
- `this._releaseProgram`
- `this.programs.compute.set`
- `backend.createProgram`
- `this._getComputeCacheKey`
- `this.caches.get`
- `this._releasePipeline`
- `this._getComputePipeline`

**Internal Comments:**
```
// get shader (x2)
// programmable stage (x2)
// determine compute pipeline (x2)
// keep track of all used times (x4)
// (x4)
```

<details><summary>Code</summary>

```typescript
getForCompute( computeNode, bindings ) {

		const { backend } = this;

		const data = this.get( computeNode );

		if ( this._needsComputeUpdate( computeNode ) ) {

			const previousPipeline = data.pipeline;

			if ( previousPipeline ) {

				previousPipeline.usedTimes --;
				previousPipeline.computeProgram.usedTimes --;

			}

			// get shader

			const nodeBuilderState = this.nodes.getForCompute( computeNode );

			// programmable stage

			let stageCompute = this.programs.compute.get( nodeBuilderState.computeShader );

			if ( stageCompute === undefined ) {

				if ( previousPipeline && previousPipeline.computeProgram.usedTimes === 0 ) this._releaseProgram( previousPipeline.computeProgram );

				stageCompute = new ProgrammableStage( nodeBuilderState.computeShader, 'compute', computeNode.name, nodeBuilderState.transforms, nodeBuilderState.nodeAttributes );
				this.programs.compute.set( nodeBuilderState.computeShader, stageCompute );

				backend.createProgram( stageCompute );

			}

			// determine compute pipeline

			const cacheKey = this._getComputeCacheKey( computeNode, stageCompute );

			let pipeline = this.caches.get( cacheKey );

			if ( pipeline === undefined ) {

				if ( previousPipeline && previousPipeline.usedTimes === 0 ) this._releasePipeline( previousPipeline );

				pipeline = this._getComputePipeline( computeNode, stageCompute, cacheKey, bindings );

			}

			// keep track of all used times

			pipeline.usedTimes ++;
			stageCompute.usedTimes ++;

			//

			data.version = computeNode.version;
			data.pipeline = pipeline;

		}

		return data.pipeline;

	}
```
</details>

### `Pipelines.getForRender(renderObject: RenderObject, promises: Promise<any>[]): RenderPipeline`

**JSDoc:**
```typescript
/**
	 * Returns a render pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @param {?Array<Promise>} [promises=null] - An array of compilation promises which is only relevant in context of `Renderer.compileAsync()`.
	 * @return {RenderPipeline} The render pipeline.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`
- **`promises`** `Promise<any>[]`

**Returns:** `RenderPipeline`

**Calls:**

- `this.get`
- `this._needsRenderUpdate`
- `renderObject.getNodeBuilderState`
- `this.programs.vertex.get`
- `this._releaseProgram`
- `this.programs.vertex.set`
- `backend.createProgram`
- `this.programs.fragment.get`
- `this.programs.fragment.set`
- `this._getRenderCacheKey`
- `this.caches.get`
- `this._releasePipeline`
- `this._getRenderPipeline`

**Internal Comments:**
```
// get shader (x2)
// programmable stages (x2)
// determine render pipeline (x2)
// keep track of all used times (x4)
// (x4)
```

<details><summary>Code</summary>

```typescript
getForRender( renderObject, promises = null ) {

		const { backend } = this;

		const data = this.get( renderObject );

		if ( this._needsRenderUpdate( renderObject ) ) {

			const previousPipeline = data.pipeline;

			if ( previousPipeline ) {

				previousPipeline.usedTimes --;
				previousPipeline.vertexProgram.usedTimes --;
				previousPipeline.fragmentProgram.usedTimes --;

			}

			// get shader

			const nodeBuilderState = renderObject.getNodeBuilderState();

			const name = renderObject.material ? renderObject.material.name : '';

			// programmable stages

			let stageVertex = this.programs.vertex.get( nodeBuilderState.vertexShader );

			if ( stageVertex === undefined ) {

				if ( previousPipeline && previousPipeline.vertexProgram.usedTimes === 0 ) this._releaseProgram( previousPipeline.vertexProgram );

				stageVertex = new ProgrammableStage( nodeBuilderState.vertexShader, 'vertex', name );
				this.programs.vertex.set( nodeBuilderState.vertexShader, stageVertex );

				backend.createProgram( stageVertex );

			}

			let stageFragment = this.programs.fragment.get( nodeBuilderState.fragmentShader );

			if ( stageFragment === undefined ) {

				if ( previousPipeline && previousPipeline.fragmentProgram.usedTimes === 0 ) this._releaseProgram( previousPipeline.fragmentProgram );

				stageFragment = new ProgrammableStage( nodeBuilderState.fragmentShader, 'fragment', name );
				this.programs.fragment.set( nodeBuilderState.fragmentShader, stageFragment );

				backend.createProgram( stageFragment );

			}

			// determine render pipeline

			const cacheKey = this._getRenderCacheKey( renderObject, stageVertex, stageFragment );

			let pipeline = this.caches.get( cacheKey );

			if ( pipeline === undefined ) {

				if ( previousPipeline && previousPipeline.usedTimes === 0 ) this._releasePipeline( previousPipeline );

				pipeline = this._getRenderPipeline( renderObject, stageVertex, stageFragment, cacheKey, promises );

			} else {

				renderObject.pipeline = pipeline;

			}

			// keep track of all used times

			pipeline.usedTimes ++;
			stageVertex.usedTimes ++;
			stageFragment.usedTimes ++;

			//

			data.pipeline = pipeline;

		}

		return data.pipeline;

	}
```
</details>

### `Pipelines.delete(object: RenderObject): any`

**JSDoc:**
```typescript
/**
	 * Deletes the pipeline for the given render object.
	 *
	 * @param {RenderObject} object - The render object.
	 * @return {?Object} The deleted dictionary.
	 */
```

**Parameters:**

- **`object`** `RenderObject`

**Returns:** `any`

**Calls:**

- `this.get`
- `this._releasePipeline`
- `this._releaseProgram`
- `super.delete`

**Internal Comments:**
```
// pipeline (x4)
// programs
```

<details><summary>Code</summary>

```typescript
delete( object ) {

		const pipeline = this.get( object ).pipeline;

		if ( pipeline ) {

			// pipeline

			pipeline.usedTimes --;

			if ( pipeline.usedTimes === 0 ) this._releasePipeline( pipeline );

			// programs

			if ( pipeline.isComputePipeline ) {

				pipeline.computeProgram.usedTimes --;

				if ( pipeline.computeProgram.usedTimes === 0 ) this._releaseProgram( pipeline.computeProgram );

			} else {

				pipeline.fragmentProgram.usedTimes --;
				pipeline.vertexProgram.usedTimes --;

				if ( pipeline.vertexProgram.usedTimes === 0 ) this._releaseProgram( pipeline.vertexProgram );
				if ( pipeline.fragmentProgram.usedTimes === 0 ) this._releaseProgram( pipeline.fragmentProgram );

			}

		}

		return super.delete( object );

	}
```
</details>

### `Pipelines.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources.
	 */
```

**Returns:** `void`

**Calls:**

- `super.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		super.dispose();

		this.caches = new Map();
		this.programs = {
			vertex: new Map(),
			fragment: new Map(),
			compute: new Map()
		};

	}
```
</details>

### `Pipelines.updateForRender(renderObject: RenderObject): void`

**JSDoc:**
```typescript
/**
	 * Updates the pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `void`

**Calls:**

- `this.getForRender`

<details><summary>Code</summary>

```typescript
updateForRender( renderObject ) {

		this.getForRender( renderObject );

	}
```
</details>

### `Pipelines._getComputePipeline(computeNode: Node, stageCompute: ProgrammableStage, cacheKey: string, bindings: BindGroup[]): ComputePipeline`

**JSDoc:**
```typescript
/**
	 * Returns a compute pipeline for the given parameters.
	 *
	 * @private
	 * @param {Node} computeNode - The compute node.
	 * @param {ProgrammableStage} stageCompute - The programmable stage representing the compute shader.
	 * @param {string} cacheKey - The cache key.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @return {ComputePipeline} The compute pipeline.
	 */
```

**Parameters:**

- **`computeNode`** `Node`
- **`stageCompute`** `ProgrammableStage`
- **`cacheKey`** `string`
- **`bindings`** `BindGroup[]`

**Returns:** `ComputePipeline`

**Calls:**

- `this._getComputeCacheKey`
- `this.caches.get`
- `this.caches.set`
- `this.backend.createComputePipeline`

**Internal Comments:**
```
// check for existing pipeline (x3)
```

<details><summary>Code</summary>

```typescript
_getComputePipeline( computeNode, stageCompute, cacheKey, bindings ) {

		// check for existing pipeline

		cacheKey = cacheKey || this._getComputeCacheKey( computeNode, stageCompute );

		let pipeline = this.caches.get( cacheKey );

		if ( pipeline === undefined ) {

			pipeline = new ComputePipeline( cacheKey, stageCompute );

			this.caches.set( cacheKey, pipeline );

			this.backend.createComputePipeline( pipeline, bindings );

		}

		return pipeline;

	}
```
</details>

### `Pipelines._getRenderPipeline(renderObject: RenderObject, stageVertex: ProgrammableStage, stageFragment: ProgrammableStage, cacheKey: string, promises: Promise<any>[]): ComputePipeline`

**JSDoc:**
```typescript
/**
	 * Returns a render pipeline for the given parameters.
	 *
	 * @private
	 * @param {RenderObject} renderObject - The render object.
	 * @param {ProgrammableStage} stageVertex - The programmable stage representing the vertex shader.
	 * @param {ProgrammableStage} stageFragment - The programmable stage representing the fragment shader.
	 * @param {string} cacheKey - The cache key.
	 * @param {?Array<Promise>} promises - An array of compilation promises which is only relevant in context of `Renderer.compileAsync()`.
	 * @return {ComputePipeline} The compute pipeline.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`
- **`stageVertex`** `ProgrammableStage`
- **`stageFragment`** `ProgrammableStage`
- **`cacheKey`** `string`
- **`promises`** `Promise<any>[]`

**Returns:** `ComputePipeline`

**Calls:**

- `this._getRenderCacheKey`
- `this.caches.get`
- `this.caches.set`
- `this.backend.createRenderPipeline`

**Internal Comments:**
```
// check for existing pipeline (x3)
// The `promises` array is `null` by default and only set to an empty array when (x5)
// `Renderer.compileAsync()` is used. The next call actually fills the array with (x5)
// pending promises that resolve when the render pipelines are ready for rendering. (x5)
```

<details><summary>Code</summary>

```typescript
_getRenderPipeline( renderObject, stageVertex, stageFragment, cacheKey, promises ) {

		// check for existing pipeline

		cacheKey = cacheKey || this._getRenderCacheKey( renderObject, stageVertex, stageFragment );

		let pipeline = this.caches.get( cacheKey );

		if ( pipeline === undefined ) {

			pipeline = new RenderPipeline( cacheKey, stageVertex, stageFragment );

			this.caches.set( cacheKey, pipeline );

			renderObject.pipeline = pipeline;

			// The `promises` array is `null` by default and only set to an empty array when
			// `Renderer.compileAsync()` is used. The next call actually fills the array with
			// pending promises that resolve when the render pipelines are ready for rendering.

			this.backend.createRenderPipeline( renderObject, promises );

		}

		return pipeline;

	}
```
</details>

### `Pipelines._getComputeCacheKey(computeNode: Node, stageCompute: ProgrammableStage): string`

**JSDoc:**
```typescript
/**
	 * Computes a cache key representing a compute pipeline.
	 *
	 * @private
	 * @param {Node} computeNode - The compute node.
	 * @param {ProgrammableStage} stageCompute - The programmable stage representing the compute shader.
	 * @return {string} The cache key.
	 */
```

**Parameters:**

- **`computeNode`** `Node`
- **`stageCompute`** `ProgrammableStage`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
_getComputeCacheKey( computeNode, stageCompute ) {

		return computeNode.id + ',' + stageCompute.id;

	}
```
</details>

### `Pipelines._getRenderCacheKey(renderObject: RenderObject, stageVertex: ProgrammableStage, stageFragment: ProgrammableStage): string`

**JSDoc:**
```typescript
/**
	 * Computes a cache key representing a render pipeline.
	 *
	 * @private
	 * @param {RenderObject} renderObject - The render object.
	 * @param {ProgrammableStage} stageVertex - The programmable stage representing the vertex shader.
	 * @param {ProgrammableStage} stageFragment - The programmable stage representing the fragment shader.
	 * @return {string} The cache key.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`
- **`stageVertex`** `ProgrammableStage`
- **`stageFragment`** `ProgrammableStage`

**Returns:** `string`

**Calls:**

- `this.backend.getRenderCacheKey`

<details><summary>Code</summary>

```typescript
_getRenderCacheKey( renderObject, stageVertex, stageFragment ) {

		return stageVertex.id + ',' + stageFragment.id + ',' + this.backend.getRenderCacheKey( renderObject );

	}
```
</details>

### `Pipelines._releasePipeline(pipeline: Pipeline): void`

**JSDoc:**
```typescript
/**
	 * Releases the given pipeline.
	 *
	 * @private
	 * @param {Pipeline} pipeline - The pipeline to release.
	 */
```

**Parameters:**

- **`pipeline`** `Pipeline`

**Returns:** `void`

**Calls:**

- `this.caches.delete`

<details><summary>Code</summary>

```typescript
_releasePipeline( pipeline ) {

		this.caches.delete( pipeline.cacheKey );

	}
```
</details>

### `Pipelines._releaseProgram(program: any): void`

**JSDoc:**
```typescript
/**
	 * Releases the shader program.
	 *
	 * @private
	 * @param {Object} program - The shader program to release.
	 */
```

**Parameters:**

- **`program`** `any`

**Returns:** `void`

**Calls:**

- `this.programs[ stage ].delete`

<details><summary>Code</summary>

```typescript
_releaseProgram( program ) {

		const code = program.code;
		const stage = program.stage;

		this.programs[ stage ].delete( code );

	}
```
</details>

### `Pipelines._needsComputeUpdate(computeNode: Node): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the compute pipeline for the given compute node requires an update.
	 *
	 * @private
	 * @param {Node} computeNode - The compute node.
	 * @return {boolean} Whether the compute pipeline for the given compute node requires an update or not.
	 */
```

**Parameters:**

- **`computeNode`** `Node`

**Returns:** `boolean`

**Calls:**

- `this.get`

<details><summary>Code</summary>

```typescript
_needsComputeUpdate( computeNode ) {

		const data = this.get( computeNode );

		return data.pipeline === undefined || data.version !== computeNode.version;

	}
```
</details>

### `Pipelines._needsRenderUpdate(renderObject: RenderObject): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the render pipeline for the given render object requires an update.
	 *
	 * @private
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the render object for the given render object requires an update or not.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `boolean`

**Calls:**

- `this.get`
- `this.backend.needsRenderUpdate`

<details><summary>Code</summary>

```typescript
_needsRenderUpdate( renderObject ) {

		const data = this.get( renderObject );

		return data.pipeline === undefined || this.backend.needsRenderUpdate( renderObject );

	}
```
</details>


---

## Classes

### `Pipelines`

<details><summary>Class Code</summary>

```ts
class Pipelines extends DataMap {

	/**
	 * Constructs a new pipeline management component.
	 *
	 * @param {Backend} backend - The renderer's backend.
	 * @param {Nodes} nodes - Renderer component for managing nodes related logic.
	 */
	constructor( backend, nodes ) {

		super();

		/**
		 * The renderer's backend.
		 *
		 * @type {Backend}
		 */
		this.backend = backend;

		/**
		 * Renderer component for managing nodes related logic.
		 *
		 * @type {Nodes}
		 */
		this.nodes = nodes;

		/**
		 * A references to the bindings management component.
		 * This reference will be set inside the `Bindings`
		 * constructor.
		 *
		 * @type {?Bindings}
		 * @default null
		 */
		this.bindings = null;

		/**
		 * Internal cache for maintaining pipelines.
		 * The key of the map is a cache key, the value the pipeline.
		 *
		 * @type {Map<string,Pipeline>}
		 */
		this.caches = new Map();

		/**
		 * This dictionary maintains for each shader stage type (vertex,
		 * fragment and compute) the programmable stage objects which
		 * represent the actual shader code.
		 *
		 * @type {Object<string,Map>}
		 */
		this.programs = {
			vertex: new Map(),
			fragment: new Map(),
			compute: new Map()
		};

	}

	/**
	 * Returns a compute pipeline for the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @return {ComputePipeline} The compute pipeline.
	 */
	getForCompute( computeNode, bindings ) {

		const { backend } = this;

		const data = this.get( computeNode );

		if ( this._needsComputeUpdate( computeNode ) ) {

			const previousPipeline = data.pipeline;

			if ( previousPipeline ) {

				previousPipeline.usedTimes --;
				previousPipeline.computeProgram.usedTimes --;

			}

			// get shader

			const nodeBuilderState = this.nodes.getForCompute( computeNode );

			// programmable stage

			let stageCompute = this.programs.compute.get( nodeBuilderState.computeShader );

			if ( stageCompute === undefined ) {

				if ( previousPipeline && previousPipeline.computeProgram.usedTimes === 0 ) this._releaseProgram( previousPipeline.computeProgram );

				stageCompute = new ProgrammableStage( nodeBuilderState.computeShader, 'compute', computeNode.name, nodeBuilderState.transforms, nodeBuilderState.nodeAttributes );
				this.programs.compute.set( nodeBuilderState.computeShader, stageCompute );

				backend.createProgram( stageCompute );

			}

			// determine compute pipeline

			const cacheKey = this._getComputeCacheKey( computeNode, stageCompute );

			let pipeline = this.caches.get( cacheKey );

			if ( pipeline === undefined ) {

				if ( previousPipeline && previousPipeline.usedTimes === 0 ) this._releasePipeline( previousPipeline );

				pipeline = this._getComputePipeline( computeNode, stageCompute, cacheKey, bindings );

			}

			// keep track of all used times

			pipeline.usedTimes ++;
			stageCompute.usedTimes ++;

			//

			data.version = computeNode.version;
			data.pipeline = pipeline;

		}

		return data.pipeline;

	}

	/**
	 * Returns a render pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @param {?Array<Promise>} [promises=null] - An array of compilation promises which is only relevant in context of `Renderer.compileAsync()`.
	 * @return {RenderPipeline} The render pipeline.
	 */
	getForRender( renderObject, promises = null ) {

		const { backend } = this;

		const data = this.get( renderObject );

		if ( this._needsRenderUpdate( renderObject ) ) {

			const previousPipeline = data.pipeline;

			if ( previousPipeline ) {

				previousPipeline.usedTimes --;
				previousPipeline.vertexProgram.usedTimes --;
				previousPipeline.fragmentProgram.usedTimes --;

			}

			// get shader

			const nodeBuilderState = renderObject.getNodeBuilderState();

			const name = renderObject.material ? renderObject.material.name : '';

			// programmable stages

			let stageVertex = this.programs.vertex.get( nodeBuilderState.vertexShader );

			if ( stageVertex === undefined ) {

				if ( previousPipeline && previousPipeline.vertexProgram.usedTimes === 0 ) this._releaseProgram( previousPipeline.vertexProgram );

				stageVertex = new ProgrammableStage( nodeBuilderState.vertexShader, 'vertex', name );
				this.programs.vertex.set( nodeBuilderState.vertexShader, stageVertex );

				backend.createProgram( stageVertex );

			}

			let stageFragment = this.programs.fragment.get( nodeBuilderState.fragmentShader );

			if ( stageFragment === undefined ) {

				if ( previousPipeline && previousPipeline.fragmentProgram.usedTimes === 0 ) this._releaseProgram( previousPipeline.fragmentProgram );

				stageFragment = new ProgrammableStage( nodeBuilderState.fragmentShader, 'fragment', name );
				this.programs.fragment.set( nodeBuilderState.fragmentShader, stageFragment );

				backend.createProgram( stageFragment );

			}

			// determine render pipeline

			const cacheKey = this._getRenderCacheKey( renderObject, stageVertex, stageFragment );

			let pipeline = this.caches.get( cacheKey );

			if ( pipeline === undefined ) {

				if ( previousPipeline && previousPipeline.usedTimes === 0 ) this._releasePipeline( previousPipeline );

				pipeline = this._getRenderPipeline( renderObject, stageVertex, stageFragment, cacheKey, promises );

			} else {

				renderObject.pipeline = pipeline;

			}

			// keep track of all used times

			pipeline.usedTimes ++;
			stageVertex.usedTimes ++;
			stageFragment.usedTimes ++;

			//

			data.pipeline = pipeline;

		}

		return data.pipeline;

	}

	/**
	 * Deletes the pipeline for the given render object.
	 *
	 * @param {RenderObject} object - The render object.
	 * @return {?Object} The deleted dictionary.
	 */
	delete( object ) {

		const pipeline = this.get( object ).pipeline;

		if ( pipeline ) {

			// pipeline

			pipeline.usedTimes --;

			if ( pipeline.usedTimes === 0 ) this._releasePipeline( pipeline );

			// programs

			if ( pipeline.isComputePipeline ) {

				pipeline.computeProgram.usedTimes --;

				if ( pipeline.computeProgram.usedTimes === 0 ) this._releaseProgram( pipeline.computeProgram );

			} else {

				pipeline.fragmentProgram.usedTimes --;
				pipeline.vertexProgram.usedTimes --;

				if ( pipeline.vertexProgram.usedTimes === 0 ) this._releaseProgram( pipeline.vertexProgram );
				if ( pipeline.fragmentProgram.usedTimes === 0 ) this._releaseProgram( pipeline.fragmentProgram );

			}

		}

		return super.delete( object );

	}

	/**
	 * Frees internal resources.
	 */
	dispose() {

		super.dispose();

		this.caches = new Map();
		this.programs = {
			vertex: new Map(),
			fragment: new Map(),
			compute: new Map()
		};

	}

	/**
	 * Updates the pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
	updateForRender( renderObject ) {

		this.getForRender( renderObject );

	}

	/**
	 * Returns a compute pipeline for the given parameters.
	 *
	 * @private
	 * @param {Node} computeNode - The compute node.
	 * @param {ProgrammableStage} stageCompute - The programmable stage representing the compute shader.
	 * @param {string} cacheKey - The cache key.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @return {ComputePipeline} The compute pipeline.
	 */
	_getComputePipeline( computeNode, stageCompute, cacheKey, bindings ) {

		// check for existing pipeline

		cacheKey = cacheKey || this._getComputeCacheKey( computeNode, stageCompute );

		let pipeline = this.caches.get( cacheKey );

		if ( pipeline === undefined ) {

			pipeline = new ComputePipeline( cacheKey, stageCompute );

			this.caches.set( cacheKey, pipeline );

			this.backend.createComputePipeline( pipeline, bindings );

		}

		return pipeline;

	}

	/**
	 * Returns a render pipeline for the given parameters.
	 *
	 * @private
	 * @param {RenderObject} renderObject - The render object.
	 * @param {ProgrammableStage} stageVertex - The programmable stage representing the vertex shader.
	 * @param {ProgrammableStage} stageFragment - The programmable stage representing the fragment shader.
	 * @param {string} cacheKey - The cache key.
	 * @param {?Array<Promise>} promises - An array of compilation promises which is only relevant in context of `Renderer.compileAsync()`.
	 * @return {ComputePipeline} The compute pipeline.
	 */
	_getRenderPipeline( renderObject, stageVertex, stageFragment, cacheKey, promises ) {

		// check for existing pipeline

		cacheKey = cacheKey || this._getRenderCacheKey( renderObject, stageVertex, stageFragment );

		let pipeline = this.caches.get( cacheKey );

		if ( pipeline === undefined ) {

			pipeline = new RenderPipeline( cacheKey, stageVertex, stageFragment );

			this.caches.set( cacheKey, pipeline );

			renderObject.pipeline = pipeline;

			// The `promises` array is `null` by default and only set to an empty array when
			// `Renderer.compileAsync()` is used. The next call actually fills the array with
			// pending promises that resolve when the render pipelines are ready for rendering.

			this.backend.createRenderPipeline( renderObject, promises );

		}

		return pipeline;

	}

	/**
	 * Computes a cache key representing a compute pipeline.
	 *
	 * @private
	 * @param {Node} computeNode - The compute node.
	 * @param {ProgrammableStage} stageCompute - The programmable stage representing the compute shader.
	 * @return {string} The cache key.
	 */
	_getComputeCacheKey( computeNode, stageCompute ) {

		return computeNode.id + ',' + stageCompute.id;

	}

	/**
	 * Computes a cache key representing a render pipeline.
	 *
	 * @private
	 * @param {RenderObject} renderObject - The render object.
	 * @param {ProgrammableStage} stageVertex - The programmable stage representing the vertex shader.
	 * @param {ProgrammableStage} stageFragment - The programmable stage representing the fragment shader.
	 * @return {string} The cache key.
	 */
	_getRenderCacheKey( renderObject, stageVertex, stageFragment ) {

		return stageVertex.id + ',' + stageFragment.id + ',' + this.backend.getRenderCacheKey( renderObject );

	}

	/**
	 * Releases the given pipeline.
	 *
	 * @private
	 * @param {Pipeline} pipeline - The pipeline to release.
	 */
	_releasePipeline( pipeline ) {

		this.caches.delete( pipeline.cacheKey );

	}

	/**
	 * Releases the shader program.
	 *
	 * @private
	 * @param {Object} program - The shader program to release.
	 */
	_releaseProgram( program ) {

		const code = program.code;
		const stage = program.stage;

		this.programs[ stage ].delete( code );

	}

	/**
	 * Returns `true` if the compute pipeline for the given compute node requires an update.
	 *
	 * @private
	 * @param {Node} computeNode - The compute node.
	 * @return {boolean} Whether the compute pipeline for the given compute node requires an update or not.
	 */
	_needsComputeUpdate( computeNode ) {

		const data = this.get( computeNode );

		return data.pipeline === undefined || data.version !== computeNode.version;

	}

	/**
	 * Returns `true` if the render pipeline for the given render object requires an update.
	 *
	 * @private
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the render object for the given render object requires an update or not.
	 */
	_needsRenderUpdate( renderObject ) {

		const data = this.get( renderObject );

		return data.pipeline === undefined || this.backend.needsRenderUpdate( renderObject );

	}

}
```
</details>

#### Methods

##### `getForCompute(computeNode: Node, bindings: BindGroup[]): ComputePipeline`

<details><summary>Code</summary>

```ts
getForCompute( computeNode, bindings ) {

		const { backend } = this;

		const data = this.get( computeNode );

		if ( this._needsComputeUpdate( computeNode ) ) {

			const previousPipeline = data.pipeline;

			if ( previousPipeline ) {

				previousPipeline.usedTimes --;
				previousPipeline.computeProgram.usedTimes --;

			}

			// get shader

			const nodeBuilderState = this.nodes.getForCompute( computeNode );

			// programmable stage

			let stageCompute = this.programs.compute.get( nodeBuilderState.computeShader );

			if ( stageCompute === undefined ) {

				if ( previousPipeline && previousPipeline.computeProgram.usedTimes === 0 ) this._releaseProgram( previousPipeline.computeProgram );

				stageCompute = new ProgrammableStage( nodeBuilderState.computeShader, 'compute', computeNode.name, nodeBuilderState.transforms, nodeBuilderState.nodeAttributes );
				this.programs.compute.set( nodeBuilderState.computeShader, stageCompute );

				backend.createProgram( stageCompute );

			}

			// determine compute pipeline

			const cacheKey = this._getComputeCacheKey( computeNode, stageCompute );

			let pipeline = this.caches.get( cacheKey );

			if ( pipeline === undefined ) {

				if ( previousPipeline && previousPipeline.usedTimes === 0 ) this._releasePipeline( previousPipeline );

				pipeline = this._getComputePipeline( computeNode, stageCompute, cacheKey, bindings );

			}

			// keep track of all used times

			pipeline.usedTimes ++;
			stageCompute.usedTimes ++;

			//

			data.version = computeNode.version;
			data.pipeline = pipeline;

		}

		return data.pipeline;

	}
```
</details>

##### `getForRender(renderObject: RenderObject, promises: Promise<any>[]): RenderPipeline`

<details><summary>Code</summary>

```ts
getForRender( renderObject, promises = null ) {

		const { backend } = this;

		const data = this.get( renderObject );

		if ( this._needsRenderUpdate( renderObject ) ) {

			const previousPipeline = data.pipeline;

			if ( previousPipeline ) {

				previousPipeline.usedTimes --;
				previousPipeline.vertexProgram.usedTimes --;
				previousPipeline.fragmentProgram.usedTimes --;

			}

			// get shader

			const nodeBuilderState = renderObject.getNodeBuilderState();

			const name = renderObject.material ? renderObject.material.name : '';

			// programmable stages

			let stageVertex = this.programs.vertex.get( nodeBuilderState.vertexShader );

			if ( stageVertex === undefined ) {

				if ( previousPipeline && previousPipeline.vertexProgram.usedTimes === 0 ) this._releaseProgram( previousPipeline.vertexProgram );

				stageVertex = new ProgrammableStage( nodeBuilderState.vertexShader, 'vertex', name );
				this.programs.vertex.set( nodeBuilderState.vertexShader, stageVertex );

				backend.createProgram( stageVertex );

			}

			let stageFragment = this.programs.fragment.get( nodeBuilderState.fragmentShader );

			if ( stageFragment === undefined ) {

				if ( previousPipeline && previousPipeline.fragmentProgram.usedTimes === 0 ) this._releaseProgram( previousPipeline.fragmentProgram );

				stageFragment = new ProgrammableStage( nodeBuilderState.fragmentShader, 'fragment', name );
				this.programs.fragment.set( nodeBuilderState.fragmentShader, stageFragment );

				backend.createProgram( stageFragment );

			}

			// determine render pipeline

			const cacheKey = this._getRenderCacheKey( renderObject, stageVertex, stageFragment );

			let pipeline = this.caches.get( cacheKey );

			if ( pipeline === undefined ) {

				if ( previousPipeline && previousPipeline.usedTimes === 0 ) this._releasePipeline( previousPipeline );

				pipeline = this._getRenderPipeline( renderObject, stageVertex, stageFragment, cacheKey, promises );

			} else {

				renderObject.pipeline = pipeline;

			}

			// keep track of all used times

			pipeline.usedTimes ++;
			stageVertex.usedTimes ++;
			stageFragment.usedTimes ++;

			//

			data.pipeline = pipeline;

		}

		return data.pipeline;

	}
```
</details>

##### `delete(object: RenderObject): any`

<details><summary>Code</summary>

```ts
delete( object ) {

		const pipeline = this.get( object ).pipeline;

		if ( pipeline ) {

			// pipeline

			pipeline.usedTimes --;

			if ( pipeline.usedTimes === 0 ) this._releasePipeline( pipeline );

			// programs

			if ( pipeline.isComputePipeline ) {

				pipeline.computeProgram.usedTimes --;

				if ( pipeline.computeProgram.usedTimes === 0 ) this._releaseProgram( pipeline.computeProgram );

			} else {

				pipeline.fragmentProgram.usedTimes --;
				pipeline.vertexProgram.usedTimes --;

				if ( pipeline.vertexProgram.usedTimes === 0 ) this._releaseProgram( pipeline.vertexProgram );
				if ( pipeline.fragmentProgram.usedTimes === 0 ) this._releaseProgram( pipeline.fragmentProgram );

			}

		}

		return super.delete( object );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		super.dispose();

		this.caches = new Map();
		this.programs = {
			vertex: new Map(),
			fragment: new Map(),
			compute: new Map()
		};

	}
```
</details>

##### `updateForRender(renderObject: RenderObject): void`

<details><summary>Code</summary>

```ts
updateForRender( renderObject ) {

		this.getForRender( renderObject );

	}
```
</details>

##### `_getComputePipeline(computeNode: Node, stageCompute: ProgrammableStage, cacheKey: string, bindings: BindGroup[]): ComputePipeline`

<details><summary>Code</summary>

```ts
_getComputePipeline( computeNode, stageCompute, cacheKey, bindings ) {

		// check for existing pipeline

		cacheKey = cacheKey || this._getComputeCacheKey( computeNode, stageCompute );

		let pipeline = this.caches.get( cacheKey );

		if ( pipeline === undefined ) {

			pipeline = new ComputePipeline( cacheKey, stageCompute );

			this.caches.set( cacheKey, pipeline );

			this.backend.createComputePipeline( pipeline, bindings );

		}

		return pipeline;

	}
```
</details>

##### `_getRenderPipeline(renderObject: RenderObject, stageVertex: ProgrammableStage, stageFragment: ProgrammableStage, cacheKey: string, promises: Promise<any>[]): ComputePipeline`

<details><summary>Code</summary>

```ts
_getRenderPipeline( renderObject, stageVertex, stageFragment, cacheKey, promises ) {

		// check for existing pipeline

		cacheKey = cacheKey || this._getRenderCacheKey( renderObject, stageVertex, stageFragment );

		let pipeline = this.caches.get( cacheKey );

		if ( pipeline === undefined ) {

			pipeline = new RenderPipeline( cacheKey, stageVertex, stageFragment );

			this.caches.set( cacheKey, pipeline );

			renderObject.pipeline = pipeline;

			// The `promises` array is `null` by default and only set to an empty array when
			// `Renderer.compileAsync()` is used. The next call actually fills the array with
			// pending promises that resolve when the render pipelines are ready for rendering.

			this.backend.createRenderPipeline( renderObject, promises );

		}

		return pipeline;

	}
```
</details>

##### `_getComputeCacheKey(computeNode: Node, stageCompute: ProgrammableStage): string`

<details><summary>Code</summary>

```ts
_getComputeCacheKey( computeNode, stageCompute ) {

		return computeNode.id + ',' + stageCompute.id;

	}
```
</details>

##### `_getRenderCacheKey(renderObject: RenderObject, stageVertex: ProgrammableStage, stageFragment: ProgrammableStage): string`

<details><summary>Code</summary>

```ts
_getRenderCacheKey( renderObject, stageVertex, stageFragment ) {

		return stageVertex.id + ',' + stageFragment.id + ',' + this.backend.getRenderCacheKey( renderObject );

	}
```
</details>

##### `_releasePipeline(pipeline: Pipeline): void`

<details><summary>Code</summary>

```ts
_releasePipeline( pipeline ) {

		this.caches.delete( pipeline.cacheKey );

	}
```
</details>

##### `_releaseProgram(program: any): void`

<details><summary>Code</summary>

```ts
_releaseProgram( program ) {

		const code = program.code;
		const stage = program.stage;

		this.programs[ stage ].delete( code );

	}
```
</details>

##### `_needsComputeUpdate(computeNode: Node): boolean`

<details><summary>Code</summary>

```ts
_needsComputeUpdate( computeNode ) {

		const data = this.get( computeNode );

		return data.pipeline === undefined || data.version !== computeNode.version;

	}
```
</details>

##### `_needsRenderUpdate(renderObject: RenderObject): boolean`

<details><summary>Code</summary>

```ts
_needsRenderUpdate( renderObject ) {

		const data = this.get( renderObject );

		return data.pipeline === undefined || this.backend.needsRenderUpdate( renderObject );

	}
```
</details>


---