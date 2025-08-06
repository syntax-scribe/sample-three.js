[⬅️ Back to Table of Contents](../../../../../index.md)

# 📄 `tern.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 65 |
| 📊 Variables & Constants | 81 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/codemirror/addon/tern.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `self` | `this` | let/var | `this` | ✗ |
| `plugins` | `any` | let/var | `this.options.plugins \|\| (this.options.plugins = {})` | ✗ |
| `data` | `{ doc: any; name: any; changed: any; }` | let/var | `{doc: doc, name: name, changed: null}` | ✗ |
| `self` | `{ addDoc: (name: any, doc: any) => { ...` | let/var | `this` | ✗ |
| `extraOptions` | `any` | let/var | `request.query && this.options.queryOptions && this.options.queryOptions[reque...` | ✗ |
| `Pos` | `any` | let/var | `CodeMirror.Pos` | ✗ |
| `cls` | `string` | let/var | `"CodeMirror-Tern-"` | ✗ |
| `bigDoc` | `number` | let/var | `250` | ✗ |
| `buf` | `any` | let/var | `ts.docs[name]` | ✗ |
| `cur` | `any` | let/var | `ts.docs[n]` | ✗ |
| `argHints` | `any` | let/var | `ts.cachedArgHints` | ✗ |
| `changed` | `any` | let/var | `data.changed` | ✗ |
| `end` | `any` | let/var | `change.from.line + (change.text.length - 1)` | ✗ |
| `completions` | `any[]` | let/var | `[]` | ✗ |
| `after` | `string` | let/var | `""` | ✗ |
| `from` | `any` | let/var | `data.start` | ✗ |
| `to` | `any` | let/var | `data.end` | ✗ |
| `completion` | `any` | let/var | `data.completions[i]` | ✗ |
| `obj` | `{ from: any; to: any; list: { text: s...` | let/var | `{from: from, to: to, list: completions}` | ✗ |
| `tooltip` | `any` | let/var | `null` | ✗ |
| `content` | `any` | let/var | `ts.options.completionTip ? ts.options.completionTip(cur.data) : cur.data.doc` | ✗ |
| `suffix` | `any` | let/var | `*not shown*` | ✗ |
| `state` | `any` | let/var | `cm.getTokenAt(cm.getCursor()).state` | ✗ |
| `lex` | `any` | let/var | `inner.state.lexical` | ✗ |
| `ch` | `any` | let/var | `*not shown*` | ✗ |
| `argPos` | `any` | let/var | `lex.pos \|\| 0` | ✗ |
| `extra` | `number` | let/var | `0` | ✗ |
| `cache` | `any` | let/var | `ts.cachedArgHints` | ✗ |
| `cache` | `any` | let/var | `ts.cachedArgHints` | ✗ |
| `tp` | `any` | let/var | `cache.type` | ✗ |
| `arg` | `any` | let/var | `tp.args[i]` | ✗ |
| `tooltip` | `any` | let/var | `ts.activeArgHints = makeTooltip(place.right + 1, place.bottom, tip, cm)` | ✗ |
| `args` | `any[]` | let/var | `[]` | ✗ |
| `pos` | `number` | let/var | `3` | ✗ |
| `depth` | `number` | let/var | `0` | ✗ |
| `start` | `number` | let/var | `pos` | ✗ |
| `req` | `{ type: string; variable: any; }` | let/var | `{type: "definition", variable: varName \|\| null}` | ✗ |
| `localDoc` | `any` | let/var | `ts.docs[data.file]` | ✗ |
| `found` | `any` | let/var | `*not shown*` | ✗ |
| `doc` | `any` | let/var | `pos && ts.docs[pos.file]` | ✗ |
| `startLine` | `number` | let/var | `data.start.line - (before.length - 1)` | ✗ |
| `nearest` | `any` | let/var | `*not shown*` | ✗ |
| `nearestDist` | `number` | let/var | `Infinity` | ✗ |
| `dist` | `number` | let/var | `Math.abs(from.line - start.line) * 10000` | ✗ |
| `name` | `any` | let/var | `findDoc(ts, cm.doc).name` | ✗ |
| `ranges` | `any[]` | let/var | `[]` | ✗ |
| `cur` | `number` | let/var | `0` | ✗ |
| `ref` | `any` | let/var | `data.refs[i]` | ✗ |
| `nextChangeOrig` | `number` | let/var | `0` | ✗ |
| `ch` | `any` | let/var | `changes[i]` | ✗ |
| `known` | `any` | let/var | `ts.docs[file]` | ✗ |
| `chs` | `any` | let/var | `perFile[file]` | ✗ |
| `origin` | `string` | let/var | `"*rename" + (++nextChangeOrig)` | ✗ |
| `files` | `any[]` | let/var | `[]` | ✗ |
| `offsetLines` | `number` | let/var | `0` | ✗ |
| `allowFragments` | `boolean` | let/var | `!query.fullDocs` | ✗ |
| `startPos` | `any` | let/var | `query.start \|\| query.end` | ✗ |
| `cur` | `any` | let/var | `ts.docs[name]` | ✗ |
| `doc` | `any` | let/var | `data.doc` | ✗ |
| `minIndent` | `any` | let/var | `null` | ✗ |
| `minLine` | `any` | let/var | `null` | ✗ |
| `endLine` | `any` | let/var | `*not shown*` | ✗ |
| `tabSize` | `number` | let/var | `4` | ✗ |
| `cmpPos` | `any` | let/var | `CodeMirror.cmpPos` | ✗ |
| `elt` | `any` | let/var | `arguments[i]` | ✗ |
| `tip` | `any` | let/var | `cm.state.ternTooltip = makeTooltip(where.right + 1, where.bottom, content, cm)` | ✗ |
| `mouseOnTip` | `boolean` | let/var | `false` | ✗ |
| `old` | `boolean` | let/var | `false` | ✗ |
| `related` | `any` | let/var | `e.relatedTarget \|\| e.toElement` | ✗ |
| `container` | `any` | let/var | `((cm.options \|\| {}).hintOptions \|\| {}).container \|\| document.body` | ✗ |
| `winW` | `number` | let/var | `window.innerWidth` | ✗ |
| `winH` | `number` | let/var | `window.innerHeight` | ✗ |
| `overlapY` | `number` | let/var | `box.bottom - winH` | ✗ |
| `overlapX` | `number` | let/var | `box.right - winW` | ✗ |
| `height` | `number` | let/var | `box.bottom - box.top` | ✗ |
| `curTop` | `number` | let/var | `pos.top - (pos.bottom - box.top)` | ✗ |
| `p` | `any` | let/var | `node && node.parentNode` | ✗ |
| `worker` | `Worker` | let/var | `ts.worker = new Worker(ts.options.workerScript)` | ✗ |
| `msgId` | `number` | let/var | `0` | ✗ |
| `pending` | `{}` | let/var | `{}` | ✗ |
| `data` | `any` | let/var | `e.data` | ✗ |


