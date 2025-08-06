[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `walk.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 📊 Variables & Constants | 24 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/acorn/walk.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `g` | `any` | let/var | `*not shown*` | ✗ |
| `define` | `any` | let/var | `*not shown*` | ✗ |
| `module` | `any` | let/var | `*not shown*` | ✗ |
| `exports` | `any` | let/var | `*not shown*` | ✗ |
| `a` | `Require` | let/var | `typeof require=="function"&&require` | ✗ |
| `f` | `Error` | let/var | `new Error("Cannot find module '"+o+"'")` | ✗ |
| `l` | `{ exports: {}; }` | let/var | `n[o]={exports:{}}` | ✗ |
| `n` | `any` | let/var | `t[o][1][e]` | ✗ |
| `i` | `Require` | let/var | `typeof require=="function"&&require` | ✗ |
| `type` | `any` | let/var | `override \|\| node.type` | ✗ |
| `found` | `any` | let/var | `visitors[type]` | ✗ |
| `type` | `any` | let/var | `override \|\| node.type` | ✗ |
| `found` | `any` | let/var | `visitors[type]` | ✗ |
| `visitor` | `any` | let/var | `funcs ? exports.make(funcs, base) : base` | ✗ |
| `type` | `any` | let/var | `override \|\| node.type` | ✗ |
| `type` | `any` | let/var | `override \|\| node.type` | ✗ |
| `type` | `any` | let/var | `override \|\| node.type` | ✗ |
| `max` | `any` | let/var | `undefined` | ✗ |
| `type` | `any` | let/var | `override \|\| node.type` | ✗ |
| `visitor` | `{}` | let/var | `{}` | ✗ |
| `base` | `{ Program: (node: any, st: any, c: an...` | let/var | `{}` | ✗ |
| `cs` | `any` | let/var | `node.cases[i]` | ✗ |
| `decl` | `any` | let/var | `node.declarations[i]` | ✗ |
| `elt` | `any` | let/var | `node.elements[i]` | ✗ |


---

## Functions

### `s(o: any, u: any): any`

**Parameters:**

- **`o`** `any`
- **`u`** `any`

**Returns:** `any`

**Calls:**

- `a`
- `i`
- `t[o][0].call`
- `s`

<details><summary>Code</summary>

```typescript
function s(o,u){if(!n[o]){if(!t[o]){var a=typeof require=="function"&&require;if(!u&&a)return a(o,!0);if(i)return i(o,!0);var f=new Error("Cannot find module '"+o+"'");throw f.code="MODULE_NOT_FOUND",f}var l=n[o]={exports:{}};t[o][0].call(l.exports,function(e){var n=t[o][1][e];return s(n?n:e)},l,l.exports,e,t,n,r)}return n[o].exports}
```
</details>

### `_classCallCheck(instance: any, Constructor: any): void`

**Parameters:**

- **`instance`** `any`
- **`Constructor`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function (instance, Constructor) { if (!(instance instanceof Constructor)) { throw new TypeError("Cannot call a class as a function"); } }
```
</details>

### `simple(node: any, visitors: any, base: any, state: any): void`

**Parameters:**

- **`node`** `any`
- **`visitors`** `any`
- **`base`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_3050`
- `complex_call_3158`
- `found`

<details><summary>Code</summary>

```typescript
function simple(node, visitors, base, state) {
  if (!base) base = exports.base;(function c(node, st, override) {
    var type = override || node.type,
        found = visitors[type];
    base[type](node, st, c);
    if (found) found(node, st);
  })(node, state);
}
```
</details>

### `ancestor(node: any, visitors: any, base: any, state: any): void`

**Parameters:**

- **`node`** `any`
- **`visitors`** `any`
- **`base`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_3345`
- `st.slice`
- `st.push`
- `complex_call_3540`
- `found`

<details><summary>Code</summary>

```typescript
function ancestor(node, visitors, base, state) {
  if (!base) base = exports.base;
  if (!state) state = [];(function c(node, st, override) {
    var type = override || node.type,
        found = visitors[type];
    if (node != st[st.length - 1]) {
      st = st.slice();
      st.push(node);
    }
    base[type](node, st, c);
    if (found) found(node, st);
  })(node, state);
}
```
</details>

### `recursive(node: any, state: any, funcs: any, base: any): void`

**Parameters:**

- **`node`** `any`
- **`state`** `any`
- **`funcs`** `any`
- **`base`** `any`

**Returns:** `void`

**Calls:**

- `exports.make`
- `complex_call_3723`
- `complex_call_3761`

<details><summary>Code</summary>

```typescript
function recursive(node, state, funcs, base) {
  var visitor = funcs ? exports.make(funcs, base) : base;(function c(node, st, override) {
    visitor[override || node.type](node, st, c);
  })(node, state);
}
```
</details>

### `makeTest(test: any): any`

**Parameters:**

- **`test`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function makeTest(test) {
  if (typeof test == "string") {
    return function (type) {
      return type == test;
    };
  } else if (!test) {
    return function () {
      return true;
    };
  } else {
    return test;
  }
}
```
</details>

### `Found(node: any, state: any): void`

**Parameters:**

- **`node`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `_classCallCheck`

<details><summary>Code</summary>

```typescript
function Found(node, state) {
  _classCallCheck(this, Found);

  this.node = node;this.state = state;
}
```
</details>

### `findNodeAt(node: any, start: any, end: any, test: any, base: any, state: any): Found`

**Parameters:**

- **`node`** `any`
- **`start`** `any`
- **`end`** `any`
- **`test`** `any`
- **`base`** `any`
- **`state`** `any`

**Returns:** `Found`

**Calls:**

- `makeTest`
- `complex_call_4307`
- `complex_call_4467`
- `test`

<details><summary>Code</summary>

```typescript
function findNodeAt(node, start, end, test, base, state) {
  test = makeTest(test);
  if (!base) base = exports.base;
  try {
    ;(function c(node, st, override) {
      var type = override || node.type;
      if ((start == null || node.start <= start) && (end == null || node.end >= end)) base[type](node, st, c);
      if (test(type, node) && (start == null || node.start == start) && (end == null || node.end == end)) throw new Found(node, st);
    })(node, state);
  } catch (e) {
    if (e instanceof Found) {
      return e;
    }throw e;
  }
}
```
</details>

### `findNodeAround(node: any, pos: any, test: any, base: any, state: any): Found`

**Parameters:**

- **`node`** `any`
- **`pos`** `any`
- **`test`** `any`
- **`base`** `any`
- **`state`** `any`

**Returns:** `Found`

**Calls:**

- `makeTest`
- `complex_call_4857`
- `complex_call_5002`
- `test`

<details><summary>Code</summary>

```typescript
function findNodeAround(node, pos, test, base, state) {
  test = makeTest(test);
  if (!base) base = exports.base;
  try {
    ;(function c(node, st, override) {
      var type = override || node.type;
      if (node.start > pos || node.end < pos) {
        return;
      }base[type](node, st, c);
      if (test(type, node)) throw new Found(node, st);
    })(node, state);
  } catch (e) {
    if (e instanceof Found) {
      return e;
    }throw e;
  }
}
```
</details>

### `findNodeAfter(node: any, pos: any, test: any, base: any, state: any): Found`

**Parameters:**

- **`node`** `any`
- **`pos`** `any`
- **`test`** `any`
- **`base`** `any`
- **`state`** `any`

**Returns:** `Found`

**Calls:**

- `makeTest`
- `complex_call_5313`
- `test`
- `complex_call_5514`

<details><summary>Code</summary>

```typescript
function findNodeAfter(node, pos, test, base, state) {
  test = makeTest(test);
  if (!base) base = exports.base;
  try {
    ;(function c(node, st, override) {
      if (node.end < pos) {
        return;
      }var type = override || node.type;
      if (node.start >= pos && test(type, node)) throw new Found(node, st);
      base[type](node, st, c);
    })(node, state);
  } catch (e) {
    if (e instanceof Found) {
      return e;
    }throw e;
  }
}
```
</details>

### `findNodeBefore(node: any, pos: any, test: any, base: any, state: any): Found`

**Parameters:**

- **`node`** `any`
- **`pos`** `any`
- **`test`** `any`
- **`base`** `any`
- **`state`** `any`

**Returns:** `Found`

**Calls:**

- `makeTest`
- `complex_call_5780`
- `test`
- `complex_call_6008`

<details><summary>Code</summary>

```typescript
function findNodeBefore(node, pos, test, base, state) {
  test = makeTest(test);
  if (!base) base = exports.base;
  var max = undefined;(function c(node, st, override) {
    if (node.start > pos) {
      return;
    }var type = override || node.type;
    if (node.end <= pos && (!max || max.node.end < node.end) && test(type, node)) max = new Found(node, st);
    base[type](node, st, c);
  })(node, state);
  return max;
}
```
</details>

### `make(funcs: any, base: any): {}`

**Parameters:**

- **`funcs`** `any`
- **`base`** `any`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function make(funcs, base) {
  if (!base) base = exports.base;
  var visitor = {};
  for (var type in base) visitor[type] = base[type];
  for (var type in funcs) visitor[type] = funcs[type];
  return visitor;
}
```
</details>

### `skipThrough(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function skipThrough(node, st, c) {
  c(node, st);
}
```
</details>

### `ignore(_node: any, _st: any, _c: any): void`

**Parameters:**

- **`_node`** `any`
- **`_st`** `any`
- **`_c`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ignore(_node, _st, _c) {}
```
</details>


---