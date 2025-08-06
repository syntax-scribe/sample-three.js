[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TTFLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/TTFLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FileLoader` | `three` |
| `Loader` | `three` |
| `opentype` | `../libs/opentype.module.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `round` | `(x: number) => number` | let/var | `Math.round` | ✗ |
| `glyphs` | `{}` | let/var | `{}` | ✗ |
| `scale` | `number` | let/var | `( 100000 ) / ( ( font.unitsPerEm \|\| 2048 ) * 72 )` | ✗ |
| `glyphIndexMap` | `any` | let/var | `font.encoding.cmap.glyphIndexMap` | ✗ |
| `unicode` | `string` | let/var | `unicodes[ i ]` | ✗ |
| `glyph` | `any` | let/var | `font.glyphs.glyphs[ glyphIndexMap[ unicode ] ]` | ✗ |
| `token` | `{ ha: number; x_min: number; x_max: n...` | let/var | `{ ha: round( glyph.advanceWidth * scale ), x_min: round( glyph.xMin * scale )...` | ✗ |
| `paths` | `any[]` | let/var | `[]` | ✗ |
| `path` | `any` | let/var | `*not shown*` | ✗ |
| `reversed` | `any[]` | let/var | `[]` | ✗ |
| `result` | `{ type: string; x: any; y: any; }` | let/var | `{ type: 'm', x: p[ p.length - 1 ].x, y: p[ p.length - 1 ].y }` | ✗ |
| `command` | `any` | let/var | `p[ i ]` | ✗ |
| `result` | `{ type: any; }` | let/var | `{ type: command.type }` | ✗ |


---

## Functions

### `TTFLoader.load(url: string, onLoad: (arg0: any) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded TTF asset
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
- `loader.setResponseType`
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

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer ) );

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

### `TTFLoader.parse(arraybuffer: ArrayBuffer): any`

**JSDoc:**
```typescript
/**
	 * Parses the given TTF data and returns a JSON for creating a font.
	 *
	 * @param {ArrayBuffer} arraybuffer - The raw TTF data as an array buffer.
	 * @return {Object} The result JSON.
	 */
```

**Parameters:**

- **`arraybuffer`** `ArrayBuffer`

**Returns:** `any`

**Calls:**

- `Object.keys`
- `round`
- `reverseCommands`
- `glyph.path.commands.forEach`
- `command.type.toLowerCase`
- `Array.isArray`
- `glyph.unicodes.forEach`
- `String.fromCodePoint`
- `font.getEnglishName`
- `commands.forEach`
- `c.type.toLowerCase`
- `paths.push`
- `path.push`
- `paths.forEach`
- `reversed.push`
- `convert`
- `opentype.parse`

<details><summary>Code</summary>

