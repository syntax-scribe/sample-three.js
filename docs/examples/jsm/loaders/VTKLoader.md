[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `VTKLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 131 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/VTKLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Loader` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `positions` | `any[]` | let/var | `[]` | ✗ |
| `colors` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `patWord` | `RegExp` | let/var | `/^[^\d.\s-]+/` | ✗ |
| `pat3Floats` | `RegExp` | let/var | `/(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)/g` | ✗ |
| `patConnectivity` | `RegExp` | let/var | `/^(\d+)\s+([\s\d]*)/` | ✗ |
| `patPOINTS` | `RegExp` | let/var | `/^POINTS /` | ✗ |
| `patPOLYGONS` | `RegExp` | let/var | `/^POLYGONS /` | ✗ |
| `patTRIANGLE_STRIPS` | `RegExp` | let/var | `/^TRIANGLE_STRIPS /` | ✗ |
| `patPOINT_DATA` | `RegExp` | let/var | `/^POINT_DATA[ ]+(\d+)/` | ✗ |
| `patCELL_DATA` | `RegExp` | let/var | `/^CELL_DATA[ ]+(\d+)/` | ✗ |
| `patCOLOR_SCALARS` | `RegExp` | let/var | `/^COLOR_SCALARS[ ]+(\w+)[ ]+3/` | ✗ |
| `patNORMALS` | `RegExp` | let/var | `/^NORMALS[ ]+(\w+)[ ]+(\w+)/` | ✗ |
| `inPointsSection` | `boolean` | let/var | `false` | ✗ |
| `inPolygonsSection` | `boolean` | let/var | `false` | ✗ |
| `inTriangleStripSection` | `boolean` | let/var | `false` | ✗ |
| `inPointDataSection` | `boolean` | let/var | `false` | ✗ |
| `inCellDataSection` | `boolean` | let/var | `false` | ✗ |
| `inColorSection` | `boolean` | let/var | `false` | ✗ |
| `inNormalsSection` | `boolean` | let/var | `false` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `dataset` | `any` | let/var | `line.split( ' ' )[ 1 ]` | ✗ |
| `k` | `number` | let/var | `1` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `numTriangles` | `number` | let/var | `geometry.attributes.position.count / 3` | ✗ |
| `newColors` | `any[]` | let/var | `[]` | ✗ |
| `r` | `any` | let/var | `colors[ 3 * i + 0 ]` | ✗ |
| `g` | `any` | let/var | `colors[ 3 * i + 1 ]` | ✗ |
| `b` | `any` | let/var | `colors[ 3 * i + 2 ]` | ✗ |
| `buffer` | `Uint8Array<any>` | let/var | `new Uint8Array( data )` | ✗ |
| `dataView` | `DataView<any>` | let/var | `new DataView( data )` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `index` | `any` | let/var | `start` | ✗ |
| `c` | `any` | let/var | `buffer[ index ]` | ✗ |
| `s` | `any[]` | let/var | `[]` | ✗ |
| `state` | `any` | let/var | `*not shown*` | ✗ |
| `line` | `any` | let/var | `*not shown*` | ✗ |
| `dataset` | `string` | let/var | `line.split( ' ' )[ 1 ]` | ✗ |
| `count` | `number` | let/var | `numberOfPoints * 4 * 3` | ✗ |
| `pointIndex` | `any` | let/var | `state.next` | ✗ |
| `count` | `number` | let/var | `size * 4` | ✗ |
| `indicesIndex` | `number` | let/var | `0` | ✗ |
| `pointIndex` | `any` | let/var | `state.next` | ✗ |
| `strip` | `any[]` | let/var | `[]` | ✗ |
| `count` | `number` | let/var | `size * 4` | ✗ |
| `indicesIndex` | `number` | let/var | `0` | ✗ |
| `pointIndex` | `any` | let/var | `state.next` | ✗ |
| `strip` | `any[]` | let/var | `[]` | ✗ |
| `count` | `number` | let/var | `numberOfPoints * 4 * 3` | ✗ |
| `pointIndex` | `any` | let/var | `state.next` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `firstLength` | `any` | let/var | `first.length` | ✗ |
| `result` | `Float32Array<any>` | let/var | `new Float32Array( firstLength + second.length )` | ✗ |
| `firstLength` | `any` | let/var | `first.length` | ✗ |
| `result` | `Int32Array<any>` | let/var | `new Int32Array( firstLength + second.length )` | ✗ |
| `obj` | `{ attributes: {}; }` | let/var | `{}` | ✗ |
| `nodeName` | `any` | let/var | `item.nodeName` | ✗ |
| `old` | `any` | let/var | `obj[ nodeName ]` | ✗ |
| `Arr` | `Uint8ArrayConstructor \| ArrayConstru...` | let/var | `typeof Uint8Array !== 'undefined' ? Uint8Array : Array` | ✗ |
| `revLookup` | `any[]` | let/var | `[]` | ✗ |
| `code` | `"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghij...` | let/var | `'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'` | ✗ |
| `len` | `any` | let/var | `b64.length` | ✗ |
| `placeHolders` | `1 \| 2 \| 0` | let/var | `b64[ len - 2 ] === '=' ? 2 : b64[ len - 1 ] === '=' ? 1 : 0` | ✗ |
| `arr` | `any[] \| Uint8Array<ArrayBuffer>` | let/var | `new Arr( len * 3 / 4 - placeHolders )` | ✗ |
| `l` | `any` | let/var | `placeHolders > 0 ? len - 4 : len` | ✗ |
| `L` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `tmp` | `number` | let/var | `( revLookup[ b64.charCodeAt( i ) ] << 18 ) \| ( revLookup[ b64.charCodeAt( i ...` | ✗ |
| `tmp` | `number` | let/var | `( revLookup[ b64.charCodeAt( i ) ] << 2 ) \| ( revLookup[ b64.charCodeAt( i +...` | ✗ |
| `tmp` | `number` | let/var | `( revLookup[ b64.charCodeAt( i ) ] << 10 ) \| ( revLookup[ b64.charCodeAt( i ...` | ✗ |
| `numBytes` | `number` | let/var | `0` | ✗ |
| `txt` | `any` | let/var | `*not shown*` | ✗ |
| `content` | `any` | let/var | `*not shown*` | ✗ |
| `textNode` | `any` | let/var | `ele[ '#text' ]` | ✗ |
| `rawData` | `any` | let/var | `Array.isArray( textNode ) ? textNode[ 0 ] : textNode` | ✗ |
| `dataPointSize` | `8` | let/var | `8` | ✗ |
| `blocks` | `any` | let/var | `byteData[ 0 ]` | ✗ |
| `headerSize` | `number` | let/var | `( blocks + 3 ) * numBytes` | ✗ |
| `padding` | `number` | let/var | `( ( headerSize % 3 ) > 0 ) ? 3 - ( headerSize % 3 ) : 0` | ✗ |
| `dataOffsets` | `any[]` | let/var | `[]` | ✗ |
| `currentOffset` | `number` | let/var | `headerSize` | ✗ |
| `cSizeStart` | `number` | let/var | `3 * numBytes` | ✗ |
| `currentBlockSize` | `any` | let/var | `byteData[ i * numBytes + cSizeStart ]` | ✗ |
| `doc` | `HTMLElement` | let/var | `dom.documentElement` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `piece` | `any` | let/var | `json.PolyData.Piece` | ✗ |
| `sections` | `string[]` | let/var | `[ 'PointData', 'CellData', 'Points', 'Verts', 'Lines', 'Strips', 'Polys' ]` | ✗ |
| `sectionIndex` | `number` | let/var | `0` | ✗ |
| `sect` | `any` | let/var | `piece[ s ]` | ✗ |
| `arr` | `any` | let/var | `Array.isArray( sect.DataArray ) ? sect.DataArray : [ sect.DataArray ]` | ✗ |
| `section` | `any` | let/var | `piece[ sect ]` | ✗ |
| `piece` | `any` | let/var | `json.PolyData.Piece` | ✗ |
| `sections` | `string[]` | let/var | `[ 'PointData', 'Points', 'Strips', 'Polys' ]` | ✗ |
| `sectionIndex` | `number` | let/var | `0` | ✗ |
| `numberOfSections` | `number` | let/var | `sections.length` | ✗ |
| `section` | `any` | let/var | `piece[ sections[ sectionIndex ] ]` | ✗ |
| `arr` | `any` | let/var | `*not shown*` | ✗ |
| `dataArrayIndex` | `number` | let/var | `0` | ✗ |
| `numberOfDataArrays` | `any` | let/var | `arr.length` | ✗ |
| `normalsName` | `any` | let/var | `section.attributes.Normals` | ✗ |
| `components` | `any` | let/var | `arr[ i ].attributes.NumberOfComponents` | ✗ |
| `components` | `any` | let/var | `section.DataArray.attributes.NumberOfComponents` | ✗ |
| `connectivity` | `Int32Array<any>` | let/var | `new Int32Array( section.DataArray[ 0 ].text.length )` | ✗ |
| `offset` | `Int32Array<any>` | let/var | `new Int32Array( section.DataArray[ 1 ].text.length )` | ✗ |
| `size` | `number` | let/var | `numberOfStrips + connectivity.length` | ✗ |
| `indicesIndex` | `number` | let/var | `0` | ✗ |
| `strip` | `any[]` | let/var | `[]` | ✗ |
| `connectivity` | `Int32Array<any>` | let/var | `new Int32Array( section.DataArray[ 0 ].text.length )` | ✗ |
| `offset` | `Int32Array<any>` | let/var | `new Int32Array( section.DataArray[ 1 ].text.length )` | ✗ |
| `size` | `number` | let/var | `numberOfPolys + connectivity.length` | ✗ |
| `indicesIndex` | `number` | let/var | `0` | ✗ |
| `connectivityIndex` | `number` | let/var | `0` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `len0` | `number` | let/var | `0` | ✗ |
| `len` | `number` | let/var | `numberOfPolys` | ✗ |
| `poly` | `any[]` | let/var | `[]` | ✗ |
| `s` | `number` | let/var | `0` | ✗ |
| `len1` | `number` | let/var | `offset[ i ]` | ✗ |
| `j` | `number` | let/var | `1` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `textDecoder` | `TextDecoder` | let/var | `new TextDecoder()` | ✗ |


---

## Functions

### `VTKLoader.load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded VRML asset
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

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
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

### `VTKLoader.parse(data: ArrayBuffer): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Parses the given VTK data and returns the resulting geometry.
	 *
	 * @param {ArrayBuffer} data - The raw VTK data as an array buffer
	 * @return {BufferGeometry} The parsed geometry.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`

**Returns:** `BufferGeometry`

**Calls:**

- `data.split`
- `lines[ i ].trim`
- `line.indexOf`
- `line.split`
- `pat3Floats.exec`
- `patWord.exec`
- `parseFloat`
- `positions.push`
- `patConnectivity.exec`
- `parseInt`
- `result[ 2 ].split`
- `indices.push`
- `color.setRGB`
- `colors.push`
- `normals.push`
- `patPOLYGONS.exec`
- `patPOINTS.exec`
- `patTRIANGLE_STRIPS.exec`
- `patPOINT_DATA.exec`
- `patCELL_DATA.exec`
- `patCOLOR_SCALARS.exec`
- `patNORMALS.exec`
- `geometry.setIndex`
- `geometry.setAttribute`
- `geometry.toNonIndexed`
- `newColors.push`
- `s.push`
- `String.fromCharCode`
- `s.join`
- `findString`
- `dataView.getFloat32`
- `dataView.getInt32`
- `strip.push`
- `result.set`
- `xml.attributes.item`
- `attribute.nodeValue.trim`
- `xml.nodeValue.trim`
- `xml.hasChildNodes`
- `xml.childNodes.item`
- `xmlToJson`
- `Array.isArray`
- `obj[ nodeName ].push`
- `code.charCodeAt`
- `'-'.charCodeAt`
- `'_'.charCodeAt`
- `b64.charCodeAt`
- `Base64toByteArray`
- `dataOffsets.push`
- `fflate.unzlibSync`
- `byteData.slice`
- `Float32Concat`
- `Int32Concat`
- `txt.filter`
- `content.slice`
- `ele[ '#text' ].split( /\s+/ ).filter`
- `new DOMParser().parseFromString`
- `json.AppendedData[ '#text' ].slice`
- `sections.map( s => {

					const sect = piece[ s ];

					if ( sect && sect.DataArray ) {

						const arr = Array.isArray( sect.DataArray ) ? sect.DataArray : [ sect.DataArray ];

						return arr.map( a => a.attributes.offset );

					}

					return [];

				} ).flat`
- `appendedData.slice`
- `json.attributes.hasOwnProperty`
- `parseDataArray`
- `normals.set`
- `points.set`
- `connectivity.set`
- `offset.set`
- `poly.push`
- `textDecoder.decode( new Uint8Array( data, 0, 250 ) ).split`
- `meta[ 0 ].indexOf`
- `parseXML`
- `textDecoder.decode`
- `meta[ 2 ].includes`
- `parseASCII`
- `parseBinary`

**Internal Comments:**
```
// connectivity of the triangles (x2)
// triangles vertices (x2)
// red, green, blue colors in the range 0 to 1 (x2)
// normal vector, one per vertex (x2)
// pattern for detecting the end of a number sequence (x2)
// pattern for reading vertices, 3 floats or integers (x2)
// pattern for connectivity, an integer followed by any number of ints (x2)
// the first integer is the number of polygon nodes (x2)
// indicates start of vertex data section (x2)
// indicates start of polygon connectivity section (x2)
// indicates start of triangle strips section (x2)
// POINT_DATA number_of_values (x2)
// CELL_DATA number_of_polys (x2)
// Start of color section (x2)
// NORMALS Normals float (x2)
// get the vertices
// numVertices i0 i1 i2 ... (x4)
// split the polygon in numVertices - 2 triangles (x2)
// Get the colors
// Get the normal vectors
// stagger
// cell (x3)
// Points and normals, by default, are empty (x2)
// Get a string (x3)
// Add the points (x2)
// Each point is 3 4-byte floats (x2)
// increment our next pointer (x12)
// 4 byte integers (x4)
// For each strip, read the first value, then record that many more points (x4)
// retrieves the n-2 triangles from the triangle strip
// divide the polygon in n-2 triangle
// Grab the next line (x3)
// Now grab the binary data (x2)
// Increment past our data (x4)
// Increment index (x3)
// Changes XML to JSON, based on https://davidwalsh.name/convert-xml-json
// Create the return object (x2)
// do attributes
// do children
// Taken from Base64-js
// Check the format
// VTP data with the header has the following structure: (x2)
// [#blocks][#u-size][#p-size][#c-size-1][#c-size-2]...[#c-size-#blocks][DATA] (x2)
// (x4)
// Each token is an integer value whose type is specified by "header_type" at the top of the file (UInt32 if no type specified). The token meanings are: (x2)
// [#blocks] = Number of blocks (x2)
// [#u-size] = Block size before compression (x2)
// [#p-size] = Size of last partial block (zero if it not needed) (x2)
// [#c-size-i] = Size in bytes of block i after compression (x2)
// The [DATA] portion stores contiguously every block appended together. The offset from the beginning of the data section to the beginning of a block is (x2)
// computed by summing the compressed block sizes from preceding blocks according to the header. (x2)
// Each data point consists of 8 bits regardless of the header type (x2)
// Get the blocks sizes after the compression. (x2)
// There are three blocks before c-size-i, so we skip 3*numBytes (x2)
//  VTP data for the uncompressed case has the following structure: (x3)
// [#bytes][DATA] (x3)
// where "[#bytes]" is an integer value specifying the number of bytes in the block of data following it. (x3)
// Get the content and optimize it
// Main part (x2)
// Get Dom (x2)
// Get the doc (x2)
// Convert to json (x2)
// Can be optimized (x2)
// Loop through the sections (x2)
// If it has a DataArray in it
// Depending on the number of DataArrays (x2)
// Parse the DataArray
// if iti is point data
// if it is points
// if it is strips
// if it is polys
// get the 5 first lines of the files to check if there is the key word binary (x2)
```

<details><summary>Code</summary>

```typescript
parse( data ) {

		function parseASCII( data ) {

			// connectivity of the triangles
			const indices = [];

			// triangles vertices
			const positions = [];

			// red, green, blue colors in the range 0 to 1
			const colors = [];

			// normal vector, one per vertex
			const normals = [];

			let result;

			// pattern for detecting the end of a number sequence
			const patWord = /^[^\d.\s-]+/;

			// pattern for reading vertices, 3 floats or integers
			const pat3Floats = /(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)/g;

			// pattern for connectivity, an integer followed by any number of ints
			// the first integer is the number of polygon nodes
			const patConnectivity = /^(\d+)\s+([\s\d]*)/;

			// indicates start of vertex data section
			const patPOINTS = /^POINTS /;

			// indicates start of polygon connectivity section
			const patPOLYGONS = /^POLYGONS /;

			// indicates start of triangle strips section
			const patTRIANGLE_STRIPS = /^TRIANGLE_STRIPS /;

			// POINT_DATA number_of_values
			const patPOINT_DATA = /^POINT_DATA[ ]+(\d+)/;

			// CELL_DATA number_of_polys
			const patCELL_DATA = /^CELL_DATA[ ]+(\d+)/;

			// Start of color section
			const patCOLOR_SCALARS = /^COLOR_SCALARS[ ]+(\w+)[ ]+3/;

			// NORMALS Normals float
			const patNORMALS = /^NORMALS[ ]+(\w+)[ ]+(\w+)/;

			let inPointsSection = false;
			let inPolygonsSection = false;
			let inTriangleStripSection = false;
			let inPointDataSection = false;
			let inCellDataSection = false;
			let inColorSection = false;
			let inNormalsSection = false;

			const color = new Color();

			const lines = data.split( '\n' );

			for ( const i in lines ) {

				const line = lines[ i ].trim();

				if ( line.indexOf( 'DATASET' ) === 0 ) {

					const dataset = line.split( ' ' )[ 1 ];

					if ( dataset !== 'POLYDATA' ) throw new Error( 'Unsupported DATASET type: ' + dataset );

				} else if ( inPointsSection ) {

					// get the vertices
					while ( ( result = pat3Floats.exec( line ) ) !== null ) {

						if ( patWord.exec( line ) !== null ) break;

						const x = parseFloat( result[ 1 ] );
						const y = parseFloat( result[ 2 ] );
						const z = parseFloat( result[ 3 ] );
						positions.push( x, y, z );

					}

				} else if ( inPolygonsSection ) {

					if ( ( result = patConnectivity.exec( line ) ) !== null ) {

						// numVertices i0 i1 i2 ...
						const numVertices = parseInt( result[ 1 ] );
						const inds = result[ 2 ].split( /\s+/ );

						if ( numVertices >= 3 ) {

							const i0 = parseInt( inds[ 0 ] );
							let k = 1;
							// split the polygon in numVertices - 2 triangles
							for ( let j = 0; j < numVertices - 2; ++ j ) {

								const i1 = parseInt( inds[ k ] );
								const i2 = parseInt( inds[ k + 1 ] );
								indices.push( i0, i1, i2 );
								k ++;

							}

						}

					}

				} else if ( inTriangleStripSection ) {

					if ( ( result = patConnectivity.exec( line ) ) !== null ) {

						// numVertices i0 i1 i2 ...
						const numVertices = parseInt( result[ 1 ] );
						const inds = result[ 2 ].split( /\s+/ );

						if ( numVertices >= 3 ) {

							// split the polygon in numVertices - 2 triangles
							for ( let j = 0; j < numVertices - 2; j ++ ) {

								if ( j % 2 === 1 ) {

									const i0 = parseInt( inds[ j ] );
									const i1 = parseInt( inds[ j + 2 ] );
									const i2 = parseInt( inds[ j + 1 ] );
									indices.push( i0, i1, i2 );

								} else {

									const i0 = parseInt( inds[ j ] );
									const i1 = parseInt( inds[ j + 1 ] );
									const i2 = parseInt( inds[ j + 2 ] );
									indices.push( i0, i1, i2 );

								}

							}

						}

					}

				} else if ( inPointDataSection || inCellDataSection ) {

					if ( inColorSection ) {

						// Get the colors

						while ( ( result = pat3Floats.exec( line ) ) !== null ) {

							if ( patWord.exec( line ) !== null ) break;

							const r = parseFloat( result[ 1 ] );
							const g = parseFloat( result[ 2 ] );
							const b = parseFloat( result[ 3 ] );

							color.setRGB( r, g, b, SRGBColorSpace );

							colors.push( color.r, color.g, color.b );

						}

					} else if ( inNormalsSection ) {

						// Get the normal vectors

						while ( ( result = pat3Floats.exec( line ) ) !== null ) {

							if ( patWord.exec( line ) !== null ) break;

							const nx = parseFloat( result[ 1 ] );
							const ny = parseFloat( result[ 2 ] );
							const nz = parseFloat( result[ 3 ] );
							normals.push( nx, ny, nz );

						}

					}

				}

				if ( patPOLYGONS.exec( line ) !== null ) {

					inPolygonsSection = true;
					inPointsSection = false;
					inTriangleStripSection = false;

				} else if ( patPOINTS.exec( line ) !== null ) {

					inPolygonsSection = false;
					inPointsSection = true;
					inTriangleStripSection = false;

				} else if ( patTRIANGLE_STRIPS.exec( line ) !== null ) {

					inPolygonsSection = false;
					inPointsSection = false;
					inTriangleStripSection = true;

				} else if ( patPOINT_DATA.exec( line ) !== null ) {

					inPointDataSection = true;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patCELL_DATA.exec( line ) !== null ) {

					inCellDataSection = true;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patCOLOR_SCALARS.exec( line ) !== null ) {

					inColorSection = true;
					inNormalsSection = false;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patNORMALS.exec( line ) !== null ) {

					inNormalsSection = true;
					inColorSection = false;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				}

			}

			let geometry = new BufferGeometry();
			geometry.setIndex( indices );
			geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );

			if ( normals.length === positions.length ) {

				geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

			}

			if ( colors.length !== indices.length ) {

				// stagger

				if ( colors.length === positions.length ) {

					geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

				}

			} else {

				// cell

				geometry = geometry.toNonIndexed();
				const numTriangles = geometry.attributes.position.count / 3;

				if ( colors.length === ( numTriangles * 3 ) ) {

					const newColors = [];

					for ( let i = 0; i < numTriangles; i ++ ) {

						const r = colors[ 3 * i + 0 ];
						const g = colors[ 3 * i + 1 ];
						const b = colors[ 3 * i + 2 ];

						color.setRGB( r, g, b, SRGBColorSpace );

						newColors.push( color.r, color.g, color.b );
						newColors.push( color.r, color.g, color.b );
						newColors.push( color.r, color.g, color.b );

					}

					geometry.setAttribute( 'color', new Float32BufferAttribute( newColors, 3 ) );

				}

			}

			return geometry;

		}

		function parseBinary( data ) {

			const buffer = new Uint8Array( data );
			const dataView = new DataView( data );

			// Points and normals, by default, are empty
			let points = [];
			let normals = [];
			let indices = [];

			let index = 0;

			function findString( buffer, start ) {

				let index = start;
				let c = buffer[ index ];
				const s = [];
				while ( c !== 10 ) {

					s.push( String.fromCharCode( c ) );
					index ++;
					c = buffer[ index ];

				}

				return { start: start,
					end: index,
					next: index + 1,
					parsedString: s.join( '' ) };

			}

			let state, line;

			while ( true ) {

				// Get a string
				state = findString( buffer, index );
				line = state.parsedString;

				if ( line.indexOf( 'DATASET' ) === 0 ) {

					const dataset = line.split( ' ' )[ 1 ];

					if ( dataset !== 'POLYDATA' ) throw new Error( 'Unsupported DATASET type: ' + dataset );

				} else if ( line.indexOf( 'POINTS' ) === 0 ) {

					// Add the points
					const numberOfPoints = parseInt( line.split( ' ' )[ 1 ], 10 );

					// Each point is 3 4-byte floats
					const count = numberOfPoints * 4 * 3;

					points = new Float32Array( numberOfPoints * 3 );

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfPoints; i ++ ) {

						points[ 3 * i ] = dataView.getFloat32( pointIndex, false );
						points[ 3 * i + 1 ] = dataView.getFloat32( pointIndex + 4, false );
						points[ 3 * i + 2 ] = dataView.getFloat32( pointIndex + 8, false );
						pointIndex = pointIndex + 12;

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'TRIANGLE_STRIPS' ) === 0 ) {

					const numberOfStrips = parseInt( line.split( ' ' )[ 1 ], 10 );
					const size = parseInt( line.split( ' ' )[ 2 ], 10 );
					// 4 byte integers
					const count = size * 4;

					indices = new Uint32Array( 3 * size - 9 * numberOfStrips );
					let indicesIndex = 0;

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfStrips; i ++ ) {

						// For each strip, read the first value, then record that many more points
						const indexCount = dataView.getInt32( pointIndex, false );
						const strip = [];
						pointIndex += 4;
						for ( let s = 0; s < indexCount; s ++ ) {

							strip.push( dataView.getInt32( pointIndex, false ) );
							pointIndex += 4;

						}

						// retrieves the n-2 triangles from the triangle strip
						for ( let j = 0; j < indexCount - 2; j ++ ) {

							if ( j % 2 ) {

								indices[ indicesIndex ++ ] = strip[ j ];
								indices[ indicesIndex ++ ] = strip[ j + 2 ];
								indices[ indicesIndex ++ ] = strip[ j + 1 ];

							} else {

								indices[ indicesIndex ++ ] = strip[ j ];
								indices[ indicesIndex ++ ] = strip[ j + 1 ];
								indices[ indicesIndex ++ ] = strip[ j + 2 ];

							}

						}

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'POLYGONS' ) === 0 ) {

					const numberOfStrips = parseInt( line.split( ' ' )[ 1 ], 10 );
					const size = parseInt( line.split( ' ' )[ 2 ], 10 );
					// 4 byte integers
					const count = size * 4;

					indices = new Uint32Array( 3 * size - 9 * numberOfStrips );
					let indicesIndex = 0;

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfStrips; i ++ ) {

						// For each strip, read the first value, then record that many more points
						const indexCount = dataView.getInt32( pointIndex, false );
						const strip = [];
						pointIndex += 4;
						for ( let s = 0; s < indexCount; s ++ ) {

							strip.push( dataView.getInt32( pointIndex, false ) );
							pointIndex += 4;

						}

						// divide the polygon in n-2 triangle
						for ( let j = 1; j < indexCount - 1; j ++ ) {

							indices[ indicesIndex ++ ] = strip[ 0 ];
							indices[ indicesIndex ++ ] = strip[ j ];
							indices[ indicesIndex ++ ] = strip[ j + 1 ];

						}

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'POINT_DATA' ) === 0 ) {

					const numberOfPoints = parseInt( line.split( ' ' )[ 1 ], 10 );

					// Grab the next line
					state = findString( buffer, state.next );

					// Now grab the binary data
					const count = numberOfPoints * 4 * 3;

					normals = new Float32Array( numberOfPoints * 3 );
					let pointIndex = state.next;
					for ( let i = 0; i < numberOfPoints; i ++ ) {

						normals[ 3 * i ] = dataView.getFloat32( pointIndex, false );
						normals[ 3 * i + 1 ] = dataView.getFloat32( pointIndex + 4, false );
						normals[ 3 * i + 2 ] = dataView.getFloat32( pointIndex + 8, false );
						pointIndex += 12;

					}

					// Increment past our data
					state.next = state.next + count;

				}

				// Increment index
				index = state.next;

				if ( index >= buffer.byteLength ) {

					break;

				}

			}

			const geometry = new BufferGeometry();
			geometry.setIndex( new BufferAttribute( indices, 1 ) );
			geometry.setAttribute( 'position', new BufferAttribute( points, 3 ) );

			if ( normals.length === points.length ) {

				geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

			}

			return geometry;

		}

		function Float32Concat( first, second ) {

			const firstLength = first.length, result = new Float32Array( firstLength + second.length );

			result.set( first );
			result.set( second, firstLength );

			return result;

		}

		function Int32Concat( first, second ) {

			const firstLength = first.length, result = new Int32Array( firstLength + second.length );

			result.set( first );
			result.set( second, firstLength );

			return result;

		}

		function parseXML( stringFile ) {

			// Changes XML to JSON, based on https://davidwalsh.name/convert-xml-json

			function xmlToJson( xml ) {

				// Create the return object
				let obj = {};

				if ( xml.nodeType === 1 ) { // element

					// do attributes

					if ( xml.attributes ) {

						if ( xml.attributes.length > 0 ) {

							obj[ 'attributes' ] = {};

							for ( let j = 0; j < xml.attributes.length; j ++ ) {

								const attribute = xml.attributes.item( j );
								obj[ 'attributes' ][ attribute.nodeName ] = attribute.nodeValue.trim();

							}

						}

					}

				} else if ( xml.nodeType === 3 ) { // text

					obj = xml.nodeValue.trim();

				}

				// do children
				if ( xml.hasChildNodes() ) {

					for ( let i = 0; i < xml.childNodes.length; i ++ ) {

						const item = xml.childNodes.item( i );
						const nodeName = item.nodeName;

						if ( typeof obj[ nodeName ] === 'undefined' ) {

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ] = tmp;

							}

						} else {

							if ( typeof obj[ nodeName ].push === 'undefined' ) {

								const old = obj[ nodeName ];
								obj[ nodeName ] = [ old ];

							}

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ].push( tmp );

							}

						}

					}

				}

				return obj;

			}

			// Taken from Base64-js
			function Base64toByteArray( b64 ) {

				const Arr = typeof Uint8Array !== 'undefined' ? Uint8Array : Array;
				const revLookup = [];
				const code = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/';

				for ( let i = 0, l = code.length; i < l; ++ i ) {

					revLookup[ code.charCodeAt( i ) ] = i;

				}

				revLookup[ '-'.charCodeAt( 0 ) ] = 62;
				revLookup[ '_'.charCodeAt( 0 ) ] = 63;

				const len = b64.length;

				if ( len % 4 > 0 ) {

					throw new Error( 'Invalid string. Length must be a multiple of 4' );

				}

				const placeHolders = b64[ len - 2 ] === '=' ? 2 : b64[ len - 1 ] === '=' ? 1 : 0;
				const arr = new Arr( len * 3 / 4 - placeHolders );
				const l = placeHolders > 0 ? len - 4 : len;

				let L = 0;
				let i, j;

				for ( i = 0, j = 0; i < l; i += 4, j += 3 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 18 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 12 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] << 6 ) | revLookup[ b64.charCodeAt( i + 3 ) ];
					arr[ L ++ ] = ( tmp & 0xFF0000 ) >> 16;
					arr[ L ++ ] = ( tmp & 0xFF00 ) >> 8;
					arr[ L ++ ] = tmp & 0xFF;

				}

				if ( placeHolders === 2 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 2 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] >> 4 );
					arr[ L ++ ] = tmp & 0xFF;

				} else if ( placeHolders === 1 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 10 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 4 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] >> 2 );
					arr[ L ++ ] = ( tmp >> 8 ) & 0xFF;
					arr[ L ++ ] = tmp & 0xFF;

				}

				return arr;

			}

			function parseDataArray( ele, compressed ) {

				let numBytes = 0;

				if ( json.attributes.header_type === 'UInt64' ) {

					numBytes = 8;

				}	else if ( json.attributes.header_type === 'UInt32' ) {

					numBytes = 4;

				}

				let txt, content;

				// Check the format
				if ( ele.attributes.format === 'binary' && compressed ) {

					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( );

					} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( );

					}

					// VTP data with the header has the following structure:
					// [#blocks][#u-size][#p-size][#c-size-1][#c-size-2]...[#c-size-#blocks][DATA]
					//
					// Each token is an integer value whose type is specified by "header_type" at the top of the file (UInt32 if no type specified). The token meanings are:
					// [#blocks] = Number of blocks
					// [#u-size] = Block size before compression
					// [#p-size] = Size of last partial block (zero if it not needed)
					// [#c-size-i] = Size in bytes of block i after compression
					//
					// The [DATA] portion stores contiguously every block appended together. The offset from the beginning of the data section to the beginning of a block is
					// computed by summing the compressed block sizes from preceding blocks according to the header.

					const textNode = ele[ '#text' ];
					const rawData = Array.isArray( textNode ) ? textNode[ 0 ] : textNode;

					const byteData = Base64toByteArray( rawData );

					// Each data point consists of 8 bits regardless of the header type
					const dataPointSize = 8;

					let blocks = byteData[ 0 ];
					for ( let i = 1; i < numBytes - 1; i ++ ) {

						blocks = blocks | ( byteData[ i ] << ( i * dataPointSize ) );

					}

					let headerSize = ( blocks + 3 ) * numBytes;
					const padding = ( ( headerSize % 3 ) > 0 ) ? 3 - ( headerSize % 3 ) : 0;
					headerSize = headerSize + padding;

					const dataOffsets = [];
					let currentOffset = headerSize;
					dataOffsets.push( currentOffset );

					// Get the blocks sizes after the compression.
					// There are three blocks before c-size-i, so we skip 3*numBytes
					const cSizeStart = 3 * numBytes;

					for ( let i = 0; i < blocks; i ++ ) {

						let currentBlockSize = byteData[ i * numBytes + cSizeStart ];

						for ( let j = 1; j < numBytes - 1; j ++ ) {

							currentBlockSize = currentBlockSize | ( byteData[ i * numBytes + cSizeStart + j ] << ( j * dataPointSize ) );

						}

						currentOffset = currentOffset + currentBlockSize;
						dataOffsets.push( currentOffset );

					}

					for ( let i = 0; i < dataOffsets.length - 1; i ++ ) {

						const data = fflate.unzlibSync( byteData.slice( dataOffsets[ i ], dataOffsets[ i + 1 ] ) );
						content = data.buffer;

						if ( ele.attributes.type === 'Float32' ) {

							content = new Float32Array( content );
							txt = Float32Concat( txt, content );

						} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

							content = new Int32Array( content );
							txt = Int32Concat( txt, content );

						}

					}

					delete ele[ '#text' ];

					if ( ele.attributes.type === 'Int64' ) {

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} else {

					if ( ele.attributes.format === 'binary' && ! compressed ) {

						content = Base64toByteArray( ele[ '#text' ] );

						//  VTP data for the uncompressed case has the following structure:
						// [#bytes][DATA]
						// where "[#bytes]" is an integer value specifying the number of bytes in the block of data following it.
						content = content.slice( numBytes ).buffer;

					} else {

						if ( ele[ '#text' ] ) {

							content = ele[ '#text' ].split( /\s+/ ).filter( function ( el ) {

								if ( el !== '' ) return el;

							} );

						} else {

							content = new Int32Array( 0 ).buffer;

						}

					}

					delete ele[ '#text' ];

					// Get the content and optimize it
					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( content );

					} else if ( ele.attributes.type === 'Int32' ) {

						txt = new Int32Array( content );

					} else if ( ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( content );

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} // endif ( ele.attributes.format === 'binary' && compressed )

				return txt;

			}

			// Main part
			// Get Dom
			const dom = new DOMParser().parseFromString( stringFile, 'application/xml' );

			// Get the doc
			const doc = dom.documentElement;
			// Convert to json
			const json = xmlToJson( doc );
			let points = [];
			let normals = [];
			let indices = [];

			if ( json.AppendedData ) {

				const appendedData = json.AppendedData[ '#text' ].slice( 1 );
				const piece = json.PolyData.Piece;

				const sections = [ 'PointData', 'CellData', 'Points', 'Verts', 'Lines', 'Strips', 'Polys' ];
				let sectionIndex = 0;

				const offsets = sections.map( s => {

					const sect = piece[ s ];

					if ( sect && sect.DataArray ) {

						const arr = Array.isArray( sect.DataArray ) ? sect.DataArray : [ sect.DataArray ];

						return arr.map( a => a.attributes.offset );

					}

					return [];

				} ).flat();

				for ( const sect of sections ) {

					const section = piece[ sect ];

					if ( section && section.DataArray ) {

						if ( Array.isArray( section.DataArray ) ) {

							for ( const sectionEle of section.DataArray ) {

								sectionEle[ '#text' ] = appendedData.slice( offsets[ sectionIndex ], offsets[ sectionIndex + 1 ] );
								sectionEle.attributes.format = 'binary';
								sectionIndex ++;

							}

						} else {

							section.DataArray[ '#text' ] = appendedData.slice( offsets[ sectionIndex ], offsets[ sectionIndex + 1 ] );
							section.DataArray.attributes.format = 'binary';
							sectionIndex ++;

						}

					}

				}

			}

			if ( json.PolyData ) {

				const piece = json.PolyData.Piece;
				const compressed = json.attributes.hasOwnProperty( 'compressor' );

				// Can be optimized
				// Loop through the sections
				const sections = [ 'PointData', 'Points', 'Strips', 'Polys' ];// +['CellData', 'Verts', 'Lines'];
				let sectionIndex = 0;
				const numberOfSections = sections.length;

				while ( sectionIndex < numberOfSections ) {

					const section = piece[ sections[ sectionIndex ] ];

					// If it has a DataArray in it

					if ( section && section.DataArray ) {

						// Depending on the number of DataArrays

						let arr;

						if ( Array.isArray( section.DataArray ) ) {

							arr = section.DataArray;

						} else {

							arr = [ section.DataArray ];

						}

						let dataArrayIndex = 0;
						const numberOfDataArrays = arr.length;

						while ( dataArrayIndex < numberOfDataArrays ) {

							// Parse the DataArray
							if ( ( '#text' in arr[ dataArrayIndex ] ) && ( arr[ dataArrayIndex ][ '#text' ].length > 0 ) ) {

								arr[ dataArrayIndex ].text = parseDataArray( arr[ dataArrayIndex ], compressed );

							}

							dataArrayIndex ++;

						}

						switch ( sections[ sectionIndex ] ) {

							// if iti is point data
							case 'PointData':

								{

									const numberOfPoints = parseInt( piece.attributes.NumberOfPoints );
									const normalsName = section.attributes.Normals;

									if ( numberOfPoints > 0 ) {

										for ( let i = 0, len = arr.length; i < len; i ++ ) {

											if ( normalsName === arr[ i ].attributes.Name ) {

												const components = arr[ i ].attributes.NumberOfComponents;
												normals = new Float32Array( numberOfPoints * components );
												normals.set( arr[ i ].text, 0 );

											}

										}

									}

								}

								break;

							// if it is points
							case 'Points':

								{

									const numberOfPoints = parseInt( piece.attributes.NumberOfPoints );

									if ( numberOfPoints > 0 ) {

										const components = section.DataArray.attributes.NumberOfComponents;
										points = new Float32Array( numberOfPoints * components );
										points.set( section.DataArray.text, 0 );

									}

								}

								break;

							// if it is strips
							case 'Strips':

								{

									const numberOfStrips = parseInt( piece.attributes.NumberOfStrips );

									if ( numberOfStrips > 0 ) {

										const connectivity = new Int32Array( section.DataArray[ 0 ].text.length );
										const offset = new Int32Array( section.DataArray[ 1 ].text.length );
										connectivity.set( section.DataArray[ 0 ].text, 0 );
										offset.set( section.DataArray[ 1 ].text, 0 );

										const size = numberOfStrips + connectivity.length;
										indices = new Uint32Array( 3 * size - 9 * numberOfStrips );

										let indicesIndex = 0;

										for ( let i = 0, len = numberOfStrips; i < len; i ++ ) {

											const strip = [];

											for ( let s = 0, len1 = offset[ i ], len0 = 0; s < len1 - len0; s ++ ) {

												strip.push( connectivity[ s ] );

												if ( i > 0 ) len0 = offset[ i - 1 ];

											}

											for ( let j = 0, len1 = offset[ i ], len0 = 0; j < len1 - len0 - 2; j ++ ) {

												if ( j % 2 ) {

													indices[ indicesIndex ++ ] = strip[ j ];
													indices[ indicesIndex ++ ] = strip[ j + 2 ];
													indices[ indicesIndex ++ ] = strip[ j + 1 ];

												} else {

													indices[ indicesIndex ++ ] = strip[ j ];
													indices[ indicesIndex ++ ] = strip[ j + 1 ];
													indices[ indicesIndex ++ ] = strip[ j + 2 ];

												}

												if ( i > 0 ) len0 = offset[ i - 1 ];

											}

										}

									}

								}

								break;

							// if it is polys
							case 'Polys':

								{

									const numberOfPolys = parseInt( piece.attributes.NumberOfPolys );

									if ( numberOfPolys > 0 ) {

										const connectivity = new Int32Array( section.DataArray[ 0 ].text.length );
										const offset = new Int32Array( section.DataArray[ 1 ].text.length );
										connectivity.set( section.DataArray[ 0 ].text, 0 );
										offset.set( section.DataArray[ 1 ].text, 0 );

										const size = numberOfPolys + connectivity.length;
										indices = new Uint32Array( 3 * size - 9 * numberOfPolys );
										let indicesIndex = 0, connectivityIndex = 0;
										let i = 0, len0 = 0;
										const len = numberOfPolys;

										while ( i < len ) {

											const poly = [];
											let s = 0;
											const len1 = offset[ i ];

											while ( s < len1 - len0 ) {

												poly.push( connectivity[ connectivityIndex ++ ] );
												s ++;

											}

											let j = 1;

											while ( j < len1 - len0 - 1 ) {

												indices[ indicesIndex ++ ] = poly[ 0 ];
												indices[ indicesIndex ++ ] = poly[ j ];
												indices[ indicesIndex ++ ] = poly[ j + 1 ];
												j ++;

											}

											i ++;
											len0 = offset[ i - 1 ];

										}

									}

								}

								break;

							default:
								break;

						}

					}

					sectionIndex ++;

				}

				const geometry = new BufferGeometry();
				geometry.setIndex( new BufferAttribute( indices, 1 ) );
				geometry.setAttribute( 'position', new BufferAttribute( points, 3 ) );

				if ( normals.length === points.length ) {

					geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

				}

				return geometry;

			} else {

				throw new Error( 'Unsupported DATASET type' );

			}

		}

		const textDecoder = new TextDecoder();

		// get the 5 first lines of the files to check if there is the key word binary
		const meta = textDecoder.decode( new Uint8Array( data, 0, 250 ) ).split( '\n' );

		if ( meta[ 0 ].indexOf( 'xml' ) !== - 1 ) {

			return parseXML( textDecoder.decode( data ) );

		} else if ( meta[ 2 ].includes( 'ASCII' ) ) {

			return parseASCII( textDecoder.decode( data ) );

		} else {

			return parseBinary( data );

		}

	}
