[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Material.MapProperty.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Material.MapProperty.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UICheckbox` | `./libs/ui.js` |
| `UIDiv` | `./libs/ui.js` |
| `UINumber` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UITexture` | `./libs/ui.three.js` |
| `SetMaterialMapCommand` | `./commands/SetMaterialMapCommand.js` |
| `SetMaterialValueCommand` | `./commands/SetMaterialValueCommand.js` |
| `SetMaterialRangeCommand` | `./commands/SetMaterialRangeCommand.js` |
| `SetMaterialVectorCommand` | `./commands/SetMaterialVectorCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `colorMaps` | `string[]` | let/var | `[ 'map', 'emissiveMap', 'sheenColorMap', 'specularColorMap', 'envMap' ]` | ✗ |
| `intensity` | `any` | let/var | `*not shown*` | ✗ |
| `scale` | `any` | let/var | `*not shown*` | ✗ |
| `scaleX` | `any` | let/var | `*not shown*` | ✗ |
| `scaleY` | `any` | let/var | `*not shown*` | ✗ |
| `rangeMin` | `any` | let/var | `*not shown*` | ✗ |
| `rangeMax` | `any` | let/var | `*not shown*` | ✗ |
| `object` | `any` | let/var | `null` | ✗ |
| `materialSlot` | `any` | let/var | `null` | ✗ |
| `material` | `any` | let/var | `null` | ✗ |
| `newMap` | `any` | let/var | `enabled.getValue() ? map.getValue() : null` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `value` | `any[]` | let/var | `[ scaleX.getValue(), scaleY.getValue() ]` | ✗ |
| `value` | `any[]` | let/var | `[ rangeMin.getValue(), rangeMax.getValue() ]` | ✗ |


---

## Functions

### `SidebarMaterialMapProperty(editor: any, property: any, name: any): UIRow`

**Parameters:**

- **`editor`** `any`
- **`property`** `any`
- **`name`** `any`

**Returns:** `UIRow`

**Calls:**

- `container.add`
- `new UIText( name ).setClass`
- `new UICheckbox( false ).setMarginRight( '8px' ).onChange`
- `new UITexture( editor ).onChange`
- `property.replace`
- `new UINumber( 1 ).setWidth( '30px' ).setRange( 0, 1 ).onChange`
- `new UINumber().setWidth( '30px' ).onChange`
- `new UIDiv().setMarginLeft`
- `new UIRow().setMarginBottom( '0px' ).setStyle`
- `range.add`
- `rangeMinRow.add`
- `new UIText( 'min:' ).setWidth`
- `new UINumber().setWidth( '40px' ).onChange`
- `new UIRow().setMarginBottom( '6px' ).setStyle`
- `rangeMaxRow.add`
- `new UIText( 'max:' ).setWidth`
- `rangeMin.setPrecision( 0 ).setRange( 0, Infinity ).setNudge( 1 ).setStep( 10 ).setUnit`
- `rangeMax.setPrecision( 0 ).setRange( 0, Infinity ).setNudge( 1 ).setStep( 10 ).setUnit`
- `enabled.getValue`
- `map.getValue`
- `geometry.hasAttribute`
- `console.warn`
- `editor.execute`
- `colorMaps.includes`
- `enabled.setDisabled`
- `onChange`
- `intensity.getValue`
- `scale.getValue`
- `scaleX.getValue`
- `scaleY.getValue`
- `rangeMin.getValue`
- `rangeMax.getValue`
- `editor.getObjectMaterial`
- `map.setValue`
- `enabled.setValue`
- `intensity.setValue`
- `scale.setValue`
- `scaleX.setValue`
- `scaleY.setValue`
- `rangeMin.setValue`
- `rangeMax.setValue`
- `container.setDisplay`
- `signals.objectSelected.add`
- `update`
- `signals.materialChanged.add`

**Internal Comments:**
```
// Additional settings for iridescenceThicknessMap (x12)
// Please add conditional if more maps are having a range property (x12)
// (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarMaterialMapProperty( editor, property, name ) {

	const signals = editor.signals;

	const container = new UIRow();
	container.add( new UIText( name ).setClass( 'Label' ) );

	const enabled = new UICheckbox( false ).setMarginRight( '8px' ).onChange( onChange );
	container.add( enabled );

	const map = new UITexture( editor ).onChange( onMapChange );
	container.add( map );

	const mapType = property.replace( 'Map', '' );

	const colorMaps = [ 'map', 'emissiveMap', 'sheenColorMap', 'specularColorMap', 'envMap' ];

	let intensity;

	if ( property === 'aoMap' ) {

		intensity = new UINumber( 1 ).setWidth( '30px' ).setRange( 0, 1 ).onChange( onIntensityChange );
		container.add( intensity );

	}

	let scale;

	if ( property === 'bumpMap' || property === 'displacementMap' ) {

		scale = new UINumber().setWidth( '30px' ).onChange( onScaleChange );
		container.add( scale );

	}

	let scaleX, scaleY;

	if ( property === 'normalMap' || property === 'clearcoatNormalMap' ) {

		scaleX = new UINumber().setWidth( '30px' ).onChange( onScaleXYChange );
		container.add( scaleX );

		scaleY = new UINumber().setWidth( '30px' ).onChange( onScaleXYChange );
		container.add( scaleY );

	}

	let rangeMin, rangeMax;

	if ( property === 'iridescenceThicknessMap' ) {

		const range = new UIDiv().setMarginLeft( '3px' );
		container.add( range );

		const rangeMinRow = new UIRow().setMarginBottom( '0px' ).setStyle( 'min-height', '0px' );
		range.add( rangeMinRow );

		rangeMinRow.add( new UIText( 'min:' ).setWidth( '35px' ) );

		rangeMin = new UINumber().setWidth( '40px' ).onChange( onRangeChange );
		rangeMinRow.add( rangeMin );

		const rangeMaxRow = new UIRow().setMarginBottom( '6px' ).setStyle( 'min-height', '0px' );
		range.add( rangeMaxRow );

		rangeMaxRow.add( new UIText( 'max:' ).setWidth( '35px' ) );

		rangeMax = new UINumber().setWidth( '40px' ).onChange( onRangeChange );
		rangeMaxRow.add( rangeMax );

		// Additional settings for iridescenceThicknessMap
		// Please add conditional if more maps are having a range property
		rangeMin.setPrecision( 0 ).setRange( 0, Infinity ).setNudge( 1 ).setStep( 10 ).setUnit( 'nm' );
		rangeMax.setPrecision( 0 ).setRange( 0, Infinity ).setNudge( 1 ).setStep( 10 ).setUnit( 'nm' );

	}

	let object = null;
	let materialSlot = null;
	let material = null;

	function onChange() {

		const newMap = enabled.getValue() ? map.getValue() : null;

		if ( material[ property ] !== newMap ) {

			if ( newMap !== null ) {

				const geometry = object.geometry;

				if ( geometry.hasAttribute( 'uv' ) === false ) console.warn( 'Geometry doesn\'t have uvs:', geometry );

				if ( property === 'envMap' ) newMap.mapping = THREE.EquirectangularReflectionMapping;

			}

			editor.execute( new SetMaterialMapCommand( editor, object, property, newMap, materialSlot ) );

		}

	}

	function onMapChange( texture ) {

		if ( texture !== null ) {

			if ( colorMaps.includes( property ) && texture.isDataTexture !== true && texture.colorSpace !== THREE.SRGBColorSpace ) {

				texture.colorSpace = THREE.SRGBColorSpace;
				material.needsUpdate = true;

			}

		}

		enabled.setDisabled( false );

		onChange();

	}

	function onIntensityChange() {

		if ( material[ `${ property }Intensity` ] !== intensity.getValue() ) {

			editor.execute( new SetMaterialValueCommand( editor, object, `${ property }Intensity`, intensity.getValue(), materialSlot ) );

		}

	}

	function onScaleChange() {

		if ( material[ `${ mapType }Scale` ] !== scale.getValue() ) {

			editor.execute( new SetMaterialValueCommand( editor, object, `${ mapType }Scale`, scale.getValue(), materialSlot ) );

		}

	}

	function onScaleXYChange() {

		const value = [ scaleX.getValue(), scaleY.getValue() ];

		if ( material[ `${ mapType }Scale` ].x !== value[ 0 ] || material[ `${ mapType }Scale` ].y !== value[ 1 ] ) {

			editor.execute( new SetMaterialVectorCommand( editor, object, `${ mapType }Scale`, value, materialSlot ) );

		}

	}

	function onRangeChange() {

		const value = [ rangeMin.getValue(), rangeMax.getValue() ];

		if ( material[ `${ mapType }Range` ][ 0 ] !== value[ 0 ] || material[ `${ mapType }Range` ][ 1 ] !== value[ 1 ] ) {

			editor.execute( new SetMaterialRangeCommand( editor, object, `${ mapType }Range`, value[ 0 ], value[ 1 ], materialSlot ) );

		}

	}

	function update( currentObject, currentMaterialSlot = 0 ) {

		object = currentObject;
		materialSlot = currentMaterialSlot;

		if ( object === null ) return;
		if ( object.material === undefined ) return;

		material = editor.getObjectMaterial( object, materialSlot );

		if ( property in material ) {

			if ( material[ property ] !== null ) {

				map.setValue( material[ property ] );

			}

			enabled.setValue( material[ property ] !== null );
			enabled.setDisabled( map.getValue() === null );

			if ( intensity !== undefined ) {

				intensity.setValue( material[ `${ property }Intensity` ] );

			}

			if ( scale !== undefined ) {

				scale.setValue( material[ `${ mapType }Scale` ] );

			}

			if ( scaleX !== undefined ) {

				scaleX.setValue( material[ `${ mapType }Scale` ].x );
				scaleY.setValue( material[ `${ mapType }Scale` ].y );

			}

			if ( rangeMin !== undefined ) {

				rangeMin.setValue( material[ `${ mapType }Range` ][ 0 ] );
				rangeMax.setValue( material[ `${ mapType }Range` ][ 1 ] );

			}

			container.setDisplay( '' );

		} else {

			container.setDisplay( 'none' );

		}

	}

	//

	signals.objectSelected.add( function ( selected ) {

		map.setValue( null );

		update( selected );

	} );

	signals.materialChanged.add( update );

	return container;

}
```
</details>

### `onChange(): void`

**Returns:** `void`

**Calls:**

- `enabled.getValue`
- `map.getValue`
- `geometry.hasAttribute`
- `console.warn`
- `editor.execute`

<details><summary>Code</summary>

```typescript
function onChange() {

		const newMap = enabled.getValue() ? map.getValue() : null;

		if ( material[ property ] !== newMap ) {

			if ( newMap !== null ) {

				const geometry = object.geometry;

				if ( geometry.hasAttribute( 'uv' ) === false ) console.warn( 'Geometry doesn\'t have uvs:', geometry );

				if ( property === 'envMap' ) newMap.mapping = THREE.EquirectangularReflectionMapping;

			}

			editor.execute( new SetMaterialMapCommand( editor, object, property, newMap, materialSlot ) );

		}

	}
