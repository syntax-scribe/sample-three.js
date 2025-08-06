[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Object.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📦 Imports | 19 |
| 📊 Variables & Constants | 41 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Object.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIInput` | `./libs/ui.js` |
| `UIButton` | `./libs/ui.js` |
| `UIColor` | `./libs/ui.js` |
| `UICheckbox` | `./libs/ui.js` |
| `UIInteger` | `./libs/ui.js` |
| `UITextArea` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UINumber` | `./libs/ui.js` |
| `UIBoolean` | `./libs/ui.three.js` |
| `SetUuidCommand` | `./commands/SetUuidCommand.js` |
| `SetValueCommand` | `./commands/SetValueCommand.js` |
| `SetPositionCommand` | `./commands/SetPositionCommand.js` |
| `SetRotationCommand` | `./commands/SetRotationCommand.js` |
| `SetScaleCommand` | `./commands/SetScaleCommand.js` |
| `SetColorCommand` | `./commands/SetColorCommand.js` |
| `SetShadowValueCommand` | `./commands/SetShadowValueCommand.js` |
| `SidebarObjectAnimation` | `./Sidebar.Object.Animation.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `objectTypeRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectType` | `UIText` | let/var | `new UIText()` | ✗ |
| `objectUUIDRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectNameRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectPositionRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectRotationRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectScaleRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectFovRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectLeftRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectRightRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectTopRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectBottomRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectNearRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectFarRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectIntensityRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectColorRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectGroundColorRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectDistanceRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectAngleRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectPenumbraRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectDecayRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectShadowRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectShadowIntensityRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectShadowBiasRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectShadowNormalBiasRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectShadowRadiusRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectVisibleRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectFrustumCulledRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectRenderOrderRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `objectUserDataRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `exportJson` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/object/export' ) )` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |
| `newPosition` | `any` | let/var | `new THREE.Vector3( objectPositionX.getValue(), objectPositionY.getValue(), ob...` | ✗ |
| `newRotation` | `any` | let/var | `new THREE.Euler( objectRotationX.getValue() * THREE.MathUtils.DEG2RAD, object...` | ✗ |
| `newScale` | `any` | let/var | `new THREE.Vector3( objectScaleX.getValue(), objectScaleY.getValue(), objectSc...` | ✗ |
| `properties` | `{ fov: UIRow; left: UIRow; right: UIR...` | let/var | `{ 'fov': objectFovRow, 'left': objectLeftRow, 'right': objectRightRow, 'top':...` | ✗ |
| `uiElement` | `any` | let/var | `properties[ property ]` | ✗ |


---

## Functions

### `SidebarObject(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setBorderTop`
- `container.setPaddingTop`
- `container.setDisplay`
- `objectTypeRow.add`
- `new UIText( strings.getKey( 'sidebar/object/type' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UIInput().setWidth( '102px' ).setFontSize( '12px' ).setDisabled`
- `new UIButton( strings.getKey( 'sidebar/object/new' ) ).setMarginLeft( '7px' ).onClick`
- `objectUUID.setValue`
- `THREE.MathUtils.generateUUID`
- `editor.execute`
- `objectUUID.getValue`
- `objectUUIDRow.add`
- `new UIText( strings.getKey( 'sidebar/object/uuid' ) ).setClass`
- `new UIInput().setWidth( '150px' ).setFontSize( '12px' ).onChange`
- `objectName.getValue`
- `objectNameRow.add`
- `new UIText( strings.getKey( 'sidebar/object/name' ) ).setClass`
- `new UINumber().setPrecision( 3 ).setWidth( '50px' ).onChange`
- `objectPositionRow.add`
- `new UIText( strings.getKey( 'sidebar/object/position' ) ).setClass`
- `new UINumber().setStep( 10 ).setNudge( 0.1 ).setUnit( '°' ).setWidth( '50px' ).onChange`
- `objectRotationRow.add`
- `new UIText( strings.getKey( 'sidebar/object/rotation' ) ).setClass`
- `new UINumber( 1 ).setPrecision( 3 ).setWidth( '50px' ).onChange`
- `objectScaleRow.add`
- `new UIText( strings.getKey( 'sidebar/object/scale' ) ).setClass`
- `new UINumber().onChange`
- `objectFovRow.add`
- `new UIText( strings.getKey( 'sidebar/object/fov' ) ).setClass`
- `objectLeftRow.add`
- `new UIText( strings.getKey( 'sidebar/object/left' ) ).setClass`
- `objectRightRow.add`
- `new UIText( strings.getKey( 'sidebar/object/right' ) ).setClass`
- `objectTopRow.add`
- `new UIText( strings.getKey( 'sidebar/object/top' ) ).setClass`
- `objectBottomRow.add`
- `new UIText( strings.getKey( 'sidebar/object/bottom' ) ).setClass`
- `objectNearRow.add`
- `new UIText( strings.getKey( 'sidebar/object/near' ) ).setClass`
- `objectFarRow.add`
- `new UIText( strings.getKey( 'sidebar/object/far' ) ).setClass`
- `objectIntensityRow.add`
- `new UIText( strings.getKey( 'sidebar/object/intensity' ) ).setClass`
- `new UIColor().onInput`
- `objectColorRow.add`
- `new UIText( strings.getKey( 'sidebar/object/color' ) ).setClass`
- `objectGroundColorRow.add`
- `new UIText( strings.getKey( 'sidebar/object/groundcolor' ) ).setClass`
- `new UINumber().setRange( 0, Infinity ).onChange`
- `objectDistanceRow.add`
- `new UIText( strings.getKey( 'sidebar/object/distance' ) ).setClass`
- `new UINumber().setPrecision( 3 ).setRange( 0, Math.PI / 2 ).onChange`
- `objectAngleRow.add`
- `new UIText( strings.getKey( 'sidebar/object/angle' ) ).setClass`
- `new UINumber().setRange( 0, 1 ).onChange`
- `objectPenumbraRow.add`
- `new UIText( strings.getKey( 'sidebar/object/penumbra' ) ).setClass`
- `objectDecayRow.add`
- `new UIText( strings.getKey( 'sidebar/object/decay' ) ).setClass`
- `objectShadowRow.add`
- `new UIText( strings.getKey( 'sidebar/object/shadow' ) ).setClass`
- `new UIBoolean( false, strings.getKey( 'sidebar/object/cast' ) ).onChange`
- `new UIBoolean( false, strings.getKey( 'sidebar/object/receive' ) ).onChange`
- `objectShadowIntensityRow.add`
- `new UIText( strings.getKey( 'sidebar/object/shadowIntensity' ) ).setClass`
- `new UINumber( 0 ).setRange( 0, 1 ).onChange`
- `objectShadowBiasRow.add`
- `new UIText( strings.getKey( 'sidebar/object/shadowBias' ) ).setClass`
- `new UINumber( 0 ).setPrecision( 5 ).setStep( 0.0001 ).setNudge( 0.00001 ).onChange`
- `objectShadowNormalBiasRow.add`
- `new UIText( strings.getKey( 'sidebar/object/shadowNormalBias' ) ).setClass`
- `new UINumber( 0 ).onChange`
- `objectShadowRadiusRow.add`
- `new UIText( strings.getKey( 'sidebar/object/shadowRadius' ) ).setClass`
- `new UINumber( 1 ).onChange`
- `new UICheckbox().onChange`
- `objectVisibleRow.add`
- `new UIText( strings.getKey( 'sidebar/object/visible' ) ).setClass`
- `objectFrustumCulledRow.add`
- `new UIText( strings.getKey( 'sidebar/object/frustumcull' ) ).setClass`
- `new UIInteger().setWidth( '50px' ).onChange`
- `objectRenderOrderRow.add`
- `new UIText( strings.getKey( 'sidebar/object/renderorder' ) ).setClass`
- `new UITextArea().setWidth( '150px' ).setHeight( '40px' ).setFontSize( '12px' ).onChange`
- `objectUserData.onKeyUp`
- `JSON.parse`
- `objectUserData.getValue`
- `objectUserData.dom.classList.add`
- `objectUserData.dom.classList.remove`
- `objectUserDataRow.add`
- `new UIText( strings.getKey( 'sidebar/object/userdata' ) ).setClass`
- `exportJson.setMarginLeft`
- `exportJson.onClick`
- `object.toJSON`
- `JSON.stringify`
- `output.replace`
- `editor.utils.save`
- `objectPositionX.getValue`
- `objectPositionY.getValue`
- `objectPositionZ.getValue`
- `object.position.distanceTo`
- `objectRotationX.getValue`
- `objectRotationY.getValue`
- `objectRotationZ.getValue`
- `new THREE.Vector3().setFromEuler( object.rotation ).distanceTo`
- `new THREE.Vector3().setFromEuler`
- `objectScaleX.getValue`
- `objectScaleY.getValue`
- `objectScaleZ.getValue`
- `object.scale.distanceTo`
- `Math.abs`
- `objectFov.getValue`
- `object.updateProjectionMatrix`
- `objectLeft.getValue`
- `objectRight.getValue`
- `objectTop.getValue`
- `objectBottom.getValue`
- `objectNear.getValue`
- `objectFar.getValue`
- `objectIntensity.getValue`
- `object.color.getHex`
- `objectColor.getHexValue`
- `object.groundColor.getHex`
- `objectGroundColor.getHexValue`
- `objectDistance.getValue`
- `objectAngle.getValue`
- `objectPenumbra.getValue`
- `objectDecay.getValue`
- `objectVisible.getValue`
- `objectFrustumCulled.getValue`
- `objectRenderOrder.getValue`
- `objectCastShadow.getValue`
- `objectReceiveShadow.getValue`
- `objectShadowIntensity.getValue`
- `objectShadowBias.getValue`
- `objectShadowNormalBias.getValue`
- `objectShadowRadius.getValue`
- `console.warn`
- `Array.isArray`
- `uiElement[ i ].setDisplay`
- `uiElement.setDisplay`
- `objectReceiveShadow.setDisplay`
- `objectShadowRow.setDisplay`
- `objectRotationRow.setDisplay`
- `objectScaleRow.setDisplay`
- `signals.objectSelected.add`
- `updateRows`
- `updateUI`
- `signals.objectChanged.add`
- `signals.refreshSidebarObject3D.add`
- `objectType.setValue`
- `objectName.setValue`
- `objectPositionX.setValue`
- `objectPositionY.setValue`
- `objectPositionZ.setValue`
- `objectRotationX.setValue`
- `objectRotationY.setValue`
- `objectRotationZ.setValue`
- `objectScaleX.setValue`
- `objectScaleY.setValue`
- `objectScaleZ.setValue`
- `objectFov.setValue`
- `objectLeft.setValue`
- `objectRight.setValue`
- `objectTop.setValue`
- `objectBottom.setValue`
- `objectNear.setValue`
- `objectFar.setValue`
- `objectIntensity.setValue`
- `objectColor.setHexValue`
- `object.color.getHexString`
- `objectGroundColor.setHexValue`
- `object.groundColor.getHexString`
- `objectDistance.setValue`
- `objectAngle.setValue`
- `objectPenumbra.setValue`
- `objectDecay.setValue`
- `objectCastShadow.setValue`
- `objectReceiveShadow.setValue`
- `objectShadowIntensity.setValue`
- `objectShadowBias.setValue`
- `objectShadowNormalBias.setValue`
- `objectShadowRadius.setValue`
- `objectVisible.setValue`
- `objectFrustumCulled.setValue`
- `objectRenderOrder.setValue`
- `objectUserData.setValue`
- `console.log`
- `objectUserData.setBorderColor`
- `objectUserData.setBackgroundColor`
- `updateTransformRows`

**Internal Comments:**
```
// Actions (x2)
/*
	let objectActions = new UI.Select().setPosition( 'absolute' ).setRight( '8px' ).setFontSize( '11px' );
	objectActions.setOptions( {

		'Actions': 'Actions',
		'Reset Position': 'Reset Position',
		'Reset Rotation': 'Reset Rotation',
		'Reset Scale': 'Reset Scale'

	} );
	objectActions.onClick( function ( event ) {

		event.stopPropagation(); // Avoid panel collapsing

	} );
	objectActions.onChange( function ( event ) {

		let object = editor.selected;

		switch ( this.getValue() ) {

			case 'Reset Position':
				editor.execute( new SetPositionCommand( editor, object, new Vector3( 0, 0, 0 ) ) );
				break;

			case 'Reset Rotation':
				editor.execute( new SetRotationCommand( editor, object, new Euler( 0, 0, 0 ) ) );
				break;

			case 'Reset Scale':
				editor.execute( new SetScaleCommand( editor, object, new Vector3( 1, 1, 1 ) ) );
				break;

		}

		this.setValue( 'Actions' );

	} );
	container.addStatic( objectActions );
	*/ (x2)
// type (x2)
// uuid (x2)
// name (x2)
// position (x2)
// rotation (x2)
// scale (x2)
// fov (x2)
// left (x2)
// right (x2)
// top (x2)
// bottom (x2)
// near (x2)
// far (x2)
// intensity (x2)
// color (x2)
// ground color (x2)
// distance (x2)
// angle (x2)
// penumbra (x2)
// decay (x2)
// shadow (x2)
// shadow intensity (x2)
// shadow bias (x2)
// shadow normal offset (x2)
// shadow radius (x2)
// visible (x2)
// frustumCulled (x2)
// renderOrder (x2)
// user data (x2)
// Export JSON (x2)
// Animations (x4)
// (x2)
// events (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarObject( editor ) {

	const strings = editor.strings;

	const signals = editor.signals;

	const container = new UIPanel();
	container.setBorderTop( '0' );
	container.setPaddingTop( '20px' );
	container.setDisplay( 'none' );

	// Actions

	/*
	let objectActions = new UI.Select().setPosition( 'absolute' ).setRight( '8px' ).setFontSize( '11px' );
	objectActions.setOptions( {

		'Actions': 'Actions',
		'Reset Position': 'Reset Position',
		'Reset Rotation': 'Reset Rotation',
		'Reset Scale': 'Reset Scale'

	} );
	objectActions.onClick( function ( event ) {

		event.stopPropagation(); // Avoid panel collapsing

	} );
	objectActions.onChange( function ( event ) {

		let object = editor.selected;

		switch ( this.getValue() ) {

			case 'Reset Position':
				editor.execute( new SetPositionCommand( editor, object, new Vector3( 0, 0, 0 ) ) );
				break;

			case 'Reset Rotation':
				editor.execute( new SetRotationCommand( editor, object, new Euler( 0, 0, 0 ) ) );
				break;

			case 'Reset Scale':
				editor.execute( new SetScaleCommand( editor, object, new Vector3( 1, 1, 1 ) ) );
				break;

		}

		this.setValue( 'Actions' );

	} );
	container.addStatic( objectActions );
	*/

	// type

	const objectTypeRow = new UIRow();
	const objectType = new UIText();

	objectTypeRow.add( new UIText( strings.getKey( 'sidebar/object/type' ) ).setClass( 'Label' ) );
	objectTypeRow.add( objectType );

	container.add( objectTypeRow );

	// uuid

	const objectUUIDRow = new UIRow();
	const objectUUID = new UIInput().setWidth( '102px' ).setFontSize( '12px' ).setDisabled( true );
	const objectUUIDRenew = new UIButton( strings.getKey( 'sidebar/object/new' ) ).setMarginLeft( '7px' ).onClick( function () {

		objectUUID.setValue( THREE.MathUtils.generateUUID() );

		editor.execute( new SetUuidCommand( editor, editor.selected, objectUUID.getValue() ) );

	} );

	objectUUIDRow.add( new UIText( strings.getKey( 'sidebar/object/uuid' ) ).setClass( 'Label' ) );
	objectUUIDRow.add( objectUUID );
	objectUUIDRow.add( objectUUIDRenew );

	container.add( objectUUIDRow );

	// name

	const objectNameRow = new UIRow();
	const objectName = new UIInput().setWidth( '150px' ).setFontSize( '12px' ).onChange( function () {

		editor.execute( new SetValueCommand( editor, editor.selected, 'name', objectName.getValue() ) );

	} );

	objectNameRow.add( new UIText( strings.getKey( 'sidebar/object/name' ) ).setClass( 'Label' ) );
	objectNameRow.add( objectName );

	container.add( objectNameRow );

	// position

	const objectPositionRow = new UIRow();
	const objectPositionX = new UINumber().setPrecision( 3 ).setWidth( '50px' ).onChange( update );
	const objectPositionY = new UINumber().setPrecision( 3 ).setWidth( '50px' ).onChange( update );
	const objectPositionZ = new UINumber().setPrecision( 3 ).setWidth( '50px' ).onChange( update );

	objectPositionRow.add( new UIText( strings.getKey( 'sidebar/object/position' ) ).setClass( 'Label' ) );
	objectPositionRow.add( objectPositionX, objectPositionY, objectPositionZ );

	container.add( objectPositionRow );

	// rotation

	const objectRotationRow = new UIRow();
	const objectRotationX = new UINumber().setStep( 10 ).setNudge( 0.1 ).setUnit( '°' ).setWidth( '50px' ).onChange( update );
	const objectRotationY = new UINumber().setStep( 10 ).setNudge( 0.1 ).setUnit( '°' ).setWidth( '50px' ).onChange( update );
	const objectRotationZ = new UINumber().setStep( 10 ).setNudge( 0.1 ).setUnit( '°' ).setWidth( '50px' ).onChange( update );

	objectRotationRow.add( new UIText( strings.getKey( 'sidebar/object/rotation' ) ).setClass( 'Label' ) );
	objectRotationRow.add( objectRotationX, objectRotationY, objectRotationZ );

	container.add( objectRotationRow );

	// scale

	const objectScaleRow = new UIRow();
	const objectScaleX = new UINumber( 1 ).setPrecision( 3 ).setWidth( '50px' ).onChange( update );
	const objectScaleY = new UINumber( 1 ).setPrecision( 3 ).setWidth( '50px' ).onChange( update );
	const objectScaleZ = new UINumber( 1 ).setPrecision( 3 ).setWidth( '50px' ).onChange( update );

	objectScaleRow.add( new UIText( strings.getKey( 'sidebar/object/scale' ) ).setClass( 'Label' ) );
	objectScaleRow.add( objectScaleX, objectScaleY, objectScaleZ );

	container.add( objectScaleRow );

	// fov

	const objectFovRow = new UIRow();
	const objectFov = new UINumber().onChange( update );

	objectFovRow.add( new UIText( strings.getKey( 'sidebar/object/fov' ) ).setClass( 'Label' ) );
	objectFovRow.add( objectFov );

	container.add( objectFovRow );

	// left

	const objectLeftRow = new UIRow();
	const objectLeft = new UINumber().onChange( update );

	objectLeftRow.add( new UIText( strings.getKey( 'sidebar/object/left' ) ).setClass( 'Label' ) );
	objectLeftRow.add( objectLeft );

	container.add( objectLeftRow );

	// right

	const objectRightRow = new UIRow();
	const objectRight = new UINumber().onChange( update );

	objectRightRow.add( new UIText( strings.getKey( 'sidebar/object/right' ) ).setClass( 'Label' ) );
	objectRightRow.add( objectRight );

	container.add( objectRightRow );

	// top

	const objectTopRow = new UIRow();
	const objectTop = new UINumber().onChange( update );

	objectTopRow.add( new UIText( strings.getKey( 'sidebar/object/top' ) ).setClass( 'Label' ) );
	objectTopRow.add( objectTop );

	container.add( objectTopRow );

	// bottom

	const objectBottomRow = new UIRow();
	const objectBottom = new UINumber().onChange( update );

	objectBottomRow.add( new UIText( strings.getKey( 'sidebar/object/bottom' ) ).setClass( 'Label' ) );
	objectBottomRow.add( objectBottom );

	container.add( objectBottomRow );

	// near

	const objectNearRow = new UIRow();
	const objectNear = new UINumber().onChange( update );

	objectNearRow.add( new UIText( strings.getKey( 'sidebar/object/near' ) ).setClass( 'Label' ) );
	objectNearRow.add( objectNear );

	container.add( objectNearRow );

	// far

	const objectFarRow = new UIRow();
	const objectFar = new UINumber().onChange( update );

	objectFarRow.add( new UIText( strings.getKey( 'sidebar/object/far' ) ).setClass( 'Label' ) );
	objectFarRow.add( objectFar );

	container.add( objectFarRow );

	// intensity

	const objectIntensityRow = new UIRow();
	const objectIntensity = new UINumber().onChange( update );

	objectIntensityRow.add( new UIText( strings.getKey( 'sidebar/object/intensity' ) ).setClass( 'Label' ) );
	objectIntensityRow.add( objectIntensity );

	container.add( objectIntensityRow );

	// color

	const objectColorRow = new UIRow();
	const objectColor = new UIColor().onInput( update );

	objectColorRow.add( new UIText( strings.getKey( 'sidebar/object/color' ) ).setClass( 'Label' ) );
	objectColorRow.add( objectColor );

	container.add( objectColorRow );

	// ground color

	const objectGroundColorRow = new UIRow();
	const objectGroundColor = new UIColor().onInput( update );

	objectGroundColorRow.add( new UIText( strings.getKey( 'sidebar/object/groundcolor' ) ).setClass( 'Label' ) );
	objectGroundColorRow.add( objectGroundColor );

	container.add( objectGroundColorRow );

	// distance

	const objectDistanceRow = new UIRow();
	const objectDistance = new UINumber().setRange( 0, Infinity ).onChange( update );

	objectDistanceRow.add( new UIText( strings.getKey( 'sidebar/object/distance' ) ).setClass( 'Label' ) );
	objectDistanceRow.add( objectDistance );

	container.add( objectDistanceRow );

	// angle

	const objectAngleRow = new UIRow();
	const objectAngle = new UINumber().setPrecision( 3 ).setRange( 0, Math.PI / 2 ).onChange( update );

	objectAngleRow.add( new UIText( strings.getKey( 'sidebar/object/angle' ) ).setClass( 'Label' ) );
	objectAngleRow.add( objectAngle );

	container.add( objectAngleRow );

	// penumbra

	const objectPenumbraRow = new UIRow();
	const objectPenumbra = new UINumber().setRange( 0, 1 ).onChange( update );

	objectPenumbraRow.add( new UIText( strings.getKey( 'sidebar/object/penumbra' ) ).setClass( 'Label' ) );
	objectPenumbraRow.add( objectPenumbra );

	container.add( objectPenumbraRow );

	// decay

	const objectDecayRow = new UIRow();
	const objectDecay = new UINumber().setRange( 0, Infinity ).onChange( update );

	objectDecayRow.add( new UIText( strings.getKey( 'sidebar/object/decay' ) ).setClass( 'Label' ) );
	objectDecayRow.add( objectDecay );

	container.add( objectDecayRow );

	// shadow

	const objectShadowRow = new UIRow();

	objectShadowRow.add( new UIText( strings.getKey( 'sidebar/object/shadow' ) ).setClass( 'Label' ) );

	const objectCastShadow = new UIBoolean( false, strings.getKey( 'sidebar/object/cast' ) ).onChange( update );
	objectShadowRow.add( objectCastShadow );

	const objectReceiveShadow = new UIBoolean( false, strings.getKey( 'sidebar/object/receive' ) ).onChange( update );
	objectShadowRow.add( objectReceiveShadow );

	container.add( objectShadowRow );

	// shadow intensity

	const objectShadowIntensityRow = new UIRow();

	objectShadowIntensityRow.add( new UIText( strings.getKey( 'sidebar/object/shadowIntensity' ) ).setClass( 'Label' ) );

	const objectShadowIntensity = new UINumber( 0 ).setRange( 0, 1 ).onChange( update );
	objectShadowIntensityRow.add( objectShadowIntensity );

	container.add( objectShadowIntensityRow );

	// shadow bias

	const objectShadowBiasRow = new UIRow();

	objectShadowBiasRow.add( new UIText( strings.getKey( 'sidebar/object/shadowBias' ) ).setClass( 'Label' ) );

	const objectShadowBias = new UINumber( 0 ).setPrecision( 5 ).setStep( 0.0001 ).setNudge( 0.00001 ).onChange( update );
	objectShadowBiasRow.add( objectShadowBias );

	container.add( objectShadowBiasRow );

	// shadow normal offset

	const objectShadowNormalBiasRow = new UIRow();

	objectShadowNormalBiasRow.add( new UIText( strings.getKey( 'sidebar/object/shadowNormalBias' ) ).setClass( 'Label' ) );

	const objectShadowNormalBias = new UINumber( 0 ).onChange( update );
	objectShadowNormalBiasRow.add( objectShadowNormalBias );

	container.add( objectShadowNormalBiasRow );

	// shadow radius

	const objectShadowRadiusRow = new UIRow();

	objectShadowRadiusRow.add( new UIText( strings.getKey( 'sidebar/object/shadowRadius' ) ).setClass( 'Label' ) );

	const objectShadowRadius = new UINumber( 1 ).onChange( update );
	objectShadowRadiusRow.add( objectShadowRadius );

	container.add( objectShadowRadiusRow );

	// visible

	const objectVisibleRow = new UIRow();
	const objectVisible = new UICheckbox().onChange( update );

	objectVisibleRow.add( new UIText( strings.getKey( 'sidebar/object/visible' ) ).setClass( 'Label' ) );
	objectVisibleRow.add( objectVisible );

	container.add( objectVisibleRow );

	// frustumCulled

	const objectFrustumCulledRow = new UIRow();
	const objectFrustumCulled = new UICheckbox().onChange( update );

	objectFrustumCulledRow.add( new UIText( strings.getKey( 'sidebar/object/frustumcull' ) ).setClass( 'Label' ) );
	objectFrustumCulledRow.add( objectFrustumCulled );

	container.add( objectFrustumCulledRow );

	// renderOrder

	const objectRenderOrderRow = new UIRow();
	const objectRenderOrder = new UIInteger().setWidth( '50px' ).onChange( update );

	objectRenderOrderRow.add( new UIText( strings.getKey( 'sidebar/object/renderorder' ) ).setClass( 'Label' ) );
	objectRenderOrderRow.add( objectRenderOrder );

	container.add( objectRenderOrderRow );

	// user data

	const objectUserDataRow = new UIRow();
	const objectUserData = new UITextArea().setWidth( '150px' ).setHeight( '40px' ).setFontSize( '12px' ).onChange( update );
	objectUserData.onKeyUp( function () {

		try {

			JSON.parse( objectUserData.getValue() );

			objectUserData.dom.classList.add( 'success' );
			objectUserData.dom.classList.remove( 'fail' );

		} catch ( error ) {

			objectUserData.dom.classList.remove( 'success' );
			objectUserData.dom.classList.add( 'fail' );

		}

	} );

	objectUserDataRow.add( new UIText( strings.getKey( 'sidebar/object/userdata' ) ).setClass( 'Label' ) );
	objectUserDataRow.add( objectUserData );

	container.add( objectUserDataRow );

	// Export JSON

	const exportJson = new UIButton( strings.getKey( 'sidebar/object/export' ) );
	exportJson.setMarginLeft( '120px' );
	exportJson.onClick( function () {

		const object = editor.selected;

		let output = object.toJSON();

		try {

			output = JSON.stringify( output, null, '\t' );
			output = output.replace( /[\n\t]+([\d\.e\-\[\]]+)/g, '$1' );

		} catch ( e ) {

			output = JSON.stringify( output );

		}


		editor.utils.save( new Blob( [ output ] ), `${ objectName.getValue() || 'object' }.json` );

	} );
	container.add( exportJson );

	// Animations

	container.add( new SidebarObjectAnimation( editor ) );

	//

	function update() {

		const object = editor.selected;

		if ( object !== null ) {

			const newPosition = new THREE.Vector3( objectPositionX.getValue(), objectPositionY.getValue(), objectPositionZ.getValue() );
			if ( object.position.distanceTo( newPosition ) >= 0.01 ) {

				editor.execute( new SetPositionCommand( editor, object, newPosition ) );

			}

			const newRotation = new THREE.Euler( objectRotationX.getValue() * THREE.MathUtils.DEG2RAD, objectRotationY.getValue() * THREE.MathUtils.DEG2RAD, objectRotationZ.getValue() * THREE.MathUtils.DEG2RAD );
			if ( new THREE.Vector3().setFromEuler( object.rotation ).distanceTo( new THREE.Vector3().setFromEuler( newRotation ) ) >= 0.01 ) {

				editor.execute( new SetRotationCommand( editor, object, newRotation ) );

			}

			const newScale = new THREE.Vector3( objectScaleX.getValue(), objectScaleY.getValue(), objectScaleZ.getValue() );
			if ( object.scale.distanceTo( newScale ) >= 0.01 ) {

				editor.execute( new SetScaleCommand( editor, object, newScale ) );

			}

			if ( object.fov !== undefined && Math.abs( object.fov - objectFov.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'fov', objectFov.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.left !== undefined && Math.abs( object.left - objectLeft.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'left', objectLeft.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.right !== undefined && Math.abs( object.right - objectRight.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'right', objectRight.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.top !== undefined && Math.abs( object.top - objectTop.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'top', objectTop.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.bottom !== undefined && Math.abs( object.bottom - objectBottom.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'bottom', objectBottom.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.near !== undefined && Math.abs( object.near - objectNear.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'near', objectNear.getValue() ) );
				if ( object.isOrthographicCamera ) {

					object.updateProjectionMatrix();

				}

			}

			if ( object.far !== undefined && Math.abs( object.far - objectFar.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'far', objectFar.getValue() ) );
				if ( object.isOrthographicCamera ) {

					object.updateProjectionMatrix();

				}

			}

			if ( object.intensity !== undefined && Math.abs( object.intensity - objectIntensity.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'intensity', objectIntensity.getValue() ) );

			}

			if ( object.color !== undefined && object.color.getHex() !== objectColor.getHexValue() ) {

				editor.execute( new SetColorCommand( editor, object, 'color', objectColor.getHexValue() ) );

			}

			if ( object.groundColor !== undefined && object.groundColor.getHex() !== objectGroundColor.getHexValue() ) {

				editor.execute( new SetColorCommand( editor, object, 'groundColor', objectGroundColor.getHexValue() ) );

			}

			if ( object.distance !== undefined && Math.abs( object.distance - objectDistance.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'distance', objectDistance.getValue() ) );

			}

			if ( object.angle !== undefined && Math.abs( object.angle - objectAngle.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'angle', objectAngle.getValue() ) );

			}

			if ( object.penumbra !== undefined && Math.abs( object.penumbra - objectPenumbra.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'penumbra', objectPenumbra.getValue() ) );

			}

			if ( object.decay !== undefined && Math.abs( object.decay - objectDecay.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'decay', objectDecay.getValue() ) );

			}

			if ( object.visible !== objectVisible.getValue() ) {

				editor.execute( new SetValueCommand( editor, object, 'visible', objectVisible.getValue() ) );

			}

			if ( object.frustumCulled !== objectFrustumCulled.getValue() ) {

				editor.execute( new SetValueCommand( editor, object, 'frustumCulled', objectFrustumCulled.getValue() ) );

			}

			if ( object.renderOrder !== objectRenderOrder.getValue() ) {

				editor.execute( new SetValueCommand( editor, object, 'renderOrder', objectRenderOrder.getValue() ) );

			}

			if ( object.castShadow !== undefined && object.castShadow !== objectCastShadow.getValue() ) {

				editor.execute( new SetValueCommand( editor, object, 'castShadow', objectCastShadow.getValue() ) );

			}

			if ( object.receiveShadow !== objectReceiveShadow.getValue() ) {

				if ( object.material !== undefined ) object.material.needsUpdate = true;
				editor.execute( new SetValueCommand( editor, object, 'receiveShadow', objectReceiveShadow.getValue() ) );

			}

			if ( object.shadow !== undefined ) {

				if ( object.shadow.intensity !== objectShadowIntensity.getValue() ) {

					editor.execute( new SetShadowValueCommand( editor, object, 'intensity', objectShadowIntensity.getValue() ) );

				}

				if ( object.shadow.bias !== objectShadowBias.getValue() ) {

					editor.execute( new SetShadowValueCommand( editor, object, 'bias', objectShadowBias.getValue() ) );

				}

				if ( object.shadow.normalBias !== objectShadowNormalBias.getValue() ) {

					editor.execute( new SetShadowValueCommand( editor, object, 'normalBias', objectShadowNormalBias.getValue() ) );

				}

				if ( object.shadow.radius !== objectShadowRadius.getValue() ) {

					editor.execute( new SetShadowValueCommand( editor, object, 'radius', objectShadowRadius.getValue() ) );

				}

			}

			try {

				const userData = JSON.parse( objectUserData.getValue() );
				if ( JSON.stringify( object.userData ) != JSON.stringify( userData ) ) {

					editor.execute( new SetValueCommand( editor, object, 'userData', userData ) );

				}

			} catch ( exception ) {

				console.warn( exception );

			}

		}

	}

	function updateRows( object ) {

		const properties = {
			'fov': objectFovRow,
			'left': objectLeftRow,
			'right': objectRightRow,
			'top': objectTopRow,
			'bottom': objectBottomRow,
			'near': objectNearRow,
			'far': objectFarRow,
			'intensity': objectIntensityRow,
			'color': objectColorRow,
			'groundColor': objectGroundColorRow,
			'distance': objectDistanceRow,
			'angle': objectAngleRow,
			'penumbra': objectPenumbraRow,
			'decay': objectDecayRow,
			'castShadow': objectShadowRow,
			'receiveShadow': objectReceiveShadow,
			'shadow': [ objectShadowIntensityRow, objectShadowBiasRow, objectShadowNormalBiasRow, objectShadowRadiusRow ]
		};

		for ( const property in properties ) {

			const uiElement = properties[ property ];

			if ( Array.isArray( uiElement ) === true ) {

				for ( let i = 0; i < uiElement.length; i ++ ) {

					uiElement[ i ].setDisplay( object[ property ] !== undefined ? '' : 'none' );

				}

			} else {

				uiElement.setDisplay( object[ property ] !== undefined ? '' : 'none' );

			}

		}

		//

		if ( object.isLight ) {

			objectReceiveShadow.setDisplay( 'none' );

		}

		if ( object.isAmbientLight || object.isHemisphereLight ) {

			objectShadowRow.setDisplay( 'none' );

		}

	}

	function updateTransformRows( object ) {

		if ( object.isLight ) {

			objectRotationRow.setDisplay( 'none' );
			objectScaleRow.setDisplay( 'none' );

		} else {

			objectRotationRow.setDisplay( '' );
			objectScaleRow.setDisplay( '' );

		}

	}

	// events

	signals.objectSelected.add( function ( object ) {

		if ( object !== null ) {

			container.setDisplay( 'block' );

			updateRows( object );
			updateUI( object );

		} else {

			container.setDisplay( 'none' );

		}

	} );

	signals.objectChanged.add( function ( object ) {

		if ( object !== editor.selected ) return;

		updateUI( object );

	} );

	signals.refreshSidebarObject3D.add( function ( object ) {

		if ( object !== editor.selected ) return;

		updateUI( object );

	} );

	function updateUI( object ) {

		objectType.setValue( object.type );

		objectUUID.setValue( object.uuid );
		objectName.setValue( object.name );

		objectPositionX.setValue( object.position.x );
		objectPositionY.setValue( object.position.y );
		objectPositionZ.setValue( object.position.z );

		objectRotationX.setValue( object.rotation.x * THREE.MathUtils.RAD2DEG );
		objectRotationY.setValue( object.rotation.y * THREE.MathUtils.RAD2DEG );
		objectRotationZ.setValue( object.rotation.z * THREE.MathUtils.RAD2DEG );

		objectScaleX.setValue( object.scale.x );
		objectScaleY.setValue( object.scale.y );
		objectScaleZ.setValue( object.scale.z );

		if ( object.fov !== undefined ) {

			objectFov.setValue( object.fov );

		}

		if ( object.left !== undefined ) {

			objectLeft.setValue( object.left );

		}

		if ( object.right !== undefined ) {

			objectRight.setValue( object.right );

		}

		if ( object.top !== undefined ) {

			objectTop.setValue( object.top );

		}

		if ( object.bottom !== undefined ) {

			objectBottom.setValue( object.bottom );

		}

		if ( object.near !== undefined ) {

			objectNear.setValue( object.near );

		}

		if ( object.far !== undefined ) {

			objectFar.setValue( object.far );

		}

		if ( object.intensity !== undefined ) {

			objectIntensity.setValue( object.intensity );

		}

		if ( object.color !== undefined ) {

			objectColor.setHexValue( object.color.getHexString() );

		}

		if ( object.groundColor !== undefined ) {

			objectGroundColor.setHexValue( object.groundColor.getHexString() );

		}

		if ( object.distance !== undefined ) {

			objectDistance.setValue( object.distance );

		}

		if ( object.angle !== undefined ) {

			objectAngle.setValue( object.angle );

		}

		if ( object.penumbra !== undefined ) {

			objectPenumbra.setValue( object.penumbra );

		}

		if ( object.decay !== undefined ) {

			objectDecay.setValue( object.decay );

		}

		if ( object.castShadow !== undefined ) {

			objectCastShadow.setValue( object.castShadow );

		}

		if ( object.receiveShadow !== undefined ) {

			objectReceiveShadow.setValue( object.receiveShadow );

		}

		if ( object.shadow !== undefined ) {

			objectShadowIntensity.setValue( object.shadow.intensity );
			objectShadowBias.setValue( object.shadow.bias );
			objectShadowNormalBias.setValue( object.shadow.normalBias );
			objectShadowRadius.setValue( object.shadow.radius );

		}

		objectVisible.setValue( object.visible );
		objectFrustumCulled.setValue( object.frustumCulled );
		objectRenderOrder.setValue( object.renderOrder );

		try {

			objectUserData.setValue( JSON.stringify( object.userData, null, '  ' ) );

		} catch ( error ) {

			console.log( error );

		}

		objectUserData.setBorderColor( 'transparent' );
		objectUserData.setBackgroundColor( '' );

		updateTransformRows( object );

	}

	return container;

}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `objectPositionX.getValue`
- `objectPositionY.getValue`
- `objectPositionZ.getValue`
- `object.position.distanceTo`
- `editor.execute`
- `objectRotationX.getValue`
- `objectRotationY.getValue`
- `objectRotationZ.getValue`
- `new THREE.Vector3().setFromEuler( object.rotation ).distanceTo`
- `new THREE.Vector3().setFromEuler`
- `objectScaleX.getValue`
- `objectScaleY.getValue`
- `objectScaleZ.getValue`
- `object.scale.distanceTo`
- `Math.abs`
- `objectFov.getValue`
- `object.updateProjectionMatrix`
- `objectLeft.getValue`
- `objectRight.getValue`
- `objectTop.getValue`
- `objectBottom.getValue`
- `objectNear.getValue`
- `objectFar.getValue`
- `objectIntensity.getValue`
- `object.color.getHex`
- `objectColor.getHexValue`
- `object.groundColor.getHex`
- `objectGroundColor.getHexValue`
- `objectDistance.getValue`
- `objectAngle.getValue`
- `objectPenumbra.getValue`
- `objectDecay.getValue`
- `objectVisible.getValue`
- `objectFrustumCulled.getValue`
- `objectRenderOrder.getValue`
- `objectCastShadow.getValue`
- `objectReceiveShadow.getValue`
- `objectShadowIntensity.getValue`
- `objectShadowBias.getValue`
- `objectShadowNormalBias.getValue`
- `objectShadowRadius.getValue`
- `JSON.parse`
- `objectUserData.getValue`
- `JSON.stringify`
- `console.warn`

<details><summary>Code</summary>

```typescript
function update() {

		const object = editor.selected;

		if ( object !== null ) {

			const newPosition = new THREE.Vector3( objectPositionX.getValue(), objectPositionY.getValue(), objectPositionZ.getValue() );
			if ( object.position.distanceTo( newPosition ) >= 0.01 ) {

				editor.execute( new SetPositionCommand( editor, object, newPosition ) );

			}

			const newRotation = new THREE.Euler( objectRotationX.getValue() * THREE.MathUtils.DEG2RAD, objectRotationY.getValue() * THREE.MathUtils.DEG2RAD, objectRotationZ.getValue() * THREE.MathUtils.DEG2RAD );
			if ( new THREE.Vector3().setFromEuler( object.rotation ).distanceTo( new THREE.Vector3().setFromEuler( newRotation ) ) >= 0.01 ) {

				editor.execute( new SetRotationCommand( editor, object, newRotation ) );

			}

			const newScale = new THREE.Vector3( objectScaleX.getValue(), objectScaleY.getValue(), objectScaleZ.getValue() );
			if ( object.scale.distanceTo( newScale ) >= 0.01 ) {

				editor.execute( new SetScaleCommand( editor, object, newScale ) );

			}

			if ( object.fov !== undefined && Math.abs( object.fov - objectFov.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'fov', objectFov.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.left !== undefined && Math.abs( object.left - objectLeft.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'left', objectLeft.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.right !== undefined && Math.abs( object.right - objectRight.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'right', objectRight.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.top !== undefined && Math.abs( object.top - objectTop.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'top', objectTop.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.bottom !== undefined && Math.abs( object.bottom - objectBottom.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'bottom', objectBottom.getValue() ) );
				object.updateProjectionMatrix();

			}

			if ( object.near !== undefined && Math.abs( object.near - objectNear.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'near', objectNear.getValue() ) );
				if ( object.isOrthographicCamera ) {

					object.updateProjectionMatrix();

				}

			}

			if ( object.far !== undefined && Math.abs( object.far - objectFar.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'far', objectFar.getValue() ) );
				if ( object.isOrthographicCamera ) {

					object.updateProjectionMatrix();

				}

			}

			if ( object.intensity !== undefined && Math.abs( object.intensity - objectIntensity.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'intensity', objectIntensity.getValue() ) );

			}

			if ( object.color !== undefined && object.color.getHex() !== objectColor.getHexValue() ) {

				editor.execute( new SetColorCommand( editor, object, 'color', objectColor.getHexValue() ) );

			}

			if ( object.groundColor !== undefined && object.groundColor.getHex() !== objectGroundColor.getHexValue() ) {

				editor.execute( new SetColorCommand( editor, object, 'groundColor', objectGroundColor.getHexValue() ) );

			}

			if ( object.distance !== undefined && Math.abs( object.distance - objectDistance.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'distance', objectDistance.getValue() ) );

			}

			if ( object.angle !== undefined && Math.abs( object.angle - objectAngle.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'angle', objectAngle.getValue() ) );

			}

			if ( object.penumbra !== undefined && Math.abs( object.penumbra - objectPenumbra.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'penumbra', objectPenumbra.getValue() ) );

			}

			if ( object.decay !== undefined && Math.abs( object.decay - objectDecay.getValue() ) >= 0.01 ) {

				editor.execute( new SetValueCommand( editor, object, 'decay', objectDecay.getValue() ) );

			}

			if ( object.visible !== objectVisible.getValue() ) {

				editor.execute( new SetValueCommand( editor, object, 'visible', objectVisible.getValue() ) );

			}

			if ( object.frustumCulled !== objectFrustumCulled.getValue() ) {

				editor.execute( new SetValueCommand( editor, object, 'frustumCulled', objectFrustumCulled.getValue() ) );

			}

			if ( object.renderOrder !== objectRenderOrder.getValue() ) {

				editor.execute( new SetValueCommand( editor, object, 'renderOrder', objectRenderOrder.getValue() ) );

			}

			if ( object.castShadow !== undefined && object.castShadow !== objectCastShadow.getValue() ) {

				editor.execute( new SetValueCommand( editor, object, 'castShadow', objectCastShadow.getValue() ) );

			}

			if ( object.receiveShadow !== objectReceiveShadow.getValue() ) {

				if ( object.material !== undefined ) object.material.needsUpdate = true;
				editor.execute( new SetValueCommand( editor, object, 'receiveShadow', objectReceiveShadow.getValue() ) );

			}

			if ( object.shadow !== undefined ) {

				if ( object.shadow.intensity !== objectShadowIntensity.getValue() ) {

					editor.execute( new SetShadowValueCommand( editor, object, 'intensity', objectShadowIntensity.getValue() ) );

				}

				if ( object.shadow.bias !== objectShadowBias.getValue() ) {

					editor.execute( new SetShadowValueCommand( editor, object, 'bias', objectShadowBias.getValue() ) );

				}

				if ( object.shadow.normalBias !== objectShadowNormalBias.getValue() ) {

					editor.execute( new SetShadowValueCommand( editor, object, 'normalBias', objectShadowNormalBias.getValue() ) );

				}

				if ( object.shadow.radius !== objectShadowRadius.getValue() ) {

					editor.execute( new SetShadowValueCommand( editor, object, 'radius', objectShadowRadius.getValue() ) );

				}

			}

			try {

				const userData = JSON.parse( objectUserData.getValue() );
				if ( JSON.stringify( object.userData ) != JSON.stringify( userData ) ) {

					editor.execute( new SetValueCommand( editor, object, 'userData', userData ) );

				}

			} catch ( exception ) {

				console.warn( exception );

			}

		}

	}
