[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `VRMLLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 97 |
| 🧱 Classes | 5 |
| 📦 Imports | 35 |
| 📊 Variables & Constants | 368 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/VRMLLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BackSide` | `three` |
| `BoxGeometry` | `three` |
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `ClampToEdgeWrapping` | `three` |
| `Color` | `three` |
| `ColorManagement` | `three` |
| `ConeGeometry` | `three` |
| `CylinderGeometry` | `three` |
| `DataTexture` | `three` |
| `DoubleSide` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `FrontSide` | `three` |
| `Group` | `three` |
| `LineBasicMaterial` | `three` |
| `LineSegments` | `three` |
| `Loader` | `three` |
| `LoaderUtils` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `MeshPhongMaterial` | `three` |
| `Object3D` | `three` |
| `Points` | `three` |
| `PointsMaterial` | `three` |
| `Quaternion` | `three` |
| `RepeatWrapping` | `three` |
| `Scene` | `three` |
| `ShapeUtils` | `three` |
| `SphereGeometry` | `three` |
| `SRGBColorSpace` | `three` |
| `TextureLoader` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |
| `chevrotain` | `../libs/chevrotain.module.min.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `path` | `any` | let/var | `( scope.path === '' ) ? LoaderUtils.extractUrlBase( url ) : scope.path` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `nodeMap` | `{}` | let/var | `{}` | ✗ |
| `lexer` | `VRMLLexer` | let/var | `new VRMLLexer( tokenData.tokens )` | ✗ |
| `parser` | `VRMLParser` | let/var | `new VRMLParser( tokenData.tokenVocabulary )` | ✗ |
| `createToken` | `any` | let/var | `chevrotain.createToken` | ✗ |
| `nodeTypes` | `string[]` | let/var | `[ 'Anchor', 'Billboard', 'Collision', 'Group', 'Transform', // grouping nodes...` | ✗ |
| `tokens` | `any[]` | let/var | `[ WhiteSpace, // keywords appear before the Identifier NodeName, DEF, USE, RO...` | ✗ |
| `tokenVocabulary` | `{}` | let/var | `{}` | ✗ |
| `token` | `any` | let/var | `tokens[ i ]` | ✗ |
| `data` | `{ version: any; nodes: any[]; routes:...` | let/var | `{ version: this.visit( ctx.version ), nodes: [], routes: [] }` | ✗ |
| `node` | `any` | let/var | `ctx.node[ i ]` | ✗ |
| `route` | `any` | let/var | `ctx.route[ i ]` | ✗ |
| `data` | `{ name: any; fields: any[]; }` | let/var | `{ name: ctx.NodeName[ 0 ].image, fields: [] }` | ✗ |
| `field` | `any` | let/var | `ctx.field[ i ]` | ✗ |
| `data` | `{ name: any; type: any; values: any; }` | let/var | `{ name: ctx.Identifier[ 0 ].image, type: null, values: null }` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `{ FROM: any; TO: any; }` | let/var | `{ FROM: ctx.RouteIdentifier[ 0 ].image, TO: ctx.RouteIdentifier[ 1 ].image }` | ✗ |
| `field` | `{ type: any; values: any[]; }` | let/var | `{ type: null, values: [] }` | ✗ |
| `node` | `any` | let/var | `ctx.node[ i ]` | ✗ |
| `use` | `any` | let/var | `ctx.use[ i ]` | ✗ |
| `stringLiteral` | `any` | let/var | `ctx.StringLiteral[ i ]` | ✗ |
| `numberLiteral` | `any` | let/var | `ctx.NumberLiteral[ i ]` | ✗ |
| `hexLiteral` | `any` | let/var | `ctx.HexLiteral[ i ]` | ✗ |
| `trueLiteral` | `any` | let/var | `ctx.TrueLiteral[ i ]` | ✗ |
| `falseLiteral` | `any` | let/var | `ctx.FalseLiteral[ i ]` | ✗ |
| `nodes` | `any` | let/var | `tree.nodes` | ✗ |
| `scene` | `any` | let/var | `new Scene()` | ✗ |
| `node` | `any` | let/var | `nodes[ i ]` | ✗ |
| `node` | `any` | let/var | `nodes[ i ]` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `nodeName` | `any` | let/var | `node.name` | ✗ |
| `build` | `any` | let/var | `*not shown*` | ✗ |
| `object` | `any` | let/var | `new Group()` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `angle` | `any` | let/var | `fieldValues[ 3 ]` | ✗ |
| `group` | `any` | let/var | `new Group()` | ✗ |
| `groundAngle` | `any` | let/var | `*not shown*` | ✗ |
| `groundColor` | `any` | let/var | `*not shown*` | ✗ |
| `skyAngle` | `any` | let/var | `*not shown*` | ✗ |
| `skyColor` | `any` | let/var | `*not shown*` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `radius` | `10000` | let/var | `10000` | ✗ |
| `skyGeometry` | `any` | let/var | `new SphereGeometry( radius, 32, 16 )` | ✗ |
| `skyMaterial` | `any` | let/var | `new MeshBasicMaterial( { fog: false, side: BackSide, depthWrite: false, depth...` | ✗ |
| `sky` | `any` | let/var | `new Mesh( skyGeometry, skyMaterial )` | ✗ |
| `groundGeometry` | `any` | let/var | `new SphereGeometry( radius, 32, 16, 0, 2 * Math.PI, 0.5 * Math.PI, 1.5 * Math...` | ✗ |
| `groundMaterial` | `any` | let/var | `new MeshBasicMaterial( { fog: false, side: BackSide, vertexColors: true, dept...` | ✗ |
| `ground` | `any` | let/var | `new Mesh( groundGeometry, groundMaterial )` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `material` | `any` | let/var | `new MeshBasicMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, color: 0x000000 } )` | ✗ |
| `geometry` | `any` | let/var | `*not shown*` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `object` | `any` | let/var | `*not shown*` | ✗ |
| `type` | `any` | let/var | `geometry._type` | ✗ |
| `pointsMaterial` | `any` | let/var | `new PointsMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, color: 0xffffff, op...` | ✗ |
| `lineMaterial` | `any` | let/var | `new LineBasicMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, color: 0xffffff,...` | ✗ |
| `material` | `any` | let/var | `new MeshPhongMaterial()` | ✗ |
| `transformData` | `any` | let/var | `*not shown*` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `textureNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `materialData` | `{ diffuseColor: any; emissiveColor: a...` | let/var | `{}` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `texture` | `any` | let/var | `*not shown*` | ✗ |
| `wrapS` | `any` | let/var | `RepeatWrapping` | ✗ |
| `wrapT` | `any` | let/var | `RepeatWrapping` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `width` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `height` | `any` | let/var | `fieldValues[ 1 ]` | ✗ |
| `num_components` | `any` | let/var | `fieldValues[ 2 ]` | ✗ |
| `data` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( 4 * width * height )` | ✗ |
| `color` | `{ r: number; g: number; b: number; a:...` | let/var | `{ r: 0, g: 0, b: 0, a: 0 }` | ✗ |
| `stride` | `number` | let/var | `k * 4` | ✗ |
| `texture` | `any` | let/var | `*not shown*` | ✗ |
| `wrapS` | `any` | let/var | `RepeatWrapping` | ✗ |
| `wrapT` | `any` | let/var | `RepeatWrapping` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `url` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `transformData` | `{ center: any; rotation: any; scale: ...` | let/var | `{ center: new Vector2(), rotation: new Vector2(), scale: new Vector2(), trans...` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `worldInfo` | `{ title: any; info: any; }` | let/var | `{}` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `coord` | `any` | let/var | `*not shown*` | ✗ |
| `normal` | `any` | let/var | `*not shown*` | ✗ |
| `texCoord` | `any` | let/var | `*not shown*` | ✗ |
| `ccw` | `boolean` | let/var | `true` | ✗ |
| `solid` | `boolean` | let/var | `true` | ✗ |
| `creaseAngle` | `number` | let/var | `0` | ✗ |
| `colorIndex` | `any` | let/var | `*not shown*` | ✗ |
| `coordIndex` | `any` | let/var | `*not shown*` | ✗ |
| `normalIndex` | `any` | let/var | `*not shown*` | ✗ |
| `texCoordIndex` | `any` | let/var | `*not shown*` | ✗ |
| `colorPerVertex` | `boolean` | let/var | `true` | ✗ |
| `normalPerVertex` | `boolean` | let/var | `true` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `colorNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `coordNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `normalNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `texCoordNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `colorAttribute` | `any` | let/var | `*not shown*` | ✗ |
| `normalAttribute` | `any` | let/var | `*not shown*` | ✗ |
| `uvAttribute` | `any` | let/var | `*not shown*` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `coord` | `any` | let/var | `*not shown*` | ✗ |
| `colorIndex` | `any` | let/var | `*not shown*` | ✗ |
| `coordIndex` | `any` | let/var | `*not shown*` | ✗ |
| `colorPerVertex` | `boolean` | let/var | `true` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `colorNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `coordNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `colorAttribute` | `any` | let/var | `*not shown*` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `coord` | `any` | let/var | `*not shown*` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `colorNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `coordNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `colorAttribute` | `any` | let/var | `new Float32BufferAttribute( color, 3 )` | ✗ |
| `size` | `any` | let/var | `new Vector3( 2, 2, 2 )` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `geometry` | `any` | let/var | `new BoxGeometry( size.x, size.y, size.z )` | ✗ |
| `radius` | `number` | let/var | `1` | ✗ |
| `height` | `number` | let/var | `2` | ✗ |
| `openEnded` | `boolean` | let/var | `false` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `geometry` | `any` | let/var | `new ConeGeometry( radius, height, 16, 1, openEnded )` | ✗ |
| `radius` | `number` | let/var | `1` | ✗ |
| `height` | `number` | let/var | `2` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `geometry` | `any` | let/var | `new CylinderGeometry( radius, radius, height, 16, 1 )` | ✗ |
| `radius` | `number` | let/var | `1` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `geometry` | `any` | let/var | `new SphereGeometry( radius, 16, 16 )` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `normal` | `any` | let/var | `*not shown*` | ✗ |
| `texCoord` | `any` | let/var | `*not shown*` | ✗ |
| `height` | `any` | let/var | `*not shown*` | ✗ |
| `colorPerVertex` | `boolean` | let/var | `true` | ✗ |
| `normalPerVertex` | `boolean` | let/var | `true` | ✗ |
| `solid` | `boolean` | let/var | `true` | ✗ |
| `ccw` | `boolean` | let/var | `true` | ✗ |
| `creaseAngle` | `number` | let/var | `0` | ✗ |
| `xDimension` | `number` | let/var | `2` | ✗ |
| `zDimension` | `number` | let/var | `2` | ✗ |
| `xSpacing` | `number` | let/var | `1` | ✗ |
| `zSpacing` | `number` | let/var | `1` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `colorNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `normalNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `texCoordNode` | `any` | let/var | `fieldValues[ 0 ]` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `colors` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `index` | `number` | let/var | `( i * xDimension ) + j` | ✗ |
| `x` | `number` | let/var | `xSpacing * i` | ✗ |
| `y` | `any` | let/var | `height[ index ]` | ✗ |
| `z` | `number` | let/var | `zSpacing * j` | ✗ |
| `r` | `any` | let/var | `color[ index * 3 + 0 ]` | ✗ |
| `g` | `any` | let/var | `color[ index * 3 + 1 ]` | ✗ |
| `b` | `any` | let/var | `color[ index * 3 + 2 ]` | ✗ |
| `xn` | `any` | let/var | `normal[ index * 3 + 0 ]` | ✗ |
| `yn` | `any` | let/var | `normal[ index * 3 + 1 ]` | ✗ |
| `zn` | `any` | let/var | `normal[ index * 3 + 2 ]` | ✗ |
| `s` | `any` | let/var | `texCoord[ index * 2 + 0 ]` | ✗ |
| `t` | `any` | let/var | `texCoord[ index * 2 + 1 ]` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `a` | `number` | let/var | `i + j * xDimension` | ✗ |
| `b` | `number` | let/var | `i + ( j + 1 ) * xDimension` | ✗ |
| `c` | `number` | let/var | `( i + 1 ) + ( j + 1 ) * xDimension` | ✗ |
| `d` | `number` | let/var | `( i + 1 ) + j * xDimension` | ✗ |
| `colorAttribute` | `any` | let/var | `*not shown*` | ✗ |
| `normalAttribute` | `any` | let/var | `*not shown*` | ✗ |
| `index` | `number` | let/var | `i + j * ( xDimension - 1 )` | ✗ |
| `r` | `any` | let/var | `color[ index * 3 + 0 ]` | ✗ |
| `g` | `any` | let/var | `color[ index * 3 + 1 ]` | ✗ |
| `b` | `any` | let/var | `color[ index * 3 + 2 ]` | ✗ |
| `index` | `number` | let/var | `i + j * ( xDimension - 1 )` | ✗ |
| `xn` | `any` | let/var | `normal[ index * 3 + 0 ]` | ✗ |
| `yn` | `any` | let/var | `normal[ index * 3 + 1 ]` | ✗ |
| `zn` | `any` | let/var | `normal[ index * 3 + 2 ]` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `crossSection` | `number[]` | let/var | `[ 1, 1, 1, - 1, - 1, - 1, - 1, 1, 1, 1 ]` | ✗ |
| `spine` | `number[]` | let/var | `[ 0, 0, 0, 0, 1, 0 ]` | ✗ |
| `scale` | `any` | let/var | `*not shown*` | ✗ |
| `orientation` | `any` | let/var | `*not shown*` | ✗ |
| `beginCap` | `boolean` | let/var | `true` | ✗ |
| `ccw` | `boolean` | let/var | `true` | ✗ |
| `creaseAngle` | `number` | let/var | `0` | ✗ |
| `endCap` | `boolean` | let/var | `true` | ✗ |
| `solid` | `boolean` | let/var | `true` | ✗ |
| `fields` | `any` | let/var | `node.fields` | ✗ |
| `field` | `any` | let/var | `fields[ i ]` | ✗ |
| `fieldName` | `any` | let/var | `field.name` | ✗ |
| `fieldValues` | `any` | let/var | `field.values` | ✗ |
| `crossSectionClosed` | `boolean` | let/var | `( crossSection[ 0 ] === crossSection[ crossSection.length - 2 ] && crossSecti...` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `spineVector` | `any` | let/var | `new Vector3()` | ✗ |
| `scaling` | `any` | let/var | `new Vector3()` | ✗ |
| `axis` | `any` | let/var | `new Vector3()` | ✗ |
| `vertex` | `any` | let/var | `new Vector3()` | ✗ |
| `quaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `angle` | `any` | let/var | `orientation ? orientation[ o + 3 ] : 0` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `spineCount` | `number` | let/var | `spine.length / 3` | ✗ |
| `crossSectionCount` | `number` | let/var | `crossSection.length / 2` | ✗ |
| `a` | `number` | let/var | `j + i * crossSectionCount` | ✗ |
| `b` | `number` | let/var | `( j + 1 ) + i * crossSectionCount` | ✗ |
| `c` | `number` | let/var | `j + ( i + 1 ) * crossSectionCount` | ✗ |
| `d` | `number` | let/var | `( j + 1 ) + ( i + 1 ) * crossSectionCount` | ✗ |
| `contour` | `any[]` | let/var | `[]` | ✗ |
| `capIndices` | `any[]` | let/var | `[]` | ✗ |
| `face` | `any` | let/var | `faces[ i ]` | ✗ |
| `indexOffset` | `number` | let/var | `crossSectionCount * ( spineCount - 1 )` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `node` | `any` | let/var | `nodeMap[ identifier ]` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `start` | `number` | let/var | `0` | ✗ |
| `i1` | `any` | let/var | `index[ start ]` | ✗ |
| `i2` | `any` | let/var | `index[ i + ( ccw ? 1 : 2 ) ]` | ✗ |
| `i3` | `any` | let/var | `index[ i + ( ccw ? 2 : 1 ) ]` | ✗ |
| `triangulatedData` | `any[]` | let/var | `[]` | ✗ |
| `start` | `number` | let/var | `0` | ✗ |
| `stride` | `number` | let/var | `start * 3` | ✗ |
| `x` | `any` | let/var | `data[ stride ]` | ✗ |
| `y` | `any` | let/var | `data[ stride + 1 ]` | ✗ |
| `z` | `any` | let/var | `data[ stride + 2 ]` | ✗ |
| `flattenData` | `any[]` | let/var | `[]` | ✗ |
| `i1` | `any` | let/var | `index[ i ]` | ✗ |
| `stride` | `number` | let/var | `i1 * 3` | ✗ |
| `x` | `any` | let/var | `data[ stride ]` | ✗ |
| `y` | `any` | let/var | `data[ stride + 1 ]` | ✗ |
| `z` | `any` | let/var | `data[ stride + 2 ]` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `i1` | `any` | let/var | `index[ i ]` | ✗ |
| `i2` | `any` | let/var | `index[ i + 1 ]` | ✗ |
| `triangulatedData` | `any[]` | let/var | `[]` | ✗ |
| `start` | `number` | let/var | `0` | ✗ |
| `stride` | `number` | let/var | `start * 3` | ✗ |
| `x` | `any` | let/var | `data[ stride ]` | ✗ |
| `y` | `any` | let/var | `data[ stride + 1 ]` | ✗ |
| `z` | `any` | let/var | `data[ stride + 2 ]` | ✗ |
| `vA` | `any` | let/var | `new Vector3()` | ✗ |
| `vB` | `any` | let/var | `new Vector3()` | ✗ |
| `vC` | `any` | let/var | `new Vector3()` | ✗ |
| `uvA` | `any` | let/var | `new Vector2()` | ✗ |
| `uvB` | `any` | let/var | `new Vector2()` | ✗ |
| `uvC` | `any` | let/var | `new Vector2()` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `a` | `any` | let/var | `index[ i ]` | ✗ |
| `b` | `any` | let/var | `index[ i + 1 ]` | ✗ |
| `c` | `any` | let/var | `index[ i + 2 ]` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `array` | `any` | let/var | `attribute.array` | ✗ |
| `itemSize` | `any` | let/var | `attribute.itemSize` | ✗ |
| `array2` | `any` | let/var | `new array.constructor( indices.length * itemSize )` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `index2` | `number` | let/var | `0` | ✗ |
| `ab` | `any` | let/var | `new Vector3()` | ✗ |
| `cb` | `any` | let/var | `new Vector3()` | ✗ |
| `faces` | `any[]` | let/var | `[]` | ✗ |
| `vertexNormals` | `{}` | let/var | `{}` | ✗ |
| `a` | `any` | let/var | `index[ i ]` | ✗ |
| `b` | `any` | let/var | `index[ i + 1 ]` | ✗ |
| `c` | `any` | let/var | `index[ i + 2 ]` | ✗ |
| `face` | `Face` | let/var | `new Face( a, b, c )` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `face` | `Face` | let/var | `faces[ i ]` | ✗ |
| `normal` | `any` | let/var | `new Vector3()` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `thresholds` | `any[]` | let/var | `[]` | ✗ |
| `startAngle` | `number` | let/var | `( topDown === true ) ? 0 : Math.PI` | ✗ |
| `angle` | `any` | let/var | `( i === 0 ) ? 0 : angles[ i - 1 ]` | ✗ |
| `point` | `any` | let/var | `new Vector3()` | ✗ |
| `indices` | `any` | let/var | `geometry.index` | ✗ |
| `positionAttribute` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `colorAttribute` | `any` | let/var | `new BufferAttribute( new Float32Array( geometry.attributes.position.count * 3...` | ✗ |
| `position` | `any` | let/var | `new Vector3()` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `thresholdIndexA` | `any` | let/var | `*not shown*` | ✗ |
| `thresholdIndexB` | `any` | let/var | `*not shown*` | ✗ |
| `t` | `number` | let/var | `1` | ✗ |
| `thresholdA` | `any` | let/var | `thresholds[ thresholdIndexA ]` | ✗ |
| `thresholdB` | `any` | let/var | `thresholds[ thresholdIndexB ]` | ✗ |
| `colorA` | `any` | let/var | `colors[ thresholdIndexA ]` | ✗ |
| `colorB` | `any` | let/var | `colors[ thresholdIndexB ]` | ✗ |
| `textureLoader` | `any` | let/var | `new TextureLoader( this.manager )` | ✗ |
| `CstParser` | `any` | let/var | `chevrotain.CstParser` | ✗ |
| `$` | `this` | let/var | `this` | ✗ |
| `Version` | `any` | let/var | `tokenVocabulary[ 'Version' ]` | ✗ |
| `LCurly` | `any` | let/var | `tokenVocabulary[ 'LCurly' ]` | ✗ |
| `RCurly` | `any` | let/var | `tokenVocabulary[ 'RCurly' ]` | ✗ |
| `LSquare` | `any` | let/var | `tokenVocabulary[ 'LSquare' ]` | ✗ |
| `RSquare` | `any` | let/var | `tokenVocabulary[ 'RSquare' ]` | ✗ |
| `Identifier` | `any` | let/var | `tokenVocabulary[ 'Identifier' ]` | ✗ |
| `RouteIdentifier` | `any` | let/var | `tokenVocabulary[ 'RouteIdentifier' ]` | ✗ |
| `StringLiteral` | `any` | let/var | `tokenVocabulary[ 'StringLiteral' ]` | ✗ |
| `HexLiteral` | `any` | let/var | `tokenVocabulary[ 'HexLiteral' ]` | ✗ |
| `NumberLiteral` | `any` | let/var | `tokenVocabulary[ 'NumberLiteral' ]` | ✗ |
| `TrueLiteral` | `any` | let/var | `tokenVocabulary[ 'TrueLiteral' ]` | ✗ |
| `FalseLiteral` | `any` | let/var | `tokenVocabulary[ 'FalseLiteral' ]` | ✗ |
| `NullLiteral` | `any` | let/var | `tokenVocabulary[ 'NullLiteral' ]` | ✗ |
| `DEF` | `any` | let/var | `tokenVocabulary[ 'DEF' ]` | ✗ |
| `USE` | `any` | let/var | `tokenVocabulary[ 'USE' ]` | ✗ |
| `ROUTE` | `any` | let/var | `tokenVocabulary[ 'ROUTE' ]` | ✗ |
| `TO` | `any` | let/var | `tokenVocabulary[ 'TO' ]` | ✗ |
| `NodeName` | `any` | let/var | `tokenVocabulary[ 'NodeName' ]` | ✗ |
| `TEXTURE_TYPE` | `{ INTENSITY: number; INTENSITY_ALPHA:...` | let/var | `{ INTENSITY: 1, INTENSITY_ALPHA: 2, RGB: 3, RGBA: 4 }` | ✗ |


---

## Functions

### `VRMLLoader.load(url: string, onLoad: (arg0: Scene) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded VRML asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Scene)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Scene) => any`
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

### `VRMLLoader.parse(data: string, path: string): Scene`

**JSDoc:**
```typescript
/**
	 * Parses the given VRML data and returns the resulting scene.
	 *
	 * @param {string} data - The raw VRML data as a string.
	 * @param {string} path - The URL base path.
	 * @return {Scene} The parsed scene.
	 */
```

**Parameters:**

- **`data`** `string`
- **`path`** `string`

**Returns:** `Scene`

**Calls:**

- `createTokens`
- `createVisitor`
- `parser.getBaseCstVisitorConstructor`
- `lexer.lex`
- `parser.vrml`
- `console.error`
- `Error`
- `visitor.visit`
- `createToken`
- `nodeTypes.join`
- `complex_call_7846`
- `this.validateVisitor`
- `this.visit`
- `data.nodes.push`
- `data.routes.push`
- `data.fields.push`
- `processField`
- `field.values.push`
- `scope.visit`
- `stringLiteral.image.replace`
- `parseFloat`
- `ctx.NullLiteral.forEach`
- `buildNodeMap`
- `getNode`
- `scene.add`
- `resolveUSE`
- `buildNode`
- `buildGroupingNode`
- `buildBackgroundNode`
- `buildShapeNode`
- `buildAppearanceNode`
- `buildMaterialNode`
- `buildImageTextureNode`
- `buildPixelTextureNode`
- `buildTextureTransformNode`
- `buildIndexedFaceSetNode`
- `buildIndexedLineSetNode`
- `buildPointSetNode`
- `buildBoxNode`
- `buildConeNode`
- `buildCylinderNode`
- `buildSphereNode`
- `buildElevationGridNode`
- `buildExtrusionNode`
- `buildGeometricNode`
- `buildWorldInfoNode`
- `console.warn`
- `build.hasOwnProperty`
- `parseFieldChildren`
- `new Vector3( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] ).normalize`
- `object.quaternion.setFromAxisAngle`
- `object.scale.set`
- `object.position.set`
- `paintFaces`
- `toColorArray`
- `skyMaterial.color.setRGB`
- `group.add`
- `pointsMaterial.color.copy`
- `lineMaterial.color.copy`
- `material.color.copy`
- `material.emissive.copy`
- `material.specular.copy`
- `material.color.set`
- `material.map.center.copy`
- `material.map.repeat.copy`
- `material.map.offset.copy`
- `new Color().setRGB`
- `parseInt`
- `hex.substring`
- `getTextureType`
- `parseHexColor`
- `textureLoader.load`
- `transformData.center.set`
- `transformData.scale.set`
- `transformData.translation.set`
- `triangulateFaceIndex`
- `computeAttributeFromIndexedData`
- `toNonIndexedAttribute`
- `flattenData`
- `triangulateFaceData`
- `computeAttributeFromFaceData`
- `convertColorsToLinearSRGB`
- `computeNormalAttribute`
- `geometry.setAttribute`
- `expandLineIndex`
- `expandLineData`
- `computeAttributeFromLineData`
- `vertices.push`
- `colors.push`
- `normals.push`
- `uvs.push`
- `indices.push`
- `spineVector.fromArray`
- `vertex.multiply`
- `quaternion.setFromAxisAngle`
- `vertex.applyQuaternion`
- `vertex.add`
- `contour.push`
- `ShapeUtils.triangulateShape`
- `capIndices.push`
- `build.clone`
- `owner.add`
- `triangulatedData.push`
- `flattenData.push`
- `uvA.fromArray`
- `uvB.fromArray`
- `uvC.fromArray`
- `array.push`
- `vA.fromArray`
- `vB.fromArray`
- `vC.fromArray`
- `cb.subVectors`
- `ab.subVectors`
- `cb.cross`
- `cb.normalize`
- `face.normal.copy`
- `vertexNormals[ a ].push`
- `vertexNormals[ b ].push`
- `vertexNormals[ c ].push`
- `faces.push`
- `weightedNormal`
- `normal.copy`
- `normals[ i ].angleTo`
- `normal.add`
- `normal.normalize`
- `color.fromBufferAttribute`
- `ColorManagement.colorSpaceToWorking`
- `attribute.setXYZ`
- `point.setFromSphericalCoords`
- `thresholds.push`
- `indices.getX`
- `position.fromBufferAttribute`
- `Math.abs`
- `color.copy( colorA ).lerp`
- `colorAttribute.setXYZ`
- `textureLoader.setPath( this.resourcePath || path ).setCrossOrigin`
- `data.indexOf`
- `generateVRMLTree`
- `parseTree`

**Internal Comments:**
```
// create lexer, parser and visitor (x2)
// lexing (x2)
// parsing (x2)
// actions (x2)
// from http://gun.teipir.gr/VRML-amgem/spec/part1/concepts.html#SyntaxBasics (x2)
// from http://gun.teipir.gr/VRML-amgem/spec/part1/nodesRef.html (x2)
// (x12)
// commas, blanks, tabs, newlines and carriage returns are whitespace characters wherever they appear outside of string fields (x2)
// keywords appear before the Identifier
// the Identifier must appear after the keywords because all keywords are valid identifiers
// the visitor is created dynamically based on the given base class
// DEF
// SFValue
// MFValue
// console.log( JSON.stringify( tree, null, 2 ) ); (x2)
// first iteration: build nodemap based on DEF statements
// second iteration: build nodes
// handle case where a node refers to a different one
// node builder
// node not supported yet
// field not supported (x22)
// sky
// ground
// render background group first (x4)
// if the appearance field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0) (x2)
// build 3D object (x2)
// if the color field is NULL and there is a material defined for the appearance affecting this PointSet, then use the emissiveColor of the material to draw the points
// if the color field is NULL and there is a material defined for the appearance affecting this IndexedLineSet, then use the emissiveColor of the material to draw the lines
// check "solid" hint (it's placed in the geometry but affects the material)
// check for vertex colors
// if the geometry field is NULL or no vertices are defined the object is not drawn (x4)
// if the material field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0) (x3)
// only apply texture transform data if a texture was defined
// respect VRML lighting model
// apply texture transform
// Intensity texture: A one-component image specifies one-byte hexadecimal or integer values representing the intensity of the image (x3)
// Intensity+Alpha texture: A two-component image specifies the intensity in the first (high) byte and the alpha opacity in the second (low) byte. (x3)
// RGB texture: Pixels in a three-component image specify the red component in the first (high) byte, followed by the green and blue components (x4)
// RGBA texture: Four-component images specify the alpha opacity byte after red/green/blue (x4)
// if the colorIndex field is not empty, then it is used to choose colors for each vertex of the IndexedFaceSet. (x2)
// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node (x5)
// if the colorIndex field is not empty, then they are used to choose one color for each face of the IndexedFaceSet (x2)
// if the colorIndex field is empty, then the color are applied to each face of the IndexedFaceSet in order (x2)
// consider vertex normals
// if the normalIndex field is not empty, then it is used to choose normals for each vertex of the IndexedFaceSet. (x2)
// if the normalIndex field is empty, then the coordIndex field is used to choose normals from the Normal node (x3)
// consider face normals
// if the normalIndex field is not empty, then they are used to choose one normal for each face of the IndexedFaceSet (x2)
// if the normalIndex field is empty, then the normals are applied to each face of the IndexedFaceSet in order (x2)
// if the normal field is NULL, then the loader should automatically generate normals, using creaseAngle to determine if and how normals are smoothed across shared vertices (x3)
// texture coordinates are always defined on vertex level
// if the texCoordIndex field is not empty, then it is used to choose texture coordinates for each vertex of the IndexedFaceSet. (x2)
// if the texCoordIndex field is empty, then the coordIndex array is used to choose texture coordinates from the TextureCoordinate node (x3)
// optional attributes
// "solid" influences the material so let's store it for later use (x12)
// build lines (x2)
// if the colorIndex field is not empty, then one color is used for each polyline of the IndexedLineSet. (x2)
// if the colorIndex field is empty, then the colors are applied to each polyline of the IndexedLineSet in order. (x3)
// if the colorIndex field is not empty, then colors are applied to each vertex of the IndexedLineSet (x2)
// vertex data (x2)
// compute a row major index (x2)
// vertices (x4)
// colors
// normals
// uvs
// indices (x4)
// from https://tecfa.unige.ch/guides/vrml/vrml97/spec/part1/nodesRef.html#ElevationGrid (x2)
// faces
// color attribute
// one color per quad (x4)
// normal attribute
// one normal per quad (x4)
// build geometry (x2)
// scale (x4)
// rotate (x4)
// translate (x4)
// triangulate cap
// begin cap
// end cap
// no uvs yet (x4)
// helper functions
// because the same 3D objects can have different transformations, it's necessary to clone them.
// materials can be influenced by the geometry (e.g. vertex normals). cloning is necessary to avoid
// any side effects
// since face definitions can have more than three vertices, it's necessary to (x2)
// perform a simple triangulation (x2)
// an index of -1 indicates that the current face has ended and the next one begins (x2)
// an index of -1 indicates that the current line has ended and the next one begins (x2)
// we use the coordIndex.length as delimiter since normalIndex must contain at least as many indices
// prepare face and raw vertex normals
// compute vertex normals and build final geometry (x2)
/**
		 * Vertically paints the faces interpolating between the
		 * specified colors at the specified angels. This is used for the Background
		 * node, but could be applied to other nodes with multiple faces as well.
		 *
		 * When used with the Background node, default is directionIsDown is true if
		 * interpolating the skyColor down from the Zenith. When interpolating up from
		 * the Nadir i.e. interpolating the groundColor, the directionIsDown is false.
		 *
		 * The first angle is never specified, it is the Zenith (0 rad). Angles are specified
		 * in radians. The geometry is thought a sphere, but could be anything. The color interpolation
		 * is linear along the Y axis in any case.
		 *
		 * You must specify one more color than you have angles at the beginning of the colors array.
		 * This is the color of the Zenith (the top of the shape).
		 *
		 * @param {BufferGeometry} geometry
		 * @param {number} radius
		 * @param {array} angles
		 * @param {array} colors
		 * @param {boolean} topDown - Whether to work top down or bottom up.
		 */
// compute threshold values (x2)
// generate vertex colors (x2)
// interpolation for sky color
// interpolation for ground color
// check version (only 2.0 is supported)
// create JSON representing the tree structure of the VRML asset (x2)
// parse the tree structure to a three.js scene (x2)
```

<details><summary>Code</summary>

```typescript
parse( data, path ) {

		const nodeMap = {};

		function generateVRMLTree( data ) {

			// create lexer, parser and visitor

			const tokenData = createTokens();

			const lexer = new VRMLLexer( tokenData.tokens );
			const parser = new VRMLParser( tokenData.tokenVocabulary );
			const visitor = createVisitor( parser.getBaseCstVisitorConstructor() );

			// lexing

			const lexingResult = lexer.lex( data );
			parser.input = lexingResult.tokens;

			// parsing

			const cstOutput = parser.vrml();

			if ( parser.errors.length > 0 ) {

				console.error( parser.errors );

				throw Error( 'THREE.VRMLLoader: Parsing errors detected.' );

			}

			// actions

			const ast = visitor.visit( cstOutput );

			return ast;

		}

		function createTokens() {

			const createToken = chevrotain.createToken;

			// from http://gun.teipir.gr/VRML-amgem/spec/part1/concepts.html#SyntaxBasics

			const RouteIdentifier = createToken( { name: 'RouteIdentifier', pattern: /[^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d][^\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]*[\.][^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d][^\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]*/ } );
			const Identifier = createToken( { name: 'Identifier', pattern: /[^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]([^\0-\x20\x22\x27\x23\x2b\x2c\x2e\x5b\x5d\x5c\x7b\x7d])*/, longer_alt: RouteIdentifier } );

			// from http://gun.teipir.gr/VRML-amgem/spec/part1/nodesRef.html

			const nodeTypes = [
				'Anchor', 'Billboard', 'Collision', 'Group', 'Transform', // grouping nodes
				'Inline', 'LOD', 'Switch', // special groups
				'AudioClip', 'DirectionalLight', 'PointLight', 'Script', 'Shape', 'Sound', 'SpotLight', 'WorldInfo', // common nodes
				'CylinderSensor', 'PlaneSensor', 'ProximitySensor', 'SphereSensor', 'TimeSensor', 'TouchSensor', 'VisibilitySensor', // sensors
				'Box', 'Cone', 'Cylinder', 'ElevationGrid', 'Extrusion', 'IndexedFaceSet', 'IndexedLineSet', 'PointSet', 'Sphere', // geometries
				'Color', 'Coordinate', 'Normal', 'TextureCoordinate', // geometric properties
				'Appearance', 'FontStyle', 'ImageTexture', 'Material', 'MovieTexture', 'PixelTexture', 'TextureTransform', // appearance
				'ColorInterpolator', 'CoordinateInterpolator', 'NormalInterpolator', 'OrientationInterpolator', 'PositionInterpolator', 'ScalarInterpolator', // interpolators
				'Background', 'Fog', 'NavigationInfo', 'Viewpoint', // bindable nodes
				'Text' // Text must be placed at the end of the regex so there are no matches for TextureTransform and TextureCoordinate
			];

			//

			const Version = createToken( {
				name: 'Version',
				pattern: /#VRML.*/,
				longer_alt: Identifier
			} );

			const NodeName = createToken( {
				name: 'NodeName',
				pattern: new RegExp( nodeTypes.join( '|' ) ),
				longer_alt: Identifier
			} );

			const DEF = createToken( {
				name: 'DEF',
				pattern: /DEF/,
				longer_alt: Identifier
			} );

			const USE = createToken( {
				name: 'USE',
				pattern: /USE/,
				longer_alt: Identifier
			} );

			const ROUTE = createToken( {
				name: 'ROUTE',
				pattern: /ROUTE/,
				longer_alt: Identifier
			} );

			const TO = createToken( {
				name: 'TO',
				pattern: /TO/,
				longer_alt: Identifier
			} );

			//

			const StringLiteral = createToken( { name: 'StringLiteral', pattern: /"(?:[^\\"\n\r]|\\[bfnrtv"\\/]|\\u[0-9a-fA-F][0-9a-fA-F][0-9a-fA-F][0-9a-fA-F])*"/ } );
			const HexLiteral = createToken( { name: 'HexLiteral', pattern: /0[xX][0-9a-fA-F]+/ } );
			const NumberLiteral = createToken( { name: 'NumberLiteral', pattern: /[-+]?[0-9]*\.?[0-9]+([eE][-+]?[0-9]+)?/ } );
			const TrueLiteral = createToken( { name: 'TrueLiteral', pattern: /TRUE/ } );
			const FalseLiteral = createToken( { name: 'FalseLiteral', pattern: /FALSE/ } );
			const NullLiteral = createToken( { name: 'NullLiteral', pattern: /NULL/ } );
			const LSquare = createToken( { name: 'LSquare', pattern: /\[/ } );
			const RSquare = createToken( { name: 'RSquare', pattern: /]/ } );
			const LCurly = createToken( { name: 'LCurly', pattern: /{/ } );
			const RCurly = createToken( { name: 'RCurly', pattern: /}/ } );
			const Comment = createToken( {
				name: 'Comment',
				pattern: /#.*/,
				group: chevrotain.Lexer.SKIPPED
			} );

			// commas, blanks, tabs, newlines and carriage returns are whitespace characters wherever they appear outside of string fields

			const WhiteSpace = createToken( {
				name: 'WhiteSpace',
				pattern: /[ ,\s]/,
				group: chevrotain.Lexer.SKIPPED
			} );

			const tokens = [
				WhiteSpace,
				// keywords appear before the Identifier
				NodeName,
				DEF,
				USE,
				ROUTE,
				TO,
				TrueLiteral,
				FalseLiteral,
				NullLiteral,
				// the Identifier must appear after the keywords because all keywords are valid identifiers
				Version,
				Identifier,
				RouteIdentifier,
				StringLiteral,
				HexLiteral,
				NumberLiteral,
				LSquare,
				RSquare,
				LCurly,
				RCurly,
				Comment
			];

			const tokenVocabulary = {};

			for ( let i = 0, l = tokens.length; i < l; i ++ ) {

				const token = tokens[ i ];

				tokenVocabulary[ token.name ] = token;

			}

			return { tokens: tokens, tokenVocabulary: tokenVocabulary };

		}


		function createVisitor( BaseVRMLVisitor ) {

			// the visitor is created dynamically based on the given base class

			class VRMLToASTVisitor extends BaseVRMLVisitor {

				constructor() {

					super();

					this.validateVisitor();

				}

				vrml( ctx ) {

					const data = {
						version: this.visit( ctx.version ),
						nodes: [],
						routes: []
					};

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						data.nodes.push( this.visit( node ) );

					}

					if ( ctx.route ) {

						for ( let i = 0, l = ctx.route.length; i < l; i ++ ) {

							const route = ctx.route[ i ];

							data.routes.push( this.visit( route ) );

						}

					}

					return data;

				}

				version( ctx ) {

					return ctx.Version[ 0 ].image;

				}

				node( ctx ) {

					const data = {
						name: ctx.NodeName[ 0 ].image,
						fields: []
					};

					if ( ctx.field ) {

						for ( let i = 0, l = ctx.field.length; i < l; i ++ ) {

							const field = ctx.field[ i ];

							data.fields.push( this.visit( field ) );

						}

					}

					// DEF

					if ( ctx.def ) {

						data.DEF = this.visit( ctx.def[ 0 ] );

					}

					return data;

				}

				field( ctx ) {

					const data = {
						name: ctx.Identifier[ 0 ].image,
						type: null,
						values: null
					};

					let result;

					// SFValue

					if ( ctx.singleFieldValue ) {

						result = this.visit( ctx.singleFieldValue[ 0 ] );

					}

					// MFValue

					if ( ctx.multiFieldValue ) {

						result = this.visit( ctx.multiFieldValue[ 0 ] );

					}

					data.type = result.type;
					data.values = result.values;

					return data;

				}

				def( ctx ) {

					return ( ctx.Identifier || ctx.NodeName )[ 0 ].image;

				}

				use( ctx ) {

					return { USE: ( ctx.Identifier || ctx.NodeName )[ 0 ].image };

				}

				singleFieldValue( ctx ) {

					return processField( this, ctx );

				}

				multiFieldValue( ctx ) {

					return processField( this, ctx );

				}

				route( ctx ) {

					const data = {
						FROM: ctx.RouteIdentifier[ 0 ].image,
						TO: ctx.RouteIdentifier[ 1 ].image
					};

					return data;

				}

			}

			function processField( scope, ctx ) {

				const field = {
					type: null,
					values: []
				};

				if ( ctx.node ) {

					field.type = 'node';

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						field.values.push( scope.visit( node ) );

					}

				}

				if ( ctx.use ) {

					field.type = 'use';

					for ( let i = 0, l = ctx.use.length; i < l; i ++ ) {

						const use = ctx.use[ i ];

						field.values.push( scope.visit( use ) );

					}

				}

				if ( ctx.StringLiteral ) {

					field.type = 'string';

					for ( let i = 0, l = ctx.StringLiteral.length; i < l; i ++ ) {

						const stringLiteral = ctx.StringLiteral[ i ];

						field.values.push( stringLiteral.image.replace( /'|"/g, '' ) );

					}

				}

				if ( ctx.NumberLiteral ) {

					field.type = 'number';

					for ( let i = 0, l = ctx.NumberLiteral.length; i < l; i ++ ) {

						const numberLiteral = ctx.NumberLiteral[ i ];

						field.values.push( parseFloat( numberLiteral.image ) );

					}

				}

				if ( ctx.HexLiteral ) {

					field.type = 'hex';

					for ( let i = 0, l = ctx.HexLiteral.length; i < l; i ++ ) {

						const hexLiteral = ctx.HexLiteral[ i ];

						field.values.push( hexLiteral.image );

					}

				}

				if ( ctx.TrueLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.TrueLiteral.length; i < l; i ++ ) {

						const trueLiteral = ctx.TrueLiteral[ i ];

						if ( trueLiteral.image === 'TRUE' ) field.values.push( true );

					}

				}

				if ( ctx.FalseLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.FalseLiteral.length; i < l; i ++ ) {

						const falseLiteral = ctx.FalseLiteral[ i ];

						if ( falseLiteral.image === 'FALSE' ) field.values.push( false );

					}

				}

				if ( ctx.NullLiteral ) {

					field.type = 'null';

					ctx.NullLiteral.forEach( function () {

						field.values.push( null );

					} );

				}

				return field;

			}

			return new VRMLToASTVisitor();

		}

		function parseTree( tree ) {

			// console.log( JSON.stringify( tree, null, 2 ) );

			const nodes = tree.nodes;
			const scene = new Scene();

			// first iteration: build nodemap based on DEF statements

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				const node = nodes[ i ];

				buildNodeMap( node );

			}

			// second iteration: build nodes

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				const node = nodes[ i ];
				const object = getNode( node );

				if ( object instanceof Object3D ) scene.add( object );

				if ( node.name === 'WorldInfo' ) scene.userData.worldInfo = object;

			}

			return scene;

		}

		function buildNodeMap( node ) {

			if ( node.DEF ) {

				nodeMap[ node.DEF ] = node;

			}

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];

				if ( field.type === 'node' ) {

					const fieldValues = field.values;

					for ( let j = 0, jl = fieldValues.length; j < jl; j ++ ) {

						buildNodeMap( fieldValues[ j ] );

					}

				}


			}

		}


		function getNode( node ) {

			// handle case where a node refers to a different one

			if ( node.USE ) {

				return resolveUSE( node.USE );

			}

			if ( node.build !== undefined ) return node.build;

			node.build = buildNode( node );

			return node.build;

		}

		// node builder

		function buildNode( node ) {

			const nodeName = node.name;
			let build;

			switch ( nodeName ) {

				case 'Anchor':
				case 'Group':
				case 'Transform':
				case 'Collision':
					build = buildGroupingNode( node );
					break;

				case 'Background':
					build = buildBackgroundNode( node );
					break;

				case 'Shape':
					build = buildShapeNode( node );
					break;

				case 'Appearance':
					build = buildAppearanceNode( node );
					break;

				case 'Material':
					build = buildMaterialNode( node );
					break;

				case 'ImageTexture':
					build = buildImageTextureNode( node );
					break;

				case 'PixelTexture':
					build = buildPixelTextureNode( node );
					break;

				case 'TextureTransform':
					build = buildTextureTransformNode( node );
					break;

				case 'IndexedFaceSet':
					build = buildIndexedFaceSetNode( node );
					break;

				case 'IndexedLineSet':
					build = buildIndexedLineSetNode( node );
					break;

				case 'PointSet':
					build = buildPointSetNode( node );
					break;

				case 'Box':
					build = buildBoxNode( node );
					break;

				case 'Cone':
					build = buildConeNode( node );
					break;

				case 'Cylinder':
					build = buildCylinderNode( node );
					break;

				case 'Sphere':
					build = buildSphereNode( node );
					break;

				case 'ElevationGrid':
					build = buildElevationGridNode( node );
					break;

				case 'Extrusion':
					build = buildExtrusionNode( node );
					break;

				case 'Color':
				case 'Coordinate':
				case 'Normal':
				case 'TextureCoordinate':
					build = buildGeometricNode( node );
					break;

				case 'WorldInfo':
					build = buildWorldInfoNode( node );
					break;

				case 'Billboard':

				case 'Inline':
				case 'LOD':
				case 'Switch':

				case 'AudioClip':
				case 'DirectionalLight':
				case 'PointLight':
				case 'Script':
				case 'Sound':
				case 'SpotLight':

				case 'CylinderSensor':
				case 'PlaneSensor':
				case 'ProximitySensor':
				case 'SphereSensor':
				case 'TimeSensor':
				case 'TouchSensor':
				case 'VisibilitySensor':

				case 'Text':

				case 'FontStyle':
				case 'MovieTexture':

				case 'ColorInterpolator':
				case 'CoordinateInterpolator':
				case 'NormalInterpolator':
				case 'OrientationInterpolator':
				case 'PositionInterpolator':
				case 'ScalarInterpolator':

				case 'Fog':
				case 'NavigationInfo':
				case 'Viewpoint':
					// node not supported yet
					break;

				default:
					console.warn( 'THREE.VRMLLoader: Unknown node:', nodeName );
					break;

			}

			if ( build !== undefined && node.DEF !== undefined && build.hasOwnProperty( 'name' ) === true ) {

				build.name = node.DEF;

			}

			return build;

		}

		function buildGroupingNode( node ) {

			const object = new Group();

			//

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bboxCenter':
						// field not supported
						break;

					case 'bboxSize':
						// field not supported
						break;

					case 'center':
						// field not supported
						break;

					case 'children':
						parseFieldChildren( fieldValues, object );
						break;

					case 'description':
						// field not supported
						break;

					case 'collide':
						// field not supported
						break;

					case 'parameter':
						// field not supported
						break;

					case 'rotation':
						const axis = new Vector3( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] ).normalize();
						const angle = fieldValues[ 3 ];
						object.quaternion.setFromAxisAngle( axis, angle );
						break;

					case 'scale':
						object.scale.set( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] );
						break;

					case 'scaleOrientation':
						// field not supported
						break;

					case 'translation':
						object.position.set( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] );
						break;

					case 'proxy':
						// field not supported
						break;

					case 'url':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return object;

		}

		function buildBackgroundNode( node ) {

			const group = new Group();

			let groundAngle, groundColor;
			let skyAngle, skyColor;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'groundAngle':
						groundAngle = fieldValues;
						break;

					case 'groundColor':
						groundColor = fieldValues;
						break;

					case 'backUrl':
						// field not supported
						break;

					case 'bottomUrl':
						// field not supported
						break;

					case 'frontUrl':
						// field not supported
						break;

					case 'leftUrl':
						// field not supported
						break;

					case 'rightUrl':
						// field not supported
						break;

					case 'topUrl':
						// field not supported
						break;

					case 'skyAngle':
						skyAngle = fieldValues;
						break;

					case 'skyColor':
						skyColor = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const radius = 10000;

			// sky

			if ( skyColor ) {

				const skyGeometry = new SphereGeometry( radius, 32, 16 );
				const skyMaterial = new MeshBasicMaterial( { fog: false, side: BackSide, depthWrite: false, depthTest: false } );

				if ( skyColor.length > 3 ) {

					paintFaces( skyGeometry, radius, skyAngle, toColorArray( skyColor ), true );
					skyMaterial.vertexColors = true;

				} else {

					skyMaterial.color.setRGB( skyColor[ 0 ], skyColor[ 1 ], skyColor[ 2 ], SRGBColorSpace );

				}

				const sky = new Mesh( skyGeometry, skyMaterial );
				group.add( sky );

			}

			// ground

			if ( groundColor ) {

				if ( groundColor.length > 0 ) {

					const groundGeometry = new SphereGeometry( radius, 32, 16, 0, 2 * Math.PI, 0.5 * Math.PI, 1.5 * Math.PI );
					const groundMaterial = new MeshBasicMaterial( { fog: false, side: BackSide, vertexColors: true, depthWrite: false, depthTest: false } );

					paintFaces( groundGeometry, radius, groundAngle, toColorArray( groundColor ), false );

					const ground = new Mesh( groundGeometry, groundMaterial );
					group.add( ground );

				}

			}

			// render background group first

			group.renderOrder = - Infinity;

			return group;

		}

		function buildShapeNode( node ) {

			const fields = node.fields;

			// if the appearance field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0)

			let material = new MeshBasicMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0x000000
			} );
			let geometry;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'appearance':
						if ( fieldValues[ 0 ] !== null ) {

							material = getNode( fieldValues[ 0 ] );

						}

						break;

					case 'geometry':
						if ( fieldValues[ 0 ] !== null ) {

							geometry = getNode( fieldValues[ 0 ] );

						}

						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// build 3D object

			let object;

			if ( geometry && geometry.attributes.position ) {

				const type = geometry._type;

				if ( type === 'points' ) { // points

					const pointsMaterial = new PointsMaterial( {
						name: Loader.DEFAULT_MATERIAL_NAME,
						color: 0xffffff,
						opacity: material.opacity,
						transparent: material.transparent
					} );

					if ( geometry.attributes.color !== undefined ) {

						pointsMaterial.vertexColors = true;

					} else {

						// if the color field is NULL and there is a material defined for the appearance affecting this PointSet, then use the emissiveColor of the material to draw the points

						if ( material.isMeshPhongMaterial ) {

							pointsMaterial.color.copy( material.emissive );

						}

					}

					object = new Points( geometry, pointsMaterial );

				} else if ( type === 'line' ) { // lines

					const lineMaterial = new LineBasicMaterial( {
						name: Loader.DEFAULT_MATERIAL_NAME,
						color: 0xffffff,
						opacity: material.opacity,
						transparent: material.transparent
					} );

					if ( geometry.attributes.color !== undefined ) {

						lineMaterial.vertexColors = true;

					} else {

						// if the color field is NULL and there is a material defined for the appearance affecting this IndexedLineSet, then use the emissiveColor of the material to draw the lines

						if ( material.isMeshPhongMaterial ) {

							lineMaterial.color.copy( material.emissive );

						}

					}

					object = new LineSegments( geometry, lineMaterial );

				} else { // consider meshes

					// check "solid" hint (it's placed in the geometry but affects the material)

					if ( geometry._solid !== undefined ) {

						material.side = ( geometry._solid ) ? FrontSide : DoubleSide;

					}

					// check for vertex colors

					if ( geometry.attributes.color !== undefined ) {

						material.vertexColors = true;

					}

					object = new Mesh( geometry, material );

				}

			} else {

				object = new Object3D();

				// if the geometry field is NULL or no vertices are defined the object is not drawn

				object.visible = false;

			}

			return object;

		}

		function buildAppearanceNode( node ) {

			let material = new MeshPhongMaterial();
			let transformData;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'material':
						if ( fieldValues[ 0 ] !== null ) {

							const materialData = getNode( fieldValues[ 0 ] );

							if ( materialData.diffuseColor ) material.color.copy( materialData.diffuseColor );
							if ( materialData.emissiveColor ) material.emissive.copy( materialData.emissiveColor );
							if ( materialData.shininess ) material.shininess = materialData.shininess;
							if ( materialData.specularColor ) material.specular.copy( materialData.specularColor );
							if ( materialData.transparency ) material.opacity = 1 - materialData.transparency;
							if ( materialData.transparency > 0 ) material.transparent = true;

						} else {

							// if the material field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0)

							material = new MeshBasicMaterial( {
								name: Loader.DEFAULT_MATERIAL_NAME,
								color: 0x000000
							} );

						}

						break;

					case 'texture':
						const textureNode = fieldValues[ 0 ];
						if ( textureNode !== null ) {

							if ( textureNode.name === 'ImageTexture' || textureNode.name === 'PixelTexture' ) {

								material.map = getNode( textureNode );

							} else {

								// MovieTexture not supported yet

							}

						}

						break;

					case 'textureTransform':
						if ( fieldValues[ 0 ] !== null ) {

							transformData = getNode( fieldValues[ 0 ] );

						}

						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// only apply texture transform data if a texture was defined

			if ( material.map ) {

				// respect VRML lighting model

				if ( material.map.__type ) {

					switch ( material.map.__type ) {

						case TEXTURE_TYPE.INTENSITY_ALPHA:
							material.opacity = 1; // ignore transparency
							break;

						case TEXTURE_TYPE.RGB:
							material.color.set( 0xffffff ); // ignore material color
							break;

						case TEXTURE_TYPE.RGBA:
							material.color.set( 0xffffff ); // ignore material color
							material.opacity = 1; // ignore transparency
							break;

						default:

					}

					delete material.map.__type;

				}

				// apply texture transform

				if ( transformData ) {

					material.map.center.copy( transformData.center );
					material.map.rotation = transformData.rotation;
					material.map.repeat.copy( transformData.scale );
					material.map.offset.copy( transformData.translation );

				}

			}

			return material;

		}

		function buildMaterialNode( node ) {

			const materialData = {};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'ambientIntensity':
						// field not supported
						break;

					case 'diffuseColor':
						materialData.diffuseColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'emissiveColor':
						materialData.emissiveColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'shininess':
						materialData.shininess = fieldValues[ 0 ];
						break;

					case 'specularColor':
						materialData.specularColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'transparency':
						materialData.transparency = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return materialData;

		}

		function parseHexColor( hex, textureType, color ) {

			let value;

			switch ( textureType ) {

				case TEXTURE_TYPE.INTENSITY:
					// Intensity texture: A one-component image specifies one-byte hexadecimal or integer values representing the intensity of the image
					value = parseInt( hex );
					color.r = value;
					color.g = value;
					color.b = value;
					color.a = 1;
					break;

				case TEXTURE_TYPE.INTENSITY_ALPHA:
					// Intensity+Alpha texture: A two-component image specifies the intensity in the first (high) byte and the alpha opacity in the second (low) byte.
					value = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.r = value;
					color.g = value;
					color.b = value;
					color.a = parseInt( '0x' + hex.substring( 4, 6 ) );
					break;

				case TEXTURE_TYPE.RGB:
					// RGB texture: Pixels in a three-component image specify the red component in the first (high) byte, followed by the green and blue components
					color.r = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.g = parseInt( '0x' + hex.substring( 4, 6 ) );
					color.b = parseInt( '0x' + hex.substring( 6, 8 ) );
					color.a = 1;
					break;

				case TEXTURE_TYPE.RGBA:
					// RGBA texture: Four-component images specify the alpha opacity byte after red/green/blue
					color.r = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.g = parseInt( '0x' + hex.substring( 4, 6 ) );
					color.b = parseInt( '0x' + hex.substring( 6, 8 ) );
					color.a = parseInt( '0x' + hex.substring( 8, 10 ) );
					break;

				default:

			}

		}

		function getTextureType( num_components ) {

			let type;

			switch ( num_components ) {

				case 1:
					type = TEXTURE_TYPE.INTENSITY;
					break;

				case 2:
					type = TEXTURE_TYPE.INTENSITY_ALPHA;
					break;

				case 3:
					type = TEXTURE_TYPE.RGB;
					break;

				case 4:
					type = TEXTURE_TYPE.RGBA;
					break;

				default:

			}

			return type;

		}

		function buildPixelTextureNode( node ) {

			let texture;
			let wrapS = RepeatWrapping;
			let wrapT = RepeatWrapping;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'image':
						const width = fieldValues[ 0 ];
						const height = fieldValues[ 1 ];
						const num_components = fieldValues[ 2 ];

						const textureType = getTextureType( num_components );

						const data = new Uint8Array( 4 * width * height );

						const color = { r: 0, g: 0, b: 0, a: 0 };

						for ( let j = 3, k = 0, jl = fieldValues.length; j < jl; j ++, k ++ ) {

							parseHexColor( fieldValues[ j ], textureType, color );

							const stride = k * 4;

							data[ stride + 0 ] = color.r;
							data[ stride + 1 ] = color.g;
							data[ stride + 2 ] = color.b;
							data[ stride + 3 ] = color.a;

						}

						texture = new DataTexture( data, width, height );
						texture.colorSpace = SRGBColorSpace;
						texture.needsUpdate = true;
						texture.__type = textureType; // needed for material modifications
						break;

					case 'repeatS':
						if ( fieldValues[ 0 ] === false ) wrapS = ClampToEdgeWrapping;
						break;

					case 'repeatT':
						if ( fieldValues[ 0 ] === false ) wrapT = ClampToEdgeWrapping;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( texture ) {

				texture.wrapS = wrapS;
				texture.wrapT = wrapT;

			}

			return texture;

		}

		function buildImageTextureNode( node ) {

			let texture;
			let wrapS = RepeatWrapping;
			let wrapT = RepeatWrapping;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'url':
						const url = fieldValues[ 0 ];
						if ( url ) texture = textureLoader.load( url );
						break;

					case 'repeatS':
						if ( fieldValues[ 0 ] === false ) wrapS = ClampToEdgeWrapping;
						break;

					case 'repeatT':
						if ( fieldValues[ 0 ] === false ) wrapT = ClampToEdgeWrapping;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( texture ) {

				texture.wrapS = wrapS;
				texture.wrapT = wrapT;
				texture.colorSpace = SRGBColorSpace;

			}

			return texture;

		}

		function buildTextureTransformNode( node ) {

			const transformData = {
				center: new Vector2(),
				rotation: new Vector2(),
				scale: new Vector2(),
				translation: new Vector2()
			};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'center':
						transformData.center.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					case 'rotation':
						transformData.rotation = fieldValues[ 0 ];
						break;

					case 'scale':
						transformData.scale.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					case 'translation':
						transformData.translation.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return transformData;

		}

		function buildGeometricNode( node ) {

			return node.fields[ 0 ].values;

		}

		function buildWorldInfoNode( node ) {

			const worldInfo = {};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'title':
						worldInfo.title = fieldValues[ 0 ];
						break;

					case 'info':
						worldInfo.info = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return worldInfo;

		}

		function buildIndexedFaceSetNode( node ) {

			let color, coord, normal, texCoord;
			let ccw = true, solid = true, creaseAngle = 0;
			let colorIndex, coordIndex, normalIndex, texCoordIndex;
			let colorPerVertex = true, normalPerVertex = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;

					case 'normal':
						const normalNode = fieldValues[ 0 ];

						if ( normalNode !== null ) {

							normal = getNode( normalNode );

						}

						break;

					case 'texCoord':
						const texCoordNode = fieldValues[ 0 ];

						if ( texCoordNode !== null ) {

							texCoord = getNode( texCoordNode );

						}

						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'colorIndex':
						colorIndex = fieldValues;
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'convex':
						// field not supported
						break;

					case 'coordIndex':
						coordIndex = fieldValues;
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'normalIndex':
						normalIndex = fieldValues;
						break;

					case 'normalPerVertex':
						normalPerVertex = fieldValues[ 0 ];
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'texCoordIndex':
						texCoordIndex = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( coordIndex === undefined ) {

				console.warn( 'THREE.VRMLLoader: Missing coordIndex.' );

				return new BufferGeometry(); // handle VRML files with incomplete geometry definition

			}

			const triangulatedCoordIndex = triangulateFaceIndex( coordIndex, ccw );

			let colorAttribute;
			let normalAttribute;
			let uvAttribute;

			if ( color ) {

				if ( colorPerVertex === true ) {

					if ( colorIndex && colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then it is used to choose colors for each vertex of the IndexedFaceSet.

						const triangulatedColorIndex = triangulateFaceIndex( colorIndex, ccw );
						colorAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedColorIndex, color, 3 );

					} else {

						// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node

						colorAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( color, 3 ) );

					}

				} else {

					if ( colorIndex && colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then they are used to choose one color for each face of the IndexedFaceSet

						const flattenFaceColors = flattenData( color, colorIndex );
						const triangulatedFaceColors = triangulateFaceData( flattenFaceColors, coordIndex );
						colorAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceColors );

					} else {

						// if the colorIndex field is empty, then the color are applied to each face of the IndexedFaceSet in order

						const triangulatedFaceColors = triangulateFaceData( color, coordIndex );
						colorAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceColors );


					}

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			if ( normal ) {

				if ( normalPerVertex === true ) {

					// consider vertex normals

					if ( normalIndex && normalIndex.length > 0 ) {

						// if the normalIndex field is not empty, then it is used to choose normals for each vertex of the IndexedFaceSet.

						const triangulatedNormalIndex = triangulateFaceIndex( normalIndex, ccw );
						normalAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedNormalIndex, normal, 3 );

					} else {

						// if the normalIndex field is empty, then the coordIndex field is used to choose normals from the Normal node

						normalAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( normal, 3 ) );

					}

				} else {

					// consider face normals

					if ( normalIndex && normalIndex.length > 0 ) {

						// if the normalIndex field is not empty, then they are used to choose one normal for each face of the IndexedFaceSet

						const flattenFaceNormals = flattenData( normal, normalIndex );
						const triangulatedFaceNormals = triangulateFaceData( flattenFaceNormals, coordIndex );
						normalAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceNormals );

					} else {

						// if the normalIndex field is empty, then the normals are applied to each face of the IndexedFaceSet in order

						const triangulatedFaceNormals = triangulateFaceData( normal, coordIndex );
						normalAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceNormals );

					}

				}

			} else {

				// if the normal field is NULL, then the loader should automatically generate normals, using creaseAngle to determine if and how normals are smoothed across shared vertices

				normalAttribute = computeNormalAttribute( triangulatedCoordIndex, coord, creaseAngle );

			}

			if ( texCoord ) {

				// texture coordinates are always defined on vertex level

				if ( texCoordIndex && texCoordIndex.length > 0 ) {

					// if the texCoordIndex field is not empty, then it is used to choose texture coordinates for each vertex of the IndexedFaceSet.

					const triangulatedTexCoordIndex = triangulateFaceIndex( texCoordIndex, ccw );
					uvAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedTexCoordIndex, texCoord, 2 );


				} else {

					// if the texCoordIndex field is empty, then the coordIndex array is used to choose texture coordinates from the TextureCoordinate node

					uvAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( texCoord, 2 ) );

				}

			}

			const geometry = new BufferGeometry();
			const positionAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( coord, 3 ) );

			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );

			// optional attributes

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );
			if ( uvAttribute ) geometry.setAttribute( 'uv', uvAttribute );

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}

		function buildIndexedLineSetNode( node ) {

			let color, coord;
			let colorIndex, coordIndex;
			let colorPerVertex = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;

					case 'colorIndex':
						colorIndex = fieldValues;
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'coordIndex':
						coordIndex = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// build lines

			let colorAttribute;

			const expandedLineIndex = expandLineIndex( coordIndex ); // create an index for three.js's linesegment primitive

			if ( color ) {

				if ( colorPerVertex === true ) {

					if ( colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then one color is used for each polyline of the IndexedLineSet.

						const expandedColorIndex = expandLineIndex( colorIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromIndexedData( expandedLineIndex, expandedColorIndex, color, 3 ); // compute data on vertex level

					} else {

						// if the colorIndex field is empty, then the colors are applied to each polyline of the IndexedLineSet in order.

						colorAttribute = toNonIndexedAttribute( expandedLineIndex, new Float32BufferAttribute( color, 3 ) );

					}

				} else {

					if ( colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then colors are applied to each vertex of the IndexedLineSet

						const flattenLineColors = flattenData( color, colorIndex ); // compute colors for each VRML primitive
						const expandedLineColors = expandLineData( flattenLineColors, coordIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromLineData( expandedLineIndex, expandedLineColors ); // compute data on vertex level


					} else {

						// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node

						const expandedLineColors = expandLineData( color, coordIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromLineData( expandedLineIndex, expandedLineColors ); // compute data on vertex level

					}

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			//

			const geometry = new BufferGeometry();

			const positionAttribute = toNonIndexedAttribute( expandedLineIndex, new Float32BufferAttribute( coord, 3 ) );
			geometry.setAttribute( 'position', positionAttribute );

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );

			geometry._type = 'line';

			return geometry;

		}

		function buildPointSetNode( node ) {

			let color, coord;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;


					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new BufferGeometry();

			geometry.setAttribute( 'position', new Float32BufferAttribute( coord, 3 ) );

			if ( color ) {

				const colorAttribute = new Float32BufferAttribute( color, 3 );
				convertColorsToLinearSRGB( colorAttribute );

				geometry.setAttribute( 'color', colorAttribute );

			}

			geometry._type = 'points';

			return geometry;

		}

		function buildBoxNode( node ) {

			const size = new Vector3( 2, 2, 2 );

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'size':
						size.x = fieldValues[ 0 ];
						size.y = fieldValues[ 1 ];
						size.z = fieldValues[ 2 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new BoxGeometry( size.x, size.y, size.z );

			return geometry;

		}

		function buildConeNode( node ) {

			let radius = 1, height = 2, openEnded = false;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bottom':
						openEnded = ! fieldValues[ 0 ];
						break;

					case 'bottomRadius':
						radius = fieldValues[ 0 ];
						break;

					case 'height':
						height = fieldValues[ 0 ];
						break;

					case 'side':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new ConeGeometry( radius, height, 16, 1, openEnded );

			return geometry;

		}

		function buildCylinderNode( node ) {

			let radius = 1, height = 2;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bottom':
						// field not supported
						break;

					case 'radius':
						radius = fieldValues[ 0 ];
						break;

					case 'height':
						height = fieldValues[ 0 ];
						break;

					case 'side':
						// field not supported
						break;

					case 'top':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new CylinderGeometry( radius, radius, height, 16, 1 );

			return geometry;

		}

		function buildSphereNode( node ) {

			let radius = 1;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'radius':
						radius = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new SphereGeometry( radius, 16, 16 );

			return geometry;

		}

		function buildElevationGridNode( node ) {

			let color;
			let normal;
			let texCoord;
			let height;

			let colorPerVertex = true;
			let normalPerVertex = true;
			let solid = true;
			let ccw = true;
			let creaseAngle = 0;
			let xDimension = 2;
			let zDimension = 2;
			let xSpacing = 1;
			let zSpacing = 1;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'normal':
						const normalNode = fieldValues[ 0 ];

						if ( normalNode !== null ) {

							normal = getNode( normalNode );

						}

						break;

					case 'texCoord':
						const texCoordNode = fieldValues[ 0 ];

						if ( texCoordNode !== null ) {

							texCoord = getNode( texCoordNode );

						}

						break;

					case 'height':
						height = fieldValues;
						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'normalPerVertex':
						normalPerVertex = fieldValues[ 0 ];
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'xDimension':
						xDimension = fieldValues[ 0 ];
						break;

					case 'xSpacing':
						xSpacing = fieldValues[ 0 ];
						break;

					case 'zDimension':
						zDimension = fieldValues[ 0 ];
						break;

					case 'zSpacing':
						zSpacing = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// vertex data

			const vertices = [];
			const normals = [];
			const colors = [];
			const uvs = [];

			for ( let i = 0; i < zDimension; i ++ ) {

				for ( let j = 0; j < xDimension; j ++ ) {

					// compute a row major index

					const index = ( i * xDimension ) + j;

					// vertices

					const x = xSpacing * i;
					const y = height[ index ];
					const z = zSpacing * j;

					vertices.push( x, y, z );

					// colors

					if ( color && colorPerVertex === true ) {

						const r = color[ index * 3 + 0 ];
						const g = color[ index * 3 + 1 ];
						const b = color[ index * 3 + 2 ];

						colors.push( r, g, b );

					}

					// normals

					if ( normal && normalPerVertex === true ) {

						const xn = normal[ index * 3 + 0 ];
						const yn = normal[ index * 3 + 1 ];
						const zn = normal[ index * 3 + 2 ];

						normals.push( xn, yn, zn );

					}

					// uvs

					if ( texCoord ) {

						const s = texCoord[ index * 2 + 0 ];
						const t = texCoord[ index * 2 + 1 ];

						uvs.push( s, t );


					} else {

						uvs.push( i / ( xDimension - 1 ), j / ( zDimension - 1 ) );

					}

				}

			}

			// indices

			const indices = [];

			for ( let i = 0; i < xDimension - 1; i ++ ) {

				for ( let j = 0; j < zDimension - 1; j ++ ) {

					// from https://tecfa.unige.ch/guides/vrml/vrml97/spec/part1/nodesRef.html#ElevationGrid

					const a = i + j * xDimension;
					const b = i + ( j + 1 ) * xDimension;
					const c = ( i + 1 ) + ( j + 1 ) * xDimension;
					const d = ( i + 1 ) + j * xDimension;

					// faces

					if ( ccw === true ) {

						indices.push( a, c, b );
						indices.push( c, a, d );

					} else {

						indices.push( a, b, c );
						indices.push( c, d, a );

					}

				}

			}

			//

			const positionAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( vertices, 3 ) );
			const uvAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( uvs, 2 ) );
			let colorAttribute;
			let normalAttribute;

			// color attribute

			if ( color ) {

				if ( colorPerVertex === false ) {

					for ( let i = 0; i < xDimension - 1; i ++ ) {

						for ( let j = 0; j < zDimension - 1; j ++ ) {

							const index = i + j * ( xDimension - 1 );

							const r = color[ index * 3 + 0 ];
							const g = color[ index * 3 + 1 ];
							const b = color[ index * 3 + 2 ];

							// one color per quad

							colors.push( r, g, b ); colors.push( r, g, b ); colors.push( r, g, b );
							colors.push( r, g, b ); colors.push( r, g, b ); colors.push( r, g, b );

						}

					}

					colorAttribute = new Float32BufferAttribute( colors, 3 );

				} else {

					colorAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( colors, 3 ) );

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			// normal attribute

			if ( normal ) {

				if ( normalPerVertex === false ) {

					for ( let i = 0; i < xDimension - 1; i ++ ) {

						for ( let j = 0; j < zDimension - 1; j ++ ) {

							const index = i + j * ( xDimension - 1 );

							const xn = normal[ index * 3 + 0 ];
							const yn = normal[ index * 3 + 1 ];
							const zn = normal[ index * 3 + 2 ];

							// one normal per quad

							normals.push( xn, yn, zn ); normals.push( xn, yn, zn ); normals.push( xn, yn, zn );
							normals.push( xn, yn, zn ); normals.push( xn, yn, zn ); normals.push( xn, yn, zn );

						}

					}

					normalAttribute = new Float32BufferAttribute( normals, 3 );

				} else {

					normalAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( normals, 3 ) );

				}

			} else {

				normalAttribute = computeNormalAttribute( indices, vertices, creaseAngle );

			}

			// build geometry

			const geometry = new BufferGeometry();
			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );
			geometry.setAttribute( 'uv', uvAttribute );

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}

		function buildExtrusionNode( node ) {

			let crossSection = [ 1, 1, 1, - 1, - 1, - 1, - 1, 1, 1, 1 ];
			let spine = [ 0, 0, 0, 0, 1, 0 ];
			let scale;
			let orientation;

			let beginCap = true;
			let ccw = true;
			let creaseAngle = 0;
			let endCap = true;
			let solid = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'beginCap':
						beginCap = fieldValues[ 0 ];
						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'convex':
						// field not supported
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'crossSection':
						crossSection = fieldValues;
						break;

					case 'endCap':
						endCap = fieldValues[ 0 ];
						break;

					case 'orientation':
						orientation = fieldValues;
						break;

					case 'scale':
						scale = fieldValues;
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'spine':
						spine = fieldValues; // only extrusion along the Y-axis are supported so far
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const crossSectionClosed = ( crossSection[ 0 ] === crossSection[ crossSection.length - 2 ] && crossSection[ 1 ] === crossSection[ crossSection.length - 1 ] );

			// vertices

			const vertices = [];
			const spineVector = new Vector3();
			const scaling = new Vector3();

			const axis = new Vector3();
			const vertex = new Vector3();
			const quaternion = new Quaternion();

			for ( let i = 0, j = 0, o = 0, il = spine.length; i < il; i += 3, j += 2, o += 4 ) {

				spineVector.fromArray( spine, i );

				scaling.x = scale ? scale[ j + 0 ] : 1;
				scaling.y = 1;
				scaling.z = scale ? scale[ j + 1 ] : 1;

				axis.x = orientation ? orientation[ o + 0 ] : 0;
				axis.y = orientation ? orientation[ o + 1 ] : 0;
				axis.z = orientation ? orientation[ o + 2 ] : 1;
				const angle = orientation ? orientation[ o + 3 ] : 0;

				for ( let k = 0, kl = crossSection.length; k < kl; k += 2 ) {

					vertex.x = crossSection[ k + 0 ];
					vertex.y = 0;
					vertex.z = crossSection[ k + 1 ];

					// scale

					vertex.multiply( scaling );

					// rotate

					quaternion.setFromAxisAngle( axis, angle );
					vertex.applyQuaternion( quaternion );

					// translate

					vertex.add( spineVector );

					vertices.push( vertex.x, vertex.y, vertex.z );

				}

			}

			// indices

			const indices = [];

			const spineCount = spine.length / 3;
			const crossSectionCount = crossSection.length / 2;

			for ( let i = 0; i < spineCount - 1; i ++ ) {

				for ( let j = 0; j < crossSectionCount - 1; j ++ ) {

					const a = j + i * crossSectionCount;
					let b = ( j + 1 ) + i * crossSectionCount;
					const c = j + ( i + 1 ) * crossSectionCount;
					let d = ( j + 1 ) + ( i + 1 ) * crossSectionCount;

					if ( ( j === crossSectionCount - 2 ) && ( crossSectionClosed === true ) ) {

						b = i * crossSectionCount;
						d = ( i + 1 ) * crossSectionCount;

					}

					if ( ccw === true ) {

						indices.push( a, b, c );
						indices.push( c, b, d );

					} else {

						indices.push( a, c, b );
						indices.push( c, d, b );

					}

				}

			}

			// triangulate cap

			if ( beginCap === true || endCap === true ) {

				const contour = [];

				for ( let i = 0, l = crossSection.length; i < l; i += 2 ) {

					contour.push( new Vector2( crossSection[ i ], crossSection[ i + 1 ] ) );

				}

				const faces = ShapeUtils.triangulateShape( contour, [] );
				const capIndices = [];

				for ( let i = 0, l = faces.length; i < l; i ++ ) {

					const face = faces[ i ];

					capIndices.push( face[ 0 ], face[ 1 ], face[ 2 ] );

				}

				// begin cap

				if ( beginCap === true ) {

					for ( let i = 0, l = capIndices.length; i < l; i += 3 ) {

						if ( ccw === true ) {

							indices.push( capIndices[ i + 0 ], capIndices[ i + 1 ], capIndices[ i + 2 ] );

						} else {

							indices.push( capIndices[ i + 0 ], capIndices[ i + 2 ], capIndices[ i + 1 ] );

						}

					}

				}

				// end cap

				if ( endCap === true ) {

					const indexOffset = crossSectionCount * ( spineCount - 1 ); // references to the first vertex of the last cross section

					for ( let i = 0, l = capIndices.length; i < l; i += 3 ) {

						if ( ccw === true ) {

							indices.push( indexOffset + capIndices[ i + 0 ], indexOffset + capIndices[ i + 2 ], indexOffset + capIndices[ i + 1 ] );

						} else {

							indices.push( indexOffset + capIndices[ i + 0 ], indexOffset + capIndices[ i + 1 ], indexOffset + capIndices[ i + 2 ] );

						}

					}

				}

			}

			const positionAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( vertices, 3 ) );
			const normalAttribute = computeNormalAttribute( indices, vertices, creaseAngle );

			const geometry = new BufferGeometry();
			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );
			// no uvs yet

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}

		// helper functions

		function resolveUSE( identifier ) {

			const node = nodeMap[ identifier ];
			const build = getNode( node );

			// because the same 3D objects can have different transformations, it's necessary to clone them.
			// materials can be influenced by the geometry (e.g. vertex normals). cloning is necessary to avoid
			// any side effects

			return ( build.isObject3D || build.isMaterial ) ? build.clone() : build;

		}

		function parseFieldChildren( children, owner ) {

			for ( let i = 0, l = children.length; i < l; i ++ ) {

				const object = getNode( children[ i ] );

				if ( object instanceof Object3D ) owner.add( object );

			}

		}

		function triangulateFaceIndex( index, ccw ) {

			const indices = [];

			// since face definitions can have more than three vertices, it's necessary to
			// perform a simple triangulation

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ start ];
				const i2 = index[ i + ( ccw ? 1 : 2 ) ];
				const i3 = index[ i + ( ccw ? 2 : 1 ) ];

				indices.push( i1, i2, i3 );

				// an index of -1 indicates that the current face has ended and the next one begins

				if ( index[ i + 3 ] === - 1 || i + 3 >= l ) {

					i += 3;
					start = i + 1;

				}

			}

			return indices;

		}

		function triangulateFaceData( data, index ) {

			const triangulatedData = [];

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const stride = start * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				triangulatedData.push( x, y, z );

				// an index of -1 indicates that the current face has ended and the next one begins

				if ( index[ i + 3 ] === - 1 || i + 3 >= l ) {

					i += 3;
					start ++;

				}

			}

			return triangulatedData;

		}

		function flattenData( data, index ) {

			const flattenData = [];

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ i ];

				const stride = i1 * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				flattenData.push( x, y, z );

			}

			return flattenData;

		}

		function expandLineIndex( index ) {

			const indices = [];

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ i ];
				const i2 = index[ i + 1 ];

				indices.push( i1, i2 );

				// an index of -1 indicates that the current line has ended and the next one begins

				if ( index[ i + 2 ] === - 1 || i + 2 >= l ) {

					i += 2;

				}

			}

			return indices;

		}

		function expandLineData( data, index ) {

			const triangulatedData = [];

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const stride = start * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				triangulatedData.push( x, y, z );

				// an index of -1 indicates that the current line has ended and the next one begins

				if ( index[ i + 2 ] === - 1 || i + 2 >= l ) {

					i += 2;
					start ++;

				}

			}

			return triangulatedData;

		}

		const vA = new Vector3();
		const vB = new Vector3();
		const vC = new Vector3();

		const uvA = new Vector2();
		const uvB = new Vector2();
		const uvC = new Vector2();

		function computeAttributeFromIndexedData( coordIndex, index, data, itemSize ) {

			const array = [];

			// we use the coordIndex.length as delimiter since normalIndex must contain at least as many indices

			for ( let i = 0, l = coordIndex.length; i < l; i += 3 ) {

				const a = index[ i ];
				const b = index[ i + 1 ];
				const c = index[ i + 2 ];

				if ( itemSize === 2 ) {

					uvA.fromArray( data, a * itemSize );
					uvB.fromArray( data, b * itemSize );
					uvC.fromArray( data, c * itemSize );

					array.push( uvA.x, uvA.y );
					array.push( uvB.x, uvB.y );
					array.push( uvC.x, uvC.y );

				} else {

					vA.fromArray( data, a * itemSize );
					vB.fromArray( data, b * itemSize );
					vC.fromArray( data, c * itemSize );

					array.push( vA.x, vA.y, vA.z );
					array.push( vB.x, vB.y, vB.z );
					array.push( vC.x, vC.y, vC.z );

				}

			}

			return new Float32BufferAttribute( array, itemSize );

		}

		function computeAttributeFromFaceData( index, faceData ) {

			const array = [];

			for ( let i = 0, j = 0, l = index.length; i < l; i += 3, j ++ ) {

				vA.fromArray( faceData, j * 3 );

				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );

			}

			return new Float32BufferAttribute( array, 3 );

		}

		function computeAttributeFromLineData( index, lineData ) {

			const array = [];

			for ( let i = 0, j = 0, l = index.length; i < l; i += 2, j ++ ) {

				vA.fromArray( lineData, j * 3 );

				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );

			}

			return new Float32BufferAttribute( array, 3 );

		}

		function toNonIndexedAttribute( indices, attribute ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				index = indices[ i ] * itemSize;

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new Float32BufferAttribute( array2, itemSize );

		}

		const ab = new Vector3();
		const cb = new Vector3();

		function computeNormalAttribute( index, coord, creaseAngle ) {

			const faces = [];
			const vertexNormals = {};

			// prepare face and raw vertex normals

			for ( let i = 0, l = index.length; i < l; i += 3 ) {

				const a = index[ i ];
				const b = index[ i + 1 ];
				const c = index[ i + 2 ];

				const face = new Face( a, b, c );

				vA.fromArray( coord, a * 3 );
				vB.fromArray( coord, b * 3 );
				vC.fromArray( coord, c * 3 );

				cb.subVectors( vC, vB );
				ab.subVectors( vA, vB );
				cb.cross( ab );

				cb.normalize();

				face.normal.copy( cb );

				if ( vertexNormals[ a ] === undefined ) vertexNormals[ a ] = [];
				if ( vertexNormals[ b ] === undefined ) vertexNormals[ b ] = [];
				if ( vertexNormals[ c ] === undefined ) vertexNormals[ c ] = [];

				vertexNormals[ a ].push( face.normal );
				vertexNormals[ b ].push( face.normal );
				vertexNormals[ c ].push( face.normal );

				faces.push( face );

			}

			// compute vertex normals and build final geometry

			const normals = [];

			for ( let i = 0, l = faces.length; i < l; i ++ ) {

				const face = faces[ i ];

				const nA = weightedNormal( vertexNormals[ face.a ], face.normal, creaseAngle );
				const nB = weightedNormal( vertexNormals[ face.b ], face.normal, creaseAngle );
				const nC = weightedNormal( vertexNormals[ face.c ], face.normal, creaseAngle );

				vA.fromArray( coord, face.a * 3 );
				vB.fromArray( coord, face.b * 3 );
				vC.fromArray( coord, face.c * 3 );

				normals.push( nA.x, nA.y, nA.z );
				normals.push( nB.x, nB.y, nB.z );
				normals.push( nC.x, nC.y, nC.z );

			}

			return new Float32BufferAttribute( normals, 3 );

		}

		function weightedNormal( normals, vector, creaseAngle ) {

			const normal = new Vector3();

			if ( creaseAngle === 0 ) {

				normal.copy( vector );

			} else {

				for ( let i = 0, l = normals.length; i < l; i ++ ) {

					if ( normals[ i ].angleTo( vector ) < creaseAngle ) {

						normal.add( normals[ i ] );

					}

				}

			}

			return normal.normalize();

		}

		function toColorArray( colors ) {

			const array = [];

			for ( let i = 0, l = colors.length; i < l; i += 3 ) {

				array.push( new Color( colors[ i ], colors[ i + 1 ], colors[ i + 2 ] ) );

			}

			return array;

		}

		function convertColorsToLinearSRGB( attribute ) {

			const color = new Color();

			for ( let i = 0; i < attribute.count; i ++ ) {

				color.fromBufferAttribute( attribute, i );

				ColorManagement.colorSpaceToWorking( color, SRGBColorSpace );

				attribute.setXYZ( i, color.r, color.g, color.b );

			}

		}

		/**
		 * Vertically paints the faces interpolating between the
		 * specified colors at the specified angels. This is used for the Background
		 * node, but could be applied to other nodes with multiple faces as well.
		 *
		 * When used with the Background node, default is directionIsDown is true if
		 * interpolating the skyColor down from the Zenith. When interpolating up from
		 * the Nadir i.e. interpolating the groundColor, the directionIsDown is false.
		 *
		 * The first angle is never specified, it is the Zenith (0 rad). Angles are specified
		 * in radians. The geometry is thought a sphere, but could be anything. The color interpolation
		 * is linear along the Y axis in any case.
		 *
		 * You must specify one more color than you have angles at the beginning of the colors array.
		 * This is the color of the Zenith (the top of the shape).
		 *
		 * @param {BufferGeometry} geometry
		 * @param {number} radius
		 * @param {array} angles
		 * @param {array} colors
		 * @param {boolean} topDown - Whether to work top down or bottom up.
		 */
		function paintFaces( geometry, radius, angles, colors, topDown ) {

			// compute threshold values

			const thresholds = [];
			const startAngle = ( topDown === true ) ? 0 : Math.PI;

			for ( let i = 0, l = colors.length; i < l; i ++ ) {

				let angle = ( i === 0 ) ? 0 : angles[ i - 1 ];
				angle = ( topDown === true ) ? angle : ( startAngle - angle );

				const point = new Vector3();
				point.setFromSphericalCoords( radius, angle, 0 );

				thresholds.push( point );

			}

			// generate vertex colors

			const indices = geometry.index;
			const positionAttribute = geometry.attributes.position;
			const colorAttribute = new BufferAttribute( new Float32Array( geometry.attributes.position.count * 3 ), 3 );

			const position = new Vector3();
			const color = new Color();

			for ( let i = 0; i < indices.count; i ++ ) {

				const index = indices.getX( i );
				position.fromBufferAttribute( positionAttribute, index );

				let thresholdIndexA, thresholdIndexB;
				let t = 1;

				for ( let j = 1; j < thresholds.length; j ++ ) {

					thresholdIndexA = j - 1;
					thresholdIndexB = j;

					const thresholdA = thresholds[ thresholdIndexA ];
					const thresholdB = thresholds[ thresholdIndexB ];

					if ( topDown === true ) {

						// interpolation for sky color

						if ( position.y <= thresholdA.y && position.y > thresholdB.y ) {

							t = Math.abs( thresholdA.y - position.y ) / Math.abs( thresholdA.y - thresholdB.y );

							break;

						}

					} else {

						// interpolation for ground color

						if ( position.y >= thresholdA.y && position.y < thresholdB.y ) {

							t = Math.abs( thresholdA.y - position.y ) / Math.abs( thresholdA.y - thresholdB.y );

							break;

						}

					}

				}

				const colorA = colors[ thresholdIndexA ];
				const colorB = colors[ thresholdIndexB ];

				color.copy( colorA ).lerp( colorB, t );

				ColorManagement.colorSpaceToWorking( color, SRGBColorSpace );

				colorAttribute.setXYZ( index, color.r, color.g, color.b );

			}

			geometry.setAttribute( 'color', colorAttribute );

		}

		//

		const textureLoader = new TextureLoader( this.manager );
		textureLoader.setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		// check version (only 2.0 is supported)

		if ( data.indexOf( '#VRML V2.0' ) === - 1 ) {

			throw Error( 'THREE.VRMLLexer: Version of VRML asset not supported.' );

		}

		// create JSON representing the tree structure of the VRML asset

		const tree = generateVRMLTree( data );

		// parse the tree structure to a three.js scene

		const scene = parseTree( tree );

		return scene;

	}
