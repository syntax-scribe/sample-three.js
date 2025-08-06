[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `USDZExporter.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 28 |
| 🧱 Classes | 2 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 72 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/exporters/USDZExporter.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NoColorSpace` | `three` |
| `DoubleSide` | `three` |
| `Color` | `three` |
| `strToU8` | `../libs/fflate.module.js` |
| `zipSync` | `../libs/fflate.module.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `key` | `any` | let/var | `item.key` | ✗ |
| `value` | `any` | let/var | `item.value` | ✗ |
| `lines` | `any[]` | let/var | `[]` | ✗ |
| `meta` | `string` | let/var | `formattedMetadata.length ? ` (\n${formattedMetadata .map( ( l ) => `${pad}\t$...` | ✗ |
| `property` | `any` | let/var | `l.property` | ✗ |
| `metadata` | `string` | let/var | `l.metadata.length ? ` (\n${l.metadata.map( ( m ) => `${pad}\t\t${m}` ).join( ...` | ✗ |
| `bodyLines` | `any[]` | let/var | `[]` | ✗ |
| `type` | `string` | let/var | `this.type ? this.type + ' ' : ''` | ✗ |
| `usedNames` | `Set<any>` | let/var | `new Set()` | ✗ |
| `files` | `{}` | let/var | `{}` | ✗ |
| `modelFileName` | `"model.usda"` | let/var | `'model.usda'` | ✗ |
| `root` | `USDNode` | let/var | `new USDNode( 'Root', 'Xform' )` | ✗ |
| `scenesNode` | `USDNode` | let/var | `new USDNode( 'Scenes', 'Scope' )` | ✗ |
| `sceneName` | `"Scene"` | let/var | `'Scene'` | ✗ |
| `sceneNode` | `USDNode` | let/var | `new USDNode( sceneName, 'Xform' )` | ✗ |
| `output` | `any` | let/var | `*not shown*` | ✗ |
| `materials` | `{}` | let/var | `{}` | ✗ |
| `textures` | `{}` | let/var | `{}` | ✗ |
| `texture` | `any` | let/var | `textures[ id ]` | ✗ |
| `blob` | `any` | let/var | `await new Promise( ( resolve ) => canvas.toBlob( resolve, 'image/png', 1 ) )` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `file` | `any` | let/var | `files[ filename ]` | ✗ |
| `headerSize` | `number` | let/var | `34 + filename.length` | ✗ |
| `offsetMod64` | `number` | let/var | `offset & 63` | ✗ |
| `padLength` | `number` | let/var | `64 - offsetMod64` | ✗ |
| `padding` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( padLength )` | ✗ |
| `name` | `any` | let/var | `object.name` | ✗ |
| `scale` | `number` | let/var | `maxTextureSize / Math.max( image.width, image.height )` | ✗ |
| `PRECISION` | `7` | let/var | `7` | ✗ |
| `child` | `any` | let/var | `object.children[ i ]` | ✗ |
| `childNode` | `any` | let/var | `*not shown*` | ✗ |
| `geometry` | `any` | let/var | `child.geometry` | ✗ |
| `material` | `any` | let/var | `child.material` | ✗ |
| `geometryFileName` | `string` | let/var | `'geometries/Geometry_' + geometry.id + '.usda'` | ✗ |
| `node` | `USDNode` | let/var | `new USDNode( name, 'Xform' )` | ✗ |
| `array` | `any` | let/var | `matrix.elements` | ✗ |
| `node` | `USDNode` | let/var | `new USDNode( 'Geometry' )` | ✗ |
| `name` | `"Geometry"` | let/var | `'Geometry'` | ✗ |
| `attributes` | `any` | let/var | `geometry.attributes` | ✗ |
| `count` | `any` | let/var | `attributes.position.count` | ✗ |
| `node` | `USDNode` | let/var | `new USDNode( name, 'Mesh' )` | ✗ |
| `id` | `number \| ""` | let/var | `i > 0 ? i : ''` | ✗ |
| `attribute` | `any` | let/var | `attributes[ 'uv' + id ]` | ✗ |
| `colorAttribute` | `any` | let/var | `attributes.color` | ✗ |
| `count` | `any` | let/var | `geometry.index !== null ? geometry.index.count : geometry.attributes.position...` | ✗ |
| `index` | `any` | let/var | `geometry.index` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `length` | `any` | let/var | `geometry.attributes.position.count` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `materialsNode` | `USDNode` | let/var | `new USDNode( 'Materials' )` | ✗ |
| `material` | `any` | let/var | `materials[ uuid ]` | ✗ |
| `materialNode` | `USDNode` | let/var | `new USDNode( `Material_${material.id}`, 'Material' )` | ✗ |
| `id` | `string` | let/var | `texture.source.id + '_' + texture.flipY` | ✗ |
| `uv` | `string` | let/var | `texture.channel > 0 ? 'st' + texture.channel : 'st'` | ✗ |
| `WRAPPINGS` | `{ 1000: string; 1001: string; 1002: s...` | let/var | `{ 1000: 'repeat', // RepeatWrapping 1001: 'clamp', // ClampToEdgeWrapping 100...` | ✗ |
| `rotation` | `any` | let/var | `texture.rotation` | ✗ |
| `primvarReaderNode` | `USDNode` | let/var | `new USDNode( `PrimvarReader_${mapType}`, 'Shader' )` | ✗ |
| `transform2dNode` | `USDNode` | let/var | `new USDNode( `Transform2d_${mapType}`, 'Shader' )` | ✗ |
| `textureNode` | `USDNode` | let/var | `new USDNode( `Texture_${texture.id}_${mapType}`, 'Shader' )` | ✗ |
| `previewSurfaceNode` | `USDNode` | let/var | `new USDNode( 'PreviewSurface', 'Shader' )` | ✗ |
| `emissiveColor` | `any` | let/var | `new Color( material.emissive.r * material.emissiveIntensity, material.emissiv...` | ✗ |
| `aoColor` | `any` | let/var | `new Color( material.aoMapIntensity, material.aoMapIntensity, material.aoMapIn...` | ✗ |
| `roughnessColor` | `any` | let/var | `new Color( material.roughness, material.roughness, material.roughness )` | ✗ |
| `metalnessColor` | `any` | let/var | `new Color( material.metalness, material.metalness, material.metalness )` | ✗ |
| `clearcoatColor` | `any` | let/var | `new Color( material.clearcoat, material.clearcoat, material.clearcoat )` | ✗ |
| `clearcoatRoughnessColor` | `any` | let/var | `new Color( material.clearcoatRoughness, material.clearcoatRoughness, material...` | ✗ |
| `node` | `USDNode` | let/var | `new USDNode( name, 'Camera' )` | ✗ |
| `projection` | `"perspective" \| "orthographic"` | let/var | `camera.isOrthographicCamera ? 'orthographic' : 'perspective'` | ✗ |
| `clippingRange` | `string` | let/var | ``(${camera.near.toPrecision( PRECISION )}, ${camera.far.toPrecision( PRECISIO...` | ✗ |
| `horizontalAperture` | `any` | let/var | `*not shown*` | ✗ |
| `verticalAperture` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `USDNode.addMetadata(key: any, value: any): void`

**Parameters:**

- **`key`** `any`
- **`value`** `any`

**Returns:** `void`

**Calls:**

- `this.metadata.push`

<details><summary>Code</summary>

```typescript
addMetadata( key, value ) {

		this.metadata.push( { key, value } );

	}
```
</details>

### `USDNode.addProperty(property: any, metadata: any[]): void`

**Parameters:**

- **`property`** `any`
- **`metadata`** `any[]`

**Returns:** `void`

**Calls:**

- `this.properties.push`

<details><summary>Code</summary>

```typescript
addProperty( property, metadata = [] ) {

		this.properties.push( { property, metadata } );

	}
```
</details>

### `USDNode.addChild(child: any): void`

**Parameters:**

- **`child`** `any`

**Returns:** `void`

**Calls:**

- `this.children.push`

<details><summary>Code</summary>

```typescript
addChild( child ) {

		this.children.push( child );

	}
```
</details>

### `USDNode.toString(indent: number): string`

**Parameters:**

- **`indent`** `number`

**Returns:** `string`

**Calls:**

- `'\t'.repeat`
- `this.metadata.map`
- `Array.isArray`
- `lines.push`
- `value.forEach`
- `lines.join`
- `formattedMetadata
				.map( ( l ) => `${pad}\t${l}` )
				.join`
- `this.properties.map`
- `l.metadata.map( ( m ) => `${pad}\t\t${m}` ).join`
- `this.children.map`
- `c.toString`
- `bodyLines.push`
- `bodyLines.join`

<details><summary>Code</summary>

```typescript
toString( indent = 0 ) {

		const pad = '\t'.repeat( indent );

		const formattedMetadata = this.metadata.map( ( item ) => {

			const key = item.key;
			const value = item.value;

			if ( Array.isArray( value ) ) {

				const lines = [];
				lines.push( `${key} = {` );
				value.forEach( ( line ) => {

					lines.push( `${pad}\t\t${line}` );

				} );
				lines.push( `${pad}\t}` );
				return lines.join( '\n' );

			} else {

				return `${key} = ${value}`;

			}

		} );

		const meta = formattedMetadata.length
			? ` (\n${formattedMetadata
				.map( ( l ) => `${pad}\t${l}` )
				.join( '\n' )}\n${pad})`
			: '';

		const properties = this.properties.map( ( l ) => {

			const property = l.property;
			const metadata = l.metadata.length
				? ` (\n${l.metadata.map( ( m ) => `${pad}\t\t${m}` ).join( '\n' )}\n${pad}\t)`
				: '';
			return `${pad}\t${property}${metadata}`;

		} );
		const children = this.children.map( ( c ) => c.toString( indent + 1 ) );

		const bodyLines = [];

		if ( properties.length > 0 ) {

			bodyLines.push( ...properties );

		}

		if ( children.length > 0 ) {

			if ( properties.length > 0 ) {

				bodyLines.push( '' );

			}

			for ( let i = 0; i < children.length; i ++ ) {

				bodyLines.push( children[ i ] );
				if ( i < children.length - 1 ) {

					bodyLines.push( '' );

				}

			}

		}

		const bodyContent = bodyLines.join( '\n' );

		const type = this.type ? this.type + ' ' : '';

		return `${pad}def ${type}"${this.name}"${meta}\n${pad}{\n${bodyContent}\n${pad}}`;

	}
```
</details>

### `USDZExporter.setTextureUtils(utils: any): void`

**JSDoc:**
```typescript
/**
	 * Sets the texture utils for this exporter. Only relevant when compressed textures have to be exported.
	 *
	 * Depending on whether you use {@link WebGLRenderer} or {@link WebGPURenderer}, you must inject the
	 * corresponding texture utils {@link WebGLTextureUtils} or {@link WebGPUTextureUtils}.
	 *
	 * @param {WebGLTextureUtils|WebGPUTextureUtils} utils - The texture utils.
	 */
```

**Parameters:**

- **`utils`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setTextureUtils( utils ) {

		this.textureUtils = utils;

	}
```
</details>

### `USDZExporter.parse(scene: Object3D, onDone: any, onError: any, options: any): void`

**JSDoc:**
```typescript
/**
	 * Parse the given 3D object and generates the USDZ output.
	 *
	 * @param {Object3D} scene - The 3D object to export.
	 * @param {USDZExporter~OnDone} onDone - A callback function that is executed when the export has finished.
	 * @param {USDZExporter~OnError} onError - A callback function that is executed when an error happens.
	 * @param {USDZExporter~Options} options - The export options.
	 */
```

**Parameters:**

- **`scene`** `Object3D`
- **`onDone`** `any`
- **`onError`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `this.parseAsync( scene, options ).then( onDone ).catch`

<details><summary>Code</summary>

```typescript
parse( scene, onDone, onError, options ) {

		this.parseAsync( scene, options ).then( onDone ).catch( onError );

	}
```
</details>

### `USDZExporter.parseAsync(scene: Object3D, options: {}): Promise<ArrayBuffer>`

**JSDoc:**
```typescript
/**
	 * Async version of {@link USDZExporter#parse}.
	 *
	 * @async
	 * @param {Object3D} scene - The 3D object to export.
	 * @param {USDZExporter~Options} options - The export options.
	 * @return {Promise<ArrayBuffer>} A Promise that resolved with the exported USDZ data.
	 */
```

**Parameters:**

- **`scene`** `Object3D`
- **`options`** `{}`

**Returns:** `Promise<ArrayBuffer>`

**Calls:**

- `Object.assign`
- `scenesNode.addMetadata`
- `root.addChild`
- `sceneNode.addMetadata`
- `sceneNode.addProperty`
- `scenesNode.addChild`
- `buildHierarchy`
- `buildMaterials`
- `buildHeader`
- `root.toString`
- `materialsNode.toString`
- `strToU8 (from ../libs/fflate.module.js)`
- `this.textureUtils.decompress`
- `imageToCanvas`
- `canvas.toBlob`
- `blob.arrayBuffer`
- `zipSync (from ../libs/fflate.module.js)`

**Internal Comments:**
```
// model file should be first in USDZ archive so we init it here (x4)
// 64 byte alignment (x2)
// https://github.com/101arrowz/fflate/issues/39#issuecomment-777263109 (x2)
```

<details><summary>Code</summary>

```typescript
async parseAsync( scene, options = {} ) {

		options = Object.assign(
			{
				ar: {
					anchoring: { type: 'plane' },
					planeAnchoring: { alignment: 'horizontal' },
				},
				includeAnchoringProperties: true,
				onlyVisible: true,
				quickLookCompatible: false,
				maxTextureSize: 1024,
			},
			options
		);

		const usedNames = new Set();

		const files = {};
		const modelFileName = 'model.usda';

		// model file should be first in USDZ archive so we init it here
		files[ modelFileName ] = null;

		const root = new USDNode( 'Root', 'Xform' );
		const scenesNode = new USDNode( 'Scenes', 'Scope' );
		scenesNode.addMetadata( 'kind', '"sceneLibrary"' );
		root.addChild( scenesNode );

		const sceneName = 'Scene';
		const sceneNode = new USDNode( sceneName, 'Xform' );
		sceneNode.addMetadata( 'customData', [
			'bool preliminary_collidesWithEnvironment = 0',
			`string sceneName = "${sceneName}"`,
		] );
		sceneNode.addMetadata( 'sceneName', `"${sceneName}"` );
		if ( options.includeAnchoringProperties ) {

			sceneNode.addProperty(
				`token preliminary:anchoring:type = "${options.ar.anchoring.type}"`
			);
			sceneNode.addProperty(
				`token preliminary:planeAnchoring:alignment = "${options.ar.planeAnchoring.alignment}"`
			);

		}

		scenesNode.addChild( sceneNode );

		let output;

		const materials = {};
		const textures = {};

		buildHierarchy( scene, sceneNode, materials, usedNames, files, options );

		const materialsNode = buildMaterials(
			materials,
			textures,
			options.quickLookCompatible
		);

		output =
			buildHeader() +
			'\n' +
			root.toString() +
			'\n\n' +
			materialsNode.toString();

		files[ modelFileName ] = strToU8( output );
		output = null;

		for ( const id in textures ) {

			let texture = textures[ id ];

			if ( texture.isCompressedTexture === true ) {

				if ( this.textureUtils === null ) {

					throw new Error(
						'THREE.USDZExporter: setTextureUtils() must be called to process compressed textures.'
					);

				} else {

					texture = await this.textureUtils.decompress( texture );

				}

			}

			const canvas = imageToCanvas(
				texture.image,
				texture.flipY,
				options.maxTextureSize
			);
			const blob = await new Promise( ( resolve ) =>
				canvas.toBlob( resolve, 'image/png', 1 )
			);

			files[ `textures/Texture_${id}.png` ] = new Uint8Array(
				await blob.arrayBuffer()
			);

		}

		// 64 byte alignment
		// https://github.com/101arrowz/fflate/issues/39#issuecomment-777263109

		let offset = 0;

		for ( const filename in files ) {

			const file = files[ filename ];
			const headerSize = 34 + filename.length;

			offset += headerSize;

			const offsetMod64 = offset & 63;

			if ( offsetMod64 !== 4 ) {

				const padLength = 64 - offsetMod64;
				const padding = new Uint8Array( padLength );

				files[ filename ] = [ file, { extra: { 12345: padding } } ];

			}

			offset = file.length;

		}

		return zipSync( files, { level: 0 } );

	}
```
</details>

### `getName(object: any, namesSet: any): any`

**Parameters:**

- **`object`** `any`
- **`namesSet`** `any`

**Returns:** `any`

**Calls:**

- `name.replace`
- `/^[0-9]/.test`
- `namesSet.has`
- `namesSet.add`

<details><summary>Code</summary>

```typescript
function getName( object, namesSet ) {

	let name = object.name;
	name = name.replace( /[^A-Za-z0-9_]/g, '' );
	if ( /^[0-9]/.test( name ) ) {

		name = '_' + name;

	}

	if ( name === '' ) {

		if ( object.isCamera ) {

			name = 'Camera';

		} else {

			name = 'Object';

		}

	}

	if ( namesSet.has( name ) ) {

		name = name + '_' + object.id;

	}

	namesSet.add( name );

	return name;

}
```
</details>

### `imageToCanvas(image: any, flipY: any, maxTextureSize: any): HTMLCanvasElement`

**Parameters:**

- **`image`** `any`
- **`flipY`** `any`
- **`maxTextureSize`** `any`

**Returns:** `HTMLCanvasElement`

**Calls:**

- `Math.max`
- `document.createElement`
- `Math.min`
- `canvas.getContext`
- `context.translate`
- `context.scale`
- `context.drawImage`

**Internal Comments:**
```
// TODO: We should be able to do this in the UsdTransform2d?
```

<details><summary>Code</summary>

```typescript
function imageToCanvas( image, flipY, maxTextureSize ) {

	if (
		( typeof HTMLImageElement !== 'undefined' &&
			image instanceof HTMLImageElement ) ||
		( typeof HTMLCanvasElement !== 'undefined' &&
			image instanceof HTMLCanvasElement ) ||
		( typeof OffscreenCanvas !== 'undefined' &&
			image instanceof OffscreenCanvas ) ||
		( typeof ImageBitmap !== 'undefined' && image instanceof ImageBitmap )
	) {

		const scale = maxTextureSize / Math.max( image.width, image.height );

		const canvas = document.createElement( 'canvas' );
		canvas.width = image.width * Math.min( 1, scale );
		canvas.height = image.height * Math.min( 1, scale );

		const context = canvas.getContext( '2d' );

		// TODO: We should be able to do this in the UsdTransform2d?

		if ( flipY === true ) {

			context.translate( 0, canvas.height );
			context.scale( 1, - 1 );

		}

		context.drawImage( image, 0, 0, canvas.width, canvas.height );

		return canvas;

	} else {

		throw new Error(
			'THREE.USDZExporter: No valid image data found. Unable to process texture.'
		);

	}

}
```
</details>

### `buildHeader(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function buildHeader() {

	return `#usda 1.0
(
	customLayerData = {
		string creator = "Three.js USDZExporter"
	}
	defaultPrim = "Root"
	metersPerUnit = 1
	upAxis = "Y"
)
`;

}
```
</details>

### `buildHierarchy(object: any, parentNode: any, materials: any, usedNames: any, files: any, options: any): void`

**Parameters:**

- **`object`** `any`
- **`parentNode`** `any`
- **`materials`** `any`
- **`usedNames`** `any`
- **`files`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `buildMeshObject`
- `strToU8 (from ../libs/fflate.module.js)`
- `buildHeader`
- `meshObject.toString`
- `buildMesh`
- `console.warn`
- `buildCamera`
- `buildXform`
- `parentNode.addChild`
- `buildHierarchy`

<details><summary>Code</summary>

```typescript
function buildHierarchy( object, parentNode, materials, usedNames, files, options ) {

	for ( let i = 0, l = object.children.length; i < l; i ++ ) {

		const child = object.children[ i ];

		if ( child.visible === false && options.onlyVisible === true ) continue;

		let childNode;

		if ( child.isMesh ) {

			const geometry = child.geometry;
			const material = child.material;

			if ( material.isMeshStandardMaterial ) {

				const geometryFileName = 'geometries/Geometry_' + geometry.id + '.usda';

				if ( ! ( geometryFileName in files ) ) {

					const meshObject = buildMeshObject( geometry );
					files[ geometryFileName ] = strToU8(
						buildHeader() + '\n' + meshObject.toString()
					);

				}

				if ( ! ( material.uuid in materials ) ) {

					materials[ material.uuid ] = material;

				}

				childNode = buildMesh(
					child,
					geometry,
					materials[ material.uuid ],
					usedNames
				);

			} else {

				console.warn(
					'THREE.USDZExporter: Unsupported material type (USDZ only supports MeshStandardMaterial)',
					child
				);

			}

		} else if ( child.isCamera ) {

			childNode = buildCamera( child, usedNames );

		} else {

			childNode = buildXform( child, usedNames );

		}

		if ( childNode ) {

			parentNode.addChild( childNode );
			buildHierarchy( child, childNode, materials, usedNames, files, options );

		}

	}

}
```
</details>

### `buildXform(object: any, usedNames: any): USDNode`

**Parameters:**

- **`object`** `any`
- **`usedNames`** `any`

**Returns:** `USDNode`

**Calls:**

- `getName`
- `buildMatrix`
- `object.matrix.determinant`
- `console.warn`
- `node.addProperty`

<details><summary>Code</summary>

```typescript
function buildXform( object, usedNames ) {

	const name = getName( object, usedNames );
	const transform = buildMatrix( object.matrix );

	if ( object.matrix.determinant() < 0 ) {

		console.warn(
			'THREE.USDZExporter: USDZ does not support negative scales',
			object
		);

	}

	const node = new USDNode( name, 'Xform' );

	node.addProperty( `matrix4d xformOp:transform = ${transform}` );
	node.addProperty( 'uniform token[] xformOpOrder = ["xformOp:transform"]' );

	return node;

}
```
</details>

### `buildMesh(object: any, geometry: any, material: any, usedNames: any): USDNode`

**Parameters:**

- **`object`** `any`
- **`geometry`** `any`
- **`material`** `any`
- **`usedNames`** `any`

**Returns:** `USDNode`

**Calls:**

- `buildXform`
- `node.addMetadata`
- `node.addProperty`

<details><summary>Code</summary>

```typescript
function buildMesh( object, geometry, material, usedNames ) {

	const node = buildXform( object, usedNames );

	node.addMetadata(
		'prepend references',
		`@./geometries/Geometry_${geometry.id}.usda@</Geometry>`
	);
	node.addMetadata( 'prepend apiSchemas', '["MaterialBindingAPI"]' );

	node.addProperty(
		`rel material:binding = </Materials/Material_${material.id}>`
	);

	return node;

}
```
</details>

### `buildMatrix(matrix: any): string`

**Parameters:**

- **`matrix`** `any`

**Returns:** `string`

**Calls:**

- `buildMatrixRow`

<details><summary>Code</summary>

```typescript
function buildMatrix( matrix ) {

	const array = matrix.elements;

	return `( ${buildMatrixRow( array, 0 )}, ${buildMatrixRow(
		array,
		4
	)}, ${buildMatrixRow( array, 8 )}, ${buildMatrixRow( array, 12 )} )`;

}
```
</details>

### `buildMatrixRow(array: any, offset: any): string`

**Parameters:**

- **`array`** `any`
- **`offset`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function buildMatrixRow( array, offset ) {

	return `(${array[ offset + 0 ]}, ${array[ offset + 1 ]}, ${array[ offset + 2 ]}, ${
		array[ offset + 3 ]
	})`;

}
```
</details>

### `buildMeshObject(geometry: any): USDNode`

**Parameters:**

- **`geometry`** `any`

**Returns:** `USDNode`

**Calls:**

- `buildMeshNode`
- `node.addChild`

<details><summary>Code</summary>

```typescript
function buildMeshObject( geometry ) {

	const node = new USDNode( 'Geometry' );

	const meshNode = buildMeshNode( geometry );
	node.addChild( meshNode );

	return node;

}
```
</details>

### `buildMeshNode(geometry: any): USDNode`

**Parameters:**

- **`geometry`** `any`

**Returns:** `USDNode`

**Calls:**

- `node.addProperty`
- `buildMeshVertexCount`
- `buildMeshVertexIndices`
- `buildVector3Array`
- `buildVector2Array`

<details><summary>Code</summary>

```typescript
function buildMeshNode( geometry ) {

	const name = 'Geometry';
	const attributes = geometry.attributes;
	const count = attributes.position.count;

	const node = new USDNode( name, 'Mesh' );

	node.addProperty(
		`int[] faceVertexCounts = [${buildMeshVertexCount( geometry )}]`
	);
	node.addProperty(
		`int[] faceVertexIndices = [${buildMeshVertexIndices( geometry )}]`
	);
	node.addProperty(
		`normal3f[] normals = [${buildVector3Array( attributes.normal, count )}]`,
		[ 'interpolation = "vertex"' ]
	);
	node.addProperty(
		`point3f[] points = [${buildVector3Array( attributes.position, count )}]`
	);

	for ( let i = 0; i < 4; i ++ ) {

		const id = i > 0 ? i : '';
		const attribute = attributes[ 'uv' + id ];
		if ( attribute !== undefined ) {

			node.addProperty(
				`texCoord2f[] primvars:st${id} = [${buildVector2Array( attribute )}]`,
				[ 'interpolation = "vertex"' ]
			);

		}

	}

	const colorAttribute = attributes.color;
	if ( colorAttribute !== undefined ) {

		node.addProperty(
			`color3f[] primvars:displayColor = [${buildVector3Array(
				colorAttribute,
				count
			)}]`,
			[ 'interpolation = "vertex"' ]
		);

	}

	node.addProperty( 'uniform token subdivisionScheme = "none"' );

	return node;

}
```
</details>

### `buildMeshVertexCount(geometry: any): string`

**Parameters:**

- **`geometry`** `any`

**Returns:** `string`

**Calls:**

- `Array( count / 3 )
		.fill( 3 )
		.join`

<details><summary>Code</summary>

```typescript
function buildMeshVertexCount( geometry ) {

	const count =
		geometry.index !== null
			? geometry.index.count
			: geometry.attributes.position.count;

	return Array( count / 3 )
		.fill( 3 )
		.join( ', ' );

}
```
</details>

### `buildMeshVertexIndices(geometry: any): string`

**Parameters:**

- **`geometry`** `any`

**Returns:** `string`

**Calls:**

- `array.push`
- `index.getX`
- `array.join`

<details><summary>Code</summary>

```typescript
function buildMeshVertexIndices( geometry ) {

	const index = geometry.index;
	const array = [];

	if ( index !== null ) {

		for ( let i = 0; i < index.count; i ++ ) {

			array.push( index.getX( i ) );

		}

	} else {

		const length = geometry.attributes.position.count;

		for ( let i = 0; i < length; i ++ ) {

			array.push( i );

		}

	}

	return array.join( ', ' );

}
```
</details>

### `buildVector3Array(attribute: any, count: any): string`

**Parameters:**

- **`attribute`** `any`
- **`count`** `any`

**Returns:** `string`

**Calls:**

- `console.warn`
- `Array( count ).fill( '(0, 0, 0)' ).join`
- `attribute.getX`
- `attribute.getY`
- `attribute.getZ`
- `array.push`
- `x.toPrecision`
- `y.toPrecision`
- `z.toPrecision`
- `array.join`

<details><summary>Code</summary>

```typescript
function buildVector3Array( attribute, count ) {

	if ( attribute === undefined ) {

		console.warn( 'USDZExporter: Normals missing.' );
		return Array( count ).fill( '(0, 0, 0)' ).join( ', ' );

	}

	const array = [];

	for ( let i = 0; i < attribute.count; i ++ ) {

		const x = attribute.getX( i );
		const y = attribute.getY( i );
		const z = attribute.getZ( i );

		array.push(
			`(${x.toPrecision( PRECISION )}, ${y.toPrecision(
				PRECISION
			)}, ${z.toPrecision( PRECISION )})`
		);

	}

	return array.join( ', ' );

}
```
</details>

### `buildVector2Array(attribute: any): string`

**Parameters:**

- **`attribute`** `any`

**Returns:** `string`

**Calls:**

- `attribute.getX`
- `attribute.getY`
- `array.push`
- `x.toPrecision`
- `y.toPrecision`
- `array.join`

<details><summary>Code</summary>

```typescript
function buildVector2Array( attribute ) {

	const array = [];

	for ( let i = 0; i < attribute.count; i ++ ) {

		const x = attribute.getX( i );
		const y = attribute.getY( i );

		array.push(
			`(${x.toPrecision( PRECISION )}, ${1 - y.toPrecision( PRECISION )})`
		);

	}

	return array.join( ', ' );

}
```
</details>

### `buildMaterials(materials: any, textures: any, quickLookCompatible: boolean): USDNode`

**Parameters:**

- **`materials`** `any`
- **`textures`** `any`
- **`quickLookCompatible`** `boolean`

**Returns:** `USDNode`

**Calls:**

- `materialsNode.addChild`
- `buildMaterial`

<details><summary>Code</summary>

```typescript
function buildMaterials( materials, textures, quickLookCompatible = false ) {

	const materialsNode = new USDNode( 'Materials' );

	for ( const uuid in materials ) {

		const material = materials[ uuid ];

		materialsNode.addChild(
			buildMaterial( material, textures, quickLookCompatible )
		);

	}

	return materialsNode;

}
```
</details>

### `buildMaterial(material: any, textures: any, quickLookCompatible: boolean): USDNode`

**Parameters:**

- **`material`** `any`
- **`textures`** `any`
- **`quickLookCompatible`** `boolean`

**Returns:** `USDNode`

**Calls:**

- `texture.repeat.clone`
- `texture.offset.clone`
- `Math.sin`
- `Math.cos`
- `primvarReaderNode.addProperty`
- `transform2dNode.addProperty`
- `( rotation * ( 180 / Math.PI ) ).toFixed`
- `buildVector2`
- `textureNode.addProperty`
- `buildColor4`
- `console.warn`
- `previewSurfaceNode.addProperty`
- `buildTextureNodes`
- `textureNodes.forEach`
- `materialNode.addChild`
- `buildColor`
- `material.emissive.getHex`
- `materialNode.addProperty`

**Internal Comments:**
```
// https://graphics.pixar.com/usd/docs/UsdPreviewSurface-Proposal.html (x2)
// rotation is around the wrong point. after rotation we need to shift offset again so that we're rotating around the right spot (x2)
// texture coordinates start in the opposite corner, need to correct (x4)
// turns out QuickLook is buggy and interprets texture repeat inverted/applies operations in a different order.
// Apple Feedback: 	FB10036297 and FB11442287
// This is NOT correct yet in QuickLook, but comes close for a range of models. (x4)
// It becomes more incorrect the bigger the offset is (x4)
// results match glTF results exactly. verified correct in usdview. (x4)
```

<details><summary>Code</summary>

```typescript
function buildMaterial( material, textures, quickLookCompatible = false ) {

	// https://graphics.pixar.com/usd/docs/UsdPreviewSurface-Proposal.html

	const materialNode = new USDNode( `Material_${material.id}`, 'Material' );

	function buildTextureNodes( texture, mapType, color ) {

		const id = texture.source.id + '_' + texture.flipY;

		textures[ id ] = texture;

		const uv = texture.channel > 0 ? 'st' + texture.channel : 'st';

		const WRAPPINGS = {
			1000: 'repeat', // RepeatWrapping
			1001: 'clamp', // ClampToEdgeWrapping
			1002: 'mirror', // MirroredRepeatWrapping
		};

		const repeat = texture.repeat.clone();
		const offset = texture.offset.clone();
		const rotation = texture.rotation;

		// rotation is around the wrong point. after rotation we need to shift offset again so that we're rotating around the right spot
		const xRotationOffset = Math.sin( rotation );
		const yRotationOffset = Math.cos( rotation );

		// texture coordinates start in the opposite corner, need to correct
		offset.y = 1 - offset.y - repeat.y;

		// turns out QuickLook is buggy and interprets texture repeat inverted/applies operations in a different order.
		// Apple Feedback: 	FB10036297 and FB11442287
		if ( quickLookCompatible ) {

			// This is NOT correct yet in QuickLook, but comes close for a range of models.
			// It becomes more incorrect the bigger the offset is

			offset.x = offset.x / repeat.x;
			offset.y = offset.y / repeat.y;

			offset.x += xRotationOffset / repeat.x;
			offset.y += yRotationOffset - 1;

		} else {

			// results match glTF results exactly. verified correct in usdview.
			offset.x += xRotationOffset * repeat.x;
			offset.y += ( 1 - yRotationOffset ) * repeat.y;

		}

		const primvarReaderNode = new USDNode( `PrimvarReader_${mapType}`, 'Shader' );
		primvarReaderNode.addProperty(
			'uniform token info:id = "UsdPrimvarReader_float2"'
		);
		primvarReaderNode.addProperty( 'float2 inputs:fallback = (0.0, 0.0)' );
		primvarReaderNode.addProperty( `token inputs:varname = "${uv}"` );
		primvarReaderNode.addProperty( 'float2 outputs:result' );

		const transform2dNode = new USDNode( `Transform2d_${mapType}`, 'Shader' );
		transform2dNode.addProperty( 'uniform token info:id = "UsdTransform2d"' );
		transform2dNode.addProperty(
			`token inputs:in.connect = </Materials/Material_${material.id}/PrimvarReader_${mapType}.outputs:result>`
		);
		transform2dNode.addProperty(
			`float inputs:rotation = ${( rotation * ( 180 / Math.PI ) ).toFixed(
				PRECISION
			)}`
		);
		transform2dNode.addProperty(
			`float2 inputs:scale = ${buildVector2( repeat )}`
		);
		transform2dNode.addProperty(
			`float2 inputs:translation = ${buildVector2( offset )}`
		);
		transform2dNode.addProperty( 'float2 outputs:result' );

		const textureNode = new USDNode(
			`Texture_${texture.id}_${mapType}`,
			'Shader'
		);
		textureNode.addProperty( 'uniform token info:id = "UsdUVTexture"' );
		textureNode.addProperty( `asset inputs:file = @textures/Texture_${id}.png@` );
		textureNode.addProperty(
			`float2 inputs:st.connect = </Materials/Material_${material.id}/Transform2d_${mapType}.outputs:result>`
		);

		if ( color !== undefined ) {

			textureNode.addProperty( `float4 inputs:scale = ${buildColor4( color )}` );

		}

		textureNode.addProperty(
			`token inputs:sourceColorSpace = "${
				texture.colorSpace === NoColorSpace ? 'raw' : 'sRGB'
			}"`
		);
		textureNode.addProperty(
			`token inputs:wrapS = "${WRAPPINGS[ texture.wrapS ]}"`
		);
		textureNode.addProperty(
			`token inputs:wrapT = "${WRAPPINGS[ texture.wrapT ]}"`
		);
		textureNode.addProperty( 'float outputs:r' );
		textureNode.addProperty( 'float outputs:g' );
		textureNode.addProperty( 'float outputs:b' );
		textureNode.addProperty( 'float3 outputs:rgb' );

		if ( material.transparent || material.alphaTest > 0.0 ) {

			textureNode.addProperty( 'float outputs:a' );

		}

		return [ primvarReaderNode, transform2dNode, textureNode ];

	}

	if ( material.side === DoubleSide ) {

		console.warn(
			'THREE.USDZExporter: USDZ does not support double sided materials',
			material
		);

	}

	const previewSurfaceNode = new USDNode( 'PreviewSurface', 'Shader' );
	previewSurfaceNode.addProperty( 'uniform token info:id = "UsdPreviewSurface"' );

	if ( material.map !== null ) {

		previewSurfaceNode.addProperty(
			`color3f inputs:diffuseColor.connect = </Materials/Material_${material.id}/Texture_${material.map.id}_diffuse.outputs:rgb>`
		);

		if ( material.transparent ) {

			previewSurfaceNode.addProperty(
				`float inputs:opacity.connect = </Materials/Material_${material.id}/Texture_${material.map.id}_diffuse.outputs:a>`
			);

		} else if ( material.alphaTest > 0.0 ) {

			previewSurfaceNode.addProperty(
				`float inputs:opacity.connect = </Materials/Material_${material.id}/Texture_${material.map.id}_diffuse.outputs:a>`
			);
			previewSurfaceNode.addProperty(
				`float inputs:opacityThreshold = ${material.alphaTest}`
			);

		}

		const textureNodes = buildTextureNodes(
			material.map,
			'diffuse',
			material.color
		);
		textureNodes.forEach( ( node ) => materialNode.addChild( node ) );

	} else {

		previewSurfaceNode.addProperty(
			`color3f inputs:diffuseColor = ${buildColor( material.color )}`
		);

	}

	if ( material.emissiveMap !== null ) {

		previewSurfaceNode.addProperty(
			`color3f inputs:emissiveColor.connect = </Materials/Material_${material.id}/Texture_${material.emissiveMap.id}_emissive.outputs:rgb>`
		);

		const emissiveColor = new Color(
			material.emissive.r * material.emissiveIntensity,
			material.emissive.g * material.emissiveIntensity,
			material.emissive.b * material.emissiveIntensity
		);
		const textureNodes = buildTextureNodes(
			material.emissiveMap,
			'emissive',
			emissiveColor
		);
		textureNodes.forEach( ( node ) => materialNode.addChild( node ) );

	} else if ( material.emissive.getHex() > 0 ) {

		previewSurfaceNode.addProperty(
			`color3f inputs:emissiveColor = ${buildColor( material.emissive )}`
		);

	}

	if ( material.normalMap !== null ) {

		previewSurfaceNode.addProperty(
			`normal3f inputs:normal.connect = </Materials/Material_${material.id}/Texture_${material.normalMap.id}_normal.outputs:rgb>`
		);

		const textureNodes = buildTextureNodes( material.normalMap, 'normal' );
		textureNodes.forEach( ( node ) => materialNode.addChild( node ) );

	}

	if ( material.aoMap !== null ) {

		previewSurfaceNode.addProperty(
			`float inputs:occlusion.connect = </Materials/Material_${material.id}/Texture_${material.aoMap.id}_occlusion.outputs:r>`
		);

		const aoColor = new Color(
			material.aoMapIntensity,
			material.aoMapIntensity,
			material.aoMapIntensity
		);
		const textureNodes = buildTextureNodes(
			material.aoMap,
			'occlusion',
			aoColor
		);
		textureNodes.forEach( ( node ) => materialNode.addChild( node ) );

	}

	if ( material.roughnessMap !== null ) {

		previewSurfaceNode.addProperty(
			`float inputs:roughness.connect = </Materials/Material_${material.id}/Texture_${material.roughnessMap.id}_roughness.outputs:g>`
		);

		const roughnessColor = new Color(
			material.roughness,
			material.roughness,
			material.roughness
		);
		const textureNodes = buildTextureNodes(
			material.roughnessMap,
			'roughness',
			roughnessColor
		);
		textureNodes.forEach( ( node ) => materialNode.addChild( node ) );

	} else {

		previewSurfaceNode.addProperty(
			`float inputs:roughness = ${material.roughness}`
		);

	}

	if ( material.metalnessMap !== null ) {

		previewSurfaceNode.addProperty(
			`float inputs:metallic.connect = </Materials/Material_${material.id}/Texture_${material.metalnessMap.id}_metallic.outputs:b>`
		);

		const metalnessColor = new Color(
			material.metalness,
			material.metalness,
			material.metalness
		);
		const textureNodes = buildTextureNodes(
			material.metalnessMap,
			'metallic',
			metalnessColor
		);
		textureNodes.forEach( ( node ) => materialNode.addChild( node ) );

	} else {

		previewSurfaceNode.addProperty(
			`float inputs:metallic = ${material.metalness}`
		);

	}

	if ( material.alphaMap !== null ) {

		previewSurfaceNode.addProperty(
			`float inputs:opacity.connect = </Materials/Material_${material.id}/Texture_${material.alphaMap.id}_opacity.outputs:r>`
		);
		previewSurfaceNode.addProperty( 'float inputs:opacityThreshold = 0.0001' );

		const textureNodes = buildTextureNodes( material.alphaMap, 'opacity' );
		textureNodes.forEach( ( node ) => materialNode.addChild( node ) );

	} else {

		previewSurfaceNode.addProperty(
			`float inputs:opacity = ${material.opacity}`
		);

	}

	if ( material.isMeshPhysicalMaterial ) {

		if ( material.clearcoatMap !== null ) {

			previewSurfaceNode.addProperty(
				`float inputs:clearcoat.connect = </Materials/Material_${material.id}/Texture_${material.clearcoatMap.id}_clearcoat.outputs:r>`
			);

			const clearcoatColor = new Color(
				material.clearcoat,
				material.clearcoat,
				material.clearcoat
			);
			const textureNodes = buildTextureNodes(
				material.clearcoatMap,
				'clearcoat',
				clearcoatColor
			);
			textureNodes.forEach( ( node ) => materialNode.addChild( node ) );

		} else {

			previewSurfaceNode.addProperty(
				`float inputs:clearcoat = ${material.clearcoat}`
			);

		}

		if ( material.clearcoatRoughnessMap !== null ) {

			previewSurfaceNode.addProperty(
				`float inputs:clearcoatRoughness.connect = </Materials/Material_${material.id}/Texture_${material.clearcoatRoughnessMap.id}_clearcoatRoughness.outputs:g>`
			);

			const clearcoatRoughnessColor = new Color(
				material.clearcoatRoughness,
				material.clearcoatRoughness,
				material.clearcoatRoughness
			);
			const textureNodes = buildTextureNodes(
				material.clearcoatRoughnessMap,
				'clearcoatRoughness',
				clearcoatRoughnessColor
			);
			textureNodes.forEach( ( node ) => materialNode.addChild( node ) );

		} else {

			previewSurfaceNode.addProperty(
				`float inputs:clearcoatRoughness = ${material.clearcoatRoughness}`
			);

		}

		previewSurfaceNode.addProperty( `float inputs:ior = ${material.ior}` );

	}

	previewSurfaceNode.addProperty( 'int inputs:useSpecularWorkflow = 0' );
	previewSurfaceNode.addProperty( 'token outputs:surface' );

	materialNode.addChild( previewSurfaceNode );

	materialNode.addProperty(
		`token outputs:surface.connect = </Materials/Material_${material.id}/PreviewSurface.outputs:surface>`
	);

	return materialNode;

}
```
</details>

### `buildTextureNodes(texture: any, mapType: any, color: any): USDNode[]`

**Parameters:**

- **`texture`** `any`
- **`mapType`** `any`
- **`color`** `any`

**Returns:** `USDNode[]`

**Calls:**

- `texture.repeat.clone`
- `texture.offset.clone`
- `Math.sin`
- `Math.cos`
- `primvarReaderNode.addProperty`
- `transform2dNode.addProperty`
- `( rotation * ( 180 / Math.PI ) ).toFixed`
- `buildVector2`
- `textureNode.addProperty`
- `buildColor4`

**Internal Comments:**
```
// rotation is around the wrong point. after rotation we need to shift offset again so that we're rotating around the right spot (x2)
// texture coordinates start in the opposite corner, need to correct (x4)
// turns out QuickLook is buggy and interprets texture repeat inverted/applies operations in a different order.
// Apple Feedback: 	FB10036297 and FB11442287
// This is NOT correct yet in QuickLook, but comes close for a range of models. (x4)
// It becomes more incorrect the bigger the offset is (x4)
// results match glTF results exactly. verified correct in usdview. (x4)
```

<details><summary>Code</summary>

```typescript
function buildTextureNodes( texture, mapType, color ) {

		const id = texture.source.id + '_' + texture.flipY;

		textures[ id ] = texture;

		const uv = texture.channel > 0 ? 'st' + texture.channel : 'st';

		const WRAPPINGS = {
			1000: 'repeat', // RepeatWrapping
			1001: 'clamp', // ClampToEdgeWrapping
			1002: 'mirror', // MirroredRepeatWrapping
		};

		const repeat = texture.repeat.clone();
		const offset = texture.offset.clone();
		const rotation = texture.rotation;

		// rotation is around the wrong point. after rotation we need to shift offset again so that we're rotating around the right spot
		const xRotationOffset = Math.sin( rotation );
		const yRotationOffset = Math.cos( rotation );

		// texture coordinates start in the opposite corner, need to correct
		offset.y = 1 - offset.y - repeat.y;

		// turns out QuickLook is buggy and interprets texture repeat inverted/applies operations in a different order.
		// Apple Feedback: 	FB10036297 and FB11442287
		if ( quickLookCompatible ) {

			// This is NOT correct yet in QuickLook, but comes close for a range of models.
			// It becomes more incorrect the bigger the offset is

			offset.x = offset.x / repeat.x;
			offset.y = offset.y / repeat.y;

			offset.x += xRotationOffset / repeat.x;
			offset.y += yRotationOffset - 1;

		} else {

			// results match glTF results exactly. verified correct in usdview.
			offset.x += xRotationOffset * repeat.x;
			offset.y += ( 1 - yRotationOffset ) * repeat.y;

		}

		const primvarReaderNode = new USDNode( `PrimvarReader_${mapType}`, 'Shader' );
		primvarReaderNode.addProperty(
			'uniform token info:id = "UsdPrimvarReader_float2"'
		);
		primvarReaderNode.addProperty( 'float2 inputs:fallback = (0.0, 0.0)' );
		primvarReaderNode.addProperty( `token inputs:varname = "${uv}"` );
		primvarReaderNode.addProperty( 'float2 outputs:result' );

		const transform2dNode = new USDNode( `Transform2d_${mapType}`, 'Shader' );
		transform2dNode.addProperty( 'uniform token info:id = "UsdTransform2d"' );
		transform2dNode.addProperty(
			`token inputs:in.connect = </Materials/Material_${material.id}/PrimvarReader_${mapType}.outputs:result>`
		);
		transform2dNode.addProperty(
			`float inputs:rotation = ${( rotation * ( 180 / Math.PI ) ).toFixed(
				PRECISION
			)}`
		);
		transform2dNode.addProperty(
			`float2 inputs:scale = ${buildVector2( repeat )}`
		);
		transform2dNode.addProperty(
			`float2 inputs:translation = ${buildVector2( offset )}`
		);
		transform2dNode.addProperty( 'float2 outputs:result' );

		const textureNode = new USDNode(
			`Texture_${texture.id}_${mapType}`,
			'Shader'
		);
		textureNode.addProperty( 'uniform token info:id = "UsdUVTexture"' );
		textureNode.addProperty( `asset inputs:file = @textures/Texture_${id}.png@` );
		textureNode.addProperty(
			`float2 inputs:st.connect = </Materials/Material_${material.id}/Transform2d_${mapType}.outputs:result>`
		);

		if ( color !== undefined ) {

			textureNode.addProperty( `float4 inputs:scale = ${buildColor4( color )}` );

		}

		textureNode.addProperty(
			`token inputs:sourceColorSpace = "${
				texture.colorSpace === NoColorSpace ? 'raw' : 'sRGB'
			}"`
		);
		textureNode.addProperty(
			`token inputs:wrapS = "${WRAPPINGS[ texture.wrapS ]}"`
		);
		textureNode.addProperty(
			`token inputs:wrapT = "${WRAPPINGS[ texture.wrapT ]}"`
		);
		textureNode.addProperty( 'float outputs:r' );
		textureNode.addProperty( 'float outputs:g' );
		textureNode.addProperty( 'float outputs:b' );
		textureNode.addProperty( 'float3 outputs:rgb' );

		if ( material.transparent || material.alphaTest > 0.0 ) {

			textureNode.addProperty( 'float outputs:a' );

		}

		return [ primvarReaderNode, transform2dNode, textureNode ];

	}
```
</details>

### `buildColor(color: any): string`

**Parameters:**

- **`color`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function buildColor( color ) {

	return `(${color.r}, ${color.g}, ${color.b})`;

}
```
</details>

### `buildColor4(color: any): string`

**Parameters:**

- **`color`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function buildColor4( color ) {

	return `(${color.r}, ${color.g}, ${color.b}, 1.0)`;

}
```
</details>

### `buildVector2(vector: any): string`

**Parameters:**

- **`vector`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function buildVector2( vector ) {

	return `(${vector.x}, ${vector.y})`;

}
```
</details>

### `buildCamera(camera: any, usedNames: any): USDNode`

**Parameters:**

- **`camera`** `any`
- **`usedNames`** `any`

**Returns:** `USDNode`

**Calls:**

- `getName`
- `buildMatrix`
- `camera.matrix.determinant`
- `console.warn`
- `node.addProperty`
- `camera.near.toPrecision`
- `camera.far.toPrecision`
- `(
			( Math.abs( camera.left ) + Math.abs( camera.right ) ) *
			10
		).toPrecision`
- `Math.abs`
- `camera.getFilmWidth().toPrecision`
- `(
			( Math.abs( camera.top ) + Math.abs( camera.bottom ) ) *
			10
		).toPrecision`
- `camera.getFilmHeight().toPrecision`
- `camera.getFocalLength().toPrecision`
- `camera.focus.toPrecision`

<details><summary>Code</summary>

```typescript
function buildCamera( camera, usedNames ) {

	const name = getName( camera, usedNames );

	const transform = buildMatrix( camera.matrix );

	if ( camera.matrix.determinant() < 0 ) {

		console.warn(
			'THREE.USDZExporter: USDZ does not support negative scales',
			camera
		);

	}

	const node = new USDNode( name, 'Camera' );
	node.addProperty( `matrix4d xformOp:transform = ${transform}` );
	node.addProperty( 'uniform token[] xformOpOrder = ["xformOp:transform"]' );

	const projection = camera.isOrthographicCamera
		? 'orthographic'
		: 'perspective';
	node.addProperty( `token projection = "${projection}"` );

	const clippingRange = `(${camera.near.toPrecision(
		PRECISION
	)}, ${camera.far.toPrecision( PRECISION )})`;
	node.addProperty( `float2 clippingRange = ${clippingRange}` );

	let horizontalAperture;
	if ( camera.isOrthographicCamera ) {

		horizontalAperture = (
			( Math.abs( camera.left ) + Math.abs( camera.right ) ) *
			10
		).toPrecision( PRECISION );

	} else {

		horizontalAperture = camera.getFilmWidth().toPrecision( PRECISION );

	}

	node.addProperty( `float horizontalAperture = ${horizontalAperture}` );

	let verticalAperture;
	if ( camera.isOrthographicCamera ) {

		verticalAperture = (
			( Math.abs( camera.top ) + Math.abs( camera.bottom ) ) *
			10
		).toPrecision( PRECISION );

	} else {

		verticalAperture = camera.getFilmHeight().toPrecision( PRECISION );

	}

	node.addProperty( `float verticalAperture = ${verticalAperture}` );

	if ( camera.isPerspectiveCamera ) {

		const focalLength = camera.getFocalLength().toPrecision( PRECISION );
		node.addProperty( `float focalLength = ${focalLength}` );

		const focusDistance = camera.focus.toPrecision( PRECISION );
		node.addProperty( `float focusDistance = ${focusDistance}` );

	}

	return node;

}
```
</details>


---

## Classes

### `USDNode`

<details><summary>Class Code</summary>

```ts
class USDNode {

	constructor( name, type = '', metadata = [], properties = [] ) {

		this.name = name;
		this.type = type;
		this.metadata = metadata;
		this.properties = properties;
		this.children = [];

	}

	addMetadata( key, value ) {

		this.metadata.push( { key, value } );

	}

	addProperty( property, metadata = [] ) {

		this.properties.push( { property, metadata } );

	}

	addChild( child ) {

		this.children.push( child );

	}

	toString( indent = 0 ) {

		const pad = '\t'.repeat( indent );

		const formattedMetadata = this.metadata.map( ( item ) => {

			const key = item.key;
			const value = item.value;

			if ( Array.isArray( value ) ) {

				const lines = [];
				lines.push( `${key} = {` );
				value.forEach( ( line ) => {

					lines.push( `${pad}\t\t${line}` );

				} );
				lines.push( `${pad}\t}` );
				return lines.join( '\n' );

			} else {

				return `${key} = ${value}`;

			}

		} );

		const meta = formattedMetadata.length
			? ` (\n${formattedMetadata
				.map( ( l ) => `${pad}\t${l}` )
				.join( '\n' )}\n${pad})`
			: '';

		const properties = this.properties.map( ( l ) => {

			const property = l.property;
			const metadata = l.metadata.length
				? ` (\n${l.metadata.map( ( m ) => `${pad}\t\t${m}` ).join( '\n' )}\n${pad}\t)`
				: '';
			return `${pad}\t${property}${metadata}`;

		} );
		const children = this.children.map( ( c ) => c.toString( indent + 1 ) );

		const bodyLines = [];

		if ( properties.length > 0 ) {

			bodyLines.push( ...properties );

		}

		if ( children.length > 0 ) {

			if ( properties.length > 0 ) {

				bodyLines.push( '' );

			}

			for ( let i = 0; i < children.length; i ++ ) {

				bodyLines.push( children[ i ] );
				if ( i < children.length - 1 ) {

					bodyLines.push( '' );

				}

			}

		}

		const bodyContent = bodyLines.join( '\n' );

		const type = this.type ? this.type + ' ' : '';

		return `${pad}def ${type}"${this.name}"${meta}\n${pad}{\n${bodyContent}\n${pad}}`;

	}

}
```
</details>

#### Methods

##### `addMetadata(key: any, value: any): void`

<details><summary>Code</summary>

```ts
addMetadata( key, value ) {

		this.metadata.push( { key, value } );

	}
```
</details>

##### `addProperty(property: any, metadata: any[]): void`

<details><summary>Code</summary>

```ts
addProperty( property, metadata = [] ) {

		this.properties.push( { property, metadata } );

	}
```
</details>

##### `addChild(child: any): void`

<details><summary>Code</summary>

```ts
addChild( child ) {

		this.children.push( child );

	}
```
</details>

##### `toString(indent: number): string`

<details><summary>Code</summary>

```ts
toString( indent = 0 ) {

		const pad = '\t'.repeat( indent );

		const formattedMetadata = this.metadata.map( ( item ) => {

			const key = item.key;
			const value = item.value;

			if ( Array.isArray( value ) ) {

				const lines = [];
				lines.push( `${key} = {` );
				value.forEach( ( line ) => {

					lines.push( `${pad}\t\t${line}` );

				} );
				lines.push( `${pad}\t}` );
				return lines.join( '\n' );

			} else {

				return `${key} = ${value}`;

			}

		} );

		const meta = formattedMetadata.length
			? ` (\n${formattedMetadata
				.map( ( l ) => `${pad}\t${l}` )
				.join( '\n' )}\n${pad})`
			: '';

		const properties = this.properties.map( ( l ) => {

			const property = l.property;
			const metadata = l.metadata.length
				? ` (\n${l.metadata.map( ( m ) => `${pad}\t\t${m}` ).join( '\n' )}\n${pad}\t)`
				: '';
			return `${pad}\t${property}${metadata}`;

		} );
		const children = this.children.map( ( c ) => c.toString( indent + 1 ) );

		const bodyLines = [];

		if ( properties.length > 0 ) {

			bodyLines.push( ...properties );

		}

		if ( children.length > 0 ) {

			if ( properties.length > 0 ) {

				bodyLines.push( '' );

			}

			for ( let i = 0; i < children.length; i ++ ) {

				bodyLines.push( children[ i ] );
				if ( i < children.length - 1 ) {

					bodyLines.push( '' );

				}

			}

		}

		const bodyContent = bodyLines.join( '\n' );

		const type = this.type ? this.type + ' ' : '';

		return `${pad}def ${type}"${this.name}"${meta}\n${pad}{\n${bodyContent}\n${pad}}`;

	}
```
</details>

### `USDZExporter`

<details><summary>Class Code</summary>

```ts
class USDZExporter {

	/**
	 * Constructs a new USDZ exporter.
	 */
	constructor() {

		/**
		 * A reference to a texture utils module.
		 *
		 * @type {?(WebGLTextureUtils|WebGPUTextureUtils)}
		 * @default null
		 */
		this.textureUtils = null;

	}

	/**
	 * Sets the texture utils for this exporter. Only relevant when compressed textures have to be exported.
	 *
	 * Depending on whether you use {@link WebGLRenderer} or {@link WebGPURenderer}, you must inject the
	 * corresponding texture utils {@link WebGLTextureUtils} or {@link WebGPUTextureUtils}.
	 *
	 * @param {WebGLTextureUtils|WebGPUTextureUtils} utils - The texture utils.
	 */
	setTextureUtils( utils ) {

		this.textureUtils = utils;

	}

	/**
	 * Parse the given 3D object and generates the USDZ output.
	 *
	 * @param {Object3D} scene - The 3D object to export.
	 * @param {USDZExporter~OnDone} onDone - A callback function that is executed when the export has finished.
	 * @param {USDZExporter~OnError} onError - A callback function that is executed when an error happens.
	 * @param {USDZExporter~Options} options - The export options.
	 */
	parse( scene, onDone, onError, options ) {

		this.parseAsync( scene, options ).then( onDone ).catch( onError );

	}

	/**
	 * Async version of {@link USDZExporter#parse}.
	 *
	 * @async
	 * @param {Object3D} scene - The 3D object to export.
	 * @param {USDZExporter~Options} options - The export options.
	 * @return {Promise<ArrayBuffer>} A Promise that resolved with the exported USDZ data.
	 */
	async parseAsync( scene, options = {} ) {

		options = Object.assign(
			{
				ar: {
					anchoring: { type: 'plane' },
					planeAnchoring: { alignment: 'horizontal' },
				},
				includeAnchoringProperties: true,
				onlyVisible: true,
				quickLookCompatible: false,
				maxTextureSize: 1024,
			},
			options
		);

		const usedNames = new Set();

		const files = {};
		const modelFileName = 'model.usda';

		// model file should be first in USDZ archive so we init it here
		files[ modelFileName ] = null;

		const root = new USDNode( 'Root', 'Xform' );
		const scenesNode = new USDNode( 'Scenes', 'Scope' );
		scenesNode.addMetadata( 'kind', '"sceneLibrary"' );
		root.addChild( scenesNode );

		const sceneName = 'Scene';
		const sceneNode = new USDNode( sceneName, 'Xform' );
		sceneNode.addMetadata( 'customData', [
			'bool preliminary_collidesWithEnvironment = 0',
			`string sceneName = "${sceneName}"`,
		] );
		sceneNode.addMetadata( 'sceneName', `"${sceneName}"` );
		if ( options.includeAnchoringProperties ) {

			sceneNode.addProperty(
				`token preliminary:anchoring:type = "${options.ar.anchoring.type}"`
			);
			sceneNode.addProperty(
				`token preliminary:planeAnchoring:alignment = "${options.ar.planeAnchoring.alignment}"`
			);

		}

		scenesNode.addChild( sceneNode );

		let output;

		const materials = {};
		const textures = {};

		buildHierarchy( scene, sceneNode, materials, usedNames, files, options );

		const materialsNode = buildMaterials(
			materials,
			textures,
			options.quickLookCompatible
		);

		output =
			buildHeader() +
			'\n' +
			root.toString() +
			'\n\n' +
			materialsNode.toString();

		files[ modelFileName ] = strToU8( output );
		output = null;

		for ( const id in textures ) {

			let texture = textures[ id ];

			if ( texture.isCompressedTexture === true ) {

				if ( this.textureUtils === null ) {

					throw new Error(
						'THREE.USDZExporter: setTextureUtils() must be called to process compressed textures.'
					);

				} else {

					texture = await this.textureUtils.decompress( texture );

				}

			}

			const canvas = imageToCanvas(
				texture.image,
				texture.flipY,
				options.maxTextureSize
			);
			const blob = await new Promise( ( resolve ) =>
				canvas.toBlob( resolve, 'image/png', 1 )
			);

			files[ `textures/Texture_${id}.png` ] = new Uint8Array(
				await blob.arrayBuffer()
			);

		}

		// 64 byte alignment
		// https://github.com/101arrowz/fflate/issues/39#issuecomment-777263109

		let offset = 0;

		for ( const filename in files ) {

			const file = files[ filename ];
			const headerSize = 34 + filename.length;

			offset += headerSize;

			const offsetMod64 = offset & 63;

			if ( offsetMod64 !== 4 ) {

				const padLength = 64 - offsetMod64;
				const padding = new Uint8Array( padLength );

				files[ filename ] = [ file, { extra: { 12345: padding } } ];

			}

			offset = file.length;

		}

		return zipSync( files, { level: 0 } );

	}

}
```
</details>

#### Methods

##### `setTextureUtils(utils: any): void`

<details><summary>Code</summary>

```ts
setTextureUtils( utils ) {

		this.textureUtils = utils;

	}
```
</details>

##### `parse(scene: Object3D, onDone: any, onError: any, options: any): void`

<details><summary>Code</summary>

```ts
parse( scene, onDone, onError, options ) {

		this.parseAsync( scene, options ).then( onDone ).catch( onError );

	}
```
</details>

##### `parseAsync(scene: Object3D, options: {}): Promise<ArrayBuffer>`

<details><summary>Code</summary>

```ts
async parseAsync( scene, options = {} ) {

		options = Object.assign(
			{
				ar: {
					anchoring: { type: 'plane' },
					planeAnchoring: { alignment: 'horizontal' },
				},
				includeAnchoringProperties: true,
				onlyVisible: true,
				quickLookCompatible: false,
				maxTextureSize: 1024,
			},
			options
		);

		const usedNames = new Set();

		const files = {};
		const modelFileName = 'model.usda';

		// model file should be first in USDZ archive so we init it here
		files[ modelFileName ] = null;

		const root = new USDNode( 'Root', 'Xform' );
		const scenesNode = new USDNode( 'Scenes', 'Scope' );
		scenesNode.addMetadata( 'kind', '"sceneLibrary"' );
		root.addChild( scenesNode );

		const sceneName = 'Scene';
		const sceneNode = new USDNode( sceneName, 'Xform' );
		sceneNode.addMetadata( 'customData', [
			'bool preliminary_collidesWithEnvironment = 0',
			`string sceneName = "${sceneName}"`,
		] );
		sceneNode.addMetadata( 'sceneName', `"${sceneName}"` );
		if ( options.includeAnchoringProperties ) {

			sceneNode.addProperty(
				`token preliminary:anchoring:type = "${options.ar.anchoring.type}"`
			);
			sceneNode.addProperty(
				`token preliminary:planeAnchoring:alignment = "${options.ar.planeAnchoring.alignment}"`
			);

		}

		scenesNode.addChild( sceneNode );

		let output;

		const materials = {};
		const textures = {};

		buildHierarchy( scene, sceneNode, materials, usedNames, files, options );

		const materialsNode = buildMaterials(
			materials,
			textures,
			options.quickLookCompatible
		);

		output =
			buildHeader() +
			'\n' +
			root.toString() +
			'\n\n' +
			materialsNode.toString();

		files[ modelFileName ] = strToU8( output );
		output = null;

		for ( const id in textures ) {

			let texture = textures[ id ];

			if ( texture.isCompressedTexture === true ) {

				if ( this.textureUtils === null ) {

					throw new Error(
						'THREE.USDZExporter: setTextureUtils() must be called to process compressed textures.'
					);

				} else {

					texture = await this.textureUtils.decompress( texture );

				}

			}

			const canvas = imageToCanvas(
				texture.image,
				texture.flipY,
				options.maxTextureSize
			);
			const blob = await new Promise( ( resolve ) =>
				canvas.toBlob( resolve, 'image/png', 1 )
			);

			files[ `textures/Texture_${id}.png` ] = new Uint8Array(
				await blob.arrayBuffer()
			);

		}

		// 64 byte alignment
		// https://github.com/101arrowz/fflate/issues/39#issuecomment-777263109

		let offset = 0;

		for ( const filename in files ) {

			const file = files[ filename ];
			const headerSize = 34 + filename.length;

			offset += headerSize;

			const offsetMod64 = offset & 63;

			if ( offsetMod64 !== 4 ) {

				const padLength = 64 - offsetMod64;
				const padding = new Uint8Array( padLength );

				files[ filename ] = [ file, { extra: { 12345: padding } } ];

			}

			offset = file.length;

		}

		return zipSync( files, { level: 0 } );

	}
```
</details>


---