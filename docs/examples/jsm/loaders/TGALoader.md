[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TGALoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 63 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/TGALoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataTextureLoader` | `three` |
| `LinearMipmapLinearFilter` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `pixel_data` | `any` | let/var | `*not shown*` | ✗ |
| `palettes` | `any` | let/var | `*not shown*` | ✗ |
| `pixel_size` | `number` | let/var | `header.pixel_size >> 3` | ✗ |
| `pixel_total` | `number` | let/var | `header.width * header.height * pixel_size` | ✗ |
| `c` | `any` | let/var | `*not shown*` | ✗ |
| `count` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `shift` | `number` | let/var | `0` | ✗ |
| `pixels` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( pixel_size )` | ✗ |
| `colormap` | `any` | let/var | `palettes` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `width` | `number` | let/var | `header.width` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `width` | `number` | let/var | `header.width` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `width` | `number` | let/var | `header.width` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `width` | `number` | let/var | `header.width` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `width` | `number` | let/var | `header.width` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `width` | `number` | let/var | `header.width` | ✗ |
| `x_start` | `any` | let/var | `*not shown*` | ✗ |
| `y_start` | `any` | let/var | `*not shown*` | ✗ |
| `x_step` | `any` | let/var | `*not shown*` | ✗ |
| `y_step` | `any` | let/var | `*not shown*` | ✗ |
| `x_end` | `any` | let/var | `*not shown*` | ✗ |
| `y_end` | `any` | let/var | `*not shown*` | ✗ |
| `TGA_TYPE_NO_DATA` | `0` | let/var | `0` | ✗ |
| `TGA_TYPE_INDEXED` | `1` | let/var | `1` | ✗ |
| `TGA_TYPE_RGB` | `2` | let/var | `2` | ✗ |
| `TGA_TYPE_GREY` | `3` | let/var | `3` | ✗ |
| `TGA_TYPE_RLE_INDEXED` | `9` | let/var | `9` | ✗ |
| `TGA_TYPE_RLE_RGB` | `10` | let/var | `10` | ✗ |
| `TGA_TYPE_RLE_GREY` | `11` | let/var | `11` | ✗ |
| `TGA_ORIGIN_MASK` | `48` | let/var | `0x30` | ✗ |
| `TGA_ORIGIN_SHIFT` | `4` | let/var | `0x04` | ✗ |
| `TGA_ORIGIN_BL` | `0` | let/var | `0x00` | ✗ |
| `TGA_ORIGIN_BR` | `1` | let/var | `0x01` | ✗ |
| `TGA_ORIGIN_UL` | `2` | let/var | `0x02` | ✗ |
| `TGA_ORIGIN_UR` | `3` | let/var | `0x03` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `content` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( buffer )` | ✗ |
| `header` | `{ id_length: number; colormap_type: n...` | let/var | `{ id_length: content[ offset ++ ], colormap_type: content[ offset ++ ], image...` | ✗ |
| `use_rle` | `boolean` | let/var | `false` | ✗ |
| `use_pal` | `boolean` | let/var | `false` | ✗ |
| `use_grey` | `boolean` | let/var | `false` | ✗ |
| `imageData` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( header.width * header.height * 4 )` | ✗ |


---

## Functions

### `TGALoader.parse(buffer: ArrayBuffer): DataTextureLoader`

**JSDoc:**
```typescript
/**
	 * Parses the given TGA texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @return {DataTextureLoader~TexData} An object representing the parsed texture data.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`

**Returns:** `DataTextureLoader`

**Calls:**

- `data.subarray`
- `pixel_data.set`
- `tgaGetImageDataGrey8bits`
- `tgaGetImageDataGrey16bits`
- `tgaGetImageData8bits`
- `tgaGetImageData16bits`
- `tgaGetImageData24bits`
- `tgaGetImageData32bits`
- `tgaCheckHeader`
- `tgaParse`
- `getTgaRGBA`

**Internal Comments:**
```
// reference from vthibault, https://github.com/vthibault/roBrowser/blob/master/src/Loaders/Targa.js
// check indexed type
// check colormap type
// What the need of a file without data ?
// Invalid type ?
// check image width and height
// check image pixel size
// parse tga image buffer
// read palettes
// read RLE
// RLE pixels
// bind pixel tmp array
// copy pixel array
// raw pixels (x6)
// Load image data according to specific method
// let func = 'tgaGetImageData' + (use_grey ? 'Grey' : '') + (header.pixel_size) + 'bits';
// func(data, y_start, y_step, y_end, x_start, x_step, x_end, width, image, palette );
// TGA constants (x2)
// check tga if it is valid format (x3)
// skip the needn't data (x3)
// get targa information about RLE compression and palette (x2)
// (x2)
```

<details><summary>Code</summary>

```typescript
parse( buffer ) {

		// reference from vthibault, https://github.com/vthibault/roBrowser/blob/master/src/Loaders/Targa.js

		function tgaCheckHeader( header ) {

			switch ( header.image_type ) {

				// check indexed type

				case TGA_TYPE_INDEXED:
				case TGA_TYPE_RLE_INDEXED:
					if ( header.colormap_length > 256 || header.colormap_size !== 24 || header.colormap_type !== 1 ) {

						throw new Error( 'THREE.TGALoader: Invalid type colormap data for indexed type.' );

					}

					break;

					// check colormap type

				case TGA_TYPE_RGB:
				case TGA_TYPE_GREY:
				case TGA_TYPE_RLE_RGB:
				case TGA_TYPE_RLE_GREY:
					if ( header.colormap_type ) {

						throw new Error( 'THREE.TGALoader: Invalid type colormap data for colormap type.' );

					}

					break;

					// What the need of a file without data ?

				case TGA_TYPE_NO_DATA:
					throw new Error( 'THREE.TGALoader: No data.' );

					// Invalid type ?

				default:
					throw new Error( 'THREE.TGALoader: Invalid type ' + header.image_type );

			}

			// check image width and height

			if ( header.width <= 0 || header.height <= 0 ) {

				throw new Error( 'THREE.TGALoader: Invalid image size.' );

			}

			// check image pixel size

			if ( header.pixel_size !== 8 && header.pixel_size !== 16 &&
				header.pixel_size !== 24 && header.pixel_size !== 32 ) {

				throw new Error( 'THREE.TGALoader: Invalid pixel size ' + header.pixel_size );

			}

		}

		// parse tga image buffer

		function tgaParse( use_rle, use_pal, header, offset, data ) {

			let pixel_data,
				palettes;

			const pixel_size = header.pixel_size >> 3;
			const pixel_total = header.width * header.height * pixel_size;

			 // read palettes

			 if ( use_pal ) {

				 palettes = data.subarray( offset, offset += header.colormap_length * ( header.colormap_size >> 3 ) );

			 }

			 // read RLE

			 if ( use_rle ) {

				 pixel_data = new Uint8Array( pixel_total );

				let c, count, i;
				let shift = 0;
				const pixels = new Uint8Array( pixel_size );

				while ( shift < pixel_total ) {

					c = data[ offset ++ ];
					count = ( c & 0x7f ) + 1;

					// RLE pixels

					if ( c & 0x80 ) {

						// bind pixel tmp array

						for ( i = 0; i < pixel_size; ++ i ) {

							pixels[ i ] = data[ offset ++ ];

						}

						// copy pixel array

						for ( i = 0; i < count; ++ i ) {

							pixel_data.set( pixels, shift + i * pixel_size );

						}

						shift += pixel_size * count;

					} else {

						// raw pixels

						count *= pixel_size;

						for ( i = 0; i < count; ++ i ) {

							pixel_data[ shift + i ] = data[ offset ++ ];

						}

						shift += count;

					}

				}

			 } else {

				// raw pixels

				pixel_data = data.subarray(
					 offset, offset += ( use_pal ? header.width * header.height : pixel_total )
				);

			 }

			 return {
				pixel_data: pixel_data,
				palettes: palettes
			 };

		}

		function tgaGetImageData8bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image, palettes ) {

			const colormap = palettes;
			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i ++ ) {

					color = image[ i ];
					imageData[ ( x + width * y ) * 4 + 3 ] = 255;
					imageData[ ( x + width * y ) * 4 + 2 ] = colormap[ ( color * 3 ) + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = colormap[ ( color * 3 ) + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = colormap[ ( color * 3 ) + 2 ];

				}

			}

			return imageData;

		}

		function tgaGetImageData16bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 2 ) {

					color = image[ i + 0 ] + ( image[ i + 1 ] << 8 );
					imageData[ ( x + width * y ) * 4 + 0 ] = ( color & 0x7C00 ) >> 7;
					imageData[ ( x + width * y ) * 4 + 1 ] = ( color & 0x03E0 ) >> 2;
					imageData[ ( x + width * y ) * 4 + 2 ] = ( color & 0x001F ) << 3;
					imageData[ ( x + width * y ) * 4 + 3 ] = ( color & 0x8000 ) ? 0 : 255;

				}

			}

			return imageData;

		}

		function tgaGetImageData24bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 3 ) {

					imageData[ ( x + width * y ) * 4 + 3 ] = 255;
					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 2 ];

				}

			}

			return imageData;

		}

		function tgaGetImageData32bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 4 ) {

					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 2 ];
					imageData[ ( x + width * y ) * 4 + 3 ] = image[ i + 3 ];

				}

			}

			return imageData;

		}

		function tgaGetImageDataGrey8bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i ++ ) {

					color = image[ i ];
					imageData[ ( x + width * y ) * 4 + 0 ] = color;
					imageData[ ( x + width * y ) * 4 + 1 ] = color;
					imageData[ ( x + width * y ) * 4 + 2 ] = color;
					imageData[ ( x + width * y ) * 4 + 3 ] = 255;

				}

			}

			return imageData;

		}

		function tgaGetImageDataGrey16bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 2 ) {

					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 3 ] = image[ i + 1 ];

				}

			}

			return imageData;

		}

		function getTgaRGBA( data, width, height, image, palette ) {

			let x_start,
				y_start,
				x_step,
				y_step,
				x_end,
				y_end;

			switch ( ( header.flags & TGA_ORIGIN_MASK ) >> TGA_ORIGIN_SHIFT ) {

				default:
				case TGA_ORIGIN_UL:
					x_start = 0;
					x_step = 1;
					x_end = width;
					y_start = 0;
					y_step = 1;
					y_end = height;
					break;

				case TGA_ORIGIN_BL:
					x_start = 0;
					x_step = 1;
					x_end = width;
					y_start = height - 1;
					y_step = - 1;
					y_end = - 1;
					break;

				case TGA_ORIGIN_UR:
					x_start = width - 1;
					x_step = - 1;
					x_end = - 1;
					y_start = 0;
					y_step = 1;
					y_end = height;
					break;

				case TGA_ORIGIN_BR:
					x_start = width - 1;
					x_step = - 1;
					x_end = - 1;
					y_start = height - 1;
					y_step = - 1;
					y_end = - 1;
					break;

			}

			if ( use_grey ) {

				switch ( header.pixel_size ) {

					case 8:
						tgaGetImageDataGrey8bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 16:
						tgaGetImageDataGrey16bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					default:
						throw new Error( 'THREE.TGALoader: Format not supported.' );
						break;

				}

			} else {

				switch ( header.pixel_size ) {

					case 8:
						tgaGetImageData8bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image, palette );
						break;

					case 16:
						tgaGetImageData16bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 24:
						tgaGetImageData24bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 32:
						tgaGetImageData32bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					default:
						throw new Error( 'THREE.TGALoader: Format not supported.' );
						break;

				}

			}

			// Load image data according to specific method
			// let func = 'tgaGetImageData' + (use_grey ? 'Grey' : '') + (header.pixel_size) + 'bits';
			// func(data, y_start, y_step, y_end, x_start, x_step, x_end, width, image, palette );
			return data;

		}

		// TGA constants

		const TGA_TYPE_NO_DATA = 0,
			TGA_TYPE_INDEXED = 1,
			TGA_TYPE_RGB = 2,
			TGA_TYPE_GREY = 3,
			TGA_TYPE_RLE_INDEXED = 9,
			TGA_TYPE_RLE_RGB = 10,
			TGA_TYPE_RLE_GREY = 11,

			TGA_ORIGIN_MASK = 0x30,
			TGA_ORIGIN_SHIFT = 0x04,
			TGA_ORIGIN_BL = 0x00,
			TGA_ORIGIN_BR = 0x01,
			TGA_ORIGIN_UL = 0x02,
			TGA_ORIGIN_UR = 0x03;

		if ( buffer.length < 19 ) throw new Error( 'THREE.TGALoader: Not enough data to contain header.' );

		let offset = 0;

		const content = new Uint8Array( buffer ),
			header = {
				id_length: content[ offset ++ ],
				colormap_type: content[ offset ++ ],
				image_type: content[ offset ++ ],
				colormap_index: content[ offset ++ ] | content[ offset ++ ] << 8,
				colormap_length: content[ offset ++ ] | content[ offset ++ ] << 8,
				colormap_size: content[ offset ++ ],
				origin: [
					content[ offset ++ ] | content[ offset ++ ] << 8,
					content[ offset ++ ] | content[ offset ++ ] << 8
				],
				width: content[ offset ++ ] | content[ offset ++ ] << 8,
				height: content[ offset ++ ] | content[ offset ++ ] << 8,
				pixel_size: content[ offset ++ ],
				flags: content[ offset ++ ]
			};

		// check tga if it is valid format

		tgaCheckHeader( header );

		if ( header.id_length + offset > buffer.length ) {

			throw new Error( 'THREE.TGALoader: No data.' );

		}

		// skip the needn't data

		offset += header.id_length;

		// get targa information about RLE compression and palette

		let use_rle = false,
			use_pal = false,
			use_grey = false;

		switch ( header.image_type ) {

			case TGA_TYPE_RLE_INDEXED:
				use_rle = true;
				use_pal = true;
				break;

			case TGA_TYPE_INDEXED:
				use_pal = true;
				break;

			case TGA_TYPE_RLE_RGB:
				use_rle = true;
				break;

			case TGA_TYPE_RGB:
				break;

			case TGA_TYPE_RLE_GREY:
				use_rle = true;
				use_grey = true;
				break;

			case TGA_TYPE_GREY:
				use_grey = true;
				break;

		}

		//

		const imageData = new Uint8Array( header.width * header.height * 4 );
		const result = tgaParse( use_rle, use_pal, header, offset, content );
		getTgaRGBA( imageData, header.width, header.height, result.pixel_data, result.palettes );

		return {

			data: imageData,
			width: header.width,
			height: header.height,
			flipY: true,
			generateMipmaps: true,
			minFilter: LinearMipmapLinearFilter,

		};

	}
```
</details>

### `tgaCheckHeader(header: any): void`

**Parameters:**

- **`header`** `any`

**Returns:** `void`

**Internal Comments:**
```
// check indexed type
// check colormap type
// What the need of a file without data ?
// Invalid type ?
// check image width and height
// check image pixel size
```

<details><summary>Code</summary>

```typescript
function tgaCheckHeader( header ) {

			switch ( header.image_type ) {

				// check indexed type

				case TGA_TYPE_INDEXED:
				case TGA_TYPE_RLE_INDEXED:
					if ( header.colormap_length > 256 || header.colormap_size !== 24 || header.colormap_type !== 1 ) {

						throw new Error( 'THREE.TGALoader: Invalid type colormap data for indexed type.' );

					}

					break;

					// check colormap type

				case TGA_TYPE_RGB:
				case TGA_TYPE_GREY:
				case TGA_TYPE_RLE_RGB:
				case TGA_TYPE_RLE_GREY:
					if ( header.colormap_type ) {

						throw new Error( 'THREE.TGALoader: Invalid type colormap data for colormap type.' );

					}

					break;

					// What the need of a file without data ?

				case TGA_TYPE_NO_DATA:
					throw new Error( 'THREE.TGALoader: No data.' );

					// Invalid type ?

				default:
					throw new Error( 'THREE.TGALoader: Invalid type ' + header.image_type );

			}

			// check image width and height

			if ( header.width <= 0 || header.height <= 0 ) {

				throw new Error( 'THREE.TGALoader: Invalid image size.' );

			}

			// check image pixel size

			if ( header.pixel_size !== 8 && header.pixel_size !== 16 &&
				header.pixel_size !== 24 && header.pixel_size !== 32 ) {

				throw new Error( 'THREE.TGALoader: Invalid pixel size ' + header.pixel_size );

			}

		}
```
</details>

### `tgaParse(use_rle: any, use_pal: any, header: any, offset: any, data: any): { pixel_data: any; palettes: any; }`

**Parameters:**

- **`use_rle`** `any`
- **`use_pal`** `any`
- **`header`** `any`
- **`offset`** `any`
- **`data`** `any`

**Returns:** `{ pixel_data: any; palettes: any; }`

**Calls:**

- `data.subarray`
- `pixel_data.set`

**Internal Comments:**
```
// read palettes
// read RLE
// RLE pixels
// bind pixel tmp array
// copy pixel array
// raw pixels (x6)
```

<details><summary>Code</summary>

```typescript
function tgaParse( use_rle, use_pal, header, offset, data ) {

			let pixel_data,
				palettes;

			const pixel_size = header.pixel_size >> 3;
			const pixel_total = header.width * header.height * pixel_size;

			 // read palettes

			 if ( use_pal ) {

				 palettes = data.subarray( offset, offset += header.colormap_length * ( header.colormap_size >> 3 ) );

			 }

			 // read RLE

			 if ( use_rle ) {

				 pixel_data = new Uint8Array( pixel_total );

				let c, count, i;
				let shift = 0;
				const pixels = new Uint8Array( pixel_size );

				while ( shift < pixel_total ) {

					c = data[ offset ++ ];
					count = ( c & 0x7f ) + 1;

					// RLE pixels

					if ( c & 0x80 ) {

						// bind pixel tmp array

						for ( i = 0; i < pixel_size; ++ i ) {

							pixels[ i ] = data[ offset ++ ];

						}

						// copy pixel array

						for ( i = 0; i < count; ++ i ) {

							pixel_data.set( pixels, shift + i * pixel_size );

						}

						shift += pixel_size * count;

					} else {

						// raw pixels

						count *= pixel_size;

						for ( i = 0; i < count; ++ i ) {

							pixel_data[ shift + i ] = data[ offset ++ ];

						}

						shift += count;

					}

				}

			 } else {

				// raw pixels

				pixel_data = data.subarray(
					 offset, offset += ( use_pal ? header.width * header.height : pixel_total )
				);

			 }

			 return {
				pixel_data: pixel_data,
				palettes: palettes
			 };

		}
```
</details>

### `tgaGetImageData8bits(imageData: any, y_start: any, y_step: any, y_end: any, x_start: any, x_step: any, x_end: any, image: any, palettes: any): any`

**Parameters:**

- **`imageData`** `any`
- **`y_start`** `any`
- **`y_step`** `any`
- **`y_end`** `any`
- **`x_start`** `any`
- **`x_step`** `any`
- **`x_end`** `any`
- **`image`** `any`
- **`palettes`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function tgaGetImageData8bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image, palettes ) {

			const colormap = palettes;
			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i ++ ) {

					color = image[ i ];
					imageData[ ( x + width * y ) * 4 + 3 ] = 255;
					imageData[ ( x + width * y ) * 4 + 2 ] = colormap[ ( color * 3 ) + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = colormap[ ( color * 3 ) + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = colormap[ ( color * 3 ) + 2 ];

				}

			}

			return imageData;

		}
```
</details>

### `tgaGetImageData16bits(imageData: any, y_start: any, y_step: any, y_end: any, x_start: any, x_step: any, x_end: any, image: any): any`

**Parameters:**

- **`imageData`** `any`
- **`y_start`** `any`
- **`y_step`** `any`
- **`y_end`** `any`
- **`x_start`** `any`
- **`x_step`** `any`
- **`x_end`** `any`
- **`image`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function tgaGetImageData16bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 2 ) {

					color = image[ i + 0 ] + ( image[ i + 1 ] << 8 );
					imageData[ ( x + width * y ) * 4 + 0 ] = ( color & 0x7C00 ) >> 7;
					imageData[ ( x + width * y ) * 4 + 1 ] = ( color & 0x03E0 ) >> 2;
					imageData[ ( x + width * y ) * 4 + 2 ] = ( color & 0x001F ) << 3;
					imageData[ ( x + width * y ) * 4 + 3 ] = ( color & 0x8000 ) ? 0 : 255;

				}

			}

			return imageData;

		}
```
</details>

### `tgaGetImageData24bits(imageData: any, y_start: any, y_step: any, y_end: any, x_start: any, x_step: any, x_end: any, image: any): any`

**Parameters:**

- **`imageData`** `any`
- **`y_start`** `any`
- **`y_step`** `any`
- **`y_end`** `any`
- **`x_start`** `any`
- **`x_step`** `any`
- **`x_end`** `any`
- **`image`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function tgaGetImageData24bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 3 ) {

					imageData[ ( x + width * y ) * 4 + 3 ] = 255;
					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 2 ];

				}

			}

			return imageData;

		}
