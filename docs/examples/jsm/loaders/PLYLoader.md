[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PLYLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 37 |
| 🧱 Classes | 2 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 41 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/PLYLoader.js`**

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
| `_color` | `any` | let/var | `new Color()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `patternHeader` | `RegExp` | let/var | `/^ply([\s\S]*)end_header(\r\n\|\r\|\n)/` | ✗ |
| `headerText` | `string` | let/var | `''` | ✗ |
| `header` | `{ comments: any[]; elements: any[]; h...` | let/var | `{ comments: [], elements: [], headerLength: headerLength, objInfo: '' }` | ✗ |
| `currentElement` | `any` | let/var | `*not shown*` | ✗ |
| `property` | `{ type: any; }` | let/var | `{ type: propertyValues[ 0 ] }` | ✗ |
| `line` | `string` | let/var | `lines[ i ]` | ✗ |
| `element` | `{}` | let/var | `{}` | ✗ |
| `list` | `any[]` | let/var | `[]` | ✗ |
| `buffer` | `{ indices: any[]; vertices: any[]; no...` | let/var | `{ indices: [], vertices: [], normals: [], uvs: [], faceVertexUvs: [], colors:...` | ✗ |
| `name` | `any` | let/var | `names[ i ]` | ✗ |
| `patternBody` | `RegExp` | let/var | `/end_header\s+(\S[\s\S]*\S\|\S)\s*$/` | ✗ |
| `body` | `any` | let/var | `*not shown*` | ✗ |
| `matches` | `any` | let/var | `*not shown*` | ✗ |
| `tokens` | `ArrayStream` | let/var | `new ArrayStream( body )` | ✗ |
| `elementDesc` | `any` | let/var | `header.elements[ i ]` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `vertex_indices` | `any` | let/var | `element.vertex_indices \|\| element.vertex_index` | ✗ |
| `texcoord` | `any` | let/var | `element.texcoord` | ✗ |
| `element` | `{}` | let/var | `{}` | ✗ |
| `read` | `number` | let/var | `0` | ✗ |
| `property` | `any` | let/var | `properties[ i ]` | ✗ |
| `valueReader` | `any` | let/var | `property.valueReader` | ✗ |
| `list` | `any[]` | let/var | `[]` | ✗ |
| `property` | `any` | let/var | `properties[ i ]` | ✗ |
| `little_endian` | `boolean` | let/var | `( header.format === 'binary_little_endian' )` | ✗ |
| `body` | `DataView<any>` | let/var | `new DataView( data, header.headerLength )` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `loc` | `number` | let/var | `0` | ✗ |
| `elementDesc` | `any` | let/var | `header.elements[ currentElement ]` | ✗ |
| `properties` | `any` | let/var | `elementDesc.properties` | ✗ |
| `element` | `{}` | let/var | `result[ 0 ]` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `cont` | `boolean` | let/var | `true` | ✗ |
| `line` | `string` | let/var | `''` | ✗ |
| `lines` | `any[]` | let/var | `[]` | ✗ |
| `geometry` | `any` | let/var | `*not shown*` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `bytes` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( data )` | ✗ |


---

## Functions

### `PLYLoader.load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded PLY asset
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

### `PLYLoader.setPropertyNameMapping(mapping: any): void`

**JSDoc:**
```typescript
/**
	 * Sets a property name mapping that maps default property names
	 * to custom ones. For example, the following maps the properties
	 * “diffuse_(red|green|blue)” in the file to standard color names.
	 *
	 * ```js
	 * loader.setPropertyNameMapping( {
	 * 	diffuse_red: 'red',
	 * 	diffuse_green: 'green',
	 * 	diffuse_blue: 'blue'
	 * } );
	 * ```
	 *
	 * @param {Object} mapping - The mapping dictionary.
	 */
```

**Parameters:**

- **`mapping`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setPropertyNameMapping( mapping ) {

		this.propertyNameMapping = mapping;

	}
```
</details>

### `PLYLoader.setCustomPropertyNameMapping(mapping: any): void`

**JSDoc:**
```typescript
/**
	 * Custom properties outside of the defaults for position, uv, normal
	 * and color attributes can be added using the setCustomPropertyNameMapping method.
	 * For example, the following maps the element properties “custom_property_a”
	 * and “custom_property_b” to an attribute “customAttribute” with an item size of 2.
	 * Attribute item sizes are set from the number of element properties in the property array.
	 *
	 * ```js
	 * loader.setCustomPropertyNameMapping( {
	 *	customAttribute: ['custom_property_a', 'custom_property_b'],
	 * } );
	 * ```
	 * @param {Object} mapping - The mapping dictionary.
	 */
```

**Parameters:**

- **`mapping`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setCustomPropertyNameMapping( mapping ) {

		this.customPropertyMapping = mapping;

	}
```
</details>

### `PLYLoader.parse(data: ArrayBuffer): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Parses the given PLY data and returns the resulting geometry.
	 *
	 * @param {ArrayBuffer} data - The raw PLY data as an array buffer.
	 * @return {BufferGeometry} The parsed geometry.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`

**Returns:** `BufferGeometry`

**Calls:**

- `patternHeader.exec`
- `headerText.split`
- `line.trim`
- `line.split`
- `lineValues.shift`
- `lineValues.join`
- `header.comments.push`
- `header.elements.push`
- `parseInt`
- `currentElement.properties.push`
- `make_ply_element_property`
- `console.log`
- `parseFloat`
- `tokens.empty`
- `parseASCIINumber`
- `tokens.next`
- `list.push`
- `Object.keys`
- `properties.map`
- `elementNames.includes`
- `findAttrName`
- `createBuffer`
- `patternBody.exec`
- `matches[ 1 ].split`
- `mapElementAttributes`
- `parseASCIIElement`
- `handleElement`
- `postProcess`
- `geometry.setIndex`
- `geometry.setAttribute`
- `geometry.toNonIndexed`
- `geometry.computeBoundingSphere`
- `buffer.vertices.push`
- `buffer.normals.push`
- `buffer.uvs.push`
- `_color.setRGB`
- `buffer.colors.push`
- `buffer[ customProperty ].push`
- `buffer.indices.push`
- `buffer.faceVertexUvs.push`
- `buffer.faceVertexColors.push`
- `property.countReader.read`
- `valueReader.read`
- `dataview.getInt8`
- `dataview.getUint8`
- `dataview.getInt16`
- `dataview.getUint16`
- `dataview.getInt32`
- `dataview.getUint32`
- `dataview.getFloat32`
- `dataview.getFloat64`
- `getBinaryReader`
- `setPropertyBinaryReaders`
- `binaryReadElement`
- `new TextDecoder().decode`
- `bytes.subarray`
- `/^ply\r\n/.test`
- `String.fromCharCode`
- `lines.push`
- `lines.join`
- `extractHeaderText`
- `parseHeader`
- `parseASCII`
- `parseBinary`

**Internal Comments:**
```
// PLY ascii format specification, as per http://en.wikipedia.org/wiki/PLY_(file_format) (x2)
// mandatory buffer data
// optional buffer data
// custom buffer data
// face colors
// correspondences for non-specific length types here match rply:
// ascii section using \r\n as line endings
// (x2)
```

<details><summary>Code</summary>

```typescript
parse( data ) {

		function parseHeader( data, headerLength = 0 ) {

			const patternHeader = /^ply([\s\S]*)end_header(\r\n|\r|\n)/;
			let headerText = '';
			const result = patternHeader.exec( data );

			if ( result !== null ) {

				headerText = result[ 1 ];

			}

			const header = {
				comments: [],
				elements: [],
				headerLength: headerLength,
				objInfo: ''
			};

			const lines = headerText.split( /\r\n|\r|\n/ );
			let currentElement;

			function make_ply_element_property( propertyValues, propertyNameMapping ) {

				const property = { type: propertyValues[ 0 ] };

				if ( property.type === 'list' ) {

					property.name = propertyValues[ 3 ];
					property.countType = propertyValues[ 1 ];
					property.itemType = propertyValues[ 2 ];

				} else {

					property.name = propertyValues[ 1 ];

				}

				if ( property.name in propertyNameMapping ) {

					property.name = propertyNameMapping[ property.name ];

				}

				return property;

			}

			for ( let i = 0; i < lines.length; i ++ ) {

				let line = lines[ i ];
				line = line.trim();

				if ( line === '' ) continue;

				const lineValues = line.split( /\s+/ );
				const lineType = lineValues.shift();
				line = lineValues.join( ' ' );

				switch ( lineType ) {

					case 'format':

						header.format = lineValues[ 0 ];
						header.version = lineValues[ 1 ];

						break;

					case 'comment':

						header.comments.push( line );

						break;

					case 'element':

						if ( currentElement !== undefined ) {

							header.elements.push( currentElement );

						}

						currentElement = {};
						currentElement.name = lineValues[ 0 ];
						currentElement.count = parseInt( lineValues[ 1 ] );
						currentElement.properties = [];

						break;

					case 'property':

						currentElement.properties.push( make_ply_element_property( lineValues, scope.propertyNameMapping ) );

						break;

					case 'obj_info':

						header.objInfo = line;

						break;


					default:

						console.log( 'unhandled', lineType, lineValues );

				}

			}

			if ( currentElement !== undefined ) {

				header.elements.push( currentElement );

			}

			return header;

		}

		function parseASCIINumber( n, type ) {

			switch ( type ) {

				case 'char': case 'uchar': case 'short': case 'ushort': case 'int': case 'uint':
				case 'int8': case 'uint8': case 'int16': case 'uint16': case 'int32': case 'uint32':

					return parseInt( n );

				case 'float': case 'double': case 'float32': case 'float64':

					return parseFloat( n );

			}

		}

		function parseASCIIElement( properties, tokens ) {

			const element = {};

			for ( let i = 0; i < properties.length; i ++ ) {

				if ( tokens.empty() ) return null;

				if ( properties[ i ].type === 'list' ) {

					const list = [];
					const n = parseASCIINumber( tokens.next(), properties[ i ].countType );

					for ( let j = 0; j < n; j ++ ) {

						if ( tokens.empty() ) return null;

						list.push( parseASCIINumber( tokens.next(), properties[ i ].itemType ) );

					}

					element[ properties[ i ].name ] = list;

				} else {

					element[ properties[ i ].name ] = parseASCIINumber( tokens.next(), properties[ i ].type );

				}

			}

			return element;

		}

		function createBuffer() {

			const buffer = {
			  indices: [],
			  vertices: [],
			  normals: [],
			  uvs: [],
			  faceVertexUvs: [],
			  colors: [],
			  faceVertexColors: []
			};

			for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

			  buffer[ customProperty ] = [];

			}

			return buffer;

		}

		function mapElementAttributes( properties ) {

			const elementNames = properties.map( property => {

				return property.name;

			} );

			function findAttrName( names ) {

				for ( let i = 0, l = names.length; i < l; i ++ ) {

					const name = names[ i ];

					if ( elementNames.includes( name ) ) return name;

				}

				return null;

			}

			return {
				attrX: findAttrName( [ 'x', 'px', 'posx' ] ) || 'x',
				attrY: findAttrName( [ 'y', 'py', 'posy' ] ) || 'y',
				attrZ: findAttrName( [ 'z', 'pz', 'posz' ] ) || 'z',
				attrNX: findAttrName( [ 'nx', 'normalx' ] ),
				attrNY: findAttrName( [ 'ny', 'normaly' ] ),
				attrNZ: findAttrName( [ 'nz', 'normalz' ] ),
				attrS: findAttrName( [ 's', 'u', 'texture_u', 'tx' ] ),
				attrT: findAttrName( [ 't', 'v', 'texture_v', 'ty' ] ),
				attrR: findAttrName( [ 'red', 'diffuse_red', 'r', 'diffuse_r' ] ),
				attrG: findAttrName( [ 'green', 'diffuse_green', 'g', 'diffuse_g' ] ),
				attrB: findAttrName( [ 'blue', 'diffuse_blue', 'b', 'diffuse_b' ] ),
			};

		}

		function parseASCII( data, header ) {

			// PLY ascii format specification, as per http://en.wikipedia.org/wiki/PLY_(file_format)

			const buffer = createBuffer();

			const patternBody = /end_header\s+(\S[\s\S]*\S|\S)\s*$/;
			let body, matches;

			if ( ( matches = patternBody.exec( data ) ) !== null ) {

				body = matches[ 1 ].split( /\s+/ );

			} else {

				body = [ ];

			}

			const tokens = new ArrayStream( body );

			loop: for ( let i = 0; i < header.elements.length; i ++ ) {

				const elementDesc = header.elements[ i ];
				const attributeMap = mapElementAttributes( elementDesc.properties );

				for ( let j = 0; j < elementDesc.count; j ++ ) {

					const element = parseASCIIElement( elementDesc.properties, tokens );

					if ( ! element ) break loop;

					handleElement( buffer, elementDesc.name, element, attributeMap );

				}

			}

			return postProcess( buffer );

		}

		function postProcess( buffer ) {

			let geometry = new BufferGeometry();

			// mandatory buffer data

			if ( buffer.indices.length > 0 ) {

				geometry.setIndex( buffer.indices );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( buffer.vertices, 3 ) );

			// optional buffer data

			if ( buffer.normals.length > 0 ) {

				geometry.setAttribute( 'normal', new Float32BufferAttribute( buffer.normals, 3 ) );

			}

			if ( buffer.uvs.length > 0 ) {

				geometry.setAttribute( 'uv', new Float32BufferAttribute( buffer.uvs, 2 ) );

			}

			if ( buffer.colors.length > 0 ) {

				geometry.setAttribute( 'color', new Float32BufferAttribute( buffer.colors, 3 ) );

			}

			if ( buffer.faceVertexUvs.length > 0 || buffer.faceVertexColors.length > 0 ) {

				geometry = geometry.toNonIndexed();

				if ( buffer.faceVertexUvs.length > 0 ) geometry.setAttribute( 'uv', new Float32BufferAttribute( buffer.faceVertexUvs, 2 ) );
				if ( buffer.faceVertexColors.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( buffer.faceVertexColors, 3 ) );

			}

			// custom buffer data

			for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

				if ( buffer[ customProperty ].length > 0 ) {

				  	geometry.setAttribute(
						customProperty,
						new Float32BufferAttribute(
					  		buffer[ customProperty ],
					  		scope.customPropertyMapping[ customProperty ].length
						)
				  	);

				}

			}

			geometry.computeBoundingSphere();

			return geometry;

		}

		function handleElement( buffer, elementName, element, cacheEntry ) {

			if ( elementName === 'vertex' ) {

				buffer.vertices.push( element[ cacheEntry.attrX ], element[ cacheEntry.attrY ], element[ cacheEntry.attrZ ] );

				if ( cacheEntry.attrNX !== null && cacheEntry.attrNY !== null && cacheEntry.attrNZ !== null ) {

					buffer.normals.push( element[ cacheEntry.attrNX ], element[ cacheEntry.attrNY ], element[ cacheEntry.attrNZ ] );

				}

				if ( cacheEntry.attrS !== null && cacheEntry.attrT !== null ) {

					buffer.uvs.push( element[ cacheEntry.attrS ], element[ cacheEntry.attrT ] );

				}

				if ( cacheEntry.attrR !== null && cacheEntry.attrG !== null && cacheEntry.attrB !== null ) {

					_color.setRGB(
						element[ cacheEntry.attrR ] / 255.0,
						element[ cacheEntry.attrG ] / 255.0,
						element[ cacheEntry.attrB ] / 255.0,
						SRGBColorSpace
					);

					buffer.colors.push( _color.r, _color.g, _color.b );

				}

				for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

					for ( const elementProperty of scope.customPropertyMapping[ customProperty ] ) {

					  buffer[ customProperty ].push( element[ elementProperty ] );

					}

				}

			} else if ( elementName === 'face' ) {

				const vertex_indices = element.vertex_indices || element.vertex_index; // issue #9338
				const texcoord = element.texcoord;

				if ( vertex_indices.length === 3 ) {

					buffer.indices.push( vertex_indices[ 0 ], vertex_indices[ 1 ], vertex_indices[ 2 ] );

					if ( texcoord && texcoord.length === 6 ) {

						buffer.faceVertexUvs.push( texcoord[ 0 ], texcoord[ 1 ] );
						buffer.faceVertexUvs.push( texcoord[ 2 ], texcoord[ 3 ] );
						buffer.faceVertexUvs.push( texcoord[ 4 ], texcoord[ 5 ] );

					}

				} else if ( vertex_indices.length === 4 ) {

					buffer.indices.push( vertex_indices[ 0 ], vertex_indices[ 1 ], vertex_indices[ 3 ] );
					buffer.indices.push( vertex_indices[ 1 ], vertex_indices[ 2 ], vertex_indices[ 3 ] );

				}

				// face colors

				if ( cacheEntry.attrR !== null && cacheEntry.attrG !== null && cacheEntry.attrB !== null ) {

					_color.setRGB(
						element[ cacheEntry.attrR ] / 255.0,
						element[ cacheEntry.attrG ] / 255.0,
						element[ cacheEntry.attrB ] / 255.0,
						SRGBColorSpace
					);
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );

				}

			}

		}

		function binaryReadElement( at, properties ) {

			const element = {};
			let read = 0;

			for ( let i = 0; i < properties.length; i ++ ) {

				const property = properties[ i ];
				const valueReader = property.valueReader;

				if ( property.type === 'list' ) {

					const list = [];

					const n = property.countReader.read( at + read );
					read += property.countReader.size;

					for ( let j = 0; j < n; j ++ ) {

						list.push( valueReader.read( at + read ) );
						read += valueReader.size;

					}

					element[ property.name ] = list;

				} else {

					element[ property.name ] = valueReader.read( at + read );
					read += valueReader.size;

				}

			}

			return [ element, read ];

		}

		function setPropertyBinaryReaders( properties, body, little_endian ) {

			function getBinaryReader( dataview, type, little_endian ) {

				switch ( type ) {

					// correspondences for non-specific length types here match rply:
					case 'int8':	case 'char':	return { read: ( at ) => {

						return dataview.getInt8( at );

					}, size: 1 };
					case 'uint8':	case 'uchar':	return { read: ( at ) => {

						return dataview.getUint8( at );

					}, size: 1 };
					case 'int16':	case 'short':	return { read: ( at ) => {

						return dataview.getInt16( at, little_endian );

					}, size: 2 };
					case 'uint16':	case 'ushort':	return { read: ( at ) => {

						return dataview.getUint16( at, little_endian );

					}, size: 2 };
					case 'int32':	case 'int':		return { read: ( at ) => {

						return dataview.getInt32( at, little_endian );

					}, size: 4 };
					case 'uint32':	case 'uint':	return { read: ( at ) => {

						return dataview.getUint32( at, little_endian );

					}, size: 4 };
					case 'float32': case 'float':	return { read: ( at ) => {

						return dataview.getFloat32( at, little_endian );

					}, size: 4 };
					case 'float64': case 'double':	return { read: ( at ) => {

						return dataview.getFloat64( at, little_endian );

					}, size: 8 };

				}

			}

			for ( let i = 0, l = properties.length; i < l; i ++ ) {

				const property = properties[ i ];

				if ( property.type === 'list' ) {

					property.countReader = getBinaryReader( body, property.countType, little_endian );
					property.valueReader = getBinaryReader( body, property.itemType, little_endian );

				} else {

					property.valueReader = getBinaryReader( body, property.type, little_endian );

				}

			}

		}

		function parseBinary( data, header ) {

			const buffer = createBuffer();

			const little_endian = ( header.format === 'binary_little_endian' );
			const body = new DataView( data, header.headerLength );
			let result, loc = 0;

			for ( let currentElement = 0; currentElement < header.elements.length; currentElement ++ ) {

				const elementDesc = header.elements[ currentElement ];
				const properties = elementDesc.properties;
				const attributeMap = mapElementAttributes( properties );

				setPropertyBinaryReaders( properties, body, little_endian );

				for ( let currentElementCount = 0; currentElementCount < elementDesc.count; currentElementCount ++ ) {

					result = binaryReadElement( loc, properties );
					loc += result[ 1 ];
					const element = result[ 0 ];

					handleElement( buffer, elementDesc.name, element, attributeMap );

				}

			}

			return postProcess( buffer );

		}

		function extractHeaderText( bytes ) {

			let i = 0;
			let cont = true;

			let line = '';
			const lines = [];

			const startLine = new TextDecoder().decode( bytes.subarray( 0, 5 ) );
			const hasCRNL = /^ply\r\n/.test( startLine );

			do {

				const c = String.fromCharCode( bytes[ i ++ ] );

				if ( c !== '\n' && c !== '\r' ) {

					line += c;

				} else {

					if ( line === 'end_header' ) cont = false;
					if ( line !== '' ) {

						lines.push( line );
						line = '';

					}

				}

			} while ( cont && i < bytes.length );

			// ascii section using \r\n as line endings
			if ( hasCRNL === true ) i ++;

			return { headerText: lines.join( '\r' ) + '\r', headerLength: i };

		}

		//

		let geometry;
		const scope = this;

		if ( data instanceof ArrayBuffer ) {

			const bytes = new Uint8Array( data );
			const { headerText, headerLength } = extractHeaderText( bytes );
			const header = parseHeader( headerText, headerLength );

			if ( header.format === 'ascii' ) {

				const text = new TextDecoder().decode( bytes );

				geometry = parseASCII( text, header );

			} else {

				geometry = parseBinary( data, header );

			}

		} else {

			geometry = parseASCII( data, parseHeader( data ) );

		}

		return geometry;

	}
