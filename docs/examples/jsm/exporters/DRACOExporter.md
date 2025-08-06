[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DRACOExporter.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/exporters/DRACOExporter.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `ColorManagement` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `encoder` | `any` | let/var | `new dracoEncoder.Encoder()` | ✗ |
| `builder` | `any` | let/var | `*not shown*` | ✗ |
| `dracoObject` | `any` | let/var | `*not shown*` | ✗ |
| `faces` | `Uint32Array<ArrayBuffer> \| Uint16Arr...` | let/var | `new ( vertices.count > 65535 ? Uint32Array : Uint16Array )( vertices.count )` | ✗ |
| `encodedData` | `any` | let/var | `new dracoEncoder.DracoInt8Array()` | ✗ |
| `encodeSpeed` | `any` | let/var | `( options.encodeSpeed !== undefined ) ? options.encodeSpeed : 5` | ✗ |
| `decodeSpeed` | `any` | let/var | `( options.decodeSpeed !== undefined ) ? options.decodeSpeed : 5` | ✗ |
| `length` | `any` | let/var | `*not shown*` | ✗ |
| `outputData` | `Int8Array<ArrayBuffer>` | let/var | `new Int8Array( new ArrayBuffer( length ) )` | ✗ |
| `_color` | `any` | let/var | `new Color()` | ✗ |
| `count` | `any` | let/var | `attribute.count` | ✗ |
| `itemSize` | `any` | let/var | `attribute.itemSize` | ✗ |
| `array` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( count * itemSize )` | ✗ |


---

## Functions

### `DRACOExporter.parse(object: any, options: {}): Int8Array<ArrayBufferLike>`

**JSDoc:**
```typescript
/**
	 * Parses the given mesh or point cloud and generates the Draco output.
	 *
	 * @param {(Mesh|Points)} object - The mesh or point cloud to export.
	 * @param {DRACOExporter~Options} options - The export options.
	 * @return {Int8Array} The exported Draco.
	 */
```

**Parameters:**

- **`object`** `any`
- **`options`** `{}`

**Returns:** `Int8Array<ArrayBufferLike>`

**Calls:**

- `Object.assign`
- `DracoEncoderModule`
- `geometry.getAttribute`
- `builder.AddFloatAttributeToMesh`
- `geometry.getIndex`
- `builder.AddFacesToMesh`
- `createVertexColorSRGBArray`
- `builder.AddFloatAttribute`
- `encoder.SetSpeedOptions`
- `encoder.SetEncodingMethod`
- `encoder.SetAttributeQuantization`
- `encoder.EncodeMeshToDracoBuffer`
- `encoder.EncodePointCloudToDracoBuffer`
- `dracoEncoder.destroy`
- `encodedData.GetValue`

**Internal Comments:**
```
//Compress using draco encoder (x2)
//Sets the desired encoding and decoding speed for the given options from 0 (slowest speed, but the best compression) to 10 (fastest, but the worst compression). (x2)
// Sets the desired encoding method for a given geometry.
// Sets the quantization (number of bits used to represent) compression options for a named attribute.
// The attribute values will be quantized in a box defined by the maximum extent of the attribute values.
//Copy encoded data to buffer. (x2)
```

<details><summary>Code</summary>

```typescript
parse( object, options = {} ) {

		options = Object.assign( {
			decodeSpeed: 5,
			encodeSpeed: 5,
			encoderMethod: DRACOExporter.MESH_EDGEBREAKER_ENCODING,
			quantization: [ 16, 8, 8, 8, 8 ],
			exportUvs: true,
			exportNormals: true,
			exportColor: false,
		}, options );

		if ( DracoEncoderModule === undefined ) {

			throw new Error( 'THREE.DRACOExporter: required the draco_encoder to work.' );

		}

		const geometry = object.geometry;

		const dracoEncoder = DracoEncoderModule();
		const encoder = new dracoEncoder.Encoder();
		let builder;
		let dracoObject;

		if ( object.isMesh === true ) {

			builder = new dracoEncoder.MeshBuilder();
			dracoObject = new dracoEncoder.Mesh();

			const vertices = geometry.getAttribute( 'position' );
			builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.POSITION, vertices.count, vertices.itemSize, vertices.array );

			const faces = geometry.getIndex();

			if ( faces !== null ) {

				builder.AddFacesToMesh( dracoObject, faces.count / 3, faces.array );

			} else {

				const faces = new ( vertices.count > 65535 ? Uint32Array : Uint16Array )( vertices.count );

				for ( let i = 0; i < faces.length; i ++ ) {

					faces[ i ] = i;

				}

				builder.AddFacesToMesh( dracoObject, vertices.count, faces );

			}

			if ( options.exportNormals === true ) {

				const normals = geometry.getAttribute( 'normal' );

				if ( normals !== undefined ) {

					builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.NORMAL, normals.count, normals.itemSize, normals.array );

				}

			}

			if ( options.exportUvs === true ) {

				const uvs = geometry.getAttribute( 'uv' );

				if ( uvs !== undefined ) {

					builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.TEX_COORD, uvs.count, uvs.itemSize, uvs.array );

				}

			}

			if ( options.exportColor === true ) {

				const colors = geometry.getAttribute( 'color' );

				if ( colors !== undefined ) {

					const array = createVertexColorSRGBArray( colors );

					builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.COLOR, colors.count, colors.itemSize, array );

				}

			}

		} else if ( object.isPoints === true ) {

			builder = new dracoEncoder.PointCloudBuilder();
			dracoObject = new dracoEncoder.PointCloud();

			const vertices = geometry.getAttribute( 'position' );
			builder.AddFloatAttribute( dracoObject, dracoEncoder.POSITION, vertices.count, vertices.itemSize, vertices.array );

			if ( options.exportColor === true ) {

				const colors = geometry.getAttribute( 'color' );

				if ( colors !== undefined ) {

					const array = createVertexColorSRGBArray( colors );

					builder.AddFloatAttribute( dracoObject, dracoEncoder.COLOR, colors.count, colors.itemSize, array );

				}

			}

		} else {

			throw new Error( 'DRACOExporter: Unsupported object type.' );

		}

		//Compress using draco encoder

		const encodedData = new dracoEncoder.DracoInt8Array();

		//Sets the desired encoding and decoding speed for the given options from 0 (slowest speed, but the best compression) to 10 (fastest, but the worst compression).

		const encodeSpeed = ( options.encodeSpeed !== undefined ) ? options.encodeSpeed : 5;
		const decodeSpeed = ( options.decodeSpeed !== undefined ) ? options.decodeSpeed : 5;

		encoder.SetSpeedOptions( encodeSpeed, decodeSpeed );

		// Sets the desired encoding method for a given geometry.

		if ( options.encoderMethod !== undefined ) {

			encoder.SetEncodingMethod( options.encoderMethod );

		}

		// Sets the quantization (number of bits used to represent) compression options for a named attribute.
		// The attribute values will be quantized in a box defined by the maximum extent of the attribute values.
		if ( options.quantization !== undefined ) {

			for ( let i = 0; i < 5; i ++ ) {

				if ( options.quantization[ i ] !== undefined ) {

					encoder.SetAttributeQuantization( i, options.quantization[ i ] );

				}

			}

		}

		let length;

		if ( object.isMesh === true ) {

			length = encoder.EncodeMeshToDracoBuffer( dracoObject, encodedData );

		} else {

			length = encoder.EncodePointCloudToDracoBuffer( dracoObject, true, encodedData );

		}

		dracoEncoder.destroy( dracoObject );

		if ( length === 0 ) {

			throw new Error( 'THREE.DRACOExporter: Draco encoding failed.' );

		}

		//Copy encoded data to buffer.
		const outputData = new Int8Array( new ArrayBuffer( length ) );

		for ( let i = 0; i < length; i ++ ) {

			outputData[ i ] = encodedData.GetValue( i );

		}

		dracoEncoder.destroy( encodedData );
		dracoEncoder.destroy( encoder );
		dracoEncoder.destroy( builder );

		return outputData;

	}