```
</details>

### `tgaGetImageData32bits(imageData: any, y_start: any, y_step: any, y_end: any, x_start: any, x_step: any, x_end: any, image: any): any`

**Parameters:**

- **`imageData`** `any`
- **`y_start`** `any`
- **`y_step`** `any`
- **`y_end`** `any`
- **`x_start`** `any`
- **`x_step`** `any`
- **`x_end`** `any`
- **`image`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function tgaGetImageData32bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 4 ) {

					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 2 ];
					imageData[ ( x + width * y ) * 4 + 3 ] = image[ i + 3 ];

				}

			}

			return imageData;

		}
```
</details>

### `tgaGetImageDataGrey8bits(imageData: any, y_start: any, y_step: any, y_end: any, x_start: any, x_step: any, x_end: any, image: any): any`

**Parameters:**

- **`imageData`** `any`
- **`y_start`** `any`
- **`y_step`** `any`
- **`y_end`** `any`
- **`x_start`** `any`
- **`x_step`** `any`
- **`x_end`** `any`
- **`image`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function tgaGetImageDataGrey8bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i ++ ) {

					color = image[ i ];
					imageData[ ( x + width * y ) * 4 + 0 ] = color;
					imageData[ ( x + width * y ) * 4 + 1 ] = color;
					imageData[ ( x + width * y ) * 4 + 2 ] = color;
					imageData[ ( x + width * y ) * 4 + 3 ] = 255;

				}

			}

			return imageData;

		}
