[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `InterleavedBuffer.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/core/InterleavedBuffer.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InterleavedBuffer` | `../../../../src/core/InterleavedBuffer.js` |
| `DynamicDrawUsage` | `../../../../src/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `object` | `InterleavedBuffer` | let/var | `new InterleavedBuffer()` | ✗ |
| `a` | `InterleavedBuffer` | let/var | `new InterleavedBuffer( new Float32Array( [ 1, 2, 3, 4 ] ), 2 )` | ✗ |
| `object` | `InterleavedBuffer` | let/var | `new InterleavedBuffer()` | ✗ |
| `instance` | `InterleavedBuffer` | let/var | `new InterleavedBuffer()` | ✗ |
| `array` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 7, 8, 9 ] )` | ✗ |
| `instance` | `InterleavedBuffer` | let/var | `new InterleavedBuffer( array, 3 )` | ✗ |
| `a` | `InterleavedBuffer` | let/var | `new InterleavedBuffer( new Float32Array( [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ] ), 3 )` | ✗ |
| `b` | `InterleavedBuffer` | let/var | `new InterleavedBuffer( new Float32Array( 9 ), 3 )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 4, 5, 6, 7, 8, 9, 1, 2, 3 ] )` | ✗ |
| `instance` | `InterleavedBuffer` | let/var | `new InterleavedBuffer( new Float32Array( [ 1, 2, 3, 7, 8, 9 ] ), 3 )` | ✗ |
| `a` | `InterleavedBuffer` | let/var | `new InterleavedBuffer()` | ✗ |
| `instance` | `InterleavedBuffer` | let/var | `new InterleavedBuffer( new Float32Array( [ 1, 2, 3, 7, 8, 9 ] ), 3 )` | ✗ |


---

## Functions

### `checkInstanceAgainstCopy(instance: any, copiedInstance: any, assert: any): void`

**Parameters:**

- **`instance`** `any`
- **`copiedInstance`** `any`
- **`assert`** `any`

**Returns:** `void`

**Calls:**

- `assert.ok`

<details><summary>Code</summary>

```typescript
function checkInstanceAgainstCopy( instance, copiedInstance, assert ) {

			assert.ok( copiedInstance instanceof InterleavedBuffer, 'the clone has the correct type' );

			for ( let i = 0; i < instance.array.length; i ++ ) {

				assert.ok( copiedInstance.array[ i ] === instance.array[ i ], 'array was copied' );

			}

			assert.ok( copiedInstance.stride === instance.stride, 'stride was copied' );
			assert.ok( copiedInstance.usage === DynamicDrawUsage, 'usage was copied' );

		}
```
</details>

### `func(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { }
```
</details>


---