```
</details>

### `createVertexColorSRGBArray(attribute: any): Float32Array<ArrayBuffer>`

**Parameters:**

- **`attribute`** `any`

**Returns:** `Float32Array<ArrayBuffer>`

**Calls:**

- `_color.fromBufferAttribute`
- `ColorManagement.workingToColorSpace`
- `attribute.getW`

**Internal Comments:**
```
// While .drc files do not specify colorspace, the only 'official' tooling (x2)
// is PLY and OBJ converters, which use sRGB. We'll assume sRGB is expected (x2)
// for .drc files, but note that Draco buffers embedded in glTF files will (x2)
// be Linear-sRGB instead. (x2)
```

<details><summary>Code</summary>

```typescript
function createVertexColorSRGBArray( attribute ) {

	// While .drc files do not specify colorspace, the only 'official' tooling
	// is PLY and OBJ converters, which use sRGB. We'll assume sRGB is expected
	// for .drc files, but note that Draco buffers embedded in glTF files will
	// be Linear-sRGB instead.

	const _color = new Color();

	const count = attribute.count;
	const itemSize = attribute.itemSize;
	const array = new Float32Array( count * itemSize );

	for ( let i = 0, il = count; i < il; i ++ ) {

		_color.fromBufferAttribute( attribute, i );

		ColorManagement.workingToColorSpace( _color, SRGBColorSpace );

		array[ i * itemSize ] = _color.r;
		array[ i * itemSize + 1 ] = _color.g;
		array[ i * itemSize + 2 ] = _color.b;

		if ( itemSize === 4 ) {

			array[ i * itemSize + 3 ] = attribute.getW( i );

		}

	}

	return array;

}
```
</details>


---

## Classes

### `DRACOExporter`

<details><summary>Class Code</summary>

```ts
class DRACOExporter {