```
</details>

### `generateVRMLTree(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `createTokens`
- `createVisitor`
- `parser.getBaseCstVisitorConstructor`
- `lexer.lex`
- `parser.vrml`
- `console.error`
- `Error`
- `visitor.visit`

**Internal Comments:**
```
// create lexer, parser and visitor (x2)
// lexing (x2)
// parsing (x2)
// actions (x2)
```

<details><summary>Code</summary>

```typescript
function generateVRMLTree( data ) {

			// create lexer, parser and visitor

			const tokenData = createTokens();

			const lexer = new VRMLLexer( tokenData.tokens );
			const parser = new VRMLParser( tokenData.tokenVocabulary );
			const visitor = createVisitor( parser.getBaseCstVisitorConstructor() );

			// lexing

			const lexingResult = lexer.lex( data );
			parser.input = lexingResult.tokens;

			// parsing

			const cstOutput = parser.vrml();

			if ( parser.errors.length > 0 ) {

				console.error( parser.errors );

				throw Error( 'THREE.VRMLLoader: Parsing errors detected.' );

			}

			// actions

			const ast = visitor.visit( cstOutput );

			return ast;

		}
```
</details>

### `createTokens(): { tokens: any[]; tokenVocabulary: {}; }`

**Returns:** `{ tokens: any[]; tokenVocabulary: {}; }`

**Calls:**

- `createToken`
- `nodeTypes.join`

**Internal Comments:**
```
// from http://gun.teipir.gr/VRML-amgem/spec/part1/concepts.html#SyntaxBasics (x2)
// from http://gun.teipir.gr/VRML-amgem/spec/part1/nodesRef.html (x2)
// (x4)
// commas, blanks, tabs, newlines and carriage returns are whitespace characters wherever they appear outside of string fields (x2)
// keywords appear before the Identifier
// the Identifier must appear after the keywords because all keywords are valid identifiers
```

<details><summary>Code</summary>

```typescript
function createTokens() {

			const createToken = chevrotain.createToken;

			// from http://gun.teipir.gr/VRML-amgem/spec/part1/concepts.html#SyntaxBasics

			const RouteIdentifier = createToken( { name: 'RouteIdentifier', pattern: /[^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d][^\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]*[\.][^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d][^\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]*/ } );
			const Identifier = createToken( { name: 'Identifier', pattern: /[^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]([^\0-\x20\x22\x27\x23\x2b\x2c\x2e\x5b\x5d\x5c\x7b\x7d])*/, longer_alt: RouteIdentifier } );

			// from http://gun.teipir.gr/VRML-amgem/spec/part1/nodesRef.html

			const nodeTypes = [
				'Anchor', 'Billboard', 'Collision', 'Group', 'Transform', // grouping nodes
				'Inline', 'LOD', 'Switch', // special groups
				'AudioClip', 'DirectionalLight', 'PointLight', 'Script', 'Shape', 'Sound', 'SpotLight', 'WorldInfo', // common nodes
				'CylinderSensor', 'PlaneSensor', 'ProximitySensor', 'SphereSensor', 'TimeSensor', 'TouchSensor', 'VisibilitySensor', // sensors
				'Box', 'Cone', 'Cylinder', 'ElevationGrid', 'Extrusion', 'IndexedFaceSet', 'IndexedLineSet', 'PointSet', 'Sphere', // geometries
				'Color', 'Coordinate', 'Normal', 'TextureCoordinate', // geometric properties
				'Appearance', 'FontStyle', 'ImageTexture', 'Material', 'MovieTexture', 'PixelTexture', 'TextureTransform', // appearance
				'ColorInterpolator', 'CoordinateInterpolator', 'NormalInterpolator', 'OrientationInterpolator', 'PositionInterpolator', 'ScalarInterpolator', // interpolators
				'Background', 'Fog', 'NavigationInfo', 'Viewpoint', // bindable nodes
				'Text' // Text must be placed at the end of the regex so there are no matches for TextureTransform and TextureCoordinate
			];

			//

			const Version = createToken( {
				name: 'Version',
				pattern: /#VRML.*/,
				longer_alt: Identifier
			} );

			const NodeName = createToken( {
				name: 'NodeName',
				pattern: new RegExp( nodeTypes.join( '|' ) ),
				longer_alt: Identifier
			} );

			const DEF = createToken( {
				name: 'DEF',
				pattern: /DEF/,
				longer_alt: Identifier
			} );

			const USE = createToken( {
				name: 'USE',
				pattern: /USE/,
				longer_alt: Identifier
			} );

			const ROUTE = createToken( {
				name: 'ROUTE',
				pattern: /ROUTE/,
				longer_alt: Identifier
			} );

			const TO = createToken( {
				name: 'TO',
				pattern: /TO/,
				longer_alt: Identifier
			} );

			//

			const StringLiteral = createToken( { name: 'StringLiteral', pattern: /"(?:[^\\"\n\r]|\\[bfnrtv"\\/]|\\u[0-9a-fA-F][0-9a-fA-F][0-9a-fA-F][0-9a-fA-F])*"/ } );
			const HexLiteral = createToken( { name: 'HexLiteral', pattern: /0[xX][0-9a-fA-F]+/ } );
			const NumberLiteral = createToken( { name: 'NumberLiteral', pattern: /[-+]?[0-9]*\.?[0-9]+([eE][-+]?[0-9]+)?/ } );
			const TrueLiteral = createToken( { name: 'TrueLiteral', pattern: /TRUE/ } );
			const FalseLiteral = createToken( { name: 'FalseLiteral', pattern: /FALSE/ } );
			const NullLiteral = createToken( { name: 'NullLiteral', pattern: /NULL/ } );
			const LSquare = createToken( { name: 'LSquare', pattern: /\[/ } );
			const RSquare = createToken( { name: 'RSquare', pattern: /]/ } );
			const LCurly = createToken( { name: 'LCurly', pattern: /{/ } );
			const RCurly = createToken( { name: 'RCurly', pattern: /}/ } );
			const Comment = createToken( {
				name: 'Comment',
				pattern: /#.*/,
				group: chevrotain.Lexer.SKIPPED
			} );

			// commas, blanks, tabs, newlines and carriage returns are whitespace characters wherever they appear outside of string fields

			const WhiteSpace = createToken( {
				name: 'WhiteSpace',
				pattern: /[ ,\s]/,
				group: chevrotain.Lexer.SKIPPED
			} );

			const tokens = [
				WhiteSpace,
				// keywords appear before the Identifier
				NodeName,
				DEF,
				USE,
				ROUTE,
				TO,
				TrueLiteral,
				FalseLiteral,
				NullLiteral,
				// the Identifier must appear after the keywords because all keywords are valid identifiers
				Version,
				Identifier,
				RouteIdentifier,
				StringLiteral,
				HexLiteral,
				NumberLiteral,
				LSquare,
				RSquare,
				LCurly,
				RCurly,
				Comment
			];

			const tokenVocabulary = {};

			for ( let i = 0, l = tokens.length; i < l; i ++ ) {

				const token = tokens[ i ];

				tokenVocabulary[ token.name ] = token;

			}

			return { tokens: tokens, tokenVocabulary: tokenVocabulary };

		}
```
</details>

### `createVisitor(BaseVRMLVisitor: any): VRMLToASTVisitor`

**Parameters:**

- **`BaseVRMLVisitor`** `any`

**Returns:** `VRMLToASTVisitor`

**Calls:**

- `complex_call_7846`
- `this.validateVisitor`
- `this.visit`
- `data.nodes.push`
- `data.routes.push`
- `data.fields.push`
- `processField`
- `field.values.push`
- `scope.visit`
- `stringLiteral.image.replace`
- `parseFloat`
- `ctx.NullLiteral.forEach`

**Internal Comments:**
```
// the visitor is created dynamically based on the given base class
// DEF
// SFValue
// MFValue
```

<details><summary>Code</summary>

```typescript
function createVisitor( BaseVRMLVisitor ) {

			// the visitor is created dynamically based on the given base class

			class VRMLToASTVisitor extends BaseVRMLVisitor {

				constructor() {

					super();

					this.validateVisitor();

				}

				vrml( ctx ) {

					const data = {
						version: this.visit( ctx.version ),
						nodes: [],
						routes: []
					};

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						data.nodes.push( this.visit( node ) );

					}

					if ( ctx.route ) {

						for ( let i = 0, l = ctx.route.length; i < l; i ++ ) {

							const route = ctx.route[ i ];

							data.routes.push( this.visit( route ) );

						}

					}

					return data;

				}

				version( ctx ) {

					return ctx.Version[ 0 ].image;

				}

				node( ctx ) {

					const data = {
						name: ctx.NodeName[ 0 ].image,
						fields: []
					};

					if ( ctx.field ) {

						for ( let i = 0, l = ctx.field.length; i < l; i ++ ) {

							const field = ctx.field[ i ];

							data.fields.push( this.visit( field ) );

						}

					}

					// DEF

					if ( ctx.def ) {

						data.DEF = this.visit( ctx.def[ 0 ] );

					}

					return data;

				}

				field( ctx ) {

					const data = {
						name: ctx.Identifier[ 0 ].image,
						type: null,
						values: null
					};

					let result;

					// SFValue

					if ( ctx.singleFieldValue ) {

						result = this.visit( ctx.singleFieldValue[ 0 ] );

					}

					// MFValue

					if ( ctx.multiFieldValue ) {

						result = this.visit( ctx.multiFieldValue[ 0 ] );

					}

					data.type = result.type;
					data.values = result.values;

					return data;

				}

				def( ctx ) {

					return ( ctx.Identifier || ctx.NodeName )[ 0 ].image;

				}

				use( ctx ) {

					return { USE: ( ctx.Identifier || ctx.NodeName )[ 0 ].image };

				}

				singleFieldValue( ctx ) {

					return processField( this, ctx );

				}

				multiFieldValue( ctx ) {

					return processField( this, ctx );

				}

				route( ctx ) {

					const data = {
						FROM: ctx.RouteIdentifier[ 0 ].image,
						TO: ctx.RouteIdentifier[ 1 ].image
					};

					return data;

				}

			}

			function processField( scope, ctx ) {

				const field = {
					type: null,
					values: []
				};

				if ( ctx.node ) {

					field.type = 'node';

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						field.values.push( scope.visit( node ) );

					}

				}

				if ( ctx.use ) {

					field.type = 'use';

					for ( let i = 0, l = ctx.use.length; i < l; i ++ ) {

						const use = ctx.use[ i ];

						field.values.push( scope.visit( use ) );

					}

				}

				if ( ctx.StringLiteral ) {

					field.type = 'string';

					for ( let i = 0, l = ctx.StringLiteral.length; i < l; i ++ ) {

						const stringLiteral = ctx.StringLiteral[ i ];

						field.values.push( stringLiteral.image.replace( /'|"/g, '' ) );

					}

				}

				if ( ctx.NumberLiteral ) {

					field.type = 'number';

					for ( let i = 0, l = ctx.NumberLiteral.length; i < l; i ++ ) {

						const numberLiteral = ctx.NumberLiteral[ i ];

						field.values.push( parseFloat( numberLiteral.image ) );

					}

				}

				if ( ctx.HexLiteral ) {

					field.type = 'hex';

					for ( let i = 0, l = ctx.HexLiteral.length; i < l; i ++ ) {

						const hexLiteral = ctx.HexLiteral[ i ];

						field.values.push( hexLiteral.image );

					}

				}

				if ( ctx.TrueLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.TrueLiteral.length; i < l; i ++ ) {

						const trueLiteral = ctx.TrueLiteral[ i ];

						if ( trueLiteral.image === 'TRUE' ) field.values.push( true );

					}

				}

				if ( ctx.FalseLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.FalseLiteral.length; i < l; i ++ ) {

						const falseLiteral = ctx.FalseLiteral[ i ];

						if ( falseLiteral.image === 'FALSE' ) field.values.push( false );

					}

				}

				if ( ctx.NullLiteral ) {

					field.type = 'null';

					ctx.NullLiteral.forEach( function () {

						field.values.push( null );

					} );

				}

				return field;

			}

			return new VRMLToASTVisitor();

		}
```
</details>

### `VRMLToASTVisitor.vrml(ctx: any): { version: any; nodes: any[]; routes: any[]; }`

**Parameters:**

- **`ctx`** `any`

**Returns:** `{ version: any; nodes: any[]; routes: any[]; }`

**Calls:**

- `this.visit`
- `data.nodes.push`
- `data.routes.push`

<details><summary>Code</summary>

```typescript
vrml( ctx ) {

					const data = {
						version: this.visit( ctx.version ),
						nodes: [],
						routes: []
					};

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						data.nodes.push( this.visit( node ) );

					}

					if ( ctx.route ) {

						for ( let i = 0, l = ctx.route.length; i < l; i ++ ) {

							const route = ctx.route[ i ];

							data.routes.push( this.visit( route ) );

						}

					}

					return data;

				}
```
</details>

### `VRMLToASTVisitor.version(ctx: any): any`

**Parameters:**

- **`ctx`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
version( ctx ) {

					return ctx.Version[ 0 ].image;

				}
```
</details>

### `VRMLToASTVisitor.node(ctx: any): { name: any; fields: any[]; }`

**Parameters:**

- **`ctx`** `any`

**Returns:** `{ name: any; fields: any[]; }`

**Calls:**

- `data.fields.push`
- `this.visit`

**Internal Comments:**
```
// DEF
```

<details><summary>Code</summary>

```typescript
node( ctx ) {

					const data = {
						name: ctx.NodeName[ 0 ].image,
						fields: []
					};

					if ( ctx.field ) {

						for ( let i = 0, l = ctx.field.length; i < l; i ++ ) {

							const field = ctx.field[ i ];

							data.fields.push( this.visit( field ) );

						}

					}

					// DEF

					if ( ctx.def ) {

						data.DEF = this.visit( ctx.def[ 0 ] );

					}

					return data;

				}
```
</details>

### `VRMLToASTVisitor.field(ctx: any): { name: any; type: any; values: any; }`

**Parameters:**

- **`ctx`** `any`

**Returns:** `{ name: any; type: any; values: any; }`

**Calls:**

- `this.visit`

**Internal Comments:**
```
// SFValue
// MFValue
```

<details><summary>Code</summary>

```typescript
field( ctx ) {

					const data = {
						name: ctx.Identifier[ 0 ].image,
						type: null,
						values: null
					};

					let result;

					// SFValue

					if ( ctx.singleFieldValue ) {

						result = this.visit( ctx.singleFieldValue[ 0 ] );

					}

					// MFValue

					if ( ctx.multiFieldValue ) {

						result = this.visit( ctx.multiFieldValue[ 0 ] );

					}

					data.type = result.type;
					data.values = result.values;

					return data;

				}
```
</details>

### `VRMLToASTVisitor.def(ctx: any): any`

**Parameters:**

- **`ctx`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
def( ctx ) {

					return ( ctx.Identifier || ctx.NodeName )[ 0 ].image;

				}
```
</details>

### `VRMLToASTVisitor.use(ctx: any): { USE: any; }`

**Parameters:**

- **`ctx`** `any`

**Returns:** `{ USE: any; }`

<details><summary>Code</summary>

```typescript
use( ctx ) {

					return { USE: ( ctx.Identifier || ctx.NodeName )[ 0 ].image };

				}
```
</details>

### `VRMLToASTVisitor.singleFieldValue(ctx: any): { type: any; values: any[]; }`

**Parameters:**

- **`ctx`** `any`

**Returns:** `{ type: any; values: any[]; }`

**Calls:**

- `processField`

<details><summary>Code</summary>

```typescript
singleFieldValue( ctx ) {

					return processField( this, ctx );

				}
```
</details>

### `VRMLToASTVisitor.multiFieldValue(ctx: any): { type: any; values: any[]; }`

**Parameters:**

- **`ctx`** `any`

**Returns:** `{ type: any; values: any[]; }`

**Calls:**

- `processField`

<details><summary>Code</summary>

```typescript
multiFieldValue( ctx ) {

					return processField( this, ctx );

				}
```
</details>

### `VRMLToASTVisitor.route(ctx: any): { FROM: any; TO: any; }`

**Parameters:**

- **`ctx`** `any`

**Returns:** `{ FROM: any; TO: any; }`

<details><summary>Code</summary>

```typescript
route( ctx ) {

					const data = {
						FROM: ctx.RouteIdentifier[ 0 ].image,
						TO: ctx.RouteIdentifier[ 1 ].image
					};

					return data;

				}
```
</details>

### `processField(scope: any, ctx: any): { type: any; values: any[]; }`

**Parameters:**

- **`scope`** `any`
- **`ctx`** `any`

**Returns:** `{ type: any; values: any[]; }`

**Calls:**

- `field.values.push`
- `scope.visit`
- `stringLiteral.image.replace`
- `parseFloat`
- `ctx.NullLiteral.forEach`

<details><summary>Code</summary>

```typescript
function processField( scope, ctx ) {

				const field = {
					type: null,
					values: []
				};

				if ( ctx.node ) {

					field.type = 'node';

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						field.values.push( scope.visit( node ) );

					}

				}

				if ( ctx.use ) {

					field.type = 'use';

					for ( let i = 0, l = ctx.use.length; i < l; i ++ ) {

						const use = ctx.use[ i ];

						field.values.push( scope.visit( use ) );

					}

				}

				if ( ctx.StringLiteral ) {

					field.type = 'string';

					for ( let i = 0, l = ctx.StringLiteral.length; i < l; i ++ ) {

						const stringLiteral = ctx.StringLiteral[ i ];

						field.values.push( stringLiteral.image.replace( /'|"/g, '' ) );

					}

				}

				if ( ctx.NumberLiteral ) {

					field.type = 'number';

					for ( let i = 0, l = ctx.NumberLiteral.length; i < l; i ++ ) {

						const numberLiteral = ctx.NumberLiteral[ i ];

						field.values.push( parseFloat( numberLiteral.image ) );

					}

				}

				if ( ctx.HexLiteral ) {

					field.type = 'hex';

					for ( let i = 0, l = ctx.HexLiteral.length; i < l; i ++ ) {

						const hexLiteral = ctx.HexLiteral[ i ];

						field.values.push( hexLiteral.image );

					}

				}

				if ( ctx.TrueLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.TrueLiteral.length; i < l; i ++ ) {

						const trueLiteral = ctx.TrueLiteral[ i ];

						if ( trueLiteral.image === 'TRUE' ) field.values.push( true );

					}

				}

				if ( ctx.FalseLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.FalseLiteral.length; i < l; i ++ ) {

						const falseLiteral = ctx.FalseLiteral[ i ];

						if ( falseLiteral.image === 'FALSE' ) field.values.push( false );

					}

				}

				if ( ctx.NullLiteral ) {

					field.type = 'null';

					ctx.NullLiteral.forEach( function () {

						field.values.push( null );

					} );

				}

				return field;

			}
```
</details>

### `parseTree(tree: any): any`

**Parameters:**

- **`tree`** `any`

**Returns:** `any`

**Calls:**

- `buildNodeMap`
- `getNode`
- `scene.add`

**Internal Comments:**
```
// console.log( JSON.stringify( tree, null, 2 ) ); (x2)
// first iteration: build nodemap based on DEF statements
// second iteration: build nodes
```

<details><summary>Code</summary>

```typescript
function parseTree( tree ) {

			// console.log( JSON.stringify( tree, null, 2 ) );

			const nodes = tree.nodes;
			const scene = new Scene();

			// first iteration: build nodemap based on DEF statements

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				const node = nodes[ i ];

				buildNodeMap( node );

			}

			// second iteration: build nodes

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				const node = nodes[ i ];
				const object = getNode( node );

				if ( object instanceof Object3D ) scene.add( object );

				if ( node.name === 'WorldInfo' ) scene.userData.worldInfo = object;

			}

			return scene;

		}
```
</details>

### `buildNodeMap(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `buildNodeMap`

<details><summary>Code</summary>

```typescript
function buildNodeMap( node ) {

			if ( node.DEF ) {

				nodeMap[ node.DEF ] = node;

			}

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];

				if ( field.type === 'node' ) {

					const fieldValues = field.values;

					for ( let j = 0, jl = fieldValues.length; j < jl; j ++ ) {

						buildNodeMap( fieldValues[ j ] );

					}

				}


			}

		}
```
</details>

### `getNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `resolveUSE`
- `buildNode`

**Internal Comments:**
```
// handle case where a node refers to a different one
```

<details><summary>Code</summary>

```typescript
function getNode( node ) {

			// handle case where a node refers to a different one

			if ( node.USE ) {

				return resolveUSE( node.USE );

			}

			if ( node.build !== undefined ) return node.build;

			node.build = buildNode( node );

			return node.build;

		}
```
</details>

### `buildNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `buildGroupingNode`
- `buildBackgroundNode`
- `buildShapeNode`
- `buildAppearanceNode`
- `buildMaterialNode`
- `buildImageTextureNode`
- `buildPixelTextureNode`
- `buildTextureTransformNode`
- `buildIndexedFaceSetNode`
- `buildIndexedLineSetNode`
- `buildPointSetNode`
- `buildBoxNode`
- `buildConeNode`
- `buildCylinderNode`
- `buildSphereNode`
- `buildElevationGridNode`
- `buildExtrusionNode`
- `buildGeometricNode`
- `buildWorldInfoNode`
- `console.warn`
- `build.hasOwnProperty`

**Internal Comments:**
```
// node not supported yet
```

<details><summary>Code</summary>

```typescript
function buildNode( node ) {

			const nodeName = node.name;
			let build;

			switch ( nodeName ) {

				case 'Anchor':
				case 'Group':
				case 'Transform':
				case 'Collision':
					build = buildGroupingNode( node );
					break;

				case 'Background':
					build = buildBackgroundNode( node );
					break;

				case 'Shape':
					build = buildShapeNode( node );
					break;

				case 'Appearance':
					build = buildAppearanceNode( node );
					break;

				case 'Material':
					build = buildMaterialNode( node );
					break;

				case 'ImageTexture':
					build = buildImageTextureNode( node );
					break;

				case 'PixelTexture':
					build = buildPixelTextureNode( node );
					break;

				case 'TextureTransform':
					build = buildTextureTransformNode( node );
					break;

				case 'IndexedFaceSet':
					build = buildIndexedFaceSetNode( node );
					break;

				case 'IndexedLineSet':
					build = buildIndexedLineSetNode( node );
					break;

				case 'PointSet':
					build = buildPointSetNode( node );
					break;

				case 'Box':
					build = buildBoxNode( node );
					break;

				case 'Cone':
					build = buildConeNode( node );
					break;

				case 'Cylinder':
					build = buildCylinderNode( node );
					break;

				case 'Sphere':
					build = buildSphereNode( node );
					break;

				case 'ElevationGrid':
					build = buildElevationGridNode( node );
					break;

				case 'Extrusion':
					build = buildExtrusionNode( node );
					break;

				case 'Color':
				case 'Coordinate':
				case 'Normal':
				case 'TextureCoordinate':
					build = buildGeometricNode( node );
					break;

				case 'WorldInfo':
					build = buildWorldInfoNode( node );
					break;

				case 'Billboard':

				case 'Inline':
				case 'LOD':
				case 'Switch':

				case 'AudioClip':
				case 'DirectionalLight':
				case 'PointLight':
				case 'Script':
				case 'Sound':
				case 'SpotLight':

				case 'CylinderSensor':
				case 'PlaneSensor':
				case 'ProximitySensor':
				case 'SphereSensor':
				case 'TimeSensor':
				case 'TouchSensor':
				case 'VisibilitySensor':

				case 'Text':

				case 'FontStyle':
				case 'MovieTexture':

				case 'ColorInterpolator':
				case 'CoordinateInterpolator':
				case 'NormalInterpolator':
				case 'OrientationInterpolator':
				case 'PositionInterpolator':
				case 'ScalarInterpolator':

				case 'Fog':
				case 'NavigationInfo':
				case 'Viewpoint':
					// node not supported yet
					break;

				default:
					console.warn( 'THREE.VRMLLoader: Unknown node:', nodeName );
					break;

			}

			if ( build !== undefined && node.DEF !== undefined && build.hasOwnProperty( 'name' ) === true ) {

				build.name = node.DEF;

			}

			return build;

		}
```
</details>

### `buildGroupingNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `parseFieldChildren`
- `new Vector3( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] ).normalize`
- `object.quaternion.setFromAxisAngle`
- `object.scale.set`
- `object.position.set`
- `console.warn`

**Internal Comments:**
```
// (x2)
// field not supported (x9)
```

<details><summary>Code</summary>

```typescript
function buildGroupingNode( node ) {

			const object = new Group();

			//

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bboxCenter':
						// field not supported
						break;

					case 'bboxSize':
						// field not supported
						break;

					case 'center':
						// field not supported
						break;

					case 'children':
						parseFieldChildren( fieldValues, object );
						break;

					case 'description':
						// field not supported
						break;

					case 'collide':
						// field not supported
						break;

					case 'parameter':
						// field not supported
						break;

					case 'rotation':
						const axis = new Vector3( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] ).normalize();
						const angle = fieldValues[ 3 ];
						object.quaternion.setFromAxisAngle( axis, angle );
						break;

					case 'scale':
						object.scale.set( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] );
						break;

					case 'scaleOrientation':
						// field not supported
						break;

					case 'translation':
						object.position.set( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] );
						break;

					case 'proxy':
						// field not supported
						break;

					case 'url':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return object;

		}
```
</details>

### `buildBackgroundNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`
- `paintFaces`
- `toColorArray`
- `skyMaterial.color.setRGB`
- `group.add`

**Internal Comments:**
```
// field not supported (x6)
// sky
// ground
// render background group first (x4)
```

<details><summary>Code</summary>

```typescript
function buildBackgroundNode( node ) {

			const group = new Group();

			let groundAngle, groundColor;
			let skyAngle, skyColor;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'groundAngle':
						groundAngle = fieldValues;
						break;

					case 'groundColor':
						groundColor = fieldValues;
						break;

					case 'backUrl':
						// field not supported
						break;

					case 'bottomUrl':
						// field not supported
						break;

					case 'frontUrl':
						// field not supported
						break;

					case 'leftUrl':
						// field not supported
						break;

					case 'rightUrl':
						// field not supported
						break;

					case 'topUrl':
						// field not supported
						break;

					case 'skyAngle':
						skyAngle = fieldValues;
						break;

					case 'skyColor':
						skyColor = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const radius = 10000;

			// sky

			if ( skyColor ) {

				const skyGeometry = new SphereGeometry( radius, 32, 16 );
				const skyMaterial = new MeshBasicMaterial( { fog: false, side: BackSide, depthWrite: false, depthTest: false } );

				if ( skyColor.length > 3 ) {

					paintFaces( skyGeometry, radius, skyAngle, toColorArray( skyColor ), true );
					skyMaterial.vertexColors = true;

				} else {

					skyMaterial.color.setRGB( skyColor[ 0 ], skyColor[ 1 ], skyColor[ 2 ], SRGBColorSpace );

				}

				const sky = new Mesh( skyGeometry, skyMaterial );
				group.add( sky );

			}

			// ground

			if ( groundColor ) {

				if ( groundColor.length > 0 ) {

					const groundGeometry = new SphereGeometry( radius, 32, 16, 0, 2 * Math.PI, 0.5 * Math.PI, 1.5 * Math.PI );
					const groundMaterial = new MeshBasicMaterial( { fog: false, side: BackSide, vertexColors: true, depthWrite: false, depthTest: false } );

					paintFaces( groundGeometry, radius, groundAngle, toColorArray( groundColor ), false );

					const ground = new Mesh( groundGeometry, groundMaterial );
					group.add( ground );

				}

			}

			// render background group first

			group.renderOrder = - Infinity;

			return group;

		}
```
</details>

### `buildShapeNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `getNode`
- `console.warn`
- `pointsMaterial.color.copy`
- `lineMaterial.color.copy`

**Internal Comments:**
```
// if the appearance field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0) (x2)
// build 3D object (x2)
// if the color field is NULL and there is a material defined for the appearance affecting this PointSet, then use the emissiveColor of the material to draw the points
// if the color field is NULL and there is a material defined for the appearance affecting this IndexedLineSet, then use the emissiveColor of the material to draw the lines
// check "solid" hint (it's placed in the geometry but affects the material)
// check for vertex colors
// if the geometry field is NULL or no vertices are defined the object is not drawn (x4)
```

<details><summary>Code</summary>

```typescript
function buildShapeNode( node ) {

			const fields = node.fields;

			// if the appearance field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0)

			let material = new MeshBasicMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0x000000
			} );
			let geometry;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'appearance':
						if ( fieldValues[ 0 ] !== null ) {

							material = getNode( fieldValues[ 0 ] );

						}

						break;

					case 'geometry':
						if ( fieldValues[ 0 ] !== null ) {

							geometry = getNode( fieldValues[ 0 ] );

						}

						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// build 3D object

			let object;

			if ( geometry && geometry.attributes.position ) {

				const type = geometry._type;

				if ( type === 'points' ) { // points

					const pointsMaterial = new PointsMaterial( {
						name: Loader.DEFAULT_MATERIAL_NAME,
						color: 0xffffff,
						opacity: material.opacity,
						transparent: material.transparent
					} );

					if ( geometry.attributes.color !== undefined ) {

						pointsMaterial.vertexColors = true;

					} else {

						// if the color field is NULL and there is a material defined for the appearance affecting this PointSet, then use the emissiveColor of the material to draw the points

						if ( material.isMeshPhongMaterial ) {

							pointsMaterial.color.copy( material.emissive );

						}

					}

					object = new Points( geometry, pointsMaterial );

				} else if ( type === 'line' ) { // lines

					const lineMaterial = new LineBasicMaterial( {
						name: Loader.DEFAULT_MATERIAL_NAME,
						color: 0xffffff,
						opacity: material.opacity,
						transparent: material.transparent
					} );

					if ( geometry.attributes.color !== undefined ) {

						lineMaterial.vertexColors = true;

					} else {

						// if the color field is NULL and there is a material defined for the appearance affecting this IndexedLineSet, then use the emissiveColor of the material to draw the lines

						if ( material.isMeshPhongMaterial ) {

							lineMaterial.color.copy( material.emissive );

						}

					}

					object = new LineSegments( geometry, lineMaterial );

				} else { // consider meshes

					// check "solid" hint (it's placed in the geometry but affects the material)

					if ( geometry._solid !== undefined ) {

						material.side = ( geometry._solid ) ? FrontSide : DoubleSide;

					}

					// check for vertex colors

					if ( geometry.attributes.color !== undefined ) {

						material.vertexColors = true;

					}

					object = new Mesh( geometry, material );

				}

			} else {

				object = new Object3D();

				// if the geometry field is NULL or no vertices are defined the object is not drawn

				object.visible = false;

			}

			return object;

		}
```
</details>

### `buildAppearanceNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `getNode`
- `material.color.copy`
- `material.emissive.copy`
- `material.specular.copy`
- `console.warn`
- `material.color.set`
- `material.map.center.copy`
- `material.map.repeat.copy`
- `material.map.offset.copy`

**Internal Comments:**
```
// if the material field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0) (x3)
// only apply texture transform data if a texture was defined
// respect VRML lighting model
// apply texture transform
```

<details><summary>Code</summary>

```typescript
function buildAppearanceNode( node ) {

			let material = new MeshPhongMaterial();
			let transformData;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'material':
						if ( fieldValues[ 0 ] !== null ) {

							const materialData = getNode( fieldValues[ 0 ] );

							if ( materialData.diffuseColor ) material.color.copy( materialData.diffuseColor );
							if ( materialData.emissiveColor ) material.emissive.copy( materialData.emissiveColor );
							if ( materialData.shininess ) material.shininess = materialData.shininess;
							if ( materialData.specularColor ) material.specular.copy( materialData.specularColor );
							if ( materialData.transparency ) material.opacity = 1 - materialData.transparency;
							if ( materialData.transparency > 0 ) material.transparent = true;

						} else {

							// if the material field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0)

							material = new MeshBasicMaterial( {
								name: Loader.DEFAULT_MATERIAL_NAME,
								color: 0x000000
							} );

						}

						break;

					case 'texture':
						const textureNode = fieldValues[ 0 ];
						if ( textureNode !== null ) {

							if ( textureNode.name === 'ImageTexture' || textureNode.name === 'PixelTexture' ) {

								material.map = getNode( textureNode );

							} else {

								// MovieTexture not supported yet

							}

						}

						break;

					case 'textureTransform':
						if ( fieldValues[ 0 ] !== null ) {

							transformData = getNode( fieldValues[ 0 ] );

						}

						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// only apply texture transform data if a texture was defined

			if ( material.map ) {

				// respect VRML lighting model

				if ( material.map.__type ) {

					switch ( material.map.__type ) {

						case TEXTURE_TYPE.INTENSITY_ALPHA:
							material.opacity = 1; // ignore transparency
							break;

						case TEXTURE_TYPE.RGB:
							material.color.set( 0xffffff ); // ignore material color
							break;

						case TEXTURE_TYPE.RGBA:
							material.color.set( 0xffffff ); // ignore material color
							material.opacity = 1; // ignore transparency
							break;

						default:

					}

					delete material.map.__type;

				}

				// apply texture transform

				if ( transformData ) {

					material.map.center.copy( transformData.center );
					material.map.rotation = transformData.rotation;
					material.map.repeat.copy( transformData.scale );
					material.map.offset.copy( transformData.translation );

				}

			}

			return material;

		}
```
</details>

### `buildMaterialNode(node: any): { diffuseColor: any; emissiveColor: any; shininess: any; specularColor: any; transparency: any; }`

**Parameters:**

- **`node`** `any`

**Returns:** `{ diffuseColor: any; emissiveColor: any; shininess: any; specularColor: any; transparency: any; }`

**Calls:**

- `new Color().setRGB`
- `console.warn`

**Internal Comments:**
```
// field not supported
```

<details><summary>Code</summary>

```typescript
function buildMaterialNode( node ) {

			const materialData = {};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'ambientIntensity':
						// field not supported
						break;

					case 'diffuseColor':
						materialData.diffuseColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'emissiveColor':
						materialData.emissiveColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'shininess':
						materialData.shininess = fieldValues[ 0 ];
						break;

					case 'specularColor':
						materialData.specularColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'transparency':
						materialData.transparency = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return materialData;

		}
```
</details>

### `parseHexColor(hex: any, textureType: any, color: any): void`

**Parameters:**

- **`hex`** `any`
- **`textureType`** `any`
- **`color`** `any`

**Returns:** `void`

**Calls:**

- `parseInt`
- `hex.substring`

**Internal Comments:**
```
// Intensity texture: A one-component image specifies one-byte hexadecimal or integer values representing the intensity of the image (x3)
// Intensity+Alpha texture: A two-component image specifies the intensity in the first (high) byte and the alpha opacity in the second (low) byte. (x3)
// RGB texture: Pixels in a three-component image specify the red component in the first (high) byte, followed by the green and blue components (x4)
// RGBA texture: Four-component images specify the alpha opacity byte after red/green/blue (x4)
```

<details><summary>Code</summary>

```typescript
function parseHexColor( hex, textureType, color ) {

			let value;

			switch ( textureType ) {

				case TEXTURE_TYPE.INTENSITY:
					// Intensity texture: A one-component image specifies one-byte hexadecimal or integer values representing the intensity of the image
					value = parseInt( hex );
					color.r = value;
					color.g = value;
					color.b = value;
					color.a = 1;
					break;

				case TEXTURE_TYPE.INTENSITY_ALPHA:
					// Intensity+Alpha texture: A two-component image specifies the intensity in the first (high) byte and the alpha opacity in the second (low) byte.
					value = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.r = value;
					color.g = value;
					color.b = value;
					color.a = parseInt( '0x' + hex.substring( 4, 6 ) );
					break;

				case TEXTURE_TYPE.RGB:
					// RGB texture: Pixels in a three-component image specify the red component in the first (high) byte, followed by the green and blue components
					color.r = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.g = parseInt( '0x' + hex.substring( 4, 6 ) );
					color.b = parseInt( '0x' + hex.substring( 6, 8 ) );
					color.a = 1;
					break;

				case TEXTURE_TYPE.RGBA:
					// RGBA texture: Four-component images specify the alpha opacity byte after red/green/blue
					color.r = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.g = parseInt( '0x' + hex.substring( 4, 6 ) );
					color.b = parseInt( '0x' + hex.substring( 6, 8 ) );
					color.a = parseInt( '0x' + hex.substring( 8, 10 ) );
					break;

				default:

			}

		}
```
</details>

### `getTextureType(num_components: any): number`

**Parameters:**

- **`num_components`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function getTextureType( num_components ) {

			let type;

			switch ( num_components ) {

				case 1:
					type = TEXTURE_TYPE.INTENSITY;
					break;

				case 2:
					type = TEXTURE_TYPE.INTENSITY_ALPHA;
					break;

				case 3:
					type = TEXTURE_TYPE.RGB;
					break;

				case 4:
					type = TEXTURE_TYPE.RGBA;
					break;

				default:

			}

			return type;

		}
```
</details>

### `buildPixelTextureNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `getTextureType`
- `parseHexColor`
- `console.warn`

<details><summary>Code</summary>

```typescript
function buildPixelTextureNode( node ) {

			let texture;
			let wrapS = RepeatWrapping;
			let wrapT = RepeatWrapping;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'image':
						const width = fieldValues[ 0 ];
						const height = fieldValues[ 1 ];
						const num_components = fieldValues[ 2 ];

						const textureType = getTextureType( num_components );

						const data = new Uint8Array( 4 * width * height );

						const color = { r: 0, g: 0, b: 0, a: 0 };

						for ( let j = 3, k = 0, jl = fieldValues.length; j < jl; j ++, k ++ ) {

							parseHexColor( fieldValues[ j ], textureType, color );

							const stride = k * 4;

							data[ stride + 0 ] = color.r;
							data[ stride + 1 ] = color.g;
							data[ stride + 2 ] = color.b;
							data[ stride + 3 ] = color.a;

						}

						texture = new DataTexture( data, width, height );
						texture.colorSpace = SRGBColorSpace;
						texture.needsUpdate = true;
						texture.__type = textureType; // needed for material modifications
						break;

					case 'repeatS':
						if ( fieldValues[ 0 ] === false ) wrapS = ClampToEdgeWrapping;
						break;

					case 'repeatT':
						if ( fieldValues[ 0 ] === false ) wrapT = ClampToEdgeWrapping;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( texture ) {

				texture.wrapS = wrapS;
				texture.wrapT = wrapT;

			}

			return texture;

		}
```
</details>

### `buildImageTextureNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `textureLoader.load`
- `console.warn`

<details><summary>Code</summary>

```typescript
function buildImageTextureNode( node ) {

			let texture;
			let wrapS = RepeatWrapping;
			let wrapT = RepeatWrapping;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'url':
						const url = fieldValues[ 0 ];
						if ( url ) texture = textureLoader.load( url );
						break;

					case 'repeatS':
						if ( fieldValues[ 0 ] === false ) wrapS = ClampToEdgeWrapping;
						break;

					case 'repeatT':
						if ( fieldValues[ 0 ] === false ) wrapT = ClampToEdgeWrapping;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( texture ) {

				texture.wrapS = wrapS;
				texture.wrapT = wrapT;
				texture.colorSpace = SRGBColorSpace;

			}

			return texture;

		}
```
</details>

### `buildTextureTransformNode(node: any): { center: any; rotation: any; scale: any; translation: any; }`

**Parameters:**

- **`node`** `any`

**Returns:** `{ center: any; rotation: any; scale: any; translation: any; }`

**Calls:**

- `transformData.center.set`
- `transformData.scale.set`
- `transformData.translation.set`
- `console.warn`

<details><summary>Code</summary>

```typescript
function buildTextureTransformNode( node ) {

			const transformData = {
				center: new Vector2(),
				rotation: new Vector2(),
				scale: new Vector2(),
				translation: new Vector2()
			};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'center':
						transformData.center.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					case 'rotation':
						transformData.rotation = fieldValues[ 0 ];
						break;

					case 'scale':
						transformData.scale.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					case 'translation':
						transformData.translation.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return transformData;

		}
```
</details>

### `buildGeometricNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function buildGeometricNode( node ) {

			return node.fields[ 0 ].values;

		}
