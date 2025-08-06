[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `VaryingNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/VaryingNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `NodeShaderStage` | `./constants.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |
| `subBuild` | `./SubBuildNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `varying` | `any` | let/var | `properties.varying` | ✗ |
| `name` | `string` | let/var | `this.name` | ✗ |
| `interpolationType` | `string` | let/var | `this.interpolationType` | ✗ |
| `interpolationSampling` | `string` | let/var | `this.interpolationSampling` | ✗ |


---

## Functions

### `VaryingNode.setInterpolation(type: string, sampling: string): VaryingNode`

**JSDoc:**
```typescript
/**
	 * Defines the interpolation type of the varying.
	 *
	 * @param {string} type - The interpolation type.
	 * @param {?string} sampling - The interpolation sampling type
	 * @return {VaryingNode} A reference to this node.
	 */
```

**Parameters:**

- **`type`** `string`
- **`sampling`** `string`

**Returns:** `VaryingNode`

<details><summary>Code</summary>

```typescript
setInterpolation( type, sampling = null ) {

		this.interpolationType = type;
		this.interpolationSampling = sampling;

		return this;

	}
```
</details>

### `VaryingNode.getHash(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `super.getHash`

<details><summary>Code</summary>

```typescript
getHash( builder ) {

		return this.name || super.getHash( builder );

	}
```
</details>

### `VaryingNode.getNodeType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.node.getNodeType`

**Internal Comments:**
```
// VaryingNode is auto type
```

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		// VaryingNode is auto type

		return this.node.getNodeType( builder );

	}
```
</details>

### `VaryingNode.setupVarying(builder: NodeBuilder): NodeVarying`

**JSDoc:**
```typescript
/**
	 * This method performs the setup of a varying node with the current node builder.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {NodeVarying} The node varying from the node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `NodeVarying`

**Calls:**

- `builder.getNodeProperties`
- `this.getNodeType`
- `builder.getVaryingFromNode`
- `subBuild (from ./SubBuildNode.js)`

**Internal Comments:**
```
// this property can be used to check if the varying can be optimized for a variable (x4)
```

<details><summary>Code</summary>

```typescript
setupVarying( builder ) {

		const properties = builder.getNodeProperties( this );

		let varying = properties.varying;

		if ( varying === undefined ) {

			const name = this.name;
			const type = this.getNodeType( builder );
			const interpolationType = this.interpolationType;
			const interpolationSampling = this.interpolationSampling;

			properties.varying = varying = builder.getVaryingFromNode( this, name, type, interpolationType, interpolationSampling );
			properties.node = subBuild( this.node, 'VERTEX' );

		}

		// this property can be used to check if the varying can be optimized for a variable
		varying.needsInterpolation || ( varying.needsInterpolation = ( builder.shaderStage === 'fragment' ) );

		return varying;

	}
```
</details>

### `VaryingNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this.setupVarying`
- `builder.flowNodeFromShaderStage`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		this.setupVarying( builder );

		builder.flowNodeFromShaderStage( NodeShaderStage.VERTEX, this.node );

	}
```
</details>

### `VaryingNode.analyze(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this.setupVarying`
- `builder.flowNodeFromShaderStage`

<details><summary>Code</summary>

```typescript
analyze( builder ) {

		this.setupVarying( builder );

		builder.flowNodeFromShaderStage( NodeShaderStage.VERTEX, this.node );

	}
```
</details>

### `VaryingNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getSubBuildProperty`
- `builder.getNodeProperties`
- `this.setupVarying`
- `this.getNodeType`
- `builder.getPropertyName`
- `builder.flowNodeFromShaderStage`

**Internal Comments:**
```
// force node run in vertex stage (x4)
```

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const propertyKey = builder.getSubBuildProperty( 'property', builder.currentStack );
		const properties = builder.getNodeProperties( this );
		const varying = this.setupVarying( builder );

		if ( properties[ propertyKey ] === undefined ) {

			const type = this.getNodeType( builder );
			const propertyName = builder.getPropertyName( varying, NodeShaderStage.VERTEX );

			// force node run in vertex stage
			builder.flowNodeFromShaderStage( NodeShaderStage.VERTEX, properties.node, type, propertyName );

			properties[ propertyKey ] = propertyName;

		}

		return builder.getPropertyName( varying );

	}
```
</details>

### `vertexStage(node: Node): VaryingNode`

**Parameters:**

- **`node`** `Node`

**Returns:** `VaryingNode`

**Calls:**

- `varying`

<details><summary>Code</summary>

```typescript
( node ) => varying( node )
```
</details>


---

## Classes

### `VaryingNode`

<details><summary>Class Code</summary>

```ts
class VaryingNode extends Node {

	static get type() {

		return 'VaryingNode';

	}

	/**
	 * Constructs a new varying node.
	 *
	 * @param {Node} node - The node for which a varying should be created.
	 * @param {?string} name - The name of the varying in the shader.
	 */
	constructor( node, name = null ) {

		super();

		/**
		 * The node for which a varying should be created.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * The name of the varying in the shader. If no name is defined,
		 * the node system auto-generates one.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.name = name;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isVaryingNode = true;

		/**
		 * The interpolation type of the varying data.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.interpolationType = null;

		/**
		 * The interpolation sampling type of varying data.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.interpolationSampling = null;

		/**
		 * This flag is used for global cache.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

	}

	/**
	 * Defines the interpolation type of the varying.
	 *
	 * @param {string} type - The interpolation type.
	 * @param {?string} sampling - The interpolation sampling type
	 * @return {VaryingNode} A reference to this node.
	 */
	setInterpolation( type, sampling = null ) {

		this.interpolationType = type;
		this.interpolationSampling = sampling;

		return this;

	}

	getHash( builder ) {

		return this.name || super.getHash( builder );

	}

	getNodeType( builder ) {

		// VaryingNode is auto type

		return this.node.getNodeType( builder );

	}

	/**
	 * This method performs the setup of a varying node with the current node builder.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {NodeVarying} The node varying from the node builder.
	 */
	setupVarying( builder ) {

		const properties = builder.getNodeProperties( this );

		let varying = properties.varying;

		if ( varying === undefined ) {

			const name = this.name;
			const type = this.getNodeType( builder );
			const interpolationType = this.interpolationType;
			const interpolationSampling = this.interpolationSampling;

			properties.varying = varying = builder.getVaryingFromNode( this, name, type, interpolationType, interpolationSampling );
			properties.node = subBuild( this.node, 'VERTEX' );

		}

		// this property can be used to check if the varying can be optimized for a variable
		varying.needsInterpolation || ( varying.needsInterpolation = ( builder.shaderStage === 'fragment' ) );

		return varying;

	}

	setup( builder ) {

		this.setupVarying( builder );

		builder.flowNodeFromShaderStage( NodeShaderStage.VERTEX, this.node );

	}

	analyze( builder ) {

		this.setupVarying( builder );

		builder.flowNodeFromShaderStage( NodeShaderStage.VERTEX, this.node );

	}

	generate( builder ) {

		const propertyKey = builder.getSubBuildProperty( 'property', builder.currentStack );
		const properties = builder.getNodeProperties( this );
		const varying = this.setupVarying( builder );

		if ( properties[ propertyKey ] === undefined ) {

			const type = this.getNodeType( builder );
			const propertyName = builder.getPropertyName( varying, NodeShaderStage.VERTEX );

			// force node run in vertex stage
			builder.flowNodeFromShaderStage( NodeShaderStage.VERTEX, properties.node, type, propertyName );

			properties[ propertyKey ] = propertyName;

		}

		return builder.getPropertyName( varying );

	}

}
```
</details>

#### Methods

##### `setInterpolation(type: string, sampling: string): VaryingNode`

<details><summary>Code</summary>

```ts
setInterpolation( type, sampling = null ) {

		this.interpolationType = type;
		this.interpolationSampling = sampling;

		return this;

	}
```
</details>

##### `getHash(builder: any): string`

<details><summary>Code</summary>

```ts
getHash( builder ) {

		return this.name || super.getHash( builder );

	}
```
</details>

##### `getNodeType(builder: any): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		// VaryingNode is auto type

		return this.node.getNodeType( builder );

	}