```
</details>

### `tgaGetImageDataGrey16bits(imageData: any, y_start: any, y_step: any, y_end: any, x_start: any, x_step: any, x_end: any, image: any): any`

**Parameters:**

- **`imageData`** `any`
- **`y_start`** `any`
- **`y_step`** `any`
- **`y_end`** `any`
- **`x_start`** `any`
- **`x_step`** `any`
- **`x_end`** `any`
- **`image`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function tgaGetImageDataGrey16bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 2 ) {

					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 3 ] = image[ i + 1 ];

				}

			}

			return imageData;

		}
```
</details>

### `getTgaRGBA(data: any, width: any, height: any, image: any, palette: any): any`

**Parameters:**

- **`data`** `any`
- **`width`** `any`
- **`height`** `any`
- **`image`** `any`
- **`palette`** `any`

**Returns:** `any`

**Calls:**

- `tgaGetImageDataGrey8bits`
- `tgaGetImageDataGrey16bits`
- `tgaGetImageData8bits`
- `tgaGetImageData16bits`
- `tgaGetImageData24bits`
- `tgaGetImageData32bits`

**Internal Comments:**
```
// Load image data according to specific method
// let func = 'tgaGetImageData' + (use_grey ? 'Grey' : '') + (header.pixel_size) + 'bits';
// func(data, y_start, y_step, y_end, x_start, x_step, x_end, width, image, palette );
```