---

## Functions

### `getFile(name: any, c: any): void`

**Parameters:**

- **`name`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `getFile`

<details><summary>Code</summary>

```typescript
function(name, c) { return getFile(self, name, c); }
```
</details>

### `getFile(name: any, c: any): void`

**Parameters:**

- **`name`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `getFile`

<details><summary>Code</summary>

```typescript
function(name, c) { return getFile(self, name, c); }
```
</details>

### `addDoc(name: any, doc: any): { doc: any; name: any; changed: any; }`

**Parameters:**

- **`name`** `any`
- **`doc`** `any`

**Returns:** `{ doc: any; name: any; changed: any; }`

**Calls:**

- `this.server.addFile`
- `docValue`
- `CodeMirror.on`

<details><summary>Code</summary>

```typescript
function(name, doc) {
      var data = {doc: doc, name: name, changed: null};
      this.server.addFile(name, docValue(this, data));
      CodeMirror.on(doc, "change", this.trackChange);
      return this.docs[name] = data;
    }
```
</details>

### `delDoc(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `resolveDoc`
- `CodeMirror.off`
- `this.server.delFile`

<details><summary>Code</summary>

```typescript
function(id) {
      var found = resolveDoc(this, id);
      if (!found) return;
      CodeMirror.off(found.doc, "change", this.trackChange);
      delete this.docs[found.name];
      this.server.delFile(found.name);
    }
```
</details>

### `hideDoc(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `closeArgHints`
- `resolveDoc`
- `sendDoc`

<details><summary>Code</summary>

```typescript
function(id) {
      closeArgHints(this);
      var found = resolveDoc(this, id);
      if (found && found.changed) sendDoc(this, found);
    }
```
</details>

### `complete(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.showHint`

<details><summary>Code</summary>

```typescript
function(cm) {
      cm.showHint({hint: this.getHint});
    }
```
</details>

### `showType(cm: any, pos: any, c: any): void`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `showContextInfo`

<details><summary>Code</summary>

```typescript
function(cm, pos, c) { showContextInfo(this, cm, pos, "type", c); }
```
</details>

### `showDocs(cm: any, pos: any, c: any): void`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `showContextInfo`

<details><summary>Code</summary>

```typescript
function(cm, pos, c) { showContextInfo(this, cm, pos, "documentation", c); }
```
</details>

### `updateArgHints(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `updateArgHints`

<details><summary>Code</summary>

```typescript
function(cm) { updateArgHints(this, cm); }
```
</details>

### `jumpToDef(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `jumpToDef`

<details><summary>Code</summary>

```typescript
function(cm) { jumpToDef(this, cm); }
```
</details>

### `jumpBack(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `jumpBack`

<details><summary>Code</summary>

```typescript
function(cm) { jumpBack(this, cm); }
```
</details>

### `rename(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `rename`

<details><summary>Code</summary>

```typescript
function(cm) { rename(this, cm); }
```
</details>

### `selectName(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `selectName`

<details><summary>Code</summary>

```typescript
function(cm) { selectName(this, cm); }
```
</details>

### `request(cm: any, query: any, c: any, pos: any): void`

**Parameters:**

- **`cm`** `any`
- **`query`** `any`
- **`c`** `any`
- **`pos`** `any`

**Returns:** `void`

**Calls:**

- `findDoc`
- `cm.getDoc`
- `buildRequest`
- `this.server.request`
- `self.options.responseFilter`
- `c`

<details><summary>Code</summary>

```typescript
function (cm, query, c, pos) {
      var self = this;
      var doc = findDoc(this, cm.getDoc());
      var request = buildRequest(this, doc, query, pos);
      var extraOptions = request.query && this.options.queryOptions && this.options.queryOptions[request.query.type]
      if (extraOptions) for (var prop in extraOptions) request.query[prop] = extraOptions[prop];

      this.server.request(request, function (error, data) {
        if (!error && self.options.responseFilter)
          data = self.options.responseFilter(doc, query, request, error, data);
        c(error, data);
      });
    }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `closeArgHints`
- `this.worker.terminate`

<details><summary>Code</summary>

```typescript
function () {
      closeArgHints(this)
      if (this.worker) {
        this.worker.terminate();
        this.worker = null;
      }
    }
```
</details>

### `addDoc(name: any, doc: any): { doc: any; name: any; changed: any; }`

**Parameters:**

- **`name`** `any`
- **`doc`** `any`

**Returns:** `{ doc: any; name: any; changed: any; }`

**Calls:**

- `this.server.addFile`
- `docValue`
- `CodeMirror.on`

<details><summary>Code</summary>

```typescript
function(name, doc) {
      var data = {doc: doc, name: name, changed: null};
      this.server.addFile(name, docValue(this, data));
      CodeMirror.on(doc, "change", this.trackChange);
      return this.docs[name] = data;
    }
