[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `zstddec.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/libs/zstddec.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `A` | `any` | let/var | `*not shown*` | ✗ |
| `I` | `any` | let/var | `*not shown*` | ✗ |
| `B` | `any` | let/var | `*not shown*` | ✗ |
| `g` | `{ env: { emscripten_notify_memory_gro...` | let/var | `{env:{emscripten_notify_memory_growth:function(A){B=new Uint8Array(I.exports....` | ✗ |
| `Q` | `any` | let/var | `A.byteLength` | ✗ |
| `C` | `"AGFzbQEAAAABpQEVYAF/AX9gAn9/AGADf39/...` | let/var | `"AGFzbQEAAAABpQEVYAF/AX9gAn9/AGADf39/AX9gBX9/f39/AX9gAX8AYAJ/fwF/YAR/f39/AX9g...` | ✗ |


---

## Functions

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `emscripten_notify_memory_growth(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(A){B=new Uint8Array(I.exports.memory.buffer)}
```
</details>

### `Q.init(): any`

**Returns:** `any`

**Calls:**

- `fetch("data:application/wasm;base64,"+C).then(A=>A.arrayBuffer()).then(A=>WebAssembly.instantiate(A,g)).then`
- `WebAssembly.instantiate(Buffer.from(C,"base64"),g).then`

<details><summary>Code</summary>

```typescript
init(){return A||(A="undefined"!=typeof fetch?fetch("data:application/wasm;base64,"+C).then(A=>A.arrayBuffer()).then(A=>WebAssembly.instantiate(A,g)).then(this._init):WebAssembly.instantiate(Buffer.from(C,"base64"),g).then(this._init),A)}
```
</details>

### `Q._init(A: any): void`

**Parameters:**

- **`A`** `any`

**Returns:** `void`

**Calls:**

- `g.env.emscripten_notify_memory_growth`

<details><summary>Code</summary>

```typescript
_init(A){I=A.instance,g.env.emscripten_notify_memory_growth(0)}
```
</details>

### `Q.decode(A: any, g: number): any`

**Parameters:**

- **`A`** `any`
- **`g`** `number`

**Returns:** `any`

**Calls:**

- `I.exports.malloc`
- `B.set`
- `Number`
- `I.exports.ZSTD_findDecompressedSize`
- `I.exports.ZSTD_decompress`
- `B.slice`
- `I.exports.free`

<details><summary>Code</summary>

```typescript
decode(A,g=0){if(!I)throw new Error("ZSTDDecoder: Await .init() before decoding.");const Q=A.byteLength,C=I.exports.malloc(Q);B.set(A,C),g=g||Number(I.exports.ZSTD_findDecompressedSize(C,Q));const E=I.exports.malloc(g),i=I.exports.ZSTD_decompress(E,g,C,Q),D=B.slice(E,E+i);return I.exports.free(C),I.exports.free(E),D}
```
</details>


---

## Classes

### `Q`

<details><summary>Class Code</summary>

```ts
class Q{init(){return A||(A="undefined"!=typeof fetch?fetch("data:application/wasm;base64,"+C).then(A=>A.arrayBuffer()).then(A=>WebAssembly.instantiate(A,g)).then(this._init):WebAssembly.instantiate(Buffer.from(C,"base64"),g).then(this._init),A)}_init(A){I=A.instance,g.env.emscripten_notify_memory_growth(0)}decode(A,g=0){if(!I)throw new Error("ZSTDDecoder: Await .init() before decoding.");const Q=A.byteLength,C=I.exports.malloc(Q);B.set(A,C),g=g||Number(I.exports.ZSTD_findDecompressedSize(C,Q));const E=I.exports.malloc(g),i=I.exports.ZSTD_decompress(E,g,C,Q),D=B.slice(E,E+i);return I.exports.free(C),I.exports.free(E),D}}
```
</details>

#### Methods

##### `init(): any`

<details><summary>Code</summary>

```ts
init(){return A||(A="undefined"!=typeof fetch?fetch("data:application/wasm;base64,"+C).then(A=>A.arrayBuffer()).then(A=>WebAssembly.instantiate(A,g)).then(this._init):WebAssembly.instantiate(Buffer.from(C,"base64"),g).then(this._init),A)}
```
</details>

##### `_init(A: any): void`

<details><summary>Code</summary>

```ts
_init(A){I=A.instance,g.env.emscripten_notify_memory_growth(0)}
```
</details>

##### `decode(A: any, g: number): any`

<details><summary>Code</summary>

```ts
decode(A,g=0){if(!I)throw new Error("ZSTDDecoder: Await .init() before decoding.");const Q=A.byteLength,C=I.exports.malloc(Q);B.set(A,C),g=g||Number(I.exports.ZSTD_findDecompressedSize(C,Q));const E=I.exports.malloc(g),i=I.exports.ZSTD_decompress(E,g,C,Q),D=B.slice(E,E+i);return I.exports.free(C),I.exports.free(E),D}
```
</details>


---