```
</details>

### `onMapChange(texture: any): void`

**Parameters:**

- **`texture`** `any`

**Returns:** `void`

**Calls:**

- `colorMaps.includes`
- `enabled.setDisabled`
- `onChange`

<details><summary>Code</summary>

```typescript
function onMapChange( texture ) {

		if ( texture !== null ) {

			if ( colorMaps.includes( property ) && texture.isDataTexture !== true && texture.colorSpace !== THREE.SRGBColorSpace ) {

				texture.colorSpace = THREE.SRGBColorSpace;
				material.needsUpdate = true;

			}

		}

		enabled.setDisabled( false );

		onChange();

	}
```
</details>

### `onIntensityChange(): void`

**Returns:** `void`

**Calls:**

- `intensity.getValue`
- `editor.execute`

<details><summary>Code</summary>

```typescript
function onIntensityChange() {

		if ( material[ `${ property }Intensity` ] !== intensity.getValue() ) {

			editor.execute( new SetMaterialValueCommand( editor, object, `${ property }Intensity`, intensity.getValue(), materialSlot ) );

		}

	}
```
</details>

### `onScaleChange(): void`

**Returns:** `void`

**Calls:**

- `scale.getValue`
- `editor.execute`

<details><summary>Code</summary>

```typescript
function onScaleChange() {

		if ( material[ `${ mapType }Scale` ] !== scale.getValue() ) {

			editor.execute( new SetMaterialValueCommand( editor, object, `${ mapType }Scale`, scale.getValue(), materialSlot ) );

		}

	}