```
</details>

### `delDoc(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `resolveDoc`
- `CodeMirror.off`
- `this.server.delFile`

<details><summary>Code</summary>

```typescript
function(id) {
      var found = resolveDoc(this, id);
      if (!found) return;
      CodeMirror.off(found.doc, "change", this.trackChange);
      delete this.docs[found.name];
      this.server.delFile(found.name);
    }
```
</details>

### `hideDoc(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `closeArgHints`
- `resolveDoc`
- `sendDoc`

<details><summary>Code</summary>

```typescript
function(id) {
      closeArgHints(this);
      var found = resolveDoc(this, id);
      if (found && found.changed) sendDoc(this, found);
    }
```
</details>

### `complete(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.showHint`

<details><summary>Code</summary>

```typescript
function(cm) {
      cm.showHint({hint: this.getHint});
    }
```
</details>

### `showType(cm: any, pos: any, c: any): void`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `showContextInfo`

<details><summary>Code</summary>

```typescript
function(cm, pos, c) { showContextInfo(this, cm, pos, "type", c); }
```
</details>

### `showDocs(cm: any, pos: any, c: any): void`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `showContextInfo`

<details><summary>Code</summary>

```typescript
function(cm, pos, c) { showContextInfo(this, cm, pos, "documentation", c); }
```
</details>

### `updateArgHints(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `updateArgHints`

<details><summary>Code</summary>

```typescript
function(cm) { updateArgHints(this, cm); }
```
</details>

### `jumpToDef(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `jumpToDef`

<details><summary>Code</summary>

```typescript
function(cm) { jumpToDef(this, cm); }
```
</details>

### `jumpBack(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `jumpBack`

<details><summary>Code</summary>

```typescript
function(cm) { jumpBack(this, cm); }
```
</details>

### `rename(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `rename`

<details><summary>Code</summary>

```typescript
function(cm) { rename(this, cm); }
```
</details>

### `selectName(cm: any): void`

**Parameters:**

- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `selectName`

<details><summary>Code</summary>

```typescript
function(cm) { selectName(this, cm); }
```
</details>

### `request(cm: any, query: any, c: any, pos: any): void`

**Parameters:**

- **`cm`** `any`
- **`query`** `any`
- **`c`** `any`
- **`pos`** `any`

**Returns:** `void`

**Calls:**

- `findDoc`
- `cm.getDoc`
- `buildRequest`
- `this.server.request`
- `self.options.responseFilter`
- `c`

<details><summary>Code</summary>

```typescript
function (cm, query, c, pos) {
      var self = this;
      var doc = findDoc(this, cm.getDoc());
      var request = buildRequest(this, doc, query, pos);
      var extraOptions = request.query && this.options.queryOptions && this.options.queryOptions[request.query.type]
      if (extraOptions) for (var prop in extraOptions) request.query[prop] = extraOptions[prop];

      this.server.request(request, function (error, data) {
        if (!error && self.options.responseFilter)
          data = self.options.responseFilter(doc, query, request, error, data);
        c(error, data);
      });
    }
```
</details>

### `destroy(): void`

**Returns:** `void`

**Calls:**

- `closeArgHints`
- `this.worker.terminate`

<details><summary>Code</summary>

```typescript
function () {
      closeArgHints(this)
      if (this.worker) {
        this.worker.terminate();
        this.worker = null;
      }
    }
```
</details>

### `getFile(ts: any, name: any, c: any): void`

**Parameters:**

- **`ts`** `any`
- **`name`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `docValue`
- `ts.options.getFile`

<details><summary>Code</summary>

```typescript
function getFile(ts, name, c) {
    var buf = ts.docs[name];
    if (buf)
      c(docValue(ts, buf));
    else if (ts.options.getFile)
      ts.options.getFile(name, c);
    else
      c(null);
  }
```
</details>

### `findDoc(ts: any, doc: any, name: any): any`

**Parameters:**

- **`ts`** `any`
- **`doc`** `any`
- **`name`** `any`

**Returns:** `any`

**Calls:**

- `ts.addDoc`

<details><summary>Code</summary>

```typescript
function findDoc(ts, doc, name) {
    for (var n in ts.docs) {
      var cur = ts.docs[n];
      if (cur.doc == doc) return cur;
    }
    if (!name) for (var i = 0;; ++i) {
      n = "[doc" + (i || "") + "]";
      if (!ts.docs[n]) { name = n; break; }
    }
    return ts.addDoc(name, doc);
  }
```
</details>

### `resolveDoc(ts: any, id: any): any`

**Parameters:**

- **`ts`** `any`
- **`id`** `any`

**Returns:** `any`

**Calls:**

- `id.getDoc`
- `findDoc`

<details><summary>Code</summary>

```typescript
function resolveDoc(ts, id) {
    if (typeof id == "string") return ts.docs[id];
    if (id instanceof CodeMirror) id = id.getDoc();
    if (id instanceof CodeMirror.Doc) return findDoc(ts, id);
  }
```
</details>

### `trackChange(ts: any, doc: any, change: any): void`

**Parameters:**

- **`ts`** `any`
- **`doc`** `any`
- **`change`** `any`

**Returns:** `void`

**Calls:**

- `findDoc`
- `cmpPos`
- `doc.lineCount`
- `setTimeout`
- `sendDoc`

<details><summary>Code</summary>

```typescript
function trackChange(ts, doc, change) {
    var data = findDoc(ts, doc);

    var argHints = ts.cachedArgHints;
    if (argHints && argHints.doc == doc && cmpPos(argHints.start, change.to) >= 0)
      ts.cachedArgHints = null;

    var changed = data.changed;
    if (changed == null)
      data.changed = changed = {from: change.from.line, to: change.from.line};
    var end = change.from.line + (change.text.length - 1);
    if (change.from.line < changed.to) changed.to = changed.to - (change.to.line - end);
    if (end >= changed.to) changed.to = end + 1;
    if (changed.from > change.from.line) changed.from = change.from.line;

    if (doc.lineCount() > bigDoc && change.to - changed.from > 100) setTimeout(function() {
      if (data.changed && data.changed.to - data.changed.from > 100) sendDoc(ts, data);
    }, 200);
  }
```
</details>

### `sendDoc(ts: any, doc: any): void`

**Parameters:**

- **`ts`** `any`
- **`doc`** `any`

**Returns:** `void`

**Calls:**

- `ts.server.request`
- `docValue`
- `window.console.error`

<details><summary>Code</summary>

```typescript
function sendDoc(ts, doc) {
    ts.server.request({files: [{type: "full", name: doc.name, text: docValue(ts, doc)}]}, function(error) {
      if (error) window.console.error(error);
      else doc.changed = null;
    });
  }
```
</details>

### `hint(ts: any, cm: any, c: any): void`

**Parameters:**

- **`ts`** `any`
- **`cm`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `ts.request`
- `showError`
- `cm.getRange`
- `Pos`
- `typeToIcon`
- `completions.push`
- `CodeMirror.on`
- `remove`
- `ts.options.completionTip`
- `makeTooltip`
- `node.parentNode.getBoundingClientRect`
- `node.getBoundingClientRect`
- `c`

<details><summary>Code</summary>

```typescript
function hint(ts, cm, c) {
    ts.request(cm, {type: "completions", types: true, docs: true, urls: true}, function(error, data) {
      if (error) return showError(ts, cm, error);
      var completions = [], after = "";
      var from = data.start, to = data.end;
      if (cm.getRange(Pos(from.line, from.ch - 2), from) == "[\"" &&
          cm.getRange(to, Pos(to.line, to.ch + 2)) != "\"]")
        after = "\"]";

      for (var i = 0; i < data.completions.length; ++i) {
        var completion = data.completions[i], className = typeToIcon(completion.type);
        if (data.guess) className += " " + cls + "guess";
        completions.push({text: completion.name + after,
                          displayText: completion.displayName || completion.name,
                          className: className,
                          data: completion});
      }

      var obj = {from: from, to: to, list: completions};
      var tooltip = null;
      CodeMirror.on(obj, "close", function() { remove(tooltip); });
      CodeMirror.on(obj, "update", function() { remove(tooltip); });
      CodeMirror.on(obj, "select", function(cur, node) {
        remove(tooltip);
        var content = ts.options.completionTip ? ts.options.completionTip(cur.data) : cur.data.doc;
        if (content) {
          tooltip = makeTooltip(node.parentNode.getBoundingClientRect().right + window.pageXOffset,
                                node.getBoundingClientRect().top + window.pageYOffset, content, cm, cls + "hint-doc");
        }
      });
      c(obj);
    });
  }
```
</details>

### `typeToIcon(type: any): string`

**Parameters:**

- **`type`** `any`

**Returns:** `string`

**Calls:**

- `/^fn\(/.test`
- `/^\[/.test`

<details><summary>Code</summary>

```typescript
function typeToIcon(type) {
    var suffix;
    if (type == "?") suffix = "unknown";
    else if (type == "number" || type == "string" || type == "bool") suffix = type;
    else if (/^fn\(/.test(type)) suffix = "fn";
    else if (/^\[/.test(type)) suffix = "array";
    else suffix = "object";
    return cls + "completion " + cls + "completion-" + suffix;
  }
```
</details>

### `showContextInfo(ts: any, cm: any, pos: any, queryName: any, c: any): void`

**Parameters:**

- **`ts`** `any`
- **`cm`** `any`
- **`pos`** `any`
- **`queryName`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `ts.request`
- `showError`
- `ts.options.typeTip`
- `elt`
- `tip.appendChild`
- `document.createTextNode`
- `tempTooltip`
- `c`

<details><summary>Code</summary>

```typescript
function showContextInfo(ts, cm, pos, queryName, c) {
    ts.request(cm, queryName, function(error, data) {
      if (error) return showError(ts, cm, error);
      if (ts.options.typeTip) {
        var tip = ts.options.typeTip(data);
      } else {
        var tip = elt("span", null, elt("strong", null, data.type || "not found"));
        if (data.doc)
          tip.appendChild(document.createTextNode(" — " + data.doc));
        if (data.url) {
          tip.appendChild(document.createTextNode(" "));
          var child = tip.appendChild(elt("a", null, "[docs]"));
          child.href = data.url;
          child.target = "_blank";
        }
      }
      tempTooltip(cm, tip, ts);
      if (c) c();
    }, pos);
  }
```
</details>

### `updateArgHints(ts: any, cm: any): void`

**Parameters:**

- **`ts`** `any`
- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `closeArgHints`
- `cm.somethingSelected`
- `cm.getTokenAt`
- `cm.getCursor`
- `CodeMirror.innerMode`
- `cm.getMode`
- `cm.getOption`
- `Math.max`
- `cm.getLine`
- `str.indexOf`
- `str.charAt`
- `Pos`
- `cm.getDoc`
- `cmpPos`
- `showArgHints`
- `ts.request`
- `(/^fn\(/).test`
- `parseFnType`

<details><summary>Code</summary>

```typescript
function updateArgHints(ts, cm) {
    closeArgHints(ts);

    if (cm.somethingSelected()) return;
    var state = cm.getTokenAt(cm.getCursor()).state;
    var inner = CodeMirror.innerMode(cm.getMode(), state);
    if (inner.mode.name != "javascript") return;
    var lex = inner.state.lexical;
    if (lex.info != "call") return;

    var ch, argPos = lex.pos || 0, tabSize = cm.getOption("tabSize");
    for (var line = cm.getCursor().line, e = Math.max(0, line - 9), found = false; line >= e; --line) {
      var str = cm.getLine(line), extra = 0;
      for (var pos = 0;;) {
        var tab = str.indexOf("\t", pos);
        if (tab == -1) break;
        extra += tabSize - (tab + extra) % tabSize - 1;
        pos = tab + 1;
      }
      ch = lex.column - extra;
      if (str.charAt(ch) == "(") {found = true; break;}
    }
    if (!found) return;

    var start = Pos(line, ch);
    var cache = ts.cachedArgHints;
    if (cache && cache.doc == cm.getDoc() && cmpPos(start, cache.start) == 0)
      return showArgHints(ts, cm, argPos);

    ts.request(cm, {type: "type", preferFunction: true, end: start}, function(error, data) {
      if (error || !data.type || !(/^fn\(/).test(data.type)) return;
      ts.cachedArgHints = {
        start: start,
        type: parseFnType(data.type),
        name: data.exprName || data.name || "fn",
        guess: data.guess,
        doc: cm.getDoc()
      };
      showArgHints(ts, cm, argPos);
    });
  }
```
</details>

### `showArgHints(ts: any, cm: any, pos: any): void`

**Parameters:**

- **`ts`** `any`
- **`cm`** `any`
- **`pos`** `any`

**Returns:** `void`

**Calls:**

- `closeArgHints`
- `elt`
- `tip.appendChild`
- `document.createTextNode`
- `cm.cursorCoords`
- `makeTooltip`
- `setTimeout`
- `onEditorActivity`

<details><summary>Code</summary>

```typescript
function showArgHints(ts, cm, pos) {
    closeArgHints(ts);

    var cache = ts.cachedArgHints, tp = cache.type;
    var tip = elt("span", cache.guess ? cls + "fhint-guess" : null,
                  elt("span", cls + "fname", cache.name), "(");
    for (var i = 0; i < tp.args.length; ++i) {
      if (i) tip.appendChild(document.createTextNode(", "));
      var arg = tp.args[i];
      tip.appendChild(elt("span", cls + "farg" + (i == pos ? " " + cls + "farg-current" : ""), arg.name || "?"));
      if (arg.type != "?") {
        tip.appendChild(document.createTextNode(":\u00a0"));
        tip.appendChild(elt("span", cls + "type", arg.type));
      }
    }
    tip.appendChild(document.createTextNode(tp.rettype ? ") ->\u00a0" : ")"));
    if (tp.rettype) tip.appendChild(elt("span", cls + "type", tp.rettype));
    var place = cm.cursorCoords(null, "page");
    var tooltip = ts.activeArgHints = makeTooltip(place.right + 1, place.bottom, tip, cm)
    setTimeout(function() {
      tooltip.clear = onEditorActivity(cm, function() {
        if (ts.activeArgHints == tooltip) closeArgHints(ts) })
    }, 20)
  }
```
</details>

### `parseFnType(text: any): { args: { name: any; type: any; }[]; rettype: any; }`

**Parameters:**

- **`text`** `any`

**Returns:** `{ args: { name: any; type: any; }[]; rettype: any; }`

**Calls:**

- `text.charAt`
- `upto.test`
- `text.slice`
- `/[{\[\(]/.test`
- `/[}\]\)]/.test`
- `text.slice(pos).match`
- `args.push`
- `skipMatching`

**Internal Comments:**
```
// Parse arguments
```

<details><summary>Code</summary>

```typescript
function parseFnType(text) {
    var args = [], pos = 3;

    function skipMatching(upto) {
      var depth = 0, start = pos;
      for (;;) {
        var next = text.charAt(pos);
        if (upto.test(next) && !depth) return text.slice(start, pos);
        if (/[{\[\(]/.test(next)) ++depth;
        else if (/[}\]\)]/.test(next)) --depth;
        ++pos;
      }
    }

    // Parse arguments
    if (text.charAt(pos) != ")") for (;;) {
      var name = text.slice(pos).match(/^([^, \(\[\{]+): /);
      if (name) {
        pos += name[0].length;
        name = name[1];
      }
      args.push({name: name, type: skipMatching(/[\),]/)});
      if (text.charAt(pos) == ")") break;
      pos += 2;
    }

    var rettype = text.slice(pos).match(/^\) -> (.*)$/);

    return {args: args, rettype: rettype && rettype[1]};
  }
```
</details>

### `skipMatching(upto: any): any`

**Parameters:**

- **`upto`** `any`

**Returns:** `any`

**Calls:**

- `text.charAt`
- `upto.test`
- `text.slice`
- `/[{\[\(]/.test`
- `/[}\]\)]/.test`

<details><summary>Code</summary>

```typescript
function skipMatching(upto) {
      var depth = 0, start = pos;
      for (;;) {
        var next = text.charAt(pos);
        if (upto.test(next) && !depth) return text.slice(start, pos);
        if (/[{\[\(]/.test(next)) ++depth;
        else if (/[}\]\)]/.test(next)) --depth;
        ++pos;
      }
    }
```
</details>

### `jumpToDef(ts: any, cm: any): void`

**Parameters:**

- **`ts`** `any`
- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `findDoc`
- `cm.getDoc`
- `ts.server.request`
- `buildRequest`
- `showError`
- `window.open`
- `findContext`
- `ts.jumpStack.push`
- `cm.getCursor`
- `moveTo`
- `atInterestingExpression`
- `dialog`
- `inner`

<details><summary>Code</summary>

```typescript
function jumpToDef(ts, cm) {
    function inner(varName) {
      var req = {type: "definition", variable: varName || null};
      var doc = findDoc(ts, cm.getDoc());
      ts.server.request(buildRequest(ts, doc, req), function(error, data) {
        if (error) return showError(ts, cm, error);
        if (!data.file && data.url) { window.open(data.url); return; }

        if (data.file) {
          var localDoc = ts.docs[data.file], found;
          if (localDoc && (found = findContext(localDoc.doc, data))) {
            ts.jumpStack.push({file: doc.name,
                               start: cm.getCursor("from"),
                               end: cm.getCursor("to")});
            moveTo(ts, doc, localDoc, found.start, found.end);
            return;
          }
        }
        showError(ts, cm, "Could not find a definition.");
      });
    }

    if (!atInterestingExpression(cm))
      dialog(cm, "Jump to variable", function(name) { if (name) inner(name); });
    else
      inner();
  }
```
</details>

### `inner(varName: any): void`

**Parameters:**

- **`varName`** `any`

**Returns:** `void`

**Calls:**

- `findDoc`
- `cm.getDoc`
- `ts.server.request`
- `buildRequest`
- `showError`
- `window.open`
- `findContext`
- `ts.jumpStack.push`
- `cm.getCursor`
- `moveTo`

<details><summary>Code</summary>

```typescript
function inner(varName) {
      var req = {type: "definition", variable: varName || null};
      var doc = findDoc(ts, cm.getDoc());
      ts.server.request(buildRequest(ts, doc, req), function(error, data) {
        if (error) return showError(ts, cm, error);
        if (!data.file && data.url) { window.open(data.url); return; }

        if (data.file) {
          var localDoc = ts.docs[data.file], found;
          if (localDoc && (found = findContext(localDoc.doc, data))) {
            ts.jumpStack.push({file: doc.name,
                               start: cm.getCursor("from"),
                               end: cm.getCursor("to")});
            moveTo(ts, doc, localDoc, found.start, found.end);
            return;
          }
        }
        showError(ts, cm, "Could not find a definition.");
      });
    }
```
</details>

### `jumpBack(ts: any, cm: any): void`

**Parameters:**

- **`ts`** `any`
- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `ts.jumpStack.pop`
- `moveTo`
- `findDoc`
- `cm.getDoc`

<details><summary>Code</summary>

```typescript
function jumpBack(ts, cm) {
    var pos = ts.jumpStack.pop(), doc = pos && ts.docs[pos.file];
    if (!doc) return;
    moveTo(ts, findDoc(ts, cm.getDoc()), doc, pos.start, pos.end);
  }
```
</details>

### `moveTo(ts: any, curDoc: any, doc: any, start: any, end: any): void`

**Parameters:**

- **`ts`** `any`
- **`curDoc`** `any`
- **`doc`** `any`
- **`start`** `any`
- **`end`** `any`

**Returns:** `void`

**Calls:**

- `doc.doc.setSelection`
- `closeArgHints`
- `ts.options.switchToDoc`

<details><summary>Code</summary>

```typescript
function moveTo(ts, curDoc, doc, start, end) {
    doc.doc.setSelection(start, end);
    if (curDoc != doc && ts.options.switchToDoc) {
      closeArgHints(ts);
      ts.options.switchToDoc(doc.name, doc.doc);
    }
  }
```
</details>

### `findContext(doc: any, data: any): any`

**Parameters:**

- **`doc`** `any`
- **`data`** `any`

**Returns:** `any`

**Calls:**

- `data.context.slice(0, data.contextOffset).split`
- `Pos`
- `doc.getLine`
- `doc.getLine(startLine).slice`
- `doc.lineCount`
- `text.slice`
- `doc.getSearchCursor`
- `cursor.findNext`
- `cursor.from`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function findContext(doc, data) {
    var before = data.context.slice(0, data.contextOffset).split("\n");
    var startLine = data.start.line - (before.length - 1);
    var start = Pos(startLine, (before.length == 1 ? data.start.ch : doc.getLine(startLine).length) - before[0].length);

    var text = doc.getLine(startLine).slice(start.ch);
    for (var cur = startLine + 1; cur < doc.lineCount() && text.length < data.context.length; ++cur)
      text += "\n" + doc.getLine(cur);
    if (text.slice(0, data.context.length) == data.context) return data;

    var cursor = doc.getSearchCursor(data.context, 0, false);
    var nearest, nearestDist = Infinity;
    while (cursor.findNext()) {
      var from = cursor.from(), dist = Math.abs(from.line - start.line) * 10000;
      if (!dist) dist = Math.abs(from.ch - start.ch);
      if (dist < nearestDist) { nearest = from; nearestDist = dist; }
    }
    if (!nearest) return null;

    if (before.length == 1)
      nearest.ch += before[0].length;
    else
      nearest = Pos(nearest.line + (before.length - 1), before[before.length - 1].length);
    if (data.start.line == data.end.line)
      var end = Pos(nearest.line, nearest.ch + (data.end.ch - data.start.ch));
    else
      var end = Pos(nearest.line + (data.end.line - data.start.line), data.end.ch);
    return {start: nearest, end: end};
  }
```
</details>

### `atInterestingExpression(cm: any): boolean`

**Parameters:**

- **`cm`** `any`

**Returns:** `boolean`

**Calls:**

- `cm.getCursor`
- `cm.getTokenAt`
- `/[\w)\]]/.test`
- `cm.getLine(pos.line).slice`
- `Math.max`

<details><summary>Code</summary>

```typescript
function atInterestingExpression(cm) {
    var pos = cm.getCursor("end"), tok = cm.getTokenAt(pos);
    if (tok.start < pos.ch && tok.type == "comment") return false;
    return /[\w)\]]/.test(cm.getLine(pos.line).slice(Math.max(pos.ch - 1, 0), pos.ch + 1));
  }