```
</details>

### `buildWorldInfoNode(node: any): { title: any; info: any; }`

**Parameters:**

- **`node`** `any`

**Returns:** `{ title: any; info: any; }`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function buildWorldInfoNode( node ) {

			const worldInfo = {};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'title':
						worldInfo.title = fieldValues[ 0 ];
						break;

					case 'info':
						worldInfo.info = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return worldInfo;

		}
```
</details>

### `buildIndexedFaceSetNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `getNode`
- `console.warn`
- `triangulateFaceIndex`
- `computeAttributeFromIndexedData`
- `toNonIndexedAttribute`
- `flattenData`
- `triangulateFaceData`
- `computeAttributeFromFaceData`
- `convertColorsToLinearSRGB`
- `computeNormalAttribute`
- `geometry.setAttribute`

**Internal Comments:**
```
// field not supported
// if the colorIndex field is not empty, then it is used to choose colors for each vertex of the IndexedFaceSet. (x2)
// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node (x3)
// if the colorIndex field is not empty, then they are used to choose one color for each face of the IndexedFaceSet (x2)
// if the colorIndex field is empty, then the color are applied to each face of the IndexedFaceSet in order (x2)
// consider vertex normals
// if the normalIndex field is not empty, then it is used to choose normals for each vertex of the IndexedFaceSet. (x2)
// if the normalIndex field is empty, then the coordIndex field is used to choose normals from the Normal node (x3)
// consider face normals
// if the normalIndex field is not empty, then they are used to choose one normal for each face of the IndexedFaceSet (x2)
// if the normalIndex field is empty, then the normals are applied to each face of the IndexedFaceSet in order (x2)
// if the normal field is NULL, then the loader should automatically generate normals, using creaseAngle to determine if and how normals are smoothed across shared vertices (x3)
// texture coordinates are always defined on vertex level
// if the texCoordIndex field is not empty, then it is used to choose texture coordinates for each vertex of the IndexedFaceSet. (x2)
// if the texCoordIndex field is empty, then the coordIndex array is used to choose texture coordinates from the TextureCoordinate node (x3)
// optional attributes
// "solid" influences the material so let's store it for later use (x4)
```

