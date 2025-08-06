[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ColladaLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 126 |
| 🧱 Classes | 1 |
| 📦 Imports | 40 |
| 📊 Variables & Constants | 337 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/ColladaLoader.js`**

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
| `DoubleSide` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `FrontSide` | `three` |
| `Group` | `three` |
| `Line` | `three` |
| `LineBasicMaterial` | `three` |
| `LineSegments` | `three` |
| `Loader` | `three` |
| `LoaderUtils` | `three` |
| `MathUtils` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `MeshLambertMaterial` | `three` |
| `MeshPhongMaterial` | `three` |
| `OrthographicCamera` | `three` |
| `PerspectiveCamera` | `three` |
| `PointLight` | `three` |
| `Quaternion` | `three` |
| `QuaternionKeyframeTrack` | `three` |
| `RepeatWrapping` | `three` |
| `Scene` | `three` |
| `Skeleton` | `three` |
| `SkinnedMesh` | `three` |
| `SpotLight` | `three` |
| `TextureLoader` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |
| `VectorKeyframeTrack` | `three` |
| `SRGBColorSpace` | `three` |
| `TGALoader` | `../loaders/TGALoader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `path` | `any` | let/var | `( scope.path === '' ) ? LoaderUtils.extractUrlBase( url ) : scope.path` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `childNodes` | `any` | let/var | `xml.childNodes` | ✗ |
| `child` | `any` | let/var | `childNodes[ i ]` | ✗ |
| `array` | `any[]` | let/var | `new Array( parts.length )` | ✗ |
| `array` | `any[]` | let/var | `new Array( parts.length )` | ✗ |
| `array` | `any[]` | let/var | `new Array( parts.length )` | ✗ |
| `library` | `any` | let/var | `getElementsByTagName( xml, libraryName )[ 0 ]` | ✗ |
| `object` | `any` | let/var | `data[ name ]` | ✗ |
| `data` | `{ sources: {}; samplers: {}; channels...` | let/var | `{ sources: {}, samplers: {}, channels: {} }` | ✗ |
| `hasChildren` | `boolean` | let/var | `false` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `id` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `{ inputs: {}; }` | let/var | `{ inputs: {}, }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ member: any; indices: any; id: any;...` | let/var | `{}` | ✗ |
| `arraySyntax` | `boolean` | let/var | `( sid.indexOf( '(' ) !== - 1 )` | ✗ |
| `memberSyntax` | `boolean` | let/var | `( sid.indexOf( '.' ) !== - 1 )` | ✗ |
| `tracks` | `any[]` | let/var | `[]` | ✗ |
| `channels` | `any` | let/var | `data.channels` | ✗ |
| `samplers` | `any` | let/var | `data.samplers` | ✗ |
| `sources` | `any` | let/var | `data.sources` | ✗ |
| `channel` | `any` | let/var | `channels[ target ]` | ✗ |
| `sampler` | `any` | let/var | `samplers[ channel.sampler ]` | ✗ |
| `inputId` | `any` | let/var | `sampler.inputs.INPUT` | ✗ |
| `outputId` | `any` | let/var | `sampler.inputs.OUTPUT` | ✗ |
| `inputSource` | `any` | let/var | `sources[ inputId ]` | ✗ |
| `outputSource` | `any` | let/var | `sources[ outputId ]` | ✗ |
| `node` | `any` | let/var | `library.nodes[ channel.id ]` | ✗ |
| `transform` | `any` | let/var | `node.transforms[ channel.sid ]` | ✗ |
| `time` | `any` | let/var | `*not shown*` | ✗ |
| `stride` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `il` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `jl` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `value` | `any` | let/var | `outputSource.array[ stride ]` | ✗ |
| `index` | `any` | let/var | `channel.indices[ 0 ] + 4 * channel.indices[ 1 ]` | ✗ |
| `animation` | `{ name: any; keyframes: { time: numbe...` | let/var | `{ name: object3D.uuid, keyframes: keyframes }` | ✗ |
| `keyframes` | `any[]` | let/var | `[]` | ✗ |
| `position` | `any` | let/var | `new Vector3()` | ✗ |
| `scale` | `any` | let/var | `new Vector3()` | ✗ |
| `quaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `keyframes` | `any` | let/var | `animation.keyframes` | ✗ |
| `name` | `any` | let/var | `animation.name` | ✗ |
| `times` | `any[]` | let/var | `[]` | ✗ |
| `positionData` | `any[]` | let/var | `[]` | ✗ |
| `quaternionData` | `any[]` | let/var | `[]` | ✗ |
| `scaleData` | `any[]` | let/var | `[]` | ✗ |
| `keyframe` | `any` | let/var | `keyframes[ i ]` | ✗ |
| `time` | `any` | let/var | `keyframe.time` | ✗ |
| `value` | `any` | let/var | `keyframe.value` | ✗ |
| `keyframe` | `any` | let/var | `*not shown*` | ✗ |
| `empty` | `boolean` | let/var | `true` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `prev` | `any` | let/var | `*not shown*` | ✗ |
| `next` | `any` | let/var | `*not shown*` | ✗ |
| `keyframe` | `any` | let/var | `keyframes[ i ]` | ✗ |
| `keyframe` | `any` | let/var | `keyframes[ i ]` | ✗ |
| `keyframe` | `any` | let/var | `keyframes[ i ]` | ✗ |
| `data` | `{ name: any; start: number; end: numb...` | let/var | `{ name: xml.getAttribute( 'id' ) \|\| 'default', start: parseFloat( xml.getAt...` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `tracks` | `any[]` | let/var | `[]` | ✗ |
| `name` | `any` | let/var | `data.name` | ✗ |
| `duration` | `number` | let/var | `( data.end - data.start ) \|\| - 1` | ✗ |
| `animations` | `any` | let/var | `data.animations` | ✗ |
| `data` | `{ id: any; skin: { sources: {}; }; }` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ sources: {}; }` | let/var | `{ sources: {} }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ inputs: {}; }` | let/var | `{ inputs: {} }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ inputs: {}; }` | let/var | `{ inputs: {} }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `build` | `{ id: any; }` | let/var | `{ id: data.id }` | ✗ |
| `geometry` | `any` | let/var | `library.geometries[ build.id ]` | ✗ |
| `BONE_LIMIT` | `4` | let/var | `4` | ✗ |
| `build` | `{ joints: any[]; indices: { array: an...` | let/var | `{ joints: [], // this must be an array to preserve the joint order indices: {...` | ✗ |
| `sources` | `any` | let/var | `data.sources` | ✗ |
| `vertexWeights` | `any` | let/var | `data.vertexWeights` | ✗ |
| `vcount` | `any` | let/var | `vertexWeights.vcount` | ✗ |
| `v` | `any` | let/var | `vertexWeights.v` | ✗ |
| `jointOffset` | `any` | let/var | `vertexWeights.inputs.JOINT.offset` | ✗ |
| `weightOffset` | `any` | let/var | `vertexWeights.inputs.WEIGHT.offset` | ✗ |
| `jointSource` | `any` | let/var | `data.sources[ data.joints.inputs.JOINT ]` | ✗ |
| `inverseSource` | `any` | let/var | `data.sources[ data.joints.inputs.INV_BIND_MATRIX ]` | ✗ |
| `weights` | `any` | let/var | `sources[ vertexWeights.inputs.WEIGHT.id ].array` | ✗ |
| `stride` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `jointCount` | `any` | let/var | `vcount[ i ]` | ✗ |
| `vertexSkinData` | `any[]` | let/var | `[]` | ✗ |
| `skinIndex` | `any` | let/var | `v[ stride + jointOffset ]` | ✗ |
| `weightId` | `any` | let/var | `v[ stride + weightOffset ]` | ✗ |
| `skinWeight` | `any` | let/var | `weights[ weightId ]` | ✗ |
| `d` | `{ index: any; weight: any; }` | let/var | `vertexSkinData[ j ]` | ✗ |
| `name` | `any` | let/var | `jointSource.array[ i ]` | ✗ |
| `data` | `{ init_from: any; }` | let/var | `{ init_from: getElementsByTagName( xml, 'init_from' )[ 0 ].textContent }` | ✗ |
| `data` | `any` | let/var | `library.images[ id ]` | ✗ |
| `data` | `{ profile: { surfaces: {}; samplers: ...` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ surfaces: {}; samplers: {}; }` | let/var | `{ surfaces: {}, samplers: {} }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ init_from: any; }` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ source: any; }` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ type: any; parameters: {}; extra: {...` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ technique: {}; }` | let/var | `{ technique: {} }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ technique: {}; }` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ name: any; }` | let/var | `{ name: xml.getAttribute( 'name' ) }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `loader` | `any` | let/var | `*not shown*` | ✗ |
| `technique` | `any` | let/var | `effect.profile.technique` | ✗ |
| `material` | `any` | let/var | `*not shown*` | ✗ |
| `sampler` | `any` | let/var | `effect.profile.samplers[ textureObject.id ]` | ✗ |
| `image` | `any` | let/var | `null` | ✗ |
| `surface` | `any` | let/var | `effect.profile.surfaces[ sampler.source ]` | ✗ |
| `extra` | `any` | let/var | `textureObject.extra` | ✗ |
| `technique` | `any` | let/var | `extra.technique` | ✗ |
| `parameters` | `any` | let/var | `technique.parameters` | ✗ |
| `parameter` | `any` | let/var | `parameters[ key ]` | ✗ |
| `transparent` | `any` | let/var | `parameters[ 'transparent' ]` | ✗ |
| `transparency` | `any` | let/var | `parameters[ 'transparency' ]` | ✗ |
| `color` | `any` | let/var | `transparent.data.color` | ✗ |
| `techniques` | `any` | let/var | `technique.extra.technique` | ✗ |
| `v` | `any` | let/var | `techniques[ k ]` | ✗ |
| `data` | `{ name: any; }` | let/var | `{ name: xml.getAttribute( 'name' ) }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ technique: any; parameters: {}; }` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `camera` | `any` | let/var | `*not shown*` | ✗ |
| `ymag` | `any` | let/var | `data.optics.parameters.ymag` | ✗ |
| `xmag` | `any` | let/var | `data.optics.parameters.xmag` | ✗ |
| `aspectRatio` | `any` | let/var | `data.optics.parameters.aspect_ratio` | ✗ |
| `data` | `any` | let/var | `library.cameras[ id ]` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ technique: any; parameters: { color...` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ color: any; falloffAngle: number; d...` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `light` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `any` | let/var | `library.lights[ id ]` | ✗ |
| `data` | `{ name: any; sources: {}; vertices: {...` | let/var | `{ name: xml.getAttribute( 'name' ), sources: {}, vertices: {}, primitives: [] }` | ✗ |
| `mesh` | `any` | let/var | `getElementsByTagName( xml, 'mesh' )[ 0 ]` | ✗ |
| `child` | `any` | let/var | `mesh.childNodes[ i ]` | ✗ |
| `data` | `{ array: any[]; stride: number; }` | let/var | `{ array: [], stride: 3 }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `accessor` | `any` | let/var | `getElementsByTagName( child, 'accessor' )[ 0 ]` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `primitive` | `{ type: any; material: any; count: nu...` | let/var | `{ type: xml.nodeName, material: xml.getAttribute( 'material' ), count: parseI...` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `inputname` | `any` | let/var | `( set > 0 ? semantic + set : semantic )` | ✗ |
| `build` | `{}` | let/var | `{}` | ✗ |
| `primitive` | `any` | let/var | `primitives[ i ]` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `primitive` | `any` | let/var | `primitives[ i ]` | ✗ |
| `build` | `{}` | let/var | `{}` | ✗ |
| `sources` | `any` | let/var | `data.sources` | ✗ |
| `vertices` | `any` | let/var | `data.vertices` | ✗ |
| `primitives` | `any` | let/var | `data.primitives` | ✗ |
| `primitiveType` | `any` | let/var | `groupedPrimitives[ type ]` | ✗ |
| `build` | `{ data: any; type: any; materialKeys:...` | let/var | `{}` | ✗ |
| `position` | `{ array: any[]; stride: number; }` | let/var | `{ array: [], stride: 0 }` | ✗ |
| `normal` | `{ array: any[]; stride: number; }` | let/var | `{ array: [], stride: 0 }` | ✗ |
| `uv` | `{ array: any[]; stride: number; }` | let/var | `{ array: [], stride: 0 }` | ✗ |
| `uv1` | `{ array: any[]; stride: number; }` | let/var | `{ array: [], stride: 0 }` | ✗ |
| `color` | `{ array: any[]; stride: number; }` | let/var | `{ array: [], stride: 0 }` | ✗ |
| `skinIndex` | `{ array: any[]; stride: number; }` | let/var | `{ array: [], stride: 4 }` | ✗ |
| `skinWeight` | `{ array: any[]; stride: number; }` | let/var | `{ array: [], stride: 4 }` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `materialKeys` | `any[]` | let/var | `[]` | ✗ |
| `start` | `number` | let/var | `0` | ✗ |
| `primitive` | `any` | let/var | `primitives[ p ]` | ✗ |
| `inputs` | `any` | let/var | `primitive.inputs` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `vc` | `any` | let/var | `primitive.vcount[ g ]` | ✗ |
| `input` | `any` | let/var | `inputs[ name ]` | ✗ |
| `id` | `any` | let/var | `vertices[ key ]` | ✗ |
| `prevLength` | `number` | let/var | `position.array.length` | ✗ |
| `count` | `number` | let/var | `( position.array.length - prevLength ) / position.stride` | ✗ |
| `indices` | `any` | let/var | `primitive.p` | ✗ |
| `stride` | `any` | let/var | `primitive.stride` | ✗ |
| `vcount` | `any` | let/var | `primitive.vcount` | ✗ |
| `index` | `number` | let/var | `indices[ i + offset ] * sourceStride` | ✗ |
| `length` | `any` | let/var | `index + sourceStride` | ✗ |
| `startIndex` | `number` | let/var | `array.length - sourceStride - 1` | ✗ |
| `sourceArray` | `any` | let/var | `source.array` | ✗ |
| `sourceStride` | `any` | let/var | `source.stride` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `count` | `any` | let/var | `vcount[ i ]` | ✗ |
| `a` | `number` | let/var | `index + stride * 0` | ✗ |
| `b` | `number` | let/var | `index + stride * 1` | ✗ |
| `c` | `number` | let/var | `index + stride * 2` | ✗ |
| `d` | `number` | let/var | `index + stride * 3` | ✗ |
| `a` | `number` | let/var | `index + stride * 0` | ✗ |
| `b` | `number` | let/var | `index + stride * 1` | ✗ |
| `c` | `number` | let/var | `index + stride * 2` | ✗ |
| `a` | `number` | let/var | `index + stride * 0` | ✗ |
| `b` | `number` | let/var | `index + stride * k` | ✗ |
| `c` | `number` | let/var | `index + stride * ( k + 1 )` | ✗ |
| `data` | `{ name: any; joints: {}; links: any[]; }` | let/var | `{ name: xml.getAttribute( 'name' ) \|\| '', joints: {}, links: [] }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ sid: any; name: any; axis: any; lim...` | let/var | `{ sid: xml.getAttribute( 'sid' ), name: xml.getAttribute( 'name' ) \|\| '', a...` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `max` | `any` | let/var | `child.getElementsByTagName( 'max' )[ 0 ]` | ✗ |
| `min` | `any` | let/var | `child.getElementsByTagName( 'min' )[ 0 ]` | ✗ |
| `data` | `{ sid: any; name: any; attachments: a...` | let/var | `{ sid: xml.getAttribute( 'sid' ), name: xml.getAttribute( 'name' ) \|\| '', a...` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ joint: any; transforms: any[]; link...` | let/var | `{ joint: xml.getAttribute( 'joint' ).split( '/' ).pop(), transforms: [], link...` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ type: any; }` | let/var | `{ type: xml.nodeName }` | ✗ |
| `data` | `{ name: any; rigidBodies: {}; }` | let/var | `{ name: xml.getAttribute( 'name' ) \|\| '', rigidBodies: {} }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ bindJointAxis: any[]; }` | let/var | `{ bindJointAxis: [] }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `data` | `{ target: any; }` | let/var | `{ target: xml.getAttribute( 'target' ).split( '/' ).pop() }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `param` | `any` | let/var | `child.getElementsByTagName( 'param' )[ 0 ]` | ✗ |
| `tmpJointIndex` | `any` | let/var | `data.axis.split( 'inst_' ).pop().split( 'axis' )[ 0 ]` | ✗ |
| `kinematicsModelId` | `string` | let/var | `Object.keys( library.kinematicsModels )[ 0 ]` | ✗ |
| `kinematicsSceneId` | `string` | let/var | `Object.keys( library.kinematicsScenes )[ 0 ]` | ✗ |
| `visualSceneId` | `string` | let/var | `Object.keys( library.visualScenes )[ 0 ]` | ✗ |
| `bindJointAxis` | `any` | let/var | `kinematicsScene.bindJointAxis` | ✗ |
| `jointMap` | `{}` | let/var | `{}` | ✗ |
| `axis` | `any` | let/var | `bindJointAxis[ i ]` | ✗ |
| `parentVisualElement` | `any` | let/var | `targetElement.parentElement` | ✗ |
| `joint` | `any` | let/var | `kinematicsModel.joints[ jointIndex ]` | ✗ |
| `m0` | `any` | let/var | `new Matrix4()` | ✗ |
| `jointData` | `any` | let/var | `jointMap[ jointIndex ]` | ✗ |
| `jointData` | `any` | let/var | `jointMap[ jointIndex ]` | ✗ |
| `joint` | `any` | let/var | `jointData.joint` | ✗ |
| `object` | `any` | let/var | `jointData.object` | ✗ |
| `axis` | `any` | let/var | `joint.axis` | ✗ |
| `transforms` | `any` | let/var | `jointData.transforms` | ✗ |
| `transform` | `any` | let/var | `transforms[ i ]` | ✗ |
| `transforms` | `any[]` | let/var | `[]` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `array` | `any` | let/var | `*not shown*` | ✗ |
| `vector` | `any` | let/var | `*not shown*` | ✗ |
| `element` | `any` | let/var | `elements[ i ]` | ✗ |
| `matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `vector` | `any` | let/var | `new Vector3()` | ✗ |
| `data` | `{ name: any; type: any; id: any; sid:...` | let/var | `{ name: xml.getAttribute( 'name' ) \|\| '', type: xml.getAttribute( 'type' ),...` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `array` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `{ id: any; materials: {}; skeletons: ...` | let/var | `{ id: parseId( xml.getAttribute( 'url' ) ), materials: {}, skeletons: [] }` | ✗ |
| `child` | `any` | let/var | `xml.childNodes[ i ]` | ✗ |
| `instance` | `any` | let/var | `instances[ j ]` | ✗ |
| `boneData` | `any[]` | let/var | `[]` | ✗ |
| `sortedBoneData` | `any[]` | let/var | `[]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `skeleton` | `any` | let/var | `skeletons[ i ]` | ✗ |
| `root` | `any` | let/var | `*not shown*` | ✗ |
| `visualScene` | `any` | let/var | `library.visualScenes[ skeleton ]` | ✗ |
| `children` | `any` | let/var | `visualScene.children` | ✗ |
| `child` | `any` | let/var | `children[ j ]` | ✗ |
| `bones` | `any[]` | let/var | `[]` | ✗ |
| `boneInverses` | `any[]` | let/var | `[]` | ✗ |
| `boneInverse` | `any` | let/var | `*not shown*` | ✗ |
| `joint` | `any` | let/var | `joints[ i ]` | ✗ |
| `objects` | `any[]` | let/var | `[]` | ✗ |
| `matrix` | `any` | let/var | `data.matrix` | ✗ |
| `nodes` | `any` | let/var | `data.nodes` | ✗ |
| `type` | `any` | let/var | `data.type` | ✗ |
| `instanceCameras` | `any` | let/var | `data.instanceCameras` | ✗ |
| `instanceControllers` | `any` | let/var | `data.instanceControllers` | ✗ |
| `instanceLights` | `any` | let/var | `data.instanceLights` | ✗ |
| `instanceGeometries` | `any` | let/var | `data.instanceGeometries` | ✗ |
| `instanceNodes` | `any` | let/var | `data.instanceNodes` | ✗ |
| `instance` | `any` | let/var | `instanceControllers[ i ]` | ✗ |
| `skeletons` | `any` | let/var | `instance.skeletons` | ✗ |
| `joints` | `any` | let/var | `controller.skin.joints` | ✗ |
| `object` | `any` | let/var | `newObjects[ j ]` | ✗ |
| `instance` | `any` | let/var | `instanceGeometries[ i ]` | ✗ |
| `object` | `any` | let/var | `*not shown*` | ✗ |
| `fallbackMaterial` | `any` | let/var | `new MeshBasicMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, color: 0xff00ff } )` | ✗ |
| `materials` | `any[]` | let/var | `[]` | ✗ |
| `id` | `any` | let/var | `instanceMaterials[ keys[ i ] ]` | ✗ |
| `objects` | `any[]` | let/var | `[]` | ✗ |
| `geometry` | `any` | let/var | `geometries[ type ]` | ✗ |
| `material` | `any` | let/var | `materials[ i ]` | ✗ |
| `lineMaterial` | `any` | let/var | `new LineBasicMaterial()` | ✗ |
| `skinning` | `boolean` | let/var | `( geometry.data.attributes.skinIndex !== undefined )` | ✗ |
| `material` | `any` | let/var | `( materials.length === 1 ) ? materials[ 0 ] : materials` | ✗ |
| `object` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `{ name: any; children: any[]; }` | let/var | `{ name: xml.getAttribute( 'name' ), children: [] }` | ✗ |
| `group` | `any` | let/var | `new Group()` | ✗ |
| `children` | `any` | let/var | `data.children` | ✗ |
| `child` | `any` | let/var | `children[ i ]` | ✗ |
| `instance` | `any` | let/var | `getElementsByTagName( xml, 'instance_visual_scene' )[ 0 ]` | ✗ |
| `clips` | `{}` | let/var | `library.clips` | ✗ |
| `tracks` | `any[]` | let/var | `[]` | ✗ |
| `result` | `string` | let/var | `''` | ✗ |
| `stack` | `any[]` | let/var | `[ parserError ]` | ✗ |
| `collada` | `any` | let/var | `getElementsByTagName( xml, 'COLLADA' )[ 0 ]` | ✗ |
| `parserError` | `Element` | let/var | `xml.getElementsByTagName( 'parsererror' )[ 0 ]` | ✗ |
| `errorElement` | `any` | let/var | `getElementsByTagName( parserError, 'div' )[ 0 ]` | ✗ |
| `errorText` | `any` | let/var | `*not shown*` | ✗ |
| `textureLoader` | `any` | let/var | `new TextureLoader( this.manager )` | ✗ |
| `tgaLoader` | `any` | let/var | `*not shown*` | ✗ |
| `tempColor` | `any` | let/var | `new Color()` | ✗ |
| `animations` | `any[]` | let/var | `[]` | ✗ |
| `kinematics` | `{}` | let/var | `{}` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `library` | `{ animations: {}; clips: {}; controll...` | let/var | `{ animations: {}, clips: {}, controllers: {}, images: {}, effects: {}, materi...` | ✗ |


---

## Functions

### `ColladaLoader.load(url: string, onLoad: (arg0: { scene: Group; animations: AnimationClip[]; kinematics: any; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded Collada asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({scene:Group,animations:Array<AnimationClip>,kinematics:Object})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { scene: Group; animations: AnimationClip[]; kinematics: any; }) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `LoaderUtils.extractUrlBase`
- `loader.setPath`
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

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text, path ) );

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

### `ColladaLoader.parse(text: string, path: string): { scene: Group; animations: AnimationClip[]; kinematics: any; }`

**JSDoc:**
```typescript
/**
	 * Parses the given Collada data and returns a result object holding the parsed scene,
	 * an array of animation clips and kinematics.
	 *
	 * @param {string} text - The raw Collada data as a string.
	 * @param {string} path - The asset path.
	 * @return {{scene:Group,animations:Array<AnimationClip>,kinematics:Object}} An object representing the parsed asset.
	 */
```

**Parameters:**

- **`text`** `string`
- **`path`** `string`

**Returns:** `{ scene: Group; animations: AnimationClip[]; kinematics: any; }`

**Calls:**

- `array.push`
- `text.trim().split`
- `parseFloat`
- `parseInt`
- `text.substring`
- `Object.keys`
- `parseAssetUnit`
- `getElementsByTagName`
- `parseAssetUpAxis`
- `xml.hasAttribute`
- `xml.getAttribute`
- `parser`
- `builder`
- `child.getAttribute`
- `parseSource`
- `parseAnimationSampler`
- `parseAnimationChannel`
- `parseAnimation`
- `console.log`
- `MathUtils.generateUUID`
- `parseId`
- `target.split`
- `parts.shift`
- `sid.indexOf`
- `sid.split`
- `indices.shift`
- `indices[ i ].replace`
- `channels.hasOwnProperty`
- `buildAnimationChannel`
- `createKeyframeTracks`
- `getBuild`
- `getNode`
- `node.matrix.clone().transpose`
- `console.warn`
- `prepareAnimationData`
- `keyframes.push`
- `keyframes.sort`
- `transformAnimationData`
- `matrix.fromArray( value ).transpose`
- `matrix.decompose`
- `times.push`
- `positionData.push`
- `quaternionData.push`
- `scaleData.push`
- `tracks.push`
- `createMissingKeyframes`
- `getPrev`
- `getNext`
- `interpolate`
- `data.animations.push`
- `getAnimation`
- `parseSkin`
- `parseFloats`
- `parseJoints`
- `parseVertexWeights`
- `parseInts`
- `buildSkin`
- `vertexSkinData.push`
- `vertexSkinData.sort`
- `build.indices.array.push`
- `build.weights.array.push`
- `new Matrix4().fromArray( data.bindShapeMatrix ).transpose`
- `new Matrix4().identity`
- `new Matrix4().fromArray( inverseSource.array, i * inverseSource.stride ).transpose`
- `build.joints.push`
- `parseEffectProfileCOMMON`
- `parseEffectNewparam`
- `parseEffectTechnique`
- `parseEffectExtra`
- `parseEffectSurface`
- `parseEffectSampler`
- `parseEffectParameters`
- `parseEffectParameter`
- `child.hasAttribute`
- `parseEffectParameterTexture`
- `parseEffectParameterTextureExtra`
- `parseEffectParameterTextureExtraTechnique`
- `child.textContent.toUpperCase`
- `parseEffectExtraTechniqueBump`
- `parseEffectExtraTechnique`
- `image.slice`
- `image.lastIndexOf`
- `extension.toLowerCase`
- `getEffect`
- `getImage`
- `getTextureLoader`
- `loader.load`
- `isEmpty`
- `texture.offset.set`
- `texture.repeat.set`
- `material.color.fromArray`
- `getTexture`
- `material.specular.fromArray`
- `material.emissive.fromArray`
- `ColorManagement.colorSpaceToWorking`
- `parseCameraOptics`
- `parseCameraTechnique`
- `parseCameraParameters`
- `parseLightTechnique`
- `parseLightParameters`
- `new Color().fromArray`
- `Math.sqrt`
- `light.color.copy`
- `parseGeometryVertices`
- `data.primitives.push`
- `parseGeometryPrimitive`
- `parseStrings`
- `accessor.getAttribute`
- `Math.max`
- `build[ primitive.type ].push`
- `groupPrimitives`
- `checkUVCoordinates`
- `buildGeometryType`
- `geometry.addGroup`
- `materialKeys.push`
- `buildGeometryData`
- `uv.array.push`
- `geometry.setAttribute`
- `tempColor.setRGB`
- `pushVector`
- `parseKinematicsTechniqueCommon`
- `parseKinematicsJoint`
- `data.links.push`
- `parseKinematicsLink`
- `parseKinematicsJointParameter`
- `data.axis.fromArray`
- `child.getElementsByTagName`
- `data.attachments.push`
- `parseKinematicsAttachment`
- `data.transforms.push`
- `parseKinematicsTransform`
- `xml.getAttribute( 'joint' ).split( '/' ).pop`
- `data.obj.fromArray( array ).transpose`
- `data.obj.fromArray`
- `MathUtils.degToRad`
- `parsePhysicsRigidBody`
- `parsePhysicsTechniqueCommon`
- `data.bindJointAxis.push`
- `parseKinematicsBindJointAxis`
- `xml.getAttribute( 'target' ).split( '/' ).pop`
- `data.axis.split( 'inst_' ).pop().split`
- `tmpJointIndex.substring`
- `getKinematicsModel`
- `getKinematicsScene`
- `getVisualScene`
- `collada.querySelector`
- `connect`
- `visualElement.getAttribute`
- `visualScene.traverse`
- `buildTransformList`
- `matrix.identity`
- `transform.sid.indexOf`
- `matrix.multiply`
- `m0.makeRotationAxis`
- `m0.makeTranslation`
- `matrix.scale`
- `object.matrix.copy`
- `object.matrix.decompose`
- `new Matrix4().fromArray( array ).transpose`
- `transforms.push`
- `new Vector3().fromArray`
- `xml.getElementsByTagName`
- `element.hasAttribute`
- `element.setAttribute`
- `generateId`
- `data.nodes.push`
- `parseNode`
- `data.instanceCameras.push`
- `data.instanceControllers.push`
- `parseNodeInstance`
- `data.instanceLights.push`
- `data.instanceGeometries.push`
- `data.instanceNodes.push`
- `data.matrix.multiply`
- `matrix.fromArray( array ).transpose`
- `vector.fromArray`
- `matrix.makeTranslation`
- `matrix.makeRotationAxis`
- `data.matrix.scale`
- `hasNode`
- `instance.getAttribute`
- `data.skeletons.push`
- `buildBoneHierarchy`
- `hasVisualScene`
- `console.error`
- `sortedBoneData.push`
- `bones.push`
- `boneInverses.push`
- `root.traverse`
- `boneData.push`
- `objects.push`
- `getCamera`
- `instanceCamera.clone`
- `getController`
- `getGeometry`
- `buildObjects`
- `buildSkeleton`
- `object.bind`
- `object.normalizeSkinWeights`
- `getLight`
- `instanceLight.clone`
- `getNode( instanceNodes[ i ] ).clone`
- `object.add`
- `materials.push`
- `getMaterial`
- `resolveMaterialBinding`
- `lineMaterial.color.copy`
- `prepareNodes`
- `data.children.push`
- `group.add`
- `animations.push`
- `getAnimationClip`
- `stack.shift`
- `stack.push`
- `result.trim`
- `new DOMParser().parseFromString`
- `parserErrorToText`
- `collada.getAttribute`
- `console.debug`
- `parseAsset`
- `textureLoader.setPath( this.resourcePath || path ).setCrossOrigin`
- `tgaLoader.setPath`
- `parseLibrary`
- `buildLibrary`
- `setupAnimations`
- `setupKinematics`
- `parseScene`
- `scene.rotation.set`
- `scene.scale.multiplyScalar`

**Internal Comments:**
```
// Non recursive xml.getElementsByTagName() ... (x2)
// asset
// library
// get
// animation
// hierarchy of related animations (x3)
// since 'id' attributes can be optional, it's necessary to generate a UUID for unique assignment (x5)
// parsing SID Addressing Syntax (x2)
// check selection syntax (x2)
//  member selection access (x3)
// array-access syntax. can be used to express fields in one-dimensional vectors or two-dimensional matrices. (x2)
// the collada spec allows the animation of data in various ways.
// depending on the transform type (matrix, translate, rotate, scale), we execute different logic
// transfer data into a sortable array
// ensure keyframes are sorted by time (x4)
// now we clean up all animation data, so we can use them for keyframe tracks
// array sort function (x2)
// check, if values of a property are missing in our keyframes
// no values at all, so we set a default value
// filling gaps (x3)
// animation clips
// controller
// there is exactly one skin per controller (x4)
// we enhance the 'sources' property of the corresponding geometry with our skin data (x5)
// process skin data for each vertex
// we sort the joints in descending order based on the weights. (x4)
// this ensures, we only proceed the most important joints of the vertex (x4)
// now we provide for each vertex a set of four index and weight values.
// the order of the skin data matches the order of vertices
// setup bind matrix
// process bones and inverse bind matrix data
// image
// effect
// some files have values for wrapU/wrapV which become NaN via parseInt
// material (x2)
// get image
// create texture if image is available
// (x7)
// <transparency> does not exist but <transparent>
// <transparent> does not exist but <transparency>
// handle case if a texture exists but no color
// we do not set an alpha map (see #13792) (x4)
// camera
// light
// geometry
// the following tags inside geometry are not supported yet (see https://github.com/mrdoob/three.js/pull/12606): convex_mesh, spline, brep
// data.sources[ id ] = data.sources[ parseId( getElementsByTagName( child, 'input' )[ 0 ].getAttribute( 'source' ) ) ]; (x4)
// our goal is to create one buffer geometry for a single type of primitives (x2)
// first, we group all primitives by their type (x2)
// second, ensure consistent uv coordinates for each type of primitives (polylist,triangles or lines) (x3)
// third, create a buffer geometry for each type of primitives (x4)
// groups (x2)
// geometry data
// see #3803
// fill missing uv coordinates (x5)
// build geometry
// convert the vertex colors from srgb to linear if present (x2)
// kinematics
// if min is equal to or greater than max, consider the joint static
// calculate middle position (x4)
// physics
// scene
// the result of the following query is an element of type 'translate', 'rotate','scale' or 'matrix' (x2)
// get the parent of the transform element (x2)
// connect the joint of the kinematics model with the element in the visual scene (x3)
// each update, we have to apply all transforms in the correct order
// if there is a connection of the transform node with a joint, apply the joint value
// nodes (x2)
// ensure all node elements have id attributes
// a skeleton can have multiple root bones. collada expresses this
// situation with multiple "skeleton" tags per controller instance
// handle case where the skeleton refers to the visual scene (#13335) (x2)
// sort bone data (the order is defined in the corresponding controller)
// add unprocessed bone data at the end of the list
// setup arrays for skeleton creation (x2)
// setup bone data from visual scene (x4)
// retrieve the boneInverse from the controller data
// Unfortunately, there can be joints in the visual scene that are not part of the (x3)
// corresponding controller. In this case, we have to create a dummy boneInverse matrix (x3)
// for the respective bone. This bone won't affect any vertices, because there are no skin indices (x3)
// and weights defined for it. But we still have to add the bone to the sorted bone list in order to (x3)
// ensure a correct animation of the model. (x3)
// instance cameras
// instance controllers
// instance lights
// instance geometries
// a single geometry instance in collada can lead to multiple object3Ds. (x2)
// this is the case when primitives are combined like triangles and lines (x2)
// instance nodes
// handle case if no materials are defined
// Collada allows to use phong and lambert materials with lines. Replacing these cases with LineBasicMaterial.
// copy compatible properties (x5)
// replace material (x4)
// regard skinning (x2)
// choose between a single or multi materials (material array) (x2)
// now create a specific 3D object (x2)
// visual scenes
// scenes
// if there are animations but no clips, we create a default clip for playback (x2)
// convert the parser error element into text with each child elements text
// separated by new lines.
// Chrome will return parser error with a div in it (x2)
// metadata (x2)
```

<details><summary>Code</summary>

```typescript
parse( text, path ) {

		function getElementsByTagName( xml, name ) {

			// Non recursive xml.getElementsByTagName() ...

			const array = [];
			const childNodes = xml.childNodes;

			for ( let i = 0, l = childNodes.length; i < l; i ++ ) {

				const child = childNodes[ i ];

				if ( child.nodeName === name ) {

					array.push( child );

				}

			}

			return array;

		}

		function parseStrings( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parts[ i ];

			}

			return array;

		}

		function parseFloats( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parseFloat( parts[ i ] );

			}

			return array;

		}

		function parseInts( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parseInt( parts[ i ] );

			}

			return array;

		}

		function parseId( text ) {

			return text.substring( 1 );

		}

		function generateId() {

			return 'three_default_' + ( count ++ );

		}

		function isEmpty( object ) {

			return Object.keys( object ).length === 0;

		}

		// asset

		function parseAsset( xml ) {

			return {
				unit: parseAssetUnit( getElementsByTagName( xml, 'unit' )[ 0 ] ),
				upAxis: parseAssetUpAxis( getElementsByTagName( xml, 'up_axis' )[ 0 ] )
			};

		}

		function parseAssetUnit( xml ) {

			if ( ( xml !== undefined ) && ( xml.hasAttribute( 'meter' ) === true ) ) {

				return parseFloat( xml.getAttribute( 'meter' ) );

			} else {

				return 1; // default 1 meter

			}

		}

		function parseAssetUpAxis( xml ) {

			return xml !== undefined ? xml.textContent : 'Y_UP';

		}

		// library

		function parseLibrary( xml, libraryName, nodeName, parser ) {

			const library = getElementsByTagName( xml, libraryName )[ 0 ];

			if ( library !== undefined ) {

				const elements = getElementsByTagName( library, nodeName );

				for ( let i = 0; i < elements.length; i ++ ) {

					parser( elements[ i ] );

				}

			}

		}

		function buildLibrary( data, builder ) {

			for ( const name in data ) {

				const object = data[ name ];
				object.build = builder( data[ name ] );

			}

		}

		// get

		function getBuild( data, builder ) {

			if ( data.build !== undefined ) return data.build;

			data.build = builder( data );

			return data.build;

		}

		// animation

		function parseAnimation( xml ) {

			const data = {
				sources: {},
				samplers: {},
				channels: {}
			};

			let hasChildren = false;

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let id;

				switch ( child.nodeName ) {

					case 'source':
						id = child.getAttribute( 'id' );
						data.sources[ id ] = parseSource( child );
						break;

					case 'sampler':
						id = child.getAttribute( 'id' );
						data.samplers[ id ] = parseAnimationSampler( child );
						break;

					case 'channel':
						id = child.getAttribute( 'target' );
						data.channels[ id ] = parseAnimationChannel( child );
						break;

					case 'animation':
						// hierarchy of related animations
						parseAnimation( child );
						hasChildren = true;
						break;

					default:
						console.log( child );

				}

			}

			if ( hasChildren === false ) {

				// since 'id' attributes can be optional, it's necessary to generate a UUID for unique assignment

				library.animations[ xml.getAttribute( 'id' ) || MathUtils.generateUUID() ] = data;

			}

		}

		function parseAnimationSampler( xml ) {

			const data = {
				inputs: {},
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const id = parseId( child.getAttribute( 'source' ) );
						const semantic = child.getAttribute( 'semantic' );
						data.inputs[ semantic ] = id;
						break;

				}

			}

			return data;

		}

		function parseAnimationChannel( xml ) {

			const data = {};

			const target = xml.getAttribute( 'target' );

			// parsing SID Addressing Syntax

			let parts = target.split( '/' );

			const id = parts.shift();
			let sid = parts.shift();

			// check selection syntax

			const arraySyntax = ( sid.indexOf( '(' ) !== - 1 );
			const memberSyntax = ( sid.indexOf( '.' ) !== - 1 );

			if ( memberSyntax ) {

				//  member selection access

				parts = sid.split( '.' );
				sid = parts.shift();
				data.member = parts.shift();

			} else if ( arraySyntax ) {

				// array-access syntax. can be used to express fields in one-dimensional vectors or two-dimensional matrices.

				const indices = sid.split( '(' );
				sid = indices.shift();

				for ( let i = 0; i < indices.length; i ++ ) {

					indices[ i ] = parseInt( indices[ i ].replace( /\)/, '' ) );

				}

				data.indices = indices;

			}

			data.id = id;
			data.sid = sid;

			data.arraySyntax = arraySyntax;
			data.memberSyntax = memberSyntax;

			data.sampler = parseId( xml.getAttribute( 'source' ) );

			return data;

		}

		function buildAnimation( data ) {

			const tracks = [];

			const channels = data.channels;
			const samplers = data.samplers;
			const sources = data.sources;

			for ( const target in channels ) {

				if ( channels.hasOwnProperty( target ) ) {

					const channel = channels[ target ];
					const sampler = samplers[ channel.sampler ];

					const inputId = sampler.inputs.INPUT;
					const outputId = sampler.inputs.OUTPUT;

					const inputSource = sources[ inputId ];
					const outputSource = sources[ outputId ];

					const animation = buildAnimationChannel( channel, inputSource, outputSource );

					createKeyframeTracks( animation, tracks );

				}

			}

			return tracks;

		}

		function getAnimation( id ) {

			return getBuild( library.animations[ id ], buildAnimation );

		}

		function buildAnimationChannel( channel, inputSource, outputSource ) {

			const node = library.nodes[ channel.id ];
			const object3D = getNode( node.id );

			const transform = node.transforms[ channel.sid ];
			const defaultMatrix = node.matrix.clone().transpose();

			let time, stride;
			let i, il, j, jl;

			const data = {};

			// the collada spec allows the animation of data in various ways.
			// depending on the transform type (matrix, translate, rotate, scale), we execute different logic

			switch ( transform ) {

				case 'matrix':

					for ( i = 0, il = inputSource.array.length; i < il; i ++ ) {

						time = inputSource.array[ i ];
						stride = i * outputSource.stride;

						if ( data[ time ] === undefined ) data[ time ] = {};

						if ( channel.arraySyntax === true ) {

							const value = outputSource.array[ stride ];
							const index = channel.indices[ 0 ] + 4 * channel.indices[ 1 ];

							data[ time ][ index ] = value;

						} else {

							for ( j = 0, jl = outputSource.stride; j < jl; j ++ ) {

								data[ time ][ j ] = outputSource.array[ stride + j ];

							}

						}

					}

					break;

				case 'translate':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

				case 'rotate':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

				case 'scale':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

			}

			const keyframes = prepareAnimationData( data, defaultMatrix );

			const animation = {
				name: object3D.uuid,
				keyframes: keyframes
			};

			return animation;

		}

		function prepareAnimationData( data, defaultMatrix ) {

			const keyframes = [];

			// transfer data into a sortable array

			for ( const time in data ) {

				keyframes.push( { time: parseFloat( time ), value: data[ time ] } );

			}

			// ensure keyframes are sorted by time

			keyframes.sort( ascending );

			// now we clean up all animation data, so we can use them for keyframe tracks

			for ( let i = 0; i < 16; i ++ ) {

				transformAnimationData( keyframes, i, defaultMatrix.elements[ i ] );

			}

			return keyframes;

			// array sort function

			function ascending( a, b ) {

				return a.time - b.time;

			}

		}

		const position = new Vector3();
		const scale = new Vector3();
		const quaternion = new Quaternion();

		function createKeyframeTracks( animation, tracks ) {

			const keyframes = animation.keyframes;
			const name = animation.name;

			const times = [];
			const positionData = [];
			const quaternionData = [];
			const scaleData = [];

			for ( let i = 0, l = keyframes.length; i < l; i ++ ) {

				const keyframe = keyframes[ i ];

				const time = keyframe.time;
				const value = keyframe.value;

				matrix.fromArray( value ).transpose();
				matrix.decompose( position, quaternion, scale );

				times.push( time );
				positionData.push( position.x, position.y, position.z );
				quaternionData.push( quaternion.x, quaternion.y, quaternion.z, quaternion.w );
				scaleData.push( scale.x, scale.y, scale.z );

			}

			if ( positionData.length > 0 ) tracks.push( new VectorKeyframeTrack( name + '.position', times, positionData ) );
			if ( quaternionData.length > 0 ) tracks.push( new QuaternionKeyframeTrack( name + '.quaternion', times, quaternionData ) );
			if ( scaleData.length > 0 ) tracks.push( new VectorKeyframeTrack( name + '.scale', times, scaleData ) );

			return tracks;

		}

		function transformAnimationData( keyframes, property, defaultValue ) {

			let keyframe;

			let empty = true;
			let i, l;

			// check, if values of a property are missing in our keyframes

			for ( i = 0, l = keyframes.length; i < l; i ++ ) {

				keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] === undefined ) {

					keyframe.value[ property ] = null; // mark as missing

				} else {

					empty = false;

				}

			}

			if ( empty === true ) {

				// no values at all, so we set a default value

				for ( i = 0, l = keyframes.length; i < l; i ++ ) {

					keyframe = keyframes[ i ];

					keyframe.value[ property ] = defaultValue;

				}

			} else {

				// filling gaps

				createMissingKeyframes( keyframes, property );

			}

		}

		function createMissingKeyframes( keyframes, property ) {

			let prev, next;

			for ( let i = 0, l = keyframes.length; i < l; i ++ ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] === null ) {

					prev = getPrev( keyframes, i, property );
					next = getNext( keyframes, i, property );

					if ( prev === null ) {

						keyframe.value[ property ] = next.value[ property ];
						continue;

					}

					if ( next === null ) {

						keyframe.value[ property ] = prev.value[ property ];
						continue;

					}

					interpolate( keyframe, prev, next, property );

				}

			}

		}

		function getPrev( keyframes, i, property ) {

			while ( i >= 0 ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] !== null ) return keyframe;

				i --;

			}

			return null;

		}

		function getNext( keyframes, i, property ) {

			while ( i < keyframes.length ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] !== null ) return keyframe;

				i ++;

			}

			return null;

		}

		function interpolate( key, prev, next, property ) {

			if ( ( next.time - prev.time ) === 0 ) {

				key.value[ property ] = prev.value[ property ];
				return;

			}

			key.value[ property ] = ( ( key.time - prev.time ) * ( next.value[ property ] - prev.value[ property ] ) / ( next.time - prev.time ) ) + prev.value[ property ];

		}

		// animation clips

		function parseAnimationClip( xml ) {

			const data = {
				name: xml.getAttribute( 'id' ) || 'default',
				start: parseFloat( xml.getAttribute( 'start' ) || 0 ),
				end: parseFloat( xml.getAttribute( 'end' ) || 0 ),
				animations: []
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'instance_animation':
						data.animations.push( parseId( child.getAttribute( 'url' ) ) );
						break;

				}

			}

			library.clips[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildAnimationClip( data ) {

			const tracks = [];

			const name = data.name;
			const duration = ( data.end - data.start ) || - 1;
			const animations = data.animations;

			for ( let i = 0, il = animations.length; i < il; i ++ ) {

				const animationTracks = getAnimation( animations[ i ] );

				for ( let j = 0, jl = animationTracks.length; j < jl; j ++ ) {

					tracks.push( animationTracks[ j ] );

				}

			}

			return new AnimationClip( name, duration, tracks );

		}

		function getAnimationClip( id ) {

			return getBuild( library.clips[ id ], buildAnimationClip );

		}

		// controller

		function parseController( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'skin':
						// there is exactly one skin per controller
						data.id = parseId( child.getAttribute( 'source' ) );
						data.skin = parseSkin( child );
						break;

					case 'morph':
						data.id = parseId( child.getAttribute( 'source' ) );
						console.warn( 'THREE.ColladaLoader: Morph target animation not supported yet.' );
						break;

				}

			}

			library.controllers[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseSkin( xml ) {

			const data = {
				sources: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'bind_shape_matrix':
						data.bindShapeMatrix = parseFloats( child.textContent );
						break;

					case 'source':
						const id = child.getAttribute( 'id' );
						data.sources[ id ] = parseSource( child );
						break;

					case 'joints':
						data.joints = parseJoints( child );
						break;

					case 'vertex_weights':
						data.vertexWeights = parseVertexWeights( child );
						break;

				}

			}

			return data;

		}

		function parseJoints( xml ) {

			const data = {
				inputs: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const semantic = child.getAttribute( 'semantic' );
						const id = parseId( child.getAttribute( 'source' ) );
						data.inputs[ semantic ] = id;
						break;

				}

			}

			return data;

		}

		function parseVertexWeights( xml ) {

			const data = {
				inputs: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const semantic = child.getAttribute( 'semantic' );
						const id = parseId( child.getAttribute( 'source' ) );
						const offset = parseInt( child.getAttribute( 'offset' ) );
						data.inputs[ semantic ] = { id: id, offset: offset };
						break;

					case 'vcount':
						data.vcount = parseInts( child.textContent );
						break;

					case 'v':
						data.v = parseInts( child.textContent );
						break;

				}

			}

			return data;

		}

		function buildController( data ) {

			const build = {
				id: data.id
			};

			const geometry = library.geometries[ build.id ];

			if ( data.skin !== undefined ) {

				build.skin = buildSkin( data.skin );

				// we enhance the 'sources' property of the corresponding geometry with our skin data

				geometry.sources.skinIndices = build.skin.indices;
				geometry.sources.skinWeights = build.skin.weights;

			}

			return build;

		}

		function buildSkin( data ) {

			const BONE_LIMIT = 4;

			const build = {
				joints: [], // this must be an array to preserve the joint order
				indices: {
					array: [],
					stride: BONE_LIMIT
				},
				weights: {
					array: [],
					stride: BONE_LIMIT
				}
			};

			const sources = data.sources;
			const vertexWeights = data.vertexWeights;

			const vcount = vertexWeights.vcount;
			const v = vertexWeights.v;
			const jointOffset = vertexWeights.inputs.JOINT.offset;
			const weightOffset = vertexWeights.inputs.WEIGHT.offset;

			const jointSource = data.sources[ data.joints.inputs.JOINT ];
			const inverseSource = data.sources[ data.joints.inputs.INV_BIND_MATRIX ];

			const weights = sources[ vertexWeights.inputs.WEIGHT.id ].array;
			let stride = 0;

			let i, j, l;

			// process skin data for each vertex

			for ( i = 0, l = vcount.length; i < l; i ++ ) {

				const jointCount = vcount[ i ]; // this is the amount of joints that affect a single vertex
				const vertexSkinData = [];

				for ( j = 0; j < jointCount; j ++ ) {

					const skinIndex = v[ stride + jointOffset ];
					const weightId = v[ stride + weightOffset ];
					const skinWeight = weights[ weightId ];

					vertexSkinData.push( { index: skinIndex, weight: skinWeight } );

					stride += 2;

				}

				// we sort the joints in descending order based on the weights.
				// this ensures, we only proceed the most important joints of the vertex

				vertexSkinData.sort( descending );

				// now we provide for each vertex a set of four index and weight values.
				// the order of the skin data matches the order of vertices

				for ( j = 0; j < BONE_LIMIT; j ++ ) {

					const d = vertexSkinData[ j ];

					if ( d !== undefined ) {

						build.indices.array.push( d.index );
						build.weights.array.push( d.weight );

					} else {

						build.indices.array.push( 0 );
						build.weights.array.push( 0 );

					}

				}

			}

			// setup bind matrix

			if ( data.bindShapeMatrix ) {

				build.bindMatrix = new Matrix4().fromArray( data.bindShapeMatrix ).transpose();

			} else {

				build.bindMatrix = new Matrix4().identity();

			}

			// process bones and inverse bind matrix data

			for ( i = 0, l = jointSource.array.length; i < l; i ++ ) {

				const name = jointSource.array[ i ];
				const boneInverse = new Matrix4().fromArray( inverseSource.array, i * inverseSource.stride ).transpose();

				build.joints.push( { name: name, boneInverse: boneInverse } );

			}

			return build;

			// array sort function

			function descending( a, b ) {

				return b.weight - a.weight;

			}

		}

		function getController( id ) {

			return getBuild( library.controllers[ id ], buildController );

		}

		// image

		function parseImage( xml ) {

			const data = {
				init_from: getElementsByTagName( xml, 'init_from' )[ 0 ].textContent
			};

			library.images[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildImage( data ) {

			if ( data.build !== undefined ) return data.build;

			return data.init_from;

		}

		function getImage( id ) {

			const data = library.images[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildImage );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find image with ID:', id );

			return null;

		}

		// effect

		function parseEffect( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'profile_COMMON':
						data.profile = parseEffectProfileCOMMON( child );
						break;

				}

			}

			library.effects[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseEffectProfileCOMMON( xml ) {

			const data = {
				surfaces: {},
				samplers: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'newparam':
						parseEffectNewparam( child, data );
						break;

					case 'technique':
						data.technique = parseEffectTechnique( child );
						break;

					case 'extra':
						data.extra = parseEffectExtra( child );
						break;

				}

			}

			return data;

		}

		function parseEffectNewparam( xml, data ) {

			const sid = xml.getAttribute( 'sid' );

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'surface':
						data.surfaces[ sid ] = parseEffectSurface( child );
						break;

					case 'sampler2D':
						data.samplers[ sid ] = parseEffectSampler( child );
						break;

				}

			}

		}

		function parseEffectSurface( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'init_from':
						data.init_from = child.textContent;
						break;

				}

			}

			return data;

		}

		function parseEffectSampler( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'source':
						data.source = child.textContent;
						break;

				}

			}

			return data;

		}

		function parseEffectTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'constant':
					case 'lambert':
					case 'blinn':
					case 'phong':
						data.type = child.nodeName;
						data.parameters = parseEffectParameters( child );
						break;

					case 'extra':
						data.extra = parseEffectExtra( child );
						break;

				}

			}

			return data;

		}

		function parseEffectParameters( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'emission':
					case 'diffuse':
					case 'specular':
					case 'bump':
					case 'ambient':
					case 'shininess':
					case 'transparency':
						data[ child.nodeName ] = parseEffectParameter( child );
						break;
					case 'transparent':
						data[ child.nodeName ] = {
							opaque: child.hasAttribute( 'opaque' ) ? child.getAttribute( 'opaque' ) : 'A_ONE',
							data: parseEffectParameter( child )
						};
						break;

				}

			}

			return data;

		}

		function parseEffectParameter( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'color':
						data[ child.nodeName ] = parseFloats( child.textContent );
						break;

					case 'float':
						data[ child.nodeName ] = parseFloat( child.textContent );
						break;

					case 'texture':
						data[ child.nodeName ] = { id: child.getAttribute( 'texture' ), extra: parseEffectParameterTexture( child ) };
						break;

				}

			}

			return data;

		}

		function parseEffectParameterTexture( xml ) {

			const data = {
				technique: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'extra':
						parseEffectParameterTextureExtra( child, data );
						break;

				}

			}

			return data;

		}

		function parseEffectParameterTextureExtra( xml, data ) {

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique':
						parseEffectParameterTextureExtraTechnique( child, data );
						break;

				}

			}

		}

		function parseEffectParameterTextureExtraTechnique( xml, data ) {

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'repeatU':
					case 'repeatV':
					case 'offsetU':
					case 'offsetV':
						data.technique[ child.nodeName ] = parseFloat( child.textContent );
						break;

					case 'wrapU':
					case 'wrapV':

						// some files have values for wrapU/wrapV which become NaN via parseInt

						if ( child.textContent.toUpperCase() === 'TRUE' ) {

							data.technique[ child.nodeName ] = 1;

						} else if ( child.textContent.toUpperCase() === 'FALSE' ) {

							data.technique[ child.nodeName ] = 0;

						} else {

							data.technique[ child.nodeName ] = parseInt( child.textContent );

						}

						break;

					case 'bump':
						data[ child.nodeName ] = parseEffectExtraTechniqueBump( child );
						break;

				}

			}

		}

		function parseEffectExtra( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique':
						data.technique = parseEffectExtraTechnique( child );
						break;

				}

			}

			return data;

		}

		function parseEffectExtraTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'double_sided':
						data[ child.nodeName ] = parseInt( child.textContent );
						break;

					case 'bump':
						data[ child.nodeName ] = parseEffectExtraTechniqueBump( child );
						break;

				}

			}

			return data;

		}

		function parseEffectExtraTechniqueBump( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'texture':
						data[ child.nodeName ] = { id: child.getAttribute( 'texture' ), texcoord: child.getAttribute( 'texcoord' ), extra: parseEffectParameterTexture( child ) };
						break;

				}

			}

			return data;

		}

		function buildEffect( data ) {

			return data;

		}

		function getEffect( id ) {

			return getBuild( library.effects[ id ], buildEffect );

		}

		// material

		function parseMaterial( xml ) {

			const data = {
				name: xml.getAttribute( 'name' )
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'instance_effect':
						data.url = parseId( child.getAttribute( 'url' ) );
						break;

				}

			}

			library.materials[ xml.getAttribute( 'id' ) ] = data;

		}

		function getTextureLoader( image ) {

			let loader;

			let extension = image.slice( ( image.lastIndexOf( '.' ) - 1 >>> 0 ) + 2 ); // http://www.jstips.co/en/javascript/get-file-extension/
			extension = extension.toLowerCase();

			switch ( extension ) {

				case 'tga':
					loader = tgaLoader;
					break;

				default:
					loader = textureLoader;

			}

			return loader;

		}

		function buildMaterial( data ) {

			const effect = getEffect( data.url );
			const technique = effect.profile.technique;

			let material;

			switch ( technique.type ) {

				case 'phong':
				case 'blinn':
					material = new MeshPhongMaterial();
					break;

				case 'lambert':
					material = new MeshLambertMaterial();
					break;

				default:
					material = new MeshBasicMaterial();
					break;

			}

			material.name = data.name || '';

			function getTexture( textureObject, colorSpace = null ) {

				const sampler = effect.profile.samplers[ textureObject.id ];
				let image = null;

				// get image

				if ( sampler !== undefined ) {

					const surface = effect.profile.surfaces[ sampler.source ];
					image = getImage( surface.init_from );

				} else {

					console.warn( 'THREE.ColladaLoader: Undefined sampler. Access image directly (see #12530).' );
					image = getImage( textureObject.id );

				}

				// create texture if image is available

				if ( image !== null ) {

					const loader = getTextureLoader( image );

					if ( loader !== undefined ) {

						const texture = loader.load( image );

						const extra = textureObject.extra;

						if ( extra !== undefined && extra.technique !== undefined && isEmpty( extra.technique ) === false ) {

							const technique = extra.technique;

							texture.wrapS = technique.wrapU ? RepeatWrapping : ClampToEdgeWrapping;
							texture.wrapT = technique.wrapV ? RepeatWrapping : ClampToEdgeWrapping;

							texture.offset.set( technique.offsetU || 0, technique.offsetV || 0 );
							texture.repeat.set( technique.repeatU || 1, technique.repeatV || 1 );

						} else {

							texture.wrapS = RepeatWrapping;
							texture.wrapT = RepeatWrapping;

						}

						if ( colorSpace !== null ) {

							texture.colorSpace = colorSpace;

						}

						return texture;

					} else {

						console.warn( 'THREE.ColladaLoader: Loader for texture %s not found.', image );

						return null;

					}

				} else {

					console.warn( 'THREE.ColladaLoader: Couldn\'t create texture with ID:', textureObject.id );

					return null;

				}

			}

			const parameters = technique.parameters;

			for ( const key in parameters ) {

				const parameter = parameters[ key ];

				switch ( key ) {

					case 'diffuse':
						if ( parameter.color ) material.color.fromArray( parameter.color );
						if ( parameter.texture ) material.map = getTexture( parameter.texture, SRGBColorSpace );
						break;
					case 'specular':
						if ( parameter.color && material.specular ) material.specular.fromArray( parameter.color );
						if ( parameter.texture ) material.specularMap = getTexture( parameter.texture );
						break;
					case 'bump':
						if ( parameter.texture ) material.normalMap = getTexture( parameter.texture );
						break;
					case 'ambient':
						if ( parameter.texture ) material.lightMap = getTexture( parameter.texture, SRGBColorSpace );
						break;
					case 'shininess':
						if ( parameter.float && material.shininess ) material.shininess = parameter.float;
						break;
					case 'emission':
						if ( parameter.color && material.emissive ) material.emissive.fromArray( parameter.color );
						if ( parameter.texture ) material.emissiveMap = getTexture( parameter.texture, SRGBColorSpace );
						break;

				}

			}

			ColorManagement.colorSpaceToWorking( material.color, SRGBColorSpace );
			if ( material.specular ) ColorManagement.colorSpaceToWorking( material.specular, SRGBColorSpace );
			if ( material.emissive ) ColorManagement.colorSpaceToWorking( material.emissive, SRGBColorSpace );

			//

			let transparent = parameters[ 'transparent' ];
			let transparency = parameters[ 'transparency' ];

			// <transparency> does not exist but <transparent>

			if ( transparency === undefined && transparent ) {

				transparency = {
					float: 1
				};

			}

			// <transparent> does not exist but <transparency>

			if ( transparent === undefined && transparency ) {

				transparent = {
					opaque: 'A_ONE',
					data: {
						color: [ 1, 1, 1, 1 ]
					} };

			}

			if ( transparent && transparency ) {

				// handle case if a texture exists but no color

				if ( transparent.data.texture ) {

					// we do not set an alpha map (see #13792)

					material.transparent = true;

				} else {

					const color = transparent.data.color;

					switch ( transparent.opaque ) {

						case 'A_ONE':
							material.opacity = color[ 3 ] * transparency.float;
							break;
						case 'RGB_ZERO':
							material.opacity = 1 - ( color[ 0 ] * transparency.float );
							break;
						case 'A_ZERO':
							material.opacity = 1 - ( color[ 3 ] * transparency.float );
							break;
						case 'RGB_ONE':
							material.opacity = color[ 0 ] * transparency.float;
							break;
						default:
							console.warn( 'THREE.ColladaLoader: Invalid opaque type "%s" of transparent tag.', transparent.opaque );

					}

					if ( material.opacity < 1 ) material.transparent = true;

				}

			}

			//


			if ( technique.extra !== undefined && technique.extra.technique !== undefined ) {

				const techniques = technique.extra.technique;

				for ( const k in techniques ) {

					const v = techniques[ k ];

					switch ( k ) {

						case 'double_sided':
							material.side = ( v === 1 ? DoubleSide : FrontSide );
							break;

						case 'bump':
							material.normalMap = getTexture( v.texture );
							material.normalScale = new Vector2( 1, 1 );
							break;

					}

				}

			}

			return material;

		}

		function getMaterial( id ) {

			return getBuild( library.materials[ id ], buildMaterial );

		}

		// camera

		function parseCamera( xml ) {

			const data = {
				name: xml.getAttribute( 'name' )
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'optics':
						data.optics = parseCameraOptics( child );
						break;

				}

			}

			library.cameras[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseCameraOptics( xml ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'technique_common':
						return parseCameraTechnique( child );

				}

			}

			return {};

		}

		function parseCameraTechnique( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'perspective':
					case 'orthographic':

						data.technique = child.nodeName;
						data.parameters = parseCameraParameters( child );

						break;

				}

			}

			return data;

		}

		function parseCameraParameters( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'xfov':
					case 'yfov':
					case 'xmag':
					case 'ymag':
					case 'znear':
					case 'zfar':
					case 'aspect_ratio':
						data[ child.nodeName ] = parseFloat( child.textContent );
						break;

				}

			}

			return data;

		}

		function buildCamera( data ) {

			let camera;

			switch ( data.optics.technique ) {

				case 'perspective':
					camera = new PerspectiveCamera(
						data.optics.parameters.yfov,
						data.optics.parameters.aspect_ratio,
						data.optics.parameters.znear,
						data.optics.parameters.zfar
					);
					break;

				case 'orthographic':
					let ymag = data.optics.parameters.ymag;
					let xmag = data.optics.parameters.xmag;
					const aspectRatio = data.optics.parameters.aspect_ratio;

					xmag = ( xmag === undefined ) ? ( ymag * aspectRatio ) : xmag;
					ymag = ( ymag === undefined ) ? ( xmag / aspectRatio ) : ymag;

					xmag *= 0.5;
					ymag *= 0.5;

					camera = new OrthographicCamera(
						- xmag, xmag, ymag, - ymag, // left, right, top, bottom
						data.optics.parameters.znear,
						data.optics.parameters.zfar
					);
					break;

				default:
					camera = new PerspectiveCamera();
					break;

			}

			camera.name = data.name || '';

			return camera;

		}

		function getCamera( id ) {

			const data = library.cameras[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildCamera );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find camera with ID:', id );

			return null;

		}

		// light

		function parseLight( xml ) {

			let data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						data = parseLightTechnique( child );
						break;

				}

			}

			library.lights[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseLightTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'directional':
					case 'point':
					case 'spot':
					case 'ambient':

						data.technique = child.nodeName;
						data.parameters = parseLightParameters( child );

				}

			}

			return data;

		}

		function parseLightParameters( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'color':
						const array = parseFloats( child.textContent );
						data.color = new Color().fromArray( array );
						ColorManagement.colorSpaceToWorking( data.color, SRGBColorSpace );
						break;

					case 'falloff_angle':
						data.falloffAngle = parseFloat( child.textContent );
						break;

					case 'quadratic_attenuation':
						const f = parseFloat( child.textContent );
						data.distance = f ? Math.sqrt( 1 / f ) : 0;
						break;

				}

			}

			return data;

		}

		function buildLight( data ) {

			let light;

			switch ( data.technique ) {

				case 'directional':
					light = new DirectionalLight();
					break;

				case 'point':
					light = new PointLight();
					break;

				case 'spot':
					light = new SpotLight();
					break;

				case 'ambient':
					light = new AmbientLight();
					break;

			}

			if ( data.parameters.color ) light.color.copy( data.parameters.color );
			if ( data.parameters.distance ) light.distance = data.parameters.distance;

			return light;

		}

		function getLight( id ) {

			const data = library.lights[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildLight );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find light with ID:', id );

			return null;

		}

		// geometry

		function parseGeometry( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ),
				sources: {},
				vertices: {},
				primitives: []
			};

			const mesh = getElementsByTagName( xml, 'mesh' )[ 0 ];

			// the following tags inside geometry are not supported yet (see https://github.com/mrdoob/three.js/pull/12606): convex_mesh, spline, brep
			if ( mesh === undefined ) return;

			for ( let i = 0; i < mesh.childNodes.length; i ++ ) {

				const child = mesh.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				const id = child.getAttribute( 'id' );

				switch ( child.nodeName ) {

					case 'source':
						data.sources[ id ] = parseSource( child );
						break;

					case 'vertices':
						// data.sources[ id ] = data.sources[ parseId( getElementsByTagName( child, 'input' )[ 0 ].getAttribute( 'source' ) ) ];
						data.vertices = parseGeometryVertices( child );
						break;

					case 'polygons':
						console.warn( 'THREE.ColladaLoader: Unsupported primitive type: ', child.nodeName );
						break;

					case 'lines':
					case 'linestrips':
					case 'polylist':
					case 'triangles':
						data.primitives.push( parseGeometryPrimitive( child ) );
						break;

					default:
						console.log( child );

				}

			}

			library.geometries[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseSource( xml ) {

			const data = {
				array: [],
				stride: 3
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'float_array':
						data.array = parseFloats( child.textContent );
						break;

					case 'Name_array':
						data.array = parseStrings( child.textContent );
						break;

					case 'technique_common':
						const accessor = getElementsByTagName( child, 'accessor' )[ 0 ];

						if ( accessor !== undefined ) {

							data.stride = parseInt( accessor.getAttribute( 'stride' ) );

						}

						break;

				}

			}

			return data;

		}

		function parseGeometryVertices( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				data[ child.getAttribute( 'semantic' ) ] = parseId( child.getAttribute( 'source' ) );

			}

			return data;

		}

		function parseGeometryPrimitive( xml ) {

			const primitive = {
				type: xml.nodeName,
				material: xml.getAttribute( 'material' ),
				count: parseInt( xml.getAttribute( 'count' ) ),
				inputs: {},
				stride: 0,
				hasUV: false
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const id = parseId( child.getAttribute( 'source' ) );
						const semantic = child.getAttribute( 'semantic' );
						const offset = parseInt( child.getAttribute( 'offset' ) );
						const set = parseInt( child.getAttribute( 'set' ) );
						const inputname = ( set > 0 ? semantic + set : semantic );
						primitive.inputs[ inputname ] = { id: id, offset: offset };
						primitive.stride = Math.max( primitive.stride, offset + 1 );
						if ( semantic === 'TEXCOORD' ) primitive.hasUV = true;
						break;

					case 'vcount':
						primitive.vcount = parseInts( child.textContent );
						break;

					case 'p':
						primitive.p = parseInts( child.textContent );
						break;

				}

			}

			return primitive;

		}

		function groupPrimitives( primitives ) {

			const build = {};

			for ( let i = 0; i < primitives.length; i ++ ) {

				const primitive = primitives[ i ];

				if ( build[ primitive.type ] === undefined ) build[ primitive.type ] = [];

				build[ primitive.type ].push( primitive );

			}

			return build;

		}

		function checkUVCoordinates( primitives ) {

			let count = 0;

			for ( let i = 0, l = primitives.length; i < l; i ++ ) {

				const primitive = primitives[ i ];

				if ( primitive.hasUV === true ) {

					count ++;

				}

			}

			if ( count > 0 && count < primitives.length ) {

				primitives.uvsNeedsFix = true;

			}

		}

		function buildGeometry( data ) {

			const build = {};

			const sources = data.sources;
			const vertices = data.vertices;
			const primitives = data.primitives;

			if ( primitives.length === 0 ) return {};

			// our goal is to create one buffer geometry for a single type of primitives
			// first, we group all primitives by their type

			const groupedPrimitives = groupPrimitives( primitives );

			for ( const type in groupedPrimitives ) {

				const primitiveType = groupedPrimitives[ type ];

				// second, ensure consistent uv coordinates for each type of primitives (polylist,triangles or lines)

				checkUVCoordinates( primitiveType );

				// third, create a buffer geometry for each type of primitives

				build[ type ] = buildGeometryType( primitiveType, sources, vertices );

			}

			return build;

		}

		function buildGeometryType( primitives, sources, vertices ) {

			const build = {};

			const position = { array: [], stride: 0 };
			const normal = { array: [], stride: 0 };
			const uv = { array: [], stride: 0 };
			const uv1 = { array: [], stride: 0 };
			const color = { array: [], stride: 0 };

			const skinIndex = { array: [], stride: 4 };
			const skinWeight = { array: [], stride: 4 };

			const geometry = new BufferGeometry();

			const materialKeys = [];

			let start = 0;

			for ( let p = 0; p < primitives.length; p ++ ) {

				const primitive = primitives[ p ];
				const inputs = primitive.inputs;

				// groups

				let count = 0;

				switch ( primitive.type ) {

					case 'lines':
					case 'linestrips':
						count = primitive.count * 2;
						break;

					case 'triangles':
						count = primitive.count * 3;
						break;

					case 'polylist':

						for ( let g = 0; g < primitive.count; g ++ ) {

							const vc = primitive.vcount[ g ];

							switch ( vc ) {

								case 3:
									count += 3; // single triangle
									break;

								case 4:
									count += 6; // quad, subdivided into two triangles
									break;

								default:
									count += ( vc - 2 ) * 3; // polylist with more than four vertices
									break;

							}

						}

						break;

					default:
						console.warn( 'THREE.ColladaLoader: Unknown primitive type:', primitive.type );

				}

				geometry.addGroup( start, count, p );
				start += count;

				// material

				if ( primitive.material ) {

					materialKeys.push( primitive.material );

				}

				// geometry data

				for ( const name in inputs ) {

					const input = inputs[ name ];

					switch ( name )	{

						case 'VERTEX':
							for ( const key in vertices ) {

								const id = vertices[ key ];

								switch ( key ) {

									case 'POSITION':
										const prevLength = position.array.length;
										buildGeometryData( primitive, sources[ id ], input.offset, position.array );
										position.stride = sources[ id ].stride;

										if ( sources.skinWeights && sources.skinIndices ) {

											buildGeometryData( primitive, sources.skinIndices, input.offset, skinIndex.array );
											buildGeometryData( primitive, sources.skinWeights, input.offset, skinWeight.array );

										}

										// see #3803

										if ( primitive.hasUV === false && primitives.uvsNeedsFix === true ) {

											const count = ( position.array.length - prevLength ) / position.stride;

											for ( let i = 0; i < count; i ++ ) {

												// fill missing uv coordinates

												uv.array.push( 0, 0 );

											}

										}

										break;

									case 'NORMAL':
										buildGeometryData( primitive, sources[ id ], input.offset, normal.array );
										normal.stride = sources[ id ].stride;
										break;

									case 'COLOR':
										buildGeometryData( primitive, sources[ id ], input.offset, color.array );
										color.stride = sources[ id ].stride;
										break;

									case 'TEXCOORD':
										buildGeometryData( primitive, sources[ id ], input.offset, uv.array );
										uv.stride = sources[ id ].stride;
										break;

									case 'TEXCOORD1':
										buildGeometryData( primitive, sources[ id ], input.offset, uv1.array );
										uv.stride = sources[ id ].stride;
										break;

									default:
										console.warn( 'THREE.ColladaLoader: Semantic "%s" not handled in geometry build process.', key );

								}

							}

							break;

						case 'NORMAL':
							buildGeometryData( primitive, sources[ input.id ], input.offset, normal.array );
							normal.stride = sources[ input.id ].stride;
							break;

						case 'COLOR':
							buildGeometryData( primitive, sources[ input.id ], input.offset, color.array, true );
							color.stride = sources[ input.id ].stride;
							break;

						case 'TEXCOORD':
							buildGeometryData( primitive, sources[ input.id ], input.offset, uv.array );
							uv.stride = sources[ input.id ].stride;
							break;

						case 'TEXCOORD1':
							buildGeometryData( primitive, sources[ input.id ], input.offset, uv1.array );
							uv1.stride = sources[ input.id ].stride;
							break;

					}

				}

			}

			// build geometry

			if ( position.array.length > 0 ) geometry.setAttribute( 'position', new Float32BufferAttribute( position.array, position.stride ) );
			if ( normal.array.length > 0 ) geometry.setAttribute( 'normal', new Float32BufferAttribute( normal.array, normal.stride ) );
			if ( color.array.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( color.array, color.stride ) );
			if ( uv.array.length > 0 ) geometry.setAttribute( 'uv', new Float32BufferAttribute( uv.array, uv.stride ) );
			if ( uv1.array.length > 0 ) geometry.setAttribute( 'uv1', new Float32BufferAttribute( uv1.array, uv1.stride ) );

			if ( skinIndex.array.length > 0 ) geometry.setAttribute( 'skinIndex', new Float32BufferAttribute( skinIndex.array, skinIndex.stride ) );
			if ( skinWeight.array.length > 0 ) geometry.setAttribute( 'skinWeight', new Float32BufferAttribute( skinWeight.array, skinWeight.stride ) );

			build.data = geometry;
			build.type = primitives[ 0 ].type;
			build.materialKeys = materialKeys;

			return build;

		}

		function buildGeometryData( primitive, source, offset, array, isColor = false ) {

			const indices = primitive.p;
			const stride = primitive.stride;
			const vcount = primitive.vcount;

			function pushVector( i ) {

				let index = indices[ i + offset ] * sourceStride;
				const length = index + sourceStride;

				for ( ; index < length; index ++ ) {

					array.push( sourceArray[ index ] );

				}

				if ( isColor ) {

					// convert the vertex colors from srgb to linear if present
					const startIndex = array.length - sourceStride - 1;
					tempColor.setRGB(
						array[ startIndex + 0 ],
						array[ startIndex + 1 ],
						array[ startIndex + 2 ],
						SRGBColorSpace
					);

					array[ startIndex + 0 ] = tempColor.r;
					array[ startIndex + 1 ] = tempColor.g;
					array[ startIndex + 2 ] = tempColor.b;

				}

			}

			const sourceArray = source.array;
			const sourceStride = source.stride;

			if ( primitive.vcount !== undefined ) {

				let index = 0;

				for ( let i = 0, l = vcount.length; i < l; i ++ ) {

					const count = vcount[ i ];

					if ( count === 4 ) {

						const a = index + stride * 0;
						const b = index + stride * 1;
						const c = index + stride * 2;
						const d = index + stride * 3;

						pushVector( a ); pushVector( b ); pushVector( d );
						pushVector( b ); pushVector( c ); pushVector( d );

					} else if ( count === 3 ) {

						const a = index + stride * 0;
						const b = index + stride * 1;
						const c = index + stride * 2;

						pushVector( a ); pushVector( b ); pushVector( c );

					} else if ( count > 4 ) {

						for ( let k = 1, kl = ( count - 2 ); k <= kl; k ++ ) {

							const a = index + stride * 0;
							const b = index + stride * k;
							const c = index + stride * ( k + 1 );

							pushVector( a ); pushVector( b ); pushVector( c );

						}

					}

					index += stride * count;

				}

			} else {

				for ( let i = 0, l = indices.length; i < l; i += stride ) {

					pushVector( i );

				}

			}

		}

		function getGeometry( id ) {

			return getBuild( library.geometries[ id ], buildGeometry );

		}

		// kinematics

		function parseKinematicsModel( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				joints: {},
				links: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						parseKinematicsTechniqueCommon( child, data );
						break;

				}

			}

			library.kinematicsModels[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildKinematicsModel( data ) {

			if ( data.build !== undefined ) return data.build;

			return data;

		}

		function getKinematicsModel( id ) {

			return getBuild( library.kinematicsModels[ id ], buildKinematicsModel );

		}

		function parseKinematicsTechniqueCommon( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'joint':
						data.joints[ child.getAttribute( 'sid' ) ] = parseKinematicsJoint( child );
						break;

					case 'link':
						data.links.push( parseKinematicsLink( child ) );
						break;

				}

			}

		}

		function parseKinematicsJoint( xml ) {

			let data;

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'prismatic':
					case 'revolute':
						data = parseKinematicsJointParameter( child );
						break;

				}

			}

			return data;

		}

		function parseKinematicsJointParameter( xml ) {

			const data = {
				sid: xml.getAttribute( 'sid' ),
				name: xml.getAttribute( 'name' ) || '',
				axis: new Vector3(),
				limits: {
					min: 0,
					max: 0
				},
				type: xml.nodeName,
				static: false,
				zeroPosition: 0,
				middlePosition: 0
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'axis':
						const array = parseFloats( child.textContent );
						data.axis.fromArray( array );
						break;
					case 'limits':
						const max = child.getElementsByTagName( 'max' )[ 0 ];
						const min = child.getElementsByTagName( 'min' )[ 0 ];

						data.limits.max = parseFloat( max.textContent );
						data.limits.min = parseFloat( min.textContent );
						break;

				}

			}

			// if min is equal to or greater than max, consider the joint static

			if ( data.limits.min >= data.limits.max ) {

				data.static = true;

			}

			// calculate middle position

			data.middlePosition = ( data.limits.min + data.limits.max ) / 2.0;

			return data;

		}

		function parseKinematicsLink( xml ) {

			const data = {
				sid: xml.getAttribute( 'sid' ),
				name: xml.getAttribute( 'name' ) || '',
				attachments: [],
				transforms: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'attachment_full':
						data.attachments.push( parseKinematicsAttachment( child ) );
						break;

					case 'matrix':
					case 'translate':
					case 'rotate':
						data.transforms.push( parseKinematicsTransform( child ) );
						break;

				}

			}

			return data;

		}

		function parseKinematicsAttachment( xml ) {

			const data = {
				joint: xml.getAttribute( 'joint' ).split( '/' ).pop(),
				transforms: [],
				links: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'link':
						data.links.push( parseKinematicsLink( child ) );
						break;

					case 'matrix':
					case 'translate':
					case 'rotate':
						data.transforms.push( parseKinematicsTransform( child ) );
						break;

				}

			}

			return data;

		}

		function parseKinematicsTransform( xml ) {

			const data = {
				type: xml.nodeName
			};

			const array = parseFloats( xml.textContent );

			switch ( data.type ) {

				case 'matrix':
					data.obj = new Matrix4();
					data.obj.fromArray( array ).transpose();
					break;

				case 'translate':
					data.obj = new Vector3();
					data.obj.fromArray( array );
					break;

				case 'rotate':
					data.obj = new Vector3();
					data.obj.fromArray( array );
					data.angle = MathUtils.degToRad( array[ 3 ] );
					break;

			}

			return data;

		}

		// physics

		function parsePhysicsModel( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				rigidBodies: {}
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'rigid_body':
						data.rigidBodies[ child.getAttribute( 'name' ) ] = {};
						parsePhysicsRigidBody( child, data.rigidBodies[ child.getAttribute( 'name' ) ] );
						break;

				}

			}

			library.physicsModels[ xml.getAttribute( 'id' ) ] = data;

		}

		function parsePhysicsRigidBody( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						parsePhysicsTechniqueCommon( child, data );
						break;

				}

			}

		}

		function parsePhysicsTechniqueCommon( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'inertia':
						data.inertia = parseFloats( child.textContent );
						break;

					case 'mass':
						data.mass = parseFloats( child.textContent )[ 0 ];
						break;

				}

			}

		}

		// scene

		function parseKinematicsScene( xml ) {

			const data = {
				bindJointAxis: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'bind_joint_axis':
						data.bindJointAxis.push( parseKinematicsBindJointAxis( child ) );
						break;

				}

			}

			library.kinematicsScenes[ parseId( xml.getAttribute( 'url' ) ) ] = data;

		}

		function parseKinematicsBindJointAxis( xml ) {

			const data = {
				target: xml.getAttribute( 'target' ).split( '/' ).pop()
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'axis':
						const param = child.getElementsByTagName( 'param' )[ 0 ];
						data.axis = param.textContent;
						const tmpJointIndex = data.axis.split( 'inst_' ).pop().split( 'axis' )[ 0 ];
						data.jointIndex = tmpJointIndex.substring( 0, tmpJointIndex.length - 1 );
						break;

				}

			}

			return data;

		}

		function buildKinematicsScene( data ) {

			if ( data.build !== undefined ) return data.build;

			return data;

		}

		function getKinematicsScene( id ) {

			return getBuild( library.kinematicsScenes[ id ], buildKinematicsScene );

		}

		function setupKinematics() {

			const kinematicsModelId = Object.keys( library.kinematicsModels )[ 0 ];
			const kinematicsSceneId = Object.keys( library.kinematicsScenes )[ 0 ];
			const visualSceneId = Object.keys( library.visualScenes )[ 0 ];

			if ( kinematicsModelId === undefined || kinematicsSceneId === undefined ) return;

			const kinematicsModel = getKinematicsModel( kinematicsModelId );
			const kinematicsScene = getKinematicsScene( kinematicsSceneId );
			const visualScene = getVisualScene( visualSceneId );

			const bindJointAxis = kinematicsScene.bindJointAxis;
			const jointMap = {};

			for ( let i = 0, l = bindJointAxis.length; i < l; i ++ ) {

				const axis = bindJointAxis[ i ];

				// the result of the following query is an element of type 'translate', 'rotate','scale' or 'matrix'

				const targetElement = collada.querySelector( '[sid="' + axis.target + '"]' );

				if ( targetElement ) {

					// get the parent of the transform element

					const parentVisualElement = targetElement.parentElement;

					// connect the joint of the kinematics model with the element in the visual scene

					connect( axis.jointIndex, parentVisualElement );

				}

			}

			function connect( jointIndex, visualElement ) {

				const visualElementName = visualElement.getAttribute( 'name' );
				const joint = kinematicsModel.joints[ jointIndex ];

				visualScene.traverse( function ( object ) {

					if ( object.name === visualElementName ) {

						jointMap[ jointIndex ] = {
							object: object,
							transforms: buildTransformList( visualElement ),
							joint: joint,
							position: joint.zeroPosition
						};

					}

				} );

			}

			const m0 = new Matrix4();

			kinematics = {

				joints: kinematicsModel && kinematicsModel.joints,

				getJointValue: function ( jointIndex ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						return jointData.position;

					} else {

						console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' doesn\'t exist.' );

					}

				},

				setJointValue: function ( jointIndex, value ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						const joint = jointData.joint;

						if ( value > joint.limits.max || value < joint.limits.min ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' value ' + value + ' outside of limits (min: ' + joint.limits.min + ', max: ' + joint.limits.max + ').' );

						} else if ( joint.static ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' is static.' );

						} else {

							const object = jointData.object;
							const axis = joint.axis;
							const transforms = jointData.transforms;

							matrix.identity();

							// each update, we have to apply all transforms in the correct order

							for ( let i = 0; i < transforms.length; i ++ ) {

								const transform = transforms[ i ];

								// if there is a connection of the transform node with a joint, apply the joint value

								if ( transform.sid && transform.sid.indexOf( jointIndex ) !== - 1 ) {

									switch ( joint.type ) {

										case 'revolute':
											matrix.multiply( m0.makeRotationAxis( axis, MathUtils.degToRad( value ) ) );
											break;

										case 'prismatic':
											matrix.multiply( m0.makeTranslation( axis.x * value, axis.y * value, axis.z * value ) );
											break;

										default:
											console.warn( 'THREE.ColladaLoader: Unknown joint type: ' + joint.type );
											break;

									}

								} else {

									switch ( transform.type ) {

										case 'matrix':
											matrix.multiply( transform.obj );
											break;

										case 'translate':
											matrix.multiply( m0.makeTranslation( transform.obj.x, transform.obj.y, transform.obj.z ) );
											break;

										case 'scale':
											matrix.scale( transform.obj );
											break;

										case 'rotate':
											matrix.multiply( m0.makeRotationAxis( transform.obj, transform.angle ) );
											break;

									}

								}

							}

							object.matrix.copy( matrix );
							object.matrix.decompose( object.position, object.quaternion, object.scale );

							jointMap[ jointIndex ].position = value;

						}

					} else {

						console.log( 'THREE.ColladaLoader: ' + jointIndex + ' does not exist.' );

					}

				}

			};

		}

		function buildTransformList( node ) {

			const transforms = [];

			const xml = collada.querySelector( '[id="' + node.id + '"]' );

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let array, vector;

				switch ( child.nodeName ) {

					case 'matrix':
						array = parseFloats( child.textContent );
						const matrix = new Matrix4().fromArray( array ).transpose();
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: matrix
						} );
						break;

					case 'translate':
					case 'scale':
						array = parseFloats( child.textContent );
						vector = new Vector3().fromArray( array );
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: vector
						} );
						break;

					case 'rotate':
						array = parseFloats( child.textContent );
						vector = new Vector3().fromArray( array );
						const angle = MathUtils.degToRad( array[ 3 ] );
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: vector,
							angle: angle
						} );
						break;

				}

			}

			return transforms;

		}

		// nodes

		function prepareNodes( xml ) {

			const elements = xml.getElementsByTagName( 'node' );

			// ensure all node elements have id attributes

			for ( let i = 0; i < elements.length; i ++ ) {

				const element = elements[ i ];

				if ( element.hasAttribute( 'id' ) === false ) {

					element.setAttribute( 'id', generateId() );

				}

			}

		}

		const matrix = new Matrix4();
		const vector = new Vector3();

		function parseNode( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				type: xml.getAttribute( 'type' ),
				id: xml.getAttribute( 'id' ),
				sid: xml.getAttribute( 'sid' ),
				matrix: new Matrix4(),
				nodes: [],
				instanceCameras: [],
				instanceControllers: [],
				instanceLights: [],
				instanceGeometries: [],
				instanceNodes: [],
				transforms: {}
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let array;

				switch ( child.nodeName ) {

					case 'node':
						data.nodes.push( child.getAttribute( 'id' ) );
						parseNode( child );
						break;

					case 'instance_camera':
						data.instanceCameras.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'instance_controller':
						data.instanceControllers.push( parseNodeInstance( child ) );
						break;

					case 'instance_light':
						data.instanceLights.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'instance_geometry':
						data.instanceGeometries.push( parseNodeInstance( child ) );
						break;

					case 'instance_node':
						data.instanceNodes.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'matrix':
						array = parseFloats( child.textContent );
						data.matrix.multiply( matrix.fromArray( array ).transpose() );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'translate':
						array = parseFloats( child.textContent );
						vector.fromArray( array );
						data.matrix.multiply( matrix.makeTranslation( vector.x, vector.y, vector.z ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'rotate':
						array = parseFloats( child.textContent );
						const angle = MathUtils.degToRad( array[ 3 ] );
						data.matrix.multiply( matrix.makeRotationAxis( vector.fromArray( array ), angle ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'scale':
						array = parseFloats( child.textContent );
						data.matrix.scale( vector.fromArray( array ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'extra':
						break;

					default:
						console.log( child );

				}

			}

			if ( hasNode( data.id ) ) {

				console.warn( 'THREE.ColladaLoader: There is already a node with ID %s. Exclude current node from further processing.', data.id );

			} else {

				library.nodes[ data.id ] = data;

			}

			return data;

		}

		function parseNodeInstance( xml ) {

			const data = {
				id: parseId( xml.getAttribute( 'url' ) ),
				materials: {},
				skeletons: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'bind_material':
						const instances = child.getElementsByTagName( 'instance_material' );

						for ( let j = 0; j < instances.length; j ++ ) {

							const instance = instances[ j ];
							const symbol = instance.getAttribute( 'symbol' );
							const target = instance.getAttribute( 'target' );

							data.materials[ symbol ] = parseId( target );

						}

						break;

					case 'skeleton':
						data.skeletons.push( parseId( child.textContent ) );
						break;

					default:
						break;

				}

			}

			return data;

		}

		function buildSkeleton( skeletons, joints ) {

			const boneData = [];
			const sortedBoneData = [];

			let i, j, data;

			// a skeleton can have multiple root bones. collada expresses this
			// situation with multiple "skeleton" tags per controller instance

			for ( i = 0; i < skeletons.length; i ++ ) {

				const skeleton = skeletons[ i ];

				let root;

				if ( hasNode( skeleton ) ) {

					root = getNode( skeleton );
					buildBoneHierarchy( root, joints, boneData );

				} else if ( hasVisualScene( skeleton ) ) {

					// handle case where the skeleton refers to the visual scene (#13335)

					const visualScene = library.visualScenes[ skeleton ];
					const children = visualScene.children;

					for ( let j = 0; j < children.length; j ++ ) {

						const child = children[ j ];

						if ( child.type === 'JOINT' ) {

							const root = getNode( child.id );
							buildBoneHierarchy( root, joints, boneData );

						}

					}

				} else {

					console.error( 'THREE.ColladaLoader: Unable to find root bone of skeleton with ID:', skeleton );

				}

			}

			// sort bone data (the order is defined in the corresponding controller)

			for ( i = 0; i < joints.length; i ++ ) {

				for ( j = 0; j < boneData.length; j ++ ) {

					data = boneData[ j ];

					if ( data.bone.name === joints[ i ].name ) {

						sortedBoneData[ i ] = data;
						data.processed = true;
						break;

					}

				}

			}

			// add unprocessed bone data at the end of the list

			for ( i = 0; i < boneData.length; i ++ ) {

				data = boneData[ i ];

				if ( data.processed === false ) {

					sortedBoneData.push( data );
					data.processed = true;

				}

			}

			// setup arrays for skeleton creation

			const bones = [];
			const boneInverses = [];

			for ( i = 0; i < sortedBoneData.length; i ++ ) {

				data = sortedBoneData[ i ];

				bones.push( data.bone );
				boneInverses.push( data.boneInverse );

			}

			return new Skeleton( bones, boneInverses );

		}

		function buildBoneHierarchy( root, joints, boneData ) {

			// setup bone data from visual scene

			root.traverse( function ( object ) {

				if ( object.isBone === true ) {

					let boneInverse;

					// retrieve the boneInverse from the controller data

					for ( let i = 0; i < joints.length; i ++ ) {

						const joint = joints[ i ];

						if ( joint.name === object.name ) {

							boneInverse = joint.boneInverse;
							break;

						}

					}

					if ( boneInverse === undefined ) {

						// Unfortunately, there can be joints in the visual scene that are not part of the
						// corresponding controller. In this case, we have to create a dummy boneInverse matrix
						// for the respective bone. This bone won't affect any vertices, because there are no skin indices
						// and weights defined for it. But we still have to add the bone to the sorted bone list in order to
						// ensure a correct animation of the model.

						boneInverse = new Matrix4();

					}

					boneData.push( { bone: object, boneInverse: boneInverse, processed: false } );

				}

			} );

		}

		function buildNode( data ) {

			const objects = [];

			const matrix = data.matrix;
			const nodes = data.nodes;
			const type = data.type;
			const instanceCameras = data.instanceCameras;
			const instanceControllers = data.instanceControllers;
			const instanceLights = data.instanceLights;
			const instanceGeometries = data.instanceGeometries;
			const instanceNodes = data.instanceNodes;

			// nodes

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				objects.push( getNode( nodes[ i ] ) );

			}

			// instance cameras

			for ( let i = 0, l = instanceCameras.length; i < l; i ++ ) {

				const instanceCamera = getCamera( instanceCameras[ i ] );

				if ( instanceCamera !== null ) {

					objects.push( instanceCamera.clone() );

				}

			}

			// instance controllers

			for ( let i = 0, l = instanceControllers.length; i < l; i ++ ) {

				const instance = instanceControllers[ i ];
				const controller = getController( instance.id );
				const geometries = getGeometry( controller.id );
				const newObjects = buildObjects( geometries, instance.materials );

				const skeletons = instance.skeletons;
				const joints = controller.skin.joints;

				const skeleton = buildSkeleton( skeletons, joints );

				for ( let j = 0, jl = newObjects.length; j < jl; j ++ ) {

					const object = newObjects[ j ];

					if ( object.isSkinnedMesh ) {

						object.bind( skeleton, controller.skin.bindMatrix );
						object.normalizeSkinWeights();

					}

					objects.push( object );

				}

			}

			// instance lights

			for ( let i = 0, l = instanceLights.length; i < l; i ++ ) {

				const instanceLight = getLight( instanceLights[ i ] );

				if ( instanceLight !== null ) {

					objects.push( instanceLight.clone() );

				}

			}

			// instance geometries

			for ( let i = 0, l = instanceGeometries.length; i < l; i ++ ) {

				const instance = instanceGeometries[ i ];

				// a single geometry instance in collada can lead to multiple object3Ds.
				// this is the case when primitives are combined like triangles and lines

				const geometries = getGeometry( instance.id );
				const newObjects = buildObjects( geometries, instance.materials );

				for ( let j = 0, jl = newObjects.length; j < jl; j ++ ) {

					objects.push( newObjects[ j ] );

				}

			}

			// instance nodes

			for ( let i = 0, l = instanceNodes.length; i < l; i ++ ) {

				objects.push( getNode( instanceNodes[ i ] ).clone() );

			}

			let object;

			if ( nodes.length === 0 && objects.length === 1 ) {

				object = objects[ 0 ];

			} else {

				object = ( type === 'JOINT' ) ? new Bone() : new Group();

				for ( let i = 0; i < objects.length; i ++ ) {

					object.add( objects[ i ] );

				}

			}

			object.name = ( type === 'JOINT' ) ? data.sid : data.name;
			object.matrix.copy( matrix );
			object.matrix.decompose( object.position, object.quaternion, object.scale );

			return object;

		}

		const fallbackMaterial = new MeshBasicMaterial( {
			name: Loader.DEFAULT_MATERIAL_NAME,
			color: 0xff00ff
		} );

		function resolveMaterialBinding( keys, instanceMaterials ) {

			const materials = [];

			for ( let i = 0, l = keys.length; i < l; i ++ ) {

				const id = instanceMaterials[ keys[ i ] ];

				if ( id === undefined ) {

					console.warn( 'THREE.ColladaLoader: Material with key %s not found. Apply fallback material.', keys[ i ] );
					materials.push( fallbackMaterial );

				} else {

					materials.push( getMaterial( id ) );

				}

			}

			return materials;

		}

		function buildObjects( geometries, instanceMaterials ) {

			const objects = [];

			for ( const type in geometries ) {

				const geometry = geometries[ type ];

				const materials = resolveMaterialBinding( geometry.materialKeys, instanceMaterials );

				// handle case if no materials are defined

				if ( materials.length === 0 ) {

					if ( type === 'lines' || type === 'linestrips' ) {

						materials.push( new LineBasicMaterial() );

					} else {

						materials.push( new MeshPhongMaterial() );

					}

				}

				// Collada allows to use phong and lambert materials with lines. Replacing these cases with LineBasicMaterial.

				if ( type === 'lines' || type === 'linestrips' ) {

					for ( let i = 0, l = materials.length; i < l; i ++ ) {

						const material = materials[ i ];

						if ( material.isMeshPhongMaterial === true || material.isMeshLambertMaterial === true ) {

							const lineMaterial = new LineBasicMaterial();

							// copy compatible properties

							lineMaterial.color.copy( material.color );
							lineMaterial.opacity = material.opacity;
							lineMaterial.transparent = material.transparent;

							// replace material

							materials[ i ] = lineMaterial;

						}

					}

				}

				// regard skinning

				const skinning = ( geometry.data.attributes.skinIndex !== undefined );

				// choose between a single or multi materials (material array)

				const material = ( materials.length === 1 ) ? materials[ 0 ] : materials;

				// now create a specific 3D object

				let object;

				switch ( type ) {

					case 'lines':
						object = new LineSegments( geometry.data, material );
						break;

					case 'linestrips':
						object = new Line( geometry.data, material );
						break;

					case 'triangles':
					case 'polylist':
						if ( skinning ) {

							object = new SkinnedMesh( geometry.data, material );

						} else {

							object = new Mesh( geometry.data, material );

						}

						break;

				}

				objects.push( object );

			}

			return objects;

		}

		function hasNode( id ) {

			return library.nodes[ id ] !== undefined;

		}

		function getNode( id ) {

			return getBuild( library.nodes[ id ], buildNode );

		}

		// visual scenes

		function parseVisualScene( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ),
				children: []
			};

			prepareNodes( xml );

			const elements = getElementsByTagName( xml, 'node' );

			for ( let i = 0; i < elements.length; i ++ ) {

				data.children.push( parseNode( elements[ i ] ) );

			}

			library.visualScenes[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildVisualScene( data ) {

			const group = new Group();
			group.name = data.name;

			const children = data.children;

			for ( let i = 0; i < children.length; i ++ ) {

				const child = children[ i ];

				group.add( getNode( child.id ) );

			}

			return group;

		}

		function hasVisualScene( id ) {

			return library.visualScenes[ id ] !== undefined;

		}

		function getVisualScene( id ) {

			return getBuild( library.visualScenes[ id ], buildVisualScene );

		}

		// scenes

		function parseScene( xml ) {

			const instance = getElementsByTagName( xml, 'instance_visual_scene' )[ 0 ];
			return getVisualScene( parseId( instance.getAttribute( 'url' ) ) );

		}

		function setupAnimations() {

			const clips = library.clips;

			if ( isEmpty( clips ) === true ) {

				if ( isEmpty( library.animations ) === false ) {

					// if there are animations but no clips, we create a default clip for playback

					const tracks = [];

					for ( const id in library.animations ) {

						const animationTracks = getAnimation( id );

						for ( let i = 0, l = animationTracks.length; i < l; i ++ ) {

							tracks.push( animationTracks[ i ] );

						}

					}

					animations.push( new AnimationClip( 'default', - 1, tracks ) );

				}

			} else {

				for ( const id in clips ) {

					animations.push( getAnimationClip( id ) );

				}

			}

		}

		// convert the parser error element into text with each child elements text
		// separated by new lines.

		function parserErrorToText( parserError ) {

			let result = '';
			const stack = [ parserError ];

			while ( stack.length ) {

				const node = stack.shift();

				if ( node.nodeType === Node.TEXT_NODE ) {

					result += node.textContent;

				} else {

					result += '\n';
					stack.push( ...node.childNodes );

				}

			}

			return result.trim();

		}

		if ( text.length === 0 ) {

			return { scene: new Scene() };

		}

		const xml = new DOMParser().parseFromString( text, 'application/xml' );

		const collada = getElementsByTagName( xml, 'COLLADA' )[ 0 ];

		const parserError = xml.getElementsByTagName( 'parsererror' )[ 0 ];
		if ( parserError !== undefined ) {

			// Chrome will return parser error with a div in it

			const errorElement = getElementsByTagName( parserError, 'div' )[ 0 ];
			let errorText;

			if ( errorElement ) {

				errorText = errorElement.textContent;

			} else {

				errorText = parserErrorToText( parserError );

			}

			console.error( 'THREE.ColladaLoader: Failed to parse collada file.\n', errorText );

			return null;

		}

		// metadata

		const version = collada.getAttribute( 'version' );
		console.debug( 'THREE.ColladaLoader: File version', version );

		const asset = parseAsset( getElementsByTagName( collada, 'asset' )[ 0 ] );
		const textureLoader = new TextureLoader( this.manager );
		textureLoader.setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		let tgaLoader;

		if ( TGALoader ) {

			tgaLoader = new TGALoader( this.manager );
			tgaLoader.setPath( this.resourcePath || path );

		}

		//

		const tempColor = new Color();
		const animations = [];
		let kinematics = {};
		let count = 0;

		//

		const library = {
			animations: {},
			clips: {},
			controllers: {},
			images: {},
			effects: {},
			materials: {},
			cameras: {},
			lights: {},
			geometries: {},
			nodes: {},
			visualScenes: {},
			kinematicsModels: {},
			physicsModels: {},
			kinematicsScenes: {}
		};

		parseLibrary( collada, 'library_animations', 'animation', parseAnimation );
		parseLibrary( collada, 'library_animation_clips', 'animation_clip', parseAnimationClip );
		parseLibrary( collada, 'library_controllers', 'controller', parseController );
		parseLibrary( collada, 'library_images', 'image', parseImage );
		parseLibrary( collada, 'library_effects', 'effect', parseEffect );
		parseLibrary( collada, 'library_materials', 'material', parseMaterial );
		parseLibrary( collada, 'library_cameras', 'camera', parseCamera );
		parseLibrary( collada, 'library_lights', 'light', parseLight );
		parseLibrary( collada, 'library_geometries', 'geometry', parseGeometry );
		parseLibrary( collada, 'library_nodes', 'node', parseNode );
		parseLibrary( collada, 'library_visual_scenes', 'visual_scene', parseVisualScene );
		parseLibrary( collada, 'library_kinematics_models', 'kinematics_model', parseKinematicsModel );
		parseLibrary( collada, 'library_physics_models', 'physics_model', parsePhysicsModel );
		parseLibrary( collada, 'scene', 'instance_kinematics_scene', parseKinematicsScene );

		buildLibrary( library.animations, buildAnimation );
		buildLibrary( library.clips, buildAnimationClip );
		buildLibrary( library.controllers, buildController );
		buildLibrary( library.images, buildImage );
		buildLibrary( library.effects, buildEffect );
		buildLibrary( library.materials, buildMaterial );
		buildLibrary( library.cameras, buildCamera );
		buildLibrary( library.lights, buildLight );
		buildLibrary( library.geometries, buildGeometry );
		buildLibrary( library.visualScenes, buildVisualScene );

		setupAnimations();
		setupKinematics();

		const scene = parseScene( getElementsByTagName( collada, 'scene' )[ 0 ] );
		scene.animations = animations;

		if ( asset.upAxis === 'Z_UP' ) {

			console.warn( 'THREE.ColladaLoader: You are loading an asset with a Z-UP coordinate system. The loader just rotates the asset to transform it into Y-UP. The vertex data are not converted, see #24289.' );
			scene.rotation.set( - Math.PI / 2, 0, 0 );

		}

		scene.scale.multiplyScalar( asset.unit );

		return {
			get animations() {

				console.warn( 'THREE.ColladaLoader: Please access animations over scene.animations now.' );
				return animations;

			},
			kinematics: kinematics,
			library: library,
			scene: scene
		};

	}
```
</details>

### `getElementsByTagName(xml: any, name: any): any[]`

**Parameters:**

- **`xml`** `any`
- **`name`** `any`

**Returns:** `any[]`

**Calls:**

- `array.push`

**Internal Comments:**
```
// Non recursive xml.getElementsByTagName() ... (x2)
```

<details><summary>Code</summary>

```typescript
function getElementsByTagName( xml, name ) {

			// Non recursive xml.getElementsByTagName() ...

			const array = [];
			const childNodes = xml.childNodes;

			for ( let i = 0, l = childNodes.length; i < l; i ++ ) {

				const child = childNodes[ i ];

				if ( child.nodeName === name ) {

					array.push( child );

				}

			}

			return array;

		}
```
</details>

### `parseStrings(text: any): any[]`

**Parameters:**

- **`text`** `any`

**Returns:** `any[]`

**Calls:**

- `text.trim().split`

<details><summary>Code</summary>

```typescript
function parseStrings( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parts[ i ];

			}

			return array;

		}
```
</details>

### `parseFloats(text: any): any[]`

**Parameters:**

- **`text`** `any`

**Returns:** `any[]`

**Calls:**

- `text.trim().split`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function parseFloats( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parseFloat( parts[ i ] );

			}

			return array;

		}
```
</details>

### `parseInts(text: any): any[]`

**Parameters:**

- **`text`** `any`

**Returns:** `any[]`

**Calls:**

- `text.trim().split`
- `parseInt`

<details><summary>Code</summary>

```typescript
function parseInts( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parseInt( parts[ i ] );

			}

			return array;

		}
```
</details>

### `parseId(text: any): any`

**Parameters:**

- **`text`** `any`

**Returns:** `any`

**Calls:**

- `text.substring`

<details><summary>Code</summary>

```typescript
function parseId( text ) {

			return text.substring( 1 );

		}
```
</details>

### `generateId(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function generateId() {

			return 'three_default_' + ( count ++ );

		}
```
</details>

### `isEmpty(object: any): boolean`

**Parameters:**

- **`object`** `any`

**Returns:** `boolean`

**Calls:**

- `Object.keys`

<details><summary>Code</summary>

```typescript
function isEmpty( object ) {

			return Object.keys( object ).length === 0;

		}
```
</details>

### `parseAsset(xml: any): { unit: number; upAxis: any; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ unit: number; upAxis: any; }`

**Calls:**

- `parseAssetUnit`
- `getElementsByTagName`
- `parseAssetUpAxis`

<details><summary>Code</summary>

```typescript
function parseAsset( xml ) {

			return {
				unit: parseAssetUnit( getElementsByTagName( xml, 'unit' )[ 0 ] ),
				upAxis: parseAssetUpAxis( getElementsByTagName( xml, 'up_axis' )[ 0 ] )
			};

		}
```
</details>

### `parseAssetUnit(xml: any): number`

**Parameters:**

- **`xml`** `any`

**Returns:** `number`

**Calls:**

- `xml.hasAttribute`
- `parseFloat`
- `xml.getAttribute`

<details><summary>Code</summary>

```typescript
function parseAssetUnit( xml ) {

			if ( ( xml !== undefined ) && ( xml.hasAttribute( 'meter' ) === true ) ) {

				return parseFloat( xml.getAttribute( 'meter' ) );

			} else {

				return 1; // default 1 meter

			}

		}
```
</details>

### `parseAssetUpAxis(xml: any): any`

**Parameters:**

- **`xml`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function parseAssetUpAxis( xml ) {

			return xml !== undefined ? xml.textContent : 'Y_UP';

		}
```
</details>

### `parseLibrary(xml: any, libraryName: any, nodeName: any, parser: any): void`

**Parameters:**

- **`xml`** `any`
- **`libraryName`** `any`
- **`nodeName`** `any`
- **`parser`** `any`

**Returns:** `void`

**Calls:**

- `getElementsByTagName`
- `parser`

<details><summary>Code</summary>

```typescript
function parseLibrary( xml, libraryName, nodeName, parser ) {

			const library = getElementsByTagName( xml, libraryName )[ 0 ];

			if ( library !== undefined ) {

				const elements = getElementsByTagName( library, nodeName );

				for ( let i = 0; i < elements.length; i ++ ) {

					parser( elements[ i ] );

				}

			}

		}
```
</details>

### `buildLibrary(data: any, builder: any): void`

**Parameters:**

- **`data`** `any`
- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder`

<details><summary>Code</summary>

```typescript
function buildLibrary( data, builder ) {

			for ( const name in data ) {

				const object = data[ name ];
				object.build = builder( data[ name ] );

			}

		}
```
</details>

### `getBuild(data: any, builder: any): any`

**Parameters:**

- **`data`** `any`
- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder`

<details><summary>Code</summary>

```typescript
function getBuild( data, builder ) {

			if ( data.build !== undefined ) return data.build;

			data.build = builder( data );

			return data.build;

		}
```
</details>

### `parseAnimation(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `child.getAttribute`
- `parseSource`
- `parseAnimationSampler`
- `parseAnimationChannel`
- `parseAnimation`
- `console.log`
- `xml.getAttribute`
- `MathUtils.generateUUID`

**Internal Comments:**
```
// hierarchy of related animations (x3)
// since 'id' attributes can be optional, it's necessary to generate a UUID for unique assignment (x5)
```

<details><summary>Code</summary>

```typescript
function parseAnimation( xml ) {

			const data = {
				sources: {},
				samplers: {},
				channels: {}
			};

			let hasChildren = false;

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let id;

				switch ( child.nodeName ) {

					case 'source':
						id = child.getAttribute( 'id' );
						data.sources[ id ] = parseSource( child );
						break;

					case 'sampler':
						id = child.getAttribute( 'id' );
						data.samplers[ id ] = parseAnimationSampler( child );
						break;

					case 'channel':
						id = child.getAttribute( 'target' );
						data.channels[ id ] = parseAnimationChannel( child );
						break;

					case 'animation':
						// hierarchy of related animations
						parseAnimation( child );
						hasChildren = true;
						break;

					default:
						console.log( child );

				}

			}

			if ( hasChildren === false ) {

				// since 'id' attributes can be optional, it's necessary to generate a UUID for unique assignment

				library.animations[ xml.getAttribute( 'id' ) || MathUtils.generateUUID() ] = data;

			}

		}
```
</details>

### `parseAnimationSampler(xml: any): { inputs: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ inputs: {}; }`

**Calls:**

- `parseId`
- `child.getAttribute`

<details><summary>Code</summary>

```typescript
function parseAnimationSampler( xml ) {

			const data = {
				inputs: {},
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const id = parseId( child.getAttribute( 'source' ) );
						const semantic = child.getAttribute( 'semantic' );
						data.inputs[ semantic ] = id;
						break;

				}

			}

			return data;

		}
```
</details>

### `parseAnimationChannel(xml: any): { member: any; indices: any; id: any; sid: any; arraySyntax: boolean; memberSyntax: boolean; sampler: any; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ member: any; indices: any; id: any; sid: any; arraySyntax: boolean; memberSyntax: boolean; sampler: any; }`

**Calls:**

- `xml.getAttribute`
- `target.split`
- `parts.shift`
- `sid.indexOf`
- `sid.split`
- `indices.shift`
- `parseInt`
- `indices[ i ].replace`
- `parseId`

**Internal Comments:**
```
// parsing SID Addressing Syntax (x2)
// check selection syntax (x2)
//  member selection access (x3)
// array-access syntax. can be used to express fields in one-dimensional vectors or two-dimensional matrices. (x2)
```

<details><summary>Code</summary>

```typescript
function parseAnimationChannel( xml ) {

			const data = {};

			const target = xml.getAttribute( 'target' );

			// parsing SID Addressing Syntax

			let parts = target.split( '/' );

			const id = parts.shift();
			let sid = parts.shift();

			// check selection syntax

			const arraySyntax = ( sid.indexOf( '(' ) !== - 1 );
			const memberSyntax = ( sid.indexOf( '.' ) !== - 1 );

			if ( memberSyntax ) {

				//  member selection access

				parts = sid.split( '.' );
				sid = parts.shift();
				data.member = parts.shift();

			} else if ( arraySyntax ) {

				// array-access syntax. can be used to express fields in one-dimensional vectors or two-dimensional matrices.

				const indices = sid.split( '(' );
				sid = indices.shift();

				for ( let i = 0; i < indices.length; i ++ ) {

					indices[ i ] = parseInt( indices[ i ].replace( /\)/, '' ) );

				}

				data.indices = indices;

			}

			data.id = id;
			data.sid = sid;

			data.arraySyntax = arraySyntax;
			data.memberSyntax = memberSyntax;

			data.sampler = parseId( xml.getAttribute( 'source' ) );

			return data;

		}
```
</details>

### `buildAnimation(data: any): any[]`

**Parameters:**

- **`data`** `any`

**Returns:** `any[]`

**Calls:**

- `channels.hasOwnProperty`
- `buildAnimationChannel`
- `createKeyframeTracks`

<details><summary>Code</summary>

```typescript
function buildAnimation( data ) {

			const tracks = [];

			const channels = data.channels;
			const samplers = data.samplers;
			const sources = data.sources;

			for ( const target in channels ) {

				if ( channels.hasOwnProperty( target ) ) {

					const channel = channels[ target ];
					const sampler = samplers[ channel.sampler ];

					const inputId = sampler.inputs.INPUT;
					const outputId = sampler.inputs.OUTPUT;

					const inputSource = sources[ inputId ];
					const outputSource = sources[ outputId ];

					const animation = buildAnimationChannel( channel, inputSource, outputSource );

					createKeyframeTracks( animation, tracks );

				}

			}

			return tracks;

		}
```
</details>

### `getAnimation(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getAnimation( id ) {

			return getBuild( library.animations[ id ], buildAnimation );

		}
```
</details>

### `buildAnimationChannel(channel: any, inputSource: any, outputSource: any): { name: any; keyframes: { time: number; value: any; }[]; }`

**Parameters:**

- **`channel`** `any`
- **`inputSource`** `any`
- **`outputSource`** `any`

**Returns:** `{ name: any; keyframes: { time: number; value: any; }[]; }`

**Calls:**

- `getNode`
- `node.matrix.clone().transpose`
- `console.warn`
- `prepareAnimationData`

**Internal Comments:**
```
// the collada spec allows the animation of data in various ways.
// depending on the transform type (matrix, translate, rotate, scale), we execute different logic
```

<details><summary>Code</summary>

```typescript
function buildAnimationChannel( channel, inputSource, outputSource ) {

			const node = library.nodes[ channel.id ];
			const object3D = getNode( node.id );

			const transform = node.transforms[ channel.sid ];
			const defaultMatrix = node.matrix.clone().transpose();

			let time, stride;
			let i, il, j, jl;

			const data = {};

			// the collada spec allows the animation of data in various ways.
			// depending on the transform type (matrix, translate, rotate, scale), we execute different logic

			switch ( transform ) {

				case 'matrix':

					for ( i = 0, il = inputSource.array.length; i < il; i ++ ) {

						time = inputSource.array[ i ];
						stride = i * outputSource.stride;

						if ( data[ time ] === undefined ) data[ time ] = {};

						if ( channel.arraySyntax === true ) {

							const value = outputSource.array[ stride ];
							const index = channel.indices[ 0 ] + 4 * channel.indices[ 1 ];

							data[ time ][ index ] = value;

						} else {

							for ( j = 0, jl = outputSource.stride; j < jl; j ++ ) {

								data[ time ][ j ] = outputSource.array[ stride + j ];

							}

						}

					}

					break;

				case 'translate':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

				case 'rotate':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

				case 'scale':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

			}

			const keyframes = prepareAnimationData( data, defaultMatrix );

			const animation = {
				name: object3D.uuid,
				keyframes: keyframes
			};

			return animation;

		}
```
</details>

### `prepareAnimationData(data: any, defaultMatrix: any): { time: number; value: any; }[]`

**Parameters:**

- **`data`** `any`
- **`defaultMatrix`** `any`

**Returns:** `{ time: number; value: any; }[]`

**Calls:**

- `keyframes.push`
- `parseFloat`
- `keyframes.sort`
- `transformAnimationData`

**Internal Comments:**
```
// transfer data into a sortable array
// ensure keyframes are sorted by time (x4)
// now we clean up all animation data, so we can use them for keyframe tracks
// array sort function
```

<details><summary>Code</summary>

```typescript
function prepareAnimationData( data, defaultMatrix ) {

			const keyframes = [];

			// transfer data into a sortable array

			for ( const time in data ) {

				keyframes.push( { time: parseFloat( time ), value: data[ time ] } );

			}

			// ensure keyframes are sorted by time

			keyframes.sort( ascending );

			// now we clean up all animation data, so we can use them for keyframe tracks

			for ( let i = 0; i < 16; i ++ ) {

				transformAnimationData( keyframes, i, defaultMatrix.elements[ i ] );

			}

			return keyframes;

			// array sort function

			function ascending( a, b ) {

				return a.time - b.time;

			}

		}
```
</details>

### `ascending(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function ascending( a, b ) {

				return a.time - b.time;

			}
```
</details>

### `createKeyframeTracks(animation: any, tracks: any): any`

**Parameters:**

- **`animation`** `any`
- **`tracks`** `any`

**Returns:** `any`

**Calls:**

- `matrix.fromArray( value ).transpose`
- `matrix.decompose`
- `times.push`
- `positionData.push`
- `quaternionData.push`
- `scaleData.push`
- `tracks.push`

<details><summary>Code</summary>

```typescript
function createKeyframeTracks( animation, tracks ) {

			const keyframes = animation.keyframes;
			const name = animation.name;

			const times = [];
			const positionData = [];
			const quaternionData = [];
			const scaleData = [];

			for ( let i = 0, l = keyframes.length; i < l; i ++ ) {

				const keyframe = keyframes[ i ];

				const time = keyframe.time;
				const value = keyframe.value;

				matrix.fromArray( value ).transpose();
				matrix.decompose( position, quaternion, scale );

				times.push( time );
				positionData.push( position.x, position.y, position.z );
				quaternionData.push( quaternion.x, quaternion.y, quaternion.z, quaternion.w );
				scaleData.push( scale.x, scale.y, scale.z );

			}

			if ( positionData.length > 0 ) tracks.push( new VectorKeyframeTrack( name + '.position', times, positionData ) );
			if ( quaternionData.length > 0 ) tracks.push( new QuaternionKeyframeTrack( name + '.quaternion', times, quaternionData ) );
			if ( scaleData.length > 0 ) tracks.push( new VectorKeyframeTrack( name + '.scale', times, scaleData ) );

			return tracks;

		}
```
</details>

### `transformAnimationData(keyframes: any, property: any, defaultValue: any): void`

**Parameters:**

- **`keyframes`** `any`
- **`property`** `any`
- **`defaultValue`** `any`

**Returns:** `void`

**Calls:**

- `createMissingKeyframes`

**Internal Comments:**
```
// check, if values of a property are missing in our keyframes
// no values at all, so we set a default value
// filling gaps (x3)
```

<details><summary>Code</summary>

```typescript
function transformAnimationData( keyframes, property, defaultValue ) {

			let keyframe;

			let empty = true;
			let i, l;

			// check, if values of a property are missing in our keyframes

			for ( i = 0, l = keyframes.length; i < l; i ++ ) {

				keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] === undefined ) {

					keyframe.value[ property ] = null; // mark as missing

				} else {

					empty = false;

				}

			}

			if ( empty === true ) {

				// no values at all, so we set a default value

				for ( i = 0, l = keyframes.length; i < l; i ++ ) {

					keyframe = keyframes[ i ];

					keyframe.value[ property ] = defaultValue;

				}

			} else {

				// filling gaps

				createMissingKeyframes( keyframes, property );

			}

		}
```
</details>

### `createMissingKeyframes(keyframes: any, property: any): void`

**Parameters:**

- **`keyframes`** `any`
- **`property`** `any`

**Returns:** `void`

**Calls:**

- `getPrev`
- `getNext`
- `interpolate`

<details><summary>Code</summary>

```typescript
function createMissingKeyframes( keyframes, property ) {

			let prev, next;

			for ( let i = 0, l = keyframes.length; i < l; i ++ ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] === null ) {

					prev = getPrev( keyframes, i, property );
					next = getNext( keyframes, i, property );

					if ( prev === null ) {

						keyframe.value[ property ] = next.value[ property ];
						continue;

					}

					if ( next === null ) {

						keyframe.value[ property ] = prev.value[ property ];
						continue;

					}

					interpolate( keyframe, prev, next, property );

				}

			}

		}
```
</details>

### `getPrev(keyframes: any, i: any, property: any): any`

**Parameters:**

- **`keyframes`** `any`
- **`i`** `any`
- **`property`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getPrev( keyframes, i, property ) {

			while ( i >= 0 ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] !== null ) return keyframe;

				i --;

			}

			return null;

		}
```
</details>

### `getNext(keyframes: any, i: any, property: any): any`

**Parameters:**

- **`keyframes`** `any`
- **`i`** `any`
- **`property`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getNext( keyframes, i, property ) {

			while ( i < keyframes.length ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] !== null ) return keyframe;

				i ++;

			}

			return null;

		}
```
</details>

### `interpolate(key: any, prev: any, next: any, property: any): void`

**Parameters:**

- **`key`** `any`
- **`prev`** `any`
- **`next`** `any`
- **`property`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function interpolate( key, prev, next, property ) {

			if ( ( next.time - prev.time ) === 0 ) {

				key.value[ property ] = prev.value[ property ];
				return;

			}

			key.value[ property ] = ( ( key.time - prev.time ) * ( next.value[ property ] - prev.value[ property ] ) / ( next.time - prev.time ) ) + prev.value[ property ];

		}
```
</details>

### `parseAnimationClip(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `xml.getAttribute`
- `parseFloat`
- `data.animations.push`
- `parseId`
- `child.getAttribute`

<details><summary>Code</summary>

```typescript
function parseAnimationClip( xml ) {

			const data = {
				name: xml.getAttribute( 'id' ) || 'default',
				start: parseFloat( xml.getAttribute( 'start' ) || 0 ),
				end: parseFloat( xml.getAttribute( 'end' ) || 0 ),
				animations: []
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'instance_animation':
						data.animations.push( parseId( child.getAttribute( 'url' ) ) );
						break;

				}

			}

			library.clips[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `buildAnimationClip(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `getAnimation`
- `tracks.push`

<details><summary>Code</summary>

```typescript
function buildAnimationClip( data ) {

			const tracks = [];

			const name = data.name;
			const duration = ( data.end - data.start ) || - 1;
			const animations = data.animations;

			for ( let i = 0, il = animations.length; i < il; i ++ ) {

				const animationTracks = getAnimation( animations[ i ] );

				for ( let j = 0, jl = animationTracks.length; j < jl; j ++ ) {

					tracks.push( animationTracks[ j ] );

				}

			}

			return new AnimationClip( name, duration, tracks );

		}
```
</details>

### `getAnimationClip(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getAnimationClip( id ) {

			return getBuild( library.clips[ id ], buildAnimationClip );

		}
```
</details>

### `parseController(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `parseId`
- `child.getAttribute`
- `parseSkin`
- `console.warn`
- `xml.getAttribute`

**Internal Comments:**
```
// there is exactly one skin per controller (x4)
```

<details><summary>Code</summary>

```typescript
function parseController( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'skin':
						// there is exactly one skin per controller
						data.id = parseId( child.getAttribute( 'source' ) );
						data.skin = parseSkin( child );
						break;

					case 'morph':
						data.id = parseId( child.getAttribute( 'source' ) );
						console.warn( 'THREE.ColladaLoader: Morph target animation not supported yet.' );
						break;

				}

			}

			library.controllers[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `parseSkin(xml: any): { sources: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ sources: {}; }`

**Calls:**

- `parseFloats`
- `child.getAttribute`
- `parseSource`
- `parseJoints`
- `parseVertexWeights`

<details><summary>Code</summary>

```typescript
function parseSkin( xml ) {

			const data = {
				sources: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'bind_shape_matrix':
						data.bindShapeMatrix = parseFloats( child.textContent );
						break;

					case 'source':
						const id = child.getAttribute( 'id' );
						data.sources[ id ] = parseSource( child );
						break;

					case 'joints':
						data.joints = parseJoints( child );
						break;

					case 'vertex_weights':
						data.vertexWeights = parseVertexWeights( child );
						break;

				}

			}

			return data;

		}
```
</details>

### `parseJoints(xml: any): { inputs: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ inputs: {}; }`

**Calls:**

- `child.getAttribute`
- `parseId`

<details><summary>Code</summary>

```typescript
function parseJoints( xml ) {

			const data = {
				inputs: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const semantic = child.getAttribute( 'semantic' );
						const id = parseId( child.getAttribute( 'source' ) );
						data.inputs[ semantic ] = id;
						break;

				}

			}

			return data;

		}
```
</details>

### `parseVertexWeights(xml: any): { inputs: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ inputs: {}; }`

**Calls:**

- `child.getAttribute`
- `parseId`
- `parseInt`
- `parseInts`

<details><summary>Code</summary>

```typescript
function parseVertexWeights( xml ) {

			const data = {
				inputs: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const semantic = child.getAttribute( 'semantic' );
						const id = parseId( child.getAttribute( 'source' ) );
						const offset = parseInt( child.getAttribute( 'offset' ) );
						data.inputs[ semantic ] = { id: id, offset: offset };
						break;

					case 'vcount':
						data.vcount = parseInts( child.textContent );
						break;

					case 'v':
						data.v = parseInts( child.textContent );
						break;

				}

			}

			return data;

		}
```
</details>

### `buildController(data: any): { id: any; }`

**Parameters:**

- **`data`** `any`

**Returns:** `{ id: any; }`

**Calls:**

- `buildSkin`

**Internal Comments:**
```
// we enhance the 'sources' property of the corresponding geometry with our skin data (x5)
```

<details><summary>Code</summary>

```typescript
function buildController( data ) {

			const build = {
				id: data.id
			};

			const geometry = library.geometries[ build.id ];

			if ( data.skin !== undefined ) {

				build.skin = buildSkin( data.skin );

				// we enhance the 'sources' property of the corresponding geometry with our skin data

				geometry.sources.skinIndices = build.skin.indices;
				geometry.sources.skinWeights = build.skin.weights;

			}

			return build;

		}
```
</details>

### `buildSkin(data: any): { joints: any[]; indices: { array: any[]; stride: number; }; weights: { array: any[]; stride: number; }; }`

**Parameters:**

- **`data`** `any`

**Returns:** `{ joints: any[]; indices: { array: any[]; stride: number; }; weights: { array: any[]; stride: number; }; }`

**Calls:**

- `vertexSkinData.push`
- `vertexSkinData.sort`
- `build.indices.array.push`
- `build.weights.array.push`
- `new Matrix4().fromArray( data.bindShapeMatrix ).transpose`
- `new Matrix4().identity`
- `new Matrix4().fromArray( inverseSource.array, i * inverseSource.stride ).transpose`
- `build.joints.push`

**Internal Comments:**
```
// process skin data for each vertex
// we sort the joints in descending order based on the weights. (x4)
// this ensures, we only proceed the most important joints of the vertex (x4)
// now we provide for each vertex a set of four index and weight values.
// the order of the skin data matches the order of vertices
// setup bind matrix
// process bones and inverse bind matrix data
// array sort function
```

<details><summary>Code</summary>

```typescript
function buildSkin( data ) {

			const BONE_LIMIT = 4;

			const build = {
				joints: [], // this must be an array to preserve the joint order
				indices: {
					array: [],
					stride: BONE_LIMIT
				},
				weights: {
					array: [],
					stride: BONE_LIMIT
				}
			};

			const sources = data.sources;
			const vertexWeights = data.vertexWeights;

			const vcount = vertexWeights.vcount;
			const v = vertexWeights.v;
			const jointOffset = vertexWeights.inputs.JOINT.offset;
			const weightOffset = vertexWeights.inputs.WEIGHT.offset;

			const jointSource = data.sources[ data.joints.inputs.JOINT ];
			const inverseSource = data.sources[ data.joints.inputs.INV_BIND_MATRIX ];

			const weights = sources[ vertexWeights.inputs.WEIGHT.id ].array;
			let stride = 0;

			let i, j, l;

			// process skin data for each vertex

			for ( i = 0, l = vcount.length; i < l; i ++ ) {

				const jointCount = vcount[ i ]; // this is the amount of joints that affect a single vertex
				const vertexSkinData = [];

				for ( j = 0; j < jointCount; j ++ ) {

					const skinIndex = v[ stride + jointOffset ];
					const weightId = v[ stride + weightOffset ];
					const skinWeight = weights[ weightId ];

					vertexSkinData.push( { index: skinIndex, weight: skinWeight } );

					stride += 2;

				}

				// we sort the joints in descending order based on the weights.
				// this ensures, we only proceed the most important joints of the vertex

				vertexSkinData.sort( descending );

				// now we provide for each vertex a set of four index and weight values.
				// the order of the skin data matches the order of vertices

				for ( j = 0; j < BONE_LIMIT; j ++ ) {

					const d = vertexSkinData[ j ];

					if ( d !== undefined ) {

						build.indices.array.push( d.index );
						build.weights.array.push( d.weight );

					} else {

						build.indices.array.push( 0 );
						build.weights.array.push( 0 );

					}

				}

			}

			// setup bind matrix

			if ( data.bindShapeMatrix ) {

				build.bindMatrix = new Matrix4().fromArray( data.bindShapeMatrix ).transpose();

			} else {

				build.bindMatrix = new Matrix4().identity();

			}

			// process bones and inverse bind matrix data

			for ( i = 0, l = jointSource.array.length; i < l; i ++ ) {

				const name = jointSource.array[ i ];
				const boneInverse = new Matrix4().fromArray( inverseSource.array, i * inverseSource.stride ).transpose();

				build.joints.push( { name: name, boneInverse: boneInverse } );

			}

			return build;

			// array sort function

			function descending( a, b ) {

				return b.weight - a.weight;

			}

		}
```
</details>

### `descending(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function descending( a, b ) {

				return b.weight - a.weight;

			}
```
</details>

### `getController(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getController( id ) {

			return getBuild( library.controllers[ id ], buildController );

		}
```
</details>

### `parseImage(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `getElementsByTagName`
- `xml.getAttribute`

<details><summary>Code</summary>

```typescript
function parseImage( xml ) {

			const data = {
				init_from: getElementsByTagName( xml, 'init_from' )[ 0 ].textContent
			};

			library.images[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `buildImage(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function buildImage( data ) {

			if ( data.build !== undefined ) return data.build;

			return data.init_from;

		}
```
</details>

### `getImage(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`
- `console.warn`

<details><summary>Code</summary>

```typescript
function getImage( id ) {

			const data = library.images[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildImage );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find image with ID:', id );

			return null;

		}
```
</details>

### `parseEffect(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `parseEffectProfileCOMMON`
- `xml.getAttribute`

<details><summary>Code</summary>

```typescript
function parseEffect( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'profile_COMMON':
						data.profile = parseEffectProfileCOMMON( child );
						break;

				}

			}

			library.effects[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `parseEffectProfileCOMMON(xml: any): { surfaces: {}; samplers: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ surfaces: {}; samplers: {}; }`

**Calls:**

- `parseEffectNewparam`
- `parseEffectTechnique`
- `parseEffectExtra`

<details><summary>Code</summary>

```typescript
function parseEffectProfileCOMMON( xml ) {

			const data = {
				surfaces: {},
				samplers: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'newparam':
						parseEffectNewparam( child, data );
						break;

					case 'technique':
						data.technique = parseEffectTechnique( child );
						break;

					case 'extra':
						data.extra = parseEffectExtra( child );
						break;

				}

			}

			return data;

		}
```
</details>

### `parseEffectNewparam(xml: any, data: any): void`

**Parameters:**

- **`xml`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `xml.getAttribute`
- `parseEffectSurface`
- `parseEffectSampler`

<details><summary>Code</summary>

```typescript
function parseEffectNewparam( xml, data ) {

			const sid = xml.getAttribute( 'sid' );

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'surface':
						data.surfaces[ sid ] = parseEffectSurface( child );
						break;

					case 'sampler2D':
						data.samplers[ sid ] = parseEffectSampler( child );
						break;

				}

			}

		}
```
</details>

### `parseEffectSurface(xml: any): { init_from: any; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ init_from: any; }`

<details><summary>Code</summary>

```typescript
function parseEffectSurface( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'init_from':
						data.init_from = child.textContent;
						break;

				}

			}

			return data;

		}
```
</details>

### `parseEffectSampler(xml: any): { source: any; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ source: any; }`

<details><summary>Code</summary>

```typescript
function parseEffectSampler( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'source':
						data.source = child.textContent;
						break;

				}

			}

			return data;

		}
```
</details>

### `parseEffectTechnique(xml: any): { type: any; parameters: {}; extra: { technique: {}; }; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ type: any; parameters: {}; extra: { technique: {}; }; }`

**Calls:**

- `parseEffectParameters`
- `parseEffectExtra`

<details><summary>Code</summary>

```typescript
function parseEffectTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'constant':
					case 'lambert':
					case 'blinn':
					case 'phong':
						data.type = child.nodeName;
						data.parameters = parseEffectParameters( child );
						break;

					case 'extra':
						data.extra = parseEffectExtra( child );
						break;

				}

			}

			return data;

		}
```
</details>

### `parseEffectParameters(xml: any): {}`

**Parameters:**

- **`xml`** `any`

**Returns:** `{}`

**Calls:**

- `parseEffectParameter`
- `child.hasAttribute`
- `child.getAttribute`

<details><summary>Code</summary>

```typescript
function parseEffectParameters( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'emission':
					case 'diffuse':
					case 'specular':
					case 'bump':
					case 'ambient':
					case 'shininess':
					case 'transparency':
						data[ child.nodeName ] = parseEffectParameter( child );
						break;
					case 'transparent':
						data[ child.nodeName ] = {
							opaque: child.hasAttribute( 'opaque' ) ? child.getAttribute( 'opaque' ) : 'A_ONE',
							data: parseEffectParameter( child )
						};
						break;

				}

			}

			return data;

		}
```
</details>

### `parseEffectParameter(xml: any): {}`

**Parameters:**

- **`xml`** `any`

**Returns:** `{}`

**Calls:**

- `parseFloats`
- `parseFloat`
- `child.getAttribute`
- `parseEffectParameterTexture`

<details><summary>Code</summary>

```typescript
function parseEffectParameter( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'color':
						data[ child.nodeName ] = parseFloats( child.textContent );
						break;

					case 'float':
						data[ child.nodeName ] = parseFloat( child.textContent );
						break;

					case 'texture':
						data[ child.nodeName ] = { id: child.getAttribute( 'texture' ), extra: parseEffectParameterTexture( child ) };
						break;

				}

			}

			return data;

		}
```
</details>

### `parseEffectParameterTexture(xml: any): { technique: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ technique: {}; }`

**Calls:**

- `parseEffectParameterTextureExtra`

<details><summary>Code</summary>

```typescript
function parseEffectParameterTexture( xml ) {

			const data = {
				technique: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'extra':
						parseEffectParameterTextureExtra( child, data );
						break;

				}

			}

			return data;

		}
```
</details>

### `parseEffectParameterTextureExtra(xml: any, data: any): void`

**Parameters:**

- **`xml`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `parseEffectParameterTextureExtraTechnique`

<details><summary>Code</summary>

```typescript
function parseEffectParameterTextureExtra( xml, data ) {

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique':
						parseEffectParameterTextureExtraTechnique( child, data );
						break;

				}

			}

		}
```
</details>

### `parseEffectParameterTextureExtraTechnique(xml: any, data: any): void`

**Parameters:**

- **`xml`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `parseFloat`
- `child.textContent.toUpperCase`
- `parseInt`
- `parseEffectExtraTechniqueBump`

**Internal Comments:**
```
// some files have values for wrapU/wrapV which become NaN via parseInt
```

<details><summary>Code</summary>

```typescript
function parseEffectParameterTextureExtraTechnique( xml, data ) {

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'repeatU':
					case 'repeatV':
					case 'offsetU':
					case 'offsetV':
						data.technique[ child.nodeName ] = parseFloat( child.textContent );
						break;

					case 'wrapU':
					case 'wrapV':

						// some files have values for wrapU/wrapV which become NaN via parseInt

						if ( child.textContent.toUpperCase() === 'TRUE' ) {

							data.technique[ child.nodeName ] = 1;

						} else if ( child.textContent.toUpperCase() === 'FALSE' ) {

							data.technique[ child.nodeName ] = 0;

						} else {

							data.technique[ child.nodeName ] = parseInt( child.textContent );

						}

						break;

					case 'bump':
						data[ child.nodeName ] = parseEffectExtraTechniqueBump( child );
						break;

				}

			}

		}
```
</details>

### `parseEffectExtra(xml: any): { technique: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ technique: {}; }`

**Calls:**

- `parseEffectExtraTechnique`

<details><summary>Code</summary>

```typescript
function parseEffectExtra( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique':
						data.technique = parseEffectExtraTechnique( child );
						break;

				}

			}

			return data;

		}
```
</details>

### `parseEffectExtraTechnique(xml: any): {}`

**Parameters:**

- **`xml`** `any`

**Returns:** `{}`

**Calls:**

- `parseInt`
- `parseEffectExtraTechniqueBump`

<details><summary>Code</summary>

```typescript
function parseEffectExtraTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'double_sided':
						data[ child.nodeName ] = parseInt( child.textContent );
						break;

					case 'bump':
						data[ child.nodeName ] = parseEffectExtraTechniqueBump( child );
						break;

				}

			}

			return data;

		}
```
</details>

### `parseEffectExtraTechniqueBump(xml: any): {}`

**Parameters:**

- **`xml`** `any`

**Returns:** `{}`

**Calls:**

- `child.getAttribute`
- `parseEffectParameterTexture`

<details><summary>Code</summary>

```typescript
function parseEffectExtraTechniqueBump( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'texture':
						data[ child.nodeName ] = { id: child.getAttribute( 'texture' ), texcoord: child.getAttribute( 'texcoord' ), extra: parseEffectParameterTexture( child ) };
						break;

				}

			}

			return data;

		}
```
</details>

### `buildEffect(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function buildEffect( data ) {

			return data;

		}
```
</details>

### `getEffect(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getEffect( id ) {

			return getBuild( library.effects[ id ], buildEffect );

		}
```
</details>

### `parseMaterial(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `xml.getAttribute`
- `parseId`
- `child.getAttribute`

<details><summary>Code</summary>

```typescript
function parseMaterial( xml ) {

			const data = {
				name: xml.getAttribute( 'name' )
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'instance_effect':
						data.url = parseId( child.getAttribute( 'url' ) );
						break;

				}

			}

			library.materials[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `getTextureLoader(image: any): any`

**Parameters:**

- **`image`** `any`

**Returns:** `any`

**Calls:**

- `image.slice`
- `image.lastIndexOf`
- `extension.toLowerCase`

<details><summary>Code</summary>

```typescript
function getTextureLoader( image ) {

			let loader;

			let extension = image.slice( ( image.lastIndexOf( '.' ) - 1 >>> 0 ) + 2 ); // http://www.jstips.co/en/javascript/get-file-extension/
			extension = extension.toLowerCase();

			switch ( extension ) {

				case 'tga':
					loader = tgaLoader;
					break;

				default:
					loader = textureLoader;

			}

			return loader;

		}
```
</details>

### `buildMaterial(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `getEffect`
- `getImage`
- `console.warn`
- `getTextureLoader`
- `loader.load`
- `isEmpty`
- `texture.offset.set`
- `texture.repeat.set`
- `material.color.fromArray`
- `getTexture`
- `material.specular.fromArray`
- `material.emissive.fromArray`
- `ColorManagement.colorSpaceToWorking`

**Internal Comments:**
```
// get image
// create texture if image is available
// (x3)
// <transparency> does not exist but <transparent>
// <transparent> does not exist but <transparency>
// handle case if a texture exists but no color
// we do not set an alpha map (see #13792) (x4)
```

<details><summary>Code</summary>

```typescript
function buildMaterial( data ) {

			const effect = getEffect( data.url );
			const technique = effect.profile.technique;

			let material;

			switch ( technique.type ) {

				case 'phong':
				case 'blinn':
					material = new MeshPhongMaterial();
					break;

				case 'lambert':
					material = new MeshLambertMaterial();
					break;

				default:
					material = new MeshBasicMaterial();
					break;

			}

			material.name = data.name || '';

			function getTexture( textureObject, colorSpace = null ) {

				const sampler = effect.profile.samplers[ textureObject.id ];
				let image = null;

				// get image

				if ( sampler !== undefined ) {

					const surface = effect.profile.surfaces[ sampler.source ];
					image = getImage( surface.init_from );

				} else {

					console.warn( 'THREE.ColladaLoader: Undefined sampler. Access image directly (see #12530).' );
					image = getImage( textureObject.id );

				}

				// create texture if image is available

				if ( image !== null ) {

					const loader = getTextureLoader( image );

					if ( loader !== undefined ) {

						const texture = loader.load( image );

						const extra = textureObject.extra;

						if ( extra !== undefined && extra.technique !== undefined && isEmpty( extra.technique ) === false ) {

							const technique = extra.technique;

							texture.wrapS = technique.wrapU ? RepeatWrapping : ClampToEdgeWrapping;
							texture.wrapT = technique.wrapV ? RepeatWrapping : ClampToEdgeWrapping;

							texture.offset.set( technique.offsetU || 0, technique.offsetV || 0 );
							texture.repeat.set( technique.repeatU || 1, technique.repeatV || 1 );

						} else {

							texture.wrapS = RepeatWrapping;
							texture.wrapT = RepeatWrapping;

						}

						if ( colorSpace !== null ) {

							texture.colorSpace = colorSpace;

						}

						return texture;

					} else {

						console.warn( 'THREE.ColladaLoader: Loader for texture %s not found.', image );

						return null;

					}

				} else {

					console.warn( 'THREE.ColladaLoader: Couldn\'t create texture with ID:', textureObject.id );

					return null;

				}

			}

			const parameters = technique.parameters;

			for ( const key in parameters ) {

				const parameter = parameters[ key ];

				switch ( key ) {

					case 'diffuse':
						if ( parameter.color ) material.color.fromArray( parameter.color );
						if ( parameter.texture ) material.map = getTexture( parameter.texture, SRGBColorSpace );
						break;
					case 'specular':
						if ( parameter.color && material.specular ) material.specular.fromArray( parameter.color );
						if ( parameter.texture ) material.specularMap = getTexture( parameter.texture );
						break;
					case 'bump':
						if ( parameter.texture ) material.normalMap = getTexture( parameter.texture );
						break;
					case 'ambient':
						if ( parameter.texture ) material.lightMap = getTexture( parameter.texture, SRGBColorSpace );
						break;
					case 'shininess':
						if ( parameter.float && material.shininess ) material.shininess = parameter.float;
						break;
					case 'emission':
						if ( parameter.color && material.emissive ) material.emissive.fromArray( parameter.color );
						if ( parameter.texture ) material.emissiveMap = getTexture( parameter.texture, SRGBColorSpace );
						break;

				}

			}

			ColorManagement.colorSpaceToWorking( material.color, SRGBColorSpace );
			if ( material.specular ) ColorManagement.colorSpaceToWorking( material.specular, SRGBColorSpace );
			if ( material.emissive ) ColorManagement.colorSpaceToWorking( material.emissive, SRGBColorSpace );

			//

			let transparent = parameters[ 'transparent' ];
			let transparency = parameters[ 'transparency' ];

			// <transparency> does not exist but <transparent>

			if ( transparency === undefined && transparent ) {

				transparency = {
					float: 1
				};

			}

			// <transparent> does not exist but <transparency>

			if ( transparent === undefined && transparency ) {

				transparent = {
					opaque: 'A_ONE',
					data: {
						color: [ 1, 1, 1, 1 ]
					} };

			}

			if ( transparent && transparency ) {

				// handle case if a texture exists but no color

				if ( transparent.data.texture ) {

					// we do not set an alpha map (see #13792)

					material.transparent = true;

				} else {

					const color = transparent.data.color;

					switch ( transparent.opaque ) {

						case 'A_ONE':
							material.opacity = color[ 3 ] * transparency.float;
							break;
						case 'RGB_ZERO':
							material.opacity = 1 - ( color[ 0 ] * transparency.float );
							break;
						case 'A_ZERO':
							material.opacity = 1 - ( color[ 3 ] * transparency.float );
							break;
						case 'RGB_ONE':
							material.opacity = color[ 0 ] * transparency.float;
							break;
						default:
							console.warn( 'THREE.ColladaLoader: Invalid opaque type "%s" of transparent tag.', transparent.opaque );

					}

					if ( material.opacity < 1 ) material.transparent = true;

				}

			}

			//


			if ( technique.extra !== undefined && technique.extra.technique !== undefined ) {

				const techniques = technique.extra.technique;

				for ( const k in techniques ) {

					const v = techniques[ k ];

					switch ( k ) {

						case 'double_sided':
							material.side = ( v === 1 ? DoubleSide : FrontSide );
							break;

						case 'bump':
							material.normalMap = getTexture( v.texture );
							material.normalScale = new Vector2( 1, 1 );
							break;

					}

				}

			}

			return material;

		}
```
</details>

### `getTexture(textureObject: any, colorSpace: any): any`

**Parameters:**

- **`textureObject`** `any`
- **`colorSpace`** `any`

**Returns:** `any`

**Calls:**

- `getImage`
- `console.warn`
- `getTextureLoader`
- `loader.load`
- `isEmpty`
- `texture.offset.set`
- `texture.repeat.set`

**Internal Comments:**
```
// get image
// create texture if image is available
```

<details><summary>Code</summary>

```typescript
function getTexture( textureObject, colorSpace = null ) {

				const sampler = effect.profile.samplers[ textureObject.id ];
				let image = null;

				// get image

				if ( sampler !== undefined ) {

					const surface = effect.profile.surfaces[ sampler.source ];
					image = getImage( surface.init_from );

				} else {

					console.warn( 'THREE.ColladaLoader: Undefined sampler. Access image directly (see #12530).' );
					image = getImage( textureObject.id );

				}

				// create texture if image is available

				if ( image !== null ) {

					const loader = getTextureLoader( image );

					if ( loader !== undefined ) {

						const texture = loader.load( image );

						const extra = textureObject.extra;

						if ( extra !== undefined && extra.technique !== undefined && isEmpty( extra.technique ) === false ) {

							const technique = extra.technique;

							texture.wrapS = technique.wrapU ? RepeatWrapping : ClampToEdgeWrapping;
							texture.wrapT = technique.wrapV ? RepeatWrapping : ClampToEdgeWrapping;

							texture.offset.set( technique.offsetU || 0, technique.offsetV || 0 );
							texture.repeat.set( technique.repeatU || 1, technique.repeatV || 1 );

						} else {

							texture.wrapS = RepeatWrapping;
							texture.wrapT = RepeatWrapping;

						}

						if ( colorSpace !== null ) {

							texture.colorSpace = colorSpace;

						}

						return texture;

					} else {

						console.warn( 'THREE.ColladaLoader: Loader for texture %s not found.', image );

						return null;

					}

				} else {

					console.warn( 'THREE.ColladaLoader: Couldn\'t create texture with ID:', textureObject.id );

					return null;

				}

			}
```
</details>

### `getMaterial(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getMaterial( id ) {

			return getBuild( library.materials[ id ], buildMaterial );

		}
```
</details>

### `parseCamera(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `xml.getAttribute`
- `parseCameraOptics`

<details><summary>Code</summary>

```typescript
function parseCamera( xml ) {

			const data = {
				name: xml.getAttribute( 'name' )
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'optics':
						data.optics = parseCameraOptics( child );
						break;

				}

			}

			library.cameras[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `parseCameraOptics(xml: any): {}`

**Parameters:**

- **`xml`** `any`

**Returns:** `{}`

**Calls:**

- `parseCameraTechnique`

<details><summary>Code</summary>

```typescript
function parseCameraOptics( xml ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'technique_common':
						return parseCameraTechnique( child );

				}

			}

			return {};

		}
```
</details>

### `parseCameraTechnique(xml: any): { technique: any; parameters: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ technique: any; parameters: {}; }`

**Calls:**

- `parseCameraParameters`

<details><summary>Code</summary>

```typescript
function parseCameraTechnique( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'perspective':
					case 'orthographic':

						data.technique = child.nodeName;
						data.parameters = parseCameraParameters( child );

						break;

				}

			}

			return data;

		}
```
</details>

### `parseCameraParameters(xml: any): {}`

**Parameters:**

- **`xml`** `any`

**Returns:** `{}`

**Calls:**

- `parseFloat`

<details><summary>Code</summary>

```typescript
function parseCameraParameters( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'xfov':
					case 'yfov':
					case 'xmag':
					case 'ymag':
					case 'znear':
					case 'zfar':
					case 'aspect_ratio':
						data[ child.nodeName ] = parseFloat( child.textContent );
						break;

				}

			}

			return data;

		}
```
</details>

### `buildCamera(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function buildCamera( data ) {

			let camera;

			switch ( data.optics.technique ) {

				case 'perspective':
					camera = new PerspectiveCamera(
						data.optics.parameters.yfov,
						data.optics.parameters.aspect_ratio,
						data.optics.parameters.znear,
						data.optics.parameters.zfar
					);
					break;

				case 'orthographic':
					let ymag = data.optics.parameters.ymag;
					let xmag = data.optics.parameters.xmag;
					const aspectRatio = data.optics.parameters.aspect_ratio;

					xmag = ( xmag === undefined ) ? ( ymag * aspectRatio ) : xmag;
					ymag = ( ymag === undefined ) ? ( xmag / aspectRatio ) : ymag;

					xmag *= 0.5;
					ymag *= 0.5;

					camera = new OrthographicCamera(
						- xmag, xmag, ymag, - ymag, // left, right, top, bottom
						data.optics.parameters.znear,
						data.optics.parameters.zfar
					);
					break;

				default:
					camera = new PerspectiveCamera();
					break;

			}

			camera.name = data.name || '';

			return camera;

		}
```
</details>

### `getCamera(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`
- `console.warn`

<details><summary>Code</summary>

```typescript
function getCamera( id ) {

			const data = library.cameras[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildCamera );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find camera with ID:', id );

			return null;

		}
```
</details>

### `parseLight(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `parseLightTechnique`
- `xml.getAttribute`

<details><summary>Code</summary>

```typescript
function parseLight( xml ) {

			let data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						data = parseLightTechnique( child );
						break;

				}

			}

			library.lights[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `parseLightTechnique(xml: any): { technique: any; parameters: { color: any; falloffAngle: number; distance: number; }; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ technique: any; parameters: { color: any; falloffAngle: number; distance: number; }; }`

**Calls:**

- `parseLightParameters`

<details><summary>Code</summary>

```typescript
function parseLightTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'directional':
					case 'point':
					case 'spot':
					case 'ambient':

						data.technique = child.nodeName;
						data.parameters = parseLightParameters( child );

				}

			}

			return data;

		}
```
</details>

### `parseLightParameters(xml: any): { color: any; falloffAngle: number; distance: number; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ color: any; falloffAngle: number; distance: number; }`

**Calls:**

- `parseFloats`
- `new Color().fromArray`
- `ColorManagement.colorSpaceToWorking`
- `parseFloat`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function parseLightParameters( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'color':
						const array = parseFloats( child.textContent );
						data.color = new Color().fromArray( array );
						ColorManagement.colorSpaceToWorking( data.color, SRGBColorSpace );
						break;

					case 'falloff_angle':
						data.falloffAngle = parseFloat( child.textContent );
						break;

					case 'quadratic_attenuation':
						const f = parseFloat( child.textContent );
						data.distance = f ? Math.sqrt( 1 / f ) : 0;
						break;

				}

			}

			return data;

		}
```
</details>

### `buildLight(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `light.color.copy`

<details><summary>Code</summary>

```typescript
function buildLight( data ) {

			let light;

			switch ( data.technique ) {

				case 'directional':
					light = new DirectionalLight();
					break;

				case 'point':
					light = new PointLight();
					break;

				case 'spot':
					light = new SpotLight();
					break;

				case 'ambient':
					light = new AmbientLight();
					break;

			}

			if ( data.parameters.color ) light.color.copy( data.parameters.color );
			if ( data.parameters.distance ) light.distance = data.parameters.distance;

			return light;

		}
```
</details>

### `getLight(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`
- `console.warn`

<details><summary>Code</summary>

```typescript
function getLight( id ) {

			const data = library.lights[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildLight );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find light with ID:', id );

			return null;

		}
```
</details>

### `parseGeometry(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `xml.getAttribute`
- `getElementsByTagName`
- `child.getAttribute`
- `parseSource`
- `parseGeometryVertices`
- `console.warn`
- `data.primitives.push`
- `parseGeometryPrimitive`
- `console.log`

**Internal Comments:**
```
// the following tags inside geometry are not supported yet (see https://github.com/mrdoob/three.js/pull/12606): convex_mesh, spline, brep
// data.sources[ id ] = data.sources[ parseId( getElementsByTagName( child, 'input' )[ 0 ].getAttribute( 'source' ) ) ]; (x4)
```

<details><summary>Code</summary>

```typescript
function parseGeometry( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ),
				sources: {},
				vertices: {},
				primitives: []
			};

			const mesh = getElementsByTagName( xml, 'mesh' )[ 0 ];

			// the following tags inside geometry are not supported yet (see https://github.com/mrdoob/three.js/pull/12606): convex_mesh, spline, brep
			if ( mesh === undefined ) return;

			for ( let i = 0; i < mesh.childNodes.length; i ++ ) {

				const child = mesh.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				const id = child.getAttribute( 'id' );

				switch ( child.nodeName ) {

					case 'source':
						data.sources[ id ] = parseSource( child );
						break;

					case 'vertices':
						// data.sources[ id ] = data.sources[ parseId( getElementsByTagName( child, 'input' )[ 0 ].getAttribute( 'source' ) ) ];
						data.vertices = parseGeometryVertices( child );
						break;

					case 'polygons':
						console.warn( 'THREE.ColladaLoader: Unsupported primitive type: ', child.nodeName );
						break;

					case 'lines':
					case 'linestrips':
					case 'polylist':
					case 'triangles':
						data.primitives.push( parseGeometryPrimitive( child ) );
						break;

					default:
						console.log( child );

				}

			}

			library.geometries[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `parseSource(xml: any): { array: any[]; stride: number; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ array: any[]; stride: number; }`

**Calls:**

- `parseFloats`
- `parseStrings`
- `getElementsByTagName`
- `parseInt`
- `accessor.getAttribute`

<details><summary>Code</summary>

```typescript
function parseSource( xml ) {

			const data = {
				array: [],
				stride: 3
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'float_array':
						data.array = parseFloats( child.textContent );
						break;

					case 'Name_array':
						data.array = parseStrings( child.textContent );
						break;

					case 'technique_common':
						const accessor = getElementsByTagName( child, 'accessor' )[ 0 ];

						if ( accessor !== undefined ) {

							data.stride = parseInt( accessor.getAttribute( 'stride' ) );

						}

						break;

				}

			}

			return data;

		}
```
</details>

### `parseGeometryVertices(xml: any): {}`

**Parameters:**

- **`xml`** `any`

**Returns:** `{}`

**Calls:**

- `child.getAttribute`
- `parseId`

<details><summary>Code</summary>

```typescript
function parseGeometryVertices( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				data[ child.getAttribute( 'semantic' ) ] = parseId( child.getAttribute( 'source' ) );

			}

			return data;

		}
```
</details>

### `parseGeometryPrimitive(xml: any): { type: any; material: any; count: number; inputs: {}; stride: number; hasUV: boolean; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ type: any; material: any; count: number; inputs: {}; stride: number; hasUV: boolean; }`

**Calls:**

- `xml.getAttribute`
- `parseInt`
- `parseId`
- `child.getAttribute`
- `Math.max`
- `parseInts`

<details><summary>Code</summary>

```typescript
function parseGeometryPrimitive( xml ) {

			const primitive = {
				type: xml.nodeName,
				material: xml.getAttribute( 'material' ),
				count: parseInt( xml.getAttribute( 'count' ) ),
				inputs: {},
				stride: 0,
				hasUV: false
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const id = parseId( child.getAttribute( 'source' ) );
						const semantic = child.getAttribute( 'semantic' );
						const offset = parseInt( child.getAttribute( 'offset' ) );
						const set = parseInt( child.getAttribute( 'set' ) );
						const inputname = ( set > 0 ? semantic + set : semantic );
						primitive.inputs[ inputname ] = { id: id, offset: offset };
						primitive.stride = Math.max( primitive.stride, offset + 1 );
						if ( semantic === 'TEXCOORD' ) primitive.hasUV = true;
						break;

					case 'vcount':
						primitive.vcount = parseInts( child.textContent );
						break;

					case 'p':
						primitive.p = parseInts( child.textContent );
						break;

				}

			}

			return primitive;

		}
```
</details>

### `groupPrimitives(primitives: any): {}`

**Parameters:**

- **`primitives`** `any`

**Returns:** `{}`

**Calls:**

- `build[ primitive.type ].push`

<details><summary>Code</summary>

```typescript
function groupPrimitives( primitives ) {

			const build = {};

			for ( let i = 0; i < primitives.length; i ++ ) {

				const primitive = primitives[ i ];

				if ( build[ primitive.type ] === undefined ) build[ primitive.type ] = [];

				build[ primitive.type ].push( primitive );

			}

			return build;

		}
```
</details>

### `checkUVCoordinates(primitives: any): void`

**Parameters:**

- **`primitives`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function checkUVCoordinates( primitives ) {

			let count = 0;

			for ( let i = 0, l = primitives.length; i < l; i ++ ) {

				const primitive = primitives[ i ];

				if ( primitive.hasUV === true ) {

					count ++;

				}

			}

			if ( count > 0 && count < primitives.length ) {

				primitives.uvsNeedsFix = true;

			}

		}
```
</details>

### `buildGeometry(data: any): {}`

**Parameters:**

- **`data`** `any`

**Returns:** `{}`

**Calls:**

- `groupPrimitives`
- `checkUVCoordinates`
- `buildGeometryType`

**Internal Comments:**
```
// our goal is to create one buffer geometry for a single type of primitives (x2)
// first, we group all primitives by their type (x2)
// second, ensure consistent uv coordinates for each type of primitives (polylist,triangles or lines) (x3)
// third, create a buffer geometry for each type of primitives (x4)
```

<details><summary>Code</summary>

```typescript
function buildGeometry( data ) {

			const build = {};

			const sources = data.sources;
			const vertices = data.vertices;
			const primitives = data.primitives;

			if ( primitives.length === 0 ) return {};

			// our goal is to create one buffer geometry for a single type of primitives
			// first, we group all primitives by their type

			const groupedPrimitives = groupPrimitives( primitives );

			for ( const type in groupedPrimitives ) {

				const primitiveType = groupedPrimitives[ type ];

				// second, ensure consistent uv coordinates for each type of primitives (polylist,triangles or lines)

				checkUVCoordinates( primitiveType );

				// third, create a buffer geometry for each type of primitives

				build[ type ] = buildGeometryType( primitiveType, sources, vertices );

			}

			return build;

		}
```
</details>

### `buildGeometryType(primitives: any, sources: any, vertices: any): { data: any; type: any; materialKeys: any[]; }`

**Parameters:**

- **`primitives`** `any`
- **`sources`** `any`
- **`vertices`** `any`

**Returns:** `{ data: any; type: any; materialKeys: any[]; }`

**Calls:**

- `console.warn`
- `geometry.addGroup`
- `materialKeys.push`
- `buildGeometryData`
- `uv.array.push`
- `geometry.setAttribute`

**Internal Comments:**
```
// groups (x2)
// material
// geometry data
// see #3803
// fill missing uv coordinates (x5)
// build geometry
```

<details><summary>Code</summary>

```typescript
function buildGeometryType( primitives, sources, vertices ) {

			const build = {};

			const position = { array: [], stride: 0 };
			const normal = { array: [], stride: 0 };
			const uv = { array: [], stride: 0 };
			const uv1 = { array: [], stride: 0 };
			const color = { array: [], stride: 0 };

			const skinIndex = { array: [], stride: 4 };
			const skinWeight = { array: [], stride: 4 };

			const geometry = new BufferGeometry();

			const materialKeys = [];

			let start = 0;

			for ( let p = 0; p < primitives.length; p ++ ) {

				const primitive = primitives[ p ];
				const inputs = primitive.inputs;

				// groups

				let count = 0;

				switch ( primitive.type ) {

					case 'lines':
					case 'linestrips':
						count = primitive.count * 2;
						break;

					case 'triangles':
						count = primitive.count * 3;
						break;

					case 'polylist':

						for ( let g = 0; g < primitive.count; g ++ ) {

							const vc = primitive.vcount[ g ];

							switch ( vc ) {

								case 3:
									count += 3; // single triangle
									break;

								case 4:
									count += 6; // quad, subdivided into two triangles
									break;

								default:
									count += ( vc - 2 ) * 3; // polylist with more than four vertices
									break;

							}

						}

						break;

					default:
						console.warn( 'THREE.ColladaLoader: Unknown primitive type:', primitive.type );

				}

				geometry.addGroup( start, count, p );
				start += count;

				// material

				if ( primitive.material ) {

					materialKeys.push( primitive.material );

				}

				// geometry data

				for ( const name in inputs ) {

					const input = inputs[ name ];

					switch ( name )	{

						case 'VERTEX':
							for ( const key in vertices ) {

								const id = vertices[ key ];

								switch ( key ) {

									case 'POSITION':
										const prevLength = position.array.length;
										buildGeometryData( primitive, sources[ id ], input.offset, position.array );
										position.stride = sources[ id ].stride;

										if ( sources.skinWeights && sources.skinIndices ) {

											buildGeometryData( primitive, sources.skinIndices, input.offset, skinIndex.array );
											buildGeometryData( primitive, sources.skinWeights, input.offset, skinWeight.array );

										}

										// see #3803

										if ( primitive.hasUV === false && primitives.uvsNeedsFix === true ) {

											const count = ( position.array.length - prevLength ) / position.stride;

											for ( let i = 0; i < count; i ++ ) {

												// fill missing uv coordinates

												uv.array.push( 0, 0 );

											}

										}

										break;

									case 'NORMAL':
										buildGeometryData( primitive, sources[ id ], input.offset, normal.array );
										normal.stride = sources[ id ].stride;
										break;

									case 'COLOR':
										buildGeometryData( primitive, sources[ id ], input.offset, color.array );
										color.stride = sources[ id ].stride;
										break;

									case 'TEXCOORD':
										buildGeometryData( primitive, sources[ id ], input.offset, uv.array );
										uv.stride = sources[ id ].stride;
										break;

									case 'TEXCOORD1':
										buildGeometryData( primitive, sources[ id ], input.offset, uv1.array );
										uv.stride = sources[ id ].stride;
										break;

									default:
										console.warn( 'THREE.ColladaLoader: Semantic "%s" not handled in geometry build process.', key );

								}

							}

							break;

						case 'NORMAL':
							buildGeometryData( primitive, sources[ input.id ], input.offset, normal.array );
							normal.stride = sources[ input.id ].stride;
							break;

						case 'COLOR':
							buildGeometryData( primitive, sources[ input.id ], input.offset, color.array, true );
							color.stride = sources[ input.id ].stride;
							break;

						case 'TEXCOORD':
							buildGeometryData( primitive, sources[ input.id ], input.offset, uv.array );
							uv.stride = sources[ input.id ].stride;
							break;

						case 'TEXCOORD1':
							buildGeometryData( primitive, sources[ input.id ], input.offset, uv1.array );
							uv1.stride = sources[ input.id ].stride;
							break;

					}

				}

			}

			// build geometry

			if ( position.array.length > 0 ) geometry.setAttribute( 'position', new Float32BufferAttribute( position.array, position.stride ) );
			if ( normal.array.length > 0 ) geometry.setAttribute( 'normal', new Float32BufferAttribute( normal.array, normal.stride ) );
			if ( color.array.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( color.array, color.stride ) );
			if ( uv.array.length > 0 ) geometry.setAttribute( 'uv', new Float32BufferAttribute( uv.array, uv.stride ) );
			if ( uv1.array.length > 0 ) geometry.setAttribute( 'uv1', new Float32BufferAttribute( uv1.array, uv1.stride ) );

			if ( skinIndex.array.length > 0 ) geometry.setAttribute( 'skinIndex', new Float32BufferAttribute( skinIndex.array, skinIndex.stride ) );
			if ( skinWeight.array.length > 0 ) geometry.setAttribute( 'skinWeight', new Float32BufferAttribute( skinWeight.array, skinWeight.stride ) );

			build.data = geometry;
			build.type = primitives[ 0 ].type;
			build.materialKeys = materialKeys;

			return build;

		}
```
</details>

### `buildGeometryData(primitive: any, source: any, offset: any, array: any, isColor: boolean): void`

**Parameters:**

- **`primitive`** `any`
- **`source`** `any`
- **`offset`** `any`
- **`array`** `any`
- **`isColor`** `boolean`

**Returns:** `void`

**Calls:**

- `array.push`
- `tempColor.setRGB`
- `pushVector`

**Internal Comments:**
```
// convert the vertex colors from srgb to linear if present (x2)
```

<details><summary>Code</summary>

```typescript
function buildGeometryData( primitive, source, offset, array, isColor = false ) {

			const indices = primitive.p;
			const stride = primitive.stride;
			const vcount = primitive.vcount;

			function pushVector( i ) {

				let index = indices[ i + offset ] * sourceStride;
				const length = index + sourceStride;

				for ( ; index < length; index ++ ) {

					array.push( sourceArray[ index ] );

				}

				if ( isColor ) {

					// convert the vertex colors from srgb to linear if present
					const startIndex = array.length - sourceStride - 1;
					tempColor.setRGB(
						array[ startIndex + 0 ],
						array[ startIndex + 1 ],
						array[ startIndex + 2 ],
						SRGBColorSpace
					);

					array[ startIndex + 0 ] = tempColor.r;
					array[ startIndex + 1 ] = tempColor.g;
					array[ startIndex + 2 ] = tempColor.b;

				}

			}

			const sourceArray = source.array;
			const sourceStride = source.stride;

			if ( primitive.vcount !== undefined ) {

				let index = 0;

				for ( let i = 0, l = vcount.length; i < l; i ++ ) {

					const count = vcount[ i ];

					if ( count === 4 ) {

						const a = index + stride * 0;
						const b = index + stride * 1;
						const c = index + stride * 2;
						const d = index + stride * 3;

						pushVector( a ); pushVector( b ); pushVector( d );
						pushVector( b ); pushVector( c ); pushVector( d );

					} else if ( count === 3 ) {

						const a = index + stride * 0;
						const b = index + stride * 1;
						const c = index + stride * 2;

						pushVector( a ); pushVector( b ); pushVector( c );

					} else if ( count > 4 ) {

						for ( let k = 1, kl = ( count - 2 ); k <= kl; k ++ ) {

							const a = index + stride * 0;
							const b = index + stride * k;
							const c = index + stride * ( k + 1 );

							pushVector( a ); pushVector( b ); pushVector( c );

						}

					}

					index += stride * count;

				}

			} else {

				for ( let i = 0, l = indices.length; i < l; i += stride ) {

					pushVector( i );

				}

			}

		}
```
</details>

### `pushVector(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `array.push`
- `tempColor.setRGB`

**Internal Comments:**
```
// convert the vertex colors from srgb to linear if present (x2)
```

<details><summary>Code</summary>

```typescript
function pushVector( i ) {

				let index = indices[ i + offset ] * sourceStride;
				const length = index + sourceStride;

				for ( ; index < length; index ++ ) {

					array.push( sourceArray[ index ] );

				}

				if ( isColor ) {

					// convert the vertex colors from srgb to linear if present
					const startIndex = array.length - sourceStride - 1;
					tempColor.setRGB(
						array[ startIndex + 0 ],
						array[ startIndex + 1 ],
						array[ startIndex + 2 ],
						SRGBColorSpace
					);

					array[ startIndex + 0 ] = tempColor.r;
					array[ startIndex + 1 ] = tempColor.g;
					array[ startIndex + 2 ] = tempColor.b;

				}

			}
```
</details>

### `getGeometry(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getGeometry( id ) {

			return getBuild( library.geometries[ id ], buildGeometry );

		}
```
</details>

### `parseKinematicsModel(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `xml.getAttribute`
- `parseKinematicsTechniqueCommon`

<details><summary>Code</summary>

```typescript
function parseKinematicsModel( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				joints: {},
				links: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						parseKinematicsTechniqueCommon( child, data );
						break;

				}

			}

			library.kinematicsModels[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `buildKinematicsModel(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function buildKinematicsModel( data ) {

			if ( data.build !== undefined ) return data.build;

			return data;

		}
```
</details>

### `getKinematicsModel(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getKinematicsModel( id ) {

			return getBuild( library.kinematicsModels[ id ], buildKinematicsModel );

		}
```
</details>

### `parseKinematicsTechniqueCommon(xml: any, data: any): void`

**Parameters:**

- **`xml`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `child.getAttribute`
- `parseKinematicsJoint`
- `data.links.push`
- `parseKinematicsLink`

<details><summary>Code</summary>

```typescript
function parseKinematicsTechniqueCommon( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'joint':
						data.joints[ child.getAttribute( 'sid' ) ] = parseKinematicsJoint( child );
						break;

					case 'link':
						data.links.push( parseKinematicsLink( child ) );
						break;

				}

			}

		}
```
</details>

### `parseKinematicsJoint(xml: any): { sid: any; name: any; axis: any; limits: { min: number; max: number; }; type: any; static: boolean; zeroPosition: number; middlePosition: number; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ sid: any; name: any; axis: any; limits: { min: number; max: number; }; type: any; static: boolean; zeroPosition: number; middlePosition: number; }`

**Calls:**

- `parseKinematicsJointParameter`

<details><summary>Code</summary>

```typescript
function parseKinematicsJoint( xml ) {

			let data;

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'prismatic':
					case 'revolute':
						data = parseKinematicsJointParameter( child );
						break;

				}

			}

			return data;

		}
```
</details>

### `parseKinematicsJointParameter(xml: any): { sid: any; name: any; axis: any; limits: { min: number; max: number; }; type: any; static: boolean; zeroPosition: number; middlePosition: number; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ sid: any; name: any; axis: any; limits: { min: number; max: number; }; type: any; static: boolean; zeroPosition: number; middlePosition: number; }`

**Calls:**

- `xml.getAttribute`
- `parseFloats`
- `data.axis.fromArray`
- `child.getElementsByTagName`
- `parseFloat`

**Internal Comments:**
```
// if min is equal to or greater than max, consider the joint static
// calculate middle position (x4)
```

<details><summary>Code</summary>

```typescript
function parseKinematicsJointParameter( xml ) {

			const data = {
				sid: xml.getAttribute( 'sid' ),
				name: xml.getAttribute( 'name' ) || '',
				axis: new Vector3(),
				limits: {
					min: 0,
					max: 0
				},
				type: xml.nodeName,
				static: false,
				zeroPosition: 0,
				middlePosition: 0
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'axis':
						const array = parseFloats( child.textContent );
						data.axis.fromArray( array );
						break;
					case 'limits':
						const max = child.getElementsByTagName( 'max' )[ 0 ];
						const min = child.getElementsByTagName( 'min' )[ 0 ];

						data.limits.max = parseFloat( max.textContent );
						data.limits.min = parseFloat( min.textContent );
						break;

				}

			}

			// if min is equal to or greater than max, consider the joint static

			if ( data.limits.min >= data.limits.max ) {

				data.static = true;

			}

			// calculate middle position

			data.middlePosition = ( data.limits.min + data.limits.max ) / 2.0;

			return data;

		}
```
</details>

### `parseKinematicsLink(xml: any): { sid: any; name: any; attachments: any[]; transforms: any[]; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ sid: any; name: any; attachments: any[]; transforms: any[]; }`

**Calls:**

- `xml.getAttribute`
- `data.attachments.push`
- `parseKinematicsAttachment`
- `data.transforms.push`
- `parseKinematicsTransform`

<details><summary>Code</summary>

```typescript
function parseKinematicsLink( xml ) {

			const data = {
				sid: xml.getAttribute( 'sid' ),
				name: xml.getAttribute( 'name' ) || '',
				attachments: [],
				transforms: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'attachment_full':
						data.attachments.push( parseKinematicsAttachment( child ) );
						break;

					case 'matrix':
					case 'translate':
					case 'rotate':
						data.transforms.push( parseKinematicsTransform( child ) );
						break;

				}

			}

			return data;

		}
```
</details>

### `parseKinematicsAttachment(xml: any): { joint: any; transforms: any[]; links: any[]; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ joint: any; transforms: any[]; links: any[]; }`

**Calls:**

- `xml.getAttribute( 'joint' ).split( '/' ).pop`
- `data.links.push`
- `parseKinematicsLink`
- `data.transforms.push`
- `parseKinematicsTransform`

<details><summary>Code</summary>

```typescript
function parseKinematicsAttachment( xml ) {

			const data = {
				joint: xml.getAttribute( 'joint' ).split( '/' ).pop(),
				transforms: [],
				links: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'link':
						data.links.push( parseKinematicsLink( child ) );
						break;

					case 'matrix':
					case 'translate':
					case 'rotate':
						data.transforms.push( parseKinematicsTransform( child ) );
						break;

				}

			}

			return data;

		}
```
</details>

### `parseKinematicsTransform(xml: any): { type: any; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ type: any; }`

**Calls:**

- `parseFloats`
- `data.obj.fromArray( array ).transpose`
- `data.obj.fromArray`
- `MathUtils.degToRad`

<details><summary>Code</summary>

```typescript
function parseKinematicsTransform( xml ) {

			const data = {
				type: xml.nodeName
			};

			const array = parseFloats( xml.textContent );

			switch ( data.type ) {

				case 'matrix':
					data.obj = new Matrix4();
					data.obj.fromArray( array ).transpose();
					break;

				case 'translate':
					data.obj = new Vector3();
					data.obj.fromArray( array );
					break;

				case 'rotate':
					data.obj = new Vector3();
					data.obj.fromArray( array );
					data.angle = MathUtils.degToRad( array[ 3 ] );
					break;

			}

			return data;

		}
```
</details>

### `parsePhysicsModel(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `xml.getAttribute`
- `child.getAttribute`
- `parsePhysicsRigidBody`

<details><summary>Code</summary>

```typescript
function parsePhysicsModel( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				rigidBodies: {}
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'rigid_body':
						data.rigidBodies[ child.getAttribute( 'name' ) ] = {};
						parsePhysicsRigidBody( child, data.rigidBodies[ child.getAttribute( 'name' ) ] );
						break;

				}

			}

			library.physicsModels[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `parsePhysicsRigidBody(xml: any, data: any): void`

**Parameters:**

- **`xml`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `parsePhysicsTechniqueCommon`

<details><summary>Code</summary>

```typescript
function parsePhysicsRigidBody( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						parsePhysicsTechniqueCommon( child, data );
						break;

				}

			}

		}
```
</details>

### `parsePhysicsTechniqueCommon(xml: any, data: any): void`

**Parameters:**

- **`xml`** `any`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `parseFloats`

<details><summary>Code</summary>

```typescript
function parsePhysicsTechniqueCommon( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'inertia':
						data.inertia = parseFloats( child.textContent );
						break;

					case 'mass':
						data.mass = parseFloats( child.textContent )[ 0 ];
						break;

				}

			}

		}
```
</details>

### `parseKinematicsScene(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `data.bindJointAxis.push`
- `parseKinematicsBindJointAxis`
- `parseId`
- `xml.getAttribute`

<details><summary>Code</summary>

```typescript
function parseKinematicsScene( xml ) {

			const data = {
				bindJointAxis: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'bind_joint_axis':
						data.bindJointAxis.push( parseKinematicsBindJointAxis( child ) );
						break;

				}

			}

			library.kinematicsScenes[ parseId( xml.getAttribute( 'url' ) ) ] = data;

		}
```
</details>

### `parseKinematicsBindJointAxis(xml: any): { target: any; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ target: any; }`

**Calls:**

- `xml.getAttribute( 'target' ).split( '/' ).pop`
- `child.getElementsByTagName`
- `data.axis.split( 'inst_' ).pop().split`
- `tmpJointIndex.substring`

<details><summary>Code</summary>

```typescript
function parseKinematicsBindJointAxis( xml ) {

			const data = {
				target: xml.getAttribute( 'target' ).split( '/' ).pop()
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'axis':
						const param = child.getElementsByTagName( 'param' )[ 0 ];
						data.axis = param.textContent;
						const tmpJointIndex = data.axis.split( 'inst_' ).pop().split( 'axis' )[ 0 ];
						data.jointIndex = tmpJointIndex.substring( 0, tmpJointIndex.length - 1 );
						break;

				}

			}

			return data;

		}
```
</details>

### `buildKinematicsScene(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function buildKinematicsScene( data ) {

			if ( data.build !== undefined ) return data.build;

			return data;

		}
```
</details>

### `getKinematicsScene(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getKinematicsScene( id ) {

			return getBuild( library.kinematicsScenes[ id ], buildKinematicsScene );

		}
```
</details>

### `setupKinematics(): void`

**Returns:** `void`

**Calls:**

- `Object.keys`
- `getKinematicsModel`
- `getKinematicsScene`
- `getVisualScene`
- `collada.querySelector`
- `connect`
- `visualElement.getAttribute`
- `visualScene.traverse`
- `buildTransformList`
- `console.warn`
- `matrix.identity`
- `transform.sid.indexOf`
- `matrix.multiply`
- `m0.makeRotationAxis`
- `MathUtils.degToRad`
- `m0.makeTranslation`
- `matrix.scale`
- `object.matrix.copy`
- `object.matrix.decompose`
- `console.log`

**Internal Comments:**
```
// the result of the following query is an element of type 'translate', 'rotate','scale' or 'matrix' (x2)
// get the parent of the transform element (x2)
// connect the joint of the kinematics model with the element in the visual scene (x3)
// each update, we have to apply all transforms in the correct order
// if there is a connection of the transform node with a joint, apply the joint value
```

<details><summary>Code</summary>

```typescript
function setupKinematics() {

			const kinematicsModelId = Object.keys( library.kinematicsModels )[ 0 ];
			const kinematicsSceneId = Object.keys( library.kinematicsScenes )[ 0 ];
			const visualSceneId = Object.keys( library.visualScenes )[ 0 ];

			if ( kinematicsModelId === undefined || kinematicsSceneId === undefined ) return;

			const kinematicsModel = getKinematicsModel( kinematicsModelId );
			const kinematicsScene = getKinematicsScene( kinematicsSceneId );
			const visualScene = getVisualScene( visualSceneId );

			const bindJointAxis = kinematicsScene.bindJointAxis;
			const jointMap = {};

			for ( let i = 0, l = bindJointAxis.length; i < l; i ++ ) {

				const axis = bindJointAxis[ i ];

				// the result of the following query is an element of type 'translate', 'rotate','scale' or 'matrix'

				const targetElement = collada.querySelector( '[sid="' + axis.target + '"]' );

				if ( targetElement ) {

					// get the parent of the transform element

					const parentVisualElement = targetElement.parentElement;

					// connect the joint of the kinematics model with the element in the visual scene

					connect( axis.jointIndex, parentVisualElement );

				}

			}

			function connect( jointIndex, visualElement ) {

				const visualElementName = visualElement.getAttribute( 'name' );
				const joint = kinematicsModel.joints[ jointIndex ];

				visualScene.traverse( function ( object ) {

					if ( object.name === visualElementName ) {

						jointMap[ jointIndex ] = {
							object: object,
							transforms: buildTransformList( visualElement ),
							joint: joint,
							position: joint.zeroPosition
						};

					}

				} );

			}

			const m0 = new Matrix4();

			kinematics = {

				joints: kinematicsModel && kinematicsModel.joints,

				getJointValue: function ( jointIndex ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						return jointData.position;

					} else {

						console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' doesn\'t exist.' );

					}

				},

				setJointValue: function ( jointIndex, value ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						const joint = jointData.joint;

						if ( value > joint.limits.max || value < joint.limits.min ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' value ' + value + ' outside of limits (min: ' + joint.limits.min + ', max: ' + joint.limits.max + ').' );

						} else if ( joint.static ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' is static.' );

						} else {

							const object = jointData.object;
							const axis = joint.axis;
							const transforms = jointData.transforms;

							matrix.identity();

							// each update, we have to apply all transforms in the correct order

							for ( let i = 0; i < transforms.length; i ++ ) {

								const transform = transforms[ i ];

								// if there is a connection of the transform node with a joint, apply the joint value

								if ( transform.sid && transform.sid.indexOf( jointIndex ) !== - 1 ) {

									switch ( joint.type ) {

										case 'revolute':
											matrix.multiply( m0.makeRotationAxis( axis, MathUtils.degToRad( value ) ) );
											break;

										case 'prismatic':
											matrix.multiply( m0.makeTranslation( axis.x * value, axis.y * value, axis.z * value ) );
											break;

										default:
											console.warn( 'THREE.ColladaLoader: Unknown joint type: ' + joint.type );
											break;

									}

								} else {

									switch ( transform.type ) {

										case 'matrix':
											matrix.multiply( transform.obj );
											break;

										case 'translate':
											matrix.multiply( m0.makeTranslation( transform.obj.x, transform.obj.y, transform.obj.z ) );
											break;

										case 'scale':
											matrix.scale( transform.obj );
											break;

										case 'rotate':
											matrix.multiply( m0.makeRotationAxis( transform.obj, transform.angle ) );
											break;

									}

								}

							}

							object.matrix.copy( matrix );
							object.matrix.decompose( object.position, object.quaternion, object.scale );

							jointMap[ jointIndex ].position = value;

						}

					} else {

						console.log( 'THREE.ColladaLoader: ' + jointIndex + ' does not exist.' );

					}

				}

			};

		}
```
</details>

### `connect(jointIndex: any, visualElement: any): void`

**Parameters:**

- **`jointIndex`** `any`
- **`visualElement`** `any`

**Returns:** `void`

**Calls:**

- `visualElement.getAttribute`
- `visualScene.traverse`
- `buildTransformList`

<details><summary>Code</summary>

```typescript
function connect( jointIndex, visualElement ) {

				const visualElementName = visualElement.getAttribute( 'name' );
				const joint = kinematicsModel.joints[ jointIndex ];

				visualScene.traverse( function ( object ) {

					if ( object.name === visualElementName ) {

						jointMap[ jointIndex ] = {
							object: object,
							transforms: buildTransformList( visualElement ),
							joint: joint,
							position: joint.zeroPosition
						};

					}

				} );

			}
```
</details>

### `getJointValue(jointIndex: any): any`

**Parameters:**

- **`jointIndex`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function ( jointIndex ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						return jointData.position;

					} else {

						console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' doesn\'t exist.' );

					}

				}
```
</details>

### `setJointValue(jointIndex: any, value: any): void`

**Parameters:**

- **`jointIndex`** `any`
- **`value`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`
- `matrix.identity`
- `transform.sid.indexOf`
- `matrix.multiply`
- `m0.makeRotationAxis`
- `MathUtils.degToRad`
- `m0.makeTranslation`
- `matrix.scale`
- `object.matrix.copy`
- `object.matrix.decompose`
- `console.log`

**Internal Comments:**
```
// each update, we have to apply all transforms in the correct order
// if there is a connection of the transform node with a joint, apply the joint value
```

<details><summary>Code</summary>

```typescript
function ( jointIndex, value ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						const joint = jointData.joint;

						if ( value > joint.limits.max || value < joint.limits.min ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' value ' + value + ' outside of limits (min: ' + joint.limits.min + ', max: ' + joint.limits.max + ').' );

						} else if ( joint.static ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' is static.' );

						} else {

							const object = jointData.object;
							const axis = joint.axis;
							const transforms = jointData.transforms;

							matrix.identity();

							// each update, we have to apply all transforms in the correct order

							for ( let i = 0; i < transforms.length; i ++ ) {

								const transform = transforms[ i ];

								// if there is a connection of the transform node with a joint, apply the joint value

								if ( transform.sid && transform.sid.indexOf( jointIndex ) !== - 1 ) {

									switch ( joint.type ) {

										case 'revolute':
											matrix.multiply( m0.makeRotationAxis( axis, MathUtils.degToRad( value ) ) );
											break;

										case 'prismatic':
											matrix.multiply( m0.makeTranslation( axis.x * value, axis.y * value, axis.z * value ) );
											break;

										default:
											console.warn( 'THREE.ColladaLoader: Unknown joint type: ' + joint.type );
											break;

									}

								} else {

									switch ( transform.type ) {

										case 'matrix':
											matrix.multiply( transform.obj );
											break;

										case 'translate':
											matrix.multiply( m0.makeTranslation( transform.obj.x, transform.obj.y, transform.obj.z ) );
											break;

										case 'scale':
											matrix.scale( transform.obj );
											break;

										case 'rotate':
											matrix.multiply( m0.makeRotationAxis( transform.obj, transform.angle ) );
											break;

									}

								}

							}

							object.matrix.copy( matrix );
							object.matrix.decompose( object.position, object.quaternion, object.scale );

							jointMap[ jointIndex ].position = value;

						}

					} else {

						console.log( 'THREE.ColladaLoader: ' + jointIndex + ' does not exist.' );

					}

				}
```
</details>

### `getJointValue(jointIndex: any): any`

**Parameters:**

- **`jointIndex`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function ( jointIndex ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						return jointData.position;

					} else {

						console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' doesn\'t exist.' );

					}

				}
```
</details>

### `setJointValue(jointIndex: any, value: any): void`

**Parameters:**

- **`jointIndex`** `any`
- **`value`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`
- `matrix.identity`
- `transform.sid.indexOf`
- `matrix.multiply`
- `m0.makeRotationAxis`
- `MathUtils.degToRad`
- `m0.makeTranslation`
- `matrix.scale`
- `object.matrix.copy`
- `object.matrix.decompose`
- `console.log`

**Internal Comments:**
```
// each update, we have to apply all transforms in the correct order
// if there is a connection of the transform node with a joint, apply the joint value
```

<details><summary>Code</summary>

```typescript
function ( jointIndex, value ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						const joint = jointData.joint;

						if ( value > joint.limits.max || value < joint.limits.min ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' value ' + value + ' outside of limits (min: ' + joint.limits.min + ', max: ' + joint.limits.max + ').' );

						} else if ( joint.static ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' is static.' );

						} else {

							const object = jointData.object;
							const axis = joint.axis;
							const transforms = jointData.transforms;

							matrix.identity();

							// each update, we have to apply all transforms in the correct order

							for ( let i = 0; i < transforms.length; i ++ ) {

								const transform = transforms[ i ];

								// if there is a connection of the transform node with a joint, apply the joint value

								if ( transform.sid && transform.sid.indexOf( jointIndex ) !== - 1 ) {

									switch ( joint.type ) {

										case 'revolute':
											matrix.multiply( m0.makeRotationAxis( axis, MathUtils.degToRad( value ) ) );
											break;

										case 'prismatic':
											matrix.multiply( m0.makeTranslation( axis.x * value, axis.y * value, axis.z * value ) );
											break;

										default:
											console.warn( 'THREE.ColladaLoader: Unknown joint type: ' + joint.type );
											break;

									}

								} else {

									switch ( transform.type ) {

										case 'matrix':
											matrix.multiply( transform.obj );
											break;

										case 'translate':
											matrix.multiply( m0.makeTranslation( transform.obj.x, transform.obj.y, transform.obj.z ) );
											break;

										case 'scale':
											matrix.scale( transform.obj );
											break;

										case 'rotate':
											matrix.multiply( m0.makeRotationAxis( transform.obj, transform.angle ) );
											break;

									}

								}

							}

							object.matrix.copy( matrix );
							object.matrix.decompose( object.position, object.quaternion, object.scale );

							jointMap[ jointIndex ].position = value;

						}

					} else {

						console.log( 'THREE.ColladaLoader: ' + jointIndex + ' does not exist.' );

					}

				}
```
</details>

### `buildTransformList(node: any): ({ sid: any; type: any; obj: any; angle?: undefined; } | { sid: any; type: any; obj: any; angle: any; })[]`

**Parameters:**

- **`node`** `any`

**Returns:** `({ sid: any; type: any; obj: any; angle?: undefined; } | { sid: any; type: any; obj: any; angle: any; })[]`

**Calls:**

- `collada.querySelector`
- `parseFloats`
- `new Matrix4().fromArray( array ).transpose`
- `transforms.push`
- `child.getAttribute`
- `new Vector3().fromArray`
- `MathUtils.degToRad`

<details><summary>Code</summary>

```typescript
function buildTransformList( node ) {

			const transforms = [];

			const xml = collada.querySelector( '[id="' + node.id + '"]' );

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let array, vector;

				switch ( child.nodeName ) {

					case 'matrix':
						array = parseFloats( child.textContent );
						const matrix = new Matrix4().fromArray( array ).transpose();
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: matrix
						} );
						break;

					case 'translate':
					case 'scale':
						array = parseFloats( child.textContent );
						vector = new Vector3().fromArray( array );
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: vector
						} );
						break;

					case 'rotate':
						array = parseFloats( child.textContent );
						vector = new Vector3().fromArray( array );
						const angle = MathUtils.degToRad( array[ 3 ] );
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: vector,
							angle: angle
						} );
						break;

				}

			}

			return transforms;

		}
```
</details>

### `prepareNodes(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `xml.getElementsByTagName`
- `element.hasAttribute`
- `element.setAttribute`
- `generateId`

**Internal Comments:**
```
// ensure all node elements have id attributes
```

<details><summary>Code</summary>

```typescript
function prepareNodes( xml ) {

			const elements = xml.getElementsByTagName( 'node' );

			// ensure all node elements have id attributes

			for ( let i = 0; i < elements.length; i ++ ) {

				const element = elements[ i ];

				if ( element.hasAttribute( 'id' ) === false ) {

					element.setAttribute( 'id', generateId() );

				}

			}

		}
```
</details>

### `parseNode(xml: any): { name: any; type: any; id: any; sid: any; matrix: any; nodes: any[]; instanceCameras: any[]; instanceControllers: any[]; instanceLights: any[]; instanceGeometries: any[]; instanceNodes: any[]; transforms: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ name: any; type: any; id: any; sid: any; matrix: any; nodes: any[]; instanceCameras: any[]; instanceControllers: any[]; instanceLights: any[]; instanceGeometries: any[]; instanceNodes: any[]; transforms: {}; }`

**Calls:**

- `xml.getAttribute`
- `data.nodes.push`
- `child.getAttribute`
- `parseNode`
- `data.instanceCameras.push`
- `parseId`
- `data.instanceControllers.push`
- `parseNodeInstance`
- `data.instanceLights.push`
- `data.instanceGeometries.push`
- `data.instanceNodes.push`
- `parseFloats`
- `data.matrix.multiply`
- `matrix.fromArray( array ).transpose`
- `vector.fromArray`
- `matrix.makeTranslation`
- `MathUtils.degToRad`
- `matrix.makeRotationAxis`
- `data.matrix.scale`
- `console.log`
- `hasNode`
- `console.warn`

<details><summary>Code</summary>

```typescript
function parseNode( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				type: xml.getAttribute( 'type' ),
				id: xml.getAttribute( 'id' ),
				sid: xml.getAttribute( 'sid' ),
				matrix: new Matrix4(),
				nodes: [],
				instanceCameras: [],
				instanceControllers: [],
				instanceLights: [],
				instanceGeometries: [],
				instanceNodes: [],
				transforms: {}
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let array;

				switch ( child.nodeName ) {

					case 'node':
						data.nodes.push( child.getAttribute( 'id' ) );
						parseNode( child );
						break;

					case 'instance_camera':
						data.instanceCameras.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'instance_controller':
						data.instanceControllers.push( parseNodeInstance( child ) );
						break;

					case 'instance_light':
						data.instanceLights.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'instance_geometry':
						data.instanceGeometries.push( parseNodeInstance( child ) );
						break;

					case 'instance_node':
						data.instanceNodes.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'matrix':
						array = parseFloats( child.textContent );
						data.matrix.multiply( matrix.fromArray( array ).transpose() );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'translate':
						array = parseFloats( child.textContent );
						vector.fromArray( array );
						data.matrix.multiply( matrix.makeTranslation( vector.x, vector.y, vector.z ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'rotate':
						array = parseFloats( child.textContent );
						const angle = MathUtils.degToRad( array[ 3 ] );
						data.matrix.multiply( matrix.makeRotationAxis( vector.fromArray( array ), angle ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'scale':
						array = parseFloats( child.textContent );
						data.matrix.scale( vector.fromArray( array ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'extra':
						break;

					default:
						console.log( child );

				}

			}

			if ( hasNode( data.id ) ) {

				console.warn( 'THREE.ColladaLoader: There is already a node with ID %s. Exclude current node from further processing.', data.id );

			} else {

				library.nodes[ data.id ] = data;

			}

			return data;

		}
```
</details>

### `parseNodeInstance(xml: any): { id: any; materials: {}; skeletons: any[]; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ id: any; materials: {}; skeletons: any[]; }`

**Calls:**

- `parseId`
- `xml.getAttribute`
- `child.getElementsByTagName`
- `instance.getAttribute`
- `data.skeletons.push`

<details><summary>Code</summary>

```typescript
function parseNodeInstance( xml ) {

			const data = {
				id: parseId( xml.getAttribute( 'url' ) ),
				materials: {},
				skeletons: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'bind_material':
						const instances = child.getElementsByTagName( 'instance_material' );

						for ( let j = 0; j < instances.length; j ++ ) {

							const instance = instances[ j ];
							const symbol = instance.getAttribute( 'symbol' );
							const target = instance.getAttribute( 'target' );

							data.materials[ symbol ] = parseId( target );

						}

						break;

					case 'skeleton':
						data.skeletons.push( parseId( child.textContent ) );
						break;

					default:
						break;

				}

			}

			return data;

		}
```
</details>

### `buildSkeleton(skeletons: any, joints: any): any`

**Parameters:**

- **`skeletons`** `any`
- **`joints`** `any`

**Returns:** `any`

**Calls:**

- `hasNode`
- `getNode`
- `buildBoneHierarchy`
- `hasVisualScene`
- `console.error`
- `sortedBoneData.push`
- `bones.push`
- `boneInverses.push`

**Internal Comments:**
```
// a skeleton can have multiple root bones. collada expresses this
// situation with multiple "skeleton" tags per controller instance
// handle case where the skeleton refers to the visual scene (#13335) (x2)
// sort bone data (the order is defined in the corresponding controller)
// add unprocessed bone data at the end of the list
// setup arrays for skeleton creation (x2)
```

<details><summary>Code</summary>

```typescript
function buildSkeleton( skeletons, joints ) {

			const boneData = [];
			const sortedBoneData = [];

			let i, j, data;

			// a skeleton can have multiple root bones. collada expresses this
			// situation with multiple "skeleton" tags per controller instance

			for ( i = 0; i < skeletons.length; i ++ ) {

				const skeleton = skeletons[ i ];

				let root;

				if ( hasNode( skeleton ) ) {

					root = getNode( skeleton );
					buildBoneHierarchy( root, joints, boneData );

				} else if ( hasVisualScene( skeleton ) ) {

					// handle case where the skeleton refers to the visual scene (#13335)

					const visualScene = library.visualScenes[ skeleton ];
					const children = visualScene.children;

					for ( let j = 0; j < children.length; j ++ ) {

						const child = children[ j ];

						if ( child.type === 'JOINT' ) {

							const root = getNode( child.id );
							buildBoneHierarchy( root, joints, boneData );

						}

					}

				} else {

					console.error( 'THREE.ColladaLoader: Unable to find root bone of skeleton with ID:', skeleton );

				}

			}

			// sort bone data (the order is defined in the corresponding controller)

			for ( i = 0; i < joints.length; i ++ ) {

				for ( j = 0; j < boneData.length; j ++ ) {

					data = boneData[ j ];

					if ( data.bone.name === joints[ i ].name ) {

						sortedBoneData[ i ] = data;
						data.processed = true;
						break;

					}

				}

			}

			// add unprocessed bone data at the end of the list

			for ( i = 0; i < boneData.length; i ++ ) {

				data = boneData[ i ];

				if ( data.processed === false ) {

					sortedBoneData.push( data );
					data.processed = true;

				}

			}

			// setup arrays for skeleton creation

			const bones = [];
			const boneInverses = [];

			for ( i = 0; i < sortedBoneData.length; i ++ ) {

				data = sortedBoneData[ i ];

				bones.push( data.bone );
				boneInverses.push( data.boneInverse );

			}

			return new Skeleton( bones, boneInverses );

		}
```
</details>

### `buildBoneHierarchy(root: any, joints: any, boneData: any): void`

**Parameters:**

- **`root`** `any`
- **`joints`** `any`
- **`boneData`** `any`

**Returns:** `void`

**Calls:**

- `root.traverse`
- `boneData.push`

**Internal Comments:**
```
// setup bone data from visual scene (x4)
// retrieve the boneInverse from the controller data
// Unfortunately, there can be joints in the visual scene that are not part of the (x3)
// corresponding controller. In this case, we have to create a dummy boneInverse matrix (x3)
// for the respective bone. This bone won't affect any vertices, because there are no skin indices (x3)
// and weights defined for it. But we still have to add the bone to the sorted bone list in order to (x3)
// ensure a correct animation of the model. (x3)
```

<details><summary>Code</summary>

```typescript
function buildBoneHierarchy( root, joints, boneData ) {

			// setup bone data from visual scene

			root.traverse( function ( object ) {

				if ( object.isBone === true ) {

					let boneInverse;

					// retrieve the boneInverse from the controller data

					for ( let i = 0; i < joints.length; i ++ ) {

						const joint = joints[ i ];

						if ( joint.name === object.name ) {

							boneInverse = joint.boneInverse;
							break;

						}

					}

					if ( boneInverse === undefined ) {

						// Unfortunately, there can be joints in the visual scene that are not part of the
						// corresponding controller. In this case, we have to create a dummy boneInverse matrix
						// for the respective bone. This bone won't affect any vertices, because there are no skin indices
						// and weights defined for it. But we still have to add the bone to the sorted bone list in order to
						// ensure a correct animation of the model.

						boneInverse = new Matrix4();

					}

					boneData.push( { bone: object, boneInverse: boneInverse, processed: false } );

				}

			} );

		}
```
</details>

### `buildNode(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `objects.push`
- `getNode`
- `getCamera`
- `instanceCamera.clone`
- `getController`
- `getGeometry`
- `buildObjects`
- `buildSkeleton`
- `object.bind`
- `object.normalizeSkinWeights`
- `getLight`
- `instanceLight.clone`
- `getNode( instanceNodes[ i ] ).clone`
- `object.add`
- `object.matrix.copy`
- `object.matrix.decompose`

**Internal Comments:**
```
// nodes
// instance cameras
// instance controllers
// instance lights
// instance geometries
// a single geometry instance in collada can lead to multiple object3Ds. (x2)
// this is the case when primitives are combined like triangles and lines (x2)
// instance nodes
```

<details><summary>Code</summary>

```typescript
function buildNode( data ) {

			const objects = [];

			const matrix = data.matrix;
			const nodes = data.nodes;
			const type = data.type;
			const instanceCameras = data.instanceCameras;
			const instanceControllers = data.instanceControllers;
			const instanceLights = data.instanceLights;
			const instanceGeometries = data.instanceGeometries;
			const instanceNodes = data.instanceNodes;

			// nodes

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				objects.push( getNode( nodes[ i ] ) );

			}

			// instance cameras

			for ( let i = 0, l = instanceCameras.length; i < l; i ++ ) {

				const instanceCamera = getCamera( instanceCameras[ i ] );

				if ( instanceCamera !== null ) {

					objects.push( instanceCamera.clone() );

				}

			}

			// instance controllers

			for ( let i = 0, l = instanceControllers.length; i < l; i ++ ) {

				const instance = instanceControllers[ i ];
				const controller = getController( instance.id );
				const geometries = getGeometry( controller.id );
				const newObjects = buildObjects( geometries, instance.materials );

				const skeletons = instance.skeletons;
				const joints = controller.skin.joints;

				const skeleton = buildSkeleton( skeletons, joints );

				for ( let j = 0, jl = newObjects.length; j < jl; j ++ ) {

					const object = newObjects[ j ];

					if ( object.isSkinnedMesh ) {

						object.bind( skeleton, controller.skin.bindMatrix );
						object.normalizeSkinWeights();

					}

					objects.push( object );

				}

			}

			// instance lights

			for ( let i = 0, l = instanceLights.length; i < l; i ++ ) {

				const instanceLight = getLight( instanceLights[ i ] );

				if ( instanceLight !== null ) {

					objects.push( instanceLight.clone() );

				}

			}

			// instance geometries

			for ( let i = 0, l = instanceGeometries.length; i < l; i ++ ) {

				const instance = instanceGeometries[ i ];

				// a single geometry instance in collada can lead to multiple object3Ds.
				// this is the case when primitives are combined like triangles and lines

				const geometries = getGeometry( instance.id );
				const newObjects = buildObjects( geometries, instance.materials );

				for ( let j = 0, jl = newObjects.length; j < jl; j ++ ) {

					objects.push( newObjects[ j ] );

				}

			}

			// instance nodes

			for ( let i = 0, l = instanceNodes.length; i < l; i ++ ) {

				objects.push( getNode( instanceNodes[ i ] ).clone() );

			}

			let object;

			if ( nodes.length === 0 && objects.length === 1 ) {

				object = objects[ 0 ];

			} else {

				object = ( type === 'JOINT' ) ? new Bone() : new Group();

				for ( let i = 0; i < objects.length; i ++ ) {

					object.add( objects[ i ] );

				}

			}

			object.name = ( type === 'JOINT' ) ? data.sid : data.name;
			object.matrix.copy( matrix );
			object.matrix.decompose( object.position, object.quaternion, object.scale );

			return object;

		}
```
</details>

### `resolveMaterialBinding(keys: any, instanceMaterials: any): any[]`

**Parameters:**

- **`keys`** `any`
- **`instanceMaterials`** `any`

**Returns:** `any[]`

**Calls:**

- `console.warn`
- `materials.push`
- `getMaterial`

<details><summary>Code</summary>

```typescript
function resolveMaterialBinding( keys, instanceMaterials ) {

			const materials = [];

			for ( let i = 0, l = keys.length; i < l; i ++ ) {

				const id = instanceMaterials[ keys[ i ] ];

				if ( id === undefined ) {

					console.warn( 'THREE.ColladaLoader: Material with key %s not found. Apply fallback material.', keys[ i ] );
					materials.push( fallbackMaterial );

				} else {

					materials.push( getMaterial( id ) );

				}

			}

			return materials;

		}
```
</details>

### `buildObjects(geometries: any, instanceMaterials: any): any[]`

**Parameters:**

- **`geometries`** `any`
- **`instanceMaterials`** `any`

**Returns:** `any[]`

**Calls:**

- `resolveMaterialBinding`
- `materials.push`
- `lineMaterial.color.copy`
- `objects.push`

**Internal Comments:**
```
// handle case if no materials are defined
// Collada allows to use phong and lambert materials with lines. Replacing these cases with LineBasicMaterial.
// copy compatible properties (x5)
// replace material (x4)
// regard skinning (x2)
// choose between a single or multi materials (material array) (x2)
// now create a specific 3D object (x2)
```

<details><summary>Code</summary>

```typescript
function buildObjects( geometries, instanceMaterials ) {

			const objects = [];

			for ( const type in geometries ) {

				const geometry = geometries[ type ];

				const materials = resolveMaterialBinding( geometry.materialKeys, instanceMaterials );

				// handle case if no materials are defined

				if ( materials.length === 0 ) {

					if ( type === 'lines' || type === 'linestrips' ) {

						materials.push( new LineBasicMaterial() );

					} else {

						materials.push( new MeshPhongMaterial() );

					}

				}

				// Collada allows to use phong and lambert materials with lines. Replacing these cases with LineBasicMaterial.

				if ( type === 'lines' || type === 'linestrips' ) {

					for ( let i = 0, l = materials.length; i < l; i ++ ) {

						const material = materials[ i ];

						if ( material.isMeshPhongMaterial === true || material.isMeshLambertMaterial === true ) {

							const lineMaterial = new LineBasicMaterial();

							// copy compatible properties

							lineMaterial.color.copy( material.color );
							lineMaterial.opacity = material.opacity;
							lineMaterial.transparent = material.transparent;

							// replace material

							materials[ i ] = lineMaterial;

						}

					}

				}

				// regard skinning

				const skinning = ( geometry.data.attributes.skinIndex !== undefined );

				// choose between a single or multi materials (material array)

				const material = ( materials.length === 1 ) ? materials[ 0 ] : materials;

				// now create a specific 3D object

				let object;

				switch ( type ) {

					case 'lines':
						object = new LineSegments( geometry.data, material );
						break;

					case 'linestrips':
						object = new Line( geometry.data, material );
						break;

					case 'triangles':
					case 'polylist':
						if ( skinning ) {

							object = new SkinnedMesh( geometry.data, material );

						} else {

							object = new Mesh( geometry.data, material );

						}

						break;

				}

				objects.push( object );

			}

			return objects;

		}
```
</details>

### `hasNode(id: any): boolean`

**Parameters:**

- **`id`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function hasNode( id ) {

			return library.nodes[ id ] !== undefined;

		}
```
</details>

### `getNode(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getNode( id ) {

			return getBuild( library.nodes[ id ], buildNode );

		}
```
</details>

### `parseVisualScene(xml: any): void`

**Parameters:**

- **`xml`** `any`

**Returns:** `void`

**Calls:**

- `xml.getAttribute`
- `prepareNodes`
- `getElementsByTagName`
- `data.children.push`
- `parseNode`

<details><summary>Code</summary>

```typescript
function parseVisualScene( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ),
				children: []
			};

			prepareNodes( xml );

			const elements = getElementsByTagName( xml, 'node' );

			for ( let i = 0; i < elements.length; i ++ ) {

				data.children.push( parseNode( elements[ i ] ) );

			}

			library.visualScenes[ xml.getAttribute( 'id' ) ] = data;

		}
```
</details>

### `buildVisualScene(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `group.add`
- `getNode`

<details><summary>Code</summary>

```typescript
function buildVisualScene( data ) {

			const group = new Group();
			group.name = data.name;

			const children = data.children;

			for ( let i = 0; i < children.length; i ++ ) {

				const child = children[ i ];

				group.add( getNode( child.id ) );

			}

			return group;

		}
```
</details>

### `hasVisualScene(id: any): boolean`

**Parameters:**

- **`id`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function hasVisualScene( id ) {

			return library.visualScenes[ id ] !== undefined;

		}
```
</details>

### `getVisualScene(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `getBuild`

<details><summary>Code</summary>

```typescript
function getVisualScene( id ) {

			return getBuild( library.visualScenes[ id ], buildVisualScene );

		}
```
</details>

### `parseScene(xml: any): any`

**Parameters:**

- **`xml`** `any`

**Returns:** `any`

**Calls:**

- `getElementsByTagName`
- `getVisualScene`
- `parseId`
- `instance.getAttribute`

<details><summary>Code</summary>

```typescript
function parseScene( xml ) {

			const instance = getElementsByTagName( xml, 'instance_visual_scene' )[ 0 ];
			return getVisualScene( parseId( instance.getAttribute( 'url' ) ) );

		}
```
</details>

### `setupAnimations(): void`

**Returns:** `void`

**Calls:**

- `isEmpty`
- `getAnimation`
- `tracks.push`
- `animations.push`
- `getAnimationClip`

**Internal Comments:**
```
// if there are animations but no clips, we create a default clip for playback (x2)
```

<details><summary>Code</summary>

```typescript
function setupAnimations() {

			const clips = library.clips;

			if ( isEmpty( clips ) === true ) {

				if ( isEmpty( library.animations ) === false ) {

					// if there are animations but no clips, we create a default clip for playback

					const tracks = [];

					for ( const id in library.animations ) {

						const animationTracks = getAnimation( id );

						for ( let i = 0, l = animationTracks.length; i < l; i ++ ) {

							tracks.push( animationTracks[ i ] );

						}

					}

					animations.push( new AnimationClip( 'default', - 1, tracks ) );

				}

			} else {

				for ( const id in clips ) {

					animations.push( getAnimationClip( id ) );

				}

			}

		}
```
</details>

### `parserErrorToText(parserError: any): string`

**Parameters:**

- **`parserError`** `any`

**Returns:** `string`

**Calls:**

- `stack.shift`
- `stack.push`
- `result.trim`

<details><summary>Code</summary>

```typescript
function parserErrorToText( parserError ) {

			let result = '';
			const stack = [ parserError ];

			while ( stack.length ) {

				const node = stack.shift();

				if ( node.nodeType === Node.TEXT_NODE ) {

					result += node.textContent;

				} else {

					result += '\n';
					stack.push( ...node.childNodes );

				}

			}

			return result.trim();

		}
```
</details>


---

## Classes

### `ColladaLoader`

<details><summary>Class Code</summary>

```ts
class ColladaLoader extends Loader {

	/**
	 * Starts loading from the given URL and passes the loaded Collada asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({scene:Group,animations:Array<AnimationClip>,kinematics:Object})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( scope.path === '' ) ? LoaderUtils.extractUrlBase( url ) : scope.path;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text, path ) );

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
	 * Parses the given Collada data and returns a result object holding the parsed scene,
	 * an array of animation clips and kinematics.
	 *
	 * @param {string} text - The raw Collada data as a string.
	 * @param {string} path - The asset path.
	 * @return {{scene:Group,animations:Array<AnimationClip>,kinematics:Object}} An object representing the parsed asset.
	 */
	parse( text, path ) {

		function getElementsByTagName( xml, name ) {

			// Non recursive xml.getElementsByTagName() ...

			const array = [];
			const childNodes = xml.childNodes;

			for ( let i = 0, l = childNodes.length; i < l; i ++ ) {

				const child = childNodes[ i ];

				if ( child.nodeName === name ) {

					array.push( child );

				}

			}

			return array;

		}

		function parseStrings( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parts[ i ];

			}

			return array;

		}

		function parseFloats( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parseFloat( parts[ i ] );

			}

			return array;

		}

		function parseInts( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parseInt( parts[ i ] );

			}

			return array;

		}

		function parseId( text ) {

			return text.substring( 1 );

		}

		function generateId() {

			return 'three_default_' + ( count ++ );

		}

		function isEmpty( object ) {

			return Object.keys( object ).length === 0;

		}

		// asset

		function parseAsset( xml ) {

			return {
				unit: parseAssetUnit( getElementsByTagName( xml, 'unit' )[ 0 ] ),
				upAxis: parseAssetUpAxis( getElementsByTagName( xml, 'up_axis' )[ 0 ] )
			};

		}

		function parseAssetUnit( xml ) {

			if ( ( xml !== undefined ) && ( xml.hasAttribute( 'meter' ) === true ) ) {

				return parseFloat( xml.getAttribute( 'meter' ) );

			} else {

				return 1; // default 1 meter

			}

		}

		function parseAssetUpAxis( xml ) {

			return xml !== undefined ? xml.textContent : 'Y_UP';

		}

		// library

		function parseLibrary( xml, libraryName, nodeName, parser ) {

			const library = getElementsByTagName( xml, libraryName )[ 0 ];

			if ( library !== undefined ) {

				const elements = getElementsByTagName( library, nodeName );

				for ( let i = 0; i < elements.length; i ++ ) {

					parser( elements[ i ] );

				}

			}

		}

		function buildLibrary( data, builder ) {

			for ( const name in data ) {

				const object = data[ name ];
				object.build = builder( data[ name ] );

			}

		}

		// get

		function getBuild( data, builder ) {

			if ( data.build !== undefined ) return data.build;

			data.build = builder( data );

			return data.build;

		}

		// animation

		function parseAnimation( xml ) {

			const data = {
				sources: {},
				samplers: {},
				channels: {}
			};

			let hasChildren = false;

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let id;

				switch ( child.nodeName ) {

					case 'source':
						id = child.getAttribute( 'id' );
						data.sources[ id ] = parseSource( child );
						break;

					case 'sampler':
						id = child.getAttribute( 'id' );
						data.samplers[ id ] = parseAnimationSampler( child );
						break;

					case 'channel':
						id = child.getAttribute( 'target' );
						data.channels[ id ] = parseAnimationChannel( child );
						break;

					case 'animation':
						// hierarchy of related animations
						parseAnimation( child );
						hasChildren = true;
						break;

					default:
						console.log( child );

				}

			}

			if ( hasChildren === false ) {

				// since 'id' attributes can be optional, it's necessary to generate a UUID for unique assignment

				library.animations[ xml.getAttribute( 'id' ) || MathUtils.generateUUID() ] = data;

			}

		}

		function parseAnimationSampler( xml ) {

			const data = {
				inputs: {},
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const id = parseId( child.getAttribute( 'source' ) );
						const semantic = child.getAttribute( 'semantic' );
						data.inputs[ semantic ] = id;
						break;

				}

			}

			return data;

		}

		function parseAnimationChannel( xml ) {

			const data = {};

			const target = xml.getAttribute( 'target' );

			// parsing SID Addressing Syntax

			let parts = target.split( '/' );

			const id = parts.shift();
			let sid = parts.shift();

			// check selection syntax

			const arraySyntax = ( sid.indexOf( '(' ) !== - 1 );
			const memberSyntax = ( sid.indexOf( '.' ) !== - 1 );

			if ( memberSyntax ) {

				//  member selection access

				parts = sid.split( '.' );
				sid = parts.shift();
				data.member = parts.shift();

			} else if ( arraySyntax ) {

				// array-access syntax. can be used to express fields in one-dimensional vectors or two-dimensional matrices.

				const indices = sid.split( '(' );
				sid = indices.shift();

				for ( let i = 0; i < indices.length; i ++ ) {

					indices[ i ] = parseInt( indices[ i ].replace( /\)/, '' ) );

				}

				data.indices = indices;

			}

			data.id = id;
			data.sid = sid;

			data.arraySyntax = arraySyntax;
			data.memberSyntax = memberSyntax;

			data.sampler = parseId( xml.getAttribute( 'source' ) );

			return data;

		}

		function buildAnimation( data ) {

			const tracks = [];

			const channels = data.channels;
			const samplers = data.samplers;
			const sources = data.sources;

			for ( const target in channels ) {

				if ( channels.hasOwnProperty( target ) ) {

					const channel = channels[ target ];
					const sampler = samplers[ channel.sampler ];

					const inputId = sampler.inputs.INPUT;
					const outputId = sampler.inputs.OUTPUT;

					const inputSource = sources[ inputId ];
					const outputSource = sources[ outputId ];

					const animation = buildAnimationChannel( channel, inputSource, outputSource );

					createKeyframeTracks( animation, tracks );

				}

			}

			return tracks;

		}

		function getAnimation( id ) {

			return getBuild( library.animations[ id ], buildAnimation );

		}

		function buildAnimationChannel( channel, inputSource, outputSource ) {

			const node = library.nodes[ channel.id ];
			const object3D = getNode( node.id );

			const transform = node.transforms[ channel.sid ];
			const defaultMatrix = node.matrix.clone().transpose();

			let time, stride;
			let i, il, j, jl;

			const data = {};

			// the collada spec allows the animation of data in various ways.
			// depending on the transform type (matrix, translate, rotate, scale), we execute different logic

			switch ( transform ) {

				case 'matrix':

					for ( i = 0, il = inputSource.array.length; i < il; i ++ ) {

						time = inputSource.array[ i ];
						stride = i * outputSource.stride;

						if ( data[ time ] === undefined ) data[ time ] = {};

						if ( channel.arraySyntax === true ) {

							const value = outputSource.array[ stride ];
							const index = channel.indices[ 0 ] + 4 * channel.indices[ 1 ];

							data[ time ][ index ] = value;

						} else {

							for ( j = 0, jl = outputSource.stride; j < jl; j ++ ) {

								data[ time ][ j ] = outputSource.array[ stride + j ];

							}

						}

					}

					break;

				case 'translate':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

				case 'rotate':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

				case 'scale':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

			}

			const keyframes = prepareAnimationData( data, defaultMatrix );

			const animation = {
				name: object3D.uuid,
				keyframes: keyframes
			};

			return animation;

		}

		function prepareAnimationData( data, defaultMatrix ) {

			const keyframes = [];

			// transfer data into a sortable array

			for ( const time in data ) {

				keyframes.push( { time: parseFloat( time ), value: data[ time ] } );

			}

			// ensure keyframes are sorted by time

			keyframes.sort( ascending );

			// now we clean up all animation data, so we can use them for keyframe tracks

			for ( let i = 0; i < 16; i ++ ) {

				transformAnimationData( keyframes, i, defaultMatrix.elements[ i ] );

			}

			return keyframes;

			// array sort function

			function ascending( a, b ) {

				return a.time - b.time;

			}

		}

		const position = new Vector3();
		const scale = new Vector3();
		const quaternion = new Quaternion();

		function createKeyframeTracks( animation, tracks ) {

			const keyframes = animation.keyframes;
			const name = animation.name;

			const times = [];
			const positionData = [];
			const quaternionData = [];
			const scaleData = [];

			for ( let i = 0, l = keyframes.length; i < l; i ++ ) {

				const keyframe = keyframes[ i ];

				const time = keyframe.time;
				const value = keyframe.value;

				matrix.fromArray( value ).transpose();
				matrix.decompose( position, quaternion, scale );

				times.push( time );
				positionData.push( position.x, position.y, position.z );
				quaternionData.push( quaternion.x, quaternion.y, quaternion.z, quaternion.w );
				scaleData.push( scale.x, scale.y, scale.z );

			}

			if ( positionData.length > 0 ) tracks.push( new VectorKeyframeTrack( name + '.position', times, positionData ) );
			if ( quaternionData.length > 0 ) tracks.push( new QuaternionKeyframeTrack( name + '.quaternion', times, quaternionData ) );
			if ( scaleData.length > 0 ) tracks.push( new VectorKeyframeTrack( name + '.scale', times, scaleData ) );

			return tracks;

		}

		function transformAnimationData( keyframes, property, defaultValue ) {

			let keyframe;

			let empty = true;
			let i, l;

			// check, if values of a property are missing in our keyframes

			for ( i = 0, l = keyframes.length; i < l; i ++ ) {

				keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] === undefined ) {

					keyframe.value[ property ] = null; // mark as missing

				} else {

					empty = false;

				}

			}

			if ( empty === true ) {

				// no values at all, so we set a default value

				for ( i = 0, l = keyframes.length; i < l; i ++ ) {

					keyframe = keyframes[ i ];

					keyframe.value[ property ] = defaultValue;

				}

			} else {

				// filling gaps

				createMissingKeyframes( keyframes, property );

			}

		}

		function createMissingKeyframes( keyframes, property ) {

			let prev, next;

			for ( let i = 0, l = keyframes.length; i < l; i ++ ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] === null ) {

					prev = getPrev( keyframes, i, property );
					next = getNext( keyframes, i, property );

					if ( prev === null ) {

						keyframe.value[ property ] = next.value[ property ];
						continue;

					}

					if ( next === null ) {

						keyframe.value[ property ] = prev.value[ property ];
						continue;

					}

					interpolate( keyframe, prev, next, property );

				}

			}

		}

		function getPrev( keyframes, i, property ) {

			while ( i >= 0 ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] !== null ) return keyframe;

				i --;

			}

			return null;

		}

		function getNext( keyframes, i, property ) {

			while ( i < keyframes.length ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] !== null ) return keyframe;

				i ++;

			}

			return null;

		}

		function interpolate( key, prev, next, property ) {

			if ( ( next.time - prev.time ) === 0 ) {

				key.value[ property ] = prev.value[ property ];
				return;

			}

			key.value[ property ] = ( ( key.time - prev.time ) * ( next.value[ property ] - prev.value[ property ] ) / ( next.time - prev.time ) ) + prev.value[ property ];

		}

		// animation clips

		function parseAnimationClip( xml ) {

			const data = {
				name: xml.getAttribute( 'id' ) || 'default',
				start: parseFloat( xml.getAttribute( 'start' ) || 0 ),
				end: parseFloat( xml.getAttribute( 'end' ) || 0 ),
				animations: []
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'instance_animation':
						data.animations.push( parseId( child.getAttribute( 'url' ) ) );
						break;

				}

			}

			library.clips[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildAnimationClip( data ) {

			const tracks = [];

			const name = data.name;
			const duration = ( data.end - data.start ) || - 1;
			const animations = data.animations;

			for ( let i = 0, il = animations.length; i < il; i ++ ) {

				const animationTracks = getAnimation( animations[ i ] );

				for ( let j = 0, jl = animationTracks.length; j < jl; j ++ ) {

					tracks.push( animationTracks[ j ] );

				}

			}

			return new AnimationClip( name, duration, tracks );

		}

		function getAnimationClip( id ) {

			return getBuild( library.clips[ id ], buildAnimationClip );

		}

		// controller

		function parseController( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'skin':
						// there is exactly one skin per controller
						data.id = parseId( child.getAttribute( 'source' ) );
						data.skin = parseSkin( child );
						break;

					case 'morph':
						data.id = parseId( child.getAttribute( 'source' ) );
						console.warn( 'THREE.ColladaLoader: Morph target animation not supported yet.' );
						break;

				}

			}

			library.controllers[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseSkin( xml ) {

			const data = {
				sources: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'bind_shape_matrix':
						data.bindShapeMatrix = parseFloats( child.textContent );
						break;

					case 'source':
						const id = child.getAttribute( 'id' );
						data.sources[ id ] = parseSource( child );
						break;

					case 'joints':
						data.joints = parseJoints( child );
						break;

					case 'vertex_weights':
						data.vertexWeights = parseVertexWeights( child );
						break;

				}

			}

			return data;

		}

		function parseJoints( xml ) {

			const data = {
				inputs: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const semantic = child.getAttribute( 'semantic' );
						const id = parseId( child.getAttribute( 'source' ) );
						data.inputs[ semantic ] = id;
						break;

				}

			}

			return data;

		}

		function parseVertexWeights( xml ) {

			const data = {
				inputs: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const semantic = child.getAttribute( 'semantic' );
						const id = parseId( child.getAttribute( 'source' ) );
						const offset = parseInt( child.getAttribute( 'offset' ) );
						data.inputs[ semantic ] = { id: id, offset: offset };
						break;

					case 'vcount':
						data.vcount = parseInts( child.textContent );
						break;

					case 'v':
						data.v = parseInts( child.textContent );
						break;

				}

			}

			return data;

		}

		function buildController( data ) {

			const build = {
				id: data.id
			};

			const geometry = library.geometries[ build.id ];

			if ( data.skin !== undefined ) {

				build.skin = buildSkin( data.skin );

				// we enhance the 'sources' property of the corresponding geometry with our skin data

				geometry.sources.skinIndices = build.skin.indices;
				geometry.sources.skinWeights = build.skin.weights;

			}

			return build;

		}

		function buildSkin( data ) {

			const BONE_LIMIT = 4;

			const build = {
				joints: [], // this must be an array to preserve the joint order
				indices: {
					array: [],
					stride: BONE_LIMIT
				},
				weights: {
					array: [],
					stride: BONE_LIMIT
				}
			};

			const sources = data.sources;
			const vertexWeights = data.vertexWeights;

			const vcount = vertexWeights.vcount;
			const v = vertexWeights.v;
			const jointOffset = vertexWeights.inputs.JOINT.offset;
			const weightOffset = vertexWeights.inputs.WEIGHT.offset;

			const jointSource = data.sources[ data.joints.inputs.JOINT ];
			const inverseSource = data.sources[ data.joints.inputs.INV_BIND_MATRIX ];

			const weights = sources[ vertexWeights.inputs.WEIGHT.id ].array;
			let stride = 0;

			let i, j, l;

			// process skin data for each vertex

			for ( i = 0, l = vcount.length; i < l; i ++ ) {

				const jointCount = vcount[ i ]; // this is the amount of joints that affect a single vertex
				const vertexSkinData = [];

				for ( j = 0; j < jointCount; j ++ ) {

					const skinIndex = v[ stride + jointOffset ];
					const weightId = v[ stride + weightOffset ];
					const skinWeight = weights[ weightId ];

					vertexSkinData.push( { index: skinIndex, weight: skinWeight } );

					stride += 2;

				}

				// we sort the joints in descending order based on the weights.
				// this ensures, we only proceed the most important joints of the vertex

				vertexSkinData.sort( descending );

				// now we provide for each vertex a set of four index and weight values.
				// the order of the skin data matches the order of vertices

				for ( j = 0; j < BONE_LIMIT; j ++ ) {

					const d = vertexSkinData[ j ];

					if ( d !== undefined ) {

						build.indices.array.push( d.index );
						build.weights.array.push( d.weight );

					} else {

						build.indices.array.push( 0 );
						build.weights.array.push( 0 );

					}

				}

			}

			// setup bind matrix

			if ( data.bindShapeMatrix ) {

				build.bindMatrix = new Matrix4().fromArray( data.bindShapeMatrix ).transpose();

			} else {

				build.bindMatrix = new Matrix4().identity();

			}

			// process bones and inverse bind matrix data

			for ( i = 0, l = jointSource.array.length; i < l; i ++ ) {

				const name = jointSource.array[ i ];
				const boneInverse = new Matrix4().fromArray( inverseSource.array, i * inverseSource.stride ).transpose();

				build.joints.push( { name: name, boneInverse: boneInverse } );

			}

			return build;

			// array sort function

			function descending( a, b ) {

				return b.weight - a.weight;

			}

		}

		function getController( id ) {

			return getBuild( library.controllers[ id ], buildController );

		}

		// image

		function parseImage( xml ) {

			const data = {
				init_from: getElementsByTagName( xml, 'init_from' )[ 0 ].textContent
			};

			library.images[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildImage( data ) {

			if ( data.build !== undefined ) return data.build;

			return data.init_from;

		}

		function getImage( id ) {

			const data = library.images[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildImage );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find image with ID:', id );

			return null;

		}

		// effect

		function parseEffect( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'profile_COMMON':
						data.profile = parseEffectProfileCOMMON( child );
						break;

				}

			}

			library.effects[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseEffectProfileCOMMON( xml ) {

			const data = {
				surfaces: {},
				samplers: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'newparam':
						parseEffectNewparam( child, data );
						break;

					case 'technique':
						data.technique = parseEffectTechnique( child );
						break;

					case 'extra':
						data.extra = parseEffectExtra( child );
						break;

				}

			}

			return data;

		}

		function parseEffectNewparam( xml, data ) {

			const sid = xml.getAttribute( 'sid' );

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'surface':
						data.surfaces[ sid ] = parseEffectSurface( child );
						break;

					case 'sampler2D':
						data.samplers[ sid ] = parseEffectSampler( child );
						break;

				}

			}

		}

		function parseEffectSurface( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'init_from':
						data.init_from = child.textContent;
						break;

				}

			}

			return data;

		}

		function parseEffectSampler( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'source':
						data.source = child.textContent;
						break;

				}

			}

			return data;

		}

		function parseEffectTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'constant':
					case 'lambert':
					case 'blinn':
					case 'phong':
						data.type = child.nodeName;
						data.parameters = parseEffectParameters( child );
						break;

					case 'extra':
						data.extra = parseEffectExtra( child );
						break;

				}

			}

			return data;

		}

		function parseEffectParameters( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'emission':
					case 'diffuse':
					case 'specular':
					case 'bump':
					case 'ambient':
					case 'shininess':
					case 'transparency':
						data[ child.nodeName ] = parseEffectParameter( child );
						break;
					case 'transparent':
						data[ child.nodeName ] = {
							opaque: child.hasAttribute( 'opaque' ) ? child.getAttribute( 'opaque' ) : 'A_ONE',
							data: parseEffectParameter( child )
						};
						break;

				}

			}

			return data;

		}

		function parseEffectParameter( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'color':
						data[ child.nodeName ] = parseFloats( child.textContent );
						break;

					case 'float':
						data[ child.nodeName ] = parseFloat( child.textContent );
						break;

					case 'texture':
						data[ child.nodeName ] = { id: child.getAttribute( 'texture' ), extra: parseEffectParameterTexture( child ) };
						break;

				}

			}

			return data;

		}

		function parseEffectParameterTexture( xml ) {

			const data = {
				technique: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'extra':
						parseEffectParameterTextureExtra( child, data );
						break;

				}

			}

			return data;

		}

		function parseEffectParameterTextureExtra( xml, data ) {

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique':
						parseEffectParameterTextureExtraTechnique( child, data );
						break;

				}

			}

		}

		function parseEffectParameterTextureExtraTechnique( xml, data ) {

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'repeatU':
					case 'repeatV':
					case 'offsetU':
					case 'offsetV':
						data.technique[ child.nodeName ] = parseFloat( child.textContent );
						break;

					case 'wrapU':
					case 'wrapV':

						// some files have values for wrapU/wrapV which become NaN via parseInt

						if ( child.textContent.toUpperCase() === 'TRUE' ) {

							data.technique[ child.nodeName ] = 1;

						} else if ( child.textContent.toUpperCase() === 'FALSE' ) {

							data.technique[ child.nodeName ] = 0;

						} else {

							data.technique[ child.nodeName ] = parseInt( child.textContent );

						}

						break;

					case 'bump':
						data[ child.nodeName ] = parseEffectExtraTechniqueBump( child );
						break;

				}

			}

		}

		function parseEffectExtra( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique':
						data.technique = parseEffectExtraTechnique( child );
						break;

				}

			}

			return data;

		}

		function parseEffectExtraTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'double_sided':
						data[ child.nodeName ] = parseInt( child.textContent );
						break;

					case 'bump':
						data[ child.nodeName ] = parseEffectExtraTechniqueBump( child );
						break;

				}

			}

			return data;

		}

		function parseEffectExtraTechniqueBump( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'texture':
						data[ child.nodeName ] = { id: child.getAttribute( 'texture' ), texcoord: child.getAttribute( 'texcoord' ), extra: parseEffectParameterTexture( child ) };
						break;

				}

			}

			return data;

		}

		function buildEffect( data ) {

			return data;

		}

		function getEffect( id ) {

			return getBuild( library.effects[ id ], buildEffect );

		}

		// material

		function parseMaterial( xml ) {

			const data = {
				name: xml.getAttribute( 'name' )
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'instance_effect':
						data.url = parseId( child.getAttribute( 'url' ) );
						break;

				}

			}

			library.materials[ xml.getAttribute( 'id' ) ] = data;

		}

		function getTextureLoader( image ) {

			let loader;

			let extension = image.slice( ( image.lastIndexOf( '.' ) - 1 >>> 0 ) + 2 ); // http://www.jstips.co/en/javascript/get-file-extension/
			extension = extension.toLowerCase();

			switch ( extension ) {

				case 'tga':
					loader = tgaLoader;
					break;

				default:
					loader = textureLoader;

			}

			return loader;

		}

		function buildMaterial( data ) {

			const effect = getEffect( data.url );
			const technique = effect.profile.technique;

			let material;

			switch ( technique.type ) {

				case 'phong':
				case 'blinn':
					material = new MeshPhongMaterial();
					break;

				case 'lambert':
					material = new MeshLambertMaterial();
					break;

				default:
					material = new MeshBasicMaterial();
					break;

			}

			material.name = data.name || '';

			function getTexture( textureObject, colorSpace = null ) {

				const sampler = effect.profile.samplers[ textureObject.id ];
				let image = null;

				// get image

				if ( sampler !== undefined ) {

					const surface = effect.profile.surfaces[ sampler.source ];
					image = getImage( surface.init_from );

				} else {

					console.warn( 'THREE.ColladaLoader: Undefined sampler. Access image directly (see #12530).' );
					image = getImage( textureObject.id );

				}

				// create texture if image is available

				if ( image !== null ) {

					const loader = getTextureLoader( image );

					if ( loader !== undefined ) {

						const texture = loader.load( image );

						const extra = textureObject.extra;

						if ( extra !== undefined && extra.technique !== undefined && isEmpty( extra.technique ) === false ) {

							const technique = extra.technique;

							texture.wrapS = technique.wrapU ? RepeatWrapping : ClampToEdgeWrapping;
							texture.wrapT = technique.wrapV ? RepeatWrapping : ClampToEdgeWrapping;

							texture.offset.set( technique.offsetU || 0, technique.offsetV || 0 );
							texture.repeat.set( technique.repeatU || 1, technique.repeatV || 1 );

						} else {

							texture.wrapS = RepeatWrapping;
							texture.wrapT = RepeatWrapping;

						}

						if ( colorSpace !== null ) {

							texture.colorSpace = colorSpace;

						}

						return texture;

					} else {

						console.warn( 'THREE.ColladaLoader: Loader for texture %s not found.', image );

						return null;

					}

				} else {

					console.warn( 'THREE.ColladaLoader: Couldn\'t create texture with ID:', textureObject.id );

					return null;

				}

			}

			const parameters = technique.parameters;

			for ( const key in parameters ) {

				const parameter = parameters[ key ];

				switch ( key ) {

					case 'diffuse':
						if ( parameter.color ) material.color.fromArray( parameter.color );
						if ( parameter.texture ) material.map = getTexture( parameter.texture, SRGBColorSpace );
						break;
					case 'specular':
						if ( parameter.color && material.specular ) material.specular.fromArray( parameter.color );
						if ( parameter.texture ) material.specularMap = getTexture( parameter.texture );
						break;
					case 'bump':
						if ( parameter.texture ) material.normalMap = getTexture( parameter.texture );
						break;
					case 'ambient':
						if ( parameter.texture ) material.lightMap = getTexture( parameter.texture, SRGBColorSpace );
						break;
					case 'shininess':
						if ( parameter.float && material.shininess ) material.shininess = parameter.float;
						break;
					case 'emission':
						if ( parameter.color && material.emissive ) material.emissive.fromArray( parameter.color );
						if ( parameter.texture ) material.emissiveMap = getTexture( parameter.texture, SRGBColorSpace );
						break;

				}

			}

			ColorManagement.colorSpaceToWorking( material.color, SRGBColorSpace );
			if ( material.specular ) ColorManagement.colorSpaceToWorking( material.specular, SRGBColorSpace );
			if ( material.emissive ) ColorManagement.colorSpaceToWorking( material.emissive, SRGBColorSpace );

			//

			let transparent = parameters[ 'transparent' ];
			let transparency = parameters[ 'transparency' ];

			// <transparency> does not exist but <transparent>

			if ( transparency === undefined && transparent ) {

				transparency = {
					float: 1
				};

			}

			// <transparent> does not exist but <transparency>

			if ( transparent === undefined && transparency ) {

				transparent = {
					opaque: 'A_ONE',
					data: {
						color: [ 1, 1, 1, 1 ]
					} };

			}

			if ( transparent && transparency ) {

				// handle case if a texture exists but no color

				if ( transparent.data.texture ) {

					// we do not set an alpha map (see #13792)

					material.transparent = true;

				} else {

					const color = transparent.data.color;

					switch ( transparent.opaque ) {

						case 'A_ONE':
							material.opacity = color[ 3 ] * transparency.float;
							break;
						case 'RGB_ZERO':
							material.opacity = 1 - ( color[ 0 ] * transparency.float );
							break;
						case 'A_ZERO':
							material.opacity = 1 - ( color[ 3 ] * transparency.float );
							break;
						case 'RGB_ONE':
							material.opacity = color[ 0 ] * transparency.float;
							break;
						default:
							console.warn( 'THREE.ColladaLoader: Invalid opaque type "%s" of transparent tag.', transparent.opaque );

					}

					if ( material.opacity < 1 ) material.transparent = true;

				}

			}

			//


			if ( technique.extra !== undefined && technique.extra.technique !== undefined ) {

				const techniques = technique.extra.technique;

				for ( const k in techniques ) {

					const v = techniques[ k ];

					switch ( k ) {

						case 'double_sided':
							material.side = ( v === 1 ? DoubleSide : FrontSide );
							break;

						case 'bump':
							material.normalMap = getTexture( v.texture );
							material.normalScale = new Vector2( 1, 1 );
							break;

					}

				}

			}

			return material;

		}

		function getMaterial( id ) {

			return getBuild( library.materials[ id ], buildMaterial );

		}

		// camera

		function parseCamera( xml ) {

			const data = {
				name: xml.getAttribute( 'name' )
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'optics':
						data.optics = parseCameraOptics( child );
						break;

				}

			}

			library.cameras[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseCameraOptics( xml ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'technique_common':
						return parseCameraTechnique( child );

				}

			}

			return {};

		}

		function parseCameraTechnique( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'perspective':
					case 'orthographic':

						data.technique = child.nodeName;
						data.parameters = parseCameraParameters( child );

						break;

				}

			}

			return data;

		}

		function parseCameraParameters( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'xfov':
					case 'yfov':
					case 'xmag':
					case 'ymag':
					case 'znear':
					case 'zfar':
					case 'aspect_ratio':
						data[ child.nodeName ] = parseFloat( child.textContent );
						break;

				}

			}

			return data;

		}

		function buildCamera( data ) {

			let camera;

			switch ( data.optics.technique ) {

				case 'perspective':
					camera = new PerspectiveCamera(
						data.optics.parameters.yfov,
						data.optics.parameters.aspect_ratio,
						data.optics.parameters.znear,
						data.optics.parameters.zfar
					);
					break;

				case 'orthographic':
					let ymag = data.optics.parameters.ymag;
					let xmag = data.optics.parameters.xmag;
					const aspectRatio = data.optics.parameters.aspect_ratio;

					xmag = ( xmag === undefined ) ? ( ymag * aspectRatio ) : xmag;
					ymag = ( ymag === undefined ) ? ( xmag / aspectRatio ) : ymag;

					xmag *= 0.5;
					ymag *= 0.5;

					camera = new OrthographicCamera(
						- xmag, xmag, ymag, - ymag, // left, right, top, bottom
						data.optics.parameters.znear,
						data.optics.parameters.zfar
					);
					break;

				default:
					camera = new PerspectiveCamera();
					break;

			}

			camera.name = data.name || '';

			return camera;

		}

		function getCamera( id ) {

			const data = library.cameras[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildCamera );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find camera with ID:', id );

			return null;

		}

		// light

		function parseLight( xml ) {

			let data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						data = parseLightTechnique( child );
						break;

				}

			}

			library.lights[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseLightTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'directional':
					case 'point':
					case 'spot':
					case 'ambient':

						data.technique = child.nodeName;
						data.parameters = parseLightParameters( child );

				}

			}

			return data;

		}

		function parseLightParameters( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'color':
						const array = parseFloats( child.textContent );
						data.color = new Color().fromArray( array );
						ColorManagement.colorSpaceToWorking( data.color, SRGBColorSpace );
						break;

					case 'falloff_angle':
						data.falloffAngle = parseFloat( child.textContent );
						break;

					case 'quadratic_attenuation':
						const f = parseFloat( child.textContent );
						data.distance = f ? Math.sqrt( 1 / f ) : 0;
						break;

				}

			}

			return data;

		}

		function buildLight( data ) {

			let light;

			switch ( data.technique ) {

				case 'directional':
					light = new DirectionalLight();
					break;

				case 'point':
					light = new PointLight();
					break;

				case 'spot':
					light = new SpotLight();
					break;

				case 'ambient':
					light = new AmbientLight();
					break;

			}

			if ( data.parameters.color ) light.color.copy( data.parameters.color );
			if ( data.parameters.distance ) light.distance = data.parameters.distance;

			return light;

		}

		function getLight( id ) {

			const data = library.lights[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildLight );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find light with ID:', id );

			return null;

		}

		// geometry

		function parseGeometry( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ),
				sources: {},
				vertices: {},
				primitives: []
			};

			const mesh = getElementsByTagName( xml, 'mesh' )[ 0 ];

			// the following tags inside geometry are not supported yet (see https://github.com/mrdoob/three.js/pull/12606): convex_mesh, spline, brep
			if ( mesh === undefined ) return;

			for ( let i = 0; i < mesh.childNodes.length; i ++ ) {

				const child = mesh.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				const id = child.getAttribute( 'id' );

				switch ( child.nodeName ) {

					case 'source':
						data.sources[ id ] = parseSource( child );
						break;

					case 'vertices':
						// data.sources[ id ] = data.sources[ parseId( getElementsByTagName( child, 'input' )[ 0 ].getAttribute( 'source' ) ) ];
						data.vertices = parseGeometryVertices( child );
						break;

					case 'polygons':
						console.warn( 'THREE.ColladaLoader: Unsupported primitive type: ', child.nodeName );
						break;

					case 'lines':
					case 'linestrips':
					case 'polylist':
					case 'triangles':
						data.primitives.push( parseGeometryPrimitive( child ) );
						break;

					default:
						console.log( child );

				}

			}

			library.geometries[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseSource( xml ) {

			const data = {
				array: [],
				stride: 3
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'float_array':
						data.array = parseFloats( child.textContent );
						break;

					case 'Name_array':
						data.array = parseStrings( child.textContent );
						break;

					case 'technique_common':
						const accessor = getElementsByTagName( child, 'accessor' )[ 0 ];

						if ( accessor !== undefined ) {

							data.stride = parseInt( accessor.getAttribute( 'stride' ) );

						}

						break;

				}

			}

			return data;

		}

		function parseGeometryVertices( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				data[ child.getAttribute( 'semantic' ) ] = parseId( child.getAttribute( 'source' ) );

			}

			return data;

		}

		function parseGeometryPrimitive( xml ) {

			const primitive = {
				type: xml.nodeName,
				material: xml.getAttribute( 'material' ),
				count: parseInt( xml.getAttribute( 'count' ) ),
				inputs: {},
				stride: 0,
				hasUV: false
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const id = parseId( child.getAttribute( 'source' ) );
						const semantic = child.getAttribute( 'semantic' );
						const offset = parseInt( child.getAttribute( 'offset' ) );
						const set = parseInt( child.getAttribute( 'set' ) );
						const inputname = ( set > 0 ? semantic + set : semantic );
						primitive.inputs[ inputname ] = { id: id, offset: offset };
						primitive.stride = Math.max( primitive.stride, offset + 1 );
						if ( semantic === 'TEXCOORD' ) primitive.hasUV = true;
						break;

					case 'vcount':
						primitive.vcount = parseInts( child.textContent );
						break;

					case 'p':
						primitive.p = parseInts( child.textContent );
						break;

				}

			}

			return primitive;

		}

		function groupPrimitives( primitives ) {

			const build = {};

			for ( let i = 0; i < primitives.length; i ++ ) {

				const primitive = primitives[ i ];

				if ( build[ primitive.type ] === undefined ) build[ primitive.type ] = [];

				build[ primitive.type ].push( primitive );

			}

			return build;

		}

		function checkUVCoordinates( primitives ) {

			let count = 0;

			for ( let i = 0, l = primitives.length; i < l; i ++ ) {

				const primitive = primitives[ i ];

				if ( primitive.hasUV === true ) {

					count ++;

				}

			}

			if ( count > 0 && count < primitives.length ) {

				primitives.uvsNeedsFix = true;

			}

		}

		function buildGeometry( data ) {

			const build = {};

			const sources = data.sources;
			const vertices = data.vertices;
			const primitives = data.primitives;

			if ( primitives.length === 0 ) return {};

			// our goal is to create one buffer geometry for a single type of primitives
			// first, we group all primitives by their type

			const groupedPrimitives = groupPrimitives( primitives );

			for ( const type in groupedPrimitives ) {

				const primitiveType = groupedPrimitives[ type ];

				// second, ensure consistent uv coordinates for each type of primitives (polylist,triangles or lines)

				checkUVCoordinates( primitiveType );

				// third, create a buffer geometry for each type of primitives

				build[ type ] = buildGeometryType( primitiveType, sources, vertices );

			}

			return build;

		}

		function buildGeometryType( primitives, sources, vertices ) {

			const build = {};

			const position = { array: [], stride: 0 };
			const normal = { array: [], stride: 0 };
			const uv = { array: [], stride: 0 };
			const uv1 = { array: [], stride: 0 };
			const color = { array: [], stride: 0 };

			const skinIndex = { array: [], stride: 4 };
			const skinWeight = { array: [], stride: 4 };

			const geometry = new BufferGeometry();

			const materialKeys = [];

			let start = 0;

			for ( let p = 0; p < primitives.length; p ++ ) {

				const primitive = primitives[ p ];
				const inputs = primitive.inputs;

				// groups

				let count = 0;

				switch ( primitive.type ) {

					case 'lines':
					case 'linestrips':
						count = primitive.count * 2;
						break;

					case 'triangles':
						count = primitive.count * 3;
						break;

					case 'polylist':

						for ( let g = 0; g < primitive.count; g ++ ) {

							const vc = primitive.vcount[ g ];

							switch ( vc ) {

								case 3:
									count += 3; // single triangle
									break;

								case 4:
									count += 6; // quad, subdivided into two triangles
									break;

								default:
									count += ( vc - 2 ) * 3; // polylist with more than four vertices
									break;

							}

						}

						break;

					default:
						console.warn( 'THREE.ColladaLoader: Unknown primitive type:', primitive.type );

				}

				geometry.addGroup( start, count, p );
				start += count;

				// material

				if ( primitive.material ) {

					materialKeys.push( primitive.material );

				}

				// geometry data

				for ( const name in inputs ) {

					const input = inputs[ name ];

					switch ( name )	{

						case 'VERTEX':
							for ( const key in vertices ) {

								const id = vertices[ key ];

								switch ( key ) {

									case 'POSITION':
										const prevLength = position.array.length;
										buildGeometryData( primitive, sources[ id ], input.offset, position.array );
										position.stride = sources[ id ].stride;

										if ( sources.skinWeights && sources.skinIndices ) {

											buildGeometryData( primitive, sources.skinIndices, input.offset, skinIndex.array );
											buildGeometryData( primitive, sources.skinWeights, input.offset, skinWeight.array );

										}

										// see #3803

										if ( primitive.hasUV === false && primitives.uvsNeedsFix === true ) {

											const count = ( position.array.length - prevLength ) / position.stride;

											for ( let i = 0; i < count; i ++ ) {

												// fill missing uv coordinates

												uv.array.push( 0, 0 );

											}

										}

										break;

									case 'NORMAL':
										buildGeometryData( primitive, sources[ id ], input.offset, normal.array );
										normal.stride = sources[ id ].stride;
										break;

									case 'COLOR':
										buildGeometryData( primitive, sources[ id ], input.offset, color.array );
										color.stride = sources[ id ].stride;
										break;

									case 'TEXCOORD':
										buildGeometryData( primitive, sources[ id ], input.offset, uv.array );
										uv.stride = sources[ id ].stride;
										break;

									case 'TEXCOORD1':
										buildGeometryData( primitive, sources[ id ], input.offset, uv1.array );
										uv.stride = sources[ id ].stride;
										break;

									default:
										console.warn( 'THREE.ColladaLoader: Semantic "%s" not handled in geometry build process.', key );

								}

							}

							break;

						case 'NORMAL':
							buildGeometryData( primitive, sources[ input.id ], input.offset, normal.array );
							normal.stride = sources[ input.id ].stride;
							break;

						case 'COLOR':
							buildGeometryData( primitive, sources[ input.id ], input.offset, color.array, true );
							color.stride = sources[ input.id ].stride;
							break;

						case 'TEXCOORD':
							buildGeometryData( primitive, sources[ input.id ], input.offset, uv.array );
							uv.stride = sources[ input.id ].stride;
							break;

						case 'TEXCOORD1':
							buildGeometryData( primitive, sources[ input.id ], input.offset, uv1.array );
							uv1.stride = sources[ input.id ].stride;
							break;

					}

				}

			}

			// build geometry

			if ( position.array.length > 0 ) geometry.setAttribute( 'position', new Float32BufferAttribute( position.array, position.stride ) );
			if ( normal.array.length > 0 ) geometry.setAttribute( 'normal', new Float32BufferAttribute( normal.array, normal.stride ) );
			if ( color.array.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( color.array, color.stride ) );
			if ( uv.array.length > 0 ) geometry.setAttribute( 'uv', new Float32BufferAttribute( uv.array, uv.stride ) );
			if ( uv1.array.length > 0 ) geometry.setAttribute( 'uv1', new Float32BufferAttribute( uv1.array, uv1.stride ) );

			if ( skinIndex.array.length > 0 ) geometry.setAttribute( 'skinIndex', new Float32BufferAttribute( skinIndex.array, skinIndex.stride ) );
			if ( skinWeight.array.length > 0 ) geometry.setAttribute( 'skinWeight', new Float32BufferAttribute( skinWeight.array, skinWeight.stride ) );

			build.data = geometry;
			build.type = primitives[ 0 ].type;
			build.materialKeys = materialKeys;

			return build;

		}

		function buildGeometryData( primitive, source, offset, array, isColor = false ) {

			const indices = primitive.p;
			const stride = primitive.stride;
			const vcount = primitive.vcount;

			function pushVector( i ) {

				let index = indices[ i + offset ] * sourceStride;
				const length = index + sourceStride;

				for ( ; index < length; index ++ ) {

					array.push( sourceArray[ index ] );

				}

				if ( isColor ) {

					// convert the vertex colors from srgb to linear if present
					const startIndex = array.length - sourceStride - 1;
					tempColor.setRGB(
						array[ startIndex + 0 ],
						array[ startIndex + 1 ],
						array[ startIndex + 2 ],
						SRGBColorSpace
					);

					array[ startIndex + 0 ] = tempColor.r;
					array[ startIndex + 1 ] = tempColor.g;
					array[ startIndex + 2 ] = tempColor.b;

				}

			}

			const sourceArray = source.array;
			const sourceStride = source.stride;

			if ( primitive.vcount !== undefined ) {

				let index = 0;

				for ( let i = 0, l = vcount.length; i < l; i ++ ) {

					const count = vcount[ i ];

					if ( count === 4 ) {

						const a = index + stride * 0;
						const b = index + stride * 1;
						const c = index + stride * 2;
						const d = index + stride * 3;

						pushVector( a ); pushVector( b ); pushVector( d );
						pushVector( b ); pushVector( c ); pushVector( d );

					} else if ( count === 3 ) {

						const a = index + stride * 0;
						const b = index + stride * 1;
						const c = index + stride * 2;

						pushVector( a ); pushVector( b ); pushVector( c );

					} else if ( count > 4 ) {

						for ( let k = 1, kl = ( count - 2 ); k <= kl; k ++ ) {

							const a = index + stride * 0;
							const b = index + stride * k;
							const c = index + stride * ( k + 1 );

							pushVector( a ); pushVector( b ); pushVector( c );

						}

					}

					index += stride * count;

				}

			} else {

				for ( let i = 0, l = indices.length; i < l; i += stride ) {

					pushVector( i );

				}

			}

		}

		function getGeometry( id ) {

			return getBuild( library.geometries[ id ], buildGeometry );

		}

		// kinematics

		function parseKinematicsModel( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				joints: {},
				links: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						parseKinematicsTechniqueCommon( child, data );
						break;

				}

			}

			library.kinematicsModels[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildKinematicsModel( data ) {

			if ( data.build !== undefined ) return data.build;

			return data;

		}

		function getKinematicsModel( id ) {

			return getBuild( library.kinematicsModels[ id ], buildKinematicsModel );

		}

		function parseKinematicsTechniqueCommon( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'joint':
						data.joints[ child.getAttribute( 'sid' ) ] = parseKinematicsJoint( child );
						break;

					case 'link':
						data.links.push( parseKinematicsLink( child ) );
						break;

				}

			}

		}

		function parseKinematicsJoint( xml ) {

			let data;

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'prismatic':
					case 'revolute':
						data = parseKinematicsJointParameter( child );
						break;

				}

			}

			return data;

		}

		function parseKinematicsJointParameter( xml ) {

			const data = {
				sid: xml.getAttribute( 'sid' ),
				name: xml.getAttribute( 'name' ) || '',
				axis: new Vector3(),
				limits: {
					min: 0,
					max: 0
				},
				type: xml.nodeName,
				static: false,
				zeroPosition: 0,
				middlePosition: 0
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'axis':
						const array = parseFloats( child.textContent );
						data.axis.fromArray( array );
						break;
					case 'limits':
						const max = child.getElementsByTagName( 'max' )[ 0 ];
						const min = child.getElementsByTagName( 'min' )[ 0 ];

						data.limits.max = parseFloat( max.textContent );
						data.limits.min = parseFloat( min.textContent );
						break;

				}

			}

			// if min is equal to or greater than max, consider the joint static

			if ( data.limits.min >= data.limits.max ) {

				data.static = true;

			}

			// calculate middle position

			data.middlePosition = ( data.limits.min + data.limits.max ) / 2.0;

			return data;

		}

		function parseKinematicsLink( xml ) {

			const data = {
				sid: xml.getAttribute( 'sid' ),
				name: xml.getAttribute( 'name' ) || '',
				attachments: [],
				transforms: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'attachment_full':
						data.attachments.push( parseKinematicsAttachment( child ) );
						break;

					case 'matrix':
					case 'translate':
					case 'rotate':
						data.transforms.push( parseKinematicsTransform( child ) );
						break;

				}

			}

			return data;

		}

		function parseKinematicsAttachment( xml ) {

			const data = {
				joint: xml.getAttribute( 'joint' ).split( '/' ).pop(),
				transforms: [],
				links: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'link':
						data.links.push( parseKinematicsLink( child ) );
						break;

					case 'matrix':
					case 'translate':
					case 'rotate':
						data.transforms.push( parseKinematicsTransform( child ) );
						break;

				}

			}

			return data;

		}

		function parseKinematicsTransform( xml ) {

			const data = {
				type: xml.nodeName
			};

			const array = parseFloats( xml.textContent );

			switch ( data.type ) {

				case 'matrix':
					data.obj = new Matrix4();
					data.obj.fromArray( array ).transpose();
					break;

				case 'translate':
					data.obj = new Vector3();
					data.obj.fromArray( array );
					break;

				case 'rotate':
					data.obj = new Vector3();
					data.obj.fromArray( array );
					data.angle = MathUtils.degToRad( array[ 3 ] );
					break;

			}

			return data;

		}

		// physics

		function parsePhysicsModel( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				rigidBodies: {}
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'rigid_body':
						data.rigidBodies[ child.getAttribute( 'name' ) ] = {};
						parsePhysicsRigidBody( child, data.rigidBodies[ child.getAttribute( 'name' ) ] );
						break;

				}

			}

			library.physicsModels[ xml.getAttribute( 'id' ) ] = data;

		}

		function parsePhysicsRigidBody( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						parsePhysicsTechniqueCommon( child, data );
						break;

				}

			}

		}

		function parsePhysicsTechniqueCommon( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'inertia':
						data.inertia = parseFloats( child.textContent );
						break;

					case 'mass':
						data.mass = parseFloats( child.textContent )[ 0 ];
						break;

				}

			}

		}

		// scene

		function parseKinematicsScene( xml ) {

			const data = {
				bindJointAxis: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'bind_joint_axis':
						data.bindJointAxis.push( parseKinematicsBindJointAxis( child ) );
						break;

				}

			}

			library.kinematicsScenes[ parseId( xml.getAttribute( 'url' ) ) ] = data;

		}

		function parseKinematicsBindJointAxis( xml ) {

			const data = {
				target: xml.getAttribute( 'target' ).split( '/' ).pop()
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'axis':
						const param = child.getElementsByTagName( 'param' )[ 0 ];
						data.axis = param.textContent;
						const tmpJointIndex = data.axis.split( 'inst_' ).pop().split( 'axis' )[ 0 ];
						data.jointIndex = tmpJointIndex.substring( 0, tmpJointIndex.length - 1 );
						break;

				}

			}

			return data;

		}

		function buildKinematicsScene( data ) {

			if ( data.build !== undefined ) return data.build;

			return data;

		}

		function getKinematicsScene( id ) {

			return getBuild( library.kinematicsScenes[ id ], buildKinematicsScene );

		}

		function setupKinematics() {

			const kinematicsModelId = Object.keys( library.kinematicsModels )[ 0 ];
			const kinematicsSceneId = Object.keys( library.kinematicsScenes )[ 0 ];
			const visualSceneId = Object.keys( library.visualScenes )[ 0 ];

			if ( kinematicsModelId === undefined || kinematicsSceneId === undefined ) return;

			const kinematicsModel = getKinematicsModel( kinematicsModelId );
			const kinematicsScene = getKinematicsScene( kinematicsSceneId );
			const visualScene = getVisualScene( visualSceneId );

			const bindJointAxis = kinematicsScene.bindJointAxis;
			const jointMap = {};

			for ( let i = 0, l = bindJointAxis.length; i < l; i ++ ) {

				const axis = bindJointAxis[ i ];

				// the result of the following query is an element of type 'translate', 'rotate','scale' or 'matrix'

				const targetElement = collada.querySelector( '[sid="' + axis.target + '"]' );

				if ( targetElement ) {

					// get the parent of the transform element

					const parentVisualElement = targetElement.parentElement;

					// connect the joint of the kinematics model with the element in the visual scene

					connect( axis.jointIndex, parentVisualElement );

				}

			}

			function connect( jointIndex, visualElement ) {

				const visualElementName = visualElement.getAttribute( 'name' );
				const joint = kinematicsModel.joints[ jointIndex ];

				visualScene.traverse( function ( object ) {

					if ( object.name === visualElementName ) {

						jointMap[ jointIndex ] = {
							object: object,
							transforms: buildTransformList( visualElement ),
							joint: joint,
							position: joint.zeroPosition
						};

					}

				} );

			}

			const m0 = new Matrix4();

			kinematics = {

				joints: kinematicsModel && kinematicsModel.joints,

				getJointValue: function ( jointIndex ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						return jointData.position;

					} else {

						console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' doesn\'t exist.' );

					}

				},

				setJointValue: function ( jointIndex, value ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						const joint = jointData.joint;

						if ( value > joint.limits.max || value < joint.limits.min ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' value ' + value + ' outside of limits (min: ' + joint.limits.min + ', max: ' + joint.limits.max + ').' );

						} else if ( joint.static ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' is static.' );

						} else {

							const object = jointData.object;
							const axis = joint.axis;
							const transforms = jointData.transforms;

							matrix.identity();

							// each update, we have to apply all transforms in the correct order

							for ( let i = 0; i < transforms.length; i ++ ) {

								const transform = transforms[ i ];

								// if there is a connection of the transform node with a joint, apply the joint value

								if ( transform.sid && transform.sid.indexOf( jointIndex ) !== - 1 ) {

									switch ( joint.type ) {

										case 'revolute':
											matrix.multiply( m0.makeRotationAxis( axis, MathUtils.degToRad( value ) ) );
											break;

										case 'prismatic':
											matrix.multiply( m0.makeTranslation( axis.x * value, axis.y * value, axis.z * value ) );
											break;

										default:
											console.warn( 'THREE.ColladaLoader: Unknown joint type: ' + joint.type );
											break;

									}

								} else {

									switch ( transform.type ) {

										case 'matrix':
											matrix.multiply( transform.obj );
											break;

										case 'translate':
											matrix.multiply( m0.makeTranslation( transform.obj.x, transform.obj.y, transform.obj.z ) );
											break;

										case 'scale':
											matrix.scale( transform.obj );
											break;

										case 'rotate':
											matrix.multiply( m0.makeRotationAxis( transform.obj, transform.angle ) );
											break;

									}

								}

							}

							object.matrix.copy( matrix );
							object.matrix.decompose( object.position, object.quaternion, object.scale );

							jointMap[ jointIndex ].position = value;

						}

					} else {

						console.log( 'THREE.ColladaLoader: ' + jointIndex + ' does not exist.' );

					}

				}

			};

		}

		function buildTransformList( node ) {

			const transforms = [];

			const xml = collada.querySelector( '[id="' + node.id + '"]' );

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let array, vector;

				switch ( child.nodeName ) {

					case 'matrix':
						array = parseFloats( child.textContent );
						const matrix = new Matrix4().fromArray( array ).transpose();
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: matrix
						} );
						break;

					case 'translate':
					case 'scale':
						array = parseFloats( child.textContent );
						vector = new Vector3().fromArray( array );
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: vector
						} );
						break;

					case 'rotate':
						array = parseFloats( child.textContent );
						vector = new Vector3().fromArray( array );
						const angle = MathUtils.degToRad( array[ 3 ] );
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: vector,
							angle: angle
						} );
						break;

				}

			}

			return transforms;

		}

		// nodes

		function prepareNodes( xml ) {

			const elements = xml.getElementsByTagName( 'node' );

			// ensure all node elements have id attributes

			for ( let i = 0; i < elements.length; i ++ ) {

				const element = elements[ i ];

				if ( element.hasAttribute( 'id' ) === false ) {

					element.setAttribute( 'id', generateId() );

				}

			}

		}

		const matrix = new Matrix4();
		const vector = new Vector3();

		function parseNode( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				type: xml.getAttribute( 'type' ),
				id: xml.getAttribute( 'id' ),
				sid: xml.getAttribute( 'sid' ),
				matrix: new Matrix4(),
				nodes: [],
				instanceCameras: [],
				instanceControllers: [],
				instanceLights: [],
				instanceGeometries: [],
				instanceNodes: [],
				transforms: {}
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let array;

				switch ( child.nodeName ) {

					case 'node':
						data.nodes.push( child.getAttribute( 'id' ) );
						parseNode( child );
						break;

					case 'instance_camera':
						data.instanceCameras.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'instance_controller':
						data.instanceControllers.push( parseNodeInstance( child ) );
						break;

					case 'instance_light':
						data.instanceLights.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'instance_geometry':
						data.instanceGeometries.push( parseNodeInstance( child ) );
						break;

					case 'instance_node':
						data.instanceNodes.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'matrix':
						array = parseFloats( child.textContent );
						data.matrix.multiply( matrix.fromArray( array ).transpose() );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'translate':
						array = parseFloats( child.textContent );
						vector.fromArray( array );
						data.matrix.multiply( matrix.makeTranslation( vector.x, vector.y, vector.z ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'rotate':
						array = parseFloats( child.textContent );
						const angle = MathUtils.degToRad( array[ 3 ] );
						data.matrix.multiply( matrix.makeRotationAxis( vector.fromArray( array ), angle ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'scale':
						array = parseFloats( child.textContent );
						data.matrix.scale( vector.fromArray( array ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'extra':
						break;

					default:
						console.log( child );

				}

			}

			if ( hasNode( data.id ) ) {

				console.warn( 'THREE.ColladaLoader: There is already a node with ID %s. Exclude current node from further processing.', data.id );

			} else {

				library.nodes[ data.id ] = data;

			}

			return data;

		}

		function parseNodeInstance( xml ) {

			const data = {
				id: parseId( xml.getAttribute( 'url' ) ),
				materials: {},
				skeletons: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'bind_material':
						const instances = child.getElementsByTagName( 'instance_material' );

						for ( let j = 0; j < instances.length; j ++ ) {

							const instance = instances[ j ];
							const symbol = instance.getAttribute( 'symbol' );
							const target = instance.getAttribute( 'target' );

							data.materials[ symbol ] = parseId( target );

						}

						break;

					case 'skeleton':
						data.skeletons.push( parseId( child.textContent ) );
						break;

					default:
						break;

				}

			}

			return data;

		}

		function buildSkeleton( skeletons, joints ) {

			const boneData = [];
			const sortedBoneData = [];

			let i, j, data;

			// a skeleton can have multiple root bones. collada expresses this
			// situation with multiple "skeleton" tags per controller instance

			for ( i = 0; i < skeletons.length; i ++ ) {

				const skeleton = skeletons[ i ];

				let root;

				if ( hasNode( skeleton ) ) {

					root = getNode( skeleton );
					buildBoneHierarchy( root, joints, boneData );

				} else if ( hasVisualScene( skeleton ) ) {

					// handle case where the skeleton refers to the visual scene (#13335)

					const visualScene = library.visualScenes[ skeleton ];
					const children = visualScene.children;

					for ( let j = 0; j < children.length; j ++ ) {

						const child = children[ j ];

						if ( child.type === 'JOINT' ) {

							const root = getNode( child.id );
							buildBoneHierarchy( root, joints, boneData );

						}

					}

				} else {

					console.error( 'THREE.ColladaLoader: Unable to find root bone of skeleton with ID:', skeleton );

				}

			}

			// sort bone data (the order is defined in the corresponding controller)

			for ( i = 0; i < joints.length; i ++ ) {

				for ( j = 0; j < boneData.length; j ++ ) {

					data = boneData[ j ];

					if ( data.bone.name === joints[ i ].name ) {

						sortedBoneData[ i ] = data;
						data.processed = true;
						break;

					}

				}

			}

			// add unprocessed bone data at the end of the list

			for ( i = 0; i < boneData.length; i ++ ) {

				data = boneData[ i ];

				if ( data.processed === false ) {

					sortedBoneData.push( data );
					data.processed = true;

				}

			}

			// setup arrays for skeleton creation

			const bones = [];
			const boneInverses = [];

			for ( i = 0; i < sortedBoneData.length; i ++ ) {

				data = sortedBoneData[ i ];

				bones.push( data.bone );
				boneInverses.push( data.boneInverse );

			}

			return new Skeleton( bones, boneInverses );

		}

		function buildBoneHierarchy( root, joints, boneData ) {

			// setup bone data from visual scene

			root.traverse( function ( object ) {

				if ( object.isBone === true ) {

					let boneInverse;

					// retrieve the boneInverse from the controller data

					for ( let i = 0; i < joints.length; i ++ ) {

						const joint = joints[ i ];

						if ( joint.name === object.name ) {

							boneInverse = joint.boneInverse;
							break;

						}

					}

					if ( boneInverse === undefined ) {

						// Unfortunately, there can be joints in the visual scene that are not part of the
						// corresponding controller. In this case, we have to create a dummy boneInverse matrix
						// for the respective bone. This bone won't affect any vertices, because there are no skin indices
						// and weights defined for it. But we still have to add the bone to the sorted bone list in order to
						// ensure a correct animation of the model.

						boneInverse = new Matrix4();

					}

					boneData.push( { bone: object, boneInverse: boneInverse, processed: false } );

				}

			} );

		}

		function buildNode( data ) {

			const objects = [];

			const matrix = data.matrix;
			const nodes = data.nodes;
			const type = data.type;
			const instanceCameras = data.instanceCameras;
			const instanceControllers = data.instanceControllers;
			const instanceLights = data.instanceLights;
			const instanceGeometries = data.instanceGeometries;
			const instanceNodes = data.instanceNodes;

			// nodes

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				objects.push( getNode( nodes[ i ] ) );

			}

			// instance cameras

			for ( let i = 0, l = instanceCameras.length; i < l; i ++ ) {

				const instanceCamera = getCamera( instanceCameras[ i ] );

				if ( instanceCamera !== null ) {

					objects.push( instanceCamera.clone() );

				}

			}

			// instance controllers

			for ( let i = 0, l = instanceControllers.length; i < l; i ++ ) {

				const instance = instanceControllers[ i ];
				const controller = getController( instance.id );
				const geometries = getGeometry( controller.id );
				const newObjects = buildObjects( geometries, instance.materials );

				const skeletons = instance.skeletons;
				const joints = controller.skin.joints;

				const skeleton = buildSkeleton( skeletons, joints );

				for ( let j = 0, jl = newObjects.length; j < jl; j ++ ) {

					const object = newObjects[ j ];

					if ( object.isSkinnedMesh ) {

						object.bind( skeleton, controller.skin.bindMatrix );
						object.normalizeSkinWeights();

					}

					objects.push( object );

				}

			}

			// instance lights

			for ( let i = 0, l = instanceLights.length; i < l; i ++ ) {

				const instanceLight = getLight( instanceLights[ i ] );

				if ( instanceLight !== null ) {

					objects.push( instanceLight.clone() );

				}

			}

			// instance geometries

			for ( let i = 0, l = instanceGeometries.length; i < l; i ++ ) {

				const instance = instanceGeometries[ i ];

				// a single geometry instance in collada can lead to multiple object3Ds.
				// this is the case when primitives are combined like triangles and lines

				const geometries = getGeometry( instance.id );
				const newObjects = buildObjects( geometries, instance.materials );

				for ( let j = 0, jl = newObjects.length; j < jl; j ++ ) {

					objects.push( newObjects[ j ] );

				}

			}

			// instance nodes

			for ( let i = 0, l = instanceNodes.length; i < l; i ++ ) {

				objects.push( getNode( instanceNodes[ i ] ).clone() );

			}

			let object;

			if ( nodes.length === 0 && objects.length === 1 ) {

				object = objects[ 0 ];

			} else {

				object = ( type === 'JOINT' ) ? new Bone() : new Group();

				for ( let i = 0; i < objects.length; i ++ ) {

					object.add( objects[ i ] );

				}

			}

			object.name = ( type === 'JOINT' ) ? data.sid : data.name;
			object.matrix.copy( matrix );
			object.matrix.decompose( object.position, object.quaternion, object.scale );

			return object;

		}

		const fallbackMaterial = new MeshBasicMaterial( {
			name: Loader.DEFAULT_MATERIAL_NAME,
			color: 0xff00ff
		} );

		function resolveMaterialBinding( keys, instanceMaterials ) {

			const materials = [];

			for ( let i = 0, l = keys.length; i < l; i ++ ) {

				const id = instanceMaterials[ keys[ i ] ];

				if ( id === undefined ) {

					console.warn( 'THREE.ColladaLoader: Material with key %s not found. Apply fallback material.', keys[ i ] );
					materials.push( fallbackMaterial );

				} else {

					materials.push( getMaterial( id ) );

				}

			}

			return materials;

		}

		function buildObjects( geometries, instanceMaterials ) {

			const objects = [];

			for ( const type in geometries ) {

				const geometry = geometries[ type ];

				const materials = resolveMaterialBinding( geometry.materialKeys, instanceMaterials );

				// handle case if no materials are defined

				if ( materials.length === 0 ) {

					if ( type === 'lines' || type === 'linestrips' ) {

						materials.push( new LineBasicMaterial() );

					} else {

						materials.push( new MeshPhongMaterial() );

					}

				}

				// Collada allows to use phong and lambert materials with lines. Replacing these cases with LineBasicMaterial.

				if ( type === 'lines' || type === 'linestrips' ) {

					for ( let i = 0, l = materials.length; i < l; i ++ ) {

						const material = materials[ i ];

						if ( material.isMeshPhongMaterial === true || material.isMeshLambertMaterial === true ) {

							const lineMaterial = new LineBasicMaterial();

							// copy compatible properties

							lineMaterial.color.copy( material.color );
							lineMaterial.opacity = material.opacity;
							lineMaterial.transparent = material.transparent;

							// replace material

							materials[ i ] = lineMaterial;

						}

					}

				}

				// regard skinning

				const skinning = ( geometry.data.attributes.skinIndex !== undefined );

				// choose between a single or multi materials (material array)

				const material = ( materials.length === 1 ) ? materials[ 0 ] : materials;

				// now create a specific 3D object

				let object;

				switch ( type ) {

					case 'lines':
						object = new LineSegments( geometry.data, material );
						break;

					case 'linestrips':
						object = new Line( geometry.data, material );
						break;

					case 'triangles':
					case 'polylist':
						if ( skinning ) {

							object = new SkinnedMesh( geometry.data, material );

						} else {

							object = new Mesh( geometry.data, material );

						}

						break;

				}

				objects.push( object );

			}

			return objects;

		}

		function hasNode( id ) {

			return library.nodes[ id ] !== undefined;

		}

		function getNode( id ) {

			return getBuild( library.nodes[ id ], buildNode );

		}

		// visual scenes

		function parseVisualScene( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ),
				children: []
			};

			prepareNodes( xml );

			const elements = getElementsByTagName( xml, 'node' );

			for ( let i = 0; i < elements.length; i ++ ) {

				data.children.push( parseNode( elements[ i ] ) );

			}

			library.visualScenes[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildVisualScene( data ) {

			const group = new Group();
			group.name = data.name;

			const children = data.children;

			for ( let i = 0; i < children.length; i ++ ) {

				const child = children[ i ];

				group.add( getNode( child.id ) );

			}

			return group;

		}

		function hasVisualScene( id ) {

			return library.visualScenes[ id ] !== undefined;

		}

		function getVisualScene( id ) {

			return getBuild( library.visualScenes[ id ], buildVisualScene );

		}

		// scenes

		function parseScene( xml ) {

			const instance = getElementsByTagName( xml, 'instance_visual_scene' )[ 0 ];
			return getVisualScene( parseId( instance.getAttribute( 'url' ) ) );

		}

		function setupAnimations() {

			const clips = library.clips;

			if ( isEmpty( clips ) === true ) {

				if ( isEmpty( library.animations ) === false ) {

					// if there are animations but no clips, we create a default clip for playback

					const tracks = [];

					for ( const id in library.animations ) {

						const animationTracks = getAnimation( id );

						for ( let i = 0, l = animationTracks.length; i < l; i ++ ) {

							tracks.push( animationTracks[ i ] );

						}

					}

					animations.push( new AnimationClip( 'default', - 1, tracks ) );

				}

			} else {

				for ( const id in clips ) {

					animations.push( getAnimationClip( id ) );

				}

			}

		}

		// convert the parser error element into text with each child elements text
		// separated by new lines.

		function parserErrorToText( parserError ) {

			let result = '';
			const stack = [ parserError ];

			while ( stack.length ) {

				const node = stack.shift();

				if ( node.nodeType === Node.TEXT_NODE ) {

					result += node.textContent;

				} else {

					result += '\n';
					stack.push( ...node.childNodes );

				}

			}

			return result.trim();

		}

		if ( text.length === 0 ) {

			return { scene: new Scene() };

		}

		const xml = new DOMParser().parseFromString( text, 'application/xml' );

		const collada = getElementsByTagName( xml, 'COLLADA' )[ 0 ];

		const parserError = xml.getElementsByTagName( 'parsererror' )[ 0 ];
		if ( parserError !== undefined ) {

			// Chrome will return parser error with a div in it

			const errorElement = getElementsByTagName( parserError, 'div' )[ 0 ];
			let errorText;

			if ( errorElement ) {

				errorText = errorElement.textContent;

			} else {

				errorText = parserErrorToText( parserError );

			}

			console.error( 'THREE.ColladaLoader: Failed to parse collada file.\n', errorText );

			return null;

		}

		// metadata

		const version = collada.getAttribute( 'version' );
		console.debug( 'THREE.ColladaLoader: File version', version );

		const asset = parseAsset( getElementsByTagName( collada, 'asset' )[ 0 ] );
		const textureLoader = new TextureLoader( this.manager );
		textureLoader.setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		let tgaLoader;

		if ( TGALoader ) {

			tgaLoader = new TGALoader( this.manager );
			tgaLoader.setPath( this.resourcePath || path );

		}

		//

		const tempColor = new Color();
		const animations = [];
		let kinematics = {};
		let count = 0;

		//

		const library = {
			animations: {},
			clips: {},
			controllers: {},
			images: {},
			effects: {},
			materials: {},
			cameras: {},
			lights: {},
			geometries: {},
			nodes: {},
			visualScenes: {},
			kinematicsModels: {},
			physicsModels: {},
			kinematicsScenes: {}
		};

		parseLibrary( collada, 'library_animations', 'animation', parseAnimation );
		parseLibrary( collada, 'library_animation_clips', 'animation_clip', parseAnimationClip );
		parseLibrary( collada, 'library_controllers', 'controller', parseController );
		parseLibrary( collada, 'library_images', 'image', parseImage );
		parseLibrary( collada, 'library_effects', 'effect', parseEffect );
		parseLibrary( collada, 'library_materials', 'material', parseMaterial );
		parseLibrary( collada, 'library_cameras', 'camera', parseCamera );
		parseLibrary( collada, 'library_lights', 'light', parseLight );
		parseLibrary( collada, 'library_geometries', 'geometry', parseGeometry );
		parseLibrary( collada, 'library_nodes', 'node', parseNode );
		parseLibrary( collada, 'library_visual_scenes', 'visual_scene', parseVisualScene );
		parseLibrary( collada, 'library_kinematics_models', 'kinematics_model', parseKinematicsModel );
		parseLibrary( collada, 'library_physics_models', 'physics_model', parsePhysicsModel );
		parseLibrary( collada, 'scene', 'instance_kinematics_scene', parseKinematicsScene );

		buildLibrary( library.animations, buildAnimation );
		buildLibrary( library.clips, buildAnimationClip );
		buildLibrary( library.controllers, buildController );
		buildLibrary( library.images, buildImage );
		buildLibrary( library.effects, buildEffect );
		buildLibrary( library.materials, buildMaterial );
		buildLibrary( library.cameras, buildCamera );
		buildLibrary( library.lights, buildLight );
		buildLibrary( library.geometries, buildGeometry );
		buildLibrary( library.visualScenes, buildVisualScene );

		setupAnimations();
		setupKinematics();

		const scene = parseScene( getElementsByTagName( collada, 'scene' )[ 0 ] );
		scene.animations = animations;

		if ( asset.upAxis === 'Z_UP' ) {

			console.warn( 'THREE.ColladaLoader: You are loading an asset with a Z-UP coordinate system. The loader just rotates the asset to transform it into Y-UP. The vertex data are not converted, see #24289.' );
			scene.rotation.set( - Math.PI / 2, 0, 0 );

		}

		scene.scale.multiplyScalar( asset.unit );

		return {
			get animations() {

				console.warn( 'THREE.ColladaLoader: Please access animations over scene.animations now.' );
				return animations;

			},
			kinematics: kinematics,
			library: library,
			scene: scene
		};

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: { scene: Group; animations: AnimationClip[]; kinematics: any; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( scope.path === '' ) ? LoaderUtils.extractUrlBase( url ) : scope.path;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text, path ) );

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

##### `parse(text: string, path: string): { scene: Group; animations: AnimationClip[]; kinematics: any; }`

<details><summary>Code</summary>

```ts
parse( text, path ) {

		function getElementsByTagName( xml, name ) {

			// Non recursive xml.getElementsByTagName() ...

			const array = [];
			const childNodes = xml.childNodes;

			for ( let i = 0, l = childNodes.length; i < l; i ++ ) {

				const child = childNodes[ i ];

				if ( child.nodeName === name ) {

					array.push( child );

				}

			}

			return array;

		}

		function parseStrings( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parts[ i ];

			}

			return array;

		}

		function parseFloats( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parseFloat( parts[ i ] );

			}

			return array;

		}

		function parseInts( text ) {

			if ( text.length === 0 ) return [];

			const parts = text.trim().split( /\s+/ );
			const array = new Array( parts.length );

			for ( let i = 0, l = parts.length; i < l; i ++ ) {

				array[ i ] = parseInt( parts[ i ] );

			}

			return array;

		}

		function parseId( text ) {

			return text.substring( 1 );

		}

		function generateId() {

			return 'three_default_' + ( count ++ );

		}

		function isEmpty( object ) {

			return Object.keys( object ).length === 0;

		}

		// asset

		function parseAsset( xml ) {

			return {
				unit: parseAssetUnit( getElementsByTagName( xml, 'unit' )[ 0 ] ),
				upAxis: parseAssetUpAxis( getElementsByTagName( xml, 'up_axis' )[ 0 ] )
			};

		}

		function parseAssetUnit( xml ) {

			if ( ( xml !== undefined ) && ( xml.hasAttribute( 'meter' ) === true ) ) {

				return parseFloat( xml.getAttribute( 'meter' ) );

			} else {

				return 1; // default 1 meter

			}

		}

		function parseAssetUpAxis( xml ) {

			return xml !== undefined ? xml.textContent : 'Y_UP';

		}

		// library

		function parseLibrary( xml, libraryName, nodeName, parser ) {

			const library = getElementsByTagName( xml, libraryName )[ 0 ];

			if ( library !== undefined ) {

				const elements = getElementsByTagName( library, nodeName );

				for ( let i = 0; i < elements.length; i ++ ) {

					parser( elements[ i ] );

				}

			}

		}

		function buildLibrary( data, builder ) {

			for ( const name in data ) {

				const object = data[ name ];
				object.build = builder( data[ name ] );

			}

		}

		// get

		function getBuild( data, builder ) {

			if ( data.build !== undefined ) return data.build;

			data.build = builder( data );

			return data.build;

		}

		// animation

		function parseAnimation( xml ) {

			const data = {
				sources: {},
				samplers: {},
				channels: {}
			};

			let hasChildren = false;

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let id;

				switch ( child.nodeName ) {

					case 'source':
						id = child.getAttribute( 'id' );
						data.sources[ id ] = parseSource( child );
						break;

					case 'sampler':
						id = child.getAttribute( 'id' );
						data.samplers[ id ] = parseAnimationSampler( child );
						break;

					case 'channel':
						id = child.getAttribute( 'target' );
						data.channels[ id ] = parseAnimationChannel( child );
						break;

					case 'animation':
						// hierarchy of related animations
						parseAnimation( child );
						hasChildren = true;
						break;

					default:
						console.log( child );

				}

			}

			if ( hasChildren === false ) {

				// since 'id' attributes can be optional, it's necessary to generate a UUID for unique assignment

				library.animations[ xml.getAttribute( 'id' ) || MathUtils.generateUUID() ] = data;

			}

		}

		function parseAnimationSampler( xml ) {

			const data = {
				inputs: {},
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const id = parseId( child.getAttribute( 'source' ) );
						const semantic = child.getAttribute( 'semantic' );
						data.inputs[ semantic ] = id;
						break;

				}

			}

			return data;

		}

		function parseAnimationChannel( xml ) {

			const data = {};

			const target = xml.getAttribute( 'target' );

			// parsing SID Addressing Syntax

			let parts = target.split( '/' );

			const id = parts.shift();
			let sid = parts.shift();

			// check selection syntax

			const arraySyntax = ( sid.indexOf( '(' ) !== - 1 );
			const memberSyntax = ( sid.indexOf( '.' ) !== - 1 );

			if ( memberSyntax ) {

				//  member selection access

				parts = sid.split( '.' );
				sid = parts.shift();
				data.member = parts.shift();

			} else if ( arraySyntax ) {

				// array-access syntax. can be used to express fields in one-dimensional vectors or two-dimensional matrices.

				const indices = sid.split( '(' );
				sid = indices.shift();

				for ( let i = 0; i < indices.length; i ++ ) {

					indices[ i ] = parseInt( indices[ i ].replace( /\)/, '' ) );

				}

				data.indices = indices;

			}

			data.id = id;
			data.sid = sid;

			data.arraySyntax = arraySyntax;
			data.memberSyntax = memberSyntax;

			data.sampler = parseId( xml.getAttribute( 'source' ) );

			return data;

		}

		function buildAnimation( data ) {

			const tracks = [];

			const channels = data.channels;
			const samplers = data.samplers;
			const sources = data.sources;

			for ( const target in channels ) {

				if ( channels.hasOwnProperty( target ) ) {

					const channel = channels[ target ];
					const sampler = samplers[ channel.sampler ];

					const inputId = sampler.inputs.INPUT;
					const outputId = sampler.inputs.OUTPUT;

					const inputSource = sources[ inputId ];
					const outputSource = sources[ outputId ];

					const animation = buildAnimationChannel( channel, inputSource, outputSource );

					createKeyframeTracks( animation, tracks );

				}

			}

			return tracks;

		}

		function getAnimation( id ) {

			return getBuild( library.animations[ id ], buildAnimation );

		}

		function buildAnimationChannel( channel, inputSource, outputSource ) {

			const node = library.nodes[ channel.id ];
			const object3D = getNode( node.id );

			const transform = node.transforms[ channel.sid ];
			const defaultMatrix = node.matrix.clone().transpose();

			let time, stride;
			let i, il, j, jl;

			const data = {};

			// the collada spec allows the animation of data in various ways.
			// depending on the transform type (matrix, translate, rotate, scale), we execute different logic

			switch ( transform ) {

				case 'matrix':

					for ( i = 0, il = inputSource.array.length; i < il; i ++ ) {

						time = inputSource.array[ i ];
						stride = i * outputSource.stride;

						if ( data[ time ] === undefined ) data[ time ] = {};

						if ( channel.arraySyntax === true ) {

							const value = outputSource.array[ stride ];
							const index = channel.indices[ 0 ] + 4 * channel.indices[ 1 ];

							data[ time ][ index ] = value;

						} else {

							for ( j = 0, jl = outputSource.stride; j < jl; j ++ ) {

								data[ time ][ j ] = outputSource.array[ stride + j ];

							}

						}

					}

					break;

				case 'translate':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

				case 'rotate':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

				case 'scale':
					console.warn( 'THREE.ColladaLoader: Animation transform type "%s" not yet implemented.', transform );
					break;

			}

			const keyframes = prepareAnimationData( data, defaultMatrix );

			const animation = {
				name: object3D.uuid,
				keyframes: keyframes
			};

			return animation;

		}

		function prepareAnimationData( data, defaultMatrix ) {

			const keyframes = [];

			// transfer data into a sortable array

			for ( const time in data ) {

				keyframes.push( { time: parseFloat( time ), value: data[ time ] } );

			}

			// ensure keyframes are sorted by time

			keyframes.sort( ascending );

			// now we clean up all animation data, so we can use them for keyframe tracks

			for ( let i = 0; i < 16; i ++ ) {

				transformAnimationData( keyframes, i, defaultMatrix.elements[ i ] );

			}

			return keyframes;

			// array sort function

			function ascending( a, b ) {

				return a.time - b.time;

			}

		}

		const position = new Vector3();
		const scale = new Vector3();
		const quaternion = new Quaternion();

		function createKeyframeTracks( animation, tracks ) {

			const keyframes = animation.keyframes;
			const name = animation.name;

			const times = [];
			const positionData = [];
			const quaternionData = [];
			const scaleData = [];

			for ( let i = 0, l = keyframes.length; i < l; i ++ ) {

				const keyframe = keyframes[ i ];

				const time = keyframe.time;
				const value = keyframe.value;

				matrix.fromArray( value ).transpose();
				matrix.decompose( position, quaternion, scale );

				times.push( time );
				positionData.push( position.x, position.y, position.z );
				quaternionData.push( quaternion.x, quaternion.y, quaternion.z, quaternion.w );
				scaleData.push( scale.x, scale.y, scale.z );

			}

			if ( positionData.length > 0 ) tracks.push( new VectorKeyframeTrack( name + '.position', times, positionData ) );
			if ( quaternionData.length > 0 ) tracks.push( new QuaternionKeyframeTrack( name + '.quaternion', times, quaternionData ) );
			if ( scaleData.length > 0 ) tracks.push( new VectorKeyframeTrack( name + '.scale', times, scaleData ) );

			return tracks;

		}

		function transformAnimationData( keyframes, property, defaultValue ) {

			let keyframe;

			let empty = true;
			let i, l;

			// check, if values of a property are missing in our keyframes

			for ( i = 0, l = keyframes.length; i < l; i ++ ) {

				keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] === undefined ) {

					keyframe.value[ property ] = null; // mark as missing

				} else {

					empty = false;

				}

			}

			if ( empty === true ) {

				// no values at all, so we set a default value

				for ( i = 0, l = keyframes.length; i < l; i ++ ) {

					keyframe = keyframes[ i ];

					keyframe.value[ property ] = defaultValue;

				}

			} else {

				// filling gaps

				createMissingKeyframes( keyframes, property );

			}

		}

		function createMissingKeyframes( keyframes, property ) {

			let prev, next;

			for ( let i = 0, l = keyframes.length; i < l; i ++ ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] === null ) {

					prev = getPrev( keyframes, i, property );
					next = getNext( keyframes, i, property );

					if ( prev === null ) {

						keyframe.value[ property ] = next.value[ property ];
						continue;

					}

					if ( next === null ) {

						keyframe.value[ property ] = prev.value[ property ];
						continue;

					}

					interpolate( keyframe, prev, next, property );

				}

			}

		}

		function getPrev( keyframes, i, property ) {

			while ( i >= 0 ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] !== null ) return keyframe;

				i --;

			}

			return null;

		}

		function getNext( keyframes, i, property ) {

			while ( i < keyframes.length ) {

				const keyframe = keyframes[ i ];

				if ( keyframe.value[ property ] !== null ) return keyframe;

				i ++;

			}

			return null;

		}

		function interpolate( key, prev, next, property ) {

			if ( ( next.time - prev.time ) === 0 ) {

				key.value[ property ] = prev.value[ property ];
				return;

			}

			key.value[ property ] = ( ( key.time - prev.time ) * ( next.value[ property ] - prev.value[ property ] ) / ( next.time - prev.time ) ) + prev.value[ property ];

		}

		// animation clips

		function parseAnimationClip( xml ) {

			const data = {
				name: xml.getAttribute( 'id' ) || 'default',
				start: parseFloat( xml.getAttribute( 'start' ) || 0 ),
				end: parseFloat( xml.getAttribute( 'end' ) || 0 ),
				animations: []
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'instance_animation':
						data.animations.push( parseId( child.getAttribute( 'url' ) ) );
						break;

				}

			}

			library.clips[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildAnimationClip( data ) {

			const tracks = [];

			const name = data.name;
			const duration = ( data.end - data.start ) || - 1;
			const animations = data.animations;

			for ( let i = 0, il = animations.length; i < il; i ++ ) {

				const animationTracks = getAnimation( animations[ i ] );

				for ( let j = 0, jl = animationTracks.length; j < jl; j ++ ) {

					tracks.push( animationTracks[ j ] );

				}

			}

			return new AnimationClip( name, duration, tracks );

		}

		function getAnimationClip( id ) {

			return getBuild( library.clips[ id ], buildAnimationClip );

		}

		// controller

		function parseController( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'skin':
						// there is exactly one skin per controller
						data.id = parseId( child.getAttribute( 'source' ) );
						data.skin = parseSkin( child );
						break;

					case 'morph':
						data.id = parseId( child.getAttribute( 'source' ) );
						console.warn( 'THREE.ColladaLoader: Morph target animation not supported yet.' );
						break;

				}

			}

			library.controllers[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseSkin( xml ) {

			const data = {
				sources: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'bind_shape_matrix':
						data.bindShapeMatrix = parseFloats( child.textContent );
						break;

					case 'source':
						const id = child.getAttribute( 'id' );
						data.sources[ id ] = parseSource( child );
						break;

					case 'joints':
						data.joints = parseJoints( child );
						break;

					case 'vertex_weights':
						data.vertexWeights = parseVertexWeights( child );
						break;

				}

			}

			return data;

		}

		function parseJoints( xml ) {

			const data = {
				inputs: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const semantic = child.getAttribute( 'semantic' );
						const id = parseId( child.getAttribute( 'source' ) );
						data.inputs[ semantic ] = id;
						break;

				}

			}

			return data;

		}

		function parseVertexWeights( xml ) {

			const data = {
				inputs: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const semantic = child.getAttribute( 'semantic' );
						const id = parseId( child.getAttribute( 'source' ) );
						const offset = parseInt( child.getAttribute( 'offset' ) );
						data.inputs[ semantic ] = { id: id, offset: offset };
						break;

					case 'vcount':
						data.vcount = parseInts( child.textContent );
						break;

					case 'v':
						data.v = parseInts( child.textContent );
						break;

				}

			}

			return data;

		}

		function buildController( data ) {

			const build = {
				id: data.id
			};

			const geometry = library.geometries[ build.id ];

			if ( data.skin !== undefined ) {

				build.skin = buildSkin( data.skin );

				// we enhance the 'sources' property of the corresponding geometry with our skin data

				geometry.sources.skinIndices = build.skin.indices;
				geometry.sources.skinWeights = build.skin.weights;

			}

			return build;

		}

		function buildSkin( data ) {

			const BONE_LIMIT = 4;

			const build = {
				joints: [], // this must be an array to preserve the joint order
				indices: {
					array: [],
					stride: BONE_LIMIT
				},
				weights: {
					array: [],
					stride: BONE_LIMIT
				}
			};

			const sources = data.sources;
			const vertexWeights = data.vertexWeights;

			const vcount = vertexWeights.vcount;
			const v = vertexWeights.v;
			const jointOffset = vertexWeights.inputs.JOINT.offset;
			const weightOffset = vertexWeights.inputs.WEIGHT.offset;

			const jointSource = data.sources[ data.joints.inputs.JOINT ];
			const inverseSource = data.sources[ data.joints.inputs.INV_BIND_MATRIX ];

			const weights = sources[ vertexWeights.inputs.WEIGHT.id ].array;
			let stride = 0;

			let i, j, l;

			// process skin data for each vertex

			for ( i = 0, l = vcount.length; i < l; i ++ ) {

				const jointCount = vcount[ i ]; // this is the amount of joints that affect a single vertex
				const vertexSkinData = [];

				for ( j = 0; j < jointCount; j ++ ) {

					const skinIndex = v[ stride + jointOffset ];
					const weightId = v[ stride + weightOffset ];
					const skinWeight = weights[ weightId ];

					vertexSkinData.push( { index: skinIndex, weight: skinWeight } );

					stride += 2;

				}

				// we sort the joints in descending order based on the weights.
				// this ensures, we only proceed the most important joints of the vertex

				vertexSkinData.sort( descending );

				// now we provide for each vertex a set of four index and weight values.
				// the order of the skin data matches the order of vertices

				for ( j = 0; j < BONE_LIMIT; j ++ ) {

					const d = vertexSkinData[ j ];

					if ( d !== undefined ) {

						build.indices.array.push( d.index );
						build.weights.array.push( d.weight );

					} else {

						build.indices.array.push( 0 );
						build.weights.array.push( 0 );

					}

				}

			}

			// setup bind matrix

			if ( data.bindShapeMatrix ) {

				build.bindMatrix = new Matrix4().fromArray( data.bindShapeMatrix ).transpose();

			} else {

				build.bindMatrix = new Matrix4().identity();

			}

			// process bones and inverse bind matrix data

			for ( i = 0, l = jointSource.array.length; i < l; i ++ ) {

				const name = jointSource.array[ i ];
				const boneInverse = new Matrix4().fromArray( inverseSource.array, i * inverseSource.stride ).transpose();

				build.joints.push( { name: name, boneInverse: boneInverse } );

			}

			return build;

			// array sort function

			function descending( a, b ) {

				return b.weight - a.weight;

			}

		}

		function getController( id ) {

			return getBuild( library.controllers[ id ], buildController );

		}

		// image

		function parseImage( xml ) {

			const data = {
				init_from: getElementsByTagName( xml, 'init_from' )[ 0 ].textContent
			};

			library.images[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildImage( data ) {

			if ( data.build !== undefined ) return data.build;

			return data.init_from;

		}

		function getImage( id ) {

			const data = library.images[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildImage );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find image with ID:', id );

			return null;

		}

		// effect

		function parseEffect( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'profile_COMMON':
						data.profile = parseEffectProfileCOMMON( child );
						break;

				}

			}

			library.effects[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseEffectProfileCOMMON( xml ) {

			const data = {
				surfaces: {},
				samplers: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'newparam':
						parseEffectNewparam( child, data );
						break;

					case 'technique':
						data.technique = parseEffectTechnique( child );
						break;

					case 'extra':
						data.extra = parseEffectExtra( child );
						break;

				}

			}

			return data;

		}

		function parseEffectNewparam( xml, data ) {

			const sid = xml.getAttribute( 'sid' );

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'surface':
						data.surfaces[ sid ] = parseEffectSurface( child );
						break;

					case 'sampler2D':
						data.samplers[ sid ] = parseEffectSampler( child );
						break;

				}

			}

		}

		function parseEffectSurface( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'init_from':
						data.init_from = child.textContent;
						break;

				}

			}

			return data;

		}

		function parseEffectSampler( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'source':
						data.source = child.textContent;
						break;

				}

			}

			return data;

		}

		function parseEffectTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'constant':
					case 'lambert':
					case 'blinn':
					case 'phong':
						data.type = child.nodeName;
						data.parameters = parseEffectParameters( child );
						break;

					case 'extra':
						data.extra = parseEffectExtra( child );
						break;

				}

			}

			return data;

		}

		function parseEffectParameters( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'emission':
					case 'diffuse':
					case 'specular':
					case 'bump':
					case 'ambient':
					case 'shininess':
					case 'transparency':
						data[ child.nodeName ] = parseEffectParameter( child );
						break;
					case 'transparent':
						data[ child.nodeName ] = {
							opaque: child.hasAttribute( 'opaque' ) ? child.getAttribute( 'opaque' ) : 'A_ONE',
							data: parseEffectParameter( child )
						};
						break;

				}

			}

			return data;

		}

		function parseEffectParameter( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'color':
						data[ child.nodeName ] = parseFloats( child.textContent );
						break;

					case 'float':
						data[ child.nodeName ] = parseFloat( child.textContent );
						break;

					case 'texture':
						data[ child.nodeName ] = { id: child.getAttribute( 'texture' ), extra: parseEffectParameterTexture( child ) };
						break;

				}

			}

			return data;

		}

		function parseEffectParameterTexture( xml ) {

			const data = {
				technique: {}
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'extra':
						parseEffectParameterTextureExtra( child, data );
						break;

				}

			}

			return data;

		}

		function parseEffectParameterTextureExtra( xml, data ) {

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique':
						parseEffectParameterTextureExtraTechnique( child, data );
						break;

				}

			}

		}

		function parseEffectParameterTextureExtraTechnique( xml, data ) {

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'repeatU':
					case 'repeatV':
					case 'offsetU':
					case 'offsetV':
						data.technique[ child.nodeName ] = parseFloat( child.textContent );
						break;

					case 'wrapU':
					case 'wrapV':

						// some files have values for wrapU/wrapV which become NaN via parseInt

						if ( child.textContent.toUpperCase() === 'TRUE' ) {

							data.technique[ child.nodeName ] = 1;

						} else if ( child.textContent.toUpperCase() === 'FALSE' ) {

							data.technique[ child.nodeName ] = 0;

						} else {

							data.technique[ child.nodeName ] = parseInt( child.textContent );

						}

						break;

					case 'bump':
						data[ child.nodeName ] = parseEffectExtraTechniqueBump( child );
						break;

				}

			}

		}

		function parseEffectExtra( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique':
						data.technique = parseEffectExtraTechnique( child );
						break;

				}

			}

			return data;

		}

		function parseEffectExtraTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'double_sided':
						data[ child.nodeName ] = parseInt( child.textContent );
						break;

					case 'bump':
						data[ child.nodeName ] = parseEffectExtraTechniqueBump( child );
						break;

				}

			}

			return data;

		}

		function parseEffectExtraTechniqueBump( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'texture':
						data[ child.nodeName ] = { id: child.getAttribute( 'texture' ), texcoord: child.getAttribute( 'texcoord' ), extra: parseEffectParameterTexture( child ) };
						break;

				}

			}

			return data;

		}

		function buildEffect( data ) {

			return data;

		}

		function getEffect( id ) {

			return getBuild( library.effects[ id ], buildEffect );

		}

		// material

		function parseMaterial( xml ) {

			const data = {
				name: xml.getAttribute( 'name' )
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'instance_effect':
						data.url = parseId( child.getAttribute( 'url' ) );
						break;

				}

			}

			library.materials[ xml.getAttribute( 'id' ) ] = data;

		}

		function getTextureLoader( image ) {

			let loader;

			let extension = image.slice( ( image.lastIndexOf( '.' ) - 1 >>> 0 ) + 2 ); // http://www.jstips.co/en/javascript/get-file-extension/
			extension = extension.toLowerCase();

			switch ( extension ) {

				case 'tga':
					loader = tgaLoader;
					break;

				default:
					loader = textureLoader;

			}

			return loader;

		}

		function buildMaterial( data ) {

			const effect = getEffect( data.url );
			const technique = effect.profile.technique;

			let material;

			switch ( technique.type ) {

				case 'phong':
				case 'blinn':
					material = new MeshPhongMaterial();
					break;

				case 'lambert':
					material = new MeshLambertMaterial();
					break;

				default:
					material = new MeshBasicMaterial();
					break;

			}

			material.name = data.name || '';

			function getTexture( textureObject, colorSpace = null ) {

				const sampler = effect.profile.samplers[ textureObject.id ];
				let image = null;

				// get image

				if ( sampler !== undefined ) {

					const surface = effect.profile.surfaces[ sampler.source ];
					image = getImage( surface.init_from );

				} else {

					console.warn( 'THREE.ColladaLoader: Undefined sampler. Access image directly (see #12530).' );
					image = getImage( textureObject.id );

				}

				// create texture if image is available

				if ( image !== null ) {

					const loader = getTextureLoader( image );

					if ( loader !== undefined ) {

						const texture = loader.load( image );

						const extra = textureObject.extra;

						if ( extra !== undefined && extra.technique !== undefined && isEmpty( extra.technique ) === false ) {

							const technique = extra.technique;

							texture.wrapS = technique.wrapU ? RepeatWrapping : ClampToEdgeWrapping;
							texture.wrapT = technique.wrapV ? RepeatWrapping : ClampToEdgeWrapping;

							texture.offset.set( technique.offsetU || 0, technique.offsetV || 0 );
							texture.repeat.set( technique.repeatU || 1, technique.repeatV || 1 );

						} else {

							texture.wrapS = RepeatWrapping;
							texture.wrapT = RepeatWrapping;

						}

						if ( colorSpace !== null ) {

							texture.colorSpace = colorSpace;

						}

						return texture;

					} else {

						console.warn( 'THREE.ColladaLoader: Loader for texture %s not found.', image );

						return null;

					}

				} else {

					console.warn( 'THREE.ColladaLoader: Couldn\'t create texture with ID:', textureObject.id );

					return null;

				}

			}

			const parameters = technique.parameters;

			for ( const key in parameters ) {

				const parameter = parameters[ key ];

				switch ( key ) {

					case 'diffuse':
						if ( parameter.color ) material.color.fromArray( parameter.color );
						if ( parameter.texture ) material.map = getTexture( parameter.texture, SRGBColorSpace );
						break;
					case 'specular':
						if ( parameter.color && material.specular ) material.specular.fromArray( parameter.color );
						if ( parameter.texture ) material.specularMap = getTexture( parameter.texture );
						break;
					case 'bump':
						if ( parameter.texture ) material.normalMap = getTexture( parameter.texture );
						break;
					case 'ambient':
						if ( parameter.texture ) material.lightMap = getTexture( parameter.texture, SRGBColorSpace );
						break;
					case 'shininess':
						if ( parameter.float && material.shininess ) material.shininess = parameter.float;
						break;
					case 'emission':
						if ( parameter.color && material.emissive ) material.emissive.fromArray( parameter.color );
						if ( parameter.texture ) material.emissiveMap = getTexture( parameter.texture, SRGBColorSpace );
						break;

				}

			}

			ColorManagement.colorSpaceToWorking( material.color, SRGBColorSpace );
			if ( material.specular ) ColorManagement.colorSpaceToWorking( material.specular, SRGBColorSpace );
			if ( material.emissive ) ColorManagement.colorSpaceToWorking( material.emissive, SRGBColorSpace );

			//

			let transparent = parameters[ 'transparent' ];
			let transparency = parameters[ 'transparency' ];

			// <transparency> does not exist but <transparent>

			if ( transparency === undefined && transparent ) {

				transparency = {
					float: 1
				};

			}

			// <transparent> does not exist but <transparency>

			if ( transparent === undefined && transparency ) {

				transparent = {
					opaque: 'A_ONE',
					data: {
						color: [ 1, 1, 1, 1 ]
					} };

			}

			if ( transparent && transparency ) {

				// handle case if a texture exists but no color

				if ( transparent.data.texture ) {

					// we do not set an alpha map (see #13792)

					material.transparent = true;

				} else {

					const color = transparent.data.color;

					switch ( transparent.opaque ) {

						case 'A_ONE':
							material.opacity = color[ 3 ] * transparency.float;
							break;
						case 'RGB_ZERO':
							material.opacity = 1 - ( color[ 0 ] * transparency.float );
							break;
						case 'A_ZERO':
							material.opacity = 1 - ( color[ 3 ] * transparency.float );
							break;
						case 'RGB_ONE':
							material.opacity = color[ 0 ] * transparency.float;
							break;
						default:
							console.warn( 'THREE.ColladaLoader: Invalid opaque type "%s" of transparent tag.', transparent.opaque );

					}

					if ( material.opacity < 1 ) material.transparent = true;

				}

			}

			//


			if ( technique.extra !== undefined && technique.extra.technique !== undefined ) {

				const techniques = technique.extra.technique;

				for ( const k in techniques ) {

					const v = techniques[ k ];

					switch ( k ) {

						case 'double_sided':
							material.side = ( v === 1 ? DoubleSide : FrontSide );
							break;

						case 'bump':
							material.normalMap = getTexture( v.texture );
							material.normalScale = new Vector2( 1, 1 );
							break;

					}

				}

			}

			return material;

		}

		function getMaterial( id ) {

			return getBuild( library.materials[ id ], buildMaterial );

		}

		// camera

		function parseCamera( xml ) {

			const data = {
				name: xml.getAttribute( 'name' )
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'optics':
						data.optics = parseCameraOptics( child );
						break;

				}

			}

			library.cameras[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseCameraOptics( xml ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'technique_common':
						return parseCameraTechnique( child );

				}

			}

			return {};

		}

		function parseCameraTechnique( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'perspective':
					case 'orthographic':

						data.technique = child.nodeName;
						data.parameters = parseCameraParameters( child );

						break;

				}

			}

			return data;

		}

		function parseCameraParameters( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'xfov':
					case 'yfov':
					case 'xmag':
					case 'ymag':
					case 'znear':
					case 'zfar':
					case 'aspect_ratio':
						data[ child.nodeName ] = parseFloat( child.textContent );
						break;

				}

			}

			return data;

		}

		function buildCamera( data ) {

			let camera;

			switch ( data.optics.technique ) {

				case 'perspective':
					camera = new PerspectiveCamera(
						data.optics.parameters.yfov,
						data.optics.parameters.aspect_ratio,
						data.optics.parameters.znear,
						data.optics.parameters.zfar
					);
					break;

				case 'orthographic':
					let ymag = data.optics.parameters.ymag;
					let xmag = data.optics.parameters.xmag;
					const aspectRatio = data.optics.parameters.aspect_ratio;

					xmag = ( xmag === undefined ) ? ( ymag * aspectRatio ) : xmag;
					ymag = ( ymag === undefined ) ? ( xmag / aspectRatio ) : ymag;

					xmag *= 0.5;
					ymag *= 0.5;

					camera = new OrthographicCamera(
						- xmag, xmag, ymag, - ymag, // left, right, top, bottom
						data.optics.parameters.znear,
						data.optics.parameters.zfar
					);
					break;

				default:
					camera = new PerspectiveCamera();
					break;

			}

			camera.name = data.name || '';

			return camera;

		}

		function getCamera( id ) {

			const data = library.cameras[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildCamera );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find camera with ID:', id );

			return null;

		}

		// light

		function parseLight( xml ) {

			let data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						data = parseLightTechnique( child );
						break;

				}

			}

			library.lights[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseLightTechnique( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'directional':
					case 'point':
					case 'spot':
					case 'ambient':

						data.technique = child.nodeName;
						data.parameters = parseLightParameters( child );

				}

			}

			return data;

		}

		function parseLightParameters( xml ) {

			const data = {};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'color':
						const array = parseFloats( child.textContent );
						data.color = new Color().fromArray( array );
						ColorManagement.colorSpaceToWorking( data.color, SRGBColorSpace );
						break;

					case 'falloff_angle':
						data.falloffAngle = parseFloat( child.textContent );
						break;

					case 'quadratic_attenuation':
						const f = parseFloat( child.textContent );
						data.distance = f ? Math.sqrt( 1 / f ) : 0;
						break;

				}

			}

			return data;

		}

		function buildLight( data ) {

			let light;

			switch ( data.technique ) {

				case 'directional':
					light = new DirectionalLight();
					break;

				case 'point':
					light = new PointLight();
					break;

				case 'spot':
					light = new SpotLight();
					break;

				case 'ambient':
					light = new AmbientLight();
					break;

			}

			if ( data.parameters.color ) light.color.copy( data.parameters.color );
			if ( data.parameters.distance ) light.distance = data.parameters.distance;

			return light;

		}

		function getLight( id ) {

			const data = library.lights[ id ];

			if ( data !== undefined ) {

				return getBuild( data, buildLight );

			}

			console.warn( 'THREE.ColladaLoader: Couldn\'t find light with ID:', id );

			return null;

		}

		// geometry

		function parseGeometry( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ),
				sources: {},
				vertices: {},
				primitives: []
			};

			const mesh = getElementsByTagName( xml, 'mesh' )[ 0 ];

			// the following tags inside geometry are not supported yet (see https://github.com/mrdoob/three.js/pull/12606): convex_mesh, spline, brep
			if ( mesh === undefined ) return;

			for ( let i = 0; i < mesh.childNodes.length; i ++ ) {

				const child = mesh.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				const id = child.getAttribute( 'id' );

				switch ( child.nodeName ) {

					case 'source':
						data.sources[ id ] = parseSource( child );
						break;

					case 'vertices':
						// data.sources[ id ] = data.sources[ parseId( getElementsByTagName( child, 'input' )[ 0 ].getAttribute( 'source' ) ) ];
						data.vertices = parseGeometryVertices( child );
						break;

					case 'polygons':
						console.warn( 'THREE.ColladaLoader: Unsupported primitive type: ', child.nodeName );
						break;

					case 'lines':
					case 'linestrips':
					case 'polylist':
					case 'triangles':
						data.primitives.push( parseGeometryPrimitive( child ) );
						break;

					default:
						console.log( child );

				}

			}

			library.geometries[ xml.getAttribute( 'id' ) ] = data;

		}

		function parseSource( xml ) {

			const data = {
				array: [],
				stride: 3
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'float_array':
						data.array = parseFloats( child.textContent );
						break;

					case 'Name_array':
						data.array = parseStrings( child.textContent );
						break;

					case 'technique_common':
						const accessor = getElementsByTagName( child, 'accessor' )[ 0 ];

						if ( accessor !== undefined ) {

							data.stride = parseInt( accessor.getAttribute( 'stride' ) );

						}

						break;

				}

			}

			return data;

		}

		function parseGeometryVertices( xml ) {

			const data = {};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				data[ child.getAttribute( 'semantic' ) ] = parseId( child.getAttribute( 'source' ) );

			}

			return data;

		}

		function parseGeometryPrimitive( xml ) {

			const primitive = {
				type: xml.nodeName,
				material: xml.getAttribute( 'material' ),
				count: parseInt( xml.getAttribute( 'count' ) ),
				inputs: {},
				stride: 0,
				hasUV: false
			};

			for ( let i = 0, l = xml.childNodes.length; i < l; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'input':
						const id = parseId( child.getAttribute( 'source' ) );
						const semantic = child.getAttribute( 'semantic' );
						const offset = parseInt( child.getAttribute( 'offset' ) );
						const set = parseInt( child.getAttribute( 'set' ) );
						const inputname = ( set > 0 ? semantic + set : semantic );
						primitive.inputs[ inputname ] = { id: id, offset: offset };
						primitive.stride = Math.max( primitive.stride, offset + 1 );
						if ( semantic === 'TEXCOORD' ) primitive.hasUV = true;
						break;

					case 'vcount':
						primitive.vcount = parseInts( child.textContent );
						break;

					case 'p':
						primitive.p = parseInts( child.textContent );
						break;

				}

			}

			return primitive;

		}

		function groupPrimitives( primitives ) {

			const build = {};

			for ( let i = 0; i < primitives.length; i ++ ) {

				const primitive = primitives[ i ];

				if ( build[ primitive.type ] === undefined ) build[ primitive.type ] = [];

				build[ primitive.type ].push( primitive );

			}

			return build;

		}

		function checkUVCoordinates( primitives ) {

			let count = 0;

			for ( let i = 0, l = primitives.length; i < l; i ++ ) {

				const primitive = primitives[ i ];

				if ( primitive.hasUV === true ) {

					count ++;

				}

			}

			if ( count > 0 && count < primitives.length ) {

				primitives.uvsNeedsFix = true;

			}

		}

		function buildGeometry( data ) {

			const build = {};

			const sources = data.sources;
			const vertices = data.vertices;
			const primitives = data.primitives;

			if ( primitives.length === 0 ) return {};

			// our goal is to create one buffer geometry for a single type of primitives
			// first, we group all primitives by their type

			const groupedPrimitives = groupPrimitives( primitives );

			for ( const type in groupedPrimitives ) {

				const primitiveType = groupedPrimitives[ type ];

				// second, ensure consistent uv coordinates for each type of primitives (polylist,triangles or lines)

				checkUVCoordinates( primitiveType );

				// third, create a buffer geometry for each type of primitives

				build[ type ] = buildGeometryType( primitiveType, sources, vertices );

			}

			return build;

		}

		function buildGeometryType( primitives, sources, vertices ) {

			const build = {};

			const position = { array: [], stride: 0 };
			const normal = { array: [], stride: 0 };
			const uv = { array: [], stride: 0 };
			const uv1 = { array: [], stride: 0 };
			const color = { array: [], stride: 0 };

			const skinIndex = { array: [], stride: 4 };
			const skinWeight = { array: [], stride: 4 };

			const geometry = new BufferGeometry();

			const materialKeys = [];

			let start = 0;

			for ( let p = 0; p < primitives.length; p ++ ) {

				const primitive = primitives[ p ];
				const inputs = primitive.inputs;

				// groups

				let count = 0;

				switch ( primitive.type ) {

					case 'lines':
					case 'linestrips':
						count = primitive.count * 2;
						break;

					case 'triangles':
						count = primitive.count * 3;
						break;

					case 'polylist':

						for ( let g = 0; g < primitive.count; g ++ ) {

							const vc = primitive.vcount[ g ];

							switch ( vc ) {

								case 3:
									count += 3; // single triangle
									break;

								case 4:
									count += 6; // quad, subdivided into two triangles
									break;

								default:
									count += ( vc - 2 ) * 3; // polylist with more than four vertices
									break;

							}

						}

						break;

					default:
						console.warn( 'THREE.ColladaLoader: Unknown primitive type:', primitive.type );

				}

				geometry.addGroup( start, count, p );
				start += count;

				// material

				if ( primitive.material ) {

					materialKeys.push( primitive.material );

				}

				// geometry data

				for ( const name in inputs ) {

					const input = inputs[ name ];

					switch ( name )	{

						case 'VERTEX':
							for ( const key in vertices ) {

								const id = vertices[ key ];

								switch ( key ) {

									case 'POSITION':
										const prevLength = position.array.length;
										buildGeometryData( primitive, sources[ id ], input.offset, position.array );
										position.stride = sources[ id ].stride;

										if ( sources.skinWeights && sources.skinIndices ) {

											buildGeometryData( primitive, sources.skinIndices, input.offset, skinIndex.array );
											buildGeometryData( primitive, sources.skinWeights, input.offset, skinWeight.array );

										}

										// see #3803

										if ( primitive.hasUV === false && primitives.uvsNeedsFix === true ) {

											const count = ( position.array.length - prevLength ) / position.stride;

											for ( let i = 0; i < count; i ++ ) {

												// fill missing uv coordinates

												uv.array.push( 0, 0 );

											}

										}

										break;

									case 'NORMAL':
										buildGeometryData( primitive, sources[ id ], input.offset, normal.array );
										normal.stride = sources[ id ].stride;
										break;

									case 'COLOR':
										buildGeometryData( primitive, sources[ id ], input.offset, color.array );
										color.stride = sources[ id ].stride;
										break;

									case 'TEXCOORD':
										buildGeometryData( primitive, sources[ id ], input.offset, uv.array );
										uv.stride = sources[ id ].stride;
										break;

									case 'TEXCOORD1':
										buildGeometryData( primitive, sources[ id ], input.offset, uv1.array );
										uv.stride = sources[ id ].stride;
										break;

									default:
										console.warn( 'THREE.ColladaLoader: Semantic "%s" not handled in geometry build process.', key );

								}

							}

							break;

						case 'NORMAL':
							buildGeometryData( primitive, sources[ input.id ], input.offset, normal.array );
							normal.stride = sources[ input.id ].stride;
							break;

						case 'COLOR':
							buildGeometryData( primitive, sources[ input.id ], input.offset, color.array, true );
							color.stride = sources[ input.id ].stride;
							break;

						case 'TEXCOORD':
							buildGeometryData( primitive, sources[ input.id ], input.offset, uv.array );
							uv.stride = sources[ input.id ].stride;
							break;

						case 'TEXCOORD1':
							buildGeometryData( primitive, sources[ input.id ], input.offset, uv1.array );
							uv1.stride = sources[ input.id ].stride;
							break;

					}

				}

			}

			// build geometry

			if ( position.array.length > 0 ) geometry.setAttribute( 'position', new Float32BufferAttribute( position.array, position.stride ) );
			if ( normal.array.length > 0 ) geometry.setAttribute( 'normal', new Float32BufferAttribute( normal.array, normal.stride ) );
			if ( color.array.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( color.array, color.stride ) );
			if ( uv.array.length > 0 ) geometry.setAttribute( 'uv', new Float32BufferAttribute( uv.array, uv.stride ) );
			if ( uv1.array.length > 0 ) geometry.setAttribute( 'uv1', new Float32BufferAttribute( uv1.array, uv1.stride ) );

			if ( skinIndex.array.length > 0 ) geometry.setAttribute( 'skinIndex', new Float32BufferAttribute( skinIndex.array, skinIndex.stride ) );
			if ( skinWeight.array.length > 0 ) geometry.setAttribute( 'skinWeight', new Float32BufferAttribute( skinWeight.array, skinWeight.stride ) );

			build.data = geometry;
			build.type = primitives[ 0 ].type;
			build.materialKeys = materialKeys;

			return build;

		}

		function buildGeometryData( primitive, source, offset, array, isColor = false ) {

			const indices = primitive.p;
			const stride = primitive.stride;
			const vcount = primitive.vcount;

			function pushVector( i ) {

				let index = indices[ i + offset ] * sourceStride;
				const length = index + sourceStride;

				for ( ; index < length; index ++ ) {

					array.push( sourceArray[ index ] );

				}

				if ( isColor ) {

					// convert the vertex colors from srgb to linear if present
					const startIndex = array.length - sourceStride - 1;
					tempColor.setRGB(
						array[ startIndex + 0 ],
						array[ startIndex + 1 ],
						array[ startIndex + 2 ],
						SRGBColorSpace
					);

					array[ startIndex + 0 ] = tempColor.r;
					array[ startIndex + 1 ] = tempColor.g;
					array[ startIndex + 2 ] = tempColor.b;

				}

			}

			const sourceArray = source.array;
			const sourceStride = source.stride;

			if ( primitive.vcount !== undefined ) {

				let index = 0;

				for ( let i = 0, l = vcount.length; i < l; i ++ ) {

					const count = vcount[ i ];

					if ( count === 4 ) {

						const a = index + stride * 0;
						const b = index + stride * 1;
						const c = index + stride * 2;
						const d = index + stride * 3;

						pushVector( a ); pushVector( b ); pushVector( d );
						pushVector( b ); pushVector( c ); pushVector( d );

					} else if ( count === 3 ) {

						const a = index + stride * 0;
						const b = index + stride * 1;
						const c = index + stride * 2;

						pushVector( a ); pushVector( b ); pushVector( c );

					} else if ( count > 4 ) {

						for ( let k = 1, kl = ( count - 2 ); k <= kl; k ++ ) {

							const a = index + stride * 0;
							const b = index + stride * k;
							const c = index + stride * ( k + 1 );

							pushVector( a ); pushVector( b ); pushVector( c );

						}

					}

					index += stride * count;

				}

			} else {

				for ( let i = 0, l = indices.length; i < l; i += stride ) {

					pushVector( i );

				}

			}

		}

		function getGeometry( id ) {

			return getBuild( library.geometries[ id ], buildGeometry );

		}

		// kinematics

		function parseKinematicsModel( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				joints: {},
				links: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						parseKinematicsTechniqueCommon( child, data );
						break;

				}

			}

			library.kinematicsModels[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildKinematicsModel( data ) {

			if ( data.build !== undefined ) return data.build;

			return data;

		}

		function getKinematicsModel( id ) {

			return getBuild( library.kinematicsModels[ id ], buildKinematicsModel );

		}

		function parseKinematicsTechniqueCommon( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'joint':
						data.joints[ child.getAttribute( 'sid' ) ] = parseKinematicsJoint( child );
						break;

					case 'link':
						data.links.push( parseKinematicsLink( child ) );
						break;

				}

			}

		}

		function parseKinematicsJoint( xml ) {

			let data;

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'prismatic':
					case 'revolute':
						data = parseKinematicsJointParameter( child );
						break;

				}

			}

			return data;

		}

		function parseKinematicsJointParameter( xml ) {

			const data = {
				sid: xml.getAttribute( 'sid' ),
				name: xml.getAttribute( 'name' ) || '',
				axis: new Vector3(),
				limits: {
					min: 0,
					max: 0
				},
				type: xml.nodeName,
				static: false,
				zeroPosition: 0,
				middlePosition: 0
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'axis':
						const array = parseFloats( child.textContent );
						data.axis.fromArray( array );
						break;
					case 'limits':
						const max = child.getElementsByTagName( 'max' )[ 0 ];
						const min = child.getElementsByTagName( 'min' )[ 0 ];

						data.limits.max = parseFloat( max.textContent );
						data.limits.min = parseFloat( min.textContent );
						break;

				}

			}

			// if min is equal to or greater than max, consider the joint static

			if ( data.limits.min >= data.limits.max ) {

				data.static = true;

			}

			// calculate middle position

			data.middlePosition = ( data.limits.min + data.limits.max ) / 2.0;

			return data;

		}

		function parseKinematicsLink( xml ) {

			const data = {
				sid: xml.getAttribute( 'sid' ),
				name: xml.getAttribute( 'name' ) || '',
				attachments: [],
				transforms: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'attachment_full':
						data.attachments.push( parseKinematicsAttachment( child ) );
						break;

					case 'matrix':
					case 'translate':
					case 'rotate':
						data.transforms.push( parseKinematicsTransform( child ) );
						break;

				}

			}

			return data;

		}

		function parseKinematicsAttachment( xml ) {

			const data = {
				joint: xml.getAttribute( 'joint' ).split( '/' ).pop(),
				transforms: [],
				links: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'link':
						data.links.push( parseKinematicsLink( child ) );
						break;

					case 'matrix':
					case 'translate':
					case 'rotate':
						data.transforms.push( parseKinematicsTransform( child ) );
						break;

				}

			}

			return data;

		}

		function parseKinematicsTransform( xml ) {

			const data = {
				type: xml.nodeName
			};

			const array = parseFloats( xml.textContent );

			switch ( data.type ) {

				case 'matrix':
					data.obj = new Matrix4();
					data.obj.fromArray( array ).transpose();
					break;

				case 'translate':
					data.obj = new Vector3();
					data.obj.fromArray( array );
					break;

				case 'rotate':
					data.obj = new Vector3();
					data.obj.fromArray( array );
					data.angle = MathUtils.degToRad( array[ 3 ] );
					break;

			}

			return data;

		}

		// physics

		function parsePhysicsModel( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				rigidBodies: {}
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'rigid_body':
						data.rigidBodies[ child.getAttribute( 'name' ) ] = {};
						parsePhysicsRigidBody( child, data.rigidBodies[ child.getAttribute( 'name' ) ] );
						break;

				}

			}

			library.physicsModels[ xml.getAttribute( 'id' ) ] = data;

		}

		function parsePhysicsRigidBody( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'technique_common':
						parsePhysicsTechniqueCommon( child, data );
						break;

				}

			}

		}

		function parsePhysicsTechniqueCommon( xml, data ) {

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'inertia':
						data.inertia = parseFloats( child.textContent );
						break;

					case 'mass':
						data.mass = parseFloats( child.textContent )[ 0 ];
						break;

				}

			}

		}

		// scene

		function parseKinematicsScene( xml ) {

			const data = {
				bindJointAxis: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'bind_joint_axis':
						data.bindJointAxis.push( parseKinematicsBindJointAxis( child ) );
						break;

				}

			}

			library.kinematicsScenes[ parseId( xml.getAttribute( 'url' ) ) ] = data;

		}

		function parseKinematicsBindJointAxis( xml ) {

			const data = {
				target: xml.getAttribute( 'target' ).split( '/' ).pop()
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				switch ( child.nodeName ) {

					case 'axis':
						const param = child.getElementsByTagName( 'param' )[ 0 ];
						data.axis = param.textContent;
						const tmpJointIndex = data.axis.split( 'inst_' ).pop().split( 'axis' )[ 0 ];
						data.jointIndex = tmpJointIndex.substring( 0, tmpJointIndex.length - 1 );
						break;

				}

			}

			return data;

		}

		function buildKinematicsScene( data ) {

			if ( data.build !== undefined ) return data.build;

			return data;

		}

		function getKinematicsScene( id ) {

			return getBuild( library.kinematicsScenes[ id ], buildKinematicsScene );

		}

		function setupKinematics() {

			const kinematicsModelId = Object.keys( library.kinematicsModels )[ 0 ];
			const kinematicsSceneId = Object.keys( library.kinematicsScenes )[ 0 ];
			const visualSceneId = Object.keys( library.visualScenes )[ 0 ];

			if ( kinematicsModelId === undefined || kinematicsSceneId === undefined ) return;

			const kinematicsModel = getKinematicsModel( kinematicsModelId );
			const kinematicsScene = getKinematicsScene( kinematicsSceneId );
			const visualScene = getVisualScene( visualSceneId );

			const bindJointAxis = kinematicsScene.bindJointAxis;
			const jointMap = {};

			for ( let i = 0, l = bindJointAxis.length; i < l; i ++ ) {

				const axis = bindJointAxis[ i ];

				// the result of the following query is an element of type 'translate', 'rotate','scale' or 'matrix'

				const targetElement = collada.querySelector( '[sid="' + axis.target + '"]' );

				if ( targetElement ) {

					// get the parent of the transform element

					const parentVisualElement = targetElement.parentElement;

					// connect the joint of the kinematics model with the element in the visual scene

					connect( axis.jointIndex, parentVisualElement );

				}

			}

			function connect( jointIndex, visualElement ) {

				const visualElementName = visualElement.getAttribute( 'name' );
				const joint = kinematicsModel.joints[ jointIndex ];

				visualScene.traverse( function ( object ) {

					if ( object.name === visualElementName ) {

						jointMap[ jointIndex ] = {
							object: object,
							transforms: buildTransformList( visualElement ),
							joint: joint,
							position: joint.zeroPosition
						};

					}

				} );

			}

			const m0 = new Matrix4();

			kinematics = {

				joints: kinematicsModel && kinematicsModel.joints,

				getJointValue: function ( jointIndex ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						return jointData.position;

					} else {

						console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' doesn\'t exist.' );

					}

				},

				setJointValue: function ( jointIndex, value ) {

					const jointData = jointMap[ jointIndex ];

					if ( jointData ) {

						const joint = jointData.joint;

						if ( value > joint.limits.max || value < joint.limits.min ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' value ' + value + ' outside of limits (min: ' + joint.limits.min + ', max: ' + joint.limits.max + ').' );

						} else if ( joint.static ) {

							console.warn( 'THREE.ColladaLoader: Joint ' + jointIndex + ' is static.' );

						} else {

							const object = jointData.object;
							const axis = joint.axis;
							const transforms = jointData.transforms;

							matrix.identity();

							// each update, we have to apply all transforms in the correct order

							for ( let i = 0; i < transforms.length; i ++ ) {

								const transform = transforms[ i ];

								// if there is a connection of the transform node with a joint, apply the joint value

								if ( transform.sid && transform.sid.indexOf( jointIndex ) !== - 1 ) {

									switch ( joint.type ) {

										case 'revolute':
											matrix.multiply( m0.makeRotationAxis( axis, MathUtils.degToRad( value ) ) );
											break;

										case 'prismatic':
											matrix.multiply( m0.makeTranslation( axis.x * value, axis.y * value, axis.z * value ) );
											break;

										default:
											console.warn( 'THREE.ColladaLoader: Unknown joint type: ' + joint.type );
											break;

									}

								} else {

									switch ( transform.type ) {

										case 'matrix':
											matrix.multiply( transform.obj );
											break;

										case 'translate':
											matrix.multiply( m0.makeTranslation( transform.obj.x, transform.obj.y, transform.obj.z ) );
											break;

										case 'scale':
											matrix.scale( transform.obj );
											break;

										case 'rotate':
											matrix.multiply( m0.makeRotationAxis( transform.obj, transform.angle ) );
											break;

									}

								}

							}

							object.matrix.copy( matrix );
							object.matrix.decompose( object.position, object.quaternion, object.scale );

							jointMap[ jointIndex ].position = value;

						}

					} else {

						console.log( 'THREE.ColladaLoader: ' + jointIndex + ' does not exist.' );

					}

				}

			};

		}

		function buildTransformList( node ) {

			const transforms = [];

			const xml = collada.querySelector( '[id="' + node.id + '"]' );

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let array, vector;

				switch ( child.nodeName ) {

					case 'matrix':
						array = parseFloats( child.textContent );
						const matrix = new Matrix4().fromArray( array ).transpose();
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: matrix
						} );
						break;

					case 'translate':
					case 'scale':
						array = parseFloats( child.textContent );
						vector = new Vector3().fromArray( array );
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: vector
						} );
						break;

					case 'rotate':
						array = parseFloats( child.textContent );
						vector = new Vector3().fromArray( array );
						const angle = MathUtils.degToRad( array[ 3 ] );
						transforms.push( {
							sid: child.getAttribute( 'sid' ),
							type: child.nodeName,
							obj: vector,
							angle: angle
						} );
						break;

				}

			}

			return transforms;

		}

		// nodes

		function prepareNodes( xml ) {

			const elements = xml.getElementsByTagName( 'node' );

			// ensure all node elements have id attributes

			for ( let i = 0; i < elements.length; i ++ ) {

				const element = elements[ i ];

				if ( element.hasAttribute( 'id' ) === false ) {

					element.setAttribute( 'id', generateId() );

				}

			}

		}

		const matrix = new Matrix4();
		const vector = new Vector3();

		function parseNode( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ) || '',
				type: xml.getAttribute( 'type' ),
				id: xml.getAttribute( 'id' ),
				sid: xml.getAttribute( 'sid' ),
				matrix: new Matrix4(),
				nodes: [],
				instanceCameras: [],
				instanceControllers: [],
				instanceLights: [],
				instanceGeometries: [],
				instanceNodes: [],
				transforms: {}
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				if ( child.nodeType !== 1 ) continue;

				let array;

				switch ( child.nodeName ) {

					case 'node':
						data.nodes.push( child.getAttribute( 'id' ) );
						parseNode( child );
						break;

					case 'instance_camera':
						data.instanceCameras.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'instance_controller':
						data.instanceControllers.push( parseNodeInstance( child ) );
						break;

					case 'instance_light':
						data.instanceLights.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'instance_geometry':
						data.instanceGeometries.push( parseNodeInstance( child ) );
						break;

					case 'instance_node':
						data.instanceNodes.push( parseId( child.getAttribute( 'url' ) ) );
						break;

					case 'matrix':
						array = parseFloats( child.textContent );
						data.matrix.multiply( matrix.fromArray( array ).transpose() );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'translate':
						array = parseFloats( child.textContent );
						vector.fromArray( array );
						data.matrix.multiply( matrix.makeTranslation( vector.x, vector.y, vector.z ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'rotate':
						array = parseFloats( child.textContent );
						const angle = MathUtils.degToRad( array[ 3 ] );
						data.matrix.multiply( matrix.makeRotationAxis( vector.fromArray( array ), angle ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'scale':
						array = parseFloats( child.textContent );
						data.matrix.scale( vector.fromArray( array ) );
						data.transforms[ child.getAttribute( 'sid' ) ] = child.nodeName;
						break;

					case 'extra':
						break;

					default:
						console.log( child );

				}

			}

			if ( hasNode( data.id ) ) {

				console.warn( 'THREE.ColladaLoader: There is already a node with ID %s. Exclude current node from further processing.', data.id );

			} else {

				library.nodes[ data.id ] = data;

			}

			return data;

		}

		function parseNodeInstance( xml ) {

			const data = {
				id: parseId( xml.getAttribute( 'url' ) ),
				materials: {},
				skeletons: []
			};

			for ( let i = 0; i < xml.childNodes.length; i ++ ) {

				const child = xml.childNodes[ i ];

				switch ( child.nodeName ) {

					case 'bind_material':
						const instances = child.getElementsByTagName( 'instance_material' );

						for ( let j = 0; j < instances.length; j ++ ) {

							const instance = instances[ j ];
							const symbol = instance.getAttribute( 'symbol' );
							const target = instance.getAttribute( 'target' );

							data.materials[ symbol ] = parseId( target );

						}

						break;

					case 'skeleton':
						data.skeletons.push( parseId( child.textContent ) );
						break;

					default:
						break;

				}

			}

			return data;

		}

		function buildSkeleton( skeletons, joints ) {

			const boneData = [];
			const sortedBoneData = [];

			let i, j, data;

			// a skeleton can have multiple root bones. collada expresses this
			// situation with multiple "skeleton" tags per controller instance

			for ( i = 0; i < skeletons.length; i ++ ) {

				const skeleton = skeletons[ i ];

				let root;

				if ( hasNode( skeleton ) ) {

					root = getNode( skeleton );
					buildBoneHierarchy( root, joints, boneData );

				} else if ( hasVisualScene( skeleton ) ) {

					// handle case where the skeleton refers to the visual scene (#13335)

					const visualScene = library.visualScenes[ skeleton ];
					const children = visualScene.children;

					for ( let j = 0; j < children.length; j ++ ) {

						const child = children[ j ];

						if ( child.type === 'JOINT' ) {

							const root = getNode( child.id );
							buildBoneHierarchy( root, joints, boneData );

						}

					}

				} else {

					console.error( 'THREE.ColladaLoader: Unable to find root bone of skeleton with ID:', skeleton );

				}

			}

			// sort bone data (the order is defined in the corresponding controller)

			for ( i = 0; i < joints.length; i ++ ) {

				for ( j = 0; j < boneData.length; j ++ ) {

					data = boneData[ j ];

					if ( data.bone.name === joints[ i ].name ) {

						sortedBoneData[ i ] = data;
						data.processed = true;
						break;

					}

				}

			}

			// add unprocessed bone data at the end of the list

			for ( i = 0; i < boneData.length; i ++ ) {

				data = boneData[ i ];

				if ( data.processed === false ) {

					sortedBoneData.push( data );
					data.processed = true;

				}

			}

			// setup arrays for skeleton creation

			const bones = [];
			const boneInverses = [];

			for ( i = 0; i < sortedBoneData.length; i ++ ) {

				data = sortedBoneData[ i ];

				bones.push( data.bone );
				boneInverses.push( data.boneInverse );

			}

			return new Skeleton( bones, boneInverses );

		}

		function buildBoneHierarchy( root, joints, boneData ) {

			// setup bone data from visual scene

			root.traverse( function ( object ) {

				if ( object.isBone === true ) {

					let boneInverse;

					// retrieve the boneInverse from the controller data

					for ( let i = 0; i < joints.length; i ++ ) {

						const joint = joints[ i ];

						if ( joint.name === object.name ) {

							boneInverse = joint.boneInverse;
							break;

						}

					}

					if ( boneInverse === undefined ) {

						// Unfortunately, there can be joints in the visual scene that are not part of the
						// corresponding controller. In this case, we have to create a dummy boneInverse matrix
						// for the respective bone. This bone won't affect any vertices, because there are no skin indices
						// and weights defined for it. But we still have to add the bone to the sorted bone list in order to
						// ensure a correct animation of the model.

						boneInverse = new Matrix4();

					}

					boneData.push( { bone: object, boneInverse: boneInverse, processed: false } );

				}

			} );

		}

		function buildNode( data ) {

			const objects = [];

			const matrix = data.matrix;
			const nodes = data.nodes;
			const type = data.type;
			const instanceCameras = data.instanceCameras;
			const instanceControllers = data.instanceControllers;
			const instanceLights = data.instanceLights;
			const instanceGeometries = data.instanceGeometries;
			const instanceNodes = data.instanceNodes;

			// nodes

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				objects.push( getNode( nodes[ i ] ) );

			}

			// instance cameras

			for ( let i = 0, l = instanceCameras.length; i < l; i ++ ) {

				const instanceCamera = getCamera( instanceCameras[ i ] );

				if ( instanceCamera !== null ) {

					objects.push( instanceCamera.clone() );

				}

			}

			// instance controllers

			for ( let i = 0, l = instanceControllers.length; i < l; i ++ ) {

				const instance = instanceControllers[ i ];
				const controller = getController( instance.id );
				const geometries = getGeometry( controller.id );
				const newObjects = buildObjects( geometries, instance.materials );

				const skeletons = instance.skeletons;
				const joints = controller.skin.joints;

				const skeleton = buildSkeleton( skeletons, joints );

				for ( let j = 0, jl = newObjects.length; j < jl; j ++ ) {

					const object = newObjects[ j ];

					if ( object.isSkinnedMesh ) {

						object.bind( skeleton, controller.skin.bindMatrix );
						object.normalizeSkinWeights();

					}

					objects.push( object );

				}

			}

			// instance lights

			for ( let i = 0, l = instanceLights.length; i < l; i ++ ) {

				const instanceLight = getLight( instanceLights[ i ] );

				if ( instanceLight !== null ) {

					objects.push( instanceLight.clone() );

				}

			}

			// instance geometries

			for ( let i = 0, l = instanceGeometries.length; i < l; i ++ ) {

				const instance = instanceGeometries[ i ];

				// a single geometry instance in collada can lead to multiple object3Ds.
				// this is the case when primitives are combined like triangles and lines

				const geometries = getGeometry( instance.id );
				const newObjects = buildObjects( geometries, instance.materials );

				for ( let j = 0, jl = newObjects.length; j < jl; j ++ ) {

					objects.push( newObjects[ j ] );

				}

			}

			// instance nodes

			for ( let i = 0, l = instanceNodes.length; i < l; i ++ ) {

				objects.push( getNode( instanceNodes[ i ] ).clone() );

			}

			let object;

			if ( nodes.length === 0 && objects.length === 1 ) {

				object = objects[ 0 ];

			} else {

				object = ( type === 'JOINT' ) ? new Bone() : new Group();

				for ( let i = 0; i < objects.length; i ++ ) {

					object.add( objects[ i ] );

				}

			}

			object.name = ( type === 'JOINT' ) ? data.sid : data.name;
			object.matrix.copy( matrix );
			object.matrix.decompose( object.position, object.quaternion, object.scale );

			return object;

		}

		const fallbackMaterial = new MeshBasicMaterial( {
			name: Loader.DEFAULT_MATERIAL_NAME,
			color: 0xff00ff
		} );

		function resolveMaterialBinding( keys, instanceMaterials ) {

			const materials = [];

			for ( let i = 0, l = keys.length; i < l; i ++ ) {

				const id = instanceMaterials[ keys[ i ] ];

				if ( id === undefined ) {

					console.warn( 'THREE.ColladaLoader: Material with key %s not found. Apply fallback material.', keys[ i ] );
					materials.push( fallbackMaterial );

				} else {

					materials.push( getMaterial( id ) );

				}

			}

			return materials;

		}

		function buildObjects( geometries, instanceMaterials ) {

			const objects = [];

			for ( const type in geometries ) {

				const geometry = geometries[ type ];

				const materials = resolveMaterialBinding( geometry.materialKeys, instanceMaterials );

				// handle case if no materials are defined

				if ( materials.length === 0 ) {

					if ( type === 'lines' || type === 'linestrips' ) {

						materials.push( new LineBasicMaterial() );

					} else {

						materials.push( new MeshPhongMaterial() );

					}

				}

				// Collada allows to use phong and lambert materials with lines. Replacing these cases with LineBasicMaterial.

				if ( type === 'lines' || type === 'linestrips' ) {

					for ( let i = 0, l = materials.length; i < l; i ++ ) {

						const material = materials[ i ];

						if ( material.isMeshPhongMaterial === true || material.isMeshLambertMaterial === true ) {

							const lineMaterial = new LineBasicMaterial();

							// copy compatible properties

							lineMaterial.color.copy( material.color );
							lineMaterial.opacity = material.opacity;
							lineMaterial.transparent = material.transparent;

							// replace material

							materials[ i ] = lineMaterial;

						}

					}

				}

				// regard skinning

				const skinning = ( geometry.data.attributes.skinIndex !== undefined );

				// choose between a single or multi materials (material array)

				const material = ( materials.length === 1 ) ? materials[ 0 ] : materials;

				// now create a specific 3D object

				let object;

				switch ( type ) {

					case 'lines':
						object = new LineSegments( geometry.data, material );
						break;

					case 'linestrips':
						object = new Line( geometry.data, material );
						break;

					case 'triangles':
					case 'polylist':
						if ( skinning ) {

							object = new SkinnedMesh( geometry.data, material );

						} else {

							object = new Mesh( geometry.data, material );

						}

						break;

				}

				objects.push( object );

			}

			return objects;

		}

		function hasNode( id ) {

			return library.nodes[ id ] !== undefined;

		}

		function getNode( id ) {

			return getBuild( library.nodes[ id ], buildNode );

		}

		// visual scenes

		function parseVisualScene( xml ) {

			const data = {
				name: xml.getAttribute( 'name' ),
				children: []
			};

			prepareNodes( xml );

			const elements = getElementsByTagName( xml, 'node' );

			for ( let i = 0; i < elements.length; i ++ ) {

				data.children.push( parseNode( elements[ i ] ) );

			}

			library.visualScenes[ xml.getAttribute( 'id' ) ] = data;

		}

		function buildVisualScene( data ) {

			const group = new Group();
			group.name = data.name;

			const children = data.children;

			for ( let i = 0; i < children.length; i ++ ) {

				const child = children[ i ];

				group.add( getNode( child.id ) );

			}

			return group;

		}

		function hasVisualScene( id ) {

			return library.visualScenes[ id ] !== undefined;

		}

		function getVisualScene( id ) {

			return getBuild( library.visualScenes[ id ], buildVisualScene );

		}

		// scenes

		function parseScene( xml ) {

			const instance = getElementsByTagName( xml, 'instance_visual_scene' )[ 0 ];
			return getVisualScene( parseId( instance.getAttribute( 'url' ) ) );

		}

		function setupAnimations() {

			const clips = library.clips;

			if ( isEmpty( clips ) === true ) {

				if ( isEmpty( library.animations ) === false ) {

					// if there are animations but no clips, we create a default clip for playback

					const tracks = [];

					for ( const id in library.animations ) {

						const animationTracks = getAnimation( id );

						for ( let i = 0, l = animationTracks.length; i < l; i ++ ) {

							tracks.push( animationTracks[ i ] );

						}

					}

					animations.push( new AnimationClip( 'default', - 1, tracks ) );

				}

			} else {

				for ( const id in clips ) {

					animations.push( getAnimationClip( id ) );

				}

			}

		}

		// convert the parser error element into text with each child elements text
		// separated by new lines.

		function parserErrorToText( parserError ) {

			let result = '';
			const stack = [ parserError ];

			while ( stack.length ) {

				const node = stack.shift();

				if ( node.nodeType === Node.TEXT_NODE ) {

					result += node.textContent;

				} else {

					result += '\n';
					stack.push( ...node.childNodes );

				}

			}

			return result.trim();

		}

		if ( text.length === 0 ) {

			return { scene: new Scene() };

		}

		const xml = new DOMParser().parseFromString( text, 'application/xml' );

		const collada = getElementsByTagName( xml, 'COLLADA' )[ 0 ];

		const parserError = xml.getElementsByTagName( 'parsererror' )[ 0 ];
		if ( parserError !== undefined ) {

			// Chrome will return parser error with a div in it

			const errorElement = getElementsByTagName( parserError, 'div' )[ 0 ];
			let errorText;

			if ( errorElement ) {

				errorText = errorElement.textContent;

			} else {

				errorText = parserErrorToText( parserError );

			}

			console.error( 'THREE.ColladaLoader: Failed to parse collada file.\n', errorText );

			return null;

		}

		// metadata

		const version = collada.getAttribute( 'version' );
		console.debug( 'THREE.ColladaLoader: File version', version );

		const asset = parseAsset( getElementsByTagName( collada, 'asset' )[ 0 ] );
		const textureLoader = new TextureLoader( this.manager );
		textureLoader.setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		let tgaLoader;

		if ( TGALoader ) {

			tgaLoader = new TGALoader( this.manager );
			tgaLoader.setPath( this.resourcePath || path );

		}

		//

		const tempColor = new Color();
		const animations = [];
		let kinematics = {};
		let count = 0;

		//

		const library = {
			animations: {},
			clips: {},
			controllers: {},
			images: {},
			effects: {},
			materials: {},
			cameras: {},
			lights: {},
			geometries: {},
			nodes: {},
			visualScenes: {},
			kinematicsModels: {},
			physicsModels: {},
			kinematicsScenes: {}
		};

		parseLibrary( collada, 'library_animations', 'animation', parseAnimation );
		parseLibrary( collada, 'library_animation_clips', 'animation_clip', parseAnimationClip );
		parseLibrary( collada, 'library_controllers', 'controller', parseController );
		parseLibrary( collada, 'library_images', 'image', parseImage );
		parseLibrary( collada, 'library_effects', 'effect', parseEffect );
		parseLibrary( collada, 'library_materials', 'material', parseMaterial );
		parseLibrary( collada, 'library_cameras', 'camera', parseCamera );
		parseLibrary( collada, 'library_lights', 'light', parseLight );
		parseLibrary( collada, 'library_geometries', 'geometry', parseGeometry );
		parseLibrary( collada, 'library_nodes', 'node', parseNode );
		parseLibrary( collada, 'library_visual_scenes', 'visual_scene', parseVisualScene );
		parseLibrary( collada, 'library_kinematics_models', 'kinematics_model', parseKinematicsModel );
		parseLibrary( collada, 'library_physics_models', 'physics_model', parsePhysicsModel );
		parseLibrary( collada, 'scene', 'instance_kinematics_scene', parseKinematicsScene );

		buildLibrary( library.animations, buildAnimation );
		buildLibrary( library.clips, buildAnimationClip );
		buildLibrary( library.controllers, buildController );
		buildLibrary( library.images, buildImage );
		buildLibrary( library.effects, buildEffect );
		buildLibrary( library.materials, buildMaterial );
		buildLibrary( library.cameras, buildCamera );
		buildLibrary( library.lights, buildLight );
		buildLibrary( library.geometries, buildGeometry );
		buildLibrary( library.visualScenes, buildVisualScene );

		setupAnimations();
		setupKinematics();

		const scene = parseScene( getElementsByTagName( collada, 'scene' )[ 0 ] );
		scene.animations = animations;

		if ( asset.upAxis === 'Z_UP' ) {

			console.warn( 'THREE.ColladaLoader: You are loading an asset with a Z-UP coordinate system. The loader just rotates the asset to transform it into Y-UP. The vertex data are not converted, see #24289.' );
			scene.rotation.set( - Math.PI / 2, 0, 0 );

		}

		scene.scale.multiplyScalar( asset.unit );

		return {
			get animations() {

				console.warn( 'THREE.ColladaLoader: Please access animations over scene.animations now.' );
				return animations;

			},
			kinematics: kinematics,
			library: library,
			scene: scene
		};

	}
```
</details>


---