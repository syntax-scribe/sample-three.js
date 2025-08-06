[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Arrays.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/accessors/Arrays.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `StorageInstancedBufferAttribute` | `../../renderers/common/StorageInstancedBufferAttribute.js` |
| `StorageBufferAttribute` | `../../renderers/common/StorageBufferAttribute.js` |
| `storage` | `./StorageBufferNode.js` |
| `getLengthFromType` | `../core/NodeUtils.js` |
| `getTypedArrayFromType` | `../core/NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `itemSize` | `any` | let/var | `*not shown*` | ✗ |
| `typedArray` | `any` | let/var | `*not shown*` | ✗ |
| `buffer` | `StorageBufferAttribute` | let/var | `new StorageBufferAttribute( count, itemSize, typedArray )` | ✗ |
| `itemSize` | `any` | let/var | `*not shown*` | ✗ |
| `typedArray` | `any` | let/var | `*not shown*` | ✗ |
| `buffer` | `StorageInstancedBufferAttribute` | let/var | `new StorageInstancedBufferAttribute( count, itemSize, typedArray )` | ✗ |


---

## Functions

### `attributeArray(count: any, type: any): StorageBufferNode`

**Parameters:**

- **`count`** `any`
- **`type`** `any`

**Returns:** `StorageBufferNode`

**Calls:**

- `type.layout.getLength`
- `getTypedArrayFromType (from ../core/NodeUtils.js)`
- `getLengthFromType (from ../core/NodeUtils.js)`
- `storage (from ./StorageBufferNode.js)`

<details><summary>Code</summary>

```typescript
( count, type = 'float' ) => {

	let itemSize, typedArray;

	if ( type.isStruct === true ) {

		itemSize = type.layout.getLength();
		typedArray = getTypedArrayFromType( 'float' );

	} else {

		itemSize = getLengthFromType( type );
		typedArray = getTypedArrayFromType( type );

	}

	const buffer = new StorageBufferAttribute( count, itemSize, typedArray );
	const node = storage( buffer, type, count );

	return node;

}
```
</details>

### `instancedArray(count: any, type: any): StorageBufferNode`

**Parameters:**

- **`count`** `any`
- **`type`** `any`

**Returns:** `StorageBufferNode`

**Calls:**

- `type.layout.getLength`
- `getTypedArrayFromType (from ../core/NodeUtils.js)`
- `getLengthFromType (from ../core/NodeUtils.js)`
- `storage (from ./StorageBufferNode.js)`

<details><summary>Code</summary>

```typescript
( count, type = 'float' ) => {

	let itemSize, typedArray;

	if ( type.isStruct === true ) {

		itemSize = type.layout.getLength();
		typedArray = getTypedArrayFromType( 'float' );

	} else {

		itemSize = getLengthFromType( type );
		typedArray = getTypedArrayFromType( type );

	}

	const buffer = new StorageInstancedBufferAttribute( count, itemSize, typedArray );
	const node = storage( buffer, type, count );

	return node;

}
```
</details>


---