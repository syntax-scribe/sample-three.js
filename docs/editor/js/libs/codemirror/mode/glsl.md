[⬅️ Back to Table of Contents](../../../../../index.md)

# 📄 `glsl.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 📊 Variables & Constants | 22 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/codemirror/mode/glsl.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indentUnit` | `any` | let/var | `config.indentUnit` | ✗ |
| `keywords` | `any` | let/var | `parserConfig.keywords \|\| words(glslKeywords)` | ✗ |
| `builtins` | `any` | let/var | `parserConfig.builtins \|\| words(glslBuiltins)` | ✗ |
| `blockKeywords` | `any` | let/var | `parserConfig.blockKeywords \|\| words("case do else for if switch while struct")` | ✗ |
| `atoms` | `any` | let/var | `parserConfig.atoms \|\| words("null")` | ✗ |
| `hooks` | `any` | let/var | `parserConfig.hooks \|\| {}` | ✗ |
| `multiLineStrings` | `any` | let/var | `parserConfig.multiLineStrings` | ✗ |
| `isOperatorChar` | `RegExp` | let/var | `/[+\-*&%=<>!?\|\/]/` | ✗ |
| `curPunc` | `any` | let/var | `*not shown*` | ✗ |
| `escaped` | `boolean` | let/var | `false` | ✗ |
| `next` | `any` | let/var | `*not shown*` | ✗ |
| `end` | `boolean` | let/var | `false` | ✗ |
| `maybeEnd` | `boolean` | let/var | `false` | ✗ |
| `ch` | `any` | let/var | `*not shown*` | ✗ |
| `t` | `any` | let/var | `state.context.type` | ✗ |
| `ctx` | `any` | let/var | `state.context` | ✗ |
| `firstChar` | `any` | let/var | `textAfter && textAfter.charAt(0)` | ✗ |
| `ctx` | `any` | let/var | `state.context` | ✗ |
| `closing` | `boolean` | let/var | `firstChar == ctx.type` | ✗ |
| `obj` | `{}` | let/var | `{}` | ✗ |
| `glslKeywords` | `string` | let/var | `"attribute const uniform varying break continue " + "do for while if else in ...` | ✗ |
| `glslBuiltins` | `string` | let/var | `"radians degrees sin cos tan asin acos atan pow " + "exp log exp2 log2 sqrt i...` | ✗ |


---

## Functions

### `tokenBase(stream: any, state: any): any`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `stream.next`
- `complex_call_2328`
- `tokenString`
- `state.tokenize`
- `/[\[\]{}\(\),;\:\.]/.test`
- `/\d/.test`
- `stream.eatWhile`
- `stream.eat`
- `tokenComment`
- `stream.skipToEnd`
- `isOperatorChar.test`
- `stream.current`
- `keywords.propertyIsEnumerable`
- `blockKeywords.propertyIsEnumerable`
- `builtins.propertyIsEnumerable`
- `atoms.propertyIsEnumerable`

<details><summary>Code</summary>

```typescript
function tokenBase(stream, state) {
      var ch = stream.next();
      if (hooks[ch]) {
        var result = hooks[ch](stream, state);
        if (result !== false) return result;
      }
      if (ch == '"' || ch == "'") {
        state.tokenize = tokenString(ch);
        return state.tokenize(stream, state);
      }
      if (/[\[\]{}\(\),;\:\.]/.test(ch)) {
        curPunc = ch;
        return "bracket";
      }
      if (/\d/.test(ch)) {
        stream.eatWhile(/[\w\.]/);
        return "number";
      }
      if (ch == "/") {
        if (stream.eat("*")) {
          state.tokenize = tokenComment;
          return tokenComment(stream, state);
        }
        if (stream.eat("/")) {
          stream.skipToEnd();
          return "comment";
        }
      }
      if (ch == "#") {
        stream.eatWhile(/[\S]+/);
        stream.eatWhile(/[\s]+/);
        stream.eatWhile(/[\S]+/);
        stream.eatWhile(/[\s]+/);
        return "comment";
      }
      if (isOperatorChar.test(ch)) {
        stream.eatWhile(isOperatorChar);
        return "operator";
      }
      stream.eatWhile(/[\w\$_]/);
      var cur = stream.current();
      if (keywords.propertyIsEnumerable(cur)) {
        if (blockKeywords.propertyIsEnumerable(cur)) curPunc = "newstatement";
        return "keyword";
      }
      if (builtins.propertyIsEnumerable(cur)) {
        return "builtin";
      }
      if (atoms.propertyIsEnumerable(cur)) return "atom";
      return "word";
    }
```
</details>

