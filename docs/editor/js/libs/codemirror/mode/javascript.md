[⬅️ Back to Table of Contents](../../../../../index.md)

# 📄 `javascript.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 106 |
| 📊 Variables & Constants | 49 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/codemirror/mode/javascript.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indentUnit` | `any` | let/var | `config.indentUnit` | ✗ |
| `statementIndent` | `any` | let/var | `parserConfig.statementIndent` | ✗ |
| `jsonldMode` | `any` | let/var | `parserConfig.jsonld` | ✗ |
| `jsonMode` | `any` | let/var | `parserConfig.json \|\| jsonldMode` | ✗ |
| `trackScope` | `boolean` | let/var | `parserConfig.trackScope !== false` | ✗ |
| `isTS` | `any` | let/var | `parserConfig.typescript` | ✗ |
| `wordRE` | `any` | let/var | `parserConfig.wordCharacters \|\| /[\w$\xa1-\uffff]/` | ✗ |
| `atom` | `{ type: string; style: string; }` | let/var | `{type: "atom", style: "atom"}` | ✗ |
| `isOperatorChar` | `RegExp` | let/var | `/[+\-*&%=<>!?\|~^@]/` | ✗ |
| `isJsonldKeyword` | `RegExp` | let/var | `/^@(context\|id\|value\|language\|type\|container\|list\|set\|reverse\|index\...` | ✗ |
| `escaped` | `boolean` | let/var | `false` | ✗ |
| `next` | `any` | let/var | `*not shown*` | ✗ |
| `inSet` | `boolean` | let/var | `false` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `content` | `any` | let/var | `*not shown*` | ✗ |
| `kw` | `any` | let/var | `keywords[word]` | ✗ |
| `escaped` | `boolean` | let/var | `false` | ✗ |
| `next` | `any` | let/var | `*not shown*` | ✗ |
| `maybeEnd` | `boolean` | let/var | `false` | ✗ |
| `ch` | `any` | let/var | `*not shown*` | ✗ |
| `escaped` | `boolean` | let/var | `false` | ✗ |
| `next` | `any` | let/var | `*not shown*` | ✗ |
| `brackets` | `string` | let/var | `"([{}])"` | ✗ |
| `depth` | `number` | let/var | `0` | ✗ |
| `sawSomething` | `boolean` | let/var | `false` | ✗ |
| `atomicTypes` | `{ atom: boolean; number: boolean; var...` | let/var | `{"atom": true, "number": true, "variable": true, "string": true, "regexp": tr...` | ✗ |
| `cc` | `any` | let/var | `state.cc` | ✗ |
| `combinator` | `any` | let/var | `cc.length ? cc.pop() : jsonMode ? expression : statement` | ✗ |
| `cx` | `{ state: any; column: any; marked: an...` | let/var | `{state: null, column: null, marked: null, cc: null}` | ✗ |
| `state` | `any` | let/var | `cx.state` | ✗ |
| `defaultVars` | `Var` | let/var | `new Var("this", new Var("arguments", null))` | ✗ |
| `state` | `any` | let/var | `cx.state` | ✗ |
| `indent` | `any` | let/var | `state.indented` | ✗ |
| `state` | `any` | let/var | `cx.state` | ✗ |
| `body` | `(type: any) => void` | let/var | `noComma ? arrowBodyNoComma : arrowBody` | ✗ |
| `maybeop` | `any` | let/var | `noComma ? maybeoperatorNoComma : maybeoperatorComma` | ✗ |
| `me` | `any` | let/var | `noComma == false ? maybeoperatorComma : maybeoperatorNoComma` | ✗ |
| `expr` | `any` | let/var | `noComma == false ? expression : expressionNoComma` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `lex` | `any` | let/var | `cx.state.lexical` | ✗ |
| `context` | `any` | let/var | `cx.state.lexical.prev` | ✗ |
| `isInterface` | `boolean` | let/var | `context && context.info == "interface"` | ✗ |
| `state` | `{ tokenize: (stream: any, state: any)...` | let/var | `{ tokenize: tokenBase, lastType: "sof", cc: [], lexical: new JSLexical((basec...` | ✗ |
| `firstChar` | `any` | let/var | `textAfter && textAfter.charAt(0)` | ✗ |
| `lexical` | `any` | let/var | `state.lexical` | ✗ |
| `top` | `any` | let/var | `*not shown*` | ✗ |
| `c` | `any` | let/var | `state.cc[i]` | ✗ |
| `type` | `any` | let/var | `lexical.type` | ✗ |
| `closing` | `boolean` | let/var | `firstChar == type` | ✗ |


---

## Functions

### `kw(type: any): { type: any; style: string; }`

**Parameters:**

- **`type`** `any`

**Returns:** `{ type: any; style: string; }`

<details><summary>Code</summary>

```typescript
function kw(type) {return {type: type, style: "keyword"};}
```
</details>

### `readRegexp(stream: any): void`

**Parameters:**

- **`stream`** `any`

**Returns:** `void`

**Calls:**

- `stream.next`

<details><summary>Code</summary>

```typescript
function readRegexp(stream) {
    var escaped = false, next, inSet = false;
    while ((next = stream.next()) != null) {
      if (!escaped) {
        if (next == "/" && !inSet) return;
        if (next == "[") inSet = true;
        else if (inSet && next == "]") inSet = false;
      }
      escaped = !escaped && next == "\\";
    }
  }
```
</details>

### `ret(tp: any, style: any, cont: any): any`

**Parameters:**

- **`tp`** `any`
- **`style`** `any`
- **`cont`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ret(tp, style, cont) {
    type = tp; content = cont;
    return style;
  }
```
</details>

### `tokenBase(stream: any, state: any): any`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `stream.next`
- `tokenString`
- `state.tokenize`
- `stream.match`
- `ret`
- `/[\[\]{}\(\),;\:\.]/.test`
- `stream.eat`
- `/\d/.test`
- `tokenComment`
- `stream.skipToEnd`
- `expressionAllowed`
- `readRegexp`
- `stream.current`
- `tokenQuasi`
- `stream.peek`
- `stream.eatWhile`
- `/\S/.test`
- `stream.string.slice`
- `isOperatorChar.test`
- `/[<>*+\-|&?]/.test`
- `wordRE.test`
- `keywords.propertyIsEnumerable`

<details><summary>Code</summary>

```typescript
function tokenBase(stream, state) {
    var ch = stream.next();
    if (ch == '"' || ch == "'") {
      state.tokenize = tokenString(ch);
      return state.tokenize(stream, state);
    } else if (ch == "." && stream.match(/^\d[\d_]*(?:[eE][+\-]?[\d_]+)?/)) {
      return ret("number", "number");
    } else if (ch == "." && stream.match("..")) {
      return ret("spread", "meta");
    } else if (/[\[\]{}\(\),;\:\.]/.test(ch)) {
      return ret(ch);
    } else if (ch == "=" && stream.eat(">")) {
      return ret("=>", "operator");
    } else if (ch == "0" && stream.match(/^(?:x[\dA-Fa-f_]+|o[0-7_]+|b[01_]+)n?/)) {
      return ret("number", "number");
    } else if (/\d/.test(ch)) {
      stream.match(/^[\d_]*(?:n|(?:\.[\d_]*)?(?:[eE][+\-]?[\d_]+)?)?/);
      return ret("number", "number");
    } else if (ch == "/") {
      if (stream.eat("*")) {
        state.tokenize = tokenComment;
        return tokenComment(stream, state);
      } else if (stream.eat("/")) {
        stream.skipToEnd();
        return ret("comment", "comment");
      } else if (expressionAllowed(stream, state, 1)) {
        readRegexp(stream);
        stream.match(/^\b(([gimyus])(?![gimyus]*\2))+\b/);
        return ret("regexp", "string-2");
      } else {
        stream.eat("=");
        return ret("operator", "operator", stream.current());
      }
    } else if (ch == "`") {
      state.tokenize = tokenQuasi;
      return tokenQuasi(stream, state);
    } else if (ch == "#" && stream.peek() == "!") {
      stream.skipToEnd();
      return ret("meta", "meta");
    } else if (ch == "#" && stream.eatWhile(wordRE)) {
      return ret("variable", "property")
    } else if (ch == "<" && stream.match("!--") ||
               (ch == "-" && stream.match("->") && !/\S/.test(stream.string.slice(0, stream.start)))) {
      stream.skipToEnd()
      return ret("comment", "comment")
    } else if (isOperatorChar.test(ch)) {
      if (ch != ">" || !state.lexical || state.lexical.type != ">") {
        if (stream.eat("=")) {
          if (ch == "!" || ch == "=") stream.eat("=")
        } else if (/[<>*+\-|&?]/.test(ch)) {
          stream.eat(ch)
          if (ch == ">") stream.eat(ch)
        }
      }
      if (ch == "?" && stream.eat(".")) return ret(".")
      return ret("operator", "operator", stream.current());
    } else if (wordRE.test(ch)) {
      stream.eatWhile(wordRE);
      var word = stream.current()
      if (state.lastType != ".") {
        if (keywords.propertyIsEnumerable(word)) {
          var kw = keywords[word]
          return ret(kw.type, kw.style, word)
        }
        if (word == "async" && stream.match(/^(\s|\/\*([^*]|\*(?!\/))*?\*\/)*[\[\(\w]/, false))
          return ret("async", "keyword", word)
      }
      return ret("variable", "variable", word)
    }
  }
```
</details>

### `tokenString(quote: any): (stream: any, state: any) => any`

**Parameters:**

- **`quote`** `any`

**Returns:** `(stream: any, state: any) => any`

**Calls:**

- `stream.peek`
- `stream.match`
- `ret`
- `stream.next`

<details><summary>Code</summary>

```typescript
function tokenString(quote) {
    return function(stream, state) {
      var escaped = false, next;
      if (jsonldMode && stream.peek() == "@" && stream.match(isJsonldKeyword)){
        state.tokenize = tokenBase;
        return ret("jsonld-keyword", "meta");
      }
      while ((next = stream.next()) != null) {
        if (next == quote && !escaped) break;
        escaped = !escaped && next == "\\";
      }
      if (!escaped) state.tokenize = tokenBase;
      return ret("string", "string");
    };
  }
```
</details>

### `tokenComment(stream: any, state: any): any`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `stream.next`
- `ret`

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
    return ret("comment", "comment");
  }
```
</details>

### `tokenQuasi(stream: any, state: any): any`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`

**Returns:** `any`

**Calls:**

- `stream.next`
- `stream.eat`
- `ret`
- `stream.current`

<details><summary>Code</summary>

```typescript
function tokenQuasi(stream, state) {
    var escaped = false, next;
    while ((next = stream.next()) != null) {
      if (!escaped && (next == "`" || next == "$" && stream.eat("{"))) {
        state.tokenize = tokenBase;
        break;
      }
      escaped = !escaped && next == "\\";
    }
    return ret("quasi", "string-2", stream.current());
  }
```
</details>

### `findFatArrow(stream: any, state: any): void`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`

**Returns:** `void`

**Calls:**

- `stream.string.indexOf`
- `/:\s*(?:\w+(?:<[^>]*>|\[\])?|\{[^}]*\})\s*$/.exec`
- `stream.string.slice`
- `stream.string.charAt`
- `brackets.indexOf`
- `wordRE.test`
- `/["'\/`]/.test`

<details><summary>Code</summary>

```typescript
function findFatArrow(stream, state) {
    if (state.fatArrowAt) state.fatArrowAt = null;
    var arrow = stream.string.indexOf("=>", stream.start);
    if (arrow < 0) return;

    if (isTS) { // Try to skip TypeScript return type declarations after the arguments
      var m = /:\s*(?:\w+(?:<[^>]*>|\[\])?|\{[^}]*\})\s*$/.exec(stream.string.slice(stream.start, arrow))
      if (m) arrow = m.index
    }

    var depth = 0, sawSomething = false;
    for (var pos = arrow - 1; pos >= 0; --pos) {
      var ch = stream.string.charAt(pos);
      var bracket = brackets.indexOf(ch);
      if (bracket >= 0 && bracket < 3) {
        if (!depth) { ++pos; break; }
        if (--depth == 0) { if (ch == "(") sawSomething = true; break; }
      } else if (bracket >= 3 && bracket < 6) {
        ++depth;
      } else if (wordRE.test(ch)) {
        sawSomething = true;
      } else if (/["'\/`]/.test(ch)) {
        for (;; --pos) {
          if (pos == 0) return
          var next = stream.string.charAt(pos - 1)
          if (next == ch && stream.string.charAt(pos - 2) != "\\") { pos--; break }
        }
      } else if (sawSomething && !depth) {
        ++pos;
        break;
      }
    }
    if (sawSomething && !depth) state.fatArrowAt = pos;
  }
```
</details>

### `JSLexical(indented: any, column: any, type: any, align: any, prev: any, info: any): void`

**Parameters:**

- **`indented`** `any`
- **`column`** `any`
- **`type`** `any`
- **`align`** `any`
- **`prev`** `any`
- **`info`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function JSLexical(indented, column, type, align, prev, info) {
    this.indented = indented;
    this.column = column;
    this.type = type;
    this.prev = prev;
    this.info = info;
    if (align != null) this.align = align;
  }
```
</details>

### `inScope(state: any, varname: any): boolean`

**Parameters:**

- **`state`** `any`
- **`varname`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function inScope(state, varname) {
    if (!trackScope) return false
    for (var v = state.localVars; v; v = v.next)
      if (v.name == varname) return true;
    for (var cx = state.context; cx; cx = cx.prev) {
      for (var v = cx.vars; v; v = v.next)
        if (v.name == varname) return true;
    }
  }
```
</details>

### `parseJS(state: any, style: any, type: any, content: any, stream: any): any`

**Parameters:**

- **`state`** `any`
- **`style`** `any`
- **`type`** `any`
- **`content`** `any`
- **`stream`** `any`

**Returns:** `any`

**Calls:**

- `state.lexical.hasOwnProperty`
- `cc.pop`
- `combinator`
- `complex_call_9599`
- `inScope`

**Internal Comments:**
```
// Communicate our context to the combinators. (x4)
// (Less wasteful than consing up a hundred closures on every call.) (x4)
```

<details><summary>Code</summary>

```typescript
function parseJS(state, style, type, content, stream) {
    var cc = state.cc;
    // Communicate our context to the combinators.
    // (Less wasteful than consing up a hundred closures on every call.)
    cx.state = state; cx.stream = stream; cx.marked = null, cx.cc = cc; cx.style = style;

    if (!state.lexical.hasOwnProperty("align"))
      state.lexical.align = true;

    while(true) {
      var combinator = cc.length ? cc.pop() : jsonMode ? expression : statement;
      if (combinator(type, content)) {
        while(cc.length && cc[cc.length - 1].lex)
          cc.pop()();
        if (cx.marked) return cx.marked;
        if (type == "variable" && inScope(state, content)) return "variable-2";
        return style;
      }
    }
  }
```
</details>

### `pass(): void`

**Returns:** `void`

**Calls:**

- `cx.cc.push`

<details><summary>Code</summary>

```typescript
function pass() {
    for (var i = arguments.length - 1; i >= 0; i--) cx.cc.push(arguments[i]);
  }
```
</details>

### `cont(): boolean`

**Returns:** `boolean`

**Calls:**

- `pass.apply`

<details><summary>Code</summary>

```typescript
function cont() {
    pass.apply(null, arguments);
    return true;
  }
```
</details>

### `inList(name: any, list: any): boolean`

**Parameters:**

- **`name`** `any`
- **`list`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function inList(name, list) {
    for (var v = list; v; v = v.next) if (v.name == name) return true
    return false;
  }
```
</details>

### `register(varname: any): void`

**Parameters:**

- **`varname`** `any`

**Returns:** `void`

**Calls:**

- `registerVarScoped`
- `inList`

**Internal Comments:**
```
// FIXME function decls are also not block scoped (x2)
// Fall through means this is global
```

<details><summary>Code</summary>

```typescript
function register(varname) {
    var state = cx.state;
    cx.marked = "def";
    if (!trackScope) return
    if (state.context) {
      if (state.lexical.info == "var" && state.context && state.context.block) {
        // FIXME function decls are also not block scoped
        var newContext = registerVarScoped(varname, state.context)
        if (newContext != null) {
          state.context = newContext
          return
        }
      } else if (!inList(varname, state.localVars)) {
        state.localVars = new Var(varname, state.localVars)
        return
      }
    }
    // Fall through means this is global
    if (parserConfig.globalVars && !inList(varname, state.globalVars))
      state.globalVars = new Var(varname, state.globalVars)
  }
```
</details>

### `registerVarScoped(varname: any, context: any): any`

**Parameters:**

- **`varname`** `any`
- **`context`** `any`

**Returns:** `any`

**Calls:**

- `registerVarScoped`
- `inList`

<details><summary>Code</summary>

```typescript
function registerVarScoped(varname, context) {
    if (!context) {
      return null
    } else if (context.block) {
      var inner = registerVarScoped(varname, context.prev)
      if (!inner) return null
      if (inner == context.prev) return context
      return new Context(inner, context.vars, true)
    } else if (inList(varname, context.vars)) {
      return context
    } else {
      return new Context(context.prev, new Var(varname, context.vars), false)
    }
  }
```
</details>

### `isModifier(name: any): boolean`

**Parameters:**

- **`name`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isModifier(name) {
    return name == "public" || name == "private" || name == "protected" || name == "abstract" || name == "readonly"
  }
```
</details>

### `Context(prev: any, vars: any, block: any): void`

**Parameters:**

- **`prev`** `any`
- **`vars`** `any`
- **`block`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Context(prev, vars, block) { this.prev = prev; this.vars = vars; this.block = block }
```
</details>

### `Var(name: any, next: any): void`

**Parameters:**

- **`name`** `any`
- **`next`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Var(name, next) { this.name = name; this.next = next }
```
</details>

### `pushcontext(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function pushcontext() {
    cx.state.context = new Context(cx.state.context, cx.state.localVars, false)
    cx.state.localVars = defaultVars
  }
```
</details>

### `pushblockcontext(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function pushblockcontext() {
    cx.state.context = new Context(cx.state.context, cx.state.localVars, true)
    cx.state.localVars = null
  }
```
</details>

### `popcontext(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function popcontext() {
    cx.state.localVars = cx.state.context.vars
    cx.state.context = cx.state.context.prev
  }
```
</details>

### `pushlex(type: any, info: any): { (): void; lex: boolean; }`

**Parameters:**

- **`type`** `any`
- **`info`** `any`

**Returns:** `{ (): void; lex: boolean; }`

**Calls:**

- `cx.stream.column`

<details><summary>Code</summary>

```typescript
function pushlex(type, info) {
    var result = function() {
      var state = cx.state, indent = state.indented;
      if (state.lexical.type == "stat") indent = state.lexical.indented;
      else for (var outer = state.lexical; outer && outer.type == ")" && outer.align; outer = outer.prev)
        indent = outer.indented;
      state.lexical = new JSLexical(indent, cx.stream.column(), type, null, state.lexical, info);
    };
    result.lex = true;
    return result;
  }
```
</details>

### `result(): void`

**Returns:** `void`

**Calls:**

- `cx.stream.column`

<details><summary>Code</summary>

```typescript
function() {
      var state = cx.state, indent = state.indented;
      if (state.lexical.type == "stat") indent = state.lexical.indented;
      else for (var outer = state.lexical; outer && outer.type == ")" && outer.align; outer = outer.prev)
        indent = outer.indented;
      state.lexical = new JSLexical(indent, cx.stream.column(), type, null, state.lexical, info);
    }
```
</details>

### `poplex(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function poplex() {
    var state = cx.state;
    if (state.lexical.prev) {
      if (state.lexical.type == ")")
        state.indented = state.lexical.indented;
      state.lexical = state.lexical.prev;
    }
  }
```
</details>

### `expect(wanted: any): (type: any) => boolean | void`

**Parameters:**

- **`wanted`** `any`

**Returns:** `(type: any) => boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function expect(wanted) {
    function exp(type) {
      if (type == wanted) return cont();
      else if (wanted == ";" || type == "}" || type == ")" || type == "]") return pass();
      else return cont(exp);
    };
    return exp;
  }
```
</details>

### `exp(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function exp(type) {
      if (type == wanted) return cont();
      else if (wanted == ";" || type == "}" || type == ")" || type == "]") return pass();
      else return cont(exp);
    }
```
</details>

### `statement(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pushlex`
- `expect`
- `cx.stream.match`
- `complex_call_13930`
- `pass`

<details><summary>Code</summary>

```typescript
function statement(type, value) {
    if (type == "var") return cont(pushlex("vardef", value), vardef, expect(";"), poplex);
    if (type == "keyword a") return cont(pushlex("form"), parenExpr, statement, poplex);
    if (type == "keyword b") return cont(pushlex("form"), statement, poplex);
    if (type == "keyword d") return cx.stream.match(/^\s*$/, false) ? cont() : cont(pushlex("stat"), maybeexpression, expect(";"), poplex);
    if (type == "debugger") return cont(expect(";"));
    if (type == "{") return cont(pushlex("}"), pushblockcontext, block, poplex, popcontext);
    if (type == ";") return cont();
    if (type == "if") {
      if (cx.state.lexical.info == "else" && cx.state.cc[cx.state.cc.length - 1] == poplex)
        cx.state.cc.pop()();
      return cont(pushlex("form"), parenExpr, statement, poplex, maybeelse);
    }
    if (type == "function") return cont(functiondef);
    if (type == "for") return cont(pushlex("form"), pushblockcontext, forspec, statement, popcontext, poplex);
    if (type == "class" || (isTS && value == "interface")) {
      cx.marked = "keyword"
      return cont(pushlex("form", type == "class" ? type : value), className, poplex)
    }
    if (type == "variable") {
      if (isTS && value == "declare") {
        cx.marked = "keyword"
        return cont(statement)
      } else if (isTS && (value == "module" || value == "enum" || value == "type") && cx.stream.match(/^\s*\w/, false)) {
        cx.marked = "keyword"
        if (value == "enum") return cont(enumdef);
        else if (value == "type") return cont(typename, expect("operator"), typeexpr, expect(";"));
        else return cont(pushlex("form"), pattern, expect("{"), pushlex("}"), block, poplex, poplex)
      } else if (isTS && value == "namespace") {
        cx.marked = "keyword"
        return cont(pushlex("form"), expression, statement, poplex)
      } else if (isTS && value == "abstract") {
        cx.marked = "keyword"
        return cont(statement)
      } else {
        return cont(pushlex("stat"), maybelabel);
      }
    }
    if (type == "switch") return cont(pushlex("form"), parenExpr, expect("{"), pushlex("}", "switch"), pushblockcontext,
                                      block, poplex, poplex, popcontext);
    if (type == "case") return cont(expression, expect(":"));
    if (type == "default") return cont(expect(":"));
    if (type == "catch") return cont(pushlex("form"), pushcontext, maybeCatchBinding, statement, poplex, popcontext);
    if (type == "export") return cont(pushlex("stat"), afterExport, poplex);
    if (type == "import") return cont(pushlex("stat"), afterImport, poplex);
    if (type == "async") return cont(statement)
    if (value == "@") return cont(expression, statement)
    return pass(pushlex("stat"), expression, expect(";"), poplex);
  }
```
</details>

### `maybeCatchBinding(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`
- `expect`

<details><summary>Code</summary>

```typescript
function maybeCatchBinding(type) {
    if (type == "(") return cont(funarg, expect(")"))
  }
```
</details>

### `expression(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `expressionInner`

<details><summary>Code</summary>

```typescript
function expression(type, value) {
    return expressionInner(type, value, false);
  }
```
</details>

### `expressionNoComma(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `expressionInner`

<details><summary>Code</summary>

```typescript
function expressionNoComma(type, value) {
    return expressionInner(type, value, true);
  }
```
</details>

### `parenExpr(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `pass`
- `cont`
- `pushlex`
- `expect`

<details><summary>Code</summary>

```typescript
function parenExpr(type) {
    if (type != "(") return pass()
    return cont(pushlex(")"), maybeexpression, expect(")"), poplex)
  }
```
</details>

### `expressionInner(type: any, value: any, noComma: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`
- **`noComma`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pushlex`
- `commasep`
- `expect`
- `pass`
- `atomicTypes.hasOwnProperty`
- `contCommasep`
- `maybeTarget`

<details><summary>Code</summary>

```typescript
function expressionInner(type, value, noComma) {
    if (cx.state.fatArrowAt == cx.stream.start) {
      var body = noComma ? arrowBodyNoComma : arrowBody;
      if (type == "(") return cont(pushcontext, pushlex(")"), commasep(funarg, ")"), poplex, expect("=>"), body, popcontext);
      else if (type == "variable") return pass(pushcontext, pattern, expect("=>"), body, popcontext);
    }

    var maybeop = noComma ? maybeoperatorNoComma : maybeoperatorComma;
    if (atomicTypes.hasOwnProperty(type)) return cont(maybeop);
    if (type == "function") return cont(functiondef, maybeop);
    if (type == "class" || (isTS && value == "interface")) { cx.marked = "keyword"; return cont(pushlex("form"), classExpression, poplex); }
    if (type == "keyword c" || type == "async") return cont(noComma ? expressionNoComma : expression);
    if (type == "(") return cont(pushlex(")"), maybeexpression, expect(")"), poplex, maybeop);
    if (type == "operator" || type == "spread") return cont(noComma ? expressionNoComma : expression);
    if (type == "[") return cont(pushlex("]"), arrayLiteral, poplex, maybeop);
    if (type == "{") return contCommasep(objprop, "}", null, maybeop);
    if (type == "quasi") return pass(quasi, maybeop);
    if (type == "new") return cont(maybeTarget(noComma));
    return cont();
  }
```
</details>

### `maybeexpression(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

**Calls:**

- `type.match`
- `pass`

<details><summary>Code</summary>

```typescript
function maybeexpression(type) {
    if (type.match(/[;\}\)\],]/)) return pass();
    return pass(expression);
  }
```
</details>

### `maybeoperatorComma(type: any, value: any): any`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `cont`
- `maybeoperatorNoComma`

<details><summary>Code</summary>

```typescript
function maybeoperatorComma(type, value) {
    if (type == ",") return cont(maybeexpression);
    return maybeoperatorNoComma(type, value, false);
  }
```
</details>

### `maybeoperatorNoComma(type: any, value: any, noComma: any): any`

**Parameters:**

- **`type`** `any`
- **`value`** `any`
- **`noComma`** `any`

**Returns:** `any`

**Calls:**

- `cont`
- `/\+\+|--/.test`
- `cx.stream.match`
- `pushlex`
- `commasep`
- `expect`
- `pass`
- `contCommasep`
- `cx.stream.backUp`

<details><summary>Code</summary>

```typescript
function maybeoperatorNoComma(type, value, noComma) {
    var me = noComma == false ? maybeoperatorComma : maybeoperatorNoComma;
    var expr = noComma == false ? expression : expressionNoComma;
    if (type == "=>") return cont(pushcontext, noComma ? arrowBodyNoComma : arrowBody, popcontext);
    if (type == "operator") {
      if (/\+\+|--/.test(value) || isTS && value == "!") return cont(me);
      if (isTS && value == "<" && cx.stream.match(/^([^<>]|<[^<>]*>)*>\s*\(/, false))
        return cont(pushlex(">"), commasep(typeexpr, ">"), poplex, me);
      if (value == "?") return cont(expression, expect(":"), expr);
      return cont(expr);
    }
    if (type == "quasi") { return pass(quasi, me); }
    if (type == ";") return;
    if (type == "(") return contCommasep(expressionNoComma, ")", "call", me);
    if (type == ".") return cont(property, me);
    if (type == "[") return cont(pushlex("]"), maybeexpression, expect("]"), poplex, me);
    if (isTS && value == "as") { cx.marked = "keyword"; return cont(typeexpr, me) }
    if (type == "regexp") {
      cx.state.lastType = cx.marked = "operator"
      cx.stream.backUp(cx.stream.pos - cx.stream.start - 1)
      return cont(expr)
    }
  }
```
</details>

### `quasi(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `pass`
- `value.slice`
- `cont`

<details><summary>Code</summary>

```typescript
function quasi(type, value) {
    if (type != "quasi") return pass();
    if (value.slice(value.length - 2) != "${") return cont(quasi);
    return cont(maybeexpression, continueQuasi);
  }
```
</details>

### `continueQuasi(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function continueQuasi(type) {
    if (type == "}") {
      cx.marked = "string-2";
      cx.state.tokenize = tokenQuasi;
      return cont(quasi);
    }
  }
```
</details>

### `arrowBody(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

**Calls:**

- `findFatArrow`
- `pass`

<details><summary>Code</summary>

```typescript
function arrowBody(type) {
    findFatArrow(cx.stream, cx.state);
    return pass(type == "{" ? statement : expression);
  }
```
</details>

### `arrowBodyNoComma(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

**Calls:**

- `findFatArrow`
- `pass`

<details><summary>Code</summary>

```typescript
function arrowBodyNoComma(type) {
    findFatArrow(cx.stream, cx.state);
    return pass(type == "{" ? statement : expressionNoComma);
  }
```
</details>

### `maybeTarget(noComma: any): (type: any) => boolean | void`

**Parameters:**

- **`noComma`** `any`

**Returns:** `(type: any) => boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function maybeTarget(noComma) {
    return function(type) {
      if (type == ".") return cont(noComma ? targetNoComma : target);
      else if (type == "variable" && isTS) return cont(maybeTypeArgs, noComma ? maybeoperatorNoComma : maybeoperatorComma)
      else return pass(noComma ? expressionNoComma : expression);
    };
  }
```
</details>

### `target(_: any, value: any): boolean`

**Parameters:**

- **`_`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function target(_, value) {
    if (value == "target") { cx.marked = "keyword"; return cont(maybeoperatorComma); }
  }
```
</details>

### `targetNoComma(_: any, value: any): boolean`

**Parameters:**

- **`_`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function targetNoComma(_, value) {
    if (value == "target") { cx.marked = "keyword"; return cont(maybeoperatorNoComma); }
  }
```
</details>

### `maybelabel(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`
- `expect`

<details><summary>Code</summary>

```typescript
function maybelabel(type) {
    if (type == ":") return cont(poplex, statement);
    return pass(maybeoperatorComma, expect(";"), poplex);
  }
```
</details>

### `property(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function property(type) {
    if (type == "variable") {cx.marked = "property"; return cont();}
  }
```
</details>

### `objprop(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `cx.stream.match`
- `isModifier`
- `expect`
- `pass`

<details><summary>Code</summary>

```typescript
function objprop(type, value) {
    if (type == "async") {
      cx.marked = "property";
      return cont(objprop);
    } else if (type == "variable" || cx.style == "keyword") {
      cx.marked = "property";
      if (value == "get" || value == "set") return cont(getterSetter);
      var m // Work around fat-arrow-detection complication for detecting typescript typed arrow params
      if (isTS && cx.state.fatArrowAt == cx.stream.start && (m = cx.stream.match(/^\s*:\s*/, false)))
        cx.state.fatArrowAt = cx.stream.pos + m[0].length
      return cont(afterprop);
    } else if (type == "number" || type == "string") {
      cx.marked = jsonldMode ? "property" : (cx.style + " property");
      return cont(afterprop);
    } else if (type == "jsonld-keyword") {
      return cont(afterprop);
    } else if (isTS && isModifier(value)) {
      cx.marked = "keyword"
      return cont(objprop)
    } else if (type == "[") {
      return cont(expression, maybetype, expect("]"), afterprop);
    } else if (type == "spread") {
      return cont(expressionNoComma, afterprop);
    } else if (value == "*") {
      cx.marked = "keyword";
      return cont(objprop);
    } else if (type == ":") {
      return pass(afterprop)
    }
  }
```
</details>

### `getterSetter(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `pass`
- `cont`

<details><summary>Code</summary>

```typescript
function getterSetter(type) {
    if (type != "variable") return pass(afterprop);
    cx.marked = "property";
    return cont(functiondef);
  }
```
</details>

### `afterprop(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function afterprop(type) {
    if (type == ":") return cont(expressionNoComma);
    if (type == "(") return pass(functiondef);
  }
```
</details>

### `commasep(what: any, end: any, sep: any): (type: any, value: any) => boolean | void`

**Parameters:**

- **`what`** `any`
- **`end`** `any`
- **`sep`** `any`

**Returns:** `(type: any, value: any) => boolean | void`

**Calls:**

- `sep.indexOf`
- `cont`
- `pass`
- `expect`

<details><summary>Code</summary>

```typescript
function commasep(what, end, sep) {
    function proceed(type, value) {
      if (sep ? sep.indexOf(type) > -1 : type == ",") {
        var lex = cx.state.lexical;
        if (lex.info == "call") lex.pos = (lex.pos || 0) + 1;
        return cont(function(type, value) {
          if (type == end || value == end) return pass()
          return pass(what)
        }, proceed);
      }
      if (type == end || value == end) return cont();
      if (sep && sep.indexOf(";") > -1) return pass(what)
      return cont(expect(end));
    }
    return function(type, value) {
      if (type == end || value == end) return cont();
      return pass(what, proceed);
    };
  }
```
</details>

### `proceed(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `sep.indexOf`
- `cont`
- `pass`
- `expect`

<details><summary>Code</summary>

```typescript
function proceed(type, value) {
      if (sep ? sep.indexOf(type) > -1 : type == ",") {
        var lex = cx.state.lexical;
        if (lex.info == "call") lex.pos = (lex.pos || 0) + 1;
        return cont(function(type, value) {
          if (type == end || value == end) return pass()
          return pass(what)
        }, proceed);
      }
      if (type == end || value == end) return cont();
      if (sep && sep.indexOf(";") > -1) return pass(what)
      return cont(expect(end));
    }
```
</details>

### `contCommasep(what: any, end: any, info: any): boolean`

**Parameters:**

- **`what`** `any`
- **`end`** `any`
- **`info`** `any`

**Returns:** `boolean`

**Calls:**

- `cx.cc.push`
- `cont`
- `pushlex`
- `commasep`

<details><summary>Code</summary>

```typescript
function contCommasep(what, end, info) {
    for (var i = 3; i < arguments.length; i++)
      cx.cc.push(arguments[i]);
    return cont(pushlex(end, info), commasep(what, end), poplex);
  }
```
</details>

### `block(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function block(type) {
    if (type == "}") return cont();
    return pass(statement, block);
  }
```
</details>

### `maybetype(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function maybetype(type, value) {
    if (isTS) {
      if (type == ":") return cont(typeexpr);
      if (value == "?") return cont(maybetype);
    }
  }
```
</details>

### `maybetypeOrIn(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function maybetypeOrIn(type, value) {
    if (isTS && (type == ":" || value == "in")) return cont(typeexpr)
  }
```
</details>

### `mayberettype(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `cx.stream.match`
- `cont`

<details><summary>Code</summary>

```typescript
function mayberettype(type) {
    if (isTS && type == ":") {
      if (cx.stream.match(/^\s*\w+\s+is\b/, false)) return cont(expression, isKW, typeexpr)
      else return cont(typeexpr)
    }
  }
```
</details>

### `isKW(_: any, value: any): boolean`

**Parameters:**

- **`_`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function isKW(_, value) {
    if (value == "is") {
      cx.marked = "keyword"
      return cont()
    }
  }
```
</details>

### `typeexpr(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pushlex`
- `commasep`
- `pass`

<details><summary>Code</summary>

```typescript
function typeexpr(type, value) {
    if (value == "keyof" || value == "typeof" || value == "infer" || value == "readonly") {
      cx.marked = "keyword"
      return cont(value == "typeof" ? expressionNoComma : typeexpr)
    }
    if (type == "variable" || value == "void") {
      cx.marked = "type"
      return cont(afterType)
    }
    if (value == "|" || value == "&") return cont(typeexpr)
    if (type == "string" || type == "number" || type == "atom") return cont(afterType);
    if (type == "[") return cont(pushlex("]"), commasep(typeexpr, "]", ","), poplex, afterType)
    if (type == "{") return cont(pushlex("}"), typeprops, poplex, afterType)
    if (type == "(") return cont(commasep(typearg, ")"), maybeReturnType, afterType)
    if (type == "<") return cont(commasep(typeexpr, ">"), typeexpr)
    if (type == "quasi") { return pass(quasiType, afterType); }
  }
```
</details>

### `maybeReturnType(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function maybeReturnType(type) {
    if (type == "=>") return cont(typeexpr)
  }
```
</details>

### `typeprops(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `type.match`
- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function typeprops(type) {
    if (type.match(/[\}\)\]]/)) return cont()
    if (type == "," || type == ";") return cont(typeprops)
    return pass(typeprop, typeprops)
  }
```
</details>

### `typeprop(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `expect`
- `pass`
- `type.match`

<details><summary>Code</summary>

```typescript
function typeprop(type, value) {
    if (type == "variable" || cx.style == "keyword") {
      cx.marked = "property"
      return cont(typeprop)
    } else if (value == "?" || type == "number" || type == "string") {
      return cont(typeprop)
    } else if (type == ":") {
      return cont(typeexpr)
    } else if (type == "[") {
      return cont(expect("variable"), maybetypeOrIn, expect("]"), typeprop)
    } else if (type == "(") {
      return pass(functiondecl, typeprop)
    } else if (!type.match(/[;\}\)\],]/)) {
      return cont()
    }
  }
```
</details>

### `quasiType(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `pass`
- `value.slice`
- `cont`

<details><summary>Code</summary>

```typescript
function quasiType(type, value) {
    if (type != "quasi") return pass();
    if (value.slice(value.length - 2) != "${") return cont(quasiType);
    return cont(typeexpr, continueQuasiType);
  }
```
</details>

### `continueQuasiType(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function continueQuasiType(type) {
    if (type == "}") {
      cx.marked = "string-2";
      cx.state.tokenize = tokenQuasi;
      return cont(quasiType);
    }
  }
```
</details>

### `typearg(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cx.stream.match`
- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function typearg(type, value) {
    if (type == "variable" && cx.stream.match(/^\s*[?:]/, false) || value == "?") return cont(typearg)
    if (type == ":") return cont(typeexpr)
    if (type == "spread") return cont(typearg)
    return pass(typeexpr)
  }
```
</details>

### `afterType(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`
- `pushlex`
- `commasep`
- `expect`

<details><summary>Code</summary>

```typescript
function afterType(type, value) {
    if (value == "<") return cont(pushlex(">"), commasep(typeexpr, ">"), poplex, afterType)
    if (value == "|" || type == "." || value == "&") return cont(typeexpr)
    if (type == "[") return cont(typeexpr, expect("]"), afterType)
    if (value == "extends" || value == "implements") { cx.marked = "keyword"; return cont(typeexpr) }
    if (value == "?") return cont(typeexpr, expect(":"), typeexpr)
  }
```
</details>

### `maybeTypeArgs(_: any, value: any): boolean`

**Parameters:**

- **`_`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`
- `pushlex`
- `commasep`

<details><summary>Code</summary>

```typescript
function maybeTypeArgs(_, value) {
    if (value == "<") return cont(pushlex(">"), commasep(typeexpr, ">"), poplex, afterType)
  }
```
</details>

### `typeparam(): void`

**Returns:** `void`

**Calls:**

- `pass`

<details><summary>Code</summary>

```typescript
function typeparam() {
    return pass(typeexpr, maybeTypeDefault)
  }
```
</details>

### `maybeTypeDefault(_: any, value: any): boolean`

**Parameters:**

- **`_`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function maybeTypeDefault(_, value) {
    if (value == "=") return cont(typeexpr)
  }
```
</details>

### `vardef(_: any, value: any): boolean | void`

**Parameters:**

- **`_`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function vardef(_, value) {
    if (value == "enum") {cx.marked = "keyword"; return cont(enumdef)}
    return pass(pattern, maybetype, maybeAssign, vardefCont);
  }
```
</details>

### `pattern(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `isModifier`
- `cont`
- `register`
- `contCommasep`

<details><summary>Code</summary>

```typescript
function pattern(type, value) {
    if (isTS && isModifier(value)) { cx.marked = "keyword"; return cont(pattern) }
    if (type == "variable") { register(value); return cont(); }
    if (type == "spread") return cont(pattern);
    if (type == "[") return contCommasep(eltpattern, "]");
    if (type == "{") return contCommasep(proppattern, "}");
  }
```
</details>

### `proppattern(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cx.stream.match`
- `register`
- `cont`
- `pass`
- `expect`

<details><summary>Code</summary>

```typescript
function proppattern(type, value) {
    if (type == "variable" && !cx.stream.match(/^\s*:/, false)) {
      register(value);
      return cont(maybeAssign);
    }
    if (type == "variable") cx.marked = "property";
    if (type == "spread") return cont(pattern);
    if (type == "}") return pass();
    if (type == "[") return cont(expression, expect(']'), expect(':'), proppattern);
    return cont(expect(":"), pattern, maybeAssign);
  }
```
</details>

### `eltpattern(): void`

**Returns:** `void`

**Calls:**

- `pass`

<details><summary>Code</summary>

```typescript
function eltpattern() {
    return pass(pattern, maybeAssign)
  }
```
</details>

### `maybeAssign(_type: any, value: any): boolean`

**Parameters:**

- **`_type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function maybeAssign(_type, value) {
    if (value == "=") return cont(expressionNoComma);
  }
```
</details>

### `vardefCont(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function vardefCont(type) {
    if (type == ",") return cont(vardef);
  }
```
</details>

### `maybeelse(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`
- `pushlex`

<details><summary>Code</summary>

```typescript
function maybeelse(type, value) {
    if (type == "keyword b" && value == "else") return cont(pushlex("form", "else"), statement, poplex);
  }
```
</details>

### `forspec(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`
- `pushlex`

<details><summary>Code</summary>

```typescript
function forspec(type, value) {
    if (value == "await") return cont(forspec);
    if (type == "(") return cont(pushlex(")"), forspec1, poplex);
  }
```
</details>

### `forspec1(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function forspec1(type) {
    if (type == "var") return cont(vardef, forspec2);
    if (type == "variable") return cont(forspec2);
    return pass(forspec2)
  }
```
</details>

### `forspec2(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function forspec2(type, value) {
    if (type == ")") return cont()
    if (type == ";") return cont(forspec2)
    if (value == "in" || value == "of") { cx.marked = "keyword"; return cont(expression, forspec2) }
    return pass(expression, forspec2)
  }
```
</details>

### `functiondef(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`
- `register`
- `pushlex`
- `commasep`

<details><summary>Code</summary>

```typescript
function functiondef(type, value) {
    if (value == "*") {cx.marked = "keyword"; return cont(functiondef);}
    if (type == "variable") {register(value); return cont(functiondef);}
    if (type == "(") return cont(pushcontext, pushlex(")"), commasep(funarg, ")"), poplex, mayberettype, statement, popcontext);
    if (isTS && value == "<") return cont(pushlex(">"), commasep(typeparam, ">"), poplex, functiondef)
  }
```
</details>

### `functiondecl(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`
- `register`
- `pushlex`
- `commasep`

<details><summary>Code</summary>

```typescript
function functiondecl(type, value) {
    if (value == "*") {cx.marked = "keyword"; return cont(functiondecl);}
    if (type == "variable") {register(value); return cont(functiondecl);}
    if (type == "(") return cont(pushcontext, pushlex(")"), commasep(funarg, ")"), poplex, mayberettype, popcontext);
    if (isTS && value == "<") return cont(pushlex(">"), commasep(typeparam, ">"), poplex, functiondecl)
  }
```
</details>

### `typename(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`
- `pushlex`
- `commasep`

<details><summary>Code</summary>

```typescript
function typename(type, value) {
    if (type == "keyword" || type == "variable") {
      cx.marked = "type"
      return cont(typename)
    } else if (value == "<") {
      return cont(pushlex(">"), commasep(typeparam, ">"), poplex)
    }
  }
```
</details>

### `funarg(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `isModifier`
- `pass`

<details><summary>Code</summary>

```typescript
function funarg(type, value) {
    if (value == "@") cont(expression, funarg)
    if (type == "spread") return cont(funarg);
    if (isTS && isModifier(value)) { cx.marked = "keyword"; return cont(funarg); }
    if (isTS && type == "this") return cont(maybetype, maybeAssign)
    return pass(pattern, maybetype, maybeAssign);
  }
```
</details>

### `classExpression(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `className`
- `classNameAfter`

**Internal Comments:**
```
// Class expressions may have an optional name.
```

<details><summary>Code</summary>

```typescript
function classExpression(type, value) {
    // Class expressions may have an optional name.
    if (type == "variable") return className(type, value);
    return classNameAfter(type, value);
  }
```
</details>

### `className(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `register`
- `cont`

<details><summary>Code</summary>

```typescript
function className(type, value) {
    if (type == "variable") {register(value); return cont(classNameAfter);}
  }
```
</details>

### `classNameAfter(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`
- `pushlex`
- `commasep`

<details><summary>Code</summary>

```typescript
function classNameAfter(type, value) {
    if (value == "<") return cont(pushlex(">"), commasep(typeparam, ">"), poplex, classNameAfter)
    if (value == "extends" || value == "implements" || (isTS && type == ",")) {
      if (value == "implements") cx.marked = "keyword";
      return cont(isTS ? typeexpr : expression, classNameAfter);
    }
    if (type == "{") return cont(pushlex("}"), classBody, poplex);
  }
```
</details>

### `classBody(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `isModifier`
- `cx.stream.match`
- `cont`
- `expect`
- `pass`

<details><summary>Code</summary>

```typescript
function classBody(type, value) {
    if (type == "async" ||
        (type == "variable" &&
         (value == "static" || value == "get" || value == "set" || (isTS && isModifier(value))) &&
         cx.stream.match(/^\s+[\w$\xa1-\uffff]/, false))) {
      cx.marked = "keyword";
      return cont(classBody);
    }
    if (type == "variable" || cx.style == "keyword") {
      cx.marked = "property";
      return cont(classfield, classBody);
    }
    if (type == "number" || type == "string") return cont(classfield, classBody);
    if (type == "[")
      return cont(expression, maybetype, expect("]"), classfield, classBody)
    if (value == "*") {
      cx.marked = "keyword";
      return cont(classBody);
    }
    if (isTS && type == "(") return pass(functiondecl, classBody)
    if (type == ";" || type == ",") return cont(classBody);
    if (type == "}") return cont();
    if (value == "@") return cont(expression, classBody)
  }
```
</details>

### `classfield(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function classfield(type, value) {
    if (value == "!") return cont(classfield)
    if (value == "?") return cont(classfield)
    if (type == ":") return cont(typeexpr, maybeAssign)
    if (value == "=") return cont(expressionNoComma)
    var context = cx.state.lexical.prev, isInterface = context && context.info == "interface"
    return pass(isInterface ? functiondecl : functiondef)
  }
```
</details>

### `afterExport(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `expect`
- `commasep`
- `pass`

<details><summary>Code</summary>

```typescript
function afterExport(type, value) {
    if (value == "*") { cx.marked = "keyword"; return cont(maybeFrom, expect(";")); }
    if (value == "default") { cx.marked = "keyword"; return cont(expression, expect(";")); }
    if (type == "{") return cont(commasep(exportField, "}"), maybeFrom, expect(";"));
    return pass(statement);
  }
```
</details>

### `exportField(type: any, value: any): boolean | void`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `expect`
- `pass`

<details><summary>Code</summary>

```typescript
function exportField(type, value) {
    if (value == "as") { cx.marked = "keyword"; return cont(expect("variable")); }
    if (type == "variable") return pass(expressionNoComma, exportField);
  }
```
</details>

### `afterImport(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`

<details><summary>Code</summary>

```typescript
function afterImport(type) {
    if (type == "string") return cont();
    if (type == "(") return pass(expression);
    if (type == ".") return pass(maybeoperatorComma);
    return pass(importSpec, maybeMoreImports, maybeFrom);
  }
```
</details>

### `importSpec(type: any, value: any): boolean`

**Parameters:**

- **`type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `contCommasep`
- `register`
- `cont`

<details><summary>Code</summary>

```typescript
function importSpec(type, value) {
    if (type == "{") return contCommasep(importSpec, "}");
    if (type == "variable") register(value);
    if (value == "*") cx.marked = "keyword";
    return cont(maybeAs);
  }
```
</details>

### `maybeMoreImports(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function maybeMoreImports(type) {
    if (type == ",") return cont(importSpec, maybeMoreImports)
  }
```
</details>

### `maybeAs(_type: any, value: any): boolean`

**Parameters:**

- **`_type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function maybeAs(_type, value) {
    if (value == "as") { cx.marked = "keyword"; return cont(importSpec); }
  }
```
</details>

### `maybeFrom(_type: any, value: any): boolean`

**Parameters:**

- **`_type`** `any`
- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `cont`

<details><summary>Code</summary>

```typescript
function maybeFrom(_type, value) {
    if (value == "from") { cx.marked = "keyword"; return cont(expression); }
  }
```
</details>

### `arrayLiteral(type: any): boolean | void`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean | void`

**Calls:**

- `cont`
- `pass`
- `commasep`

<details><summary>Code</summary>

```typescript
function arrayLiteral(type) {
    if (type == "]") return cont();
    return pass(commasep(expressionNoComma, "]"));
  }
```
</details>

### `enumdef(): void`

**Returns:** `void`

**Calls:**

- `pass`
- `pushlex`
- `expect`
- `commasep`

<details><summary>Code</summary>

```typescript
function enumdef() {
    return pass(pushlex("form"), pattern, expect("{"), pushlex("}"), commasep(enummember, "}"), poplex, poplex)
  }
```
</details>

### `enummember(): void`

**Returns:** `void`

**Calls:**

- `pass`

<details><summary>Code</summary>

```typescript
function enummember() {
    return pass(pattern, maybeAssign);
  }
```
</details>

### `isContinuedStatement(state: any, textAfter: any): boolean`

**Parameters:**

- **`state`** `any`
- **`textAfter`** `any`

**Returns:** `boolean`

**Calls:**

- `isOperatorChar.test`
- `textAfter.charAt`
- `/[,.]/.test`

<details><summary>Code</summary>

```typescript
function isContinuedStatement(state, textAfter) {
    return state.lastType == "operator" || state.lastType == "," ||
      isOperatorChar.test(textAfter.charAt(0)) ||
      /[,.]/.test(textAfter.charAt(0));
  }
```
</details>

### `expressionAllowed(stream: any, state: any, backUp: any): boolean`

**Parameters:**

- **`stream`** `any`
- **`state`** `any`
- **`backUp`** `any`

**Returns:** `boolean`

**Calls:**

- `/^(?:operator|sof|keyword [bcd]|case|new|export|default|spread|[\[{}\(,;:]|=>)$/.test`
- `/\{\s*$/.test`
- `stream.string.slice`

<details><summary>Code</summary>

```typescript
function expressionAllowed(stream, state, backUp) {
    return state.tokenize == tokenBase &&
      /^(?:operator|sof|keyword [bcd]|case|new|export|default|spread|[\[{}\(,;:]|=>)$/.test(state.lastType) ||
      (state.lastType == "quasi" && /\{\s*$/.test(stream.string.slice(0, stream.pos - (backUp || 0))))
  }
```
</details>

### `startState(basecolumn: any): { tokenize: (stream: any, state: any) => any; lastType: string; cc: any[]; lexical: JSLexical; localVars: any; context: Context; indented: any; }`

**Parameters:**

- **`basecolumn`** `any`

**Returns:** `{ tokenize: (stream: any, state: any) => any; lastType: string; cc: any[]; lexical: JSLexical; localVars: any; context: Context; indented: any; }`

<details><summary>Code</summary>

```typescript
function(basecolumn) {
      var state = {
        tokenize: tokenBase,
        lastType: "sof",
        cc: [],
        lexical: new JSLexical((basecolumn || 0) - indentUnit, 0, "block", false),
        localVars: parserConfig.localVars,
        context: parserConfig.localVars && new Context(null, null, false),
        indented: basecolumn || 0
      };
      if (parserConfig.globalVars && typeof parserConfig.globalVars == "object")
        state.globalVars = parserConfig.globalVars;
      return state;
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
- `state.lexical.hasOwnProperty`
- `stream.indentation`
- `findFatArrow`
- `stream.eatSpace`
- `state.tokenize`
- `parseJS`

<details><summary>Code</summary>

```typescript
function(stream, state) {
      if (stream.sol()) {
        if (!state.lexical.hasOwnProperty("align"))
          state.lexical.align = false;
        state.indented = stream.indentation();
        findFatArrow(stream, state);
      }
      if (state.tokenize != tokenComment && stream.eatSpace()) return null;
      var style = state.tokenize(stream, state);
      if (type == "comment") return style;
      state.lastType = type == "operator" && (content == "++" || content == "--") ? "incdec" : type;
      return parseJS(state, style, type, content, stream);
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
- `/^\s*else\b/.test`
- `/^[,\.=+\-*:?[\(]/.test`
- `isContinuedStatement`
- `/^(?:case|default)\b/.test`

**Internal Comments:**
```
// Kludge to prevent 'maybelse' from blocking lexical scope pops
```

<details><summary>Code</summary>

```typescript
function(state, textAfter) {
      if (state.tokenize == tokenComment || state.tokenize == tokenQuasi) return CodeMirror.Pass;
      if (state.tokenize != tokenBase) return 0;
      var firstChar = textAfter && textAfter.charAt(0), lexical = state.lexical, top;
      // Kludge to prevent 'maybelse' from blocking lexical scope pops
      if (!/^\s*else\b/.test(textAfter)) for (var i = state.cc.length - 1; i >= 0; --i) {
        var c = state.cc[i];
        if (c == poplex) lexical = lexical.prev;
        else if (c != maybeelse && c != popcontext) break;
      }
      while ((lexical.type == "stat" || lexical.type == "form") &&
             (firstChar == "}" || ((top = state.cc[state.cc.length - 1]) &&
                                   (top == maybeoperatorComma || top == maybeoperatorNoComma) &&
                                   !/^[,\.=+\-*:?[\(]/.test(textAfter))))
        lexical = lexical.prev;
      if (statementIndent && lexical.type == ")" && lexical.prev.type == "stat")
        lexical = lexical.prev;
      var type = lexical.type, closing = firstChar == type;

      if (type == "vardef") return lexical.indented + (state.lastType == "operator" || state.lastType == "," ? lexical.info.length + 1 : 0);
      else if (type == "form" && firstChar == "{") return lexical.indented;
      else if (type == "form") return lexical.indented + indentUnit;
      else if (type == "stat")
        return lexical.indented + (isContinuedStatement(state, textAfter) ? statementIndent || indentUnit : 0);
      else if (lexical.info == "switch" && !closing && parserConfig.doubleIndentSwitch != false)
        return lexical.indented + (/^(?:case|default)\b/.test(textAfter) ? indentUnit : 2 * indentUnit);
      else if (lexical.align) return lexical.column + (closing ? 0 : 1);
      else return lexical.indented + (closing ? 0 : indentUnit);
    }
```
</details>

### `skipExpression(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `parseJS`

<details><summary>Code</summary>

```typescript
function(state) {
      parseJS(state, "atom", "atom", "true", new CodeMirror.StringStream("", 2, null))
    }
```
</details>

### `startState(basecolumn: any): { tokenize: (stream: any, state: any) => any; lastType: string; cc: any[]; lexical: JSLexical; localVars: any; context: Context; indented: any; }`

**Parameters:**

- **`basecolumn`** `any`

**Returns:** `{ tokenize: (stream: any, state: any) => any; lastType: string; cc: any[]; lexical: JSLexical; localVars: any; context: Context; indented: any; }`

<details><summary>Code</summary>

```typescript
function(basecolumn) {
      var state = {
        tokenize: tokenBase,
        lastType: "sof",
        cc: [],
        lexical: new JSLexical((basecolumn || 0) - indentUnit, 0, "block", false),
        localVars: parserConfig.localVars,
        context: parserConfig.localVars && new Context(null, null, false),
        indented: basecolumn || 0
      };
      if (parserConfig.globalVars && typeof parserConfig.globalVars == "object")
        state.globalVars = parserConfig.globalVars;
      return state;
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
- `state.lexical.hasOwnProperty`
- `stream.indentation`
- `findFatArrow`
- `stream.eatSpace`
- `state.tokenize`
- `parseJS`

<details><summary>Code</summary>

```typescript
function(stream, state) {
      if (stream.sol()) {
        if (!state.lexical.hasOwnProperty("align"))
          state.lexical.align = false;
        state.indented = stream.indentation();
        findFatArrow(stream, state);
      }
      if (state.tokenize != tokenComment && stream.eatSpace()) return null;
      var style = state.tokenize(stream, state);
      if (type == "comment") return style;
      state.lastType = type == "operator" && (content == "++" || content == "--") ? "incdec" : type;
      return parseJS(state, style, type, content, stream);
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
- `/^\s*else\b/.test`
- `/^[,\.=+\-*:?[\(]/.test`
- `isContinuedStatement`
- `/^(?:case|default)\b/.test`

**Internal Comments:**
```
// Kludge to prevent 'maybelse' from blocking lexical scope pops
```

<details><summary>Code</summary>

```typescript
function(state, textAfter) {
      if (state.tokenize == tokenComment || state.tokenize == tokenQuasi) return CodeMirror.Pass;
      if (state.tokenize != tokenBase) return 0;
      var firstChar = textAfter && textAfter.charAt(0), lexical = state.lexical, top;
      // Kludge to prevent 'maybelse' from blocking lexical scope pops
      if (!/^\s*else\b/.test(textAfter)) for (var i = state.cc.length - 1; i >= 0; --i) {
        var c = state.cc[i];
        if (c == poplex) lexical = lexical.prev;
        else if (c != maybeelse && c != popcontext) break;
      }
      while ((lexical.type == "stat" || lexical.type == "form") &&
             (firstChar == "}" || ((top = state.cc[state.cc.length - 1]) &&
                                   (top == maybeoperatorComma || top == maybeoperatorNoComma) &&
                                   !/^[,\.=+\-*:?[\(]/.test(textAfter))))
        lexical = lexical.prev;
      if (statementIndent && lexical.type == ")" && lexical.prev.type == "stat")
        lexical = lexical.prev;
      var type = lexical.type, closing = firstChar == type;

      if (type == "vardef") return lexical.indented + (state.lastType == "operator" || state.lastType == "," ? lexical.info.length + 1 : 0);
      else if (type == "form" && firstChar == "{") return lexical.indented;
      else if (type == "form") return lexical.indented + indentUnit;
      else if (type == "stat")
        return lexical.indented + (isContinuedStatement(state, textAfter) ? statementIndent || indentUnit : 0);
      else if (lexical.info == "switch" && !closing && parserConfig.doubleIndentSwitch != false)
        return lexical.indented + (/^(?:case|default)\b/.test(textAfter) ? indentUnit : 2 * indentUnit);
      else if (lexical.align) return lexical.column + (closing ? 0 : 1);
      else return lexical.indented + (closing ? 0 : indentUnit);
    }
```
</details>

### `skipExpression(state: any): void`

**Parameters:**

- **`state`** `any`

**Returns:** `void`

**Calls:**

- `parseJS`

<details><summary>Code</summary>

```typescript
function(state) {
      parseJS(state, "atom", "atom", "true", new CodeMirror.StringStream("", 2, null))
    }
```
</details>


---