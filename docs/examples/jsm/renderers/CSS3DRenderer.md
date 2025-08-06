[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CSS3DRenderer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 3 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 26 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/renderers/CSS3DRenderer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix4` | `three` |
| `Object3D` | `three` |
| `Quaternion` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_position` | `any` | let/var | `new Vector3()` | ✗ |
| `_quaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `_scale` | `any` | let/var | `new Vector3()` | ✗ |
| `_matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_matrix2` | `any` | let/var | `new Matrix4()` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `_width` | `any` | let/var | `*not shown*` | ✗ |
| `_height` | `any` | let/var | `*not shown*` | ✗ |
| `_widthHalf` | `any` | let/var | `*not shown*` | ✗ |
| `_heightHalf` | `any` | let/var | `*not shown*` | ✗ |
| `cache` | `{ camera: { style: string; }; objects...` | let/var | `{ camera: { style: '' }, objects: new WeakMap() }` | ✗ |
| `domElement` | `any` | let/var | `parameters.element !== undefined ? parameters.element : document.createElemen...` | ✗ |
| `fov` | `number` | let/var | `camera.projectionMatrix.elements[ 5 ] * _heightHalf` | ✗ |
| `tx` | `any` | let/var | `*not shown*` | ✗ |
| `ty` | `any` | let/var | `*not shown*` | ✗ |
| `scaleByViewOffset` | `number` | let/var | `camera.view && camera.view.enabled ? camera.view.height / camera.view.fullHei...` | ✗ |
| `cameraCSSMatrix` | `string` | let/var | `camera.isOrthographicCamera ? `scale( ${ scaleByViewOffset } )` + 'scale(' + ...` | ✗ |
| `perspective` | `string` | let/var | `camera.isPerspectiveCamera ? 'perspective(' + fov + 'px) ' : ''` | ✗ |
| `style` | `string` | let/var | `perspective + cameraCSSMatrix + 'translate(' + _widthHalf + 'px,' + _heightHa...` | ✗ |
| `elements` | `any` | let/var | `matrix.elements` | ✗ |
| `elements` | `any` | let/var | `matrix.elements` | ✗ |
| `matrix3d` | `string` | let/var | `'matrix3d(' + epsilon( elements[ 0 ] ) + ',' + epsilon( elements[ 1 ] ) + ','...` | ✗ |
| `visible` | `boolean` | let/var | `( object.layers.test( camera.layers ) === true )` | ✗ |
| `element` | `any` | let/var | `object.element` | ✗ |
| `style` | `any` | let/var | `*not shown*` | ✗ |
| `objectData` | `{ style: string; }` | let/var | `{ style: style }` | ✗ |


---

## Functions

### `CSS3DObject.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `source.element.cloneNode`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.element = source.element.cloneNode( true );

		return this;

	}
```
</details>

### `CSS3DSprite.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.rotation2D = source.rotation2D;

		return this;

	}