```typescript
parse( arraybuffer ) {

		function convert( font, reversed ) {

			const round = Math.round;

			const glyphs = {};
			const scale = ( 100000 ) / ( ( font.unitsPerEm || 2048 ) * 72 );

			const glyphIndexMap = font.encoding.cmap.glyphIndexMap;
			const unicodes = Object.keys( glyphIndexMap );

			for ( let i = 0; i < unicodes.length; i ++ ) {

				const unicode = unicodes[ i ];
				const glyph = font.glyphs.glyphs[ glyphIndexMap[ unicode ] ];

				if ( unicode !== undefined ) {

					const token = {
						ha: round( glyph.advanceWidth * scale ),
						x_min: round( glyph.xMin * scale ),
						x_max: round( glyph.xMax * scale ),
						o: ''
					};

					if ( reversed ) {

						glyph.path.commands = reverseCommands( glyph.path.commands );

					}

					glyph.path.commands.forEach( function ( command ) {

						if ( command.type.toLowerCase() === 'c' ) {

							command.type = 'b';

						}

						token.o += command.type.toLowerCase() + ' ';

						if ( command.x !== undefined && command.y !== undefined ) {

							token.o += round( command.x * scale ) + ' ' + round( command.y * scale ) + ' ';

						}

						if ( command.x1 !== undefined && command.y1 !== undefined ) {

							token.o += round( command.x1 * scale ) + ' ' + round( command.y1 * scale ) + ' ';

						}

						if ( command.x2 !== undefined && command.y2 !== undefined ) {

							token.o += round( command.x2 * scale ) + ' ' + round( command.y2 * scale ) + ' ';

						}

					} );

					if ( Array.isArray( glyph.unicodes ) && glyph.unicodes.length > 0 ) {
						
						glyph.unicodes.forEach( function ( unicode ) {
							
							glyphs[ String.fromCodePoint( unicode ) ] = token;
							
						} );
						
					} else {

						glyphs[ String.fromCodePoint( glyph.unicode ) ] = token;

					}

				}

			}

			return {
				glyphs: glyphs,
				familyName: font.getEnglishName( 'fullName' ),
				ascender: round( font.ascender * scale ),
				descender: round( font.descender * scale ),
				underlinePosition: font.tables.post.underlinePosition,
				underlineThickness: font.tables.post.underlineThickness,
				boundingBox: {
					xMin: font.tables.head.xMin,
					xMax: font.tables.head.xMax,
					yMin: font.tables.head.yMin,
					yMax: font.tables.head.yMax
				},
				resolution: 1000,
				original_font_information: font.tables.name
			};

		}

		function reverseCommands( commands ) {

			const paths = [];
			let path;

			commands.forEach( function ( c ) {

				if ( c.type.toLowerCase() === 'm' ) {

					path = [ c ];
					paths.push( path );

				} else if ( c.type.toLowerCase() !== 'z' ) {

					path.push( c );

				}

			} );

			const reversed = [];

			paths.forEach( function ( p ) {

				const result = {
					type: 'm',
					x: p[ p.length - 1 ].x,
					y: p[ p.length - 1 ].y
				};

				reversed.push( result );

				for ( let i = p.length - 1; i > 0; i -- ) {

					const command = p[ i ];
					const result = { type: command.type };

					if ( command.x2 !== undefined && command.y2 !== undefined ) {

						result.x1 = command.x2;
						result.y1 = command.y2;
						result.x2 = command.x1;
						result.y2 = command.y1;

					} else if ( command.x1 !== undefined && command.y1 !== undefined ) {

						result.x1 = command.x1;
						result.y1 = command.y1;

					}

					result.x = p[ i - 1 ].x;
					result.y = p[ i - 1 ].y;
					reversed.push( result );

				}

			} );

			return reversed;

		}

		return convert( opentype.parse( arraybuffer ), this.reversed );

	}
```
</details>

### `convert(font: any, reversed: any): { glyphs: {}; familyName: any; ascender: number; descender: number; underlinePosition: any; underlineThickness: any; boundingBox: { xMin: any; xMax: any; yMin: any; yMax: any; }; resolution: number; original_font_information: any; }`

**Parameters:**

- **`font`** `any`
- **`reversed`** `any`

**Returns:** `{ glyphs: {}; familyName: any; ascender: number; descender: number; underlinePosition: any; underlineThickness: any; boundingBox: { xMin: any; xMax: any; yMin: any; yMax: any; }; resolution: number; original_font_information: any; }`

**Calls:**

- `Object.keys`
- `round`
- `reverseCommands`
- `glyph.path.commands.forEach`
- `command.type.toLowerCase`
- `Array.isArray`
- `glyph.unicodes.forEach`
- `String.fromCodePoint`
- `font.getEnglishName`

<details><summary>Code</summary>

