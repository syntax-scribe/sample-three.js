[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CSS2DRenderer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 2 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 19 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/renderers/CSS2DRenderer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix4` | `three` |
| `Object3D` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector` | `any` | let/var | `new Vector3()` | ✗ |
| `_viewMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_viewProjectionMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_a` | `any` | let/var | `new Vector3()` | ✗ |
| `_b` | `any` | let/var | `new Vector3()` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `_width` | `any` | let/var | `*not shown*` | ✗ |
| `_height` | `any` | let/var | `*not shown*` | ✗ |
| `_widthHalf` | `any` | let/var | `*not shown*` | ✗ |
| `_heightHalf` | `any` | let/var | `*not shown*` | ✗ |
| `cache` | `{ objects: WeakMap<WeakKey, any>; }` | let/var | `{ objects: new WeakMap() }` | ✗ |
| `domElement` | `any` | let/var | `parameters.element !== undefined ? parameters.element : document.createElemen...` | ✗ |
| `visible` | `boolean` | let/var | `( _vector.z >= - 1 && _vector.z <= 1 ) && ( object.layers.test( camera.layers...` | ✗ |
| `element` | `any` | let/var | `object.element` | ✗ |
| `objectData` | `{ distanceToCameraSquared: any; }` | let/var | `{ distanceToCameraSquared: getDistanceToSquared( camera, object ) }` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `distanceA` | `any` | let/var | `cache.objects.get( a ).distanceToCameraSquared` | ✗ |
| `distanceB` | `any` | let/var | `cache.objects.get( b ).distanceToCameraSquared` | ✗ |
| `zMax` | `number` | let/var | `sorted.length` | ✗ |


---

## Functions

### `CSS2DObject.copy(source: any, recursive: any): this`

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

		this.center = source.center;

		return this;

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

			if ( object.isCSS2DObject ) object.element.style.display = 'none';

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				hideObject( object.children[ i ] );

			}

		}
```
</details>

### `renderObject(object: any, scene: any, camera: any): void`

**Parameters:**

- **`object`** `any`
- **`scene`** `any`
- **`camera`** `any`

**Returns:** `void`

**Calls:**

- `hideObject`
- `_vector.setFromMatrixPosition`
- `_vector.applyMatrix4`
- `object.layers.test`
- `object.onBeforeRender`
- `domElement.appendChild`
- `object.onAfterRender`
- `getDistanceToSquared`
- `cache.objects.set`
- `renderObject`

<details><summary>Code</summary>

```typescript
function renderObject( object, scene, camera ) {

			if ( object.visible === false ) {

				hideObject( object );

				return;

			}

			if ( object.isCSS2DObject ) {

				_vector.setFromMatrixPosition( object.matrixWorld );
				_vector.applyMatrix4( _viewProjectionMatrix );

				const visible = ( _vector.z >= - 1 && _vector.z <= 1 ) && ( object.layers.test( camera.layers ) === true );

				const element = object.element;
				element.style.display = visible === true ? '' : 'none';

				if ( visible === true ) {

					object.onBeforeRender( _this, scene, camera );

					element.style.transform = 'translate(' + ( - 100 * object.center.x ) + '%,' + ( - 100 * object.center.y ) + '%)' + 'translate(' + ( _vector.x * _widthHalf + _widthHalf ) + 'px,' + ( - _vector.y * _heightHalf + _heightHalf ) + 'px)';

					if ( element.parentNode !== domElement ) {

						domElement.appendChild( element );

					}

					object.onAfterRender( _this, scene, camera );

				}

				const objectData = {
					distanceToCameraSquared: getDistanceToSquared( camera, object )
				};

				cache.objects.set( object, objectData );

			}

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				renderObject( object.children[ i ], scene, camera );

			}

		}
```
</details>

### `getDistanceToSquared(object1: any, object2: any): any`

**Parameters:**

- **`object1`** `any`
- **`object2`** `any`

**Returns:** `any`

**Calls:**

- `_a.setFromMatrixPosition`
- `_b.setFromMatrixPosition`
- `_a.distanceToSquared`

<details><summary>Code</summary>

```typescript
function getDistanceToSquared( object1, object2 ) {

			_a.setFromMatrixPosition( object1.matrixWorld );
			_b.setFromMatrixPosition( object2.matrixWorld );

			return _a.distanceToSquared( _b );

		}
```
</details>

### `filterAndFlatten(scene: any): any[]`

**Parameters:**

- **`scene`** `any`

**Returns:** `any[]`

**Calls:**

- `scene.traverseVisible`
- `result.push`

<details><summary>Code</summary>

```typescript
function filterAndFlatten( scene ) {

			const result = [];

			scene.traverseVisible( function ( object ) {

				if ( object.isCSS2DObject ) result.push( object );

			} );

			return result;

		}
