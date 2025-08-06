[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `STLLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 49 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/STLLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Loader` | `three` |
| `Vector3` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `reader` | `DataView<any>` | let/var | `new DataView( data )` | ✗ |
| `face_size` | `number` | let/var | `( 32 / 8 * 3 ) + ( ( 32 / 8 * 3 ) * 3 ) + ( 16 / 8 )` | ✗ |
| `expect` | `number` | let/var | `80 + ( 32 / 8 ) + ( n_faces * face_size )` | ✗ |
| `solid` | `number[]` | let/var | `[ 115, 111, 108, 105, 100 ]` | ✗ |
| `reader` | `DataView<any>` | let/var | `new DataView( data )` | ✗ |
| `r` | `any` | let/var | `*not shown*` | ✗ |
| `g` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `any` | let/var | `*not shown*` | ✗ |
| `hasColors` | `boolean` | let/var | `false` | ✗ |
| `colors` | `any` | let/var | `*not shown*` | ✗ |
| `defaultR` | `any` | let/var | `*not shown*` | ✗ |
| `defaultG` | `any` | let/var | `*not shown*` | ✗ |
| `defaultB` | `any` | let/var | `*not shown*` | ✗ |
| `alpha` | `any` | let/var | `*not shown*` | ✗ |
| `dataOffset` | `84` | let/var | `84` | ✗ |
| `faceLength` | `number` | let/var | `12 * 4 + 2` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `vertices` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( faces * 3 * 3 )` | ✗ |
| `normals` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( faces * 3 * 3 )` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `start` | `number` | let/var | `dataOffset + face * faceLength` | ✗ |
| `vertexstart` | `number` | let/var | `start + i * 12` | ✗ |
| `componentIdx` | `number` | let/var | `( face * 3 * 3 ) + ( ( i - 1 ) * 3 )` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `patternSolid` | `RegExp` | let/var | `/solid([\s\S]*?)endsolid/g` | ✗ |
| `patternFace` | `RegExp` | let/var | `/facet([\s\S]*?)endfacet/g` | ✗ |
| `patternName` | `RegExp` | let/var | `/solid\s(.+)/` | ✗ |
| `faceCounter` | `number` | let/var | `0` | ✗ |
| `patternFloat` | `string` | let/var | `/[\s]+([+-]?(?:\d*)(?:\.\d*)?(?:[eE][+-]?\d+)?)/.source` | ✗ |
| `patternVertex` | `RegExp` | let/var | `new RegExp( 'vertex' + patternFloat + patternFloat + patternFloat, 'g' )` | ✗ |
| `patternNormal` | `RegExp` | let/var | `new RegExp( 'normal' + patternFloat + patternFloat + patternFloat, 'g' )` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `groupNames` | `any[]` | let/var | `[]` | ✗ |
| `normal` | `any` | let/var | `new Vector3()` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `groupCount` | `number` | let/var | `0` | ✗ |
| `startVertex` | `number` | let/var | `0` | ✗ |
| `endVertex` | `number` | let/var | `0` | ✗ |
| `solid` | `string` | let/var | `result[ 0 ]` | ✗ |
| `name` | `string` | let/var | `( result = patternName.exec( solid ) ) !== null ? result[ 1 ] : ''` | ✗ |
| `vertexCountPerFace` | `number` | let/var | `0` | ✗ |
| `normalCountPerFace` | `number` | let/var | `0` | ✗ |
| `text` | `string` | let/var | `result[ 0 ]` | ✗ |
| `start` | `number` | let/var | `startVertex` | ✗ |
| `count` | `number` | let/var | `endVertex - startVertex` | ✗ |
| `array_buffer` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( buffer.length )` | ✗ |


---

## Functions

### `STLLoader.load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded STL asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: BufferGeometry) => any`
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

### `STLLoader.parse(data: ArrayBuffer): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Parses the given STL data and returns the resulting geometry.
	 *
	 * @param {ArrayBuffer} data - The raw STL data as an array buffer.
	 * @return {BufferGeometry} The parsed geometry.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`

**Returns:** `BufferGeometry`

**Calls:**

- `reader.getUint32`
- `matchDataViewAt`
- `reader.getUint8`
- `reader.getFloat32`
- `reader.getUint16`
- `color.setRGB`
- `geometry.setAttribute`
- `patternSolid.exec`
- `patternName.exec`
- `groupNames.push`
- `patternFace.exec`
- `patternNormal.exec`
- `parseFloat`
- `patternVertex.exec`
- `vertices.push`
- `normals.push`
- `console.error`
- `geometry.addGroup`
- `new TextDecoder().decode`
- `buffer.charCodeAt`
- `ensureBinary`
- `isBinary`
- `parseBinary`
- `parseASCII`
- `ensureString`

**Internal Comments:**
```
// An ASCII STL data must begin with 'solid ' as the first six bytes. (x2)
// However, ASCII STLs lacking the SPACE after the 'd' are known to be (x2)
// plentiful.  So, check the first 5 bytes for 'solid'. (x2)
// Several encodings, such as UTF-8, precede the text with up to 5 bytes: (x2)
// https://en.wikipedia.org/wiki/Byte_order_mark#Byte_order_marks_by_encoding (x2)
// Search for "solid" to start anywhere after those prefixes. (x2)
// US-ASCII ordinal values for 's', 'o', 'l', 'i', 'd' (x2)
// If "solid" text is matched to the current offset, declare it to be an ASCII STL.
// Couldn't find "solid" text at the beginning; it is binary STL.
// Check if each byte in query matches the corresponding byte from the current offset
// process STL header
// check for default color in header ("COLOR=rgba" sequence).
// facet has its own unique color (x3)
// every face have to own ONE valid normal
// each face have to own THREE valid vertices
// start (x2)
```

<details><summary>Code</summary>

```typescript
parse( data ) {

		function isBinary( data ) {

			const reader = new DataView( data );
			const face_size = ( 32 / 8 * 3 ) + ( ( 32 / 8 * 3 ) * 3 ) + ( 16 / 8 );
			const n_faces = reader.getUint32( 80, true );
			const expect = 80 + ( 32 / 8 ) + ( n_faces * face_size );

			if ( expect === reader.byteLength ) {

				return true;

			}

			// An ASCII STL data must begin with 'solid ' as the first six bytes.
			// However, ASCII STLs lacking the SPACE after the 'd' are known to be
			// plentiful.  So, check the first 5 bytes for 'solid'.

			// Several encodings, such as UTF-8, precede the text with up to 5 bytes:
			// https://en.wikipedia.org/wiki/Byte_order_mark#Byte_order_marks_by_encoding
			// Search for "solid" to start anywhere after those prefixes.

			// US-ASCII ordinal values for 's', 'o', 'l', 'i', 'd'

			const solid = [ 115, 111, 108, 105, 100 ];

			for ( let off = 0; off < 5; off ++ ) {

				// If "solid" text is matched to the current offset, declare it to be an ASCII STL.

				if ( matchDataViewAt( solid, reader, off ) ) return false;

			}

			// Couldn't find "solid" text at the beginning; it is binary STL.

			return true;

		}

		function matchDataViewAt( query, reader, offset ) {

			// Check if each byte in query matches the corresponding byte from the current offset

			for ( let i = 0, il = query.length; i < il; i ++ ) {

				if ( query[ i ] !== reader.getUint8( offset + i ) ) return false;

			}

			return true;

		}

		function parseBinary( data ) {

			const reader = new DataView( data );
			const faces = reader.getUint32( 80, true );

			let r, g, b, hasColors = false, colors;
			let defaultR, defaultG, defaultB, alpha;

			// process STL header
			// check for default color in header ("COLOR=rgba" sequence).

			for ( let index = 0; index < 80 - 10; index ++ ) {

				if ( ( reader.getUint32( index, false ) == 0x434F4C4F /*COLO*/ ) &&
					( reader.getUint8( index + 4 ) == 0x52 /*'R'*/ ) &&
					( reader.getUint8( index + 5 ) == 0x3D /*'='*/ ) ) {

					hasColors = true;
					colors = new Float32Array( faces * 3 * 3 );

					defaultR = reader.getUint8( index + 6 ) / 255;
					defaultG = reader.getUint8( index + 7 ) / 255;
					defaultB = reader.getUint8( index + 8 ) / 255;
					alpha = reader.getUint8( index + 9 ) / 255;

				}

			}

			const dataOffset = 84;
			const faceLength = 12 * 4 + 2;

			const geometry = new BufferGeometry();

			const vertices = new Float32Array( faces * 3 * 3 );
			const normals = new Float32Array( faces * 3 * 3 );

			const color = new Color();

			for ( let face = 0; face < faces; face ++ ) {

				const start = dataOffset + face * faceLength;
				const normalX = reader.getFloat32( start, true );
				const normalY = reader.getFloat32( start + 4, true );
				const normalZ = reader.getFloat32( start + 8, true );

				if ( hasColors ) {

					const packedColor = reader.getUint16( start + 48, true );

					if ( ( packedColor & 0x8000 ) === 0 ) {

						// facet has its own unique color

						r = ( packedColor & 0x1F ) / 31;
						g = ( ( packedColor >> 5 ) & 0x1F ) / 31;
						b = ( ( packedColor >> 10 ) & 0x1F ) / 31;

					} else {

						r = defaultR;
						g = defaultG;
						b = defaultB;

					}

				}

				for ( let i = 1; i <= 3; i ++ ) {

					const vertexstart = start + i * 12;
					const componentIdx = ( face * 3 * 3 ) + ( ( i - 1 ) * 3 );

					vertices[ componentIdx ] = reader.getFloat32( vertexstart, true );
					vertices[ componentIdx + 1 ] = reader.getFloat32( vertexstart + 4, true );
					vertices[ componentIdx + 2 ] = reader.getFloat32( vertexstart + 8, true );

					normals[ componentIdx ] = normalX;
					normals[ componentIdx + 1 ] = normalY;
					normals[ componentIdx + 2 ] = normalZ;

					if ( hasColors ) {

						color.setRGB( r, g, b, SRGBColorSpace );

						colors[ componentIdx ] = color.r;
						colors[ componentIdx + 1 ] = color.g;
						colors[ componentIdx + 2 ] = color.b;

					}

				}

			}

			geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );
			geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

			if ( hasColors ) {

				geometry.setAttribute( 'color', new BufferAttribute( colors, 3 ) );
				geometry.hasColors = true;
				geometry.alpha = alpha;

			}

			return geometry;

		}

		function parseASCII( data ) {

			const geometry = new BufferGeometry();
			const patternSolid = /solid([\s\S]*?)endsolid/g;
			const patternFace = /facet([\s\S]*?)endfacet/g;
			const patternName = /solid\s(.+)/;
			let faceCounter = 0;

			const patternFloat = /[\s]+([+-]?(?:\d*)(?:\.\d*)?(?:[eE][+-]?\d+)?)/.source;
			const patternVertex = new RegExp( 'vertex' + patternFloat + patternFloat + patternFloat, 'g' );
			const patternNormal = new RegExp( 'normal' + patternFloat + patternFloat + patternFloat, 'g' );

			const vertices = [];
			const normals = [];
			const groupNames = [];

			const normal = new Vector3();

			let result;

			let groupCount = 0;
			let startVertex = 0;
			let endVertex = 0;

			while ( ( result = patternSolid.exec( data ) ) !== null ) {

				startVertex = endVertex;

				const solid = result[ 0 ];

				const name = ( result = patternName.exec( solid ) ) !== null ? result[ 1 ] : '';
				groupNames.push( name );

				while ( ( result = patternFace.exec( solid ) ) !== null ) {

					let vertexCountPerFace = 0;
					let normalCountPerFace = 0;

					const text = result[ 0 ];

					while ( ( result = patternNormal.exec( text ) ) !== null ) {

						normal.x = parseFloat( result[ 1 ] );
						normal.y = parseFloat( result[ 2 ] );
						normal.z = parseFloat( result[ 3 ] );
						normalCountPerFace ++;

					}

					while ( ( result = patternVertex.exec( text ) ) !== null ) {

						vertices.push( parseFloat( result[ 1 ] ), parseFloat( result[ 2 ] ), parseFloat( result[ 3 ] ) );
						normals.push( normal.x, normal.y, normal.z );
						vertexCountPerFace ++;
						endVertex ++;

					}

					// every face have to own ONE valid normal

					if ( normalCountPerFace !== 1 ) {

						console.error( 'THREE.STLLoader: Something isn\'t right with the normal of face number ' + faceCounter );

					}

					// each face have to own THREE valid vertices

					if ( vertexCountPerFace !== 3 ) {

						console.error( 'THREE.STLLoader: Something isn\'t right with the vertices of face number ' + faceCounter );

					}

					faceCounter ++;

				}

				const start = startVertex;
				const count = endVertex - startVertex;

				geometry.userData.groupNames = groupNames;

				geometry.addGroup( start, count, groupCount );
				groupCount ++;

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
			geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

			return geometry;

		}

		function ensureString( buffer ) {

			if ( typeof buffer !== 'string' ) {

				return new TextDecoder().decode( buffer );

			}

			return buffer;

		}

		function ensureBinary( buffer ) {

			if ( typeof buffer === 'string' ) {

				const array_buffer = new Uint8Array( buffer.length );
				for ( let i = 0; i < buffer.length; i ++ ) {

					array_buffer[ i ] = buffer.charCodeAt( i ) & 0xff; // implicitly assumes little-endian

				}

				return array_buffer.buffer || array_buffer;

			} else {

				return buffer;

			}

		}

		// start

		const binData = ensureBinary( data );

		return isBinary( binData ) ? parseBinary( binData ) : parseASCII( ensureString( data ) );

	}
