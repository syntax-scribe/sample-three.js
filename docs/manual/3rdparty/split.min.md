[⬅️ Back to Table of Contents](../../index.md)

# 📄 `split.min.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 📊 Variables & Constants | 47 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/3rdparty/split.min.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `e` | `Window & typeof globalThis` | let/var | `window` | ✗ |
| `t` | `Document` | let/var | `e.document` | ✗ |
| `n` | `string` | let/var | `"addEventListener"` | ✗ |
| `i` | `string` | let/var | `"removeEventListener"` | ✗ |
| `r` | `string` | let/var | `"getBoundingClientRect"` | ✗ |
| `o` | `boolean` | let/var | `e.attachEvent&&!e[n]` | ✗ |
| `a` | `string` | let/var | `["","-webkit-","-moz-","-o-"].filter(function(e){var n=t.createElement("div")...` | ✗ |
| `t` | `any` | let/var | `E[this.a]` | ✗ |
| `n` | `any` | let/var | `E[this.b]` | ✗ |
| `i` | `any` | let/var | `t.size+n.size` | ✗ |
| `t` | `any` | let/var | `*not shown*` | ✗ |
| `e` | `any` | let/var | `E[this.a].element` | ✗ |
| `t` | `any` | let/var | `E[this.b].element` | ✗ |
| `t` | `this` | let/var | `this` | ✗ |
| `n` | `any` | let/var | `E[t.a].element` | ✗ |
| `r` | `any` | let/var | `E[t.b].element` | ✗ |
| `i` | `this` | let/var | `this` | ✗ |
| `r` | `any` | let/var | `E[i.a].element` | ✗ |
| `o` | `any` | let/var | `E[i.b].element` | ✗ |
| `i` | `any` | let/var | `F[n-1]` | ✗ |
| `r` | `any` | let/var | `E[i.a]` | ✗ |
| `s` | `any` | let/var | `E[i.b]` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `any` | let/var | `*not shown*` | ✗ |
| `G` | `any` | let/var | `*not shown*` | ✗ |
| `E` | `any` | let/var | `*not shown*` | ✗ |
| `w` | `any` | let/var | `l(u[0]).parentNode` | ✗ |
| `D` | `string` | let/var | `e.getComputedStyle(w).flexDirection` | ✗ |
| `U` | `any` | let/var | `c.sizes\|\|u.map(function(){return 100/u.length})` | ✗ |
| `k` | `any` | let/var | `void 0!==c.minSize?c.minSize:100` | ✗ |
| `x` | `any` | let/var | `Array.isArray(k)?k:u.map(function(){return k})` | ✗ |
| `L` | `any` | let/var | `void 0!==c.gutterSize?c.gutterSize:10` | ✗ |
| `M` | `any` | let/var | `void 0!==c.snapOffset?c.snapOffset:30` | ✗ |
| `O` | `any` | let/var | `c.direction\|\|"horizontal"` | ✗ |
| `j` | `any` | let/var | `c.cursor\|\|("horizontal"===O?"ew-resize":"ns-resize")` | ✗ |
| `C` | `any` | let/var | `c.gutter\|\|function(e,n){var i=t.createElement("div");return i.className="gu...` | ✗ |
| `i` | `{}` | let/var | `{}` | ✗ |
| `A` | `any` | let/var | `c.elementStyle\|\|function(e,t,n){var i={};return"string"==typeof t\|\|t inst...` | ✗ |
| `n` | `any` | let/var | `*not shown*` | ✗ |
| `B` | `any` | let/var | `c.gutterStyle\|\|function(e,t){return n={},n[e]=t+"px",n;var n}` | ✗ |
| `F` | `any[]` | let/var | `[]` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `s` | `{ element: any; size: any; minSize: a...` | let/var | `{element:l(e),size:U[t],minSize:x[t]}` | ✗ |
| `a` | `number` | let/var | `i.a` | ✗ |
| `f` | `any` | let/var | `s.element[r]()[y]` | ✗ |
| `t` | `any` | let/var | `F[e-1]` | ✗ |
| `n` | `any` | let/var | `F[e]` | ✗ |


---

## Functions