	/**
	 * Parses the given mesh or point cloud and generates the Draco output.
	 *
	 * @param {(Mesh|Points)} object - The mesh or point cloud to export.
	 * @param {DRACOExporter~Options} options - The export options.
	 * @return {Int8Array} The exported Draco.
	 */
	parse( object, options = {} ) {

		options = Object.assign( {
			decodeSpeed: 5,
			encodeSpeed: 5,
			encoderMethod: DRACOExporter.MESH_EDGEBREAKER_ENCODING,
			quantization: [ 16, 8, 8, 8, 8 ],
			exportUvs: true,
			exportNormals: true,
			exportColor: false,
		}, options );

		if ( DracoEncoderModule === undefined ) {

			throw new Error( 'THREE.DRACOExporter: required the draco_encoder to work.' );

		}

		const geometry = object.geometry;

		const dracoEncoder = DracoEncoderModule();
		const encoder = new dracoEncoder.Encoder();
		let builder;
		let dracoObject;

		if ( object.isMesh === true ) {

			builder = new dracoEncoder.MeshBuilder();
			dracoObject = new dracoEncoder.Mesh();

			const vertices = geometry.getAttribute( 'position' );
			builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.POSITION, vertices.count, vertices.itemSize, vertices.array );

			const faces = geometry.getIndex();

			if ( faces !== null ) {

				builder.AddFacesToMesh( dracoObject, faces.count / 3, faces.array );

			} else {

				const faces = new ( vertices.count > 65535 ? Uint32Array : Uint16Array )( vertices.count );

				for ( let i = 0; i < faces.length; i ++ ) {

					faces[ i ] = i;

				}

				builder.AddFacesToMesh( dracoObject, vertices.count, faces );

			}

			if ( options.exportNormals === true ) {

				const normals = geometry.getAttribute( 'normal' );

				if ( normals !== undefined ) {

					builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.NORMAL, normals.count, normals.itemSize, normals.array );

				}

			}