### `tokenString(quote: any): (stream: any, state: any) => string`

**Parameters:**

- **`quote`** `any`

**Returns:** `(stream: any, state: any) => string`

**Calls:**

- `stream.next`

<details><summary>Code</summary>

```typescript
function tokenString(quote) {
      return function(stream, state) {
        var escaped = false, next, end = false;
        while ((next = stream.next()) != null) {
          if (next == quote && !escaped) {end = true; break;}
          escaped = !escaped && next == "\\";
        }
        if (end || !(escaped || multiLineStrings))
          state.tokenize = tokenBase;
        return "string";
      };
    }
```
</details>

### `tokenComment(stream: any, state: any): string`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`

**Returns:** `string`

**Calls:**

- `stream.next`

<details><summary>Code</summary>

```typescript
function tokenComment(stream, state) {
      var maybeEnd = false, ch;
      while (ch = stream.next()) {
        if (ch == "/" && maybeEnd) {
          state.tokenize = tokenBase;
          break;
        }
        maybeEnd = (ch == "*");
      }
      return "comment";
    }
```
</details>

### `Context(indented: any, column: any, type: any, align: any, prev: any): void`

**Parameters:**

- **`indented`** `any`
- **`column`** `any`
- **`type`** `any`
- **`align`** `any`
- **`prev`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Context(indented, column, type, align, prev) {
      this.indented = indented;
      this.column = column;
      this.type = type;
      this.align = align;
      this.prev = prev;
    }
```
</details>

### `pushContext(state: any, col: any, type: any): Context`

**Parameters:**

- **`state`** `any`
- **`col`** `any`
- **`type`** `any`

**Returns:** `Context`

<details><summary>Code</summary>

```typescript
function pushContext(state, col, type) {
      return state.context = new Context(state.indented, col, type, null, state.context);
    }
```
</details>

### `popContext(state: any): any`

**Parameters:**

- **`state`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function popContext(state) {
      var t = state.context.type;
      if (t == ")" || t == "]" || t == "}")
        state.indented = state.context.indented;
      return state.context = state.context.prev;
    }
```
</details>

### `startState(basecolumn: any): { tokenize: any; context: Context; indented: number; startOfLine: boolean; }`

**Parameters:**

- **`basecolumn`** `any`

**Returns:** `{ tokenize: any; context: Context; indented: number; startOfLine: boolean; }`

<details><summary>Code</summary>

```typescript
function(basecolumn) {
        return {
          tokenize: null,
          context: new Context((basecolumn || 0) - indentUnit, 0, "top", false),
          indented: 0,
          startOfLine: true
        };
      }
```
</details>

### `token(stream: any, state: any): any`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `stream.sol`
- `stream.indentation`
- `stream.eatSpace`
- `complex_call_5555`
- `popContext`
- `pushContext`
- `stream.column`

<details><summary>Code</summary>

```typescript
function(stream, state) {
        var ctx = state.context;
        if (stream.sol()) {
          if (ctx.align == null) ctx.align = false;
          state.indented = stream.indentation();
          state.startOfLine = true;
        }
        if (stream.eatSpace()) return null;
        curPunc = null;
        var style = (state.tokenize || tokenBase)(stream, state);
        if (style == "comment" || style == "meta") return style;
        if (ctx.align == null) ctx.align = true;

        if ((curPunc == ";" || curPunc == ":") && ctx.type == "statement") popContext(state);
        else if (curPunc == "{") pushContext(state, stream.column(), "}");
        else if (curPunc == "[") pushContext(state, stream.column(), "]");
        else if (curPunc == "(") pushContext(state, stream.column(), ")");
        else if (curPunc == "}") {
          while (ctx.type == "statement") ctx = popContext(state);
          if (ctx.type == "}") ctx = popContext(state);
          while (ctx.type == "statement") ctx = popContext(state);
        }
        else if (curPunc == ctx.type) popContext(state);
        else if (ctx.type == "}" || ctx.type == "top" || (ctx.type == "statement" && curPunc == "newstatement"))
          pushContext(state, stream.column(), "statement");
        state.startOfLine = false;
        return style;
      }
```
</details>

