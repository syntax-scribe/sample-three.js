[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `tern.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 67 |
| 📊 Variables & Constants | 97 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/ternjs/tern.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `defaultOptions` | `{ debug: boolean; async: boolean; get...` | let/var | `exports.defaultOptions = { debug: false, async: false, getFile: function(_f, ...` | ✗ |
| `queryTypes` | `{ completions: { takesFile: boolean; ...` | let/var | `{ completions: { takesFile: true, run: findCompletions }, properties: { run: ...` | ✗ |
| `Server` | `typeof Server` | let/var | `exports.Server = function(options) { this.cx = null; this.options = options \...` | ✗ |
| `file` | `any` | let/var | `this.files[i]` | ✗ |
| `self` | `any` | let/var | `this` | ✗ |
| `cx` | `any` | let/var | `this.cx` | ✗ |
| `query` | `any` | let/var | `doc.query` | ✗ |
| `files` | `any` | let/var | `doc.files \|\| []` | ✗ |
| `file` | `any` | let/var | `files[i]` | ✗ |
| `timeBudget` | `any[]` | let/var | `typeof doc.timeout == "number" ? [doc.timeout] : null` | ✗ |
| `queryType` | `any` | let/var | `queryTypes[query.type]` | ✗ |
| `file` | `any` | let/var | `queryType.takesFile && resolveFile(srv, files, query.file)` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `file` | `File` | let/var | `new File(name, parent)` | ✗ |
| `done` | `boolean` | let/var | `true` | ✗ |
| `returned` | `boolean` | let/var | `false` | ✗ |
| `e` | `any` | let/var | `srv.fetchError` | ✗ |
| `done` | `boolean` | let/var | `true` | ✗ |
| `toAnalyze` | `any[]` | let/var | `[]` | ✗ |
| `file` | `any` | let/var | `srv.files[i]` | ✗ |
| `startTime` | `number` | let/var | `+new Date` | ✗ |
| `closest` | `any` | let/var | `null` | ✗ |
| `err` | `Error` | let/var | `new Error(msg)` | ✗ |
| `file` | `any` | let/var | `localFiles[isRef[1]]` | ✗ |
| `realFile` | `any` | let/var | `file.backing = srv.findFile(file.name)` | ✗ |
| `offset` | `any` | let/var | `*not shown*` | ✗ |
| `pos` | `any` | let/var | `foundPos == null ? Math.max(0, realFile.text.lastIndexOf("\n", offset)) : fou...` | ✗ |
| `inObject` | `any` | let/var | `*not shown*` | ✗ |
| `atFunction` | `any` | let/var | `*not shown*` | ✗ |
| `text` | `any` | let/var | `file.text` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `cut` | `any` | let/var | `m[1].length` | ✗ |
| `white` | `string` | let/var | `""` | ✗ |
| `scope` | `any` | let/var | `file.scope = scopeDepth(scopeStart) < scopeDepth(scopeEnd) ? scopeEnd : scope...` | ✗ |
| `fOld` | `any` | let/var | `inner.fnType` | ✗ |
| `fNew` | `any` | let/var | `newInner.fnType` | ✗ |
| `size` | `number` | let/var | `0` | ✗ |
| `depth` | `number` | let/var | `0` | ✗ |
| `known` | `any` | let/var | `srv.budgets[bName]` | ✗ |
| `file` | `any` | let/var | `doc.files[i]` | ✗ |
| `offsetSkipLines` | `number` | let/var | `25` | ✗ |
| `text` | `any` | let/var | `file.text` | ✗ |
| `offsets` | `any` | let/var | `file.lineOffsets \|\| (file.lineOffsets = [0])` | ✗ |
| `pos` | `number` | let/var | `0` | ✗ |
| `curLine` | `number` | let/var | `0` | ✗ |
| `resolvePos` | `(file: any, pos: any, tolerant: any) ...` | let/var | `exports.resolvePos = function(file, pos, tolerant) { if (typeof pos != "numbe...` | ✗ |
| `offsets` | `any` | let/var | `file.lineOffsets \|\| (file.lineOffsets = [0])` | ✗ |
| `text` | `any` | let/var | `file.text` | ✗ |
| `line` | `any` | let/var | `*not shown*` | ✗ |
| `lineStart` | `any` | let/var | `*not shown*` | ✗ |
| `outputPos` | `(query: any, file: any, pos: any) => any` | let/var | `exports.outputPos = function(query, file, pos) { if (query.lineCharPositions)...` | ✗ |
| `curProp` | `any` | let/var | `objNode.properties[i]` | ✗ |
| `wordEnd` | `any` | let/var | `wordStart` | ✗ |
| `text` | `any` | let/var | `file.text` | ✗ |
| `completions` | `any[]` | let/var | `[]` | ✗ |
| `ignoreObj` | `any` | let/var | `*not shown*` | ✗ |
| `wrapAsObjs` | `any` | let/var | `query.types \|\| query.depths \|\| query.docs \|\| query.urls \|\| query.origins` | ✗ |
| `c` | `any` | let/var | `completions[i]` | ✗ |
| `rec` | `any` | let/var | `wrapAsObjs ? {name: prop} : prop` | ✗ |
| `val` | `any` | let/var | `obj.props[prop]` | ✗ |
| `hookname` | `any` | let/var | `*not shown*` | ✗ |
| `prop` | `any` | let/var | `*not shown*` | ✗ |
| `objType` | `any` | let/var | `*not shown*` | ✗ |
| `isKey` | `any` | let/var | `*not shown*` | ✗ |
| `memberExpr` | `any` | let/var | `*not shown*` | ✗ |
| `objLit` | `any` | let/var | `*not shown*` | ✗ |
| `pathStart` | `number` | let/var | `wordStart - 1` | ✗ |
| `prefix` | `any` | let/var | `query.prefix` | ✗ |
| `found` | `any[]` | let/var | `[]` | ✗ |
| `start` | `any` | let/var | `query.start && resolvePos(file, query.start)` | ✗ |
| `findExpr` | `(file: any, query: any, wide: any) =>...` | let/var | `exports.findQueryExpr = function(file, query, wide) { if (query.end == null) ...` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `objProp` | `any` | let/var | `*not shown*` | ✗ |
| `name` | `any` | let/var | `objProp.key.name` | ✗ |
| `exprName` | `any` | let/var | `*not shown*` | ✗ |
| `exprType` | `any` | let/var | `type` | ✗ |
| `result` | `{ guess: any; type: any; name: any; e...` | let/var | `{guess: infer.didGuess(), type: infer.toString(exprType, query.depth), name: ...` | ✗ |
| `result` | `{ url: any; doc: any; type: any; }` | let/var | `{url: type.url, doc: type.doc, type: infer.toString(type)}` | ✗ |
| `ctor` | `any` | let/var | `*not shown*` | ✗ |
| `boring` | `any` | let/var | `infer.cx().protos` | ✗ |
| `node` | `any` | let/var | `obj.originNode` | ✗ |
| `getSpan` | `(obj: any) => { origin: any; node: an...` | let/var | `exports.getSpan = function(obj) { if (!obj.origin) return; if (obj.originNode...` | ✗ |
| `storeSpan` | `(srv: any, query: any, span: any, tar...` | let/var | `exports.storeSpan = function(srv, query, span, target) { target.origin = span...` | ✗ |
| `result` | `{ url: any; doc: any; origin: any; }` | let/var | `{url: type.url, doc: type.doc, origin: type.origin}` | ✗ |
| `tp` | `any` | let/var | `type.types[i]` | ✗ |
| `spanFile` | `any` | let/var | `span.node.sourceFile \|\| srv.findFile(span.origin)` | ✗ |
| `name` | `any` | let/var | `expr.node.name` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `refs` | `any[]` | let/var | `[]` | ✗ |
| `cur` | `any` | let/var | `srv.files[i]` | ✗ |
| `refs` | `any[]` | let/var | `[]` | ✗ |
| `cur` | `any` | let/var | `srv.files[i]` | ✗ |
| `p` | `any` | let/var | `expr.node.property` | ✗ |
| `k` | `any` | let/var | `expr.node.properties[i].key` | ✗ |
| `refs` | `any[]` | let/var | `data.refs` | ✗ |
| `changes` | `any[]` | let/var | `data.changes = []` | ✗ |
| `use` | `any` | let/var | `refs[i]` | ✗ |


---

## Functions

### `getFile(_f: any, c: any): void`

**Parameters:**

- **`_f`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(_f, c) { if (this.async) c(null, null); }
```
</details>

### `getFile(_f: any, c: any): void`

**Parameters:**

- **`_f`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(_f, c) { if (this.async) c(null, null); }
```
</details>

### `getFile(_f: any, c: any): void`

**Parameters:**

- **`_f`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(_f, c) { if (this.async) c(null, null); }
```
</details>

### `getFile(_f: any, c: any): void`

**Parameters:**

- **`_f`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(_f, c) { if (this.async) c(null, null); }
```
</details>

### `File(name: any, parent: any): void`

**Parameters:**

- **`name`** `any`
- **`parent`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function File(name, parent) {
    this.name = name;
    this.parent = parent;
    this.scope = this.text = this.ast = this.lineOffsets = null;
  }
```
</details>

### `updateText(file: any, text: any, srv: any): void`

**Parameters:**

- **`file`** `any`
- **`text`** `any`
- **`srv`** `any`

**Returns:** `void`

**Calls:**

- `text.replace`
- `infer.withContext`
- `infer.parse`

<details><summary>Code</summary>

```typescript
function updateText(file, text, srv) {
    file.text = srv.options.stripCRs ? text.replace(/\r\n/g, "\n") : text;
    infer.withContext(srv.cx, function() {
      file.ast = infer.parse(file.text, srv.passes, {directSourceFile: file, allowReturnOutsideFunction: true});
    });
    file.lineOffsets = null;
  }
```
</details>

### `addFile(name: any, text: any, parent: any): void`

**Parameters:**

- **`name`** `any`
- **`text`** `any`
- **`parent`** `any`

**Returns:** `void`

**Calls:**

- `ensureFile`

**Internal Comments:**
```
// Don't crash when sloppy plugins pass non-existent parent ids
```

<details><summary>Code</summary>

```typescript
function(name, /*optional*/ text, parent) {
      // Don't crash when sloppy plugins pass non-existent parent ids
      if (parent && !(parent in this.fileMap)) parent = null;
      ensureFile(this, name, parent, text);
    }
```
</details>

### `delFile(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.findFile`
- `this.needsPurge.push`
- `this.files.splice`
- `this.files.indexOf`

<details><summary>Code</summary>

```typescript
function(name) {
      var file = this.findFile(name);
      if (file) {
        this.needsPurge.push(file.name);
        this.files.splice(this.files.indexOf(file), 1);
        delete this.fileMap[name];
      }
    }
```
</details>

### `reset(): void`

**Returns:** `void`

**Calls:**

- `this.signal`
- `Object.create`

<details><summary>Code</summary>

```typescript
function() {
      this.signal("reset");
      this.cx = new infer.Context(this.defs, this);
      this.uses = 0;
      this.budgets = Object.create(null);
      for (var i = 0; i < this.files.length; ++i) {
        var file = this.files[i];
        file.scope = null;
      }
    }
```
</details>

### `request(doc: any, c: any): any`

**Parameters:**

- **`doc`** `any`
- **`c`** `any`

**Returns:** `any`

**Calls:**

- `invalidDoc`
- `c`
- `doRequest`
- `self.reset`
- `analyzeAll`

<details><summary>Code</summary>

```typescript
function(doc, c) {
      var inv = invalidDoc(doc);
      if (inv) return c(inv);

      var self = this;
      doRequest(this, doc, function(err, data) {
        c(err, data);
        if (self.uses > 40) {
          self.reset();
          analyzeAll(self, null, function(){});
        }
      });
    }
```
</details>

### `findFile(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(name) {
      return this.fileMap[name];
    }
```
</details>

### `flush(c: any): void`

**Parameters:**

- **`c`** `any`

**Returns:** `void`

**Calls:**

- `analyzeAll`
- `c`
- `infer.withContext`

<details><summary>Code</summary>

```typescript
function(c) {
      var cx = this.cx;
      analyzeAll(this, null, function(err) {
        if (err) return c(err);
        infer.withContext(cx, c);
      });
    }
```
</details>

### `startAsyncAction(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {
      ++this.pending;
    }
```
</details>

### `finishAsyncAction(err: any): void`

**Parameters:**

- **`err`** `any`

**Returns:** `void`

**Calls:**

- `this.signal`

<details><summary>Code</summary>

```typescript
function(err) {
      if (err) this.asyncError = err;
      if (--this.pending === 0) this.signal("everythingFetched");
    }
```
</details>

### `addFile(name: any, text: any, parent: any): void`

**Parameters:**

- **`name`** `any`
- **`text`** `any`
- **`parent`** `any`

**Returns:** `void`

**Calls:**

- `ensureFile`

**Internal Comments:**
```
// Don't crash when sloppy plugins pass non-existent parent ids
```

<details><summary>Code</summary>

```typescript
function(name, /*optional*/ text, parent) {
      // Don't crash when sloppy plugins pass non-existent parent ids
      if (parent && !(parent in this.fileMap)) parent = null;
      ensureFile(this, name, parent, text);
    }
```
</details>

### `delFile(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.findFile`
- `this.needsPurge.push`
- `this.files.splice`
- `this.files.indexOf`

<details><summary>Code</summary>

```typescript
function(name) {
      var file = this.findFile(name);
      if (file) {
        this.needsPurge.push(file.name);
        this.files.splice(this.files.indexOf(file), 1);
        delete this.fileMap[name];
      }
    }
```
</details>

### `reset(): void`

**Returns:** `void`

**Calls:**

- `this.signal`
- `Object.create`

<details><summary>Code</summary>

```typescript
function() {
      this.signal("reset");
      this.cx = new infer.Context(this.defs, this);
      this.uses = 0;
      this.budgets = Object.create(null);
      for (var i = 0; i < this.files.length; ++i) {
        var file = this.files[i];
        file.scope = null;
      }
    }
```
</details>

### `request(doc: any, c: any): any`

**Parameters:**

- **`doc`** `any`
- **`c`** `any`

**Returns:** `any`

**Calls:**

- `invalidDoc`
- `c`
- `doRequest`
- `self.reset`
- `analyzeAll`

<details><summary>Code</summary>

```typescript
function(doc, c) {
      var inv = invalidDoc(doc);
      if (inv) return c(inv);

      var self = this;
      doRequest(this, doc, function(err, data) {
        c(err, data);
        if (self.uses > 40) {
          self.reset();
          analyzeAll(self, null, function(){});
        }
      });
    }
```
</details>

### `findFile(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(name) {
      return this.fileMap[name];
    }
```
</details>

### `flush(c: any): void`

**Parameters:**

- **`c`** `any`

**Returns:** `void`

**Calls:**

- `analyzeAll`
- `c`
- `infer.withContext`

<details><summary>Code</summary>

```typescript
function(c) {
      var cx = this.cx;
      analyzeAll(this, null, function(err) {
        if (err) return c(err);
        infer.withContext(cx, c);
      });
    }
```
</details>

### `startAsyncAction(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {
      ++this.pending;
    }
```
</details>

### `finishAsyncAction(err: any): void`

**Parameters:**

- **`err`** `any`

**Returns:** `void`

**Calls:**

- `this.signal`

<details><summary>Code</summary>

```typescript
function(err) {
      if (err) this.asyncError = err;
      if (--this.pending === 0) this.signal("everythingFetched");
    }
```
</details>

### `doRequest(srv: any, doc: any, c: any): any`

**Parameters:**

- **`srv`** `any`
- **`doc`** `any`
- **`c`** `any`

**Returns:** `any`

**Calls:**

- `queryTypes.hasOwnProperty`
- `c`
- `srv.delFile`
- `ensureFile`
- `analyzeAll`
- `/^#/.test`
- `resolveFile`
- `queryType.run`
- `console.error`
- `infer.withContext`
- `infer.withTimeout`

**Internal Comments:**
```
// Respond as soon as possible when this just uploads files
```

<details><summary>Code</summary>

```typescript
function doRequest(srv, doc, c) {
    if (doc.query && !queryTypes.hasOwnProperty(doc.query.type))
      return c("No query type '" + doc.query.type + "' defined");

    var query = doc.query;
    // Respond as soon as possible when this just uploads files
    if (!query) c(null, {});

    var files = doc.files || [];
    if (files.length) ++srv.uses;
    for (var i = 0; i < files.length; ++i) {
      var file = files[i];
      if (file.type == "delete")
        srv.delFile(file.name);
      else
        ensureFile(srv, file.name, null, file.type == "full" ? file.text : null);
    }

    var timeBudget = typeof doc.timeout == "number" ? [doc.timeout] : null;
    if (!query) {
      analyzeAll(srv, timeBudget, function(){});
      return;
    }

    var queryType = queryTypes[query.type];
    if (queryType.takesFile) {
      if (typeof query.file != "string") return c(".query.file must be a string");
      if (!/^#/.test(query.file)) ensureFile(srv, query.file, null);
    }

    analyzeAll(srv, timeBudget, function(err) {
      if (err) return c(err);
      var file = queryType.takesFile && resolveFile(srv, files, query.file);
      if (queryType.fullFile && file.type == "part")
        return c("Can't run a " + query.type + " query on a file fragment");

      function run() {
        var result;
        try {
          result = queryType.run(srv, query, file);
        } catch (e) {
          if (srv.options.debug && e.name != "TernError") console.error(e.stack);
          return c(e);
        }
        c(null, result);
      }
      infer.withContext(srv.cx, timeBudget ? function() { infer.withTimeout(timeBudget[0], run); } : run);
    });
  }
```
</details>

### `run(): any`

**Returns:** `any`

**Calls:**

- `queryType.run`
- `console.error`
- `c`

<details><summary>Code</summary>

```typescript
function run() {
        var result;
        try {
          result = queryType.run(srv, query, file);
        } catch (e) {
          if (srv.options.debug && e.name != "TernError") console.error(e.stack);
          return c(e);
        }
        c(null, result);
      }
```
</details>

### `analyzeFile(srv: any, file: any): any`

**Parameters:**

- **`srv`** `any`
- **`file`** `any`

**Returns:** `any`

**Calls:**

- `infer.withContext`
- `srv.signal`
- `infer.analyze`

<details><summary>Code</summary>

```typescript
function analyzeFile(srv, file) {
    infer.withContext(srv.cx, function() {
      file.scope = srv.cx.topScope;
      srv.signal("beforeLoad", file);
      infer.analyze(file.ast, file.name, file.scope, srv.passes);
      srv.signal("afterLoad", file);
    });
    return file;
  }
```
</details>

### `ensureFile(srv: any, name: any, parent: any, text: any): void`

**Parameters:**

- **`srv`** `any`
- **`name`** `any`
- **`parent`** `any`
- **`text`** `any`

**Returns:** `void`

**Calls:**

- `srv.findFile`
- `srv.needsPurge.push`
- `updateText`
- `parentDepth`
- `srv.files.push`
- `srv.startAsyncAction`
- `srv.options.getFile`
- `srv.finishAsyncAction`

<details><summary>Code</summary>

```typescript
function ensureFile(srv, name, parent, text) {
    var known = srv.findFile(name);
    if (known) {
      if (text != null) {
        if (known.scope) {
          srv.needsPurge.push(name);
          known.scope = null;
        }
        updateText(known, text, srv);
      }
      if (parentDepth(srv, known.parent) > parentDepth(srv, parent)) {
        known.parent = parent;
        if (known.excluded) known.excluded = null;
      }
      return;
    }

    var file = new File(name, parent);
    srv.files.push(file);
    srv.fileMap[name] = file;
    if (text != null) {
      updateText(file, text, srv);
    } else if (srv.options.async) {
      srv.startAsyncAction();
      srv.options.getFile(name, function(err, text) {
        updateText(file, text || "", srv);
        srv.finishAsyncAction(err);
      });
    } else {
      updateText(file, srv.options.getFile(name) || "", srv);
    }
  }
```
</details>

### `fetchAll(srv: any, c: any): void`

**Parameters:**

- **`srv`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `srv.files.forEach`
- `srv.options.getFile`
- `c`
- `updateText`
- `fetchAll`

<details><summary>Code</summary>

```typescript
function fetchAll(srv, c) {
    var done = true, returned = false;
    srv.files.forEach(function(file) {
      if (file.text != null) return;
      if (srv.options.async) {
        done = false;
        srv.options.getFile(file.name, function(err, text) {
          if (err && !returned) { returned = true; return c(err); }
          updateText(file, text || "", srv);
          fetchAll(srv, c);
        });
      } else {
        try {
          updateText(file, srv.options.getFile(file.name) || "", srv);
        } catch (e) { return c(e); }
      }
    });
    if (done) c();
  }
```
</details>

### `waitOnFetch(srv: any, timeBudget: any, c: any): void`

**Parameters:**

- **`srv`** `any`
- **`timeBudget`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `srv.off`
- `clearTimeout`
- `analyzeAll`
- `srv.on`
- `setTimeout`

<details><summary>Code</summary>

```typescript
function waitOnFetch(srv, timeBudget, c) {
    var done = function() {
      srv.off("everythingFetched", done);
      clearTimeout(timeout);
      analyzeAll(srv, timeBudget, c);
    };
    srv.on("everythingFetched", done);
    var timeout = setTimeout(done, srv.options.fetchTimeout);
  }
```
</details>

### `done(): void`

**Returns:** `void`

**Calls:**

- `srv.off`
- `clearTimeout`
- `analyzeAll`

<details><summary>Code</summary>

```typescript
function() {
      srv.off("everythingFetched", done);
      clearTimeout(timeout);
      analyzeAll(srv, timeBudget, c);
    }
```
</details>

### `analyzeAll(srv: any, timeBudget: any, c: any): any`

**Parameters:**

- **`srv`** `any`
- **`timeBudget`** `any`
- **`c`** `any`

**Returns:** `any`

**Calls:**

- `waitOnFetch`
- `c`
- `infer.withContext`
- `infer.purge`
- `toAnalyze.push`
- `toAnalyze.sort`
- `parentDepth`
- `chargeOnBudget`
- `infer.withTimeout`
- `analyzeFile`

**Internal Comments:**
```
// The second inner loop might add new files. The outer loop keeps
// repeating both inner loops until all files have been looked at.
```

<details><summary>Code</summary>

```typescript
function analyzeAll(srv, timeBudget, c) {
    if (srv.pending) return waitOnFetch(srv, timeBudget, c);

    var e = srv.fetchError;
    if (e) { srv.fetchError = null; return c(e); }

    if (srv.needsPurge.length > 0) infer.withContext(srv.cx, function() {
      infer.purge(srv.needsPurge);
      srv.needsPurge.length = 0;
    });

    var done = true;
    // The second inner loop might add new files. The outer loop keeps
    // repeating both inner loops until all files have been looked at.
    for (var i = 0; i < srv.files.length;) {
      var toAnalyze = [];
      for (; i < srv.files.length; ++i) {
        var file = srv.files[i];
        if (file.text == null) done = false;
        else if (file.scope == null && !file.excluded) toAnalyze.push(file);
      }
      toAnalyze.sort(function(a, b) {
        return parentDepth(srv, a.parent) - parentDepth(srv, b.parent);
      });
      for (var j = 0; j < toAnalyze.length; j++) {
        var file = toAnalyze[j];
        if (file.parent && !chargeOnBudget(srv, file)) {
          file.excluded = true;
        } else if (timeBudget) {
          var startTime = +new Date;
          infer.withTimeout(timeBudget[0], function() { analyzeFile(srv, file); });
          timeBudget[0] -= +new Date - startTime;
        } else {
          analyzeFile(srv, file);
        }
      }
    }
    if (done) c();
    else waitOnFetch(srv, timeBudget, c);
  }
```
</details>

### `firstLine(str: any): any`

**Parameters:**

- **`str`** `any`

**Returns:** `any`

**Calls:**

- `str.indexOf`
- `str.slice`

<details><summary>Code</summary>

```typescript
function firstLine(str) {
    var end = str.indexOf("\n");
    if (end < 0) return str;
    return str.slice(0, end);
  }
```
</details>

### `findMatchingPosition(line: any, file: any, near: any): any`

**Parameters:**

- **`line`** `any`
- **`file`** `any`
- **`near`** `any`

**Returns:** `any`

**Calls:**

- `Math.max`
- `/^\s*$/.test`
- `file.indexOf`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function findMatchingPosition(line, file, near) {
    var pos = Math.max(0, near - 500), closest = null;
    if (!/^\s*$/.test(line)) for (;;) {
      var found = file.indexOf(line, pos);
      if (found < 0 || found > near + 500) break;
      if (closest == null || Math.abs(closest - near) > Math.abs(found - near))
        closest = found;
      pos = found + line.length;
    }
    return closest;
  }
```
</details>

### `scopeDepth(s: any): number`

**Parameters:**

- **`s`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function scopeDepth(s) {
    for (var i = 0; s; ++i, s = s.prev) {}
    return i;
  }
```
</details>

### `ternError(msg: any): Error`

**Parameters:**

- **`msg`** `any`

**Returns:** `Error`

<details><summary>Code</summary>

```typescript
function ternError(msg) {
    var err = new Error(msg);
    err.name = "TernError";
    return err;
  }
```
</details>

### `resolveFile(srv: any, localFiles: any, name: any): any`

**Parameters:**

- **`srv`** `any`
- **`localFiles`** `any`
- **`name`** `any`

**Returns:** `any`

**Calls:**

- `name.match`
- `srv.findFile`
- `ternError`
- `resolvePos`
- `firstLine`
- `findMatchingPosition`
- `Math.max`
- `realFile.text.lastIndexOf`
- `infer.withContext`
- `infer.purge`
- `text.match`
- `walk.findNodeAround`
- `line.match`
- `text.slice`
- `infer.scopeAt`
- `scopeDepth`
- `infer.parse`
- `infer.analyze`
- `inObject.type.getProp`
- `prop.addType`
- `Math.min`
- `fOld.args[i].propagate`
- `fOld.self.propagate`
- `fNew.retval.propagate`

**Internal Comments:**
```
// This is a partial file (x2)
// This is a kludge to tie together the function types (if any) (x2)
// outside and inside of the fragment, so that arguments and (x2)
// return values have some information known about them. (x2)
```

<details><summary>Code</summary>

```typescript
function resolveFile(srv, localFiles, name) {
    var isRef = name.match(/^#(\d+)$/);
    if (!isRef) return srv.findFile(name);

    var file = localFiles[isRef[1]];
    if (!file || file.type == "delete") throw ternError("Reference to unknown file " + name);
    if (file.type == "full") return srv.findFile(file.name);

    // This is a partial file

    var realFile = file.backing = srv.findFile(file.name);
    var offset;
    file.offset = offset = resolvePos(realFile, file.offsetLines == null ? file.offset : {line: file.offsetLines, ch: 0}, true);
    var line = firstLine(file.text);
    var foundPos = findMatchingPosition(line, realFile.text, offset);
    var pos = foundPos == null ? Math.max(0, realFile.text.lastIndexOf("\n", offset)) : foundPos;
    var inObject, atFunction;

    infer.withContext(srv.cx, function() {
      infer.purge(file.name, pos, pos + file.text.length);

      var text = file.text, m;
      if (m = text.match(/(?:"([^"]*)"|([\w$]+))\s*:\s*function\b/)) {
        var objNode = walk.findNodeAround(file.backing.ast, pos, "ObjectExpression");
        if (objNode && objNode.node.objType)
          inObject = {type: objNode.node.objType, prop: m[2] || m[1]};
      }
      if (foundPos && (m = line.match(/^(.*?)\bfunction\b/))) {
        var cut = m[1].length, white = "";
        for (var i = 0; i < cut; ++i) white += " ";
        text = white + text.slice(cut);
        atFunction = true;
      }

      var scopeStart = infer.scopeAt(realFile.ast, pos, realFile.scope);
      var scopeEnd = infer.scopeAt(realFile.ast, pos + text.length, realFile.scope);
      var scope = file.scope = scopeDepth(scopeStart) < scopeDepth(scopeEnd) ? scopeEnd : scopeStart;
      file.ast = infer.parse(text, srv.passes, {directSourceFile: file, allowReturnOutsideFunction: true});
      infer.analyze(file.ast, file.name, scope, srv.passes);

      // This is a kludge to tie together the function types (if any)
      // outside and inside of the fragment, so that arguments and
      // return values have some information known about them.
      tieTogether: if (inObject || atFunction) {
        var newInner = infer.scopeAt(file.ast, line.length, scopeStart);
        if (!newInner.fnType) break tieTogether;
        if (inObject) {
          var prop = inObject.type.getProp(inObject.prop);
          prop.addType(newInner.fnType);
        } else if (atFunction) {
          var inner = infer.scopeAt(realFile.ast, pos + line.length, realFile.scope);
          if (inner == scopeStart || !inner.fnType) break tieTogether;
          var fOld = inner.fnType, fNew = newInner.fnType;
          if (!fNew || (fNew.name != fOld.name && fOld.name)) break tieTogether;
          for (var i = 0, e = Math.min(fOld.args.length, fNew.args.length); i < e; ++i)
            fOld.args[i].propagate(fNew.args[i]);
          fOld.self.propagate(fNew.self);
          fNew.retval.propagate(fOld.retval);
        }
      }
    });
    return file;
  }
```
</details>

### `astSize(node: any): number`

**Parameters:**

- **`node`** `any`

**Returns:** `number`

**Calls:**

- `walk.simple`

<details><summary>Code</summary>

```typescript
function astSize(node) {
    var size = 0;
    walk.simple(node, {Expression: function() { ++size; }});
    return size;
  }
```
</details>

### `Expression(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { ++size; }
```
</details>

### `Expression(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { ++size; }
```
</details>

### `parentDepth(srv: any, parent: any): number`

**Parameters:**

- **`srv`** `any`
- **`parent`** `any`

**Returns:** `number`

**Calls:**

- `srv.findFile`

<details><summary>Code</summary>

```typescript
function parentDepth(srv, parent) {
    var depth = 0;
    while (parent) {
      parent = srv.findFile(parent).parent;
      ++depth;
    }
    return depth;
  }
```
</details>

### `budgetName(srv: any, file: any): any`

**Parameters:**

- **`srv`** `any`
- **`file`** `any`

**Returns:** `any`

**Calls:**

- `srv.findFile`

<details><summary>Code</summary>

```typescript
function budgetName(srv, file) {
    for (;;) {
      var parent = srv.findFile(file.parent);
      if (!parent.parent) break;
      file = parent;
    }
    return file.name;
  }
```
</details>

### `chargeOnBudget(srv: any, file: any): boolean`

**Parameters:**

- **`srv`** `any`
- **`file`** `any`

**Returns:** `boolean`

**Calls:**

- `budgetName`
- `astSize`

<details><summary>Code</summary>

```typescript
function chargeOnBudget(srv, file) {
    var bName = budgetName(srv, file);
    var size = astSize(file.ast);
    var known = srv.budgets[bName];
    if (known == null)
      known = srv.budgets[bName] = srv.options.dependencyBudget;
    if (known < size) return false;
    srv.budgets[bName] = known - size;
    return true;
  }
```
</details>

### `isPosition(val: any): boolean`

**Parameters:**

- **`val`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isPosition(val) {
    return typeof val == "number" || typeof val == "object" &&
      typeof val.line == "number" && typeof val.ch == "number";
  }
```
</details>

### `invalidDoc(doc: any): ".query.type must be a string" | ".query.start must be a position" | ".query.end must be a position" | "Files property must be an array" | ".files[n] must be objects" | ".files[n].name must be a string" | ".files[n].text must be a string" | ".files[n].offset must be a position" | ".files[n].type must be \"full\" or ...`

**Parameters:**

- **`doc`** `any`

**Returns:** `".query.type must be a string" | ".query.start must be a position" | ".query.end must be a position" | "Files property must be an array" | ".files[n] must be objects" | ".files[n].name must be a string" | ".files[n].text must be a string" | ".files[n].offset must be a position" | ".files[n].type must be \"full\" or ...`

**Calls:**

- `isPosition`
- `Array.isArray`

<details><summary>Code</summary>

```typescript
function invalidDoc(doc) {
    if (doc.query) {
      if (typeof doc.query.type != "string") return ".query.type must be a string";
      if (doc.query.start && !isPosition(doc.query.start)) return ".query.start must be a position";
      if (doc.query.end && !isPosition(doc.query.end)) return ".query.end must be a position";
    }
    if (doc.files) {
      if (!Array.isArray(doc.files)) return "Files property must be an array";
      for (var i = 0; i < doc.files.length; ++i) {
        var file = doc.files[i];
        if (typeof file != "object") return ".files[n] must be objects";
        else if (typeof file.name != "string") return ".files[n].name must be a string";
        else if (file.type == "delete") continue;
        else if (typeof file.text != "string") return ".files[n].text must be a string";
        else if (file.type == "part") {
          if (!isPosition(file.offset) && typeof file.offsetLines != "number")
            return ".files[n].offset must be a position";
        } else if (file.type != "full") return ".files[n].type must be \"full\" or \"part\"";
      }
    }
  }
```
</details>

### `findLineStart(file: any, line: any): number`

**Parameters:**

- **`file`** `any`
- **`line`** `any`

**Returns:** `number`

**Calls:**

- `Math.min`
- `Math.floor`
- `text.indexOf`
- `offsets.push`

<details><summary>Code</summary>

```typescript
function findLineStart(file, line) {
    var text = file.text, offsets = file.lineOffsets || (file.lineOffsets = [0]);
    var pos = 0, curLine = 0;
    var storePos = Math.min(Math.floor(line / offsetSkipLines), offsets.length - 1);
    var pos = offsets[storePos], curLine = storePos * offsetSkipLines;

    while (curLine < line) {
      ++curLine;
      pos = text.indexOf("\n", pos) + 1;
      if (pos === 0) return null;
      if (curLine % offsetSkipLines === 0) offsets.push(pos);
    }
    return pos;
  }
```
</details>

### `asLineChar(file: any, pos: any): { line: number; ch: number; }`

**Parameters:**

- **`file`** `any`
- **`pos`** `any`

**Returns:** `{ line: number; ch: number; }`

**Calls:**

- `text.indexOf`

<details><summary>Code</summary>

```typescript
function asLineChar(file, pos) {
    if (!file) return {line: 0, ch: 0};
    var offsets = file.lineOffsets || (file.lineOffsets = [0]);
    var text = file.text, line, lineStart;
    for (var i = offsets.length - 1; i >= 0; --i) if (offsets[i] <= pos) {
      line = i * offsetSkipLines;
      lineStart = offsets[i];
    }
    for (;;) {
      var eol = text.indexOf("\n", lineStart);
      if (eol >= pos || eol < 0) break;
      lineStart = eol + 1;
      ++line;
    }
    return {line: line, ch: pos - lineStart};
  }
```
</details>

### `clean(obj: any): any`

**Parameters:**

- **`obj`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function clean(obj) {
    for (var prop in obj) if (obj[prop] == null) delete obj[prop];
    return obj;
  }
```
</details>

### `maybeSet(obj: any, prop: any, val: any): void`

**Parameters:**

- **`obj`** `any`
- **`prop`** `any`
- **`val`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function maybeSet(obj, prop, val) {
    if (val != null) obj[prop] = val;
  }
```
</details>

### `compareCompletions(a: any, b: any): 1 | 0 | -1`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `1 | 0 | -1`

**Calls:**

- `/^[A-Z]/.test`

<details><summary>Code</summary>

```typescript
function compareCompletions(a, b) {
    if (typeof a != "string") { a = a.name; b = b.name; }
    var aUp = /^[A-Z]/.test(a), bUp = /^[A-Z]/.test(b);
    if (aUp == bUp) return a < b ? -1 : a == b ? 0 : 1;
    else return aUp ? 1 : -1;
  }
```
</details>

### `isStringAround(node: any, start: any, end: any): boolean`

**Parameters:**

- **`node`** `any`
- **`start`** `any`
- **`end`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isStringAround(node, start, end) {
    return node.type == "Literal" && typeof node.value == "string" &&
      node.start == start - 1 && node.end <= end + 1;
  }
```
</details>

### `pointInProp(objNode: any, point: any): any`

**Parameters:**

- **`objNode`** `any`
- **`point`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function pointInProp(objNode, point) {
    for (var i = 0; i < objNode.properties.length; i++) {
      var curProp = objNode.properties[i];
      if (curProp.key.start <= point && curProp.key.end >= point)
        return curProp;
    }
  }
```
</details>

### `findCompletions(srv: any, query: any, file: any): any`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`
- **`file`** `any`

**Returns:** `any`

**Calls:**

- `ternError`
- `complex_call_19365`
- `resolvePos`
- `acorn.isIdentifierChar`
- `text.charCodeAt`
- `text.slice`
- `word.toLowerCase`
- `(query.caseInsensitive ? prop.toLowerCase() : prop).indexOf`
- `prop.toLowerCase`
- `completions.push`
- `infer.resetGuessing`
- `val.getType`
- `infer.didGuess`
- `infer.toString`
- `maybeSet`
- `addInfo`
- `infer.findExpressionAround`
- `isStringAround`
- `infer.parentNode`
- `pointInProp`
- `/:\s*$/.test`
- `file.text.slice`
- `infer.typeFromContext`
- `prop.value.slice`
- `infer.expressionType`
- `text.charAt`
- `infer.def.parsePath(path, file.scope).getObjType`
- `infer.forAllPropertiesOf`
- `objType.guessProperties`
- `gather`
- `infer.forAllLocalsAt`
- `jsKeywords.forEach`
- `srv.passes[hookname].forEach`
- `hook`
- `completions.sort`
- `outputPos`

**Internal Comments:**
```
// 'hasOwnProperty' and such are usually just noise, leave them
// out when no prefix is provided.
// Decide whether this is an object property, either in a member
// expression or an object literal.
// Since we can't use the type of the literal itself to complete (x3)
// its properties (it doesn't contain the information we need), (x3)
// we have to try asking the surrounding expression for type info. (x3)
```

<details><summary>Code</summary>

```typescript
function findCompletions(srv, query, file) {
    if (query.end == null) throw ternError("missing .query.end field");
    if (srv.passes.completion) for (var i = 0; i < srv.passes.completion.length; i++) {
      var result = srv.passes.completion[i](file, query);
      if (result) return result;
    }

    var wordStart = resolvePos(file, query.end), wordEnd = wordStart, text = file.text;
    while (wordStart && acorn.isIdentifierChar(text.charCodeAt(wordStart - 1))) --wordStart;
    if (query.expandWordForward !== false)
      while (wordEnd < text.length && acorn.isIdentifierChar(text.charCodeAt(wordEnd))) ++wordEnd;
    var word = text.slice(wordStart, wordEnd), completions = [], ignoreObj;
    if (query.caseInsensitive) word = word.toLowerCase();
    var wrapAsObjs = query.types || query.depths || query.docs || query.urls || query.origins;

    function gather(prop, obj, depth, addInfo) {
      // 'hasOwnProperty' and such are usually just noise, leave them
      // out when no prefix is provided.
      if ((objLit || query.omitObjectPrototype !== false) && obj == srv.cx.protos.Object && !word) return;
      if (query.filter !== false && word &&
          (query.caseInsensitive ? prop.toLowerCase() : prop).indexOf(word) !== 0) return;
      if (ignoreObj && ignoreObj.props[prop]) return;
      for (var i = 0; i < completions.length; ++i) {
        var c = completions[i];
        if ((wrapAsObjs ? c.name : c) == prop) return;
      }
      var rec = wrapAsObjs ? {name: prop} : prop;
      completions.push(rec);

      if (obj && (query.types || query.docs || query.urls || query.origins)) {
        var val = obj.props[prop];
        infer.resetGuessing();
        var type = val.getType();
        rec.guess = infer.didGuess();
        if (query.types)
          rec.type = infer.toString(val);
        if (query.docs)
          maybeSet(rec, "doc", val.doc || type && type.doc);
        if (query.urls)
          maybeSet(rec, "url", val.url || type && type.url);
        if (query.origins)
          maybeSet(rec, "origin", val.origin || type && type.origin);
      }
      if (query.depths) rec.depth = depth;
      if (wrapAsObjs && addInfo) addInfo(rec);
    }

    var hookname, prop, objType, isKey;

    var exprAt = infer.findExpressionAround(file.ast, null, wordStart, file.scope);
    var memberExpr, objLit;
    // Decide whether this is an object property, either in a member
    // expression or an object literal.
    if (exprAt) {
      if (exprAt.node.type == "MemberExpression" && exprAt.node.object.end < wordStart) {
        memberExpr = exprAt;
      } else if (isStringAround(exprAt.node, wordStart, wordEnd)) {
        var parent = infer.parentNode(exprAt.node, file.ast);
        if (parent.type == "MemberExpression" && parent.property == exprAt.node)
          memberExpr = {node: parent, state: exprAt.state};
      } else if (exprAt.node.type == "ObjectExpression") {
        var objProp = pointInProp(exprAt.node, wordEnd);
        if (objProp) {
          objLit = exprAt;
          prop = isKey = objProp.key.name;
        } else if (!word && !/:\s*$/.test(file.text.slice(0, wordStart))) {
          objLit = exprAt;
          prop = isKey = true;
        }
      }
    }

    if (objLit) {
      // Since we can't use the type of the literal itself to complete
      // its properties (it doesn't contain the information we need),
      // we have to try asking the surrounding expression for type info.
      objType = infer.typeFromContext(file.ast, objLit);
      ignoreObj = objLit.node.objType;
    } else if (memberExpr) {
      prop = memberExpr.node.property;
      prop = prop.type == "Literal" ? prop.value.slice(1) : prop.name;
      memberExpr.node = memberExpr.node.object;
      objType = infer.expressionType(memberExpr);
    } else if (text.charAt(wordStart - 1) == ".") {
      var pathStart = wordStart - 1;
      while (pathStart && (text.charAt(pathStart - 1) == "." || acorn.isIdentifierChar(text.charCodeAt(pathStart - 1)))) pathStart--;
      var path = text.slice(pathStart, wordStart - 1);
      if (path) {
        objType = infer.def.parsePath(path, file.scope).getObjType();
        prop = word;
      }
    }

    if (prop != null) {
      srv.cx.completingProperty = prop;

      if (objType) infer.forAllPropertiesOf(objType, gather);

      if (!completions.length && query.guess !== false && objType && objType.guessProperties)
        objType.guessProperties(function(p, o, d) {if (p != prop && p != "✖") gather(p, o, d);});
      if (!completions.length && word.length >= 2 && query.guess !== false)
        for (var prop in srv.cx.props) gather(prop, srv.cx.props[prop][0], 0);
      hookname = "memberCompletion";
    } else {
      infer.forAllLocalsAt(file.ast, wordStart, file.scope, gather);
      if (query.includeKeywords) jsKeywords.forEach(function(kw) {
        gather(kw, null, 0, function(rec) { rec.isKeyword = true; });
      });
      hookname = "variableCompletion";
    }
    if (srv.passes[hookname])
      srv.passes[hookname].forEach(function(hook) {hook(file, wordStart, wordEnd, gather);});

    if (query.sort !== false) completions.sort(compareCompletions);
    srv.cx.completingProperty = null;

    return {start: outputPos(query, file, wordStart),
            end: outputPos(query, file, wordEnd),
            isProperty: !!prop,
            isObjectKey: !!isKey,
            completions: completions};
  }
```
</details>

### `gather(prop: any, obj: any, depth: any, addInfo: any): void`

**Parameters:**

- **`prop`** `any`
- **`obj`** `any`
- **`depth`** `any`
- **`addInfo`** `any`

**Returns:** `void`

**Calls:**

- `(query.caseInsensitive ? prop.toLowerCase() : prop).indexOf`
- `prop.toLowerCase`
- `completions.push`
- `infer.resetGuessing`
- `val.getType`
- `infer.didGuess`
- `infer.toString`
- `maybeSet`
- `addInfo`

**Internal Comments:**
```
// 'hasOwnProperty' and such are usually just noise, leave them
// out when no prefix is provided.
```

<details><summary>Code</summary>

```typescript
function gather(prop, obj, depth, addInfo) {
      // 'hasOwnProperty' and such are usually just noise, leave them
      // out when no prefix is provided.
      if ((objLit || query.omitObjectPrototype !== false) && obj == srv.cx.protos.Object && !word) return;
      if (query.filter !== false && word &&
          (query.caseInsensitive ? prop.toLowerCase() : prop).indexOf(word) !== 0) return;
      if (ignoreObj && ignoreObj.props[prop]) return;
      for (var i = 0; i < completions.length; ++i) {
        var c = completions[i];
        if ((wrapAsObjs ? c.name : c) == prop) return;
      }
      var rec = wrapAsObjs ? {name: prop} : prop;
      completions.push(rec);

      if (obj && (query.types || query.docs || query.urls || query.origins)) {
        var val = obj.props[prop];
        infer.resetGuessing();
        var type = val.getType();
        rec.guess = infer.didGuess();
        if (query.types)
          rec.type = infer.toString(val);
        if (query.docs)
          maybeSet(rec, "doc", val.doc || type && type.doc);
        if (query.urls)
          maybeSet(rec, "url", val.url || type && type.url);
        if (query.origins)
          maybeSet(rec, "origin", val.origin || type && type.origin);
      }
      if (query.depths) rec.depth = depth;
      if (wrapAsObjs && addInfo) addInfo(rec);
    }
```
</details>

### `findProperties(srv: any, query: any): { completions: string[]; }`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`

**Returns:** `{ completions: string[]; }`

**Calls:**

- `prop.indexOf`
- `found.push`
- `found.sort`

<details><summary>Code</summary>

```typescript
function findProperties(srv, query) {
    var prefix = query.prefix, found = [];
    for (var prop in srv.cx.props)
      if (prop != "<i>" && (!prefix || prop.indexOf(prefix) === 0)) found.push(prop);
    if (query.sort !== false) found.sort(compareCompletions);
    return {completions: found};
  }
```
</details>

### `findExprOrThrow(file: any, query: any, wide: any): any`

**Parameters:**

- **`file`** `any`
- **`query`** `any`
- **`wide`** `any`

**Returns:** `any`

**Calls:**

- `findExpr`
- `ternError`

<details><summary>Code</summary>

```typescript
function findExprOrThrow(file, query, wide) {
    var expr = findExpr(file, query, wide);
    if (expr) return expr;
    throw ternError("No expression at the given position.");
  }
```
</details>

### `ensureObj(tp: any): any`

**Parameters:**

- **`tp`** `any`

**Returns:** `any`

**Calls:**

- `tp.getType`

<details><summary>Code</summary>

```typescript
function ensureObj(tp) {
    if (!tp || !(tp = tp.getType()) || !(tp instanceof infer.Obj)) return null;
    return tp;
  }
```
</details>

### `findExprType(srv: any, query: any, file: any, expr: any): any`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`
- **`file`** `any`
- **`expr`** `any`

**Returns:** `any`

**Calls:**

- `infer.resetGuessing`
- `infer.expressionType`
- `resolvePos`
- `srv.passes["typeAt"].forEach`
- `hook`
- `ternError`
- `pointInProp`
- `ensureObj`
- `infer.typeFromContext`
- `fromCx.hasProp`
- `fromLocal.hasProp`

<details><summary>Code</summary>

```typescript
function findExprType(srv, query, file, expr) {
    var type;
    if (expr) {
      infer.resetGuessing();
      type = infer.expressionType(expr);
    }
    if (srv.passes["typeAt"]) {
      var pos = resolvePos(file, query.end);
      srv.passes["typeAt"].forEach(function(hook) {
        type = hook(file, pos, expr, type);
      });
    }
    if (!type) throw ternError("No type found at the given position.");

    var objProp;
    if (expr.node.type == "ObjectExpression" && query.end != null &&
        (objProp = pointInProp(expr.node, resolvePos(file, query.end)))) {
      var name = objProp.key.name;
      var fromCx = ensureObj(infer.typeFromContext(file.ast, expr));
      if (fromCx && fromCx.hasProp(name)) {
        type = fromCx.hasProp(name);
      } else {
        var fromLocal = ensureObj(type);
        if (fromLocal && fromLocal.hasProp(name))
          type = fromLocal.hasProp(name);
      }
    }
    return type;
  }
```
</details>

### `findTypeAt(srv: any, query: any, file: any): any`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`
- **`file`** `any`

**Returns:** `any`

**Calls:**

- `findExpr`
- `findExprType`
- `type.getFunctionType`
- `type.getType`
- `ternError`
- `infer.didGuess`
- `infer.toString`
- `storeTypeDocs`
- `clean`

<details><summary>Code</summary>

```typescript
function findTypeAt(srv, query, file) {
    var expr = findExpr(file, query), exprName;
    var type = findExprType(srv, query, file, expr), exprType = type;
    if (query.preferFunction)
      type = type.getFunctionType() || type.getType();
    else
      type = type.getType();

    if (expr) {
      if (expr.node.type == "Identifier")
        exprName = expr.node.name;
      else if (expr.node.type == "MemberExpression" && !expr.node.computed)
        exprName = expr.node.property.name;
    }

    if (query.depth != null && typeof query.depth != "number")
      throw ternError(".query.depth must be a number");

    var result = {guess: infer.didGuess(),
                  type: infer.toString(exprType, query.depth),
                  name: type && type.name,
                  exprName: exprName};
    if (type) storeTypeDocs(type, result);
    if (!result.doc && exprType.doc) result.doc = exprType.doc;

    return clean(result);
  }
```
</details>

### `findDocs(srv: any, query: any, file: any): any`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`
- **`file`** `any`

**Returns:** `any`

**Calls:**

- `findExpr`
- `findExprType`
- `infer.toString`
- `type.getType`
- `storeTypeDocs`
- `clean`

<details><summary>Code</summary>

```typescript
function findDocs(srv, query, file) {
    var expr = findExpr(file, query);
    var type = findExprType(srv, query, file, expr);
    var result = {url: type.url, doc: type.doc, type: infer.toString(type)};
    var inner = type.getType();
    if (inner) storeTypeDocs(inner, result);
    return clean(result);
  }
```
</details>

### `storeTypeDocs(type: any, out: any): void`

**Parameters:**

- **`type`** `any`
- **`out`** `any`

**Returns:** `void`

**Calls:**

- `infer.cx`

<details><summary>Code</summary>

```typescript
function storeTypeDocs(type, out) {
    if (!out.url) out.url = type.url;
    if (!out.doc) out.doc = type.doc;
    if (!out.origin) out.origin = type.origin;
    var ctor, boring = infer.cx().protos;
    if (!out.url && !out.doc && type.proto && (ctor = type.proto.hasCtor) &&
        type.proto != boring.Object && type.proto != boring.Function && type.proto != boring.Array) {
      out.url = ctor.url;
      out.doc = ctor.doc;
    }
  }
```
</details>

### `findDef(srv: any, query: any, file: any): any`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`
- **`file`** `any`

**Returns:** `any`

**Calls:**

- `findExpr`
- `findExprType`
- `infer.didGuess`
- `getSpan`
- `storeTypeDocs`
- `srv.findFile`
- `outputPos`
- `Math.max`
- `spanFile.text.slice`
- `storeSpan`
- `clean`

<details><summary>Code</summary>

```typescript
function findDef(srv, query, file) {
    var expr = findExpr(file, query);
    var type = findExprType(srv, query, file, expr);
    if (infer.didGuess()) return {};

    var span = getSpan(type);
    var result = {url: type.url, doc: type.doc, origin: type.origin};

    if (type.types) for (var i = type.types.length - 1; i >= 0; --i) {
      var tp = type.types[i];
      storeTypeDocs(tp, result);
      if (!span) span = getSpan(tp);
    }

    if (span && span.node) { // refers to a loaded file
      var spanFile = span.node.sourceFile || srv.findFile(span.origin);
      var start = outputPos(query, spanFile, span.node.start), end = outputPos(query, spanFile, span.node.end);
      result.start = start; result.end = end;
      result.file = span.origin;
      var cxStart = Math.max(0, span.node.start - 50);
      result.contextOffset = span.node.start - cxStart;
      result.context = spanFile.text.slice(cxStart, cxStart + 50);
    } else if (span) { // external
      result.file = span.origin;
      storeSpan(srv, query, span, result);
    }
    return clean(result);
  }
```
</details>

### `findRefsToVariable(srv: any, query: any, file: any, expr: any, checkShadowing: any): { refs: any[]; type: string; name: any; }`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`
- **`file`** `any`
- **`expr`** `any`
- **`checkShadowing`** `any`

**Returns:** `{ refs: any[]; type: string; name: any; }`

**Calls:**

- `ternError`
- `s.hasProp`
- `asLineChar`
- `refs.push`
- `outputPos`
- `infer.findRefs`
- `storeRef`

<details><summary>Code</summary>

```typescript
function findRefsToVariable(srv, query, file, expr, checkShadowing) {
    var name = expr.node.name;

    for (var scope = expr.state; scope && !(name in scope.props); scope = scope.prev) {}
    if (!scope) throw ternError("Could not find a definition for " + name + " " + !!srv.cx.topScope.props.x);

    var type, refs = [];
    function storeRef(file) {
      return function(node, scopeHere) {
        if (checkShadowing) for (var s = scopeHere; s != scope; s = s.prev) {
          var exists = s.hasProp(checkShadowing);
          if (exists)
            throw ternError("Renaming `" + name + "` to `" + checkShadowing + "` would make a variable at line " +
                            (asLineChar(file, node.start).line + 1) + " point to the definition at line " +
                            (asLineChar(file, exists.name.start).line + 1));
        }
        refs.push({file: file.name,
                   start: outputPos(query, file, node.start),
                   end: outputPos(query, file, node.end)});
      };
    }

    if (scope.originNode) {
      type = "local";
      if (checkShadowing) {
        for (var prev = scope.prev; prev; prev = prev.prev)
          if (checkShadowing in prev.props) break;
        if (prev) infer.findRefs(scope.originNode, scope, checkShadowing, prev, function(node) {
          throw ternError("Renaming `" + name + "` to `" + checkShadowing + "` would shadow the definition used at line " +
                          (asLineChar(file, node.start).line + 1));
        });
      }
      infer.findRefs(scope.originNode, scope, name, scope, storeRef(file));
    } else {
      type = "global";
      for (var i = 0; i < srv.files.length; ++i) {
        var cur = srv.files[i];
        infer.findRefs(cur.ast, cur.scope, name, scope, storeRef(cur));
      }
    }

    return {refs: refs, type: type, name: name};
  }
```
</details>

### `storeRef(file: any): (node: any, scopeHere: any) => void`

**Parameters:**

- **`file`** `any`

**Returns:** `(node: any, scopeHere: any) => void`

**Calls:**

- `s.hasProp`
- `ternError`
- `asLineChar`
- `refs.push`
- `outputPos`

<details><summary>Code</summary>

```typescript
function storeRef(file) {
      return function(node, scopeHere) {
        if (checkShadowing) for (var s = scopeHere; s != scope; s = s.prev) {
          var exists = s.hasProp(checkShadowing);
          if (exists)
            throw ternError("Renaming `" + name + "` to `" + checkShadowing + "` would make a variable at line " +
                            (asLineChar(file, node.start).line + 1) + " point to the definition at line " +
                            (asLineChar(file, exists.name.start).line + 1));
        }
        refs.push({file: file.name,
                   start: outputPos(query, file, node.start),
                   end: outputPos(query, file, node.end)});
      };
    }
```
</details>

### `findRefsToProperty(srv: any, query: any, expr: any, prop: any): { refs: any[]; name: any; }`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`
- **`expr`** `any`
- **`prop`** `any`

**Returns:** `{ refs: any[]; name: any; }`

**Calls:**

- `infer.expressionType(expr).getObjType`
- `ternError`
- `refs.push`
- `outputPos`
- `infer.findPropRefs`
- `storeRef`

<details><summary>Code</summary>

```typescript
function findRefsToProperty(srv, query, expr, prop) {
    var objType = infer.expressionType(expr).getObjType();
    if (!objType) throw ternError("Couldn't determine type of base object.");

    var refs = [];
    function storeRef(file) {
      return function(node) {
        refs.push({file: file.name,
                   start: outputPos(query, file, node.start),
                   end: outputPos(query, file, node.end)});
      };
    }
    for (var i = 0; i < srv.files.length; ++i) {
      var cur = srv.files[i];
      infer.findPropRefs(cur.ast, cur.scope, objType, prop.name, storeRef(cur));
    }

    return {refs: refs, name: prop.name};
  }
```
</details>

### `storeRef(file: any): (node: any) => void`

**Parameters:**

- **`file`** `any`

**Returns:** `(node: any) => void`

**Calls:**

- `refs.push`
- `outputPos`

<details><summary>Code</summary>

```typescript
function storeRef(file) {
      return function(node) {
        refs.push({file: file.name,
                   start: outputPos(query, file, node.start),
                   end: outputPos(query, file, node.end)});
      };
    }
```
</details>

### `findRefs(srv: any, query: any, file: any): { refs: any[]; name: any; }`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`
- **`file`** `any`

**Returns:** `{ refs: any[]; name: any; }`

**Calls:**

- `findExprOrThrow`
- `findRefsToVariable`
- `findRefsToProperty`
- `resolvePos`
- `ternError`

<details><summary>Code</summary>

```typescript
function findRefs(srv, query, file) {
    var expr = findExprOrThrow(file, query, true);
    if (expr.node.type == "Identifier") {
      return findRefsToVariable(srv, query, file, expr);
    } else if (expr.node.type == "MemberExpression" && !expr.node.computed) {
      var p = expr.node.property;
      expr.node = expr.node.object;
      return findRefsToProperty(srv, query, expr, p);
    } else if (expr.node.type == "ObjectExpression") {
      var pos = resolvePos(file, query.end);
      for (var i = 0; i < expr.node.properties.length; ++i) {
        var k = expr.node.properties[i].key;
        if (k.start <= pos && k.end >= pos)
          return findRefsToProperty(srv, query, expr, k);
      }
    }
    throw ternError("Not at a variable or property name.");
  }
```
</details>

### `buildRename(srv: any, query: any, file: any): { refs: any[]; type: string; name: any; }`

**Parameters:**

- **`srv`** `any`
- **`query`** `any`
- **`file`** `any`

**Returns:** `{ refs: any[]; type: string; name: any; }`

**Calls:**

- `ternError`
- `findExprOrThrow`
- `findRefsToVariable`
- `srv.files.map`
- `changes.push`

<details><summary>Code</summary>

```typescript
function buildRename(srv, query, file) {
    if (typeof query.newName != "string") throw ternError(".query.newName should be a string");
    var expr = findExprOrThrow(file, query);
    if (!expr || expr.node.type != "Identifier") throw ternError("Not at a variable.");

    var data = findRefsToVariable(srv, query, file, expr, query.newName), refs = data.refs;
    delete data.refs;
    data.files = srv.files.map(function(f){return f.name;});

    var changes = data.changes = [];
    for (var i = 0; i < refs.length; ++i) {
      var use = refs[i];
      use.text = query.newName;
      changes.push(use);
    }

    return data;
  }
```
</details>

### `listFiles(srv: any): { files: any; }`

**Parameters:**

- **`srv`** `any`

**Returns:** `{ files: any; }`

**Calls:**

- `srv.files.map`

<details><summary>Code</summary>

```typescript
function listFiles(srv) {
    return {files: srv.files.map(function(f){return f.name;})};
  }
```
</details>


---