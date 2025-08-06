[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Viewport.Info.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Viewport.Info.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIBreak` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `objectsUnitText` | `UIText` | let/var | `new UIText( strings.getKey( 'viewport/info/objects' ) )` | ✗ |
| `verticesUnitText` | `UIText` | let/var | `new UIText( strings.getKey( 'viewport/info/vertices' ) )` | ✗ |
| `trianglesUnitText` | `UIText` | let/var | `new UIText( strings.getKey( 'viewport/info/triangles' ) )` | ✗ |
| `pluralRules` | `PluralRules` | let/var | `new Intl.PluralRules( editor.config.getKey( 'language' ) )` | ✗ |
| `scene` | `any` | let/var | `editor.scene` | ✗ |
| `objects` | `number` | let/var | `0` | ✗ |
| `vertices` | `number` | let/var | `0` | ✗ |
| `triangles` | `number` | let/var | `0` | ✗ |
| `object` | `any` | let/var | `scene.children[ i ]` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `positionAttribute` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `pluralRules` | `PluralRules` | let/var | `new Intl.PluralRules( editor.config.getKey( 'language' ) )` | ✗ |
| `objectsStringKey` | `"viewport/info/objects" \| "viewport/...` | let/var | `( pluralRules.select( objects ) === 'one' ) ? 'viewport/info/object' : 'viewp...` | ✗ |
| `verticesStringKey` | `"viewport/info/vertices" \| "viewport...` | let/var | `( pluralRules.select( vertices ) === 'one' ) ? 'viewport/info/vertex' : 'view...` | ✗ |
| `trianglesStringKey` | `"viewport/info/triangles" \| "viewpor...` | let/var | `( pluralRules.select( triangles ) === 'one' ) ? 'viewport/info/triangle' : 'v...` | ✗ |
| `samplesStringKey` | `"viewport/info/sample" \| "viewport/i...` | let/var | `( pluralRules.select( samples ) === 'one' ) ? 'viewport/info/sample' : 'viewp...` | ✗ |
| `isRealisticShading` | `boolean` | let/var | `( editor.viewportShading === 'realistic' )` | ✗ |


---

## Functions

### `ViewportInfo(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setId`
- `container.setPosition`
- `container.setLeft`
- `container.setBottom`
- `container.setFontSize`
- `container.setColor`
- `container.setTextTransform`
- `new UIText( '0' ).setTextAlign( 'right' ).setWidth( '60px' ).setMarginRight`
- `new UIText( '0' ).setTextAlign( 'right' ).setWidth( '60px' ).setMarginRight( '6px' ).setHidden`
- `strings.getKey`
- `new UIText( strings.getKey( 'viewport/info/samples' ) ).setHidden`
- `container.add`
- `signals.objectAdded.add`
- `signals.objectRemoved.add`
- `signals.objectChanged.add`
- `signals.geometryChanged.add`
- `signals.sceneRendered.add`
- `editor.config.getKey`
- `object.traverseVisible`
- `objectsText.setValue`
- `editor.utils.formatNumber`
- `verticesText.setValue`
- `trianglesText.setValue`
- `pluralRules.select`
- `objectsUnitText.setValue`
- `verticesUnitText.setValue`
- `trianglesUnitText.setValue`
- `frametimeText.setValue`
- `Number( frametime ).toFixed`
- `editor.signals.pathTracerUpdated.add`
- `Math.floor`
- `samplesText.setValue`
- `samplesUnitText.setValue`
- `editor.signals.viewportShadingChanged.add`
- `samplesText.setHidden`
- `samplesUnitText.setHidden`

**Internal Comments:**
```
// (x9)
// update counts only if vertex data are defined
```

<details><summary>Code</summary>

```typescript
function ViewportInfo( editor ) {

	const signals = editor.signals;
	const strings = editor.strings;

	const container = new UIPanel();
	container.setId( 'info' );
	container.setPosition( 'absolute' );
	container.setLeft( '10px' );
	container.setBottom( '20px' );
	container.setFontSize( '12px' );
	container.setColor( '#fff' );
	container.setTextTransform( 'lowercase' );

	const objectsText = new UIText( '0' ).setTextAlign( 'right' ).setWidth( '60px' ).setMarginRight( '6px' );
	const verticesText = new UIText( '0' ).setTextAlign( 'right' ).setWidth( '60px' ).setMarginRight( '6px' );
	const trianglesText = new UIText( '0' ).setTextAlign( 'right' ).setWidth( '60px' ).setMarginRight( '6px' );
	const frametimeText = new UIText( '0' ).setTextAlign( 'right' ).setWidth( '60px' ).setMarginRight( '6px' );
	const samplesText = new UIText( '0' ).setTextAlign( 'right' ).setWidth( '60px' ).setMarginRight( '6px' ).setHidden( true );

	const objectsUnitText = new UIText( strings.getKey( 'viewport/info/objects' ) );
	const verticesUnitText = new UIText( strings.getKey( 'viewport/info/vertices' ) );
	const trianglesUnitText = new UIText( strings.getKey( 'viewport/info/triangles' ) );
	const samplesUnitText = new UIText( strings.getKey( 'viewport/info/samples' ) ).setHidden( true );

	container.add( objectsText, objectsUnitText, new UIBreak() );
	container.add( verticesText, verticesUnitText, new UIBreak() );
	container.add( trianglesText, trianglesUnitText, new UIBreak() );
	container.add( frametimeText, new UIText( strings.getKey( 'viewport/info/rendertime' ) ), new UIBreak() );
	container.add( samplesText, samplesUnitText, new UIBreak() );

	signals.objectAdded.add( update );
	signals.objectRemoved.add( update );
	signals.objectChanged.add( update );
	signals.geometryChanged.add( update );
	signals.sceneRendered.add( updateFrametime );

	//

	const pluralRules = new Intl.PluralRules( editor.config.getKey( 'language' ) );

	//

	function update() {

		const scene = editor.scene;

		let objects = 0, vertices = 0, triangles = 0;

		for ( let i = 0, l = scene.children.length; i < l; i ++ ) {

			const object = scene.children[ i ];

			object.traverseVisible( function ( object ) {

				objects ++;

				if ( object.isMesh || object.isPoints ) {

					const geometry = object.geometry;
					const positionAttribute = geometry.attributes.position;

					// update counts only if vertex data are defined

					if ( positionAttribute !== undefined && positionAttribute !== null ) {

						vertices += positionAttribute.count;

					}

					if ( object.isMesh ) {

						if ( geometry.index !== null ) {

							triangles += geometry.index.count / 3;

						} else if ( positionAttribute !== undefined && positionAttribute !== null ) {

							triangles += positionAttribute.count / 3;

						}

					}

				}

			} );

		}

		objectsText.setValue( editor.utils.formatNumber( objects ) );
		verticesText.setValue( editor.utils.formatNumber( vertices ) );
		trianglesText.setValue( editor.utils.formatNumber( triangles ) );

		const pluralRules = new Intl.PluralRules( editor.config.getKey( 'language' ) );

		const objectsStringKey = ( pluralRules.select( objects ) === 'one' ) ? 'viewport/info/object' : 'viewport/info/objects';
		objectsUnitText.setValue( strings.getKey( objectsStringKey ) );

		const verticesStringKey = ( pluralRules.select( vertices ) === 'one' ) ? 'viewport/info/vertex' : 'viewport/info/vertices';
		verticesUnitText.setValue( strings.getKey( verticesStringKey ) );

		const trianglesStringKey = ( pluralRules.select( triangles ) === 'one' ) ? 'viewport/info/triangle' : 'viewport/info/triangles';
		trianglesUnitText.setValue( strings.getKey( trianglesStringKey ) );

	}

	function updateFrametime( frametime ) {

		frametimeText.setValue( Number( frametime ).toFixed( 2 ) );

	}

	//

	editor.signals.pathTracerUpdated.add( function ( samples ) {

		samples = Math.floor( samples );

		samplesText.setValue( samples );

		const samplesStringKey = ( pluralRules.select( samples ) === 'one' ) ? 'viewport/info/sample' : 'viewport/info/samples';
		samplesUnitText.setValue( strings.getKey( samplesStringKey ) );

	} );

	editor.signals.viewportShadingChanged.add( function () {

		const isRealisticShading = ( editor.viewportShading === 'realistic' );

		samplesText.setHidden( ! isRealisticShading );
		samplesUnitText.setHidden( ! isRealisticShading );

		container.setBottom( isRealisticShading ? '32px' : '20px' );

	} );

	return container;

}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `object.traverseVisible`
- `objectsText.setValue`
- `editor.utils.formatNumber`
- `verticesText.setValue`
- `trianglesText.setValue`
- `editor.config.getKey`
- `pluralRules.select`
- `objectsUnitText.setValue`
- `strings.getKey`
- `verticesUnitText.setValue`
- `trianglesUnitText.setValue`

**Internal Comments:**
```
// update counts only if vertex data are defined
```

<details><summary>Code</summary>

```typescript
function update() {

		const scene = editor.scene;

		let objects = 0, vertices = 0, triangles = 0;

		for ( let i = 0, l = scene.children.length; i < l; i ++ ) {

			const object = scene.children[ i ];

			object.traverseVisible( function ( object ) {

				objects ++;

				if ( object.isMesh || object.isPoints ) {

					const geometry = object.geometry;
					const positionAttribute = geometry.attributes.position;

					// update counts only if vertex data are defined

					if ( positionAttribute !== undefined && positionAttribute !== null ) {

						vertices += positionAttribute.count;

					}

					if ( object.isMesh ) {

						if ( geometry.index !== null ) {

							triangles += geometry.index.count / 3;

						} else if ( positionAttribute !== undefined && positionAttribute !== null ) {

							triangles += positionAttribute.count / 3;

						}

					}

				}

			} );

		}

		objectsText.setValue( editor.utils.formatNumber( objects ) );
		verticesText.setValue( editor.utils.formatNumber( vertices ) );
		trianglesText.setValue( editor.utils.formatNumber( triangles ) );

		const pluralRules = new Intl.PluralRules( editor.config.getKey( 'language' ) );

		const objectsStringKey = ( pluralRules.select( objects ) === 'one' ) ? 'viewport/info/object' : 'viewport/info/objects';
		objectsUnitText.setValue( strings.getKey( objectsStringKey ) );

		const verticesStringKey = ( pluralRules.select( vertices ) === 'one' ) ? 'viewport/info/vertex' : 'viewport/info/vertices';
		verticesUnitText.setValue( strings.getKey( verticesStringKey ) );

		const trianglesStringKey = ( pluralRules.select( triangles ) === 'one' ) ? 'viewport/info/triangle' : 'viewport/info/triangles';
		trianglesUnitText.setValue( strings.getKey( trianglesStringKey ) );

	}
```
</details>

### `updateFrametime(frametime: any): void`

**Parameters:**

- **`frametime`** `any`

**Returns:** `void`

**Calls:**

- `frametimeText.setValue`
- `Number( frametime ).toFixed`

<details><summary>Code</summary>

```typescript
function updateFrametime( frametime ) {

		frametimeText.setValue( Number( frametime ).toFixed( 2 ) );

	}
```
</details>


---