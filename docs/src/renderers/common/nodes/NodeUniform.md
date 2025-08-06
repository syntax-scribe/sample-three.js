[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `NodeUniform.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 16 |
| 🧱 Classes | 8 |
| 📦 Imports | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/nodes/NodeUniform.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NumberUniform` | `../Uniform.js` |
| `Vector2Uniform` | `../Uniform.js` |
| `Vector3Uniform` | `../Uniform.js` |
| `Vector4Uniform` | `../Uniform.js` |
| `ColorUniform` | `../Uniform.js` |
| `Matrix2Uniform` | `../Uniform.js` |
| `Matrix3Uniform` | `../Uniform.js` |
| `Matrix4Uniform` | `../Uniform.js` |


---

## Functions

### `NumberNodeUniform.getValue(): number`

**JSDoc:**
```typescript
/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {number} The value.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

### `NumberNodeUniform.getType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Vector2NodeUniform.getValue(): Vector2`

**JSDoc:**
```typescript
/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Vector2} The value.
	 */
```

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

### `Vector2NodeUniform.getType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Vector3NodeUniform.getValue(): Vector3`

**JSDoc:**
```typescript
/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Vector3} The value.
	 */
```

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

### `Vector3NodeUniform.getType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Vector4NodeUniform.getValue(): Vector4`

**JSDoc:**
```typescript
/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Vector4} The value.
	 */
```

**Returns:** `Vector4`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

### `Vector4NodeUniform.getType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `ColorNodeUniform.getValue(): Color`

**JSDoc:**
```typescript
/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Color} The value.
	 */
```

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

### `ColorNodeUniform.getType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Matrix2NodeUniform.getValue(): Matrix2`

**JSDoc:**
```typescript
/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Matrix2} The value.
	 */
```

**Returns:** `Matrix2`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

### `Matrix2NodeUniform.getType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Matrix3NodeUniform.getValue(): Matrix3`

**JSDoc:**
```typescript
/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Matrix3} The value.
	 */
```

**Returns:** `Matrix3`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

### `Matrix3NodeUniform.getType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Matrix4NodeUniform.getValue(): Matrix4`

**JSDoc:**
```typescript
/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Matrix4} The value.
	 */
```

**Returns:** `Matrix4`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

### `Matrix4NodeUniform.getType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType() {

		return this.nodeUniform.type;

	}
```
</details>


---

## Classes

### `NumberNodeUniform`

<details><summary>Class Code</summary>

```ts
class NumberNodeUniform extends NumberUniform {

	/**
	 * Constructs a new node-based Number uniform.
	 *
	 * @param {NodeUniform} nodeUniform - The node uniform.
	 */
	constructor( nodeUniform ) {

		super( nodeUniform.name, nodeUniform.value );

		/**
		 * The node uniform.
		 *
		 * @type {NodeUniform}
		 */
		this.nodeUniform = nodeUniform;

	}

	/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {number} The value.
	 */
	getValue() {

		return this.nodeUniform.value;

	}

	/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
	getType() {

		return this.nodeUniform.type;

	}

}
```
</details>

#### Methods

##### `getValue(): number`

<details><summary>Code</summary>

```ts
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

##### `getType(): string`

<details><summary>Code</summary>

```ts
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Vector2NodeUniform`

<details><summary>Class Code</summary>

```ts
class Vector2NodeUniform extends Vector2Uniform {

	/**
	 * Constructs a new node-based Vector2 uniform.
	 *
	 * @param {NodeUniform} nodeUniform - The node uniform.
	 */
	constructor( nodeUniform ) {

		super( nodeUniform.name, nodeUniform.value );

		/**
		 * The node uniform.
		 *
		 * @type {NodeUniform}
		 */
		this.nodeUniform = nodeUniform;

	}

	/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Vector2} The value.
	 */
	getValue() {

		return this.nodeUniform.value;

	}

	/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
	getType() {

		return this.nodeUniform.type;

	}

}
```
</details>

#### Methods

##### `getValue(): Vector2`

<details><summary>Code</summary>

```ts
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

##### `getType(): string`

<details><summary>Code</summary>

```ts
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Vector3NodeUniform`

<details><summary>Class Code</summary>

```ts
class Vector3NodeUniform extends Vector3Uniform {

	/**
	 * Constructs a new node-based Vector3 uniform.
	 *
	 * @param {NodeUniform} nodeUniform - The node uniform.
	 */
	constructor( nodeUniform ) {

		super( nodeUniform.name, nodeUniform.value );

		/**
		 * The node uniform.
		 *
		 * @type {NodeUniform}
		 */
		this.nodeUniform = nodeUniform;

	}

	/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Vector3} The value.
	 */
	getValue() {

		return this.nodeUniform.value;

	}

	/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
	getType() {

		return this.nodeUniform.type;

	}

}
```
</details>

#### Methods

##### `getValue(): Vector3`

<details><summary>Code</summary>

```ts
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

