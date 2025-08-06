[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `GLTFExporter.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 62 |
| 🧱 Classes | 16 |
| 📦 Imports | 27 |
| 📊 Variables & Constants | 243 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/exporters/GLTFExporter.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `ClampToEdgeWrapping` | `three` |
| `Color` | `three` |
| `DoubleSide` | `three` |
| `InterpolateDiscrete` | `three` |
| `InterpolateLinear` | `three` |
| `NoColorSpace` | `three` |
| `LinearFilter` | `three` |
| `LinearMipmapLinearFilter` | `three` |
| `LinearMipmapNearestFilter` | `three` |
| `MathUtils` | `three` |
| `Matrix4` | `three` |
| `MirroredRepeatWrapping` | `three` |
| `NearestFilter` | `three` |
| `NearestMipmapLinearFilter` | `three` |
| `NearestMipmapNearestFilter` | `three` |
| `PropertyBinding` | `three` |
| `RGBAFormat` | `three` |
| `RepeatWrapping` | `three` |
| `Scene` | `three` |
| `Source` | `three` |
| `SRGBColorSpace` | `three` |
| `CompressedTexture` | `three` |
| `Vector3` | `three` |
| `Quaternion` | `three` |
| `REVISION` | `three` |
| `ImageUtils` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `KHR_mesh_quantization_Extra...` | `{ POSITION: string[]; NORMAL: string[...` | let/var | `{ POSITION: [ 'byte', 'byte normalized', 'unsigned byte', 'unsigned byte norm...` | ✗ |
| `writer` | `GLTFWriter` | let/var | `new GLTFWriter()` | ✗ |
| `plugins` | `any[]` | let/var | `[]` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `WEBGL_CONSTANTS` | `{ POINTS: number; LINES: number; LINE...` | let/var | `{ POINTS: 0x0000, LINES: 0x0001, LINE_LOOP: 0x0002, LINE_STRIP: 0x0003, TRIAN...` | ✗ |
| `KHR_MESH_QUANTIZATION` | `"KHR_mesh_quantization"` | let/var | `'KHR_mesh_quantization'` | ✗ |
| `THREE_TO_WEBGL` | `typeof THREE_TO_WEBGL` | let/var | `{}` | ✗ |
| `PATH_PROPERTIES` | `{ scale: string; position: string; qu...` | let/var | `{ scale: 'scale', position: 'translation', quaternion: 'rotation', morphTarge...` | ✗ |
| `DEFAULT_SPECULAR_COLOR` | `any` | let/var | `new Color()` | ✗ |
| `GLB_HEADER_BYTES` | `12` | let/var | `12` | ✗ |
| `GLB_HEADER_MAGIC` | `1179937895` | let/var | `0x46546C67` | ✗ |
| `GLB_VERSION` | `2` | let/var | `2` | ✗ |
| `GLB_CHUNK_PREFIX_BYTES` | `8` | let/var | `8` | ✗ |
| `GLB_CHUNK_TYPE_JSON` | `1313821514` | let/var | `0x4E4F534A` | ✗ |
| `GLB_CHUNK_TYPE_BIN` | `5130562` | let/var | `0x004E4942` | ✗ |
| `output` | `{ min: any[]; max: any[]; }` | let/var | `{ min: new Array( attribute.itemSize ).fill( Number.POSITIVE_INFINITY ), max:...` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `array` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( paddedLength )` | ✗ |
| `quality` | `any` | let/var | `*not shown*` | ✗ |
| `writer` | `this` | let/var | `this` | ✗ |
| `buffers` | `any[]` | let/var | `writer.buffers` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `writer.json` | ✗ |
| `extensionsUsed` | `{}` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionsRequired` | `{}` | let/var | `writer.extensionsRequired` | ✗ |
| `blob` | `Blob` | let/var | `new Blob( buffers, { type: 'application/octet-stream' } )` | ✗ |
| `reader` | `FileReader` | let/var | `new FileReader()` | ✗ |
| `binaryChunkPrefix` | `DataView<ArrayBuffer>` | let/var | `new DataView( new ArrayBuffer( GLB_CHUNK_PREFIX_BYTES ) )` | ✗ |
| `jsonChunkPrefix` | `DataView<ArrayBuffer>` | let/var | `new DataView( new ArrayBuffer( GLB_CHUNK_PREFIX_BYTES ) )` | ✗ |
| `header` | `ArrayBuffer` | let/var | `new ArrayBuffer( GLB_HEADER_BYTES )` | ✗ |
| `headerView` | `DataView<ArrayBuffer>` | let/var | `new DataView( header )` | ✗ |
| `totalByteLength` | `number` | let/var | `GLB_HEADER_BYTES + jsonChunkPrefix.byteLength + jsonChunk.byteLength + binary...` | ✗ |
| `glbBlob` | `Blob` | let/var | `new Blob( [ header, jsonChunkPrefix, jsonChunk, binaryChunkPrefix, binaryChun...` | ✗ |
| `glbReader` | `FileReader` | let/var | `new FileReader()` | ✗ |
| `reader` | `FileReader` | let/var | `new FileReader()` | ✗ |
| `base64data` | `string \| ArrayBuffer` | let/var | `reader.result` | ✗ |
| `options` | `{}` | let/var | `this.options` | ✗ |
| `extensionsUsed` | `{}` | let/var | `this.extensionsUsed` | ✗ |
| `uids` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `cache` | `{ meshes: Map<any, any>; attributes: ...` | let/var | `this.cache` | ✗ |
| `v` | `any` | let/var | `new Vector3()` | ✗ |
| `cache` | `{ meshes: Map<any, any>; attributes: ...` | let/var | `this.cache` | ✗ |
| `v` | `any` | let/var | `new Vector3()` | ✗ |
| `didTransform` | `boolean` | let/var | `false` | ✗ |
| `transformDef` | `{ offset: any; rotation: any; scale: ...` | let/var | `{}` | ✗ |
| `metalness` | `any` | let/var | `metalnessMap ? metalnessMap.image : null` | ✗ |
| `roughness` | `any` | let/var | `roughnessMap ? roughnessMap.image : null` | ✗ |
| `data` | `Uint8ClampedArray<ArrayBufferLike>` | let/var | `context.getImageData( 0, 0, width, height ).data` | ✗ |
| `data` | `Uint8ClampedArray<ArrayBufferLike>` | let/var | `context.getImageData( 0, 0, width, height ).data` | ✗ |
| `reference` | `any` | let/var | `metalnessMap \|\| roughnessMap` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `buffers` | `any[]` | let/var | `this.buffers` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `componentSize` | `any` | let/var | `*not shown*` | ✗ |
| `byteStride` | `number` | let/var | `attribute.itemSize * componentSize` | ✗ |
| `dataView` | `DataView<ArrayBuffer>` | let/var | `new DataView( new ArrayBuffer( byteLength ) )` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `bufferViewDef` | `{ buffer: 0; byteOffset: number; byte...` | let/var | `{ buffer: this.processBuffer( dataView.buffer ), byteOffset: this.byteOffset,...` | ✗ |
| `output` | `{ id: number; byteLength: number; }` | let/var | `{ id: json.bufferViews.length - 1, byteLength: 0 }` | ✗ |
| `writer` | `this` | let/var | `this` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `writer.json` | ✗ |
| `reader` | `FileReader` | let/var | `new FileReader()` | ✗ |
| `bufferViewDef` | `{ buffer: 0; byteOffset: number; byte...` | let/var | `{ buffer: writer.processBuffer( buffer ), byteOffset: writer.byteOffset, byte...` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `types` | `{ 1: string; 2: string; 3: string; 4:...` | let/var | `{ 1: 'SCALAR', 2: 'VEC2', 3: 'VEC3', 4: 'VEC4', 9: 'MAT3', 16: 'MAT4' }` | ✗ |
| `componentType` | `any` | let/var | `*not shown*` | ✗ |
| `bufferViewTarget` | `any` | let/var | `*not shown*` | ✗ |
| `accessorDef` | `{ bufferView: any; byteOffset: any; c...` | let/var | `{ bufferView: bufferView.id, byteOffset: bufferView.byteOffset, componentType...` | ✗ |
| `writer` | `this` | let/var | `this` | ✗ |
| `cache` | `{ meshes: Map<any, any>; attributes: ...` | let/var | `writer.cache` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `writer.json` | ✗ |
| `options` | `{}` | let/var | `writer.options` | ✗ |
| `pending` | `any[]` | let/var | `writer.pending` | ✗ |
| `key` | `string` | let/var | `mimeType + ':flipY/' + flipY.toString()` | ✗ |
| `imageDef` | `{ mimeType: string; }` | let/var | `{ mimeType: mimeType }` | ✗ |
| `data` | `Uint8ClampedArray<ArrayBuffer>` | let/var | `new Uint8ClampedArray( image.height * image.width * 4 )` | ✗ |
| `index` | `number` | let/var | `json.images.push( imageDef ) - 1` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `samplerDef` | `{ magFilter: any; minFilter: any; wra...` | let/var | `{ magFilter: THREE_TO_WEBGL[ map.magFilter ], minFilter: THREE_TO_WEBGL[ map....` | ✗ |
| `writer` | `this` | let/var | `this` | ✗ |
| `options` | `{}` | let/var | `writer.options` | ✗ |
| `cache` | `{ meshes: Map<any, any>; attributes: ...` | let/var | `this.cache` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `mimeType` | `any` | let/var | `map.userData.mimeType` | ✗ |
| `textureDef` | `{ sampler: number; source: number; }` | let/var | `{ sampler: this.processSampler( map ), source: this.processImage( map.image, ...` | ✗ |
| `index` | `number` | let/var | `json.textures.push( textureDef ) - 1` | ✗ |
| `cache` | `{ meshes: Map<any, any>; attributes: ...` | let/var | `this.cache` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `materialDef` | `{ pbrMetallicRoughness: {}; }` | let/var | `{ pbrMetallicRoughness: {} }` | ✗ |
| `metalRoughTexture` | `any` | let/var | `await this.buildMetalRoughTextureAsync( material.metalnessMap, material.rough...` | ✗ |
| `metalRoughMapDef` | `{ index: number; texCoord: any; }` | let/var | `{ index: await this.processTextureAsync( metalRoughTexture ), texCoord: metal...` | ✗ |
| `baseColorMapDef` | `{ index: number; texCoord: any; }` | let/var | `{ index: await this.processTextureAsync( material.map ), texCoord: material.m...` | ✗ |
| `emissive` | `any` | let/var | `material.emissive` | ✗ |
| `emissiveMapDef` | `{ index: number; texCoord: any; }` | let/var | `{ index: await this.processTextureAsync( material.emissiveMap ), texCoord: ma...` | ✗ |
| `normalMapDef` | `{ index: number; texCoord: any; }` | let/var | `{ index: await this.processTextureAsync( material.normalMap ), texCoord: mate...` | ✗ |
| `occlusionMapDef` | `{ index: number; texCoord: any; }` | let/var | `{ index: await this.processTextureAsync( material.aoMap ), texCoord: material...` | ✗ |
| `index` | `number` | let/var | `json.materials.push( materialDef ) - 1` | ✗ |
| `cache` | `{ meshes: Map<any, any>; attributes: ...` | let/var | `this.cache` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `meshCacheKeyParts` | `any[]` | let/var | `[ mesh.geometry.uuid ]` | ✗ |
| `geometry` | `any` | let/var | `mesh.geometry` | ✗ |
| `mode` | `any` | let/var | `*not shown*` | ✗ |
| `meshDef` | `{ weights: any[]; extras: { targetNam...` | let/var | `{}` | ✗ |
| `attributes` | `{}` | let/var | `{}` | ✗ |
| `primitives` | `any[]` | let/var | `[]` | ✗ |
| `targets` | `any[]` | let/var | `[]` | ✗ |
| `nameConversion` | `{ uv: string; uv1: string; uv2: strin...` | let/var | `{ uv: 'TEXCOORD_0', uv1: 'TEXCOORD_1', uv2: 'TEXCOORD_2', uv3: 'TEXCOORD_3', ...` | ✗ |
| `modifiedAttribute` | `any` | let/var | `null` | ✗ |
| `attribute` | `any` | let/var | `geometry.attributes[ attributeName ]` | ✗ |
| `validVertexAttributes` | `RegExp` | let/var | `/^(POSITION\|NORMAL\|TANGENT\|TEXCOORD_\d+\|COLOR_\d+\|JOINTS_\d+\|WEIGHTS_\d...` | ✗ |
| `array` | `any` | let/var | `attribute.array` | ✗ |
| `weights` | `any[]` | let/var | `[]` | ✗ |
| `targetNames` | `any[]` | let/var | `[]` | ✗ |
| `reverseDictionary` | `{}` | let/var | `{}` | ✗ |
| `target` | `{}` | let/var | `{}` | ✗ |
| `warned` | `boolean` | let/var | `false` | ✗ |
| `attribute` | `any` | let/var | `geometry.morphAttributes[ attributeName ][ i ]` | ✗ |
| `baseAttribute` | `any` | let/var | `geometry.attributes[ attributeName ]` | ✗ |
| `didForceIndices` | `boolean` | let/var | `false` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `materials` | `any` | let/var | `isMultiMaterial ? mesh.material : [ mesh.material ]` | ✗ |
| `groups` | `any` | let/var | `isMultiMaterial ? geometry.groups : [ { materialIndex: 0, start: undefined, c...` | ✗ |
| `primitive` | `{ mode: number; attributes: {}; }` | let/var | `{ mode: mode, attributes: attributes, }` | ✗ |
| `material` | `number` | let/var | `await this.processMaterialAsync( materials[ groups[ i ].materialIndex ] )` | ✗ |
| `index` | `number` | let/var | `json.meshes.push( meshDef ) - 1` | ✗ |
| `attrType` | `any` | let/var | `undefined` | ✗ |
| `attrNamePrefix` | `string` | let/var | `attributeName.split( '_', 1 )[ 0 ]` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `isOrtho` | `any` | let/var | `camera.isOrthographicCamera` | ✗ |
| `cameraDef` | `{ type: string; }` | let/var | `{ type: isOrtho ? 'orthographic' : 'perspective' }` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `nodeMap` | `Map<any, any>` | let/var | `this.nodeMap` | ✗ |
| `tracks` | `any` | let/var | `clip.tracks` | ✗ |
| `channels` | `any[]` | let/var | `[]` | ✗ |
| `samplers` | `any[]` | let/var | `[]` | ✗ |
| `track` | `any` | let/var | `tracks[ i ]` | ✗ |
| `trackProperty` | `any` | let/var | `PATH_PROPERTIES[ trackBinding.propertyName ]` | ✗ |
| `inputItemSize` | `1` | let/var | `1` | ✗ |
| `outputItemSize` | `number` | let/var | `track.values.length / track.times.length` | ✗ |
| `interpolation` | `any` | let/var | `*not shown*` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `nodeMap` | `Map<any, any>` | let/var | `this.nodeMap` | ✗ |
| `node` | `any` | let/var | `json.nodes[ nodeMap.get( object ) ]` | ✗ |
| `skeleton` | `any` | let/var | `object.skeleton` | ✗ |
| `rootJoint` | `any` | let/var | `object.skeleton.bones[ 0 ]` | ✗ |
| `joints` | `any[]` | let/var | `[]` | ✗ |
| `inverseBindMatrices` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( skeleton.bones.length * 16 )` | ✗ |
| `temporaryBoneInverse` | `any` | let/var | `new Matrix4()` | ✗ |
| `skinIndex` | `number` | let/var | `node.skin = json.skins.length - 1` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `options` | `{}` | let/var | `this.options` | ✗ |
| `nodeMap` | `Map<any, any>` | let/var | `this.nodeMap` | ✗ |
| `nodeDef` | `{ rotation: any; translation: any; sc...` | let/var | `{}` | ✗ |
| `meshIndex` | `number` | let/var | `await this.processMeshAsync( object )` | ✗ |
| `nodeIndex` | `number` | let/var | `json.nodes.push( nodeDef ) - 1` | ✗ |
| `children` | `any[]` | let/var | `[]` | ✗ |
| `child` | `any` | let/var | `object.children[ i ]` | ✗ |
| `childNodeIndex` | `number` | let/var | `await this.processNodeAsync( child )` | ✗ |
| `json` | `{ asset: { version: string; generator...` | let/var | `this.json` | ✗ |
| `options` | `{}` | let/var | `this.options` | ✗ |
| `sceneDef` | `{ name: any; nodes: number[]; }` | let/var | `{}` | ✗ |
| `nodes` | `any[]` | let/var | `[]` | ✗ |
| `child` | `any` | let/var | `scene.children[ i ]` | ✗ |
| `nodeIndex` | `number` | let/var | `await this.processNodeAsync( child )` | ✗ |
| `scene` | `any` | let/var | `new Scene()` | ✗ |
| `options` | `{}` | let/var | `this.options` | ✗ |
| `objectsWithoutScene` | `any[]` | let/var | `[]` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `json` | `any` | let/var | `writer.json` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `lightDef` | `{ name: any; color: any; intensity: a...` | let/var | `{}` | ✗ |
| `lights` | `any` | let/var | `json.extensions[ this.name ].lights` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ clearcoatFactor: any; clearcoatText...` | let/var | `{}` | ✗ |
| `clearcoatMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.clearcoatMap ), texCoord:...` | ✗ |
| `clearcoatRoughnessMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.clearcoatRoughnessMap ), ...` | ✗ |
| `clearcoatNormalMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.clearcoatNormalMap ), tex...` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ dispersion: any; }` | let/var | `{}` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ iridescenceFactor: any; iridescence...` | let/var | `{}` | ✗ |
| `iridescenceMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.iridescenceMap ), texCoor...` | ✗ |
| `iridescenceThicknessMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.iridescenceThicknessMap )...` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ transmissionFactor: any; transmissi...` | let/var | `{}` | ✗ |
| `transmissionMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.transmissionMap ), texCoo...` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ thicknessFactor: any; thicknessText...` | let/var | `{}` | ✗ |
| `thicknessMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.thicknessMap ), texCoord:...` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ ior: any; }` | let/var | `{}` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ specularTexture: { index: any; texC...` | let/var | `{}` | ✗ |
| `specularIntensityMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.specularIntensityMap ), t...` | ✗ |
| `specularColorMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.specularColorMap ), texCo...` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ sheenRoughnessTexture: { index: any...` | let/var | `{}` | ✗ |
| `sheenRoughnessMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.sheenRoughnessMap ), texC...` | ✗ |
| `sheenColorMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.sheenColorMap ), texCoord...` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ anisotropyTexture: { index: any; };...` | let/var | `{}` | ✗ |
| `anisotropyMapDef` | `{ index: any; }` | let/var | `{ index: await writer.processTextureAsync( material.anisotropyMap ) }` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ emissiveStrength: any; }` | let/var | `{}` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `extensionsUsed` | `any` | let/var | `writer.extensionsUsed` | ✗ |
| `extensionDef` | `{ bumpTexture: { index: any; texCoord...` | let/var | `{}` | ✗ |
| `bumpMapDef` | `{ index: any; texCoord: any; }` | let/var | `{ index: await writer.processTextureAsync( material.bumpMap ), texCoord: mate...` | ✗ |
| `writer` | `any` | let/var | `this.writer` | ✗ |
| `mesh` | `any` | let/var | `object` | ✗ |
| `translationAttr` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( mesh.count * 3 )` | ✗ |
| `rotationAttr` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( mesh.count * 4 )` | ✗ |
| `scaleAttr` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( mesh.count * 3 )` | ✗ |
| `matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `position` | `any` | let/var | `new Vector3()` | ✗ |
| `quaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `scale` | `any` | let/var | `new Vector3()` | ✗ |
| `attributes` | `{ TRANSLATION: any; ROTATION: any; SC...` | let/var | `{ TRANSLATION: writer.processAccessor( new BufferAttribute( translationAttr, ...` | ✗ |
| `tolerance` | `0.001` | let/var | `0.001` | ✗ |
| `times` | `any` | let/var | `new track.TimeBufferType( track.times.length + 1 )` | ✗ |
| `values` | `any` | let/var | `new track.ValueBufferType( track.values.length + valueSize )` | ✗ |
| `index` | `any` | let/var | `*not shown*` | ✗ |
| `tracks` | `any[]` | let/var | `[]` | ✗ |
| `mergedTracks` | `{}` | let/var | `{}` | ✗ |
| `sourceTracks` | `any` | let/var | `clip.tracks` | ✗ |
| `sourceTrack` | `any` | let/var | `sourceTracks[ i ]` | ✗ |
| `targetCount` | `any` | let/var | `sourceTrackNode.morphTargetInfluences.length` | ✗ |
| `targetIndex` | `any` | let/var | `sourceTrackNode.morphTargetDictionary[ sourceTrackBinding.propertyIndex ]` | ✗ |
| `mergedTrack` | `any` | let/var | `*not shown*` | ✗ |
| `values` | `any` | let/var | `new mergedTrack.ValueBufferType( targetCount * mergedTrack.times.length )` | ✗ |
| `dstAttribute` | `any` | let/var | `new BufferAttribute( new Float32Array( srcAttribute.count * srcAttribute.item...` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `getToBlobPromise` | *none* | new Promise(...) |


---

## Functions

### `GLTFExporter.register(callback: any): GLTFExporter`

**JSDoc:**
```typescript
/**
	 * Registers a plugin callback. This API is internally used to implement the various
	 * glTF extensions but can also used by third-party code to add additional logic
	 * to the exporter.
	 *
	 * @param {function(writer:GLTFWriter)} callback - The callback function to register.
	 * @return {GLTFExporter} A reference to this exporter.
	 */
```

**Parameters:**

- **`callback`** `any`

**Returns:** `GLTFExporter`

**Calls:**

- `this.pluginCallbacks.indexOf`
- `this.pluginCallbacks.push`

<details><summary>Code</summary>

```typescript
register( callback ) {

		if ( this.pluginCallbacks.indexOf( callback ) === - 1 ) {

			this.pluginCallbacks.push( callback );

		}

		return this;

	}
```
</details>

### `GLTFExporter.unregister(callback: Function): GLTFExporter`

**JSDoc:**
```typescript
/**
	 * Unregisters a plugin callback.
	 *
	 * @param {Function} callback - The callback function to unregister.
	 * @return {GLTFExporter} A reference to this exporter.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `GLTFExporter`

**Calls:**

- `this.pluginCallbacks.indexOf`
- `this.pluginCallbacks.splice`

<details><summary>Code</summary>

```typescript
unregister( callback ) {

		if ( this.pluginCallbacks.indexOf( callback ) !== - 1 ) {

			this.pluginCallbacks.splice( this.pluginCallbacks.indexOf( callback ), 1 );

		}

		return this;

	}
```
</details>

### `GLTFExporter.setTextureUtils(utils: any): GLTFExporter`

**JSDoc:**
```typescript
/**
	 * Sets the texture utils for this exporter. Only relevant when compressed textures have to be exported.
	 *
	 * Depending on whether you use {@link WebGLRenderer} or {@link WebGPURenderer}, you must inject the
	 * corresponding texture utils {@link WebGLTextureUtils} or {@link WebGPUTextureUtils}.
	 *
	 * @param {WebGLTextureUtils|WebGPUTextureUtils} utils - The texture utils.
	 * @return {GLTFExporter} A reference to this exporter.
	 */
```

**Parameters:**

- **`utils`** `any`

**Returns:** `GLTFExporter`

<details><summary>Code</summary>

```typescript
setTextureUtils( utils ) {

		this.textureUtils = utils;

		return this;

	}
```
</details>

### `GLTFExporter.parse(input: any, onDone: any, onError: any, options: any): void`

**JSDoc:**
```typescript
/**
	 * Parses the given scenes and generates the glTF output.
	 *
	 * @param {Scene|Array<Scene>} input - A scene or an array of scenes.
	 * @param {GLTFExporter~OnDone} onDone - A callback function that is executed when the export has finished.
	 * @param {GLTFExporter~OnError} onError - A callback function that is executed when an error happens.
	 * @param {GLTFExporter~Options} options - options
	 */
```

**Parameters:**

- **`input`** `any`
- **`onDone`** `any`
- **`onError`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `plugins.push`
- `complex_call_6387`
- `writer.setPlugins`
- `writer.setTextureUtils`
- `writer.writeAsync( input, onDone, options ).catch`

<details><summary>Code</summary>

```typescript
parse( input, onDone, onError, options ) {

		const writer = new GLTFWriter();
		const plugins = [];

		for ( let i = 0, il = this.pluginCallbacks.length; i < il; i ++ ) {

			plugins.push( this.pluginCallbacks[ i ]( writer ) );

		}

		writer.setPlugins( plugins );
		writer.setTextureUtils( this.textureUtils );
		writer.writeAsync( input, onDone, options ).catch( onError );

	}
```
</details>

### `GLTFExporter.parseAsync(input: any, options: any): Promise<string | ArrayBuffer>`

**JSDoc:**
```typescript
/**
	 * Async version of {@link GLTFExporter#parse}.
	 *
	 * @param {Scene|Array<Scene>} input - A scene or an array of scenes.
	 * @param {GLTFExporter~Options} options - options.
	 * @return {Promise<ArrayBuffer|string>} A Promise that resolved with the exported glTF data.
	 */
```

**Parameters:**

- **`input`** `any`
- **`options`** `any`

**Returns:** `Promise<string | ArrayBuffer>`

**Calls:**

- `scope.parse`

<details><summary>Code</summary>

```typescript
parseAsync( input, options ) {

		const scope = this;

		return new Promise( function ( resolve, reject ) {

			scope.parse( input, resolve, reject, options );

		} );

	}
```
</details>

### `equalArray(array1: any[], array2: any[]): boolean`

**JSDoc:**
```typescript
/**
 * Compare two arrays
 *
 * @private
 * @param {Array} array1 Array 1 to compare
 * @param {Array} array2 Array 2 to compare
 * @return {boolean}        Returns true if both arrays are equal
 */
```

**Parameters:**

- **`array1`** `any[]`
- **`array2`** `any[]`

**Returns:** `boolean`

**Calls:**

- `array1.every`

<details><summary>Code</summary>

```typescript
function equalArray( array1, array2 ) {

	return ( array1.length === array2.length ) && array1.every( function ( element, index ) {

		return element === array2[ index ];

	} );

}
```
</details>

### `stringToArrayBuffer(text: string): ArrayBuffer`

**JSDoc:**
```typescript
/**
 * Converts a string to an ArrayBuffer.
 *
 * @private
 * @param {string} text
 * @return {ArrayBuffer}
 */
```

**Parameters:**

- **`text`** `string`

**Returns:** `ArrayBuffer`

**Calls:**

- `new TextEncoder().encode`

<details><summary>Code</summary>

```typescript
function stringToArrayBuffer( text ) {

	return new TextEncoder().encode( text ).buffer;

}
```
</details>

### `isIdentityMatrix(matrix: Matrix4): boolean`

**JSDoc:**
```typescript
/**
 * Is identity matrix
 *
 * @private
 * @param {Matrix4} matrix
 * @returns {boolean} Returns true, if parameter is identity matrix
 */
```

**Parameters:**

- **`matrix`** `Matrix4`

**Returns:** `boolean`

**Calls:**

- `equalArray`

<details><summary>Code</summary>

```typescript
function isIdentityMatrix( matrix ) {

	return equalArray( matrix.elements, [ 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1 ] );

}
```
</details>

### `getMinMax(attribute: BufferAttribute, start: number, count: number): any`

**JSDoc:**
```typescript
/**
 * Get the min and max vectors from the given attribute
 *
 * @private
 * @param {BufferAttribute} attribute Attribute to find the min/max in range from start to start + count
 * @param {number} start Start index
 * @param {number} count Range to cover
 * @return {Object} Object containing the `min` and `max` values (As an array of attribute.itemSize components)
 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`start`** `number`
- **`count`** `number`

**Returns:** `any`

**Calls:**

- `new Array( attribute.itemSize ).fill`
- `attribute.getX`
- `attribute.getY`
- `attribute.getZ`
- `attribute.getW`
- `MathUtils.normalize`
- `Math.min`
- `Math.max`

**Internal Comments:**
```
// no support for interleaved data for itemSize > 4 (x3)
```

<details><summary>Code</summary>

```typescript
function getMinMax( attribute, start, count ) {

	const output = {

		min: new Array( attribute.itemSize ).fill( Number.POSITIVE_INFINITY ),
		max: new Array( attribute.itemSize ).fill( Number.NEGATIVE_INFINITY )

	};

	for ( let i = start; i < start + count; i ++ ) {

		for ( let a = 0; a < attribute.itemSize; a ++ ) {

			let value;

			if ( attribute.itemSize > 4 ) {

				 // no support for interleaved data for itemSize > 4

				value = attribute.array[ i * attribute.itemSize + a ];

			} else {

				if ( a === 0 ) value = attribute.getX( i );
				else if ( a === 1 ) value = attribute.getY( i );
				else if ( a === 2 ) value = attribute.getZ( i );
				else if ( a === 3 ) value = attribute.getW( i );

				if ( attribute.normalized === true ) {

					value = MathUtils.normalize( value, attribute.array );

				}

			}

			output.min[ a ] = Math.min( output.min[ a ], value );
			output.max[ a ] = Math.max( output.max[ a ], value );

		}

	}

	return output;

}
```
</details>

### `getPaddedBufferSize(bufferSize: number): number`

**JSDoc:**
```typescript
/**
 * Get the required size + padding for a buffer, rounded to the next 4-byte boundary.
 * https://github.com/KhronosGroup/glTF/tree/master/specification/2.0#data-alignment
 *
 * @private
 * @param {number} bufferSize The size the original buffer. Should be an integer.
 * @returns {number} new buffer size with required padding as an integer.
 *
 */
```

**Parameters:**

- **`bufferSize`** `number`

**Returns:** `number`

**Calls:**

- `Math.ceil`

<details><summary>Code</summary>

```typescript
function getPaddedBufferSize( bufferSize ) {

	return Math.ceil( bufferSize / 4 ) * 4;

}
```
</details>

### `getPaddedArrayBuffer(arrayBuffer: ArrayBuffer, paddingByte: number): ArrayBuffer`

**JSDoc:**
```typescript
/**
 * Returns a buffer aligned to 4-byte boundary.
 *
 * @private
 * @param {ArrayBuffer} arrayBuffer Buffer to pad
 * @param {number} [paddingByte=0] Should be an integer
 * @returns {ArrayBuffer} The same buffer if it's already aligned to 4-byte boundary or a new buffer
 */
```

**Parameters:**

- **`arrayBuffer`** `ArrayBuffer`
- **`paddingByte`** `number`

**Returns:** `ArrayBuffer`

**Calls:**

- `getPaddedBufferSize`
- `array.set`

<details><summary>Code</summary>

```typescript
function getPaddedArrayBuffer( arrayBuffer, paddingByte = 0 ) {

	const paddedLength = getPaddedBufferSize( arrayBuffer.byteLength );

	if ( paddedLength !== arrayBuffer.byteLength ) {

		const array = new Uint8Array( paddedLength );
		array.set( new Uint8Array( arrayBuffer ) );

		if ( paddingByte !== 0 ) {

			for ( let i = arrayBuffer.byteLength; i < paddedLength; i ++ ) {

				array[ i ] = paddingByte;

			}

		}

		return array.buffer;

	}

	return arrayBuffer;

}
```
</details>

### `getCanvas(): HTMLCanvasElement | OffscreenCanvas`

**Returns:** `HTMLCanvasElement | OffscreenCanvas`

**Calls:**

- `document.createElement`

<details><summary>Code</summary>

```typescript
function getCanvas() {

	if ( typeof document === 'undefined' && typeof OffscreenCanvas !== 'undefined' ) {

		return new OffscreenCanvas( 1, 1 );

	}

	return document.createElement( 'canvas' );

}
```
</details>

### `getToBlobPromise(canvas: any, mimeType: any): any`

**Parameters:**

- **`canvas`** `any`
- **`mimeType`** `any`

**Returns:** `any`

**Calls:**

- `canvas.toBlob`
- `canvas.convertToBlob`

**Internal Comments:**
```
// Blink's implementation of convertToBlob seems to default to a quality level of 100%
// Use the Blink default quality levels of toBlob instead so that file sizes are comparable.
```

<details><summary>Code</summary>

```typescript
function getToBlobPromise( canvas, mimeType ) {

	if ( canvas.toBlob !== undefined ) {

		return new Promise( ( resolve ) => canvas.toBlob( resolve, mimeType ) );

	}

	let quality;

	// Blink's implementation of convertToBlob seems to default to a quality level of 100%
	// Use the Blink default quality levels of toBlob instead so that file sizes are comparable.
	if ( mimeType === 'image/jpeg' ) {

		quality = 0.92;

	} else if ( mimeType === 'image/webp' ) {

		quality = 0.8;

	}

	return canvas.convertToBlob( {

		type: mimeType,
		quality: quality

	} );

}
```
</details>

### `GLTFWriter.setPlugins(plugins: any): void`

**Parameters:**

- **`plugins`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setPlugins( plugins ) {

		this.plugins = plugins;

	}
```
</details>

### `GLTFWriter.setTextureUtils(utils: any): void`

**Parameters:**

- **`utils`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setTextureUtils( utils ) {

		this.textureUtils = utils;

	}
```
</details>

### `GLTFWriter.writeAsync(input: any, onDone: Function, options: any): Promise<void>`

**JSDoc:**
```typescript
/**
	 * Parse scenes and generate GLTF output
	 *
	 * @param {Scene|Array<Scene>} input Scene or Array of THREE.Scenes
	 * @param {Function} onDone Callback on completed
	 * @param {Object} options options
	 */
```

**Parameters:**

- **`input`** `any`
- **`onDone`** `Function`
- **`options`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `Object.assign`
- `this.processInputAsync`
- `Promise.all`
- `Object.keys`
- `reader.readAsArrayBuffer`
- `getPaddedArrayBuffer`
- `binaryChunkPrefix.setUint32`
- `stringToArrayBuffer`
- `JSON.stringify`
- `jsonChunkPrefix.setUint32`
- `headerView.setUint32`
- `glbReader.readAsArrayBuffer`
- `onDone`
- `reader.readAsDataURL`

**Internal Comments:**
```
// default options (x2)
// Only TRS properties, and not matrices, may be targeted by animation. (x5)
// Merge buffers. (x2)
// Declare extensions. (x2)
// Update bytelength of the single buffer.
// https://github.com/KhronosGroup/glTF/blob/master/specification/2.0/README.md#glb-file-format-specification (x2)
// Binary chunk. (x2)
// JSON chunk. (x2)
// GLB header. (x2)
```

<details><summary>Code</summary>

```typescript
async writeAsync( input, onDone, options = {} ) {

		this.options = Object.assign( {
			// default options
			binary: false,
			trs: false,
			onlyVisible: true,
			maxTextureSize: Infinity,
			animations: [],
			includeCustomExtensions: false
		}, options );

		if ( this.options.animations.length > 0 ) {

			// Only TRS properties, and not matrices, may be targeted by animation.
			this.options.trs = true;

		}

		await this.processInputAsync( input );

		await Promise.all( this.pending );

		const writer = this;
		const buffers = writer.buffers;
		const json = writer.json;
		options = writer.options;

		const extensionsUsed = writer.extensionsUsed;
		const extensionsRequired = writer.extensionsRequired;

		// Merge buffers.
		const blob = new Blob( buffers, { type: 'application/octet-stream' } );

		// Declare extensions.
		const extensionsUsedList = Object.keys( extensionsUsed );
		const extensionsRequiredList = Object.keys( extensionsRequired );

		if ( extensionsUsedList.length > 0 ) json.extensionsUsed = extensionsUsedList;
		if ( extensionsRequiredList.length > 0 ) json.extensionsRequired = extensionsRequiredList;

		// Update bytelength of the single buffer.
		if ( json.buffers && json.buffers.length > 0 ) json.buffers[ 0 ].byteLength = blob.size;

		if ( options.binary === true ) {

			// https://github.com/KhronosGroup/glTF/blob/master/specification/2.0/README.md#glb-file-format-specification

			const reader = new FileReader();
			reader.readAsArrayBuffer( blob );
			reader.onloadend = function () {

				// Binary chunk.
				const binaryChunk = getPaddedArrayBuffer( reader.result );
				const binaryChunkPrefix = new DataView( new ArrayBuffer( GLB_CHUNK_PREFIX_BYTES ) );
				binaryChunkPrefix.setUint32( 0, binaryChunk.byteLength, true );
				binaryChunkPrefix.setUint32( 4, GLB_CHUNK_TYPE_BIN, true );

				// JSON chunk.
				const jsonChunk = getPaddedArrayBuffer( stringToArrayBuffer( JSON.stringify( json ) ), 0x20 );
				const jsonChunkPrefix = new DataView( new ArrayBuffer( GLB_CHUNK_PREFIX_BYTES ) );
				jsonChunkPrefix.setUint32( 0, jsonChunk.byteLength, true );
				jsonChunkPrefix.setUint32( 4, GLB_CHUNK_TYPE_JSON, true );

				// GLB header.
				const header = new ArrayBuffer( GLB_HEADER_BYTES );
				const headerView = new DataView( header );
				headerView.setUint32( 0, GLB_HEADER_MAGIC, true );
				headerView.setUint32( 4, GLB_VERSION, true );
				const totalByteLength = GLB_HEADER_BYTES
					+ jsonChunkPrefix.byteLength + jsonChunk.byteLength
					+ binaryChunkPrefix.byteLength + binaryChunk.byteLength;
				headerView.setUint32( 8, totalByteLength, true );

				const glbBlob = new Blob( [
					header,
					jsonChunkPrefix,
					jsonChunk,
					binaryChunkPrefix,
					binaryChunk
				], { type: 'application/octet-stream' } );

				const glbReader = new FileReader();
				glbReader.readAsArrayBuffer( glbBlob );
				glbReader.onloadend = function () {

					onDone( glbReader.result );

				};

			};

		} else {

			if ( json.buffers && json.buffers.length > 0 ) {

				const reader = new FileReader();
				reader.readAsDataURL( blob );
				reader.onloadend = function () {

					const base64data = reader.result;
					json.buffers[ 0 ].uri = base64data;
					onDone( json );

				};

			} else {

				onDone( json );

			}

		}


	}
```
</details>

### `GLTFWriter.serializeUserData(object: any, objectDef: any): void`

**JSDoc:**
```typescript
/**
	 * Serializes a userData.
	 *
	 * @param {THREE.Object3D|THREE.Material} object
	 * @param {Object} objectDef
	 */
```

**Parameters:**

- **`object`** `any`
- **`objectDef`** `any`

**Returns:** `void`

**Calls:**

- `Object.keys`
- `JSON.parse`
- `JSON.stringify`
- `console.warn`

<details><summary>Code</summary>

```typescript
serializeUserData( object, objectDef ) {

		if ( Object.keys( object.userData ).length === 0 ) return;

		const options = this.options;
		const extensionsUsed = this.extensionsUsed;

		try {

			const json = JSON.parse( JSON.stringify( object.userData ) );

			if ( options.includeCustomExtensions && json.gltfExtensions ) {

				if ( objectDef.extensions === undefined ) objectDef.extensions = {};

				for ( const extensionName in json.gltfExtensions ) {

					objectDef.extensions[ extensionName ] = json.gltfExtensions[ extensionName ];
					extensionsUsed[ extensionName ] = true;

				}

				delete json.gltfExtensions;

			}

			if ( Object.keys( json ).length > 0 ) objectDef.extras = json;

		} catch ( error ) {

			console.warn( 'THREE.GLTFExporter: userData of \'' + object.name + '\' ' +
				'won\'t be serialized because of JSON.stringify error - ' + error.message );

		}

	}
```
</details>

### `GLTFWriter.getUID(attribute: any, isRelativeCopy: boolean): number`

**JSDoc:**
```typescript
/**
	 * Returns ids for buffer attributes.
	 *
	 * @param {Object} attribute
	 * @param {boolean} [isRelativeCopy=false]
	 * @return {number} An integer
	 */
```

**Parameters:**

- **`attribute`** `any`
- **`isRelativeCopy`** `boolean`

**Returns:** `number`

**Calls:**

- `this.uids.has`
- `uids.set`
- `this.uids.set`
- `this.uids.get`
- `uids.get`

<details><summary>Code</summary>

```typescript
getUID( attribute, isRelativeCopy = false ) {

		if ( this.uids.has( attribute ) === false ) {

			const uids = new Map();

			uids.set( true, this.uid ++ );
			uids.set( false, this.uid ++ );

			this.uids.set( attribute, uids );

		}

		const uids = this.uids.get( attribute );

		return uids.get( isRelativeCopy );

	}
```
</details>

### `GLTFWriter.isNormalizedNormalAttribute(normal: BufferAttribute): boolean`

**JSDoc:**
```typescript
/**
	 * Checks if normal attribute values are normalized.
	 *
	 * @param {BufferAttribute} normal
	 * @returns {boolean}
	 */
```

**Parameters:**

- **`normal`** `BufferAttribute`

**Returns:** `boolean`

**Calls:**

- `cache.attributesNormalized.has`
- `Math.abs`
- `v.fromBufferAttribute( normal, i ).length`

**Internal Comments:**
```
// 0.0005 is from glTF-validator
```

<details><summary>Code</summary>

```typescript
isNormalizedNormalAttribute( normal ) {

		const cache = this.cache;

		if ( cache.attributesNormalized.has( normal ) ) return false;

		const v = new Vector3();

		for ( let i = 0, il = normal.count; i < il; i ++ ) {

			// 0.0005 is from glTF-validator
			if ( Math.abs( v.fromBufferAttribute( normal, i ).length() - 1.0 ) > 0.0005 ) return false;

		}

		return true;

	}
```
</details>

### `GLTFWriter.createNormalizedNormalAttribute(normal: BufferAttribute): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Creates normalized normal buffer attribute.
	 *
	 * @param {BufferAttribute} normal
	 * @returns {BufferAttribute}
	 *
	 */
```

**Parameters:**

- **`normal`** `BufferAttribute`

**Returns:** `BufferAttribute`

**Calls:**

- `cache.attributesNormalized.has`
- `cache.attributesNormalized.get`
- `normal.clone`
- `v.fromBufferAttribute`
- `v.setX`
- `v.normalize`
- `attribute.setXYZ`
- `cache.attributesNormalized.set`

**Internal Comments:**
```
// if values can't be normalized set (1, 0, 0) (x4)
```

<details><summary>Code</summary>

```typescript
createNormalizedNormalAttribute( normal ) {

		const cache = this.cache;

		if ( cache.attributesNormalized.has( normal ) )	return cache.attributesNormalized.get( normal );

		const attribute = normal.clone();
		const v = new Vector3();

		for ( let i = 0, il = attribute.count; i < il; i ++ ) {

			v.fromBufferAttribute( attribute, i );

			if ( v.x === 0 && v.y === 0 && v.z === 0 ) {

				// if values can't be normalized set (1, 0, 0)
				v.setX( 1.0 );

			} else {

				v.normalize();

			}

			attribute.setXYZ( i, v.x, v.y, v.z );

		}

		cache.attributesNormalized.set( normal, attribute );

		return attribute;

	}
```
</details>

### `GLTFWriter.applyTextureTransform(mapDef: any, texture: THREE.Texture): void`

**JSDoc:**
```typescript
/**
	 * Applies a texture transform, if present, to the map definition. Requires
	 * the KHR_texture_transform extension.
	 *
	 * @param {Object} mapDef
	 * @param {THREE.Texture} texture
	 */
```

**Parameters:**

- **`mapDef`** `any`
- **`texture`** `THREE.Texture`

**Returns:** `void`

**Calls:**

- `texture.offset.toArray`
- `texture.repeat.toArray`

<details><summary>Code</summary>

```typescript
applyTextureTransform( mapDef, texture ) {

		let didTransform = false;
		const transformDef = {};

		if ( texture.offset.x !== 0 || texture.offset.y !== 0 ) {

			transformDef.offset = texture.offset.toArray();
			didTransform = true;

		}

		if ( texture.rotation !== 0 ) {

			transformDef.rotation = texture.rotation;
			didTransform = true;

		}

		if ( texture.repeat.x !== 1 || texture.repeat.y !== 1 ) {

			transformDef.scale = texture.repeat.toArray();
			didTransform = true;

		}

		if ( didTransform ) {

			mapDef.extensions = mapDef.extensions || {};
			mapDef.extensions[ 'KHR_texture_transform' ] = transformDef;
			this.extensionsUsed[ 'KHR_texture_transform' ] = true;

		}

	}
```
</details>

### `GLTFWriter.buildMetalRoughTextureAsync(metalnessMap: any, roughnessMap: any): Promise<any>`

**Parameters:**

- **`metalnessMap`** `any`
- **`roughnessMap`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `Math.pow`
- `this.decompressTextureAsync`
- `Math.max`
- `getCanvas`
- `canvas.getContext`
- `context.fillRect`
- `context.getImageData`
- `context.drawImage`
- `getEncodingConversion`
- `convert`
- `context.putImageData`
- `reference.clone`
- `console.warn`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
async buildMetalRoughTextureAsync( metalnessMap, roughnessMap ) {

		if ( metalnessMap === roughnessMap ) return metalnessMap;

		function getEncodingConversion( map ) {

			if ( map.colorSpace === SRGBColorSpace ) {

				return function SRGBToLinear( c ) {

					return ( c < 0.04045 ) ? c * 0.0773993808 : Math.pow( c * 0.9478672986 + 0.0521327014, 2.4 );

				};

			}

			return function LinearToLinear( c ) {

				return c;

			};

		}

		if ( metalnessMap instanceof CompressedTexture ) {

			metalnessMap = await this.decompressTextureAsync( metalnessMap );

		}

		if ( roughnessMap instanceof CompressedTexture ) {

			roughnessMap = await this.decompressTextureAsync( roughnessMap );

		}

		const metalness = metalnessMap ? metalnessMap.image : null;
		const roughness = roughnessMap ? roughnessMap.image : null;

		const width = Math.max( metalness ? metalness.width : 0, roughness ? roughness.width : 0 );
		const height = Math.max( metalness ? metalness.height : 0, roughness ? roughness.height : 0 );

		const canvas = getCanvas();
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d', {
			willReadFrequently: true,
		} );
		context.fillStyle = '#00ffff';
		context.fillRect( 0, 0, width, height );

		const composite = context.getImageData( 0, 0, width, height );

		if ( metalness ) {

			context.drawImage( metalness, 0, 0, width, height );

			const convert = getEncodingConversion( metalnessMap );
			const data = context.getImageData( 0, 0, width, height ).data;

			for ( let i = 2; i < data.length; i += 4 ) {

				composite.data[ i ] = convert( data[ i ] / 256 ) * 256;

			}

		}

		if ( roughness ) {

			context.drawImage( roughness, 0, 0, width, height );

			const convert = getEncodingConversion( roughnessMap );
			const data = context.getImageData( 0, 0, width, height ).data;

			for ( let i = 1; i < data.length; i += 4 ) {

				composite.data[ i ] = convert( data[ i ] / 256 ) * 256;

			}

		}

		context.putImageData( composite, 0, 0 );

		//

		const reference = metalnessMap || roughnessMap;

		const texture = reference.clone();

		texture.source = new Source( canvas );
		texture.colorSpace = NoColorSpace;
		texture.channel = ( metalnessMap || roughnessMap ).channel;

		if ( metalnessMap && roughnessMap && metalnessMap.channel !== roughnessMap.channel ) {

			console.warn( 'THREE.GLTFExporter: UV channels for metalnessMap and roughnessMap textures must match.' );

		}

		console.warn( 'THREE.GLTFExporter: Merged metalnessMap and roughnessMap textures.' );

		return texture;

	}
```
</details>

### `GLTFWriter.decompressTextureAsync(texture: any, maxTextureSize: number): Promise<any>`

**Parameters:**

- **`texture`** `any`
- **`maxTextureSize`** `number`

**Returns:** `Promise<any>`

**Calls:**

- `this.textureUtils.decompress`

<details><summary>Code</summary>

```typescript
async decompressTextureAsync( texture, maxTextureSize = Infinity ) {

		if ( this.textureUtils === null ) {

			throw new Error( 'THREE.GLTFExporter: setTextureUtils() must be called to process compressed textures.' );

		}

		return await this.textureUtils.decompress( texture, maxTextureSize );

	}
```
</details>

### `GLTFWriter.processBuffer(buffer: ArrayBuffer): 0`

**JSDoc:**
```typescript
/**
	 * Process a buffer to append to the default one.
	 * @param {ArrayBuffer} buffer
	 * @return {0}
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`

**Returns:** `0`

**Calls:**

- `buffers.push`

**Internal Comments:**
```
// All buffers are merged before export. (x4)
```

<details><summary>Code</summary>

```typescript
processBuffer( buffer ) {

		const json = this.json;
		const buffers = this.buffers;

		if ( ! json.buffers ) json.buffers = [ { byteLength: 0 } ];

		// All buffers are merged before export.
		buffers.push( buffer );

		return 0;

	}
```
</details>

### `GLTFWriter.processBufferView(attribute: BufferAttribute, componentType: number, start: number, count: number, target: number): any`

**JSDoc:**
```typescript
/**
	 * Process and generate a BufferView
	 * @param {BufferAttribute} attribute
	 * @param {number} componentType
	 * @param {number} start
	 * @param {number} count
	 * @param {number} [target] Target usage of the BufferView
	 * @return {Object}
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`componentType`** `number`
- **`start`** `number`
- **`count`** `number`
- **`target`** `number`

**Returns:** `any`

**Calls:**

- `Math.ceil`
- `getPaddedBufferSize`
- `attribute.getX`
- `attribute.getY`
- `attribute.getZ`
- `attribute.getW`
- `MathUtils.normalize`
- `dataView.setFloat32`
- `dataView.setInt32`
- `dataView.setUint32`
- `dataView.setInt16`
- `dataView.setUint16`
- `dataView.setInt8`
- `dataView.setUint8`
- `this.processBuffer`
- `json.bufferViews.push`

**Internal Comments:**
```
// Create a new dataview and dump the attribute's array into it (x2)
// Each element of a vertex attribute MUST be aligned to 4-byte boundaries (x3)
// inside a bufferView (x3)
// no support for interleaved data for itemSize > 4 (x3)
// Only define byteStride for vertex attributes. (x4)
// @TODO Merge bufferViews where possible. (x2)
```

<details><summary>Code</summary>

```typescript
processBufferView( attribute, componentType, start, count, target ) {

		const json = this.json;

		if ( ! json.bufferViews ) json.bufferViews = [];

		// Create a new dataview and dump the attribute's array into it

		let componentSize;

		switch ( componentType ) {

			case WEBGL_CONSTANTS.BYTE:
			case WEBGL_CONSTANTS.UNSIGNED_BYTE:

				componentSize = 1;

				break;

			case WEBGL_CONSTANTS.SHORT:
			case WEBGL_CONSTANTS.UNSIGNED_SHORT:

				componentSize = 2;

				break;

			default:

				componentSize = 4;

		}

		let byteStride = attribute.itemSize * componentSize;

		if ( target === WEBGL_CONSTANTS.ARRAY_BUFFER ) {

			// Each element of a vertex attribute MUST be aligned to 4-byte boundaries
			// inside a bufferView
			byteStride = Math.ceil( byteStride / 4 ) * 4;

		}

		const byteLength = getPaddedBufferSize( count * byteStride );
		const dataView = new DataView( new ArrayBuffer( byteLength ) );
		let offset = 0;

		for ( let i = start; i < start + count; i ++ ) {

			for ( let a = 0; a < attribute.itemSize; a ++ ) {

				let value;

				if ( attribute.itemSize > 4 ) {

					 // no support for interleaved data for itemSize > 4

					value = attribute.array[ i * attribute.itemSize + a ];

				} else {

					if ( a === 0 ) value = attribute.getX( i );
					else if ( a === 1 ) value = attribute.getY( i );
					else if ( a === 2 ) value = attribute.getZ( i );
					else if ( a === 3 ) value = attribute.getW( i );

					if ( attribute.normalized === true ) {

						value = MathUtils.normalize( value, attribute.array );

					}

				}

				if ( componentType === WEBGL_CONSTANTS.FLOAT ) {

					dataView.setFloat32( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.INT ) {

					dataView.setInt32( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.UNSIGNED_INT ) {

					dataView.setUint32( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.SHORT ) {

					dataView.setInt16( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.UNSIGNED_SHORT ) {

					dataView.setUint16( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.BYTE ) {

					dataView.setInt8( offset, value );

				} else if ( componentType === WEBGL_CONSTANTS.UNSIGNED_BYTE ) {

					dataView.setUint8( offset, value );

				}

				offset += componentSize;

			}

			if ( ( offset % byteStride ) !== 0 ) {

				offset += byteStride - ( offset % byteStride );

			}

		}

		const bufferViewDef = {

			buffer: this.processBuffer( dataView.buffer ),
			byteOffset: this.byteOffset,
			byteLength: byteLength

		};

		if ( target !== undefined ) bufferViewDef.target = target;

		if ( target === WEBGL_CONSTANTS.ARRAY_BUFFER ) {

			// Only define byteStride for vertex attributes.
			bufferViewDef.byteStride = byteStride;

		}

		this.byteOffset += byteLength;

		json.bufferViews.push( bufferViewDef );

		// @TODO Merge bufferViews where possible.
		const output = {

			id: json.bufferViews.length - 1,
			byteLength: 0

		};

		return output;

	}
```
</details>

### `GLTFWriter.processBufferViewImage(blob: Blob): Promise<number>`

**JSDoc:**
```typescript
/**
	 * Process and generate a BufferView from an image Blob.
	 * @param {Blob} blob
	 * @return {Promise<number>} An integer
	 */
```

**Parameters:**

- **`blob`** `Blob`

**Returns:** `Promise<number>`

**Calls:**

- `reader.readAsArrayBuffer`
- `getPaddedArrayBuffer`
- `writer.processBuffer`
- `resolve`
- `json.bufferViews.push`

<details><summary>Code</summary>

```typescript
processBufferViewImage( blob ) {

		const writer = this;
		const json = writer.json;

		if ( ! json.bufferViews ) json.bufferViews = [];

		return new Promise( function ( resolve ) {

			const reader = new FileReader();
			reader.readAsArrayBuffer( blob );
			reader.onloadend = function () {

				const buffer = getPaddedArrayBuffer( reader.result );

				const bufferViewDef = {
					buffer: writer.processBuffer( buffer ),
					byteOffset: writer.byteOffset,
					byteLength: buffer.byteLength
				};

				writer.byteOffset += buffer.byteLength;
				resolve( json.bufferViews.push( bufferViewDef ) - 1 );

			};

		} );

	}
```
</details>

### `GLTFWriter.processAccessor(attribute: BufferAttribute, geometry: BufferGeometry, start: number, count: number): number`

**JSDoc:**
```typescript
/**
	 * Process attribute to generate an accessor
	 * @param {BufferAttribute} attribute Attribute to process
	 * @param {?BufferGeometry} [geometry] Geometry used for truncated draw range
	 * @param {number} [start=0]
	 * @param {number} [count=Infinity]
	 * @return {?number} Index of the processed accessor on the "accessors" array
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`geometry`** `BufferGeometry`
- **`start`** `number`
- **`count`** `number`

**Returns:** `number`

**Calls:**

- `getMinMax`
- `this.processBufferView`
- `json.accessors.push`

**Internal Comments:**
```
// Detect the component type of the attribute array
// Skip creating an accessor if the attribute doesn't have data to export
// If geometry isn't provided, don't infer the target usage of the bufferView. For
// animation samplers, target must not be set.
```

<details><summary>Code</summary>

```typescript
processAccessor( attribute, geometry, start, count ) {

		const json = this.json;

		const types = {

			1: 'SCALAR',
			2: 'VEC2',
			3: 'VEC3',
			4: 'VEC4',
			9: 'MAT3',
			16: 'MAT4'

		};

		let componentType;

		// Detect the component type of the attribute array
		if ( attribute.array.constructor === Float32Array ) {

			componentType = WEBGL_CONSTANTS.FLOAT;

		} else if ( attribute.array.constructor === Int32Array ) {

			componentType = WEBGL_CONSTANTS.INT;

		} else if ( attribute.array.constructor === Uint32Array ) {

			componentType = WEBGL_CONSTANTS.UNSIGNED_INT;

		} else if ( attribute.array.constructor === Int16Array ) {

			componentType = WEBGL_CONSTANTS.SHORT;

		} else if ( attribute.array.constructor === Uint16Array ) {

			componentType = WEBGL_CONSTANTS.UNSIGNED_SHORT;

		} else if ( attribute.array.constructor === Int8Array ) {

			componentType = WEBGL_CONSTANTS.BYTE;

		} else if ( attribute.array.constructor === Uint8Array ) {

			componentType = WEBGL_CONSTANTS.UNSIGNED_BYTE;

		} else {

			throw new Error( 'THREE.GLTFExporter: Unsupported bufferAttribute component type: ' + attribute.array.constructor.name );

		}

		if ( start === undefined ) start = 0;
		if ( count === undefined || count === Infinity ) count = attribute.count;

		// Skip creating an accessor if the attribute doesn't have data to export
		if ( count === 0 ) return null;

		const minMax = getMinMax( attribute, start, count );
		let bufferViewTarget;

		// If geometry isn't provided, don't infer the target usage of the bufferView. For
		// animation samplers, target must not be set.
		if ( geometry !== undefined ) {

			bufferViewTarget = attribute === geometry.index ? WEBGL_CONSTANTS.ELEMENT_ARRAY_BUFFER : WEBGL_CONSTANTS.ARRAY_BUFFER;

		}

		const bufferView = this.processBufferView( attribute, componentType, start, count, bufferViewTarget );

		const accessorDef = {

			bufferView: bufferView.id,
			byteOffset: bufferView.byteOffset,
			componentType: componentType,
			count: count,
			max: minMax.max,
			min: minMax.min,
			type: types[ attribute.itemSize ]

		};

		if ( attribute.normalized === true ) accessorDef.normalized = true;
		if ( ! json.accessors ) json.accessors = [];

		return json.accessors.push( accessorDef ) - 1;

	}
```
</details>

### `GLTFWriter.processImage(image: new (width?: number, height?: number) => HTMLImageElement, format: number, flipY: boolean, mimeType: string): number`

**JSDoc:**
```typescript
/**
	 * Process image
	 * @param {Image} image to process
	 * @param {number} format Identifier of the format (RGBAFormat)
	 * @param {boolean} flipY before writing out the image
	 * @param {string} mimeType export format
	 * @return {number}     Index of the processed texture in the "images" array
	 */
```

**Parameters:**

- **`image`** `new (width?: number, height?: number) => HTMLImageElement`
- **`format`** `number`
- **`flipY`** `boolean`
- **`mimeType`** `string`

**Returns:** `number`

**Calls:**

- `cache.images.has`
- `cache.images.set`
- `cache.images.get`
- `flipY.toString`
- `getCanvas`
- `Math.min`
- `canvas.getContext`
- `ctx.translate`
- `ctx.scale`
- `console.error`
- `console.warn`
- `ctx.putImageData`
- `ctx.drawImage`
- `pending.push`
- `getToBlobPromise( canvas, mimeType )
						.then( blob => writer.processBufferViewImage( blob ) )
						.then`
- `ImageUtils.getDataURL`
- `json.images.push`

<details><summary>Code</summary>

```typescript
processImage( image, format, flipY, mimeType = 'image/png' ) {

		if ( image !== null ) {

			const writer = this;
			const cache = writer.cache;
			const json = writer.json;
			const options = writer.options;
			const pending = writer.pending;

			if ( ! cache.images.has( image ) ) cache.images.set( image, {} );

			const cachedImages = cache.images.get( image );

			const key = mimeType + ':flipY/' + flipY.toString();

			if ( cachedImages[ key ] !== undefined ) return cachedImages[ key ];

			if ( ! json.images ) json.images = [];

			const imageDef = { mimeType: mimeType };

			const canvas = getCanvas();

			canvas.width = Math.min( image.width, options.maxTextureSize );
			canvas.height = Math.min( image.height, options.maxTextureSize );

			const ctx = canvas.getContext( '2d', {
				willReadFrequently: true,
			} );

			if ( flipY === true ) {

				ctx.translate( 0, canvas.height );
				ctx.scale( 1, - 1 );

			}

			if ( image.data !== undefined ) { // THREE.DataTexture

				if ( format !== RGBAFormat ) {

					console.error( 'GLTFExporter: Only RGBAFormat is supported.', format );

				}

				if ( image.width > options.maxTextureSize || image.height > options.maxTextureSize ) {

					console.warn( 'GLTFExporter: Image size is bigger than maxTextureSize', image );

				}

				const data = new Uint8ClampedArray( image.height * image.width * 4 );

				for ( let i = 0; i < data.length; i += 4 ) {

					data[ i + 0 ] = image.data[ i + 0 ];
					data[ i + 1 ] = image.data[ i + 1 ];
					data[ i + 2 ] = image.data[ i + 2 ];
					data[ i + 3 ] = image.data[ i + 3 ];

				}

				ctx.putImageData( new ImageData( data, image.width, image.height ), 0, 0 );

			} else {

				if ( ( typeof HTMLImageElement !== 'undefined' && image instanceof HTMLImageElement ) ||
					( typeof HTMLCanvasElement !== 'undefined' && image instanceof HTMLCanvasElement ) ||
					( typeof ImageBitmap !== 'undefined' && image instanceof ImageBitmap ) ||
					( typeof OffscreenCanvas !== 'undefined' && image instanceof OffscreenCanvas ) ) {

					ctx.drawImage( image, 0, 0, canvas.width, canvas.height );

				} else {

					throw new Error( 'THREE.GLTFExporter: Invalid image type. Use HTMLImageElement, HTMLCanvasElement, ImageBitmap or OffscreenCanvas.' );

				}

			}

			if ( options.binary === true ) {

				pending.push(

					getToBlobPromise( canvas, mimeType )
						.then( blob => writer.processBufferViewImage( blob ) )
						.then( bufferViewIndex => {

							imageDef.bufferView = bufferViewIndex;

						} )

				);

			} else {

				imageDef.uri = ImageUtils.getDataURL( canvas, mimeType );

			}

			const index = json.images.push( imageDef ) - 1;
			cachedImages[ key ] = index;
			return index;

		} else {

			throw new Error( 'THREE.GLTFExporter: No valid image data found. Unable to process texture.' );

		}

	}
```
</details>

### `GLTFWriter.processSampler(map: Texture): number`

**JSDoc:**
```typescript
/**
	 * Process sampler
	 * @param {Texture} map Texture to process
	 * @return {number}      Index of the processed texture in the "samplers" array
	 */
```

**Parameters:**

- **`map`** `Texture`

**Returns:** `number`

**Calls:**

- `json.samplers.push`

<details><summary>Code</summary>

```typescript
processSampler( map ) {

		const json = this.json;

		if ( ! json.samplers ) json.samplers = [];

		const samplerDef = {
			magFilter: THREE_TO_WEBGL[ map.magFilter ],
			minFilter: THREE_TO_WEBGL[ map.minFilter ],
			wrapS: THREE_TO_WEBGL[ map.wrapS ],
			wrapT: THREE_TO_WEBGL[ map.wrapT ]
		};

		return json.samplers.push( samplerDef ) - 1;

	}
```
</details>

### `GLTFWriter.processTextureAsync(map: Texture): Promise<number>`

**JSDoc:**
```typescript
/**
	 * Process texture
	 * @param {Texture} map Map to process
	 * @return {Promise<number>} Index of the processed texture in the "textures" array
	 */
```

**Parameters:**

- **`map`** `Texture`

**Returns:** `Promise<number>`

**Calls:**

- `cache.textures.has`
- `cache.textures.get`
- `this.decompressTextureAsync`
- `this.processSampler`
- `this.processImage`
- `this._invokeAllAsync`
- `ext.writeTexture`
- `json.textures.push`
- `cache.textures.set`

**Internal Comments:**
```
// make non-readable textures (e.g. CompressedTexture) readable by blitting them into a new texture
```

<details><summary>Code</summary>

```typescript
async processTextureAsync( map ) {

		const writer = this;
		const options = writer.options;
		const cache = this.cache;
		const json = this.json;

		if ( cache.textures.has( map ) ) return cache.textures.get( map );

		if ( ! json.textures ) json.textures = [];

		// make non-readable textures (e.g. CompressedTexture) readable by blitting them into a new texture
		if ( map instanceof CompressedTexture ) {

			map = await this.decompressTextureAsync( map, options.maxTextureSize );

		}

		let mimeType = map.userData.mimeType;

		if ( mimeType === 'image/webp' ) mimeType = 'image/png';

		const textureDef = {
			sampler: this.processSampler( map ),
			source: this.processImage( map.image, map.format, map.flipY, mimeType )
		};

		if ( map.name ) textureDef.name = map.name;

		await this._invokeAllAsync( async function ( ext ) {

			ext.writeTexture && await ext.writeTexture( map, textureDef );

		} );

		const index = json.textures.push( textureDef ) - 1;
		cache.textures.set( map, index );
		return index;

	}
```
</details>

### `GLTFWriter.processMaterialAsync(material: THREE.Material): Promise<number>`

**JSDoc:**
```typescript
/**
	 * Process material
	 * @param {THREE.Material} material Material to process
	 * @return {Promise<number|null>} Index of the processed material in the "materials" array
	 */
```

**Parameters:**

- **`material`** `THREE.Material`

**Returns:** `Promise<number>`

**Calls:**

- `cache.materials.has`
- `cache.materials.get`
- `console.warn`
- `material.color.toArray().concat`
- `equalArray`
- `this.buildMetalRoughTextureAsync`
- `this.processTextureAsync`
- `this.applyTextureTransform`
- `Math.max`
- `material.emissive.toArray`
- `this.serializeUserData`
- `this._invokeAllAsync`
- `ext.writeMaterialAsync`
- `json.materials.push`
- `cache.materials.set`

**Internal Comments:**
```
// @QUESTION Should we avoid including any attribute that has the default value? (x2)
// pbrMetallicRoughness.baseColorFactor (x2)
// pbrMetallicRoughness.metallicRoughnessTexture
// pbrMetallicRoughness.baseColorTexture
// emissiveTexture
// normalTexture
// glTF normal scale is univariate. Ignore `y`, which may be flipped. (x4)
// Context: https://github.com/mrdoob/three.js/issues/11438#issuecomment-507003995 (x4)
// occlusionTexture
// alphaMode
// doubleSided
```

<details><summary>Code</summary>

```typescript
async processMaterialAsync( material ) {

		const cache = this.cache;
		const json = this.json;

		if ( cache.materials.has( material ) ) return cache.materials.get( material );

		if ( material.isShaderMaterial ) {

			console.warn( 'GLTFExporter: THREE.ShaderMaterial not supported.' );
			return null;

		}

		if ( ! json.materials ) json.materials = [];

		// @QUESTION Should we avoid including any attribute that has the default value?
		const materialDef = {	pbrMetallicRoughness: {} };

		if ( material.isMeshStandardMaterial !== true && material.isMeshBasicMaterial !== true ) {

			console.warn( 'GLTFExporter: Use MeshStandardMaterial or MeshBasicMaterial for best results.' );

		}

		// pbrMetallicRoughness.baseColorFactor
		const color = material.color.toArray().concat( [ material.opacity ] );

		if ( ! equalArray( color, [ 1, 1, 1, 1 ] ) ) {

			materialDef.pbrMetallicRoughness.baseColorFactor = color;

		}

		if ( material.isMeshStandardMaterial ) {

			materialDef.pbrMetallicRoughness.metallicFactor = material.metalness;
			materialDef.pbrMetallicRoughness.roughnessFactor = material.roughness;

		} else {

			materialDef.pbrMetallicRoughness.metallicFactor = 0;
			materialDef.pbrMetallicRoughness.roughnessFactor = 1;

		}

		// pbrMetallicRoughness.metallicRoughnessTexture
		if ( material.metalnessMap || material.roughnessMap ) {

			const metalRoughTexture = await this.buildMetalRoughTextureAsync( material.metalnessMap, material.roughnessMap );

			const metalRoughMapDef = {
				index: await this.processTextureAsync( metalRoughTexture ),
				texCoord: metalRoughTexture.channel
			};
			this.applyTextureTransform( metalRoughMapDef, metalRoughTexture );
			materialDef.pbrMetallicRoughness.metallicRoughnessTexture = metalRoughMapDef;

		}

		// pbrMetallicRoughness.baseColorTexture
		if ( material.map ) {

			const baseColorMapDef = {
				index: await this.processTextureAsync( material.map ),
				texCoord: material.map.channel
			};
			this.applyTextureTransform( baseColorMapDef, material.map );
			materialDef.pbrMetallicRoughness.baseColorTexture = baseColorMapDef;

		}

		if ( material.emissive ) {

			const emissive = material.emissive;
			const maxEmissiveComponent = Math.max( emissive.r, emissive.g, emissive.b );

			if ( maxEmissiveComponent > 0 ) {

				materialDef.emissiveFactor = material.emissive.toArray();

			}

			// emissiveTexture
			if ( material.emissiveMap ) {

				const emissiveMapDef = {
					index: await this.processTextureAsync( material.emissiveMap ),
					texCoord: material.emissiveMap.channel
				};
				this.applyTextureTransform( emissiveMapDef, material.emissiveMap );
				materialDef.emissiveTexture = emissiveMapDef;

			}

		}

		// normalTexture
		if ( material.normalMap ) {

			const normalMapDef = {
				index: await this.processTextureAsync( material.normalMap ),
				texCoord: material.normalMap.channel
			};

			if ( material.normalScale && material.normalScale.x !== 1 ) {

				// glTF normal scale is univariate. Ignore `y`, which may be flipped.
				// Context: https://github.com/mrdoob/three.js/issues/11438#issuecomment-507003995
				normalMapDef.scale = material.normalScale.x;

			}

			this.applyTextureTransform( normalMapDef, material.normalMap );
			materialDef.normalTexture = normalMapDef;

		}

		// occlusionTexture
		if ( material.aoMap ) {

			const occlusionMapDef = {
				index: await this.processTextureAsync( material.aoMap ),
				texCoord: material.aoMap.channel
			};

			if ( material.aoMapIntensity !== 1.0 ) {

				occlusionMapDef.strength = material.aoMapIntensity;

			}

			this.applyTextureTransform( occlusionMapDef, material.aoMap );
			materialDef.occlusionTexture = occlusionMapDef;

		}

		// alphaMode
		if ( material.transparent ) {

			materialDef.alphaMode = 'BLEND';

		} else {

			if ( material.alphaTest > 0.0 ) {

				materialDef.alphaMode = 'MASK';
				materialDef.alphaCutoff = material.alphaTest;

			}

		}

		// doubleSided
		if ( material.side === DoubleSide ) materialDef.doubleSided = true;
		if ( material.name !== '' ) materialDef.name = material.name;

		this.serializeUserData( material, materialDef );

		await this._invokeAllAsync( async function ( ext ) {

			ext.writeMaterialAsync && await ext.writeMaterialAsync( material, materialDef );

		} );

		const index = json.materials.push( materialDef ) - 1;
		cache.materials.set( material, index );
		return index;

	}
```
</details>

### `GLTFWriter.processMeshAsync(mesh: THREE.Mesh): Promise<number>`

**JSDoc:**
```typescript
/**
	 * Process mesh
	 * @param {THREE.Mesh} mesh Mesh to process
	 * @return {Promise<number|null>} Index of the processed mesh in the "meshes" array
	 */
```

**Parameters:**

- **`mesh`** `THREE.Mesh`

**Returns:** `Promise<number>`

**Calls:**

- `Array.isArray`
- `meshCacheKeyParts.push`
- `meshCacheKeyParts.join`
- `cache.meshes.has`
- `cache.meshes.get`
- `geometry.getAttribute`
- `this.isNormalizedNormalAttribute`
- `console.warn`
- `geometry.setAttribute`
- `this.createNormalizedNormalAttribute`
- `attributeName.slice`
- `attributeName.toUpperCase`
- `validVertexAttributes.test`
- `cache.attributes.has`
- `this.getUID`
- `cache.attributes.get`
- `attributeName.startsWith`
- `GLTFExporter.Utils.toFloat32BufferAttribute`
- `this.processAccessor`
- `this.detectMeshQuantization`
- `cache.attributes.set`
- `Object.keys`
- `attribute.clone`
- `relativeAttribute.setX`
- `attribute.getX`
- `baseAttribute.getX`
- `relativeAttribute.setY`
- `attribute.getY`
- `baseAttribute.getY`
- `relativeAttribute.setZ`
- `attribute.getZ`
- `baseAttribute.getZ`
- `relativeAttribute.setW`
- `attribute.getW`
- `baseAttribute.getW`
- `targets.push`
- `weights.push`
- `targetNames.push`
- `geometry.setIndex`
- `this.serializeUserData`
- `this.processMaterialAsync`
- `primitives.push`
- `this._invokeAllAsync`
- `ext.writeMesh`
- `json.meshes.push`
- `cache.meshes.set`

**Internal Comments:**
```
// Use the correct mode
// Conversion between attributes names in threejs and gltf spec (x2)
// @QUESTION Detect if .vertexColors = true? (x2)
// For every attribute create an accessor (x2)
// Ignore morph target attributes, which are exported later.
// Prefix all geometry attributes except the ones specifically (x2)
// listed in the spec; non-spec attributes are considered custom. (x2)
// Enforce glTF vertex attribute requirements: (x3)
// - JOINTS_0 must be UNSIGNED_BYTE or UNSIGNED_SHORT (x3)
// - Only custom attributes may be INT or UNSIGNED_INT (x3)
// Skip if no exportable attributes found
// Morph targets
// glTF 2.0 morph supports only POSITION/NORMAL/TANGENT.
// Three.js doesn't support TANGENT yet.
// Three.js morph attribute has absolute values while the one of glTF has relative values. (x2)
// (x2)
// glTF 2.0 Specification: (x2)
// https://github.com/KhronosGroup/glTF/tree/master/specification/2.0#morph-targets (x2)
// Clones attribute not to override (x2)
```

<details><summary>Code</summary>

```typescript
async processMeshAsync( mesh ) {

		const cache = this.cache;
		const json = this.json;

		const meshCacheKeyParts = [ mesh.geometry.uuid ];

		if ( Array.isArray( mesh.material ) ) {

			for ( let i = 0, l = mesh.material.length; i < l; i ++ ) {

				meshCacheKeyParts.push( mesh.material[ i ].uuid	);

			}

		} else {

			meshCacheKeyParts.push( mesh.material.uuid );

		}

		const meshCacheKey = meshCacheKeyParts.join( ':' );

		if ( cache.meshes.has( meshCacheKey ) ) return cache.meshes.get( meshCacheKey );

		const geometry = mesh.geometry;

		let mode;

		// Use the correct mode
		if ( mesh.isLineSegments ) {

			mode = WEBGL_CONSTANTS.LINES;

		} else if ( mesh.isLineLoop ) {

			mode = WEBGL_CONSTANTS.LINE_LOOP;

		} else if ( mesh.isLine ) {

			mode = WEBGL_CONSTANTS.LINE_STRIP;

		} else if ( mesh.isPoints ) {

			mode = WEBGL_CONSTANTS.POINTS;

		} else {

			mode = mesh.material.wireframe ? WEBGL_CONSTANTS.LINES : WEBGL_CONSTANTS.TRIANGLES;

		}

		const meshDef = {};
		const attributes = {};
		const primitives = [];
		const targets = [];

		// Conversion between attributes names in threejs and gltf spec
		const nameConversion = {
			uv: 'TEXCOORD_0',
			uv1: 'TEXCOORD_1',
			uv2: 'TEXCOORD_2',
			uv3: 'TEXCOORD_3',
			color: 'COLOR_0',
			skinWeight: 'WEIGHTS_0',
			skinIndex: 'JOINTS_0'
		};

		const originalNormal = geometry.getAttribute( 'normal' );

		if ( originalNormal !== undefined && ! this.isNormalizedNormalAttribute( originalNormal ) ) {

			console.warn( 'THREE.GLTFExporter: Creating normalized normal attribute from the non-normalized one.' );

			geometry.setAttribute( 'normal', this.createNormalizedNormalAttribute( originalNormal ) );

		}

		// @QUESTION Detect if .vertexColors = true?
		// For every attribute create an accessor
		let modifiedAttribute = null;

		for ( let attributeName in geometry.attributes ) {

			// Ignore morph target attributes, which are exported later.
			if ( attributeName.slice( 0, 5 ) === 'morph' ) continue;

			const attribute = geometry.attributes[ attributeName ];
			attributeName = nameConversion[ attributeName ] || attributeName.toUpperCase();

			// Prefix all geometry attributes except the ones specifically
			// listed in the spec; non-spec attributes are considered custom.
			const validVertexAttributes =
					/^(POSITION|NORMAL|TANGENT|TEXCOORD_\d+|COLOR_\d+|JOINTS_\d+|WEIGHTS_\d+)$/;

			if ( ! validVertexAttributes.test( attributeName ) ) attributeName = '_' + attributeName;

			if ( cache.attributes.has( this.getUID( attribute ) ) ) {

				attributes[ attributeName ] = cache.attributes.get( this.getUID( attribute ) );
				continue;

			}

			// Enforce glTF vertex attribute requirements:
			// - JOINTS_0 must be UNSIGNED_BYTE or UNSIGNED_SHORT
			// - Only custom attributes may be INT or UNSIGNED_INT
			modifiedAttribute = null;
			const array = attribute.array;

			if ( attributeName === 'JOINTS_0' &&
				! ( array instanceof Uint16Array ) &&
				! ( array instanceof Uint8Array ) ) {

				console.warn( 'GLTFExporter: Attribute "skinIndex" converted to type UNSIGNED_SHORT.' );
				modifiedAttribute = new BufferAttribute( new Uint16Array( array ), attribute.itemSize, attribute.normalized );

			} else if ( ( array instanceof Uint32Array || array instanceof Int32Array ) && ! attributeName.startsWith( '_' ) ) {

				console.warn( `GLTFExporter: Attribute "${ attributeName }" converted to type FLOAT.` );
				modifiedAttribute = GLTFExporter.Utils.toFloat32BufferAttribute( attribute );

			}

			const accessor = this.processAccessor( modifiedAttribute || attribute, geometry );

			if ( accessor !== null ) {

				if ( ! attributeName.startsWith( '_' ) ) {

					this.detectMeshQuantization( attributeName, attribute );

				}

				attributes[ attributeName ] = accessor;
				cache.attributes.set( this.getUID( attribute ), accessor );

			}

		}

		if ( originalNormal !== undefined ) geometry.setAttribute( 'normal', originalNormal );

		// Skip if no exportable attributes found
		if ( Object.keys( attributes ).length === 0 ) return null;

		// Morph targets
		if ( mesh.morphTargetInfluences !== undefined && mesh.morphTargetInfluences.length > 0 ) {

			const weights = [];
			const targetNames = [];
			const reverseDictionary = {};

			if ( mesh.morphTargetDictionary !== undefined ) {

				for ( const key in mesh.morphTargetDictionary ) {

					reverseDictionary[ mesh.morphTargetDictionary[ key ] ] = key;

				}

			}

			for ( let i = 0; i < mesh.morphTargetInfluences.length; ++ i ) {

				const target = {};
				let warned = false;

				for ( const attributeName in geometry.morphAttributes ) {

					// glTF 2.0 morph supports only POSITION/NORMAL/TANGENT.
					// Three.js doesn't support TANGENT yet.

					if ( attributeName !== 'position' && attributeName !== 'normal' ) {

						if ( ! warned ) {

							console.warn( 'GLTFExporter: Only POSITION and NORMAL morph are supported.' );
							warned = true;

						}

						continue;

					}

					const attribute = geometry.morphAttributes[ attributeName ][ i ];
					const gltfAttributeName = attributeName.toUpperCase();

					// Three.js morph attribute has absolute values while the one of glTF has relative values.
					//
					// glTF 2.0 Specification:
					// https://github.com/KhronosGroup/glTF/tree/master/specification/2.0#morph-targets

					const baseAttribute = geometry.attributes[ attributeName ];

					if ( cache.attributes.has( this.getUID( attribute, true ) ) ) {

						target[ gltfAttributeName ] = cache.attributes.get( this.getUID( attribute, true ) );
						continue;

					}

					// Clones attribute not to override
					const relativeAttribute = attribute.clone();

					if ( ! geometry.morphTargetsRelative ) {

						for ( let j = 0, jl = attribute.count; j < jl; j ++ ) {

							for ( let a = 0; a < attribute.itemSize; a ++ ) {

								if ( a === 0 ) relativeAttribute.setX( j, attribute.getX( j ) - baseAttribute.getX( j ) );
								if ( a === 1 ) relativeAttribute.setY( j, attribute.getY( j ) - baseAttribute.getY( j ) );
								if ( a === 2 ) relativeAttribute.setZ( j, attribute.getZ( j ) - baseAttribute.getZ( j ) );
								if ( a === 3 ) relativeAttribute.setW( j, attribute.getW( j ) - baseAttribute.getW( j ) );

							}

						}

					}

					target[ gltfAttributeName ] = this.processAccessor( relativeAttribute, geometry );
					cache.attributes.set( this.getUID( baseAttribute, true ), target[ gltfAttributeName ] );

				}

				targets.push( target );

				weights.push( mesh.morphTargetInfluences[ i ] );

				if ( mesh.morphTargetDictionary !== undefined ) targetNames.push( reverseDictionary[ i ] );

			}

			meshDef.weights = weights;

			if ( targetNames.length > 0 ) {

				meshDef.extras = {};
				meshDef.extras.targetNames = targetNames;

			}

		}

		const isMultiMaterial = Array.isArray( mesh.material );

		if ( isMultiMaterial && geometry.groups.length === 0 ) return null;

		let didForceIndices = false;

		if ( isMultiMaterial && geometry.index === null ) {

			const indices = [];

			for ( let i = 0, il = geometry.attributes.position.count; i < il; i ++ ) {

				indices[ i ] = i;

			}

			geometry.setIndex( indices );

			didForceIndices = true;

		}

		const materials = isMultiMaterial ? mesh.material : [ mesh.material ];
		const groups = isMultiMaterial ? geometry.groups : [ { materialIndex: 0, start: undefined, count: undefined } ];

		for ( let i = 0, il = groups.length; i < il; i ++ ) {

			const primitive = {
				mode: mode,
				attributes: attributes,
			};

			this.serializeUserData( geometry, primitive );

			if ( targets.length > 0 ) primitive.targets = targets;

			if ( geometry.index !== null ) {

				let cacheKey = this.getUID( geometry.index );

				if ( groups[ i ].start !== undefined || groups[ i ].count !== undefined ) {

					cacheKey += ':' + groups[ i ].start + ':' + groups[ i ].count;

				}

				if ( cache.attributes.has( cacheKey ) ) {

					primitive.indices = cache.attributes.get( cacheKey );

				} else {

					primitive.indices = this.processAccessor( geometry.index, geometry, groups[ i ].start, groups[ i ].count );
					cache.attributes.set( cacheKey, primitive.indices );

				}

				if ( primitive.indices === null ) delete primitive.indices;

			}

			const material = await this.processMaterialAsync( materials[ groups[ i ].materialIndex ] );

			if ( material !== null ) primitive.material = material;

			primitives.push( primitive );

		}

		if ( didForceIndices === true ) {

			geometry.setIndex( null );

		}

		meshDef.primitives = primitives;

		if ( ! json.meshes ) json.meshes = [];

		await this._invokeAllAsync( function ( ext ) {

			ext.writeMesh && ext.writeMesh( mesh, meshDef );

		} );

		const index = json.meshes.push( meshDef ) - 1;
		cache.meshes.set( meshCacheKey, index );
		return index;

	}
```
</details>

### `GLTFWriter.detectMeshQuantization(attributeName: string, attribute: THREE.BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * If a vertex attribute with a
	 * [non-standard data type](https://registry.khronos.org/glTF/specs/2.0/glTF-2.0.html#meshes-overview)
	 * is used, it is checked whether it is a valid data type according to the
	 * [KHR_mesh_quantization](https://github.com/KhronosGroup/glTF/blob/main/extensions/2.0/Khronos/KHR_mesh_quantization/README.md)
	 * extension.
	 * In this case the extension is automatically added to the list of used extensions.
	 *
	 * @param {string} attributeName
	 * @param {THREE.BufferAttribute} attribute
	 */
```

**Parameters:**

- **`attributeName`** `string`
- **`attribute`** `THREE.BufferAttribute`

**Returns:** `void`

**Calls:**

- `attributeName.split`
- `KHR_mesh_quantization_ExtraAttrTypes[ attrNamePrefix ].includes`

<details><summary>Code</summary>

```typescript
detectMeshQuantization( attributeName, attribute ) {

		if ( this.extensionsUsed[ KHR_MESH_QUANTIZATION ] ) return;

		let attrType = undefined;

		switch ( attribute.array.constructor ) {

			case Int8Array:

				attrType = 'byte';

				break;

			case Uint8Array:

				attrType = 'unsigned byte';

				break;

			case Int16Array:

				attrType = 'short';

				break;

			case Uint16Array:

				attrType = 'unsigned short';

				break;

			default:

				return;

		}

		if ( attribute.normalized ) attrType += ' normalized';

		const attrNamePrefix = attributeName.split( '_', 1 )[ 0 ];

		if ( KHR_mesh_quantization_ExtraAttrTypes[ attrNamePrefix ] && KHR_mesh_quantization_ExtraAttrTypes[ attrNamePrefix ].includes( attrType ) ) {

			this.extensionsUsed[ KHR_MESH_QUANTIZATION ] = true;
			this.extensionsRequired[ KHR_MESH_QUANTIZATION ] = true;

		}

	}
```
</details>

### `GLTFWriter.processCamera(camera: THREE.Camera): number`

**JSDoc:**
```typescript
/**
	 * Process camera
	 * @param {THREE.Camera} camera Camera to process
	 * @return {number} Index of the processed mesh in the "camera" array
	 */
```

**Parameters:**

- **`camera`** `THREE.Camera`

**Returns:** `number`

**Calls:**

- `MathUtils.degToRad`
- `json.cameras.push`

**Internal Comments:**
```
// Question: Is saving "type" as name intentional?
```

<details><summary>Code</summary>

```typescript
processCamera( camera ) {

		const json = this.json;

		if ( ! json.cameras ) json.cameras = [];

		const isOrtho = camera.isOrthographicCamera;

		const cameraDef = {
			type: isOrtho ? 'orthographic' : 'perspective'
		};

		if ( isOrtho ) {

			cameraDef.orthographic = {
				xmag: camera.right * 2,
				ymag: camera.top * 2,
				zfar: camera.far <= 0 ? 0.001 : camera.far,
				znear: camera.near < 0 ? 0 : camera.near
			};

		} else {

			cameraDef.perspective = {
				aspectRatio: camera.aspect,
				yfov: MathUtils.degToRad( camera.fov ),
				zfar: camera.far <= 0 ? 0.001 : camera.far,
				znear: camera.near < 0 ? 0 : camera.near
			};

		}

		// Question: Is saving "type" as name intentional?
		if ( camera.name !== '' ) cameraDef.name = camera.type;

		return json.cameras.push( cameraDef ) - 1;

	}
```
</details>

### `GLTFWriter.processAnimation(clip: THREE.AnimationClip, root: THREE.Object3D): number`

**JSDoc:**
```typescript
/**
	 * Creates glTF animation entry from AnimationClip object.
	 *
	 * Status:
	 * - Only properties listed in PATH_PROPERTIES may be animated.
	 *
	 * @param {THREE.AnimationClip} clip
	 * @param {THREE.Object3D} root
	 * @return {number|null}
	 */
```

**Parameters:**

- **`clip`** `THREE.AnimationClip`
- **`root`** `THREE.Object3D`

**Returns:** `number`

**Calls:**

- `GLTFExporter.Utils.mergeMorphTargetTracks`
- `clip.clone`
- `PropertyBinding.parseTrackName`
- `PropertyBinding.findNode`
- `trackNode.skeleton.getBoneByName`
- `console.warn`
- `track.getInterpolation`
- `samplers.push`
- `this.processAccessor`
- `channels.push`
- `nodeMap.get`
- `json.animations.push`

**Internal Comments:**
```
// @TODO export CubicInterpolant(InterpolateSmooth) as CUBICSPLINE
// Detecting glTF cubic spline interpolant by checking factory method's special property
// GLTFCubicSplineInterpolant is a custom interpolant and track doesn't return
// valid value from .getInterpolation().
// itemSize of CUBICSPLINE keyframe is 9 (x3)
// (VEC3 * 3: inTangent, splineVertex, and outTangent) (x3)
// but needs to be stored as VEC3 so dividing by 3 here. (x3)
```

<details><summary>Code</summary>

```typescript
processAnimation( clip, root ) {

		const json = this.json;
		const nodeMap = this.nodeMap;

		if ( ! json.animations ) json.animations = [];

		clip = GLTFExporter.Utils.mergeMorphTargetTracks( clip.clone(), root );

		const tracks = clip.tracks;
		const channels = [];
		const samplers = [];

		for ( let i = 0; i < tracks.length; ++ i ) {

			const track = tracks[ i ];
			const trackBinding = PropertyBinding.parseTrackName( track.name );
			let trackNode = PropertyBinding.findNode( root, trackBinding.nodeName );
			const trackProperty = PATH_PROPERTIES[ trackBinding.propertyName ];

			if ( trackBinding.objectName === 'bones' ) {

				if ( trackNode.isSkinnedMesh === true ) {

					trackNode = trackNode.skeleton.getBoneByName( trackBinding.objectIndex );

				} else {

					trackNode = undefined;

				}

			}

			if ( ! trackNode || ! trackProperty ) {

				console.warn( 'THREE.GLTFExporter: Could not export animation track "%s".', track.name );
				continue;

			}

			const inputItemSize = 1;
			let outputItemSize = track.values.length / track.times.length;

			if ( trackProperty === PATH_PROPERTIES.morphTargetInfluences ) {

				outputItemSize /= trackNode.morphTargetInfluences.length;

			}

			let interpolation;

			// @TODO export CubicInterpolant(InterpolateSmooth) as CUBICSPLINE

			// Detecting glTF cubic spline interpolant by checking factory method's special property
			// GLTFCubicSplineInterpolant is a custom interpolant and track doesn't return
			// valid value from .getInterpolation().
			if ( track.createInterpolant.isInterpolantFactoryMethodGLTFCubicSpline === true ) {

				interpolation = 'CUBICSPLINE';

				// itemSize of CUBICSPLINE keyframe is 9
				// (VEC3 * 3: inTangent, splineVertex, and outTangent)
				// but needs to be stored as VEC3 so dividing by 3 here.
				outputItemSize /= 3;

			} else if ( track.getInterpolation() === InterpolateDiscrete ) {

				interpolation = 'STEP';

			} else {

				interpolation = 'LINEAR';

			}

			samplers.push( {
				input: this.processAccessor( new BufferAttribute( track.times, inputItemSize ) ),
				output: this.processAccessor( new BufferAttribute( track.values, outputItemSize ) ),
				interpolation: interpolation
			} );

			channels.push( {
				sampler: samplers.length - 1,
				target: {
					node: nodeMap.get( trackNode ),
					path: trackProperty
				}
			} );

		}

		json.animations.push( {
			name: clip.name || 'clip_' + json.animations.length,
			samplers: samplers,
			channels: channels
		} );

		return json.animations.length - 1;

	}
```
</details>

### `GLTFWriter.processSkin(object: THREE.Object3D): number`

**JSDoc:**
```typescript
/**
	 * @param {THREE.Object3D} object
	 * @return {number|null}
	 */
```

**Parameters:**

- **`object`** `THREE.Object3D`

**Returns:** `number`

**Calls:**

- `nodeMap.get`
- `joints.push`
- `temporaryBoneInverse.copy`
- `temporaryBoneInverse.multiply( object.bindMatrix ).toArray`
- `json.skins.push`
- `this.processAccessor`

<details><summary>Code</summary>

```typescript
processSkin( object ) {

		const json = this.json;
		const nodeMap = this.nodeMap;

		const node = json.nodes[ nodeMap.get( object ) ];

		const skeleton = object.skeleton;

		if ( skeleton === undefined ) return null;

		const rootJoint = object.skeleton.bones[ 0 ];

		if ( rootJoint === undefined ) return null;

		const joints = [];
		const inverseBindMatrices = new Float32Array( skeleton.bones.length * 16 );
		const temporaryBoneInverse = new Matrix4();

		for ( let i = 0; i < skeleton.bones.length; ++ i ) {

			joints.push( nodeMap.get( skeleton.bones[ i ] ) );
			temporaryBoneInverse.copy( skeleton.boneInverses[ i ] );
			temporaryBoneInverse.multiply( object.bindMatrix ).toArray( inverseBindMatrices, i * 16 );

		}

		if ( json.skins === undefined ) json.skins = [];

		json.skins.push( {
			inverseBindMatrices: this.processAccessor( new BufferAttribute( inverseBindMatrices, 16 ) ),
			joints: joints,
			skeleton: nodeMap.get( rootJoint )
		} );

		const skinIndex = node.skin = json.skins.length - 1;

		return skinIndex;

	}
```
</details>

### `GLTFWriter.processNodeAsync(object: THREE.Object3D): Promise<number>`

**JSDoc:**
```typescript
/**
	 * Process Object3D node
	 * @param {THREE.Object3D} object Object3D to processNodeAsync
	 * @return {Promise<number>} Index of the node in the nodes list
	 */
```

**Parameters:**

- **`object`** `THREE.Object3D`

**Returns:** `Promise<number>`

**Calls:**

- `object.quaternion.toArray`
- `object.position.toArray`
- `object.scale.toArray`
- `equalArray`
- `object.updateMatrix`
- `isIdentityMatrix`
- `String`
- `this.serializeUserData`
- `this.processMeshAsync`
- `this.processCamera`
- `this.skins.push`
- `json.nodes.push`
- `nodeMap.set`
- `this.processNodeAsync`
- `children.push`
- `this._invokeAllAsync`
- `ext.writeNode`

**Internal Comments:**
```
// We don't export empty strings name because it represents no-name in Three.js.
```

<details><summary>Code</summary>

```typescript
async processNodeAsync( object ) {

		const json = this.json;
		const options = this.options;
		const nodeMap = this.nodeMap;

		if ( ! json.nodes ) json.nodes = [];

		const nodeDef = {};

		if ( options.trs ) {

			const rotation = object.quaternion.toArray();
			const position = object.position.toArray();
			const scale = object.scale.toArray();

			if ( ! equalArray( rotation, [ 0, 0, 0, 1 ] ) ) {

				nodeDef.rotation = rotation;

			}

			if ( ! equalArray( position, [ 0, 0, 0 ] ) ) {

				nodeDef.translation = position;

			}

			if ( ! equalArray( scale, [ 1, 1, 1 ] ) ) {

				nodeDef.scale = scale;

			}

		} else {

			if ( object.matrixAutoUpdate ) {

				object.updateMatrix();

			}

			if ( isIdentityMatrix( object.matrix ) === false ) {

				nodeDef.matrix = object.matrix.elements;

			}

		}

		// We don't export empty strings name because it represents no-name in Three.js.
		if ( object.name !== '' ) nodeDef.name = String( object.name );

		this.serializeUserData( object, nodeDef );

		if ( object.isMesh || object.isLine || object.isPoints ) {

			const meshIndex = await this.processMeshAsync( object );

			if ( meshIndex !== null ) nodeDef.mesh = meshIndex;

		} else if ( object.isCamera ) {

			nodeDef.camera = this.processCamera( object );

		}

		if ( object.isSkinnedMesh ) this.skins.push( object );

		const nodeIndex = json.nodes.push( nodeDef ) - 1;
		nodeMap.set( object, nodeIndex );

		if ( object.children.length > 0 ) {

			const children = [];

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				const child = object.children[ i ];

				if ( child.visible || options.onlyVisible === false ) {

					const childNodeIndex = await this.processNodeAsync( child );

					if ( childNodeIndex !== null ) children.push( childNodeIndex );

				}

			}

			if ( children.length > 0 ) nodeDef.children = children;

		}

		await this._invokeAllAsync( function ( ext ) {

			ext.writeNode && ext.writeNode( object, nodeDef );

		} );

		return nodeIndex;

	}
```
</details>

### `GLTFWriter.processSceneAsync(scene: Scene): Promise<void>`

**JSDoc:**
```typescript
/**
	 * Process Scene
	 * @param {Scene} scene Scene to process
	 */
```

**Parameters:**

- **`scene`** `Scene`

**Returns:** `Promise<void>`

**Calls:**

- `json.scenes.push`
- `this.processNodeAsync`
- `nodes.push`
- `this.serializeUserData`

<details><summary>Code</summary>

```typescript
async processSceneAsync( scene ) {

		const json = this.json;
		const options = this.options;

		if ( ! json.scenes ) {

			json.scenes = [];
			json.scene = 0;

		}

		const sceneDef = {};

		if ( scene.name !== '' ) sceneDef.name = scene.name;

		json.scenes.push( sceneDef );

		const nodes = [];

		for ( let i = 0, l = scene.children.length; i < l; i ++ ) {

			const child = scene.children[ i ];

			if ( child.visible || options.onlyVisible === false ) {

				const nodeIndex = await this.processNodeAsync( child );

				if ( nodeIndex !== null ) nodes.push( nodeIndex );

			}

		}

		if ( nodes.length > 0 ) sceneDef.nodes = nodes;

		this.serializeUserData( scene, sceneDef );

	}
```
</details>

### `GLTFWriter.processObjectsAsync(objects: THREE.Object3D[]): Promise<void>`

**JSDoc:**
```typescript
/**
	 * Creates a Scene to hold a list of objects and parse it
	 * @param {Array<THREE.Object3D>} objects List of objects to process
	 */
```

**Parameters:**

- **`objects`** `THREE.Object3D[]`

**Returns:** `Promise<void>`

**Calls:**

- `scene.children.push`
- `this.processSceneAsync`

**Internal Comments:**
```
// We push directly to children instead of calling `add` to prevent (x5)
// modify the .parent and break its original scene and hierarchy (x5)
```

<details><summary>Code</summary>

```typescript
async processObjectsAsync( objects ) {

		const scene = new Scene();
		scene.name = 'AuxScene';

		for ( let i = 0; i < objects.length; i ++ ) {

			// We push directly to children instead of calling `add` to prevent
			// modify the .parent and break its original scene and hierarchy
			scene.children.push( objects[ i ] );

		}

		await this.processSceneAsync( scene );

	}
```
</details>

### `GLTFWriter.processInputAsync(input: any): Promise<void>`

**JSDoc:**
```typescript
/**
	 * @param {THREE.Object3D|Array<THREE.Object3D>} input
	 */
```

**Parameters:**

- **`input`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `this._invokeAllAsync`
- `ext.beforeParse`
- `this.processSceneAsync`
- `objectsWithoutScene.push`
- `this.processObjectsAsync`
- `this.processSkin`
- `this.processAnimation`
- `ext.afterParse`

<details><summary>Code</summary>

```typescript
async processInputAsync( input ) {

		const options = this.options;

		input = input instanceof Array ? input : [ input ];

		await this._invokeAllAsync( function ( ext ) {

			ext.beforeParse && ext.beforeParse( input );

		} );

		const objectsWithoutScene = [];

		for ( let i = 0; i < input.length; i ++ ) {

			if ( input[ i ] instanceof Scene ) {

				await this.processSceneAsync( input[ i ] );

			} else {

				objectsWithoutScene.push( input[ i ] );

			}

		}

		if ( objectsWithoutScene.length > 0 ) {

			await this.processObjectsAsync( objectsWithoutScene );

		}

		for ( let i = 0; i < this.skins.length; ++ i ) {

			this.processSkin( this.skins[ i ] );

		}

		for ( let i = 0; i < options.animations.length; ++ i ) {

			this.processAnimation( options.animations[ i ], input[ 0 ] );

		}

		await this._invokeAllAsync( function ( ext ) {

			ext.afterParse && ext.afterParse( input );

		} );

	}
```
</details>

### `GLTFWriter._invokeAllAsync(func: any): Promise<void>`

**Parameters:**

- **`func`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `func`

<details><summary>Code</summary>

```typescript
async _invokeAllAsync( func ) {

		for ( let i = 0, il = this.plugins.length; i < il; i ++ ) {

			await func( this.plugins[ i ] );

		}

	}
```
</details>

### `getEncodingConversion(map: any): (c: any) => any`

**Parameters:**

- **`map`** `any`

**Returns:** `(c: any) => any`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function getEncodingConversion( map ) {

			if ( map.colorSpace === SRGBColorSpace ) {

				return function SRGBToLinear( c ) {

					return ( c < 0.04045 ) ? c * 0.0773993808 : Math.pow( c * 0.9478672986 + 0.0521327014, 2.4 );

				};

			}

			return function LinearToLinear( c ) {

				return c;

			};

		}
```
</details>

### `GLTFLightExtension.writeNode(light: any, nodeDef: any): void`

**Parameters:**

- **`light`** `any`
- **`nodeDef`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`
- `light.color.toArray`
- `lights.push`

<details><summary>Code</summary>

```typescript
writeNode( light, nodeDef ) {

		if ( ! light.isLight ) return;

		if ( ! light.isDirectionalLight && ! light.isPointLight && ! light.isSpotLight ) {

			console.warn( 'THREE.GLTFExporter: Only directional, point, and spot lights are supported.', light );
			return;

		}

		const writer = this.writer;
		const json = writer.json;
		const extensionsUsed = writer.extensionsUsed;

		const lightDef = {};

		if ( light.name ) lightDef.name = light.name;

		lightDef.color = light.color.toArray();

		lightDef.intensity = light.intensity;

		if ( light.isDirectionalLight ) {

			lightDef.type = 'directional';

		} else if ( light.isPointLight ) {

			lightDef.type = 'point';

			if ( light.distance > 0 ) lightDef.range = light.distance;

		} else if ( light.isSpotLight ) {

			lightDef.type = 'spot';

			if ( light.distance > 0 ) lightDef.range = light.distance;

			lightDef.spot = {};
			lightDef.spot.innerConeAngle = ( 1.0 - light.penumbra ) * light.angle;
			lightDef.spot.outerConeAngle = light.angle;

		}

		if ( light.decay !== undefined && light.decay !== 2 ) {

			console.warn( 'THREE.GLTFExporter: Light decay may be lost. glTF is physically-based, '
				+ 'and expects light.decay=2.' );

		}

		if ( light.target
				&& ( light.target.parent !== light
				|| light.target.position.x !== 0
				|| light.target.position.y !== 0
				|| light.target.position.z !== - 1 ) ) {

			console.warn( 'THREE.GLTFExporter: Light direction may be lost. For best results, '
				+ 'make light.target a child of the light with position 0,0,-1.' );

		}

		if ( ! extensionsUsed[ this.name ] ) {

			json.extensions = json.extensions || {};
			json.extensions[ this.name ] = { lights: [] };
			extensionsUsed[ this.name ] = true;

		}

		const lights = json.extensions[ this.name ].lights;
		lights.push( lightDef );

		nodeDef.extensions = nodeDef.extensions || {};
		nodeDef.extensions[ this.name ] = { light: lights.length - 1 };

	}
```
</details>

### `GLTFMaterialsUnlitExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshBasicMaterial ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = {};

		extensionsUsed[ this.name ] = true;

		materialDef.pbrMetallicRoughness.metallicFactor = 0.0;
		materialDef.pbrMetallicRoughness.roughnessFactor = 0.9;

	}
```
</details>

### `GLTFMaterialsClearcoatExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `writer.processTextureAsync`
- `writer.applyTextureTransform`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.clearcoat === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.clearcoatFactor = material.clearcoat;

		if ( material.clearcoatMap ) {

			const clearcoatMapDef = {
				index: await writer.processTextureAsync( material.clearcoatMap ),
				texCoord: material.clearcoatMap.channel
			};
			writer.applyTextureTransform( clearcoatMapDef, material.clearcoatMap );
			extensionDef.clearcoatTexture = clearcoatMapDef;

		}

		extensionDef.clearcoatRoughnessFactor = material.clearcoatRoughness;

		if ( material.clearcoatRoughnessMap ) {

			const clearcoatRoughnessMapDef = {
				index: await writer.processTextureAsync( material.clearcoatRoughnessMap ),
				texCoord: material.clearcoatRoughnessMap.channel
			};
			writer.applyTextureTransform( clearcoatRoughnessMapDef, material.clearcoatRoughnessMap );
			extensionDef.clearcoatRoughnessTexture = clearcoatRoughnessMapDef;

		}

		if ( material.clearcoatNormalMap ) {

			const clearcoatNormalMapDef = {
				index: await writer.processTextureAsync( material.clearcoatNormalMap ),
				texCoord: material.clearcoatNormalMap.channel
			};

			if ( material.clearcoatNormalScale.x !== 1 ) clearcoatNormalMapDef.scale = material.clearcoatNormalScale.x;

			writer.applyTextureTransform( clearcoatNormalMapDef, material.clearcoatNormalMap );
			extensionDef.clearcoatNormalTexture = clearcoatNormalMapDef;

		}

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;


	}
```
</details>

### `GLTFMaterialsDispersionExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.dispersion === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.dispersion = material.dispersion;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsIridescenceExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `writer.processTextureAsync`
- `writer.applyTextureTransform`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.iridescence === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.iridescenceFactor = material.iridescence;

		if ( material.iridescenceMap ) {

			const iridescenceMapDef = {
				index: await writer.processTextureAsync( material.iridescenceMap ),
				texCoord: material.iridescenceMap.channel
			};
			writer.applyTextureTransform( iridescenceMapDef, material.iridescenceMap );
			extensionDef.iridescenceTexture = iridescenceMapDef;

		}

		extensionDef.iridescenceIor = material.iridescenceIOR;
		extensionDef.iridescenceThicknessMinimum = material.iridescenceThicknessRange[ 0 ];
		extensionDef.iridescenceThicknessMaximum = material.iridescenceThicknessRange[ 1 ];

		if ( material.iridescenceThicknessMap ) {

			const iridescenceThicknessMapDef = {
				index: await writer.processTextureAsync( material.iridescenceThicknessMap ),
				texCoord: material.iridescenceThicknessMap.channel
			};
			writer.applyTextureTransform( iridescenceThicknessMapDef, material.iridescenceThicknessMap );
			extensionDef.iridescenceThicknessTexture = iridescenceThicknessMapDef;

		}

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsTransmissionExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `writer.processTextureAsync`
- `writer.applyTextureTransform`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.transmission === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.transmissionFactor = material.transmission;

		if ( material.transmissionMap ) {

			const transmissionMapDef = {
				index: await writer.processTextureAsync( material.transmissionMap ),
				texCoord: material.transmissionMap.channel
			};
			writer.applyTextureTransform( transmissionMapDef, material.transmissionMap );
			extensionDef.transmissionTexture = transmissionMapDef;

		}

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsVolumeExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `writer.processTextureAsync`
- `writer.applyTextureTransform`
- `material.attenuationColor.toArray`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.transmission === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.thicknessFactor = material.thickness;

		if ( material.thicknessMap ) {

			const thicknessMapDef = {
				index: await writer.processTextureAsync( material.thicknessMap ),
				texCoord: material.thicknessMap.channel
			};
			writer.applyTextureTransform( thicknessMapDef, material.thicknessMap );
			extensionDef.thicknessTexture = thicknessMapDef;

		}

		if ( material.attenuationDistance !== Infinity ) {

			extensionDef.attenuationDistance = material.attenuationDistance;

		}

		extensionDef.attenuationColor = material.attenuationColor.toArray();

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsIorExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.ior === 1.5 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.ior = material.ior;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsSpecularExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `material.specularColor.equals`
- `writer.processTextureAsync`
- `writer.applyTextureTransform`
- `material.specularColor.toArray`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || ( material.specularIntensity === 1.0 &&
		       material.specularColor.equals( DEFAULT_SPECULAR_COLOR ) &&
		     ! material.specularIntensityMap && ! material.specularColorMap ) ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.specularIntensityMap ) {

			const specularIntensityMapDef = {
				index: await writer.processTextureAsync( material.specularIntensityMap ),
				texCoord: material.specularIntensityMap.channel
			};
			writer.applyTextureTransform( specularIntensityMapDef, material.specularIntensityMap );
			extensionDef.specularTexture = specularIntensityMapDef;

		}

		if ( material.specularColorMap ) {

			const specularColorMapDef = {
				index: await writer.processTextureAsync( material.specularColorMap ),
				texCoord: material.specularColorMap.channel
			};
			writer.applyTextureTransform( specularColorMapDef, material.specularColorMap );
			extensionDef.specularColorTexture = specularColorMapDef;

		}

		extensionDef.specularFactor = material.specularIntensity;
		extensionDef.specularColorFactor = material.specularColor.toArray();

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsSheenExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `writer.processTextureAsync`
- `writer.applyTextureTransform`
- `material.sheenColor.toArray`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.sheen == 0.0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.sheenRoughnessMap ) {

			const sheenRoughnessMapDef = {
				index: await writer.processTextureAsync( material.sheenRoughnessMap ),
				texCoord: material.sheenRoughnessMap.channel
			};
			writer.applyTextureTransform( sheenRoughnessMapDef, material.sheenRoughnessMap );
			extensionDef.sheenRoughnessTexture = sheenRoughnessMapDef;

		}

		if ( material.sheenColorMap ) {

			const sheenColorMapDef = {
				index: await writer.processTextureAsync( material.sheenColorMap ),
				texCoord: material.sheenColorMap.channel
			};
			writer.applyTextureTransform( sheenColorMapDef, material.sheenColorMap );
			extensionDef.sheenColorTexture = sheenColorMapDef;

		}

		extensionDef.sheenRoughnessFactor = material.sheenRoughness;
		extensionDef.sheenColorFactor = material.sheenColor.toArray();

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsAnisotropyExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `writer.processTextureAsync`
- `writer.applyTextureTransform`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.anisotropy == 0.0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.anisotropyMap ) {

			const anisotropyMapDef = { index: await writer.processTextureAsync( material.anisotropyMap ) };
			writer.applyTextureTransform( anisotropyMapDef, material.anisotropyMap );
			extensionDef.anisotropyTexture = anisotropyMapDef;

		}

		extensionDef.anisotropyStrength = material.anisotropy;
		extensionDef.anisotropyRotation = material.anisotropyRotation;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsEmissiveStrengthExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshStandardMaterial || material.emissiveIntensity === 1.0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.emissiveStrength = material.emissiveIntensity;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsBumpExtension.writeMaterialAsync(material: any, materialDef: any): Promise<void>`

**Parameters:**

- **`material`** `any`
- **`materialDef`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `writer.processTextureAsync`
- `writer.applyTextureTransform`

<details><summary>Code</summary>

```typescript
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshStandardMaterial || (
		       material.bumpScale === 1 &&
		     ! material.bumpMap ) ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.bumpMap ) {

			const bumpMapDef = {
				index: await writer.processTextureAsync( material.bumpMap ),
				texCoord: material.bumpMap.channel
			};
			writer.applyTextureTransform( bumpMapDef, material.bumpMap );
			extensionDef.bumpTexture = bumpMapDef;

		}

		extensionDef.bumpFactor = material.bumpScale;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMeshGpuInstancing.writeNode(object: any, nodeDef: any): void`

**Parameters:**

- **`object`** `any`
- **`nodeDef`** `any`

**Returns:** `void`

**Calls:**

- `mesh.getMatrixAt`
- `matrix.decompose`
- `position.toArray`
- `quaternion.toArray`
- `scale.toArray`
- `writer.processAccessor`

<details><summary>Code</summary>

```typescript
writeNode( object, nodeDef ) {

		if ( ! object.isInstancedMesh ) return;

		const writer = this.writer;

		const mesh = object;

		const translationAttr = new Float32Array( mesh.count * 3 );
		const rotationAttr = new Float32Array( mesh.count * 4 );
		const scaleAttr = new Float32Array( mesh.count * 3 );

		const matrix = new Matrix4();
		const position = new Vector3();
		const quaternion = new Quaternion();
		const scale = new Vector3();

		for ( let i = 0; i < mesh.count; i ++ ) {

			mesh.getMatrixAt( i, matrix );
			matrix.decompose( position, quaternion, scale );

			position.toArray( translationAttr, i * 3 );
			quaternion.toArray( rotationAttr, i * 4 );
			scale.toArray( scaleAttr, i * 3 );

		}

		const attributes = {
			TRANSLATION: writer.processAccessor( new BufferAttribute( translationAttr, 3 ) ),
			ROTATION: writer.processAccessor( new BufferAttribute( rotationAttr, 4 ) ),
			SCALE: writer.processAccessor( new BufferAttribute( scaleAttr, 3 ) ),
		};

		if ( mesh.instanceColor )
			attributes._COLOR_0 = writer.processAccessor( mesh.instanceColor );

		nodeDef.extensions = nodeDef.extensions || {};
		nodeDef.extensions[ this.name ] = { attributes };

		writer.extensionsUsed[ this.name ] = true;
		writer.extensionsRequired[ this.name ] = true;

	}
```
</details>

### `insertKeyframe(track: any, time: any): number`

**Parameters:**

- **`track`** `any`
- **`time`** `any`

**Returns:** `number`

**Calls:**

- `track.getValueSize`
- `track.createInterpolant`
- `Math.abs`
- `times.set`
- `values.set`
- `interpolant.evaluate`
- `track.times.slice`
- `track.values.slice`

<details><summary>Code</summary>

```typescript
function ( track, time ) {

		const tolerance = 0.001; // 1ms
		const valueSize = track.getValueSize();

		const times = new track.TimeBufferType( track.times.length + 1 );
		const values = new track.ValueBufferType( track.values.length + valueSize );
		const interpolant = track.createInterpolant( new track.ValueBufferType( valueSize ) );

		let index;

		if ( track.times.length === 0 ) {

			times[ 0 ] = time;

			for ( let i = 0; i < valueSize; i ++ ) {

				values[ i ] = 0;

			}

			index = 0;

		} else if ( time < track.times[ 0 ] ) {

			if ( Math.abs( track.times[ 0 ] - time ) < tolerance ) return 0;

			times[ 0 ] = time;
			times.set( track.times, 1 );

			values.set( interpolant.evaluate( time ), 0 );
			values.set( track.values, valueSize );

			index = 0;

		} else if ( time > track.times[ track.times.length - 1 ] ) {

			if ( Math.abs( track.times[ track.times.length - 1 ] - time ) < tolerance ) {

				return track.times.length - 1;

			}

			times[ times.length - 1 ] = time;
			times.set( track.times, 0 );

			values.set( track.values, 0 );
			values.set( interpolant.evaluate( time ), track.values.length );

			index = times.length - 1;

		} else {

			for ( let i = 0; i < track.times.length; i ++ ) {

				if ( Math.abs( track.times[ i ] - time ) < tolerance ) return i;

				if ( track.times[ i ] < time && track.times[ i + 1 ] > time ) {

					times.set( track.times.slice( 0, i + 1 ), 0 );
					times[ i + 1 ] = time;
					times.set( track.times.slice( i + 1 ), i + 2 );

					values.set( track.values.slice( 0, ( i + 1 ) * valueSize ), 0 );
					values.set( interpolant.evaluate( time ), ( i + 1 ) * valueSize );
					values.set( track.values.slice( ( i + 1 ) * valueSize ), ( i + 2 ) * valueSize );

					index = i + 1;

					break;

				}

			}

		}

		track.times = times;
		track.values = values;

		return index;

	}
```
</details>

### `mergeMorphTargetTracks(clip: any, root: any): any`

**Parameters:**

- **`clip`** `any`
- **`root`** `any`

**Returns:** `any`

**Calls:**

- `PropertyBinding.parseTrackName`
- `PropertyBinding.findNode`
- `tracks.push`
- `console.warn`
- `sourceTrack.clone`
- `sourceTrack.setInterpolation`
- `sourceTrack.createInterpolant`
- `sourceInterpolant.evaluate`
- `this.insertKeyframe`

**Internal Comments:**
```
// Tracks that don't affect morph targets, or that affect all morph targets together, can be left as-is. (x4)
// This should never happen, because glTF morph target animations
// affect all targets already.
// If this is the first time we've seen this object, create a new
// track to store merged keyframe data for each morph target.
// We need to take into consideration the intended target node (x4)
// of our original un-merged morphTarget animation. (x4)
// For every existing keyframe of the merged track, write a (possibly
// interpolated) value from the source track.
// For every existing keyframe of the source track, write a (possibly
// new) keyframe to the merged track. Values from the previous loop may
// be written again, but keyframes are de-duplicated.
```

<details><summary>Code</summary>

```typescript
function ( clip, root ) {

		const tracks = [];
		const mergedTracks = {};
		const sourceTracks = clip.tracks;

		for ( let i = 0; i < sourceTracks.length; ++ i ) {

			let sourceTrack = sourceTracks[ i ];
			const sourceTrackBinding = PropertyBinding.parseTrackName( sourceTrack.name );
			const sourceTrackNode = PropertyBinding.findNode( root, sourceTrackBinding.nodeName );

			if ( sourceTrackBinding.propertyName !== 'morphTargetInfluences' || sourceTrackBinding.propertyIndex === undefined ) {

				// Tracks that don't affect morph targets, or that affect all morph targets together, can be left as-is.
				tracks.push( sourceTrack );
				continue;

			}

			if ( sourceTrack.createInterpolant !== sourceTrack.InterpolantFactoryMethodDiscrete
				&& sourceTrack.createInterpolant !== sourceTrack.InterpolantFactoryMethodLinear ) {

				if ( sourceTrack.createInterpolant.isInterpolantFactoryMethodGLTFCubicSpline ) {

					// This should never happen, because glTF morph target animations
					// affect all targets already.
					throw new Error( 'THREE.GLTFExporter: Cannot merge tracks with glTF CUBICSPLINE interpolation.' );

				}

				console.warn( 'THREE.GLTFExporter: Morph target interpolation mode not yet supported. Using LINEAR instead.' );

				sourceTrack = sourceTrack.clone();
				sourceTrack.setInterpolation( InterpolateLinear );

			}

			const targetCount = sourceTrackNode.morphTargetInfluences.length;
			const targetIndex = sourceTrackNode.morphTargetDictionary[ sourceTrackBinding.propertyIndex ];

			if ( targetIndex === undefined ) {

				throw new Error( 'THREE.GLTFExporter: Morph target name not found: ' + sourceTrackBinding.propertyIndex );

			}

			let mergedTrack;

			// If this is the first time we've seen this object, create a new
			// track to store merged keyframe data for each morph target.
			if ( mergedTracks[ sourceTrackNode.uuid ] === undefined ) {

				mergedTrack = sourceTrack.clone();

				const values = new mergedTrack.ValueBufferType( targetCount * mergedTrack.times.length );

				for ( let j = 0; j < mergedTrack.times.length; j ++ ) {

					values[ j * targetCount + targetIndex ] = mergedTrack.values[ j ];

				}

				// We need to take into consideration the intended target node
				// of our original un-merged morphTarget animation.
				mergedTrack.name = ( sourceTrackBinding.nodeName || '' ) + '.morphTargetInfluences';
				mergedTrack.values = values;

				mergedTracks[ sourceTrackNode.uuid ] = mergedTrack;
				tracks.push( mergedTrack );

				continue;

			}

			const sourceInterpolant = sourceTrack.createInterpolant( new sourceTrack.ValueBufferType( 1 ) );

			mergedTrack = mergedTracks[ sourceTrackNode.uuid ];

			// For every existing keyframe of the merged track, write a (possibly
			// interpolated) value from the source track.
			for ( let j = 0; j < mergedTrack.times.length; j ++ ) {

				mergedTrack.values[ j * targetCount + targetIndex ] = sourceInterpolant.evaluate( mergedTrack.times[ j ] );

			}

			// For every existing keyframe of the source track, write a (possibly
			// new) keyframe to the merged track. Values from the previous loop may
			// be written again, but keyframes are de-duplicated.
			for ( let j = 0; j < sourceTrack.times.length; j ++ ) {

				const keyframeIndex = this.insertKeyframe( mergedTrack, sourceTrack.times[ j ] );
				mergedTrack.values[ keyframeIndex * targetCount + targetIndex ] = sourceTrack.values[ j ];

			}

		}

		clip.tracks = tracks;

		return clip;

	}
```
</details>

### `toFloat32BufferAttribute(srcAttribute: any): any`

**Parameters:**

- **`srcAttribute`** `any`

**Returns:** `any`

**Calls:**

- `dstAttribute.array.set`
- `dstAttribute.setComponent`
- `srcAttribute.getComponent`

<details><summary>Code</summary>

```typescript
function ( srcAttribute ) {

		const dstAttribute = new BufferAttribute( new Float32Array( srcAttribute.count * srcAttribute.itemSize ), srcAttribute.itemSize, false );

		if ( ! srcAttribute.normalized && ! srcAttribute.isInterleavedBufferAttribute ) {

			dstAttribute.array.set( srcAttribute.array );

			return dstAttribute;

		}

		for ( let i = 0, il = srcAttribute.count; i < il; i ++ ) {

			for ( let j = 0; j < srcAttribute.itemSize; j ++ ) {

				dstAttribute.setComponent( i, j, srcAttribute.getComponent( i, j ) );

			}

		}

		return dstAttribute;

	}
```
</details>

### `insertKeyframe(track: any, time: any): number`

**Parameters:**

- **`track`** `any`
- **`time`** `any`

**Returns:** `number`

**Calls:**

- `track.getValueSize`
- `track.createInterpolant`
- `Math.abs`
- `times.set`
- `values.set`
- `interpolant.evaluate`
- `track.times.slice`
- `track.values.slice`

<details><summary>Code</summary>

```typescript
function ( track, time ) {

		const tolerance = 0.001; // 1ms
		const valueSize = track.getValueSize();

		const times = new track.TimeBufferType( track.times.length + 1 );
		const values = new track.ValueBufferType( track.values.length + valueSize );
		const interpolant = track.createInterpolant( new track.ValueBufferType( valueSize ) );

		let index;

		if ( track.times.length === 0 ) {

			times[ 0 ] = time;

			for ( let i = 0; i < valueSize; i ++ ) {

				values[ i ] = 0;

			}

			index = 0;

		} else if ( time < track.times[ 0 ] ) {

			if ( Math.abs( track.times[ 0 ] - time ) < tolerance ) return 0;

			times[ 0 ] = time;
			times.set( track.times, 1 );

			values.set( interpolant.evaluate( time ), 0 );
			values.set( track.values, valueSize );

			index = 0;

		} else if ( time > track.times[ track.times.length - 1 ] ) {

			if ( Math.abs( track.times[ track.times.length - 1 ] - time ) < tolerance ) {

				return track.times.length - 1;

			}

			times[ times.length - 1 ] = time;
			times.set( track.times, 0 );

			values.set( track.values, 0 );
			values.set( interpolant.evaluate( time ), track.values.length );

			index = times.length - 1;

		} else {

			for ( let i = 0; i < track.times.length; i ++ ) {

				if ( Math.abs( track.times[ i ] - time ) < tolerance ) return i;

				if ( track.times[ i ] < time && track.times[ i + 1 ] > time ) {

					times.set( track.times.slice( 0, i + 1 ), 0 );
					times[ i + 1 ] = time;
					times.set( track.times.slice( i + 1 ), i + 2 );

					values.set( track.values.slice( 0, ( i + 1 ) * valueSize ), 0 );
					values.set( interpolant.evaluate( time ), ( i + 1 ) * valueSize );
					values.set( track.values.slice( ( i + 1 ) * valueSize ), ( i + 2 ) * valueSize );

					index = i + 1;

					break;

				}

			}

		}

		track.times = times;
		track.values = values;

		return index;

	}
```
</details>

### `mergeMorphTargetTracks(clip: any, root: any): any`

**Parameters:**

- **`clip`** `any`
- **`root`** `any`

**Returns:** `any`

**Calls:**

- `PropertyBinding.parseTrackName`
- `PropertyBinding.findNode`
- `tracks.push`
- `console.warn`
- `sourceTrack.clone`
- `sourceTrack.setInterpolation`
- `sourceTrack.createInterpolant`
- `sourceInterpolant.evaluate`
- `this.insertKeyframe`

**Internal Comments:**
```
// Tracks that don't affect morph targets, or that affect all morph targets together, can be left as-is. (x4)
// This should never happen, because glTF morph target animations
// affect all targets already.
// If this is the first time we've seen this object, create a new
// track to store merged keyframe data for each morph target.
// We need to take into consideration the intended target node (x4)
// of our original un-merged morphTarget animation. (x4)
// For every existing keyframe of the merged track, write a (possibly
// interpolated) value from the source track.
// For every existing keyframe of the source track, write a (possibly
// new) keyframe to the merged track. Values from the previous loop may
// be written again, but keyframes are de-duplicated.
```

<details><summary>Code</summary>

```typescript
function ( clip, root ) {

		const tracks = [];
		const mergedTracks = {};
		const sourceTracks = clip.tracks;

		for ( let i = 0; i < sourceTracks.length; ++ i ) {

			let sourceTrack = sourceTracks[ i ];
			const sourceTrackBinding = PropertyBinding.parseTrackName( sourceTrack.name );
			const sourceTrackNode = PropertyBinding.findNode( root, sourceTrackBinding.nodeName );

			if ( sourceTrackBinding.propertyName !== 'morphTargetInfluences' || sourceTrackBinding.propertyIndex === undefined ) {

				// Tracks that don't affect morph targets, or that affect all morph targets together, can be left as-is.
				tracks.push( sourceTrack );
				continue;

			}

			if ( sourceTrack.createInterpolant !== sourceTrack.InterpolantFactoryMethodDiscrete
				&& sourceTrack.createInterpolant !== sourceTrack.InterpolantFactoryMethodLinear ) {

				if ( sourceTrack.createInterpolant.isInterpolantFactoryMethodGLTFCubicSpline ) {

					// This should never happen, because glTF morph target animations
					// affect all targets already.
					throw new Error( 'THREE.GLTFExporter: Cannot merge tracks with glTF CUBICSPLINE interpolation.' );

				}

				console.warn( 'THREE.GLTFExporter: Morph target interpolation mode not yet supported. Using LINEAR instead.' );

				sourceTrack = sourceTrack.clone();
				sourceTrack.setInterpolation( InterpolateLinear );

			}

			const targetCount = sourceTrackNode.morphTargetInfluences.length;
			const targetIndex = sourceTrackNode.morphTargetDictionary[ sourceTrackBinding.propertyIndex ];

			if ( targetIndex === undefined ) {

				throw new Error( 'THREE.GLTFExporter: Morph target name not found: ' + sourceTrackBinding.propertyIndex );

			}

			let mergedTrack;

			// If this is the first time we've seen this object, create a new
			// track to store merged keyframe data for each morph target.
			if ( mergedTracks[ sourceTrackNode.uuid ] === undefined ) {

				mergedTrack = sourceTrack.clone();

				const values = new mergedTrack.ValueBufferType( targetCount * mergedTrack.times.length );

				for ( let j = 0; j < mergedTrack.times.length; j ++ ) {

					values[ j * targetCount + targetIndex ] = mergedTrack.values[ j ];

				}

				// We need to take into consideration the intended target node
				// of our original un-merged morphTarget animation.
				mergedTrack.name = ( sourceTrackBinding.nodeName || '' ) + '.morphTargetInfluences';
				mergedTrack.values = values;

				mergedTracks[ sourceTrackNode.uuid ] = mergedTrack;
				tracks.push( mergedTrack );

				continue;

			}

			const sourceInterpolant = sourceTrack.createInterpolant( new sourceTrack.ValueBufferType( 1 ) );

			mergedTrack = mergedTracks[ sourceTrackNode.uuid ];

			// For every existing keyframe of the merged track, write a (possibly
			// interpolated) value from the source track.
			for ( let j = 0; j < mergedTrack.times.length; j ++ ) {

				mergedTrack.values[ j * targetCount + targetIndex ] = sourceInterpolant.evaluate( mergedTrack.times[ j ] );

			}

			// For every existing keyframe of the source track, write a (possibly
			// new) keyframe to the merged track. Values from the previous loop may
			// be written again, but keyframes are de-duplicated.
			for ( let j = 0; j < sourceTrack.times.length; j ++ ) {

				const keyframeIndex = this.insertKeyframe( mergedTrack, sourceTrack.times[ j ] );
				mergedTrack.values[ keyframeIndex * targetCount + targetIndex ] = sourceTrack.values[ j ];

			}

		}

		clip.tracks = tracks;

		return clip;

	}
```
</details>

### `toFloat32BufferAttribute(srcAttribute: any): any`

**Parameters:**

- **`srcAttribute`** `any`

**Returns:** `any`

**Calls:**

- `dstAttribute.array.set`
- `dstAttribute.setComponent`
- `srcAttribute.getComponent`

<details><summary>Code</summary>

```typescript
function ( srcAttribute ) {

		const dstAttribute = new BufferAttribute( new Float32Array( srcAttribute.count * srcAttribute.itemSize ), srcAttribute.itemSize, false );

		if ( ! srcAttribute.normalized && ! srcAttribute.isInterleavedBufferAttribute ) {

			dstAttribute.array.set( srcAttribute.array );

			return dstAttribute;

		}

		for ( let i = 0, il = srcAttribute.count; i < il; i ++ ) {

			for ( let j = 0; j < srcAttribute.itemSize; j ++ ) {

				dstAttribute.setComponent( i, j, srcAttribute.getComponent( i, j ) );

			}

		}

		return dstAttribute;

	}
```
</details>


---

## Classes

### `GLTFExporter`

<details><summary>Class Code</summary>

```ts
class GLTFExporter {

	/**
	 * Constructs a new glTF exporter.
	 */
	constructor() {

		/**
		 * A reference to a texture utils module.
		 *
		 * @type {?(WebGLTextureUtils|WebGPUTextureUtils)}
		 * @default null
		 */
		this.textureUtils = null;

		this.pluginCallbacks = [];

		this.register( function ( writer ) {

			return new GLTFLightExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsUnlitExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsTransmissionExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsVolumeExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsIorExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsSpecularExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsClearcoatExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsDispersionExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsIridescenceExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsSheenExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsAnisotropyExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsEmissiveStrengthExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMaterialsBumpExtension( writer );

		} );

		this.register( function ( writer ) {

			return new GLTFMeshGpuInstancing( writer );

		} );

	}

	/**
	 * Registers a plugin callback. This API is internally used to implement the various
	 * glTF extensions but can also used by third-party code to add additional logic
	 * to the exporter.
	 *
	 * @param {function(writer:GLTFWriter)} callback - The callback function to register.
	 * @return {GLTFExporter} A reference to this exporter.
	 */
	register( callback ) {

		if ( this.pluginCallbacks.indexOf( callback ) === - 1 ) {

			this.pluginCallbacks.push( callback );

		}

		return this;

	}

	/**
	 * Unregisters a plugin callback.
	 *
	 * @param {Function} callback - The callback function to unregister.
	 * @return {GLTFExporter} A reference to this exporter.
	 */
	unregister( callback ) {

		if ( this.pluginCallbacks.indexOf( callback ) !== - 1 ) {

			this.pluginCallbacks.splice( this.pluginCallbacks.indexOf( callback ), 1 );

		}

		return this;

	}

	/**
	 * Sets the texture utils for this exporter. Only relevant when compressed textures have to be exported.
	 *
	 * Depending on whether you use {@link WebGLRenderer} or {@link WebGPURenderer}, you must inject the
	 * corresponding texture utils {@link WebGLTextureUtils} or {@link WebGPUTextureUtils}.
	 *
	 * @param {WebGLTextureUtils|WebGPUTextureUtils} utils - The texture utils.
	 * @return {GLTFExporter} A reference to this exporter.
	 */
	setTextureUtils( utils ) {

		this.textureUtils = utils;

		return this;

	}

	/**
	 * Parses the given scenes and generates the glTF output.
	 *
	 * @param {Scene|Array<Scene>} input - A scene or an array of scenes.
	 * @param {GLTFExporter~OnDone} onDone - A callback function that is executed when the export has finished.
	 * @param {GLTFExporter~OnError} onError - A callback function that is executed when an error happens.
	 * @param {GLTFExporter~Options} options - options
	 */
	parse( input, onDone, onError, options ) {

		const writer = new GLTFWriter();
		const plugins = [];

		for ( let i = 0, il = this.pluginCallbacks.length; i < il; i ++ ) {

			plugins.push( this.pluginCallbacks[ i ]( writer ) );

		}

		writer.setPlugins( plugins );
		writer.setTextureUtils( this.textureUtils );
		writer.writeAsync( input, onDone, options ).catch( onError );

	}

	/**
	 * Async version of {@link GLTFExporter#parse}.
	 *
	 * @param {Scene|Array<Scene>} input - A scene or an array of scenes.
	 * @param {GLTFExporter~Options} options - options.
	 * @return {Promise<ArrayBuffer|string>} A Promise that resolved with the exported glTF data.
	 */
	parseAsync( input, options ) {

		const scope = this;

		return new Promise( function ( resolve, reject ) {

			scope.parse( input, resolve, reject, options );

		} );

	}

}
```
</details>

#### Methods

##### `register(callback: any): GLTFExporter`

<details><summary>Code</summary>

```ts
register( callback ) {

		if ( this.pluginCallbacks.indexOf( callback ) === - 1 ) {

			this.pluginCallbacks.push( callback );

		}

		return this;

	}
```
</details>

##### `unregister(callback: Function): GLTFExporter`

<details><summary>Code</summary>

```ts
unregister( callback ) {

		if ( this.pluginCallbacks.indexOf( callback ) !== - 1 ) {

			this.pluginCallbacks.splice( this.pluginCallbacks.indexOf( callback ), 1 );

		}

		return this;

	}
```
</details>

##### `setTextureUtils(utils: any): GLTFExporter`

<details><summary>Code</summary>

```ts
setTextureUtils( utils ) {

		this.textureUtils = utils;

		return this;

	}
```
</details>

##### `parse(input: any, onDone: any, onError: any, options: any): void`

<details><summary>Code</summary>

```ts
parse( input, onDone, onError, options ) {

		const writer = new GLTFWriter();
		const plugins = [];

		for ( let i = 0, il = this.pluginCallbacks.length; i < il; i ++ ) {

			plugins.push( this.pluginCallbacks[ i ]( writer ) );

		}

		writer.setPlugins( plugins );
		writer.setTextureUtils( this.textureUtils );
		writer.writeAsync( input, onDone, options ).catch( onError );

	}
```
</details>

##### `parseAsync(input: any, options: any): Promise<string | ArrayBuffer>`

<details><summary>Code</summary>

```ts
parseAsync( input, options ) {

		const scope = this;

		return new Promise( function ( resolve, reject ) {

			scope.parse( input, resolve, reject, options );

		} );

	}
```
</details>

### `GLTFWriter`

<details><summary>Class Code</summary>

```ts
class GLTFWriter {

	constructor() {

		this.plugins = [];

		this.options = {};
		this.pending = [];
		this.buffers = [];

		this.byteOffset = 0;
		this.buffers = [];
		this.nodeMap = new Map();
		this.skins = [];

		this.extensionsUsed = {};
		this.extensionsRequired = {};

		this.uids = new Map();
		this.uid = 0;

		this.json = {
			asset: {
				version: '2.0',
				generator: 'THREE.GLTFExporter r' + REVISION
			}
		};

		this.cache = {
			meshes: new Map(),
			attributes: new Map(),
			attributesNormalized: new Map(),
			materials: new Map(),
			textures: new Map(),
			images: new Map()
		};

		this.textureUtils = null;

	}

	setPlugins( plugins ) {

		this.plugins = plugins;

	}

	setTextureUtils( utils ) {

		this.textureUtils = utils;

	}

	/**
	 * Parse scenes and generate GLTF output
	 *
	 * @param {Scene|Array<Scene>} input Scene or Array of THREE.Scenes
	 * @param {Function} onDone Callback on completed
	 * @param {Object} options options
	 */
	async writeAsync( input, onDone, options = {} ) {

		this.options = Object.assign( {
			// default options
			binary: false,
			trs: false,
			onlyVisible: true,
			maxTextureSize: Infinity,
			animations: [],
			includeCustomExtensions: false
		}, options );

		if ( this.options.animations.length > 0 ) {

			// Only TRS properties, and not matrices, may be targeted by animation.
			this.options.trs = true;

		}

		await this.processInputAsync( input );

		await Promise.all( this.pending );

		const writer = this;
		const buffers = writer.buffers;
		const json = writer.json;
		options = writer.options;

		const extensionsUsed = writer.extensionsUsed;
		const extensionsRequired = writer.extensionsRequired;

		// Merge buffers.
		const blob = new Blob( buffers, { type: 'application/octet-stream' } );

		// Declare extensions.
		const extensionsUsedList = Object.keys( extensionsUsed );
		const extensionsRequiredList = Object.keys( extensionsRequired );

		if ( extensionsUsedList.length > 0 ) json.extensionsUsed = extensionsUsedList;
		if ( extensionsRequiredList.length > 0 ) json.extensionsRequired = extensionsRequiredList;

		// Update bytelength of the single buffer.
		if ( json.buffers && json.buffers.length > 0 ) json.buffers[ 0 ].byteLength = blob.size;

		if ( options.binary === true ) {

			// https://github.com/KhronosGroup/glTF/blob/master/specification/2.0/README.md#glb-file-format-specification

			const reader = new FileReader();
			reader.readAsArrayBuffer( blob );
			reader.onloadend = function () {

				// Binary chunk.
				const binaryChunk = getPaddedArrayBuffer( reader.result );
				const binaryChunkPrefix = new DataView( new ArrayBuffer( GLB_CHUNK_PREFIX_BYTES ) );
				binaryChunkPrefix.setUint32( 0, binaryChunk.byteLength, true );
				binaryChunkPrefix.setUint32( 4, GLB_CHUNK_TYPE_BIN, true );

				// JSON chunk.
				const jsonChunk = getPaddedArrayBuffer( stringToArrayBuffer( JSON.stringify( json ) ), 0x20 );
				const jsonChunkPrefix = new DataView( new ArrayBuffer( GLB_CHUNK_PREFIX_BYTES ) );
				jsonChunkPrefix.setUint32( 0, jsonChunk.byteLength, true );
				jsonChunkPrefix.setUint32( 4, GLB_CHUNK_TYPE_JSON, true );

				// GLB header.
				const header = new ArrayBuffer( GLB_HEADER_BYTES );
				const headerView = new DataView( header );
				headerView.setUint32( 0, GLB_HEADER_MAGIC, true );
				headerView.setUint32( 4, GLB_VERSION, true );
				const totalByteLength = GLB_HEADER_BYTES
					+ jsonChunkPrefix.byteLength + jsonChunk.byteLength
					+ binaryChunkPrefix.byteLength + binaryChunk.byteLength;
				headerView.setUint32( 8, totalByteLength, true );

				const glbBlob = new Blob( [
					header,
					jsonChunkPrefix,
					jsonChunk,
					binaryChunkPrefix,
					binaryChunk
				], { type: 'application/octet-stream' } );

				const glbReader = new FileReader();
				glbReader.readAsArrayBuffer( glbBlob );
				glbReader.onloadend = function () {

					onDone( glbReader.result );

				};

			};

		} else {

			if ( json.buffers && json.buffers.length > 0 ) {

				const reader = new FileReader();
				reader.readAsDataURL( blob );
				reader.onloadend = function () {

					const base64data = reader.result;
					json.buffers[ 0 ].uri = base64data;
					onDone( json );

				};

			} else {

				onDone( json );

			}

		}


	}

	/**
	 * Serializes a userData.
	 *
	 * @param {THREE.Object3D|THREE.Material} object
	 * @param {Object} objectDef
	 */
	serializeUserData( object, objectDef ) {

		if ( Object.keys( object.userData ).length === 0 ) return;

		const options = this.options;
		const extensionsUsed = this.extensionsUsed;

		try {

			const json = JSON.parse( JSON.stringify( object.userData ) );

			if ( options.includeCustomExtensions && json.gltfExtensions ) {

				if ( objectDef.extensions === undefined ) objectDef.extensions = {};

				for ( const extensionName in json.gltfExtensions ) {

					objectDef.extensions[ extensionName ] = json.gltfExtensions[ extensionName ];
					extensionsUsed[ extensionName ] = true;

				}

				delete json.gltfExtensions;

			}

			if ( Object.keys( json ).length > 0 ) objectDef.extras = json;

		} catch ( error ) {

			console.warn( 'THREE.GLTFExporter: userData of \'' + object.name + '\' ' +
				'won\'t be serialized because of JSON.stringify error - ' + error.message );

		}

	}

	/**
	 * Returns ids for buffer attributes.
	 *
	 * @param {Object} attribute
	 * @param {boolean} [isRelativeCopy=false]
	 * @return {number} An integer
	 */
	getUID( attribute, isRelativeCopy = false ) {

		if ( this.uids.has( attribute ) === false ) {

			const uids = new Map();

			uids.set( true, this.uid ++ );
			uids.set( false, this.uid ++ );

			this.uids.set( attribute, uids );

		}

		const uids = this.uids.get( attribute );

		return uids.get( isRelativeCopy );

	}

	/**
	 * Checks if normal attribute values are normalized.
	 *
	 * @param {BufferAttribute} normal
	 * @returns {boolean}
	 */
	isNormalizedNormalAttribute( normal ) {

		const cache = this.cache;

		if ( cache.attributesNormalized.has( normal ) ) return false;

		const v = new Vector3();

		for ( let i = 0, il = normal.count; i < il; i ++ ) {

			// 0.0005 is from glTF-validator
			if ( Math.abs( v.fromBufferAttribute( normal, i ).length() - 1.0 ) > 0.0005 ) return false;

		}

		return true;

	}

	/**
	 * Creates normalized normal buffer attribute.
	 *
	 * @param {BufferAttribute} normal
	 * @returns {BufferAttribute}
	 *
	 */
	createNormalizedNormalAttribute( normal ) {

		const cache = this.cache;

		if ( cache.attributesNormalized.has( normal ) )	return cache.attributesNormalized.get( normal );

		const attribute = normal.clone();
		const v = new Vector3();

		for ( let i = 0, il = attribute.count; i < il; i ++ ) {

			v.fromBufferAttribute( attribute, i );

			if ( v.x === 0 && v.y === 0 && v.z === 0 ) {

				// if values can't be normalized set (1, 0, 0)
				v.setX( 1.0 );

			} else {

				v.normalize();

			}

			attribute.setXYZ( i, v.x, v.y, v.z );

		}

		cache.attributesNormalized.set( normal, attribute );

		return attribute;

	}

	/**
	 * Applies a texture transform, if present, to the map definition. Requires
	 * the KHR_texture_transform extension.
	 *
	 * @param {Object} mapDef
	 * @param {THREE.Texture} texture
	 */
	applyTextureTransform( mapDef, texture ) {

		let didTransform = false;
		const transformDef = {};

		if ( texture.offset.x !== 0 || texture.offset.y !== 0 ) {

			transformDef.offset = texture.offset.toArray();
			didTransform = true;

		}

		if ( texture.rotation !== 0 ) {

			transformDef.rotation = texture.rotation;
			didTransform = true;

		}

		if ( texture.repeat.x !== 1 || texture.repeat.y !== 1 ) {

			transformDef.scale = texture.repeat.toArray();
			didTransform = true;

		}

		if ( didTransform ) {

			mapDef.extensions = mapDef.extensions || {};
			mapDef.extensions[ 'KHR_texture_transform' ] = transformDef;
			this.extensionsUsed[ 'KHR_texture_transform' ] = true;

		}

	}

	async buildMetalRoughTextureAsync( metalnessMap, roughnessMap ) {

		if ( metalnessMap === roughnessMap ) return metalnessMap;

		function getEncodingConversion( map ) {

			if ( map.colorSpace === SRGBColorSpace ) {

				return function SRGBToLinear( c ) {

					return ( c < 0.04045 ) ? c * 0.0773993808 : Math.pow( c * 0.9478672986 + 0.0521327014, 2.4 );

				};

			}

			return function LinearToLinear( c ) {

				return c;

			};

		}

		if ( metalnessMap instanceof CompressedTexture ) {

			metalnessMap = await this.decompressTextureAsync( metalnessMap );

		}

		if ( roughnessMap instanceof CompressedTexture ) {

			roughnessMap = await this.decompressTextureAsync( roughnessMap );

		}

		const metalness = metalnessMap ? metalnessMap.image : null;
		const roughness = roughnessMap ? roughnessMap.image : null;

		const width = Math.max( metalness ? metalness.width : 0, roughness ? roughness.width : 0 );
		const height = Math.max( metalness ? metalness.height : 0, roughness ? roughness.height : 0 );

		const canvas = getCanvas();
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d', {
			willReadFrequently: true,
		} );
		context.fillStyle = '#00ffff';
		context.fillRect( 0, 0, width, height );

		const composite = context.getImageData( 0, 0, width, height );

		if ( metalness ) {

			context.drawImage( metalness, 0, 0, width, height );

			const convert = getEncodingConversion( metalnessMap );
			const data = context.getImageData( 0, 0, width, height ).data;

			for ( let i = 2; i < data.length; i += 4 ) {

				composite.data[ i ] = convert( data[ i ] / 256 ) * 256;

			}

		}

		if ( roughness ) {

			context.drawImage( roughness, 0, 0, width, height );

			const convert = getEncodingConversion( roughnessMap );
			const data = context.getImageData( 0, 0, width, height ).data;

			for ( let i = 1; i < data.length; i += 4 ) {

				composite.data[ i ] = convert( data[ i ] / 256 ) * 256;

			}

		}

		context.putImageData( composite, 0, 0 );

		//

		const reference = metalnessMap || roughnessMap;

		const texture = reference.clone();

		texture.source = new Source( canvas );
		texture.colorSpace = NoColorSpace;
		texture.channel = ( metalnessMap || roughnessMap ).channel;

		if ( metalnessMap && roughnessMap && metalnessMap.channel !== roughnessMap.channel ) {

			console.warn( 'THREE.GLTFExporter: UV channels for metalnessMap and roughnessMap textures must match.' );

		}

		console.warn( 'THREE.GLTFExporter: Merged metalnessMap and roughnessMap textures.' );

		return texture;

	}


	async decompressTextureAsync( texture, maxTextureSize = Infinity ) {

		if ( this.textureUtils === null ) {

			throw new Error( 'THREE.GLTFExporter: setTextureUtils() must be called to process compressed textures.' );

		}

		return await this.textureUtils.decompress( texture, maxTextureSize );

	}

	/**
	 * Process a buffer to append to the default one.
	 * @param {ArrayBuffer} buffer
	 * @return {0}
	 */
	processBuffer( buffer ) {

		const json = this.json;
		const buffers = this.buffers;

		if ( ! json.buffers ) json.buffers = [ { byteLength: 0 } ];

		// All buffers are merged before export.
		buffers.push( buffer );

		return 0;

	}

	/**
	 * Process and generate a BufferView
	 * @param {BufferAttribute} attribute
	 * @param {number} componentType
	 * @param {number} start
	 * @param {number} count
	 * @param {number} [target] Target usage of the BufferView
	 * @return {Object}
	 */
	processBufferView( attribute, componentType, start, count, target ) {

		const json = this.json;

		if ( ! json.bufferViews ) json.bufferViews = [];

		// Create a new dataview and dump the attribute's array into it

		let componentSize;

		switch ( componentType ) {

			case WEBGL_CONSTANTS.BYTE:
			case WEBGL_CONSTANTS.UNSIGNED_BYTE:

				componentSize = 1;

				break;

			case WEBGL_CONSTANTS.SHORT:
			case WEBGL_CONSTANTS.UNSIGNED_SHORT:

				componentSize = 2;

				break;

			default:

				componentSize = 4;

		}

		let byteStride = attribute.itemSize * componentSize;

		if ( target === WEBGL_CONSTANTS.ARRAY_BUFFER ) {

			// Each element of a vertex attribute MUST be aligned to 4-byte boundaries
			// inside a bufferView
			byteStride = Math.ceil( byteStride / 4 ) * 4;

		}

		const byteLength = getPaddedBufferSize( count * byteStride );
		const dataView = new DataView( new ArrayBuffer( byteLength ) );
		let offset = 0;

		for ( let i = start; i < start + count; i ++ ) {

			for ( let a = 0; a < attribute.itemSize; a ++ ) {

				let value;

				if ( attribute.itemSize > 4 ) {

					 // no support for interleaved data for itemSize > 4

					value = attribute.array[ i * attribute.itemSize + a ];

				} else {

					if ( a === 0 ) value = attribute.getX( i );
					else if ( a === 1 ) value = attribute.getY( i );
					else if ( a === 2 ) value = attribute.getZ( i );
					else if ( a === 3 ) value = attribute.getW( i );

					if ( attribute.normalized === true ) {

						value = MathUtils.normalize( value, attribute.array );

					}

				}

				if ( componentType === WEBGL_CONSTANTS.FLOAT ) {

					dataView.setFloat32( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.INT ) {

					dataView.setInt32( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.UNSIGNED_INT ) {

					dataView.setUint32( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.SHORT ) {

					dataView.setInt16( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.UNSIGNED_SHORT ) {

					dataView.setUint16( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.BYTE ) {

					dataView.setInt8( offset, value );

				} else if ( componentType === WEBGL_CONSTANTS.UNSIGNED_BYTE ) {

					dataView.setUint8( offset, value );

				}

				offset += componentSize;

			}

			if ( ( offset % byteStride ) !== 0 ) {

				offset += byteStride - ( offset % byteStride );

			}

		}

		const bufferViewDef = {

			buffer: this.processBuffer( dataView.buffer ),
			byteOffset: this.byteOffset,
			byteLength: byteLength

		};

		if ( target !== undefined ) bufferViewDef.target = target;

		if ( target === WEBGL_CONSTANTS.ARRAY_BUFFER ) {

			// Only define byteStride for vertex attributes.
			bufferViewDef.byteStride = byteStride;

		}

		this.byteOffset += byteLength;

		json.bufferViews.push( bufferViewDef );

		// @TODO Merge bufferViews where possible.
		const output = {

			id: json.bufferViews.length - 1,
			byteLength: 0

		};

		return output;

	}

	/**
	 * Process and generate a BufferView from an image Blob.
	 * @param {Blob} blob
	 * @return {Promise<number>} An integer
	 */
	processBufferViewImage( blob ) {

		const writer = this;
		const json = writer.json;

		if ( ! json.bufferViews ) json.bufferViews = [];

		return new Promise( function ( resolve ) {

			const reader = new FileReader();
			reader.readAsArrayBuffer( blob );
			reader.onloadend = function () {

				const buffer = getPaddedArrayBuffer( reader.result );

				const bufferViewDef = {
					buffer: writer.processBuffer( buffer ),
					byteOffset: writer.byteOffset,
					byteLength: buffer.byteLength
				};

				writer.byteOffset += buffer.byteLength;
				resolve( json.bufferViews.push( bufferViewDef ) - 1 );

			};

		} );

	}

	/**
	 * Process attribute to generate an accessor
	 * @param {BufferAttribute} attribute Attribute to process
	 * @param {?BufferGeometry} [geometry] Geometry used for truncated draw range
	 * @param {number} [start=0]
	 * @param {number} [count=Infinity]
	 * @return {?number} Index of the processed accessor on the "accessors" array
	 */
	processAccessor( attribute, geometry, start, count ) {

		const json = this.json;

		const types = {

			1: 'SCALAR',
			2: 'VEC2',
			3: 'VEC3',
			4: 'VEC4',
			9: 'MAT3',
			16: 'MAT4'

		};

		let componentType;

		// Detect the component type of the attribute array
		if ( attribute.array.constructor === Float32Array ) {

			componentType = WEBGL_CONSTANTS.FLOAT;

		} else if ( attribute.array.constructor === Int32Array ) {

			componentType = WEBGL_CONSTANTS.INT;

		} else if ( attribute.array.constructor === Uint32Array ) {

			componentType = WEBGL_CONSTANTS.UNSIGNED_INT;

		} else if ( attribute.array.constructor === Int16Array ) {

			componentType = WEBGL_CONSTANTS.SHORT;

		} else if ( attribute.array.constructor === Uint16Array ) {

			componentType = WEBGL_CONSTANTS.UNSIGNED_SHORT;

		} else if ( attribute.array.constructor === Int8Array ) {

			componentType = WEBGL_CONSTANTS.BYTE;

		} else if ( attribute.array.constructor === Uint8Array ) {

			componentType = WEBGL_CONSTANTS.UNSIGNED_BYTE;

		} else {

			throw new Error( 'THREE.GLTFExporter: Unsupported bufferAttribute component type: ' + attribute.array.constructor.name );

		}

		if ( start === undefined ) start = 0;
		if ( count === undefined || count === Infinity ) count = attribute.count;

		// Skip creating an accessor if the attribute doesn't have data to export
		if ( count === 0 ) return null;

		const minMax = getMinMax( attribute, start, count );
		let bufferViewTarget;

		// If geometry isn't provided, don't infer the target usage of the bufferView. For
		// animation samplers, target must not be set.
		if ( geometry !== undefined ) {

			bufferViewTarget = attribute === geometry.index ? WEBGL_CONSTANTS.ELEMENT_ARRAY_BUFFER : WEBGL_CONSTANTS.ARRAY_BUFFER;

		}

		const bufferView = this.processBufferView( attribute, componentType, start, count, bufferViewTarget );

		const accessorDef = {

			bufferView: bufferView.id,
			byteOffset: bufferView.byteOffset,
			componentType: componentType,
			count: count,
			max: minMax.max,
			min: minMax.min,
			type: types[ attribute.itemSize ]

		};

		if ( attribute.normalized === true ) accessorDef.normalized = true;
		if ( ! json.accessors ) json.accessors = [];

		return json.accessors.push( accessorDef ) - 1;

	}

	/**
	 * Process image
	 * @param {Image} image to process
	 * @param {number} format Identifier of the format (RGBAFormat)
	 * @param {boolean} flipY before writing out the image
	 * @param {string} mimeType export format
	 * @return {number}     Index of the processed texture in the "images" array
	 */
	processImage( image, format, flipY, mimeType = 'image/png' ) {

		if ( image !== null ) {

			const writer = this;
			const cache = writer.cache;
			const json = writer.json;
			const options = writer.options;
			const pending = writer.pending;

			if ( ! cache.images.has( image ) ) cache.images.set( image, {} );

			const cachedImages = cache.images.get( image );

			const key = mimeType + ':flipY/' + flipY.toString();

			if ( cachedImages[ key ] !== undefined ) return cachedImages[ key ];

			if ( ! json.images ) json.images = [];

			const imageDef = { mimeType: mimeType };

			const canvas = getCanvas();

			canvas.width = Math.min( image.width, options.maxTextureSize );
			canvas.height = Math.min( image.height, options.maxTextureSize );

			const ctx = canvas.getContext( '2d', {
				willReadFrequently: true,
			} );

			if ( flipY === true ) {

				ctx.translate( 0, canvas.height );
				ctx.scale( 1, - 1 );

			}

			if ( image.data !== undefined ) { // THREE.DataTexture

				if ( format !== RGBAFormat ) {

					console.error( 'GLTFExporter: Only RGBAFormat is supported.', format );

				}

				if ( image.width > options.maxTextureSize || image.height > options.maxTextureSize ) {

					console.warn( 'GLTFExporter: Image size is bigger than maxTextureSize', image );

				}

				const data = new Uint8ClampedArray( image.height * image.width * 4 );

				for ( let i = 0; i < data.length; i += 4 ) {

					data[ i + 0 ] = image.data[ i + 0 ];
					data[ i + 1 ] = image.data[ i + 1 ];
					data[ i + 2 ] = image.data[ i + 2 ];
					data[ i + 3 ] = image.data[ i + 3 ];

				}

				ctx.putImageData( new ImageData( data, image.width, image.height ), 0, 0 );

			} else {

				if ( ( typeof HTMLImageElement !== 'undefined' && image instanceof HTMLImageElement ) ||
					( typeof HTMLCanvasElement !== 'undefined' && image instanceof HTMLCanvasElement ) ||
					( typeof ImageBitmap !== 'undefined' && image instanceof ImageBitmap ) ||
					( typeof OffscreenCanvas !== 'undefined' && image instanceof OffscreenCanvas ) ) {

					ctx.drawImage( image, 0, 0, canvas.width, canvas.height );

				} else {

					throw new Error( 'THREE.GLTFExporter: Invalid image type. Use HTMLImageElement, HTMLCanvasElement, ImageBitmap or OffscreenCanvas.' );

				}

			}

			if ( options.binary === true ) {

				pending.push(

					getToBlobPromise( canvas, mimeType )
						.then( blob => writer.processBufferViewImage( blob ) )
						.then( bufferViewIndex => {

							imageDef.bufferView = bufferViewIndex;

						} )

				);

			} else {

				imageDef.uri = ImageUtils.getDataURL( canvas, mimeType );

			}

			const index = json.images.push( imageDef ) - 1;
			cachedImages[ key ] = index;
			return index;

		} else {

			throw new Error( 'THREE.GLTFExporter: No valid image data found. Unable to process texture.' );

		}

	}

	/**
	 * Process sampler
	 * @param {Texture} map Texture to process
	 * @return {number}      Index of the processed texture in the "samplers" array
	 */
	processSampler( map ) {

		const json = this.json;

		if ( ! json.samplers ) json.samplers = [];

		const samplerDef = {
			magFilter: THREE_TO_WEBGL[ map.magFilter ],
			minFilter: THREE_TO_WEBGL[ map.minFilter ],
			wrapS: THREE_TO_WEBGL[ map.wrapS ],
			wrapT: THREE_TO_WEBGL[ map.wrapT ]
		};

		return json.samplers.push( samplerDef ) - 1;

	}

	/**
	 * Process texture
	 * @param {Texture} map Map to process
	 * @return {Promise<number>} Index of the processed texture in the "textures" array
	 */
	async processTextureAsync( map ) {

		const writer = this;
		const options = writer.options;
		const cache = this.cache;
		const json = this.json;

		if ( cache.textures.has( map ) ) return cache.textures.get( map );

		if ( ! json.textures ) json.textures = [];

		// make non-readable textures (e.g. CompressedTexture) readable by blitting them into a new texture
		if ( map instanceof CompressedTexture ) {

			map = await this.decompressTextureAsync( map, options.maxTextureSize );

		}

		let mimeType = map.userData.mimeType;

		if ( mimeType === 'image/webp' ) mimeType = 'image/png';

		const textureDef = {
			sampler: this.processSampler( map ),
			source: this.processImage( map.image, map.format, map.flipY, mimeType )
		};

		if ( map.name ) textureDef.name = map.name;

		await this._invokeAllAsync( async function ( ext ) {

			ext.writeTexture && await ext.writeTexture( map, textureDef );

		} );

		const index = json.textures.push( textureDef ) - 1;
		cache.textures.set( map, index );
		return index;

	}

	/**
	 * Process material
	 * @param {THREE.Material} material Material to process
	 * @return {Promise<number|null>} Index of the processed material in the "materials" array
	 */
	async processMaterialAsync( material ) {

		const cache = this.cache;
		const json = this.json;

		if ( cache.materials.has( material ) ) return cache.materials.get( material );

		if ( material.isShaderMaterial ) {

			console.warn( 'GLTFExporter: THREE.ShaderMaterial not supported.' );
			return null;

		}

		if ( ! json.materials ) json.materials = [];

		// @QUESTION Should we avoid including any attribute that has the default value?
		const materialDef = {	pbrMetallicRoughness: {} };

		if ( material.isMeshStandardMaterial !== true && material.isMeshBasicMaterial !== true ) {

			console.warn( 'GLTFExporter: Use MeshStandardMaterial or MeshBasicMaterial for best results.' );

		}

		// pbrMetallicRoughness.baseColorFactor
		const color = material.color.toArray().concat( [ material.opacity ] );

		if ( ! equalArray( color, [ 1, 1, 1, 1 ] ) ) {

			materialDef.pbrMetallicRoughness.baseColorFactor = color;

		}

		if ( material.isMeshStandardMaterial ) {

			materialDef.pbrMetallicRoughness.metallicFactor = material.metalness;
			materialDef.pbrMetallicRoughness.roughnessFactor = material.roughness;

		} else {

			materialDef.pbrMetallicRoughness.metallicFactor = 0;
			materialDef.pbrMetallicRoughness.roughnessFactor = 1;

		}

		// pbrMetallicRoughness.metallicRoughnessTexture
		if ( material.metalnessMap || material.roughnessMap ) {

			const metalRoughTexture = await this.buildMetalRoughTextureAsync( material.metalnessMap, material.roughnessMap );

			const metalRoughMapDef = {
				index: await this.processTextureAsync( metalRoughTexture ),
				texCoord: metalRoughTexture.channel
			};
			this.applyTextureTransform( metalRoughMapDef, metalRoughTexture );
			materialDef.pbrMetallicRoughness.metallicRoughnessTexture = metalRoughMapDef;

		}

		// pbrMetallicRoughness.baseColorTexture
		if ( material.map ) {

			const baseColorMapDef = {
				index: await this.processTextureAsync( material.map ),
				texCoord: material.map.channel
			};
			this.applyTextureTransform( baseColorMapDef, material.map );
			materialDef.pbrMetallicRoughness.baseColorTexture = baseColorMapDef;

		}

		if ( material.emissive ) {

			const emissive = material.emissive;
			const maxEmissiveComponent = Math.max( emissive.r, emissive.g, emissive.b );

			if ( maxEmissiveComponent > 0 ) {

				materialDef.emissiveFactor = material.emissive.toArray();

			}

			// emissiveTexture
			if ( material.emissiveMap ) {

				const emissiveMapDef = {
					index: await this.processTextureAsync( material.emissiveMap ),
					texCoord: material.emissiveMap.channel
				};
				this.applyTextureTransform( emissiveMapDef, material.emissiveMap );
				materialDef.emissiveTexture = emissiveMapDef;

			}

		}

		// normalTexture
		if ( material.normalMap ) {

			const normalMapDef = {
				index: await this.processTextureAsync( material.normalMap ),
				texCoord: material.normalMap.channel
			};

			if ( material.normalScale && material.normalScale.x !== 1 ) {

				// glTF normal scale is univariate. Ignore `y`, which may be flipped.
				// Context: https://github.com/mrdoob/three.js/issues/11438#issuecomment-507003995
				normalMapDef.scale = material.normalScale.x;

			}

			this.applyTextureTransform( normalMapDef, material.normalMap );
			materialDef.normalTexture = normalMapDef;

		}

		// occlusionTexture
		if ( material.aoMap ) {

			const occlusionMapDef = {
				index: await this.processTextureAsync( material.aoMap ),
				texCoord: material.aoMap.channel
			};

			if ( material.aoMapIntensity !== 1.0 ) {

				occlusionMapDef.strength = material.aoMapIntensity;

			}

			this.applyTextureTransform( occlusionMapDef, material.aoMap );
			materialDef.occlusionTexture = occlusionMapDef;

		}

		// alphaMode
		if ( material.transparent ) {

			materialDef.alphaMode = 'BLEND';

		} else {

			if ( material.alphaTest > 0.0 ) {

				materialDef.alphaMode = 'MASK';
				materialDef.alphaCutoff = material.alphaTest;

			}

		}

		// doubleSided
		if ( material.side === DoubleSide ) materialDef.doubleSided = true;
		if ( material.name !== '' ) materialDef.name = material.name;

		this.serializeUserData( material, materialDef );

		await this._invokeAllAsync( async function ( ext ) {

			ext.writeMaterialAsync && await ext.writeMaterialAsync( material, materialDef );

		} );

		const index = json.materials.push( materialDef ) - 1;
		cache.materials.set( material, index );
		return index;

	}

	/**
	 * Process mesh
	 * @param {THREE.Mesh} mesh Mesh to process
	 * @return {Promise<number|null>} Index of the processed mesh in the "meshes" array
	 */
	async processMeshAsync( mesh ) {

		const cache = this.cache;
		const json = this.json;

		const meshCacheKeyParts = [ mesh.geometry.uuid ];

		if ( Array.isArray( mesh.material ) ) {

			for ( let i = 0, l = mesh.material.length; i < l; i ++ ) {

				meshCacheKeyParts.push( mesh.material[ i ].uuid	);

			}

		} else {

			meshCacheKeyParts.push( mesh.material.uuid );

		}

		const meshCacheKey = meshCacheKeyParts.join( ':' );

		if ( cache.meshes.has( meshCacheKey ) ) return cache.meshes.get( meshCacheKey );

		const geometry = mesh.geometry;

		let mode;

		// Use the correct mode
		if ( mesh.isLineSegments ) {

			mode = WEBGL_CONSTANTS.LINES;

		} else if ( mesh.isLineLoop ) {

			mode = WEBGL_CONSTANTS.LINE_LOOP;

		} else if ( mesh.isLine ) {

			mode = WEBGL_CONSTANTS.LINE_STRIP;

		} else if ( mesh.isPoints ) {

			mode = WEBGL_CONSTANTS.POINTS;

		} else {

			mode = mesh.material.wireframe ? WEBGL_CONSTANTS.LINES : WEBGL_CONSTANTS.TRIANGLES;

		}

		const meshDef = {};
		const attributes = {};
		const primitives = [];
		const targets = [];

		// Conversion between attributes names in threejs and gltf spec
		const nameConversion = {
			uv: 'TEXCOORD_0',
			uv1: 'TEXCOORD_1',
			uv2: 'TEXCOORD_2',
			uv3: 'TEXCOORD_3',
			color: 'COLOR_0',
			skinWeight: 'WEIGHTS_0',
			skinIndex: 'JOINTS_0'
		};

		const originalNormal = geometry.getAttribute( 'normal' );

		if ( originalNormal !== undefined && ! this.isNormalizedNormalAttribute( originalNormal ) ) {

			console.warn( 'THREE.GLTFExporter: Creating normalized normal attribute from the non-normalized one.' );

			geometry.setAttribute( 'normal', this.createNormalizedNormalAttribute( originalNormal ) );

		}

		// @QUESTION Detect if .vertexColors = true?
		// For every attribute create an accessor
		let modifiedAttribute = null;

		for ( let attributeName in geometry.attributes ) {

			// Ignore morph target attributes, which are exported later.
			if ( attributeName.slice( 0, 5 ) === 'morph' ) continue;

			const attribute = geometry.attributes[ attributeName ];
			attributeName = nameConversion[ attributeName ] || attributeName.toUpperCase();

			// Prefix all geometry attributes except the ones specifically
			// listed in the spec; non-spec attributes are considered custom.
			const validVertexAttributes =
					/^(POSITION|NORMAL|TANGENT|TEXCOORD_\d+|COLOR_\d+|JOINTS_\d+|WEIGHTS_\d+)$/;

			if ( ! validVertexAttributes.test( attributeName ) ) attributeName = '_' + attributeName;

			if ( cache.attributes.has( this.getUID( attribute ) ) ) {

				attributes[ attributeName ] = cache.attributes.get( this.getUID( attribute ) );
				continue;

			}

			// Enforce glTF vertex attribute requirements:
			// - JOINTS_0 must be UNSIGNED_BYTE or UNSIGNED_SHORT
			// - Only custom attributes may be INT or UNSIGNED_INT
			modifiedAttribute = null;
			const array = attribute.array;

			if ( attributeName === 'JOINTS_0' &&
				! ( array instanceof Uint16Array ) &&
				! ( array instanceof Uint8Array ) ) {

				console.warn( 'GLTFExporter: Attribute "skinIndex" converted to type UNSIGNED_SHORT.' );
				modifiedAttribute = new BufferAttribute( new Uint16Array( array ), attribute.itemSize, attribute.normalized );

			} else if ( ( array instanceof Uint32Array || array instanceof Int32Array ) && ! attributeName.startsWith( '_' ) ) {

				console.warn( `GLTFExporter: Attribute "${ attributeName }" converted to type FLOAT.` );
				modifiedAttribute = GLTFExporter.Utils.toFloat32BufferAttribute( attribute );

			}

			const accessor = this.processAccessor( modifiedAttribute || attribute, geometry );

			if ( accessor !== null ) {

				if ( ! attributeName.startsWith( '_' ) ) {

					this.detectMeshQuantization( attributeName, attribute );

				}

				attributes[ attributeName ] = accessor;
				cache.attributes.set( this.getUID( attribute ), accessor );

			}

		}

		if ( originalNormal !== undefined ) geometry.setAttribute( 'normal', originalNormal );

		// Skip if no exportable attributes found
		if ( Object.keys( attributes ).length === 0 ) return null;

		// Morph targets
		if ( mesh.morphTargetInfluences !== undefined && mesh.morphTargetInfluences.length > 0 ) {

			const weights = [];
			const targetNames = [];
			const reverseDictionary = {};

			if ( mesh.morphTargetDictionary !== undefined ) {

				for ( const key in mesh.morphTargetDictionary ) {

					reverseDictionary[ mesh.morphTargetDictionary[ key ] ] = key;

				}

			}

			for ( let i = 0; i < mesh.morphTargetInfluences.length; ++ i ) {

				const target = {};
				let warned = false;

				for ( const attributeName in geometry.morphAttributes ) {

					// glTF 2.0 morph supports only POSITION/NORMAL/TANGENT.
					// Three.js doesn't support TANGENT yet.

					if ( attributeName !== 'position' && attributeName !== 'normal' ) {

						if ( ! warned ) {

							console.warn( 'GLTFExporter: Only POSITION and NORMAL morph are supported.' );
							warned = true;

						}

						continue;

					}

					const attribute = geometry.morphAttributes[ attributeName ][ i ];
					const gltfAttributeName = attributeName.toUpperCase();

					// Three.js morph attribute has absolute values while the one of glTF has relative values.
					//
					// glTF 2.0 Specification:
					// https://github.com/KhronosGroup/glTF/tree/master/specification/2.0#morph-targets

					const baseAttribute = geometry.attributes[ attributeName ];

					if ( cache.attributes.has( this.getUID( attribute, true ) ) ) {

						target[ gltfAttributeName ] = cache.attributes.get( this.getUID( attribute, true ) );
						continue;

					}

					// Clones attribute not to override
					const relativeAttribute = attribute.clone();

					if ( ! geometry.morphTargetsRelative ) {

						for ( let j = 0, jl = attribute.count; j < jl; j ++ ) {

							for ( let a = 0; a < attribute.itemSize; a ++ ) {

								if ( a === 0 ) relativeAttribute.setX( j, attribute.getX( j ) - baseAttribute.getX( j ) );
								if ( a === 1 ) relativeAttribute.setY( j, attribute.getY( j ) - baseAttribute.getY( j ) );
								if ( a === 2 ) relativeAttribute.setZ( j, attribute.getZ( j ) - baseAttribute.getZ( j ) );
								if ( a === 3 ) relativeAttribute.setW( j, attribute.getW( j ) - baseAttribute.getW( j ) );

							}

						}

					}

					target[ gltfAttributeName ] = this.processAccessor( relativeAttribute, geometry );
					cache.attributes.set( this.getUID( baseAttribute, true ), target[ gltfAttributeName ] );

				}

				targets.push( target );

				weights.push( mesh.morphTargetInfluences[ i ] );

				if ( mesh.morphTargetDictionary !== undefined ) targetNames.push( reverseDictionary[ i ] );

			}

			meshDef.weights = weights;

			if ( targetNames.length > 0 ) {

				meshDef.extras = {};
				meshDef.extras.targetNames = targetNames;

			}

		}

		const isMultiMaterial = Array.isArray( mesh.material );

		if ( isMultiMaterial && geometry.groups.length === 0 ) return null;

		let didForceIndices = false;

		if ( isMultiMaterial && geometry.index === null ) {

			const indices = [];

			for ( let i = 0, il = geometry.attributes.position.count; i < il; i ++ ) {

				indices[ i ] = i;

			}

			geometry.setIndex( indices );

			didForceIndices = true;

		}

		const materials = isMultiMaterial ? mesh.material : [ mesh.material ];
		const groups = isMultiMaterial ? geometry.groups : [ { materialIndex: 0, start: undefined, count: undefined } ];

		for ( let i = 0, il = groups.length; i < il; i ++ ) {

			const primitive = {
				mode: mode,
				attributes: attributes,
			};

			this.serializeUserData( geometry, primitive );

			if ( targets.length > 0 ) primitive.targets = targets;

			if ( geometry.index !== null ) {

				let cacheKey = this.getUID( geometry.index );

				if ( groups[ i ].start !== undefined || groups[ i ].count !== undefined ) {

					cacheKey += ':' + groups[ i ].start + ':' + groups[ i ].count;

				}

				if ( cache.attributes.has( cacheKey ) ) {

					primitive.indices = cache.attributes.get( cacheKey );

				} else {

					primitive.indices = this.processAccessor( geometry.index, geometry, groups[ i ].start, groups[ i ].count );
					cache.attributes.set( cacheKey, primitive.indices );

				}

				if ( primitive.indices === null ) delete primitive.indices;

			}

			const material = await this.processMaterialAsync( materials[ groups[ i ].materialIndex ] );

			if ( material !== null ) primitive.material = material;

			primitives.push( primitive );

		}

		if ( didForceIndices === true ) {

			geometry.setIndex( null );

		}

		meshDef.primitives = primitives;

		if ( ! json.meshes ) json.meshes = [];

		await this._invokeAllAsync( function ( ext ) {

			ext.writeMesh && ext.writeMesh( mesh, meshDef );

		} );

		const index = json.meshes.push( meshDef ) - 1;
		cache.meshes.set( meshCacheKey, index );
		return index;

	}

	/**
	 * If a vertex attribute with a
	 * [non-standard data type](https://registry.khronos.org/glTF/specs/2.0/glTF-2.0.html#meshes-overview)
	 * is used, it is checked whether it is a valid data type according to the
	 * [KHR_mesh_quantization](https://github.com/KhronosGroup/glTF/blob/main/extensions/2.0/Khronos/KHR_mesh_quantization/README.md)
	 * extension.
	 * In this case the extension is automatically added to the list of used extensions.
	 *
	 * @param {string} attributeName
	 * @param {THREE.BufferAttribute} attribute
	 */
	detectMeshQuantization( attributeName, attribute ) {

		if ( this.extensionsUsed[ KHR_MESH_QUANTIZATION ] ) return;

		let attrType = undefined;

		switch ( attribute.array.constructor ) {

			case Int8Array:

				attrType = 'byte';

				break;

			case Uint8Array:

				attrType = 'unsigned byte';

				break;

			case Int16Array:

				attrType = 'short';

				break;

			case Uint16Array:

				attrType = 'unsigned short';

				break;

			default:

				return;

		}

		if ( attribute.normalized ) attrType += ' normalized';

		const attrNamePrefix = attributeName.split( '_', 1 )[ 0 ];

		if ( KHR_mesh_quantization_ExtraAttrTypes[ attrNamePrefix ] && KHR_mesh_quantization_ExtraAttrTypes[ attrNamePrefix ].includes( attrType ) ) {

			this.extensionsUsed[ KHR_MESH_QUANTIZATION ] = true;
			this.extensionsRequired[ KHR_MESH_QUANTIZATION ] = true;

		}

	}

	/**
	 * Process camera
	 * @param {THREE.Camera} camera Camera to process
	 * @return {number} Index of the processed mesh in the "camera" array
	 */
	processCamera( camera ) {

		const json = this.json;

		if ( ! json.cameras ) json.cameras = [];

		const isOrtho = camera.isOrthographicCamera;

		const cameraDef = {
			type: isOrtho ? 'orthographic' : 'perspective'
		};

		if ( isOrtho ) {

			cameraDef.orthographic = {
				xmag: camera.right * 2,
				ymag: camera.top * 2,
				zfar: camera.far <= 0 ? 0.001 : camera.far,
				znear: camera.near < 0 ? 0 : camera.near
			};

		} else {

			cameraDef.perspective = {
				aspectRatio: camera.aspect,
				yfov: MathUtils.degToRad( camera.fov ),
				zfar: camera.far <= 0 ? 0.001 : camera.far,
				znear: camera.near < 0 ? 0 : camera.near
			};

		}

		// Question: Is saving "type" as name intentional?
		if ( camera.name !== '' ) cameraDef.name = camera.type;

		return json.cameras.push( cameraDef ) - 1;

	}

	/**
	 * Creates glTF animation entry from AnimationClip object.
	 *
	 * Status:
	 * - Only properties listed in PATH_PROPERTIES may be animated.
	 *
	 * @param {THREE.AnimationClip} clip
	 * @param {THREE.Object3D} root
	 * @return {number|null}
	 */
	processAnimation( clip, root ) {

		const json = this.json;
		const nodeMap = this.nodeMap;

		if ( ! json.animations ) json.animations = [];

		clip = GLTFExporter.Utils.mergeMorphTargetTracks( clip.clone(), root );

		const tracks = clip.tracks;
		const channels = [];
		const samplers = [];

		for ( let i = 0; i < tracks.length; ++ i ) {

			const track = tracks[ i ];
			const trackBinding = PropertyBinding.parseTrackName( track.name );
			let trackNode = PropertyBinding.findNode( root, trackBinding.nodeName );
			const trackProperty = PATH_PROPERTIES[ trackBinding.propertyName ];

			if ( trackBinding.objectName === 'bones' ) {

				if ( trackNode.isSkinnedMesh === true ) {

					trackNode = trackNode.skeleton.getBoneByName( trackBinding.objectIndex );

				} else {

					trackNode = undefined;

				}

			}

			if ( ! trackNode || ! trackProperty ) {

				console.warn( 'THREE.GLTFExporter: Could not export animation track "%s".', track.name );
				continue;

			}

			const inputItemSize = 1;
			let outputItemSize = track.values.length / track.times.length;

			if ( trackProperty === PATH_PROPERTIES.morphTargetInfluences ) {

				outputItemSize /= trackNode.morphTargetInfluences.length;

			}

			let interpolation;

			// @TODO export CubicInterpolant(InterpolateSmooth) as CUBICSPLINE

			// Detecting glTF cubic spline interpolant by checking factory method's special property
			// GLTFCubicSplineInterpolant is a custom interpolant and track doesn't return
			// valid value from .getInterpolation().
			if ( track.createInterpolant.isInterpolantFactoryMethodGLTFCubicSpline === true ) {

				interpolation = 'CUBICSPLINE';

				// itemSize of CUBICSPLINE keyframe is 9
				// (VEC3 * 3: inTangent, splineVertex, and outTangent)
				// but needs to be stored as VEC3 so dividing by 3 here.
				outputItemSize /= 3;

			} else if ( track.getInterpolation() === InterpolateDiscrete ) {

				interpolation = 'STEP';

			} else {

				interpolation = 'LINEAR';

			}

			samplers.push( {
				input: this.processAccessor( new BufferAttribute( track.times, inputItemSize ) ),
				output: this.processAccessor( new BufferAttribute( track.values, outputItemSize ) ),
				interpolation: interpolation
			} );

			channels.push( {
				sampler: samplers.length - 1,
				target: {
					node: nodeMap.get( trackNode ),
					path: trackProperty
				}
			} );

		}

		json.animations.push( {
			name: clip.name || 'clip_' + json.animations.length,
			samplers: samplers,
			channels: channels
		} );

		return json.animations.length - 1;

	}

	/**
	 * @param {THREE.Object3D} object
	 * @return {number|null}
	 */
	 processSkin( object ) {

		const json = this.json;
		const nodeMap = this.nodeMap;

		const node = json.nodes[ nodeMap.get( object ) ];

		const skeleton = object.skeleton;

		if ( skeleton === undefined ) return null;

		const rootJoint = object.skeleton.bones[ 0 ];

		if ( rootJoint === undefined ) return null;

		const joints = [];
		const inverseBindMatrices = new Float32Array( skeleton.bones.length * 16 );
		const temporaryBoneInverse = new Matrix4();

		for ( let i = 0; i < skeleton.bones.length; ++ i ) {

			joints.push( nodeMap.get( skeleton.bones[ i ] ) );
			temporaryBoneInverse.copy( skeleton.boneInverses[ i ] );
			temporaryBoneInverse.multiply( object.bindMatrix ).toArray( inverseBindMatrices, i * 16 );

		}

		if ( json.skins === undefined ) json.skins = [];

		json.skins.push( {
			inverseBindMatrices: this.processAccessor( new BufferAttribute( inverseBindMatrices, 16 ) ),
			joints: joints,
			skeleton: nodeMap.get( rootJoint )
		} );

		const skinIndex = node.skin = json.skins.length - 1;

		return skinIndex;

	}

	/**
	 * Process Object3D node
	 * @param {THREE.Object3D} object Object3D to processNodeAsync
	 * @return {Promise<number>} Index of the node in the nodes list
	 */
	async processNodeAsync( object ) {

		const json = this.json;
		const options = this.options;
		const nodeMap = this.nodeMap;

		if ( ! json.nodes ) json.nodes = [];

		const nodeDef = {};

		if ( options.trs ) {

			const rotation = object.quaternion.toArray();
			const position = object.position.toArray();
			const scale = object.scale.toArray();

			if ( ! equalArray( rotation, [ 0, 0, 0, 1 ] ) ) {

				nodeDef.rotation = rotation;

			}

			if ( ! equalArray( position, [ 0, 0, 0 ] ) ) {

				nodeDef.translation = position;

			}

			if ( ! equalArray( scale, [ 1, 1, 1 ] ) ) {

				nodeDef.scale = scale;

			}

		} else {

			if ( object.matrixAutoUpdate ) {

				object.updateMatrix();

			}

			if ( isIdentityMatrix( object.matrix ) === false ) {

				nodeDef.matrix = object.matrix.elements;

			}

		}

		// We don't export empty strings name because it represents no-name in Three.js.
		if ( object.name !== '' ) nodeDef.name = String( object.name );

		this.serializeUserData( object, nodeDef );

		if ( object.isMesh || object.isLine || object.isPoints ) {

			const meshIndex = await this.processMeshAsync( object );

			if ( meshIndex !== null ) nodeDef.mesh = meshIndex;

		} else if ( object.isCamera ) {

			nodeDef.camera = this.processCamera( object );

		}

		if ( object.isSkinnedMesh ) this.skins.push( object );

		const nodeIndex = json.nodes.push( nodeDef ) - 1;
		nodeMap.set( object, nodeIndex );

		if ( object.children.length > 0 ) {

			const children = [];

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				const child = object.children[ i ];

				if ( child.visible || options.onlyVisible === false ) {

					const childNodeIndex = await this.processNodeAsync( child );

					if ( childNodeIndex !== null ) children.push( childNodeIndex );

				}

			}

			if ( children.length > 0 ) nodeDef.children = children;

		}

		await this._invokeAllAsync( function ( ext ) {

			ext.writeNode && ext.writeNode( object, nodeDef );

		} );

		return nodeIndex;

	}

	/**
	 * Process Scene
	 * @param {Scene} scene Scene to process
	 */
	async processSceneAsync( scene ) {

		const json = this.json;
		const options = this.options;

		if ( ! json.scenes ) {

			json.scenes = [];
			json.scene = 0;

		}

		const sceneDef = {};

		if ( scene.name !== '' ) sceneDef.name = scene.name;

		json.scenes.push( sceneDef );

		const nodes = [];

		for ( let i = 0, l = scene.children.length; i < l; i ++ ) {

			const child = scene.children[ i ];

			if ( child.visible || options.onlyVisible === false ) {

				const nodeIndex = await this.processNodeAsync( child );

				if ( nodeIndex !== null ) nodes.push( nodeIndex );

			}

		}

		if ( nodes.length > 0 ) sceneDef.nodes = nodes;

		this.serializeUserData( scene, sceneDef );

	}

	/**
	 * Creates a Scene to hold a list of objects and parse it
	 * @param {Array<THREE.Object3D>} objects List of objects to process
	 */
	async processObjectsAsync( objects ) {

		const scene = new Scene();
		scene.name = 'AuxScene';

		for ( let i = 0; i < objects.length; i ++ ) {

			// We push directly to children instead of calling `add` to prevent
			// modify the .parent and break its original scene and hierarchy
			scene.children.push( objects[ i ] );

		}

		await this.processSceneAsync( scene );

	}

	/**
	 * @param {THREE.Object3D|Array<THREE.Object3D>} input
	 */
	async processInputAsync( input ) {

		const options = this.options;

		input = input instanceof Array ? input : [ input ];

		await this._invokeAllAsync( function ( ext ) {

			ext.beforeParse && ext.beforeParse( input );

		} );

		const objectsWithoutScene = [];

		for ( let i = 0; i < input.length; i ++ ) {

			if ( input[ i ] instanceof Scene ) {

				await this.processSceneAsync( input[ i ] );

			} else {

				objectsWithoutScene.push( input[ i ] );

			}

		}

		if ( objectsWithoutScene.length > 0 ) {

			await this.processObjectsAsync( objectsWithoutScene );

		}

		for ( let i = 0; i < this.skins.length; ++ i ) {

			this.processSkin( this.skins[ i ] );

		}

		for ( let i = 0; i < options.animations.length; ++ i ) {

			this.processAnimation( options.animations[ i ], input[ 0 ] );

		}

		await this._invokeAllAsync( function ( ext ) {

			ext.afterParse && ext.afterParse( input );

		} );

	}

	async _invokeAllAsync( func ) {

		for ( let i = 0, il = this.plugins.length; i < il; i ++ ) {

			await func( this.plugins[ i ] );

		}

	}

}
```
</details>

#### Methods

##### `setPlugins(plugins: any): void`

<details><summary>Code</summary>

```ts
setPlugins( plugins ) {

		this.plugins = plugins;

	}
```
</details>

##### `setTextureUtils(utils: any): void`

<details><summary>Code</summary>

```ts
setTextureUtils( utils ) {

		this.textureUtils = utils;

	}
```
</details>

##### `writeAsync(input: any, onDone: Function, options: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeAsync( input, onDone, options = {} ) {

		this.options = Object.assign( {
			// default options
			binary: false,
			trs: false,
			onlyVisible: true,
			maxTextureSize: Infinity,
			animations: [],
			includeCustomExtensions: false
		}, options );

		if ( this.options.animations.length > 0 ) {

			// Only TRS properties, and not matrices, may be targeted by animation.
			this.options.trs = true;

		}

		await this.processInputAsync( input );

		await Promise.all( this.pending );

		const writer = this;
		const buffers = writer.buffers;
		const json = writer.json;
		options = writer.options;

		const extensionsUsed = writer.extensionsUsed;
		const extensionsRequired = writer.extensionsRequired;

		// Merge buffers.
		const blob = new Blob( buffers, { type: 'application/octet-stream' } );

		// Declare extensions.
		const extensionsUsedList = Object.keys( extensionsUsed );
		const extensionsRequiredList = Object.keys( extensionsRequired );

		if ( extensionsUsedList.length > 0 ) json.extensionsUsed = extensionsUsedList;
		if ( extensionsRequiredList.length > 0 ) json.extensionsRequired = extensionsRequiredList;

		// Update bytelength of the single buffer.
		if ( json.buffers && json.buffers.length > 0 ) json.buffers[ 0 ].byteLength = blob.size;

		if ( options.binary === true ) {

			// https://github.com/KhronosGroup/glTF/blob/master/specification/2.0/README.md#glb-file-format-specification

			const reader = new FileReader();
			reader.readAsArrayBuffer( blob );
			reader.onloadend = function () {

				// Binary chunk.
				const binaryChunk = getPaddedArrayBuffer( reader.result );
				const binaryChunkPrefix = new DataView( new ArrayBuffer( GLB_CHUNK_PREFIX_BYTES ) );
				binaryChunkPrefix.setUint32( 0, binaryChunk.byteLength, true );
				binaryChunkPrefix.setUint32( 4, GLB_CHUNK_TYPE_BIN, true );

				// JSON chunk.
				const jsonChunk = getPaddedArrayBuffer( stringToArrayBuffer( JSON.stringify( json ) ), 0x20 );
				const jsonChunkPrefix = new DataView( new ArrayBuffer( GLB_CHUNK_PREFIX_BYTES ) );
				jsonChunkPrefix.setUint32( 0, jsonChunk.byteLength, true );
				jsonChunkPrefix.setUint32( 4, GLB_CHUNK_TYPE_JSON, true );

				// GLB header.
				const header = new ArrayBuffer( GLB_HEADER_BYTES );
				const headerView = new DataView( header );
				headerView.setUint32( 0, GLB_HEADER_MAGIC, true );
				headerView.setUint32( 4, GLB_VERSION, true );
				const totalByteLength = GLB_HEADER_BYTES
					+ jsonChunkPrefix.byteLength + jsonChunk.byteLength
					+ binaryChunkPrefix.byteLength + binaryChunk.byteLength;
				headerView.setUint32( 8, totalByteLength, true );

				const glbBlob = new Blob( [
					header,
					jsonChunkPrefix,
					jsonChunk,
					binaryChunkPrefix,
					binaryChunk
				], { type: 'application/octet-stream' } );

				const glbReader = new FileReader();
				glbReader.readAsArrayBuffer( glbBlob );
				glbReader.onloadend = function () {

					onDone( glbReader.result );

				};

			};

		} else {

			if ( json.buffers && json.buffers.length > 0 ) {

				const reader = new FileReader();
				reader.readAsDataURL( blob );
				reader.onloadend = function () {

					const base64data = reader.result;
					json.buffers[ 0 ].uri = base64data;
					onDone( json );

				};

			} else {

				onDone( json );

			}

		}


	}
```
</details>

##### `serializeUserData(object: any, objectDef: any): void`

<details><summary>Code</summary>

```ts
serializeUserData( object, objectDef ) {

		if ( Object.keys( object.userData ).length === 0 ) return;

		const options = this.options;
		const extensionsUsed = this.extensionsUsed;

		try {

			const json = JSON.parse( JSON.stringify( object.userData ) );

			if ( options.includeCustomExtensions && json.gltfExtensions ) {

				if ( objectDef.extensions === undefined ) objectDef.extensions = {};

				for ( const extensionName in json.gltfExtensions ) {

					objectDef.extensions[ extensionName ] = json.gltfExtensions[ extensionName ];
					extensionsUsed[ extensionName ] = true;

				}

				delete json.gltfExtensions;

			}

			if ( Object.keys( json ).length > 0 ) objectDef.extras = json;

		} catch ( error ) {

			console.warn( 'THREE.GLTFExporter: userData of \'' + object.name + '\' ' +
				'won\'t be serialized because of JSON.stringify error - ' + error.message );

		}

	}
```
</details>

##### `getUID(attribute: any, isRelativeCopy: boolean): number`

<details><summary>Code</summary>

```ts
getUID( attribute, isRelativeCopy = false ) {

		if ( this.uids.has( attribute ) === false ) {

			const uids = new Map();

			uids.set( true, this.uid ++ );
			uids.set( false, this.uid ++ );

			this.uids.set( attribute, uids );

		}

		const uids = this.uids.get( attribute );

		return uids.get( isRelativeCopy );

	}
```
</details>

##### `isNormalizedNormalAttribute(normal: BufferAttribute): boolean`

<details><summary>Code</summary>

```ts
isNormalizedNormalAttribute( normal ) {

		const cache = this.cache;

		if ( cache.attributesNormalized.has( normal ) ) return false;

		const v = new Vector3();

		for ( let i = 0, il = normal.count; i < il; i ++ ) {

			// 0.0005 is from glTF-validator
			if ( Math.abs( v.fromBufferAttribute( normal, i ).length() - 1.0 ) > 0.0005 ) return false;

		}

		return true;

	}
```
</details>

##### `createNormalizedNormalAttribute(normal: BufferAttribute): BufferAttribute`

<details><summary>Code</summary>

```ts
createNormalizedNormalAttribute( normal ) {

		const cache = this.cache;

		if ( cache.attributesNormalized.has( normal ) )	return cache.attributesNormalized.get( normal );

		const attribute = normal.clone();
		const v = new Vector3();

		for ( let i = 0, il = attribute.count; i < il; i ++ ) {

			v.fromBufferAttribute( attribute, i );

			if ( v.x === 0 && v.y === 0 && v.z === 0 ) {

				// if values can't be normalized set (1, 0, 0)
				v.setX( 1.0 );

			} else {

				v.normalize();

			}

			attribute.setXYZ( i, v.x, v.y, v.z );

		}

		cache.attributesNormalized.set( normal, attribute );

		return attribute;

	}
```
</details>

##### `applyTextureTransform(mapDef: any, texture: THREE.Texture): void`

<details><summary>Code</summary>

```ts
applyTextureTransform( mapDef, texture ) {

		let didTransform = false;
		const transformDef = {};

		if ( texture.offset.x !== 0 || texture.offset.y !== 0 ) {

			transformDef.offset = texture.offset.toArray();
			didTransform = true;

		}

		if ( texture.rotation !== 0 ) {

			transformDef.rotation = texture.rotation;
			didTransform = true;

		}

		if ( texture.repeat.x !== 1 || texture.repeat.y !== 1 ) {

			transformDef.scale = texture.repeat.toArray();
			didTransform = true;

		}

		if ( didTransform ) {

			mapDef.extensions = mapDef.extensions || {};
			mapDef.extensions[ 'KHR_texture_transform' ] = transformDef;
			this.extensionsUsed[ 'KHR_texture_transform' ] = true;

		}

	}
```
</details>

##### `buildMetalRoughTextureAsync(metalnessMap: any, roughnessMap: any): Promise<any>`

<details><summary>Code</summary>

```ts
async buildMetalRoughTextureAsync( metalnessMap, roughnessMap ) {

		if ( metalnessMap === roughnessMap ) return metalnessMap;

		function getEncodingConversion( map ) {

			if ( map.colorSpace === SRGBColorSpace ) {

				return function SRGBToLinear( c ) {

					return ( c < 0.04045 ) ? c * 0.0773993808 : Math.pow( c * 0.9478672986 + 0.0521327014, 2.4 );

				};

			}

			return function LinearToLinear( c ) {

				return c;

			};

		}

		if ( metalnessMap instanceof CompressedTexture ) {

			metalnessMap = await this.decompressTextureAsync( metalnessMap );

		}

		if ( roughnessMap instanceof CompressedTexture ) {

			roughnessMap = await this.decompressTextureAsync( roughnessMap );

		}

		const metalness = metalnessMap ? metalnessMap.image : null;
		const roughness = roughnessMap ? roughnessMap.image : null;

		const width = Math.max( metalness ? metalness.width : 0, roughness ? roughness.width : 0 );
		const height = Math.max( metalness ? metalness.height : 0, roughness ? roughness.height : 0 );

		const canvas = getCanvas();
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d', {
			willReadFrequently: true,
		} );
		context.fillStyle = '#00ffff';
		context.fillRect( 0, 0, width, height );

		const composite = context.getImageData( 0, 0, width, height );

		if ( metalness ) {

			context.drawImage( metalness, 0, 0, width, height );

			const convert = getEncodingConversion( metalnessMap );
			const data = context.getImageData( 0, 0, width, height ).data;

			for ( let i = 2; i < data.length; i += 4 ) {

				composite.data[ i ] = convert( data[ i ] / 256 ) * 256;

			}

		}

		if ( roughness ) {

			context.drawImage( roughness, 0, 0, width, height );

			const convert = getEncodingConversion( roughnessMap );
			const data = context.getImageData( 0, 0, width, height ).data;

			for ( let i = 1; i < data.length; i += 4 ) {

				composite.data[ i ] = convert( data[ i ] / 256 ) * 256;

			}

		}

		context.putImageData( composite, 0, 0 );

		//

		const reference = metalnessMap || roughnessMap;

		const texture = reference.clone();

		texture.source = new Source( canvas );
		texture.colorSpace = NoColorSpace;
		texture.channel = ( metalnessMap || roughnessMap ).channel;

		if ( metalnessMap && roughnessMap && metalnessMap.channel !== roughnessMap.channel ) {

			console.warn( 'THREE.GLTFExporter: UV channels for metalnessMap and roughnessMap textures must match.' );

		}

		console.warn( 'THREE.GLTFExporter: Merged metalnessMap and roughnessMap textures.' );

		return texture;

	}
```
</details>

##### `decompressTextureAsync(texture: any, maxTextureSize: number): Promise<any>`

<details><summary>Code</summary>

```ts
async decompressTextureAsync( texture, maxTextureSize = Infinity ) {

		if ( this.textureUtils === null ) {

			throw new Error( 'THREE.GLTFExporter: setTextureUtils() must be called to process compressed textures.' );

		}

		return await this.textureUtils.decompress( texture, maxTextureSize );

	}
```
</details>

##### `processBuffer(buffer: ArrayBuffer): 0`

<details><summary>Code</summary>

```ts
processBuffer( buffer ) {

		const json = this.json;
		const buffers = this.buffers;

		if ( ! json.buffers ) json.buffers = [ { byteLength: 0 } ];

		// All buffers are merged before export.
		buffers.push( buffer );

		return 0;

	}
```
</details>

##### `processBufferView(attribute: BufferAttribute, componentType: number, start: number, count: number, target: number): any`

<details><summary>Code</summary>

```ts
processBufferView( attribute, componentType, start, count, target ) {

		const json = this.json;

		if ( ! json.bufferViews ) json.bufferViews = [];

		// Create a new dataview and dump the attribute's array into it

		let componentSize;

		switch ( componentType ) {

			case WEBGL_CONSTANTS.BYTE:
			case WEBGL_CONSTANTS.UNSIGNED_BYTE:

				componentSize = 1;

				break;

			case WEBGL_CONSTANTS.SHORT:
			case WEBGL_CONSTANTS.UNSIGNED_SHORT:

				componentSize = 2;

				break;

			default:

				componentSize = 4;

		}

		let byteStride = attribute.itemSize * componentSize;

		if ( target === WEBGL_CONSTANTS.ARRAY_BUFFER ) {

			// Each element of a vertex attribute MUST be aligned to 4-byte boundaries
			// inside a bufferView
			byteStride = Math.ceil( byteStride / 4 ) * 4;

		}

		const byteLength = getPaddedBufferSize( count * byteStride );
		const dataView = new DataView( new ArrayBuffer( byteLength ) );
		let offset = 0;

		for ( let i = start; i < start + count; i ++ ) {

			for ( let a = 0; a < attribute.itemSize; a ++ ) {

				let value;

				if ( attribute.itemSize > 4 ) {

					 // no support for interleaved data for itemSize > 4

					value = attribute.array[ i * attribute.itemSize + a ];

				} else {

					if ( a === 0 ) value = attribute.getX( i );
					else if ( a === 1 ) value = attribute.getY( i );
					else if ( a === 2 ) value = attribute.getZ( i );
					else if ( a === 3 ) value = attribute.getW( i );

					if ( attribute.normalized === true ) {

						value = MathUtils.normalize( value, attribute.array );

					}

				}

				if ( componentType === WEBGL_CONSTANTS.FLOAT ) {

					dataView.setFloat32( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.INT ) {

					dataView.setInt32( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.UNSIGNED_INT ) {

					dataView.setUint32( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.SHORT ) {

					dataView.setInt16( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.UNSIGNED_SHORT ) {

					dataView.setUint16( offset, value, true );

				} else if ( componentType === WEBGL_CONSTANTS.BYTE ) {

					dataView.setInt8( offset, value );

				} else if ( componentType === WEBGL_CONSTANTS.UNSIGNED_BYTE ) {

					dataView.setUint8( offset, value );

				}

				offset += componentSize;

			}

			if ( ( offset % byteStride ) !== 0 ) {

				offset += byteStride - ( offset % byteStride );

			}

		}

		const bufferViewDef = {

			buffer: this.processBuffer( dataView.buffer ),
			byteOffset: this.byteOffset,
			byteLength: byteLength

		};

		if ( target !== undefined ) bufferViewDef.target = target;

		if ( target === WEBGL_CONSTANTS.ARRAY_BUFFER ) {

			// Only define byteStride for vertex attributes.
			bufferViewDef.byteStride = byteStride;

		}

		this.byteOffset += byteLength;

		json.bufferViews.push( bufferViewDef );

		// @TODO Merge bufferViews where possible.
		const output = {

			id: json.bufferViews.length - 1,
			byteLength: 0

		};

		return output;

	}
```
</details>

##### `processBufferViewImage(blob: Blob): Promise<number>`

<details><summary>Code</summary>

```ts
processBufferViewImage( blob ) {

		const writer = this;
		const json = writer.json;

		if ( ! json.bufferViews ) json.bufferViews = [];

		return new Promise( function ( resolve ) {

			const reader = new FileReader();
			reader.readAsArrayBuffer( blob );
			reader.onloadend = function () {

				const buffer = getPaddedArrayBuffer( reader.result );

				const bufferViewDef = {
					buffer: writer.processBuffer( buffer ),
					byteOffset: writer.byteOffset,
					byteLength: buffer.byteLength
				};

				writer.byteOffset += buffer.byteLength;
				resolve( json.bufferViews.push( bufferViewDef ) - 1 );

			};

		} );

	}
```
</details>

##### `processAccessor(attribute: BufferAttribute, geometry: BufferGeometry, start: number, count: number): number`

<details><summary>Code</summary>

```ts
processAccessor( attribute, geometry, start, count ) {

		const json = this.json;

		const types = {

			1: 'SCALAR',
			2: 'VEC2',
			3: 'VEC3',
			4: 'VEC4',
			9: 'MAT3',
			16: 'MAT4'

		};

		let componentType;

		// Detect the component type of the attribute array
		if ( attribute.array.constructor === Float32Array ) {

			componentType = WEBGL_CONSTANTS.FLOAT;

		} else if ( attribute.array.constructor === Int32Array ) {

			componentType = WEBGL_CONSTANTS.INT;

		} else if ( attribute.array.constructor === Uint32Array ) {

			componentType = WEBGL_CONSTANTS.UNSIGNED_INT;

		} else if ( attribute.array.constructor === Int16Array ) {

			componentType = WEBGL_CONSTANTS.SHORT;

		} else if ( attribute.array.constructor === Uint16Array ) {

			componentType = WEBGL_CONSTANTS.UNSIGNED_SHORT;

		} else if ( attribute.array.constructor === Int8Array ) {

			componentType = WEBGL_CONSTANTS.BYTE;

		} else if ( attribute.array.constructor === Uint8Array ) {

			componentType = WEBGL_CONSTANTS.UNSIGNED_BYTE;

		} else {

			throw new Error( 'THREE.GLTFExporter: Unsupported bufferAttribute component type: ' + attribute.array.constructor.name );

		}

		if ( start === undefined ) start = 0;
		if ( count === undefined || count === Infinity ) count = attribute.count;

		// Skip creating an accessor if the attribute doesn't have data to export
		if ( count === 0 ) return null;

		const minMax = getMinMax( attribute, start, count );
		let bufferViewTarget;

		// If geometry isn't provided, don't infer the target usage of the bufferView. For
		// animation samplers, target must not be set.
		if ( geometry !== undefined ) {

			bufferViewTarget = attribute === geometry.index ? WEBGL_CONSTANTS.ELEMENT_ARRAY_BUFFER : WEBGL_CONSTANTS.ARRAY_BUFFER;

		}

		const bufferView = this.processBufferView( attribute, componentType, start, count, bufferViewTarget );

		const accessorDef = {

			bufferView: bufferView.id,
			byteOffset: bufferView.byteOffset,
			componentType: componentType,
			count: count,
			max: minMax.max,
			min: minMax.min,
			type: types[ attribute.itemSize ]

		};

		if ( attribute.normalized === true ) accessorDef.normalized = true;
		if ( ! json.accessors ) json.accessors = [];

		return json.accessors.push( accessorDef ) - 1;

	}
```
</details>

##### `processImage(image: new (width?: number, height?: number) => HTMLImageElement, format: number, flipY: boolean, mimeType: string): number`

<details><summary>Code</summary>

```ts
processImage( image, format, flipY, mimeType = 'image/png' ) {

		if ( image !== null ) {

			const writer = this;
			const cache = writer.cache;
			const json = writer.json;
			const options = writer.options;
			const pending = writer.pending;

			if ( ! cache.images.has( image ) ) cache.images.set( image, {} );

			const cachedImages = cache.images.get( image );

			const key = mimeType + ':flipY/' + flipY.toString();

			if ( cachedImages[ key ] !== undefined ) return cachedImages[ key ];

			if ( ! json.images ) json.images = [];

			const imageDef = { mimeType: mimeType };

			const canvas = getCanvas();

			canvas.width = Math.min( image.width, options.maxTextureSize );
			canvas.height = Math.min( image.height, options.maxTextureSize );

			const ctx = canvas.getContext( '2d', {
				willReadFrequently: true,
			} );

			if ( flipY === true ) {

				ctx.translate( 0, canvas.height );
				ctx.scale( 1, - 1 );

			}

			if ( image.data !== undefined ) { // THREE.DataTexture

				if ( format !== RGBAFormat ) {

					console.error( 'GLTFExporter: Only RGBAFormat is supported.', format );

				}

				if ( image.width > options.maxTextureSize || image.height > options.maxTextureSize ) {

					console.warn( 'GLTFExporter: Image size is bigger than maxTextureSize', image );

				}

				const data = new Uint8ClampedArray( image.height * image.width * 4 );

				for ( let i = 0; i < data.length; i += 4 ) {

					data[ i + 0 ] = image.data[ i + 0 ];
					data[ i + 1 ] = image.data[ i + 1 ];
					data[ i + 2 ] = image.data[ i + 2 ];
					data[ i + 3 ] = image.data[ i + 3 ];

				}

				ctx.putImageData( new ImageData( data, image.width, image.height ), 0, 0 );

			} else {

				if ( ( typeof HTMLImageElement !== 'undefined' && image instanceof HTMLImageElement ) ||
					( typeof HTMLCanvasElement !== 'undefined' && image instanceof HTMLCanvasElement ) ||
					( typeof ImageBitmap !== 'undefined' && image instanceof ImageBitmap ) ||
					( typeof OffscreenCanvas !== 'undefined' && image instanceof OffscreenCanvas ) ) {

					ctx.drawImage( image, 0, 0, canvas.width, canvas.height );

				} else {

					throw new Error( 'THREE.GLTFExporter: Invalid image type. Use HTMLImageElement, HTMLCanvasElement, ImageBitmap or OffscreenCanvas.' );

				}

			}

			if ( options.binary === true ) {

				pending.push(

					getToBlobPromise( canvas, mimeType )
						.then( blob => writer.processBufferViewImage( blob ) )
						.then( bufferViewIndex => {

							imageDef.bufferView = bufferViewIndex;

						} )

				);

			} else {

				imageDef.uri = ImageUtils.getDataURL( canvas, mimeType );

			}

			const index = json.images.push( imageDef ) - 1;
			cachedImages[ key ] = index;
			return index;

		} else {

			throw new Error( 'THREE.GLTFExporter: No valid image data found. Unable to process texture.' );

		}

	}
```
</details>

##### `processSampler(map: Texture): number`

<details><summary>Code</summary>

```ts
processSampler( map ) {

		const json = this.json;

		if ( ! json.samplers ) json.samplers = [];

		const samplerDef = {
			magFilter: THREE_TO_WEBGL[ map.magFilter ],
			minFilter: THREE_TO_WEBGL[ map.minFilter ],
			wrapS: THREE_TO_WEBGL[ map.wrapS ],
			wrapT: THREE_TO_WEBGL[ map.wrapT ]
		};

		return json.samplers.push( samplerDef ) - 1;

	}
```
</details>

##### `processTextureAsync(map: Texture): Promise<number>`

<details><summary>Code</summary>

```ts
async processTextureAsync( map ) {

		const writer = this;
		const options = writer.options;
		const cache = this.cache;
		const json = this.json;

		if ( cache.textures.has( map ) ) return cache.textures.get( map );

		if ( ! json.textures ) json.textures = [];

		// make non-readable textures (e.g. CompressedTexture) readable by blitting them into a new texture
		if ( map instanceof CompressedTexture ) {

			map = await this.decompressTextureAsync( map, options.maxTextureSize );

		}

		let mimeType = map.userData.mimeType;

		if ( mimeType === 'image/webp' ) mimeType = 'image/png';

		const textureDef = {
			sampler: this.processSampler( map ),
			source: this.processImage( map.image, map.format, map.flipY, mimeType )
		};

		if ( map.name ) textureDef.name = map.name;

		await this._invokeAllAsync( async function ( ext ) {

			ext.writeTexture && await ext.writeTexture( map, textureDef );

		} );

		const index = json.textures.push( textureDef ) - 1;
		cache.textures.set( map, index );
		return index;

	}
```
</details>

##### `processMaterialAsync(material: THREE.Material): Promise<number>`

<details><summary>Code</summary>

```ts
async processMaterialAsync( material ) {

		const cache = this.cache;
		const json = this.json;

		if ( cache.materials.has( material ) ) return cache.materials.get( material );

		if ( material.isShaderMaterial ) {

			console.warn( 'GLTFExporter: THREE.ShaderMaterial not supported.' );
			return null;

		}

		if ( ! json.materials ) json.materials = [];

		// @QUESTION Should we avoid including any attribute that has the default value?
		const materialDef = {	pbrMetallicRoughness: {} };

		if ( material.isMeshStandardMaterial !== true && material.isMeshBasicMaterial !== true ) {

			console.warn( 'GLTFExporter: Use MeshStandardMaterial or MeshBasicMaterial for best results.' );

		}

		// pbrMetallicRoughness.baseColorFactor
		const color = material.color.toArray().concat( [ material.opacity ] );

		if ( ! equalArray( color, [ 1, 1, 1, 1 ] ) ) {

			materialDef.pbrMetallicRoughness.baseColorFactor = color;

		}

		if ( material.isMeshStandardMaterial ) {

			materialDef.pbrMetallicRoughness.metallicFactor = material.metalness;
			materialDef.pbrMetallicRoughness.roughnessFactor = material.roughness;

		} else {

			materialDef.pbrMetallicRoughness.metallicFactor = 0;
			materialDef.pbrMetallicRoughness.roughnessFactor = 1;

		}

		// pbrMetallicRoughness.metallicRoughnessTexture
		if ( material.metalnessMap || material.roughnessMap ) {

			const metalRoughTexture = await this.buildMetalRoughTextureAsync( material.metalnessMap, material.roughnessMap );

			const metalRoughMapDef = {
				index: await this.processTextureAsync( metalRoughTexture ),
				texCoord: metalRoughTexture.channel
			};
			this.applyTextureTransform( metalRoughMapDef, metalRoughTexture );
			materialDef.pbrMetallicRoughness.metallicRoughnessTexture = metalRoughMapDef;

		}

		// pbrMetallicRoughness.baseColorTexture
		if ( material.map ) {

			const baseColorMapDef = {
				index: await this.processTextureAsync( material.map ),
				texCoord: material.map.channel
			};
			this.applyTextureTransform( baseColorMapDef, material.map );
			materialDef.pbrMetallicRoughness.baseColorTexture = baseColorMapDef;

		}

		if ( material.emissive ) {

			const emissive = material.emissive;
			const maxEmissiveComponent = Math.max( emissive.r, emissive.g, emissive.b );

			if ( maxEmissiveComponent > 0 ) {

				materialDef.emissiveFactor = material.emissive.toArray();

			}

			// emissiveTexture
			if ( material.emissiveMap ) {

				const emissiveMapDef = {
					index: await this.processTextureAsync( material.emissiveMap ),
					texCoord: material.emissiveMap.channel
				};
				this.applyTextureTransform( emissiveMapDef, material.emissiveMap );
				materialDef.emissiveTexture = emissiveMapDef;

			}

		}

		// normalTexture
		if ( material.normalMap ) {

			const normalMapDef = {
				index: await this.processTextureAsync( material.normalMap ),
				texCoord: material.normalMap.channel
			};

			if ( material.normalScale && material.normalScale.x !== 1 ) {

				// glTF normal scale is univariate. Ignore `y`, which may be flipped.
				// Context: https://github.com/mrdoob/three.js/issues/11438#issuecomment-507003995
				normalMapDef.scale = material.normalScale.x;

			}

			this.applyTextureTransform( normalMapDef, material.normalMap );
			materialDef.normalTexture = normalMapDef;

		}

		// occlusionTexture
		if ( material.aoMap ) {

			const occlusionMapDef = {
				index: await this.processTextureAsync( material.aoMap ),
				texCoord: material.aoMap.channel
			};

			if ( material.aoMapIntensity !== 1.0 ) {

				occlusionMapDef.strength = material.aoMapIntensity;

			}

			this.applyTextureTransform( occlusionMapDef, material.aoMap );
			materialDef.occlusionTexture = occlusionMapDef;

		}

		// alphaMode
		if ( material.transparent ) {

			materialDef.alphaMode = 'BLEND';

		} else {

			if ( material.alphaTest > 0.0 ) {

				materialDef.alphaMode = 'MASK';
				materialDef.alphaCutoff = material.alphaTest;

			}

		}

		// doubleSided
		if ( material.side === DoubleSide ) materialDef.doubleSided = true;
		if ( material.name !== '' ) materialDef.name = material.name;

		this.serializeUserData( material, materialDef );

		await this._invokeAllAsync( async function ( ext ) {

			ext.writeMaterialAsync && await ext.writeMaterialAsync( material, materialDef );

		} );

		const index = json.materials.push( materialDef ) - 1;
		cache.materials.set( material, index );
		return index;

	}
```
</details>

##### `processMeshAsync(mesh: THREE.Mesh): Promise<number>`

<details><summary>Code</summary>

```ts
async processMeshAsync( mesh ) {

		const cache = this.cache;
		const json = this.json;

		const meshCacheKeyParts = [ mesh.geometry.uuid ];

		if ( Array.isArray( mesh.material ) ) {

			for ( let i = 0, l = mesh.material.length; i < l; i ++ ) {

				meshCacheKeyParts.push( mesh.material[ i ].uuid	);

			}

		} else {

			meshCacheKeyParts.push( mesh.material.uuid );

		}

		const meshCacheKey = meshCacheKeyParts.join( ':' );

		if ( cache.meshes.has( meshCacheKey ) ) return cache.meshes.get( meshCacheKey );

		const geometry = mesh.geometry;

		let mode;

		// Use the correct mode
		if ( mesh.isLineSegments ) {

			mode = WEBGL_CONSTANTS.LINES;

		} else if ( mesh.isLineLoop ) {

			mode = WEBGL_CONSTANTS.LINE_LOOP;

		} else if ( mesh.isLine ) {

			mode = WEBGL_CONSTANTS.LINE_STRIP;

		} else if ( mesh.isPoints ) {

			mode = WEBGL_CONSTANTS.POINTS;

		} else {

			mode = mesh.material.wireframe ? WEBGL_CONSTANTS.LINES : WEBGL_CONSTANTS.TRIANGLES;

		}

		const meshDef = {};
		const attributes = {};
		const primitives = [];
		const targets = [];

		// Conversion between attributes names in threejs and gltf spec
		const nameConversion = {
			uv: 'TEXCOORD_0',
			uv1: 'TEXCOORD_1',
			uv2: 'TEXCOORD_2',
			uv3: 'TEXCOORD_3',
			color: 'COLOR_0',
			skinWeight: 'WEIGHTS_0',
			skinIndex: 'JOINTS_0'
		};

		const originalNormal = geometry.getAttribute( 'normal' );

		if ( originalNormal !== undefined && ! this.isNormalizedNormalAttribute( originalNormal ) ) {

			console.warn( 'THREE.GLTFExporter: Creating normalized normal attribute from the non-normalized one.' );

			geometry.setAttribute( 'normal', this.createNormalizedNormalAttribute( originalNormal ) );

		}

		// @QUESTION Detect if .vertexColors = true?
		// For every attribute create an accessor
		let modifiedAttribute = null;

		for ( let attributeName in geometry.attributes ) {

			// Ignore morph target attributes, which are exported later.
			if ( attributeName.slice( 0, 5 ) === 'morph' ) continue;

			const attribute = geometry.attributes[ attributeName ];
			attributeName = nameConversion[ attributeName ] || attributeName.toUpperCase();

			// Prefix all geometry attributes except the ones specifically
			// listed in the spec; non-spec attributes are considered custom.
			const validVertexAttributes =
					/^(POSITION|NORMAL|TANGENT|TEXCOORD_\d+|COLOR_\d+|JOINTS_\d+|WEIGHTS_\d+)$/;

			if ( ! validVertexAttributes.test( attributeName ) ) attributeName = '_' + attributeName;

			if ( cache.attributes.has( this.getUID( attribute ) ) ) {

				attributes[ attributeName ] = cache.attributes.get( this.getUID( attribute ) );
				continue;

			}

			// Enforce glTF vertex attribute requirements:
			// - JOINTS_0 must be UNSIGNED_BYTE or UNSIGNED_SHORT
			// - Only custom attributes may be INT or UNSIGNED_INT
			modifiedAttribute = null;
			const array = attribute.array;

			if ( attributeName === 'JOINTS_0' &&
				! ( array instanceof Uint16Array ) &&
				! ( array instanceof Uint8Array ) ) {

				console.warn( 'GLTFExporter: Attribute "skinIndex" converted to type UNSIGNED_SHORT.' );
				modifiedAttribute = new BufferAttribute( new Uint16Array( array ), attribute.itemSize, attribute.normalized );

			} else if ( ( array instanceof Uint32Array || array instanceof Int32Array ) && ! attributeName.startsWith( '_' ) ) {

				console.warn( `GLTFExporter: Attribute "${ attributeName }" converted to type FLOAT.` );
				modifiedAttribute = GLTFExporter.Utils.toFloat32BufferAttribute( attribute );

			}

			const accessor = this.processAccessor( modifiedAttribute || attribute, geometry );

			if ( accessor !== null ) {

				if ( ! attributeName.startsWith( '_' ) ) {

					this.detectMeshQuantization( attributeName, attribute );

				}

				attributes[ attributeName ] = accessor;
				cache.attributes.set( this.getUID( attribute ), accessor );

			}

		}

		if ( originalNormal !== undefined ) geometry.setAttribute( 'normal', originalNormal );

		// Skip if no exportable attributes found
		if ( Object.keys( attributes ).length === 0 ) return null;

		// Morph targets
		if ( mesh.morphTargetInfluences !== undefined && mesh.morphTargetInfluences.length > 0 ) {

			const weights = [];
			const targetNames = [];
			const reverseDictionary = {};

			if ( mesh.morphTargetDictionary !== undefined ) {

				for ( const key in mesh.morphTargetDictionary ) {

					reverseDictionary[ mesh.morphTargetDictionary[ key ] ] = key;

				}

			}

			for ( let i = 0; i < mesh.morphTargetInfluences.length; ++ i ) {

				const target = {};
				let warned = false;

				for ( const attributeName in geometry.morphAttributes ) {

					// glTF 2.0 morph supports only POSITION/NORMAL/TANGENT.
					// Three.js doesn't support TANGENT yet.

					if ( attributeName !== 'position' && attributeName !== 'normal' ) {

						if ( ! warned ) {

							console.warn( 'GLTFExporter: Only POSITION and NORMAL morph are supported.' );
							warned = true;

						}

						continue;

					}

					const attribute = geometry.morphAttributes[ attributeName ][ i ];
					const gltfAttributeName = attributeName.toUpperCase();

					// Three.js morph attribute has absolute values while the one of glTF has relative values.
					//
					// glTF 2.0 Specification:
					// https://github.com/KhronosGroup/glTF/tree/master/specification/2.0#morph-targets

					const baseAttribute = geometry.attributes[ attributeName ];

					if ( cache.attributes.has( this.getUID( attribute, true ) ) ) {

						target[ gltfAttributeName ] = cache.attributes.get( this.getUID( attribute, true ) );
						continue;

					}

					// Clones attribute not to override
					const relativeAttribute = attribute.clone();

					if ( ! geometry.morphTargetsRelative ) {

						for ( let j = 0, jl = attribute.count; j < jl; j ++ ) {

							for ( let a = 0; a < attribute.itemSize; a ++ ) {

								if ( a === 0 ) relativeAttribute.setX( j, attribute.getX( j ) - baseAttribute.getX( j ) );
								if ( a === 1 ) relativeAttribute.setY( j, attribute.getY( j ) - baseAttribute.getY( j ) );
								if ( a === 2 ) relativeAttribute.setZ( j, attribute.getZ( j ) - baseAttribute.getZ( j ) );
								if ( a === 3 ) relativeAttribute.setW( j, attribute.getW( j ) - baseAttribute.getW( j ) );

							}

						}

					}

					target[ gltfAttributeName ] = this.processAccessor( relativeAttribute, geometry );
					cache.attributes.set( this.getUID( baseAttribute, true ), target[ gltfAttributeName ] );

				}

				targets.push( target );

				weights.push( mesh.morphTargetInfluences[ i ] );

				if ( mesh.morphTargetDictionary !== undefined ) targetNames.push( reverseDictionary[ i ] );

			}

			meshDef.weights = weights;

			if ( targetNames.length > 0 ) {

				meshDef.extras = {};
				meshDef.extras.targetNames = targetNames;

			}

		}

		const isMultiMaterial = Array.isArray( mesh.material );

		if ( isMultiMaterial && geometry.groups.length === 0 ) return null;

		let didForceIndices = false;

		if ( isMultiMaterial && geometry.index === null ) {

			const indices = [];

			for ( let i = 0, il = geometry.attributes.position.count; i < il; i ++ ) {

				indices[ i ] = i;

			}

			geometry.setIndex( indices );

			didForceIndices = true;

		}

		const materials = isMultiMaterial ? mesh.material : [ mesh.material ];
		const groups = isMultiMaterial ? geometry.groups : [ { materialIndex: 0, start: undefined, count: undefined } ];

		for ( let i = 0, il = groups.length; i < il; i ++ ) {

			const primitive = {
				mode: mode,
				attributes: attributes,
			};

			this.serializeUserData( geometry, primitive );

			if ( targets.length > 0 ) primitive.targets = targets;

			if ( geometry.index !== null ) {

				let cacheKey = this.getUID( geometry.index );

				if ( groups[ i ].start !== undefined || groups[ i ].count !== undefined ) {

					cacheKey += ':' + groups[ i ].start + ':' + groups[ i ].count;

				}

				if ( cache.attributes.has( cacheKey ) ) {

					primitive.indices = cache.attributes.get( cacheKey );

				} else {

					primitive.indices = this.processAccessor( geometry.index, geometry, groups[ i ].start, groups[ i ].count );
					cache.attributes.set( cacheKey, primitive.indices );

				}

				if ( primitive.indices === null ) delete primitive.indices;

			}

			const material = await this.processMaterialAsync( materials[ groups[ i ].materialIndex ] );

			if ( material !== null ) primitive.material = material;

			primitives.push( primitive );

		}

		if ( didForceIndices === true ) {

			geometry.setIndex( null );

		}

		meshDef.primitives = primitives;

		if ( ! json.meshes ) json.meshes = [];

		await this._invokeAllAsync( function ( ext ) {

			ext.writeMesh && ext.writeMesh( mesh, meshDef );

		} );

		const index = json.meshes.push( meshDef ) - 1;
		cache.meshes.set( meshCacheKey, index );
		return index;

	}
```
</details>

##### `detectMeshQuantization(attributeName: string, attribute: THREE.BufferAttribute): void`

<details><summary>Code</summary>

```ts
detectMeshQuantization( attributeName, attribute ) {

		if ( this.extensionsUsed[ KHR_MESH_QUANTIZATION ] ) return;

		let attrType = undefined;

		switch ( attribute.array.constructor ) {

			case Int8Array:

				attrType = 'byte';

				break;

			case Uint8Array:

				attrType = 'unsigned byte';

				break;

			case Int16Array:

				attrType = 'short';

				break;

			case Uint16Array:

				attrType = 'unsigned short';

				break;

			default:

				return;

		}

		if ( attribute.normalized ) attrType += ' normalized';

		const attrNamePrefix = attributeName.split( '_', 1 )[ 0 ];

		if ( KHR_mesh_quantization_ExtraAttrTypes[ attrNamePrefix ] && KHR_mesh_quantization_ExtraAttrTypes[ attrNamePrefix ].includes( attrType ) ) {

			this.extensionsUsed[ KHR_MESH_QUANTIZATION ] = true;
			this.extensionsRequired[ KHR_MESH_QUANTIZATION ] = true;

		}

	}
```
</details>

##### `processCamera(camera: THREE.Camera): number`

<details><summary>Code</summary>

```ts
processCamera( camera ) {

		const json = this.json;

		if ( ! json.cameras ) json.cameras = [];

		const isOrtho = camera.isOrthographicCamera;

		const cameraDef = {
			type: isOrtho ? 'orthographic' : 'perspective'
		};

		if ( isOrtho ) {

			cameraDef.orthographic = {
				xmag: camera.right * 2,
				ymag: camera.top * 2,
				zfar: camera.far <= 0 ? 0.001 : camera.far,
				znear: camera.near < 0 ? 0 : camera.near
			};

		} else {

			cameraDef.perspective = {
				aspectRatio: camera.aspect,
				yfov: MathUtils.degToRad( camera.fov ),
				zfar: camera.far <= 0 ? 0.001 : camera.far,
				znear: camera.near < 0 ? 0 : camera.near
			};

		}

		// Question: Is saving "type" as name intentional?
		if ( camera.name !== '' ) cameraDef.name = camera.type;

		return json.cameras.push( cameraDef ) - 1;

	}
```
</details>

##### `processAnimation(clip: THREE.AnimationClip, root: THREE.Object3D): number`

<details><summary>Code</summary>

```ts
processAnimation( clip, root ) {

		const json = this.json;
		const nodeMap = this.nodeMap;

		if ( ! json.animations ) json.animations = [];

		clip = GLTFExporter.Utils.mergeMorphTargetTracks( clip.clone(), root );

		const tracks = clip.tracks;
		const channels = [];
		const samplers = [];

		for ( let i = 0; i < tracks.length; ++ i ) {

			const track = tracks[ i ];
			const trackBinding = PropertyBinding.parseTrackName( track.name );
			let trackNode = PropertyBinding.findNode( root, trackBinding.nodeName );
			const trackProperty = PATH_PROPERTIES[ trackBinding.propertyName ];

			if ( trackBinding.objectName === 'bones' ) {

				if ( trackNode.isSkinnedMesh === true ) {

					trackNode = trackNode.skeleton.getBoneByName( trackBinding.objectIndex );

				} else {

					trackNode = undefined;

				}

			}

			if ( ! trackNode || ! trackProperty ) {

				console.warn( 'THREE.GLTFExporter: Could not export animation track "%s".', track.name );
				continue;

			}

			const inputItemSize = 1;
			let outputItemSize = track.values.length / track.times.length;

			if ( trackProperty === PATH_PROPERTIES.morphTargetInfluences ) {

				outputItemSize /= trackNode.morphTargetInfluences.length;

			}

			let interpolation;

			// @TODO export CubicInterpolant(InterpolateSmooth) as CUBICSPLINE

			// Detecting glTF cubic spline interpolant by checking factory method's special property
			// GLTFCubicSplineInterpolant is a custom interpolant and track doesn't return
			// valid value from .getInterpolation().
			if ( track.createInterpolant.isInterpolantFactoryMethodGLTFCubicSpline === true ) {

				interpolation = 'CUBICSPLINE';

				// itemSize of CUBICSPLINE keyframe is 9
				// (VEC3 * 3: inTangent, splineVertex, and outTangent)
				// but needs to be stored as VEC3 so dividing by 3 here.
				outputItemSize /= 3;

			} else if ( track.getInterpolation() === InterpolateDiscrete ) {

				interpolation = 'STEP';

			} else {

				interpolation = 'LINEAR';

			}

			samplers.push( {
				input: this.processAccessor( new BufferAttribute( track.times, inputItemSize ) ),
				output: this.processAccessor( new BufferAttribute( track.values, outputItemSize ) ),
				interpolation: interpolation
			} );

			channels.push( {
				sampler: samplers.length - 1,
				target: {
					node: nodeMap.get( trackNode ),
					path: trackProperty
				}
			} );

		}

		json.animations.push( {
			name: clip.name || 'clip_' + json.animations.length,
			samplers: samplers,
			channels: channels
		} );

		return json.animations.length - 1;

	}
```
</details>

##### `processSkin(object: THREE.Object3D): number`

<details><summary>Code</summary>

```ts
processSkin( object ) {

		const json = this.json;
		const nodeMap = this.nodeMap;

		const node = json.nodes[ nodeMap.get( object ) ];

		const skeleton = object.skeleton;

		if ( skeleton === undefined ) return null;

		const rootJoint = object.skeleton.bones[ 0 ];

		if ( rootJoint === undefined ) return null;

		const joints = [];
		const inverseBindMatrices = new Float32Array( skeleton.bones.length * 16 );
		const temporaryBoneInverse = new Matrix4();

		for ( let i = 0; i < skeleton.bones.length; ++ i ) {

			joints.push( nodeMap.get( skeleton.bones[ i ] ) );
			temporaryBoneInverse.copy( skeleton.boneInverses[ i ] );
			temporaryBoneInverse.multiply( object.bindMatrix ).toArray( inverseBindMatrices, i * 16 );

		}

		if ( json.skins === undefined ) json.skins = [];

		json.skins.push( {
			inverseBindMatrices: this.processAccessor( new BufferAttribute( inverseBindMatrices, 16 ) ),
			joints: joints,
			skeleton: nodeMap.get( rootJoint )
		} );

		const skinIndex = node.skin = json.skins.length - 1;

		return skinIndex;

	}
```
</details>

##### `processNodeAsync(object: THREE.Object3D): Promise<number>`

<details><summary>Code</summary>

```ts
async processNodeAsync( object ) {

		const json = this.json;
		const options = this.options;
		const nodeMap = this.nodeMap;

		if ( ! json.nodes ) json.nodes = [];

		const nodeDef = {};

		if ( options.trs ) {

			const rotation = object.quaternion.toArray();
			const position = object.position.toArray();
			const scale = object.scale.toArray();

			if ( ! equalArray( rotation, [ 0, 0, 0, 1 ] ) ) {

				nodeDef.rotation = rotation;

			}

			if ( ! equalArray( position, [ 0, 0, 0 ] ) ) {

				nodeDef.translation = position;

			}

			if ( ! equalArray( scale, [ 1, 1, 1 ] ) ) {

				nodeDef.scale = scale;

			}

		} else {

			if ( object.matrixAutoUpdate ) {

				object.updateMatrix();

			}

			if ( isIdentityMatrix( object.matrix ) === false ) {

				nodeDef.matrix = object.matrix.elements;

			}

		}

		// We don't export empty strings name because it represents no-name in Three.js.
		if ( object.name !== '' ) nodeDef.name = String( object.name );

		this.serializeUserData( object, nodeDef );

		if ( object.isMesh || object.isLine || object.isPoints ) {

			const meshIndex = await this.processMeshAsync( object );

			if ( meshIndex !== null ) nodeDef.mesh = meshIndex;

		} else if ( object.isCamera ) {

			nodeDef.camera = this.processCamera( object );

		}

		if ( object.isSkinnedMesh ) this.skins.push( object );

		const nodeIndex = json.nodes.push( nodeDef ) - 1;
		nodeMap.set( object, nodeIndex );

		if ( object.children.length > 0 ) {

			const children = [];

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				const child = object.children[ i ];

				if ( child.visible || options.onlyVisible === false ) {

					const childNodeIndex = await this.processNodeAsync( child );

					if ( childNodeIndex !== null ) children.push( childNodeIndex );

				}

			}

			if ( children.length > 0 ) nodeDef.children = children;

		}

		await this._invokeAllAsync( function ( ext ) {

			ext.writeNode && ext.writeNode( object, nodeDef );

		} );

		return nodeIndex;

	}
```
</details>

##### `processSceneAsync(scene: Scene): Promise<void>`

<details><summary>Code</summary>

```ts
async processSceneAsync( scene ) {

		const json = this.json;
		const options = this.options;

		if ( ! json.scenes ) {

			json.scenes = [];
			json.scene = 0;

		}

		const sceneDef = {};

		if ( scene.name !== '' ) sceneDef.name = scene.name;

		json.scenes.push( sceneDef );

		const nodes = [];

		for ( let i = 0, l = scene.children.length; i < l; i ++ ) {

			const child = scene.children[ i ];

			if ( child.visible || options.onlyVisible === false ) {

				const nodeIndex = await this.processNodeAsync( child );

				if ( nodeIndex !== null ) nodes.push( nodeIndex );

			}

		}

		if ( nodes.length > 0 ) sceneDef.nodes = nodes;

		this.serializeUserData( scene, sceneDef );

	}
```
</details>

##### `processObjectsAsync(objects: THREE.Object3D[]): Promise<void>`

<details><summary>Code</summary>

```ts
async processObjectsAsync( objects ) {

		const scene = new Scene();
		scene.name = 'AuxScene';

		for ( let i = 0; i < objects.length; i ++ ) {

			// We push directly to children instead of calling `add` to prevent
			// modify the .parent and break its original scene and hierarchy
			scene.children.push( objects[ i ] );

		}

		await this.processSceneAsync( scene );

	}
```
</details>

##### `processInputAsync(input: any): Promise<void>`

<details><summary>Code</summary>

```ts
async processInputAsync( input ) {

		const options = this.options;

		input = input instanceof Array ? input : [ input ];

		await this._invokeAllAsync( function ( ext ) {

			ext.beforeParse && ext.beforeParse( input );

		} );

		const objectsWithoutScene = [];

		for ( let i = 0; i < input.length; i ++ ) {

			if ( input[ i ] instanceof Scene ) {

				await this.processSceneAsync( input[ i ] );

			} else {

				objectsWithoutScene.push( input[ i ] );

			}

		}

		if ( objectsWithoutScene.length > 0 ) {

			await this.processObjectsAsync( objectsWithoutScene );

		}

		for ( let i = 0; i < this.skins.length; ++ i ) {

			this.processSkin( this.skins[ i ] );

		}

		for ( let i = 0; i < options.animations.length; ++ i ) {

			this.processAnimation( options.animations[ i ], input[ 0 ] );

		}

		await this._invokeAllAsync( function ( ext ) {

			ext.afterParse && ext.afterParse( input );

		} );

	}
```
</details>

##### `_invokeAllAsync(func: any): Promise<void>`

<details><summary>Code</summary>

```ts
async _invokeAllAsync( func ) {

		for ( let i = 0, il = this.plugins.length; i < il; i ++ ) {

			await func( this.plugins[ i ] );

		}

	}
```
</details>

### `GLTFLightExtension`

<details><summary>Class Code</summary>

```ts
class GLTFLightExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_lights_punctual';

	}

	writeNode( light, nodeDef ) {

		if ( ! light.isLight ) return;

		if ( ! light.isDirectionalLight && ! light.isPointLight && ! light.isSpotLight ) {

			console.warn( 'THREE.GLTFExporter: Only directional, point, and spot lights are supported.', light );
			return;

		}

		const writer = this.writer;
		const json = writer.json;
		const extensionsUsed = writer.extensionsUsed;

		const lightDef = {};

		if ( light.name ) lightDef.name = light.name;

		lightDef.color = light.color.toArray();

		lightDef.intensity = light.intensity;

		if ( light.isDirectionalLight ) {

			lightDef.type = 'directional';

		} else if ( light.isPointLight ) {

			lightDef.type = 'point';

			if ( light.distance > 0 ) lightDef.range = light.distance;

		} else if ( light.isSpotLight ) {

			lightDef.type = 'spot';

			if ( light.distance > 0 ) lightDef.range = light.distance;

			lightDef.spot = {};
			lightDef.spot.innerConeAngle = ( 1.0 - light.penumbra ) * light.angle;
			lightDef.spot.outerConeAngle = light.angle;

		}

		if ( light.decay !== undefined && light.decay !== 2 ) {

			console.warn( 'THREE.GLTFExporter: Light decay may be lost. glTF is physically-based, '
				+ 'and expects light.decay=2.' );

		}

		if ( light.target
				&& ( light.target.parent !== light
				|| light.target.position.x !== 0
				|| light.target.position.y !== 0
				|| light.target.position.z !== - 1 ) ) {

			console.warn( 'THREE.GLTFExporter: Light direction may be lost. For best results, '
				+ 'make light.target a child of the light with position 0,0,-1.' );

		}

		if ( ! extensionsUsed[ this.name ] ) {

			json.extensions = json.extensions || {};
			json.extensions[ this.name ] = { lights: [] };
			extensionsUsed[ this.name ] = true;

		}

		const lights = json.extensions[ this.name ].lights;
		lights.push( lightDef );

		nodeDef.extensions = nodeDef.extensions || {};
		nodeDef.extensions[ this.name ] = { light: lights.length - 1 };

	}

}
```
</details>

#### Methods

##### `writeNode(light: any, nodeDef: any): void`

<details><summary>Code</summary>

```ts
writeNode( light, nodeDef ) {

		if ( ! light.isLight ) return;

		if ( ! light.isDirectionalLight && ! light.isPointLight && ! light.isSpotLight ) {

			console.warn( 'THREE.GLTFExporter: Only directional, point, and spot lights are supported.', light );
			return;

		}

		const writer = this.writer;
		const json = writer.json;
		const extensionsUsed = writer.extensionsUsed;

		const lightDef = {};

		if ( light.name ) lightDef.name = light.name;

		lightDef.color = light.color.toArray();

		lightDef.intensity = light.intensity;

		if ( light.isDirectionalLight ) {

			lightDef.type = 'directional';

		} else if ( light.isPointLight ) {

			lightDef.type = 'point';

			if ( light.distance > 0 ) lightDef.range = light.distance;

		} else if ( light.isSpotLight ) {

			lightDef.type = 'spot';

			if ( light.distance > 0 ) lightDef.range = light.distance;

			lightDef.spot = {};
			lightDef.spot.innerConeAngle = ( 1.0 - light.penumbra ) * light.angle;
			lightDef.spot.outerConeAngle = light.angle;

		}

		if ( light.decay !== undefined && light.decay !== 2 ) {

			console.warn( 'THREE.GLTFExporter: Light decay may be lost. glTF is physically-based, '
				+ 'and expects light.decay=2.' );

		}

		if ( light.target
				&& ( light.target.parent !== light
				|| light.target.position.x !== 0
				|| light.target.position.y !== 0
				|| light.target.position.z !== - 1 ) ) {

			console.warn( 'THREE.GLTFExporter: Light direction may be lost. For best results, '
				+ 'make light.target a child of the light with position 0,0,-1.' );

		}

		if ( ! extensionsUsed[ this.name ] ) {

			json.extensions = json.extensions || {};
			json.extensions[ this.name ] = { lights: [] };
			extensionsUsed[ this.name ] = true;

		}

		const lights = json.extensions[ this.name ].lights;
		lights.push( lightDef );

		nodeDef.extensions = nodeDef.extensions || {};
		nodeDef.extensions[ this.name ] = { light: lights.length - 1 };

	}
```
</details>

### `GLTFMaterialsUnlitExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsUnlitExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_unlit';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshBasicMaterial ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = {};

		extensionsUsed[ this.name ] = true;

		materialDef.pbrMetallicRoughness.metallicFactor = 0.0;
		materialDef.pbrMetallicRoughness.roughnessFactor = 0.9;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshBasicMaterial ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = {};

		extensionsUsed[ this.name ] = true;

		materialDef.pbrMetallicRoughness.metallicFactor = 0.0;
		materialDef.pbrMetallicRoughness.roughnessFactor = 0.9;

	}
```
</details>

### `GLTFMaterialsClearcoatExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsClearcoatExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_clearcoat';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.clearcoat === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.clearcoatFactor = material.clearcoat;

		if ( material.clearcoatMap ) {

			const clearcoatMapDef = {
				index: await writer.processTextureAsync( material.clearcoatMap ),
				texCoord: material.clearcoatMap.channel
			};
			writer.applyTextureTransform( clearcoatMapDef, material.clearcoatMap );
			extensionDef.clearcoatTexture = clearcoatMapDef;

		}

		extensionDef.clearcoatRoughnessFactor = material.clearcoatRoughness;

		if ( material.clearcoatRoughnessMap ) {

			const clearcoatRoughnessMapDef = {
				index: await writer.processTextureAsync( material.clearcoatRoughnessMap ),
				texCoord: material.clearcoatRoughnessMap.channel
			};
			writer.applyTextureTransform( clearcoatRoughnessMapDef, material.clearcoatRoughnessMap );
			extensionDef.clearcoatRoughnessTexture = clearcoatRoughnessMapDef;

		}

		if ( material.clearcoatNormalMap ) {

			const clearcoatNormalMapDef = {
				index: await writer.processTextureAsync( material.clearcoatNormalMap ),
				texCoord: material.clearcoatNormalMap.channel
			};

			if ( material.clearcoatNormalScale.x !== 1 ) clearcoatNormalMapDef.scale = material.clearcoatNormalScale.x;

			writer.applyTextureTransform( clearcoatNormalMapDef, material.clearcoatNormalMap );
			extensionDef.clearcoatNormalTexture = clearcoatNormalMapDef;

		}

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;


	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.clearcoat === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.clearcoatFactor = material.clearcoat;

		if ( material.clearcoatMap ) {

			const clearcoatMapDef = {
				index: await writer.processTextureAsync( material.clearcoatMap ),
				texCoord: material.clearcoatMap.channel
			};
			writer.applyTextureTransform( clearcoatMapDef, material.clearcoatMap );
			extensionDef.clearcoatTexture = clearcoatMapDef;

		}

		extensionDef.clearcoatRoughnessFactor = material.clearcoatRoughness;

		if ( material.clearcoatRoughnessMap ) {

			const clearcoatRoughnessMapDef = {
				index: await writer.processTextureAsync( material.clearcoatRoughnessMap ),
				texCoord: material.clearcoatRoughnessMap.channel
			};
			writer.applyTextureTransform( clearcoatRoughnessMapDef, material.clearcoatRoughnessMap );
			extensionDef.clearcoatRoughnessTexture = clearcoatRoughnessMapDef;

		}

		if ( material.clearcoatNormalMap ) {

			const clearcoatNormalMapDef = {
				index: await writer.processTextureAsync( material.clearcoatNormalMap ),
				texCoord: material.clearcoatNormalMap.channel
			};

			if ( material.clearcoatNormalScale.x !== 1 ) clearcoatNormalMapDef.scale = material.clearcoatNormalScale.x;

			writer.applyTextureTransform( clearcoatNormalMapDef, material.clearcoatNormalMap );
			extensionDef.clearcoatNormalTexture = clearcoatNormalMapDef;

		}

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;


	}
```
</details>

### `GLTFMaterialsDispersionExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsDispersionExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_dispersion';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.dispersion === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.dispersion = material.dispersion;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.dispersion === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.dispersion = material.dispersion;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsIridescenceExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsIridescenceExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_iridescence';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.iridescence === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.iridescenceFactor = material.iridescence;

		if ( material.iridescenceMap ) {

			const iridescenceMapDef = {
				index: await writer.processTextureAsync( material.iridescenceMap ),
				texCoord: material.iridescenceMap.channel
			};
			writer.applyTextureTransform( iridescenceMapDef, material.iridescenceMap );
			extensionDef.iridescenceTexture = iridescenceMapDef;

		}

		extensionDef.iridescenceIor = material.iridescenceIOR;
		extensionDef.iridescenceThicknessMinimum = material.iridescenceThicknessRange[ 0 ];
		extensionDef.iridescenceThicknessMaximum = material.iridescenceThicknessRange[ 1 ];

		if ( material.iridescenceThicknessMap ) {

			const iridescenceThicknessMapDef = {
				index: await writer.processTextureAsync( material.iridescenceThicknessMap ),
				texCoord: material.iridescenceThicknessMap.channel
			};
			writer.applyTextureTransform( iridescenceThicknessMapDef, material.iridescenceThicknessMap );
			extensionDef.iridescenceThicknessTexture = iridescenceThicknessMapDef;

		}

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.iridescence === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.iridescenceFactor = material.iridescence;

		if ( material.iridescenceMap ) {

			const iridescenceMapDef = {
				index: await writer.processTextureAsync( material.iridescenceMap ),
				texCoord: material.iridescenceMap.channel
			};
			writer.applyTextureTransform( iridescenceMapDef, material.iridescenceMap );
			extensionDef.iridescenceTexture = iridescenceMapDef;

		}

		extensionDef.iridescenceIor = material.iridescenceIOR;
		extensionDef.iridescenceThicknessMinimum = material.iridescenceThicknessRange[ 0 ];
		extensionDef.iridescenceThicknessMaximum = material.iridescenceThicknessRange[ 1 ];

		if ( material.iridescenceThicknessMap ) {

			const iridescenceThicknessMapDef = {
				index: await writer.processTextureAsync( material.iridescenceThicknessMap ),
				texCoord: material.iridescenceThicknessMap.channel
			};
			writer.applyTextureTransform( iridescenceThicknessMapDef, material.iridescenceThicknessMap );
			extensionDef.iridescenceThicknessTexture = iridescenceThicknessMapDef;

		}

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsTransmissionExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsTransmissionExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_transmission';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.transmission === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.transmissionFactor = material.transmission;

		if ( material.transmissionMap ) {

			const transmissionMapDef = {
				index: await writer.processTextureAsync( material.transmissionMap ),
				texCoord: material.transmissionMap.channel
			};
			writer.applyTextureTransform( transmissionMapDef, material.transmissionMap );
			extensionDef.transmissionTexture = transmissionMapDef;

		}

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.transmission === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.transmissionFactor = material.transmission;

		if ( material.transmissionMap ) {

			const transmissionMapDef = {
				index: await writer.processTextureAsync( material.transmissionMap ),
				texCoord: material.transmissionMap.channel
			};
			writer.applyTextureTransform( transmissionMapDef, material.transmissionMap );
			extensionDef.transmissionTexture = transmissionMapDef;

		}

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsVolumeExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsVolumeExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_volume';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.transmission === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.thicknessFactor = material.thickness;

		if ( material.thicknessMap ) {

			const thicknessMapDef = {
				index: await writer.processTextureAsync( material.thicknessMap ),
				texCoord: material.thicknessMap.channel
			};
			writer.applyTextureTransform( thicknessMapDef, material.thicknessMap );
			extensionDef.thicknessTexture = thicknessMapDef;

		}

		if ( material.attenuationDistance !== Infinity ) {

			extensionDef.attenuationDistance = material.attenuationDistance;

		}

		extensionDef.attenuationColor = material.attenuationColor.toArray();

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.transmission === 0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.thicknessFactor = material.thickness;

		if ( material.thicknessMap ) {

			const thicknessMapDef = {
				index: await writer.processTextureAsync( material.thicknessMap ),
				texCoord: material.thicknessMap.channel
			};
			writer.applyTextureTransform( thicknessMapDef, material.thicknessMap );
			extensionDef.thicknessTexture = thicknessMapDef;

		}

		if ( material.attenuationDistance !== Infinity ) {

			extensionDef.attenuationDistance = material.attenuationDistance;

		}

		extensionDef.attenuationColor = material.attenuationColor.toArray();

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsIorExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsIorExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_ior';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.ior === 1.5 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.ior = material.ior;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.ior === 1.5 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.ior = material.ior;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsSpecularExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsSpecularExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_specular';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || ( material.specularIntensity === 1.0 &&
		       material.specularColor.equals( DEFAULT_SPECULAR_COLOR ) &&
		     ! material.specularIntensityMap && ! material.specularColorMap ) ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.specularIntensityMap ) {

			const specularIntensityMapDef = {
				index: await writer.processTextureAsync( material.specularIntensityMap ),
				texCoord: material.specularIntensityMap.channel
			};
			writer.applyTextureTransform( specularIntensityMapDef, material.specularIntensityMap );
			extensionDef.specularTexture = specularIntensityMapDef;

		}

		if ( material.specularColorMap ) {

			const specularColorMapDef = {
				index: await writer.processTextureAsync( material.specularColorMap ),
				texCoord: material.specularColorMap.channel
			};
			writer.applyTextureTransform( specularColorMapDef, material.specularColorMap );
			extensionDef.specularColorTexture = specularColorMapDef;

		}

		extensionDef.specularFactor = material.specularIntensity;
		extensionDef.specularColorFactor = material.specularColor.toArray();

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || ( material.specularIntensity === 1.0 &&
		       material.specularColor.equals( DEFAULT_SPECULAR_COLOR ) &&
		     ! material.specularIntensityMap && ! material.specularColorMap ) ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.specularIntensityMap ) {

			const specularIntensityMapDef = {
				index: await writer.processTextureAsync( material.specularIntensityMap ),
				texCoord: material.specularIntensityMap.channel
			};
			writer.applyTextureTransform( specularIntensityMapDef, material.specularIntensityMap );
			extensionDef.specularTexture = specularIntensityMapDef;

		}

		if ( material.specularColorMap ) {

			const specularColorMapDef = {
				index: await writer.processTextureAsync( material.specularColorMap ),
				texCoord: material.specularColorMap.channel
			};
			writer.applyTextureTransform( specularColorMapDef, material.specularColorMap );
			extensionDef.specularColorTexture = specularColorMapDef;

		}

		extensionDef.specularFactor = material.specularIntensity;
		extensionDef.specularColorFactor = material.specularColor.toArray();

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsSheenExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsSheenExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_sheen';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.sheen == 0.0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.sheenRoughnessMap ) {

			const sheenRoughnessMapDef = {
				index: await writer.processTextureAsync( material.sheenRoughnessMap ),
				texCoord: material.sheenRoughnessMap.channel
			};
			writer.applyTextureTransform( sheenRoughnessMapDef, material.sheenRoughnessMap );
			extensionDef.sheenRoughnessTexture = sheenRoughnessMapDef;

		}

		if ( material.sheenColorMap ) {

			const sheenColorMapDef = {
				index: await writer.processTextureAsync( material.sheenColorMap ),
				texCoord: material.sheenColorMap.channel
			};
			writer.applyTextureTransform( sheenColorMapDef, material.sheenColorMap );
			extensionDef.sheenColorTexture = sheenColorMapDef;

		}

		extensionDef.sheenRoughnessFactor = material.sheenRoughness;
		extensionDef.sheenColorFactor = material.sheenColor.toArray();

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.sheen == 0.0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.sheenRoughnessMap ) {

			const sheenRoughnessMapDef = {
				index: await writer.processTextureAsync( material.sheenRoughnessMap ),
				texCoord: material.sheenRoughnessMap.channel
			};
			writer.applyTextureTransform( sheenRoughnessMapDef, material.sheenRoughnessMap );
			extensionDef.sheenRoughnessTexture = sheenRoughnessMapDef;

		}

		if ( material.sheenColorMap ) {

			const sheenColorMapDef = {
				index: await writer.processTextureAsync( material.sheenColorMap ),
				texCoord: material.sheenColorMap.channel
			};
			writer.applyTextureTransform( sheenColorMapDef, material.sheenColorMap );
			extensionDef.sheenColorTexture = sheenColorMapDef;

		}

		extensionDef.sheenRoughnessFactor = material.sheenRoughness;
		extensionDef.sheenColorFactor = material.sheenColor.toArray();

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsAnisotropyExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsAnisotropyExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_anisotropy';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.anisotropy == 0.0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.anisotropyMap ) {

			const anisotropyMapDef = { index: await writer.processTextureAsync( material.anisotropyMap ) };
			writer.applyTextureTransform( anisotropyMapDef, material.anisotropyMap );
			extensionDef.anisotropyTexture = anisotropyMapDef;

		}

		extensionDef.anisotropyStrength = material.anisotropy;
		extensionDef.anisotropyRotation = material.anisotropyRotation;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshPhysicalMaterial || material.anisotropy == 0.0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.anisotropyMap ) {

			const anisotropyMapDef = { index: await writer.processTextureAsync( material.anisotropyMap ) };
			writer.applyTextureTransform( anisotropyMapDef, material.anisotropyMap );
			extensionDef.anisotropyTexture = anisotropyMapDef;

		}

		extensionDef.anisotropyStrength = material.anisotropy;
		extensionDef.anisotropyRotation = material.anisotropyRotation;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsEmissiveStrengthExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsEmissiveStrengthExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'KHR_materials_emissive_strength';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshStandardMaterial || material.emissiveIntensity === 1.0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.emissiveStrength = material.emissiveIntensity;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshStandardMaterial || material.emissiveIntensity === 1.0 ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		extensionDef.emissiveStrength = material.emissiveIntensity;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMaterialsBumpExtension`

<details><summary>Class Code</summary>

```ts
class GLTFMaterialsBumpExtension {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'EXT_materials_bump';

	}

	async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshStandardMaterial || (
		       material.bumpScale === 1 &&
		     ! material.bumpMap ) ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.bumpMap ) {

			const bumpMapDef = {
				index: await writer.processTextureAsync( material.bumpMap ),
				texCoord: material.bumpMap.channel
			};
			writer.applyTextureTransform( bumpMapDef, material.bumpMap );
			extensionDef.bumpTexture = bumpMapDef;

		}

		extensionDef.bumpFactor = material.bumpScale;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeMaterialAsync(material: any, materialDef: any): Promise<void>`

<details><summary>Code</summary>

```ts
async writeMaterialAsync( material, materialDef ) {

		if ( ! material.isMeshStandardMaterial || (
		       material.bumpScale === 1 &&
		     ! material.bumpMap ) ) return;

		const writer = this.writer;
		const extensionsUsed = writer.extensionsUsed;

		const extensionDef = {};

		if ( material.bumpMap ) {

			const bumpMapDef = {
				index: await writer.processTextureAsync( material.bumpMap ),
				texCoord: material.bumpMap.channel
			};
			writer.applyTextureTransform( bumpMapDef, material.bumpMap );
			extensionDef.bumpTexture = bumpMapDef;

		}

		extensionDef.bumpFactor = material.bumpScale;

		materialDef.extensions = materialDef.extensions || {};
		materialDef.extensions[ this.name ] = extensionDef;

		extensionsUsed[ this.name ] = true;

	}
```
</details>

### `GLTFMeshGpuInstancing`

<details><summary>Class Code</summary>

```ts
class GLTFMeshGpuInstancing {

	constructor( writer ) {

		this.writer = writer;
		this.name = 'EXT_mesh_gpu_instancing';

	}

	writeNode( object, nodeDef ) {

		if ( ! object.isInstancedMesh ) return;

		const writer = this.writer;

		const mesh = object;

		const translationAttr = new Float32Array( mesh.count * 3 );
		const rotationAttr = new Float32Array( mesh.count * 4 );
		const scaleAttr = new Float32Array( mesh.count * 3 );

		const matrix = new Matrix4();
		const position = new Vector3();
		const quaternion = new Quaternion();
		const scale = new Vector3();

		for ( let i = 0; i < mesh.count; i ++ ) {

			mesh.getMatrixAt( i, matrix );
			matrix.decompose( position, quaternion, scale );

			position.toArray( translationAttr, i * 3 );
			quaternion.toArray( rotationAttr, i * 4 );
			scale.toArray( scaleAttr, i * 3 );

		}

		const attributes = {
			TRANSLATION: writer.processAccessor( new BufferAttribute( translationAttr, 3 ) ),
			ROTATION: writer.processAccessor( new BufferAttribute( rotationAttr, 4 ) ),
			SCALE: writer.processAccessor( new BufferAttribute( scaleAttr, 3 ) ),
		};

		if ( mesh.instanceColor )
			attributes._COLOR_0 = writer.processAccessor( mesh.instanceColor );

		nodeDef.extensions = nodeDef.extensions || {};
		nodeDef.extensions[ this.name ] = { attributes };

		writer.extensionsUsed[ this.name ] = true;
		writer.extensionsRequired[ this.name ] = true;

	}

}
```
</details>

#### Methods

##### `writeNode(object: any, nodeDef: any): void`

<details><summary>Code</summary>

```ts
writeNode( object, nodeDef ) {

		if ( ! object.isInstancedMesh ) return;

		const writer = this.writer;

		const mesh = object;

		const translationAttr = new Float32Array( mesh.count * 3 );
		const rotationAttr = new Float32Array( mesh.count * 4 );
		const scaleAttr = new Float32Array( mesh.count * 3 );

		const matrix = new Matrix4();
		const position = new Vector3();
		const quaternion = new Quaternion();
		const scale = new Vector3();

		for ( let i = 0; i < mesh.count; i ++ ) {

			mesh.getMatrixAt( i, matrix );
			matrix.decompose( position, quaternion, scale );

			position.toArray( translationAttr, i * 3 );
			quaternion.toArray( rotationAttr, i * 4 );
			scale.toArray( scaleAttr, i * 3 );

		}

		const attributes = {
			TRANSLATION: writer.processAccessor( new BufferAttribute( translationAttr, 3 ) ),
			ROTATION: writer.processAccessor( new BufferAttribute( rotationAttr, 4 ) ),
			SCALE: writer.processAccessor( new BufferAttribute( scaleAttr, 3 ) ),
		};

		if ( mesh.instanceColor )
			attributes._COLOR_0 = writer.processAccessor( mesh.instanceColor );

		nodeDef.extensions = nodeDef.extensions || {};
		nodeDef.extensions[ this.name ] = { attributes };

		writer.extensionsUsed[ this.name ] = true;
		writer.extensionsRequired[ this.name ] = true;

	}
```
</details>


---