```
</details>

### `parseHeader(data: any, headerLength: number): { comments: any[]; elements: any[]; headerLength: number; objInfo: string; }`

**Parameters:**

- **`data`** `any`
- **`headerLength`** `number`

**Returns:** `{ comments: any[]; elements: any[]; headerLength: number; objInfo: string; }`

**Calls:**

- `patternHeader.exec`
- `headerText.split`
- `line.trim`
- `line.split`
- `lineValues.shift`
- `lineValues.join`
- `header.comments.push`
- `header.elements.push`
- `parseInt`
- `currentElement.properties.push`
- `make_ply_element_property`
- `console.log`

<details><summary>Code</summary>

```typescript
function parseHeader( data, headerLength = 0 ) {

			const patternHeader = /^ply([\s\S]*)end_header(\r\n|\r|\n)/;
			let headerText = '';
			const result = patternHeader.exec( data );

			if ( result !== null ) {

				headerText = result[ 1 ];

			}

			const header = {
				comments: [],
				elements: [],
				headerLength: headerLength,
				objInfo: ''
			};

			const lines = headerText.split( /\r\n|\r|\n/ );
			let currentElement;

			function make_ply_element_property( propertyValues, propertyNameMapping ) {

				const property = { type: propertyValues[ 0 ] };

				if ( property.type === 'list' ) {

					property.name = propertyValues[ 3 ];
					property.countType = propertyValues[ 1 ];
					property.itemType = propertyValues[ 2 ];

				} else {

					property.name = propertyValues[ 1 ];

				}

				if ( property.name in propertyNameMapping ) {

					property.name = propertyNameMapping[ property.name ];

				}

				return property;

			}

			for ( let i = 0; i < lines.length; i ++ ) {

				let line = lines[ i ];
				line = line.trim();

				if ( line === '' ) continue;

				const lineValues = line.split( /\s+/ );
				const lineType = lineValues.shift();
				line = lineValues.join( ' ' );

				switch ( lineType ) {

					case 'format':

						header.format = lineValues[ 0 ];
						header.version = lineValues[ 1 ];

						break;

					case 'comment':

						header.comments.push( line );

						break;

					case 'element':

						if ( currentElement !== undefined ) {

							header.elements.push( currentElement );

						}

						currentElement = {};
						currentElement.name = lineValues[ 0 ];
						currentElement.count = parseInt( lineValues[ 1 ] );
						currentElement.properties = [];

						break;

					case 'property':

						currentElement.properties.push( make_ply_element_property( lineValues, scope.propertyNameMapping ) );

						break;

					case 'obj_info':

						header.objInfo = line;

						break;


					default:

						console.log( 'unhandled', lineType, lineValues );

				}

			}

			if ( currentElement !== undefined ) {

				header.elements.push( currentElement );

			}

			return header;

		}
