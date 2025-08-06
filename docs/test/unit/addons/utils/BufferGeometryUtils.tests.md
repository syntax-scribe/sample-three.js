[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `BufferGeometryUtils.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/addons/utils/BufferGeometryUtils.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../../../../src/core/BufferGeometry.js` |
| `BufferAttribute` | `../../../../src/core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `vertices` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ - 1.0, - 1.0, 0.0, // Bottom left 1.0, - 1.0, 0.0, // Bot...` | ✗ |
| `morphVertices` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 0.0, - 1.0, 0.0, // Bottom 1.0, 0.0, 0.0, // Right 0.0, 1...` | ✗ |


---

## Functions

### `getGeometry(): BufferGeometry`

**Returns:** `BufferGeometry`

**Calls:**

- `geometry.setAttribute`

**Internal Comments:**
```
// square (x2)
```

<details><summary>Code</summary>

```typescript
() => {

	const geometry = new BufferGeometry();

	// square
	const vertices = new Float32Array( [
		- 1.0, - 1.0, 0.0, // Bottom left
		1.0, - 1.0, 0.0, // Bottom right
		1.0, 1.0, 0.0, // Top right
		- 1.0, 1.0, 0.0 // Top left
	] );

	const morphVertices = new Float32Array( [
		0.0, - 1.0, 0.0, // Bottom
		1.0, 0.0, 0.0, // Right
		0.0, 1.0, 0.0, // Top
		- 1.0, 0.0, 0.0 // Left
	] );

	geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );

	geometry.morphAttributes.position = [
		new BufferAttribute( morphVertices, 3 )
	];

	return geometry;

}
```
</details>


---