```
</details>

### `rename(ts: any, cm: any): void`

**Parameters:**

- **`ts`** `any`
- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `cm.getTokenAt`
- `cm.getCursor`
- `/\w/.test`
- `showError`
- `dialog`
- `ts.request`
- `applyChanges`

<details><summary>Code</summary>

```typescript
function rename(ts, cm) {
    var token = cm.getTokenAt(cm.getCursor());
    if (!/\w/.test(token.string)) return showError(ts, cm, "Not at a variable");
    dialog(cm, "New name for " + token.string, function(newName) {
      ts.request(cm, {type: "rename", newName: newName, fullDocs: true}, function(error, data) {
        if (error) return showError(ts, cm, error);
        applyChanges(ts, data.changes);
      });
    });
  }
```
</details>

### `selectName(ts: any, cm: any): void`

**Parameters:**

- **`ts`** `any`
- **`cm`** `any`

**Returns:** `void`

**Calls:**

- `findDoc`
- `ts.request`
- `showError`
- `cm.getCursor`
- `ranges.push`
- `cmpPos`
- `cm.setSelections`

<details><summary>Code</summary>

```typescript
function selectName(ts, cm) {
    var name = findDoc(ts, cm.doc).name;
    ts.request(cm, {type: "refs"}, function(error, data) {
      if (error) return showError(ts, cm, error);
      var ranges = [], cur = 0;
      var curPos = cm.getCursor();
      for (var i = 0; i < data.refs.length; i++) {
        var ref = data.refs[i];
        if (ref.file == name) {
          ranges.push({anchor: ref.start, head: ref.end});
          if (cmpPos(curPos, ref.start) >= 0 && cmpPos(curPos, ref.end) <= 0)
            cur = ranges.length - 1;
        }
      }
      cm.setSelections(ranges, cur);
    });
  }
