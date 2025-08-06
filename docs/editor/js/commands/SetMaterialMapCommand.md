[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetMaterialMapCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/SetMaterialMapCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |
| `ObjectLoader` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `( object !== null ) ? editor.getObjectMaterial( object, materialSlot ) : null` | ✗ |
| `meta` | `{ geometries: {}; materials: {}; text...` | let/var | `{ geometries: {}, materials: {}, textures: {}, images: {} }` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `data` | `any` | let/var | `cache[ key ]` | ✗ |
| `map` | `any` | let/var | `null` | ✗ |
| `loader` | `any` | let/var | `new ObjectLoader()` | ✗ |


---

## Functions

### `SetMaterialMapCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.oldMap.dispose`
- `this.editor.getObjectMaterial`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		if ( this.oldMap !== null && this.oldMap !== undefined ) this.oldMap.dispose();

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.mapName ] = this.newMap;
		material.needsUpdate = true;

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialMapCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.getObjectMaterial`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.mapName ] = this.oldMap;
		material.needsUpdate = true;

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialMapCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`
- `serializeMap`
- `map.toJSON`
- `extractFromCache`
- `values.push`

**Internal Comments:**
```
// serializes a map (THREE.Texture)
// Note: The function 'extractFromCache' is copied from Object3D.toJSON()
// extract data from the cache hash
// remove metadata on each item
// and return as array
```

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.mapName = this.mapName;
		output.newMap = serializeMap( this.newMap );
		output.oldMap = serializeMap( this.oldMap );
		output.materialSlot = this.materialSlot;

		return output;

		// serializes a map (THREE.Texture)

		function serializeMap( map ) {

			if ( map === null || map === undefined ) return null;

			const meta = {
				geometries: {},
				materials: {},
				textures: {},
				images: {}
			};

			const json = map.toJSON( meta );
			const images = extractFromCache( meta.images );
			if ( images.length > 0 ) json.images = images;
			json.sourceFile = map.sourceFile;

			return json;

		}

		// Note: The function 'extractFromCache' is copied from Object3D.toJSON()

		// extract data from the cache hash
		// remove metadata on each item
		// and return as array
		function extractFromCache( cache ) {

			const values = [];
			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}

	}
```
</details>

### `SetMaterialMapCommand.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `super.fromJSON`
- `this.editor.objectByUuid`
- `parseTexture`
- `loader.parseImages`
- `loader.parseTextures`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.mapName = json.mapName;
		this.oldMap = parseTexture( json.oldMap );
		this.newMap = parseTexture( json.newMap );
		this.materialSlot = json.materialSlot;

		function parseTexture( json ) {

			let map = null;
			if ( json !== null ) {

				const loader = new ObjectLoader();
				const images = loader.parseImages( json.images );
				const textures = loader.parseTextures( [ json ], images );
				map = textures[ json.uuid ];
				map.sourceFile = json.sourceFile;

			}

			return map;

		}

	}
```
</details>

### `serializeMap(map: any): any`

**Parameters:**

- **`map`** `any`

**Returns:** `any`

**Calls:**

- `map.toJSON`
- `extractFromCache`

<details><summary>Code</summary>

```typescript
function serializeMap( map ) {

			if ( map === null || map === undefined ) return null;

			const meta = {
				geometries: {},
				materials: {},
				textures: {},
				images: {}
			};

			const json = map.toJSON( meta );
			const images = extractFromCache( meta.images );
			if ( images.length > 0 ) json.images = images;
			json.sourceFile = map.sourceFile;

			return json;

		}
```
</details>

### `extractFromCache(cache: any): any[]`

**Parameters:**

- **`cache`** `any`

**Returns:** `any[]`

**Calls:**

- `values.push`

<details><summary>Code</summary>

```typescript
function extractFromCache( cache ) {

			const values = [];
			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}
```
</details>

### `parseTexture(json: any): any`

**Parameters:**

- **`json`** `any`

**Returns:** `any`

**Calls:**

- `loader.parseImages`
- `loader.parseTextures`

<details><summary>Code</summary>

```typescript
function parseTexture( json ) {

			let map = null;
			if ( json !== null ) {

				const loader = new ObjectLoader();
				const images = loader.parseImages( json.images );
				const textures = loader.parseTextures( [ json ], images );
				map = textures[ json.uuid ];
				map.sourceFile = json.sourceFile;

			}

			return map;

		}
