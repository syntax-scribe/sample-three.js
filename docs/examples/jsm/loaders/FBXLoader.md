[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FBXLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 108 |
| 🧱 Classes | 8 |
| 📦 Imports | 44 |
| 📊 Variables & Constants | 319 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/FBXLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AmbientLight` | `three` |
| `AnimationClip` | `three` |
| `Bone` | `three` |
| `BufferGeometry` | `three` |
| `ClampToEdgeWrapping` | `three` |
| `Color` | `three` |
| `ColorManagement` | `three` |
| `DirectionalLight` | `three` |
| `EquirectangularReflectionMapping` | `three` |
| `Euler` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Group` | `three` |
| `Line` | `three` |
| `LineBasicMaterial` | `three` |
| `Loader` | `three` |
| `LoaderUtils` | `three` |
| `MathUtils` | `three` |
| `Matrix3` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshLambertMaterial` | `three` |
| `MeshPhongMaterial` | `three` |
| `NumberKeyframeTrack` | `three` |
| `Object3D` | `three` |
| `PerspectiveCamera` | `three` |
| `PointLight` | `three` |
| `PropertyBinding` | `three` |
| `Quaternion` | `three` |
| `QuaternionKeyframeTrack` | `three` |
| `RepeatWrapping` | `three` |
| `SRGBColorSpace` | `three` |
| `ShapeUtils` | `three` |
| `Skeleton` | `three` |
| `SkinnedMesh` | `three` |
| `SpotLight` | `three` |
| `Texture` | `three` |
| `TextureLoader` | `three` |
| `Uint16BufferAttribute` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |
| `Vector4` | `three` |
| `VectorKeyframeTrack` | `three` |
| `NURBSCurve` | `../curves/NURBSCurve.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `fbxTree` | `any` | let/var | `*not shown*` | ✗ |
| `connections` | `any` | let/var | `*not shown*` | ✗ |
| `sceneGraph` | `any` | let/var | `*not shown*` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `path` | `any` | let/var | `( scope.path === '' ) ? LoaderUtils.extractUrlBase( url ) : scope.path` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `connectionMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `rawConnections` | `any` | let/var | `fbxTree.Connections.connections` | ✗ |
| `fromID` | `any` | let/var | `rawConnection[ 0 ]` | ✗ |
| `toID` | `any` | let/var | `rawConnection[ 1 ]` | ✗ |
| `relationship` | `any` | let/var | `rawConnection[ 2 ]` | ✗ |
| `parentRelationship` | `{ ID: any; relationship: any; }` | let/var | `{ ID: toID, relationship: relationship }` | ✗ |
| `childRelationship` | `{ ID: any; relationship: any; }` | let/var | `{ ID: fromID, relationship: relationship }` | ✗ |
| `images` | `{}` | let/var | `{}` | ✗ |
| `blobs` | `{}` | let/var | `{}` | ✗ |
| `videoNodes` | `any` | let/var | `fbxTree.Objects.Video` | ✗ |
| `videoNode` | `any` | let/var | `videoNodes[ nodeID ]` | ✗ |
| `arrayBufferContent` | `boolean` | let/var | `( videoNode.Content instanceof ArrayBuffer ) && ( videoNode.Content.byteLengt...` | ✗ |
| `base64Content` | `boolean` | let/var | `( typeof videoNode.Content === 'string' ) && ( videoNode.Content !== '' )` | ✗ |
| `filename` | `any` | let/var | `images[ id ]` | ✗ |
| `content` | `any` | let/var | `videoNode.Content` | ✗ |
| `fileName` | `any` | let/var | `videoNode.RelativeFilename \|\| videoNode.Filename` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `array` | `Uint8Array<any>` | let/var | `new Uint8Array( content )` | ✗ |
| `textureMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `textureNodes` | `any` | let/var | `fbxTree.Objects.Texture` | ✗ |
| `wrapModeU` | `any` | let/var | `textureNode.WrapModeU` | ✗ |
| `wrapModeV` | `any` | let/var | `textureNode.WrapModeV` | ✗ |
| `valueU` | `any` | let/var | `wrapModeU !== undefined ? wrapModeU.value : 0` | ✗ |
| `valueV` | `any` | let/var | `wrapModeV !== undefined ? wrapModeV.value : 0` | ✗ |
| `values` | `any` | let/var | `textureNode.Scaling.value` | ✗ |
| `values` | `any` | let/var | `textureNode.Translation.value` | ✗ |
| `loaderPath` | `any` | let/var | `loader.path` | ✗ |
| `children` | `any` | let/var | `connections.get( textureNode.id ).children` | ✗ |
| `fileName` | `any` | let/var | `*not shown*` | ✗ |
| `materialMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `materialNodes` | `any` | let/var | `fbxTree.Objects.Material` | ✗ |
| `ID` | `any` | let/var | `materialNode.id` | ✗ |
| `name` | `any` | let/var | `materialNode.attrName` | ✗ |
| `type` | `any` | let/var | `materialNode.ShadingModel` | ✗ |
| `material` | `any` | let/var | `*not shown*` | ✗ |
| `parameters` | `{ bumpScale: any; color: any; displac...` | let/var | `{}` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `type` | `any` | let/var | `child.relationship` | ✗ |
| `skeletons` | `{}` | let/var | `{}` | ✗ |
| `morphTargets` | `{}` | let/var | `{}` | ✗ |
| `DeformerNodes` | `any` | let/var | `fbxTree.Objects.Deformer` | ✗ |
| `deformerNode` | `any` | let/var | `DeformerNodes[ nodeID ]` | ✗ |
| `morphTarget` | `{ id: string; }` | let/var | `{ id: nodeID, }` | ✗ |
| `rawBones` | `any[]` | let/var | `[]` | ✗ |
| `boneNode` | `any` | let/var | `deformerNodes[ child.ID ]` | ✗ |
| `rawBone` | `{ ID: any; indices: any[]; weights: a...` | let/var | `{ ID: child.ID, indices: [], weights: [], transformLink: new Matrix4().fromAr...` | ✗ |
| `rawMorphTargets` | `any[]` | let/var | `[]` | ✗ |
| `child` | `any` | let/var | `relationships.children[ i ]` | ✗ |
| `morphTargetNode` | `any` | let/var | `deformerNodes[ child.ID ]` | ✗ |
| `rawMorphTarget` | `{ name: any; initialWeight: any; id: ...` | let/var | `{ name: morphTargetNode.attrName, initialWeight: morphTargetNode.DeformPercen...` | ✗ |
| `modelNodes` | `any` | let/var | `fbxTree.Objects.Model` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `modelNode` | `any` | let/var | `modelNodes[ model.ID ]` | ✗ |
| `parentConnections` | `any` | let/var | `connections.get( model.ID ).parents` | ✗ |
| `modelMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `modelNodes` | `any` | let/var | `fbxTree.Objects.Model` | ✗ |
| `node` | `any` | let/var | `modelNodes[ nodeID ]` | ✗ |
| `bone` | `any` | let/var | `null` | ✗ |
| `skeleton` | `any` | let/var | `skeletons[ ID ]` | ✗ |
| `subBone` | `any` | let/var | `bone` | ✗ |
| `model` | `any` | let/var | `*not shown*` | ✗ |
| `cameraAttribute` | `any` | let/var | `*not shown*` | ✗ |
| `attr` | `any` | let/var | `fbxTree.Objects.NodeAttribute[ child.ID ]` | ✗ |
| `type` | `number` | let/var | `0` | ✗ |
| `nearClippingPlane` | `number` | let/var | `1` | ✗ |
| `farClippingPlane` | `number` | let/var | `1000` | ✗ |
| `width` | `number` | let/var | `window.innerWidth` | ✗ |
| `height` | `number` | let/var | `window.innerHeight` | ✗ |
| `aspect` | `number` | let/var | `width / height` | ✗ |
| `fov` | `number` | let/var | `45` | ✗ |
| `focalLength` | `any` | let/var | `cameraAttribute.FocalLength ? cameraAttribute.FocalLength.value : null` | ✗ |
| `model` | `any` | let/var | `*not shown*` | ✗ |
| `lightAttribute` | `any` | let/var | `*not shown*` | ✗ |
| `attr` | `any` | let/var | `fbxTree.Objects.NodeAttribute[ child.ID ]` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `color` | `number` | let/var | `0xffffff` | ✗ |
| `intensity` | `number` | let/var | `( lightAttribute.Intensity === undefined ) ? 1 : lightAttribute.Intensity.val...` | ✗ |
| `distance` | `number` | let/var | `0` | ✗ |
| `decay` | `1` | let/var | `1` | ✗ |
| `angle` | `number` | let/var | `Math.PI / 3` | ✗ |
| `penumbra` | `number` | let/var | `0` | ✗ |
| `model` | `any` | let/var | `*not shown*` | ✗ |
| `geometry` | `any` | let/var | `null` | ✗ |
| `material` | `any` | let/var | `null` | ✗ |
| `materials` | `any[]` | let/var | `[]` | ✗ |
| `needsDefaultMaterial` | `boolean` | let/var | `false` | ✗ |
| `group` | `any` | let/var | `geometry.groups[ i ]` | ✗ |
| `defaultMaterial` | `any` | let/var | `new MeshPhongMaterial()` | ✗ |
| `material` | `any` | let/var | `new LineBasicMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, color: 0x3300ff,...` | ✗ |
| `transformData` | `{ inheritType: number; eulerOrder: st...` | let/var | `{}` | ✗ |
| `children` | `any` | let/var | `connections.get( model.ID ).children` | ✗ |
| `lookAtTarget` | `any` | let/var | `fbxTree.Objects.Model[ child.ID ]` | ✗ |
| `pos` | `any` | let/var | `lookAtTarget.Lcl_Translation.value` | ✗ |
| `skeleton` | `any` | let/var | `skeletons[ ID ]` | ✗ |
| `parents` | `any` | let/var | `connections.get( parseInt( skeleton.ID ) ).parents` | ✗ |
| `geoID` | `any` | let/var | `parent.ID` | ✗ |
| `bindMatrices` | `{}` | let/var | `{}` | ✗ |
| `BindPoseNode` | `any` | let/var | `fbxTree.Objects.Pose` | ✗ |
| `poseNodes` | `any` | let/var | `BindPoseNode[ nodeID ].PoseNode` | ✗ |
| `ambientColor` | `any` | let/var | `fbxTree.GlobalSettings.AmbientColor.value` | ✗ |
| `r` | `any` | let/var | `ambientColor[ 0 ]` | ✗ |
| `g` | `any` | let/var | `ambientColor[ 1 ]` | ✗ |
| `b` | `any` | let/var | `ambientColor[ 2 ]` | ✗ |
| `geometryMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `geoNodes` | `any` | let/var | `fbxTree.Objects.Geometry` | ✗ |
| `skeletons` | `any` | let/var | `deformers.skeletons` | ✗ |
| `morphTargets` | `any[]` | let/var | `[]` | ✗ |
| `modelNode` | `any` | let/var | `modelNodes[ 0 ]` | ✗ |
| `transformData` | `{ eulerOrder: string; inheritType: nu...` | let/var | `{}` | ✗ |
| `geo` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `positionAttribute` | `any` | let/var | `new Float32BufferAttribute( buffers.vertex, 3 )` | ✗ |
| `normalAttribute` | `any` | let/var | `new Float32BufferAttribute( buffers.normal, 3 )` | ✗ |
| `name` | `string` | let/var | `i === 0 ? 'uv' : `uv${ i }`` | ✗ |
| `prevMaterialIndex` | `any` | let/var | `buffers.materialIndex[ 0 ]` | ✗ |
| `startIndex` | `number` | let/var | `0` | ✗ |
| `lastGroup` | `any` | let/var | `geo.groups[ geo.groups.length - 1 ]` | ✗ |
| `lastIndex` | `any` | let/var | `lastGroup.start + lastGroup.count` | ✗ |
| `geoInfo` | `{ vertexPositions: any; vertexIndices...` | let/var | `{}` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `buffers` | `{ vertex: any[]; normal: any[]; color...` | let/var | `{ vertex: [], normal: [], colors: [], uvs: [], materialIndex: [], vertexWeigh...` | ✗ |
| `polygonIndex` | `number` | let/var | `0` | ✗ |
| `faceLength` | `number` | let/var | `0` | ✗ |
| `displayedWeightsWarning` | `boolean` | let/var | `false` | ✗ |
| `facePositionIndexes` | `any[]` | let/var | `[]` | ✗ |
| `faceNormals` | `any[]` | let/var | `[]` | ✗ |
| `faceColors` | `any[]` | let/var | `[]` | ✗ |
| `faceUVs` | `any[]` | let/var | `[]` | ✗ |
| `faceWeights` | `any[]` | let/var | `[]` | ✗ |
| `faceWeightIndices` | `any[]` | let/var | `[]` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `materialIndex` | `any` | let/var | `*not shown*` | ✗ |
| `endOfFace` | `boolean` | let/var | `false` | ✗ |
| `weightIndices` | `any[]` | let/var | `[]` | ✗ |
| `weights` | `any[]` | let/var | `[]` | ✗ |
| `wIndex` | `number[]` | let/var | `[ 0, 0, 0, 0 ]` | ✗ |
| `Weight` | `number[]` | let/var | `[ 0, 0, 0, 0 ]` | ✗ |
| `currentWeight` | `any` | let/var | `weight` | ✗ |
| `currentIndex` | `any` | let/var | `weightIndices[ weightIndex ]` | ✗ |
| `tmp` | `number` | let/var | `wIndex[ comparedWeightIndex ]` | ✗ |
| `normal` | `any` | let/var | `new Vector3( 0.0, 0.0, 0.0 )` | ✗ |
| `current` | `any` | let/var | `vertices[ i ]` | ✗ |
| `next` | `any` | let/var | `vertices[ ( i + 1 ) % vertices.length ]` | ✗ |
| `up` | `any` | let/var | `Math.abs( normalVector.z ) > 0.5 ? new Vector3( 0.0, 1.0, 0.0 ) : new Vector3...` | ✗ |
| `triangles` | `any` | let/var | `*not shown*` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `positions` | `any` | let/var | `geoInfo.baseVertexPositions \|\| geoInfo.vertexPositions` | ✗ |
| `triangulationInput` | `any[]` | let/var | `[]` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `morphGeoNode` | `any` | let/var | `fbxTree.Objects.Geometry[ rawTarget.geoID ]` | ✗ |
| `basePositions` | `any` | let/var | `parentGeoNode.Vertices !== undefined ? parentGeoNode.Vertices.a : []` | ✗ |
| `baseIndices` | `any` | let/var | `parentGeoNode.PolygonVertexIndex !== undefined ? parentGeoNode.PolygonVertexI...` | ✗ |
| `morphPositionsSparse` | `any` | let/var | `morphGeoNode.Vertices !== undefined ? morphGeoNode.Vertices.a : []` | ✗ |
| `morphIndices` | `any` | let/var | `morphGeoNode.Indexes !== undefined ? morphGeoNode.Indexes.a : []` | ✗ |
| `length` | `number` | let/var | `parentGeo.attributes.position.count * 3` | ✗ |
| `morphPositions` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( length )` | ✗ |
| `morphIndex` | `number` | let/var | `morphIndices[ i ] * 3` | ✗ |
| `morphGeoInfo` | `{ vertexIndices: any; vertexPositions...` | let/var | `{ vertexIndices: baseIndices, vertexPositions: morphPositions, baseVertexPosi...` | ✗ |
| `positionAttribute` | `any` | let/var | `new Float32BufferAttribute( morphBuffers.vertex, 3 )` | ✗ |
| `mappingType` | `any` | let/var | `NormalNode.MappingInformationType` | ✗ |
| `referenceType` | `any` | let/var | `NormalNode.ReferenceInformationType` | ✗ |
| `buffer` | `any` | let/var | `NormalNode.Normals.a` | ✗ |
| `indexBuffer` | `any[]` | let/var | `[]` | ✗ |
| `mappingType` | `any` | let/var | `UVNode.MappingInformationType` | ✗ |
| `referenceType` | `any` | let/var | `UVNode.ReferenceInformationType` | ✗ |
| `buffer` | `any` | let/var | `UVNode.UV.a` | ✗ |
| `indexBuffer` | `any[]` | let/var | `[]` | ✗ |
| `mappingType` | `any` | let/var | `ColorNode.MappingInformationType` | ✗ |
| `referenceType` | `any` | let/var | `ColorNode.ReferenceInformationType` | ✗ |
| `buffer` | `any` | let/var | `ColorNode.Colors.a` | ✗ |
| `indexBuffer` | `any[]` | let/var | `[]` | ✗ |
| `mappingType` | `any` | let/var | `MaterialNode.MappingInformationType` | ✗ |
| `referenceType` | `any` | let/var | `MaterialNode.ReferenceInformationType` | ✗ |
| `materialIndexBuffer` | `any` | let/var | `MaterialNode.Materials.a` | ✗ |
| `materialIndices` | `any[]` | let/var | `[]` | ✗ |
| `degree` | `number` | let/var | `order - 1` | ✗ |
| `knots` | `any` | let/var | `geoNode.KnotVector.a` | ✗ |
| `controlPoints` | `any[]` | let/var | `[]` | ✗ |
| `pointsValues` | `any` | let/var | `geoNode.Points.a` | ✗ |
| `startKnot` | `any` | let/var | `*not shown*` | ✗ |
| `endKnot` | `any` | let/var | `*not shown*` | ✗ |
| `curve` | `NURBSCurve` | let/var | `new NURBSCurve( degree, knots, controlPoints, startKnot, endKnot )` | ✗ |
| `animationClips` | `any[]` | let/var | `[]` | ✗ |
| `rawClip` | `any` | let/var | `rawClips[ key ]` | ✗ |
| `rawCurveNodes` | `any` | let/var | `fbxTree.Objects.AnimationCurveNode` | ✗ |
| `curveNodesMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `rawCurveNode` | `any` | let/var | `rawCurveNodes[ nodeID ]` | ✗ |
| `curveNode` | `{ id: any; attr: any; curves: {}; }` | let/var | `{ id: rawCurveNode.id, attr: rawCurveNode.attrName, curves: {}, }` | ✗ |
| `rawCurves` | `any` | let/var | `fbxTree.Objects.AnimationCurve` | ✗ |
| `animationCurve` | `{ id: any; times: any; values: any; }` | let/var | `{ id: rawCurves[ nodeID ].id, times: rawCurves[ nodeID ].KeyTime.a.map( conve...` | ✗ |
| `animationCurveID` | `any` | let/var | `relationships.parents[ 0 ].ID` | ✗ |
| `animationCurveRelationship` | `any` | let/var | `relationships.parents[ 0 ].relationship` | ✗ |
| `rawLayers` | `any` | let/var | `fbxTree.Objects.AnimationLayer` | ✗ |
| `layersMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `layerCurveNodes` | `any[]` | let/var | `[]` | ✗ |
| `children` | `any` | let/var | `connection.children` | ✗ |
| `modelID` | `any` | let/var | `connections.get( child.ID ).parents.filter( function ( parent ) { return pare...` | ✗ |
| `rawModel` | `any` | let/var | `fbxTree.Objects.Model[ modelID.toString() ]` | ✗ |
| `node` | `{ modelName: any; ID: any; initialPos...` | let/var | `{ modelName: rawModel.attrName ? PropertyBinding.sanitizeNodeName( rawModel.a...` | ✗ |
| `deformerID` | `any` | let/var | `connections.get( child.ID ).parents.filter( function ( parent ) { return pare...` | ✗ |
| `morpherID` | `any` | let/var | `connections.get( deformerID ).parents[ 0 ].ID` | ✗ |
| `geoID` | `any` | let/var | `connections.get( morpherID ).parents[ 0 ].ID` | ✗ |
| `modelID` | `any` | let/var | `connections.get( geoID ).parents[ 0 ].ID` | ✗ |
| `rawModel` | `any` | let/var | `fbxTree.Objects.Model[ modelID ]` | ✗ |
| `node` | `{ modelName: any; morphName: any; }` | let/var | `{ modelName: rawModel.attrName ? PropertyBinding.sanitizeNodeName( rawModel.a...` | ✗ |
| `rawStacks` | `any` | let/var | `fbxTree.Objects.AnimationStack` | ✗ |
| `rawClips` | `{}` | let/var | `{}` | ✗ |
| `children` | `any` | let/var | `connections.get( parseInt( nodeID ) ).children` | ✗ |
| `tracks` | `any[]` | let/var | `[]` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `tracks` | `any[]` | let/var | `[]` | ✗ |
| `initialPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `initialScale` | `any` | let/var | `new Vector3()` | ✗ |
| `times` | `any` | let/var | `*not shown*` | ✗ |
| `values` | `any` | let/var | `*not shown*` | ✗ |
| `quaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `euler` | `any` | let/var | `new Euler()` | ✗ |
| `quaternionValues` | `any[]` | let/var | `[]` | ✗ |
| `curves` | `any` | let/var | `rawTracks.DeformPercent.curves.morph` | ✗ |
| `morphNum` | `any` | let/var | `sceneGraph.getObjectByName( rawTracks.modelName ).morphTargetDictionary[ rawT...` | ✗ |
| `times` | `any[]` | let/var | `[]` | ✗ |
| `targetIndex` | `number` | let/var | `1` | ✗ |
| `lastValue` | `any` | let/var | `times[ 0 ]` | ✗ |
| `currentValue` | `any` | let/var | `times[ i ]` | ✗ |
| `prevValue` | `any` | let/var | `initialValue` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `xIndex` | `number` | let/var | `- 1` | ✗ |
| `yIndex` | `number` | let/var | `- 1` | ✗ |
| `zIndex` | `number` | let/var | `- 1` | ✗ |
| `xValue` | `any` | let/var | `curves.x.values[ xIndex ]` | ✗ |
| `yValue` | `any` | let/var | `curves.y.values[ yIndex ]` | ✗ |
| `zValue` | `any` | let/var | `curves.z.values[ zIndex ]` | ✗ |
| `times` | `any[]` | let/var | `[]` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `initialValue` | `any[]` | let/var | `[ curvex.values[ i - 1 ], curvey.values[ i - 1 ], curvez.values[ i - 1 ], ]` | ✗ |
| `currentValue` | `any[]` | let/var | `[ curvex.values[ i ], curvey.values[ i ], curvez.values[ i ], ]` | ✗ |
| `valuesSpan` | `number[]` | let/var | `[ currentValue[ 0 ] - initialValue[ 0 ], currentValue[ 1 ] - initialValue[ 1 ...` | ✗ |
| `absoluteSpan` | `number[]` | let/var | `[ Math.abs( valuesSpan[ 0 ] ), Math.abs( valuesSpan[ 1 ] ), Math.abs( valuesS...` | ✗ |
| `numSubIntervals` | `number` | let/var | `maxAbsSpan / 180` | ✗ |
| `E1` | `any` | let/var | `new Euler( ...initialValueRad, eulerOrder )` | ✗ |
| `E2` | `any` | let/var | `new Euler( ...currentValueRad, eulerOrder )` | ✗ |
| `initialTime` | `any` | let/var | `curvex.times[ i - 1 ]` | ✗ |
| `timeSpan` | `number` | let/var | `curvex.times[ i ] - initialTime` | ✗ |
| `Q` | `any` | let/var | `new Quaternion()` | ✗ |
| `E` | `any` | let/var | `new Euler()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `node` | `{ name: any; }` | let/var | `{ name: nodeName }` | ✗ |
| `id` | `any` | let/var | `attrs[ 0 ]` | ✗ |
| `name` | `string` | let/var | `''` | ✗ |
| `type` | `string` | let/var | `''` | ✗ |
| `parentName` | `any` | let/var | `currentNode.name` | ✗ |
| `innerPropName` | `any` | let/var | `props[ 0 ]` | ✗ |
| `innerPropType1` | `any` | let/var | `props[ 1 ]` | ✗ |
| `innerPropType2` | `any` | let/var | `props[ 2 ]` | ✗ |
| `innerPropFlag` | `any` | let/var | `props[ 3 ]` | ✗ |
| `innerPropValue` | `any` | let/var | `props[ 4 ]` | ✗ |
| `reader` | `BinaryReader` | let/var | `new BinaryReader( buffer )` | ✗ |
| `allNodes` | `FBXTree` | let/var | `new FBXTree()` | ✗ |
| `node` | `{ singleProperty: boolean; propertyLi...` | let/var | `{}` | ✗ |
| `endOffset` | `any` | let/var | `( version >= 7500 ) ? reader.getUint64() : reader.getUint32()` | ✗ |
| `numProperties` | `any` | let/var | `( version >= 7500 ) ? reader.getUint64() : reader.getUint32()` | ✗ |
| `propertyList` | `any[]` | let/var | `[]` | ✗ |
| `id` | `any` | let/var | `propertyList.length > 0 ? propertyList[ 0 ] : ''` | ✗ |
| `attrName` | `any` | let/var | `propertyList.length > 1 ? propertyList[ 1 ] : ''` | ✗ |
| `attrType` | `any` | let/var | `propertyList.length > 2 ? propertyList[ 2 ] : ''` | ✗ |
| `value` | `any` | let/var | `subNode.propertyList[ 0 ]` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `innerPropName` | `any` | let/var | `subNode.propertyList[ 0 ]` | ✗ |
| `innerPropType1` | `any` | let/var | `subNode.propertyList[ 1 ]` | ✗ |
| `innerPropType2` | `any` | let/var | `subNode.propertyList[ 2 ]` | ✗ |
| `innerPropFlag` | `any` | let/var | `subNode.propertyList[ 3 ]` | ✗ |
| `innerPropValue` | `any` | let/var | `*not shown*` | ✗ |
| `length` | `any` | let/var | `*not shown*` | ✗ |
| `reader2` | `BinaryReader` | let/var | `new BinaryReader( data.buffer )` | ✗ |
| `a` | `any[]` | let/var | `[]` | ✗ |
| `a` | `any[]` | let/var | `[]` | ✗ |
| `low` | `any` | let/var | `*not shown*` | ✗ |
| `high` | `any` | let/var | `*not shown*` | ✗ |
| `a` | `any[]` | let/var | `[]` | ✗ |
| `low` | `any` | let/var | `*not shown*` | ✗ |
| `high` | `any` | let/var | `*not shown*` | ✗ |
| `a` | `any[]` | let/var | `[]` | ✗ |
| `a` | `any[]` | let/var | `[]` | ✗ |
| `start` | `number` | let/var | `this.offset` | ✗ |
| `a` | `Uint8Array<any>` | let/var | `new Uint8Array( this.dv.buffer, start, size )` | ✗ |
| `CORRECT` | `"Kaydara FBX Binary \0"` | let/var | `'Kaydara\u0020FBX\u0020Binary\u0020\u0020\0'` | ✗ |
| `CORRECT` | `string[]` | let/var | `[ 'K', 'a', 'y', 'd', 'a', 'r', 'a', '\\', 'F', 'B', 'X', '\\', 'B', 'i', 'n'...` | ✗ |
| `cursor` | `number` | let/var | `0` | ✗ |
| `result` | `any` | let/var | `text[ offset - 1 ]` | ✗ |
| `versionRegExp` | `RegExp` | let/var | `/FBXVersion: (\d+)/` | ✗ |
| `dataArray` | `any[]` | let/var | `[]` | ✗ |
| `index` | `any` | let/var | `*not shown*` | ✗ |
| `from` | `number` | let/var | `index * infoObject.dataSize` | ✗ |
| `to` | `any` | let/var | `from + infoObject.dataSize` | ✗ |
| `tempEuler` | `any` | let/var | `new Euler()` | ✗ |
| `tempVec` | `any` | let/var | `new Vector3()` | ✗ |
| `lTranslationM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lPreRotationM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lRotationM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lPostRotationM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lScalingM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lScalingPivotM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lScalingOffsetM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lRotationOffsetM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lRotationPivotM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lParentGX` | `any` | let/var | `new Matrix4()` | ✗ |
| `lParentLX` | `any` | let/var | `new Matrix4()` | ✗ |
| `lGlobalT` | `any` | let/var | `new Matrix4()` | ✗ |
| `inheritType` | `any` | let/var | `( transformData.inheritType ) ? transformData.inheritType : 0` | ✗ |
| `lParentGRM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lParentTM` | `any` | let/var | `new Matrix4()` | ✗ |
| `lLSM` | `any` | let/var | `lScalingM` | ✗ |
| `lGlobalRS` | `any` | let/var | `new Matrix4()` | ✗ |
| `enums` | `string[]` | let/var | `[ 'ZYX', // -> XYZ extrinsic 'YZX', // -> XZY extrinsic 'XZY', // -> YZX extr...` | ✗ |


---

## Functions

### `FBXLoader.load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded FBX asset
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

- `LoaderUtils.extractUrlBase`
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

		const path = ( scope.path === '' ) ? LoaderUtils.extractUrlBase( url ) : scope.path;

		const loader = new FileLoader( this.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );

		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer, path ) );

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

### `FBXLoader.parse(FBXBuffer: ArrayBuffer, path: string): Group`

**JSDoc:**
```typescript
/**
	 * Parses the given FBX data and returns the resulting group.
	 *
	 * @param {ArrayBuffer} FBXBuffer - The raw FBX data as an array buffer.
	 * @param {string} path - The URL base path.
	 * @return {Group} An object representing the parsed asset.
	 */
```

**Parameters:**

- **`FBXBuffer`** `ArrayBuffer`
- **`path`** `string`

**Returns:** `Group`

**Calls:**

- `isFbxFormatBinary`
- `new BinaryParser().parse`
- `convertArrayBufferToString`
- `isFbxFormatASCII`
- `getFbxVersion`
- `new TextParser().parse`
- `new TextureLoader( this.manager ).setPath( this.resourcePath || path ).setCrossOrigin`
- `new FBXTreeParser( textureLoader, this.manager ).parse`

**Internal Comments:**
```
// console.log( fbxTree ); (x2)
```

<details><summary>Code</summary>

```typescript
parse( FBXBuffer, path ) {

		if ( isFbxFormatBinary( FBXBuffer ) ) {

			fbxTree = new BinaryParser().parse( FBXBuffer );

		} else {

			const FBXText = convertArrayBufferToString( FBXBuffer );

			if ( ! isFbxFormatASCII( FBXText ) ) {

				throw new Error( 'THREE.FBXLoader: Unknown format.' );

			}

			if ( getFbxVersion( FBXText ) < 7000 ) {

				throw new Error( 'THREE.FBXLoader: FBX version not supported, FileVersion: ' + getFbxVersion( FBXText ) );

			}

			fbxTree = new TextParser().parse( FBXText );

		}

		// console.log( fbxTree );

		const textureLoader = new TextureLoader( this.manager ).setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		return new FBXTreeParser( textureLoader, this.manager ).parse( fbxTree );

	}
```
</details>

### `FBXTreeParser.parse(): any`

**Returns:** `any`

**Calls:**

- `this.parseConnections`
- `this.parseImages`
- `this.parseTextures`
- `this.parseMaterials`
- `this.parseDeformers`
- `new GeometryParser().parse`
- `this.parseScene`

<details><summary>Code</summary>

```typescript
parse() {

		connections = this.parseConnections();

		const images = this.parseImages();
		const textures = this.parseTextures( images );
		const materials = this.parseMaterials( textures );
		const deformers = this.parseDeformers();
		const geometryMap = new GeometryParser().parse( deformers );

		this.parseScene( deformers, geometryMap, materials );

		return sceneGraph;

	}
```
</details>

### `FBXTreeParser.parseConnections(): Map<any, any>`

**Returns:** `Map<any, any>`

**Calls:**

- `rawConnections.forEach`
- `connectionMap.has`
- `connectionMap.set`
- `connectionMap.get( fromID ).parents.push`
- `connectionMap.get( toID ).children.push`

<details><summary>Code</summary>

```typescript
parseConnections() {

		const connectionMap = new Map();

		if ( 'Connections' in fbxTree ) {

			const rawConnections = fbxTree.Connections.connections;

			rawConnections.forEach( function ( rawConnection ) {

				const fromID = rawConnection[ 0 ];
				const toID = rawConnection[ 1 ];
				const relationship = rawConnection[ 2 ];

				if ( ! connectionMap.has( fromID ) ) {

					connectionMap.set( fromID, {
						parents: [],
						children: []
					} );

				}

				const parentRelationship = { ID: toID, relationship: relationship };
				connectionMap.get( fromID ).parents.push( parentRelationship );

				if ( ! connectionMap.has( toID ) ) {

					connectionMap.set( toID, {
						parents: [],
						children: []
					} );

				}

				const childRelationship = { ID: fromID, relationship: relationship };
				connectionMap.get( toID ).children.push( childRelationship );

			} );

		}

		return connectionMap;

	}
```
</details>

### `FBXTreeParser.parseImages(): {}`

**Returns:** `{}`

**Calls:**

- `parseInt`
- `this.parseImage`
- `images[ id ].split( '\\' ).pop`

**Internal Comments:**
```
// raw image data is in videoNode.Content
```

<details><summary>Code</summary>

```typescript
parseImages() {

		const images = {};
		const blobs = {};

		if ( 'Video' in fbxTree.Objects ) {

			const videoNodes = fbxTree.Objects.Video;

			for ( const nodeID in videoNodes ) {

				const videoNode = videoNodes[ nodeID ];

				const id = parseInt( nodeID );

				images[ id ] = videoNode.RelativeFilename || videoNode.Filename;

				// raw image data is in videoNode.Content
				if ( 'Content' in videoNode ) {

					const arrayBufferContent = ( videoNode.Content instanceof ArrayBuffer ) && ( videoNode.Content.byteLength > 0 );
					const base64Content = ( typeof videoNode.Content === 'string' ) && ( videoNode.Content !== '' );

					if ( arrayBufferContent || base64Content ) {

						const image = this.parseImage( videoNodes[ nodeID ] );

						blobs[ videoNode.RelativeFilename || videoNode.Filename ] = image;

					}

				}

			}

		}

		for ( const id in images ) {

			const filename = images[ id ];

			if ( blobs[ filename ] !== undefined ) images[ id ] = blobs[ filename ];
			else images[ id ] = images[ id ].split( '\\' ).pop();

		}

		return images;

	}
```
</details>

### `FBXTreeParser.parseImage(videoNode: any): string`

**Parameters:**

- **`videoNode`** `any`

**Returns:** `string`

**Calls:**

- `fileName.slice( fileName.lastIndexOf( '.' ) + 1 ).toLowerCase`
- `this.manager.getHandler`
- `console.warn`
- `window.URL.createObjectURL`

<details><summary>Code</summary>

```typescript
parseImage( videoNode ) {

		const content = videoNode.Content;
		const fileName = videoNode.RelativeFilename || videoNode.Filename;
		const extension = fileName.slice( fileName.lastIndexOf( '.' ) + 1 ).toLowerCase();

		let type;

		switch ( extension ) {

			case 'bmp':

				type = 'image/bmp';
				break;

			case 'jpg':
			case 'jpeg':

				type = 'image/jpeg';
				break;

			case 'png':

				type = 'image/png';
				break;

			case 'tif':

				type = 'image/tiff';
				break;

			case 'tga':

				if ( this.manager.getHandler( '.tga' ) === null ) {

					console.warn( 'FBXLoader: TGA loader not found, skipping ', fileName );

				}

				type = 'image/tga';
				break;

			case 'webp':

				type = 'image/webp';
				break;

			default:

				console.warn( 'FBXLoader: Image type "' + extension + '" is not supported.' );
				return;

		}

		if ( typeof content === 'string' ) { // ASCII format

			return 'data:' + type + ';base64,' + content;

		} else { // Binary Format

			const array = new Uint8Array( content );
			return window.URL.createObjectURL( new Blob( [ array ], { type: type } ) );

		}

	}
```
</details>

### `FBXTreeParser.parseTextures(images: any): Map<any, any>`

**Parameters:**

- **`images`** `any`

**Returns:** `Map<any, any>`

**Calls:**

- `this.parseTexture`
- `textureMap.set`
- `parseInt`

<details><summary>Code</summary>

```typescript
parseTextures( images ) {

		const textureMap = new Map();

		if ( 'Texture' in fbxTree.Objects ) {

			const textureNodes = fbxTree.Objects.Texture;
			for ( const nodeID in textureNodes ) {

				const texture = this.parseTexture( textureNodes[ nodeID ], images );
				textureMap.set( parseInt( nodeID ), texture );

			}

		}

		return textureMap;

	}
```
</details>

### `FBXTreeParser.parseTexture(textureNode: any, images: any): any`

**Parameters:**

- **`textureNode`** `any`
- **`images`** `any`

**Returns:** `any`

**Calls:**

- `this.loadTexture`

**Internal Comments:**
```
// http://download.autodesk.com/us/fbx/SDKdocs/FBX_SDK_Help/files/fbxsdkref/class_k_fbx_texture.html#889640e63e2e681259ea81061b85143a (x4)
// 0: repeat(default), 1: clamp (x4)
```

<details><summary>Code</summary>

```typescript
parseTexture( textureNode, images ) {

		const texture = this.loadTexture( textureNode, images );

		texture.ID = textureNode.id;

		texture.name = textureNode.attrName;

		const wrapModeU = textureNode.WrapModeU;
		const wrapModeV = textureNode.WrapModeV;

		const valueU = wrapModeU !== undefined ? wrapModeU.value : 0;
		const valueV = wrapModeV !== undefined ? wrapModeV.value : 0;

		// http://download.autodesk.com/us/fbx/SDKdocs/FBX_SDK_Help/files/fbxsdkref/class_k_fbx_texture.html#889640e63e2e681259ea81061b85143a
		// 0: repeat(default), 1: clamp

		texture.wrapS = valueU === 0 ? RepeatWrapping : ClampToEdgeWrapping;
		texture.wrapT = valueV === 0 ? RepeatWrapping : ClampToEdgeWrapping;

		if ( 'Scaling' in textureNode ) {

			const values = textureNode.Scaling.value;

			texture.repeat.x = values[ 0 ];
			texture.repeat.y = values[ 1 ];

		}

		if ( 'Translation' in textureNode ) {

			const values = textureNode.Translation.value;

			texture.offset.x = values[ 0 ];
			texture.offset.y = values[ 1 ];

		}

		return texture;

	}
```
</details>

### `FBXTreeParser.loadTexture(textureNode: any, images: any): any`

**Parameters:**

- **`textureNode`** `any`
- **`images`** `any`

**Returns:** `any`

**Calls:**

- `textureNode.FileName.split( '.' ).pop().toLowerCase`
- `this.manager.getHandler`
- `loader.setPath`
- `connections.get`
- `fileName.indexOf`
- `console.warn`
- `loader.load`

**Internal Comments:**
```
// revert to initial path (x4)
```

<details><summary>Code</summary>

```typescript
loadTexture( textureNode, images ) {

		const extension = textureNode.FileName.split( '.' ).pop().toLowerCase();

		let loader = this.manager.getHandler( `.${extension}` );
		if ( loader === null ) loader = this.textureLoader;

		const loaderPath = loader.path;

		if ( ! loaderPath ) {

			loader.setPath( this.textureLoader.path );

		}

		const children = connections.get( textureNode.id ).children;

		let fileName;

		if ( children !== undefined && children.length > 0 && images[ children[ 0 ].ID ] !== undefined ) {

			fileName = images[ children[ 0 ].ID ];

			if ( fileName.indexOf( 'blob:' ) === 0 || fileName.indexOf( 'data:' ) === 0 ) {

				loader.setPath( undefined );

			}

		}

		if ( fileName === undefined ) {

			console.warn( 'FBXLoader: Undefined filename, creating placeholder texture.' );
			return new Texture();

		}

		const texture = loader.load( fileName );

		// revert to initial path
		loader.setPath( loaderPath );

		return texture;

	}
```
</details>

### `FBXTreeParser.parseMaterials(textureMap: any): Map<any, any>`

**Parameters:**

- **`textureMap`** `any`

**Returns:** `Map<any, any>`

**Calls:**

- `this.parseMaterial`
- `materialMap.set`
- `parseInt`

<details><summary>Code</summary>

```typescript
parseMaterials( textureMap ) {

		const materialMap = new Map();

		if ( 'Material' in fbxTree.Objects ) {

			const materialNodes = fbxTree.Objects.Material;

			for ( const nodeID in materialNodes ) {

				const material = this.parseMaterial( materialNodes[ nodeID ], textureMap );

				if ( material !== null ) materialMap.set( parseInt( nodeID ), material );

			}

		}

		return materialMap;

	}
```
</details>

### `FBXTreeParser.parseMaterial(materialNode: any, textureMap: any): any`

**Parameters:**

- **`materialNode`** `any`
- **`textureMap`** `any`

**Returns:** `any`

**Calls:**

- `connections.has`
- `this.parseParameters`
- `type.toLowerCase`
- `console.warn`
- `material.setValues`

**Internal Comments:**
```
// Case where FBX wraps shading model in property object.
// Ignore unused materials which don't have any connections.
```

<details><summary>Code</summary>

```typescript
parseMaterial( materialNode, textureMap ) {

		const ID = materialNode.id;
		const name = materialNode.attrName;
		let type = materialNode.ShadingModel;

		// Case where FBX wraps shading model in property object.
		if ( typeof type === 'object' ) {

			type = type.value;

		}

		// Ignore unused materials which don't have any connections.
		if ( ! connections.has( ID ) ) return null;

		const parameters = this.parseParameters( materialNode, textureMap, ID );

		let material;

		switch ( type.toLowerCase() ) {

			case 'phong':
				material = new MeshPhongMaterial();
				break;
			case 'lambert':
				material = new MeshLambertMaterial();
				break;
			default:
				console.warn( 'THREE.FBXLoader: unknown material type "%s". Defaulting to MeshPhongMaterial.', type );
				material = new MeshPhongMaterial();
				break;

		}

		material.setValues( parameters );
		material.name = name;

		return material;

	}
```
</details>

### `FBXTreeParser.parseParameters(materialNode: any, textureMap: any, ID: any): { bumpScale: any; color: any; displacementScale: any; emissive: any; emissiveIntensity: number; opacity: number; transparent: boolean; reflectivity: any; shininess: any; specular: any; }`

**Parameters:**

- **`materialNode`** `any`
- **`textureMap`** `any`
- **`ID`** `any`

**Returns:** `{ bumpScale: any; color: any; displacementScale: any; emissive: any; emissiveIntensity: number; opacity: number; transparent: boolean; reflectivity: any; shininess: any; specular: any; }`

**Calls:**

- `ColorManagement.colorSpaceToWorking`
- `new Color().fromArray`
- `parseFloat`
- `connections.get( ID ).children.forEach`
- `scope.getTexture`
- `console.warn`

**Internal Comments:**
```
// The blender exporter exports diffuse here instead of in materialNode.Diffuse (x4)
// The blender exporter exports emissive color here instead of in materialNode.Emissive (x4)
// the transparency handling is implemented based on Blender/Unity's approach: https://github.com/sobotka/blender-addons/blob/7d80f2f97161fc8e353a657b179b9aa1f8e5280b/io_scene_fbx/import_fbx.py#L1444-L1459 (x4)
// The blender exporter exports specular color here instead of in materialNode.Specular (x4)
```

<details><summary>Code</summary>

```typescript
parseParameters( materialNode, textureMap, ID ) {

		const parameters = {};

		if ( materialNode.BumpFactor ) {

			parameters.bumpScale = materialNode.BumpFactor.value;

		}

		if ( materialNode.Diffuse ) {

			parameters.color = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.Diffuse.value ), SRGBColorSpace );

		} else if ( materialNode.DiffuseColor && ( materialNode.DiffuseColor.type === 'Color' || materialNode.DiffuseColor.type === 'ColorRGB' ) ) {

			// The blender exporter exports diffuse here instead of in materialNode.Diffuse
			parameters.color = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.DiffuseColor.value ), SRGBColorSpace );

		}

		if ( materialNode.DisplacementFactor ) {

			parameters.displacementScale = materialNode.DisplacementFactor.value;

		}

		if ( materialNode.Emissive ) {

			parameters.emissive = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.Emissive.value ), SRGBColorSpace );

		} else if ( materialNode.EmissiveColor && ( materialNode.EmissiveColor.type === 'Color' || materialNode.EmissiveColor.type === 'ColorRGB' ) ) {

			// The blender exporter exports emissive color here instead of in materialNode.Emissive
			parameters.emissive = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.EmissiveColor.value ), SRGBColorSpace );

		}

		if ( materialNode.EmissiveFactor ) {

			parameters.emissiveIntensity = parseFloat( materialNode.EmissiveFactor.value );

		}

		// the transparency handling is implemented based on Blender/Unity's approach: https://github.com/sobotka/blender-addons/blob/7d80f2f97161fc8e353a657b179b9aa1f8e5280b/io_scene_fbx/import_fbx.py#L1444-L1459

		parameters.opacity = 1 - ( materialNode.TransparencyFactor ? parseFloat( materialNode.TransparencyFactor.value ) : 0 );

		if ( parameters.opacity === 1 || parameters.opacity === 0 ) {

			parameters.opacity = ( materialNode.Opacity ? parseFloat( materialNode.Opacity.value ) : null );

			if ( parameters.opacity === null ) {

				parameters.opacity = 1 - ( materialNode.TransparentColor ? parseFloat( materialNode.TransparentColor.value[ 0 ] ) : 0 );

			}

		}

		if ( parameters.opacity < 1.0 ) {

			parameters.transparent = true;

		}

		if ( materialNode.ReflectionFactor ) {

			parameters.reflectivity = materialNode.ReflectionFactor.value;

		}

		if ( materialNode.Shininess ) {

			parameters.shininess = materialNode.Shininess.value;

		}

		if ( materialNode.Specular ) {

			parameters.specular = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.Specular.value ), SRGBColorSpace );

		} else if ( materialNode.SpecularColor && materialNode.SpecularColor.type === 'Color' ) {

			// The blender exporter exports specular color here instead of in materialNode.Specular
			parameters.specular = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.SpecularColor.value ), SRGBColorSpace );

		}

		const scope = this;
		connections.get( ID ).children.forEach( function ( child ) {

			const type = child.relationship;

			switch ( type ) {

				case 'Bump':
					parameters.bumpMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'Maya|TEX_ao_map':
					parameters.aoMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'DiffuseColor':
				case 'Maya|TEX_color_map':
					parameters.map = scope.getTexture( textureMap, child.ID );
					if ( parameters.map !== undefined ) {

						parameters.map.colorSpace = SRGBColorSpace;

					}

					break;

				case 'DisplacementColor':
					parameters.displacementMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'EmissiveColor':
					parameters.emissiveMap = scope.getTexture( textureMap, child.ID );
					if ( parameters.emissiveMap !== undefined ) {

						parameters.emissiveMap.colorSpace = SRGBColorSpace;

					}

					break;

				case 'NormalMap':
				case 'Maya|TEX_normal_map':
					parameters.normalMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'ReflectionColor':
					parameters.envMap = scope.getTexture( textureMap, child.ID );
					if ( parameters.envMap !== undefined ) {

						parameters.envMap.mapping = EquirectangularReflectionMapping;
						parameters.envMap.colorSpace = SRGBColorSpace;

					}

					break;

				case 'SpecularColor':
					parameters.specularMap = scope.getTexture( textureMap, child.ID );
					if ( parameters.specularMap !== undefined ) {

						parameters.specularMap.colorSpace = SRGBColorSpace;

					}

					break;

				case 'TransparentColor':
				case 'TransparencyFactor':
					parameters.alphaMap = scope.getTexture( textureMap, child.ID );
					parameters.transparent = true;
					break;

				case 'AmbientColor':
				case 'ShininessExponent': // AKA glossiness map
				case 'SpecularFactor': // AKA specularLevel
				case 'VectorDisplacementColor': // NOTE: Seems to be a copy of DisplacementColor
				default:
					console.warn( 'THREE.FBXLoader: %s map is not supported in three.js, skipping texture.', type );
					break;

			}

		} );

		return parameters;

	}
```
</details>

### `FBXTreeParser.getTexture(textureMap: any, id: any): any`

**Parameters:**

- **`textureMap`** `any`
- **`id`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`
- `connections.get`
- `textureMap.get`

**Internal Comments:**
```
// if the texture is a layered texture, just use the first layer and issue a warning
```

<details><summary>Code</summary>

```typescript
getTexture( textureMap, id ) {

		// if the texture is a layered texture, just use the first layer and issue a warning
		if ( 'LayeredTexture' in fbxTree.Objects && id in fbxTree.Objects.LayeredTexture ) {

			console.warn( 'THREE.FBXLoader: layered textures are not supported in three.js. Discarding all but first layer.' );
			id = connections.get( id ).children[ 0 ].ID;

		}

		return textureMap.get( id );

	}
```
</details>

### `FBXTreeParser.parseDeformers(): { skeletons: {}; morphTargets: {}; }`

**Returns:** `{ skeletons: {}; morphTargets: {}; }`

**Calls:**

- `connections.get`
- `parseInt`
- `this.parseSkeleton`
- `console.warn`
- `this.parseMorphTargets`

<details><summary>Code</summary>

```typescript
parseDeformers() {

		const skeletons = {};
		const morphTargets = {};

		if ( 'Deformer' in fbxTree.Objects ) {

			const DeformerNodes = fbxTree.Objects.Deformer;

			for ( const nodeID in DeformerNodes ) {

				const deformerNode = DeformerNodes[ nodeID ];

				const relationships = connections.get( parseInt( nodeID ) );

				if ( deformerNode.attrType === 'Skin' ) {

					const skeleton = this.parseSkeleton( relationships, DeformerNodes );
					skeleton.ID = nodeID;

					if ( relationships.parents.length > 1 ) console.warn( 'THREE.FBXLoader: skeleton attached to more than one geometry is not supported.' );
					skeleton.geometryID = relationships.parents[ 0 ].ID;

					skeletons[ nodeID ] = skeleton;

				} else if ( deformerNode.attrType === 'BlendShape' ) {

					const morphTarget = {
						id: nodeID,
					};

					morphTarget.rawTargets = this.parseMorphTargets( relationships, DeformerNodes );
					morphTarget.id = nodeID;

					if ( relationships.parents.length > 1 ) console.warn( 'THREE.FBXLoader: morph target attached to more than one geometry is not supported.' );

					morphTargets[ nodeID ] = morphTarget;

				}

			}

		}

		return {

			skeletons: skeletons,
			morphTargets: morphTargets,

		};

	}
```
</details>

### `FBXTreeParser.parseSkeleton(relationships: any, deformerNodes: any): { rawBones: any[]; bones: any[]; }`

**Parameters:**

- **`relationships`** `any`
- **`deformerNodes`** `any`

**Returns:** `{ rawBones: any[]; bones: any[]; }`

**Calls:**

- `relationships.children.forEach`
- `new Matrix4().fromArray`
- `rawBones.push`

<details><summary>Code</summary>

```typescript
parseSkeleton( relationships, deformerNodes ) {

		const rawBones = [];

		relationships.children.forEach( function ( child ) {

			const boneNode = deformerNodes[ child.ID ];

			if ( boneNode.attrType !== 'Cluster' ) return;

			const rawBone = {

				ID: child.ID,
				indices: [],
				weights: [],
				transformLink: new Matrix4().fromArray( boneNode.TransformLink.a ),
				// transform: new Matrix4().fromArray( boneNode.Transform.a ),
				// linkMode: boneNode.Mode,

			};

			if ( 'Indexes' in boneNode ) {

				rawBone.indices = boneNode.Indexes.a;
				rawBone.weights = boneNode.Weights.a;

			}

			rawBones.push( rawBone );

		} );

		return {

			rawBones: rawBones,
			bones: []

		};

	}
```
</details>

### `FBXTreeParser.parseMorphTargets(relationships: any, deformerNodes: any): { name: any; initialWeight: any; id: any; fullWeights: any; }[]`

**Parameters:**

- **`relationships`** `any`
- **`deformerNodes`** `any`

**Returns:** `{ name: any; initialWeight: any; id: any; fullWeights: any; }[]`

**Calls:**

- `connections.get( parseInt( child.ID ) ).children.filter`
- `rawMorphTargets.push`

<details><summary>Code</summary>

```typescript
parseMorphTargets( relationships, deformerNodes ) {

		const rawMorphTargets = [];

		for ( let i = 0; i < relationships.children.length; i ++ ) {

			const child = relationships.children[ i ];

			const morphTargetNode = deformerNodes[ child.ID ];

			const rawMorphTarget = {

				name: morphTargetNode.attrName,
				initialWeight: morphTargetNode.DeformPercent,
				id: morphTargetNode.id,
				fullWeights: morphTargetNode.FullWeights.a

			};

			if ( morphTargetNode.attrType !== 'BlendShapeChannel' ) return;

			rawMorphTarget.geoID = connections.get( parseInt( child.ID ) ).children.filter( function ( child ) {

				return child.relationship === undefined;

			} )[ 0 ].ID;

			rawMorphTargets.push( rawMorphTarget );

		}

		return rawMorphTargets;

	}
```
</details>

### `FBXTreeParser.parseScene(deformers: any, geometryMap: any, materialMap: any): void`

**Parameters:**

- **`deformers`** `any`
- **`geometryMap`** `any`
- **`materialMap`** `any`

**Returns:** `void`

**Calls:**

- `this.parseModels`
- `modelMap.forEach`
- `scope.setLookAtProperties`
- `connections.get`
- `parentConnections.forEach`
- `modelMap.get`
- `parent.add`
- `sceneGraph.add`
- `this.bindSkeleton`
- `this.addGlobalSceneSettings`
- `sceneGraph.traverse`
- `generateTransform`
- `node.applyMatrix4`
- `node.updateWorldMatrix`
- `new AnimationParser().parse`

**Internal Comments:**
```
// if all the models where already combined in a single group, just return that
```

<details><summary>Code</summary>

```typescript
parseScene( deformers, geometryMap, materialMap ) {

		sceneGraph = new Group();

		const modelMap = this.parseModels( deformers.skeletons, geometryMap, materialMap );

		const modelNodes = fbxTree.Objects.Model;

		const scope = this;
		modelMap.forEach( function ( model ) {

			const modelNode = modelNodes[ model.ID ];
			scope.setLookAtProperties( model, modelNode );

			const parentConnections = connections.get( model.ID ).parents;

			parentConnections.forEach( function ( connection ) {

				const parent = modelMap.get( connection.ID );
				if ( parent !== undefined ) parent.add( model );

			} );

			if ( model.parent === null ) {

				sceneGraph.add( model );

			}


		} );

		this.bindSkeleton( deformers.skeletons, geometryMap, modelMap );

		this.addGlobalSceneSettings();

		sceneGraph.traverse( function ( node ) {

			if ( node.userData.transformData ) {

				if ( node.parent ) {

					node.userData.transformData.parentMatrix = node.parent.matrix;
					node.userData.transformData.parentMatrixWorld = node.parent.matrixWorld;

				}

				const transform = generateTransform( node.userData.transformData );

				node.applyMatrix4( transform );
				node.updateWorldMatrix();

			}

		} );

		const animations = new AnimationParser().parse();

		// if all the models where already combined in a single group, just return that
		if ( sceneGraph.children.length === 1 && sceneGraph.children[ 0 ].isGroup ) {

			sceneGraph.children[ 0 ].animations = animations;
			sceneGraph = sceneGraph.children[ 0 ];

		}

		sceneGraph.animations = animations;

	}
```
</details>

### `FBXTreeParser.parseModels(skeletons: any, geometryMap: any, materialMap: any): Map<any, any>`

**Parameters:**

- **`skeletons`** `any`
- **`geometryMap`** `any`
- **`materialMap`** `any`

**Returns:** `Map<any, any>`

**Calls:**

- `parseInt`
- `connections.get`
- `this.buildSkeleton`
- `this.createCamera`
- `this.createLight`
- `this.createMesh`
- `this.createCurve`
- `PropertyBinding.sanitizeNodeName`
- `this.getTransformData`
- `modelMap.set`

<details><summary>Code</summary>

```typescript
parseModels( skeletons, geometryMap, materialMap ) {

		const modelMap = new Map();
		const modelNodes = fbxTree.Objects.Model;

		for ( const nodeID in modelNodes ) {

			const id = parseInt( nodeID );
			const node = modelNodes[ nodeID ];
			const relationships = connections.get( id );

			let model = this.buildSkeleton( relationships, skeletons, id, node.attrName );

			if ( ! model ) {

				switch ( node.attrType ) {

					case 'Camera':
						model = this.createCamera( relationships );
						break;
					case 'Light':
						model = this.createLight( relationships );
						break;
					case 'Mesh':
						model = this.createMesh( relationships, geometryMap, materialMap );
						break;
					case 'NurbsCurve':
						model = this.createCurve( relationships, geometryMap );
						break;
					case 'LimbNode':
					case 'Root':
						model = new Bone();
						break;
					case 'Null':
					default:
						model = new Group();
						break;

				}

				model.name = node.attrName ? PropertyBinding.sanitizeNodeName( node.attrName ) : '';
				model.userData.originalName = node.attrName;

				model.ID = id;

			}

			this.getTransformData( model, node );
			modelMap.set( id, model );

		}

		return modelMap;

	}
```
</details>

### `FBXTreeParser.buildSkeleton(relationships: any, skeletons: any, id: any, name: any): any`

**Parameters:**

- **`relationships`** `any`
- **`skeletons`** `any`
- **`id`** `any`
- **`name`** `any`

**Returns:** `any`

**Calls:**

- `relationships.parents.forEach`
- `skeleton.rawBones.forEach`
- `bone.matrixWorld.copy`
- `PropertyBinding.sanitizeNodeName`
- `bone.add`

**Internal Comments:**
```
// set name and id here - otherwise in cases where "subBone" is created it will not have a name / id (x4)
// In cases where a bone is shared between multiple meshes
// duplicate the bone here and add it as a child of the first bone
```

<details><summary>Code</summary>

```typescript
buildSkeleton( relationships, skeletons, id, name ) {

		let bone = null;

		relationships.parents.forEach( function ( parent ) {

			for ( const ID in skeletons ) {

				const skeleton = skeletons[ ID ];

				skeleton.rawBones.forEach( function ( rawBone, i ) {

					if ( rawBone.ID === parent.ID ) {

						const subBone = bone;
						bone = new Bone();

						bone.matrixWorld.copy( rawBone.transformLink );

						// set name and id here - otherwise in cases where "subBone" is created it will not have a name / id

						bone.name = name ? PropertyBinding.sanitizeNodeName( name ) : '';
						bone.userData.originalName = name;
						bone.ID = id;

						skeleton.bones[ i ] = bone;

						// In cases where a bone is shared between multiple meshes
						// duplicate the bone here and add it as a child of the first bone
						if ( subBone !== null ) {

							bone.add( subBone );

						}

					}

				} );

			}

		} );

		return bone;

	}
```
</details>

### `FBXTreeParser.createCamera(relationships: any): any`

**Parameters:**

- **`relationships`** `any`

**Returns:** `any`

**Calls:**

- `relationships.children.forEach`
- `model.setFocalLength`
- `console.warn`

<details><summary>Code</summary>

```typescript
createCamera( relationships ) {

		let model;
		let cameraAttribute;

		relationships.children.forEach( function ( child ) {

			const attr = fbxTree.Objects.NodeAttribute[ child.ID ];

			if ( attr !== undefined ) {

				cameraAttribute = attr;

			}

		} );

		if ( cameraAttribute === undefined ) {

			model = new Object3D();

		} else {

			let type = 0;
			if ( cameraAttribute.CameraProjectionType !== undefined && cameraAttribute.CameraProjectionType.value === 1 ) {

				type = 1;

			}

			let nearClippingPlane = 1;
			if ( cameraAttribute.NearPlane !== undefined ) {

				nearClippingPlane = cameraAttribute.NearPlane.value / 1000;

			}

			let farClippingPlane = 1000;
			if ( cameraAttribute.FarPlane !== undefined ) {

				farClippingPlane = cameraAttribute.FarPlane.value / 1000;

			}


			let width = window.innerWidth;
			let height = window.innerHeight;

			if ( cameraAttribute.AspectWidth !== undefined && cameraAttribute.AspectHeight !== undefined ) {

				width = cameraAttribute.AspectWidth.value;
				height = cameraAttribute.AspectHeight.value;

			}

			const aspect = width / height;

			let fov = 45;
			if ( cameraAttribute.FieldOfView !== undefined ) {

				fov = cameraAttribute.FieldOfView.value;

			}

			const focalLength = cameraAttribute.FocalLength ? cameraAttribute.FocalLength.value : null;

			switch ( type ) {

				case 0: // Perspective
					model = new PerspectiveCamera( fov, aspect, nearClippingPlane, farClippingPlane );
					if ( focalLength !== null ) model.setFocalLength( focalLength );
					break;

				case 1: // Orthographic
					console.warn( 'THREE.FBXLoader: Orthographic cameras not supported yet.' );
					model = new Object3D();
					break;

				default:
					console.warn( 'THREE.FBXLoader: Unknown camera type ' + type + '.' );
					model = new Object3D();
					break;

			}

		}

		return model;

	}
```
</details>

### `FBXTreeParser.createLight(relationships: any): any`

**Parameters:**

- **`relationships`** `any`

**Returns:** `any`

**Calls:**

- `relationships.children.forEach`
- `ColorManagement.colorSpaceToWorking`
- `new Color().fromArray`
- `MathUtils.degToRad`
- `Math.max`
- `console.warn`

**Internal Comments:**
```
// LightType can be undefined for Point lights
// light disabled
// TODO: could this be calculated linearly from FarAttenuationStart to FarAttenuationEnd? (x2)
// TODO: this is not correct - FBX calculates outer and inner angle in degrees (x3)
// with OuterAngle > InnerAngle && OuterAngle <= Math.PI (x3)
// while three.js uses a penumbra between (0, 1) to attenuate the inner angle (x3)
```

<details><summary>Code</summary>

```typescript
createLight( relationships ) {

		let model;
		let lightAttribute;

		relationships.children.forEach( function ( child ) {

			const attr = fbxTree.Objects.NodeAttribute[ child.ID ];

			if ( attr !== undefined ) {

				lightAttribute = attr;

			}

		} );

		if ( lightAttribute === undefined ) {

			model = new Object3D();

		} else {

			let type;

			// LightType can be undefined for Point lights
			if ( lightAttribute.LightType === undefined ) {

				type = 0;

			} else {

				type = lightAttribute.LightType.value;

			}

			let color = 0xffffff;

			if ( lightAttribute.Color !== undefined ) {

				color = ColorManagement.colorSpaceToWorking( new Color().fromArray( lightAttribute.Color.value ), SRGBColorSpace );

			}

			let intensity = ( lightAttribute.Intensity === undefined ) ? 1 : lightAttribute.Intensity.value / 100;

			// light disabled
			if ( lightAttribute.CastLightOnObject !== undefined && lightAttribute.CastLightOnObject.value === 0 ) {

				intensity = 0;

			}

			let distance = 0;
			if ( lightAttribute.FarAttenuationEnd !== undefined ) {

				if ( lightAttribute.EnableFarAttenuation !== undefined && lightAttribute.EnableFarAttenuation.value === 0 ) {

					distance = 0;

				} else {

					distance = lightAttribute.FarAttenuationEnd.value;

				}

			}

			// TODO: could this be calculated linearly from FarAttenuationStart to FarAttenuationEnd?
			const decay = 1;

			switch ( type ) {

				case 0: // Point
					model = new PointLight( color, intensity, distance, decay );
					break;

				case 1: // Directional
					model = new DirectionalLight( color, intensity );
					break;

				case 2: // Spot
					let angle = Math.PI / 3;

					if ( lightAttribute.InnerAngle !== undefined ) {

						angle = MathUtils.degToRad( lightAttribute.InnerAngle.value );

					}

					let penumbra = 0;
					if ( lightAttribute.OuterAngle !== undefined ) {

						// TODO: this is not correct - FBX calculates outer and inner angle in degrees
						// with OuterAngle > InnerAngle && OuterAngle <= Math.PI
						// while three.js uses a penumbra between (0, 1) to attenuate the inner angle
						penumbra = MathUtils.degToRad( lightAttribute.OuterAngle.value );
						penumbra = Math.max( penumbra, 1 );

					}

					model = new SpotLight( color, intensity, distance, angle, penumbra, decay );
					break;

				default:
					console.warn( 'THREE.FBXLoader: Unknown light type ' + lightAttribute.LightType.value + ', defaulting to a PointLight.' );
					model = new PointLight( color, intensity );
					break;

			}

			if ( lightAttribute.CastShadows !== undefined && lightAttribute.CastShadows.value === 1 ) {

				model.castShadow = true;

			}

		}

		return model;

	}
```
</details>

### `FBXTreeParser.createMesh(relationships: any, geometryMap: any, materialMap: any): any`

**Parameters:**

- **`relationships`** `any`
- **`geometryMap`** `any`
- **`materialMap`** `any`

**Returns:** `any`

**Calls:**

- `relationships.children.forEach`
- `geometryMap.has`
- `geometryMap.get`
- `materialMap.has`
- `materials.push`
- `materialMap.get`
- `materials.forEach`
- `model.normalizeSkinWeights`

**Internal Comments:**
```
// get geometry and materials(s) from connections (x5)
// Sanitization: If geometry has groups, then it must match the provided material array.
// If not, we need to clean up the `group.materialIndex` properties inside the groups and point at a (new) default material.
// This isn't well defined; Unity creates default material, while Blender implicitly uses the previous material in the list.
```

<details><summary>Code</summary>

```typescript
createMesh( relationships, geometryMap, materialMap ) {

		let model;
		let geometry = null;
		let material = null;
		const materials = [];

		// get geometry and materials(s) from connections
		relationships.children.forEach( function ( child ) {

			if ( geometryMap.has( child.ID ) ) {

				geometry = geometryMap.get( child.ID );

			}

			if ( materialMap.has( child.ID ) ) {

				materials.push( materialMap.get( child.ID ) );

			}

		} );

		if ( materials.length > 1 ) {

			material = materials;

		} else if ( materials.length > 0 ) {

			material = materials[ 0 ];

		} else {

			material = new MeshPhongMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0xcccccc
			} );
			materials.push( material );

		}

		if ( 'color' in geometry.attributes ) {

			materials.forEach( function ( material ) {

				material.vertexColors = true;

			} );

		}

		// Sanitization: If geometry has groups, then it must match the provided material array.
		// If not, we need to clean up the `group.materialIndex` properties inside the groups and point at a (new) default material.
		// This isn't well defined; Unity creates default material, while Blender implicitly uses the previous material in the list.
		if ( geometry.groups.length > 0 ) {

			let needsDefaultMaterial = false;

			for ( let i = 0, il = geometry.groups.length; i < il; i ++ ) {

				const group = geometry.groups[ i ];

				if ( group.materialIndex < 0 || group.materialIndex >= materials.length ) {

					group.materialIndex = materials.length;
					needsDefaultMaterial = true;

				}

			}

			if ( needsDefaultMaterial ) {

				const defaultMaterial = new MeshPhongMaterial();
				materials.push( defaultMaterial );

			}

		}

		if ( geometry.FBX_Deformer ) {

			model = new SkinnedMesh( geometry, material );
			model.normalizeSkinWeights();

		} else {

			model = new Mesh( geometry, material );

		}

		return model;

	}
```
</details>

### `FBXTreeParser.createCurve(relationships: any, geometryMap: any): any`

**Parameters:**

- **`relationships`** `any`
- **`geometryMap`** `any`

**Returns:** `any`

**Calls:**

- `relationships.children.reduce`
- `geometryMap.has`
- `geometryMap.get`

**Internal Comments:**
```
// FBX does not list materials for Nurbs lines, so we'll just put our own in here. (x2)
```

<details><summary>Code</summary>

```typescript
createCurve( relationships, geometryMap ) {

		const geometry = relationships.children.reduce( function ( geo, child ) {

			if ( geometryMap.has( child.ID ) ) geo = geometryMap.get( child.ID );

			return geo;

		}, null );

		// FBX does not list materials for Nurbs lines, so we'll just put our own in here.
		const material = new LineBasicMaterial( {
			name: Loader.DEFAULT_MATERIAL_NAME,
			color: 0x3300ff,
			linewidth: 1
		} );
		return new Line( geometry, material );

	}
```
</details>

### `FBXTreeParser.getTransformData(model: any, modelNode: any): void`

**Parameters:**

- **`model`** `any`
- **`modelNode`** `any`

**Returns:** `void`

**Calls:**

- `parseInt`
- `getEulerOrder`

<details><summary>Code</summary>

```typescript
getTransformData( model, modelNode ) {

		const transformData = {};

		if ( 'InheritType' in modelNode ) transformData.inheritType = parseInt( modelNode.InheritType.value );

		if ( 'RotationOrder' in modelNode ) transformData.eulerOrder = getEulerOrder( modelNode.RotationOrder.value );
		else transformData.eulerOrder = getEulerOrder( 0 );

		if ( 'Lcl_Translation' in modelNode ) transformData.translation = modelNode.Lcl_Translation.value;

		if ( 'PreRotation' in modelNode ) transformData.preRotation = modelNode.PreRotation.value;
		if ( 'Lcl_Rotation' in modelNode ) transformData.rotation = modelNode.Lcl_Rotation.value;
		if ( 'PostRotation' in modelNode ) transformData.postRotation = modelNode.PostRotation.value;

		if ( 'Lcl_Scaling' in modelNode ) transformData.scale = modelNode.Lcl_Scaling.value;

		if ( 'ScalingOffset' in modelNode ) transformData.scalingOffset = modelNode.ScalingOffset.value;
		if ( 'ScalingPivot' in modelNode ) transformData.scalingPivot = modelNode.ScalingPivot.value;

		if ( 'RotationOffset' in modelNode ) transformData.rotationOffset = modelNode.RotationOffset.value;
		if ( 'RotationPivot' in modelNode ) transformData.rotationPivot = modelNode.RotationPivot.value;

		model.userData.transformData = transformData;

	}
```
</details>

### `FBXTreeParser.setLookAtProperties(model: any, modelNode: any): void`

**Parameters:**

- **`model`** `any`
- **`modelNode`** `any`

**Returns:** `void`

**Calls:**

- `connections.get`
- `children.forEach`
- `model.target.position.fromArray`
- `sceneGraph.add`
- `model.lookAt`
- `new Vector3().fromArray`

**Internal Comments:**
```
// DirectionalLight, SpotLight
```

<details><summary>Code</summary>

```typescript
setLookAtProperties( model, modelNode ) {

		if ( 'LookAtProperty' in modelNode ) {

			const children = connections.get( model.ID ).children;

			children.forEach( function ( child ) {

				if ( child.relationship === 'LookAtProperty' ) {

					const lookAtTarget = fbxTree.Objects.Model[ child.ID ];

					if ( 'Lcl_Translation' in lookAtTarget ) {

						const pos = lookAtTarget.Lcl_Translation.value;

						// DirectionalLight, SpotLight
						if ( model.target !== undefined ) {

							model.target.position.fromArray( pos );
							sceneGraph.add( model.target );

						} else { // Cameras and other Object3Ds

							model.lookAt( new Vector3().fromArray( pos ) );

						}

					}

				}

			} );

		}

	}
```
</details>

### `FBXTreeParser.bindSkeleton(skeletons: any, geometryMap: any, modelMap: any): void`

**Parameters:**

- **`skeletons`** `any`
- **`geometryMap`** `any`
- **`modelMap`** `any`

**Returns:** `void`

**Calls:**

- `this.parsePoseNodes`
- `connections.get`
- `parseInt`
- `parents.forEach`
- `geometryMap.has`
- `geoRelationships.parents.forEach`
- `modelMap.has`
- `modelMap.get`
- `model.bind`

<details><summary>Code</summary>

```typescript
bindSkeleton( skeletons, geometryMap, modelMap ) {

		const bindMatrices = this.parsePoseNodes();

		for ( const ID in skeletons ) {

			const skeleton = skeletons[ ID ];

			const parents = connections.get( parseInt( skeleton.ID ) ).parents;

			parents.forEach( function ( parent ) {

				if ( geometryMap.has( parent.ID ) ) {

					const geoID = parent.ID;
					const geoRelationships = connections.get( geoID );

					geoRelationships.parents.forEach( function ( geoConnParent ) {

						if ( modelMap.has( geoConnParent.ID ) ) {

							const model = modelMap.get( geoConnParent.ID );

							model.bind( new Skeleton( skeleton.bones ), bindMatrices[ geoConnParent.ID ] );

						}

					} );

				}

			} );

		}

	}
```
</details>

### `FBXTreeParser.parsePoseNodes(): {}`

**Returns:** `{}`

**Calls:**

- `Array.isArray`
- `poseNodes.forEach`
- `new Matrix4().fromArray`

<details><summary>Code</summary>

```typescript
parsePoseNodes() {

		const bindMatrices = {};

		if ( 'Pose' in fbxTree.Objects ) {

			const BindPoseNode = fbxTree.Objects.Pose;

			for ( const nodeID in BindPoseNode ) {

				if ( BindPoseNode[ nodeID ].attrType === 'BindPose' && BindPoseNode[ nodeID ].NbPoseNodes > 0 ) {

					const poseNodes = BindPoseNode[ nodeID ].PoseNode;

					if ( Array.isArray( poseNodes ) ) {

						poseNodes.forEach( function ( poseNode ) {

							bindMatrices[ poseNode.Node ] = new Matrix4().fromArray( poseNode.Matrix.a );

						} );

					} else {

						bindMatrices[ poseNodes.Node ] = new Matrix4().fromArray( poseNodes.Matrix.a );

					}

				}

			}

		}

		return bindMatrices;

	}
```
</details>

### `FBXTreeParser.addGlobalSceneSettings(): void`

**Returns:** `void`

**Calls:**

- `new Color().setRGB`
- `sceneGraph.add`

**Internal Comments:**
```
// Parse ambient color - if it's not set to black (default), create an ambient light (x2)
```

<details><summary>Code</summary>

```typescript
addGlobalSceneSettings() {

		if ( 'GlobalSettings' in fbxTree ) {

			if ( 'AmbientColor' in fbxTree.GlobalSettings ) {

				// Parse ambient color - if it's not set to black (default), create an ambient light

				const ambientColor = fbxTree.GlobalSettings.AmbientColor.value;
				const r = ambientColor[ 0 ];
				const g = ambientColor[ 1 ];
				const b = ambientColor[ 2 ];

				if ( r !== 0 || g !== 0 || b !== 0 ) {

					const color = new Color().setRGB( r, g, b, SRGBColorSpace );
					sceneGraph.add( new AmbientLight( color, 1 ) );

				}

			}

			if ( 'UnitScaleFactor' in fbxTree.GlobalSettings ) {

				sceneGraph.userData.unitScaleFactor = fbxTree.GlobalSettings.UnitScaleFactor.value;

			}

		}

	}
```
</details>

### `GeometryParser.parse(deformers: any): Map<any, any>`

**Parameters:**

- **`deformers`** `any`

**Returns:** `Map<any, any>`

**Calls:**

- `connections.get`
- `parseInt`
- `this.parseGeometry`
- `geometryMap.set`
- `console.warn`

**Internal Comments:**
```
// report warnings
```

<details><summary>Code</summary>

```typescript
parse( deformers ) {

		const geometryMap = new Map();

		if ( 'Geometry' in fbxTree.Objects ) {

			const geoNodes = fbxTree.Objects.Geometry;

			for ( const nodeID in geoNodes ) {

				const relationships = connections.get( parseInt( nodeID ) );
				const geo = this.parseGeometry( relationships, geoNodes[ nodeID ], deformers );

				geometryMap.set( parseInt( nodeID ), geo );

			}

		}

		// report warnings

		if ( this.negativeMaterialIndices === true ) {

			console.warn( 'THREE.FBXLoader: The FBX file contains invalid (negative) material indices. The asset might not render as expected.' );

		}

		return geometryMap;

	}
```
</details>

### `GeometryParser.parseGeometry(relationships: any, geoNode: any, deformers: any): any`

**Parameters:**

- **`relationships`** `any`
- **`geoNode`** `any`
- **`deformers`** `any`

**Returns:** `any`

**Calls:**

- `this.parseMeshGeometry`
- `this.parseNurbsGeometry`

<details><summary>Code</summary>

```typescript
parseGeometry( relationships, geoNode, deformers ) {

		switch ( geoNode.attrType ) {

			case 'Mesh':
				return this.parseMeshGeometry( relationships, geoNode, deformers );
				break;

			case 'NurbsCurve':
				return this.parseNurbsGeometry( geoNode );
				break;

		}

	}
```
</details>

### `GeometryParser.parseMeshGeometry(relationships: any, geoNode: any, deformers: any): any`

**Parameters:**

- **`relationships`** `any`
- **`geoNode`** `any`
- **`deformers`** `any`

**Returns:** `any`

**Calls:**

- `relationships.parents.map`
- `relationships.children.reduce`
- `relationships.children.forEach`
- `morphTargets.push`
- `getEulerOrder`
- `parseInt`
- `generateTransform`
- `this.genGeometry`

**Internal Comments:**
```
// don't create geometry if it is not associated with any models
// Assume one model and get the preRotation from that (x2)
// if there is more than one model associated with the geometry this may cause problems (x2)
```

<details><summary>Code</summary>

```typescript
parseMeshGeometry( relationships, geoNode, deformers ) {

		const skeletons = deformers.skeletons;
		const morphTargets = [];

		const modelNodes = relationships.parents.map( function ( parent ) {

			return fbxTree.Objects.Model[ parent.ID ];

		} );

		// don't create geometry if it is not associated with any models
		if ( modelNodes.length === 0 ) return;

		const skeleton = relationships.children.reduce( function ( skeleton, child ) {

			if ( skeletons[ child.ID ] !== undefined ) skeleton = skeletons[ child.ID ];

			return skeleton;

		}, null );

		relationships.children.forEach( function ( child ) {

			if ( deformers.morphTargets[ child.ID ] !== undefined ) {

				morphTargets.push( deformers.morphTargets[ child.ID ] );

			}

		} );

		// Assume one model and get the preRotation from that
		// if there is more than one model associated with the geometry this may cause problems
		const modelNode = modelNodes[ 0 ];

		const transformData = {};

		if ( 'RotationOrder' in modelNode ) transformData.eulerOrder = getEulerOrder( modelNode.RotationOrder.value );
		if ( 'InheritType' in modelNode ) transformData.inheritType = parseInt( modelNode.InheritType.value );

		if ( 'GeometricTranslation' in modelNode ) transformData.translation = modelNode.GeometricTranslation.value;
		if ( 'GeometricRotation' in modelNode ) transformData.rotation = modelNode.GeometricRotation.value;
		if ( 'GeometricScaling' in modelNode ) transformData.scale = modelNode.GeometricScaling.value;

		const transform = generateTransform( transformData );

		return this.genGeometry( geoNode, skeleton, morphTargets, transform );

	}
```
</details>

### `GeometryParser.genGeometry(geoNode: any, skeleton: any, morphTargets: any, preTransform: any): any`

**Parameters:**

- **`geoNode`** `any`
- **`skeleton`** `any`
- **`morphTargets`** `any`
- **`preTransform`** `any`

**Returns:** `any`

**Calls:**

- `this.parseGeoNode`
- `this.genBuffers`
- `positionAttribute.applyMatrix4`
- `geo.setAttribute`
- `new Matrix3().getNormalMatrix`
- `normalAttribute.applyNormalMatrix`
- `buffers.uvs.forEach`
- `buffers.materialIndex.forEach`
- `geo.addGroup`
- `this.addMorphTargets`

**Internal Comments:**
```
// used later to bind the skeleton to the model (x4)
// Convert the material indices of each vertex into rendering groups on the geometry. (x2)
// the loop above doesn't add the last group, do that here.
// case where there are multiple materials but the whole geometry is only
// using one of them
```

<details><summary>Code</summary>

```typescript
genGeometry( geoNode, skeleton, morphTargets, preTransform ) {

		const geo = new BufferGeometry();
		if ( geoNode.attrName ) geo.name = geoNode.attrName;

		const geoInfo = this.parseGeoNode( geoNode, skeleton );
		const buffers = this.genBuffers( geoInfo );

		const positionAttribute = new Float32BufferAttribute( buffers.vertex, 3 );

		positionAttribute.applyMatrix4( preTransform );

		geo.setAttribute( 'position', positionAttribute );

		if ( buffers.colors.length > 0 ) {

			geo.setAttribute( 'color', new Float32BufferAttribute( buffers.colors, 3 ) );

		}

		if ( skeleton ) {

			geo.setAttribute( 'skinIndex', new Uint16BufferAttribute( buffers.weightsIndices, 4 ) );

			geo.setAttribute( 'skinWeight', new Float32BufferAttribute( buffers.vertexWeights, 4 ) );

			// used later to bind the skeleton to the model
			geo.FBX_Deformer = skeleton;

		}

		if ( buffers.normal.length > 0 ) {

			const normalMatrix = new Matrix3().getNormalMatrix( preTransform );

			const normalAttribute = new Float32BufferAttribute( buffers.normal, 3 );
			normalAttribute.applyNormalMatrix( normalMatrix );

			geo.setAttribute( 'normal', normalAttribute );

		}

		buffers.uvs.forEach( function ( uvBuffer, i ) {

			const name = i === 0 ? 'uv' : `uv${ i }`;

			geo.setAttribute( name, new Float32BufferAttribute( buffers.uvs[ i ], 2 ) );

		} );

		if ( geoInfo.material && geoInfo.material.mappingType !== 'AllSame' ) {

			// Convert the material indices of each vertex into rendering groups on the geometry.
			let prevMaterialIndex = buffers.materialIndex[ 0 ];
			let startIndex = 0;

			buffers.materialIndex.forEach( function ( currentIndex, i ) {

				if ( currentIndex !== prevMaterialIndex ) {

					geo.addGroup( startIndex, i - startIndex, prevMaterialIndex );

					prevMaterialIndex = currentIndex;
					startIndex = i;

				}

			} );

			// the loop above doesn't add the last group, do that here.
			if ( geo.groups.length > 0 ) {

				const lastGroup = geo.groups[ geo.groups.length - 1 ];
				const lastIndex = lastGroup.start + lastGroup.count;

				if ( lastIndex !== buffers.materialIndex.length ) {

					geo.addGroup( lastIndex, buffers.materialIndex.length - lastIndex, prevMaterialIndex );

				}

			}

			// case where there are multiple materials but the whole geometry is only
			// using one of them
			if ( geo.groups.length === 0 ) {

				geo.addGroup( 0, buffers.materialIndex.length, buffers.materialIndex[ 0 ] );

			}

		}

		this.addMorphTargets( geo, geoNode, morphTargets, preTransform );

		return geo;

	}
```
</details>

### `GeometryParser.parseGeoNode(geoNode: any, skeleton: any): { vertexPositions: any; vertexIndices: any; color: { dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }; material: { dataSize: number; buffer: any; indices: number[]; mappingType: any; referenceType: any; }; normal: { ...; }; uv: any[]; weightTable: {}; skeleton: any; }`

**Parameters:**

- **`geoNode`** `any`
- **`skeleton`** `any`

**Returns:** `{ vertexPositions: any; vertexIndices: any; color: { dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }; material: { dataSize: number; buffer: any; indices: number[]; mappingType: any; referenceType: any; }; normal: { ...; }; uv: any[]; weightTable: {}; skeleton: any; }`

**Calls:**

- `this.parseVertexColors`
- `this.parseMaterialIndices`
- `this.parseNormals`
- `geoInfo.uv.push`
- `this.parseUVs`
- `skeleton.rawBones.forEach`
- `rawBone.indices.forEach`
- `geoInfo.weightTable[ index ].push`

**Internal Comments:**
```
// loop over the bone's vertex indices and weights (x5)
```

<details><summary>Code</summary>

```typescript
parseGeoNode( geoNode, skeleton ) {

		const geoInfo = {};

		geoInfo.vertexPositions = ( geoNode.Vertices !== undefined ) ? geoNode.Vertices.a : [];
		geoInfo.vertexIndices = ( geoNode.PolygonVertexIndex !== undefined ) ? geoNode.PolygonVertexIndex.a : [];

		if ( geoNode.LayerElementColor && geoNode.LayerElementColor[ 0 ].Colors ) {

			geoInfo.color = this.parseVertexColors( geoNode.LayerElementColor[ 0 ] );

		}

		if ( geoNode.LayerElementMaterial ) {

			geoInfo.material = this.parseMaterialIndices( geoNode.LayerElementMaterial[ 0 ] );

		}

		if ( geoNode.LayerElementNormal ) {

			geoInfo.normal = this.parseNormals( geoNode.LayerElementNormal[ 0 ] );

		}

		if ( geoNode.LayerElementUV ) {

			geoInfo.uv = [];

			let i = 0;
			while ( geoNode.LayerElementUV[ i ] ) {

				if ( geoNode.LayerElementUV[ i ].UV ) {

					geoInfo.uv.push( this.parseUVs( geoNode.LayerElementUV[ i ] ) );

				}

				i ++;

			}

		}

		geoInfo.weightTable = {};

		if ( skeleton !== null ) {

			geoInfo.skeleton = skeleton;

			skeleton.rawBones.forEach( function ( rawBone, i ) {

				// loop over the bone's vertex indices and weights
				rawBone.indices.forEach( function ( index, j ) {

					if ( geoInfo.weightTable[ index ] === undefined ) geoInfo.weightTable[ index ] = [];

					geoInfo.weightTable[ index ].push( {

						id: i,
						weight: rawBone.weights[ j ],

					} );

				} );

			} );

		}

		return geoInfo;

	}
```
</details>

### `GeometryParser.genBuffers(geoInfo: any): { vertex: any[]; normal: any[]; colors: any[]; uvs: any[]; materialIndex: any[]; vertexWeights: any[]; weightsIndices: any[]; }`

**Parameters:**

- **`geoInfo`** `any`

**Returns:** `{ vertex: any[]; normal: any[]; colors: any[]; uvs: any[]; materialIndex: any[]; vertexWeights: any[]; weightsIndices: any[]; }`

**Calls:**

- `geoInfo.vertexIndices.forEach`
- `facePositionIndexes.push`
- `getData`
- `faceColors.push`
- `geoInfo.weightTable[ vertexIndex ].forEach`
- `weights.push`
- `weightIndices.push`
- `console.warn`
- `weights.forEach`
- `Weight.forEach`
- `faceWeights.push`
- `faceWeightIndices.push`
- `faceNormals.push`
- `geoInfo.uv.forEach`
- `faceUVs[ i ].push`
- `scope.genFace`

**Internal Comments:**
```
// these will hold data for a single face (x2)
// Face index and vertex index arrays are combined in a single array
// A cube with quad faces looks like this:
// PolygonVertexIndex: *24 {
//  a: 0, 1, 3, -3, 2, 3, 5, -5, 4, 5, 7, -7, 6, 7, 1, -1, 1, 7, 5, -4, 6, 0, 2, -5
//  }
// Negative numbers mark the end of a face - first face here is 0, 1, 3, -3
// to find index of last vertex bit shift the index: ^ - 1
// if the weight array is shorter than 4 pad with 0s
// reset arrays for the next face (x3)
```

<details><summary>Code</summary>

```typescript
genBuffers( geoInfo ) {

		const buffers = {
			vertex: [],
			normal: [],
			colors: [],
			uvs: [],
			materialIndex: [],
			vertexWeights: [],
			weightsIndices: [],
		};

		let polygonIndex = 0;
		let faceLength = 0;
		let displayedWeightsWarning = false;

		// these will hold data for a single face
		let facePositionIndexes = [];
		let faceNormals = [];
		let faceColors = [];
		let faceUVs = [];
		let faceWeights = [];
		let faceWeightIndices = [];

		const scope = this;
		geoInfo.vertexIndices.forEach( function ( vertexIndex, polygonVertexIndex ) {

			let materialIndex;
			let endOfFace = false;

			// Face index and vertex index arrays are combined in a single array
			// A cube with quad faces looks like this:
			// PolygonVertexIndex: *24 {
			//  a: 0, 1, 3, -3, 2, 3, 5, -5, 4, 5, 7, -7, 6, 7, 1, -1, 1, 7, 5, -4, 6, 0, 2, -5
			//  }
			// Negative numbers mark the end of a face - first face here is 0, 1, 3, -3
			// to find index of last vertex bit shift the index: ^ - 1
			if ( vertexIndex < 0 ) {

				vertexIndex = vertexIndex ^ - 1; // equivalent to ( x * -1 ) - 1
				endOfFace = true;

			}

			let weightIndices = [];
			let weights = [];

			facePositionIndexes.push( vertexIndex * 3, vertexIndex * 3 + 1, vertexIndex * 3 + 2 );

			if ( geoInfo.color ) {

				const data = getData( polygonVertexIndex, polygonIndex, vertexIndex, geoInfo.color );

				faceColors.push( data[ 0 ], data[ 1 ], data[ 2 ] );

			}

			if ( geoInfo.skeleton ) {

				if ( geoInfo.weightTable[ vertexIndex ] !== undefined ) {

					geoInfo.weightTable[ vertexIndex ].forEach( function ( wt ) {

						weights.push( wt.weight );
						weightIndices.push( wt.id );

					} );


				}

				if ( weights.length > 4 ) {

					if ( ! displayedWeightsWarning ) {

						console.warn( 'THREE.FBXLoader: Vertex has more than 4 skinning weights assigned to vertex. Deleting additional weights.' );
						displayedWeightsWarning = true;

					}

					const wIndex = [ 0, 0, 0, 0 ];
					const Weight = [ 0, 0, 0, 0 ];

					weights.forEach( function ( weight, weightIndex ) {

						let currentWeight = weight;
						let currentIndex = weightIndices[ weightIndex ];

						Weight.forEach( function ( comparedWeight, comparedWeightIndex, comparedWeightArray ) {

							if ( currentWeight > comparedWeight ) {

								comparedWeightArray[ comparedWeightIndex ] = currentWeight;
								currentWeight = comparedWeight;

								const tmp = wIndex[ comparedWeightIndex ];
								wIndex[ comparedWeightIndex ] = currentIndex;
								currentIndex = tmp;

							}

						} );

					} );

					weightIndices = wIndex;
					weights = Weight;

				}

				// if the weight array is shorter than 4 pad with 0s
				while ( weights.length < 4 ) {

					weights.push( 0 );
					weightIndices.push( 0 );

				}

				for ( let i = 0; i < 4; ++ i ) {

					faceWeights.push( weights[ i ] );
					faceWeightIndices.push( weightIndices[ i ] );

				}

			}

			if ( geoInfo.normal ) {

				const data = getData( polygonVertexIndex, polygonIndex, vertexIndex, geoInfo.normal );

				faceNormals.push( data[ 0 ], data[ 1 ], data[ 2 ] );

			}

			if ( geoInfo.material && geoInfo.material.mappingType !== 'AllSame' ) {

				materialIndex = getData( polygonVertexIndex, polygonIndex, vertexIndex, geoInfo.material )[ 0 ];

				if ( materialIndex < 0 ) {

					scope.negativeMaterialIndices = true;
					materialIndex = 0; // fallback

				}

			}

			if ( geoInfo.uv ) {

				geoInfo.uv.forEach( function ( uv, i ) {

					const data = getData( polygonVertexIndex, polygonIndex, vertexIndex, uv );

					if ( faceUVs[ i ] === undefined ) {

						faceUVs[ i ] = [];

					}

					faceUVs[ i ].push( data[ 0 ] );
					faceUVs[ i ].push( data[ 1 ] );

				} );

			}

			faceLength ++;

			if ( endOfFace ) {

				scope.genFace( buffers, geoInfo, facePositionIndexes, materialIndex, faceNormals, faceColors, faceUVs, faceWeights, faceWeightIndices, faceLength );

				polygonIndex ++;
				faceLength = 0;

				// reset arrays for the next face
				facePositionIndexes = [];
				faceNormals = [];
				faceColors = [];
				faceUVs = [];
				faceWeights = [];
				faceWeightIndices = [];

			}

		} );

		return buffers;

	}
```
</details>

### `GeometryParser.getNormalNewell(vertices: any): any`

**Parameters:**

- **`vertices`** `any`

**Returns:** `any`

**Calls:**

- `normal.normalize`

<details><summary>Code</summary>

```typescript
getNormalNewell( vertices ) {

		const normal = new Vector3( 0.0, 0.0, 0.0 );

		for ( let i = 0; i < vertices.length; i ++ ) {

			const current = vertices[ i ];
			const next = vertices[ ( i + 1 ) % vertices.length ];

			normal.x += ( current.y - next.y ) * ( current.z + next.z );
			normal.y += ( current.z - next.z ) * ( current.x + next.x );
			normal.z += ( current.x - next.x ) * ( current.y + next.y );

		}

		normal.normalize();

		return normal;

	}
```
</details>

### `GeometryParser.getNormalTangentAndBitangent(vertices: any): { normal: any; tangent: any; bitangent: any; }`

**Parameters:**

- **`vertices`** `any`

**Returns:** `{ normal: any; tangent: any; bitangent: any; }`

**Calls:**

- `this.getNormalNewell`
- `Math.abs`
- `up.cross( normalVector ).normalize`
- `normalVector.clone().cross( tangent ).normalize`

**Internal Comments:**
```
// Avoid up being equal or almost equal to normalVector (x2)
```

<details><summary>Code</summary>

```typescript
getNormalTangentAndBitangent( vertices ) {

		const normalVector = this.getNormalNewell( vertices );
		// Avoid up being equal or almost equal to normalVector
		const up = Math.abs( normalVector.z ) > 0.5 ? new Vector3( 0.0, 1.0, 0.0 ) : new Vector3( 0.0, 0.0, 1.0 );
		const tangent = up.cross( normalVector ).normalize();
		const bitangent = normalVector.clone().cross( tangent ).normalize();

		return {
			normal: normalVector,
			tangent: tangent,
			bitangent: bitangent
		};

	}
```
</details>

### `GeometryParser.flattenVertex(vertex: any, normalTangent: any, normalBitangent: any): any`

**Parameters:**

- **`vertex`** `any`
- **`normalTangent`** `any`
- **`normalBitangent`** `any`

**Returns:** `any`

**Calls:**

- `vertex.dot`

<details><summary>Code</summary>

```typescript
flattenVertex( vertex, normalTangent, normalBitangent ) {

		return new Vector2(
			vertex.dot( normalTangent ),
			vertex.dot( normalBitangent )
		);

	}
```
</details>

### `GeometryParser.genFace(buffers: any, geoInfo: any, facePositionIndexes: any, materialIndex: any, faceNormals: any, faceColors: any, faceUVs: any, faceWeights: any, faceWeightIndices: any, faceLength: any): void`

**Parameters:**

- **`buffers`** `any`
- **`geoInfo`** `any`
- **`facePositionIndexes`** `any`
- **`materialIndex`** `any`
- **`faceNormals`** `any`
- **`faceColors`** `any`
- **`faceUVs`** `any`
- **`faceWeights`** `any`
- **`faceWeightIndices`** `any`
- **`faceLength`** `any`

**Returns:** `void`

**Calls:**

- `vertices.push`
- `this.getNormalTangentAndBitangent`
- `triangulationInput.push`
- `this.flattenVertex`
- `ShapeUtils.triangulateShape`
- `buffers.vertex.push`
- `buffers.vertexWeights.push`
- `buffers.weightsIndices.push`
- `buffers.colors.push`
- `buffers.materialIndex.push`
- `buffers.normal.push`
- `geoInfo.uv.forEach`
- `buffers.uvs[ j ].push`

**Internal Comments:**
```
// Triangulate n-gon using earcut (x2)
// in morphing scenario vertexPositions represent morphPositions (x2)
// while baseVertexPositions represent the original geometry's positions (x2)
// When vertices is an array of [0,0,0] elements (which is the case for vertices not participating in morph) (x3)
// the triangulationInput will be an array of [0,0] elements (x3)
// resulting in an array of 0 triangles being returned from ShapeUtils.triangulateShape (x3)
// leading to not pushing into buffers.vertex the redundant vertices (the vertices that are not morphed). (x3)
// That's why, in order to support morphing scenario, "positions" is looking first for baseVertexPositions, (x3)
// so that we don't end up with an array of 0 triangles for the faces not participating in morph. (x3)
// Regular triangle, skip earcut triangulation step (x3)
```

<details><summary>Code</summary>

```typescript
genFace( buffers, geoInfo, facePositionIndexes, materialIndex, faceNormals, faceColors, faceUVs, faceWeights, faceWeightIndices, faceLength ) {

		let triangles;

		if ( faceLength > 3 ) {

			// Triangulate n-gon using earcut

			const vertices = [];
			// in morphing scenario vertexPositions represent morphPositions
			// while baseVertexPositions represent the original geometry's positions
			const positions = geoInfo.baseVertexPositions || geoInfo.vertexPositions;
			for ( let i = 0; i < facePositionIndexes.length; i += 3 ) {

				vertices.push(
					new Vector3(
						positions[ facePositionIndexes[ i ] ],
						positions[ facePositionIndexes[ i + 1 ] ],
						positions[ facePositionIndexes[ i + 2 ] ]
					)
				);

			}

			const { tangent, bitangent } = this.getNormalTangentAndBitangent( vertices );
			const triangulationInput = [];

			for ( const vertex of vertices ) {

				triangulationInput.push( this.flattenVertex( vertex, tangent, bitangent ) );

			}

			// When vertices is an array of [0,0,0] elements (which is the case for vertices not participating in morph)
			// the triangulationInput will be an array of [0,0] elements
			// resulting in an array of 0 triangles being returned from ShapeUtils.triangulateShape
			// leading to not pushing into buffers.vertex the redundant vertices (the vertices that are not morphed).
			// That's why, in order to support morphing scenario, "positions" is looking first for baseVertexPositions,
			// so that we don't end up with an array of 0 triangles for the faces not participating in morph.
			triangles = ShapeUtils.triangulateShape( triangulationInput, [] );

		} else {

			// Regular triangle, skip earcut triangulation step
			triangles = [[ 0, 1, 2 ]];

		}

		for ( const [ i0, i1, i2 ] of triangles ) {

			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i0 * 3 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i0 * 3 + 1 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i0 * 3 + 2 ] ] );

			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i1 * 3 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i1 * 3 + 1 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i1 * 3 + 2 ] ] );

			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i2 * 3 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i2 * 3 + 1 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i2 * 3 + 2 ] ] );

			if ( geoInfo.skeleton ) {

				buffers.vertexWeights.push( faceWeights[ i0 * 4 ] );
				buffers.vertexWeights.push( faceWeights[ i0 * 4 + 1 ] );
				buffers.vertexWeights.push( faceWeights[ i0 * 4 + 2 ] );
				buffers.vertexWeights.push( faceWeights[ i0 * 4 + 3 ] );

				buffers.vertexWeights.push( faceWeights[ i1 * 4 ] );
				buffers.vertexWeights.push( faceWeights[ i1 * 4 + 1 ] );
				buffers.vertexWeights.push( faceWeights[ i1 * 4 + 2 ] );
				buffers.vertexWeights.push( faceWeights[ i1 * 4 + 3 ] );

				buffers.vertexWeights.push( faceWeights[ i2 * 4 ] );
				buffers.vertexWeights.push( faceWeights[ i2 * 4 + 1 ] );
				buffers.vertexWeights.push( faceWeights[ i2 * 4 + 2 ] );
				buffers.vertexWeights.push( faceWeights[ i2 * 4 + 3 ] );

				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 + 1 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 + 2 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 + 3 ] );

				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 + 1 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 + 2 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 + 3 ] );

				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 + 1 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 + 2 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 + 3 ] );

			}

			if ( geoInfo.color ) {

				buffers.colors.push( faceColors[ i0 * 3 ] );
				buffers.colors.push( faceColors[ i0 * 3 + 1 ] );
				buffers.colors.push( faceColors[ i0 * 3 + 2 ] );

				buffers.colors.push( faceColors[ i1 * 3 ] );
				buffers.colors.push( faceColors[ i1 * 3 + 1 ] );
				buffers.colors.push( faceColors[ i1 * 3 + 2 ] );

				buffers.colors.push( faceColors[ i2 * 3 ] );
				buffers.colors.push( faceColors[ i2 * 3 + 1 ] );
				buffers.colors.push( faceColors[ i2 * 3 + 2 ] );

			}

			if ( geoInfo.material && geoInfo.material.mappingType !== 'AllSame' ) {

				buffers.materialIndex.push( materialIndex );
				buffers.materialIndex.push( materialIndex );
				buffers.materialIndex.push( materialIndex );

			}

			if ( geoInfo.normal ) {

				buffers.normal.push( faceNormals[ i0 * 3 ] );
				buffers.normal.push( faceNormals[ i0 * 3 + 1 ] );
				buffers.normal.push( faceNormals[ i0 * 3 + 2 ] );

				buffers.normal.push( faceNormals[ i1 * 3 ] );
				buffers.normal.push( faceNormals[ i1 * 3 + 1 ] );
				buffers.normal.push( faceNormals[ i1 * 3 + 2 ] );

				buffers.normal.push( faceNormals[ i2 * 3 ] );
				buffers.normal.push( faceNormals[ i2 * 3 + 1 ] );
				buffers.normal.push( faceNormals[ i2 * 3 + 2 ] );

			}

			if ( geoInfo.uv ) {

				geoInfo.uv.forEach( function ( uv, j ) {

					if ( buffers.uvs[ j ] === undefined ) buffers.uvs[ j ] = [];

					buffers.uvs[ j ].push( faceUVs[ j ][ i0 * 2 ] );
					buffers.uvs[ j ].push( faceUVs[ j ][ i0 * 2 + 1 ] );

					buffers.uvs[ j ].push( faceUVs[ j ][ i1 * 2 ] );
					buffers.uvs[ j ].push( faceUVs[ j ][ i1 * 2 + 1 ] );

					buffers.uvs[ j ].push( faceUVs[ j ][ i2 * 2 ] );
					buffers.uvs[ j ].push( faceUVs[ j ][ i2 * 2 + 1 ] );

				} );

			}

		}

	}
```
</details>

### `GeometryParser.addMorphTargets(parentGeo: any, parentGeoNode: any, morphTargets: any, preTransform: any): void`

**Parameters:**

- **`parentGeo`** `any`
- **`parentGeoNode`** `any`
- **`morphTargets`** `any`
- **`preTransform`** `any`

**Returns:** `void`

**Calls:**

- `morphTargets.forEach`
- `morphTarget.rawTargets.forEach`
- `scope.genMorphGeometry`

**Internal Comments:**
```
// parentGeo.morphAttributes.normal = []; // not implemented (x2)
```

<details><summary>Code</summary>

```typescript
addMorphTargets( parentGeo, parentGeoNode, morphTargets, preTransform ) {

		if ( morphTargets.length === 0 ) return;

		parentGeo.morphTargetsRelative = true;

		parentGeo.morphAttributes.position = [];
		// parentGeo.morphAttributes.normal = []; // not implemented

		const scope = this;
		morphTargets.forEach( function ( morphTarget ) {

			morphTarget.rawTargets.forEach( function ( rawTarget ) {

				const morphGeoNode = fbxTree.Objects.Geometry[ rawTarget.geoID ];

				if ( morphGeoNode !== undefined ) {

					scope.genMorphGeometry( parentGeo, parentGeoNode, morphGeoNode, preTransform, rawTarget.name );

				}

			} );

		} );

	}
```
</details>

### `GeometryParser.genMorphGeometry(parentGeo: any, parentGeoNode: any, morphGeoNode: any, preTransform: any, name: any): void`

**Parameters:**

- **`parentGeo`** `any`
- **`parentGeoNode`** `any`
- **`morphGeoNode`** `any`
- **`preTransform`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.genBuffers`
- `positionAttribute.applyMatrix4`
- `parentGeo.morphAttributes.position.push`

**Internal Comments:**
```
// TODO: add morph normal support (x2)
```

<details><summary>Code</summary>

```typescript
genMorphGeometry( parentGeo, parentGeoNode, morphGeoNode, preTransform, name ) {

		const basePositions = parentGeoNode.Vertices !== undefined ? parentGeoNode.Vertices.a : [];
		const baseIndices = parentGeoNode.PolygonVertexIndex !== undefined ? parentGeoNode.PolygonVertexIndex.a : [];

		const morphPositionsSparse = morphGeoNode.Vertices !== undefined ? morphGeoNode.Vertices.a : [];
		const morphIndices = morphGeoNode.Indexes !== undefined ? morphGeoNode.Indexes.a : [];

		const length = parentGeo.attributes.position.count * 3;
		const morphPositions = new Float32Array( length );

		for ( let i = 0; i < morphIndices.length; i ++ ) {

			const morphIndex = morphIndices[ i ] * 3;

			morphPositions[ morphIndex ] = morphPositionsSparse[ i * 3 ];
			morphPositions[ morphIndex + 1 ] = morphPositionsSparse[ i * 3 + 1 ];
			morphPositions[ morphIndex + 2 ] = morphPositionsSparse[ i * 3 + 2 ];

		}

		// TODO: add morph normal support
		const morphGeoInfo = {
			vertexIndices: baseIndices,
			vertexPositions: morphPositions,
			baseVertexPositions: basePositions
		};

		const morphBuffers = this.genBuffers( morphGeoInfo );

		const positionAttribute = new Float32BufferAttribute( morphBuffers.vertex, 3 );
		positionAttribute.name = name || morphGeoNode.attrName;

		positionAttribute.applyMatrix4( preTransform );

		parentGeo.morphAttributes.position.push( positionAttribute );

	}
```
</details>

### `GeometryParser.parseNormals(NormalNode: any): { dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }`

**Parameters:**

- **`NormalNode`** `any`

**Returns:** `{ dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }`

<details><summary>Code</summary>

```typescript
parseNormals( NormalNode ) {

		const mappingType = NormalNode.MappingInformationType;
		const referenceType = NormalNode.ReferenceInformationType;
		const buffer = NormalNode.Normals.a;
		let indexBuffer = [];
		if ( referenceType === 'IndexToDirect' ) {

			if ( 'NormalIndex' in NormalNode ) {

				indexBuffer = NormalNode.NormalIndex.a;

			} else if ( 'NormalsIndex' in NormalNode ) {

				indexBuffer = NormalNode.NormalsIndex.a;

			}

		}

		return {
			dataSize: 3,
			buffer: buffer,
			indices: indexBuffer,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}
```
</details>

### `GeometryParser.parseUVs(UVNode: any): { dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }`

**Parameters:**

- **`UVNode`** `any`

**Returns:** `{ dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }`

<details><summary>Code</summary>

```typescript
parseUVs( UVNode ) {

		const mappingType = UVNode.MappingInformationType;
		const referenceType = UVNode.ReferenceInformationType;
		const buffer = UVNode.UV.a;
		let indexBuffer = [];
		if ( referenceType === 'IndexToDirect' ) {

			indexBuffer = UVNode.UVIndex.a;

		}

		return {
			dataSize: 2,
			buffer: buffer,
			indices: indexBuffer,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}
```
</details>

### `GeometryParser.parseVertexColors(ColorNode: any): { dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }`

**Parameters:**

- **`ColorNode`** `any`

**Returns:** `{ dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }`

**Calls:**

- `c.fromArray`
- `ColorManagement.colorSpaceToWorking`
- `c.toArray`

<details><summary>Code</summary>

```typescript
parseVertexColors( ColorNode ) {

		const mappingType = ColorNode.MappingInformationType;
		const referenceType = ColorNode.ReferenceInformationType;
		const buffer = ColorNode.Colors.a;
		let indexBuffer = [];
		if ( referenceType === 'IndexToDirect' ) {

			indexBuffer = ColorNode.ColorIndex.a;

		}

		for ( let i = 0, c = new Color(); i < buffer.length; i += 4 ) {

			c.fromArray( buffer, i );
			ColorManagement.colorSpaceToWorking( c, SRGBColorSpace );
			c.toArray( buffer, i );

		}

		return {
			dataSize: 4,
			buffer: buffer,
			indices: indexBuffer,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}
```
</details>

### `GeometryParser.parseMaterialIndices(MaterialNode: any): { dataSize: number; buffer: any; indices: number[]; mappingType: any; referenceType: any; }`

**Parameters:**

- **`MaterialNode`** `any`

**Returns:** `{ dataSize: number; buffer: any; indices: number[]; mappingType: any; referenceType: any; }`

**Calls:**

- `materialIndices.push`

**Internal Comments:**
```
// Since materials are stored as indices, there's a bit of a mismatch between FBX and what (x2)
// we expect.So we create an intermediate buffer that points to the index in the buffer, (x2)
// for conforming with the other functions we've written for other data. (x2)
```

<details><summary>Code</summary>

```typescript
parseMaterialIndices( MaterialNode ) {

		const mappingType = MaterialNode.MappingInformationType;
		const referenceType = MaterialNode.ReferenceInformationType;

		if ( mappingType === 'NoMappingInformation' ) {

			return {
				dataSize: 1,
				buffer: [ 0 ],
				indices: [ 0 ],
				mappingType: 'AllSame',
				referenceType: referenceType
			};

		}

		const materialIndexBuffer = MaterialNode.Materials.a;

		// Since materials are stored as indices, there's a bit of a mismatch between FBX and what
		// we expect.So we create an intermediate buffer that points to the index in the buffer,
		// for conforming with the other functions we've written for other data.
		const materialIndices = [];

		for ( let i = 0; i < materialIndexBuffer.length; ++ i ) {

			materialIndices.push( i );

		}

		return {
			dataSize: 1,
			buffer: materialIndexBuffer,
			indices: materialIndices,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}
```
</details>

### `GeometryParser.parseNurbsGeometry(geoNode: any): any`

**Parameters:**

- **`geoNode`** `any`

**Returns:** `any`

**Calls:**

- `parseInt`
- `isNaN`
- `console.error`
- `controlPoints.push`
- `new Vector4().fromArray`
- `curve.getPoints`
- `new BufferGeometry().setFromPoints`

<details><summary>Code</summary>

```typescript
parseNurbsGeometry( geoNode ) {

		const order = parseInt( geoNode.Order );

		if ( isNaN( order ) ) {

			console.error( 'THREE.FBXLoader: Invalid Order %s given for geometry ID: %s', geoNode.Order, geoNode.id );
			return new BufferGeometry();

		}

		const degree = order - 1;

		const knots = geoNode.KnotVector.a;
		const controlPoints = [];
		const pointsValues = geoNode.Points.a;

		for ( let i = 0, l = pointsValues.length; i < l; i += 4 ) {

			controlPoints.push( new Vector4().fromArray( pointsValues, i ) );

		}

		let startKnot, endKnot;

		if ( geoNode.Form === 'Closed' ) {

			controlPoints.push( controlPoints[ 0 ] );

		} else if ( geoNode.Form === 'Periodic' ) {

			startKnot = degree;
			endKnot = knots.length - 1 - startKnot;

			for ( let i = 0; i < degree; ++ i ) {

				controlPoints.push( controlPoints[ i ] );

			}

		}

		const curve = new NURBSCurve( degree, knots, controlPoints, startKnot, endKnot );
		const points = curve.getPoints( controlPoints.length * 12 );

		return new BufferGeometry().setFromPoints( points );

	}
```
</details>

### `AnimationParser.parse(): any[]`

**Returns:** `any[]`

**Calls:**

- `this.parseClips`
- `this.addClip`
- `animationClips.push`

<details><summary>Code</summary>

```typescript
parse() {

		const animationClips = [];

		const rawClips = this.parseClips();

		if ( rawClips !== undefined ) {

			for ( const key in rawClips ) {

				const rawClip = rawClips[ key ];

				const clip = this.addClip( rawClip );

				animationClips.push( clip );

			}

		}

		return animationClips;

	}
```
</details>

### `AnimationParser.parseClips(): {}`

**Returns:** `{}`

**Calls:**

- `this.parseAnimationCurveNodes`
- `this.parseAnimationCurves`
- `this.parseAnimationLayers`
- `this.parseAnimStacks`

**Internal Comments:**
```
// since the actual transformation data is stored in FBXTree.Objects.AnimationCurve,
// if this is undefined we can safely assume there are no animations
```

<details><summary>Code</summary>

```typescript
parseClips() {

		// since the actual transformation data is stored in FBXTree.Objects.AnimationCurve,
		// if this is undefined we can safely assume there are no animations
		if ( fbxTree.Objects.AnimationCurve === undefined ) return undefined;

		const curveNodesMap = this.parseAnimationCurveNodes();

		this.parseAnimationCurves( curveNodesMap );

		const layersMap = this.parseAnimationLayers( curveNodesMap );
		const rawClips = this.parseAnimStacks( layersMap );

		return rawClips;

	}
```
</details>

### `AnimationParser.parseAnimationCurveNodes(): Map<any, any>`

**Returns:** `Map<any, any>`

**Calls:**

- `rawCurveNode.attrName.match`
- `curveNodesMap.set`

<details><summary>Code</summary>

```typescript
parseAnimationCurveNodes() {

		const rawCurveNodes = fbxTree.Objects.AnimationCurveNode;

		const curveNodesMap = new Map();

		for ( const nodeID in rawCurveNodes ) {

			const rawCurveNode = rawCurveNodes[ nodeID ];

			if ( rawCurveNode.attrName.match( /S|R|T|DeformPercent/ ) !== null ) {

				const curveNode = {

					id: rawCurveNode.id,
					attr: rawCurveNode.attrName,
					curves: {},

				};

				curveNodesMap.set( curveNode.id, curveNode );

			}

		}

		return curveNodesMap;

	}
```
</details>

### `AnimationParser.parseAnimationCurves(curveNodesMap: any): void`

**Parameters:**

- **`curveNodesMap`** `any`

**Returns:** `void`

**Calls:**

- `rawCurves[ nodeID ].KeyTime.a.map`
- `connections.get`
- `animationCurveRelationship.match`
- `curveNodesMap.get`
- `curveNodesMap.has`

**Internal Comments:**
```
// TODO: Many values are identical up to roundoff error, but won't be optimised
// e.g. position times: [0, 0.4, 0. 8]
// position values: [7.23538335023477e-7, 93.67518615722656, -0.9982695579528809, 7.23538335023477e-7, 93.67518615722656, -0.9982695579528809, 7.235384487103147e-7, 93.67520904541016, -0.9982695579528809]
// clearly, this should be optimised to
// times: [0], positions [7.23538335023477e-7, 93.67518615722656, -0.9982695579528809]
// this shows up in nearly every FBX file, and generally time array is length > 100
```

<details><summary>Code</summary>

```typescript
parseAnimationCurves( curveNodesMap ) {

		const rawCurves = fbxTree.Objects.AnimationCurve;

		// TODO: Many values are identical up to roundoff error, but won't be optimised
		// e.g. position times: [0, 0.4, 0. 8]
		// position values: [7.23538335023477e-7, 93.67518615722656, -0.9982695579528809, 7.23538335023477e-7, 93.67518615722656, -0.9982695579528809, 7.235384487103147e-7, 93.67520904541016, -0.9982695579528809]
		// clearly, this should be optimised to
		// times: [0], positions [7.23538335023477e-7, 93.67518615722656, -0.9982695579528809]
		// this shows up in nearly every FBX file, and generally time array is length > 100

		for ( const nodeID in rawCurves ) {

			const animationCurve = {

				id: rawCurves[ nodeID ].id,
				times: rawCurves[ nodeID ].KeyTime.a.map( convertFBXTimeToSeconds ),
				values: rawCurves[ nodeID ].KeyValueFloat.a,

			};

			const relationships = connections.get( animationCurve.id );

			if ( relationships !== undefined ) {

				const animationCurveID = relationships.parents[ 0 ].ID;
				const animationCurveRelationship = relationships.parents[ 0 ].relationship;

				if ( animationCurveRelationship.match( /X/ ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'x' ] = animationCurve;

				} else if ( animationCurveRelationship.match( /Y/ ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'y' ] = animationCurve;

				} else if ( animationCurveRelationship.match( /Z/ ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'z' ] = animationCurve;

				} else if ( animationCurveRelationship.match( /DeformPercent/ ) && curveNodesMap.has( animationCurveID ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'morph' ] = animationCurve;

				}

			}

		}

	}
```
</details>

### `AnimationParser.parseAnimationLayers(curveNodesMap: any): Map<any, any>`

**Parameters:**

- **`curveNodesMap`** `any`

**Returns:** `Map<any, any>`

**Calls:**

- `connections.get`
- `parseInt`
- `children.forEach`
- `curveNodesMap.has`
- `curveNodesMap.get`
- `connections.get( child.ID ).parents.filter`
- `modelID.toString`
- `console.warn`
- `PropertyBinding.sanitizeNodeName`
- `sceneGraph.traverse`
- `layersMap.set`

**Internal Comments:**
```
// all the animationCurveNodes used in the layer (x2)
// check that the curves are defined for at least one axis, otherwise ignore the curveNode
// if the animated model is pre rotated, we'll have to apply the pre rotations to every
// animation value as well
// assuming geometry is not used in more than one model (x2)
```

<details><summary>Code</summary>

```typescript
parseAnimationLayers( curveNodesMap ) {

		const rawLayers = fbxTree.Objects.AnimationLayer;

		const layersMap = new Map();

		for ( const nodeID in rawLayers ) {

			const layerCurveNodes = [];

			const connection = connections.get( parseInt( nodeID ) );

			if ( connection !== undefined ) {

				// all the animationCurveNodes used in the layer
				const children = connection.children;

				children.forEach( function ( child, i ) {

					if ( curveNodesMap.has( child.ID ) ) {

						const curveNode = curveNodesMap.get( child.ID );

						// check that the curves are defined for at least one axis, otherwise ignore the curveNode
						if ( curveNode.curves.x !== undefined || curveNode.curves.y !== undefined || curveNode.curves.z !== undefined ) {

							if ( layerCurveNodes[ i ] === undefined ) {

								const modelID = connections.get( child.ID ).parents.filter( function ( parent ) {

									return parent.relationship !== undefined;

								} )[ 0 ].ID;

								if ( modelID !== undefined ) {

									const rawModel = fbxTree.Objects.Model[ modelID.toString() ];

									if ( rawModel === undefined ) {

										console.warn( 'THREE.FBXLoader: Encountered a unused curve.', child );
										return;

									}

									const node = {

										modelName: rawModel.attrName ? PropertyBinding.sanitizeNodeName( rawModel.attrName ) : '',
										ID: rawModel.id,
										initialPosition: [ 0, 0, 0 ],
										initialRotation: [ 0, 0, 0 ],
										initialScale: [ 1, 1, 1 ],

									};

									sceneGraph.traverse( function ( child ) {

										if ( child.ID === rawModel.id ) {

											node.transform = child.matrix;

											if ( child.userData.transformData ) node.eulerOrder = child.userData.transformData.eulerOrder;

										}

									} );

									if ( ! node.transform ) node.transform = new Matrix4();

									// if the animated model is pre rotated, we'll have to apply the pre rotations to every
									// animation value as well
									if ( 'PreRotation' in rawModel ) node.preRotation = rawModel.PreRotation.value;
									if ( 'PostRotation' in rawModel ) node.postRotation = rawModel.PostRotation.value;

									layerCurveNodes[ i ] = node;

								}

							}

							if ( layerCurveNodes[ i ] ) layerCurveNodes[ i ][ curveNode.attr ] = curveNode;

						} else if ( curveNode.curves.morph !== undefined ) {

							if ( layerCurveNodes[ i ] === undefined ) {

								const deformerID = connections.get( child.ID ).parents.filter( function ( parent ) {

									return parent.relationship !== undefined;

								} )[ 0 ].ID;

								const morpherID = connections.get( deformerID ).parents[ 0 ].ID;
								const geoID = connections.get( morpherID ).parents[ 0 ].ID;

								// assuming geometry is not used in more than one model
								const modelID = connections.get( geoID ).parents[ 0 ].ID;

								const rawModel = fbxTree.Objects.Model[ modelID ];

								const node = {

									modelName: rawModel.attrName ? PropertyBinding.sanitizeNodeName( rawModel.attrName ) : '',
									morphName: fbxTree.Objects.Deformer[ deformerID ].attrName,

								};

								layerCurveNodes[ i ] = node;

							}

							layerCurveNodes[ i ][ curveNode.attr ] = curveNode;

						}

					}

				} );

				layersMap.set( parseInt( nodeID ), layerCurveNodes );

			}

		}

		return layersMap;

	}
```
</details>

### `AnimationParser.parseAnimStacks(layersMap: any): {}`

**Parameters:**

- **`layersMap`** `any`

**Returns:** `{}`

**Calls:**

- `connections.get`
- `parseInt`
- `console.warn`
- `layersMap.get`

**Internal Comments:**
```
// connect the stacks (clips) up to the layers (x2)
// it seems like stacks will always be associated with a single layer. But just in case there are files (x4)
// where there are multiple layers per stack, we'll display a warning (x4)
```

<details><summary>Code</summary>

```typescript
parseAnimStacks( layersMap ) {

		const rawStacks = fbxTree.Objects.AnimationStack;

		// connect the stacks (clips) up to the layers
		const rawClips = {};

		for ( const nodeID in rawStacks ) {

			const children = connections.get( parseInt( nodeID ) ).children;

			if ( children.length > 1 ) {

				// it seems like stacks will always be associated with a single layer. But just in case there are files
				// where there are multiple layers per stack, we'll display a warning
				console.warn( 'THREE.FBXLoader: Encountered an animation stack with multiple layers, this is currently not supported. Ignoring subsequent layers.' );

			}

			const layer = layersMap.get( children[ 0 ].ID );

			rawClips[ nodeID ] = {

				name: rawStacks[ nodeID ].attrName,
				layer: layer,

			};

		}

		return rawClips;

	}
```
</details>

### `AnimationParser.addClip(rawClip: any): any`

**Parameters:**

- **`rawClip`** `any`

**Returns:** `any`

**Calls:**

- `rawClip.layer.forEach`
- `tracks.concat`
- `scope.generateTracks`

<details><summary>Code</summary>

```typescript
addClip( rawClip ) {

		let tracks = [];

		const scope = this;
		rawClip.layer.forEach( function ( rawTracks ) {

			tracks = tracks.concat( scope.generateTracks( rawTracks ) );

		} );

		return new AnimationClip( rawClip.name, - 1, tracks );

	}
```
</details>

### `AnimationParser.generateTracks(rawTracks: any): any[]`

**Parameters:**

- **`rawTracks`** `any`

**Returns:** `any[]`

**Calls:**

- `rawTracks.transform.decompose`
- `initialPosition.toArray`
- `initialScale.toArray`
- `Object.keys`
- `this.generateVectorTrack`
- `tracks.push`
- `this.generateRotationTrack`
- `this.generateMorphTrack`

<details><summary>Code</summary>

```typescript
generateTracks( rawTracks ) {

		const tracks = [];

		let initialPosition = new Vector3();
		let initialScale = new Vector3();

		if ( rawTracks.transform ) rawTracks.transform.decompose( initialPosition, new Quaternion(), initialScale );

		initialPosition = initialPosition.toArray();
		initialScale = initialScale.toArray();

		if ( rawTracks.T !== undefined && Object.keys( rawTracks.T.curves ).length > 0 ) {

			const positionTrack = this.generateVectorTrack( rawTracks.modelName, rawTracks.T.curves, initialPosition, 'position' );
			if ( positionTrack !== undefined ) tracks.push( positionTrack );

		}

		if ( rawTracks.R !== undefined && Object.keys( rawTracks.R.curves ).length > 0 ) {

			const rotationTrack = this.generateRotationTrack( rawTracks.modelName, rawTracks.R.curves, rawTracks.preRotation, rawTracks.postRotation, rawTracks.eulerOrder );
			if ( rotationTrack !== undefined ) tracks.push( rotationTrack );

		}

		if ( rawTracks.S !== undefined && Object.keys( rawTracks.S.curves ).length > 0 ) {

			const scaleTrack = this.generateVectorTrack( rawTracks.modelName, rawTracks.S.curves, initialScale, 'scale' );
			if ( scaleTrack !== undefined ) tracks.push( scaleTrack );

		}

		if ( rawTracks.DeformPercent !== undefined ) {

			const morphTrack = this.generateMorphTrack( rawTracks );
			if ( morphTrack !== undefined ) tracks.push( morphTrack );

		}

		return tracks;

	}
```
</details>

### `AnimationParser.generateVectorTrack(modelName: any, curves: any, initialValue: any, type: any): any`

**Parameters:**

- **`modelName`** `any`
- **`curves`** `any`
- **`initialValue`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `this.getTimesForAllAxes`
- `this.getKeyframeTrackValues`

<details><summary>Code</summary>

```typescript
generateVectorTrack( modelName, curves, initialValue, type ) {

		const times = this.getTimesForAllAxes( curves );
		const values = this.getKeyframeTrackValues( times, curves, initialValue );

		return new VectorKeyframeTrack( modelName + '.' + type, times, values );

	}
```
</details>

### `AnimationParser.generateRotationTrack(modelName: any, curves: any, preRotation: any, postRotation: any, eulerOrder: any): any`

**Parameters:**

- **`modelName`** `any`
- **`curves`** `any`
- **`preRotation`** `any`
- **`postRotation`** `any`
- **`eulerOrder`** `any`

**Returns:** `any`

**Calls:**

- `this.interpolateRotations`
- `getEulerOrder`
- `preRotation.map`
- `preRotation.push`
- `new Euler().fromArray`
- `new Quaternion().setFromEuler`
- `postRotation.map`
- `postRotation.push`
- `new Quaternion().setFromEuler( postRotation ).invert`
- `euler.set`
- `quaternion.setFromEuler`
- `quaternion.premultiply`
- `quaternion.multiply`
- `new Quaternion().fromArray`
- `prevQuat.dot`
- `quaternion.set`
- `quaternion.toArray`

**Internal Comments:**
```
// For Maya models using "Joint Orient", Euler order only applies to rotation, not pre/post-rotations (x2)
// Check unroll
```

<details><summary>Code</summary>

```typescript
generateRotationTrack( modelName, curves, preRotation, postRotation, eulerOrder ) {

		let times;
		let values;

		if ( curves.x !== undefined && curves.y !== undefined && curves.z !== undefined ) {

			const result = this.interpolateRotations( curves.x, curves.y, curves.z, eulerOrder );

			times = result[ 0 ];
			values = result[ 1 ];

		}

		// For Maya models using "Joint Orient", Euler order only applies to rotation, not pre/post-rotations
		const defaultEulerOrder = getEulerOrder( 0 );

		if ( preRotation !== undefined ) {

			preRotation = preRotation.map( MathUtils.degToRad );
			preRotation.push( defaultEulerOrder );

			preRotation = new Euler().fromArray( preRotation );
			preRotation = new Quaternion().setFromEuler( preRotation );

		}

		if ( postRotation !== undefined ) {

			postRotation = postRotation.map( MathUtils.degToRad );
			postRotation.push( defaultEulerOrder );

			postRotation = new Euler().fromArray( postRotation );
			postRotation = new Quaternion().setFromEuler( postRotation ).invert();

		}

		const quaternion = new Quaternion();
		const euler = new Euler();

		const quaternionValues = [];

		if ( ! values || ! times ) return new QuaternionKeyframeTrack( modelName + '.quaternion', [ 0 ], [ 0 ] );

		for ( let i = 0; i < values.length; i += 3 ) {

			euler.set( values[ i ], values[ i + 1 ], values[ i + 2 ], eulerOrder );
			quaternion.setFromEuler( euler );

			if ( preRotation !== undefined ) quaternion.premultiply( preRotation );
			if ( postRotation !== undefined ) quaternion.multiply( postRotation );

			// Check unroll
			if ( i > 2 ) {

				const prevQuat = new Quaternion().fromArray(
					quaternionValues,
					( ( i - 3 ) / 3 ) * 4
				);

				if ( prevQuat.dot( quaternion ) < 0 ) {

					quaternion.set( - quaternion.x, - quaternion.y, - quaternion.z, - quaternion.w );

				}

			}

			quaternion.toArray( quaternionValues, ( i / 3 ) * 4 );

		}

		return new QuaternionKeyframeTrack( modelName + '.quaternion', times, quaternionValues );

	}
```
</details>

### `AnimationParser.generateMorphTrack(rawTracks: any): any`

**Parameters:**

- **`rawTracks`** `any`

**Returns:** `any`

**Calls:**

- `curves.values.map`
- `sceneGraph.getObjectByName`

<details><summary>Code</summary>

```typescript
generateMorphTrack( rawTracks ) {

		const curves = rawTracks.DeformPercent.curves.morph;
		const values = curves.values.map( function ( val ) {

			return val / 100;

		} );

		const morphNum = sceneGraph.getObjectByName( rawTracks.modelName ).morphTargetDictionary[ rawTracks.morphName ];

		return new NumberKeyframeTrack( rawTracks.modelName + '.morphTargetInfluences[' + morphNum + ']', curves.times, values );

	}
```
</details>

### `AnimationParser.getTimesForAllAxes(curves: any): any[]`

**Parameters:**

- **`curves`** `any`

**Returns:** `any[]`

**Calls:**

- `times.concat`
- `times.sort`
- `times.slice`

**Internal Comments:**
```
// first join together the times for each axis, if defined
// then sort them (x3)
// and remove duplicates
```

<details><summary>Code</summary>

```typescript
getTimesForAllAxes( curves ) {

		let times = [];

		// first join together the times for each axis, if defined
		if ( curves.x !== undefined ) times = times.concat( curves.x.times );
		if ( curves.y !== undefined ) times = times.concat( curves.y.times );
		if ( curves.z !== undefined ) times = times.concat( curves.z.times );

		// then sort them
		times = times.sort( function ( a, b ) {

			return a - b;

		} );

		// and remove duplicates
		if ( times.length > 1 ) {

			let targetIndex = 1;
			let lastValue = times[ 0 ];
			for ( let i = 1; i < times.length; i ++ ) {

				const currentValue = times[ i ];
				if ( currentValue !== lastValue ) {

					times[ targetIndex ] = currentValue;
					lastValue = currentValue;
					targetIndex ++;

				}

			}

			times = times.slice( 0, targetIndex );

		}

		return times;

	}
```
</details>

### `AnimationParser.getKeyframeTrackValues(times: any, curves: any, initialValue: any): any[]`

**Parameters:**

- **`times`** `any`
- **`curves`** `any`
- **`initialValue`** `any`

**Returns:** `any[]`

**Calls:**

- `times.forEach`
- `curves.x.times.indexOf`
- `curves.y.times.indexOf`
- `curves.z.times.indexOf`
- `values.push`

**Internal Comments:**
```
// if there is an x value defined for this frame, use that
// otherwise use the x value from the previous frame (x4)
```

<details><summary>Code</summary>

```typescript
getKeyframeTrackValues( times, curves, initialValue ) {

		const prevValue = initialValue;

		const values = [];

		let xIndex = - 1;
		let yIndex = - 1;
		let zIndex = - 1;

		times.forEach( function ( time ) {

			if ( curves.x ) xIndex = curves.x.times.indexOf( time );
			if ( curves.y ) yIndex = curves.y.times.indexOf( time );
			if ( curves.z ) zIndex = curves.z.times.indexOf( time );

			// if there is an x value defined for this frame, use that
			if ( xIndex !== - 1 ) {

				const xValue = curves.x.values[ xIndex ];
				values.push( xValue );
				prevValue[ 0 ] = xValue;

			} else {

				// otherwise use the x value from the previous frame
				values.push( prevValue[ 0 ] );

			}

			if ( yIndex !== - 1 ) {

				const yValue = curves.y.values[ yIndex ];
				values.push( yValue );
				prevValue[ 1 ] = yValue;

			} else {

				values.push( prevValue[ 1 ] );

			}

			if ( zIndex !== - 1 ) {

				const zValue = curves.z.values[ zIndex ];
				values.push( zValue );
				prevValue[ 2 ] = zValue;

			} else {

				values.push( prevValue[ 2 ] );

			}

		} );

		return values;

	}
```
</details>

### `AnimationParser.interpolateRotations(curvex: any, curvey: any, curvez: any, eulerOrder: any): any[][]`

**Parameters:**

- **`curvex`** `any`
- **`curvey`** `any`
- **`curvez`** `any`
- **`eulerOrder`** `any`

**Returns:** `any[][]`

**Calls:**

- `times.push`
- `values.push`
- `MathUtils.degToRad`
- `isNaN`
- `initialValue.map`
- `currentValue.map`
- `Math.abs`
- `Math.max`
- `new Quaternion().setFromEuler`
- `Q1.dot`
- `Q2.set`
- `Q.copy`
- `Q1.clone().slerp`
- `Q2.clone`
- `E.setFromQuaternion`

**Internal Comments:**
```
// Add first frame (x4)
// Check unroll
// Interpolate (x2)
```

<details><summary>Code</summary>

```typescript
interpolateRotations( curvex, curvey, curvez, eulerOrder ) {

		const times = [];
		const values = [];

		// Add first frame
		times.push( curvex.times[ 0 ] );
		values.push( MathUtils.degToRad( curvex.values[ 0 ] ) );
		values.push( MathUtils.degToRad( curvey.values[ 0 ] ) );
		values.push( MathUtils.degToRad( curvez.values[ 0 ] ) );

		for ( let i = 1; i < curvex.values.length; i ++ ) {

			const initialValue = [
				curvex.values[ i - 1 ],
				curvey.values[ i - 1 ],
				curvez.values[ i - 1 ],
			];

			if ( isNaN( initialValue[ 0 ] ) || isNaN( initialValue[ 1 ] ) || isNaN( initialValue[ 2 ] ) ) {

				continue;

			}

			const initialValueRad = initialValue.map( MathUtils.degToRad );

			const currentValue = [
				curvex.values[ i ],
				curvey.values[ i ],
				curvez.values[ i ],
			];

			if ( isNaN( currentValue[ 0 ] ) || isNaN( currentValue[ 1 ] ) || isNaN( currentValue[ 2 ] ) ) {

				continue;

			}

			const currentValueRad = currentValue.map( MathUtils.degToRad );

			const valuesSpan = [
				currentValue[ 0 ] - initialValue[ 0 ],
				currentValue[ 1 ] - initialValue[ 1 ],
				currentValue[ 2 ] - initialValue[ 2 ],
			];

			const absoluteSpan = [
				Math.abs( valuesSpan[ 0 ] ),
				Math.abs( valuesSpan[ 1 ] ),
				Math.abs( valuesSpan[ 2 ] ),
			];

			if ( absoluteSpan[ 0 ] >= 180 || absoluteSpan[ 1 ] >= 180 || absoluteSpan[ 2 ] >= 180 ) {

				const maxAbsSpan = Math.max( ...absoluteSpan );

				const numSubIntervals = maxAbsSpan / 180;

				const E1 = new Euler( ...initialValueRad, eulerOrder );
				const E2 = new Euler( ...currentValueRad, eulerOrder );

				const Q1 = new Quaternion().setFromEuler( E1 );
				const Q2 = new Quaternion().setFromEuler( E2 );

				// Check unroll
				if ( Q1.dot( Q2 ) ) {

					Q2.set( - Q2.x, - Q2.y, - Q2.z, - Q2.w );

				}

				// Interpolate
				const initialTime = curvex.times[ i - 1 ];
				const timeSpan = curvex.times[ i ] - initialTime;

				const Q = new Quaternion();
				const E = new Euler();
				for ( let t = 0; t < 1; t += 1 / numSubIntervals ) {

					Q.copy( Q1.clone().slerp( Q2.clone(), t ) );

					times.push( initialTime + t * timeSpan );
					E.setFromQuaternion( Q, eulerOrder );

					values.push( E.x );
					values.push( E.y );
					values.push( E.z );

				}

			} else {

				times.push( curvex.times[ i ] );
				values.push( MathUtils.degToRad( curvex.values[ i ] ) );
				values.push( MathUtils.degToRad( curvey.values[ i ] ) );
				values.push( MathUtils.degToRad( curvez.values[ i ] ) );

			}

		}

		return [ times, values ];

	}
```
</details>

### `TextParser.getPrevNode(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getPrevNode() {

		return this.nodeStack[ this.currentIndent - 2 ];

	}
```
</details>

### `TextParser.getCurrentNode(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getCurrentNode() {

		return this.nodeStack[ this.currentIndent - 1 ];

	}
```
</details>

### `TextParser.getCurrentProp(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getCurrentProp() {

		return this.currentProp;

	}
```
</details>

### `TextParser.pushStack(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.nodeStack.push`

<details><summary>Code</summary>

```typescript
pushStack( node ) {

		this.nodeStack.push( node );
		this.currentIndent += 1;

	}
```
</details>

### `TextParser.popStack(): void`

**Returns:** `void`

**Calls:**

- `this.nodeStack.pop`

<details><summary>Code</summary>

```typescript
popStack() {

		this.nodeStack.pop();
		this.currentIndent -= 1;

	}
```
</details>

### `TextParser.setCurrentProp(val: any, name: any): void`

**Parameters:**

- **`val`** `any`
- **`name`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setCurrentProp( val, name ) {

		this.currentProp = val;
		this.currentPropName = name;

	}
```
</details>

### `TextParser.parse(text: any): FBXTree`

**Parameters:**

- **`text`** `any`

**Returns:** `FBXTree`

**Calls:**

- `text.split`
- `split.forEach`
- `line.match`
- `scope.parseNodeBegin`
- `scope.parseNodeProperty`
- `scope.popStack`
- `scope.parseNodePropertyContinued`

**Internal Comments:**
```
// large arrays are split over multiple lines terminated with a ',' character (x4)
// if this is encountered the line needs to be joined to the previous line (x4)
```

<details><summary>Code</summary>

```typescript
parse( text ) {

		this.currentIndent = 0;

		this.allNodes = new FBXTree();
		this.nodeStack = [];
		this.currentProp = [];
		this.currentPropName = '';

		const scope = this;

		const split = text.split( /[\r\n]+/ );

		split.forEach( function ( line, i ) {

			const matchComment = line.match( /^[\s\t]*;/ );
			const matchEmpty = line.match( /^[\s\t]*$/ );

			if ( matchComment || matchEmpty ) return;

			const matchBeginning = line.match( '^\\t{' + scope.currentIndent + '}(\\w+):(.*){', '' );
			const matchProperty = line.match( '^\\t{' + ( scope.currentIndent ) + '}(\\w+):[\\s\\t\\r\\n](.*)' );
			const matchEnd = line.match( '^\\t{' + ( scope.currentIndent - 1 ) + '}}' );

			if ( matchBeginning ) {

				scope.parseNodeBegin( line, matchBeginning );

			} else if ( matchProperty ) {

				scope.parseNodeProperty( line, matchProperty, split[ ++ i ] );

			} else if ( matchEnd ) {

				scope.popStack();

			} else if ( line.match( /^[^\s\t}]/ ) ) {

				// large arrays are split over multiple lines terminated with a ',' character
				// if this is encountered the line needs to be joined to the previous line
				scope.parseNodePropertyContinued( line );

			}

		} );

		return this.allNodes;

	}
```
</details>

### `TextParser.parseNodeBegin(line: any, property: any): void`

**Parameters:**

- **`line`** `any`
- **`property`** `any`

**Returns:** `void`

**Calls:**

- `property[ 1 ].trim().replace( /^"/, '' ).replace`
- `property[ 2 ].split( ',' ).map`
- `attr.trim().replace( /^"/, '' ).replace`
- `this.parseNodeAttr`
- `this.getCurrentNode`
- `this.allNodes.add`
- `currentNode.PoseNode.push`
- `this.pushStack`

**Internal Comments:**
```
// a top node
// if the subnode already exists, append it
// special case Pose needs PoseNodes as an array
```

<details><summary>Code</summary>

```typescript
parseNodeBegin( line, property ) {

		const nodeName = property[ 1 ].trim().replace( /^"/, '' ).replace( /"$/, '' );

		const nodeAttrs = property[ 2 ].split( ',' ).map( function ( attr ) {

			return attr.trim().replace( /^"/, '' ).replace( /"$/, '' );

		} );

		const node = { name: nodeName };
		const attrs = this.parseNodeAttr( nodeAttrs );

		const currentNode = this.getCurrentNode();

		// a top node
		if ( this.currentIndent === 0 ) {

			this.allNodes.add( nodeName, node );

		} else { // a subnode

			// if the subnode already exists, append it
			if ( nodeName in currentNode ) {

				// special case Pose needs PoseNodes as an array
				if ( nodeName === 'PoseNode' ) {

					currentNode.PoseNode.push( node );

				} else if ( currentNode[ nodeName ].id !== undefined ) {

					currentNode[ nodeName ] = {};
					currentNode[ nodeName ][ currentNode[ nodeName ].id ] = currentNode[ nodeName ];

				}

				if ( attrs.id !== '' ) currentNode[ nodeName ][ attrs.id ] = node;

			} else if ( typeof attrs.id === 'number' ) {

				currentNode[ nodeName ] = {};
				currentNode[ nodeName ][ attrs.id ] = node;

			} else if ( nodeName !== 'Properties70' ) {

				if ( nodeName === 'PoseNode' )	currentNode[ nodeName ] = [ node ];
				else currentNode[ nodeName ] = node;

			}

		}

		if ( typeof attrs.id === 'number' ) node.id = attrs.id;
		if ( attrs.name !== '' ) node.attrName = attrs.name;
		if ( attrs.type !== '' ) node.attrType = attrs.type;

		this.pushStack( node );

	}
```
</details>

### `TextParser.parseNodeAttr(attrs: any): { id: any; name: string; type: string; }`

**Parameters:**

- **`attrs`** `any`

**Returns:** `{ id: any; name: string; type: string; }`

**Calls:**

- `parseInt`
- `isNaN`
- `attrs[ 1 ].replace`

<details><summary>Code</summary>

```typescript
parseNodeAttr( attrs ) {

		let id = attrs[ 0 ];

		if ( attrs[ 0 ] !== '' ) {

			id = parseInt( attrs[ 0 ] );

			if ( isNaN( id ) ) {

				id = attrs[ 0 ];

			}

		}

		let name = '', type = '';

		if ( attrs.length > 1 ) {

			name = attrs[ 1 ].replace( /^(\w+)::/, '' );
			type = attrs[ 2 ];

		}

		return { id: id, name: name, type: type };

	}
```
</details>

### `TextParser.parseNodeProperty(line: any, property: any, contentLine: any): void`

**Parameters:**

- **`line`** `any`
- **`property`** `any`
- **`contentLine`** `any`

**Returns:** `void`

**Calls:**

- `property[ 1 ].replace( /^"/, '' ).replace( /"$/, '' ).trim`
- `property[ 2 ].replace( /^"/, '' ).replace( /"$/, '' ).trim`
- `contentLine.replace( /"/g, '' ).replace( /,$/, '' ).trim`
- `this.getCurrentNode`
- `this.parseNodeSpecialProperty`
- `propValue.split( ',' ).slice`
- `parseInt`
- `rest.map`
- `elem.trim().replace`
- `append`
- `Array.isArray`
- `currentNode[ propName ].push`
- `this.setCurrentProp`
- `propValue.slice`
- `parseNumberArray`

**Internal Comments:**
```
// for special case: base64 image data follows "Content: ," line
//	Content: ,
//	 "/9j/4RDaRXhpZgAATU0A..."
// Connections
// Node
// connections
// convert string to array, unless it ends in ',' in which case more will be added to it
```

<details><summary>Code</summary>

```typescript
parseNodeProperty( line, property, contentLine ) {

		let propName = property[ 1 ].replace( /^"/, '' ).replace( /"$/, '' ).trim();
		let propValue = property[ 2 ].replace( /^"/, '' ).replace( /"$/, '' ).trim();

		// for special case: base64 image data follows "Content: ," line
		//	Content: ,
		//	 "/9j/4RDaRXhpZgAATU0A..."
		if ( propName === 'Content' && propValue === ',' ) {

			propValue = contentLine.replace( /"/g, '' ).replace( /,$/, '' ).trim();

		}

		const currentNode = this.getCurrentNode();
		const parentName = currentNode.name;

		if ( parentName === 'Properties70' ) {

			this.parseNodeSpecialProperty( line, propName, propValue );
			return;

		}

		// Connections
		if ( propName === 'C' ) {

			const connProps = propValue.split( ',' ).slice( 1 );
			const from = parseInt( connProps[ 0 ] );
			const to = parseInt( connProps[ 1 ] );

			let rest = propValue.split( ',' ).slice( 3 );

			rest = rest.map( function ( elem ) {

				return elem.trim().replace( /^"/, '' );

			} );

			propName = 'connections';
			propValue = [ from, to ];
			append( propValue, rest );

			if ( currentNode[ propName ] === undefined ) {

				currentNode[ propName ] = [];

			}

		}

		// Node
		if ( propName === 'Node' ) currentNode.id = propValue;

		// connections
		if ( propName in currentNode && Array.isArray( currentNode[ propName ] ) ) {

			currentNode[ propName ].push( propValue );

		} else {

			if ( propName !== 'a' ) currentNode[ propName ] = propValue;
			else currentNode.a = propValue;

		}

		this.setCurrentProp( currentNode, propName );

		// convert string to array, unless it ends in ',' in which case more will be added to it
		if ( propName === 'a' && propValue.slice( - 1 ) !== ',' ) {

			currentNode.a = parseNumberArray( propValue );

		}

	}
```
</details>

### `TextParser.parseNodePropertyContinued(line: any): void`

**Parameters:**

- **`line`** `any`

**Returns:** `void`

**Calls:**

- `this.getCurrentNode`
- `line.slice`
- `parseNumberArray`

**Internal Comments:**
```
// if the line doesn't end in ',' we have reached the end of the property value
// so convert the string to an array
```

<details><summary>Code</summary>

```typescript
parseNodePropertyContinued( line ) {

		const currentNode = this.getCurrentNode();

		currentNode.a += line;

		// if the line doesn't end in ',' we have reached the end of the property value
		// so convert the string to an array
		if ( line.slice( - 1 ) !== ',' ) {

			currentNode.a = parseNumberArray( currentNode.a );

		}

	}
```
</details>

### `TextParser.parseNodeSpecialProperty(line: any, propName: any, propValue: any): void`

**Parameters:**

- **`line`** `any`
- **`propName`** `any`
- **`propValue`** `any`

**Returns:** `void`

**Calls:**

- `propValue.split( '",' ).map`
- `prop.trim().replace( /^\"/, '' ).replace`
- `parseFloat`
- `parseNumberArray`
- `this.getPrevNode`
- `this.setCurrentProp`

**Internal Comments:**
```
// split this (x2)
// P: "Lcl Scaling", "Lcl Scaling", "", "A",1,1,1 (x2)
// into array like below (x2)
// ["Lcl Scaling", "Lcl Scaling", "", "A", "1,1,1" ] (x2)
// cast values where needed, otherwise leave as strings
// CAUTION: these props must append to parent's parent (x6)
```

<details><summary>Code</summary>

```typescript
parseNodeSpecialProperty( line, propName, propValue ) {

		// split this
		// P: "Lcl Scaling", "Lcl Scaling", "", "A",1,1,1
		// into array like below
		// ["Lcl Scaling", "Lcl Scaling", "", "A", "1,1,1" ]
		const props = propValue.split( '",' ).map( function ( prop ) {

			return prop.trim().replace( /^\"/, '' ).replace( /\s/, '_' );

		} );

		const innerPropName = props[ 0 ];
		const innerPropType1 = props[ 1 ];
		const innerPropType2 = props[ 2 ];
		const innerPropFlag = props[ 3 ];
		let innerPropValue = props[ 4 ];

		// cast values where needed, otherwise leave as strings
		switch ( innerPropType1 ) {

			case 'int':
			case 'enum':
			case 'bool':
			case 'ULongLong':
			case 'double':
			case 'Number':
			case 'FieldOfView':
				innerPropValue = parseFloat( innerPropValue );
				break;

			case 'Color':
			case 'ColorRGB':
			case 'Vector3D':
			case 'Lcl_Translation':
			case 'Lcl_Rotation':
			case 'Lcl_Scaling':
				innerPropValue = parseNumberArray( innerPropValue );
				break;

		}

		// CAUTION: these props must append to parent's parent
		this.getPrevNode()[ innerPropName ] = {

			'type': innerPropType1,
			'type2': innerPropType2,
			'flag': innerPropFlag,
			'value': innerPropValue

		};

		this.setCurrentProp( this.getPrevNode(), innerPropName );

	}
```
</details>

### `BinaryParser.parse(buffer: any): FBXTree`

**Parameters:**

- **`buffer`** `any`

**Returns:** `FBXTree`

**Calls:**

- `reader.skip`
- `reader.getUint32`
- `this.endOfContent`
- `this.parseNode`
- `allNodes.add`

<details><summary>Code</summary>

```typescript
parse( buffer ) {

		const reader = new BinaryReader( buffer );
		reader.skip( 23 ); // skip magic 23 bytes

		const version = reader.getUint32();

		if ( version < 6400 ) {

			throw new Error( 'THREE.FBXLoader: FBX version not supported, FileVersion: ' + version );

		}

		const allNodes = new FBXTree();

		while ( ! this.endOfContent( reader ) ) {

			const node = this.parseNode( reader, version );
			if ( node !== null ) allNodes.add( node.name, node );

		}

		return allNodes;

	}
```
</details>

### `BinaryParser.endOfContent(reader: any): boolean`

**Parameters:**

- **`reader`** `any`

**Returns:** `boolean`

**Calls:**

- `reader.size`
- `reader.getOffset`

**Internal Comments:**
```
// footer size: 160bytes + 16-byte alignment padding
// - 16bytes: magic (x2)
// - padding til 16-byte alignment (at least 1byte?)
//	(seems like some exporters embed fixed 15 or 16bytes?)
// - 4bytes: magic
// - 4bytes: version
// - 120bytes: zero
```

<details><summary>Code</summary>

```typescript
endOfContent( reader ) {

		// footer size: 160bytes + 16-byte alignment padding
		// - 16bytes: magic
		// - padding til 16-byte alignment (at least 1byte?)
		//	(seems like some exporters embed fixed 15 or 16bytes?)
		// - 4bytes: magic
		// - 4bytes: version
		// - 120bytes: zero
		// - 16bytes: magic
		if ( reader.size() % 16 === 0 ) {

			return ( ( reader.getOffset() + 160 + 16 ) & ~ 0xf ) >= reader.size();

		} else {

			return reader.getOffset() + 160 + 16 >= reader.size();

		}

	}
```
</details>

### `BinaryParser.parseNode(reader: any, version: any): { singleProperty: boolean; propertyList: any[]; id: number; attrName: any; attrType: any; name: any; }`

**Parameters:**

- **`reader`** `any`
- **`version`** `any`

**Returns:** `{ singleProperty: boolean; propertyList: any[]; id: number; attrName: any; attrType: any; name: any; }`

**Calls:**

- `reader.getUint64`
- `reader.getUint32`
- `reader.getUint8`
- `reader.getString`
- `propertyList.push`
- `this.parseProperty`
- `reader.getOffset`
- `this.parseNode`
- `this.parseSubNode`

**Internal Comments:**
```
// The first three data sizes depends on version. (x2)
// Regards this node as NULL-record if endOffset is zero
// Regards the first three elements in propertyList as id, attrName, and attrType (x2)
// check if this node represents just a single property (x4)
// like (name, 0) set or (name2, [0, 1, 2]) set of {name: 0, name2: [0, 1, 2]} (x4)
```

<details><summary>Code</summary>

```typescript
parseNode( reader, version ) {

		const node = {};

		// The first three data sizes depends on version.
		const endOffset = ( version >= 7500 ) ? reader.getUint64() : reader.getUint32();
		const numProperties = ( version >= 7500 ) ? reader.getUint64() : reader.getUint32();

		( version >= 7500 ) ? reader.getUint64() : reader.getUint32(); // the returned propertyListLen is not used

		const nameLen = reader.getUint8();
		const name = reader.getString( nameLen );

		// Regards this node as NULL-record if endOffset is zero
		if ( endOffset === 0 ) return null;

		const propertyList = [];

		for ( let i = 0; i < numProperties; i ++ ) {

			propertyList.push( this.parseProperty( reader ) );

		}

		// Regards the first three elements in propertyList as id, attrName, and attrType
		const id = propertyList.length > 0 ? propertyList[ 0 ] : '';
		const attrName = propertyList.length > 1 ? propertyList[ 1 ] : '';
		const attrType = propertyList.length > 2 ? propertyList[ 2 ] : '';

		// check if this node represents just a single property
		// like (name, 0) set or (name2, [0, 1, 2]) set of {name: 0, name2: [0, 1, 2]}
		node.singleProperty = ( numProperties === 1 && reader.getOffset() === endOffset ) ? true : false;

		while ( endOffset > reader.getOffset() ) {

			const subNode = this.parseNode( reader, version );

			if ( subNode !== null ) this.parseSubNode( name, node, subNode );

		}

		node.propertyList = propertyList; // raw property list used by parent

		if ( typeof id === 'number' ) node.id = id;
		if ( attrName !== '' ) node.attrName = attrName;
		if ( attrType !== '' ) node.attrType = attrType;
		if ( name !== '' ) node.name = name;

		return node;

	}
```
</details>

### `BinaryParser.parseSubNode(name: any, node: any, subNode: any): void`

**Parameters:**

- **`name`** `any`
- **`node`** `any`
- **`subNode`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `subNode.propertyList.forEach`
- `array.push`
- `node.connections.push`
- `Object.keys`
- `keys.forEach`
- `innerPropName.indexOf`
- `innerPropName.replace`
- `innerPropType1.indexOf`
- `innerPropType1.replace`
- `node[ subNode.name ].push`

**Internal Comments:**
```
// special case: child node is single property
// first Connection is FBX type (OO, OP, etc.). We'll discard these
// this will be copied to parent, see above (x4)
```

<details><summary>Code</summary>

```typescript
parseSubNode( name, node, subNode ) {

		// special case: child node is single property
		if ( subNode.singleProperty === true ) {

			const value = subNode.propertyList[ 0 ];

			if ( Array.isArray( value ) ) {

				node[ subNode.name ] = subNode;

				subNode.a = value;

			} else {

				node[ subNode.name ] = value;

			}

		} else if ( name === 'Connections' && subNode.name === 'C' ) {

			const array = [];

			subNode.propertyList.forEach( function ( property, i ) {

				// first Connection is FBX type (OO, OP, etc.). We'll discard these
				if ( i !== 0 ) array.push( property );

			} );

			if ( node.connections === undefined ) {

				node.connections = [];

			}

			node.connections.push( array );

		} else if ( subNode.name === 'Properties70' ) {

			const keys = Object.keys( subNode );

			keys.forEach( function ( key ) {

				node[ key ] = subNode[ key ];

			} );

		} else if ( name === 'Properties70' && subNode.name === 'P' ) {

			let innerPropName = subNode.propertyList[ 0 ];
			let innerPropType1 = subNode.propertyList[ 1 ];
			const innerPropType2 = subNode.propertyList[ 2 ];
			const innerPropFlag = subNode.propertyList[ 3 ];
			let innerPropValue;

			if ( innerPropName.indexOf( 'Lcl ' ) === 0 ) innerPropName = innerPropName.replace( 'Lcl ', 'Lcl_' );
			if ( innerPropType1.indexOf( 'Lcl ' ) === 0 ) innerPropType1 = innerPropType1.replace( 'Lcl ', 'Lcl_' );

			if ( innerPropType1 === 'Color' || innerPropType1 === 'ColorRGB' || innerPropType1 === 'Vector' || innerPropType1 === 'Vector3D' || innerPropType1.indexOf( 'Lcl_' ) === 0 ) {

				innerPropValue = [
					subNode.propertyList[ 4 ],
					subNode.propertyList[ 5 ],
					subNode.propertyList[ 6 ]
				];

			} else {

				innerPropValue = subNode.propertyList[ 4 ];

			}

			// this will be copied to parent, see above
			node[ innerPropName ] = {

				'type': innerPropType1,
				'type2': innerPropType2,
				'flag': innerPropFlag,
				'value': innerPropValue

			};

		} else if ( node[ subNode.name ] === undefined ) {

			if ( typeof subNode.id === 'number' ) {

				node[ subNode.name ] = {};
				node[ subNode.name ][ subNode.id ] = subNode;

			} else {

				node[ subNode.name ] = subNode;

			}

		} else {

			if ( subNode.name === 'PoseNode' ) {

				if ( ! Array.isArray( node[ subNode.name ] ) ) {

					node[ subNode.name ] = [ node[ subNode.name ] ];

				}

				node[ subNode.name ].push( subNode );

			} else if ( node[ subNode.name ][ subNode.id ] === undefined ) {

				node[ subNode.name ][ subNode.id ] = subNode;

			}

		}

	}
```
</details>

### `BinaryParser.parseProperty(reader: any): any`

**Parameters:**

- **`reader`** `any`

**Returns:** `any`

**Calls:**

- `reader.getString`
- `reader.getBoolean`
- `reader.getFloat64`
- `reader.getFloat32`
- `reader.getInt32`
- `reader.getInt64`
- `reader.getUint32`
- `reader.getArrayBuffer`
- `reader.getInt16`
- `reader.getBooleanArray`
- `reader.getFloat64Array`
- `reader.getFloat32Array`
- `reader.getInt32Array`
- `reader.getInt64Array`
- `fflate.unzlibSync`
- `reader2.getBooleanArray`
- `reader2.getFloat64Array`
- `reader2.getFloat32Array`
- `reader2.getInt32Array`
- `reader2.getInt64Array`

<details><summary>Code</summary>

```typescript
parseProperty( reader ) {

		const type = reader.getString( 1 );
		let length;

		switch ( type ) {

			case 'C':
				return reader.getBoolean();

			case 'D':
				return reader.getFloat64();

			case 'F':
				return reader.getFloat32();

			case 'I':
				return reader.getInt32();

			case 'L':
				return reader.getInt64();

			case 'R':
				length = reader.getUint32();
				return reader.getArrayBuffer( length );

			case 'S':
				length = reader.getUint32();
				return reader.getString( length );

			case 'Y':
				return reader.getInt16();

			case 'b':
			case 'c':
			case 'd':
			case 'f':
			case 'i':
			case 'l':

				const arrayLength = reader.getUint32();
				const encoding = reader.getUint32(); // 0: non-compressed, 1: compressed
				const compressedLength = reader.getUint32();

				if ( encoding === 0 ) {

					switch ( type ) {

						case 'b':
						case 'c':
							return reader.getBooleanArray( arrayLength );

						case 'd':
							return reader.getFloat64Array( arrayLength );

						case 'f':
							return reader.getFloat32Array( arrayLength );

						case 'i':
							return reader.getInt32Array( arrayLength );

						case 'l':
							return reader.getInt64Array( arrayLength );

					}

				}

				const data = fflate.unzlibSync( new Uint8Array( reader.getArrayBuffer( compressedLength ) ) );
				const reader2 = new BinaryReader( data.buffer );

				switch ( type ) {

					case 'b':
					case 'c':
						return reader2.getBooleanArray( arrayLength );

					case 'd':
						return reader2.getFloat64Array( arrayLength );

					case 'f':
						return reader2.getFloat32Array( arrayLength );

					case 'i':
						return reader2.getInt32Array( arrayLength );

					case 'l':
						return reader2.getInt64Array( arrayLength );

				}

				break; // cannot happen but is required by the DeepScan

			default:
				throw new Error( 'THREE.FBXLoader: Unknown property type ' + type );

		}

	}
```
</details>

### `BinaryReader.getOffset(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getOffset() {

		return this.offset;

	}
```
</details>

### `BinaryReader.size(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
size() {

		return this.dv.buffer.byteLength;

	}
```
</details>

### `BinaryReader.skip(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
skip( length ) {

		this.offset += length;

	}
```
</details>

### `BinaryReader.getBoolean(): boolean`

**Returns:** `boolean`

**Calls:**

- `this.getUint8`

<details><summary>Code</summary>

```typescript
getBoolean() {

		return ( this.getUint8() & 1 ) === 1;

	}
```
</details>

### `BinaryReader.getBooleanArray(size: any): boolean[]`

**Parameters:**

- **`size`** `any`

**Returns:** `boolean[]`

**Calls:**

- `a.push`
- `this.getBoolean`

<details><summary>Code</summary>

```typescript
getBooleanArray( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getBoolean() );

		}

		return a;

	}
```
</details>

### `BinaryReader.getUint8(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getUint8`

<details><summary>Code</summary>

```typescript
getUint8() {

		const value = this.dv.getUint8( this.offset );
		this.offset += 1;
		return value;

	}
```
</details>

### `BinaryReader.getInt16(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getInt16`

<details><summary>Code</summary>

```typescript
getInt16() {

		const value = this.dv.getInt16( this.offset, this.littleEndian );
		this.offset += 2;
		return value;

	}
```
</details>

### `BinaryReader.getInt32(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getInt32`

<details><summary>Code</summary>

```typescript
getInt32() {

		const value = this.dv.getInt32( this.offset, this.littleEndian );
		this.offset += 4;
		return value;

	}
```
</details>

### `BinaryReader.getInt32Array(size: any): number[]`

**Parameters:**

- **`size`** `any`

**Returns:** `number[]`

**Calls:**

- `a.push`
- `this.getInt32`

<details><summary>Code</summary>

```typescript
getInt32Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getInt32() );

		}

		return a;

	}
```
</details>

### `BinaryReader.getUint32(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getUint32`

<details><summary>Code</summary>

```typescript
getUint32() {

		const value = this.dv.getUint32( this.offset, this.littleEndian );
		this.offset += 4;
		return value;

	}
```
</details>

### `BinaryReader.getInt64(): number`

**Returns:** `number`

**Calls:**

- `this.getUint32`

**Internal Comments:**
```
// calculate negative value
```

<details><summary>Code</summary>

```typescript
getInt64() {

		let low, high;

		if ( this.littleEndian ) {

			low = this.getUint32();
			high = this.getUint32();

		} else {

			high = this.getUint32();
			low = this.getUint32();

		}

		// calculate negative value
		if ( high & 0x80000000 ) {

			high = ~ high & 0xFFFFFFFF;
			low = ~ low & 0xFFFFFFFF;

			if ( low === 0xFFFFFFFF ) high = ( high + 1 ) & 0xFFFFFFFF;

			low = ( low + 1 ) & 0xFFFFFFFF;

			return - ( high * 0x100000000 + low );

		}

		return high * 0x100000000 + low;

	}
```
</details>

### `BinaryReader.getInt64Array(size: any): number[]`

**Parameters:**

- **`size`** `any`

**Returns:** `number[]`

**Calls:**

- `a.push`
- `this.getInt64`

<details><summary>Code</summary>

```typescript
getInt64Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getInt64() );

		}

		return a;

	}
```
</details>

### `BinaryReader.getUint64(): number`

**Returns:** `number`

**Calls:**

- `this.getUint32`

<details><summary>Code</summary>

```typescript
getUint64() {

		let low, high;

		if ( this.littleEndian ) {

			low = this.getUint32();
			high = this.getUint32();

		} else {

			high = this.getUint32();
			low = this.getUint32();

		}

		return high * 0x100000000 + low;

	}
```
</details>

### `BinaryReader.getFloat32(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getFloat32`

<details><summary>Code</summary>

```typescript
getFloat32() {

		const value = this.dv.getFloat32( this.offset, this.littleEndian );
		this.offset += 4;
		return value;

	}
```
</details>

### `BinaryReader.getFloat32Array(size: any): number[]`

**Parameters:**

- **`size`** `any`

**Returns:** `number[]`

**Calls:**

- `a.push`
- `this.getFloat32`

<details><summary>Code</summary>

```typescript
getFloat32Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat32() );

		}

		return a;

	}
```
</details>

### `BinaryReader.getFloat64(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getFloat64`

<details><summary>Code</summary>

```typescript
getFloat64() {

		const value = this.dv.getFloat64( this.offset, this.littleEndian );
		this.offset += 8;
		return value;

	}
```
</details>

### `BinaryReader.getFloat64Array(size: any): number[]`

**Parameters:**

- **`size`** `any`

**Returns:** `number[]`

**Calls:**

- `a.push`
- `this.getFloat64`

<details><summary>Code</summary>

```typescript
getFloat64Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat64() );

		}

		return a;

	}
```
</details>

### `BinaryReader.getArrayBuffer(size: any): any`

**Parameters:**

- **`size`** `any`

**Returns:** `any`

**Calls:**

- `this.dv.buffer.slice`

<details><summary>Code</summary>

```typescript
getArrayBuffer( size ) {

		const value = this.dv.buffer.slice( this.offset, this.offset + size );
		this.offset += size;
		return value;

	}
```
</details>

### `BinaryReader.getString(size: any): string`

**Parameters:**

- **`size`** `any`

**Returns:** `string`

**Calls:**

- `this.skip`
- `a.indexOf`
- `this._textDecoder.decode`

<details><summary>Code</summary>

```typescript
getString( size ) {

		const start = this.offset;
		let a = new Uint8Array( this.dv.buffer, start, size );

		this.skip( size );

		const nullByte = a.indexOf( 0 );
		if ( nullByte >= 0 ) a = new Uint8Array( this.dv.buffer, start, nullByte );

		return this._textDecoder.decode( a );

	}
```
</details>

### `FBXTree.add(key: any, val: any): void`

**Parameters:**

- **`key`** `any`
- **`val`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
add( key, val ) {

		this[ key ] = val;

	}
```
</details>

### `isFbxFormatBinary(buffer: any): boolean`

**Parameters:**

- **`buffer`** `any`

**Returns:** `boolean`

**Calls:**

- `convertArrayBufferToString`

<details><summary>Code</summary>

```typescript
function isFbxFormatBinary( buffer ) {

	const CORRECT = 'Kaydara\u0020FBX\u0020Binary\u0020\u0020\0';

	return buffer.byteLength >= CORRECT.length && CORRECT === convertArrayBufferToString( buffer, 0, CORRECT.length );

}
```
</details>

### `isFbxFormatASCII(text: any): boolean`

**Parameters:**

- **`text`** `any`

**Returns:** `boolean`

**Calls:**

- `text.slice`
- `read`

<details><summary>Code</summary>

```typescript
function isFbxFormatASCII( text ) {

	const CORRECT = [ 'K', 'a', 'y', 'd', 'a', 'r', 'a', '\\', 'F', 'B', 'X', '\\', 'B', 'i', 'n', 'a', 'r', 'y', '\\', '\\' ];

	let cursor = 0;

	function read( offset ) {

		const result = text[ offset - 1 ];
		text = text.slice( cursor + offset );
		cursor ++;
		return result;

	}

	for ( let i = 0; i < CORRECT.length; ++ i ) {

		const num = read( 1 );
		if ( num === CORRECT[ i ] ) {

			return false;

		}

	}

	return true;

}
```
</details>

### `read(offset: any): any`

**Parameters:**

- **`offset`** `any`

**Returns:** `any`

**Calls:**

- `text.slice`

<details><summary>Code</summary>

```typescript
function read( offset ) {

		const result = text[ offset - 1 ];
		text = text.slice( cursor + offset );
		cursor ++;
		return result;

	}
```
</details>

### `getFbxVersion(text: any): number`

**Parameters:**

- **`text`** `any`

**Returns:** `number`

**Calls:**

- `text.match`
- `parseInt`

<details><summary>Code</summary>

```typescript
function getFbxVersion( text ) {

	const versionRegExp = /FBXVersion: (\d+)/;
	const match = text.match( versionRegExp );

	if ( match ) {

		const version = parseInt( match[ 1 ] );
		return version;

	}

	throw new Error( 'THREE.FBXLoader: Cannot find the version number for the file given.' );

}
```
</details>

### `convertFBXTimeToSeconds(time: any): number`

**Parameters:**

- **`time`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function convertFBXTimeToSeconds( time ) {

	return time / 46186158000;

}
```
</details>

### `getData(polygonVertexIndex: any, polygonIndex: any, vertexIndex: any, infoObject: any): any`

**Parameters:**

- **`polygonVertexIndex`** `any`
- **`polygonIndex`** `any`
- **`vertexIndex`** `any`
- **`infoObject`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`
- `slice`

<details><summary>Code</summary>

```typescript
function getData( polygonVertexIndex, polygonIndex, vertexIndex, infoObject ) {

	let index;

	switch ( infoObject.mappingType ) {

		case 'ByPolygonVertex' :
			index = polygonVertexIndex;
			break;
		case 'ByPolygon' :
			index = polygonIndex;
			break;
		case 'ByVertice' :
			index = vertexIndex;
			break;
		case 'AllSame' :
			index = infoObject.indices[ 0 ];
			break;
		default :
			console.warn( 'THREE.FBXLoader: unknown attribute mapping type ' + infoObject.mappingType );

	}

	if ( infoObject.referenceType === 'IndexToDirect' ) index = infoObject.indices[ index ];

	const from = index * infoObject.dataSize;
	const to = from + infoObject.dataSize;

	return slice( dataArray, infoObject.buffer, from, to );

}
```
</details>

### `generateTransform(transformData: any): any`

**Parameters:**

- **`transformData`** `any`

**Returns:** `any`

**Calls:**

- `lTranslationM.setPosition`
- `tempVec.fromArray`
- `getEulerOrder`
- `transformData.preRotation.map`
- `array.push`
- `lPreRotationM.makeRotationFromEuler`
- `tempEuler.fromArray`
- `transformData.rotation.map`
- `lRotationM.makeRotationFromEuler`
- `transformData.postRotation.map`
- `lPostRotationM.makeRotationFromEuler`
- `lPostRotationM.invert`
- `lScalingM.scale`
- `lScalingOffsetM.setPosition`
- `lScalingPivotM.setPosition`
- `lRotationOffsetM.setPosition`
- `lRotationPivotM.setPosition`
- `lParentLX.copy`
- `lParentGX.copy`
- `lPreRotationM.clone().multiply( lRotationM ).multiply`
- `lParentGRM.extractRotation`
- `lParentTM.copyPosition`
- `lParentTM.clone().invert().multiply`
- `lParentGRM.clone().invert().multiply`
- `lGlobalRS.copy( lParentGRM ).multiply( lLRM ).multiply( lParentGSM ).multiply`
- `lGlobalRS.copy( lParentGRM ).multiply( lParentGSM ).multiply( lLRM ).multiply`
- `new Matrix4().scale`
- `new Vector3().setFromMatrixScale`
- `lParentLSM.clone().invert`
- `lParentGSM.clone().multiply`
- `lGlobalRS.copy( lParentGRM ).multiply( lLRM ).multiply( lParentGSM_noLocal ).multiply`
- `lRotationPivotM.clone().invert`
- `lScalingPivotM.clone().invert`
- `lTranslationM.clone().multiply( lRotationOffsetM ).multiply( lRotationPivotM ).multiply( lPreRotationM ).multiply( lRotationM ).multiply( lPostRotationM ).multiply( lRotationPivotM_inv ).multiply( lScalingOffsetM ).multiply( lScalingPivotM ).multiply( lScalingM ).multiply`
- `new Matrix4().copyPosition`
- `lParentGX.clone().multiply`
- `lGlobalT.copyPosition`
- `lGlobalT.clone().multiply`
- `lTransform.premultiply`
- `lParentGX.invert`

**Internal Comments:**
```
// For Maya models using "Joint Orient", Euler order only applies to rotation, not pre/post-rotations (x2)
// Pivots and offsets
// parent transform
// Global Rotation (x2)
// Global Shear*Scaling (x2)
// Calculate the local transform matrix (x2)
// from global to local (x4)
```

<details><summary>Code</summary>

```typescript
function generateTransform( transformData ) {

	const lTranslationM = new Matrix4();
	const lPreRotationM = new Matrix4();
	const lRotationM = new Matrix4();
	const lPostRotationM = new Matrix4();

	const lScalingM = new Matrix4();
	const lScalingPivotM = new Matrix4();
	const lScalingOffsetM = new Matrix4();
	const lRotationOffsetM = new Matrix4();
	const lRotationPivotM = new Matrix4();

	const lParentGX = new Matrix4();
	const lParentLX = new Matrix4();
	const lGlobalT = new Matrix4();

	const inheritType = ( transformData.inheritType ) ? transformData.inheritType : 0;

	if ( transformData.translation ) lTranslationM.setPosition( tempVec.fromArray( transformData.translation ) );

	// For Maya models using "Joint Orient", Euler order only applies to rotation, not pre/post-rotations
	const defaultEulerOrder = getEulerOrder( 0 );

	if ( transformData.preRotation ) {

		const array = transformData.preRotation.map( MathUtils.degToRad );
		array.push( defaultEulerOrder );
		lPreRotationM.makeRotationFromEuler( tempEuler.fromArray( array ) );

	}

	if ( transformData.rotation ) {

		const array = transformData.rotation.map( MathUtils.degToRad );
		array.push( transformData.eulerOrder || defaultEulerOrder );
		lRotationM.makeRotationFromEuler( tempEuler.fromArray( array ) );

	}

	if ( transformData.postRotation ) {

		const array = transformData.postRotation.map( MathUtils.degToRad );
		array.push( defaultEulerOrder );
		lPostRotationM.makeRotationFromEuler( tempEuler.fromArray( array ) );
		lPostRotationM.invert();

	}

	if ( transformData.scale ) lScalingM.scale( tempVec.fromArray( transformData.scale ) );

	// Pivots and offsets
	if ( transformData.scalingOffset ) lScalingOffsetM.setPosition( tempVec.fromArray( transformData.scalingOffset ) );
	if ( transformData.scalingPivot ) lScalingPivotM.setPosition( tempVec.fromArray( transformData.scalingPivot ) );
	if ( transformData.rotationOffset ) lRotationOffsetM.setPosition( tempVec.fromArray( transformData.rotationOffset ) );
	if ( transformData.rotationPivot ) lRotationPivotM.setPosition( tempVec.fromArray( transformData.rotationPivot ) );

	// parent transform
	if ( transformData.parentMatrixWorld ) {

		lParentLX.copy( transformData.parentMatrix );
		lParentGX.copy( transformData.parentMatrixWorld );

	}

	const lLRM = lPreRotationM.clone().multiply( lRotationM ).multiply( lPostRotationM );
	// Global Rotation
	const lParentGRM = new Matrix4();
	lParentGRM.extractRotation( lParentGX );

	// Global Shear*Scaling
	const lParentTM = new Matrix4();
	lParentTM.copyPosition( lParentGX );

	const lParentGRSM = lParentTM.clone().invert().multiply( lParentGX );
	const lParentGSM = lParentGRM.clone().invert().multiply( lParentGRSM );
	const lLSM = lScalingM;

	const lGlobalRS = new Matrix4();

	if ( inheritType === 0 ) {

		lGlobalRS.copy( lParentGRM ).multiply( lLRM ).multiply( lParentGSM ).multiply( lLSM );

	} else if ( inheritType === 1 ) {

		lGlobalRS.copy( lParentGRM ).multiply( lParentGSM ).multiply( lLRM ).multiply( lLSM );

	} else {

		const lParentLSM = new Matrix4().scale( new Vector3().setFromMatrixScale( lParentLX ) );
		const lParentLSM_inv = lParentLSM.clone().invert();
		const lParentGSM_noLocal = lParentGSM.clone().multiply( lParentLSM_inv );

		lGlobalRS.copy( lParentGRM ).multiply( lLRM ).multiply( lParentGSM_noLocal ).multiply( lLSM );

	}

	const lRotationPivotM_inv = lRotationPivotM.clone().invert();
	const lScalingPivotM_inv = lScalingPivotM.clone().invert();
	// Calculate the local transform matrix
	let lTransform = lTranslationM.clone().multiply( lRotationOffsetM ).multiply( lRotationPivotM ).multiply( lPreRotationM ).multiply( lRotationM ).multiply( lPostRotationM ).multiply( lRotationPivotM_inv ).multiply( lScalingOffsetM ).multiply( lScalingPivotM ).multiply( lScalingM ).multiply( lScalingPivotM_inv );

	const lLocalTWithAllPivotAndOffsetInfo = new Matrix4().copyPosition( lTransform );

	const lGlobalTranslation = lParentGX.clone().multiply( lLocalTWithAllPivotAndOffsetInfo );
	lGlobalT.copyPosition( lGlobalTranslation );

	lTransform = lGlobalT.clone().multiply( lGlobalRS );

	// from global to local
	lTransform.premultiply( lParentGX.invert() );

	return lTransform;

}
```
</details>

### `getEulerOrder(order: any): string`

**Parameters:**

- **`order`** `any`

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function getEulerOrder( order ) {

	order = order || 0;

	const enums = [
		'ZYX', // -> XYZ extrinsic
		'YZX', // -> XZY extrinsic
		'XZY', // -> YZX extrinsic
		'ZXY', // -> YXZ extrinsic
		'YXZ', // -> ZXY extrinsic
		'XYZ', // -> ZYX extrinsic
		//'SphericXYZ', // not possible to support
	];

	if ( order === 6 ) {

		console.warn( 'THREE.FBXLoader: unsupported Euler Order: Spherical XYZ. Animations and rotations may be incorrect.' );
		return enums[ 0 ];

	}

	return enums[ order ];

}
```
</details>

### `parseNumberArray(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `value.split( ',' ).map`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function parseNumberArray( value ) {

	const array = value.split( ',' ).map( function ( val ) {

		return parseFloat( val );

	} );

	return array;

}
```
</details>

### `convertArrayBufferToString(buffer: any, from: any, to: any): string`

**Parameters:**

- **`buffer`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `string`

**Calls:**

- `new TextDecoder().decode`

<details><summary>Code</summary>

```typescript
function convertArrayBufferToString( buffer, from, to ) {

	if ( from === undefined ) from = 0;
	if ( to === undefined ) to = buffer.byteLength;

	return new TextDecoder().decode( new Uint8Array( buffer, from, to ) );

}
```
</details>

### `append(a: any, b: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function append( a, b ) {

	for ( let i = 0, j = a.length, l = b.length; i < l; i ++, j ++ ) {

		a[ j ] = b[ i ];

	}

}
```
</details>

### `slice(a: any, b: any, from: any, to: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function slice( a, b, from, to ) {

	for ( let i = from, j = 0; i < to; i ++, j ++ ) {

		a[ j ] = b[ i ];

	}

	return a;

}
```
</details>


---

## Classes

### `FBXLoader`

<details><summary>Class Code</summary>

```ts
class FBXLoader extends Loader {

	/**
	 * Constructs a new FBX loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded FBX asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( scope.path === '' ) ? LoaderUtils.extractUrlBase( url ) : scope.path;

		const loader = new FileLoader( this.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );

		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer, path ) );

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
	 * Parses the given FBX data and returns the resulting group.
	 *
	 * @param {ArrayBuffer} FBXBuffer - The raw FBX data as an array buffer.
	 * @param {string} path - The URL base path.
	 * @return {Group} An object representing the parsed asset.
	 */
	parse( FBXBuffer, path ) {

		if ( isFbxFormatBinary( FBXBuffer ) ) {

			fbxTree = new BinaryParser().parse( FBXBuffer );

		} else {

			const FBXText = convertArrayBufferToString( FBXBuffer );

			if ( ! isFbxFormatASCII( FBXText ) ) {

				throw new Error( 'THREE.FBXLoader: Unknown format.' );

			}

			if ( getFbxVersion( FBXText ) < 7000 ) {

				throw new Error( 'THREE.FBXLoader: FBX version not supported, FileVersion: ' + getFbxVersion( FBXText ) );

			}

			fbxTree = new TextParser().parse( FBXText );

		}

		// console.log( fbxTree );

		const textureLoader = new TextureLoader( this.manager ).setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		return new FBXTreeParser( textureLoader, this.manager ).parse( fbxTree );

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

		const path = ( scope.path === '' ) ? LoaderUtils.extractUrlBase( url ) : scope.path;

		const loader = new FileLoader( this.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );

		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer, path ) );

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

##### `parse(FBXBuffer: ArrayBuffer, path: string): Group`

<details><summary>Code</summary>

```ts
parse( FBXBuffer, path ) {

		if ( isFbxFormatBinary( FBXBuffer ) ) {

			fbxTree = new BinaryParser().parse( FBXBuffer );

		} else {

			const FBXText = convertArrayBufferToString( FBXBuffer );

			if ( ! isFbxFormatASCII( FBXText ) ) {

				throw new Error( 'THREE.FBXLoader: Unknown format.' );

			}

			if ( getFbxVersion( FBXText ) < 7000 ) {

				throw new Error( 'THREE.FBXLoader: FBX version not supported, FileVersion: ' + getFbxVersion( FBXText ) );

			}

			fbxTree = new TextParser().parse( FBXText );

		}

		// console.log( fbxTree );

		const textureLoader = new TextureLoader( this.manager ).setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		return new FBXTreeParser( textureLoader, this.manager ).parse( fbxTree );

	}
```
</details>

### `FBXTreeParser`

<details><summary>Class Code</summary>

```ts
class FBXTreeParser {

	constructor( textureLoader, manager ) {

		this.textureLoader = textureLoader;
		this.manager = manager;

	}

	parse() {

		connections = this.parseConnections();

		const images = this.parseImages();
		const textures = this.parseTextures( images );
		const materials = this.parseMaterials( textures );
		const deformers = this.parseDeformers();
		const geometryMap = new GeometryParser().parse( deformers );

		this.parseScene( deformers, geometryMap, materials );

		return sceneGraph;

	}

	// Parses FBXTree.Connections which holds parent-child connections between objects (e.g. material -> texture, model->geometry )
	// and details the connection type
	parseConnections() {

		const connectionMap = new Map();

		if ( 'Connections' in fbxTree ) {

			const rawConnections = fbxTree.Connections.connections;

			rawConnections.forEach( function ( rawConnection ) {

				const fromID = rawConnection[ 0 ];
				const toID = rawConnection[ 1 ];
				const relationship = rawConnection[ 2 ];

				if ( ! connectionMap.has( fromID ) ) {

					connectionMap.set( fromID, {
						parents: [],
						children: []
					} );

				}

				const parentRelationship = { ID: toID, relationship: relationship };
				connectionMap.get( fromID ).parents.push( parentRelationship );

				if ( ! connectionMap.has( toID ) ) {

					connectionMap.set( toID, {
						parents: [],
						children: []
					} );

				}

				const childRelationship = { ID: fromID, relationship: relationship };
				connectionMap.get( toID ).children.push( childRelationship );

			} );

		}

		return connectionMap;

	}

	// Parse FBXTree.Objects.Video for embedded image data
	// These images are connected to textures in FBXTree.Objects.Textures
	// via FBXTree.Connections.
	parseImages() {

		const images = {};
		const blobs = {};

		if ( 'Video' in fbxTree.Objects ) {

			const videoNodes = fbxTree.Objects.Video;

			for ( const nodeID in videoNodes ) {

				const videoNode = videoNodes[ nodeID ];

				const id = parseInt( nodeID );

				images[ id ] = videoNode.RelativeFilename || videoNode.Filename;

				// raw image data is in videoNode.Content
				if ( 'Content' in videoNode ) {

					const arrayBufferContent = ( videoNode.Content instanceof ArrayBuffer ) && ( videoNode.Content.byteLength > 0 );
					const base64Content = ( typeof videoNode.Content === 'string' ) && ( videoNode.Content !== '' );

					if ( arrayBufferContent || base64Content ) {

						const image = this.parseImage( videoNodes[ nodeID ] );

						blobs[ videoNode.RelativeFilename || videoNode.Filename ] = image;

					}

				}

			}

		}

		for ( const id in images ) {

			const filename = images[ id ];

			if ( blobs[ filename ] !== undefined ) images[ id ] = blobs[ filename ];
			else images[ id ] = images[ id ].split( '\\' ).pop();

		}

		return images;

	}

	// Parse embedded image data in FBXTree.Video.Content
	parseImage( videoNode ) {

		const content = videoNode.Content;
		const fileName = videoNode.RelativeFilename || videoNode.Filename;
		const extension = fileName.slice( fileName.lastIndexOf( '.' ) + 1 ).toLowerCase();

		let type;

		switch ( extension ) {

			case 'bmp':

				type = 'image/bmp';
				break;

			case 'jpg':
			case 'jpeg':

				type = 'image/jpeg';
				break;

			case 'png':

				type = 'image/png';
				break;

			case 'tif':

				type = 'image/tiff';
				break;

			case 'tga':

				if ( this.manager.getHandler( '.tga' ) === null ) {

					console.warn( 'FBXLoader: TGA loader not found, skipping ', fileName );

				}

				type = 'image/tga';
				break;

			case 'webp':

				type = 'image/webp';
				break;

			default:

				console.warn( 'FBXLoader: Image type "' + extension + '" is not supported.' );
				return;

		}

		if ( typeof content === 'string' ) { // ASCII format

			return 'data:' + type + ';base64,' + content;

		} else { // Binary Format

			const array = new Uint8Array( content );
			return window.URL.createObjectURL( new Blob( [ array ], { type: type } ) );

		}

	}

	// Parse nodes in FBXTree.Objects.Texture
	// These contain details such as UV scaling, cropping, rotation etc and are connected
	// to images in FBXTree.Objects.Video
	parseTextures( images ) {

		const textureMap = new Map();

		if ( 'Texture' in fbxTree.Objects ) {

			const textureNodes = fbxTree.Objects.Texture;
			for ( const nodeID in textureNodes ) {

				const texture = this.parseTexture( textureNodes[ nodeID ], images );
				textureMap.set( parseInt( nodeID ), texture );

			}

		}

		return textureMap;

	}

	// Parse individual node in FBXTree.Objects.Texture
	parseTexture( textureNode, images ) {

		const texture = this.loadTexture( textureNode, images );

		texture.ID = textureNode.id;

		texture.name = textureNode.attrName;

		const wrapModeU = textureNode.WrapModeU;
		const wrapModeV = textureNode.WrapModeV;

		const valueU = wrapModeU !== undefined ? wrapModeU.value : 0;
		const valueV = wrapModeV !== undefined ? wrapModeV.value : 0;

		// http://download.autodesk.com/us/fbx/SDKdocs/FBX_SDK_Help/files/fbxsdkref/class_k_fbx_texture.html#889640e63e2e681259ea81061b85143a
		// 0: repeat(default), 1: clamp

		texture.wrapS = valueU === 0 ? RepeatWrapping : ClampToEdgeWrapping;
		texture.wrapT = valueV === 0 ? RepeatWrapping : ClampToEdgeWrapping;

		if ( 'Scaling' in textureNode ) {

			const values = textureNode.Scaling.value;

			texture.repeat.x = values[ 0 ];
			texture.repeat.y = values[ 1 ];

		}

		if ( 'Translation' in textureNode ) {

			const values = textureNode.Translation.value;

			texture.offset.x = values[ 0 ];
			texture.offset.y = values[ 1 ];

		}

		return texture;

	}

	// load a texture specified as a blob or data URI, or via an external URL using TextureLoader
	loadTexture( textureNode, images ) {

		const extension = textureNode.FileName.split( '.' ).pop().toLowerCase();

		let loader = this.manager.getHandler( `.${extension}` );
		if ( loader === null ) loader = this.textureLoader;

		const loaderPath = loader.path;

		if ( ! loaderPath ) {

			loader.setPath( this.textureLoader.path );

		}

		const children = connections.get( textureNode.id ).children;

		let fileName;

		if ( children !== undefined && children.length > 0 && images[ children[ 0 ].ID ] !== undefined ) {

			fileName = images[ children[ 0 ].ID ];

			if ( fileName.indexOf( 'blob:' ) === 0 || fileName.indexOf( 'data:' ) === 0 ) {

				loader.setPath( undefined );

			}

		}

		if ( fileName === undefined ) {

			console.warn( 'FBXLoader: Undefined filename, creating placeholder texture.' );
			return new Texture();

		}

		const texture = loader.load( fileName );

		// revert to initial path
		loader.setPath( loaderPath );

		return texture;

	}

	// Parse nodes in FBXTree.Objects.Material
	parseMaterials( textureMap ) {

		const materialMap = new Map();

		if ( 'Material' in fbxTree.Objects ) {

			const materialNodes = fbxTree.Objects.Material;

			for ( const nodeID in materialNodes ) {

				const material = this.parseMaterial( materialNodes[ nodeID ], textureMap );

				if ( material !== null ) materialMap.set( parseInt( nodeID ), material );

			}

		}

		return materialMap;

	}

	// Parse single node in FBXTree.Objects.Material
	// Materials are connected to texture maps in FBXTree.Objects.Textures
	// FBX format currently only supports Lambert and Phong shading models
	parseMaterial( materialNode, textureMap ) {

		const ID = materialNode.id;
		const name = materialNode.attrName;
		let type = materialNode.ShadingModel;

		// Case where FBX wraps shading model in property object.
		if ( typeof type === 'object' ) {

			type = type.value;

		}

		// Ignore unused materials which don't have any connections.
		if ( ! connections.has( ID ) ) return null;

		const parameters = this.parseParameters( materialNode, textureMap, ID );

		let material;

		switch ( type.toLowerCase() ) {

			case 'phong':
				material = new MeshPhongMaterial();
				break;
			case 'lambert':
				material = new MeshLambertMaterial();
				break;
			default:
				console.warn( 'THREE.FBXLoader: unknown material type "%s". Defaulting to MeshPhongMaterial.', type );
				material = new MeshPhongMaterial();
				break;

		}

		material.setValues( parameters );
		material.name = name;

		return material;

	}

	// Parse FBX material and return parameters suitable for a three.js material
	// Also parse the texture map and return any textures associated with the material
	parseParameters( materialNode, textureMap, ID ) {

		const parameters = {};

		if ( materialNode.BumpFactor ) {

			parameters.bumpScale = materialNode.BumpFactor.value;

		}

		if ( materialNode.Diffuse ) {

			parameters.color = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.Diffuse.value ), SRGBColorSpace );

		} else if ( materialNode.DiffuseColor && ( materialNode.DiffuseColor.type === 'Color' || materialNode.DiffuseColor.type === 'ColorRGB' ) ) {

			// The blender exporter exports diffuse here instead of in materialNode.Diffuse
			parameters.color = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.DiffuseColor.value ), SRGBColorSpace );

		}

		if ( materialNode.DisplacementFactor ) {

			parameters.displacementScale = materialNode.DisplacementFactor.value;

		}

		if ( materialNode.Emissive ) {

			parameters.emissive = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.Emissive.value ), SRGBColorSpace );

		} else if ( materialNode.EmissiveColor && ( materialNode.EmissiveColor.type === 'Color' || materialNode.EmissiveColor.type === 'ColorRGB' ) ) {

			// The blender exporter exports emissive color here instead of in materialNode.Emissive
			parameters.emissive = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.EmissiveColor.value ), SRGBColorSpace );

		}

		if ( materialNode.EmissiveFactor ) {

			parameters.emissiveIntensity = parseFloat( materialNode.EmissiveFactor.value );

		}

		// the transparency handling is implemented based on Blender/Unity's approach: https://github.com/sobotka/blender-addons/blob/7d80f2f97161fc8e353a657b179b9aa1f8e5280b/io_scene_fbx/import_fbx.py#L1444-L1459

		parameters.opacity = 1 - ( materialNode.TransparencyFactor ? parseFloat( materialNode.TransparencyFactor.value ) : 0 );

		if ( parameters.opacity === 1 || parameters.opacity === 0 ) {

			parameters.opacity = ( materialNode.Opacity ? parseFloat( materialNode.Opacity.value ) : null );

			if ( parameters.opacity === null ) {

				parameters.opacity = 1 - ( materialNode.TransparentColor ? parseFloat( materialNode.TransparentColor.value[ 0 ] ) : 0 );

			}

		}

		if ( parameters.opacity < 1.0 ) {

			parameters.transparent = true;

		}

		if ( materialNode.ReflectionFactor ) {

			parameters.reflectivity = materialNode.ReflectionFactor.value;

		}

		if ( materialNode.Shininess ) {

			parameters.shininess = materialNode.Shininess.value;

		}

		if ( materialNode.Specular ) {

			parameters.specular = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.Specular.value ), SRGBColorSpace );

		} else if ( materialNode.SpecularColor && materialNode.SpecularColor.type === 'Color' ) {

			// The blender exporter exports specular color here instead of in materialNode.Specular
			parameters.specular = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.SpecularColor.value ), SRGBColorSpace );

		}

		const scope = this;
		connections.get( ID ).children.forEach( function ( child ) {

			const type = child.relationship;

			switch ( type ) {

				case 'Bump':
					parameters.bumpMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'Maya|TEX_ao_map':
					parameters.aoMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'DiffuseColor':
				case 'Maya|TEX_color_map':
					parameters.map = scope.getTexture( textureMap, child.ID );
					if ( parameters.map !== undefined ) {

						parameters.map.colorSpace = SRGBColorSpace;

					}

					break;

				case 'DisplacementColor':
					parameters.displacementMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'EmissiveColor':
					parameters.emissiveMap = scope.getTexture( textureMap, child.ID );
					if ( parameters.emissiveMap !== undefined ) {

						parameters.emissiveMap.colorSpace = SRGBColorSpace;

					}

					break;

				case 'NormalMap':
				case 'Maya|TEX_normal_map':
					parameters.normalMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'ReflectionColor':
					parameters.envMap = scope.getTexture( textureMap, child.ID );
					if ( parameters.envMap !== undefined ) {

						parameters.envMap.mapping = EquirectangularReflectionMapping;
						parameters.envMap.colorSpace = SRGBColorSpace;

					}

					break;

				case 'SpecularColor':
					parameters.specularMap = scope.getTexture( textureMap, child.ID );
					if ( parameters.specularMap !== undefined ) {

						parameters.specularMap.colorSpace = SRGBColorSpace;

					}

					break;

				case 'TransparentColor':
				case 'TransparencyFactor':
					parameters.alphaMap = scope.getTexture( textureMap, child.ID );
					parameters.transparent = true;
					break;

				case 'AmbientColor':
				case 'ShininessExponent': // AKA glossiness map
				case 'SpecularFactor': // AKA specularLevel
				case 'VectorDisplacementColor': // NOTE: Seems to be a copy of DisplacementColor
				default:
					console.warn( 'THREE.FBXLoader: %s map is not supported in three.js, skipping texture.', type );
					break;

			}

		} );

		return parameters;

	}

	// get a texture from the textureMap for use by a material.
	getTexture( textureMap, id ) {

		// if the texture is a layered texture, just use the first layer and issue a warning
		if ( 'LayeredTexture' in fbxTree.Objects && id in fbxTree.Objects.LayeredTexture ) {

			console.warn( 'THREE.FBXLoader: layered textures are not supported in three.js. Discarding all but first layer.' );
			id = connections.get( id ).children[ 0 ].ID;

		}

		return textureMap.get( id );

	}

	// Parse nodes in FBXTree.Objects.Deformer
	// Deformer node can contain skinning or Vertex Cache animation data, however only skinning is supported here
	// Generates map of Skeleton-like objects for use later when generating and binding skeletons.
	parseDeformers() {

		const skeletons = {};
		const morphTargets = {};

		if ( 'Deformer' in fbxTree.Objects ) {

			const DeformerNodes = fbxTree.Objects.Deformer;

			for ( const nodeID in DeformerNodes ) {

				const deformerNode = DeformerNodes[ nodeID ];

				const relationships = connections.get( parseInt( nodeID ) );

				if ( deformerNode.attrType === 'Skin' ) {

					const skeleton = this.parseSkeleton( relationships, DeformerNodes );
					skeleton.ID = nodeID;

					if ( relationships.parents.length > 1 ) console.warn( 'THREE.FBXLoader: skeleton attached to more than one geometry is not supported.' );
					skeleton.geometryID = relationships.parents[ 0 ].ID;

					skeletons[ nodeID ] = skeleton;

				} else if ( deformerNode.attrType === 'BlendShape' ) {

					const morphTarget = {
						id: nodeID,
					};

					morphTarget.rawTargets = this.parseMorphTargets( relationships, DeformerNodes );
					morphTarget.id = nodeID;

					if ( relationships.parents.length > 1 ) console.warn( 'THREE.FBXLoader: morph target attached to more than one geometry is not supported.' );

					morphTargets[ nodeID ] = morphTarget;

				}

			}

		}

		return {

			skeletons: skeletons,
			morphTargets: morphTargets,

		};

	}

	// Parse single nodes in FBXTree.Objects.Deformer
	// The top level skeleton node has type 'Skin' and sub nodes have type 'Cluster'
	// Each skin node represents a skeleton and each cluster node represents a bone
	parseSkeleton( relationships, deformerNodes ) {

		const rawBones = [];

		relationships.children.forEach( function ( child ) {

			const boneNode = deformerNodes[ child.ID ];

			if ( boneNode.attrType !== 'Cluster' ) return;

			const rawBone = {

				ID: child.ID,
				indices: [],
				weights: [],
				transformLink: new Matrix4().fromArray( boneNode.TransformLink.a ),
				// transform: new Matrix4().fromArray( boneNode.Transform.a ),
				// linkMode: boneNode.Mode,

			};

			if ( 'Indexes' in boneNode ) {

				rawBone.indices = boneNode.Indexes.a;
				rawBone.weights = boneNode.Weights.a;

			}

			rawBones.push( rawBone );

		} );

		return {

			rawBones: rawBones,
			bones: []

		};

	}

	// The top level morph deformer node has type "BlendShape" and sub nodes have type "BlendShapeChannel"
	parseMorphTargets( relationships, deformerNodes ) {

		const rawMorphTargets = [];

		for ( let i = 0; i < relationships.children.length; i ++ ) {

			const child = relationships.children[ i ];

			const morphTargetNode = deformerNodes[ child.ID ];

			const rawMorphTarget = {

				name: morphTargetNode.attrName,
				initialWeight: morphTargetNode.DeformPercent,
				id: morphTargetNode.id,
				fullWeights: morphTargetNode.FullWeights.a

			};

			if ( morphTargetNode.attrType !== 'BlendShapeChannel' ) return;

			rawMorphTarget.geoID = connections.get( parseInt( child.ID ) ).children.filter( function ( child ) {

				return child.relationship === undefined;

			} )[ 0 ].ID;

			rawMorphTargets.push( rawMorphTarget );

		}

		return rawMorphTargets;

	}

	// create the main Group() to be returned by the loader
	parseScene( deformers, geometryMap, materialMap ) {

		sceneGraph = new Group();

		const modelMap = this.parseModels( deformers.skeletons, geometryMap, materialMap );

		const modelNodes = fbxTree.Objects.Model;

		const scope = this;
		modelMap.forEach( function ( model ) {

			const modelNode = modelNodes[ model.ID ];
			scope.setLookAtProperties( model, modelNode );

			const parentConnections = connections.get( model.ID ).parents;

			parentConnections.forEach( function ( connection ) {

				const parent = modelMap.get( connection.ID );
				if ( parent !== undefined ) parent.add( model );

			} );

			if ( model.parent === null ) {

				sceneGraph.add( model );

			}


		} );

		this.bindSkeleton( deformers.skeletons, geometryMap, modelMap );

		this.addGlobalSceneSettings();

		sceneGraph.traverse( function ( node ) {

			if ( node.userData.transformData ) {

				if ( node.parent ) {

					node.userData.transformData.parentMatrix = node.parent.matrix;
					node.userData.transformData.parentMatrixWorld = node.parent.matrixWorld;

				}

				const transform = generateTransform( node.userData.transformData );

				node.applyMatrix4( transform );
				node.updateWorldMatrix();

			}

		} );

		const animations = new AnimationParser().parse();

		// if all the models where already combined in a single group, just return that
		if ( sceneGraph.children.length === 1 && sceneGraph.children[ 0 ].isGroup ) {

			sceneGraph.children[ 0 ].animations = animations;
			sceneGraph = sceneGraph.children[ 0 ];

		}

		sceneGraph.animations = animations;

	}

	// parse nodes in FBXTree.Objects.Model
	parseModels( skeletons, geometryMap, materialMap ) {

		const modelMap = new Map();
		const modelNodes = fbxTree.Objects.Model;

		for ( const nodeID in modelNodes ) {

			const id = parseInt( nodeID );
			const node = modelNodes[ nodeID ];
			const relationships = connections.get( id );

			let model = this.buildSkeleton( relationships, skeletons, id, node.attrName );

			if ( ! model ) {

				switch ( node.attrType ) {

					case 'Camera':
						model = this.createCamera( relationships );
						break;
					case 'Light':
						model = this.createLight( relationships );
						break;
					case 'Mesh':
						model = this.createMesh( relationships, geometryMap, materialMap );
						break;
					case 'NurbsCurve':
						model = this.createCurve( relationships, geometryMap );
						break;
					case 'LimbNode':
					case 'Root':
						model = new Bone();
						break;
					case 'Null':
					default:
						model = new Group();
						break;

				}

				model.name = node.attrName ? PropertyBinding.sanitizeNodeName( node.attrName ) : '';
				model.userData.originalName = node.attrName;

				model.ID = id;

			}

			this.getTransformData( model, node );
			modelMap.set( id, model );

		}

		return modelMap;

	}

	buildSkeleton( relationships, skeletons, id, name ) {

		let bone = null;

		relationships.parents.forEach( function ( parent ) {

			for ( const ID in skeletons ) {

				const skeleton = skeletons[ ID ];

				skeleton.rawBones.forEach( function ( rawBone, i ) {

					if ( rawBone.ID === parent.ID ) {

						const subBone = bone;
						bone = new Bone();

						bone.matrixWorld.copy( rawBone.transformLink );

						// set name and id here - otherwise in cases where "subBone" is created it will not have a name / id

						bone.name = name ? PropertyBinding.sanitizeNodeName( name ) : '';
						bone.userData.originalName = name;
						bone.ID = id;

						skeleton.bones[ i ] = bone;

						// In cases where a bone is shared between multiple meshes
						// duplicate the bone here and add it as a child of the first bone
						if ( subBone !== null ) {

							bone.add( subBone );

						}

					}

				} );

			}

		} );

		return bone;

	}

	// create a PerspectiveCamera or OrthographicCamera
	createCamera( relationships ) {

		let model;
		let cameraAttribute;

		relationships.children.forEach( function ( child ) {

			const attr = fbxTree.Objects.NodeAttribute[ child.ID ];

			if ( attr !== undefined ) {

				cameraAttribute = attr;

			}

		} );

		if ( cameraAttribute === undefined ) {

			model = new Object3D();

		} else {

			let type = 0;
			if ( cameraAttribute.CameraProjectionType !== undefined && cameraAttribute.CameraProjectionType.value === 1 ) {

				type = 1;

			}

			let nearClippingPlane = 1;
			if ( cameraAttribute.NearPlane !== undefined ) {

				nearClippingPlane = cameraAttribute.NearPlane.value / 1000;

			}

			let farClippingPlane = 1000;
			if ( cameraAttribute.FarPlane !== undefined ) {

				farClippingPlane = cameraAttribute.FarPlane.value / 1000;

			}


			let width = window.innerWidth;
			let height = window.innerHeight;

			if ( cameraAttribute.AspectWidth !== undefined && cameraAttribute.AspectHeight !== undefined ) {

				width = cameraAttribute.AspectWidth.value;
				height = cameraAttribute.AspectHeight.value;

			}

			const aspect = width / height;

			let fov = 45;
			if ( cameraAttribute.FieldOfView !== undefined ) {

				fov = cameraAttribute.FieldOfView.value;

			}

			const focalLength = cameraAttribute.FocalLength ? cameraAttribute.FocalLength.value : null;

			switch ( type ) {

				case 0: // Perspective
					model = new PerspectiveCamera( fov, aspect, nearClippingPlane, farClippingPlane );
					if ( focalLength !== null ) model.setFocalLength( focalLength );
					break;

				case 1: // Orthographic
					console.warn( 'THREE.FBXLoader: Orthographic cameras not supported yet.' );
					model = new Object3D();
					break;

				default:
					console.warn( 'THREE.FBXLoader: Unknown camera type ' + type + '.' );
					model = new Object3D();
					break;

			}

		}

		return model;

	}

	// Create a DirectionalLight, PointLight or SpotLight
	createLight( relationships ) {

		let model;
		let lightAttribute;

		relationships.children.forEach( function ( child ) {

			const attr = fbxTree.Objects.NodeAttribute[ child.ID ];

			if ( attr !== undefined ) {

				lightAttribute = attr;

			}

		} );

		if ( lightAttribute === undefined ) {

			model = new Object3D();

		} else {

			let type;

			// LightType can be undefined for Point lights
			if ( lightAttribute.LightType === undefined ) {

				type = 0;

			} else {

				type = lightAttribute.LightType.value;

			}

			let color = 0xffffff;

			if ( lightAttribute.Color !== undefined ) {

				color = ColorManagement.colorSpaceToWorking( new Color().fromArray( lightAttribute.Color.value ), SRGBColorSpace );

			}

			let intensity = ( lightAttribute.Intensity === undefined ) ? 1 : lightAttribute.Intensity.value / 100;

			// light disabled
			if ( lightAttribute.CastLightOnObject !== undefined && lightAttribute.CastLightOnObject.value === 0 ) {

				intensity = 0;

			}

			let distance = 0;
			if ( lightAttribute.FarAttenuationEnd !== undefined ) {

				if ( lightAttribute.EnableFarAttenuation !== undefined && lightAttribute.EnableFarAttenuation.value === 0 ) {

					distance = 0;

				} else {

					distance = lightAttribute.FarAttenuationEnd.value;

				}

			}

			// TODO: could this be calculated linearly from FarAttenuationStart to FarAttenuationEnd?
			const decay = 1;

			switch ( type ) {

				case 0: // Point
					model = new PointLight( color, intensity, distance, decay );
					break;

				case 1: // Directional
					model = new DirectionalLight( color, intensity );
					break;

				case 2: // Spot
					let angle = Math.PI / 3;

					if ( lightAttribute.InnerAngle !== undefined ) {

						angle = MathUtils.degToRad( lightAttribute.InnerAngle.value );

					}

					let penumbra = 0;
					if ( lightAttribute.OuterAngle !== undefined ) {

						// TODO: this is not correct - FBX calculates outer and inner angle in degrees
						// with OuterAngle > InnerAngle && OuterAngle <= Math.PI
						// while three.js uses a penumbra between (0, 1) to attenuate the inner angle
						penumbra = MathUtils.degToRad( lightAttribute.OuterAngle.value );
						penumbra = Math.max( penumbra, 1 );

					}

					model = new SpotLight( color, intensity, distance, angle, penumbra, decay );
					break;

				default:
					console.warn( 'THREE.FBXLoader: Unknown light type ' + lightAttribute.LightType.value + ', defaulting to a PointLight.' );
					model = new PointLight( color, intensity );
					break;

			}

			if ( lightAttribute.CastShadows !== undefined && lightAttribute.CastShadows.value === 1 ) {

				model.castShadow = true;

			}

		}

		return model;

	}

	createMesh( relationships, geometryMap, materialMap ) {

		let model;
		let geometry = null;
		let material = null;
		const materials = [];

		// get geometry and materials(s) from connections
		relationships.children.forEach( function ( child ) {

			if ( geometryMap.has( child.ID ) ) {

				geometry = geometryMap.get( child.ID );

			}

			if ( materialMap.has( child.ID ) ) {

				materials.push( materialMap.get( child.ID ) );

			}

		} );

		if ( materials.length > 1 ) {

			material = materials;

		} else if ( materials.length > 0 ) {

			material = materials[ 0 ];

		} else {

			material = new MeshPhongMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0xcccccc
			} );
			materials.push( material );

		}

		if ( 'color' in geometry.attributes ) {

			materials.forEach( function ( material ) {

				material.vertexColors = true;

			} );

		}

		// Sanitization: If geometry has groups, then it must match the provided material array.
		// If not, we need to clean up the `group.materialIndex` properties inside the groups and point at a (new) default material.
		// This isn't well defined; Unity creates default material, while Blender implicitly uses the previous material in the list.
		if ( geometry.groups.length > 0 ) {

			let needsDefaultMaterial = false;

			for ( let i = 0, il = geometry.groups.length; i < il; i ++ ) {

				const group = geometry.groups[ i ];

				if ( group.materialIndex < 0 || group.materialIndex >= materials.length ) {

					group.materialIndex = materials.length;
					needsDefaultMaterial = true;

				}

			}

			if ( needsDefaultMaterial ) {

				const defaultMaterial = new MeshPhongMaterial();
				materials.push( defaultMaterial );

			}

		}

		if ( geometry.FBX_Deformer ) {

			model = new SkinnedMesh( geometry, material );
			model.normalizeSkinWeights();

		} else {

			model = new Mesh( geometry, material );

		}

		return model;

	}

	createCurve( relationships, geometryMap ) {

		const geometry = relationships.children.reduce( function ( geo, child ) {

			if ( geometryMap.has( child.ID ) ) geo = geometryMap.get( child.ID );

			return geo;

		}, null );

		// FBX does not list materials for Nurbs lines, so we'll just put our own in here.
		const material = new LineBasicMaterial( {
			name: Loader.DEFAULT_MATERIAL_NAME,
			color: 0x3300ff,
			linewidth: 1
		} );
		return new Line( geometry, material );

	}

	// parse the model node for transform data
	getTransformData( model, modelNode ) {

		const transformData = {};

		if ( 'InheritType' in modelNode ) transformData.inheritType = parseInt( modelNode.InheritType.value );

		if ( 'RotationOrder' in modelNode ) transformData.eulerOrder = getEulerOrder( modelNode.RotationOrder.value );
		else transformData.eulerOrder = getEulerOrder( 0 );

		if ( 'Lcl_Translation' in modelNode ) transformData.translation = modelNode.Lcl_Translation.value;

		if ( 'PreRotation' in modelNode ) transformData.preRotation = modelNode.PreRotation.value;
		if ( 'Lcl_Rotation' in modelNode ) transformData.rotation = modelNode.Lcl_Rotation.value;
		if ( 'PostRotation' in modelNode ) transformData.postRotation = modelNode.PostRotation.value;

		if ( 'Lcl_Scaling' in modelNode ) transformData.scale = modelNode.Lcl_Scaling.value;

		if ( 'ScalingOffset' in modelNode ) transformData.scalingOffset = modelNode.ScalingOffset.value;
		if ( 'ScalingPivot' in modelNode ) transformData.scalingPivot = modelNode.ScalingPivot.value;

		if ( 'RotationOffset' in modelNode ) transformData.rotationOffset = modelNode.RotationOffset.value;
		if ( 'RotationPivot' in modelNode ) transformData.rotationPivot = modelNode.RotationPivot.value;

		model.userData.transformData = transformData;

	}

	setLookAtProperties( model, modelNode ) {

		if ( 'LookAtProperty' in modelNode ) {

			const children = connections.get( model.ID ).children;

			children.forEach( function ( child ) {

				if ( child.relationship === 'LookAtProperty' ) {

					const lookAtTarget = fbxTree.Objects.Model[ child.ID ];

					if ( 'Lcl_Translation' in lookAtTarget ) {

						const pos = lookAtTarget.Lcl_Translation.value;

						// DirectionalLight, SpotLight
						if ( model.target !== undefined ) {

							model.target.position.fromArray( pos );
							sceneGraph.add( model.target );

						} else { // Cameras and other Object3Ds

							model.lookAt( new Vector3().fromArray( pos ) );

						}

					}

				}

			} );

		}

	}

	bindSkeleton( skeletons, geometryMap, modelMap ) {

		const bindMatrices = this.parsePoseNodes();

		for ( const ID in skeletons ) {

			const skeleton = skeletons[ ID ];

			const parents = connections.get( parseInt( skeleton.ID ) ).parents;

			parents.forEach( function ( parent ) {

				if ( geometryMap.has( parent.ID ) ) {

					const geoID = parent.ID;
					const geoRelationships = connections.get( geoID );

					geoRelationships.parents.forEach( function ( geoConnParent ) {

						if ( modelMap.has( geoConnParent.ID ) ) {

							const model = modelMap.get( geoConnParent.ID );

							model.bind( new Skeleton( skeleton.bones ), bindMatrices[ geoConnParent.ID ] );

						}

					} );

				}

			} );

		}

	}

	parsePoseNodes() {

		const bindMatrices = {};

		if ( 'Pose' in fbxTree.Objects ) {

			const BindPoseNode = fbxTree.Objects.Pose;

			for ( const nodeID in BindPoseNode ) {

				if ( BindPoseNode[ nodeID ].attrType === 'BindPose' && BindPoseNode[ nodeID ].NbPoseNodes > 0 ) {

					const poseNodes = BindPoseNode[ nodeID ].PoseNode;

					if ( Array.isArray( poseNodes ) ) {

						poseNodes.forEach( function ( poseNode ) {

							bindMatrices[ poseNode.Node ] = new Matrix4().fromArray( poseNode.Matrix.a );

						} );

					} else {

						bindMatrices[ poseNodes.Node ] = new Matrix4().fromArray( poseNodes.Matrix.a );

					}

				}

			}

		}

		return bindMatrices;

	}

	addGlobalSceneSettings() {

		if ( 'GlobalSettings' in fbxTree ) {

			if ( 'AmbientColor' in fbxTree.GlobalSettings ) {

				// Parse ambient color - if it's not set to black (default), create an ambient light

				const ambientColor = fbxTree.GlobalSettings.AmbientColor.value;
				const r = ambientColor[ 0 ];
				const g = ambientColor[ 1 ];
				const b = ambientColor[ 2 ];

				if ( r !== 0 || g !== 0 || b !== 0 ) {

					const color = new Color().setRGB( r, g, b, SRGBColorSpace );
					sceneGraph.add( new AmbientLight( color, 1 ) );

				}

			}

			if ( 'UnitScaleFactor' in fbxTree.GlobalSettings ) {

				sceneGraph.userData.unitScaleFactor = fbxTree.GlobalSettings.UnitScaleFactor.value;

			}

		}

	}

}
```
</details>

#### Methods

##### `parse(): any`

<details><summary>Code</summary>

```ts
parse() {

		connections = this.parseConnections();

		const images = this.parseImages();
		const textures = this.parseTextures( images );
		const materials = this.parseMaterials( textures );
		const deformers = this.parseDeformers();
		const geometryMap = new GeometryParser().parse( deformers );

		this.parseScene( deformers, geometryMap, materials );

		return sceneGraph;

	}
```
</details>

##### `parseConnections(): Map<any, any>`

<details><summary>Code</summary>

```ts
parseConnections() {

		const connectionMap = new Map();

		if ( 'Connections' in fbxTree ) {

			const rawConnections = fbxTree.Connections.connections;

			rawConnections.forEach( function ( rawConnection ) {

				const fromID = rawConnection[ 0 ];
				const toID = rawConnection[ 1 ];
				const relationship = rawConnection[ 2 ];

				if ( ! connectionMap.has( fromID ) ) {

					connectionMap.set( fromID, {
						parents: [],
						children: []
					} );

				}

				const parentRelationship = { ID: toID, relationship: relationship };
				connectionMap.get( fromID ).parents.push( parentRelationship );

				if ( ! connectionMap.has( toID ) ) {

					connectionMap.set( toID, {
						parents: [],
						children: []
					} );

				}

				const childRelationship = { ID: fromID, relationship: relationship };
				connectionMap.get( toID ).children.push( childRelationship );

			} );

		}

		return connectionMap;

	}
```
</details>

##### `parseImages(): {}`

<details><summary>Code</summary>

```ts
parseImages() {

		const images = {};
		const blobs = {};

		if ( 'Video' in fbxTree.Objects ) {

			const videoNodes = fbxTree.Objects.Video;

			for ( const nodeID in videoNodes ) {

				const videoNode = videoNodes[ nodeID ];

				const id = parseInt( nodeID );

				images[ id ] = videoNode.RelativeFilename || videoNode.Filename;

				// raw image data is in videoNode.Content
				if ( 'Content' in videoNode ) {

					const arrayBufferContent = ( videoNode.Content instanceof ArrayBuffer ) && ( videoNode.Content.byteLength > 0 );
					const base64Content = ( typeof videoNode.Content === 'string' ) && ( videoNode.Content !== '' );

					if ( arrayBufferContent || base64Content ) {

						const image = this.parseImage( videoNodes[ nodeID ] );

						blobs[ videoNode.RelativeFilename || videoNode.Filename ] = image;

					}

				}

			}

		}

		for ( const id in images ) {

			const filename = images[ id ];

			if ( blobs[ filename ] !== undefined ) images[ id ] = blobs[ filename ];
			else images[ id ] = images[ id ].split( '\\' ).pop();

		}

		return images;

	}
```
</details>

##### `parseImage(videoNode: any): string`

<details><summary>Code</summary>

```ts
parseImage( videoNode ) {

		const content = videoNode.Content;
		const fileName = videoNode.RelativeFilename || videoNode.Filename;
		const extension = fileName.slice( fileName.lastIndexOf( '.' ) + 1 ).toLowerCase();

		let type;

		switch ( extension ) {

			case 'bmp':

				type = 'image/bmp';
				break;

			case 'jpg':
			case 'jpeg':

				type = 'image/jpeg';
				break;

			case 'png':

				type = 'image/png';
				break;

			case 'tif':

				type = 'image/tiff';
				break;

			case 'tga':

				if ( this.manager.getHandler( '.tga' ) === null ) {

					console.warn( 'FBXLoader: TGA loader not found, skipping ', fileName );

				}

				type = 'image/tga';
				break;

			case 'webp':

				type = 'image/webp';
				break;

			default:

				console.warn( 'FBXLoader: Image type "' + extension + '" is not supported.' );
				return;

		}

		if ( typeof content === 'string' ) { // ASCII format

			return 'data:' + type + ';base64,' + content;

		} else { // Binary Format

			const array = new Uint8Array( content );
			return window.URL.createObjectURL( new Blob( [ array ], { type: type } ) );

		}

	}
```
</details>

##### `parseTextures(images: any): Map<any, any>`

<details><summary>Code</summary>

```ts
parseTextures( images ) {

		const textureMap = new Map();

		if ( 'Texture' in fbxTree.Objects ) {

			const textureNodes = fbxTree.Objects.Texture;
			for ( const nodeID in textureNodes ) {

				const texture = this.parseTexture( textureNodes[ nodeID ], images );
				textureMap.set( parseInt( nodeID ), texture );

			}

		}

		return textureMap;

	}
```
</details>

##### `parseTexture(textureNode: any, images: any): any`

<details><summary>Code</summary>

```ts
parseTexture( textureNode, images ) {

		const texture = this.loadTexture( textureNode, images );

		texture.ID = textureNode.id;

		texture.name = textureNode.attrName;

		const wrapModeU = textureNode.WrapModeU;
		const wrapModeV = textureNode.WrapModeV;

		const valueU = wrapModeU !== undefined ? wrapModeU.value : 0;
		const valueV = wrapModeV !== undefined ? wrapModeV.value : 0;

		// http://download.autodesk.com/us/fbx/SDKdocs/FBX_SDK_Help/files/fbxsdkref/class_k_fbx_texture.html#889640e63e2e681259ea81061b85143a
		// 0: repeat(default), 1: clamp

		texture.wrapS = valueU === 0 ? RepeatWrapping : ClampToEdgeWrapping;
		texture.wrapT = valueV === 0 ? RepeatWrapping : ClampToEdgeWrapping;

		if ( 'Scaling' in textureNode ) {

			const values = textureNode.Scaling.value;

			texture.repeat.x = values[ 0 ];
			texture.repeat.y = values[ 1 ];

		}

		if ( 'Translation' in textureNode ) {

			const values = textureNode.Translation.value;

			texture.offset.x = values[ 0 ];
			texture.offset.y = values[ 1 ];

		}

		return texture;

	}
```
</details>

##### `loadTexture(textureNode: any, images: any): any`

<details><summary>Code</summary>

```ts
loadTexture( textureNode, images ) {

		const extension = textureNode.FileName.split( '.' ).pop().toLowerCase();

		let loader = this.manager.getHandler( `.${extension}` );
		if ( loader === null ) loader = this.textureLoader;

		const loaderPath = loader.path;

		if ( ! loaderPath ) {

			loader.setPath( this.textureLoader.path );

		}

		const children = connections.get( textureNode.id ).children;

		let fileName;

		if ( children !== undefined && children.length > 0 && images[ children[ 0 ].ID ] !== undefined ) {

			fileName = images[ children[ 0 ].ID ];

			if ( fileName.indexOf( 'blob:' ) === 0 || fileName.indexOf( 'data:' ) === 0 ) {

				loader.setPath( undefined );

			}

		}

		if ( fileName === undefined ) {

			console.warn( 'FBXLoader: Undefined filename, creating placeholder texture.' );
			return new Texture();

		}

		const texture = loader.load( fileName );

		// revert to initial path
		loader.setPath( loaderPath );

		return texture;

	}
```
</details>

##### `parseMaterials(textureMap: any): Map<any, any>`

<details><summary>Code</summary>

```ts
parseMaterials( textureMap ) {

		const materialMap = new Map();

		if ( 'Material' in fbxTree.Objects ) {

			const materialNodes = fbxTree.Objects.Material;

			for ( const nodeID in materialNodes ) {

				const material = this.parseMaterial( materialNodes[ nodeID ], textureMap );

				if ( material !== null ) materialMap.set( parseInt( nodeID ), material );

			}

		}

		return materialMap;

	}
```
</details>

##### `parseMaterial(materialNode: any, textureMap: any): any`

<details><summary>Code</summary>

```ts
parseMaterial( materialNode, textureMap ) {

		const ID = materialNode.id;
		const name = materialNode.attrName;
		let type = materialNode.ShadingModel;

		// Case where FBX wraps shading model in property object.
		if ( typeof type === 'object' ) {

			type = type.value;

		}

		// Ignore unused materials which don't have any connections.
		if ( ! connections.has( ID ) ) return null;

		const parameters = this.parseParameters( materialNode, textureMap, ID );

		let material;

		switch ( type.toLowerCase() ) {

			case 'phong':
				material = new MeshPhongMaterial();
				break;
			case 'lambert':
				material = new MeshLambertMaterial();
				break;
			default:
				console.warn( 'THREE.FBXLoader: unknown material type "%s". Defaulting to MeshPhongMaterial.', type );
				material = new MeshPhongMaterial();
				break;

		}

		material.setValues( parameters );
		material.name = name;

		return material;

	}
```
</details>

##### `parseParameters(materialNode: any, textureMap: any, ID: any): { bumpScale: any; color: any; displacementScale: any; emissive: any; emissiveIntensity: number; opacity: number; transparent: boolean; reflectivity: any; shininess: any; specular: any; }`

<details><summary>Code</summary>

```ts
parseParameters( materialNode, textureMap, ID ) {

		const parameters = {};

		if ( materialNode.BumpFactor ) {

			parameters.bumpScale = materialNode.BumpFactor.value;

		}

		if ( materialNode.Diffuse ) {

			parameters.color = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.Diffuse.value ), SRGBColorSpace );

		} else if ( materialNode.DiffuseColor && ( materialNode.DiffuseColor.type === 'Color' || materialNode.DiffuseColor.type === 'ColorRGB' ) ) {

			// The blender exporter exports diffuse here instead of in materialNode.Diffuse
			parameters.color = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.DiffuseColor.value ), SRGBColorSpace );

		}

		if ( materialNode.DisplacementFactor ) {

			parameters.displacementScale = materialNode.DisplacementFactor.value;

		}

		if ( materialNode.Emissive ) {

			parameters.emissive = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.Emissive.value ), SRGBColorSpace );

		} else if ( materialNode.EmissiveColor && ( materialNode.EmissiveColor.type === 'Color' || materialNode.EmissiveColor.type === 'ColorRGB' ) ) {

			// The blender exporter exports emissive color here instead of in materialNode.Emissive
			parameters.emissive = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.EmissiveColor.value ), SRGBColorSpace );

		}

		if ( materialNode.EmissiveFactor ) {

			parameters.emissiveIntensity = parseFloat( materialNode.EmissiveFactor.value );

		}

		// the transparency handling is implemented based on Blender/Unity's approach: https://github.com/sobotka/blender-addons/blob/7d80f2f97161fc8e353a657b179b9aa1f8e5280b/io_scene_fbx/import_fbx.py#L1444-L1459

		parameters.opacity = 1 - ( materialNode.TransparencyFactor ? parseFloat( materialNode.TransparencyFactor.value ) : 0 );

		if ( parameters.opacity === 1 || parameters.opacity === 0 ) {

			parameters.opacity = ( materialNode.Opacity ? parseFloat( materialNode.Opacity.value ) : null );

			if ( parameters.opacity === null ) {

				parameters.opacity = 1 - ( materialNode.TransparentColor ? parseFloat( materialNode.TransparentColor.value[ 0 ] ) : 0 );

			}

		}

		if ( parameters.opacity < 1.0 ) {

			parameters.transparent = true;

		}

		if ( materialNode.ReflectionFactor ) {

			parameters.reflectivity = materialNode.ReflectionFactor.value;

		}

		if ( materialNode.Shininess ) {

			parameters.shininess = materialNode.Shininess.value;

		}

		if ( materialNode.Specular ) {

			parameters.specular = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.Specular.value ), SRGBColorSpace );

		} else if ( materialNode.SpecularColor && materialNode.SpecularColor.type === 'Color' ) {

			// The blender exporter exports specular color here instead of in materialNode.Specular
			parameters.specular = ColorManagement.colorSpaceToWorking( new Color().fromArray( materialNode.SpecularColor.value ), SRGBColorSpace );

		}

		const scope = this;
		connections.get( ID ).children.forEach( function ( child ) {

			const type = child.relationship;

			switch ( type ) {

				case 'Bump':
					parameters.bumpMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'Maya|TEX_ao_map':
					parameters.aoMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'DiffuseColor':
				case 'Maya|TEX_color_map':
					parameters.map = scope.getTexture( textureMap, child.ID );
					if ( parameters.map !== undefined ) {

						parameters.map.colorSpace = SRGBColorSpace;

					}

					break;

				case 'DisplacementColor':
					parameters.displacementMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'EmissiveColor':
					parameters.emissiveMap = scope.getTexture( textureMap, child.ID );
					if ( parameters.emissiveMap !== undefined ) {

						parameters.emissiveMap.colorSpace = SRGBColorSpace;

					}

					break;

				case 'NormalMap':
				case 'Maya|TEX_normal_map':
					parameters.normalMap = scope.getTexture( textureMap, child.ID );
					break;

				case 'ReflectionColor':
					parameters.envMap = scope.getTexture( textureMap, child.ID );
					if ( parameters.envMap !== undefined ) {

						parameters.envMap.mapping = EquirectangularReflectionMapping;
						parameters.envMap.colorSpace = SRGBColorSpace;

					}

					break;

				case 'SpecularColor':
					parameters.specularMap = scope.getTexture( textureMap, child.ID );
					if ( parameters.specularMap !== undefined ) {

						parameters.specularMap.colorSpace = SRGBColorSpace;

					}

					break;

				case 'TransparentColor':
				case 'TransparencyFactor':
					parameters.alphaMap = scope.getTexture( textureMap, child.ID );
					parameters.transparent = true;
					break;

				case 'AmbientColor':
				case 'ShininessExponent': // AKA glossiness map
				case 'SpecularFactor': // AKA specularLevel
				case 'VectorDisplacementColor': // NOTE: Seems to be a copy of DisplacementColor
				default:
					console.warn( 'THREE.FBXLoader: %s map is not supported in three.js, skipping texture.', type );
					break;

			}

		} );

		return parameters;

	}
```
</details>

##### `getTexture(textureMap: any, id: any): any`

<details><summary>Code</summary>

```ts
getTexture( textureMap, id ) {

		// if the texture is a layered texture, just use the first layer and issue a warning
		if ( 'LayeredTexture' in fbxTree.Objects && id in fbxTree.Objects.LayeredTexture ) {

			console.warn( 'THREE.FBXLoader: layered textures are not supported in three.js. Discarding all but first layer.' );
			id = connections.get( id ).children[ 0 ].ID;

		}

		return textureMap.get( id );

	}
```
</details>

##### `parseDeformers(): { skeletons: {}; morphTargets: {}; }`

<details><summary>Code</summary>

```ts
parseDeformers() {

		const skeletons = {};
		const morphTargets = {};

		if ( 'Deformer' in fbxTree.Objects ) {

			const DeformerNodes = fbxTree.Objects.Deformer;

			for ( const nodeID in DeformerNodes ) {

				const deformerNode = DeformerNodes[ nodeID ];

				const relationships = connections.get( parseInt( nodeID ) );

				if ( deformerNode.attrType === 'Skin' ) {

					const skeleton = this.parseSkeleton( relationships, DeformerNodes );
					skeleton.ID = nodeID;

					if ( relationships.parents.length > 1 ) console.warn( 'THREE.FBXLoader: skeleton attached to more than one geometry is not supported.' );
					skeleton.geometryID = relationships.parents[ 0 ].ID;

					skeletons[ nodeID ] = skeleton;

				} else if ( deformerNode.attrType === 'BlendShape' ) {

					const morphTarget = {
						id: nodeID,
					};

					morphTarget.rawTargets = this.parseMorphTargets( relationships, DeformerNodes );
					morphTarget.id = nodeID;

					if ( relationships.parents.length > 1 ) console.warn( 'THREE.FBXLoader: morph target attached to more than one geometry is not supported.' );

					morphTargets[ nodeID ] = morphTarget;

				}

			}

		}

		return {

			skeletons: skeletons,
			morphTargets: morphTargets,

		};

	}
```
</details>

##### `parseSkeleton(relationships: any, deformerNodes: any): { rawBones: any[]; bones: any[]; }`

<details><summary>Code</summary>

```ts
parseSkeleton( relationships, deformerNodes ) {

		const rawBones = [];

		relationships.children.forEach( function ( child ) {

			const boneNode = deformerNodes[ child.ID ];

			if ( boneNode.attrType !== 'Cluster' ) return;

			const rawBone = {

				ID: child.ID,
				indices: [],
				weights: [],
				transformLink: new Matrix4().fromArray( boneNode.TransformLink.a ),
				// transform: new Matrix4().fromArray( boneNode.Transform.a ),
				// linkMode: boneNode.Mode,

			};

			if ( 'Indexes' in boneNode ) {

				rawBone.indices = boneNode.Indexes.a;
				rawBone.weights = boneNode.Weights.a;

			}

			rawBones.push( rawBone );

		} );

		return {

			rawBones: rawBones,
			bones: []

		};

	}
```
</details>

##### `parseMorphTargets(relationships: any, deformerNodes: any): { name: any; initialWeight: any; id: any; fullWeights: any; }[]`

<details><summary>Code</summary>

```ts
parseMorphTargets( relationships, deformerNodes ) {

		const rawMorphTargets = [];

		for ( let i = 0; i < relationships.children.length; i ++ ) {

			const child = relationships.children[ i ];

			const morphTargetNode = deformerNodes[ child.ID ];

			const rawMorphTarget = {

				name: morphTargetNode.attrName,
				initialWeight: morphTargetNode.DeformPercent,
				id: morphTargetNode.id,
				fullWeights: morphTargetNode.FullWeights.a

			};

			if ( morphTargetNode.attrType !== 'BlendShapeChannel' ) return;

			rawMorphTarget.geoID = connections.get( parseInt( child.ID ) ).children.filter( function ( child ) {

				return child.relationship === undefined;

			} )[ 0 ].ID;

			rawMorphTargets.push( rawMorphTarget );

		}

		return rawMorphTargets;

	}
```
</details>

##### `parseScene(deformers: any, geometryMap: any, materialMap: any): void`

<details><summary>Code</summary>

```ts
parseScene( deformers, geometryMap, materialMap ) {

		sceneGraph = new Group();

		const modelMap = this.parseModels( deformers.skeletons, geometryMap, materialMap );

		const modelNodes = fbxTree.Objects.Model;

		const scope = this;
		modelMap.forEach( function ( model ) {

			const modelNode = modelNodes[ model.ID ];
			scope.setLookAtProperties( model, modelNode );

			const parentConnections = connections.get( model.ID ).parents;

			parentConnections.forEach( function ( connection ) {

				const parent = modelMap.get( connection.ID );
				if ( parent !== undefined ) parent.add( model );

			} );

			if ( model.parent === null ) {

				sceneGraph.add( model );

			}


		} );

		this.bindSkeleton( deformers.skeletons, geometryMap, modelMap );

		this.addGlobalSceneSettings();

		sceneGraph.traverse( function ( node ) {

			if ( node.userData.transformData ) {

				if ( node.parent ) {

					node.userData.transformData.parentMatrix = node.parent.matrix;
					node.userData.transformData.parentMatrixWorld = node.parent.matrixWorld;

				}

				const transform = generateTransform( node.userData.transformData );

				node.applyMatrix4( transform );
				node.updateWorldMatrix();

			}

		} );

		const animations = new AnimationParser().parse();

		// if all the models where already combined in a single group, just return that
		if ( sceneGraph.children.length === 1 && sceneGraph.children[ 0 ].isGroup ) {

			sceneGraph.children[ 0 ].animations = animations;
			sceneGraph = sceneGraph.children[ 0 ];

		}

		sceneGraph.animations = animations;

	}
```
</details>

##### `parseModels(skeletons: any, geometryMap: any, materialMap: any): Map<any, any>`

<details><summary>Code</summary>

```ts
parseModels( skeletons, geometryMap, materialMap ) {

		const modelMap = new Map();
		const modelNodes = fbxTree.Objects.Model;

		for ( const nodeID in modelNodes ) {

			const id = parseInt( nodeID );
			const node = modelNodes[ nodeID ];
			const relationships = connections.get( id );

			let model = this.buildSkeleton( relationships, skeletons, id, node.attrName );

			if ( ! model ) {

				switch ( node.attrType ) {

					case 'Camera':
						model = this.createCamera( relationships );
						break;
					case 'Light':
						model = this.createLight( relationships );
						break;
					case 'Mesh':
						model = this.createMesh( relationships, geometryMap, materialMap );
						break;
					case 'NurbsCurve':
						model = this.createCurve( relationships, geometryMap );
						break;
					case 'LimbNode':
					case 'Root':
						model = new Bone();
						break;
					case 'Null':
					default:
						model = new Group();
						break;

				}

				model.name = node.attrName ? PropertyBinding.sanitizeNodeName( node.attrName ) : '';
				model.userData.originalName = node.attrName;

				model.ID = id;

			}

			this.getTransformData( model, node );
			modelMap.set( id, model );

		}

		return modelMap;

	}
```
</details>

##### `buildSkeleton(relationships: any, skeletons: any, id: any, name: any): any`

<details><summary>Code</summary>

```ts
buildSkeleton( relationships, skeletons, id, name ) {

		let bone = null;

		relationships.parents.forEach( function ( parent ) {

			for ( const ID in skeletons ) {

				const skeleton = skeletons[ ID ];

				skeleton.rawBones.forEach( function ( rawBone, i ) {

					if ( rawBone.ID === parent.ID ) {

						const subBone = bone;
						bone = new Bone();

						bone.matrixWorld.copy( rawBone.transformLink );

						// set name and id here - otherwise in cases where "subBone" is created it will not have a name / id

						bone.name = name ? PropertyBinding.sanitizeNodeName( name ) : '';
						bone.userData.originalName = name;
						bone.ID = id;

						skeleton.bones[ i ] = bone;

						// In cases where a bone is shared between multiple meshes
						// duplicate the bone here and add it as a child of the first bone
						if ( subBone !== null ) {

							bone.add( subBone );

						}

					}

				} );

			}

		} );

		return bone;

	}
```
</details>

##### `createCamera(relationships: any): any`

<details><summary>Code</summary>

```ts
createCamera( relationships ) {

		let model;
		let cameraAttribute;

		relationships.children.forEach( function ( child ) {

			const attr = fbxTree.Objects.NodeAttribute[ child.ID ];

			if ( attr !== undefined ) {

				cameraAttribute = attr;

			}

		} );

		if ( cameraAttribute === undefined ) {

			model = new Object3D();

		} else {

			let type = 0;
			if ( cameraAttribute.CameraProjectionType !== undefined && cameraAttribute.CameraProjectionType.value === 1 ) {

				type = 1;

			}

			let nearClippingPlane = 1;
			if ( cameraAttribute.NearPlane !== undefined ) {

				nearClippingPlane = cameraAttribute.NearPlane.value / 1000;

			}

			let farClippingPlane = 1000;
			if ( cameraAttribute.FarPlane !== undefined ) {

				farClippingPlane = cameraAttribute.FarPlane.value / 1000;

			}


			let width = window.innerWidth;
			let height = window.innerHeight;

			if ( cameraAttribute.AspectWidth !== undefined && cameraAttribute.AspectHeight !== undefined ) {

				width = cameraAttribute.AspectWidth.value;
				height = cameraAttribute.AspectHeight.value;

			}

			const aspect = width / height;

			let fov = 45;
			if ( cameraAttribute.FieldOfView !== undefined ) {

				fov = cameraAttribute.FieldOfView.value;

			}

			const focalLength = cameraAttribute.FocalLength ? cameraAttribute.FocalLength.value : null;

			switch ( type ) {

				case 0: // Perspective
					model = new PerspectiveCamera( fov, aspect, nearClippingPlane, farClippingPlane );
					if ( focalLength !== null ) model.setFocalLength( focalLength );
					break;

				case 1: // Orthographic
					console.warn( 'THREE.FBXLoader: Orthographic cameras not supported yet.' );
					model = new Object3D();
					break;

				default:
					console.warn( 'THREE.FBXLoader: Unknown camera type ' + type + '.' );
					model = new Object3D();
					break;

			}

		}

		return model;

	}
```
</details>

##### `createLight(relationships: any): any`

<details><summary>Code</summary>

```ts
createLight( relationships ) {

		let model;
		let lightAttribute;

		relationships.children.forEach( function ( child ) {

			const attr = fbxTree.Objects.NodeAttribute[ child.ID ];

			if ( attr !== undefined ) {

				lightAttribute = attr;

			}

		} );

		if ( lightAttribute === undefined ) {

			model = new Object3D();

		} else {

			let type;

			// LightType can be undefined for Point lights
			if ( lightAttribute.LightType === undefined ) {

				type = 0;

			} else {

				type = lightAttribute.LightType.value;

			}

			let color = 0xffffff;

			if ( lightAttribute.Color !== undefined ) {

				color = ColorManagement.colorSpaceToWorking( new Color().fromArray( lightAttribute.Color.value ), SRGBColorSpace );

			}

			let intensity = ( lightAttribute.Intensity === undefined ) ? 1 : lightAttribute.Intensity.value / 100;

			// light disabled
			if ( lightAttribute.CastLightOnObject !== undefined && lightAttribute.CastLightOnObject.value === 0 ) {

				intensity = 0;

			}

			let distance = 0;
			if ( lightAttribute.FarAttenuationEnd !== undefined ) {

				if ( lightAttribute.EnableFarAttenuation !== undefined && lightAttribute.EnableFarAttenuation.value === 0 ) {

					distance = 0;

				} else {

					distance = lightAttribute.FarAttenuationEnd.value;

				}

			}

			// TODO: could this be calculated linearly from FarAttenuationStart to FarAttenuationEnd?
			const decay = 1;

			switch ( type ) {

				case 0: // Point
					model = new PointLight( color, intensity, distance, decay );
					break;

				case 1: // Directional
					model = new DirectionalLight( color, intensity );
					break;

				case 2: // Spot
					let angle = Math.PI / 3;

					if ( lightAttribute.InnerAngle !== undefined ) {

						angle = MathUtils.degToRad( lightAttribute.InnerAngle.value );

					}

					let penumbra = 0;
					if ( lightAttribute.OuterAngle !== undefined ) {

						// TODO: this is not correct - FBX calculates outer and inner angle in degrees
						// with OuterAngle > InnerAngle && OuterAngle <= Math.PI
						// while three.js uses a penumbra between (0, 1) to attenuate the inner angle
						penumbra = MathUtils.degToRad( lightAttribute.OuterAngle.value );
						penumbra = Math.max( penumbra, 1 );

					}

					model = new SpotLight( color, intensity, distance, angle, penumbra, decay );
					break;

				default:
					console.warn( 'THREE.FBXLoader: Unknown light type ' + lightAttribute.LightType.value + ', defaulting to a PointLight.' );
					model = new PointLight( color, intensity );
					break;

			}

			if ( lightAttribute.CastShadows !== undefined && lightAttribute.CastShadows.value === 1 ) {

				model.castShadow = true;

			}

		}

		return model;

	}
```
</details>

##### `createMesh(relationships: any, geometryMap: any, materialMap: any): any`

<details><summary>Code</summary>

```ts
createMesh( relationships, geometryMap, materialMap ) {

		let model;
		let geometry = null;
		let material = null;
		const materials = [];

		// get geometry and materials(s) from connections
		relationships.children.forEach( function ( child ) {

			if ( geometryMap.has( child.ID ) ) {

				geometry = geometryMap.get( child.ID );

			}

			if ( materialMap.has( child.ID ) ) {

				materials.push( materialMap.get( child.ID ) );

			}

		} );

		if ( materials.length > 1 ) {

			material = materials;

		} else if ( materials.length > 0 ) {

			material = materials[ 0 ];

		} else {

			material = new MeshPhongMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0xcccccc
			} );
			materials.push( material );

		}

		if ( 'color' in geometry.attributes ) {

			materials.forEach( function ( material ) {

				material.vertexColors = true;

			} );

		}

		// Sanitization: If geometry has groups, then it must match the provided material array.
		// If not, we need to clean up the `group.materialIndex` properties inside the groups and point at a (new) default material.
		// This isn't well defined; Unity creates default material, while Blender implicitly uses the previous material in the list.
		if ( geometry.groups.length > 0 ) {

			let needsDefaultMaterial = false;

			for ( let i = 0, il = geometry.groups.length; i < il; i ++ ) {

				const group = geometry.groups[ i ];

				if ( group.materialIndex < 0 || group.materialIndex >= materials.length ) {

					group.materialIndex = materials.length;
					needsDefaultMaterial = true;

				}

			}

			if ( needsDefaultMaterial ) {

				const defaultMaterial = new MeshPhongMaterial();
				materials.push( defaultMaterial );

			}

		}

		if ( geometry.FBX_Deformer ) {

			model = new SkinnedMesh( geometry, material );
			model.normalizeSkinWeights();

		} else {

			model = new Mesh( geometry, material );

		}

		return model;

	}
```
</details>

##### `createCurve(relationships: any, geometryMap: any): any`

<details><summary>Code</summary>

```ts
createCurve( relationships, geometryMap ) {

		const geometry = relationships.children.reduce( function ( geo, child ) {

			if ( geometryMap.has( child.ID ) ) geo = geometryMap.get( child.ID );

			return geo;

		}, null );

		// FBX does not list materials for Nurbs lines, so we'll just put our own in here.
		const material = new LineBasicMaterial( {
			name: Loader.DEFAULT_MATERIAL_NAME,
			color: 0x3300ff,
			linewidth: 1
		} );
		return new Line( geometry, material );

	}
```
</details>

##### `getTransformData(model: any, modelNode: any): void`

<details><summary>Code</summary>

```ts
getTransformData( model, modelNode ) {

		const transformData = {};

		if ( 'InheritType' in modelNode ) transformData.inheritType = parseInt( modelNode.InheritType.value );

		if ( 'RotationOrder' in modelNode ) transformData.eulerOrder = getEulerOrder( modelNode.RotationOrder.value );
		else transformData.eulerOrder = getEulerOrder( 0 );

		if ( 'Lcl_Translation' in modelNode ) transformData.translation = modelNode.Lcl_Translation.value;

		if ( 'PreRotation' in modelNode ) transformData.preRotation = modelNode.PreRotation.value;
		if ( 'Lcl_Rotation' in modelNode ) transformData.rotation = modelNode.Lcl_Rotation.value;
		if ( 'PostRotation' in modelNode ) transformData.postRotation = modelNode.PostRotation.value;

		if ( 'Lcl_Scaling' in modelNode ) transformData.scale = modelNode.Lcl_Scaling.value;

		if ( 'ScalingOffset' in modelNode ) transformData.scalingOffset = modelNode.ScalingOffset.value;
		if ( 'ScalingPivot' in modelNode ) transformData.scalingPivot = modelNode.ScalingPivot.value;

		if ( 'RotationOffset' in modelNode ) transformData.rotationOffset = modelNode.RotationOffset.value;
		if ( 'RotationPivot' in modelNode ) transformData.rotationPivot = modelNode.RotationPivot.value;

		model.userData.transformData = transformData;

	}
```
</details>

##### `setLookAtProperties(model: any, modelNode: any): void`

<details><summary>Code</summary>

```ts
setLookAtProperties( model, modelNode ) {

		if ( 'LookAtProperty' in modelNode ) {

			const children = connections.get( model.ID ).children;

			children.forEach( function ( child ) {

				if ( child.relationship === 'LookAtProperty' ) {

					const lookAtTarget = fbxTree.Objects.Model[ child.ID ];

					if ( 'Lcl_Translation' in lookAtTarget ) {

						const pos = lookAtTarget.Lcl_Translation.value;

						// DirectionalLight, SpotLight
						if ( model.target !== undefined ) {

							model.target.position.fromArray( pos );
							sceneGraph.add( model.target );

						} else { // Cameras and other Object3Ds

							model.lookAt( new Vector3().fromArray( pos ) );

						}

					}

				}

			} );

		}

	}
```
</details>

##### `bindSkeleton(skeletons: any, geometryMap: any, modelMap: any): void`

<details><summary>Code</summary>

```ts
bindSkeleton( skeletons, geometryMap, modelMap ) {

		const bindMatrices = this.parsePoseNodes();

		for ( const ID in skeletons ) {

			const skeleton = skeletons[ ID ];

			const parents = connections.get( parseInt( skeleton.ID ) ).parents;

			parents.forEach( function ( parent ) {

				if ( geometryMap.has( parent.ID ) ) {

					const geoID = parent.ID;
					const geoRelationships = connections.get( geoID );

					geoRelationships.parents.forEach( function ( geoConnParent ) {

						if ( modelMap.has( geoConnParent.ID ) ) {

							const model = modelMap.get( geoConnParent.ID );

							model.bind( new Skeleton( skeleton.bones ), bindMatrices[ geoConnParent.ID ] );

						}

					} );

				}

			} );

		}

	}
```
</details>

##### `parsePoseNodes(): {}`

<details><summary>Code</summary>

```ts
parsePoseNodes() {

		const bindMatrices = {};

		if ( 'Pose' in fbxTree.Objects ) {

			const BindPoseNode = fbxTree.Objects.Pose;

			for ( const nodeID in BindPoseNode ) {

				if ( BindPoseNode[ nodeID ].attrType === 'BindPose' && BindPoseNode[ nodeID ].NbPoseNodes > 0 ) {

					const poseNodes = BindPoseNode[ nodeID ].PoseNode;

					if ( Array.isArray( poseNodes ) ) {

						poseNodes.forEach( function ( poseNode ) {

							bindMatrices[ poseNode.Node ] = new Matrix4().fromArray( poseNode.Matrix.a );

						} );

					} else {

						bindMatrices[ poseNodes.Node ] = new Matrix4().fromArray( poseNodes.Matrix.a );

					}

				}

			}

		}

		return bindMatrices;

	}
```
</details>

##### `addGlobalSceneSettings(): void`

<details><summary>Code</summary>

```ts
addGlobalSceneSettings() {

		if ( 'GlobalSettings' in fbxTree ) {

			if ( 'AmbientColor' in fbxTree.GlobalSettings ) {

				// Parse ambient color - if it's not set to black (default), create an ambient light

				const ambientColor = fbxTree.GlobalSettings.AmbientColor.value;
				const r = ambientColor[ 0 ];
				const g = ambientColor[ 1 ];
				const b = ambientColor[ 2 ];

				if ( r !== 0 || g !== 0 || b !== 0 ) {

					const color = new Color().setRGB( r, g, b, SRGBColorSpace );
					sceneGraph.add( new AmbientLight( color, 1 ) );

				}

			}

			if ( 'UnitScaleFactor' in fbxTree.GlobalSettings ) {

				sceneGraph.userData.unitScaleFactor = fbxTree.GlobalSettings.UnitScaleFactor.value;

			}

		}

	}
```
</details>

### `GeometryParser`

<details><summary>Class Code</summary>

```ts
class GeometryParser {

	constructor() {

		this.negativeMaterialIndices = false;

	}

	// Parse nodes in FBXTree.Objects.Geometry
	parse( deformers ) {

		const geometryMap = new Map();

		if ( 'Geometry' in fbxTree.Objects ) {

			const geoNodes = fbxTree.Objects.Geometry;

			for ( const nodeID in geoNodes ) {

				const relationships = connections.get( parseInt( nodeID ) );
				const geo = this.parseGeometry( relationships, geoNodes[ nodeID ], deformers );

				geometryMap.set( parseInt( nodeID ), geo );

			}

		}

		// report warnings

		if ( this.negativeMaterialIndices === true ) {

			console.warn( 'THREE.FBXLoader: The FBX file contains invalid (negative) material indices. The asset might not render as expected.' );

		}

		return geometryMap;

	}

	// Parse single node in FBXTree.Objects.Geometry
	parseGeometry( relationships, geoNode, deformers ) {

		switch ( geoNode.attrType ) {

			case 'Mesh':
				return this.parseMeshGeometry( relationships, geoNode, deformers );
				break;

			case 'NurbsCurve':
				return this.parseNurbsGeometry( geoNode );
				break;

		}

	}

	// Parse single node mesh geometry in FBXTree.Objects.Geometry
	parseMeshGeometry( relationships, geoNode, deformers ) {

		const skeletons = deformers.skeletons;
		const morphTargets = [];

		const modelNodes = relationships.parents.map( function ( parent ) {

			return fbxTree.Objects.Model[ parent.ID ];

		} );

		// don't create geometry if it is not associated with any models
		if ( modelNodes.length === 0 ) return;

		const skeleton = relationships.children.reduce( function ( skeleton, child ) {

			if ( skeletons[ child.ID ] !== undefined ) skeleton = skeletons[ child.ID ];

			return skeleton;

		}, null );

		relationships.children.forEach( function ( child ) {

			if ( deformers.morphTargets[ child.ID ] !== undefined ) {

				morphTargets.push( deformers.morphTargets[ child.ID ] );

			}

		} );

		// Assume one model and get the preRotation from that
		// if there is more than one model associated with the geometry this may cause problems
		const modelNode = modelNodes[ 0 ];

		const transformData = {};

		if ( 'RotationOrder' in modelNode ) transformData.eulerOrder = getEulerOrder( modelNode.RotationOrder.value );
		if ( 'InheritType' in modelNode ) transformData.inheritType = parseInt( modelNode.InheritType.value );

		if ( 'GeometricTranslation' in modelNode ) transformData.translation = modelNode.GeometricTranslation.value;
		if ( 'GeometricRotation' in modelNode ) transformData.rotation = modelNode.GeometricRotation.value;
		if ( 'GeometricScaling' in modelNode ) transformData.scale = modelNode.GeometricScaling.value;

		const transform = generateTransform( transformData );

		return this.genGeometry( geoNode, skeleton, morphTargets, transform );

	}

	// Generate a BufferGeometry from a node in FBXTree.Objects.Geometry
	genGeometry( geoNode, skeleton, morphTargets, preTransform ) {

		const geo = new BufferGeometry();
		if ( geoNode.attrName ) geo.name = geoNode.attrName;

		const geoInfo = this.parseGeoNode( geoNode, skeleton );
		const buffers = this.genBuffers( geoInfo );

		const positionAttribute = new Float32BufferAttribute( buffers.vertex, 3 );

		positionAttribute.applyMatrix4( preTransform );

		geo.setAttribute( 'position', positionAttribute );

		if ( buffers.colors.length > 0 ) {

			geo.setAttribute( 'color', new Float32BufferAttribute( buffers.colors, 3 ) );

		}

		if ( skeleton ) {

			geo.setAttribute( 'skinIndex', new Uint16BufferAttribute( buffers.weightsIndices, 4 ) );

			geo.setAttribute( 'skinWeight', new Float32BufferAttribute( buffers.vertexWeights, 4 ) );

			// used later to bind the skeleton to the model
			geo.FBX_Deformer = skeleton;

		}

		if ( buffers.normal.length > 0 ) {

			const normalMatrix = new Matrix3().getNormalMatrix( preTransform );

			const normalAttribute = new Float32BufferAttribute( buffers.normal, 3 );
			normalAttribute.applyNormalMatrix( normalMatrix );

			geo.setAttribute( 'normal', normalAttribute );

		}

		buffers.uvs.forEach( function ( uvBuffer, i ) {

			const name = i === 0 ? 'uv' : `uv${ i }`;

			geo.setAttribute( name, new Float32BufferAttribute( buffers.uvs[ i ], 2 ) );

		} );

		if ( geoInfo.material && geoInfo.material.mappingType !== 'AllSame' ) {

			// Convert the material indices of each vertex into rendering groups on the geometry.
			let prevMaterialIndex = buffers.materialIndex[ 0 ];
			let startIndex = 0;

			buffers.materialIndex.forEach( function ( currentIndex, i ) {

				if ( currentIndex !== prevMaterialIndex ) {

					geo.addGroup( startIndex, i - startIndex, prevMaterialIndex );

					prevMaterialIndex = currentIndex;
					startIndex = i;

				}

			} );

			// the loop above doesn't add the last group, do that here.
			if ( geo.groups.length > 0 ) {

				const lastGroup = geo.groups[ geo.groups.length - 1 ];
				const lastIndex = lastGroup.start + lastGroup.count;

				if ( lastIndex !== buffers.materialIndex.length ) {

					geo.addGroup( lastIndex, buffers.materialIndex.length - lastIndex, prevMaterialIndex );

				}

			}

			// case where there are multiple materials but the whole geometry is only
			// using one of them
			if ( geo.groups.length === 0 ) {

				geo.addGroup( 0, buffers.materialIndex.length, buffers.materialIndex[ 0 ] );

			}

		}

		this.addMorphTargets( geo, geoNode, morphTargets, preTransform );

		return geo;

	}

	parseGeoNode( geoNode, skeleton ) {

		const geoInfo = {};

		geoInfo.vertexPositions = ( geoNode.Vertices !== undefined ) ? geoNode.Vertices.a : [];
		geoInfo.vertexIndices = ( geoNode.PolygonVertexIndex !== undefined ) ? geoNode.PolygonVertexIndex.a : [];

		if ( geoNode.LayerElementColor && geoNode.LayerElementColor[ 0 ].Colors ) {

			geoInfo.color = this.parseVertexColors( geoNode.LayerElementColor[ 0 ] );

		}

		if ( geoNode.LayerElementMaterial ) {

			geoInfo.material = this.parseMaterialIndices( geoNode.LayerElementMaterial[ 0 ] );

		}

		if ( geoNode.LayerElementNormal ) {

			geoInfo.normal = this.parseNormals( geoNode.LayerElementNormal[ 0 ] );

		}

		if ( geoNode.LayerElementUV ) {

			geoInfo.uv = [];

			let i = 0;
			while ( geoNode.LayerElementUV[ i ] ) {

				if ( geoNode.LayerElementUV[ i ].UV ) {

					geoInfo.uv.push( this.parseUVs( geoNode.LayerElementUV[ i ] ) );

				}

				i ++;

			}

		}

		geoInfo.weightTable = {};

		if ( skeleton !== null ) {

			geoInfo.skeleton = skeleton;

			skeleton.rawBones.forEach( function ( rawBone, i ) {

				// loop over the bone's vertex indices and weights
				rawBone.indices.forEach( function ( index, j ) {

					if ( geoInfo.weightTable[ index ] === undefined ) geoInfo.weightTable[ index ] = [];

					geoInfo.weightTable[ index ].push( {

						id: i,
						weight: rawBone.weights[ j ],

					} );

				} );

			} );

		}

		return geoInfo;

	}

	genBuffers( geoInfo ) {

		const buffers = {
			vertex: [],
			normal: [],
			colors: [],
			uvs: [],
			materialIndex: [],
			vertexWeights: [],
			weightsIndices: [],
		};

		let polygonIndex = 0;
		let faceLength = 0;
		let displayedWeightsWarning = false;

		// these will hold data for a single face
		let facePositionIndexes = [];
		let faceNormals = [];
		let faceColors = [];
		let faceUVs = [];
		let faceWeights = [];
		let faceWeightIndices = [];

		const scope = this;
		geoInfo.vertexIndices.forEach( function ( vertexIndex, polygonVertexIndex ) {

			let materialIndex;
			let endOfFace = false;

			// Face index and vertex index arrays are combined in a single array
			// A cube with quad faces looks like this:
			// PolygonVertexIndex: *24 {
			//  a: 0, 1, 3, -3, 2, 3, 5, -5, 4, 5, 7, -7, 6, 7, 1, -1, 1, 7, 5, -4, 6, 0, 2, -5
			//  }
			// Negative numbers mark the end of a face - first face here is 0, 1, 3, -3
			// to find index of last vertex bit shift the index: ^ - 1
			if ( vertexIndex < 0 ) {

				vertexIndex = vertexIndex ^ - 1; // equivalent to ( x * -1 ) - 1
				endOfFace = true;

			}

			let weightIndices = [];
			let weights = [];

			facePositionIndexes.push( vertexIndex * 3, vertexIndex * 3 + 1, vertexIndex * 3 + 2 );

			if ( geoInfo.color ) {

				const data = getData( polygonVertexIndex, polygonIndex, vertexIndex, geoInfo.color );

				faceColors.push( data[ 0 ], data[ 1 ], data[ 2 ] );

			}

			if ( geoInfo.skeleton ) {

				if ( geoInfo.weightTable[ vertexIndex ] !== undefined ) {

					geoInfo.weightTable[ vertexIndex ].forEach( function ( wt ) {

						weights.push( wt.weight );
						weightIndices.push( wt.id );

					} );


				}

				if ( weights.length > 4 ) {

					if ( ! displayedWeightsWarning ) {

						console.warn( 'THREE.FBXLoader: Vertex has more than 4 skinning weights assigned to vertex. Deleting additional weights.' );
						displayedWeightsWarning = true;

					}

					const wIndex = [ 0, 0, 0, 0 ];
					const Weight = [ 0, 0, 0, 0 ];

					weights.forEach( function ( weight, weightIndex ) {

						let currentWeight = weight;
						let currentIndex = weightIndices[ weightIndex ];

						Weight.forEach( function ( comparedWeight, comparedWeightIndex, comparedWeightArray ) {

							if ( currentWeight > comparedWeight ) {

								comparedWeightArray[ comparedWeightIndex ] = currentWeight;
								currentWeight = comparedWeight;

								const tmp = wIndex[ comparedWeightIndex ];
								wIndex[ comparedWeightIndex ] = currentIndex;
								currentIndex = tmp;

							}

						} );

					} );

					weightIndices = wIndex;
					weights = Weight;

				}

				// if the weight array is shorter than 4 pad with 0s
				while ( weights.length < 4 ) {

					weights.push( 0 );
					weightIndices.push( 0 );

				}

				for ( let i = 0; i < 4; ++ i ) {

					faceWeights.push( weights[ i ] );
					faceWeightIndices.push( weightIndices[ i ] );

				}

			}

			if ( geoInfo.normal ) {

				const data = getData( polygonVertexIndex, polygonIndex, vertexIndex, geoInfo.normal );

				faceNormals.push( data[ 0 ], data[ 1 ], data[ 2 ] );

			}

			if ( geoInfo.material && geoInfo.material.mappingType !== 'AllSame' ) {

				materialIndex = getData( polygonVertexIndex, polygonIndex, vertexIndex, geoInfo.material )[ 0 ];

				if ( materialIndex < 0 ) {

					scope.negativeMaterialIndices = true;
					materialIndex = 0; // fallback

				}

			}

			if ( geoInfo.uv ) {

				geoInfo.uv.forEach( function ( uv, i ) {

					const data = getData( polygonVertexIndex, polygonIndex, vertexIndex, uv );

					if ( faceUVs[ i ] === undefined ) {

						faceUVs[ i ] = [];

					}

					faceUVs[ i ].push( data[ 0 ] );
					faceUVs[ i ].push( data[ 1 ] );

				} );

			}

			faceLength ++;

			if ( endOfFace ) {

				scope.genFace( buffers, geoInfo, facePositionIndexes, materialIndex, faceNormals, faceColors, faceUVs, faceWeights, faceWeightIndices, faceLength );

				polygonIndex ++;
				faceLength = 0;

				// reset arrays for the next face
				facePositionIndexes = [];
				faceNormals = [];
				faceColors = [];
				faceUVs = [];
				faceWeights = [];
				faceWeightIndices = [];

			}

		} );

		return buffers;

	}

	// See https://www.khronos.org/opengl/wiki/Calculating_a_Surface_Normal
	getNormalNewell( vertices ) {

		const normal = new Vector3( 0.0, 0.0, 0.0 );

		for ( let i = 0; i < vertices.length; i ++ ) {

			const current = vertices[ i ];
			const next = vertices[ ( i + 1 ) % vertices.length ];

			normal.x += ( current.y - next.y ) * ( current.z + next.z );
			normal.y += ( current.z - next.z ) * ( current.x + next.x );
			normal.z += ( current.x - next.x ) * ( current.y + next.y );

		}

		normal.normalize();

		return normal;

	}

	getNormalTangentAndBitangent( vertices ) {

		const normalVector = this.getNormalNewell( vertices );
		// Avoid up being equal or almost equal to normalVector
		const up = Math.abs( normalVector.z ) > 0.5 ? new Vector3( 0.0, 1.0, 0.0 ) : new Vector3( 0.0, 0.0, 1.0 );
		const tangent = up.cross( normalVector ).normalize();
		const bitangent = normalVector.clone().cross( tangent ).normalize();

		return {
			normal: normalVector,
			tangent: tangent,
			bitangent: bitangent
		};

	}

	flattenVertex( vertex, normalTangent, normalBitangent ) {

		return new Vector2(
			vertex.dot( normalTangent ),
			vertex.dot( normalBitangent )
		);

	}

	// Generate data for a single face in a geometry. If the face is a quad then split it into 2 tris
	genFace( buffers, geoInfo, facePositionIndexes, materialIndex, faceNormals, faceColors, faceUVs, faceWeights, faceWeightIndices, faceLength ) {

		let triangles;

		if ( faceLength > 3 ) {

			// Triangulate n-gon using earcut

			const vertices = [];
			// in morphing scenario vertexPositions represent morphPositions
			// while baseVertexPositions represent the original geometry's positions
			const positions = geoInfo.baseVertexPositions || geoInfo.vertexPositions;
			for ( let i = 0; i < facePositionIndexes.length; i += 3 ) {

				vertices.push(
					new Vector3(
						positions[ facePositionIndexes[ i ] ],
						positions[ facePositionIndexes[ i + 1 ] ],
						positions[ facePositionIndexes[ i + 2 ] ]
					)
				);

			}

			const { tangent, bitangent } = this.getNormalTangentAndBitangent( vertices );
			const triangulationInput = [];

			for ( const vertex of vertices ) {

				triangulationInput.push( this.flattenVertex( vertex, tangent, bitangent ) );

			}

			// When vertices is an array of [0,0,0] elements (which is the case for vertices not participating in morph)
			// the triangulationInput will be an array of [0,0] elements
			// resulting in an array of 0 triangles being returned from ShapeUtils.triangulateShape
			// leading to not pushing into buffers.vertex the redundant vertices (the vertices that are not morphed).
			// That's why, in order to support morphing scenario, "positions" is looking first for baseVertexPositions,
			// so that we don't end up with an array of 0 triangles for the faces not participating in morph.
			triangles = ShapeUtils.triangulateShape( triangulationInput, [] );

		} else {

			// Regular triangle, skip earcut triangulation step
			triangles = [[ 0, 1, 2 ]];

		}

		for ( const [ i0, i1, i2 ] of triangles ) {

			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i0 * 3 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i0 * 3 + 1 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i0 * 3 + 2 ] ] );

			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i1 * 3 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i1 * 3 + 1 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i1 * 3 + 2 ] ] );

			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i2 * 3 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i2 * 3 + 1 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i2 * 3 + 2 ] ] );

			if ( geoInfo.skeleton ) {

				buffers.vertexWeights.push( faceWeights[ i0 * 4 ] );
				buffers.vertexWeights.push( faceWeights[ i0 * 4 + 1 ] );
				buffers.vertexWeights.push( faceWeights[ i0 * 4 + 2 ] );
				buffers.vertexWeights.push( faceWeights[ i0 * 4 + 3 ] );

				buffers.vertexWeights.push( faceWeights[ i1 * 4 ] );
				buffers.vertexWeights.push( faceWeights[ i1 * 4 + 1 ] );
				buffers.vertexWeights.push( faceWeights[ i1 * 4 + 2 ] );
				buffers.vertexWeights.push( faceWeights[ i1 * 4 + 3 ] );

				buffers.vertexWeights.push( faceWeights[ i2 * 4 ] );
				buffers.vertexWeights.push( faceWeights[ i2 * 4 + 1 ] );
				buffers.vertexWeights.push( faceWeights[ i2 * 4 + 2 ] );
				buffers.vertexWeights.push( faceWeights[ i2 * 4 + 3 ] );

				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 + 1 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 + 2 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 + 3 ] );

				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 + 1 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 + 2 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 + 3 ] );

				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 + 1 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 + 2 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 + 3 ] );

			}

			if ( geoInfo.color ) {

				buffers.colors.push( faceColors[ i0 * 3 ] );
				buffers.colors.push( faceColors[ i0 * 3 + 1 ] );
				buffers.colors.push( faceColors[ i0 * 3 + 2 ] );

				buffers.colors.push( faceColors[ i1 * 3 ] );
				buffers.colors.push( faceColors[ i1 * 3 + 1 ] );
				buffers.colors.push( faceColors[ i1 * 3 + 2 ] );

				buffers.colors.push( faceColors[ i2 * 3 ] );
				buffers.colors.push( faceColors[ i2 * 3 + 1 ] );
				buffers.colors.push( faceColors[ i2 * 3 + 2 ] );

			}

			if ( geoInfo.material && geoInfo.material.mappingType !== 'AllSame' ) {

				buffers.materialIndex.push( materialIndex );
				buffers.materialIndex.push( materialIndex );
				buffers.materialIndex.push( materialIndex );

			}

			if ( geoInfo.normal ) {

				buffers.normal.push( faceNormals[ i0 * 3 ] );
				buffers.normal.push( faceNormals[ i0 * 3 + 1 ] );
				buffers.normal.push( faceNormals[ i0 * 3 + 2 ] );

				buffers.normal.push( faceNormals[ i1 * 3 ] );
				buffers.normal.push( faceNormals[ i1 * 3 + 1 ] );
				buffers.normal.push( faceNormals[ i1 * 3 + 2 ] );

				buffers.normal.push( faceNormals[ i2 * 3 ] );
				buffers.normal.push( faceNormals[ i2 * 3 + 1 ] );
				buffers.normal.push( faceNormals[ i2 * 3 + 2 ] );

			}

			if ( geoInfo.uv ) {

				geoInfo.uv.forEach( function ( uv, j ) {

					if ( buffers.uvs[ j ] === undefined ) buffers.uvs[ j ] = [];

					buffers.uvs[ j ].push( faceUVs[ j ][ i0 * 2 ] );
					buffers.uvs[ j ].push( faceUVs[ j ][ i0 * 2 + 1 ] );

					buffers.uvs[ j ].push( faceUVs[ j ][ i1 * 2 ] );
					buffers.uvs[ j ].push( faceUVs[ j ][ i1 * 2 + 1 ] );

					buffers.uvs[ j ].push( faceUVs[ j ][ i2 * 2 ] );
					buffers.uvs[ j ].push( faceUVs[ j ][ i2 * 2 + 1 ] );

				} );

			}

		}

	}

	addMorphTargets( parentGeo, parentGeoNode, morphTargets, preTransform ) {

		if ( morphTargets.length === 0 ) return;

		parentGeo.morphTargetsRelative = true;

		parentGeo.morphAttributes.position = [];
		// parentGeo.morphAttributes.normal = []; // not implemented

		const scope = this;
		morphTargets.forEach( function ( morphTarget ) {

			morphTarget.rawTargets.forEach( function ( rawTarget ) {

				const morphGeoNode = fbxTree.Objects.Geometry[ rawTarget.geoID ];

				if ( morphGeoNode !== undefined ) {

					scope.genMorphGeometry( parentGeo, parentGeoNode, morphGeoNode, preTransform, rawTarget.name );

				}

			} );

		} );

	}

	// a morph geometry node is similar to a standard  node, and the node is also contained
	// in FBXTree.Objects.Geometry, however it can only have attributes for position, normal
	// and a special attribute Index defining which vertices of the original geometry are affected
	// Normal and position attributes only have data for the vertices that are affected by the morph
	genMorphGeometry( parentGeo, parentGeoNode, morphGeoNode, preTransform, name ) {

		const basePositions = parentGeoNode.Vertices !== undefined ? parentGeoNode.Vertices.a : [];
		const baseIndices = parentGeoNode.PolygonVertexIndex !== undefined ? parentGeoNode.PolygonVertexIndex.a : [];

		const morphPositionsSparse = morphGeoNode.Vertices !== undefined ? morphGeoNode.Vertices.a : [];
		const morphIndices = morphGeoNode.Indexes !== undefined ? morphGeoNode.Indexes.a : [];

		const length = parentGeo.attributes.position.count * 3;
		const morphPositions = new Float32Array( length );

		for ( let i = 0; i < morphIndices.length; i ++ ) {

			const morphIndex = morphIndices[ i ] * 3;

			morphPositions[ morphIndex ] = morphPositionsSparse[ i * 3 ];
			morphPositions[ morphIndex + 1 ] = morphPositionsSparse[ i * 3 + 1 ];
			morphPositions[ morphIndex + 2 ] = morphPositionsSparse[ i * 3 + 2 ];

		}

		// TODO: add morph normal support
		const morphGeoInfo = {
			vertexIndices: baseIndices,
			vertexPositions: morphPositions,
			baseVertexPositions: basePositions
		};

		const morphBuffers = this.genBuffers( morphGeoInfo );

		const positionAttribute = new Float32BufferAttribute( morphBuffers.vertex, 3 );
		positionAttribute.name = name || morphGeoNode.attrName;

		positionAttribute.applyMatrix4( preTransform );

		parentGeo.morphAttributes.position.push( positionAttribute );

	}

	// Parse normal from FBXTree.Objects.Geometry.LayerElementNormal if it exists
	parseNormals( NormalNode ) {

		const mappingType = NormalNode.MappingInformationType;
		const referenceType = NormalNode.ReferenceInformationType;
		const buffer = NormalNode.Normals.a;
		let indexBuffer = [];
		if ( referenceType === 'IndexToDirect' ) {

			if ( 'NormalIndex' in NormalNode ) {

				indexBuffer = NormalNode.NormalIndex.a;

			} else if ( 'NormalsIndex' in NormalNode ) {

				indexBuffer = NormalNode.NormalsIndex.a;

			}

		}

		return {
			dataSize: 3,
			buffer: buffer,
			indices: indexBuffer,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}

	// Parse UVs from FBXTree.Objects.Geometry.LayerElementUV if it exists
	parseUVs( UVNode ) {

		const mappingType = UVNode.MappingInformationType;
		const referenceType = UVNode.ReferenceInformationType;
		const buffer = UVNode.UV.a;
		let indexBuffer = [];
		if ( referenceType === 'IndexToDirect' ) {

			indexBuffer = UVNode.UVIndex.a;

		}

		return {
			dataSize: 2,
			buffer: buffer,
			indices: indexBuffer,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}

	// Parse Vertex Colors from FBXTree.Objects.Geometry.LayerElementColor if it exists
	parseVertexColors( ColorNode ) {

		const mappingType = ColorNode.MappingInformationType;
		const referenceType = ColorNode.ReferenceInformationType;
		const buffer = ColorNode.Colors.a;
		let indexBuffer = [];
		if ( referenceType === 'IndexToDirect' ) {

			indexBuffer = ColorNode.ColorIndex.a;

		}

		for ( let i = 0, c = new Color(); i < buffer.length; i += 4 ) {

			c.fromArray( buffer, i );
			ColorManagement.colorSpaceToWorking( c, SRGBColorSpace );
			c.toArray( buffer, i );

		}

		return {
			dataSize: 4,
			buffer: buffer,
			indices: indexBuffer,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}

	// Parse mapping and material data in FBXTree.Objects.Geometry.LayerElementMaterial if it exists
	parseMaterialIndices( MaterialNode ) {

		const mappingType = MaterialNode.MappingInformationType;
		const referenceType = MaterialNode.ReferenceInformationType;

		if ( mappingType === 'NoMappingInformation' ) {

			return {
				dataSize: 1,
				buffer: [ 0 ],
				indices: [ 0 ],
				mappingType: 'AllSame',
				referenceType: referenceType
			};

		}

		const materialIndexBuffer = MaterialNode.Materials.a;

		// Since materials are stored as indices, there's a bit of a mismatch between FBX and what
		// we expect.So we create an intermediate buffer that points to the index in the buffer,
		// for conforming with the other functions we've written for other data.
		const materialIndices = [];

		for ( let i = 0; i < materialIndexBuffer.length; ++ i ) {

			materialIndices.push( i );

		}

		return {
			dataSize: 1,
			buffer: materialIndexBuffer,
			indices: materialIndices,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}

	// Generate a NurbGeometry from a node in FBXTree.Objects.Geometry
	parseNurbsGeometry( geoNode ) {

		const order = parseInt( geoNode.Order );

		if ( isNaN( order ) ) {

			console.error( 'THREE.FBXLoader: Invalid Order %s given for geometry ID: %s', geoNode.Order, geoNode.id );
			return new BufferGeometry();

		}

		const degree = order - 1;

		const knots = geoNode.KnotVector.a;
		const controlPoints = [];
		const pointsValues = geoNode.Points.a;

		for ( let i = 0, l = pointsValues.length; i < l; i += 4 ) {

			controlPoints.push( new Vector4().fromArray( pointsValues, i ) );

		}

		let startKnot, endKnot;

		if ( geoNode.Form === 'Closed' ) {

			controlPoints.push( controlPoints[ 0 ] );

		} else if ( geoNode.Form === 'Periodic' ) {

			startKnot = degree;
			endKnot = knots.length - 1 - startKnot;

			for ( let i = 0; i < degree; ++ i ) {

				controlPoints.push( controlPoints[ i ] );

			}

		}

		const curve = new NURBSCurve( degree, knots, controlPoints, startKnot, endKnot );
		const points = curve.getPoints( controlPoints.length * 12 );

		return new BufferGeometry().setFromPoints( points );

	}

}
```
</details>

#### Methods

##### `parse(deformers: any): Map<any, any>`

<details><summary>Code</summary>

```ts
parse( deformers ) {

		const geometryMap = new Map();

		if ( 'Geometry' in fbxTree.Objects ) {

			const geoNodes = fbxTree.Objects.Geometry;

			for ( const nodeID in geoNodes ) {

				const relationships = connections.get( parseInt( nodeID ) );
				const geo = this.parseGeometry( relationships, geoNodes[ nodeID ], deformers );

				geometryMap.set( parseInt( nodeID ), geo );

			}

		}

		// report warnings

		if ( this.negativeMaterialIndices === true ) {

			console.warn( 'THREE.FBXLoader: The FBX file contains invalid (negative) material indices. The asset might not render as expected.' );

		}

		return geometryMap;

	}
```
</details>

##### `parseGeometry(relationships: any, geoNode: any, deformers: any): any`

<details><summary>Code</summary>

```ts
parseGeometry( relationships, geoNode, deformers ) {

		switch ( geoNode.attrType ) {

			case 'Mesh':
				return this.parseMeshGeometry( relationships, geoNode, deformers );
				break;

			case 'NurbsCurve':
				return this.parseNurbsGeometry( geoNode );
				break;

		}

	}
```
</details>

##### `parseMeshGeometry(relationships: any, geoNode: any, deformers: any): any`

<details><summary>Code</summary>

```ts
parseMeshGeometry( relationships, geoNode, deformers ) {

		const skeletons = deformers.skeletons;
		const morphTargets = [];

		const modelNodes = relationships.parents.map( function ( parent ) {

			return fbxTree.Objects.Model[ parent.ID ];

		} );

		// don't create geometry if it is not associated with any models
		if ( modelNodes.length === 0 ) return;

		const skeleton = relationships.children.reduce( function ( skeleton, child ) {

			if ( skeletons[ child.ID ] !== undefined ) skeleton = skeletons[ child.ID ];

			return skeleton;

		}, null );

		relationships.children.forEach( function ( child ) {

			if ( deformers.morphTargets[ child.ID ] !== undefined ) {

				morphTargets.push( deformers.morphTargets[ child.ID ] );

			}

		} );

		// Assume one model and get the preRotation from that
		// if there is more than one model associated with the geometry this may cause problems
		const modelNode = modelNodes[ 0 ];

		const transformData = {};

		if ( 'RotationOrder' in modelNode ) transformData.eulerOrder = getEulerOrder( modelNode.RotationOrder.value );
		if ( 'InheritType' in modelNode ) transformData.inheritType = parseInt( modelNode.InheritType.value );

		if ( 'GeometricTranslation' in modelNode ) transformData.translation = modelNode.GeometricTranslation.value;
		if ( 'GeometricRotation' in modelNode ) transformData.rotation = modelNode.GeometricRotation.value;
		if ( 'GeometricScaling' in modelNode ) transformData.scale = modelNode.GeometricScaling.value;

		const transform = generateTransform( transformData );

		return this.genGeometry( geoNode, skeleton, morphTargets, transform );

	}
```
</details>

##### `genGeometry(geoNode: any, skeleton: any, morphTargets: any, preTransform: any): any`

<details><summary>Code</summary>

```ts
genGeometry( geoNode, skeleton, morphTargets, preTransform ) {

		const geo = new BufferGeometry();
		if ( geoNode.attrName ) geo.name = geoNode.attrName;

		const geoInfo = this.parseGeoNode( geoNode, skeleton );
		const buffers = this.genBuffers( geoInfo );

		const positionAttribute = new Float32BufferAttribute( buffers.vertex, 3 );

		positionAttribute.applyMatrix4( preTransform );

		geo.setAttribute( 'position', positionAttribute );

		if ( buffers.colors.length > 0 ) {

			geo.setAttribute( 'color', new Float32BufferAttribute( buffers.colors, 3 ) );

		}

		if ( skeleton ) {

			geo.setAttribute( 'skinIndex', new Uint16BufferAttribute( buffers.weightsIndices, 4 ) );

			geo.setAttribute( 'skinWeight', new Float32BufferAttribute( buffers.vertexWeights, 4 ) );

			// used later to bind the skeleton to the model
			geo.FBX_Deformer = skeleton;

		}

		if ( buffers.normal.length > 0 ) {

			const normalMatrix = new Matrix3().getNormalMatrix( preTransform );

			const normalAttribute = new Float32BufferAttribute( buffers.normal, 3 );
			normalAttribute.applyNormalMatrix( normalMatrix );

			geo.setAttribute( 'normal', normalAttribute );

		}

		buffers.uvs.forEach( function ( uvBuffer, i ) {

			const name = i === 0 ? 'uv' : `uv${ i }`;

			geo.setAttribute( name, new Float32BufferAttribute( buffers.uvs[ i ], 2 ) );

		} );

		if ( geoInfo.material && geoInfo.material.mappingType !== 'AllSame' ) {

			// Convert the material indices of each vertex into rendering groups on the geometry.
			let prevMaterialIndex = buffers.materialIndex[ 0 ];
			let startIndex = 0;

			buffers.materialIndex.forEach( function ( currentIndex, i ) {

				if ( currentIndex !== prevMaterialIndex ) {

					geo.addGroup( startIndex, i - startIndex, prevMaterialIndex );

					prevMaterialIndex = currentIndex;
					startIndex = i;

				}

			} );

			// the loop above doesn't add the last group, do that here.
			if ( geo.groups.length > 0 ) {

				const lastGroup = geo.groups[ geo.groups.length - 1 ];
				const lastIndex = lastGroup.start + lastGroup.count;

				if ( lastIndex !== buffers.materialIndex.length ) {

					geo.addGroup( lastIndex, buffers.materialIndex.length - lastIndex, prevMaterialIndex );

				}

			}

			// case where there are multiple materials but the whole geometry is only
			// using one of them
			if ( geo.groups.length === 0 ) {

				geo.addGroup( 0, buffers.materialIndex.length, buffers.materialIndex[ 0 ] );

			}

		}

		this.addMorphTargets( geo, geoNode, morphTargets, preTransform );

		return geo;

	}
```
</details>

##### `parseGeoNode(geoNode: any, skeleton: any): { vertexPositions: any; vertexIndices: any; color: { dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }; material: { dataSize: number; buffer: any; indices: number[]; mappingType: any; referenceType: any; }; normal: { ...; }; uv: any[]; weightTable: {}; skeleton: any; }`

<details><summary>Code</summary>

```ts
parseGeoNode( geoNode, skeleton ) {

		const geoInfo = {};

		geoInfo.vertexPositions = ( geoNode.Vertices !== undefined ) ? geoNode.Vertices.a : [];
		geoInfo.vertexIndices = ( geoNode.PolygonVertexIndex !== undefined ) ? geoNode.PolygonVertexIndex.a : [];

		if ( geoNode.LayerElementColor && geoNode.LayerElementColor[ 0 ].Colors ) {

			geoInfo.color = this.parseVertexColors( geoNode.LayerElementColor[ 0 ] );

		}

		if ( geoNode.LayerElementMaterial ) {

			geoInfo.material = this.parseMaterialIndices( geoNode.LayerElementMaterial[ 0 ] );

		}

		if ( geoNode.LayerElementNormal ) {

			geoInfo.normal = this.parseNormals( geoNode.LayerElementNormal[ 0 ] );

		}

		if ( geoNode.LayerElementUV ) {

			geoInfo.uv = [];

			let i = 0;
			while ( geoNode.LayerElementUV[ i ] ) {

				if ( geoNode.LayerElementUV[ i ].UV ) {

					geoInfo.uv.push( this.parseUVs( geoNode.LayerElementUV[ i ] ) );

				}

				i ++;

			}

		}

		geoInfo.weightTable = {};

		if ( skeleton !== null ) {

			geoInfo.skeleton = skeleton;

			skeleton.rawBones.forEach( function ( rawBone, i ) {

				// loop over the bone's vertex indices and weights
				rawBone.indices.forEach( function ( index, j ) {

					if ( geoInfo.weightTable[ index ] === undefined ) geoInfo.weightTable[ index ] = [];

					geoInfo.weightTable[ index ].push( {

						id: i,
						weight: rawBone.weights[ j ],

					} );

				} );

			} );

		}

		return geoInfo;

	}
```
</details>

##### `genBuffers(geoInfo: any): { vertex: any[]; normal: any[]; colors: any[]; uvs: any[]; materialIndex: any[]; vertexWeights: any[]; weightsIndices: any[]; }`

<details><summary>Code</summary>

```ts
genBuffers( geoInfo ) {

		const buffers = {
			vertex: [],
			normal: [],
			colors: [],
			uvs: [],
			materialIndex: [],
			vertexWeights: [],
			weightsIndices: [],
		};

		let polygonIndex = 0;
		let faceLength = 0;
		let displayedWeightsWarning = false;

		// these will hold data for a single face
		let facePositionIndexes = [];
		let faceNormals = [];
		let faceColors = [];
		let faceUVs = [];
		let faceWeights = [];
		let faceWeightIndices = [];

		const scope = this;
		geoInfo.vertexIndices.forEach( function ( vertexIndex, polygonVertexIndex ) {

			let materialIndex;
			let endOfFace = false;

			// Face index and vertex index arrays are combined in a single array
			// A cube with quad faces looks like this:
			// PolygonVertexIndex: *24 {
			//  a: 0, 1, 3, -3, 2, 3, 5, -5, 4, 5, 7, -7, 6, 7, 1, -1, 1, 7, 5, -4, 6, 0, 2, -5
			//  }
			// Negative numbers mark the end of a face - first face here is 0, 1, 3, -3
			// to find index of last vertex bit shift the index: ^ - 1
			if ( vertexIndex < 0 ) {

				vertexIndex = vertexIndex ^ - 1; // equivalent to ( x * -1 ) - 1
				endOfFace = true;

			}

			let weightIndices = [];
			let weights = [];

			facePositionIndexes.push( vertexIndex * 3, vertexIndex * 3 + 1, vertexIndex * 3 + 2 );

			if ( geoInfo.color ) {

				const data = getData( polygonVertexIndex, polygonIndex, vertexIndex, geoInfo.color );

				faceColors.push( data[ 0 ], data[ 1 ], data[ 2 ] );

			}

			if ( geoInfo.skeleton ) {

				if ( geoInfo.weightTable[ vertexIndex ] !== undefined ) {

					geoInfo.weightTable[ vertexIndex ].forEach( function ( wt ) {

						weights.push( wt.weight );
						weightIndices.push( wt.id );

					} );


				}

				if ( weights.length > 4 ) {

					if ( ! displayedWeightsWarning ) {

						console.warn( 'THREE.FBXLoader: Vertex has more than 4 skinning weights assigned to vertex. Deleting additional weights.' );
						displayedWeightsWarning = true;

					}

					const wIndex = [ 0, 0, 0, 0 ];
					const Weight = [ 0, 0, 0, 0 ];

					weights.forEach( function ( weight, weightIndex ) {

						let currentWeight = weight;
						let currentIndex = weightIndices[ weightIndex ];

						Weight.forEach( function ( comparedWeight, comparedWeightIndex, comparedWeightArray ) {

							if ( currentWeight > comparedWeight ) {

								comparedWeightArray[ comparedWeightIndex ] = currentWeight;
								currentWeight = comparedWeight;

								const tmp = wIndex[ comparedWeightIndex ];
								wIndex[ comparedWeightIndex ] = currentIndex;
								currentIndex = tmp;

							}

						} );

					} );

					weightIndices = wIndex;
					weights = Weight;

				}

				// if the weight array is shorter than 4 pad with 0s
				while ( weights.length < 4 ) {

					weights.push( 0 );
					weightIndices.push( 0 );

				}

				for ( let i = 0; i < 4; ++ i ) {

					faceWeights.push( weights[ i ] );
					faceWeightIndices.push( weightIndices[ i ] );

				}

			}

			if ( geoInfo.normal ) {

				const data = getData( polygonVertexIndex, polygonIndex, vertexIndex, geoInfo.normal );

				faceNormals.push( data[ 0 ], data[ 1 ], data[ 2 ] );

			}

			if ( geoInfo.material && geoInfo.material.mappingType !== 'AllSame' ) {

				materialIndex = getData( polygonVertexIndex, polygonIndex, vertexIndex, geoInfo.material )[ 0 ];

				if ( materialIndex < 0 ) {

					scope.negativeMaterialIndices = true;
					materialIndex = 0; // fallback

				}

			}

			if ( geoInfo.uv ) {

				geoInfo.uv.forEach( function ( uv, i ) {

					const data = getData( polygonVertexIndex, polygonIndex, vertexIndex, uv );

					if ( faceUVs[ i ] === undefined ) {

						faceUVs[ i ] = [];

					}

					faceUVs[ i ].push( data[ 0 ] );
					faceUVs[ i ].push( data[ 1 ] );

				} );

			}

			faceLength ++;

			if ( endOfFace ) {

				scope.genFace( buffers, geoInfo, facePositionIndexes, materialIndex, faceNormals, faceColors, faceUVs, faceWeights, faceWeightIndices, faceLength );

				polygonIndex ++;
				faceLength = 0;

				// reset arrays for the next face
				facePositionIndexes = [];
				faceNormals = [];
				faceColors = [];
				faceUVs = [];
				faceWeights = [];
				faceWeightIndices = [];

			}

		} );

		return buffers;

	}
```
</details>

##### `getNormalNewell(vertices: any): any`

<details><summary>Code</summary>

```ts
getNormalNewell( vertices ) {

		const normal = new Vector3( 0.0, 0.0, 0.0 );

		for ( let i = 0; i < vertices.length; i ++ ) {

			const current = vertices[ i ];
			const next = vertices[ ( i + 1 ) % vertices.length ];

			normal.x += ( current.y - next.y ) * ( current.z + next.z );
			normal.y += ( current.z - next.z ) * ( current.x + next.x );
			normal.z += ( current.x - next.x ) * ( current.y + next.y );

		}

		normal.normalize();

		return normal;

	}
```
</details>

##### `getNormalTangentAndBitangent(vertices: any): { normal: any; tangent: any; bitangent: any; }`

<details><summary>Code</summary>

```ts
getNormalTangentAndBitangent( vertices ) {

		const normalVector = this.getNormalNewell( vertices );
		// Avoid up being equal or almost equal to normalVector
		const up = Math.abs( normalVector.z ) > 0.5 ? new Vector3( 0.0, 1.0, 0.0 ) : new Vector3( 0.0, 0.0, 1.0 );
		const tangent = up.cross( normalVector ).normalize();
		const bitangent = normalVector.clone().cross( tangent ).normalize();

		return {
			normal: normalVector,
			tangent: tangent,
			bitangent: bitangent
		};

	}
```
</details>

##### `flattenVertex(vertex: any, normalTangent: any, normalBitangent: any): any`

<details><summary>Code</summary>

```ts
flattenVertex( vertex, normalTangent, normalBitangent ) {

		return new Vector2(
			vertex.dot( normalTangent ),
			vertex.dot( normalBitangent )
		);

	}
```
</details>

##### `genFace(buffers: any, geoInfo: any, facePositionIndexes: any, materialIndex: any, faceNormals: any, faceColors: any, faceUVs: any, faceWeights: any, faceWeightIndices: any, faceLength: any): void`

<details><summary>Code</summary>

```ts
genFace( buffers, geoInfo, facePositionIndexes, materialIndex, faceNormals, faceColors, faceUVs, faceWeights, faceWeightIndices, faceLength ) {

		let triangles;

		if ( faceLength > 3 ) {

			// Triangulate n-gon using earcut

			const vertices = [];
			// in morphing scenario vertexPositions represent morphPositions
			// while baseVertexPositions represent the original geometry's positions
			const positions = geoInfo.baseVertexPositions || geoInfo.vertexPositions;
			for ( let i = 0; i < facePositionIndexes.length; i += 3 ) {

				vertices.push(
					new Vector3(
						positions[ facePositionIndexes[ i ] ],
						positions[ facePositionIndexes[ i + 1 ] ],
						positions[ facePositionIndexes[ i + 2 ] ]
					)
				);

			}

			const { tangent, bitangent } = this.getNormalTangentAndBitangent( vertices );
			const triangulationInput = [];

			for ( const vertex of vertices ) {

				triangulationInput.push( this.flattenVertex( vertex, tangent, bitangent ) );

			}

			// When vertices is an array of [0,0,0] elements (which is the case for vertices not participating in morph)
			// the triangulationInput will be an array of [0,0] elements
			// resulting in an array of 0 triangles being returned from ShapeUtils.triangulateShape
			// leading to not pushing into buffers.vertex the redundant vertices (the vertices that are not morphed).
			// That's why, in order to support morphing scenario, "positions" is looking first for baseVertexPositions,
			// so that we don't end up with an array of 0 triangles for the faces not participating in morph.
			triangles = ShapeUtils.triangulateShape( triangulationInput, [] );

		} else {

			// Regular triangle, skip earcut triangulation step
			triangles = [[ 0, 1, 2 ]];

		}

		for ( const [ i0, i1, i2 ] of triangles ) {

			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i0 * 3 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i0 * 3 + 1 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i0 * 3 + 2 ] ] );

			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i1 * 3 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i1 * 3 + 1 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i1 * 3 + 2 ] ] );

			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i2 * 3 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i2 * 3 + 1 ] ] );
			buffers.vertex.push( geoInfo.vertexPositions[ facePositionIndexes[ i2 * 3 + 2 ] ] );

			if ( geoInfo.skeleton ) {

				buffers.vertexWeights.push( faceWeights[ i0 * 4 ] );
				buffers.vertexWeights.push( faceWeights[ i0 * 4 + 1 ] );
				buffers.vertexWeights.push( faceWeights[ i0 * 4 + 2 ] );
				buffers.vertexWeights.push( faceWeights[ i0 * 4 + 3 ] );

				buffers.vertexWeights.push( faceWeights[ i1 * 4 ] );
				buffers.vertexWeights.push( faceWeights[ i1 * 4 + 1 ] );
				buffers.vertexWeights.push( faceWeights[ i1 * 4 + 2 ] );
				buffers.vertexWeights.push( faceWeights[ i1 * 4 + 3 ] );

				buffers.vertexWeights.push( faceWeights[ i2 * 4 ] );
				buffers.vertexWeights.push( faceWeights[ i2 * 4 + 1 ] );
				buffers.vertexWeights.push( faceWeights[ i2 * 4 + 2 ] );
				buffers.vertexWeights.push( faceWeights[ i2 * 4 + 3 ] );

				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 + 1 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 + 2 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i0 * 4 + 3 ] );

				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 + 1 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 + 2 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i1 * 4 + 3 ] );

				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 + 1 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 + 2 ] );
				buffers.weightsIndices.push( faceWeightIndices[ i2 * 4 + 3 ] );

			}

			if ( geoInfo.color ) {

				buffers.colors.push( faceColors[ i0 * 3 ] );
				buffers.colors.push( faceColors[ i0 * 3 + 1 ] );
				buffers.colors.push( faceColors[ i0 * 3 + 2 ] );

				buffers.colors.push( faceColors[ i1 * 3 ] );
				buffers.colors.push( faceColors[ i1 * 3 + 1 ] );
				buffers.colors.push( faceColors[ i1 * 3 + 2 ] );

				buffers.colors.push( faceColors[ i2 * 3 ] );
				buffers.colors.push( faceColors[ i2 * 3 + 1 ] );
				buffers.colors.push( faceColors[ i2 * 3 + 2 ] );

			}

			if ( geoInfo.material && geoInfo.material.mappingType !== 'AllSame' ) {

				buffers.materialIndex.push( materialIndex );
				buffers.materialIndex.push( materialIndex );
				buffers.materialIndex.push( materialIndex );

			}

			if ( geoInfo.normal ) {

				buffers.normal.push( faceNormals[ i0 * 3 ] );
				buffers.normal.push( faceNormals[ i0 * 3 + 1 ] );
				buffers.normal.push( faceNormals[ i0 * 3 + 2 ] );

				buffers.normal.push( faceNormals[ i1 * 3 ] );
				buffers.normal.push( faceNormals[ i1 * 3 + 1 ] );
				buffers.normal.push( faceNormals[ i1 * 3 + 2 ] );

				buffers.normal.push( faceNormals[ i2 * 3 ] );
				buffers.normal.push( faceNormals[ i2 * 3 + 1 ] );
				buffers.normal.push( faceNormals[ i2 * 3 + 2 ] );

			}

			if ( geoInfo.uv ) {

				geoInfo.uv.forEach( function ( uv, j ) {

					if ( buffers.uvs[ j ] === undefined ) buffers.uvs[ j ] = [];

					buffers.uvs[ j ].push( faceUVs[ j ][ i0 * 2 ] );
					buffers.uvs[ j ].push( faceUVs[ j ][ i0 * 2 + 1 ] );

					buffers.uvs[ j ].push( faceUVs[ j ][ i1 * 2 ] );
					buffers.uvs[ j ].push( faceUVs[ j ][ i1 * 2 + 1 ] );

					buffers.uvs[ j ].push( faceUVs[ j ][ i2 * 2 ] );
					buffers.uvs[ j ].push( faceUVs[ j ][ i2 * 2 + 1 ] );

				} );

			}

		}

	}
```
</details>

##### `addMorphTargets(parentGeo: any, parentGeoNode: any, morphTargets: any, preTransform: any): void`

<details><summary>Code</summary>

```ts
addMorphTargets( parentGeo, parentGeoNode, morphTargets, preTransform ) {

		if ( morphTargets.length === 0 ) return;

		parentGeo.morphTargetsRelative = true;

		parentGeo.morphAttributes.position = [];
		// parentGeo.morphAttributes.normal = []; // not implemented

		const scope = this;
		morphTargets.forEach( function ( morphTarget ) {

			morphTarget.rawTargets.forEach( function ( rawTarget ) {

				const morphGeoNode = fbxTree.Objects.Geometry[ rawTarget.geoID ];

				if ( morphGeoNode !== undefined ) {

					scope.genMorphGeometry( parentGeo, parentGeoNode, morphGeoNode, preTransform, rawTarget.name );

				}

			} );

		} );

	}
```
</details>

##### `genMorphGeometry(parentGeo: any, parentGeoNode: any, morphGeoNode: any, preTransform: any, name: any): void`

<details><summary>Code</summary>

```ts
genMorphGeometry( parentGeo, parentGeoNode, morphGeoNode, preTransform, name ) {

		const basePositions = parentGeoNode.Vertices !== undefined ? parentGeoNode.Vertices.a : [];
		const baseIndices = parentGeoNode.PolygonVertexIndex !== undefined ? parentGeoNode.PolygonVertexIndex.a : [];

		const morphPositionsSparse = morphGeoNode.Vertices !== undefined ? morphGeoNode.Vertices.a : [];
		const morphIndices = morphGeoNode.Indexes !== undefined ? morphGeoNode.Indexes.a : [];

		const length = parentGeo.attributes.position.count * 3;
		const morphPositions = new Float32Array( length );

		for ( let i = 0; i < morphIndices.length; i ++ ) {

			const morphIndex = morphIndices[ i ] * 3;

			morphPositions[ morphIndex ] = morphPositionsSparse[ i * 3 ];
			morphPositions[ morphIndex + 1 ] = morphPositionsSparse[ i * 3 + 1 ];
			morphPositions[ morphIndex + 2 ] = morphPositionsSparse[ i * 3 + 2 ];

		}

		// TODO: add morph normal support
		const morphGeoInfo = {
			vertexIndices: baseIndices,
			vertexPositions: morphPositions,
			baseVertexPositions: basePositions
		};

		const morphBuffers = this.genBuffers( morphGeoInfo );

		const positionAttribute = new Float32BufferAttribute( morphBuffers.vertex, 3 );
		positionAttribute.name = name || morphGeoNode.attrName;

		positionAttribute.applyMatrix4( preTransform );

		parentGeo.morphAttributes.position.push( positionAttribute );

	}
```
</details>

##### `parseNormals(NormalNode: any): { dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }`

<details><summary>Code</summary>

```ts
parseNormals( NormalNode ) {

		const mappingType = NormalNode.MappingInformationType;
		const referenceType = NormalNode.ReferenceInformationType;
		const buffer = NormalNode.Normals.a;
		let indexBuffer = [];
		if ( referenceType === 'IndexToDirect' ) {

			if ( 'NormalIndex' in NormalNode ) {

				indexBuffer = NormalNode.NormalIndex.a;

			} else if ( 'NormalsIndex' in NormalNode ) {

				indexBuffer = NormalNode.NormalsIndex.a;

			}

		}

		return {
			dataSize: 3,
			buffer: buffer,
			indices: indexBuffer,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}
```
</details>

##### `parseUVs(UVNode: any): { dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }`

<details><summary>Code</summary>

```ts
parseUVs( UVNode ) {

		const mappingType = UVNode.MappingInformationType;
		const referenceType = UVNode.ReferenceInformationType;
		const buffer = UVNode.UV.a;
		let indexBuffer = [];
		if ( referenceType === 'IndexToDirect' ) {

			indexBuffer = UVNode.UVIndex.a;

		}

		return {
			dataSize: 2,
			buffer: buffer,
			indices: indexBuffer,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}
```
</details>

##### `parseVertexColors(ColorNode: any): { dataSize: number; buffer: any; indices: any; mappingType: any; referenceType: any; }`

<details><summary>Code</summary>

```ts
parseVertexColors( ColorNode ) {

		const mappingType = ColorNode.MappingInformationType;
		const referenceType = ColorNode.ReferenceInformationType;
		const buffer = ColorNode.Colors.a;
		let indexBuffer = [];
		if ( referenceType === 'IndexToDirect' ) {

			indexBuffer = ColorNode.ColorIndex.a;

		}

		for ( let i = 0, c = new Color(); i < buffer.length; i += 4 ) {

			c.fromArray( buffer, i );
			ColorManagement.colorSpaceToWorking( c, SRGBColorSpace );
			c.toArray( buffer, i );

		}

		return {
			dataSize: 4,
			buffer: buffer,
			indices: indexBuffer,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}
```
</details>

##### `parseMaterialIndices(MaterialNode: any): { dataSize: number; buffer: any; indices: number[]; mappingType: any; referenceType: any; }`

<details><summary>Code</summary>

```ts
parseMaterialIndices( MaterialNode ) {

		const mappingType = MaterialNode.MappingInformationType;
		const referenceType = MaterialNode.ReferenceInformationType;

		if ( mappingType === 'NoMappingInformation' ) {

			return {
				dataSize: 1,
				buffer: [ 0 ],
				indices: [ 0 ],
				mappingType: 'AllSame',
				referenceType: referenceType
			};

		}

		const materialIndexBuffer = MaterialNode.Materials.a;

		// Since materials are stored as indices, there's a bit of a mismatch between FBX and what
		// we expect.So we create an intermediate buffer that points to the index in the buffer,
		// for conforming with the other functions we've written for other data.
		const materialIndices = [];

		for ( let i = 0; i < materialIndexBuffer.length; ++ i ) {

			materialIndices.push( i );

		}

		return {
			dataSize: 1,
			buffer: materialIndexBuffer,
			indices: materialIndices,
			mappingType: mappingType,
			referenceType: referenceType
		};

	}
```
</details>

##### `parseNurbsGeometry(geoNode: any): any`

<details><summary>Code</summary>

```ts
parseNurbsGeometry( geoNode ) {

		const order = parseInt( geoNode.Order );

		if ( isNaN( order ) ) {

			console.error( 'THREE.FBXLoader: Invalid Order %s given for geometry ID: %s', geoNode.Order, geoNode.id );
			return new BufferGeometry();

		}

		const degree = order - 1;

		const knots = geoNode.KnotVector.a;
		const controlPoints = [];
		const pointsValues = geoNode.Points.a;

		for ( let i = 0, l = pointsValues.length; i < l; i += 4 ) {

			controlPoints.push( new Vector4().fromArray( pointsValues, i ) );

		}

		let startKnot, endKnot;

		if ( geoNode.Form === 'Closed' ) {

			controlPoints.push( controlPoints[ 0 ] );

		} else if ( geoNode.Form === 'Periodic' ) {

			startKnot = degree;
			endKnot = knots.length - 1 - startKnot;

			for ( let i = 0; i < degree; ++ i ) {

				controlPoints.push( controlPoints[ i ] );

			}

		}

		const curve = new NURBSCurve( degree, knots, controlPoints, startKnot, endKnot );
		const points = curve.getPoints( controlPoints.length * 12 );

		return new BufferGeometry().setFromPoints( points );

	}
```
</details>

### `AnimationParser`

<details><summary>Class Code</summary>

```ts
class AnimationParser {

	// take raw animation clips and turn them into three.js animation clips
	parse() {

		const animationClips = [];

		const rawClips = this.parseClips();

		if ( rawClips !== undefined ) {

			for ( const key in rawClips ) {

				const rawClip = rawClips[ key ];

				const clip = this.addClip( rawClip );

				animationClips.push( clip );

			}

		}

		return animationClips;

	}

	parseClips() {

		// since the actual transformation data is stored in FBXTree.Objects.AnimationCurve,
		// if this is undefined we can safely assume there are no animations
		if ( fbxTree.Objects.AnimationCurve === undefined ) return undefined;

		const curveNodesMap = this.parseAnimationCurveNodes();

		this.parseAnimationCurves( curveNodesMap );

		const layersMap = this.parseAnimationLayers( curveNodesMap );
		const rawClips = this.parseAnimStacks( layersMap );

		return rawClips;

	}

	// parse nodes in FBXTree.Objects.AnimationCurveNode
	// each AnimationCurveNode holds data for an animation transform for a model (e.g. left arm rotation )
	// and is referenced by an AnimationLayer
	parseAnimationCurveNodes() {

		const rawCurveNodes = fbxTree.Objects.AnimationCurveNode;

		const curveNodesMap = new Map();

		for ( const nodeID in rawCurveNodes ) {

			const rawCurveNode = rawCurveNodes[ nodeID ];

			if ( rawCurveNode.attrName.match( /S|R|T|DeformPercent/ ) !== null ) {

				const curveNode = {

					id: rawCurveNode.id,
					attr: rawCurveNode.attrName,
					curves: {},

				};

				curveNodesMap.set( curveNode.id, curveNode );

			}

		}

		return curveNodesMap;

	}

	// parse nodes in FBXTree.Objects.AnimationCurve and connect them up to
	// previously parsed AnimationCurveNodes. Each AnimationCurve holds data for a single animated
	// axis ( e.g. times and values of x rotation)
	parseAnimationCurves( curveNodesMap ) {

		const rawCurves = fbxTree.Objects.AnimationCurve;

		// TODO: Many values are identical up to roundoff error, but won't be optimised
		// e.g. position times: [0, 0.4, 0. 8]
		// position values: [7.23538335023477e-7, 93.67518615722656, -0.9982695579528809, 7.23538335023477e-7, 93.67518615722656, -0.9982695579528809, 7.235384487103147e-7, 93.67520904541016, -0.9982695579528809]
		// clearly, this should be optimised to
		// times: [0], positions [7.23538335023477e-7, 93.67518615722656, -0.9982695579528809]
		// this shows up in nearly every FBX file, and generally time array is length > 100

		for ( const nodeID in rawCurves ) {

			const animationCurve = {

				id: rawCurves[ nodeID ].id,
				times: rawCurves[ nodeID ].KeyTime.a.map( convertFBXTimeToSeconds ),
				values: rawCurves[ nodeID ].KeyValueFloat.a,

			};

			const relationships = connections.get( animationCurve.id );

			if ( relationships !== undefined ) {

				const animationCurveID = relationships.parents[ 0 ].ID;
				const animationCurveRelationship = relationships.parents[ 0 ].relationship;

				if ( animationCurveRelationship.match( /X/ ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'x' ] = animationCurve;

				} else if ( animationCurveRelationship.match( /Y/ ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'y' ] = animationCurve;

				} else if ( animationCurveRelationship.match( /Z/ ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'z' ] = animationCurve;

				} else if ( animationCurveRelationship.match( /DeformPercent/ ) && curveNodesMap.has( animationCurveID ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'morph' ] = animationCurve;

				}

			}

		}

	}

	// parse nodes in FBXTree.Objects.AnimationLayer. Each layers holds references
	// to various AnimationCurveNodes and is referenced by an AnimationStack node
	// note: theoretically a stack can have multiple layers, however in practice there always seems to be one per stack
	parseAnimationLayers( curveNodesMap ) {

		const rawLayers = fbxTree.Objects.AnimationLayer;

		const layersMap = new Map();

		for ( const nodeID in rawLayers ) {

			const layerCurveNodes = [];

			const connection = connections.get( parseInt( nodeID ) );

			if ( connection !== undefined ) {

				// all the animationCurveNodes used in the layer
				const children = connection.children;

				children.forEach( function ( child, i ) {

					if ( curveNodesMap.has( child.ID ) ) {

						const curveNode = curveNodesMap.get( child.ID );

						// check that the curves are defined for at least one axis, otherwise ignore the curveNode
						if ( curveNode.curves.x !== undefined || curveNode.curves.y !== undefined || curveNode.curves.z !== undefined ) {

							if ( layerCurveNodes[ i ] === undefined ) {

								const modelID = connections.get( child.ID ).parents.filter( function ( parent ) {

									return parent.relationship !== undefined;

								} )[ 0 ].ID;

								if ( modelID !== undefined ) {

									const rawModel = fbxTree.Objects.Model[ modelID.toString() ];

									if ( rawModel === undefined ) {

										console.warn( 'THREE.FBXLoader: Encountered a unused curve.', child );
										return;

									}

									const node = {

										modelName: rawModel.attrName ? PropertyBinding.sanitizeNodeName( rawModel.attrName ) : '',
										ID: rawModel.id,
										initialPosition: [ 0, 0, 0 ],
										initialRotation: [ 0, 0, 0 ],
										initialScale: [ 1, 1, 1 ],

									};

									sceneGraph.traverse( function ( child ) {

										if ( child.ID === rawModel.id ) {

											node.transform = child.matrix;

											if ( child.userData.transformData ) node.eulerOrder = child.userData.transformData.eulerOrder;

										}

									} );

									if ( ! node.transform ) node.transform = new Matrix4();

									// if the animated model is pre rotated, we'll have to apply the pre rotations to every
									// animation value as well
									if ( 'PreRotation' in rawModel ) node.preRotation = rawModel.PreRotation.value;
									if ( 'PostRotation' in rawModel ) node.postRotation = rawModel.PostRotation.value;

									layerCurveNodes[ i ] = node;

								}

							}

							if ( layerCurveNodes[ i ] ) layerCurveNodes[ i ][ curveNode.attr ] = curveNode;

						} else if ( curveNode.curves.morph !== undefined ) {

							if ( layerCurveNodes[ i ] === undefined ) {

								const deformerID = connections.get( child.ID ).parents.filter( function ( parent ) {

									return parent.relationship !== undefined;

								} )[ 0 ].ID;

								const morpherID = connections.get( deformerID ).parents[ 0 ].ID;
								const geoID = connections.get( morpherID ).parents[ 0 ].ID;

								// assuming geometry is not used in more than one model
								const modelID = connections.get( geoID ).parents[ 0 ].ID;

								const rawModel = fbxTree.Objects.Model[ modelID ];

								const node = {

									modelName: rawModel.attrName ? PropertyBinding.sanitizeNodeName( rawModel.attrName ) : '',
									morphName: fbxTree.Objects.Deformer[ deformerID ].attrName,

								};

								layerCurveNodes[ i ] = node;

							}

							layerCurveNodes[ i ][ curveNode.attr ] = curveNode;

						}

					}

				} );

				layersMap.set( parseInt( nodeID ), layerCurveNodes );

			}

		}

		return layersMap;

	}

	// parse nodes in FBXTree.Objects.AnimationStack. These are the top level node in the animation
	// hierarchy. Each Stack node will be used to create an AnimationClip
	parseAnimStacks( layersMap ) {

		const rawStacks = fbxTree.Objects.AnimationStack;

		// connect the stacks (clips) up to the layers
		const rawClips = {};

		for ( const nodeID in rawStacks ) {

			const children = connections.get( parseInt( nodeID ) ).children;

			if ( children.length > 1 ) {

				// it seems like stacks will always be associated with a single layer. But just in case there are files
				// where there are multiple layers per stack, we'll display a warning
				console.warn( 'THREE.FBXLoader: Encountered an animation stack with multiple layers, this is currently not supported. Ignoring subsequent layers.' );

			}

			const layer = layersMap.get( children[ 0 ].ID );

			rawClips[ nodeID ] = {

				name: rawStacks[ nodeID ].attrName,
				layer: layer,

			};

		}

		return rawClips;

	}

	addClip( rawClip ) {

		let tracks = [];

		const scope = this;
		rawClip.layer.forEach( function ( rawTracks ) {

			tracks = tracks.concat( scope.generateTracks( rawTracks ) );

		} );

		return new AnimationClip( rawClip.name, - 1, tracks );

	}

	generateTracks( rawTracks ) {

		const tracks = [];

		let initialPosition = new Vector3();
		let initialScale = new Vector3();

		if ( rawTracks.transform ) rawTracks.transform.decompose( initialPosition, new Quaternion(), initialScale );

		initialPosition = initialPosition.toArray();
		initialScale = initialScale.toArray();

		if ( rawTracks.T !== undefined && Object.keys( rawTracks.T.curves ).length > 0 ) {

			const positionTrack = this.generateVectorTrack( rawTracks.modelName, rawTracks.T.curves, initialPosition, 'position' );
			if ( positionTrack !== undefined ) tracks.push( positionTrack );

		}

		if ( rawTracks.R !== undefined && Object.keys( rawTracks.R.curves ).length > 0 ) {

			const rotationTrack = this.generateRotationTrack( rawTracks.modelName, rawTracks.R.curves, rawTracks.preRotation, rawTracks.postRotation, rawTracks.eulerOrder );
			if ( rotationTrack !== undefined ) tracks.push( rotationTrack );

		}

		if ( rawTracks.S !== undefined && Object.keys( rawTracks.S.curves ).length > 0 ) {

			const scaleTrack = this.generateVectorTrack( rawTracks.modelName, rawTracks.S.curves, initialScale, 'scale' );
			if ( scaleTrack !== undefined ) tracks.push( scaleTrack );

		}

		if ( rawTracks.DeformPercent !== undefined ) {

			const morphTrack = this.generateMorphTrack( rawTracks );
			if ( morphTrack !== undefined ) tracks.push( morphTrack );

		}

		return tracks;

	}

	generateVectorTrack( modelName, curves, initialValue, type ) {

		const times = this.getTimesForAllAxes( curves );
		const values = this.getKeyframeTrackValues( times, curves, initialValue );

		return new VectorKeyframeTrack( modelName + '.' + type, times, values );

	}

	generateRotationTrack( modelName, curves, preRotation, postRotation, eulerOrder ) {

		let times;
		let values;

		if ( curves.x !== undefined && curves.y !== undefined && curves.z !== undefined ) {

			const result = this.interpolateRotations( curves.x, curves.y, curves.z, eulerOrder );

			times = result[ 0 ];
			values = result[ 1 ];

		}

		// For Maya models using "Joint Orient", Euler order only applies to rotation, not pre/post-rotations
		const defaultEulerOrder = getEulerOrder( 0 );

		if ( preRotation !== undefined ) {

			preRotation = preRotation.map( MathUtils.degToRad );
			preRotation.push( defaultEulerOrder );

			preRotation = new Euler().fromArray( preRotation );
			preRotation = new Quaternion().setFromEuler( preRotation );

		}

		if ( postRotation !== undefined ) {

			postRotation = postRotation.map( MathUtils.degToRad );
			postRotation.push( defaultEulerOrder );

			postRotation = new Euler().fromArray( postRotation );
			postRotation = new Quaternion().setFromEuler( postRotation ).invert();

		}

		const quaternion = new Quaternion();
		const euler = new Euler();

		const quaternionValues = [];

		if ( ! values || ! times ) return new QuaternionKeyframeTrack( modelName + '.quaternion', [ 0 ], [ 0 ] );

		for ( let i = 0; i < values.length; i += 3 ) {

			euler.set( values[ i ], values[ i + 1 ], values[ i + 2 ], eulerOrder );
			quaternion.setFromEuler( euler );

			if ( preRotation !== undefined ) quaternion.premultiply( preRotation );
			if ( postRotation !== undefined ) quaternion.multiply( postRotation );

			// Check unroll
			if ( i > 2 ) {

				const prevQuat = new Quaternion().fromArray(
					quaternionValues,
					( ( i - 3 ) / 3 ) * 4
				);

				if ( prevQuat.dot( quaternion ) < 0 ) {

					quaternion.set( - quaternion.x, - quaternion.y, - quaternion.z, - quaternion.w );

				}

			}

			quaternion.toArray( quaternionValues, ( i / 3 ) * 4 );

		}

		return new QuaternionKeyframeTrack( modelName + '.quaternion', times, quaternionValues );

	}

	generateMorphTrack( rawTracks ) {

		const curves = rawTracks.DeformPercent.curves.morph;
		const values = curves.values.map( function ( val ) {

			return val / 100;

		} );

		const morphNum = sceneGraph.getObjectByName( rawTracks.modelName ).morphTargetDictionary[ rawTracks.morphName ];

		return new NumberKeyframeTrack( rawTracks.modelName + '.morphTargetInfluences[' + morphNum + ']', curves.times, values );

	}

	// For all animated objects, times are defined separately for each axis
	// Here we'll combine the times into one sorted array without duplicates
	getTimesForAllAxes( curves ) {

		let times = [];

		// first join together the times for each axis, if defined
		if ( curves.x !== undefined ) times = times.concat( curves.x.times );
		if ( curves.y !== undefined ) times = times.concat( curves.y.times );
		if ( curves.z !== undefined ) times = times.concat( curves.z.times );

		// then sort them
		times = times.sort( function ( a, b ) {

			return a - b;

		} );

		// and remove duplicates
		if ( times.length > 1 ) {

			let targetIndex = 1;
			let lastValue = times[ 0 ];
			for ( let i = 1; i < times.length; i ++ ) {

				const currentValue = times[ i ];
				if ( currentValue !== lastValue ) {

					times[ targetIndex ] = currentValue;
					lastValue = currentValue;
					targetIndex ++;

				}

			}

			times = times.slice( 0, targetIndex );

		}

		return times;

	}

	getKeyframeTrackValues( times, curves, initialValue ) {

		const prevValue = initialValue;

		const values = [];

		let xIndex = - 1;
		let yIndex = - 1;
		let zIndex = - 1;

		times.forEach( function ( time ) {

			if ( curves.x ) xIndex = curves.x.times.indexOf( time );
			if ( curves.y ) yIndex = curves.y.times.indexOf( time );
			if ( curves.z ) zIndex = curves.z.times.indexOf( time );

			// if there is an x value defined for this frame, use that
			if ( xIndex !== - 1 ) {

				const xValue = curves.x.values[ xIndex ];
				values.push( xValue );
				prevValue[ 0 ] = xValue;

			} else {

				// otherwise use the x value from the previous frame
				values.push( prevValue[ 0 ] );

			}

			if ( yIndex !== - 1 ) {

				const yValue = curves.y.values[ yIndex ];
				values.push( yValue );
				prevValue[ 1 ] = yValue;

			} else {

				values.push( prevValue[ 1 ] );

			}

			if ( zIndex !== - 1 ) {

				const zValue = curves.z.values[ zIndex ];
				values.push( zValue );
				prevValue[ 2 ] = zValue;

			} else {

				values.push( prevValue[ 2 ] );

			}

		} );

		return values;

	}

	// Rotations are defined as Euler angles which can have values  of any size
	// These will be converted to quaternions which don't support values greater than
	// PI, so we'll interpolate large rotations
	interpolateRotations( curvex, curvey, curvez, eulerOrder ) {

		const times = [];
		const values = [];

		// Add first frame
		times.push( curvex.times[ 0 ] );
		values.push( MathUtils.degToRad( curvex.values[ 0 ] ) );
		values.push( MathUtils.degToRad( curvey.values[ 0 ] ) );
		values.push( MathUtils.degToRad( curvez.values[ 0 ] ) );

		for ( let i = 1; i < curvex.values.length; i ++ ) {

			const initialValue = [
				curvex.values[ i - 1 ],
				curvey.values[ i - 1 ],
				curvez.values[ i - 1 ],
			];

			if ( isNaN( initialValue[ 0 ] ) || isNaN( initialValue[ 1 ] ) || isNaN( initialValue[ 2 ] ) ) {

				continue;

			}

			const initialValueRad = initialValue.map( MathUtils.degToRad );

			const currentValue = [
				curvex.values[ i ],
				curvey.values[ i ],
				curvez.values[ i ],
			];

			if ( isNaN( currentValue[ 0 ] ) || isNaN( currentValue[ 1 ] ) || isNaN( currentValue[ 2 ] ) ) {

				continue;

			}

			const currentValueRad = currentValue.map( MathUtils.degToRad );

			const valuesSpan = [
				currentValue[ 0 ] - initialValue[ 0 ],
				currentValue[ 1 ] - initialValue[ 1 ],
				currentValue[ 2 ] - initialValue[ 2 ],
			];

			const absoluteSpan = [
				Math.abs( valuesSpan[ 0 ] ),
				Math.abs( valuesSpan[ 1 ] ),
				Math.abs( valuesSpan[ 2 ] ),
			];

			if ( absoluteSpan[ 0 ] >= 180 || absoluteSpan[ 1 ] >= 180 || absoluteSpan[ 2 ] >= 180 ) {

				const maxAbsSpan = Math.max( ...absoluteSpan );

				const numSubIntervals = maxAbsSpan / 180;

				const E1 = new Euler( ...initialValueRad, eulerOrder );
				const E2 = new Euler( ...currentValueRad, eulerOrder );

				const Q1 = new Quaternion().setFromEuler( E1 );
				const Q2 = new Quaternion().setFromEuler( E2 );

				// Check unroll
				if ( Q1.dot( Q2 ) ) {

					Q2.set( - Q2.x, - Q2.y, - Q2.z, - Q2.w );

				}

				// Interpolate
				const initialTime = curvex.times[ i - 1 ];
				const timeSpan = curvex.times[ i ] - initialTime;

				const Q = new Quaternion();
				const E = new Euler();
				for ( let t = 0; t < 1; t += 1 / numSubIntervals ) {

					Q.copy( Q1.clone().slerp( Q2.clone(), t ) );

					times.push( initialTime + t * timeSpan );
					E.setFromQuaternion( Q, eulerOrder );

					values.push( E.x );
					values.push( E.y );
					values.push( E.z );

				}

			} else {

				times.push( curvex.times[ i ] );
				values.push( MathUtils.degToRad( curvex.values[ i ] ) );
				values.push( MathUtils.degToRad( curvey.values[ i ] ) );
				values.push( MathUtils.degToRad( curvez.values[ i ] ) );

			}

		}

		return [ times, values ];

	}

}
```
</details>

#### Methods

##### `parse(): any[]`

<details><summary>Code</summary>

```ts
parse() {

		const animationClips = [];

		const rawClips = this.parseClips();

		if ( rawClips !== undefined ) {

			for ( const key in rawClips ) {

				const rawClip = rawClips[ key ];

				const clip = this.addClip( rawClip );

				animationClips.push( clip );

			}

		}

		return animationClips;

	}
```
</details>

##### `parseClips(): {}`

<details><summary>Code</summary>

```ts
parseClips() {

		// since the actual transformation data is stored in FBXTree.Objects.AnimationCurve,
		// if this is undefined we can safely assume there are no animations
		if ( fbxTree.Objects.AnimationCurve === undefined ) return undefined;

		const curveNodesMap = this.parseAnimationCurveNodes();

		this.parseAnimationCurves( curveNodesMap );

		const layersMap = this.parseAnimationLayers( curveNodesMap );
		const rawClips = this.parseAnimStacks( layersMap );

		return rawClips;

	}
```
</details>

##### `parseAnimationCurveNodes(): Map<any, any>`

<details><summary>Code</summary>

```ts
parseAnimationCurveNodes() {

		const rawCurveNodes = fbxTree.Objects.AnimationCurveNode;

		const curveNodesMap = new Map();

		for ( const nodeID in rawCurveNodes ) {

			const rawCurveNode = rawCurveNodes[ nodeID ];

			if ( rawCurveNode.attrName.match( /S|R|T|DeformPercent/ ) !== null ) {

				const curveNode = {

					id: rawCurveNode.id,
					attr: rawCurveNode.attrName,
					curves: {},

				};

				curveNodesMap.set( curveNode.id, curveNode );

			}

		}

		return curveNodesMap;

	}
```
</details>

##### `parseAnimationCurves(curveNodesMap: any): void`

<details><summary>Code</summary>

```ts
parseAnimationCurves( curveNodesMap ) {

		const rawCurves = fbxTree.Objects.AnimationCurve;

		// TODO: Many values are identical up to roundoff error, but won't be optimised
		// e.g. position times: [0, 0.4, 0. 8]
		// position values: [7.23538335023477e-7, 93.67518615722656, -0.9982695579528809, 7.23538335023477e-7, 93.67518615722656, -0.9982695579528809, 7.235384487103147e-7, 93.67520904541016, -0.9982695579528809]
		// clearly, this should be optimised to
		// times: [0], positions [7.23538335023477e-7, 93.67518615722656, -0.9982695579528809]
		// this shows up in nearly every FBX file, and generally time array is length > 100

		for ( const nodeID in rawCurves ) {

			const animationCurve = {

				id: rawCurves[ nodeID ].id,
				times: rawCurves[ nodeID ].KeyTime.a.map( convertFBXTimeToSeconds ),
				values: rawCurves[ nodeID ].KeyValueFloat.a,

			};

			const relationships = connections.get( animationCurve.id );

			if ( relationships !== undefined ) {

				const animationCurveID = relationships.parents[ 0 ].ID;
				const animationCurveRelationship = relationships.parents[ 0 ].relationship;

				if ( animationCurveRelationship.match( /X/ ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'x' ] = animationCurve;

				} else if ( animationCurveRelationship.match( /Y/ ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'y' ] = animationCurve;

				} else if ( animationCurveRelationship.match( /Z/ ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'z' ] = animationCurve;

				} else if ( animationCurveRelationship.match( /DeformPercent/ ) && curveNodesMap.has( animationCurveID ) ) {

					curveNodesMap.get( animationCurveID ).curves[ 'morph' ] = animationCurve;

				}

			}

		}

	}
```
</details>

##### `parseAnimationLayers(curveNodesMap: any): Map<any, any>`

<details><summary>Code</summary>

```ts
parseAnimationLayers( curveNodesMap ) {

		const rawLayers = fbxTree.Objects.AnimationLayer;

		const layersMap = new Map();

		for ( const nodeID in rawLayers ) {

			const layerCurveNodes = [];

			const connection = connections.get( parseInt( nodeID ) );

			if ( connection !== undefined ) {

				// all the animationCurveNodes used in the layer
				const children = connection.children;

				children.forEach( function ( child, i ) {

					if ( curveNodesMap.has( child.ID ) ) {

						const curveNode = curveNodesMap.get( child.ID );

						// check that the curves are defined for at least one axis, otherwise ignore the curveNode
						if ( curveNode.curves.x !== undefined || curveNode.curves.y !== undefined || curveNode.curves.z !== undefined ) {

							if ( layerCurveNodes[ i ] === undefined ) {

								const modelID = connections.get( child.ID ).parents.filter( function ( parent ) {

									return parent.relationship !== undefined;

								} )[ 0 ].ID;

								if ( modelID !== undefined ) {

									const rawModel = fbxTree.Objects.Model[ modelID.toString() ];

									if ( rawModel === undefined ) {

										console.warn( 'THREE.FBXLoader: Encountered a unused curve.', child );
										return;

									}

									const node = {

										modelName: rawModel.attrName ? PropertyBinding.sanitizeNodeName( rawModel.attrName ) : '',
										ID: rawModel.id,
										initialPosition: [ 0, 0, 0 ],
										initialRotation: [ 0, 0, 0 ],
										initialScale: [ 1, 1, 1 ],

									};

									sceneGraph.traverse( function ( child ) {

										if ( child.ID === rawModel.id ) {

											node.transform = child.matrix;

											if ( child.userData.transformData ) node.eulerOrder = child.userData.transformData.eulerOrder;

										}

									} );

									if ( ! node.transform ) node.transform = new Matrix4();

									// if the animated model is pre rotated, we'll have to apply the pre rotations to every
									// animation value as well
									if ( 'PreRotation' in rawModel ) node.preRotation = rawModel.PreRotation.value;
									if ( 'PostRotation' in rawModel ) node.postRotation = rawModel.PostRotation.value;

									layerCurveNodes[ i ] = node;

								}

							}

							if ( layerCurveNodes[ i ] ) layerCurveNodes[ i ][ curveNode.attr ] = curveNode;

						} else if ( curveNode.curves.morph !== undefined ) {

							if ( layerCurveNodes[ i ] === undefined ) {

								const deformerID = connections.get( child.ID ).parents.filter( function ( parent ) {

									return parent.relationship !== undefined;

								} )[ 0 ].ID;

								const morpherID = connections.get( deformerID ).parents[ 0 ].ID;
								const geoID = connections.get( morpherID ).parents[ 0 ].ID;

								// assuming geometry is not used in more than one model
								const modelID = connections.get( geoID ).parents[ 0 ].ID;

								const rawModel = fbxTree.Objects.Model[ modelID ];

								const node = {

									modelName: rawModel.attrName ? PropertyBinding.sanitizeNodeName( rawModel.attrName ) : '',
									morphName: fbxTree.Objects.Deformer[ deformerID ].attrName,

								};

								layerCurveNodes[ i ] = node;

							}

							layerCurveNodes[ i ][ curveNode.attr ] = curveNode;

						}

					}

				} );

				layersMap.set( parseInt( nodeID ), layerCurveNodes );

			}

		}

		return layersMap;

	}
```
</details>

##### `parseAnimStacks(layersMap: any): {}`

<details><summary>Code</summary>

```ts
parseAnimStacks( layersMap ) {

		const rawStacks = fbxTree.Objects.AnimationStack;

		// connect the stacks (clips) up to the layers
		const rawClips = {};

		for ( const nodeID in rawStacks ) {

			const children = connections.get( parseInt( nodeID ) ).children;

			if ( children.length > 1 ) {

				// it seems like stacks will always be associated with a single layer. But just in case there are files
				// where there are multiple layers per stack, we'll display a warning
				console.warn( 'THREE.FBXLoader: Encountered an animation stack with multiple layers, this is currently not supported. Ignoring subsequent layers.' );

			}

			const layer = layersMap.get( children[ 0 ].ID );

			rawClips[ nodeID ] = {

				name: rawStacks[ nodeID ].attrName,
				layer: layer,

			};

		}

		return rawClips;

	}
```
</details>

##### `addClip(rawClip: any): any`

<details><summary>Code</summary>

```ts
addClip( rawClip ) {

		let tracks = [];

		const scope = this;
		rawClip.layer.forEach( function ( rawTracks ) {

			tracks = tracks.concat( scope.generateTracks( rawTracks ) );

		} );

		return new AnimationClip( rawClip.name, - 1, tracks );

	}
```
</details>

##### `generateTracks(rawTracks: any): any[]`

<details><summary>Code</summary>

```ts
generateTracks( rawTracks ) {

		const tracks = [];

		let initialPosition = new Vector3();
		let initialScale = new Vector3();

		if ( rawTracks.transform ) rawTracks.transform.decompose( initialPosition, new Quaternion(), initialScale );

		initialPosition = initialPosition.toArray();
		initialScale = initialScale.toArray();

		if ( rawTracks.T !== undefined && Object.keys( rawTracks.T.curves ).length > 0 ) {

			const positionTrack = this.generateVectorTrack( rawTracks.modelName, rawTracks.T.curves, initialPosition, 'position' );
			if ( positionTrack !== undefined ) tracks.push( positionTrack );

		}

		if ( rawTracks.R !== undefined && Object.keys( rawTracks.R.curves ).length > 0 ) {

			const rotationTrack = this.generateRotationTrack( rawTracks.modelName, rawTracks.R.curves, rawTracks.preRotation, rawTracks.postRotation, rawTracks.eulerOrder );
			if ( rotationTrack !== undefined ) tracks.push( rotationTrack );

		}

		if ( rawTracks.S !== undefined && Object.keys( rawTracks.S.curves ).length > 0 ) {

			const scaleTrack = this.generateVectorTrack( rawTracks.modelName, rawTracks.S.curves, initialScale, 'scale' );
			if ( scaleTrack !== undefined ) tracks.push( scaleTrack );

		}

		if ( rawTracks.DeformPercent !== undefined ) {

			const morphTrack = this.generateMorphTrack( rawTracks );
			if ( morphTrack !== undefined ) tracks.push( morphTrack );

		}

		return tracks;

	}
```
</details>

##### `generateVectorTrack(modelName: any, curves: any, initialValue: any, type: any): any`

<details><summary>Code</summary>

```ts
generateVectorTrack( modelName, curves, initialValue, type ) {

		const times = this.getTimesForAllAxes( curves );
		const values = this.getKeyframeTrackValues( times, curves, initialValue );

		return new VectorKeyframeTrack( modelName + '.' + type, times, values );

	}
```
</details>

##### `generateRotationTrack(modelName: any, curves: any, preRotation: any, postRotation: any, eulerOrder: any): any`

<details><summary>Code</summary>

```ts
generateRotationTrack( modelName, curves, preRotation, postRotation, eulerOrder ) {

		let times;
		let values;

		if ( curves.x !== undefined && curves.y !== undefined && curves.z !== undefined ) {

			const result = this.interpolateRotations( curves.x, curves.y, curves.z, eulerOrder );

			times = result[ 0 ];
			values = result[ 1 ];

		}

		// For Maya models using "Joint Orient", Euler order only applies to rotation, not pre/post-rotations
		const defaultEulerOrder = getEulerOrder( 0 );

		if ( preRotation !== undefined ) {

			preRotation = preRotation.map( MathUtils.degToRad );
			preRotation.push( defaultEulerOrder );

			preRotation = new Euler().fromArray( preRotation );
			preRotation = new Quaternion().setFromEuler( preRotation );

		}

		if ( postRotation !== undefined ) {

			postRotation = postRotation.map( MathUtils.degToRad );
			postRotation.push( defaultEulerOrder );

			postRotation = new Euler().fromArray( postRotation );
			postRotation = new Quaternion().setFromEuler( postRotation ).invert();

		}

		const quaternion = new Quaternion();
		const euler = new Euler();

		const quaternionValues = [];

		if ( ! values || ! times ) return new QuaternionKeyframeTrack( modelName + '.quaternion', [ 0 ], [ 0 ] );

		for ( let i = 0; i < values.length; i += 3 ) {

			euler.set( values[ i ], values[ i + 1 ], values[ i + 2 ], eulerOrder );
			quaternion.setFromEuler( euler );

			if ( preRotation !== undefined ) quaternion.premultiply( preRotation );
			if ( postRotation !== undefined ) quaternion.multiply( postRotation );

			// Check unroll
			if ( i > 2 ) {

				const prevQuat = new Quaternion().fromArray(
					quaternionValues,
					( ( i - 3 ) / 3 ) * 4
				);

				if ( prevQuat.dot( quaternion ) < 0 ) {

					quaternion.set( - quaternion.x, - quaternion.y, - quaternion.z, - quaternion.w );

				}

			}

			quaternion.toArray( quaternionValues, ( i / 3 ) * 4 );

		}

		return new QuaternionKeyframeTrack( modelName + '.quaternion', times, quaternionValues );

	}
```
</details>

##### `generateMorphTrack(rawTracks: any): any`

<details><summary>Code</summary>

```ts
generateMorphTrack( rawTracks ) {

		const curves = rawTracks.DeformPercent.curves.morph;
		const values = curves.values.map( function ( val ) {

			return val / 100;

		} );

		const morphNum = sceneGraph.getObjectByName( rawTracks.modelName ).morphTargetDictionary[ rawTracks.morphName ];

		return new NumberKeyframeTrack( rawTracks.modelName + '.morphTargetInfluences[' + morphNum + ']', curves.times, values );

	}
```
</details>

##### `getTimesForAllAxes(curves: any): any[]`

<details><summary>Code</summary>

```ts
getTimesForAllAxes( curves ) {

		let times = [];

		// first join together the times for each axis, if defined
		if ( curves.x !== undefined ) times = times.concat( curves.x.times );
		if ( curves.y !== undefined ) times = times.concat( curves.y.times );
		if ( curves.z !== undefined ) times = times.concat( curves.z.times );

		// then sort them
		times = times.sort( function ( a, b ) {

			return a - b;

		} );

		// and remove duplicates
		if ( times.length > 1 ) {

			let targetIndex = 1;
			let lastValue = times[ 0 ];
			for ( let i = 1; i < times.length; i ++ ) {

				const currentValue = times[ i ];
				if ( currentValue !== lastValue ) {

					times[ targetIndex ] = currentValue;
					lastValue = currentValue;
					targetIndex ++;

				}

			}

			times = times.slice( 0, targetIndex );

		}

		return times;

	}
```
</details>

##### `getKeyframeTrackValues(times: any, curves: any, initialValue: any): any[]`

<details><summary>Code</summary>

```ts
getKeyframeTrackValues( times, curves, initialValue ) {

		const prevValue = initialValue;

		const values = [];

		let xIndex = - 1;
		let yIndex = - 1;
		let zIndex = - 1;

		times.forEach( function ( time ) {

			if ( curves.x ) xIndex = curves.x.times.indexOf( time );
			if ( curves.y ) yIndex = curves.y.times.indexOf( time );
			if ( curves.z ) zIndex = curves.z.times.indexOf( time );

			// if there is an x value defined for this frame, use that
			if ( xIndex !== - 1 ) {

				const xValue = curves.x.values[ xIndex ];
				values.push( xValue );
				prevValue[ 0 ] = xValue;

			} else {

				// otherwise use the x value from the previous frame
				values.push( prevValue[ 0 ] );

			}

			if ( yIndex !== - 1 ) {

				const yValue = curves.y.values[ yIndex ];
				values.push( yValue );
				prevValue[ 1 ] = yValue;

			} else {

				values.push( prevValue[ 1 ] );

			}

			if ( zIndex !== - 1 ) {

				const zValue = curves.z.values[ zIndex ];
				values.push( zValue );
				prevValue[ 2 ] = zValue;

			} else {

				values.push( prevValue[ 2 ] );

			}

		} );

		return values;

	}
```
</details>

##### `interpolateRotations(curvex: any, curvey: any, curvez: any, eulerOrder: any): any[][]`

<details><summary>Code</summary>

```ts
interpolateRotations( curvex, curvey, curvez, eulerOrder ) {

		const times = [];
		const values = [];

		// Add first frame
		times.push( curvex.times[ 0 ] );
		values.push( MathUtils.degToRad( curvex.values[ 0 ] ) );
		values.push( MathUtils.degToRad( curvey.values[ 0 ] ) );
		values.push( MathUtils.degToRad( curvez.values[ 0 ] ) );

		for ( let i = 1; i < curvex.values.length; i ++ ) {

			const initialValue = [
				curvex.values[ i - 1 ],
				curvey.values[ i - 1 ],
				curvez.values[ i - 1 ],
			];

			if ( isNaN( initialValue[ 0 ] ) || isNaN( initialValue[ 1 ] ) || isNaN( initialValue[ 2 ] ) ) {

				continue;

			}

			const initialValueRad = initialValue.map( MathUtils.degToRad );

			const currentValue = [
				curvex.values[ i ],
				curvey.values[ i ],
				curvez.values[ i ],
			];

			if ( isNaN( currentValue[ 0 ] ) || isNaN( currentValue[ 1 ] ) || isNaN( currentValue[ 2 ] ) ) {

				continue;

			}

			const currentValueRad = currentValue.map( MathUtils.degToRad );

			const valuesSpan = [
				currentValue[ 0 ] - initialValue[ 0 ],
				currentValue[ 1 ] - initialValue[ 1 ],
				currentValue[ 2 ] - initialValue[ 2 ],
			];

			const absoluteSpan = [
				Math.abs( valuesSpan[ 0 ] ),
				Math.abs( valuesSpan[ 1 ] ),
				Math.abs( valuesSpan[ 2 ] ),
			];

			if ( absoluteSpan[ 0 ] >= 180 || absoluteSpan[ 1 ] >= 180 || absoluteSpan[ 2 ] >= 180 ) {

				const maxAbsSpan = Math.max( ...absoluteSpan );

				const numSubIntervals = maxAbsSpan / 180;

				const E1 = new Euler( ...initialValueRad, eulerOrder );
				const E2 = new Euler( ...currentValueRad, eulerOrder );

				const Q1 = new Quaternion().setFromEuler( E1 );
				const Q2 = new Quaternion().setFromEuler( E2 );

				// Check unroll
				if ( Q1.dot( Q2 ) ) {

					Q2.set( - Q2.x, - Q2.y, - Q2.z, - Q2.w );

				}

				// Interpolate
				const initialTime = curvex.times[ i - 1 ];
				const timeSpan = curvex.times[ i ] - initialTime;

				const Q = new Quaternion();
				const E = new Euler();
				for ( let t = 0; t < 1; t += 1 / numSubIntervals ) {

					Q.copy( Q1.clone().slerp( Q2.clone(), t ) );

					times.push( initialTime + t * timeSpan );
					E.setFromQuaternion( Q, eulerOrder );

					values.push( E.x );
					values.push( E.y );
					values.push( E.z );

				}

			} else {

				times.push( curvex.times[ i ] );
				values.push( MathUtils.degToRad( curvex.values[ i ] ) );
				values.push( MathUtils.degToRad( curvey.values[ i ] ) );
				values.push( MathUtils.degToRad( curvez.values[ i ] ) );

			}

		}

		return [ times, values ];

	}
```
</details>

### `TextParser`

<details><summary>Class Code</summary>

```ts
class TextParser {

	getPrevNode() {

		return this.nodeStack[ this.currentIndent - 2 ];

	}

	getCurrentNode() {

		return this.nodeStack[ this.currentIndent - 1 ];

	}

	getCurrentProp() {

		return this.currentProp;

	}

	pushStack( node ) {

		this.nodeStack.push( node );
		this.currentIndent += 1;

	}

	popStack() {

		this.nodeStack.pop();
		this.currentIndent -= 1;

	}

	setCurrentProp( val, name ) {

		this.currentProp = val;
		this.currentPropName = name;

	}

	parse( text ) {

		this.currentIndent = 0;

		this.allNodes = new FBXTree();
		this.nodeStack = [];
		this.currentProp = [];
		this.currentPropName = '';

		const scope = this;

		const split = text.split( /[\r\n]+/ );

		split.forEach( function ( line, i ) {

			const matchComment = line.match( /^[\s\t]*;/ );
			const matchEmpty = line.match( /^[\s\t]*$/ );

			if ( matchComment || matchEmpty ) return;

			const matchBeginning = line.match( '^\\t{' + scope.currentIndent + '}(\\w+):(.*){', '' );
			const matchProperty = line.match( '^\\t{' + ( scope.currentIndent ) + '}(\\w+):[\\s\\t\\r\\n](.*)' );
			const matchEnd = line.match( '^\\t{' + ( scope.currentIndent - 1 ) + '}}' );

			if ( matchBeginning ) {

				scope.parseNodeBegin( line, matchBeginning );

			} else if ( matchProperty ) {

				scope.parseNodeProperty( line, matchProperty, split[ ++ i ] );

			} else if ( matchEnd ) {

				scope.popStack();

			} else if ( line.match( /^[^\s\t}]/ ) ) {

				// large arrays are split over multiple lines terminated with a ',' character
				// if this is encountered the line needs to be joined to the previous line
				scope.parseNodePropertyContinued( line );

			}

		} );

		return this.allNodes;

	}

	parseNodeBegin( line, property ) {

		const nodeName = property[ 1 ].trim().replace( /^"/, '' ).replace( /"$/, '' );

		const nodeAttrs = property[ 2 ].split( ',' ).map( function ( attr ) {

			return attr.trim().replace( /^"/, '' ).replace( /"$/, '' );

		} );

		const node = { name: nodeName };
		const attrs = this.parseNodeAttr( nodeAttrs );

		const currentNode = this.getCurrentNode();

		// a top node
		if ( this.currentIndent === 0 ) {

			this.allNodes.add( nodeName, node );

		} else { // a subnode

			// if the subnode already exists, append it
			if ( nodeName in currentNode ) {

				// special case Pose needs PoseNodes as an array
				if ( nodeName === 'PoseNode' ) {

					currentNode.PoseNode.push( node );

				} else if ( currentNode[ nodeName ].id !== undefined ) {

					currentNode[ nodeName ] = {};
					currentNode[ nodeName ][ currentNode[ nodeName ].id ] = currentNode[ nodeName ];

				}

				if ( attrs.id !== '' ) currentNode[ nodeName ][ attrs.id ] = node;

			} else if ( typeof attrs.id === 'number' ) {

				currentNode[ nodeName ] = {};
				currentNode[ nodeName ][ attrs.id ] = node;

			} else if ( nodeName !== 'Properties70' ) {

				if ( nodeName === 'PoseNode' )	currentNode[ nodeName ] = [ node ];
				else currentNode[ nodeName ] = node;

			}

		}

		if ( typeof attrs.id === 'number' ) node.id = attrs.id;
		if ( attrs.name !== '' ) node.attrName = attrs.name;
		if ( attrs.type !== '' ) node.attrType = attrs.type;

		this.pushStack( node );

	}

	parseNodeAttr( attrs ) {

		let id = attrs[ 0 ];

		if ( attrs[ 0 ] !== '' ) {

			id = parseInt( attrs[ 0 ] );

			if ( isNaN( id ) ) {

				id = attrs[ 0 ];

			}

		}

		let name = '', type = '';

		if ( attrs.length > 1 ) {

			name = attrs[ 1 ].replace( /^(\w+)::/, '' );
			type = attrs[ 2 ];

		}

		return { id: id, name: name, type: type };

	}

	parseNodeProperty( line, property, contentLine ) {

		let propName = property[ 1 ].replace( /^"/, '' ).replace( /"$/, '' ).trim();
		let propValue = property[ 2 ].replace( /^"/, '' ).replace( /"$/, '' ).trim();

		// for special case: base64 image data follows "Content: ," line
		//	Content: ,
		//	 "/9j/4RDaRXhpZgAATU0A..."
		if ( propName === 'Content' && propValue === ',' ) {

			propValue = contentLine.replace( /"/g, '' ).replace( /,$/, '' ).trim();

		}

		const currentNode = this.getCurrentNode();
		const parentName = currentNode.name;

		if ( parentName === 'Properties70' ) {

			this.parseNodeSpecialProperty( line, propName, propValue );
			return;

		}

		// Connections
		if ( propName === 'C' ) {

			const connProps = propValue.split( ',' ).slice( 1 );
			const from = parseInt( connProps[ 0 ] );
			const to = parseInt( connProps[ 1 ] );

			let rest = propValue.split( ',' ).slice( 3 );

			rest = rest.map( function ( elem ) {

				return elem.trim().replace( /^"/, '' );

			} );

			propName = 'connections';
			propValue = [ from, to ];
			append( propValue, rest );

			if ( currentNode[ propName ] === undefined ) {

				currentNode[ propName ] = [];

			}

		}

		// Node
		if ( propName === 'Node' ) currentNode.id = propValue;

		// connections
		if ( propName in currentNode && Array.isArray( currentNode[ propName ] ) ) {

			currentNode[ propName ].push( propValue );

		} else {

			if ( propName !== 'a' ) currentNode[ propName ] = propValue;
			else currentNode.a = propValue;

		}

		this.setCurrentProp( currentNode, propName );

		// convert string to array, unless it ends in ',' in which case more will be added to it
		if ( propName === 'a' && propValue.slice( - 1 ) !== ',' ) {

			currentNode.a = parseNumberArray( propValue );

		}

	}

	parseNodePropertyContinued( line ) {

		const currentNode = this.getCurrentNode();

		currentNode.a += line;

		// if the line doesn't end in ',' we have reached the end of the property value
		// so convert the string to an array
		if ( line.slice( - 1 ) !== ',' ) {

			currentNode.a = parseNumberArray( currentNode.a );

		}

	}

	// parse "Property70"
	parseNodeSpecialProperty( line, propName, propValue ) {

		// split this
		// P: "Lcl Scaling", "Lcl Scaling", "", "A",1,1,1
		// into array like below
		// ["Lcl Scaling", "Lcl Scaling", "", "A", "1,1,1" ]
		const props = propValue.split( '",' ).map( function ( prop ) {

			return prop.trim().replace( /^\"/, '' ).replace( /\s/, '_' );

		} );

		const innerPropName = props[ 0 ];
		const innerPropType1 = props[ 1 ];
		const innerPropType2 = props[ 2 ];
		const innerPropFlag = props[ 3 ];
		let innerPropValue = props[ 4 ];

		// cast values where needed, otherwise leave as strings
		switch ( innerPropType1 ) {

			case 'int':
			case 'enum':
			case 'bool':
			case 'ULongLong':
			case 'double':
			case 'Number':
			case 'FieldOfView':
				innerPropValue = parseFloat( innerPropValue );
				break;

			case 'Color':
			case 'ColorRGB':
			case 'Vector3D':
			case 'Lcl_Translation':
			case 'Lcl_Rotation':
			case 'Lcl_Scaling':
				innerPropValue = parseNumberArray( innerPropValue );
				break;

		}

		// CAUTION: these props must append to parent's parent
		this.getPrevNode()[ innerPropName ] = {

			'type': innerPropType1,
			'type2': innerPropType2,
			'flag': innerPropFlag,
			'value': innerPropValue

		};

		this.setCurrentProp( this.getPrevNode(), innerPropName );

	}

}
```
</details>

#### Methods

##### `getPrevNode(): any`

<details><summary>Code</summary>

```ts
getPrevNode() {

		return this.nodeStack[ this.currentIndent - 2 ];

	}
```
</details>

##### `getCurrentNode(): any`

<details><summary>Code</summary>

```ts
getCurrentNode() {

		return this.nodeStack[ this.currentIndent - 1 ];

	}
```
</details>

##### `getCurrentProp(): any`

<details><summary>Code</summary>

```ts
getCurrentProp() {

		return this.currentProp;

	}
```
</details>

##### `pushStack(node: any): void`

<details><summary>Code</summary>

```ts
pushStack( node ) {

		this.nodeStack.push( node );
		this.currentIndent += 1;

	}
```
</details>

##### `popStack(): void`

<details><summary>Code</summary>

```ts
popStack() {

		this.nodeStack.pop();
		this.currentIndent -= 1;

	}
```
</details>

##### `setCurrentProp(val: any, name: any): void`

<details><summary>Code</summary>

```ts
setCurrentProp( val, name ) {

		this.currentProp = val;
		this.currentPropName = name;

	}
```
</details>

##### `parse(text: any): FBXTree`

<details><summary>Code</summary>

```ts
parse( text ) {

		this.currentIndent = 0;

		this.allNodes = new FBXTree();
		this.nodeStack = [];
		this.currentProp = [];
		this.currentPropName = '';

		const scope = this;

		const split = text.split( /[\r\n]+/ );

		split.forEach( function ( line, i ) {

			const matchComment = line.match( /^[\s\t]*;/ );
			const matchEmpty = line.match( /^[\s\t]*$/ );

			if ( matchComment || matchEmpty ) return;

			const matchBeginning = line.match( '^\\t{' + scope.currentIndent + '}(\\w+):(.*){', '' );
			const matchProperty = line.match( '^\\t{' + ( scope.currentIndent ) + '}(\\w+):[\\s\\t\\r\\n](.*)' );
			const matchEnd = line.match( '^\\t{' + ( scope.currentIndent - 1 ) + '}}' );

			if ( matchBeginning ) {

				scope.parseNodeBegin( line, matchBeginning );

			} else if ( matchProperty ) {

				scope.parseNodeProperty( line, matchProperty, split[ ++ i ] );

			} else if ( matchEnd ) {

				scope.popStack();

			} else if ( line.match( /^[^\s\t}]/ ) ) {

				// large arrays are split over multiple lines terminated with a ',' character
				// if this is encountered the line needs to be joined to the previous line
				scope.parseNodePropertyContinued( line );

			}

		} );

		return this.allNodes;

	}
```
</details>

##### `parseNodeBegin(line: any, property: any): void`

<details><summary>Code</summary>

```ts
parseNodeBegin( line, property ) {

		const nodeName = property[ 1 ].trim().replace( /^"/, '' ).replace( /"$/, '' );

		const nodeAttrs = property[ 2 ].split( ',' ).map( function ( attr ) {

			return attr.trim().replace( /^"/, '' ).replace( /"$/, '' );

		} );

		const node = { name: nodeName };
		const attrs = this.parseNodeAttr( nodeAttrs );

		const currentNode = this.getCurrentNode();

		// a top node
		if ( this.currentIndent === 0 ) {

			this.allNodes.add( nodeName, node );

		} else { // a subnode

			// if the subnode already exists, append it
			if ( nodeName in currentNode ) {

				// special case Pose needs PoseNodes as an array
				if ( nodeName === 'PoseNode' ) {

					currentNode.PoseNode.push( node );

				} else if ( currentNode[ nodeName ].id !== undefined ) {

					currentNode[ nodeName ] = {};
					currentNode[ nodeName ][ currentNode[ nodeName ].id ] = currentNode[ nodeName ];

				}

				if ( attrs.id !== '' ) currentNode[ nodeName ][ attrs.id ] = node;

			} else if ( typeof attrs.id === 'number' ) {

				currentNode[ nodeName ] = {};
				currentNode[ nodeName ][ attrs.id ] = node;

			} else if ( nodeName !== 'Properties70' ) {

				if ( nodeName === 'PoseNode' )	currentNode[ nodeName ] = [ node ];
				else currentNode[ nodeName ] = node;

			}

		}

		if ( typeof attrs.id === 'number' ) node.id = attrs.id;
		if ( attrs.name !== '' ) node.attrName = attrs.name;
		if ( attrs.type !== '' ) node.attrType = attrs.type;

		this.pushStack( node );

	}
```
</details>

##### `parseNodeAttr(attrs: any): { id: any; name: string; type: string; }`

<details><summary>Code</summary>

```ts
parseNodeAttr( attrs ) {

		let id = attrs[ 0 ];

		if ( attrs[ 0 ] !== '' ) {

			id = parseInt( attrs[ 0 ] );

			if ( isNaN( id ) ) {

				id = attrs[ 0 ];

			}

		}

		let name = '', type = '';

		if ( attrs.length > 1 ) {

			name = attrs[ 1 ].replace( /^(\w+)::/, '' );
			type = attrs[ 2 ];

		}

		return { id: id, name: name, type: type };

	}
```
</details>

##### `parseNodeProperty(line: any, property: any, contentLine: any): void`

<details><summary>Code</summary>

```ts
parseNodeProperty( line, property, contentLine ) {

		let propName = property[ 1 ].replace( /^"/, '' ).replace( /"$/, '' ).trim();
		let propValue = property[ 2 ].replace( /^"/, '' ).replace( /"$/, '' ).trim();

		// for special case: base64 image data follows "Content: ," line
		//	Content: ,
		//	 "/9j/4RDaRXhpZgAATU0A..."
		if ( propName === 'Content' && propValue === ',' ) {

			propValue = contentLine.replace( /"/g, '' ).replace( /,$/, '' ).trim();

		}

		const currentNode = this.getCurrentNode();
		const parentName = currentNode.name;

		if ( parentName === 'Properties70' ) {

			this.parseNodeSpecialProperty( line, propName, propValue );
			return;

		}

		// Connections
		if ( propName === 'C' ) {

			const connProps = propValue.split( ',' ).slice( 1 );
			const from = parseInt( connProps[ 0 ] );
			const to = parseInt( connProps[ 1 ] );

			let rest = propValue.split( ',' ).slice( 3 );

			rest = rest.map( function ( elem ) {

				return elem.trim().replace( /^"/, '' );

			} );

			propName = 'connections';
			propValue = [ from, to ];
			append( propValue, rest );

			if ( currentNode[ propName ] === undefined ) {

				currentNode[ propName ] = [];

			}

		}

		// Node
		if ( propName === 'Node' ) currentNode.id = propValue;

		// connections
		if ( propName in currentNode && Array.isArray( currentNode[ propName ] ) ) {

			currentNode[ propName ].push( propValue );

		} else {

			if ( propName !== 'a' ) currentNode[ propName ] = propValue;
			else currentNode.a = propValue;

		}

		this.setCurrentProp( currentNode, propName );

		// convert string to array, unless it ends in ',' in which case more will be added to it
		if ( propName === 'a' && propValue.slice( - 1 ) !== ',' ) {

			currentNode.a = parseNumberArray( propValue );

		}

	}
```
</details>

##### `parseNodePropertyContinued(line: any): void`

<details><summary>Code</summary>

```ts
parseNodePropertyContinued( line ) {

		const currentNode = this.getCurrentNode();

		currentNode.a += line;

		// if the line doesn't end in ',' we have reached the end of the property value
		// so convert the string to an array
		if ( line.slice( - 1 ) !== ',' ) {

			currentNode.a = parseNumberArray( currentNode.a );

		}

	}
```
</details>

##### `parseNodeSpecialProperty(line: any, propName: any, propValue: any): void`

<details><summary>Code</summary>

```ts
parseNodeSpecialProperty( line, propName, propValue ) {

		// split this
		// P: "Lcl Scaling", "Lcl Scaling", "", "A",1,1,1
		// into array like below
		// ["Lcl Scaling", "Lcl Scaling", "", "A", "1,1,1" ]
		const props = propValue.split( '",' ).map( function ( prop ) {

			return prop.trim().replace( /^\"/, '' ).replace( /\s/, '_' );

		} );

		const innerPropName = props[ 0 ];
		const innerPropType1 = props[ 1 ];
		const innerPropType2 = props[ 2 ];
		const innerPropFlag = props[ 3 ];
		let innerPropValue = props[ 4 ];

		// cast values where needed, otherwise leave as strings
		switch ( innerPropType1 ) {

			case 'int':
			case 'enum':
			case 'bool':
			case 'ULongLong':
			case 'double':
			case 'Number':
			case 'FieldOfView':
				innerPropValue = parseFloat( innerPropValue );
				break;

			case 'Color':
			case 'ColorRGB':
			case 'Vector3D':
			case 'Lcl_Translation':
			case 'Lcl_Rotation':
			case 'Lcl_Scaling':
				innerPropValue = parseNumberArray( innerPropValue );
				break;

		}

		// CAUTION: these props must append to parent's parent
		this.getPrevNode()[ innerPropName ] = {

			'type': innerPropType1,
			'type2': innerPropType2,
			'flag': innerPropFlag,
			'value': innerPropValue

		};

		this.setCurrentProp( this.getPrevNode(), innerPropName );

	}
```
</details>

### `BinaryParser`

<details><summary>Class Code</summary>

```ts
class BinaryParser {

	parse( buffer ) {

		const reader = new BinaryReader( buffer );
		reader.skip( 23 ); // skip magic 23 bytes

		const version = reader.getUint32();

		if ( version < 6400 ) {

			throw new Error( 'THREE.FBXLoader: FBX version not supported, FileVersion: ' + version );

		}

		const allNodes = new FBXTree();

		while ( ! this.endOfContent( reader ) ) {

			const node = this.parseNode( reader, version );
			if ( node !== null ) allNodes.add( node.name, node );

		}

		return allNodes;

	}

	// Check if reader has reached the end of content.
	endOfContent( reader ) {

		// footer size: 160bytes + 16-byte alignment padding
		// - 16bytes: magic
		// - padding til 16-byte alignment (at least 1byte?)
		//	(seems like some exporters embed fixed 15 or 16bytes?)
		// - 4bytes: magic
		// - 4bytes: version
		// - 120bytes: zero
		// - 16bytes: magic
		if ( reader.size() % 16 === 0 ) {

			return ( ( reader.getOffset() + 160 + 16 ) & ~ 0xf ) >= reader.size();

		} else {

			return reader.getOffset() + 160 + 16 >= reader.size();

		}

	}

	// recursively parse nodes until the end of the file is reached
	parseNode( reader, version ) {

		const node = {};

		// The first three data sizes depends on version.
		const endOffset = ( version >= 7500 ) ? reader.getUint64() : reader.getUint32();
		const numProperties = ( version >= 7500 ) ? reader.getUint64() : reader.getUint32();

		( version >= 7500 ) ? reader.getUint64() : reader.getUint32(); // the returned propertyListLen is not used

		const nameLen = reader.getUint8();
		const name = reader.getString( nameLen );

		// Regards this node as NULL-record if endOffset is zero
		if ( endOffset === 0 ) return null;

		const propertyList = [];

		for ( let i = 0; i < numProperties; i ++ ) {

			propertyList.push( this.parseProperty( reader ) );

		}

		// Regards the first three elements in propertyList as id, attrName, and attrType
		const id = propertyList.length > 0 ? propertyList[ 0 ] : '';
		const attrName = propertyList.length > 1 ? propertyList[ 1 ] : '';
		const attrType = propertyList.length > 2 ? propertyList[ 2 ] : '';

		// check if this node represents just a single property
		// like (name, 0) set or (name2, [0, 1, 2]) set of {name: 0, name2: [0, 1, 2]}
		node.singleProperty = ( numProperties === 1 && reader.getOffset() === endOffset ) ? true : false;

		while ( endOffset > reader.getOffset() ) {

			const subNode = this.parseNode( reader, version );

			if ( subNode !== null ) this.parseSubNode( name, node, subNode );

		}

		node.propertyList = propertyList; // raw property list used by parent

		if ( typeof id === 'number' ) node.id = id;
		if ( attrName !== '' ) node.attrName = attrName;
		if ( attrType !== '' ) node.attrType = attrType;
		if ( name !== '' ) node.name = name;

		return node;

	}

	parseSubNode( name, node, subNode ) {

		// special case: child node is single property
		if ( subNode.singleProperty === true ) {

			const value = subNode.propertyList[ 0 ];

			if ( Array.isArray( value ) ) {

				node[ subNode.name ] = subNode;

				subNode.a = value;

			} else {

				node[ subNode.name ] = value;

			}

		} else if ( name === 'Connections' && subNode.name === 'C' ) {

			const array = [];

			subNode.propertyList.forEach( function ( property, i ) {

				// first Connection is FBX type (OO, OP, etc.). We'll discard these
				if ( i !== 0 ) array.push( property );

			} );

			if ( node.connections === undefined ) {

				node.connections = [];

			}

			node.connections.push( array );

		} else if ( subNode.name === 'Properties70' ) {

			const keys = Object.keys( subNode );

			keys.forEach( function ( key ) {

				node[ key ] = subNode[ key ];

			} );

		} else if ( name === 'Properties70' && subNode.name === 'P' ) {

			let innerPropName = subNode.propertyList[ 0 ];
			let innerPropType1 = subNode.propertyList[ 1 ];
			const innerPropType2 = subNode.propertyList[ 2 ];
			const innerPropFlag = subNode.propertyList[ 3 ];
			let innerPropValue;

			if ( innerPropName.indexOf( 'Lcl ' ) === 0 ) innerPropName = innerPropName.replace( 'Lcl ', 'Lcl_' );
			if ( innerPropType1.indexOf( 'Lcl ' ) === 0 ) innerPropType1 = innerPropType1.replace( 'Lcl ', 'Lcl_' );

			if ( innerPropType1 === 'Color' || innerPropType1 === 'ColorRGB' || innerPropType1 === 'Vector' || innerPropType1 === 'Vector3D' || innerPropType1.indexOf( 'Lcl_' ) === 0 ) {

				innerPropValue = [
					subNode.propertyList[ 4 ],
					subNode.propertyList[ 5 ],
					subNode.propertyList[ 6 ]
				];

			} else {

				innerPropValue = subNode.propertyList[ 4 ];

			}

			// this will be copied to parent, see above
			node[ innerPropName ] = {

				'type': innerPropType1,
				'type2': innerPropType2,
				'flag': innerPropFlag,
				'value': innerPropValue

			};

		} else if ( node[ subNode.name ] === undefined ) {

			if ( typeof subNode.id === 'number' ) {

				node[ subNode.name ] = {};
				node[ subNode.name ][ subNode.id ] = subNode;

			} else {

				node[ subNode.name ] = subNode;

			}

		} else {

			if ( subNode.name === 'PoseNode' ) {

				if ( ! Array.isArray( node[ subNode.name ] ) ) {

					node[ subNode.name ] = [ node[ subNode.name ] ];

				}

				node[ subNode.name ].push( subNode );

			} else if ( node[ subNode.name ][ subNode.id ] === undefined ) {

				node[ subNode.name ][ subNode.id ] = subNode;

			}

		}

	}

	parseProperty( reader ) {

		const type = reader.getString( 1 );
		let length;

		switch ( type ) {

			case 'C':
				return reader.getBoolean();

			case 'D':
				return reader.getFloat64();

			case 'F':
				return reader.getFloat32();

			case 'I':
				return reader.getInt32();

			case 'L':
				return reader.getInt64();

			case 'R':
				length = reader.getUint32();
				return reader.getArrayBuffer( length );

			case 'S':
				length = reader.getUint32();
				return reader.getString( length );

			case 'Y':
				return reader.getInt16();

			case 'b':
			case 'c':
			case 'd':
			case 'f':
			case 'i':
			case 'l':

				const arrayLength = reader.getUint32();
				const encoding = reader.getUint32(); // 0: non-compressed, 1: compressed
				const compressedLength = reader.getUint32();

				if ( encoding === 0 ) {

					switch ( type ) {

						case 'b':
						case 'c':
							return reader.getBooleanArray( arrayLength );

						case 'd':
							return reader.getFloat64Array( arrayLength );

						case 'f':
							return reader.getFloat32Array( arrayLength );

						case 'i':
							return reader.getInt32Array( arrayLength );

						case 'l':
							return reader.getInt64Array( arrayLength );

					}

				}

				const data = fflate.unzlibSync( new Uint8Array( reader.getArrayBuffer( compressedLength ) ) );
				const reader2 = new BinaryReader( data.buffer );

				switch ( type ) {

					case 'b':
					case 'c':
						return reader2.getBooleanArray( arrayLength );

					case 'd':
						return reader2.getFloat64Array( arrayLength );

					case 'f':
						return reader2.getFloat32Array( arrayLength );

					case 'i':
						return reader2.getInt32Array( arrayLength );

					case 'l':
						return reader2.getInt64Array( arrayLength );

				}

				break; // cannot happen but is required by the DeepScan

			default:
				throw new Error( 'THREE.FBXLoader: Unknown property type ' + type );

		}

	}

}
```
</details>

#### Methods

##### `parse(buffer: any): FBXTree`

<details><summary>Code</summary>

```ts
parse( buffer ) {

		const reader = new BinaryReader( buffer );
		reader.skip( 23 ); // skip magic 23 bytes

		const version = reader.getUint32();

		if ( version < 6400 ) {

			throw new Error( 'THREE.FBXLoader: FBX version not supported, FileVersion: ' + version );

		}

		const allNodes = new FBXTree();

		while ( ! this.endOfContent( reader ) ) {

			const node = this.parseNode( reader, version );
			if ( node !== null ) allNodes.add( node.name, node );

		}

		return allNodes;

	}
```
</details>

##### `endOfContent(reader: any): boolean`

<details><summary>Code</summary>

```ts
endOfContent( reader ) {

		// footer size: 160bytes + 16-byte alignment padding
		// - 16bytes: magic
		// - padding til 16-byte alignment (at least 1byte?)
		//	(seems like some exporters embed fixed 15 or 16bytes?)
		// - 4bytes: magic
		// - 4bytes: version
		// - 120bytes: zero
		// - 16bytes: magic
		if ( reader.size() % 16 === 0 ) {

			return ( ( reader.getOffset() + 160 + 16 ) & ~ 0xf ) >= reader.size();

		} else {

			return reader.getOffset() + 160 + 16 >= reader.size();

		}

	}
```
</details>

##### `parseNode(reader: any, version: any): { singleProperty: boolean; propertyList: any[]; id: number; attrName: any; attrType: any; name: any; }`

<details><summary>Code</summary>

```ts
parseNode( reader, version ) {

		const node = {};

		// The first three data sizes depends on version.
		const endOffset = ( version >= 7500 ) ? reader.getUint64() : reader.getUint32();
		const numProperties = ( version >= 7500 ) ? reader.getUint64() : reader.getUint32();

		( version >= 7500 ) ? reader.getUint64() : reader.getUint32(); // the returned propertyListLen is not used

		const nameLen = reader.getUint8();
		const name = reader.getString( nameLen );

		// Regards this node as NULL-record if endOffset is zero
		if ( endOffset === 0 ) return null;

		const propertyList = [];

		for ( let i = 0; i < numProperties; i ++ ) {

			propertyList.push( this.parseProperty( reader ) );

		}

		// Regards the first three elements in propertyList as id, attrName, and attrType
		const id = propertyList.length > 0 ? propertyList[ 0 ] : '';
		const attrName = propertyList.length > 1 ? propertyList[ 1 ] : '';
		const attrType = propertyList.length > 2 ? propertyList[ 2 ] : '';

		// check if this node represents just a single property
		// like (name, 0) set or (name2, [0, 1, 2]) set of {name: 0, name2: [0, 1, 2]}
		node.singleProperty = ( numProperties === 1 && reader.getOffset() === endOffset ) ? true : false;

		while ( endOffset > reader.getOffset() ) {

			const subNode = this.parseNode( reader, version );

			if ( subNode !== null ) this.parseSubNode( name, node, subNode );

		}

		node.propertyList = propertyList; // raw property list used by parent

		if ( typeof id === 'number' ) node.id = id;
		if ( attrName !== '' ) node.attrName = attrName;
		if ( attrType !== '' ) node.attrType = attrType;
		if ( name !== '' ) node.name = name;

		return node;

	}
```
</details>

##### `parseSubNode(name: any, node: any, subNode: any): void`

<details><summary>Code</summary>

```ts
parseSubNode( name, node, subNode ) {

		// special case: child node is single property
		if ( subNode.singleProperty === true ) {

			const value = subNode.propertyList[ 0 ];

			if ( Array.isArray( value ) ) {

				node[ subNode.name ] = subNode;

				subNode.a = value;

			} else {

				node[ subNode.name ] = value;

			}

		} else if ( name === 'Connections' && subNode.name === 'C' ) {

			const array = [];

			subNode.propertyList.forEach( function ( property, i ) {

				// first Connection is FBX type (OO, OP, etc.). We'll discard these
				if ( i !== 0 ) array.push( property );

			} );

			if ( node.connections === undefined ) {

				node.connections = [];

			}

			node.connections.push( array );

		} else if ( subNode.name === 'Properties70' ) {

			const keys = Object.keys( subNode );

			keys.forEach( function ( key ) {

				node[ key ] = subNode[ key ];

			} );

		} else if ( name === 'Properties70' && subNode.name === 'P' ) {

			let innerPropName = subNode.propertyList[ 0 ];
			let innerPropType1 = subNode.propertyList[ 1 ];
			const innerPropType2 = subNode.propertyList[ 2 ];
			const innerPropFlag = subNode.propertyList[ 3 ];
			let innerPropValue;

			if ( innerPropName.indexOf( 'Lcl ' ) === 0 ) innerPropName = innerPropName.replace( 'Lcl ', 'Lcl_' );
			if ( innerPropType1.indexOf( 'Lcl ' ) === 0 ) innerPropType1 = innerPropType1.replace( 'Lcl ', 'Lcl_' );

			if ( innerPropType1 === 'Color' || innerPropType1 === 'ColorRGB' || innerPropType1 === 'Vector' || innerPropType1 === 'Vector3D' || innerPropType1.indexOf( 'Lcl_' ) === 0 ) {

				innerPropValue = [
					subNode.propertyList[ 4 ],
					subNode.propertyList[ 5 ],
					subNode.propertyList[ 6 ]
				];

			} else {

				innerPropValue = subNode.propertyList[ 4 ];

			}

			// this will be copied to parent, see above
			node[ innerPropName ] = {

				'type': innerPropType1,
				'type2': innerPropType2,
				'flag': innerPropFlag,
				'value': innerPropValue

			};

		} else if ( node[ subNode.name ] === undefined ) {

			if ( typeof subNode.id === 'number' ) {

				node[ subNode.name ] = {};
				node[ subNode.name ][ subNode.id ] = subNode;

			} else {

				node[ subNode.name ] = subNode;

			}

		} else {

			if ( subNode.name === 'PoseNode' ) {

				if ( ! Array.isArray( node[ subNode.name ] ) ) {

					node[ subNode.name ] = [ node[ subNode.name ] ];

				}

				node[ subNode.name ].push( subNode );

			} else if ( node[ subNode.name ][ subNode.id ] === undefined ) {

				node[ subNode.name ][ subNode.id ] = subNode;

			}

		}

	}
```
</details>

##### `parseProperty(reader: any): any`

<details><summary>Code</summary>

```ts
parseProperty( reader ) {

		const type = reader.getString( 1 );
		let length;

		switch ( type ) {

			case 'C':
				return reader.getBoolean();

			case 'D':
				return reader.getFloat64();

			case 'F':
				return reader.getFloat32();

			case 'I':
				return reader.getInt32();

			case 'L':
				return reader.getInt64();

			case 'R':
				length = reader.getUint32();
				return reader.getArrayBuffer( length );

			case 'S':
				length = reader.getUint32();
				return reader.getString( length );

			case 'Y':
				return reader.getInt16();

			case 'b':
			case 'c':
			case 'd':
			case 'f':
			case 'i':
			case 'l':

				const arrayLength = reader.getUint32();
				const encoding = reader.getUint32(); // 0: non-compressed, 1: compressed
				const compressedLength = reader.getUint32();

				if ( encoding === 0 ) {

					switch ( type ) {

						case 'b':
						case 'c':
							return reader.getBooleanArray( arrayLength );

						case 'd':
							return reader.getFloat64Array( arrayLength );

						case 'f':
							return reader.getFloat32Array( arrayLength );

						case 'i':
							return reader.getInt32Array( arrayLength );

						case 'l':
							return reader.getInt64Array( arrayLength );

					}

				}

				const data = fflate.unzlibSync( new Uint8Array( reader.getArrayBuffer( compressedLength ) ) );
				const reader2 = new BinaryReader( data.buffer );

				switch ( type ) {

					case 'b':
					case 'c':
						return reader2.getBooleanArray( arrayLength );

					case 'd':
						return reader2.getFloat64Array( arrayLength );

					case 'f':
						return reader2.getFloat32Array( arrayLength );

					case 'i':
						return reader2.getInt32Array( arrayLength );

					case 'l':
						return reader2.getInt64Array( arrayLength );

				}

				break; // cannot happen but is required by the DeepScan

			default:
				throw new Error( 'THREE.FBXLoader: Unknown property type ' + type );

		}

	}
```
</details>

### `BinaryReader`

<details><summary>Class Code</summary>

```ts
class BinaryReader {

	constructor( buffer, littleEndian ) {

		this.dv = new DataView( buffer );
		this.offset = 0;
		this.littleEndian = ( littleEndian !== undefined ) ? littleEndian : true;
		this._textDecoder = new TextDecoder();

	}

	getOffset() {

		return this.offset;

	}

	size() {

		return this.dv.buffer.byteLength;

	}

	skip( length ) {

		this.offset += length;

	}

	// seems like true/false representation depends on exporter.
	// true: 1 or 'Y'(=0x59), false: 0 or 'T'(=0x54)
	// then sees LSB.
	getBoolean() {

		return ( this.getUint8() & 1 ) === 1;

	}

	getBooleanArray( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getBoolean() );

		}

		return a;

	}

	getUint8() {

		const value = this.dv.getUint8( this.offset );
		this.offset += 1;
		return value;

	}

	getInt16() {

		const value = this.dv.getInt16( this.offset, this.littleEndian );
		this.offset += 2;
		return value;

	}

	getInt32() {

		const value = this.dv.getInt32( this.offset, this.littleEndian );
		this.offset += 4;
		return value;

	}

	getInt32Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getInt32() );

		}

		return a;

	}

	getUint32() {

		const value = this.dv.getUint32( this.offset, this.littleEndian );
		this.offset += 4;
		return value;

	}

	// JavaScript doesn't support 64-bit integer so calculate this here
	// 1 << 32 will return 1 so using multiply operation instead here.
	// There's a possibility that this method returns wrong value if the value
	// is out of the range between Number.MAX_SAFE_INTEGER and Number.MIN_SAFE_INTEGER.
	// TODO: safely handle 64-bit integer
	getInt64() {

		let low, high;

		if ( this.littleEndian ) {

			low = this.getUint32();
			high = this.getUint32();

		} else {

			high = this.getUint32();
			low = this.getUint32();

		}

		// calculate negative value
		if ( high & 0x80000000 ) {

			high = ~ high & 0xFFFFFFFF;
			low = ~ low & 0xFFFFFFFF;

			if ( low === 0xFFFFFFFF ) high = ( high + 1 ) & 0xFFFFFFFF;

			low = ( low + 1 ) & 0xFFFFFFFF;

			return - ( high * 0x100000000 + low );

		}

		return high * 0x100000000 + low;

	}

	getInt64Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getInt64() );

		}

		return a;

	}

	// Note: see getInt64() comment
	getUint64() {

		let low, high;

		if ( this.littleEndian ) {

			low = this.getUint32();
			high = this.getUint32();

		} else {

			high = this.getUint32();
			low = this.getUint32();

		}

		return high * 0x100000000 + low;

	}

	getFloat32() {

		const value = this.dv.getFloat32( this.offset, this.littleEndian );
		this.offset += 4;
		return value;

	}

	getFloat32Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat32() );

		}

		return a;

	}

	getFloat64() {

		const value = this.dv.getFloat64( this.offset, this.littleEndian );
		this.offset += 8;
		return value;

	}

	getFloat64Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat64() );

		}

		return a;

	}

	getArrayBuffer( size ) {

		const value = this.dv.buffer.slice( this.offset, this.offset + size );
		this.offset += size;
		return value;

	}

	getString( size ) {

		const start = this.offset;
		let a = new Uint8Array( this.dv.buffer, start, size );

		this.skip( size );

		const nullByte = a.indexOf( 0 );
		if ( nullByte >= 0 ) a = new Uint8Array( this.dv.buffer, start, nullByte );

		return this._textDecoder.decode( a );

	}

}
```
</details>

#### Methods

##### `getOffset(): number`

<details><summary>Code</summary>

```ts
getOffset() {

		return this.offset;

	}
```
</details>

##### `size(): any`

<details><summary>Code</summary>

```ts
size() {

		return this.dv.buffer.byteLength;

	}
```
</details>

##### `skip(length: any): void`

<details><summary>Code</summary>

```ts
skip( length ) {

		this.offset += length;

	}
```
</details>

##### `getBoolean(): boolean`

<details><summary>Code</summary>

```ts
getBoolean() {

		return ( this.getUint8() & 1 ) === 1;

	}
```
</details>

##### `getBooleanArray(size: any): boolean[]`

<details><summary>Code</summary>

```ts
getBooleanArray( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getBoolean() );

		}

		return a;

	}
```
</details>

##### `getUint8(): number`

<details><summary>Code</summary>

```ts
getUint8() {

		const value = this.dv.getUint8( this.offset );
		this.offset += 1;
		return value;

	}
```
</details>

##### `getInt16(): number`

<details><summary>Code</summary>

```ts
getInt16() {

		const value = this.dv.getInt16( this.offset, this.littleEndian );
		this.offset += 2;
		return value;

	}
```
</details>

##### `getInt32(): number`

<details><summary>Code</summary>

```ts
getInt32() {

		const value = this.dv.getInt32( this.offset, this.littleEndian );
		this.offset += 4;
		return value;

	}
```
</details>

##### `getInt32Array(size: any): number[]`

<details><summary>Code</summary>

```ts
getInt32Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getInt32() );

		}

		return a;

	}
```
</details>

##### `getUint32(): number`

<details><summary>Code</summary>

```ts
getUint32() {

		const value = this.dv.getUint32( this.offset, this.littleEndian );
		this.offset += 4;
		return value;

	}
```
</details>

##### `getInt64(): number`

<details><summary>Code</summary>

```ts
getInt64() {

		let low, high;

		if ( this.littleEndian ) {

			low = this.getUint32();
			high = this.getUint32();

		} else {

			high = this.getUint32();
			low = this.getUint32();

		}

		// calculate negative value
		if ( high & 0x80000000 ) {

			high = ~ high & 0xFFFFFFFF;
			low = ~ low & 0xFFFFFFFF;

			if ( low === 0xFFFFFFFF ) high = ( high + 1 ) & 0xFFFFFFFF;

			low = ( low + 1 ) & 0xFFFFFFFF;

			return - ( high * 0x100000000 + low );

		}

		return high * 0x100000000 + low;

	}
```
</details>

##### `getInt64Array(size: any): number[]`

<details><summary>Code</summary>

```ts
getInt64Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getInt64() );

		}

		return a;

	}
```
</details>

##### `getUint64(): number`

<details><summary>Code</summary>

```ts
getUint64() {

		let low, high;

		if ( this.littleEndian ) {

			low = this.getUint32();
			high = this.getUint32();

		} else {

			high = this.getUint32();
			low = this.getUint32();

		}

		return high * 0x100000000 + low;

	}
```
</details>

##### `getFloat32(): number`

<details><summary>Code</summary>

```ts
getFloat32() {

		const value = this.dv.getFloat32( this.offset, this.littleEndian );
		this.offset += 4;
		return value;

	}
```
</details>

##### `getFloat32Array(size: any): number[]`

<details><summary>Code</summary>

```ts
getFloat32Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat32() );

		}

		return a;

	}
```
</details>

##### `getFloat64(): number`

<details><summary>Code</summary>

```ts
getFloat64() {

		const value = this.dv.getFloat64( this.offset, this.littleEndian );
		this.offset += 8;
		return value;

	}
```
</details>

##### `getFloat64Array(size: any): number[]`

<details><summary>Code</summary>

```ts
getFloat64Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat64() );

		}

		return a;

	}
```
</details>

##### `getArrayBuffer(size: any): any`

<details><summary>Code</summary>

```ts
getArrayBuffer( size ) {

		const value = this.dv.buffer.slice( this.offset, this.offset + size );
		this.offset += size;
		return value;

	}
```
</details>

##### `getString(size: any): string`

<details><summary>Code</summary>

```ts
getString( size ) {

		const start = this.offset;
		let a = new Uint8Array( this.dv.buffer, start, size );

		this.skip( size );

		const nullByte = a.indexOf( 0 );
		if ( nullByte >= 0 ) a = new Uint8Array( this.dv.buffer, start, nullByte );

		return this._textDecoder.decode( a );

	}
```
</details>

### `FBXTree`

<details><summary>Class Code</summary>

```ts
class FBXTree {

	add( key, val ) {

		this[ key ] = val;

	}

}
```
</details>

#### Methods

##### `add(key: any, val: any): void`

<details><summary>Code</summary>

```ts
add( key, val ) {

		this[ key ] = val;

	}
```
</details>


---