```
</details>

### `zOrder(scene: any): void`

**Parameters:**

- **`scene`** `any`

**Returns:** `void`

**Calls:**

- `filterAndFlatten( scene ).sort`
- `cache.objects.get`

<details><summary>Code</summary>

```typescript
function zOrder( scene ) {

			const sorted = filterAndFlatten( scene ).sort( function ( a, b ) {

				if ( a.renderOrder !== b.renderOrder ) {

					return b.renderOrder - a.renderOrder;

				}

				const distanceA = cache.objects.get( a ).distanceToCameraSquared;
				const distanceB = cache.objects.get( b ).distanceToCameraSquared;

				return distanceA - distanceB;

			} );

			const zMax = sorted.length;

			for ( let i = 0, l = sorted.length; i < l; i ++ ) {

				sorted[ i ].element.style.zIndex = zMax - i;

			}

		}
```
</details>


---

## Classes

### `CSS2DObject`

<details><summary>Class Code</summary>

```ts
class CSS2DObject extends Object3D {

	/**
	 * Constructs a new CSS2D object.
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
		this.isCSS2DObject = true;

		/**
		 * The DOM element which defines the appearance of this 3D object.
		 *
		 * @type {DOMElement}
		 * @readonly
		 * @default true
		 */
		this.element = element;

		this.element.style.position = 'absolute';
		this.element.style.userSelect = 'none';

		this.element.setAttribute( 'draggable', false );

		/**
		 * The 3D objects center point.
		 * `( 0, 0 )` is the lower left, `( 1, 1 )` is the top right.
		 *
		 * @type {Vector2}
		 * @default (0.5,0.5)
		 */
		this.center = new Vector2( 0.5, 0.5 );

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

		this.center = source.center;

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

		this.center = source.center;

		return this;

	}
```
</details>

### `CSS2DRenderer`

<details><summary>Class Code</summary>

```ts
class CSS2DRenderer {

	/**
	 * Constructs a new CSS2D renderer.
	 *
	 * @param {CSS2DRenderer~Parameters} [parameters] - The parameters.
	 */
	constructor( parameters = {} ) {

		const _this = this;

		let _width, _height;
		let _widthHalf, _heightHalf;

		const cache = {
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

			if ( scene.matrixWorldAutoUpdate === true ) scene.updateMatrixWorld();
			if ( camera.parent === null && camera.matrixWorldAutoUpdate === true ) camera.updateMatrixWorld();

			_viewMatrix.copy( camera.matrixWorldInverse );
			_viewProjectionMatrix.multiplyMatrices( camera.projectionMatrix, _viewMatrix );

			renderObject( scene, scene, camera );
			zOrder( scene );

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

		};

		function hideObject( object ) {

			if ( object.isCSS2DObject ) object.element.style.display = 'none';

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				hideObject( object.children[ i ] );

			}

		}

		function renderObject( object, scene, camera ) {

			if ( object.visible === false ) {

				hideObject( object );

				return;

			}

			if ( object.isCSS2DObject ) {

				_vector.setFromMatrixPosition( object.matrixWorld );
				_vector.applyMatrix4( _viewProjectionMatrix );

				const visible = ( _vector.z >= - 1 && _vector.z <= 1 ) && ( object.layers.test( camera.layers ) === true );

				const element = object.element;
				element.style.display = visible === true ? '' : 'none';

				if ( visible === true ) {

					object.onBeforeRender( _this, scene, camera );

					element.style.transform = 'translate(' + ( - 100 * object.center.x ) + '%,' + ( - 100 * object.center.y ) + '%)' + 'translate(' + ( _vector.x * _widthHalf + _widthHalf ) + 'px,' + ( - _vector.y * _heightHalf + _heightHalf ) + 'px)';

					if ( element.parentNode !== domElement ) {

						domElement.appendChild( element );

					}

					object.onAfterRender( _this, scene, camera );

				}

				const objectData = {
					distanceToCameraSquared: getDistanceToSquared( camera, object )
				};

				cache.objects.set( object, objectData );

			}

			for ( let i = 0, l = object.children.length; i < l; i ++ ) {

				renderObject( object.children[ i ], scene, camera );

			}

		}

		function getDistanceToSquared( object1, object2 ) {

			_a.setFromMatrixPosition( object1.matrixWorld );
			_b.setFromMatrixPosition( object2.matrixWorld );

			return _a.distanceToSquared( _b );

		}

		function filterAndFlatten( scene ) {

			const result = [];

			scene.traverseVisible( function ( object ) {

				if ( object.isCSS2DObject ) result.push( object );

			} );

			return result;

		}

		function zOrder( scene ) {

			const sorted = filterAndFlatten( scene ).sort( function ( a, b ) {

				if ( a.renderOrder !== b.renderOrder ) {

					return b.renderOrder - a.renderOrder;

				}

				const distanceA = cache.objects.get( a ).distanceToCameraSquared;
				const distanceB = cache.objects.get( b ).distanceToCameraSquared;

				return distanceA - distanceB;

			} );

			const zMax = sorted.length;

			for ( let i = 0, l = sorted.length; i < l; i ++ ) {

				sorted[ i ].element.style.zIndex = zMax - i;

			}

		}

	}

}
```
</details>


---