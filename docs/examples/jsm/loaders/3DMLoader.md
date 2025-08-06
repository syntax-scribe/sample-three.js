[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `3DMLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 21 |
| 🧱 Classes | 1 |
| 📦 Imports | 26 |
| 📊 Variables & Constants | 106 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/3DMLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometryLoader` | `three` |
| `CanvasTexture` | `three` |
| `ClampToEdgeWrapping` | `three` |
| `Color` | `three` |
| `DirectionalLight` | `three` |
| `DoubleSide` | `three` |
| `FileLoader` | `three` |
| `LinearFilter` | `three` |
| `Line` | `three` |
| `LineBasicMaterial` | `three` |
| `Loader` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshPhysicalMaterial` | `three` |
| `MeshStandardMaterial` | `three` |
| `Object3D` | `three` |
| `PointLight` | `three` |
| `Points` | `three` |
| `PointsMaterial` | `three` |
| `RectAreaLight` | `three` |
| `RepeatWrapping` | `three` |
| `SpotLight` | `three` |
| `Sprite` | `three` |
| `SpriteMaterial` | `three` |
| `TextureLoader` | `three` |
| `EXRLoader` | `../loaders/EXRLoader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_taskCache` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `worker` | `any` | let/var | `*not shown*` | ✗ |
| `taskID` | `any` | let/var | `*not shown*` | ✗ |
| `taskCost` | `number` | let/var | `buffer.byteLength` | ✗ |
| `mat` | `{ name: any; color: { r: any; g: any;...` | let/var | `{}` | ✗ |
| `m` | `any` | let/var | `this.materials[ i ]` | ✗ |
| `_mat` | `{ name: any; color: {}; type: any; ve...` | let/var | `{}` | ✗ |
| `mat` | `any` | let/var | `new MeshPhysicalMaterial( { color: new Color( material.diffuseColor.r / 255.0...` | ✗ |
| `pbr` | `any` | let/var | `material.pbr` | ✗ |
| `textureLoader` | `any` | let/var | `new TextureLoader()` | ✗ |
| `texture` | `any` | let/var | `material.textures[ i ]` | ✗ |
| `object` | `any` | let/var | `new Object3D()` | ✗ |
| `instanceDefinitionObjects` | `any[]` | let/var | `[]` | ✗ |
| `instanceDefinitions` | `any[]` | let/var | `[]` | ✗ |
| `instanceReferences` | `any[]` | let/var | `[]` | ✗ |
| `objects` | `any` | let/var | `data.objects` | ✗ |
| `materials` | `any` | let/var | `data.materials` | ✗ |
| `obj` | `any` | let/var | `objects[ i ]` | ✗ |
| `attributes` | `any` | let/var | `obj.attributes` | ✗ |
| `matId` | `any` | let/var | `null` | ✗ |
| `material` | `any` | let/var | `null` | ✗ |
| `rMaterial` | `any` | let/var | `materials[ matId ]` | ✗ |
| `layer` | `any` | let/var | `data.layers[ attributes.layerIndex ]` | ✗ |
| `iDef` | `any` | let/var | `instanceDefinitions[ i ]` | ✗ |
| `objId` | `any` | let/var | `iDef.attributes.objectIds[ j ]` | ✗ |
| `idoId` | `any` | let/var | `instanceDefinitionObjects[ p ].userData.attributes.id` | ✗ |
| `iRef` | `any` | let/var | `instanceReferences[ j ]` | ✗ |
| `iRefObject` | `any` | let/var | `new Object3D()` | ✗ |
| `xf` | `any` | let/var | `iRef.geometry.xform.array` | ✗ |
| `matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `loader` | `any` | let/var | `new BufferGeometryLoader()` | ✗ |
| `attributes` | `any` | let/var | `obj.attributes` | ✗ |
| `geometry` | `any` | let/var | `*not shown*` | ✗ |
| `material` | `any` | let/var | `*not shown*` | ✗ |
| `_color` | `any` | let/var | `*not shown*` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `points` | `any` | let/var | `new Points( geometry, material )` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( geometry, mat )` | ✗ |
| `lines` | `any` | let/var | `new Line( geometry, material )` | ✗ |
| `font` | `string` | let/var | ``${geometry.fontHeight}px ${geometry.fontFace}`` | ✗ |
| `width` | `number` | let/var | `ctx.measureText( geometry.text ).width + 10` | ✗ |
| `height` | `any` | let/var | `geometry.fontHeight + 10` | ✗ |
| `r` | `number` | let/var | `window.devicePixelRatio` | ✗ |
| `texture` | `any` | let/var | `new CanvasTexture( ctx.canvas )` | ✗ |
| `sprite` | `any` | let/var | `new Sprite( material )` | ✗ |
| `light` | `any` | let/var | `*not shown*` | ✗ |
| `jsLoader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `jsContent` | `Promise<any>` | let/var | `new Promise( ( resolve, reject ) => { jsLoader.load( 'rhino3dm.js', resolve, ...` | ✗ |
| `binaryLoader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `binaryContent` | `Promise<any>` | let/var | `new Promise( ( resolve, reject ) => { binaryLoader.load( 'rhino3dm.wasm', res...` | ✗ |
| `worker` | `Worker` | let/var | `new Worker( this.workerSourceURL )` | ✗ |
| `message` | `any` | let/var | `e.data` | ✗ |
| `worker` | `any` | let/var | `this.workerPool[ this.workerPool.length - 1 ]` | ✗ |
| `libraryPending` | `any` | let/var | `*not shown*` | ✗ |
| `libraryConfig` | `any` | let/var | `*not shown*` | ✗ |
| `rhino` | `any` | let/var | `*not shown*` | ✗ |
| `taskID` | `any` | let/var | `*not shown*` | ✗ |
| `message` | `any` | let/var | `e.data` | ✗ |
| `wasmBinary` | `any` | let/var | `libraryConfig.wasmBinary` | ✗ |
| `RhinoModule` | `any` | let/var | `*not shown*` | ✗ |
| `buffer` | `any` | let/var | `message.buffer` | ✗ |
| `arr` | `Uint8Array<any>` | let/var | `new Uint8Array( buffer )` | ✗ |
| `objects` | `any[]` | let/var | `[]` | ✗ |
| `materials` | `any[]` | let/var | `[]` | ✗ |
| `layers` | `any[]` | let/var | `[]` | ✗ |
| `views` | `any[]` | let/var | `[]` | ✗ |
| `namedViews` | `any[]` | let/var | `[]` | ✗ |
| `groups` | `any[]` | let/var | `[]` | ✗ |
| `strings` | `any[]` | let/var | `[]` | ✗ |
| `cnt` | `any` | let/var | `objs.count` | ✗ |
| `textureTypes` | `any[]` | let/var | `[ // rhino.TextureType.Bitmap, rhino.TextureType.Diffuse, rhino.TextureType.B...` | ✗ |
| `pbrTextureTypes` | `any[]` | let/var | `[ rhino.TextureType.PBR_BaseColor, rhino.TextureType.PBR_Subsurface, rhino.Te...` | ✗ |
| `textures` | `any[]` | let/var | `[]` | ✗ |
| `strings_count` | `any` | let/var | `doc.strings().count` | ✗ |
| `reflectionId` | `any` | let/var | `doc.settings().renderSettings().renderEnvironments.reflectionId` | ✗ |
| `renderEnvironment` | `any` | let/var | `null` | ✗ |
| `id` | `any` | let/var | `content.id` | ✗ |
| `fileName` | `any` | let/var | `renderTexture.fileName` | ✗ |
| `_fileName` | `any` | let/var | `doc.embeddedFiles().get( j ).fileName` | ✗ |
| `backgroundImage` | `string` | let/var | `'data:image/png;base64,' + background` | ✗ |
| `renderSettings` | `{ ambientLight: any; backgroundColorT...` | let/var | `{ ambientLight: doc.settings().renderSettings().ambientLight, backgroundColor...` | ✗ |
| `textures` | `any[]` | let/var | `[]` | ✗ |
| `textureType` | `any` | let/var | `tTypes[ i ].constructor.name` | ✗ |
| `texture` | `{ type: any; }` | let/var | `{ type: tType }` | ✗ |
| `objectType` | `any` | let/var | `_geometry.objectType` | ✗ |
| `geometry` | `any` | let/var | `*not shown*` | ✗ |
| `attributes` | `any` | let/var | `*not shown*` | ✗ |
| `position` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `mesh` | `any` | let/var | `*not shown*` | ✗ |
| `pt` | `any` | let/var | `_geometry.location` | ✗ |
| `color` | `{ itemSize: number; type: string; arr...` | let/var | `{}` | ✗ |
| `result` | `{}` | let/var | `{}` | ✗ |
| `value` | `any` | let/var | `object[ property ]` | ✗ |
| `pointCount` | `any` | let/var | `pointLimit` | ✗ |
| `rc` | `any[]` | let/var | `[]` | ✗ |
| `ts` | `any[]` | let/var | `[]` | ✗ |
| `segmentCount` | `any` | let/var | `curve.segmentCount` | ✗ |
| `domain` | `any` | let/var | `curve.domain` | ✗ |
| `divisions` | `number` | let/var | `pointCount - 1.0` | ✗ |
| `t` | `any` | let/var | `domain[ 0 ] + ( j / divisions ) * ( domain[ 1 ] - domain[ 0 ] )` | ✗ |
| `tS` | `number` | let/var | `tan[ 0 ] * tan[ 0 ] + tan[ 1 ] * tan[ 1 ] + tan[ 2 ] * tan[ 2 ]` | ✗ |
| `ptS` | `number` | let/var | `prevTan[ 0 ] * prevTan[ 0 ] + prevTan[ 1 ] * prevTan[ 1 ] + prevTan[ 2 ] * pr...` | ✗ |
| `angle` | `any` | let/var | `*not shown*` | ✗ |
| `theta` | `number` | let/var | `( tan.x * prevTan.x + tan.y * prevTan.y + tan.z * prevTan.z ) / denominator` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `Rhino3dmWorker` | *none* | new Promise( function ( resolve ) {

					/* Like Basis Loader */
					RhinoModule = { wasmBinary, onRuntimeInitialized: resolve };

					rhino3dm( RhinoModule ); // eslint-disable-line no-undef

				 } ).then, new Promise(...), libraryPending.then |


---

## Functions

### `Rhino3dmLoader.setLibraryPath(path: string): Rhino3dmLoader`

**JSDoc:**
```typescript
/**
	 * Path to a folder containing the JS and WASM libraries.
	 *
	 * @param {string} path - The library path to set.
	 * @return {Rhino3dmLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`path`** `string`

**Returns:** `Rhino3dmLoader`

<details><summary>Code</summary>

```typescript
setLibraryPath( path ) {

		this.libraryPath = path;

		return this;

	}
```
</details>

### `Rhino3dmLoader.setWorkerLimit(workerLimit: number): Rhino3dmLoader`

**JSDoc:**
```typescript
/**
	 * Sets the maximum number of Web Workers to be used during decoding.
	 * A lower limit may be preferable if workers are also for other
	 * tasks in the application.
	 *
	 * @param {number} workerLimit - The worker limit.
	 * @return {Rhino3dmLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`workerLimit`** `number`

**Returns:** `Rhino3dmLoader`

<details><summary>Code</summary>

```typescript
setWorkerLimit( workerLimit ) {

		this.workerLimit = workerLimit;

		return this;

	}
```
</details>

### `Rhino3dmLoader.load(url: string, onLoad: (arg0: Object3D) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded 3DM asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Object3D)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Object3D) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setResponseType`
- `loader.setRequestHeader`
- `loader.load`
- `_taskCache.has`
- `_taskCache.get`
- `cachedTask.promise.then( onLoad ).catch`
- `this.decodeObjects( buffer, url )
				.then( result => {

					result.userData.warnings = this.warnings;
					onLoad( result );

				 } )
				.catch`
- `onError`

**Internal Comments:**
```
// Check for an existing task using this buffer. A transferred buffer cannot be transferred
// again from this thread.
```

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );

		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );

		this.url = url;

		loader.load( url, ( buffer ) => {

			// Check for an existing task using this buffer. A transferred buffer cannot be transferred
			// again from this thread.
			if ( _taskCache.has( buffer ) ) {

				const cachedTask = _taskCache.get( buffer );

				return cachedTask.promise.then( onLoad ).catch( onError );

			}

			this.decodeObjects( buffer, url )
				.then( result => {

					result.userData.warnings = this.warnings;
					onLoad( result );

				 } )
				.catch( e => onError( e ) );

		}, onProgress, onError );

	}
```
</details>

### `Rhino3dmLoader.debug(): void`

**JSDoc:**
```typescript
/**
	 * Prints debug messages to the browser console.
	 */
```

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

### `Rhino3dmLoader.decodeObjects(buffer: ArrayBuffer, url: string): Promise<Object3D>`

**JSDoc:**
```typescript
/**
	 * Decodes the 3DM asset data with a Web Worker.
	 *
	 * @param {ArrayBuffer} buffer - The raw 3DM asset data as an array buffer.
	 * @param {string} url - The asset URL.
	 * @return {Promise<Object3D>} A Promise that resolved with the decoded 3D object.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`
- **`url`** `string`

**Returns:** `Promise<Object3D>`

**Calls:**

- `this._getWorker( taskCost )
			.then( ( _worker ) => {

				worker = _worker;
				taskID = this.workerNextTaskID ++;

				return new Promise( ( resolve, reject ) => {

					worker._callbacks[ taskID ] = { resolve, reject };

					worker.postMessage( { type: 'decode', id: taskID, buffer }, [ buffer ] );

					// this.debug();

				} );

			} )
			.then( ( message ) => this._createGeometry( message.data ) )
			.catch`
- `objectPending
			.catch( () => true )
			.then`
- `this._releaseTask`
- `_taskCache.set`

**Internal Comments:**
```
// Remove task from the task list. (x6)
// Note: replaced '.finally()' with '.catch().then()' block - iOS 11 support (#19416) (x6)
// Cache the task result. (x4)
```

<details><summary>Code</summary>

```typescript
decodeObjects( buffer, url ) {

		let worker;
		let taskID;

		const taskCost = buffer.byteLength;

		const objectPending = this._getWorker( taskCost )
			.then( ( _worker ) => {

				worker = _worker;
				taskID = this.workerNextTaskID ++;

				return new Promise( ( resolve, reject ) => {

					worker._callbacks[ taskID ] = { resolve, reject };

					worker.postMessage( { type: 'decode', id: taskID, buffer }, [ buffer ] );

					// this.debug();

				} );

			} )
			.then( ( message ) => this._createGeometry( message.data ) )
			.catch( e => {

				throw e;

			} );

		// Remove task from the task list.
		// Note: replaced '.finally()' with '.catch().then()' block - iOS 11 support (#19416)
		objectPending
			.catch( () => true )
			.then( () => {

				if ( worker && taskID ) {

					this._releaseTask( worker, taskID );

					//this.debug();

				}

			} );

		// Cache the task result.
		_taskCache.set( buffer, {

			url: url,
			promise: objectPending

		} );

		return objectPending;

	}
```
</details>

### `Rhino3dmLoader.parse(data: ArrayBuffer, onLoad: (arg0: Object3D) => any, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Parses the given 3DM data and passes the loaded 3DM asset
	 * to the `onLoad()` callback.
	 *
	 * @param {ArrayBuffer} data - The raw 3DM asset data as an array buffer.
	 * @param {function(Object3D)} onLoad - Executed when the loading process has been finished.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`
- **`onLoad`** `(arg0: Object3D) => any`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `this.decodeObjects( data, '' )
			.then( result => {

				result.userData.warnings = this.warnings;
				onLoad( result );

			} )
			.catch`
- `onError`

<details><summary>Code</summary>

```typescript
parse( data, onLoad, onError ) {

		this.decodeObjects( data, '' )
			.then( result => {

				result.userData.warnings = this.warnings;
				onLoad( result );

			} )
			.catch( e => onError( e ) );

	}
```
</details>

### `Rhino3dmLoader._compareMaterials(material: any): any`

**Parameters:**

- **`material`** `any`

**Returns:** `any`

**Calls:**

- `JSON.stringify`
- `this.materials.push`

<details><summary>Code</summary>

```typescript
_compareMaterials( material ) {

		const mat = {};
		mat.name = material.name;
		mat.color = {};
		mat.color.r = material.color.r;
		mat.color.g = material.color.g;
		mat.color.b = material.color.b;
		mat.type = material.type;
		mat.vertexColors = material.vertexColors;

		const json = JSON.stringify( mat );

		for ( let i = 0; i < this.materials.length; i ++ ) {

			const m = this.materials[ i ];
			const _mat = {};
			_mat.name = m.name;
			_mat.color = {};
			_mat.color.r = m.color.r;
			_mat.color.g = m.color.g;
			_mat.color.b = m.color.b;
			_mat.type = m.type;
			_mat.vertexColors = m.vertexColors;

			if ( JSON.stringify( _mat ) === json ) {

				return m;

			}

		}

		this.materials.push( material );

		return material;

	}
```
</details>

### `Rhino3dmLoader._createMaterial(material: any, renderEnvironment: any): any`

**Parameters:**

- **`material`** `any`
- **`renderEnvironment`** `any`

**Returns:** `any`

**Calls:**

- `textureLoader.load`
- `this.warnings.push`
- `map.repeat.set`
- `new EXRLoader().load`

**Internal Comments:**
```
//console.log(material) (x2)
//some compromises (x4)
//console.log(texture.type )
```

<details><summary>Code</summary>

```typescript
_createMaterial( material, renderEnvironment ) {

		if ( material === undefined ) {

			return new MeshStandardMaterial( {
				color: new Color( 1, 1, 1 ),
				metalness: 0.8,
				name: Loader.DEFAULT_MATERIAL_NAME,
				side: DoubleSide
			} );

		}

		//console.log(material)

		const mat = new MeshPhysicalMaterial( {

			color: new Color( material.diffuseColor.r / 255.0, material.diffuseColor.g / 255.0, material.diffuseColor.b / 255.0 ),
			emissive: new Color( material.emissionColor.r, material.emissionColor.g, material.emissionColor.b ),
			flatShading: material.disableLighting,
			ior: material.indexOfRefraction,
			name: material.name,
			reflectivity: material.reflectivity,
			opacity: 1.0 - material.transparency,
			side: DoubleSide,
			specularColor: material.specularColor,
			transparent: material.transparency > 0 ? true : false

		} );

		mat.userData.id = material.id;

		if ( material.pbrSupported ) {

			const pbr = material.pbr;

			mat.anisotropy = pbr.anisotropic;
			mat.anisotropyRotation = pbr.anisotropicRotation;
			mat.color = new Color( pbr.baseColor.r, pbr.baseColor.g, pbr.baseColor.b );
			mat.clearcoat = pbr.clearcoat;
			mat.clearcoatRoughness = pbr.clearcoatRoughness;
			mat.metalness = pbr.metallic;
			mat.transmission = 1 - pbr.opacity;
			mat.roughness = pbr.roughness;
			mat.sheen = pbr.sheen;
			mat.specularIntensity = pbr.specular;
			mat.thickness = pbr.subsurface;

		}

		if ( material.pbrSupported && material.pbr.opacity === 0 && material.transparency === 1 ) {

			//some compromises

			mat.opacity = 0.2;
			mat.transmission = 1.00;

		}

		const textureLoader = new TextureLoader();

		for ( let i = 0; i < material.textures.length; i ++ ) {

			const texture = material.textures[ i ];

			if ( texture.image !== null ) {

				const map = textureLoader.load( texture.image );

				//console.log(texture.type )

				switch ( texture.type ) {

					case 'Bump':

						mat.bumpMap = map;

						break;

					case 'Diffuse':

						mat.map = map;

						break;

					case 'Emap':

						mat.envMap = map;

						break;

					case 'Opacity':

						mat.transmissionMap = map;

						break;

					case 'Transparency':

						mat.alphaMap = map;
						mat.transparent = true;

						break;

					case 'PBR_Alpha':

						mat.alphaMap = map;
						mat.transparent = true;

						break;

					case 'PBR_AmbientOcclusion':

						mat.aoMap = map;

						break;

					case 'PBR_Anisotropic':

						mat.anisotropyMap = map;

						break;

					case 'PBR_BaseColor':

						mat.map = map;

						break;

					case 'PBR_Clearcoat':

						mat.clearcoatMap = map;

						break;

					case 'PBR_ClearcoatBump':

						mat.clearcoatNormalMap = map;

						break;

					case 'PBR_ClearcoatRoughness':

						mat.clearcoatRoughnessMap = map;

						break;

					case 'PBR_Displacement':

						mat.displacementMap = map;

						break;

					case 'PBR_Emission':

						mat.emissiveMap = map;

						break;

					case 'PBR_Metallic':

						mat.metalnessMap = map;

						break;

					case 'PBR_Roughness':

						mat.roughnessMap = map;

						break;

					case 'PBR_Sheen':

						mat.sheenColorMap = map;

						break;

					case 'PBR_Specular':

						mat.specularColorMap = map;

						break;

					case 'PBR_Subsurface':

						mat.thicknessMap = map;

						break;

					default:

						this.warnings.push( {
							message: `THREE.3DMLoader: No conversion exists for 3dm ${texture.type}.`,
							type: 'no conversion'
						} );

						break;

				}

				map.wrapS = texture.wrapU === 0 ? RepeatWrapping : ClampToEdgeWrapping;
				map.wrapT = texture.wrapV === 0 ? RepeatWrapping : ClampToEdgeWrapping;

				if ( texture.repeat ) {

					map.repeat.set( texture.repeat[ 0 ], texture.repeat[ 1 ] );

				}

			}

		}

		if ( renderEnvironment ) {

			new EXRLoader().load( renderEnvironment.image, function ( texture ) {

				texture.mapping = THREE.EquirectangularReflectionMapping;
				mat.envMap = texture;

			} );

		}

		return mat;

	}
```
</details>

### `Rhino3dmLoader._createGeometry(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `instanceDefinitions.push`
- `instanceReferences.push`
- `this._createMaterial`
- `this._createObject`
- `instanceDefinitionObjects.push`
- `object.add`
- `objects.push`
- `matrix.set`
- `iRefObject.applyMatrix4`
- `iRefObject.add`
- `objects[ p ].clone`

**Internal Comments:**
```
//check layer index
// Currently clones geometry and does not take advantage of instancing
```

<details><summary>Code</summary>

```typescript
_createGeometry( data ) {

		const object = new Object3D();
		const instanceDefinitionObjects = [];
		const instanceDefinitions = [];
		const instanceReferences = [];

		object.userData[ 'layers' ] = data.layers;
		object.userData[ 'groups' ] = data.groups;
		object.userData[ 'settings' ] = data.settings;
		object.userData.settings[ 'renderSettings' ] = data.renderSettings;
		object.userData[ 'objectType' ] = 'File3dm';
		object.userData[ 'materials' ] = null;

		object.name = this.url;

		let objects = data.objects;
		const materials = data.materials;

		for ( let i = 0; i < objects.length; i ++ ) {

			const obj = objects[ i ];
			const attributes = obj.attributes;

			switch ( obj.objectType ) {

				case 'InstanceDefinition':

					instanceDefinitions.push( obj );

					break;

				case 'InstanceReference':

					instanceReferences.push( obj );

					break;

				default:

					let matId = null;

					switch ( attributes.materialSource.name ) {

						case 'ObjectMaterialSource_MaterialFromLayer':
							//check layer index
							if ( attributes.layerIndex >= 0 ) {

								matId = data.layers[ attributes.layerIndex ].renderMaterialIndex;

							}

							break;

						case 'ObjectMaterialSource_MaterialFromObject':

							if ( attributes.materialIndex >= 0 ) {

								matId = attributes.materialIndex;

							}

							break;

					}

					let material = null;

					if ( matId >= 0 ) {

						const rMaterial = materials[ matId ];
						material = this._createMaterial( rMaterial, data.renderEnvironment );


					}

					const _object = this._createObject( obj, material );

					if ( _object === undefined ) {

						continue;

					}

					const layer = data.layers[ attributes.layerIndex ];

					_object.visible = layer ? data.layers[ attributes.layerIndex ].visible : true;

					if ( attributes.isInstanceDefinitionObject ) {

						instanceDefinitionObjects.push( _object );

					} else {

						object.add( _object );

					}

					break;

			}

		}

		for ( let i = 0; i < instanceDefinitions.length; i ++ ) {

			const iDef = instanceDefinitions[ i ];

			objects = [];

			for ( let j = 0; j < iDef.attributes.objectIds.length; j ++ ) {

				const objId = iDef.attributes.objectIds[ j ];

				for ( let p = 0; p < instanceDefinitionObjects.length; p ++ ) {

					const idoId = instanceDefinitionObjects[ p ].userData.attributes.id;

					if ( objId === idoId ) {

						objects.push( instanceDefinitionObjects[ p ] );

					}

				}

			}

			// Currently clones geometry and does not take advantage of instancing

			for ( let j = 0; j < instanceReferences.length; j ++ ) {

				const iRef = instanceReferences[ j ];

				if ( iRef.geometry.parentIdefId === iDef.attributes.id ) {

					const iRefObject = new Object3D();
					const xf = iRef.geometry.xform.array;

					const matrix = new Matrix4();
					matrix.set( ...xf );

					iRefObject.applyMatrix4( matrix );

					for ( let p = 0; p < objects.length; p ++ ) {

						iRefObject.add( objects[ p ].clone( true ) );

					}

					object.add( iRefObject );

				}

			}

		}

		object.userData[ 'materials' ] = this.materials;
		object.name = '';
		return object;

	}
```
</details>

### `Rhino3dmLoader._createObject(obj: any, mat: any): any`

**Parameters:**

- **`obj`** `any`
- **`mat`** `any`

**Returns:** `any`

**Calls:**

- `loader.parse`
- `geometry.attributes.hasOwnProperty`
- `this._compareMaterials`
- `this._createMaterial`
- `document.createElement( 'canvas' ).getContext`
- `ctx.measureText`
- `ctx.setTransform`
- `ctx.fillRect`
- `ctx.fillText`
- `sprite.position.set`
- `sprite.scale.set`
- `light.position.set`
- `light.target.position.set`
- `Math.abs`
- `light.lookAt`

**Internal Comments:**
```
// no conversion exists, warning has already been printed to the console
```

<details><summary>Code</summary>

```typescript
_createObject( obj, mat ) {

		const loader = new BufferGeometryLoader();

		const attributes = obj.attributes;

		let geometry, material, _color, color;

		switch ( obj.objectType ) {

			case 'Point':
			case 'PointSet':

				geometry = loader.parse( obj.geometry );

				if ( geometry.attributes.hasOwnProperty( 'color' ) ) {

					material = new PointsMaterial( { vertexColors: true, sizeAttenuation: false, size: 2 } );

				} else {

					_color = attributes.drawColor;
					color = new Color( _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 );
					material = new PointsMaterial( { color: color, sizeAttenuation: false, size: 2 } );

				}

				material = this._compareMaterials( material );

				const points = new Points( geometry, material );
				points.userData[ 'attributes' ] = attributes;
				points.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					points.name = attributes.name;

				}

				return points;

			case 'Mesh':
			case 'Extrusion':
			case 'SubD':
			case 'Brep':

				if ( obj.geometry === null ) return;

				geometry = loader.parse( obj.geometry );


				if ( mat === null ) {

					mat = this._createMaterial();

				}


				if ( geometry.attributes.hasOwnProperty( 'color' ) ) {

					mat.vertexColors = true;

				}

				mat = this._compareMaterials( mat );

				const mesh = new Mesh( geometry, mat );
				mesh.castShadow = attributes.castsShadows;
				mesh.receiveShadow = attributes.receivesShadows;
				mesh.userData[ 'attributes' ] = attributes;
				mesh.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					mesh.name = attributes.name;

				}

				return mesh;

			case 'Curve':

				geometry = loader.parse( obj.geometry );

				_color = attributes.drawColor;
				color = new Color( _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 );

				material = new LineBasicMaterial( { color: color } );
				material = this._compareMaterials( material );

				const lines = new Line( geometry, material );
				lines.userData[ 'attributes' ] = attributes;
				lines.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					lines.name = attributes.name;

				}

				return lines;

			case 'TextDot':

				geometry = obj.geometry;

				const ctx = document.createElement( 'canvas' ).getContext( '2d' );
				const font = `${geometry.fontHeight}px ${geometry.fontFace}`;
				ctx.font = font;
				const width = ctx.measureText( geometry.text ).width + 10;
				const height = geometry.fontHeight + 10;

				const r = window.devicePixelRatio;

				ctx.canvas.width = width * r;
				ctx.canvas.height = height * r;
				ctx.canvas.style.width = width + 'px';
				ctx.canvas.style.height = height + 'px';
				ctx.setTransform( r, 0, 0, r, 0, 0 );

				ctx.font = font;
				ctx.textBaseline = 'middle';
				ctx.textAlign = 'center';
				color = attributes.drawColor;
				ctx.fillStyle = `rgba(${color.r},${color.g},${color.b},${color.a})`;
				ctx.fillRect( 0, 0, width, height );
				ctx.fillStyle = 'white';
				ctx.fillText( geometry.text, width / 2, height / 2 );

				const texture = new CanvasTexture( ctx.canvas );
				texture.minFilter = LinearFilter;
				texture.generateMipmaps = false;
				texture.wrapS = ClampToEdgeWrapping;
				texture.wrapT = ClampToEdgeWrapping;

				material = new SpriteMaterial( { map: texture, depthTest: false } );
				const sprite = new Sprite( material );
				sprite.position.set( geometry.point[ 0 ], geometry.point[ 1 ], geometry.point[ 2 ] );
				sprite.scale.set( width / 10, height / 10, 1.0 );

				sprite.userData[ 'attributes' ] = attributes;
				sprite.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					sprite.name = attributes.name;

				}

				return sprite;

			case 'Light':

				geometry = obj.geometry;

				let light;

				switch ( geometry.lightStyle.name ) {

					case 'LightStyle_WorldPoint':

						light = new PointLight();
						light.castShadow = attributes.castsShadows;
						light.position.set( geometry.location[ 0 ], geometry.location[ 1 ], geometry.location[ 2 ] );
						light.shadow.normalBias = 0.1;

						break;

					case 'LightStyle_WorldSpot':

						light = new SpotLight();
						light.castShadow = attributes.castsShadows;
						light.position.set( geometry.location[ 0 ], geometry.location[ 1 ], geometry.location[ 2 ] );
						light.target.position.set( geometry.direction[ 0 ], geometry.direction[ 1 ], geometry.direction[ 2 ] );
						light.angle = geometry.spotAngleRadians;
						light.shadow.normalBias = 0.1;

						break;

					case 'LightStyle_WorldRectangular':

						light = new RectAreaLight();
						const width = Math.abs( geometry.width[ 2 ] );
						const height = Math.abs( geometry.length[ 0 ] );
						light.position.set( geometry.location[ 0 ] - ( height / 2 ), geometry.location[ 1 ], geometry.location[ 2 ] - ( width / 2 ) );
						light.height = height;
						light.width = width;
						light.lookAt( geometry.direction[ 0 ], geometry.direction[ 1 ], geometry.direction[ 2 ] );

						break;

					case 'LightStyle_WorldDirectional':

						light = new DirectionalLight();
						light.castShadow = attributes.castsShadows;
						light.position.set( geometry.location[ 0 ], geometry.location[ 1 ], geometry.location[ 2 ] );
						light.target.position.set( geometry.direction[ 0 ], geometry.direction[ 1 ], geometry.direction[ 2 ] );
						light.shadow.normalBias = 0.1;

						break;

					case 'LightStyle_WorldLinear':
						// no conversion exists, warning has already been printed to the console
						break;

					default:
						break;

				}

				if ( light ) {

					light.intensity = geometry.intensity;
					_color = geometry.diffuse;
					color = new Color( _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 );
					light.color = color;
					light.userData[ 'attributes' ] = attributes;
					light.userData[ 'objectType' ] = obj.objectType;

				}

				return light;

		}

	}
```
</details>

### `Rhino3dmLoader._initLibrary(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `jsLoader.setPath`
- `jsLoader.load`
- `binaryLoader.setPath`
- `binaryLoader.setResponseType`
- `binaryLoader.load`
- `Promise.all( [ jsContent, binaryContent ] )
				.then`
- `Rhino3dmWorker.toString`
- `[
						'/* rhino3dm.js */',
						jsContent,
						'/* worker */',
						fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
					].join`
- `fn.substring`
- `fn.indexOf`
- `fn.lastIndexOf`
- `URL.createObjectURL`

**Internal Comments:**
```
// Load rhino3dm wrapper. (x2)
// Load rhino3dm WASM binary. (x2)
//this.libraryBinary = binaryContent; (x5)
```

<details><summary>Code</summary>

```typescript
_initLibrary() {

		if ( ! this.libraryPending ) {

			// Load rhino3dm wrapper.
			const jsLoader = new FileLoader( this.manager );
			jsLoader.setPath( this.libraryPath );
			const jsContent = new Promise( ( resolve, reject ) => {

				jsLoader.load( 'rhino3dm.js', resolve, undefined, reject );

			} );

			// Load rhino3dm WASM binary.
			const binaryLoader = new FileLoader( this.manager );
			binaryLoader.setPath( this.libraryPath );
			binaryLoader.setResponseType( 'arraybuffer' );
			const binaryContent = new Promise( ( resolve, reject ) => {

				binaryLoader.load( 'rhino3dm.wasm', resolve, undefined, reject );

			} );

			this.libraryPending = Promise.all( [ jsContent, binaryContent ] )
				.then( ( [ jsContent, binaryContent ] ) => {

					//this.libraryBinary = binaryContent;
					this.libraryConfig.wasmBinary = binaryContent;

					const fn = Rhino3dmWorker.toString();

					const body = [
						'/* rhino3dm.js */',
						jsContent,
						'/* worker */',
						fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
					].join( '\n' );

					this.workerSourceURL = URL.createObjectURL( new Blob( [ body ] ) );

				} );

		}

		return this.libraryPending;

	}
```
</details>

### `Rhino3dmLoader._getWorker(taskCost: any): Promise<any>`

**Parameters:**

- **`taskCost`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `this._initLibrary().then`
- `worker.postMessage`
- `this.warnings.push`
- `console.warn`
- `worker._callbacks[ message.id ].resolve`
- `worker._callbacks[ message.id ].reject`
- `console.error`
- `this.workerPool.push`
- `this.workerPool.sort`

<details><summary>Code</summary>

```typescript
_getWorker( taskCost ) {

		return this._initLibrary().then( () => {

			if ( this.workerPool.length < this.workerLimit ) {

				const worker = new Worker( this.workerSourceURL );

				worker._callbacks = {};
				worker._taskCosts = {};
				worker._taskLoad = 0;

				worker.postMessage( {
					type: 'init',
					libraryConfig: this.libraryConfig
				} );

				worker.onmessage = e => {

					const message = e.data;

					switch ( message.type ) {

						case 'warning':
							this.warnings.push( message.data );
							console.warn( message.data );
							break;

						case 'decode':
							worker._callbacks[ message.id ].resolve( message );
							break;

						case 'error':
							worker._callbacks[ message.id ].reject( message );
							break;

						default:
							console.error( 'THREE.Rhino3dmLoader: Unexpected message, "' + message.type + '"' );

					}

				};

				this.workerPool.push( worker );

			} else {

				this.workerPool.sort( function ( a, b ) {

					return a._taskLoad > b._taskLoad ? - 1 : 1;

				} );

			}

			const worker = this.workerPool[ this.workerPool.length - 1 ];

			worker._taskLoad += taskCost;

			return worker;

		} );

	}
```
</details>

### `Rhino3dmLoader._releaseTask(worker: any, taskID: any): void`

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

### `Rhino3dmLoader.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the loader is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this.workerPool[ i ].terminate`

<details><summary>Code</summary>

```typescript
dispose() {

		for ( let i = 0; i < this.workerPool.length; ++ i ) {

			this.workerPool[ i ].terminate();

		}

		this.workerPool.length = 0;

	}
```
</details>

### `Rhino3dmWorker(): void`

**Returns:** `void`

**Calls:**

- `new Promise( function ( resolve ) {

					/* Like Basis Loader */
					RhinoModule = { wasmBinary, onRuntimeInitialized: resolve };

					rhino3dm( RhinoModule ); // eslint-disable-line no-undef

				 } ).then`
- `rhino3dm`
- `libraryPending.then`
- `decodeObjects`
- `self.postMessage`
- `rhino.File3dm.fromByteArray`
- `doc.objects`
- `objs.get`
- `extractObjectData`
- `_object.delete`
- `objects.push`
- `doc.instanceDefinitions`
- `doc.instanceDefinitions().get`
- `extractProperties`
- `idef.getObjectIds`
- `doc.materials`
- `doc.materials().get`
- `textures.push`
- `extractTextures`
- `_material.physicallyBased`
- `materials.push`
- `_material.delete`
- `doc.layers`
- `doc.layers().get`
- `layers.push`
- `_layer.delete`
- `doc.views`
- `doc.views().get`
- `views.push`
- `_view.delete`
- `doc.namedViews`
- `doc.namedViews().get`
- `namedViews.push`
- `_namedView.delete`
- `doc.groups`
- `doc.groups().get`
- `groups.push`
- `_group.delete`
- `doc.settings`
- `doc.strings`
- `strings.push`
- `doc.strings().get`
- `doc.settings().renderSettings`
- `doc.renderContent`
- `rc.get`
- `content.findChild`
- `doc.embeddedFiles`
- `doc.embeddedFiles().get`
- `doc.getEmbeddedFileAsBase64`
- `doc.delete`
- `m.getTexture`
- `textureType.substring`
- `extractTextureData`
- `_texture.delete`
- `d.getEmbeddedFileAsBase64`
- `t.uvwTransform.toFloatArray`
- `object.geometry`
- `object.attributes`
- `curveToPoints`
- `position.array.push`
- `_attributes.drawColor`
- `_geometry.toThreejsJSON`
- `_geometry.faces`
- `faces.get`
- `face.getMesh`
- `mesh.append`
- `_mesh.delete`
- `face.delete`
- `mesh.faces`
- `mesh.compact`
- `mesh.toThreejsJSON`
- `faces.delete`
- `mesh.delete`
- `_geometry.getMesh`
- `_geometry.xform.toFloatArray`
- `_geometry.subdivide`
- `rhino.Mesh.createFromSubDControlNet`
- `_attributes.getGroupList`
- `_attributes.getUserStrings`
- `_geometry.getUserStrings`
- `_attributes.decals`
- `objectType.substring`
- `value.hasOwnProperty`
- `rc.push`
- `curve.point`
- `curve.segmentCurve`
- `rc.concat`
- `segment.delete`
- `Math.floor`
- `curve.tryGetPolyline`
- `pLine.get`
- `pLine.delete`
- `ts.push`
- `curve.tangentAt`
- `ts.slice`
- `Math.sqrt`
- `Math.acos`
- `Math.max`
- `Math.min`
- `ts.map`
- `curve.pointAt`

**Internal Comments:**
```
/* Like Basis Loader */ (x3)
//Handle objects (x2)
// Handle instance definitions
// console.log( `Instance Definitions Count: ${doc.instanceDefinitions().count()}` );
// Handle materials (x2)
// rhino.TextureType.Bitmap, (x3)
// Handle layers
// Handle views
// Handle named views
// Handle groups
// Handle settings (x2)
//TODO: Handle other document stuff like dimstyles, instance definitions, bitmaps etc. (x2)
// Handle dimstyles (x2)
// console.log( `Dimstyle Count: ${doc.dimstyles().count()}` ); (x2)
// Handle bitmaps (x2)
// console.log( `Bitmap Count: ${doc.bitmaps().count()}` ); (x2)
// Handle strings (x2)
// console.log( `Document Strings Count: ${doc.strings().count()}` ); (x2)
// Note: doc.strings().documentUserTextCount() counts any doc.strings defined in a section (x2)
// console.log( `Document User Text Count: ${doc.strings().documentUserTextCount()}` ); (x2)
// Handle Render Environments for Material Environment (x2)
// get the id of the active render environment skylight, which we'll use for environment texture (x2)
// there could be multiple render environments in a 3dm file
// Handle Render Settings (x2)
// skip instance definition objects
//if( _attributes.isInstanceDefinitionObject ) { continue; }
// TODO: handle other geometry types
// TODO: precalculate resulting vertices and faces and warn on excessive results (x4)
/*
				case rhino.ObjectType.Annotation:
				case rhino.ObjectType.Hatch:
				case rhino.ObjectType.ClipPlane:
				*/
// Duplicated from THREE.Vector3 (x2)
// How to pass imports to worker? (x2)
```

<details><summary>Code</summary>

```typescript
function Rhino3dmWorker() {

	let libraryPending;
	let libraryConfig;
	let rhino;
	let taskID;

	onmessage = function ( e ) {

		const message = e.data;

		switch ( message.type ) {

			case 'init':

				libraryConfig = message.libraryConfig;
				const wasmBinary = libraryConfig.wasmBinary;
				let RhinoModule;
				libraryPending = new Promise( function ( resolve ) {

					/* Like Basis Loader */
					RhinoModule = { wasmBinary, onRuntimeInitialized: resolve };

					rhino3dm( RhinoModule ); // eslint-disable-line no-undef

				 } ).then( () => {

					rhino = RhinoModule;

				 } );

				break;

			case 'decode':

				taskID = message.id;
				const buffer = message.buffer;
				libraryPending.then( () => {

					try {

						const data = decodeObjects( rhino, buffer );
						self.postMessage( { type: 'decode', id: message.id, data } );

					} catch ( error ) {

						self.postMessage( { type: 'error', id: message.id, error } );

					}

				} );

				break;

		}

	};

	function decodeObjects( rhino, buffer ) {

		const arr = new Uint8Array( buffer );
		const doc = rhino.File3dm.fromByteArray( arr );

		const objects = [];
		const materials = [];
		const layers = [];
		const views = [];
		const namedViews = [];
		const groups = [];
		const strings = [];

		//Handle objects

		const objs = doc.objects();
		const cnt = objs.count;

		for ( let i = 0; i < cnt; i ++ ) {

			const _object = objs.get( i );

			const object = extractObjectData( _object, doc );

			_object.delete();

			if ( object ) {

				objects.push( object );

			}

		}

		// Handle instance definitions
		// console.log( `Instance Definitions Count: ${doc.instanceDefinitions().count()}` );

		for ( let i = 0; i < doc.instanceDefinitions().count; i ++ ) {

			const idef = doc.instanceDefinitions().get( i );
			const idefAttributes = extractProperties( idef );
			idefAttributes.objectIds = idef.getObjectIds();

			objects.push( { geometry: null, attributes: idefAttributes, objectType: 'InstanceDefinition' } );

		}

		// Handle materials

		const textureTypes = [
			// rhino.TextureType.Bitmap,
			rhino.TextureType.Diffuse,
			rhino.TextureType.Bump,
			rhino.TextureType.Transparency,
			rhino.TextureType.Opacity,
			rhino.TextureType.Emap
		];

		const pbrTextureTypes = [
			rhino.TextureType.PBR_BaseColor,
			rhino.TextureType.PBR_Subsurface,
			rhino.TextureType.PBR_SubsurfaceScattering,
			rhino.TextureType.PBR_SubsurfaceScatteringRadius,
			rhino.TextureType.PBR_Metallic,
			rhino.TextureType.PBR_Specular,
			rhino.TextureType.PBR_SpecularTint,
			rhino.TextureType.PBR_Roughness,
			rhino.TextureType.PBR_Anisotropic,
			rhino.TextureType.PBR_Anisotropic_Rotation,
			rhino.TextureType.PBR_Sheen,
			rhino.TextureType.PBR_SheenTint,
			rhino.TextureType.PBR_Clearcoat,
			rhino.TextureType.PBR_ClearcoatBump,
			rhino.TextureType.PBR_ClearcoatRoughness,
			rhino.TextureType.PBR_OpacityIor,
			rhino.TextureType.PBR_OpacityRoughness,
			rhino.TextureType.PBR_Emission,
			rhino.TextureType.PBR_AmbientOcclusion,
			rhino.TextureType.PBR_Displacement
		];

		for ( let i = 0; i < doc.materials().count; i ++ ) {

			const _material = doc.materials().get( i );

			const material = extractProperties( _material );

			const textures = [];

			textures.push( ...extractTextures( _material, textureTypes, doc ) );

			material.pbrSupported = _material.physicallyBased().supported;

			if ( material.pbrSupported ) {

				textures.push( ...extractTextures( _material, pbrTextureTypes, doc ) );
				material.pbr = extractProperties( _material.physicallyBased() );

			}

			material.textures = textures;

			materials.push( material );

			_material.delete();

		}

		// Handle layers

		for ( let i = 0; i < doc.layers().count; i ++ ) {

			const _layer = doc.layers().get( i );
			const layer = extractProperties( _layer );

			layers.push( layer );

			_layer.delete();

		}

		// Handle views

		for ( let i = 0; i < doc.views().count; i ++ ) {

			const _view = doc.views().get( i );
			const view = extractProperties( _view );

			views.push( view );

			_view.delete();

		}

		// Handle named views

		for ( let i = 0; i < doc.namedViews().count; i ++ ) {

			const _namedView = doc.namedViews().get( i );
			const namedView = extractProperties( _namedView );

			namedViews.push( namedView );

			_namedView.delete();

		}

		// Handle groups

		for ( let i = 0; i < doc.groups().count; i ++ ) {

			const _group = doc.groups().get( i );
			const group = extractProperties( _group );

			groups.push( group );

			_group.delete();

		}

		// Handle settings

		const settings = extractProperties( doc.settings() );

		//TODO: Handle other document stuff like dimstyles, instance definitions, bitmaps etc.

		// Handle dimstyles
		// console.log( `Dimstyle Count: ${doc.dimstyles().count()}` );

		// Handle bitmaps
		// console.log( `Bitmap Count: ${doc.bitmaps().count()}` );

		// Handle strings
		// console.log( `Document Strings Count: ${doc.strings().count()}` );
		// Note: doc.strings().documentUserTextCount() counts any doc.strings defined in a section
		// console.log( `Document User Text Count: ${doc.strings().documentUserTextCount()}` );

		const strings_count = doc.strings().count;

		for ( let i = 0; i < strings_count; i ++ ) {

			strings.push( doc.strings().get( i ) );

		}

		// Handle Render Environments for Material Environment

		// get the id of the active render environment skylight, which we'll use for environment texture
		const reflectionId = doc.settings().renderSettings().renderEnvironments.reflectionId;

		const rc = doc.renderContent();

		let renderEnvironment = null;

		for ( let i = 0; i < rc.count; i ++ ) {

			const content = rc.get( i );

			switch ( content.kind ) {

				case 'environment':

					const id = content.id;

					// there could be multiple render environments in a 3dm file
					if ( id !== reflectionId ) break;

					const renderTexture = content.findChild( 'texture' );
					const fileName = renderTexture.fileName;

					for ( let j = 0; j < doc.embeddedFiles().count; j ++ ) {

						const _fileName = doc.embeddedFiles().get( j ).fileName;

						if ( fileName === _fileName ) {

							const background = doc.getEmbeddedFileAsBase64( fileName );
							const backgroundImage = 'data:image/png;base64,' + background;
							renderEnvironment = { type: 'renderEnvironment', image: backgroundImage, name: fileName };

						}

					}

					break;

			}

		}

		// Handle Render Settings

		const renderSettings = {
			ambientLight: doc.settings().renderSettings().ambientLight,
			backgroundColorTop: doc.settings().renderSettings().backgroundColorTop,
			backgroundColorBottom: doc.settings().renderSettings().backgroundColorBottom,
			useHiddenLights: doc.settings().renderSettings().useHiddenLights,
			depthCue: doc.settings().renderSettings().depthCue,
			flatShade: doc.settings().renderSettings().flatShade,
			renderBackFaces: doc.settings().renderSettings().renderBackFaces,
			renderPoints: doc.settings().renderSettings().renderPoints,
			renderCurves: doc.settings().renderSettings().renderCurves,
			renderIsoParams: doc.settings().renderSettings().renderIsoParams,
			renderMeshEdges: doc.settings().renderSettings().renderMeshEdges,
			renderAnnotations: doc.settings().renderSettings().renderAnnotations,
			useViewportSize: doc.settings().renderSettings().useViewportSize,
			scaleBackgroundToFit: doc.settings().renderSettings().scaleBackgroundToFit,
			transparentBackground: doc.settings().renderSettings().transparentBackground,
			imageDpi: doc.settings().renderSettings().imageDpi,
			shadowMapLevel: doc.settings().renderSettings().shadowMapLevel,
			namedView: doc.settings().renderSettings().namedView,
			snapShot: doc.settings().renderSettings().snapShot,
			specificViewport: doc.settings().renderSettings().specificViewport,
			groundPlane: extractProperties( doc.settings().renderSettings().groundPlane ),
			safeFrame: extractProperties( doc.settings().renderSettings().safeFrame ),
			dithering: extractProperties( doc.settings().renderSettings().dithering ),
			skylight: extractProperties( doc.settings().renderSettings().skylight ),
			linearWorkflow: extractProperties( doc.settings().renderSettings().linearWorkflow ),
			renderChannels: extractProperties( doc.settings().renderSettings().renderChannels ),
			sun: extractProperties( doc.settings().renderSettings().sun ),
			renderEnvironments: extractProperties( doc.settings().renderSettings().renderEnvironments ),
			postEffects: extractProperties( doc.settings().renderSettings().postEffects ),

		};

		doc.delete();

		return { objects, materials, layers, views, namedViews, groups, strings, settings, renderSettings, renderEnvironment };

	}

	function extractTextures( m, tTypes, d ) {

		const textures = [];

		for ( let i = 0; i < tTypes.length; i ++ ) {

			const _texture = m.getTexture( tTypes[ i ] );
			if ( _texture ) {

				let textureType = tTypes[ i ].constructor.name;
				textureType = textureType.substring( 12, textureType.length );
				const texture = extractTextureData( _texture, textureType, d );
				textures.push( texture );
				_texture.delete();

			}

		}

		return textures;

	}

	function extractTextureData( t, tType, d ) {

		const texture = { type: tType };

		const image = d.getEmbeddedFileAsBase64( t.fileName );

		texture.wrapU = t.wrapU;
		texture.wrapV = t.wrapV;
		texture.wrapW = t.wrapW;
		const uvw = t.uvwTransform.toFloatArray( true );

		texture.repeat = [ uvw[ 0 ], uvw[ 5 ] ];

		if ( image ) {

			texture.image = 'data:image/png;base64,' + image;

		} else {

			self.postMessage( { type: 'warning', id: taskID, data: {
				message: `THREE.3DMLoader: Image for ${tType} texture not embedded in file.`,
				type: 'missing resource'
			}

			} );

			texture.image = null;

		}

		return texture;

	}

	function extractObjectData( object, doc ) {

		const _geometry = object.geometry();
		const _attributes = object.attributes();
		let objectType = _geometry.objectType;
		let geometry, attributes, position, data, mesh;

		// skip instance definition objects
		//if( _attributes.isInstanceDefinitionObject ) { continue; }

		// TODO: handle other geometry types
		switch ( objectType ) {

			case rhino.ObjectType.Curve:

				const pts = curveToPoints( _geometry, 100 );

				position = {};
				attributes = {};
				data = {};

				position.itemSize = 3;
				position.type = 'Float32Array';
				position.array = [];

				for ( let j = 0; j < pts.length; j ++ ) {

					position.array.push( pts[ j ][ 0 ] );
					position.array.push( pts[ j ][ 1 ] );
					position.array.push( pts[ j ][ 2 ] );

				}

				attributes.position = position;
				data.attributes = attributes;

				geometry = { data };

				break;

			case rhino.ObjectType.Point:

				const pt = _geometry.location;

				position = {};
				const color = {};
				attributes = {};
				data = {};

				position.itemSize = 3;
				position.type = 'Float32Array';
				position.array = [ pt[ 0 ], pt[ 1 ], pt[ 2 ] ];

				const _color = _attributes.drawColor( doc );

				color.itemSize = 3;
				color.type = 'Float32Array';
				color.array = [ _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 ];

				attributes.position = position;
				attributes.color = color;
				data.attributes = attributes;

				geometry = { data };

				break;

			case rhino.ObjectType.PointSet:
			case rhino.ObjectType.Mesh:

				geometry = _geometry.toThreejsJSON();

				break;

			case rhino.ObjectType.Brep:

				const faces = _geometry.faces();
				mesh = new rhino.Mesh();

				for ( let faceIndex = 0; faceIndex < faces.count; faceIndex ++ ) {

					const face = faces.get( faceIndex );
					const _mesh = face.getMesh( rhino.MeshType.Any );

					if ( _mesh ) {

						mesh.append( _mesh );
						_mesh.delete();

					}

					face.delete();

				}

				if ( mesh.faces().count > 0 ) {

					mesh.compact();
					geometry = mesh.toThreejsJSON();
					faces.delete();

				}

				mesh.delete();

				break;

			case rhino.ObjectType.Extrusion:

				mesh = _geometry.getMesh( rhino.MeshType.Any );

				if ( mesh ) {

					geometry = mesh.toThreejsJSON();
					mesh.delete();

				}

				break;

			case rhino.ObjectType.TextDot:

				geometry = extractProperties( _geometry );

				break;

			case rhino.ObjectType.Light:

				geometry = extractProperties( _geometry );

				if ( geometry.lightStyle.name === 'LightStyle_WorldLinear' ) {

					self.postMessage( { type: 'warning', id: taskID, data: {
						message: `THREE.3DMLoader: No conversion exists for ${objectType.constructor.name} ${geometry.lightStyle.name}`,
						type: 'no conversion',
						guid: _attributes.id
					}

					} );

				}

				break;

			case rhino.ObjectType.InstanceReference:

				geometry = extractProperties( _geometry );
				geometry.xform = extractProperties( _geometry.xform );
				geometry.xform.array = _geometry.xform.toFloatArray( true );

				break;

			case rhino.ObjectType.SubD:

				// TODO: precalculate resulting vertices and faces and warn on excessive results
				_geometry.subdivide( 3 );
				mesh = rhino.Mesh.createFromSubDControlNet( _geometry, false );
				if ( mesh ) {

					geometry = mesh.toThreejsJSON();
					mesh.delete();

				}

				break;

				/*
				case rhino.ObjectType.Annotation:
				case rhino.ObjectType.Hatch:
				case rhino.ObjectType.ClipPlane:
				*/

			default:

				self.postMessage( { type: 'warning', id: taskID, data: {
					message: `THREE.3DMLoader: Conversion not implemented for ${objectType.constructor.name}`,
					type: 'not implemented',
					guid: _attributes.id
				}

				} );

				break;

		}

		if ( geometry ) {

			attributes = extractProperties( _attributes );
			attributes.geometry = extractProperties( _geometry );

			if ( _attributes.groupCount > 0 ) {

				attributes.groupIds = _attributes.getGroupList();

			}

			if ( _attributes.userStringCount > 0 ) {

				attributes.userStrings = _attributes.getUserStrings();

			}

			if ( _geometry.userStringCount > 0 ) {

				attributes.geometry.userStrings = _geometry.getUserStrings();

			}

			if ( _attributes.decals().count > 0 ) {

				self.postMessage( { type: 'warning', id: taskID, data: {
					message: 'THREE.3DMLoader: No conversion exists for the decals associated with this object.',
					type: 'no conversion',
					guid: _attributes.id
				}

				} );

			}

			attributes.drawColor = _attributes.drawColor( doc );

			objectType = objectType.constructor.name;
			objectType = objectType.substring( 11, objectType.length );

			return { geometry, attributes, objectType };

		} else {

			self.postMessage( { type: 'warning', id: taskID, data: {
				message: `THREE.3DMLoader: ${objectType.constructor.name} has no associated mesh geometry.`,
				type: 'missing mesh',
				guid: _attributes.id
			}

			} );

		}

	}

	function extractProperties( object ) {

		const result = {};

		for ( const property in object ) {

			const value = object[ property ];

			if ( typeof value !== 'function' ) {

				if ( typeof value === 'object' && value !== null && value.hasOwnProperty( 'constructor' ) ) {

					result[ property ] = { name: value.constructor.name, value: value.value };

				} else if ( typeof value === 'object' && value !== null ) {

					result[ property ] = extractProperties( value );

				} else {

					result[ property ] = value;

				}

			} else {

				// these are functions that could be called to extract more data.
				//console.log( `${property}: ${object[ property ].constructor.name}` );

			}

		}

		return result;

	}

	function curveToPoints( curve, pointLimit ) {

		let pointCount = pointLimit;
		let rc = [];
		const ts = [];

		if ( curve instanceof rhino.LineCurve ) {

			return [ curve.pointAtStart, curve.pointAtEnd ];

		}

		if ( curve instanceof rhino.PolylineCurve ) {

			pointCount = curve.pointCount;
			for ( let i = 0; i < pointCount; i ++ ) {

				rc.push( curve.point( i ) );

			}

			return rc;

		}

		if ( curve instanceof rhino.PolyCurve ) {

			const segmentCount = curve.segmentCount;

			for ( let i = 0; i < segmentCount; i ++ ) {

				const segment = curve.segmentCurve( i );
				const segmentArray = curveToPoints( segment, pointCount );
				rc = rc.concat( segmentArray );
				segment.delete();

			}

			return rc;

		}

		if ( curve instanceof rhino.ArcCurve ) {

			pointCount = Math.floor( curve.angleDegrees / 5 );
			pointCount = pointCount < 2 ? 2 : pointCount;
			// alternative to this hardcoded version: https://stackoverflow.com/a/18499923/2179399

		}

		if ( curve instanceof rhino.NurbsCurve && curve.degree === 1 ) {

			const pLine = curve.tryGetPolyline();

			for ( let i = 0; i < pLine.count; i ++ ) {

				rc.push( pLine.get( i ) );

			}

			pLine.delete();

			return rc;

		}

		const domain = curve.domain;
		const divisions = pointCount - 1.0;

		for ( let j = 0; j < pointCount; j ++ ) {

			const t = domain[ 0 ] + ( j / divisions ) * ( domain[ 1 ] - domain[ 0 ] );

			if ( t === domain[ 0 ] || t === domain[ 1 ] ) {

				ts.push( t );
				continue;

			}

			const tan = curve.tangentAt( t );
			const prevTan = curve.tangentAt( ts.slice( - 1 )[ 0 ] );

			// Duplicated from THREE.Vector3
			// How to pass imports to worker?

			const tS = tan[ 0 ] * tan[ 0 ] + tan[ 1 ] * tan[ 1 ] + tan[ 2 ] * tan[ 2 ];
			const ptS = prevTan[ 0 ] * prevTan[ 0 ] + prevTan[ 1 ] * prevTan[ 1 ] + prevTan[ 2 ] * prevTan[ 2 ];

			const denominator = Math.sqrt( tS * ptS );

			let angle;

			if ( denominator === 0 ) {

				angle = Math.PI / 2;

			} else {

				const theta = ( tan.x * prevTan.x + tan.y * prevTan.y + tan.z * prevTan.z ) / denominator;
				angle = Math.acos( Math.max( - 1, Math.min( 1, theta ) ) );

			}

			if ( angle < 0.1 ) continue;

			ts.push( t );

		}

		rc = ts.map( t => curve.pointAt( t ) );
		return rc;

	}

}
```
</details>

### `decodeObjects(rhino: any, buffer: any): { objects: { geometry: any; attributes: {}; objectType: any; }[]; materials: {}[]; layers: {}[]; views: {}[]; namedViews: {}[]; groups: {}[]; strings: any[]; settings: {}; renderSettings: { ambientLight: any; backgroundColorTop: any; ... 26 more ...; postEffects: {}; }; renderEnvironment: { ...; }; }`

**Parameters:**

- **`rhino`** `any`
- **`buffer`** `any`

**Returns:** `{ objects: { geometry: any; attributes: {}; objectType: any; }[]; materials: {}[]; layers: {}[]; views: {}[]; namedViews: {}[]; groups: {}[]; strings: any[]; settings: {}; renderSettings: { ambientLight: any; backgroundColorTop: any; ... 26 more ...; postEffects: {}; }; renderEnvironment: { ...; }; }`

**Calls:**

- `rhino.File3dm.fromByteArray`
- `doc.objects`
- `objs.get`
- `extractObjectData`
- `_object.delete`
- `objects.push`
- `doc.instanceDefinitions`
- `doc.instanceDefinitions().get`
- `extractProperties`
- `idef.getObjectIds`
- `doc.materials`
- `doc.materials().get`
- `textures.push`
- `extractTextures`
- `_material.physicallyBased`
- `materials.push`
- `_material.delete`
- `doc.layers`
- `doc.layers().get`
- `layers.push`
- `_layer.delete`
- `doc.views`
- `doc.views().get`
- `views.push`
- `_view.delete`
- `doc.namedViews`
- `doc.namedViews().get`
- `namedViews.push`
- `_namedView.delete`
- `doc.groups`
- `doc.groups().get`
- `groups.push`
- `_group.delete`
- `doc.settings`
- `doc.strings`
- `strings.push`
- `doc.strings().get`
- `doc.settings().renderSettings`
- `doc.renderContent`
- `rc.get`
- `content.findChild`
- `doc.embeddedFiles`
- `doc.embeddedFiles().get`
- `doc.getEmbeddedFileAsBase64`
- `doc.delete`

**Internal Comments:**
```
//Handle objects (x2)
// Handle instance definitions
// console.log( `Instance Definitions Count: ${doc.instanceDefinitions().count()}` );
// Handle materials (x2)
// rhino.TextureType.Bitmap, (x3)
// Handle layers
// Handle views
// Handle named views
// Handle groups
// Handle settings (x2)
//TODO: Handle other document stuff like dimstyles, instance definitions, bitmaps etc. (x2)
// Handle dimstyles (x2)
// console.log( `Dimstyle Count: ${doc.dimstyles().count()}` ); (x2)
// Handle bitmaps (x2)
// console.log( `Bitmap Count: ${doc.bitmaps().count()}` ); (x2)
// Handle strings (x2)
// console.log( `Document Strings Count: ${doc.strings().count()}` ); (x2)
// Note: doc.strings().documentUserTextCount() counts any doc.strings defined in a section (x2)
// console.log( `Document User Text Count: ${doc.strings().documentUserTextCount()}` ); (x2)
// Handle Render Environments for Material Environment (x2)
// get the id of the active render environment skylight, which we'll use for environment texture (x2)
// there could be multiple render environments in a 3dm file
// Handle Render Settings (x2)
```

<details><summary>Code</summary>

```typescript
function decodeObjects( rhino, buffer ) {

		const arr = new Uint8Array( buffer );
		const doc = rhino.File3dm.fromByteArray( arr );

		const objects = [];
		const materials = [];
		const layers = [];
		const views = [];
		const namedViews = [];
		const groups = [];
		const strings = [];

		//Handle objects

		const objs = doc.objects();
		const cnt = objs.count;

		for ( let i = 0; i < cnt; i ++ ) {

			const _object = objs.get( i );

			const object = extractObjectData( _object, doc );

			_object.delete();

			if ( object ) {

				objects.push( object );

			}

		}

		// Handle instance definitions
		// console.log( `Instance Definitions Count: ${doc.instanceDefinitions().count()}` );

		for ( let i = 0; i < doc.instanceDefinitions().count; i ++ ) {

			const idef = doc.instanceDefinitions().get( i );
			const idefAttributes = extractProperties( idef );
			idefAttributes.objectIds = idef.getObjectIds();

			objects.push( { geometry: null, attributes: idefAttributes, objectType: 'InstanceDefinition' } );

		}

		// Handle materials

		const textureTypes = [
			// rhino.TextureType.Bitmap,
			rhino.TextureType.Diffuse,
			rhino.TextureType.Bump,
			rhino.TextureType.Transparency,
			rhino.TextureType.Opacity,
			rhino.TextureType.Emap
		];

		const pbrTextureTypes = [
			rhino.TextureType.PBR_BaseColor,
			rhino.TextureType.PBR_Subsurface,
			rhino.TextureType.PBR_SubsurfaceScattering,
			rhino.TextureType.PBR_SubsurfaceScatteringRadius,
			rhino.TextureType.PBR_Metallic,
			rhino.TextureType.PBR_Specular,
			rhino.TextureType.PBR_SpecularTint,
			rhino.TextureType.PBR_Roughness,
			rhino.TextureType.PBR_Anisotropic,
			rhino.TextureType.PBR_Anisotropic_Rotation,
			rhino.TextureType.PBR_Sheen,
			rhino.TextureType.PBR_SheenTint,
			rhino.TextureType.PBR_Clearcoat,
			rhino.TextureType.PBR_ClearcoatBump,
			rhino.TextureType.PBR_ClearcoatRoughness,
			rhino.TextureType.PBR_OpacityIor,
			rhino.TextureType.PBR_OpacityRoughness,
			rhino.TextureType.PBR_Emission,
			rhino.TextureType.PBR_AmbientOcclusion,
			rhino.TextureType.PBR_Displacement
		];

		for ( let i = 0; i < doc.materials().count; i ++ ) {

			const _material = doc.materials().get( i );

			const material = extractProperties( _material );

			const textures = [];

			textures.push( ...extractTextures( _material, textureTypes, doc ) );

			material.pbrSupported = _material.physicallyBased().supported;

			if ( material.pbrSupported ) {

				textures.push( ...extractTextures( _material, pbrTextureTypes, doc ) );
				material.pbr = extractProperties( _material.physicallyBased() );

			}

			material.textures = textures;

			materials.push( material );

			_material.delete();

		}

		// Handle layers

		for ( let i = 0; i < doc.layers().count; i ++ ) {

			const _layer = doc.layers().get( i );
			const layer = extractProperties( _layer );

			layers.push( layer );

			_layer.delete();

		}

		// Handle views

		for ( let i = 0; i < doc.views().count; i ++ ) {

			const _view = doc.views().get( i );
			const view = extractProperties( _view );

			views.push( view );

			_view.delete();

		}

		// Handle named views

		for ( let i = 0; i < doc.namedViews().count; i ++ ) {

			const _namedView = doc.namedViews().get( i );
			const namedView = extractProperties( _namedView );

			namedViews.push( namedView );

			_namedView.delete();

		}

		// Handle groups

		for ( let i = 0; i < doc.groups().count; i ++ ) {

			const _group = doc.groups().get( i );
			const group = extractProperties( _group );

			groups.push( group );

			_group.delete();

		}

		// Handle settings

		const settings = extractProperties( doc.settings() );

		//TODO: Handle other document stuff like dimstyles, instance definitions, bitmaps etc.

		// Handle dimstyles
		// console.log( `Dimstyle Count: ${doc.dimstyles().count()}` );

		// Handle bitmaps
		// console.log( `Bitmap Count: ${doc.bitmaps().count()}` );

		// Handle strings
		// console.log( `Document Strings Count: ${doc.strings().count()}` );
		// Note: doc.strings().documentUserTextCount() counts any doc.strings defined in a section
		// console.log( `Document User Text Count: ${doc.strings().documentUserTextCount()}` );

		const strings_count = doc.strings().count;

		for ( let i = 0; i < strings_count; i ++ ) {

			strings.push( doc.strings().get( i ) );

		}

		// Handle Render Environments for Material Environment

		// get the id of the active render environment skylight, which we'll use for environment texture
		const reflectionId = doc.settings().renderSettings().renderEnvironments.reflectionId;

		const rc = doc.renderContent();

		let renderEnvironment = null;

		for ( let i = 0; i < rc.count; i ++ ) {

			const content = rc.get( i );

			switch ( content.kind ) {

				case 'environment':

					const id = content.id;

					// there could be multiple render environments in a 3dm file
					if ( id !== reflectionId ) break;

					const renderTexture = content.findChild( 'texture' );
					const fileName = renderTexture.fileName;

					for ( let j = 0; j < doc.embeddedFiles().count; j ++ ) {

						const _fileName = doc.embeddedFiles().get( j ).fileName;

						if ( fileName === _fileName ) {

							const background = doc.getEmbeddedFileAsBase64( fileName );
							const backgroundImage = 'data:image/png;base64,' + background;
							renderEnvironment = { type: 'renderEnvironment', image: backgroundImage, name: fileName };

						}

					}

					break;

			}

		}

		// Handle Render Settings

		const renderSettings = {
			ambientLight: doc.settings().renderSettings().ambientLight,
			backgroundColorTop: doc.settings().renderSettings().backgroundColorTop,
			backgroundColorBottom: doc.settings().renderSettings().backgroundColorBottom,
			useHiddenLights: doc.settings().renderSettings().useHiddenLights,
			depthCue: doc.settings().renderSettings().depthCue,
			flatShade: doc.settings().renderSettings().flatShade,
			renderBackFaces: doc.settings().renderSettings().renderBackFaces,
			renderPoints: doc.settings().renderSettings().renderPoints,
			renderCurves: doc.settings().renderSettings().renderCurves,
			renderIsoParams: doc.settings().renderSettings().renderIsoParams,
			renderMeshEdges: doc.settings().renderSettings().renderMeshEdges,
			renderAnnotations: doc.settings().renderSettings().renderAnnotations,
			useViewportSize: doc.settings().renderSettings().useViewportSize,
			scaleBackgroundToFit: doc.settings().renderSettings().scaleBackgroundToFit,
			transparentBackground: doc.settings().renderSettings().transparentBackground,
			imageDpi: doc.settings().renderSettings().imageDpi,
			shadowMapLevel: doc.settings().renderSettings().shadowMapLevel,
			namedView: doc.settings().renderSettings().namedView,
			snapShot: doc.settings().renderSettings().snapShot,
			specificViewport: doc.settings().renderSettings().specificViewport,
			groundPlane: extractProperties( doc.settings().renderSettings().groundPlane ),
			safeFrame: extractProperties( doc.settings().renderSettings().safeFrame ),
			dithering: extractProperties( doc.settings().renderSettings().dithering ),
			skylight: extractProperties( doc.settings().renderSettings().skylight ),
			linearWorkflow: extractProperties( doc.settings().renderSettings().linearWorkflow ),
			renderChannels: extractProperties( doc.settings().renderSettings().renderChannels ),
			sun: extractProperties( doc.settings().renderSettings().sun ),
			renderEnvironments: extractProperties( doc.settings().renderSettings().renderEnvironments ),
			postEffects: extractProperties( doc.settings().renderSettings().postEffects ),

		};

		doc.delete();

		return { objects, materials, layers, views, namedViews, groups, strings, settings, renderSettings, renderEnvironment };

	}
```
</details>

### `extractTextures(m: any, tTypes: any, d: any): { type: any; }[]`

**Parameters:**

- **`m`** `any`
- **`tTypes`** `any`
- **`d`** `any`

**Returns:** `{ type: any; }[]`

**Calls:**

- `m.getTexture`
- `textureType.substring`
- `extractTextureData`
- `textures.push`
- `_texture.delete`

<details><summary>Code</summary>

```typescript
function extractTextures( m, tTypes, d ) {

		const textures = [];

		for ( let i = 0; i < tTypes.length; i ++ ) {

			const _texture = m.getTexture( tTypes[ i ] );
			if ( _texture ) {

				let textureType = tTypes[ i ].constructor.name;
				textureType = textureType.substring( 12, textureType.length );
				const texture = extractTextureData( _texture, textureType, d );
				textures.push( texture );
				_texture.delete();

			}

		}

		return textures;

	}
```
</details>

### `extractTextureData(t: any, tType: any, d: any): { type: any; }`

**Parameters:**

- **`t`** `any`
- **`tType`** `any`
- **`d`** `any`

**Returns:** `{ type: any; }`

**Calls:**

- `d.getEmbeddedFileAsBase64`
- `t.uvwTransform.toFloatArray`
- `self.postMessage`

<details><summary>Code</summary>

```typescript
function extractTextureData( t, tType, d ) {

		const texture = { type: tType };

		const image = d.getEmbeddedFileAsBase64( t.fileName );

		texture.wrapU = t.wrapU;
		texture.wrapV = t.wrapV;
		texture.wrapW = t.wrapW;
		const uvw = t.uvwTransform.toFloatArray( true );

		texture.repeat = [ uvw[ 0 ], uvw[ 5 ] ];

		if ( image ) {

			texture.image = 'data:image/png;base64,' + image;

		} else {

			self.postMessage( { type: 'warning', id: taskID, data: {
				message: `THREE.3DMLoader: Image for ${tType} texture not embedded in file.`,
				type: 'missing resource'
			}

			} );

			texture.image = null;

		}

		return texture;

	}
```
</details>

### `extractObjectData(object: any, doc: any): { geometry: any; attributes: {}; objectType: any; }`

**Parameters:**

- **`object`** `any`
- **`doc`** `any`

**Returns:** `{ geometry: any; attributes: {}; objectType: any; }`

**Calls:**

- `object.geometry`
- `object.attributes`
- `curveToPoints`
- `position.array.push`
- `_attributes.drawColor`
- `_geometry.toThreejsJSON`
- `_geometry.faces`
- `faces.get`
- `face.getMesh`
- `mesh.append`
- `_mesh.delete`
- `face.delete`
- `mesh.faces`
- `mesh.compact`
- `mesh.toThreejsJSON`
- `faces.delete`
- `mesh.delete`
- `_geometry.getMesh`
- `extractProperties`
- `self.postMessage`
- `_geometry.xform.toFloatArray`
- `_geometry.subdivide`
- `rhino.Mesh.createFromSubDControlNet`
- `_attributes.getGroupList`
- `_attributes.getUserStrings`
- `_geometry.getUserStrings`
- `_attributes.decals`
- `objectType.substring`

**Internal Comments:**
```
// skip instance definition objects
//if( _attributes.isInstanceDefinitionObject ) { continue; }
// TODO: handle other geometry types
// TODO: precalculate resulting vertices and faces and warn on excessive results (x4)
/*
				case rhino.ObjectType.Annotation:
				case rhino.ObjectType.Hatch:
				case rhino.ObjectType.ClipPlane:
				*/
```

<details><summary>Code</summary>

```typescript
function extractObjectData( object, doc ) {

		const _geometry = object.geometry();
		const _attributes = object.attributes();
		let objectType = _geometry.objectType;
		let geometry, attributes, position, data, mesh;

		// skip instance definition objects
		//if( _attributes.isInstanceDefinitionObject ) { continue; }

		// TODO: handle other geometry types
		switch ( objectType ) {

			case rhino.ObjectType.Curve:

				const pts = curveToPoints( _geometry, 100 );

				position = {};
				attributes = {};
				data = {};

				position.itemSize = 3;
				position.type = 'Float32Array';
				position.array = [];

				for ( let j = 0; j < pts.length; j ++ ) {

					position.array.push( pts[ j ][ 0 ] );
					position.array.push( pts[ j ][ 1 ] );
					position.array.push( pts[ j ][ 2 ] );

				}

				attributes.position = position;
				data.attributes = attributes;

				geometry = { data };

				break;

			case rhino.ObjectType.Point:

				const pt = _geometry.location;

				position = {};
				const color = {};
				attributes = {};
				data = {};

				position.itemSize = 3;
				position.type = 'Float32Array';
				position.array = [ pt[ 0 ], pt[ 1 ], pt[ 2 ] ];

				const _color = _attributes.drawColor( doc );

				color.itemSize = 3;
				color.type = 'Float32Array';
				color.array = [ _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 ];

				attributes.position = position;
				attributes.color = color;
				data.attributes = attributes;

				geometry = { data };

				break;

			case rhino.ObjectType.PointSet:
			case rhino.ObjectType.Mesh:

				geometry = _geometry.toThreejsJSON();

				break;

			case rhino.ObjectType.Brep:

				const faces = _geometry.faces();
				mesh = new rhino.Mesh();

				for ( let faceIndex = 0; faceIndex < faces.count; faceIndex ++ ) {

					const face = faces.get( faceIndex );
					const _mesh = face.getMesh( rhino.MeshType.Any );

					if ( _mesh ) {

						mesh.append( _mesh );
						_mesh.delete();

					}

					face.delete();

				}

				if ( mesh.faces().count > 0 ) {

					mesh.compact();
					geometry = mesh.toThreejsJSON();
					faces.delete();

				}

				mesh.delete();

				break;

			case rhino.ObjectType.Extrusion:

				mesh = _geometry.getMesh( rhino.MeshType.Any );

				if ( mesh ) {

					geometry = mesh.toThreejsJSON();
					mesh.delete();

				}

				break;

			case rhino.ObjectType.TextDot:

				geometry = extractProperties( _geometry );

				break;

			case rhino.ObjectType.Light:

				geometry = extractProperties( _geometry );

				if ( geometry.lightStyle.name === 'LightStyle_WorldLinear' ) {

					self.postMessage( { type: 'warning', id: taskID, data: {
						message: `THREE.3DMLoader: No conversion exists for ${objectType.constructor.name} ${geometry.lightStyle.name}`,
						type: 'no conversion',
						guid: _attributes.id
					}

					} );

				}

				break;

			case rhino.ObjectType.InstanceReference:

				geometry = extractProperties( _geometry );
				geometry.xform = extractProperties( _geometry.xform );
				geometry.xform.array = _geometry.xform.toFloatArray( true );

				break;

			case rhino.ObjectType.SubD:

				// TODO: precalculate resulting vertices and faces and warn on excessive results
				_geometry.subdivide( 3 );
				mesh = rhino.Mesh.createFromSubDControlNet( _geometry, false );
				if ( mesh ) {

					geometry = mesh.toThreejsJSON();
					mesh.delete();

				}

				break;

				/*
				case rhino.ObjectType.Annotation:
				case rhino.ObjectType.Hatch:
				case rhino.ObjectType.ClipPlane:
				*/

			default:

				self.postMessage( { type: 'warning', id: taskID, data: {
					message: `THREE.3DMLoader: Conversion not implemented for ${objectType.constructor.name}`,
					type: 'not implemented',
					guid: _attributes.id
				}

				} );

				break;

		}

		if ( geometry ) {

			attributes = extractProperties( _attributes );
			attributes.geometry = extractProperties( _geometry );

			if ( _attributes.groupCount > 0 ) {

				attributes.groupIds = _attributes.getGroupList();

			}

			if ( _attributes.userStringCount > 0 ) {

				attributes.userStrings = _attributes.getUserStrings();

			}

			if ( _geometry.userStringCount > 0 ) {

				attributes.geometry.userStrings = _geometry.getUserStrings();

			}

			if ( _attributes.decals().count > 0 ) {

				self.postMessage( { type: 'warning', id: taskID, data: {
					message: 'THREE.3DMLoader: No conversion exists for the decals associated with this object.',
					type: 'no conversion',
					guid: _attributes.id
				}

				} );

			}

			attributes.drawColor = _attributes.drawColor( doc );

			objectType = objectType.constructor.name;
			objectType = objectType.substring( 11, objectType.length );

			return { geometry, attributes, objectType };

		} else {

			self.postMessage( { type: 'warning', id: taskID, data: {
				message: `THREE.3DMLoader: ${objectType.constructor.name} has no associated mesh geometry.`,
				type: 'missing mesh',
				guid: _attributes.id
			}

			} );

		}

	}
```
</details>

### `extractProperties(object: any): {}`

**Parameters:**

- **`object`** `any`

**Returns:** `{}`

**Calls:**

- `value.hasOwnProperty`
- `extractProperties`

<details><summary>Code</summary>

```typescript
function extractProperties( object ) {

		const result = {};

		for ( const property in object ) {

			const value = object[ property ];

			if ( typeof value !== 'function' ) {

				if ( typeof value === 'object' && value !== null && value.hasOwnProperty( 'constructor' ) ) {

					result[ property ] = { name: value.constructor.name, value: value.value };

				} else if ( typeof value === 'object' && value !== null ) {

					result[ property ] = extractProperties( value );

				} else {

					result[ property ] = value;

				}

			} else {

				// these are functions that could be called to extract more data.
				//console.log( `${property}: ${object[ property ].constructor.name}` );

			}

		}

		return result;

	}
```
</details>

### `curveToPoints(curve: any, pointLimit: any): any`

**Parameters:**

- **`curve`** `any`
- **`pointLimit`** `any`

**Returns:** `any`

**Calls:**

- `rc.push`
- `curve.point`
- `curve.segmentCurve`
- `curveToPoints`
- `rc.concat`
- `segment.delete`
- `Math.floor`
- `curve.tryGetPolyline`
- `pLine.get`
- `pLine.delete`
- `ts.push`
- `curve.tangentAt`
- `ts.slice`
- `Math.sqrt`
- `Math.acos`
- `Math.max`
- `Math.min`
- `ts.map`
- `curve.pointAt`

**Internal Comments:**
```
// Duplicated from THREE.Vector3 (x2)
// How to pass imports to worker? (x2)
```

<details><summary>Code</summary>

```typescript
function curveToPoints( curve, pointLimit ) {

		let pointCount = pointLimit;
		let rc = [];
		const ts = [];

		if ( curve instanceof rhino.LineCurve ) {

			return [ curve.pointAtStart, curve.pointAtEnd ];

		}

		if ( curve instanceof rhino.PolylineCurve ) {

			pointCount = curve.pointCount;
			for ( let i = 0; i < pointCount; i ++ ) {

				rc.push( curve.point( i ) );

			}

			return rc;

		}

		if ( curve instanceof rhino.PolyCurve ) {

			const segmentCount = curve.segmentCount;

			for ( let i = 0; i < segmentCount; i ++ ) {

				const segment = curve.segmentCurve( i );
				const segmentArray = curveToPoints( segment, pointCount );
				rc = rc.concat( segmentArray );
				segment.delete();

			}

			return rc;

		}

		if ( curve instanceof rhino.ArcCurve ) {

			pointCount = Math.floor( curve.angleDegrees / 5 );
			pointCount = pointCount < 2 ? 2 : pointCount;
			// alternative to this hardcoded version: https://stackoverflow.com/a/18499923/2179399

		}

		if ( curve instanceof rhino.NurbsCurve && curve.degree === 1 ) {

			const pLine = curve.tryGetPolyline();

			for ( let i = 0; i < pLine.count; i ++ ) {

				rc.push( pLine.get( i ) );

			}

			pLine.delete();

			return rc;

		}

		const domain = curve.domain;
		const divisions = pointCount - 1.0;

		for ( let j = 0; j < pointCount; j ++ ) {

			const t = domain[ 0 ] + ( j / divisions ) * ( domain[ 1 ] - domain[ 0 ] );

			if ( t === domain[ 0 ] || t === domain[ 1 ] ) {

				ts.push( t );
				continue;

			}

			const tan = curve.tangentAt( t );
			const prevTan = curve.tangentAt( ts.slice( - 1 )[ 0 ] );

			// Duplicated from THREE.Vector3
			// How to pass imports to worker?

			const tS = tan[ 0 ] * tan[ 0 ] + tan[ 1 ] * tan[ 1 ] + tan[ 2 ] * tan[ 2 ];
			const ptS = prevTan[ 0 ] * prevTan[ 0 ] + prevTan[ 1 ] * prevTan[ 1 ] + prevTan[ 2 ] * prevTan[ 2 ];

			const denominator = Math.sqrt( tS * ptS );

			let angle;

			if ( denominator === 0 ) {

				angle = Math.PI / 2;

			} else {

				const theta = ( tan.x * prevTan.x + tan.y * prevTan.y + tan.z * prevTan.z ) / denominator;
				angle = Math.acos( Math.max( - 1, Math.min( 1, theta ) ) );

			}

			if ( angle < 0.1 ) continue;

			ts.push( t );

		}

		rc = ts.map( t => curve.pointAt( t ) );
		return rc;

	}
```
</details>


---

## Classes

### `Rhino3dmLoader`

<details><summary>Class Code</summary>

```ts
class Rhino3dmLoader extends Loader {

	/**
	 * Constructs a new Rhino 3DM loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		// internals

		this.libraryPath = '';
		this.libraryPending = null;
		this.libraryBinary = null;
		this.libraryConfig = {};

		this.url = '';

		this.workerLimit = 4;
		this.workerPool = [];
		this.workerNextTaskID = 1;
		this.workerSourceURL = '';
		this.workerConfig = {};

		this.materials = [];
		this.warnings = [];

	}

	/**
	 * Path to a folder containing the JS and WASM libraries.
	 *
	 * @param {string} path - The library path to set.
	 * @return {Rhino3dmLoader} A reference to this loader.
	 */
	setLibraryPath( path ) {

		this.libraryPath = path;

		return this;

	}

	/**
	 * Sets the maximum number of Web Workers to be used during decoding.
	 * A lower limit may be preferable if workers are also for other
	 * tasks in the application.
	 *
	 * @param {number} workerLimit - The worker limit.
	 * @return {Rhino3dmLoader} A reference to this loader.
	 */
	setWorkerLimit( workerLimit ) {

		this.workerLimit = workerLimit;

		return this;

	}

	/**
	 * Starts loading from the given URL and passes the loaded 3DM asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Object3D)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );

		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );

		this.url = url;

		loader.load( url, ( buffer ) => {

			// Check for an existing task using this buffer. A transferred buffer cannot be transferred
			// again from this thread.
			if ( _taskCache.has( buffer ) ) {

				const cachedTask = _taskCache.get( buffer );

				return cachedTask.promise.then( onLoad ).catch( onError );

			}

			this.decodeObjects( buffer, url )
				.then( result => {

					result.userData.warnings = this.warnings;
					onLoad( result );

				 } )
				.catch( e => onError( e ) );

		}, onProgress, onError );

	}

	/**
	 * Prints debug messages to the browser console.
	 */
	debug() {

		console.log( 'Task load: ', this.workerPool.map( ( worker ) => worker._taskLoad ) );

	}

	/**
	 * Decodes the 3DM asset data with a Web Worker.
	 *
	 * @param {ArrayBuffer} buffer - The raw 3DM asset data as an array buffer.
	 * @param {string} url - The asset URL.
	 * @return {Promise<Object3D>} A Promise that resolved with the decoded 3D object.
	 */
	decodeObjects( buffer, url ) {

		let worker;
		let taskID;

		const taskCost = buffer.byteLength;

		const objectPending = this._getWorker( taskCost )
			.then( ( _worker ) => {

				worker = _worker;
				taskID = this.workerNextTaskID ++;

				return new Promise( ( resolve, reject ) => {

					worker._callbacks[ taskID ] = { resolve, reject };

					worker.postMessage( { type: 'decode', id: taskID, buffer }, [ buffer ] );

					// this.debug();

				} );

			} )
			.then( ( message ) => this._createGeometry( message.data ) )
			.catch( e => {

				throw e;

			} );

		// Remove task from the task list.
		// Note: replaced '.finally()' with '.catch().then()' block - iOS 11 support (#19416)
		objectPending
			.catch( () => true )
			.then( () => {

				if ( worker && taskID ) {

					this._releaseTask( worker, taskID );

					//this.debug();

				}

			} );

		// Cache the task result.
		_taskCache.set( buffer, {

			url: url,
			promise: objectPending

		} );

		return objectPending;

	}

	/**
	 * Parses the given 3DM data and passes the loaded 3DM asset
	 * to the `onLoad()` callback.
	 *
	 * @param {ArrayBuffer} data - The raw 3DM asset data as an array buffer.
	 * @param {function(Object3D)} onLoad - Executed when the loading process has been finished.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	parse( data, onLoad, onError ) {

		this.decodeObjects( data, '' )
			.then( result => {

				result.userData.warnings = this.warnings;
				onLoad( result );

			} )
			.catch( e => onError( e ) );

	}

	_compareMaterials( material ) {

		const mat = {};
		mat.name = material.name;
		mat.color = {};
		mat.color.r = material.color.r;
		mat.color.g = material.color.g;
		mat.color.b = material.color.b;
		mat.type = material.type;
		mat.vertexColors = material.vertexColors;

		const json = JSON.stringify( mat );

		for ( let i = 0; i < this.materials.length; i ++ ) {

			const m = this.materials[ i ];
			const _mat = {};
			_mat.name = m.name;
			_mat.color = {};
			_mat.color.r = m.color.r;
			_mat.color.g = m.color.g;
			_mat.color.b = m.color.b;
			_mat.type = m.type;
			_mat.vertexColors = m.vertexColors;

			if ( JSON.stringify( _mat ) === json ) {

				return m;

			}

		}

		this.materials.push( material );

		return material;

	}

	_createMaterial( material, renderEnvironment ) {

		if ( material === undefined ) {

			return new MeshStandardMaterial( {
				color: new Color( 1, 1, 1 ),
				metalness: 0.8,
				name: Loader.DEFAULT_MATERIAL_NAME,
				side: DoubleSide
			} );

		}

		//console.log(material)

		const mat = new MeshPhysicalMaterial( {

			color: new Color( material.diffuseColor.r / 255.0, material.diffuseColor.g / 255.0, material.diffuseColor.b / 255.0 ),
			emissive: new Color( material.emissionColor.r, material.emissionColor.g, material.emissionColor.b ),
			flatShading: material.disableLighting,
			ior: material.indexOfRefraction,
			name: material.name,
			reflectivity: material.reflectivity,
			opacity: 1.0 - material.transparency,
			side: DoubleSide,
			specularColor: material.specularColor,
			transparent: material.transparency > 0 ? true : false

		} );

		mat.userData.id = material.id;

		if ( material.pbrSupported ) {

			const pbr = material.pbr;

			mat.anisotropy = pbr.anisotropic;
			mat.anisotropyRotation = pbr.anisotropicRotation;
			mat.color = new Color( pbr.baseColor.r, pbr.baseColor.g, pbr.baseColor.b );
			mat.clearcoat = pbr.clearcoat;
			mat.clearcoatRoughness = pbr.clearcoatRoughness;
			mat.metalness = pbr.metallic;
			mat.transmission = 1 - pbr.opacity;
			mat.roughness = pbr.roughness;
			mat.sheen = pbr.sheen;
			mat.specularIntensity = pbr.specular;
			mat.thickness = pbr.subsurface;

		}

		if ( material.pbrSupported && material.pbr.opacity === 0 && material.transparency === 1 ) {

			//some compromises

			mat.opacity = 0.2;
			mat.transmission = 1.00;

		}

		const textureLoader = new TextureLoader();

		for ( let i = 0; i < material.textures.length; i ++ ) {

			const texture = material.textures[ i ];

			if ( texture.image !== null ) {

				const map = textureLoader.load( texture.image );

				//console.log(texture.type )

				switch ( texture.type ) {

					case 'Bump':

						mat.bumpMap = map;

						break;

					case 'Diffuse':

						mat.map = map;

						break;

					case 'Emap':

						mat.envMap = map;

						break;

					case 'Opacity':

						mat.transmissionMap = map;

						break;

					case 'Transparency':

						mat.alphaMap = map;
						mat.transparent = true;

						break;

					case 'PBR_Alpha':

						mat.alphaMap = map;
						mat.transparent = true;

						break;

					case 'PBR_AmbientOcclusion':

						mat.aoMap = map;

						break;

					case 'PBR_Anisotropic':

						mat.anisotropyMap = map;

						break;

					case 'PBR_BaseColor':

						mat.map = map;

						break;

					case 'PBR_Clearcoat':

						mat.clearcoatMap = map;

						break;

					case 'PBR_ClearcoatBump':

						mat.clearcoatNormalMap = map;

						break;

					case 'PBR_ClearcoatRoughness':

						mat.clearcoatRoughnessMap = map;

						break;

					case 'PBR_Displacement':

						mat.displacementMap = map;

						break;

					case 'PBR_Emission':

						mat.emissiveMap = map;

						break;

					case 'PBR_Metallic':

						mat.metalnessMap = map;

						break;

					case 'PBR_Roughness':

						mat.roughnessMap = map;

						break;

					case 'PBR_Sheen':

						mat.sheenColorMap = map;

						break;

					case 'PBR_Specular':

						mat.specularColorMap = map;

						break;

					case 'PBR_Subsurface':

						mat.thicknessMap = map;

						break;

					default:

						this.warnings.push( {
							message: `THREE.3DMLoader: No conversion exists for 3dm ${texture.type}.`,
							type: 'no conversion'
						} );

						break;

				}

				map.wrapS = texture.wrapU === 0 ? RepeatWrapping : ClampToEdgeWrapping;
				map.wrapT = texture.wrapV === 0 ? RepeatWrapping : ClampToEdgeWrapping;

				if ( texture.repeat ) {

					map.repeat.set( texture.repeat[ 0 ], texture.repeat[ 1 ] );

				}

			}

		}

		if ( renderEnvironment ) {

			new EXRLoader().load( renderEnvironment.image, function ( texture ) {

				texture.mapping = THREE.EquirectangularReflectionMapping;
				mat.envMap = texture;

			} );

		}

		return mat;

	}

	_createGeometry( data ) {

		const object = new Object3D();
		const instanceDefinitionObjects = [];
		const instanceDefinitions = [];
		const instanceReferences = [];

		object.userData[ 'layers' ] = data.layers;
		object.userData[ 'groups' ] = data.groups;
		object.userData[ 'settings' ] = data.settings;
		object.userData.settings[ 'renderSettings' ] = data.renderSettings;
		object.userData[ 'objectType' ] = 'File3dm';
		object.userData[ 'materials' ] = null;

		object.name = this.url;

		let objects = data.objects;
		const materials = data.materials;

		for ( let i = 0; i < objects.length; i ++ ) {

			const obj = objects[ i ];
			const attributes = obj.attributes;

			switch ( obj.objectType ) {

				case 'InstanceDefinition':

					instanceDefinitions.push( obj );

					break;

				case 'InstanceReference':

					instanceReferences.push( obj );

					break;

				default:

					let matId = null;

					switch ( attributes.materialSource.name ) {

						case 'ObjectMaterialSource_MaterialFromLayer':
							//check layer index
							if ( attributes.layerIndex >= 0 ) {

								matId = data.layers[ attributes.layerIndex ].renderMaterialIndex;

							}

							break;

						case 'ObjectMaterialSource_MaterialFromObject':

							if ( attributes.materialIndex >= 0 ) {

								matId = attributes.materialIndex;

							}

							break;

					}

					let material = null;

					if ( matId >= 0 ) {

						const rMaterial = materials[ matId ];
						material = this._createMaterial( rMaterial, data.renderEnvironment );


					}

					const _object = this._createObject( obj, material );

					if ( _object === undefined ) {

						continue;

					}

					const layer = data.layers[ attributes.layerIndex ];

					_object.visible = layer ? data.layers[ attributes.layerIndex ].visible : true;

					if ( attributes.isInstanceDefinitionObject ) {

						instanceDefinitionObjects.push( _object );

					} else {

						object.add( _object );

					}

					break;

			}

		}

		for ( let i = 0; i < instanceDefinitions.length; i ++ ) {

			const iDef = instanceDefinitions[ i ];

			objects = [];

			for ( let j = 0; j < iDef.attributes.objectIds.length; j ++ ) {

				const objId = iDef.attributes.objectIds[ j ];

				for ( let p = 0; p < instanceDefinitionObjects.length; p ++ ) {

					const idoId = instanceDefinitionObjects[ p ].userData.attributes.id;

					if ( objId === idoId ) {

						objects.push( instanceDefinitionObjects[ p ] );

					}

				}

			}

			// Currently clones geometry and does not take advantage of instancing

			for ( let j = 0; j < instanceReferences.length; j ++ ) {

				const iRef = instanceReferences[ j ];

				if ( iRef.geometry.parentIdefId === iDef.attributes.id ) {

					const iRefObject = new Object3D();
					const xf = iRef.geometry.xform.array;

					const matrix = new Matrix4();
					matrix.set( ...xf );

					iRefObject.applyMatrix4( matrix );

					for ( let p = 0; p < objects.length; p ++ ) {

						iRefObject.add( objects[ p ].clone( true ) );

					}

					object.add( iRefObject );

				}

			}

		}

		object.userData[ 'materials' ] = this.materials;
		object.name = '';
		return object;

	}

	_createObject( obj, mat ) {

		const loader = new BufferGeometryLoader();

		const attributes = obj.attributes;

		let geometry, material, _color, color;

		switch ( obj.objectType ) {

			case 'Point':
			case 'PointSet':

				geometry = loader.parse( obj.geometry );

				if ( geometry.attributes.hasOwnProperty( 'color' ) ) {

					material = new PointsMaterial( { vertexColors: true, sizeAttenuation: false, size: 2 } );

				} else {

					_color = attributes.drawColor;
					color = new Color( _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 );
					material = new PointsMaterial( { color: color, sizeAttenuation: false, size: 2 } );

				}

				material = this._compareMaterials( material );

				const points = new Points( geometry, material );
				points.userData[ 'attributes' ] = attributes;
				points.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					points.name = attributes.name;

				}

				return points;

			case 'Mesh':
			case 'Extrusion':
			case 'SubD':
			case 'Brep':

				if ( obj.geometry === null ) return;

				geometry = loader.parse( obj.geometry );


				if ( mat === null ) {

					mat = this._createMaterial();

				}


				if ( geometry.attributes.hasOwnProperty( 'color' ) ) {

					mat.vertexColors = true;

				}

				mat = this._compareMaterials( mat );

				const mesh = new Mesh( geometry, mat );
				mesh.castShadow = attributes.castsShadows;
				mesh.receiveShadow = attributes.receivesShadows;
				mesh.userData[ 'attributes' ] = attributes;
				mesh.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					mesh.name = attributes.name;

				}

				return mesh;

			case 'Curve':

				geometry = loader.parse( obj.geometry );

				_color = attributes.drawColor;
				color = new Color( _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 );

				material = new LineBasicMaterial( { color: color } );
				material = this._compareMaterials( material );

				const lines = new Line( geometry, material );
				lines.userData[ 'attributes' ] = attributes;
				lines.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					lines.name = attributes.name;

				}

				return lines;

			case 'TextDot':

				geometry = obj.geometry;

				const ctx = document.createElement( 'canvas' ).getContext( '2d' );
				const font = `${geometry.fontHeight}px ${geometry.fontFace}`;
				ctx.font = font;
				const width = ctx.measureText( geometry.text ).width + 10;
				const height = geometry.fontHeight + 10;

				const r = window.devicePixelRatio;

				ctx.canvas.width = width * r;
				ctx.canvas.height = height * r;
				ctx.canvas.style.width = width + 'px';
				ctx.canvas.style.height = height + 'px';
				ctx.setTransform( r, 0, 0, r, 0, 0 );

				ctx.font = font;
				ctx.textBaseline = 'middle';
				ctx.textAlign = 'center';
				color = attributes.drawColor;
				ctx.fillStyle = `rgba(${color.r},${color.g},${color.b},${color.a})`;
				ctx.fillRect( 0, 0, width, height );
				ctx.fillStyle = 'white';
				ctx.fillText( geometry.text, width / 2, height / 2 );

				const texture = new CanvasTexture( ctx.canvas );
				texture.minFilter = LinearFilter;
				texture.generateMipmaps = false;
				texture.wrapS = ClampToEdgeWrapping;
				texture.wrapT = ClampToEdgeWrapping;

				material = new SpriteMaterial( { map: texture, depthTest: false } );
				const sprite = new Sprite( material );
				sprite.position.set( geometry.point[ 0 ], geometry.point[ 1 ], geometry.point[ 2 ] );
				sprite.scale.set( width / 10, height / 10, 1.0 );

				sprite.userData[ 'attributes' ] = attributes;
				sprite.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					sprite.name = attributes.name;

				}

				return sprite;

			case 'Light':

				geometry = obj.geometry;

				let light;

				switch ( geometry.lightStyle.name ) {

					case 'LightStyle_WorldPoint':

						light = new PointLight();
						light.castShadow = attributes.castsShadows;
						light.position.set( geometry.location[ 0 ], geometry.location[ 1 ], geometry.location[ 2 ] );
						light.shadow.normalBias = 0.1;

						break;

					case 'LightStyle_WorldSpot':

						light = new SpotLight();
						light.castShadow = attributes.castsShadows;
						light.position.set( geometry.location[ 0 ], geometry.location[ 1 ], geometry.location[ 2 ] );
						light.target.position.set( geometry.direction[ 0 ], geometry.direction[ 1 ], geometry.direction[ 2 ] );
						light.angle = geometry.spotAngleRadians;
						light.shadow.normalBias = 0.1;

						break;

					case 'LightStyle_WorldRectangular':

						light = new RectAreaLight();
						const width = Math.abs( geometry.width[ 2 ] );
						const height = Math.abs( geometry.length[ 0 ] );
						light.position.set( geometry.location[ 0 ] - ( height / 2 ), geometry.location[ 1 ], geometry.location[ 2 ] - ( width / 2 ) );
						light.height = height;
						light.width = width;
						light.lookAt( geometry.direction[ 0 ], geometry.direction[ 1 ], geometry.direction[ 2 ] );

						break;

					case 'LightStyle_WorldDirectional':

						light = new DirectionalLight();
						light.castShadow = attributes.castsShadows;
						light.position.set( geometry.location[ 0 ], geometry.location[ 1 ], geometry.location[ 2 ] );
						light.target.position.set( geometry.direction[ 0 ], geometry.direction[ 1 ], geometry.direction[ 2 ] );
						light.shadow.normalBias = 0.1;

						break;

					case 'LightStyle_WorldLinear':
						// no conversion exists, warning has already been printed to the console
						break;

					default:
						break;

				}

				if ( light ) {

					light.intensity = geometry.intensity;
					_color = geometry.diffuse;
					color = new Color( _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 );
					light.color = color;
					light.userData[ 'attributes' ] = attributes;
					light.userData[ 'objectType' ] = obj.objectType;

				}

				return light;

		}

	}

	_initLibrary() {

		if ( ! this.libraryPending ) {

			// Load rhino3dm wrapper.
			const jsLoader = new FileLoader( this.manager );
			jsLoader.setPath( this.libraryPath );
			const jsContent = new Promise( ( resolve, reject ) => {

				jsLoader.load( 'rhino3dm.js', resolve, undefined, reject );

			} );

			// Load rhino3dm WASM binary.
			const binaryLoader = new FileLoader( this.manager );
			binaryLoader.setPath( this.libraryPath );
			binaryLoader.setResponseType( 'arraybuffer' );
			const binaryContent = new Promise( ( resolve, reject ) => {

				binaryLoader.load( 'rhino3dm.wasm', resolve, undefined, reject );

			} );

			this.libraryPending = Promise.all( [ jsContent, binaryContent ] )
				.then( ( [ jsContent, binaryContent ] ) => {

					//this.libraryBinary = binaryContent;
					this.libraryConfig.wasmBinary = binaryContent;

					const fn = Rhino3dmWorker.toString();

					const body = [
						'/* rhino3dm.js */',
						jsContent,
						'/* worker */',
						fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
					].join( '\n' );

					this.workerSourceURL = URL.createObjectURL( new Blob( [ body ] ) );

				} );

		}

		return this.libraryPending;

	}

	_getWorker( taskCost ) {

		return this._initLibrary().then( () => {

			if ( this.workerPool.length < this.workerLimit ) {

				const worker = new Worker( this.workerSourceURL );

				worker._callbacks = {};
				worker._taskCosts = {};
				worker._taskLoad = 0;

				worker.postMessage( {
					type: 'init',
					libraryConfig: this.libraryConfig
				} );

				worker.onmessage = e => {

					const message = e.data;

					switch ( message.type ) {

						case 'warning':
							this.warnings.push( message.data );
							console.warn( message.data );
							break;

						case 'decode':
							worker._callbacks[ message.id ].resolve( message );
							break;

						case 'error':
							worker._callbacks[ message.id ].reject( message );
							break;

						default:
							console.error( 'THREE.Rhino3dmLoader: Unexpected message, "' + message.type + '"' );

					}

				};

				this.workerPool.push( worker );

			} else {

				this.workerPool.sort( function ( a, b ) {

					return a._taskLoad > b._taskLoad ? - 1 : 1;

				} );

			}

			const worker = this.workerPool[ this.workerPool.length - 1 ];

			worker._taskLoad += taskCost;

			return worker;

		} );

	}

	_releaseTask( worker, taskID ) {

		worker._taskLoad -= worker._taskCosts[ taskID ];
		delete worker._callbacks[ taskID ];
		delete worker._taskCosts[ taskID ];

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the loader is no longer required.
	 */
	dispose() {

		for ( let i = 0; i < this.workerPool.length; ++ i ) {

			this.workerPool[ i ].terminate();

		}

		this.workerPool.length = 0;

	}

}
```
</details>

#### Methods

##### `setLibraryPath(path: string): Rhino3dmLoader`

<details><summary>Code</summary>

```ts
setLibraryPath( path ) {

		this.libraryPath = path;

		return this;

	}
```
</details>

##### `setWorkerLimit(workerLimit: number): Rhino3dmLoader`

<details><summary>Code</summary>

```ts
setWorkerLimit( workerLimit ) {

		this.workerLimit = workerLimit;

		return this;

	}
```
</details>

##### `load(url: string, onLoad: (arg0: Object3D) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );

		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );

		this.url = url;

		loader.load( url, ( buffer ) => {

			// Check for an existing task using this buffer. A transferred buffer cannot be transferred
			// again from this thread.
			if ( _taskCache.has( buffer ) ) {

				const cachedTask = _taskCache.get( buffer );

				return cachedTask.promise.then( onLoad ).catch( onError );

			}

			this.decodeObjects( buffer, url )
				.then( result => {

					result.userData.warnings = this.warnings;
					onLoad( result );

				 } )
				.catch( e => onError( e ) );

		}, onProgress, onError );

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

##### `decodeObjects(buffer: ArrayBuffer, url: string): Promise<Object3D>`

<details><summary>Code</summary>

```ts
decodeObjects( buffer, url ) {

		let worker;
		let taskID;

		const taskCost = buffer.byteLength;

		const objectPending = this._getWorker( taskCost )
			.then( ( _worker ) => {

				worker = _worker;
				taskID = this.workerNextTaskID ++;

				return new Promise( ( resolve, reject ) => {

					worker._callbacks[ taskID ] = { resolve, reject };

					worker.postMessage( { type: 'decode', id: taskID, buffer }, [ buffer ] );

					// this.debug();

				} );

			} )
			.then( ( message ) => this._createGeometry( message.data ) )
			.catch( e => {

				throw e;

			} );

		// Remove task from the task list.
		// Note: replaced '.finally()' with '.catch().then()' block - iOS 11 support (#19416)
		objectPending
			.catch( () => true )
			.then( () => {

				if ( worker && taskID ) {

					this._releaseTask( worker, taskID );

					//this.debug();

				}

			} );

		// Cache the task result.
		_taskCache.set( buffer, {

			url: url,
			promise: objectPending

		} );

		return objectPending;

	}
```
</details>

##### `parse(data: ArrayBuffer, onLoad: (arg0: Object3D) => any, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
parse( data, onLoad, onError ) {

		this.decodeObjects( data, '' )
			.then( result => {

				result.userData.warnings = this.warnings;
				onLoad( result );

			} )
			.catch( e => onError( e ) );

	}
```
</details>

##### `_compareMaterials(material: any): any`

<details><summary>Code</summary>

```ts
_compareMaterials( material ) {

		const mat = {};
		mat.name = material.name;
		mat.color = {};
		mat.color.r = material.color.r;
		mat.color.g = material.color.g;
		mat.color.b = material.color.b;
		mat.type = material.type;
		mat.vertexColors = material.vertexColors;

		const json = JSON.stringify( mat );

		for ( let i = 0; i < this.materials.length; i ++ ) {

			const m = this.materials[ i ];
			const _mat = {};
			_mat.name = m.name;
			_mat.color = {};
			_mat.color.r = m.color.r;
			_mat.color.g = m.color.g;
			_mat.color.b = m.color.b;
			_mat.type = m.type;
			_mat.vertexColors = m.vertexColors;

			if ( JSON.stringify( _mat ) === json ) {

				return m;

			}

		}

		this.materials.push( material );

		return material;

	}
```
</details>

##### `_createMaterial(material: any, renderEnvironment: any): any`

<details><summary>Code</summary>

```ts
_createMaterial( material, renderEnvironment ) {

		if ( material === undefined ) {

			return new MeshStandardMaterial( {
				color: new Color( 1, 1, 1 ),
				metalness: 0.8,
				name: Loader.DEFAULT_MATERIAL_NAME,
				side: DoubleSide
			} );

		}

		//console.log(material)

		const mat = new MeshPhysicalMaterial( {

			color: new Color( material.diffuseColor.r / 255.0, material.diffuseColor.g / 255.0, material.diffuseColor.b / 255.0 ),
			emissive: new Color( material.emissionColor.r, material.emissionColor.g, material.emissionColor.b ),
			flatShading: material.disableLighting,
			ior: material.indexOfRefraction,
			name: material.name,
			reflectivity: material.reflectivity,
			opacity: 1.0 - material.transparency,
			side: DoubleSide,
			specularColor: material.specularColor,
			transparent: material.transparency > 0 ? true : false

		} );

		mat.userData.id = material.id;

		if ( material.pbrSupported ) {

			const pbr = material.pbr;

			mat.anisotropy = pbr.anisotropic;
			mat.anisotropyRotation = pbr.anisotropicRotation;
			mat.color = new Color( pbr.baseColor.r, pbr.baseColor.g, pbr.baseColor.b );
			mat.clearcoat = pbr.clearcoat;
			mat.clearcoatRoughness = pbr.clearcoatRoughness;
			mat.metalness = pbr.metallic;
			mat.transmission = 1 - pbr.opacity;
			mat.roughness = pbr.roughness;
			mat.sheen = pbr.sheen;
			mat.specularIntensity = pbr.specular;
			mat.thickness = pbr.subsurface;

		}

		if ( material.pbrSupported && material.pbr.opacity === 0 && material.transparency === 1 ) {

			//some compromises

			mat.opacity = 0.2;
			mat.transmission = 1.00;

		}

		const textureLoader = new TextureLoader();

		for ( let i = 0; i < material.textures.length; i ++ ) {

			const texture = material.textures[ i ];

			if ( texture.image !== null ) {

				const map = textureLoader.load( texture.image );

				//console.log(texture.type )

				switch ( texture.type ) {

					case 'Bump':

						mat.bumpMap = map;

						break;

					case 'Diffuse':

						mat.map = map;

						break;

					case 'Emap':

						mat.envMap = map;

						break;

					case 'Opacity':

						mat.transmissionMap = map;

						break;

					case 'Transparency':

						mat.alphaMap = map;
						mat.transparent = true;

						break;

					case 'PBR_Alpha':

						mat.alphaMap = map;
						mat.transparent = true;

						break;

					case 'PBR_AmbientOcclusion':

						mat.aoMap = map;

						break;

					case 'PBR_Anisotropic':

						mat.anisotropyMap = map;

						break;

					case 'PBR_BaseColor':

						mat.map = map;

						break;

					case 'PBR_Clearcoat':

						mat.clearcoatMap = map;

						break;

					case 'PBR_ClearcoatBump':

						mat.clearcoatNormalMap = map;

						break;

					case 'PBR_ClearcoatRoughness':

						mat.clearcoatRoughnessMap = map;

						break;

					case 'PBR_Displacement':

						mat.displacementMap = map;

						break;

					case 'PBR_Emission':

						mat.emissiveMap = map;

						break;

					case 'PBR_Metallic':

						mat.metalnessMap = map;

						break;

					case 'PBR_Roughness':

						mat.roughnessMap = map;

						break;

					case 'PBR_Sheen':

						mat.sheenColorMap = map;

						break;

					case 'PBR_Specular':

						mat.specularColorMap = map;

						break;

					case 'PBR_Subsurface':

						mat.thicknessMap = map;

						break;

					default:

						this.warnings.push( {
							message: `THREE.3DMLoader: No conversion exists for 3dm ${texture.type}.`,
							type: 'no conversion'
						} );

						break;

				}

				map.wrapS = texture.wrapU === 0 ? RepeatWrapping : ClampToEdgeWrapping;
				map.wrapT = texture.wrapV === 0 ? RepeatWrapping : ClampToEdgeWrapping;

				if ( texture.repeat ) {

					map.repeat.set( texture.repeat[ 0 ], texture.repeat[ 1 ] );

				}

			}

		}

		if ( renderEnvironment ) {

			new EXRLoader().load( renderEnvironment.image, function ( texture ) {

				texture.mapping = THREE.EquirectangularReflectionMapping;
				mat.envMap = texture;

			} );

		}

		return mat;

	}
```
</details>

##### `_createGeometry(data: any): any`

<details><summary>Code</summary>

```ts
_createGeometry( data ) {

		const object = new Object3D();
		const instanceDefinitionObjects = [];
		const instanceDefinitions = [];
		const instanceReferences = [];

		object.userData[ 'layers' ] = data.layers;
		object.userData[ 'groups' ] = data.groups;
		object.userData[ 'settings' ] = data.settings;
		object.userData.settings[ 'renderSettings' ] = data.renderSettings;
		object.userData[ 'objectType' ] = 'File3dm';
		object.userData[ 'materials' ] = null;

		object.name = this.url;

		let objects = data.objects;
		const materials = data.materials;

		for ( let i = 0; i < objects.length; i ++ ) {

			const obj = objects[ i ];
			const attributes = obj.attributes;

			switch ( obj.objectType ) {

				case 'InstanceDefinition':

					instanceDefinitions.push( obj );

					break;

				case 'InstanceReference':

					instanceReferences.push( obj );

					break;

				default:

					let matId = null;

					switch ( attributes.materialSource.name ) {

						case 'ObjectMaterialSource_MaterialFromLayer':
							//check layer index
							if ( attributes.layerIndex >= 0 ) {

								matId = data.layers[ attributes.layerIndex ].renderMaterialIndex;

							}

							break;

						case 'ObjectMaterialSource_MaterialFromObject':

							if ( attributes.materialIndex >= 0 ) {

								matId = attributes.materialIndex;

							}

							break;

					}

					let material = null;

					if ( matId >= 0 ) {

						const rMaterial = materials[ matId ];
						material = this._createMaterial( rMaterial, data.renderEnvironment );


					}

					const _object = this._createObject( obj, material );

					if ( _object === undefined ) {

						continue;

					}

					const layer = data.layers[ attributes.layerIndex ];

					_object.visible = layer ? data.layers[ attributes.layerIndex ].visible : true;

					if ( attributes.isInstanceDefinitionObject ) {

						instanceDefinitionObjects.push( _object );

					} else {

						object.add( _object );

					}

					break;

			}

		}

		for ( let i = 0; i < instanceDefinitions.length; i ++ ) {

			const iDef = instanceDefinitions[ i ];

			objects = [];

			for ( let j = 0; j < iDef.attributes.objectIds.length; j ++ ) {

				const objId = iDef.attributes.objectIds[ j ];

				for ( let p = 0; p < instanceDefinitionObjects.length; p ++ ) {

					const idoId = instanceDefinitionObjects[ p ].userData.attributes.id;

					if ( objId === idoId ) {

						objects.push( instanceDefinitionObjects[ p ] );

					}

				}

			}

			// Currently clones geometry and does not take advantage of instancing

			for ( let j = 0; j < instanceReferences.length; j ++ ) {

				const iRef = instanceReferences[ j ];

				if ( iRef.geometry.parentIdefId === iDef.attributes.id ) {

					const iRefObject = new Object3D();
					const xf = iRef.geometry.xform.array;

					const matrix = new Matrix4();
					matrix.set( ...xf );

					iRefObject.applyMatrix4( matrix );

					for ( let p = 0; p < objects.length; p ++ ) {

						iRefObject.add( objects[ p ].clone( true ) );

					}

					object.add( iRefObject );

				}

			}

		}

		object.userData[ 'materials' ] = this.materials;
		object.name = '';
		return object;

	}
```
</details>

##### `_createObject(obj: any, mat: any): any`

<details><summary>Code</summary>

```ts
_createObject( obj, mat ) {

		const loader = new BufferGeometryLoader();

		const attributes = obj.attributes;

		let geometry, material, _color, color;

		switch ( obj.objectType ) {

			case 'Point':
			case 'PointSet':

				geometry = loader.parse( obj.geometry );

				if ( geometry.attributes.hasOwnProperty( 'color' ) ) {

					material = new PointsMaterial( { vertexColors: true, sizeAttenuation: false, size: 2 } );

				} else {

					_color = attributes.drawColor;
					color = new Color( _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 );
					material = new PointsMaterial( { color: color, sizeAttenuation: false, size: 2 } );

				}

				material = this._compareMaterials( material );

				const points = new Points( geometry, material );
				points.userData[ 'attributes' ] = attributes;
				points.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					points.name = attributes.name;

				}

				return points;

			case 'Mesh':
			case 'Extrusion':
			case 'SubD':
			case 'Brep':

				if ( obj.geometry === null ) return;

				geometry = loader.parse( obj.geometry );


				if ( mat === null ) {

					mat = this._createMaterial();

				}


				if ( geometry.attributes.hasOwnProperty( 'color' ) ) {

					mat.vertexColors = true;

				}

				mat = this._compareMaterials( mat );

				const mesh = new Mesh( geometry, mat );
				mesh.castShadow = attributes.castsShadows;
				mesh.receiveShadow = attributes.receivesShadows;
				mesh.userData[ 'attributes' ] = attributes;
				mesh.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					mesh.name = attributes.name;

				}

				return mesh;

			case 'Curve':

				geometry = loader.parse( obj.geometry );

				_color = attributes.drawColor;
				color = new Color( _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 );

				material = new LineBasicMaterial( { color: color } );
				material = this._compareMaterials( material );

				const lines = new Line( geometry, material );
				lines.userData[ 'attributes' ] = attributes;
				lines.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					lines.name = attributes.name;

				}

				return lines;

			case 'TextDot':

				geometry = obj.geometry;

				const ctx = document.createElement( 'canvas' ).getContext( '2d' );
				const font = `${geometry.fontHeight}px ${geometry.fontFace}`;
				ctx.font = font;
				const width = ctx.measureText( geometry.text ).width + 10;
				const height = geometry.fontHeight + 10;

				const r = window.devicePixelRatio;

				ctx.canvas.width = width * r;
				ctx.canvas.height = height * r;
				ctx.canvas.style.width = width + 'px';
				ctx.canvas.style.height = height + 'px';
				ctx.setTransform( r, 0, 0, r, 0, 0 );

				ctx.font = font;
				ctx.textBaseline = 'middle';
				ctx.textAlign = 'center';
				color = attributes.drawColor;
				ctx.fillStyle = `rgba(${color.r},${color.g},${color.b},${color.a})`;
				ctx.fillRect( 0, 0, width, height );
				ctx.fillStyle = 'white';
				ctx.fillText( geometry.text, width / 2, height / 2 );

				const texture = new CanvasTexture( ctx.canvas );
				texture.minFilter = LinearFilter;
				texture.generateMipmaps = false;
				texture.wrapS = ClampToEdgeWrapping;
				texture.wrapT = ClampToEdgeWrapping;

				material = new SpriteMaterial( { map: texture, depthTest: false } );
				const sprite = new Sprite( material );
				sprite.position.set( geometry.point[ 0 ], geometry.point[ 1 ], geometry.point[ 2 ] );
				sprite.scale.set( width / 10, height / 10, 1.0 );

				sprite.userData[ 'attributes' ] = attributes;
				sprite.userData[ 'objectType' ] = obj.objectType;

				if ( attributes.name ) {

					sprite.name = attributes.name;

				}

				return sprite;

			case 'Light':

				geometry = obj.geometry;

				let light;

				switch ( geometry.lightStyle.name ) {

					case 'LightStyle_WorldPoint':

						light = new PointLight();
						light.castShadow = attributes.castsShadows;
						light.position.set( geometry.location[ 0 ], geometry.location[ 1 ], geometry.location[ 2 ] );
						light.shadow.normalBias = 0.1;

						break;

					case 'LightStyle_WorldSpot':

						light = new SpotLight();
						light.castShadow = attributes.castsShadows;
						light.position.set( geometry.location[ 0 ], geometry.location[ 1 ], geometry.location[ 2 ] );
						light.target.position.set( geometry.direction[ 0 ], geometry.direction[ 1 ], geometry.direction[ 2 ] );
						light.angle = geometry.spotAngleRadians;
						light.shadow.normalBias = 0.1;

						break;

					case 'LightStyle_WorldRectangular':

						light = new RectAreaLight();
						const width = Math.abs( geometry.width[ 2 ] );
						const height = Math.abs( geometry.length[ 0 ] );
						light.position.set( geometry.location[ 0 ] - ( height / 2 ), geometry.location[ 1 ], geometry.location[ 2 ] - ( width / 2 ) );
						light.height = height;
						light.width = width;
						light.lookAt( geometry.direction[ 0 ], geometry.direction[ 1 ], geometry.direction[ 2 ] );

						break;

					case 'LightStyle_WorldDirectional':

						light = new DirectionalLight();
						light.castShadow = attributes.castsShadows;
						light.position.set( geometry.location[ 0 ], geometry.location[ 1 ], geometry.location[ 2 ] );
						light.target.position.set( geometry.direction[ 0 ], geometry.direction[ 1 ], geometry.direction[ 2 ] );
						light.shadow.normalBias = 0.1;

						break;

					case 'LightStyle_WorldLinear':
						// no conversion exists, warning has already been printed to the console
						break;

					default:
						break;

				}

				if ( light ) {

					light.intensity = geometry.intensity;
					_color = geometry.diffuse;
					color = new Color( _color.r / 255.0, _color.g / 255.0, _color.b / 255.0 );
					light.color = color;
					light.userData[ 'attributes' ] = attributes;
					light.userData[ 'objectType' ] = obj.objectType;

				}

				return light;

		}

	}
```
</details>

##### `_initLibrary(): Promise<void>`

<details><summary>Code</summary>

```ts
_initLibrary() {

		if ( ! this.libraryPending ) {

			// Load rhino3dm wrapper.
			const jsLoader = new FileLoader( this.manager );
			jsLoader.setPath( this.libraryPath );
			const jsContent = new Promise( ( resolve, reject ) => {

				jsLoader.load( 'rhino3dm.js', resolve, undefined, reject );

			} );

			// Load rhino3dm WASM binary.
			const binaryLoader = new FileLoader( this.manager );
			binaryLoader.setPath( this.libraryPath );
			binaryLoader.setResponseType( 'arraybuffer' );
			const binaryContent = new Promise( ( resolve, reject ) => {

				binaryLoader.load( 'rhino3dm.wasm', resolve, undefined, reject );

			} );

			this.libraryPending = Promise.all( [ jsContent, binaryContent ] )
				.then( ( [ jsContent, binaryContent ] ) => {

					//this.libraryBinary = binaryContent;
					this.libraryConfig.wasmBinary = binaryContent;

					const fn = Rhino3dmWorker.toString();

					const body = [
						'/* rhino3dm.js */',
						jsContent,
						'/* worker */',
						fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
					].join( '\n' );

					this.workerSourceURL = URL.createObjectURL( new Blob( [ body ] ) );

				} );

		}

		return this.libraryPending;

	}
```
</details>

##### `_getWorker(taskCost: any): Promise<any>`

<details><summary>Code</summary>

```ts
_getWorker( taskCost ) {

		return this._initLibrary().then( () => {

			if ( this.workerPool.length < this.workerLimit ) {

				const worker = new Worker( this.workerSourceURL );

				worker._callbacks = {};
				worker._taskCosts = {};
				worker._taskLoad = 0;

				worker.postMessage( {
					type: 'init',
					libraryConfig: this.libraryConfig
				} );

				worker.onmessage = e => {

					const message = e.data;

					switch ( message.type ) {

						case 'warning':
							this.warnings.push( message.data );
							console.warn( message.data );
							break;

						case 'decode':
							worker._callbacks[ message.id ].resolve( message );
							break;

						case 'error':
							worker._callbacks[ message.id ].reject( message );
							break;

						default:
							console.error( 'THREE.Rhino3dmLoader: Unexpected message, "' + message.type + '"' );

					}

				};

				this.workerPool.push( worker );

			} else {

				this.workerPool.sort( function ( a, b ) {

					return a._taskLoad > b._taskLoad ? - 1 : 1;

				} );

			}

			const worker = this.workerPool[ this.workerPool.length - 1 ];

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

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		for ( let i = 0; i < this.workerPool.length; ++ i ) {

			this.workerPool[ i ].terminate();

		}

		this.workerPool.length = 0;

	}
```
</details>


---