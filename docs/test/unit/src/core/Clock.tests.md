[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Clock.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/core/Clock.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Clock` | `../../../../src/core/Clock.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `reference` | `typeof globalThis` | let/var | `( typeof global !== 'undefined' ) ? global : self` | ✗ |
| `object` | `Clock` | let/var | `new Clock()` | ✗ |
| `object_all` | `Clock` | let/var | `new Clock( false )` | ✗ |
| `clock` | `Clock` | let/var | `new Clock( false )` | ✗ |


---

## Functions

### `mockPerformance(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function mockPerformance() {

			const reference = ( typeof global !== 'undefined' ) ? global : self;

			reference.performance = {
				deltaTime: 0,

				next: function ( delta ) {

					this.deltaTime += delta;

				},

				now: function () {

					return this.deltaTime;

				}

			};

		}
```
</details>

### `next(delta: any): void`

**Parameters:**

- **`delta`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( delta ) {

					this.deltaTime += delta;

				}
```
</details>

### `now(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.deltaTime;

				}
```
</details>

### `next(delta: any): void`

**Parameters:**

- **`delta`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( delta ) {

					this.deltaTime += delta;

				}
```
</details>

### `now(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.deltaTime;

				}
```
</details>


---