[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SVGRenderer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 2 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 55 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/renderers/SVGRenderer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box2` | `three` |
| `Camera` | `three` |
| `Color` | `three` |
| `Matrix3` | `three` |
| `Matrix4` | `three` |
| `Object3D` | `three` |
| `SRGBColorSpace` | `three` |
| `Vector3` | `three` |
| `Projector` | `../renderers/Projector.js` |
| `RenderableFace` | `../renderers/Projector.js` |
| `RenderableLine` | `../renderers/Projector.js` |
| `RenderableSprite` | `../renderers/Projector.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_renderData` | `any` | let/var | `*not shown*` | ✗ |
| `_elements` | `any` | let/var | `*not shown*` | ✗ |
| `_lights` | `any` | let/var | `*not shown*` | ✗ |
| `_svgWidth` | `any` | let/var | `*not shown*` | ✗ |
| `_svgHeight` | `any` | let/var | `*not shown*` | ✗ |
| `_svgWidthHalf` | `any` | let/var | `*not shown*` | ✗ |
| `_svgHeightHalf` | `any` | let/var | `*not shown*` | ✗ |
| `_v1` | `any` | let/var | `*not shown*` | ✗ |
| `_v2` | `any` | let/var | `*not shown*` | ✗ |
| `_v3` | `any` | let/var | `*not shown*` | ✗ |
| `_svgNode` | `any` | let/var | `*not shown*` | ✗ |
| `_pathCount` | `number` | let/var | `0` | ✗ |
| `_precision` | `any` | let/var | `null` | ✗ |
| `_quality` | `number` | let/var | `1` | ✗ |
| `_currentPath` | `any` | let/var | `*not shown*` | ✗ |
| `_currentStyle` | `any` | let/var | `*not shown*` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `_clipBox` | `any` | let/var | `new Box2()` | ✗ |
| `_elemBox` | `any` | let/var | `new Box2()` | ✗ |
| `_color` | `any` | let/var | `new Color()` | ✗ |
| `_diffuseColor` | `any` | let/var | `new Color()` | ✗ |
| `_ambientLight` | `any` | let/var | `new Color()` | ✗ |
| `_directionalLights` | `any` | let/var | `new Color()` | ✗ |
| `_pointLights` | `any` | let/var | `new Color()` | ✗ |
| `_clearColor` | `any` | let/var | `new Color()` | ✗ |
| `_vector3` | `any` | let/var | `new Vector3()` | ✗ |
| `_centroid` | `any` | let/var | `new Vector3()` | ✗ |
| `_normal` | `any` | let/var | `new Vector3()` | ✗ |
| `_normalViewMatrix` | `any` | let/var | `new Matrix3()` | ✗ |
| `_viewMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_viewProjectionMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_svgPathPool` | `any[]` | let/var | `[]` | ✗ |
| `_projector` | `Projector` | let/var | `new Projector()` | ✗ |
| `background` | `any` | let/var | `scene.background` | ✗ |
| `element` | `Objects` | let/var | `_elements[ e ]` | ✗ |
| `material` | `any` | let/var | `element.material` | ✗ |
| `x` | `number` | let/var | `_vector3.x * _svgWidthHalf` | ✗ |
| `y` | `number` | let/var | `- _vector3.y * _svgHeightHalf` | ✗ |
| `node` | `any` | let/var | `object.node` | ✗ |
| `light` | `any` | let/var | `lights[ l ]` | ✗ |
| `lightColor` | `any` | let/var | `light.color` | ✗ |
| `light` | `any` | let/var | `lights[ l ]` | ✗ |
| `lightColor` | `any` | let/var | `light.color` | ✗ |
| `scaleX` | `number` | let/var | `element.scale.x * _svgWidthHalf` | ✗ |
| `scaleY` | `number` | let/var | `element.scale.y * _svgHeightHalf` | ✗ |
| `path` | `string` | let/var | `'M' + convert( v1.x - scaleX * 0.5 ) + ',' + convert( v1.y - scaleY * 0.5 ) +...` | ✗ |
| `style` | `string` | let/var | `''` | ✗ |
| `path` | `string` | let/var | `'M' + convert( v1.positionScreen.x ) + ',' + convert( v1.positionScreen.y ) +...` | ✗ |
| `style` | `string` | let/var | `'fill:none;stroke:' + material.color.getStyle( _this.outputColorSpace ) + ';s...` | ✗ |
| `path` | `string` | let/var | `'M' + convert( v1.positionScreen.x ) + ',' + convert( v1.positionScreen.y ) +...` | ✗ |
| `style` | `string` | let/var | `''` | ✗ |
| `x` | `number` | let/var | `v2.x - v1.x` | ✗ |
| `y` | `number` | let/var | `v2.y - v1.y` | ✗ |
| `det` | `number` | let/var | `x * x + y * y` | ✗ |
| `idet` | `number` | let/var | `pixels / Math.sqrt( det )` | ✗ |


---

## Functions

### `removeChildNodes(): void`

**Returns:** `void`

**Calls:**

- `_svg.removeChild`

<details><summary>Code</summary>

```typescript
function removeChildNodes() {

			_pathCount = 0;

			while ( _svg.childNodes.length > 0 ) {

				_svg.removeChild( _svg.childNodes[ 0 ] );

			}

		}
```
</details>

### `convert(c: any): any`

**Parameters:**

- **`c`** `any`

**Returns:** `any`

**Calls:**

- `c.toFixed`

<details><summary>Code</summary>

```typescript
function convert( c ) {

			return _precision !== null ? c.toFixed( _precision ) : c;

		}
```
</details>

### `calculateLights(lights: any): void`

**Parameters:**

- **`lights`** `any`

**Returns:** `void`

**Calls:**

- `_ambientLight.setRGB`
- `_directionalLights.setRGB`
- `_pointLights.setRGB`

<details><summary>Code</summary>

```typescript
function calculateLights( lights ) {

			_ambientLight.setRGB( 0, 0, 0 );
			_directionalLights.setRGB( 0, 0, 0 );
			_pointLights.setRGB( 0, 0, 0 );

			for ( let l = 0, ll = lights.length; l < ll; l ++ ) {

				const light = lights[ l ];
				const lightColor = light.color;

				if ( light.isAmbientLight ) {

					_ambientLight.r += lightColor.r;
					_ambientLight.g += lightColor.g;
					_ambientLight.b += lightColor.b;

				} else if ( light.isDirectionalLight ) {

					_directionalLights.r += lightColor.r;
					_directionalLights.g += lightColor.g;
					_directionalLights.b += lightColor.b;

				} else if ( light.isPointLight ) {

					_pointLights.r += lightColor.r;
					_pointLights.g += lightColor.g;
					_pointLights.b += lightColor.b;

				}

			}

		}
```
</details>

### `calculateLight(lights: any, position: any, normal: any, color: any): void`

**Parameters:**

- **`lights`** `any`
- **`position`** `any`
- **`normal`** `any`
- **`color`** `any`

**Returns:** `void`

**Calls:**

- `_vector3.setFromMatrixPosition( light.matrixWorld ).normalize`
- `normal.dot`
- `_vector3.setFromMatrixPosition`
- `_vector3.subVectors( lightPosition, position ).normalize`
- `Math.min`
- `position.distanceTo`

<details><summary>Code</summary>

```typescript
function calculateLight( lights, position, normal, color ) {

			for ( let l = 0, ll = lights.length; l < ll; l ++ ) {

				const light = lights[ l ];
				const lightColor = light.color;

				if ( light.isDirectionalLight ) {

					const lightPosition = _vector3.setFromMatrixPosition( light.matrixWorld ).normalize();

					let amount = normal.dot( lightPosition );

					if ( amount <= 0 ) continue;

					amount *= light.intensity;

					color.r += lightColor.r * amount;
					color.g += lightColor.g * amount;
					color.b += lightColor.b * amount;

				} else if ( light.isPointLight ) {

					const lightPosition = _vector3.setFromMatrixPosition( light.matrixWorld );

					let amount = normal.dot( _vector3.subVectors( lightPosition, position ).normalize() );

					if ( amount <= 0 ) continue;

					amount *= light.distance == 0 ? 1 : 1 - Math.min( position.distanceTo( lightPosition ) / light.distance, 1 );

					if ( amount == 0 ) continue;

					amount *= light.intensity;

					color.r += lightColor.r * amount;
					color.g += lightColor.g * amount;
					color.b += lightColor.b * amount;

				}

			}

		}
```
</details>

### `renderSprite(v1: any, element: any, material: any): void`

**Parameters:**

- **`v1`** `any`
- **`element`** `any`
- **`material`** `any`

**Returns:** `void`

**Calls:**

- `convert`
- `material.color.getStyle`
- `addPath`

<details><summary>Code</summary>

```typescript
function renderSprite( v1, element, material ) {

			let scaleX = element.scale.x * _svgWidthHalf;
			let scaleY = element.scale.y * _svgHeightHalf;

			if ( material.isPointsMaterial ) {

				scaleX *= material.size;
				scaleY *= material.size;

			}

			const path = 'M' + convert( v1.x - scaleX * 0.5 ) + ',' + convert( v1.y - scaleY * 0.5 ) + 'h' + convert( scaleX ) + 'v' + convert( scaleY ) + 'h' + convert( - scaleX ) + 'z';
			let style = '';

			if ( material.isSpriteMaterial || material.isPointsMaterial ) {

				style = 'fill:' + material.color.getStyle( _this.outputColorSpace ) + ';fill-opacity:' + material.opacity;

			}

			addPath( style, path );

		}
```
</details>

### `renderLine(v1: any, v2: any, material: any): void`

**Parameters:**

- **`v1`** `any`
- **`v2`** `any`
- **`material`** `any`

**Returns:** `void`

**Calls:**

- `convert`
- `material.color.getStyle`
- `addPath`

<details><summary>Code</summary>

```typescript
function renderLine( v1, v2, material ) {

			const path = 'M' + convert( v1.positionScreen.x ) + ',' + convert( v1.positionScreen.y ) + 'L' + convert( v2.positionScreen.x ) + ',' + convert( v2.positionScreen.y );

			if ( material.isLineBasicMaterial ) {

				let style = 'fill:none;stroke:' + material.color.getStyle( _this.outputColorSpace ) + ';stroke-opacity:' + material.opacity + ';stroke-width:' + material.linewidth + ';stroke-linecap:' + material.linecap;

				if ( material.isLineDashedMaterial ) {

					style = style + ';stroke-dasharray:' + material.dashSize + ',' + material.gapSize;

				}

				addPath( style, path );

			}

		}
```
</details>

### `renderFace3(v1: any, v2: any, v3: any, element: any, material: any): void`

**Parameters:**

- **`v1`** `any`
- **`v2`** `any`
- **`v3`** `any`
- **`element`** `any`
- **`material`** `any`

**Returns:** `void`

**Calls:**

- `convert`
- `_color.copy`
- `_color.multiply`
- `_diffuseColor.copy`
- `_diffuseColor.multiply`
- `_centroid.copy( v1.positionWorld ).add( v2.positionWorld ).add( v3.positionWorld ).divideScalar`
- `calculateLight`
- `_color.multiply( _diffuseColor ).add`
- `_normal.copy( element.normalModel ).applyMatrix3( _normalViewMatrix ).normalize`
- `_color.setRGB( _normal.x, _normal.y, _normal.z ).multiplyScalar( 0.5 ).addScalar`
- `_color.getStyle`
- `addPath`

<details><summary>Code</summary>

```typescript
function renderFace3( v1, v2, v3, element, material ) {

			_this.info.render.vertices += 3;
			_this.info.render.faces ++;

			const path = 'M' + convert( v1.positionScreen.x ) + ',' + convert( v1.positionScreen.y ) + 'L' + convert( v2.positionScreen.x ) + ',' + convert( v2.positionScreen.y ) + 'L' + convert( v3.positionScreen.x ) + ',' + convert( v3.positionScreen.y ) + 'z';
			let style = '';

			if ( material.isMeshBasicMaterial ) {

				_color.copy( material.color );

				if ( material.vertexColors ) {

					_color.multiply( element.color );

				}

			} else if ( material.isMeshLambertMaterial || material.isMeshPhongMaterial || material.isMeshStandardMaterial ) {

				_diffuseColor.copy( material.color );

				if ( material.vertexColors ) {

					_diffuseColor.multiply( element.color );

				}

				_color.copy( _ambientLight );

				_centroid.copy( v1.positionWorld ).add( v2.positionWorld ).add( v3.positionWorld ).divideScalar( 3 );

				calculateLight( _lights, _centroid, element.normalModel, _color );

				_color.multiply( _diffuseColor ).add( material.emissive );

			} else if ( material.isMeshNormalMaterial ) {

				_normal.copy( element.normalModel ).applyMatrix3( _normalViewMatrix ).normalize();

				_color.setRGB( _normal.x, _normal.y, _normal.z ).multiplyScalar( 0.5 ).addScalar( 0.5 );

			}

			if ( material.wireframe ) {

				style = 'fill:none;stroke:' + _color.getStyle( _this.outputColorSpace ) + ';stroke-opacity:' + material.opacity + ';stroke-width:' + material.wireframeLinewidth + ';stroke-linecap:' + material.wireframeLinecap + ';stroke-linejoin:' + material.wireframeLinejoin;

			} else {

				style = 'fill:' + _color.getStyle( _this.outputColorSpace ) + ';fill-opacity:' + material.opacity;

			}

			addPath( style, path );

		}
```
</details>

### `expand(v1: any, v2: any, pixels: any): void`

**Parameters:**

- **`v1`** `any`
- **`v2`** `any`
- **`pixels`** `any`

**Returns:** `void`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function expand( v1, v2, pixels ) {

			let x = v2.x - v1.x, y = v2.y - v1.y;
			const det = x * x + y * y;

			if ( det === 0 ) return;

			const idet = pixels / Math.sqrt( det );

			x *= idet; y *= idet;

			v2.x += x; v2.y += y;
			v1.x -= x; v1.y -= y;

		}
```
</details>

### `addPath(style: any, path: any): void`

**Parameters:**

- **`style`** `any`
- **`path`** `any`

**Returns:** `void`

**Calls:**

- `flushPath`

<details><summary>Code</summary>

```typescript
function addPath( style, path ) {

			if ( _currentStyle === style ) {

				_currentPath += path;

			} else {

				flushPath();

				_currentStyle = style;
				_currentPath = path;

			}

		}
```
</details>

### `flushPath(): void`

**Returns:** `void`

**Calls:**

- `getPathNode`
- `_svgNode.setAttribute`
- `_svg.appendChild`

<details><summary>Code</summary>

```typescript
function flushPath() {

			if ( _currentPath ) {

				_svgNode = getPathNode( _pathCount ++ );
				_svgNode.setAttribute( 'd', _currentPath );
				_svgNode.setAttribute( 'style', _currentStyle );
				_svg.appendChild( _svgNode );

			}

			_currentPath = '';
			_currentStyle = '';

		}
```
</details>

### `getPathNode(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `document.createElementNS`
- `_svgPathPool[ id ].setAttribute`

<details><summary>Code</summary>

```typescript
function getPathNode( id ) {

			if ( _svgPathPool[ id ] == null ) {

				_svgPathPool[ id ] = document.createElementNS( 'http://www.w3.org/2000/svg', 'path' );

				if ( _quality == 0 ) {

					_svgPathPool[ id ].setAttribute( 'shape-rendering', 'crispEdges' ); //optimizeSpeed

				}

				return _svgPathPool[ id ];

			}

			return _svgPathPool[ id ];

		}
```
</details>


---

## Classes

### `SVGObject`

<details><summary>Class Code</summary>

```ts
class SVGObject extends Object3D {

	/**
	 * Constructs a new SVG object.
	 *
	 * @param {SVGElement} node - The SVG element.
	 */
	constructor( node ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSVGObject = true;

		/**
		 * This SVG element.
		 *
		 * @type {SVGElement}
		 */
		this.node = node;

	}

}
```
</details>

### `SVGRenderer`

<details><summary>Class Code</summary>

```ts
class SVGRenderer {

	/**
	 * Constructs a new SVG renderer.
	 */
	constructor() {

		let _renderData, _elements, _lights,
			_svgWidth, _svgHeight, _svgWidthHalf, _svgHeightHalf,

			_v1, _v2, _v3,

			_svgNode,
			_pathCount = 0,

			_precision = null,
			_quality = 1,

			_currentPath, _currentStyle;

		const _this = this,
			_clipBox = new Box2(),
			_elemBox = new Box2(),

			_color = new Color(),
			_diffuseColor = new Color(),
			_ambientLight = new Color(),
			_directionalLights = new Color(),
			_pointLights = new Color(),
			_clearColor = new Color(),

			_vector3 = new Vector3(), // Needed for PointLight
			_centroid = new Vector3(),
			_normal = new Vector3(),
			_normalViewMatrix = new Matrix3(),

			_viewMatrix = new Matrix4(),
			_viewProjectionMatrix = new Matrix4(),

			_svgPathPool = [],

			_projector = new Projector(),
			_svg = document.createElementNS( 'http://www.w3.org/2000/svg', 'svg' );

		/**
		 * The DOM where the renderer appends its child-elements.
		 *
		 * @type {DOMElement}
		 */
		this.domElement = _svg;

		/**
		 * Whether to automatically perform a clear before a render call or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.autoClear = true;

		/**
		 * Whether to sort 3D objects or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.sortObjects = true;

		/**
		 * Whether to sort elements or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.sortElements = true;

		/**
		 * Number of fractional pixels to enlarge polygons in order to
		 * prevent anti-aliasing gaps. Range is `[0,1]`.
		 *
		 * @type {number}
		 * @default 0.5
		 */
		this.overdraw = 0.5;

		/**
		 * The output color space.
		 *
		 * @type {(SRGBColorSpace|LinearSRGBColorSpace)}
		 * @default SRGBColorSpace
		 */
		this.outputColorSpace = SRGBColorSpace;

		/**
		 * Provides information about the number of
		 * rendered vertices and faces.
		 *
		 * @type {Object}
		 */
		this.info = {

			render: {

				vertices: 0,
				faces: 0

			}

		};

		/**
		 * Sets the render quality. Setting to `high` means This value indicates that the browser
		 * tries to improve the SVG quality over rendering speed and geometric precision.
		 *
		 * @param {('low'|'high')} quality - The quality.
		 */
		this.setQuality = function ( quality ) {

			switch ( quality ) {

				case 'high': _quality = 1; break;
				case 'low': _quality = 0; break;

			}

		};

		/**
		 * Sets the clear color.
		 *
		 * @param {(number|Color|string)} color - The clear color to set.
		 */
		this.setClearColor = function ( color ) {

			_clearColor.set( color );

		};

		this.setPixelRatio = function () {};

		/**
		 * Resizes the renderer to the given width and height.
		 *
		 * @param {number} width - The width of the renderer.
		 * @param {number} height - The height of the renderer.
		 */
		this.setSize = function ( width, height ) {

			_svgWidth = width; _svgHeight = height;
			_svgWidthHalf = _svgWidth / 2; _svgHeightHalf = _svgHeight / 2;

			_svg.setAttribute( 'viewBox', ( - _svgWidthHalf ) + ' ' + ( - _svgHeightHalf ) + ' ' + _svgWidth + ' ' + _svgHeight );
			_svg.setAttribute( 'width', _svgWidth );
			_svg.setAttribute( 'height', _svgHeight );

			_clipBox.min.set( - _svgWidthHalf, - _svgHeightHalf );
			_clipBox.max.set( _svgWidthHalf, _svgHeightHalf );

		};

		/**
		 * Returns an object containing the width and height of the renderer.
		 *
		 * @return {{width:number,height:number}} The size of the renderer.
		 */
		this.getSize = function () {

			return {
				width: _svgWidth,
				height: _svgHeight
			};

		};

		/**
		 * Sets the precision of the data used to create a paths.
		 *
		 * @param {number} precision - The precision to set.
		 */
		this.setPrecision = function ( precision ) {

			_precision = precision;

		};

		function removeChildNodes() {

			_pathCount = 0;

			while ( _svg.childNodes.length > 0 ) {

				_svg.removeChild( _svg.childNodes[ 0 ] );

			}

		}

		function convert( c ) {

			return _precision !== null ? c.toFixed( _precision ) : c;

		}

		/**
		 * Performs a manual clear with the defined clear color.
		 */
		this.clear = function () {

			removeChildNodes();
			_svg.style.backgroundColor = _clearColor.getStyle( _this.outputColorSpace );

		};

		/**
		 * Renders the given scene using the given camera.
		 *
		 * @param {Object3D} scene - A scene or any other type of 3D object.
		 * @param {Camera} camera - The camera.
		 */
		this.render = function ( scene, camera ) {

			if ( camera instanceof Camera === false ) {

				console.error( 'THREE.SVGRenderer.render: camera is not an instance of Camera.' );
				return;

			}

			const background = scene.background;

			if ( background && background.isColor ) {

				removeChildNodes();
				_svg.style.backgroundColor = background.getStyle( _this.outputColorSpace );

			} else if ( this.autoClear === true ) {

				this.clear();

			}

			_this.info.render.vertices = 0;
			_this.info.render.faces = 0;

			_viewMatrix.copy( camera.matrixWorldInverse );
			_viewProjectionMatrix.multiplyMatrices( camera.projectionMatrix, _viewMatrix );

			_renderData = _projector.projectScene( scene, camera, this.sortObjects, this.sortElements );
			_elements = _renderData.elements;
			_lights = _renderData.lights;

			_normalViewMatrix.getNormalMatrix( camera.matrixWorldInverse );

			calculateLights( _lights );

			 // reset accumulated path

			_currentPath = '';
			_currentStyle = '';

			for ( let e = 0, el = _elements.length; e < el; e ++ ) {

				const element = _elements[ e ];
				const material = element.material;

				if ( material === undefined || material.opacity === 0 ) continue;

				_elemBox.makeEmpty();

				if ( element instanceof RenderableSprite ) {

					_v1 = element;
					_v1.x *= _svgWidthHalf; _v1.y *= - _svgHeightHalf;

					renderSprite( _v1, element, material );

				} else if ( element instanceof RenderableLine ) {

					_v1 = element.v1; _v2 = element.v2;

					_v1.positionScreen.x *= _svgWidthHalf; _v1.positionScreen.y *= - _svgHeightHalf;
					_v2.positionScreen.x *= _svgWidthHalf; _v2.positionScreen.y *= - _svgHeightHalf;

					_elemBox.setFromPoints( [ _v1.positionScreen, _v2.positionScreen ] );

					if ( _clipBox.intersectsBox( _elemBox ) === true ) {

						renderLine( _v1, _v2, material );

					}

				} else if ( element instanceof RenderableFace ) {

					_v1 = element.v1; _v2 = element.v2; _v3 = element.v3;

					if ( _v1.positionScreen.z < - 1 || _v1.positionScreen.z > 1 ) continue;
					if ( _v2.positionScreen.z < - 1 || _v2.positionScreen.z > 1 ) continue;
					if ( _v3.positionScreen.z < - 1 || _v3.positionScreen.z > 1 ) continue;

					_v1.positionScreen.x *= _svgWidthHalf; _v1.positionScreen.y *= - _svgHeightHalf;
					_v2.positionScreen.x *= _svgWidthHalf; _v2.positionScreen.y *= - _svgHeightHalf;
					_v3.positionScreen.x *= _svgWidthHalf; _v3.positionScreen.y *= - _svgHeightHalf;

					if ( this.overdraw > 0 ) {

						expand( _v1.positionScreen, _v2.positionScreen, this.overdraw );
						expand( _v2.positionScreen, _v3.positionScreen, this.overdraw );
						expand( _v3.positionScreen, _v1.positionScreen, this.overdraw );

					}

					_elemBox.setFromPoints( [
						_v1.positionScreen,
						_v2.positionScreen,
						_v3.positionScreen
					] );

					if ( _clipBox.intersectsBox( _elemBox ) === true ) {

						renderFace3( _v1, _v2, _v3, element, material );

					}

				}

			}

			flushPath(); // just to flush last svg:path

			scene.traverseVisible( function ( object ) {

				 if ( object.isSVGObject ) {

					_vector3.setFromMatrixPosition( object.matrixWorld );
					_vector3.applyMatrix4( _viewProjectionMatrix );

					if ( _vector3.z < - 1 || _vector3.z > 1 ) return;

					const x = _vector3.x * _svgWidthHalf;
					const y = - _vector3.y * _svgHeightHalf;

					const node = object.node;
					node.setAttribute( 'transform', 'translate(' + x + ',' + y + ')' );

					_svg.appendChild( node );

				}

			} );

		};

		function calculateLights( lights ) {

			_ambientLight.setRGB( 0, 0, 0 );
			_directionalLights.setRGB( 0, 0, 0 );
			_pointLights.setRGB( 0, 0, 0 );

			for ( let l = 0, ll = lights.length; l < ll; l ++ ) {

				const light = lights[ l ];
				const lightColor = light.color;

				if ( light.isAmbientLight ) {

					_ambientLight.r += lightColor.r;
					_ambientLight.g += lightColor.g;
					_ambientLight.b += lightColor.b;

				} else if ( light.isDirectionalLight ) {

					_directionalLights.r += lightColor.r;
					_directionalLights.g += lightColor.g;
					_directionalLights.b += lightColor.b;

				} else if ( light.isPointLight ) {

					_pointLights.r += lightColor.r;
					_pointLights.g += lightColor.g;
					_pointLights.b += lightColor.b;

				}

			}

		}

		function calculateLight( lights, position, normal, color ) {

			for ( let l = 0, ll = lights.length; l < ll; l ++ ) {

				const light = lights[ l ];
				const lightColor = light.color;

				if ( light.isDirectionalLight ) {

					const lightPosition = _vector3.setFromMatrixPosition( light.matrixWorld ).normalize();

					let amount = normal.dot( lightPosition );

					if ( amount <= 0 ) continue;

					amount *= light.intensity;

					color.r += lightColor.r * amount;
					color.g += lightColor.g * amount;
					color.b += lightColor.b * amount;

				} else if ( light.isPointLight ) {

					const lightPosition = _vector3.setFromMatrixPosition( light.matrixWorld );

					let amount = normal.dot( _vector3.subVectors( lightPosition, position ).normalize() );

					if ( amount <= 0 ) continue;

					amount *= light.distance == 0 ? 1 : 1 - Math.min( position.distanceTo( lightPosition ) / light.distance, 1 );

					if ( amount == 0 ) continue;

					amount *= light.intensity;

					color.r += lightColor.r * amount;
					color.g += lightColor.g * amount;
					color.b += lightColor.b * amount;

				}

			}

		}

		function renderSprite( v1, element, material ) {

			let scaleX = element.scale.x * _svgWidthHalf;
			let scaleY = element.scale.y * _svgHeightHalf;

			if ( material.isPointsMaterial ) {

				scaleX *= material.size;
				scaleY *= material.size;

			}

			const path = 'M' + convert( v1.x - scaleX * 0.5 ) + ',' + convert( v1.y - scaleY * 0.5 ) + 'h' + convert( scaleX ) + 'v' + convert( scaleY ) + 'h' + convert( - scaleX ) + 'z';
			let style = '';

			if ( material.isSpriteMaterial || material.isPointsMaterial ) {

				style = 'fill:' + material.color.getStyle( _this.outputColorSpace ) + ';fill-opacity:' + material.opacity;

			}

			addPath( style, path );

		}

		function renderLine( v1, v2, material ) {

			const path = 'M' + convert( v1.positionScreen.x ) + ',' + convert( v1.positionScreen.y ) + 'L' + convert( v2.positionScreen.x ) + ',' + convert( v2.positionScreen.y );

			if ( material.isLineBasicMaterial ) {

				let style = 'fill:none;stroke:' + material.color.getStyle( _this.outputColorSpace ) + ';stroke-opacity:' + material.opacity + ';stroke-width:' + material.linewidth + ';stroke-linecap:' + material.linecap;

				if ( material.isLineDashedMaterial ) {

					style = style + ';stroke-dasharray:' + material.dashSize + ',' + material.gapSize;

				}

				addPath( style, path );

			}

		}

		function renderFace3( v1, v2, v3, element, material ) {

			_this.info.render.vertices += 3;
			_this.info.render.faces ++;

			const path = 'M' + convert( v1.positionScreen.x ) + ',' + convert( v1.positionScreen.y ) + 'L' + convert( v2.positionScreen.x ) + ',' + convert( v2.positionScreen.y ) + 'L' + convert( v3.positionScreen.x ) + ',' + convert( v3.positionScreen.y ) + 'z';
			let style = '';

			if ( material.isMeshBasicMaterial ) {

				_color.copy( material.color );

				if ( material.vertexColors ) {

					_color.multiply( element.color );

				}

			} else if ( material.isMeshLambertMaterial || material.isMeshPhongMaterial || material.isMeshStandardMaterial ) {

				_diffuseColor.copy( material.color );

				if ( material.vertexColors ) {

					_diffuseColor.multiply( element.color );

				}

				_color.copy( _ambientLight );

				_centroid.copy( v1.positionWorld ).add( v2.positionWorld ).add( v3.positionWorld ).divideScalar( 3 );

				calculateLight( _lights, _centroid, element.normalModel, _color );

				_color.multiply( _diffuseColor ).add( material.emissive );

			} else if ( material.isMeshNormalMaterial ) {

				_normal.copy( element.normalModel ).applyMatrix3( _normalViewMatrix ).normalize();

				_color.setRGB( _normal.x, _normal.y, _normal.z ).multiplyScalar( 0.5 ).addScalar( 0.5 );

			}

			if ( material.wireframe ) {

				style = 'fill:none;stroke:' + _color.getStyle( _this.outputColorSpace ) + ';stroke-opacity:' + material.opacity + ';stroke-width:' + material.wireframeLinewidth + ';stroke-linecap:' + material.wireframeLinecap + ';stroke-linejoin:' + material.wireframeLinejoin;

			} else {

				style = 'fill:' + _color.getStyle( _this.outputColorSpace ) + ';fill-opacity:' + material.opacity;

			}

			addPath( style, path );

		}

		// Hide anti-alias gaps

		function expand( v1, v2, pixels ) {

			let x = v2.x - v1.x, y = v2.y - v1.y;
			const det = x * x + y * y;

			if ( det === 0 ) return;

			const idet = pixels / Math.sqrt( det );

			x *= idet; y *= idet;

			v2.x += x; v2.y += y;
			v1.x -= x; v1.y -= y;

		}

		function addPath( style, path ) {

			if ( _currentStyle === style ) {

				_currentPath += path;

			} else {

				flushPath();

				_currentStyle = style;
				_currentPath = path;

			}

		}

		function flushPath() {

			if ( _currentPath ) {

				_svgNode = getPathNode( _pathCount ++ );
				_svgNode.setAttribute( 'd', _currentPath );
				_svgNode.setAttribute( 'style', _currentStyle );
				_svg.appendChild( _svgNode );

			}

			_currentPath = '';
			_currentStyle = '';

		}

		function getPathNode( id ) {

			if ( _svgPathPool[ id ] == null ) {

				_svgPathPool[ id ] = document.createElementNS( 'http://www.w3.org/2000/svg', 'path' );

				if ( _quality == 0 ) {

					_svgPathPool[ id ].setAttribute( 'shape-rendering', 'crispEdges' ); //optimizeSpeed

				}

				return _svgPathPool[ id ];

			}

			return _svgPathPool[ id ];

		}

	}

}
```
</details>


---