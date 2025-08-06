[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AMFLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 58 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/AMFLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Group` | `three` |
| `Loader` | `three` |
| `Mesh` | `three` |
| `MeshPhongMaterial` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `view` | `DataView<any>` | let/var | `new DataView( data )` | ✗ |
| `zip` | `any` | let/var | `null` | ✗ |
| `file` | `any` | let/var | `null` | ✗ |
| `scale` | `number` | let/var | `1.0` | ✗ |
| `unit` | `string` | let/var | `'millimeter'` | ✗ |
| `scaleUnits` | `{ millimeter: number; inch: number; f...` | let/var | `{ millimeter: 1.0, inch: 25.4, feet: 304.8, meter: 1000.0, micron: 0.001 }` | ✗ |
| `matName` | `string` | let/var | `'AMF Material'` | ✗ |
| `matId` | `any` | let/var | `node.attributes.id.textContent` | ✗ |
| `color` | `{ r: number; g: number; b: number; a:...` | let/var | `{ r: 1.0, g: 1.0, b: 1.0, a: 1.0 }` | ✗ |
| `loadedMaterial` | `any` | let/var | `null` | ✗ |
| `matChildEl` | `any` | let/var | `node.childNodes[ i ]` | ✗ |
| `color` | `{ r: number; g: number; b: number; a:...` | let/var | `{ r: 1.0, g: 1.0, b: 1.0, a: 1.0 }` | ✗ |
| `matColor` | `any` | let/var | `node.childNodes[ i ]` | ✗ |
| `volume` | `{ name: string; triangles: any[]; mat...` | let/var | `{ name: '', triangles: [], materialId: null }` | ✗ |
| `currVolumeNode` | `any` | let/var | `node.firstElementChild` | ✗ |
| `v1` | `any` | let/var | `currVolumeNode.getElementsByTagName( 'v1' )[ 0 ].textContent` | ✗ |
| `v2` | `any` | let/var | `currVolumeNode.getElementsByTagName( 'v2' )[ 0 ].textContent` | ✗ |
| `v3` | `any` | let/var | `currVolumeNode.getElementsByTagName( 'v3' )[ 0 ].textContent` | ✗ |
| `vertArray` | `any[]` | let/var | `[]` | ✗ |
| `normalArray` | `any[]` | let/var | `[]` | ✗ |
| `currVerticesNode` | `any` | let/var | `node.firstElementChild` | ✗ |
| `vNode` | `any` | let/var | `currVerticesNode.firstElementChild` | ✗ |
| `x` | `any` | let/var | `vNode.getElementsByTagName( 'x' )[ 0 ].textContent` | ✗ |
| `y` | `any` | let/var | `vNode.getElementsByTagName( 'y' )[ 0 ].textContent` | ✗ |
| `z` | `any` | let/var | `vNode.getElementsByTagName( 'z' )[ 0 ].textContent` | ✗ |
| `nx` | `any` | let/var | `vNode.getElementsByTagName( 'nx' )[ 0 ].textContent` | ✗ |
| `ny` | `any` | let/var | `vNode.getElementsByTagName( 'ny' )[ 0 ].textContent` | ✗ |
| `nz` | `any` | let/var | `vNode.getElementsByTagName( 'nz' )[ 0 ].textContent` | ✗ |
| `objId` | `any` | let/var | `node.attributes.id.textContent` | ✗ |
| `loadedObject` | `{ name: string; meshes: any[]; }` | let/var | `{ name: 'amfobject', meshes: [] }` | ✗ |
| `currColor` | `any` | let/var | `null` | ✗ |
| `currObjNode` | `any` | let/var | `node.firstElementChild` | ✗ |
| `currMeshNode` | `any` | let/var | `currObjNode.firstElementChild` | ✗ |
| `mesh` | `{ vertices: any[]; normals: any[]; vo...` | let/var | `{ vertices: [], normals: [], volumes: [], color: currColor }` | ✗ |
| `amfName` | `string` | let/var | `''` | ✗ |
| `amfAuthor` | `string` | let/var | `''` | ✗ |
| `amfMaterials` | `{}` | let/var | `{}` | ✗ |
| `amfObjects` | `{}` | let/var | `{}` | ✗ |
| `childNodes` | `NodeListOf<ChildNode>` | let/var | `xmlData.documentElement.childNodes` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `child` | `ChildNode` | let/var | `childNodes[ i ]` | ✗ |
| `sceneObject` | `any` | let/var | `new Group()` | ✗ |
| `defaultMaterial` | `any` | let/var | `new MeshPhongMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, color: 0xaaaaff,...` | ✗ |
| `part` | `any` | let/var | `amfObjects[ id ]` | ✗ |
| `meshes` | `any` | let/var | `part.meshes` | ✗ |
| `newObject` | `any` | let/var | `new Group()` | ✗ |
| `objDefaultMaterial` | `any` | let/var | `defaultMaterial` | ✗ |
| `mesh` | `any` | let/var | `meshes[ i ]` | ✗ |
| `vertices` | `any` | let/var | `new Float32BufferAttribute( mesh.vertices, 3 )` | ✗ |
| `normals` | `any` | let/var | `null` | ✗ |
| `color` | `any` | let/var | `mesh.color` | ✗ |
| `volumes` | `any` | let/var | `mesh.volumes` | ✗ |
| `volume` | `any` | let/var | `volumes[ j ]` | ✗ |
| `newGeometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `any` | let/var | `objDefaultMaterial` | ✗ |


---

## Functions

### `AMFLoader.load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded AMF asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Group) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setResponseType`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `onLoad`
- `scope.parse`
- `onError`
- `console.error`
- `scope.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `AMFLoader.parse(data: ArrayBuffer): Group`

**JSDoc:**
```typescript
/**
	 * Parses the given AMF data and returns the resulting group.
	 *
	 * @param {ArrayBuffer} data - The raw AMF asset data as an array buffer.
	 * @return {Group} A group representing the parsed asset.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`

**Returns:** `Group`

**Calls:**

- `String.fromCharCode`
- `view.getUint8`
- `console.log`
- `fflate.unzipSync`
- `file.toLowerCase().slice`
- `new TextDecoder().decode`
- `new DOMParser().parseFromString`
- `xmlData.documentElement.nodeName.toLowerCase`
- `node.documentElement.attributes.unit.value.toLowerCase`
- `loadColor`
- `currVolumeNode.getElementsByTagName`
- `volume.triangles.push`
- `vNode.getElementsByTagName`
- `vertArray.push`
- `normalArray.push`
- `loadMeshVertices`
- `mesh.normals.concat`
- `mesh.vertices.concat`
- `mesh.volumes.push`
- `loadMeshVolume`
- `loadedObject.meshes.push`
- `loadDocument`
- `loadDocumentScale`
- `loadMaterials`
- `loadObject`
- `defaultMaterial.clone`
- `newGeometry.setIndex`
- `newGeometry.setAttribute`
- `vertices.clone`
- `normals.clone`
- `newGeometry.scale`
- `newObject.add`
- `material.clone`
- `sceneObject.add`

<details><summary>Code</summary>

```typescript
parse( data ) {

		function loadDocument( data ) {

			let view = new DataView( data );
			const magic = String.fromCharCode( view.getUint8( 0 ), view.getUint8( 1 ) );

			if ( magic === 'PK' ) {

				let zip = null;
				let file = null;

				console.log( 'THREE.AMFLoader: Loading Zip' );

				try {

					zip = fflate.unzipSync( new Uint8Array( data ) );

				} catch ( e ) {

					if ( e instanceof ReferenceError ) {

						console.log( 'THREE.AMFLoader: fflate missing and file is compressed.' );
						return null;

					}

				}

				for ( file in zip ) {

					if ( file.toLowerCase().slice( - 4 ) === '.amf' ) {

						break;

					}

				}

				console.log( 'THREE.AMFLoader: Trying to load file asset: ' + file );
				view = new DataView( zip[ file ].buffer );

			}

			const fileText = new TextDecoder().decode( view );
			const xmlData = new DOMParser().parseFromString( fileText, 'application/xml' );

			if ( xmlData.documentElement.nodeName.toLowerCase() !== 'amf' ) {

				console.log( 'THREE.AMFLoader: Error loading AMF - no AMF document found.' );
				return null;

			}

			return xmlData;

		}

		function loadDocumentScale( node ) {

			let scale = 1.0;
			let unit = 'millimeter';

			if ( node.documentElement.attributes.unit !== undefined ) {

				unit = node.documentElement.attributes.unit.value.toLowerCase();

			}

			const scaleUnits = {
				millimeter: 1.0,
				inch: 25.4,
				feet: 304.8,
				meter: 1000.0,
				micron: 0.001
			};

			if ( scaleUnits[ unit ] !== undefined ) {

				scale = scaleUnits[ unit ];

			}

			console.log( 'THREE.AMFLoader: Unit scale: ' + scale );
			return scale;

		}

		function loadMaterials( node ) {

			let matName = 'AMF Material';
			const matId = node.attributes.id.textContent;
			let color = { r: 1.0, g: 1.0, b: 1.0, a: 1.0 };

			let loadedMaterial = null;

			for ( let i = 0; i < node.childNodes.length; i ++ ) {

				const matChildEl = node.childNodes[ i ];

				if ( matChildEl.nodeName === 'metadata' && matChildEl.attributes.type !== undefined ) {

					if ( matChildEl.attributes.type.value === 'name' ) {

						matName = matChildEl.textContent;

					}

				} else if ( matChildEl.nodeName === 'color' ) {

					color = loadColor( matChildEl );

				}

			}

			loadedMaterial = new MeshPhongMaterial( {
				flatShading: true,
				color: new Color( color.r, color.g, color.b ),
				name: matName
			} );

			if ( color.a !== 1.0 ) {

				loadedMaterial.transparent = true;
				loadedMaterial.opacity = color.a;

			}

			return { id: matId, material: loadedMaterial };

		}

		function loadColor( node ) {

			const color = { r: 1.0, g: 1.0, b: 1.0, a: 1.0 };

			for ( let i = 0; i < node.childNodes.length; i ++ ) {

				const matColor = node.childNodes[ i ];

				if ( matColor.nodeName === 'r' ) {

					color.r = matColor.textContent;

				} else if ( matColor.nodeName === 'g' ) {

					color.g = matColor.textContent;

				} else if ( matColor.nodeName === 'b' ) {

					color.b = matColor.textContent;

				} else if ( matColor.nodeName === 'a' ) {

					color.a = matColor.textContent;

				}

			}

			return color;

		}

		function loadMeshVolume( node ) {

			const volume = { name: '', triangles: [], materialId: null };

			let currVolumeNode = node.firstElementChild;

			if ( node.attributes.materialid !== undefined ) {

				volume.materialId = node.attributes.materialid.nodeValue;

			}

			while ( currVolumeNode ) {

				if ( currVolumeNode.nodeName === 'metadata' ) {

					if ( currVolumeNode.attributes.type !== undefined ) {

						if ( currVolumeNode.attributes.type.value === 'name' ) {

							volume.name = currVolumeNode.textContent;

						}

					}

				} else if ( currVolumeNode.nodeName === 'triangle' ) {

					const v1 = currVolumeNode.getElementsByTagName( 'v1' )[ 0 ].textContent;
					const v2 = currVolumeNode.getElementsByTagName( 'v2' )[ 0 ].textContent;
					const v3 = currVolumeNode.getElementsByTagName( 'v3' )[ 0 ].textContent;

					volume.triangles.push( v1, v2, v3 );

				}

				currVolumeNode = currVolumeNode.nextElementSibling;

			}

			return volume;

		}

		function loadMeshVertices( node ) {

			const vertArray = [];
			const normalArray = [];
			let currVerticesNode = node.firstElementChild;

			while ( currVerticesNode ) {

				if ( currVerticesNode.nodeName === 'vertex' ) {

					let vNode = currVerticesNode.firstElementChild;

					while ( vNode ) {

						if ( vNode.nodeName === 'coordinates' ) {

							const x = vNode.getElementsByTagName( 'x' )[ 0 ].textContent;
							const y = vNode.getElementsByTagName( 'y' )[ 0 ].textContent;
							const z = vNode.getElementsByTagName( 'z' )[ 0 ].textContent;

							vertArray.push( x, y, z );

						} else if ( vNode.nodeName === 'normal' ) {

							const nx = vNode.getElementsByTagName( 'nx' )[ 0 ].textContent;
							const ny = vNode.getElementsByTagName( 'ny' )[ 0 ].textContent;
							const nz = vNode.getElementsByTagName( 'nz' )[ 0 ].textContent;

							normalArray.push( nx, ny, nz );

						}

						vNode = vNode.nextElementSibling;

					}

				}

				currVerticesNode = currVerticesNode.nextElementSibling;

			}

			return { 'vertices': vertArray, 'normals': normalArray };

		}

		function loadObject( node ) {

			const objId = node.attributes.id.textContent;
			const loadedObject = { name: 'amfobject', meshes: [] };
			let currColor = null;
			let currObjNode = node.firstElementChild;

			while ( currObjNode ) {

				if ( currObjNode.nodeName === 'metadata' ) {

					if ( currObjNode.attributes.type !== undefined ) {

						if ( currObjNode.attributes.type.value === 'name' ) {

							loadedObject.name = currObjNode.textContent;

						}

					}

				} else if ( currObjNode.nodeName === 'color' ) {

					currColor = loadColor( currObjNode );

				} else if ( currObjNode.nodeName === 'mesh' ) {

					let currMeshNode = currObjNode.firstElementChild;
					const mesh = { vertices: [], normals: [], volumes: [], color: currColor };

					while ( currMeshNode ) {

						if ( currMeshNode.nodeName === 'vertices' ) {

							const loadedVertices = loadMeshVertices( currMeshNode );

							mesh.normals = mesh.normals.concat( loadedVertices.normals );
							mesh.vertices = mesh.vertices.concat( loadedVertices.vertices );

						} else if ( currMeshNode.nodeName === 'volume' ) {

							mesh.volumes.push( loadMeshVolume( currMeshNode ) );

						}

						currMeshNode = currMeshNode.nextElementSibling;

					}

					loadedObject.meshes.push( mesh );

				}

				currObjNode = currObjNode.nextElementSibling;

			}

			return { 'id': objId, 'obj': loadedObject };

		}

		const xmlData = loadDocument( data );
		let amfName = '';
		let amfAuthor = '';
		const amfScale = loadDocumentScale( xmlData );
		const amfMaterials = {};
		const amfObjects = {};
		const childNodes = xmlData.documentElement.childNodes;

		let i, j;

		for ( i = 0; i < childNodes.length; i ++ ) {

			const child = childNodes[ i ];

			if ( child.nodeName === 'metadata' ) {

				if ( child.attributes.type !== undefined ) {

					if ( child.attributes.type.value === 'name' ) {

						amfName = child.textContent;

					} else if ( child.attributes.type.value === 'author' ) {

						amfAuthor = child.textContent;

					}

				}

			} else if ( child.nodeName === 'material' ) {

				const loadedMaterial = loadMaterials( child );

				amfMaterials[ loadedMaterial.id ] = loadedMaterial.material;

			} else if ( child.nodeName === 'object' ) {

				const loadedObject = loadObject( child );

				amfObjects[ loadedObject.id ] = loadedObject.obj;

			}

		}

		const sceneObject = new Group();
		const defaultMaterial = new MeshPhongMaterial( {
			name: Loader.DEFAULT_MATERIAL_NAME,
			color: 0xaaaaff,
			flatShading: true
		} );

		sceneObject.name = amfName;
		sceneObject.userData.author = amfAuthor;
		sceneObject.userData.loader = 'AMF';

		for ( const id in amfObjects ) {

			const part = amfObjects[ id ];
			const meshes = part.meshes;
			const newObject = new Group();
			newObject.name = part.name || '';

			for ( i = 0; i < meshes.length; i ++ ) {

				let objDefaultMaterial = defaultMaterial;
				const mesh = meshes[ i ];
				const vertices = new Float32BufferAttribute( mesh.vertices, 3 );
				let normals = null;

				if ( mesh.normals.length ) {

					normals = new Float32BufferAttribute( mesh.normals, 3 );

				}

				if ( mesh.color ) {

					const color = mesh.color;

					objDefaultMaterial = defaultMaterial.clone();
					objDefaultMaterial.color = new Color( color.r, color.g, color.b );

					if ( color.a !== 1.0 ) {

						objDefaultMaterial.transparent = true;
						objDefaultMaterial.opacity = color.a;

					}

				}

				const volumes = mesh.volumes;

				for ( j = 0; j < volumes.length; j ++ ) {

					const volume = volumes[ j ];
					const newGeometry = new BufferGeometry();
					let material = objDefaultMaterial;

					newGeometry.setIndex( volume.triangles );
					newGeometry.setAttribute( 'position', vertices.clone() );

					if ( normals ) {

						newGeometry.setAttribute( 'normal', normals.clone() );

					}

					if ( amfMaterials[ volume.materialId ] !== undefined ) {

						material = amfMaterials[ volume.materialId ];

					}

					newGeometry.scale( amfScale, amfScale, amfScale );
					newObject.add( new Mesh( newGeometry, material.clone() ) );

				}

			}

			sceneObject.add( newObject );

		}

		return sceneObject;

	}
```
</details>

### `loadDocument(data: any): Document`

**Parameters:**

- **`data`** `any`

**Returns:** `Document`

**Calls:**

- `String.fromCharCode`
- `view.getUint8`
- `console.log`
- `fflate.unzipSync`
- `file.toLowerCase().slice`
- `new TextDecoder().decode`
- `new DOMParser().parseFromString`
- `xmlData.documentElement.nodeName.toLowerCase`

<details><summary>Code</summary>

```typescript
function loadDocument( data ) {

			let view = new DataView( data );
			const magic = String.fromCharCode( view.getUint8( 0 ), view.getUint8( 1 ) );

			if ( magic === 'PK' ) {

				let zip = null;
				let file = null;

				console.log( 'THREE.AMFLoader: Loading Zip' );

				try {

					zip = fflate.unzipSync( new Uint8Array( data ) );

				} catch ( e ) {

					if ( e instanceof ReferenceError ) {

						console.log( 'THREE.AMFLoader: fflate missing and file is compressed.' );
						return null;

					}

				}

				for ( file in zip ) {

					if ( file.toLowerCase().slice( - 4 ) === '.amf' ) {

						break;

					}

				}

				console.log( 'THREE.AMFLoader: Trying to load file asset: ' + file );
				view = new DataView( zip[ file ].buffer );

			}

			const fileText = new TextDecoder().decode( view );
			const xmlData = new DOMParser().parseFromString( fileText, 'application/xml' );

			if ( xmlData.documentElement.nodeName.toLowerCase() !== 'amf' ) {

				console.log( 'THREE.AMFLoader: Error loading AMF - no AMF document found.' );
				return null;

			}

			return xmlData;

		}
```
</details>

### `loadDocumentScale(node: any): number`

**Parameters:**

- **`node`** `any`

**Returns:** `number`

**Calls:**

- `node.documentElement.attributes.unit.value.toLowerCase`
- `console.log`

<details><summary>Code</summary>

```typescript
function loadDocumentScale( node ) {

			let scale = 1.0;
			let unit = 'millimeter';

			if ( node.documentElement.attributes.unit !== undefined ) {

				unit = node.documentElement.attributes.unit.value.toLowerCase();

			}

			const scaleUnits = {
				millimeter: 1.0,
				inch: 25.4,
				feet: 304.8,
				meter: 1000.0,
				micron: 0.001
			};

			if ( scaleUnits[ unit ] !== undefined ) {

				scale = scaleUnits[ unit ];

			}

			console.log( 'THREE.AMFLoader: Unit scale: ' + scale );
			return scale;

		}
```
</details>

### `loadMaterials(node: any): { id: any; material: any; }`

**Parameters:**

- **`node`** `any`

**Returns:** `{ id: any; material: any; }`

**Calls:**

- `loadColor`

<details><summary>Code</summary>

```typescript
function loadMaterials( node ) {

			let matName = 'AMF Material';
			const matId = node.attributes.id.textContent;
			let color = { r: 1.0, g: 1.0, b: 1.0, a: 1.0 };

			let loadedMaterial = null;

			for ( let i = 0; i < node.childNodes.length; i ++ ) {

				const matChildEl = node.childNodes[ i ];

				if ( matChildEl.nodeName === 'metadata' && matChildEl.attributes.type !== undefined ) {

					if ( matChildEl.attributes.type.value === 'name' ) {

						matName = matChildEl.textContent;

					}

				} else if ( matChildEl.nodeName === 'color' ) {

					color = loadColor( matChildEl );

				}

			}

			loadedMaterial = new MeshPhongMaterial( {
				flatShading: true,
				color: new Color( color.r, color.g, color.b ),
				name: matName
			} );

			if ( color.a !== 1.0 ) {

				loadedMaterial.transparent = true;
				loadedMaterial.opacity = color.a;

			}

			return { id: matId, material: loadedMaterial };

		}
```
</details>

### `loadColor(node: any): { r: number; g: number; b: number; a: number; }`

**Parameters:**

- **`node`** `any`

**Returns:** `{ r: number; g: number; b: number; a: number; }`

<details><summary>Code</summary>

```typescript
function loadColor( node ) {

			const color = { r: 1.0, g: 1.0, b: 1.0, a: 1.0 };

			for ( let i = 0; i < node.childNodes.length; i ++ ) {

				const matColor = node.childNodes[ i ];

				if ( matColor.nodeName === 'r' ) {

					color.r = matColor.textContent;

				} else if ( matColor.nodeName === 'g' ) {

					color.g = matColor.textContent;

				} else if ( matColor.nodeName === 'b' ) {

					color.b = matColor.textContent;

				} else if ( matColor.nodeName === 'a' ) {

					color.a = matColor.textContent;

				}

			}

			return color;

		}
```
</details>

### `loadMeshVolume(node: any): { name: string; triangles: any[]; materialId: any; }`

**Parameters:**

- **`node`** `any`

**Returns:** `{ name: string; triangles: any[]; materialId: any; }`

**Calls:**

- `currVolumeNode.getElementsByTagName`
- `volume.triangles.push`

<details><summary>Code</summary>

```typescript
function loadMeshVolume( node ) {

			const volume = { name: '', triangles: [], materialId: null };

			let currVolumeNode = node.firstElementChild;

			if ( node.attributes.materialid !== undefined ) {

				volume.materialId = node.attributes.materialid.nodeValue;

			}

			while ( currVolumeNode ) {

				if ( currVolumeNode.nodeName === 'metadata' ) {

					if ( currVolumeNode.attributes.type !== undefined ) {

						if ( currVolumeNode.attributes.type.value === 'name' ) {

							volume.name = currVolumeNode.textContent;

						}

					}

				} else if ( currVolumeNode.nodeName === 'triangle' ) {

					const v1 = currVolumeNode.getElementsByTagName( 'v1' )[ 0 ].textContent;
					const v2 = currVolumeNode.getElementsByTagName( 'v2' )[ 0 ].textContent;
					const v3 = currVolumeNode.getElementsByTagName( 'v3' )[ 0 ].textContent;

					volume.triangles.push( v1, v2, v3 );

				}

				currVolumeNode = currVolumeNode.nextElementSibling;

			}

			return volume;

		}
```
</details>

### `loadMeshVertices(node: any): { vertices: any[]; normals: any[]; }`

**Parameters:**

- **`node`** `any`

**Returns:** `{ vertices: any[]; normals: any[]; }`

**Calls:**

- `vNode.getElementsByTagName`
- `vertArray.push`
- `normalArray.push`

<details><summary>Code</summary>

```typescript
function loadMeshVertices( node ) {

			const vertArray = [];
			const normalArray = [];
			let currVerticesNode = node.firstElementChild;

			while ( currVerticesNode ) {

				if ( currVerticesNode.nodeName === 'vertex' ) {

					let vNode = currVerticesNode.firstElementChild;

					while ( vNode ) {

						if ( vNode.nodeName === 'coordinates' ) {

							const x = vNode.getElementsByTagName( 'x' )[ 0 ].textContent;
							const y = vNode.getElementsByTagName( 'y' )[ 0 ].textContent;
							const z = vNode.getElementsByTagName( 'z' )[ 0 ].textContent;

							vertArray.push( x, y, z );

						} else if ( vNode.nodeName === 'normal' ) {

							const nx = vNode.getElementsByTagName( 'nx' )[ 0 ].textContent;
							const ny = vNode.getElementsByTagName( 'ny' )[ 0 ].textContent;
							const nz = vNode.getElementsByTagName( 'nz' )[ 0 ].textContent;

							normalArray.push( nx, ny, nz );

						}

						vNode = vNode.nextElementSibling;

					}

				}

				currVerticesNode = currVerticesNode.nextElementSibling;

			}

			return { 'vertices': vertArray, 'normals': normalArray };

		}
```
</details>

### `loadObject(node: any): { id: any; obj: { name: string; meshes: any[]; }; }`

**Parameters:**

- **`node`** `any`

**Returns:** `{ id: any; obj: { name: string; meshes: any[]; }; }`

**Calls:**

- `loadColor`
- `loadMeshVertices`
- `mesh.normals.concat`
- `mesh.vertices.concat`
- `mesh.volumes.push`
- `loadMeshVolume`
- `loadedObject.meshes.push`

<details><summary>Code</summary>

```typescript
function loadObject( node ) {

			const objId = node.attributes.id.textContent;
			const loadedObject = { name: 'amfobject', meshes: [] };
			let currColor = null;
			let currObjNode = node.firstElementChild;

			while ( currObjNode ) {

				if ( currObjNode.nodeName === 'metadata' ) {

					if ( currObjNode.attributes.type !== undefined ) {

						if ( currObjNode.attributes.type.value === 'name' ) {

							loadedObject.name = currObjNode.textContent;

						}

					}

				} else if ( currObjNode.nodeName === 'color' ) {

					currColor = loadColor( currObjNode );

				} else if ( currObjNode.nodeName === 'mesh' ) {

					let currMeshNode = currObjNode.firstElementChild;
					const mesh = { vertices: [], normals: [], volumes: [], color: currColor };

					while ( currMeshNode ) {

						if ( currMeshNode.nodeName === 'vertices' ) {

							const loadedVertices = loadMeshVertices( currMeshNode );

							mesh.normals = mesh.normals.concat( loadedVertices.normals );
							mesh.vertices = mesh.vertices.concat( loadedVertices.vertices );

						} else if ( currMeshNode.nodeName === 'volume' ) {

							mesh.volumes.push( loadMeshVolume( currMeshNode ) );

						}

						currMeshNode = currMeshNode.nextElementSibling;

					}

					loadedObject.meshes.push( mesh );

				}

				currObjNode = currObjNode.nextElementSibling;

			}

			return { 'id': objId, 'obj': loadedObject };

		}
```
</details>


---

## Classes

### `AMFLoader`

<details><summary>Class Code</summary>

```ts
class AMFLoader extends Loader {

	/**
	 * Constructs a new AMF loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded AMF asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Parses the given AMF data and returns the resulting group.
	 *
	 * @param {ArrayBuffer} data - The raw AMF asset data as an array buffer.
	 * @return {Group} A group representing the parsed asset.
	 */
	parse( data ) {

		function loadDocument( data ) {

			let view = new DataView( data );
			const magic = String.fromCharCode( view.getUint8( 0 ), view.getUint8( 1 ) );

			if ( magic === 'PK' ) {

				let zip = null;
				let file = null;

				console.log( 'THREE.AMFLoader: Loading Zip' );

				try {

					zip = fflate.unzipSync( new Uint8Array( data ) );

				} catch ( e ) {

					if ( e instanceof ReferenceError ) {

						console.log( 'THREE.AMFLoader: fflate missing and file is compressed.' );
						return null;

					}

				}

				for ( file in zip ) {

					if ( file.toLowerCase().slice( - 4 ) === '.amf' ) {

						break;

					}

				}

				console.log( 'THREE.AMFLoader: Trying to load file asset: ' + file );
				view = new DataView( zip[ file ].buffer );

			}

			const fileText = new TextDecoder().decode( view );
			const xmlData = new DOMParser().parseFromString( fileText, 'application/xml' );

			if ( xmlData.documentElement.nodeName.toLowerCase() !== 'amf' ) {

				console.log( 'THREE.AMFLoader: Error loading AMF - no AMF document found.' );
				return null;

			}

			return xmlData;

		}

		function loadDocumentScale( node ) {

			let scale = 1.0;
			let unit = 'millimeter';

			if ( node.documentElement.attributes.unit !== undefined ) {

				unit = node.documentElement.attributes.unit.value.toLowerCase();

			}

			const scaleUnits = {
				millimeter: 1.0,
				inch: 25.4,
				feet: 304.8,
				meter: 1000.0,
				micron: 0.001
			};

			if ( scaleUnits[ unit ] !== undefined ) {

				scale = scaleUnits[ unit ];

			}

			console.log( 'THREE.AMFLoader: Unit scale: ' + scale );
			return scale;

		}

		function loadMaterials( node ) {

			let matName = 'AMF Material';
			const matId = node.attributes.id.textContent;
			let color = { r: 1.0, g: 1.0, b: 1.0, a: 1.0 };

			let loadedMaterial = null;

			for ( let i = 0; i < node.childNodes.length; i ++ ) {

				const matChildEl = node.childNodes[ i ];

				if ( matChildEl.nodeName === 'metadata' && matChildEl.attributes.type !== undefined ) {

					if ( matChildEl.attributes.type.value === 'name' ) {

						matName = matChildEl.textContent;

					}

				} else if ( matChildEl.nodeName === 'color' ) {

					color = loadColor( matChildEl );

				}

			}

			loadedMaterial = new MeshPhongMaterial( {
				flatShading: true,
				color: new Color( color.r, color.g, color.b ),
				name: matName
			} );

			if ( color.a !== 1.0 ) {

				loadedMaterial.transparent = true;
				loadedMaterial.opacity = color.a;

			}

			return { id: matId, material: loadedMaterial };

		}

		function loadColor( node ) {

			const color = { r: 1.0, g: 1.0, b: 1.0, a: 1.0 };

			for ( let i = 0; i < node.childNodes.length; i ++ ) {

				const matColor = node.childNodes[ i ];

				if ( matColor.nodeName === 'r' ) {

					color.r = matColor.textContent;

				} else if ( matColor.nodeName === 'g' ) {

					color.g = matColor.textContent;

				} else if ( matColor.nodeName === 'b' ) {

					color.b = matColor.textContent;

				} else if ( matColor.nodeName === 'a' ) {

					color.a = matColor.textContent;

				}

			}

			return color;

		}

		function loadMeshVolume( node ) {

			const volume = { name: '', triangles: [], materialId: null };

			let currVolumeNode = node.firstElementChild;

			if ( node.attributes.materialid !== undefined ) {

				volume.materialId = node.attributes.materialid.nodeValue;

			}

			while ( currVolumeNode ) {

				if ( currVolumeNode.nodeName === 'metadata' ) {

					if ( currVolumeNode.attributes.type !== undefined ) {

						if ( currVolumeNode.attributes.type.value === 'name' ) {

							volume.name = currVolumeNode.textContent;

						}

					}

				} else if ( currVolumeNode.nodeName === 'triangle' ) {

					const v1 = currVolumeNode.getElementsByTagName( 'v1' )[ 0 ].textContent;
					const v2 = currVolumeNode.getElementsByTagName( 'v2' )[ 0 ].textContent;
					const v3 = currVolumeNode.getElementsByTagName( 'v3' )[ 0 ].textContent;

					volume.triangles.push( v1, v2, v3 );

				}

				currVolumeNode = currVolumeNode.nextElementSibling;

			}

			return volume;

		}

		function loadMeshVertices( node ) {

			const vertArray = [];
			const normalArray = [];
			let currVerticesNode = node.firstElementChild;

			while ( currVerticesNode ) {

				if ( currVerticesNode.nodeName === 'vertex' ) {

					let vNode = currVerticesNode.firstElementChild;

					while ( vNode ) {

						if ( vNode.nodeName === 'coordinates' ) {

							const x = vNode.getElementsByTagName( 'x' )[ 0 ].textContent;
							const y = vNode.getElementsByTagName( 'y' )[ 0 ].textContent;
							const z = vNode.getElementsByTagName( 'z' )[ 0 ].textContent;

							vertArray.push( x, y, z );

						} else if ( vNode.nodeName === 'normal' ) {

							const nx = vNode.getElementsByTagName( 'nx' )[ 0 ].textContent;
							const ny = vNode.getElementsByTagName( 'ny' )[ 0 ].textContent;
							const nz = vNode.getElementsByTagName( 'nz' )[ 0 ].textContent;

							normalArray.push( nx, ny, nz );

						}

						vNode = vNode.nextElementSibling;

					}

				}

				currVerticesNode = currVerticesNode.nextElementSibling;

			}

			return { 'vertices': vertArray, 'normals': normalArray };

		}

		function loadObject( node ) {

			const objId = node.attributes.id.textContent;
			const loadedObject = { name: 'amfobject', meshes: [] };
			let currColor = null;
			let currObjNode = node.firstElementChild;

			while ( currObjNode ) {

				if ( currObjNode.nodeName === 'metadata' ) {

					if ( currObjNode.attributes.type !== undefined ) {

						if ( currObjNode.attributes.type.value === 'name' ) {

							loadedObject.name = currObjNode.textContent;

						}

					}

				} else if ( currObjNode.nodeName === 'color' ) {

					currColor = loadColor( currObjNode );

				} else if ( currObjNode.nodeName === 'mesh' ) {

					let currMeshNode = currObjNode.firstElementChild;
					const mesh = { vertices: [], normals: [], volumes: [], color: currColor };

					while ( currMeshNode ) {

						if ( currMeshNode.nodeName === 'vertices' ) {

							const loadedVertices = loadMeshVertices( currMeshNode );

							mesh.normals = mesh.normals.concat( loadedVertices.normals );
							mesh.vertices = mesh.vertices.concat( loadedVertices.vertices );

						} else if ( currMeshNode.nodeName === 'volume' ) {

							mesh.volumes.push( loadMeshVolume( currMeshNode ) );

						}

						currMeshNode = currMeshNode.nextElementSibling;

					}

					loadedObject.meshes.push( mesh );

				}

				currObjNode = currObjNode.nextElementSibling;

			}

			return { 'id': objId, 'obj': loadedObject };

		}

		const xmlData = loadDocument( data );
		let amfName = '';
		let amfAuthor = '';
		const amfScale = loadDocumentScale( xmlData );
		const amfMaterials = {};
		const amfObjects = {};
		const childNodes = xmlData.documentElement.childNodes;

		let i, j;

		for ( i = 0; i < childNodes.length; i ++ ) {

			const child = childNodes[ i ];

			if ( child.nodeName === 'metadata' ) {

				if ( child.attributes.type !== undefined ) {

					if ( child.attributes.type.value === 'name' ) {

						amfName = child.textContent;

					} else if ( child.attributes.type.value === 'author' ) {

						amfAuthor = child.textContent;

					}

				}

			} else if ( child.nodeName === 'material' ) {

				const loadedMaterial = loadMaterials( child );

				amfMaterials[ loadedMaterial.id ] = loadedMaterial.material;

			} else if ( child.nodeName === 'object' ) {

				const loadedObject = loadObject( child );

				amfObjects[ loadedObject.id ] = loadedObject.obj;

			}

		}

		const sceneObject = new Group();
		const defaultMaterial = new MeshPhongMaterial( {
			name: Loader.DEFAULT_MATERIAL_NAME,
			color: 0xaaaaff,
			flatShading: true
		} );

		sceneObject.name = amfName;
		sceneObject.userData.author = amfAuthor;
		sceneObject.userData.loader = 'AMF';

		for ( const id in amfObjects ) {

			const part = amfObjects[ id ];
			const meshes = part.meshes;
			const newObject = new Group();
			newObject.name = part.name || '';

			for ( i = 0; i < meshes.length; i ++ ) {

				let objDefaultMaterial = defaultMaterial;
				const mesh = meshes[ i ];
				const vertices = new Float32BufferAttribute( mesh.vertices, 3 );
				let normals = null;

				if ( mesh.normals.length ) {

					normals = new Float32BufferAttribute( mesh.normals, 3 );

				}

				if ( mesh.color ) {

					const color = mesh.color;

					objDefaultMaterial = defaultMaterial.clone();
					objDefaultMaterial.color = new Color( color.r, color.g, color.b );

					if ( color.a !== 1.0 ) {

						objDefaultMaterial.transparent = true;
						objDefaultMaterial.opacity = color.a;

					}

				}

				const volumes = mesh.volumes;

				for ( j = 0; j < volumes.length; j ++ ) {

					const volume = volumes[ j ];
					const newGeometry = new BufferGeometry();
					let material = objDefaultMaterial;

					newGeometry.setIndex( volume.triangles );
					newGeometry.setAttribute( 'position', vertices.clone() );

					if ( normals ) {

						newGeometry.setAttribute( 'normal', normals.clone() );

					}

					if ( amfMaterials[ volume.materialId ] !== undefined ) {

						material = amfMaterials[ volume.materialId ];

					}

					newGeometry.scale( amfScale, amfScale, amfScale );
					newObject.add( new Mesh( newGeometry, material.clone() ) );

				}

			}

			sceneObject.add( newObject );

		}

		return sceneObject;

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `parse(data: ArrayBuffer): Group`

<details><summary>Code</summary>

```ts
parse( data ) {

		function loadDocument( data ) {

			let view = new DataView( data );
			const magic = String.fromCharCode( view.getUint8( 0 ), view.getUint8( 1 ) );

			if ( magic === 'PK' ) {

				let zip = null;
				let file = null;

				console.log( 'THREE.AMFLoader: Loading Zip' );

				try {

					zip = fflate.unzipSync( new Uint8Array( data ) );

				} catch ( e ) {

					if ( e instanceof ReferenceError ) {

						console.log( 'THREE.AMFLoader: fflate missing and file is compressed.' );
						return null;

					}

				}

				for ( file in zip ) {

					if ( file.toLowerCase().slice( - 4 ) === '.amf' ) {

						break;

					}

				}

				console.log( 'THREE.AMFLoader: Trying to load file asset: ' + file );
				view = new DataView( zip[ file ].buffer );

			}

			const fileText = new TextDecoder().decode( view );
			const xmlData = new DOMParser().parseFromString( fileText, 'application/xml' );

			if ( xmlData.documentElement.nodeName.toLowerCase() !== 'amf' ) {

				console.log( 'THREE.AMFLoader: Error loading AMF - no AMF document found.' );
				return null;

			}

			return xmlData;

		}

		function loadDocumentScale( node ) {

			let scale = 1.0;
			let unit = 'millimeter';

			if ( node.documentElement.attributes.unit !== undefined ) {

				unit = node.documentElement.attributes.unit.value.toLowerCase();

			}

			const scaleUnits = {
				millimeter: 1.0,
				inch: 25.4,
				feet: 304.8,
				meter: 1000.0,
				micron: 0.001
			};

			if ( scaleUnits[ unit ] !== undefined ) {

				scale = scaleUnits[ unit ];

			}

			console.log( 'THREE.AMFLoader: Unit scale: ' + scale );
			return scale;

		}

		function loadMaterials( node ) {

			let matName = 'AMF Material';
			const matId = node.attributes.id.textContent;
			let color = { r: 1.0, g: 1.0, b: 1.0, a: 1.0 };

			let loadedMaterial = null;

			for ( let i = 0; i < node.childNodes.length; i ++ ) {

				const matChildEl = node.childNodes[ i ];

				if ( matChildEl.nodeName === 'metadata' && matChildEl.attributes.type !== undefined ) {

					if ( matChildEl.attributes.type.value === 'name' ) {

						matName = matChildEl.textContent;

					}

				} else if ( matChildEl.nodeName === 'color' ) {

					color = loadColor( matChildEl );

				}

			}

			loadedMaterial = new MeshPhongMaterial( {
				flatShading: true,
				color: new Color( color.r, color.g, color.b ),
				name: matName
			} );

			if ( color.a !== 1.0 ) {

				loadedMaterial.transparent = true;
				loadedMaterial.opacity = color.a;

			}

			return { id: matId, material: loadedMaterial };

		}

		function loadColor( node ) {

			const color = { r: 1.0, g: 1.0, b: 1.0, a: 1.0 };

			for ( let i = 0; i < node.childNodes.length; i ++ ) {

				const matColor = node.childNodes[ i ];

				if ( matColor.nodeName === 'r' ) {

					color.r = matColor.textContent;

				} else if ( matColor.nodeName === 'g' ) {

					color.g = matColor.textContent;

				} else if ( matColor.nodeName === 'b' ) {

					color.b = matColor.textContent;

				} else if ( matColor.nodeName === 'a' ) {

					color.a = matColor.textContent;

				}

			}

			return color;

		}

		function loadMeshVolume( node ) {

			const volume = { name: '', triangles: [], materialId: null };

			let currVolumeNode = node.firstElementChild;

			if ( node.attributes.materialid !== undefined ) {

				volume.materialId = node.attributes.materialid.nodeValue;

			}

			while ( currVolumeNode ) {

				if ( currVolumeNode.nodeName === 'metadata' ) {

					if ( currVolumeNode.attributes.type !== undefined ) {

						if ( currVolumeNode.attributes.type.value === 'name' ) {

							volume.name = currVolumeNode.textContent;

						}

					}

				} else if ( currVolumeNode.nodeName === 'triangle' ) {

					const v1 = currVolumeNode.getElementsByTagName( 'v1' )[ 0 ].textContent;
					const v2 = currVolumeNode.getElementsByTagName( 'v2' )[ 0 ].textContent;
					const v3 = currVolumeNode.getElementsByTagName( 'v3' )[ 0 ].textContent;

					volume.triangles.push( v1, v2, v3 );

				}

				currVolumeNode = currVolumeNode.nextElementSibling;

			}

			return volume;

		}

		function loadMeshVertices( node ) {

			const vertArray = [];
			const normalArray = [];
			let currVerticesNode = node.firstElementChild;

			while ( currVerticesNode ) {

				if ( currVerticesNode.nodeName === 'vertex' ) {

					let vNode = currVerticesNode.firstElementChild;

					while ( vNode ) {

						if ( vNode.nodeName === 'coordinates' ) {

							const x = vNode.getElementsByTagName( 'x' )[ 0 ].textContent;
							const y = vNode.getElementsByTagName( 'y' )[ 0 ].textContent;
							const z = vNode.getElementsByTagName( 'z' )[ 0 ].textContent;

							vertArray.push( x, y, z );

						} else if ( vNode.nodeName === 'normal' ) {

							const nx = vNode.getElementsByTagName( 'nx' )[ 0 ].textContent;
							const ny = vNode.getElementsByTagName( 'ny' )[ 0 ].textContent;
							const nz = vNode.getElementsByTagName( 'nz' )[ 0 ].textContent;

							normalArray.push( nx, ny, nz );

						}

						vNode = vNode.nextElementSibling;

					}

				}

				currVerticesNode = currVerticesNode.nextElementSibling;

			}

			return { 'vertices': vertArray, 'normals': normalArray };

		}

		function loadObject( node ) {

			const objId = node.attributes.id.textContent;
			const loadedObject = { name: 'amfobject', meshes: [] };
			let currColor = null;
			let currObjNode = node.firstElementChild;

			while ( currObjNode ) {

				if ( currObjNode.nodeName === 'metadata' ) {

					if ( currObjNode.attributes.type !== undefined ) {

						if ( currObjNode.attributes.type.value === 'name' ) {

							loadedObject.name = currObjNode.textContent;

						}

					}

				} else if ( currObjNode.nodeName === 'color' ) {

					currColor = loadColor( currObjNode );

				} else if ( currObjNode.nodeName === 'mesh' ) {

					let currMeshNode = currObjNode.firstElementChild;
					const mesh = { vertices: [], normals: [], volumes: [], color: currColor };

					while ( currMeshNode ) {

						if ( currMeshNode.nodeName === 'vertices' ) {

							const loadedVertices = loadMeshVertices( currMeshNode );

							mesh.normals = mesh.normals.concat( loadedVertices.normals );
							mesh.vertices = mesh.vertices.concat( loadedVertices.vertices );

						} else if ( currMeshNode.nodeName === 'volume' ) {

							mesh.volumes.push( loadMeshVolume( currMeshNode ) );

						}

						currMeshNode = currMeshNode.nextElementSibling;

					}

					loadedObject.meshes.push( mesh );

				}

				currObjNode = currObjNode.nextElementSibling;

			}

			return { 'id': objId, 'obj': loadedObject };

		}

		const xmlData = loadDocument( data );
		let amfName = '';
		let amfAuthor = '';
		const amfScale = loadDocumentScale( xmlData );
		const amfMaterials = {};
		const amfObjects = {};
		const childNodes = xmlData.documentElement.childNodes;

		let i, j;

		for ( i = 0; i < childNodes.length; i ++ ) {

			const child = childNodes[ i ];

			if ( child.nodeName === 'metadata' ) {

				if ( child.attributes.type !== undefined ) {

					if ( child.attributes.type.value === 'name' ) {

						amfName = child.textContent;

					} else if ( child.attributes.type.value === 'author' ) {

						amfAuthor = child.textContent;

					}

				}

			} else if ( child.nodeName === 'material' ) {

				const loadedMaterial = loadMaterials( child );

				amfMaterials[ loadedMaterial.id ] = loadedMaterial.material;

			} else if ( child.nodeName === 'object' ) {

				const loadedObject = loadObject( child );

				amfObjects[ loadedObject.id ] = loadedObject.obj;

			}

		}

		const sceneObject = new Group();
		const defaultMaterial = new MeshPhongMaterial( {
			name: Loader.DEFAULT_MATERIAL_NAME,
			color: 0xaaaaff,
			flatShading: true
		} );

		sceneObject.name = amfName;
		sceneObject.userData.author = amfAuthor;
		sceneObject.userData.loader = 'AMF';

		for ( const id in amfObjects ) {

			const part = amfObjects[ id ];
			const meshes = part.meshes;
			const newObject = new Group();
			newObject.name = part.name || '';

			for ( i = 0; i < meshes.length; i ++ ) {

				let objDefaultMaterial = defaultMaterial;
				const mesh = meshes[ i ];
				const vertices = new Float32BufferAttribute( mesh.vertices, 3 );
				let normals = null;

				if ( mesh.normals.length ) {

					normals = new Float32BufferAttribute( mesh.normals, 3 );

				}

				if ( mesh.color ) {

					const color = mesh.color;

					objDefaultMaterial = defaultMaterial.clone();
					objDefaultMaterial.color = new Color( color.r, color.g, color.b );

					if ( color.a !== 1.0 ) {

						objDefaultMaterial.transparent = true;
						objDefaultMaterial.opacity = color.a;

					}

				}

				const volumes = mesh.volumes;

				for ( j = 0; j < volumes.length; j ++ ) {

					const volume = volumes[ j ];
					const newGeometry = new BufferGeometry();
					let material = objDefaultMaterial;

					newGeometry.setIndex( volume.triangles );
					newGeometry.setAttribute( 'position', vertices.clone() );

					if ( normals ) {

						newGeometry.setAttribute( 'normal', normals.clone() );

					}

					if ( amfMaterials[ volume.materialId ] !== undefined ) {

						material = amfMaterials[ volume.materialId ];

					}

					newGeometry.scale( amfScale, amfScale, amfScale );
					newObject.add( new Mesh( newGeometry, material.clone() ) );

				}

			}

			sceneObject.add( newObject );

		}

		return sceneObject;

	}
```
</details>


---