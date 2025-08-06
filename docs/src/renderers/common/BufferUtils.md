[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BufferUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/common/BufferUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GPU_CHUNK_BYTES` | `./Constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `floatLength` | `number` | let/var | `strideLength * count` | ✗ |
| `strideLength` | `4` | let/var | `4` | ✗ |


---

## Functions

### `getFloatLength(floatLength: number): number`

**JSDoc:**
```typescript
/**
 * This function is usually called with the length in bytes of an array buffer.
 * It returns an padded value which ensure chunk size alignment according to STD140 layout.
 *
 * @function
 * @param {number} floatLength - The buffer length.
 * @return {number} The padded length.
 */
```

**Parameters:**

- **`floatLength`** `number`

**Returns:** `number`

**Internal Comments:**
```
// ensure chunk size alignment (STD140 layout)
```

<details><summary>Code</summary>

```typescript
function getFloatLength( floatLength ) {

	// ensure chunk size alignment (STD140 layout)

	return floatLength + ( ( GPU_CHUNK_BYTES - ( floatLength % GPU_CHUNK_BYTES ) ) % GPU_CHUNK_BYTES );

}
```
</details>

### `getVectorLength(count: number, vectorLength: number): number`

**JSDoc:**
```typescript
/**
 * Given the count of vectors and their vector length, this function computes
 * a total length in bytes with buffer alignment according to STD140 layout.
 *
 * @function
 * @param {number} count - The number of vectors.
 * @param {number} [vectorLength=4] - The vector length.
 * @return {number} The padded length.
 */
```

**Parameters:**

- **`count`** `number`
- **`vectorLength`** `number`

**Returns:** `number`

**Calls:**

- `getStrideLength`
- `getFloatLength`

<details><summary>Code</summary>

```typescript
function getVectorLength( count, vectorLength = 4 ) {

	const strideLength = getStrideLength( vectorLength );

	const floatLength = strideLength * count;

	return getFloatLength( floatLength );

}
```
</details>

### `getStrideLength(vectorLength: number): number`

**JSDoc:**
```typescript
/**
 * This function is called with a vector length and ensure the computed length
 * matches a predefined stride (in this case `4`).
 *
 * @function
 * @param {number} vectorLength - The vector length.
 * @return {number} The padded length.
 */
```

**Parameters:**

- **`vectorLength`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function getStrideLength( vectorLength ) {

	const strideLength = 4;

	return vectorLength + ( ( strideLength - ( vectorLength % strideLength ) ) % strideLength );

}
```
</details>


---