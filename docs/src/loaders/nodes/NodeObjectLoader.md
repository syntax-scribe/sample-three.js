[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeObjectLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/loaders/nodes/NodeObjectLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeLoader` | `./NodeLoader.js` |
| `NodeMaterialLoader` | `./NodeMaterialLoader.js` |
| `ObjectLoader` | `../../loaders/ObjectLoader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `loader` | `NodeLoader` | let/var | `new NodeLoader()` | ✗ |
| `materials` | `{}` | let/var | `{}` | ✗ |
| `loader` | `NodeMaterialLoader` | let/var | `new NodeMaterialLoader()` | ✗ |
| `data` | `any` | let/var | `json[ i ]` | ✗ |


---

## Functions

### `NodeObjectLoader.setNodes(value: { [x: string]: Node.constructor; }): NodeObjectLoader`

**JSDoc:**
```typescript
/**
	 * Defines the dictionary of node types.
	 *
	 * @param {Object<string,Node.constructor>} value - The node library defined as `<classname,class>`.
	 * @return {NodeObjectLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `{ [x: string]: Node.constructor; }`

**Returns:** `NodeObjectLoader`

<details><summary>Code</summary>

```typescript
setNodes( value ) {

		this.nodes = value;
		return this;

	}
```
</details>

### `NodeObjectLoader.setNodeMaterials(value: { [x: string]: NodeMaterial.constructor; }): NodeObjectLoader`

**JSDoc:**
```typescript
/**
	 * Defines the dictionary of node material types.
	 *
	 * @param {Object<string,NodeMaterial.constructor>} value - The node material library defined as `<classname,class>`.
	 * @return {NodeObjectLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `{ [x: string]: NodeMaterial.constructor; }`

**Returns:** `NodeObjectLoader`

<details><summary>Code</summary>

```typescript
setNodeMaterials( value ) {

		this.nodeMaterials = value;
		return this;

	}
```
</details>

### `NodeObjectLoader.parse(json: any, onLoad: Function): Object3D`

**JSDoc:**
```typescript
/**
	 * Parses the node objects from the given JSON.
	 *
	 * @param {Object} json - The JSON definition
	 * @param {Function} onLoad - The onLoad callback function.
	 * @return {Object3D}. The parsed 3D object.
	 */
```

**Parameters:**

- **`json`** `any`
- **`onLoad`** `Function`

**Returns:** `Object3D`

**Calls:**

- `super.parse`

<details><summary>Code</summary>

```typescript
parse( json, onLoad ) {

		this._nodesJSON = json.nodes;

		const data = super.parse( json, onLoad );

		this._nodesJSON = null; // dispose

		return data;

	}
```
</details>

### `NodeObjectLoader.parseNodes(json: any[], textures: { [x: string]: Texture; }): { [x: string]: Node; }`

**JSDoc:**
```typescript
/**
	 * Parses the node objects from the given JSON and textures.
	 *
	 * @param {Object[]} json - The JSON definition
	 * @param {Object<string,Texture>} textures - The texture library.
	 * @return {Object<string,Node>}. The parsed nodes.
	 */
```

**Parameters:**

- **`json`** `any[]`
- **`textures`** `{ [x: string]: Texture; }`

**Returns:** `{ [x: string]: Node; }`

**Calls:**

- `loader.setNodes`
- `loader.setTextures`
- `loader.parseNodes`

<details><summary>Code</summary>

```typescript
parseNodes( json, textures ) {

		if ( json !== undefined ) {

			const loader = new NodeLoader();
			loader.setNodes( this.nodes );
			loader.setTextures( textures );

			return loader.parseNodes( json );

		}

		return {};

	}
```
</details>

### `NodeObjectLoader.parseMaterials(json: any, textures: { [x: string]: Texture; }): { [x: string]: NodeMaterial; }`

**JSDoc:**
```typescript
/**
	 * Parses the node objects from the given JSON and textures.
	 *
	 * @param {Object} json - The JSON definition
	 * @param {Object<string,Texture>} textures - The texture library.
	 * @return {Object<string,NodeMaterial>}. The parsed materials.
	 */
```

**Parameters:**

- **`json`** `any`
- **`textures`** `{ [x: string]: Texture; }`

**Returns:** `{ [x: string]: NodeMaterial; }`

**Calls:**

- `this.parseNodes`
- `loader.setTextures`
- `loader.setNodes`
- `loader.setNodeMaterials`
- `loader.parse`

<details><summary>Code</summary>

```typescript
parseMaterials( json, textures ) {

		const materials = {};

		if ( json !== undefined ) {

			const nodes = this.parseNodes( this._nodesJSON, textures );

			const loader = new NodeMaterialLoader();
			loader.setTextures( textures );
			loader.setNodes( nodes );
			loader.setNodeMaterials( this.nodeMaterials );

			for ( let i = 0, l = json.length; i < l; i ++ ) {

				const data = json[ i ];

				materials[ data.uuid ] = loader.parse( data );

			}

		}

		return materials;

	}
```
</details>


---

## Classes

### `NodeObjectLoader`

<details><summary>Class Code</summary>

```ts
class NodeObjectLoader extends ObjectLoader {

	/**
	 * Constructs a new node object loader.
	 *
	 * @param {LoadingManager} [manager] - A reference to a loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * Represents a dictionary of node types.
		 *
		 * @type {Object<string,Node.constructor>}
		 */
		this.nodes = {};

		/**
		 * Represents a dictionary of node material types.
		 *
		 * @type {Object<string,NodeMaterial.constructor>}
		 */
		this.nodeMaterials = {};

		/**
		 * A reference to hold the `nodes` JSON property.
		 *
		 * @private
		 * @type {?Object[]}
		 */
		this._nodesJSON = null;

	}

	/**
	 * Defines the dictionary of node types.
	 *
	 * @param {Object<string,Node.constructor>} value - The node library defined as `<classname,class>`.
	 * @return {NodeObjectLoader} A reference to this loader.
	 */
	setNodes( value ) {

		this.nodes = value;
		return this;

	}

	/**
	 * Defines the dictionary of node material types.
	 *
	 * @param {Object<string,NodeMaterial.constructor>} value - The node material library defined as `<classname,class>`.
	 * @return {NodeObjectLoader} A reference to this loader.
	 */
	setNodeMaterials( value ) {

		this.nodeMaterials = value;
		return this;

	}

	/**
	 * Parses the node objects from the given JSON.
	 *
	 * @param {Object} json - The JSON definition
	 * @param {Function} onLoad - The onLoad callback function.
	 * @return {Object3D}. The parsed 3D object.
	 */
	parse( json, onLoad ) {

		this._nodesJSON = json.nodes;

		const data = super.parse( json, onLoad );

		this._nodesJSON = null; // dispose

		return data;

	}

	/**
	 * Parses the node objects from the given JSON and textures.
	 *
	 * @param {Object[]} json - The JSON definition
	 * @param {Object<string,Texture>} textures - The texture library.
	 * @return {Object<string,Node>}. The parsed nodes.
	 */
	parseNodes( json, textures ) {

		if ( json !== undefined ) {

			const loader = new NodeLoader();
			loader.setNodes( this.nodes );
			loader.setTextures( textures );

			return loader.parseNodes( json );

		}

		return {};

	}

	/**
	 * Parses the node objects from the given JSON and textures.
	 *
	 * @param {Object} json - The JSON definition
	 * @param {Object<string,Texture>} textures - The texture library.
	 * @return {Object<string,NodeMaterial>}. The parsed materials.
	 */
	parseMaterials( json, textures ) {

		const materials = {};

		if ( json !== undefined ) {

			const nodes = this.parseNodes( this._nodesJSON, textures );

			const loader = new NodeMaterialLoader();
			loader.setTextures( textures );
			loader.setNodes( nodes );
			loader.setNodeMaterials( this.nodeMaterials );

			for ( let i = 0, l = json.length; i < l; i ++ ) {

				const data = json[ i ];

				materials[ data.uuid ] = loader.parse( data );

			}

		}

		return materials;

	}

}
```
</details>

#### Methods

##### `setNodes(value: { [x: string]: Node.constructor; }): NodeObjectLoader`

<details><summary>Code</summary>

```ts
setNodes( value ) {

		this.nodes = value;
		return this;

	}
