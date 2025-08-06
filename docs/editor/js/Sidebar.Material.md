[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Material.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 16 |
| 📊 Variables & Constants | 88 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Material.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIButton` | `./libs/ui.js` |
| `UIInput` | `./libs/ui.js` |
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UISelect` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UITextArea` | `./libs/ui.js` |
| `SetMaterialCommand` | `./commands/SetMaterialCommand.js` |
| `SetMaterialValueCommand` | `./commands/SetMaterialValueCommand.js` |
| `SidebarMaterialBooleanProperty` | `./Sidebar.Material.BooleanProperty.js` |
| `SidebarMaterialColorProperty` | `./Sidebar.Material.ColorProperty.js` |
| `SidebarMaterialConstantProperty` | `./Sidebar.Material.ConstantProperty.js` |
| `SidebarMaterialMapProperty` | `./Sidebar.Material.MapProperty.js` |
| `SidebarMaterialNumberProperty` | `./Sidebar.Material.NumberProperty.js` |
| `SidebarMaterialRangeValueProperty` | `./Sidebar.Material.RangeValueProperty.js` |
| `SidebarMaterialProgram` | `./Sidebar.Material.Program.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `currentObject` | `any` | let/var | `*not shown*` | ✗ |
| `currentMaterialSlot` | `number` | let/var | `0` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `materialSlotRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `materialClassRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `materialUUIDRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `materialNameRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `materialProgram` | `any` | let/var | `new SidebarMaterialProgram( editor, 'vertexShader' )` | ✗ |
| `materialColor` | `any` | let/var | `new SidebarMaterialColorProperty( editor, 'color', strings.getKey( 'sidebar/m...` | ✗ |
| `materialSpecular` | `any` | let/var | `new SidebarMaterialColorProperty( editor, 'specular', strings.getKey( 'sideba...` | ✗ |
| `materialShininess` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'shininess', strings.getKey( 'side...` | ✗ |
| `materialEmissive` | `any` | let/var | `new SidebarMaterialColorProperty( editor, 'emissive', strings.getKey( 'sideba...` | ✗ |
| `materialReflectivity` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'reflectivity', strings.getKey( 's...` | ✗ |
| `materialIOR` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'ior', strings.getKey( 'sidebar/ma...` | ✗ |
| `materialRoughness` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'roughness', strings.getKey( 'side...` | ✗ |
| `materialMetalness` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'metalness', strings.getKey( 'side...` | ✗ |
| `materialClearcoat` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'clearcoat', strings.getKey( 'side...` | ✗ |
| `materialClearcoatRoughness` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'clearcoatRoughness', strings.getK...` | ✗ |
| `materialDispersion` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'dispersion', strings.getKey( 'sid...` | ✗ |
| `materialIridescence` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'iridescence', strings.getKey( 'si...` | ✗ |
| `materialIridescenceIOR` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'iridescenceIOR', strings.getKey( ...` | ✗ |
| `materialIridescenceThicknes...` | `any` | let/var | `new SidebarMaterialRangeValueProperty( editor, 'iridescenceThicknessRange', s...` | ✗ |
| `materialSheen` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'sheen', strings.getKey( 'sidebar/...` | ✗ |
| `materialSheenRoughness` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'sheenRoughness', strings.getKey( ...` | ✗ |
| `materialSheenColor` | `any` | let/var | `new SidebarMaterialColorProperty( editor, 'sheenColor', strings.getKey( 'side...` | ✗ |
| `materialTransmission` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'transmission', strings.getKey( 's...` | ✗ |
| `materialAttenuationDistance` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'attenuationDistance', strings.get...` | ✗ |
| `materialAttenuationColor` | `any` | let/var | `new SidebarMaterialColorProperty( editor, 'attenuationColor', strings.getKey(...` | ✗ |
| `materialThickness` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'thickness', strings.getKey( 'side...` | ✗ |
| `materialVertexColors` | `any` | let/var | `new SidebarMaterialBooleanProperty( editor, 'vertexColors', strings.getKey( '...` | ✗ |
| `materialDepthPackingOptions` | `{ [x: number]: string; }` | let/var | `{ [ THREE.BasicDepthPacking ]: 'Basic', [ THREE.RGBADepthPacking ]: 'RGBA' }` | ✗ |
| `materialDepthPacking` | `any` | let/var | `new SidebarMaterialConstantProperty( editor, 'depthPacking', strings.getKey( ...` | ✗ |
| `materialMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'map', strings.getKey( 'sidebar/mater...` | ✗ |
| `materialSpecularMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'specularMap', strings.getKey( 'sideb...` | ✗ |
| `materialEmissiveMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'emissiveMap', strings.getKey( 'sideb...` | ✗ |
| `materialMatcapMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'matcap', strings.getKey( 'sidebar/ma...` | ✗ |
| `materialAlphaMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'alphaMap', strings.getKey( 'sidebar/...` | ✗ |
| `materialBumpMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'bumpMap', strings.getKey( 'sidebar/m...` | ✗ |
| `materialNormalMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'normalMap', strings.getKey( 'sidebar...` | ✗ |
| `materialClearcoatMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'clearcoatMap', strings.getKey( 'side...` | ✗ |
| `materialClearcoatNormalMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'clearcoatNormalMap', strings.getKey(...` | ✗ |
| `materialClearcoatRoughnessMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'clearcoatRoughnessMap', strings.getK...` | ✗ |
| `materialDisplacementMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'displacementMap', strings.getKey( 's...` | ✗ |
| `materialRoughnessMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'roughnessMap', strings.getKey( 'side...` | ✗ |
| `materialMetalnessMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'metalnessMap', strings.getKey( 'side...` | ✗ |
| `materialIridescenceMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'iridescenceMap', strings.getKey( 'si...` | ✗ |
| `materialSheenColorMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'sheenColorMap', strings.getKey( 'sid...` | ✗ |
| `materialSheenRoughnessMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'sheenRoughnessMap', strings.getKey( ...` | ✗ |
| `materialIridescenceThicknes...` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'iridescenceThicknessMap', strings.ge...` | ✗ |
| `materialEnvMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'envMap', strings.getKey( 'sidebar/ma...` | ✗ |
| `materialLightMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'lightMap', strings.getKey( 'sidebar/...` | ✗ |
| `materialAOMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'aoMap', strings.getKey( 'sidebar/mat...` | ✗ |
| `materialGradientMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'gradientMap', strings.getKey( 'sideb...` | ✗ |
| `transmissionMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'transmissionMap', strings.getKey( 's...` | ✗ |
| `thicknessMap` | `any` | let/var | `new SidebarMaterialMapProperty( editor, 'thicknessMap', strings.getKey( 'side...` | ✗ |
| `materialSideOptions` | `{ 0: string; 1: string; 2: string; }` | let/var | `{ 0: 'Front', 1: 'Back', 2: 'Double' }` | ✗ |
| `materialSide` | `any` | let/var | `new SidebarMaterialConstantProperty( editor, 'side', strings.getKey( 'sidebar...` | ✗ |
| `materialSize` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'size', strings.getKey( 'sidebar/m...` | ✗ |
| `materialSizeAttenuation` | `any` | let/var | `new SidebarMaterialBooleanProperty( editor, 'sizeAttenuation', strings.getKey...` | ✗ |
| `materialFlatShading` | `any` | let/var | `new SidebarMaterialBooleanProperty( editor, 'flatShading', strings.getKey( 's...` | ✗ |
| `materialBlendingOptions` | `{ 0: string; 1: string; 2: string; 3:...` | let/var | `{ 0: 'No', 1: 'Normal', 2: 'Additive', 3: 'Subtractive', 4: 'Multiply', 5: 'C...` | ✗ |
| `materialBlending` | `any` | let/var | `new SidebarMaterialConstantProperty( editor, 'blending', strings.getKey( 'sid...` | ✗ |
| `materialOpacity` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'opacity', strings.getKey( 'sideba...` | ✗ |
| `materialTransparent` | `any` | let/var | `new SidebarMaterialBooleanProperty( editor, 'transparent', strings.getKey( 's...` | ✗ |
| `materialForceSinglePass` | `any` | let/var | `new SidebarMaterialBooleanProperty( editor, 'forceSinglePass', strings.getKey...` | ✗ |
| `materialAlphaTest` | `any` | let/var | `new SidebarMaterialNumberProperty( editor, 'alphaTest', strings.getKey( 'side...` | ✗ |
| `materialDepthTest` | `any` | let/var | `new SidebarMaterialBooleanProperty( editor, 'depthTest', strings.getKey( 'sid...` | ✗ |
| `materialDepthWrite` | `any` | let/var | `new SidebarMaterialBooleanProperty( editor, 'depthWrite', strings.getKey( 'si...` | ✗ |
| `materialWireframe` | `any` | let/var | `new SidebarMaterialBooleanProperty( editor, 'wireframe', strings.getKey( 'sid...` | ✗ |
| `materialUserDataRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `exportJson` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/material/export' ) )` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |
| `material` | `any` | let/var | `Array.isArray( object.material ) ? object.material[ currentMaterialSlot ] : o...` | ✗ |
| `previousSelectedSlot` | `number` | let/var | `currentMaterialSlot` | ✗ |
| `currentMaterial` | `any` | let/var | `currentObject.material` | ✗ |
| `properties` | `string[]` | let/var | `[ 'color', 'emissive', 'roughness', 'metalness', 'map', 'emissiveMap', 'alpha...` | ✗ |
| `value` | `any` | let/var | `currentMaterial[ property ]` | ✗ |
| `material` | `any` | let/var | `currentObject.material` | ✗ |
| `material` | `any` | let/var | `currentObject.material` | ✗ |
| `slotOptions` | `{}` | let/var | `{}` | ✗ |
| `hasMaterial` | `boolean` | let/var | `false` | ✗ |
| `materialClasses` | `{ LineBasicMaterial: any; LineDashedM...` | let/var | `{ 'LineBasicMaterial': THREE.LineBasicMaterial, 'LineDashedMaterial': THREE.L...` | ✗ |
| `meshMaterialOptions` | `{ MeshBasicMaterial: string; MeshDept...` | let/var | `{ 'MeshBasicMaterial': 'MeshBasicMaterial', 'MeshDepthMaterial': 'MeshDepthMa...` | ✗ |
| `lineMaterialOptions` | `{ LineBasicMaterial: string; LineDash...` | let/var | `{ 'LineBasicMaterial': 'LineBasicMaterial', 'LineDashedMaterial': 'LineDashed...` | ✗ |
| `spriteMaterialOptions` | `{ SpriteMaterial: string; RawShaderMa...` | let/var | `{ 'SpriteMaterial': 'SpriteMaterial', 'RawShaderMaterial': 'RawShaderMaterial...` | ✗ |
| `pointsMaterialOptions` | `{ PointsMaterial: string; RawShaderMa...` | let/var | `{ 'PointsMaterial': 'PointsMaterial', 'RawShaderMaterial': 'RawShaderMaterial...` | ✗ |


---

## Functions

### `SidebarMaterial(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setBorderTop`
- `container.setDisplay`
- `container.setPaddingTop`
- `materialSlotRow.add`
- `new UIText( strings.getKey( 'sidebar/material/slot' ) ).setClass`
- `strings.getKey`
- `new UISelect().setWidth( '170px' ).setFontSize( '12px' ).onChange`
- `materialSlotSelect.setOptions( { 0: '' } ).setValue`
- `container.add`
- `new UISelect().setWidth( '150px' ).setFontSize( '12px' ).onChange`
- `materialClassRow.add`
- `new UIText( strings.getKey( 'sidebar/material/type' ) ).setClass`
- `new UIInput().setWidth( '102px' ).setFontSize( '12px' ).setDisabled`
- `new UIButton( strings.getKey( 'sidebar/material/new' ) ).setMarginLeft`
- `materialUUIDRenew.onClick`
- `materialUUID.setValue`
- `THREE.MathUtils.generateUUID`
- `update`
- `materialUUIDRow.add`
- `new UIText( strings.getKey( 'sidebar/material/uuid' ) ).setClass`
- `new UIInput().setWidth( '150px' ).setFontSize( '12px' ).onChange`
- `editor.execute`
- `materialName.getValue`
- `materialNameRow.add`
- `new UIText( strings.getKey( 'sidebar/material/name' ) ).setClass`
- `new UITextArea().setWidth( '150px' ).setHeight( '40px' ).setFontSize( '12px' ).onChange`
- `materialUserData.onKeyUp`
- `JSON.parse`
- `materialUserData.getValue`
- `materialUserData.dom.classList.add`
- `materialUserData.dom.classList.remove`
- `materialUserDataRow.add`
- `new UIText( strings.getKey( 'sidebar/material/userdata' ) ).setClass`
- `exportJson.setMarginLeft`
- `exportJson.onClick`
- `Array.isArray`
- `material.toJSON`
- `JSON.stringify`
- `output.replace`
- `editor.utils.save`
- `parseInt`
- `materialSlotSelect.getValue`
- `editor.signals.materialChanged.dispatch`
- `editor.getObjectMaterial`
- `materialUUID.getValue`
- `materialClass.getValue`
- `value.clone`
- `editor.removeMaterial`
- `editor.addMaterial`
- `console.warn`
- `refreshUI`
- `materialSlotRow.setDisplay`
- `Math.max`
- `Math.min`
- `String`
- `materialSlotSelect.setOptions( slotOptions ).setValue`
- `materialName.setValue`
- `materialClass.setOptions`
- `materialClass.setValue`
- `setRowVisibility`
- `materialUserData.setValue`
- `console.log`
- `materialUserData.setBorderColor`
- `materialUserData.setBackgroundColor`
- `signals.objectSelected.add`
- `signals.materialChanged.add`

**Internal Comments:**
```
// Current material slot (x2)
// type (x2)
// uuid (x2)
// name (x2)
// program (x2)
// color (x2)
// specular (x2)
// shininess (x2)
// emissive (x2)
// reflectivity (x2)
// ior (x2)
// roughness (x2)
// metalness (x2)
// clearcoat (x2)
// clearcoatRoughness (x2)
// dispersion (x2)
// iridescence (x2)
// iridescenceIOR (x2)
// iridescenceThicknessMax (x2)
// sheen (x2)
// sheen roughness (x2)
// sheen color (x2)
// transmission (x2)
// attenuation distance (x2)
// attenuation tint (x2)
// thickness (x2)
// vertex colors (x2)
// depth packing (x2)
// map (x2)
// specular map (x2)
// emissive map (x2)
// matcap map (x2)
// alpha map (x2)
// bump map (x2)
// normal map (x2)
// clearcoat map (x2)
// clearcoat normal map (x2)
// clearcoat roughness map (x2)
// displacement map (x2)
// roughness map (x2)
// metalness map (x2)
// iridescence map (x2)
// sheen color map (x2)
// sheen roughness map (x2)
// iridescence thickness map (x2)
// env map (x2)
// light map (x2)
// ambient occlusion map (x2)
// gradient map (x2)
// transmission map (x2)
// thickness map (x2)
// side (x2)
// size (x2)
// sizeAttenuation (x2)
// flatShading (x2)
// blending (x2)
// opacity (x2)
// transparent (x2)
// forceSinglePass (x2)
// alpha test (x2)
// depth test (x2)
// depth write (x2)
// wireframe (x2)
// userData (x2)
// Export JSON (x2)
// (x2)
// TODO Find a easier to maintain approach (x2)
// don't remove the entire multi-material. just the material of the selected slot (x4)
// events (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarMaterial( editor ) {

	const signals = editor.signals;
	const strings = editor.strings;

	let currentObject;

	let currentMaterialSlot = 0;

	const container = new UIPanel();
	container.setBorderTop( '0' );
	container.setDisplay( 'none' );
	container.setPaddingTop( '20px' );

	// Current material slot

	const materialSlotRow = new UIRow();

	materialSlotRow.add( new UIText( strings.getKey( 'sidebar/material/slot' ) ).setClass( 'Label' ) );

	const materialSlotSelect = new UISelect().setWidth( '170px' ).setFontSize( '12px' ).onChange( update );
	materialSlotSelect.setOptions( { 0: '' } ).setValue( 0 );
	materialSlotRow.add( materialSlotSelect );

	container.add( materialSlotRow );

	// type

	const materialClassRow = new UIRow();
	const materialClass = new UISelect().setWidth( '150px' ).setFontSize( '12px' ).onChange( update );

	materialClassRow.add( new UIText( strings.getKey( 'sidebar/material/type' ) ).setClass( 'Label' ) );
	materialClassRow.add( materialClass );

	container.add( materialClassRow );

	// uuid

	const materialUUIDRow = new UIRow();
	const materialUUID = new UIInput().setWidth( '102px' ).setFontSize( '12px' ).setDisabled( true );
	const materialUUIDRenew = new UIButton( strings.getKey( 'sidebar/material/new' ) ).setMarginLeft( '7px' );
	materialUUIDRenew.onClick( function () {

		materialUUID.setValue( THREE.MathUtils.generateUUID() );
		update();

	} );

	materialUUIDRow.add( new UIText( strings.getKey( 'sidebar/material/uuid' ) ).setClass( 'Label' ) );
	materialUUIDRow.add( materialUUID );
	materialUUIDRow.add( materialUUIDRenew );

	container.add( materialUUIDRow );

	// name

	const materialNameRow = new UIRow();
	const materialName = new UIInput().setWidth( '150px' ).setFontSize( '12px' ).onChange( function () {

		editor.execute( new SetMaterialValueCommand( editor, editor.selected, 'name', materialName.getValue(), currentMaterialSlot ) );

	} );

	materialNameRow.add( new UIText( strings.getKey( 'sidebar/material/name' ) ).setClass( 'Label' ) );
	materialNameRow.add( materialName );

	container.add( materialNameRow );

	// program

	const materialProgram = new SidebarMaterialProgram( editor, 'vertexShader' );
	container.add( materialProgram );

	// color

	const materialColor = new SidebarMaterialColorProperty( editor, 'color', strings.getKey( 'sidebar/material/color' ) );
	container.add( materialColor );

	// specular

	const materialSpecular = new SidebarMaterialColorProperty( editor, 'specular', strings.getKey( 'sidebar/material/specular' ) );
	container.add( materialSpecular );

	// shininess

	const materialShininess = new SidebarMaterialNumberProperty( editor, 'shininess', strings.getKey( 'sidebar/material/shininess' ) );
	container.add( materialShininess );

	// emissive

	const materialEmissive = new SidebarMaterialColorProperty( editor, 'emissive', strings.getKey( 'sidebar/material/emissive' ) );
	container.add( materialEmissive );

	// reflectivity

	const materialReflectivity = new SidebarMaterialNumberProperty( editor, 'reflectivity', strings.getKey( 'sidebar/material/reflectivity' ) );
	container.add( materialReflectivity );

	// ior

	const materialIOR = new SidebarMaterialNumberProperty( editor, 'ior', strings.getKey( 'sidebar/material/ior' ), [ 1, 2.333 ], 3 );
	container.add( materialIOR );

	// roughness

	const materialRoughness = new SidebarMaterialNumberProperty( editor, 'roughness', strings.getKey( 'sidebar/material/roughness' ), [ 0, 1 ] );
	container.add( materialRoughness );

	// metalness

	const materialMetalness = new SidebarMaterialNumberProperty( editor, 'metalness', strings.getKey( 'sidebar/material/metalness' ), [ 0, 1 ] );
	container.add( materialMetalness );

	// clearcoat

	const materialClearcoat = new SidebarMaterialNumberProperty( editor, 'clearcoat', strings.getKey( 'sidebar/material/clearcoat' ), [ 0, 1 ] );
	container.add( materialClearcoat );

	// clearcoatRoughness

	const materialClearcoatRoughness = new SidebarMaterialNumberProperty( editor, 'clearcoatRoughness', strings.getKey( 'sidebar/material/clearcoatroughness' ), [ 0, 1 ] );
	container.add( materialClearcoatRoughness );

	// dispersion

	const materialDispersion = new SidebarMaterialNumberProperty( editor, 'dispersion', strings.getKey( 'sidebar/material/dispersion' ), [ 0, 10 ] );
	container.add( materialDispersion );

	// iridescence

	const materialIridescence = new SidebarMaterialNumberProperty( editor, 'iridescence', strings.getKey( 'sidebar/material/iridescence' ), [ 0, 1 ] );
	container.add( materialIridescence );

	// iridescenceIOR

	const materialIridescenceIOR = new SidebarMaterialNumberProperty( editor, 'iridescenceIOR', strings.getKey( 'sidebar/material/iridescenceIOR' ), [ 1, 5 ] );
	container.add( materialIridescenceIOR );

	// iridescenceThicknessMax

	const materialIridescenceThicknessMax = new SidebarMaterialRangeValueProperty( editor, 'iridescenceThicknessRange', strings.getKey( 'sidebar/material/iridescenceThicknessMax' ), false, [ 0, Infinity ], 0, 10, 1, 'nm' );
	container.add( materialIridescenceThicknessMax );

	// sheen

	const materialSheen = new SidebarMaterialNumberProperty( editor, 'sheen', strings.getKey( 'sidebar/material/sheen' ), [ 0, 1 ] );
	container.add( materialSheen );

	// sheen roughness

	const materialSheenRoughness = new SidebarMaterialNumberProperty( editor, 'sheenRoughness', strings.getKey( 'sidebar/material/sheenroughness' ), [ 0, 1 ] );
	container.add( materialSheenRoughness );

	// sheen color

	const materialSheenColor = new SidebarMaterialColorProperty( editor, 'sheenColor', strings.getKey( 'sidebar/material/sheencolor' ) );
	container.add( materialSheenColor );

	// transmission

	const materialTransmission = new SidebarMaterialNumberProperty( editor, 'transmission', strings.getKey( 'sidebar/material/transmission' ), [ 0, 1 ] );
	container.add( materialTransmission );

	// attenuation distance

	const materialAttenuationDistance = new SidebarMaterialNumberProperty( editor, 'attenuationDistance', strings.getKey( 'sidebar/material/attenuationDistance' ) );
	container.add( materialAttenuationDistance );

	// attenuation tint

	const materialAttenuationColor = new SidebarMaterialColorProperty( editor, 'attenuationColor', strings.getKey( 'sidebar/material/attenuationColor' ) );
	container.add( materialAttenuationColor );

	// thickness

	const materialThickness = new SidebarMaterialNumberProperty( editor, 'thickness', strings.getKey( 'sidebar/material/thickness' ) );
	container.add( materialThickness );

	// vertex colors

	const materialVertexColors = new SidebarMaterialBooleanProperty( editor, 'vertexColors', strings.getKey( 'sidebar/material/vertexcolors' ) );
	container.add( materialVertexColors );

	// depth packing

	const materialDepthPackingOptions = {
		[ THREE.BasicDepthPacking ]: 'Basic',
		[ THREE.RGBADepthPacking ]: 'RGBA'
	};

	const materialDepthPacking = new SidebarMaterialConstantProperty( editor, 'depthPacking', strings.getKey( 'sidebar/material/depthPacking' ), materialDepthPackingOptions );
	container.add( materialDepthPacking );

	// map

	const materialMap = new SidebarMaterialMapProperty( editor, 'map', strings.getKey( 'sidebar/material/map' ) );
	container.add( materialMap );

	// specular map

	const materialSpecularMap = new SidebarMaterialMapProperty( editor, 'specularMap', strings.getKey( 'sidebar/material/specularmap' ) );
	container.add( materialSpecularMap );

	// emissive map

	const materialEmissiveMap = new SidebarMaterialMapProperty( editor, 'emissiveMap', strings.getKey( 'sidebar/material/emissivemap' ) );
	container.add( materialEmissiveMap );

	// matcap map

	const materialMatcapMap = new SidebarMaterialMapProperty( editor, 'matcap', strings.getKey( 'sidebar/material/matcap' ) );
	container.add( materialMatcapMap );

	// alpha map

	const materialAlphaMap = new SidebarMaterialMapProperty( editor, 'alphaMap', strings.getKey( 'sidebar/material/alphamap' ) );
	container.add( materialAlphaMap );

	// bump map

	const materialBumpMap = new SidebarMaterialMapProperty( editor, 'bumpMap', strings.getKey( 'sidebar/material/bumpmap' ) );
	container.add( materialBumpMap );

	// normal map

	const materialNormalMap = new SidebarMaterialMapProperty( editor, 'normalMap', strings.getKey( 'sidebar/material/normalmap' ) );
	container.add( materialNormalMap );

	// clearcoat map

	const materialClearcoatMap = new SidebarMaterialMapProperty( editor, 'clearcoatMap', strings.getKey( 'sidebar/material/clearcoatmap' ) );
	container.add( materialClearcoatMap );

	// clearcoat normal map

	const materialClearcoatNormalMap = new SidebarMaterialMapProperty( editor, 'clearcoatNormalMap', strings.getKey( 'sidebar/material/clearcoatnormalmap' ) );
	container.add( materialClearcoatNormalMap );

	// clearcoat roughness map

	const materialClearcoatRoughnessMap = new SidebarMaterialMapProperty( editor, 'clearcoatRoughnessMap', strings.getKey( 'sidebar/material/clearcoatroughnessmap' ) );
	container.add( materialClearcoatRoughnessMap );

	// displacement map

	const materialDisplacementMap = new SidebarMaterialMapProperty( editor, 'displacementMap', strings.getKey( 'sidebar/material/displacementmap' ) );
	container.add( materialDisplacementMap );

	// roughness map

	const materialRoughnessMap = new SidebarMaterialMapProperty( editor, 'roughnessMap', strings.getKey( 'sidebar/material/roughnessmap' ) );
	container.add( materialRoughnessMap );

	// metalness map

	const materialMetalnessMap = new SidebarMaterialMapProperty( editor, 'metalnessMap', strings.getKey( 'sidebar/material/metalnessmap' ) );
	container.add( materialMetalnessMap );

	// iridescence map

	const materialIridescenceMap = new SidebarMaterialMapProperty( editor, 'iridescenceMap', strings.getKey( 'sidebar/material/iridescencemap' ) );
	container.add( materialIridescenceMap );

	// sheen color map

	const materialSheenColorMap = new SidebarMaterialMapProperty( editor, 'sheenColorMap', strings.getKey( 'sidebar/material/sheencolormap' ) );
	container.add( materialSheenColorMap );

	// sheen roughness map

	const materialSheenRoughnessMap = new SidebarMaterialMapProperty( editor, 'sheenRoughnessMap', strings.getKey( 'sidebar/material/sheenroughnessmap' ) );
	container.add( materialSheenRoughnessMap );

	// iridescence thickness map

	const materialIridescenceThicknessMap = new SidebarMaterialMapProperty( editor, 'iridescenceThicknessMap', strings.getKey( 'sidebar/material/iridescencethicknessmap' ) );
	container.add( materialIridescenceThicknessMap );

	// env map

	const materialEnvMap = new SidebarMaterialMapProperty( editor, 'envMap', strings.getKey( 'sidebar/material/envmap' ) );
	container.add( materialEnvMap );

	// light map

	const materialLightMap = new SidebarMaterialMapProperty( editor, 'lightMap', strings.getKey( 'sidebar/material/lightmap' ) );
	container.add( materialLightMap );

	// ambient occlusion map

	const materialAOMap = new SidebarMaterialMapProperty( editor, 'aoMap', strings.getKey( 'sidebar/material/aomap' ) );
	container.add( materialAOMap );

	// gradient map

	const materialGradientMap = new SidebarMaterialMapProperty( editor, 'gradientMap', strings.getKey( 'sidebar/material/gradientmap' ) );
	container.add( materialGradientMap );

	// transmission map

	const transmissionMap = new SidebarMaterialMapProperty( editor, 'transmissionMap', strings.getKey( 'sidebar/material/transmissionmap' ) );
	container.add( transmissionMap );

	// thickness map

	const thicknessMap = new SidebarMaterialMapProperty( editor, 'thicknessMap', strings.getKey( 'sidebar/material/thicknessmap' ) );
	container.add( thicknessMap );

	// side

	const materialSideOptions = {
		0: 'Front',
		1: 'Back',
		2: 'Double'
	};

	const materialSide = new SidebarMaterialConstantProperty( editor, 'side', strings.getKey( 'sidebar/material/side' ), materialSideOptions );
	container.add( materialSide );

	// size

	const materialSize = new SidebarMaterialNumberProperty( editor, 'size', strings.getKey( 'sidebar/material/size' ), [ 0, Infinity ] );
	container.add( materialSize );

	// sizeAttenuation

	const materialSizeAttenuation = new SidebarMaterialBooleanProperty( editor, 'sizeAttenuation', strings.getKey( 'sidebar/material/sizeAttenuation' ) );
	container.add( materialSizeAttenuation );

	// flatShading

	const materialFlatShading = new SidebarMaterialBooleanProperty( editor, 'flatShading', strings.getKey( 'sidebar/material/flatShading' ) );
	container.add( materialFlatShading );

	// blending

	const materialBlendingOptions = {
		0: 'No',
		1: 'Normal',
		2: 'Additive',
		3: 'Subtractive',
		4: 'Multiply',
		5: 'Custom'
	};

	const materialBlending = new SidebarMaterialConstantProperty( editor, 'blending', strings.getKey( 'sidebar/material/blending' ), materialBlendingOptions );
	container.add( materialBlending );

	// opacity

	const materialOpacity = new SidebarMaterialNumberProperty( editor, 'opacity', strings.getKey( 'sidebar/material/opacity' ), [ 0, 1 ] );
	container.add( materialOpacity );

	// transparent

	const materialTransparent = new SidebarMaterialBooleanProperty( editor, 'transparent', strings.getKey( 'sidebar/material/transparent' ) );
	container.add( materialTransparent );

	// forceSinglePass

	const materialForceSinglePass = new SidebarMaterialBooleanProperty( editor, 'forceSinglePass', strings.getKey( 'sidebar/material/forcesinglepass' ) );
	container.add( materialForceSinglePass );

	// alpha test

	const materialAlphaTest = new SidebarMaterialNumberProperty( editor, 'alphaTest', strings.getKey( 'sidebar/material/alphatest' ), [ 0, 1 ] );
	container.add( materialAlphaTest );

	// depth test

	const materialDepthTest = new SidebarMaterialBooleanProperty( editor, 'depthTest', strings.getKey( 'sidebar/material/depthtest' ) );
	container.add( materialDepthTest );

	// depth write

	const materialDepthWrite = new SidebarMaterialBooleanProperty( editor, 'depthWrite', strings.getKey( 'sidebar/material/depthwrite' ) );
	container.add( materialDepthWrite );

	// wireframe

	const materialWireframe = new SidebarMaterialBooleanProperty( editor, 'wireframe', strings.getKey( 'sidebar/material/wireframe' ) );
	container.add( materialWireframe );

	// userData

	const materialUserDataRow = new UIRow();
	const materialUserData = new UITextArea().setWidth( '150px' ).setHeight( '40px' ).setFontSize( '12px' ).onChange( update );
	materialUserData.onKeyUp( function () {

		try {

			JSON.parse( materialUserData.getValue() );

			materialUserData.dom.classList.add( 'success' );
			materialUserData.dom.classList.remove( 'fail' );

		} catch ( error ) {

			materialUserData.dom.classList.remove( 'success' );
			materialUserData.dom.classList.add( 'fail' );

		}

	} );

	materialUserDataRow.add( new UIText( strings.getKey( 'sidebar/material/userdata' ) ).setClass( 'Label' ) );
	materialUserDataRow.add( materialUserData );

	container.add( materialUserDataRow );

	// Export JSON

	const exportJson = new UIButton( strings.getKey( 'sidebar/material/export' ) );
	exportJson.setMarginLeft( '120px' );
	exportJson.onClick( function () {

		const object = editor.selected;
		const material = Array.isArray( object.material ) ? object.material[ currentMaterialSlot ] : object.material;

		let output = material.toJSON();

		try {

			output = JSON.stringify( output, null, '\t' );
			output = output.replace( /[\n\t]+([\d\.e\-\[\]]+)/g, '$1' );

		} catch ( e ) {

			output = JSON.stringify( output );

		}

		editor.utils.save( new Blob( [ output ] ), `${ materialName.getValue() || 'material' }.json` );

	} );
	container.add( exportJson );

	//

	function update() {

		const previousSelectedSlot = currentMaterialSlot;

		currentMaterialSlot = parseInt( materialSlotSelect.getValue() );

		if ( currentMaterialSlot !== previousSelectedSlot ) {

			editor.signals.materialChanged.dispatch( currentObject, currentMaterialSlot );

		}

		let material = editor.getObjectMaterial( currentObject, currentMaterialSlot );

		if ( material ) {

			if ( material.uuid !== undefined && material.uuid !== materialUUID.getValue() ) {

				editor.execute( new SetMaterialValueCommand( editor, currentObject, 'uuid', materialUUID.getValue(), currentMaterialSlot ) );

			}

			if ( material.type !== materialClass.getValue() ) {

				material = new materialClasses[ materialClass.getValue() ]();

				if ( material.type === 'RawShaderMaterial' ) {

					material.vertexShader = vertexShaderVariables + material.vertexShader;

				}

				const currentMaterial = currentObject.material;

				if ( material.type === 'MeshPhysicalMaterial' && currentMaterial.type === 'MeshStandardMaterial' ) {

					// TODO Find a easier to maintain approach

					const properties = [
						'color', 'emissive', 'roughness', 'metalness', 'map', 'emissiveMap', 'alphaMap',
						'bumpMap', 'normalMap', 'normalScale', 'displacementMap', 'roughnessMap', 'metalnessMap',
						'envMap', 'lightMap', 'aoMap', 'side'
					];

					for ( const property of properties ) {

						const value = currentMaterial[ property ];

						if ( value === null ) continue;

						if ( value[ 'clone' ] !== undefined ) {

							material[ property ] = value.clone();

						} else {

							material[ property ] = value;

						}

					}

				}

				if ( Array.isArray( currentMaterial ) ) {

					// don't remove the entire multi-material. just the material of the selected slot

					editor.removeMaterial( currentMaterial[ currentMaterialSlot ] );

				} else {

					editor.removeMaterial( currentMaterial );

				}

				editor.execute( new SetMaterialCommand( editor, currentObject, material, currentMaterialSlot ), strings.getKey( 'command/SetMaterial' ) + ': ' + materialClass.getValue() );
				editor.addMaterial( material );
				// TODO Copy other references in the scene graph
				// keeping name and UUID then.
				// Also there should be means to create a unique
				// copy for the current object explicitly and to
				// attach the current material to other objects.

			}

			try {

				const userData = JSON.parse( materialUserData.getValue() );
				if ( JSON.stringify( material.userData ) != JSON.stringify( userData ) ) {

					editor.execute( new SetMaterialValueCommand( editor, currentObject, 'userData', userData, currentMaterialSlot ) );

				}

			} catch ( exception ) {

				console.warn( exception );

			}

			refreshUI();

		}

	}

	//

	function setRowVisibility() {

		const material = currentObject.material;

		if ( Array.isArray( material ) ) {

			materialSlotRow.setDisplay( '' );

		} else {

			materialSlotRow.setDisplay( 'none' );

		}

	}

	function refreshUI() {

		if ( ! currentObject ) return;

		let material = currentObject.material;

		if ( Array.isArray( material ) ) {

			const slotOptions = {};

			currentMaterialSlot = Math.max( 0, Math.min( material.length, currentMaterialSlot ) );

			for ( let i = 0; i < material.length; i ++ ) {

				slotOptions[ i ] = String( i + 1 ) + ': ' + material[ i ].name;

			}

			materialSlotSelect.setOptions( slotOptions ).setValue( currentMaterialSlot );

		}

		material = editor.getObjectMaterial( currentObject, currentMaterialSlot );

		if ( material.uuid !== undefined ) {

			materialUUID.setValue( material.uuid );

		}

		if ( material.name !== undefined ) {

			materialName.setValue( material.name );

		}

		if ( currentObject.isMesh ) {

			materialClass.setOptions( meshMaterialOptions );

		} else if ( currentObject.isSprite ) {

			materialClass.setOptions( spriteMaterialOptions );

		} else if ( currentObject.isPoints ) {

			materialClass.setOptions( pointsMaterialOptions );

		} else if ( currentObject.isLine ) {

			materialClass.setOptions( lineMaterialOptions );

		}

		materialClass.setValue( material.type );

		setRowVisibility();

		try {

			materialUserData.setValue( JSON.stringify( material.userData, null, '  ' ) );

		} catch ( error ) {

			console.log( error );

		}

		materialUserData.setBorderColor( 'transparent' );
		materialUserData.setBackgroundColor( '' );

	}

	// events

	signals.objectSelected.add( function ( object ) {

		let hasMaterial = false;

		if ( object && object.material ) {

			hasMaterial = true;

			if ( Array.isArray( object.material ) && object.material.length === 0 ) {

				hasMaterial = false;

			}

		}

		if ( hasMaterial ) {

			currentObject = object;
			refreshUI();
			container.setDisplay( '' );

		} else {

			currentObject = null;
			container.setDisplay( 'none' );

		}

	} );

	signals.materialChanged.add( refreshUI );

	return container;

}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `parseInt`
- `materialSlotSelect.getValue`
- `editor.signals.materialChanged.dispatch`
- `editor.getObjectMaterial`
- `materialUUID.getValue`
- `editor.execute`
- `materialClass.getValue`
- `value.clone`
- `Array.isArray`
- `editor.removeMaterial`
- `strings.getKey`
- `editor.addMaterial`
- `JSON.parse`
- `materialUserData.getValue`
- `JSON.stringify`
- `console.warn`
- `refreshUI`

**Internal Comments:**
```
// TODO Find a easier to maintain approach (x2)
// don't remove the entire multi-material. just the material of the selected slot (x4)
```

<details><summary>Code</summary>

```typescript
function update() {

		const previousSelectedSlot = currentMaterialSlot;

		currentMaterialSlot = parseInt( materialSlotSelect.getValue() );

		if ( currentMaterialSlot !== previousSelectedSlot ) {

			editor.signals.materialChanged.dispatch( currentObject, currentMaterialSlot );

		}

		let material = editor.getObjectMaterial( currentObject, currentMaterialSlot );

		if ( material ) {

			if ( material.uuid !== undefined && material.uuid !== materialUUID.getValue() ) {

				editor.execute( new SetMaterialValueCommand( editor, currentObject, 'uuid', materialUUID.getValue(), currentMaterialSlot ) );

			}

			if ( material.type !== materialClass.getValue() ) {

				material = new materialClasses[ materialClass.getValue() ]();

				if ( material.type === 'RawShaderMaterial' ) {

					material.vertexShader = vertexShaderVariables + material.vertexShader;

				}

				const currentMaterial = currentObject.material;

				if ( material.type === 'MeshPhysicalMaterial' && currentMaterial.type === 'MeshStandardMaterial' ) {

					// TODO Find a easier to maintain approach

					const properties = [
						'color', 'emissive', 'roughness', 'metalness', 'map', 'emissiveMap', 'alphaMap',
						'bumpMap', 'normalMap', 'normalScale', 'displacementMap', 'roughnessMap', 'metalnessMap',
						'envMap', 'lightMap', 'aoMap', 'side'
					];

					for ( const property of properties ) {

						const value = currentMaterial[ property ];

						if ( value === null ) continue;

						if ( value[ 'clone' ] !== undefined ) {

							material[ property ] = value.clone();

						} else {

							material[ property ] = value;

						}

					}

				}

				if ( Array.isArray( currentMaterial ) ) {

					// don't remove the entire multi-material. just the material of the selected slot

					editor.removeMaterial( currentMaterial[ currentMaterialSlot ] );

				} else {

					editor.removeMaterial( currentMaterial );

				}

				editor.execute( new SetMaterialCommand( editor, currentObject, material, currentMaterialSlot ), strings.getKey( 'command/SetMaterial' ) + ': ' + materialClass.getValue() );
				editor.addMaterial( material );
				// TODO Copy other references in the scene graph
				// keeping name and UUID then.
				// Also there should be means to create a unique
				// copy for the current object explicitly and to
				// attach the current material to other objects.

			}

			try {

				const userData = JSON.parse( materialUserData.getValue() );
				if ( JSON.stringify( material.userData ) != JSON.stringify( userData ) ) {

					editor.execute( new SetMaterialValueCommand( editor, currentObject, 'userData', userData, currentMaterialSlot ) );

				}

			} catch ( exception ) {

				console.warn( exception );

			}

			refreshUI();

		}

	}
```
</details>

### `setRowVisibility(): void`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `materialSlotRow.setDisplay`

<details><summary>Code</summary>

```typescript
function setRowVisibility() {

		const material = currentObject.material;

		if ( Array.isArray( material ) ) {

			materialSlotRow.setDisplay( '' );

		} else {

			materialSlotRow.setDisplay( 'none' );

		}

	}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `Math.max`
- `Math.min`
- `String`
- `materialSlotSelect.setOptions( slotOptions ).setValue`
- `editor.getObjectMaterial`
- `materialUUID.setValue`
- `materialName.setValue`
- `materialClass.setOptions`
- `materialClass.setValue`
- `setRowVisibility`
- `materialUserData.setValue`
- `JSON.stringify`
- `console.log`
- `materialUserData.setBorderColor`
- `materialUserData.setBackgroundColor`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		if ( ! currentObject ) return;

		let material = currentObject.material;

		if ( Array.isArray( material ) ) {

			const slotOptions = {};

			currentMaterialSlot = Math.max( 0, Math.min( material.length, currentMaterialSlot ) );

			for ( let i = 0; i < material.length; i ++ ) {

				slotOptions[ i ] = String( i + 1 ) + ': ' + material[ i ].name;

			}

			materialSlotSelect.setOptions( slotOptions ).setValue( currentMaterialSlot );

		}

		material = editor.getObjectMaterial( currentObject, currentMaterialSlot );

		if ( material.uuid !== undefined ) {

			materialUUID.setValue( material.uuid );

		}

		if ( material.name !== undefined ) {

			materialName.setValue( material.name );

		}

		if ( currentObject.isMesh ) {

			materialClass.setOptions( meshMaterialOptions );

		} else if ( currentObject.isSprite ) {

			materialClass.setOptions( spriteMaterialOptions );

		} else if ( currentObject.isPoints ) {

			materialClass.setOptions( pointsMaterialOptions );

		} else if ( currentObject.isLine ) {

			materialClass.setOptions( lineMaterialOptions );

		}

		materialClass.setValue( material.type );

		setRowVisibility();

		try {

			materialUserData.setValue( JSON.stringify( material.userData, null, '  ' ) );

		} catch ( error ) {

			console.log( error );

		}

		materialUserData.setBorderColor( 'transparent' );
		materialUserData.setBackgroundColor( '' );

	}
```
</details>


---