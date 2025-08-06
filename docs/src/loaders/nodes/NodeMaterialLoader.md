[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeMaterialLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/loaders/nodes/NodeMaterialLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `MaterialLoader` | `../../loaders/MaterialLoader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `nodes` | `{ [x: string]: Node.constructor; }` | let/var | `this.nodes` | ✗ |
| `inputNodes` | `any` | let/var | `json.inputNodes` | ✗ |
| `uuid` | `any` | let/var | `inputNodes[ property ]` | ✗ |
| `materialClass` | `NodeMaterial.constructor` | let/var | `this.nodeMaterials[ type ]` | ✗ |


---

## Functions

### `NodeMaterialLoader.parse(json: any): NodeMaterial`

**JSDoc:**
```typescript
/**
	 * Parses the node material from the given JSON.
	 *
	 * @param {Object} json - The JSON definition
	 * @return {NodeMaterial}. The parsed material.
	 */
```

**Parameters:**

- **`json`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `super.parse`

<details><summary>Code</summary>

```typescript
parse( json ) {

		const material = super.parse( json );

		const nodes = this.nodes;
		const inputNodes = json.inputNodes;

		for ( const property in inputNodes ) {

			const uuid = inputNodes[ property ];

			material[ property ] = nodes[ uuid ];

		}

		return material;

	}
```
</details>

### `NodeMaterialLoader.setNodes(value: { [x: string]: Node.constructor; }): NodeLoader`

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

### `NodeMaterialLoader.setNodeMaterials(value: { [x: string]: NodeMaterial.constructor; }): NodeLoader`

**JSDoc:**
```typescript
/**
	 * Defines the dictionary of node material types.
	 *
	 * @param {Object<string,NodeMaterial.constructor>} value - The node material library defined as `<classname,class>`.
	 * @return {NodeLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `{ [x: string]: NodeMaterial.constructor; }`

**Returns:** `NodeLoader`

<details><summary>Code</summary>

```typescript
setNodeMaterials( value ) {

		this.nodeMaterials = value;
		return this;

	}
```
</details>

### `NodeMaterialLoader.createMaterialFromType(type: string): Node`

**JSDoc:**
```typescript
/**
	 * Creates a node material from the given type.
	 *
	 * @param {string} type - The node material type.
	 * @return {Node} The created node material instance.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `Node`

**Calls:**

- `super.createMaterialFromType`

<details><summary>Code</summary>

```typescript
createMaterialFromType( type ) {

		const materialClass = this.nodeMaterials[ type ];

		if ( materialClass !== undefined ) {

			return new materialClass();

		}

		return super.createMaterialFromType( type );

	}
```
</details>


---

## Classes

### `NodeMaterialLoader`

<details><summary>Class Code</summary>

```ts
class NodeMaterialLoader extends MaterialLoader {

	/**
	 * Constructs a new node material loader.
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

	}

	/**
	 * Parses the node material from the given JSON.
	 *
	 * @param {Object} json - The JSON definition
	 * @return {NodeMaterial}. The parsed material.
	 */
	parse( json ) {

		const material = super.parse( json );

		const nodes = this.nodes;
		const inputNodes = json.inputNodes;

		for ( const property in inputNodes ) {

			const uuid = inputNodes[ property ];

			material[ property ] = nodes[ uuid ];

		}

		return material;

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
	 * Defines the dictionary of node material types.
	 *
	 * @param {Object<string,NodeMaterial.constructor>} value - The node material library defined as `<classname,class>`.
	 * @return {NodeLoader} A reference to this loader.
	 */
	setNodeMaterials( value ) {

		this.nodeMaterials = value;
		return this;

	}

	/**
	 * Creates a node material from the given type.
	 *
	 * @param {string} type - The node material type.
	 * @return {Node} The created node material instance.
	 */
	createMaterialFromType( type ) {

		const materialClass = this.nodeMaterials[ type ];

		if ( materialClass !== undefined ) {

			return new materialClass();

		}

		return super.createMaterialFromType( type );

	}

}
```
</details>

#### Methods

##### `parse(json: any): NodeMaterial`

<details><summary>Code</summary>

```ts
parse( json ) {

		const material = super.parse( json );

		const nodes = this.nodes;
		const inputNodes = json.inputNodes;

		for ( const property in inputNodes ) {

			const uuid = inputNodes[ property ];

			material[ property ] = nodes[ uuid ];

		}

		return material;

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

##### `setNodeMaterials(value: { [x: string]: NodeMaterial.constructor; }): NodeLoader`

<details><summary>Code</summary>

```ts
setNodeMaterials( value ) {

		this.nodeMaterials = value;
		return this;

	}
```
</details>

##### `createMaterialFromType(type: string): Node`

<details><summary>Code</summary>

```ts
createMaterialFromType( type ) {

		const materialClass = this.nodeMaterials[ type ];

		if ( materialClass !== undefined ) {

			return new materialClass();

		}

		return super.createMaterialFromType( type );

	}
```
</details>


---