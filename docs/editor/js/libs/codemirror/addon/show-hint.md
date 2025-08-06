[⬅️ Back to Table of Contents](../../../../../index.md)

# 📄 `show-hint.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 88 |
| 📊 Variables & Constants | 64 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/codemirror/addon/show-hint.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `HINT_ELEMENT_CLASS` | `string` | let/var | `"CodeMirror-hint"` | ✗ |
| `ACTIVE_HINT_ELEMENT_CLASS` | `string` | let/var | `"CodeMirror-hint-active"` | ✗ |
| `newOpts` | `{ hint: any; }` | let/var | `{hint: getHints}` | ✗ |
| `completion` | `Completion` | let/var | `this.state.completionActive = new Completion(this, options)` | ✗ |
| `self` | `this` | let/var | `this` | ✗ |
| `requestAnimationFrame` | `(fn: any) => Timeout` | let/var | `window.requestAnimationFrame \|\| function(fn) { return setTimeout(fn, 1000/6...` | ✗ |
| `cancelAnimationFrame` | `{ (id: number): void; (timeout: strin...` | let/var | `window.cancelAnimationFrame \|\| clearTimeout` | ✗ |
| `completion` | `any` | let/var | `data.list[i]` | ✗ |
| `self` | `this` | let/var | `this` | ✗ |
| `identStart` | `any` | let/var | `this.startPos` | ✗ |
| `self` | `this` | let/var | `this` | ✗ |
| `self` | `this` | let/var | `this` | ✗ |
| `myTick` | `number` | let/var | `++this.tick` | ✗ |
| `picked` | `any` | let/var | `(this.widget && this.widget.picked) \|\| (first && this.options.completeSingle)` | ✗ |
| `editor` | `any` | let/var | `cm.options.hintOptions` | ✗ |
| `out` | `{ hint: any; }` | let/var | `{}` | ✗ |
| `baseMap` | `{ Up: () => void; Down: () => void; P...` | let/var | `{ Up: function() {handle.moveFocus(-1);}, Down: function() {handle.moveFocus(...` | ✗ |
| `custom` | `any` | let/var | `completion.options.customKeys` | ✗ |
| `ourMap` | `{}` | let/var | `custom ? {} : baseMap` | ✗ |
| `bound` | `any` | let/var | `*not shown*` | ✗ |
| `extra` | `any` | let/var | `completion.options.extraKeys` | ✗ |
| `widget` | `this` | let/var | `this` | ✗ |
| `cm` | `any` | let/var | `completion.cm` | ✗ |
| `ownerDocument` | `any` | let/var | `cm.getInputField().ownerDocument` | ✗ |
| `parentWindow` | `any` | let/var | `ownerDocument.defaultView \|\| ownerDocument.parentWindow` | ✗ |
| `hints` | `any` | let/var | `this.hints = ownerDocument.createElement("ul")` | ✗ |
| `theme` | `any` | let/var | `completion.cm.options.theme` | ✗ |
| `completions` | `any` | let/var | `data.list` | ✗ |
| `cur` | `any` | let/var | `completions[i]` | ✗ |
| `className` | `string` | let/var | `HINT_ELEMENT_CLASS + (i != this.selectedHint ? "" : " " + ACTIVE_HINT_ELEMENT...` | ✗ |
| `container` | `any` | let/var | `completion.options.container \|\| ownerDocument.body` | ✗ |
| `left` | `any` | let/var | `pos.left` | ✗ |
| `top` | `any` | let/var | `pos.bottom` | ✗ |
| `below` | `boolean` | let/var | `true` | ✗ |
| `offsetLeft` | `number` | let/var | `0` | ✗ |
| `offsetTop` | `number` | let/var | `0` | ✗ |
| `isContainerPositioned` | `boolean` | let/var | `['absolute', 'relative', 'fixed'].indexOf(parentWindow.getComputedStyle(conta...` | ✗ |
| `offsetParent` | `any` | let/var | `isContainerPositioned ? container : container.offsetParent` | ✗ |
| `winW` | `any` | let/var | `parentWindow.innerWidth \|\| Math.max(ownerDocument.body.offsetWidth, ownerDo...` | ✗ |
| `winH` | `any` | let/var | `parentWindow.innerHeight \|\| Math.max(ownerDocument.body.offsetHeight, owner...` | ✗ |
| `box` | `any` | let/var | `completion.options.moveOnOverlap ? hints.getBoundingClientRect() : new DOMRect()` | ✗ |
| `scrolls` | `boolean` | let/var | `completion.options.paddingForScrollbar ? hints.scrollHeight > hints.clientHei...` | ✗ |
| `startScroll` | `any` | let/var | `*not shown*` | ✗ |
| `overlapY` | `number` | let/var | `box.bottom - winH` | ✗ |
| `height` | `number` | let/var | `box.bottom - box.top` | ✗ |
| `curTop` | `number` | let/var | `pos.top - (pos.bottom - box.top)` | ✗ |
| `overlapX` | `number` | let/var | `box.right - winW` | ✗ |
| `closingOnBlur` | `any` | let/var | `*not shown*` | ✗ |
| `newTop` | `number` | let/var | `top + startScroll.top - curScroll.top` | ✗ |
| `point` | `number` | let/var | `newTop - (parentWindow.pageYOffset \|\| (ownerDocument.documentElement \|\| o...` | ✗ |
| `cm` | `any` | let/var | `this.completion.cm` | ✗ |
| `widget` | `this` | let/var | `this` | ✗ |
| `node` | `any` | let/var | `this.hints.childNodes[this.selectedHint]` | ✗ |
| `node1` | `any` | let/var | `this.hints.childNodes[selectedHintRange.from]` | ✗ |
| `node2` | `any` | let/var | `this.hints.childNodes[selectedHintRange.to]` | ✗ |
| `firstNode` | `any` | let/var | `this.hints.firstChild` | ✗ |
| `margin` | `any` | let/var | `this.completion.options.scrollMargin \|\| 0` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `words` | `any` | let/var | `*not shown*` | ✗ |
| `term` | `any` | let/var | `*not shown*` | ✗ |
| `to` | `any` | let/var | `cur` | ✗ |
| `found` | `any[]` | let/var | `[]` | ✗ |
| `word` | `any` | let/var | `options.words[i]` | ✗ |
| `defaultOptions` | `{ hint: any; completeSingle: boolean;...` | let/var | `{ hint: CodeMirror.hint.auto, completeSingle: true, alignWithWord: true, clos...` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `fetchHints` | *none* | result.then, result.then |