<details><summary>Code</summary>

```typescript
function buildIndexedFaceSetNode( node ) {

			let color, coord, normal, texCoord;
			let ccw = true, solid = true, creaseAngle = 0;
			let colorIndex, coordIndex, normalIndex, texCoordIndex;
			let colorPerVertex = true, normalPerVertex = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;

					case 'normal':
						const normalNode = fieldValues[ 0 ];

						if ( normalNode !== null ) {

							normal = getNode( normalNode );

						}

						break;

					case 'texCoord':
						const texCoordNode = fieldValues[ 0 ];

						if ( texCoordNode !== null ) {

							texCoord = getNode( texCoordNode );

						}

						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'colorIndex':
						colorIndex = fieldValues;
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'convex':
						// field not supported
						break;

					case 'coordIndex':
						coordIndex = fieldValues;
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'normalIndex':
						normalIndex = fieldValues;
						break;

					case 'normalPerVertex':
						normalPerVertex = fieldValues[ 0 ];
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'texCoordIndex':
						texCoordIndex = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( coordIndex === undefined ) {

				console.warn( 'THREE.VRMLLoader: Missing coordIndex.' );

				return new BufferGeometry(); // handle VRML files with incomplete geometry definition

			}

			const triangulatedCoordIndex = triangulateFaceIndex( coordIndex, ccw );

			let colorAttribute;
			let normalAttribute;
			let uvAttribute;

			if ( color ) {

				if ( colorPerVertex === true ) {

					if ( colorIndex && colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then it is used to choose colors for each vertex of the IndexedFaceSet.

						const triangulatedColorIndex = triangulateFaceIndex( colorIndex, ccw );
						colorAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedColorIndex, color, 3 );

					} else {

						// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node

						colorAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( color, 3 ) );

					}

				} else {

					if ( colorIndex && colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then they are used to choose one color for each face of the IndexedFaceSet

						const flattenFaceColors = flattenData( color, colorIndex );
						const triangulatedFaceColors = triangulateFaceData( flattenFaceColors, coordIndex );
						colorAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceColors );

					} else {

						// if the colorIndex field is empty, then the color are applied to each face of the IndexedFaceSet in order

						const triangulatedFaceColors = triangulateFaceData( color, coordIndex );
						colorAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceColors );


					}

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			if ( normal ) {

				if ( normalPerVertex === true ) {

					// consider vertex normals

					if ( normalIndex && normalIndex.length > 0 ) {

						// if the normalIndex field is not empty, then it is used to choose normals for each vertex of the IndexedFaceSet.

						const triangulatedNormalIndex = triangulateFaceIndex( normalIndex, ccw );
						normalAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedNormalIndex, normal, 3 );

					} else {

						// if the normalIndex field is empty, then the coordIndex field is used to choose normals from the Normal node

						normalAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( normal, 3 ) );

					}

				} else {

					// consider face normals

					if ( normalIndex && normalIndex.length > 0 ) {

						// if the normalIndex field is not empty, then they are used to choose one normal for each face of the IndexedFaceSet

						const flattenFaceNormals = flattenData( normal, normalIndex );
						const triangulatedFaceNormals = triangulateFaceData( flattenFaceNormals, coordIndex );
						normalAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceNormals );

					} else {

						// if the normalIndex field is empty, then the normals are applied to each face of the IndexedFaceSet in order

						const triangulatedFaceNormals = triangulateFaceData( normal, coordIndex );
						normalAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceNormals );

					}

				}

			} else {

				// if the normal field is NULL, then the loader should automatically generate normals, using creaseAngle to determine if and how normals are smoothed across shared vertices

				normalAttribute = computeNormalAttribute( triangulatedCoordIndex, coord, creaseAngle );

			}

			if ( texCoord ) {

				// texture coordinates are always defined on vertex level

				if ( texCoordIndex && texCoordIndex.length > 0 ) {

					// if the texCoordIndex field is not empty, then it is used to choose texture coordinates for each vertex of the IndexedFaceSet.

					const triangulatedTexCoordIndex = triangulateFaceIndex( texCoordIndex, ccw );
					uvAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedTexCoordIndex, texCoord, 2 );


				} else {

					// if the texCoordIndex field is empty, then the coordIndex array is used to choose texture coordinates from the TextureCoordinate node

					uvAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( texCoord, 2 ) );

				}

			}

			const geometry = new BufferGeometry();
			const positionAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( coord, 3 ) );

			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );

			// optional attributes

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );
			if ( uvAttribute ) geometry.setAttribute( 'uv', uvAttribute );

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}
```
</details>

### `buildIndexedLineSetNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `getNode`
- `console.warn`
- `expandLineIndex`
- `computeAttributeFromIndexedData`
- `toNonIndexedAttribute`
- `flattenData`
- `expandLineData`
- `computeAttributeFromLineData`
- `convertColorsToLinearSRGB`
- `geometry.setAttribute`

**Internal Comments:**
```
// build lines (x2)
// if the colorIndex field is not empty, then one color is used for each polyline of the IndexedLineSet. (x2)
// if the colorIndex field is empty, then the colors are applied to each polyline of the IndexedLineSet in order. (x3)
// if the colorIndex field is not empty, then colors are applied to each vertex of the IndexedLineSet (x2)
// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node (x2)
// (x2)
```

<details><summary>Code</summary>

```typescript
function buildIndexedLineSetNode( node ) {

			let color, coord;
			let colorIndex, coordIndex;
			let colorPerVertex = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;

					case 'colorIndex':
						colorIndex = fieldValues;
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'coordIndex':
						coordIndex = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// build lines

			let colorAttribute;

			const expandedLineIndex = expandLineIndex( coordIndex ); // create an index for three.js's linesegment primitive

			if ( color ) {

				if ( colorPerVertex === true ) {

					if ( colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then one color is used for each polyline of the IndexedLineSet.

						const expandedColorIndex = expandLineIndex( colorIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromIndexedData( expandedLineIndex, expandedColorIndex, color, 3 ); // compute data on vertex level

					} else {

						// if the colorIndex field is empty, then the colors are applied to each polyline of the IndexedLineSet in order.

						colorAttribute = toNonIndexedAttribute( expandedLineIndex, new Float32BufferAttribute( color, 3 ) );

					}

				} else {

					if ( colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then colors are applied to each vertex of the IndexedLineSet

						const flattenLineColors = flattenData( color, colorIndex ); // compute colors for each VRML primitive
						const expandedLineColors = expandLineData( flattenLineColors, coordIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromLineData( expandedLineIndex, expandedLineColors ); // compute data on vertex level


					} else {

						// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node

						const expandedLineColors = expandLineData( color, coordIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromLineData( expandedLineIndex, expandedLineColors ); // compute data on vertex level

					}

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			//

			const geometry = new BufferGeometry();

			const positionAttribute = toNonIndexedAttribute( expandedLineIndex, new Float32BufferAttribute( coord, 3 ) );
			geometry.setAttribute( 'position', positionAttribute );

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );

			geometry._type = 'line';

			return geometry;

		}
```
</details>

### `buildPointSetNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `getNode`
- `console.warn`
- `geometry.setAttribute`
- `convertColorsToLinearSRGB`

<details><summary>Code</summary>

```typescript
function buildPointSetNode( node ) {

			let color, coord;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;


					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new BufferGeometry();

			geometry.setAttribute( 'position', new Float32BufferAttribute( coord, 3 ) );

			if ( color ) {

				const colorAttribute = new Float32BufferAttribute( color, 3 );
				convertColorsToLinearSRGB( colorAttribute );

				geometry.setAttribute( 'color', colorAttribute );

			}

			geometry._type = 'points';

			return geometry;

		}
```
</details>

### `buildBoxNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function buildBoxNode( node ) {

			const size = new Vector3( 2, 2, 2 );

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'size':
						size.x = fieldValues[ 0 ];
						size.y = fieldValues[ 1 ];
						size.z = fieldValues[ 2 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new BoxGeometry( size.x, size.y, size.z );

			return geometry;

		}
```
</details>

### `buildConeNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`

**Internal Comments:**
```
// field not supported
```

<details><summary>Code</summary>

```typescript
function buildConeNode( node ) {

			let radius = 1, height = 2, openEnded = false;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bottom':
						openEnded = ! fieldValues[ 0 ];
						break;

					case 'bottomRadius':
						radius = fieldValues[ 0 ];
						break;

					case 'height':
						height = fieldValues[ 0 ];
						break;

					case 'side':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new ConeGeometry( radius, height, 16, 1, openEnded );

			return geometry;

		}
```
</details>

### `buildCylinderNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`

**Internal Comments:**
```
// field not supported (x3)
```

<details><summary>Code</summary>

```typescript
function buildCylinderNode( node ) {

			let radius = 1, height = 2;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bottom':
						// field not supported
						break;

					case 'radius':
						radius = fieldValues[ 0 ];
						break;

					case 'height':
						height = fieldValues[ 0 ];
						break;

					case 'side':
						// field not supported
						break;

					case 'top':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new CylinderGeometry( radius, radius, height, 16, 1 );

			return geometry;

		}
```
</details>

### `buildSphereNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function buildSphereNode( node ) {

			let radius = 1;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'radius':
						radius = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new SphereGeometry( radius, 16, 16 );

			return geometry;

		}
```
</details>

### `buildElevationGridNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `getNode`
- `console.warn`
- `vertices.push`
- `colors.push`
- `normals.push`
- `uvs.push`
- `indices.push`
- `toNonIndexedAttribute`
- `convertColorsToLinearSRGB`
- `computeNormalAttribute`
- `geometry.setAttribute`

**Internal Comments:**
```
// vertex data (x2)
// compute a row major index (x2)
// vertices (x2)
// colors
// normals
// uvs
// indices (x2)
// from https://tecfa.unige.ch/guides/vrml/vrml97/spec/part1/nodesRef.html#ElevationGrid (x2)
// faces
// (x2)
// color attribute
// one color per quad (x4)
// normal attribute
// one normal per quad (x4)
// build geometry (x2)
// "solid" influences the material so let's store it for later use (x4)
```

<details><summary>Code</summary>

```typescript
function buildElevationGridNode( node ) {

			let color;
			let normal;
			let texCoord;
			let height;

			let colorPerVertex = true;
			let normalPerVertex = true;
			let solid = true;
			let ccw = true;
			let creaseAngle = 0;
			let xDimension = 2;
			let zDimension = 2;
			let xSpacing = 1;
			let zSpacing = 1;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'normal':
						const normalNode = fieldValues[ 0 ];

						if ( normalNode !== null ) {

							normal = getNode( normalNode );

						}

						break;

					case 'texCoord':
						const texCoordNode = fieldValues[ 0 ];

						if ( texCoordNode !== null ) {

							texCoord = getNode( texCoordNode );

						}

						break;

					case 'height':
						height = fieldValues;
						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'normalPerVertex':
						normalPerVertex = fieldValues[ 0 ];
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'xDimension':
						xDimension = fieldValues[ 0 ];
						break;

					case 'xSpacing':
						xSpacing = fieldValues[ 0 ];
						break;

					case 'zDimension':
						zDimension = fieldValues[ 0 ];
						break;

					case 'zSpacing':
						zSpacing = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// vertex data

			const vertices = [];
			const normals = [];
			const colors = [];
			const uvs = [];

			for ( let i = 0; i < zDimension; i ++ ) {

				for ( let j = 0; j < xDimension; j ++ ) {

					// compute a row major index

					const index = ( i * xDimension ) + j;

					// vertices

					const x = xSpacing * i;
					const y = height[ index ];
					const z = zSpacing * j;

					vertices.push( x, y, z );

					// colors

					if ( color && colorPerVertex === true ) {

						const r = color[ index * 3 + 0 ];
						const g = color[ index * 3 + 1 ];
						const b = color[ index * 3 + 2 ];

						colors.push( r, g, b );

					}

					// normals

					if ( normal && normalPerVertex === true ) {

						const xn = normal[ index * 3 + 0 ];
						const yn = normal[ index * 3 + 1 ];
						const zn = normal[ index * 3 + 2 ];

						normals.push( xn, yn, zn );

					}

					// uvs

					if ( texCoord ) {

						const s = texCoord[ index * 2 + 0 ];
						const t = texCoord[ index * 2 + 1 ];

						uvs.push( s, t );


					} else {

						uvs.push( i / ( xDimension - 1 ), j / ( zDimension - 1 ) );

					}

				}

			}

			// indices

			const indices = [];

			for ( let i = 0; i < xDimension - 1; i ++ ) {

				for ( let j = 0; j < zDimension - 1; j ++ ) {

					// from https://tecfa.unige.ch/guides/vrml/vrml97/spec/part1/nodesRef.html#ElevationGrid

					const a = i + j * xDimension;
					const b = i + ( j + 1 ) * xDimension;
					const c = ( i + 1 ) + ( j + 1 ) * xDimension;
					const d = ( i + 1 ) + j * xDimension;

					// faces

					if ( ccw === true ) {

						indices.push( a, c, b );
						indices.push( c, a, d );

					} else {

						indices.push( a, b, c );
						indices.push( c, d, a );

					}

				}

			}

			//

			const positionAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( vertices, 3 ) );
			const uvAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( uvs, 2 ) );
			let colorAttribute;
			let normalAttribute;

			// color attribute

			if ( color ) {

				if ( colorPerVertex === false ) {

					for ( let i = 0; i < xDimension - 1; i ++ ) {

						for ( let j = 0; j < zDimension - 1; j ++ ) {

							const index = i + j * ( xDimension - 1 );

							const r = color[ index * 3 + 0 ];
							const g = color[ index * 3 + 1 ];
							const b = color[ index * 3 + 2 ];

							// one color per quad

							colors.push( r, g, b ); colors.push( r, g, b ); colors.push( r, g, b );
							colors.push( r, g, b ); colors.push( r, g, b ); colors.push( r, g, b );

						}

					}

					colorAttribute = new Float32BufferAttribute( colors, 3 );

				} else {

					colorAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( colors, 3 ) );

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			// normal attribute

			if ( normal ) {

				if ( normalPerVertex === false ) {

					for ( let i = 0; i < xDimension - 1; i ++ ) {

						for ( let j = 0; j < zDimension - 1; j ++ ) {

							const index = i + j * ( xDimension - 1 );

							const xn = normal[ index * 3 + 0 ];
							const yn = normal[ index * 3 + 1 ];
							const zn = normal[ index * 3 + 2 ];

							// one normal per quad

							normals.push( xn, yn, zn ); normals.push( xn, yn, zn ); normals.push( xn, yn, zn );
							normals.push( xn, yn, zn ); normals.push( xn, yn, zn ); normals.push( xn, yn, zn );

						}

					}

					normalAttribute = new Float32BufferAttribute( normals, 3 );

				} else {

					normalAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( normals, 3 ) );

				}

			} else {

				normalAttribute = computeNormalAttribute( indices, vertices, creaseAngle );

			}

			// build geometry

			const geometry = new BufferGeometry();
			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );
			geometry.setAttribute( 'uv', uvAttribute );

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}
```
</details>

### `buildExtrusionNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`
- `spineVector.fromArray`
- `vertex.multiply`
- `quaternion.setFromAxisAngle`
- `vertex.applyQuaternion`
- `vertex.add`
- `vertices.push`
- `indices.push`
- `contour.push`
- `ShapeUtils.triangulateShape`
- `capIndices.push`
- `toNonIndexedAttribute`
- `computeNormalAttribute`
- `geometry.setAttribute`

**Internal Comments:**
```
// field not supported
// vertices (x2)
// scale (x4)
// rotate (x4)
// translate (x4)
// indices (x2)
// triangulate cap
// begin cap
// end cap
// no uvs yet (x4)
// "solid" influences the material so let's store it for later use (x4)
```

<details><summary>Code</summary>

