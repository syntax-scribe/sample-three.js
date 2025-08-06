[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `shapefile.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 48 |
| 📊 Variables & Constants | 60 |
| ⚡ Async/Await Patterns | 19 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/tools/geo-picking/shapefile.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `array` | `undefined` | let/var | `this._array` | ✗ |
| `request` | `XMLHttpRequest` | let/var | `new XMLHttpRequest` | ✗ |
| `empty` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array(0)` | ✗ |
| `c` | `Uint8Array<any>` | let/var | `new Uint8Array(a.length + b.length)` | ✗ |
| `that` | `any` | let/var | `this` | ✗ |
| `that` | `any` | let/var | `this` | ✗ |
| `index` | `number` | let/var | `this._array.length - this._index` | ✗ |
| `array` | `Uint8Array<any>` | let/var | `new Uint8Array(length)` | ✗ |
| `types` | `{ B: (value: any) => any; C: (value: ...` | let/var | `{ B: readNumber, C: readString, D: readDate, F: readNumber, L: readBoolean, M...` | ✗ |
| `that` | `any` | let/var | `this` | ✗ |
| `i` | `number` | let/var | `1` | ✗ |
| `prototype` | `any` | let/var | `Dbf.prototype` | ✗ |
| `i` | `number` | let/var | `40` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `coordinates` | `any[]` | let/var | `new Array(n)` | ✗ |
| `i` | `number` | let/var | `44` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `parts` | `any[]` | let/var | `new Array(n)` | ✗ |
| `points` | `any[]` | let/var | `new Array(m)` | ✗ |
| `polygons` | `any[]` | let/var | `[]` | ✗ |
| `holes` | `any[]` | let/var | `[]` | ✗ |
| `n` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `area` | `number` | let/var | `ring[n - 1][1] * ring[0][0] - ring[n - 1][0] * ring[0][1]` | ✗ |
| `i` | `number` | let/var | `-1` | ✗ |
| `n` | `any` | let/var | `hole.length` | ✗ |
| `c` | `any` | let/var | `*not shown*` | ✗ |
| `x` | `any` | let/var | `point[0]` | ✗ |
| `y` | `any` | let/var | `point[1]` | ✗ |
| `contains` | `number` | let/var | `-1` | ✗ |
| `pi` | `any` | let/var | `ring[i]` | ✗ |
| `xi` | `any` | let/var | `pi[0]` | ✗ |
| `yi` | `any` | let/var | `pi[1]` | ✗ |
| `pj` | `any` | let/var | `ring[j]` | ✗ |
| `xj` | `any` | let/var | `pj[0]` | ✗ |
| `yj` | `any` | let/var | `pj[1]` | ✗ |
| `x20` | `number` | let/var | `p2[0] - p0[0]` | ✗ |
| `y20` | `number` | let/var | `p2[1] - p0[1]` | ✗ |
| `x10` | `number` | let/var | `p1[0] - p0[0]` | ✗ |
| `y10` | `number` | let/var | `p1[1] - p0[1]` | ✗ |
| `t` | `number` | let/var | `(x20 * x10 + y20 * y10) / (x10 * x10 + y10 * y10)` | ✗ |
| `i` | `number` | let/var | `44` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `parts` | `any[]` | let/var | `new Array(n)` | ✗ |
| `points` | `any[]` | let/var | `new Array(m)` | ✗ |
| `ab` | `Uint8Array<any>` | let/var | `new Uint8Array(a.length + b.length)` | ✗ |
| `that` | `any` | let/var | `this` | ✗ |
| `length` | `number` | let/var | `header.getInt32(4, false) * 2 - 4` | ✗ |
| `parsers` | `{ 0: () => any; 1: (record: any) => {...` | let/var | `{ 0: parseNull, 1: parsePoint, 3: parsePolyLine, 5: parsePolygon, 8: parseMul...` | ✗ |
| `prototype$2` | `any` | let/var | `Shp.prototype` | ✗ |
| `that` | `any` | let/var | `this` | ✗ |
| `dbf` | `any` | let/var | `results[0]` | ✗ |
| `shp` | `any` | let/var | `results[1]` | ✗ |
| `prototype$1` | `any` | let/var | `Shapefile.prototype` | ✗ |
| `shp$$1` | `any` | let/var | `sources[0]` | ✗ |
| `dbf$$1` | `any` | let/var | `sources[1]` | ✗ |
| `encoding` | `string` | let/var | `"windows-1252"` | ✗ |
| `encoding` | `string` | let/var | `"windows-1252"` | ✗ |
| `features` | `any[]` | let/var | `[]` | ✗ |
| `collection` | `{ type: string; features: any[]; bbox...` | let/var | `{type: "FeatureCollection", features: features, bbox: source.bbox}` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `array_cancel` | *none* | Promise.resolve |
| promise-chain | `array_read` | *none* | Promise.resolve |
| promise-chain | `fetchPath` | *none* | fetch(url).then, response.arrayBuffer().then |
| promise-chain | `requestPath` | *none* | new Promise(...) |
| promise-chain | `slice_read` | *none* | that._source.read().then |
| promise-chain | `slice_slice` | *none* | Promise.resolve, that._source.read().then |
| promise-chain | `dbf_read` | *none* | that._source.slice(that._recordLength).then |
| promise-chain | `dbf` | *none* | source.slice(32).then, source.slice(head.getUint16(8, true) - 32).then |
| promise-chain | `shp_read` | *none* | that._source.slice(12).then, that._source.slice(4).then, that._source.slice(length).then |
| promise-chain | `skip` | *none* | that._source.slice(4).then |
| promise-chain | `read` | *none* | that._source.slice(length).then |
| promise-chain | `shp` | *none* | source.slice(100).then |
| promise-chain | `shapefile_cancel` | *none* | Promise.all([
    this._dbf && this._dbf.cancel(),
    this._shp.cancel()
  ]).then, Promise.all |
| promise-chain | `shapefile_read` | *none* | Promise.all([
    that._dbf ? that._dbf.read() : {value: {}},
    that._shp.read()
  ]).then, Promise.all |
| promise-chain | `shapefile` | *none* | Promise.all([
    shp(shpSource),
    dbfSource && dbf(dbfSource, decoder)
  ]).then, Promise.all |
| promise-chain | `open` | *none* | path(shp$$1.substring(0, shp$$1.length - 4) + ".dbf").catch, Promise.all([shp$$1, dbf$$1]).then, Promise.all |
| promise-chain | `openShp` | *none* | Promise.resolve(source).then, Promise.resolve |
| promise-chain | `openDbf` | *none* | Promise.resolve(source).then, Promise.resolve |
| promise-chain | `read` | *none* | open(shp$$1, dbf$$1, options).then, source.read().then, source.read().then |


---

## Functions

### `array_cancel(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `Promise.resolve`

<details><summary>Code</summary>

```typescript
function() {
  this._array = null;
  return Promise.resolve();
}
```
</details>

### `array_read(): Promise<{ done: boolean; value: any; }>`

**Returns:** `Promise<{ done: boolean; value: any; }>`

**Calls:**

- `Promise.resolve`

<details><summary>Code</summary>

```typescript
function() {
  var array = this._array;
  this._array = null;
  return Promise.resolve(array ? {done: false, value: array} : {done: true, value: undefined});
}
```
</details>

### `array(array: any): ArraySource`

**Parameters:**

- **`array`** `any`

**Returns:** `ArraySource`

<details><summary>Code</summary>

```typescript
function array(array) {
  return new ArraySource(array instanceof Uint8Array ? array : new Uint8Array(array));
}
```
</details>

### `ArraySource(array: any): void`

**Parameters:**

- **`array`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ArraySource(array) {
  this._array = array;
}
```
</details>

### `fetchPath(url: any): Promise<Response>`

**Parameters:**

- **`url`** `any`

**Returns:** `Promise<Response>`

**Calls:**

- `fetch(url).then`
- `response.body.getReader`
- `response.arrayBuffer().then`

<details><summary>Code</summary>

```typescript
function(url) {
  return fetch(url).then(function(response) {
    return response.body && response.body.getReader
        ? response.body.getReader()
        : response.arrayBuffer().then(array);
  });
}
```
</details>

### `requestPath(url: any): Promise<any>`

**Parameters:**

- **`url`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `resolve`
- `array`
- `request.open`
- `request.send`

<details><summary>Code</summary>

```typescript
function(url) {
  return new Promise(function(resolve, reject) {
    var request = new XMLHttpRequest;
    request.responseType = "arraybuffer";
    request.onload = function() { resolve(array(request.response)); };
    request.onerror = reject;
    request.ontimeout = reject;
    request.open("GET", url, true);
    request.send();
  });
}
```
</details>

### `path(path: any): Promise<any>`

**Parameters:**

- **`path`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `complex_call_1494`

<details><summary>Code</summary>

```typescript
function path(path) {
  return (typeof fetch === "function" ? fetchPath : requestPath)(path);
}
```
</details>

### `stream(source: any): any`

**Parameters:**

- **`source`** `any`

**Returns:** `any`

**Calls:**

- `source.getReader`

<details><summary>Code</summary>

```typescript
function stream(source) {
  return typeof source.read === "function" ? source : source.getReader();
}
```
</details>

### `slice_cancel(): any`

**Returns:** `any`

**Calls:**

- `this._source.cancel`

<details><summary>Code</summary>

```typescript
function() {
  return this._source.cancel();
}
```
</details>

### `concat(a: any, b: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `c.set`

<details><summary>Code</summary>

```typescript
function concat(a, b) {
  if (!a.length) return b;
  if (!b.length) return a;
  var c = new Uint8Array(a.length + b.length);
  c.set(a);
  c.set(b, a.length);
  return c;
}
```
</details>

### `slice_read(): any`

**Returns:** `any`

**Calls:**

- `that._array.subarray`
- `that._source.read().then`
- `concat`

<details><summary>Code</summary>

```typescript
function() {
  var that = this, array = that._array.subarray(that._index);
  return that._source.read().then(function(result) {
    that._array = empty;
    that._index = 0;
    return result.done ? (array.length > 0
        ? {done: false, value: array}
        : {done: true, value: undefined})
        : {done: false, value: concat(array, result.value)};
  });
}
```
</details>

### `slice_slice(length: any): any`

**Parameters:**

- **`length`** `any`

**Returns:** `any`

**Calls:**

- `Promise.resolve`
- `this._array.subarray`
- `array.set`
- `complex_call_2868`
- `that._source.read().then`
- `array.subarray`
- `result.value.subarray`
- `read`

**Internal Comments:**
```
// If the request fits within the remaining buffer, resolve it immediately.
// Otherwise, read chunks repeatedly until the request is fulfilled. (x2)
// When done, it’s possible the request wasn’t fully fulfilled!
// If so, the pre-allocated array is too big and needs slicing.
// If this chunk fulfills the request, return the resulting array.
// Otherwise copy this chunk into the array, then read the next chunk. (x4)
```

<details><summary>Code</summary>

```typescript
function(length) {
  if ((length |= 0) < 0) throw new Error("invalid length");
  var that = this, index = this._array.length - this._index;

  // If the request fits within the remaining buffer, resolve it immediately.
  if (this._index + length <= this._array.length) {
    return Promise.resolve(this._array.subarray(this._index, this._index += length));
  }

  // Otherwise, read chunks repeatedly until the request is fulfilled.
  var array = new Uint8Array(length);
  array.set(this._array.subarray(this._index));
  return (function read() {
    return that._source.read().then(function(result) {

      // When done, it’s possible the request wasn’t fully fulfilled!
      // If so, the pre-allocated array is too big and needs slicing.
      if (result.done) {
        that._array = empty;
        that._index = 0;
        return index > 0 ? array.subarray(0, index) : null;
      }

      // If this chunk fulfills the request, return the resulting array.
      if (index + result.value.length >= length) {
        that._array = result.value;
        that._index = length - index;
        array.set(result.value.subarray(0, length - index), index);
        return array;
      }

      // Otherwise copy this chunk into the array, then read the next chunk.
      array.set(result.value, index);
      index += result.value.length;
      return read();
    });
  })();
}
```
</details>

### `slice(source: any): any`

**Parameters:**

- **`source`** `any`

**Returns:** `any`

**Calls:**

- `source.getReader`

<details><summary>Code</summary>

```typescript
function slice(source) {
  return typeof source.slice === "function" ? source :
      new SliceSource(typeof source.read === "function" ? source
          : source.getReader());
}
```
</details>

### `SliceSource(source: any): void`

**Parameters:**

- **`source`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function SliceSource(source) {
  this._source = source;
  this._array = empty;
  this._index = 0;
}
```
</details>

### `dbf_cancel(): any`

**Returns:** `any`

**Calls:**

- `this._source.cancel`

<details><summary>Code</summary>

```typescript
function() {
  return this._source.cancel();
}
```
</details>

### `readBoolean(value: any): boolean`

**Parameters:**

- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `/^[nf]$/i.test`
- `/^[yt]$/i.test`

<details><summary>Code</summary>

```typescript
function(value) {
  return /^[nf]$/i.test(value) ? false
      : /^[yt]$/i.test(value) ? true
      : null;
}
```
</details>

### `readDate(value: any): Date`

**Parameters:**

- **`value`** `any`

**Returns:** `Date`

**Calls:**

- `value.substring`

<details><summary>Code</summary>

```typescript
function(value) {
  return new Date(+value.substring(0, 4), value.substring(4, 6) - 1, +value.substring(6, 8));
}
```
</details>

### `readNumber(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `value.trim`
- `isNaN`

<details><summary>Code</summary>

```typescript
function(value) {
  return !(value = value.trim()) || isNaN(value = +value) ? null : value;
}
```
</details>

### `readString(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `value.trim`

<details><summary>Code</summary>

```typescript
function(value) {
  return value.trim() || null;
}
```
</details>

### `dbf_read(): any`

**Returns:** `any`

**Calls:**

- `that._source.slice(that._recordLength).then`
- `that._fields.reduce`
- `complex_call_5020`
- `that._decode`
- `value.subarray`

<details><summary>Code</summary>

```typescript
function() {
  var that = this, i = 1;
  return that._source.slice(that._recordLength).then(function(value) {
    return value && (value[0] !== 0x1a) ? {done: false, value: that._fields.reduce(function(p, f) {
      p[f.name] = types[f.type](that._decode(value.subarray(i, i += f.length)));
      return p;
    }, {})} : {done: true, value: undefined};
  });
}
```
</details>

### `view(array: any): DataView<any>`

**Parameters:**

- **`array`** `any`

**Returns:** `DataView<any>`

<details><summary>Code</summary>

```typescript
function(array) {
  return new DataView(array.buffer, array.byteOffset, array.byteLength);
}
```
</details>

### `dbf(source: any, decoder: any): any`

**Parameters:**

- **`source`** `any`
- **`decoder`** `any`

**Returns:** `any`

**Calls:**

- `slice`
- `source.slice(32).then`
- `view`
- `source.slice(head.getUint16(8, true) - 32).then`

<details><summary>Code</summary>

```typescript
function(source, decoder) {
  source = slice(source);
  return source.slice(32).then(function(array) {
    var head = view(array);
    return source.slice(head.getUint16(8, true) - 32).then(function(array) {
      return new Dbf(source, decoder, head, view(array));
    });
  });
}
```
</details>

### `Dbf(source: any, decoder: any, head: any, body: any): void`

**Parameters:**

- **`source`** `any`
- **`decoder`** `any`
- **`head`** `any`
- **`body`** `any`

**Returns:** `void`

**Calls:**

- `decoder.decode.bind`
- `head.getUint16`
- `body.getUint8`
- `this._fields.push`
- `this._decode`
- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
function Dbf(source, decoder, head, body) {
  this._source = source;
  this._decode = decoder.decode.bind(decoder);
  this._recordLength = head.getUint16(10, true);
  this._fields = [];
  for (var n = 0; body.getUint8(n) !== 0x0d; n += 32) {
    for (var j = 0; j < 11; ++j) if (body.getUint8(n + j) === 0) break;
    this._fields.push({
      name: this._decode(new Uint8Array(body.buffer, body.byteOffset + n, j)),
      type: String.fromCharCode(body.getUint8(n + 11)),
      length: body.getUint8(n + 16)
    });
  }
}
```
</details>

### `cancel(): any`

**Returns:** `any`

**Calls:**

- `this._source.cancel`

<details><summary>Code</summary>

```typescript
function cancel() {
  return this._source.cancel();
}
```
</details>

### `parseMultiPoint(record: any): { type: string; coordinates: any[]; }`

**Parameters:**

- **`record`** `any`

**Returns:** `{ type: string; coordinates: any[]; }`

**Calls:**

- `record.getInt32`
- `record.getFloat64`

<details><summary>Code</summary>

```typescript
function(record) {
  var i = 40, j, n = record.getInt32(36, true), coordinates = new Array(n);
  for (j = 0; j < n; ++j, i += 16) coordinates[j] = [record.getFloat64(i, true), record.getFloat64(i + 8, true)];
  return {type: "MultiPoint", coordinates: coordinates};
}
```
</details>

### `parseNull(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
  return null;
}
```
</details>

### `parsePoint(record: any): { type: string; coordinates: any[]; }`

**Parameters:**

- **`record`** `any`

**Returns:** `{ type: string; coordinates: any[]; }`

**Calls:**

- `record.getFloat64`

<details><summary>Code</summary>

```typescript
function(record) {
  return {type: "Point", coordinates: [record.getFloat64(4, true), record.getFloat64(12, true)]};
}
```
</details>

### `parsePolygon(record: any): { type: string; coordinates: any; }`

**Parameters:**

- **`record`** `any`

**Returns:** `{ type: string; coordinates: any; }`

**Calls:**

- `record.getInt32`
- `record.getFloat64`
- `parts.forEach`
- `points.slice`
- `ringClockwise`
- `polygons.push`
- `holes.push`
- `holes.forEach`
- `polygons.some`
- `ringContainsSome`
- `polygon.push`

<details><summary>Code</summary>

```typescript
function(record) {
  var i = 44, j, n = record.getInt32(36, true), m = record.getInt32(40, true), parts = new Array(n), points = new Array(m), polygons = [], holes = [];
  for (j = 0; j < n; ++j, i += 4) parts[j] = record.getInt32(i, true);
  for (j = 0; j < m; ++j, i += 16) points[j] = [record.getFloat64(i, true), record.getFloat64(i + 8, true)];

  parts.forEach(function(i, j) {
    var ring = points.slice(i, parts[j + 1]);
    if (ringClockwise(ring)) polygons.push([ring]);
    else holes.push(ring);
  });

  holes.forEach(function(hole) {
    polygons.some(function(polygon) {
      if (ringContainsSome(polygon[0], hole)) {
        polygon.push(hole);
        return true;
      }
    }) || polygons.push([hole]);
  });

  return polygons.length === 1
      ? {type: "Polygon", coordinates: polygons[0]}
      : {type: "MultiPolygon", coordinates: polygons};
}
```
</details>

### `ringClockwise(ring: any): boolean`

**Parameters:**

- **`ring`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function ringClockwise(ring) {
  var n;
  if ((n = ring.length) < 4) return false;
  var i = 0, area = ring[n - 1][1] * ring[0][0] - ring[n - 1][0] * ring[0][1];
  while (++i < n) area += ring[i - 1][1] * ring[i][0] - ring[i - 1][0] * ring[i][1];
  return area >= 0;
}
```
</details>

### `ringContainsSome(ring: any, hole: any): boolean`

**Parameters:**

- **`ring`** `any`
- **`hole`** `any`

**Returns:** `boolean`

**Calls:**

- `ringContains`

<details><summary>Code</summary>

```typescript
function ringContainsSome(ring, hole) {
  var i = -1, n = hole.length, c;
  while (++i < n) {
    if (c = ringContains(ring, hole[i])) {
      return c > 0;
    }
  }
  return false;
}
```
</details>

### `ringContains(ring: any, point: any): number`

**Parameters:**

- **`ring`** `any`
- **`point`** `any`

**Returns:** `number`

**Calls:**

- `segmentContains`

<details><summary>Code</summary>

```typescript
function ringContains(ring, point) {
  var x = point[0], y = point[1], contains = -1;
  for (var i = 0, n = ring.length, j = n - 1; i < n; j = i++) {
    var pi = ring[i], xi = pi[0], yi = pi[1],
        pj = ring[j], xj = pj[0], yj = pj[1];
    if (segmentContains(pi, pj, point)) {
      return 0;
    }
    if (((yi > y) !== (yj > y)) && (x < (xj - xi) * (y - yi) / (yj - yi) + xi)) {
      contains = -contains;
    }
  }
  return contains;
}
```
</details>

### `segmentContains(p0: any, p1: any, p2: any): boolean`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function segmentContains(p0, p1, p2) {
  var x20 = p2[0] - p0[0], y20 = p2[1] - p0[1];
  if (x20 === 0 && y20 === 0) return true;
  var x10 = p1[0] - p0[0], y10 = p1[1] - p0[1];
  if (x10 === 0 && y10 === 0) return false;
  var t = (x20 * x10 + y20 * y10) / (x10 * x10 + y10 * y10);
  return t < 0 || t > 1 ? false : t === 0 || t === 1 ? true : t * x10 === x20 && t * y10 === y20;
}
```
</details>

### `parsePolyLine(record: any): { type: string; coordinates: any[]; }`

**Parameters:**

- **`record`** `any`

**Returns:** `{ type: string; coordinates: any[]; }`

**Calls:**

- `record.getInt32`
- `record.getFloat64`
- `parts.map`
- `points.slice`

<details><summary>Code</summary>

```typescript
function(record) {
  var i = 44, j, n = record.getInt32(36, true), m = record.getInt32(40, true), parts = new Array(n), points = new Array(m);
  for (j = 0; j < n; ++j, i += 4) parts[j] = record.getInt32(i, true);
  for (j = 0; j < m; ++j, i += 16) points[j] = [record.getFloat64(i, true), record.getFloat64(i + 8, true)];
  return n === 1
      ? {type: "LineString", coordinates: points}
      : {type: "MultiLineString", coordinates: parts.map(function(i, j) { return points.slice(i, parts[j + 1]); })};
}
```
</details>

### `concat$1(a: any, b: any): Uint8Array<any>`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `ab.set`

<details><summary>Code</summary>

```typescript
function(a, b) {
  var ab = new Uint8Array(a.length + b.length);
  ab.set(a, 0);
  ab.set(b, a.length);
  return ab;
}
```
</details>

### `shp_read(): any`

**Returns:** `any`

**Calls:**

- `that._source.slice(12).then`
- `view`
- `that._source.slice(4).then`
- `concat$1`
- `array.slice`
- `header.getInt32`
- `skip`
- `read`
- `that._source.slice(length).then`
- `that._parse`

**Internal Comments:**
```
// If the record starts with an invalid shape type (see #36), scan ahead in
// four-byte increments to find the next valid record, identified by the
// expected index, a non-empty content length and a valid shape type.
// All records should have at least four bytes (for the record shape type),
// so an invalid content length indicates corruption.
```

<details><summary>Code</summary>

```typescript
function() {
  var that = this;
  ++that._index;
  return that._source.slice(12).then(function(array) {
    if (array == null) return {done: true, value: undefined};
    var header = view(array);

    // If the record starts with an invalid shape type (see #36), scan ahead in
    // four-byte increments to find the next valid record, identified by the
    // expected index, a non-empty content length and a valid shape type.
    function skip() {
      return that._source.slice(4).then(function(chunk) {
        if (chunk == null) return {done: true, value: undefined};
        header = view(array = concat$1(array.slice(4), chunk));
        return header.getInt32(0, false) !== that._index ? skip() : read();
      });
    }

    // All records should have at least four bytes (for the record shape type),
    // so an invalid content length indicates corruption.
    function read() {
      var length = header.getInt32(4, false) * 2 - 4, type = header.getInt32(8, true);
      return length < 0 || (type && type !== that._type) ? skip() : that._source.slice(length).then(function(chunk) {
        return {done: false, value: type ? that._parse(view(concat$1(array.slice(8), chunk))) : null};
      });
    }

    return read();
  });
}
```
</details>

### `skip(): any`

**Returns:** `any`

**Calls:**

- `that._source.slice(4).then`
- `view`
- `concat$1`
- `array.slice`
- `header.getInt32`
- `skip`
- `read`

<details><summary>Code</summary>

```typescript
function skip() {
      return that._source.slice(4).then(function(chunk) {
        if (chunk == null) return {done: true, value: undefined};
        header = view(array = concat$1(array.slice(4), chunk));
        return header.getInt32(0, false) !== that._index ? skip() : read();
      });
    }
```
</details>

### `read(): any`

**Returns:** `any`

**Calls:**

- `header.getInt32`
- `skip`
- `that._source.slice(length).then`
- `that._parse`
- `view`
- `concat$1`
- `array.slice`

<details><summary>Code</summary>

```typescript
function read() {
      var length = header.getInt32(4, false) * 2 - 4, type = header.getInt32(8, true);
      return length < 0 || (type && type !== that._type) ? skip() : that._source.slice(length).then(function(chunk) {
        return {done: false, value: type ? that._parse(view(concat$1(array.slice(8), chunk))) : null};
      });
    }
```
</details>

### `shp(source: any): any`

**Parameters:**

- **`source`** `any`

**Returns:** `any`

**Calls:**

- `slice`
- `source.slice(100).then`
- `view`

<details><summary>Code</summary>

```typescript
function(source) {
  source = slice(source);
  return source.slice(100).then(function(array) {
    return new Shp(source, view(array));
  });
}
```
</details>

### `Shp(source: any, header: any): void`

**Parameters:**

- **`source`** `any`
- **`header`** `any`

**Returns:** `void`

**Calls:**

- `header.getInt32`
- `header.getFloat64`

<details><summary>Code</summary>

```typescript
function Shp(source, header) {
  var type = header.getInt32(32, true);
  if (!(type in parsers)) throw new Error("unsupported shape type: " + type);
  this._source = source;
  this._type = type;
  this._index = 0;
  this._parse = parsers[type];
  this.bbox = [header.getFloat64(36, true), header.getFloat64(44, true), header.getFloat64(52, true), header.getFloat64(60, true)];
}
```
</details>

### `noop(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function noop() {}
```
</details>

### `shapefile_cancel(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `Promise.all([
    this._dbf && this._dbf.cancel(),
    this._shp.cancel()
  ]).then`

<details><summary>Code</summary>

```typescript
function() {
  return Promise.all([
    this._dbf && this._dbf.cancel(),
    this._shp.cancel()
  ]).then(noop);
}
```
</details>

### `shapefile_read(): Promise<any>`

**Returns:** `Promise<any>`

**Calls:**

- `Promise.all([
    that._dbf ? that._dbf.read() : {value: {}},
    that._shp.read()
  ]).then`

<details><summary>Code</summary>

```typescript
function() {
  var that = this;
  return Promise.all([
    that._dbf ? that._dbf.read() : {value: {}},
    that._shp.read()
  ]).then(function(results) {
    var dbf = results[0], shp = results[1];
    return shp.done ? shp : {
      done: false,
      value: {
        type: "Feature",
        properties: dbf.value,
        geometry: shp.value
      }
    };
  });
}
```
</details>

### `shapefile(shpSource: any, dbfSource: any, decoder: any): Promise<Shapefile>`

**Parameters:**

- **`shpSource`** `any`
- **`dbfSource`** `any`
- **`decoder`** `any`

**Returns:** `Promise<Shapefile>`

**Calls:**

- `Promise.all([
    shp(shpSource),
    dbfSource && dbf(dbfSource, decoder)
  ]).then`

<details><summary>Code</summary>

```typescript
function(shpSource, dbfSource, decoder) {
  return Promise.all([
    shp(shpSource),
    dbfSource && dbf(dbfSource, decoder)
  ]).then(function(sources) {
    return new Shapefile(sources[0], sources[1]);
  });
}
```
</details>

### `Shapefile(shp$$1: any, dbf$$1: any): void`

**Parameters:**

- **`shp$$1`** `any`
- **`dbf$$1`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Shapefile(shp$$1, dbf$$1) {
  this._shp = shp$$1;
  this._dbf = dbf$$1;
  this.bbox = shp$$1.bbox;
}
```
</details>

### `open(shp$$1: any, dbf$$1: any, options: any): Promise<Shapefile>`

**Parameters:**

- **`shp$$1`** `any`
- **`dbf$$1`** `any`
- **`options`** `any`

**Returns:** `Promise<Shapefile>`

**Calls:**

- `/\.dbf$/.test`
- `path`
- `array`
- `stream`
- `/\.shp$/.test`
- `path(shp$$1.substring(0, shp$$1.length - 4) + ".dbf").catch`
- `Promise.all([shp$$1, dbf$$1]).then`
- `shapefile`

<details><summary>Code</summary>

```typescript
function open(shp$$1, dbf$$1, options) {
  if (typeof dbf$$1 === "string") {
    if (!/\.dbf$/.test(dbf$$1)) dbf$$1 += ".dbf";
    dbf$$1 = path(dbf$$1);
  } else if (dbf$$1 instanceof ArrayBuffer || dbf$$1 instanceof Uint8Array) {
    dbf$$1 = array(dbf$$1);
  } else if (dbf$$1 != null) {
    dbf$$1 = stream(dbf$$1);
  }
  if (typeof shp$$1 === "string") {
    if (!/\.shp$/.test(shp$$1)) shp$$1 += ".shp";
    if (dbf$$1 === undefined) dbf$$1 = path(shp$$1.substring(0, shp$$1.length - 4) + ".dbf").catch(function() {});
    shp$$1 = path(shp$$1);
  } else if (shp$$1 instanceof ArrayBuffer || shp$$1 instanceof Uint8Array) {
    shp$$1 = array(shp$$1);
  } else {
    shp$$1 = stream(shp$$1);
  }
  return Promise.all([shp$$1, dbf$$1]).then(function(sources) {
    var shp$$1 = sources[0], dbf$$1 = sources[1], encoding = "windows-1252";
    if (options && options.encoding != null) encoding = options.encoding;
    return shapefile(shp$$1, dbf$$1, dbf$$1 && new TextDecoder(encoding));
  });
}
```
</details>

### `openShp(source: any): Promise<any>`

**Parameters:**

- **`source`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `/\.shp$/.test`
- `path`
- `array`
- `stream`
- `Promise.resolve(source).then`

<details><summary>Code</summary>

```typescript
function openShp(source) {
  if (typeof source === "string") {
    if (!/\.shp$/.test(source)) source += ".shp";
    source = path(source);
  } else if (source instanceof ArrayBuffer || source instanceof Uint8Array) {
    source = array(source);
  } else {
    source = stream(source);
  }
  return Promise.resolve(source).then(shp);
}
```
</details>

### `openDbf(source: any, options: any): Promise<any>`

**Parameters:**

- **`source`** `any`
- **`options`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `/\.dbf$/.test`
- `path`
- `array`
- `stream`
- `Promise.resolve(source).then`
- `dbf`

<details><summary>Code</summary>

```typescript
function openDbf(source, options) {
  var encoding = "windows-1252";
  if (options && options.encoding != null) encoding = options.encoding;
  encoding = new TextDecoder(encoding);
  if (typeof source === "string") {
    if (!/\.dbf$/.test(source)) source += ".dbf";
    source = path(source);
  } else if (source instanceof ArrayBuffer || source instanceof Uint8Array) {
    source = array(source);
  } else {
    source = stream(source);
  }
  return Promise.resolve(source).then(function(source) {
    return dbf(source, encoding);
  });
}
```
</details>

### `read(shp$$1: any, dbf$$1: any, options: any): Promise<any>`

**Parameters:**

- **`shp$$1`** `any`
- **`dbf$$1`** `any`
- **`options`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `open(shp$$1, dbf$$1, options).then`
- `source.read().then`
- `features.push`

<details><summary>Code</summary>

```typescript
function read(shp$$1, dbf$$1, options) {
  return open(shp$$1, dbf$$1, options).then(function(source) {
    var features = [], collection = {type: "FeatureCollection", features: features, bbox: source.bbox};
    return source.read().then(function read(result) {
      if (result.done) return collection;
      features.push(result.value);
      return source.read().then(read);
    });
  });
}
```
</details>


---