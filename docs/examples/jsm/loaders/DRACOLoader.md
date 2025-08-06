[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DRACOLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 21 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 39 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/DRACOLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `ColorManagement` | `three` |
| `FileLoader` | `three` |
| `Loader` | `three` |
| `LinearSRGBColorSpace` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_taskCache` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `taskConfig` | `{ attributeIDs: any; attributeTypes: ...` | let/var | `{ attributeIDs: attributeIDs \|\| this.defaultAttributeIDs, attributeTypes: a...` | ✗ |
| `worker` | `any` | let/var | `*not shown*` | ✗ |
| `taskID` | `number` | let/var | `this.workerNextTaskID ++` | ✗ |
| `taskCost` | `any` | let/var | `buffer.byteLength` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `result` | `any` | let/var | `geometryData.attributes[ i ]` | ✗ |
| `name` | `any` | let/var | `result.name` | ✗ |
| `array` | `any` | let/var | `result.array` | ✗ |
| `itemSize` | `any` | let/var | `result.itemSize` | ✗ |
| `attribute` | `any` | let/var | `new BufferAttribute( array, itemSize )` | ✗ |
| `_color` | `any` | let/var | `new Color()` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `useJS` | `boolean` | let/var | `typeof WebAssembly !== 'object' \|\| this.decoderConfig.type === 'js'` | ✗ |
| `librariesPending` | `any[]` | let/var | `[]` | ✗ |
| `jsContent` | `any` | let/var | `libraries[ 0 ]` | ✗ |
| `worker` | `Worker` | let/var | `new Worker( this.workerSourceURL )` | ✗ |
| `message` | `any` | let/var | `e.data` | ✗ |
| `worker` | `any` | let/var | `this.workerPool[ this.workerPool.length - 1 ]` | ✗ |
| `decoderConfig` | `any` | let/var | `*not shown*` | ✗ |
| `decoderPending` | `any` | let/var | `*not shown*` | ✗ |
| `message` | `any` | let/var | `e.data` | ✗ |
| `buffer` | `any` | let/var | `message.buffer` | ✗ |
| `taskConfig` | `any` | let/var | `message.taskConfig` | ✗ |
| `draco` | `any` | let/var | `module.draco` | ✗ |
| `decoder` | `any` | let/var | `new draco.Decoder()` | ✗ |
| `attributeIDs` | `any` | let/var | `taskConfig.attributeIDs` | ✗ |
| `attributeTypes` | `any` | let/var | `taskConfig.attributeTypes` | ✗ |
| `dracoGeometry` | `any` | let/var | `*not shown*` | ✗ |
| `decodingStatus` | `any` | let/var | `*not shown*` | ✗ |
| `geometry` | `{ index: any; attributes: any[]; }` | let/var | `{ index: null, attributes: [] }` | ✗ |
| `attributeType` | `Window` | let/var | `self[ attributeTypes[ attributeName ] ]` | ✗ |
| `attribute` | `any` | let/var | `*not shown*` | ✗ |
| `attributeID` | `any` | let/var | `*not shown*` | ✗ |
| `numIndices` | `number` | let/var | `numFaces * 3` | ✗ |
| `byteLength` | `number` | let/var | `numIndices * 4` | ✗ |
| `numValues` | `number` | let/var | `numPoints * numComponents` | ✗ |
| `byteLength` | `number` | let/var | `numValues * attributeType.BYTES_PER_ELEMENT` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `DRACOWorker` | *none* | new Promise(...), decoderPending.then |


---

## Functions

### `DRACOLoader.setDecoderPath(path: string): DRACOLoader`

**JSDoc:**
```typescript
/**
	 * Provides configuration for the decoder libraries. Configuration cannot be changed after decoding begins.
	 *
	 * @param {string} path - The decoder path.
	 * @return {DRACOLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`path`** `string`

**Returns:** `DRACOLoader`

<details><summary>Code</summary>

```typescript
setDecoderPath( path ) {

		this.decoderPath = path;

		return this;

	}
```
</details>

### `DRACOLoader.setDecoderConfig(config: { type: "js" | "wasm"; }): DRACOLoader`

**JSDoc:**
```typescript
/**
	 * Provides configuration for the decoder libraries. Configuration cannot be changed after decoding begins.
	 *
	 * @param {{type:('js'|'wasm')}} config - The decoder config.
	 * @return {DRACOLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`config`** `{ type: "js" | "wasm"; }`

**Returns:** `DRACOLoader`

<details><summary>Code</summary>

```typescript
setDecoderConfig( config ) {

		this.decoderConfig = config;

		return this;

	}
```
</details>

### `DRACOLoader.setWorkerLimit(workerLimit: number): DRACOLoader`

**JSDoc:**
```typescript
/**
	 * Sets the maximum number of Web Workers to be used during decoding.
	 * A lower limit may be preferable if workers are also for other tasks in the application.
	 *
	 * @param {number} workerLimit - The worker limit.
	 * @return {DRACOLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`workerLimit`** `number`

**Returns:** `DRACOLoader`

<details><summary>Code</summary>

```typescript
setWorkerLimit( workerLimit ) {

		this.workerLimit = workerLimit;

		return this;

	}
```
</details>

### `DRACOLoader.load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded Draco asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: BufferGeometry) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setResponseType`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `this.parse`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );

		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );

		loader.load( url, ( buffer ) => {

			this.parse( buffer, onLoad, onError );

		}, onProgress, onError );

	}
```
</details>

### `DRACOLoader.parse(buffer: ArrayBuffer, onLoad: (arg0: BufferGeometry) => any, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Parses the given Draco data.
	 *
	 * @param {ArrayBuffer} buffer - The raw Draco data as an array buffer.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading/parsing process has been finished.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`
- **`onLoad`** `(arg0: BufferGeometry) => any`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `this.decodeDracoFile( buffer, onLoad, null, null, SRGBColorSpace, onError ).catch`

<details><summary>Code</summary>

```typescript
parse( buffer, onLoad, onError = ()=>{} ) {

		this.decodeDracoFile( buffer, onLoad, null, null, SRGBColorSpace, onError ).catch( onError );

	}
```
</details>

### `DRACOLoader.decodeDracoFile(buffer: any, callback: any, attributeIDs: any, attributeTypes: any, vertexColorSpace: any, onError: () => void): any`

**Parameters:**

- **`buffer`** `any`
- **`callback`** `any`
- **`attributeIDs`** `any`
- **`attributeTypes`** `any`
- **`vertexColorSpace`** `any`
- **`onError`** `() => void`

**Returns:** `any`

**Calls:**

- `this.decodeGeometry( buffer, taskConfig ).then( callback ).catch`

<details><summary>Code</summary>

```typescript
decodeDracoFile( buffer, callback, attributeIDs, attributeTypes, vertexColorSpace = LinearSRGBColorSpace, onError = () => {} ) {

		const taskConfig = {
			attributeIDs: attributeIDs || this.defaultAttributeIDs,
			attributeTypes: attributeTypes || this.defaultAttributeTypes,
			useUniqueIDs: !! attributeIDs,
			vertexColorSpace: vertexColorSpace,
		};

		return this.decodeGeometry( buffer, taskConfig ).then( callback ).catch( onError );

	}
```
</details>

### `DRACOLoader.decodeGeometry(buffer: any, taskConfig: any): any`

**Parameters:**

- **`buffer`** `any`
- **`taskConfig`** `any`

**Returns:** `any`

**Calls:**

- `JSON.stringify`
- `_taskCache.has`
- `_taskCache.get`
- `this._getWorker( taskID, taskCost )
			.then( ( _worker ) => {

				worker = _worker;

				return new Promise( ( resolve, reject ) => {

					worker._callbacks[ taskID ] = { resolve, reject };

					worker.postMessage( { type: 'decode', id: taskID, taskConfig, buffer }, [ buffer ] );

					// this.debug();

				} );

			} )
			.then`
- `this._createGeometry`
- `geometryPending
			.catch( () => true )
			.then`
- `this._releaseTask`
- `_taskCache.set`

**Internal Comments:**
```
// Check for an existing task using this buffer. A transferred buffer cannot be transferred
// again from this thread.
// Technically, it would be possible to wait for the previous task to complete,
// transfer the buffer back, and decode again with the second configuration. That
// is complex, and I don't know of any reason to decode a Draco buffer twice in
// different ways, so this is left unimplemented.
// (x2)
// Obtain a worker and assign a task, and construct a geometry instance (x2)
// when the task completes. (x2)
// Remove task from the task list. (x6)
// Note: replaced '.finally()' with '.catch().then()' block - iOS 11 support (#19416) (x6)
// Cache the task result. (x4)
```

<details><summary>Code</summary>

```typescript
decodeGeometry( buffer, taskConfig ) {

		const taskKey = JSON.stringify( taskConfig );

		// Check for an existing task using this buffer. A transferred buffer cannot be transferred
		// again from this thread.
		if ( _taskCache.has( buffer ) ) {

			const cachedTask = _taskCache.get( buffer );

			if ( cachedTask.key === taskKey ) {

				return cachedTask.promise;

			} else if ( buffer.byteLength === 0 ) {

				// Technically, it would be possible to wait for the previous task to complete,
				// transfer the buffer back, and decode again with the second configuration. That
				// is complex, and I don't know of any reason to decode a Draco buffer twice in
				// different ways, so this is left unimplemented.
				throw new Error(

					'THREE.DRACOLoader: Unable to re-decode a buffer with different ' +
					'settings. Buffer has already been transferred.'

				);

			}

		}

		//

		let worker;
		const taskID = this.workerNextTaskID ++;
		const taskCost = buffer.byteLength;

		// Obtain a worker and assign a task, and construct a geometry instance
		// when the task completes.
		const geometryPending = this._getWorker( taskID, taskCost )
			.then( ( _worker ) => {

				worker = _worker;

				return new Promise( ( resolve, reject ) => {

					worker._callbacks[ taskID ] = { resolve, reject };

					worker.postMessage( { type: 'decode', id: taskID, taskConfig, buffer }, [ buffer ] );

					// this.debug();

				} );

			} )
			.then( ( message ) => this._createGeometry( message.geometry ) );

		// Remove task from the task list.
		// Note: replaced '.finally()' with '.catch().then()' block - iOS 11 support (#19416)
		geometryPending
			.catch( () => true )
			.then( () => {

				if ( worker && taskID ) {

					this._releaseTask( worker, taskID );

					// this.debug();

				}

			} );

		// Cache the task result.
		_taskCache.set( buffer, {

			key: taskKey,
			promise: geometryPending

		} );

		return geometryPending;

	}
```
</details>

### `DRACOLoader._createGeometry(geometryData: any): any`

**Parameters:**

- **`geometryData`** `any`

**Returns:** `any`

**Calls:**

- `geometry.setIndex`
- `this._assignVertexColorSpace`
- `geometry.setAttribute`

<details><summary>Code</summary>

```typescript
_createGeometry( geometryData ) {

		const geometry = new BufferGeometry();

		if ( geometryData.index ) {

			geometry.setIndex( new BufferAttribute( geometryData.index.array, 1 ) );

		}

		for ( let i = 0; i < geometryData.attributes.length; i ++ ) {

			const result = geometryData.attributes[ i ];
			const name = result.name;
			const array = result.array;
			const itemSize = result.itemSize;

			const attribute = new BufferAttribute( array, itemSize );

			if ( name === 'color' ) {

				this._assignVertexColorSpace( attribute, result.vertexColorSpace );

				attribute.normalized = ( array instanceof Float32Array ) === false;

			}

			geometry.setAttribute( name, attribute );

		}

		return geometry;

	}
```
</details>

### `DRACOLoader._assignVertexColorSpace(attribute: any, inputColorSpace: any): void`

**Parameters:**

- **`attribute`** `any`
- **`inputColorSpace`** `any`

**Returns:** `void`

**Calls:**

- `_color.fromBufferAttribute`
- `ColorManagement.colorSpaceToWorking`
- `attribute.setXYZ`

**Internal Comments:**
```
// While .drc files do not specify colorspace, the only 'official' tooling
// is PLY and OBJ converters, which use sRGB. We'll assume sRGB when a .drc
// file is passed into .load() or .parse(). GLTFLoader uses internal APIs
// to decode geometry, and vertex colors are already Linear-sRGB in there.
```

<details><summary>Code</summary>

```typescript
_assignVertexColorSpace( attribute, inputColorSpace ) {

		// While .drc files do not specify colorspace, the only 'official' tooling
		// is PLY and OBJ converters, which use sRGB. We'll assume sRGB when a .drc
		// file is passed into .load() or .parse(). GLTFLoader uses internal APIs
		// to decode geometry, and vertex colors are already Linear-sRGB in there.

		if ( inputColorSpace !== SRGBColorSpace ) return;

		const _color = new Color();

		for ( let i = 0, il = attribute.count; i < il; i ++ ) {

			_color.fromBufferAttribute( attribute, i );
			ColorManagement.colorSpaceToWorking( _color, SRGBColorSpace );
			attribute.setXYZ( i, _color.r, _color.g, _color.b );

		}

	}
```
</details>

### `DRACOLoader._loadLibrary(url: any, responseType: any): Promise<any>`

**Parameters:**

- **`url`** `any`
- **`responseType`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `loader.setPath`
- `loader.setResponseType`
- `loader.setWithCredentials`
- `loader.load`

<details><summary>Code</summary>

```typescript
_loadLibrary( url, responseType ) {

		const loader = new FileLoader( this.manager );
		loader.setPath( this.decoderPath );
		loader.setResponseType( responseType );
		loader.setWithCredentials( this.withCredentials );

		return new Promise( ( resolve, reject ) => {

			loader.load( url, resolve, undefined, reject );

		} );

	}
```
</details>

### `DRACOLoader.preload(): this`

**Returns:** `this`

**Calls:**

- `this._initDecoder`

<details><summary>Code</summary>

```typescript
preload() {

		this._initDecoder();

		return this;

	}
```
</details>

### `DRACOLoader._initDecoder(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `librariesPending.push`
- `this._loadLibrary`
- `Promise.all( librariesPending )
			.then`
- `DRACOWorker.toString`
- `[
					'/* draco decoder */',
					jsContent,
					'',
					'/* worker */',
					fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
				].join`
- `fn.substring`
- `fn.indexOf`
- `fn.lastIndexOf`
- `URL.createObjectURL`

<details><summary>Code</summary>

```typescript
_initDecoder() {

		if ( this.decoderPending ) return this.decoderPending;

		const useJS = typeof WebAssembly !== 'object' || this.decoderConfig.type === 'js';
		const librariesPending = [];

		if ( useJS ) {

			librariesPending.push( this._loadLibrary( 'draco_decoder.js', 'text' ) );

		} else {

			librariesPending.push( this._loadLibrary( 'draco_wasm_wrapper.js', 'text' ) );
			librariesPending.push( this._loadLibrary( 'draco_decoder.wasm', 'arraybuffer' ) );

		}

		this.decoderPending = Promise.all( librariesPending )
			.then( ( libraries ) => {

				const jsContent = libraries[ 0 ];

				if ( ! useJS ) {

					this.decoderConfig.wasmBinary = libraries[ 1 ];

				}

				const fn = DRACOWorker.toString();

				const body = [
					'/* draco decoder */',
					jsContent,
					'',
					'/* worker */',
					fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
				].join( '\n' );

				this.workerSourceURL = URL.createObjectURL( new Blob( [ body ] ) );

			} );

		return this.decoderPending;

	}
```
</details>

### `DRACOLoader._getWorker(taskID: any, taskCost: any): Promise<any>`

**Parameters:**

- **`taskID`** `any`
- **`taskCost`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `this._initDecoder().then`
- `worker.postMessage`
- `worker._callbacks[ message.id ].resolve`
- `worker._callbacks[ message.id ].reject`
- `console.error`
- `this.workerPool.push`
- `this.workerPool.sort`

<details><summary>Code</summary>

```typescript
_getWorker( taskID, taskCost ) {

		return this._initDecoder().then( () => {

			if ( this.workerPool.length < this.workerLimit ) {

				const worker = new Worker( this.workerSourceURL );

				worker._callbacks = {};
				worker._taskCosts = {};
				worker._taskLoad = 0;

				worker.postMessage( { type: 'init', decoderConfig: this.decoderConfig } );

				worker.onmessage = function ( e ) {

					const message = e.data;

					switch ( message.type ) {

						case 'decode':
							worker._callbacks[ message.id ].resolve( message );
							break;

						case 'error':
							worker._callbacks[ message.id ].reject( message );
							break;

						default:
							console.error( 'THREE.DRACOLoader: Unexpected message, "' + message.type + '"' );

					}

				};

				this.workerPool.push( worker );

			} else {

				this.workerPool.sort( function ( a, b ) {

					return a._taskLoad > b._taskLoad ? - 1 : 1;

				} );

			}

			const worker = this.workerPool[ this.workerPool.length - 1 ];
			worker._taskCosts[ taskID ] = taskCost;
			worker._taskLoad += taskCost;
			return worker;

		} );

	}
```
</details>

### `DRACOLoader._releaseTask(worker: any, taskID: any): void`

**Parameters:**

- **`worker`** `any`
- **`taskID`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_releaseTask( worker, taskID ) {

		worker._taskLoad -= worker._taskCosts[ taskID ];
		delete worker._callbacks[ taskID ];
		delete worker._taskCosts[ taskID ];

	}
```
</details>

### `DRACOLoader.debug(): void`

**Returns:** `void`

**Calls:**

- `console.log`
- `this.workerPool.map`

<details><summary>Code</summary>

```typescript
debug() {

		console.log( 'Task load: ', this.workerPool.map( ( worker ) => worker._taskLoad ) );

	}
```
</details>

### `DRACOLoader.dispose(): this`

**Returns:** `this`

**Calls:**

- `this.workerPool[ i ].terminate`
- `URL.revokeObjectURL`

<details><summary>Code</summary>

```typescript
dispose() {

		for ( let i = 0; i < this.workerPool.length; ++ i ) {

			this.workerPool[ i ].terminate();

		}

		this.workerPool.length = 0;

		if ( this.workerSourceURL !== '' ) {

			URL.revokeObjectURL( this.workerSourceURL );

		}

		return this;

	}
```
</details>

### `DRACOWorker(): void`

**Returns:** `void`

**Calls:**

- `resolve`
- `DracoDecoderModule`
- `decoderPending.then`
- `decodeGeometry`
- `geometry.attributes.map`
- `buffers.push`
- `self.postMessage`
- `console.error`
- `draco.destroy`
- `decoder.GetEncodedGeometryType`
- `decoder.DecodeArrayToMesh`
- `decoder.DecodeArrayToPointCloud`
- `decodingStatus.ok`
- `decodingStatus.error_msg`
- `decoder.GetAttributeByUniqueId`
- `decoder.GetAttributeId`
- `decoder.GetAttribute`
- `decodeAttribute`
- `geometry.attributes.push`
- `decodeIndex`
- `dracoGeometry.num_faces`
- `draco._malloc`
- `decoder.GetTrianglesUInt32Array`
- `new Uint32Array( draco.HEAPF32.buffer, ptr, numIndices ).slice`
- `draco._free`
- `attribute.num_components`
- `dracoGeometry.num_points`
- `getDracoDataType`
- `decoder.GetAttributeDataArrayForAllPoints`
- `new attributeType( draco.HEAPF32.buffer, ptr, numValues ).slice`

**Internal Comments:**
```
// Module is Promise-like. Wrap before resolving to avoid loop. (x3)
// Gather all vertex attributes.
// A Draco file may be created with default vertex attributes, whose attribute IDs
// are mapped 1:1 from their semantic name (POSITION, NORMAL, ...). Alternatively,
// a Draco file may contain a custom set of attributes, identified by known unique
// IDs. glTF files always do the latter, and `.drc` files typically do the former.
// Add index.
```

<details><summary>Code</summary>

```typescript
function DRACOWorker() {

	let decoderConfig;
	let decoderPending;

	onmessage = function ( e ) {

		const message = e.data;

		switch ( message.type ) {

			case 'init':
				decoderConfig = message.decoderConfig;
				decoderPending = new Promise( function ( resolve/*, reject*/ ) {

					decoderConfig.onModuleLoaded = function ( draco ) {

						// Module is Promise-like. Wrap before resolving to avoid loop.
						resolve( { draco: draco } );

					};

					DracoDecoderModule( decoderConfig ); // eslint-disable-line no-undef

				} );
				break;

			case 'decode':
				const buffer = message.buffer;
				const taskConfig = message.taskConfig;
				decoderPending.then( ( module ) => {

					const draco = module.draco;
					const decoder = new draco.Decoder();

					try {

						const geometry = decodeGeometry( draco, decoder, new Int8Array( buffer ), taskConfig );

						const buffers = geometry.attributes.map( ( attr ) => attr.array.buffer );

						if ( geometry.index ) buffers.push( geometry.index.array.buffer );

						self.postMessage( { type: 'decode', id: message.id, geometry }, buffers );

					} catch ( error ) {

						console.error( error );

						self.postMessage( { type: 'error', id: message.id, error: error.message } );

					} finally {

						draco.destroy( decoder );

					}

				} );
				break;

		}

	};

	function decodeGeometry( draco, decoder, array, taskConfig ) {

		const attributeIDs = taskConfig.attributeIDs;
		const attributeTypes = taskConfig.attributeTypes;

		let dracoGeometry;
		let decodingStatus;

		const geometryType = decoder.GetEncodedGeometryType( array );

		if ( geometryType === draco.TRIANGULAR_MESH ) {

			dracoGeometry = new draco.Mesh();
			decodingStatus = decoder.DecodeArrayToMesh( array, array.byteLength, dracoGeometry );

		} else if ( geometryType === draco.POINT_CLOUD ) {

			dracoGeometry = new draco.PointCloud();
			decodingStatus = decoder.DecodeArrayToPointCloud( array, array.byteLength, dracoGeometry );

		} else {

			throw new Error( 'THREE.DRACOLoader: Unexpected geometry type.' );

		}

		if ( ! decodingStatus.ok() || dracoGeometry.ptr === 0 ) {

			throw new Error( 'THREE.DRACOLoader: Decoding failed: ' + decodingStatus.error_msg() );

		}

		const geometry = { index: null, attributes: [] };

		// Gather all vertex attributes.
		for ( const attributeName in attributeIDs ) {

			const attributeType = self[ attributeTypes[ attributeName ] ];

			let attribute;
			let attributeID;

			// A Draco file may be created with default vertex attributes, whose attribute IDs
			// are mapped 1:1 from their semantic name (POSITION, NORMAL, ...). Alternatively,
			// a Draco file may contain a custom set of attributes, identified by known unique
			// IDs. glTF files always do the latter, and `.drc` files typically do the former.
			if ( taskConfig.useUniqueIDs ) {

				attributeID = attributeIDs[ attributeName ];
				attribute = decoder.GetAttributeByUniqueId( dracoGeometry, attributeID );

			} else {

				attributeID = decoder.GetAttributeId( dracoGeometry, draco[ attributeIDs[ attributeName ] ] );

				if ( attributeID === - 1 ) continue;

				attribute = decoder.GetAttribute( dracoGeometry, attributeID );

			}

			const attributeResult = decodeAttribute( draco, decoder, dracoGeometry, attributeName, attributeType, attribute );

			if ( attributeName === 'color' ) {

				attributeResult.vertexColorSpace = taskConfig.vertexColorSpace;

			}

			geometry.attributes.push( attributeResult );

		}

		// Add index.
		if ( geometryType === draco.TRIANGULAR_MESH ) {

			geometry.index = decodeIndex( draco, decoder, dracoGeometry );

		}

		draco.destroy( dracoGeometry );

		return geometry;

	}

	function decodeIndex( draco, decoder, dracoGeometry ) {

		const numFaces = dracoGeometry.num_faces();
		const numIndices = numFaces * 3;
		const byteLength = numIndices * 4;

		const ptr = draco._malloc( byteLength );
		decoder.GetTrianglesUInt32Array( dracoGeometry, byteLength, ptr );
		const index = new Uint32Array( draco.HEAPF32.buffer, ptr, numIndices ).slice();
		draco._free( ptr );

		return { array: index, itemSize: 1 };

	}

	function decodeAttribute( draco, decoder, dracoGeometry, attributeName, attributeType, attribute ) {

		const numComponents = attribute.num_components();
		const numPoints = dracoGeometry.num_points();
		const numValues = numPoints * numComponents;
		const byteLength = numValues * attributeType.BYTES_PER_ELEMENT;
		const dataType = getDracoDataType( draco, attributeType );

		const ptr = draco._malloc( byteLength );
		decoder.GetAttributeDataArrayForAllPoints( dracoGeometry, attribute, dataType, byteLength, ptr );
		const array = new attributeType( draco.HEAPF32.buffer, ptr, numValues ).slice();
		draco._free( ptr );

		return {
			name: attributeName,
			array: array,
			itemSize: numComponents
		};

	}

	function getDracoDataType( draco, attributeType ) {

		switch ( attributeType ) {

			case Float32Array: return draco.DT_FLOAT32;
			case Int8Array: return draco.DT_INT8;
			case Int16Array: return draco.DT_INT16;
			case Int32Array: return draco.DT_INT32;
			case Uint8Array: return draco.DT_UINT8;
			case Uint16Array: return draco.DT_UINT16;
			case Uint32Array: return draco.DT_UINT32;

		}

	}

}
```
</details>

### `decodeGeometry(draco: any, decoder: any, array: any, taskConfig: any): { index: any; attributes: any[]; }`

**Parameters:**

- **`draco`** `any`
- **`decoder`** `any`
- **`array`** `any`
- **`taskConfig`** `any`

**Returns:** `{ index: any; attributes: any[]; }`

**Calls:**

- `decoder.GetEncodedGeometryType`
- `decoder.DecodeArrayToMesh`
- `decoder.DecodeArrayToPointCloud`
- `decodingStatus.ok`
- `decodingStatus.error_msg`
- `decoder.GetAttributeByUniqueId`
- `decoder.GetAttributeId`
- `decoder.GetAttribute`
- `decodeAttribute`
- `geometry.attributes.push`
- `decodeIndex`
- `draco.destroy`

**Internal Comments:**
```
// Gather all vertex attributes.
// A Draco file may be created with default vertex attributes, whose attribute IDs
// are mapped 1:1 from their semantic name (POSITION, NORMAL, ...). Alternatively,
// a Draco file may contain a custom set of attributes, identified by known unique
// IDs. glTF files always do the latter, and `.drc` files typically do the former.
// Add index.
```

<details><summary>Code</summary>

```typescript
function decodeGeometry( draco, decoder, array, taskConfig ) {

		const attributeIDs = taskConfig.attributeIDs;
		const attributeTypes = taskConfig.attributeTypes;

		let dracoGeometry;
		let decodingStatus;

		const geometryType = decoder.GetEncodedGeometryType( array );

		if ( geometryType === draco.TRIANGULAR_MESH ) {

			dracoGeometry = new draco.Mesh();
			decodingStatus = decoder.DecodeArrayToMesh( array, array.byteLength, dracoGeometry );

		} else if ( geometryType === draco.POINT_CLOUD ) {

			dracoGeometry = new draco.PointCloud();
			decodingStatus = decoder.DecodeArrayToPointCloud( array, array.byteLength, dracoGeometry );

		} else {

			throw new Error( 'THREE.DRACOLoader: Unexpected geometry type.' );

		}

		if ( ! decodingStatus.ok() || dracoGeometry.ptr === 0 ) {

			throw new Error( 'THREE.DRACOLoader: Decoding failed: ' + decodingStatus.error_msg() );

		}

		const geometry = { index: null, attributes: [] };

		// Gather all vertex attributes.
		for ( const attributeName in attributeIDs ) {

			const attributeType = self[ attributeTypes[ attributeName ] ];

			let attribute;
			let attributeID;

			// A Draco file may be created with default vertex attributes, whose attribute IDs
			// are mapped 1:1 from their semantic name (POSITION, NORMAL, ...). Alternatively,
			// a Draco file may contain a custom set of attributes, identified by known unique
			// IDs. glTF files always do the latter, and `.drc` files typically do the former.
			if ( taskConfig.useUniqueIDs ) {

				attributeID = attributeIDs[ attributeName ];
				attribute = decoder.GetAttributeByUniqueId( dracoGeometry, attributeID );

			} else {

				attributeID = decoder.GetAttributeId( dracoGeometry, draco[ attributeIDs[ attributeName ] ] );

				if ( attributeID === - 1 ) continue;

				attribute = decoder.GetAttribute( dracoGeometry, attributeID );

			}

			const attributeResult = decodeAttribute( draco, decoder, dracoGeometry, attributeName, attributeType, attribute );

			if ( attributeName === 'color' ) {

				attributeResult.vertexColorSpace = taskConfig.vertexColorSpace;

			}

			geometry.attributes.push( attributeResult );

		}

		// Add index.
		if ( geometryType === draco.TRIANGULAR_MESH ) {

			geometry.index = decodeIndex( draco, decoder, dracoGeometry );

		}

		draco.destroy( dracoGeometry );

		return geometry;

	}
```
</details>

### `decodeIndex(draco: any, decoder: any, dracoGeometry: any): { array: Uint32Array<ArrayBuffer>; itemSize: number; }`

**Parameters:**

- **`draco`** `any`
- **`decoder`** `any`
- **`dracoGeometry`** `any`

**Returns:** `{ array: Uint32Array<ArrayBuffer>; itemSize: number; }`

**Calls:**

- `dracoGeometry.num_faces`
- `draco._malloc`
- `decoder.GetTrianglesUInt32Array`
- `new Uint32Array( draco.HEAPF32.buffer, ptr, numIndices ).slice`
- `draco._free`

<details><summary>Code</summary>

```typescript
function decodeIndex( draco, decoder, dracoGeometry ) {

		const numFaces = dracoGeometry.num_faces();
		const numIndices = numFaces * 3;
		const byteLength = numIndices * 4;

		const ptr = draco._malloc( byteLength );
		decoder.GetTrianglesUInt32Array( dracoGeometry, byteLength, ptr );
		const index = new Uint32Array( draco.HEAPF32.buffer, ptr, numIndices ).slice();
		draco._free( ptr );

		return { array: index, itemSize: 1 };

	}
```
</details>

### `decodeAttribute(draco: any, decoder: any, dracoGeometry: any, attributeName: any, attributeType: any, attribute: any): { name: any; array: any; itemSize: any; }`

**Parameters:**

- **`draco`** `any`
- **`decoder`** `any`
- **`dracoGeometry`** `any`
- **`attributeName`** `any`
- **`attributeType`** `any`
- **`attribute`** `any`

**Returns:** `{ name: any; array: any; itemSize: any; }`

**Calls:**

- `attribute.num_components`
- `dracoGeometry.num_points`
- `getDracoDataType`
- `draco._malloc`
- `decoder.GetAttributeDataArrayForAllPoints`
- `new attributeType( draco.HEAPF32.buffer, ptr, numValues ).slice`
- `draco._free`

<details><summary>Code</summary>

```typescript
function decodeAttribute( draco, decoder, dracoGeometry, attributeName, attributeType, attribute ) {

		const numComponents = attribute.num_components();
		const numPoints = dracoGeometry.num_points();
		const numValues = numPoints * numComponents;
		const byteLength = numValues * attributeType.BYTES_PER_ELEMENT;
		const dataType = getDracoDataType( draco, attributeType );

		const ptr = draco._malloc( byteLength );
		decoder.GetAttributeDataArrayForAllPoints( dracoGeometry, attribute, dataType, byteLength, ptr );
		const array = new attributeType( draco.HEAPF32.buffer, ptr, numValues ).slice();
		draco._free( ptr );

		return {
			name: attributeName,
			array: array,
			itemSize: numComponents
		};

	}
```
</details>

### `getDracoDataType(draco: any, attributeType: any): any`

**Parameters:**

- **`draco`** `any`
- **`attributeType`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getDracoDataType( draco, attributeType ) {

		switch ( attributeType ) {

			case Float32Array: return draco.DT_FLOAT32;
			case Int8Array: return draco.DT_INT8;
			case Int16Array: return draco.DT_INT16;
			case Int32Array: return draco.DT_INT32;
			case Uint8Array: return draco.DT_UINT8;
			case Uint16Array: return draco.DT_UINT16;
			case Uint32Array: return draco.DT_UINT32;

		}

	}
```
</details>


---

## Classes

### `DRACOLoader`

<details><summary>Class Code</summary>

```ts
class DRACOLoader extends Loader {

	/**
	 * Constructs a new Draco loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		this.decoderPath = '';
		this.decoderConfig = {};
		this.decoderBinary = null;
		this.decoderPending = null;

		this.workerLimit = 4;
		this.workerPool = [];
		this.workerNextTaskID = 1;
		this.workerSourceURL = '';

		this.defaultAttributeIDs = {
			position: 'POSITION',
			normal: 'NORMAL',
			color: 'COLOR',
			uv: 'TEX_COORD'
		};
		this.defaultAttributeTypes = {
			position: 'Float32Array',
			normal: 'Float32Array',
			color: 'Float32Array',
			uv: 'Float32Array'
		};

	}

	/**
	 * Provides configuration for the decoder libraries. Configuration cannot be changed after decoding begins.
	 *
	 * @param {string} path - The decoder path.
	 * @return {DRACOLoader} A reference to this loader.
	 */
	setDecoderPath( path ) {

		this.decoderPath = path;

		return this;

	}

	/**
	 * Provides configuration for the decoder libraries. Configuration cannot be changed after decoding begins.
	 *
	 * @param {{type:('js'|'wasm')}} config - The decoder config.
	 * @return {DRACOLoader} A reference to this loader.
	 */
	setDecoderConfig( config ) {

		this.decoderConfig = config;

		return this;

	}

	/**
	 * Sets the maximum number of Web Workers to be used during decoding.
	 * A lower limit may be preferable if workers are also for other tasks in the application.
	 *
	 * @param {number} workerLimit - The worker limit.
	 * @return {DRACOLoader} A reference to this loader.
	 */
	setWorkerLimit( workerLimit ) {

		this.workerLimit = workerLimit;

		return this;

	}

	/**
	 * Starts loading from the given URL and passes the loaded Draco asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );

		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );

		loader.load( url, ( buffer ) => {

			this.parse( buffer, onLoad, onError );

		}, onProgress, onError );

	}

	/**
	 * Parses the given Draco data.
	 *
	 * @param {ArrayBuffer} buffer - The raw Draco data as an array buffer.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading/parsing process has been finished.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	parse( buffer, onLoad, onError = ()=>{} ) {

		this.decodeDracoFile( buffer, onLoad, null, null, SRGBColorSpace, onError ).catch( onError );

	}

	//

	decodeDracoFile( buffer, callback, attributeIDs, attributeTypes, vertexColorSpace = LinearSRGBColorSpace, onError = () => {} ) {

		const taskConfig = {
			attributeIDs: attributeIDs || this.defaultAttributeIDs,
			attributeTypes: attributeTypes || this.defaultAttributeTypes,
			useUniqueIDs: !! attributeIDs,
			vertexColorSpace: vertexColorSpace,
		};

		return this.decodeGeometry( buffer, taskConfig ).then( callback ).catch( onError );

	}

	decodeGeometry( buffer, taskConfig ) {

		const taskKey = JSON.stringify( taskConfig );

		// Check for an existing task using this buffer. A transferred buffer cannot be transferred
		// again from this thread.
		if ( _taskCache.has( buffer ) ) {

			const cachedTask = _taskCache.get( buffer );

			if ( cachedTask.key === taskKey ) {

				return cachedTask.promise;

			} else if ( buffer.byteLength === 0 ) {

				// Technically, it would be possible to wait for the previous task to complete,
				// transfer the buffer back, and decode again with the second configuration. That
				// is complex, and I don't know of any reason to decode a Draco buffer twice in
				// different ways, so this is left unimplemented.
				throw new Error(

					'THREE.DRACOLoader: Unable to re-decode a buffer with different ' +
					'settings. Buffer has already been transferred.'

				);

			}

		}

		//

		let worker;
		const taskID = this.workerNextTaskID ++;
		const taskCost = buffer.byteLength;

		// Obtain a worker and assign a task, and construct a geometry instance
		// when the task completes.
		const geometryPending = this._getWorker( taskID, taskCost )
			.then( ( _worker ) => {

				worker = _worker;

				return new Promise( ( resolve, reject ) => {

					worker._callbacks[ taskID ] = { resolve, reject };

					worker.postMessage( { type: 'decode', id: taskID, taskConfig, buffer }, [ buffer ] );

					// this.debug();

				} );

			} )
			.then( ( message ) => this._createGeometry( message.geometry ) );

		// Remove task from the task list.
		// Note: replaced '.finally()' with '.catch().then()' block - iOS 11 support (#19416)
		geometryPending
			.catch( () => true )
			.then( () => {

				if ( worker && taskID ) {

					this._releaseTask( worker, taskID );

					// this.debug();

				}

			} );

		// Cache the task result.
		_taskCache.set( buffer, {

			key: taskKey,
			promise: geometryPending

		} );

		return geometryPending;

	}

	_createGeometry( geometryData ) {

		const geometry = new BufferGeometry();

		if ( geometryData.index ) {

			geometry.setIndex( new BufferAttribute( geometryData.index.array, 1 ) );

		}

		for ( let i = 0; i < geometryData.attributes.length; i ++ ) {

			const result = geometryData.attributes[ i ];
			const name = result.name;
			const array = result.array;
			const itemSize = result.itemSize;

			const attribute = new BufferAttribute( array, itemSize );

			if ( name === 'color' ) {

				this._assignVertexColorSpace( attribute, result.vertexColorSpace );

				attribute.normalized = ( array instanceof Float32Array ) === false;

			}

			geometry.setAttribute( name, attribute );

		}

		return geometry;

	}

	_assignVertexColorSpace( attribute, inputColorSpace ) {

		// While .drc files do not specify colorspace, the only 'official' tooling
		// is PLY and OBJ converters, which use sRGB. We'll assume sRGB when a .drc
		// file is passed into .load() or .parse(). GLTFLoader uses internal APIs
		// to decode geometry, and vertex colors are already Linear-sRGB in there.

		if ( inputColorSpace !== SRGBColorSpace ) return;

		const _color = new Color();

		for ( let i = 0, il = attribute.count; i < il; i ++ ) {

			_color.fromBufferAttribute( attribute, i );
			ColorManagement.colorSpaceToWorking( _color, SRGBColorSpace );
			attribute.setXYZ( i, _color.r, _color.g, _color.b );

		}

	}

	_loadLibrary( url, responseType ) {

		const loader = new FileLoader( this.manager );
		loader.setPath( this.decoderPath );
		loader.setResponseType( responseType );
		loader.setWithCredentials( this.withCredentials );

		return new Promise( ( resolve, reject ) => {

			loader.load( url, resolve, undefined, reject );

		} );

	}

	preload() {

		this._initDecoder();

		return this;

	}

	_initDecoder() {

		if ( this.decoderPending ) return this.decoderPending;

		const useJS = typeof WebAssembly !== 'object' || this.decoderConfig.type === 'js';
		const librariesPending = [];

		if ( useJS ) {

			librariesPending.push( this._loadLibrary( 'draco_decoder.js', 'text' ) );

		} else {

			librariesPending.push( this._loadLibrary( 'draco_wasm_wrapper.js', 'text' ) );
			librariesPending.push( this._loadLibrary( 'draco_decoder.wasm', 'arraybuffer' ) );

		}

		this.decoderPending = Promise.all( librariesPending )
			.then( ( libraries ) => {

				const jsContent = libraries[ 0 ];

				if ( ! useJS ) {

					this.decoderConfig.wasmBinary = libraries[ 1 ];

				}

				const fn = DRACOWorker.toString();

				const body = [
					'/* draco decoder */',
					jsContent,
					'',
					'/* worker */',
					fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
				].join( '\n' );

				this.workerSourceURL = URL.createObjectURL( new Blob( [ body ] ) );

			} );

		return this.decoderPending;

	}

	_getWorker( taskID, taskCost ) {

		return this._initDecoder().then( () => {

			if ( this.workerPool.length < this.workerLimit ) {

				const worker = new Worker( this.workerSourceURL );

				worker._callbacks = {};
				worker._taskCosts = {};
				worker._taskLoad = 0;

				worker.postMessage( { type: 'init', decoderConfig: this.decoderConfig } );

				worker.onmessage = function ( e ) {

					const message = e.data;

					switch ( message.type ) {

						case 'decode':
							worker._callbacks[ message.id ].resolve( message );
							break;

						case 'error':
							worker._callbacks[ message.id ].reject( message );
							break;

						default:
							console.error( 'THREE.DRACOLoader: Unexpected message, "' + message.type + '"' );

					}

				};

				this.workerPool.push( worker );

			} else {

				this.workerPool.sort( function ( a, b ) {

					return a._taskLoad > b._taskLoad ? - 1 : 1;

				} );

			}

			const worker = this.workerPool[ this.workerPool.length - 1 ];
			worker._taskCosts[ taskID ] = taskCost;
			worker._taskLoad += taskCost;
			return worker;

		} );

	}

	_releaseTask( worker, taskID ) {

		worker._taskLoad -= worker._taskCosts[ taskID ];
		delete worker._callbacks[ taskID ];
		delete worker._taskCosts[ taskID ];

	}

	debug() {

		console.log( 'Task load: ', this.workerPool.map( ( worker ) => worker._taskLoad ) );

	}

	dispose() {

		for ( let i = 0; i < this.workerPool.length; ++ i ) {

			this.workerPool[ i ].terminate();

		}

		this.workerPool.length = 0;

		if ( this.workerSourceURL !== '' ) {

			URL.revokeObjectURL( this.workerSourceURL );

		}

		return this;

	}

}
```
</details>

#### Methods

##### `setDecoderPath(path: string): DRACOLoader`

<details><summary>Code</summary>

```ts
setDecoderPath( path ) {

		this.decoderPath = path;

		return this;

	}
