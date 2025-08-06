[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Loader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 82 |
| ⚡ Async/Await Patterns | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Loader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TGALoader` | `three/addons/loaders/TGALoader.js` |
| `AddObjectCommand` | `./commands/AddObjectCommand.js` |
| `LoaderUtils` | `./LoaderUtils.js` |
| `unzipSync` | `three/addons/libs/fflate.module.js` |
| `strFromU8` | `three/addons/libs/fflate.module.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `manager` | `any` | let/var | `new THREE.LoadingManager()` | ✗ |
| `file` | `any` | let/var | `filesMap[ url ]` | ✗ |
| `filename` | `any` | let/var | `file.name` | ✗ |
| `reader` | `FileReader` | let/var | `new FileReader()` | ✗ |
| `size` | `string` | let/var | `'(' + editor.utils.formatNumber( Math.floor( event.total / 1000 ) ) + ' KB)'` | ✗ |
| `progress` | `string` | let/var | `Math.floor( ( event.loaded / event.total ) * 100 ) + '%'` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `loader` | `any` | let/var | `new Rhino3dmLoader()` | ✗ |
| `loader` | `any` | let/var | `new TDSLoader()` | ✗ |
| `loader` | `any` | let/var | `new ThreeMFLoader()` | ✗ |
| `loader` | `any` | let/var | `new AMFLoader()` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `loader` | `any` | let/var | `new ColladaLoader( manager )` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `loader` | `any` | let/var | `new DRACOLoader()` | ✗ |
| `object` | `any` | let/var | `*not shown*` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshStandardMaterial()` | ✗ |
| `material` | `any` | let/var | `new THREE.PointsMaterial( { size: 0.01 } )` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `loader` | `any` | let/var | `new FBXLoader( manager )` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `loader` | `any` | let/var | `await createGLTFLoader()` | ✗ |
| `scene` | `any` | let/var | `result.scene` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `loader` | `any` | let/var | `await createGLTFLoader( manager )` | ✗ |
| `scene` | `any` | let/var | `result.scene` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `blob` | `Blob` | let/var | `new Blob( [ contents ], { type: 'text/javascript' } )` | ✗ |
| `worker` | `Worker` | let/var | `new Worker( url )` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `loader` | `any` | let/var | `new KMZLoader()` | ✗ |
| `loader` | `any` | let/var | `new LDrawLoader()` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshStandardMaterial()` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `object` | `any` | let/var | `*not shown*` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshStandardMaterial()` | ✗ |
| `material` | `any` | let/var | `new THREE.PointsMaterial( { size: 0.01 } )` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshStandardMaterial()` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `loader` | `any` | let/var | `new SVGLoader()` | ✗ |
| `paths` | `any` | let/var | `loader.parse( contents ).paths` | ✗ |
| `group` | `any` | let/var | `new THREE.Group()` | ✗ |
| `path` | `any` | let/var | `paths[ i ]` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshBasicMaterial( { color: path.color, depthWrite: false } )` | ✗ |
| `shape` | `any` | let/var | `shapes[ j ]` | ✗ |
| `geometry` | `any` | let/var | `new THREE.ShapeGeometry( shape )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `group` | `any` | let/var | `new THREE.Group()` | ✗ |
| `chunk` | `any` | let/var | `chunks[ i ]` | ✗ |
| `mesh` | `any` | let/var | `new VOXMesh( chunk )` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshStandardMaterial()` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `contents` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `material` | `any` | let/var | `new THREE.PointsMaterial()` | ✗ |
| `points` | `any` | let/var | `new THREE.Points( geometry, material )` | ✗ |
| `loader` | `any` | let/var | `new THREE.BufferGeometryLoader()` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( result )` | ✗ |
| `loader` | `any` | let/var | `new THREE.ObjectLoader()` | ✗ |
| `manager` | `any` | let/var | `new THREE.LoadingManager()` | ✗ |
| `file` | `any` | let/var | `zip[ url ]` | ✗ |
| `blob` | `Blob` | let/var | `new Blob( [ file.buffer ], { type: 'application/octet-stream' } )` | ✗ |
| `file` | `any` | let/var | `zip[ path ]` | ✗ |
| `loader` | `any` | let/var | `new FBXLoader( manager )` | ✗ |
| `loader` | `any` | let/var | `await createGLTFLoader()` | ✗ |
| `scene` | `any` | let/var | `result.scene` | ✗ |
| `loader` | `any` | let/var | `await createGLTFLoader( manager )` | ✗ |
| `scene` | `any` | let/var | `result.scene` | ✗ |
| `dracoLoader` | `any` | let/var | `new DRACOLoader()` | ✗ |
| `ktx2Loader` | `any` | let/var | `new KTX2Loader( manager )` | ✗ |
| `loader` | `any` | let/var | `new GLTFLoader( manager )` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| await-expression | `Loader` | import( 'three/addons/loaders/3DMLoader.js' ), import( 'three/addons/loaders/TDSLoader.js' ), import( 'three/addons/loaders/3MFLoader.js' ), import( 'three/addons/loaders/AMFLoader.js' ), import( 'three/addons/loaders/ColladaLoader.js' ), import( 'three/addons/loaders/DRACOLoader.js' ), import( 'three/addons/loaders/FBXLoader.js' ), createGLTFLoader(), createGLTFLoader( manager ), import( 'three/addons/loaders/KMZLoader.js' ), import( 'three/addons/loaders/LDrawLoader.js' ), import( 'three/addons/loaders/MD2Loader.js' ), import( 'three/addons/loaders/OBJLoader.js' ), import( 'three/addons/loaders/PCDLoader.js' ), import( 'three/addons/loaders/PLYLoader.js' ), import( 'three/addons/loaders/STLLoader.js' ), import( 'three/addons/loaders/SVGLoader.js' ), import( 'three/addons/loaders/USDLoader.js' ), import( 'three/addons/loaders/USDLoader.js' ), import( 'three/addons/loaders/VOXLoader.js' ), import( 'three/addons/loaders/VTKLoader.js' ), import( 'three/addons/loaders/VRMLLoader.js' ), import( 'three/addons/loaders/XYZLoader.js' ), import( 'three/addons/loaders/MTLLoader.js' ), import( 'three/addons/loaders/OBJLoader.js' ), import( 'three/addons/loaders/FBXLoader.js' ), createGLTFLoader(), createGLTFLoader( manager ), import( 'three/addons/loaders/GLTFLoader.js' ), import( 'three/addons/loaders/DRACOLoader.js' ), import( 'three/addons/loaders/KTX2Loader.js' ), import( 'three/addons/libs/meshopt_decoder.module.js' ) | *none* |
| async-function | `handleZIP` | import( 'three/addons/loaders/MTLLoader.js' ), import( 'three/addons/loaders/OBJLoader.js' ), import( 'three/addons/loaders/FBXLoader.js' ), createGLTFLoader(), createGLTFLoader( manager ) | *none* |
| async-function | `createGLTFLoader` | import( 'three/addons/loaders/GLTFLoader.js' ), import( 'three/addons/loaders/DRACOLoader.js' ), import( 'three/addons/loaders/KTX2Loader.js' ), import( 'three/addons/libs/meshopt_decoder.module.js' ) | *none* |


---

## Functions

### `Loader(editor: any): void`

**Parameters:**

- **`editor`** `any`

**Returns:** `void`

**Calls:**

- `LoaderUtils.getFilesFromItemList`
- `scope.loadFiles`
- `LoaderUtils.createFilesMap`
- `manager.setURLModifier`
- `url.replace`
- `console.log`
- `URL.createObjectURL`
- `manager.addHandler`
- `scope.loadFile`
- `filename.split( '.' ).pop().toLowerCase`
- `reader.addEventListener`
- `editor.utils.formatNumber`
- `Math.floor`
- `complex_call_1828`
- `loader.setLibraryPath`
- `loader.parse`
- `editor.execute`
- `console.error`
- `reader.readAsArrayBuffer`
- `complex_call_2395`
- `complex_call_2799`
- `complex_call_3203`
- `complex_call_3657`
- `reader.readAsText`
- `complex_call_4147`
- `loader.setDecoderPath`
- `geometry.hasAttribute`
- `loader.dispose`
- `complex_call_5139`
- `createGLTFLoader`
- `scene.animations.push`
- `loader.dracoLoader.dispose`
- `loader.ktx2Loader.dispose`
- `contents.indexOf`
- `handleJSON`
- `worker.postMessage`
- `Date.now`
- `JSON.parse`
- `alert`
- `complex_call_7507`
- `complex_call_7969`
- `loader.setPath`
- `complex_call_8630`
- `new MD2Loader().parse`
- `mesh.animations.push`
- `complex_call_9280`
- `new OBJLoader().parse`
- `complex_call_9707`
- `new PCDLoader().parse`
- `complex_call_10141`
- `new PLYLoader().parse`
- `complex_call_10987`
- `new STLLoader().parse`
- `reader.readAsBinaryString`
- `complex_call_11650`
- `group.scale.multiplyScalar`
- `SVGLoader.createShapes`
- `group.add`
- `complex_call_12725`
- `new USDLoader().parse`
- `complex_call_13166`
- `complex_call_13606`
- `new VOXLoader().parse`
- `complex_call_14252`
- `new VTKLoader().parse`
- `complex_call_14798`
- `new VRMLLoader().parse`
- `complex_call_15198`
- `new XYZLoader().parse`
- `handleZIP`
- `data.metadata.type.toLowerCase`
- `loader.setResourcePath`
- `editor.fromJSON`
- `unzipSync (from three/addons/libs/fflate.module.js)`
- `complex_call_17526`
- `complex_call_17604`
- `new MTLLoader( manager ).parse`
- `strFromU8 (from three/addons/libs/fflate.module.js)`
- `new OBJLoader().setMaterials( materials ).parse`
- `path.split( '.' ).pop().toLowerCase`
- `complex_call_18137`
- `complex_call_19244`
- `complex_call_19324`
- `complex_call_19404`
- `complex_call_19487`
- `dracoLoader.setDecoderPath`
- `ktx2Loader.setTranscoderPath`
- `editor.signals.rendererDetectKTX2Support.dispatch`
- `loader.setDRACOLoader`
- `loader.setKTX2Loader`
- `loader.setMeshoptDecoder`

**Internal Comments:**
```
// 2.0
// >= 3.0 (x2)
// Convert from LDraw coordinates: rotate 180 degrees around OX (x5)
// (x3)
// Poly
```

<details><summary>Code</summary>

```typescript
function Loader( editor ) {

	const scope = this;

	this.texturePath = '';

	this.loadItemList = function ( items ) {

		LoaderUtils.getFilesFromItemList( items, function ( files, filesMap ) {

			scope.loadFiles( files, filesMap );

		} );

	};

	this.loadFiles = function ( files, filesMap ) {

		if ( files.length > 0 ) {

			filesMap = filesMap || LoaderUtils.createFilesMap( files );

			const manager = new THREE.LoadingManager();
			manager.setURLModifier( function ( url ) {

				url = url.replace( /^(\.?\/)/, '' ); // remove './'

				const file = filesMap[ url ];

				if ( file ) {

					console.log( 'Loading', url );

					return URL.createObjectURL( file );

				}

				return url;

			} );

			manager.addHandler( /\.tga$/i, new TGALoader() );

			for ( let i = 0; i < files.length; i ++ ) {

				scope.loadFile( files[ i ], manager );

			}

		}

	};

	this.loadFile = function ( file, manager ) {

		const filename = file.name;
		const extension = filename.split( '.' ).pop().toLowerCase();

		const reader = new FileReader();
		reader.addEventListener( 'progress', function ( event ) {

			const size = '(' + editor.utils.formatNumber( Math.floor( event.total / 1000 ) ) + ' KB)';
			const progress = Math.floor( ( event.loaded / event.total ) * 100 ) + '%';

			console.log( 'Loading', filename, size, progress );

		} );

		switch ( extension ) {

			case '3dm':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { Rhino3dmLoader } = await import( 'three/addons/loaders/3DMLoader.js' );

					const loader = new Rhino3dmLoader();
					loader.setLibraryPath( '../examples/jsm/libs/rhino3dm/' );
					loader.parse( contents, function ( object ) {

						object.name = filename;

						editor.execute( new AddObjectCommand( editor, object ) );

					}, function ( error ) {

						console.error( error );

					} );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case '3ds':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const { TDSLoader } = await import( 'three/addons/loaders/TDSLoader.js' );

					const loader = new TDSLoader();
					const object = loader.parse( event.target.result );

					editor.execute( new AddObjectCommand( editor, object ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case '3mf':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const { ThreeMFLoader } = await import( 'three/addons/loaders/3MFLoader.js' );

					const loader = new ThreeMFLoader();
					const object = loader.parse( event.target.result );

					editor.execute( new AddObjectCommand( editor, object ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'amf':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const { AMFLoader } = await import( 'three/addons/loaders/AMFLoader.js' );

					const loader = new AMFLoader();
					const amfobject = loader.parse( event.target.result );

					editor.execute( new AddObjectCommand( editor, amfobject ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'dae':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { ColladaLoader } = await import( 'three/addons/loaders/ColladaLoader.js' );

					const loader = new ColladaLoader( manager );
					const collada = loader.parse( contents );

					collada.scene.name = filename;

					editor.execute( new AddObjectCommand( editor, collada.scene ) );

				}, false );
				reader.readAsText( file );

				break;

			}

			case 'drc':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { DRACOLoader } = await import( 'three/addons/loaders/DRACOLoader.js' );

					const loader = new DRACOLoader();
					loader.setDecoderPath( '../examples/jsm/libs/draco/' );
					loader.parse( contents, function ( geometry ) {

						let object;

						if ( geometry.index !== null ) {

							const material = new THREE.MeshStandardMaterial();

							object = new THREE.Mesh( geometry, material );
							object.name = filename;

						} else {

							const material = new THREE.PointsMaterial( { size: 0.01 } );
							material.vertexColors = geometry.hasAttribute( 'color' );

							object = new THREE.Points( geometry, material );
							object.name = filename;

						}

						loader.dispose();
						editor.execute( new AddObjectCommand( editor, object ) );

					} );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'fbx':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { FBXLoader } = await import( 'three/addons/loaders/FBXLoader.js' );

					const loader = new FBXLoader( manager );
					const object = loader.parse( contents );

					editor.execute( new AddObjectCommand( editor, object ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'glb':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const loader = await createGLTFLoader();

					loader.parse( contents, '', function ( result ) {

						const scene = result.scene;
						scene.name = filename;

						scene.animations.push( ...result.animations );
						editor.execute( new AddObjectCommand( editor, scene ) );

						loader.dracoLoader.dispose();
						loader.ktx2Loader.dispose();

					} );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'gltf':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const loader = await createGLTFLoader( manager );

					loader.parse( contents, '', function ( result ) {

						const scene = result.scene;
						scene.name = filename;

						scene.animations.push( ...result.animations );
						editor.execute( new AddObjectCommand( editor, scene ) );

						loader.dracoLoader.dispose();
						loader.ktx2Loader.dispose();

					} );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'js':
			case 'json':

			{

				reader.addEventListener( 'load', function ( event ) {

					const contents = event.target.result;

					// 2.0

					if ( contents.indexOf( 'postMessage' ) !== - 1 ) {

						const blob = new Blob( [ contents ], { type: 'text/javascript' } );
						const url = URL.createObjectURL( blob );

						const worker = new Worker( url );

						worker.onmessage = function ( event ) {

							event.data.metadata = { version: 2 };
							handleJSON( event.data );

						};

						worker.postMessage( Date.now() );

						return;

					}

					// >= 3.0

					let data;

					try {

						data = JSON.parse( contents );

					} catch ( error ) {

						alert( error );
						return;

					}

					handleJSON( data );

				}, false );
				reader.readAsText( file );

				break;

			}

			case 'kmz':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const { KMZLoader } = await import( 'three/addons/loaders/KMZLoader.js' );

					const loader = new KMZLoader();
					const collada = loader.parse( event.target.result );

					collada.scene.name = filename;

					editor.execute( new AddObjectCommand( editor, collada.scene ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'ldr':
			case 'mpd':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const { LDrawLoader } = await import( 'three/addons/loaders/LDrawLoader.js' );

					const loader = new LDrawLoader();
					loader.setPath( '../../examples/models/ldraw/officialLibrary/' );
					loader.parse( event.target.result, function ( group ) {

						group.name = filename;
						// Convert from LDraw coordinates: rotate 180 degrees around OX
						group.rotation.x = Math.PI;

						editor.execute( new AddObjectCommand( editor, group ) );

					} );

				}, false );
				reader.readAsText( file );

				break;

			}

			case 'md2':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { MD2Loader } = await import( 'three/addons/loaders/MD2Loader.js' );

					const geometry = new MD2Loader().parse( contents );
					const material = new THREE.MeshStandardMaterial();

					const mesh = new THREE.Mesh( geometry, material );
					mesh.mixer = new THREE.AnimationMixer( mesh );
					mesh.name = filename;

					mesh.animations.push( ...geometry.animations );
					editor.execute( new AddObjectCommand( editor, mesh ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'obj':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { OBJLoader } = await import( 'three/addons/loaders/OBJLoader.js' );

					const object = new OBJLoader().parse( contents );
					object.name = filename;

					editor.execute( new AddObjectCommand( editor, object ) );

				}, false );
				reader.readAsText( file );

				break;

			}

			case 'pcd':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { PCDLoader } = await import( 'three/addons/loaders/PCDLoader.js' );

					const points = new PCDLoader().parse( contents );
					points.name = filename;

					editor.execute( new AddObjectCommand( editor, points ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'ply':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { PLYLoader } = await import( 'three/addons/loaders/PLYLoader.js' );

					const geometry = new PLYLoader().parse( contents );
					let object;

					if ( geometry.index !== null ) {

						const material = new THREE.MeshStandardMaterial();

						object = new THREE.Mesh( geometry, material );
						object.name = filename;

					} else {

						const material = new THREE.PointsMaterial( { size: 0.01 } );
						material.vertexColors = geometry.hasAttribute( 'color' );

						object = new THREE.Points( geometry, material );
						object.name = filename;

					}

					editor.execute( new AddObjectCommand( editor, object ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'stl':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { STLLoader } = await import( 'three/addons/loaders/STLLoader.js' );

					const geometry = new STLLoader().parse( contents );
					const material = new THREE.MeshStandardMaterial();

					const mesh = new THREE.Mesh( geometry, material );
					mesh.name = filename;

					editor.execute( new AddObjectCommand( editor, mesh ) );

				}, false );

				if ( reader.readAsBinaryString !== undefined ) {

					reader.readAsBinaryString( file );

				} else {

					reader.readAsArrayBuffer( file );

				}

				break;

			}

			case 'svg':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { SVGLoader } = await import( 'three/addons/loaders/SVGLoader.js' );

					const loader = new SVGLoader();
					const paths = loader.parse( contents ).paths;

					//

					const group = new THREE.Group();
					group.name = filename;
					group.scale.multiplyScalar( 0.1 );
					group.scale.y *= - 1;

					for ( let i = 0; i < paths.length; i ++ ) {

						const path = paths[ i ];

						const material = new THREE.MeshBasicMaterial( {
							color: path.color,
							depthWrite: false
						} );

						const shapes = SVGLoader.createShapes( path );

						for ( let j = 0; j < shapes.length; j ++ ) {

							const shape = shapes[ j ];

							const geometry = new THREE.ShapeGeometry( shape );
							const mesh = new THREE.Mesh( geometry, material );

							group.add( mesh );

						}

					}

					editor.execute( new AddObjectCommand( editor, group ) );

				}, false );
				reader.readAsText( file );

				break;

			}

			case 'usda':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { USDLoader } = await import( 'three/addons/loaders/USDLoader.js' );

					const group = new USDLoader().parse( contents );
					group.name = filename;

					editor.execute( new AddObjectCommand( editor, group ) );

				}, false );
				reader.readAsText( file );

				break;

			}

			case 'usdc':
			case 'usdz':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { USDLoader } = await import( 'three/addons/loaders/USDLoader.js' );

					const group = new USDLoader().parse( contents );
					group.name = filename;

					editor.execute( new AddObjectCommand( editor, group ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'vox':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { VOXLoader, VOXMesh } = await import( 'three/addons/loaders/VOXLoader.js' );

					const chunks = new VOXLoader().parse( contents );

					const group = new THREE.Group();
					group.name = filename;

					for ( let i = 0; i < chunks.length; i ++ ) {

						const chunk = chunks[ i ];

						const mesh = new VOXMesh( chunk );
						group.add( mesh );

					}

					editor.execute( new AddObjectCommand( editor, group ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'vtk':
			case 'vtp':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { VTKLoader } = await import( 'three/addons/loaders/VTKLoader.js' );

					const geometry = new VTKLoader().parse( contents );
					const material = new THREE.MeshStandardMaterial();

					const mesh = new THREE.Mesh( geometry, material );
					mesh.name = filename;

					editor.execute( new AddObjectCommand( editor, mesh ) );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			case 'wrl':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { VRMLLoader } = await import( 'three/addons/loaders/VRMLLoader.js' );

					const result = new VRMLLoader().parse( contents );

					editor.execute( new AddObjectCommand( editor, result ) );

				}, false );
				reader.readAsText( file );

				break;

			}

			case 'xyz':

			{

				reader.addEventListener( 'load', async function ( event ) {

					const contents = event.target.result;

					const { XYZLoader } = await import( 'three/addons/loaders/XYZLoader.js' );

					const geometry = new XYZLoader().parse( contents );

					const material = new THREE.PointsMaterial();
					material.vertexColors = geometry.hasAttribute( 'color' );

					const points = new THREE.Points( geometry, material );
					points.name = filename;

					editor.execute( new AddObjectCommand( editor, points ) );

				}, false );
				reader.readAsText( file );

				break;

			}

			case 'zip':

			{

				reader.addEventListener( 'load', function ( event ) {

					handleZIP( event.target.result );

				}, false );
				reader.readAsArrayBuffer( file );

				break;

			}

			default:

				console.error( 'Unsupported file format (' + extension + ').' );

				break;

		}

	};

	function handleJSON( data ) {

		if ( data.metadata === undefined ) { // 2.0

			data.metadata = { type: 'Geometry' };

		}

		if ( data.metadata.type === undefined ) { // 3.0

			data.metadata.type = 'Geometry';

		}

		if ( data.metadata.formatVersion !== undefined ) {

			data.metadata.version = data.metadata.formatVersion;

		}

		switch ( data.metadata.type.toLowerCase() ) {

			case 'buffergeometry':

			{

				const loader = new THREE.BufferGeometryLoader();
				const result = loader.parse( data );

				const mesh = new THREE.Mesh( result );

				editor.execute( new AddObjectCommand( editor, mesh ) );

				break;

			}

			case 'geometry':

				console.error( 'Loader: "Geometry" is no longer supported.' );

				break;

			case 'object':

			{

				const loader = new THREE.ObjectLoader();
				loader.setResourcePath( scope.texturePath );

				loader.parse( data, function ( result ) {

					editor.execute( new AddObjectCommand( editor, result ) );

				} );

				break;

			}

			case 'app':

				editor.fromJSON( data );

				break;

		}

	}

	async function handleZIP( contents ) {

		const zip = unzipSync( new Uint8Array( contents ) );

		const manager = new THREE.LoadingManager();
		manager.setURLModifier( function ( url ) {

			const file = zip[ url ];

			if ( file ) {

				console.log( 'Loading', url );

				const blob = new Blob( [ file.buffer ], { type: 'application/octet-stream' } );
				return URL.createObjectURL( blob );

			}

			return url;

		} );

		// Poly

		if ( zip[ 'model.obj' ] && zip[ 'materials.mtl' ] ) {

			const { MTLLoader } = await import( 'three/addons/loaders/MTLLoader.js' );
			const { OBJLoader } = await import( 'three/addons/loaders/OBJLoader.js' );

			const materials = new MTLLoader( manager ).parse( strFromU8( zip[ 'materials.mtl' ] ) );
			const object = new OBJLoader().setMaterials( materials ).parse( strFromU8( zip[ 'model.obj' ] ) );

			editor.execute( new AddObjectCommand( editor, object ) );
			return;

		}

		//

		for ( const path in zip ) {

			const file = zip[ path ];

			const extension = path.split( '.' ).pop().toLowerCase();

			switch ( extension ) {

				case 'fbx':

				{

					const { FBXLoader } = await import( 'three/addons/loaders/FBXLoader.js' );

					const loader = new FBXLoader( manager );
					const object = loader.parse( file.buffer );

					editor.execute( new AddObjectCommand( editor, object ) );

					break;

				}

				case 'glb':

				{

					const loader = await createGLTFLoader();

					loader.parse( file.buffer, '', function ( result ) {

						const scene = result.scene;

						scene.animations.push( ...result.animations );
						editor.execute( new AddObjectCommand( editor, scene ) );

						loader.dracoLoader.dispose();
						loader.ktx2Loader.dispose();

					} );

					break;

				}

				case 'gltf':

				{

					const loader = await createGLTFLoader( manager );

					loader.parse( strFromU8( file ), '', function ( result ) {

						const scene = result.scene;

						scene.animations.push( ...result.animations );
						editor.execute( new AddObjectCommand( editor, scene ) );

						loader.dracoLoader.dispose();
						loader.ktx2Loader.dispose();

					} );

					break;

				}

			}

		}

	}

	async function createGLTFLoader( manager ) {

		const { GLTFLoader } = await import( 'three/addons/loaders/GLTFLoader.js' );
		const { DRACOLoader } = await import( 'three/addons/loaders/DRACOLoader.js' );
		const { KTX2Loader } = await import( 'three/addons/loaders/KTX2Loader.js' );
		const { MeshoptDecoder } = await import( 'three/addons/libs/meshopt_decoder.module.js' );

		const dracoLoader = new DRACOLoader();
		dracoLoader.setDecoderPath( '../examples/jsm/libs/draco/gltf/' );

		const ktx2Loader = new KTX2Loader( manager );
		ktx2Loader.setTranscoderPath( '../examples/jsm/libs/basis/' );

		editor.signals.rendererDetectKTX2Support.dispatch( ktx2Loader );

		const loader = new GLTFLoader( manager );
		loader.setDRACOLoader( dracoLoader );
		loader.setKTX2Loader( ktx2Loader );
		loader.setMeshoptDecoder( MeshoptDecoder );

		return loader;

	}

}
```
</details>

### `handleJSON(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `data.metadata.type.toLowerCase`
- `loader.parse`
- `editor.execute`
- `console.error`
- `loader.setResourcePath`
- `editor.fromJSON`

<details><summary>Code</summary>

```typescript
function handleJSON( data ) {

		if ( data.metadata === undefined ) { // 2.0

			data.metadata = { type: 'Geometry' };

		}

		if ( data.metadata.type === undefined ) { // 3.0

			data.metadata.type = 'Geometry';

		}

		if ( data.metadata.formatVersion !== undefined ) {

			data.metadata.version = data.metadata.formatVersion;

		}

		switch ( data.metadata.type.toLowerCase() ) {

			case 'buffergeometry':

			{

				const loader = new THREE.BufferGeometryLoader();
				const result = loader.parse( data );

				const mesh = new THREE.Mesh( result );

				editor.execute( new AddObjectCommand( editor, mesh ) );

				break;

			}

			case 'geometry':

				console.error( 'Loader: "Geometry" is no longer supported.' );

				break;

			case 'object':

			{

				const loader = new THREE.ObjectLoader();
				loader.setResourcePath( scope.texturePath );

				loader.parse( data, function ( result ) {

					editor.execute( new AddObjectCommand( editor, result ) );

				} );

				break;

			}

			case 'app':

				editor.fromJSON( data );

				break;

		}

	}
```
</details>

### `handleZIP(contents: any): Promise<void>`

**Parameters:**

- **`contents`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `unzipSync (from three/addons/libs/fflate.module.js)`
- `manager.setURLModifier`
- `console.log`
- `URL.createObjectURL`
- `complex_call_17526`
- `complex_call_17604`
- `new MTLLoader( manager ).parse`
- `strFromU8 (from three/addons/libs/fflate.module.js)`
- `new OBJLoader().setMaterials( materials ).parse`
- `editor.execute`
- `path.split( '.' ).pop().toLowerCase`
- `complex_call_18137`
- `loader.parse`
- `createGLTFLoader`
- `scene.animations.push`
- `loader.dracoLoader.dispose`
- `loader.ktx2Loader.dispose`

**Internal Comments:**
```
// Poly
//
```

<details><summary>Code</summary>

```typescript
async function handleZIP( contents ) {

		const zip = unzipSync( new Uint8Array( contents ) );

		const manager = new THREE.LoadingManager();
		manager.setURLModifier( function ( url ) {

			const file = zip[ url ];

			if ( file ) {

				console.log( 'Loading', url );

				const blob = new Blob( [ file.buffer ], { type: 'application/octet-stream' } );
				return URL.createObjectURL( blob );

			}

			return url;

		} );

		// Poly

		if ( zip[ 'model.obj' ] && zip[ 'materials.mtl' ] ) {

			const { MTLLoader } = await import( 'three/addons/loaders/MTLLoader.js' );
			const { OBJLoader } = await import( 'three/addons/loaders/OBJLoader.js' );

			const materials = new MTLLoader( manager ).parse( strFromU8( zip[ 'materials.mtl' ] ) );
			const object = new OBJLoader().setMaterials( materials ).parse( strFromU8( zip[ 'model.obj' ] ) );

			editor.execute( new AddObjectCommand( editor, object ) );
			return;

		}

		//

		for ( const path in zip ) {

			const file = zip[ path ];

			const extension = path.split( '.' ).pop().toLowerCase();

			switch ( extension ) {

				case 'fbx':

				{

					const { FBXLoader } = await import( 'three/addons/loaders/FBXLoader.js' );

					const loader = new FBXLoader( manager );
					const object = loader.parse( file.buffer );

					editor.execute( new AddObjectCommand( editor, object ) );

					break;

				}

				case 'glb':

				{

					const loader = await createGLTFLoader();

					loader.parse( file.buffer, '', function ( result ) {

						const scene = result.scene;

						scene.animations.push( ...result.animations );
						editor.execute( new AddObjectCommand( editor, scene ) );

						loader.dracoLoader.dispose();
						loader.ktx2Loader.dispose();

					} );

					break;

				}

				case 'gltf':

				{

					const loader = await createGLTFLoader( manager );

					loader.parse( strFromU8( file ), '', function ( result ) {

						const scene = result.scene;

						scene.animations.push( ...result.animations );
						editor.execute( new AddObjectCommand( editor, scene ) );

						loader.dracoLoader.dispose();
						loader.ktx2Loader.dispose();

					} );

					break;

				}

			}

		}

	}
```
</details>

### `createGLTFLoader(manager: any): Promise<any>`

**Parameters:**

- **`manager`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `complex_call_19244`
- `complex_call_19324`
- `complex_call_19404`
- `complex_call_19487`
- `dracoLoader.setDecoderPath`
- `ktx2Loader.setTranscoderPath`
- `editor.signals.rendererDetectKTX2Support.dispatch`
- `loader.setDRACOLoader`
- `loader.setKTX2Loader`
- `loader.setMeshoptDecoder`

<details><summary>Code</summary>

```typescript
async function createGLTFLoader( manager ) {

		const { GLTFLoader } = await import( 'three/addons/loaders/GLTFLoader.js' );
		const { DRACOLoader } = await import( 'three/addons/loaders/DRACOLoader.js' );
		const { KTX2Loader } = await import( 'three/addons/loaders/KTX2Loader.js' );
		const { MeshoptDecoder } = await import( 'three/addons/libs/meshopt_decoder.module.js' );

		const dracoLoader = new DRACOLoader();
		dracoLoader.setDecoderPath( '../examples/jsm/libs/draco/gltf/' );

		const ktx2Loader = new KTX2Loader( manager );
		ktx2Loader.setTranscoderPath( '../examples/jsm/libs/basis/' );

		editor.signals.rendererDetectKTX2Support.dispatch( ktx2Loader );

		const loader = new GLTFLoader( manager );
		loader.setDRACOLoader( dracoLoader );
		loader.setKTX2Loader( ktx2Loader );
		loader.setMeshoptDecoder( MeshoptDecoder );

		return loader;

	}
```
</details>


---