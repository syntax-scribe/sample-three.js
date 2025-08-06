[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LightingModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/LightingModel.js`**

## Functions

### `LightingModel.start(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * This method is intended for setting up lighting model and context data
	 * which are later used in the evaluation process.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `builder.lightsNode.setupLights`
- `builder.lightsNode.getLightNodes`
- `this.indirect`

**Internal Comments:**
```
// lights ( direct ) (x5)
// indirect (x4)
```

<details><summary>Code</summary>

```typescript
start( builder ) {

		// lights ( direct )

		builder.lightsNode.setupLights( builder, builder.lightsNode.getLightNodes( builder ) );

		// indirect

		this.indirect( builder );

	}
```
</details>

### `LightingModel.finish(): void`

**JSDoc:**
```typescript
/**
	 * This method is intended for executing final tasks like final updates
	 * to the outgoing light.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
finish( /*builder*/ ) { }
```
</details>

### `LightingModel.direct(): void`

**JSDoc:**
```typescript
/**
	 * This method is intended for implementing the direct light term and
	 * executed during the build process of directional, point and spot light nodes.
	 *
	 * @abstract
	 * @param {Object} lightData - The light data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
direct( /*lightData, builder*/ ) { }
```
</details>

### `LightingModel.directRectArea(): void`

**JSDoc:**
```typescript
/**
	 * This method is intended for implementing the direct light term for
	 * rect area light nodes.
	 *
	 * @abstract
	 * @param {Object} lightData - The light data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
directRectArea( /*lightData, builder*/ ) {}
```
</details>

### `LightingModel.indirect(): void`

**JSDoc:**
```typescript
/**
	 * This method is intended for implementing the indirect light term.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
indirect( /*builder*/ ) { }
```
</details>

### `LightingModel.ambientOcclusion(): void`

**JSDoc:**
```typescript
/**
	 * This method is intended for implementing the ambient occlusion term.
	 * Unlike other methods, this method must be called manually by the lighting
	 * model in its indirect term.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
ambientOcclusion( /*input, stack, builder*/ ) { }
```
</details>


---

## Classes

### `LightingModel`

<details><summary>Class Code</summary>

```ts
class LightingModel {

	/**
	 * This method is intended for setting up lighting model and context data
	 * which are later used in the evaluation process.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	start( builder ) {

		// lights ( direct )

		builder.lightsNode.setupLights( builder, builder.lightsNode.getLightNodes( builder ) );

		// indirect

		this.indirect( builder );

	}

	/**
	 * This method is intended for executing final tasks like final updates
	 * to the outgoing light.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	finish( /*builder*/ ) { }

	/**
	 * This method is intended for implementing the direct light term and
	 * executed during the build process of directional, point and spot light nodes.
	 *
	 * @abstract
	 * @param {Object} lightData - The light data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	direct( /*lightData, builder*/ ) { }

	/**
	 * This method is intended for implementing the direct light term for
	 * rect area light nodes.
	 *
	 * @abstract
	 * @param {Object} lightData - The light data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	directRectArea( /*lightData, builder*/ ) {}

	/**
	 * This method is intended for implementing the indirect light term.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	indirect( /*builder*/ ) { }

	/**
	 * This method is intended for implementing the ambient occlusion term.
	 * Unlike other methods, this method must be called manually by the lighting
	 * model in its indirect term.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	ambientOcclusion( /*input, stack, builder*/ ) { }

}
```
</details>

#### Methods

##### `start(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
start( builder ) {

		// lights ( direct )

		builder.lightsNode.setupLights( builder, builder.lightsNode.getLightNodes( builder ) );

		// indirect

		this.indirect( builder );

	}
```
</details>

##### `finish(): void`

<details><summary>Code</summary>

```ts
finish( /*builder*/ ) { }
```
</details>

##### `direct(): void`

<details><summary>Code</summary>

```ts
direct( /*lightData, builder*/ ) { }
```
</details>

##### `directRectArea(): void`

<details><summary>Code</summary>

```ts
directRectArea( /*lightData, builder*/ ) {}
```
</details>

##### `indirect(): void`

<details><summary>Code</summary>

```ts
indirect( /*builder*/ ) { }
```
</details>

##### `ambientOcclusion(): void`

<details><summary>Code</summary>

```ts
ambientOcclusion( /*input, stack, builder*/ ) { }
```
</details>


---