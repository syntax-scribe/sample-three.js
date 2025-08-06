[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `acorn.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 47 |
| 📊 Variables & Constants | 197 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/acorn/acorn.js`**

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
| `Parser` | `any` | let/var | `_state.Parser` | ✗ |
| `getOptions` | `any` | let/var | `_options.getOptions` | ✗ |
| `version` | `string` | let/var | `"1.0.1"` | ✗ |
| `startPos` | `any` | let/var | `p.options.locations ? [p.pos, p.curPosition()] : p.pos` | ✗ |
| `tt` | `any` | let/var | `require("./tokentype").types` | ✗ |
| `Parser` | `any` | let/var | `require("./state").Parser` | ✗ |
| `reservedWords` | `any` | let/var | `require("./identifier").reservedWords` | ✗ |
| `has` | `any` | let/var | `require("./util").has` | ✗ |
| `pp` | `any` | let/var | `Parser.prototype` | ✗ |
| `key` | `any` | let/var | `prop.key` | ✗ |
| `name` | `any` | let/var | `undefined` | ✗ |
| `kind` | `any` | let/var | `prop.kind \|\| "init"` | ✗ |
| `other` | `any` | let/var | `undefined` | ✗ |
| `isGetSet` | `boolean` | let/var | `kind !== "init"` | ✗ |
| `failOnShorthandAssign` | `any` | let/var | `undefined` | ✗ |
| `prec` | `any` | let/var | `this.type.binop` | ✗ |
| `op` | `any` | let/var | `this.type` | ✗ |
| `update` | `boolean` | let/var | `this.type === tt.incDec` | ✗ |
| `node` | `any` | let/var | `undefined` | ✗ |
| `type` | `string` | let/var | `this.type === tt._this ? "ThisExpression" : "Super"` | ✗ |
| `value` | `any` | let/var | `this.value` | ✗ |
| `val` | `any` | let/var | `undefined` | ✗ |
| `exprList` | `any[]` | let/var | `[]` | ✗ |
| `first` | `boolean` | let/var | `true` | ✗ |
| `refShorthandDefaultPos` | `{ start: number; }` | let/var | `{ start: 0 }` | ✗ |
| `spreadStart` | `any` | let/var | `undefined` | ✗ |
| `innerParenStart` | `any` | let/var | `undefined` | ✗ |
| `empty` | `any[]` | let/var | `[]` | ✗ |
| `first` | `boolean` | let/var | `true` | ✗ |
| `propHash` | `{}` | let/var | `{}` | ✗ |
| `isGenerator` | `any` | let/var | `undefined` | ✗ |
| `start` | `any` | let/var | `undefined` | ✗ |
| `allowExpressionBody` | `any` | let/var | `undefined` | ✗ |
| `isExpression` | `boolean` | let/var | `allowExpression && this.type !== tt.braceL` | ✗ |
| `oldInFunc` | `undefined` | let/var | `this.inFunction` | ✗ |
| `oldInGen` | `undefined` | let/var | `this.inGenerator` | ✗ |
| `oldLabels` | `undefined` | let/var | `this.labels` | ✗ |
| `nameHash` | `{}` | let/var | `{}` | ✗ |
| `oldStrict` | `undefined` | let/var | `this.strict` | ✗ |
| `elts` | `any[]` | let/var | `[]` | ✗ |
| `first` | `boolean` | let/var | `true` | ✗ |
| `f` | `string` | let/var | `""` | ✗ |
| `cats` | `any[]` | let/var | `[]` | ✗ |
| `cat` | `any[]` | let/var | `cats[i]` | ✗ |
| `reservedWords` | `{ 3: Function; 5: Function; 6: Functi...` | let/var | `{ 3: makePredicate("abstract boolean byte char class double enum export exten...` | ✗ |
| `ecma5AndLessKeywords` | `string` | let/var | `"break case catch continue debugger default do else finally for function if r...` | ✗ |
| `keywords` | `{ 5: Function; 6: Function; }` | let/var | `{ 5: makePredicate(ecma5AndLessKeywords), 6: makePredicate(ecma5AndLessKeywor...` | ✗ |
| `nonASCIIidentifierStartChars` | `string` | let/var | `"ªµºÀ-ÖØ-öø-ˁˆ-ˑˠ-ˤˬˮͰ-ʹͶͷͺ-ͽͿΆΈ-ΊΌΎ-ΡΣ-ϵϷ-ҁҊ-ԯԱ-Ֆՙա-ևא-תװ-ײؠ-يٮٯٱ-ۓەۥۦۮۯۺ-ۼۿ...` | ✗ |
| `nonASCIIidentifierChars` | `string` | let/var | `"‌‍·̀-ͯ·҃-֑҇-ׇֽֿׁׂׅׄؐ-ًؚ-٩ٰۖ-ۜ۟-۪ۤۧۨ-ۭ۰-۹ܑܰ-݊ަ-ް߀-߉߫-߳ࠖ-࠙ࠛ-ࠣࠥ-ࠧࠩ-࡙࠭-࡛ࣤ-ःऺ-़ा-...` | ✗ |
| `nonASCIIidentifierStart` | `RegExp` | let/var | `new RegExp("[" + nonASCIIidentifierStartChars + "]")` | ✗ |
| `nonASCIIidentifier` | `RegExp` | let/var | `new RegExp("[" + nonASCIIidentifierStartChars + nonASCIIidentifierChars + "]")` | ✗ |
| `astralIdentifierStartCodes` | `number[]` | let/var | `[0, 11, 2, 25, 2, 18, 2, 1, 2, 14, 3, 13, 35, 122, 70, 52, 268, 28, 4, 48, 48...` | ✗ |
| `astralIdentifierCodes` | `number[]` | let/var | `[509, 0, 227, 0, 150, 4, 294, 9, 1368, 2, 2, 1, 6, 3, 41, 2, 5, 0, 166, 1, 13...` | ✗ |
| `pos` | `number` | let/var | `65536` | ✗ |
| `prop` | `any` | let/var | `props[key]` | ✗ |
| `Parser` | `any` | let/var | `require("./state").Parser` | ✗ |
| `lineBreakG` | `any` | let/var | `require("./whitespace").lineBreakG` | ✗ |
| `Position` | `typeof Position` | let/var | `exports.Position = (function () { function Position(line, col) { _classCallCh...` | ✗ |
| `SourceLocation` | `typeof SourceLocation` | let/var | `exports.SourceLocation = function SourceLocation(p, start, end) { _classCallC...` | ✗ |
| `pp` | `any` | let/var | `Parser.prototype` | ✗ |
| `err` | `SyntaxError` | let/var | `new SyntaxError(message)` | ✗ |
| `tt` | `any` | let/var | `require("./tokentype").types` | ✗ |
| `Parser` | `any` | let/var | `require("./state").Parser` | ✗ |
| `reservedWords` | `any` | let/var | `require("./identifier").reservedWords` | ✗ |
| `has` | `any` | let/var | `require("./util").has` | ✗ |
| `pp` | `any` | let/var | `Parser.prototype` | ✗ |
| `prop` | `any` | let/var | `node.properties[i]` | ✗ |
| `end` | `any` | let/var | `exprList.length` | ✗ |
| `last` | `any` | let/var | `exprList[end - 1]` | ✗ |
| `arg` | `any` | let/var | `last.argument` | ✗ |
| `elt` | `any` | let/var | `exprList[i]` | ✗ |
| `elts` | `any[]` | let/var | `[]` | ✗ |
| `first` | `boolean` | let/var | `true` | ✗ |
| `elem` | `any` | let/var | `expr.elements[i]` | ✗ |
| `Parser` | `any` | let/var | `require("./state").Parser` | ✗ |
| `SourceLocation` | `any` | let/var | `require("./location").SourceLocation` | ✗ |
| `pp` | `any` | let/var | `Parser.prototype` | ✗ |
| `Node` | `() => void` | let/var | `exports.Node = function Node() { _classCallCheck(this, Node); }` | ✗ |
| `node` | `any` | let/var | `new Node()` | ✗ |
| `node` | `any` | let/var | `new Node()` | ✗ |
| `start` | `any` | let/var | `pos` | ✗ |
| `has` | `any` | let/var | `_util.has` | ✗ |
| `isArray` | `any` | let/var | `_util.isArray` | ✗ |
| `SourceLocation` | `any` | let/var | `require("./location").SourceLocation` | ✗ |
| `defaultOptions` | `{ ecmaVersion: number; sourceType: st...` | let/var | `{ // `ecmaVersion` indicates the ECMAScript version to parse. Must // be eith...` | ✗ |
| `options` | `{ onComment: any; }` | let/var | `{}` | ✗ |
| `tokens` | `any` | let/var | `options.onToken` | ✗ |
| `comment` | `{ type: string; value: any; start: an...` | let/var | `{ type: block ? "Block" : "Line", value: text, start: start, end: end }` | ✗ |
| `tt` | `any` | let/var | `require("./tokentype").types` | ✗ |
| `Parser` | `any` | let/var | `require("./state").Parser` | ✗ |
| `lineBreak` | `any` | let/var | `require("./whitespace").lineBreak` | ✗ |
| `pp` | `any` | let/var | `Parser.prototype` | ✗ |
| `reservedWords` | `any` | let/var | `_identifier.reservedWords` | ✗ |
| `keywords` | `any` | let/var | `_identifier.keywords` | ✗ |
| `tt` | `any` | let/var | `_tokentype.types` | ✗ |
| `lineBreak` | `any` | let/var | `_tokentype.lineBreak` | ✗ |
| `plugins` | `{}` | let/var | `{}` | ✗ |
| `plugin` | `any` | let/var | `exports.plugins[_name]` | ✗ |
| `tt` | `any` | let/var | `require("./tokentype").types` | ✗ |
| `Parser` | `any` | let/var | `require("./state").Parser` | ✗ |
| `lineBreak` | `any` | let/var | `require("./whitespace").lineBreak` | ✗ |
| `pp` | `any` | let/var | `Parser.prototype` | ✗ |
| `first` | `boolean` | let/var | `true` | ✗ |
| `loopLabel` | `{ kind: string; }` | let/var | `{ kind: "loop" }` | ✗ |
| `switchLabel` | `{ kind: string; }` | let/var | `{ kind: "switch" }` | ✗ |
| `starttype` | `any` | let/var | `this.type` | ✗ |
| `maybeName` | `any` | let/var | `this.value` | ✗ |
| `isBreak` | `boolean` | let/var | `keyword == "break"` | ✗ |
| `lab` | `any` | let/var | `this.labels[i]` | ✗ |
| `varKind` | `any` | let/var | `this.type` | ✗ |
| `refShorthandDefaultPos` | `{ start: number; }` | let/var | `{ start: 0 }` | ✗ |
| `isCase` | `boolean` | let/var | `this.type === tt._case` | ✗ |
| `empty` | `any[]` | let/var | `[]` | ✗ |
| `kind` | `string` | let/var | `this.type.isLoop ? "loop" : this.type === tt._switch ? "switch" : null` | ✗ |
| `first` | `boolean` | let/var | `true` | ✗ |
| `oldStrict` | `any` | let/var | `undefined` | ✗ |
| `type` | `string` | let/var | `this.type === tt._in ? "ForInStatement" : "ForOfStatement"` | ✗ |
| `needsSemi` | `boolean` | let/var | `true` | ✗ |
| `nodes` | `any[]` | let/var | `[]` | ✗ |
| `first` | `boolean` | let/var | `true` | ✗ |
| `nodes` | `any[]` | let/var | `[]` | ✗ |
| `first` | `boolean` | let/var | `true` | ✗ |
| `Parser` | `any` | let/var | `require("./state").Parser` | ✗ |
| `tt` | `any` | let/var | `require("./tokentype").types` | ✗ |
| `lineBreak` | `any` | let/var | `require("./whitespace").lineBreak` | ✗ |
| `TokContext` | `typeof TokContext` | let/var | `exports.TokContext = function TokContext(token, isExpr, preserveSpace, overri...` | ✗ |
| `types` | `{ b_stat: TokContext; b_expr: TokCont...` | let/var | `{ b_stat: new TokContext("{", false), b_expr: new TokContext("{", true), b_tm...` | ✗ |
| `pp` | `any` | let/var | `Parser.prototype` | ✗ |
| `parent` | `any` | let/var | `undefined` | ✗ |
| `update` | `any` | let/var | `undefined` | ✗ |
| `type` | `any` | let/var | `this.type` | ✗ |
| `statementParens` | `boolean` | let/var | `prevType === tt._if \|\| prevType === tt._for \|\| prevType === tt._with \|\|...` | ✗ |
| `isIdentifierStart` | `any` | let/var | `_identifier.isIdentifierStart` | ✗ |
| `isIdentifierChar` | `any` | let/var | `_identifier.isIdentifierChar` | ✗ |
| `tt` | `any` | let/var | `_tokentype.types` | ✗ |
| `keywordTypes` | `any` | let/var | `_tokentype.keywords` | ✗ |
| `Parser` | `any` | let/var | `require("./state").Parser` | ✗ |
| `SourceLocation` | `any` | let/var | `require("./location").SourceLocation` | ✗ |
| `lineBreak` | `any` | let/var | `_whitespace.lineBreak` | ✗ |
| `lineBreakG` | `any` | let/var | `_whitespace.lineBreakG` | ✗ |
| `isNewLine` | `any` | let/var | `_whitespace.isNewLine` | ✗ |
| `nonASCIIwhitespace` | `any` | let/var | `_whitespace.nonASCIIwhitespace` | ✗ |
| `Token` | `typeof Token` | let/var | `exports.Token = function Token(p) { _classCallCheck(this, Token); this.type =...` | ✗ |
| `pp` | `any` | let/var | `Parser.prototype` | ✗ |
| `self` | `any` | let/var | `this` | ✗ |
| `startLoc` | `any` | let/var | `this.options.onComment && this.options.locations && this.curPosition()` | ✗ |
| `start` | `undefined` | let/var | `this.pos` | ✗ |
| `match` | `any` | let/var | `undefined` | ✗ |
| `start` | `any` | let/var | `this.pos` | ✗ |
| `startLoc` | `any` | let/var | `this.options.onComment && this.options.locations && this.curPosition()` | ✗ |
| `prevType` | `undefined` | let/var | `this.type` | ✗ |
| `size` | `number` | let/var | `1` | ✗ |
| `regexpUnicodeSupport` | `boolean` | let/var | `false` | ✗ |
| `escaped` | `any` | let/var | `undefined` | ✗ |
| `inClass` | `any` | let/var | `undefined` | ✗ |
| `start` | `any` | let/var | `this.pos` | ✗ |
| `tmp` | `any` | let/var | `content` | ✗ |
| `validFlags` | `RegExp` | let/var | `/^[gmsiy]*$/` | ✗ |
| `value` | `any` | let/var | `undefined` | ✗ |
| `start` | `any` | let/var | `this.pos` | ✗ |
| `total` | `number` | let/var | `0` | ✗ |
| `val` | `any` | let/var | `undefined` | ✗ |
| `start` | `any` | let/var | `this.pos` | ✗ |
| `isFloat` | `boolean` | let/var | `false` | ✗ |
| `octal` | `boolean` | let/var | `this.input.charCodeAt(this.pos) === 48` | ✗ |
| `val` | `any` | let/var | `undefined` | ✗ |
| `code` | `any` | let/var | `undefined` | ✗ |
| `out` | `string` | let/var | `""` | ✗ |
| `chunkStart` | `number` | let/var | `++this.pos` | ✗ |
| `out` | `string` | let/var | `""` | ✗ |
| `chunkStart` | `any` | let/var | `this.pos` | ✗ |
| `containsEsc` | `any` | let/var | `*not shown*` | ✗ |
| `word` | `string` | let/var | `""` | ✗ |
| `first` | `boolean` | let/var | `true` | ✗ |
| `chunkStart` | `any` | let/var | `this.pos` | ✗ |
| `astral` | `boolean` | let/var | `this.options.ecmaVersion >= 6` | ✗ |
| `escStart` | `any` | let/var | `this.pos` | ✗ |
| `type` | `any` | let/var | `tt.name` | ✗ |
| `conf` | `any` | let/var | `arguments[1] === undefined ? {} : arguments[1]` | ✗ |
| `TokenType` | `typeof TokenType` | let/var | `exports.TokenType = function TokenType(label) { var conf = arguments[1] === u...` | ✗ |
| `beforeExpr` | `{ beforeExpr: boolean; }` | let/var | `{ beforeExpr: true }` | ✗ |
| `startsExpr` | `{ startsExpr: boolean; }` | let/var | `{ startsExpr: true }` | ✗ |
| `types` | `{ num: TokenType; regexp: TokenType; ...` | let/var | `{ num: new TokenType("num", startsExpr), regexp: new TokenType("regexp", star...` | ✗ |
| `keywords` | `{}` | let/var | `{}` | ✗ |
| `options` | `any` | let/var | `arguments[1] === undefined ? {} : arguments[1]` | ✗ |
| `lineBreak` | `RegExp` | let/var | `/\r\n?\|\n\|\u2028\|\u2029/` | ✗ |
| `lineBreakG` | `RegExp` | let/var | `new RegExp(lineBreak.source, "g")` | ✗ |
| `nonASCIIwhitespace` | `RegExp` | let/var | `/[\u1680\u180e\u2000-\u200a\u202f\u205f\u3000\ufeff]/` | ✗ |


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

### `parse(input: any, options: any): any`

**Parameters:**

- **`input`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `parser`
- `p.curPosition`
- `p.nextToken`
- `p.parseTopLevel`
- `p.startNodeAt`

<details><summary>Code</summary>

```typescript
function parse(input, options) {
  var p = parser(options, input);
  var startPos = p.options.locations ? [p.pos, p.curPosition()] : p.pos;
  p.nextToken();
  return p.parseTopLevel(p.options.program || p.startNodeAt(startPos));
}
```
</details>

### `parseExpressionAt(input: any, pos: any, options: any): any`

**Parameters:**

- **`input`** `any`
- **`pos`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `parser`
- `p.nextToken`
- `p.parseExpression`

<details><summary>Code</summary>

```typescript
function parseExpressionAt(input, pos, options) {
  var p = parser(options, input, pos);
  p.nextToken();
  return p.parseExpression();
}
```
</details>

### `tokenizer(input: any, options: any): any`

**Parameters:**

- **`input`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `parser`

<details><summary>Code</summary>

```typescript
function tokenizer(input, options) {
  return parser(options, input);
}
```
</details>

### `parser(options: any, input: any): any`

**Parameters:**

- **`options`** `any`
- **`input`** `any`

**Returns:** `any`

**Calls:**

- `getOptions`
- `String`

<details><summary>Code</summary>

```typescript
function parser(options, input) {
  return new Parser(getOptions(options), String(input));
}
```
</details>

### `makePredicate(words: any): Function`

**Parameters:**

- **`words`** `any`

**Returns:** `Function`

**Calls:**

- `words.split`
- `cats[j].push`
- `cats.push`
- `JSON.stringify`
- `cats.sort`
- `compareTo`

**Internal Comments:**
```
// When there are more than three length categories, an outer
// switch first dispatches on the lengths, to save on comparisons.
```

<details><summary>Code</summary>

```typescript
function makePredicate(words) {
  words = words.split(" ");
  var f = "",
      cats = [];
  out: for (var i = 0; i < words.length; ++i) {
    for (var j = 0; j < cats.length; ++j) {
      if (cats[j][0].length == words[i].length) {
        cats[j].push(words[i]);
        continue out;
      }
    }cats.push([words[i]]);
  }
  function compareTo(arr) {
    if (arr.length == 1) {
      return f += "return str === " + JSON.stringify(arr[0]) + ";";
    }f += "switch(str){";
    for (var i = 0; i < arr.length; ++i) {
      f += "case " + JSON.stringify(arr[i]) + ":";
    }f += "return true}return false;";
  }

  // When there are more than three length categories, an outer
  // switch first dispatches on the lengths, to save on comparisons.

  if (cats.length > 3) {
    cats.sort(function (a, b) {
      return b.length - a.length;
    });
    f += "switch(str.length){";
    for (var i = 0; i < cats.length; ++i) {
      var cat = cats[i];
      f += "case " + cat[0].length + ":";
      compareTo(cat);
    }
    f += "}"

    // Otherwise, simply generate a flat `switch` statement.

    ;
  } else {
    compareTo(words);
  }
  return new Function("str", f);
}
```
</details>

### `compareTo(arr: any): string`

**Parameters:**

- **`arr`** `any`

**Returns:** `string`

**Calls:**

- `JSON.stringify`

<details><summary>Code</summary>

```typescript
function compareTo(arr) {
    if (arr.length == 1) {
      return f += "return str === " + JSON.stringify(arr[0]) + ";";
    }f += "switch(str){";
    for (var i = 0; i < arr.length; ++i) {
      f += "case " + JSON.stringify(arr[i]) + ":";
    }f += "return true}return false;";
  }
```
</details>

### `isInAstralSet(code: any, set: any): boolean`

**Parameters:**

- **`code`** `any`
- **`set`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isInAstralSet(code, set) {
  var pos = 65536;
  for (var i = 0; i < set.length; i += 2) {
    pos += set[i];
    if (pos > code) {
      return false;
    }pos += set[i + 1];
    if (pos >= code) {
      return true;
    }
  }
}
```
</details>

### `isIdentifierStart(code: any, astral: any): boolean`

**Parameters:**

- **`code`** `any`
- **`astral`** `any`

**Returns:** `boolean`

**Calls:**

- `nonASCIIidentifierStart.test`
- `String.fromCharCode`
- `isInAstralSet`

<details><summary>Code</summary>

```typescript
function isIdentifierStart(code, astral) {
  if (code < 65) {
    return code === 36;
  }if (code < 91) {
    return true;
  }if (code < 97) {
    return code === 95;
  }if (code < 123) {
    return true;
  }if (code <= 65535) {
    return code >= 170 && nonASCIIidentifierStart.test(String.fromCharCode(code));
  }if (astral === false) {
    return false;
  }return isInAstralSet(code, astralIdentifierStartCodes);
}
```
</details>

### `isIdentifierChar(code: any, astral: any): boolean`

**Parameters:**

- **`code`** `any`
- **`astral`** `any`

**Returns:** `boolean`

**Calls:**

- `nonASCIIidentifier.test`
- `String.fromCharCode`
- `isInAstralSet`

<details><summary>Code</summary>

```typescript
function isIdentifierChar(code, astral) {
  if (code < 48) {
    return code === 36;
  }if (code < 58) {
    return true;
  }if (code < 65) {
    return false;
  }if (code < 91) {
    return true;
  }if (code < 97) {
    return code === 95;
  }if (code < 123) {
    return true;
  }if (code <= 65535) {
    return code >= 170 && nonASCIIidentifier.test(String.fromCharCode(code));
  }if (astral === false) {
    return false;
  }return isInAstralSet(code, astralIdentifierStartCodes) || isInAstralSet(code, astralIdentifierCodes);
}
```
</details>

### `defineProperties(target: any, props: any): void`

**Parameters:**

- **`target`** `any`
- **`props`** `any`

**Returns:** `void`

**Calls:**

- `Object.defineProperties`

<details><summary>Code</summary>

```typescript
function defineProperties(target, props) { for (var key in props) { var prop = props[key]; prop.configurable = true; if (prop.value) prop.writable = true; } Object.defineProperties(target, props); }
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

### `Position(line: any, col: any): void`

**Parameters:**

- **`line`** `any`
- **`col`** `any`

**Returns:** `void`

**Calls:**

- `_classCallCheck`

<details><summary>Code</summary>

```typescript
function Position(line, col) {
    _classCallCheck(this, Position);

    this.line = line;
    this.column = col;
  }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `getLineInfo(input: any, offset: any): Position`

**Parameters:**

- **`input`** `any`
- **`offset`** `any`

**Returns:** `Position`

**Calls:**

- `lineBreakG.exec`

<details><summary>Code</summary>

```typescript
function getLineInfo(input, offset) {
  for (var line = 1, cur = 0;;) {
    lineBreakG.lastIndex = cur;
    var match = lineBreakG.exec(input);
    if (match && match.index < offset) {
      ++line;
      cur = match.index + match[0].length;
    } else {
      return new Position(line, offset - cur);
    }
  }
}
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

### `getOptions(opts: any): { onComment: any; }`

**Parameters:**

- **`opts`** `any`

**Returns:** `{ onComment: any; }`

**Calls:**

- `has`
- `isArray`
- `complex_call_50806`
- `tokens.push`
- `pushComment`

<details><summary>Code</summary>

```typescript
function getOptions(opts) {
  var options = {};
  for (var opt in defaultOptions) {
    options[opt] = opts && has(opts, opt) ? opts[opt] : defaultOptions[opt];
  }if (isArray(options.onToken)) {
    (function () {
      var tokens = options.onToken;
      options.onToken = function (token) {
        return tokens.push(token);
      };
    })();
  }
  if (isArray(options.onComment)) options.onComment = pushComment(options, options.onComment);

  return options;
}
```
</details>

### `pushComment(options: any, array: any): (block: any, text: any, start: any, end: any, startLoc: any, endLoc: any) => void`

**Parameters:**

- **`options`** `any`
- **`array`** `any`

**Returns:** `(block: any, text: any, start: any, end: any, startLoc: any, endLoc: any) => void`

**Calls:**

- `array.push`

<details><summary>Code</summary>

```typescript
function pushComment(options, array) {
  return function (block, text, start, end, startLoc, endLoc) {
    var comment = {
      type: block ? "Block" : "Line",
      value: text,
      start: start,
      end: end
    };
    if (options.locations) comment.loc = new SourceLocation(this, startLoc, endLoc);
    if (options.ranges) comment.range = [start, end];
    array.push(comment);
  };
}
```
</details>

### `Parser(options: any, input: any, startPos: any): void`

**Parameters:**

- **`options`** `any`
- **`input`** `any`
- **`startPos`** `any`

**Returns:** `void`

**Calls:**

- `this.loadPlugins`
- `Math.max`
- `this.input.lastIndexOf`
- `this.input.slice(0, this.lineStart).split`
- `this.initialContext`
- `this.input.slice`
- `this.skipLineComment`

**Internal Comments:**
```
// Set up token state
// The current position of the tokenizer in the input.
// Properties of the current token: (x4)
// Its type (x4)
// For tokens that include more information than their type, the value (x4)
// Its start and end offset (x4)
// And, if locations are used, the {line, column} object (x4)
// corresponding to those offsets (x4)
// Position information for the previous token (x4)
// The context stack is used to superficially track syntactic (x4)
// context to predict whether a regular expression is allowed in a (x4)
// given position. (x4)
// Figure out if it's a module code. (x4)
// Flags to track whether we are in a function, a generator. (x4)
// Labels in scope. (x4)
// If enabled, skip leading hashbang line.
```

<details><summary>Code</summary>

```typescript
function Parser(options, input, startPos) {
  this.options = options;
  this.loadPlugins(this.options.plugins);
  this.sourceFile = this.options.sourceFile || null;
  this.isKeyword = keywords[this.options.ecmaVersion >= 6 ? 6 : 5];
  this.isReservedWord = reservedWords[this.options.ecmaVersion];
  this.input = input;

  // Set up token state

  // The current position of the tokenizer in the input.
  if (startPos) {
    this.pos = startPos;
    this.lineStart = Math.max(0, this.input.lastIndexOf("\n", startPos));
    this.curLine = this.input.slice(0, this.lineStart).split(lineBreak).length;
  } else {
    this.pos = this.lineStart = 0;
    this.curLine = 1;
  }

  // Properties of the current token:
  // Its type
  this.type = tt.eof;
  // For tokens that include more information than their type, the value
  this.value = null;
  // Its start and end offset
  this.start = this.end = this.pos;
  // And, if locations are used, the {line, column} object
  // corresponding to those offsets
  this.startLoc = this.endLoc = null;

  // Position information for the previous token
  this.lastTokEndLoc = this.lastTokStartLoc = null;
  this.lastTokStart = this.lastTokEnd = this.pos;

  // The context stack is used to superficially track syntactic
  // context to predict whether a regular expression is allowed in a
  // given position.
  this.context = this.initialContext();
  this.exprAllowed = true;

  // Figure out if it's a module code.
  this.strict = this.inModule = this.options.sourceType === "module";

  // Flags to track whether we are in a function, a generator.
  this.inFunction = this.inGenerator = false;
  // Labels in scope.
  this.labels = [];

  // If enabled, skip leading hashbang line.
  if (this.pos === 0 && this.options.allowHashBang && this.input.slice(0, 2) === "#!") this.skipLineComment(2);
}
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

### `next(): { done: boolean; value: any; }`

**Returns:** `{ done: boolean; value: any; }`

**Calls:**

- `self.getToken`

<details><summary>Code</summary>

```typescript
function next() {
      var token = self.getToken();
      return {
        done: token.type === tt.eof,
        value: token
      };
    }
```
</details>

### `next(): { done: boolean; value: any; }`

**Returns:** `{ done: boolean; value: any; }`

**Calls:**

- `self.getToken`

<details><summary>Code</summary>

```typescript
function next() {
      var token = self.getToken();
      return {
        done: token.type === tt.eof,
        value: token
      };
    }
```
</details>

### `codePointToString(code: any): string`

**Parameters:**

- **`code`** `any`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`

**Internal Comments:**
```
// UTF-16 Decoding
```

<details><summary>Code</summary>

```typescript
function codePointToString(code) {
  // UTF-16 Decoding
  if (code <= 65535) {
    return String.fromCharCode(code);
  }return String.fromCharCode((code - 65536 >> 10) + 55296, (code - 65536 & 1023) + 56320);
}
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

### `binop(name: any, prec: any): TokenType`

**Parameters:**

- **`name`** `any`
- **`prec`** `any`

**Returns:** `TokenType`

<details><summary>Code</summary>

```typescript
function binop(name, prec) {
  return new TokenType(name, { beforeExpr: true, binop: prec });
}
```
</details>

### `kw(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function kw(name) {
  var options = arguments[1] === undefined ? {} : arguments[1];

  options.keyword = name;
  keywords[name] = types["_" + name] = new TokenType(name, options);
}
```
</details>

### `isArray(obj: any): boolean`

**Parameters:**

- **`obj`** `any`

**Returns:** `boolean`

**Calls:**

- `Object.prototype.toString.call`

<details><summary>Code</summary>

```typescript
function isArray(obj) {
  return Object.prototype.toString.call(obj) === "[object Array]";
}
```
</details>

### `has(obj: any, propName: any): any`

**Parameters:**

- **`obj`** `any`
- **`propName`** `any`

**Returns:** `any`

**Calls:**

- `Object.prototype.hasOwnProperty.call`

<details><summary>Code</summary>

```typescript
function has(obj, propName) {
  return Object.prototype.hasOwnProperty.call(obj, propName);
}
```
</details>

### `isNewLine(code: any): boolean`

**Parameters:**

- **`code`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isNewLine(code) {
  return code === 10 || code === 13 || code === 8232 || code == 8233;
}
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `value(n: any): Position`

**Parameters:**

- **`n`** `any`

**Returns:** `Position`

<details><summary>Code</summary>

```typescript
function offset(n) {
        return new Position(this.line, this.column + n);
      }
```
</details>

### `next(): { done: boolean; value: any; }`

**Returns:** `{ done: boolean; value: any; }`

**Calls:**

- `self.getToken`

<details><summary>Code</summary>

```typescript
function next() {
      var token = self.getToken();
      return {
        done: token.type === tt.eof,
        value: token
      };
    }
```
</details>

### `next(): { done: boolean; value: any; }`

**Returns:** `{ done: boolean; value: any; }`

**Calls:**

- `self.getToken`

<details><summary>Code</summary>

```typescript
function next() {
      var token = self.getToken();
      return {
        done: token.type === tt.eof,
        value: token
      };
    }
```
</details>


---