```
</details>

### `onScaleXYChange(): void`

**Returns:** `void`

**Calls:**

- `scaleX.getValue`
- `scaleY.getValue`
- `editor.execute`

<details><summary>Code</summary>

```typescript
function onScaleXYChange() {

		const value = [ scaleX.getValue(), scaleY.getValue() ];

		if ( material[ `${ mapType }Scale` ].x !== value[ 0 ] || material[ `${ mapType }Scale` ].y !== value[ 1 ] ) {

			editor.execute( new SetMaterialVectorCommand( editor, object, `${ mapType }Scale`, value, materialSlot ) );

		}

	}
```
</details>

### `onRangeChange(): void`

**Returns:** `void`

**Calls:**

- `rangeMin.getValue`
- `rangeMax.getValue`
- `editor.execute`

<details><summary>Code</summary>

```typescript
function onRangeChange() {

		const value = [ rangeMin.getValue(), rangeMax.getValue() ];

		if ( material[ `${ mapType }Range` ][ 0 ] !== value[ 0 ] || material[ `${ mapType }Range` ][ 1 ] !== value[ 1 ] ) {

			editor.execute( new SetMaterialRangeCommand( editor, object, `${ mapType }Range`, value[ 0 ], value[ 1 ], materialSlot ) );

		}

	}