### `indent(state: any, textAfter: any): any`

**Parameters:**

- **`state`** `any`
- **`textAfter`** `any`

**Returns:** `any`

**Calls:**

- `textAfter.charAt`

<details><summary>Code</summary>

```typescript
function(state, textAfter) {
        if (state.tokenize != tokenBase && state.tokenize != null) return 0;
        var firstChar = textAfter && textAfter.charAt(0), ctx = state.context, closing = firstChar == ctx.type;
        if (ctx.type == "statement") return ctx.indented + (firstChar == "{" ? 0 : indentUnit);
        else if (ctx.align) return ctx.column + (closing ? 0 : 1);
        else return ctx.indented + (closing ? 0 : indentUnit);
      }
```
</details>

### `startState(basecolumn: any): { tokenize: any; context: Context; indented: number; startOfLine: boolean; }`

**Parameters:**

- **`basecolumn`** `any`

**Returns:** `{ tokenize: any; context: Context; indented: number; startOfLine: boolean; }`

<details><summary>Code</summary>

```typescript
function(basecolumn) {
        return {
          tokenize: null,
          context: new Context((basecolumn || 0) - indentUnit, 0, "top", false),
          indented: 0,
          startOfLine: true
        };
      }
```
</details>

### `token(stream: any, state: any): any`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `stream.sol`
- `stream.indentation`
- `stream.eatSpace`
- `complex_call_5555`
- `popContext`
- `pushContext`
- `stream.column`

<details><summary>Code</summary>

```typescript
function(stream, state) {
        var ctx = state.context;
        if (stream.sol()) {
          if (ctx.align == null) ctx.align = false;
          state.indented = stream.indentation();
          state.startOfLine = true;
        }
        if (stream.eatSpace()) return null;
        curPunc = null;
        var style = (state.tokenize || tokenBase)(stream, state);
        if (style == "comment" || style == "meta") return style;
        if (ctx.align == null) ctx.align = true;

        if ((curPunc == ";" || curPunc == ":") && ctx.type == "statement") popContext(state);
        else if (curPunc == "{") pushContext(state, stream.column(), "}");
        else if (curPunc == "[") pushContext(state, stream.column(), "]");
        else if (curPunc == "(") pushContext(state, stream.column(), ")");
        else if (curPunc == "}") {
          while (ctx.type == "statement") ctx = popContext(state);
          if (ctx.type == "}") ctx = popContext(state);
          while (ctx.type == "statement") ctx = popContext(state);
        }
        else if (curPunc == ctx.type) popContext(state);
        else if (ctx.type == "}" || ctx.type == "top" || (ctx.type == "statement" && curPunc == "newstatement"))
          pushContext(state, stream.column(), "statement");
        state.startOfLine = false;
        return style;
      }
```
</details>

### `indent(state: any, textAfter: any): any`

**Parameters:**

- **`state`** `any`
- **`textAfter`** `any`

**Returns:** `any`

**Calls:**

- `textAfter.charAt`

<details><summary>Code</summary>

```typescript
function(state, textAfter) {
        if (state.tokenize != tokenBase && state.tokenize != null) return 0;
        var firstChar = textAfter && textAfter.charAt(0), ctx = state.context, closing = firstChar == ctx.type;
        if (ctx.type == "statement") return ctx.indented + (firstChar == "{" ? 0 : indentUnit);
        else if (ctx.align) return ctx.column + (closing ? 0 : 1);
        else return ctx.indented + (closing ? 0 : indentUnit);
      }
```
</details>

### `words(str: any): {}`

**Parameters:**

- **`str`** `any`

**Returns:** `{}`

**Calls:**

- `str.split`

<details><summary>Code</summary>

```typescript
function words(str) {
    var obj = {}, words = str.split(" ");
    for (var i = 0; i < words.length; ++i) obj[words[i]] = true;
    return obj;
  }
```
</details>

### `cppHook(stream: any, state: any): false | "meta"`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`

**Returns:** `false | "meta"`

**Calls:**

- `stream.skipToEnd`

<details><summary>Code</summary>

```typescript
function cppHook(stream, state) {
    if (!state.startOfLine) return false;
    stream.skipToEnd();
    return "meta";
  }
```
</details>


---