```
</details>

### `applyChanges(ts: any, changes: any): void`

**Parameters:**

- **`ts`** `any`
- **`changes`** `any`

**Returns:** `void`

**Calls:**

- `Object.create`
- `(perFile[ch.file] || (perFile[ch.file] = [])).push`
- `chs.sort`
- `cmpPos`
- `known.doc.replaceRange`

<details><summary>Code</summary>

```typescript
function applyChanges(ts, changes) {
    var perFile = Object.create(null);
    for (var i = 0; i < changes.length; ++i) {
      var ch = changes[i];
      (perFile[ch.file] || (perFile[ch.file] = [])).push(ch);
    }
    for (var file in perFile) {
      var known = ts.docs[file], chs = perFile[file];;
      if (!known) continue;
      chs.sort(function(a, b) { return cmpPos(b.start, a.start); });
      var origin = "*rename" + (++nextChangeOrig);
      for (var i = 0; i < chs.length; ++i) {
        var ch = chs[i];
        known.doc.replaceRange(ch.text, ch.start, ch.end, origin);
      }
    }
  }
```
</details>

### `buildRequest(ts: any, doc: any, query: any, pos: any): { query: any; files: ({ type: string; name: any; offsetLines: any; text: any; } | { type: string; name: any; text: any; })[]; }`

**Parameters:**

- **`ts`** `any`
- **`doc`** `any`
- **`query`** `any`
- **`pos`** `any`

**Returns:** `{ query: any; files: ({ type: string; name: any; offsetLines: any; text: any; } | { type: string; name: any; text: any; })[]; }`

**Calls:**

- `doc.doc.getCursor`
- `doc.doc.somethingSelected`
- `doc.doc.lineCount`
- `files.push`
- `getFragmentAround`
- `Pos`
- `docValue`

<details><summary>Code</summary>

```typescript
function buildRequest(ts, doc, query, pos) {
    var files = [], offsetLines = 0, allowFragments = !query.fullDocs;
    if (!allowFragments) delete query.fullDocs;
    if (typeof query == "string") query = {type: query};
    query.lineCharPositions = true;
    if (query.end == null) {
      query.end = pos || doc.doc.getCursor("end");
      if (doc.doc.somethingSelected())
        query.start = doc.doc.getCursor("start");
    }
    var startPos = query.start || query.end;

    if (doc.changed) {
      if (doc.doc.lineCount() > bigDoc && allowFragments !== false &&
          doc.changed.to - doc.changed.from < 100 &&
          doc.changed.from <= startPos.line && doc.changed.to > query.end.line) {
        files.push(getFragmentAround(doc, startPos, query.end));
        query.file = "#0";
        var offsetLines = files[0].offsetLines;
        if (query.start != null) query.start = Pos(query.start.line - -offsetLines, query.start.ch);
        query.end = Pos(query.end.line - offsetLines, query.end.ch);
      } else {
        files.push({type: "full",
                    name: doc.name,
                    text: docValue(ts, doc)});
        query.file = doc.name;
        doc.changed = null;
      }
    } else {
      query.file = doc.name;
    }
    for (var name in ts.docs) {
      var cur = ts.docs[name];
      if (cur.changed && cur != doc) {
        files.push({type: "full", name: cur.name, text: docValue(ts, cur)});
        cur.changed = null;
      }
    }

    return {query: query, files: files};
  }
