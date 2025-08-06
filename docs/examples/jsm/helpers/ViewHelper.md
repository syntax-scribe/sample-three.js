[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ViewHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 16 |
| 📊 Variables & Constants | 36 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/ViewHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CylinderGeometry` | `three` |
| `CanvasTexture` | `three` |
| `Color` | `three` |
| `Euler` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `Object3D` | `three` |
| `OrthographicCamera` | `three` |
| `Quaternion` | `three` |
| `Raycaster` | `three` |
| `Sprite` | `three` |
| `SpriteMaterial` | `three` |
| `SRGBColorSpace` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |
| `Vector4` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `color1` | `any` | let/var | `new Color( '#ff4466' )` | ✗ |
| `color2` | `any` | let/var | `new Color( '#88ff44' )` | ✗ |
| `color3` | `any` | let/var | `new Color( '#4488ff' )` | ✗ |
| `color4` | `any` | let/var | `new Color( '#000000' )` | ✗ |
| `options` | `{}` | let/var | `{}` | ✗ |
| `interactiveObjects` | `any[]` | let/var | `[]` | ✗ |
| `raycaster` | `any` | let/var | `new Raycaster()` | ✗ |
| `mouse` | `any` | let/var | `new Vector2()` | ✗ |
| `dummy` | `any` | let/var | `new Object3D()` | ✗ |
| `orthoCamera` | `any` | let/var | `new OrthographicCamera( - 2, 2, 2, - 2, 0, 4 )` | ✗ |
| `xAxis` | `any` | let/var | `new Mesh( geometry, getAxisMaterial( color1 ) )` | ✗ |
| `yAxis` | `any` | let/var | `new Mesh( geometry, getAxisMaterial( color2 ) )` | ✗ |
| `zAxis` | `any` | let/var | `new Mesh( geometry, getAxisMaterial( color3 ) )` | ✗ |
| `posXAxisHelper` | `any` | let/var | `new Sprite( spriteMaterial1 )` | ✗ |
| `posYAxisHelper` | `any` | let/var | `new Sprite( spriteMaterial2 )` | ✗ |
| `posZAxisHelper` | `any` | let/var | `new Sprite( spriteMaterial3 )` | ✗ |
| `negXAxisHelper` | `any` | let/var | `new Sprite( spriteMaterial4 )` | ✗ |
| `negYAxisHelper` | `any` | let/var | `new Sprite( spriteMaterial4 )` | ✗ |
| `negZAxisHelper` | `any` | let/var | `new Sprite( spriteMaterial4 )` | ✗ |
| `point` | `any` | let/var | `new Vector3()` | ✗ |
| `dim` | `128` | let/var | `128` | ✗ |
| `turnRate` | `number` | let/var | `2 * Math.PI` | ✗ |
| `x` | `number` | let/var | `domElement.offsetWidth - dim` | ✗ |
| `y` | `number` | let/var | `renderer.isWebGPURenderer ? domElement.offsetHeight - dim : 0` | ✗ |
| `targetPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `targetQuaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `q1` | `any` | let/var | `new Quaternion()` | ✗ |
| `q2` | `any` | let/var | `new Quaternion()` | ✗ |
| `viewport` | `any` | let/var | `new Vector4()` | ✗ |
| `radius` | `number` | let/var | `0` | ✗ |
| `offsetX` | `any` | let/var | `rect.left + ( domElement.offsetWidth - dim )` | ✗ |
| `offsetY` | `any` | let/var | `rect.top + ( domElement.offsetHeight - dim )` | ✗ |
| `intersection` | `any` | let/var | `intersects[ 0 ]` | ✗ |
| `object` | `any` | let/var | `intersection.object` | ✗ |
| `step` | `number` | let/var | `delta * turnRate` | ✗ |
| `texture` | `any` | let/var | `new CanvasTexture( canvas )` | ✗ |


---

## Functions

### `prepareAnimationData(object: any, focusPoint: any): void`

**Parameters:**

- **`object`** `any`
- **`focusPoint`** `any`

**Returns:** `void`

**Calls:**

- `targetPosition.set`
- `targetQuaternion.setFromEuler`
- `console.error`
- `camera.position.distanceTo`
- `targetPosition.multiplyScalar( radius ).add`
- `dummy.position.copy`
- `dummy.lookAt`
- `q1.copy`
- `q2.copy`

**Internal Comments:**
```
// (x3)
```

<details><summary>Code</summary>

```typescript
function prepareAnimationData( object, focusPoint ) {

			switch ( object.userData.type ) {

				case 'posX':
					targetPosition.set( 1, 0, 0 );
					targetQuaternion.setFromEuler( new Euler( 0, Math.PI * 0.5, 0 ) );
					break;

				case 'posY':
					targetPosition.set( 0, 1, 0 );
					targetQuaternion.setFromEuler( new Euler( - Math.PI * 0.5, 0, 0 ) );
					break;

				case 'posZ':
					targetPosition.set( 0, 0, 1 );
					targetQuaternion.setFromEuler( new Euler() );
					break;

				case 'negX':
					targetPosition.set( - 1, 0, 0 );
					targetQuaternion.setFromEuler( new Euler( 0, - Math.PI * 0.5, 0 ) );
					break;

				case 'negY':
					targetPosition.set( 0, - 1, 0 );
					targetQuaternion.setFromEuler( new Euler( Math.PI * 0.5, 0, 0 ) );
					break;

				case 'negZ':
					targetPosition.set( 0, 0, - 1 );
					targetQuaternion.setFromEuler( new Euler( 0, Math.PI, 0 ) );
					break;

				default:
					console.error( 'ViewHelper: Invalid axis.' );

			}

			//

			radius = camera.position.distanceTo( focusPoint );
			targetPosition.multiplyScalar( radius ).add( focusPoint );

			dummy.position.copy( focusPoint );

			dummy.lookAt( camera.position );
			q1.copy( dummy.quaternion );

			dummy.lookAt( targetPosition );
			q2.copy( dummy.quaternion );

		}
```
</details>

### `getAxisMaterial(color: any): any`

**Parameters:**

- **`color`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getAxisMaterial( color ) {

			return new MeshBasicMaterial( { color: color, toneMapped: false } );

		}
```
</details>

### `getSpriteMaterial(color: any, text: any): any`

**Parameters:**

- **`color`** `any`
- **`text`** `any`

**Returns:** `any`

**Calls:**

- `document.createElement`
- `canvas.getContext`
- `context.beginPath`
- `context.arc`
- `context.closePath`
- `color.getStyle`
- `context.fill`
- `context.fillText`

<details><summary>Code</summary>

```typescript
function getSpriteMaterial( color, text ) {

			const { font = '24px Arial', color: labelColor = '#000000', radius = 14 } = options;

			const canvas = document.createElement( 'canvas' );
			canvas.width = 64;
			canvas.height = 64;

			const context = canvas.getContext( '2d' );
			context.beginPath();
			context.arc( 32, 32, radius, 0, 2 * Math.PI );
			context.closePath();
			context.fillStyle = color.getStyle();
			context.fill();

			if ( text ) {

				context.font = font;
				context.textAlign = 'center';
				context.fillStyle = labelColor;
				context.fillText( text, 32, 41 );

			}

			const texture = new CanvasTexture( canvas );
			texture.colorSpace = SRGBColorSpace;

			return new SpriteMaterial( { map: texture, toneMapped: false } );

		}
```
</details>

### `updateLabels(): void`

**Returns:** `void`

**Calls:**

- `posXAxisHelper.material.map.dispose`
- `posYAxisHelper.material.map.dispose`
- `posZAxisHelper.material.map.dispose`
- `posXAxisHelper.material.dispose`
- `posYAxisHelper.material.dispose`
- `posZAxisHelper.material.dispose`
- `getSpriteMaterial`

<details><summary>Code</summary>

```typescript
function updateLabels() {

			posXAxisHelper.material.map.dispose();
			posYAxisHelper.material.map.dispose();
			posZAxisHelper.material.map.dispose();

			posXAxisHelper.material.dispose();
			posYAxisHelper.material.dispose();
			posZAxisHelper.material.dispose();

			posXAxisHelper.material = getSpriteMaterial( color1, options.labelX );
			posYAxisHelper.material = getSpriteMaterial( color2, options.labelY );
			posZAxisHelper.material = getSpriteMaterial( color3, options.labelZ );

		}
```
</details>


---

## Classes

### `ViewHelper`

<details><summary>Class Code</summary>

```ts
class ViewHelper extends Object3D {

	/**
	 * Constructs a new view helper.
	 *
	 * @param {Camera} camera - The camera whose transformation should be visualized.
	 * @param {HTMLDOMElement} [domElement] - The DOM element that is used to render the view.
	 */
	constructor( camera, domElement ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isViewHelper = true;

		/**
		 * Whether the helper is currently animating or not.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default false
		 */
		this.animating = false;

		/**
		 * The helper's center point.
		 *
		 * @type {Vector3}
		 */
		this.center = new Vector3();

		const color1 = new Color( '#ff4466' );
		const color2 = new Color( '#88ff44' );
		const color3 = new Color( '#4488ff' );
		const color4 = new Color( '#000000' );

		const options = {};

		const interactiveObjects = [];
		const raycaster = new Raycaster();
		const mouse = new Vector2();
		const dummy = new Object3D();

		const orthoCamera = new OrthographicCamera( - 2, 2, 2, - 2, 0, 4 );
		orthoCamera.position.set( 0, 0, 2 );

		const geometry = new CylinderGeometry( 0.04, 0.04, 0.8, 5 ).rotateZ( - Math.PI / 2 ).translate( 0.4, 0, 0 );

		const xAxis = new Mesh( geometry, getAxisMaterial( color1 ) );
		const yAxis = new Mesh( geometry, getAxisMaterial( color2 ) );
		const zAxis = new Mesh( geometry, getAxisMaterial( color3 ) );

		yAxis.rotation.z = Math.PI / 2;
		zAxis.rotation.y = - Math.PI / 2;

		this.add( xAxis );
		this.add( zAxis );
		this.add( yAxis );

		const spriteMaterial1 = getSpriteMaterial( color1 );
		const spriteMaterial2 = getSpriteMaterial( color2 );
		const spriteMaterial3 = getSpriteMaterial( color3 );
		const spriteMaterial4 = getSpriteMaterial( color4 );

		const posXAxisHelper = new Sprite( spriteMaterial1 );
		const posYAxisHelper = new Sprite( spriteMaterial2 );
		const posZAxisHelper = new Sprite( spriteMaterial3 );
		const negXAxisHelper = new Sprite( spriteMaterial4 );
		const negYAxisHelper = new Sprite( spriteMaterial4 );
		const negZAxisHelper = new Sprite( spriteMaterial4 );

		posXAxisHelper.position.x = 1;
		posYAxisHelper.position.y = 1;
		posZAxisHelper.position.z = 1;
		negXAxisHelper.position.x = - 1;
		negYAxisHelper.position.y = - 1;
		negZAxisHelper.position.z = - 1;

		negXAxisHelper.material.opacity = 0.2;
		negYAxisHelper.material.opacity = 0.2;
		negZAxisHelper.material.opacity = 0.2;

		posXAxisHelper.userData.type = 'posX';
		posYAxisHelper.userData.type = 'posY';
		posZAxisHelper.userData.type = 'posZ';
		negXAxisHelper.userData.type = 'negX';
		negYAxisHelper.userData.type = 'negY';
		negZAxisHelper.userData.type = 'negZ';

		this.add( posXAxisHelper );
		this.add( posYAxisHelper );
		this.add( posZAxisHelper );
		this.add( negXAxisHelper );
		this.add( negYAxisHelper );
		this.add( negZAxisHelper );

		interactiveObjects.push( posXAxisHelper );
		interactiveObjects.push( posYAxisHelper );
		interactiveObjects.push( posZAxisHelper );
		interactiveObjects.push( negXAxisHelper );
		interactiveObjects.push( negYAxisHelper );
		interactiveObjects.push( negZAxisHelper );

		const point = new Vector3();
		const dim = 128;
		const turnRate = 2 * Math.PI; // turn rate in angles per second

		/**
		 * Renders the helper in a separate view in the bottom-right corner
		 * of the viewport.
		 *
		 * @param {WebGLRenderer|WebGPURenderer} renderer - The renderer.
		 */
		this.render = function ( renderer ) {

			this.quaternion.copy( camera.quaternion ).invert();
			this.updateMatrixWorld();

			point.set( 0, 0, 1 );
			point.applyQuaternion( camera.quaternion );

			//

			const x = domElement.offsetWidth - dim;
			const y = renderer.isWebGPURenderer ? domElement.offsetHeight - dim : 0;

			renderer.clearDepth();

			renderer.getViewport( viewport );
			renderer.setViewport( x, y, dim, dim );

			renderer.render( this, orthoCamera );

			renderer.setViewport( viewport.x, viewport.y, viewport.z, viewport.w );

		};

		const targetPosition = new Vector3();
		const targetQuaternion = new Quaternion();

		const q1 = new Quaternion();
		const q2 = new Quaternion();
		const viewport = new Vector4();
		let radius = 0;

		/**
		 * This method should be called when a click or pointer event
		 * has happened in the app.
		 *
		 * @param {PointerEvent} event - The event to process.
		 * @return {boolean} Whether an intersection with the helper has been detected or not.
		 */
		this.handleClick = function ( event ) {

			if ( this.animating === true ) return false;

			const rect = domElement.getBoundingClientRect();
			const offsetX = rect.left + ( domElement.offsetWidth - dim );
			const offsetY = rect.top + ( domElement.offsetHeight - dim );
			mouse.x = ( ( event.clientX - offsetX ) / ( rect.right - offsetX ) ) * 2 - 1;
			mouse.y = - ( ( event.clientY - offsetY ) / ( rect.bottom - offsetY ) ) * 2 + 1;

			raycaster.setFromCamera( mouse, orthoCamera );

			const intersects = raycaster.intersectObjects( interactiveObjects );

			if ( intersects.length > 0 ) {

				const intersection = intersects[ 0 ];
				const object = intersection.object;

				prepareAnimationData( object, this.center );

				this.animating = true;

				return true;

			} else {

				return false;

			}

		};

		/**
		 * Sets labels for each axis. By default, they are unlabeled.
		 *
		 * @param {string|undefined} labelX - The label for the x-axis.
		 * @param {string|undefined} labelY - The label for the y-axis.
		 * @param {string|undefined} labelZ - The label for the z-axis.
		 */
		this.setLabels = function ( labelX, labelY, labelZ ) {

			options.labelX = labelX;
			options.labelY = labelY;
			options.labelZ = labelZ;

			updateLabels();

		};

		/**
		 * Sets the label style. Has no effect when the axes are unlabeled.
		 *
		 * @param {string} [font='24px Arial'] - The label font.
		 * @param {string} [color='#000000'] - The label color.
		 * @param {number} [radius=14] - The label radius.
		 */
		this.setLabelStyle = function ( font, color, radius ) {

			options.font = font;
			options.color = color;
			options.radius = radius;

			updateLabels();

		};

		/**
		 * Updates the helper. This method should be called in the app's animation
		 * loop.
		 *
		 * @param {number} delta - The delta time in seconds.
		 */
		this.update = function ( delta ) {

			const step = delta * turnRate;

			// animate position by doing a slerp and then scaling the position on the unit sphere

			q1.rotateTowards( q2, step );
			camera.position.set( 0, 0, 1 ).applyQuaternion( q1 ).multiplyScalar( radius ).add( this.center );

			// animate orientation

			camera.quaternion.rotateTowards( targetQuaternion, step );

			if ( q1.angleTo( q2 ) === 0 ) {

				this.animating = false;

			}

		};

		/**
		 * Frees the GPU-related resources allocated by this instance. Call this
		 * method whenever this instance is no longer used in your app.
		 */
		this.dispose = function () {

			geometry.dispose();

			xAxis.material.dispose();
			yAxis.material.dispose();
			zAxis.material.dispose();

			posXAxisHelper.material.map.dispose();
			posYAxisHelper.material.map.dispose();
			posZAxisHelper.material.map.dispose();
			negXAxisHelper.material.map.dispose();
			negYAxisHelper.material.map.dispose();
			negZAxisHelper.material.map.dispose();

			posXAxisHelper.material.dispose();
			posYAxisHelper.material.dispose();
			posZAxisHelper.material.dispose();
			negXAxisHelper.material.dispose();
			negYAxisHelper.material.dispose();
			negZAxisHelper.material.dispose();

		};

		function prepareAnimationData( object, focusPoint ) {

			switch ( object.userData.type ) {

				case 'posX':
					targetPosition.set( 1, 0, 0 );
					targetQuaternion.setFromEuler( new Euler( 0, Math.PI * 0.5, 0 ) );
					break;

				case 'posY':
					targetPosition.set( 0, 1, 0 );
					targetQuaternion.setFromEuler( new Euler( - Math.PI * 0.5, 0, 0 ) );
					break;

				case 'posZ':
					targetPosition.set( 0, 0, 1 );
					targetQuaternion.setFromEuler( new Euler() );
					break;

				case 'negX':
					targetPosition.set( - 1, 0, 0 );
					targetQuaternion.setFromEuler( new Euler( 0, - Math.PI * 0.5, 0 ) );
					break;

				case 'negY':
					targetPosition.set( 0, - 1, 0 );
					targetQuaternion.setFromEuler( new Euler( Math.PI * 0.5, 0, 0 ) );
					break;

				case 'negZ':
					targetPosition.set( 0, 0, - 1 );
					targetQuaternion.setFromEuler( new Euler( 0, Math.PI, 0 ) );
					break;

				default:
					console.error( 'ViewHelper: Invalid axis.' );

			}

			//

			radius = camera.position.distanceTo( focusPoint );
			targetPosition.multiplyScalar( radius ).add( focusPoint );

			dummy.position.copy( focusPoint );

			dummy.lookAt( camera.position );
			q1.copy( dummy.quaternion );

			dummy.lookAt( targetPosition );
			q2.copy( dummy.quaternion );

		}

		function getAxisMaterial( color ) {

			return new MeshBasicMaterial( { color: color, toneMapped: false } );

		}

		function getSpriteMaterial( color, text ) {

			const { font = '24px Arial', color: labelColor = '#000000', radius = 14 } = options;

			const canvas = document.createElement( 'canvas' );
			canvas.width = 64;
			canvas.height = 64;

			const context = canvas.getContext( '2d' );
			context.beginPath();
			context.arc( 32, 32, radius, 0, 2 * Math.PI );
			context.closePath();
			context.fillStyle = color.getStyle();
			context.fill();

			if ( text ) {

				context.font = font;
				context.textAlign = 'center';
				context.fillStyle = labelColor;
				context.fillText( text, 32, 41 );

			}

			const texture = new CanvasTexture( canvas );
			texture.colorSpace = SRGBColorSpace;

			return new SpriteMaterial( { map: texture, toneMapped: false } );

		}

		function updateLabels() {

			posXAxisHelper.material.map.dispose();
			posYAxisHelper.material.map.dispose();
			posZAxisHelper.material.map.dispose();

			posXAxisHelper.material.dispose();
			posYAxisHelper.material.dispose();
			posZAxisHelper.material.dispose();

			posXAxisHelper.material = getSpriteMaterial( color1, options.labelX );
			posYAxisHelper.material = getSpriteMaterial( color2, options.labelY );
			posZAxisHelper.material = getSpriteMaterial( color3, options.labelZ );

		}

	}

}
```
</details>


---