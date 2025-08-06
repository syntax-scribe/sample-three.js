[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ui.three.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 28 |
| 🧱 Classes | 6 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 53 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/libs/ui.three.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FullScreenQuad` | `three/addons/postprocessing/Pass.js` |
| `UISpan` | `./ui.js` |
| `UIDiv` | `./ui.js` |
| `UIRow` | `./ui.js` |
| `UIButton` | `./ui.js` |
| `UICheckbox` | `./ui.js` |
| `UIText` | `./ui.js` |
| `UINumber` | `./ui.js` |
| `MoveObjectCommand` | `../commands/MoveObjectCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `cache` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `reader` | `FileReader` | let/var | `new FileReader()` | ✗ |
| `hash` | `string` | let/var | ``${file.lastModified}_${file.size}_${file.name}`` | ✗ |
| `loader` | `any` | let/var | `new RGBELoader()` | ✗ |
| `loader` | `any` | let/var | `new TGALoader()` | ✗ |
| `arrayBuffer` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `ktx2Loader` | `any` | let/var | `new KTX2Loader()` | ✗ |
| `arrayBuffer` | `string \| ArrayBuffer` | let/var | `event.target.result` | ✗ |
| `exrLoader` | `any` | let/var | `new EXRLoader()` | ✗ |
| `texture` | `any` | let/var | `new THREE.Texture( this )` | ✗ |
| `canvas` | `any` | let/var | `this.dom.children[ 0 ]` | ✗ |
| `image` | `any` | let/var | `texture.image` | ✗ |
| `scale` | `number` | let/var | `canvas.width / image.width` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `changeEvent` | `Event` | let/var | `new Event( 'change', { bubbles: true, cancelable: true } )` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `changeEvent` | `Event` | let/var | `new Event( 'change', { bubbles: true, cancelable: true } )` | ✗ |
| `currentDrag` | `any` | let/var | `*not shown*` | ✗ |
| `area` | `number` | let/var | `event.offsetY / this.clientHeight` | ✗ |
| `scene` | `any` | let/var | `scope.scene` | ✗ |
| `area` | `number` | let/var | `event.offsetY / this.clientHeight` | ✗ |
| `nextObject` | `any` | let/var | `*not shown*` | ✗ |
| `parent` | `any` | let/var | `*not shown*` | ✗ |
| `newParentIsChild` | `boolean` | let/var | `false` | ✗ |
| `editor` | `any` | let/var | `scope.editor` | ✗ |
| `changeEvent` | `Event` | let/var | `new Event( 'change', { bubbles: true, cancelable: true } )` | ✗ |
| `div` | `any` | let/var | `options[ i ]` | ✗ |
| `element` | `any` | let/var | `this.options[ i ]` | ✗ |
| `y` | `number` | let/var | `element.offsetTop - this.dom.offsetTop` | ✗ |
| `bottomY` | `any` | let/var | `y + element.offsetHeight` | ✗ |
| `minScroll` | `number` | let/var | `bottomY - this.dom.offsetHeight` | ✗ |
| `row` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `addPointButton` | `UIButton` | let/var | `new UIButton( '+' )` | ✗ |
| `point` | `any` | let/var | `this.pointsUI[ this.pointsUI.length - 1 ]` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `pointUI` | `any` | let/var | `this.pointsUI[ i ]` | ✗ |
| `point` | `any` | let/var | `points[ i ]` | ✗ |
| `pointRow` | `UIDiv` | let/var | `new UIDiv()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `row` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `addPointButton` | `UIButton` | let/var | `new UIButton( '+' )` | ✗ |
| `point` | `any` | let/var | `this.pointsUI[ this.pointsUI.length - 1 ]` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `pointUI` | `any` | let/var | `this.pointsUI[ i ]` | ✗ |
| `point` | `any` | let/var | `points[ i ]` | ✗ |
| `pointRow` | `UIDiv` | let/var | `new UIDiv()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `renderer` | `any` | let/var | `*not shown*` | ✗ |
| `fsQuad` | `any` | let/var | `*not shown*` | ✗ |
| `image` | `any` | let/var | `texture.image` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `loadFile` | import( 'three/addons/loaders/RGBELoader.js' ), import( 'three/addons/loaders/TGALoader.js' ), import( 'three/addons/loaders/KTX2Loader.js' ), import( 'three/addons/loaders/EXRLoader.js' ) | *none* |


---

## Functions

### `UITexture.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.texture;

	}
```
</details>

### `UITexture.setValue(texture: any): void`

**Parameters:**

- **`texture`** `any`

**Returns:** `void`

**Calls:**

- `canvas.getContext`
- `context.clearRect`
- `renderToCanvas`
- `context.drawImage`

**Internal Comments:**
```
// Seems like context can be null if the canvas is not visible
// Always clear the context before set new texture, because new texture may has transparency (x4)
```

<details><summary>Code</summary>

```typescript
setValue( texture ) {

		const canvas = this.dom.children[ 0 ];
		const context = canvas.getContext( '2d' );

		// Seems like context can be null if the canvas is not visible
		if ( context ) {

			// Always clear the context before set new texture, because new texture may has transparency
			context.clearRect( 0, 0, canvas.width, canvas.height );

		}

		if ( texture !== null ) {

			const image = texture.image;

			if ( image !== undefined && image !== null && image.width > 0 ) {

				canvas.title = texture.sourceFile;
				const scale = canvas.width / image.width;

				if ( texture.isDataTexture || texture.isCompressedTexture ) {

					const canvas2 = renderToCanvas( texture );
					context.drawImage( canvas2, 0, 0, image.width * scale, image.height * scale );

				} else {

					context.drawImage( image, 0, 0, image.width * scale, image.height * scale );

				}

			} else {

				canvas.title = texture.sourceFile + ' (error)';

			}

		} else {

			canvas.title = 'empty';

		}

		this.texture = texture;

	}
```
</details>

### `UITexture.setColorSpace(colorSpace: any): this`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `this`

**Calls:**

- `this.getValue`

<details><summary>Code</summary>

```typescript
setColorSpace( colorSpace ) {

		const texture = this.getValue();

		if ( texture !== null ) {

			texture.colorSpace = colorSpace;

		}

		return this;

	}
