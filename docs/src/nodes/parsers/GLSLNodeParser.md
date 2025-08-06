[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `GLSLNodeParser.js`

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
📂 **`src/nodes/parsers/GLSLNodeParser.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeParser` | `../core/NodeParser.js` |
| `GLSLNodeFunction` | `./GLSLNodeFunction.js` |


---

## Functions

### `GLSLNodeParser.parseFunction(source: string): GLSLNodeFunction`

**JSDoc:**
```typescript
/**
	 * The method parses the given GLSL code an returns a node function.
	 *
	 * @param {string} source - The GLSL code.
	 * @return {GLSLNodeFunction} A node function.
	 */
```

**Parameters:**

- **`source`** `string`

**Returns:** `GLSLNodeFunction`

<details><summary>Code</summary>

```typescript
parseFunction( source ) {

		return new GLSLNodeFunction( source );

	}
```
</details>


---

## Classes

### `GLSLNodeParser`

<details><summary>Class Code</summary>

```ts
class GLSLNodeParser extends NodeParser {

	/**
	 * The method parses the given GLSL code an returns a node function.
	 *
	 * @param {string} source - The GLSL code.
	 * @return {GLSLNodeFunction} A node function.
	 */
	parseFunction( source ) {

		return new GLSLNodeFunction( source );

	}

}
```
</details>

#### Methods

##### `parseFunction(source: string): GLSLNodeFunction`

<details><summary>Code</summary>

```ts
parseFunction( source ) {

		return new GLSLNodeFunction( source );

	}
```
</details>


---