```
</details>

### `updateRows(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `uiElement[ i ].setDisplay`
- `uiElement.setDisplay`
- `objectReceiveShadow.setDisplay`
- `objectShadowRow.setDisplay`

**Internal Comments:**
```
//
```

<details><summary>Code</summary>

```typescript
function updateRows( object ) {

		const properties = {
			'fov': objectFovRow,
			'left': objectLeftRow,
			'right': objectRightRow,
			'top': objectTopRow,
			'bottom': objectBottomRow,
			'near': objectNearRow,
			'far': objectFarRow,
			'intensity': objectIntensityRow,
			'color': objectColorRow,
			'groundColor': objectGroundColorRow,
			'distance': objectDistanceRow,
			'angle': objectAngleRow,
			'penumbra': objectPenumbraRow,
			'decay': objectDecayRow,
			'castShadow': objectShadowRow,
			'receiveShadow': objectReceiveShadow,
			'shadow': [ objectShadowIntensityRow, objectShadowBiasRow, objectShadowNormalBiasRow, objectShadowRadiusRow ]
		};

		for ( const property in properties ) {

			const uiElement = properties[ property ];

			if ( Array.isArray( uiElement ) === true ) {

				for ( let i = 0; i < uiElement.length; i ++ ) {

					uiElement[ i ].setDisplay( object[ property ] !== undefined ? '' : 'none' );

				}

			} else {

				uiElement.setDisplay( object[ property ] !== undefined ? '' : 'none' );

			}

		}

		//

		if ( object.isLight ) {

			objectReceiveShadow.setDisplay( 'none' );

		}

		if ( object.isAmbientLight || object.isHemisphereLight ) {

			objectShadowRow.setDisplay( 'none' );

		}

	}
```
</details>

### `updateTransformRows(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `objectRotationRow.setDisplay`
- `objectScaleRow.setDisplay`

<details><summary>Code</summary>

```typescript
function updateTransformRows( object ) {

		if ( object.isLight ) {

			objectRotationRow.setDisplay( 'none' );
			objectScaleRow.setDisplay( 'none' );

		} else {

			objectRotationRow.setDisplay( '' );
			objectScaleRow.setDisplay( '' );

		}

	}
```
</details>

### `updateUI(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `objectType.setValue`
- `objectUUID.setValue`
- `objectName.setValue`
- `objectPositionX.setValue`
- `objectPositionY.setValue`
- `objectPositionZ.setValue`
- `objectRotationX.setValue`
- `objectRotationY.setValue`
- `objectRotationZ.setValue`
- `objectScaleX.setValue`
- `objectScaleY.setValue`
- `objectScaleZ.setValue`
- `objectFov.setValue`
- `objectLeft.setValue`
- `objectRight.setValue`
- `objectTop.setValue`
- `objectBottom.setValue`
- `objectNear.setValue`
- `objectFar.setValue`
- `objectIntensity.setValue`
- `objectColor.setHexValue`
- `object.color.getHexString`
- `objectGroundColor.setHexValue`
- `object.groundColor.getHexString`
- `objectDistance.setValue`
- `objectAngle.setValue`
- `objectPenumbra.setValue`
- `objectDecay.setValue`
- `objectCastShadow.setValue`
- `objectReceiveShadow.setValue`
- `objectShadowIntensity.setValue`
- `objectShadowBias.setValue`
- `objectShadowNormalBias.setValue`
- `objectShadowRadius.setValue`
- `objectVisible.setValue`
- `objectFrustumCulled.setValue`
- `objectRenderOrder.setValue`
- `objectUserData.setValue`
- `JSON.stringify`
- `console.log`
- `objectUserData.setBorderColor`
- `objectUserData.setBackgroundColor`
- `updateTransformRows`

<details><summary>Code</summary>

```typescript
function updateUI( object ) {

		objectType.setValue( object.type );

		objectUUID.setValue( object.uuid );
		objectName.setValue( object.name );

		objectPositionX.setValue( object.position.x );
		objectPositionY.setValue( object.position.y );
		objectPositionZ.setValue( object.position.z );

		objectRotationX.setValue( object.rotation.x * THREE.MathUtils.RAD2DEG );
		objectRotationY.setValue( object.rotation.y * THREE.MathUtils.RAD2DEG );
		objectRotationZ.setValue( object.rotation.z * THREE.MathUtils.RAD2DEG );

		objectScaleX.setValue( object.scale.x );
		objectScaleY.setValue( object.scale.y );
		objectScaleZ.setValue( object.scale.z );

		if ( object.fov !== undefined ) {

			objectFov.setValue( object.fov );

		}

		if ( object.left !== undefined ) {

			objectLeft.setValue( object.left );

		}

		if ( object.right !== undefined ) {

			objectRight.setValue( object.right );

		}

		if ( object.top !== undefined ) {

			objectTop.setValue( object.top );

		}

		if ( object.bottom !== undefined ) {

			objectBottom.setValue( object.bottom );

		}

		if ( object.near !== undefined ) {

			objectNear.setValue( object.near );

		}

		if ( object.far !== undefined ) {

			objectFar.setValue( object.far );

		}

		if ( object.intensity !== undefined ) {

			objectIntensity.setValue( object.intensity );

		}

		if ( object.color !== undefined ) {

			objectColor.setHexValue( object.color.getHexString() );

		}

		if ( object.groundColor !== undefined ) {

			objectGroundColor.setHexValue( object.groundColor.getHexString() );

		}

		if ( object.distance !== undefined ) {

			objectDistance.setValue( object.distance );

		}

		if ( object.angle !== undefined ) {

			objectAngle.setValue( object.angle );

		}

		if ( object.penumbra !== undefined ) {

			objectPenumbra.setValue( object.penumbra );

		}

		if ( object.decay !== undefined ) {

			objectDecay.setValue( object.decay );

		}

		if ( object.castShadow !== undefined ) {

			objectCastShadow.setValue( object.castShadow );

		}

		if ( object.receiveShadow !== undefined ) {

			objectReceiveShadow.setValue( object.receiveShadow );

		}

		if ( object.shadow !== undefined ) {

			objectShadowIntensity.setValue( object.shadow.intensity );
			objectShadowBias.setValue( object.shadow.bias );
			objectShadowNormalBias.setValue( object.shadow.normalBias );
			objectShadowRadius.setValue( object.shadow.radius );

		}

		objectVisible.setValue( object.visible );
		objectFrustumCulled.setValue( object.frustumCulled );
		objectRenderOrder.setValue( object.renderOrder );

		try {

			objectUserData.setValue( JSON.stringify( object.userData, null, '  ' ) );

		} catch ( error ) {

			console.log( error );

		}

		objectUserData.setBorderColor( 'transparent' );
		objectUserData.setBackgroundColor( '' );

		updateTransformRows( object );

	}
```
</details>


---