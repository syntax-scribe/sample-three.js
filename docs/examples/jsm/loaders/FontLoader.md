[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FontLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 2 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 21 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/FontLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FileLoader` | `three` |
| `Loader` | `three` |
| `ShapePath` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `shapes` | `any[]` | let/var | `[]` | ✗ |
| `scale` | `number` | let/var | `size / data.resolution` | ✗ |
| `line_height` | `number` | let/var | `( data.boundingBox.yMax - data.boundingBox.yMin + data.underlineThickness ) *...` | ✗ |
| `paths` | `any[]` | let/var | `[]` | ✗ |
| `offsetX` | `number` | let/var | `0` | ✗ |
| `offsetY` | `number` | let/var | `0` | ✗ |
| `char` | `any` | let/var | `chars[ i ]` | ✗ |
| `glyph` | `any` | let/var | `data.glyphs[ char ] \|\| data.glyphs[ '?' ]` | ✗ |
| `path` | `any` | let/var | `new ShapePath()` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `cpx` | `any` | let/var | `*not shown*` | ✗ |
| `cpy` | `any` | let/var | `*not shown*` | ✗ |
| `cpx1` | `any` | let/var | `*not shown*` | ✗ |
| `cpy1` | `any` | let/var | `*not shown*` | ✗ |
| `cpx2` | `any` | let/var | `*not shown*` | ✗ |
| `cpy2` | `any` | let/var | `*not shown*` | ✗ |
| `outline` | `any` | let/var | `glyph._cachedOutline \|\| ( glyph._cachedOutline = glyph.o.split( ' ' ) )` | ✗ |
| `action` | `any` | let/var | `outline[ i ++ ]` | ✗ |


---

## Functions

### `FontLoader.load(url: string, onLoad: (arg0: Font) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded font
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Font)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Font) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `scope.parse`
- `JSON.parse`
- `onLoad`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( text ) {

			const font = scope.parse( JSON.parse( text ) );

			if ( onLoad ) onLoad( font );

		}, onProgress, onError );

	}
```
</details>

### `FontLoader.parse(json: any): Font`

**JSDoc:**
```typescript
/**
	 * Parses the given font data and returns the resulting font.
	 *
	 * @param {Object} json - The raw font data as a JSON object.
	 * @return {Font} The font.
	 */
```

**Parameters:**

- **`json`** `any`

**Returns:** `Font`

<details><summary>Code</summary>

```typescript
parse( json ) {

		return new Font( json );

	}
```
</details>

### `Font.generateShapes(text: string, size: number): Shape[]`

**JSDoc:**
```typescript
/**
	 * Generates geometry shapes from the given text and size. The result of this method
	 * should be used with {@link ShapeGeometry} to generate the actual geometry data.
	 *
	 * @param {string} text - The text.
	 * @param {number} [size=100] - The text size.
	 * @return {Array<Shape>} An array of shapes representing the text.
	 */
```

**Parameters:**

- **`text`** `string`
- **`size`** `number`

**Returns:** `Shape[]`

**Calls:**

- `createPaths`
- `shapes.push`
- `paths[ p ].toShapes`

<details><summary>Code</summary>

```typescript
generateShapes( text, size = 100 ) {

		const shapes = [];
		const paths = createPaths( text, size, this.data );

		for ( let p = 0, pl = paths.length; p < pl; p ++ ) {

			shapes.push( ...paths[ p ].toShapes() );

		}

		return shapes;

	}