<details><summary>Code</summary>

```typescript
function getTgaRGBA( data, width, height, image, palette ) {

			let x_start,
				y_start,
				x_step,
				y_step,
				x_end,
				y_end;

			switch ( ( header.flags & TGA_ORIGIN_MASK ) >> TGA_ORIGIN_SHIFT ) {

				default:
				case TGA_ORIGIN_UL:
					x_start = 0;
					x_step = 1;
					x_end = width;
					y_start = 0;
					y_step = 1;
					y_end = height;
					break;

				case TGA_ORIGIN_BL:
					x_start = 0;
					x_step = 1;
					x_end = width;
					y_start = height - 1;
					y_step = - 1;
					y_end = - 1;
					break;

				case TGA_ORIGIN_UR:
					x_start = width - 1;
					x_step = - 1;
					x_end = - 1;
					y_start = 0;
					y_step = 1;
					y_end = height;
					break;

				case TGA_ORIGIN_BR:
					x_start = width - 1;
					x_step = - 1;
					x_end = - 1;
					y_start = height - 1;
					y_step = - 1;
					y_end = - 1;
					break;

			}

			if ( use_grey ) {

				switch ( header.pixel_size ) {

					case 8:
						tgaGetImageDataGrey8bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 16:
						tgaGetImageDataGrey16bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					default:
						throw new Error( 'THREE.TGALoader: Format not supported.' );
						break;

				}

			} else {

				switch ( header.pixel_size ) {

					case 8:
						tgaGetImageData8bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image, palette );
						break;

					case 16:
						tgaGetImageData16bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 24:
						tgaGetImageData24bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 32:
						tgaGetImageData32bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					default:
						throw new Error( 'THREE.TGALoader: Format not supported.' );
						break;

				}

			}

			// Load image data according to specific method
			// let func = 'tgaGetImageData' + (use_grey ? 'Grey' : '') + (header.pixel_size) + 'bits';
			// func(data, y_start, y_step, y_end, x_start, x_step, x_end, width, image, palette );
			return data;

		}
```
</details>