```
</details>

### `make_ply_element_property(propertyValues: any, propertyNameMapping: any): { type: any; }`

**Parameters:**

- **`propertyValues`** `any`
- **`propertyNameMapping`** `any`

**Returns:** `{ type: any; }`

<details><summary>Code</summary>

```typescript
function make_ply_element_property( propertyValues, propertyNameMapping ) {

				const property = { type: propertyValues[ 0 ] };

				if ( property.type === 'list' ) {

					property.name = propertyValues[ 3 ];
					property.countType = propertyValues[ 1 ];
					property.itemType = propertyValues[ 2 ];

				} else {

					property.name = propertyValues[ 1 ];

				}

				if ( property.name in propertyNameMapping ) {

					property.name = propertyNameMapping[ property.name ];

				}

				return property;

			}
```
</details>

### `parseASCIINumber(n: any, type: any): number`

**Parameters:**

- **`n`** `any`
- **`type`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function parseASCIINumber( n, type ) {

			switch ( type ) {

				case 'char': case 'uchar': case 'short': case 'ushort': case 'int': case 'uint':
				case 'int8': case 'uint8': case 'int16': case 'uint16': case 'int32': case 'uint32':

					return parseInt( n );

				case 'float': case 'double': case 'float32': case 'float64':

					return parseFloat( n );

			}

		}
```
</details>

### `parseASCIIElement(properties: any, tokens: any): {}`

**Parameters:**

- **`properties`** `any`
- **`tokens`** `any`

**Returns:** `{}`

**Calls:**

- `tokens.empty`
- `parseASCIINumber`
- `tokens.next`
- `list.push`

<details><summary>Code</summary>

```typescript
function parseASCIIElement( properties, tokens ) {

			const element = {};

			for ( let i = 0; i < properties.length; i ++ ) {

				if ( tokens.empty() ) return null;

				if ( properties[ i ].type === 'list' ) {

					const list = [];
					const n = parseASCIINumber( tokens.next(), properties[ i ].countType );

					for ( let j = 0; j < n; j ++ ) {

						if ( tokens.empty() ) return null;

						list.push( parseASCIINumber( tokens.next(), properties[ i ].itemType ) );

					}

					element[ properties[ i ].name ] = list;

				} else {

					element[ properties[ i ].name ] = parseASCIINumber( tokens.next(), properties[ i ].type );

				}

			}

			return element;

		}
```
</details>

### `createBuffer(): { indices: any[]; vertices: any[]; normals: any[]; uvs: any[]; faceVertexUvs: any[]; colors: any[]; faceVertexColors: any[]; }`

**Returns:** `{ indices: any[]; vertices: any[]; normals: any[]; uvs: any[]; faceVertexUvs: any[]; colors: any[]; faceVertexColors: any[]; }`

**Calls:**

- `Object.keys`

<details><summary>Code</summary>

```typescript
function createBuffer() {

			const buffer = {
			  indices: [],
			  vertices: [],
			  normals: [],
			  uvs: [],
			  faceVertexUvs: [],
			  colors: [],
			  faceVertexColors: []
			};

			for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

			  buffer[ customProperty ] = [];

			}

			return buffer;

		}
```
</details>

### `mapElementAttributes(properties: any): { attrX: any; attrY: any; attrZ: any; attrNX: any; attrNY: any; attrNZ: any; attrS: any; attrT: any; attrR: any; attrG: any; attrB: any; }`

**Parameters:**

- **`properties`** `any`

**Returns:** `{ attrX: any; attrY: any; attrZ: any; attrNX: any; attrNY: any; attrNZ: any; attrS: any; attrT: any; attrR: any; attrG: any; attrB: any; }`

**Calls:**

- `properties.map`
- `elementNames.includes`
- `findAttrName`

<details><summary>Code</summary>

```typescript
function mapElementAttributes( properties ) {

			const elementNames = properties.map( property => {

				return property.name;

			} );

			function findAttrName( names ) {

				for ( let i = 0, l = names.length; i < l; i ++ ) {

					const name = names[ i ];

					if ( elementNames.includes( name ) ) return name;

				}

				return null;

			}

			return {
				attrX: findAttrName( [ 'x', 'px', 'posx' ] ) || 'x',
				attrY: findAttrName( [ 'y', 'py', 'posy' ] ) || 'y',
				attrZ: findAttrName( [ 'z', 'pz', 'posz' ] ) || 'z',
				attrNX: findAttrName( [ 'nx', 'normalx' ] ),
				attrNY: findAttrName( [ 'ny', 'normaly' ] ),
				attrNZ: findAttrName( [ 'nz', 'normalz' ] ),
				attrS: findAttrName( [ 's', 'u', 'texture_u', 'tx' ] ),
				attrT: findAttrName( [ 't', 'v', 'texture_v', 'ty' ] ),
				attrR: findAttrName( [ 'red', 'diffuse_red', 'r', 'diffuse_r' ] ),
				attrG: findAttrName( [ 'green', 'diffuse_green', 'g', 'diffuse_g' ] ),
				attrB: findAttrName( [ 'blue', 'diffuse_blue', 'b', 'diffuse_b' ] ),
			};

		}
```
</details>