```typescript
function buildExtrusionNode( node ) {

			let crossSection = [ 1, 1, 1, - 1, - 1, - 1, - 1, 1, 1, 1 ];
			let spine = [ 0, 0, 0, 0, 1, 0 ];
			let scale;
			let orientation;

			let beginCap = true;
			let ccw = true;
			let creaseAngle = 0;
			let endCap = true;
			let solid = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'beginCap':
						beginCap = fieldValues[ 0 ];
						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'convex':
						// field not supported
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'crossSection':
						crossSection = fieldValues;
						break;

					case 'endCap':
						endCap = fieldValues[ 0 ];
						break;

					case 'orientation':
						orientation = fieldValues;
						break;

					case 'scale':
						scale = fieldValues;
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'spine':
						spine = fieldValues; // only extrusion along the Y-axis are supported so far
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const crossSectionClosed = ( crossSection[ 0 ] === crossSection[ crossSection.length - 2 ] && crossSection[ 1 ] === crossSection[ crossSection.length - 1 ] );

			// vertices

			const vertices = [];
			const spineVector = new Vector3();
			const scaling = new Vector3();

			const axis = new Vector3();
			const vertex = new Vector3();
			const quaternion = new Quaternion();

			for ( let i = 0, j = 0, o = 0, il = spine.length; i < il; i += 3, j += 2, o += 4 ) {

				spineVector.fromArray( spine, i );

				scaling.x = scale ? scale[ j + 0 ] : 1;
				scaling.y = 1;
				scaling.z = scale ? scale[ j + 1 ] : 1;

				axis.x = orientation ? orientation[ o + 0 ] : 0;
				axis.y = orientation ? orientation[ o + 1 ] : 0;
				axis.z = orientation ? orientation[ o + 2 ] : 1;
				const angle = orientation ? orientation[ o + 3 ] : 0;

				for ( let k = 0, kl = crossSection.length; k < kl; k += 2 ) {

					vertex.x = crossSection[ k + 0 ];
					vertex.y = 0;
					vertex.z = crossSection[ k + 1 ];

					// scale

					vertex.multiply( scaling );

					// rotate

					quaternion.setFromAxisAngle( axis, angle );
					vertex.applyQuaternion( quaternion );

					// translate

					vertex.add( spineVector );

					vertices.push( vertex.x, vertex.y, vertex.z );

				}

			}

			// indices

			const indices = [];

			const spineCount = spine.length / 3;
			const crossSectionCount = crossSection.length / 2;

			for ( let i = 0; i < spineCount - 1; i ++ ) {

				for ( let j = 0; j < crossSectionCount - 1; j ++ ) {

					const a = j + i * crossSectionCount;
					let b = ( j + 1 ) + i * crossSectionCount;
					const c = j + ( i + 1 ) * crossSectionCount;
					let d = ( j + 1 ) + ( i + 1 ) * crossSectionCount;

					if ( ( j === crossSectionCount - 2 ) && ( crossSectionClosed === true ) ) {

						b = i * crossSectionCount;
						d = ( i + 1 ) * crossSectionCount;

					}

					if ( ccw === true ) {

						indices.push( a, b, c );
						indices.push( c, b, d );

					} else {

						indices.push( a, c, b );
						indices.push( c, d, b );

					}

				}

			}

			// triangulate cap

			if ( beginCap === true || endCap === true ) {

				const contour = [];

				for ( let i = 0, l = crossSection.length; i < l; i += 2 ) {

					contour.push( new Vector2( crossSection[ i ], crossSection[ i + 1 ] ) );

				}

				const faces = ShapeUtils.triangulateShape( contour, [] );
				const capIndices = [];

				for ( let i = 0, l = faces.length; i < l; i ++ ) {

					const face = faces[ i ];

					capIndices.push( face[ 0 ], face[ 1 ], face[ 2 ] );

				}

				// begin cap

				if ( beginCap === true ) {

					for ( let i = 0, l = capIndices.length; i < l; i += 3 ) {

						if ( ccw === true ) {

							indices.push( capIndices[ i + 0 ], capIndices[ i + 1 ], capIndices[ i + 2 ] );

						} else {

							indices.push( capIndices[ i + 0 ], capIndices[ i + 2 ], capIndices[ i + 1 ] );

						}

					}

				}

				// end cap

				if ( endCap === true ) {

					const indexOffset = crossSectionCount * ( spineCount - 1 ); // references to the first vertex of the last cross section

					for ( let i = 0, l = capIndices.length; i < l; i += 3 ) {

						if ( ccw === true ) {

							indices.push( indexOffset + capIndices[ i + 0 ], indexOffset + capIndices[ i + 2 ], indexOffset + capIndices[ i + 1 ] );

						} else {

							indices.push( indexOffset + capIndices[ i + 0 ], indexOffset + capIndices[ i + 1 ], indexOffset + capIndices[ i + 2 ] );

						}

					}

				}

			}

			const positionAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( vertices, 3 ) );
			const normalAttribute = computeNormalAttribute( indices, vertices, creaseAngle );

			const geometry = new BufferGeometry();
			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );
			// no uvs yet

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}
```
</details>

### `resolveUSE(identifier: any): any`

**Parameters:**

- **`identifier`** `any`

**Returns:** `any`

**Calls:**

- `getNode`
- `build.clone`

**Internal Comments:**
```
// because the same 3D objects can have different transformations, it's necessary to clone them.
// materials can be influenced by the geometry (e.g. vertex normals). cloning is necessary to avoid
// any side effects
```

<details><summary>Code</summary>

```typescript
function resolveUSE( identifier ) {

			const node = nodeMap[ identifier ];
			const build = getNode( node );

			// because the same 3D objects can have different transformations, it's necessary to clone them.
			// materials can be influenced by the geometry (e.g. vertex normals). cloning is necessary to avoid
			// any side effects

			return ( build.isObject3D || build.isMaterial ) ? build.clone() : build;

		}
```
</details>

### `parseFieldChildren(children: any, owner: any): void`

**Parameters:**

- **`children`** `any`
- **`owner`** `any`

**Returns:** `void`

**Calls:**

- `getNode`
- `owner.add`

<details><summary>Code</summary>

```typescript
function parseFieldChildren( children, owner ) {

			for ( let i = 0, l = children.length; i < l; i ++ ) {

				const object = getNode( children[ i ] );

				if ( object instanceof Object3D ) owner.add( object );

			}

		}
```
</details>

### `triangulateFaceIndex(index: any, ccw: any): any[]`

**Parameters:**

- **`index`** `any`
- **`ccw`** `any`

**Returns:** `any[]`

**Calls:**

- `indices.push`

**Internal Comments:**
```
// since face definitions can have more than three vertices, it's necessary to (x2)
// perform a simple triangulation (x2)
// an index of -1 indicates that the current face has ended and the next one begins
```

<details><summary>Code</summary>

```typescript
function triangulateFaceIndex( index, ccw ) {

			const indices = [];

			// since face definitions can have more than three vertices, it's necessary to
			// perform a simple triangulation

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ start ];
				const i2 = index[ i + ( ccw ? 1 : 2 ) ];
				const i3 = index[ i + ( ccw ? 2 : 1 ) ];

				indices.push( i1, i2, i3 );

				// an index of -1 indicates that the current face has ended and the next one begins

				if ( index[ i + 3 ] === - 1 || i + 3 >= l ) {

					i += 3;
					start = i + 1;

				}

			}

			return indices;

		}
```
</details>

### `triangulateFaceData(data: any, index: any): any[]`

**Parameters:**

- **`data`** `any`
- **`index`** `any`

**Returns:** `any[]`

**Calls:**

- `triangulatedData.push`

**Internal Comments:**
```
// an index of -1 indicates that the current face has ended and the next one begins
```

<details><summary>Code</summary>

```typescript
function triangulateFaceData( data, index ) {

			const triangulatedData = [];

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const stride = start * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				triangulatedData.push( x, y, z );

				// an index of -1 indicates that the current face has ended and the next one begins

				if ( index[ i + 3 ] === - 1 || i + 3 >= l ) {

					i += 3;
					start ++;

				}

			}

			return triangulatedData;

		}
```
</details>

### `flattenData(data: any, index: any): any[]`

**Parameters:**

- **`data`** `any`
- **`index`** `any`

**Returns:** `any[]`

**Calls:**

- `flattenData.push`

<details><summary>Code</summary>

```typescript
function flattenData( data, index ) {

			const flattenData = [];

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ i ];

				const stride = i1 * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				flattenData.push( x, y, z );

			}

			return flattenData;

		}
```
</details>

### `expandLineIndex(index: any): any[]`

**Parameters:**

- **`index`** `any`

**Returns:** `any[]`

**Calls:**

- `indices.push`

**Internal Comments:**
```
// an index of -1 indicates that the current line has ended and the next one begins
```

<details><summary>Code</summary>

```typescript
function expandLineIndex( index ) {

			const indices = [];

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ i ];
				const i2 = index[ i + 1 ];

				indices.push( i1, i2 );

				// an index of -1 indicates that the current line has ended and the next one begins

				if ( index[ i + 2 ] === - 1 || i + 2 >= l ) {

					i += 2;

				}

			}

			return indices;

		}
```
</details>

### `expandLineData(data: any, index: any): any[]`

**Parameters:**

- **`data`** `any`
- **`index`** `any`

**Returns:** `any[]`

**Calls:**

- `triangulatedData.push`

**Internal Comments:**
```
// an index of -1 indicates that the current line has ended and the next one begins
```

<details><summary>Code</summary>

```typescript
function expandLineData( data, index ) {

			const triangulatedData = [];

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const stride = start * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				triangulatedData.push( x, y, z );

				// an index of -1 indicates that the current line has ended and the next one begins

				if ( index[ i + 2 ] === - 1 || i + 2 >= l ) {

					i += 2;
					start ++;

				}

			}

			return triangulatedData;

		}
```
</details>

### `computeAttributeFromIndexedData(coordIndex: any, index: any, data: any, itemSize: any): any`

**Parameters:**

- **`coordIndex`** `any`
- **`index`** `any`
- **`data`** `any`
- **`itemSize`** `any`

**Returns:** `any`

**Calls:**

- `uvA.fromArray`
- `uvB.fromArray`
- `uvC.fromArray`
- `array.push`
- `vA.fromArray`
- `vB.fromArray`
- `vC.fromArray`

**Internal Comments:**
```
// we use the coordIndex.length as delimiter since normalIndex must contain at least as many indices
```

<details><summary>Code</summary>

```typescript
function computeAttributeFromIndexedData( coordIndex, index, data, itemSize ) {

			const array = [];

			// we use the coordIndex.length as delimiter since normalIndex must contain at least as many indices

			for ( let i = 0, l = coordIndex.length; i < l; i += 3 ) {

				const a = index[ i ];
				const b = index[ i + 1 ];
				const c = index[ i + 2 ];

				if ( itemSize === 2 ) {

					uvA.fromArray( data, a * itemSize );
					uvB.fromArray( data, b * itemSize );
					uvC.fromArray( data, c * itemSize );

					array.push( uvA.x, uvA.y );
					array.push( uvB.x, uvB.y );
					array.push( uvC.x, uvC.y );

				} else {

					vA.fromArray( data, a * itemSize );
					vB.fromArray( data, b * itemSize );
					vC.fromArray( data, c * itemSize );

					array.push( vA.x, vA.y, vA.z );
					array.push( vB.x, vB.y, vB.z );
					array.push( vC.x, vC.y, vC.z );

				}

			}

			return new Float32BufferAttribute( array, itemSize );

		}
```
</details>

### `computeAttributeFromFaceData(index: any, faceData: any): any`

**Parameters:**

- **`index`** `any`
- **`faceData`** `any`

**Returns:** `any`

**Calls:**

- `vA.fromArray`
- `array.push`

<details><summary>Code</summary>

```typescript
function computeAttributeFromFaceData( index, faceData ) {

			const array = [];

			for ( let i = 0, j = 0, l = index.length; i < l; i += 3, j ++ ) {

				vA.fromArray( faceData, j * 3 );

				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );

			}

			return new Float32BufferAttribute( array, 3 );

		}
```
</details>

### `computeAttributeFromLineData(index: any, lineData: any): any`

**Parameters:**

- **`index`** `any`
- **`lineData`** `any`

**Returns:** `any`

**Calls:**

- `vA.fromArray`
- `array.push`

<details><summary>Code</summary>

```typescript
function computeAttributeFromLineData( index, lineData ) {

			const array = [];

			for ( let i = 0, j = 0, l = index.length; i < l; i += 2, j ++ ) {

				vA.fromArray( lineData, j * 3 );

				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );

			}

			return new Float32BufferAttribute( array, 3 );

		}
```
</details>

### `toNonIndexedAttribute(indices: any, attribute: any): any`

**Parameters:**

- **`indices`** `any`
- **`attribute`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function toNonIndexedAttribute( indices, attribute ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				index = indices[ i ] * itemSize;

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new Float32BufferAttribute( array2, itemSize );

		}
```
</details>

### `computeNormalAttribute(index: any, coord: any, creaseAngle: any): any`

**Parameters:**

- **`index`** `any`
- **`coord`** `any`
- **`creaseAngle`** `any`

**Returns:** `any`

**Calls:**

- `vA.fromArray`
- `vB.fromArray`
- `vC.fromArray`
- `cb.subVectors`
- `ab.subVectors`
- `cb.cross`
- `cb.normalize`
- `face.normal.copy`
- `vertexNormals[ a ].push`
- `vertexNormals[ b ].push`
- `vertexNormals[ c ].push`
- `faces.push`
- `weightedNormal`
- `normals.push`

**Internal Comments:**
```
// prepare face and raw vertex normals
// compute vertex normals and build final geometry (x2)
```

<details><summary>Code</summary>

```typescript
function computeNormalAttribute( index, coord, creaseAngle ) {

			const faces = [];
			const vertexNormals = {};

			// prepare face and raw vertex normals

			for ( let i = 0, l = index.length; i < l; i += 3 ) {

				const a = index[ i ];
				const b = index[ i + 1 ];
				const c = index[ i + 2 ];

				const face = new Face( a, b, c );

				vA.fromArray( coord, a * 3 );
				vB.fromArray( coord, b * 3 );
				vC.fromArray( coord, c * 3 );

				cb.subVectors( vC, vB );
				ab.subVectors( vA, vB );
				cb.cross( ab );

				cb.normalize();

				face.normal.copy( cb );

				if ( vertexNormals[ a ] === undefined ) vertexNormals[ a ] = [];
				if ( vertexNormals[ b ] === undefined ) vertexNormals[ b ] = [];
				if ( vertexNormals[ c ] === undefined ) vertexNormals[ c ] = [];

				vertexNormals[ a ].push( face.normal );
				vertexNormals[ b ].push( face.normal );
				vertexNormals[ c ].push( face.normal );

				faces.push( face );

			}

			// compute vertex normals and build final geometry

			const normals = [];

			for ( let i = 0, l = faces.length; i < l; i ++ ) {

				const face = faces[ i ];

				const nA = weightedNormal( vertexNormals[ face.a ], face.normal, creaseAngle );
				const nB = weightedNormal( vertexNormals[ face.b ], face.normal, creaseAngle );
				const nC = weightedNormal( vertexNormals[ face.c ], face.normal, creaseAngle );

				vA.fromArray( coord, face.a * 3 );
				vB.fromArray( coord, face.b * 3 );
				vC.fromArray( coord, face.c * 3 );

				normals.push( nA.x, nA.y, nA.z );
				normals.push( nB.x, nB.y, nB.z );
				normals.push( nC.x, nC.y, nC.z );

			}

			return new Float32BufferAttribute( normals, 3 );

		}
```
</details>

### `weightedNormal(normals: any, vector: any, creaseAngle: any): any`

**Parameters:**

- **`normals`** `any`
- **`vector`** `any`
- **`creaseAngle`** `any`

**Returns:** `any`

**Calls:**

- `normal.copy`
- `normals[ i ].angleTo`
- `normal.add`
- `normal.normalize`

<details><summary>Code</summary>

```typescript
function weightedNormal( normals, vector, creaseAngle ) {

			const normal = new Vector3();

			if ( creaseAngle === 0 ) {

				normal.copy( vector );

			} else {

				for ( let i = 0, l = normals.length; i < l; i ++ ) {

					if ( normals[ i ].angleTo( vector ) < creaseAngle ) {

						normal.add( normals[ i ] );

					}

				}

			}

			return normal.normalize();

		}
```
</details>

### `toColorArray(colors: any): any[]`

**Parameters:**

- **`colors`** `any`

**Returns:** `any[]`

**Calls:**

- `array.push`

<details><summary>Code</summary>

```typescript
function toColorArray( colors ) {

			const array = [];

			for ( let i = 0, l = colors.length; i < l; i += 3 ) {

				array.push( new Color( colors[ i ], colors[ i + 1 ], colors[ i + 2 ] ) );

			}

			return array;

		}
```
</details>

### `convertColorsToLinearSRGB(attribute: any): void`

**Parameters:**

- **`attribute`** `any`

**Returns:** `void`

**Calls:**

- `color.fromBufferAttribute`
- `ColorManagement.colorSpaceToWorking`
- `attribute.setXYZ`

<details><summary>Code</summary>

```typescript
function convertColorsToLinearSRGB( attribute ) {

			const color = new Color();

			for ( let i = 0; i < attribute.count; i ++ ) {

				color.fromBufferAttribute( attribute, i );

				ColorManagement.colorSpaceToWorking( color, SRGBColorSpace );

				attribute.setXYZ( i, color.r, color.g, color.b );

			}

		}
