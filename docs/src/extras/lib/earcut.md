[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `earcut.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 35 |
| 📊 Variables & Constants | 91 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/extras/lib/earcut.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `hasHoles` | `any` | let/var | `holeIndices && holeIndices.length` | ✗ |
| `outerLen` | `any` | let/var | `hasHoles ? holeIndices[0] * dim : data.length` | ✗ |
| `triangles` | `any[]` | let/var | `[]` | ✗ |
| `minX` | `any` | let/var | `*not shown*` | ✗ |
| `minY` | `any` | let/var | `*not shown*` | ✗ |
| `invSize` | `any` | let/var | `*not shown*` | ✗ |
| `maxX` | `number` | let/var | `-Infinity` | ✗ |
| `maxY` | `number` | let/var | `-Infinity` | ✗ |
| `x` | `any` | let/var | `data[i]` | ✗ |
| `y` | `any` | let/var | `data[i + 1]` | ✗ |
| `last` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `any` | let/var | `start` | ✗ |
| `again` | `any` | let/var | `*not shown*` | ✗ |
| `stop` | `any` | let/var | `ear` | ✗ |
| `prev` | `any` | let/var | `ear.prev` | ✗ |
| `next` | `any` | let/var | `ear.next` | ✗ |
| `a` | `any` | let/var | `ear.prev` | ✗ |
| `b` | `any` | let/var | `ear` | ✗ |
| `c` | `any` | let/var | `ear.next` | ✗ |
| `ax` | `any` | let/var | `a.x` | ✗ |
| `bx` | `any` | let/var | `b.x` | ✗ |
| `cx` | `any` | let/var | `c.x` | ✗ |
| `ay` | `any` | let/var | `a.y` | ✗ |
| `by` | `any` | let/var | `b.y` | ✗ |
| `cy` | `any` | let/var | `c.y` | ✗ |
| `p` | `any` | let/var | `c.next` | ✗ |
| `a` | `any` | let/var | `ear.prev` | ✗ |
| `b` | `any` | let/var | `ear` | ✗ |
| `c` | `any` | let/var | `ear.next` | ✗ |
| `ax` | `any` | let/var | `a.x` | ✗ |
| `bx` | `any` | let/var | `b.x` | ✗ |
| `cx` | `any` | let/var | `c.x` | ✗ |
| `ay` | `any` | let/var | `a.y` | ✗ |
| `by` | `any` | let/var | `b.y` | ✗ |
| `cy` | `any` | let/var | `c.y` | ✗ |
| `p` | `any` | let/var | `ear.prevZ` | ✗ |
| `n` | `any` | let/var | `ear.nextZ` | ✗ |
| `p` | `any` | let/var | `start` | ✗ |
| `a` | `any` | let/var | `p.prev` | ✗ |
| `b` | `any` | let/var | `p.next.next` | ✗ |
| `a` | `any` | let/var | `start` | ✗ |
| `b` | `any` | let/var | `a.next.next` | ✗ |
| `queue` | `any[]` | let/var | `[]` | ✗ |
| `start` | `number` | let/var | `holeIndices[i] * dim` | ✗ |
| `end` | `any` | let/var | `i < len - 1 ? holeIndices[i + 1] * dim : data.length` | ✗ |
| `result` | `number` | let/var | `a.x - b.x` | ✗ |
| `aSlope` | `number` | let/var | `(a.next.y - a.y) / (a.next.x - a.x)` | ✗ |
| `bSlope` | `number` | let/var | `(b.next.y - b.y) / (b.next.x - b.x)` | ✗ |
| `p` | `any` | let/var | `outerNode` | ✗ |
| `hx` | `any` | let/var | `hole.x` | ✗ |
| `hy` | `any` | let/var | `hole.y` | ✗ |
| `qx` | `number` | let/var | `-Infinity` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `x` | `any` | let/var | `p.x + (hy - p.y) * (p.next.x - p.x) / (p.next.y - p.y)` | ✗ |
| `stop` | `any` | let/var | `m` | ✗ |
| `mx` | `any` | let/var | `m.x` | ✗ |
| `my` | `any` | let/var | `m.y` | ✗ |
| `tanMin` | `number` | let/var | `Infinity` | ✗ |
| `tan` | `number` | let/var | `Math.abs(hy - p.y) / (hx - p.x)` | ✗ |
| `p` | `any` | let/var | `start` | ✗ |
| `numMerges` | `any` | let/var | `*not shown*` | ✗ |
| `inSize` | `number` | let/var | `1` | ✗ |
| `p` | `any` | let/var | `list` | ✗ |
| `e` | `any` | let/var | `*not shown*` | ✗ |
| `tail` | `any` | let/var | `null` | ✗ |
| `q` | `any` | let/var | `p` | ✗ |
| `pSize` | `number` | let/var | `0` | ✗ |
| `qSize` | `number` | let/var | `inSize` | ✗ |
| `p` | `any` | let/var | `start` | ✗ |
| `leftmost` | `any` | let/var | `start` | ✗ |
| `p` | `any` | let/var | `a` | ✗ |
| `p` | `any` | let/var | `a` | ✗ |
| `inside` | `boolean` | let/var | `false` | ✗ |
| `px` | `number` | let/var | `(a.x + b.x) / 2` | ✗ |
| `py` | `number` | let/var | `(a.y + b.y) / 2` | ✗ |
| `an` | `any` | let/var | `a.next` | ✗ |
| `bp` | `any` | let/var | `b.prev` | ✗ |
| `hasHoles` | `any` | let/var | `holeIndices && holeIndices.length` | ✗ |
| `outerLen` | `any` | let/var | `hasHoles ? holeIndices[0] * dim : data.length` | ✗ |
| `start` | `number` | let/var | `holeIndices[i] * dim` | ✗ |
| `end` | `any` | let/var | `i < len - 1 ? holeIndices[i + 1] * dim : data.length` | ✗ |
| `trianglesArea` | `number` | let/var | `0` | ✗ |
| `a` | `number` | let/var | `triangles[i] * dim` | ✗ |
| `b` | `number` | let/var | `triangles[i + 1] * dim` | ✗ |
| `c` | `number` | let/var | `triangles[i + 2] * dim` | ✗ |
| `sum` | `number` | let/var | `0` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `holes` | `any[]` | let/var | `[]` | ✗ |
| `dimensions` | `any` | let/var | `data[0][0].length` | ✗ |
| `holeIndex` | `number` | let/var | `0` | ✗ |
| `prevLen` | `number` | let/var | `0` | ✗ |


---

## Functions

### `earcut(data: any, holeIndices: any, dim: number): any[]`

**Parameters:**

- **`data`** `any`
- **`holeIndices`** `any`
- **`dim`** `number`

**Returns:** `any[]`

**Calls:**

- `linkedList`
- `eliminateHoles`
- `Math.max`
- `earcutLinked`

**Internal Comments:**
```
// if the shape is not too simple, we'll use z-order curve hash later; calculate polygon bbox
// minX, minY and invSize are later used to transform coords into integers for z-order calculation (x3)
```

<details><summary>Code</summary>

```typescript
export default function earcut(data, holeIndices, dim = 2) {

    const hasHoles = holeIndices && holeIndices.length;
    const outerLen = hasHoles ? holeIndices[0] * dim : data.length;
    let outerNode = linkedList(data, 0, outerLen, dim, true);
    const triangles = [];

    if (!outerNode || outerNode.next === outerNode.prev) return triangles;

    let minX, minY, invSize;

    if (hasHoles) outerNode = eliminateHoles(data, holeIndices, outerNode, dim);

    // if the shape is not too simple, we'll use z-order curve hash later; calculate polygon bbox
    if (data.length > 80 * dim) {
        minX = Infinity;
        minY = Infinity;
        let maxX = -Infinity;
        let maxY = -Infinity;

        for (let i = dim; i < outerLen; i += dim) {
            const x = data[i];
            const y = data[i + 1];
            if (x < minX) minX = x;
            if (y < minY) minY = y;
            if (x > maxX) maxX = x;
            if (y > maxY) maxY = y;
        }

        // minX, minY and invSize are later used to transform coords into integers for z-order calculation
        invSize = Math.max(maxX - minX, maxY - minY);
        invSize = invSize !== 0 ? 32767 / invSize : 0;
    }

    earcutLinked(outerNode, triangles, dim, minX, minY, invSize, 0);

    return triangles;
}
```
</details>

### `linkedList(data: any, start: any, end: any, dim: any, clockwise: any): any`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`end`** `any`
- **`dim`** `any`
- **`clockwise`** `any`

**Returns:** `any`

**Calls:**

- `signedArea`
- `insertNode`
- `equals`
- `removeNode`

<details><summary>Code</summary>

```typescript
function linkedList(data, start, end, dim, clockwise) {
    let last;

    if (clockwise === (signedArea(data, start, end, dim) > 0)) {
        for (let i = start; i < end; i += dim) last = insertNode(i / dim | 0, data[i], data[i + 1], last);
    } else {
        for (let i = end - dim; i >= start; i -= dim) last = insertNode(i / dim | 0, data[i], data[i + 1], last);
    }

    if (last && equals(last, last.next)) {
        removeNode(last);
        last = last.next;
    }

    return last;
}
```
</details>

### `filterPoints(start: any, end: any): any`

**Parameters:**

- **`start`** `any`
- **`end`** `any`

**Returns:** `any`

**Calls:**

- `equals`
- `area`
- `removeNode`

<details><summary>Code</summary>

```typescript
function filterPoints(start, end) {
    if (!start) return start;
    if (!end) end = start;

    let p = start,
        again;
    do {
        again = false;

        if (!p.steiner && (equals(p, p.next) || area(p.prev, p, p.next) === 0)) {
            removeNode(p);
            p = end = p.prev;
            if (p === p.next) break;
            again = true;

        } else {
            p = p.next;
        }
    } while (again || p !== end);

    return end;
}
```
</details>

### `earcutLinked(ear: any, triangles: any, dim: any, minX: any, minY: any, invSize: any, pass: any): void`

**Parameters:**

- **`ear`** `any`
- **`triangles`** `any`
- **`dim`** `any`
- **`minX`** `any`
- **`minY`** `any`
- **`invSize`** `any`
- **`pass`** `any`

**Returns:** `void`

**Calls:**

- `indexCurve`
- `isEarHashed`
- `isEar`
- `triangles.push`
- `removeNode`
- `earcutLinked`
- `filterPoints`
- `cureLocalIntersections`
- `splitEarcut`

**Internal Comments:**
```
// interlink polygon nodes in z-order
// iterate through ears, slicing them one by one
// skipping the next vertex leads to less sliver triangles (x3)
// if we looped through the whole remaining polygon and can't find any more ears
// try filtering points and slicing again
```

<details><summary>Code</summary>

```typescript
function earcutLinked(ear, triangles, dim, minX, minY, invSize, pass) {
    if (!ear) return;

    // interlink polygon nodes in z-order
    if (!pass && invSize) indexCurve(ear, minX, minY, invSize);

    let stop = ear;

    // iterate through ears, slicing them one by one
    while (ear.prev !== ear.next) {
        const prev = ear.prev;
        const next = ear.next;

        if (invSize ? isEarHashed(ear, minX, minY, invSize) : isEar(ear)) {
            triangles.push(prev.i, ear.i, next.i); // cut off the triangle

            removeNode(ear);

            // skipping the next vertex leads to less sliver triangles
            ear = next.next;
            stop = next.next;

            continue;
        }

        ear = next;

        // if we looped through the whole remaining polygon and can't find any more ears
        if (ear === stop) {
            // try filtering points and slicing again
            if (!pass) {
                earcutLinked(filterPoints(ear), triangles, dim, minX, minY, invSize, 1);

            // if this didn't work, try curing all small self-intersections locally
            } else if (pass === 1) {
                ear = cureLocalIntersections(filterPoints(ear), triangles);
                earcutLinked(ear, triangles, dim, minX, minY, invSize, 2);

            // as a last resort, try splitting the remaining polygon into two
            } else if (pass === 2) {
                splitEarcut(ear, triangles, dim, minX, minY, invSize);
            }

            break;
        }
    }
}
```
</details>

### `isEar(ear: any): boolean`

**Parameters:**

- **`ear`** `any`

**Returns:** `boolean`

**Calls:**

- `area`
- `Math.min`
- `Math.max`
- `pointInTriangleExceptFirst`

**Internal Comments:**
```
// now make sure we don't have other points inside the potential ear (x2)
// triangle bbox (x2)
```

<details><summary>Code</summary>

```typescript
function isEar(ear) {
    const a = ear.prev,
        b = ear,
        c = ear.next;

    if (area(a, b, c) >= 0) return false; // reflex, can't be an ear

    // now make sure we don't have other points inside the potential ear
    const ax = a.x, bx = b.x, cx = c.x, ay = a.y, by = b.y, cy = c.y;

    // triangle bbox
    const x0 = Math.min(ax, bx, cx),
        y0 = Math.min(ay, by, cy),
        x1 = Math.max(ax, bx, cx),
        y1 = Math.max(ay, by, cy);

    let p = c.next;
    while (p !== a) {
        if (p.x >= x0 && p.x <= x1 && p.y >= y0 && p.y <= y1 &&
            pointInTriangleExceptFirst(ax, ay, bx, by, cx, cy, p.x, p.y) &&
            area(p.prev, p, p.next) >= 0) return false;
        p = p.next;
    }

    return true;
}
```
</details>

### `isEarHashed(ear: any, minX: any, minY: any, invSize: any): boolean`

**Parameters:**

- **`ear`** `any`
- **`minX`** `any`
- **`minY`** `any`
- **`invSize`** `any`

**Returns:** `boolean`

**Calls:**

- `area`
- `Math.min`
- `Math.max`
- `zOrder`
- `pointInTriangleExceptFirst`

**Internal Comments:**
```
// triangle bbox (x2)
// z-order range for the current triangle bbox; (x2)
// look for points inside the triangle in both directions
// look for remaining points in decreasing z-order
// look for remaining points in increasing z-order
```

<details><summary>Code</summary>

```typescript
function isEarHashed(ear, minX, minY, invSize) {
    const a = ear.prev,
        b = ear,
        c = ear.next;

    if (area(a, b, c) >= 0) return false; // reflex, can't be an ear

    const ax = a.x, bx = b.x, cx = c.x, ay = a.y, by = b.y, cy = c.y;

    // triangle bbox
    const x0 = Math.min(ax, bx, cx),
        y0 = Math.min(ay, by, cy),
        x1 = Math.max(ax, bx, cx),
        y1 = Math.max(ay, by, cy);

    // z-order range for the current triangle bbox;
    const minZ = zOrder(x0, y0, minX, minY, invSize),
        maxZ = zOrder(x1, y1, minX, minY, invSize);

    let p = ear.prevZ,
        n = ear.nextZ;

    // look for points inside the triangle in both directions
    while (p && p.z >= minZ && n && n.z <= maxZ) {
        if (p.x >= x0 && p.x <= x1 && p.y >= y0 && p.y <= y1 && p !== a && p !== c &&
            pointInTriangleExceptFirst(ax, ay, bx, by, cx, cy, p.x, p.y) && area(p.prev, p, p.next) >= 0) return false;
        p = p.prevZ;

        if (n.x >= x0 && n.x <= x1 && n.y >= y0 && n.y <= y1 && n !== a && n !== c &&
            pointInTriangleExceptFirst(ax, ay, bx, by, cx, cy, n.x, n.y) && area(n.prev, n, n.next) >= 0) return false;
        n = n.nextZ;
    }

    // look for remaining points in decreasing z-order
    while (p && p.z >= minZ) {
        if (p.x >= x0 && p.x <= x1 && p.y >= y0 && p.y <= y1 && p !== a && p !== c &&
            pointInTriangleExceptFirst(ax, ay, bx, by, cx, cy, p.x, p.y) && area(p.prev, p, p.next) >= 0) return false;
        p = p.prevZ;
    }

    // look for remaining points in increasing z-order
    while (n && n.z <= maxZ) {
        if (n.x >= x0 && n.x <= x1 && n.y >= y0 && n.y <= y1 && n !== a && n !== c &&
            pointInTriangleExceptFirst(ax, ay, bx, by, cx, cy, n.x, n.y) && area(n.prev, n, n.next) >= 0) return false;
        n = n.nextZ;
    }

    return true;
}
```
</details>

### `cureLocalIntersections(start: any, triangles: any): any`

**Parameters:**

- **`start`** `any`
- **`triangles`** `any`

**Returns:** `any`

**Calls:**

- `equals`
- `intersects`
- `locallyInside`
- `triangles.push`
- `removeNode`
- `filterPoints`

**Internal Comments:**
```
// remove two nodes involved (x3)
```

<details><summary>Code</summary>

```typescript
function cureLocalIntersections(start, triangles) {
    let p = start;
    do {
        const a = p.prev,
            b = p.next.next;

        if (!equals(a, b) && intersects(a, p, p.next, b) && locallyInside(a, b) && locallyInside(b, a)) {

            triangles.push(a.i, p.i, b.i);

            // remove two nodes involved
            removeNode(p);
            removeNode(p.next);

            p = start = b;
        }
        p = p.next;
    } while (p !== start);

    return filterPoints(p);
}
```
</details>

### `splitEarcut(start: any, triangles: any, dim: any, minX: any, minY: any, invSize: any): void`

**Parameters:**

- **`start`** `any`
- **`triangles`** `any`
- **`dim`** `any`
- **`minX`** `any`
- **`minY`** `any`
- **`invSize`** `any`

**Returns:** `void`

**Calls:**

- `isValidDiagonal`
- `splitPolygon`
- `filterPoints`
- `earcutLinked`

**Internal Comments:**
```
// look for a valid diagonal that divides the polygon into two (x2)
// split the polygon in two by the diagonal (x2)
// filter colinear points around the cuts (x3)
// run earcut on each half (x3)
```

<details><summary>Code</summary>

```typescript
function splitEarcut(start, triangles, dim, minX, minY, invSize) {
    // look for a valid diagonal that divides the polygon into two
    let a = start;
    do {
        let b = a.next.next;
        while (b !== a.prev) {
            if (a.i !== b.i && isValidDiagonal(a, b)) {
                // split the polygon in two by the diagonal
                let c = splitPolygon(a, b);

                // filter colinear points around the cuts
                a = filterPoints(a, a.next);
                c = filterPoints(c, c.next);

                // run earcut on each half
                earcutLinked(a, triangles, dim, minX, minY, invSize, 0);
                earcutLinked(c, triangles, dim, minX, minY, invSize, 0);
                return;
            }
            b = b.next;
        }
        a = a.next;
    } while (a !== start);
}
```
</details>

### `eliminateHoles(data: any, holeIndices: any, outerNode: any, dim: any): any`

**Parameters:**

- **`data`** `any`
- **`holeIndices`** `any`
- **`outerNode`** `any`
- **`dim`** `any`

**Returns:** `any`

**Calls:**

- `linkedList`
- `queue.push`
- `getLeftmost`
- `queue.sort`
- `eliminateHole`

**Internal Comments:**
```
// process holes from left to right
```

<details><summary>Code</summary>

```typescript
function eliminateHoles(data, holeIndices, outerNode, dim) {
    const queue = [];

    for (let i = 0, len = holeIndices.length; i < len; i++) {
        const start = holeIndices[i] * dim;
        const end = i < len - 1 ? holeIndices[i + 1] * dim : data.length;
        const list = linkedList(data, start, end, dim, false);
        if (list === list.next) list.steiner = true;
        queue.push(getLeftmost(list));
    }

    queue.sort(compareXYSlope);

    // process holes from left to right
    for (let i = 0; i < queue.length; i++) {
        outerNode = eliminateHole(queue[i], outerNode);
    }

    return outerNode;
}
```
</details>

### `compareXYSlope(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

**Internal Comments:**
```
// when the left-most point of 2 holes meet at a vertex, sort the holes counterclockwise so that when we find
// the bridge to the outer shell is always the point that they meet at.
```

<details><summary>Code</summary>

```typescript
function compareXYSlope(a, b) {
    let result = a.x - b.x;
    // when the left-most point of 2 holes meet at a vertex, sort the holes counterclockwise so that when we find
    // the bridge to the outer shell is always the point that they meet at.
    if (result === 0) {
        result = a.y - b.y;
        if (result === 0) {
            const aSlope = (a.next.y - a.y) / (a.next.x - a.x);
            const bSlope = (b.next.y - b.y) / (b.next.x - b.x);
            result = aSlope - bSlope;
        }
    }
    return result;
}
```
</details>

### `eliminateHole(hole: any, outerNode: any): any`

**Parameters:**

- **`hole`** `any`
- **`outerNode`** `any`

**Returns:** `any`

**Calls:**

- `findHoleBridge`
- `splitPolygon`
- `filterPoints`

**Internal Comments:**
```
// filter collinear points around the cuts (x3)
```

<details><summary>Code</summary>

```typescript
function eliminateHole(hole, outerNode) {
    const bridge = findHoleBridge(hole, outerNode);
    if (!bridge) {
        return outerNode;
    }

    const bridgeReverse = splitPolygon(bridge, hole);

    // filter collinear points around the cuts
    filterPoints(bridgeReverse, bridgeReverse.next);
    return filterPoints(bridge, bridge.next);
}
```
</details>

### `findHoleBridge(hole: any, outerNode: any): any`

**Parameters:**

- **`hole`** `any`
- **`outerNode`** `any`

**Returns:** `any`

**Calls:**

- `equals`
- `pointInTriangle`
- `Math.abs`
- `locallyInside`
- `sectorContainsSector`

**Internal Comments:**
```
// find a segment intersected by a ray from the hole's leftmost point to the left;
// segment's endpoint with lesser x will be potential connection point
// unless they intersect at a vertex, then choose the vertex
// look for points inside the triangle of hole point, segment intersection and endpoint; (x2)
// if there are no points found, we have a valid connection; (x2)
// otherwise choose the point of the minimum angle with the ray as connection point (x2)
```

<details><summary>Code</summary>

```typescript
function findHoleBridge(hole, outerNode) {
    let p = outerNode;
    const hx = hole.x;
    const hy = hole.y;
    let qx = -Infinity;
    let m;

    // find a segment intersected by a ray from the hole's leftmost point to the left;
    // segment's endpoint with lesser x will be potential connection point
    // unless they intersect at a vertex, then choose the vertex
    if (equals(hole, p)) return p;
    do {
        if (equals(hole, p.next)) return p.next;
        else if (hy <= p.y && hy >= p.next.y && p.next.y !== p.y) {
            const x = p.x + (hy - p.y) * (p.next.x - p.x) / (p.next.y - p.y);
            if (x <= hx && x > qx) {
                qx = x;
                m = p.x < p.next.x ? p : p.next;
                if (x === hx) return m; // hole touches outer segment; pick leftmost endpoint
            }
        }
        p = p.next;
    } while (p !== outerNode);

    if (!m) return null;

    // look for points inside the triangle of hole point, segment intersection and endpoint;
    // if there are no points found, we have a valid connection;
    // otherwise choose the point of the minimum angle with the ray as connection point

    const stop = m;
    const mx = m.x;
    const my = m.y;
    let tanMin = Infinity;

    p = m;

    do {
        if (hx >= p.x && p.x >= mx && hx !== p.x &&
                pointInTriangle(hy < my ? hx : qx, hy, mx, my, hy < my ? qx : hx, hy, p.x, p.y)) {

            const tan = Math.abs(hy - p.y) / (hx - p.x); // tangential

            if (locallyInside(p, hole) &&
                (tan < tanMin || (tan === tanMin && (p.x > m.x || (p.x === m.x && sectorContainsSector(m, p)))))) {
                m = p;
                tanMin = tan;
            }
        }

        p = p.next;
    } while (p !== stop);

    return m;
}
```
</details>

### `sectorContainsSector(m: any, p: any): boolean`

**Parameters:**

- **`m`** `any`
- **`p`** `any`

**Returns:** `boolean`

**Calls:**

- `area`

<details><summary>Code</summary>

```typescript
function sectorContainsSector(m, p) {
    return area(m.prev, m, p.prev) < 0 && area(p.next, m, m.next) < 0;
}
```
</details>

### `indexCurve(start: any, minX: any, minY: any, invSize: any): void`

**Parameters:**

- **`start`** `any`
- **`minX`** `any`
- **`minY`** `any`
- **`invSize`** `any`

**Returns:** `void`

**Calls:**

- `zOrder`
- `sortLinked`

<details><summary>Code</summary>

```typescript
function indexCurve(start, minX, minY, invSize) {
    let p = start;
    do {
        if (p.z === 0) p.z = zOrder(p.x, p.y, minX, minY, invSize);
        p.prevZ = p.prev;
        p.nextZ = p.next;
        p = p.next;
    } while (p !== start);

    p.prevZ.nextZ = null;
    p.prevZ = null;

    sortLinked(p);
}
```
</details>

### `sortLinked(list: any): any`

**Parameters:**

- **`list`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function sortLinked(list) {
    let numMerges;
    let inSize = 1;

    do {
        let p = list;
        let e;
        list = null;
        let tail = null;
        numMerges = 0;

        while (p) {
            numMerges++;
            let q = p;
            let pSize = 0;
            for (let i = 0; i < inSize; i++) {
                pSize++;
                q = q.nextZ;
                if (!q) break;
            }
            let qSize = inSize;

            while (pSize > 0 || (qSize > 0 && q)) {

                if (pSize !== 0 && (qSize === 0 || !q || p.z <= q.z)) {
                    e = p;
                    p = p.nextZ;
                    pSize--;
                } else {
                    e = q;
                    q = q.nextZ;
                    qSize--;
                }

                if (tail) tail.nextZ = e;
                else list = e;

                e.prevZ = tail;
                tail = e;
            }

            p = q;
        }

        tail.nextZ = null;
        inSize *= 2;

    } while (numMerges > 1);

    return list;
}
```
</details>

### `zOrder(x: any, y: any, minX: any, minY: any, invSize: any): number`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`minX`** `any`
- **`minY`** `any`
- **`invSize`** `any`

**Returns:** `number`

**Internal Comments:**
```
// coords are transformed into non-negative 15-bit integer range (x3)
```

<details><summary>Code</summary>

```typescript
function zOrder(x, y, minX, minY, invSize) {
    // coords are transformed into non-negative 15-bit integer range
    x = (x - minX) * invSize | 0;
    y = (y - minY) * invSize | 0;

    x = (x | (x << 8)) & 0x00FF00FF;
    x = (x | (x << 4)) & 0x0F0F0F0F;
    x = (x | (x << 2)) & 0x33333333;
    x = (x | (x << 1)) & 0x55555555;

    y = (y | (y << 8)) & 0x00FF00FF;
    y = (y | (y << 4)) & 0x0F0F0F0F;
    y = (y | (y << 2)) & 0x33333333;
    y = (y | (y << 1)) & 0x55555555;

    return x | (y << 1);
}
```
</details>

### `getLeftmost(start: any): any`

**Parameters:**

- **`start`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getLeftmost(start) {
    let p = start,
        leftmost = start;
    do {
        if (p.x < leftmost.x || (p.x === leftmost.x && p.y < leftmost.y)) leftmost = p;
        p = p.next;
    } while (p !== start);

    return leftmost;
}
```
</details>

### `pointInTriangle(ax: any, ay: any, bx: any, by: any, cx: any, cy: any, px: any, py: any): boolean`

**Parameters:**

- **`ax`** `any`
- **`ay`** `any`
- **`bx`** `any`
- **`by`** `any`
- **`cx`** `any`
- **`cy`** `any`
- **`px`** `any`
- **`py`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function pointInTriangle(ax, ay, bx, by, cx, cy, px, py) {
    return (cx - px) * (ay - py) >= (ax - px) * (cy - py) &&
           (ax - px) * (by - py) >= (bx - px) * (ay - py) &&
           (bx - px) * (cy - py) >= (cx - px) * (by - py);
}
```
</details>

### `pointInTriangleExceptFirst(ax: any, ay: any, bx: any, by: any, cx: any, cy: any, px: any, py: any): boolean`

**Parameters:**

- **`ax`** `any`
- **`ay`** `any`
- **`bx`** `any`
- **`by`** `any`
- **`cx`** `any`
- **`cy`** `any`
- **`px`** `any`
- **`py`** `any`

**Returns:** `boolean`

**Calls:**

- `pointInTriangle`

<details><summary>Code</summary>

```typescript
function pointInTriangleExceptFirst(ax, ay, bx, by, cx, cy, px, py) {
    return !(ax === px && ay === py) && pointInTriangle(ax, ay, bx, by, cx, cy, px, py);
}
```
</details>

### `isValidDiagonal(a: any, b: any): number | boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number | boolean`

**Calls:**

- `intersectsPolygon`
- `locallyInside`
- `middleInside`
- `area`
- `equals`

<details><summary>Code</summary>

```typescript
function isValidDiagonal(a, b) {
    return a.next.i !== b.i && a.prev.i !== b.i && !intersectsPolygon(a, b) && // dones't intersect other edges
           (locallyInside(a, b) && locallyInside(b, a) && middleInside(a, b) && // locally visible
            (area(a.prev, a, b.prev) || area(a, b.prev, b)) || // does not create opposite-facing sectors
            equals(a, b) && area(a.prev, a, a.next) > 0 && area(b.prev, b, b.next) > 0); // special zero-length case
}
```
</details>

### `area(p: any, q: any, r: any): number`

**Parameters:**

- **`p`** `any`
- **`q`** `any`
- **`r`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function area(p, q, r) {
    return (q.y - p.y) * (r.x - q.x) - (q.x - p.x) * (r.y - q.y);
}
```
</details>

### `equals(p1: any, p2: any): boolean`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function equals(p1, p2) {
    return p1.x === p2.x && p1.y === p2.y;
}
```
</details>

### `intersects(p1: any, q1: any, p2: any, q2: any): boolean`

**Parameters:**

- **`p1`** `any`
- **`q1`** `any`
- **`p2`** `any`
- **`q2`** `any`

**Returns:** `boolean`

**Calls:**

- `sign`
- `area`
- `onSegment`

<details><summary>Code</summary>

```typescript
function intersects(p1, q1, p2, q2) {
    const o1 = sign(area(p1, q1, p2));
    const o2 = sign(area(p1, q1, q2));
    const o3 = sign(area(p2, q2, p1));
    const o4 = sign(area(p2, q2, q1));

    if (o1 !== o2 && o3 !== o4) return true; // general case

    if (o1 === 0 && onSegment(p1, p2, q1)) return true; // p1, q1 and p2 are collinear and p2 lies on p1q1
    if (o2 === 0 && onSegment(p1, q2, q1)) return true; // p1, q1 and q2 are collinear and q2 lies on p1q1
    if (o3 === 0 && onSegment(p2, p1, q2)) return true; // p2, q2 and p1 are collinear and p1 lies on p2q2
    if (o4 === 0 && onSegment(p2, q1, q2)) return true; // p2, q2 and q1 are collinear and q1 lies on p2q2

    return false;
}
```
</details>

### `onSegment(p: any, q: any, r: any): boolean`

**Parameters:**

- **`p`** `any`
- **`q`** `any`
- **`r`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function onSegment(p, q, r) {
    return q.x <= Math.max(p.x, r.x) && q.x >= Math.min(p.x, r.x) && q.y <= Math.max(p.y, r.y) && q.y >= Math.min(p.y, r.y);
}
```
</details>

### `sign(num: any): 1 | 0 | -1`

**Parameters:**

- **`num`** `any`

**Returns:** `1 | 0 | -1`

<details><summary>Code</summary>

```typescript
function sign(num) {
    return num > 0 ? 1 : num < 0 ? -1 : 0;
}
```
</details>

### `intersectsPolygon(a: any, b: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `boolean`

**Calls:**

- `intersects`

<details><summary>Code</summary>

```typescript
function intersectsPolygon(a, b) {
    let p = a;
    do {
        if (p.i !== a.i && p.next.i !== a.i && p.i !== b.i && p.next.i !== b.i &&
                intersects(p, p.next, a, b)) return true;
        p = p.next;
    } while (p !== a);

    return false;
}
```
</details>

### `locallyInside(a: any, b: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `boolean`

**Calls:**

- `area`

<details><summary>Code</summary>

```typescript
function locallyInside(a, b) {
    return area(a.prev, a, a.next) < 0 ?
        area(a, b, a.next) >= 0 && area(a, a.prev, b) >= 0 :
        area(a, b, a.prev) < 0 || area(a, a.next, b) < 0;
}
```
</details>

### `middleInside(a: any, b: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function middleInside(a, b) {
    let p = a;
    let inside = false;
    const px = (a.x + b.x) / 2;
    const py = (a.y + b.y) / 2;
    do {
        if (((p.y > py) !== (p.next.y > py)) && p.next.y !== p.y &&
                (px < (p.next.x - p.x) * (py - p.y) / (p.next.y - p.y) + p.x))
            inside = !inside;
        p = p.next;
    } while (p !== a);

    return inside;
}
```
</details>

### `splitPolygon(a: any, b: any): { i: any; x: any; y: any; prev: any; next: any; z: number; prevZ: any; nextZ: any; steiner: boolean; }`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `{ i: any; x: any; y: any; prev: any; next: any; z: number; prevZ: any; nextZ: any; steiner: boolean; }`

**Calls:**

- `createNode`

<details><summary>Code</summary>

```typescript
function splitPolygon(a, b) {
    const a2 = createNode(a.i, a.x, a.y),
        b2 = createNode(b.i, b.x, b.y),
        an = a.next,
        bp = b.prev;

    a.next = b;
    b.prev = a;

    a2.next = an;
    an.prev = a2;

    b2.next = a2;
    a2.prev = b2;

    bp.next = b2;
    b2.prev = bp;

    return b2;
}
```
</details>

### `insertNode(i: any, x: any, y: any, last: any): { i: any; x: any; y: any; prev: any; next: any; z: number; prevZ: any; nextZ: any; steiner: boolean; }`

**Parameters:**

- **`i`** `any`
- **`x`** `any`
- **`y`** `any`
- **`last`** `any`

**Returns:** `{ i: any; x: any; y: any; prev: any; next: any; z: number; prevZ: any; nextZ: any; steiner: boolean; }`

**Calls:**

- `createNode`

<details><summary>Code</summary>

```typescript
function insertNode(i, x, y, last) {
    const p = createNode(i, x, y);

    if (!last) {
        p.prev = p;
        p.next = p;

    } else {
        p.next = last.next;
        p.prev = last;
        last.next.prev = p;
        last.next = p;
    }
    return p;
}
```
</details>

### `removeNode(p: any): void`

**Parameters:**

- **`p`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function removeNode(p) {
    p.next.prev = p.prev;
    p.prev.next = p.next;

    if (p.prevZ) p.prevZ.nextZ = p.nextZ;
    if (p.nextZ) p.nextZ.prevZ = p.prevZ;
}
```
</details>