```
</details>

### `update(currentObject: any, currentMaterialSlot: number): void`

**Parameters:**

- **`currentObject`** `any`
- **`currentMaterialSlot`** `number`

**Returns:** `void`

**Calls:**

- `editor.getObjectMaterial`
- `map.setValue`
- `enabled.setValue`
- `enabled.setDisabled`
- `map.getValue`
- `intensity.setValue`
- `scale.setValue`
- `scaleX.setValue`
- `scaleY.setValue`
- `rangeMin.setValue`
- `rangeMax.setValue`
- `container.setDisplay`

<details><summary>Code</summary>

```typescript
function update( currentObject, currentMaterialSlot = 0 ) {

		object = currentObject;
		materialSlot = currentMaterialSlot;

		if ( object === null ) return;
		if ( object.material === undefined ) return;

		material = editor.getObjectMaterial( object, materialSlot );

		if ( property in material ) {

			if ( material[ property ] !== null ) {

				map.setValue( material[ property ] );

			}

			enabled.setValue( material[ property ] !== null );
			enabled.setDisabled( map.getValue() === null );

			if ( intensity !== undefined ) {

				intensity.setValue( material[ `${ property }Intensity` ] );

			}

			if ( scale !== undefined ) {

				scale.setValue( material[ `${ mapType }Scale` ] );

			}

			if ( scaleX !== undefined ) {

				scaleX.setValue( material[ `${ mapType }Scale` ].x );
				scaleY.setValue( material[ `${ mapType }Scale` ].y );

			}

			if ( rangeMin !== undefined ) {

				rangeMin.setValue( material[ `${ mapType }Range` ][ 0 ] );
				rangeMax.setValue( material[ `${ mapType }Range` ][ 1 ] );

			}

			container.setDisplay( '' );

		} else {

			container.setDisplay( 'none' );

		}

	}
```
</details>


---