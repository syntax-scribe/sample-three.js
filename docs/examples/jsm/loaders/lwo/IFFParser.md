[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `IFFParser.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 54 |
| 🧱 Classes | 3 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 28 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/lwo/IFFParser.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LWO2Parser` | `./LWO2Parser.js` |
| `LWO3Parser` | `./LWO3Parser.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `surface` | `{ attributes: {}; connections: {}; na...` | let/var | `{ attributes: {}, // LWO2 style non-node attributes will go here connections:...` | ✗ |
| `surface` | `{ attributes: {}; connections: {}; na...` | let/var | `{ attributes: {}, // LWO2 style non-node attributes will go here connections:...` | ✗ |
| `node` | `{ name: string; }` | let/var | `{ name: name }` | ✗ |
| `map` | `{}` | let/var | `{}` | ✗ |
| `texture` | `{ index: number; }` | let/var | `{ index: this.reader.getUint32() }` | ✗ |
| `texture` | `{ index: number; fileName: string; }` | let/var | `{ index: this.reader.getUint32(), fileName: '' }` | ✗ |
| `endOffset` | `number` | let/var | `this.reader.offset + length - 4` | ✗ |
| `endOffset` | `number` | let/var | `this.reader.offset + length - 4` | ✗ |
| `layer` | `{ number: number; flags: number; pivo...` | let/var | `{ number: number, flags: flags, // If the least significant bit of flags is s...` | ✗ |
| `parsedLength` | `any` | let/var | `16 + stringOffset( this.currentLayer.name )` | ✗ |
| `finalOffset` | `any` | let/var | `this.reader.offset + length` | ✗ |
| `remainingLength` | `number` | let/var | `length - 6 - stringOffset( name )` | ✗ |
| `uvIndices` | `any[]` | let/var | `[]` | ✗ |
| `polyIndices` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `finalOffset` | `any` | let/var | `this.reader.offset + length` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `polygonDimensions` | `any[]` | let/var | `[]` | ✗ |
| `geometryData` | `{ type: string; vertexIndices: number...` | let/var | `{ type: type, vertexIndices: indices, polygonDimensions: polygonDimensions, p...` | ✗ |
| `finalOffset` | `any` | let/var | `this.reader.offset + length` | ✗ |
| `a` | `any[]` | let/var | `[]` | ✗ |
| `a` | `any[]` | let/var | `[]` | ✗ |
| `start` | `number` | let/var | `this.offset` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `length` | `any` | let/var | `*not shown*` | ✗ |
| `nodeType` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `IFFParser.parse(buffer: any): { materials: {}; layers: any[]; tags: any[]; textures: any[]; }`

**Parameters:**

- **`buffer`** `any`

**Returns:** `{ materials: {}; layers: any[]; tags: any[]; textures: any[]; }`

**Calls:**

- `this.parseTopForm`
- `this.reader.endOfFile`
- `this.parser.parseBlock`
- `this.debugger.closeForms`

**Internal Comments:**
```
// start out at the top level to add any data before first layer is encountered (x4)
```

<details><summary>Code</summary>

```typescript
parse( buffer ) {

		this.reader = new DataViewReader( buffer );

		this.tree = {
			materials: {},
			layers: [],
			tags: [],
			textures: [],
		};

		// start out at the top level to add any data before first layer is encountered
		this.currentLayer = this.tree;
		this.currentForm = this.tree;

		this.parseTopForm();

		if ( this.tree.format === undefined ) return;

		if ( this.tree.format === 'LWO2' ) {

			this.parser = new LWO2Parser( this );
			while ( ! this.reader.endOfFile() ) this.parser.parseBlock();

		} else if ( this.tree.format === 'LWO3' ) {

			this.parser = new LWO3Parser( this );
			while ( ! this.reader.endOfFile() ) this.parser.parseBlock();

		}

		this.debugger.offset = this.reader.offset;
		this.debugger.closeForms();

		return this.tree;

	}
```
</details>

### `IFFParser.parseTopForm(): void`

**Returns:** `void`

**Calls:**

- `this.reader.getIDTag`
- `console.warn`
- `this.reader.getUint32`
- `this.debugger.log`

<details><summary>Code</summary>

```typescript
parseTopForm() {

		this.debugger.offset = this.reader.offset;

		const topForm = this.reader.getIDTag();

		if ( topForm !== 'FORM' ) {

			console.warn( 'LWOLoader: Top-level FORM missing.' );
			return;

		}

		const length = this.reader.getUint32();

		this.debugger.dataOffset = this.reader.offset;
		this.debugger.length = length;

		const type = this.reader.getIDTag();

		if ( type === 'LWO2' ) {

			this.tree.format = type;

		} else if ( type === 'LWO3' ) {

			this.tree.format = type;

		}

		this.debugger.node = 0;
		this.debugger.nodeID = type;
		this.debugger.log();

		return;

	}
```
</details>

### `IFFParser.parseForm(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getIDTag`
- `this.skipForm`
- `this.parseTextureNodeAttribute`
- `this.parseEnvelope`
- `this.parseForm`
- `this.parseClip`
- `this.parseImage`
- `this.reader.skip`
- `this.reader.getUint32`
- `this.reader.getString`
- `this.parseImageStateForm`
- `this.parseSurfaceForm`
- `this.parseValueForm`
- `this.parseSubNode`
- `this.setupForm`
- `this.parseConnections`
- `this.parseEntryForm`
- `this.parseImageMap`
- `this.parseXVAL`
- `this.parseXVAL3`
- `this.parseUnknownForm`
- `this.debugger.log`

**Internal Comments:**
```
// SKIPPED FORMS
// if skipForm( length ) is called, the entire form and any sub forms and chunks are skipped
// Car Material FORMS
// if break; is called directly, the position in the lwoTree is not created
// any sub chunks and forms are added to the parent form instead
// used by texture nodes
// this.setupForm( type, length ); (x5)
// CLIP FORM AND SUB FORMS
// Not in spec, used by texture nodes
// SURF FORM AND SUB FORMS
// Image Map Layer
//Texture Mapping Form
```

<details><summary>Code</summary>

```typescript
parseForm( length ) {

		const type = this.reader.getIDTag();

		switch ( type ) {

			// SKIPPED FORMS
			// if skipForm( length ) is called, the entire form and any sub forms and chunks are skipped

			case 'ISEQ': // Image sequence
			case 'ANIM': // plug in animation
			case 'STCC': // Color-cycling Still
			case 'VPVL':
			case 'VPRM':
			case 'NROT':
			case 'WRPW': // image wrap w ( for cylindrical and spherical projections)
			case 'WRPH': // image wrap h
			case 'FUNC':
			case 'FALL':
			case 'OPAC':
			case 'GRAD': // gradient texture
			case 'ENVS':
			case 'VMOP':
			case 'VMBG':

			// Car Material FORMS
			case 'OMAX':
			case 'STEX':
			case 'CKBG':
			case 'CKEY':
			case 'VMLA':
			case 'VMLB':
				this.debugger.skipped = true;
				this.skipForm( length ); // not currently supported
				break;

			// if break; is called directly, the position in the lwoTree is not created
			// any sub chunks and forms are added to the parent form instead
			case 'META':
			case 'NNDS':
			case 'NODS':
			case 'NDTA':
			case 'ADAT':
			case 'AOVS':
			case 'BLOK':

			// used by texture nodes
			case 'IBGC': // imageBackgroundColor
			case 'IOPC': // imageOpacity
			case 'IIMG': // hold reference to image path
			case 'TXTR':
				// this.setupForm( type, length );
				this.debugger.length = 4;
				this.debugger.skipped = true;
				break;

			case 'IFAL': // imageFallof
			case 'ISCL': // imageScale
			case 'IPOS': // imagePosition
			case 'IROT': // imageRotation
			case 'IBMP':
			case 'IUTD':
			case 'IVTD':
				this.parseTextureNodeAttribute( type );
				break;

			case 'ENVL':
				this.parseEnvelope( length );
				break;

				// CLIP FORM AND SUB FORMS

			case 'CLIP':
				if ( this.tree.format === 'LWO2' ) {

					this.parseForm( length );

				} else {

					this.parseClip( length );

				}

				break;

			case 'STIL':
				this.parseImage();
				break;

			case 'XREF': // clone of another STIL
				this.reader.skip( 8 ); // unknown
				this.currentForm.referenceTexture = {
					index: this.reader.getUint32(),
					refName: this.reader.getString() // internal unique ref
				};
				break;

				// Not in spec, used by texture nodes

			case 'IMST':
				this.parseImageStateForm( length );
				break;

				// SURF FORM AND SUB FORMS

			case 'SURF':
				this.parseSurfaceForm( length );
				break;

			case 'VALU': // Not in spec
				this.parseValueForm( length );
				break;

			case 'NTAG':
				this.parseSubNode( length );
				break;

			case 'ATTR': // BSDF Node Attributes
			case 'SATR': // Standard Node Attributes
				this.setupForm( 'attributes', length );
				break;

			case 'NCON':
				this.parseConnections( length );
				break;

			case 'SSHA':
				this.parentForm = this.currentForm;
				this.currentForm = this.currentSurface;
				this.setupForm( 'surfaceShader', length );
				break;

			case 'SSHD':
				this.setupForm( 'surfaceShaderData', length );
				break;

			case 'ENTR': // Not in spec
				this.parseEntryForm( length );
				break;

				// Image Map Layer

			case 'IMAP':
				this.parseImageMap( length );
				break;

			case 'TAMP':
				this.parseXVAL( 'amplitude', length );
				break;

				//Texture Mapping Form

			case 'TMAP':
				this.setupForm( 'textureMap', length );
				break;

			case 'CNTR':
				this.parseXVAL3( 'center', length );
				break;

			case 'SIZE':
				this.parseXVAL3( 'scale', length );
				break;

			case 'ROTA':
				this.parseXVAL3( 'rotation', length );
				break;

			default:
				this.parseUnknownForm( type, length );

		}

		this.debugger.node = 0;
		this.debugger.nodeID = type;
		this.debugger.log();

	}
```
</details>

### `IFFParser.setupForm(type: any, length: any): void`

**Parameters:**

- **`type`** `any`
- **`length`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`

**Internal Comments:**
```
// should never see this unless there's a bug in the reader (x4)
```

<details><summary>Code</summary>

```typescript
setupForm( type, length ) {

		if ( ! this.currentForm ) this.currentForm = this.currentNode;

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		if ( ! this.currentForm[ type ] ) {

			this.currentForm[ type ] = {};
			this.currentForm = this.currentForm[ type ];


		} else {

			// should never see this unless there's a bug in the reader
			console.warn( 'LWOLoader: form already exists on parent: ', type, this.currentForm );

			this.currentForm = this.currentForm[ type ];

		}


	}
```
</details>

### `IFFParser.skipForm(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.skip`

<details><summary>Code</summary>

```typescript
skipForm( length ) {

		this.reader.skip( length - 4 );

	}
```
</details>

### `IFFParser.parseUnknownForm(type: any, length: any): void`

**Parameters:**

- **`type`** `any`
- **`length`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`
- `printBuffer`
- `this.reader.skip`

<details><summary>Code</summary>

```typescript
parseUnknownForm( type, length ) {

		console.warn( 'LWOLoader: unknown FORM encountered: ' + type, length );

		printBuffer( this.reader.dv.buffer, this.reader.offset, length - 4 );
		this.reader.skip( length - 4 );

	}
```
</details>

### `IFFParser.parseSurfaceForm(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.skip`
- `this.reader.getString`

<details><summary>Code</summary>

```typescript
parseSurfaceForm( length ) {

		this.reader.skip( 8 ); // unknown Uint32 x2

		const name = this.reader.getString();

		const surface = {
			attributes: {}, // LWO2 style non-node attributes will go here
			connections: {},
			name: name,
			inputName: name,
			nodes: {},
			source: this.reader.getString(),
		};

		this.tree.materials[ name ] = surface;
		this.currentSurface = surface;

		this.parentForm = this.tree.materials;
		this.currentForm = surface;
		this.currentFormEnd = this.reader.offset + length;

	}
```
</details>

### `IFFParser.parseSurfaceLwo2(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getString`

<details><summary>Code</summary>

```typescript
parseSurfaceLwo2( length ) {

		const name = this.reader.getString();

		const surface = {
			attributes: {}, // LWO2 style non-node attributes will go here
			connections: {},
			name: name,
			nodes: {},
			source: this.reader.getString(),
		};

		this.tree.materials[ name ] = surface;
		this.currentSurface = surface;

		this.parentForm = this.tree.materials;
		this.currentForm = surface;
		this.currentFormEnd = this.reader.offset + length;

	}
```
</details>

### `IFFParser.parseSubNode(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.skip`
- `this.reader.getString`

**Internal Comments:**
```
// parse the NRNM CHUNK of the subnode FORM to get (x5)
// a meaningful name for the subNode (x5)
// some subnodes can be renamed, but Input and Surface cannot (x5)
```

<details><summary>Code</summary>

```typescript
parseSubNode( length ) {

		// parse the NRNM CHUNK of the subnode FORM to get
		// a meaningful name for the subNode
		// some subnodes can be renamed, but Input and Surface cannot

		this.reader.skip( 8 ); // NRNM + length
		const name = this.reader.getString();

		const node = {
			name: name
		};
		this.currentForm = node;
		this.currentNode = node;

		this.currentFormEnd = this.reader.offset + length;


	}
```
</details>

### `IFFParser.parseConnections(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
parseConnections( length ) {

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		this.currentForm = this.currentSurface.connections;

	}
```
</details>

### `IFFParser.parseEntryForm(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.skip`
- `this.reader.getString`
- `this.setupForm`

<details><summary>Code</summary>

```typescript
parseEntryForm( length ) {

		this.reader.skip( 8 ); // NAME + length
		const name = this.reader.getString();
		this.currentForm = this.currentNode.attributes;

		this.setupForm( name, length );

	}
```
</details>

### `IFFParser.parseValueForm(): void`

**Returns:** `void`

**Calls:**

- `this.reader.skip`
- `this.reader.getString`
- `this.reader.getUint64`
- `this.reader.getUint32`
- `this.reader.getFloat64`
- `this.reader.getFloat64Array`

<details><summary>Code</summary>

```typescript
parseValueForm() {

		this.reader.skip( 8 ); // unknown + length

		const valueType = this.reader.getString();

		if ( valueType === 'double' ) {

			this.currentForm.value = this.reader.getUint64();

		} else if ( valueType === 'int' ) {

			this.currentForm.value = this.reader.getUint32();

		} else if ( valueType === 'vparam' ) {

			this.reader.skip( 24 );
			this.currentForm.value = this.reader.getFloat64();

		} else if ( valueType === 'vparam3' ) {

			this.reader.skip( 24 );
			this.currentForm.value = this.reader.getFloat64Array( 3 );

		}

	}
```
</details>

### `IFFParser.parseImageStateForm(): void`

**Returns:** `void`

**Calls:**

- `this.reader.skip`
- `this.reader.getFloat32`

<details><summary>Code</summary>

```typescript
parseImageStateForm() {

		this.reader.skip( 8 ); // unknown

		this.currentForm.mipMapLevel = this.reader.getFloat32();

	}
```
</details>

### `IFFParser.parseImageMap(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.currentForm.maps.push`
- `this.reader.skip`

<details><summary>Code</summary>

```typescript
parseImageMap( length ) {

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		if ( ! this.currentForm.maps ) this.currentForm.maps = [];

		const map = {};
		this.currentForm.maps.push( map );
		this.currentForm = map;

		this.reader.skip( 10 ); // unknown, could be an issue if it contains a VX

	}
```
</details>

### `IFFParser.parseTextureNodeAttribute(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.skip`
- `this.reader.getFloat32Array`
- `this.reader.getFloat32`

<details><summary>Code</summary>

```typescript
parseTextureNodeAttribute( type ) {

		this.reader.skip( 28 ); // FORM + length + VPRM + unknown + Uint32 x2 + float32

		this.reader.skip( 20 ); // FORM + length + VPVL + float32 + Uint32

		switch ( type ) {

			case 'ISCL':
				this.currentNode.scale = this.reader.getFloat32Array( 3 );
				break;
			case 'IPOS':
				this.currentNode.position = this.reader.getFloat32Array( 3 );
				break;
			case 'IROT':
				this.currentNode.rotation = this.reader.getFloat32Array( 3 );
				break;
			case 'IFAL':
				this.currentNode.falloff = this.reader.getFloat32Array( 3 );
				break;

			case 'IBMP':
				this.currentNode.amplitude = this.reader.getFloat32();
				break;
			case 'IUTD':
				this.currentNode.uTiles = this.reader.getFloat32();
				break;
			case 'IVTD':
				this.currentNode.vTiles = this.reader.getFloat32();
				break;

		}

		this.reader.skip( 2 ); // unknown


	}
```
</details>

### `IFFParser.parseEnvelope(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.skip`

<details><summary>Code</summary>

```typescript
parseEnvelope( length ) {

		this.reader.skip( length - 4 ); // skipping  entirely for now

	}
```
</details>

### `IFFParser.parseClip(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getIDTag`
- `this.reader.skip`
- `this.reader.getString`
- `this.reader.setOffset`
- `this.reader.getUint32`
- `this.tree.textures.push`

**Internal Comments:**
```
// inside surface node
// otherwise top level (x5)
```

<details><summary>Code</summary>

```typescript
parseClip( length ) {

		const tag = this.reader.getIDTag();

		// inside surface node
		if ( tag === 'FORM' ) {

			this.reader.skip( 16 );

			this.currentNode.fileName = this.reader.getString();

			return;

		}

		// otherwise top level
		this.reader.setOffset( this.reader.offset - 4 );

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		this.reader.skip( 8 ); // unknown

		const texture = {
			index: this.reader.getUint32()
		};
		this.tree.textures.push( texture );
		this.currentForm = texture;

	}
```
</details>

### `IFFParser.parseClipLwo2(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getUint32`
- `this.reader.getIDTag`
- `this.reader.getUint16`
- `this.reader.getString`
- `this.tree.textures.push`

**Internal Comments:**
```
// search STIL block
```

<details><summary>Code</summary>

```typescript
parseClipLwo2( length ) {

		const texture = {
			index: this.reader.getUint32(),
			fileName: ''
		};

		// search STIL block
		while ( true ) {

			const tag = this.reader.getIDTag();
			const n_length = this.reader.getUint16();
			if ( tag === 'STIL' ) {

				texture.fileName = this.reader.getString();
				break;

			}

			if ( n_length >= length ) {

				break;

			}

		}

		this.tree.textures.push( texture );
		this.currentForm = texture;

	}
```
</details>

### `IFFParser.parseImage(): void`

**Returns:** `void`

**Calls:**

- `this.reader.skip`
- `this.reader.getString`

<details><summary>Code</summary>

```typescript
parseImage() {

		this.reader.skip( 8 ); // unknown
		this.currentForm.fileName = this.reader.getString();

	}
```
</details>

### `IFFParser.parseXVAL(type: any, length: any): void`

**Parameters:**

- **`type`** `any`
- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.skip`
- `this.reader.getFloat32`
- `this.reader.setOffset`

<details><summary>Code</summary>

```typescript
parseXVAL( type, length ) {

		const endOffset = this.reader.offset + length - 4;
		this.reader.skip( 8 );

		this.currentForm[ type ] = this.reader.getFloat32();

		this.reader.setOffset( endOffset ); // set end offset directly to skip optional envelope

	}
```
</details>

### `IFFParser.parseXVAL3(type: any, length: any): void`

**Parameters:**

- **`type`** `any`
- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.skip`
- `this.reader.getFloat32`
- `this.reader.setOffset`

<details><summary>Code</summary>

```typescript
parseXVAL3( type, length ) {

		const endOffset = this.reader.offset + length - 4;
		this.reader.skip( 8 );

		this.currentForm[ type ] = {
			x: this.reader.getFloat32(),
			y: this.reader.getFloat32(),
			z: this.reader.getFloat32(),
		};

		this.reader.setOffset( endOffset );

	}
```
</details>

### `IFFParser.parseObjectTag(): void`

**Returns:** `void`

**Calls:**

- `this.reader.getIDTag`
- `this.reader.getString`

<details><summary>Code</summary>

```typescript
parseObjectTag() {

		if ( ! this.tree.objectTags ) this.tree.objectTags = {};

		this.tree.objectTags[ this.reader.getIDTag() ] = {
			tagString: this.reader.getString()
		};

	}
```
</details>

### `IFFParser.parseLayer(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getUint16`
- `this.reader.getFloat32Array`
- `this.reader.getString`
- `this.tree.layers.push`
- `stringOffset`

**Internal Comments:**
```
// if we have not reached then end of the layer block, there must be a parent defined (x5)
```

<details><summary>Code</summary>

```typescript
parseLayer( length ) {

		const number = this.reader.getUint16();
		const flags = this.reader.getUint16(); // If the least significant bit of flags is set, the layer is hidden.
		const pivot = this.reader.getFloat32Array( 3 ); // Note: this seems to be superfluous, as the geometry is translated when pivot is present
		const layer = {
			number: number,
			flags: flags, // If the least significant bit of flags is set, the layer is hidden.
			pivot: [ - pivot[ 0 ], pivot[ 1 ], pivot[ 2 ] ], // Note: this seems to be superfluous, as the geometry is translated when pivot is present
			name: this.reader.getString(),
		};

		this.tree.layers.push( layer );
		this.currentLayer = layer;

		const parsedLength = 16 + stringOffset( this.currentLayer.name ); // index ( 2 ) + flags( 2 ) + pivot( 12 ) + stringlength

		// if we have not reached then end of the layer block, there must be a parent defined
		this.currentLayer.parent = ( parsedLength < length ) ? this.reader.getUint16() : - 1; // omitted or -1 for no parent

	}
```
</details>

### `IFFParser.parsePoints(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.currentPoints.push`
- `this.reader.getFloat32`

**Internal Comments:**
```
// x -> -x to match three.js right handed coords (x5)
```

<details><summary>Code</summary>

```typescript
parsePoints( length ) {

		this.currentPoints = [];
		for ( let i = 0; i < length / 4; i += 3 ) {

			// x -> -x to match three.js right handed coords
			this.currentPoints.push( - this.reader.getFloat32(), this.reader.getFloat32(), this.reader.getFloat32() );

		}

	}
```
</details>

### `IFFParser.parseVertexMapping(length: any, discontinuous: any): void`

**Parameters:**

- **`length`** `any`
- **`discontinuous`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getString`
- `this.reader.setOffset`
- `stringOffset`
- `this.reader.getIDTag`
- `this.reader.getUint16`
- `this.parseUVMapping`
- `this.parseMorphTargets`
- `this.reader.skip`
- `console.warn`

**Internal Comments:**
```
// then we are in a texture node and the VMAP chunk is just a reference to a UV channel name (x5)
// otherwise reset to initial length and parse normal VMAP CHUNK (x5)
// unsupported VMAPs
```

<details><summary>Code</summary>

```typescript
parseVertexMapping( length, discontinuous ) {

		const finalOffset = this.reader.offset + length;

		const channelName = this.reader.getString();

		if ( this.reader.offset === finalOffset ) {

			// then we are in a texture node and the VMAP chunk is just a reference to a UV channel name
			this.currentForm.UVChannel = channelName;
			return;

		}

		// otherwise reset to initial length and parse normal VMAP CHUNK
		this.reader.setOffset( this.reader.offset - stringOffset( channelName ) );

		const type = this.reader.getIDTag();

		this.reader.getUint16(); // dimension
		const name = this.reader.getString();

		const remainingLength = length - 6 - stringOffset( name );

		switch ( type ) {

			case 'TXUV':
				this.parseUVMapping( name, finalOffset, discontinuous );
				break;
			case 'MORF':
			case 'SPOT':
				this.parseMorphTargets( name, finalOffset, type ); // can't be discontinuous
				break;
			// unsupported VMAPs
			case 'APSL':
			case 'NORM':
			case 'WGHT':
			case 'MNVW':
			case 'PICK':
			case 'RGB ':
			case 'RGBA':
				this.reader.skip( remainingLength );
				break;
			default:
				console.warn( 'LWOLoader: unknown vertex map type: ' + type );
				this.reader.skip( remainingLength );

		}

	}
```
</details>

### `IFFParser.parseUVMapping(name: any, finalOffset: any, discontinuous: any): void`

**Parameters:**

- **`name`** `any`
- **`finalOffset`** `any`
- **`discontinuous`** `any`

**Returns:** `void`

**Calls:**

- `uvIndices.push`
- `this.reader.getVariableLengthIndex`
- `polyIndices.push`
- `uvs.push`
- `this.reader.getFloat32`

<details><summary>Code</summary>

```typescript
parseUVMapping( name, finalOffset, discontinuous ) {

		const uvIndices = [];
		const polyIndices = [];
		const uvs = [];

		while ( this.reader.offset < finalOffset ) {

			uvIndices.push( this.reader.getVariableLengthIndex() );

			if ( discontinuous ) polyIndices.push( this.reader.getVariableLengthIndex() );

			uvs.push( this.reader.getFloat32(), this.reader.getFloat32() );

		}

		if ( discontinuous ) {

			if ( ! this.currentLayer.discontinuousUVs ) this.currentLayer.discontinuousUVs = {};

			this.currentLayer.discontinuousUVs[ name ] = {
				uvIndices: uvIndices,
				polyIndices: polyIndices,
				uvs: uvs,
			};

		} else {

			if ( ! this.currentLayer.uvs ) this.currentLayer.uvs = {};

			this.currentLayer.uvs[ name ] = {
				uvIndices: uvIndices,
				uvs: uvs,
			};

		}

	}
```
</details>

### `IFFParser.parseMorphTargets(name: any, finalOffset: any, type: any): void`

**Parameters:**

- **`name`** `any`
- **`finalOffset`** `any`
- **`type`** `any`

**Returns:** `void`

**Calls:**

- `indices.push`
- `this.reader.getVariableLengthIndex`
- `points.push`
- `this.reader.getFloat32`

**Internal Comments:**
```
// z -> -z to match three.js right handed coords (x4)
```

<details><summary>Code</summary>

```typescript
parseMorphTargets( name, finalOffset, type ) {

		const indices = [];
		const points = [];

		type = ( type === 'MORF' ) ? 'relative' : 'absolute';

		while ( this.reader.offset < finalOffset ) {

			indices.push( this.reader.getVariableLengthIndex() );
			// z -> -z to match three.js right handed coords
			points.push( this.reader.getFloat32(), this.reader.getFloat32(), - this.reader.getFloat32() );

		}

		if ( ! this.currentLayer.morphTargets ) this.currentLayer.morphTargets = {};

		this.currentLayer.morphTargets[ name ] = {
			indices: indices,
			points: points,
			type: type,
		};

	}
```
</details>

### `IFFParser.parsePolygonList(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getIDTag`
- `this.reader.getUint16`
- `polygonDimensions.push`
- `indices.push`
- `this.reader.getVariableLengthIndex`

**Internal Comments:**
```
// hold a list of polygon sizes, to be split up later (x2)
//const flags = numverts & 64512; // 6 high order bits are flags - ignoring for now (x3)
// Note: assuming that all polys will be lines or points if the first is
```

<details><summary>Code</summary>

```typescript
parsePolygonList( length ) {

		const finalOffset = this.reader.offset + length;
		const type = this.reader.getIDTag();

		const indices = [];

		// hold a list of polygon sizes, to be split up later
		const polygonDimensions = [];

		while ( this.reader.offset < finalOffset ) {

			let numverts = this.reader.getUint16();

			//const flags = numverts & 64512; // 6 high order bits are flags - ignoring for now
			numverts = numverts & 1023; // remaining ten low order bits are vertex num
			polygonDimensions.push( numverts );

			for ( let j = 0; j < numverts; j ++ ) indices.push( this.reader.getVariableLengthIndex() );

		}

		const geometryData = {
			type: type,
			vertexIndices: indices,
			polygonDimensions: polygonDimensions,
			points: this.currentPoints
		};

		// Note: assuming that all polys will be lines or points if the first is
		if ( polygonDimensions[ 0 ] === 1 ) geometryData.type = 'points';
		else if ( polygonDimensions[ 0 ] === 2 ) geometryData.type = 'lines';

		this.currentLayer.geometry = geometryData;

	}
```
</details>

### `IFFParser.parseTagStrings(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getStringArray`

<details><summary>Code</summary>

```typescript
parseTagStrings( length ) {

		this.tree.tags = this.reader.getStringArray( length );

	}
```
</details>

### `IFFParser.parsePolygonTagMapping(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getIDTag`
- `this.parseMaterialIndices`
- `this.reader.skip`

<details><summary>Code</summary>

```typescript
parsePolygonTagMapping( length ) {

		const finalOffset = this.reader.offset + length;
		const type = this.reader.getIDTag();
		if ( type === 'SURF' ) this.parseMaterialIndices( finalOffset );
		else { //PART, SMGP, COLR not supported

			this.reader.skip( length - 4 );

		}

	}
```
</details>

### `IFFParser.parseMaterialIndices(finalOffset: any): void`

**Parameters:**

- **`finalOffset`** `any`

**Returns:** `void`

**Calls:**

- `this.reader.getVariableLengthIndex`
- `this.reader.getUint16`
- `this.currentLayer.geometry.materialIndices.push`

**Internal Comments:**
```
// array holds polygon index followed by material index (x6)
```

<details><summary>Code</summary>

```typescript
parseMaterialIndices( finalOffset ) {

		// array holds polygon index followed by material index
		this.currentLayer.geometry.materialIndices = [];

		while ( this.reader.offset < finalOffset ) {

			const polygonIndex = this.reader.getVariableLengthIndex();
			const materialIndex = this.reader.getUint16();

			this.currentLayer.geometry.materialIndices.push( polygonIndex, materialIndex );

		}

	}
```
</details>

### `IFFParser.parseUnknownCHUNK(blockID: any, length: any): void`

**Parameters:**

- **`blockID`** `any`
- **`length`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`
- `this.reader.getString`

**Internal Comments:**
```
// print the chunk plus some bytes padding either side (x2)
// printBuffer( this.reader.dv.buffer, this.reader.offset - 20, length + 40 ); (x2)
```

<details><summary>Code</summary>

```typescript
parseUnknownCHUNK( blockID, length ) {

		console.warn( 'LWOLoader: unknown chunk type: ' + blockID + ' length: ' + length );

		// print the chunk plus some bytes padding either side
		// printBuffer( this.reader.dv.buffer, this.reader.offset - 20, length + 40 );

		const data = this.reader.getString( length );

		this.currentForm[ blockID ] = data;

	}
```
</details>

### `DataViewReader.size(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
size() {

		return this.dv.buffer.byteLength;

	}
```
</details>

### `DataViewReader.setOffset(offset: any): void`

**Parameters:**

- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
setOffset( offset ) {

		if ( offset > 0 && offset < this.dv.buffer.byteLength ) {

			this.offset = offset;

		} else {

			console.error( 'LWOLoader: invalid buffer offset' );

		}

	}
```
</details>

### `DataViewReader.endOfFile(): boolean`

**Returns:** `boolean`

**Calls:**

- `this.size`

<details><summary>Code</summary>

```typescript
endOfFile() {

		if ( this.offset >= this.size() ) return true;
		return false;

	}
```
</details>

### `DataViewReader.skip(length: any): void`

**Parameters:**

- **`length`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
skip( length ) {

		this.offset += length;

	}
```
</details>

### `DataViewReader.getUint8(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getUint8`

<details><summary>Code</summary>

```typescript
getUint8() {

		const value = this.dv.getUint8( this.offset );
		this.offset += 1;
		return value;

	}
```
</details>

### `DataViewReader.getUint16(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getUint16`

<details><summary>Code</summary>

```typescript
getUint16() {

		const value = this.dv.getUint16( this.offset );
		this.offset += 2;
		return value;

	}
```
</details>

### `DataViewReader.getInt32(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getInt32`

<details><summary>Code</summary>

```typescript
getInt32() {

		const value = this.dv.getInt32( this.offset, false );
		this.offset += 4;
		return value;

	}
```
</details>

### `DataViewReader.getUint32(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getUint32`

<details><summary>Code</summary>

```typescript
getUint32() {

		const value = this.dv.getUint32( this.offset, false );
		this.offset += 4;
		return value;

	}
```
</details>

### `DataViewReader.getUint64(): number`

**Returns:** `number`

**Calls:**

- `this.getUint32`

<details><summary>Code</summary>

```typescript
getUint64() {

		const low = this.getUint32();
		const high = this.getUint32();
		return high * 0x100000000 + low;

	}
```
</details>

### `DataViewReader.getFloat32(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getFloat32`

<details><summary>Code</summary>

```typescript
getFloat32() {

		const value = this.dv.getFloat32( this.offset, false );
		this.offset += 4;
		return value;

	}
```
</details>

### `DataViewReader.getFloat32Array(size: any): number[]`

**Parameters:**

- **`size`** `any`

**Returns:** `number[]`

**Calls:**

- `a.push`
- `this.getFloat32`

<details><summary>Code</summary>

```typescript
getFloat32Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat32() );

		}

		return a;

	}
```
</details>

### `DataViewReader.getFloat64(): number`

**Returns:** `number`

**Calls:**

- `this.dv.getFloat64`

<details><summary>Code</summary>

```typescript
getFloat64() {

		const value = this.dv.getFloat64( this.offset, this.littleEndian );
		this.offset += 8;
		return value;

	}
```
</details>

### `DataViewReader.getFloat64Array(size: any): number[]`

**Parameters:**

- **`size`** `any`

**Returns:** `number[]`

**Calls:**

- `a.push`
- `this.getFloat64`

<details><summary>Code</summary>

```typescript
getFloat64Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat64() );

		}

		return a;

	}
```
</details>

### `DataViewReader.getVariableLengthIndex(): number`

**Returns:** `number`

**Calls:**

- `this.getUint8`

<details><summary>Code</summary>

```typescript
getVariableLengthIndex() {

		const firstByte = this.getUint8();

		if ( firstByte === 255 ) {

			return this.getUint8() * 65536 + this.getUint8() * 256 + this.getUint8();

		}

		return firstByte * 256 + this.getUint8();

	}
```
</details>

### `DataViewReader.getIDTag(): string`

**Returns:** `string`

**Calls:**

- `this.getString`

<details><summary>Code</summary>

```typescript
getIDTag() {

		return this.getString( 4 );

	}
```
</details>

### `DataViewReader.getString(size: any): string`

**Parameters:**

- **`size`** `any`

**Returns:** `string`

**Calls:**

- `this._textDecoder.decode`
- `this._bytes.indexOf`
- `this.skip`

**Internal Comments:**
```
// use 1:1 mapping of buffer to avoid redundant new array creation. (x3)
// account for null byte in length (x3)
// if string with terminating nullbyte is uneven, extra nullbyte is added, skip that too (x3)
```

<details><summary>Code</summary>

```typescript
getString( size ) {

		if ( size === 0 ) return;

		const start = this.offset;

		let result;
		let length;

		if ( size ) {

			length = size;
			result = this._textDecoder.decode( new Uint8Array( this.dv.buffer, start, size ) );

		} else {

			// use 1:1 mapping of buffer to avoid redundant new array creation.
			length = this._bytes.indexOf( 0, start ) - start;

			result = this._textDecoder.decode( new Uint8Array( this.dv.buffer, start, length ) );

			// account for null byte in length
			length ++;

			// if string with terminating nullbyte is uneven, extra nullbyte is added, skip that too
			length += length % 2;

		}

		this.skip( length );

		return result;

	}
```
</details>

### `DataViewReader.getStringArray(size: any): any`

**Parameters:**

- **`size`** `any`

**Returns:** `any`

**Calls:**

- `this.getString`
- `a.split`
- `a.filter`

<details><summary>Code</summary>

```typescript
getStringArray( size ) {

		let a = this.getString( size );
		a = a.split( '\0' );

		return a.filter( Boolean ); // return array with any empty strings removed

	}
```
</details>

### `Debugger.enable(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
enable() {

		this.active = true;

	}
```
</details>

### `Debugger.log(): void`

**Returns:** `void`

**Calls:**

- `console.log`
- `'| '.repeat`
- `this.formList.push`

<details><summary>Code</summary>

```typescript
log() {

		if ( ! this.active ) return;

		let nodeType;

		switch ( this.node ) {

			case 0:
				nodeType = 'FORM';
				break;

			case 1:
				nodeType = 'CHK';
				break;

			case 2:
				nodeType = 'S-CHK';
				break;

		}

		console.log(
			'| '.repeat( this.depth ) +
			nodeType,
			this.nodeID,
			`( ${this.offset} ) -> ( ${this.dataOffset + this.length} )`,
			( ( this.node == 0 ) ? ' {' : '' ),
			( ( this.skipped ) ? 'SKIPPED' : '' ),
			( ( this.node == 0 && this.skipped ) ? '}' : '' )
		);

		if ( this.node == 0 && ! this.skipped ) {

			this.depth += 1;
			this.formList.push( this.dataOffset + this.length );

		}

		this.skipped = false;

	}
```
</details>

### `Debugger.closeForms(): void`

**Returns:** `void`

**Calls:**

- `console.log`
- `'| '.repeat`
- `this.formList.splice`

<details><summary>Code</summary>

```typescript
closeForms() {

		if ( ! this.active ) return;

		for ( let i = this.formList.length - 1; i >= 0; i -- ) {

			if ( this.offset >= this.formList[ i ] ) {

				this.depth -= 1;
				console.log( '| '.repeat( this.depth ) + '}' );
				this.formList.splice( - 1, 1 );

			}

		}

	}
```
</details>

### `stringOffset(string: any): any`

**Parameters:**

- **`string`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function stringOffset( string ) {

	return string.length + 1 + ( ( string.length + 1 ) % 2 );

}
```
</details>

### `printBuffer(buffer: any, from: any, to: any): void`

**Parameters:**

- **`buffer`** `any`
- **`from`** `any`
- **`to`** `any`

**Returns:** `void`

**Calls:**

- `console.log`
- `new TextDecoder().decode`

<details><summary>Code</summary>

```typescript
function printBuffer( buffer, from, to ) {

	console.log( new TextDecoder().decode( new Uint8Array( buffer, from, to ) ) );

}
```
</details>


---

## Classes

### `IFFParser`

<details><summary>Class Code</summary>

```ts
class IFFParser {

	constructor() {

		this.debugger = new Debugger();
		// this.debugger.enable(); // un-comment to log IFF hierarchy.

	}

	parse( buffer ) {

		this.reader = new DataViewReader( buffer );

		this.tree = {
			materials: {},
			layers: [],
			tags: [],
			textures: [],
		};

		// start out at the top level to add any data before first layer is encountered
		this.currentLayer = this.tree;
		this.currentForm = this.tree;

		this.parseTopForm();

		if ( this.tree.format === undefined ) return;

		if ( this.tree.format === 'LWO2' ) {

			this.parser = new LWO2Parser( this );
			while ( ! this.reader.endOfFile() ) this.parser.parseBlock();

		} else if ( this.tree.format === 'LWO3' ) {

			this.parser = new LWO3Parser( this );
			while ( ! this.reader.endOfFile() ) this.parser.parseBlock();

		}

		this.debugger.offset = this.reader.offset;
		this.debugger.closeForms();

		return this.tree;

	}

	parseTopForm() {

		this.debugger.offset = this.reader.offset;

		const topForm = this.reader.getIDTag();

		if ( topForm !== 'FORM' ) {

			console.warn( 'LWOLoader: Top-level FORM missing.' );
			return;

		}

		const length = this.reader.getUint32();

		this.debugger.dataOffset = this.reader.offset;
		this.debugger.length = length;

		const type = this.reader.getIDTag();

		if ( type === 'LWO2' ) {

			this.tree.format = type;

		} else if ( type === 'LWO3' ) {

			this.tree.format = type;

		}

		this.debugger.node = 0;
		this.debugger.nodeID = type;
		this.debugger.log();

		return;

	}


	///
	// FORM PARSING METHODS
	///

	// Forms are organisational and can contain any number of sub chunks and sub forms
	// FORM ::= 'FORM'[ID4], length[U4], type[ID4], ( chunk[CHUNK] | form[FORM] ) * }
	parseForm( length ) {

		const type = this.reader.getIDTag();

		switch ( type ) {

			// SKIPPED FORMS
			// if skipForm( length ) is called, the entire form and any sub forms and chunks are skipped

			case 'ISEQ': // Image sequence
			case 'ANIM': // plug in animation
			case 'STCC': // Color-cycling Still
			case 'VPVL':
			case 'VPRM':
			case 'NROT':
			case 'WRPW': // image wrap w ( for cylindrical and spherical projections)
			case 'WRPH': // image wrap h
			case 'FUNC':
			case 'FALL':
			case 'OPAC':
			case 'GRAD': // gradient texture
			case 'ENVS':
			case 'VMOP':
			case 'VMBG':

			// Car Material FORMS
			case 'OMAX':
			case 'STEX':
			case 'CKBG':
			case 'CKEY':
			case 'VMLA':
			case 'VMLB':
				this.debugger.skipped = true;
				this.skipForm( length ); // not currently supported
				break;

			// if break; is called directly, the position in the lwoTree is not created
			// any sub chunks and forms are added to the parent form instead
			case 'META':
			case 'NNDS':
			case 'NODS':
			case 'NDTA':
			case 'ADAT':
			case 'AOVS':
			case 'BLOK':

			// used by texture nodes
			case 'IBGC': // imageBackgroundColor
			case 'IOPC': // imageOpacity
			case 'IIMG': // hold reference to image path
			case 'TXTR':
				// this.setupForm( type, length );
				this.debugger.length = 4;
				this.debugger.skipped = true;
				break;

			case 'IFAL': // imageFallof
			case 'ISCL': // imageScale
			case 'IPOS': // imagePosition
			case 'IROT': // imageRotation
			case 'IBMP':
			case 'IUTD':
			case 'IVTD':
				this.parseTextureNodeAttribute( type );
				break;

			case 'ENVL':
				this.parseEnvelope( length );
				break;

				// CLIP FORM AND SUB FORMS

			case 'CLIP':
				if ( this.tree.format === 'LWO2' ) {

					this.parseForm( length );

				} else {

					this.parseClip( length );

				}

				break;

			case 'STIL':
				this.parseImage();
				break;

			case 'XREF': // clone of another STIL
				this.reader.skip( 8 ); // unknown
				this.currentForm.referenceTexture = {
					index: this.reader.getUint32(),
					refName: this.reader.getString() // internal unique ref
				};
				break;

				// Not in spec, used by texture nodes

			case 'IMST':
				this.parseImageStateForm( length );
				break;

				// SURF FORM AND SUB FORMS

			case 'SURF':
				this.parseSurfaceForm( length );
				break;

			case 'VALU': // Not in spec
				this.parseValueForm( length );
				break;

			case 'NTAG':
				this.parseSubNode( length );
				break;

			case 'ATTR': // BSDF Node Attributes
			case 'SATR': // Standard Node Attributes
				this.setupForm( 'attributes', length );
				break;

			case 'NCON':
				this.parseConnections( length );
				break;

			case 'SSHA':
				this.parentForm = this.currentForm;
				this.currentForm = this.currentSurface;
				this.setupForm( 'surfaceShader', length );
				break;

			case 'SSHD':
				this.setupForm( 'surfaceShaderData', length );
				break;

			case 'ENTR': // Not in spec
				this.parseEntryForm( length );
				break;

				// Image Map Layer

			case 'IMAP':
				this.parseImageMap( length );
				break;

			case 'TAMP':
				this.parseXVAL( 'amplitude', length );
				break;

				//Texture Mapping Form

			case 'TMAP':
				this.setupForm( 'textureMap', length );
				break;

			case 'CNTR':
				this.parseXVAL3( 'center', length );
				break;

			case 'SIZE':
				this.parseXVAL3( 'scale', length );
				break;

			case 'ROTA':
				this.parseXVAL3( 'rotation', length );
				break;

			default:
				this.parseUnknownForm( type, length );

		}

		this.debugger.node = 0;
		this.debugger.nodeID = type;
		this.debugger.log();

	}

	setupForm( type, length ) {

		if ( ! this.currentForm ) this.currentForm = this.currentNode;

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		if ( ! this.currentForm[ type ] ) {

			this.currentForm[ type ] = {};
			this.currentForm = this.currentForm[ type ];


		} else {

			// should never see this unless there's a bug in the reader
			console.warn( 'LWOLoader: form already exists on parent: ', type, this.currentForm );

			this.currentForm = this.currentForm[ type ];

		}


	}

	skipForm( length ) {

		this.reader.skip( length - 4 );

	}

	parseUnknownForm( type, length ) {

		console.warn( 'LWOLoader: unknown FORM encountered: ' + type, length );

		printBuffer( this.reader.dv.buffer, this.reader.offset, length - 4 );
		this.reader.skip( length - 4 );

	}

	parseSurfaceForm( length ) {

		this.reader.skip( 8 ); // unknown Uint32 x2

		const name = this.reader.getString();

		const surface = {
			attributes: {}, // LWO2 style non-node attributes will go here
			connections: {},
			name: name,
			inputName: name,
			nodes: {},
			source: this.reader.getString(),
		};

		this.tree.materials[ name ] = surface;
		this.currentSurface = surface;

		this.parentForm = this.tree.materials;
		this.currentForm = surface;
		this.currentFormEnd = this.reader.offset + length;

	}

	parseSurfaceLwo2( length ) {

		const name = this.reader.getString();

		const surface = {
			attributes: {}, // LWO2 style non-node attributes will go here
			connections: {},
			name: name,
			nodes: {},
			source: this.reader.getString(),
		};

		this.tree.materials[ name ] = surface;
		this.currentSurface = surface;

		this.parentForm = this.tree.materials;
		this.currentForm = surface;
		this.currentFormEnd = this.reader.offset + length;

	}

	parseSubNode( length ) {

		// parse the NRNM CHUNK of the subnode FORM to get
		// a meaningful name for the subNode
		// some subnodes can be renamed, but Input and Surface cannot

		this.reader.skip( 8 ); // NRNM + length
		const name = this.reader.getString();

		const node = {
			name: name
		};
		this.currentForm = node;
		this.currentNode = node;

		this.currentFormEnd = this.reader.offset + length;


	}

	// collect attributes from all nodes at the top level of a surface
	parseConnections( length ) {

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		this.currentForm = this.currentSurface.connections;

	}

	// surface node attribute data, e.g. specular, roughness etc
	parseEntryForm( length ) {

		this.reader.skip( 8 ); // NAME + length
		const name = this.reader.getString();
		this.currentForm = this.currentNode.attributes;

		this.setupForm( name, length );

	}

	// parse values from material - doesn't match up to other LWO3 data types
	// sub form of entry form
	parseValueForm() {

		this.reader.skip( 8 ); // unknown + length

		const valueType = this.reader.getString();

		if ( valueType === 'double' ) {

			this.currentForm.value = this.reader.getUint64();

		} else if ( valueType === 'int' ) {

			this.currentForm.value = this.reader.getUint32();

		} else if ( valueType === 'vparam' ) {

			this.reader.skip( 24 );
			this.currentForm.value = this.reader.getFloat64();

		} else if ( valueType === 'vparam3' ) {

			this.reader.skip( 24 );
			this.currentForm.value = this.reader.getFloat64Array( 3 );

		}

	}

	// holds various data about texture node image state
	// Data other than mipMapLevel unknown
	parseImageStateForm() {

		this.reader.skip( 8 ); // unknown

		this.currentForm.mipMapLevel = this.reader.getFloat32();

	}

	// LWO2 style image data node OR LWO3 textures defined at top level in editor (not as SURF node)
	parseImageMap( length ) {

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		if ( ! this.currentForm.maps ) this.currentForm.maps = [];

		const map = {};
		this.currentForm.maps.push( map );
		this.currentForm = map;

		this.reader.skip( 10 ); // unknown, could be an issue if it contains a VX

	}

	parseTextureNodeAttribute( type ) {

		this.reader.skip( 28 ); // FORM + length + VPRM + unknown + Uint32 x2 + float32

		this.reader.skip( 20 ); // FORM + length + VPVL + float32 + Uint32

		switch ( type ) {

			case 'ISCL':
				this.currentNode.scale = this.reader.getFloat32Array( 3 );
				break;
			case 'IPOS':
				this.currentNode.position = this.reader.getFloat32Array( 3 );
				break;
			case 'IROT':
				this.currentNode.rotation = this.reader.getFloat32Array( 3 );
				break;
			case 'IFAL':
				this.currentNode.falloff = this.reader.getFloat32Array( 3 );
				break;

			case 'IBMP':
				this.currentNode.amplitude = this.reader.getFloat32();
				break;
			case 'IUTD':
				this.currentNode.uTiles = this.reader.getFloat32();
				break;
			case 'IVTD':
				this.currentNode.vTiles = this.reader.getFloat32();
				break;

		}

		this.reader.skip( 2 ); // unknown


	}

	// ENVL forms are currently ignored
	parseEnvelope( length ) {

		this.reader.skip( length - 4 ); // skipping  entirely for now

	}

	///
	// CHUNK PARSING METHODS
	///

	// clips can either be defined inside a surface node, or at the top
	// level and they have a different format in each case
	parseClip( length ) {

		const tag = this.reader.getIDTag();

		// inside surface node
		if ( tag === 'FORM' ) {

			this.reader.skip( 16 );

			this.currentNode.fileName = this.reader.getString();

			return;

		}

		// otherwise top level
		this.reader.setOffset( this.reader.offset - 4 );

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		this.reader.skip( 8 ); // unknown

		const texture = {
			index: this.reader.getUint32()
		};
		this.tree.textures.push( texture );
		this.currentForm = texture;

	}

	parseClipLwo2( length ) {

		const texture = {
			index: this.reader.getUint32(),
			fileName: ''
		};

		// search STIL block
		while ( true ) {

			const tag = this.reader.getIDTag();
			const n_length = this.reader.getUint16();
			if ( tag === 'STIL' ) {

				texture.fileName = this.reader.getString();
				break;

			}

			if ( n_length >= length ) {

				break;

			}

		}

		this.tree.textures.push( texture );
		this.currentForm = texture;

	}

	parseImage() {

		this.reader.skip( 8 ); // unknown
		this.currentForm.fileName = this.reader.getString();

	}

	parseXVAL( type, length ) {

		const endOffset = this.reader.offset + length - 4;
		this.reader.skip( 8 );

		this.currentForm[ type ] = this.reader.getFloat32();

		this.reader.setOffset( endOffset ); // set end offset directly to skip optional envelope

	}

	parseXVAL3( type, length ) {

		const endOffset = this.reader.offset + length - 4;
		this.reader.skip( 8 );

		this.currentForm[ type ] = {
			x: this.reader.getFloat32(),
			y: this.reader.getFloat32(),
			z: this.reader.getFloat32(),
		};

		this.reader.setOffset( endOffset );

	}

	// Tags associated with an object
	// OTAG { type[ID4], tag-string[S0] }
	parseObjectTag() {

		if ( ! this.tree.objectTags ) this.tree.objectTags = {};

		this.tree.objectTags[ this.reader.getIDTag() ] = {
			tagString: this.reader.getString()
		};

	}

	// Signals the start of a new layer. All the data chunks which follow will be included in this layer until another layer chunk is encountered.
	// LAYR: number[U2], flags[U2], pivot[VEC12], name[S0], parent[U2]
	parseLayer( length ) {

		const number = this.reader.getUint16();
		const flags = this.reader.getUint16(); // If the least significant bit of flags is set, the layer is hidden.
		const pivot = this.reader.getFloat32Array( 3 ); // Note: this seems to be superfluous, as the geometry is translated when pivot is present
		const layer = {
			number: number,
			flags: flags, // If the least significant bit of flags is set, the layer is hidden.
			pivot: [ - pivot[ 0 ], pivot[ 1 ], pivot[ 2 ] ], // Note: this seems to be superfluous, as the geometry is translated when pivot is present
			name: this.reader.getString(),
		};

		this.tree.layers.push( layer );
		this.currentLayer = layer;

		const parsedLength = 16 + stringOffset( this.currentLayer.name ); // index ( 2 ) + flags( 2 ) + pivot( 12 ) + stringlength

		// if we have not reached then end of the layer block, there must be a parent defined
		this.currentLayer.parent = ( parsedLength < length ) ? this.reader.getUint16() : - 1; // omitted or -1 for no parent

	}

	// VEC12 * ( F4 + F4 + F4 ) array of x,y,z vectors
	// Converting from left to right handed coordinate system:
	// x -> -x and switch material FrontSide -> BackSide
	parsePoints( length ) {

		this.currentPoints = [];
		for ( let i = 0; i < length / 4; i += 3 ) {

			// x -> -x to match three.js right handed coords
			this.currentPoints.push( - this.reader.getFloat32(), this.reader.getFloat32(), this.reader.getFloat32() );

		}

	}

	// parse VMAP or VMAD
	// Associates a set of floating-point vectors with a set of points.
	// VMAP: { type[ID4], dimension[U2], name[S0], ( vert[VX], value[F4] # dimension ) * }

	// VMAD Associates a set of floating-point vectors with the vertices of specific polygons.
	// Similar to VMAP UVs, but associates with polygon vertices rather than points
	// to solve to problem of UV seams:  VMAD chunks are paired with VMAPs of the same name,
	// if they exist. The vector values in the VMAD will then replace those in the
	// corresponding VMAP, but only for calculations involving the specified polygons.
	// VMAD { type[ID4], dimension[U2], name[S0], ( vert[VX], poly[VX], value[F4] # dimension ) * }
	parseVertexMapping( length, discontinuous ) {

		const finalOffset = this.reader.offset + length;

		const channelName = this.reader.getString();

		if ( this.reader.offset === finalOffset ) {

			// then we are in a texture node and the VMAP chunk is just a reference to a UV channel name
			this.currentForm.UVChannel = channelName;
			return;

		}

		// otherwise reset to initial length and parse normal VMAP CHUNK
		this.reader.setOffset( this.reader.offset - stringOffset( channelName ) );

		const type = this.reader.getIDTag();

		this.reader.getUint16(); // dimension
		const name = this.reader.getString();

		const remainingLength = length - 6 - stringOffset( name );

		switch ( type ) {

			case 'TXUV':
				this.parseUVMapping( name, finalOffset, discontinuous );
				break;
			case 'MORF':
			case 'SPOT':
				this.parseMorphTargets( name, finalOffset, type ); // can't be discontinuous
				break;
			// unsupported VMAPs
			case 'APSL':
			case 'NORM':
			case 'WGHT':
			case 'MNVW':
			case 'PICK':
			case 'RGB ':
			case 'RGBA':
				this.reader.skip( remainingLength );
				break;
			default:
				console.warn( 'LWOLoader: unknown vertex map type: ' + type );
				this.reader.skip( remainingLength );

		}

	}

	parseUVMapping( name, finalOffset, discontinuous ) {

		const uvIndices = [];
		const polyIndices = [];
		const uvs = [];

		while ( this.reader.offset < finalOffset ) {

			uvIndices.push( this.reader.getVariableLengthIndex() );

			if ( discontinuous ) polyIndices.push( this.reader.getVariableLengthIndex() );

			uvs.push( this.reader.getFloat32(), this.reader.getFloat32() );

		}

		if ( discontinuous ) {

			if ( ! this.currentLayer.discontinuousUVs ) this.currentLayer.discontinuousUVs = {};

			this.currentLayer.discontinuousUVs[ name ] = {
				uvIndices: uvIndices,
				polyIndices: polyIndices,
				uvs: uvs,
			};

		} else {

			if ( ! this.currentLayer.uvs ) this.currentLayer.uvs = {};

			this.currentLayer.uvs[ name ] = {
				uvIndices: uvIndices,
				uvs: uvs,
			};

		}

	}

	parseMorphTargets( name, finalOffset, type ) {

		const indices = [];
		const points = [];

		type = ( type === 'MORF' ) ? 'relative' : 'absolute';

		while ( this.reader.offset < finalOffset ) {

			indices.push( this.reader.getVariableLengthIndex() );
			// z -> -z to match three.js right handed coords
			points.push( this.reader.getFloat32(), this.reader.getFloat32(), - this.reader.getFloat32() );

		}

		if ( ! this.currentLayer.morphTargets ) this.currentLayer.morphTargets = {};

		this.currentLayer.morphTargets[ name ] = {
			indices: indices,
			points: points,
			type: type,
		};

	}

	// A list of polygons for the current layer.
	// POLS { type[ID4], ( numvert+flags[U2], vert[VX] # numvert ) * }
	parsePolygonList( length ) {

		const finalOffset = this.reader.offset + length;
		const type = this.reader.getIDTag();

		const indices = [];

		// hold a list of polygon sizes, to be split up later
		const polygonDimensions = [];

		while ( this.reader.offset < finalOffset ) {

			let numverts = this.reader.getUint16();

			//const flags = numverts & 64512; // 6 high order bits are flags - ignoring for now
			numverts = numverts & 1023; // remaining ten low order bits are vertex num
			polygonDimensions.push( numverts );

			for ( let j = 0; j < numverts; j ++ ) indices.push( this.reader.getVariableLengthIndex() );

		}

		const geometryData = {
			type: type,
			vertexIndices: indices,
			polygonDimensions: polygonDimensions,
			points: this.currentPoints
		};

		// Note: assuming that all polys will be lines or points if the first is
		if ( polygonDimensions[ 0 ] === 1 ) geometryData.type = 'points';
		else if ( polygonDimensions[ 0 ] === 2 ) geometryData.type = 'lines';

		this.currentLayer.geometry = geometryData;

	}

	// Lists the tag strings that can be associated with polygons by the PTAG chunk.
	// TAGS { tag-string[S0] * }
	parseTagStrings( length ) {

		this.tree.tags = this.reader.getStringArray( length );

	}

	// Associates tags of a given type with polygons in the most recent POLS chunk.
	// PTAG { type[ID4], ( poly[VX], tag[U2] ) * }
	parsePolygonTagMapping( length ) {

		const finalOffset = this.reader.offset + length;
		const type = this.reader.getIDTag();
		if ( type === 'SURF' ) this.parseMaterialIndices( finalOffset );
		else { //PART, SMGP, COLR not supported

			this.reader.skip( length - 4 );

		}

	}

	parseMaterialIndices( finalOffset ) {

		// array holds polygon index followed by material index
		this.currentLayer.geometry.materialIndices = [];

		while ( this.reader.offset < finalOffset ) {

			const polygonIndex = this.reader.getVariableLengthIndex();
			const materialIndex = this.reader.getUint16();

			this.currentLayer.geometry.materialIndices.push( polygonIndex, materialIndex );

		}

	}

	parseUnknownCHUNK( blockID, length ) {

		console.warn( 'LWOLoader: unknown chunk type: ' + blockID + ' length: ' + length );

		// print the chunk plus some bytes padding either side
		// printBuffer( this.reader.dv.buffer, this.reader.offset - 20, length + 40 );

		const data = this.reader.getString( length );

		this.currentForm[ blockID ] = data;

	}

}
```
</details>

#### Methods

##### `parse(buffer: any): { materials: {}; layers: any[]; tags: any[]; textures: any[]; }`

<details><summary>Code</summary>

```ts
parse( buffer ) {

		this.reader = new DataViewReader( buffer );

		this.tree = {
			materials: {},
			layers: [],
			tags: [],
			textures: [],
		};

		// start out at the top level to add any data before first layer is encountered
		this.currentLayer = this.tree;
		this.currentForm = this.tree;

		this.parseTopForm();

		if ( this.tree.format === undefined ) return;

		if ( this.tree.format === 'LWO2' ) {

			this.parser = new LWO2Parser( this );
			while ( ! this.reader.endOfFile() ) this.parser.parseBlock();

		} else if ( this.tree.format === 'LWO3' ) {

			this.parser = new LWO3Parser( this );
			while ( ! this.reader.endOfFile() ) this.parser.parseBlock();

		}

		this.debugger.offset = this.reader.offset;
		this.debugger.closeForms();

		return this.tree;

	}
```
</details>

##### `parseTopForm(): void`

<details><summary>Code</summary>

```ts
parseTopForm() {

		this.debugger.offset = this.reader.offset;

		const topForm = this.reader.getIDTag();

		if ( topForm !== 'FORM' ) {

			console.warn( 'LWOLoader: Top-level FORM missing.' );
			return;

		}

		const length = this.reader.getUint32();

		this.debugger.dataOffset = this.reader.offset;
		this.debugger.length = length;

		const type = this.reader.getIDTag();

		if ( type === 'LWO2' ) {

			this.tree.format = type;

		} else if ( type === 'LWO3' ) {

			this.tree.format = type;

		}

		this.debugger.node = 0;
		this.debugger.nodeID = type;
		this.debugger.log();

		return;

	}
```
</details>

##### `parseForm(length: any): void`

<details><summary>Code</summary>

```ts
parseForm( length ) {

		const type = this.reader.getIDTag();

		switch ( type ) {

			// SKIPPED FORMS
			// if skipForm( length ) is called, the entire form and any sub forms and chunks are skipped

			case 'ISEQ': // Image sequence
			case 'ANIM': // plug in animation
			case 'STCC': // Color-cycling Still
			case 'VPVL':
			case 'VPRM':
			case 'NROT':
			case 'WRPW': // image wrap w ( for cylindrical and spherical projections)
			case 'WRPH': // image wrap h
			case 'FUNC':
			case 'FALL':
			case 'OPAC':
			case 'GRAD': // gradient texture
			case 'ENVS':
			case 'VMOP':
			case 'VMBG':

			// Car Material FORMS
			case 'OMAX':
			case 'STEX':
			case 'CKBG':
			case 'CKEY':
			case 'VMLA':
			case 'VMLB':
				this.debugger.skipped = true;
				this.skipForm( length ); // not currently supported
				break;

			// if break; is called directly, the position in the lwoTree is not created
			// any sub chunks and forms are added to the parent form instead
			case 'META':
			case 'NNDS':
			case 'NODS':
			case 'NDTA':
			case 'ADAT':
			case 'AOVS':
			case 'BLOK':

			// used by texture nodes
			case 'IBGC': // imageBackgroundColor
			case 'IOPC': // imageOpacity
			case 'IIMG': // hold reference to image path
			case 'TXTR':
				// this.setupForm( type, length );
				this.debugger.length = 4;
				this.debugger.skipped = true;
				break;

			case 'IFAL': // imageFallof
			case 'ISCL': // imageScale
			case 'IPOS': // imagePosition
			case 'IROT': // imageRotation
			case 'IBMP':
			case 'IUTD':
			case 'IVTD':
				this.parseTextureNodeAttribute( type );
				break;

			case 'ENVL':
				this.parseEnvelope( length );
				break;

				// CLIP FORM AND SUB FORMS

			case 'CLIP':
				if ( this.tree.format === 'LWO2' ) {

					this.parseForm( length );

				} else {

					this.parseClip( length );

				}

				break;

			case 'STIL':
				this.parseImage();
				break;

			case 'XREF': // clone of another STIL
				this.reader.skip( 8 ); // unknown
				this.currentForm.referenceTexture = {
					index: this.reader.getUint32(),
					refName: this.reader.getString() // internal unique ref
				};
				break;

				// Not in spec, used by texture nodes

			case 'IMST':
				this.parseImageStateForm( length );
				break;

				// SURF FORM AND SUB FORMS

			case 'SURF':
				this.parseSurfaceForm( length );
				break;

			case 'VALU': // Not in spec
				this.parseValueForm( length );
				break;

			case 'NTAG':
				this.parseSubNode( length );
				break;

			case 'ATTR': // BSDF Node Attributes
			case 'SATR': // Standard Node Attributes
				this.setupForm( 'attributes', length );
				break;

			case 'NCON':
				this.parseConnections( length );
				break;

			case 'SSHA':
				this.parentForm = this.currentForm;
				this.currentForm = this.currentSurface;
				this.setupForm( 'surfaceShader', length );
				break;

			case 'SSHD':
				this.setupForm( 'surfaceShaderData', length );
				break;

			case 'ENTR': // Not in spec
				this.parseEntryForm( length );
				break;

				// Image Map Layer

			case 'IMAP':
				this.parseImageMap( length );
				break;

			case 'TAMP':
				this.parseXVAL( 'amplitude', length );
				break;

				//Texture Mapping Form

			case 'TMAP':
				this.setupForm( 'textureMap', length );
				break;

			case 'CNTR':
				this.parseXVAL3( 'center', length );
				break;

			case 'SIZE':
				this.parseXVAL3( 'scale', length );
				break;

			case 'ROTA':
				this.parseXVAL3( 'rotation', length );
				break;

			default:
				this.parseUnknownForm( type, length );

		}

		this.debugger.node = 0;
		this.debugger.nodeID = type;
		this.debugger.log();

	}
```
</details>

##### `setupForm(type: any, length: any): void`

<details><summary>Code</summary>

```ts
setupForm( type, length ) {

		if ( ! this.currentForm ) this.currentForm = this.currentNode;

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		if ( ! this.currentForm[ type ] ) {

			this.currentForm[ type ] = {};
			this.currentForm = this.currentForm[ type ];


		} else {

			// should never see this unless there's a bug in the reader
			console.warn( 'LWOLoader: form already exists on parent: ', type, this.currentForm );

			this.currentForm = this.currentForm[ type ];

		}


	}
```
</details>

##### `skipForm(length: any): void`

<details><summary>Code</summary>

```ts
skipForm( length ) {

		this.reader.skip( length - 4 );

	}
```
</details>

##### `parseUnknownForm(type: any, length: any): void`

<details><summary>Code</summary>

```ts
parseUnknownForm( type, length ) {

		console.warn( 'LWOLoader: unknown FORM encountered: ' + type, length );

		printBuffer( this.reader.dv.buffer, this.reader.offset, length - 4 );
		this.reader.skip( length - 4 );

	}
```
</details>

##### `parseSurfaceForm(length: any): void`

<details><summary>Code</summary>

```ts
parseSurfaceForm( length ) {

		this.reader.skip( 8 ); // unknown Uint32 x2

		const name = this.reader.getString();

		const surface = {
			attributes: {}, // LWO2 style non-node attributes will go here
			connections: {},
			name: name,
			inputName: name,
			nodes: {},
			source: this.reader.getString(),
		};

		this.tree.materials[ name ] = surface;
		this.currentSurface = surface;

		this.parentForm = this.tree.materials;
		this.currentForm = surface;
		this.currentFormEnd = this.reader.offset + length;

	}
```
</details>

##### `parseSurfaceLwo2(length: any): void`

<details><summary>Code</summary>

```ts
parseSurfaceLwo2( length ) {

		const name = this.reader.getString();

		const surface = {
			attributes: {}, // LWO2 style non-node attributes will go here
			connections: {},
			name: name,
			nodes: {},
			source: this.reader.getString(),
		};

		this.tree.materials[ name ] = surface;
		this.currentSurface = surface;

		this.parentForm = this.tree.materials;
		this.currentForm = surface;
		this.currentFormEnd = this.reader.offset + length;

	}
```
</details>

##### `parseSubNode(length: any): void`

<details><summary>Code</summary>

```ts
parseSubNode( length ) {

		// parse the NRNM CHUNK of the subnode FORM to get
		// a meaningful name for the subNode
		// some subnodes can be renamed, but Input and Surface cannot

		this.reader.skip( 8 ); // NRNM + length
		const name = this.reader.getString();

		const node = {
			name: name
		};
		this.currentForm = node;
		this.currentNode = node;

		this.currentFormEnd = this.reader.offset + length;


	}
```
</details>

##### `parseConnections(length: any): void`

<details><summary>Code</summary>

```ts
parseConnections( length ) {

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		this.currentForm = this.currentSurface.connections;

	}
```
</details>

##### `parseEntryForm(length: any): void`

<details><summary>Code</summary>

```ts
parseEntryForm( length ) {

		this.reader.skip( 8 ); // NAME + length
		const name = this.reader.getString();
		this.currentForm = this.currentNode.attributes;

		this.setupForm( name, length );

	}
```
</details>

##### `parseValueForm(): void`

<details><summary>Code</summary>

```ts
parseValueForm() {

		this.reader.skip( 8 ); // unknown + length

		const valueType = this.reader.getString();

		if ( valueType === 'double' ) {

			this.currentForm.value = this.reader.getUint64();

		} else if ( valueType === 'int' ) {

			this.currentForm.value = this.reader.getUint32();

		} else if ( valueType === 'vparam' ) {

			this.reader.skip( 24 );
			this.currentForm.value = this.reader.getFloat64();

		} else if ( valueType === 'vparam3' ) {

			this.reader.skip( 24 );
			this.currentForm.value = this.reader.getFloat64Array( 3 );

		}

	}
```
</details>

##### `parseImageStateForm(): void`

<details><summary>Code</summary>

```ts
parseImageStateForm() {

		this.reader.skip( 8 ); // unknown

		this.currentForm.mipMapLevel = this.reader.getFloat32();

	}
```
</details>

##### `parseImageMap(length: any): void`

<details><summary>Code</summary>

```ts
parseImageMap( length ) {

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		if ( ! this.currentForm.maps ) this.currentForm.maps = [];

		const map = {};
		this.currentForm.maps.push( map );
		this.currentForm = map;

		this.reader.skip( 10 ); // unknown, could be an issue if it contains a VX

	}
```
</details>

##### `parseTextureNodeAttribute(type: any): void`

<details><summary>Code</summary>

```ts
parseTextureNodeAttribute( type ) {

		this.reader.skip( 28 ); // FORM + length + VPRM + unknown + Uint32 x2 + float32

		this.reader.skip( 20 ); // FORM + length + VPVL + float32 + Uint32

		switch ( type ) {

			case 'ISCL':
				this.currentNode.scale = this.reader.getFloat32Array( 3 );
				break;
			case 'IPOS':
				this.currentNode.position = this.reader.getFloat32Array( 3 );
				break;
			case 'IROT':
				this.currentNode.rotation = this.reader.getFloat32Array( 3 );
				break;
			case 'IFAL':
				this.currentNode.falloff = this.reader.getFloat32Array( 3 );
				break;

			case 'IBMP':
				this.currentNode.amplitude = this.reader.getFloat32();
				break;
			case 'IUTD':
				this.currentNode.uTiles = this.reader.getFloat32();
				break;
			case 'IVTD':
				this.currentNode.vTiles = this.reader.getFloat32();
				break;

		}

		this.reader.skip( 2 ); // unknown


	}
```
</details>

##### `parseEnvelope(length: any): void`

<details><summary>Code</summary>

```ts
parseEnvelope( length ) {

		this.reader.skip( length - 4 ); // skipping  entirely for now

	}
```
</details>

##### `parseClip(length: any): void`

<details><summary>Code</summary>

```ts
parseClip( length ) {

		const tag = this.reader.getIDTag();

		// inside surface node
		if ( tag === 'FORM' ) {

			this.reader.skip( 16 );

			this.currentNode.fileName = this.reader.getString();

			return;

		}

		// otherwise top level
		this.reader.setOffset( this.reader.offset - 4 );

		this.currentFormEnd = this.reader.offset + length;
		this.parentForm = this.currentForm;

		this.reader.skip( 8 ); // unknown

		const texture = {
			index: this.reader.getUint32()
		};
		this.tree.textures.push( texture );
		this.currentForm = texture;

	}
```
</details>

##### `parseClipLwo2(length: any): void`

<details><summary>Code</summary>

```ts
parseClipLwo2( length ) {

		const texture = {
			index: this.reader.getUint32(),
			fileName: ''
		};

		// search STIL block
		while ( true ) {

			const tag = this.reader.getIDTag();
			const n_length = this.reader.getUint16();
			if ( tag === 'STIL' ) {

				texture.fileName = this.reader.getString();
				break;

			}

			if ( n_length >= length ) {

				break;

			}

		}

		this.tree.textures.push( texture );
		this.currentForm = texture;

	}
```
</details>

##### `parseImage(): void`

<details><summary>Code</summary>

```ts
parseImage() {

		this.reader.skip( 8 ); // unknown
		this.currentForm.fileName = this.reader.getString();

	}
```
</details>

##### `parseXVAL(type: any, length: any): void`

<details><summary>Code</summary>

```ts
parseXVAL( type, length ) {

		const endOffset = this.reader.offset + length - 4;
		this.reader.skip( 8 );

		this.currentForm[ type ] = this.reader.getFloat32();

		this.reader.setOffset( endOffset ); // set end offset directly to skip optional envelope

	}
```
</details>

##### `parseXVAL3(type: any, length: any): void`

<details><summary>Code</summary>

```ts
parseXVAL3( type, length ) {

		const endOffset = this.reader.offset + length - 4;
		this.reader.skip( 8 );

		this.currentForm[ type ] = {
			x: this.reader.getFloat32(),
			y: this.reader.getFloat32(),
			z: this.reader.getFloat32(),
		};

		this.reader.setOffset( endOffset );

	}
```
</details>

##### `parseObjectTag(): void`

<details><summary>Code</summary>

```ts
parseObjectTag() {

		if ( ! this.tree.objectTags ) this.tree.objectTags = {};

		this.tree.objectTags[ this.reader.getIDTag() ] = {
			tagString: this.reader.getString()
		};

	}
```
</details>

##### `parseLayer(length: any): void`

<details><summary>Code</summary>

```ts
parseLayer( length ) {

		const number = this.reader.getUint16();
		const flags = this.reader.getUint16(); // If the least significant bit of flags is set, the layer is hidden.
		const pivot = this.reader.getFloat32Array( 3 ); // Note: this seems to be superfluous, as the geometry is translated when pivot is present
		const layer = {
			number: number,
			flags: flags, // If the least significant bit of flags is set, the layer is hidden.
			pivot: [ - pivot[ 0 ], pivot[ 1 ], pivot[ 2 ] ], // Note: this seems to be superfluous, as the geometry is translated when pivot is present
			name: this.reader.getString(),
		};

		this.tree.layers.push( layer );
		this.currentLayer = layer;

		const parsedLength = 16 + stringOffset( this.currentLayer.name ); // index ( 2 ) + flags( 2 ) + pivot( 12 ) + stringlength

		// if we have not reached then end of the layer block, there must be a parent defined
		this.currentLayer.parent = ( parsedLength < length ) ? this.reader.getUint16() : - 1; // omitted or -1 for no parent

	}
```
</details>

##### `parsePoints(length: any): void`

<details><summary>Code</summary>

```ts
parsePoints( length ) {

		this.currentPoints = [];
		for ( let i = 0; i < length / 4; i += 3 ) {

			// x -> -x to match three.js right handed coords
			this.currentPoints.push( - this.reader.getFloat32(), this.reader.getFloat32(), this.reader.getFloat32() );

		}

	}
```
</details>

##### `parseVertexMapping(length: any, discontinuous: any): void`

<details><summary>Code</summary>

```ts
parseVertexMapping( length, discontinuous ) {

		const finalOffset = this.reader.offset + length;

		const channelName = this.reader.getString();

		if ( this.reader.offset === finalOffset ) {

			// then we are in a texture node and the VMAP chunk is just a reference to a UV channel name
			this.currentForm.UVChannel = channelName;
			return;

		}

		// otherwise reset to initial length and parse normal VMAP CHUNK
		this.reader.setOffset( this.reader.offset - stringOffset( channelName ) );

		const type = this.reader.getIDTag();

		this.reader.getUint16(); // dimension
		const name = this.reader.getString();

		const remainingLength = length - 6 - stringOffset( name );

		switch ( type ) {

			case 'TXUV':
				this.parseUVMapping( name, finalOffset, discontinuous );
				break;
			case 'MORF':
			case 'SPOT':
				this.parseMorphTargets( name, finalOffset, type ); // can't be discontinuous
				break;
			// unsupported VMAPs
			case 'APSL':
			case 'NORM':
			case 'WGHT':
			case 'MNVW':
			case 'PICK':
			case 'RGB ':
			case 'RGBA':
				this.reader.skip( remainingLength );
				break;
			default:
				console.warn( 'LWOLoader: unknown vertex map type: ' + type );
				this.reader.skip( remainingLength );

		}

	}
```
</details>

##### `parseUVMapping(name: any, finalOffset: any, discontinuous: any): void`

<details><summary>Code</summary>

```ts
parseUVMapping( name, finalOffset, discontinuous ) {

		const uvIndices = [];
		const polyIndices = [];
		const uvs = [];

		while ( this.reader.offset < finalOffset ) {

			uvIndices.push( this.reader.getVariableLengthIndex() );

			if ( discontinuous ) polyIndices.push( this.reader.getVariableLengthIndex() );

			uvs.push( this.reader.getFloat32(), this.reader.getFloat32() );

		}

		if ( discontinuous ) {

			if ( ! this.currentLayer.discontinuousUVs ) this.currentLayer.discontinuousUVs = {};

			this.currentLayer.discontinuousUVs[ name ] = {
				uvIndices: uvIndices,
				polyIndices: polyIndices,
				uvs: uvs,
			};

		} else {

			if ( ! this.currentLayer.uvs ) this.currentLayer.uvs = {};

			this.currentLayer.uvs[ name ] = {
				uvIndices: uvIndices,
				uvs: uvs,
			};

		}

	}
```
</details>

##### `parseMorphTargets(name: any, finalOffset: any, type: any): void`

<details><summary>Code</summary>

```ts
parseMorphTargets( name, finalOffset, type ) {

		const indices = [];
		const points = [];

		type = ( type === 'MORF' ) ? 'relative' : 'absolute';

		while ( this.reader.offset < finalOffset ) {

			indices.push( this.reader.getVariableLengthIndex() );
			// z -> -z to match three.js right handed coords
			points.push( this.reader.getFloat32(), this.reader.getFloat32(), - this.reader.getFloat32() );

		}

		if ( ! this.currentLayer.morphTargets ) this.currentLayer.morphTargets = {};

		this.currentLayer.morphTargets[ name ] = {
			indices: indices,
			points: points,
			type: type,
		};

	}
```
</details>

##### `parsePolygonList(length: any): void`

<details><summary>Code</summary>

```ts
parsePolygonList( length ) {

		const finalOffset = this.reader.offset + length;
		const type = this.reader.getIDTag();

		const indices = [];

		// hold a list of polygon sizes, to be split up later
		const polygonDimensions = [];

		while ( this.reader.offset < finalOffset ) {

			let numverts = this.reader.getUint16();

			//const flags = numverts & 64512; // 6 high order bits are flags - ignoring for now
			numverts = numverts & 1023; // remaining ten low order bits are vertex num
			polygonDimensions.push( numverts );

			for ( let j = 0; j < numverts; j ++ ) indices.push( this.reader.getVariableLengthIndex() );

		}

		const geometryData = {
			type: type,
			vertexIndices: indices,
			polygonDimensions: polygonDimensions,
			points: this.currentPoints
		};

		// Note: assuming that all polys will be lines or points if the first is
		if ( polygonDimensions[ 0 ] === 1 ) geometryData.type = 'points';
		else if ( polygonDimensions[ 0 ] === 2 ) geometryData.type = 'lines';

		this.currentLayer.geometry = geometryData;

	}
```
</details>

##### `parseTagStrings(length: any): void`

<details><summary>Code</summary>

```ts
parseTagStrings( length ) {

		this.tree.tags = this.reader.getStringArray( length );

	}
```
</details>

##### `parsePolygonTagMapping(length: any): void`

<details><summary>Code</summary>

```ts
parsePolygonTagMapping( length ) {

		const finalOffset = this.reader.offset + length;
		const type = this.reader.getIDTag();
		if ( type === 'SURF' ) this.parseMaterialIndices( finalOffset );
		else { //PART, SMGP, COLR not supported

			this.reader.skip( length - 4 );

		}

	}
```
</details>

##### `parseMaterialIndices(finalOffset: any): void`

<details><summary>Code</summary>

```ts
parseMaterialIndices( finalOffset ) {

		// array holds polygon index followed by material index
		this.currentLayer.geometry.materialIndices = [];

		while ( this.reader.offset < finalOffset ) {

			const polygonIndex = this.reader.getVariableLengthIndex();
			const materialIndex = this.reader.getUint16();

			this.currentLayer.geometry.materialIndices.push( polygonIndex, materialIndex );

		}

	}
```
</details>

##### `parseUnknownCHUNK(blockID: any, length: any): void`

<details><summary>Code</summary>

```ts
parseUnknownCHUNK( blockID, length ) {

		console.warn( 'LWOLoader: unknown chunk type: ' + blockID + ' length: ' + length );

		// print the chunk plus some bytes padding either side
		// printBuffer( this.reader.dv.buffer, this.reader.offset - 20, length + 40 );

		const data = this.reader.getString( length );

		this.currentForm[ blockID ] = data;

	}
```
</details>

### `DataViewReader`

<details><summary>Class Code</summary>

```ts
class DataViewReader {

	constructor( buffer ) {

		this.dv = new DataView( buffer );
		this.offset = 0;
		this._textDecoder = new TextDecoder();
		this._bytes = new Uint8Array( buffer );

	}

	size() {

		return this.dv.buffer.byteLength;

	}

	setOffset( offset ) {

		if ( offset > 0 && offset < this.dv.buffer.byteLength ) {

			this.offset = offset;

		} else {

			console.error( 'LWOLoader: invalid buffer offset' );

		}

	}

	endOfFile() {

		if ( this.offset >= this.size() ) return true;
		return false;

	}

	skip( length ) {

		this.offset += length;

	}

	getUint8() {

		const value = this.dv.getUint8( this.offset );
		this.offset += 1;
		return value;

	}

	getUint16() {

		const value = this.dv.getUint16( this.offset );
		this.offset += 2;
		return value;

	}

	getInt32() {

		const value = this.dv.getInt32( this.offset, false );
		this.offset += 4;
		return value;

	}

	getUint32() {

		const value = this.dv.getUint32( this.offset, false );
		this.offset += 4;
		return value;

	}

	getUint64() {

		const low = this.getUint32();
		const high = this.getUint32();
		return high * 0x100000000 + low;

	}

	getFloat32() {

		const value = this.dv.getFloat32( this.offset, false );
		this.offset += 4;
		return value;

	}

	getFloat32Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat32() );

		}

		return a;

	}

	getFloat64() {

		const value = this.dv.getFloat64( this.offset, this.littleEndian );
		this.offset += 8;
		return value;

	}

	getFloat64Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat64() );

		}

		return a;

	}

	// get variable-length index data type
	// VX ::= index[U2] | (index + 0xFF000000)[U4]
	// If the index value is less than 65,280 (0xFF00),then VX === U2
	// otherwise VX === U4 with bits 24-31 set
	// When reading an index, if the first byte encountered is 255 (0xFF), then
	// the four-byte form is being used and the first byte should be discarded or masked out.
	getVariableLengthIndex() {

		const firstByte = this.getUint8();

		if ( firstByte === 255 ) {

			return this.getUint8() * 65536 + this.getUint8() * 256 + this.getUint8();

		}

		return firstByte * 256 + this.getUint8();

	}

	// An ID tag is a sequence of 4 bytes containing 7-bit ASCII values
	getIDTag() {

		return this.getString( 4 );

	}

	getString( size ) {

		if ( size === 0 ) return;

		const start = this.offset;

		let result;
		let length;

		if ( size ) {

			length = size;
			result = this._textDecoder.decode( new Uint8Array( this.dv.buffer, start, size ) );

		} else {

			// use 1:1 mapping of buffer to avoid redundant new array creation.
			length = this._bytes.indexOf( 0, start ) - start;

			result = this._textDecoder.decode( new Uint8Array( this.dv.buffer, start, length ) );

			// account for null byte in length
			length ++;

			// if string with terminating nullbyte is uneven, extra nullbyte is added, skip that too
			length += length % 2;

		}

		this.skip( length );

		return result;

	}

	getStringArray( size ) {

		let a = this.getString( size );
		a = a.split( '\0' );

		return a.filter( Boolean ); // return array with any empty strings removed

	}

}
```
</details>

#### Methods

##### `size(): any`

<details><summary>Code</summary>

```ts
size() {

		return this.dv.buffer.byteLength;

	}
```
</details>

##### `setOffset(offset: any): void`

<details><summary>Code</summary>

```ts
setOffset( offset ) {

		if ( offset > 0 && offset < this.dv.buffer.byteLength ) {

			this.offset = offset;

		} else {

			console.error( 'LWOLoader: invalid buffer offset' );

		}

	}
```
</details>

##### `endOfFile(): boolean`

<details><summary>Code</summary>

```ts
endOfFile() {

		if ( this.offset >= this.size() ) return true;
		return false;

	}
```
</details>

##### `skip(length: any): void`

<details><summary>Code</summary>

```ts
skip( length ) {

		this.offset += length;

	}
```
</details>

##### `getUint8(): number`

<details><summary>Code</summary>

```ts
getUint8() {

		const value = this.dv.getUint8( this.offset );
		this.offset += 1;
		return value;

	}
```
</details>

##### `getUint16(): number`

<details><summary>Code</summary>

```ts
getUint16() {

		const value = this.dv.getUint16( this.offset );
		this.offset += 2;
		return value;

	}
```
</details>

##### `getInt32(): number`

<details><summary>Code</summary>

```ts
getInt32() {

		const value = this.dv.getInt32( this.offset, false );
		this.offset += 4;
		return value;

	}
```
</details>

##### `getUint32(): number`

<details><summary>Code</summary>

```ts
getUint32() {

		const value = this.dv.getUint32( this.offset, false );
		this.offset += 4;
		return value;

	}
```
</details>

##### `getUint64(): number`

<details><summary>Code</summary>

```ts
getUint64() {

		const low = this.getUint32();
		const high = this.getUint32();
		return high * 0x100000000 + low;

	}
```
</details>

##### `getFloat32(): number`

<details><summary>Code</summary>

```ts
getFloat32() {

		const value = this.dv.getFloat32( this.offset, false );
		this.offset += 4;
		return value;

	}
```
</details>

##### `getFloat32Array(size: any): number[]`

<details><summary>Code</summary>

```ts
getFloat32Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat32() );

		}

		return a;

	}
```
</details>

##### `getFloat64(): number`

<details><summary>Code</summary>

```ts
getFloat64() {

		const value = this.dv.getFloat64( this.offset, this.littleEndian );
		this.offset += 8;
		return value;

	}
```
</details>

##### `getFloat64Array(size: any): number[]`

<details><summary>Code</summary>

```ts
getFloat64Array( size ) {

		const a = [];

		for ( let i = 0; i < size; i ++ ) {

			a.push( this.getFloat64() );

		}

		return a;

	}
```
</details>

##### `getVariableLengthIndex(): number`

<details><summary>Code</summary>

```ts
getVariableLengthIndex() {

		const firstByte = this.getUint8();

		if ( firstByte === 255 ) {

			return this.getUint8() * 65536 + this.getUint8() * 256 + this.getUint8();

		}

		return firstByte * 256 + this.getUint8();

	}
```
</details>

##### `getIDTag(): string`

<details><summary>Code</summary>

```ts
getIDTag() {

		return this.getString( 4 );

	}
```
</details>

##### `getString(size: any): string`

<details><summary>Code</summary>

```ts
getString( size ) {

		if ( size === 0 ) return;

		const start = this.offset;

		let result;
		let length;

		if ( size ) {

			length = size;
			result = this._textDecoder.decode( new Uint8Array( this.dv.buffer, start, size ) );

		} else {

			// use 1:1 mapping of buffer to avoid redundant new array creation.
			length = this._bytes.indexOf( 0, start ) - start;

			result = this._textDecoder.decode( new Uint8Array( this.dv.buffer, start, length ) );

			// account for null byte in length
			length ++;

			// if string with terminating nullbyte is uneven, extra nullbyte is added, skip that too
			length += length % 2;

		}

		this.skip( length );

		return result;

	}
```
</details>

##### `getStringArray(size: any): any`

<details><summary>Code</summary>

```ts
getStringArray( size ) {

		let a = this.getString( size );
		a = a.split( '\0' );

		return a.filter( Boolean ); // return array with any empty strings removed

	}
```
</details>

### `Debugger`

<details><summary>Class Code</summary>

```ts
class Debugger {

	constructor() {

		this.active = false;
		this.depth = 0;
		this.formList = [];
		this.offset = 0;

		this.node = 0; // 0 = FORM, 1 = CHUNK, 2 = SUBNODE
		this.nodeID = 'FORM';

		this.dataOffset = 0;
		this.length = 0;
		this.skipped = false;

	}

	enable() {

		this.active = true;

	}

	log() {

		if ( ! this.active ) return;

		let nodeType;

		switch ( this.node ) {

			case 0:
				nodeType = 'FORM';
				break;

			case 1:
				nodeType = 'CHK';
				break;

			case 2:
				nodeType = 'S-CHK';
				break;

		}

		console.log(
			'| '.repeat( this.depth ) +
			nodeType,
			this.nodeID,
			`( ${this.offset} ) -> ( ${this.dataOffset + this.length} )`,
			( ( this.node == 0 ) ? ' {' : '' ),
			( ( this.skipped ) ? 'SKIPPED' : '' ),
			( ( this.node == 0 && this.skipped ) ? '}' : '' )
		);

		if ( this.node == 0 && ! this.skipped ) {

			this.depth += 1;
			this.formList.push( this.dataOffset + this.length );

		}

		this.skipped = false;

	}

	closeForms() {

		if ( ! this.active ) return;

		for ( let i = this.formList.length - 1; i >= 0; i -- ) {

			if ( this.offset >= this.formList[ i ] ) {

				this.depth -= 1;
				console.log( '| '.repeat( this.depth ) + '}' );
				this.formList.splice( - 1, 1 );

			}

		}

	}

}
```
</details>

#### Methods

##### `enable(): void`

<details><summary>Code</summary>

```ts
enable() {

		this.active = true;

	}
```
</details>

##### `log(): void`

<details><summary>Code</summary>

```ts
log() {

		if ( ! this.active ) return;

		let nodeType;

		switch ( this.node ) {

			case 0:
				nodeType = 'FORM';
				break;

			case 1:
				nodeType = 'CHK';
				break;

			case 2:
				nodeType = 'S-CHK';
				break;

		}

		console.log(
			'| '.repeat( this.depth ) +
			nodeType,
			this.nodeID,
			`( ${this.offset} ) -> ( ${this.dataOffset + this.length} )`,
			( ( this.node == 0 ) ? ' {' : '' ),
			( ( this.skipped ) ? 'SKIPPED' : '' ),
			( ( this.node == 0 && this.skipped ) ? '}' : '' )
		);

		if ( this.node == 0 && ! this.skipped ) {

			this.depth += 1;
			this.formList.push( this.dataOffset + this.length );

		}

		this.skipped = false;

	}
```
</details>

##### `closeForms(): void`

<details><summary>Code</summary>

```ts
closeForms() {

		if ( ! this.active ) return;

		for ( let i = this.formList.length - 1; i >= 0; i -- ) {

			if ( this.offset >= this.formList[ i ] ) {

				this.depth -= 1;
				console.log( '| '.repeat( this.depth ) + '}' );
				this.formList.splice( - 1, 1 );

			}

		}

	}
```
</details>


---