```
</details>

### `parseASCII(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `data.split`
- `lines[ i ].trim`
- `line.indexOf`
- `line.split`
- `pat3Floats.exec`
- `patWord.exec`
- `parseFloat`
- `positions.push`
- `patConnectivity.exec`
- `parseInt`
- `result[ 2 ].split`
- `indices.push`
- `color.setRGB`
- `colors.push`
- `normals.push`
- `patPOLYGONS.exec`
- `patPOINTS.exec`
- `patTRIANGLE_STRIPS.exec`
- `patPOINT_DATA.exec`
- `patCELL_DATA.exec`
- `patCOLOR_SCALARS.exec`
- `patNORMALS.exec`
- `geometry.setIndex`
- `geometry.setAttribute`
- `geometry.toNonIndexed`
- `newColors.push`

**Internal Comments:**
```
// connectivity of the triangles (x2)
// triangles vertices (x2)
// red, green, blue colors in the range 0 to 1 (x2)
// normal vector, one per vertex (x2)
// pattern for detecting the end of a number sequence (x2)
// pattern for reading vertices, 3 floats or integers (x2)
// pattern for connectivity, an integer followed by any number of ints (x2)
// the first integer is the number of polygon nodes (x2)
// indicates start of vertex data section (x2)
// indicates start of polygon connectivity section (x2)
// indicates start of triangle strips section (x2)
// POINT_DATA number_of_values (x2)
// CELL_DATA number_of_polys (x2)
// Start of color section (x2)
// NORMALS Normals float (x2)
// get the vertices
// numVertices i0 i1 i2 ... (x4)
// split the polygon in numVertices - 2 triangles (x2)
// Get the colors
// Get the normal vectors
// stagger
// cell (x3)
```

<details><summary>Code</summary>

```typescript
function parseASCII( data ) {

			// connectivity of the triangles
			const indices = [];

			// triangles vertices
			const positions = [];

			// red, green, blue colors in the range 0 to 1
			const colors = [];

			// normal vector, one per vertex
			const normals = [];

			let result;

			// pattern for detecting the end of a number sequence
			const patWord = /^[^\d.\s-]+/;

			// pattern for reading vertices, 3 floats or integers
			const pat3Floats = /(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)/g;

			// pattern for connectivity, an integer followed by any number of ints
			// the first integer is the number of polygon nodes
			const patConnectivity = /^(\d+)\s+([\s\d]*)/;

			// indicates start of vertex data section
			const patPOINTS = /^POINTS /;

			// indicates start of polygon connectivity section
			const patPOLYGONS = /^POLYGONS /;

			// indicates start of triangle strips section
			const patTRIANGLE_STRIPS = /^TRIANGLE_STRIPS /;

			// POINT_DATA number_of_values
			const patPOINT_DATA = /^POINT_DATA[ ]+(\d+)/;

			// CELL_DATA number_of_polys
			const patCELL_DATA = /^CELL_DATA[ ]+(\d+)/;

			// Start of color section
			const patCOLOR_SCALARS = /^COLOR_SCALARS[ ]+(\w+)[ ]+3/;

			// NORMALS Normals float
			const patNORMALS = /^NORMALS[ ]+(\w+)[ ]+(\w+)/;

			let inPointsSection = false;
			let inPolygonsSection = false;
			let inTriangleStripSection = false;
			let inPointDataSection = false;
			let inCellDataSection = false;
			let inColorSection = false;
			let inNormalsSection = false;

			const color = new Color();

			const lines = data.split( '\n' );

			for ( const i in lines ) {

				const line = lines[ i ].trim();

				if ( line.indexOf( 'DATASET' ) === 0 ) {

					const dataset = line.split( ' ' )[ 1 ];

					if ( dataset !== 'POLYDATA' ) throw new Error( 'Unsupported DATASET type: ' + dataset );

				} else if ( inPointsSection ) {

					// get the vertices
					while ( ( result = pat3Floats.exec( line ) ) !== null ) {

						if ( patWord.exec( line ) !== null ) break;

						const x = parseFloat( result[ 1 ] );
						const y = parseFloat( result[ 2 ] );
						const z = parseFloat( result[ 3 ] );
						positions.push( x, y, z );

					}

				} else if ( inPolygonsSection ) {

					if ( ( result = patConnectivity.exec( line ) ) !== null ) {

						// numVertices i0 i1 i2 ...
						const numVertices = parseInt( result[ 1 ] );
						const inds = result[ 2 ].split( /\s+/ );

						if ( numVertices >= 3 ) {

							const i0 = parseInt( inds[ 0 ] );
							let k = 1;
							// split the polygon in numVertices - 2 triangles
							for ( let j = 0; j < numVertices - 2; ++ j ) {

								const i1 = parseInt( inds[ k ] );
								const i2 = parseInt( inds[ k + 1 ] );
								indices.push( i0, i1, i2 );
								k ++;

							}

						}

					}

				} else if ( inTriangleStripSection ) {

					if ( ( result = patConnectivity.exec( line ) ) !== null ) {

						// numVertices i0 i1 i2 ...
						const numVertices = parseInt( result[ 1 ] );
						const inds = result[ 2 ].split( /\s+/ );

						if ( numVertices >= 3 ) {

							// split the polygon in numVertices - 2 triangles
							for ( let j = 0; j < numVertices - 2; j ++ ) {

								if ( j % 2 === 1 ) {

									const i0 = parseInt( inds[ j ] );
									const i1 = parseInt( inds[ j + 2 ] );
									const i2 = parseInt( inds[ j + 1 ] );
									indices.push( i0, i1, i2 );

								} else {

									const i0 = parseInt( inds[ j ] );
									const i1 = parseInt( inds[ j + 1 ] );
									const i2 = parseInt( inds[ j + 2 ] );
									indices.push( i0, i1, i2 );

								}

							}

						}

					}

				} else if ( inPointDataSection || inCellDataSection ) {

					if ( inColorSection ) {

						// Get the colors

						while ( ( result = pat3Floats.exec( line ) ) !== null ) {

							if ( patWord.exec( line ) !== null ) break;

							const r = parseFloat( result[ 1 ] );
							const g = parseFloat( result[ 2 ] );
							const b = parseFloat( result[ 3 ] );

							color.setRGB( r, g, b, SRGBColorSpace );

							colors.push( color.r, color.g, color.b );

						}

					} else if ( inNormalsSection ) {

						// Get the normal vectors

						while ( ( result = pat3Floats.exec( line ) ) !== null ) {

							if ( patWord.exec( line ) !== null ) break;

							const nx = parseFloat( result[ 1 ] );
							const ny = parseFloat( result[ 2 ] );
							const nz = parseFloat( result[ 3 ] );
							normals.push( nx, ny, nz );

						}

					}

				}

				if ( patPOLYGONS.exec( line ) !== null ) {

					inPolygonsSection = true;
					inPointsSection = false;
					inTriangleStripSection = false;

				} else if ( patPOINTS.exec( line ) !== null ) {

					inPolygonsSection = false;
					inPointsSection = true;
					inTriangleStripSection = false;

				} else if ( patTRIANGLE_STRIPS.exec( line ) !== null ) {

					inPolygonsSection = false;
					inPointsSection = false;
					inTriangleStripSection = true;

				} else if ( patPOINT_DATA.exec( line ) !== null ) {

					inPointDataSection = true;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patCELL_DATA.exec( line ) !== null ) {

					inCellDataSection = true;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patCOLOR_SCALARS.exec( line ) !== null ) {

					inColorSection = true;
					inNormalsSection = false;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patNORMALS.exec( line ) !== null ) {

					inNormalsSection = true;
					inColorSection = false;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				}

			}

			let geometry = new BufferGeometry();
			geometry.setIndex( indices );
			geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );

			if ( normals.length === positions.length ) {

				geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

			}

			if ( colors.length !== indices.length ) {

				// stagger

				if ( colors.length === positions.length ) {

					geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

				}

			} else {

				// cell

				geometry = geometry.toNonIndexed();
				const numTriangles = geometry.attributes.position.count / 3;

				if ( colors.length === ( numTriangles * 3 ) ) {

					const newColors = [];

					for ( let i = 0; i < numTriangles; i ++ ) {

						const r = colors[ 3 * i + 0 ];
						const g = colors[ 3 * i + 1 ];
						const b = colors[ 3 * i + 2 ];

						color.setRGB( r, g, b, SRGBColorSpace );

						newColors.push( color.r, color.g, color.b );
						newColors.push( color.r, color.g, color.b );
						newColors.push( color.r, color.g, color.b );

					}

					geometry.setAttribute( 'color', new Float32BufferAttribute( newColors, 3 ) );

				}

			}

			return geometry;

		}
```
</details>

### `parseBinary(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `s.push`
- `String.fromCharCode`
- `s.join`
- `findString`
- `line.indexOf`
- `line.split`
- `parseInt`
- `dataView.getFloat32`
- `dataView.getInt32`
- `strip.push`
- `geometry.setIndex`
- `geometry.setAttribute`

**Internal Comments:**
```
// Points and normals, by default, are empty (x2)
// Get a string (x3)
// Add the points (x2)
// Each point is 3 4-byte floats (x2)
// increment our next pointer (x12)
// 4 byte integers (x4)
// For each strip, read the first value, then record that many more points (x4)
// retrieves the n-2 triangles from the triangle strip
// divide the polygon in n-2 triangle
// Grab the next line (x3)
// Now grab the binary data (x2)
// Increment past our data (x4)
// Increment index (x3)
```

<details><summary>Code</summary>

```typescript
function parseBinary( data ) {

			const buffer = new Uint8Array( data );
			const dataView = new DataView( data );

			// Points and normals, by default, are empty
			let points = [];
			let normals = [];
			let indices = [];

			let index = 0;

			function findString( buffer, start ) {

				let index = start;
				let c = buffer[ index ];
				const s = [];
				while ( c !== 10 ) {

					s.push( String.fromCharCode( c ) );
					index ++;
					c = buffer[ index ];

				}

				return { start: start,
					end: index,
					next: index + 1,
					parsedString: s.join( '' ) };

			}

			let state, line;

			while ( true ) {

				// Get a string
				state = findString( buffer, index );
				line = state.parsedString;

				if ( line.indexOf( 'DATASET' ) === 0 ) {

					const dataset = line.split( ' ' )[ 1 ];

					if ( dataset !== 'POLYDATA' ) throw new Error( 'Unsupported DATASET type: ' + dataset );

				} else if ( line.indexOf( 'POINTS' ) === 0 ) {

					// Add the points
					const numberOfPoints = parseInt( line.split( ' ' )[ 1 ], 10 );

					// Each point is 3 4-byte floats
					const count = numberOfPoints * 4 * 3;

					points = new Float32Array( numberOfPoints * 3 );

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfPoints; i ++ ) {

						points[ 3 * i ] = dataView.getFloat32( pointIndex, false );
						points[ 3 * i + 1 ] = dataView.getFloat32( pointIndex + 4, false );
						points[ 3 * i + 2 ] = dataView.getFloat32( pointIndex + 8, false );
						pointIndex = pointIndex + 12;

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'TRIANGLE_STRIPS' ) === 0 ) {

					const numberOfStrips = parseInt( line.split( ' ' )[ 1 ], 10 );
					const size = parseInt( line.split( ' ' )[ 2 ], 10 );
					// 4 byte integers
					const count = size * 4;

					indices = new Uint32Array( 3 * size - 9 * numberOfStrips );
					let indicesIndex = 0;

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfStrips; i ++ ) {

						// For each strip, read the first value, then record that many more points
						const indexCount = dataView.getInt32( pointIndex, false );
						const strip = [];
						pointIndex += 4;
						for ( let s = 0; s < indexCount; s ++ ) {

							strip.push( dataView.getInt32( pointIndex, false ) );
							pointIndex += 4;

						}

						// retrieves the n-2 triangles from the triangle strip
						for ( let j = 0; j < indexCount - 2; j ++ ) {

							if ( j % 2 ) {

								indices[ indicesIndex ++ ] = strip[ j ];
								indices[ indicesIndex ++ ] = strip[ j + 2 ];
								indices[ indicesIndex ++ ] = strip[ j + 1 ];

							} else {

								indices[ indicesIndex ++ ] = strip[ j ];
								indices[ indicesIndex ++ ] = strip[ j + 1 ];
								indices[ indicesIndex ++ ] = strip[ j + 2 ];

							}

						}

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'POLYGONS' ) === 0 ) {

					const numberOfStrips = parseInt( line.split( ' ' )[ 1 ], 10 );
					const size = parseInt( line.split( ' ' )[ 2 ], 10 );
					// 4 byte integers
					const count = size * 4;

					indices = new Uint32Array( 3 * size - 9 * numberOfStrips );
					let indicesIndex = 0;

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfStrips; i ++ ) {

						// For each strip, read the first value, then record that many more points
						const indexCount = dataView.getInt32( pointIndex, false );
						const strip = [];
						pointIndex += 4;
						for ( let s = 0; s < indexCount; s ++ ) {

							strip.push( dataView.getInt32( pointIndex, false ) );
							pointIndex += 4;

						}

						// divide the polygon in n-2 triangle
						for ( let j = 1; j < indexCount - 1; j ++ ) {

							indices[ indicesIndex ++ ] = strip[ 0 ];
							indices[ indicesIndex ++ ] = strip[ j ];
							indices[ indicesIndex ++ ] = strip[ j + 1 ];

						}

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'POINT_DATA' ) === 0 ) {

					const numberOfPoints = parseInt( line.split( ' ' )[ 1 ], 10 );

					// Grab the next line
					state = findString( buffer, state.next );

					// Now grab the binary data
					const count = numberOfPoints * 4 * 3;

					normals = new Float32Array( numberOfPoints * 3 );
					let pointIndex = state.next;
					for ( let i = 0; i < numberOfPoints; i ++ ) {

						normals[ 3 * i ] = dataView.getFloat32( pointIndex, false );
						normals[ 3 * i + 1 ] = dataView.getFloat32( pointIndex + 4, false );
						normals[ 3 * i + 2 ] = dataView.getFloat32( pointIndex + 8, false );
						pointIndex += 12;

					}

					// Increment past our data
					state.next = state.next + count;

				}

				// Increment index
				index = state.next;

				if ( index >= buffer.byteLength ) {

					break;

				}

			}

			const geometry = new BufferGeometry();
			geometry.setIndex( new BufferAttribute( indices, 1 ) );
			geometry.setAttribute( 'position', new BufferAttribute( points, 3 ) );

			if ( normals.length === points.length ) {

				geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

			}

			return geometry;

		}
```
</details>

### `findString(buffer: any, start: any): { start: any; end: any; next: any; parsedString: string; }`

**Parameters:**

- **`buffer`** `any`
- **`start`** `any`

**Returns:** `{ start: any; end: any; next: any; parsedString: string; }`

**Calls:**

- `s.push`
- `String.fromCharCode`
- `s.join`

<details><summary>Code</summary>

```typescript
function findString( buffer, start ) {

				let index = start;
				let c = buffer[ index ];
				const s = [];
				while ( c !== 10 ) {

					s.push( String.fromCharCode( c ) );
					index ++;
					c = buffer[ index ];

				}

				return { start: start,
					end: index,
					next: index + 1,
					parsedString: s.join( '' ) };

			}
```
</details>

### `Float32Concat(first: any, second: any): Float32Array<any>`

**Parameters:**

- **`first`** `any`
- **`second`** `any`

**Returns:** `Float32Array<any>`

**Calls:**

- `result.set`

<details><summary>Code</summary>

```typescript
function Float32Concat( first, second ) {

			const firstLength = first.length, result = new Float32Array( firstLength + second.length );

			result.set( first );
			result.set( second, firstLength );

			return result;

		}
```
</details>

### `Int32Concat(first: any, second: any): Int32Array<any>`

**Parameters:**

- **`first`** `any`
- **`second`** `any`

**Returns:** `Int32Array<any>`

**Calls:**

- `result.set`

<details><summary>Code</summary>

```typescript
function Int32Concat( first, second ) {

			const firstLength = first.length, result = new Int32Array( firstLength + second.length );

			result.set( first );
			result.set( second, firstLength );

			return result;

		}
```
</details>

### `parseXML(stringFile: any): any`

**Parameters:**

- **`stringFile`** `any`

**Returns:** `any`

**Calls:**

- `xml.attributes.item`
- `attribute.nodeValue.trim`
- `xml.nodeValue.trim`
- `xml.hasChildNodes`
- `xml.childNodes.item`
- `xmlToJson`
- `Array.isArray`
- `obj[ nodeName ].push`
- `code.charCodeAt`
- `'-'.charCodeAt`
- `'_'.charCodeAt`
- `b64.charCodeAt`
- `Base64toByteArray`
- `dataOffsets.push`
- `fflate.unzlibSync`
- `byteData.slice`
- `Float32Concat`
- `Int32Concat`
- `txt.filter`
- `content.slice`
- `ele[ '#text' ].split( /\s+/ ).filter`
- `new DOMParser().parseFromString`
- `json.AppendedData[ '#text' ].slice`
- `sections.map( s => {

					const sect = piece[ s ];

					if ( sect && sect.DataArray ) {

						const arr = Array.isArray( sect.DataArray ) ? sect.DataArray : [ sect.DataArray ];

						return arr.map( a => a.attributes.offset );

					}

					return [];

				} ).flat`
- `appendedData.slice`
- `json.attributes.hasOwnProperty`
- `parseDataArray`
- `parseInt`
- `normals.set`
- `points.set`
- `connectivity.set`
- `offset.set`
- `strip.push`
- `poly.push`
- `geometry.setIndex`
- `geometry.setAttribute`

**Internal Comments:**
```
// Changes XML to JSON, based on https://davidwalsh.name/convert-xml-json
// Create the return object (x2)
// do attributes
// do children
// Taken from Base64-js
// Check the format
// VTP data with the header has the following structure: (x2)
// [#blocks][#u-size][#p-size][#c-size-1][#c-size-2]...[#c-size-#blocks][DATA] (x2)
// (x4)
// Each token is an integer value whose type is specified by "header_type" at the top of the file (UInt32 if no type specified). The token meanings are: (x2)
// [#blocks] = Number of blocks (x2)
// [#u-size] = Block size before compression (x2)
// [#p-size] = Size of last partial block (zero if it not needed) (x2)
// [#c-size-i] = Size in bytes of block i after compression (x2)
// The [DATA] portion stores contiguously every block appended together. The offset from the beginning of the data section to the beginning of a block is (x2)
// computed by summing the compressed block sizes from preceding blocks according to the header. (x2)
// Each data point consists of 8 bits regardless of the header type (x2)
// Get the blocks sizes after the compression. (x2)
// There are three blocks before c-size-i, so we skip 3*numBytes (x2)
//  VTP data for the uncompressed case has the following structure: (x3)
// [#bytes][DATA] (x3)
// where "[#bytes]" is an integer value specifying the number of bytes in the block of data following it. (x3)
// Get the content and optimize it
// Main part (x2)
// Get Dom (x2)
// Get the doc (x2)
// Convert to json (x2)
// Can be optimized (x2)
// Loop through the sections (x2)
// If it has a DataArray in it
// Depending on the number of DataArrays (x2)
// Parse the DataArray
// if iti is point data
// if it is points
// if it is strips
// if it is polys
```

<details><summary>Code</summary>

```typescript
function parseXML( stringFile ) {

			// Changes XML to JSON, based on https://davidwalsh.name/convert-xml-json

			function xmlToJson( xml ) {

				// Create the return object
				let obj = {};

				if ( xml.nodeType === 1 ) { // element

					// do attributes

					if ( xml.attributes ) {

						if ( xml.attributes.length > 0 ) {

							obj[ 'attributes' ] = {};

							for ( let j = 0; j < xml.attributes.length; j ++ ) {

								const attribute = xml.attributes.item( j );
								obj[ 'attributes' ][ attribute.nodeName ] = attribute.nodeValue.trim();

							}

						}

					}

				} else if ( xml.nodeType === 3 ) { // text

					obj = xml.nodeValue.trim();

				}

				// do children
				if ( xml.hasChildNodes() ) {

					for ( let i = 0; i < xml.childNodes.length; i ++ ) {

						const item = xml.childNodes.item( i );
						const nodeName = item.nodeName;

						if ( typeof obj[ nodeName ] === 'undefined' ) {

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ] = tmp;

							}

						} else {

							if ( typeof obj[ nodeName ].push === 'undefined' ) {

								const old = obj[ nodeName ];
								obj[ nodeName ] = [ old ];

							}

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ].push( tmp );

							}

						}

					}

				}

				return obj;

			}

			// Taken from Base64-js
			function Base64toByteArray( b64 ) {

				const Arr = typeof Uint8Array !== 'undefined' ? Uint8Array : Array;
				const revLookup = [];
				const code = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/';

				for ( let i = 0, l = code.length; i < l; ++ i ) {

					revLookup[ code.charCodeAt( i ) ] = i;

				}

				revLookup[ '-'.charCodeAt( 0 ) ] = 62;
				revLookup[ '_'.charCodeAt( 0 ) ] = 63;

				const len = b64.length;

				if ( len % 4 > 0 ) {

					throw new Error( 'Invalid string. Length must be a multiple of 4' );

				}

				const placeHolders = b64[ len - 2 ] === '=' ? 2 : b64[ len - 1 ] === '=' ? 1 : 0;
				const arr = new Arr( len * 3 / 4 - placeHolders );
				const l = placeHolders > 0 ? len - 4 : len;

				let L = 0;
				let i, j;

				for ( i = 0, j = 0; i < l; i += 4, j += 3 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 18 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 12 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] << 6 ) | revLookup[ b64.charCodeAt( i + 3 ) ];
					arr[ L ++ ] = ( tmp & 0xFF0000 ) >> 16;
					arr[ L ++ ] = ( tmp & 0xFF00 ) >> 8;
					arr[ L ++ ] = tmp & 0xFF;

				}

				if ( placeHolders === 2 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 2 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] >> 4 );
					arr[ L ++ ] = tmp & 0xFF;

				} else if ( placeHolders === 1 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 10 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 4 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] >> 2 );
					arr[ L ++ ] = ( tmp >> 8 ) & 0xFF;
					arr[ L ++ ] = tmp & 0xFF;

				}

				return arr;

			}

			function parseDataArray( ele, compressed ) {

				let numBytes = 0;

				if ( json.attributes.header_type === 'UInt64' ) {

					numBytes = 8;

				}	else if ( json.attributes.header_type === 'UInt32' ) {

					numBytes = 4;

				}

				let txt, content;

				// Check the format
				if ( ele.attributes.format === 'binary' && compressed ) {

					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( );

					} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( );

					}

					// VTP data with the header has the following structure:
					// [#blocks][#u-size][#p-size][#c-size-1][#c-size-2]...[#c-size-#blocks][DATA]
					//
					// Each token is an integer value whose type is specified by "header_type" at the top of the file (UInt32 if no type specified). The token meanings are:
					// [#blocks] = Number of blocks
					// [#u-size] = Block size before compression
					// [#p-size] = Size of last partial block (zero if it not needed)
					// [#c-size-i] = Size in bytes of block i after compression
					//
					// The [DATA] portion stores contiguously every block appended together. The offset from the beginning of the data section to the beginning of a block is
					// computed by summing the compressed block sizes from preceding blocks according to the header.

					const textNode = ele[ '#text' ];
					const rawData = Array.isArray( textNode ) ? textNode[ 0 ] : textNode;

					const byteData = Base64toByteArray( rawData );

					// Each data point consists of 8 bits regardless of the header type
					const dataPointSize = 8;

					let blocks = byteData[ 0 ];
					for ( let i = 1; i < numBytes - 1; i ++ ) {

						blocks = blocks | ( byteData[ i ] << ( i * dataPointSize ) );

					}

					let headerSize = ( blocks + 3 ) * numBytes;
					const padding = ( ( headerSize % 3 ) > 0 ) ? 3 - ( headerSize % 3 ) : 0;
					headerSize = headerSize + padding;

					const dataOffsets = [];
					let currentOffset = headerSize;
					dataOffsets.push( currentOffset );

					// Get the blocks sizes after the compression.
					// There are three blocks before c-size-i, so we skip 3*numBytes
					const cSizeStart = 3 * numBytes;

					for ( let i = 0; i < blocks; i ++ ) {

						let currentBlockSize = byteData[ i * numBytes + cSizeStart ];

						for ( let j = 1; j < numBytes - 1; j ++ ) {

							currentBlockSize = currentBlockSize | ( byteData[ i * numBytes + cSizeStart + j ] << ( j * dataPointSize ) );

						}

						currentOffset = currentOffset + currentBlockSize;
						dataOffsets.push( currentOffset );

					}

					for ( let i = 0; i < dataOffsets.length - 1; i ++ ) {

						const data = fflate.unzlibSync( byteData.slice( dataOffsets[ i ], dataOffsets[ i + 1 ] ) );
						content = data.buffer;

						if ( ele.attributes.type === 'Float32' ) {

							content = new Float32Array( content );
							txt = Float32Concat( txt, content );

						} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

							content = new Int32Array( content );
							txt = Int32Concat( txt, content );

						}

					}

					delete ele[ '#text' ];

					if ( ele.attributes.type === 'Int64' ) {

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} else {

					if ( ele.attributes.format === 'binary' && ! compressed ) {

						content = Base64toByteArray( ele[ '#text' ] );

						//  VTP data for the uncompressed case has the following structure:
						// [#bytes][DATA]
						// where "[#bytes]" is an integer value specifying the number of bytes in the block of data following it.
						content = content.slice( numBytes ).buffer;

					} else {

						if ( ele[ '#text' ] ) {

							content = ele[ '#text' ].split( /\s+/ ).filter( function ( el ) {

								if ( el !== '' ) return el;

							} );

						} else {

							content = new Int32Array( 0 ).buffer;

						}

					}

					delete ele[ '#text' ];

					// Get the content and optimize it
					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( content );

					} else if ( ele.attributes.type === 'Int32' ) {

						txt = new Int32Array( content );

					} else if ( ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( content );

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} // endif ( ele.attributes.format === 'binary' && compressed )

				return txt;

			}

			// Main part
			// Get Dom
			const dom = new DOMParser().parseFromString( stringFile, 'application/xml' );

			// Get the doc
			const doc = dom.documentElement;
			// Convert to json
			const json = xmlToJson( doc );
			let points = [];
			let normals = [];
			let indices = [];

			if ( json.AppendedData ) {

				const appendedData = json.AppendedData[ '#text' ].slice( 1 );
				const piece = json.PolyData.Piece;

				const sections = [ 'PointData', 'CellData', 'Points', 'Verts', 'Lines', 'Strips', 'Polys' ];
				let sectionIndex = 0;

				const offsets = sections.map( s => {

					const sect = piece[ s ];

					if ( sect && sect.DataArray ) {

						const arr = Array.isArray( sect.DataArray ) ? sect.DataArray : [ sect.DataArray ];

						return arr.map( a => a.attributes.offset );

					}

					return [];

				} ).flat();

				for ( const sect of sections ) {

					const section = piece[ sect ];

					if ( section && section.DataArray ) {

						if ( Array.isArray( section.DataArray ) ) {

							for ( const sectionEle of section.DataArray ) {

								sectionEle[ '#text' ] = appendedData.slice( offsets[ sectionIndex ], offsets[ sectionIndex + 1 ] );
								sectionEle.attributes.format = 'binary';
								sectionIndex ++;

							}

						} else {

							section.DataArray[ '#text' ] = appendedData.slice( offsets[ sectionIndex ], offsets[ sectionIndex + 1 ] );
							section.DataArray.attributes.format = 'binary';
							sectionIndex ++;

						}

					}

				}

			}

			if ( json.PolyData ) {

				const piece = json.PolyData.Piece;
				const compressed = json.attributes.hasOwnProperty( 'compressor' );

				// Can be optimized
				// Loop through the sections
				const sections = [ 'PointData', 'Points', 'Strips', 'Polys' ];// +['CellData', 'Verts', 'Lines'];
				let sectionIndex = 0;
				const numberOfSections = sections.length;

				while ( sectionIndex < numberOfSections ) {

					const section = piece[ sections[ sectionIndex ] ];

					// If it has a DataArray in it

					if ( section && section.DataArray ) {

						// Depending on the number of DataArrays

						let arr;

						if ( Array.isArray( section.DataArray ) ) {

							arr = section.DataArray;

						} else {

							arr = [ section.DataArray ];

						}

						let dataArrayIndex = 0;
						const numberOfDataArrays = arr.length;

						while ( dataArrayIndex < numberOfDataArrays ) {

							// Parse the DataArray
							if ( ( '#text' in arr[ dataArrayIndex ] ) && ( arr[ dataArrayIndex ][ '#text' ].length > 0 ) ) {

								arr[ dataArrayIndex ].text = parseDataArray( arr[ dataArrayIndex ], compressed );

							}

							dataArrayIndex ++;

						}

						switch ( sections[ sectionIndex ] ) {

							// if iti is point data
							case 'PointData':

								{

									const numberOfPoints = parseInt( piece.attributes.NumberOfPoints );
									const normalsName = section.attributes.Normals;

									if ( numberOfPoints > 0 ) {

										for ( let i = 0, len = arr.length; i < len; i ++ ) {

											if ( normalsName === arr[ i ].attributes.Name ) {

												const components = arr[ i ].attributes.NumberOfComponents;
												normals = new Float32Array( numberOfPoints * components );
												normals.set( arr[ i ].text, 0 );

											}

										}

									}

								}

								break;

							// if it is points
							case 'Points':

								{

									const numberOfPoints = parseInt( piece.attributes.NumberOfPoints );

									if ( numberOfPoints > 0 ) {

										const components = section.DataArray.attributes.NumberOfComponents;
										points = new Float32Array( numberOfPoints * components );
										points.set( section.DataArray.text, 0 );

									}

								}

								break;

							// if it is strips
							case 'Strips':

								{

									const numberOfStrips = parseInt( piece.attributes.NumberOfStrips );

									if ( numberOfStrips > 0 ) {

										const connectivity = new Int32Array( section.DataArray[ 0 ].text.length );
										const offset = new Int32Array( section.DataArray[ 1 ].text.length );
										connectivity.set( section.DataArray[ 0 ].text, 0 );
										offset.set( section.DataArray[ 1 ].text, 0 );

										const size = numberOfStrips + connectivity.length;
										indices = new Uint32Array( 3 * size - 9 * numberOfStrips );

										let indicesIndex = 0;

										for ( let i = 0, len = numberOfStrips; i < len; i ++ ) {

											const strip = [];

											for ( let s = 0, len1 = offset[ i ], len0 = 0; s < len1 - len0; s ++ ) {

												strip.push( connectivity[ s ] );

												if ( i > 0 ) len0 = offset[ i - 1 ];

											}

											for ( let j = 0, len1 = offset[ i ], len0 = 0; j < len1 - len0 - 2; j ++ ) {

												if ( j % 2 ) {

													indices[ indicesIndex ++ ] = strip[ j ];
													indices[ indicesIndex ++ ] = strip[ j + 2 ];
													indices[ indicesIndex ++ ] = strip[ j + 1 ];

												} else {

													indices[ indicesIndex ++ ] = strip[ j ];
													indices[ indicesIndex ++ ] = strip[ j + 1 ];
													indices[ indicesIndex ++ ] = strip[ j + 2 ];

												}

												if ( i > 0 ) len0 = offset[ i - 1 ];

											}

										}

									}

								}

								break;

							// if it is polys
							case 'Polys':

								{

									const numberOfPolys = parseInt( piece.attributes.NumberOfPolys );

									if ( numberOfPolys > 0 ) {

										const connectivity = new Int32Array( section.DataArray[ 0 ].text.length );
										const offset = new Int32Array( section.DataArray[ 1 ].text.length );
										connectivity.set( section.DataArray[ 0 ].text, 0 );
										offset.set( section.DataArray[ 1 ].text, 0 );

										const size = numberOfPolys + connectivity.length;
										indices = new Uint32Array( 3 * size - 9 * numberOfPolys );
										let indicesIndex = 0, connectivityIndex = 0;
										let i = 0, len0 = 0;
										const len = numberOfPolys;

										while ( i < len ) {

											const poly = [];
											let s = 0;
											const len1 = offset[ i ];

											while ( s < len1 - len0 ) {

												poly.push( connectivity[ connectivityIndex ++ ] );
												s ++;

											}

											let j = 1;

											while ( j < len1 - len0 - 1 ) {

												indices[ indicesIndex ++ ] = poly[ 0 ];
												indices[ indicesIndex ++ ] = poly[ j ];
												indices[ indicesIndex ++ ] = poly[ j + 1 ];
												j ++;

											}

											i ++;
											len0 = offset[ i - 1 ];

										}

									}

								}

								break;

							default:
								break;

						}

					}

					sectionIndex ++;

				}

				const geometry = new BufferGeometry();
				geometry.setIndex( new BufferAttribute( indices, 1 ) );
				geometry.setAttribute( 'position', new BufferAttribute( points, 3 ) );

				if ( normals.length === points.length ) {

					geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

				}

				return geometry;

			} else {

				throw new Error( 'Unsupported DATASET type' );

			}

		}
```
</details>

### `xmlToJson(xml: any): { attributes: {}; }`

**Parameters:**

- **`xml`** `any`

**Returns:** `{ attributes: {}; }`

**Calls:**

- `xml.attributes.item`
- `attribute.nodeValue.trim`
- `xml.nodeValue.trim`
- `xml.hasChildNodes`
- `xml.childNodes.item`
- `xmlToJson`
- `Array.isArray`
- `obj[ nodeName ].push`

**Internal Comments:**
```
// Create the return object (x2)
// do attributes
// do children
```

<details><summary>Code</summary>

```typescript
function xmlToJson( xml ) {

				// Create the return object
				let obj = {};

				if ( xml.nodeType === 1 ) { // element

					// do attributes

					if ( xml.attributes ) {

						if ( xml.attributes.length > 0 ) {

							obj[ 'attributes' ] = {};

							for ( let j = 0; j < xml.attributes.length; j ++ ) {

								const attribute = xml.attributes.item( j );
								obj[ 'attributes' ][ attribute.nodeName ] = attribute.nodeValue.trim();

							}

						}

					}

				} else if ( xml.nodeType === 3 ) { // text

					obj = xml.nodeValue.trim();

				}

				// do children
				if ( xml.hasChildNodes() ) {

					for ( let i = 0; i < xml.childNodes.length; i ++ ) {

						const item = xml.childNodes.item( i );
						const nodeName = item.nodeName;

						if ( typeof obj[ nodeName ] === 'undefined' ) {

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ] = tmp;

							}

						} else {

							if ( typeof obj[ nodeName ].push === 'undefined' ) {

								const old = obj[ nodeName ];
								obj[ nodeName ] = [ old ];

							}

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ].push( tmp );

							}

						}

					}

				}

				return obj;

			}
```
</details>

### `Base64toByteArray(b64: any): any[] | Uint8Array<ArrayBuffer>`

**Parameters:**

- **`b64`** `any`

**Returns:** `any[] | Uint8Array<ArrayBuffer>`

**Calls:**

- `code.charCodeAt`
- `'-'.charCodeAt`
- `'_'.charCodeAt`
- `b64.charCodeAt`

<details><summary>Code</summary>

```typescript
function Base64toByteArray( b64 ) {

				const Arr = typeof Uint8Array !== 'undefined' ? Uint8Array : Array;
				const revLookup = [];
				const code = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/';

				for ( let i = 0, l = code.length; i < l; ++ i ) {

					revLookup[ code.charCodeAt( i ) ] = i;

				}

				revLookup[ '-'.charCodeAt( 0 ) ] = 62;
				revLookup[ '_'.charCodeAt( 0 ) ] = 63;

				const len = b64.length;

				if ( len % 4 > 0 ) {

					throw new Error( 'Invalid string. Length must be a multiple of 4' );

				}

				const placeHolders = b64[ len - 2 ] === '=' ? 2 : b64[ len - 1 ] === '=' ? 1 : 0;
				const arr = new Arr( len * 3 / 4 - placeHolders );
				const l = placeHolders > 0 ? len - 4 : len;

				let L = 0;
				let i, j;

				for ( i = 0, j = 0; i < l; i += 4, j += 3 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 18 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 12 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] << 6 ) | revLookup[ b64.charCodeAt( i + 3 ) ];
					arr[ L ++ ] = ( tmp & 0xFF0000 ) >> 16;
					arr[ L ++ ] = ( tmp & 0xFF00 ) >> 8;
					arr[ L ++ ] = tmp & 0xFF;

				}

				if ( placeHolders === 2 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 2 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] >> 4 );
					arr[ L ++ ] = tmp & 0xFF;

				} else if ( placeHolders === 1 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 10 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 4 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] >> 2 );
					arr[ L ++ ] = ( tmp >> 8 ) & 0xFF;
					arr[ L ++ ] = tmp & 0xFF;

				}

				return arr;

			}
```
</details>

### `parseDataArray(ele: any, compressed: any): Int32Array<any> | Float32Array<any>`

**Parameters:**

- **`ele`** `any`
- **`compressed`** `any`

**Returns:** `Int32Array<any> | Float32Array<any>`

**Calls:**

- `Array.isArray`
- `Base64toByteArray`
- `dataOffsets.push`
- `fflate.unzlibSync`
- `byteData.slice`
- `Float32Concat`
- `Int32Concat`
- `txt.filter`
- `content.slice`
- `ele[ '#text' ].split( /\s+/ ).filter`

**Internal Comments:**
```
// Check the format
// VTP data with the header has the following structure: (x2)
// [#blocks][#u-size][#p-size][#c-size-1][#c-size-2]...[#c-size-#blocks][DATA] (x2)
// (x4)
// Each token is an integer value whose type is specified by "header_type" at the top of the file (UInt32 if no type specified). The token meanings are: (x2)
// [#blocks] = Number of blocks (x2)
// [#u-size] = Block size before compression (x2)
// [#p-size] = Size of last partial block (zero if it not needed) (x2)
// [#c-size-i] = Size in bytes of block i after compression (x2)
// The [DATA] portion stores contiguously every block appended together. The offset from the beginning of the data section to the beginning of a block is (x2)
// computed by summing the compressed block sizes from preceding blocks according to the header. (x2)
// Each data point consists of 8 bits regardless of the header type (x2)
// Get the blocks sizes after the compression. (x2)
// There are three blocks before c-size-i, so we skip 3*numBytes (x2)
//  VTP data for the uncompressed case has the following structure: (x3)
// [#bytes][DATA] (x3)
// where "[#bytes]" is an integer value specifying the number of bytes in the block of data following it. (x3)
// Get the content and optimize it
```

<details><summary>Code</summary>

```typescript
function parseDataArray( ele, compressed ) {

				let numBytes = 0;

				if ( json.attributes.header_type === 'UInt64' ) {

					numBytes = 8;

				}	else if ( json.attributes.header_type === 'UInt32' ) {

					numBytes = 4;

				}

				let txt, content;

				// Check the format
				if ( ele.attributes.format === 'binary' && compressed ) {

					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( );

					} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( );

					}

					// VTP data with the header has the following structure:
					// [#blocks][#u-size][#p-size][#c-size-1][#c-size-2]...[#c-size-#blocks][DATA]
					//
					// Each token is an integer value whose type is specified by "header_type" at the top of the file (UInt32 if no type specified). The token meanings are:
					// [#blocks] = Number of blocks
					// [#u-size] = Block size before compression
					// [#p-size] = Size of last partial block (zero if it not needed)
					// [#c-size-i] = Size in bytes of block i after compression
					//
					// The [DATA] portion stores contiguously every block appended together. The offset from the beginning of the data section to the beginning of a block is
					// computed by summing the compressed block sizes from preceding blocks according to the header.

					const textNode = ele[ '#text' ];
					const rawData = Array.isArray( textNode ) ? textNode[ 0 ] : textNode;

					const byteData = Base64toByteArray( rawData );

					// Each data point consists of 8 bits regardless of the header type
					const dataPointSize = 8;

					let blocks = byteData[ 0 ];
					for ( let i = 1; i < numBytes - 1; i ++ ) {

						blocks = blocks | ( byteData[ i ] << ( i * dataPointSize ) );

					}

					let headerSize = ( blocks + 3 ) * numBytes;
					const padding = ( ( headerSize % 3 ) > 0 ) ? 3 - ( headerSize % 3 ) : 0;
					headerSize = headerSize + padding;

					const dataOffsets = [];
					let currentOffset = headerSize;
					dataOffsets.push( currentOffset );

					// Get the blocks sizes after the compression.
					// There are three blocks before c-size-i, so we skip 3*numBytes
					const cSizeStart = 3 * numBytes;

					for ( let i = 0; i < blocks; i ++ ) {

						let currentBlockSize = byteData[ i * numBytes + cSizeStart ];

						for ( let j = 1; j < numBytes - 1; j ++ ) {

							currentBlockSize = currentBlockSize | ( byteData[ i * numBytes + cSizeStart + j ] << ( j * dataPointSize ) );

						}

						currentOffset = currentOffset + currentBlockSize;
						dataOffsets.push( currentOffset );

					}

					for ( let i = 0; i < dataOffsets.length - 1; i ++ ) {

						const data = fflate.unzlibSync( byteData.slice( dataOffsets[ i ], dataOffsets[ i + 1 ] ) );
						content = data.buffer;

						if ( ele.attributes.type === 'Float32' ) {

							content = new Float32Array( content );
							txt = Float32Concat( txt, content );

						} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

							content = new Int32Array( content );
							txt = Int32Concat( txt, content );

						}

					}

					delete ele[ '#text' ];

					if ( ele.attributes.type === 'Int64' ) {

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} else {

					if ( ele.attributes.format === 'binary' && ! compressed ) {

						content = Base64toByteArray( ele[ '#text' ] );

						//  VTP data for the uncompressed case has the following structure:
						// [#bytes][DATA]
						// where "[#bytes]" is an integer value specifying the number of bytes in the block of data following it.
						content = content.slice( numBytes ).buffer;

					} else {

						if ( ele[ '#text' ] ) {

							content = ele[ '#text' ].split( /\s+/ ).filter( function ( el ) {

								if ( el !== '' ) return el;

							} );

						} else {

							content = new Int32Array( 0 ).buffer;

						}

					}

					delete ele[ '#text' ];

					// Get the content and optimize it
					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( content );

					} else if ( ele.attributes.type === 'Int32' ) {

						txt = new Int32Array( content );

					} else if ( ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( content );

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} // endif ( ele.attributes.format === 'binary' && compressed )

				return txt;

			}
```
</details>


---

## Classes

### `VTKLoader`

<details><summary>Class Code</summary>

```ts
class VTKLoader extends Loader {

	/**
	 * Constructs a new VTK loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded VRML asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
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
	 * Parses the given VTK data and returns the resulting geometry.
	 *
	 * @param {ArrayBuffer} data - The raw VTK data as an array buffer
	 * @return {BufferGeometry} The parsed geometry.
	 */
	parse( data ) {

		function parseASCII( data ) {

			// connectivity of the triangles
			const indices = [];

			// triangles vertices
			const positions = [];

			// red, green, blue colors in the range 0 to 1
			const colors = [];

			// normal vector, one per vertex
			const normals = [];

			let result;

			// pattern for detecting the end of a number sequence
			const patWord = /^[^\d.\s-]+/;

			// pattern for reading vertices, 3 floats or integers
			const pat3Floats = /(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)/g;

			// pattern for connectivity, an integer followed by any number of ints
			// the first integer is the number of polygon nodes
			const patConnectivity = /^(\d+)\s+([\s\d]*)/;

			// indicates start of vertex data section
			const patPOINTS = /^POINTS /;

			// indicates start of polygon connectivity section
			const patPOLYGONS = /^POLYGONS /;

			// indicates start of triangle strips section
			const patTRIANGLE_STRIPS = /^TRIANGLE_STRIPS /;

			// POINT_DATA number_of_values
			const patPOINT_DATA = /^POINT_DATA[ ]+(\d+)/;

			// CELL_DATA number_of_polys
			const patCELL_DATA = /^CELL_DATA[ ]+(\d+)/;

			// Start of color section
			const patCOLOR_SCALARS = /^COLOR_SCALARS[ ]+(\w+)[ ]+3/;

			// NORMALS Normals float
			const patNORMALS = /^NORMALS[ ]+(\w+)[ ]+(\w+)/;

			let inPointsSection = false;
			let inPolygonsSection = false;
			let inTriangleStripSection = false;
			let inPointDataSection = false;
			let inCellDataSection = false;
			let inColorSection = false;
			let inNormalsSection = false;

			const color = new Color();

			const lines = data.split( '\n' );

			for ( const i in lines ) {

				const line = lines[ i ].trim();

				if ( line.indexOf( 'DATASET' ) === 0 ) {

					const dataset = line.split( ' ' )[ 1 ];

					if ( dataset !== 'POLYDATA' ) throw new Error( 'Unsupported DATASET type: ' + dataset );

				} else if ( inPointsSection ) {

					// get the vertices
					while ( ( result = pat3Floats.exec( line ) ) !== null ) {

						if ( patWord.exec( line ) !== null ) break;

						const x = parseFloat( result[ 1 ] );
						const y = parseFloat( result[ 2 ] );
						const z = parseFloat( result[ 3 ] );
						positions.push( x, y, z );

					}

				} else if ( inPolygonsSection ) {

					if ( ( result = patConnectivity.exec( line ) ) !== null ) {

						// numVertices i0 i1 i2 ...
						const numVertices = parseInt( result[ 1 ] );
						const inds = result[ 2 ].split( /\s+/ );

						if ( numVertices >= 3 ) {

							const i0 = parseInt( inds[ 0 ] );
							let k = 1;
							// split the polygon in numVertices - 2 triangles
							for ( let j = 0; j < numVertices - 2; ++ j ) {

								const i1 = parseInt( inds[ k ] );
								const i2 = parseInt( inds[ k + 1 ] );
								indices.push( i0, i1, i2 );
								k ++;

							}

						}

					}

				} else if ( inTriangleStripSection ) {

					if ( ( result = patConnectivity.exec( line ) ) !== null ) {

						// numVertices i0 i1 i2 ...
						const numVertices = parseInt( result[ 1 ] );
						const inds = result[ 2 ].split( /\s+/ );

						if ( numVertices >= 3 ) {

							// split the polygon in numVertices - 2 triangles
							for ( let j = 0; j < numVertices - 2; j ++ ) {

								if ( j % 2 === 1 ) {

									const i0 = parseInt( inds[ j ] );
									const i1 = parseInt( inds[ j + 2 ] );
									const i2 = parseInt( inds[ j + 1 ] );
									indices.push( i0, i1, i2 );

								} else {

									const i0 = parseInt( inds[ j ] );
									const i1 = parseInt( inds[ j + 1 ] );
									const i2 = parseInt( inds[ j + 2 ] );
									indices.push( i0, i1, i2 );

								}

							}

						}

					}

				} else if ( inPointDataSection || inCellDataSection ) {

					if ( inColorSection ) {

						// Get the colors

						while ( ( result = pat3Floats.exec( line ) ) !== null ) {

							if ( patWord.exec( line ) !== null ) break;

							const r = parseFloat( result[ 1 ] );
							const g = parseFloat( result[ 2 ] );
							const b = parseFloat( result[ 3 ] );

							color.setRGB( r, g, b, SRGBColorSpace );

							colors.push( color.r, color.g, color.b );

						}

					} else if ( inNormalsSection ) {

						// Get the normal vectors

						while ( ( result = pat3Floats.exec( line ) ) !== null ) {

							if ( patWord.exec( line ) !== null ) break;

							const nx = parseFloat( result[ 1 ] );
							const ny = parseFloat( result[ 2 ] );
							const nz = parseFloat( result[ 3 ] );
							normals.push( nx, ny, nz );

						}

					}

				}

				if ( patPOLYGONS.exec( line ) !== null ) {

					inPolygonsSection = true;
					inPointsSection = false;
					inTriangleStripSection = false;

				} else if ( patPOINTS.exec( line ) !== null ) {

					inPolygonsSection = false;
					inPointsSection = true;
					inTriangleStripSection = false;

				} else if ( patTRIANGLE_STRIPS.exec( line ) !== null ) {

					inPolygonsSection = false;
					inPointsSection = false;
					inTriangleStripSection = true;

				} else if ( patPOINT_DATA.exec( line ) !== null ) {

					inPointDataSection = true;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patCELL_DATA.exec( line ) !== null ) {

					inCellDataSection = true;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patCOLOR_SCALARS.exec( line ) !== null ) {

					inColorSection = true;
					inNormalsSection = false;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patNORMALS.exec( line ) !== null ) {

					inNormalsSection = true;
					inColorSection = false;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				}

			}

			let geometry = new BufferGeometry();
			geometry.setIndex( indices );
			geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );

			if ( normals.length === positions.length ) {

				geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

			}

			if ( colors.length !== indices.length ) {

				// stagger

				if ( colors.length === positions.length ) {

					geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

				}

			} else {

				// cell

				geometry = geometry.toNonIndexed();
				const numTriangles = geometry.attributes.position.count / 3;

				if ( colors.length === ( numTriangles * 3 ) ) {

					const newColors = [];

					for ( let i = 0; i < numTriangles; i ++ ) {

						const r = colors[ 3 * i + 0 ];
						const g = colors[ 3 * i + 1 ];
						const b = colors[ 3 * i + 2 ];

						color.setRGB( r, g, b, SRGBColorSpace );

						newColors.push( color.r, color.g, color.b );
						newColors.push( color.r, color.g, color.b );
						newColors.push( color.r, color.g, color.b );

					}

					geometry.setAttribute( 'color', new Float32BufferAttribute( newColors, 3 ) );

				}

			}

			return geometry;

		}

		function parseBinary( data ) {

			const buffer = new Uint8Array( data );
			const dataView = new DataView( data );

			// Points and normals, by default, are empty
			let points = [];
			let normals = [];
			let indices = [];

			let index = 0;

			function findString( buffer, start ) {

				let index = start;
				let c = buffer[ index ];
				const s = [];
				while ( c !== 10 ) {

					s.push( String.fromCharCode( c ) );
					index ++;
					c = buffer[ index ];

				}

				return { start: start,
					end: index,
					next: index + 1,
					parsedString: s.join( '' ) };

			}

			let state, line;

			while ( true ) {

				// Get a string
				state = findString( buffer, index );
				line = state.parsedString;

				if ( line.indexOf( 'DATASET' ) === 0 ) {

					const dataset = line.split( ' ' )[ 1 ];

					if ( dataset !== 'POLYDATA' ) throw new Error( 'Unsupported DATASET type: ' + dataset );

				} else if ( line.indexOf( 'POINTS' ) === 0 ) {

					// Add the points
					const numberOfPoints = parseInt( line.split( ' ' )[ 1 ], 10 );

					// Each point is 3 4-byte floats
					const count = numberOfPoints * 4 * 3;

					points = new Float32Array( numberOfPoints * 3 );

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfPoints; i ++ ) {

						points[ 3 * i ] = dataView.getFloat32( pointIndex, false );
						points[ 3 * i + 1 ] = dataView.getFloat32( pointIndex + 4, false );
						points[ 3 * i + 2 ] = dataView.getFloat32( pointIndex + 8, false );
						pointIndex = pointIndex + 12;

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'TRIANGLE_STRIPS' ) === 0 ) {

					const numberOfStrips = parseInt( line.split( ' ' )[ 1 ], 10 );
					const size = parseInt( line.split( ' ' )[ 2 ], 10 );
					// 4 byte integers
					const count = size * 4;

					indices = new Uint32Array( 3 * size - 9 * numberOfStrips );
					let indicesIndex = 0;

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfStrips; i ++ ) {

						// For each strip, read the first value, then record that many more points
						const indexCount = dataView.getInt32( pointIndex, false );
						const strip = [];
						pointIndex += 4;
						for ( let s = 0; s < indexCount; s ++ ) {

							strip.push( dataView.getInt32( pointIndex, false ) );
							pointIndex += 4;

						}

						// retrieves the n-2 triangles from the triangle strip
						for ( let j = 0; j < indexCount - 2; j ++ ) {

							if ( j % 2 ) {

								indices[ indicesIndex ++ ] = strip[ j ];
								indices[ indicesIndex ++ ] = strip[ j + 2 ];
								indices[ indicesIndex ++ ] = strip[ j + 1 ];

							} else {

								indices[ indicesIndex ++ ] = strip[ j ];
								indices[ indicesIndex ++ ] = strip[ j + 1 ];
								indices[ indicesIndex ++ ] = strip[ j + 2 ];

							}

						}

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'POLYGONS' ) === 0 ) {

					const numberOfStrips = parseInt( line.split( ' ' )[ 1 ], 10 );
					const size = parseInt( line.split( ' ' )[ 2 ], 10 );
					// 4 byte integers
					const count = size * 4;

					indices = new Uint32Array( 3 * size - 9 * numberOfStrips );
					let indicesIndex = 0;

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfStrips; i ++ ) {

						// For each strip, read the first value, then record that many more points
						const indexCount = dataView.getInt32( pointIndex, false );
						const strip = [];
						pointIndex += 4;
						for ( let s = 0; s < indexCount; s ++ ) {

							strip.push( dataView.getInt32( pointIndex, false ) );
							pointIndex += 4;

						}

						// divide the polygon in n-2 triangle
						for ( let j = 1; j < indexCount - 1; j ++ ) {

							indices[ indicesIndex ++ ] = strip[ 0 ];
							indices[ indicesIndex ++ ] = strip[ j ];
							indices[ indicesIndex ++ ] = strip[ j + 1 ];

						}

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'POINT_DATA' ) === 0 ) {

					const numberOfPoints = parseInt( line.split( ' ' )[ 1 ], 10 );

					// Grab the next line
					state = findString( buffer, state.next );

					// Now grab the binary data
					const count = numberOfPoints * 4 * 3;

					normals = new Float32Array( numberOfPoints * 3 );
					let pointIndex = state.next;
					for ( let i = 0; i < numberOfPoints; i ++ ) {

						normals[ 3 * i ] = dataView.getFloat32( pointIndex, false );
						normals[ 3 * i + 1 ] = dataView.getFloat32( pointIndex + 4, false );
						normals[ 3 * i + 2 ] = dataView.getFloat32( pointIndex + 8, false );
						pointIndex += 12;

					}

					// Increment past our data
					state.next = state.next + count;

				}

				// Increment index
				index = state.next;

				if ( index >= buffer.byteLength ) {

					break;

				}

			}

			const geometry = new BufferGeometry();
			geometry.setIndex( new BufferAttribute( indices, 1 ) );
			geometry.setAttribute( 'position', new BufferAttribute( points, 3 ) );

			if ( normals.length === points.length ) {

				geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

			}

			return geometry;

		}

		function Float32Concat( first, second ) {

			const firstLength = first.length, result = new Float32Array( firstLength + second.length );

			result.set( first );
			result.set( second, firstLength );

			return result;

		}

		function Int32Concat( first, second ) {

			const firstLength = first.length, result = new Int32Array( firstLength + second.length );

			result.set( first );
			result.set( second, firstLength );

			return result;

		}

		function parseXML( stringFile ) {

			// Changes XML to JSON, based on https://davidwalsh.name/convert-xml-json

			function xmlToJson( xml ) {

				// Create the return object
				let obj = {};

				if ( xml.nodeType === 1 ) { // element

					// do attributes

					if ( xml.attributes ) {

						if ( xml.attributes.length > 0 ) {

							obj[ 'attributes' ] = {};

							for ( let j = 0; j < xml.attributes.length; j ++ ) {

								const attribute = xml.attributes.item( j );
								obj[ 'attributes' ][ attribute.nodeName ] = attribute.nodeValue.trim();

							}

						}

					}

				} else if ( xml.nodeType === 3 ) { // text

					obj = xml.nodeValue.trim();

				}

				// do children
				if ( xml.hasChildNodes() ) {

					for ( let i = 0; i < xml.childNodes.length; i ++ ) {

						const item = xml.childNodes.item( i );
						const nodeName = item.nodeName;

						if ( typeof obj[ nodeName ] === 'undefined' ) {

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ] = tmp;

							}

						} else {

							if ( typeof obj[ nodeName ].push === 'undefined' ) {

								const old = obj[ nodeName ];
								obj[ nodeName ] = [ old ];

							}

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ].push( tmp );

							}

						}

					}

				}

				return obj;

			}

			// Taken from Base64-js
			function Base64toByteArray( b64 ) {

				const Arr = typeof Uint8Array !== 'undefined' ? Uint8Array : Array;
				const revLookup = [];
				const code = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/';

				for ( let i = 0, l = code.length; i < l; ++ i ) {

					revLookup[ code.charCodeAt( i ) ] = i;

				}

				revLookup[ '-'.charCodeAt( 0 ) ] = 62;
				revLookup[ '_'.charCodeAt( 0 ) ] = 63;

				const len = b64.length;

				if ( len % 4 > 0 ) {

					throw new Error( 'Invalid string. Length must be a multiple of 4' );

				}

				const placeHolders = b64[ len - 2 ] === '=' ? 2 : b64[ len - 1 ] === '=' ? 1 : 0;
				const arr = new Arr( len * 3 / 4 - placeHolders );
				const l = placeHolders > 0 ? len - 4 : len;

				let L = 0;
				let i, j;

				for ( i = 0, j = 0; i < l; i += 4, j += 3 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 18 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 12 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] << 6 ) | revLookup[ b64.charCodeAt( i + 3 ) ];
					arr[ L ++ ] = ( tmp & 0xFF0000 ) >> 16;
					arr[ L ++ ] = ( tmp & 0xFF00 ) >> 8;
					arr[ L ++ ] = tmp & 0xFF;

				}

				if ( placeHolders === 2 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 2 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] >> 4 );
					arr[ L ++ ] = tmp & 0xFF;

				} else if ( placeHolders === 1 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 10 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 4 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] >> 2 );
					arr[ L ++ ] = ( tmp >> 8 ) & 0xFF;
					arr[ L ++ ] = tmp & 0xFF;

				}

				return arr;

			}

			function parseDataArray( ele, compressed ) {

				let numBytes = 0;

				if ( json.attributes.header_type === 'UInt64' ) {

					numBytes = 8;

				}	else if ( json.attributes.header_type === 'UInt32' ) {

					numBytes = 4;

				}

				let txt, content;

				// Check the format
				if ( ele.attributes.format === 'binary' && compressed ) {

					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( );

					} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( );

					}

					// VTP data with the header has the following structure:
					// [#blocks][#u-size][#p-size][#c-size-1][#c-size-2]...[#c-size-#blocks][DATA]
					//
					// Each token is an integer value whose type is specified by "header_type" at the top of the file (UInt32 if no type specified). The token meanings are:
					// [#blocks] = Number of blocks
					// [#u-size] = Block size before compression
					// [#p-size] = Size of last partial block (zero if it not needed)
					// [#c-size-i] = Size in bytes of block i after compression
					//
					// The [DATA] portion stores contiguously every block appended together. The offset from the beginning of the data section to the beginning of a block is
					// computed by summing the compressed block sizes from preceding blocks according to the header.

					const textNode = ele[ '#text' ];
					const rawData = Array.isArray( textNode ) ? textNode[ 0 ] : textNode;

					const byteData = Base64toByteArray( rawData );

					// Each data point consists of 8 bits regardless of the header type
					const dataPointSize = 8;

					let blocks = byteData[ 0 ];
					for ( let i = 1; i < numBytes - 1; i ++ ) {

						blocks = blocks | ( byteData[ i ] << ( i * dataPointSize ) );

					}

					let headerSize = ( blocks + 3 ) * numBytes;
					const padding = ( ( headerSize % 3 ) > 0 ) ? 3 - ( headerSize % 3 ) : 0;
					headerSize = headerSize + padding;

					const dataOffsets = [];
					let currentOffset = headerSize;
					dataOffsets.push( currentOffset );

					// Get the blocks sizes after the compression.
					// There are three blocks before c-size-i, so we skip 3*numBytes
					const cSizeStart = 3 * numBytes;

					for ( let i = 0; i < blocks; i ++ ) {

						let currentBlockSize = byteData[ i * numBytes + cSizeStart ];

						for ( let j = 1; j < numBytes - 1; j ++ ) {

							currentBlockSize = currentBlockSize | ( byteData[ i * numBytes + cSizeStart + j ] << ( j * dataPointSize ) );

						}

						currentOffset = currentOffset + currentBlockSize;
						dataOffsets.push( currentOffset );

					}

					for ( let i = 0; i < dataOffsets.length - 1; i ++ ) {

						const data = fflate.unzlibSync( byteData.slice( dataOffsets[ i ], dataOffsets[ i + 1 ] ) );
						content = data.buffer;

						if ( ele.attributes.type === 'Float32' ) {

							content = new Float32Array( content );
							txt = Float32Concat( txt, content );

						} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

							content = new Int32Array( content );
							txt = Int32Concat( txt, content );

						}

					}

					delete ele[ '#text' ];

					if ( ele.attributes.type === 'Int64' ) {

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} else {

					if ( ele.attributes.format === 'binary' && ! compressed ) {

						content = Base64toByteArray( ele[ '#text' ] );

						//  VTP data for the uncompressed case has the following structure:
						// [#bytes][DATA]
						// where "[#bytes]" is an integer value specifying the number of bytes in the block of data following it.
						content = content.slice( numBytes ).buffer;

					} else {

						if ( ele[ '#text' ] ) {

							content = ele[ '#text' ].split( /\s+/ ).filter( function ( el ) {

								if ( el !== '' ) return el;

							} );

						} else {

							content = new Int32Array( 0 ).buffer;

						}

					}

					delete ele[ '#text' ];

					// Get the content and optimize it
					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( content );

					} else if ( ele.attributes.type === 'Int32' ) {

						txt = new Int32Array( content );

					} else if ( ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( content );

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} // endif ( ele.attributes.format === 'binary' && compressed )

				return txt;

			}

			// Main part
			// Get Dom
			const dom = new DOMParser().parseFromString( stringFile, 'application/xml' );

			// Get the doc
			const doc = dom.documentElement;
			// Convert to json
			const json = xmlToJson( doc );
			let points = [];
			let normals = [];
			let indices = [];

			if ( json.AppendedData ) {

				const appendedData = json.AppendedData[ '#text' ].slice( 1 );
				const piece = json.PolyData.Piece;

				const sections = [ 'PointData', 'CellData', 'Points', 'Verts', 'Lines', 'Strips', 'Polys' ];
				let sectionIndex = 0;

				const offsets = sections.map( s => {

					const sect = piece[ s ];

					if ( sect && sect.DataArray ) {

						const arr = Array.isArray( sect.DataArray ) ? sect.DataArray : [ sect.DataArray ];

						return arr.map( a => a.attributes.offset );

					}

					return [];

				} ).flat();

				for ( const sect of sections ) {

					const section = piece[ sect ];

					if ( section && section.DataArray ) {

						if ( Array.isArray( section.DataArray ) ) {

							for ( const sectionEle of section.DataArray ) {

								sectionEle[ '#text' ] = appendedData.slice( offsets[ sectionIndex ], offsets[ sectionIndex + 1 ] );
								sectionEle.attributes.format = 'binary';
								sectionIndex ++;

							}

						} else {

							section.DataArray[ '#text' ] = appendedData.slice( offsets[ sectionIndex ], offsets[ sectionIndex + 1 ] );
							section.DataArray.attributes.format = 'binary';
							sectionIndex ++;

						}

					}

				}

			}

			if ( json.PolyData ) {

				const piece = json.PolyData.Piece;
				const compressed = json.attributes.hasOwnProperty( 'compressor' );

				// Can be optimized
				// Loop through the sections
				const sections = [ 'PointData', 'Points', 'Strips', 'Polys' ];// +['CellData', 'Verts', 'Lines'];
				let sectionIndex = 0;
				const numberOfSections = sections.length;

				while ( sectionIndex < numberOfSections ) {

					const section = piece[ sections[ sectionIndex ] ];

					// If it has a DataArray in it

					if ( section && section.DataArray ) {

						// Depending on the number of DataArrays

						let arr;

						if ( Array.isArray( section.DataArray ) ) {

							arr = section.DataArray;

						} else {

							arr = [ section.DataArray ];

						}

						let dataArrayIndex = 0;
						const numberOfDataArrays = arr.length;

						while ( dataArrayIndex < numberOfDataArrays ) {

							// Parse the DataArray
							if ( ( '#text' in arr[ dataArrayIndex ] ) && ( arr[ dataArrayIndex ][ '#text' ].length > 0 ) ) {

								arr[ dataArrayIndex ].text = parseDataArray( arr[ dataArrayIndex ], compressed );

							}

							dataArrayIndex ++;

						}

						switch ( sections[ sectionIndex ] ) {

							// if iti is point data
							case 'PointData':

								{

									const numberOfPoints = parseInt( piece.attributes.NumberOfPoints );
									const normalsName = section.attributes.Normals;

									if ( numberOfPoints > 0 ) {

										for ( let i = 0, len = arr.length; i < len; i ++ ) {

											if ( normalsName === arr[ i ].attributes.Name ) {

												const components = arr[ i ].attributes.NumberOfComponents;
												normals = new Float32Array( numberOfPoints * components );
												normals.set( arr[ i ].text, 0 );

											}

										}

									}

								}

								break;

							// if it is points
							case 'Points':

								{

									const numberOfPoints = parseInt( piece.attributes.NumberOfPoints );

									if ( numberOfPoints > 0 ) {

										const components = section.DataArray.attributes.NumberOfComponents;
										points = new Float32Array( numberOfPoints * components );
										points.set( section.DataArray.text, 0 );

									}

								}

								break;

							// if it is strips
							case 'Strips':

								{

									const numberOfStrips = parseInt( piece.attributes.NumberOfStrips );

									if ( numberOfStrips > 0 ) {

										const connectivity = new Int32Array( section.DataArray[ 0 ].text.length );
										const offset = new Int32Array( section.DataArray[ 1 ].text.length );
										connectivity.set( section.DataArray[ 0 ].text, 0 );
										offset.set( section.DataArray[ 1 ].text, 0 );

										const size = numberOfStrips + connectivity.length;
										indices = new Uint32Array( 3 * size - 9 * numberOfStrips );

										let indicesIndex = 0;

										for ( let i = 0, len = numberOfStrips; i < len; i ++ ) {

											const strip = [];

											for ( let s = 0, len1 = offset[ i ], len0 = 0; s < len1 - len0; s ++ ) {

												strip.push( connectivity[ s ] );

												if ( i > 0 ) len0 = offset[ i - 1 ];

											}

											for ( let j = 0, len1 = offset[ i ], len0 = 0; j < len1 - len0 - 2; j ++ ) {

												if ( j % 2 ) {

													indices[ indicesIndex ++ ] = strip[ j ];
													indices[ indicesIndex ++ ] = strip[ j + 2 ];
													indices[ indicesIndex ++ ] = strip[ j + 1 ];

												} else {

													indices[ indicesIndex ++ ] = strip[ j ];
													indices[ indicesIndex ++ ] = strip[ j + 1 ];
													indices[ indicesIndex ++ ] = strip[ j + 2 ];

												}

												if ( i > 0 ) len0 = offset[ i - 1 ];

											}

										}

									}

								}

								break;

							// if it is polys
							case 'Polys':

								{

									const numberOfPolys = parseInt( piece.attributes.NumberOfPolys );

									if ( numberOfPolys > 0 ) {

										const connectivity = new Int32Array( section.DataArray[ 0 ].text.length );
										const offset = new Int32Array( section.DataArray[ 1 ].text.length );
										connectivity.set( section.DataArray[ 0 ].text, 0 );
										offset.set( section.DataArray[ 1 ].text, 0 );

										const size = numberOfPolys + connectivity.length;
										indices = new Uint32Array( 3 * size - 9 * numberOfPolys );
										let indicesIndex = 0, connectivityIndex = 0;
										let i = 0, len0 = 0;
										const len = numberOfPolys;

										while ( i < len ) {

											const poly = [];
											let s = 0;
											const len1 = offset[ i ];

											while ( s < len1 - len0 ) {

												poly.push( connectivity[ connectivityIndex ++ ] );
												s ++;

											}

											let j = 1;

											while ( j < len1 - len0 - 1 ) {

												indices[ indicesIndex ++ ] = poly[ 0 ];
												indices[ indicesIndex ++ ] = poly[ j ];
												indices[ indicesIndex ++ ] = poly[ j + 1 ];
												j ++;

											}

											i ++;
											len0 = offset[ i - 1 ];

										}

									}

								}

								break;

							default:
								break;

						}

					}

					sectionIndex ++;

				}

				const geometry = new BufferGeometry();
				geometry.setIndex( new BufferAttribute( indices, 1 ) );
				geometry.setAttribute( 'position', new BufferAttribute( points, 3 ) );

				if ( normals.length === points.length ) {

					geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

				}

				return geometry;

			} else {

				throw new Error( 'Unsupported DATASET type' );

			}

		}

		const textDecoder = new TextDecoder();

		// get the 5 first lines of the files to check if there is the key word binary
		const meta = textDecoder.decode( new Uint8Array( data, 0, 250 ) ).split( '\n' );

		if ( meta[ 0 ].indexOf( 'xml' ) !== - 1 ) {

			return parseXML( textDecoder.decode( data ) );

		} else if ( meta[ 2 ].includes( 'ASCII' ) ) {

			return parseASCII( textDecoder.decode( data ) );

		} else {

			return parseBinary( data );

		}

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

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
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

##### `parse(data: ArrayBuffer): BufferGeometry`

<details><summary>Code</summary>

```ts
parse( data ) {

		function parseASCII( data ) {

			// connectivity of the triangles
			const indices = [];

			// triangles vertices
			const positions = [];

			// red, green, blue colors in the range 0 to 1
			const colors = [];

			// normal vector, one per vertex
			const normals = [];

			let result;

			// pattern for detecting the end of a number sequence
			const patWord = /^[^\d.\s-]+/;

			// pattern for reading vertices, 3 floats or integers
			const pat3Floats = /(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)\s+(\-?\d+\.?[\d\-\+e]*)/g;

			// pattern for connectivity, an integer followed by any number of ints
			// the first integer is the number of polygon nodes
			const patConnectivity = /^(\d+)\s+([\s\d]*)/;

			// indicates start of vertex data section
			const patPOINTS = /^POINTS /;

			// indicates start of polygon connectivity section
			const patPOLYGONS = /^POLYGONS /;

			// indicates start of triangle strips section
			const patTRIANGLE_STRIPS = /^TRIANGLE_STRIPS /;

			// POINT_DATA number_of_values
			const patPOINT_DATA = /^POINT_DATA[ ]+(\d+)/;

			// CELL_DATA number_of_polys
			const patCELL_DATA = /^CELL_DATA[ ]+(\d+)/;

			// Start of color section
			const patCOLOR_SCALARS = /^COLOR_SCALARS[ ]+(\w+)[ ]+3/;

			// NORMALS Normals float
			const patNORMALS = /^NORMALS[ ]+(\w+)[ ]+(\w+)/;

			let inPointsSection = false;
			let inPolygonsSection = false;
			let inTriangleStripSection = false;
			let inPointDataSection = false;
			let inCellDataSection = false;
			let inColorSection = false;
			let inNormalsSection = false;

			const color = new Color();

			const lines = data.split( '\n' );

			for ( const i in lines ) {

				const line = lines[ i ].trim();

				if ( line.indexOf( 'DATASET' ) === 0 ) {

					const dataset = line.split( ' ' )[ 1 ];

					if ( dataset !== 'POLYDATA' ) throw new Error( 'Unsupported DATASET type: ' + dataset );

				} else if ( inPointsSection ) {

					// get the vertices
					while ( ( result = pat3Floats.exec( line ) ) !== null ) {

						if ( patWord.exec( line ) !== null ) break;

						const x = parseFloat( result[ 1 ] );
						const y = parseFloat( result[ 2 ] );
						const z = parseFloat( result[ 3 ] );
						positions.push( x, y, z );

					}

				} else if ( inPolygonsSection ) {

					if ( ( result = patConnectivity.exec( line ) ) !== null ) {

						// numVertices i0 i1 i2 ...
						const numVertices = parseInt( result[ 1 ] );
						const inds = result[ 2 ].split( /\s+/ );

						if ( numVertices >= 3 ) {

							const i0 = parseInt( inds[ 0 ] );
							let k = 1;
							// split the polygon in numVertices - 2 triangles
							for ( let j = 0; j < numVertices - 2; ++ j ) {

								const i1 = parseInt( inds[ k ] );
								const i2 = parseInt( inds[ k + 1 ] );
								indices.push( i0, i1, i2 );
								k ++;

							}

						}

					}

				} else if ( inTriangleStripSection ) {

					if ( ( result = patConnectivity.exec( line ) ) !== null ) {

						// numVertices i0 i1 i2 ...
						const numVertices = parseInt( result[ 1 ] );
						const inds = result[ 2 ].split( /\s+/ );

						if ( numVertices >= 3 ) {

							// split the polygon in numVertices - 2 triangles
							for ( let j = 0; j < numVertices - 2; j ++ ) {

								if ( j % 2 === 1 ) {

									const i0 = parseInt( inds[ j ] );
									const i1 = parseInt( inds[ j + 2 ] );
									const i2 = parseInt( inds[ j + 1 ] );
									indices.push( i0, i1, i2 );

								} else {

									const i0 = parseInt( inds[ j ] );
									const i1 = parseInt( inds[ j + 1 ] );
									const i2 = parseInt( inds[ j + 2 ] );
									indices.push( i0, i1, i2 );

								}

							}

						}

					}

				} else if ( inPointDataSection || inCellDataSection ) {

					if ( inColorSection ) {

						// Get the colors

						while ( ( result = pat3Floats.exec( line ) ) !== null ) {

							if ( patWord.exec( line ) !== null ) break;

							const r = parseFloat( result[ 1 ] );
							const g = parseFloat( result[ 2 ] );
							const b = parseFloat( result[ 3 ] );

							color.setRGB( r, g, b, SRGBColorSpace );

							colors.push( color.r, color.g, color.b );

						}

					} else if ( inNormalsSection ) {

						// Get the normal vectors

						while ( ( result = pat3Floats.exec( line ) ) !== null ) {

							if ( patWord.exec( line ) !== null ) break;

							const nx = parseFloat( result[ 1 ] );
							const ny = parseFloat( result[ 2 ] );
							const nz = parseFloat( result[ 3 ] );
							normals.push( nx, ny, nz );

						}

					}

				}

				if ( patPOLYGONS.exec( line ) !== null ) {

					inPolygonsSection = true;
					inPointsSection = false;
					inTriangleStripSection = false;

				} else if ( patPOINTS.exec( line ) !== null ) {

					inPolygonsSection = false;
					inPointsSection = true;
					inTriangleStripSection = false;

				} else if ( patTRIANGLE_STRIPS.exec( line ) !== null ) {

					inPolygonsSection = false;
					inPointsSection = false;
					inTriangleStripSection = true;

				} else if ( patPOINT_DATA.exec( line ) !== null ) {

					inPointDataSection = true;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patCELL_DATA.exec( line ) !== null ) {

					inCellDataSection = true;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patCOLOR_SCALARS.exec( line ) !== null ) {

					inColorSection = true;
					inNormalsSection = false;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				} else if ( patNORMALS.exec( line ) !== null ) {

					inNormalsSection = true;
					inColorSection = false;
					inPointsSection = false;
					inPolygonsSection = false;
					inTriangleStripSection = false;

				}

			}

			let geometry = new BufferGeometry();
			geometry.setIndex( indices );
			geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );

			if ( normals.length === positions.length ) {

				geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

			}

			if ( colors.length !== indices.length ) {

				// stagger

				if ( colors.length === positions.length ) {

					geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

				}

			} else {

				// cell

				geometry = geometry.toNonIndexed();
				const numTriangles = geometry.attributes.position.count / 3;

				if ( colors.length === ( numTriangles * 3 ) ) {

					const newColors = [];

					for ( let i = 0; i < numTriangles; i ++ ) {

						const r = colors[ 3 * i + 0 ];
						const g = colors[ 3 * i + 1 ];
						const b = colors[ 3 * i + 2 ];

						color.setRGB( r, g, b, SRGBColorSpace );

						newColors.push( color.r, color.g, color.b );
						newColors.push( color.r, color.g, color.b );
						newColors.push( color.r, color.g, color.b );

					}

					geometry.setAttribute( 'color', new Float32BufferAttribute( newColors, 3 ) );

				}

			}

			return geometry;

		}

		function parseBinary( data ) {

			const buffer = new Uint8Array( data );
			const dataView = new DataView( data );

			// Points and normals, by default, are empty
			let points = [];
			let normals = [];
			let indices = [];

			let index = 0;

			function findString( buffer, start ) {

				let index = start;
				let c = buffer[ index ];
				const s = [];
				while ( c !== 10 ) {

					s.push( String.fromCharCode( c ) );
					index ++;
					c = buffer[ index ];

				}

				return { start: start,
					end: index,
					next: index + 1,
					parsedString: s.join( '' ) };

			}

			let state, line;

			while ( true ) {

				// Get a string
				state = findString( buffer, index );
				line = state.parsedString;

				if ( line.indexOf( 'DATASET' ) === 0 ) {

					const dataset = line.split( ' ' )[ 1 ];

					if ( dataset !== 'POLYDATA' ) throw new Error( 'Unsupported DATASET type: ' + dataset );

				} else if ( line.indexOf( 'POINTS' ) === 0 ) {

					// Add the points
					const numberOfPoints = parseInt( line.split( ' ' )[ 1 ], 10 );

					// Each point is 3 4-byte floats
					const count = numberOfPoints * 4 * 3;

					points = new Float32Array( numberOfPoints * 3 );

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfPoints; i ++ ) {

						points[ 3 * i ] = dataView.getFloat32( pointIndex, false );
						points[ 3 * i + 1 ] = dataView.getFloat32( pointIndex + 4, false );
						points[ 3 * i + 2 ] = dataView.getFloat32( pointIndex + 8, false );
						pointIndex = pointIndex + 12;

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'TRIANGLE_STRIPS' ) === 0 ) {

					const numberOfStrips = parseInt( line.split( ' ' )[ 1 ], 10 );
					const size = parseInt( line.split( ' ' )[ 2 ], 10 );
					// 4 byte integers
					const count = size * 4;

					indices = new Uint32Array( 3 * size - 9 * numberOfStrips );
					let indicesIndex = 0;

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfStrips; i ++ ) {

						// For each strip, read the first value, then record that many more points
						const indexCount = dataView.getInt32( pointIndex, false );
						const strip = [];
						pointIndex += 4;
						for ( let s = 0; s < indexCount; s ++ ) {

							strip.push( dataView.getInt32( pointIndex, false ) );
							pointIndex += 4;

						}

						// retrieves the n-2 triangles from the triangle strip
						for ( let j = 0; j < indexCount - 2; j ++ ) {

							if ( j % 2 ) {

								indices[ indicesIndex ++ ] = strip[ j ];
								indices[ indicesIndex ++ ] = strip[ j + 2 ];
								indices[ indicesIndex ++ ] = strip[ j + 1 ];

							} else {

								indices[ indicesIndex ++ ] = strip[ j ];
								indices[ indicesIndex ++ ] = strip[ j + 1 ];
								indices[ indicesIndex ++ ] = strip[ j + 2 ];

							}

						}

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'POLYGONS' ) === 0 ) {

					const numberOfStrips = parseInt( line.split( ' ' )[ 1 ], 10 );
					const size = parseInt( line.split( ' ' )[ 2 ], 10 );
					// 4 byte integers
					const count = size * 4;

					indices = new Uint32Array( 3 * size - 9 * numberOfStrips );
					let indicesIndex = 0;

					let pointIndex = state.next;
					for ( let i = 0; i < numberOfStrips; i ++ ) {

						// For each strip, read the first value, then record that many more points
						const indexCount = dataView.getInt32( pointIndex, false );
						const strip = [];
						pointIndex += 4;
						for ( let s = 0; s < indexCount; s ++ ) {

							strip.push( dataView.getInt32( pointIndex, false ) );
							pointIndex += 4;

						}

						// divide the polygon in n-2 triangle
						for ( let j = 1; j < indexCount - 1; j ++ ) {

							indices[ indicesIndex ++ ] = strip[ 0 ];
							indices[ indicesIndex ++ ] = strip[ j ];
							indices[ indicesIndex ++ ] = strip[ j + 1 ];

						}

					}

					// increment our next pointer
					state.next = state.next + count + 1;

				} else if ( line.indexOf( 'POINT_DATA' ) === 0 ) {

					const numberOfPoints = parseInt( line.split( ' ' )[ 1 ], 10 );

					// Grab the next line
					state = findString( buffer, state.next );

					// Now grab the binary data
					const count = numberOfPoints * 4 * 3;

					normals = new Float32Array( numberOfPoints * 3 );
					let pointIndex = state.next;
					for ( let i = 0; i < numberOfPoints; i ++ ) {

						normals[ 3 * i ] = dataView.getFloat32( pointIndex, false );
						normals[ 3 * i + 1 ] = dataView.getFloat32( pointIndex + 4, false );
						normals[ 3 * i + 2 ] = dataView.getFloat32( pointIndex + 8, false );
						pointIndex += 12;

					}

					// Increment past our data
					state.next = state.next + count;

				}

				// Increment index
				index = state.next;

				if ( index >= buffer.byteLength ) {

					break;

				}

			}

			const geometry = new BufferGeometry();
			geometry.setIndex( new BufferAttribute( indices, 1 ) );
			geometry.setAttribute( 'position', new BufferAttribute( points, 3 ) );

			if ( normals.length === points.length ) {

				geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

			}

			return geometry;

		}

		function Float32Concat( first, second ) {

			const firstLength = first.length, result = new Float32Array( firstLength + second.length );

			result.set( first );
			result.set( second, firstLength );

			return result;

		}

		function Int32Concat( first, second ) {

			const firstLength = first.length, result = new Int32Array( firstLength + second.length );

			result.set( first );
			result.set( second, firstLength );

			return result;

		}

		function parseXML( stringFile ) {

			// Changes XML to JSON, based on https://davidwalsh.name/convert-xml-json

			function xmlToJson( xml ) {

				// Create the return object
				let obj = {};

				if ( xml.nodeType === 1 ) { // element

					// do attributes

					if ( xml.attributes ) {

						if ( xml.attributes.length > 0 ) {

							obj[ 'attributes' ] = {};

							for ( let j = 0; j < xml.attributes.length; j ++ ) {

								const attribute = xml.attributes.item( j );
								obj[ 'attributes' ][ attribute.nodeName ] = attribute.nodeValue.trim();

							}

						}

					}

				} else if ( xml.nodeType === 3 ) { // text

					obj = xml.nodeValue.trim();

				}

				// do children
				if ( xml.hasChildNodes() ) {

					for ( let i = 0; i < xml.childNodes.length; i ++ ) {

						const item = xml.childNodes.item( i );
						const nodeName = item.nodeName;

						if ( typeof obj[ nodeName ] === 'undefined' ) {

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ] = tmp;

							}

						} else {

							if ( typeof obj[ nodeName ].push === 'undefined' ) {

								const old = obj[ nodeName ];
								obj[ nodeName ] = [ old ];

							}

							const tmp = xmlToJson( item );

							if ( tmp !== '' ) {

								if ( Array.isArray( tmp[ '#text' ] ) ) {

									tmp[ '#text' ] = tmp[ '#text' ][ 0 ];

								}

								obj[ nodeName ].push( tmp );

							}

						}

					}

				}

				return obj;

			}

			// Taken from Base64-js
			function Base64toByteArray( b64 ) {

				const Arr = typeof Uint8Array !== 'undefined' ? Uint8Array : Array;
				const revLookup = [];
				const code = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/';

				for ( let i = 0, l = code.length; i < l; ++ i ) {

					revLookup[ code.charCodeAt( i ) ] = i;

				}

				revLookup[ '-'.charCodeAt( 0 ) ] = 62;
				revLookup[ '_'.charCodeAt( 0 ) ] = 63;

				const len = b64.length;

				if ( len % 4 > 0 ) {

					throw new Error( 'Invalid string. Length must be a multiple of 4' );

				}

				const placeHolders = b64[ len - 2 ] === '=' ? 2 : b64[ len - 1 ] === '=' ? 1 : 0;
				const arr = new Arr( len * 3 / 4 - placeHolders );
				const l = placeHolders > 0 ? len - 4 : len;

				let L = 0;
				let i, j;

				for ( i = 0, j = 0; i < l; i += 4, j += 3 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 18 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 12 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] << 6 ) | revLookup[ b64.charCodeAt( i + 3 ) ];
					arr[ L ++ ] = ( tmp & 0xFF0000 ) >> 16;
					arr[ L ++ ] = ( tmp & 0xFF00 ) >> 8;
					arr[ L ++ ] = tmp & 0xFF;

				}

				if ( placeHolders === 2 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 2 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] >> 4 );
					arr[ L ++ ] = tmp & 0xFF;

				} else if ( placeHolders === 1 ) {

					const tmp = ( revLookup[ b64.charCodeAt( i ) ] << 10 ) | ( revLookup[ b64.charCodeAt( i + 1 ) ] << 4 ) | ( revLookup[ b64.charCodeAt( i + 2 ) ] >> 2 );
					arr[ L ++ ] = ( tmp >> 8 ) & 0xFF;
					arr[ L ++ ] = tmp & 0xFF;

				}

				return arr;

			}

			function parseDataArray( ele, compressed ) {

				let numBytes = 0;

				if ( json.attributes.header_type === 'UInt64' ) {

					numBytes = 8;

				}	else if ( json.attributes.header_type === 'UInt32' ) {

					numBytes = 4;

				}

				let txt, content;

				// Check the format
				if ( ele.attributes.format === 'binary' && compressed ) {

					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( );

					} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( );

					}

					// VTP data with the header has the following structure:
					// [#blocks][#u-size][#p-size][#c-size-1][#c-size-2]...[#c-size-#blocks][DATA]
					//
					// Each token is an integer value whose type is specified by "header_type" at the top of the file (UInt32 if no type specified). The token meanings are:
					// [#blocks] = Number of blocks
					// [#u-size] = Block size before compression
					// [#p-size] = Size of last partial block (zero if it not needed)
					// [#c-size-i] = Size in bytes of block i after compression
					//
					// The [DATA] portion stores contiguously every block appended together. The offset from the beginning of the data section to the beginning of a block is
					// computed by summing the compressed block sizes from preceding blocks according to the header.

					const textNode = ele[ '#text' ];
					const rawData = Array.isArray( textNode ) ? textNode[ 0 ] : textNode;

					const byteData = Base64toByteArray( rawData );

					// Each data point consists of 8 bits regardless of the header type
					const dataPointSize = 8;

					let blocks = byteData[ 0 ];
					for ( let i = 1; i < numBytes - 1; i ++ ) {

						blocks = blocks | ( byteData[ i ] << ( i * dataPointSize ) );

					}

					let headerSize = ( blocks + 3 ) * numBytes;
					const padding = ( ( headerSize % 3 ) > 0 ) ? 3 - ( headerSize % 3 ) : 0;
					headerSize = headerSize + padding;

					const dataOffsets = [];
					let currentOffset = headerSize;
					dataOffsets.push( currentOffset );

					// Get the blocks sizes after the compression.
					// There are three blocks before c-size-i, so we skip 3*numBytes
					const cSizeStart = 3 * numBytes;

					for ( let i = 0; i < blocks; i ++ ) {

						let currentBlockSize = byteData[ i * numBytes + cSizeStart ];

						for ( let j = 1; j < numBytes - 1; j ++ ) {

							currentBlockSize = currentBlockSize | ( byteData[ i * numBytes + cSizeStart + j ] << ( j * dataPointSize ) );

						}

						currentOffset = currentOffset + currentBlockSize;
						dataOffsets.push( currentOffset );

					}

					for ( let i = 0; i < dataOffsets.length - 1; i ++ ) {

						const data = fflate.unzlibSync( byteData.slice( dataOffsets[ i ], dataOffsets[ i + 1 ] ) );
						content = data.buffer;

						if ( ele.attributes.type === 'Float32' ) {

							content = new Float32Array( content );
							txt = Float32Concat( txt, content );

						} else if ( ele.attributes.type === 'Int32' || ele.attributes.type === 'Int64' ) {

							content = new Int32Array( content );
							txt = Int32Concat( txt, content );

						}

					}

					delete ele[ '#text' ];

					if ( ele.attributes.type === 'Int64' ) {

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} else {

					if ( ele.attributes.format === 'binary' && ! compressed ) {

						content = Base64toByteArray( ele[ '#text' ] );

						//  VTP data for the uncompressed case has the following structure:
						// [#bytes][DATA]
						// where "[#bytes]" is an integer value specifying the number of bytes in the block of data following it.
						content = content.slice( numBytes ).buffer;

					} else {

						if ( ele[ '#text' ] ) {

							content = ele[ '#text' ].split( /\s+/ ).filter( function ( el ) {

								if ( el !== '' ) return el;

							} );

						} else {

							content = new Int32Array( 0 ).buffer;

						}

					}

					delete ele[ '#text' ];

					// Get the content and optimize it
					if ( ele.attributes.type === 'Float32' ) {

						txt = new Float32Array( content );

					} else if ( ele.attributes.type === 'Int32' ) {

						txt = new Int32Array( content );

					} else if ( ele.attributes.type === 'Int64' ) {

						txt = new Int32Array( content );

						if ( ele.attributes.format === 'binary' ) {

							txt = txt.filter( function ( el, idx ) {

								if ( idx % 2 !== 1 ) return true;

							} );

						}

					}

				} // endif ( ele.attributes.format === 'binary' && compressed )

				return txt;

			}

			// Main part
			// Get Dom
			const dom = new DOMParser().parseFromString( stringFile, 'application/xml' );

			// Get the doc
			const doc = dom.documentElement;
			// Convert to json
			const json = xmlToJson( doc );
			let points = [];
			let normals = [];
			let indices = [];

			if ( json.AppendedData ) {

				const appendedData = json.AppendedData[ '#text' ].slice( 1 );
				const piece = json.PolyData.Piece;

				const sections = [ 'PointData', 'CellData', 'Points', 'Verts', 'Lines', 'Strips', 'Polys' ];
				let sectionIndex = 0;

				const offsets = sections.map( s => {

					const sect = piece[ s ];

					if ( sect && sect.DataArray ) {

						const arr = Array.isArray( sect.DataArray ) ? sect.DataArray : [ sect.DataArray ];

						return arr.map( a => a.attributes.offset );

					}

					return [];

				} ).flat();

				for ( const sect of sections ) {

					const section = piece[ sect ];

					if ( section && section.DataArray ) {

						if ( Array.isArray( section.DataArray ) ) {

							for ( const sectionEle of section.DataArray ) {

								sectionEle[ '#text' ] = appendedData.slice( offsets[ sectionIndex ], offsets[ sectionIndex + 1 ] );
								sectionEle.attributes.format = 'binary';
								sectionIndex ++;

							}

						} else {

							section.DataArray[ '#text' ] = appendedData.slice( offsets[ sectionIndex ], offsets[ sectionIndex + 1 ] );
							section.DataArray.attributes.format = 'binary';
							sectionIndex ++;

						}

					}

				}

			}

			if ( json.PolyData ) {

				const piece = json.PolyData.Piece;
				const compressed = json.attributes.hasOwnProperty( 'compressor' );

				// Can be optimized
				// Loop through the sections
				const sections = [ 'PointData', 'Points', 'Strips', 'Polys' ];// +['CellData', 'Verts', 'Lines'];
				let sectionIndex = 0;
				const numberOfSections = sections.length;

				while ( sectionIndex < numberOfSections ) {

					const section = piece[ sections[ sectionIndex ] ];

					// If it has a DataArray in it

					if ( section && section.DataArray ) {

						// Depending on the number of DataArrays

						let arr;

						if ( Array.isArray( section.DataArray ) ) {

							arr = section.DataArray;

						} else {

							arr = [ section.DataArray ];

						}

						let dataArrayIndex = 0;
						const numberOfDataArrays = arr.length;

						while ( dataArrayIndex < numberOfDataArrays ) {

							// Parse the DataArray
							if ( ( '#text' in arr[ dataArrayIndex ] ) && ( arr[ dataArrayIndex ][ '#text' ].length > 0 ) ) {

								arr[ dataArrayIndex ].text = parseDataArray( arr[ dataArrayIndex ], compressed );

							}

							dataArrayIndex ++;

						}

						switch ( sections[ sectionIndex ] ) {

							// if iti is point data
							case 'PointData':

								{

									const numberOfPoints = parseInt( piece.attributes.NumberOfPoints );
									const normalsName = section.attributes.Normals;

									if ( numberOfPoints > 0 ) {

										for ( let i = 0, len = arr.length; i < len; i ++ ) {

											if ( normalsName === arr[ i ].attributes.Name ) {

												const components = arr[ i ].attributes.NumberOfComponents;
												normals = new Float32Array( numberOfPoints * components );
												normals.set( arr[ i ].text, 0 );

											}

										}

									}

								}

								break;

							// if it is points
							case 'Points':

								{

									const numberOfPoints = parseInt( piece.attributes.NumberOfPoints );

									if ( numberOfPoints > 0 ) {

										const components = section.DataArray.attributes.NumberOfComponents;
										points = new Float32Array( numberOfPoints * components );
										points.set( section.DataArray.text, 0 );

									}

								}

								break;

							// if it is strips
							case 'Strips':

								{

									const numberOfStrips = parseInt( piece.attributes.NumberOfStrips );

									if ( numberOfStrips > 0 ) {

										const connectivity = new Int32Array( section.DataArray[ 0 ].text.length );
										const offset = new Int32Array( section.DataArray[ 1 ].text.length );
										connectivity.set( section.DataArray[ 0 ].text, 0 );
										offset.set( section.DataArray[ 1 ].text, 0 );

										const size = numberOfStrips + connectivity.length;
										indices = new Uint32Array( 3 * size - 9 * numberOfStrips );

										let indicesIndex = 0;

										for ( let i = 0, len = numberOfStrips; i < len; i ++ ) {

											const strip = [];

											for ( let s = 0, len1 = offset[ i ], len0 = 0; s < len1 - len0; s ++ ) {

												strip.push( connectivity[ s ] );

												if ( i > 0 ) len0 = offset[ i - 1 ];

											}

											for ( let j = 0, len1 = offset[ i ], len0 = 0; j < len1 - len0 - 2; j ++ ) {

												if ( j % 2 ) {

													indices[ indicesIndex ++ ] = strip[ j ];
													indices[ indicesIndex ++ ] = strip[ j + 2 ];
													indices[ indicesIndex ++ ] = strip[ j + 1 ];

												} else {

													indices[ indicesIndex ++ ] = strip[ j ];
													indices[ indicesIndex ++ ] = strip[ j + 1 ];
													indices[ indicesIndex ++ ] = strip[ j + 2 ];

												}

												if ( i > 0 ) len0 = offset[ i - 1 ];

											}

										}

									}

								}

								break;

							// if it is polys
							case 'Polys':

								{

									const numberOfPolys = parseInt( piece.attributes.NumberOfPolys );

									if ( numberOfPolys > 0 ) {

										const connectivity = new Int32Array( section.DataArray[ 0 ].text.length );
										const offset = new Int32Array( section.DataArray[ 1 ].text.length );
										connectivity.set( section.DataArray[ 0 ].text, 0 );
										offset.set( section.DataArray[ 1 ].text, 0 );

										const size = numberOfPolys + connectivity.length;
										indices = new Uint32Array( 3 * size - 9 * numberOfPolys );
										let indicesIndex = 0, connectivityIndex = 0;
										let i = 0, len0 = 0;
										const len = numberOfPolys;

										while ( i < len ) {

											const poly = [];
											let s = 0;
											const len1 = offset[ i ];

											while ( s < len1 - len0 ) {

												poly.push( connectivity[ connectivityIndex ++ ] );
												s ++;

											}

											let j = 1;

											while ( j < len1 - len0 - 1 ) {

												indices[ indicesIndex ++ ] = poly[ 0 ];
												indices[ indicesIndex ++ ] = poly[ j ];
												indices[ indicesIndex ++ ] = poly[ j + 1 ];
												j ++;

											}

											i ++;
											len0 = offset[ i - 1 ];

										}

									}

								}

								break;

							default:
								break;

						}

					}

					sectionIndex ++;

				}

				const geometry = new BufferGeometry();
				geometry.setIndex( new BufferAttribute( indices, 1 ) );
				geometry.setAttribute( 'position', new BufferAttribute( points, 3 ) );

				if ( normals.length === points.length ) {

					geometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

				}

				return geometry;

			} else {

				throw new Error( 'Unsupported DATASET type' );

			}

		}

		const textDecoder = new TextDecoder();

		// get the 5 first lines of the files to check if there is the key word binary
		const meta = textDecoder.decode( new Uint8Array( data, 0, 250 ) ).split( '\n' );

		if ( meta[ 0 ].indexOf( 'xml' ) !== - 1 ) {

			return parseXML( textDecoder.decode( data ) );

		} else if ( meta[ 2 ].includes( 'ASCII' ) ) {

			return parseASCII( textDecoder.decode( data ) );

		} else {

			return parseBinary( data );

		}

	}
```
</details>


---