---

## Functions

### `Completion(cm: any, options: any): void`

**Parameters:**

- **`cm`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `this.cm.getCursor`
- `this.cm.getLine`
- `this.cm.getSelection`
- `cm.on`
- `self.cursorActivity`

<details><summary>Code</summary>

```typescript
function Completion(cm, options) {
    this.cm = cm;
    this.options = options;
    this.widget = null;
    this.debounce = 0;
    this.tick = 0;
    this.startPos = this.cm.getCursor("start");
    this.startLen = this.cm.getLine(this.startPos.line).length - this.cm.getSelection().length;

    if (this.options.updateOnCursorActivity) {
      var self = this;
      cm.on("cursorActivity", this.activityFunc = function() { self.cursorActivity(); });
    }
  }
```
</details>

### `close(): void`

**Returns:** `void`

**Calls:**

- `this.active`
- `this.cm.off`
- `CodeMirror.signal`
- `this.widget.close`

<details><summary>Code</summary>

```typescript
function() {
      if (!this.active()) return;
      this.cm.state.completionActive = null;
      this.tick = null;
      if (this.options.updateOnCursorActivity) {
        this.cm.off("cursorActivity", this.activityFunc);
      }

      if (this.widget && this.data) CodeMirror.signal(this.data, "close");
      if (this.widget) this.widget.close();
      CodeMirror.signal(this.cm, "endCompletion", this.cm);
    }
```
</details>

### `active(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() {
      return this.cm.state.completionActive == this;
    }
```
</details>

### `pick(data: any, i: any): void`

**Parameters:**

- **`data`** `any`
- **`i`** `any`

**Returns:** `void`

**Calls:**

- `this.cm.operation`
- `completion.hint`
- `self.cm.replaceRange`
- `getText`
- `CodeMirror.signal`
- `self.cm.scrollIntoView`
- `this.close`

<details><summary>Code</summary>

```typescript
function(data, i) {
      var completion = data.list[i], self = this;
      this.cm.operation(function() {
        if (completion.hint)
          completion.hint(self.cm, data, completion);
        else
          self.cm.replaceRange(getText(completion), completion.from || data.from,
                               completion.to || data.to, "complete");
        CodeMirror.signal(data, "pick", completion);
        self.cm.scrollIntoView();
      });
      if (this.options.closeOnPick) {
        this.close();
      }
    }
```
</details>

### `cursorActivity(): void`

**Returns:** `void`

**Calls:**

- `cancelAnimationFrame`
- `this.cm.getCursor`
- `this.cm.getLine`
- `this.cm.somethingSelected`
- `this.options.closeCharacters.test`
- `line.charAt`
- `this.close`
- `requestAnimationFrame`
- `self.update`
- `this.widget.disable`

<details><summary>Code</summary>

```typescript
function() {
      if (this.debounce) {
        cancelAnimationFrame(this.debounce);
        this.debounce = 0;
      }

      var identStart = this.startPos;
      if(this.data) {
        identStart = this.data.from;
      }

      var pos = this.cm.getCursor(), line = this.cm.getLine(pos.line);
      if (pos.line != this.startPos.line || line.length - pos.ch != this.startLen - this.startPos.ch ||
          pos.ch < identStart.ch || this.cm.somethingSelected() ||
          (!pos.ch || this.options.closeCharacters.test(line.charAt(pos.ch - 1)))) {
        this.close();
      } else {
        var self = this;
        this.debounce = requestAnimationFrame(function() {self.update();});
        if (this.widget) this.widget.disable();
      }
    }
```
</details>

### `update(first: any): void`

**Parameters:**

- **`first`** `any`

**Returns:** `void`

**Calls:**

- `fetchHints`
- `self.finishUpdate`

<details><summary>Code</summary>

```typescript
function(first) {
      if (this.tick == null) return
      var self = this, myTick = ++this.tick
      fetchHints(this.options.hint, this.cm, this.options, function(data) {
        if (self.tick == myTick) self.finishUpdate(data, first)
      })
    }
```
</details>

### `finishUpdate(data: any, first: any): void`

**Parameters:**

- **`data`** `any`
- **`first`** `any`

**Returns:** `void`

**Calls:**

- `CodeMirror.signal`
- `this.widget.close`
- `this.pick`

<details><summary>Code</summary>

```typescript
function(data, first) {
      if (this.data) CodeMirror.signal(this.data, "update");

      var picked = (this.widget && this.widget.picked) || (first && this.options.completeSingle);
      if (this.widget) this.widget.close();

      this.data = data;

      if (data && data.list.length) {
        if (picked && data.list.length == 1) {
          this.pick(data, 0);
        } else {
          this.widget = new Widget(this, data);
          CodeMirror.signal(data, "shown");
        }
      }
    }