---

## Classes

### `TGALoader`

<details><summary>Class Code</summary>

```ts
class TGALoader extends DataTextureLoader {

	/**
	 * Constructs a new TGA loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Parses the given TGA texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @return {DataTextureLoader~TexData} An object representing the parsed texture data.
	 */
	parse( buffer ) {

		// reference from vthibault, https://github.com/vthibault/roBrowser/blob/master/src/Loaders/Targa.js

		function tgaCheckHeader( header ) {

			switch ( header.image_type ) {

				// check indexed type

				case TGA_TYPE_INDEXED:
				case TGA_TYPE_RLE_INDEXED:
					if ( header.colormap_length > 256 || header.colormap_size !== 24 || header.colormap_type !== 1 ) {

						throw new Error( 'THREE.TGALoader: Invalid type colormap data for indexed type.' );

					}

					break;

					// check colormap type

				case TGA_TYPE_RGB:
				case TGA_TYPE_GREY:
				case TGA_TYPE_RLE_RGB:
				case TGA_TYPE_RLE_GREY:
					if ( header.colormap_type ) {

						throw new Error( 'THREE.TGALoader: Invalid type colormap data for colormap type.' );

					}

					break;

					// What the need of a file without data ?

				case TGA_TYPE_NO_DATA:
					throw new Error( 'THREE.TGALoader: No data.' );

					// Invalid type ?

				default:
					throw new Error( 'THREE.TGALoader: Invalid type ' + header.image_type );

			}

			// check image width and height

			if ( header.width <= 0 || header.height <= 0 ) {

				throw new Error( 'THREE.TGALoader: Invalid image size.' );

			}

			// check image pixel size

			if ( header.pixel_size !== 8 && header.pixel_size !== 16 &&
				header.pixel_size !== 24 && header.pixel_size !== 32 ) {

				throw new Error( 'THREE.TGALoader: Invalid pixel size ' + header.pixel_size );

			}

		}

		// parse tga image buffer

		function tgaParse( use_rle, use_pal, header, offset, data ) {

			let pixel_data,
				palettes;

			const pixel_size = header.pixel_size >> 3;
			const pixel_total = header.width * header.height * pixel_size;

			 // read palettes

			 if ( use_pal ) {

				 palettes = data.subarray( offset, offset += header.colormap_length * ( header.colormap_size >> 3 ) );

			 }

			 // read RLE

			 if ( use_rle ) {

				 pixel_data = new Uint8Array( pixel_total );

				let c, count, i;
				let shift = 0;
				const pixels = new Uint8Array( pixel_size );

				while ( shift < pixel_total ) {

					c = data[ offset ++ ];
					count = ( c & 0x7f ) + 1;

					// RLE pixels

					if ( c & 0x80 ) {

						// bind pixel tmp array

						for ( i = 0; i < pixel_size; ++ i ) {

							pixels[ i ] = data[ offset ++ ];

						}

						// copy pixel array

						for ( i = 0; i < count; ++ i ) {

							pixel_data.set( pixels, shift + i * pixel_size );

						}

						shift += pixel_size * count;

					} else {

						// raw pixels

						count *= pixel_size;

						for ( i = 0; i < count; ++ i ) {

							pixel_data[ shift + i ] = data[ offset ++ ];

						}

						shift += count;

					}

				}

			 } else {

				// raw pixels

				pixel_data = data.subarray(
					 offset, offset += ( use_pal ? header.width * header.height : pixel_total )
				);

			 }

			 return {
				pixel_data: pixel_data,
				palettes: palettes
			 };

		}

		function tgaGetImageData8bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image, palettes ) {

			const colormap = palettes;
			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i ++ ) {

					color = image[ i ];
					imageData[ ( x + width * y ) * 4 + 3 ] = 255;
					imageData[ ( x + width * y ) * 4 + 2 ] = colormap[ ( color * 3 ) + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = colormap[ ( color * 3 ) + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = colormap[ ( color * 3 ) + 2 ];

				}

			}

			return imageData;

		}

		function tgaGetImageData16bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 2 ) {

					color = image[ i + 0 ] + ( image[ i + 1 ] << 8 );
					imageData[ ( x + width * y ) * 4 + 0 ] = ( color & 0x7C00 ) >> 7;
					imageData[ ( x + width * y ) * 4 + 1 ] = ( color & 0x03E0 ) >> 2;
					imageData[ ( x + width * y ) * 4 + 2 ] = ( color & 0x001F ) << 3;
					imageData[ ( x + width * y ) * 4 + 3 ] = ( color & 0x8000 ) ? 0 : 255;

				}

			}

			return imageData;

		}

		function tgaGetImageData24bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 3 ) {

					imageData[ ( x + width * y ) * 4 + 3 ] = 255;
					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 2 ];

				}

			}

			return imageData;

		}

		function tgaGetImageData32bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 4 ) {

					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 2 ];
					imageData[ ( x + width * y ) * 4 + 3 ] = image[ i + 3 ];

				}

			}

			return imageData;

		}

		function tgaGetImageDataGrey8bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i ++ ) {

					color = image[ i ];
					imageData[ ( x + width * y ) * 4 + 0 ] = color;
					imageData[ ( x + width * y ) * 4 + 1 ] = color;
					imageData[ ( x + width * y ) * 4 + 2 ] = color;
					imageData[ ( x + width * y ) * 4 + 3 ] = 255;

				}

			}

			return imageData;

		}

		function tgaGetImageDataGrey16bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 2 ) {

					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 3 ] = image[ i + 1 ];

				}

			}

			return imageData;

		}

		function getTgaRGBA( data, width, height, image, palette ) {

			let x_start,
				y_start,
				x_step,
				y_step,
				x_end,
				y_end;

			switch ( ( header.flags & TGA_ORIGIN_MASK ) >> TGA_ORIGIN_SHIFT ) {

				default:
				case TGA_ORIGIN_UL:
					x_start = 0;
					x_step = 1;
					x_end = width;
					y_start = 0;
					y_step = 1;
					y_end = height;
					break;

				case TGA_ORIGIN_BL:
					x_start = 0;
					x_step = 1;
					x_end = width;
					y_start = height - 1;
					y_step = - 1;
					y_end = - 1;
					break;

				case TGA_ORIGIN_UR:
					x_start = width - 1;
					x_step = - 1;
					x_end = - 1;
					y_start = 0;
					y_step = 1;
					y_end = height;
					break;

				case TGA_ORIGIN_BR:
					x_start = width - 1;
					x_step = - 1;
					x_end = - 1;
					y_start = height - 1;
					y_step = - 1;
					y_end = - 1;
					break;

			}

			if ( use_grey ) {

				switch ( header.pixel_size ) {

					case 8:
						tgaGetImageDataGrey8bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 16:
						tgaGetImageDataGrey16bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					default:
						throw new Error( 'THREE.TGALoader: Format not supported.' );
						break;

				}

			} else {

				switch ( header.pixel_size ) {

					case 8:
						tgaGetImageData8bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image, palette );
						break;

					case 16:
						tgaGetImageData16bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 24:
						tgaGetImageData24bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 32:
						tgaGetImageData32bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					default:
						throw new Error( 'THREE.TGALoader: Format not supported.' );
						break;

				}

			}

			// Load image data according to specific method
			// let func = 'tgaGetImageData' + (use_grey ? 'Grey' : '') + (header.pixel_size) + 'bits';
			// func(data, y_start, y_step, y_end, x_start, x_step, x_end, width, image, palette );
			return data;

		}

		// TGA constants

		const TGA_TYPE_NO_DATA = 0,
			TGA_TYPE_INDEXED = 1,
			TGA_TYPE_RGB = 2,
			TGA_TYPE_GREY = 3,
			TGA_TYPE_RLE_INDEXED = 9,
			TGA_TYPE_RLE_RGB = 10,
			TGA_TYPE_RLE_GREY = 11,

			TGA_ORIGIN_MASK = 0x30,
			TGA_ORIGIN_SHIFT = 0x04,
			TGA_ORIGIN_BL = 0x00,
			TGA_ORIGIN_BR = 0x01,
			TGA_ORIGIN_UL = 0x02,
			TGA_ORIGIN_UR = 0x03;

		if ( buffer.length < 19 ) throw new Error( 'THREE.TGALoader: Not enough data to contain header.' );

		let offset = 0;

		const content = new Uint8Array( buffer ),
			header = {
				id_length: content[ offset ++ ],
				colormap_type: content[ offset ++ ],
				image_type: content[ offset ++ ],
				colormap_index: content[ offset ++ ] | content[ offset ++ ] << 8,
				colormap_length: content[ offset ++ ] | content[ offset ++ ] << 8,
				colormap_size: content[ offset ++ ],
				origin: [
					content[ offset ++ ] | content[ offset ++ ] << 8,
					content[ offset ++ ] | content[ offset ++ ] << 8
				],
				width: content[ offset ++ ] | content[ offset ++ ] << 8,
				height: content[ offset ++ ] | content[ offset ++ ] << 8,
				pixel_size: content[ offset ++ ],
				flags: content[ offset ++ ]
			};

		// check tga if it is valid format

		tgaCheckHeader( header );

		if ( header.id_length + offset > buffer.length ) {

			throw new Error( 'THREE.TGALoader: No data.' );

		}

		// skip the needn't data

		offset += header.id_length;

		// get targa information about RLE compression and palette

		let use_rle = false,
			use_pal = false,
			use_grey = false;

		switch ( header.image_type ) {

			case TGA_TYPE_RLE_INDEXED:
				use_rle = true;
				use_pal = true;
				break;

			case TGA_TYPE_INDEXED:
				use_pal = true;
				break;

			case TGA_TYPE_RLE_RGB:
				use_rle = true;
				break;

			case TGA_TYPE_RGB:
				break;

			case TGA_TYPE_RLE_GREY:
				use_rle = true;
				use_grey = true;
				break;

			case TGA_TYPE_GREY:
				use_grey = true;
				break;

		}

		//

		const imageData = new Uint8Array( header.width * header.height * 4 );
		const result = tgaParse( use_rle, use_pal, header, offset, content );
		getTgaRGBA( imageData, header.width, header.height, result.pixel_data, result.palettes );

		return {

			data: imageData,
			width: header.width,
			height: header.height,
			flipY: true,
			generateMipmaps: true,
			minFilter: LinearMipmapLinearFilter,

		};

	}

}
```
</details>

