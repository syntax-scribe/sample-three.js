[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `AudioListener.tests.js`

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
📂 **`test/unit/src/audio/AudioListener.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AudioListener` | `../../../../src/audio/AudioListener.js` |
| `Object3D` | `../../../../src/core/Object3D.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `object` | `AudioListener` | let/var | `new AudioListener()` | ✗ |
| `object` | `AudioListener` | let/var | `new AudioListener()` | ✗ |
| `object` | `AudioListener` | let/var | `new AudioListener()` | ✗ |


---

## Functions

### `mockWindowAudioContext(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function mockWindowAudioContext() {

			global.window = {
				AudioContext: function () {

					return {
						createGain: () => {

							return {
								connect: () => {},
							};

						}
					};

				},
			};

		}
```
</details>

### `AudioContext(): { createGain: () => { connect: () => void; }; }`

**Returns:** `{ createGain: () => { connect: () => void; }; }`

<details><summary>Code</summary>

```typescript
function () {

					return {
						createGain: () => {

							return {
								connect: () => {},
							};

						}
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

### `AudioContext(): { createGain: () => { connect: () => void; }; }`

**Returns:** `{ createGain: () => { connect: () => void; }; }`

<details><summary>Code</summary>

```typescript
function () {

					return {
						createGain: () => {

							return {
								connect: () => {},
							};

						}
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


---