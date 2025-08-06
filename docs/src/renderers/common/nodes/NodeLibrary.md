[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `NodeLibrary.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/nodes/NodeLibrary.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `nodeMaterial` | `any` | let/var | `null` | ✗ |


---

## Functions

### `NodeLibrary.fromMaterial(material: Material): NodeMaterial`

**JSDoc:**
```typescript
/**
	 * Returns a matching node material instance for the given material object.
	 *
	 * This method also assigns/copies the properties of the given material object
	 * to the node material. This is done to make sure the current material
	 * configuration carries over to the node version.
	 *
	 * @param {Material} material - A material.
	 * @return {NodeMaterial} The corresponding node material.
	 */
```

**Parameters:**

- **`material`** `Material`

**Returns:** `NodeMaterial`

**Calls:**

- `this.getMaterialNodeClass`

<details><summary>Code</summary>

```typescript
fromMaterial( material ) {

		if ( material.isNodeMaterial ) return material;

		let nodeMaterial = null;

		const nodeMaterialClass = this.getMaterialNodeClass( material.type );

		if ( nodeMaterialClass !== null ) {

			nodeMaterial = new nodeMaterialClass();

			for ( const key in material ) {

				nodeMaterial[ key ] = material[ key ];

			}

		}

		return nodeMaterial;

	}
```
</details>

### `NodeLibrary.addToneMapping(toneMappingNode: Function, toneMapping: number): void`

**JSDoc:**
```typescript
/**
	 * Adds a tone mapping node function for a tone mapping technique (constant).
	 *
	 * @param {Function} toneMappingNode - The tone mapping node function.
	 * @param {number} toneMapping - The tone mapping.
	 */
```

**Parameters:**

- **`toneMappingNode`** `Function`
- **`toneMapping`** `number`

**Returns:** `void`

**Calls:**

- `this.addType`

<details><summary>Code</summary>

```typescript
addToneMapping( toneMappingNode, toneMapping ) {

		this.addType( toneMappingNode, toneMapping, this.toneMappingNodes );

	}
```
</details>

### `NodeLibrary.getToneMappingFunction(toneMapping: number): Function`

**JSDoc:**
```typescript
/**
	 * Returns a tone mapping node function for a tone mapping technique (constant).
	 *
	 * @param {number} toneMapping - The tone mapping.
	 * @return {?Function} The tone mapping node function. Returns `null` if no node function is found.
	 */
```

**Parameters:**

- **`toneMapping`** `number`

**Returns:** `Function`

**Calls:**

- `this.toneMappingNodes.get`

<details><summary>Code</summary>

```typescript
getToneMappingFunction( toneMapping ) {

		return this.toneMappingNodes.get( toneMapping ) || null;

	}
```
</details>

### `NodeLibrary.getMaterialNodeClass(materialType: string): NodeMaterial.constructor`

**JSDoc:**
```typescript
/**
	 * Returns a node material class definition for a material type.
	 *
	 * @param {string} materialType - The material type.
	 * @return {?NodeMaterial.constructor} The node material class definition. Returns `null` if no node material is found.
	 */
```

**Parameters:**

- **`materialType`** `string`

**Returns:** `NodeMaterial.constructor`

**Calls:**

- `this.materialNodes.get`

<details><summary>Code</summary>

```typescript
getMaterialNodeClass( materialType ) {

		return this.materialNodes.get( materialType ) || null;

	}
```
</details>

### `NodeLibrary.addMaterial(materialNodeClass: NodeMaterial.constructor, materialClassType: string): void`

**JSDoc:**
```typescript
/**
	 * Adds a node material class definition for a given material type.
	 *
	 * @param {NodeMaterial.constructor} materialNodeClass - The node material class definition.
	 * @param {string} materialClassType - The material type.
	 */
```

**Parameters:**

- **`materialNodeClass`** `NodeMaterial.constructor`
- **`materialClassType`** `string`

**Returns:** `void`

**Calls:**

- `this.addType`

<details><summary>Code</summary>

```typescript
addMaterial( materialNodeClass, materialClassType ) {

		this.addType( materialNodeClass, materialClassType, this.materialNodes );

	}
```
</details>

### `NodeLibrary.getLightNodeClass(light: Light.constructor): AnalyticLightNode.constructor`

**JSDoc:**
```typescript
/**
	 * Returns a light node class definition for a light class definition.
	 *
	 * @param {Light.constructor} light - The light class definition.
	 * @return {?AnalyticLightNode.constructor} The light node class definition. Returns `null` if no light node is found.
	 */
```

**Parameters:**

- **`light`** `Light.constructor`

**Returns:** `AnalyticLightNode.constructor`

**Calls:**

- `this.lightNodes.get`

<details><summary>Code</summary>

```typescript
getLightNodeClass( light ) {

		return this.lightNodes.get( light ) || null;

	}
```
</details>

### `NodeLibrary.addLight(lightNodeClass: AnalyticLightNode.constructor, lightClass: Light.constructor): void`

**JSDoc:**
```typescript
/**
	 * Adds a light node class definition for a given light class definition.
	 *
	 * @param {AnalyticLightNode.constructor} lightNodeClass - The light node class definition.
	 * @param {Light.constructor} lightClass - The light class definition.
	 */
```

**Parameters:**

- **`lightNodeClass`** `AnalyticLightNode.constructor`
- **`lightClass`** `Light.constructor`

**Returns:** `void`

**Calls:**

- `this.addClass`

<details><summary>Code</summary>

```typescript
addLight( lightNodeClass, lightClass ) {

		this.addClass( lightNodeClass, lightClass, this.lightNodes );

	}
```
</details>

### `NodeLibrary.addType(nodeClass: any, type: string | number, library: Map<any, any>): void`

**JSDoc:**
```typescript
/**
	 * Adds a node class definition for the given type to the provided type library.
	 *
	 * @param {any} nodeClass - The node class definition.
	 * @param {number|string} type - The object type.
	 * @param {Map} library - The type library.
	 */
```

**Parameters:**

- **`nodeClass`** `any`
- **`type`** `string | number`
- **`library`** `Map<any, any>`

**Returns:** `void`

**Calls:**

- `library.has`
- `console.warn`
- `library.set`

<details><summary>Code</summary>

```typescript
addType( nodeClass, type, library ) {

		if ( library.has( type ) ) {

			console.warn( `Redefinition of node ${ type }` );
			return;

		}

		if ( typeof nodeClass !== 'function' ) throw new Error( `Node class ${ nodeClass.name } is not a class.` );
		if ( typeof type === 'function' || typeof type === 'object' ) throw new Error( `Base class ${ type } is not a class.` );

		library.set( type, nodeClass );

	}
```
</details>

### `NodeLibrary.addClass(nodeClass: any, baseClass: any, library: WeakMap<any, any>): void`

**JSDoc:**
```typescript
/**
	 * Adds a node class definition for the given class definition to the provided type library.
	 *
	 * @param {any} nodeClass - The node class definition.
	 * @param {any} baseClass - The class definition.
	 * @param {WeakMap} library - The type library.
	 */
```

**Parameters:**

- **`nodeClass`** `any`
- **`baseClass`** `any`
- **`library`** `WeakMap<any, any>`

**Returns:** `void`

**Calls:**

- `library.has`
- `console.warn`
- `library.set`

<details><summary>Code</summary>

```typescript
addClass( nodeClass, baseClass, library ) {

		if ( library.has( baseClass ) ) {

			console.warn( `Redefinition of node ${ baseClass.name }` );
			return;

		}

		if ( typeof nodeClass !== 'function' ) throw new Error( `Node class ${ nodeClass.name } is not a class.` );
		if ( typeof baseClass !== 'function' ) throw new Error( `Base class ${ baseClass.name } is not a class.` );

		library.set( baseClass, nodeClass );

	}
```
</details>


---

## Classes

### `NodeLibrary`

<details><summary>Class Code</summary>

```ts
class NodeLibrary {

	/**
	 * Constructs a new node library.
	 */
	constructor() {

		/**
		 * A weak map that maps lights to light nodes.
		 *
		 * @type {WeakMap<Light.constructor,AnalyticLightNode.constructor>}
		 */
		this.lightNodes = new WeakMap();

		/**
		 * A map that maps materials to node materials.
		 *
		 * @type {Map<string,NodeMaterial.constructor>}
		 */
		this.materialNodes = new Map();

		/**
		 * A map that maps tone mapping techniques (constants)
		 * to tone mapping node functions.
		 *
		 * @type {Map<number,Function>}
		 */
		this.toneMappingNodes = new Map();

	}

	/**
	 * Returns a matching node material instance for the given material object.
	 *
	 * This method also assigns/copies the properties of the given material object
	 * to the node material. This is done to make sure the current material
	 * configuration carries over to the node version.
	 *
	 * @param {Material} material - A material.
	 * @return {NodeMaterial} The corresponding node material.
	 */
	fromMaterial( material ) {

		if ( material.isNodeMaterial ) return material;

		let nodeMaterial = null;

		const nodeMaterialClass = this.getMaterialNodeClass( material.type );

		if ( nodeMaterialClass !== null ) {

			nodeMaterial = new nodeMaterialClass();

			for ( const key in material ) {

				nodeMaterial[ key ] = material[ key ];

			}

		}

		return nodeMaterial;

	}

	/**
	 * Adds a tone mapping node function for a tone mapping technique (constant).
	 *
	 * @param {Function} toneMappingNode - The tone mapping node function.
	 * @param {number} toneMapping - The tone mapping.
	 */
	addToneMapping( toneMappingNode, toneMapping ) {

		this.addType( toneMappingNode, toneMapping, this.toneMappingNodes );

	}

	/**
	 * Returns a tone mapping node function for a tone mapping technique (constant).
	 *
	 * @param {number} toneMapping - The tone mapping.
	 * @return {?Function} The tone mapping node function. Returns `null` if no node function is found.
	 */
	getToneMappingFunction( toneMapping ) {

		return this.toneMappingNodes.get( toneMapping ) || null;

	}

	/**
	 * Returns a node material class definition for a material type.
	 *
	 * @param {string} materialType - The material type.
	 * @return {?NodeMaterial.constructor} The node material class definition. Returns `null` if no node material is found.
	 */
	getMaterialNodeClass( materialType ) {

		return this.materialNodes.get( materialType ) || null;

	}

	/**
	 * Adds a node material class definition for a given material type.
	 *
	 * @param {NodeMaterial.constructor} materialNodeClass - The node material class definition.
	 * @param {string} materialClassType - The material type.
	 */
	addMaterial( materialNodeClass, materialClassType ) {

		this.addType( materialNodeClass, materialClassType, this.materialNodes );

	}

	/**
	 * Returns a light node class definition for a light class definition.
	 *
	 * @param {Light.constructor} light - The light class definition.
	 * @return {?AnalyticLightNode.constructor} The light node class definition. Returns `null` if no light node is found.
	 */
	getLightNodeClass( light ) {

		return this.lightNodes.get( light ) || null;

	}

	/**
	 * Adds a light node class definition for a given light class definition.
	 *
	 * @param {AnalyticLightNode.constructor} lightNodeClass - The light node class definition.
	 * @param {Light.constructor} lightClass - The light class definition.
	 */
	addLight( lightNodeClass, lightClass ) {

		this.addClass( lightNodeClass, lightClass, this.lightNodes );

	}

	/**
	 * Adds a node class definition for the given type to the provided type library.
	 *
	 * @param {any} nodeClass - The node class definition.
	 * @param {number|string} type - The object type.
	 * @param {Map} library - The type library.
	 */
	addType( nodeClass, type, library ) {

		if ( library.has( type ) ) {

			console.warn( `Redefinition of node ${ type }` );
			return;

		}

		if ( typeof nodeClass !== 'function' ) throw new Error( `Node class ${ nodeClass.name } is not a class.` );
		if ( typeof type === 'function' || typeof type === 'object' ) throw new Error( `Base class ${ type } is not a class.` );

		library.set( type, nodeClass );

	}

	/**
	 * Adds a node class definition for the given class definition to the provided type library.
	 *
	 * @param {any} nodeClass - The node class definition.
	 * @param {any} baseClass - The class definition.
	 * @param {WeakMap} library - The type library.
	 */
	addClass( nodeClass, baseClass, library ) {

		if ( library.has( baseClass ) ) {

			console.warn( `Redefinition of node ${ baseClass.name }` );
			return;

		}

		if ( typeof nodeClass !== 'function' ) throw new Error( `Node class ${ nodeClass.name } is not a class.` );
		if ( typeof baseClass !== 'function' ) throw new Error( `Base class ${ baseClass.name } is not a class.` );

		library.set( baseClass, nodeClass );

	}

}
```
</details>

#### Methods

##### `fromMaterial(material: Material): NodeMaterial`

<details><summary>Code</summary>

```ts
fromMaterial( material ) {

		if ( material.isNodeMaterial ) return material;

		let nodeMaterial = null;

		const nodeMaterialClass = this.getMaterialNodeClass( material.type );

		if ( nodeMaterialClass !== null ) {

			nodeMaterial = new nodeMaterialClass();

			for ( const key in material ) {

				nodeMaterial[ key ] = material[ key ];

			}

		}

		return nodeMaterial;

	}
```
</details>

##### `addToneMapping(toneMappingNode: Function, toneMapping: number): void`

<details><summary>Code</summary>

```ts
addToneMapping( toneMappingNode, toneMapping ) {

		this.addType( toneMappingNode, toneMapping, this.toneMappingNodes );

	}
```
</details>

##### `getToneMappingFunction(toneMapping: number): Function`

<details><summary>Code</summary>

```ts
getToneMappingFunction( toneMapping ) {

		return this.toneMappingNodes.get( toneMapping ) || null;

	}
```
</details>

##### `getMaterialNodeClass(materialType: string): NodeMaterial.constructor`

<details><summary>Code</summary>

```ts
getMaterialNodeClass( materialType ) {

		return this.materialNodes.get( materialType ) || null;

	}
```
</details>

##### `addMaterial(materialNodeClass: NodeMaterial.constructor, materialClassType: string): void`

<details><summary>Code</summary>

```ts
addMaterial( materialNodeClass, materialClassType ) {

		this.addType( materialNodeClass, materialClassType, this.materialNodes );

	}
```
</details>

##### `getLightNodeClass(light: Light.constructor): AnalyticLightNode.constructor`

<details><summary>Code</summary>

```ts
getLightNodeClass( light ) {

		return this.lightNodes.get( light ) || null;

	}
```
</details>

##### `addLight(lightNodeClass: AnalyticLightNode.constructor, lightClass: Light.constructor): void`

<details><summary>Code</summary>

```ts
addLight( lightNodeClass, lightClass ) {

		this.addClass( lightNodeClass, lightClass, this.lightNodes );

	}
```
</details>

##### `addType(nodeClass: any, type: string | number, library: Map<any, any>): void`

<details><summary>Code</summary>

```ts
addType( nodeClass, type, library ) {

		if ( library.has( type ) ) {

			console.warn( `Redefinition of node ${ type }` );
			return;

		}

		if ( typeof nodeClass !== 'function' ) throw new Error( `Node class ${ nodeClass.name } is not a class.` );
		if ( typeof type === 'function' || typeof type === 'object' ) throw new Error( `Base class ${ type } is not a class.` );

		library.set( type, nodeClass );

	}
```
</details>

##### `addClass(nodeClass: any, baseClass: any, library: WeakMap<any, any>): void`

<details><summary>Code</summary>

```ts
addClass( nodeClass, baseClass, library ) {

		if ( library.has( baseClass ) ) {

			console.warn( `Redefinition of node ${ baseClass.name }` );
			return;

		}

		if ( typeof nodeClass !== 'function' ) throw new Error( `Node class ${ nodeClass.name } is not a class.` );
		if ( typeof baseClass !== 'function' ) throw new Error( `Base class ${ baseClass.name } is not a class.` );

		library.set( baseClass, nodeClass );

	}
```
</details>


---