[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Audio.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/audio/Audio.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Audio` | `../../../../src/audio/Audio.js` |
| `Object3D` | `../../../../src/core/Object3D.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `object` | `Audio` | let/var | `new Audio( listener )` | ✗ |
| `object` | `Audio` | let/var | `new Audio( listener )` | ✗ |
| `object` | `Audio` | let/var | `new Audio( listener )` | ✗ |


---

## Functions

### `mockListener(): { context: { createGain: () => { connect: () => void; }; }; getInput: () => void; }`

**Returns:** `{ context: { createGain: () => { connect: () => void; }; }; getInput: () => void; }`

<details><summary>Code</summary>

```typescript
function mockListener() {

			return {
				context: {
					createGain: () => {

						return {
							connect: () => {},
						};

					}
				},
				getInput: () => {},
			};

		}
```
</details>

### `createGain(): { connect: () => void; }`

**Returns:** `{ connect: () => void; }`

<details><summary>Code</summary>

```typescript
() => {

						return {
							connect: () => {},
						};

					}
```
</details>

### `connect(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `connect(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `createGain(): { connect: () => void; }`

**Returns:** `{ connect: () => void; }`

<details><summary>Code</summary>

```typescript
() => {

						return {
							connect: () => {},
						};

					}
```
</details>

### `connect(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `connect(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `getInput(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `createGain(): { connect: () => void; }`

**Returns:** `{ connect: () => void; }`

<details><summary>Code</summary>

```typescript
() => {

						return {
							connect: () => {},
						};

					}
```
</details>

### `connect(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `connect(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `createGain(): { connect: () => void; }`

**Returns:** `{ connect: () => void; }`

<details><summary>Code</summary>

```typescript
() => {

						return {
							connect: () => {},
						};

					}
```
</details>

### `connect(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `connect(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `getInput(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>


---