```
</details>

##### `setNodeMaterials(value: { [x: string]: NodeMaterial.constructor; }): NodeObjectLoader`

<details><summary>Code</summary>

```ts
setNodeMaterials( value ) {

		this.nodeMaterials = value;
		return this;

	}
```
</details>

##### `parse(json: any, onLoad: Function): Object3D`

<details><summary>Code</summary>

```ts
parse( json, onLoad ) {

		this._nodesJSON = json.nodes;

		const data = super.parse( json, onLoad );

		this._nodesJSON = null; // dispose

		return data;

	}
```
</details>

##### `parseNodes(json: any[], textures: { [x: string]: Texture; }): { [x: string]: Node; }`

<details><summary>Code</summary>

```ts
parseNodes( json, textures ) {

		if ( json !== undefined ) {

			const loader = new NodeLoader();
			loader.setNodes( this.nodes );
			loader.setTextures( textures );

			return loader.parseNodes( json );

		}

		return {};

	}
```
</details>

##### `parseMaterials(json: any, textures: { [x: string]: Texture; }): { [x: string]: NodeMaterial; }`

<details><summary>Code</summary>

```ts
parseMaterials( json, textures ) {

		const materials = {};

		if ( json !== undefined ) {

			const nodes = this.parseNodes( this._nodesJSON, textures );

			const loader = new NodeMaterialLoader();
			loader.setTextures( textures );
			loader.setNodes( nodes );
			loader.setNodeMaterials( this.nodeMaterials );

			for ( let i = 0, l = json.length; i < l; i ++ ) {

				const data = json[ i ];

				materials[ data.uuid ] = loader.parse( data );

			}

		}

		return materials;

	}
```
</details>


---