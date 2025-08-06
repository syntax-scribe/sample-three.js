[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `doc_comment.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 33 |
| 📊 Variables & Constants | 38 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/ternjs/doc_comment.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `WG_MADEUP` | `number` | let/var | `1` | ✗ |
| `WG_STRONG` | `number` | let/var | `101` | ✗ |
| `prop` | `any` | let/var | `node.properties[i]` | ✗ |
| `prop` | `any` | let/var | `type.props[node.arguments[1].value]` | ✗ |
| `defs` | `any` | let/var | `data["!typedef"]` | ✗ |
| `orig` | `any` | let/var | `data["!name"]` | ✗ |
| `result` | `any` | let/var | `comments[comments.length - 1]` | ✗ |
| `labels` | `any[]` | let/var | `[]` | ✗ |
| `types` | `any[]` | let/var | `[]` | ✗ |
| `madeUp` | `boolean` | let/var | `false` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `union` | `boolean` | let/var | `false` | ✗ |
| `madeUp` | `boolean` | let/var | `false` | ✗ |
| `isOptional` | `boolean` | let/var | `false` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `madeUp` | `boolean` | let/var | `false` | ✗ |
| `ret` | `any` | let/var | `infer.ANull` | ✗ |
| `start` | `any` | let/var | `pos` | ✗ |
| `defs` | `any` | let/var | `cx.parent && cx.parent.jsdocTypedefs` | ✗ |
| `found` | `any` | let/var | `*not shown*` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `args` | `any` | let/var | `*not shown*` | ✗ |
| `ret` | `any` | let/var | `*not shown*` | ✗ |
| `foundOne` | `any` | let/var | `*not shown*` | ✗ |
| `self` | `any` | let/var | `*not shown*` | ✗ |
| `parsed` | `any` | let/var | `*not shown*` | ✗ |
| `comment` | `any` | let/var | `comments[i]` | ✗ |
| `decl` | `RegExp` | let/var | `/(?:\n\|\$\|\*)\s*@(type\|param\|arg(?:ument)?\|returns?\|this)\s+(.*)/g` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `argname` | `string` | let/var | `name[2] + (parsed.isOptional \|\| (name[1] === '[' && name[3] === ']') ? "?" ...` | ✗ |
| `re` | `RegExp` | let/var | `/\s@typedef\s+(.*)/g` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `name` | `RegExpMatchArray` | let/var | `parsed && m[1].slice(parsed.end).match(/^\s*(\S+)/)` | ✗ |
| `weight` | `any` | let/var | `infer.cx().parent._docComment.weight` | ✗ |
| `fn` | `any` | let/var | `*not shown*` | ✗ |
| `decl` | `any` | let/var | `node.declarations[0]` | ✗ |
| `name` | `any` | let/var | `fn.argNames[i]` | ✗ |
| `known` | `any` | let/var | `args[name]` | ✗ |


---

## Functions

### `postParse(ast: any, text: any): void`

**Parameters:**

- **`ast`** `any`
- **`text`** `any`

**Returns:** `void`

**Calls:**

- `comment.ensureCommentsBefore`
- `walk.simple`
- `attachComments`
- `isDefinePropertyCall`

<details><summary>Code</summary>

```typescript
function postParse(ast, text) {
    function attachComments(node) { comment.ensureCommentsBefore(text, node); }

    walk.simple(ast, {
      VariableDeclaration: attachComments,
      FunctionDeclaration: attachComments,
      AssignmentExpression: function(node) {
        if (node.operator == "=") attachComments(node);
      },
      ObjectExpression: function(node) {
        for (var i = 0; i < node.properties.length; ++i)
          attachComments(node.properties[i]);
      },
      CallExpression: function(node) {
        if (isDefinePropertyCall(node)) attachComments(node);
      }
    });
  }
```
</details>

### `attachComments(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `comment.ensureCommentsBefore`

<details><summary>Code</summary>

```typescript
function attachComments(node) { comment.ensureCommentsBefore(text, node); }
```
</details>

### `AssignmentExpression(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `attachComments`

<details><summary>Code</summary>

```typescript
function(node) {
        if (node.operator == "=") attachComments(node);
      }
```
</details>

### `ObjectExpression(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `attachComments`

<details><summary>Code</summary>

```typescript
function(node) {
        for (var i = 0; i < node.properties.length; ++i)
          attachComments(node.properties[i]);
      }
```
</details>

### `CallExpression(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `isDefinePropertyCall`
- `attachComments`

<details><summary>Code</summary>

```typescript
function(node) {
        if (isDefinePropertyCall(node)) attachComments(node);
      }
```
</details>

### `AssignmentExpression(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `attachComments`

<details><summary>Code</summary>

```typescript
function(node) {
        if (node.operator == "=") attachComments(node);
      }
```
</details>

### `ObjectExpression(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `attachComments`

<details><summary>Code</summary>

```typescript
function(node) {
        for (var i = 0; i < node.properties.length; ++i)
          attachComments(node.properties[i]);
      }
```
</details>

### `CallExpression(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `isDefinePropertyCall`
- `attachComments`

<details><summary>Code</summary>

```typescript
function(node) {
        if (isDefinePropertyCall(node)) attachComments(node);
      }
```
</details>

### `isDefinePropertyCall(node: any): boolean`

**Parameters:**

- **`node`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isDefinePropertyCall(node) {
    return node.callee.type == "MemberExpression" &&
      node.callee.object.name == "Object" &&
      node.callee.property.name == "defineProperty" &&
      node.arguments.length >= 3 &&
      typeof node.arguments[1].value == "string";
  }
```
</details>

### `postInfer(ast: any, scope: any): void`

**Parameters:**

- **`ast`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `jsdocParseTypedefs`
- `walk.simple`
- `interpretComments`
- `scope.getProp`
- `infer.expressionType`
- `node.objType.getProp`
- `isDefinePropertyCall`
- `infer.expressionType({node: node.arguments[0], state: scope}).getObjType`

<details><summary>Code</summary>

```typescript
function postInfer(ast, scope) {
    jsdocParseTypedefs(ast.sourceFile.text, scope);

    walk.simple(ast, {
      VariableDeclaration: function(node, scope) {
        if (node.commentsBefore)
          interpretComments(node, node.commentsBefore, scope,
                            scope.getProp(node.declarations[0].id.name));
      },
      FunctionDeclaration: function(node, scope) {
        if (node.commentsBefore)
          interpretComments(node, node.commentsBefore, scope,
                            scope.getProp(node.id.name),
                            node.body.scope.fnType);
      },
      AssignmentExpression: function(node, scope) {
        if (node.commentsBefore)
          interpretComments(node, node.commentsBefore, scope,
                            infer.expressionType({node: node.left, state: scope}));
      },
      ObjectExpression: function(node, scope) {
        for (var i = 0; i < node.properties.length; ++i) {
          var prop = node.properties[i];
          if (prop.commentsBefore)
            interpretComments(prop, prop.commentsBefore, scope,
                              node.objType.getProp(prop.key.name));
        }
      },
      CallExpression: function(node, scope) {
        if (node.commentsBefore && isDefinePropertyCall(node)) {
          var type = infer.expressionType({node: node.arguments[0], state: scope}).getObjType();
          if (type && type instanceof infer.Obj) {
            var prop = type.props[node.arguments[1].value];
            if (prop) interpretComments(node, node.commentsBefore, scope, prop);
          }
        }
      }
    }, infer.searchVisitor, scope);
  }
```
</details>

### `VariableDeclaration(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `interpretComments`
- `scope.getProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.commentsBefore)
          interpretComments(node, node.commentsBefore, scope,
                            scope.getProp(node.declarations[0].id.name));
      }
```
</details>

### `FunctionDeclaration(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `interpretComments`
- `scope.getProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.commentsBefore)
          interpretComments(node, node.commentsBefore, scope,
                            scope.getProp(node.id.name),
                            node.body.scope.fnType);
      }
```
</details>

### `AssignmentExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `interpretComments`
- `infer.expressionType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.commentsBefore)
          interpretComments(node, node.commentsBefore, scope,
                            infer.expressionType({node: node.left, state: scope}));
      }
```
</details>

### `ObjectExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `interpretComments`
- `node.objType.getProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        for (var i = 0; i < node.properties.length; ++i) {
          var prop = node.properties[i];
          if (prop.commentsBefore)
            interpretComments(prop, prop.commentsBefore, scope,
                              node.objType.getProp(prop.key.name));
        }
      }
```
</details>

### `CallExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `isDefinePropertyCall`
- `infer.expressionType({node: node.arguments[0], state: scope}).getObjType`
- `interpretComments`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.commentsBefore && isDefinePropertyCall(node)) {
          var type = infer.expressionType({node: node.arguments[0], state: scope}).getObjType();
          if (type && type instanceof infer.Obj) {
            var prop = type.props[node.arguments[1].value];
            if (prop) interpretComments(node, node.commentsBefore, scope, prop);
          }
        }
      }
```
</details>

### `VariableDeclaration(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `interpretComments`
- `scope.getProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.commentsBefore)
          interpretComments(node, node.commentsBefore, scope,
                            scope.getProp(node.declarations[0].id.name));
      }
```
</details>

### `FunctionDeclaration(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `interpretComments`
- `scope.getProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.commentsBefore)
          interpretComments(node, node.commentsBefore, scope,
                            scope.getProp(node.id.name),
                            node.body.scope.fnType);
      }
```
</details>

### `AssignmentExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `interpretComments`
- `infer.expressionType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.commentsBefore)
          interpretComments(node, node.commentsBefore, scope,
                            infer.expressionType({node: node.left, state: scope}));
      }
```
</details>

### `ObjectExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `interpretComments`
- `node.objType.getProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        for (var i = 0; i < node.properties.length; ++i) {
          var prop = node.properties[i];
          if (prop.commentsBefore)
            interpretComments(prop, prop.commentsBefore, scope,
                              node.objType.getProp(prop.key.name));
        }
      }
```
</details>

### `CallExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `isDefinePropertyCall`
- `infer.expressionType({node: node.arguments[0], state: scope}).getObjType`
- `interpretComments`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.commentsBefore && isDefinePropertyCall(node)) {
          var type = infer.expressionType({node: node.arguments[0], state: scope}).getObjType();
          if (type && type instanceof infer.Obj) {
            var prop = type.props[node.arguments[1].value];
            if (prop) interpretComments(node, node.commentsBefore, scope, prop);
          }
        }
      }
```
</details>

### `postLoadDef(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `infer.cx`
- `maybeInstance`
- `infer.def.parse`

<details><summary>Code</summary>

```typescript
function postLoadDef(data) {
    var defs = data["!typedef"];
    var cx = infer.cx(), orig = data["!name"];
    if (defs) for (var name in defs)
      cx.parent.jsdocTypedefs[name] =
        maybeInstance(infer.def.parse(defs[name], orig, name), name);
  }
```
</details>

### `interpretComments(node: any, comments: any, scope: any, aval: any, type: any): void`

**Parameters:**

- **`node`** `any`
- **`comments`** `any`
- **`scope`** `any`
- **`aval`** `any`
- **`type`** `any`

**Returns:** `void`

**Calls:**

- `jsdocInterpretComments`
- `infer.cx`
- `result.trim().replace`
- `result.search`
- `result.slice`
- `result.replace`

<details><summary>Code</summary>

```typescript
function interpretComments(node, comments, scope, aval, type) {
    jsdocInterpretComments(node, scope, aval, comments);
    var cx = infer.cx();

    if (!type && aval instanceof infer.AVal && aval.types.length) {
      type = aval.types[aval.types.length - 1];
      if (!(type instanceof infer.Obj) || type.origin != cx.curOrigin || type.doc)
        type = null;
    }

    var result = comments[comments.length - 1];
    if (cx.parent._docComment.fullDocs) {
      result = result.trim().replace(/\n[ \t]*\* ?/g, "\n");
    } else {
      var dot = result.search(/\.\s/);
      if (dot > 5) result = result.slice(0, dot + 1);
      result = result.trim().replace(/\s*\n\s*\*\s*|\s{1,}/g, " ");
    }
    result = result.replace(/^\s*\*+\s*/, "");

    if (aval instanceof infer.AVal) aval.doc = result;
    if (type) type.doc = result;
  }
```
</details>

### `skipSpace(str: any, pos: any): any`

**Parameters:**

- **`str`** `any`
- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `/\s/.test`
- `str.charAt`

<details><summary>Code</summary>

```typescript
function skipSpace(str, pos) {
    while (/\s/.test(str.charAt(pos))) ++pos;
    return pos;
  }
```
</details>

### `isIdentifier(string: any): boolean`

**Parameters:**

- **`string`** `any`

**Returns:** `boolean`

**Calls:**

- `acorn.isIdentifierStart`
- `string.charCodeAt`
- `acorn.isIdentifierChar`

<details><summary>Code</summary>

```typescript
function isIdentifier(string) {
    if (!acorn.isIdentifierStart(string.charCodeAt(0))) return false;
    for (var i = 1; i < string.length; i++)
      if (!acorn.isIdentifierChar(string.charCodeAt(i))) return false;
    return true;
  }
```
</details>

### `parseLabelList(scope: any, str: any, pos: any, close: any): any`

**Parameters:**

- **`scope`** `any`
- **`str`** `any`
- **`pos`** `any`
- **`close`** `any`

**Returns:** `any`

**Calls:**

- `skipSpace`
- `str.charAt`
- `str.indexOf`
- `str.slice`
- `isIdentifier`
- `labels.push`
- `parseType`
- `types.push`

<details><summary>Code</summary>

```typescript
function parseLabelList(scope, str, pos, close) {
    var labels = [], types = [], madeUp = false;
    for (var first = true; ; first = false) {
      pos = skipSpace(str, pos);
      if (first && str.charAt(pos) == close) break;
      var colon = str.indexOf(":", pos);
      if (colon < 0) return null;
      var label = str.slice(pos, colon);
      if (!isIdentifier(label)) return null;
      labels.push(label);
      pos = colon + 1;
      var type = parseType(scope, str, pos);
      if (!type) return null;
      pos = type.end;
      madeUp = madeUp || type.madeUp;
      types.push(type.type);
      pos = skipSpace(str, pos);
      var next = str.charAt(pos);
      ++pos;
      if (next == close) break;
      if (next != ",") return null;
    }
    return {labels: labels, types: types, end: pos, madeUp: madeUp};
  }
```
</details>

### `parseType(scope: any, str: any, pos: any): any`

**Parameters:**

- **`scope`** `any`
- **`str`** `any`
- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `parseTypeInner`
- `inner.type.propagate`
- `skipSpace`
- `str.charAt`
- `type.propagate`

<details><summary>Code</summary>

```typescript
function parseType(scope, str, pos) {
    var type, union = false, madeUp = false;
    for (;;) {
      var inner = parseTypeInner(scope, str, pos);
      if (!inner) return null;
      madeUp = madeUp || inner.madeUp;
      if (union) inner.type.propagate(union);
      else type = inner.type;
      pos = skipSpace(str, inner.end);
      if (str.charAt(pos) != "|") break;
      pos++;
      if (!union) {
        union = new infer.AVal;
        type.propagate(union);
        type = union;
      }
    }
    var isOptional = false;
    if (str.charAt(pos) == "=") {
      ++pos;
      isOptional = true;
    }
    return {type: type, end: pos, isOptional: isOptional, madeUp: madeUp};
  }
```
</details>

### `parseTypeInner(scope: any, str: any, pos: any): any`

**Parameters:**

- **`scope`** `any`
- **`str`** `any`
- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `skipSpace`
- `str.indexOf`
- `parseLabelList`
- `str.charAt`
- `parseType`
- `type.defProp`
- `fields.types[i].propagate`
- `acorn.isIdentifierStart`
- `str.charCodeAt`
- `acorn.isIdentifierChar`
- `str.slice`
- `/^(number|integer)$/i.test`
- `infer.cx`
- `/^bool(ean)?$/i.test`
- `/^string$/i.test`
- `/^(null|undefined)$/i.test`
- `/^array$/i.test`
- `/^object$/i.test`
- `val.type.propagate`
- `infer.def.parsePath(path, scope).getObjType`
- `maybeInstance`
- `Object.create`

<details><summary>Code</summary>

```typescript
function parseTypeInner(scope, str, pos) {
    pos = skipSpace(str, pos);
    var type, madeUp = false;

    if (str.indexOf("function(", pos) == pos) {
      var args = parseLabelList(scope, str, pos + 9, ")"), ret = infer.ANull;
      if (!args) return null;
      pos = skipSpace(str, args.end);
      if (str.charAt(pos) == ":") {
        ++pos;
        var retType = parseType(scope, str, pos + 1);
        if (!retType) return null;
        pos = retType.end;
        ret = retType.type;
        madeUp = retType.madeUp;
      }
      type = new infer.Fn(null, infer.ANull, args.types, args.labels, ret);
    } else if (str.charAt(pos) == "[") {
      var inner = parseType(scope, str, pos + 1);
      if (!inner) return null;
      pos = skipSpace(str, inner.end);
      madeUp = inner.madeUp;
      if (str.charAt(pos) != "]") return null;
      ++pos;
      type = new infer.Arr(inner.type);
    } else if (str.charAt(pos) == "{") {
      var fields = parseLabelList(scope, str, pos + 1, "}");
      if (!fields) return null;
      type = new infer.Obj(true);
      for (var i = 0; i < fields.types.length; ++i) {
        var field = type.defProp(fields.labels[i]);
        field.initializer = true;
        fields.types[i].propagate(field);
      }
      pos = fields.end;
      madeUp = fields.madeUp;
    } else if (str.charAt(pos) == "(") {
      var inner = parseType(scope, str, pos + 1);
      if (!inner) return null;
      pos = skipSpace(str, inner.end);
      if (str.charAt(pos) != ")") return null;
      ++pos;
      type = inner.type;
    } else {
      var start = pos;
      if (!acorn.isIdentifierStart(str.charCodeAt(pos))) return null;
      while (acorn.isIdentifierChar(str.charCodeAt(pos))) ++pos;
      if (start == pos) return null;
      var word = str.slice(start, pos);
      if (/^(number|integer)$/i.test(word)) type = infer.cx().num;
      else if (/^bool(ean)?$/i.test(word)) type = infer.cx().bool;
      else if (/^string$/i.test(word)) type = infer.cx().str;
      else if (/^(null|undefined)$/i.test(word)) type = infer.ANull;
      else if (/^array$/i.test(word)) {
        var inner = null;
        if (str.charAt(pos) == "." && str.charAt(pos + 1) == "<") {
          var inAngles = parseType(scope, str, pos + 2);
          if (!inAngles) return null;
          pos = skipSpace(str, inAngles.end);
          madeUp = inAngles.madeUp;
          if (str.charAt(pos++) != ">") return null;
          inner = inAngles.type;
        }
        type = new infer.Arr(inner);
      } else if (/^object$/i.test(word)) {
        type = new infer.Obj(true);
        if (str.charAt(pos) == "." && str.charAt(pos + 1) == "<") {
          var key = parseType(scope, str, pos + 2);
          if (!key) return null;
          pos = skipSpace(str, key.end);
          if (str.charAt(pos++) != ",") return null;
          var val = parseType(scope, str, pos);
          if (!val) return null;
          pos = skipSpace(str, val.end);
          madeUp = key.madeUp || val.madeUp;
          if (str.charAt(pos++) != ">") return null;
          val.type.propagate(type.defProp("<i>"));
        }
      } else {
        while (str.charCodeAt(pos) == 46 ||
               acorn.isIdentifierChar(str.charCodeAt(pos))) ++pos;
        var path = str.slice(start, pos);
        var cx = infer.cx(), defs = cx.parent && cx.parent.jsdocTypedefs, found;
        if (defs && (path in defs)) {
          type = defs[path];
        } else if (found = infer.def.parsePath(path, scope).getObjType()) {
          type = maybeInstance(found, path);
        } else {
          if (!cx.jsdocPlaceholders) cx.jsdocPlaceholders = Object.create(null);
          if (!(path in cx.jsdocPlaceholders))
            type = cx.jsdocPlaceholders[path] = new infer.Obj(null, path);
          else
            type = cx.jsdocPlaceholders[path];
          madeUp = true;
        }
      }
    }

    return {type: type, end: pos, madeUp: madeUp};
  }
```
</details>

### `maybeInstance(type: any, path: any): any`

**Parameters:**

- **`type`** `any`
- **`path`** `any`

**Returns:** `any`

**Calls:**

- `/^[A-Z]/.test`
- `type.getProp("prototype").getObjType`
- `infer.getInstance`

<details><summary>Code</summary>

```typescript
function maybeInstance(type, path) {
    if (type instanceof infer.Fn && /^[A-Z]/.test(path)) {
      var proto = type.getProp("prototype").getObjType();
      if (proto instanceof infer.Obj) return infer.getInstance(proto);
    }
    return type;
  }
```
</details>

### `parseTypeOuter(scope: any, str: any, pos: any): any`

**Parameters:**

- **`scope`** `any`
- **`str`** `any`
- **`pos`** `any`

**Returns:** `any`

**Calls:**

- `skipSpace`
- `str.charAt`
- `parseType`

<details><summary>Code</summary>

```typescript
function parseTypeOuter(scope, str, pos) {
    pos = skipSpace(str, pos || 0);
    if (str.charAt(pos) != "{") return null;
    var result = parseType(scope, str, pos + 1);
    if (!result) return null;
    var end = skipSpace(str, result.end);
    if (str.charAt(end) != "}") return null;
    result.end = end + 1;
    return result;
  }
```
</details>

### `jsdocInterpretComments(node: any, scope: any, aval: any, comments: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`aval`** `any`
- **`comments`** `any`

**Returns:** `void`

**Calls:**

- `decl.exec`
- `parseType`
- `parseTypeOuter`
- `m[2].slice(parsed.end).match`
- `Object.create`
- `applyType`

<details><summary>Code</summary>

```typescript
function jsdocInterpretComments(node, scope, aval, comments) {
    var type, args, ret, foundOne, self, parsed;

    for (var i = 0; i < comments.length; ++i) {
      var comment = comments[i];
      var decl = /(?:\n|\$|\*)\s*@(type|param|arg(?:ument)?|returns?|this)\s+(.*)/g, m;
      while (m = decl.exec(comment)) {
        if (m[1] == "this" && (parsed = parseType(scope, m[2], 0))) {
          self = parsed;
          foundOne = true;
          continue;
        }

        if (!(parsed = parseTypeOuter(scope, m[2]))) continue;
        foundOne = true;

        switch(m[1]) {
        case "returns": case "return":
          ret = parsed; break;
        case "type":
          type = parsed; break;
        case "param": case "arg": case "argument":
            var name = m[2].slice(parsed.end).match(/^\s*(\[?)\s*([^\]\s=]+)\s*(?:=[^\]]+\s*)?(\]?).*/);
            if (!name) continue;
            var argname = name[2] + (parsed.isOptional || (name[1] === '[' && name[3] === ']') ? "?" : "");
          (args || (args = Object.create(null)))[argname] = parsed;
          break;
        }
      }
    }

    if (foundOne) applyType(type, self, args, ret, node, aval);
  }
```
</details>

### `jsdocParseTypedefs(text: any, scope: any): void`

**Parameters:**

- **`text`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `infer.cx`
- `re.exec`
- `parseTypeOuter`
- `m[1].slice(parsed.end).match`

<details><summary>Code</summary>

```typescript
function jsdocParseTypedefs(text, scope) {
    var cx = infer.cx();

    var re = /\s@typedef\s+(.*)/g, m;
    while (m = re.exec(text)) {
      var parsed = parseTypeOuter(scope, m[1]);
      var name = parsed && m[1].slice(parsed.end).match(/^\s*(\S+)/);
      if (name)
        cx.parent.jsdocTypedefs[name[1]] = parsed.type;
    }
  }
```
</details>

### `propagateWithWeight(type: any, target: any): void`

**Parameters:**

- **`type`** `any`
- **`target`** `any`

**Returns:** `void`

**Calls:**

- `infer.cx`
- `type.type.propagate`

<details><summary>Code</summary>

```typescript
function propagateWithWeight(type, target) {
    var weight = infer.cx().parent._docComment.weight;
    type.type.propagate(target, weight || (type.madeUp ? WG_MADEUP : undefined));
  }
```
</details>

### `applyType(type: any, self: any, args: any, ret: any, node: any, aval: any): void`

**Parameters:**

- **`type`** `any`
- **`self`** `any`
- **`args`** `any`
- **`ret`** `any`
- **`node`** `any`
- **`aval`** `any`

**Returns:** `void`

**Calls:**

- `propagateWithWeight`

<details><summary>Code</summary>

```typescript
function applyType(type, self, args, ret, node, aval) {
    var fn;
    if (node.type == "VariableDeclaration") {
      var decl = node.declarations[0];
      if (decl.init && decl.init.type == "FunctionExpression") fn = decl.init.body.scope.fnType;
    } else if (node.type == "FunctionDeclaration") {
      fn = node.body.scope.fnType;
    } else if (node.type == "AssignmentExpression") {
      if (node.right.type == "FunctionExpression")
        fn = node.right.body.scope.fnType;
    } else if (node.type == "CallExpression") {
    } else { // An object property
      if (node.value.type == "FunctionExpression") fn = node.value.body.scope.fnType;
    }

    if (fn && (args || ret || self)) {
      if (args) for (var i = 0; i < fn.argNames.length; ++i) {
        var name = fn.argNames[i], known = args[name];
        if (!known && (known = args[name + "?"]))
          fn.argNames[i] += "?";
        if (known) propagateWithWeight(known, fn.args[i]);
      }
      if (ret) propagateWithWeight(ret, fn.retval);
      if (self) propagateWithWeight(self, fn.self);
    } else if (type) {
      propagateWithWeight(type, aval);
    }
  }
```
</details>


---