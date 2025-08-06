[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/loaders/nodes/NodeLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `nodeObject` | `../../nodes/tsl/TSLBase.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `Loader` | `../Loader.js` |
| `FileLoader` | `../../loaders/FileLoader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `loader` | `FileLoader` | let/var | `new FileLoader( this.manager )` | ✗ |
| `nodes` | `{}` | let/var | `{}` | ✗ |
| `meta` | `{ nodes: {}; textures: { [x: string]:...` | let/var | `{ nodes, textures: this.textures }` | ✗ |
| `node` | `any` | let/var | `nodes[ nodeJSON.uuid ]` | ✗ |
| `meta` | `{ nodes: { [x: string]: Node; }; text...` | let/var | `{ nodes, textures: this.textures }` | ✗ |


---

## Functions

### `NodeLoader.load(url: string, onLoad: Function, onProgress: Function, onError: Function): void`

**JSDoc:**
```typescript
/**
	 * Loads the node definitions from the given URL.
	 *
	 * @param {string} url - The path/URL of the file to be loaded.
	 * @param {Function} onLoad - Will be called when load completes.
	 * @param {Function} onProgress - Will be called while load progresses.
	 * @param {Function} onError - Will be called when errors are thrown during the loading process.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `Function`
- **`onProgress`** `Function`
- **`onError`** `Function`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `onLoad`
- `this.parse`
- `JSON.parse`
- `onError`
- `console.error`
- `this.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, ( text ) => {

			try {

				onLoad( this.parse( JSON.parse( text ) ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				this.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `NodeLoader.parseNodes(json: any[]): { [x: string]: Node; }`

**JSDoc:**
```typescript
/**
	 * Parse the node dependencies for the loaded node.
	 *
	 * @param {Array<Object>} [json] - The JSON definition
	 * @return {Object<string,Node>} A dictionary with node dependencies.
	 */
```

**Parameters:**

- **`json`** `any[]`

**Returns:** `{ [x: string]: Node; }`

**Calls:**

- `this.createNodeFromType`
- `node.deserialize`

<details><summary>Code</summary>

```typescript
parseNodes( json ) {

		const nodes = {};

		if ( json !== undefined ) {

			for ( const nodeJSON of json ) {

				const { uuid, type } = nodeJSON;

				nodes[ uuid ] = this.createNodeFromType( type );
				nodes[ uuid ].uuid = uuid;

			}

			const meta = { nodes, textures: this.textures };

			for ( const nodeJSON of json ) {

				nodeJSON.meta = meta;

				const node = nodes[ nodeJSON.uuid ];
				node.deserialize( nodeJSON );

				delete nodeJSON.meta;

			}

		}

		return nodes;

	}
```
</details>

### `NodeLoader.parse(json: { type: string; uuid: string; nodes?: any[]; meta?: any; }): Node`

**JSDoc:**
```typescript
/**
	 * Parses the node from the given JSON.
	 *
	 * @param {Object} json - The JSON definition
	 * @param {string} json.type - The node type.
	 * @param {string} json.uuid - The node UUID.
	 * @param {Array<Object>} [json.nodes] - The node dependencies.
	 * @param {Object} [json.meta] - The meta data.
	 * @return {Node} The parsed node.
	 */
```

**Parameters:**

- **`json`** `{ type: string; uuid: string; nodes?: any[]; meta?: any; }`

**Returns:** `Node`

**Calls:**

- `this.createNodeFromType`
- `this.parseNodes`
- `node.deserialize`

<details><summary>Code</summary>

```typescript
parse( json ) {

		const node = this.createNodeFromType( json.type );
		node.uuid = json.uuid;

		const nodes = this.parseNodes( json.nodes );
		const meta = { nodes, textures: this.textures };

		json.meta = meta;

		node.deserialize( json );

		delete json.meta;

		return node;

	}
```
</details>

### `NodeLoader.setTextures(value: { [x: string]: Texture; }): NodeLoader`

**JSDoc:**
```typescript
/**
	 * Defines the dictionary of textures.
	 *
	 * @param {Object<string,Texture>} value - The texture library defines as `<uuid,texture>`.
	 * @return {NodeLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `{ [x: string]: Texture; }`

**Returns:** `NodeLoader`

<details><summary>Code</summary>

```typescript
setTextures( value ) {

		this.textures = value;
		return this;

	}
```
</details>

### `NodeLoader.setNodes(value: { [x: string]: Node.constructor; }): NodeLoader`

**JSDoc:**
```typescript
/**
	 * Defines the dictionary of node types.
	 *
	 * @param {Object<string,Node.constructor>} value - The node library defined as `<classname,class>`.
	 * @return {NodeLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `{ [x: string]: Node.constructor; }`

**Returns:** `NodeLoader`

<details><summary>Code</summary>

```typescript
setNodes( value ) {

		this.nodes = value;
		return this;

	}
```
</details>

### `NodeLoader.createNodeFromType(type: string): Node`

**JSDoc:**
```typescript
/**
	 * Creates a node object from the given type.
	 *
	 * @param {string} type - The node type.
	 * @return {Node} The created node instance.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `Node`

**Calls:**

- `console.error`
- `float (from ../../nodes/tsl/TSLBase.js)`
- `nodeObject (from ../../nodes/tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
createNodeFromType( type ) {

		if ( this.nodes[ type ] === undefined ) {

			console.error( 'THREE.NodeLoader: Node type not found:', type );
			return float();

		}

		return nodeObject( new this.nodes[ type ]() );

	}
```
</details>


---

## Classes

### `NodeLoader`

<details><summary>Class Code</summary>

```ts
class NodeLoader extends Loader {

	/**
	 * Constructs a new node loader.
	 *
	 * @param {LoadingManager} [manager] - A reference to a loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * Represents a dictionary of textures.
		 *
		 * @type {Object<string,Texture>}
		 */
		this.textures = {};

		/**
		 * Represents a dictionary of node types.
		 *
		 * @type {Object<string,Node.constructor>}
		 */
		this.nodes = {};

	}

	/**
	 * Loads the node definitions from the given URL.
	 *
	 * @param {string} url - The path/URL of the file to be loaded.
	 * @param {Function} onLoad - Will be called when load completes.
	 * @param {Function} onProgress - Will be called while load progresses.
	 * @param {Function} onError - Will be called when errors are thrown during the loading process.
	 */
	load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, ( text ) => {

			try {

				onLoad( this.parse( JSON.parse( text ) ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				this.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Parse the node dependencies for the loaded node.
	 *
	 * @param {Array<Object>} [json] - The JSON definition
	 * @return {Object<string,Node>} A dictionary with node dependencies.
	 */
	parseNodes( json ) {

		const nodes = {};

		if ( json !== undefined ) {

			for ( const nodeJSON of json ) {

				const { uuid, type } = nodeJSON;

				nodes[ uuid ] = this.createNodeFromType( type );
				nodes[ uuid ].uuid = uuid;

			}

			const meta = { nodes, textures: this.textures };

			for ( const nodeJSON of json ) {

				nodeJSON.meta = meta;

				const node = nodes[ nodeJSON.uuid ];
				node.deserialize( nodeJSON );

				delete nodeJSON.meta;

			}

		}

		return nodes;

	}

	/**
	 * Parses the node from the given JSON.
	 *
	 * @param {Object} json - The JSON definition
	 * @param {string} json.type - The node type.
	 * @param {string} json.uuid - The node UUID.
	 * @param {Array<Object>} [json.nodes] - The node dependencies.
	 * @param {Object} [json.meta] - The meta data.
	 * @return {Node} The parsed node.
	 */
	parse( json ) {

		const node = this.createNodeFromType( json.type );
		node.uuid = json.uuid;

		const nodes = this.parseNodes( json.nodes );
		const meta = { nodes, textures: this.textures };

		json.meta = meta;

		node.deserialize( json );

		delete json.meta;

		return node;

	}

	/**
	 * Defines the dictionary of textures.
	 *
	 * @param {Object<string,Texture>} value - The texture library defines as `<uuid,texture>`.
	 * @return {NodeLoader} A reference to this loader.
	 */
	setTextures( value ) {

		this.textures = value;
		return this;

	}

	/**
	 * Defines the dictionary of node types.
	 *
	 * @param {Object<string,Node.constructor>} value - The node library defined as `<classname,class>`.
	 * @return {NodeLoader} A reference to this loader.
	 */
	setNodes( value ) {

		this.nodes = value;
		return this;

	}

	/**
	 * Creates a node object from the given type.
	 *
	 * @param {string} type - The node type.
	 * @return {Node} The created node instance.
	 */
	createNodeFromType( type ) {

		if ( this.nodes[ type ] === undefined ) {

			console.error( 'THREE.NodeLoader: Node type not found:', type );
			return float();

		}

		return nodeObject( new this.nodes[ type ]() );

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: Function, onProgress: Function, onError: Function): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, ( text ) => {

			try {

				onLoad( this.parse( JSON.parse( text ) ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				this.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `parseNodes(json: any[]): { [x: string]: Node; }`

<details><summary>Code</summary>

```ts
parseNodes( json ) {

		const nodes = {};

		if ( json !== undefined ) {

			for ( const nodeJSON of json ) {

				const { uuid, type } = nodeJSON;

				nodes[ uuid ] = this.createNodeFromType( type );
				nodes[ uuid ].uuid = uuid;

			}

			const meta = { nodes, textures: this.textures };

			for ( const nodeJSON of json ) {

				nodeJSON.meta = meta;

				const node = nodes[ nodeJSON.uuid ];
				node.deserialize( nodeJSON );

				delete nodeJSON.meta;

			}

		}

		return nodes;

	}
```
</details>

##### `parse(json: { type: string; uuid: string; nodes?: any[]; meta?: any; }): Node`

<details><summary>Code</summary>

```ts
parse( json ) {

		const node = this.createNodeFromType( json.type );
		node.uuid = json.uuid;

		const nodes = this.parseNodes( json.nodes );
		const meta = { nodes, textures: this.textures };

		json.meta = meta;

		node.deserialize( json );

		delete json.meta;

		return node;

	}
```
</details>

##### `setTextures(value: { [x: string]: Texture; }): NodeLoader`

<details><summary>Code</summary>

```ts
setTextures( value ) {

		this.textures = value;
		return this;

	}
```
</details>

##### `setNodes(value: { [x: string]: Node.constructor; }): NodeLoader`

<details><summary>Code</summary>

```ts
setNodes( value ) {

		this.nodes = value;
		return this;

	}
```
</details>

##### `createNodeFromType(type: string): Node`

<details><summary>Code</summary>

```ts
createNodeFromType( type ) {

		if ( this.nodes[ type ] === undefined ) {

			console.error( 'THREE.NodeLoader: Node type not found:', type );
			return float();

		}

		return nodeObject( new this.nodes[ type ]() );

	}
```
</details>


---