### `findAttrName(names: any): any`

**Parameters:**

- **`names`** `any`

**Returns:** `any`

**Calls:**

- `elementNames.includes`

<details><summary>Code</summary>

```typescript
function findAttrName( names ) {

				for ( let i = 0, l = names.length; i < l; i ++ ) {

					const name = names[ i ];

					if ( elementNames.includes( name ) ) return name;

				}

				return null;

			}
```
</details>

### `parseASCII(data: any, header: any): any`

**Parameters:**

- **`data`** `any`
- **`header`** `any`

**Returns:** `any`

**Calls:**

- `createBuffer`
- `patternBody.exec`
- `matches[ 1 ].split`
- `mapElementAttributes`
- `parseASCIIElement`
- `handleElement`
- `postProcess`

**Internal Comments:**
```
// PLY ascii format specification, as per http://en.wikipedia.org/wiki/PLY_(file_format) (x2)
```

<details><summary>Code</summary>

```typescript
function parseASCII( data, header ) {

			// PLY ascii format specification, as per http://en.wikipedia.org/wiki/PLY_(file_format)

			const buffer = createBuffer();

			const patternBody = /end_header\s+(\S[\s\S]*\S|\S)\s*$/;
			let body, matches;

			if ( ( matches = patternBody.exec( data ) ) !== null ) {

				body = matches[ 1 ].split( /\s+/ );

			} else {

				body = [ ];

			}

			const tokens = new ArrayStream( body );

			loop: for ( let i = 0; i < header.elements.length; i ++ ) {

				const elementDesc = header.elements[ i ];
				const attributeMap = mapElementAttributes( elementDesc.properties );

				for ( let j = 0; j < elementDesc.count; j ++ ) {

					const element = parseASCIIElement( elementDesc.properties, tokens );

					if ( ! element ) break loop;

					handleElement( buffer, elementDesc.name, element, attributeMap );

				}

			}

			return postProcess( buffer );

		}
```
</details>

### `postProcess(buffer: any): any`

**Parameters:**

- **`buffer`** `any`

**Returns:** `any`

**Calls:**

- `geometry.setIndex`
- `geometry.setAttribute`
- `geometry.toNonIndexed`
- `Object.keys`
- `geometry.computeBoundingSphere`

**Internal Comments:**
```
// mandatory buffer data
// optional buffer data
// custom buffer data
```

<details><summary>Code</summary>

```typescript
function postProcess( buffer ) {

			let geometry = new BufferGeometry();

			// mandatory buffer data

			if ( buffer.indices.length > 0 ) {

				geometry.setIndex( buffer.indices );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( buffer.vertices, 3 ) );

			// optional buffer data

			if ( buffer.normals.length > 0 ) {

				geometry.setAttribute( 'normal', new Float32BufferAttribute( buffer.normals, 3 ) );

			}

			if ( buffer.uvs.length > 0 ) {

				geometry.setAttribute( 'uv', new Float32BufferAttribute( buffer.uvs, 2 ) );

			}

			if ( buffer.colors.length > 0 ) {

				geometry.setAttribute( 'color', new Float32BufferAttribute( buffer.colors, 3 ) );

			}

			if ( buffer.faceVertexUvs.length > 0 || buffer.faceVertexColors.length > 0 ) {

				geometry = geometry.toNonIndexed();

				if ( buffer.faceVertexUvs.length > 0 ) geometry.setAttribute( 'uv', new Float32BufferAttribute( buffer.faceVertexUvs, 2 ) );
				if ( buffer.faceVertexColors.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( buffer.faceVertexColors, 3 ) );

			}

			// custom buffer data

			for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

				if ( buffer[ customProperty ].length > 0 ) {

				  	geometry.setAttribute(
						customProperty,
						new Float32BufferAttribute(
					  		buffer[ customProperty ],
					  		scope.customPropertyMapping[ customProperty ].length
						)
				  	);

				}

			}

			geometry.computeBoundingSphere();

			return geometry;

		}
```
</details>

### `handleElement(buffer: any, elementName: any, element: any, cacheEntry: any): void`

**Parameters:**

- **`buffer`** `any`
- **`elementName`** `any`
- **`element`** `any`
- **`cacheEntry`** `any`

**Returns:** `void`

**Calls:**

- `buffer.vertices.push`
- `buffer.normals.push`
- `buffer.uvs.push`
- `_color.setRGB`
- `buffer.colors.push`
- `Object.keys`
- `buffer[ customProperty ].push`
- `buffer.indices.push`
- `buffer.faceVertexUvs.push`
- `buffer.faceVertexColors.push`

**Internal Comments:**
```
// face colors
```

<details><summary>Code</summary>

```typescript
function handleElement( buffer, elementName, element, cacheEntry ) {

			if ( elementName === 'vertex' ) {

				buffer.vertices.push( element[ cacheEntry.attrX ], element[ cacheEntry.attrY ], element[ cacheEntry.attrZ ] );

				if ( cacheEntry.attrNX !== null && cacheEntry.attrNY !== null && cacheEntry.attrNZ !== null ) {

					buffer.normals.push( element[ cacheEntry.attrNX ], element[ cacheEntry.attrNY ], element[ cacheEntry.attrNZ ] );

				}

				if ( cacheEntry.attrS !== null && cacheEntry.attrT !== null ) {

					buffer.uvs.push( element[ cacheEntry.attrS ], element[ cacheEntry.attrT ] );

				}

				if ( cacheEntry.attrR !== null && cacheEntry.attrG !== null && cacheEntry.attrB !== null ) {

					_color.setRGB(
						element[ cacheEntry.attrR ] / 255.0,
						element[ cacheEntry.attrG ] / 255.0,
						element[ cacheEntry.attrB ] / 255.0,
						SRGBColorSpace
					);

					buffer.colors.push( _color.r, _color.g, _color.b );

				}

				for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

					for ( const elementProperty of scope.customPropertyMapping[ customProperty ] ) {

					  buffer[ customProperty ].push( element[ elementProperty ] );

					}

				}

			} else if ( elementName === 'face' ) {

				const vertex_indices = element.vertex_indices || element.vertex_index; // issue #9338
				const texcoord = element.texcoord;

				if ( vertex_indices.length === 3 ) {

					buffer.indices.push( vertex_indices[ 0 ], vertex_indices[ 1 ], vertex_indices[ 2 ] );

					if ( texcoord && texcoord.length === 6 ) {

						buffer.faceVertexUvs.push( texcoord[ 0 ], texcoord[ 1 ] );
						buffer.faceVertexUvs.push( texcoord[ 2 ], texcoord[ 3 ] );
						buffer.faceVertexUvs.push( texcoord[ 4 ], texcoord[ 5 ] );

					}

				} else if ( vertex_indices.length === 4 ) {

					buffer.indices.push( vertex_indices[ 0 ], vertex_indices[ 1 ], vertex_indices[ 3 ] );
					buffer.indices.push( vertex_indices[ 1 ], vertex_indices[ 2 ], vertex_indices[ 3 ] );

				}

				// face colors

				if ( cacheEntry.attrR !== null && cacheEntry.attrG !== null && cacheEntry.attrB !== null ) {

					_color.setRGB(
						element[ cacheEntry.attrR ] / 255.0,
						element[ cacheEntry.attrG ] / 255.0,
						element[ cacheEntry.attrB ] / 255.0,
						SRGBColorSpace
					);
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );

				}

			}

		}
```
</details>

### `binaryReadElement(at: any, properties: any): {}[]`

**Parameters:**

- **`at`** `any`
- **`properties`** `any`

**Returns:** `{}[]`

**Calls:**

- `property.countReader.read`
- `list.push`
- `valueReader.read`

<details><summary>Code</summary>

```typescript
function binaryReadElement( at, properties ) {

			const element = {};
			let read = 0;

			for ( let i = 0; i < properties.length; i ++ ) {

				const property = properties[ i ];
				const valueReader = property.valueReader;

				if ( property.type === 'list' ) {

					const list = [];

					const n = property.countReader.read( at + read );
					read += property.countReader.size;

					for ( let j = 0; j < n; j ++ ) {

						list.push( valueReader.read( at + read ) );
						read += valueReader.size;

					}

					element[ property.name ] = list;

				} else {

					element[ property.name ] = valueReader.read( at + read );
					read += valueReader.size;

				}

			}

			return [ element, read ];

		}
```
</details>

### `setPropertyBinaryReaders(properties: any, body: any, little_endian: any): void`

**Parameters:**

- **`properties`** `any`
- **`body`** `any`
- **`little_endian`** `any`

**Returns:** `void`

**Calls:**

- `dataview.getInt8`
- `dataview.getUint8`
- `dataview.getInt16`
- `dataview.getUint16`
- `dataview.getInt32`
- `dataview.getUint32`
- `dataview.getFloat32`
- `dataview.getFloat64`
- `getBinaryReader`

**Internal Comments:**
```
// correspondences for non-specific length types here match rply:
```

<details><summary>Code</summary>