```
</details>

### `close(): void`

**Returns:** `void`

**Calls:**

- `this.active`
- `this.cm.off`
- `CodeMirror.signal`
- `this.widget.close`

<details><summary>Code</summary>

```typescript
function() {
      if (!this.active()) return;
      this.cm.state.completionActive = null;
      this.tick = null;
      if (this.options.updateOnCursorActivity) {
        this.cm.off("cursorActivity", this.activityFunc);
      }

      if (this.widget && this.data) CodeMirror.signal(this.data, "close");
      if (this.widget) this.widget.close();
      CodeMirror.signal(this.cm, "endCompletion", this.cm);
    }
```
</details>

### `active(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() {
      return this.cm.state.completionActive == this;
    }
```
</details>

### `pick(data: any, i: any): void`

**Parameters:**

- **`data`** `any`
- **`i`** `any`

**Returns:** `void`

**Calls:**

- `this.cm.operation`
- `completion.hint`
- `self.cm.replaceRange`
- `getText`
- `CodeMirror.signal`
- `self.cm.scrollIntoView`
- `this.close`

<details><summary>Code</summary>

```typescript
function(data, i) {
      var completion = data.list[i], self = this;
      this.cm.operation(function() {
        if (completion.hint)
          completion.hint(self.cm, data, completion);
        else
          self.cm.replaceRange(getText(completion), completion.from || data.from,
                               completion.to || data.to, "complete");
        CodeMirror.signal(data, "pick", completion);
        self.cm.scrollIntoView();
      });
      if (this.options.closeOnPick) {
        this.close();
      }
    }
```
</details>

### `cursorActivity(): void`

**Returns:** `void`

**Calls:**

- `cancelAnimationFrame`
- `this.cm.getCursor`
- `this.cm.getLine`
- `this.cm.somethingSelected`
- `this.options.closeCharacters.test`
- `line.charAt`
- `this.close`
- `requestAnimationFrame`
- `self.update`
- `this.widget.disable`

<details><summary>Code</summary>

```typescript
function() {
      if (this.debounce) {
        cancelAnimationFrame(this.debounce);
        this.debounce = 0;
      }

      var identStart = this.startPos;
      if(this.data) {
        identStart = this.data.from;
      }

      var pos = this.cm.getCursor(), line = this.cm.getLine(pos.line);
      if (pos.line != this.startPos.line || line.length - pos.ch != this.startLen - this.startPos.ch ||
          pos.ch < identStart.ch || this.cm.somethingSelected() ||
          (!pos.ch || this.options.closeCharacters.test(line.charAt(pos.ch - 1)))) {
        this.close();
      } else {
        var self = this;
        this.debounce = requestAnimationFrame(function() {self.update();});
        if (this.widget) this.widget.disable();
      }
    }
```
</details>

### `update(first: any): void`

**Parameters:**

- **`first`** `any`

**Returns:** `void`

**Calls:**

- `fetchHints`
- `self.finishUpdate`

<details><summary>Code</summary>

```typescript
function(first) {
      if (this.tick == null) return
      var self = this, myTick = ++this.tick
      fetchHints(this.options.hint, this.cm, this.options, function(data) {
        if (self.tick == myTick) self.finishUpdate(data, first)
      })
    }
```
</details>

### `finishUpdate(data: any, first: any): void`

**Parameters:**

- **`data`** `any`
- **`first`** `any`

**Returns:** `void`

**Calls:**

- `CodeMirror.signal`
- `this.widget.close`
- `this.pick`

<details><summary>Code</summary>

```typescript
function(data, first) {
      if (this.data) CodeMirror.signal(this.data, "update");

      var picked = (this.widget && this.widget.picked) || (first && this.options.completeSingle);
      if (this.widget) this.widget.close();

      this.data = data;

      if (data && data.list.length) {
        if (picked && data.list.length == 1) {
          this.pick(data, 0);
        } else {
          this.widget = new Widget(this, data);
          CodeMirror.signal(data, "shown");
        }
      }
    }
```
</details>

### `parseOptions(cm: any, pos: any, options: any): { hint: any; }`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`
- **`options`** `any`

**Returns:** `{ hint: any; }`

**Calls:**

- `out.hint.resolve`

<details><summary>Code</summary>

```typescript
function parseOptions(cm, pos, options) {
    var editor = cm.options.hintOptions;
    var out = {};
    for (var prop in defaultOptions) out[prop] = defaultOptions[prop];
    if (editor) for (var prop in editor)
      if (editor[prop] !== undefined) out[prop] = editor[prop];
    if (options) for (var prop in options)
      if (options[prop] !== undefined) out[prop] = options[prop];
    if (out.hint.resolve) out.hint = out.hint.resolve(cm, pos)
    return out;
  }
```
</details>

### `getText(completion: any): any`

**Parameters:**

- **`completion`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getText(completion) {
    if (typeof completion == "string") return completion;
    else return completion.text;
  }
```
</details>

### `buildKeyMap(completion: any, handle: any): {}`

**Parameters:**

- **`completion`** `any`
- **`handle`** `any`

**Returns:** `{}`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`
- `handle.setFocus`
- `/Mac/.test`
- `val`
- `baseMap.hasOwnProperty`
- `custom.hasOwnProperty`
- `addBinding`
- `extra.hasOwnProperty`

<details><summary>Code</summary>

```typescript
function buildKeyMap(completion, handle) {
    var baseMap = {
      Up: function() {handle.moveFocus(-1);},
      Down: function() {handle.moveFocus(1);},
      PageUp: function() {handle.moveFocus(-handle.menuSize() + 1, true);},
      PageDown: function() {handle.moveFocus(handle.menuSize() - 1, true);},
      Home: function() {handle.setFocus(0);},
      End: function() {handle.setFocus(handle.length - 1);},
      Enter: handle.pick,
      Tab: handle.pick,
      Esc: handle.close
    };

    var mac = /Mac/.test(navigator.platform);

    if (mac) {
      baseMap["Ctrl-P"] = function() {handle.moveFocus(-1);};
      baseMap["Ctrl-N"] = function() {handle.moveFocus(1);};
    }

    var custom = completion.options.customKeys;
    var ourMap = custom ? {} : baseMap;
    function addBinding(key, val) {
      var bound;
      if (typeof val != "string")
        bound = function(cm) { return val(cm, handle); };
      // This mechanism is deprecated
      else if (baseMap.hasOwnProperty(val))
        bound = baseMap[val];
      else
        bound = val;
      ourMap[key] = bound;
    }
    if (custom)
      for (var key in custom) if (custom.hasOwnProperty(key))
        addBinding(key, custom[key]);
    var extra = completion.options.extraKeys;
    if (extra)
      for (var key in extra) if (extra.hasOwnProperty(key))
        addBinding(key, extra[key]);
    return ourMap;
  }
```
</details>

### `Up(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-1);}
```
</details>

### `Down(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(1);}
```
</details>

### `PageUp(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-handle.menuSize() + 1, true);}
```
</details>

### `PageDown(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(handle.menuSize() - 1, true);}
```
</details>

### `Home(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(0);}
```
</details>

### `End(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(handle.length - 1);}
```
</details>

### `Up(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-1);}
```
</details>

### `Down(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(1);}
```
</details>

### `PageUp(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-handle.menuSize() + 1, true);}
```
</details>

### `PageDown(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(handle.menuSize() - 1, true);}
```
</details>

### `Home(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(0);}
```
</details>

### `End(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(handle.length - 1);}
```
</details>

### `Up(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-1);}
```
</details>

### `Down(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(1);}
```
</details>

### `PageUp(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-handle.menuSize() + 1, true);}
```
</details>

### `PageDown(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(handle.menuSize() - 1, true);}
```
</details>

### `Home(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(0);}
```
</details>

### `End(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(handle.length - 1);}
```
</details>

### `Up(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-1);}
```
</details>

### `Down(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(1);}
```
</details>

### `PageUp(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-handle.menuSize() + 1, true);}
```
</details>

### `PageDown(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(handle.menuSize() - 1, true);}
```
</details>

### `Home(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(0);}
```
</details>

### `End(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(handle.length - 1);}
```
</details>

### `Up(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-1);}
```
</details>

### `Down(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(1);}
```
</details>

### `PageUp(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-handle.menuSize() + 1, true);}
```
</details>

### `PageDown(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(handle.menuSize() - 1, true);}
```
</details>

### `Home(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(0);}
```
</details>

### `End(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(handle.length - 1);}
```
</details>

### `Up(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-1);}
```
</details>

### `Down(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(1);}
```
</details>

### `PageUp(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(-handle.menuSize() + 1, true);}
```
</details>

### `PageDown(): void`

**Returns:** `void`

**Calls:**

- `handle.moveFocus`
- `handle.menuSize`

<details><summary>Code</summary>

```typescript
function() {handle.moveFocus(handle.menuSize() - 1, true);}
```
</details>

### `Home(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(0);}
```
</details>

### `End(): void`

**Returns:** `void`

**Calls:**

- `handle.setFocus`

<details><summary>Code</summary>

```typescript
function() {handle.setFocus(handle.length - 1);}
```
</details>

### `addBinding(key: any, val: any): void`

**Parameters:**

- **`key`** `any`
- **`val`** `any`

**Returns:** `void`

**Calls:**

- `val`
- `baseMap.hasOwnProperty`

<details><summary>Code</summary>

```typescript
function addBinding(key, val) {
      var bound;
      if (typeof val != "string")
        bound = function(cm) { return val(cm, handle); };
      // This mechanism is deprecated
      else if (baseMap.hasOwnProperty(val))
        bound = baseMap[val];
      else
        bound = val;
      ourMap[key] = bound;
    }