### `s(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(){return!1}
```
</details>

### `l(e: any): any`

**Parameters:**

- **`e`** `any`

**Returns:** `any`

**Calls:**

- `t.querySelector`

<details><summary>Code</summary>

```typescript
function(e){return"string"==typeof e||e instanceof String?t.querySelector(e):e}
```
</details>

### `z(e: any, t: any, n: any): void`

**Parameters:**

- **`e`** `any`
- **`t`** `any`
- **`n`** `any`

**Returns:** `void`

**Calls:**

- `A`
- `Object.keys(i).forEach`

<details><summary>Code</summary>

```typescript
function z(e,t,n){var i=A(y,t,n);Object.keys(i).forEach(function(t){return e.style[t]=i[t]})}
```
</details>

### `h(e: any, t: any): void`

**Parameters:**

- **`e`** `any`
- **`t`** `any`

**Returns:** `void`

**Calls:**

- `B`
- `Object.keys(n).forEach`

<details><summary>Code</summary>

```typescript
function h(e,t){var n=B(y,t);Object.keys(n).forEach(function(t){return e.style[t]=n[t]})}
```
</details>

### `f(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `z`

<details><summary>Code</summary>

```typescript
function f(e){var t=E[this.a],n=E[this.b],i=t.size+n.size;t.size=e/this.size*i,n.size=i-e/this.size*i,z(t.element,t.size,this.aGutterSize),z(n.element,n.size,this.bGutterSize)}
```
</details>

### `m(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `f.call`
- `c.onDrag`

<details><summary>Code</summary>

```typescript
function m(e){var t;this.dragging&&((t="touches"in e?e.touches[0][b]-this.start:e[b]-this.start)<=E[this.a].minSize+M+this.aGutterSize?t=E[this.a].minSize+this.aGutterSize:t>=this.size-(E[this.b].minSize+M+this.bGutterSize)&&(t=this.size-(E[this.b].minSize+this.bGutterSize)),f.call(this,t),c.onDrag&&c.onDrag())}
```
</details>

### `g(): void`

**Returns:** `void`

**Calls:**

- `complex_call_1346`
- `complex_call_1356`
- `complex_call_1411`

<details><summary>Code</summary>

```typescript
function g(){var e=E[this.a].element,t=E[this.b].element;this.size=e[r]()[y]+t[r]()[y]+this.aGutterSize+this.bGutterSize,this.start=e[r]()[G]}
```
</details>

### `d(): void`

**Returns:** `void`

**Calls:**

- `c.onDragEnd`
- `complex_call_1532`
- `complex_call_1555`
- `complex_call_1579`
- `complex_call_1606`
- `complex_call_1638`
- `complex_call_1698`
- `complex_call_1720`
- `complex_call_1740`
- `complex_call_1762`

<details><summary>Code</summary>

```typescript
function d(){var t=this,n=E[t.a].element,r=E[t.b].element;t.dragging&&c.onDragEnd&&c.onDragEnd(),t.dragging=!1,e[i]("mouseup",t.stop),e[i]("touchend",t.stop),e[i]("touchcancel",t.stop),t.parent[i]("mousemove",t.move),t.parent[i]("touchmove",t.move),delete t.stop,delete t.move,n[i]("selectstart",s),n[i]("dragstart",s),r[i]("selectstart",s),r[i]("dragstart",s),n.style.userSelect="",n.style.webkitUserSelect="",n.style.MozUserSelect="",n.style.pointerEvents="",r.style.userSelect="",r.style.webkitUserSelect="",r.style.MozUserSelect="",r.style.pointerEvents="",t.gutter.style.cursor="",t.parent.style.cursor=""}
```
</details>

### `S(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `c.onDragStart`
- `t.preventDefault`
- `m.bind`
- `d.bind`
- `complex_call_2202`
- `complex_call_2225`
- `complex_call_2249`
- `complex_call_2276`
- `complex_call_2308`
- `complex_call_2340`
- `complex_call_2362`
- `complex_call_2382`
- `complex_call_2404`
- `g.call`

<details><summary>Code</summary>

```typescript
function S(t){var i=this,r=E[i.a].element,o=E[i.b].element;!i.dragging&&c.onDragStart&&c.onDragStart(),t.preventDefault(),i.dragging=!0,i.move=m.bind(i),i.stop=d.bind(i),e[n]("mouseup",i.stop),e[n]("touchend",i.stop),e[n]("touchcancel",i.stop),i.parent[n]("mousemove",i.move),i.parent[n]("touchmove",i.move),r[n]("selectstart",s),r[n]("dragstart",s),o[n]("selectstart",s),o[n]("dragstart",s),r.style.userSelect="none",r.style.webkitUserSelect="none",r.style.MozUserSelect="none",r.style.pointerEvents="none",o.style.userSelect="none",o.style.webkitUserSelect="none",o.style.MozUserSelect="none",o.style.pointerEvents="none",i.gutter.style.cursor=j,i.parent.style.cursor=j,g.call(i)}
```
</details>

### `v(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `e.forEach`
- `z`

<details><summary>Code</summary>

```typescript
function v(e){e.forEach(function(t,n){if(n>0){var i=F[n-1],r=E[i.a],s=E[i.b];r.size=e[n-1],s.size=t,z(r.element,r.size,i.aGutterSize),z(s.element,s.size,i.bGutterSize)}})}
```
</details>

### `p(): void`

**Returns:** `void`

**Calls:**

- `F.forEach`
- `e.parent.removeChild`

<details><summary>Code</summary>

```typescript
function p(){F.forEach(function(e){e.parent.removeChild(e.gutter),E[e.a].element.style[y]="",E[e.b].element.style[y]=""})}
```
</details>

### `getSizes(): any`

**Returns:** `any`

**Calls:**

- `E.map`

<details><summary>Code</summary>

```typescript
function(){return E.map(function(e){return e.size})}
```
</details>

### `collapse(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `g.call`
- `f.call`

<details><summary>Code</summary>

```typescript
function(e){if(e===F.length){var t=F[e-1];g.call(t),o||f.call(t,t.size-t.bGutterSize)}else{var n=F[e];g.call(n),o||f.call(n,n.aGutterSize)}}
```
</details>

### `getSizes(): any`

**Returns:** `any`

**Calls:**

- `E.map`

<details><summary>Code</summary>

```typescript
function(){return E.map(function(e){return e.size})}
```
</details>

### `collapse(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `g.call`
- `f.call`

<details><summary>Code</summary>

```typescript
function(e){if(e===F.length){var t=F[e-1];g.call(t),o||f.call(t,t.size-t.bGutterSize)}else{var n=F[e];g.call(n),o||f.call(n,n.aGutterSize)}}
```
</details>


---