##### `getType(): string`

<details><summary>Code</summary>

```ts
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Vector4NodeUniform`

<details><summary>Class Code</summary>

```ts
class Vector4NodeUniform extends Vector4Uniform {

	/**
	 * Constructs a new node-based Vector4 uniform.
	 *
	 * @param {NodeUniform} nodeUniform - The node uniform.
	 */
	constructor( nodeUniform ) {

		super( nodeUniform.name, nodeUniform.value );

		/**
		 * The node uniform.
		 *
		 * @type {NodeUniform}
		 */
		this.nodeUniform = nodeUniform;

	}

	/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Vector4} The value.
	 */
	getValue() {

		return this.nodeUniform.value;

	}

	/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
	getType() {

		return this.nodeUniform.type;

	}

}
```
</details>

#### Methods

##### `getValue(): Vector4`

<details><summary>Code</summary>

```ts
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

##### `getType(): string`

<details><summary>Code</summary>

```ts
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `ColorNodeUniform`

<details><summary>Class Code</summary>

```ts
class ColorNodeUniform extends ColorUniform {

	/**
	 * Constructs a new node-based Color uniform.
	 *
	 * @param {NodeUniform} nodeUniform - The node uniform.
	 */
	constructor( nodeUniform ) {

		super( nodeUniform.name, nodeUniform.value );

		/**
		 * The node uniform.
		 *
		 * @type {NodeUniform}
		 */
		this.nodeUniform = nodeUniform;

	}

	/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Color} The value.
	 */
	getValue() {

		return this.nodeUniform.value;

	}

	/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
	getType() {

		return this.nodeUniform.type;

	}

}
```
</details>

#### Methods

##### `getValue(): Color`

<details><summary>Code</summary>

```ts
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

##### `getType(): string`

<details><summary>Code</summary>

```ts
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Matrix2NodeUniform`

<details><summary>Class Code</summary>

```ts
class Matrix2NodeUniform extends Matrix2Uniform {

	/**
	 * Constructs a new node-based Matrix2 uniform.
	 *
	 * @param {NodeUniform} nodeUniform - The node uniform.
	 */
	constructor( nodeUniform ) {

		super( nodeUniform.name, nodeUniform.value );

		/**
		 * The node uniform.
		 *
		 * @type {NodeUniform}
		 */
		this.nodeUniform = nodeUniform;

	}

	/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Matrix2} The value.
	 */
	getValue() {

		return this.nodeUniform.value;

	}

	/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
	getType() {

		return this.nodeUniform.type;

	}

}
```
</details>

#### Methods

##### `getValue(): Matrix2`

<details><summary>Code</summary>

```ts
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

##### `getType(): string`

<details><summary>Code</summary>

```ts
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Matrix3NodeUniform`

<details><summary>Class Code</summary>

```ts
class Matrix3NodeUniform extends Matrix3Uniform {

	/**
	 * Constructs a new node-based Matrix3 uniform.
	 *
	 * @param {NodeUniform} nodeUniform - The node uniform.
	 */
	constructor( nodeUniform ) {

		super( nodeUniform.name, nodeUniform.value );

		/**
		 * The node uniform.
		 *
		 * @type {NodeUniform}
		 */
		this.nodeUniform = nodeUniform;

	}

	/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Matrix3} The value.
	 */
	getValue() {

		return this.nodeUniform.value;

	}

	/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
	getType() {

		return this.nodeUniform.type;

	}

}
```
</details>

#### Methods

##### `getValue(): Matrix3`

<details><summary>Code</summary>

```ts
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

##### `getType(): string`

<details><summary>Code</summary>

```ts
getType() {

		return this.nodeUniform.type;

	}
```
</details>

### `Matrix4NodeUniform`

<details><summary>Class Code</summary>

```ts
class Matrix4NodeUniform extends Matrix4Uniform {

	/**
	 * Constructs a new node-based Matrix4 uniform.
	 *
	 * @param {NodeUniform} nodeUniform - The node uniform.
	 */
	constructor( nodeUniform ) {

		super( nodeUniform.name, nodeUniform.value );

		/**
		 * The node uniform.
		 *
		 * @type {NodeUniform}
		 */
		this.nodeUniform = nodeUniform;

	}

	/**
	 * Overwritten to return the value of the node uniform.
	 *
	 * @return {Matrix4} The value.
	 */
	getValue() {

		return this.nodeUniform.value;

	}

	/**
	 * Returns the node uniform data type.
	 *
	 * @return {string} The data type.
	 */
	getType() {

		return this.nodeUniform.type;

	}

}
```
</details>

#### Methods

##### `getValue(): Matrix4`

<details><summary>Code</summary>

```ts
getValue() {

		return this.nodeUniform.value;

	}
```
</details>

##### `getType(): string`

<details><summary>Code</summary>

```ts
getType() {

		return this.nodeUniform.type;

	}
```
</details>


---