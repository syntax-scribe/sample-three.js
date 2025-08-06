[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `AudioContext.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/audio/AudioContext.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AudioContext` | `../../../../src/audio/AudioContext.js` |


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