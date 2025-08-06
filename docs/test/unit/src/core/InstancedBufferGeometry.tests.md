[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `InstancedBufferGeometry.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/core/InstancedBufferGeometry.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InstancedBufferGeometry` | `../../../../src/core/InstancedBufferGeometry.js` |
| `BufferGeometry` | `../../../../src/core/BufferGeometry.js` |
| `BufferAttribute` | `../../../../src/core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `object` | `InstancedBufferGeometry` | let/var | `new InstancedBufferGeometry()` | ✗ |
| `object` | `InstancedBufferGeometry` | let/var | `new InstancedBufferGeometry()` | ✗ |
| `object` | `InstancedBufferGeometry` | let/var | `new InstancedBufferGeometry()` | ✗ |
| `object` | `InstancedBufferGeometry` | let/var | `new InstancedBufferGeometry()` | ✗ |
| `instanceMock1` | `{}` | let/var | `{}` | ✗ |
| `instanceMock2` | `{}` | let/var | `{}` | ✗ |
| `defaultAttribute1` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1 ] ) )` | ✗ |
| `defaultAttribute2` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 2 ] ) )` | ✗ |
| `instance` | `InstancedBufferGeometry` | let/var | `new InstancedBufferGeometry()` | ✗ |


---

## Functions

### `createClonableMock(): { callCount: number; clone: () => ...; }`

**Returns:** `{ callCount: number; clone: () => ...; }`

<details><summary>Code</summary>

```typescript
function createClonableMock() {

			return {
				callCount: 0,
				clone: function () {

					this.callCount ++;
					return this;

				}
			};

		}
```
</details>

### `clone(): { callCount: number; clone: () => ...; }`

**Returns:** `{ callCount: number; clone: () => ...; }`

<details><summary>Code</summary>

```typescript
function () {

					this.callCount ++;
					return this;

				}
```
</details>

### `clone(): { callCount: number; clone: () => ...; }`

**Returns:** `{ callCount: number; clone: () => ...; }`

<details><summary>Code</summary>

```typescript
function () {

					this.callCount ++;
					return this;

				}
```
</details>


---