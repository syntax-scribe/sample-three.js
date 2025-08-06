[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WGSLNodeParser.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/nodes/WGSLNodeParser.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeParser` | `../../../nodes/core/NodeParser.js` |
| `WGSLNodeFunction` | `./WGSLNodeFunction.js` |


---

## Functions

### `WGSLNodeParser.parseFunction(source: string): WGSLNodeFunction`

**JSDoc:**
```typescript
/**
	 * The method parses the given WGSL code an returns a node function.
	 *
	 * @param {string} source - The WGSL code.
	 * @return {WGSLNodeFunction} A node function.
	 */
```

**Parameters:**

- **`source`** `string`

**Returns:** `WGSLNodeFunction`

<details><summary>Code</summary>

```typescript
parseFunction( source ) {

		return new WGSLNodeFunction( source );

	}
```
</details>


---

## Classes

### `WGSLNodeParser`

<details><summary>Class Code</summary>

```ts
class WGSLNodeParser extends NodeParser {

	/**
	 * The method parses the given WGSL code an returns a node function.
	 *
	 * @param {string} source - The WGSL code.
	 * @return {WGSLNodeFunction} A node function.
	 */
	parseFunction( source ) {

		return new WGSLNodeFunction( source );

	}

}
```
</details>

#### Methods

##### `parseFunction(source: string): WGSLNodeFunction`

<details><summary>Code</summary>

```ts
parseFunction( source ) {

		return new WGSLNodeFunction( source );

	}
```
</details>


---