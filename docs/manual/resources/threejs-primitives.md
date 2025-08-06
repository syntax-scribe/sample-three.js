[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-primitives.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 26 |
| 🧱 Classes | 12 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 79 |
| ⚡ Async/Await Patterns | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`manual/resources/threejs-primitives.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `threejsLessonUtils` | `./threejs-lesson-utils.js` |
| `FontLoader` | `../../examples/jsm/loaders/FontLoader.js` |
| `ParametricGeometry` | `../../examples/jsm/geometries/ParametricGeometry.js` |
| `TextGeometry` | `../../examples/jsm/geometries/TextGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `darkColors` | `{ lines: string; }` | let/var | `{ lines: '#DDD', }` | ✗ |
| `lightColors` | `{ lines: string; }` | let/var | `{ lines: '#000', }` | ✗ |
| `isDarkMode` | `boolean` | let/var | `darkMatcher.matches` | ✗ |
| `colors` | `{ lines: string; }` | let/var | `isDarkMode ? darkColors : lightColors` | ✗ |
| `fontLoader` | `FontLoader` | let/var | `new FontLoader()` | ✗ |
| `fontPromise` | `Promise<any>` | let/var | `new Promise( ( resolve ) => { fontLoader.load( '/examples/fonts/helvetiker_re...` | ✗ |
| `shape` | `any` | let/var | `new THREE.Shape()` | ✗ |
| `x` | `-2.5` | let/var | `- 2.5` | ✗ |
| `y` | `-5` | let/var | `- 5` | ✗ |
| `extrudeSettings` | `{ steps: number; depth: number; bevel...` | let/var | `{ steps, depth, bevelEnabled, bevelThickness, bevelSize, bevelSegments, }` | ✗ |
| `geometry` | `any` | let/var | `new THREE.ExtrudeGeometry( shape, extrudeSettings )` | ✗ |
| `outline` | `any` | let/var | `new THREE.Shape( [ [ - 2, - 0.1 ], [ 2, - 0.1 ], [ 2, 0.6 ], [ 1.6, 0.6 ], [ ...` | ✗ |
| `x` | `-2.5` | let/var | `- 2.5` | ✗ |
| `y` | `-5` | let/var | `- 5` | ✗ |
| `shape` | `any` | let/var | `new THREE.CurvePath()` | ✗ |
| `extrudeSettings` | `{ steps: number; bevelEnabled: boolea...` | let/var | `{ steps, bevelEnabled: false, extrudePath: shape, }` | ✗ |
| `geometry` | `any` | let/var | `new THREE.ExtrudeGeometry( outline, extrudeSettings )` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `z` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `number` | let/var | `- 2 * ( 1 - Math.cos( u ) / 2 ) * Math.sin( v )` | ✗ |
| `verticesOfCube` | `number[]` | let/var | `[ - 1, - 1, - 1, 1, - 1, - 1, 1, 1, - 1, - 1, 1, - 1, - 1, - 1, 1, 1, - 1, 1,...` | ✗ |
| `indicesOfFaces` | `number[]` | let/var | `[ 2, 1, 0, 0, 3, 2, 0, 4, 7, 7, 3, 0, 0, 1, 5, 5, 4, 0, 1, 2, 6, 6, 5, 1, 2, ...` | ✗ |
| `shape` | `any` | let/var | `new THREE.Shape()` | ✗ |
| `x` | `-2.5` | let/var | `- 2.5` | ✗ |
| `y` | `-5` | let/var | `- 5` | ✗ |
| `shape` | `any` | let/var | `new THREE.Shape()` | ✗ |
| `x` | `-2.5` | let/var | `- 2.5` | ✗ |
| `y` | `-5` | let/var | `- 5` | ✗ |
| `tx` | `number` | let/var | `t * 3 - 1.5` | ✗ |
| `tz` | `0` | let/var | `0` | ✗ |
| `path` | `CustomSinCurve` | let/var | `new CustomSinCurve( 4 )` | ✗ |
| `size` | `8` | let/var | `8` | ✗ |
| `radius` | `7` | let/var | `7` | ✗ |
| `widthSegments` | `12` | let/var | `12` | ✗ |
| `heightSegments` | `8` | let/var | `8` | ✗ |
| `geometry` | `any` | let/var | `new THREE.SphereGeometry( radius, widthSegments, heightSegments )` | ✗ |
| `material` | `any` | let/var | `new THREE.PointsMaterial( { color: 'red', size: 0.2, } )` | ✗ |
| `points` | `any` | let/var | `new THREE.Points( geometry, material )` | ✗ |
| `radius` | `7` | let/var | `7` | ✗ |
| `widthSegments` | `12` | let/var | `12` | ✗ |
| `heightSegments` | `8` | let/var | `8` | ✗ |
| `geometry` | `any` | let/var | `new THREE.SphereGeometry( radius, widthSegments, heightSegments )` | ✗ |
| `material` | `any` | let/var | `new THREE.PointsMaterial( { color: 'red', size: 3 * window.devicePixelRatio, ...` | ✗ |
| `points` | `any` | let/var | `new THREE.Points( geometry, material )` | ✗ |
| `diagrams` | `{ BoxGeometry: { ui: { width: { type:...` | let/var | `{ BoxGeometry: { ui: { width: { type: 'range', min: 1, max: 10, precision: 1,...` | ✗ |
| `name` | `any` | let/var | `base.dataset.primitive` | ✗ |
| `info` | `any` | let/var | `diagrams[ name ]` | ✗ |
| `text` | `any` | let/var | `base.innerHTML` | ✗ |
| `createRE` | `RegExp` | let/var | `/^\s*(?:function *)*create\d*\((.*?)\)/` | ✗ |
| `indentRE` | `RegExp` | let/var | `/^(\s*)[^\s]/` | ✗ |
| `prefixLen` | `number` | let/var | `m[ 1 ].length` | ✗ |
| `trimmedLines` | `any` | let/var | `src ? src.split( '\n' ).slice( 1, - 1 ) : rawLines.slice( 1, rawLines.length ...` | ✗ |
| `i` | `number` | let/var | `2` | ✗ |
| `createFn` | `any` | let/var | `info[ `create${i}` ]` | ✗ |
| `name` | `any` | let/var | `base.dataset.diagram` | ✗ |
| `info` | `any` | let/var | `diagrams[ name ]` | ✗ |
| `promise` | `Promise<any>` | let/var | `( result instanceof Promise ) ? result : Promise.resolve( result )` | ✗ |
| `diagramInfo` | `any` | let/var | `await promise` | ✗ |
| `geometry` | `any` | let/var | `diagramInfo` | ✗ |
| `geometry` | `any` | let/var | `diagramInfo.geometry \|\| diagramInfo.lineGeometry \|\| diagramInfo.mesh.geom...` | ✗ |
| `centerOffset` | `any` | let/var | `new THREE.Vector3()` | ✗ |
| `mesh` | `any` | let/var | `diagramInfo.mesh` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshPhongMaterial( { flatShading: info.flatShading === false ? fals...` | ✗ |
| `lineMesh` | `any` | let/var | `new THREE.LineSegments( diagramInfo.lineGeometry \|\| diagramInfo.geometry, n...` | ✗ |
| `primitives` | `{}` | let/var | `{}` | ✗ |
| `root` | `any` | let/var | `new THREE.Object3D()` | ✗ |
| `primitiveName` | `any` | let/var | `base.dataset.primitive` | ✗ |
| `infos` | `any` | let/var | `primitives[ primitiveName ]` | ✗ |
| `params` | `{}` | let/var | `{}` | ✗ |
| `nameRE` | `RegExp` | let/var | `/ui: ([a-zA-Z0-9_]+) *$/` | ✗ |
| `name` | `string` | let/var | `nameRE.exec( span.textContent )[ 1 ]` | ✗ |
| `ui` | `any` | let/var | `info.ui[ name ]` | ✗ |
| `valueRange` | `number` | let/var | `ui.max - ui.min` | ✗ |
| `inputMax` | `100` | let/var | `100` | ✗ |
| `precision` | `any` | let/var | `ui.precision === undefined ? ( valueRange > 4 ? 0 : 2 ) : ui.precision` | ✗ |
| `padding` | `any` | let/var | `ui.max.toFixed( precision ).length` | ✗ |
| `newValue` | `any` | let/var | `input.value * valueRange / inputMax + ui.min` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `addGeometry` | promise | Promise.resolve |
| async-function | `updateGeometry` | addGeometry( root, info, Object.values( params ) ) | *none* |
| async-function | `createLiveImage` | addGeometry( root, info ) | *none* |


---

## Functions

### `klein(v: any, u: any, target: any): void`

**Parameters:**

- **`v`** `any`
- **`u`** `any`
- **`target`** `any`

**Returns:** `void`

**Calls:**

- `Math.cos`
- `Math.sin`
- `target.set( x, y, z ).multiplyScalar`

<details><summary>Code</summary>

```typescript
function klein( v, u, target ) {

					u *= Math.PI;
					v *= 2 * Math.PI;
					u = u * 2;

					let x;
					let z;

					if ( u < Math.PI ) {

						x = 3 * Math.cos( u ) * ( 1 + Math.sin( u ) ) + ( 2 * ( 1 - Math.cos( u ) / 2 ) ) * Math.cos( u ) * Math.cos( v );
						z = - 8 * Math.sin( u ) - 2 * ( 1 - Math.cos( u ) / 2 ) * Math.sin( u ) * Math.cos( v );

					} else {

						x = 3 * Math.cos( u ) * ( 1 + Math.sin( u ) ) + ( 2 * ( 1 - Math.cos( u ) / 2 ) ) * Math.cos( v + Math.PI );
						z = - 8 * Math.sin( u );

					}

					const y = - 2 * ( 1 - Math.cos( u ) / 2 ) * Math.sin( v );

					target.set( x, y, z ).multiplyScalar( 0.75 );

				}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve.getPoint(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.sin`
- `new THREE.Vector3( tx, ty, tz ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `addLink(parent: any, name: any, href: any): HTMLAnchorElement`

**Parameters:**

- **`parent`** `any`
- **`name`** `any`
- **`href`** `any`

**Returns:** `HTMLAnchorElement`

**Calls:**

- `document.createElement`
- `a.setAttribute`
- `a.appendChild`
- `parent.appendChild`

<details><summary>Code</summary>

```typescript
function addLink( parent, name, href ) {

		const a = document.createElement( 'a' );
		a.setAttribute( 'target', '_blank' );
		a.href = href || `https://threejs.org/docs/#api/en/geometries/${name}`;
		const code = document.createElement( 'code' );
		code.textContent = name;
		a.appendChild( code );
		parent.appendChild( a );
		return a;

	}
```
</details>

### `addDeepLink(parent: any, name: any, href: any): HTMLAnchorElement`

**Parameters:**

- **`parent`** `any`
- **`name`** `any`
- **`href`** `any`

**Returns:** `HTMLAnchorElement`

**Calls:**

- `document.createElement`
- `parent.appendChild`

<details><summary>Code</summary>

```typescript
function addDeepLink( parent, name, href ) {

		const a = document.createElement( 'a' );
		a.href = href || `https://threejs.org/docs/#api/en/geometries/${name}`;
		a.textContent = name;
		a.className = 'deep-link';
		parent.appendChild( a );
		return a;

	}
```
</details>

### `addElem(parent: any, type: any, className: any, text: any): any`

**Parameters:**

- **`parent`** `any`
- **`type`** `any`
- **`className`** `any`
- **`text`** `any`

**Returns:** `any`

**Calls:**

- `document.createElement`
- `parent.appendChild`

<details><summary>Code</summary>

```typescript
function addElem( parent, type, className, text ) {

		const elem = document.createElement( type );
		elem.className = className;
		if ( text ) {

			elem.textContent = text;

		}

		parent.appendChild( elem );
		return elem;

	}
```
</details>

### `addDiv(parent: any, className: any): any`

**Parameters:**

- **`parent`** `any`
- **`className`** `any`

**Returns:** `any`

**Calls:**

- `addElem`

<details><summary>Code</summary>

```typescript
function addDiv( parent, className ) {

		return addElem( parent, 'div', className );

	}
```
</details>

### `createPrimitiveDOM(base: any): void`

**Parameters:**

- **`base`** `any`

**Returns:** `void`

**Calls:**

- `addDiv`
- `addDeepLink`
- `addLink`
- `createFn.toString().replace( /return (new THREE\.[a-zA-Z]+Geometry)/, 'const geometry = $1' ).split`
- `indentRE.exec`
- `createRE.exec`
- `m2[ 1 ].trim`
- `src.split( '\n' ).slice`
- `rawLines.slice( 1, rawLines.length - 1 ).map`
- `line.substring`
- `argString.split( ',' ).map`
- `arg.trim`
- `arg.trim().split`
- `trimmedLines.findIndex`
- `l.indexOf`
- `trimmedLines.splice`
- `addElem`
- `trimmedLines.join`
- `createLiveImage`
- `makeExample`

**Internal Comments:**
```
// I get that this is super brittle. I think I'd have to
// work through a bunch more examples to come up with a better
// structure. Also, I don't want to generate actual code and
// use eval. (maybe a bad striction)
```

<details><summary>Code</summary>

```typescript
function createPrimitiveDOM( base ) {

		const name = base.dataset.primitive;
		const info = diagrams[ name ];
		if ( ! info ) {

			throw new Error( `no primitive ${name}` );

		}

		const text = base.innerHTML;
		base.innerHTML = '';

		const pair = addDiv( base, 'pair' );
		const elem = addDiv( pair, 'shape' );

		const right = addDiv( pair, 'desc' );
		addDeepLink( right, '#', `#${base.id}` );
		addLink( right, name );
		addDiv( right, '.note' ).innerHTML = text;

		// I get that this is super brittle. I think I'd have to
		// work through a bunch more examples to come up with a better
		// structure. Also, I don't want to generate actual code and
		// use eval. (maybe a bad striction)

		function makeExample( elem, createFn, src ) {

			const rawLines = createFn.toString().replace( /return (new THREE\.[a-zA-Z]+Geometry)/, 'const geometry = $1' ).split( /\n/ );
			const createRE = /^\s*(?:function *)*create\d*\((.*?)\)/;
			const indentRE = /^(\s*)[^\s]/;
			const m = indentRE.exec( rawLines[ 2 ] );
			const prefixLen = m[ 1 ].length;
			const m2 = createRE.exec( rawLines[ 0 ] );
			const argString = m2[ 1 ].trim();
			const trimmedLines = src
				? src.split( '\n' ).slice( 1, - 1 )
				: rawLines.slice( 1, rawLines.length - 1 ).map( line => line.substring( prefixLen ) );
			if ( info.addConstCode !== false && argString ) {

				const lines = argString.split( ',' ).map( ( arg ) => {

					return `const ${arg.trim()};  // ui: ${arg.trim().split( ' ' )[ 0 ]}`;

				} );
				const lineNdx = trimmedLines.findIndex( l => l.indexOf( 'const geometry' ) >= 0 );
				trimmedLines.splice( lineNdx < 0 ? 0 : lineNdx, 0, ...lines );

			}

			addElem( base, 'pre', 'prettyprint showmods', trimmedLines.join( '\n' ) );

			createLiveImage( elem, { ...info, create: createFn }, name );

		}

		makeExample( elem, info.create, info.src );

		{

			let i = 2;
			for ( ;; ) {

				const createFn = info[ `create${i}` ];
				if ( ! createFn ) {

					break;

				}

				const shapeElem = addDiv( base, 'shape' );
				makeExample( shapeElem, createFn, info[ `src${i}` ] );
				++ i;

			}

		}

	}
```
</details>

### `makeExample(elem: any, createFn: any, src: any): void`

**Parameters:**

- **`elem`** `any`
- **`createFn`** `any`
- **`src`** `any`

**Returns:** `void`

**Calls:**

- `createFn.toString().replace( /return (new THREE\.[a-zA-Z]+Geometry)/, 'const geometry = $1' ).split`
- `indentRE.exec`
- `createRE.exec`
- `m2[ 1 ].trim`
- `src.split( '\n' ).slice`
- `rawLines.slice( 1, rawLines.length - 1 ).map`
- `line.substring`
- `argString.split( ',' ).map`
- `arg.trim`
- `arg.trim().split`
- `trimmedLines.findIndex`
- `l.indexOf`
- `trimmedLines.splice`
- `addElem`
- `trimmedLines.join`
- `createLiveImage`

<details><summary>Code</summary>

```typescript
function makeExample( elem, createFn, src ) {

			const rawLines = createFn.toString().replace( /return (new THREE\.[a-zA-Z]+Geometry)/, 'const geometry = $1' ).split( /\n/ );
			const createRE = /^\s*(?:function *)*create\d*\((.*?)\)/;
			const indentRE = /^(\s*)[^\s]/;
			const m = indentRE.exec( rawLines[ 2 ] );
			const prefixLen = m[ 1 ].length;
			const m2 = createRE.exec( rawLines[ 0 ] );
			const argString = m2[ 1 ].trim();
			const trimmedLines = src
				? src.split( '\n' ).slice( 1, - 1 )
				: rawLines.slice( 1, rawLines.length - 1 ).map( line => line.substring( prefixLen ) );
			if ( info.addConstCode !== false && argString ) {

				const lines = argString.split( ',' ).map( ( arg ) => {

					return `const ${arg.trim()};  // ui: ${arg.trim().split( ' ' )[ 0 ]}`;

				} );
				const lineNdx = trimmedLines.findIndex( l => l.indexOf( 'const geometry' ) >= 0 );
				trimmedLines.splice( lineNdx < 0 ? 0 : lineNdx, 0, ...lines );

			}

			addElem( base, 'pre', 'prettyprint showmods', trimmedLines.join( '\n' ) );

			createLiveImage( elem, { ...info, create: createFn }, name );

		}
```
</details>

### `createDiagram(base: any): void`

**Parameters:**

- **`base`** `any`

**Returns:** `void`

**Calls:**

- `createLiveImage`

<details><summary>Code</summary>

```typescript
function createDiagram( base ) {

		const name = base.dataset.diagram;
		const info = diagrams[ name ];
		if ( ! info ) {

			throw new Error( `no primitive ${name}` );

		}

		createLiveImage( base, info, name );

	}
```
</details>

### `addGeometry(root: any, info: any, args: any[]): Promise<void>`

**Parameters:**

- **`root`** `any`
- **`info`** `any`
- **`args`** `any[]`

**Returns:** `Promise<void>`

**Calls:**

- `info.create`
- `Promise.resolve`
- `geometry.computeBoundingBox`
- `geometry.boundingBox.getCenter( centerOffset ).multiplyScalar`
- `material.color.setHSL`
- `Math.random`
- `mesh.position.copy`
- `root.add`
- `lineMesh.position.copy`

<details><summary>Code</summary>

```typescript
async function addGeometry( root, info, args = [] ) {

		const result = info.create( ...args );
		const promise = ( result instanceof Promise ) ? result : Promise.resolve( result );

		let diagramInfo = await promise;
		if ( diagramInfo instanceof THREE.BufferGeometry ) {

			const geometry = diagramInfo;
			diagramInfo = {
				geometry,
			};

		}

		const geometry = diagramInfo.geometry || diagramInfo.lineGeometry || diagramInfo.mesh.geometry;
		geometry.computeBoundingBox();
		const centerOffset = new THREE.Vector3();
		geometry.boundingBox.getCenter( centerOffset ).multiplyScalar( - 1 );

		let mesh = diagramInfo.mesh;
		if ( diagramInfo.geometry ) {

			if ( ! info.material ) {

				const material = new THREE.MeshPhongMaterial( {
					flatShading: info.flatShading === false ? false : true,
					side: THREE.DoubleSide,
				} );
				material.color.setHSL( Math.random(), .5, .5 );
				info.material = material;

			}

			mesh = new THREE.Mesh( diagramInfo.geometry, info.material );

		}

		if ( mesh ) {

			mesh.position.copy( centerOffset );
			root.add( mesh );

		}

		if ( info.showLines !== false ) {

			const lineMesh = new THREE.LineSegments(
				diagramInfo.lineGeometry || diagramInfo.geometry,
				new THREE.LineBasicMaterial( {
					color: diagramInfo.geometry ? 0xffffff : colors.lines,
					transparent: true,
					opacity: 0.5,
				} ) );
			lineMesh.position.copy( centerOffset );
			root.add( lineMesh );

		}

	}
```
</details>

### `updateGeometry(root: any, info: any, params: any): Promise<void>`

**Parameters:**

- **`root`** `any`
- **`info`** `any`
- **`params`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `root.children.slice`
- `addGeometry`
- `Object.values`
- `oldChildren.forEach`
- `root.remove`
- `child.geometry.dispose`

<details><summary>Code</summary>

```typescript
async function updateGeometry( root, info, params ) {

		const oldChildren = root.children.slice();
		await addGeometry( root, info, Object.values( params ) );
		oldChildren.forEach( ( child ) => {

			root.remove( child );
			child.geometry.dispose();

		} );

	}
```
</details>

### `createLiveImage(elem: any, info: any, name: any): Promise<void>`

**Parameters:**

- **`elem`** `any`
- **`info`** `any`
- **`name`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `primitives[ name ].push`
- `addGeometry`
- `threejsLessonUtils.addDiagram`

<details><summary>Code</summary>

```typescript
async function createLiveImage( elem, info, name ) {

		const root = new THREE.Object3D();

		primitives[ name ] = primitives[ name ] || [];
		primitives[ name ].push( {
			root,
			info,
		} );

		await addGeometry( root, info );
		threejsLessonUtils.addDiagram( elem, { create: () => root } );

	}
```
</details>

### `create(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => root
```
</details>

### `create(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => root
```
</details>

### `getValueElem(commentElem: any): any`

**Parameters:**

- **`commentElem`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getValueElem( commentElem ) {

		return commentElem.previousElementSibling &&
           commentElem.previousElementSibling.previousElementSibling &&
           commentElem.previousElementSibling.previousElementSibling.previousElementSibling;

	}
```
</details>


---

## Classes

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>

### `CustomSinCurve`

<details><summary>Class Code</summary>

```ts
class CustomSinCurve extends THREE.Curve {

					constructor( scale ) {

						super();
						this.scale = scale;

					}
					getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}

				}
```
</details>

#### Methods

##### `getPoint(t: any): any`

<details><summary>Code</summary>

```ts
getPoint( t ) {

						const tx = t * 3 - 1.5;
						const ty = Math.sin( 2 * Math.PI * t );
						const tz = 0;
						return new THREE.Vector3( tx, ty, tz ).multiplyScalar( this.scale );

					}
```
</details>


---