```
</details>

### `getFragmentAround(data: any, start: any, end: any): { type: string; name: any; offsetLines: any; text: any; }`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`end`** `any`

**Returns:** `{ type: string; name: any; offsetLines: any; text: any; }`

**Calls:**

- `Math.max`
- `doc.getLine`
- `line.search`
- `CodeMirror.countColumn`
- `Math.min`
- `doc.lastLine`
- `Pos`
- `doc.getRange`

<details><summary>Code</summary>

```typescript
function getFragmentAround(data, start, end) {
    var doc = data.doc;
    var minIndent = null, minLine = null, endLine, tabSize = 4;
    for (var p = start.line - 1, min = Math.max(0, p - 50); p >= min; --p) {
      var line = doc.getLine(p), fn = line.search(/\bfunction\b/);
      if (fn < 0) continue;
      var indent = CodeMirror.countColumn(line, null, tabSize);
      if (minIndent != null && minIndent <= indent) continue;
      minIndent = indent;
      minLine = p;
    }
    if (minLine == null) minLine = min;
    var max = Math.min(doc.lastLine(), end.line + 20);
    if (minIndent == null || minIndent == CodeMirror.countColumn(doc.getLine(start.line), null, tabSize))
      endLine = max;
    else for (endLine = end.line + 1; endLine < max; ++endLine) {
      var indent = CodeMirror.countColumn(doc.getLine(endLine), null, tabSize);
      if (indent <= minIndent) break;
    }
    var from = Pos(minLine, 0);

    return {type: "part",
            name: data.name,
            offsetLines: from.line,
            text: doc.getRange(from, Pos(endLine, end.line == endLine ? null : 0))};
  }