			if ( options.exportUvs === true ) {

				const uvs = geometry.getAttribute( 'uv' );

				if ( uvs !== undefined ) {

					builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.TEX_COORD, uvs.count, uvs.itemSize, uvs.array );

				}

			}

			if ( options.exportColor === true ) {

				const colors = geometry.getAttribute( 'color' );

				if ( colors !== undefined ) {

					const array = createVertexColorSRGBArray( colors );

					builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.COLOR, colors.count, colors.itemSize, array );

				}

			}

		} else if ( object.isPoints === true ) {

			builder = new dracoEncoder.PointCloudBuilder();
			dracoObject = new dracoEncoder.PointCloud();

			const vertices = geometry.getAttribute( 'position' );
			builder.AddFloatAttribute( dracoObject, dracoEncoder.POSITION, vertices.count, vertices.itemSize, vertices.array );

			if ( options.exportColor === true ) {

				const colors = geometry.getAttribute( 'color' );

				if ( colors !== undefined ) {

					const array = createVertexColorSRGBArray( colors );

					builder.AddFloatAttribute( dracoObject, dracoEncoder.COLOR, colors.count, colors.itemSize, array );

				}

			}

		} else {

			throw new Error( 'DRACOExporter: Unsupported object type.' );

		}

		//Compress using draco encoder

		const encodedData = new dracoEncoder.DracoInt8Array();

		//Sets the desired encoding and decoding speed for the given options from 0 (slowest speed, but the best compression) to 10 (fastest, but the worst compression).

		const encodeSpeed = ( options.encodeSpeed !== undefined ) ? options.encodeSpeed : 5;
		const decodeSpeed = ( options.decodeSpeed !== undefined ) ? options.decodeSpeed : 5;

		encoder.SetSpeedOptions( encodeSpeed, decodeSpeed );

		// Sets the desired encoding method for a given geometry.

		if ( options.encoderMethod !== undefined ) {

			encoder.SetEncodingMethod( options.encoderMethod );

		}

		// Sets the quantization (number of bits used to represent) compression options for a named attribute.
		// The attribute values will be quantized in a box defined by the maximum extent of the attribute values.
		if ( options.quantization !== undefined ) {

			for ( let i = 0; i < 5; i ++ ) {

				if ( options.quantization[ i ] !== undefined ) {

					encoder.SetAttributeQuantization( i, options.quantization[ i ] );

				}

			}

		}

		let length;

		if ( object.isMesh === true ) {

			length = encoder.EncodeMeshToDracoBuffer( dracoObject, encodedData );

		} else {

			length = encoder.EncodePointCloudToDracoBuffer( dracoObject, true, encodedData );

		}

		dracoEncoder.destroy( dracoObject );

		if ( length === 0 ) {

			throw new Error( 'THREE.DRACOExporter: Draco encoding failed.' );

		}

		//Copy encoded data to buffer.
		const outputData = new Int8Array( new ArrayBuffer( length ) );

		for ( let i = 0; i < length; i ++ ) {

			outputData[ i ] = encodedData.GetValue( i );

		}

		dracoEncoder.destroy( encodedData );
		dracoEncoder.destroy( encoder );
		dracoEncoder.destroy( builder );

		return outputData;

	}

}
```
</details>

#### Methods

##### `parse(object: any, options: {}): Int8Array<ArrayBufferLike>`

<details><summary>Code</summary>

```ts
parse( object, options = {} ) {

		options = Object.assign( {
			decodeSpeed: 5,
			encodeSpeed: 5,
			encoderMethod: DRACOExporter.MESH_EDGEBREAKER_ENCODING,
			quantization: [ 16, 8, 8, 8, 8 ],
			exportUvs: true,
			exportNormals: true,
			exportColor: false,
		}, options );

		if ( DracoEncoderModule === undefined ) {

			throw new Error( 'THREE.DRACOExporter: required the draco_encoder to work.' );

		}

		const geometry = object.geometry;

		const dracoEncoder = DracoEncoderModule();
		const encoder = new dracoEncoder.Encoder();
		let builder;
		let dracoObject;

		if ( object.isMesh === true ) {

			builder = new dracoEncoder.MeshBuilder();
			dracoObject = new dracoEncoder.Mesh();

			const vertices = geometry.getAttribute( 'position' );
			builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.POSITION, vertices.count, vertices.itemSize, vertices.array );

			const faces = geometry.getIndex();

			if ( faces !== null ) {

				builder.AddFacesToMesh( dracoObject, faces.count / 3, faces.array );

			} else {

				const faces = new ( vertices.count > 65535 ? Uint32Array : Uint16Array )( vertices.count );

				for ( let i = 0; i < faces.length; i ++ ) {

					faces[ i ] = i;

				}

				builder.AddFacesToMesh( dracoObject, vertices.count, faces );

			}

			if ( options.exportNormals === true ) {

				const normals = geometry.getAttribute( 'normal' );

				if ( normals !== undefined ) {

					builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.NORMAL, normals.count, normals.itemSize, normals.array );

				}

			}

			if ( options.exportUvs === true ) {

				const uvs = geometry.getAttribute( 'uv' );

				if ( uvs !== undefined ) {

					builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.TEX_COORD, uvs.count, uvs.itemSize, uvs.array );

				}

			}

			if ( options.exportColor === true ) {

				const colors = geometry.getAttribute( 'color' );

				if ( colors !== undefined ) {

					const array = createVertexColorSRGBArray( colors );

					builder.AddFloatAttributeToMesh( dracoObject, dracoEncoder.COLOR, colors.count, colors.itemSize, array );

				}

			}

		} else if ( object.isPoints === true ) {

			builder = new dracoEncoder.PointCloudBuilder();
			dracoObject = new dracoEncoder.PointCloud();

			const vertices = geometry.getAttribute( 'position' );
			builder.AddFloatAttribute( dracoObject, dracoEncoder.POSITION, vertices.count, vertices.itemSize, vertices.array );

			if ( options.exportColor === true ) {

				const colors = geometry.getAttribute( 'color' );

				if ( colors !== undefined ) {

					const array = createVertexColorSRGBArray( colors );

					builder.AddFloatAttribute( dracoObject, dracoEncoder.COLOR, colors.count, colors.itemSize, array );

				}

			}

		} else {

			throw new Error( 'DRACOExporter: Unsupported object type.' );

		}

		//Compress using draco encoder

		const encodedData = new dracoEncoder.DracoInt8Array();

		//Sets the desired encoding and decoding speed for the given options from 0 (slowest speed, but the best compression) to 10 (fastest, but the worst compression).

		const encodeSpeed = ( options.encodeSpeed !== undefined ) ? options.encodeSpeed : 5;
		const decodeSpeed = ( options.decodeSpeed !== undefined ) ? options.decodeSpeed : 5;

		encoder.SetSpeedOptions( encodeSpeed, decodeSpeed );

		// Sets the desired encoding method for a given geometry.

		if ( options.encoderMethod !== undefined ) {

			encoder.SetEncodingMethod( options.encoderMethod );

		}

		// Sets the quantization (number of bits used to represent) compression options for a named attribute.
		// The attribute values will be quantized in a box defined by the maximum extent of the attribute values.
		if ( options.quantization !== undefined ) {

			for ( let i = 0; i < 5; i ++ ) {

				if ( options.quantization[ i ] !== undefined ) {

					encoder.SetAttributeQuantization( i, options.quantization[ i ] );

				}

			}

		}

		let length;

		if ( object.isMesh === true ) {

			length = encoder.EncodeMeshToDracoBuffer( dracoObject, encodedData );

		} else {

			length = encoder.EncodePointCloudToDracoBuffer( dracoObject, true, encodedData );

		}

		dracoEncoder.destroy( dracoObject );

		if ( length === 0 ) {

			throw new Error( 'THREE.DRACOExporter: Draco encoding failed.' );

		}

		//Copy encoded data to buffer.
		const outputData = new Int8Array( new ArrayBuffer( length ) );

		for ( let i = 0; i < length; i ++ ) {

			outputData[ i ] = encodedData.GetValue( i );

		}

		dracoEncoder.destroy( encodedData );
		dracoEncoder.destroy( encoder );
		dracoEncoder.destroy( builder );

		return outputData;

	}
```
</details>


---