```
</details>

### `getHintElement(hintsElement: any, el: any): any`

**Parameters:**

- **`hintsElement`** `any`
- **`el`** `any`

**Returns:** `any`

**Calls:**

- `el.nodeName.toUpperCase`

<details><summary>Code</summary>

```typescript
function getHintElement(hintsElement, el) {
    while (el && el != hintsElement) {
      if (el.nodeName.toUpperCase() === "LI" && el.parentNode == hintsElement) return el;
      el = el.parentNode;
    }
  }
```
</details>

### `Widget(completion: any, data: any): boolean`

**Parameters:**

- **`completion`** `any`
- **`data`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.floor`
- `Math.random`
- `cm.getInputField`
- `ownerDocument.createElement`
- `hints.setAttribute`
- `hints.appendChild`
- `elt.setAttribute`
- `cur.render`
- `elt.appendChild`
- `ownerDocument.createTextNode`
- `getText`
- `cm.cursorCoords`
- `['absolute', 'relative', 'fixed'].indexOf`
- `parentWindow.getComputedStyle`
- `offsetParent.getBoundingClientRect`
- `ownerDocument.body.getBoundingClientRect`
- `Math.max`
- `container.appendChild`
- `cm.getInputField().setAttribute`
- `hints.getBoundingClientRect`
- `setTimeout`
- `cm.getScrollInfo`
- `cm.getCursor`
- `cm.addKeyMap`
- `buildKeyMap`
- `widget.changeActive`
- `widget.screenAmount`
- `completion.close`
- `widget.pick`
- `cm.on`
- `clearTimeout`
- `cm.getWrapperElement().getBoundingClientRect`
- `CodeMirror.on`
- `getHintElement`
- `cm.focus`
- `this.getSelectedHintRange`
- `this.scrollToActive`
- `CodeMirror.signal`