```
</details>

### `UITexture.onChange(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
onChange( callback ) {

		this.onChangeCallback = callback;

		return this;

	}
```
</details>

### `loadFile(file: any): Promise<void>`

**Parameters:**

- **`file`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `file.name.split( '.' ).pop().toLowerCase`
- `cache.has`
- `cache.get`
- `scope.setValue`
- `scope.onChangeCallback`
- `reader.addEventListener`
- `complex_call_1721`
- `loader.load`
- `cache.set`
- `reader.readAsDataURL`
- `complex_call_2260`
- `complex_call_2841`
- `URL.createObjectURL`
- `ktx2Loader.setTranscoderPath`
- `editor.signals.rendererDetectKTX2Support.dispatch`
- `ktx2Loader.load`
- `ktx2Loader.dispose`
- `reader.readAsArrayBuffer`
- `complex_call_3737`
- `exrLoader.load`
- `file.type.match`
- `document.createElement`
- `image.addEventListener`
- `form.reset`

**Internal Comments:**
```
// assuming RGBE/Radiance HDR image format (x2)
```

<details><summary>Code</summary>

```typescript
async function loadFile( file ) {

			const extension = file.name.split( '.' ).pop().toLowerCase();
			const reader = new FileReader();

			const hash = `${file.lastModified}_${file.size}_${file.name}`;

			if ( cache.has( hash ) ) {

				const texture = cache.get( hash );

				scope.setValue( texture );

				if ( scope.onChangeCallback ) scope.onChangeCallback( texture );

			} else if ( extension === 'hdr' || extension === 'pic' ) {

				reader.addEventListener( 'load', async function ( event ) {

					// assuming RGBE/Radiance HDR image format

					const { RGBELoader } = await import( 'three/addons/loaders/RGBELoader.js' );

					const loader = new RGBELoader();
					loader.load( event.target.result, function ( hdrTexture ) {

						hdrTexture.sourceFile = file.name;

						cache.set( hash, hdrTexture );

						scope.setValue( hdrTexture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( hdrTexture );

					} );

				} );

				reader.readAsDataURL( file );

			} else if ( extension === 'tga' ) {

				reader.addEventListener( 'load', async function ( event ) {

					const { TGALoader } = await import( 'three/addons/loaders/TGALoader.js' );

					const loader = new TGALoader();
					loader.load( event.target.result, function ( texture ) {

						texture.colorSpace = THREE.SRGBColorSpace;
						texture.sourceFile = file.name;

						cache.set( hash, texture );

						scope.setValue( texture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( texture );


					} );

				}, false );

				reader.readAsDataURL( file );

			} else if ( extension === 'ktx2' ) {

				reader.addEventListener( 'load', async function ( event ) {

					const { KTX2Loader } = await import( 'three/addons/loaders/KTX2Loader.js' );

					const arrayBuffer = event.target.result;
					const blobURL = URL.createObjectURL( new Blob( [ arrayBuffer ] ) );
					const ktx2Loader = new KTX2Loader();
					ktx2Loader.setTranscoderPath( '../../examples/jsm/libs/basis/' );
					editor.signals.rendererDetectKTX2Support.dispatch( ktx2Loader );

					ktx2Loader.load( blobURL, function ( texture ) {

						texture.colorSpace = THREE.SRGBColorSpace;
						texture.sourceFile = file.name;
						texture.needsUpdate = true;

						cache.set( hash, texture );

						scope.setValue( texture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( texture );
						ktx2Loader.dispose();

					} );

				} );

				reader.readAsArrayBuffer( file );

			} else if ( extension === 'exr' ) {

				reader.addEventListener( 'load', async function ( event ) {

					const { EXRLoader } = await import( 'three/addons/loaders/EXRLoader.js' );

					const arrayBuffer = event.target.result;
					const blobURL = URL.createObjectURL( new Blob( [ arrayBuffer ] ) );
					const exrLoader = new EXRLoader();

					exrLoader.load( blobURL, function ( texture ) {

						texture.sourceFile = file.name;
						texture.needsUpdate = true;

						cache.set( hash, texture );

						scope.setValue( texture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( texture );

					} );

				} );

				reader.readAsArrayBuffer( file );

			} else if ( file.type.match( 'image.*' ) ) {

				reader.addEventListener( 'load', function ( event ) {

					const image = document.createElement( 'img' );
					image.addEventListener( 'load', function () {

						const texture = new THREE.Texture( this );
						texture.sourceFile = file.name;
						texture.needsUpdate = true;

						cache.set( hash, texture );

						scope.setValue( texture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( texture );

					}, false );

					image.src = event.target.result;

				}, false );

				reader.readAsDataURL( file );

			}

			form.reset();

		}
```
</details>

### `UIOutliner.selectIndex(index: any): void`

**Parameters:**

- **`index`** `any`

**Returns:** `void`

**Calls:**

- `this.setValue`
- `this.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
selectIndex( index ) {

		if ( index >= 0 && index < this.options.length ) {

			this.setValue( this.options[ index ].value );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			this.dom.dispatchEvent( changeEvent );

		}

	}
```
</details>

### `UIOutliner.setOptions(options: any): this`

**Parameters:**

- **`options`** `any`

**Returns:** `this`

**Calls:**

- `scope.dom.removeChild`
- `scope.setValue`
- `scope.dom.dispatchEvent`
- `event.dataTransfer.setData`
- `scene.getObjectById`
- `moveObject`
- `object.traverse`
- `editor.execute`
- `scope.dom.appendChild`
- `scope.options.push`
- `div.addEventListener`

**Internal Comments:**
```
// Drag (x2)
// end of list (no next object) (x3)
// (x4)
```

<details><summary>Code</summary>

```typescript
setOptions( options ) {

		const scope = this;

		while ( scope.dom.children.length > 0 ) {

			scope.dom.removeChild( scope.dom.firstChild );

		}

		function onClick() {

			scope.setValue( this.value );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			scope.dom.dispatchEvent( changeEvent );

		}

		// Drag

		let currentDrag;

		function onDrag() {

			currentDrag = this;

		}

		function onDragStart( event ) {

			event.dataTransfer.setData( 'text', 'foo' );

		}

		function onDragOver( event ) {

			if ( this === currentDrag ) return;

			const area = event.offsetY / this.clientHeight;

			if ( area < 0.25 ) {

				this.className = 'option dragTop';

			} else if ( area > 0.75 ) {

				this.className = 'option dragBottom';

			} else {

				this.className = 'option drag';

			}

		}

		function onDragLeave() {

			if ( this === currentDrag ) return;

			this.className = 'option';

		}

		function onDrop( event ) {

			if ( this === currentDrag || currentDrag === undefined ) return;

			this.className = 'option';

			const scene = scope.scene;
			const object = scene.getObjectById( currentDrag.value );

			const area = event.offsetY / this.clientHeight;

			if ( area < 0.25 ) {

				const nextObject = scene.getObjectById( this.value );
				moveObject( object, nextObject.parent, nextObject );

			} else if ( area > 0.75 ) {

				let nextObject, parent;

				if ( this.nextSibling !== null ) {

					nextObject = scene.getObjectById( this.nextSibling.value );
					parent = nextObject.parent;

				} else {

					// end of list (no next object)

					nextObject = null;
					parent = scene.getObjectById( this.value ).parent;

				}

				moveObject( object, parent, nextObject );

			} else {

				const parentObject = scene.getObjectById( this.value );
				moveObject( object, parentObject );

			}

		}

		function moveObject( object, newParent, nextObject ) {

			if ( nextObject === null ) nextObject = undefined;

			let newParentIsChild = false;

			object.traverse( function ( child ) {

				if ( child === newParent ) newParentIsChild = true;

			} );

			if ( newParentIsChild ) return;

			const editor = scope.editor;
			editor.execute( new MoveObjectCommand( editor, object, newParent, nextObject ) );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			scope.dom.dispatchEvent( changeEvent );

		}

		//

		scope.options = [];

		for ( let i = 0; i < options.length; i ++ ) {

			const div = options[ i ];
			div.className = 'option';
			scope.dom.appendChild( div );

			scope.options.push( div );

			div.addEventListener( 'click', onClick );

			if ( div.draggable === true ) {

				div.addEventListener( 'drag', onDrag );
				div.addEventListener( 'dragstart', onDragStart ); // Firefox needs this

				div.addEventListener( 'dragover', onDragOver );
				div.addEventListener( 'dragleave', onDragLeave );
				div.addEventListener( 'drop', onDrop );

			}


		}

		return scope;

	}
```
</details>

### `UIOutliner.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.selectedValue;

	}
```
</details>

### `UIOutliner.setValue(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `element.classList.add`
- `element.classList.remove`

**Internal Comments:**
```
// scroll into view (x2)
```

<details><summary>Code</summary>

```typescript
setValue( value ) {

		for ( let i = 0; i < this.options.length; i ++ ) {

			const element = this.options[ i ];

			if ( element.value === value ) {

				element.classList.add( 'active' );

				// scroll into view

				const y = element.offsetTop - this.dom.offsetTop;
				const bottomY = y + element.offsetHeight;
				const minScroll = bottomY - this.dom.offsetHeight;

				if ( this.dom.scrollTop > y ) {

					this.dom.scrollTop = y;

				} else if ( this.dom.scrollTop < minScroll ) {

					this.dom.scrollTop = minScroll;

				}

				this.selectedIndex = i;

			} else {

				element.classList.remove( 'active' );

			}

		}

		this.selectedValue = value;

		return this;

	}
```
</details>

### `onClick(): void`

**Returns:** `void`

**Calls:**

- `scope.setValue`
- `scope.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onClick() {

			scope.setValue( this.value );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			scope.dom.dispatchEvent( changeEvent );

		}
```
</details>

### `onDrag(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function onDrag() {

			currentDrag = this;

		}
```
</details>

### `onDragStart(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.dataTransfer.setData`

<details><summary>Code</summary>

```typescript
function onDragStart( event ) {

			event.dataTransfer.setData( 'text', 'foo' );

		}
```
</details>

### `onDragOver(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function onDragOver( event ) {

			if ( this === currentDrag ) return;

			const area = event.offsetY / this.clientHeight;

			if ( area < 0.25 ) {

				this.className = 'option dragTop';

			} else if ( area > 0.75 ) {

				this.className = 'option dragBottom';

			} else {

				this.className = 'option drag';

			}

		}
```
</details>

### `onDragLeave(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function onDragLeave() {

			if ( this === currentDrag ) return;

			this.className = 'option';

		}
```
</details>

### `onDrop(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `scene.getObjectById`
- `moveObject`

**Internal Comments:**
```
// end of list (no next object) (x3)
```

<details><summary>Code</summary>

```typescript
function onDrop( event ) {

			if ( this === currentDrag || currentDrag === undefined ) return;

			this.className = 'option';

			const scene = scope.scene;
			const object = scene.getObjectById( currentDrag.value );

			const area = event.offsetY / this.clientHeight;

			if ( area < 0.25 ) {

				const nextObject = scene.getObjectById( this.value );
				moveObject( object, nextObject.parent, nextObject );

			} else if ( area > 0.75 ) {

				let nextObject, parent;

				if ( this.nextSibling !== null ) {

					nextObject = scene.getObjectById( this.nextSibling.value );
					parent = nextObject.parent;

				} else {

					// end of list (no next object)

					nextObject = null;
					parent = scene.getObjectById( this.value ).parent;

				}

				moveObject( object, parent, nextObject );

			} else {

				const parentObject = scene.getObjectById( this.value );
				moveObject( object, parentObject );

			}

		}
```
</details>

### `moveObject(object: any, newParent: any, nextObject: any): void`

**Parameters:**

- **`object`** `any`
- **`newParent`** `any`
- **`nextObject`** `any`

**Returns:** `void`

**Calls:**

- `object.traverse`
- `editor.execute`
- `scope.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
function moveObject( object, newParent, nextObject ) {

			if ( nextObject === null ) nextObject = undefined;

			let newParentIsChild = false;

			object.traverse( function ( child ) {

				if ( child === newParent ) newParentIsChild = true;

			} );

			if ( newParentIsChild ) return;

			const editor = scope.editor;
			editor.execute( new MoveObjectCommand( editor, object, newParent, nextObject ) );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			scope.dom.dispatchEvent( changeEvent );

		}
```
</details>

### `UIPoints.onChange(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
onChange( callback ) {

		this.onChangeCallback = callback;

		return this;

	}
```
</details>

### `UIPoints.clear(): void`

**Returns:** `void`

**Calls:**

- `this.deletePointRow`

<details><summary>Code</summary>

```typescript
clear() {

		for ( let i = this.pointsUI.length - 1; i >= 0; -- i ) {

			this.deletePointRow( i, false );

		}

		this.lastPointIdx = 0;

	}
```
</details>

### `UIPoints.deletePointRow(idx: any, needsUpdate: boolean): void`

**Parameters:**

- **`idx`** `any`
- **`needsUpdate`** `boolean`

**Returns:** `void`

**Calls:**

- `this.pointsList.remove`
- `this.pointsUI.splice`
- `this.update`

<details><summary>Code</summary>

```typescript
deletePointRow( idx, needsUpdate = true ) {

		if ( ! this.pointsUI[ idx ] ) return;

		this.pointsList.remove( this.pointsUI[ idx ].row );

		this.pointsUI.splice( idx, 1 );

		if ( needsUpdate === true ) {

			this.update();

		}

		this.lastPointIdx --;

	}
```
</details>

### `UIPoints2.getValue(): any[]`

**Returns:** `any[]`

**Calls:**

- `points.push`
- `pointUI.x.getValue`
- `pointUI.y.getValue`
- `pointUI.lbl.setValue`

<details><summary>Code</summary>

```typescript
getValue() {

		const points = [];

		let count = 0;

		for ( let i = 0; i < this.pointsUI.length; i ++ ) {

			const pointUI = this.pointsUI[ i ];

			if ( ! pointUI ) continue;

			points.push( new THREE.Vector2( pointUI.x.getValue(), pointUI.y.getValue() ) );
			++ count;
			pointUI.lbl.setValue( count );

		}

		return points;

	}
```
</details>

### `UIPoints2.setValue(points: any, needsUpdate: boolean): this`

**Parameters:**

- **`points`** `any`
- **`needsUpdate`** `boolean`

**Returns:** `this`

**Calls:**

- `this.clear`
- `this.pointsList.add`
- `this.createPointRow`
- `this.update`

<details><summary>Code</summary>

```typescript
setValue( points, needsUpdate = true ) {

		this.clear();

		for ( let i = 0; i < points.length; i ++ ) {

			const point = points[ i ];
			this.pointsList.add( this.createPointRow( point.x, point.y ) );

		}

		if ( needsUpdate === true ) this.update();

		return this;

	}
```
</details>

### `UIPoints2.createPointRow(x: any, y: any): UIDiv`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `UIDiv`

**Calls:**

- `new UIText( this.lastPointIdx + 1 ).setWidth`
- `new UINumber( x ).setWidth( '30px' ).onChange`
- `new UINumber( y ).setWidth( '30px' ).onChange`
- `new UIButton( '-' ).onClick`
- `scope.pointsList.getIndexOfChild`
- `scope.deletePointRow`
- `this.pointsUI.push`
- `pointRow.add`

<details><summary>Code</summary>

```typescript
createPointRow( x, y ) {

		const pointRow = new UIDiv();
		const lbl = new UIText( this.lastPointIdx + 1 ).setWidth( '20px' );
		const txtX = new UINumber( x ).setWidth( '30px' ).onChange( this.update );
		const txtY = new UINumber( y ).setWidth( '30px' ).onChange( this.update );

		const scope = this;
		const btn = new UIButton( '-' ).onClick( function () {

			if ( scope.isEditing ) return;

			const idx = scope.pointsList.getIndexOfChild( pointRow );
			scope.deletePointRow( idx );

		} );

		this.pointsUI.push( { row: pointRow, lbl: lbl, x: txtX, y: txtY } );
		++ this.lastPointIdx;
		pointRow.add( lbl, txtX, txtY, btn );

		return pointRow;

	}
```
</details>

### `UIPoints3.getValue(): any[]`

**Returns:** `any[]`

**Calls:**

- `points.push`
- `pointUI.x.getValue`
- `pointUI.y.getValue`
- `pointUI.z.getValue`
- `pointUI.lbl.setValue`

<details><summary>Code</summary>

```typescript
getValue() {

		const points = [];
		let count = 0;

		for ( let i = 0; i < this.pointsUI.length; i ++ ) {

			const pointUI = this.pointsUI[ i ];

			if ( ! pointUI ) continue;

			points.push( new THREE.Vector3( pointUI.x.getValue(), pointUI.y.getValue(), pointUI.z.getValue() ) );
			++ count;
			pointUI.lbl.setValue( count );

		}

		return points;

	}
```
</details>

### `UIPoints3.setValue(points: any, needsUpdate: boolean): this`

**Parameters:**

- **`points`** `any`
- **`needsUpdate`** `boolean`

**Returns:** `this`

**Calls:**

- `this.clear`
- `this.pointsList.add`
- `this.createPointRow`
- `this.update`

<details><summary>Code</summary>

```typescript
setValue( points, needsUpdate = true ) {

		this.clear();

		for ( let i = 0; i < points.length; i ++ ) {

			const point = points[ i ];
			this.pointsList.add( this.createPointRow( point.x, point.y, point.z ) );

		}

		if ( needsUpdate === true ) this.update();

		return this;

	}
```
</details>

### `UIPoints3.createPointRow(x: any, y: any, z: any): UIDiv`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`

**Returns:** `UIDiv`

**Calls:**

- `new UIText( this.lastPointIdx + 1 ).setWidth`
- `new UINumber( x ).setWidth( '30px' ).onChange`
- `new UINumber( y ).setWidth( '30px' ).onChange`
- `new UINumber( z ).setWidth( '30px' ).onChange`
- `new UIButton( '-' ).onClick`
- `scope.pointsList.getIndexOfChild`
- `scope.deletePointRow`
- `this.pointsUI.push`
- `pointRow.add`

<details><summary>Code</summary>

```typescript
createPointRow( x, y, z ) {

		const pointRow = new UIDiv();
		const lbl = new UIText( this.lastPointIdx + 1 ).setWidth( '20px' );
		const txtX = new UINumber( x ).setWidth( '30px' ).onChange( this.update );
		const txtY = new UINumber( y ).setWidth( '30px' ).onChange( this.update );
		const txtZ = new UINumber( z ).setWidth( '30px' ).onChange( this.update );

		const scope = this;
		const btn = new UIButton( '-' ).onClick( function () {

			if ( scope.isEditing ) return;

			const idx = scope.pointsList.getIndexOfChild( pointRow );
			scope.deletePointRow( idx );

		} );

		this.pointsUI.push( { row: pointRow, lbl: lbl, x: txtX, y: txtY, z: txtZ } );
		++ this.lastPointIdx;
		pointRow.add( lbl, txtX, txtY, txtZ, btn );

		return pointRow;

	}
```
</details>

### `UIBoolean.getValue(): any`

**Returns:** `any`

**Calls:**

- `this.checkbox.getValue`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.checkbox.getValue();

	}
```
</details>

### `UIBoolean.setValue(value: any): UICheckbox`

**Parameters:**

- **`value`** `any`

**Returns:** `UICheckbox`

**Calls:**

- `this.checkbox.setValue`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		return this.checkbox.setValue( value );

	}
```
</details>

### `renderToCanvas(texture: any): any`

**Parameters:**

- **`texture`** `any`

**Returns:** `any`

**Calls:**

- `renderer.setSize`
- `fsQuad.render`

<details><summary>Code</summary>

```typescript
function renderToCanvas( texture ) {

	if ( renderer === undefined ) {

		renderer = new THREE.WebGLRenderer();

	}

	if ( fsQuad === undefined ) {

		fsQuad = new FullScreenQuad( new THREE.MeshBasicMaterial() );

	}

	const image = texture.image;

	renderer.setSize( image.width, image.height, false );

	fsQuad.material.map = texture;
	fsQuad.render( renderer );

	return renderer.domElement;

}
```
</details>


---

## Classes

### `UITexture`

<details><summary>Class Code</summary>

```ts
class UITexture extends UISpan {

	constructor( editor ) {

		super();

		const scope = this;

		const form = document.createElement( 'form' );

		const input = document.createElement( 'input' );
		input.type = 'file';
		input.addEventListener( 'change', function ( event ) {

			loadFile( event.target.files[ 0 ] );

		} );
		form.appendChild( input );

		const canvas = document.createElement( 'canvas' );
		canvas.width = 32;
		canvas.height = 16;
		canvas.style.cursor = 'pointer';
		canvas.style.marginRight = '5px';
		canvas.style.border = '1px solid #888';
		canvas.addEventListener( 'click', function () {

			input.click();

		} );
		canvas.addEventListener( 'drop', function ( event ) {

			event.preventDefault();
			event.stopPropagation();
			loadFile( event.dataTransfer.files[ 0 ] );

		} );
		this.dom.appendChild( canvas );

		async function loadFile( file ) {

			const extension = file.name.split( '.' ).pop().toLowerCase();
			const reader = new FileReader();

			const hash = `${file.lastModified}_${file.size}_${file.name}`;

			if ( cache.has( hash ) ) {

				const texture = cache.get( hash );

				scope.setValue( texture );

				if ( scope.onChangeCallback ) scope.onChangeCallback( texture );

			} else if ( extension === 'hdr' || extension === 'pic' ) {

				reader.addEventListener( 'load', async function ( event ) {

					// assuming RGBE/Radiance HDR image format

					const { RGBELoader } = await import( 'three/addons/loaders/RGBELoader.js' );

					const loader = new RGBELoader();
					loader.load( event.target.result, function ( hdrTexture ) {

						hdrTexture.sourceFile = file.name;

						cache.set( hash, hdrTexture );

						scope.setValue( hdrTexture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( hdrTexture );

					} );

				} );

				reader.readAsDataURL( file );

			} else if ( extension === 'tga' ) {

				reader.addEventListener( 'load', async function ( event ) {

					const { TGALoader } = await import( 'three/addons/loaders/TGALoader.js' );

					const loader = new TGALoader();
					loader.load( event.target.result, function ( texture ) {

						texture.colorSpace = THREE.SRGBColorSpace;
						texture.sourceFile = file.name;

						cache.set( hash, texture );

						scope.setValue( texture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( texture );


					} );

				}, false );

				reader.readAsDataURL( file );

			} else if ( extension === 'ktx2' ) {

				reader.addEventListener( 'load', async function ( event ) {

					const { KTX2Loader } = await import( 'three/addons/loaders/KTX2Loader.js' );

					const arrayBuffer = event.target.result;
					const blobURL = URL.createObjectURL( new Blob( [ arrayBuffer ] ) );
					const ktx2Loader = new KTX2Loader();
					ktx2Loader.setTranscoderPath( '../../examples/jsm/libs/basis/' );
					editor.signals.rendererDetectKTX2Support.dispatch( ktx2Loader );

					ktx2Loader.load( blobURL, function ( texture ) {

						texture.colorSpace = THREE.SRGBColorSpace;
						texture.sourceFile = file.name;
						texture.needsUpdate = true;

						cache.set( hash, texture );

						scope.setValue( texture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( texture );
						ktx2Loader.dispose();

					} );

				} );

				reader.readAsArrayBuffer( file );

			} else if ( extension === 'exr' ) {

				reader.addEventListener( 'load', async function ( event ) {

					const { EXRLoader } = await import( 'three/addons/loaders/EXRLoader.js' );

					const arrayBuffer = event.target.result;
					const blobURL = URL.createObjectURL( new Blob( [ arrayBuffer ] ) );
					const exrLoader = new EXRLoader();

					exrLoader.load( blobURL, function ( texture ) {

						texture.sourceFile = file.name;
						texture.needsUpdate = true;

						cache.set( hash, texture );

						scope.setValue( texture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( texture );

					} );

				} );

				reader.readAsArrayBuffer( file );

			} else if ( file.type.match( 'image.*' ) ) {

				reader.addEventListener( 'load', function ( event ) {

					const image = document.createElement( 'img' );
					image.addEventListener( 'load', function () {

						const texture = new THREE.Texture( this );
						texture.sourceFile = file.name;
						texture.needsUpdate = true;

						cache.set( hash, texture );

						scope.setValue( texture );

						if ( scope.onChangeCallback ) scope.onChangeCallback( texture );

					}, false );

					image.src = event.target.result;

				}, false );

				reader.readAsDataURL( file );

			}

			form.reset();

		}

		this.texture = null;
		this.onChangeCallback = null;

	}

	getValue() {

		return this.texture;

	}

	setValue( texture ) {

		const canvas = this.dom.children[ 0 ];
		const context = canvas.getContext( '2d' );

		// Seems like context can be null if the canvas is not visible
		if ( context ) {

			// Always clear the context before set new texture, because new texture may has transparency
			context.clearRect( 0, 0, canvas.width, canvas.height );

		}

		if ( texture !== null ) {

			const image = texture.image;

			if ( image !== undefined && image !== null && image.width > 0 ) {

				canvas.title = texture.sourceFile;
				const scale = canvas.width / image.width;

				if ( texture.isDataTexture || texture.isCompressedTexture ) {

					const canvas2 = renderToCanvas( texture );
					context.drawImage( canvas2, 0, 0, image.width * scale, image.height * scale );

				} else {

					context.drawImage( image, 0, 0, image.width * scale, image.height * scale );

				}

			} else {

				canvas.title = texture.sourceFile + ' (error)';

			}

		} else {

			canvas.title = 'empty';

		}

		this.texture = texture;

	}

	setColorSpace( colorSpace ) {

		const texture = this.getValue();

		if ( texture !== null ) {

			texture.colorSpace = colorSpace;

		}

		return this;

	}

	onChange( callback ) {

		this.onChangeCallback = callback;

		return this;

	}

}
```
</details>

#### Methods

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.texture;

	}
```
</details>

##### `setValue(texture: any): void`

<details><summary>Code</summary>

```ts
setValue( texture ) {

		const canvas = this.dom.children[ 0 ];
		const context = canvas.getContext( '2d' );

		// Seems like context can be null if the canvas is not visible
		if ( context ) {

			// Always clear the context before set new texture, because new texture may has transparency
			context.clearRect( 0, 0, canvas.width, canvas.height );

		}

		if ( texture !== null ) {

			const image = texture.image;

			if ( image !== undefined && image !== null && image.width > 0 ) {

				canvas.title = texture.sourceFile;
				const scale = canvas.width / image.width;

				if ( texture.isDataTexture || texture.isCompressedTexture ) {

					const canvas2 = renderToCanvas( texture );
					context.drawImage( canvas2, 0, 0, image.width * scale, image.height * scale );

				} else {

					context.drawImage( image, 0, 0, image.width * scale, image.height * scale );

				}

			} else {

				canvas.title = texture.sourceFile + ' (error)';

			}

		} else {

			canvas.title = 'empty';

		}

		this.texture = texture;

	}
```
</details>

##### `setColorSpace(colorSpace: any): this`

<details><summary>Code</summary>

```ts
setColorSpace( colorSpace ) {

		const texture = this.getValue();

		if ( texture !== null ) {

			texture.colorSpace = colorSpace;

		}

		return this;

	}
```
</details>

##### `onChange(callback: any): this`

<details><summary>Code</summary>

```ts
onChange( callback ) {

		this.onChangeCallback = callback;

		return this;

	}
```
</details>

### `UIOutliner`

<details><summary>Class Code</summary>

```ts
class UIOutliner extends UIDiv {

	constructor( editor ) {

		super();

		this.dom.className = 'Outliner';
		this.dom.tabIndex = 0;	// keyup event is ignored without setting tabIndex

		const scope = this;

		// hack
		this.scene = editor.scene;

		// Prevent native scroll behavior
		this.dom.addEventListener( 'keydown', function ( event ) {

			switch ( event.code ) {

				case 'ArrowUp':
				case 'ArrowDown':
					event.preventDefault();
					event.stopPropagation();
					break;

			}

		} );

		// Keybindings to support arrow navigation
		this.dom.addEventListener( 'keyup', function ( event ) {

			switch ( event.code ) {

				case 'ArrowUp':
					scope.selectIndex( scope.selectedIndex - 1 );
					break;
				case 'ArrowDown':
					scope.selectIndex( scope.selectedIndex + 1 );
					break;

			}

		} );

		this.editor = editor;

		this.options = [];
		this.selectedIndex = - 1;
		this.selectedValue = null;

	}

	selectIndex( index ) {

		if ( index >= 0 && index < this.options.length ) {

			this.setValue( this.options[ index ].value );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			this.dom.dispatchEvent( changeEvent );

		}

	}

	setOptions( options ) {

		const scope = this;

		while ( scope.dom.children.length > 0 ) {

			scope.dom.removeChild( scope.dom.firstChild );

		}

		function onClick() {

			scope.setValue( this.value );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			scope.dom.dispatchEvent( changeEvent );

		}

		// Drag

		let currentDrag;

		function onDrag() {

			currentDrag = this;

		}

		function onDragStart( event ) {

			event.dataTransfer.setData( 'text', 'foo' );

		}

		function onDragOver( event ) {

			if ( this === currentDrag ) return;

			const area = event.offsetY / this.clientHeight;

			if ( area < 0.25 ) {

				this.className = 'option dragTop';

			} else if ( area > 0.75 ) {

				this.className = 'option dragBottom';

			} else {

				this.className = 'option drag';

			}

		}

		function onDragLeave() {

			if ( this === currentDrag ) return;

			this.className = 'option';

		}

		function onDrop( event ) {

			if ( this === currentDrag || currentDrag === undefined ) return;

			this.className = 'option';

			const scene = scope.scene;
			const object = scene.getObjectById( currentDrag.value );

			const area = event.offsetY / this.clientHeight;

			if ( area < 0.25 ) {

				const nextObject = scene.getObjectById( this.value );
				moveObject( object, nextObject.parent, nextObject );

			} else if ( area > 0.75 ) {

				let nextObject, parent;

				if ( this.nextSibling !== null ) {

					nextObject = scene.getObjectById( this.nextSibling.value );
					parent = nextObject.parent;

				} else {

					// end of list (no next object)

					nextObject = null;
					parent = scene.getObjectById( this.value ).parent;

				}

				moveObject( object, parent, nextObject );

			} else {

				const parentObject = scene.getObjectById( this.value );
				moveObject( object, parentObject );

			}

		}

		function moveObject( object, newParent, nextObject ) {

			if ( nextObject === null ) nextObject = undefined;

			let newParentIsChild = false;

			object.traverse( function ( child ) {

				if ( child === newParent ) newParentIsChild = true;

			} );

			if ( newParentIsChild ) return;

			const editor = scope.editor;
			editor.execute( new MoveObjectCommand( editor, object, newParent, nextObject ) );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			scope.dom.dispatchEvent( changeEvent );

		}

		//

		scope.options = [];

		for ( let i = 0; i < options.length; i ++ ) {

			const div = options[ i ];
			div.className = 'option';
			scope.dom.appendChild( div );

			scope.options.push( div );

			div.addEventListener( 'click', onClick );

			if ( div.draggable === true ) {

				div.addEventListener( 'drag', onDrag );
				div.addEventListener( 'dragstart', onDragStart ); // Firefox needs this

				div.addEventListener( 'dragover', onDragOver );
				div.addEventListener( 'dragleave', onDragLeave );
				div.addEventListener( 'drop', onDrop );

			}


		}

		return scope;

	}

	getValue() {

		return this.selectedValue;

	}

	setValue( value ) {

		for ( let i = 0; i < this.options.length; i ++ ) {

			const element = this.options[ i ];

			if ( element.value === value ) {

				element.classList.add( 'active' );

				// scroll into view

				const y = element.offsetTop - this.dom.offsetTop;
				const bottomY = y + element.offsetHeight;
				const minScroll = bottomY - this.dom.offsetHeight;

				if ( this.dom.scrollTop > y ) {

					this.dom.scrollTop = y;

				} else if ( this.dom.scrollTop < minScroll ) {

					this.dom.scrollTop = minScroll;

				}

				this.selectedIndex = i;

			} else {

				element.classList.remove( 'active' );

			}

		}

		this.selectedValue = value;

		return this;

	}

}
```
</details>

#### Methods

##### `selectIndex(index: any): void`

<details><summary>Code</summary>

```ts
selectIndex( index ) {

		if ( index >= 0 && index < this.options.length ) {

			this.setValue( this.options[ index ].value );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			this.dom.dispatchEvent( changeEvent );

		}

	}
```
</details>

##### `setOptions(options: any): this`

<details><summary>Code</summary>

```ts
setOptions( options ) {

		const scope = this;

		while ( scope.dom.children.length > 0 ) {

			scope.dom.removeChild( scope.dom.firstChild );

		}

		function onClick() {

			scope.setValue( this.value );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			scope.dom.dispatchEvent( changeEvent );

		}

		// Drag

		let currentDrag;

		function onDrag() {

			currentDrag = this;

		}

		function onDragStart( event ) {

			event.dataTransfer.setData( 'text', 'foo' );

		}

		function onDragOver( event ) {

			if ( this === currentDrag ) return;

			const area = event.offsetY / this.clientHeight;

			if ( area < 0.25 ) {

				this.className = 'option dragTop';

			} else if ( area > 0.75 ) {

				this.className = 'option dragBottom';

			} else {

				this.className = 'option drag';

			}

		}

		function onDragLeave() {

			if ( this === currentDrag ) return;

			this.className = 'option';

		}

		function onDrop( event ) {

			if ( this === currentDrag || currentDrag === undefined ) return;

			this.className = 'option';

			const scene = scope.scene;
			const object = scene.getObjectById( currentDrag.value );

			const area = event.offsetY / this.clientHeight;

			if ( area < 0.25 ) {

				const nextObject = scene.getObjectById( this.value );
				moveObject( object, nextObject.parent, nextObject );

			} else if ( area > 0.75 ) {

				let nextObject, parent;

				if ( this.nextSibling !== null ) {

					nextObject = scene.getObjectById( this.nextSibling.value );
					parent = nextObject.parent;

				} else {

					// end of list (no next object)

					nextObject = null;
					parent = scene.getObjectById( this.value ).parent;

				}

				moveObject( object, parent, nextObject );

			} else {

				const parentObject = scene.getObjectById( this.value );
				moveObject( object, parentObject );

			}

		}

		function moveObject( object, newParent, nextObject ) {

			if ( nextObject === null ) nextObject = undefined;

			let newParentIsChild = false;

			object.traverse( function ( child ) {

				if ( child === newParent ) newParentIsChild = true;

			} );

			if ( newParentIsChild ) return;

			const editor = scope.editor;
			editor.execute( new MoveObjectCommand( editor, object, newParent, nextObject ) );

			const changeEvent = new Event( 'change', { bubbles: true, cancelable: true } );
			scope.dom.dispatchEvent( changeEvent );

		}

		//

		scope.options = [];

		for ( let i = 0; i < options.length; i ++ ) {

			const div = options[ i ];
			div.className = 'option';
			scope.dom.appendChild( div );

			scope.options.push( div );

			div.addEventListener( 'click', onClick );

			if ( div.draggable === true ) {

				div.addEventListener( 'drag', onDrag );
				div.addEventListener( 'dragstart', onDragStart ); // Firefox needs this

				div.addEventListener( 'dragover', onDragOver );
				div.addEventListener( 'dragleave', onDragLeave );
				div.addEventListener( 'drop', onDrop );

			}


		}

		return scope;

	}
```
</details>

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.selectedValue;

	}
```
</details>

##### `setValue(value: any): this`

<details><summary>Code</summary>

```ts
setValue( value ) {

		for ( let i = 0; i < this.options.length; i ++ ) {

			const element = this.options[ i ];

			if ( element.value === value ) {

				element.classList.add( 'active' );

				// scroll into view

				const y = element.offsetTop - this.dom.offsetTop;
				const bottomY = y + element.offsetHeight;
				const minScroll = bottomY - this.dom.offsetHeight;

				if ( this.dom.scrollTop > y ) {

					this.dom.scrollTop = y;

				} else if ( this.dom.scrollTop < minScroll ) {

					this.dom.scrollTop = minScroll;

				}

				this.selectedIndex = i;

			} else {

				element.classList.remove( 'active' );

			}

		}

		this.selectedValue = value;

		return this;

	}
```
</details>

### `UIPoints`

<details><summary>Class Code</summary>

```ts
class UIPoints extends UISpan {

	constructor() {

		super();

		this.dom.style.display = 'inline-block';

		this.pointsList = new UIDiv();
		this.add( this.pointsList );

		this.pointsUI = [];
		this.lastPointIdx = 0;
		this.onChangeCallback = null;

		this.update = () => { // bind lexical this

			if ( this.onChangeCallback !== null ) {

				this.onChangeCallback();

			}

		};

	}

	onChange( callback ) {

		this.onChangeCallback = callback;

		return this;

	}

	clear() {

		for ( let i = this.pointsUI.length - 1; i >= 0; -- i ) {

			this.deletePointRow( i, false );

		}

		this.lastPointIdx = 0;

	}

	deletePointRow( idx, needsUpdate = true ) {

		if ( ! this.pointsUI[ idx ] ) return;

		this.pointsList.remove( this.pointsUI[ idx ].row );

		this.pointsUI.splice( idx, 1 );

		if ( needsUpdate === true ) {

			this.update();

		}

		this.lastPointIdx --;

	}

}
```
</details>

#### Methods

##### `onChange(callback: any): this`

<details><summary>Code</summary>

```ts
onChange( callback ) {

		this.onChangeCallback = callback;

		return this;

	}
```
</details>

##### `clear(): void`

<details><summary>Code</summary>

```ts
clear() {

		for ( let i = this.pointsUI.length - 1; i >= 0; -- i ) {

			this.deletePointRow( i, false );

		}

		this.lastPointIdx = 0;

	}
```
</details>

##### `deletePointRow(idx: any, needsUpdate: boolean): void`

<details><summary>Code</summary>

```ts
deletePointRow( idx, needsUpdate = true ) {

		if ( ! this.pointsUI[ idx ] ) return;

		this.pointsList.remove( this.pointsUI[ idx ].row );

		this.pointsUI.splice( idx, 1 );

		if ( needsUpdate === true ) {

			this.update();

		}

		this.lastPointIdx --;

	}
```
</details>

### `UIPoints2`

<details><summary>Class Code</summary>

```ts
class UIPoints2 extends UIPoints {

	constructor() {

		super();

		const row = new UIRow();
		this.add( row );

		const addPointButton = new UIButton( '+' );
		addPointButton.onClick( () => {

			if ( this.pointsUI.length === 0 ) {

				this.pointsList.add( this.createPointRow( 0, 0 ) );

			} else {

				const point = this.pointsUI[ this.pointsUI.length - 1 ];

				this.pointsList.add( this.createPointRow( point.x.getValue(), point.y.getValue() ) );

			}

			this.update();

		} );
		row.add( addPointButton );

	}

	getValue() {

		const points = [];

		let count = 0;

		for ( let i = 0; i < this.pointsUI.length; i ++ ) {

			const pointUI = this.pointsUI[ i ];

			if ( ! pointUI ) continue;

			points.push( new THREE.Vector2( pointUI.x.getValue(), pointUI.y.getValue() ) );
			++ count;
			pointUI.lbl.setValue( count );

		}

		return points;

	}

	setValue( points, needsUpdate = true ) {

		this.clear();

		for ( let i = 0; i < points.length; i ++ ) {

			const point = points[ i ];
			this.pointsList.add( this.createPointRow( point.x, point.y ) );

		}

		if ( needsUpdate === true ) this.update();

		return this;

	}

	createPointRow( x, y ) {

		const pointRow = new UIDiv();
		const lbl = new UIText( this.lastPointIdx + 1 ).setWidth( '20px' );
		const txtX = new UINumber( x ).setWidth( '30px' ).onChange( this.update );
		const txtY = new UINumber( y ).setWidth( '30px' ).onChange( this.update );

		const scope = this;
		const btn = new UIButton( '-' ).onClick( function () {

			if ( scope.isEditing ) return;

			const idx = scope.pointsList.getIndexOfChild( pointRow );
			scope.deletePointRow( idx );

		} );

		this.pointsUI.push( { row: pointRow, lbl: lbl, x: txtX, y: txtY } );
		++ this.lastPointIdx;
		pointRow.add( lbl, txtX, txtY, btn );

		return pointRow;

	}

}
```
</details>

#### Methods

##### `getValue(): any[]`

<details><summary>Code</summary>

```ts
getValue() {

		const points = [];

		let count = 0;

		for ( let i = 0; i < this.pointsUI.length; i ++ ) {

			const pointUI = this.pointsUI[ i ];

			if ( ! pointUI ) continue;

			points.push( new THREE.Vector2( pointUI.x.getValue(), pointUI.y.getValue() ) );
			++ count;
			pointUI.lbl.setValue( count );

		}

		return points;

	}
```
</details>

##### `setValue(points: any, needsUpdate: boolean): this`

<details><summary>Code</summary>

```ts
setValue( points, needsUpdate = true ) {

		this.clear();

		for ( let i = 0; i < points.length; i ++ ) {

			const point = points[ i ];
			this.pointsList.add( this.createPointRow( point.x, point.y ) );

		}

		if ( needsUpdate === true ) this.update();

		return this;

	}
```
</details>

##### `createPointRow(x: any, y: any): UIDiv`

<details><summary>Code</summary>

```ts
createPointRow( x, y ) {

		const pointRow = new UIDiv();
		const lbl = new UIText( this.lastPointIdx + 1 ).setWidth( '20px' );
		const txtX = new UINumber( x ).setWidth( '30px' ).onChange( this.update );
		const txtY = new UINumber( y ).setWidth( '30px' ).onChange( this.update );

		const scope = this;
		const btn = new UIButton( '-' ).onClick( function () {

			if ( scope.isEditing ) return;

			const idx = scope.pointsList.getIndexOfChild( pointRow );
			scope.deletePointRow( idx );

		} );

		this.pointsUI.push( { row: pointRow, lbl: lbl, x: txtX, y: txtY } );
		++ this.lastPointIdx;
		pointRow.add( lbl, txtX, txtY, btn );

		return pointRow;

	}
```
</details>

### `UIPoints3`

<details><summary>Class Code</summary>

```ts
class UIPoints3 extends UIPoints {

	constructor() {

		super();

		const row = new UIRow();
		this.add( row );

		const addPointButton = new UIButton( '+' );
		addPointButton.onClick( () => {

			if ( this.pointsUI.length === 0 ) {

				this.pointsList.add( this.createPointRow( 0, 0, 0 ) );

			} else {

				const point = this.pointsUI[ this.pointsUI.length - 1 ];

				this.pointsList.add( this.createPointRow( point.x.getValue(), point.y.getValue(), point.z.getValue() ) );

			}

			this.update();

		} );
		row.add( addPointButton );

	}

	getValue() {

		const points = [];
		let count = 0;

		for ( let i = 0; i < this.pointsUI.length; i ++ ) {

			const pointUI = this.pointsUI[ i ];

			if ( ! pointUI ) continue;

			points.push( new THREE.Vector3( pointUI.x.getValue(), pointUI.y.getValue(), pointUI.z.getValue() ) );
			++ count;
			pointUI.lbl.setValue( count );

		}

		return points;

	}

	setValue( points, needsUpdate = true ) {

		this.clear();

		for ( let i = 0; i < points.length; i ++ ) {

			const point = points[ i ];
			this.pointsList.add( this.createPointRow( point.x, point.y, point.z ) );

		}

		if ( needsUpdate === true ) this.update();

		return this;

	}

	createPointRow( x, y, z ) {

		const pointRow = new UIDiv();
		const lbl = new UIText( this.lastPointIdx + 1 ).setWidth( '20px' );
		const txtX = new UINumber( x ).setWidth( '30px' ).onChange( this.update );
		const txtY = new UINumber( y ).setWidth( '30px' ).onChange( this.update );
		const txtZ = new UINumber( z ).setWidth( '30px' ).onChange( this.update );

		const scope = this;
		const btn = new UIButton( '-' ).onClick( function () {

			if ( scope.isEditing ) return;

			const idx = scope.pointsList.getIndexOfChild( pointRow );
			scope.deletePointRow( idx );

		} );

		this.pointsUI.push( { row: pointRow, lbl: lbl, x: txtX, y: txtY, z: txtZ } );
		++ this.lastPointIdx;
		pointRow.add( lbl, txtX, txtY, txtZ, btn );

		return pointRow;

	}

}
```
</details>

#### Methods

##### `getValue(): any[]`

<details><summary>Code</summary>

```ts
getValue() {

		const points = [];
		let count = 0;

		for ( let i = 0; i < this.pointsUI.length; i ++ ) {

			const pointUI = this.pointsUI[ i ];

			if ( ! pointUI ) continue;

			points.push( new THREE.Vector3( pointUI.x.getValue(), pointUI.y.getValue(), pointUI.z.getValue() ) );
			++ count;
			pointUI.lbl.setValue( count );

		}

		return points;

	}
```
</details>

##### `setValue(points: any, needsUpdate: boolean): this`

<details><summary>Code</summary>

```ts
setValue( points, needsUpdate = true ) {

		this.clear();

		for ( let i = 0; i < points.length; i ++ ) {

			const point = points[ i ];
			this.pointsList.add( this.createPointRow( point.x, point.y, point.z ) );

		}

		if ( needsUpdate === true ) this.update();

		return this;

	}
```
</details>

##### `createPointRow(x: any, y: any, z: any): UIDiv`

<details><summary>Code</summary>

```ts
createPointRow( x, y, z ) {

		const pointRow = new UIDiv();
		const lbl = new UIText( this.lastPointIdx + 1 ).setWidth( '20px' );
		const txtX = new UINumber( x ).setWidth( '30px' ).onChange( this.update );
		const txtY = new UINumber( y ).setWidth( '30px' ).onChange( this.update );
		const txtZ = new UINumber( z ).setWidth( '30px' ).onChange( this.update );

		const scope = this;
		const btn = new UIButton( '-' ).onClick( function () {

			if ( scope.isEditing ) return;

			const idx = scope.pointsList.getIndexOfChild( pointRow );
			scope.deletePointRow( idx );

		} );

		this.pointsUI.push( { row: pointRow, lbl: lbl, x: txtX, y: txtY, z: txtZ } );
		++ this.lastPointIdx;
		pointRow.add( lbl, txtX, txtY, txtZ, btn );

		return pointRow;

	}
```
</details>

### `UIBoolean`

<details><summary>Class Code</summary>

```ts
class UIBoolean extends UISpan {

	constructor( boolean, text ) {

		super();

		this.setMarginRight( '4px' );

		this.checkbox = new UICheckbox( boolean );
		this.text = new UIText( text ).setMarginLeft( '3px' );

		this.add( this.checkbox );
		this.add( this.text );

	}

	getValue() {

		return this.checkbox.getValue();

	}

	setValue( value ) {

		return this.checkbox.setValue( value );

	}

}
```
</details>

#### Methods

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.checkbox.getValue();

	}
```
</details>

##### `setValue(value: any): UICheckbox`

<details><summary>Code</summary>

```ts
setValue( value ) {

		return this.checkbox.setValue( value );

	}
```
</details>


---