```
</details>

### `epsilon(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function epsilon( value ) {

			return Math.abs( value ) < 1e-10 ? 0 : value;

		}
```
</details>

### `getCameraCSSMatrix(matrix: any): string`

**Parameters:**

- **`matrix`** `any`

**Returns:** `string`

**Calls:**

- `epsilon`

<details><summary>Code</summary>

```typescript
function getCameraCSSMatrix( matrix ) {

			const elements = matrix.elements;

			return 'matrix3d(' +
				epsilon( elements[ 0 ] ) + ',' +
				epsilon( - elements[ 1 ] ) + ',' +
				epsilon( elements[ 2 ] ) + ',' +
				epsilon( elements[ 3 ] ) + ',' +
				epsilon( elements[ 4 ] ) + ',' +
				epsilon( - elements[ 5 ] ) + ',' +
				epsilon( elements[ 6 ] ) + ',' +
				epsilon( elements[ 7 ] ) + ',' +
				epsilon( elements[ 8 ] ) + ',' +
				epsilon( - elements[ 9 ] ) + ',' +
				epsilon( elements[ 10 ] ) + ',' +
				epsilon( elements[ 11 ] ) + ',' +
				epsilon( elements[ 12 ] ) + ',' +
				epsilon( - elements[ 13 ] ) + ',' +
				epsilon( elements[ 14 ] ) + ',' +
				epsilon( elements[ 15 ] ) +
			')';

		}
```
</details>

### `getObjectCSSMatrix(matrix: any): string`

**Parameters:**

- **`matrix`** `any`

**Returns:** `string`

**Calls:**

- `epsilon`

<details><summary>Code</summary>

```typescript
function getObjectCSSMatrix( matrix ) {

			const elements = matrix.elements;
			const matrix3d = 'matrix3d(' +
				epsilon( elements[ 0 ] ) + ',' +
				epsilon( elements[ 1 ] ) + ',' +
				epsilon( elements[ 2 ] ) + ',' +
				epsilon( elements[ 3 ] ) + ',' +
				epsilon( - elements[ 4 ] ) + ',' +
				epsilon( - elements[ 5 ] ) + ',' +
				epsilon( - elements[ 6 ] ) + ',' +
				epsilon( - elements[ 7 ] ) + ',' +
				epsilon( elements[ 8 ] ) + ',' +
				epsilon( elements[ 9 ] ) + ',' +
				epsilon( elements[ 10 ] ) + ',' +
				epsilon( elements[ 11 ] ) + ',' +
				epsilon( elements[ 12 ] ) + ',' +
				epsilon( elements[ 13 ] ) + ',' +
				epsilon( elements[ 14 ] ) + ',' +
				epsilon( elements[ 15 ] ) +
			')';

			return 'translate(-50%,-50%)' + matrix3d;

		}
```
</details>

### `hideObject(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `hideObject`

<details><summary>Code</summary>

```typescript
function hideObject( object ) {

			if ( object.isCSS3DObject ) object.element.style.display = 'none';

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				hideObject( object.children[ i ] );

			}

		}
```
</details>

### `renderObject(object: any, scene: any, camera: any, cameraCSSMatrix: any): void`

**Parameters:**

- **`object`** `any`
- **`scene`** `any`
- **`camera`** `any`
- **`cameraCSSMatrix`** `any`

**Returns:** `void`

**Calls:**

- `hideObject`
- `object.layers.test`
- `object.onBeforeRender`
- `_matrix.copy`
- `_matrix.transpose`
- `_matrix.multiply`
- `_matrix2.makeRotationZ`
- `object.matrixWorld.decompose`
- `_matrix.setPosition`
- `_matrix.scale`
- `getObjectCSSMatrix`
- `cache.objects.get`
- `cache.objects.set`
- `cameraElement.appendChild`
- `object.onAfterRender`
- `renderObject`

**Internal Comments:**
```
// http://swiftcoder.wordpress.com/2008/11/25/constructing-a-billboard-matrix/ (x4)
```

<details><summary>Code</summary>

```typescript
function renderObject( object, scene, camera, cameraCSSMatrix ) {

			if ( object.visible === false ) {

				hideObject( object );

				return;

			}

			if ( object.isCSS3DObject ) {

				const visible = ( object.layers.test( camera.layers ) === true );

				const element = object.element;
				element.style.display = visible === true ? '' : 'none';

				if ( visible === true ) {

					object.onBeforeRender( _this, scene, camera );

					let style;

					if ( object.isCSS3DSprite ) {

						// http://swiftcoder.wordpress.com/2008/11/25/constructing-a-billboard-matrix/

						_matrix.copy( camera.matrixWorldInverse );
						_matrix.transpose();

						if ( object.rotation2D !== 0 ) _matrix.multiply( _matrix2.makeRotationZ( object.rotation2D ) );

						object.matrixWorld.decompose( _position, _quaternion, _scale );
						_matrix.setPosition( _position );
						_matrix.scale( _scale );

						_matrix.elements[ 3 ] = 0;
						_matrix.elements[ 7 ] = 0;
						_matrix.elements[ 11 ] = 0;
						_matrix.elements[ 15 ] = 1;

						style = getObjectCSSMatrix( _matrix );

					} else {

						style = getObjectCSSMatrix( object.matrixWorld );

					}

					const cachedObject = cache.objects.get( object );

					if ( cachedObject === undefined || cachedObject.style !== style ) {

						element.style.transform = style;

						const objectData = { style: style };
						cache.objects.set( object, objectData );

					}

					if ( element.parentNode !== cameraElement ) {

						cameraElement.appendChild( element );

					}

					object.onAfterRender( _this, scene, camera );

				}

			}

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				renderObject( object.children[ i ], scene, camera, cameraCSSMatrix );

			}

		}
```
</details>


---

## Classes

### `CSS3DObject`

<details><summary>Class Code</summary>

```ts
class CSS3DObject extends Object3D {

	/**
	 * Constructs a new CSS3D object.
	 *
	 * @param {DOMElement} [element] - The DOM element.
	 */
	constructor( element = document.createElement( 'div' ) ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCSS3DObject = true;

		/**
		 * The DOM element which defines the appearance of this 3D object.
		 *
		 * @type {DOMElement}
		 * @readonly
		 * @default true
		 */
		this.element = element;
		this.element.style.position = 'absolute';
		this.element.style.pointerEvents = 'auto';
		this.element.style.userSelect = 'none';

		this.element.setAttribute( 'draggable', false );

		this.addEventListener( 'removed', function () {

			this.traverse( function ( object ) {

				if (
					object.element instanceof object.element.ownerDocument.defaultView.Element &&
					object.element.parentNode !== null
				) {

					object.element.remove();

				}

			} );

		} );

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.element = source.element.cloneNode( true );

		return this;

	}

}
```
</details>

#### Methods

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		this.element = source.element.cloneNode( true );

		return this;

	}
```
</details>

### `CSS3DSprite`

<details><summary>Class Code</summary>

```ts
class CSS3DSprite extends CSS3DObject {

	/**
	 * Constructs a new CSS3D sprite object.
	 *
	 * @param {DOMElement} [element] - The DOM element.
	 */
	constructor( element ) {

		super( element );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCSS3DSprite = true;

		/**
		 * The sprite's rotation in radians.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.rotation2D = 0;

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.rotation2D = source.rotation2D;

		return this;

	}

}
```
</details>

#### Methods

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		this.rotation2D = source.rotation2D;

		return this;

	}
```
</details>

### `CSS3DRenderer`

<details><summary>Class Code</summary>

```ts
class CSS3DRenderer {

	/**
	 * Constructs a new CSS3D renderer.
	 *
	 * @param {CSS3DRenderer~Parameters} [parameters] - The parameters.
	 */
	constructor( parameters = {} ) {

		const _this = this;

		let _width, _height;
		let _widthHalf, _heightHalf;

		const cache = {
			camera: { style: '' },
			objects: new WeakMap()
		};

		const domElement = parameters.element !== undefined ? parameters.element : document.createElement( 'div' );

		domElement.style.overflow = 'hidden';

		/**
		 * The DOM where the renderer appends its child-elements.
		 *
		 * @type {DOMElement}
		 */
		this.domElement = domElement;

		const viewElement = document.createElement( 'div' );
		viewElement.style.transformOrigin = '0 0';
		viewElement.style.pointerEvents = 'none';
		domElement.appendChild( viewElement );

		const cameraElement = document.createElement( 'div' );

		cameraElement.style.transformStyle = 'preserve-3d';

		viewElement.appendChild( cameraElement );

		/**
		 * Returns an object containing the width and height of the renderer.
		 *
		 * @return {{width:number,height:number}} The size of the renderer.
		 */
		this.getSize = function () {

			return {
				width: _width,
				height: _height
			};

		};

		/**
		 * Renders the given scene using the given camera.
		 *
		 * @param {Object3D} scene - A scene or any other type of 3D object.
		 * @param {Camera} camera - The camera.
		 */
		this.render = function ( scene, camera ) {

			const fov = camera.projectionMatrix.elements[ 5 ] * _heightHalf;

			if ( camera.view && camera.view.enabled ) {

				// view offset
				viewElement.style.transform = `translate( ${ - camera.view.offsetX * ( _width / camera.view.width ) }px, ${ - camera.view.offsetY * ( _height / camera.view.height ) }px )`;

				// view fullWidth and fullHeight, view width and height
				viewElement.style.transform += `scale( ${ camera.view.fullWidth / camera.view.width }, ${ camera.view.fullHeight / camera.view.height } )`;

			} else {

				viewElement.style.transform = '';

			}

			if ( scene.matrixWorldAutoUpdate === true ) scene.updateMatrixWorld();
			if ( camera.parent === null && camera.matrixWorldAutoUpdate === true ) camera.updateMatrixWorld();

			let tx, ty;

			if ( camera.isOrthographicCamera ) {

				tx = - ( camera.right + camera.left ) / 2;
				ty = ( camera.top + camera.bottom ) / 2;

			}

			const scaleByViewOffset = camera.view && camera.view.enabled ? camera.view.height / camera.view.fullHeight : 1;
			const cameraCSSMatrix = camera.isOrthographicCamera ?
				`scale( ${ scaleByViewOffset } )` + 'scale(' + fov + ')' + 'translate(' + epsilon( tx ) + 'px,' + epsilon( ty ) + 'px)' + getCameraCSSMatrix( camera.matrixWorldInverse ) :
				`scale( ${ scaleByViewOffset } )` + 'translateZ(' + fov + 'px)' + getCameraCSSMatrix( camera.matrixWorldInverse );
			const perspective = camera.isPerspectiveCamera ? 'perspective(' + fov + 'px) ' : '';

			const style = perspective + cameraCSSMatrix +
				'translate(' + _widthHalf + 'px,' + _heightHalf + 'px)';

			if ( cache.camera.style !== style ) {

				cameraElement.style.transform = style;

				cache.camera.style = style;

			}

			renderObject( scene, scene, camera, cameraCSSMatrix );

		};

		/**
		 * Resizes the renderer to the given width and height.
		 *
		 * @param {number} width - The width of the renderer.
		 * @param {number} height - The height of the renderer.
		 */
		this.setSize = function ( width, height ) {

			_width = width;
			_height = height;
			_widthHalf = _width / 2;
			_heightHalf = _height / 2;

			domElement.style.width = width + 'px';
			domElement.style.height = height + 'px';

			viewElement.style.width = width + 'px';
			viewElement.style.height = height + 'px';

			cameraElement.style.width = width + 'px';
			cameraElement.style.height = height + 'px';

		};

		function epsilon( value ) {

			return Math.abs( value ) < 1e-10 ? 0 : value;

		}

		function getCameraCSSMatrix( matrix ) {

			const elements = matrix.elements;

			return 'matrix3d(' +
				epsilon( elements[ 0 ] ) + ',' +
				epsilon( - elements[ 1 ] ) + ',' +
				epsilon( elements[ 2 ] ) + ',' +
				epsilon( elements[ 3 ] ) + ',' +
				epsilon( elements[ 4 ] ) + ',' +
				epsilon( - elements[ 5 ] ) + ',' +
				epsilon( elements[ 6 ] ) + ',' +
				epsilon( elements[ 7 ] ) + ',' +
				epsilon( elements[ 8 ] ) + ',' +
				epsilon( - elements[ 9 ] ) + ',' +
				epsilon( elements[ 10 ] ) + ',' +
				epsilon( elements[ 11 ] ) + ',' +
				epsilon( elements[ 12 ] ) + ',' +
				epsilon( - elements[ 13 ] ) + ',' +
				epsilon( elements[ 14 ] ) + ',' +
				epsilon( elements[ 15 ] ) +
			')';

		}

		function getObjectCSSMatrix( matrix ) {

			const elements = matrix.elements;
			const matrix3d = 'matrix3d(' +
				epsilon( elements[ 0 ] ) + ',' +
				epsilon( elements[ 1 ] ) + ',' +
				epsilon( elements[ 2 ] ) + ',' +
				epsilon( elements[ 3 ] ) + ',' +
				epsilon( - elements[ 4 ] ) + ',' +
				epsilon( - elements[ 5 ] ) + ',' +
				epsilon( - elements[ 6 ] ) + ',' +
				epsilon( - elements[ 7 ] ) + ',' +
				epsilon( elements[ 8 ] ) + ',' +
				epsilon( elements[ 9 ] ) + ',' +
				epsilon( elements[ 10 ] ) + ',' +
				epsilon( elements[ 11 ] ) + ',' +
				epsilon( elements[ 12 ] ) + ',' +
				epsilon( elements[ 13 ] ) + ',' +
				epsilon( elements[ 14 ] ) + ',' +
				epsilon( elements[ 15 ] ) +
			')';

			return 'translate(-50%,-50%)' + matrix3d;

		}

		function hideObject( object ) {

			if ( object.isCSS3DObject ) object.element.style.display = 'none';

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				hideObject( object.children[ i ] );

			}

		}

		function renderObject( object, scene, camera, cameraCSSMatrix ) {

			if ( object.visible === false ) {

				hideObject( object );

				return;

			}

			if ( object.isCSS3DObject ) {

				const visible = ( object.layers.test( camera.layers ) === true );

				const element = object.element;
				element.style.display = visible === true ? '' : 'none';

				if ( visible === true ) {

					object.onBeforeRender( _this, scene, camera );

					let style;

					if ( object.isCSS3DSprite ) {

						// http://swiftcoder.wordpress.com/2008/11/25/constructing-a-billboard-matrix/

						_matrix.copy( camera.matrixWorldInverse );
						_matrix.transpose();

						if ( object.rotation2D !== 0 ) _matrix.multiply( _matrix2.makeRotationZ( object.rotation2D ) );

						object.matrixWorld.decompose( _position, _quaternion, _scale );
						_matrix.setPosition( _position );
						_matrix.scale( _scale );

						_matrix.elements[ 3 ] = 0;
						_matrix.elements[ 7 ] = 0;
						_matrix.elements[ 11 ] = 0;
						_matrix.elements[ 15 ] = 1;

						style = getObjectCSSMatrix( _matrix );

					} else {

						style = getObjectCSSMatrix( object.matrixWorld );

					}

					const cachedObject = cache.objects.get( object );

					if ( cachedObject === undefined || cachedObject.style !== style ) {

						element.style.transform = style;

						const objectData = { style: style };
						cache.objects.set( object, objectData );

					}

					if ( element.parentNode !== cameraElement ) {

						cameraElement.appendChild( element );

					}

					object.onAfterRender( _this, scene, camera );

				}

			}

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				renderObject( object.children[ i ], scene, camera, cameraCSSMatrix );

			}

		}

	}

}
```
</details>


---