```
</details>

### `isBinary(data: any): boolean`

**Parameters:**

- **`data`** `any`

**Returns:** `boolean`

**Calls:**

- `reader.getUint32`
- `matchDataViewAt`

**Internal Comments:**
```
// An ASCII STL data must begin with 'solid ' as the first six bytes. (x2)
// However, ASCII STLs lacking the SPACE after the 'd' are known to be (x2)
// plentiful.  So, check the first 5 bytes for 'solid'. (x2)
// Several encodings, such as UTF-8, precede the text with up to 5 bytes: (x2)
// https://en.wikipedia.org/wiki/Byte_order_mark#Byte_order_marks_by_encoding (x2)
// Search for "solid" to start anywhere after those prefixes. (x2)
// US-ASCII ordinal values for 's', 'o', 'l', 'i', 'd' (x2)
// If "solid" text is matched to the current offset, declare it to be an ASCII STL.
// Couldn't find "solid" text at the beginning; it is binary STL.
```

<details><summary>Code</summary>

```typescript
function isBinary( data ) {

			const reader = new DataView( data );
			const face_size = ( 32 / 8 * 3 ) + ( ( 32 / 8 * 3 ) * 3 ) + ( 16 / 8 );
			const n_faces = reader.getUint32( 80, true );
			const expect = 80 + ( 32 / 8 ) + ( n_faces * face_size );

			if ( expect === reader.byteLength ) {

				return true;

			}

			// An ASCII STL data must begin with 'solid ' as the first six bytes.
			// However, ASCII STLs lacking the SPACE after the 'd' are known to be
			// plentiful.  So, check the first 5 bytes for 'solid'.

			// Several encodings, such as UTF-8, precede the text with up to 5 bytes:
			// https://en.wikipedia.org/wiki/Byte_order_mark#Byte_order_marks_by_encoding
			// Search for "solid" to start anywhere after those prefixes.

			// US-ASCII ordinal values for 's', 'o', 'l', 'i', 'd'

			const solid = [ 115, 111, 108, 105, 100 ];

			for ( let off = 0; off < 5; off ++ ) {

				// If "solid" text is matched to the current offset, declare it to be an ASCII STL.

				if ( matchDataViewAt( solid, reader, off ) ) return false;

			}

			// Couldn't find "solid" text at the beginning; it is binary STL.

			return true;

		}
