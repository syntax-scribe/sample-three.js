[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `meshopt_decoder.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 30 |
| 📊 Variables & Constants | 25 |
| ⚡ Async/Await Patterns | 2 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/libs/meshopt_decoder.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `wasm_base` | `string` | let/var | `'b9H79Tebbbe8Fv9Gbb9Gvuuuuueu9Giuuub9Geueu9Giuuueuikqbeeedddillviebeoweuec:q:...` | ✗ |
| `wasm_simd` | `string` | let/var | `'b9H79TebbbeKl9Gbb9Gvuuuuueu9Giuuub9Geueuikqbbebeedddilve9Weeeviebeoweuec:q:6...` | ✗ |
| `detector` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array([ 0, 97, 115, 109, 1, 0, 0, 0, 1, 4, 1, 96, 0, 0, 3, 3, 2, 0, ...` | ✗ |
| `wasmpack` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array([ 32, 0, 65, 2, 1, 106, 34, 33, 3, 128, 11, 4, 13, 64, 6, 253,...` | ✗ |
| `wasm` | `any` | let/var | `WebAssembly.validate(detector) ? unpack(wasm_simd) : unpack(wasm_base)` | ✗ |
| `instance` | `any` | let/var | `*not shown*` | ✗ |
| `result` | `Uint8Array<any>` | let/var | `new Uint8Array(data.length)` | ✗ |
| `write` | `number` | let/var | `0` | ✗ |
| `sbrk` | `any` | let/var | `instance.exports.sbrk` | ✗ |
| `count4` | `number` | let/var | `(count + 3) & ~3` | ✗ |
| `heap` | `Uint8Array<any>` | let/var | `new Uint8Array(instance.exports.memory.buffer)` | ✗ |
| `filters` | `{ NONE: string; OCTAHEDRAL: string; Q...` | let/var | `{ NONE: '', OCTAHEDRAL: 'meshopt_decodeFilterOct', QUATERNION: 'meshopt_decod...` | ✗ |
| `decoders` | `{ ATTRIBUTES: string; TRIANGLES: stri...` | let/var | `{ ATTRIBUTES: 'meshopt_decodeVertexBuffer', TRIANGLES: 'meshopt_decodeIndexBu...` | ✗ |
| `workers` | `any[]` | let/var | `[]` | ✗ |
| `requestId` | `number` | let/var | `0` | ✗ |
| `worker` | `{ object: Worker; pending: number; re...` | let/var | `{ object: new Worker(url), pending: 0, requests: {}, }` | ✗ |
| `data` | `any` | let/var | `event.data` | ✗ |
| `source` | `string` | let/var | `'self.ready = WebAssembly.instantiate(new Uint8Array([' + new Uint8Array(wasm...` | ✗ |
| `blob` | `Blob` | let/var | `new Blob([source], { type: 'text/javascript' })` | ✗ |
| `worker` | `any` | let/var | `workers[0]` | ✗ |
| `data` | `Uint8Array<any>` | let/var | `new Uint8Array(source)` | ✗ |
| `id` | `number` | let/var | `++requestId` | ✗ |
| `data` | `any` | let/var | `event.data` | ✗ |
| `target` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array(data.count * data.size)` | ✗ |
| `target` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array(count * size)` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `decodeWorker` | *none* | new Promise(...) |
| promise-chain | `workerProcess` | *none* | self.ready.then |


---

## Functions

### `unpack(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `data.charCodeAt`
- `result.buffer.slice`

<details><summary>Code</summary>

```typescript
function unpack(data) {
		var result = new Uint8Array(data.length);
		for (var i = 0; i < data.length; ++i) {
			var ch = data.charCodeAt(i);
			result[i] = ch > 96 ? ch - 97 : ch > 64 ? ch - 39 : ch + 4;
		}
		var write = 0;
		for (var i = 0; i < data.length; ++i) {
			result[write++] = result[i] < 60 ? wasmpack[result[i]] : (result[i] - 60) * 64 + result[++i];
		}
		return result.buffer.slice(0, write);
	}
```
</details>

### `decode(instance: any, fun: any, target: any, count: any, size: any, source: any, filter: any): void`

**Parameters:**

- **`instance`** `any`
- **`fun`** `any`
- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`filter`** `any`

**Returns:** `void`

**Calls:**

- `sbrk`
- `heap.set`
- `fun`
- `filter`
- `target.set`
- `heap.subarray`

<details><summary>Code</summary>

```typescript
function decode(instance, fun, target, count, size, source, filter) {
		var sbrk = instance.exports.sbrk;
		var count4 = (count + 3) & ~3;
		var tp = sbrk(count4 * size);
		var sp = sbrk(source.length);
		var heap = new Uint8Array(instance.exports.memory.buffer);
		heap.set(source, sp);
		var res = fun(tp, count, size, sp, source.length);
		if (res == 0 && filter) {
			filter(tp, count4, size);
		}
		target.set(heap.subarray(tp, tp + count * size));
		sbrk(tp - sbrk(0));
		if (res != 0) {
			throw new Error('Malformed buffer data: ' + res);
		}
	}
```
</details>

### `createWorker(url: any): { object: Worker; pending: number; requests: {}; }`

**Parameters:**

- **`url`** `any`

**Returns:** `{ object: Worker; pending: number; requests: {}; }`

**Calls:**

- `complex_call_21609`

<details><summary>Code</summary>

```typescript
function createWorker(url) {
		var worker = {
			object: new Worker(url),
			pending: 0,
			requests: {},
		};

		worker.object.onmessage = function (event) {
			var data = event.data;

			worker.pending -= data.count;
			worker.requests[data.id][data.action](data.value);
			delete worker.requests[data.id];
		};

		return worker;
	}
```
</details>

### `initWorkers(count: any): void`

**Parameters:**

- **`count`** `any`

**Returns:** `void`

**Calls:**

- `decode.toString`
- `workerProcess.toString`
- `URL.createObjectURL`
- `createWorker`
- `workers[i].object.postMessage`
- `URL.revokeObjectURL`

<details><summary>Code</summary>

```typescript
function initWorkers(count) {
		var source =
			'self.ready = WebAssembly.instantiate(new Uint8Array([' +
			new Uint8Array(wasm) +
			']), {})' +
			'.then(function(result) { result.instance.exports.__wasm_call_ctors(); return result.instance; });' +
			'self.onmessage = ' +
			workerProcess.name +
			';' +
			decode.toString() +
			workerProcess.toString();

		var blob = new Blob([source], { type: 'text/javascript' });
		var url = URL.createObjectURL(blob);

		for (var i = workers.length; i < count; ++i) {
			workers[i] = createWorker(url);
		}

		for (var i = count; i < workers.length; ++i) {
			workers[i].object.postMessage({});
		}

		workers.length = count;

		URL.revokeObjectURL(url);
	}
```
</details>

### `decodeWorker(count: any, size: any, source: any, mode: any, filter: any): Promise<any>`

**Parameters:**

- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`mode`** `any`
- **`filter`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `worker.object.postMessage`

<details><summary>Code</summary>

```typescript
function decodeWorker(count, size, source, mode, filter) {
		var worker = workers[0];

		for (var i = 1; i < workers.length; ++i) {
			if (workers[i].pending < worker.pending) {
				worker = workers[i];
			}
		}

		return new Promise(function (resolve, reject) {
			var data = new Uint8Array(source);
			var id = ++requestId;

			worker.pending += count;
			worker.requests[id] = { resolve: resolve, reject: reject };
			worker.object.postMessage({ id: id, count: count, size: size, source: data, mode: mode, filter: filter }, [data.buffer]);
		});
	}
```
</details>

### `workerProcess(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `self.close`
- `self.ready.then`
- `decode`
- `self.postMessage`

<details><summary>Code</summary>

```typescript
function workerProcess(event) {
		var data = event.data;
		if (!data.id) {
			return self.close();
		}
		self.ready.then(function (instance) {
			try {
				var target = new Uint8Array(data.count * data.size);
				decode(instance, instance.exports[data.mode], target, data.count, data.size, data.source, instance.exports[data.filter]);
				self.postMessage({ id: data.id, count: data.count, action: 'resolve', value: target }, [target.buffer]);
			} catch (error) {
				self.postMessage({ id: data.id, count: data.count, action: 'reject', value: error });
			}
		});
	}
```
</details>

### `useWorkers(count: any): void`

**Parameters:**

- **`count`** `any`

**Returns:** `void`

**Calls:**

- `initWorkers`

<details><summary>Code</summary>

```typescript
function (count) {
			initWorkers(count);
		}
```
</details>

### `decodeVertexBuffer(target: any, count: any, size: any, source: any, filter: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`filter`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source, filter) {
			decode(instance, instance.exports.meshopt_decodeVertexBuffer, target, count, size, source, instance.exports[filters[filter]]);
		}
```
</details>

### `decodeIndexBuffer(target: any, count: any, size: any, source: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source) {
			decode(instance, instance.exports.meshopt_decodeIndexBuffer, target, count, size, source);
		}
```
</details>

### `decodeIndexSequence(target: any, count: any, size: any, source: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source) {
			decode(instance, instance.exports.meshopt_decodeIndexSequence, target, count, size, source);
		}
```
</details>

### `decodeGltfBuffer(target: any, count: any, size: any, source: any, mode: any, filter: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`mode`** `any`
- **`filter`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source, mode, filter) {
			decode(instance, instance.exports[decoders[mode]], target, count, size, source, instance.exports[filters[filter]]);
		}
```
</details>

### `decodeGltfBufferAsync(count: any, size: any, source: any, mode: any, filter: any): Promise<any>`

**Parameters:**

- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`mode`** `any`
- **`filter`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `decodeWorker`
- `ready.then`
- `decode`

<details><summary>Code</summary>

```typescript
function (count, size, source, mode, filter) {
			if (workers.length > 0) {
				return decodeWorker(count, size, source, decoders[mode], filters[filter]);
			}

			return ready.then(function () {
				var target = new Uint8Array(count * size);
				decode(instance, instance.exports[decoders[mode]], target, count, size, source, instance.exports[filters[filter]]);
				return target;
			});
		}
```
</details>

### `useWorkers(count: any): void`

**Parameters:**

- **`count`** `any`

**Returns:** `void`

**Calls:**

- `initWorkers`

<details><summary>Code</summary>

```typescript
function (count) {
			initWorkers(count);
		}
```
</details>

### `decodeVertexBuffer(target: any, count: any, size: any, source: any, filter: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`filter`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source, filter) {
			decode(instance, instance.exports.meshopt_decodeVertexBuffer, target, count, size, source, instance.exports[filters[filter]]);
		}
```
</details>

### `decodeIndexBuffer(target: any, count: any, size: any, source: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source) {
			decode(instance, instance.exports.meshopt_decodeIndexBuffer, target, count, size, source);
		}
```
</details>

### `decodeIndexSequence(target: any, count: any, size: any, source: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source) {
			decode(instance, instance.exports.meshopt_decodeIndexSequence, target, count, size, source);
		}
```
</details>

### `decodeGltfBuffer(target: any, count: any, size: any, source: any, mode: any, filter: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`mode`** `any`
- **`filter`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source, mode, filter) {
			decode(instance, instance.exports[decoders[mode]], target, count, size, source, instance.exports[filters[filter]]);
		}
```
</details>

### `decodeGltfBufferAsync(count: any, size: any, source: any, mode: any, filter: any): Promise<any>`

**Parameters:**

- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`mode`** `any`
- **`filter`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `decodeWorker`
- `ready.then`
- `decode`

<details><summary>Code</summary>

```typescript
function (count, size, source, mode, filter) {
			if (workers.length > 0) {
				return decodeWorker(count, size, source, decoders[mode], filters[filter]);
			}

			return ready.then(function () {
				var target = new Uint8Array(count * size);
				decode(instance, instance.exports[decoders[mode]], target, count, size, source, instance.exports[filters[filter]]);
				return target;
			});
		}
```
</details>

### `useWorkers(count: any): void`

**Parameters:**

- **`count`** `any`

**Returns:** `void`

**Calls:**

- `initWorkers`

<details><summary>Code</summary>

```typescript
function (count) {
			initWorkers(count);
		}
```
</details>

### `decodeVertexBuffer(target: any, count: any, size: any, source: any, filter: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`filter`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source, filter) {
			decode(instance, instance.exports.meshopt_decodeVertexBuffer, target, count, size, source, instance.exports[filters[filter]]);
		}
```
</details>

### `decodeIndexBuffer(target: any, count: any, size: any, source: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source) {
			decode(instance, instance.exports.meshopt_decodeIndexBuffer, target, count, size, source);
		}
```
</details>

### `decodeIndexSequence(target: any, count: any, size: any, source: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source) {
			decode(instance, instance.exports.meshopt_decodeIndexSequence, target, count, size, source);
		}
```
</details>

### `decodeGltfBuffer(target: any, count: any, size: any, source: any, mode: any, filter: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`mode`** `any`
- **`filter`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source, mode, filter) {
			decode(instance, instance.exports[decoders[mode]], target, count, size, source, instance.exports[filters[filter]]);
		}
```
</details>

### `decodeGltfBufferAsync(count: any, size: any, source: any, mode: any, filter: any): Promise<any>`

**Parameters:**

- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`mode`** `any`
- **`filter`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `decodeWorker`
- `ready.then`
- `decode`

<details><summary>Code</summary>

```typescript
function (count, size, source, mode, filter) {
			if (workers.length > 0) {
				return decodeWorker(count, size, source, decoders[mode], filters[filter]);
			}

			return ready.then(function () {
				var target = new Uint8Array(count * size);
				decode(instance, instance.exports[decoders[mode]], target, count, size, source, instance.exports[filters[filter]]);
				return target;
			});
		}
```
</details>

### `useWorkers(count: any): void`

**Parameters:**

- **`count`** `any`

**Returns:** `void`

**Calls:**

- `initWorkers`

<details><summary>Code</summary>

```typescript
function (count) {
			initWorkers(count);
		}
```
</details>

### `decodeVertexBuffer(target: any, count: any, size: any, source: any, filter: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`filter`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source, filter) {
			decode(instance, instance.exports.meshopt_decodeVertexBuffer, target, count, size, source, instance.exports[filters[filter]]);
		}
```
</details>

### `decodeIndexBuffer(target: any, count: any, size: any, source: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source) {
			decode(instance, instance.exports.meshopt_decodeIndexBuffer, target, count, size, source);
		}
```
</details>

### `decodeIndexSequence(target: any, count: any, size: any, source: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source) {
			decode(instance, instance.exports.meshopt_decodeIndexSequence, target, count, size, source);
		}
```
</details>

### `decodeGltfBuffer(target: any, count: any, size: any, source: any, mode: any, filter: any): void`

**Parameters:**

- **`target`** `any`
- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`mode`** `any`
- **`filter`** `any`

**Returns:** `void`

**Calls:**

- `decode`

<details><summary>Code</summary>

```typescript
function (target, count, size, source, mode, filter) {
			decode(instance, instance.exports[decoders[mode]], target, count, size, source, instance.exports[filters[filter]]);
		}
```
</details>

### `decodeGltfBufferAsync(count: any, size: any, source: any, mode: any, filter: any): Promise<any>`

**Parameters:**

- **`count`** `any`
- **`size`** `any`
- **`source`** `any`
- **`mode`** `any`
- **`filter`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `decodeWorker`
- `ready.then`
- `decode`

<details><summary>Code</summary>

```typescript
function (count, size, source, mode, filter) {
			if (workers.length > 0) {
				return decodeWorker(count, size, source, decoders[mode], filters[filter]);
			}

			return ready.then(function () {
				var target = new Uint8Array(count * size);
				decode(instance, instance.exports[decoders[mode]], target, count, size, source, instance.exports[filters[filter]]);
				return target;
			});
		}
```
</details>


---