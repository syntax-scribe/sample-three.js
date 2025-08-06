[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `3MFLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 39 |
| 🧱 Classes | 1 |
| 📦 Imports | 19 |
| 📊 Variables & Constants | 167 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/3MFLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `ClampToEdgeWrapping` | `three` |
| `Color` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Group` | `three` |
| `LinearFilter` | `three` |
| `LinearMipmapLinearFilter` | `three` |
| `Loader` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshPhongMaterial` | `three` |
| `MeshStandardMaterial` | `three` |
| `MirroredRepeatWrapping` | `three` |
| `NearestFilter` | `three` |
| `RepeatWrapping` | `three` |
| `TextureLoader` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `COLOR_SPACE_3MF` | `any` | let/var | `SRGBColorSpace` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `textureLoader` | `any` | let/var | `new TextureLoader( this.manager )` | ✗ |
| `zip` | `any` | let/var | `null` | ✗ |
| `file` | `any` | let/var | `null` | ✗ |
| `relsName` | `any` | let/var | `*not shown*` | ✗ |
| `modelRelsName` | `any` | let/var | `*not shown*` | ✗ |
| `modelPartNames` | `any[]` | let/var | `[]` | ✗ |
| `texturesPartNames` | `any[]` | let/var | `[]` | ✗ |
| `modelRels` | `any` | let/var | `*not shown*` | ✗ |
| `modelParts` | `{}` | let/var | `{}` | ✗ |
| `printTicketParts` | `{}` | let/var | `{}` | ✗ |
| `texturesParts` | `{}` | let/var | `{}` | ✗ |
| `textDecoder` | `TextDecoder` | let/var | `new TextDecoder()` | ✗ |
| `rootModelFile` | `any` | let/var | `null` | ✗ |
| `relsView` | `any` | let/var | `zip[ relsName ]` | ✗ |
| `relsView` | `any` | let/var | `zip[ modelRelsName ]` | ✗ |
| `modelPart` | `string` | let/var | `modelPartNames[ i ]` | ✗ |
| `view` | `any` | let/var | `zip[ modelPart ]` | ✗ |
| `extensions` | `{}` | let/var | `{}` | ✗ |
| `attr` | `Attr` | let/var | `modelNode.attributes[ i ]` | ✗ |
| `texturesPartName` | `string` | let/var | `texturesPartNames[ i ]` | ✗ |
| `relationships` | `any[]` | let/var | `[]` | ✗ |
| `relsNode` | `Element` | let/var | `relsNodes[ i ]` | ✗ |
| `relationship` | `{ target: string; id: string; type: s...` | let/var | `{ target: relsNode.getAttribute( 'Target' ), //required id: relsNode.getAttri...` | ✗ |
| `metadataData` | `{}` | let/var | `{}` | ✗ |
| `metadataNode` | `any` | let/var | `metadataNodes[ i ]` | ✗ |
| `validNames` | `string[]` | let/var | `[ 'Title', 'Designer', 'Description', 'Copyright', 'LicenseTerms', 'Rating', ...` | ✗ |
| `basematerialsData` | `{ id: any; basematerials: any[]; }` | let/var | `{ id: basematerialsNode.getAttribute( 'id' ), // required basematerials: [] }` | ✗ |
| `basematerialNode` | `any` | let/var | `basematerialNodes[ i ]` | ✗ |
| `texture2dData` | `{ id: any; path: any; contenttype: an...` | let/var | `{ id: texture2DNode.getAttribute( 'id' ), // required path: texture2DNode.get...` | ✗ |
| `texture2DGroupData` | `{ id: any; texid: any; displaypropert...` | let/var | `{ id: texture2DGroupNode.getAttribute( 'id' ), // required texid: texture2DGr...` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `tex2coordNode` | `any` | let/var | `tex2coordNodes[ i ]` | ✗ |
| `colorGroupData` | `{ id: any; displaypropertiesid: any; }` | let/var | `{ id: colorGroupNode.getAttribute( 'id' ), // required displaypropertiesid: c...` | ✗ |
| `colors` | `any[]` | let/var | `[]` | ✗ |
| `colorObject` | `any` | let/var | `new Color()` | ✗ |
| `colorNode` | `any` | let/var | `colorNodes[ i ]` | ✗ |
| `portNodes` | `any` | let/var | `implicitIONode.children` | ✗ |
| `portArguments` | `{}` | let/var | `{}` | ✗ |
| `args` | `{ type: any; }` | let/var | `{ type: portNodes[ i ].nodeName.substring( 2 ) }` | ✗ |
| `attrib` | `any` | let/var | `portNodes[ i ].attributes[ j ]` | ✗ |
| `implicitFunctionData` | `{ id: any; displayname: any; }` | let/var | `{ id: implicitFunctionNode.getAttribute( 'id' ), displayname: implicitFunctio...` | ✗ |
| `functionNodes` | `any` | let/var | `implicitFunctionNode.children` | ✗ |
| `operations` | `{}` | let/var | `{}` | ✗ |
| `operatorNode` | `any` | let/var | `functionNodes[ i ]` | ✗ |
| `inputNodes` | `any` | let/var | `operatorNode.children` | ✗ |
| `portArguments` | `{ op: any; identifier: any; }` | let/var | `{ 'op': operatorNode.nodeName.substring( 2 ), 'identifier': operatorNode.getA...` | ✗ |
| `metallicDisplaypropertiesData` | `{ id: any; }` | let/var | `{ id: metallicDisplaypropetiesNode.getAttribute( 'id' ) // required }` | ✗ |
| `metallicData` | `any[]` | let/var | `[]` | ✗ |
| `metallicNode` | `any` | let/var | `metallicNodes[ i ]` | ✗ |
| `basematerialData` | `{ name: any; displaycolor: any; displ...` | let/var | `{}` | ✗ |
| `meshData` | `{ vertices: Float32Array<ArrayBuffer>...` | let/var | `{}` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `vertexNode` | `any` | let/var | `vertexNodes[ i ]` | ✗ |
| `triangleProperties` | `any[]` | let/var | `[]` | ✗ |
| `triangles` | `any[]` | let/var | `[]` | ✗ |
| `triangleNode` | `any` | let/var | `triangleNodes[ i ]` | ✗ |
| `triangleProperty` | `{ v1: number; v2: number; v3: number; }` | let/var | `{}` | ✗ |
| `components` | `any[]` | let/var | `[]` | ✗ |
| `componentNode` | `any` | let/var | `componentNodes[ i ]` | ✗ |
| `componentData` | `{ objectId: any; transform: any; }` | let/var | `{}` | ✗ |
| `t` | `any[]` | let/var | `[]` | ✗ |
| `matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `objectData` | `{ type: any; }` | let/var | `{ type: objectNode.getAttribute( 'type' ) }` | ✗ |
| `resourcesData` | `{ basematerials: {}; texture2d: {}; c...` | let/var | `{}` | ✗ |
| `basematerialsNode` | `any` | let/var | `basematerialsNodes[ i ]` | ✗ |
| `textures2DNode` | `any` | let/var | `textures2DNodes[ i ]` | ✗ |
| `colorGroupNode` | `any` | let/var | `colorGroupNodes[ i ]` | ✗ |
| `implicitFunctionNode` | `any` | let/var | `implicitFunctionNodes[ i ]` | ✗ |
| `pbmetallicdisplayproperties...` | `any` | let/var | `pbmetallicdisplaypropertiesNodes[ i ]` | ✗ |
| `textures2DGroupNode` | `any` | let/var | `textures2DGroupNodes[ i ]` | ✗ |
| `objectNode` | `any` | let/var | `objectNodes[ i ]` | ✗ |
| `buildData` | `any[]` | let/var | `[]` | ✗ |
| `itemNode` | `any` | let/var | `itemNodes[ i ]` | ✗ |
| `buildItem` | `{ objectId: any; }` | let/var | `{ objectId: itemNode.getAttribute( 'objectid' ) }` | ✗ |
| `modelData` | `{ unit: any; }` | let/var | `{ unit: modelNode.getAttribute( 'unit' ) \|\| 'millimeter' }` | ✗ |
| `texid` | `any` | let/var | `texture2dgroup.texid` | ✗ |
| `texture2ds` | `any` | let/var | `modelData.resources.texture2d` | ✗ |
| `texture2d` | `any` | let/var | `texture2ds[ texid ]` | ✗ |
| `data` | `any` | let/var | `textureData[ texture2d.path ]` | ✗ |
| `type` | `any` | let/var | `texture2d.contenttype` | ✗ |
| `blob` | `Blob` | let/var | `new Blob( [ data ], { type: type } )` | ✗ |
| `objectPindex` | `any` | let/var | `objectData.pindex` | ✗ |
| `materialMap` | `{}` | let/var | `{}` | ✗ |
| `triangleProperty` | `any` | let/var | `triangleProperties[ i ]` | ✗ |
| `pindex` | `any` | let/var | `( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectPindex` | ✗ |
| `meshes` | `any[]` | let/var | `[]` | ✗ |
| `materialIndex` | `string` | let/var | `keys[ i ]` | ✗ |
| `trianglePropertiesProps` | `any` | let/var | `materialMap[ materialIndex ]` | ✗ |
| `basematerialData` | `any` | let/var | `basematerials.basematerials[ materialIndex ]` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `positionData` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any` | let/var | `meshData.vertices` | ✗ |
| `triangleProperty` | `any` | let/var | `trianglePropertiesProps[ j ]` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( geometry, material )` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `positionData` | `any[]` | let/var | `[]` | ✗ |
| `uvData` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any` | let/var | `meshData.vertices` | ✗ |
| `uvs` | `any` | let/var | `texture2dgroup.uvs` | ✗ |
| `triangleProperty` | `any` | let/var | `triangleProperties[ i ]` | ✗ |
| `material` | `any` | let/var | `new MeshPhongMaterial( { map: texture, flatShading: true } )` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( geometry, material )` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `positionData` | `any[]` | let/var | `[]` | ✗ |
| `colorData` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any` | let/var | `meshData.vertices` | ✗ |
| `colors` | `any` | let/var | `colorgroup.colors` | ✗ |
| `triangleProperty` | `any` | let/var | `triangleProperties[ i ]` | ✗ |
| `v1` | `any` | let/var | `triangleProperty.v1` | ✗ |
| `v2` | `any` | let/var | `triangleProperty.v2` | ✗ |
| `v3` | `any` | let/var | `triangleProperty.v3` | ✗ |
| `p1` | `any` | let/var | `( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectData.pindex` | ✗ |
| `p2` | `any` | let/var | `( triangleProperty.p2 !== undefined ) ? triangleProperty.p2 : p1` | ✗ |
| `p3` | `any` | let/var | `( triangleProperty.p3 !== undefined ) ? triangleProperty.p3 : p1` | ✗ |
| `material` | `any` | let/var | `new MeshPhongMaterial( { vertexColors: true, flatShading: true } )` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( geometry, material )` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `any` | let/var | `new MeshPhongMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, color: 0xffffff,...` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( geometry, material )` | ✗ |
| `meshes` | `any[]` | let/var | `[]` | ✗ |
| `resourceId` | `string` | let/var | `keys[ i ]` | ✗ |
| `triangleProperties` | `any` | let/var | `resourceMap[ resourceId ]` | ✗ |
| `basematerials` | `any` | let/var | `modelData.resources.basematerials[ resourceId ]` | ✗ |
| `texture2dgroup` | `any` | let/var | `modelData.resources.texture2dgroup[ resourceId ]` | ✗ |
| `colorgroup` | `any` | let/var | `modelData.resources.colorgroup[ resourceId ]` | ✗ |
| `resourceMap` | `{}` | let/var | `{}` | ✗ |
| `triangleProperties` | `any` | let/var | `meshData[ 'triangleProperties' ]` | ✗ |
| `objectPid` | `any` | let/var | `objectData.pid` | ✗ |
| `triangleProperty` | `any` | let/var | `triangleProperties[ i ]` | ✗ |
| `pid` | `any` | let/var | `( triangleProperty.pid !== undefined ) ? triangleProperty.pid : objectPid` | ✗ |
| `group` | `any` | let/var | `new Group()` | ✗ |
| `availableExtensions` | `any[]` | let/var | `[]` | ✗ |
| `ns` | `string` | let/var | `keys[ i ]` | ✗ |
| `extension` | `any` | let/var | `scope.availableExtensions[ j ]` | ✗ |
| `extension` | `any` | let/var | `availableExtensions[ i ]` | ✗ |
| `material` | `any` | let/var | `*not shown*` | ✗ |
| `displaypropertiesid` | `any` | let/var | `materialData.displaypropertiesid` | ✗ |
| `pbmetallicdisplayproperties` | `any` | let/var | `modelData.resources.pbmetallicdisplayproperties` | ✗ |
| `pbmetallicdisplayproperty` | `any` | let/var | `pbmetallicdisplayproperties[ displaypropertiesid ]` | ✗ |
| `metallicData` | `any` | let/var | `pbmetallicdisplayproperty.data[ materialData.index ]` | ✗ |
| `displaycolor` | `any` | let/var | `materialData.displaycolor` | ✗ |
| `composite` | `any` | let/var | `new Group()` | ✗ |
| `component` | `any` | let/var | `compositeData[ j ]` | ✗ |
| `build` | `any` | let/var | `objects[ component.objectId ]` | ✗ |
| `transform` | `any` | let/var | `component.transform` | ✗ |
| `objectData` | `any` | let/var | `modelData[ 'resources' ][ 'object' ][ objectId ]` | ✗ |
| `meshData` | `any` | let/var | `objectData[ 'mesh' ]` | ✗ |
| `extensions` | `any` | let/var | `modelData[ 'extensions' ]` | ✗ |
| `modelXml` | `any` | let/var | `modelData[ 'xml' ]` | ✗ |
| `compositeData` | `any` | let/var | `objectData[ 'components' ]` | ✗ |
| `modelsData` | `any` | let/var | `data3mf.model` | ✗ |
| `modelRels` | `any` | let/var | `data3mf.modelRels` | ✗ |
| `objects` | `{}` | let/var | `{}` | ✗ |
| `textureData` | `{}` | let/var | `{}` | ✗ |
| `modelRel` | `any` | let/var | `modelRels[ i ]` | ✗ |
| `modelsKey` | `string` | let/var | `modelsKeys[ i ]` | ✗ |
| `modelData` | `any` | let/var | `modelsData[ modelsKey ]` | ✗ |
| `objectId` | `string` | let/var | `objectIds[ j ]` | ✗ |
| `rel` | `any` | let/var | `rels[ i ]` | ✗ |
| `group` | `any` | let/var | `new Group()` | ✗ |
| `buildData` | `any` | let/var | `data3mf.model[ relationship[ 'target' ].substring( 1 ) ][ 'build' ]` | ✗ |
| `buildItem` | `any` | let/var | `buildData[ i ]` | ✗ |
| `transform` | `any` | let/var | `buildItem[ 'transform' ]` | ✗ |


---

## Functions

### `ThreeMFLoader.load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded 3MF asset
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
		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer ) );

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

### `ThreeMFLoader.parse(data: ArrayBuffer): Group`

**JSDoc:**
```typescript
/**
	 * Parses the given 3MF data and returns the resulting group.
	 *
	 * @param {ArrayBuffer} data - The raw 3MF asset data as an array buffer.
	 * @return {Group} A group representing the parsed asset.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`

**Returns:** `Group`

**Calls:**

- `fflate.unzipSync`
- `console.error`
- `file.match`
- `modelPartNames.push`
- `texturesPartNames.push`
- `textDecoder.decode`
- `parseRelsXml`
- `new DOMParser().parseFromString`
- `xmlData.documentElement.nodeName.toLowerCase`
- `xmlData.querySelector`
- `attr.name.match`
- `parseModelNode`
- `Object.keys`
- `relsXmlData.querySelectorAll`
- `relsNode.getAttribute`
- `relationships.push`
- `metadataNode.getAttribute`
- `validNames.indexOf`
- `basematerialsNode.getAttribute`
- `basematerialsNode.querySelectorAll`
- `parseBasematerialNode`
- `basematerialsData.basematerials.push`
- `texture2DNode.getAttribute`
- `texture2DGroupNode.getAttribute`
- `texture2DGroupNode.querySelectorAll`
- `tex2coordNode.getAttribute`
- `uvs.push`
- `parseFloat`
- `colorGroupNode.getAttribute`
- `colorGroupNode.querySelectorAll`
- `colorNode.getAttribute`
- `colorObject.setStyle`
- `color.substring`
- `colors.push`
- `portNodes[ i ].nodeName.substring`
- `portNodes[ i ].getAttribute`
- `implicitFunctionNode.getAttribute`
- `parseImplicitIONode`
- `operatorNode.nodeName.substring`
- `operatorNode.getAttribute`
- `inputNodes[ i ].nodeName.substring`
- `metallicDisplaypropetiesNode.getAttribute`
- `metallicDisplaypropetiesNode.querySelectorAll`
- `metallicData.push`
- `metallicNode.getAttribute`
- `basematerialNode.getAttribute`
- `meshNode.querySelectorAll`
- `vertexNode.getAttribute`
- `vertices.push`
- `triangleNode.getAttribute`
- `parseInt`
- `triangles.push`
- `triangleProperties.push`
- `componentsNode.querySelectorAll`
- `parseComponentNode`
- `components.push`
- `componentNode.getAttribute`
- `parseTransform`
- `transform.split( ' ' ).forEach`
- `t.push`
- `matrix.set`
- `objectNode.getAttribute`
- `objectNode.querySelector`
- `parseMeshNode`
- `parseComponentsNode`
- `resourcesNode.querySelectorAll`
- `parseBasematerialsNode`
- `parseTexture2DNode`
- `parseColorGroupNode`
- `parseImplicitFunctionNode`
- `parseMetallicDisplaypropertiesNode`
- `parseTextures2DGroupNode`
- `parseObjectNode`
- `buildNode.querySelectorAll`
- `itemNode.getAttribute`
- `buildData.push`
- `modelNode.getAttribute`
- `modelNode.querySelectorAll`
- `parseMetadataNodes`
- `modelNode.querySelector`
- `parseResourcesNode`
- `parseBuildNode`
- `URL.createObjectURL`
- `textureLoader.load`
- `URL.revokeObjectURL`
- `materialMap[ pindex ].push`
- `getBuild`
- `positionData.push`
- `geometry.setAttribute`
- `meshes.push`
- `uvData.push`
- `colorData.push`
- `geometry.setIndex`
- `getResourceType`
- `buildBasematerialsMeshes`
- `buildTexturedMesh`
- `buildVertexColorMesh`
- `buildDefaultMesh`
- `resourceMap[ pid ].push`
- `analyzeObject`
- `buildMeshes`
- `group.add`
- `availableExtensions.push`
- `extension.apply`
- `builder`
- `displaycolor.substring`
- `material.color.setStyle`
- `displaycolor.charAt`
- `buildObject`
- `build.clone`
- `object3D.applyMatrix4`
- `composite.add`
- `applyExtensions`
- `console.warn`
- `modelRel.target.substring`
- `rel.target.split( '.' ).pop`
- `extension.toLowerCase`
- `fetch3DModelPart`
- `relationship[ 'target' ].substring`
- `objects[ buildItem[ 'objectId' ] ].clone`
- `loadDocument`
- `buildObjects`
- `build`

**Internal Comments:**
```
// (x39)
// optional
// texture parameters
// geometry (x4)
// material (x4)
// mesh (x4)
// metallic display property, use StandardMaterial (x2)
// otherwise use PhongMaterial (x3)
// displaycolor MUST be specified with a value of a 6 or 8 digit hexadecimal number, e.g. "#RRGGBB" or "#RRGGBBAA" (x2)
// process alpha if set
// apply component transform (x2)
// evaluate model relationships to textures
// start build
// apply transform (x2)
```

<details><summary>Code</summary>

```typescript
parse( data ) {

		const scope = this;
		const textureLoader = new TextureLoader( this.manager );

		function loadDocument( data ) {

			let zip = null;
			let file = null;

			let relsName;
			let modelRelsName;
			const modelPartNames = [];
			const texturesPartNames = [];

			let modelRels;
			const modelParts = {};
			const printTicketParts = {};
			const texturesParts = {};

			const textDecoder = new TextDecoder();

			try {

				zip = fflate.unzipSync( new Uint8Array( data ) );

			} catch ( e ) {

				if ( e instanceof ReferenceError ) {

					console.error( 'THREE.3MFLoader: fflate missing and file is compressed.' );
					return null;

				}

			}

			let rootModelFile = null;

			for ( file in zip ) {

				if ( file.match( /\_rels\/.rels$/ ) ) {

					relsName = file;

				} else if ( file.match( /3D\/_rels\/.*\.model\.rels$/ ) ) {

					modelRelsName = file;

				} else if ( file.match( /^3D\/[^\/]*\.model$/ ) ) {

					rootModelFile = file;

				} else if ( file.match( /^3D\/.*\/.*\.model$/ ) ) {

					modelPartNames.push( file ); // sub models

				} else if ( file.match( /^3D\/Textures?\/.*/ ) ) {

					texturesPartNames.push( file );

				}

			}

			modelPartNames.push( rootModelFile ); // push root model at the end so it is processed after the sub models

			if ( relsName === undefined ) throw new Error( 'THREE.ThreeMFLoader: Cannot find relationship file `rels` in 3MF archive.' );

			//

			const relsView = zip[ relsName ];
			const relsFileText = textDecoder.decode( relsView );
			const rels = parseRelsXml( relsFileText );

			//

			if ( modelRelsName ) {

				const relsView = zip[ modelRelsName ];
				const relsFileText = textDecoder.decode( relsView );
				modelRels = parseRelsXml( relsFileText );

			}

			//

			for ( let i = 0; i < modelPartNames.length; i ++ ) {

				const modelPart = modelPartNames[ i ];
				const view = zip[ modelPart ];

				const fileText = textDecoder.decode( view );
				const xmlData = new DOMParser().parseFromString( fileText, 'application/xml' );

				if ( xmlData.documentElement.nodeName.toLowerCase() !== 'model' ) {

					console.error( 'THREE.3MFLoader: Error loading 3MF - no 3MF document found: ', modelPart );

				}

				const modelNode = xmlData.querySelector( 'model' );
				const extensions = {};

				for ( let i = 0; i < modelNode.attributes.length; i ++ ) {

					const attr = modelNode.attributes[ i ];
					if ( attr.name.match( /^xmlns:(.+)$/ ) ) {

						extensions[ attr.value ] = RegExp.$1;

					}

				}

				const modelData = parseModelNode( modelNode );
				modelData[ 'xml' ] = modelNode;

				if ( 0 < Object.keys( extensions ).length ) {

					modelData[ 'extensions' ] = extensions;

				}

				modelParts[ modelPart ] = modelData;

			}

			//

			for ( let i = 0; i < texturesPartNames.length; i ++ ) {

				const texturesPartName = texturesPartNames[ i ];
				texturesParts[ texturesPartName ] = zip[ texturesPartName ].buffer;

			}

			return {
				rels: rels,
				modelRels: modelRels,
				model: modelParts,
				printTicket: printTicketParts,
				texture: texturesParts
			};

		}

		function parseRelsXml( relsFileText ) {

			const relationships = [];

			const relsXmlData = new DOMParser().parseFromString( relsFileText, 'application/xml' );

			const relsNodes = relsXmlData.querySelectorAll( 'Relationship' );

			for ( let i = 0; i < relsNodes.length; i ++ ) {

				const relsNode = relsNodes[ i ];

				const relationship = {
					target: relsNode.getAttribute( 'Target' ), //required
					id: relsNode.getAttribute( 'Id' ), //required
					type: relsNode.getAttribute( 'Type' ) //required
				};

				relationships.push( relationship );

			}

			return relationships;

		}

		function parseMetadataNodes( metadataNodes ) {

			const metadataData = {};

			for ( let i = 0; i < metadataNodes.length; i ++ ) {

				const metadataNode = metadataNodes[ i ];
				const name = metadataNode.getAttribute( 'name' );
				const validNames = [
					'Title',
					'Designer',
					'Description',
					'Copyright',
					'LicenseTerms',
					'Rating',
					'CreationDate',
					'ModificationDate'
				];

				if ( 0 <= validNames.indexOf( name ) ) {

					metadataData[ name ] = metadataNode.textContent;

				}

			}

			return metadataData;

		}

		function parseBasematerialsNode( basematerialsNode ) {

			const basematerialsData = {
				id: basematerialsNode.getAttribute( 'id' ), // required
				basematerials: []
			};

			const basematerialNodes = basematerialsNode.querySelectorAll( 'base' );

			for ( let i = 0; i < basematerialNodes.length; i ++ ) {

				const basematerialNode = basematerialNodes[ i ];
				const basematerialData = parseBasematerialNode( basematerialNode );
				basematerialData.index = i; // the order and count of the material nodes form an implicit 0-based index
				basematerialsData.basematerials.push( basematerialData );

			}

			return basematerialsData;

		}

		function parseTexture2DNode( texture2DNode ) {

			const texture2dData = {
				id: texture2DNode.getAttribute( 'id' ), // required
				path: texture2DNode.getAttribute( 'path' ), // required
				contenttype: texture2DNode.getAttribute( 'contenttype' ), // required
				tilestyleu: texture2DNode.getAttribute( 'tilestyleu' ),
				tilestylev: texture2DNode.getAttribute( 'tilestylev' ),
				filter: texture2DNode.getAttribute( 'filter' ),
			};

			return texture2dData;

		}

		function parseTextures2DGroupNode( texture2DGroupNode ) {

			const texture2DGroupData = {
				id: texture2DGroupNode.getAttribute( 'id' ), // required
				texid: texture2DGroupNode.getAttribute( 'texid' ), // required
				displaypropertiesid: texture2DGroupNode.getAttribute( 'displaypropertiesid' )
			};

			const tex2coordNodes = texture2DGroupNode.querySelectorAll( 'tex2coord' );

			const uvs = [];

			for ( let i = 0; i < tex2coordNodes.length; i ++ ) {

				const tex2coordNode = tex2coordNodes[ i ];
				const u = tex2coordNode.getAttribute( 'u' );
				const v = tex2coordNode.getAttribute( 'v' );

				uvs.push( parseFloat( u ), parseFloat( v ) );

			}

			texture2DGroupData[ 'uvs' ] = new Float32Array( uvs );

			return texture2DGroupData;

		}

		function parseColorGroupNode( colorGroupNode ) {

			const colorGroupData = {
				id: colorGroupNode.getAttribute( 'id' ), // required
				displaypropertiesid: colorGroupNode.getAttribute( 'displaypropertiesid' )
			};

			const colorNodes = colorGroupNode.querySelectorAll( 'color' );

			const colors = [];
			const colorObject = new Color();

			for ( let i = 0; i < colorNodes.length; i ++ ) {

				const colorNode = colorNodes[ i ];
				const color = colorNode.getAttribute( 'color' );

				colorObject.setStyle( color.substring( 0, 7 ), COLOR_SPACE_3MF );

				colors.push( colorObject.r, colorObject.g, colorObject.b );

			}

			colorGroupData[ 'colors' ] = new Float32Array( colors );

			return colorGroupData;

		}

		function parseImplicitIONode( implicitIONode ) {

			const portNodes = implicitIONode.children;
			const portArguments = {};
			for ( let i = 0; i < portNodes.length; i ++ ) {

				const args = { type: portNodes[ i ].nodeName.substring( 2 ) };
				for ( let j = 0; j < portNodes[ i ].attributes.length; j ++ ) {

					const attrib = portNodes[ i ].attributes[ j ];
					if ( attrib.specified ) {

		 				args[ attrib.name ] = attrib.value;

					}

				}

				portArguments[ portNodes[ i ].getAttribute( 'identifier' ) ] = args;

			}

			return portArguments;

		}

		function parseImplicitFunctionNode( implicitFunctionNode ) {

			const implicitFunctionData = {
				id: implicitFunctionNode.getAttribute( 'id' ),
				displayname: implicitFunctionNode.getAttribute( 'displayname' )
			};

			const functionNodes = implicitFunctionNode.children;

			const operations = {};

			for ( let i = 0; i < functionNodes.length; i ++ ) {

				const operatorNode = functionNodes[ i ];

				if ( operatorNode.nodeName === 'i:in' || operatorNode.nodeName === 'i:out' ) {

					operations[ operatorNode.nodeName === 'i:in' ? 'inputs' : 'outputs' ] = parseImplicitIONode( operatorNode );

				} else {

					const inputNodes = operatorNode.children;
					const portArguments = { 'op': operatorNode.nodeName.substring( 2 ), 'identifier': operatorNode.getAttribute( 'identifier' ) };
					for ( let i = 0; i < inputNodes.length; i ++ ) {

						portArguments[ inputNodes[ i ].nodeName.substring( 2 ) ] = parseImplicitIONode( inputNodes[ i ] );

					}

					operations[ portArguments[ 'identifier' ] ] = portArguments;

				}

			}

			implicitFunctionData[ 'operations' ] = operations;

			return implicitFunctionData;

		}

		function parseMetallicDisplaypropertiesNode( metallicDisplaypropetiesNode ) {

			const metallicDisplaypropertiesData = {
				id: metallicDisplaypropetiesNode.getAttribute( 'id' ) // required
			};

			const metallicNodes = metallicDisplaypropetiesNode.querySelectorAll( 'pbmetallic' );

			const metallicData = [];

			for ( let i = 0; i < metallicNodes.length; i ++ ) {

				const metallicNode = metallicNodes[ i ];

				metallicData.push( {
					name: metallicNode.getAttribute( 'name' ), // required
					metallicness: parseFloat( metallicNode.getAttribute( 'metallicness' ) ), // required
					roughness: parseFloat( metallicNode.getAttribute( 'roughness' ) ) // required
				} );

			}

			metallicDisplaypropertiesData.data = metallicData;

			return metallicDisplaypropertiesData;

		}

		function parseBasematerialNode( basematerialNode ) {

			const basematerialData = {};

			basematerialData[ 'name' ] = basematerialNode.getAttribute( 'name' ); // required
			basematerialData[ 'displaycolor' ] = basematerialNode.getAttribute( 'displaycolor' ); // required
			basematerialData[ 'displaypropertiesid' ] = basematerialNode.getAttribute( 'displaypropertiesid' );

			return basematerialData;

		}

		function parseMeshNode( meshNode ) {

			const meshData = {};

			const vertices = [];
			const vertexNodes = meshNode.querySelectorAll( 'vertices vertex' );

			for ( let i = 0; i < vertexNodes.length; i ++ ) {

				const vertexNode = vertexNodes[ i ];
				const x = vertexNode.getAttribute( 'x' );
				const y = vertexNode.getAttribute( 'y' );
				const z = vertexNode.getAttribute( 'z' );

				vertices.push( parseFloat( x ), parseFloat( y ), parseFloat( z ) );

			}

			meshData[ 'vertices' ] = new Float32Array( vertices );

			const triangleProperties = [];
			const triangles = [];
			const triangleNodes = meshNode.querySelectorAll( 'triangles triangle' );

			for ( let i = 0; i < triangleNodes.length; i ++ ) {

				const triangleNode = triangleNodes[ i ];
				const v1 = triangleNode.getAttribute( 'v1' );
				const v2 = triangleNode.getAttribute( 'v2' );
				const v3 = triangleNode.getAttribute( 'v3' );
				const p1 = triangleNode.getAttribute( 'p1' );
				const p2 = triangleNode.getAttribute( 'p2' );
				const p3 = triangleNode.getAttribute( 'p3' );
				const pid = triangleNode.getAttribute( 'pid' );

				const triangleProperty = {};

				triangleProperty[ 'v1' ] = parseInt( v1, 10 );
				triangleProperty[ 'v2' ] = parseInt( v2, 10 );
				triangleProperty[ 'v3' ] = parseInt( v3, 10 );

				triangles.push( triangleProperty[ 'v1' ], triangleProperty[ 'v2' ], triangleProperty[ 'v3' ] );

				// optional

				if ( p1 ) {

					triangleProperty[ 'p1' ] = parseInt( p1, 10 );

				}

				if ( p2 ) {

					triangleProperty[ 'p2' ] = parseInt( p2, 10 );

				}

				if ( p3 ) {

					triangleProperty[ 'p3' ] = parseInt( p3, 10 );

				}

				if ( pid ) {

					triangleProperty[ 'pid' ] = pid;

				}

				if ( 0 < Object.keys( triangleProperty ).length ) {

					triangleProperties.push( triangleProperty );

				}

			}

			meshData[ 'triangleProperties' ] = triangleProperties;
			meshData[ 'triangles' ] = new Uint32Array( triangles );

			return meshData;

		}

		function parseComponentsNode( componentsNode ) {

			const components = [];

			const componentNodes = componentsNode.querySelectorAll( 'component' );

			for ( let i = 0; i < componentNodes.length; i ++ ) {

				const componentNode = componentNodes[ i ];
				const componentData = parseComponentNode( componentNode );
				components.push( componentData );

			}

			return components;

		}

		function parseComponentNode( componentNode ) {

			const componentData = {};

			componentData[ 'objectId' ] = componentNode.getAttribute( 'objectid' ); // required

			const transform = componentNode.getAttribute( 'transform' );

			if ( transform ) {

				componentData[ 'transform' ] = parseTransform( transform );

			}

			return componentData;

		}

		function parseTransform( transform ) {

			const t = [];
			transform.split( ' ' ).forEach( function ( s ) {

				t.push( parseFloat( s ) );

			} );

			const matrix = new Matrix4();
			matrix.set(
				t[ 0 ], t[ 3 ], t[ 6 ], t[ 9 ],
				t[ 1 ], t[ 4 ], t[ 7 ], t[ 10 ],
				t[ 2 ], t[ 5 ], t[ 8 ], t[ 11 ],
				 0.0, 0.0, 0.0, 1.0
			);

			return matrix;

		}

		function parseObjectNode( objectNode ) {

			const objectData = {
				type: objectNode.getAttribute( 'type' )
			};

			const id = objectNode.getAttribute( 'id' );

			if ( id ) {

				objectData[ 'id' ] = id;

			}

			const pid = objectNode.getAttribute( 'pid' );

			if ( pid ) {

				objectData[ 'pid' ] = pid;

			}

			const pindex = objectNode.getAttribute( 'pindex' );

			if ( pindex ) {

				objectData[ 'pindex' ] = pindex;

			}

			const thumbnail = objectNode.getAttribute( 'thumbnail' );

			if ( thumbnail ) {

				objectData[ 'thumbnail' ] = thumbnail;

			}

			const partnumber = objectNode.getAttribute( 'partnumber' );

			if ( partnumber ) {

				objectData[ 'partnumber' ] = partnumber;

			}

			const name = objectNode.getAttribute( 'name' );

			if ( name ) {

				objectData[ 'name' ] = name;

			}

			const meshNode = objectNode.querySelector( 'mesh' );

			if ( meshNode ) {

				objectData[ 'mesh' ] = parseMeshNode( meshNode );

			}

			const componentsNode = objectNode.querySelector( 'components' );

			if ( componentsNode ) {

				objectData[ 'components' ] = parseComponentsNode( componentsNode );

			}

			return objectData;

		}

		function parseResourcesNode( resourcesNode ) {

			const resourcesData = {};

			resourcesData[ 'basematerials' ] = {};
			const basematerialsNodes = resourcesNode.querySelectorAll( 'basematerials' );

			for ( let i = 0; i < basematerialsNodes.length; i ++ ) {

				const basematerialsNode = basematerialsNodes[ i ];
				const basematerialsData = parseBasematerialsNode( basematerialsNode );
				resourcesData[ 'basematerials' ][ basematerialsData[ 'id' ] ] = basematerialsData;

			}

			//

			resourcesData[ 'texture2d' ] = {};
			const textures2DNodes = resourcesNode.querySelectorAll( 'texture2d' );

			for ( let i = 0; i < textures2DNodes.length; i ++ ) {

				const textures2DNode = textures2DNodes[ i ];
				const texture2DData = parseTexture2DNode( textures2DNode );
				resourcesData[ 'texture2d' ][ texture2DData[ 'id' ] ] = texture2DData;

			}

			//

			resourcesData[ 'colorgroup' ] = {};
			const colorGroupNodes = resourcesNode.querySelectorAll( 'colorgroup' );

			for ( let i = 0; i < colorGroupNodes.length; i ++ ) {

				const colorGroupNode = colorGroupNodes[ i ];
				const colorGroupData = parseColorGroupNode( colorGroupNode );
				resourcesData[ 'colorgroup' ][ colorGroupData[ 'id' ] ] = colorGroupData;

			}

			//

			const implicitFunctionNodes = resourcesNode.querySelectorAll( 'implicitfunction' );

			if ( implicitFunctionNodes.length > 0 ) {

				resourcesData[ 'implicitfunction' ] = {};

			}


			for ( let i = 0; i < implicitFunctionNodes.length; i ++ ) {

				const implicitFunctionNode = implicitFunctionNodes[ i ];
				const implicitFunctionData = parseImplicitFunctionNode( implicitFunctionNode );
				resourcesData[ 'implicitfunction' ][ implicitFunctionData[ 'id' ] ] = implicitFunctionData;

			}

			//

			resourcesData[ 'pbmetallicdisplayproperties' ] = {};
			const pbmetallicdisplaypropertiesNodes = resourcesNode.querySelectorAll( 'pbmetallicdisplayproperties' );

			for ( let i = 0; i < pbmetallicdisplaypropertiesNodes.length; i ++ ) {

				const pbmetallicdisplaypropertiesNode = pbmetallicdisplaypropertiesNodes[ i ];
				const pbmetallicdisplaypropertiesData = parseMetallicDisplaypropertiesNode( pbmetallicdisplaypropertiesNode );
				resourcesData[ 'pbmetallicdisplayproperties' ][ pbmetallicdisplaypropertiesData[ 'id' ] ] = pbmetallicdisplaypropertiesData;

			}

			//

			resourcesData[ 'texture2dgroup' ] = {};
			const textures2DGroupNodes = resourcesNode.querySelectorAll( 'texture2dgroup' );

			for ( let i = 0; i < textures2DGroupNodes.length; i ++ ) {

				const textures2DGroupNode = textures2DGroupNodes[ i ];
				const textures2DGroupData = parseTextures2DGroupNode( textures2DGroupNode );
				resourcesData[ 'texture2dgroup' ][ textures2DGroupData[ 'id' ] ] = textures2DGroupData;

			}

			//

			resourcesData[ 'object' ] = {};
			const objectNodes = resourcesNode.querySelectorAll( 'object' );

			for ( let i = 0; i < objectNodes.length; i ++ ) {

				const objectNode = objectNodes[ i ];
				const objectData = parseObjectNode( objectNode );
				resourcesData[ 'object' ][ objectData[ 'id' ] ] = objectData;

			}

			return resourcesData;

		}

		function parseBuildNode( buildNode ) {

			const buildData = [];
			const itemNodes = buildNode.querySelectorAll( 'item' );

			for ( let i = 0; i < itemNodes.length; i ++ ) {

				const itemNode = itemNodes[ i ];
				const buildItem = {
					objectId: itemNode.getAttribute( 'objectid' )
				};
				const transform = itemNode.getAttribute( 'transform' );

				if ( transform ) {

					buildItem[ 'transform' ] = parseTransform( transform );

				}

				buildData.push( buildItem );

			}

			return buildData;

		}

		function parseModelNode( modelNode ) {

			const modelData = { unit: modelNode.getAttribute( 'unit' ) || 'millimeter' };
			const metadataNodes = modelNode.querySelectorAll( 'metadata' );

			if ( metadataNodes ) {

				modelData[ 'metadata' ] = parseMetadataNodes( metadataNodes );

			}

			const resourcesNode = modelNode.querySelector( 'resources' );

			if ( resourcesNode ) {

				modelData[ 'resources' ] = parseResourcesNode( resourcesNode );

			}

			const buildNode = modelNode.querySelector( 'build' );

			if ( buildNode ) {

				modelData[ 'build' ] = parseBuildNode( buildNode );

			}

			return modelData;

		}

		function buildTexture( texture2dgroup, objects, modelData, textureData ) {

			const texid = texture2dgroup.texid;
			const texture2ds = modelData.resources.texture2d;
			const texture2d = texture2ds[ texid ];

			if ( texture2d ) {

				const data = textureData[ texture2d.path ];
				const type = texture2d.contenttype;

				const blob = new Blob( [ data ], { type: type } );
				const sourceURI = URL.createObjectURL( blob );

				const texture = textureLoader.load( sourceURI, function () {

					URL.revokeObjectURL( sourceURI );

				} );

				texture.colorSpace = COLOR_SPACE_3MF;

				// texture parameters

				switch ( texture2d.tilestyleu ) {

					case 'wrap':
						texture.wrapS = RepeatWrapping;
						break;

					case 'mirror':
						texture.wrapS = MirroredRepeatWrapping;
						break;

					case 'none':
					case 'clamp':
						texture.wrapS = ClampToEdgeWrapping;
						break;

					default:
						texture.wrapS = RepeatWrapping;

				}

				switch ( texture2d.tilestylev ) {

					case 'wrap':
						texture.wrapT = RepeatWrapping;
						break;

					case 'mirror':
						texture.wrapT = MirroredRepeatWrapping;
						break;

					case 'none':
					case 'clamp':
						texture.wrapT = ClampToEdgeWrapping;
						break;

					default:
						texture.wrapT = RepeatWrapping;

				}

				switch ( texture2d.filter ) {

					case 'auto':
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearMipmapLinearFilter;
						break;

					case 'linear':
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearFilter;
						texture.generateMipmaps = false;
						break;

					case 'nearest':
						texture.magFilter = NearestFilter;
						texture.minFilter = NearestFilter;
						texture.generateMipmaps = false;
						break;

					default:
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearMipmapLinearFilter;

				}

				return texture;

			} else {

				return null;

			}

		}

		function buildBasematerialsMeshes( basematerials, triangleProperties, meshData, objects, modelData, textureData, objectData ) {

			const objectPindex = objectData.pindex;

			const materialMap = {};

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];
				const pindex = ( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectPindex;

				if ( materialMap[ pindex ] === undefined ) materialMap[ pindex ] = [];

				materialMap[ pindex ].push( triangleProperty );

			}

			//

			const keys = Object.keys( materialMap );
			const meshes = [];

			for ( let i = 0, l = keys.length; i < l; i ++ ) {

				const materialIndex = keys[ i ];
				const trianglePropertiesProps = materialMap[ materialIndex ];
				const basematerialData = basematerials.basematerials[ materialIndex ];
				const material = getBuild( basematerialData, objects, modelData, textureData, objectData, buildBasematerial );

				//

				const geometry = new BufferGeometry();

				const positionData = [];

				const vertices = meshData.vertices;

				for ( let j = 0, jl = trianglePropertiesProps.length; j < jl; j ++ ) {

					const triangleProperty = trianglePropertiesProps[ j ];

					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 2 ] );

					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 2 ] );

					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 2 ] );


				}

				geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );

				//

				const mesh = new Mesh( geometry, material );
				meshes.push( mesh );

			}

			return meshes;

		}

		function buildTexturedMesh( texture2dgroup, triangleProperties, meshData, objects, modelData, textureData, objectData ) {

			// geometry

			const geometry = new BufferGeometry();

			const positionData = [];
			const uvData = [];

			const vertices = meshData.vertices;
			const uvs = texture2dgroup.uvs;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];

				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 2 ] );

				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 2 ] );

				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 2 ] );

				//

				uvData.push( uvs[ ( triangleProperty.p1 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p1 * 2 ) + 1 ] );

				uvData.push( uvs[ ( triangleProperty.p2 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p2 * 2 ) + 1 ] );

				uvData.push( uvs[ ( triangleProperty.p3 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p3 * 2 ) + 1 ] );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );
			geometry.setAttribute( 'uv', new Float32BufferAttribute( uvData, 2 ) );

			// material

			const texture = getBuild( texture2dgroup, objects, modelData, textureData, objectData, buildTexture );

			const material = new MeshPhongMaterial( { map: texture, flatShading: true } );

			// mesh

			const mesh = new Mesh( geometry, material );

			return mesh;

		}

		function buildVertexColorMesh( colorgroup, triangleProperties, meshData, objectData ) {

			// geometry

			const geometry = new BufferGeometry();

			const positionData = [];
			const colorData = [];

			const vertices = meshData.vertices;
			const colors = colorgroup.colors;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];

				const v1 = triangleProperty.v1;
				const v2 = triangleProperty.v2;
				const v3 = triangleProperty.v3;

				positionData.push( vertices[ ( v1 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v1 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v1 * 3 ) + 2 ] );

				positionData.push( vertices[ ( v2 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v2 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v2 * 3 ) + 2 ] );

				positionData.push( vertices[ ( v3 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v3 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v3 * 3 ) + 2 ] );

				//

				const p1 = ( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectData.pindex;
				const p2 = ( triangleProperty.p2 !== undefined ) ? triangleProperty.p2 : p1;
				const p3 = ( triangleProperty.p3 !== undefined ) ? triangleProperty.p3 : p1;

				colorData.push( colors[ ( p1 * 3 ) + 0 ] );
				colorData.push( colors[ ( p1 * 3 ) + 1 ] );
				colorData.push( colors[ ( p1 * 3 ) + 2 ] );

				colorData.push( colors[ ( p2 * 3 ) + 0 ] );
				colorData.push( colors[ ( p2 * 3 ) + 1 ] );
				colorData.push( colors[ ( p2 * 3 ) + 2 ] );

				colorData.push( colors[ ( p3 * 3 ) + 0 ] );
				colorData.push( colors[ ( p3 * 3 ) + 1 ] );
				colorData.push( colors[ ( p3 * 3 ) + 2 ] );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );
			geometry.setAttribute( 'color', new Float32BufferAttribute( colorData, 3 ) );

			// material

			const material = new MeshPhongMaterial( { vertexColors: true, flatShading: true } );

			// mesh

			const mesh = new Mesh( geometry, material );

			return mesh;

		}

		function buildDefaultMesh( meshData ) {

			const geometry = new BufferGeometry();
			geometry.setIndex( new BufferAttribute( meshData[ 'triangles' ], 1 ) );
			geometry.setAttribute( 'position', new BufferAttribute( meshData[ 'vertices' ], 3 ) );

			const material = new MeshPhongMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0xffffff,
				flatShading: true
			} );

			const mesh = new Mesh( geometry, material );

			return mesh;

		}

		function buildMeshes( resourceMap, meshData, objects, modelData, textureData, objectData ) {

			const keys = Object.keys( resourceMap );
			const meshes = [];

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				const resourceId = keys[ i ];
				const triangleProperties = resourceMap[ resourceId ];
				const resourceType = getResourceType( resourceId, modelData );

				switch ( resourceType ) {

					case 'material':
						const basematerials = modelData.resources.basematerials[ resourceId ];
						const newMeshes = buildBasematerialsMeshes( basematerials, triangleProperties, meshData, objects, modelData, textureData, objectData );

						for ( let j = 0, jl = newMeshes.length; j < jl; j ++ ) {

							meshes.push( newMeshes[ j ] );

						}

						break;

					case 'texture':
						const texture2dgroup = modelData.resources.texture2dgroup[ resourceId ];
						meshes.push( buildTexturedMesh( texture2dgroup, triangleProperties, meshData, objects, modelData, textureData, objectData ) );
						break;

					case 'vertexColors':
						const colorgroup = modelData.resources.colorgroup[ resourceId ];
						meshes.push( buildVertexColorMesh( colorgroup, triangleProperties, meshData, objectData ) );
						break;

					case 'default':
						meshes.push( buildDefaultMesh( meshData ) );
						break;

					default:
						console.error( 'THREE.3MFLoader: Unsupported resource type.' );

				}

			}

			if ( objectData.name ) {

				for ( let i = 0; i < meshes.length; i ++ ) {

					meshes[ i ].name = objectData.name;

				}

			}

			return meshes;

		}

		function getResourceType( pid, modelData ) {

			if ( modelData.resources.texture2dgroup[ pid ] !== undefined ) {

				return 'texture';

			} else if ( modelData.resources.basematerials[ pid ] !== undefined ) {

				return 'material';

			} else if ( modelData.resources.colorgroup[ pid ] !== undefined ) {

				return 'vertexColors';

			} else if ( pid === 'default' ) {

				return 'default';

			} else {

				return undefined;

			}

		}

		function analyzeObject( meshData, objectData ) {

			const resourceMap = {};

			const triangleProperties = meshData[ 'triangleProperties' ];

			const objectPid = objectData.pid;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];
				let pid = ( triangleProperty.pid !== undefined ) ? triangleProperty.pid : objectPid;

				if ( pid === undefined ) pid = 'default';

				if ( resourceMap[ pid ] === undefined ) resourceMap[ pid ] = [];

				resourceMap[ pid ].push( triangleProperty );

			}

			return resourceMap;

		}

		function buildGroup( meshData, objects, modelData, textureData, objectData ) {

			const group = new Group();

			const resourceMap = analyzeObject( meshData, objectData );
			const meshes = buildMeshes( resourceMap, meshData, objects, modelData, textureData, objectData );

			for ( let i = 0, l = meshes.length; i < l; i ++ ) {

				group.add( meshes[ i ] );

			}

			return group;

		}

		function applyExtensions( extensions, meshData, modelXml ) {

			if ( ! extensions ) {

				return;

			}

			const availableExtensions = [];
			const keys = Object.keys( extensions );

			for ( let i = 0; i < keys.length; i ++ ) {

				const ns = keys[ i ];

				for ( let j = 0; j < scope.availableExtensions.length; j ++ ) {

					const extension = scope.availableExtensions[ j ];

					if ( extension.ns === ns ) {

						availableExtensions.push( extension );

					}

				}

			}

			for ( let i = 0; i < availableExtensions.length; i ++ ) {

				const extension = availableExtensions[ i ];
				extension.apply( modelXml, extensions[ extension[ 'ns' ] ], meshData );

			}

		}

		function getBuild( data, objects, modelData, textureData, objectData, builder ) {

			if ( data.build !== undefined ) return data.build;

			data.build = builder( data, objects, modelData, textureData, objectData );

			return data.build;

		}

		function buildBasematerial( materialData, objects, modelData ) {

			let material;

			const displaypropertiesid = materialData.displaypropertiesid;
			const pbmetallicdisplayproperties = modelData.resources.pbmetallicdisplayproperties;

			if ( displaypropertiesid !== null && pbmetallicdisplayproperties[ displaypropertiesid ] !== undefined ) {

				// metallic display property, use StandardMaterial

				const pbmetallicdisplayproperty = pbmetallicdisplayproperties[ displaypropertiesid ];
				const metallicData = pbmetallicdisplayproperty.data[ materialData.index ];

				material = new MeshStandardMaterial( { flatShading: true, roughness: metallicData.roughness, metalness: metallicData.metallicness } );

			} else {

				// otherwise use PhongMaterial

				material = new MeshPhongMaterial( { flatShading: true } );

			}

			material.name = materialData.name;

			// displaycolor MUST be specified with a value of a 6 or 8 digit hexadecimal number, e.g. "#RRGGBB" or "#RRGGBBAA"

			const displaycolor = materialData.displaycolor;

			const color = displaycolor.substring( 0, 7 );
			material.color.setStyle( color, COLOR_SPACE_3MF );

			// process alpha if set

			if ( displaycolor.length === 9 ) {

				material.opacity = parseInt( displaycolor.charAt( 7 ) + displaycolor.charAt( 8 ), 16 ) / 255;

			}

			return material;

		}

		function buildComposite( compositeData, objects, modelData, textureData ) {

			const composite = new Group();

			for ( let j = 0; j < compositeData.length; j ++ ) {

				const component = compositeData[ j ];
				let build = objects[ component.objectId ];

				if ( build === undefined ) {

					buildObject( component.objectId, objects, modelData, textureData );
					build = objects[ component.objectId ];

				}

				const object3D = build.clone();

				// apply component transform

				const transform = component.transform;

				if ( transform ) {

					object3D.applyMatrix4( transform );

				}

				composite.add( object3D );

			}

			return composite;

		}

		function buildObject( objectId, objects, modelData, textureData ) {

			const objectData = modelData[ 'resources' ][ 'object' ][ objectId ];

			if ( objectData[ 'mesh' ] ) {

				const meshData = objectData[ 'mesh' ];

				const extensions = modelData[ 'extensions' ];
				const modelXml = modelData[ 'xml' ];

				applyExtensions( extensions, meshData, modelXml );

				objects[ objectData.id ] = getBuild( meshData, objects, modelData, textureData, objectData, buildGroup );

			} else {

				const compositeData = objectData[ 'components' ];

				objects[ objectData.id ] = getBuild( compositeData, objects, modelData, textureData, objectData, buildComposite );

			}

			if ( objectData.name ) {

				objects[ objectData.id ].name = objectData.name;

			}

			if ( modelData.resources.implicitfunction ) {

				console.warn( 'THREE.ThreeMFLoader: Implicit Functions are implemented in data-only.', modelData.resources.implicitfunction );

			}

		}

		function buildObjects( data3mf ) {

			const modelsData = data3mf.model;
			const modelRels = data3mf.modelRels;
			const objects = {};
			const modelsKeys = Object.keys( modelsData );
			const textureData = {};

			// evaluate model relationships to textures

			if ( modelRels ) {

				for ( let i = 0, l = modelRels.length; i < l; i ++ ) {

					const modelRel = modelRels[ i ];
					const textureKey = modelRel.target.substring( 1 );

					if ( data3mf.texture[ textureKey ] ) {

						textureData[ modelRel.target ] = data3mf.texture[ textureKey ];

					}

				}

			}

			// start build

			for ( let i = 0; i < modelsKeys.length; i ++ ) {

				const modelsKey = modelsKeys[ i ];
				const modelData = modelsData[ modelsKey ];

				const objectIds = Object.keys( modelData[ 'resources' ][ 'object' ] );

				for ( let j = 0; j < objectIds.length; j ++ ) {

					const objectId = objectIds[ j ];

					buildObject( objectId, objects, modelData, textureData );

				}

			}

			return objects;

		}

		function fetch3DModelPart( rels ) {

			for ( let i = 0; i < rels.length; i ++ ) {

				const rel = rels[ i ];
				const extension = rel.target.split( '.' ).pop();

				if ( extension.toLowerCase() === 'model' ) return rel;

			}

		}

		function build( objects, data3mf ) {

			const group = new Group();

			const relationship = fetch3DModelPart( data3mf[ 'rels' ] );
			const buildData = data3mf.model[ relationship[ 'target' ].substring( 1 ) ][ 'build' ];

			for ( let i = 0; i < buildData.length; i ++ ) {

				const buildItem = buildData[ i ];
				const object3D = objects[ buildItem[ 'objectId' ] ].clone();

				// apply transform

				const transform = buildItem[ 'transform' ];

				if ( transform ) {

					object3D.applyMatrix4( transform );

				}

				group.add( object3D );

			}

			return group;

		}

		const data3mf = loadDocument( data );
		const objects = buildObjects( data3mf );

		return build( objects, data3mf );

	}
```
</details>

### `ThreeMFLoader.addExtension(extension: any): void`

**JSDoc:**
```typescript
/**
	 * Adds a 3MF extension.
	 *
	 * @param {Object} extension - The extension to add.
	 */
```

**Parameters:**

- **`extension`** `any`

**Returns:** `void`

**Calls:**

- `this.availableExtensions.push`

<details><summary>Code</summary>

```typescript
addExtension( extension ) {

		this.availableExtensions.push( extension );

	}
```
</details>

### `loadDocument(data: any): { rels: { target: string; id: string; type: string; }[]; modelRels: { target: string; id: string; type: string; }[]; model: {}; printTicket: {}; texture: {}; }`

**Parameters:**

- **`data`** `any`

**Returns:** `{ rels: { target: string; id: string; type: string; }[]; modelRels: { target: string; id: string; type: string; }[]; model: {}; printTicket: {}; texture: {}; }`

**Calls:**

- `fflate.unzipSync`
- `console.error`
- `file.match`
- `modelPartNames.push`
- `texturesPartNames.push`
- `textDecoder.decode`
- `parseRelsXml`
- `new DOMParser().parseFromString`
- `xmlData.documentElement.nodeName.toLowerCase`
- `xmlData.querySelector`
- `attr.name.match`
- `parseModelNode`
- `Object.keys`

**Internal Comments:**
```
// (x5)
```

<details><summary>Code</summary>

```typescript
function loadDocument( data ) {

			let zip = null;
			let file = null;

			let relsName;
			let modelRelsName;
			const modelPartNames = [];
			const texturesPartNames = [];

			let modelRels;
			const modelParts = {};
			const printTicketParts = {};
			const texturesParts = {};

			const textDecoder = new TextDecoder();

			try {

				zip = fflate.unzipSync( new Uint8Array( data ) );

			} catch ( e ) {

				if ( e instanceof ReferenceError ) {

					console.error( 'THREE.3MFLoader: fflate missing and file is compressed.' );
					return null;

				}

			}

			let rootModelFile = null;

			for ( file in zip ) {

				if ( file.match( /\_rels\/.rels$/ ) ) {

					relsName = file;

				} else if ( file.match( /3D\/_rels\/.*\.model\.rels$/ ) ) {

					modelRelsName = file;

				} else if ( file.match( /^3D\/[^\/]*\.model$/ ) ) {

					rootModelFile = file;

				} else if ( file.match( /^3D\/.*\/.*\.model$/ ) ) {

					modelPartNames.push( file ); // sub models

				} else if ( file.match( /^3D\/Textures?\/.*/ ) ) {

					texturesPartNames.push( file );

				}

			}

			modelPartNames.push( rootModelFile ); // push root model at the end so it is processed after the sub models

			if ( relsName === undefined ) throw new Error( 'THREE.ThreeMFLoader: Cannot find relationship file `rels` in 3MF archive.' );

			//

			const relsView = zip[ relsName ];
			const relsFileText = textDecoder.decode( relsView );
			const rels = parseRelsXml( relsFileText );

			//

			if ( modelRelsName ) {

				const relsView = zip[ modelRelsName ];
				const relsFileText = textDecoder.decode( relsView );
				modelRels = parseRelsXml( relsFileText );

			}

			//

			for ( let i = 0; i < modelPartNames.length; i ++ ) {

				const modelPart = modelPartNames[ i ];
				const view = zip[ modelPart ];

				const fileText = textDecoder.decode( view );
				const xmlData = new DOMParser().parseFromString( fileText, 'application/xml' );

				if ( xmlData.documentElement.nodeName.toLowerCase() !== 'model' ) {

					console.error( 'THREE.3MFLoader: Error loading 3MF - no 3MF document found: ', modelPart );

				}

				const modelNode = xmlData.querySelector( 'model' );
				const extensions = {};

				for ( let i = 0; i < modelNode.attributes.length; i ++ ) {

					const attr = modelNode.attributes[ i ];
					if ( attr.name.match( /^xmlns:(.+)$/ ) ) {

						extensions[ attr.value ] = RegExp.$1;

					}

				}

				const modelData = parseModelNode( modelNode );
				modelData[ 'xml' ] = modelNode;

				if ( 0 < Object.keys( extensions ).length ) {

					modelData[ 'extensions' ] = extensions;

				}

				modelParts[ modelPart ] = modelData;

			}

			//

			for ( let i = 0; i < texturesPartNames.length; i ++ ) {

				const texturesPartName = texturesPartNames[ i ];
				texturesParts[ texturesPartName ] = zip[ texturesPartName ].buffer;

			}

			return {
				rels: rels,
				modelRels: modelRels,
				model: modelParts,
				printTicket: printTicketParts,
				texture: texturesParts
			};

		}
```
</details>

### `parseRelsXml(relsFileText: any): { target: string; id: string; type: string; }[]`

**Parameters:**

- **`relsFileText`** `any`

**Returns:** `{ target: string; id: string; type: string; }[]`

**Calls:**

- `new DOMParser().parseFromString`
- `relsXmlData.querySelectorAll`
- `relsNode.getAttribute`
- `relationships.push`

<details><summary>Code</summary>

```typescript
function parseRelsXml( relsFileText ) {

			const relationships = [];

			const relsXmlData = new DOMParser().parseFromString( relsFileText, 'application/xml' );

			const relsNodes = relsXmlData.querySelectorAll( 'Relationship' );

			for ( let i = 0; i < relsNodes.length; i ++ ) {

				const relsNode = relsNodes[ i ];

				const relationship = {
					target: relsNode.getAttribute( 'Target' ), //required
					id: relsNode.getAttribute( 'Id' ), //required
					type: relsNode.getAttribute( 'Type' ) //required
				};

				relationships.push( relationship );

			}

			return relationships;

		}
```
</details>

### `parseMetadataNodes(metadataNodes: any): {}`

**Parameters:**

- **`metadataNodes`** `any`

**Returns:** `{}`

**Calls:**

- `metadataNode.getAttribute`
- `validNames.indexOf`

<details><summary>Code</summary>

```typescript
function parseMetadataNodes( metadataNodes ) {

			const metadataData = {};

			for ( let i = 0; i < metadataNodes.length; i ++ ) {

				const metadataNode = metadataNodes[ i ];
				const name = metadataNode.getAttribute( 'name' );
				const validNames = [
					'Title',
					'Designer',
					'Description',
					'Copyright',
					'LicenseTerms',
					'Rating',
					'CreationDate',
					'ModificationDate'
				];

				if ( 0 <= validNames.indexOf( name ) ) {

					metadataData[ name ] = metadataNode.textContent;

				}

			}

			return metadataData;

		}
```
</details>

### `parseBasematerialsNode(basematerialsNode: any): { id: any; basematerials: any[]; }`

**Parameters:**

- **`basematerialsNode`** `any`

**Returns:** `{ id: any; basematerials: any[]; }`

**Calls:**

- `basematerialsNode.getAttribute`
- `basematerialsNode.querySelectorAll`
- `parseBasematerialNode`
- `basematerialsData.basematerials.push`

<details><summary>Code</summary>

```typescript
function parseBasematerialsNode( basematerialsNode ) {

			const basematerialsData = {
				id: basematerialsNode.getAttribute( 'id' ), // required
				basematerials: []
			};

			const basematerialNodes = basematerialsNode.querySelectorAll( 'base' );

			for ( let i = 0; i < basematerialNodes.length; i ++ ) {

				const basematerialNode = basematerialNodes[ i ];
				const basematerialData = parseBasematerialNode( basematerialNode );
				basematerialData.index = i; // the order and count of the material nodes form an implicit 0-based index
				basematerialsData.basematerials.push( basematerialData );

			}

			return basematerialsData;

		}
```
</details>

### `parseTexture2DNode(texture2DNode: any): { id: any; path: any; contenttype: any; tilestyleu: any; tilestylev: any; filter: any; }`

**Parameters:**

- **`texture2DNode`** `any`

**Returns:** `{ id: any; path: any; contenttype: any; tilestyleu: any; tilestylev: any; filter: any; }`

**Calls:**

- `texture2DNode.getAttribute`

<details><summary>Code</summary>

```typescript
function parseTexture2DNode( texture2DNode ) {

			const texture2dData = {
				id: texture2DNode.getAttribute( 'id' ), // required
				path: texture2DNode.getAttribute( 'path' ), // required
				contenttype: texture2DNode.getAttribute( 'contenttype' ), // required
				tilestyleu: texture2DNode.getAttribute( 'tilestyleu' ),
				tilestylev: texture2DNode.getAttribute( 'tilestylev' ),
				filter: texture2DNode.getAttribute( 'filter' ),
			};

			return texture2dData;

		}
```
</details>

### `parseTextures2DGroupNode(texture2DGroupNode: any): { id: any; texid: any; displaypropertiesid: any; }`

**Parameters:**

- **`texture2DGroupNode`** `any`

**Returns:** `{ id: any; texid: any; displaypropertiesid: any; }`

**Calls:**

- `texture2DGroupNode.getAttribute`
- `texture2DGroupNode.querySelectorAll`
- `tex2coordNode.getAttribute`
- `uvs.push`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function parseTextures2DGroupNode( texture2DGroupNode ) {

			const texture2DGroupData = {
				id: texture2DGroupNode.getAttribute( 'id' ), // required
				texid: texture2DGroupNode.getAttribute( 'texid' ), // required
				displaypropertiesid: texture2DGroupNode.getAttribute( 'displaypropertiesid' )
			};

			const tex2coordNodes = texture2DGroupNode.querySelectorAll( 'tex2coord' );

			const uvs = [];

			for ( let i = 0; i < tex2coordNodes.length; i ++ ) {

				const tex2coordNode = tex2coordNodes[ i ];
				const u = tex2coordNode.getAttribute( 'u' );
				const v = tex2coordNode.getAttribute( 'v' );

				uvs.push( parseFloat( u ), parseFloat( v ) );

			}

			texture2DGroupData[ 'uvs' ] = new Float32Array( uvs );

			return texture2DGroupData;

		}
```
</details>

### `parseColorGroupNode(colorGroupNode: any): { id: any; displaypropertiesid: any; }`

**Parameters:**

- **`colorGroupNode`** `any`

**Returns:** `{ id: any; displaypropertiesid: any; }`

**Calls:**

- `colorGroupNode.getAttribute`
- `colorGroupNode.querySelectorAll`
- `colorNode.getAttribute`
- `colorObject.setStyle`
- `color.substring`
- `colors.push`

<details><summary>Code</summary>

```typescript
function parseColorGroupNode( colorGroupNode ) {

			const colorGroupData = {
				id: colorGroupNode.getAttribute( 'id' ), // required
				displaypropertiesid: colorGroupNode.getAttribute( 'displaypropertiesid' )
			};

			const colorNodes = colorGroupNode.querySelectorAll( 'color' );

			const colors = [];
			const colorObject = new Color();

			for ( let i = 0; i < colorNodes.length; i ++ ) {

				const colorNode = colorNodes[ i ];
				const color = colorNode.getAttribute( 'color' );

				colorObject.setStyle( color.substring( 0, 7 ), COLOR_SPACE_3MF );

				colors.push( colorObject.r, colorObject.g, colorObject.b );

			}

			colorGroupData[ 'colors' ] = new Float32Array( colors );

			return colorGroupData;

		}
```
</details>

### `parseImplicitIONode(implicitIONode: any): {}`

**Parameters:**

- **`implicitIONode`** `any`

**Returns:** `{}`

**Calls:**

- `portNodes[ i ].nodeName.substring`
- `portNodes[ i ].getAttribute`

<details><summary>Code</summary>

```typescript
function parseImplicitIONode( implicitIONode ) {

			const portNodes = implicitIONode.children;
			const portArguments = {};
			for ( let i = 0; i < portNodes.length; i ++ ) {

				const args = { type: portNodes[ i ].nodeName.substring( 2 ) };
				for ( let j = 0; j < portNodes[ i ].attributes.length; j ++ ) {

					const attrib = portNodes[ i ].attributes[ j ];
					if ( attrib.specified ) {

		 				args[ attrib.name ] = attrib.value;

					}

				}

				portArguments[ portNodes[ i ].getAttribute( 'identifier' ) ] = args;

			}

			return portArguments;

		}
```
</details>

### `parseImplicitFunctionNode(implicitFunctionNode: any): { id: any; displayname: any; }`

**Parameters:**

- **`implicitFunctionNode`** `any`

**Returns:** `{ id: any; displayname: any; }`

**Calls:**

- `implicitFunctionNode.getAttribute`
- `parseImplicitIONode`
- `operatorNode.nodeName.substring`
- `operatorNode.getAttribute`
- `inputNodes[ i ].nodeName.substring`

<details><summary>Code</summary>

```typescript
function parseImplicitFunctionNode( implicitFunctionNode ) {

			const implicitFunctionData = {
				id: implicitFunctionNode.getAttribute( 'id' ),
				displayname: implicitFunctionNode.getAttribute( 'displayname' )
			};

			const functionNodes = implicitFunctionNode.children;

			const operations = {};

			for ( let i = 0; i < functionNodes.length; i ++ ) {

				const operatorNode = functionNodes[ i ];

				if ( operatorNode.nodeName === 'i:in' || operatorNode.nodeName === 'i:out' ) {

					operations[ operatorNode.nodeName === 'i:in' ? 'inputs' : 'outputs' ] = parseImplicitIONode( operatorNode );

				} else {

					const inputNodes = operatorNode.children;
					const portArguments = { 'op': operatorNode.nodeName.substring( 2 ), 'identifier': operatorNode.getAttribute( 'identifier' ) };
					for ( let i = 0; i < inputNodes.length; i ++ ) {

						portArguments[ inputNodes[ i ].nodeName.substring( 2 ) ] = parseImplicitIONode( inputNodes[ i ] );

					}

					operations[ portArguments[ 'identifier' ] ] = portArguments;

				}

			}

			implicitFunctionData[ 'operations' ] = operations;

			return implicitFunctionData;

		}
```
</details>

### `parseMetallicDisplaypropertiesNode(metallicDisplaypropetiesNode: any): { id: any; }`

**Parameters:**

- **`metallicDisplaypropetiesNode`** `any`

**Returns:** `{ id: any; }`

**Calls:**

- `metallicDisplaypropetiesNode.getAttribute`
- `metallicDisplaypropetiesNode.querySelectorAll`
- `metallicData.push`
- `metallicNode.getAttribute`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function parseMetallicDisplaypropertiesNode( metallicDisplaypropetiesNode ) {

			const metallicDisplaypropertiesData = {
				id: metallicDisplaypropetiesNode.getAttribute( 'id' ) // required
			};

			const metallicNodes = metallicDisplaypropetiesNode.querySelectorAll( 'pbmetallic' );

			const metallicData = [];

			for ( let i = 0; i < metallicNodes.length; i ++ ) {

				const metallicNode = metallicNodes[ i ];

				metallicData.push( {
					name: metallicNode.getAttribute( 'name' ), // required
					metallicness: parseFloat( metallicNode.getAttribute( 'metallicness' ) ), // required
					roughness: parseFloat( metallicNode.getAttribute( 'roughness' ) ) // required
				} );

			}

			metallicDisplaypropertiesData.data = metallicData;

			return metallicDisplaypropertiesData;

		}
```
</details>

### `parseBasematerialNode(basematerialNode: any): { name: any; displaycolor: any; displaypropertiesid: any; }`

**Parameters:**

- **`basematerialNode`** `any`

**Returns:** `{ name: any; displaycolor: any; displaypropertiesid: any; }`

**Calls:**

- `basematerialNode.getAttribute`

<details><summary>Code</summary>

```typescript
function parseBasematerialNode( basematerialNode ) {

			const basematerialData = {};

			basematerialData[ 'name' ] = basematerialNode.getAttribute( 'name' ); // required
			basematerialData[ 'displaycolor' ] = basematerialNode.getAttribute( 'displaycolor' ); // required
			basematerialData[ 'displaypropertiesid' ] = basematerialNode.getAttribute( 'displaypropertiesid' );

			return basematerialData;

		}
```
</details>

### `parseMeshNode(meshNode: any): { vertices: Float32Array<ArrayBuffer>; triangleProperties: { v1: number; v2: number; v3: number; }[]; triangles: Uint32Array<ArrayBuffer>; }`

**Parameters:**

- **`meshNode`** `any`

**Returns:** `{ vertices: Float32Array<ArrayBuffer>; triangleProperties: { v1: number; v2: number; v3: number; }[]; triangles: Uint32Array<ArrayBuffer>; }`

**Calls:**

- `meshNode.querySelectorAll`
- `vertexNode.getAttribute`
- `vertices.push`
- `parseFloat`
- `triangleNode.getAttribute`
- `parseInt`
- `triangles.push`
- `Object.keys`
- `triangleProperties.push`

**Internal Comments:**
```
// optional
```

<details><summary>Code</summary>

```typescript
function parseMeshNode( meshNode ) {

			const meshData = {};

			const vertices = [];
			const vertexNodes = meshNode.querySelectorAll( 'vertices vertex' );

			for ( let i = 0; i < vertexNodes.length; i ++ ) {

				const vertexNode = vertexNodes[ i ];
				const x = vertexNode.getAttribute( 'x' );
				const y = vertexNode.getAttribute( 'y' );
				const z = vertexNode.getAttribute( 'z' );

				vertices.push( parseFloat( x ), parseFloat( y ), parseFloat( z ) );

			}

			meshData[ 'vertices' ] = new Float32Array( vertices );

			const triangleProperties = [];
			const triangles = [];
			const triangleNodes = meshNode.querySelectorAll( 'triangles triangle' );

			for ( let i = 0; i < triangleNodes.length; i ++ ) {

				const triangleNode = triangleNodes[ i ];
				const v1 = triangleNode.getAttribute( 'v1' );
				const v2 = triangleNode.getAttribute( 'v2' );
				const v3 = triangleNode.getAttribute( 'v3' );
				const p1 = triangleNode.getAttribute( 'p1' );
				const p2 = triangleNode.getAttribute( 'p2' );
				const p3 = triangleNode.getAttribute( 'p3' );
				const pid = triangleNode.getAttribute( 'pid' );

				const triangleProperty = {};

				triangleProperty[ 'v1' ] = parseInt( v1, 10 );
				triangleProperty[ 'v2' ] = parseInt( v2, 10 );
				triangleProperty[ 'v3' ] = parseInt( v3, 10 );

				triangles.push( triangleProperty[ 'v1' ], triangleProperty[ 'v2' ], triangleProperty[ 'v3' ] );

				// optional

				if ( p1 ) {

					triangleProperty[ 'p1' ] = parseInt( p1, 10 );

				}

				if ( p2 ) {

					triangleProperty[ 'p2' ] = parseInt( p2, 10 );

				}

				if ( p3 ) {

					triangleProperty[ 'p3' ] = parseInt( p3, 10 );

				}

				if ( pid ) {

					triangleProperty[ 'pid' ] = pid;

				}

				if ( 0 < Object.keys( triangleProperty ).length ) {

					triangleProperties.push( triangleProperty );

				}

			}

			meshData[ 'triangleProperties' ] = triangleProperties;
			meshData[ 'triangles' ] = new Uint32Array( triangles );

			return meshData;

		}
```
</details>

### `parseComponentsNode(componentsNode: any): { objectId: any; transform: any; }[]`

**Parameters:**

- **`componentsNode`** `any`

**Returns:** `{ objectId: any; transform: any; }[]`

**Calls:**

- `componentsNode.querySelectorAll`
- `parseComponentNode`
- `components.push`

<details><summary>Code</summary>

```typescript
function parseComponentsNode( componentsNode ) {

			const components = [];

			const componentNodes = componentsNode.querySelectorAll( 'component' );

			for ( let i = 0; i < componentNodes.length; i ++ ) {

				const componentNode = componentNodes[ i ];
				const componentData = parseComponentNode( componentNode );
				components.push( componentData );

			}

			return components;

		}
```
</details>

### `parseComponentNode(componentNode: any): { objectId: any; transform: any; }`

**Parameters:**

- **`componentNode`** `any`

**Returns:** `{ objectId: any; transform: any; }`

**Calls:**

- `componentNode.getAttribute`
- `parseTransform`

<details><summary>Code</summary>

```typescript
function parseComponentNode( componentNode ) {

			const componentData = {};

			componentData[ 'objectId' ] = componentNode.getAttribute( 'objectid' ); // required

			const transform = componentNode.getAttribute( 'transform' );

			if ( transform ) {

				componentData[ 'transform' ] = parseTransform( transform );

			}

			return componentData;

		}
```
</details>

### `parseTransform(transform: any): any`

**Parameters:**

- **`transform`** `any`

**Returns:** `any`

**Calls:**

- `transform.split( ' ' ).forEach`
- `t.push`
- `parseFloat`
- `matrix.set`

<details><summary>Code</summary>

```typescript
function parseTransform( transform ) {

			const t = [];
			transform.split( ' ' ).forEach( function ( s ) {

				t.push( parseFloat( s ) );

			} );

			const matrix = new Matrix4();
			matrix.set(
				t[ 0 ], t[ 3 ], t[ 6 ], t[ 9 ],
				t[ 1 ], t[ 4 ], t[ 7 ], t[ 10 ],
				t[ 2 ], t[ 5 ], t[ 8 ], t[ 11 ],
				 0.0, 0.0, 0.0, 1.0
			);

			return matrix;

		}
```
</details>

### `parseObjectNode(objectNode: any): { type: any; }`

**Parameters:**

- **`objectNode`** `any`

**Returns:** `{ type: any; }`

**Calls:**

- `objectNode.getAttribute`
- `objectNode.querySelector`
- `parseMeshNode`
- `parseComponentsNode`

<details><summary>Code</summary>

```typescript
function parseObjectNode( objectNode ) {

			const objectData = {
				type: objectNode.getAttribute( 'type' )
			};

			const id = objectNode.getAttribute( 'id' );

			if ( id ) {

				objectData[ 'id' ] = id;

			}

			const pid = objectNode.getAttribute( 'pid' );

			if ( pid ) {

				objectData[ 'pid' ] = pid;

			}

			const pindex = objectNode.getAttribute( 'pindex' );

			if ( pindex ) {

				objectData[ 'pindex' ] = pindex;

			}

			const thumbnail = objectNode.getAttribute( 'thumbnail' );

			if ( thumbnail ) {

				objectData[ 'thumbnail' ] = thumbnail;

			}

			const partnumber = objectNode.getAttribute( 'partnumber' );

			if ( partnumber ) {

				objectData[ 'partnumber' ] = partnumber;

			}

			const name = objectNode.getAttribute( 'name' );

			if ( name ) {

				objectData[ 'name' ] = name;

			}

			const meshNode = objectNode.querySelector( 'mesh' );

			if ( meshNode ) {

				objectData[ 'mesh' ] = parseMeshNode( meshNode );

			}

			const componentsNode = objectNode.querySelector( 'components' );

			if ( componentsNode ) {

				objectData[ 'components' ] = parseComponentsNode( componentsNode );

			}

			return objectData;

		}
```
</details>

### `parseResourcesNode(resourcesNode: any): { basematerials: {}; texture2d: {}; colorgroup: {}; implicitfunction: {}; pbmetallicdisplayproperties: {}; texture2dgroup: {}; object: {}; }`

**Parameters:**

- **`resourcesNode`** `any`

**Returns:** `{ basematerials: {}; texture2d: {}; colorgroup: {}; implicitfunction: {}; pbmetallicdisplayproperties: {}; texture2dgroup: {}; object: {}; }`

**Calls:**

- `resourcesNode.querySelectorAll`
- `parseBasematerialsNode`
- `parseTexture2DNode`
- `parseColorGroupNode`
- `parseImplicitFunctionNode`
- `parseMetallicDisplaypropertiesNode`
- `parseTextures2DGroupNode`
- `parseObjectNode`

**Internal Comments:**
```
// (x22)
```

<details><summary>Code</summary>

```typescript
function parseResourcesNode( resourcesNode ) {

			const resourcesData = {};

			resourcesData[ 'basematerials' ] = {};
			const basematerialsNodes = resourcesNode.querySelectorAll( 'basematerials' );

			for ( let i = 0; i < basematerialsNodes.length; i ++ ) {

				const basematerialsNode = basematerialsNodes[ i ];
				const basematerialsData = parseBasematerialsNode( basematerialsNode );
				resourcesData[ 'basematerials' ][ basematerialsData[ 'id' ] ] = basematerialsData;

			}

			//

			resourcesData[ 'texture2d' ] = {};
			const textures2DNodes = resourcesNode.querySelectorAll( 'texture2d' );

			for ( let i = 0; i < textures2DNodes.length; i ++ ) {

				const textures2DNode = textures2DNodes[ i ];
				const texture2DData = parseTexture2DNode( textures2DNode );
				resourcesData[ 'texture2d' ][ texture2DData[ 'id' ] ] = texture2DData;

			}

			//

			resourcesData[ 'colorgroup' ] = {};
			const colorGroupNodes = resourcesNode.querySelectorAll( 'colorgroup' );

			for ( let i = 0; i < colorGroupNodes.length; i ++ ) {

				const colorGroupNode = colorGroupNodes[ i ];
				const colorGroupData = parseColorGroupNode( colorGroupNode );
				resourcesData[ 'colorgroup' ][ colorGroupData[ 'id' ] ] = colorGroupData;

			}

			//

			const implicitFunctionNodes = resourcesNode.querySelectorAll( 'implicitfunction' );

			if ( implicitFunctionNodes.length > 0 ) {

				resourcesData[ 'implicitfunction' ] = {};

			}


			for ( let i = 0; i < implicitFunctionNodes.length; i ++ ) {

				const implicitFunctionNode = implicitFunctionNodes[ i ];
				const implicitFunctionData = parseImplicitFunctionNode( implicitFunctionNode );
				resourcesData[ 'implicitfunction' ][ implicitFunctionData[ 'id' ] ] = implicitFunctionData;

			}

			//

			resourcesData[ 'pbmetallicdisplayproperties' ] = {};
			const pbmetallicdisplaypropertiesNodes = resourcesNode.querySelectorAll( 'pbmetallicdisplayproperties' );

			for ( let i = 0; i < pbmetallicdisplaypropertiesNodes.length; i ++ ) {

				const pbmetallicdisplaypropertiesNode = pbmetallicdisplaypropertiesNodes[ i ];
				const pbmetallicdisplaypropertiesData = parseMetallicDisplaypropertiesNode( pbmetallicdisplaypropertiesNode );
				resourcesData[ 'pbmetallicdisplayproperties' ][ pbmetallicdisplaypropertiesData[ 'id' ] ] = pbmetallicdisplaypropertiesData;

			}

			//

			resourcesData[ 'texture2dgroup' ] = {};
			const textures2DGroupNodes = resourcesNode.querySelectorAll( 'texture2dgroup' );

			for ( let i = 0; i < textures2DGroupNodes.length; i ++ ) {

				const textures2DGroupNode = textures2DGroupNodes[ i ];
				const textures2DGroupData = parseTextures2DGroupNode( textures2DGroupNode );
				resourcesData[ 'texture2dgroup' ][ textures2DGroupData[ 'id' ] ] = textures2DGroupData;

			}

			//

			resourcesData[ 'object' ] = {};
			const objectNodes = resourcesNode.querySelectorAll( 'object' );

			for ( let i = 0; i < objectNodes.length; i ++ ) {

				const objectNode = objectNodes[ i ];
				const objectData = parseObjectNode( objectNode );
				resourcesData[ 'object' ][ objectData[ 'id' ] ] = objectData;

			}

			return resourcesData;

		}
```
</details>

### `parseBuildNode(buildNode: any): { objectId: any; }[]`

**Parameters:**

- **`buildNode`** `any`

**Returns:** `{ objectId: any; }[]`

**Calls:**

- `buildNode.querySelectorAll`
- `itemNode.getAttribute`
- `parseTransform`
- `buildData.push`

<details><summary>Code</summary>

```typescript
function parseBuildNode( buildNode ) {

			const buildData = [];
			const itemNodes = buildNode.querySelectorAll( 'item' );

			for ( let i = 0; i < itemNodes.length; i ++ ) {

				const itemNode = itemNodes[ i ];
				const buildItem = {
					objectId: itemNode.getAttribute( 'objectid' )
				};
				const transform = itemNode.getAttribute( 'transform' );

				if ( transform ) {

					buildItem[ 'transform' ] = parseTransform( transform );

				}

				buildData.push( buildItem );

			}

			return buildData;

		}
```
</details>

### `parseModelNode(modelNode: any): { unit: any; }`

**Parameters:**

- **`modelNode`** `any`

**Returns:** `{ unit: any; }`

**Calls:**

- `modelNode.getAttribute`
- `modelNode.querySelectorAll`
- `parseMetadataNodes`
- `modelNode.querySelector`
- `parseResourcesNode`
- `parseBuildNode`

<details><summary>Code</summary>

```typescript
function parseModelNode( modelNode ) {

			const modelData = { unit: modelNode.getAttribute( 'unit' ) || 'millimeter' };
			const metadataNodes = modelNode.querySelectorAll( 'metadata' );

			if ( metadataNodes ) {

				modelData[ 'metadata' ] = parseMetadataNodes( metadataNodes );

			}

			const resourcesNode = modelNode.querySelector( 'resources' );

			if ( resourcesNode ) {

				modelData[ 'resources' ] = parseResourcesNode( resourcesNode );

			}

			const buildNode = modelNode.querySelector( 'build' );

			if ( buildNode ) {

				modelData[ 'build' ] = parseBuildNode( buildNode );

			}

			return modelData;

		}
```
</details>

### `buildTexture(texture2dgroup: any, objects: any, modelData: any, textureData: any): any`

**Parameters:**

- **`texture2dgroup`** `any`
- **`objects`** `any`
- **`modelData`** `any`
- **`textureData`** `any`

**Returns:** `any`

**Calls:**

- `URL.createObjectURL`
- `textureLoader.load`
- `URL.revokeObjectURL`

**Internal Comments:**
```
// texture parameters
```

<details><summary>Code</summary>

```typescript
function buildTexture( texture2dgroup, objects, modelData, textureData ) {

			const texid = texture2dgroup.texid;
			const texture2ds = modelData.resources.texture2d;
			const texture2d = texture2ds[ texid ];

			if ( texture2d ) {

				const data = textureData[ texture2d.path ];
				const type = texture2d.contenttype;

				const blob = new Blob( [ data ], { type: type } );
				const sourceURI = URL.createObjectURL( blob );

				const texture = textureLoader.load( sourceURI, function () {

					URL.revokeObjectURL( sourceURI );

				} );

				texture.colorSpace = COLOR_SPACE_3MF;

				// texture parameters

				switch ( texture2d.tilestyleu ) {

					case 'wrap':
						texture.wrapS = RepeatWrapping;
						break;

					case 'mirror':
						texture.wrapS = MirroredRepeatWrapping;
						break;

					case 'none':
					case 'clamp':
						texture.wrapS = ClampToEdgeWrapping;
						break;

					default:
						texture.wrapS = RepeatWrapping;

				}

				switch ( texture2d.tilestylev ) {

					case 'wrap':
						texture.wrapT = RepeatWrapping;
						break;

					case 'mirror':
						texture.wrapT = MirroredRepeatWrapping;
						break;

					case 'none':
					case 'clamp':
						texture.wrapT = ClampToEdgeWrapping;
						break;

					default:
						texture.wrapT = RepeatWrapping;

				}

				switch ( texture2d.filter ) {

					case 'auto':
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearMipmapLinearFilter;
						break;

					case 'linear':
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearFilter;
						texture.generateMipmaps = false;
						break;

					case 'nearest':
						texture.magFilter = NearestFilter;
						texture.minFilter = NearestFilter;
						texture.generateMipmaps = false;
						break;

					default:
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearMipmapLinearFilter;

				}

				return texture;

			} else {

				return null;

			}

		}
```
</details>

### `buildBasematerialsMeshes(basematerials: any, triangleProperties: any, meshData: any, objects: any, modelData: any, textureData: any, objectData: any): any[]`

**Parameters:**

- **`basematerials`** `any`
- **`triangleProperties`** `any`
- **`meshData`** `any`
- **`objects`** `any`
- **`modelData`** `any`
- **`textureData`** `any`
- **`objectData`** `any`

**Returns:** `any[]`

**Calls:**

- `materialMap[ pindex ].push`
- `Object.keys`
- `getBuild`
- `positionData.push`
- `geometry.setAttribute`
- `meshes.push`

**Internal Comments:**
```
// (x6)
```

<details><summary>Code</summary>

```typescript
function buildBasematerialsMeshes( basematerials, triangleProperties, meshData, objects, modelData, textureData, objectData ) {

			const objectPindex = objectData.pindex;

			const materialMap = {};

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];
				const pindex = ( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectPindex;

				if ( materialMap[ pindex ] === undefined ) materialMap[ pindex ] = [];

				materialMap[ pindex ].push( triangleProperty );

			}

			//

			const keys = Object.keys( materialMap );
			const meshes = [];

			for ( let i = 0, l = keys.length; i < l; i ++ ) {

				const materialIndex = keys[ i ];
				const trianglePropertiesProps = materialMap[ materialIndex ];
				const basematerialData = basematerials.basematerials[ materialIndex ];
				const material = getBuild( basematerialData, objects, modelData, textureData, objectData, buildBasematerial );

				//

				const geometry = new BufferGeometry();

				const positionData = [];

				const vertices = meshData.vertices;

				for ( let j = 0, jl = trianglePropertiesProps.length; j < jl; j ++ ) {

					const triangleProperty = trianglePropertiesProps[ j ];

					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 2 ] );

					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 2 ] );

					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 2 ] );


				}

				geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );

				//

				const mesh = new Mesh( geometry, material );
				meshes.push( mesh );

			}

			return meshes;

		}
```
</details>

### `buildTexturedMesh(texture2dgroup: any, triangleProperties: any, meshData: any, objects: any, modelData: any, textureData: any, objectData: any): any`

**Parameters:**

- **`texture2dgroup`** `any`
- **`triangleProperties`** `any`
- **`meshData`** `any`
- **`objects`** `any`
- **`modelData`** `any`
- **`textureData`** `any`
- **`objectData`** `any`

**Returns:** `any`

**Calls:**

- `positionData.push`
- `uvData.push`
- `geometry.setAttribute`
- `getBuild`

**Internal Comments:**
```
// geometry (x2)
// (x4)
// material (x2)
// mesh (x2)
```

<details><summary>Code</summary>

```typescript
function buildTexturedMesh( texture2dgroup, triangleProperties, meshData, objects, modelData, textureData, objectData ) {

			// geometry

			const geometry = new BufferGeometry();

			const positionData = [];
			const uvData = [];

			const vertices = meshData.vertices;
			const uvs = texture2dgroup.uvs;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];

				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 2 ] );

				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 2 ] );

				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 2 ] );

				//

				uvData.push( uvs[ ( triangleProperty.p1 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p1 * 2 ) + 1 ] );

				uvData.push( uvs[ ( triangleProperty.p2 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p2 * 2 ) + 1 ] );

				uvData.push( uvs[ ( triangleProperty.p3 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p3 * 2 ) + 1 ] );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );
			geometry.setAttribute( 'uv', new Float32BufferAttribute( uvData, 2 ) );

			// material

			const texture = getBuild( texture2dgroup, objects, modelData, textureData, objectData, buildTexture );

			const material = new MeshPhongMaterial( { map: texture, flatShading: true } );

			// mesh

			const mesh = new Mesh( geometry, material );

			return mesh;

		}
```
</details>

### `buildVertexColorMesh(colorgroup: any, triangleProperties: any, meshData: any, objectData: any): any`

**Parameters:**

- **`colorgroup`** `any`
- **`triangleProperties`** `any`
- **`meshData`** `any`
- **`objectData`** `any`

**Returns:** `any`

**Calls:**

- `positionData.push`
- `colorData.push`
- `geometry.setAttribute`

**Internal Comments:**
```
// geometry (x2)
// (x2)
// material (x2)
// mesh (x2)
```

<details><summary>Code</summary>

```typescript
function buildVertexColorMesh( colorgroup, triangleProperties, meshData, objectData ) {

			// geometry

			const geometry = new BufferGeometry();

			const positionData = [];
			const colorData = [];

			const vertices = meshData.vertices;
			const colors = colorgroup.colors;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];

				const v1 = triangleProperty.v1;
				const v2 = triangleProperty.v2;
				const v3 = triangleProperty.v3;

				positionData.push( vertices[ ( v1 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v1 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v1 * 3 ) + 2 ] );

				positionData.push( vertices[ ( v2 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v2 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v2 * 3 ) + 2 ] );

				positionData.push( vertices[ ( v3 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v3 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v3 * 3 ) + 2 ] );

				//

				const p1 = ( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectData.pindex;
				const p2 = ( triangleProperty.p2 !== undefined ) ? triangleProperty.p2 : p1;
				const p3 = ( triangleProperty.p3 !== undefined ) ? triangleProperty.p3 : p1;

				colorData.push( colors[ ( p1 * 3 ) + 0 ] );
				colorData.push( colors[ ( p1 * 3 ) + 1 ] );
				colorData.push( colors[ ( p1 * 3 ) + 2 ] );

				colorData.push( colors[ ( p2 * 3 ) + 0 ] );
				colorData.push( colors[ ( p2 * 3 ) + 1 ] );
				colorData.push( colors[ ( p2 * 3 ) + 2 ] );

				colorData.push( colors[ ( p3 * 3 ) + 0 ] );
				colorData.push( colors[ ( p3 * 3 ) + 1 ] );
				colorData.push( colors[ ( p3 * 3 ) + 2 ] );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );
			geometry.setAttribute( 'color', new Float32BufferAttribute( colorData, 3 ) );

			// material

			const material = new MeshPhongMaterial( { vertexColors: true, flatShading: true } );

			// mesh

			const mesh = new Mesh( geometry, material );

			return mesh;

		}
```
</details>

### `buildDefaultMesh(meshData: any): any`

**Parameters:**

- **`meshData`** `any`

**Returns:** `any`

**Calls:**

- `geometry.setIndex`
- `geometry.setAttribute`

<details><summary>Code</summary>

```typescript
function buildDefaultMesh( meshData ) {

			const geometry = new BufferGeometry();
			geometry.setIndex( new BufferAttribute( meshData[ 'triangles' ], 1 ) );
			geometry.setAttribute( 'position', new BufferAttribute( meshData[ 'vertices' ], 3 ) );

			const material = new MeshPhongMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0xffffff,
				flatShading: true
			} );

			const mesh = new Mesh( geometry, material );

			return mesh;

		}
```
</details>

### `buildMeshes(resourceMap: any, meshData: any, objects: any, modelData: any, textureData: any, objectData: any): any[]`

**Parameters:**

- **`resourceMap`** `any`
- **`meshData`** `any`
- **`objects`** `any`
- **`modelData`** `any`
- **`textureData`** `any`
- **`objectData`** `any`

**Returns:** `any[]`

**Calls:**

- `Object.keys`
- `getResourceType`
- `buildBasematerialsMeshes`
- `meshes.push`
- `buildTexturedMesh`
- `buildVertexColorMesh`
- `buildDefaultMesh`
- `console.error`

<details><summary>Code</summary>

```typescript
function buildMeshes( resourceMap, meshData, objects, modelData, textureData, objectData ) {

			const keys = Object.keys( resourceMap );
			const meshes = [];

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				const resourceId = keys[ i ];
				const triangleProperties = resourceMap[ resourceId ];
				const resourceType = getResourceType( resourceId, modelData );

				switch ( resourceType ) {

					case 'material':
						const basematerials = modelData.resources.basematerials[ resourceId ];
						const newMeshes = buildBasematerialsMeshes( basematerials, triangleProperties, meshData, objects, modelData, textureData, objectData );

						for ( let j = 0, jl = newMeshes.length; j < jl; j ++ ) {

							meshes.push( newMeshes[ j ] );

						}

						break;

					case 'texture':
						const texture2dgroup = modelData.resources.texture2dgroup[ resourceId ];
						meshes.push( buildTexturedMesh( texture2dgroup, triangleProperties, meshData, objects, modelData, textureData, objectData ) );
						break;

					case 'vertexColors':
						const colorgroup = modelData.resources.colorgroup[ resourceId ];
						meshes.push( buildVertexColorMesh( colorgroup, triangleProperties, meshData, objectData ) );
						break;

					case 'default':
						meshes.push( buildDefaultMesh( meshData ) );
						break;

					default:
						console.error( 'THREE.3MFLoader: Unsupported resource type.' );

				}

			}

			if ( objectData.name ) {

				for ( let i = 0; i < meshes.length; i ++ ) {

					meshes[ i ].name = objectData.name;

				}

			}

			return meshes;

		}
```
</details>

### `getResourceType(pid: any, modelData: any): "default" | "material" | "texture" | "vertexColors"`

**Parameters:**

- **`pid`** `any`
- **`modelData`** `any`

**Returns:** `"default" | "material" | "texture" | "vertexColors"`

<details><summary>Code</summary>

```typescript
function getResourceType( pid, modelData ) {

			if ( modelData.resources.texture2dgroup[ pid ] !== undefined ) {

				return 'texture';

			} else if ( modelData.resources.basematerials[ pid ] !== undefined ) {

				return 'material';

			} else if ( modelData.resources.colorgroup[ pid ] !== undefined ) {

				return 'vertexColors';

			} else if ( pid === 'default' ) {

				return 'default';

			} else {

				return undefined;

			}

		}
```
</details>

### `analyzeObject(meshData: any, objectData: any): {}`

**Parameters:**

- **`meshData`** `any`
- **`objectData`** `any`

**Returns:** `{}`

**Calls:**

- `resourceMap[ pid ].push`

<details><summary>Code</summary>

```typescript
function analyzeObject( meshData, objectData ) {

			const resourceMap = {};

			const triangleProperties = meshData[ 'triangleProperties' ];

			const objectPid = objectData.pid;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];
				let pid = ( triangleProperty.pid !== undefined ) ? triangleProperty.pid : objectPid;

				if ( pid === undefined ) pid = 'default';

				if ( resourceMap[ pid ] === undefined ) resourceMap[ pid ] = [];

				resourceMap[ pid ].push( triangleProperty );

			}

			return resourceMap;

		}
```
</details>

### `buildGroup(meshData: any, objects: any, modelData: any, textureData: any, objectData: any): any`

**Parameters:**

- **`meshData`** `any`
- **`objects`** `any`
- **`modelData`** `any`
- **`textureData`** `any`
- **`objectData`** `any`

**Returns:** `any`

**Calls:**

- `analyzeObject`
- `buildMeshes`
- `group.add`

<details><summary>Code</summary>

```typescript
function buildGroup( meshData, objects, modelData, textureData, objectData ) {

			const group = new Group();

			const resourceMap = analyzeObject( meshData, objectData );
			const meshes = buildMeshes( resourceMap, meshData, objects, modelData, textureData, objectData );

			for ( let i = 0, l = meshes.length; i < l; i ++ ) {

				group.add( meshes[ i ] );

			}

			return group;

		}
```
</details>

### `applyExtensions(extensions: any, meshData: any, modelXml: any): void`

**Parameters:**

- **`extensions`** `any`
- **`meshData`** `any`
- **`modelXml`** `any`

**Returns:** `void`

**Calls:**

- `Object.keys`
- `availableExtensions.push`
- `extension.apply`

<details><summary>Code</summary>

```typescript
function applyExtensions( extensions, meshData, modelXml ) {

			if ( ! extensions ) {

				return;

			}

			const availableExtensions = [];
			const keys = Object.keys( extensions );

			for ( let i = 0; i < keys.length; i ++ ) {

				const ns = keys[ i ];

				for ( let j = 0; j < scope.availableExtensions.length; j ++ ) {

					const extension = scope.availableExtensions[ j ];

					if ( extension.ns === ns ) {

						availableExtensions.push( extension );

					}

				}

			}

			for ( let i = 0; i < availableExtensions.length; i ++ ) {

				const extension = availableExtensions[ i ];
				extension.apply( modelXml, extensions[ extension[ 'ns' ] ], meshData );

			}

		}
```
</details>

### `getBuild(data: any, objects: any, modelData: any, textureData: any, objectData: any, builder: any): any`

**Parameters:**

- **`data`** `any`
- **`objects`** `any`
- **`modelData`** `any`
- **`textureData`** `any`
- **`objectData`** `any`
- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder`

<details><summary>Code</summary>

```typescript
function getBuild( data, objects, modelData, textureData, objectData, builder ) {

			if ( data.build !== undefined ) return data.build;

			data.build = builder( data, objects, modelData, textureData, objectData );

			return data.build;

		}
```
</details>

### `buildBasematerial(materialData: any, objects: any, modelData: any): any`

**Parameters:**

- **`materialData`** `any`
- **`objects`** `any`
- **`modelData`** `any`

**Returns:** `any`

**Calls:**

- `displaycolor.substring`
- `material.color.setStyle`
- `parseInt`
- `displaycolor.charAt`

**Internal Comments:**
```
// metallic display property, use StandardMaterial (x2)
// otherwise use PhongMaterial (x3)
// displaycolor MUST be specified with a value of a 6 or 8 digit hexadecimal number, e.g. "#RRGGBB" or "#RRGGBBAA" (x2)
// process alpha if set
```

<details><summary>Code</summary>

```typescript
function buildBasematerial( materialData, objects, modelData ) {

			let material;

			const displaypropertiesid = materialData.displaypropertiesid;
			const pbmetallicdisplayproperties = modelData.resources.pbmetallicdisplayproperties;

			if ( displaypropertiesid !== null && pbmetallicdisplayproperties[ displaypropertiesid ] !== undefined ) {

				// metallic display property, use StandardMaterial

				const pbmetallicdisplayproperty = pbmetallicdisplayproperties[ displaypropertiesid ];
				const metallicData = pbmetallicdisplayproperty.data[ materialData.index ];

				material = new MeshStandardMaterial( { flatShading: true, roughness: metallicData.roughness, metalness: metallicData.metallicness } );

			} else {

				// otherwise use PhongMaterial

				material = new MeshPhongMaterial( { flatShading: true } );

			}

			material.name = materialData.name;

			// displaycolor MUST be specified with a value of a 6 or 8 digit hexadecimal number, e.g. "#RRGGBB" or "#RRGGBBAA"

			const displaycolor = materialData.displaycolor;

			const color = displaycolor.substring( 0, 7 );
			material.color.setStyle( color, COLOR_SPACE_3MF );

			// process alpha if set

			if ( displaycolor.length === 9 ) {

				material.opacity = parseInt( displaycolor.charAt( 7 ) + displaycolor.charAt( 8 ), 16 ) / 255;

			}

			return material;

		}
```
</details>

### `buildComposite(compositeData: any, objects: any, modelData: any, textureData: any): any`

**Parameters:**

- **`compositeData`** `any`
- **`objects`** `any`
- **`modelData`** `any`
- **`textureData`** `any`

**Returns:** `any`

**Calls:**

- `buildObject`
- `build.clone`
- `object3D.applyMatrix4`
- `composite.add`

**Internal Comments:**
```
// apply component transform (x2)
```

<details><summary>Code</summary>

```typescript
function buildComposite( compositeData, objects, modelData, textureData ) {

			const composite = new Group();

			for ( let j = 0; j < compositeData.length; j ++ ) {

				const component = compositeData[ j ];
				let build = objects[ component.objectId ];

				if ( build === undefined ) {

					buildObject( component.objectId, objects, modelData, textureData );
					build = objects[ component.objectId ];

				}

				const object3D = build.clone();

				// apply component transform

				const transform = component.transform;

				if ( transform ) {

					object3D.applyMatrix4( transform );

				}

				composite.add( object3D );

			}

			return composite;

		}
```
</details>

### `buildObject(objectId: any, objects: any, modelData: any, textureData: any): void`

**Parameters:**

- **`objectId`** `any`
- **`objects`** `any`
- **`modelData`** `any`
- **`textureData`** `any`

**Returns:** `void`

**Calls:**

- `applyExtensions`
- `getBuild`
- `console.warn`

<details><summary>Code</summary>

```typescript
function buildObject( objectId, objects, modelData, textureData ) {

			const objectData = modelData[ 'resources' ][ 'object' ][ objectId ];

			if ( objectData[ 'mesh' ] ) {

				const meshData = objectData[ 'mesh' ];

				const extensions = modelData[ 'extensions' ];
				const modelXml = modelData[ 'xml' ];

				applyExtensions( extensions, meshData, modelXml );

				objects[ objectData.id ] = getBuild( meshData, objects, modelData, textureData, objectData, buildGroup );

			} else {

				const compositeData = objectData[ 'components' ];

				objects[ objectData.id ] = getBuild( compositeData, objects, modelData, textureData, objectData, buildComposite );

			}

			if ( objectData.name ) {

				objects[ objectData.id ].name = objectData.name;

			}

			if ( modelData.resources.implicitfunction ) {

				console.warn( 'THREE.ThreeMFLoader: Implicit Functions are implemented in data-only.', modelData.resources.implicitfunction );

			}

		}
```
</details>

### `buildObjects(data3mf: any): {}`

**Parameters:**

- **`data3mf`** `any`

**Returns:** `{}`

**Calls:**

- `Object.keys`
- `modelRel.target.substring`
- `buildObject`

**Internal Comments:**
```
// evaluate model relationships to textures
// start build
```

<details><summary>Code</summary>

```typescript
function buildObjects( data3mf ) {

			const modelsData = data3mf.model;
			const modelRels = data3mf.modelRels;
			const objects = {};
			const modelsKeys = Object.keys( modelsData );
			const textureData = {};

			// evaluate model relationships to textures

			if ( modelRels ) {

				for ( let i = 0, l = modelRels.length; i < l; i ++ ) {

					const modelRel = modelRels[ i ];
					const textureKey = modelRel.target.substring( 1 );

					if ( data3mf.texture[ textureKey ] ) {

						textureData[ modelRel.target ] = data3mf.texture[ textureKey ];

					}

				}

			}

			// start build

			for ( let i = 0; i < modelsKeys.length; i ++ ) {

				const modelsKey = modelsKeys[ i ];
				const modelData = modelsData[ modelsKey ];

				const objectIds = Object.keys( modelData[ 'resources' ][ 'object' ] );

				for ( let j = 0; j < objectIds.length; j ++ ) {

					const objectId = objectIds[ j ];

					buildObject( objectId, objects, modelData, textureData );

				}

			}

			return objects;

		}
```
</details>

### `fetch3DModelPart(rels: any): any`

**Parameters:**

- **`rels`** `any`

**Returns:** `any`

**Calls:**

- `rel.target.split( '.' ).pop`
- `extension.toLowerCase`

<details><summary>Code</summary>

```typescript
function fetch3DModelPart( rels ) {

			for ( let i = 0; i < rels.length; i ++ ) {

				const rel = rels[ i ];
				const extension = rel.target.split( '.' ).pop();

				if ( extension.toLowerCase() === 'model' ) return rel;

			}

		}
```
</details>

### `build(objects: any, data3mf: any): any`

**Parameters:**

- **`objects`** `any`
- **`data3mf`** `any`

**Returns:** `any`

**Calls:**

- `fetch3DModelPart`
- `relationship[ 'target' ].substring`
- `objects[ buildItem[ 'objectId' ] ].clone`
- `object3D.applyMatrix4`
- `group.add`

**Internal Comments:**
```
// apply transform (x2)
```

<details><summary>Code</summary>

```typescript
function build( objects, data3mf ) {

			const group = new Group();

			const relationship = fetch3DModelPart( data3mf[ 'rels' ] );
			const buildData = data3mf.model[ relationship[ 'target' ].substring( 1 ) ][ 'build' ];

			for ( let i = 0; i < buildData.length; i ++ ) {

				const buildItem = buildData[ i ];
				const object3D = objects[ buildItem[ 'objectId' ] ].clone();

				// apply transform

				const transform = buildItem[ 'transform' ];

				if ( transform ) {

					object3D.applyMatrix4( transform );

				}

				group.add( object3D );

			}

			return group;

		}
```
</details>


---

## Classes

### `ThreeMFLoader`

<details><summary>Class Code</summary>

```ts
class ThreeMFLoader extends Loader {

	/**
	 * Constructs a new 3MF loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * An array of available extensions.
		 *
		 * @type {Array<Object>}
		 */
		this.availableExtensions = [];

	}

	/**
	 * Starts loading from the given URL and passes the loaded 3MF asset
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
		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer ) );

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
	 * Parses the given 3MF data and returns the resulting group.
	 *
	 * @param {ArrayBuffer} data - The raw 3MF asset data as an array buffer.
	 * @return {Group} A group representing the parsed asset.
	 */
	parse( data ) {

		const scope = this;
		const textureLoader = new TextureLoader( this.manager );

		function loadDocument( data ) {

			let zip = null;
			let file = null;

			let relsName;
			let modelRelsName;
			const modelPartNames = [];
			const texturesPartNames = [];

			let modelRels;
			const modelParts = {};
			const printTicketParts = {};
			const texturesParts = {};

			const textDecoder = new TextDecoder();

			try {

				zip = fflate.unzipSync( new Uint8Array( data ) );

			} catch ( e ) {

				if ( e instanceof ReferenceError ) {

					console.error( 'THREE.3MFLoader: fflate missing and file is compressed.' );
					return null;

				}

			}

			let rootModelFile = null;

			for ( file in zip ) {

				if ( file.match( /\_rels\/.rels$/ ) ) {

					relsName = file;

				} else if ( file.match( /3D\/_rels\/.*\.model\.rels$/ ) ) {

					modelRelsName = file;

				} else if ( file.match( /^3D\/[^\/]*\.model$/ ) ) {

					rootModelFile = file;

				} else if ( file.match( /^3D\/.*\/.*\.model$/ ) ) {

					modelPartNames.push( file ); // sub models

				} else if ( file.match( /^3D\/Textures?\/.*/ ) ) {

					texturesPartNames.push( file );

				}

			}

			modelPartNames.push( rootModelFile ); // push root model at the end so it is processed after the sub models

			if ( relsName === undefined ) throw new Error( 'THREE.ThreeMFLoader: Cannot find relationship file `rels` in 3MF archive.' );

			//

			const relsView = zip[ relsName ];
			const relsFileText = textDecoder.decode( relsView );
			const rels = parseRelsXml( relsFileText );

			//

			if ( modelRelsName ) {

				const relsView = zip[ modelRelsName ];
				const relsFileText = textDecoder.decode( relsView );
				modelRels = parseRelsXml( relsFileText );

			}

			//

			for ( let i = 0; i < modelPartNames.length; i ++ ) {

				const modelPart = modelPartNames[ i ];
				const view = zip[ modelPart ];

				const fileText = textDecoder.decode( view );
				const xmlData = new DOMParser().parseFromString( fileText, 'application/xml' );

				if ( xmlData.documentElement.nodeName.toLowerCase() !== 'model' ) {

					console.error( 'THREE.3MFLoader: Error loading 3MF - no 3MF document found: ', modelPart );

				}

				const modelNode = xmlData.querySelector( 'model' );
				const extensions = {};

				for ( let i = 0; i < modelNode.attributes.length; i ++ ) {

					const attr = modelNode.attributes[ i ];
					if ( attr.name.match( /^xmlns:(.+)$/ ) ) {

						extensions[ attr.value ] = RegExp.$1;

					}

				}

				const modelData = parseModelNode( modelNode );
				modelData[ 'xml' ] = modelNode;

				if ( 0 < Object.keys( extensions ).length ) {

					modelData[ 'extensions' ] = extensions;

				}

				modelParts[ modelPart ] = modelData;

			}

			//

			for ( let i = 0; i < texturesPartNames.length; i ++ ) {

				const texturesPartName = texturesPartNames[ i ];
				texturesParts[ texturesPartName ] = zip[ texturesPartName ].buffer;

			}

			return {
				rels: rels,
				modelRels: modelRels,
				model: modelParts,
				printTicket: printTicketParts,
				texture: texturesParts
			};

		}

		function parseRelsXml( relsFileText ) {

			const relationships = [];

			const relsXmlData = new DOMParser().parseFromString( relsFileText, 'application/xml' );

			const relsNodes = relsXmlData.querySelectorAll( 'Relationship' );

			for ( let i = 0; i < relsNodes.length; i ++ ) {

				const relsNode = relsNodes[ i ];

				const relationship = {
					target: relsNode.getAttribute( 'Target' ), //required
					id: relsNode.getAttribute( 'Id' ), //required
					type: relsNode.getAttribute( 'Type' ) //required
				};

				relationships.push( relationship );

			}

			return relationships;

		}

		function parseMetadataNodes( metadataNodes ) {

			const metadataData = {};

			for ( let i = 0; i < metadataNodes.length; i ++ ) {

				const metadataNode = metadataNodes[ i ];
				const name = metadataNode.getAttribute( 'name' );
				const validNames = [
					'Title',
					'Designer',
					'Description',
					'Copyright',
					'LicenseTerms',
					'Rating',
					'CreationDate',
					'ModificationDate'
				];

				if ( 0 <= validNames.indexOf( name ) ) {

					metadataData[ name ] = metadataNode.textContent;

				}

			}

			return metadataData;

		}

		function parseBasematerialsNode( basematerialsNode ) {

			const basematerialsData = {
				id: basematerialsNode.getAttribute( 'id' ), // required
				basematerials: []
			};

			const basematerialNodes = basematerialsNode.querySelectorAll( 'base' );

			for ( let i = 0; i < basematerialNodes.length; i ++ ) {

				const basematerialNode = basematerialNodes[ i ];
				const basematerialData = parseBasematerialNode( basematerialNode );
				basematerialData.index = i; // the order and count of the material nodes form an implicit 0-based index
				basematerialsData.basematerials.push( basematerialData );

			}

			return basematerialsData;

		}

		function parseTexture2DNode( texture2DNode ) {

			const texture2dData = {
				id: texture2DNode.getAttribute( 'id' ), // required
				path: texture2DNode.getAttribute( 'path' ), // required
				contenttype: texture2DNode.getAttribute( 'contenttype' ), // required
				tilestyleu: texture2DNode.getAttribute( 'tilestyleu' ),
				tilestylev: texture2DNode.getAttribute( 'tilestylev' ),
				filter: texture2DNode.getAttribute( 'filter' ),
			};

			return texture2dData;

		}

		function parseTextures2DGroupNode( texture2DGroupNode ) {

			const texture2DGroupData = {
				id: texture2DGroupNode.getAttribute( 'id' ), // required
				texid: texture2DGroupNode.getAttribute( 'texid' ), // required
				displaypropertiesid: texture2DGroupNode.getAttribute( 'displaypropertiesid' )
			};

			const tex2coordNodes = texture2DGroupNode.querySelectorAll( 'tex2coord' );

			const uvs = [];

			for ( let i = 0; i < tex2coordNodes.length; i ++ ) {

				const tex2coordNode = tex2coordNodes[ i ];
				const u = tex2coordNode.getAttribute( 'u' );
				const v = tex2coordNode.getAttribute( 'v' );

				uvs.push( parseFloat( u ), parseFloat( v ) );

			}

			texture2DGroupData[ 'uvs' ] = new Float32Array( uvs );

			return texture2DGroupData;

		}

		function parseColorGroupNode( colorGroupNode ) {

			const colorGroupData = {
				id: colorGroupNode.getAttribute( 'id' ), // required
				displaypropertiesid: colorGroupNode.getAttribute( 'displaypropertiesid' )
			};

			const colorNodes = colorGroupNode.querySelectorAll( 'color' );

			const colors = [];
			const colorObject = new Color();

			for ( let i = 0; i < colorNodes.length; i ++ ) {

				const colorNode = colorNodes[ i ];
				const color = colorNode.getAttribute( 'color' );

				colorObject.setStyle( color.substring( 0, 7 ), COLOR_SPACE_3MF );

				colors.push( colorObject.r, colorObject.g, colorObject.b );

			}

			colorGroupData[ 'colors' ] = new Float32Array( colors );

			return colorGroupData;

		}

		function parseImplicitIONode( implicitIONode ) {

			const portNodes = implicitIONode.children;
			const portArguments = {};
			for ( let i = 0; i < portNodes.length; i ++ ) {

				const args = { type: portNodes[ i ].nodeName.substring( 2 ) };
				for ( let j = 0; j < portNodes[ i ].attributes.length; j ++ ) {

					const attrib = portNodes[ i ].attributes[ j ];
					if ( attrib.specified ) {

		 				args[ attrib.name ] = attrib.value;

					}

				}

				portArguments[ portNodes[ i ].getAttribute( 'identifier' ) ] = args;

			}

			return portArguments;

		}

		function parseImplicitFunctionNode( implicitFunctionNode ) {

			const implicitFunctionData = {
				id: implicitFunctionNode.getAttribute( 'id' ),
				displayname: implicitFunctionNode.getAttribute( 'displayname' )
			};

			const functionNodes = implicitFunctionNode.children;

			const operations = {};

			for ( let i = 0; i < functionNodes.length; i ++ ) {

				const operatorNode = functionNodes[ i ];

				if ( operatorNode.nodeName === 'i:in' || operatorNode.nodeName === 'i:out' ) {

					operations[ operatorNode.nodeName === 'i:in' ? 'inputs' : 'outputs' ] = parseImplicitIONode( operatorNode );

				} else {

					const inputNodes = operatorNode.children;
					const portArguments = { 'op': operatorNode.nodeName.substring( 2 ), 'identifier': operatorNode.getAttribute( 'identifier' ) };
					for ( let i = 0; i < inputNodes.length; i ++ ) {

						portArguments[ inputNodes[ i ].nodeName.substring( 2 ) ] = parseImplicitIONode( inputNodes[ i ] );

					}

					operations[ portArguments[ 'identifier' ] ] = portArguments;

				}

			}

			implicitFunctionData[ 'operations' ] = operations;

			return implicitFunctionData;

		}

		function parseMetallicDisplaypropertiesNode( metallicDisplaypropetiesNode ) {

			const metallicDisplaypropertiesData = {
				id: metallicDisplaypropetiesNode.getAttribute( 'id' ) // required
			};

			const metallicNodes = metallicDisplaypropetiesNode.querySelectorAll( 'pbmetallic' );

			const metallicData = [];

			for ( let i = 0; i < metallicNodes.length; i ++ ) {

				const metallicNode = metallicNodes[ i ];

				metallicData.push( {
					name: metallicNode.getAttribute( 'name' ), // required
					metallicness: parseFloat( metallicNode.getAttribute( 'metallicness' ) ), // required
					roughness: parseFloat( metallicNode.getAttribute( 'roughness' ) ) // required
				} );

			}

			metallicDisplaypropertiesData.data = metallicData;

			return metallicDisplaypropertiesData;

		}

		function parseBasematerialNode( basematerialNode ) {

			const basematerialData = {};

			basematerialData[ 'name' ] = basematerialNode.getAttribute( 'name' ); // required
			basematerialData[ 'displaycolor' ] = basematerialNode.getAttribute( 'displaycolor' ); // required
			basematerialData[ 'displaypropertiesid' ] = basematerialNode.getAttribute( 'displaypropertiesid' );

			return basematerialData;

		}

		function parseMeshNode( meshNode ) {

			const meshData = {};

			const vertices = [];
			const vertexNodes = meshNode.querySelectorAll( 'vertices vertex' );

			for ( let i = 0; i < vertexNodes.length; i ++ ) {

				const vertexNode = vertexNodes[ i ];
				const x = vertexNode.getAttribute( 'x' );
				const y = vertexNode.getAttribute( 'y' );
				const z = vertexNode.getAttribute( 'z' );

				vertices.push( parseFloat( x ), parseFloat( y ), parseFloat( z ) );

			}

			meshData[ 'vertices' ] = new Float32Array( vertices );

			const triangleProperties = [];
			const triangles = [];
			const triangleNodes = meshNode.querySelectorAll( 'triangles triangle' );

			for ( let i = 0; i < triangleNodes.length; i ++ ) {

				const triangleNode = triangleNodes[ i ];
				const v1 = triangleNode.getAttribute( 'v1' );
				const v2 = triangleNode.getAttribute( 'v2' );
				const v3 = triangleNode.getAttribute( 'v3' );
				const p1 = triangleNode.getAttribute( 'p1' );
				const p2 = triangleNode.getAttribute( 'p2' );
				const p3 = triangleNode.getAttribute( 'p3' );
				const pid = triangleNode.getAttribute( 'pid' );

				const triangleProperty = {};

				triangleProperty[ 'v1' ] = parseInt( v1, 10 );
				triangleProperty[ 'v2' ] = parseInt( v2, 10 );
				triangleProperty[ 'v3' ] = parseInt( v3, 10 );

				triangles.push( triangleProperty[ 'v1' ], triangleProperty[ 'v2' ], triangleProperty[ 'v3' ] );

				// optional

				if ( p1 ) {

					triangleProperty[ 'p1' ] = parseInt( p1, 10 );

				}

				if ( p2 ) {

					triangleProperty[ 'p2' ] = parseInt( p2, 10 );

				}

				if ( p3 ) {

					triangleProperty[ 'p3' ] = parseInt( p3, 10 );

				}

				if ( pid ) {

					triangleProperty[ 'pid' ] = pid;

				}

				if ( 0 < Object.keys( triangleProperty ).length ) {

					triangleProperties.push( triangleProperty );

				}

			}

			meshData[ 'triangleProperties' ] = triangleProperties;
			meshData[ 'triangles' ] = new Uint32Array( triangles );

			return meshData;

		}

		function parseComponentsNode( componentsNode ) {

			const components = [];

			const componentNodes = componentsNode.querySelectorAll( 'component' );

			for ( let i = 0; i < componentNodes.length; i ++ ) {

				const componentNode = componentNodes[ i ];
				const componentData = parseComponentNode( componentNode );
				components.push( componentData );

			}

			return components;

		}

		function parseComponentNode( componentNode ) {

			const componentData = {};

			componentData[ 'objectId' ] = componentNode.getAttribute( 'objectid' ); // required

			const transform = componentNode.getAttribute( 'transform' );

			if ( transform ) {

				componentData[ 'transform' ] = parseTransform( transform );

			}

			return componentData;

		}

		function parseTransform( transform ) {

			const t = [];
			transform.split( ' ' ).forEach( function ( s ) {

				t.push( parseFloat( s ) );

			} );

			const matrix = new Matrix4();
			matrix.set(
				t[ 0 ], t[ 3 ], t[ 6 ], t[ 9 ],
				t[ 1 ], t[ 4 ], t[ 7 ], t[ 10 ],
				t[ 2 ], t[ 5 ], t[ 8 ], t[ 11 ],
				 0.0, 0.0, 0.0, 1.0
			);

			return matrix;

		}

		function parseObjectNode( objectNode ) {

			const objectData = {
				type: objectNode.getAttribute( 'type' )
			};

			const id = objectNode.getAttribute( 'id' );

			if ( id ) {

				objectData[ 'id' ] = id;

			}

			const pid = objectNode.getAttribute( 'pid' );

			if ( pid ) {

				objectData[ 'pid' ] = pid;

			}

			const pindex = objectNode.getAttribute( 'pindex' );

			if ( pindex ) {

				objectData[ 'pindex' ] = pindex;

			}

			const thumbnail = objectNode.getAttribute( 'thumbnail' );

			if ( thumbnail ) {

				objectData[ 'thumbnail' ] = thumbnail;

			}

			const partnumber = objectNode.getAttribute( 'partnumber' );

			if ( partnumber ) {

				objectData[ 'partnumber' ] = partnumber;

			}

			const name = objectNode.getAttribute( 'name' );

			if ( name ) {

				objectData[ 'name' ] = name;

			}

			const meshNode = objectNode.querySelector( 'mesh' );

			if ( meshNode ) {

				objectData[ 'mesh' ] = parseMeshNode( meshNode );

			}

			const componentsNode = objectNode.querySelector( 'components' );

			if ( componentsNode ) {

				objectData[ 'components' ] = parseComponentsNode( componentsNode );

			}

			return objectData;

		}

		function parseResourcesNode( resourcesNode ) {

			const resourcesData = {};

			resourcesData[ 'basematerials' ] = {};
			const basematerialsNodes = resourcesNode.querySelectorAll( 'basematerials' );

			for ( let i = 0; i < basematerialsNodes.length; i ++ ) {

				const basematerialsNode = basematerialsNodes[ i ];
				const basematerialsData = parseBasematerialsNode( basematerialsNode );
				resourcesData[ 'basematerials' ][ basematerialsData[ 'id' ] ] = basematerialsData;

			}

			//

			resourcesData[ 'texture2d' ] = {};
			const textures2DNodes = resourcesNode.querySelectorAll( 'texture2d' );

			for ( let i = 0; i < textures2DNodes.length; i ++ ) {

				const textures2DNode = textures2DNodes[ i ];
				const texture2DData = parseTexture2DNode( textures2DNode );
				resourcesData[ 'texture2d' ][ texture2DData[ 'id' ] ] = texture2DData;

			}

			//

			resourcesData[ 'colorgroup' ] = {};
			const colorGroupNodes = resourcesNode.querySelectorAll( 'colorgroup' );

			for ( let i = 0; i < colorGroupNodes.length; i ++ ) {

				const colorGroupNode = colorGroupNodes[ i ];
				const colorGroupData = parseColorGroupNode( colorGroupNode );
				resourcesData[ 'colorgroup' ][ colorGroupData[ 'id' ] ] = colorGroupData;

			}

			//

			const implicitFunctionNodes = resourcesNode.querySelectorAll( 'implicitfunction' );

			if ( implicitFunctionNodes.length > 0 ) {

				resourcesData[ 'implicitfunction' ] = {};

			}


			for ( let i = 0; i < implicitFunctionNodes.length; i ++ ) {

				const implicitFunctionNode = implicitFunctionNodes[ i ];
				const implicitFunctionData = parseImplicitFunctionNode( implicitFunctionNode );
				resourcesData[ 'implicitfunction' ][ implicitFunctionData[ 'id' ] ] = implicitFunctionData;

			}

			//

			resourcesData[ 'pbmetallicdisplayproperties' ] = {};
			const pbmetallicdisplaypropertiesNodes = resourcesNode.querySelectorAll( 'pbmetallicdisplayproperties' );

			for ( let i = 0; i < pbmetallicdisplaypropertiesNodes.length; i ++ ) {

				const pbmetallicdisplaypropertiesNode = pbmetallicdisplaypropertiesNodes[ i ];
				const pbmetallicdisplaypropertiesData = parseMetallicDisplaypropertiesNode( pbmetallicdisplaypropertiesNode );
				resourcesData[ 'pbmetallicdisplayproperties' ][ pbmetallicdisplaypropertiesData[ 'id' ] ] = pbmetallicdisplaypropertiesData;

			}

			//

			resourcesData[ 'texture2dgroup' ] = {};
			const textures2DGroupNodes = resourcesNode.querySelectorAll( 'texture2dgroup' );

			for ( let i = 0; i < textures2DGroupNodes.length; i ++ ) {

				const textures2DGroupNode = textures2DGroupNodes[ i ];
				const textures2DGroupData = parseTextures2DGroupNode( textures2DGroupNode );
				resourcesData[ 'texture2dgroup' ][ textures2DGroupData[ 'id' ] ] = textures2DGroupData;

			}

			//

			resourcesData[ 'object' ] = {};
			const objectNodes = resourcesNode.querySelectorAll( 'object' );

			for ( let i = 0; i < objectNodes.length; i ++ ) {

				const objectNode = objectNodes[ i ];
				const objectData = parseObjectNode( objectNode );
				resourcesData[ 'object' ][ objectData[ 'id' ] ] = objectData;

			}

			return resourcesData;

		}

		function parseBuildNode( buildNode ) {

			const buildData = [];
			const itemNodes = buildNode.querySelectorAll( 'item' );

			for ( let i = 0; i < itemNodes.length; i ++ ) {

				const itemNode = itemNodes[ i ];
				const buildItem = {
					objectId: itemNode.getAttribute( 'objectid' )
				};
				const transform = itemNode.getAttribute( 'transform' );

				if ( transform ) {

					buildItem[ 'transform' ] = parseTransform( transform );

				}

				buildData.push( buildItem );

			}

			return buildData;

		}

		function parseModelNode( modelNode ) {

			const modelData = { unit: modelNode.getAttribute( 'unit' ) || 'millimeter' };
			const metadataNodes = modelNode.querySelectorAll( 'metadata' );

			if ( metadataNodes ) {

				modelData[ 'metadata' ] = parseMetadataNodes( metadataNodes );

			}

			const resourcesNode = modelNode.querySelector( 'resources' );

			if ( resourcesNode ) {

				modelData[ 'resources' ] = parseResourcesNode( resourcesNode );

			}

			const buildNode = modelNode.querySelector( 'build' );

			if ( buildNode ) {

				modelData[ 'build' ] = parseBuildNode( buildNode );

			}

			return modelData;

		}

		function buildTexture( texture2dgroup, objects, modelData, textureData ) {

			const texid = texture2dgroup.texid;
			const texture2ds = modelData.resources.texture2d;
			const texture2d = texture2ds[ texid ];

			if ( texture2d ) {

				const data = textureData[ texture2d.path ];
				const type = texture2d.contenttype;

				const blob = new Blob( [ data ], { type: type } );
				const sourceURI = URL.createObjectURL( blob );

				const texture = textureLoader.load( sourceURI, function () {

					URL.revokeObjectURL( sourceURI );

				} );

				texture.colorSpace = COLOR_SPACE_3MF;

				// texture parameters

				switch ( texture2d.tilestyleu ) {

					case 'wrap':
						texture.wrapS = RepeatWrapping;
						break;

					case 'mirror':
						texture.wrapS = MirroredRepeatWrapping;
						break;

					case 'none':
					case 'clamp':
						texture.wrapS = ClampToEdgeWrapping;
						break;

					default:
						texture.wrapS = RepeatWrapping;

				}

				switch ( texture2d.tilestylev ) {

					case 'wrap':
						texture.wrapT = RepeatWrapping;
						break;

					case 'mirror':
						texture.wrapT = MirroredRepeatWrapping;
						break;

					case 'none':
					case 'clamp':
						texture.wrapT = ClampToEdgeWrapping;
						break;

					default:
						texture.wrapT = RepeatWrapping;

				}

				switch ( texture2d.filter ) {

					case 'auto':
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearMipmapLinearFilter;
						break;

					case 'linear':
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearFilter;
						texture.generateMipmaps = false;
						break;

					case 'nearest':
						texture.magFilter = NearestFilter;
						texture.minFilter = NearestFilter;
						texture.generateMipmaps = false;
						break;

					default:
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearMipmapLinearFilter;

				}

				return texture;

			} else {

				return null;

			}

		}

		function buildBasematerialsMeshes( basematerials, triangleProperties, meshData, objects, modelData, textureData, objectData ) {

			const objectPindex = objectData.pindex;

			const materialMap = {};

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];
				const pindex = ( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectPindex;

				if ( materialMap[ pindex ] === undefined ) materialMap[ pindex ] = [];

				materialMap[ pindex ].push( triangleProperty );

			}

			//

			const keys = Object.keys( materialMap );
			const meshes = [];

			for ( let i = 0, l = keys.length; i < l; i ++ ) {

				const materialIndex = keys[ i ];
				const trianglePropertiesProps = materialMap[ materialIndex ];
				const basematerialData = basematerials.basematerials[ materialIndex ];
				const material = getBuild( basematerialData, objects, modelData, textureData, objectData, buildBasematerial );

				//

				const geometry = new BufferGeometry();

				const positionData = [];

				const vertices = meshData.vertices;

				for ( let j = 0, jl = trianglePropertiesProps.length; j < jl; j ++ ) {

					const triangleProperty = trianglePropertiesProps[ j ];

					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 2 ] );

					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 2 ] );

					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 2 ] );


				}

				geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );

				//

				const mesh = new Mesh( geometry, material );
				meshes.push( mesh );

			}

			return meshes;

		}

		function buildTexturedMesh( texture2dgroup, triangleProperties, meshData, objects, modelData, textureData, objectData ) {

			// geometry

			const geometry = new BufferGeometry();

			const positionData = [];
			const uvData = [];

			const vertices = meshData.vertices;
			const uvs = texture2dgroup.uvs;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];

				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 2 ] );

				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 2 ] );

				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 2 ] );

				//

				uvData.push( uvs[ ( triangleProperty.p1 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p1 * 2 ) + 1 ] );

				uvData.push( uvs[ ( triangleProperty.p2 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p2 * 2 ) + 1 ] );

				uvData.push( uvs[ ( triangleProperty.p3 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p3 * 2 ) + 1 ] );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );
			geometry.setAttribute( 'uv', new Float32BufferAttribute( uvData, 2 ) );

			// material

			const texture = getBuild( texture2dgroup, objects, modelData, textureData, objectData, buildTexture );

			const material = new MeshPhongMaterial( { map: texture, flatShading: true } );

			// mesh

			const mesh = new Mesh( geometry, material );

			return mesh;

		}

		function buildVertexColorMesh( colorgroup, triangleProperties, meshData, objectData ) {

			// geometry

			const geometry = new BufferGeometry();

			const positionData = [];
			const colorData = [];

			const vertices = meshData.vertices;
			const colors = colorgroup.colors;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];

				const v1 = triangleProperty.v1;
				const v2 = triangleProperty.v2;
				const v3 = triangleProperty.v3;

				positionData.push( vertices[ ( v1 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v1 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v1 * 3 ) + 2 ] );

				positionData.push( vertices[ ( v2 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v2 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v2 * 3 ) + 2 ] );

				positionData.push( vertices[ ( v3 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v3 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v3 * 3 ) + 2 ] );

				//

				const p1 = ( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectData.pindex;
				const p2 = ( triangleProperty.p2 !== undefined ) ? triangleProperty.p2 : p1;
				const p3 = ( triangleProperty.p3 !== undefined ) ? triangleProperty.p3 : p1;

				colorData.push( colors[ ( p1 * 3 ) + 0 ] );
				colorData.push( colors[ ( p1 * 3 ) + 1 ] );
				colorData.push( colors[ ( p1 * 3 ) + 2 ] );

				colorData.push( colors[ ( p2 * 3 ) + 0 ] );
				colorData.push( colors[ ( p2 * 3 ) + 1 ] );
				colorData.push( colors[ ( p2 * 3 ) + 2 ] );

				colorData.push( colors[ ( p3 * 3 ) + 0 ] );
				colorData.push( colors[ ( p3 * 3 ) + 1 ] );
				colorData.push( colors[ ( p3 * 3 ) + 2 ] );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );
			geometry.setAttribute( 'color', new Float32BufferAttribute( colorData, 3 ) );

			// material

			const material = new MeshPhongMaterial( { vertexColors: true, flatShading: true } );

			// mesh

			const mesh = new Mesh( geometry, material );

			return mesh;

		}

		function buildDefaultMesh( meshData ) {

			const geometry = new BufferGeometry();
			geometry.setIndex( new BufferAttribute( meshData[ 'triangles' ], 1 ) );
			geometry.setAttribute( 'position', new BufferAttribute( meshData[ 'vertices' ], 3 ) );

			const material = new MeshPhongMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0xffffff,
				flatShading: true
			} );

			const mesh = new Mesh( geometry, material );

			return mesh;

		}

		function buildMeshes( resourceMap, meshData, objects, modelData, textureData, objectData ) {

			const keys = Object.keys( resourceMap );
			const meshes = [];

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				const resourceId = keys[ i ];
				const triangleProperties = resourceMap[ resourceId ];
				const resourceType = getResourceType( resourceId, modelData );

				switch ( resourceType ) {

					case 'material':
						const basematerials = modelData.resources.basematerials[ resourceId ];
						const newMeshes = buildBasematerialsMeshes( basematerials, triangleProperties, meshData, objects, modelData, textureData, objectData );

						for ( let j = 0, jl = newMeshes.length; j < jl; j ++ ) {

							meshes.push( newMeshes[ j ] );

						}

						break;

					case 'texture':
						const texture2dgroup = modelData.resources.texture2dgroup[ resourceId ];
						meshes.push( buildTexturedMesh( texture2dgroup, triangleProperties, meshData, objects, modelData, textureData, objectData ) );
						break;

					case 'vertexColors':
						const colorgroup = modelData.resources.colorgroup[ resourceId ];
						meshes.push( buildVertexColorMesh( colorgroup, triangleProperties, meshData, objectData ) );
						break;

					case 'default':
						meshes.push( buildDefaultMesh( meshData ) );
						break;

					default:
						console.error( 'THREE.3MFLoader: Unsupported resource type.' );

				}

			}

			if ( objectData.name ) {

				for ( let i = 0; i < meshes.length; i ++ ) {

					meshes[ i ].name = objectData.name;

				}

			}

			return meshes;

		}

		function getResourceType( pid, modelData ) {

			if ( modelData.resources.texture2dgroup[ pid ] !== undefined ) {

				return 'texture';

			} else if ( modelData.resources.basematerials[ pid ] !== undefined ) {

				return 'material';

			} else if ( modelData.resources.colorgroup[ pid ] !== undefined ) {

				return 'vertexColors';

			} else if ( pid === 'default' ) {

				return 'default';

			} else {

				return undefined;

			}

		}

		function analyzeObject( meshData, objectData ) {

			const resourceMap = {};

			const triangleProperties = meshData[ 'triangleProperties' ];

			const objectPid = objectData.pid;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];
				let pid = ( triangleProperty.pid !== undefined ) ? triangleProperty.pid : objectPid;

				if ( pid === undefined ) pid = 'default';

				if ( resourceMap[ pid ] === undefined ) resourceMap[ pid ] = [];

				resourceMap[ pid ].push( triangleProperty );

			}

			return resourceMap;

		}

		function buildGroup( meshData, objects, modelData, textureData, objectData ) {

			const group = new Group();

			const resourceMap = analyzeObject( meshData, objectData );
			const meshes = buildMeshes( resourceMap, meshData, objects, modelData, textureData, objectData );

			for ( let i = 0, l = meshes.length; i < l; i ++ ) {

				group.add( meshes[ i ] );

			}

			return group;

		}

		function applyExtensions( extensions, meshData, modelXml ) {

			if ( ! extensions ) {

				return;

			}

			const availableExtensions = [];
			const keys = Object.keys( extensions );

			for ( let i = 0; i < keys.length; i ++ ) {

				const ns = keys[ i ];

				for ( let j = 0; j < scope.availableExtensions.length; j ++ ) {

					const extension = scope.availableExtensions[ j ];

					if ( extension.ns === ns ) {

						availableExtensions.push( extension );

					}

				}

			}

			for ( let i = 0; i < availableExtensions.length; i ++ ) {

				const extension = availableExtensions[ i ];
				extension.apply( modelXml, extensions[ extension[ 'ns' ] ], meshData );

			}

		}

		function getBuild( data, objects, modelData, textureData, objectData, builder ) {

			if ( data.build !== undefined ) return data.build;

			data.build = builder( data, objects, modelData, textureData, objectData );

			return data.build;

		}

		function buildBasematerial( materialData, objects, modelData ) {

			let material;

			const displaypropertiesid = materialData.displaypropertiesid;
			const pbmetallicdisplayproperties = modelData.resources.pbmetallicdisplayproperties;

			if ( displaypropertiesid !== null && pbmetallicdisplayproperties[ displaypropertiesid ] !== undefined ) {

				// metallic display property, use StandardMaterial

				const pbmetallicdisplayproperty = pbmetallicdisplayproperties[ displaypropertiesid ];
				const metallicData = pbmetallicdisplayproperty.data[ materialData.index ];

				material = new MeshStandardMaterial( { flatShading: true, roughness: metallicData.roughness, metalness: metallicData.metallicness } );

			} else {

				// otherwise use PhongMaterial

				material = new MeshPhongMaterial( { flatShading: true } );

			}

			material.name = materialData.name;

			// displaycolor MUST be specified with a value of a 6 or 8 digit hexadecimal number, e.g. "#RRGGBB" or "#RRGGBBAA"

			const displaycolor = materialData.displaycolor;

			const color = displaycolor.substring( 0, 7 );
			material.color.setStyle( color, COLOR_SPACE_3MF );

			// process alpha if set

			if ( displaycolor.length === 9 ) {

				material.opacity = parseInt( displaycolor.charAt( 7 ) + displaycolor.charAt( 8 ), 16 ) / 255;

			}

			return material;

		}

		function buildComposite( compositeData, objects, modelData, textureData ) {

			const composite = new Group();

			for ( let j = 0; j < compositeData.length; j ++ ) {

				const component = compositeData[ j ];
				let build = objects[ component.objectId ];

				if ( build === undefined ) {

					buildObject( component.objectId, objects, modelData, textureData );
					build = objects[ component.objectId ];

				}

				const object3D = build.clone();

				// apply component transform

				const transform = component.transform;

				if ( transform ) {

					object3D.applyMatrix4( transform );

				}

				composite.add( object3D );

			}

			return composite;

		}

		function buildObject( objectId, objects, modelData, textureData ) {

			const objectData = modelData[ 'resources' ][ 'object' ][ objectId ];

			if ( objectData[ 'mesh' ] ) {

				const meshData = objectData[ 'mesh' ];

				const extensions = modelData[ 'extensions' ];
				const modelXml = modelData[ 'xml' ];

				applyExtensions( extensions, meshData, modelXml );

				objects[ objectData.id ] = getBuild( meshData, objects, modelData, textureData, objectData, buildGroup );

			} else {

				const compositeData = objectData[ 'components' ];

				objects[ objectData.id ] = getBuild( compositeData, objects, modelData, textureData, objectData, buildComposite );

			}

			if ( objectData.name ) {

				objects[ objectData.id ].name = objectData.name;

			}

			if ( modelData.resources.implicitfunction ) {

				console.warn( 'THREE.ThreeMFLoader: Implicit Functions are implemented in data-only.', modelData.resources.implicitfunction );

			}

		}

		function buildObjects( data3mf ) {

			const modelsData = data3mf.model;
			const modelRels = data3mf.modelRels;
			const objects = {};
			const modelsKeys = Object.keys( modelsData );
			const textureData = {};

			// evaluate model relationships to textures

			if ( modelRels ) {

				for ( let i = 0, l = modelRels.length; i < l; i ++ ) {

					const modelRel = modelRels[ i ];
					const textureKey = modelRel.target.substring( 1 );

					if ( data3mf.texture[ textureKey ] ) {

						textureData[ modelRel.target ] = data3mf.texture[ textureKey ];

					}

				}

			}

			// start build

			for ( let i = 0; i < modelsKeys.length; i ++ ) {

				const modelsKey = modelsKeys[ i ];
				const modelData = modelsData[ modelsKey ];

				const objectIds = Object.keys( modelData[ 'resources' ][ 'object' ] );

				for ( let j = 0; j < objectIds.length; j ++ ) {

					const objectId = objectIds[ j ];

					buildObject( objectId, objects, modelData, textureData );

				}

			}

			return objects;

		}

		function fetch3DModelPart( rels ) {

			for ( let i = 0; i < rels.length; i ++ ) {

				const rel = rels[ i ];
				const extension = rel.target.split( '.' ).pop();

				if ( extension.toLowerCase() === 'model' ) return rel;

			}

		}

		function build( objects, data3mf ) {

			const group = new Group();

			const relationship = fetch3DModelPart( data3mf[ 'rels' ] );
			const buildData = data3mf.model[ relationship[ 'target' ].substring( 1 ) ][ 'build' ];

			for ( let i = 0; i < buildData.length; i ++ ) {

				const buildItem = buildData[ i ];
				const object3D = objects[ buildItem[ 'objectId' ] ].clone();

				// apply transform

				const transform = buildItem[ 'transform' ];

				if ( transform ) {

					object3D.applyMatrix4( transform );

				}

				group.add( object3D );

			}

			return group;

		}

		const data3mf = loadDocument( data );
		const objects = buildObjects( data3mf );

		return build( objects, data3mf );

	}

	/**
	 * Adds a 3MF extension.
	 *
	 * @param {Object} extension - The extension to add.
	 */
	addExtension( extension ) {

		this.availableExtensions.push( extension );

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
		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer ) );

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

		const scope = this;
		const textureLoader = new TextureLoader( this.manager );

		function loadDocument( data ) {

			let zip = null;
			let file = null;

			let relsName;
			let modelRelsName;
			const modelPartNames = [];
			const texturesPartNames = [];

			let modelRels;
			const modelParts = {};
			const printTicketParts = {};
			const texturesParts = {};

			const textDecoder = new TextDecoder();

			try {

				zip = fflate.unzipSync( new Uint8Array( data ) );

			} catch ( e ) {

				if ( e instanceof ReferenceError ) {

					console.error( 'THREE.3MFLoader: fflate missing and file is compressed.' );
					return null;

				}

			}

			let rootModelFile = null;

			for ( file in zip ) {

				if ( file.match( /\_rels\/.rels$/ ) ) {

					relsName = file;

				} else if ( file.match( /3D\/_rels\/.*\.model\.rels$/ ) ) {

					modelRelsName = file;

				} else if ( file.match( /^3D\/[^\/]*\.model$/ ) ) {

					rootModelFile = file;

				} else if ( file.match( /^3D\/.*\/.*\.model$/ ) ) {

					modelPartNames.push( file ); // sub models

				} else if ( file.match( /^3D\/Textures?\/.*/ ) ) {

					texturesPartNames.push( file );

				}

			}

			modelPartNames.push( rootModelFile ); // push root model at the end so it is processed after the sub models

			if ( relsName === undefined ) throw new Error( 'THREE.ThreeMFLoader: Cannot find relationship file `rels` in 3MF archive.' );

			//

			const relsView = zip[ relsName ];
			const relsFileText = textDecoder.decode( relsView );
			const rels = parseRelsXml( relsFileText );

			//

			if ( modelRelsName ) {

				const relsView = zip[ modelRelsName ];
				const relsFileText = textDecoder.decode( relsView );
				modelRels = parseRelsXml( relsFileText );

			}

			//

			for ( let i = 0; i < modelPartNames.length; i ++ ) {

				const modelPart = modelPartNames[ i ];
				const view = zip[ modelPart ];

				const fileText = textDecoder.decode( view );
				const xmlData = new DOMParser().parseFromString( fileText, 'application/xml' );

				if ( xmlData.documentElement.nodeName.toLowerCase() !== 'model' ) {

					console.error( 'THREE.3MFLoader: Error loading 3MF - no 3MF document found: ', modelPart );

				}

				const modelNode = xmlData.querySelector( 'model' );
				const extensions = {};

				for ( let i = 0; i < modelNode.attributes.length; i ++ ) {

					const attr = modelNode.attributes[ i ];
					if ( attr.name.match( /^xmlns:(.+)$/ ) ) {

						extensions[ attr.value ] = RegExp.$1;

					}

				}

				const modelData = parseModelNode( modelNode );
				modelData[ 'xml' ] = modelNode;

				if ( 0 < Object.keys( extensions ).length ) {

					modelData[ 'extensions' ] = extensions;

				}

				modelParts[ modelPart ] = modelData;

			}

			//

			for ( let i = 0; i < texturesPartNames.length; i ++ ) {

				const texturesPartName = texturesPartNames[ i ];
				texturesParts[ texturesPartName ] = zip[ texturesPartName ].buffer;

			}

			return {
				rels: rels,
				modelRels: modelRels,
				model: modelParts,
				printTicket: printTicketParts,
				texture: texturesParts
			};

		}

		function parseRelsXml( relsFileText ) {

			const relationships = [];

			const relsXmlData = new DOMParser().parseFromString( relsFileText, 'application/xml' );

			const relsNodes = relsXmlData.querySelectorAll( 'Relationship' );

			for ( let i = 0; i < relsNodes.length; i ++ ) {

				const relsNode = relsNodes[ i ];

				const relationship = {
					target: relsNode.getAttribute( 'Target' ), //required
					id: relsNode.getAttribute( 'Id' ), //required
					type: relsNode.getAttribute( 'Type' ) //required
				};

				relationships.push( relationship );

			}

			return relationships;

		}

		function parseMetadataNodes( metadataNodes ) {

			const metadataData = {};

			for ( let i = 0; i < metadataNodes.length; i ++ ) {

				const metadataNode = metadataNodes[ i ];
				const name = metadataNode.getAttribute( 'name' );
				const validNames = [
					'Title',
					'Designer',
					'Description',
					'Copyright',
					'LicenseTerms',
					'Rating',
					'CreationDate',
					'ModificationDate'
				];

				if ( 0 <= validNames.indexOf( name ) ) {

					metadataData[ name ] = metadataNode.textContent;

				}

			}

			return metadataData;

		}

		function parseBasematerialsNode( basematerialsNode ) {

			const basematerialsData = {
				id: basematerialsNode.getAttribute( 'id' ), // required
				basematerials: []
			};

			const basematerialNodes = basematerialsNode.querySelectorAll( 'base' );

			for ( let i = 0; i < basematerialNodes.length; i ++ ) {

				const basematerialNode = basematerialNodes[ i ];
				const basematerialData = parseBasematerialNode( basematerialNode );
				basematerialData.index = i; // the order and count of the material nodes form an implicit 0-based index
				basematerialsData.basematerials.push( basematerialData );

			}

			return basematerialsData;

		}

		function parseTexture2DNode( texture2DNode ) {

			const texture2dData = {
				id: texture2DNode.getAttribute( 'id' ), // required
				path: texture2DNode.getAttribute( 'path' ), // required
				contenttype: texture2DNode.getAttribute( 'contenttype' ), // required
				tilestyleu: texture2DNode.getAttribute( 'tilestyleu' ),
				tilestylev: texture2DNode.getAttribute( 'tilestylev' ),
				filter: texture2DNode.getAttribute( 'filter' ),
			};

			return texture2dData;

		}

		function parseTextures2DGroupNode( texture2DGroupNode ) {

			const texture2DGroupData = {
				id: texture2DGroupNode.getAttribute( 'id' ), // required
				texid: texture2DGroupNode.getAttribute( 'texid' ), // required
				displaypropertiesid: texture2DGroupNode.getAttribute( 'displaypropertiesid' )
			};

			const tex2coordNodes = texture2DGroupNode.querySelectorAll( 'tex2coord' );

			const uvs = [];

			for ( let i = 0; i < tex2coordNodes.length; i ++ ) {

				const tex2coordNode = tex2coordNodes[ i ];
				const u = tex2coordNode.getAttribute( 'u' );
				const v = tex2coordNode.getAttribute( 'v' );

				uvs.push( parseFloat( u ), parseFloat( v ) );

			}

			texture2DGroupData[ 'uvs' ] = new Float32Array( uvs );

			return texture2DGroupData;

		}

		function parseColorGroupNode( colorGroupNode ) {

			const colorGroupData = {
				id: colorGroupNode.getAttribute( 'id' ), // required
				displaypropertiesid: colorGroupNode.getAttribute( 'displaypropertiesid' )
			};

			const colorNodes = colorGroupNode.querySelectorAll( 'color' );

			const colors = [];
			const colorObject = new Color();

			for ( let i = 0; i < colorNodes.length; i ++ ) {

				const colorNode = colorNodes[ i ];
				const color = colorNode.getAttribute( 'color' );

				colorObject.setStyle( color.substring( 0, 7 ), COLOR_SPACE_3MF );

				colors.push( colorObject.r, colorObject.g, colorObject.b );

			}

			colorGroupData[ 'colors' ] = new Float32Array( colors );

			return colorGroupData;

		}

		function parseImplicitIONode( implicitIONode ) {

			const portNodes = implicitIONode.children;
			const portArguments = {};
			for ( let i = 0; i < portNodes.length; i ++ ) {

				const args = { type: portNodes[ i ].nodeName.substring( 2 ) };
				for ( let j = 0; j < portNodes[ i ].attributes.length; j ++ ) {

					const attrib = portNodes[ i ].attributes[ j ];
					if ( attrib.specified ) {

		 				args[ attrib.name ] = attrib.value;

					}

				}

				portArguments[ portNodes[ i ].getAttribute( 'identifier' ) ] = args;

			}

			return portArguments;

		}

		function parseImplicitFunctionNode( implicitFunctionNode ) {

			const implicitFunctionData = {
				id: implicitFunctionNode.getAttribute( 'id' ),
				displayname: implicitFunctionNode.getAttribute( 'displayname' )
			};

			const functionNodes = implicitFunctionNode.children;

			const operations = {};

			for ( let i = 0; i < functionNodes.length; i ++ ) {

				const operatorNode = functionNodes[ i ];

				if ( operatorNode.nodeName === 'i:in' || operatorNode.nodeName === 'i:out' ) {

					operations[ operatorNode.nodeName === 'i:in' ? 'inputs' : 'outputs' ] = parseImplicitIONode( operatorNode );

				} else {

					const inputNodes = operatorNode.children;
					const portArguments = { 'op': operatorNode.nodeName.substring( 2 ), 'identifier': operatorNode.getAttribute( 'identifier' ) };
					for ( let i = 0; i < inputNodes.length; i ++ ) {

						portArguments[ inputNodes[ i ].nodeName.substring( 2 ) ] = parseImplicitIONode( inputNodes[ i ] );

					}

					operations[ portArguments[ 'identifier' ] ] = portArguments;

				}

			}

			implicitFunctionData[ 'operations' ] = operations;

			return implicitFunctionData;

		}

		function parseMetallicDisplaypropertiesNode( metallicDisplaypropetiesNode ) {

			const metallicDisplaypropertiesData = {
				id: metallicDisplaypropetiesNode.getAttribute( 'id' ) // required
			};

			const metallicNodes = metallicDisplaypropetiesNode.querySelectorAll( 'pbmetallic' );

			const metallicData = [];

			for ( let i = 0; i < metallicNodes.length; i ++ ) {

				const metallicNode = metallicNodes[ i ];

				metallicData.push( {
					name: metallicNode.getAttribute( 'name' ), // required
					metallicness: parseFloat( metallicNode.getAttribute( 'metallicness' ) ), // required
					roughness: parseFloat( metallicNode.getAttribute( 'roughness' ) ) // required
				} );

			}

			metallicDisplaypropertiesData.data = metallicData;

			return metallicDisplaypropertiesData;

		}

		function parseBasematerialNode( basematerialNode ) {

			const basematerialData = {};

			basematerialData[ 'name' ] = basematerialNode.getAttribute( 'name' ); // required
			basematerialData[ 'displaycolor' ] = basematerialNode.getAttribute( 'displaycolor' ); // required
			basematerialData[ 'displaypropertiesid' ] = basematerialNode.getAttribute( 'displaypropertiesid' );

			return basematerialData;

		}

		function parseMeshNode( meshNode ) {

			const meshData = {};

			const vertices = [];
			const vertexNodes = meshNode.querySelectorAll( 'vertices vertex' );

			for ( let i = 0; i < vertexNodes.length; i ++ ) {

				const vertexNode = vertexNodes[ i ];
				const x = vertexNode.getAttribute( 'x' );
				const y = vertexNode.getAttribute( 'y' );
				const z = vertexNode.getAttribute( 'z' );

				vertices.push( parseFloat( x ), parseFloat( y ), parseFloat( z ) );

			}

			meshData[ 'vertices' ] = new Float32Array( vertices );

			const triangleProperties = [];
			const triangles = [];
			const triangleNodes = meshNode.querySelectorAll( 'triangles triangle' );

			for ( let i = 0; i < triangleNodes.length; i ++ ) {

				const triangleNode = triangleNodes[ i ];
				const v1 = triangleNode.getAttribute( 'v1' );
				const v2 = triangleNode.getAttribute( 'v2' );
				const v3 = triangleNode.getAttribute( 'v3' );
				const p1 = triangleNode.getAttribute( 'p1' );
				const p2 = triangleNode.getAttribute( 'p2' );
				const p3 = triangleNode.getAttribute( 'p3' );
				const pid = triangleNode.getAttribute( 'pid' );

				const triangleProperty = {};

				triangleProperty[ 'v1' ] = parseInt( v1, 10 );
				triangleProperty[ 'v2' ] = parseInt( v2, 10 );
				triangleProperty[ 'v3' ] = parseInt( v3, 10 );

				triangles.push( triangleProperty[ 'v1' ], triangleProperty[ 'v2' ], triangleProperty[ 'v3' ] );

				// optional

				if ( p1 ) {

					triangleProperty[ 'p1' ] = parseInt( p1, 10 );

				}

				if ( p2 ) {

					triangleProperty[ 'p2' ] = parseInt( p2, 10 );

				}

				if ( p3 ) {

					triangleProperty[ 'p3' ] = parseInt( p3, 10 );

				}

				if ( pid ) {

					triangleProperty[ 'pid' ] = pid;

				}

				if ( 0 < Object.keys( triangleProperty ).length ) {

					triangleProperties.push( triangleProperty );

				}

			}

			meshData[ 'triangleProperties' ] = triangleProperties;
			meshData[ 'triangles' ] = new Uint32Array( triangles );

			return meshData;

		}

		function parseComponentsNode( componentsNode ) {

			const components = [];

			const componentNodes = componentsNode.querySelectorAll( 'component' );

			for ( let i = 0; i < componentNodes.length; i ++ ) {

				const componentNode = componentNodes[ i ];
				const componentData = parseComponentNode( componentNode );
				components.push( componentData );

			}

			return components;

		}

		function parseComponentNode( componentNode ) {

			const componentData = {};

			componentData[ 'objectId' ] = componentNode.getAttribute( 'objectid' ); // required

			const transform = componentNode.getAttribute( 'transform' );

			if ( transform ) {

				componentData[ 'transform' ] = parseTransform( transform );

			}

			return componentData;

		}

		function parseTransform( transform ) {

			const t = [];
			transform.split( ' ' ).forEach( function ( s ) {

				t.push( parseFloat( s ) );

			} );

			const matrix = new Matrix4();
			matrix.set(
				t[ 0 ], t[ 3 ], t[ 6 ], t[ 9 ],
				t[ 1 ], t[ 4 ], t[ 7 ], t[ 10 ],
				t[ 2 ], t[ 5 ], t[ 8 ], t[ 11 ],
				 0.0, 0.0, 0.0, 1.0
			);

			return matrix;

		}

		function parseObjectNode( objectNode ) {

			const objectData = {
				type: objectNode.getAttribute( 'type' )
			};

			const id = objectNode.getAttribute( 'id' );

			if ( id ) {

				objectData[ 'id' ] = id;

			}

			const pid = objectNode.getAttribute( 'pid' );

			if ( pid ) {

				objectData[ 'pid' ] = pid;

			}

			const pindex = objectNode.getAttribute( 'pindex' );

			if ( pindex ) {

				objectData[ 'pindex' ] = pindex;

			}

			const thumbnail = objectNode.getAttribute( 'thumbnail' );

			if ( thumbnail ) {

				objectData[ 'thumbnail' ] = thumbnail;

			}

			const partnumber = objectNode.getAttribute( 'partnumber' );

			if ( partnumber ) {

				objectData[ 'partnumber' ] = partnumber;

			}

			const name = objectNode.getAttribute( 'name' );

			if ( name ) {

				objectData[ 'name' ] = name;

			}

			const meshNode = objectNode.querySelector( 'mesh' );

			if ( meshNode ) {

				objectData[ 'mesh' ] = parseMeshNode( meshNode );

			}

			const componentsNode = objectNode.querySelector( 'components' );

			if ( componentsNode ) {

				objectData[ 'components' ] = parseComponentsNode( componentsNode );

			}

			return objectData;

		}

		function parseResourcesNode( resourcesNode ) {

			const resourcesData = {};

			resourcesData[ 'basematerials' ] = {};
			const basematerialsNodes = resourcesNode.querySelectorAll( 'basematerials' );

			for ( let i = 0; i < basematerialsNodes.length; i ++ ) {

				const basematerialsNode = basematerialsNodes[ i ];
				const basematerialsData = parseBasematerialsNode( basematerialsNode );
				resourcesData[ 'basematerials' ][ basematerialsData[ 'id' ] ] = basematerialsData;

			}

			//

			resourcesData[ 'texture2d' ] = {};
			const textures2DNodes = resourcesNode.querySelectorAll( 'texture2d' );

			for ( let i = 0; i < textures2DNodes.length; i ++ ) {

				const textures2DNode = textures2DNodes[ i ];
				const texture2DData = parseTexture2DNode( textures2DNode );
				resourcesData[ 'texture2d' ][ texture2DData[ 'id' ] ] = texture2DData;

			}

			//

			resourcesData[ 'colorgroup' ] = {};
			const colorGroupNodes = resourcesNode.querySelectorAll( 'colorgroup' );

			for ( let i = 0; i < colorGroupNodes.length; i ++ ) {

				const colorGroupNode = colorGroupNodes[ i ];
				const colorGroupData = parseColorGroupNode( colorGroupNode );
				resourcesData[ 'colorgroup' ][ colorGroupData[ 'id' ] ] = colorGroupData;

			}

			//

			const implicitFunctionNodes = resourcesNode.querySelectorAll( 'implicitfunction' );

			if ( implicitFunctionNodes.length > 0 ) {

				resourcesData[ 'implicitfunction' ] = {};

			}


			for ( let i = 0; i < implicitFunctionNodes.length; i ++ ) {

				const implicitFunctionNode = implicitFunctionNodes[ i ];
				const implicitFunctionData = parseImplicitFunctionNode( implicitFunctionNode );
				resourcesData[ 'implicitfunction' ][ implicitFunctionData[ 'id' ] ] = implicitFunctionData;

			}

			//

			resourcesData[ 'pbmetallicdisplayproperties' ] = {};
			const pbmetallicdisplaypropertiesNodes = resourcesNode.querySelectorAll( 'pbmetallicdisplayproperties' );

			for ( let i = 0; i < pbmetallicdisplaypropertiesNodes.length; i ++ ) {

				const pbmetallicdisplaypropertiesNode = pbmetallicdisplaypropertiesNodes[ i ];
				const pbmetallicdisplaypropertiesData = parseMetallicDisplaypropertiesNode( pbmetallicdisplaypropertiesNode );
				resourcesData[ 'pbmetallicdisplayproperties' ][ pbmetallicdisplaypropertiesData[ 'id' ] ] = pbmetallicdisplaypropertiesData;

			}

			//

			resourcesData[ 'texture2dgroup' ] = {};
			const textures2DGroupNodes = resourcesNode.querySelectorAll( 'texture2dgroup' );

			for ( let i = 0; i < textures2DGroupNodes.length; i ++ ) {

				const textures2DGroupNode = textures2DGroupNodes[ i ];
				const textures2DGroupData = parseTextures2DGroupNode( textures2DGroupNode );
				resourcesData[ 'texture2dgroup' ][ textures2DGroupData[ 'id' ] ] = textures2DGroupData;

			}

			//

			resourcesData[ 'object' ] = {};
			const objectNodes = resourcesNode.querySelectorAll( 'object' );

			for ( let i = 0; i < objectNodes.length; i ++ ) {

				const objectNode = objectNodes[ i ];
				const objectData = parseObjectNode( objectNode );
				resourcesData[ 'object' ][ objectData[ 'id' ] ] = objectData;

			}

			return resourcesData;

		}

		function parseBuildNode( buildNode ) {

			const buildData = [];
			const itemNodes = buildNode.querySelectorAll( 'item' );

			for ( let i = 0; i < itemNodes.length; i ++ ) {

				const itemNode = itemNodes[ i ];
				const buildItem = {
					objectId: itemNode.getAttribute( 'objectid' )
				};
				const transform = itemNode.getAttribute( 'transform' );

				if ( transform ) {

					buildItem[ 'transform' ] = parseTransform( transform );

				}

				buildData.push( buildItem );

			}

			return buildData;

		}

		function parseModelNode( modelNode ) {

			const modelData = { unit: modelNode.getAttribute( 'unit' ) || 'millimeter' };
			const metadataNodes = modelNode.querySelectorAll( 'metadata' );

			if ( metadataNodes ) {

				modelData[ 'metadata' ] = parseMetadataNodes( metadataNodes );

			}

			const resourcesNode = modelNode.querySelector( 'resources' );

			if ( resourcesNode ) {

				modelData[ 'resources' ] = parseResourcesNode( resourcesNode );

			}

			const buildNode = modelNode.querySelector( 'build' );

			if ( buildNode ) {

				modelData[ 'build' ] = parseBuildNode( buildNode );

			}

			return modelData;

		}

		function buildTexture( texture2dgroup, objects, modelData, textureData ) {

			const texid = texture2dgroup.texid;
			const texture2ds = modelData.resources.texture2d;
			const texture2d = texture2ds[ texid ];

			if ( texture2d ) {

				const data = textureData[ texture2d.path ];
				const type = texture2d.contenttype;

				const blob = new Blob( [ data ], { type: type } );
				const sourceURI = URL.createObjectURL( blob );

				const texture = textureLoader.load( sourceURI, function () {

					URL.revokeObjectURL( sourceURI );

				} );

				texture.colorSpace = COLOR_SPACE_3MF;

				// texture parameters

				switch ( texture2d.tilestyleu ) {

					case 'wrap':
						texture.wrapS = RepeatWrapping;
						break;

					case 'mirror':
						texture.wrapS = MirroredRepeatWrapping;
						break;

					case 'none':
					case 'clamp':
						texture.wrapS = ClampToEdgeWrapping;
						break;

					default:
						texture.wrapS = RepeatWrapping;

				}

				switch ( texture2d.tilestylev ) {

					case 'wrap':
						texture.wrapT = RepeatWrapping;
						break;

					case 'mirror':
						texture.wrapT = MirroredRepeatWrapping;
						break;

					case 'none':
					case 'clamp':
						texture.wrapT = ClampToEdgeWrapping;
						break;

					default:
						texture.wrapT = RepeatWrapping;

				}

				switch ( texture2d.filter ) {

					case 'auto':
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearMipmapLinearFilter;
						break;

					case 'linear':
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearFilter;
						texture.generateMipmaps = false;
						break;

					case 'nearest':
						texture.magFilter = NearestFilter;
						texture.minFilter = NearestFilter;
						texture.generateMipmaps = false;
						break;

					default:
						texture.magFilter = LinearFilter;
						texture.minFilter = LinearMipmapLinearFilter;

				}

				return texture;

			} else {

				return null;

			}

		}

		function buildBasematerialsMeshes( basematerials, triangleProperties, meshData, objects, modelData, textureData, objectData ) {

			const objectPindex = objectData.pindex;

			const materialMap = {};

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];
				const pindex = ( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectPindex;

				if ( materialMap[ pindex ] === undefined ) materialMap[ pindex ] = [];

				materialMap[ pindex ].push( triangleProperty );

			}

			//

			const keys = Object.keys( materialMap );
			const meshes = [];

			for ( let i = 0, l = keys.length; i < l; i ++ ) {

				const materialIndex = keys[ i ];
				const trianglePropertiesProps = materialMap[ materialIndex ];
				const basematerialData = basematerials.basematerials[ materialIndex ];
				const material = getBuild( basematerialData, objects, modelData, textureData, objectData, buildBasematerial );

				//

				const geometry = new BufferGeometry();

				const positionData = [];

				const vertices = meshData.vertices;

				for ( let j = 0, jl = trianglePropertiesProps.length; j < jl; j ++ ) {

					const triangleProperty = trianglePropertiesProps[ j ];

					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 2 ] );

					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 2 ] );

					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 0 ] );
					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 1 ] );
					positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 2 ] );


				}

				geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );

				//

				const mesh = new Mesh( geometry, material );
				meshes.push( mesh );

			}

			return meshes;

		}

		function buildTexturedMesh( texture2dgroup, triangleProperties, meshData, objects, modelData, textureData, objectData ) {

			// geometry

			const geometry = new BufferGeometry();

			const positionData = [];
			const uvData = [];

			const vertices = meshData.vertices;
			const uvs = texture2dgroup.uvs;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];

				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v1 * 3 ) + 2 ] );

				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v2 * 3 ) + 2 ] );

				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 0 ] );
				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 1 ] );
				positionData.push( vertices[ ( triangleProperty.v3 * 3 ) + 2 ] );

				//

				uvData.push( uvs[ ( triangleProperty.p1 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p1 * 2 ) + 1 ] );

				uvData.push( uvs[ ( triangleProperty.p2 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p2 * 2 ) + 1 ] );

				uvData.push( uvs[ ( triangleProperty.p3 * 2 ) + 0 ] );
				uvData.push( uvs[ ( triangleProperty.p3 * 2 ) + 1 ] );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );
			geometry.setAttribute( 'uv', new Float32BufferAttribute( uvData, 2 ) );

			// material

			const texture = getBuild( texture2dgroup, objects, modelData, textureData, objectData, buildTexture );

			const material = new MeshPhongMaterial( { map: texture, flatShading: true } );

			// mesh

			const mesh = new Mesh( geometry, material );

			return mesh;

		}

		function buildVertexColorMesh( colorgroup, triangleProperties, meshData, objectData ) {

			// geometry

			const geometry = new BufferGeometry();

			const positionData = [];
			const colorData = [];

			const vertices = meshData.vertices;
			const colors = colorgroup.colors;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];

				const v1 = triangleProperty.v1;
				const v2 = triangleProperty.v2;
				const v3 = triangleProperty.v3;

				positionData.push( vertices[ ( v1 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v1 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v1 * 3 ) + 2 ] );

				positionData.push( vertices[ ( v2 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v2 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v2 * 3 ) + 2 ] );

				positionData.push( vertices[ ( v3 * 3 ) + 0 ] );
				positionData.push( vertices[ ( v3 * 3 ) + 1 ] );
				positionData.push( vertices[ ( v3 * 3 ) + 2 ] );

				//

				const p1 = ( triangleProperty.p1 !== undefined ) ? triangleProperty.p1 : objectData.pindex;
				const p2 = ( triangleProperty.p2 !== undefined ) ? triangleProperty.p2 : p1;
				const p3 = ( triangleProperty.p3 !== undefined ) ? triangleProperty.p3 : p1;

				colorData.push( colors[ ( p1 * 3 ) + 0 ] );
				colorData.push( colors[ ( p1 * 3 ) + 1 ] );
				colorData.push( colors[ ( p1 * 3 ) + 2 ] );

				colorData.push( colors[ ( p2 * 3 ) + 0 ] );
				colorData.push( colors[ ( p2 * 3 ) + 1 ] );
				colorData.push( colors[ ( p2 * 3 ) + 2 ] );

				colorData.push( colors[ ( p3 * 3 ) + 0 ] );
				colorData.push( colors[ ( p3 * 3 ) + 1 ] );
				colorData.push( colors[ ( p3 * 3 ) + 2 ] );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( positionData, 3 ) );
			geometry.setAttribute( 'color', new Float32BufferAttribute( colorData, 3 ) );

			// material

			const material = new MeshPhongMaterial( { vertexColors: true, flatShading: true } );

			// mesh

			const mesh = new Mesh( geometry, material );

			return mesh;

		}

		function buildDefaultMesh( meshData ) {

			const geometry = new BufferGeometry();
			geometry.setIndex( new BufferAttribute( meshData[ 'triangles' ], 1 ) );
			geometry.setAttribute( 'position', new BufferAttribute( meshData[ 'vertices' ], 3 ) );

			const material = new MeshPhongMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0xffffff,
				flatShading: true
			} );

			const mesh = new Mesh( geometry, material );

			return mesh;

		}

		function buildMeshes( resourceMap, meshData, objects, modelData, textureData, objectData ) {

			const keys = Object.keys( resourceMap );
			const meshes = [];

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				const resourceId = keys[ i ];
				const triangleProperties = resourceMap[ resourceId ];
				const resourceType = getResourceType( resourceId, modelData );

				switch ( resourceType ) {

					case 'material':
						const basematerials = modelData.resources.basematerials[ resourceId ];
						const newMeshes = buildBasematerialsMeshes( basematerials, triangleProperties, meshData, objects, modelData, textureData, objectData );

						for ( let j = 0, jl = newMeshes.length; j < jl; j ++ ) {

							meshes.push( newMeshes[ j ] );

						}

						break;

					case 'texture':
						const texture2dgroup = modelData.resources.texture2dgroup[ resourceId ];
						meshes.push( buildTexturedMesh( texture2dgroup, triangleProperties, meshData, objects, modelData, textureData, objectData ) );
						break;

					case 'vertexColors':
						const colorgroup = modelData.resources.colorgroup[ resourceId ];
						meshes.push( buildVertexColorMesh( colorgroup, triangleProperties, meshData, objectData ) );
						break;

					case 'default':
						meshes.push( buildDefaultMesh( meshData ) );
						break;

					default:
						console.error( 'THREE.3MFLoader: Unsupported resource type.' );

				}

			}

			if ( objectData.name ) {

				for ( let i = 0; i < meshes.length; i ++ ) {

					meshes[ i ].name = objectData.name;

				}

			}

			return meshes;

		}

		function getResourceType( pid, modelData ) {

			if ( modelData.resources.texture2dgroup[ pid ] !== undefined ) {

				return 'texture';

			} else if ( modelData.resources.basematerials[ pid ] !== undefined ) {

				return 'material';

			} else if ( modelData.resources.colorgroup[ pid ] !== undefined ) {

				return 'vertexColors';

			} else if ( pid === 'default' ) {

				return 'default';

			} else {

				return undefined;

			}

		}

		function analyzeObject( meshData, objectData ) {

			const resourceMap = {};

			const triangleProperties = meshData[ 'triangleProperties' ];

			const objectPid = objectData.pid;

			for ( let i = 0, l = triangleProperties.length; i < l; i ++ ) {

				const triangleProperty = triangleProperties[ i ];
				let pid = ( triangleProperty.pid !== undefined ) ? triangleProperty.pid : objectPid;

				if ( pid === undefined ) pid = 'default';

				if ( resourceMap[ pid ] === undefined ) resourceMap[ pid ] = [];

				resourceMap[ pid ].push( triangleProperty );

			}

			return resourceMap;

		}

		function buildGroup( meshData, objects, modelData, textureData, objectData ) {

			const group = new Group();

			const resourceMap = analyzeObject( meshData, objectData );
			const meshes = buildMeshes( resourceMap, meshData, objects, modelData, textureData, objectData );

			for ( let i = 0, l = meshes.length; i < l; i ++ ) {

				group.add( meshes[ i ] );

			}

			return group;

		}

		function applyExtensions( extensions, meshData, modelXml ) {

			if ( ! extensions ) {

				return;

			}

			const availableExtensions = [];
			const keys = Object.keys( extensions );

			for ( let i = 0; i < keys.length; i ++ ) {

				const ns = keys[ i ];

				for ( let j = 0; j < scope.availableExtensions.length; j ++ ) {

					const extension = scope.availableExtensions[ j ];

					if ( extension.ns === ns ) {

						availableExtensions.push( extension );

					}

				}

			}

			for ( let i = 0; i < availableExtensions.length; i ++ ) {

				const extension = availableExtensions[ i ];
				extension.apply( modelXml, extensions[ extension[ 'ns' ] ], meshData );

			}

		}

		function getBuild( data, objects, modelData, textureData, objectData, builder ) {

			if ( data.build !== undefined ) return data.build;

			data.build = builder( data, objects, modelData, textureData, objectData );

			return data.build;

		}

		function buildBasematerial( materialData, objects, modelData ) {

			let material;

			const displaypropertiesid = materialData.displaypropertiesid;
			const pbmetallicdisplayproperties = modelData.resources.pbmetallicdisplayproperties;

			if ( displaypropertiesid !== null && pbmetallicdisplayproperties[ displaypropertiesid ] !== undefined ) {

				// metallic display property, use StandardMaterial

				const pbmetallicdisplayproperty = pbmetallicdisplayproperties[ displaypropertiesid ];
				const metallicData = pbmetallicdisplayproperty.data[ materialData.index ];

				material = new MeshStandardMaterial( { flatShading: true, roughness: metallicData.roughness, metalness: metallicData.metallicness } );

			} else {

				// otherwise use PhongMaterial

				material = new MeshPhongMaterial( { flatShading: true } );

			}

			material.name = materialData.name;

			// displaycolor MUST be specified with a value of a 6 or 8 digit hexadecimal number, e.g. "#RRGGBB" or "#RRGGBBAA"

			const displaycolor = materialData.displaycolor;

			const color = displaycolor.substring( 0, 7 );
			material.color.setStyle( color, COLOR_SPACE_3MF );

			// process alpha if set

			if ( displaycolor.length === 9 ) {

				material.opacity = parseInt( displaycolor.charAt( 7 ) + displaycolor.charAt( 8 ), 16 ) / 255;

			}

			return material;

		}

		function buildComposite( compositeData, objects, modelData, textureData ) {

			const composite = new Group();

			for ( let j = 0; j < compositeData.length; j ++ ) {

				const component = compositeData[ j ];
				let build = objects[ component.objectId ];

				if ( build === undefined ) {

					buildObject( component.objectId, objects, modelData, textureData );
					build = objects[ component.objectId ];

				}

				const object3D = build.clone();

				// apply component transform

				const transform = component.transform;

				if ( transform ) {

					object3D.applyMatrix4( transform );

				}

				composite.add( object3D );

			}

			return composite;

		}

		function buildObject( objectId, objects, modelData, textureData ) {

			const objectData = modelData[ 'resources' ][ 'object' ][ objectId ];

			if ( objectData[ 'mesh' ] ) {

				const meshData = objectData[ 'mesh' ];

				const extensions = modelData[ 'extensions' ];
				const modelXml = modelData[ 'xml' ];

				applyExtensions( extensions, meshData, modelXml );

				objects[ objectData.id ] = getBuild( meshData, objects, modelData, textureData, objectData, buildGroup );

			} else {

				const compositeData = objectData[ 'components' ];

				objects[ objectData.id ] = getBuild( compositeData, objects, modelData, textureData, objectData, buildComposite );

			}

			if ( objectData.name ) {

				objects[ objectData.id ].name = objectData.name;

			}

			if ( modelData.resources.implicitfunction ) {

				console.warn( 'THREE.ThreeMFLoader: Implicit Functions are implemented in data-only.', modelData.resources.implicitfunction );

			}

		}

		function buildObjects( data3mf ) {

			const modelsData = data3mf.model;
			const modelRels = data3mf.modelRels;
			const objects = {};
			const modelsKeys = Object.keys( modelsData );
			const textureData = {};

			// evaluate model relationships to textures

			if ( modelRels ) {

				for ( let i = 0, l = modelRels.length; i < l; i ++ ) {

					const modelRel = modelRels[ i ];
					const textureKey = modelRel.target.substring( 1 );

					if ( data3mf.texture[ textureKey ] ) {

						textureData[ modelRel.target ] = data3mf.texture[ textureKey ];

					}

				}

			}

			// start build

			for ( let i = 0; i < modelsKeys.length; i ++ ) {

				const modelsKey = modelsKeys[ i ];
				const modelData = modelsData[ modelsKey ];

				const objectIds = Object.keys( modelData[ 'resources' ][ 'object' ] );

				for ( let j = 0; j < objectIds.length; j ++ ) {

					const objectId = objectIds[ j ];

					buildObject( objectId, objects, modelData, textureData );

				}

			}

			return objects;

		}

		function fetch3DModelPart( rels ) {

			for ( let i = 0; i < rels.length; i ++ ) {

				const rel = rels[ i ];
				const extension = rel.target.split( '.' ).pop();

				if ( extension.toLowerCase() === 'model' ) return rel;

			}

		}

		function build( objects, data3mf ) {

			const group = new Group();

			const relationship = fetch3DModelPart( data3mf[ 'rels' ] );
			const buildData = data3mf.model[ relationship[ 'target' ].substring( 1 ) ][ 'build' ];

			for ( let i = 0; i < buildData.length; i ++ ) {

				const buildItem = buildData[ i ];
				const object3D = objects[ buildItem[ 'objectId' ] ].clone();

				// apply transform

				const transform = buildItem[ 'transform' ];

				if ( transform ) {

					object3D.applyMatrix4( transform );

				}

				group.add( object3D );

			}

			return group;

		}

		const data3mf = loadDocument( data );
		const objects = buildObjects( data3mf );

		return build( objects, data3mf );

	}
```
</details>

##### `addExtension(extension: any): void`

<details><summary>Code</summary>

```ts
addExtension( extension ) {

		this.availableExtensions.push( extension );

	}
```
</details>


---