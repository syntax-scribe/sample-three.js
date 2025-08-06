[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `mikktspace.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/libs/mikktspace.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `lTextDecoder` | `any` | let/var | `typeof TextDecoder === 'undefined' ? (0, module.require)('util').TextDecoder ...` | ✗ |
| `cachedTextDecoder` | `any` | let/var | `new lTextDecoder('utf-8', { ignoreBOM: true, fatal: true })` | ✗ |
| `cachegetUint8Memory0` | `any` | let/var | `null` | ✗ |
| `heap_next` | `number` | let/var | `heap.length` | ✗ |
| `idx` | `number` | let/var | `heap_next` | ✗ |
| `cachegetFloat32Memory0` | `any` | let/var | `null` | ✗ |
| `WASM_VECTOR_LEN` | `number` | let/var | `0` | ✗ |
| `cachegetInt32Memory0` | `any` | let/var | `null` | ✗ |
| `len0` | `number` | let/var | `WASM_VECTOR_LEN` | ✗ |
| `len1` | `number` | let/var | `WASM_VECTOR_LEN` | ✗ |
| `len2` | `number` | let/var | `WASM_VECTOR_LEN` | ✗ |
| `r0` | `any` | let/var | `getInt32Memory0()[retptr / 4 + 0]` | ✗ |
| `r1` | `any` | let/var | `getInt32Memory0()[retptr / 4 + 1]` | ✗ |
| `wasmDataURI` | `"data:application/octet-stream;base64...` | let/var | `'data:application/octet-stream;base64,AGFzbQEAAAABiQEWYAN/f38AYAJ/fwBgAn9/AX9...` | ✗ |
| `wasm` | `any` | let/var | `*not shown*` | ✓ |
| `isReady` | `boolean` | let/var | `false` | ✓ |


---

## Functions

### `getUint8Memory0(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getUint8Memory0() {
    if (cachegetUint8Memory0 === null || cachegetUint8Memory0.buffer !== wasm.memory.buffer) {
        cachegetUint8Memory0 = new Uint8Array(wasm.memory.buffer);
    }
    return cachegetUint8Memory0;
}
```
</details>

### `getStringFromWasm0(ptr: any, len: any): any`

**Parameters:**

- **`ptr`** `any`
- **`len`** `any`

**Returns:** `any`

**Calls:**

- `cachedTextDecoder.decode`
- `getUint8Memory0().subarray`

<details><summary>Code</summary>

```typescript
function getStringFromWasm0(ptr, len) {
    return cachedTextDecoder.decode(getUint8Memory0().subarray(ptr, ptr + len));
}
```
</details>

### `addHeapObject(obj: any): number`

**Parameters:**

- **`obj`** `any`

**Returns:** `number`

**Calls:**

- `heap.push`

<details><summary>Code</summary>

```typescript
function addHeapObject(obj) {
    if (heap_next === heap.length) heap.push(heap.length + 1);
    const idx = heap_next;
    heap_next = heap[idx];

    heap[idx] = obj;
    return idx;
}
```
</details>

### `getObject(idx: any): any`

**Parameters:**

- **`idx`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getObject(idx) { return heap[idx]; }
```
</details>

### `dropObject(idx: any): void`

**Parameters:**