```
</details>

### `matchDataViewAt(query: any, reader: any, offset: any): boolean`

**Parameters:**

- **`query`** `any`
- **`reader`** `any`
- **`offset`** `any`

**Returns:** `boolean`

**Calls:**

- `reader.getUint8`

**Internal Comments:**
```
// Check if each byte in query matches the corresponding byte from the current offset
```

<details><summary>Code</summary>

```typescript
function matchDataViewAt( query, reader, offset ) {

			// Check if each byte in query matches the corresponding byte from the current offset

			for ( let i = 0, il = query.length; i < il; i ++ ) {

				if ( query[ i ] !== reader.getUint8( offset + i ) ) return false;

			}

			return true;

		}
```
</details>

### `parseBinary(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `reader.getUint32`
- `reader.getUint8`
- `reader.getFloat32`
- `reader.getUint16`
- `color.setRGB`
- `geometry.setAttribute`

**Internal Comments:**
```
// process STL header
// check for default color in header ("COLOR=rgba" sequence).
// facet has its own unique color (x3)
```

<details><summary>Code</summary>

```typescript
function parseBinary( data ) {

			const reader = new DataView( data );
			const faces = reader.getUint32( 80, true );

			let r, g, b, hasColors = false, colors;
			let defaultR, defaultG, defaultB, alpha;

			// process STL header
			// check for default color in header ("COLOR=rgba" sequence).

			for ( let index = 0; index < 80 - 10; index ++ ) {

				if ( ( reader.getUint32( index, false ) == 0x434F4C4F /*COLO*/ ) &&
					( reader.getUint8( index + 4 ) == 0x52 /*'R'*/ ) &&
					( reader.getUint8( index + 5 ) == 0x3D /*'='*/ ) ) {

					hasColors = true;
					colors = new Float32Array( faces * 3 * 3 );

					defaultR = reader.getUint8( index + 6 ) / 255;
					defaultG = reader.getUint8( index + 7 ) / 255;
					defaultB = reader.getUint8( index + 8 ) / 255;
					alpha = reader.getUint8( index + 9 ) / 255;

				}

			}

			const dataOffset = 84;
			const faceLength = 12 * 4 + 2;

			const geometry = new BufferGeometry();

			const vertices = new Float32Array( faces * 3 * 3 );
			const normals = new Float32Array( faces * 3 * 3 );

			const color = new Color();

			for ( let face = 0; face < faces; face ++ ) {

				const start = dataOffset + face * faceLength;
				const normalX = reader.getFloat32( start, true );
				const normalY = reader.getFloat32( start + 4, true );
				const normalZ = reader.getFloat32( start + 8, true );

				if ( hasColors ) {

					const packedColor = reader.getUint16( start + 48, true );

					if ( ( packedColor & 0x8000 ) === 0 ) {

						// facet has its own unique color

						r = ( packedColor & 0x1F ) / 31;
						g = ( ( packedColor >> 5 ) & 0x1F ) / 31;
						b = ( ( packedColor >> 10 ) & 0x1F ) / 31;

					} else {

						r = defaultR;
						g = defaultG;
						b = defaultB;

					}

				}

				for ( let i = 1; i <= 3; i ++ ) {

					const vertexstart = start + i * 12;
					const componentIdx = ( face * 3 * 3 ) + ( ( i - 1 ) * 3 );

					vertices[ componentIdx ] = reader.getFloat32( vertexstart, true );
					vertices[ componentIdx + 1 ] = reader.getFloat32( vertexstart + 4, true );
					vertices[ componentIdx + 2 ] = reader.getFloat32( vertexstart + 8, true );

					normals[ componentIdx ] = normalX;
					normals[ componentIdx + 1 ] = normalY;
					normals[ componentIdx + 2 ] = normalZ;

					if ( hasColors ) {

						color.setRGB( r, g, b, SRGBColorSpace );

						colors[ componentIdx ] = color.r;
						colors[ componentIdx + 1 ] = color.g;
						colors[ componentIdx + 2 ] = color.b;

					}

				}

			}

			geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );
			geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

			if ( hasColors ) {

				geometry.setAttribute( 'color', new BufferAttribute( colors, 3 ) );
				geometry.hasColors = true;
				geometry.alpha = alpha;

			}

			return geometry;

		}
```
</details>

### `parseASCII(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `patternSolid.exec`
- `patternName.exec`
- `groupNames.push`
- `patternFace.exec`
- `patternNormal.exec`
- `parseFloat`
- `patternVertex.exec`
- `vertices.push`
- `normals.push`
- `console.error`
- `geometry.addGroup`
- `geometry.setAttribute`

**Internal Comments:**
```
// every face have to own ONE valid normal
// each face have to own THREE valid vertices
```

<details><summary>Code</summary>

```typescript
function parseASCII( data ) {

			const geometry = new BufferGeometry();
			const patternSolid = /solid([\s\S]*?)endsolid/g;
			const patternFace = /facet([\s\S]*?)endfacet/g;
			const patternName = /solid\s(.+)/;
			let faceCounter = 0;

			const patternFloat = /[\s]+([+-]?(?:\d*)(?:\.\d*)?(?:[eE][+-]?\d+)?)/.source;
			const patternVertex = new RegExp( 'vertex' + patternFloat + patternFloat + patternFloat, 'g' );
			const patternNormal = new RegExp( 'normal' + patternFloat + patternFloat + patternFloat, 'g' );

			const vertices = [];
			const normals = [];
			const groupNames = [];

			const normal = new Vector3();

			let result;

			let groupCount = 0;
			let startVertex = 0;
			let endVertex = 0;

			while ( ( result = patternSolid.exec( data ) ) !== null ) {

				startVertex = endVertex;

				const solid = result[ 0 ];

				const name = ( result = patternName.exec( solid ) ) !== null ? result[ 1 ] : '';
				groupNames.push( name );

				while ( ( result = patternFace.exec( solid ) ) !== null ) {

					let vertexCountPerFace = 0;
					let normalCountPerFace = 0;

					const text = result[ 0 ];

					while ( ( result = patternNormal.exec( text ) ) !== null ) {

						normal.x = parseFloat( result[ 1 ] );
						normal.y = parseFloat( result[ 2 ] );
						normal.z = parseFloat( result[ 3 ] );
						normalCountPerFace ++;

					}

					while ( ( result = patternVertex.exec( text ) ) !== null ) {

						vertices.push( parseFloat( result[ 1 ] ), parseFloat( result[ 2 ] ), parseFloat( result[ 3 ] ) );
						normals.push( normal.x, normal.y, normal.z );
						vertexCountPerFace ++;
						endVertex ++;

					}

					// every face have to own ONE valid normal

					if ( normalCountPerFace !== 1 ) {

						console.error( 'THREE.STLLoader: Something isn\'t right with the normal of face number ' + faceCounter );

					}

					// each face have to own THREE valid vertices

					if ( vertexCountPerFace !== 3 ) {

						console.error( 'THREE.STLLoader: Something isn\'t right with the vertices of face number ' + faceCounter );

					}

					faceCounter ++;

				}

				const start = startVertex;
				const count = endVertex - startVertex;

				geometry.userData.groupNames = groupNames;

				geometry.addGroup( start, count, groupCount );
				groupCount ++;

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
			geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

			return geometry;

		}
```
</details>

### `ensureString(buffer: any): string`

**Parameters:**

- **`buffer`** `any`

**Returns:** `string`

**Calls:**

- `new TextDecoder().decode`

<details><summary>Code</summary>

```typescript
function ensureString( buffer ) {

			if ( typeof buffer !== 'string' ) {

				return new TextDecoder().decode( buffer );

			}

			return buffer;

		}
```
</details>

### `ensureBinary(buffer: any): any`

**Parameters:**

- **`buffer`** `any`

**Returns:** `any`

**Calls:**

- `buffer.charCodeAt`

<details><summary>Code</summary>

```typescript
function ensureBinary( buffer ) {

			if ( typeof buffer === 'string' ) {

				const array_buffer = new Uint8Array( buffer.length );
				for ( let i = 0; i < buffer.length; i ++ ) {

					array_buffer[ i ] = buffer.charCodeAt( i ) & 0xff; // implicitly assumes little-endian

				}

				return array_buffer.buffer || array_buffer;

			} else {

				return buffer;

			}

		}
```
</details>


---

## Classes

### `STLLoader`

<details><summary>Class Code</summary>

```ts
class STLLoader extends Loader {

	/**
	 * Constructs a new STL loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded STL asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading process has been finished.
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
	 * Parses the given STL data and returns the resulting geometry.
	 *
	 * @param {ArrayBuffer} data - The raw STL data as an array buffer.
	 * @return {BufferGeometry} The parsed geometry.
	 */
	parse( data ) {

		function isBinary( data ) {

			const reader = new DataView( data );
			const face_size = ( 32 / 8 * 3 ) + ( ( 32 / 8 * 3 ) * 3 ) + ( 16 / 8 );
			const n_faces = reader.getUint32( 80, true );
			const expect = 80 + ( 32 / 8 ) + ( n_faces * face_size );

			if ( expect === reader.byteLength ) {

				return true;

			}

			// An ASCII STL data must begin with 'solid ' as the first six bytes.
			// However, ASCII STLs lacking the SPACE after the 'd' are known to be
			// plentiful.  So, check the first 5 bytes for 'solid'.

			// Several encodings, such as UTF-8, precede the text with up to 5 bytes:
			// https://en.wikipedia.org/wiki/Byte_order_mark#Byte_order_marks_by_encoding
			// Search for "solid" to start anywhere after those prefixes.

			// US-ASCII ordinal values for 's', 'o', 'l', 'i', 'd'

			const solid = [ 115, 111, 108, 105, 100 ];

			for ( let off = 0; off < 5; off ++ ) {

				// If "solid" text is matched to the current offset, declare it to be an ASCII STL.

				if ( matchDataViewAt( solid, reader, off ) ) return false;

			}

			// Couldn't find "solid" text at the beginning; it is binary STL.

			return true;

		}

		function matchDataViewAt( query, reader, offset ) {

			// Check if each byte in query matches the corresponding byte from the current offset

			for ( let i = 0, il = query.length; i < il; i ++ ) {

				if ( query[ i ] !== reader.getUint8( offset + i ) ) return false;

			}

			return true;

		}

		function parseBinary( data ) {

			const reader = new DataView( data );
			const faces = reader.getUint32( 80, true );

			let r, g, b, hasColors = false, colors;
			let defaultR, defaultG, defaultB, alpha;

			// process STL header
			// check for default color in header ("COLOR=rgba" sequence).

			for ( let index = 0; index < 80 - 10; index ++ ) {

				if ( ( reader.getUint32( index, false ) == 0x434F4C4F /*COLO*/ ) &&
					( reader.getUint8( index + 4 ) == 0x52 /*'R'*/ ) &&
					( reader.getUint8( index + 5 ) == 0x3D /*'='*/ ) ) {

					hasColors = true;
					colors = new Float32Array( faces * 3 * 3 );

					defaultR = reader.getUint8( index + 6 ) / 255;
					defaultG = reader.getUint8( index + 7 ) / 255;
					defaultB = reader.getUint8( index + 8 ) / 255;
					alpha = reader.getUint8( index + 9 ) / 255;

				}

			}

			const dataOffset = 84;
			const faceLength = 12 * 4 + 2;

			const geometry = new BufferGeometry();

			const vertices = new Float32Array( faces * 3 * 3 );
			const normals = new Float32Array( faces * 3 * 3 );

			const color = new Color();

			for ( let face = 0; face < faces; face ++ ) {

				const start = dataOffset + face * faceLength;
				const normalX = reader.getFloat32( start, true );
				const normalY = reader.getFloat32( start + 4, true );
				const normalZ = reader.getFloat32( start + 8, true );

				if ( hasColors ) {

					const packedColor = reader.getUint16( start + 48, true );

					if ( ( packedColor & 0x8000 ) === 0 ) {

						// facet has its own unique color

						r = ( packedColor & 0x1F ) / 31;
						g = ( ( packedColor >> 5 ) & 0x1F ) / 31;
						b = ( ( packedColor >> 10 ) & 0x1F ) / 31;

					} else {

						r = defaultR;
						g = defaultG;
						b = defaultB;

					}

				}

				for ( let i = 1; i <= 3; i ++ ) {

					const vertexstart = start + i * 12;
					const componentIdx = ( face * 3 * 3 ) + ( ( i - 1 ) * 3 );

					vertices[ componentIdx ] = reader.getFloat32( vertexstart, true );
					vertices[ componentIdx + 1 ] = reader.getFloat32( vertexstart + 4, true );
					vertices[ componentIdx + 2 ] = reader.getFloat32( vertexstart + 8, true );

					normals[ componentIdx ] = normalX;
					normals[ componentIdx + 1 ] = normalY;
					normals[ componentIdx + 2 ] = normalZ;

					if ( hasColors ) {

						color.setRGB( r, g, b, SRGBColorSpace );

						colors[ componentIdx ] = color.r;
						colors[ componentIdx + 1 ] = color.g;
						colors[ componentIdx + 2 ] = color.b;

					}

				}

			}

			geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );
			geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

			if ( hasColors ) {

				geometry.setAttribute( 'color', new BufferAttribute( colors, 3 ) );
				geometry.hasColors = true;
				geometry.alpha = alpha;

			}

			return geometry;

		}

		function parseASCII( data ) {

			const geometry = new BufferGeometry();
			const patternSolid = /solid([\s\S]*?)endsolid/g;
			const patternFace = /facet([\s\S]*?)endfacet/g;
			const patternName = /solid\s(.+)/;
			let faceCounter = 0;

			const patternFloat = /[\s]+([+-]?(?:\d*)(?:\.\d*)?(?:[eE][+-]?\d+)?)/.source;
			const patternVertex = new RegExp( 'vertex' + patternFloat + patternFloat + patternFloat, 'g' );
			const patternNormal = new RegExp( 'normal' + patternFloat + patternFloat + patternFloat, 'g' );

			const vertices = [];
			const normals = [];
			const groupNames = [];

			const normal = new Vector3();

			let result;

			let groupCount = 0;
			let startVertex = 0;
			let endVertex = 0;

			while ( ( result = patternSolid.exec( data ) ) !== null ) {

				startVertex = endVertex;

				const solid = result[ 0 ];

				const name = ( result = patternName.exec( solid ) ) !== null ? result[ 1 ] : '';
				groupNames.push( name );

				while ( ( result = patternFace.exec( solid ) ) !== null ) {

					let vertexCountPerFace = 0;
					let normalCountPerFace = 0;

					const text = result[ 0 ];

					while ( ( result = patternNormal.exec( text ) ) !== null ) {

						normal.x = parseFloat( result[ 1 ] );
						normal.y = parseFloat( result[ 2 ] );
						normal.z = parseFloat( result[ 3 ] );
						normalCountPerFace ++;

					}

					while ( ( result = patternVertex.exec( text ) ) !== null ) {

						vertices.push( parseFloat( result[ 1 ] ), parseFloat( result[ 2 ] ), parseFloat( result[ 3 ] ) );
						normals.push( normal.x, normal.y, normal.z );
						vertexCountPerFace ++;
						endVertex ++;

					}

					// every face have to own ONE valid normal

					if ( normalCountPerFace !== 1 ) {

						console.error( 'THREE.STLLoader: Something isn\'t right with the normal of face number ' + faceCounter );

					}

					// each face have to own THREE valid vertices

					if ( vertexCountPerFace !== 3 ) {

						console.error( 'THREE.STLLoader: Something isn\'t right with the vertices of face number ' + faceCounter );

					}

					faceCounter ++;

				}

				const start = startVertex;
				const count = endVertex - startVertex;

				geometry.userData.groupNames = groupNames;

				geometry.addGroup( start, count, groupCount );
				groupCount ++;

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
			geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

			return geometry;

		}

		function ensureString( buffer ) {

			if ( typeof buffer !== 'string' ) {

				return new TextDecoder().decode( buffer );

			}

			return buffer;

		}

		function ensureBinary( buffer ) {

			if ( typeof buffer === 'string' ) {

				const array_buffer = new Uint8Array( buffer.length );
				for ( let i = 0; i < buffer.length; i ++ ) {

					array_buffer[ i ] = buffer.charCodeAt( i ) & 0xff; // implicitly assumes little-endian

				}

				return array_buffer.buffer || array_buffer;

			} else {

				return buffer;

			}

		}

		// start

		const binData = ensureBinary( data );

		return isBinary( binData ) ? parseBinary( binData ) : parseASCII( ensureString( data ) );

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );

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

##### `parse(data: ArrayBuffer): BufferGeometry`

<details><summary>Code</summary>

```ts
parse( data ) {

		function isBinary( data ) {

			const reader = new DataView( data );
			const face_size = ( 32 / 8 * 3 ) + ( ( 32 / 8 * 3 ) * 3 ) + ( 16 / 8 );
			const n_faces = reader.getUint32( 80, true );
			const expect = 80 + ( 32 / 8 ) + ( n_faces * face_size );

			if ( expect === reader.byteLength ) {

				return true;

			}

			// An ASCII STL data must begin with 'solid ' as the first six bytes.
			// However, ASCII STLs lacking the SPACE after the 'd' are known to be
			// plentiful.  So, check the first 5 bytes for 'solid'.

			// Several encodings, such as UTF-8, precede the text with up to 5 bytes:
			// https://en.wikipedia.org/wiki/Byte_order_mark#Byte_order_marks_by_encoding
			// Search for "solid" to start anywhere after those prefixes.

			// US-ASCII ordinal values for 's', 'o', 'l', 'i', 'd'

			const solid = [ 115, 111, 108, 105, 100 ];

			for ( let off = 0; off < 5; off ++ ) {

				// If "solid" text is matched to the current offset, declare it to be an ASCII STL.

				if ( matchDataViewAt( solid, reader, off ) ) return false;

			}

			// Couldn't find "solid" text at the beginning; it is binary STL.

			return true;

		}

		function matchDataViewAt( query, reader, offset ) {

			// Check if each byte in query matches the corresponding byte from the current offset

			for ( let i = 0, il = query.length; i < il; i ++ ) {

				if ( query[ i ] !== reader.getUint8( offset + i ) ) return false;

			}

			return true;

		}

		function parseBinary( data ) {

			const reader = new DataView( data );
			const faces = reader.getUint32( 80, true );

			let r, g, b, hasColors = false, colors;
			let defaultR, defaultG, defaultB, alpha;

			// process STL header
			// check for default color in header ("COLOR=rgba" sequence).

			for ( let index = 0; index < 80 - 10; index ++ ) {

				if ( ( reader.getUint32( index, false ) == 0x434F4C4F /*COLO*/ ) &&
					( reader.getUint8( index + 4 ) == 0x52 /*'R'*/ ) &&
					( reader.getUint8( index + 5 ) == 0x3D /*'='*/ ) ) {

					hasColors = true;
					colors = new Float32Array( faces * 3 * 3 );

					defaultR = reader.getUint8( index + 6 ) / 255;
					defaultG = reader.getUint8( index + 7 ) / 255;
					defaultB = reader.getUint8( index + 8 ) / 255;
					alpha = reader.getUint8( index + 9 ) / 255;

				}

			}

			const dataOffset = 84;
			const faceLength = 12 * 4 + 2;

			const geometry = new BufferGeometry();

			const vertices = new Float32Array( faces * 3 * 3 );
			const normals = new Float32Array( faces * 3 * 3 );

			const color = new Color();

			for ( let face = 0; face < faces; face ++ ) {

				const start = dataOffset + face * faceLength;
				const normalX = reader.getFloat32( start, true );
				const normalY = reader.getFloat32( start + 4, true );
				const normalZ = reader.getFloat32( start + 8, true );

				if ( hasColors ) {

					const packedColor = reader.getUint16( start + 48, true );

					if ( ( packedColor & 0x8000 ) === 0 ) {

						// facet has its own unique color

						r = ( packedColor & 0x1F ) / 31;
						g = ( ( packedColor >> 5 ) & 0x1F ) / 31;
						b = ( ( packedColor >> 10 ) & 0x1F ) / 31;

					} else {

						r = defaultR;
						g = defaultG;
						b = defaultB;

					}

				}

				for ( let i = 1; i <= 3; i ++ ) {

					const vertexstart = start + i * 12;
					const componentIdx = ( face * 3 * 3 ) + ( ( i - 1 ) * 3 );

					vertices[ componentIdx ] = reader.getFloat32( vertexstart, true );
					vertices[ componentIdx + 1 ] = reader.getFloat32( vertexstart + 4, true );
					vertices[ componentIdx + 2 ] = reader.getFloat32( vertexstart + 8, true );

					normals[ componentIdx ] = normalX;
					normals[ componentIdx + 1 ] = normalY;
					normals[ componentIdx + 2 ] = normalZ;

					if ( hasColors ) {

						color.setRGB( r, g, b, SRGBColorSpace );

						colors[ componentIdx ] = color.r;
						colors[ componentIdx + 1 ] = color.g;
						colors[ componentIdx + 2 ] = color.b;

					}

				}

			}

			geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );
			geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

			if ( hasColors ) {

				geometry.setAttribute( 'color', new BufferAttribute( colors, 3 ) );
				geometry.hasColors = true;
				geometry.alpha = alpha;

			}

			return geometry;

		}

		function parseASCII( data ) {

			const geometry = new BufferGeometry();
			const patternSolid = /solid([\s\S]*?)endsolid/g;
			const patternFace = /facet([\s\S]*?)endfacet/g;
			const patternName = /solid\s(.+)/;
			let faceCounter = 0;

			const patternFloat = /[\s]+([+-]?(?:\d*)(?:\.\d*)?(?:[eE][+-]?\d+)?)/.source;
			const patternVertex = new RegExp( 'vertex' + patternFloat + patternFloat + patternFloat, 'g' );
			const patternNormal = new RegExp( 'normal' + patternFloat + patternFloat + patternFloat, 'g' );

			const vertices = [];
			const normals = [];
			const groupNames = [];

			const normal = new Vector3();

			let result;

			let groupCount = 0;
			let startVertex = 0;
			let endVertex = 0;

			while ( ( result = patternSolid.exec( data ) ) !== null ) {

				startVertex = endVertex;

				const solid = result[ 0 ];

				const name = ( result = patternName.exec( solid ) ) !== null ? result[ 1 ] : '';
				groupNames.push( name );

				while ( ( result = patternFace.exec( solid ) ) !== null ) {

					let vertexCountPerFace = 0;
					let normalCountPerFace = 0;

					const text = result[ 0 ];

					while ( ( result = patternNormal.exec( text ) ) !== null ) {

						normal.x = parseFloat( result[ 1 ] );
						normal.y = parseFloat( result[ 2 ] );
						normal.z = parseFloat( result[ 3 ] );
						normalCountPerFace ++;

					}

					while ( ( result = patternVertex.exec( text ) ) !== null ) {

						vertices.push( parseFloat( result[ 1 ] ), parseFloat( result[ 2 ] ), parseFloat( result[ 3 ] ) );
						normals.push( normal.x, normal.y, normal.z );
						vertexCountPerFace ++;
						endVertex ++;

					}

					// every face have to own ONE valid normal

					if ( normalCountPerFace !== 1 ) {

						console.error( 'THREE.STLLoader: Something isn\'t right with the normal of face number ' + faceCounter );

					}

					// each face have to own THREE valid vertices

					if ( vertexCountPerFace !== 3 ) {

						console.error( 'THREE.STLLoader: Something isn\'t right with the vertices of face number ' + faceCounter );

					}

					faceCounter ++;

				}

				const start = startVertex;
				const count = endVertex - startVertex;

				geometry.userData.groupNames = groupNames;

				geometry.addGroup( start, count, groupCount );
				groupCount ++;

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
			geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

			return geometry;

		}

		function ensureString( buffer ) {

			if ( typeof buffer !== 'string' ) {

				return new TextDecoder().decode( buffer );

			}

			return buffer;

		}

		function ensureBinary( buffer ) {

			if ( typeof buffer === 'string' ) {

				const array_buffer = new Uint8Array( buffer.length );
				for ( let i = 0; i < buffer.length; i ++ ) {

					array_buffer[ i ] = buffer.charCodeAt( i ) & 0xff; // implicitly assumes little-endian

				}

				return array_buffer.buffer || array_buffer;

			} else {

				return buffer;

			}

		}

		// start

		const binData = ensureBinary( data );

		return isBinary( binData ) ? parseBinary( binData ) : parseASCII( ensureString( data ) );

	}
```
</details>


---