```
</details>

### `paintFaces(geometry: BufferGeometry, radius: number, angles: any[], colors: any[], topDown: boolean): void`

**JSDoc:**
```typescript
/**
		 * Vertically paints the faces interpolating between the
		 * specified colors at the specified angels. This is used for the Background
		 * node, but could be applied to other nodes with multiple faces as well.
		 *
		 * When used with the Background node, default is directionIsDown is true if
		 * interpolating the skyColor down from the Zenith. When interpolating up from
		 * the Nadir i.e. interpolating the groundColor, the directionIsDown is false.
		 *
		 * The first angle is never specified, it is the Zenith (0 rad). Angles are specified
		 * in radians. The geometry is thought a sphere, but could be anything. The color interpolation
		 * is linear along the Y axis in any case.
		 *
		 * You must specify one more color than you have angles at the beginning of the colors array.
		 * This is the color of the Zenith (the top of the shape).
		 *
		 * @param {BufferGeometry} geometry
		 * @param {number} radius
		 * @param {array} angles
		 * @param {array} colors
		 * @param {boolean} topDown - Whether to work top down or bottom up.
		 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`
- **`radius`** `number`
- **`angles`** `any[]`
- **`colors`** `any[]`
- **`topDown`** `boolean`

**Returns:** `void`

**Calls:**

- `point.setFromSphericalCoords`
- `thresholds.push`
- `indices.getX`
- `position.fromBufferAttribute`
- `Math.abs`
- `color.copy( colorA ).lerp`
- `ColorManagement.colorSpaceToWorking`
- `colorAttribute.setXYZ`
- `geometry.setAttribute`

**Internal Comments:**
```
// compute threshold values (x2)
// generate vertex colors (x2)
// interpolation for sky color
// interpolation for ground color
```

<details><summary>Code</summary>

```typescript
function paintFaces( geometry, radius, angles, colors, topDown ) {

			// compute threshold values

			const thresholds = [];
			const startAngle = ( topDown === true ) ? 0 : Math.PI;

			for ( let i = 0, l = colors.length; i < l; i ++ ) {

				let angle = ( i === 0 ) ? 0 : angles[ i - 1 ];
				angle = ( topDown === true ) ? angle : ( startAngle - angle );

				const point = new Vector3();
				point.setFromSphericalCoords( radius, angle, 0 );

				thresholds.push( point );

			}

			// generate vertex colors

			const indices = geometry.index;
			const positionAttribute = geometry.attributes.position;
			const colorAttribute = new BufferAttribute( new Float32Array( geometry.attributes.position.count * 3 ), 3 );

			const position = new Vector3();
			const color = new Color();

			for ( let i = 0; i < indices.count; i ++ ) {

				const index = indices.getX( i );
				position.fromBufferAttribute( positionAttribute, index );

				let thresholdIndexA, thresholdIndexB;
				let t = 1;

				for ( let j = 1; j < thresholds.length; j ++ ) {

					thresholdIndexA = j - 1;
					thresholdIndexB = j;

					const thresholdA = thresholds[ thresholdIndexA ];
					const thresholdB = thresholds[ thresholdIndexB ];

					if ( topDown === true ) {

						// interpolation for sky color

						if ( position.y <= thresholdA.y && position.y > thresholdB.y ) {

							t = Math.abs( thresholdA.y - position.y ) / Math.abs( thresholdA.y - thresholdB.y );

							break;

						}

					} else {

						// interpolation for ground color

						if ( position.y >= thresholdA.y && position.y < thresholdB.y ) {

							t = Math.abs( thresholdA.y - position.y ) / Math.abs( thresholdA.y - thresholdB.y );

							break;

						}

					}

				}

				const colorA = colors[ thresholdIndexA ];
				const colorB = colors[ thresholdIndexB ];

				color.copy( colorA ).lerp( colorB, t );

				ColorManagement.colorSpaceToWorking( color, SRGBColorSpace );

				colorAttribute.setXYZ( index, color.r, color.g, color.b );

			}

			geometry.setAttribute( 'color', colorAttribute );

		}
```
</details>

### `VRMLLexer.lex(inputText: any): any`

**Parameters:**

- **`inputText`** `any`

**Returns:** `any`

**Calls:**

- `this.lexer.tokenize`
- `console.error`
- `Error`

<details><summary>Code</summary>

```typescript
lex( inputText ) {

		const lexingResult = this.lexer.tokenize( inputText );

		if ( lexingResult.errors.length > 0 ) {

			console.error( lexingResult.errors );

			throw Error( 'THREE.VRMLLexer: Lexing errors detected.' );

		}

		return lexingResult;

	}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

					$.SUBRULE( $.singleFieldValue );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

					$.SUBRULE( $.singleFieldValue );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

					$.SUBRULE( $.multiFieldValue );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

					$.SUBRULE( $.multiFieldValue );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

					$.CONSUME( Identifier );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

					$.CONSUME( Identifier );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

					$.CONSUME( NodeName );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

					$.CONSUME( NodeName );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

					$.CONSUME( Identifier );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

					$.CONSUME( Identifier );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

					$.CONSUME( NodeName );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

					$.CONSUME( NodeName );

				}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

						$.SUBRULE( $.node );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

						$.SUBRULE( $.node );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

						$.SUBRULE( $.use );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

						$.SUBRULE( $.use );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( StringLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( StringLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( HexLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( HexLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( NumberLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( NumberLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( TrueLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( TrueLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( FalseLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( FalseLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( NullLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( NullLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

						$.SUBRULE( $.node );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

						$.SUBRULE( $.node );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

						$.SUBRULE( $.use );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.SUBRULE`

<details><summary>Code</summary>

```typescript
function () {

						$.SUBRULE( $.use );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( StringLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( StringLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( HexLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( HexLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( NumberLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( NumberLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( NullLiteral );

					}
```
</details>

### `ALT(): void`

**Returns:** `void`

**Calls:**

- `$.CONSUME`

<details><summary>Code</summary>

```typescript
function () {

						$.CONSUME( NullLiteral );

					}
```
</details>


---

## Classes

### `VRMLLoader`

<details><summary>Class Code</summary>

```ts
class VRMLLoader extends Loader {

	/**
	 * Constructs a new VRML loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded VRML asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Scene)} onLoad - Executed when the loading process has been finished.
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
	 * Parses the given VRML data and returns the resulting scene.
	 *
	 * @param {string} data - The raw VRML data as a string.
	 * @param {string} path - The URL base path.
	 * @return {Scene} The parsed scene.
	 */
	parse( data, path ) {

		const nodeMap = {};

		function generateVRMLTree( data ) {

			// create lexer, parser and visitor

			const tokenData = createTokens();

			const lexer = new VRMLLexer( tokenData.tokens );
			const parser = new VRMLParser( tokenData.tokenVocabulary );
			const visitor = createVisitor( parser.getBaseCstVisitorConstructor() );

			// lexing

			const lexingResult = lexer.lex( data );
			parser.input = lexingResult.tokens;

			// parsing

			const cstOutput = parser.vrml();

			if ( parser.errors.length > 0 ) {

				console.error( parser.errors );

				throw Error( 'THREE.VRMLLoader: Parsing errors detected.' );

			}

			// actions

			const ast = visitor.visit( cstOutput );

			return ast;

		}

		function createTokens() {

			const createToken = chevrotain.createToken;

			// from http://gun.teipir.gr/VRML-amgem/spec/part1/concepts.html#SyntaxBasics

			const RouteIdentifier = createToken( { name: 'RouteIdentifier', pattern: /[^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d][^\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]*[\.][^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d][^\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]*/ } );
			const Identifier = createToken( { name: 'Identifier', pattern: /[^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]([^\0-\x20\x22\x27\x23\x2b\x2c\x2e\x5b\x5d\x5c\x7b\x7d])*/, longer_alt: RouteIdentifier } );

			// from http://gun.teipir.gr/VRML-amgem/spec/part1/nodesRef.html

			const nodeTypes = [
				'Anchor', 'Billboard', 'Collision', 'Group', 'Transform', // grouping nodes
				'Inline', 'LOD', 'Switch', // special groups
				'AudioClip', 'DirectionalLight', 'PointLight', 'Script', 'Shape', 'Sound', 'SpotLight', 'WorldInfo', // common nodes
				'CylinderSensor', 'PlaneSensor', 'ProximitySensor', 'SphereSensor', 'TimeSensor', 'TouchSensor', 'VisibilitySensor', // sensors
				'Box', 'Cone', 'Cylinder', 'ElevationGrid', 'Extrusion', 'IndexedFaceSet', 'IndexedLineSet', 'PointSet', 'Sphere', // geometries
				'Color', 'Coordinate', 'Normal', 'TextureCoordinate', // geometric properties
				'Appearance', 'FontStyle', 'ImageTexture', 'Material', 'MovieTexture', 'PixelTexture', 'TextureTransform', // appearance
				'ColorInterpolator', 'CoordinateInterpolator', 'NormalInterpolator', 'OrientationInterpolator', 'PositionInterpolator', 'ScalarInterpolator', // interpolators
				'Background', 'Fog', 'NavigationInfo', 'Viewpoint', // bindable nodes
				'Text' // Text must be placed at the end of the regex so there are no matches for TextureTransform and TextureCoordinate
			];

			//

			const Version = createToken( {
				name: 'Version',
				pattern: /#VRML.*/,
				longer_alt: Identifier
			} );

			const NodeName = createToken( {
				name: 'NodeName',
				pattern: new RegExp( nodeTypes.join( '|' ) ),
				longer_alt: Identifier
			} );

			const DEF = createToken( {
				name: 'DEF',
				pattern: /DEF/,
				longer_alt: Identifier
			} );

			const USE = createToken( {
				name: 'USE',
				pattern: /USE/,
				longer_alt: Identifier
			} );

			const ROUTE = createToken( {
				name: 'ROUTE',
				pattern: /ROUTE/,
				longer_alt: Identifier
			} );

			const TO = createToken( {
				name: 'TO',
				pattern: /TO/,
				longer_alt: Identifier
			} );

			//

			const StringLiteral = createToken( { name: 'StringLiteral', pattern: /"(?:[^\\"\n\r]|\\[bfnrtv"\\/]|\\u[0-9a-fA-F][0-9a-fA-F][0-9a-fA-F][0-9a-fA-F])*"/ } );
			const HexLiteral = createToken( { name: 'HexLiteral', pattern: /0[xX][0-9a-fA-F]+/ } );
			const NumberLiteral = createToken( { name: 'NumberLiteral', pattern: /[-+]?[0-9]*\.?[0-9]+([eE][-+]?[0-9]+)?/ } );
			const TrueLiteral = createToken( { name: 'TrueLiteral', pattern: /TRUE/ } );
			const FalseLiteral = createToken( { name: 'FalseLiteral', pattern: /FALSE/ } );
			const NullLiteral = createToken( { name: 'NullLiteral', pattern: /NULL/ } );
			const LSquare = createToken( { name: 'LSquare', pattern: /\[/ } );
			const RSquare = createToken( { name: 'RSquare', pattern: /]/ } );
			const LCurly = createToken( { name: 'LCurly', pattern: /{/ } );
			const RCurly = createToken( { name: 'RCurly', pattern: /}/ } );
			const Comment = createToken( {
				name: 'Comment',
				pattern: /#.*/,
				group: chevrotain.Lexer.SKIPPED
			} );

			// commas, blanks, tabs, newlines and carriage returns are whitespace characters wherever they appear outside of string fields

			const WhiteSpace = createToken( {
				name: 'WhiteSpace',
				pattern: /[ ,\s]/,
				group: chevrotain.Lexer.SKIPPED
			} );

			const tokens = [
				WhiteSpace,
				// keywords appear before the Identifier
				NodeName,
				DEF,
				USE,
				ROUTE,
				TO,
				TrueLiteral,
				FalseLiteral,
				NullLiteral,
				// the Identifier must appear after the keywords because all keywords are valid identifiers
				Version,
				Identifier,
				RouteIdentifier,
				StringLiteral,
				HexLiteral,
				NumberLiteral,
				LSquare,
				RSquare,
				LCurly,
				RCurly,
				Comment
			];

			const tokenVocabulary = {};

			for ( let i = 0, l = tokens.length; i < l; i ++ ) {

				const token = tokens[ i ];

				tokenVocabulary[ token.name ] = token;

			}

			return { tokens: tokens, tokenVocabulary: tokenVocabulary };

		}


		function createVisitor( BaseVRMLVisitor ) {

			// the visitor is created dynamically based on the given base class

			class VRMLToASTVisitor extends BaseVRMLVisitor {

				constructor() {

					super();

					this.validateVisitor();

				}

				vrml( ctx ) {

					const data = {
						version: this.visit( ctx.version ),
						nodes: [],
						routes: []
					};

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						data.nodes.push( this.visit( node ) );

					}

					if ( ctx.route ) {

						for ( let i = 0, l = ctx.route.length; i < l; i ++ ) {

							const route = ctx.route[ i ];

							data.routes.push( this.visit( route ) );

						}

					}

					return data;

				}

				version( ctx ) {

					return ctx.Version[ 0 ].image;

				}

				node( ctx ) {

					const data = {
						name: ctx.NodeName[ 0 ].image,
						fields: []
					};

					if ( ctx.field ) {

						for ( let i = 0, l = ctx.field.length; i < l; i ++ ) {

							const field = ctx.field[ i ];

							data.fields.push( this.visit( field ) );

						}

					}

					// DEF

					if ( ctx.def ) {

						data.DEF = this.visit( ctx.def[ 0 ] );

					}

					return data;

				}

				field( ctx ) {

					const data = {
						name: ctx.Identifier[ 0 ].image,
						type: null,
						values: null
					};

					let result;

					// SFValue

					if ( ctx.singleFieldValue ) {

						result = this.visit( ctx.singleFieldValue[ 0 ] );

					}

					// MFValue

					if ( ctx.multiFieldValue ) {

						result = this.visit( ctx.multiFieldValue[ 0 ] );

					}

					data.type = result.type;
					data.values = result.values;

					return data;

				}

				def( ctx ) {

					return ( ctx.Identifier || ctx.NodeName )[ 0 ].image;

				}

				use( ctx ) {

					return { USE: ( ctx.Identifier || ctx.NodeName )[ 0 ].image };

				}

				singleFieldValue( ctx ) {

					return processField( this, ctx );

				}

				multiFieldValue( ctx ) {

					return processField( this, ctx );

				}

				route( ctx ) {

					const data = {
						FROM: ctx.RouteIdentifier[ 0 ].image,
						TO: ctx.RouteIdentifier[ 1 ].image
					};

					return data;

				}

			}

			function processField( scope, ctx ) {

				const field = {
					type: null,
					values: []
				};

				if ( ctx.node ) {

					field.type = 'node';

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						field.values.push( scope.visit( node ) );

					}

				}

				if ( ctx.use ) {

					field.type = 'use';

					for ( let i = 0, l = ctx.use.length; i < l; i ++ ) {

						const use = ctx.use[ i ];

						field.values.push( scope.visit( use ) );

					}

				}

				if ( ctx.StringLiteral ) {

					field.type = 'string';

					for ( let i = 0, l = ctx.StringLiteral.length; i < l; i ++ ) {

						const stringLiteral = ctx.StringLiteral[ i ];

						field.values.push( stringLiteral.image.replace( /'|"/g, '' ) );

					}

				}

				if ( ctx.NumberLiteral ) {

					field.type = 'number';

					for ( let i = 0, l = ctx.NumberLiteral.length; i < l; i ++ ) {

						const numberLiteral = ctx.NumberLiteral[ i ];

						field.values.push( parseFloat( numberLiteral.image ) );

					}

				}

				if ( ctx.HexLiteral ) {

					field.type = 'hex';

					for ( let i = 0, l = ctx.HexLiteral.length; i < l; i ++ ) {

						const hexLiteral = ctx.HexLiteral[ i ];

						field.values.push( hexLiteral.image );

					}

				}

				if ( ctx.TrueLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.TrueLiteral.length; i < l; i ++ ) {

						const trueLiteral = ctx.TrueLiteral[ i ];

						if ( trueLiteral.image === 'TRUE' ) field.values.push( true );

					}

				}

				if ( ctx.FalseLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.FalseLiteral.length; i < l; i ++ ) {

						const falseLiteral = ctx.FalseLiteral[ i ];

						if ( falseLiteral.image === 'FALSE' ) field.values.push( false );

					}

				}

				if ( ctx.NullLiteral ) {

					field.type = 'null';

					ctx.NullLiteral.forEach( function () {

						field.values.push( null );

					} );

				}

				return field;

			}

			return new VRMLToASTVisitor();

		}

		function parseTree( tree ) {

			// console.log( JSON.stringify( tree, null, 2 ) );

			const nodes = tree.nodes;
			const scene = new Scene();

			// first iteration: build nodemap based on DEF statements

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				const node = nodes[ i ];

				buildNodeMap( node );

			}

			// second iteration: build nodes

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				const node = nodes[ i ];
				const object = getNode( node );

				if ( object instanceof Object3D ) scene.add( object );

				if ( node.name === 'WorldInfo' ) scene.userData.worldInfo = object;

			}

			return scene;

		}

		function buildNodeMap( node ) {

			if ( node.DEF ) {

				nodeMap[ node.DEF ] = node;

			}

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];

				if ( field.type === 'node' ) {

					const fieldValues = field.values;

					for ( let j = 0, jl = fieldValues.length; j < jl; j ++ ) {

						buildNodeMap( fieldValues[ j ] );

					}

				}


			}

		}


		function getNode( node ) {

			// handle case where a node refers to a different one

			if ( node.USE ) {

				return resolveUSE( node.USE );

			}

			if ( node.build !== undefined ) return node.build;

			node.build = buildNode( node );

			return node.build;

		}

		// node builder

		function buildNode( node ) {

			const nodeName = node.name;
			let build;

			switch ( nodeName ) {

				case 'Anchor':
				case 'Group':
				case 'Transform':
				case 'Collision':
					build = buildGroupingNode( node );
					break;

				case 'Background':
					build = buildBackgroundNode( node );
					break;

				case 'Shape':
					build = buildShapeNode( node );
					break;

				case 'Appearance':
					build = buildAppearanceNode( node );
					break;

				case 'Material':
					build = buildMaterialNode( node );
					break;

				case 'ImageTexture':
					build = buildImageTextureNode( node );
					break;

				case 'PixelTexture':
					build = buildPixelTextureNode( node );
					break;

				case 'TextureTransform':
					build = buildTextureTransformNode( node );
					break;

				case 'IndexedFaceSet':
					build = buildIndexedFaceSetNode( node );
					break;

				case 'IndexedLineSet':
					build = buildIndexedLineSetNode( node );
					break;

				case 'PointSet':
					build = buildPointSetNode( node );
					break;

				case 'Box':
					build = buildBoxNode( node );
					break;

				case 'Cone':
					build = buildConeNode( node );
					break;

				case 'Cylinder':
					build = buildCylinderNode( node );
					break;

				case 'Sphere':
					build = buildSphereNode( node );
					break;

				case 'ElevationGrid':
					build = buildElevationGridNode( node );
					break;

				case 'Extrusion':
					build = buildExtrusionNode( node );
					break;

				case 'Color':
				case 'Coordinate':
				case 'Normal':
				case 'TextureCoordinate':
					build = buildGeometricNode( node );
					break;

				case 'WorldInfo':
					build = buildWorldInfoNode( node );
					break;

				case 'Billboard':

				case 'Inline':
				case 'LOD':
				case 'Switch':

				case 'AudioClip':
				case 'DirectionalLight':
				case 'PointLight':
				case 'Script':
				case 'Sound':
				case 'SpotLight':

				case 'CylinderSensor':
				case 'PlaneSensor':
				case 'ProximitySensor':
				case 'SphereSensor':
				case 'TimeSensor':
				case 'TouchSensor':
				case 'VisibilitySensor':

				case 'Text':

				case 'FontStyle':
				case 'MovieTexture':

				case 'ColorInterpolator':
				case 'CoordinateInterpolator':
				case 'NormalInterpolator':
				case 'OrientationInterpolator':
				case 'PositionInterpolator':
				case 'ScalarInterpolator':

				case 'Fog':
				case 'NavigationInfo':
				case 'Viewpoint':
					// node not supported yet
					break;

				default:
					console.warn( 'THREE.VRMLLoader: Unknown node:', nodeName );
					break;

			}

			if ( build !== undefined && node.DEF !== undefined && build.hasOwnProperty( 'name' ) === true ) {

				build.name = node.DEF;

			}

			return build;

		}

		function buildGroupingNode( node ) {

			const object = new Group();

			//

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bboxCenter':
						// field not supported
						break;

					case 'bboxSize':
						// field not supported
						break;

					case 'center':
						// field not supported
						break;

					case 'children':
						parseFieldChildren( fieldValues, object );
						break;

					case 'description':
						// field not supported
						break;

					case 'collide':
						// field not supported
						break;

					case 'parameter':
						// field not supported
						break;

					case 'rotation':
						const axis = new Vector3( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] ).normalize();
						const angle = fieldValues[ 3 ];
						object.quaternion.setFromAxisAngle( axis, angle );
						break;

					case 'scale':
						object.scale.set( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] );
						break;

					case 'scaleOrientation':
						// field not supported
						break;

					case 'translation':
						object.position.set( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] );
						break;

					case 'proxy':
						// field not supported
						break;

					case 'url':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return object;

		}

		function buildBackgroundNode( node ) {

			const group = new Group();

			let groundAngle, groundColor;
			let skyAngle, skyColor;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'groundAngle':
						groundAngle = fieldValues;
						break;

					case 'groundColor':
						groundColor = fieldValues;
						break;

					case 'backUrl':
						// field not supported
						break;

					case 'bottomUrl':
						// field not supported
						break;

					case 'frontUrl':
						// field not supported
						break;

					case 'leftUrl':
						// field not supported
						break;

					case 'rightUrl':
						// field not supported
						break;

					case 'topUrl':
						// field not supported
						break;

					case 'skyAngle':
						skyAngle = fieldValues;
						break;

					case 'skyColor':
						skyColor = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const radius = 10000;

			// sky

			if ( skyColor ) {

				const skyGeometry = new SphereGeometry( radius, 32, 16 );
				const skyMaterial = new MeshBasicMaterial( { fog: false, side: BackSide, depthWrite: false, depthTest: false } );

				if ( skyColor.length > 3 ) {

					paintFaces( skyGeometry, radius, skyAngle, toColorArray( skyColor ), true );
					skyMaterial.vertexColors = true;

				} else {

					skyMaterial.color.setRGB( skyColor[ 0 ], skyColor[ 1 ], skyColor[ 2 ], SRGBColorSpace );

				}

				const sky = new Mesh( skyGeometry, skyMaterial );
				group.add( sky );

			}

			// ground

			if ( groundColor ) {

				if ( groundColor.length > 0 ) {

					const groundGeometry = new SphereGeometry( radius, 32, 16, 0, 2 * Math.PI, 0.5 * Math.PI, 1.5 * Math.PI );
					const groundMaterial = new MeshBasicMaterial( { fog: false, side: BackSide, vertexColors: true, depthWrite: false, depthTest: false } );

					paintFaces( groundGeometry, radius, groundAngle, toColorArray( groundColor ), false );

					const ground = new Mesh( groundGeometry, groundMaterial );
					group.add( ground );

				}

			}

			// render background group first

			group.renderOrder = - Infinity;

			return group;

		}

		function buildShapeNode( node ) {

			const fields = node.fields;

			// if the appearance field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0)

			let material = new MeshBasicMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0x000000
			} );
			let geometry;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'appearance':
						if ( fieldValues[ 0 ] !== null ) {

							material = getNode( fieldValues[ 0 ] );

						}

						break;

					case 'geometry':
						if ( fieldValues[ 0 ] !== null ) {

							geometry = getNode( fieldValues[ 0 ] );

						}

						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// build 3D object

			let object;

			if ( geometry && geometry.attributes.position ) {

				const type = geometry._type;

				if ( type === 'points' ) { // points

					const pointsMaterial = new PointsMaterial( {
						name: Loader.DEFAULT_MATERIAL_NAME,
						color: 0xffffff,
						opacity: material.opacity,
						transparent: material.transparent
					} );

					if ( geometry.attributes.color !== undefined ) {

						pointsMaterial.vertexColors = true;

					} else {

						// if the color field is NULL and there is a material defined for the appearance affecting this PointSet, then use the emissiveColor of the material to draw the points

						if ( material.isMeshPhongMaterial ) {

							pointsMaterial.color.copy( material.emissive );

						}

					}

					object = new Points( geometry, pointsMaterial );

				} else if ( type === 'line' ) { // lines

					const lineMaterial = new LineBasicMaterial( {
						name: Loader.DEFAULT_MATERIAL_NAME,
						color: 0xffffff,
						opacity: material.opacity,
						transparent: material.transparent
					} );

					if ( geometry.attributes.color !== undefined ) {

						lineMaterial.vertexColors = true;

					} else {

						// if the color field is NULL and there is a material defined for the appearance affecting this IndexedLineSet, then use the emissiveColor of the material to draw the lines

						if ( material.isMeshPhongMaterial ) {

							lineMaterial.color.copy( material.emissive );

						}

					}

					object = new LineSegments( geometry, lineMaterial );

				} else { // consider meshes

					// check "solid" hint (it's placed in the geometry but affects the material)

					if ( geometry._solid !== undefined ) {

						material.side = ( geometry._solid ) ? FrontSide : DoubleSide;

					}

					// check for vertex colors

					if ( geometry.attributes.color !== undefined ) {

						material.vertexColors = true;

					}

					object = new Mesh( geometry, material );

				}

			} else {

				object = new Object3D();

				// if the geometry field is NULL or no vertices are defined the object is not drawn

				object.visible = false;

			}

			return object;

		}

		function buildAppearanceNode( node ) {

			let material = new MeshPhongMaterial();
			let transformData;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'material':
						if ( fieldValues[ 0 ] !== null ) {

							const materialData = getNode( fieldValues[ 0 ] );

							if ( materialData.diffuseColor ) material.color.copy( materialData.diffuseColor );
							if ( materialData.emissiveColor ) material.emissive.copy( materialData.emissiveColor );
							if ( materialData.shininess ) material.shininess = materialData.shininess;
							if ( materialData.specularColor ) material.specular.copy( materialData.specularColor );
							if ( materialData.transparency ) material.opacity = 1 - materialData.transparency;
							if ( materialData.transparency > 0 ) material.transparent = true;

						} else {

							// if the material field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0)

							material = new MeshBasicMaterial( {
								name: Loader.DEFAULT_MATERIAL_NAME,
								color: 0x000000
							} );

						}

						break;

					case 'texture':
						const textureNode = fieldValues[ 0 ];
						if ( textureNode !== null ) {

							if ( textureNode.name === 'ImageTexture' || textureNode.name === 'PixelTexture' ) {

								material.map = getNode( textureNode );

							} else {

								// MovieTexture not supported yet

							}

						}

						break;

					case 'textureTransform':
						if ( fieldValues[ 0 ] !== null ) {

							transformData = getNode( fieldValues[ 0 ] );

						}

						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// only apply texture transform data if a texture was defined

			if ( material.map ) {

				// respect VRML lighting model

				if ( material.map.__type ) {

					switch ( material.map.__type ) {

						case TEXTURE_TYPE.INTENSITY_ALPHA:
							material.opacity = 1; // ignore transparency
							break;

						case TEXTURE_TYPE.RGB:
							material.color.set( 0xffffff ); // ignore material color
							break;

						case TEXTURE_TYPE.RGBA:
							material.color.set( 0xffffff ); // ignore material color
							material.opacity = 1; // ignore transparency
							break;

						default:

					}

					delete material.map.__type;

				}

				// apply texture transform

				if ( transformData ) {

					material.map.center.copy( transformData.center );
					material.map.rotation = transformData.rotation;
					material.map.repeat.copy( transformData.scale );
					material.map.offset.copy( transformData.translation );

				}

			}

			return material;

		}

		function buildMaterialNode( node ) {

			const materialData = {};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'ambientIntensity':
						// field not supported
						break;

					case 'diffuseColor':
						materialData.diffuseColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'emissiveColor':
						materialData.emissiveColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'shininess':
						materialData.shininess = fieldValues[ 0 ];
						break;

					case 'specularColor':
						materialData.specularColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'transparency':
						materialData.transparency = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return materialData;

		}

		function parseHexColor( hex, textureType, color ) {

			let value;

			switch ( textureType ) {

				case TEXTURE_TYPE.INTENSITY:
					// Intensity texture: A one-component image specifies one-byte hexadecimal or integer values representing the intensity of the image
					value = parseInt( hex );
					color.r = value;
					color.g = value;
					color.b = value;
					color.a = 1;
					break;

				case TEXTURE_TYPE.INTENSITY_ALPHA:
					// Intensity+Alpha texture: A two-component image specifies the intensity in the first (high) byte and the alpha opacity in the second (low) byte.
					value = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.r = value;
					color.g = value;
					color.b = value;
					color.a = parseInt( '0x' + hex.substring( 4, 6 ) );
					break;

				case TEXTURE_TYPE.RGB:
					// RGB texture: Pixels in a three-component image specify the red component in the first (high) byte, followed by the green and blue components
					color.r = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.g = parseInt( '0x' + hex.substring( 4, 6 ) );
					color.b = parseInt( '0x' + hex.substring( 6, 8 ) );
					color.a = 1;
					break;

				case TEXTURE_TYPE.RGBA:
					// RGBA texture: Four-component images specify the alpha opacity byte after red/green/blue
					color.r = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.g = parseInt( '0x' + hex.substring( 4, 6 ) );
					color.b = parseInt( '0x' + hex.substring( 6, 8 ) );
					color.a = parseInt( '0x' + hex.substring( 8, 10 ) );
					break;

				default:

			}

		}

		function getTextureType( num_components ) {

			let type;

			switch ( num_components ) {

				case 1:
					type = TEXTURE_TYPE.INTENSITY;
					break;

				case 2:
					type = TEXTURE_TYPE.INTENSITY_ALPHA;
					break;

				case 3:
					type = TEXTURE_TYPE.RGB;
					break;

				case 4:
					type = TEXTURE_TYPE.RGBA;
					break;

				default:

			}

			return type;

		}

		function buildPixelTextureNode( node ) {

			let texture;
			let wrapS = RepeatWrapping;
			let wrapT = RepeatWrapping;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'image':
						const width = fieldValues[ 0 ];
						const height = fieldValues[ 1 ];
						const num_components = fieldValues[ 2 ];

						const textureType = getTextureType( num_components );

						const data = new Uint8Array( 4 * width * height );

						const color = { r: 0, g: 0, b: 0, a: 0 };

						for ( let j = 3, k = 0, jl = fieldValues.length; j < jl; j ++, k ++ ) {

							parseHexColor( fieldValues[ j ], textureType, color );

							const stride = k * 4;

							data[ stride + 0 ] = color.r;
							data[ stride + 1 ] = color.g;
							data[ stride + 2 ] = color.b;
							data[ stride + 3 ] = color.a;

						}

						texture = new DataTexture( data, width, height );
						texture.colorSpace = SRGBColorSpace;
						texture.needsUpdate = true;
						texture.__type = textureType; // needed for material modifications
						break;

					case 'repeatS':
						if ( fieldValues[ 0 ] === false ) wrapS = ClampToEdgeWrapping;
						break;

					case 'repeatT':
						if ( fieldValues[ 0 ] === false ) wrapT = ClampToEdgeWrapping;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( texture ) {

				texture.wrapS = wrapS;
				texture.wrapT = wrapT;

			}

			return texture;

		}

		function buildImageTextureNode( node ) {

			let texture;
			let wrapS = RepeatWrapping;
			let wrapT = RepeatWrapping;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'url':
						const url = fieldValues[ 0 ];
						if ( url ) texture = textureLoader.load( url );
						break;

					case 'repeatS':
						if ( fieldValues[ 0 ] === false ) wrapS = ClampToEdgeWrapping;
						break;

					case 'repeatT':
						if ( fieldValues[ 0 ] === false ) wrapT = ClampToEdgeWrapping;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( texture ) {

				texture.wrapS = wrapS;
				texture.wrapT = wrapT;
				texture.colorSpace = SRGBColorSpace;

			}

			return texture;

		}

		function buildTextureTransformNode( node ) {

			const transformData = {
				center: new Vector2(),
				rotation: new Vector2(),
				scale: new Vector2(),
				translation: new Vector2()
			};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'center':
						transformData.center.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					case 'rotation':
						transformData.rotation = fieldValues[ 0 ];
						break;

					case 'scale':
						transformData.scale.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					case 'translation':
						transformData.translation.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return transformData;

		}

		function buildGeometricNode( node ) {

			return node.fields[ 0 ].values;

		}

		function buildWorldInfoNode( node ) {

			const worldInfo = {};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'title':
						worldInfo.title = fieldValues[ 0 ];
						break;

					case 'info':
						worldInfo.info = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return worldInfo;

		}

		function buildIndexedFaceSetNode( node ) {

			let color, coord, normal, texCoord;
			let ccw = true, solid = true, creaseAngle = 0;
			let colorIndex, coordIndex, normalIndex, texCoordIndex;
			let colorPerVertex = true, normalPerVertex = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;

					case 'normal':
						const normalNode = fieldValues[ 0 ];

						if ( normalNode !== null ) {

							normal = getNode( normalNode );

						}

						break;

					case 'texCoord':
						const texCoordNode = fieldValues[ 0 ];

						if ( texCoordNode !== null ) {

							texCoord = getNode( texCoordNode );

						}

						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'colorIndex':
						colorIndex = fieldValues;
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'convex':
						// field not supported
						break;

					case 'coordIndex':
						coordIndex = fieldValues;
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'normalIndex':
						normalIndex = fieldValues;
						break;

					case 'normalPerVertex':
						normalPerVertex = fieldValues[ 0 ];
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'texCoordIndex':
						texCoordIndex = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( coordIndex === undefined ) {

				console.warn( 'THREE.VRMLLoader: Missing coordIndex.' );

				return new BufferGeometry(); // handle VRML files with incomplete geometry definition

			}

			const triangulatedCoordIndex = triangulateFaceIndex( coordIndex, ccw );

			let colorAttribute;
			let normalAttribute;
			let uvAttribute;

			if ( color ) {

				if ( colorPerVertex === true ) {

					if ( colorIndex && colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then it is used to choose colors for each vertex of the IndexedFaceSet.

						const triangulatedColorIndex = triangulateFaceIndex( colorIndex, ccw );
						colorAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedColorIndex, color, 3 );

					} else {

						// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node

						colorAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( color, 3 ) );

					}

				} else {

					if ( colorIndex && colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then they are used to choose one color for each face of the IndexedFaceSet

						const flattenFaceColors = flattenData( color, colorIndex );
						const triangulatedFaceColors = triangulateFaceData( flattenFaceColors, coordIndex );
						colorAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceColors );

					} else {

						// if the colorIndex field is empty, then the color are applied to each face of the IndexedFaceSet in order

						const triangulatedFaceColors = triangulateFaceData( color, coordIndex );
						colorAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceColors );


					}

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			if ( normal ) {

				if ( normalPerVertex === true ) {

					// consider vertex normals

					if ( normalIndex && normalIndex.length > 0 ) {

						// if the normalIndex field is not empty, then it is used to choose normals for each vertex of the IndexedFaceSet.

						const triangulatedNormalIndex = triangulateFaceIndex( normalIndex, ccw );
						normalAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedNormalIndex, normal, 3 );

					} else {

						// if the normalIndex field is empty, then the coordIndex field is used to choose normals from the Normal node

						normalAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( normal, 3 ) );

					}

				} else {

					// consider face normals

					if ( normalIndex && normalIndex.length > 0 ) {

						// if the normalIndex field is not empty, then they are used to choose one normal for each face of the IndexedFaceSet

						const flattenFaceNormals = flattenData( normal, normalIndex );
						const triangulatedFaceNormals = triangulateFaceData( flattenFaceNormals, coordIndex );
						normalAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceNormals );

					} else {

						// if the normalIndex field is empty, then the normals are applied to each face of the IndexedFaceSet in order

						const triangulatedFaceNormals = triangulateFaceData( normal, coordIndex );
						normalAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceNormals );

					}

				}

			} else {

				// if the normal field is NULL, then the loader should automatically generate normals, using creaseAngle to determine if and how normals are smoothed across shared vertices

				normalAttribute = computeNormalAttribute( triangulatedCoordIndex, coord, creaseAngle );

			}

			if ( texCoord ) {

				// texture coordinates are always defined on vertex level

				if ( texCoordIndex && texCoordIndex.length > 0 ) {

					// if the texCoordIndex field is not empty, then it is used to choose texture coordinates for each vertex of the IndexedFaceSet.

					const triangulatedTexCoordIndex = triangulateFaceIndex( texCoordIndex, ccw );
					uvAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedTexCoordIndex, texCoord, 2 );


				} else {

					// if the texCoordIndex field is empty, then the coordIndex array is used to choose texture coordinates from the TextureCoordinate node

					uvAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( texCoord, 2 ) );

				}

			}

			const geometry = new BufferGeometry();
			const positionAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( coord, 3 ) );

			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );

			// optional attributes

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );
			if ( uvAttribute ) geometry.setAttribute( 'uv', uvAttribute );

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}

		function buildIndexedLineSetNode( node ) {

			let color, coord;
			let colorIndex, coordIndex;
			let colorPerVertex = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;

					case 'colorIndex':
						colorIndex = fieldValues;
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'coordIndex':
						coordIndex = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// build lines

			let colorAttribute;

			const expandedLineIndex = expandLineIndex( coordIndex ); // create an index for three.js's linesegment primitive

			if ( color ) {

				if ( colorPerVertex === true ) {

					if ( colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then one color is used for each polyline of the IndexedLineSet.

						const expandedColorIndex = expandLineIndex( colorIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromIndexedData( expandedLineIndex, expandedColorIndex, color, 3 ); // compute data on vertex level

					} else {

						// if the colorIndex field is empty, then the colors are applied to each polyline of the IndexedLineSet in order.

						colorAttribute = toNonIndexedAttribute( expandedLineIndex, new Float32BufferAttribute( color, 3 ) );

					}

				} else {

					if ( colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then colors are applied to each vertex of the IndexedLineSet

						const flattenLineColors = flattenData( color, colorIndex ); // compute colors for each VRML primitive
						const expandedLineColors = expandLineData( flattenLineColors, coordIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromLineData( expandedLineIndex, expandedLineColors ); // compute data on vertex level


					} else {

						// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node

						const expandedLineColors = expandLineData( color, coordIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromLineData( expandedLineIndex, expandedLineColors ); // compute data on vertex level

					}

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			//

			const geometry = new BufferGeometry();

			const positionAttribute = toNonIndexedAttribute( expandedLineIndex, new Float32BufferAttribute( coord, 3 ) );
			geometry.setAttribute( 'position', positionAttribute );

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );

			geometry._type = 'line';

			return geometry;

		}

		function buildPointSetNode( node ) {

			let color, coord;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;


					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new BufferGeometry();

			geometry.setAttribute( 'position', new Float32BufferAttribute( coord, 3 ) );

			if ( color ) {

				const colorAttribute = new Float32BufferAttribute( color, 3 );
				convertColorsToLinearSRGB( colorAttribute );

				geometry.setAttribute( 'color', colorAttribute );

			}

			geometry._type = 'points';

			return geometry;

		}

		function buildBoxNode( node ) {

			const size = new Vector3( 2, 2, 2 );

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'size':
						size.x = fieldValues[ 0 ];
						size.y = fieldValues[ 1 ];
						size.z = fieldValues[ 2 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new BoxGeometry( size.x, size.y, size.z );

			return geometry;

		}

		function buildConeNode( node ) {

			let radius = 1, height = 2, openEnded = false;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bottom':
						openEnded = ! fieldValues[ 0 ];
						break;

					case 'bottomRadius':
						radius = fieldValues[ 0 ];
						break;

					case 'height':
						height = fieldValues[ 0 ];
						break;

					case 'side':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new ConeGeometry( radius, height, 16, 1, openEnded );

			return geometry;

		}

		function buildCylinderNode( node ) {

			let radius = 1, height = 2;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bottom':
						// field not supported
						break;

					case 'radius':
						radius = fieldValues[ 0 ];
						break;

					case 'height':
						height = fieldValues[ 0 ];
						break;

					case 'side':
						// field not supported
						break;

					case 'top':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new CylinderGeometry( radius, radius, height, 16, 1 );

			return geometry;

		}

		function buildSphereNode( node ) {

			let radius = 1;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'radius':
						radius = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new SphereGeometry( radius, 16, 16 );

			return geometry;

		}

		function buildElevationGridNode( node ) {

			let color;
			let normal;
			let texCoord;
			let height;

			let colorPerVertex = true;
			let normalPerVertex = true;
			let solid = true;
			let ccw = true;
			let creaseAngle = 0;
			let xDimension = 2;
			let zDimension = 2;
			let xSpacing = 1;
			let zSpacing = 1;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'normal':
						const normalNode = fieldValues[ 0 ];

						if ( normalNode !== null ) {

							normal = getNode( normalNode );

						}

						break;

					case 'texCoord':
						const texCoordNode = fieldValues[ 0 ];

						if ( texCoordNode !== null ) {

							texCoord = getNode( texCoordNode );

						}

						break;

					case 'height':
						height = fieldValues;
						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'normalPerVertex':
						normalPerVertex = fieldValues[ 0 ];
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'xDimension':
						xDimension = fieldValues[ 0 ];
						break;

					case 'xSpacing':
						xSpacing = fieldValues[ 0 ];
						break;

					case 'zDimension':
						zDimension = fieldValues[ 0 ];
						break;

					case 'zSpacing':
						zSpacing = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// vertex data

			const vertices = [];
			const normals = [];
			const colors = [];
			const uvs = [];

			for ( let i = 0; i < zDimension; i ++ ) {

				for ( let j = 0; j < xDimension; j ++ ) {

					// compute a row major index

					const index = ( i * xDimension ) + j;

					// vertices

					const x = xSpacing * i;
					const y = height[ index ];
					const z = zSpacing * j;

					vertices.push( x, y, z );

					// colors

					if ( color && colorPerVertex === true ) {

						const r = color[ index * 3 + 0 ];
						const g = color[ index * 3 + 1 ];
						const b = color[ index * 3 + 2 ];

						colors.push( r, g, b );

					}

					// normals

					if ( normal && normalPerVertex === true ) {

						const xn = normal[ index * 3 + 0 ];
						const yn = normal[ index * 3 + 1 ];
						const zn = normal[ index * 3 + 2 ];

						normals.push( xn, yn, zn );

					}

					// uvs

					if ( texCoord ) {

						const s = texCoord[ index * 2 + 0 ];
						const t = texCoord[ index * 2 + 1 ];

						uvs.push( s, t );


					} else {

						uvs.push( i / ( xDimension - 1 ), j / ( zDimension - 1 ) );

					}

				}

			}

			// indices

			const indices = [];

			for ( let i = 0; i < xDimension - 1; i ++ ) {

				for ( let j = 0; j < zDimension - 1; j ++ ) {

					// from https://tecfa.unige.ch/guides/vrml/vrml97/spec/part1/nodesRef.html#ElevationGrid

					const a = i + j * xDimension;
					const b = i + ( j + 1 ) * xDimension;
					const c = ( i + 1 ) + ( j + 1 ) * xDimension;
					const d = ( i + 1 ) + j * xDimension;

					// faces

					if ( ccw === true ) {

						indices.push( a, c, b );
						indices.push( c, a, d );

					} else {

						indices.push( a, b, c );
						indices.push( c, d, a );

					}

				}

			}

			//

			const positionAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( vertices, 3 ) );
			const uvAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( uvs, 2 ) );
			let colorAttribute;
			let normalAttribute;

			// color attribute

			if ( color ) {

				if ( colorPerVertex === false ) {

					for ( let i = 0; i < xDimension - 1; i ++ ) {

						for ( let j = 0; j < zDimension - 1; j ++ ) {

							const index = i + j * ( xDimension - 1 );

							const r = color[ index * 3 + 0 ];
							const g = color[ index * 3 + 1 ];
							const b = color[ index * 3 + 2 ];

							// one color per quad

							colors.push( r, g, b ); colors.push( r, g, b ); colors.push( r, g, b );
							colors.push( r, g, b ); colors.push( r, g, b ); colors.push( r, g, b );

						}

					}

					colorAttribute = new Float32BufferAttribute( colors, 3 );

				} else {

					colorAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( colors, 3 ) );

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			// normal attribute

			if ( normal ) {

				if ( normalPerVertex === false ) {

					for ( let i = 0; i < xDimension - 1; i ++ ) {

						for ( let j = 0; j < zDimension - 1; j ++ ) {

							const index = i + j * ( xDimension - 1 );

							const xn = normal[ index * 3 + 0 ];
							const yn = normal[ index * 3 + 1 ];
							const zn = normal[ index * 3 + 2 ];

							// one normal per quad

							normals.push( xn, yn, zn ); normals.push( xn, yn, zn ); normals.push( xn, yn, zn );
							normals.push( xn, yn, zn ); normals.push( xn, yn, zn ); normals.push( xn, yn, zn );

						}

					}

					normalAttribute = new Float32BufferAttribute( normals, 3 );

				} else {

					normalAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( normals, 3 ) );

				}

			} else {

				normalAttribute = computeNormalAttribute( indices, vertices, creaseAngle );

			}

			// build geometry

			const geometry = new BufferGeometry();
			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );
			geometry.setAttribute( 'uv', uvAttribute );

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}

		function buildExtrusionNode( node ) {

			let crossSection = [ 1, 1, 1, - 1, - 1, - 1, - 1, 1, 1, 1 ];
			let spine = [ 0, 0, 0, 0, 1, 0 ];
			let scale;
			let orientation;

			let beginCap = true;
			let ccw = true;
			let creaseAngle = 0;
			let endCap = true;
			let solid = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'beginCap':
						beginCap = fieldValues[ 0 ];
						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'convex':
						// field not supported
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'crossSection':
						crossSection = fieldValues;
						break;

					case 'endCap':
						endCap = fieldValues[ 0 ];
						break;

					case 'orientation':
						orientation = fieldValues;
						break;

					case 'scale':
						scale = fieldValues;
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'spine':
						spine = fieldValues; // only extrusion along the Y-axis are supported so far
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const crossSectionClosed = ( crossSection[ 0 ] === crossSection[ crossSection.length - 2 ] && crossSection[ 1 ] === crossSection[ crossSection.length - 1 ] );

			// vertices

			const vertices = [];
			const spineVector = new Vector3();
			const scaling = new Vector3();

			const axis = new Vector3();
			const vertex = new Vector3();
			const quaternion = new Quaternion();

			for ( let i = 0, j = 0, o = 0, il = spine.length; i < il; i += 3, j += 2, o += 4 ) {

				spineVector.fromArray( spine, i );

				scaling.x = scale ? scale[ j + 0 ] : 1;
				scaling.y = 1;
				scaling.z = scale ? scale[ j + 1 ] : 1;

				axis.x = orientation ? orientation[ o + 0 ] : 0;
				axis.y = orientation ? orientation[ o + 1 ] : 0;
				axis.z = orientation ? orientation[ o + 2 ] : 1;
				const angle = orientation ? orientation[ o + 3 ] : 0;

				for ( let k = 0, kl = crossSection.length; k < kl; k += 2 ) {

					vertex.x = crossSection[ k + 0 ];
					vertex.y = 0;
					vertex.z = crossSection[ k + 1 ];

					// scale

					vertex.multiply( scaling );

					// rotate

					quaternion.setFromAxisAngle( axis, angle );
					vertex.applyQuaternion( quaternion );

					// translate

					vertex.add( spineVector );

					vertices.push( vertex.x, vertex.y, vertex.z );

				}

			}

			// indices

			const indices = [];

			const spineCount = spine.length / 3;
			const crossSectionCount = crossSection.length / 2;

			for ( let i = 0; i < spineCount - 1; i ++ ) {

				for ( let j = 0; j < crossSectionCount - 1; j ++ ) {

					const a = j + i * crossSectionCount;
					let b = ( j + 1 ) + i * crossSectionCount;
					const c = j + ( i + 1 ) * crossSectionCount;
					let d = ( j + 1 ) + ( i + 1 ) * crossSectionCount;

					if ( ( j === crossSectionCount - 2 ) && ( crossSectionClosed === true ) ) {

						b = i * crossSectionCount;
						d = ( i + 1 ) * crossSectionCount;

					}

					if ( ccw === true ) {

						indices.push( a, b, c );
						indices.push( c, b, d );

					} else {

						indices.push( a, c, b );
						indices.push( c, d, b );

					}

				}

			}

			// triangulate cap

			if ( beginCap === true || endCap === true ) {

				const contour = [];

				for ( let i = 0, l = crossSection.length; i < l; i += 2 ) {

					contour.push( new Vector2( crossSection[ i ], crossSection[ i + 1 ] ) );

				}

				const faces = ShapeUtils.triangulateShape( contour, [] );
				const capIndices = [];

				for ( let i = 0, l = faces.length; i < l; i ++ ) {

					const face = faces[ i ];

					capIndices.push( face[ 0 ], face[ 1 ], face[ 2 ] );

				}

				// begin cap

				if ( beginCap === true ) {

					for ( let i = 0, l = capIndices.length; i < l; i += 3 ) {

						if ( ccw === true ) {

							indices.push( capIndices[ i + 0 ], capIndices[ i + 1 ], capIndices[ i + 2 ] );

						} else {

							indices.push( capIndices[ i + 0 ], capIndices[ i + 2 ], capIndices[ i + 1 ] );

						}

					}

				}

				// end cap

				if ( endCap === true ) {

					const indexOffset = crossSectionCount * ( spineCount - 1 ); // references to the first vertex of the last cross section

					for ( let i = 0, l = capIndices.length; i < l; i += 3 ) {

						if ( ccw === true ) {

							indices.push( indexOffset + capIndices[ i + 0 ], indexOffset + capIndices[ i + 2 ], indexOffset + capIndices[ i + 1 ] );

						} else {

							indices.push( indexOffset + capIndices[ i + 0 ], indexOffset + capIndices[ i + 1 ], indexOffset + capIndices[ i + 2 ] );

						}

					}

				}

			}

			const positionAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( vertices, 3 ) );
			const normalAttribute = computeNormalAttribute( indices, vertices, creaseAngle );

			const geometry = new BufferGeometry();
			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );
			// no uvs yet

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}

		// helper functions

		function resolveUSE( identifier ) {

			const node = nodeMap[ identifier ];
			const build = getNode( node );

			// because the same 3D objects can have different transformations, it's necessary to clone them.
			// materials can be influenced by the geometry (e.g. vertex normals). cloning is necessary to avoid
			// any side effects

			return ( build.isObject3D || build.isMaterial ) ? build.clone() : build;

		}

		function parseFieldChildren( children, owner ) {

			for ( let i = 0, l = children.length; i < l; i ++ ) {

				const object = getNode( children[ i ] );

				if ( object instanceof Object3D ) owner.add( object );

			}

		}

		function triangulateFaceIndex( index, ccw ) {

			const indices = [];

			// since face definitions can have more than three vertices, it's necessary to
			// perform a simple triangulation

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ start ];
				const i2 = index[ i + ( ccw ? 1 : 2 ) ];
				const i3 = index[ i + ( ccw ? 2 : 1 ) ];

				indices.push( i1, i2, i3 );

				// an index of -1 indicates that the current face has ended and the next one begins

				if ( index[ i + 3 ] === - 1 || i + 3 >= l ) {

					i += 3;
					start = i + 1;

				}

			}

			return indices;

		}

		function triangulateFaceData( data, index ) {

			const triangulatedData = [];

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const stride = start * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				triangulatedData.push( x, y, z );

				// an index of -1 indicates that the current face has ended and the next one begins

				if ( index[ i + 3 ] === - 1 || i + 3 >= l ) {

					i += 3;
					start ++;

				}

			}

			return triangulatedData;

		}

		function flattenData( data, index ) {

			const flattenData = [];

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ i ];

				const stride = i1 * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				flattenData.push( x, y, z );

			}

			return flattenData;

		}

		function expandLineIndex( index ) {

			const indices = [];

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ i ];
				const i2 = index[ i + 1 ];

				indices.push( i1, i2 );

				// an index of -1 indicates that the current line has ended and the next one begins

				if ( index[ i + 2 ] === - 1 || i + 2 >= l ) {

					i += 2;

				}

			}

			return indices;

		}

		function expandLineData( data, index ) {

			const triangulatedData = [];

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const stride = start * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				triangulatedData.push( x, y, z );

				// an index of -1 indicates that the current line has ended and the next one begins

				if ( index[ i + 2 ] === - 1 || i + 2 >= l ) {

					i += 2;
					start ++;

				}

			}

			return triangulatedData;

		}

		const vA = new Vector3();
		const vB = new Vector3();
		const vC = new Vector3();

		const uvA = new Vector2();
		const uvB = new Vector2();
		const uvC = new Vector2();

		function computeAttributeFromIndexedData( coordIndex, index, data, itemSize ) {

			const array = [];

			// we use the coordIndex.length as delimiter since normalIndex must contain at least as many indices

			for ( let i = 0, l = coordIndex.length; i < l; i += 3 ) {

				const a = index[ i ];
				const b = index[ i + 1 ];
				const c = index[ i + 2 ];

				if ( itemSize === 2 ) {

					uvA.fromArray( data, a * itemSize );
					uvB.fromArray( data, b * itemSize );
					uvC.fromArray( data, c * itemSize );

					array.push( uvA.x, uvA.y );
					array.push( uvB.x, uvB.y );
					array.push( uvC.x, uvC.y );

				} else {

					vA.fromArray( data, a * itemSize );
					vB.fromArray( data, b * itemSize );
					vC.fromArray( data, c * itemSize );

					array.push( vA.x, vA.y, vA.z );
					array.push( vB.x, vB.y, vB.z );
					array.push( vC.x, vC.y, vC.z );

				}

			}

			return new Float32BufferAttribute( array, itemSize );

		}

		function computeAttributeFromFaceData( index, faceData ) {

			const array = [];

			for ( let i = 0, j = 0, l = index.length; i < l; i += 3, j ++ ) {

				vA.fromArray( faceData, j * 3 );

				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );

			}

			return new Float32BufferAttribute( array, 3 );

		}

		function computeAttributeFromLineData( index, lineData ) {

			const array = [];

			for ( let i = 0, j = 0, l = index.length; i < l; i += 2, j ++ ) {

				vA.fromArray( lineData, j * 3 );

				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );

			}

			return new Float32BufferAttribute( array, 3 );

		}

		function toNonIndexedAttribute( indices, attribute ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				index = indices[ i ] * itemSize;

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new Float32BufferAttribute( array2, itemSize );

		}

		const ab = new Vector3();
		const cb = new Vector3();

		function computeNormalAttribute( index, coord, creaseAngle ) {

			const faces = [];
			const vertexNormals = {};

			// prepare face and raw vertex normals

			for ( let i = 0, l = index.length; i < l; i += 3 ) {

				const a = index[ i ];
				const b = index[ i + 1 ];
				const c = index[ i + 2 ];

				const face = new Face( a, b, c );

				vA.fromArray( coord, a * 3 );
				vB.fromArray( coord, b * 3 );
				vC.fromArray( coord, c * 3 );

				cb.subVectors( vC, vB );
				ab.subVectors( vA, vB );
				cb.cross( ab );

				cb.normalize();

				face.normal.copy( cb );

				if ( vertexNormals[ a ] === undefined ) vertexNormals[ a ] = [];
				if ( vertexNormals[ b ] === undefined ) vertexNormals[ b ] = [];
				if ( vertexNormals[ c ] === undefined ) vertexNormals[ c ] = [];

				vertexNormals[ a ].push( face.normal );
				vertexNormals[ b ].push( face.normal );
				vertexNormals[ c ].push( face.normal );

				faces.push( face );

			}

			// compute vertex normals and build final geometry

			const normals = [];

			for ( let i = 0, l = faces.length; i < l; i ++ ) {

				const face = faces[ i ];

				const nA = weightedNormal( vertexNormals[ face.a ], face.normal, creaseAngle );
				const nB = weightedNormal( vertexNormals[ face.b ], face.normal, creaseAngle );
				const nC = weightedNormal( vertexNormals[ face.c ], face.normal, creaseAngle );

				vA.fromArray( coord, face.a * 3 );
				vB.fromArray( coord, face.b * 3 );
				vC.fromArray( coord, face.c * 3 );

				normals.push( nA.x, nA.y, nA.z );
				normals.push( nB.x, nB.y, nB.z );
				normals.push( nC.x, nC.y, nC.z );

			}

			return new Float32BufferAttribute( normals, 3 );

		}

		function weightedNormal( normals, vector, creaseAngle ) {

			const normal = new Vector3();

			if ( creaseAngle === 0 ) {

				normal.copy( vector );

			} else {

				for ( let i = 0, l = normals.length; i < l; i ++ ) {

					if ( normals[ i ].angleTo( vector ) < creaseAngle ) {

						normal.add( normals[ i ] );

					}

				}

			}

			return normal.normalize();

		}

		function toColorArray( colors ) {

			const array = [];

			for ( let i = 0, l = colors.length; i < l; i += 3 ) {

				array.push( new Color( colors[ i ], colors[ i + 1 ], colors[ i + 2 ] ) );

			}

			return array;

		}

		function convertColorsToLinearSRGB( attribute ) {

			const color = new Color();

			for ( let i = 0; i < attribute.count; i ++ ) {

				color.fromBufferAttribute( attribute, i );

				ColorManagement.colorSpaceToWorking( color, SRGBColorSpace );

				attribute.setXYZ( i, color.r, color.g, color.b );

			}

		}

		/**
		 * Vertically paints the faces interpolating between the
		 * specified colors at the specified angels. This is used for the Background
		 * node, but could be applied to other nodes with multiple faces as well.
		 *
		 * When used with the Background node, default is directionIsDown is true if
		 * interpolating the skyColor down from the Zenith. When interpolating up from
		 * the Nadir i.e. interpolating the groundColor, the directionIsDown is false.
		 *
		 * The first angle is never specified, it is the Zenith (0 rad). Angles are specified
		 * in radians. The geometry is thought a sphere, but could be anything. The color interpolation
		 * is linear along the Y axis in any case.
		 *
		 * You must specify one more color than you have angles at the beginning of the colors array.
		 * This is the color of the Zenith (the top of the shape).
		 *
		 * @param {BufferGeometry} geometry
		 * @param {number} radius
		 * @param {array} angles
		 * @param {array} colors
		 * @param {boolean} topDown - Whether to work top down or bottom up.
		 */
		function paintFaces( geometry, radius, angles, colors, topDown ) {

			// compute threshold values

			const thresholds = [];
			const startAngle = ( topDown === true ) ? 0 : Math.PI;

			for ( let i = 0, l = colors.length; i < l; i ++ ) {

				let angle = ( i === 0 ) ? 0 : angles[ i - 1 ];
				angle = ( topDown === true ) ? angle : ( startAngle - angle );

				const point = new Vector3();
				point.setFromSphericalCoords( radius, angle, 0 );

				thresholds.push( point );

			}

			// generate vertex colors

			const indices = geometry.index;
			const positionAttribute = geometry.attributes.position;
			const colorAttribute = new BufferAttribute( new Float32Array( geometry.attributes.position.count * 3 ), 3 );

			const position = new Vector3();
			const color = new Color();

			for ( let i = 0; i < indices.count; i ++ ) {

				const index = indices.getX( i );
				position.fromBufferAttribute( positionAttribute, index );

				let thresholdIndexA, thresholdIndexB;
				let t = 1;

				for ( let j = 1; j < thresholds.length; j ++ ) {

					thresholdIndexA = j - 1;
					thresholdIndexB = j;

					const thresholdA = thresholds[ thresholdIndexA ];
					const thresholdB = thresholds[ thresholdIndexB ];

					if ( topDown === true ) {

						// interpolation for sky color

						if ( position.y <= thresholdA.y && position.y > thresholdB.y ) {

							t = Math.abs( thresholdA.y - position.y ) / Math.abs( thresholdA.y - thresholdB.y );

							break;

						}

					} else {

						// interpolation for ground color

						if ( position.y >= thresholdA.y && position.y < thresholdB.y ) {

							t = Math.abs( thresholdA.y - position.y ) / Math.abs( thresholdA.y - thresholdB.y );

							break;

						}

					}

				}

				const colorA = colors[ thresholdIndexA ];
				const colorB = colors[ thresholdIndexB ];

				color.copy( colorA ).lerp( colorB, t );

				ColorManagement.colorSpaceToWorking( color, SRGBColorSpace );

				colorAttribute.setXYZ( index, color.r, color.g, color.b );

			}

			geometry.setAttribute( 'color', colorAttribute );

		}

		//

		const textureLoader = new TextureLoader( this.manager );
		textureLoader.setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		// check version (only 2.0 is supported)

		if ( data.indexOf( '#VRML V2.0' ) === - 1 ) {

			throw Error( 'THREE.VRMLLexer: Version of VRML asset not supported.' );

		}

		// create JSON representing the tree structure of the VRML asset

		const tree = generateVRMLTree( data );

		// parse the tree structure to a three.js scene

		const scene = parseTree( tree );

		return scene;

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: Scene) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

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

