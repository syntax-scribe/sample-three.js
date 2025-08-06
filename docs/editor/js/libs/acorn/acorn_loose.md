[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `acorn_loose.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 📊 Variables & Constants | 85 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/acorn/acorn_loose.js`**

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
| `LooseParser` | `any` | let/var | `_state.LooseParser` | ✗ |
| `p` | `any` | let/var | `new LooseParser(input, options)` | ✗ |
| `LooseParser` | `any` | let/var | `require("./state").LooseParser` | ✗ |
| `isDummy` | `any` | let/var | `require("./parseutil").isDummy` | ✗ |
| `tt` | `any` | let/var | `require("..").tokTypes` | ✗ |
| `lp` | `any` | let/var | `LooseParser.prototype` | ✗ |
| `indent` | `any` | let/var | `this.curIndent` | ✗ |
| `line` | `any` | let/var | `this.curLineStart` | ✗ |
| `prec` | `any` | let/var | `this.tok.type.binop` | ✗ |
| `update` | `boolean` | let/var | `this.tok.type === tt.incDec` | ✗ |
| `node` | `any` | let/var | `undefined` | ✗ |
| `type` | `string` | let/var | `this.tok.type === tt._this ? "ThisExpression" : "Super"` | ✗ |
| `val` | `any` | let/var | `this.tok.value` | ✗ |
| `startIndent` | `any` | let/var | `this.curIndent` | ✗ |
| `line` | `any` | let/var | `this.curLineStart` | ✗ |
| `indent` | `any` | let/var | `this.curIndent + 1` | ✗ |
| `line` | `any` | let/var | `this.curLineStart` | ✗ |
| `isGenerator` | `any` | let/var | `undefined` | ✗ |
| `start` | `any` | let/var | `undefined` | ✗ |
| `key` | `any` | let/var | `this.tok.type === tt.num \|\| this.tok.type === tt.string ? this.parseExprAto...` | ✗ |
| `name` | `any` | let/var | `this.tok.type === tt.name ? this.tok.value : this.tok.type.keyword` | ✗ |
| `props` | `any` | let/var | `node.properties` | ✗ |
| `indent` | `any` | let/var | `this.curIndent` | ✗ |
| `line` | `any` | let/var | `this.curLineStart` | ✗ |
| `elts` | `any[]` | let/var | `[]` | ✗ |
| `LooseParser` | `any` | let/var | `require("./state").LooseParser` | ✗ |
| `Node` | `any` | let/var | `_.Node` | ✗ |
| `SourceLocation` | `any` | let/var | `_.SourceLocation` | ✗ |
| `lineBreak` | `any` | let/var | `_.lineBreak` | ✗ |
| `isNewLine` | `any` | let/var | `_.isNewLine` | ✗ |
| `tt` | `any` | let/var | `_.tokTypes` | ✗ |
| `lp` | `any` | let/var | `LooseParser.prototype` | ✗ |
| `node` | `any` | let/var | `new Node()` | ✗ |
| `node` | `any` | let/var | `new Node()` | ✗ |
| `tokenizer` | `any` | let/var | `_.tokenizer` | ✗ |
| `SourceLocation` | `any` | let/var | `_.SourceLocation` | ✗ |
| `tt` | `any` | let/var | `_.tokTypes` | ✗ |
| `LooseParser` | `any` | let/var | `require("./state").LooseParser` | ✗ |
| `isDummy` | `any` | let/var | `require("./parseutil").isDummy` | ✗ |
| `getLineInfo` | `any` | let/var | `_.getLineInfo` | ✗ |
| `tt` | `any` | let/var | `_.tokTypes` | ✗ |
| `lp` | `any` | let/var | `LooseParser.prototype` | ✗ |
| `starttype` | `any` | let/var | `this.tok.type` | ✗ |
| `isBreak` | `boolean` | let/var | `starttype === tt._break` | ✗ |
| `blockIndent` | `any` | let/var | `this.curIndent` | ✗ |
| `line` | `any` | let/var | `this.curLineStart` | ✗ |
| `cur` | `any` | let/var | `undefined` | ✗ |
| `isCase` | `boolean` | let/var | `this.tok.type === tt._case` | ✗ |
| `blockIndent` | `any` | let/var | `this.curIndent` | ✗ |
| `line` | `any` | let/var | `this.curLineStart` | ✗ |
| `type` | `string` | let/var | `this.tok.type === tt._in ? "ForInStatement" : "ForOfStatement"` | ✗ |
| `indent` | `any` | let/var | `this.curIndent + 1` | ✗ |
| `line` | `any` | let/var | `this.curLineStart` | ✗ |
| `isGenerator` | `any` | let/var | `undefined` | ✗ |
| `start` | `any` | let/var | `undefined` | ✗ |
| `elt` | `any` | let/var | `undefined` | ✗ |
| `elts` | `any[]` | let/var | `[]` | ✗ |
| `indent` | `any` | let/var | `this.curIndent` | ✗ |
| `line` | `any` | let/var | `this.curLineStart` | ✗ |
| `continuedLine` | `any` | let/var | `this.nextLineStart` | ✗ |
| `elts` | `any[]` | let/var | `[]` | ✗ |
| `indent` | `any` | let/var | `this.curIndent` | ✗ |
| `line` | `any` | let/var | `this.curLineStart` | ✗ |
| `continuedLine` | `any` | let/var | `this.nextLineStart` | ✗ |
| `tt` | `any` | let/var | `_.tokTypes` | ✗ |
| `Token` | `any` | let/var | `_.Token` | ✗ |
| `isNewLine` | `any` | let/var | `_.isNewLine` | ✗ |
| `SourceLocation` | `any` | let/var | `_.SourceLocation` | ✗ |
| `getLineInfo` | `any` | let/var | `_.getLineInfo` | ✗ |
| `lineBreakG` | `any` | let/var | `_.lineBreakG` | ✗ |
| `LooseParser` | `any` | let/var | `require("./state").LooseParser` | ✗ |
| `lp` | `any` | let/var | `LooseParser.prototype` | ✗ |
| `msg` | `string` | let/var | `e.message` | ✗ |
| `pos` | `any` | let/var | `e.raisedAt` | ✗ |
| `replace` | `boolean` | let/var | `true` | ✗ |
| `match` | `any` | let/var | `undefined` | ✗ |


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

### `_interopRequireWildcard(obj: any): any`

**Parameters:**

- **`obj`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (obj) { return obj && obj.__esModule ? obj : { "default": obj }; }
```
</details>

### `parse_dammit(input: any, options: any): any`

**Parameters:**

- **`input`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `p.next`
- `p.parseTopLevel`

<details><summary>Code</summary>

```typescript
function parse_dammit(input, options) {
  var p = new LooseParser(input, options);
  p.next();
  return p.parseTopLevel();
}
```
</details>

### `isDummy(node: any): boolean`

**Parameters:**

- **`node`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isDummy(node) {
  return node.name == "✖";
}
```
</details>

### `LooseParser(input: any, options: any): void`

**Parameters:**

- **`input`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `tokenizer`
- `this.toks.curPosition`
- `this.lineEnd`

<details><summary>Code</summary>

```typescript
function LooseParser(input, options) {
  this.toks = tokenizer(input, options);
  this.options = this.toks.options;
  this.input = this.toks.input;
  this.tok = this.last = { type: tt.eof, start: 0, end: 0 };
  if (this.options.locations) {
    var here = this.toks.curPosition();
    this.tok.loc = new SourceLocation(this.toks, here, here);
  }
  this.ahead = []; // Tokens ahead
  this.context = []; // Indentation contexted
  this.curIndent = 0;
  this.curLineStart = 0;
  this.nextLineStart = this.lineEnd(this.curLineStart) + 1;
}
```
</details>

### `isSpace(ch: any): any`

**Parameters:**

- **`ch`** `any`

**Returns:** `any`

**Calls:**

- `isNewLine`

<details><summary>Code</summary>

```typescript
function isSpace(ch) {
  return ch < 14 && ch > 8 || ch === 32 || ch === 160 || isNewLine(ch);
}
```
</details>


---