```
</details>

### `elt(tagname: any, cls: any): any`

**Parameters:**

- **`tagname`** `any`
- **`cls`** `any`

**Returns:** `any`

**Calls:**

- `document.createElement`
- `document.createTextNode`
- `e.appendChild`

<details><summary>Code</summary>

```typescript
function elt(tagname, cls /*, ... elts*/) {
    var e = document.createElement(tagname);
    if (cls) e.className = cls;
    for (var i = 2; i < arguments.length; ++i) {
      var elt = arguments[i];
      if (typeof elt == "string") elt = document.createTextNode(elt);
      e.appendChild(elt);
    }
    return e;
  }
```
</details>

### `dialog(cm: any, text: any, f: any): void`

**Parameters:**

- **`cm`** `any`
- **`text`** `any`
- **`f`** `any`

**Returns:** `void`

**Calls:**

- `cm.openDialog`
- `f`
- `prompt`

<details><summary>Code</summary>

```typescript
function dialog(cm, text, f) {
    if (cm.openDialog)
      cm.openDialog(text + ": <input type=text>", f);
    else
      f(prompt(text, ""));
  }
```
</details>

### `tempTooltip(cm: any, content: any, ts: any): void`

**Parameters:**

- **`cm`** `any`
- **`content`** `any`
- **`ts`** `any`

**Returns:** `void`

**Calls:**

- `remove`
- `cm.cursorCoords`
- `makeTooltip`
- `clear`
- `fadeOut`
- `clearActivity`
- `CodeMirror.on`
- `CodeMirror.contains`
- `setTimeout`
- `onEditorActivity`

<details><summary>Code</summary>

```typescript
function tempTooltip(cm, content, ts) {
    if (cm.state.ternTooltip) remove(cm.state.ternTooltip);
    var where = cm.cursorCoords();
    var tip = cm.state.ternTooltip = makeTooltip(where.right + 1, where.bottom, content, cm);
    function maybeClear() {
      old = true;
      if (!mouseOnTip) clear();
    }
    function clear() {
      cm.state.ternTooltip = null;
      if (tip.parentNode) fadeOut(tip)
      clearActivity()
    }
    var mouseOnTip = false, old = false;
    CodeMirror.on(tip, "mousemove", function() { mouseOnTip = true; });
    CodeMirror.on(tip, "mouseout", function(e) {
      var related = e.relatedTarget || e.toElement
      if (!related || !CodeMirror.contains(tip, related)) {
        if (old) clear();
        else mouseOnTip = false;
      }
    });
    setTimeout(maybeClear, ts.options.hintDelay ? ts.options.hintDelay : 1700);
    var clearActivity = onEditorActivity(cm, clear)
  }
```
</details>

### `maybeClear(): void`

**Returns:** `void`

**Calls:**

- `clear`

<details><summary>Code</summary>

```typescript
function maybeClear() {
      old = true;
      if (!mouseOnTip) clear();
    }
```
</details>

### `clear(): void`

**Returns:** `void`

**Calls:**

- `fadeOut`
- `clearActivity`

<details><summary>Code</summary>

```typescript
function clear() {
      cm.state.ternTooltip = null;
      if (tip.parentNode) fadeOut(tip)
      clearActivity()
    }
