[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MaterialXLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 27 |
| 🧱 Classes | 4 |
| 📦 Imports | 93 |
| 📊 Variables & Constants | 48 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/MaterialXLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FileLoader` | `three/webgpu` |
| `Loader` | `three/webgpu` |
| `TextureLoader` | `three/webgpu` |
| `RepeatWrapping` | `three/webgpu` |
| `MeshBasicNodeMaterial` | `three/webgpu` |
| `MeshPhysicalNodeMaterial` | `three/webgpu` |
| `DoubleSide` | `three/webgpu` |
| `float` | `three/tsl` |
| `bool` | `three/tsl` |
| `int` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `vec4` | `three/tsl` |
| `color` | `three/tsl` |
| `texture` | `three/tsl` |
| `positionLocal` | `three/tsl` |
| `positionWorld` | `three/tsl` |
| `uv` | `three/tsl` |
| `vertexColor` | `three/tsl` |
| `normalLocal` | `three/tsl` |
| `normalWorld` | `three/tsl` |
| `tangentLocal` | `three/tsl` |
| `tangentWorld` | `three/tsl` |
| `mul` | `three/tsl` |
| `abs` | `three/tsl` |
| `sign` | `three/tsl` |
| `floor` | `three/tsl` |
| `ceil` | `three/tsl` |
| `round` | `three/tsl` |
| `sin` | `three/tsl` |
| `cos` | `three/tsl` |
| `tan` | `three/tsl` |
| `asin` | `three/tsl` |
| `acos` | `three/tsl` |
| `sqrt` | `three/tsl` |
| `exp` | `three/tsl` |
| `clamp` | `three/tsl` |
| `min` | `three/tsl` |
| `max` | `three/tsl` |
| `normalize` | `three/tsl` |
| `length` | `three/tsl` |
| `dot` | `three/tsl` |
| `cross` | `three/tsl` |
| `normalMap` | `three/tsl` |
| `remap` | `three/tsl` |
| `smoothstep` | `three/tsl` |
| `luminance` | `three/tsl` |
| `mx_rgbtohsv` | `three/tsl` |
| `mx_hsvtorgb` | `three/tsl` |
| `mix` | `three/tsl` |
| `saturation` | `three/tsl` |
| `transpose` | `three/tsl` |
| `determinant` | `three/tsl` |
| `inverse` | `three/tsl` |
| `log` | `three/tsl` |
| `reflect` | `three/tsl` |
| `refract` | `three/tsl` |
| `element` | `three/tsl` |
| `mx_ramplr` | `three/tsl` |
| `mx_ramptb` | `three/tsl` |
| `mx_splitlr` | `three/tsl` |
| `mx_splittb` | `three/tsl` |
| `mx_fractal_noise_float` | `three/tsl` |
| `mx_noise_float` | `three/tsl` |
| `mx_cell_noise_float` | `three/tsl` |
| `mx_worley_noise_float` | `three/tsl` |
| `mx_transform_uv` | `three/tsl` |
| `mx_safepower` | `three/tsl` |
| `mx_contrast` | `three/tsl` |
| `mx_srgb_texture_to_lin_rec709` | `three/tsl` |
| `mx_add` | `three/tsl` |
| `mx_atan2` | `three/tsl` |
| `mx_divide` | `three/tsl` |
| `mx_modulo` | `three/tsl` |
| `mx_multiply` | `three/tsl` |
| `mx_power` | `three/tsl` |
| `mx_subtract` | `three/tsl` |
| `mx_timer` | `three/tsl` |
| `mx_frame` | `three/tsl` |
| `mat3` | `three/tsl` |
| `mx_ramp4` | `three/tsl` |
| `mx_invert` | `three/tsl` |
| `mx_ifgreater` | `three/tsl` |
| `mx_ifgreatereq` | `three/tsl` |
| `mx_ifequal` | `three/tsl` |
| `distance` | `three/tsl` |
| `mx_separate` | `three/tsl` |
| `mx_place2d` | `three/tsl` |
| `mx_rotate2d` | `three/tsl` |
| `mx_rotate3d` | `three/tsl` |
| `mx_heighttonormal` | `three/tsl` |
| `mx_unifiednoise2d` | `three/tsl` |
| `mx_unifiednoise3d` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `colorSpaceLib` | `{ mx_srgb_texture_to_lin_rec709: any; }` | let/var | `{ mx_srgb_texture_to_lin_rec709 }` | ✗ |
| `MXElements` | `MXElement[]` | let/var | `[ // << Math >> new MXElement( 'add', mx_add, [ 'in1', 'in2' ] ), new MXEleme...` | ✗ |
| `MtlXLibrary` | `{}` | let/var | `{}` | ✗ |
| `nodeX` | `this` | let/var | `this` | ✗ |
| `nodeX` | `this` | let/var | `this` | ✗ |
| `referencePath` | `any` | let/var | `null` | ✗ |
| `nodeName` | `string` | let/var | ``mx_${ csSource }_to_${ csTarget }`` | ✗ |
| `filePrefix` | `any` | let/var | `this.getRecursiveAttribute( 'fileprefix' ) \|\| ''` | ✗ |
| `loader` | `any` | let/var | `this.materialX.textureLoader` | ✗ |
| `uri` | `any` | let/var | `filePrefix + this.value` | ✗ |
| `nodeClass` | `any` | let/var | `null` | ✗ |
| `node` | `any` | let/var | `this.node` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `type` | `any` | let/var | `this.type` | ✗ |
| `element` | `any` | let/var | `this.element` | ✗ |
| `index` | `number` | let/var | `indexNode ? parseInt( indexNode.value ) : 0` | ✗ |
| `index` | `number` | let/var | `indexNode ? parseInt( indexNode.value ) : 0` | ✗ |
| `nodeElement` | `any` | let/var | `MtlXLibrary[ element ]` | ✗ |
| `nodes` | `{}` | let/var | `{}` | ✗ |
| `nodes` | `any[]` | let/var | `[]` | ✗ |
| `vector` | `any[]` | let/var | `[]` | ✗ |
| `colorNode` | `any` | let/var | `null` | ✗ |
| `opacityNode` | `any` | let/var | `null` | ✗ |
| `roughnessNode` | `any` | let/var | `null` | ✗ |
| `metalnessNode` | `any` | let/var | `null` | ✗ |
| `specularIntensityNode` | `any` | let/var | `null` | ✗ |
| `specularColorNode` | `any` | let/var | `null` | ✗ |
| `iorNode` | `any` | let/var | `null` | ✗ |
| `anisotropyNode` | `any` | let/var | `null` | ✗ |
| `anisotropyRotationNode` | `any` | let/var | `null` | ✗ |
| `transmissionNode` | `any` | let/var | `null` | ✗ |
| `transmissionColorNode` | `any` | let/var | `null` | ✗ |
| `thinFilmThicknessNode` | `any` | let/var | `null` | ✗ |
| `thinFilmIorNode` | `any` | let/var | `null` | ✗ |
| `sheenNode` | `any` | let/var | `null` | ✗ |
| `sheenColorNode` | `any` | let/var | `null` | ✗ |
| `sheenRoughnessNode` | `any` | let/var | `null` | ✗ |
| `clearcoatNode` | `any` | let/var | `null` | ✗ |
| `clearcoatRoughnessNode` | `any` | let/var | `null` | ✗ |
| `normalNode` | `any` | let/var | `null` | ✗ |
| `emissiveNode` | `any` | let/var | `null` | ✗ |
| `element` | `any` | let/var | `this.element` | ✗ |
| `material` | `any` | let/var | `new MeshBasicNodeMaterial()` | ✗ |
| `material` | `any` | let/var | `new MeshPhysicalNodeMaterial()` | ✗ |
| `materials` | `{}` | let/var | `{}` | ✗ |
| `isUnlit` | `boolean` | let/var | `true` | ✗ |
| `materialXNode` | `MaterialXNode` | let/var | `new MaterialXNode( this, nodeXML, nodePath )` | ✗ |
| `rootXML` | `HTMLElement` | let/var | `new DOMParser().parseFromString( text, 'application/xml' ).documentElement` | ✗ |


---

## Functions

### `MaterialXLoader.load(url: string, onLoad: (arg0: { [x: string]: NodeMaterial; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): MaterialXLoader`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded MaterialX asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Object<string,NodeMaterial>)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {MaterialXLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { [x: string]: NodeMaterial; }) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `MaterialXLoader`

**Calls:**

- `onError`
- `console.error`
- `new FileLoader( this.manager )
			.setPath( this.path )
			.load`
- `onLoad`
- `this.parse`
- `_onError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const _onError = function ( e ) {

			if ( onError ) {

				onError( e );

			} else {

				console.error( e );

			}

		};

		new FileLoader( this.manager )
			.setPath( this.path )
			.load( url, async ( text ) => {

				try {

					onLoad( this.parse( text ) );

				} catch ( e ) {

					_onError( e );

				}

			}, onProgress, _onError );

		return this;

	}
```
</details>

### `MaterialXLoader.parse(text: string): { [x: string]: NodeMaterial; }`

**JSDoc:**
```typescript
/**
	 * Parses the given MaterialX data and returns the resulting materials.
	 *
	 * Supported standard_surface inputs:
	 * - base, base_color: Base color/albedo
	 * - opacity: Alpha/transparency
	 * - specular_roughness: Surface roughness
	 * - metalness: Metallic property
	 * - specular: Specular reflection intensity
	 * - specular_color: Specular reflection color
	 * - ior: Index of refraction
	 * - specular_anisotropy, specular_rotation: Anisotropic reflection
	 * - transmission, transmission_color: Transmission properties
	 * - thin_film_thickness, thin_film_ior: Thin film interference
	 * - sheen, sheen_color, sheen_roughness: Sheen properties
	 * - normal: Normal map
	 * - coat, coat_roughness, coat_color: Clearcoat properties
	 * - emission, emissionColor: Emission properties
	 *
	 * @param {string} text - The raw MaterialX data as a string.
	 * @return {Object<string,NodeMaterial>} A dictionary holding the parse node materials.
	 */
```

**Parameters:**

- **`text`** `string`

**Returns:** `{ [x: string]: NodeMaterial; }`

**Calls:**

- `new MaterialX( this.manager, this.path ).parse`

<details><summary>Code</summary>

```typescript
parse( text ) {

		return new MaterialX( this.manager, this.path ).parse( text );

	}
```
</details>

### `_onError(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `onError`
- `console.error`

<details><summary>Code</summary>

```typescript
function ( e ) {

			if ( onError ) {

				onError( e );

			} else {

				console.error( e );

			}

		}
```
</details>

### `MaterialXNode.getNodeGraph(): this`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
getNodeGraph() {

		let nodeX = this;

		while ( nodeX !== null ) {

			if ( nodeX.element === 'nodegraph' ) {

				break;

			}

			nodeX = nodeX.parent;

		}

		return nodeX;

	}
```
</details>

### `MaterialXNode.getRoot(): this`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
getRoot() {

		let nodeX = this;

		while ( nodeX.parent !== null ) {

			nodeX = nodeX.parent;

		}

		return nodeX;

	}
```
</details>

### `MaterialXNode.getColorSpaceNode(): any`

**Returns:** `any`

**Calls:**

- `this.getAttribute`
- `this.getRoot().getAttribute`

<details><summary>Code</summary>

```typescript
getColorSpaceNode() {

		const csSource = this.getAttribute( 'colorspace' );
		const csTarget = this.getRoot().getAttribute( 'colorspace' );

		const nodeName = `mx_${ csSource }_to_${ csTarget }`;

		return colorSpaceLib[ nodeName ];

	}
```
</details>

### `MaterialXNode.getTexture(): any`

**Returns:** `any`

**Calls:**

- `this.getRecursiveAttribute`
- `this.materialX.manager.getHandler`
- `loader.load`

<details><summary>Code</summary>

```typescript
getTexture() {

		const filePrefix = this.getRecursiveAttribute( 'fileprefix' ) || '';

		let loader = this.materialX.textureLoader;
		const uri = filePrefix + this.value;

		if ( uri ) {

			const handler = this.materialX.manager.getHandler( uri );
			if ( handler !== null ) loader = handler;

		}

		const texture = loader.load( uri );
		texture.wrapS = texture.wrapT = RepeatWrapping;
		texture.flipY = false;

		return texture;

	}
```
</details>

### `MaterialXNode.getClassFromType(type: any): any`

**Parameters:**

- **`type`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getClassFromType( type ) {

		let nodeClass = null;

		if ( type === 'integer' ) nodeClass = int;
		else if ( type === 'float' ) nodeClass = float;
		else if ( type === 'vector2' ) nodeClass = vec2;
		else if ( type === 'vector3' ) nodeClass = vec3;
		else if ( type === 'vector4' || type === 'color4' ) nodeClass = vec4;
		else if ( type === 'color3' ) nodeClass = color;
		else if ( type === 'boolean' ) nodeClass = bool;

		return nodeClass;

	}
```
</details>

### `MaterialXNode.getNode(out: any): any`

**Parameters:**

- **`out`** `any`

**Returns:** `any`

**Calls:**

- `this.getAttribute`
- `/^UV(\d+)$/.test`
- `parseInt`
- `defaultGeomProp.match`
- `uv (from three/tsl)`
- `out.startsWith`
- `this.getNodeByName`
- `mx_separate (from three/tsl)`
- `this.getClassFromType`
- `nodeClass`
- `this.getVector`
- `this.materialX.getMaterialXNode( this.referencePath ).getNode`
- `this.getChildByName`
- `vertexColor (from three/tsl)`
- `file.getTexture`
- `mx_transform_uv (from three/tsl)`
- `this.getNodesByNames`
- `texture (from three/tsl)`
- `file.getColorSpaceNode`
- `colorSpaceNode`
- `new XMLSerializer().serializeToString`
- `nodeElement.nodeFunc`
- `console.warn`
- `float (from three/tsl)`
- `nodeToTypeClass`

**Internal Comments:**
```
// Handle <input name="texcoord" type="vector2" ... />
// Try to get index from defaultgeomprop (e.g., "UV0" => 0) (x2)
// Multi-output support for separate/separate3
// (x5)
```

<details><summary>Code</summary>

```typescript
getNode( out = null ) {

		let node = this.node;

		if ( node !== null && out === null ) {

			return node;

		}

		// Handle <input name="texcoord" type="vector2" ... />
		if (
			this.element === 'input' &&
			this.name === 'texcoord' &&
			this.type === 'vector2'
		) {

			// Try to get index from defaultgeomprop (e.g., "UV0" => 0)
			let index = 0;
			const defaultGeomProp = this.getAttribute( 'defaultgeomprop' );
			if ( defaultGeomProp && /^UV(\d+)$/.test( defaultGeomProp ) ) {

				index = parseInt( defaultGeomProp.match( /^UV(\d+)$/ )[ 1 ], 10 );

			}

			node = uv( index );

		}

		// Multi-output support for separate/separate3
		if (
			( this.element === 'separate3' || this.element === 'separate2' || this.element === 'separate4' ) &&
			out && typeof out === 'string' && out.startsWith( 'out' )
		) {

			const inNode = this.getNodeByName( 'in' );
			return mx_separate( inNode, out );

		}

		//

		const type = this.type;

		if ( this.isConst ) {

			const nodeClass = this.getClassFromType( type );

			node = nodeClass( ...this.getVector() );

		} else if ( this.hasReference ) {

			if ( this.element === 'output' && this.output && out === null ) {

				out = this.output;

			}

			node = this.materialX.getMaterialXNode( this.referencePath ).getNode( out );

		} else {

			const element = this.element;

			if ( element === 'convert' ) {

				const nodeClass = this.getClassFromType( type );

				node = nodeClass( this.getNodeByName( 'in' ) );

			} else if ( element === 'constant' ) {

				node = this.getNodeByName( 'value' );

			} else if ( element === 'position' ) {

				const space = this.getAttribute( 'space' );
				node = space === 'world' ? positionWorld : positionLocal;

			} else if ( element === 'normal' ) {

				const space = this.getAttribute( 'space' );
				node = space === 'world' ? normalWorld : normalLocal;

			} else if ( element === 'tangent' ) {

				const space = this.getAttribute( 'space' );
				node = space === 'world' ? tangentWorld : tangentLocal;

			} else if ( element === 'texcoord' ) {

				const indexNode = this.getChildByName( 'index' );
				const index = indexNode ? parseInt( indexNode.value ) : 0;

				node = uv( index );

			} else if ( element === 'geomcolor' ) {

				const indexNode = this.getChildByName( 'index' );
				const index = indexNode ? parseInt( indexNode.value ) : 0;

				node = vertexColor( index );

			} else if ( element === 'tiledimage' ) {

				const file = this.getChildByName( 'file' );

				const textureFile = file.getTexture();
				const uvTiling = mx_transform_uv( ...this.getNodesByNames( [ 'uvtiling', 'uvoffset' ] ) );

				node = texture( textureFile, uvTiling );

				const colorSpaceNode = file.getColorSpaceNode();

				if ( colorSpaceNode ) {

					node = colorSpaceNode( node );

				}

			} else if ( element === 'image' ) {

				const file = this.getChildByName( 'file' );
				const uvNode = this.getNodeByName( 'texcoord' );

				const textureFile = file.getTexture();

				node = texture( textureFile, uvNode );

				const colorSpaceNode = file.getColorSpaceNode();

				if ( colorSpaceNode ) {

					node = colorSpaceNode( node );

				}

			} else if ( MtlXLibrary[ element ] !== undefined ) {

				const nodeElement = MtlXLibrary[ element ];

				if ( ! nodeElement ) {

					throw new Error( `THREE.MaterialXLoader: Unexpected node ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );

				}

				if ( ! nodeElement.nodeFunc ) {

					throw new Error( `THREE.MaterialXLoader: Unexpected node 2 ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );

				}

				if ( out !== null ) {

					node = nodeElement.nodeFunc( ...this.getNodesByNames( ...nodeElement.params ), out );

				} else {

					node = nodeElement.nodeFunc( ...this.getNodesByNames( ...nodeElement.params ) );

				}

			}

		}

		//

		if ( node === null ) {

			console.warn( `THREE.MaterialXLoader: Unexpected node ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );

			node = float( 0 );

		}

		//

		const nodeToTypeClass = this.getClassFromType( type );

		if ( nodeToTypeClass !== null ) {

			node = nodeToTypeClass( node );

		} else {

			console.warn( `THREE.MaterialXLoader: Unexpected node ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );
			node = float( 0 );

		}

		node.name = this.name;

		this.node = node;

		return node;

	}
```
</details>

### `MaterialXNode.getChildByName(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getChildByName( name ) {

		for ( const input of this.children ) {

			if ( input.name === name ) {

				return input;

			}

		}

	}
```
</details>

### `MaterialXNode.getNodes(): {}`

**Returns:** `{}`

**Calls:**

- `input.getNode`

<details><summary>Code</summary>

```typescript
getNodes() {

		const nodes = {};

		for ( const input of this.children ) {

			const node = input.getNode();

			nodes[ node.name ] = node;

		}

		return nodes;

	}
```
</details>

### `MaterialXNode.getNodeByName(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.getChildByName`
- `child.getNode`

<details><summary>Code</summary>

```typescript
getNodeByName( name ) {

		const child = this.getChildByName( name );

		return child ? child.getNode( child.output ) : undefined;

	}
```
</details>

### `MaterialXNode.getNodesByNames(names: any[]): any[]`

**Parameters:**

- **`names`** `any[]`

**Returns:** `any[]`

**Calls:**

- `this.getNodeByName`
- `nodes.push`

<details><summary>Code</summary>

```typescript
getNodesByNames( ...names ) {

		const nodes = [];

		for ( const name of names ) {

			const node = this.getNodeByName( name );

			if ( node ) nodes.push( node );

		}

		return nodes;

	}
```
</details>

### `MaterialXNode.getValue(): any`

**Returns:** `any`

**Calls:**

- `this.value.trim`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.value.trim();

	}
```
</details>

### `MaterialXNode.getVector(): number[]`

**Returns:** `number[]`

**Calls:**

- `this.getValue().split`
- `vector.push`
- `Number`
- `val.trim`

<details><summary>Code</summary>

```typescript
getVector() {

		const vector = [];

		for ( const val of this.getValue().split( /[,|\s]/ ) ) {

			if ( val !== '' ) {

				vector.push( Number( val.trim() ) );

			}

		}

		return vector;

	}
```
</details>

### `MaterialXNode.getAttribute(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.nodeXML.getAttribute`

<details><summary>Code</summary>

```typescript
getAttribute( name ) {

		return this.nodeXML.getAttribute( name );

	}
```
</details>

### `MaterialXNode.getRecursiveAttribute(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.nodeXML.getAttribute`
- `this.parent.getRecursiveAttribute`

<details><summary>Code</summary>

```typescript
getRecursiveAttribute( name ) {

		let attribute = this.nodeXML.getAttribute( name );

		if ( attribute === null && this.parent !== null ) {

			attribute = this.parent.getRecursiveAttribute( name );

		}

		return attribute;

	}
```
</details>

### `MaterialXNode.setStandardSurfaceToGltfPBR(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `this.getNodes`
- `mul (from three/tsl)`
- `clamp (from three/tsl)`
- `float (from three/tsl)`
- `color (from three/tsl)`

**Internal Comments:**
```
// (x32)
// Clamp IOR to valid range for Three.js (1.0 to 2.333) (x3)
// Auto-enable iridescence when thin film parameters are present
```

<details><summary>Code</summary>

```typescript
setStandardSurfaceToGltfPBR( material ) {

		const inputs = this.getNodes();

		//

		let colorNode = null;

		if ( inputs.base && inputs.base_color ) colorNode = mul( inputs.base, inputs.base_color );
		else if ( inputs.base ) colorNode = inputs.base;
		else if ( inputs.base_color ) colorNode = inputs.base_color;

		//

		let opacityNode = null;

		if ( inputs.opacity ) opacityNode = inputs.opacity;

		//

		let roughnessNode = null;

		if ( inputs.specular_roughness ) roughnessNode = inputs.specular_roughness;

		//

		let metalnessNode = null;

		if ( inputs.metalness ) metalnessNode = inputs.metalness;

		//

		let specularIntensityNode = null;

		if ( inputs.specular ) specularIntensityNode = inputs.specular;

		//

		let specularColorNode = null;

		if ( inputs.specular_color ) specularColorNode = inputs.specular_color;

		//

		let iorNode = null;

		if ( inputs.ior ) iorNode = inputs.ior;

		//

		let anisotropyNode = null;
		let anisotropyRotationNode = null;

		if ( inputs.specular_anisotropy ) anisotropyNode = inputs.specular_anisotropy;
		if ( inputs.specular_rotation ) anisotropyRotationNode = inputs.specular_rotation;

		//

		let transmissionNode = null;
		let transmissionColorNode = null;

		if ( inputs.transmission ) transmissionNode = inputs.transmission;
		if ( inputs.transmission_color ) transmissionColorNode = inputs.transmission_color;

		//

		let thinFilmThicknessNode = null;
		let thinFilmIorNode = null;

		if ( inputs.thin_film_thickness ) thinFilmThicknessNode = inputs.thin_film_thickness;

		if ( inputs.thin_film_ior ) {

			// Clamp IOR to valid range for Three.js (1.0 to 2.333)
			thinFilmIorNode = clamp( inputs.thin_film_ior, float( 1.0 ), float( 2.333 ) );

		}

		//

		let sheenNode = null;
		let sheenColorNode = null;
		let sheenRoughnessNode = null;

		if ( inputs.sheen ) sheenNode = inputs.sheen;
		if ( inputs.sheen_color ) sheenColorNode = inputs.sheen_color;
		if ( inputs.sheen_roughness ) sheenRoughnessNode = inputs.sheen_roughness;

		//

		let clearcoatNode = null;
		let clearcoatRoughnessNode = null;

		if ( inputs.coat ) clearcoatNode = inputs.coat;
		if ( inputs.coat_roughness ) clearcoatRoughnessNode = inputs.coat_roughness;

		if ( inputs.coat_color ) {

			colorNode = colorNode ? mul( colorNode, inputs.coat_color ) : colorNode;

		}

		//

		let normalNode = null;

		if ( inputs.normal ) normalNode = inputs.normal;

		//

		let emissiveNode = null;

		if ( inputs.emission ) emissiveNode = inputs.emission;
		if ( inputs.emissionColor ) {

			emissiveNode = emissiveNode ? mul( emissiveNode, inputs.emissionColor ) : emissiveNode;

		}

		//

		material.colorNode = colorNode || color( 0.8, 0.8, 0.8 );
		material.opacityNode = opacityNode || float( 1.0 );
		material.roughnessNode = roughnessNode || float( 0.2 );
		material.metalnessNode = metalnessNode || float( 0 );
		material.specularIntensityNode = specularIntensityNode || float( 0.5 );
		material.specularColorNode = specularColorNode || color( 1.0, 1.0, 1.0 );
		material.iorNode = iorNode || float( 1.5 );
		material.anisotropyNode = anisotropyNode || float( 0 );
		material.anisotropyRotationNode = anisotropyRotationNode || float( 0 );
		material.transmissionNode = transmissionNode || float( 0 );
		material.transmissionColorNode = transmissionColorNode || color( 1.0, 1.0, 1.0 );
		material.thinFilmThicknessNode = thinFilmThicknessNode || float( 0 );
		material.thinFilmIorNode = thinFilmIorNode || float( 1.5 );
		material.sheenNode = sheenNode || float( 0 );
		material.sheenColorNode = sheenColorNode || color( 1.0, 1.0, 1.0 );
		material.sheenRoughnessNode = sheenRoughnessNode || float( 0.5 );
		material.clearcoatNode = clearcoatNode || float( 0 );
		material.clearcoatRoughnessNode = clearcoatRoughnessNode || float( 0 );
		if ( normalNode ) material.normalNode = normalNode;
		if ( emissiveNode ) material.emissiveNode = emissiveNode;

		// Auto-enable iridescence when thin film parameters are present
		if ( thinFilmThicknessNode && thinFilmThicknessNode.value !== undefined && thinFilmThicknessNode.value > 0 ) {

			material.iridescence = 1.0;

		}

		if ( opacityNode !== null ) {

			material.transparent = true;

		}

		if ( transmissionNode !== null ) {

			material.side = DoubleSide;
			material.transparent = true;

		}

	}
```
</details>

### `MaterialXNode.setMaterial(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `this.setStandardSurfaceToGltfPBR`

<details><summary>Code</summary>

```typescript
setMaterial( material ) {

		const element = this.element;

		if ( element === 'gltf_pbr' ) {

			//this.setGltfPBR( material );

		} else if ( element === 'standard_surface' ) {

			this.setStandardSurfaceToGltfPBR( material );

		}

	}
```
</details>

### `MaterialXNode.toBasicMaterial(): any`

**Returns:** `any`

**Calls:**

- `this.children.toReversed`
- `nodeX.getNode`

<details><summary>Code</summary>

```typescript
toBasicMaterial() {

		const material = new MeshBasicNodeMaterial();
		material.name = this.name;

		for ( const nodeX of this.children.toReversed() ) {

			if ( nodeX.name === 'out' ) {

				material.colorNode = nodeX.getNode();

				break;

			}

		}

		return material;

	}
```
</details>

### `MaterialXNode.toPhysicalMaterial(): any`

**Returns:** `any`

**Calls:**

- `this.materialX.getMaterialXNode`
- `shaderProperties.setMaterial`

<details><summary>Code</summary>

```typescript
toPhysicalMaterial() {

		const material = new MeshPhysicalNodeMaterial();
		material.name = this.name;

		for ( const nodeX of this.children ) {

			const shaderProperties = this.materialX.getMaterialXNode( nodeX.nodeName );
			shaderProperties.setMaterial( material );

		}

		return material;

	}
```
</details>

### `MaterialXNode.toMaterials(): {}`

**Returns:** `{}`

**Calls:**

- `nodeX.toPhysicalMaterial`
- `nodeX.toBasicMaterial`

<details><summary>Code</summary>

```typescript
toMaterials() {

		const materials = {};

		let isUnlit = true;

		for ( const nodeX of this.children ) {

			if ( nodeX.element === 'surfacematerial' ) {

				const material = nodeX.toPhysicalMaterial();

				materials[ material.name ] = material;

				isUnlit = false;

			}

		}

		if ( isUnlit ) {

			for ( const nodeX of this.children ) {

				if ( nodeX.element === 'nodegraph' ) {

					const material = nodeX.toBasicMaterial();

					materials[ material.name ] = material;

				}

			}

		}

		return materials;

	}
```
</details>

### `MaterialXNode.add(materialXNode: any): void`

**Parameters:**

- **`materialXNode`** `any`

**Returns:** `void`

**Calls:**

- `this.children.push`

<details><summary>Code</summary>

```typescript
add( materialXNode ) {

		materialXNode.parent = this;

		this.children.push( materialXNode );

	}
```
</details>

### `MaterialX.addMaterialXNode(materialXNode: any): void`

**Parameters:**

- **`materialXNode`** `any`

**Returns:** `void`

**Calls:**

- `this.nodesXLib.set`

<details><summary>Code</summary>

```typescript
addMaterialXNode( materialXNode ) {

		this.nodesXLib.set( materialXNode.nodePath, materialXNode );

	}
```
</details>

### `MaterialX.getMaterialXNode(names: any[]): any`

**Parameters:**

- **`names`** `any[]`

**Returns:** `any`

**Calls:**

- `this.nodesXLib.get`
- `names.join`

<details><summary>Code</summary>

```typescript
getMaterialXNode( ...names ) {

		return this.nodesXLib.get( names.join( '/' ) );

	}
```
</details>

### `MaterialX.parseNode(nodeXML: any, nodePath: string): MaterialXNode`

**Parameters:**

- **`nodeXML`** `any`
- **`nodePath`** `string`

**Returns:** `MaterialXNode`

**Calls:**

- `this.addMaterialXNode`
- `this.parseNode`
- `materialXNode.add`

<details><summary>Code</summary>

```typescript
parseNode( nodeXML, nodePath = '' ) {

		const materialXNode = new MaterialXNode( this, nodeXML, nodePath );
		if ( materialXNode.nodePath ) this.addMaterialXNode( materialXNode );

		for ( const childNodeXML of nodeXML.children ) {

			const childMXNode = this.parseNode( childNodeXML, materialXNode.nodePath );
			materialXNode.add( childMXNode );

		}

		return materialXNode;

	}
```
</details>

### `MaterialX.parse(text: any): { materials: {}; }`

**Parameters:**

- **`text`** `any`

**Returns:** `{ materials: {}; }`

**Calls:**

- `new DOMParser().parseFromString`
- `this.textureLoader.setPath`
- `this.parseNode( rootXML ).toMaterials`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
parse( text ) {

		const rootXML = new DOMParser().parseFromString( text, 'application/xml' ).documentElement;

		this.textureLoader.setPath( this.path );

		//

		const materials = this.parseNode( rootXML ).toMaterials();

		return { materials };

	}
```
</details>


---

## Classes

### `MXElement`

<details><summary>Class Code</summary>

```ts
class MXElement {

	constructor( name, nodeFunc, params = [] ) {

		this.name = name;
		this.nodeFunc = nodeFunc;
		this.params = params;

	}

}
```
</details>

### `MaterialXLoader`

<details><summary>Class Code</summary>

```ts
class MaterialXLoader extends Loader {

	/**
	 * Constructs a new MaterialX loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded MaterialX asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Object<string,NodeMaterial>)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {MaterialXLoader} A reference to this loader.
	 */
	load( url, onLoad, onProgress, onError ) {

		const _onError = function ( e ) {

			if ( onError ) {

				onError( e );

			} else {

				console.error( e );

			}

		};

		new FileLoader( this.manager )
			.setPath( this.path )
			.load( url, async ( text ) => {

				try {

					onLoad( this.parse( text ) );

				} catch ( e ) {

					_onError( e );

				}

			}, onProgress, _onError );

		return this;

	}

	/**
	 * Parses the given MaterialX data and returns the resulting materials.
	 *
	 * Supported standard_surface inputs:
	 * - base, base_color: Base color/albedo
	 * - opacity: Alpha/transparency
	 * - specular_roughness: Surface roughness
	 * - metalness: Metallic property
	 * - specular: Specular reflection intensity
	 * - specular_color: Specular reflection color
	 * - ior: Index of refraction
	 * - specular_anisotropy, specular_rotation: Anisotropic reflection
	 * - transmission, transmission_color: Transmission properties
	 * - thin_film_thickness, thin_film_ior: Thin film interference
	 * - sheen, sheen_color, sheen_roughness: Sheen properties
	 * - normal: Normal map
	 * - coat, coat_roughness, coat_color: Clearcoat properties
	 * - emission, emissionColor: Emission properties
	 *
	 * @param {string} text - The raw MaterialX data as a string.
	 * @return {Object<string,NodeMaterial>} A dictionary holding the parse node materials.
	 */
	parse( text ) {

		return new MaterialX( this.manager, this.path ).parse( text );

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: { [x: string]: NodeMaterial; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): MaterialXLoader`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const _onError = function ( e ) {

			if ( onError ) {

				onError( e );

			} else {

				console.error( e );

			}

		};

		new FileLoader( this.manager )
			.setPath( this.path )
			.load( url, async ( text ) => {

				try {

					onLoad( this.parse( text ) );

				} catch ( e ) {

					_onError( e );

				}

			}, onProgress, _onError );

		return this;

	}
```
</details>

##### `parse(text: string): { [x: string]: NodeMaterial; }`

<details><summary>Code</summary>

```ts
parse( text ) {

		return new MaterialX( this.manager, this.path ).parse( text );

	}
```
</details>

### `MaterialXNode`

<details><summary>Class Code</summary>

```ts
class MaterialXNode {

	constructor( materialX, nodeXML, nodePath = '' ) {

		if ( ! materialX || typeof materialX !== 'object' ) {

			console.warn( 'MaterialXNode: materialX argument is not an object!', { materialX, nodeXML, nodePath } );

		}

		this.materialX = materialX;
		this.nodeXML = nodeXML;
		this.nodePath = nodePath ? nodePath + '/' + this.name : this.name;

		this.parent = null;

		this.node = null;

		this.children = [];

	}

	get element() {

		return this.nodeXML.nodeName;

	}

	get nodeGraph() {

		return this.getAttribute( 'nodegraph' );

	}

	get nodeName() {

		return this.getAttribute( 'nodename' );

	}

	get interfaceName() {

		return this.getAttribute( 'interfacename' );

	}

	get output() {

		return this.getAttribute( 'output' );

	}

	get name() {

		return this.getAttribute( 'name' );

	}

	get type() {

		return this.getAttribute( 'type' );

	}

	get value() {

		return this.getAttribute( 'value' );

	}

	getNodeGraph() {

		let nodeX = this;

		while ( nodeX !== null ) {

			if ( nodeX.element === 'nodegraph' ) {

				break;

			}

			nodeX = nodeX.parent;

		}

		return nodeX;

	}

	getRoot() {

		let nodeX = this;

		while ( nodeX.parent !== null ) {

			nodeX = nodeX.parent;

		}

		return nodeX;

	}

	get referencePath() {

		let referencePath = null;

		if ( this.nodeGraph !== null && this.output !== null ) {

			referencePath = this.nodeGraph + '/' + this.output;

		} else if ( this.nodeName !== null || this.interfaceName !== null ) {

			referencePath = this.getNodeGraph().nodePath + '/' + ( this.nodeName || this.interfaceName );

		}

		return referencePath;

	}

	get hasReference() {

		return this.referencePath !== null;

	}

	get isConst() {

		return this.element === 'input' && this.value !== null && this.type !== 'filename';

	}

	getColorSpaceNode() {

		const csSource = this.getAttribute( 'colorspace' );
		const csTarget = this.getRoot().getAttribute( 'colorspace' );

		const nodeName = `mx_${ csSource }_to_${ csTarget }`;

		return colorSpaceLib[ nodeName ];

	}

	getTexture() {

		const filePrefix = this.getRecursiveAttribute( 'fileprefix' ) || '';

		let loader = this.materialX.textureLoader;
		const uri = filePrefix + this.value;

		if ( uri ) {

			const handler = this.materialX.manager.getHandler( uri );
			if ( handler !== null ) loader = handler;

		}

		const texture = loader.load( uri );
		texture.wrapS = texture.wrapT = RepeatWrapping;
		texture.flipY = false;

		return texture;

	}

	getClassFromType( type ) {

		let nodeClass = null;

		if ( type === 'integer' ) nodeClass = int;
		else if ( type === 'float' ) nodeClass = float;
		else if ( type === 'vector2' ) nodeClass = vec2;
		else if ( type === 'vector3' ) nodeClass = vec3;
		else if ( type === 'vector4' || type === 'color4' ) nodeClass = vec4;
		else if ( type === 'color3' ) nodeClass = color;
		else if ( type === 'boolean' ) nodeClass = bool;

		return nodeClass;

	}

	getNode( out = null ) {

		let node = this.node;

		if ( node !== null && out === null ) {

			return node;

		}

		// Handle <input name="texcoord" type="vector2" ... />
		if (
			this.element === 'input' &&
			this.name === 'texcoord' &&
			this.type === 'vector2'
		) {

			// Try to get index from defaultgeomprop (e.g., "UV0" => 0)
			let index = 0;
			const defaultGeomProp = this.getAttribute( 'defaultgeomprop' );
			if ( defaultGeomProp && /^UV(\d+)$/.test( defaultGeomProp ) ) {

				index = parseInt( defaultGeomProp.match( /^UV(\d+)$/ )[ 1 ], 10 );

			}

			node = uv( index );

		}

		// Multi-output support for separate/separate3
		if (
			( this.element === 'separate3' || this.element === 'separate2' || this.element === 'separate4' ) &&
			out && typeof out === 'string' && out.startsWith( 'out' )
		) {

			const inNode = this.getNodeByName( 'in' );
			return mx_separate( inNode, out );

		}

		//

		const type = this.type;

		if ( this.isConst ) {

			const nodeClass = this.getClassFromType( type );

			node = nodeClass( ...this.getVector() );

		} else if ( this.hasReference ) {

			if ( this.element === 'output' && this.output && out === null ) {

				out = this.output;

			}

			node = this.materialX.getMaterialXNode( this.referencePath ).getNode( out );

		} else {

			const element = this.element;

			if ( element === 'convert' ) {

				const nodeClass = this.getClassFromType( type );

				node = nodeClass( this.getNodeByName( 'in' ) );

			} else if ( element === 'constant' ) {

				node = this.getNodeByName( 'value' );

			} else if ( element === 'position' ) {

				const space = this.getAttribute( 'space' );
				node = space === 'world' ? positionWorld : positionLocal;

			} else if ( element === 'normal' ) {

				const space = this.getAttribute( 'space' );
				node = space === 'world' ? normalWorld : normalLocal;

			} else if ( element === 'tangent' ) {

				const space = this.getAttribute( 'space' );
				node = space === 'world' ? tangentWorld : tangentLocal;

			} else if ( element === 'texcoord' ) {

				const indexNode = this.getChildByName( 'index' );
				const index = indexNode ? parseInt( indexNode.value ) : 0;

				node = uv( index );

			} else if ( element === 'geomcolor' ) {

				const indexNode = this.getChildByName( 'index' );
				const index = indexNode ? parseInt( indexNode.value ) : 0;

				node = vertexColor( index );

			} else if ( element === 'tiledimage' ) {

				const file = this.getChildByName( 'file' );

				const textureFile = file.getTexture();
				const uvTiling = mx_transform_uv( ...this.getNodesByNames( [ 'uvtiling', 'uvoffset' ] ) );

				node = texture( textureFile, uvTiling );

				const colorSpaceNode = file.getColorSpaceNode();

				if ( colorSpaceNode ) {

					node = colorSpaceNode( node );

				}

			} else if ( element === 'image' ) {

				const file = this.getChildByName( 'file' );
				const uvNode = this.getNodeByName( 'texcoord' );

				const textureFile = file.getTexture();

				node = texture( textureFile, uvNode );

				const colorSpaceNode = file.getColorSpaceNode();

				if ( colorSpaceNode ) {

					node = colorSpaceNode( node );

				}

			} else if ( MtlXLibrary[ element ] !== undefined ) {

				const nodeElement = MtlXLibrary[ element ];

				if ( ! nodeElement ) {

					throw new Error( `THREE.MaterialXLoader: Unexpected node ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );

				}

				if ( ! nodeElement.nodeFunc ) {

					throw new Error( `THREE.MaterialXLoader: Unexpected node 2 ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );

				}

				if ( out !== null ) {

					node = nodeElement.nodeFunc( ...this.getNodesByNames( ...nodeElement.params ), out );

				} else {

					node = nodeElement.nodeFunc( ...this.getNodesByNames( ...nodeElement.params ) );

				}

			}

		}

		//

		if ( node === null ) {

			console.warn( `THREE.MaterialXLoader: Unexpected node ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );

			node = float( 0 );

		}

		//

		const nodeToTypeClass = this.getClassFromType( type );

		if ( nodeToTypeClass !== null ) {

			node = nodeToTypeClass( node );

		} else {

			console.warn( `THREE.MaterialXLoader: Unexpected node ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );
			node = float( 0 );

		}

		node.name = this.name;

		this.node = node;

		return node;

	}

	getChildByName( name ) {

		for ( const input of this.children ) {

			if ( input.name === name ) {

				return input;

			}

		}

	}

	getNodes() {

		const nodes = {};

		for ( const input of this.children ) {

			const node = input.getNode();

			nodes[ node.name ] = node;

		}

		return nodes;

	}

	getNodeByName( name ) {

		const child = this.getChildByName( name );

		return child ? child.getNode( child.output ) : undefined;

	}

	getNodesByNames( ...names ) {

		const nodes = [];

		for ( const name of names ) {

			const node = this.getNodeByName( name );

			if ( node ) nodes.push( node );

		}

		return nodes;

	}

	getValue() {

		return this.value.trim();

	}

	getVector() {

		const vector = [];

		for ( const val of this.getValue().split( /[,|\s]/ ) ) {

			if ( val !== '' ) {

				vector.push( Number( val.trim() ) );

			}

		}

		return vector;

	}

	getAttribute( name ) {

		return this.nodeXML.getAttribute( name );

	}

	getRecursiveAttribute( name ) {

		let attribute = this.nodeXML.getAttribute( name );

		if ( attribute === null && this.parent !== null ) {

			attribute = this.parent.getRecursiveAttribute( name );

		}

		return attribute;

	}

	setStandardSurfaceToGltfPBR( material ) {

		const inputs = this.getNodes();

		//

		let colorNode = null;

		if ( inputs.base && inputs.base_color ) colorNode = mul( inputs.base, inputs.base_color );
		else if ( inputs.base ) colorNode = inputs.base;
		else if ( inputs.base_color ) colorNode = inputs.base_color;

		//

		let opacityNode = null;

		if ( inputs.opacity ) opacityNode = inputs.opacity;

		//

		let roughnessNode = null;

		if ( inputs.specular_roughness ) roughnessNode = inputs.specular_roughness;

		//

		let metalnessNode = null;

		if ( inputs.metalness ) metalnessNode = inputs.metalness;

		//

		let specularIntensityNode = null;

		if ( inputs.specular ) specularIntensityNode = inputs.specular;

		//

		let specularColorNode = null;

		if ( inputs.specular_color ) specularColorNode = inputs.specular_color;

		//

		let iorNode = null;

		if ( inputs.ior ) iorNode = inputs.ior;

		//

		let anisotropyNode = null;
		let anisotropyRotationNode = null;

		if ( inputs.specular_anisotropy ) anisotropyNode = inputs.specular_anisotropy;
		if ( inputs.specular_rotation ) anisotropyRotationNode = inputs.specular_rotation;

		//

		let transmissionNode = null;
		let transmissionColorNode = null;

		if ( inputs.transmission ) transmissionNode = inputs.transmission;
		if ( inputs.transmission_color ) transmissionColorNode = inputs.transmission_color;

		//

		let thinFilmThicknessNode = null;
		let thinFilmIorNode = null;

		if ( inputs.thin_film_thickness ) thinFilmThicknessNode = inputs.thin_film_thickness;

		if ( inputs.thin_film_ior ) {

			// Clamp IOR to valid range for Three.js (1.0 to 2.333)
			thinFilmIorNode = clamp( inputs.thin_film_ior, float( 1.0 ), float( 2.333 ) );

		}

		//

		let sheenNode = null;
		let sheenColorNode = null;
		let sheenRoughnessNode = null;

		if ( inputs.sheen ) sheenNode = inputs.sheen;
		if ( inputs.sheen_color ) sheenColorNode = inputs.sheen_color;
		if ( inputs.sheen_roughness ) sheenRoughnessNode = inputs.sheen_roughness;

		//

		let clearcoatNode = null;
		let clearcoatRoughnessNode = null;

		if ( inputs.coat ) clearcoatNode = inputs.coat;
		if ( inputs.coat_roughness ) clearcoatRoughnessNode = inputs.coat_roughness;

		if ( inputs.coat_color ) {

			colorNode = colorNode ? mul( colorNode, inputs.coat_color ) : colorNode;

		}

		//

		let normalNode = null;

		if ( inputs.normal ) normalNode = inputs.normal;

		//

		let emissiveNode = null;

		if ( inputs.emission ) emissiveNode = inputs.emission;
		if ( inputs.emissionColor ) {

			emissiveNode = emissiveNode ? mul( emissiveNode, inputs.emissionColor ) : emissiveNode;

		}

		//

		material.colorNode = colorNode || color( 0.8, 0.8, 0.8 );
		material.opacityNode = opacityNode || float( 1.0 );
		material.roughnessNode = roughnessNode || float( 0.2 );
		material.metalnessNode = metalnessNode || float( 0 );
		material.specularIntensityNode = specularIntensityNode || float( 0.5 );
		material.specularColorNode = specularColorNode || color( 1.0, 1.0, 1.0 );
		material.iorNode = iorNode || float( 1.5 );
		material.anisotropyNode = anisotropyNode || float( 0 );
		material.anisotropyRotationNode = anisotropyRotationNode || float( 0 );
		material.transmissionNode = transmissionNode || float( 0 );
		material.transmissionColorNode = transmissionColorNode || color( 1.0, 1.0, 1.0 );
		material.thinFilmThicknessNode = thinFilmThicknessNode || float( 0 );
		material.thinFilmIorNode = thinFilmIorNode || float( 1.5 );
		material.sheenNode = sheenNode || float( 0 );
		material.sheenColorNode = sheenColorNode || color( 1.0, 1.0, 1.0 );
		material.sheenRoughnessNode = sheenRoughnessNode || float( 0.5 );
		material.clearcoatNode = clearcoatNode || float( 0 );
		material.clearcoatRoughnessNode = clearcoatRoughnessNode || float( 0 );
		if ( normalNode ) material.normalNode = normalNode;
		if ( emissiveNode ) material.emissiveNode = emissiveNode;

		// Auto-enable iridescence when thin film parameters are present
		if ( thinFilmThicknessNode && thinFilmThicknessNode.value !== undefined && thinFilmThicknessNode.value > 0 ) {

			material.iridescence = 1.0;

		}

		if ( opacityNode !== null ) {

			material.transparent = true;

		}

		if ( transmissionNode !== null ) {

			material.side = DoubleSide;
			material.transparent = true;

		}

	}

	/*setGltfPBR( material ) {

		const inputs = this.getNodes();

		console.log( inputs );

	}*/

	setMaterial( material ) {

		const element = this.element;

		if ( element === 'gltf_pbr' ) {

			//this.setGltfPBR( material );

		} else if ( element === 'standard_surface' ) {

			this.setStandardSurfaceToGltfPBR( material );

		}

	}

	toBasicMaterial() {

		const material = new MeshBasicNodeMaterial();
		material.name = this.name;

		for ( const nodeX of this.children.toReversed() ) {

			if ( nodeX.name === 'out' ) {

				material.colorNode = nodeX.getNode();

				break;

			}

		}

		return material;

	}

	toPhysicalMaterial() {

		const material = new MeshPhysicalNodeMaterial();
		material.name = this.name;

		for ( const nodeX of this.children ) {

			const shaderProperties = this.materialX.getMaterialXNode( nodeX.nodeName );
			shaderProperties.setMaterial( material );

		}

		return material;

	}

	toMaterials() {

		const materials = {};

		let isUnlit = true;

		for ( const nodeX of this.children ) {

			if ( nodeX.element === 'surfacematerial' ) {

				const material = nodeX.toPhysicalMaterial();

				materials[ material.name ] = material;

				isUnlit = false;

			}

		}

		if ( isUnlit ) {

			for ( const nodeX of this.children ) {

				if ( nodeX.element === 'nodegraph' ) {

					const material = nodeX.toBasicMaterial();

					materials[ material.name ] = material;

				}

			}

		}

		return materials;

	}

	add( materialXNode ) {

		materialXNode.parent = this;

		this.children.push( materialXNode );

	}

}
```
</details>

#### Methods

##### `getNodeGraph(): this`

<details><summary>Code</summary>

```ts
getNodeGraph() {

		let nodeX = this;

		while ( nodeX !== null ) {

			if ( nodeX.element === 'nodegraph' ) {

				break;

			}

			nodeX = nodeX.parent;

		}

		return nodeX;

	}
```
</details>

##### `getRoot(): this`

<details><summary>Code</summary>

```ts
getRoot() {

		let nodeX = this;

		while ( nodeX.parent !== null ) {

			nodeX = nodeX.parent;

		}

		return nodeX;

	}
```
</details>

##### `getColorSpaceNode(): any`

<details><summary>Code</summary>

```ts
getColorSpaceNode() {

		const csSource = this.getAttribute( 'colorspace' );
		const csTarget = this.getRoot().getAttribute( 'colorspace' );

		const nodeName = `mx_${ csSource }_to_${ csTarget }`;

		return colorSpaceLib[ nodeName ];

	}
```
</details>

##### `getTexture(): any`

<details><summary>Code</summary>

```ts
getTexture() {

		const filePrefix = this.getRecursiveAttribute( 'fileprefix' ) || '';

		let loader = this.materialX.textureLoader;
		const uri = filePrefix + this.value;

		if ( uri ) {

			const handler = this.materialX.manager.getHandler( uri );
			if ( handler !== null ) loader = handler;

		}

		const texture = loader.load( uri );
		texture.wrapS = texture.wrapT = RepeatWrapping;
		texture.flipY = false;

		return texture;

	}
```
</details>

##### `getClassFromType(type: any): any`

<details><summary>Code</summary>

```ts
getClassFromType( type ) {

		let nodeClass = null;

		if ( type === 'integer' ) nodeClass = int;
		else if ( type === 'float' ) nodeClass = float;
		else if ( type === 'vector2' ) nodeClass = vec2;
		else if ( type === 'vector3' ) nodeClass = vec3;
		else if ( type === 'vector4' || type === 'color4' ) nodeClass = vec4;
		else if ( type === 'color3' ) nodeClass = color;
		else if ( type === 'boolean' ) nodeClass = bool;

		return nodeClass;

	}
```
</details>

##### `getNode(out: any): any`

<details><summary>Code</summary>

```ts
getNode( out = null ) {

		let node = this.node;

		if ( node !== null && out === null ) {

			return node;

		}

		// Handle <input name="texcoord" type="vector2" ... />
		if (
			this.element === 'input' &&
			this.name === 'texcoord' &&
			this.type === 'vector2'
		) {

			// Try to get index from defaultgeomprop (e.g., "UV0" => 0)
			let index = 0;
			const defaultGeomProp = this.getAttribute( 'defaultgeomprop' );
			if ( defaultGeomProp && /^UV(\d+)$/.test( defaultGeomProp ) ) {

				index = parseInt( defaultGeomProp.match( /^UV(\d+)$/ )[ 1 ], 10 );

			}

			node = uv( index );

		}

		// Multi-output support for separate/separate3
		if (
			( this.element === 'separate3' || this.element === 'separate2' || this.element === 'separate4' ) &&
			out && typeof out === 'string' && out.startsWith( 'out' )
		) {

			const inNode = this.getNodeByName( 'in' );
			return mx_separate( inNode, out );

		}

		//

		const type = this.type;

		if ( this.isConst ) {

			const nodeClass = this.getClassFromType( type );

			node = nodeClass( ...this.getVector() );

		} else if ( this.hasReference ) {

			if ( this.element === 'output' && this.output && out === null ) {

				out = this.output;

			}

			node = this.materialX.getMaterialXNode( this.referencePath ).getNode( out );

		} else {

			const element = this.element;

			if ( element === 'convert' ) {

				const nodeClass = this.getClassFromType( type );

				node = nodeClass( this.getNodeByName( 'in' ) );

			} else if ( element === 'constant' ) {

				node = this.getNodeByName( 'value' );

			} else if ( element === 'position' ) {

				const space = this.getAttribute( 'space' );
				node = space === 'world' ? positionWorld : positionLocal;

			} else if ( element === 'normal' ) {

				const space = this.getAttribute( 'space' );
				node = space === 'world' ? normalWorld : normalLocal;

			} else if ( element === 'tangent' ) {

				const space = this.getAttribute( 'space' );
				node = space === 'world' ? tangentWorld : tangentLocal;

			} else if ( element === 'texcoord' ) {

				const indexNode = this.getChildByName( 'index' );
				const index = indexNode ? parseInt( indexNode.value ) : 0;

				node = uv( index );

			} else if ( element === 'geomcolor' ) {

				const indexNode = this.getChildByName( 'index' );
				const index = indexNode ? parseInt( indexNode.value ) : 0;

				node = vertexColor( index );

			} else if ( element === 'tiledimage' ) {

				const file = this.getChildByName( 'file' );

				const textureFile = file.getTexture();
				const uvTiling = mx_transform_uv( ...this.getNodesByNames( [ 'uvtiling', 'uvoffset' ] ) );

				node = texture( textureFile, uvTiling );

				const colorSpaceNode = file.getColorSpaceNode();

				if ( colorSpaceNode ) {

					node = colorSpaceNode( node );

				}

			} else if ( element === 'image' ) {

				const file = this.getChildByName( 'file' );
				const uvNode = this.getNodeByName( 'texcoord' );

				const textureFile = file.getTexture();

				node = texture( textureFile, uvNode );

				const colorSpaceNode = file.getColorSpaceNode();

				if ( colorSpaceNode ) {

					node = colorSpaceNode( node );

				}

			} else if ( MtlXLibrary[ element ] !== undefined ) {

				const nodeElement = MtlXLibrary[ element ];

				if ( ! nodeElement ) {

					throw new Error( `THREE.MaterialXLoader: Unexpected node ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );

				}

				if ( ! nodeElement.nodeFunc ) {

					throw new Error( `THREE.MaterialXLoader: Unexpected node 2 ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );

				}

				if ( out !== null ) {

					node = nodeElement.nodeFunc( ...this.getNodesByNames( ...nodeElement.params ), out );

				} else {

					node = nodeElement.nodeFunc( ...this.getNodesByNames( ...nodeElement.params ) );

				}

			}

		}

		//

		if ( node === null ) {

			console.warn( `THREE.MaterialXLoader: Unexpected node ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );

			node = float( 0 );

		}

		//

		const nodeToTypeClass = this.getClassFromType( type );

		if ( nodeToTypeClass !== null ) {

			node = nodeToTypeClass( node );

		} else {

			console.warn( `THREE.MaterialXLoader: Unexpected node ${ new XMLSerializer().serializeToString( this.nodeXML ) }.` );
			node = float( 0 );

		}

		node.name = this.name;

		this.node = node;

		return node;

	}
```
</details>

##### `getChildByName(name: any): any`

<details><summary>Code</summary>

```ts
getChildByName( name ) {

		for ( const input of this.children ) {

			if ( input.name === name ) {

				return input;

			}

		}

	}
```
</details>

##### `getNodes(): {}`

<details><summary>Code</summary>

```ts
getNodes() {

		const nodes = {};

		for ( const input of this.children ) {

			const node = input.getNode();

			nodes[ node.name ] = node;

		}

		return nodes;

	}
```
</details>

##### `getNodeByName(name: any): any`

<details><summary>Code</summary>

```ts
getNodeByName( name ) {

		const child = this.getChildByName( name );

		return child ? child.getNode( child.output ) : undefined;

	}
```
</details>

##### `getNodesByNames(names: any[]): any[]`

<details><summary>Code</summary>

```ts
getNodesByNames( ...names ) {

		const nodes = [];

		for ( const name of names ) {

			const node = this.getNodeByName( name );

			if ( node ) nodes.push( node );

		}

		return nodes;

	}
```
</details>

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.value.trim();

	}
```
</details>

##### `getVector(): number[]`

<details><summary>Code</summary>

```ts
getVector() {

		const vector = [];

		for ( const val of this.getValue().split( /[,|\s]/ ) ) {

			if ( val !== '' ) {

				vector.push( Number( val.trim() ) );

			}

		}

		return vector;

	}
```
</details>

##### `getAttribute(name: any): any`

<details><summary>Code</summary>

```ts
getAttribute( name ) {

		return this.nodeXML.getAttribute( name );

	}
```
</details>

##### `getRecursiveAttribute(name: any): any`

<details><summary>Code</summary>

```ts
getRecursiveAttribute( name ) {

		let attribute = this.nodeXML.getAttribute( name );

		if ( attribute === null && this.parent !== null ) {

			attribute = this.parent.getRecursiveAttribute( name );

		}

		return attribute;

	}
```
</details>

##### `setStandardSurfaceToGltfPBR(material: any): void`

<details><summary>Code</summary>

```ts
setStandardSurfaceToGltfPBR( material ) {

		const inputs = this.getNodes();

		//

		let colorNode = null;

		if ( inputs.base && inputs.base_color ) colorNode = mul( inputs.base, inputs.base_color );
		else if ( inputs.base ) colorNode = inputs.base;
		else if ( inputs.base_color ) colorNode = inputs.base_color;

		//

		let opacityNode = null;

		if ( inputs.opacity ) opacityNode = inputs.opacity;

		//

		let roughnessNode = null;

		if ( inputs.specular_roughness ) roughnessNode = inputs.specular_roughness;

		//

		let metalnessNode = null;

		if ( inputs.metalness ) metalnessNode = inputs.metalness;

		//

		let specularIntensityNode = null;

		if ( inputs.specular ) specularIntensityNode = inputs.specular;

		//

		let specularColorNode = null;

		if ( inputs.specular_color ) specularColorNode = inputs.specular_color;

		//

		let iorNode = null;

		if ( inputs.ior ) iorNode = inputs.ior;

		//

		let anisotropyNode = null;
		let anisotropyRotationNode = null;

		if ( inputs.specular_anisotropy ) anisotropyNode = inputs.specular_anisotropy;
		if ( inputs.specular_rotation ) anisotropyRotationNode = inputs.specular_rotation;

		//

		let transmissionNode = null;
		let transmissionColorNode = null;

		if ( inputs.transmission ) transmissionNode = inputs.transmission;
		if ( inputs.transmission_color ) transmissionColorNode = inputs.transmission_color;

		//

		let thinFilmThicknessNode = null;
		let thinFilmIorNode = null;

		if ( inputs.thin_film_thickness ) thinFilmThicknessNode = inputs.thin_film_thickness;

		if ( inputs.thin_film_ior ) {

			// Clamp IOR to valid range for Three.js (1.0 to 2.333)
			thinFilmIorNode = clamp( inputs.thin_film_ior, float( 1.0 ), float( 2.333 ) );

		}

		//

		let sheenNode = null;
		let sheenColorNode = null;
		let sheenRoughnessNode = null;

		if ( inputs.sheen ) sheenNode = inputs.sheen;
		if ( inputs.sheen_color ) sheenColorNode = inputs.sheen_color;
		if ( inputs.sheen_roughness ) sheenRoughnessNode = inputs.sheen_roughness;

		//

		let clearcoatNode = null;
		let clearcoatRoughnessNode = null;

		if ( inputs.coat ) clearcoatNode = inputs.coat;
		if ( inputs.coat_roughness ) clearcoatRoughnessNode = inputs.coat_roughness;

		if ( inputs.coat_color ) {

			colorNode = colorNode ? mul( colorNode, inputs.coat_color ) : colorNode;

		}

		//

		let normalNode = null;

		if ( inputs.normal ) normalNode = inputs.normal;

		//

		let emissiveNode = null;

		if ( inputs.emission ) emissiveNode = inputs.emission;
		if ( inputs.emissionColor ) {

			emissiveNode = emissiveNode ? mul( emissiveNode, inputs.emissionColor ) : emissiveNode;

		}

		//

		material.colorNode = colorNode || color( 0.8, 0.8, 0.8 );
		material.opacityNode = opacityNode || float( 1.0 );
		material.roughnessNode = roughnessNode || float( 0.2 );
		material.metalnessNode = metalnessNode || float( 0 );
		material.specularIntensityNode = specularIntensityNode || float( 0.5 );
		material.specularColorNode = specularColorNode || color( 1.0, 1.0, 1.0 );
		material.iorNode = iorNode || float( 1.5 );
		material.anisotropyNode = anisotropyNode || float( 0 );
		material.anisotropyRotationNode = anisotropyRotationNode || float( 0 );
		material.transmissionNode = transmissionNode || float( 0 );
		material.transmissionColorNode = transmissionColorNode || color( 1.0, 1.0, 1.0 );
		material.thinFilmThicknessNode = thinFilmThicknessNode || float( 0 );
		material.thinFilmIorNode = thinFilmIorNode || float( 1.5 );
		material.sheenNode = sheenNode || float( 0 );
		material.sheenColorNode = sheenColorNode || color( 1.0, 1.0, 1.0 );
		material.sheenRoughnessNode = sheenRoughnessNode || float( 0.5 );
		material.clearcoatNode = clearcoatNode || float( 0 );
		material.clearcoatRoughnessNode = clearcoatRoughnessNode || float( 0 );
		if ( normalNode ) material.normalNode = normalNode;
		if ( emissiveNode ) material.emissiveNode = emissiveNode;

		// Auto-enable iridescence when thin film parameters are present
		if ( thinFilmThicknessNode && thinFilmThicknessNode.value !== undefined && thinFilmThicknessNode.value > 0 ) {

			material.iridescence = 1.0;

		}

		if ( opacityNode !== null ) {

			material.transparent = true;

		}

		if ( transmissionNode !== null ) {

			material.side = DoubleSide;
			material.transparent = true;

		}

	}
```
</details>

##### `setMaterial(material: any): void`

<details><summary>Code</summary>

```ts
setMaterial( material ) {

		const element = this.element;

		if ( element === 'gltf_pbr' ) {

			//this.setGltfPBR( material );

		} else if ( element === 'standard_surface' ) {

			this.setStandardSurfaceToGltfPBR( material );

		}

	}
```
</details>

##### `toBasicMaterial(): any`

<details><summary>Code</summary>

```ts
toBasicMaterial() {

		const material = new MeshBasicNodeMaterial();
		material.name = this.name;

		for ( const nodeX of this.children.toReversed() ) {

			if ( nodeX.name === 'out' ) {

				material.colorNode = nodeX.getNode();

				break;

			}

		}

		return material;

	}
```
</details>

##### `toPhysicalMaterial(): any`

<details><summary>Code</summary>

```ts
toPhysicalMaterial() {

		const material = new MeshPhysicalNodeMaterial();
		material.name = this.name;

		for ( const nodeX of this.children ) {

			const shaderProperties = this.materialX.getMaterialXNode( nodeX.nodeName );
			shaderProperties.setMaterial( material );

		}

		return material;

	}
```
</details>

##### `toMaterials(): {}`

<details><summary>Code</summary>

```ts
toMaterials() {

		const materials = {};

		let isUnlit = true;

		for ( const nodeX of this.children ) {

			if ( nodeX.element === 'surfacematerial' ) {

				const material = nodeX.toPhysicalMaterial();

				materials[ material.name ] = material;

				isUnlit = false;

			}

		}

		if ( isUnlit ) {

			for ( const nodeX of this.children ) {

				if ( nodeX.element === 'nodegraph' ) {

					const material = nodeX.toBasicMaterial();

					materials[ material.name ] = material;

				}

			}

		}

		return materials;

	}
```
</details>

##### `add(materialXNode: any): void`

<details><summary>Code</summary>

```ts
add( materialXNode ) {

		materialXNode.parent = this;

		this.children.push( materialXNode );

	}
```
</details>

### `MaterialX`

<details><summary>Class Code</summary>

```ts
class MaterialX {

	constructor( manager, path ) {

		this.manager = manager;
		this.path = path;
		this.resourcePath = '';

		this.nodesXLib = new Map();
		//this.nodesXRefLib = new WeakMap();

		this.textureLoader = new TextureLoader( manager );

	}

	addMaterialXNode( materialXNode ) {

		this.nodesXLib.set( materialXNode.nodePath, materialXNode );

	}

	/*getMaterialXNodeFromXML( xmlNode ) {

        return this.nodesXRefLib.get( xmlNode );

    }*/

	getMaterialXNode( ...names ) {

		return this.nodesXLib.get( names.join( '/' ) );

	}

	parseNode( nodeXML, nodePath = '' ) {

		const materialXNode = new MaterialXNode( this, nodeXML, nodePath );
		if ( materialXNode.nodePath ) this.addMaterialXNode( materialXNode );

		for ( const childNodeXML of nodeXML.children ) {

			const childMXNode = this.parseNode( childNodeXML, materialXNode.nodePath );
			materialXNode.add( childMXNode );

		}

		return materialXNode;

	}

	parse( text ) {

		const rootXML = new DOMParser().parseFromString( text, 'application/xml' ).documentElement;

		this.textureLoader.setPath( this.path );

		//

		const materials = this.parseNode( rootXML ).toMaterials();

		return { materials };

	}

}
```
</details>

#### Methods

##### `addMaterialXNode(materialXNode: any): void`

<details><summary>Code</summary>

```ts
addMaterialXNode( materialXNode ) {

		this.nodesXLib.set( materialXNode.nodePath, materialXNode );

	}
```
</details>

##### `getMaterialXNode(names: any[]): any`

<details><summary>Code</summary>

```ts
getMaterialXNode( ...names ) {

		return this.nodesXLib.get( names.join( '/' ) );

	}
```
</details>

##### `parseNode(nodeXML: any, nodePath: string): MaterialXNode`

<details><summary>Code</summary>

```ts
parseNode( nodeXML, nodePath = '' ) {

		const materialXNode = new MaterialXNode( this, nodeXML, nodePath );
		if ( materialXNode.nodePath ) this.addMaterialXNode( materialXNode );

		for ( const childNodeXML of nodeXML.children ) {

			const childMXNode = this.parseNode( childNodeXML, materialXNode.nodePath );
			materialXNode.add( childMXNode );

		}

		return materialXNode;

	}
```
</details>

##### `parse(text: any): { materials: {}; }`

<details><summary>Code</summary>

```ts
parse( text ) {

		const rootXML = new DOMParser().parseFromString( text, 'application/xml' ).documentElement;

		this.textureLoader.setPath( this.path );

		//

		const materials = this.parseNode( rootXML ).toMaterials();

		return { materials };

	}
```
</details>


---