```typescript
function setPropertyBinaryReaders( properties, body, little_endian ) {

			function getBinaryReader( dataview, type, little_endian ) {

				switch ( type ) {

					// correspondences for non-specific length types here match rply:
					case 'int8':	case 'char':	return { read: ( at ) => {

						return dataview.getInt8( at );

					}, size: 1 };
					case 'uint8':	case 'uchar':	return { read: ( at ) => {

						return dataview.getUint8( at );

					}, size: 1 };
					case 'int16':	case 'short':	return { read: ( at ) => {

						return dataview.getInt16( at, little_endian );

					}, size: 2 };
					case 'uint16':	case 'ushort':	return { read: ( at ) => {

						return dataview.getUint16( at, little_endian );

					}, size: 2 };
					case 'int32':	case 'int':		return { read: ( at ) => {

						return dataview.getInt32( at, little_endian );

					}, size: 4 };
					case 'uint32':	case 'uint':	return { read: ( at ) => {

						return dataview.getUint32( at, little_endian );

					}, size: 4 };
					case 'float32': case 'float':	return { read: ( at ) => {

						return dataview.getFloat32( at, little_endian );

					}, size: 4 };
					case 'float64': case 'double':	return { read: ( at ) => {

						return dataview.getFloat64( at, little_endian );

					}, size: 8 };

				}

			}

			for ( let i = 0, l = properties.length; i < l; i ++ ) {

				const property = properties[ i ];

				if ( property.type === 'list' ) {

					property.countReader = getBinaryReader( body, property.countType, little_endian );
					property.valueReader = getBinaryReader( body, property.itemType, little_endian );

				} else {

					property.valueReader = getBinaryReader( body, property.type, little_endian );

				}

			}

		}
```
</details>

### `getBinaryReader(dataview: any, type: any, little_endian: any): { read: (at: any) => any; size: number; }`

**Parameters:**

- **`dataview`** `any`
- **`type`** `any`
- **`little_endian`** `any`

**Returns:** `{ read: (at: any) => any; size: number; }`

**Calls:**

- `dataview.getInt8`
- `dataview.getUint8`
- `dataview.getInt16`
- `dataview.getUint16`
- `dataview.getInt32`
- `dataview.getUint32`
- `dataview.getFloat32`
- `dataview.getFloat64`

**Internal Comments:**
```
// correspondences for non-specific length types here match rply:
```

<details><summary>Code</summary>