**Internal Comments:**
```
// We offset the cursor position because left and top are relative to the offsetParent's top left corner. (x2)
// If we're at the edge of the screen, then we want the menu to appear on the left of the cursor. (x2)
// Compute in the timeout to avoid reflow on init (x2)
// The first hint doesn't need to be scrolled to on init (x2)
```

<details><summary>Code</summary>

```typescript
function Widget(completion, data) {
    this.id = "cm-complete-" + Math.floor(Math.random(1e6))
    this.completion = completion;
    this.data = data;
    this.picked = false;
    var widget = this, cm = completion.cm;
    var ownerDocument = cm.getInputField().ownerDocument;
    var parentWindow = ownerDocument.defaultView || ownerDocument.parentWindow;

    var hints = this.hints = ownerDocument.createElement("ul");
    hints.setAttribute("role", "listbox")
    hints.setAttribute("aria-expanded", "true")
    hints.id = this.id
    var theme = completion.cm.options.theme;
    hints.className = "CodeMirror-hints " + theme;
    this.selectedHint = data.selectedHint || 0;

    var completions = data.list;
    for (var i = 0; i < completions.length; ++i) {
      var elt = hints.appendChild(ownerDocument.createElement("li")), cur = completions[i];
      var className = HINT_ELEMENT_CLASS + (i != this.selectedHint ? "" : " " + ACTIVE_HINT_ELEMENT_CLASS);
      if (cur.className != null) className = cur.className + " " + className;
      elt.className = className;
      if (i == this.selectedHint) elt.setAttribute("aria-selected", "true")
      elt.id = this.id + "-" + i
      elt.setAttribute("role", "option")
      if (cur.render) cur.render(elt, data, cur);
      else elt.appendChild(ownerDocument.createTextNode(cur.displayText || getText(cur)));
      elt.hintId = i;
    }

    var container = completion.options.container || ownerDocument.body;
    var pos = cm.cursorCoords(completion.options.alignWithWord ? data.from : null);
    var left = pos.left, top = pos.bottom, below = true;
    var offsetLeft = 0, offsetTop = 0;
    if (container !== ownerDocument.body) {
      // We offset the cursor position because left and top are relative to the offsetParent's top left corner.
      var isContainerPositioned = ['absolute', 'relative', 'fixed'].indexOf(parentWindow.getComputedStyle(container).position) !== -1;
      var offsetParent = isContainerPositioned ? container : container.offsetParent;
      var offsetParentPosition = offsetParent.getBoundingClientRect();
      var bodyPosition = ownerDocument.body.getBoundingClientRect();
      offsetLeft = (offsetParentPosition.left - bodyPosition.left - offsetParent.scrollLeft);
      offsetTop = (offsetParentPosition.top - bodyPosition.top - offsetParent.scrollTop);
    }
    hints.style.left = (left - offsetLeft) + "px";
    hints.style.top = (top - offsetTop) + "px";

    // If we're at the edge of the screen, then we want the menu to appear on the left of the cursor.
    var winW = parentWindow.innerWidth || Math.max(ownerDocument.body.offsetWidth, ownerDocument.documentElement.offsetWidth);
    var winH = parentWindow.innerHeight || Math.max(ownerDocument.body.offsetHeight, ownerDocument.documentElement.offsetHeight);
    container.appendChild(hints);
    cm.getInputField().setAttribute("aria-autocomplete", "list")
    cm.getInputField().setAttribute("aria-owns", this.id)
    cm.getInputField().setAttribute("aria-activedescendant", this.id + "-" + this.selectedHint)

    var box = completion.options.moveOnOverlap ? hints.getBoundingClientRect() : new DOMRect();
    var scrolls = completion.options.paddingForScrollbar ? hints.scrollHeight > hints.clientHeight + 1 : false;

    // Compute in the timeout to avoid reflow on init
    var startScroll;
    setTimeout(function() { startScroll = cm.getScrollInfo(); });

    var overlapY = box.bottom - winH;
    if (overlapY > 0) {
      var height = box.bottom - box.top, curTop = pos.top - (pos.bottom - box.top);
      if (curTop - height > 0) { // Fits above cursor
        hints.style.top = (top = pos.top - height - offsetTop) + "px";
        below = false;
      } else if (height > winH) {
        hints.style.height = (winH - 5) + "px";
        hints.style.top = (top = pos.bottom - box.top - offsetTop) + "px";
        var cursor = cm.getCursor();
        if (data.from.ch != cursor.ch) {
          pos = cm.cursorCoords(cursor);
          hints.style.left = (left = pos.left - offsetLeft) + "px";
          box = hints.getBoundingClientRect();
        }
      }
    }
    var overlapX = box.right - winW;
    if (scrolls) overlapX += cm.display.nativeBarWidth;
    if (overlapX > 0) {
      if (box.right - box.left > winW) {
        hints.style.width = (winW - 5) + "px";
        overlapX -= (box.right - box.left) - winW;
      }
      hints.style.left = (left = pos.left - overlapX - offsetLeft) + "px";
    }
    if (scrolls) for (var node = hints.firstChild; node; node = node.nextSibling)
      node.style.paddingRight = cm.display.nativeBarWidth + "px"

    cm.addKeyMap(this.keyMap = buildKeyMap(completion, {
      moveFocus: function(n, avoidWrap) { widget.changeActive(widget.selectedHint + n, avoidWrap); },
      setFocus: function(n) { widget.changeActive(n); },
      menuSize: function() { return widget.screenAmount(); },
      length: completions.length,
      close: function() { completion.close(); },
      pick: function() { widget.pick(); },
      data: data
    }));

    if (completion.options.closeOnUnfocus) {
      var closingOnBlur;
      cm.on("blur", this.onBlur = function() { closingOnBlur = setTimeout(function() { completion.close(); }, 100); });
      cm.on("focus", this.onFocus = function() { clearTimeout(closingOnBlur); });
    }

    cm.on("scroll", this.onScroll = function() {
      var curScroll = cm.getScrollInfo(), editor = cm.getWrapperElement().getBoundingClientRect();
      if (!startScroll) startScroll = cm.getScrollInfo();
      var newTop = top + startScroll.top - curScroll.top;
      var point = newTop - (parentWindow.pageYOffset || (ownerDocument.documentElement || ownerDocument.body).scrollTop);
      if (!below) point += hints.offsetHeight;
      if (point <= editor.top || point >= editor.bottom) return completion.close();
      hints.style.top = newTop + "px";
      hints.style.left = (left + startScroll.left - curScroll.left) + "px";
    });

    CodeMirror.on(hints, "dblclick", function(e) {
      var t = getHintElement(hints, e.target || e.srcElement);
      if (t && t.hintId != null) {widget.changeActive(t.hintId); widget.pick();}
    });

    CodeMirror.on(hints, "click", function(e) {
      var t = getHintElement(hints, e.target || e.srcElement);
      if (t && t.hintId != null) {
        widget.changeActive(t.hintId);
        if (completion.options.completeOnSingleClick) widget.pick();
      }
    });

    CodeMirror.on(hints, "mousedown", function() {
      setTimeout(function(){cm.focus();}, 20);
    });

    // The first hint doesn't need to be scrolled to on init
    var selectedHintRange = this.getSelectedHintRange();
    if (selectedHintRange.from !== 0 || selectedHintRange.to !== 0) {
      this.scrollToActive();
    }

    CodeMirror.signal(data, "select", completions[this.selectedHint], hints.childNodes[this.selectedHint]);
    return true;
  }
```
</details>