```
</details>

### `onEditorActivity(cm: any, f: any): () => void`

**Parameters:**

- **`cm`** `any`
- **`f`** `any`

**Returns:** `() => void`

**Calls:**

- `cm.on`
- `cm.off`

<details><summary>Code</summary>

```typescript
function onEditorActivity(cm, f) {
    cm.on("cursorActivity", f)
    cm.on("blur", f)
    cm.on("scroll", f)
    cm.on("setDoc", f)
    return function() {
      cm.off("cursorActivity", f)
      cm.off("blur", f)
      cm.off("scroll", f)
      cm.off("setDoc", f)
    }
  }
```
</details>

### `makeTooltip(x: any, y: any, content: any, cm: any, className: any): any`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`content`** `any`
- **`cm`** `any`
- **`className`** `any`

**Returns:** `any`

**Calls:**

- `elt`
- `container.appendChild`
- `cm.cursorCoords`
- `node.getBoundingClientRect`
- `document.querySelector`

<details><summary>Code</summary>

```typescript
function makeTooltip(x, y, content, cm, className) {
    var node = elt("div", cls + "tooltip" + " " + (className || ""), content);
    node.style.left = x + "px";
    node.style.top = y + "px";
    var container = ((cm.options || {}).hintOptions || {}).container || document.body;
    container.appendChild(node);

    var pos = cm.cursorCoords();
    var winW = window.innerWidth;
    var winH = window.innerHeight;
    var box = node.getBoundingClientRect();
    var hints = document.querySelector(".CodeMirror-hints");
    var overlapY = box.bottom - winH;
    var overlapX = box.right - winW;

    if (hints && overlapX > 0) {
      node.style.left = 0;
      var box = node.getBoundingClientRect();
      node.style.left = (x = x - hints.offsetWidth - box.width) + "px";
      overlapX = box.right - winW;
    }
    if (overlapY > 0) {
      var height = box.bottom - box.top, curTop = pos.top - (pos.bottom - box.top);
      if (curTop - height > 0) { // Fits above cursor
        node.style.top = (pos.top - height) + "px";
      } else if (height > winH) {
        node.style.height = (winH - 5) + "px";
        node.style.top = (pos.bottom - box.top) + "px";
      }
    }
    if (overlapX > 0) {
      if (box.right - box.left > winW) {
        node.style.width = (winW - 5) + "px";
        overlapX -= (box.right - box.left) - winW;
      }
      node.style.left = (x - overlapX) + "px";
    }

    return node;
  }
```
</details>

### `remove(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `p.removeChild`

<details><summary>Code</summary>

```typescript
function remove(node) {
    var p = node && node.parentNode;
    if (p) p.removeChild(node);
  }
```
</details>

### `fadeOut(tooltip: any): void`

**Parameters:**

- **`tooltip`** `any`

**Returns:** `void`

**Calls:**

- `setTimeout`
- `remove`

<details><summary>Code</summary>

```typescript
function fadeOut(tooltip) {
    tooltip.style.opacity = "0";
    setTimeout(function() { remove(tooltip); }, 1100);
  }
```
</details>

### `showError(ts: any, cm: any, msg: any): void`

**Parameters:**

- **`ts`** `any`
- **`cm`** `any`
- **`msg`** `any`

**Returns:** `void`

**Calls:**

- `ts.options.showError`
- `tempTooltip`
- `String`

<details><summary>Code</summary>

```typescript
function showError(ts, cm, msg) {
    if (ts.options.showError)
      ts.options.showError(cm, msg);
    else
      tempTooltip(cm, String(msg), ts);
  }
```
</details>

### `closeArgHints(ts: any): void`

**Parameters:**

- **`ts`** `any`

**Returns:** `void`

**Calls:**

- `ts.activeArgHints.clear`
- `remove`

<details><summary>Code</summary>

```typescript
function closeArgHints(ts) {
    if (ts.activeArgHints) {
      if (ts.activeArgHints.clear) ts.activeArgHints.clear()
      remove(ts.activeArgHints)
      ts.activeArgHints = null
    }
  }
```
</details>

### `docValue(ts: any, doc: any): any`

**Parameters:**

- **`ts`** `any`
- **`doc`** `any`

**Returns:** `any`

**Calls:**

- `doc.doc.getValue`
- `ts.options.fileFilter`

<details><summary>Code</summary>

```typescript
function docValue(ts, doc) {
    var val = doc.doc.getValue();
    if (ts.options.fileFilter) val = ts.options.fileFilter(val, doc.name, doc.doc);
    return val;
  }
```
</details>

### `WorkerServer(ts: any): void`

**Parameters:**

- **`ts`** `any`

**Returns:** `void`

**Calls:**

- `worker.postMessage`
- `getFile`
- `send`
- `String`
- `window.console.log`
- `complex_call_25769`
- `complex_call_25921`

<details><summary>Code</summary>

```typescript
function WorkerServer(ts) {
    var worker = ts.worker = new Worker(ts.options.workerScript);
    worker.postMessage({type: "init",
                        defs: ts.options.defs,
                        plugins: ts.options.plugins,
                        scripts: ts.options.workerDeps});
    var msgId = 0, pending = {};

    function send(data, c) {
      if (c) {
        data.id = ++msgId;
        pending[msgId] = c;
      }
      worker.postMessage(data);
    }
    worker.onmessage = function(e) {
      var data = e.data;
      if (data.type == "getFile") {
        getFile(ts, data.name, function(err, text) {
          send({type: "getFile", err: String(err), text: text, id: data.id});
        });
      } else if (data.type == "debug") {
        window.console.log(data.message);
      } else if (data.id && pending[data.id]) {
        pending[data.id](data.err, data.body);
        delete pending[data.id];
      }
    };
    worker.onerror = function(e) {
      for (var id in pending) pending[id](e);
      pending = {};
    };

    this.addFile = function(name, text) { send({type: "add", name: name, text: text}); };
    this.delFile = function(name) { send({type: "del", name: name}); };
    this.request = function(body, c) { send({type: "req", body: body}, c); };
  }
```
</details>

### `send(data: any, c: any): void`

**Parameters:**

- **`data`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `worker.postMessage`

<details><summary>Code</summary>

```typescript
function send(data, c) {
      if (c) {
        data.id = ++msgId;
        pending[msgId] = c;
      }
      worker.postMessage(data);
    }
```
</details>


---