```typescript
function getBinaryReader( dataview, type, little_endian ) {

				switch ( type ) {

					// correspondences for non-specific length types here match rply:
					case 'int8':	case 'char':	return { read: ( at ) => {

						return dataview.getInt8( at );

					}, size: 1 };
					case 'uint8':	case 'uchar':	return { read: ( at ) => {

						return dataview.getUint8( at );

					}, size: 1 };
					case 'int16':	case 'short':	return { read: ( at ) => {

						return dataview.getInt16( at, little_endian );

					}, size: 2 };
					case 'uint16':	case 'ushort':	return { read: ( at ) => {

						return dataview.getUint16( at, little_endian );

					}, size: 2 };
					case 'int32':	case 'int':		return { read: ( at ) => {

						return dataview.getInt32( at, little_endian );

					}, size: 4 };
					case 'uint32':	case 'uint':	return { read: ( at ) => {

						return dataview.getUint32( at, little_endian );

					}, size: 4 };
					case 'float32': case 'float':	return { read: ( at ) => {

						return dataview.getFloat32( at, little_endian );

					}, size: 4 };
					case 'float64': case 'double':	return { read: ( at ) => {

						return dataview.getFloat64( at, little_endian );

					}, size: 8 };

				}

			}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getInt8`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getInt8( at );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getInt8`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getInt8( at );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getUint8`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getUint8( at );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getUint8`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getUint8( at );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getInt16`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getInt16( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getInt16`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getInt16( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getUint16`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getUint16( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getUint16`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getUint16( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getInt32`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getInt32( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getInt32`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getInt32( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getUint32`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getUint32( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getUint32`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getUint32( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getFloat32`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getFloat32( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getFloat32`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getFloat32( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getFloat64`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getFloat64( at, little_endian );

					}
```
</details>

### `read(at: any): any`

**Parameters:**

- **`at`** `any`

**Returns:** `any`

**Calls:**

- `dataview.getFloat64`

<details><summary>Code</summary>

```typescript
( at ) => {

						return dataview.getFloat64( at, little_endian );

					}
```
</details>

### `parseBinary(data: any, header: any): any`

**Parameters:**

- **`data`** `any`
- **`header`** `any`

**Returns:** `any`

**Calls:**

- `createBuffer`
- `mapElementAttributes`
- `setPropertyBinaryReaders`
- `binaryReadElement`
- `handleElement`
- `postProcess`

<details><summary>Code</summary>

```typescript
function parseBinary( data, header ) {

			const buffer = createBuffer();

			const little_endian = ( header.format === 'binary_little_endian' );
			const body = new DataView( data, header.headerLength );
			let result, loc = 0;

			for ( let currentElement = 0; currentElement < header.elements.length; currentElement ++ ) {

				const elementDesc = header.elements[ currentElement ];
				const properties = elementDesc.properties;
				const attributeMap = mapElementAttributes( properties );

				setPropertyBinaryReaders( properties, body, little_endian );

				for ( let currentElementCount = 0; currentElementCount < elementDesc.count; currentElementCount ++ ) {

					result = binaryReadElement( loc, properties );
					loc += result[ 1 ];
					const element = result[ 0 ];

					handleElement( buffer, elementDesc.name, element, attributeMap );

				}

			}

			return postProcess( buffer );

		}
```
</details>

### `extractHeaderText(bytes: any): { headerText: string; headerLength: number; }`

**Parameters:**

- **`bytes`** `any`

**Returns:** `{ headerText: string; headerLength: number; }`

**Calls:**

- `new TextDecoder().decode`
- `bytes.subarray`
- `/^ply\r\n/.test`
- `String.fromCharCode`
- `lines.push`
- `lines.join`

**Internal Comments:**
```
// ascii section using \r\n as line endings
```

<details><summary>Code</summary>

```typescript
function extractHeaderText( bytes ) {

			let i = 0;
			let cont = true;

			let line = '';
			const lines = [];

			const startLine = new TextDecoder().decode( bytes.subarray( 0, 5 ) );
			const hasCRNL = /^ply\r\n/.test( startLine );

			do {

				const c = String.fromCharCode( bytes[ i ++ ] );

				if ( c !== '\n' && c !== '\r' ) {

					line += c;

				} else {

					if ( line === 'end_header' ) cont = false;
					if ( line !== '' ) {

						lines.push( line );
						line = '';

					}

				}

			} while ( cont && i < bytes.length );

			// ascii section using \r\n as line endings
			if ( hasCRNL === true ) i ++;

			return { headerText: lines.join( '\r' ) + '\r', headerLength: i };

		}
```
</details>

### `ArrayStream.empty(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
empty() {

		return this.i >= this.arr.length;

	}
```
</details>

### `ArrayStream.next(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
next() {

		return this.arr[ this.i ++ ];

	}
```
</details>


---

## Classes

### `PLYLoader`

<details><summary>Class Code</summary>

```ts
class PLYLoader extends Loader {

	/**
	 * Constructs a new PLY loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		// internals

		this.propertyNameMapping = {};
		this.customPropertyMapping = {};

	}

	/**
	 * Starts loading from the given URL and passes the loaded PLY asset
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
	 * Sets a property name mapping that maps default property names
	 * to custom ones. For example, the following maps the properties
	 * “diffuse_(red|green|blue)” in the file to standard color names.
	 *
	 * ```js
	 * loader.setPropertyNameMapping( {
	 * 	diffuse_red: 'red',
	 * 	diffuse_green: 'green',
	 * 	diffuse_blue: 'blue'
	 * } );
	 * ```
	 *
	 * @param {Object} mapping - The mapping dictionary.
	 */
	setPropertyNameMapping( mapping ) {

		this.propertyNameMapping = mapping;

	}

	/**
	 * Custom properties outside of the defaults for position, uv, normal
	 * and color attributes can be added using the setCustomPropertyNameMapping method.
	 * For example, the following maps the element properties “custom_property_a”
	 * and “custom_property_b” to an attribute “customAttribute” with an item size of 2.
	 * Attribute item sizes are set from the number of element properties in the property array.
	 *
	 * ```js
	 * loader.setCustomPropertyNameMapping( {
	 *	customAttribute: ['custom_property_a', 'custom_property_b'],
	 * } );
	 * ```
	 * @param {Object} mapping - The mapping dictionary.
	 */
	setCustomPropertyNameMapping( mapping ) {

		this.customPropertyMapping = mapping;

	}

	/**
	 * Parses the given PLY data and returns the resulting geometry.
	 *
	 * @param {ArrayBuffer} data - The raw PLY data as an array buffer.
	 * @return {BufferGeometry} The parsed geometry.
	 */
	parse( data ) {

		function parseHeader( data, headerLength = 0 ) {

			const patternHeader = /^ply([\s\S]*)end_header(\r\n|\r|\n)/;
			let headerText = '';
			const result = patternHeader.exec( data );

			if ( result !== null ) {

				headerText = result[ 1 ];

			}

			const header = {
				comments: [],
				elements: [],
				headerLength: headerLength,
				objInfo: ''
			};

			const lines = headerText.split( /\r\n|\r|\n/ );
			let currentElement;

			function make_ply_element_property( propertyValues, propertyNameMapping ) {

				const property = { type: propertyValues[ 0 ] };

				if ( property.type === 'list' ) {

					property.name = propertyValues[ 3 ];
					property.countType = propertyValues[ 1 ];
					property.itemType = propertyValues[ 2 ];

				} else {

					property.name = propertyValues[ 1 ];

				}

				if ( property.name in propertyNameMapping ) {

					property.name = propertyNameMapping[ property.name ];

				}

				return property;

			}

			for ( let i = 0; i < lines.length; i ++ ) {

				let line = lines[ i ];
				line = line.trim();

				if ( line === '' ) continue;

				const lineValues = line.split( /\s+/ );
				const lineType = lineValues.shift();
				line = lineValues.join( ' ' );

				switch ( lineType ) {

					case 'format':

						header.format = lineValues[ 0 ];
						header.version = lineValues[ 1 ];

						break;

					case 'comment':

						header.comments.push( line );

						break;

					case 'element':

						if ( currentElement !== undefined ) {

							header.elements.push( currentElement );

						}

						currentElement = {};
						currentElement.name = lineValues[ 0 ];
						currentElement.count = parseInt( lineValues[ 1 ] );
						currentElement.properties = [];

						break;

					case 'property':

						currentElement.properties.push( make_ply_element_property( lineValues, scope.propertyNameMapping ) );

						break;

					case 'obj_info':

						header.objInfo = line;

						break;


					default:

						console.log( 'unhandled', lineType, lineValues );

				}

			}

			if ( currentElement !== undefined ) {

				header.elements.push( currentElement );

			}

			return header;

		}

		function parseASCIINumber( n, type ) {

			switch ( type ) {

				case 'char': case 'uchar': case 'short': case 'ushort': case 'int': case 'uint':
				case 'int8': case 'uint8': case 'int16': case 'uint16': case 'int32': case 'uint32':

					return parseInt( n );

				case 'float': case 'double': case 'float32': case 'float64':

					return parseFloat( n );

			}

		}

		function parseASCIIElement( properties, tokens ) {

			const element = {};

			for ( let i = 0; i < properties.length; i ++ ) {

				if ( tokens.empty() ) return null;

				if ( properties[ i ].type === 'list' ) {

					const list = [];
					const n = parseASCIINumber( tokens.next(), properties[ i ].countType );

					for ( let j = 0; j < n; j ++ ) {

						if ( tokens.empty() ) return null;

						list.push( parseASCIINumber( tokens.next(), properties[ i ].itemType ) );

					}

					element[ properties[ i ].name ] = list;

				} else {

					element[ properties[ i ].name ] = parseASCIINumber( tokens.next(), properties[ i ].type );

				}

			}

			return element;

		}

		function createBuffer() {

			const buffer = {
			  indices: [],
			  vertices: [],
			  normals: [],
			  uvs: [],
			  faceVertexUvs: [],
			  colors: [],
			  faceVertexColors: []
			};

			for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

			  buffer[ customProperty ] = [];

			}

			return buffer;

		}

		function mapElementAttributes( properties ) {

			const elementNames = properties.map( property => {

				return property.name;

			} );

			function findAttrName( names ) {

				for ( let i = 0, l = names.length; i < l; i ++ ) {

					const name = names[ i ];

					if ( elementNames.includes( name ) ) return name;

				}

				return null;

			}

			return {
				attrX: findAttrName( [ 'x', 'px', 'posx' ] ) || 'x',
				attrY: findAttrName( [ 'y', 'py', 'posy' ] ) || 'y',
				attrZ: findAttrName( [ 'z', 'pz', 'posz' ] ) || 'z',
				attrNX: findAttrName( [ 'nx', 'normalx' ] ),
				attrNY: findAttrName( [ 'ny', 'normaly' ] ),
				attrNZ: findAttrName( [ 'nz', 'normalz' ] ),
				attrS: findAttrName( [ 's', 'u', 'texture_u', 'tx' ] ),
				attrT: findAttrName( [ 't', 'v', 'texture_v', 'ty' ] ),
				attrR: findAttrName( [ 'red', 'diffuse_red', 'r', 'diffuse_r' ] ),
				attrG: findAttrName( [ 'green', 'diffuse_green', 'g', 'diffuse_g' ] ),
				attrB: findAttrName( [ 'blue', 'diffuse_blue', 'b', 'diffuse_b' ] ),
			};

		}

		function parseASCII( data, header ) {

			// PLY ascii format specification, as per http://en.wikipedia.org/wiki/PLY_(file_format)

			const buffer = createBuffer();

			const patternBody = /end_header\s+(\S[\s\S]*\S|\S)\s*$/;
			let body, matches;

			if ( ( matches = patternBody.exec( data ) ) !== null ) {

				body = matches[ 1 ].split( /\s+/ );

			} else {

				body = [ ];

			}

			const tokens = new ArrayStream( body );

			loop: for ( let i = 0; i < header.elements.length; i ++ ) {

				const elementDesc = header.elements[ i ];
				const attributeMap = mapElementAttributes( elementDesc.properties );

				for ( let j = 0; j < elementDesc.count; j ++ ) {

					const element = parseASCIIElement( elementDesc.properties, tokens );

					if ( ! element ) break loop;

					handleElement( buffer, elementDesc.name, element, attributeMap );

				}

			}

			return postProcess( buffer );

		}

		function postProcess( buffer ) {

			let geometry = new BufferGeometry();

			// mandatory buffer data

			if ( buffer.indices.length > 0 ) {

				geometry.setIndex( buffer.indices );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( buffer.vertices, 3 ) );

			// optional buffer data

			if ( buffer.normals.length > 0 ) {

				geometry.setAttribute( 'normal', new Float32BufferAttribute( buffer.normals, 3 ) );

			}

			if ( buffer.uvs.length > 0 ) {

				geometry.setAttribute( 'uv', new Float32BufferAttribute( buffer.uvs, 2 ) );

			}

			if ( buffer.colors.length > 0 ) {

				geometry.setAttribute( 'color', new Float32BufferAttribute( buffer.colors, 3 ) );

			}

			if ( buffer.faceVertexUvs.length > 0 || buffer.faceVertexColors.length > 0 ) {

				geometry = geometry.toNonIndexed();

				if ( buffer.faceVertexUvs.length > 0 ) geometry.setAttribute( 'uv', new Float32BufferAttribute( buffer.faceVertexUvs, 2 ) );
				if ( buffer.faceVertexColors.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( buffer.faceVertexColors, 3 ) );

			}

			// custom buffer data

			for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

				if ( buffer[ customProperty ].length > 0 ) {

				  	geometry.setAttribute(
						customProperty,
						new Float32BufferAttribute(
					  		buffer[ customProperty ],
					  		scope.customPropertyMapping[ customProperty ].length
						)
				  	);

				}

			}

			geometry.computeBoundingSphere();

			return geometry;

		}

		function handleElement( buffer, elementName, element, cacheEntry ) {

			if ( elementName === 'vertex' ) {

				buffer.vertices.push( element[ cacheEntry.attrX ], element[ cacheEntry.attrY ], element[ cacheEntry.attrZ ] );

				if ( cacheEntry.attrNX !== null && cacheEntry.attrNY !== null && cacheEntry.attrNZ !== null ) {

					buffer.normals.push( element[ cacheEntry.attrNX ], element[ cacheEntry.attrNY ], element[ cacheEntry.attrNZ ] );

				}

				if ( cacheEntry.attrS !== null && cacheEntry.attrT !== null ) {

					buffer.uvs.push( element[ cacheEntry.attrS ], element[ cacheEntry.attrT ] );

				}

				if ( cacheEntry.attrR !== null && cacheEntry.attrG !== null && cacheEntry.attrB !== null ) {

					_color.setRGB(
						element[ cacheEntry.attrR ] / 255.0,
						element[ cacheEntry.attrG ] / 255.0,
						element[ cacheEntry.attrB ] / 255.0,
						SRGBColorSpace
					);

					buffer.colors.push( _color.r, _color.g, _color.b );

				}

				for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

					for ( const elementProperty of scope.customPropertyMapping[ customProperty ] ) {

					  buffer[ customProperty ].push( element[ elementProperty ] );

					}

				}

			} else if ( elementName === 'face' ) {

				const vertex_indices = element.vertex_indices || element.vertex_index; // issue #9338
				const texcoord = element.texcoord;

				if ( vertex_indices.length === 3 ) {

					buffer.indices.push( vertex_indices[ 0 ], vertex_indices[ 1 ], vertex_indices[ 2 ] );

					if ( texcoord && texcoord.length === 6 ) {

						buffer.faceVertexUvs.push( texcoord[ 0 ], texcoord[ 1 ] );
						buffer.faceVertexUvs.push( texcoord[ 2 ], texcoord[ 3 ] );
						buffer.faceVertexUvs.push( texcoord[ 4 ], texcoord[ 5 ] );

					}

				} else if ( vertex_indices.length === 4 ) {

					buffer.indices.push( vertex_indices[ 0 ], vertex_indices[ 1 ], vertex_indices[ 3 ] );
					buffer.indices.push( vertex_indices[ 1 ], vertex_indices[ 2 ], vertex_indices[ 3 ] );

				}

				// face colors

				if ( cacheEntry.attrR !== null && cacheEntry.attrG !== null && cacheEntry.attrB !== null ) {

					_color.setRGB(
						element[ cacheEntry.attrR ] / 255.0,
						element[ cacheEntry.attrG ] / 255.0,
						element[ cacheEntry.attrB ] / 255.0,
						SRGBColorSpace
					);
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );

				}

			}

		}

		function binaryReadElement( at, properties ) {

			const element = {};
			let read = 0;

			for ( let i = 0; i < properties.length; i ++ ) {

				const property = properties[ i ];
				const valueReader = property.valueReader;

				if ( property.type === 'list' ) {

					const list = [];

					const n = property.countReader.read( at + read );
					read += property.countReader.size;

					for ( let j = 0; j < n; j ++ ) {

						list.push( valueReader.read( at + read ) );
						read += valueReader.size;

					}

					element[ property.name ] = list;

				} else {

					element[ property.name ] = valueReader.read( at + read );
					read += valueReader.size;

				}

			}

			return [ element, read ];

		}

		function setPropertyBinaryReaders( properties, body, little_endian ) {

			function getBinaryReader( dataview, type, little_endian ) {

				switch ( type ) {

					// correspondences for non-specific length types here match rply:
					case 'int8':	case 'char':	return { read: ( at ) => {

						return dataview.getInt8( at );

					}, size: 1 };
					case 'uint8':	case 'uchar':	return { read: ( at ) => {

						return dataview.getUint8( at );

					}, size: 1 };
					case 'int16':	case 'short':	return { read: ( at ) => {

						return dataview.getInt16( at, little_endian );

					}, size: 2 };
					case 'uint16':	case 'ushort':	return { read: ( at ) => {

						return dataview.getUint16( at, little_endian );

					}, size: 2 };
					case 'int32':	case 'int':		return { read: ( at ) => {

						return dataview.getInt32( at, little_endian );

					}, size: 4 };
					case 'uint32':	case 'uint':	return { read: ( at ) => {

						return dataview.getUint32( at, little_endian );

					}, size: 4 };
					case 'float32': case 'float':	return { read: ( at ) => {

						return dataview.getFloat32( at, little_endian );

					}, size: 4 };
					case 'float64': case 'double':	return { read: ( at ) => {

						return dataview.getFloat64( at, little_endian );

					}, size: 8 };

				}

			}

			for ( let i = 0, l = properties.length; i < l; i ++ ) {

				const property = properties[ i ];

				if ( property.type === 'list' ) {

					property.countReader = getBinaryReader( body, property.countType, little_endian );
					property.valueReader = getBinaryReader( body, property.itemType, little_endian );

				} else {

					property.valueReader = getBinaryReader( body, property.type, little_endian );

				}

			}

		}

		function parseBinary( data, header ) {

			const buffer = createBuffer();

			const little_endian = ( header.format === 'binary_little_endian' );
			const body = new DataView( data, header.headerLength );
			let result, loc = 0;

			for ( let currentElement = 0; currentElement < header.elements.length; currentElement ++ ) {

				const elementDesc = header.elements[ currentElement ];
				const properties = elementDesc.properties;
				const attributeMap = mapElementAttributes( properties );

				setPropertyBinaryReaders( properties, body, little_endian );

				for ( let currentElementCount = 0; currentElementCount < elementDesc.count; currentElementCount ++ ) {

					result = binaryReadElement( loc, properties );
					loc += result[ 1 ];
					const element = result[ 0 ];

					handleElement( buffer, elementDesc.name, element, attributeMap );

				}

			}

			return postProcess( buffer );

		}

		function extractHeaderText( bytes ) {

			let i = 0;
			let cont = true;

			let line = '';
			const lines = [];

			const startLine = new TextDecoder().decode( bytes.subarray( 0, 5 ) );
			const hasCRNL = /^ply\r\n/.test( startLine );

			do {

				const c = String.fromCharCode( bytes[ i ++ ] );

				if ( c !== '\n' && c !== '\r' ) {

					line += c;

				} else {

					if ( line === 'end_header' ) cont = false;
					if ( line !== '' ) {

						lines.push( line );
						line = '';

					}

				}

			} while ( cont && i < bytes.length );

			// ascii section using \r\n as line endings
			if ( hasCRNL === true ) i ++;

			return { headerText: lines.join( '\r' ) + '\r', headerLength: i };

		}

		//

		let geometry;
		const scope = this;

		if ( data instanceof ArrayBuffer ) {

			const bytes = new Uint8Array( data );
			const { headerText, headerLength } = extractHeaderText( bytes );
			const header = parseHeader( headerText, headerLength );

			if ( header.format === 'ascii' ) {

				const text = new TextDecoder().decode( bytes );

				geometry = parseASCII( text, header );

			} else {

				geometry = parseBinary( data, header );

			}

		} else {

			geometry = parseASCII( data, parseHeader( data ) );

		}

		return geometry;

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

##### `setPropertyNameMapping(mapping: any): void`

<details><summary>Code</summary>

```ts
setPropertyNameMapping( mapping ) {

		this.propertyNameMapping = mapping;

	}
```
</details>

##### `setCustomPropertyNameMapping(mapping: any): void`

<details><summary>Code</summary>

```ts
setCustomPropertyNameMapping( mapping ) {

		this.customPropertyMapping = mapping;

	}
```
</details>

##### `parse(data: ArrayBuffer): BufferGeometry`

<details><summary>Code</summary>

```ts
parse( data ) {

		function parseHeader( data, headerLength = 0 ) {

			const patternHeader = /^ply([\s\S]*)end_header(\r\n|\r|\n)/;
			let headerText = '';
			const result = patternHeader.exec( data );

			if ( result !== null ) {

				headerText = result[ 1 ];

			}

			const header = {
				comments: [],
				elements: [],
				headerLength: headerLength,
				objInfo: ''
			};

			const lines = headerText.split( /\r\n|\r|\n/ );
			let currentElement;

			function make_ply_element_property( propertyValues, propertyNameMapping ) {

				const property = { type: propertyValues[ 0 ] };

				if ( property.type === 'list' ) {

					property.name = propertyValues[ 3 ];
					property.countType = propertyValues[ 1 ];
					property.itemType = propertyValues[ 2 ];

				} else {

					property.name = propertyValues[ 1 ];

				}

				if ( property.name in propertyNameMapping ) {

					property.name = propertyNameMapping[ property.name ];

				}

				return property;

			}

			for ( let i = 0; i < lines.length; i ++ ) {

				let line = lines[ i ];
				line = line.trim();

				if ( line === '' ) continue;

				const lineValues = line.split( /\s+/ );
				const lineType = lineValues.shift();
				line = lineValues.join( ' ' );

				switch ( lineType ) {

					case 'format':

						header.format = lineValues[ 0 ];
						header.version = lineValues[ 1 ];

						break;

					case 'comment':

						header.comments.push( line );

						break;

					case 'element':

						if ( currentElement !== undefined ) {

							header.elements.push( currentElement );

						}

						currentElement = {};
						currentElement.name = lineValues[ 0 ];
						currentElement.count = parseInt( lineValues[ 1 ] );
						currentElement.properties = [];

						break;

					case 'property':

						currentElement.properties.push( make_ply_element_property( lineValues, scope.propertyNameMapping ) );

						break;

					case 'obj_info':

						header.objInfo = line;

						break;


					default:

						console.log( 'unhandled', lineType, lineValues );

				}

			}

			if ( currentElement !== undefined ) {

				header.elements.push( currentElement );

			}

			return header;

		}

		function parseASCIINumber( n, type ) {

			switch ( type ) {

				case 'char': case 'uchar': case 'short': case 'ushort': case 'int': case 'uint':
				case 'int8': case 'uint8': case 'int16': case 'uint16': case 'int32': case 'uint32':

					return parseInt( n );

				case 'float': case 'double': case 'float32': case 'float64':

					return parseFloat( n );

			}

		}

		function parseASCIIElement( properties, tokens ) {

			const element = {};

			for ( let i = 0; i < properties.length; i ++ ) {

				if ( tokens.empty() ) return null;

				if ( properties[ i ].type === 'list' ) {

					const list = [];
					const n = parseASCIINumber( tokens.next(), properties[ i ].countType );

					for ( let j = 0; j < n; j ++ ) {

						if ( tokens.empty() ) return null;

						list.push( parseASCIINumber( tokens.next(), properties[ i ].itemType ) );

					}

					element[ properties[ i ].name ] = list;

				} else {

					element[ properties[ i ].name ] = parseASCIINumber( tokens.next(), properties[ i ].type );

				}

			}

			return element;

		}

		function createBuffer() {

			const buffer = {
			  indices: [],
			  vertices: [],
			  normals: [],
			  uvs: [],
			  faceVertexUvs: [],
			  colors: [],
			  faceVertexColors: []
			};

			for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

			  buffer[ customProperty ] = [];

			}

			return buffer;

		}

		function mapElementAttributes( properties ) {

			const elementNames = properties.map( property => {

				return property.name;

			} );

			function findAttrName( names ) {

				for ( let i = 0, l = names.length; i < l; i ++ ) {

					const name = names[ i ];

					if ( elementNames.includes( name ) ) return name;

				}

				return null;

			}

			return {
				attrX: findAttrName( [ 'x', 'px', 'posx' ] ) || 'x',
				attrY: findAttrName( [ 'y', 'py', 'posy' ] ) || 'y',
				attrZ: findAttrName( [ 'z', 'pz', 'posz' ] ) || 'z',
				attrNX: findAttrName( [ 'nx', 'normalx' ] ),
				attrNY: findAttrName( [ 'ny', 'normaly' ] ),
				attrNZ: findAttrName( [ 'nz', 'normalz' ] ),
				attrS: findAttrName( [ 's', 'u', 'texture_u', 'tx' ] ),
				attrT: findAttrName( [ 't', 'v', 'texture_v', 'ty' ] ),
				attrR: findAttrName( [ 'red', 'diffuse_red', 'r', 'diffuse_r' ] ),
				attrG: findAttrName( [ 'green', 'diffuse_green', 'g', 'diffuse_g' ] ),
				attrB: findAttrName( [ 'blue', 'diffuse_blue', 'b', 'diffuse_b' ] ),
			};

		}

		function parseASCII( data, header ) {

			// PLY ascii format specification, as per http://en.wikipedia.org/wiki/PLY_(file_format)

			const buffer = createBuffer();

			const patternBody = /end_header\s+(\S[\s\S]*\S|\S)\s*$/;
			let body, matches;

			if ( ( matches = patternBody.exec( data ) ) !== null ) {

				body = matches[ 1 ].split( /\s+/ );

			} else {

				body = [ ];

			}

			const tokens = new ArrayStream( body );

			loop: for ( let i = 0; i < header.elements.length; i ++ ) {

				const elementDesc = header.elements[ i ];
				const attributeMap = mapElementAttributes( elementDesc.properties );

				for ( let j = 0; j < elementDesc.count; j ++ ) {

					const element = parseASCIIElement( elementDesc.properties, tokens );

					if ( ! element ) break loop;

					handleElement( buffer, elementDesc.name, element, attributeMap );

				}

			}

			return postProcess( buffer );

		}

		function postProcess( buffer ) {

			let geometry = new BufferGeometry();

			// mandatory buffer data

			if ( buffer.indices.length > 0 ) {

				geometry.setIndex( buffer.indices );

			}

			geometry.setAttribute( 'position', new Float32BufferAttribute( buffer.vertices, 3 ) );

			// optional buffer data

			if ( buffer.normals.length > 0 ) {

				geometry.setAttribute( 'normal', new Float32BufferAttribute( buffer.normals, 3 ) );

			}

			if ( buffer.uvs.length > 0 ) {

				geometry.setAttribute( 'uv', new Float32BufferAttribute( buffer.uvs, 2 ) );

			}

			if ( buffer.colors.length > 0 ) {

				geometry.setAttribute( 'color', new Float32BufferAttribute( buffer.colors, 3 ) );

			}

			if ( buffer.faceVertexUvs.length > 0 || buffer.faceVertexColors.length > 0 ) {

				geometry = geometry.toNonIndexed();

				if ( buffer.faceVertexUvs.length > 0 ) geometry.setAttribute( 'uv', new Float32BufferAttribute( buffer.faceVertexUvs, 2 ) );
				if ( buffer.faceVertexColors.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( buffer.faceVertexColors, 3 ) );

			}

			// custom buffer data

			for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

				if ( buffer[ customProperty ].length > 0 ) {

				  	geometry.setAttribute(
						customProperty,
						new Float32BufferAttribute(
					  		buffer[ customProperty ],
					  		scope.customPropertyMapping[ customProperty ].length
						)
				  	);

				}

			}

			geometry.computeBoundingSphere();

			return geometry;

		}

		function handleElement( buffer, elementName, element, cacheEntry ) {

			if ( elementName === 'vertex' ) {

				buffer.vertices.push( element[ cacheEntry.attrX ], element[ cacheEntry.attrY ], element[ cacheEntry.attrZ ] );

				if ( cacheEntry.attrNX !== null && cacheEntry.attrNY !== null && cacheEntry.attrNZ !== null ) {

					buffer.normals.push( element[ cacheEntry.attrNX ], element[ cacheEntry.attrNY ], element[ cacheEntry.attrNZ ] );

				}

				if ( cacheEntry.attrS !== null && cacheEntry.attrT !== null ) {

					buffer.uvs.push( element[ cacheEntry.attrS ], element[ cacheEntry.attrT ] );

				}

				if ( cacheEntry.attrR !== null && cacheEntry.attrG !== null && cacheEntry.attrB !== null ) {

					_color.setRGB(
						element[ cacheEntry.attrR ] / 255.0,
						element[ cacheEntry.attrG ] / 255.0,
						element[ cacheEntry.attrB ] / 255.0,
						SRGBColorSpace
					);

					buffer.colors.push( _color.r, _color.g, _color.b );

				}

				for ( const customProperty of Object.keys( scope.customPropertyMapping ) ) {

					for ( const elementProperty of scope.customPropertyMapping[ customProperty ] ) {

					  buffer[ customProperty ].push( element[ elementProperty ] );

					}

				}

			} else if ( elementName === 'face' ) {

				const vertex_indices = element.vertex_indices || element.vertex_index; // issue #9338
				const texcoord = element.texcoord;

				if ( vertex_indices.length === 3 ) {

					buffer.indices.push( vertex_indices[ 0 ], vertex_indices[ 1 ], vertex_indices[ 2 ] );

					if ( texcoord && texcoord.length === 6 ) {

						buffer.faceVertexUvs.push( texcoord[ 0 ], texcoord[ 1 ] );
						buffer.faceVertexUvs.push( texcoord[ 2 ], texcoord[ 3 ] );
						buffer.faceVertexUvs.push( texcoord[ 4 ], texcoord[ 5 ] );

					}

				} else if ( vertex_indices.length === 4 ) {

					buffer.indices.push( vertex_indices[ 0 ], vertex_indices[ 1 ], vertex_indices[ 3 ] );
					buffer.indices.push( vertex_indices[ 1 ], vertex_indices[ 2 ], vertex_indices[ 3 ] );

				}

				// face colors

				if ( cacheEntry.attrR !== null && cacheEntry.attrG !== null && cacheEntry.attrB !== null ) {

					_color.setRGB(
						element[ cacheEntry.attrR ] / 255.0,
						element[ cacheEntry.attrG ] / 255.0,
						element[ cacheEntry.attrB ] / 255.0,
						SRGBColorSpace
					);
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );
					buffer.faceVertexColors.push( _color.r, _color.g, _color.b );

				}

			}

		}

		function binaryReadElement( at, properties ) {

			const element = {};
			let read = 0;

			for ( let i = 0; i < properties.length; i ++ ) {

				const property = properties[ i ];
				const valueReader = property.valueReader;

				if ( property.type === 'list' ) {

					const list = [];

					const n = property.countReader.read( at + read );
					read += property.countReader.size;

					for ( let j = 0; j < n; j ++ ) {

						list.push( valueReader.read( at + read ) );
						read += valueReader.size;

					}

					element[ property.name ] = list;

				} else {

					element[ property.name ] = valueReader.read( at + read );
					read += valueReader.size;

				}

			}

			return [ element, read ];

		}

		function setPropertyBinaryReaders( properties, body, little_endian ) {

			function getBinaryReader( dataview, type, little_endian ) {

				switch ( type ) {

					// correspondences for non-specific length types here match rply:
					case 'int8':	case 'char':	return { read: ( at ) => {

						return dataview.getInt8( at );

					}, size: 1 };
					case 'uint8':	case 'uchar':	return { read: ( at ) => {

						return dataview.getUint8( at );

					}, size: 1 };
					case 'int16':	case 'short':	return { read: ( at ) => {

						return dataview.getInt16( at, little_endian );

					}, size: 2 };
					case 'uint16':	case 'ushort':	return { read: ( at ) => {

						return dataview.getUint16( at, little_endian );

					}, size: 2 };
					case 'int32':	case 'int':		return { read: ( at ) => {

						return dataview.getInt32( at, little_endian );

					}, size: 4 };
					case 'uint32':	case 'uint':	return { read: ( at ) => {

						return dataview.getUint32( at, little_endian );

					}, size: 4 };
					case 'float32': case 'float':	return { read: ( at ) => {

						return dataview.getFloat32( at, little_endian );

					}, size: 4 };
					case 'float64': case 'double':	return { read: ( at ) => {

						return dataview.getFloat64( at, little_endian );

					}, size: 8 };

				}

			}

			for ( let i = 0, l = properties.length; i < l; i ++ ) {

				const property = properties[ i ];

				if ( property.type === 'list' ) {

					property.countReader = getBinaryReader( body, property.countType, little_endian );
					property.valueReader = getBinaryReader( body, property.itemType, little_endian );

				} else {

					property.valueReader = getBinaryReader( body, property.type, little_endian );

				}

			}

		}

		function parseBinary( data, header ) {

			const buffer = createBuffer();

			const little_endian = ( header.format === 'binary_little_endian' );
			const body = new DataView( data, header.headerLength );
			let result, loc = 0;

			for ( let currentElement = 0; currentElement < header.elements.length; currentElement ++ ) {

				const elementDesc = header.elements[ currentElement ];
				const properties = elementDesc.properties;
				const attributeMap = mapElementAttributes( properties );

				setPropertyBinaryReaders( properties, body, little_endian );

				for ( let currentElementCount = 0; currentElementCount < elementDesc.count; currentElementCount ++ ) {

					result = binaryReadElement( loc, properties );
					loc += result[ 1 ];
					const element = result[ 0 ];

					handleElement( buffer, elementDesc.name, element, attributeMap );

				}

			}

			return postProcess( buffer );

		}

		function extractHeaderText( bytes ) {

			let i = 0;
			let cont = true;

			let line = '';
			const lines = [];

			const startLine = new TextDecoder().decode( bytes.subarray( 0, 5 ) );
			const hasCRNL = /^ply\r\n/.test( startLine );

			do {

				const c = String.fromCharCode( bytes[ i ++ ] );

				if ( c !== '\n' && c !== '\r' ) {

					line += c;

				} else {

					if ( line === 'end_header' ) cont = false;
					if ( line !== '' ) {

						lines.push( line );
						line = '';

					}

				}

			} while ( cont && i < bytes.length );

			// ascii section using \r\n as line endings
			if ( hasCRNL === true ) i ++;

			return { headerText: lines.join( '\r' ) + '\r', headerLength: i };

		}

		//

		let geometry;
		const scope = this;

		if ( data instanceof ArrayBuffer ) {

			const bytes = new Uint8Array( data );
			const { headerText, headerLength } = extractHeaderText( bytes );
			const header = parseHeader( headerText, headerLength );

			if ( header.format === 'ascii' ) {

				const text = new TextDecoder().decode( bytes );

				geometry = parseASCII( text, header );

			} else {

				geometry = parseBinary( data, header );

			}

		} else {

			geometry = parseASCII( data, parseHeader( data ) );

		}

		return geometry;

	}
```
</details>

### `ArrayStream`

<details><summary>Class Code</summary>

```ts
class ArrayStream {

	constructor( arr ) {

		this.arr = arr;
		this.i = 0;

	}

	empty() {

		return this.i >= this.arr.length;

	}

	next() {

		return this.arr[ this.i ++ ];

	}

}
```
</details>

#### Methods

##### `empty(): boolean`

<details><summary>Code</summary>

```ts
empty() {

		return this.i >= this.arr.length;

	}
```
</details>

##### `next(): any`

<details><summary>Code</summary>

```ts
next() {

		return this.arr[ this.i ++ ];

	}
```
</details>


---