### `moveFocus(n: any, avoidWrap: any): void`

**Parameters:**

- **`n`** `any`
- **`avoidWrap`** `any`

**Returns:** `void`

**Calls:**

- `widget.changeActive`

<details><summary>Code</summary>

```typescript
function(n, avoidWrap) { widget.changeActive(widget.selectedHint + n, avoidWrap); }
```
</details>

### `setFocus(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `widget.changeActive`

<details><summary>Code</summary>

```typescript
function(n) { widget.changeActive(n); }
```
</details>

### `menuSize(): number`

**Returns:** `number`

**Calls:**

- `widget.screenAmount`

<details><summary>Code</summary>

```typescript
function() { return widget.screenAmount(); }
```
</details>

### `close(): void`

**Returns:** `void`

**Calls:**

- `completion.close`

<details><summary>Code</summary>

```typescript
function() { completion.close(); }
```
</details>

### `pick(): void`

**Returns:** `void`

**Calls:**

- `widget.pick`

<details><summary>Code</summary>

```typescript
function() { widget.pick(); }
```
</details>

### `moveFocus(n: any, avoidWrap: any): void`

**Parameters:**

- **`n`** `any`
- **`avoidWrap`** `any`

**Returns:** `void`

**Calls:**

- `widget.changeActive`

<details><summary>Code</summary>

```typescript
function(n, avoidWrap) { widget.changeActive(widget.selectedHint + n, avoidWrap); }
```
</details>

### `setFocus(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `widget.changeActive`

<details><summary>Code</summary>

```typescript
function(n) { widget.changeActive(n); }
```
</details>

### `menuSize(): number`

**Returns:** `number`

**Calls:**

- `widget.screenAmount`

<details><summary>Code</summary>

```typescript
function() { return widget.screenAmount(); }
```
</details>

### `close(): void`

**Returns:** `void`

**Calls:**

- `completion.close`

<details><summary>Code</summary>

```typescript
function() { completion.close(); }
```
</details>

### `pick(): void`

**Returns:** `void`

**Calls:**

- `widget.pick`

<details><summary>Code</summary>

```typescript
function() { widget.pick(); }
```
</details>

### `close(): void`

**Returns:** `void`

**Calls:**

- `this.hints.parentNode.removeChild`
- `this.completion.cm.removeKeyMap`
- `this.completion.cm.getInputField`
- `input.removeAttribute`
- `cm.off`

<details><summary>Code</summary>

```typescript
function() {
      if (this.completion.widget != this) return;
      this.completion.widget = null;
      if (this.hints.parentNode) this.hints.parentNode.removeChild(this.hints);
      this.completion.cm.removeKeyMap(this.keyMap);
      var input = this.completion.cm.getInputField()
      input.removeAttribute("aria-activedescendant")
      input.removeAttribute("aria-owns")

      var cm = this.completion.cm;
      if (this.completion.options.closeOnUnfocus) {
        cm.off("blur", this.onBlur);
        cm.off("focus", this.onFocus);
      }
      cm.off("scroll", this.onScroll);
    }
```
</details>

### `disable(): void`

**Returns:** `void`

**Calls:**

- `this.completion.cm.removeKeyMap`
- `this.completion.cm.addKeyMap`

<details><summary>Code</summary>

```typescript
function() {
      this.completion.cm.removeKeyMap(this.keyMap);
      var widget = this;
      this.keyMap = {Enter: function() { widget.picked = true; }};
      this.completion.cm.addKeyMap(this.keyMap);
    }
```
</details>