- **`idx`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function dropObject(idx) {
    if (idx < 36) return;
    heap[idx] = heap_next;
    heap_next = idx;
}
```
</details>

### `takeObject(idx: any): any`

**Parameters:**

- **`idx`** `any`

**Returns:** `any`

**Calls:**

- `getObject`
- `dropObject`

<details><summary>Code</summary>

```typescript
function takeObject(idx) {
    const ret = getObject(idx);
    dropObject(idx);
    return ret;
}
```
</details>

### `getFloat32Memory0(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getFloat32Memory0() {
    if (cachegetFloat32Memory0 === null || cachegetFloat32Memory0.buffer !== wasm.memory.buffer) {
        cachegetFloat32Memory0 = new Float32Array(wasm.memory.buffer);
    }
    return cachegetFloat32Memory0;
}
```
</details>

### `passArrayF32ToWasm0(arg: any, malloc: any): any`

**Parameters:**

- **`arg`** `any`
- **`malloc`** `any`

**Returns:** `any`

**Calls:**

- `malloc`
- `getFloat32Memory0().set`

<details><summary>Code</summary>

```typescript
function passArrayF32ToWasm0(arg, malloc) {
    const ptr = malloc(arg.length * 4);
    getFloat32Memory0().set(arg, ptr / 4);
    WASM_VECTOR_LEN = arg.length;
    return ptr;
}
```
</details>

### `getInt32Memory0(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getInt32Memory0() {
    if (cachegetInt32Memory0 === null || cachegetInt32Memory0.buffer !== wasm.memory.buffer) {
        cachegetInt32Memory0 = new Int32Array(wasm.memory.buffer);
    }
    return cachegetInt32Memory0;
}
```
</details>

### `getArrayF32FromWasm0(ptr: any, len: any): any`

**Parameters:**

- **`ptr`** `any`
- **`len`** `any`

**Returns:** `any`

**Calls:**

- `getFloat32Memory0().subarray`

<details><summary>Code</summary>

```typescript
function getArrayF32FromWasm0(ptr, len) {
    return getFloat32Memory0().subarray(ptr / 4, ptr / 4 + len);
}
```
</details>

### `generateTangents(position: Float32Array<ArrayBufferLike>, normal: Float32Array<ArrayBufferLike>, texcoord: Float32Array<ArrayBufferLike>): Float32Array<ArrayBufferLike>`

**JSDoc:**
```typescript
/**
* Generates vertex tangents for the given position/normal/texcoord attributes.
* @param {Float32Array} position
* @param {Float32Array} normal
* @param {Float32Array} texcoord
* @returns {Float32Array}
*/
```

**Parameters:**

- **`position`** `Float32Array<ArrayBufferLike>`
- **`normal`** `Float32Array<ArrayBufferLike>`
- **`texcoord`** `Float32Array<ArrayBufferLike>`

**Returns:** `Float32Array<ArrayBufferLike>`

**Calls:**

- `wasm.__wbindgen_add_to_stack_pointer`
- `passArrayF32ToWasm0`
- `wasm.generateTangents`
- `getInt32Memory0`
- `getArrayF32FromWasm0(r0, r1).slice`
- `wasm.__wbindgen_free`

<details><summary>Code</summary>

```typescript
export function generateTangents(position, normal, texcoord) {
    try {
        const retptr = wasm.__wbindgen_add_to_stack_pointer(-16);
        var ptr0 = passArrayF32ToWasm0(position, wasm.__wbindgen_malloc);
        var len0 = WASM_VECTOR_LEN;
        var ptr1 = passArrayF32ToWasm0(normal, wasm.__wbindgen_malloc);
        var len1 = WASM_VECTOR_LEN;
        var ptr2 = passArrayF32ToWasm0(texcoord, wasm.__wbindgen_malloc);
        var len2 = WASM_VECTOR_LEN;
        wasm.generateTangents(retptr, ptr0, len0, ptr1, len1, ptr2, len2);
        var r0 = getInt32Memory0()[retptr / 4 + 0];
        var r1 = getInt32Memory0()[retptr / 4 + 1];
        var v3 = getArrayF32FromWasm0(r0, r1).slice();
        wasm.__wbindgen_free(r0, r1 * 4);
        return v3;
    } finally {
        wasm.__wbindgen_add_to_stack_pointer(16);
    }
}
```
</details>

### `__wbindgen_string_new(arg0: any, arg1: any): number`

**Parameters:**

- **`arg0`** `any`
- **`arg1`** `any`

**Returns:** `number`

**Calls:**

- `getStringFromWasm0`
- `addHeapObject`

<details><summary>Code</summary>

```typescript
function(arg0, arg1) {
    var ret = getStringFromWasm0(arg0, arg1);
    return addHeapObject(ret);
}
```
</details>

### `__wbindgen_rethrow(arg0: any): never`

**Parameters:**

- **`arg0`** `any`

**Returns:** `never`

**Calls:**

- `takeObject`

<details><summary>Code</summary>

```typescript
function(arg0) {
    throw takeObject(arg0);
}
```
</details>


---