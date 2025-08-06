[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PDBLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 31 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/PDBLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Loader` | `three` |
| `Color` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `build` | `{ geometryAtoms: any; geometryBonds: ...` | let/var | `{ geometryAtoms: new BufferGeometry(), geometryBonds: new BufferGeometry(), j...` | ✗ |
| `geometryAtoms` | `any` | let/var | `build.geometryAtoms` | ✗ |
| `geometryBonds` | `any` | let/var | `build.geometryBonds` | ✗ |
| `verticesAtoms` | `any[]` | let/var | `[]` | ✗ |
| `colorsAtoms` | `any[]` | let/var | `[]` | ✗ |
| `verticesBonds` | `any[]` | let/var | `[]` | ✗ |
| `c` | `any` | let/var | `new Color()` | ✗ |
| `atom` | `any` | let/var | `atoms[ i ]` | ✗ |
| `x` | `any` | let/var | `atom[ 0 ]` | ✗ |
| `y` | `any` | let/var | `atom[ 1 ]` | ✗ |
| `z` | `any` | let/var | `atom[ 2 ]` | ✗ |
| `r` | `number` | let/var | `atom[ 3 ][ 0 ] / 255` | ✗ |
| `g` | `number` | let/var | `atom[ 3 ][ 1 ] / 255` | ✗ |
| `b` | `number` | let/var | `atom[ 3 ][ 2 ] / 255` | ✗ |
| `bond` | `any` | let/var | `_bonds[ i ]` | ✗ |
| `start` | `any` | let/var | `bond[ 0 ]` | ✗ |
| `end` | `any` | let/var | `bond[ 1 ]` | ✗ |
| `startAtom` | `any` | let/var | `_atomMap[ start ]` | ✗ |
| `endAtom` | `any` | let/var | `_atomMap[ end ]` | ✗ |
| `x` | `any` | let/var | `startAtom[ 0 ]` | ✗ |
| `y` | `any` | let/var | `startAtom[ 1 ]` | ✗ |
| `z` | `any` | let/var | `startAtom[ 2 ]` | ✗ |
| `CPK` | `{ h: number[]; he: number[]; li: numb...` | let/var | `{ h: [ 255, 255, 255 ], he: [ 217, 255, 255 ], li: [ 204, 128, 255 ], be: [ 1...` | ✗ |
| `atoms` | `any[]` | let/var | `[]` | ✗ |
| `_bonds` | `any[]` | let/var | `[]` | ✗ |
| `_bhash` | `{}` | let/var | `{}` | ✗ |
| `_atomMap` | `{}` | let/var | `{}` | ✗ |
| `index` | `number` | let/var | `parseInt( lines[ i ].slice( 6, 11 ) ) - 1` | ✗ |
| `atomData` | `any[]` | let/var | `[ x, y, z, CPK[ e ], capitalize( e ) ]` | ✗ |


---

## Functions

### `PDBLoader.load(url: string, onLoad: (arg0: any) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded PDB asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Object)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: any) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `onLoad`
- `scope.parse`
- `onError`
- `console.error`
- `scope.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `PDBLoader.parse(text: string): any`

**JSDoc:**
```typescript
/**
	 * Parses the given PDB data and returns an object holding the atoms and
	 * bond geometries as well as the raw atom data as JSON.
	 *
	 * @param {string} text - The raw PDB data as a string.
	 * @return {Object} The result object.
	 */
```

**Parameters:**

- **`text`** `string`

**Returns:** `any`

**Calls:**

- `text.replace( /^\s\s*/, '' ).replace`
- `text.charAt( 0 ).toUpperCase`
- `text.slice( 1 ).toLowerCase`
- `Math.min`
- `Math.max`
- `parseInt`
- `lines[ i ].slice`
- `hash`
- `_bonds.push`
- `verticesAtoms.push`
- `c.setRGB`
- `colorsAtoms.push`
- `verticesBonds.push`
- `geometryAtoms.setAttribute`
- `geometryBonds.setAttribute`
- `text.split`
- `parseFloat`
- `trim( lines[ i ].slice( 76, 78 ) ).toLowerCase`
- `trim( lines[ i ].slice( 12, 14 ) ).toLowerCase`
- `capitalize`
- `atoms.push`
- `parseBond`
- `buildGeometry`

**Internal Comments:**
```
// Based on CanvasMol PDB parser
// atoms (x2)
// bonds
// build geometry (x4)
// parse (x2)
// build and return geometry
```

<details><summary>Code</summary>

```typescript
parse( text ) {

		// Based on CanvasMol PDB parser

		function trim( text ) {

			return text.replace( /^\s\s*/, '' ).replace( /\s\s*$/, '' );

		}

		function capitalize( text ) {

			return text.charAt( 0 ).toUpperCase() + text.slice( 1 ).toLowerCase();

		}

		function hash( s, e ) {

			return 's' + Math.min( s, e ) + 'e' + Math.max( s, e );

		}

		function parseBond( start, length, satom, i ) {

			const eatom = parseInt( lines[ i ].slice( start, start + length ) );

			if ( eatom ) {

				const h = hash( satom, eatom );

				if ( _bhash[ h ] === undefined ) {

					_bonds.push( [ satom - 1, eatom - 1, 1 ] );
					_bhash[ h ] = _bonds.length - 1;

				} else {

					// doesn't really work as almost all PDBs
					// have just normal bonds appearing multiple
					// times instead of being double/triple bonds
					// bonds[bhash[h]][2] += 1;

				}

			}

		}

		function buildGeometry() {

			const build = {
				geometryAtoms: new BufferGeometry(),
				geometryBonds: new BufferGeometry(),
				json: {
					atoms: atoms
				}
			};

			const geometryAtoms = build.geometryAtoms;
			const geometryBonds = build.geometryBonds;

			const verticesAtoms = [];
			const colorsAtoms = [];
			const verticesBonds = [];

			// atoms

			const c = new Color();

			for ( let i = 0, l = atoms.length; i < l; i ++ ) {

				const atom = atoms[ i ];

				const x = atom[ 0 ];
				const y = atom[ 1 ];
				const z = atom[ 2 ];

				verticesAtoms.push( x, y, z );

				const r = atom[ 3 ][ 0 ] / 255;
				const g = atom[ 3 ][ 1 ] / 255;
				const b = atom[ 3 ][ 2 ] / 255;

				c.setRGB( r, g, b, SRGBColorSpace );

				colorsAtoms.push( c.r, c.g, c.b );

			}

			// bonds

			for ( let i = 0, l = _bonds.length; i < l; i ++ ) {

				const bond = _bonds[ i ];

				const start = bond[ 0 ];
				const end = bond[ 1 ];

				const startAtom = _atomMap[ start ];
				const endAtom = _atomMap[ end ];

				let x = startAtom[ 0 ];
				let y = startAtom[ 1 ];
				let z = startAtom[ 2 ];

				verticesBonds.push( x, y, z );

				x = endAtom[ 0 ];
				y = endAtom[ 1 ];
				z = endAtom[ 2 ];

				verticesBonds.push( x, y, z );

			}

			// build geometry

			geometryAtoms.setAttribute( 'position', new Float32BufferAttribute( verticesAtoms, 3 ) );
			geometryAtoms.setAttribute( 'color', new Float32BufferAttribute( colorsAtoms, 3 ) );

			geometryBonds.setAttribute( 'position', new Float32BufferAttribute( verticesBonds, 3 ) );

			return build;

		}

		const CPK = { h: [ 255, 255, 255 ], he: [ 217, 255, 255 ], li: [ 204, 128, 255 ], be: [ 194, 255, 0 ], b: [ 255, 181, 181 ], c: [ 144, 144, 144 ], n: [ 48, 80, 248 ], o: [ 255, 13, 13 ], f: [ 144, 224, 80 ], ne: [ 179, 227, 245 ], na: [ 171, 92, 242 ], mg: [ 138, 255, 0 ], al: [ 191, 166, 166 ], si: [ 240, 200, 160 ], p: [ 255, 128, 0 ], s: [ 255, 255, 48 ], cl: [ 31, 240, 31 ], ar: [ 128, 209, 227 ], k: [ 143, 64, 212 ], ca: [ 61, 255, 0 ], sc: [ 230, 230, 230 ], ti: [ 191, 194, 199 ], v: [ 166, 166, 171 ], cr: [ 138, 153, 199 ], mn: [ 156, 122, 199 ], fe: [ 224, 102, 51 ], co: [ 240, 144, 160 ], ni: [ 80, 208, 80 ], cu: [ 200, 128, 51 ], zn: [ 125, 128, 176 ], ga: [ 194, 143, 143 ], ge: [ 102, 143, 143 ], as: [ 189, 128, 227 ], se: [ 255, 161, 0 ], br: [ 166, 41, 41 ], kr: [ 92, 184, 209 ], rb: [ 112, 46, 176 ], sr: [ 0, 255, 0 ], y: [ 148, 255, 255 ], zr: [ 148, 224, 224 ], nb: [ 115, 194, 201 ], mo: [ 84, 181, 181 ], tc: [ 59, 158, 158 ], ru: [ 36, 143, 143 ], rh: [ 10, 125, 140 ], pd: [ 0, 105, 133 ], ag: [ 192, 192, 192 ], cd: [ 255, 217, 143 ], in: [ 166, 117, 115 ], sn: [ 102, 128, 128 ], sb: [ 158, 99, 181 ], te: [ 212, 122, 0 ], i: [ 148, 0, 148 ], xe: [ 66, 158, 176 ], cs: [ 87, 23, 143 ], ba: [ 0, 201, 0 ], la: [ 112, 212, 255 ], ce: [ 255, 255, 199 ], pr: [ 217, 255, 199 ], nd: [ 199, 255, 199 ], pm: [ 163, 255, 199 ], sm: [ 143, 255, 199 ], eu: [ 97, 255, 199 ], gd: [ 69, 255, 199 ], tb: [ 48, 255, 199 ], dy: [ 31, 255, 199 ], ho: [ 0, 255, 156 ], er: [ 0, 230, 117 ], tm: [ 0, 212, 82 ], yb: [ 0, 191, 56 ], lu: [ 0, 171, 36 ], hf: [ 77, 194, 255 ], ta: [ 77, 166, 255 ], w: [ 33, 148, 214 ], re: [ 38, 125, 171 ], os: [ 38, 102, 150 ], ir: [ 23, 84, 135 ], pt: [ 208, 208, 224 ], au: [ 255, 209, 35 ], hg: [ 184, 184, 208 ], tl: [ 166, 84, 77 ], pb: [ 87, 89, 97 ], bi: [ 158, 79, 181 ], po: [ 171, 92, 0 ], at: [ 117, 79, 69 ], rn: [ 66, 130, 150 ], fr: [ 66, 0, 102 ], ra: [ 0, 125, 0 ], ac: [ 112, 171, 250 ], th: [ 0, 186, 255 ], pa: [ 0, 161, 255 ], u: [ 0, 143, 255 ], np: [ 0, 128, 255 ], pu: [ 0, 107, 255 ], am: [ 84, 92, 242 ], cm: [ 120, 92, 227 ], bk: [ 138, 79, 227 ], cf: [ 161, 54, 212 ], es: [ 179, 31, 212 ], fm: [ 179, 31, 186 ], md: [ 179, 13, 166 ], no: [ 189, 13, 135 ], lr: [ 199, 0, 102 ], rf: [ 204, 0, 89 ], db: [ 209, 0, 79 ], sg: [ 217, 0, 69 ], bh: [ 224, 0, 56 ], hs: [ 230, 0, 46 ], mt: [ 235, 0, 38 ], ds: [ 235, 0, 38 ], rg: [ 235, 0, 38 ], cn: [ 235, 0, 38 ], uut: [ 235, 0, 38 ], uuq: [ 235, 0, 38 ], uup: [ 235, 0, 38 ], uuh: [ 235, 0, 38 ], uus: [ 235, 0, 38 ], uuo: [ 235, 0, 38 ] };

		const atoms = [];

		const _bonds = [];
		const _bhash = {};
		const _atomMap = {};

		// parse

		const lines = text.split( '\n' );

		for ( let i = 0, l = lines.length; i < l; i ++ ) {

			if ( lines[ i ].slice( 0, 4 ) === 'ATOM' || lines[ i ].slice( 0, 6 ) === 'HETATM' ) {

				const x = parseFloat( lines[ i ].slice( 30, 37 ) );
				const y = parseFloat( lines[ i ].slice( 38, 45 ) );
				const z = parseFloat( lines[ i ].slice( 46, 53 ) );
				const index = parseInt( lines[ i ].slice( 6, 11 ) ) - 1;

				let e = trim( lines[ i ].slice( 76, 78 ) ).toLowerCase();

				if ( e === '' ) {

					e = trim( lines[ i ].slice( 12, 14 ) ).toLowerCase();

				}

				const atomData = [ x, y, z, CPK[ e ], capitalize( e ) ];

				atoms.push( atomData );
				_atomMap[ index ] = atomData;

			} else if ( lines[ i ].slice( 0, 6 ) === 'CONECT' ) {

				const satom = parseInt( lines[ i ].slice( 6, 11 ) );

				parseBond( 11, 5, satom, i );
				parseBond( 16, 5, satom, i );
				parseBond( 21, 5, satom, i );
				parseBond( 26, 5, satom, i );

			}

		}

		// build and return geometry

		return buildGeometry();

	}
```
</details>

### `trim(text: any): any`

**Parameters:**

- **`text`** `any`

**Returns:** `any`

**Calls:**

- `text.replace( /^\s\s*/, '' ).replace`

<details><summary>Code</summary>

```typescript
function trim( text ) {

			return text.replace( /^\s\s*/, '' ).replace( /\s\s*$/, '' );

		}
```
</details>

### `capitalize(text: any): any`

**Parameters:**

- **`text`** `any`

**Returns:** `any`

**Calls:**

- `text.charAt( 0 ).toUpperCase`
- `text.slice( 1 ).toLowerCase`

<details><summary>Code</summary>

```typescript
function capitalize( text ) {

			return text.charAt( 0 ).toUpperCase() + text.slice( 1 ).toLowerCase();

		}
```
</details>

### `hash(s: any, e: any): string`

**Parameters:**

- **`s`** `any`
- **`e`** `any`

**Returns:** `string`

**Calls:**

- `Math.min`
- `Math.max`

<details><summary>Code</summary>

```typescript
function hash( s, e ) {

			return 's' + Math.min( s, e ) + 'e' + Math.max( s, e );

		}
```
</details>

### `parseBond(start: any, length: any, satom: any, i: any): void`

**Parameters:**

- **`start`** `any`
- **`length`** `any`
- **`satom`** `any`
- **`i`** `any`

**Returns:** `void`

**Calls:**

- `parseInt`
- `lines[ i ].slice`
- `hash`
- `_bonds.push`

<details><summary>Code</summary>

```typescript
function parseBond( start, length, satom, i ) {

			const eatom = parseInt( lines[ i ].slice( start, start + length ) );

			if ( eatom ) {

				const h = hash( satom, eatom );

				if ( _bhash[ h ] === undefined ) {

					_bonds.push( [ satom - 1, eatom - 1, 1 ] );
					_bhash[ h ] = _bonds.length - 1;

				} else {

					// doesn't really work as almost all PDBs
					// have just normal bonds appearing multiple
					// times instead of being double/triple bonds
					// bonds[bhash[h]][2] += 1;

				}

			}

		}
```
</details>

### `buildGeometry(): { geometryAtoms: any; geometryBonds: any; json: { atoms: any[]; }; }`

**Returns:** `{ geometryAtoms: any; geometryBonds: any; json: { atoms: any[]; }; }`

**Calls:**

- `verticesAtoms.push`
- `c.setRGB`
- `colorsAtoms.push`
- `verticesBonds.push`
- `geometryAtoms.setAttribute`
- `geometryBonds.setAttribute`

**Internal Comments:**
```
// atoms (x2)
// bonds
// build geometry (x4)
```

<details><summary>Code</summary>

```typescript
function buildGeometry() {

			const build = {
				geometryAtoms: new BufferGeometry(),
				geometryBonds: new BufferGeometry(),
				json: {
					atoms: atoms
				}
			};

			const geometryAtoms = build.geometryAtoms;
			const geometryBonds = build.geometryBonds;

			const verticesAtoms = [];
			const colorsAtoms = [];
			const verticesBonds = [];

			// atoms

			const c = new Color();

			for ( let i = 0, l = atoms.length; i < l; i ++ ) {

				const atom = atoms[ i ];

				const x = atom[ 0 ];
				const y = atom[ 1 ];
				const z = atom[ 2 ];

				verticesAtoms.push( x, y, z );

				const r = atom[ 3 ][ 0 ] / 255;
				const g = atom[ 3 ][ 1 ] / 255;
				const b = atom[ 3 ][ 2 ] / 255;

				c.setRGB( r, g, b, SRGBColorSpace );

				colorsAtoms.push( c.r, c.g, c.b );

			}

			// bonds

			for ( let i = 0, l = _bonds.length; i < l; i ++ ) {

				const bond = _bonds[ i ];

				const start = bond[ 0 ];
				const end = bond[ 1 ];

				const startAtom = _atomMap[ start ];
				const endAtom = _atomMap[ end ];

				let x = startAtom[ 0 ];
				let y = startAtom[ 1 ];
				let z = startAtom[ 2 ];

				verticesBonds.push( x, y, z );

				x = endAtom[ 0 ];
				y = endAtom[ 1 ];
				z = endAtom[ 2 ];

				verticesBonds.push( x, y, z );

			}

			// build geometry

			geometryAtoms.setAttribute( 'position', new Float32BufferAttribute( verticesAtoms, 3 ) );
			geometryAtoms.setAttribute( 'color', new Float32BufferAttribute( colorsAtoms, 3 ) );

			geometryBonds.setAttribute( 'position', new Float32BufferAttribute( verticesBonds, 3 ) );

			return build;

		}
```
</details>


---

## Classes

### `PDBLoader`

<details><summary>Class Code</summary>

```ts
class PDBLoader extends Loader {

	/**
	 * Constructs a new PDB loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded PDB asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Object)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Parses the given PDB data and returns an object holding the atoms and
	 * bond geometries as well as the raw atom data as JSON.
	 *
	 * @param {string} text - The raw PDB data as a string.
	 * @return {Object} The result object.
	 */
	parse( text ) {

		// Based on CanvasMol PDB parser

		function trim( text ) {

			return text.replace( /^\s\s*/, '' ).replace( /\s\s*$/, '' );

		}

		function capitalize( text ) {

			return text.charAt( 0 ).toUpperCase() + text.slice( 1 ).toLowerCase();

		}

		function hash( s, e ) {

			return 's' + Math.min( s, e ) + 'e' + Math.max( s, e );

		}

		function parseBond( start, length, satom, i ) {

			const eatom = parseInt( lines[ i ].slice( start, start + length ) );

			if ( eatom ) {

				const h = hash( satom, eatom );

				if ( _bhash[ h ] === undefined ) {

					_bonds.push( [ satom - 1, eatom - 1, 1 ] );
					_bhash[ h ] = _bonds.length - 1;

				} else {

					// doesn't really work as almost all PDBs
					// have just normal bonds appearing multiple
					// times instead of being double/triple bonds
					// bonds[bhash[h]][2] += 1;

				}

			}

		}

		function buildGeometry() {

			const build = {
				geometryAtoms: new BufferGeometry(),
				geometryBonds: new BufferGeometry(),
				json: {
					atoms: atoms
				}
			};

			const geometryAtoms = build.geometryAtoms;
			const geometryBonds = build.geometryBonds;

			const verticesAtoms = [];
			const colorsAtoms = [];
			const verticesBonds = [];

			// atoms

			const c = new Color();

			for ( let i = 0, l = atoms.length; i < l; i ++ ) {

				const atom = atoms[ i ];

				const x = atom[ 0 ];
				const y = atom[ 1 ];
				const z = atom[ 2 ];

				verticesAtoms.push( x, y, z );

				const r = atom[ 3 ][ 0 ] / 255;
				const g = atom[ 3 ][ 1 ] / 255;
				const b = atom[ 3 ][ 2 ] / 255;

				c.setRGB( r, g, b, SRGBColorSpace );

				colorsAtoms.push( c.r, c.g, c.b );

			}

			// bonds

			for ( let i = 0, l = _bonds.length; i < l; i ++ ) {

				const bond = _bonds[ i ];

				const start = bond[ 0 ];
				const end = bond[ 1 ];

				const startAtom = _atomMap[ start ];
				const endAtom = _atomMap[ end ];

				let x = startAtom[ 0 ];
				let y = startAtom[ 1 ];
				let z = startAtom[ 2 ];

				verticesBonds.push( x, y, z );

				x = endAtom[ 0 ];
				y = endAtom[ 1 ];
				z = endAtom[ 2 ];

				verticesBonds.push( x, y, z );

			}

			// build geometry

			geometryAtoms.setAttribute( 'position', new Float32BufferAttribute( verticesAtoms, 3 ) );
			geometryAtoms.setAttribute( 'color', new Float32BufferAttribute( colorsAtoms, 3 ) );

			geometryBonds.setAttribute( 'position', new Float32BufferAttribute( verticesBonds, 3 ) );

			return build;

		}

		const CPK = { h: [ 255, 255, 255 ], he: [ 217, 255, 255 ], li: [ 204, 128, 255 ], be: [ 194, 255, 0 ], b: [ 255, 181, 181 ], c: [ 144, 144, 144 ], n: [ 48, 80, 248 ], o: [ 255, 13, 13 ], f: [ 144, 224, 80 ], ne: [ 179, 227, 245 ], na: [ 171, 92, 242 ], mg: [ 138, 255, 0 ], al: [ 191, 166, 166 ], si: [ 240, 200, 160 ], p: [ 255, 128, 0 ], s: [ 255, 255, 48 ], cl: [ 31, 240, 31 ], ar: [ 128, 209, 227 ], k: [ 143, 64, 212 ], ca: [ 61, 255, 0 ], sc: [ 230, 230, 230 ], ti: [ 191, 194, 199 ], v: [ 166, 166, 171 ], cr: [ 138, 153, 199 ], mn: [ 156, 122, 199 ], fe: [ 224, 102, 51 ], co: [ 240, 144, 160 ], ni: [ 80, 208, 80 ], cu: [ 200, 128, 51 ], zn: [ 125, 128, 176 ], ga: [ 194, 143, 143 ], ge: [ 102, 143, 143 ], as: [ 189, 128, 227 ], se: [ 255, 161, 0 ], br: [ 166, 41, 41 ], kr: [ 92, 184, 209 ], rb: [ 112, 46, 176 ], sr: [ 0, 255, 0 ], y: [ 148, 255, 255 ], zr: [ 148, 224, 224 ], nb: [ 115, 194, 201 ], mo: [ 84, 181, 181 ], tc: [ 59, 158, 158 ], ru: [ 36, 143, 143 ], rh: [ 10, 125, 140 ], pd: [ 0, 105, 133 ], ag: [ 192, 192, 192 ], cd: [ 255, 217, 143 ], in: [ 166, 117, 115 ], sn: [ 102, 128, 128 ], sb: [ 158, 99, 181 ], te: [ 212, 122, 0 ], i: [ 148, 0, 148 ], xe: [ 66, 158, 176 ], cs: [ 87, 23, 143 ], ba: [ 0, 201, 0 ], la: [ 112, 212, 255 ], ce: [ 255, 255, 199 ], pr: [ 217, 255, 199 ], nd: [ 199, 255, 199 ], pm: [ 163, 255, 199 ], sm: [ 143, 255, 199 ], eu: [ 97, 255, 199 ], gd: [ 69, 255, 199 ], tb: [ 48, 255, 199 ], dy: [ 31, 255, 199 ], ho: [ 0, 255, 156 ], er: [ 0, 230, 117 ], tm: [ 0, 212, 82 ], yb: [ 0, 191, 56 ], lu: [ 0, 171, 36 ], hf: [ 77, 194, 255 ], ta: [ 77, 166, 255 ], w: [ 33, 148, 214 ], re: [ 38, 125, 171 ], os: [ 38, 102, 150 ], ir: [ 23, 84, 135 ], pt: [ 208, 208, 224 ], au: [ 255, 209, 35 ], hg: [ 184, 184, 208 ], tl: [ 166, 84, 77 ], pb: [ 87, 89, 97 ], bi: [ 158, 79, 181 ], po: [ 171, 92, 0 ], at: [ 117, 79, 69 ], rn: [ 66, 130, 150 ], fr: [ 66, 0, 102 ], ra: [ 0, 125, 0 ], ac: [ 112, 171, 250 ], th: [ 0, 186, 255 ], pa: [ 0, 161, 255 ], u: [ 0, 143, 255 ], np: [ 0, 128, 255 ], pu: [ 0, 107, 255 ], am: [ 84, 92, 242 ], cm: [ 120, 92, 227 ], bk: [ 138, 79, 227 ], cf: [ 161, 54, 212 ], es: [ 179, 31, 212 ], fm: [ 179, 31, 186 ], md: [ 179, 13, 166 ], no: [ 189, 13, 135 ], lr: [ 199, 0, 102 ], rf: [ 204, 0, 89 ], db: [ 209, 0, 79 ], sg: [ 217, 0, 69 ], bh: [ 224, 0, 56 ], hs: [ 230, 0, 46 ], mt: [ 235, 0, 38 ], ds: [ 235, 0, 38 ], rg: [ 235, 0, 38 ], cn: [ 235, 0, 38 ], uut: [ 235, 0, 38 ], uuq: [ 235, 0, 38 ], uup: [ 235, 0, 38 ], uuh: [ 235, 0, 38 ], uus: [ 235, 0, 38 ], uuo: [ 235, 0, 38 ] };

		const atoms = [];

		const _bonds = [];
		const _bhash = {};
		const _atomMap = {};

		// parse

		const lines = text.split( '\n' );

		for ( let i = 0, l = lines.length; i < l; i ++ ) {

			if ( lines[ i ].slice( 0, 4 ) === 'ATOM' || lines[ i ].slice( 0, 6 ) === 'HETATM' ) {

				const x = parseFloat( lines[ i ].slice( 30, 37 ) );
				const y = parseFloat( lines[ i ].slice( 38, 45 ) );
				const z = parseFloat( lines[ i ].slice( 46, 53 ) );
				const index = parseInt( lines[ i ].slice( 6, 11 ) ) - 1;

				let e = trim( lines[ i ].slice( 76, 78 ) ).toLowerCase();

				if ( e === '' ) {

					e = trim( lines[ i ].slice( 12, 14 ) ).toLowerCase();

				}

				const atomData = [ x, y, z, CPK[ e ], capitalize( e ) ];

				atoms.push( atomData );
				_atomMap[ index ] = atomData;

			} else if ( lines[ i ].slice( 0, 6 ) === 'CONECT' ) {

				const satom = parseInt( lines[ i ].slice( 6, 11 ) );

				parseBond( 11, 5, satom, i );
				parseBond( 16, 5, satom, i );
				parseBond( 21, 5, satom, i );
				parseBond( 26, 5, satom, i );

			}

		}

		// build and return geometry

		return buildGeometry();

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: any) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `parse(text: string): any`

<details><summary>Code</summary>

```ts
parse( text ) {

		// Based on CanvasMol PDB parser

		function trim( text ) {

			return text.replace( /^\s\s*/, '' ).replace( /\s\s*$/, '' );

		}

		function capitalize( text ) {

			return text.charAt( 0 ).toUpperCase() + text.slice( 1 ).toLowerCase();

		}

		function hash( s, e ) {

			return 's' + Math.min( s, e ) + 'e' + Math.max( s, e );

		}

		function parseBond( start, length, satom, i ) {

			const eatom = parseInt( lines[ i ].slice( start, start + length ) );

			if ( eatom ) {

				const h = hash( satom, eatom );

				if ( _bhash[ h ] === undefined ) {

					_bonds.push( [ satom - 1, eatom - 1, 1 ] );
					_bhash[ h ] = _bonds.length - 1;

				} else {

					// doesn't really work as almost all PDBs
					// have just normal bonds appearing multiple
					// times instead of being double/triple bonds
					// bonds[bhash[h]][2] += 1;

				}

			}

		}

		function buildGeometry() {

			const build = {
				geometryAtoms: new BufferGeometry(),
				geometryBonds: new BufferGeometry(),
				json: {
					atoms: atoms
				}
			};

			const geometryAtoms = build.geometryAtoms;
			const geometryBonds = build.geometryBonds;

			const verticesAtoms = [];
			const colorsAtoms = [];
			const verticesBonds = [];

			// atoms

			const c = new Color();

			for ( let i = 0, l = atoms.length; i < l; i ++ ) {

				const atom = atoms[ i ];

				const x = atom[ 0 ];
				const y = atom[ 1 ];
				const z = atom[ 2 ];

				verticesAtoms.push( x, y, z );

				const r = atom[ 3 ][ 0 ] / 255;
				const g = atom[ 3 ][ 1 ] / 255;
				const b = atom[ 3 ][ 2 ] / 255;

				c.setRGB( r, g, b, SRGBColorSpace );

				colorsAtoms.push( c.r, c.g, c.b );

			}

			// bonds

			for ( let i = 0, l = _bonds.length; i < l; i ++ ) {

				const bond = _bonds[ i ];

				const start = bond[ 0 ];
				const end = bond[ 1 ];

				const startAtom = _atomMap[ start ];
				const endAtom = _atomMap[ end ];

				let x = startAtom[ 0 ];
				let y = startAtom[ 1 ];
				let z = startAtom[ 2 ];

				verticesBonds.push( x, y, z );

				x = endAtom[ 0 ];
				y = endAtom[ 1 ];
				z = endAtom[ 2 ];

				verticesBonds.push( x, y, z );

			}

			// build geometry

			geometryAtoms.setAttribute( 'position', new Float32BufferAttribute( verticesAtoms, 3 ) );
			geometryAtoms.setAttribute( 'color', new Float32BufferAttribute( colorsAtoms, 3 ) );

			geometryBonds.setAttribute( 'position', new Float32BufferAttribute( verticesBonds, 3 ) );

			return build;

		}

		const CPK = { h: [ 255, 255, 255 ], he: [ 217, 255, 255 ], li: [ 204, 128, 255 ], be: [ 194, 255, 0 ], b: [ 255, 181, 181 ], c: [ 144, 144, 144 ], n: [ 48, 80, 248 ], o: [ 255, 13, 13 ], f: [ 144, 224, 80 ], ne: [ 179, 227, 245 ], na: [ 171, 92, 242 ], mg: [ 138, 255, 0 ], al: [ 191, 166, 166 ], si: [ 240, 200, 160 ], p: [ 255, 128, 0 ], s: [ 255, 255, 48 ], cl: [ 31, 240, 31 ], ar: [ 128, 209, 227 ], k: [ 143, 64, 212 ], ca: [ 61, 255, 0 ], sc: [ 230, 230, 230 ], ti: [ 191, 194, 199 ], v: [ 166, 166, 171 ], cr: [ 138, 153, 199 ], mn: [ 156, 122, 199 ], fe: [ 224, 102, 51 ], co: [ 240, 144, 160 ], ni: [ 80, 208, 80 ], cu: [ 200, 128, 51 ], zn: [ 125, 128, 176 ], ga: [ 194, 143, 143 ], ge: [ 102, 143, 143 ], as: [ 189, 128, 227 ], se: [ 255, 161, 0 ], br: [ 166, 41, 41 ], kr: [ 92, 184, 209 ], rb: [ 112, 46, 176 ], sr: [ 0, 255, 0 ], y: [ 148, 255, 255 ], zr: [ 148, 224, 224 ], nb: [ 115, 194, 201 ], mo: [ 84, 181, 181 ], tc: [ 59, 158, 158 ], ru: [ 36, 143, 143 ], rh: [ 10, 125, 140 ], pd: [ 0, 105, 133 ], ag: [ 192, 192, 192 ], cd: [ 255, 217, 143 ], in: [ 166, 117, 115 ], sn: [ 102, 128, 128 ], sb: [ 158, 99, 181 ], te: [ 212, 122, 0 ], i: [ 148, 0, 148 ], xe: [ 66, 158, 176 ], cs: [ 87, 23, 143 ], ba: [ 0, 201, 0 ], la: [ 112, 212, 255 ], ce: [ 255, 255, 199 ], pr: [ 217, 255, 199 ], nd: [ 199, 255, 199 ], pm: [ 163, 255, 199 ], sm: [ 143, 255, 199 ], eu: [ 97, 255, 199 ], gd: [ 69, 255, 199 ], tb: [ 48, 255, 199 ], dy: [ 31, 255, 199 ], ho: [ 0, 255, 156 ], er: [ 0, 230, 117 ], tm: [ 0, 212, 82 ], yb: [ 0, 191, 56 ], lu: [ 0, 171, 36 ], hf: [ 77, 194, 255 ], ta: [ 77, 166, 255 ], w: [ 33, 148, 214 ], re: [ 38, 125, 171 ], os: [ 38, 102, 150 ], ir: [ 23, 84, 135 ], pt: [ 208, 208, 224 ], au: [ 255, 209, 35 ], hg: [ 184, 184, 208 ], tl: [ 166, 84, 77 ], pb: [ 87, 89, 97 ], bi: [ 158, 79, 181 ], po: [ 171, 92, 0 ], at: [ 117, 79, 69 ], rn: [ 66, 130, 150 ], fr: [ 66, 0, 102 ], ra: [ 0, 125, 0 ], ac: [ 112, 171, 250 ], th: [ 0, 186, 255 ], pa: [ 0, 161, 255 ], u: [ 0, 143, 255 ], np: [ 0, 128, 255 ], pu: [ 0, 107, 255 ], am: [ 84, 92, 242 ], cm: [ 120, 92, 227 ], bk: [ 138, 79, 227 ], cf: [ 161, 54, 212 ], es: [ 179, 31, 212 ], fm: [ 179, 31, 186 ], md: [ 179, 13, 166 ], no: [ 189, 13, 135 ], lr: [ 199, 0, 102 ], rf: [ 204, 0, 89 ], db: [ 209, 0, 79 ], sg: [ 217, 0, 69 ], bh: [ 224, 0, 56 ], hs: [ 230, 0, 46 ], mt: [ 235, 0, 38 ], ds: [ 235, 0, 38 ], rg: [ 235, 0, 38 ], cn: [ 235, 0, 38 ], uut: [ 235, 0, 38 ], uuq: [ 235, 0, 38 ], uup: [ 235, 0, 38 ], uuh: [ 235, 0, 38 ], uus: [ 235, 0, 38 ], uuo: [ 235, 0, 38 ] };

		const atoms = [];

		const _bonds = [];
		const _bhash = {};
		const _atomMap = {};

		// parse

		const lines = text.split( '\n' );

		for ( let i = 0, l = lines.length; i < l; i ++ ) {

			if ( lines[ i ].slice( 0, 4 ) === 'ATOM' || lines[ i ].slice( 0, 6 ) === 'HETATM' ) {

				const x = parseFloat( lines[ i ].slice( 30, 37 ) );
				const y = parseFloat( lines[ i ].slice( 38, 45 ) );
				const z = parseFloat( lines[ i ].slice( 46, 53 ) );
				const index = parseInt( lines[ i ].slice( 6, 11 ) ) - 1;

				let e = trim( lines[ i ].slice( 76, 78 ) ).toLowerCase();

				if ( e === '' ) {

					e = trim( lines[ i ].slice( 12, 14 ) ).toLowerCase();

				}

				const atomData = [ x, y, z, CPK[ e ], capitalize( e ) ];

				atoms.push( atomData );
				_atomMap[ index ] = atomData;

			} else if ( lines[ i ].slice( 0, 6 ) === 'CONECT' ) {

				const satom = parseInt( lines[ i ].slice( 6, 11 ) );

				parseBond( 11, 5, satom, i );
				parseBond( 16, 5, satom, i );
				parseBond( 21, 5, satom, i );
				parseBond( 26, 5, satom, i );

			}

		}

		// build and return geometry

		return buildGeometry();

	}
```
</details>


---