```typescript
function convert( font, reversed ) {

			const round = Math.round;

			const glyphs = {};
			const scale = ( 100000 ) / ( ( font.unitsPerEm || 2048 ) * 72 );

			const glyphIndexMap = font.encoding.cmap.glyphIndexMap;
			const unicodes = Object.keys( glyphIndexMap );

			for ( let i = 0; i < unicodes.length; i ++ ) {

				const unicode = unicodes[ i ];
				const glyph = font.glyphs.glyphs[ glyphIndexMap[ unicode ] ];

				if ( unicode !== undefined ) {

					const token = {
						ha: round( glyph.advanceWidth * scale ),
						x_min: round( glyph.xMin * scale ),
						x_max: round( glyph.xMax * scale ),
						o: ''
					};

					if ( reversed ) {

						glyph.path.commands = reverseCommands( glyph.path.commands );

					}

					glyph.path.commands.forEach( function ( command ) {

						if ( command.type.toLowerCase() === 'c' ) {

							command.type = 'b';

						}

						token.o += command.type.toLowerCase() + ' ';

						if ( command.x !== undefined && command.y !== undefined ) {

							token.o += round( command.x * scale ) + ' ' + round( command.y * scale ) + ' ';

						}

						if ( command.x1 !== undefined && command.y1 !== undefined ) {

							token.o += round( command.x1 * scale ) + ' ' + round( command.y1 * scale ) + ' ';

						}

						if ( command.x2 !== undefined && command.y2 !== undefined ) {

							token.o += round( command.x2 * scale ) + ' ' + round( command.y2 * scale ) + ' ';

						}

					} );

					if ( Array.isArray( glyph.unicodes ) && glyph.unicodes.length > 0 ) {
						
						glyph.unicodes.forEach( function ( unicode ) {
							
							glyphs[ String.fromCodePoint( unicode ) ] = token;
							
						} );
						
					} else {

						glyphs[ String.fromCodePoint( glyph.unicode ) ] = token;

					}

				}

			}

			return {
				glyphs: glyphs,
				familyName: font.getEnglishName( 'fullName' ),
				ascender: round( font.ascender * scale ),
				descender: round( font.descender * scale ),
				underlinePosition: font.tables.post.underlinePosition,
				underlineThickness: font.tables.post.underlineThickness,
				boundingBox: {
					xMin: font.tables.head.xMin,
					xMax: font.tables.head.xMax,
					yMin: font.tables.head.yMin,
					yMax: font.tables.head.yMax
				},
				resolution: 1000,
				original_font_information: font.tables.name
			};

		}
```
</details>

### `reverseCommands(commands: any): any[]`

**Parameters:**

- **`commands`** `any`

**Returns:** `any[]`

**Calls:**

- `commands.forEach`
- `c.type.toLowerCase`
- `paths.push`
- `path.push`
- `paths.forEach`
- `reversed.push`

<details><summary>Code</summary>

```typescript
function reverseCommands( commands ) {

			const paths = [];
			let path;

			commands.forEach( function ( c ) {

				if ( c.type.toLowerCase() === 'm' ) {

					path = [ c ];
					paths.push( path );

				} else if ( c.type.toLowerCase() !== 'z' ) {

					path.push( c );

				}

			} );

			const reversed = [];

			paths.forEach( function ( p ) {

				const result = {
					type: 'm',
					x: p[ p.length - 1 ].x,
					y: p[ p.length - 1 ].y
				};

				reversed.push( result );

				for ( let i = p.length - 1; i > 0; i -- ) {

					const command = p[ i ];
					const result = { type: command.type };

					if ( command.x2 !== undefined && command.y2 !== undefined ) {

						result.x1 = command.x2;
						result.y1 = command.y2;
						result.x2 = command.x1;
						result.y2 = command.y1;

					} else if ( command.x1 !== undefined && command.y1 !== undefined ) {

						result.x1 = command.x1;
						result.y1 = command.y1;

					}

					result.x = p[ i - 1 ].x;
					result.y = p[ i - 1 ].y;
					reversed.push( result );

				}

			} );

			return reversed;

		}
```
</details>


---

## Classes

### `TTFLoader`

<details><summary>Class Code</summary>

