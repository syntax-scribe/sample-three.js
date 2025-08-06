[⬅️ Back to Table of Contents](../../../../../index.md)

# 📄 `dialog.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/codemirror/addon/dialog.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `dialog` | `any` | let/var | `*not shown*` | ✗ |
| `closed` | `boolean` | let/var | `false` | ✗ |
| `me` | `any` | let/var | `this` | ✗ |
| `inp` | `any` | let/var | `dialog.getElementsByTagName("input")[0]` | ✗ |
| `button` | `any` | let/var | `*not shown*` | ✗ |
| `closed` | `boolean` | let/var | `false` | ✗ |
| `me` | `any` | let/var | `this` | ✗ |
| `blurring` | `number` | let/var | `1` | ✗ |
| `b` | `any` | let/var | `buttons[i]` | ✗ |
| `closed` | `boolean` | let/var | `false` | ✗ |
| `doneTimer` | `any` | let/var | `*not shown*` | ✗ |
| `duration` | `any` | let/var | `options && typeof options.duration !== "undefined" ? options.duration : 5000` | ✗ |


---

## Functions

### `dialogDiv(cm: any, template: any, bottom: any): any`

**Parameters:**

- **`cm`** `any`
- **`template`** `any`
- **`bottom`** `any`

**Returns:** `any`

**Calls:**

- `cm.getWrapperElement`
- `wrap.appendChild`
- `document.createElement`
- `dialog.appendChild`
- `CodeMirror.addClass`

<details><summary>Code</summary>

```typescript
function dialogDiv(cm, template, bottom) {
    var wrap = cm.getWrapperElement();
    var dialog;
    dialog = wrap.appendChild(document.createElement("div"));
    if (bottom)
      dialog.className = "CodeMirror-dialog CodeMirror-dialog-bottom";
    else
      dialog.className = "CodeMirror-dialog CodeMirror-dialog-top";

    if (typeof template == "string") {
      dialog.innerHTML = template;
    } else { // Assuming it's a detached DOM element.
      dialog.appendChild(template);
    }
    CodeMirror.addClass(wrap, 'dialog-opened');
    return dialog;
  }
```
</details>

### `closeNotification(cm: any, newVal: any): void`

**Parameters:**

- **`cm`** `any`
- **`newVal`** `any`

**Returns:** `void`

**Calls:**

- `cm.state.currentNotificationClose`

<details><summary>Code</summary>

```typescript
function closeNotification(cm, newVal) {
    if (cm.state.currentNotificationClose)
      cm.state.currentNotificationClose();
    cm.state.currentNotificationClose = newVal;
  }
```
</details>

### `close(newVal: any): void`

**Parameters:**

- **`newVal`** `any`

**Returns:** `void`

**Calls:**

- `CodeMirror.rmClass`
- `dialog.parentNode.removeChild`
- `me.focus`
- `options.onClose`

<details><summary>Code</summary>

```typescript
function close(newVal) {
      if (typeof newVal == 'string') {
        inp.value = newVal;
      } else {
        if (closed) return;
        closed = true;
        CodeMirror.rmClass(dialog.parentNode, 'dialog-opened');
        dialog.parentNode.removeChild(dialog);
        me.focus();

        if (options.onClose) options.onClose(dialog);
      }
    }
```
</details>

### `close(): void`

**Returns:** `void`

**Calls:**

- `CodeMirror.rmClass`
- `dialog.parentNode.removeChild`
- `me.focus`

<details><summary>Code</summary>

```typescript
function close() {
      if (closed) return;
      closed = true;
      CodeMirror.rmClass(dialog.parentNode, 'dialog-opened');
      dialog.parentNode.removeChild(dialog);
      me.focus();
    }
```
</details>

### `close(): void`

**Returns:** `void`

**Calls:**

- `clearTimeout`
- `CodeMirror.rmClass`
- `dialog.parentNode.removeChild`

<details><summary>Code</summary>

```typescript
function close() {
      if (closed) return;
      closed = true;
      clearTimeout(doneTimer);
      CodeMirror.rmClass(dialog.parentNode, 'dialog-opened');
      dialog.parentNode.removeChild(dialog);
    }
```
</details>


---