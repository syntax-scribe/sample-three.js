[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Layers.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/Layers.js`**

## Functions

### `Layers.set(layer: number): void`

**JSDoc:**
```typescript
/**
	 * Sets membership to the given layer, and remove membership all other layers.
	 *
	 * @param {number} layer - The layer to set.
	 */
```

**Parameters:**

- **`layer`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set( layer ) {

		this.mask = ( 1 << layer | 0 ) >>> 0;

	}
```
</details>

### `Layers.enable(layer: number): void`

**JSDoc:**
```typescript
/**
	 * Adds membership of the given layer.
	 *
	 * @param {number} layer - The layer to enable.
	 */
```

**Parameters:**

- **`layer`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
enable( layer ) {

		this.mask |= 1 << layer | 0;

	}
```
</details>

### `Layers.enableAll(): void`

**JSDoc:**
```typescript
/**
	 * Adds membership to all layers.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
enableAll() {

		this.mask = 0xffffffff | 0;

	}
```
</details>

### `Layers.toggle(layer: number): void`

**JSDoc:**
```typescript
/**
	 * Toggles the membership of the given layer.
	 *
	 * @param {number} layer - The layer to toggle.
	 */
```

**Parameters:**

- **`layer`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
toggle( layer ) {

		this.mask ^= 1 << layer | 0;

	}
```
</details>

### `Layers.disable(layer: number): void`

**JSDoc:**
```typescript
/**
	 * Removes membership of the given layer.
	 *
	 * @param {number} layer - The layer to enable.
	 */
```

**Parameters:**

- **`layer`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
disable( layer ) {

		this.mask &= ~ ( 1 << layer | 0 );

	}
```
</details>

### `Layers.disableAll(): void`

**JSDoc:**
```typescript
/**
	 * Removes the membership from all layers.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
disableAll() {

		this.mask = 0;

	}
```
</details>

### `Layers.test(layers: Layers): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this and the given layers object have at least one
	 * layer in common.
	 *
	 * @param {Layers} layers - The layers to test.
	 * @return {boolean } Whether this and the given layers object have at least one layer in common or not.
	 */
```

**Parameters:**

- **`layers`** `Layers`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
test( layers ) {

		return ( this.mask & layers.mask ) !== 0;

	}
```
</details>

### `Layers.isEnabled(layer: number): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given layer is enabled.
	 *
	 * @param {number} layer - The layer to test.
	 * @return {boolean } Whether the given layer is enabled or not.
	 */
```

**Parameters:**

- **`layer`** `number`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isEnabled( layer ) {

		return ( this.mask & ( 1 << layer | 0 ) ) !== 0;

	}
```
</details>


---

## Classes

### `Layers`

<details><summary>Class Code</summary>

```ts
class Layers {

	/**
	 * Constructs a new layers instance, with membership
	 * initially set to layer `0`.
	 */
	constructor() {

		/**
		 * A bit mask storing which of the 32 layers this layers object is currently
		 * a member of.
		 *
		 * @type {number}
		 */
		this.mask = 1 | 0;

	}

	/**
	 * Sets membership to the given layer, and remove membership all other layers.
	 *
	 * @param {number} layer - The layer to set.
	 */
	set( layer ) {

		this.mask = ( 1 << layer | 0 ) >>> 0;

	}

	/**
	 * Adds membership of the given layer.
	 *
	 * @param {number} layer - The layer to enable.
	 */
	enable( layer ) {

		this.mask |= 1 << layer | 0;

	}

	/**
	 * Adds membership to all layers.
	 */
	enableAll() {

		this.mask = 0xffffffff | 0;

	}

	/**
	 * Toggles the membership of the given layer.
	 *
	 * @param {number} layer - The layer to toggle.
	 */
	toggle( layer ) {

		this.mask ^= 1 << layer | 0;

	}

	/**
	 * Removes membership of the given layer.
	 *
	 * @param {number} layer - The layer to enable.
	 */
	disable( layer ) {

		this.mask &= ~ ( 1 << layer | 0 );

	}

	/**
	 * Removes the membership from all layers.
	 */
	disableAll() {

		this.mask = 0;

	}

	/**
	 * Returns `true` if this and the given layers object have at least one
	 * layer in common.
	 *
	 * @param {Layers} layers - The layers to test.
	 * @return {boolean } Whether this and the given layers object have at least one layer in common or not.
	 */
	test( layers ) {

		return ( this.mask & layers.mask ) !== 0;

	}

	/**
	 * Returns `true` if the given layer is enabled.
	 *
	 * @param {number} layer - The layer to test.
	 * @return {boolean } Whether the given layer is enabled or not.
	 */
	isEnabled( layer ) {

		return ( this.mask & ( 1 << layer | 0 ) ) !== 0;

	}

}
```
</details>

#### Methods

##### `set(layer: number): void`

<details><summary>Code</summary>

```ts
set( layer ) {

		this.mask = ( 1 << layer | 0 ) >>> 0;

	}
```
</details>

##### `enable(layer: number): void`

<details><summary>Code</summary>

```ts
enable( layer ) {

		this.mask |= 1 << layer | 0;

	}
```
</details>

##### `enableAll(): void`

<details><summary>Code</summary>

```ts
enableAll() {

		this.mask = 0xffffffff | 0;

	}
```
</details>

##### `toggle(layer: number): void`

<details><summary>Code</summary>

```ts
toggle( layer ) {

		this.mask ^= 1 << layer | 0;

	}
```
</details>

##### `disable(layer: number): void`

<details><summary>Code</summary>

```ts
disable( layer ) {

		this.mask &= ~ ( 1 << layer | 0 );

	}
```
</details>

##### `disableAll(): void`

<details><summary>Code</summary>

```ts
disableAll() {

		this.mask = 0;

	}
```
</details>

##### `test(layers: Layers): boolean`

<details><summary>Code</summary>

```ts
test( layers ) {

		return ( this.mask & layers.mask ) !== 0;

	}
```
</details>

##### `isEnabled(layer: number): boolean`

<details><summary>Code</summary>

```ts
isEnabled( layer ) {

		return ( this.mask & ( 1 << layer | 0 ) ) !== 0;

	}
```
</details>


---