### `Enter(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { widget.picked = true; }
```
</details>

### `Enter(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { widget.picked = true; }
```
</details>

### `pick(): void`

**Returns:** `void`

**Calls:**

- `this.completion.pick`

<details><summary>Code</summary>

```typescript
function() {
      this.completion.pick(this.data, this.selectedHint);
    }
```
</details>

### `changeActive(i: any, avoidWrap: any): void`

**Parameters:**

- **`i`** `any`
- **`avoidWrap`** `any`

**Returns:** `void`

**Calls:**

- `node.className.replace`
- `node.removeAttribute`
- `node.setAttribute`
- `this.completion.cm.getInputField().setAttribute`
- `this.scrollToActive`
- `CodeMirror.signal`

<details><summary>Code</summary>

```typescript
function(i, avoidWrap) {
      if (i >= this.data.list.length)
        i = avoidWrap ? this.data.list.length - 1 : 0;
      else if (i < 0)
        i = avoidWrap ? 0  : this.data.list.length - 1;
      if (this.selectedHint == i) return;
      var node = this.hints.childNodes[this.selectedHint];
      if (node) {
        node.className = node.className.replace(" " + ACTIVE_HINT_ELEMENT_CLASS, "");
        node.removeAttribute("aria-selected")
      }
      node = this.hints.childNodes[this.selectedHint = i];
      node.className += " " + ACTIVE_HINT_ELEMENT_CLASS;
      node.setAttribute("aria-selected", "true")
      this.completion.cm.getInputField().setAttribute("aria-activedescendant", node.id)
      this.scrollToActive()
      CodeMirror.signal(this.data, "select", this.data.list[this.selectedHint], node);
    }
```
</details>

### `scrollToActive(): void`

**Returns:** `void`

**Calls:**

- `this.getSelectedHintRange`

<details><summary>Code</summary>

```typescript
function() {
      var selectedHintRange = this.getSelectedHintRange();
      var node1 = this.hints.childNodes[selectedHintRange.from];
      var node2 = this.hints.childNodes[selectedHintRange.to];
      var firstNode = this.hints.firstChild;
      if (node1.offsetTop < this.hints.scrollTop)
        this.hints.scrollTop = node1.offsetTop - firstNode.offsetTop;
      else if (node2.offsetTop + node2.offsetHeight > this.hints.scrollTop + this.hints.clientHeight)
        this.hints.scrollTop = node2.offsetTop + node2.offsetHeight - this.hints.clientHeight + firstNode.offsetTop;
    }
```
</details>

### `screenAmount(): number`

**Returns:** `number`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
function() {
      return Math.floor(this.hints.clientHeight / this.hints.firstChild.offsetHeight) || 1;
    }
```
</details>

### `getSelectedHintRange(): { from: number; to: number; }`

**Returns:** `{ from: number; to: number; }`

**Calls:**

- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function() {
      var margin = this.completion.options.scrollMargin || 0;
      return {
        from: Math.max(0, this.selectedHint - margin),
        to: Math.min(this.data.list.length - 1, this.selectedHint + margin),
      };
    }
```
</details>

### `close(): void`

**Returns:** `void`

**Calls:**

- `this.hints.parentNode.removeChild`
- `this.completion.cm.removeKeyMap`
- `this.completion.cm.getInputField`
- `input.removeAttribute`
- `cm.off`

<details><summary>Code</summary>

```typescript
function() {
      if (this.completion.widget != this) return;
      this.completion.widget = null;
      if (this.hints.parentNode) this.hints.parentNode.removeChild(this.hints);
      this.completion.cm.removeKeyMap(this.keyMap);
      var input = this.completion.cm.getInputField()
      input.removeAttribute("aria-activedescendant")
      input.removeAttribute("aria-owns")

      var cm = this.completion.cm;
      if (this.completion.options.closeOnUnfocus) {
        cm.off("blur", this.onBlur);
        cm.off("focus", this.onFocus);
      }
      cm.off("scroll", this.onScroll);
    }
```
</details>

### `disable(): void`

**Returns:** `void`

**Calls:**

- `this.completion.cm.removeKeyMap`
- `this.completion.cm.addKeyMap`

<details><summary>Code</summary>

```typescript
function() {
      this.completion.cm.removeKeyMap(this.keyMap);
      var widget = this;
      this.keyMap = {Enter: function() { widget.picked = true; }};
      this.completion.cm.addKeyMap(this.keyMap);
    }
```
</details>

### `Enter(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { widget.picked = true; }
```
</details>

### `Enter(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { widget.picked = true; }
```
</details>

### `pick(): void`

**Returns:** `void`

**Calls:**

- `this.completion.pick`

<details><summary>Code</summary>

```typescript
function() {
      this.completion.pick(this.data, this.selectedHint);
    }
```
</details>

### `changeActive(i: any, avoidWrap: any): void`

**Parameters:**

- **`i`** `any`
- **`avoidWrap`** `any`

**Returns:** `void`

**Calls:**

- `node.className.replace`
- `node.removeAttribute`
- `node.setAttribute`
- `this.completion.cm.getInputField().setAttribute`
- `this.scrollToActive`
- `CodeMirror.signal`

<details><summary>Code</summary>

```typescript
function(i, avoidWrap) {
      if (i >= this.data.list.length)
        i = avoidWrap ? this.data.list.length - 1 : 0;
      else if (i < 0)
        i = avoidWrap ? 0  : this.data.list.length - 1;
      if (this.selectedHint == i) return;
      var node = this.hints.childNodes[this.selectedHint];
      if (node) {
        node.className = node.className.replace(" " + ACTIVE_HINT_ELEMENT_CLASS, "");
        node.removeAttribute("aria-selected")
      }
      node = this.hints.childNodes[this.selectedHint = i];
      node.className += " " + ACTIVE_HINT_ELEMENT_CLASS;
      node.setAttribute("aria-selected", "true")
      this.completion.cm.getInputField().setAttribute("aria-activedescendant", node.id)
      this.scrollToActive()
      CodeMirror.signal(this.data, "select", this.data.list[this.selectedHint], node);
    }
```
</details>

### `scrollToActive(): void`

**Returns:** `void`

**Calls:**

- `this.getSelectedHintRange`

<details><summary>Code</summary>

```typescript
function() {
      var selectedHintRange = this.getSelectedHintRange();
      var node1 = this.hints.childNodes[selectedHintRange.from];
      var node2 = this.hints.childNodes[selectedHintRange.to];
      var firstNode = this.hints.firstChild;
      if (node1.offsetTop < this.hints.scrollTop)
        this.hints.scrollTop = node1.offsetTop - firstNode.offsetTop;
      else if (node2.offsetTop + node2.offsetHeight > this.hints.scrollTop + this.hints.clientHeight)
        this.hints.scrollTop = node2.offsetTop + node2.offsetHeight - this.hints.clientHeight + firstNode.offsetTop;
    }
```
</details>

### `screenAmount(): number`

**Returns:** `number`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
function() {
      return Math.floor(this.hints.clientHeight / this.hints.firstChild.offsetHeight) || 1;
    }
```
</details>

### `getSelectedHintRange(): { from: number; to: number; }`

**Returns:** `{ from: number; to: number; }`

**Calls:**

- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function() {
      var margin = this.completion.options.scrollMargin || 0;
      return {
        from: Math.max(0, this.selectedHint - margin),
        to: Math.min(this.data.list.length - 1, this.selectedHint + margin),
      };
    }
```
</details>

### `applicableHelpers(cm: any, helpers: any): any`

**Parameters:**

- **`cm`** `any`
- **`helpers`** `any`

**Returns:** `any`

**Calls:**

- `cm.somethingSelected`
- `result.push`

<details><summary>Code</summary>

```typescript
function applicableHelpers(cm, helpers) {
    if (!cm.somethingSelected()) return helpers
    var result = []
    for (var i = 0; i < helpers.length; i++)
      if (helpers[i].supportsSelection) result.push(helpers[i])
    return result
  }
```
</details>

### `fetchHints(hint: any, cm: any, options: any, callback: any): void`

**Parameters:**

- **`hint`** `any`
- **`cm`** `any`
- **`options`** `any`
- **`callback`** `any`

**Returns:** `void`

**Calls:**

- `hint`
- `result.then`
- `callback`

<details><summary>Code</summary>

```typescript
function fetchHints(hint, cm, options, callback) {
    if (hint.async) {
      hint(cm, callback, options)
    } else {
      var result = hint(cm, options)
      if (result && result.then) result.then(callback)
      else callback(result)
    }
  }
```
</details>

### `resolveAutoHints(cm: any, pos: any): { (cm: any, callback: any, options: any): void; async: boolean; supportsSelection: boolean; } | ((cm: any, options: any) => any)`

**Parameters:**

- **`cm`** `any`
- **`pos`** `any`

**Returns:** `{ (cm: any, callback: any, options: any): void; async: boolean; supportsSelection: boolean; } | ((cm: any, options: any) => any)`

**Calls:**

- `cm.getHelpers`
- `applicableHelpers`
- `callback`
- `fetchHints`
- `run`
- `cm.getHelper`
- `cm.getCursor`
- `CodeMirror.hint.fromList`
- `CodeMirror.hint.anyword`

<details><summary>Code</summary>

```typescript
function resolveAutoHints(cm, pos) {
    var helpers = cm.getHelpers(pos, "hint"), words
    if (helpers.length) {
      var resolved = function(cm, callback, options) {
        var app = applicableHelpers(cm, helpers);
        function run(i) {
          if (i == app.length) return callback(null)
          fetchHints(app[i], cm, options, function(result) {
            if (result && result.list.length > 0) callback(result)
            else run(i + 1)
          })
        }
        run(0)
      }
      resolved.async = true
      resolved.supportsSelection = true
      return resolved
    } else if (words = cm.getHelper(cm.getCursor(), "hintWords")) {
      return function(cm) { return CodeMirror.hint.fromList(cm, {words: words}) }
    } else if (CodeMirror.hint.anyword) {
      return function(cm, options) { return CodeMirror.hint.anyword(cm, options) }
    } else {
      return function() {}
    }
  }
```
</details>

### `resolved(cm: any, callback: any, options: any): void`

**Parameters:**

- **`cm`** `any`
- **`callback`** `any`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `applicableHelpers`
- `callback`
- `fetchHints`
- `run`

<details><summary>Code</summary>

```typescript
function(cm, callback, options) {
        var app = applicableHelpers(cm, helpers);
        function run(i) {
          if (i == app.length) return callback(null)
          fetchHints(app[i], cm, options, function(result) {
            if (result && result.list.length > 0) callback(result)
            else run(i + 1)
          })
        }
        run(0)
      }
```
</details>

### `run(i: any): any`

**Parameters:**

- **`i`** `any`

**Returns:** `any`

**Calls:**

- `callback`
- `fetchHints`
- `run`

<details><summary>Code</summary>

```typescript
function run(i) {
          if (i == app.length) return callback(null)
          fetchHints(app[i], cm, options, function(result) {
            if (result && result.list.length > 0) callback(result)
            else run(i + 1)
          })
        }
```
</details>


---