### `createNode(i: any, x: any, y: any): { i: any; x: any; y: any; prev: any; next: any; z: number; prevZ: any; nextZ: any; steiner: boolean; }`

**Parameters:**

- **`i`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `{ i: any; x: any; y: any; prev: any; next: any; z: number; prevZ: any; nextZ: any; steiner: boolean; }`

<details><summary>Code</summary>

```typescript
function createNode(i, x, y) {
    return {
        i, // vertex index in coordinates array
        x, y, // vertex coordinates
        prev: null, // previous and next vertex nodes in a polygon ring
        next: null,
        z: 0, // z-order curve value
        prevZ: null, // previous and next nodes in z-order
        nextZ: null,
        steiner: false // indicates whether this is a steiner point
    };
}
```
</details>

### `deviation(data: any, holeIndices: any, dim: any, triangles: any): number`

**Parameters:**

- **`data`** `any`
- **`holeIndices`** `any`
- **`dim`** `any`
- **`triangles`** `any`

**Returns:** `number`

**Calls:**

- `Math.abs`
- `signedArea`

<details><summary>Code</summary>

```typescript
export function deviation(data, holeIndices, dim, triangles) {
    const hasHoles = holeIndices && holeIndices.length;
    const outerLen = hasHoles ? holeIndices[0] * dim : data.length;

    let polygonArea = Math.abs(signedArea(data, 0, outerLen, dim));
    if (hasHoles) {
        for (let i = 0, len = holeIndices.length; i < len; i++) {
            const start = holeIndices[i] * dim;
            const end = i < len - 1 ? holeIndices[i + 1] * dim : data.length;
            polygonArea -= Math.abs(signedArea(data, start, end, dim));
        }
    }

    let trianglesArea = 0;
    for (let i = 0; i < triangles.length; i += 3) {
        const a = triangles[i] * dim;
        const b = triangles[i + 1] * dim;
        const c = triangles[i + 2] * dim;
        trianglesArea += Math.abs(
            (data[a] - data[c]) * (data[b + 1] - data[a + 1]) -
            (data[a] - data[b]) * (data[c + 1] - data[a + 1]));
    }

    return polygonArea === 0 && trianglesArea === 0 ? 0 :
        Math.abs((trianglesArea - polygonArea) / polygonArea);
}
```
</details>

### `signedArea(data: any, start: any, end: any, dim: any): number`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`end`** `any`
- **`dim`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function signedArea(data, start, end, dim) {
    let sum = 0;
    for (let i = start, j = end - dim; i < end; i += dim) {
        sum += (data[j] - data[i]) * (data[i + 1] + data[j + 1]);
        j = i;
    }
    return sum;
}
```
</details>

### `flatten(data: any): { vertices: any[]; holes: number[]; dimensions: any; }`

**Parameters:**

- **`data`** `any`

**Returns:** `{ vertices: any[]; holes: number[]; dimensions: any; }`

**Calls:**

- `vertices.push`
- `holes.push`

<details><summary>Code</summary>

```typescript
export function flatten(data) {
    const vertices = [];
    const holes = [];
    const dimensions = data[0][0].length;
    let holeIndex = 0;
    let prevLen = 0;

    for (const ring of data) {
        for (const p of ring) {
            for (let d = 0; d < dimensions; d++) vertices.push(p[d]);
        }
        if (prevLen) {
            holeIndex += prevLen;
            holes.push(holeIndex);
        }
        prevLen = ring.length;
    }
    return {vertices, holes, dimensions};
}
```
</details>


---