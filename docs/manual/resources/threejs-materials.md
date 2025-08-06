[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-materials.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 51 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/threejs-materials.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `threejsLessonUtils` | `./threejs-lesson-utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `radius` | `7` | let/var | `7` | ✗ |
| `widthDivisions` | `100` | let/var | `100` | ✗ |
| `heightDivisions` | `50` | let/var | `50` | ✗ |
| `widthDivisions` | `12` | let/var | `12` | ✗ |
| `heightDivisions` | `9` | let/var | `9` | ✗ |
| `widthDivisions` | `12` | let/var | `12` | ✗ |
| `heightDivisions` | `9` | let/var | `9` | ✗ |
| `geometry` | `any` | let/var | `new THREE.SphereGeometry( radius, widthDivisions, heightDivisions )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshPhongMaterial( { flatShading, color: 'hsl(300,50%,50%)', } )` | ✗ |
| `geometry` | `any` | let/var | `lowPoly ? lowPolySphereGeometry : highPolySphereGeometry` | ✗ |
| `material` | `any` | let/var | `new MaterialCtor( { color: 'hsl(210,50%,50%)', ...params, } )` | ✗ |
| `base` | `any` | let/var | `new THREE.Object3D()` | ✗ |
| `size` | `6` | let/var | `6` | ✗ |
| `geometry` | `any` | let/var | `new THREE.PlaneGeometry( size, size )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshBasicMaterial( { side } )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `numMetal` | `5` | let/var | `5` | ✗ |
| `numRough` | `7` | let/var | `7` | ✗ |
| `meshes` | `any[]` | let/var | `[]` | ✗ |
| `MatCtor` | `any` | let/var | `physical ? THREE.MeshPhysicalMaterial : THREE.MeshStandardMaterial` | ✗ |
| `color` | `"hsl(160,50%,50%)" \| "hsl(140,50%,50%)"` | let/var | `physical ? 'hsl(160,50%,50%)' : 'hsl(140,50%,50%)'` | ✗ |
| `row` | `any[]` | let/var | `[]` | ✗ |
| `material` | `any` | let/var | `new MatCtor( { color, roughness: r / ( numRough - 1 ), metalness: 1 - m / ( n...` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( highPolySphereGeometry, material )` | ✗ |
| `width` | `number` | let/var | `( rect.right - rect.left ) * renderInfo.pixelRatio` | ✗ |
| `height` | `number` | let/var | `( rect.bottom - rect.top ) * renderInfo.pixelRatio` | ✗ |
| `left` | `number` | let/var | `rect.left * renderInfo.pixelRatio` | ✗ |
| `bottom` | `number` | let/var | `( renderer.domElement.clientHeight - rect.bottom ) * renderInfo.pixelRatio` | ✗ |
| `cellSize` | `number` | let/var | `Math.min( width / numRough, height / numMetal ) \| 0` | ✗ |
| `xOff` | `number` | let/var | `( width - cellSize * numRough ) / 2` | ✗ |
| `yOff` | `number` | let/var | `( height - cellSize * numMetal ) / 2` | ✗ |
| `x` | `number` | let/var | `left + xOff + r * cellSize` | ✗ |
| `y` | `number` | let/var | `bottom + yOff + m * cellSize` | ✗ |
| `mesh` | `any` | let/var | `meshes[ m ][ r ]` | ✗ |
| `settings` | `{ clearcoat: number; clearcoatRoughne...` | let/var | `{ clearcoat: .5, clearcoatRoughness: 0, }` | ✗ |
| `radius` | `4` | let/var | `4` | ✗ |
| `tube` | `1.5` | let/var | `1.5` | ✗ |
| `radialSegments` | `8` | let/var | `8` | ✗ |
| `tubularSegments` | `64` | let/var | `64` | ✗ |
| `p` | `2` | let/var | `2` | ✗ |
| `q` | `3` | let/var | `3` | ✗ |
| `geometry` | `any` | let/var | `new THREE.TorusKnotGeometry( radius, tube, tubularSegments, radialSegments, p...` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshDepthMaterial()` | ✗ |
| `radius` | `4` | let/var | `4` | ✗ |
| `tube` | `1.5` | let/var | `1.5` | ✗ |
| `radialSegments` | `8` | let/var | `8` | ✗ |
| `tubularSegments` | `64` | let/var | `64` | ✗ |
| `p` | `2` | let/var | `2` | ✗ |
| `q` | `3` | let/var | `3` | ✗ |
| `geometry` | `any` | let/var | `new THREE.TorusKnotGeometry( radius, tube, tubularSegments, radialSegments, p...` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshNormalMaterial()` | ✗ |


---

## Functions

### `makeSphere(widthDivisions: any, heightDivisions: any): any`

**Parameters:**

- **`widthDivisions`** `any`
- **`heightDivisions`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function makeSphere( widthDivisions, heightDivisions ) {

		const radius = 7;
		return new THREE.SphereGeometry( radius, widthDivisions, heightDivisions );

	}
```
</details>

### `smoothOrFlat(flatShading: any, radius: number): any`

**Parameters:**

- **`flatShading`** `any`
- **`radius`** `number`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function smoothOrFlat( flatShading, radius = 7 ) {

		const widthDivisions = 12;
		const heightDivisions = 9;
		const geometry = new THREE.SphereGeometry( radius, widthDivisions, heightDivisions );
		const material = new THREE.MeshPhongMaterial( {
			flatShading,
			color: 'hsl(300,50%,50%)',
		} );
		return new THREE.Mesh( geometry, material );

	}
```
</details>

### `basicLambertPhongExample(MaterialCtor: any, lowPoly: any, params: {}): { obj3D: any; trackball: any; }`

**Parameters:**

- **`MaterialCtor`** `any`
- **`lowPoly`** `any`
- **`params`** `{}`

**Returns:** `{ obj3D: any; trackball: any; }`

<details><summary>Code</summary>

```typescript
function basicLambertPhongExample( MaterialCtor, lowPoly, params = {} ) {

		const geometry = lowPoly ? lowPolySphereGeometry : highPolySphereGeometry;
		const material = new MaterialCtor( {
			color: 'hsl(210,50%,50%)',
			...params,
		} );
		return {
			obj3D: new THREE.Mesh( geometry, material ),
			trackball: lowPoly,
		};

	}
```
</details>

### `sideExample(side: any): any`

**Parameters:**

- **`side`** `any`

**Returns:** `any`

**Calls:**

- `[
			{ position: [ - 1, 0, 0 ], up: [ 0, 1, 0 ], },
			{ position: [ 1, 0, 0 ], up: [ 0, - 1, 0 ], },
			{ position: [ 0, - 1, 0 ], up: [ 0, 0, - 1 ], },
			{ position: [ 0, 1, 0 ], up: [ 0, 0, 1 ], },
			{ position: [ 0, 0, - 1 ], up: [ 1, 0, 0 ], },
			{ position: [ 0, 0, 1 ], up: [ - 1, 0, 0 ], },
		].forEach`
- `material.color.setHSL`
- `mesh.up.set`
- `mesh.lookAt`
- `mesh.position.set( ...settings.position ).multiplyScalar`
- `base.add`

<details><summary>Code</summary>

```typescript
function sideExample( side ) {

		const base = new THREE.Object3D();
		const size = 6;
		const geometry = new THREE.PlaneGeometry( size, size );
		[
			{ position: [ - 1, 0, 0 ], up: [ 0, 1, 0 ], },
			{ position: [ 1, 0, 0 ], up: [ 0, - 1, 0 ], },
			{ position: [ 0, - 1, 0 ], up: [ 0, 0, - 1 ], },
			{ position: [ 0, 1, 0 ], up: [ 0, 0, 1 ], },
			{ position: [ 0, 0, - 1 ], up: [ 1, 0, 0 ], },
			{ position: [ 0, 0, 1 ], up: [ - 1, 0, 0 ], },
		].forEach( ( settings, ndx ) => {

			const material = new THREE.MeshBasicMaterial( { side } );
			material.color.setHSL( ndx / 6, .5, .5 );
			const mesh = new THREE.Mesh( geometry, material );
			mesh.up.set( ...settings.up );
			mesh.lookAt( ...settings.position );
			mesh.position.set( ...settings.position ).multiplyScalar( size * .75 );
			base.add( mesh );

		} );
		return base;

	}
```
</details>

### `makeStandardPhysicalMaterialGrid(elem: any, physical: any, update: any): { obj3D: any; trackball: boolean; render(renderInfo: any): void; }`

**Parameters:**

- **`elem`** `any`
- **`physical`** `any`
- **`update`** `any`

**Returns:** `{ obj3D: any; trackball: boolean; render(renderInfo: any): void; }`

**Calls:**

- `row.push`
- `meshes.push`
- `elem.getBoundingClientRect`
- `Math.min`
- `camera.updateProjectionMatrix`
- `update`
- `renderer.setViewport`
- `renderer.setScissor`
- `scene.add`
- `renderer.render`
- `scene.remove`

<details><summary>Code</summary>

```typescript
function makeStandardPhysicalMaterialGrid( elem, physical, update ) {

		const numMetal = 5;
		const numRough = 7;
		const meshes = [];
		const MatCtor = physical ? THREE.MeshPhysicalMaterial : THREE.MeshStandardMaterial;
		const color = physical ? 'hsl(160,50%,50%)' : 'hsl(140,50%,50%)';
		for ( let m = 0; m < numMetal; ++ m ) {

			const row = [];
			for ( let r = 0; r < numRough; ++ r ) {

				const material = new MatCtor( {
					color,
					roughness: r / ( numRough - 1 ),
					metalness: 1 - m / ( numMetal - 1 ),
				} );
				const mesh = new THREE.Mesh( highPolySphereGeometry, material );
				row.push( mesh );

			}

			meshes.push( row );

		}

		return {
			obj3D: null,
			trackball: false,
			render( renderInfo ) {

				const { camera, scene, renderer } = renderInfo;
				const rect = elem.getBoundingClientRect();

				const width = ( rect.right - rect.left ) * renderInfo.pixelRatio;
				const height = ( rect.bottom - rect.top ) * renderInfo.pixelRatio;
				const left = rect.left * renderInfo.pixelRatio;
				const bottom = ( renderer.domElement.clientHeight - rect.bottom ) * renderInfo.pixelRatio;

				const cellSize = Math.min( width / numRough, height / numMetal ) | 0;
				const xOff = ( width - cellSize * numRough ) / 2;
				const yOff = ( height - cellSize * numMetal ) / 2;

				camera.aspect = 1;
				camera.updateProjectionMatrix();

				if ( update ) {

					update( meshes );

				}

				for ( let m = 0; m < numMetal; ++ m ) {

					for ( let r = 0; r < numRough; ++ r ) {

						const x = left + xOff + r * cellSize;
						const y = bottom + yOff + m * cellSize;
						renderer.setViewport( x, y, cellSize, cellSize );
						renderer.setScissor( x, y, cellSize, cellSize );
						const mesh = meshes[ m ][ r ];
						scene.add( mesh );
						renderer.render( scene, camera );
						scene.remove( mesh );

					}

				}

			},
		};

	}
```
</details>

### `addElem(parent: any, type: any, style: {}): any`

**Parameters:**

- **`parent`** `any`
- **`type`** `any`
- **`style`** `{}`

**Returns:** `any`

**Calls:**

- `document.createElement`
- `Object.assign`
- `parent.appendChild`

<details><summary>Code</summary>

```typescript
function addElem( parent, type, style = {} ) {

					const elem = document.createElement( type );
					Object.assign( elem.style, style );
					parent.appendChild( elem );
					return elem;

				}
```
</details>

### `addRange(elem: any, obj: any, prop: any, min: any, max: any): void`

**Parameters:**

- **`elem`** `any`
- **`obj`** `any`
- **`prop`** `any`
- **`min`** `any`
- **`max`** `any`

**Returns:** `void`

**Calls:**

- `addElem`
- `obj[ prop ].toFixed`
- `updateNum`
- `Object.assign`
- `input.addEventListener`

<details><summary>Code</summary>

```typescript
function addRange( elem, obj, prop, min, max ) {

					const outer = addElem( elem, 'div', {
						width: '100%',
						textAlign: 'center',
						'font-family': 'monospace',
					} );

					const div = addElem( outer, 'div', {
						textAlign: 'left',
						display: 'inline-block',
					} );

					const label = addElem( div, 'label', {
						display: 'inline-block',
						width: '12em',
					} );
					label.textContent = prop;

					const num = addElem( div, 'div', {
						display: 'inline-block',
						width: '3em',
					} );

					function updateNum() {

						num.textContent = obj[ prop ].toFixed( 2 );

					}

					updateNum();

					const input = addElem( div, 'input', {
					} );
					Object.assign( input, {
						type: 'range',
						min: 0,
						max: 100,
						value: ( obj[ prop ] - min ) / ( max - min ) * 100,
					} );
					input.addEventListener( 'input', () => {

						obj[ prop ] = min + ( max - min ) * input.value / 100;
						updateNum();

					} );

				}
```
</details>

### `updateNum(): void`

**Returns:** `void`

**Calls:**

- `obj[ prop ].toFixed`

<details><summary>Code</summary>

```typescript
function updateNum() {

						num.textContent = obj[ prop ].toFixed( 2 );

					}
```
</details>


---