##### `parse(data: string, path: string): Scene`

<details><summary>Code</summary>

```ts
parse( data, path ) {

		const nodeMap = {};

		function generateVRMLTree( data ) {

			// create lexer, parser and visitor

			const tokenData = createTokens();

			const lexer = new VRMLLexer( tokenData.tokens );
			const parser = new VRMLParser( tokenData.tokenVocabulary );
			const visitor = createVisitor( parser.getBaseCstVisitorConstructor() );

			// lexing

			const lexingResult = lexer.lex( data );
			parser.input = lexingResult.tokens;

			// parsing

			const cstOutput = parser.vrml();

			if ( parser.errors.length > 0 ) {

				console.error( parser.errors );

				throw Error( 'THREE.VRMLLoader: Parsing errors detected.' );

			}

			// actions

			const ast = visitor.visit( cstOutput );

			return ast;

		}

		function createTokens() {

			const createToken = chevrotain.createToken;

			// from http://gun.teipir.gr/VRML-amgem/spec/part1/concepts.html#SyntaxBasics

			const RouteIdentifier = createToken( { name: 'RouteIdentifier', pattern: /[^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d][^\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]*[\.][^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d][^\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]*/ } );
			const Identifier = createToken( { name: 'Identifier', pattern: /[^\x30-\x39\0-\x20\x22\x27\x23\x2b\x2c\x2d\x2e\x5b\x5d\x5c\x7b\x7d]([^\0-\x20\x22\x27\x23\x2b\x2c\x2e\x5b\x5d\x5c\x7b\x7d])*/, longer_alt: RouteIdentifier } );

			// from http://gun.teipir.gr/VRML-amgem/spec/part1/nodesRef.html

			const nodeTypes = [
				'Anchor', 'Billboard', 'Collision', 'Group', 'Transform', // grouping nodes
				'Inline', 'LOD', 'Switch', // special groups
				'AudioClip', 'DirectionalLight', 'PointLight', 'Script', 'Shape', 'Sound', 'SpotLight', 'WorldInfo', // common nodes
				'CylinderSensor', 'PlaneSensor', 'ProximitySensor', 'SphereSensor', 'TimeSensor', 'TouchSensor', 'VisibilitySensor', // sensors
				'Box', 'Cone', 'Cylinder', 'ElevationGrid', 'Extrusion', 'IndexedFaceSet', 'IndexedLineSet', 'PointSet', 'Sphere', // geometries
				'Color', 'Coordinate', 'Normal', 'TextureCoordinate', // geometric properties
				'Appearance', 'FontStyle', 'ImageTexture', 'Material', 'MovieTexture', 'PixelTexture', 'TextureTransform', // appearance
				'ColorInterpolator', 'CoordinateInterpolator', 'NormalInterpolator', 'OrientationInterpolator', 'PositionInterpolator', 'ScalarInterpolator', // interpolators
				'Background', 'Fog', 'NavigationInfo', 'Viewpoint', // bindable nodes
				'Text' // Text must be placed at the end of the regex so there are no matches for TextureTransform and TextureCoordinate
			];

			//

			const Version = createToken( {
				name: 'Version',
				pattern: /#VRML.*/,
				longer_alt: Identifier
			} );

			const NodeName = createToken( {
				name: 'NodeName',
				pattern: new RegExp( nodeTypes.join( '|' ) ),
				longer_alt: Identifier
			} );

			const DEF = createToken( {
				name: 'DEF',
				pattern: /DEF/,
				longer_alt: Identifier
			} );

			const USE = createToken( {
				name: 'USE',
				pattern: /USE/,
				longer_alt: Identifier
			} );

			const ROUTE = createToken( {
				name: 'ROUTE',
				pattern: /ROUTE/,
				longer_alt: Identifier
			} );

			const TO = createToken( {
				name: 'TO',
				pattern: /TO/,
				longer_alt: Identifier
			} );

			//

			const StringLiteral = createToken( { name: 'StringLiteral', pattern: /"(?:[^\\"\n\r]|\\[bfnrtv"\\/]|\\u[0-9a-fA-F][0-9a-fA-F][0-9a-fA-F][0-9a-fA-F])*"/ } );
			const HexLiteral = createToken( { name: 'HexLiteral', pattern: /0[xX][0-9a-fA-F]+/ } );
			const NumberLiteral = createToken( { name: 'NumberLiteral', pattern: /[-+]?[0-9]*\.?[0-9]+([eE][-+]?[0-9]+)?/ } );
			const TrueLiteral = createToken( { name: 'TrueLiteral', pattern: /TRUE/ } );
			const FalseLiteral = createToken( { name: 'FalseLiteral', pattern: /FALSE/ } );
			const NullLiteral = createToken( { name: 'NullLiteral', pattern: /NULL/ } );
			const LSquare = createToken( { name: 'LSquare', pattern: /\[/ } );
			const RSquare = createToken( { name: 'RSquare', pattern: /]/ } );
			const LCurly = createToken( { name: 'LCurly', pattern: /{/ } );
			const RCurly = createToken( { name: 'RCurly', pattern: /}/ } );
			const Comment = createToken( {
				name: 'Comment',
				pattern: /#.*/,
				group: chevrotain.Lexer.SKIPPED
			} );

			// commas, blanks, tabs, newlines and carriage returns are whitespace characters wherever they appear outside of string fields

			const WhiteSpace = createToken( {
				name: 'WhiteSpace',
				pattern: /[ ,\s]/,
				group: chevrotain.Lexer.SKIPPED
			} );

			const tokens = [
				WhiteSpace,
				// keywords appear before the Identifier
				NodeName,
				DEF,
				USE,
				ROUTE,
				TO,
				TrueLiteral,
				FalseLiteral,
				NullLiteral,
				// the Identifier must appear after the keywords because all keywords are valid identifiers
				Version,
				Identifier,
				RouteIdentifier,
				StringLiteral,
				HexLiteral,
				NumberLiteral,
				LSquare,
				RSquare,
				LCurly,
				RCurly,
				Comment
			];

			const tokenVocabulary = {};

			for ( let i = 0, l = tokens.length; i < l; i ++ ) {

				const token = tokens[ i ];

				tokenVocabulary[ token.name ] = token;

			}

			return { tokens: tokens, tokenVocabulary: tokenVocabulary };

		}


		function createVisitor( BaseVRMLVisitor ) {

			// the visitor is created dynamically based on the given base class

			class VRMLToASTVisitor extends BaseVRMLVisitor {

				constructor() {

					super();

					this.validateVisitor();

				}

				vrml( ctx ) {

					const data = {
						version: this.visit( ctx.version ),
						nodes: [],
						routes: []
					};

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						data.nodes.push( this.visit( node ) );

					}

					if ( ctx.route ) {

						for ( let i = 0, l = ctx.route.length; i < l; i ++ ) {

							const route = ctx.route[ i ];

							data.routes.push( this.visit( route ) );

						}

					}

					return data;

				}

				version( ctx ) {

					return ctx.Version[ 0 ].image;

				}

				node( ctx ) {

					const data = {
						name: ctx.NodeName[ 0 ].image,
						fields: []
					};

					if ( ctx.field ) {

						for ( let i = 0, l = ctx.field.length; i < l; i ++ ) {

							const field = ctx.field[ i ];

							data.fields.push( this.visit( field ) );

						}

					}

					// DEF

					if ( ctx.def ) {

						data.DEF = this.visit( ctx.def[ 0 ] );

					}

					return data;

				}

				field( ctx ) {

					const data = {
						name: ctx.Identifier[ 0 ].image,
						type: null,
						values: null
					};

					let result;

					// SFValue

					if ( ctx.singleFieldValue ) {

						result = this.visit( ctx.singleFieldValue[ 0 ] );

					}

					// MFValue

					if ( ctx.multiFieldValue ) {

						result = this.visit( ctx.multiFieldValue[ 0 ] );

					}

					data.type = result.type;
					data.values = result.values;

					return data;

				}

				def( ctx ) {

					return ( ctx.Identifier || ctx.NodeName )[ 0 ].image;

				}

				use( ctx ) {

					return { USE: ( ctx.Identifier || ctx.NodeName )[ 0 ].image };

				}

				singleFieldValue( ctx ) {

					return processField( this, ctx );

				}

				multiFieldValue( ctx ) {

					return processField( this, ctx );

				}

				route( ctx ) {

					const data = {
						FROM: ctx.RouteIdentifier[ 0 ].image,
						TO: ctx.RouteIdentifier[ 1 ].image
					};

					return data;

				}

			}

			function processField( scope, ctx ) {

				const field = {
					type: null,
					values: []
				};

				if ( ctx.node ) {

					field.type = 'node';

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						field.values.push( scope.visit( node ) );

					}

				}

				if ( ctx.use ) {

					field.type = 'use';

					for ( let i = 0, l = ctx.use.length; i < l; i ++ ) {

						const use = ctx.use[ i ];

						field.values.push( scope.visit( use ) );

					}

				}

				if ( ctx.StringLiteral ) {

					field.type = 'string';

					for ( let i = 0, l = ctx.StringLiteral.length; i < l; i ++ ) {

						const stringLiteral = ctx.StringLiteral[ i ];

						field.values.push( stringLiteral.image.replace( /'|"/g, '' ) );

					}

				}

				if ( ctx.NumberLiteral ) {

					field.type = 'number';

					for ( let i = 0, l = ctx.NumberLiteral.length; i < l; i ++ ) {

						const numberLiteral = ctx.NumberLiteral[ i ];

						field.values.push( parseFloat( numberLiteral.image ) );

					}

				}

				if ( ctx.HexLiteral ) {

					field.type = 'hex';

					for ( let i = 0, l = ctx.HexLiteral.length; i < l; i ++ ) {

						const hexLiteral = ctx.HexLiteral[ i ];

						field.values.push( hexLiteral.image );

					}

				}

				if ( ctx.TrueLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.TrueLiteral.length; i < l; i ++ ) {

						const trueLiteral = ctx.TrueLiteral[ i ];

						if ( trueLiteral.image === 'TRUE' ) field.values.push( true );

					}

				}

				if ( ctx.FalseLiteral ) {

					field.type = 'boolean';

					for ( let i = 0, l = ctx.FalseLiteral.length; i < l; i ++ ) {

						const falseLiteral = ctx.FalseLiteral[ i ];

						if ( falseLiteral.image === 'FALSE' ) field.values.push( false );

					}

				}

				if ( ctx.NullLiteral ) {

					field.type = 'null';

					ctx.NullLiteral.forEach( function () {

						field.values.push( null );

					} );

				}

				return field;

			}

			return new VRMLToASTVisitor();

		}

		function parseTree( tree ) {

			// console.log( JSON.stringify( tree, null, 2 ) );

			const nodes = tree.nodes;
			const scene = new Scene();

			// first iteration: build nodemap based on DEF statements

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				const node = nodes[ i ];

				buildNodeMap( node );

			}

			// second iteration: build nodes

			for ( let i = 0, l = nodes.length; i < l; i ++ ) {

				const node = nodes[ i ];
				const object = getNode( node );

				if ( object instanceof Object3D ) scene.add( object );

				if ( node.name === 'WorldInfo' ) scene.userData.worldInfo = object;

			}

			return scene;

		}

		function buildNodeMap( node ) {

			if ( node.DEF ) {

				nodeMap[ node.DEF ] = node;

			}

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];

				if ( field.type === 'node' ) {

					const fieldValues = field.values;

					for ( let j = 0, jl = fieldValues.length; j < jl; j ++ ) {

						buildNodeMap( fieldValues[ j ] );

					}

				}


			}

		}


		function getNode( node ) {

			// handle case where a node refers to a different one

			if ( node.USE ) {

				return resolveUSE( node.USE );

			}

			if ( node.build !== undefined ) return node.build;

			node.build = buildNode( node );

			return node.build;

		}

		// node builder

		function buildNode( node ) {

			const nodeName = node.name;
			let build;

			switch ( nodeName ) {

				case 'Anchor':
				case 'Group':
				case 'Transform':
				case 'Collision':
					build = buildGroupingNode( node );
					break;

				case 'Background':
					build = buildBackgroundNode( node );
					break;

				case 'Shape':
					build = buildShapeNode( node );
					break;

				case 'Appearance':
					build = buildAppearanceNode( node );
					break;

				case 'Material':
					build = buildMaterialNode( node );
					break;

				case 'ImageTexture':
					build = buildImageTextureNode( node );
					break;

				case 'PixelTexture':
					build = buildPixelTextureNode( node );
					break;

				case 'TextureTransform':
					build = buildTextureTransformNode( node );
					break;

				case 'IndexedFaceSet':
					build = buildIndexedFaceSetNode( node );
					break;

				case 'IndexedLineSet':
					build = buildIndexedLineSetNode( node );
					break;

				case 'PointSet':
					build = buildPointSetNode( node );
					break;

				case 'Box':
					build = buildBoxNode( node );
					break;

				case 'Cone':
					build = buildConeNode( node );
					break;

				case 'Cylinder':
					build = buildCylinderNode( node );
					break;

				case 'Sphere':
					build = buildSphereNode( node );
					break;

				case 'ElevationGrid':
					build = buildElevationGridNode( node );
					break;

				case 'Extrusion':
					build = buildExtrusionNode( node );
					break;

				case 'Color':
				case 'Coordinate':
				case 'Normal':
				case 'TextureCoordinate':
					build = buildGeometricNode( node );
					break;

				case 'WorldInfo':
					build = buildWorldInfoNode( node );
					break;

				case 'Billboard':

				case 'Inline':
				case 'LOD':
				case 'Switch':

				case 'AudioClip':
				case 'DirectionalLight':
				case 'PointLight':
				case 'Script':
				case 'Sound':
				case 'SpotLight':

				case 'CylinderSensor':
				case 'PlaneSensor':
				case 'ProximitySensor':
				case 'SphereSensor':
				case 'TimeSensor':
				case 'TouchSensor':
				case 'VisibilitySensor':

				case 'Text':

				case 'FontStyle':
				case 'MovieTexture':

				case 'ColorInterpolator':
				case 'CoordinateInterpolator':
				case 'NormalInterpolator':
				case 'OrientationInterpolator':
				case 'PositionInterpolator':
				case 'ScalarInterpolator':

				case 'Fog':
				case 'NavigationInfo':
				case 'Viewpoint':
					// node not supported yet
					break;

				default:
					console.warn( 'THREE.VRMLLoader: Unknown node:', nodeName );
					break;

			}

			if ( build !== undefined && node.DEF !== undefined && build.hasOwnProperty( 'name' ) === true ) {

				build.name = node.DEF;

			}

			return build;

		}

		function buildGroupingNode( node ) {

			const object = new Group();

			//

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bboxCenter':
						// field not supported
						break;

					case 'bboxSize':
						// field not supported
						break;

					case 'center':
						// field not supported
						break;

					case 'children':
						parseFieldChildren( fieldValues, object );
						break;

					case 'description':
						// field not supported
						break;

					case 'collide':
						// field not supported
						break;

					case 'parameter':
						// field not supported
						break;

					case 'rotation':
						const axis = new Vector3( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] ).normalize();
						const angle = fieldValues[ 3 ];
						object.quaternion.setFromAxisAngle( axis, angle );
						break;

					case 'scale':
						object.scale.set( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] );
						break;

					case 'scaleOrientation':
						// field not supported
						break;

					case 'translation':
						object.position.set( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ] );
						break;

					case 'proxy':
						// field not supported
						break;

					case 'url':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return object;

		}

		function buildBackgroundNode( node ) {

			const group = new Group();

			let groundAngle, groundColor;
			let skyAngle, skyColor;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'groundAngle':
						groundAngle = fieldValues;
						break;

					case 'groundColor':
						groundColor = fieldValues;
						break;

					case 'backUrl':
						// field not supported
						break;

					case 'bottomUrl':
						// field not supported
						break;

					case 'frontUrl':
						// field not supported
						break;

					case 'leftUrl':
						// field not supported
						break;

					case 'rightUrl':
						// field not supported
						break;

					case 'topUrl':
						// field not supported
						break;

					case 'skyAngle':
						skyAngle = fieldValues;
						break;

					case 'skyColor':
						skyColor = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const radius = 10000;

			// sky

			if ( skyColor ) {

				const skyGeometry = new SphereGeometry( radius, 32, 16 );
				const skyMaterial = new MeshBasicMaterial( { fog: false, side: BackSide, depthWrite: false, depthTest: false } );

				if ( skyColor.length > 3 ) {

					paintFaces( skyGeometry, radius, skyAngle, toColorArray( skyColor ), true );
					skyMaterial.vertexColors = true;

				} else {

					skyMaterial.color.setRGB( skyColor[ 0 ], skyColor[ 1 ], skyColor[ 2 ], SRGBColorSpace );

				}

				const sky = new Mesh( skyGeometry, skyMaterial );
				group.add( sky );

			}

			// ground

			if ( groundColor ) {

				if ( groundColor.length > 0 ) {

					const groundGeometry = new SphereGeometry( radius, 32, 16, 0, 2 * Math.PI, 0.5 * Math.PI, 1.5 * Math.PI );
					const groundMaterial = new MeshBasicMaterial( { fog: false, side: BackSide, vertexColors: true, depthWrite: false, depthTest: false } );

					paintFaces( groundGeometry, radius, groundAngle, toColorArray( groundColor ), false );

					const ground = new Mesh( groundGeometry, groundMaterial );
					group.add( ground );

				}

			}

			// render background group first

			group.renderOrder = - Infinity;

			return group;

		}

		function buildShapeNode( node ) {

			const fields = node.fields;

			// if the appearance field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0)

			let material = new MeshBasicMaterial( {
				name: Loader.DEFAULT_MATERIAL_NAME,
				color: 0x000000
			} );
			let geometry;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'appearance':
						if ( fieldValues[ 0 ] !== null ) {

							material = getNode( fieldValues[ 0 ] );

						}

						break;

					case 'geometry':
						if ( fieldValues[ 0 ] !== null ) {

							geometry = getNode( fieldValues[ 0 ] );

						}

						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// build 3D object

			let object;

			if ( geometry && geometry.attributes.position ) {

				const type = geometry._type;

				if ( type === 'points' ) { // points

					const pointsMaterial = new PointsMaterial( {
						name: Loader.DEFAULT_MATERIAL_NAME,
						color: 0xffffff,
						opacity: material.opacity,
						transparent: material.transparent
					} );

					if ( geometry.attributes.color !== undefined ) {

						pointsMaterial.vertexColors = true;

					} else {

						// if the color field is NULL and there is a material defined for the appearance affecting this PointSet, then use the emissiveColor of the material to draw the points

						if ( material.isMeshPhongMaterial ) {

							pointsMaterial.color.copy( material.emissive );

						}

					}

					object = new Points( geometry, pointsMaterial );

				} else if ( type === 'line' ) { // lines

					const lineMaterial = new LineBasicMaterial( {
						name: Loader.DEFAULT_MATERIAL_NAME,
						color: 0xffffff,
						opacity: material.opacity,
						transparent: material.transparent
					} );

					if ( geometry.attributes.color !== undefined ) {

						lineMaterial.vertexColors = true;

					} else {

						// if the color field is NULL and there is a material defined for the appearance affecting this IndexedLineSet, then use the emissiveColor of the material to draw the lines

						if ( material.isMeshPhongMaterial ) {

							lineMaterial.color.copy( material.emissive );

						}

					}

					object = new LineSegments( geometry, lineMaterial );

				} else { // consider meshes

					// check "solid" hint (it's placed in the geometry but affects the material)

					if ( geometry._solid !== undefined ) {

						material.side = ( geometry._solid ) ? FrontSide : DoubleSide;

					}

					// check for vertex colors

					if ( geometry.attributes.color !== undefined ) {

						material.vertexColors = true;

					}

					object = new Mesh( geometry, material );

				}

			} else {

				object = new Object3D();

				// if the geometry field is NULL or no vertices are defined the object is not drawn

				object.visible = false;

			}

			return object;

		}

		function buildAppearanceNode( node ) {

			let material = new MeshPhongMaterial();
			let transformData;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'material':
						if ( fieldValues[ 0 ] !== null ) {

							const materialData = getNode( fieldValues[ 0 ] );

							if ( materialData.diffuseColor ) material.color.copy( materialData.diffuseColor );
							if ( materialData.emissiveColor ) material.emissive.copy( materialData.emissiveColor );
							if ( materialData.shininess ) material.shininess = materialData.shininess;
							if ( materialData.specularColor ) material.specular.copy( materialData.specularColor );
							if ( materialData.transparency ) material.opacity = 1 - materialData.transparency;
							if ( materialData.transparency > 0 ) material.transparent = true;

						} else {

							// if the material field is NULL or unspecified, lighting is off and the unlit object color is (0, 0, 0)

							material = new MeshBasicMaterial( {
								name: Loader.DEFAULT_MATERIAL_NAME,
								color: 0x000000
							} );

						}

						break;

					case 'texture':
						const textureNode = fieldValues[ 0 ];
						if ( textureNode !== null ) {

							if ( textureNode.name === 'ImageTexture' || textureNode.name === 'PixelTexture' ) {

								material.map = getNode( textureNode );

							} else {

								// MovieTexture not supported yet

							}

						}

						break;

					case 'textureTransform':
						if ( fieldValues[ 0 ] !== null ) {

							transformData = getNode( fieldValues[ 0 ] );

						}

						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// only apply texture transform data if a texture was defined

			if ( material.map ) {

				// respect VRML lighting model

				if ( material.map.__type ) {

					switch ( material.map.__type ) {

						case TEXTURE_TYPE.INTENSITY_ALPHA:
							material.opacity = 1; // ignore transparency
							break;

						case TEXTURE_TYPE.RGB:
							material.color.set( 0xffffff ); // ignore material color
							break;

						case TEXTURE_TYPE.RGBA:
							material.color.set( 0xffffff ); // ignore material color
							material.opacity = 1; // ignore transparency
							break;

						default:

					}

					delete material.map.__type;

				}

				// apply texture transform

				if ( transformData ) {

					material.map.center.copy( transformData.center );
					material.map.rotation = transformData.rotation;
					material.map.repeat.copy( transformData.scale );
					material.map.offset.copy( transformData.translation );

				}

			}

			return material;

		}

		function buildMaterialNode( node ) {

			const materialData = {};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'ambientIntensity':
						// field not supported
						break;

					case 'diffuseColor':
						materialData.diffuseColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'emissiveColor':
						materialData.emissiveColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'shininess':
						materialData.shininess = fieldValues[ 0 ];
						break;

					case 'specularColor':
						materialData.specularColor = new Color().setRGB( fieldValues[ 0 ], fieldValues[ 1 ], fieldValues[ 2 ], SRGBColorSpace );
						break;

					case 'transparency':
						materialData.transparency = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return materialData;

		}

		function parseHexColor( hex, textureType, color ) {

			let value;

			switch ( textureType ) {

				case TEXTURE_TYPE.INTENSITY:
					// Intensity texture: A one-component image specifies one-byte hexadecimal or integer values representing the intensity of the image
					value = parseInt( hex );
					color.r = value;
					color.g = value;
					color.b = value;
					color.a = 1;
					break;

				case TEXTURE_TYPE.INTENSITY_ALPHA:
					// Intensity+Alpha texture: A two-component image specifies the intensity in the first (high) byte and the alpha opacity in the second (low) byte.
					value = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.r = value;
					color.g = value;
					color.b = value;
					color.a = parseInt( '0x' + hex.substring( 4, 6 ) );
					break;

				case TEXTURE_TYPE.RGB:
					// RGB texture: Pixels in a three-component image specify the red component in the first (high) byte, followed by the green and blue components
					color.r = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.g = parseInt( '0x' + hex.substring( 4, 6 ) );
					color.b = parseInt( '0x' + hex.substring( 6, 8 ) );
					color.a = 1;
					break;

				case TEXTURE_TYPE.RGBA:
					// RGBA texture: Four-component images specify the alpha opacity byte after red/green/blue
					color.r = parseInt( '0x' + hex.substring( 2, 4 ) );
					color.g = parseInt( '0x' + hex.substring( 4, 6 ) );
					color.b = parseInt( '0x' + hex.substring( 6, 8 ) );
					color.a = parseInt( '0x' + hex.substring( 8, 10 ) );
					break;

				default:

			}

		}

		function getTextureType( num_components ) {

			let type;

			switch ( num_components ) {

				case 1:
					type = TEXTURE_TYPE.INTENSITY;
					break;

				case 2:
					type = TEXTURE_TYPE.INTENSITY_ALPHA;
					break;

				case 3:
					type = TEXTURE_TYPE.RGB;
					break;

				case 4:
					type = TEXTURE_TYPE.RGBA;
					break;

				default:

			}

			return type;

		}

		function buildPixelTextureNode( node ) {

			let texture;
			let wrapS = RepeatWrapping;
			let wrapT = RepeatWrapping;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'image':
						const width = fieldValues[ 0 ];
						const height = fieldValues[ 1 ];
						const num_components = fieldValues[ 2 ];

						const textureType = getTextureType( num_components );

						const data = new Uint8Array( 4 * width * height );

						const color = { r: 0, g: 0, b: 0, a: 0 };

						for ( let j = 3, k = 0, jl = fieldValues.length; j < jl; j ++, k ++ ) {

							parseHexColor( fieldValues[ j ], textureType, color );

							const stride = k * 4;

							data[ stride + 0 ] = color.r;
							data[ stride + 1 ] = color.g;
							data[ stride + 2 ] = color.b;
							data[ stride + 3 ] = color.a;

						}

						texture = new DataTexture( data, width, height );
						texture.colorSpace = SRGBColorSpace;
						texture.needsUpdate = true;
						texture.__type = textureType; // needed for material modifications
						break;

					case 'repeatS':
						if ( fieldValues[ 0 ] === false ) wrapS = ClampToEdgeWrapping;
						break;

					case 'repeatT':
						if ( fieldValues[ 0 ] === false ) wrapT = ClampToEdgeWrapping;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( texture ) {

				texture.wrapS = wrapS;
				texture.wrapT = wrapT;

			}

			return texture;

		}

		function buildImageTextureNode( node ) {

			let texture;
			let wrapS = RepeatWrapping;
			let wrapT = RepeatWrapping;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'url':
						const url = fieldValues[ 0 ];
						if ( url ) texture = textureLoader.load( url );
						break;

					case 'repeatS':
						if ( fieldValues[ 0 ] === false ) wrapS = ClampToEdgeWrapping;
						break;

					case 'repeatT':
						if ( fieldValues[ 0 ] === false ) wrapT = ClampToEdgeWrapping;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( texture ) {

				texture.wrapS = wrapS;
				texture.wrapT = wrapT;
				texture.colorSpace = SRGBColorSpace;

			}

			return texture;

		}

		function buildTextureTransformNode( node ) {

			const transformData = {
				center: new Vector2(),
				rotation: new Vector2(),
				scale: new Vector2(),
				translation: new Vector2()
			};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'center':
						transformData.center.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					case 'rotation':
						transformData.rotation = fieldValues[ 0 ];
						break;

					case 'scale':
						transformData.scale.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					case 'translation':
						transformData.translation.set( fieldValues[ 0 ], fieldValues[ 1 ] );
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return transformData;

		}

		function buildGeometricNode( node ) {

			return node.fields[ 0 ].values;

		}

		function buildWorldInfoNode( node ) {

			const worldInfo = {};

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'title':
						worldInfo.title = fieldValues[ 0 ];
						break;

					case 'info':
						worldInfo.info = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			return worldInfo;

		}

		function buildIndexedFaceSetNode( node ) {

			let color, coord, normal, texCoord;
			let ccw = true, solid = true, creaseAngle = 0;
			let colorIndex, coordIndex, normalIndex, texCoordIndex;
			let colorPerVertex = true, normalPerVertex = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;

					case 'normal':
						const normalNode = fieldValues[ 0 ];

						if ( normalNode !== null ) {

							normal = getNode( normalNode );

						}

						break;

					case 'texCoord':
						const texCoordNode = fieldValues[ 0 ];

						if ( texCoordNode !== null ) {

							texCoord = getNode( texCoordNode );

						}

						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'colorIndex':
						colorIndex = fieldValues;
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'convex':
						// field not supported
						break;

					case 'coordIndex':
						coordIndex = fieldValues;
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'normalIndex':
						normalIndex = fieldValues;
						break;

					case 'normalPerVertex':
						normalPerVertex = fieldValues[ 0 ];
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'texCoordIndex':
						texCoordIndex = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			if ( coordIndex === undefined ) {

				console.warn( 'THREE.VRMLLoader: Missing coordIndex.' );

				return new BufferGeometry(); // handle VRML files with incomplete geometry definition

			}

			const triangulatedCoordIndex = triangulateFaceIndex( coordIndex, ccw );

			let colorAttribute;
			let normalAttribute;
			let uvAttribute;

			if ( color ) {

				if ( colorPerVertex === true ) {

					if ( colorIndex && colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then it is used to choose colors for each vertex of the IndexedFaceSet.

						const triangulatedColorIndex = triangulateFaceIndex( colorIndex, ccw );
						colorAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedColorIndex, color, 3 );

					} else {

						// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node

						colorAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( color, 3 ) );

					}

				} else {

					if ( colorIndex && colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then they are used to choose one color for each face of the IndexedFaceSet

						const flattenFaceColors = flattenData( color, colorIndex );
						const triangulatedFaceColors = triangulateFaceData( flattenFaceColors, coordIndex );
						colorAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceColors );

					} else {

						// if the colorIndex field is empty, then the color are applied to each face of the IndexedFaceSet in order

						const triangulatedFaceColors = triangulateFaceData( color, coordIndex );
						colorAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceColors );


					}

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			if ( normal ) {

				if ( normalPerVertex === true ) {

					// consider vertex normals

					if ( normalIndex && normalIndex.length > 0 ) {

						// if the normalIndex field is not empty, then it is used to choose normals for each vertex of the IndexedFaceSet.

						const triangulatedNormalIndex = triangulateFaceIndex( normalIndex, ccw );
						normalAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedNormalIndex, normal, 3 );

					} else {

						// if the normalIndex field is empty, then the coordIndex field is used to choose normals from the Normal node

						normalAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( normal, 3 ) );

					}

				} else {

					// consider face normals

					if ( normalIndex && normalIndex.length > 0 ) {

						// if the normalIndex field is not empty, then they are used to choose one normal for each face of the IndexedFaceSet

						const flattenFaceNormals = flattenData( normal, normalIndex );
						const triangulatedFaceNormals = triangulateFaceData( flattenFaceNormals, coordIndex );
						normalAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceNormals );

					} else {

						// if the normalIndex field is empty, then the normals are applied to each face of the IndexedFaceSet in order

						const triangulatedFaceNormals = triangulateFaceData( normal, coordIndex );
						normalAttribute = computeAttributeFromFaceData( triangulatedCoordIndex, triangulatedFaceNormals );

					}

				}

			} else {

				// if the normal field is NULL, then the loader should automatically generate normals, using creaseAngle to determine if and how normals are smoothed across shared vertices

				normalAttribute = computeNormalAttribute( triangulatedCoordIndex, coord, creaseAngle );

			}

			if ( texCoord ) {

				// texture coordinates are always defined on vertex level

				if ( texCoordIndex && texCoordIndex.length > 0 ) {

					// if the texCoordIndex field is not empty, then it is used to choose texture coordinates for each vertex of the IndexedFaceSet.

					const triangulatedTexCoordIndex = triangulateFaceIndex( texCoordIndex, ccw );
					uvAttribute = computeAttributeFromIndexedData( triangulatedCoordIndex, triangulatedTexCoordIndex, texCoord, 2 );


				} else {

					// if the texCoordIndex field is empty, then the coordIndex array is used to choose texture coordinates from the TextureCoordinate node

					uvAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( texCoord, 2 ) );

				}

			}

			const geometry = new BufferGeometry();
			const positionAttribute = toNonIndexedAttribute( triangulatedCoordIndex, new Float32BufferAttribute( coord, 3 ) );

			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );

			// optional attributes

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );
			if ( uvAttribute ) geometry.setAttribute( 'uv', uvAttribute );

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}

		function buildIndexedLineSetNode( node ) {

			let color, coord;
			let colorIndex, coordIndex;
			let colorPerVertex = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;

					case 'colorIndex':
						colorIndex = fieldValues;
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'coordIndex':
						coordIndex = fieldValues;
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// build lines

			let colorAttribute;

			const expandedLineIndex = expandLineIndex( coordIndex ); // create an index for three.js's linesegment primitive

			if ( color ) {

				if ( colorPerVertex === true ) {

					if ( colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then one color is used for each polyline of the IndexedLineSet.

						const expandedColorIndex = expandLineIndex( colorIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromIndexedData( expandedLineIndex, expandedColorIndex, color, 3 ); // compute data on vertex level

					} else {

						// if the colorIndex field is empty, then the colors are applied to each polyline of the IndexedLineSet in order.

						colorAttribute = toNonIndexedAttribute( expandedLineIndex, new Float32BufferAttribute( color, 3 ) );

					}

				} else {

					if ( colorIndex.length > 0 ) {

						// if the colorIndex field is not empty, then colors are applied to each vertex of the IndexedLineSet

						const flattenLineColors = flattenData( color, colorIndex ); // compute colors for each VRML primitive
						const expandedLineColors = expandLineData( flattenLineColors, coordIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromLineData( expandedLineIndex, expandedLineColors ); // compute data on vertex level


					} else {

						// if the colorIndex field is empty, then the coordIndex field is used to choose colors from the Color node

						const expandedLineColors = expandLineData( color, coordIndex ); // compute colors for each line segment (rendering primitive)
						colorAttribute = computeAttributeFromLineData( expandedLineIndex, expandedLineColors ); // compute data on vertex level

					}

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			//

			const geometry = new BufferGeometry();

			const positionAttribute = toNonIndexedAttribute( expandedLineIndex, new Float32BufferAttribute( coord, 3 ) );
			geometry.setAttribute( 'position', positionAttribute );

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );

			geometry._type = 'line';

			return geometry;

		}

		function buildPointSetNode( node ) {

			let color, coord;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'coord':
						const coordNode = fieldValues[ 0 ];

						if ( coordNode !== null ) {

							coord = getNode( coordNode );

						}

						break;


					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new BufferGeometry();

			geometry.setAttribute( 'position', new Float32BufferAttribute( coord, 3 ) );

			if ( color ) {

				const colorAttribute = new Float32BufferAttribute( color, 3 );
				convertColorsToLinearSRGB( colorAttribute );

				geometry.setAttribute( 'color', colorAttribute );

			}

			geometry._type = 'points';

			return geometry;

		}

		function buildBoxNode( node ) {

			const size = new Vector3( 2, 2, 2 );

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'size':
						size.x = fieldValues[ 0 ];
						size.y = fieldValues[ 1 ];
						size.z = fieldValues[ 2 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new BoxGeometry( size.x, size.y, size.z );

			return geometry;

		}

		function buildConeNode( node ) {

			let radius = 1, height = 2, openEnded = false;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bottom':
						openEnded = ! fieldValues[ 0 ];
						break;

					case 'bottomRadius':
						radius = fieldValues[ 0 ];
						break;

					case 'height':
						height = fieldValues[ 0 ];
						break;

					case 'side':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new ConeGeometry( radius, height, 16, 1, openEnded );

			return geometry;

		}

		function buildCylinderNode( node ) {

			let radius = 1, height = 2;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'bottom':
						// field not supported
						break;

					case 'radius':
						radius = fieldValues[ 0 ];
						break;

					case 'height':
						height = fieldValues[ 0 ];
						break;

					case 'side':
						// field not supported
						break;

					case 'top':
						// field not supported
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new CylinderGeometry( radius, radius, height, 16, 1 );

			return geometry;

		}

		function buildSphereNode( node ) {

			let radius = 1;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'radius':
						radius = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const geometry = new SphereGeometry( radius, 16, 16 );

			return geometry;

		}

		function buildElevationGridNode( node ) {

			let color;
			let normal;
			let texCoord;
			let height;

			let colorPerVertex = true;
			let normalPerVertex = true;
			let solid = true;
			let ccw = true;
			let creaseAngle = 0;
			let xDimension = 2;
			let zDimension = 2;
			let xSpacing = 1;
			let zSpacing = 1;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'color':
						const colorNode = fieldValues[ 0 ];

						if ( colorNode !== null ) {

							color = getNode( colorNode );

						}

						break;

					case 'normal':
						const normalNode = fieldValues[ 0 ];

						if ( normalNode !== null ) {

							normal = getNode( normalNode );

						}

						break;

					case 'texCoord':
						const texCoordNode = fieldValues[ 0 ];

						if ( texCoordNode !== null ) {

							texCoord = getNode( texCoordNode );

						}

						break;

					case 'height':
						height = fieldValues;
						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'colorPerVertex':
						colorPerVertex = fieldValues[ 0 ];
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'normalPerVertex':
						normalPerVertex = fieldValues[ 0 ];
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'xDimension':
						xDimension = fieldValues[ 0 ];
						break;

					case 'xSpacing':
						xSpacing = fieldValues[ 0 ];
						break;

					case 'zDimension':
						zDimension = fieldValues[ 0 ];
						break;

					case 'zSpacing':
						zSpacing = fieldValues[ 0 ];
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			// vertex data

			const vertices = [];
			const normals = [];
			const colors = [];
			const uvs = [];

			for ( let i = 0; i < zDimension; i ++ ) {

				for ( let j = 0; j < xDimension; j ++ ) {

					// compute a row major index

					const index = ( i * xDimension ) + j;

					// vertices

					const x = xSpacing * i;
					const y = height[ index ];
					const z = zSpacing * j;

					vertices.push( x, y, z );

					// colors

					if ( color && colorPerVertex === true ) {

						const r = color[ index * 3 + 0 ];
						const g = color[ index * 3 + 1 ];
						const b = color[ index * 3 + 2 ];

						colors.push( r, g, b );

					}

					// normals

					if ( normal && normalPerVertex === true ) {

						const xn = normal[ index * 3 + 0 ];
						const yn = normal[ index * 3 + 1 ];
						const zn = normal[ index * 3 + 2 ];

						normals.push( xn, yn, zn );

					}

					// uvs

					if ( texCoord ) {

						const s = texCoord[ index * 2 + 0 ];
						const t = texCoord[ index * 2 + 1 ];

						uvs.push( s, t );


					} else {

						uvs.push( i / ( xDimension - 1 ), j / ( zDimension - 1 ) );

					}

				}

			}

			// indices

			const indices = [];

			for ( let i = 0; i < xDimension - 1; i ++ ) {

				for ( let j = 0; j < zDimension - 1; j ++ ) {

					// from https://tecfa.unige.ch/guides/vrml/vrml97/spec/part1/nodesRef.html#ElevationGrid

					const a = i + j * xDimension;
					const b = i + ( j + 1 ) * xDimension;
					const c = ( i + 1 ) + ( j + 1 ) * xDimension;
					const d = ( i + 1 ) + j * xDimension;

					// faces

					if ( ccw === true ) {

						indices.push( a, c, b );
						indices.push( c, a, d );

					} else {

						indices.push( a, b, c );
						indices.push( c, d, a );

					}

				}

			}

			//

			const positionAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( vertices, 3 ) );
			const uvAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( uvs, 2 ) );
			let colorAttribute;
			let normalAttribute;

			// color attribute

			if ( color ) {

				if ( colorPerVertex === false ) {

					for ( let i = 0; i < xDimension - 1; i ++ ) {

						for ( let j = 0; j < zDimension - 1; j ++ ) {

							const index = i + j * ( xDimension - 1 );

							const r = color[ index * 3 + 0 ];
							const g = color[ index * 3 + 1 ];
							const b = color[ index * 3 + 2 ];

							// one color per quad

							colors.push( r, g, b ); colors.push( r, g, b ); colors.push( r, g, b );
							colors.push( r, g, b ); colors.push( r, g, b ); colors.push( r, g, b );

						}

					}

					colorAttribute = new Float32BufferAttribute( colors, 3 );

				} else {

					colorAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( colors, 3 ) );

				}

				convertColorsToLinearSRGB( colorAttribute );

			}

			// normal attribute

			if ( normal ) {

				if ( normalPerVertex === false ) {

					for ( let i = 0; i < xDimension - 1; i ++ ) {

						for ( let j = 0; j < zDimension - 1; j ++ ) {

							const index = i + j * ( xDimension - 1 );

							const xn = normal[ index * 3 + 0 ];
							const yn = normal[ index * 3 + 1 ];
							const zn = normal[ index * 3 + 2 ];

							// one normal per quad

							normals.push( xn, yn, zn ); normals.push( xn, yn, zn ); normals.push( xn, yn, zn );
							normals.push( xn, yn, zn ); normals.push( xn, yn, zn ); normals.push( xn, yn, zn );

						}

					}

					normalAttribute = new Float32BufferAttribute( normals, 3 );

				} else {

					normalAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( normals, 3 ) );

				}

			} else {

				normalAttribute = computeNormalAttribute( indices, vertices, creaseAngle );

			}

			// build geometry

			const geometry = new BufferGeometry();
			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );
			geometry.setAttribute( 'uv', uvAttribute );

			if ( colorAttribute ) geometry.setAttribute( 'color', colorAttribute );

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}

		function buildExtrusionNode( node ) {

			let crossSection = [ 1, 1, 1, - 1, - 1, - 1, - 1, 1, 1, 1 ];
			let spine = [ 0, 0, 0, 0, 1, 0 ];
			let scale;
			let orientation;

			let beginCap = true;
			let ccw = true;
			let creaseAngle = 0;
			let endCap = true;
			let solid = true;

			const fields = node.fields;

			for ( let i = 0, l = fields.length; i < l; i ++ ) {

				const field = fields[ i ];
				const fieldName = field.name;
				const fieldValues = field.values;

				switch ( fieldName ) {

					case 'beginCap':
						beginCap = fieldValues[ 0 ];
						break;

					case 'ccw':
						ccw = fieldValues[ 0 ];
						break;

					case 'convex':
						// field not supported
						break;

					case 'creaseAngle':
						creaseAngle = fieldValues[ 0 ];
						break;

					case 'crossSection':
						crossSection = fieldValues;
						break;

					case 'endCap':
						endCap = fieldValues[ 0 ];
						break;

					case 'orientation':
						orientation = fieldValues;
						break;

					case 'scale':
						scale = fieldValues;
						break;

					case 'solid':
						solid = fieldValues[ 0 ];
						break;

					case 'spine':
						spine = fieldValues; // only extrusion along the Y-axis are supported so far
						break;

					default:
						console.warn( 'THREE.VRMLLoader: Unknown field:', fieldName );
						break;

				}

			}

			const crossSectionClosed = ( crossSection[ 0 ] === crossSection[ crossSection.length - 2 ] && crossSection[ 1 ] === crossSection[ crossSection.length - 1 ] );

			// vertices

			const vertices = [];
			const spineVector = new Vector3();
			const scaling = new Vector3();

			const axis = new Vector3();
			const vertex = new Vector3();
			const quaternion = new Quaternion();

			for ( let i = 0, j = 0, o = 0, il = spine.length; i < il; i += 3, j += 2, o += 4 ) {

				spineVector.fromArray( spine, i );

				scaling.x = scale ? scale[ j + 0 ] : 1;
				scaling.y = 1;
				scaling.z = scale ? scale[ j + 1 ] : 1;

				axis.x = orientation ? orientation[ o + 0 ] : 0;
				axis.y = orientation ? orientation[ o + 1 ] : 0;
				axis.z = orientation ? orientation[ o + 2 ] : 1;
				const angle = orientation ? orientation[ o + 3 ] : 0;

				for ( let k = 0, kl = crossSection.length; k < kl; k += 2 ) {

					vertex.x = crossSection[ k + 0 ];
					vertex.y = 0;
					vertex.z = crossSection[ k + 1 ];

					// scale

					vertex.multiply( scaling );

					// rotate

					quaternion.setFromAxisAngle( axis, angle );
					vertex.applyQuaternion( quaternion );

					// translate

					vertex.add( spineVector );

					vertices.push( vertex.x, vertex.y, vertex.z );

				}

			}

			// indices

			const indices = [];

			const spineCount = spine.length / 3;
			const crossSectionCount = crossSection.length / 2;

			for ( let i = 0; i < spineCount - 1; i ++ ) {

				for ( let j = 0; j < crossSectionCount - 1; j ++ ) {

					const a = j + i * crossSectionCount;
					let b = ( j + 1 ) + i * crossSectionCount;
					const c = j + ( i + 1 ) * crossSectionCount;
					let d = ( j + 1 ) + ( i + 1 ) * crossSectionCount;

					if ( ( j === crossSectionCount - 2 ) && ( crossSectionClosed === true ) ) {

						b = i * crossSectionCount;
						d = ( i + 1 ) * crossSectionCount;

					}

					if ( ccw === true ) {

						indices.push( a, b, c );
						indices.push( c, b, d );

					} else {

						indices.push( a, c, b );
						indices.push( c, d, b );

					}

				}

			}

			// triangulate cap

			if ( beginCap === true || endCap === true ) {

				const contour = [];

				for ( let i = 0, l = crossSection.length; i < l; i += 2 ) {

					contour.push( new Vector2( crossSection[ i ], crossSection[ i + 1 ] ) );

				}

				const faces = ShapeUtils.triangulateShape( contour, [] );
				const capIndices = [];

				for ( let i = 0, l = faces.length; i < l; i ++ ) {

					const face = faces[ i ];

					capIndices.push( face[ 0 ], face[ 1 ], face[ 2 ] );

				}

				// begin cap

				if ( beginCap === true ) {

					for ( let i = 0, l = capIndices.length; i < l; i += 3 ) {

						if ( ccw === true ) {

							indices.push( capIndices[ i + 0 ], capIndices[ i + 1 ], capIndices[ i + 2 ] );

						} else {

							indices.push( capIndices[ i + 0 ], capIndices[ i + 2 ], capIndices[ i + 1 ] );

						}

					}

				}

				// end cap

				if ( endCap === true ) {

					const indexOffset = crossSectionCount * ( spineCount - 1 ); // references to the first vertex of the last cross section

					for ( let i = 0, l = capIndices.length; i < l; i += 3 ) {

						if ( ccw === true ) {

							indices.push( indexOffset + capIndices[ i + 0 ], indexOffset + capIndices[ i + 2 ], indexOffset + capIndices[ i + 1 ] );

						} else {

							indices.push( indexOffset + capIndices[ i + 0 ], indexOffset + capIndices[ i + 1 ], indexOffset + capIndices[ i + 2 ] );

						}

					}

				}

			}

			const positionAttribute = toNonIndexedAttribute( indices, new Float32BufferAttribute( vertices, 3 ) );
			const normalAttribute = computeNormalAttribute( indices, vertices, creaseAngle );

			const geometry = new BufferGeometry();
			geometry.setAttribute( 'position', positionAttribute );
			geometry.setAttribute( 'normal', normalAttribute );
			// no uvs yet

			// "solid" influences the material so let's store it for later use

			geometry._solid = solid;
			geometry._type = 'mesh';

			return geometry;

		}

		// helper functions

		function resolveUSE( identifier ) {

			const node = nodeMap[ identifier ];
			const build = getNode( node );

			// because the same 3D objects can have different transformations, it's necessary to clone them.
			// materials can be influenced by the geometry (e.g. vertex normals). cloning is necessary to avoid
			// any side effects

			return ( build.isObject3D || build.isMaterial ) ? build.clone() : build;

		}

		function parseFieldChildren( children, owner ) {

			for ( let i = 0, l = children.length; i < l; i ++ ) {

				const object = getNode( children[ i ] );

				if ( object instanceof Object3D ) owner.add( object );

			}

		}

		function triangulateFaceIndex( index, ccw ) {

			const indices = [];

			// since face definitions can have more than three vertices, it's necessary to
			// perform a simple triangulation

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ start ];
				const i2 = index[ i + ( ccw ? 1 : 2 ) ];
				const i3 = index[ i + ( ccw ? 2 : 1 ) ];

				indices.push( i1, i2, i3 );

				// an index of -1 indicates that the current face has ended and the next one begins

				if ( index[ i + 3 ] === - 1 || i + 3 >= l ) {

					i += 3;
					start = i + 1;

				}

			}

			return indices;

		}

		function triangulateFaceData( data, index ) {

			const triangulatedData = [];

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const stride = start * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				triangulatedData.push( x, y, z );

				// an index of -1 indicates that the current face has ended and the next one begins

				if ( index[ i + 3 ] === - 1 || i + 3 >= l ) {

					i += 3;
					start ++;

				}

			}

			return triangulatedData;

		}

		function flattenData( data, index ) {

			const flattenData = [];

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ i ];

				const stride = i1 * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				flattenData.push( x, y, z );

			}

			return flattenData;

		}

		function expandLineIndex( index ) {

			const indices = [];

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const i1 = index[ i ];
				const i2 = index[ i + 1 ];

				indices.push( i1, i2 );

				// an index of -1 indicates that the current line has ended and the next one begins

				if ( index[ i + 2 ] === - 1 || i + 2 >= l ) {

					i += 2;

				}

			}

			return indices;

		}

		function expandLineData( data, index ) {

			const triangulatedData = [];

			let start = 0;

			for ( let i = 0, l = index.length; i < l; i ++ ) {

				const stride = start * 3;

				const x = data[ stride ];
				const y = data[ stride + 1 ];
				const z = data[ stride + 2 ];

				triangulatedData.push( x, y, z );

				// an index of -1 indicates that the current line has ended and the next one begins

				if ( index[ i + 2 ] === - 1 || i + 2 >= l ) {

					i += 2;
					start ++;

				}

			}

			return triangulatedData;

		}

		const vA = new Vector3();
		const vB = new Vector3();
		const vC = new Vector3();

		const uvA = new Vector2();
		const uvB = new Vector2();
		const uvC = new Vector2();

		function computeAttributeFromIndexedData( coordIndex, index, data, itemSize ) {

			const array = [];

			// we use the coordIndex.length as delimiter since normalIndex must contain at least as many indices

			for ( let i = 0, l = coordIndex.length; i < l; i += 3 ) {

				const a = index[ i ];
				const b = index[ i + 1 ];
				const c = index[ i + 2 ];

				if ( itemSize === 2 ) {

					uvA.fromArray( data, a * itemSize );
					uvB.fromArray( data, b * itemSize );
					uvC.fromArray( data, c * itemSize );

					array.push( uvA.x, uvA.y );
					array.push( uvB.x, uvB.y );
					array.push( uvC.x, uvC.y );

				} else {

					vA.fromArray( data, a * itemSize );
					vB.fromArray( data, b * itemSize );
					vC.fromArray( data, c * itemSize );

					array.push( vA.x, vA.y, vA.z );
					array.push( vB.x, vB.y, vB.z );
					array.push( vC.x, vC.y, vC.z );

				}

			}

			return new Float32BufferAttribute( array, itemSize );

		}

		function computeAttributeFromFaceData( index, faceData ) {

			const array = [];

			for ( let i = 0, j = 0, l = index.length; i < l; i += 3, j ++ ) {

				vA.fromArray( faceData, j * 3 );

				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );

			}

			return new Float32BufferAttribute( array, 3 );

		}

		function computeAttributeFromLineData( index, lineData ) {

			const array = [];

			for ( let i = 0, j = 0, l = index.length; i < l; i += 2, j ++ ) {

				vA.fromArray( lineData, j * 3 );

				array.push( vA.x, vA.y, vA.z );
				array.push( vA.x, vA.y, vA.z );

			}

			return new Float32BufferAttribute( array, 3 );

		}

		function toNonIndexedAttribute( indices, attribute ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				index = indices[ i ] * itemSize;

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new Float32BufferAttribute( array2, itemSize );

		}

		const ab = new Vector3();
		const cb = new Vector3();

		function computeNormalAttribute( index, coord, creaseAngle ) {

			const faces = [];
			const vertexNormals = {};

			// prepare face and raw vertex normals

			for ( let i = 0, l = index.length; i < l; i += 3 ) {

				const a = index[ i ];
				const b = index[ i + 1 ];
				const c = index[ i + 2 ];

				const face = new Face( a, b, c );

				vA.fromArray( coord, a * 3 );
				vB.fromArray( coord, b * 3 );
				vC.fromArray( coord, c * 3 );

				cb.subVectors( vC, vB );
				ab.subVectors( vA, vB );
				cb.cross( ab );

				cb.normalize();

				face.normal.copy( cb );

				if ( vertexNormals[ a ] === undefined ) vertexNormals[ a ] = [];
				if ( vertexNormals[ b ] === undefined ) vertexNormals[ b ] = [];
				if ( vertexNormals[ c ] === undefined ) vertexNormals[ c ] = [];

				vertexNormals[ a ].push( face.normal );
				vertexNormals[ b ].push( face.normal );
				vertexNormals[ c ].push( face.normal );

				faces.push( face );

			}

			// compute vertex normals and build final geometry

			const normals = [];

			for ( let i = 0, l = faces.length; i < l; i ++ ) {

				const face = faces[ i ];

				const nA = weightedNormal( vertexNormals[ face.a ], face.normal, creaseAngle );
				const nB = weightedNormal( vertexNormals[ face.b ], face.normal, creaseAngle );
				const nC = weightedNormal( vertexNormals[ face.c ], face.normal, creaseAngle );

				vA.fromArray( coord, face.a * 3 );
				vB.fromArray( coord, face.b * 3 );
				vC.fromArray( coord, face.c * 3 );

				normals.push( nA.x, nA.y, nA.z );
				normals.push( nB.x, nB.y, nB.z );
				normals.push( nC.x, nC.y, nC.z );

			}

			return new Float32BufferAttribute( normals, 3 );

		}

		function weightedNormal( normals, vector, creaseAngle ) {

			const normal = new Vector3();

			if ( creaseAngle === 0 ) {

				normal.copy( vector );

			} else {

				for ( let i = 0, l = normals.length; i < l; i ++ ) {

					if ( normals[ i ].angleTo( vector ) < creaseAngle ) {

						normal.add( normals[ i ] );

					}

				}

			}

			return normal.normalize();

		}

		function toColorArray( colors ) {

			const array = [];

			for ( let i = 0, l = colors.length; i < l; i += 3 ) {

				array.push( new Color( colors[ i ], colors[ i + 1 ], colors[ i + 2 ] ) );

			}

			return array;

		}

		function convertColorsToLinearSRGB( attribute ) {

			const color = new Color();

			for ( let i = 0; i < attribute.count; i ++ ) {

				color.fromBufferAttribute( attribute, i );

				ColorManagement.colorSpaceToWorking( color, SRGBColorSpace );

				attribute.setXYZ( i, color.r, color.g, color.b );

			}

		}

		/**
		 * Vertically paints the faces interpolating between the
		 * specified colors at the specified angels. This is used for the Background
		 * node, but could be applied to other nodes with multiple faces as well.
		 *
		 * When used with the Background node, default is directionIsDown is true if
		 * interpolating the skyColor down from the Zenith. When interpolating up from
		 * the Nadir i.e. interpolating the groundColor, the directionIsDown is false.
		 *
		 * The first angle is never specified, it is the Zenith (0 rad). Angles are specified
		 * in radians. The geometry is thought a sphere, but could be anything. The color interpolation
		 * is linear along the Y axis in any case.
		 *
		 * You must specify one more color than you have angles at the beginning of the colors array.
		 * This is the color of the Zenith (the top of the shape).
		 *
		 * @param {BufferGeometry} geometry
		 * @param {number} radius
		 * @param {array} angles
		 * @param {array} colors
		 * @param {boolean} topDown - Whether to work top down or bottom up.
		 */
		function paintFaces( geometry, radius, angles, colors, topDown ) {

			// compute threshold values

			const thresholds = [];
			const startAngle = ( topDown === true ) ? 0 : Math.PI;

			for ( let i = 0, l = colors.length; i < l; i ++ ) {

				let angle = ( i === 0 ) ? 0 : angles[ i - 1 ];
				angle = ( topDown === true ) ? angle : ( startAngle - angle );

				const point = new Vector3();
				point.setFromSphericalCoords( radius, angle, 0 );

				thresholds.push( point );

			}

			// generate vertex colors

			const indices = geometry.index;
			const positionAttribute = geometry.attributes.position;
			const colorAttribute = new BufferAttribute( new Float32Array( geometry.attributes.position.count * 3 ), 3 );

			const position = new Vector3();
			const color = new Color();

			for ( let i = 0; i < indices.count; i ++ ) {

				const index = indices.getX( i );
				position.fromBufferAttribute( positionAttribute, index );

				let thresholdIndexA, thresholdIndexB;
				let t = 1;

				for ( let j = 1; j < thresholds.length; j ++ ) {

					thresholdIndexA = j - 1;
					thresholdIndexB = j;

					const thresholdA = thresholds[ thresholdIndexA ];
					const thresholdB = thresholds[ thresholdIndexB ];

					if ( topDown === true ) {

						// interpolation for sky color

						if ( position.y <= thresholdA.y && position.y > thresholdB.y ) {

							t = Math.abs( thresholdA.y - position.y ) / Math.abs( thresholdA.y - thresholdB.y );

							break;

						}

					} else {

						// interpolation for ground color

						if ( position.y >= thresholdA.y && position.y < thresholdB.y ) {

							t = Math.abs( thresholdA.y - position.y ) / Math.abs( thresholdA.y - thresholdB.y );

							break;

						}

					}

				}

				const colorA = colors[ thresholdIndexA ];
				const colorB = colors[ thresholdIndexB ];

				color.copy( colorA ).lerp( colorB, t );

				ColorManagement.colorSpaceToWorking( color, SRGBColorSpace );

				colorAttribute.setXYZ( index, color.r, color.g, color.b );

			}

			geometry.setAttribute( 'color', colorAttribute );

		}

		//

		const textureLoader = new TextureLoader( this.manager );
		textureLoader.setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		// check version (only 2.0 is supported)

		if ( data.indexOf( '#VRML V2.0' ) === - 1 ) {

			throw Error( 'THREE.VRMLLexer: Version of VRML asset not supported.' );

		}

		// create JSON representing the tree structure of the VRML asset

		const tree = generateVRMLTree( data );

		// parse the tree structure to a three.js scene

		const scene = parseTree( tree );

		return scene;

	}
```
</details>