#### Methods

##### `parse(buffer: ArrayBuffer): DataTextureLoader`

<details><summary>Code</summary>

```ts
parse( buffer ) {

		// reference from vthibault, https://github.com/vthibault/roBrowser/blob/master/src/Loaders/Targa.js

		function tgaCheckHeader( header ) {

			switch ( header.image_type ) {

				// check indexed type

				case TGA_TYPE_INDEXED:
				case TGA_TYPE_RLE_INDEXED:
					if ( header.colormap_length > 256 || header.colormap_size !== 24 || header.colormap_type !== 1 ) {

						throw new Error( 'THREE.TGALoader: Invalid type colormap data for indexed type.' );

					}

					break;

					// check colormap type

				case TGA_TYPE_RGB:
				case TGA_TYPE_GREY:
				case TGA_TYPE_RLE_RGB:
				case TGA_TYPE_RLE_GREY:
					if ( header.colormap_type ) {

						throw new Error( 'THREE.TGALoader: Invalid type colormap data for colormap type.' );

					}

					break;

					// What the need of a file without data ?

				case TGA_TYPE_NO_DATA:
					throw new Error( 'THREE.TGALoader: No data.' );

					// Invalid type ?

				default:
					throw new Error( 'THREE.TGALoader: Invalid type ' + header.image_type );

			}

			// check image width and height

			if ( header.width <= 0 || header.height <= 0 ) {

				throw new Error( 'THREE.TGALoader: Invalid image size.' );

			}

			// check image pixel size

			if ( header.pixel_size !== 8 && header.pixel_size !== 16 &&
				header.pixel_size !== 24 && header.pixel_size !== 32 ) {

				throw new Error( 'THREE.TGALoader: Invalid pixel size ' + header.pixel_size );

			}

		}

		// parse tga image buffer

		function tgaParse( use_rle, use_pal, header, offset, data ) {

			let pixel_data,
				palettes;

			const pixel_size = header.pixel_size >> 3;
			const pixel_total = header.width * header.height * pixel_size;

			 // read palettes

			 if ( use_pal ) {

				 palettes = data.subarray( offset, offset += header.colormap_length * ( header.colormap_size >> 3 ) );

			 }

			 // read RLE

			 if ( use_rle ) {

				 pixel_data = new Uint8Array( pixel_total );

				let c, count, i;
				let shift = 0;
				const pixels = new Uint8Array( pixel_size );

				while ( shift < pixel_total ) {

					c = data[ offset ++ ];
					count = ( c & 0x7f ) + 1;

					// RLE pixels

					if ( c & 0x80 ) {

						// bind pixel tmp array

						for ( i = 0; i < pixel_size; ++ i ) {

							pixels[ i ] = data[ offset ++ ];

						}

						// copy pixel array

						for ( i = 0; i < count; ++ i ) {

							pixel_data.set( pixels, shift + i * pixel_size );

						}

						shift += pixel_size * count;

					} else {

						// raw pixels

						count *= pixel_size;

						for ( i = 0; i < count; ++ i ) {

							pixel_data[ shift + i ] = data[ offset ++ ];

						}

						shift += count;

					}

				}

			 } else {

				// raw pixels

				pixel_data = data.subarray(
					 offset, offset += ( use_pal ? header.width * header.height : pixel_total )
				);

			 }

			 return {
				pixel_data: pixel_data,
				palettes: palettes
			 };

		}

		function tgaGetImageData8bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image, palettes ) {

			const colormap = palettes;
			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i ++ ) {

					color = image[ i ];
					imageData[ ( x + width * y ) * 4 + 3 ] = 255;
					imageData[ ( x + width * y ) * 4 + 2 ] = colormap[ ( color * 3 ) + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = colormap[ ( color * 3 ) + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = colormap[ ( color * 3 ) + 2 ];

				}

			}

			return imageData;

		}

		function tgaGetImageData16bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 2 ) {

					color = image[ i + 0 ] + ( image[ i + 1 ] << 8 );
					imageData[ ( x + width * y ) * 4 + 0 ] = ( color & 0x7C00 ) >> 7;
					imageData[ ( x + width * y ) * 4 + 1 ] = ( color & 0x03E0 ) >> 2;
					imageData[ ( x + width * y ) * 4 + 2 ] = ( color & 0x001F ) << 3;
					imageData[ ( x + width * y ) * 4 + 3 ] = ( color & 0x8000 ) ? 0 : 255;

				}

			}

			return imageData;

		}

		function tgaGetImageData24bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 3 ) {

					imageData[ ( x + width * y ) * 4 + 3 ] = 255;
					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 2 ];

				}

			}

			return imageData;

		}

		function tgaGetImageData32bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 4 ) {

					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 1 ];
					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 2 ];
					imageData[ ( x + width * y ) * 4 + 3 ] = image[ i + 3 ];

				}

			}

			return imageData;

		}

		function tgaGetImageDataGrey8bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let color, i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i ++ ) {

					color = image[ i ];
					imageData[ ( x + width * y ) * 4 + 0 ] = color;
					imageData[ ( x + width * y ) * 4 + 1 ] = color;
					imageData[ ( x + width * y ) * 4 + 2 ] = color;
					imageData[ ( x + width * y ) * 4 + 3 ] = 255;

				}

			}

			return imageData;

		}

		function tgaGetImageDataGrey16bits( imageData, y_start, y_step, y_end, x_start, x_step, x_end, image ) {

			let i = 0, x, y;
			const width = header.width;

			for ( y = y_start; y !== y_end; y += y_step ) {

				for ( x = x_start; x !== x_end; x += x_step, i += 2 ) {

					imageData[ ( x + width * y ) * 4 + 0 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 1 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 2 ] = image[ i + 0 ];
					imageData[ ( x + width * y ) * 4 + 3 ] = image[ i + 1 ];

				}

			}

			return imageData;

		}

		function getTgaRGBA( data, width, height, image, palette ) {

			let x_start,
				y_start,
				x_step,
				y_step,
				x_end,
				y_end;

			switch ( ( header.flags & TGA_ORIGIN_MASK ) >> TGA_ORIGIN_SHIFT ) {

				default:
				case TGA_ORIGIN_UL:
					x_start = 0;
					x_step = 1;
					x_end = width;
					y_start = 0;
					y_step = 1;
					y_end = height;
					break;

				case TGA_ORIGIN_BL:
					x_start = 0;
					x_step = 1;
					x_end = width;
					y_start = height - 1;
					y_step = - 1;
					y_end = - 1;
					break;

				case TGA_ORIGIN_UR:
					x_start = width - 1;
					x_step = - 1;
					x_end = - 1;
					y_start = 0;
					y_step = 1;
					y_end = height;
					break;

				case TGA_ORIGIN_BR:
					x_start = width - 1;
					x_step = - 1;
					x_end = - 1;
					y_start = height - 1;
					y_step = - 1;
					y_end = - 1;
					break;

			}

			if ( use_grey ) {

				switch ( header.pixel_size ) {

					case 8:
						tgaGetImageDataGrey8bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 16:
						tgaGetImageDataGrey16bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					default:
						throw new Error( 'THREE.TGALoader: Format not supported.' );
						break;

				}

			} else {

				switch ( header.pixel_size ) {

					case 8:
						tgaGetImageData8bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image, palette );
						break;

					case 16:
						tgaGetImageData16bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 24:
						tgaGetImageData24bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					case 32:
						tgaGetImageData32bits( data, y_start, y_step, y_end, x_start, x_step, x_end, image );
						break;

					default:
						throw new Error( 'THREE.TGALoader: Format not supported.' );
						break;

				}

			}

			// Load image data according to specific method
			// let func = 'tgaGetImageData' + (use_grey ? 'Grey' : '') + (header.pixel_size) + 'bits';
			// func(data, y_start, y_step, y_end, x_start, x_step, x_end, width, image, palette );
			return data;

		}

		// TGA constants

		const TGA_TYPE_NO_DATA = 0,
			TGA_TYPE_INDEXED = 1,
			TGA_TYPE_RGB = 2,
			TGA_TYPE_GREY = 3,
			TGA_TYPE_RLE_INDEXED = 9,
			TGA_TYPE_RLE_RGB = 10,
			TGA_TYPE_RLE_GREY = 11,

			TGA_ORIGIN_MASK = 0x30,
			TGA_ORIGIN_SHIFT = 0x04,
			TGA_ORIGIN_BL = 0x00,
			TGA_ORIGIN_BR = 0x01,
			TGA_ORIGIN_UL = 0x02,
			TGA_ORIGIN_UR = 0x03;

		if ( buffer.length < 19 ) throw new Error( 'THREE.TGALoader: Not enough data to contain header.' );

		let offset = 0;

		const content = new Uint8Array( buffer ),
			header = {
				id_length: content[ offset ++ ],
				colormap_type: content[ offset ++ ],
				image_type: content[ offset ++ ],
				colormap_index: content[ offset ++ ] | content[ offset ++ ] << 8,
				colormap_length: content[ offset ++ ] | content[ offset ++ ] << 8,
				colormap_size: content[ offset ++ ],
				origin: [
					content[ offset ++ ] | content[ offset ++ ] << 8,
					content[ offset ++ ] | content[ offset ++ ] << 8
				],
				width: content[ offset ++ ] | content[ offset ++ ] << 8,
				height: content[ offset ++ ] | content[ offset ++ ] << 8,
				pixel_size: content[ offset ++ ],
				flags: content[ offset ++ ]
			};

		// check tga if it is valid format

		tgaCheckHeader( header );

		if ( header.id_length + offset > buffer.length ) {

			throw new Error( 'THREE.TGALoader: No data.' );

		}

		// skip the needn't data

		offset += header.id_length;

		// get targa information about RLE compression and palette

		let use_rle = false,
			use_pal = false,
			use_grey = false;

		switch ( header.image_type ) {

			case TGA_TYPE_RLE_INDEXED:
				use_rle = true;
				use_pal = true;
				break;

			case TGA_TYPE_INDEXED:
				use_pal = true;
				break;

			case TGA_TYPE_RLE_RGB:
				use_rle = true;
				break;

			case TGA_TYPE_RGB:
				break;

			case TGA_TYPE_RLE_GREY:
				use_rle = true;
				use_grey = true;
				break;

			case TGA_TYPE_GREY:
				use_grey = true;
				break;

		}

		//

		const imageData = new Uint8Array( header.width * header.height * 4 );
		const result = tgaParse( use_rle, use_pal, header, offset, content );
		getTgaRGBA( imageData, header.width, header.height, result.pixel_data, result.palettes );

		return {

			data: imageData,
			width: header.width,
			height: header.height,
			flipY: true,
			generateMipmaps: true,
			minFilter: LinearMipmapLinearFilter,

		};

	}
```
</details>


---