```
</details>

### `createPaths(text: any, size: any, data: any): any[]`

**Parameters:**

- **`text`** `any`
- **`size`** `any`
- **`data`** `any`

**Returns:** `any[]`

**Calls:**

- `Array.from`
- `createPath`
- `paths.push`

<details><summary>Code</summary>

```typescript
function createPaths( text, size, data ) {

	const chars = Array.from( text );
	const scale = size / data.resolution;
	const line_height = ( data.boundingBox.yMax - data.boundingBox.yMin + data.underlineThickness ) * scale;

	const paths = [];

	let offsetX = 0, offsetY = 0;

	for ( let i = 0; i < chars.length; i ++ ) {

		const char = chars[ i ];

		if ( char === '\n' ) {

			offsetX = 0;
			offsetY -= line_height;

		} else {

			const ret = createPath( char, scale, offsetX, offsetY, data );
			offsetX += ret.offsetX;
			paths.push( ret.path );

		}

	}

	return paths;

}
```
</details>

### `createPath(char: any, scale: any, offsetX: any, offsetY: any, data: any): { offsetX: number; path: any; }`

**Parameters:**

- **`char`** `any`
- **`scale`** `any`
- **`offsetX`** `any`
- **`offsetY`** `any`
- **`data`** `any`

**Returns:** `{ offsetX: number; path: any; }`

**Calls:**

- `console.error`
- `glyph.o.split`
- `path.moveTo`
- `path.lineTo`
- `path.quadraticCurveTo`
- `path.bezierCurveTo`

<details><summary>Code</summary>

```typescript
function createPath( char, scale, offsetX, offsetY, data ) {

	const glyph = data.glyphs[ char ] || data.glyphs[ '?' ];

	if ( ! glyph ) {

		console.error( 'THREE.Font: character "' + char + '" does not exists in font family ' + data.familyName + '.' );

		return;

	}

	const path = new ShapePath();

	let x, y, cpx, cpy, cpx1, cpy1, cpx2, cpy2;

	if ( glyph.o ) {

		const outline = glyph._cachedOutline || ( glyph._cachedOutline = glyph.o.split( ' ' ) );

		for ( let i = 0, l = outline.length; i < l; ) {

			const action = outline[ i ++ ];

			switch ( action ) {

				case 'm': // moveTo

					x = outline[ i ++ ] * scale + offsetX;
					y = outline[ i ++ ] * scale + offsetY;

					path.moveTo( x, y );

					break;

				case 'l': // lineTo

					x = outline[ i ++ ] * scale + offsetX;
					y = outline[ i ++ ] * scale + offsetY;

					path.lineTo( x, y );

					break;

				case 'q': // quadraticCurveTo

					cpx = outline[ i ++ ] * scale + offsetX;
					cpy = outline[ i ++ ] * scale + offsetY;
					cpx1 = outline[ i ++ ] * scale + offsetX;
					cpy1 = outline[ i ++ ] * scale + offsetY;

					path.quadraticCurveTo( cpx1, cpy1, cpx, cpy );

					break;

				case 'b': // bezierCurveTo

					cpx = outline[ i ++ ] * scale + offsetX;
					cpy = outline[ i ++ ] * scale + offsetY;
					cpx1 = outline[ i ++ ] * scale + offsetX;
					cpy1 = outline[ i ++ ] * scale + offsetY;
					cpx2 = outline[ i ++ ] * scale + offsetX;
					cpy2 = outline[ i ++ ] * scale + offsetY;

					path.bezierCurveTo( cpx1, cpy1, cpx2, cpy2, cpx, cpy );

					break;

			}

		}

	}

	return { offsetX: glyph.ha * scale, path: path };

}
```
</details>


---

## Classes

### `FontLoader`

<details><summary>Class Code</summary>

```ts
class FontLoader extends Loader {

	/**
	 * Constructs a new font loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded font
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Font)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( text ) {

			const font = scope.parse( JSON.parse( text ) );

			if ( onLoad ) onLoad( font );

		}, onProgress, onError );

	}

	/**
	 * Parses the given font data and returns the resulting font.
	 *
	 * @param {Object} json - The raw font data as a JSON object.
	 * @return {Font} The font.
	 */
	parse( json ) {

		return new Font( json );

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: Font) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( text ) {

			const font = scope.parse( JSON.parse( text ) );

			if ( onLoad ) onLoad( font );

		}, onProgress, onError );

	}
```
</details>

##### `parse(json: any): Font`

<details><summary>Code</summary>

```ts
parse( json ) {

		return new Font( json );

	}
```
</details>

### `Font`

<details><summary>Class Code</summary>

```ts
class Font {

	/**
	 * Constructs a new font.
	 *
	 * @param {Object} data - The font data as JSON.
	 */
	constructor( data ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isFont = true;

		this.type = 'Font';

		/**
		 * The font data as JSON.
		 *
		 * @type {Object}
		 */
		this.data = data;

	}

	/**
	 * Generates geometry shapes from the given text and size. The result of this method
	 * should be used with {@link ShapeGeometry} to generate the actual geometry data.
	 *
	 * @param {string} text - The text.
	 * @param {number} [size=100] - The text size.
	 * @return {Array<Shape>} An array of shapes representing the text.
	 */
	generateShapes( text, size = 100 ) {

		const shapes = [];
		const paths = createPaths( text, size, this.data );

		for ( let p = 0, pl = paths.length; p < pl; p ++ ) {

			shapes.push( ...paths[ p ].toShapes() );

		}

		return shapes;

	}

}
```
</details>

#### Methods

##### `generateShapes(text: string, size: number): Shape[]`

<details><summary>Code</summary>

```ts
generateShapes( text, size = 100 ) {

		const shapes = [];
		const paths = createPaths( text, size, this.data );

		for ( let p = 0, pl = paths.length; p < pl; p ++ ) {

			shapes.push( ...paths[ p ].toShapes() );

		}

		return shapes;

	}
```
</details>


---