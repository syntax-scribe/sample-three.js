[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeParser.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/NodeParser.js`**

## Functions

### `NodeParser.parseFunction(): NodeFunction`

**JSDoc:**
```typescript
/**
	 * The method parses the given native code an returns a node function.
	 *
	 * @abstract
	 * @param {string} source - The native shader code.
	 * @return {NodeFunction} A node function.
	 */
```

**Returns:** `NodeFunction`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
parseFunction( /*source*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>


---

## Classes

### `NodeParser`

<details><summary>Class Code</summary>

```ts
class NodeParser {

	/**
	 * The method parses the given native code an returns a node function.
	 *
	 * @abstract
	 * @param {string} source - The native shader code.
	 * @return {NodeFunction} A node function.
	 */
	parseFunction( /*source*/ ) {

		console.warn( 'Abstract function.' );

	}

}
```
</details>

#### Methods

##### `parseFunction(): NodeFunction`

<details><summary>Code</summary>

```ts
parseFunction( /*source*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>


---