```
</details>

##### `setDecoderConfig(config: { type: "js" | "wasm"; }): DRACOLoader`

<details><summary>Code</summary>

```ts
setDecoderConfig( config ) {

		this.decoderConfig = config;

		return this;

	}
```
</details>

##### `setWorkerLimit(workerLimit: number): DRACOLoader`

<details><summary>Code</summary>

```ts
setWorkerLimit( workerLimit ) {

		this.workerLimit = workerLimit;

		return this;

	}
```
</details>

##### `load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );

		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );

		loader.load( url, ( buffer ) => {

			this.parse( buffer, onLoad, onError );

		}, onProgress, onError );

	}
```
</details>

##### `parse(buffer: ArrayBuffer, onLoad: (arg0: BufferGeometry) => any, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
parse( buffer, onLoad, onError = ()=>{} ) {

		this.decodeDracoFile( buffer, onLoad, null, null, SRGBColorSpace, onError ).catch( onError );

	}
```
</details>

##### `decodeDracoFile(buffer: any, callback: any, attributeIDs: any, attributeTypes: any, vertexColorSpace: any, onError: () => void): any`

<details><summary>Code</summary>

```ts
decodeDracoFile( buffer, callback, attributeIDs, attributeTypes, vertexColorSpace = LinearSRGBColorSpace, onError = () => {} ) {

		const taskConfig = {
			attributeIDs: attributeIDs || this.defaultAttributeIDs,
			attributeTypes: attributeTypes || this.defaultAttributeTypes,
			useUniqueIDs: !! attributeIDs,
			vertexColorSpace: vertexColorSpace,
		};

		return this.decodeGeometry( buffer, taskConfig ).then( callback ).catch( onError );

	}
```
</details>

##### `decodeGeometry(buffer: any, taskConfig: any): any`

<details><summary>Code</summary>

```ts
decodeGeometry( buffer, taskConfig ) {

		const taskKey = JSON.stringify( taskConfig );

		// Check for an existing task using this buffer. A transferred buffer cannot be transferred
		// again from this thread.
		if ( _taskCache.has( buffer ) ) {

			const cachedTask = _taskCache.get( buffer );

			if ( cachedTask.key === taskKey ) {

				return cachedTask.promise;

			} else if ( buffer.byteLength === 0 ) {

				// Technically, it would be possible to wait for the previous task to complete,
				// transfer the buffer back, and decode again with the second configuration. That
				// is complex, and I don't know of any reason to decode a Draco buffer twice in
				// different ways, so this is left unimplemented.
				throw new Error(

					'THREE.DRACOLoader: Unable to re-decode a buffer with different ' +
					'settings. Buffer has already been transferred.'

				);

			}

		}

		//

		let worker;
		const taskID = this.workerNextTaskID ++;
		const taskCost = buffer.byteLength;

		// Obtain a worker and assign a task, and construct a geometry instance
		// when the task completes.
		const geometryPending = this._getWorker( taskID, taskCost )
			.then( ( _worker ) => {

				worker = _worker;

				return new Promise( ( resolve, reject ) => {

					worker._callbacks[ taskID ] = { resolve, reject };

					worker.postMessage( { type: 'decode', id: taskID, taskConfig, buffer }, [ buffer ] );

					// this.debug();

				} );

			} )
			.then( ( message ) => this._createGeometry( message.geometry ) );

		// Remove task from the task list.
		// Note: replaced '.finally()' with '.catch().then()' block - iOS 11 support (#19416)
		geometryPending
			.catch( () => true )
			.then( () => {

				if ( worker && taskID ) {

					this._releaseTask( worker, taskID );

					// this.debug();

				}

			} );

		// Cache the task result.
		_taskCache.set( buffer, {

			key: taskKey,
			promise: geometryPending

		} );

		return geometryPending;

	}
```
</details>

##### `_createGeometry(geometryData: any): any`

<details><summary>Code</summary>

```ts
_createGeometry( geometryData ) {

		const geometry = new BufferGeometry();

		if ( geometryData.index ) {

			geometry.setIndex( new BufferAttribute( geometryData.index.array, 1 ) );

		}

		for ( let i = 0; i < geometryData.attributes.length; i ++ ) {

			const result = geometryData.attributes[ i ];
			const name = result.name;
			const array = result.array;
			const itemSize = result.itemSize;

			const attribute = new BufferAttribute( array, itemSize );

			if ( name === 'color' ) {

				this._assignVertexColorSpace( attribute, result.vertexColorSpace );

				attribute.normalized = ( array instanceof Float32Array ) === false;

			}

			geometry.setAttribute( name, attribute );

		}

		return geometry;

	}
```
</details>

##### `_assignVertexColorSpace(attribute: any, inputColorSpace: any): void`

<details><summary>Code</summary>

```ts
_assignVertexColorSpace( attribute, inputColorSpace ) {

		// While .drc files do not specify colorspace, the only 'official' tooling
		// is PLY and OBJ converters, which use sRGB. We'll assume sRGB when a .drc
		// file is passed into .load() or .parse(). GLTFLoader uses internal APIs
		// to decode geometry, and vertex colors are already Linear-sRGB in there.

		if ( inputColorSpace !== SRGBColorSpace ) return;

		const _color = new Color();

		for ( let i = 0, il = attribute.count; i < il; i ++ ) {

			_color.fromBufferAttribute( attribute, i );
			ColorManagement.colorSpaceToWorking( _color, SRGBColorSpace );
			attribute.setXYZ( i, _color.r, _color.g, _color.b );

		}

	}
```
</details>

##### `_loadLibrary(url: any, responseType: any): Promise<any>`

<details><summary>Code</summary>

```ts
_loadLibrary( url, responseType ) {

		const loader = new FileLoader( this.manager );
		loader.setPath( this.decoderPath );
		loader.setResponseType( responseType );
		loader.setWithCredentials( this.withCredentials );

		return new Promise( ( resolve, reject ) => {

			loader.load( url, resolve, undefined, reject );

		} );

	}
```
</details>

##### `preload(): this`

<details><summary>Code</summary>

```ts
preload() {

		this._initDecoder();

		return this;

	}
```
</details>

##### `_initDecoder(): Promise<void>`

<details><summary>Code</summary>

```ts
_initDecoder() {

		if ( this.decoderPending ) return this.decoderPending;

		const useJS = typeof WebAssembly !== 'object' || this.decoderConfig.type === 'js';
		const librariesPending = [];

		if ( useJS ) {

			librariesPending.push( this._loadLibrary( 'draco_decoder.js', 'text' ) );

		} else {

			librariesPending.push( this._loadLibrary( 'draco_wasm_wrapper.js', 'text' ) );
			librariesPending.push( this._loadLibrary( 'draco_decoder.wasm', 'arraybuffer' ) );

		}

		this.decoderPending = Promise.all( librariesPending )
			.then( ( libraries ) => {

				const jsContent = libraries[ 0 ];

				if ( ! useJS ) {

					this.decoderConfig.wasmBinary = libraries[ 1 ];

				}

				const fn = DRACOWorker.toString();

				const body = [
					'/* draco decoder */',
					jsContent,
					'',
					'/* worker */',
					fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
				].join( '\n' );

				this.workerSourceURL = URL.createObjectURL( new Blob( [ body ] ) );

			} );

		return this.decoderPending;

	}
```
</details>

##### `_getWorker(taskID: any, taskCost: any): Promise<any>`

<details><summary>Code</summary>

```ts
_getWorker( taskID, taskCost ) {

		return this._initDecoder().then( () => {

			if ( this.workerPool.length < this.workerLimit ) {

				const worker = new Worker( this.workerSourceURL );

				worker._callbacks = {};
				worker._taskCosts = {};
				worker._taskLoad = 0;

				worker.postMessage( { type: 'init', decoderConfig: this.decoderConfig } );

				worker.onmessage = function ( e ) {

					const message = e.data;

					switch ( message.type ) {

						case 'decode':
							worker._callbacks[ message.id ].resolve( message );
							break;

						case 'error':
							worker._callbacks[ message.id ].reject( message );
							break;

						default:
							console.error( 'THREE.DRACOLoader: Unexpected message, "' + message.type + '"' );

					}

				};

				this.workerPool.push( worker );

			} else {

				this.workerPool.sort( function ( a, b ) {

					return a._taskLoad > b._taskLoad ? - 1 : 1;

				} );

			}

			const worker = this.workerPool[ this.workerPool.length - 1 ];
			worker._taskCosts[ taskID ] = taskCost;
			worker._taskLoad += taskCost;
			return worker;

		} );

	}
```
</details>

##### `_releaseTask(worker: any, taskID: any): void`

<details><summary>Code</summary>

```ts
_releaseTask( worker, taskID ) {

		worker._taskLoad -= worker._taskCosts[ taskID ];
		delete worker._callbacks[ taskID ];
		delete worker._taskCosts[ taskID ];

	}
```
</details>

##### `debug(): void`

<details><summary>Code</summary>

```ts
debug() {

		console.log( 'Task load: ', this.workerPool.map( ( worker ) => worker._taskLoad ) );

	}
```
</details>

##### `dispose(): this`

<details><summary>Code</summary>

```ts
dispose() {

		for ( let i = 0; i < this.workerPool.length; ++ i ) {

			this.workerPool[ i ].terminate();

		}

		this.workerPool.length = 0;

		if ( this.workerSourceURL !== '' ) {

			URL.revokeObjectURL( this.workerSourceURL );

		}

		return this;

	}
```
</details>


---