```
</details>

##### `setupVarying(builder: NodeBuilder): NodeVarying`

<details><summary>Code</summary>

```ts
setupVarying( builder ) {

		const properties = builder.getNodeProperties( this );

		let varying = properties.varying;

		if ( varying === undefined ) {

			const name = this.name;
			const type = this.getNodeType( builder );
			const interpolationType = this.interpolationType;
			const interpolationSampling = this.interpolationSampling;

			properties.varying = varying = builder.getVaryingFromNode( this, name, type, interpolationType, interpolationSampling );
			properties.node = subBuild( this.node, 'VERTEX' );

		}

		// this property can be used to check if the varying can be optimized for a variable
		varying.needsInterpolation || ( varying.needsInterpolation = ( builder.shaderStage === 'fragment' ) );

		return varying;

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		this.setupVarying( builder );

		builder.flowNodeFromShaderStage( NodeShaderStage.VERTEX, this.node );

	}
```
</details>

##### `analyze(builder: any): void`

<details><summary>Code</summary>

```ts
analyze( builder ) {

		this.setupVarying( builder );

		builder.flowNodeFromShaderStage( NodeShaderStage.VERTEX, this.node );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const propertyKey = builder.getSubBuildProperty( 'property', builder.currentStack );
		const properties = builder.getNodeProperties( this );
		const varying = this.setupVarying( builder );

		if ( properties[ propertyKey ] === undefined ) {

			const type = this.getNodeType( builder );
			const propertyName = builder.getPropertyName( varying, NodeShaderStage.VERTEX );

			// force node run in vertex stage
			builder.flowNodeFromShaderStage( NodeShaderStage.VERTEX, properties.node, type, propertyName );

			properties[ propertyKey ] = propertyName;

		}

		return builder.getPropertyName( varying );

	}
```
</details>


---