```ts
class TTFLoader extends Loader {

	/**
	 * Constructs a new TTF loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * Whether the TTF commands should be reversed or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.reversed = false;

	}

	/**
	 * Starts loading from the given URL and passes the loaded TTF asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Object)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer ) );

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
	 * Parses the given TTF data and returns a JSON for creating a font.
	 *
	 * @param {ArrayBuffer} arraybuffer - The raw TTF data as an array buffer.
	 * @return {Object} The result JSON.
	 */
	parse( arraybuffer ) {

		function convert( font, reversed ) {

			const round = Math.round;

			const glyphs = {};
			const scale = ( 100000 ) / ( ( font.unitsPerEm || 2048 ) * 72 );

			const glyphIndexMap = font.encoding.cmap.glyphIndexMap;
			const unicodes = Object.keys( glyphIndexMap );

			for ( let i = 0; i < unicodes.length; i ++ ) {

				const unicode = unicodes[ i ];
				const glyph = font.glyphs.glyphs[ glyphIndexMap[ unicode ] ];

				if ( unicode !== undefined ) {

					const token = {
						ha: round( glyph.advanceWidth * scale ),
						x_min: round( glyph.xMin * scale ),
						x_max: round( glyph.xMax * scale ),
						o: ''
					};

					if ( reversed ) {

						glyph.path.commands = reverseCommands( glyph.path.commands );

					}

					glyph.path.commands.forEach( function ( command ) {

						if ( command.type.toLowerCase() === 'c' ) {

							command.type = 'b';

						}

						token.o += command.type.toLowerCase() + ' ';

						if ( command.x !== undefined && command.y !== undefined ) {

							token.o += round( command.x * scale ) + ' ' + round( command.y * scale ) + ' ';

						}

						if ( command.x1 !== undefined && command.y1 !== undefined ) {

							token.o += round( command.x1 * scale ) + ' ' + round( command.y1 * scale ) + ' ';

						}

						if ( command.x2 !== undefined && command.y2 !== undefined ) {

							token.o += round( command.x2 * scale ) + ' ' + round( command.y2 * scale ) + ' ';

						}

					} );

					if ( Array.isArray( glyph.unicodes ) && glyph.unicodes.length > 0 ) {
						
						glyph.unicodes.forEach( function ( unicode ) {
							
							glyphs[ String.fromCodePoint( unicode ) ] = token;
							
						} );
						
					} else {

						glyphs[ String.fromCodePoint( glyph.unicode ) ] = token;

					}

				}

			}

			return {
				glyphs: glyphs,
				familyName: font.getEnglishName( 'fullName' ),
				ascender: round( font.ascender * scale ),
				descender: round( font.descender * scale ),
				underlinePosition: font.tables.post.underlinePosition,
				underlineThickness: font.tables.post.underlineThickness,
				boundingBox: {
					xMin: font.tables.head.xMin,
					xMax: font.tables.head.xMax,
					yMin: font.tables.head.yMin,
					yMax: font.tables.head.yMax
				},
				resolution: 1000,
				original_font_information: font.tables.name
			};

		}

		function reverseCommands( commands ) {

			const paths = [];
			let path;

			commands.forEach( function ( c ) {

				if ( c.type.toLowerCase() === 'm' ) {

					path = [ c ];
					paths.push( path );

				} else if ( c.type.toLowerCase() !== 'z' ) {

					path.push( c );

				}

			} );

			const reversed = [];

			paths.forEach( function ( p ) {

				const result = {
					type: 'm',
					x: p[ p.length - 1 ].x,
					y: p[ p.length - 1 ].y
				};

				reversed.push( result );

				for ( let i = p.length - 1; i > 0; i -- ) {

					const command = p[ i ];
					const result = { type: command.type };

					if ( command.x2 !== undefined && command.y2 !== undefined ) {

						result.x1 = command.x2;
						result.y1 = command.y2;
						result.x2 = command.x1;
						result.y2 = command.y1;

					} else if ( command.x1 !== undefined && command.y1 !== undefined ) {

						result.x1 = command.x1;
						result.y1 = command.y1;

					}

					result.x = p[ i - 1 ].x;
					result.y = p[ i - 1 ].y;
					reversed.push( result );

				}

			} );

			return reversed;

		}

		return convert( opentype.parse( arraybuffer ), this.reversed );

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

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer ) );

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

##### `parse(arraybuffer: ArrayBuffer): any`

<details><summary>Code</summary>

```ts
parse( arraybuffer ) {

		function convert( font, reversed ) {

			const round = Math.round;

			const glyphs = {};
			const scale = ( 100000 ) / ( ( font.unitsPerEm || 2048 ) * 72 );

			const glyphIndexMap = font.encoding.cmap.glyphIndexMap;
			const unicodes = Object.keys( glyphIndexMap );

			for ( let i = 0; i < unicodes.length; i ++ ) {

				const unicode = unicodes[ i ];
				const glyph = font.glyphs.glyphs[ glyphIndexMap[ unicode ] ];

				if ( unicode !== undefined ) {

					const token = {
						ha: round( glyph.advanceWidth * scale ),
						x_min: round( glyph.xMin * scale ),
						x_max: round( glyph.xMax * scale ),
						o: ''
					};

					if ( reversed ) {

						glyph.path.commands = reverseCommands( glyph.path.commands );

					}

					glyph.path.commands.forEach( function ( command ) {

						if ( command.type.toLowerCase() === 'c' ) {

							command.type = 'b';

						}

						token.o += command.type.toLowerCase() + ' ';

						if ( command.x !== undefined && command.y !== undefined ) {

							token.o += round( command.x * scale ) + ' ' + round( command.y * scale ) + ' ';

						}

						if ( command.x1 !== undefined && command.y1 !== undefined ) {

							token.o += round( command.x1 * scale ) + ' ' + round( command.y1 * scale ) + ' ';

						}

						if ( command.x2 !== undefined && command.y2 !== undefined ) {

							token.o += round( command.x2 * scale ) + ' ' + round( command.y2 * scale ) + ' ';

						}

					} );

					if ( Array.isArray( glyph.unicodes ) && glyph.unicodes.length > 0 ) {
						
						glyph.unicodes.forEach( function ( unicode ) {
							
							glyphs[ String.fromCodePoint( unicode ) ] = token;
							
						} );
						
					} else {

						glyphs[ String.fromCodePoint( glyph.unicode ) ] = token;

					}

				}

			}

			return {
				glyphs: glyphs,
				familyName: font.getEnglishName( 'fullName' ),
				ascender: round( font.ascender * scale ),
				descender: round( font.descender * scale ),
				underlinePosition: font.tables.post.underlinePosition,
				underlineThickness: font.tables.post.underlineThickness,
				boundingBox: {
					xMin: font.tables.head.xMin,
					xMax: font.tables.head.xMax,
					yMin: font.tables.head.yMin,
					yMax: font.tables.head.yMax
				},
				resolution: 1000,
				original_font_information: font.tables.name
			};

		}

		function reverseCommands( commands ) {

			const paths = [];
			let path;

			commands.forEach( function ( c ) {

				if ( c.type.toLowerCase() === 'm' ) {

					path = [ c ];
					paths.push( path );

				} else if ( c.type.toLowerCase() !== 'z' ) {

					path.push( c );

				}

			} );

			const reversed = [];

			paths.forEach( function ( p ) {

				const result = {
					type: 'm',
					x: p[ p.length - 1 ].x,
					y: p[ p.length - 1 ].y
				};

				reversed.push( result );

				for ( let i = p.length - 1; i > 0; i -- ) {

					const command = p[ i ];
					const result = { type: command.type };

					if ( command.x2 !== undefined && command.y2 !== undefined ) {

						result.x1 = command.x2;
						result.y1 = command.y2;
						result.x2 = command.x1;
						result.y2 = command.y1;

					} else if ( command.x1 !== undefined && command.y1 !== undefined ) {

						result.x1 = command.x1;
						result.y1 = command.y1;

					}

					result.x = p[ i - 1 ].x;
					result.y = p[ i - 1 ].y;
					reversed.push( result );

				}

			} );

			return reversed;

		}

		return convert( opentype.parse( arraybuffer ), this.reversed );

	}
```
</details>


---