### `VRMLToASTVisitor`

<details><summary>Class Code</summary>

```ts
class VRMLToASTVisitor extends BaseVRMLVisitor {

				constructor() {

					super();

					this.validateVisitor();

				}

				vrml( ctx ) {

					const data = {
						version: this.visit( ctx.version ),
						nodes: [],
						routes: []
					};

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						data.nodes.push( this.visit( node ) );

					}

					if ( ctx.route ) {

						for ( let i = 0, l = ctx.route.length; i < l; i ++ ) {

							const route = ctx.route[ i ];

							data.routes.push( this.visit( route ) );

						}

					}

					return data;

				}

				version( ctx ) {

					return ctx.Version[ 0 ].image;

				}

				node( ctx ) {

					const data = {
						name: ctx.NodeName[ 0 ].image,
						fields: []
					};

					if ( ctx.field ) {

						for ( let i = 0, l = ctx.field.length; i < l; i ++ ) {

							const field = ctx.field[ i ];

							data.fields.push( this.visit( field ) );

						}

					}

					// DEF

					if ( ctx.def ) {

						data.DEF = this.visit( ctx.def[ 0 ] );

					}

					return data;

				}

				field( ctx ) {

					const data = {
						name: ctx.Identifier[ 0 ].image,
						type: null,
						values: null
					};

					let result;

					// SFValue

					if ( ctx.singleFieldValue ) {

						result = this.visit( ctx.singleFieldValue[ 0 ] );

					}

					// MFValue

					if ( ctx.multiFieldValue ) {

						result = this.visit( ctx.multiFieldValue[ 0 ] );

					}

					data.type = result.type;
					data.values = result.values;

					return data;

				}

				def( ctx ) {

					return ( ctx.Identifier || ctx.NodeName )[ 0 ].image;

				}

				use( ctx ) {

					return { USE: ( ctx.Identifier || ctx.NodeName )[ 0 ].image };

				}

				singleFieldValue( ctx ) {

					return processField( this, ctx );

				}

				multiFieldValue( ctx ) {

					return processField( this, ctx );

				}

				route( ctx ) {

					const data = {
						FROM: ctx.RouteIdentifier[ 0 ].image,
						TO: ctx.RouteIdentifier[ 1 ].image
					};

					return data;

				}

			}
```
</details>

#### Methods

##### `vrml(ctx: any): { version: any; nodes: any[]; routes: any[]; }`

<details><summary>Code</summary>

```ts
vrml( ctx ) {

					const data = {
						version: this.visit( ctx.version ),
						nodes: [],
						routes: []
					};

					for ( let i = 0, l = ctx.node.length; i < l; i ++ ) {

						const node = ctx.node[ i ];

						data.nodes.push( this.visit( node ) );

					}

					if ( ctx.route ) {

						for ( let i = 0, l = ctx.route.length; i < l; i ++ ) {

							const route = ctx.route[ i ];

							data.routes.push( this.visit( route ) );

						}

					}

					return data;

				}
```
</details>

##### `version(ctx: any): any`

<details><summary>Code</summary>

```ts
version( ctx ) {

					return ctx.Version[ 0 ].image;

				}
```
</details>

##### `node(ctx: any): { name: any; fields: any[]; }`

<details><summary>Code</summary>

```ts
node( ctx ) {

					const data = {
						name: ctx.NodeName[ 0 ].image,
						fields: []
					};

					if ( ctx.field ) {

						for ( let i = 0, l = ctx.field.length; i < l; i ++ ) {

							const field = ctx.field[ i ];

							data.fields.push( this.visit( field ) );

						}

					}

					// DEF

					if ( ctx.def ) {

						data.DEF = this.visit( ctx.def[ 0 ] );

					}

					return data;

				}
```
</details>

##### `field(ctx: any): { name: any; type: any; values: any; }`

<details><summary>Code</summary>

```ts
field( ctx ) {

					const data = {
						name: ctx.Identifier[ 0 ].image,
						type: null,
						values: null
					};

					let result;

					// SFValue

					if ( ctx.singleFieldValue ) {

						result = this.visit( ctx.singleFieldValue[ 0 ] );

					}

					// MFValue

					if ( ctx.multiFieldValue ) {

						result = this.visit( ctx.multiFieldValue[ 0 ] );

					}

					data.type = result.type;
					data.values = result.values;

					return data;

				}
```
</details>

##### `def(ctx: any): any`

<details><summary>Code</summary>

```ts
def( ctx ) {

					return ( ctx.Identifier || ctx.NodeName )[ 0 ].image;

				}
```
</details>

##### `use(ctx: any): { USE: any; }`

<details><summary>Code</summary>

```ts
use( ctx ) {

					return { USE: ( ctx.Identifier || ctx.NodeName )[ 0 ].image };

				}
```
</details>

##### `singleFieldValue(ctx: any): { type: any; values: any[]; }`

<details><summary>Code</summary>

```ts
singleFieldValue( ctx ) {

					return processField( this, ctx );

				}
```
</details>

##### `multiFieldValue(ctx: any): { type: any; values: any[]; }`

<details><summary>Code</summary>

```ts
multiFieldValue( ctx ) {

					return processField( this, ctx );

				}
```
</details>

##### `route(ctx: any): { FROM: any; TO: any; }`

<details><summary>Code</summary>

```ts
route( ctx ) {

					const data = {
						FROM: ctx.RouteIdentifier[ 0 ].image,
						TO: ctx.RouteIdentifier[ 1 ].image
					};

					return data;

				}
```
</details>

### `VRMLLexer`

<details><summary>Class Code</summary>

```ts
class VRMLLexer {

	constructor( tokens ) {

		this.lexer = new chevrotain.Lexer( tokens );

	}

	lex( inputText ) {

		const lexingResult = this.lexer.tokenize( inputText );

		if ( lexingResult.errors.length > 0 ) {

			console.error( lexingResult.errors );

			throw Error( 'THREE.VRMLLexer: Lexing errors detected.' );

		}

		return lexingResult;

	}

}
```
</details>

#### Methods

##### `lex(inputText: any): any`

<details><summary>Code</summary>

```ts
lex( inputText ) {

		const lexingResult = this.lexer.tokenize( inputText );

		if ( lexingResult.errors.length > 0 ) {

			console.error( lexingResult.errors );

			throw Error( 'THREE.VRMLLexer: Lexing errors detected.' );

		}

		return lexingResult;

	}
```
</details>

### `VRMLParser`

<details><summary>Class Code</summary>

```ts
class VRMLParser extends CstParser {

	constructor( tokenVocabulary ) {

		super( tokenVocabulary );

		const $ = this;

		const Version = tokenVocabulary[ 'Version' ];
		const LCurly = tokenVocabulary[ 'LCurly' ];
		const RCurly = tokenVocabulary[ 'RCurly' ];
		const LSquare = tokenVocabulary[ 'LSquare' ];
		const RSquare = tokenVocabulary[ 'RSquare' ];
		const Identifier = tokenVocabulary[ 'Identifier' ];
		const RouteIdentifier = tokenVocabulary[ 'RouteIdentifier' ];
		const StringLiteral = tokenVocabulary[ 'StringLiteral' ];
		const HexLiteral = tokenVocabulary[ 'HexLiteral' ];
		const NumberLiteral = tokenVocabulary[ 'NumberLiteral' ];
		const TrueLiteral = tokenVocabulary[ 'TrueLiteral' ];
		const FalseLiteral = tokenVocabulary[ 'FalseLiteral' ];
		const NullLiteral = tokenVocabulary[ 'NullLiteral' ];
		const DEF = tokenVocabulary[ 'DEF' ];
		const USE = tokenVocabulary[ 'USE' ];
		const ROUTE = tokenVocabulary[ 'ROUTE' ];
		const TO = tokenVocabulary[ 'TO' ];
		const NodeName = tokenVocabulary[ 'NodeName' ];

		$.RULE( 'vrml', function () {

			$.SUBRULE( $.version );
			$.AT_LEAST_ONE( function () {

				$.SUBRULE( $.node );

			} );
			$.MANY( function () {

				$.SUBRULE( $.route );

			} );

		} );

		$.RULE( 'version', function () {

			$.CONSUME( Version );

		} );

		$.RULE( 'node', function () {

			$.OPTION( function () {

				$.SUBRULE( $.def );

			} );

			$.CONSUME( NodeName );
			$.CONSUME( LCurly );
			$.MANY( function () {

				$.SUBRULE( $.field );

			} );
			$.CONSUME( RCurly );

		} );

		$.RULE( 'field', function () {

			$.CONSUME( Identifier );

			$.OR2( [
				{ ALT: function () {

					$.SUBRULE( $.singleFieldValue );

				} },
				{ ALT: function () {

					$.SUBRULE( $.multiFieldValue );

				} }
			] );

		} );

		$.RULE( 'def', function () {

			$.CONSUME( DEF );
			$.OR( [
				{ ALT: function () {

					$.CONSUME( Identifier );

				} },
				{ ALT: function () {

					$.CONSUME( NodeName );

				} }
			] );

		} );

		$.RULE( 'use', function () {

			$.CONSUME( USE );
			$.OR( [
				{ ALT: function () {

					$.CONSUME( Identifier );

				} },
				{ ALT: function () {

					$.CONSUME( NodeName );

				} }
			] );

		} );

		$.RULE( 'singleFieldValue', function () {

			$.AT_LEAST_ONE( function () {

				$.OR( [
					{ ALT: function () {

						$.SUBRULE( $.node );

					} },
					{ ALT: function () {

						$.SUBRULE( $.use );

					} },
					{ ALT: function () {

						$.CONSUME( StringLiteral );

					} },
					{ ALT: function () {

						$.CONSUME( HexLiteral );

					} },
					{ ALT: function () {

						$.CONSUME( NumberLiteral );

					} },
					{ ALT: function () {

						$.CONSUME( TrueLiteral );

					} },
					{ ALT: function () {

						$.CONSUME( FalseLiteral );

					} },
					{ ALT: function () {

						$.CONSUME( NullLiteral );

					} }
				] );


			} );

		} );

		$.RULE( 'multiFieldValue', function () {

			$.CONSUME( LSquare );
			$.MANY( function () {

				$.OR( [
					{ ALT: function () {

						$.SUBRULE( $.node );

					} },
					{ ALT: function () {

						$.SUBRULE( $.use );

					} },
					{ ALT: function () {

						$.CONSUME( StringLiteral );

					} },
					{ ALT: function () {

						$.CONSUME( HexLiteral );

					} },
					{ ALT: function () {

						$.CONSUME( NumberLiteral );

					} },
					{ ALT: function () {

						$.CONSUME( NullLiteral );

					} }
				] );

			} );
			$.CONSUME( RSquare );

		} );

		$.RULE( 'route', function () {

			$.CONSUME( ROUTE );
			$.CONSUME( RouteIdentifier );
			$.CONSUME( TO );
			$.CONSUME2( RouteIdentifier );

		} );

		this.performSelfAnalysis();

	}

}
```
</details>

### `Face`

<details><summary>Class Code</summary>

```ts
class Face {

	constructor( a, b, c ) {

		this.a = a;
		this.b = b;
		this.c = c;
		this.normal = new Vector3();

	}

}
```
</details>


---