```
</details>


---

## Classes

### `SetMaterialMapCommand`

<details><summary>Class Code</summary>

```ts
class SetMaterialMapCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @param {string} [mapName='']
	 * @param {THREE.Texture|null} [newMap=null]
	 * @param {number} [materialSlot=-1]
	 * @constructor
	 */
	constructor( editor, object = null, mapName = '', newMap = null, materialSlot = - 1 ) {

		super( editor );

		this.type = 'SetMaterialMapCommand';
		this.name = editor.strings.getKey( 'command/SetMaterialMap' ) + ': ' + mapName;

		this.object = object;
		this.materialSlot = materialSlot;

		const material = ( object !== null ) ? editor.getObjectMaterial( object, materialSlot ) : null;

		this.oldMap = ( object !== null ) ? material[ mapName ] : undefined;
		this.newMap = newMap;

		this.mapName = mapName;

	}

	execute() {

		if ( this.oldMap !== null && this.oldMap !== undefined ) this.oldMap.dispose();

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.mapName ] = this.newMap;
		material.needsUpdate = true;

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}

	undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.mapName ] = this.oldMap;
		material.needsUpdate = true;

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.mapName = this.mapName;
		output.newMap = serializeMap( this.newMap );
		output.oldMap = serializeMap( this.oldMap );
		output.materialSlot = this.materialSlot;

		return output;

		// serializes a map (THREE.Texture)

		function serializeMap( map ) {

			if ( map === null || map === undefined ) return null;

			const meta = {
				geometries: {},
				materials: {},
				textures: {},
				images: {}
			};

			const json = map.toJSON( meta );
			const images = extractFromCache( meta.images );
			if ( images.length > 0 ) json.images = images;
			json.sourceFile = map.sourceFile;

			return json;

		}

		// Note: The function 'extractFromCache' is copied from Object3D.toJSON()

		// extract data from the cache hash
		// remove metadata on each item
		// and return as array
		function extractFromCache( cache ) {

			const values = [];
			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.mapName = json.mapName;
		this.oldMap = parseTexture( json.oldMap );
		this.newMap = parseTexture( json.newMap );
		this.materialSlot = json.materialSlot;

		function parseTexture( json ) {

			let map = null;
			if ( json !== null ) {

				const loader = new ObjectLoader();
				const images = loader.parseImages( json.images );
				const textures = loader.parseTextures( [ json ], images );
				map = textures[ json.uuid ];
				map.sourceFile = json.sourceFile;

			}

			return map;

		}

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		if ( this.oldMap !== null && this.oldMap !== undefined ) this.oldMap.dispose();

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.mapName ] = this.newMap;
		material.needsUpdate = true;

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.mapName ] = this.oldMap;
		material.needsUpdate = true;

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.mapName = this.mapName;
		output.newMap = serializeMap( this.newMap );
		output.oldMap = serializeMap( this.oldMap );
		output.materialSlot = this.materialSlot;

		return output;

		// serializes a map (THREE.Texture)

		function serializeMap( map ) {

			if ( map === null || map === undefined ) return null;

			const meta = {
				geometries: {},
				materials: {},
				textures: {},
				images: {}
			};

			const json = map.toJSON( meta );
			const images = extractFromCache( meta.images );
			if ( images.length > 0 ) json.images = images;
			json.sourceFile = map.sourceFile;

			return json;

		}

		// Note: The function 'extractFromCache' is copied from Object3D.toJSON()

		// extract data from the cache hash
		// remove metadata on each item
		// and return as array
		function extractFromCache( cache ) {

			const values = [];
			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}

	}
```
</details>

##### `fromJSON(json: any): void`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.mapName = json.mapName;
		this.oldMap = parseTexture( json.oldMap );
		this.newMap = parseTexture( json.newMap );
		this.materialSlot = json.materialSlot;

		function parseTexture( json ) {

			let map = null;
			if ( json !== null ) {

				const loader = new ObjectLoader();
				const images = loader.parseImages( json.images );
				const textures = loader.parseTextures( [ json ], images );
				map = textures[ json.uuid ];
				map.sourceFile = json.sourceFile;

			}

			return map;

		}

	}
```
</details>


---