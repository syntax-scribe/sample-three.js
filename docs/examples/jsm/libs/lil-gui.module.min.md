[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `lil-gui.module.min.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 118 |
| 🧱 Classes | 8 |
| 📊 Variables & Constants | 40 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/libs/lil-gui.module.min.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `e` | `any` | let/var | `*not shown*` | ✗ |
| `s` | `{ isPrimitive: boolean; match: (t: an...` | let/var | `{isPrimitive:!0,match:t=>"string"==typeof t,fromHexString:e,toHexString:e}` | ✗ |
| `n` | `{ isPrimitive: boolean; match: (t: an...` | let/var | `{isPrimitive:!0,match:t=>"number"==typeof t,fromHexString:t=>parseInt(t.subst...` | ✗ |
| `l` | `{ isPrimitive: boolean; match: (arg: ...` | let/var | `{isPrimitive:!1,match:Array.isArray,fromHexString(t,i,e=1){const s=n.fromHexS...` | ✗ |
| `r` | `{ isPrimitive: boolean; match: (t: an...` | let/var | `{isPrimitive:!1,match:t=>Object(t)===t,fromHexString(t,i,e=1){const s=n.fromH...` | ✗ |
| `o` | `({ isPrimitive: boolean; match: (arg:...` | let/var | `[s,n,l,r]` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `r` | `boolean` | let/var | `void 0!==l` | ✗ |
| `i` | `number` | let/var | `(t-this._min)/(this._max-this._min)` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `e` | `any` | let/var | `*not shown*` | ✗ |
| `s` | `any` | let/var | `*not shown*` | ✗ |
| `n` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `r` | `boolean` | let/var | `!1` | ✗ |
| `s` | `number` | let/var | `t.clientX-i` | ✗ |
| `n` | `number` | let/var | `t.clientY-e` | ✗ |
| `i` | `number` | let/var | `t.clientY-s` | ✗ |
| `e` | `any` | let/var | `(s=t,n=i.left,l=i.right,r=this._min,o=this._max,(s-n)/(l-n)*(o-r)+r)` | ✗ |
| `s` | `any` | let/var | `*not shown*` | ✗ |
| `n` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `r` | `any` | let/var | `*not shown*` | ✗ |
| `o` | `any` | let/var | `*not shown*` | ✗ |
| `s` | `any` | let/var | `*not shown*` | ✗ |
| `n` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `boolean` | let/var | `!1` | ✗ |
| `t` | `number` | let/var | `i.touches[0].clientX-s` | ✗ |
| `e` | `number` | let/var | `i.touches[0].clientY-n` | ✗ |
| `d` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `number` | let/var | `this._normalizeMouseWheel(t)*this._step` | ✗ |
| `i` | `number` | let/var | `this._stepExplicit?1:10` | ✗ |
| `i` | `number` | let/var | `Math.round(t/this._step)*this._step` | ✗ |
| `t` | `any` | let/var | `this.parent.root.$children` | ✗ |
| `p` | `boolean` | let/var | `!1` | ✗ |
| `r` | `any` | let/var | `t[e]` | ✗ |
| `i` | `{ controllers: {}; folders: {}; }` | let/var | `{controllers:{},folders:{}}` | ✗ |
| `i` | `number` | let/var | `this.$children.clientHeight` | ✗ |
| `s` | `number` | let/var | `t?this.$children.scrollHeight:0` | ✗ |


---

## Functions

### `t.name(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
name(t){return this._name=t,this.$name.innerHTML=t,this}
```
</details>

### `t.onChange(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
onChange(t){return this._onChange=t,this}
```
</details>

### `t._callOnChange(): void`

**Returns:** `void`

**Calls:**

- `this.parent._callOnChange`
- `this._onChange.call`
- `this.getValue`

<details><summary>Code</summary>

```typescript
_callOnChange(){this.parent._callOnChange(this),void 0!==this._onChange&&this._onChange.call(this,this.getValue()),this._changed=!0}
```
</details>

### `t.onFinishChange(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
onFinishChange(t){return this._onFinishChange=t,this}
```
</details>

### `t._callOnFinishChange(): void`

**Returns:** `void`

**Calls:**

- `this.parent._callOnFinishChange`
- `this._onFinishChange.call`
- `this.getValue`

<details><summary>Code</summary>

```typescript
_callOnFinishChange(){this._changed&&(this.parent._callOnFinishChange(this),void 0!==this._onFinishChange&&this._onFinishChange.call(this,this.getValue())),this._changed=!1}
```
</details>

### `t.reset(): this`

**Returns:** `this`

**Calls:**

- `this.setValue`
- `this._callOnFinishChange`

<details><summary>Code</summary>

```typescript
reset(){return this.setValue(this.initialValue),this._callOnFinishChange(),this}
```
</details>

### `t.enable(t: boolean): this`

**Parameters:**

- **`t`** `boolean`

**Returns:** `this`

**Calls:**

- `this.disable`

<details><summary>Code</summary>

```typescript
enable(t=!0){return this.disable(!t)}
```
</details>

### `t.disable(t: boolean): this`

**Parameters:**

- **`t`** `boolean`

**Returns:** `this`

**Calls:**

- `this.domElement.classList.toggle`
- `this.$disable.toggleAttribute`

<details><summary>Code</summary>

```typescript
disable(t=!0){return t===this._disabled||(this._disabled=t,this.domElement.classList.toggle("disabled",t),this.$disable.toggleAttribute("disabled",t)),this}
```
</details>

### `t.show(t: boolean): this`

**Parameters:**

- **`t`** `boolean`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
show(t=!0){return this._hidden=!t,this.domElement.style.display=this._hidden?"none":"",this}
```
</details>

### `t.hide(): this`

**Returns:** `this`

**Calls:**

- `this.show`

<details><summary>Code</summary>

```typescript
hide(){return this.show(!1)}
```
</details>

### `t.options(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `this.parent.add`
- `i.name`
- `this.destroy`

<details><summary>Code</summary>

```typescript
options(t){const i=this.parent.add(this.object,this.property,t);return i.name(this._name),this.destroy(),i}
```
</details>

### `t.min(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
min(t){return this}
```
</details>

### `t.max(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
max(t){return this}
```
</details>

### `t.step(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
step(t){return this}
```
</details>

### `t.decimals(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
decimals(t){return this}
```
</details>

### `t.listen(t: boolean): this`

**Parameters:**

- **`t`** `boolean`

**Returns:** `this`

**Calls:**

- `cancelAnimationFrame`
- `this._listenCallback`

<details><summary>Code</summary>

```typescript
listen(t=!0){return this._listening=t,void 0!==this._listenCallbackID&&(cancelAnimationFrame(this._listenCallbackID),this._listenCallbackID=void 0),this._listening&&this._listenCallback(),this}
```
</details>

### `t._listenCallback(): void`

**Returns:** `void`

**Calls:**

- `requestAnimationFrame`
- `this.save`
- `this.updateDisplay`

<details><summary>Code</summary>

```typescript
_listenCallback(){this._listenCallbackID=requestAnimationFrame(this._listenCallback);const t=this.save();t!==this._listenPrevValue&&this.updateDisplay(),this._listenPrevValue=t}
```
</details>

### `t.getValue(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue(){return this.object[this.property]}
```
</details>

### `t.setValue(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

**Calls:**

- `this._callOnChange`
- `this.updateDisplay`

<details><summary>Code</summary>

```typescript
setValue(t){return this.object[this.property]=t,this._callOnChange(),this.updateDisplay(),this}
```
</details>

### `t.updateDisplay(): this`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
updateDisplay(){return this}
```
</details>

### `t.load(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

**Calls:**

- `this.setValue`
- `this._callOnFinishChange`

<details><summary>Code</summary>

```typescript
load(t){return this.setValue(t),this._callOnFinishChange(),this}
```
</details>

### `t.save(): any`

**Returns:** `any`

**Calls:**

- `this.getValue`

<details><summary>Code</summary>

```typescript
save(){return this.getValue()}
```
</details>

### `t.destroy(): void`

**Returns:** `void`

**Calls:**

- `this.listen`
- `this.parent.children.splice`
- `this.parent.children.indexOf`
- `this.parent.controllers.splice`
- `this.parent.controllers.indexOf`
- `this.parent.$children.removeChild`

<details><summary>Code</summary>

```typescript
destroy(){this.listen(!1),this.parent.children.splice(this.parent.children.indexOf(this),1),this.parent.controllers.splice(this.parent.controllers.indexOf(this),1),this.parent.$children.removeChild(this.domElement)}
```
</details>

### `i.updateDisplay(): this`

**Returns:** `this`

**Calls:**

- `this.getValue`

<details><summary>Code</summary>

```typescript
updateDisplay(){return this.$input.checked=this.getValue(),this}
```
</details>

### `e(t: any): string`

**Parameters:**

- **`t`** `any`

**Returns:** `string`

**Calls:**

- `t.match`
- `parseInt(i[1]).toString(16).padStart`
- `parseInt(i[2]).toString(16).padStart`
- `parseInt(i[3]).toString(16).padStart`

<details><summary>Code</summary>

```typescript
function e(t){let i,e;return(i=t.match(/(#|0x)?([a-f0-9]{6})/i))?e=i[2]:(i=t.match(/rgb\(\s*(\d*)\s*,\s*(\d*)\s*,\s*(\d*)\s*\)/))?e=parseInt(i[1]).toString(16).padStart(2,0)+parseInt(i[2]).toString(16).padStart(2,0)+parseInt(i[3]).toString(16).padStart(2,0):(i=t.match(/^#?([a-f0-9])([a-f0-9])([a-f0-9])$/i))&&(e=i[1]+i[1]+i[2]+i[2]+i[3]+i[3]),!!e&&"#"+e}
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"string"==typeof t
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"string"==typeof t
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"string"==typeof t
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"number"==typeof t
```
</details>

### `fromHexString(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
t=>parseInt(t.substring(1),16)
```
</details>

### `toHexString(t: any): string`

**Parameters:**

- **`t`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
t=>"#"+t.toString(16).padStart(6,0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"number"==typeof t
```
</details>

### `fromHexString(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
t=>parseInt(t.substring(1),16)
```
</details>

### `toHexString(t: any): string`

**Parameters:**

- **`t`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
t=>"#"+t.toString(16).padStart(6,0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"number"==typeof t
```
</details>

### `fromHexString(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
t=>parseInt(t.substring(1),16)
```
</details>

### `toHexString(t: any): string`

**Parameters:**

- **`t`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
t=>"#"+t.toString(16).padStart(6,0)
```
</details>

### `toHexString([t,i,e]: any, s: number): string`

**Parameters:**

- **`[t,i,e]`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
([t,i,e],s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `toHexString([t,i,e]: any, s: number): string`

**Parameters:**

- **`[t,i,e]`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
([t,i,e],s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `toHexString([t,i,e]: any, s: number): string`

**Parameters:**

- **`[t,i,e]`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
([t,i,e],s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>Object(t)===t
```
</details>

### `toHexString({r:t,g:i,b:e}: any, s: number): string`

**Parameters:**

- **`{r:t,g:i,b:e}`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
({r:t,g:i,b:e},s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>Object(t)===t
```
</details>

### `toHexString({r:t,g:i,b:e}: any, s: number): string`

**Parameters:**

- **`{r:t,g:i,b:e}`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
({r:t,g:i,b:e},s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>Object(t)===t
```
</details>

### `toHexString({r:t,g:i,b:e}: any, s: number): string`

**Parameters:**

- **`{r:t,g:i,b:e}`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
({r:t,g:i,b:e},s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"string"==typeof t
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"string"==typeof t
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"string"==typeof t
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"number"==typeof t
```
</details>

### `fromHexString(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
t=>parseInt(t.substring(1),16)
```
</details>

### `toHexString(t: any): string`

**Parameters:**

- **`t`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
t=>"#"+t.toString(16).padStart(6,0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"number"==typeof t
```
</details>

### `fromHexString(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
t=>parseInt(t.substring(1),16)
```
</details>

### `toHexString(t: any): string`

**Parameters:**

- **`t`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
t=>"#"+t.toString(16).padStart(6,0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>"number"==typeof t
```
</details>

### `fromHexString(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
t=>parseInt(t.substring(1),16)
```
</details>

### `toHexString(t: any): string`

**Parameters:**

- **`t`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
t=>"#"+t.toString(16).padStart(6,0)
```
</details>

### `toHexString([t,i,e]: any, s: number): string`

**Parameters:**

- **`[t,i,e]`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
([t,i,e],s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `toHexString([t,i,e]: any, s: number): string`

**Parameters:**

- **`[t,i,e]`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
([t,i,e],s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `toHexString([t,i,e]: any, s: number): string`

**Parameters:**

- **`[t,i,e]`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
([t,i,e],s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>Object(t)===t
```
</details>

### `toHexString({r:t,g:i,b:e}: any, s: number): string`

**Parameters:**

- **`{r:t,g:i,b:e}`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
({r:t,g:i,b:e},s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>Object(t)===t
```
</details>

### `toHexString({r:t,g:i,b:e}: any, s: number): string`

**Parameters:**

- **`{r:t,g:i,b:e}`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
({r:t,g:i,b:e},s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `match(t: any): boolean`

**Parameters:**

- **`t`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
t=>Object(t)===t
```
</details>

### `toHexString({r:t,g:i,b:e}: any, s: number): string`

**Parameters:**

- **`{r:t,g:i,b:e}`** `any`
- **`s`** `number`

**Returns:** `string`

**Calls:**

- `n.toHexString`

<details><summary>Code</summary>

```typescript
({r:t,g:i,b:e},s=1)=>n.toHexString(t*(s=255/s)<<16^i*s<<8^e*s<<0)
```
</details>

### `a.reset(): this`

**Returns:** `this`

**Calls:**

- `this._setValueFromHexString`

<details><summary>Code</summary>

```typescript
reset(){return this._setValueFromHexString(this._initialValueHexString),this}
```
</details>

### `a._setValueFromHexString(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `this._format.fromHexString`
- `this.setValue`
- `this.getValue`
- `this._callOnChange`
- `this.updateDisplay`

<details><summary>Code</summary>

```typescript
_setValueFromHexString(t){if(this._format.isPrimitive){const i=this._format.fromHexString(t);this.setValue(i)}else this._format.fromHexString(t,this.getValue(),this._rgbScale),this._callOnChange(),this.updateDisplay()}
```
</details>

### `a.save(): string`

**Returns:** `string`

**Calls:**

- `this._format.toHexString`
- `this.getValue`

<details><summary>Code</summary>

```typescript
save(){return this._format.toHexString(this.getValue(),this._rgbScale)}
```
</details>

### `a.load(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

**Calls:**

- `this._setValueFromHexString`
- `this._callOnFinishChange`

<details><summary>Code</summary>

```typescript
load(t){return this._setValueFromHexString(t),this._callOnFinishChange(),this}
```
</details>

### `a.updateDisplay(): this`

**Returns:** `this`

**Calls:**

- `this._format.toHexString`
- `this.getValue`
- `this.$input.value.substring`

<details><summary>Code</summary>

```typescript
updateDisplay(){return this.$input.value=this._format.toHexString(this.getValue(),this._rgbScale),this._textFocused||(this.$text.value=this.$input.value.substring(1)),this.$display.style.backgroundColor=this.$input.value,this}
```
</details>

### `d.decimals(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

**Calls:**

- `this.updateDisplay`

<details><summary>Code</summary>

```typescript
decimals(t){return this._decimals=t,this.updateDisplay(),this}
```
</details>

### `d.min(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

**Calls:**

- `this._onUpdateMinMax`

<details><summary>Code</summary>

```typescript
min(t){return this._min=t,this._onUpdateMinMax(),this}
```
</details>

### `d.max(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

**Calls:**

- `this._onUpdateMinMax`

<details><summary>Code</summary>

```typescript
max(t){return this._max=t,this._onUpdateMinMax(),this}
```
</details>

### `d.step(t: any, i: boolean): this`

**Parameters:**

- **`t`** `any`
- **`i`** `boolean`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
step(t,i=!0){return this._step=t,this._stepExplicit=i,this}
```
</details>

### `d.updateDisplay(): this`

**Returns:** `this`

**Calls:**

- `this.getValue`
- `Math.max`
- `Math.min`
- `t.toFixed`

<details><summary>Code</summary>

```typescript
updateDisplay(){const t=this.getValue();if(this._hasSlider){let i=(t-this._min)/(this._max-this._min);i=Math.max(0,Math.min(i,1)),this.$fill.style.width=100*i+"%"}return this._inputFocused||(this.$input.value=void 0===this._decimals?t:t.toFixed(this._decimals)),this}
```
</details>

### `d._initInput(): void`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `this.$input.setAttribute`
- `this.$widget.appendChild`
- `parseFloat`
- `isNaN`
- `this._snapClampSetValue`
- `this.getValue`
- `Math.abs`
- `t.preventDefault`
- `this.$input.blur`
- `this._setDraggingStyle`
- `a`
- `this._arrowKeyMultiplier`
- `this._callOnFinishChange`
- `window.removeEventListener`
- `this.$input.addEventListener`
- `this._snap`
- `this.setValue`
- `this._clamp`
- `i.preventDefault`
- `t`
- `this._normalizeMouseWheel`
- `window.addEventListener`
- `this.updateDisplay`

<details><summary>Code</summary>

```typescript
_initInput(){this.$input=document.createElement("input"),this.$input.setAttribute("type","number"),this.$input.setAttribute("step","any"),this.$input.setAttribute("aria-labelledby",this.$name.id),this.$widget.appendChild(this.$input),this.$disable=this.$input;const t=t=>{const i=parseFloat(this.$input.value);isNaN(i)||(this._snapClampSetValue(i+t),this.$input.value=this.getValue())};let i,e,s,n,l,r=!1;const o=t=>{if(r){const s=t.clientX-i,n=t.clientY-e;Math.abs(n)>5?(t.preventDefault(),this.$input.blur(),r=!1,this._setDraggingStyle(!0,"vertical")):Math.abs(s)>5&&a()}if(!r){const i=t.clientY-s;l-=i*this._step*this._arrowKeyMultiplier(t),n+l>this._max?l=this._max-n:n+l<this._min&&(l=this._min-n),this._snapClampSetValue(n+l)}s=t.clientY},a=()=>{this._setDraggingStyle(!1,"vertical"),this._callOnFinishChange(),window.removeEventListener("mousemove",o),window.removeEventListener("mouseup",a)};this.$input.addEventListener("input",()=>{let t=parseFloat(this.$input.value);isNaN(t)||(this._stepExplicit&&(t=this._snap(t)),this.setValue(this._clamp(t)))}),this.$input.addEventListener("keydown",i=>{"Enter"===i.code&&this.$input.blur(),"ArrowUp"===i.code&&(i.preventDefault(),t(this._step*this._arrowKeyMultiplier(i))),"ArrowDown"===i.code&&(i.preventDefault(),t(this._step*this._arrowKeyMultiplier(i)*-1))}),this.$input.addEventListener("wheel",i=>{this._inputFocused&&(i.preventDefault(),t(this._step*this._normalizeMouseWheel(i)))},{passive:!1}),this.$input.addEventListener("mousedown",t=>{i=t.clientX,e=s=t.clientY,r=!0,n=this.getValue(),l=0,window.addEventListener("mousemove",o),window.addEventListener("mouseup",a)}),this.$input.addEventListener("focus",()=>{this._inputFocused=!0}),this.$input.addEventListener("blur",()=>{this._inputFocused=!1,this.updateDisplay(),this._callOnFinishChange()})}
```
</details>

### `d._initSlider(): void`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `this.$slider.classList.add`
- `this.$fill.classList.add`
- `this.$slider.appendChild`
- `this.$widget.insertBefore`
- `this.domElement.classList.add`
- `this.$slider.getBoundingClientRect`
- `this._snapClampSetValue`
- `t`
- `this._callOnFinishChange`
- `this._setDraggingStyle`
- `window.removeEventListener`
- `i.preventDefault`
- `Math.abs`
- `r`
- `this._callOnFinishChange.bind`
- `this.$slider.addEventListener`
- `window.addEventListener`
- `t.preventDefault`
- `this._normalizeMouseWheel`
- `this.getValue`
- `clearTimeout`
- `setTimeout`

<details><summary>Code</summary>

```typescript
_initSlider(){this._hasSlider=!0,this.$slider=document.createElement("div"),this.$slider.classList.add("slider"),this.$fill=document.createElement("div"),this.$fill.classList.add("fill"),this.$slider.appendChild(this.$fill),this.$widget.insertBefore(this.$slider,this.$input),this.domElement.classList.add("hasSlider");const t=t=>{const i=this.$slider.getBoundingClientRect();let e=(s=t,n=i.left,l=i.right,r=this._min,o=this._max,(s-n)/(l-n)*(o-r)+r);var s,n,l,r,o;this._snapClampSetValue(e)},i=i=>{t(i.clientX)},e=()=>{this._callOnFinishChange(),this._setDraggingStyle(!1),window.removeEventListener("mousemove",i),window.removeEventListener("mouseup",e)};let s,n,l=!1;const r=i=>{i.preventDefault(),this._setDraggingStyle(!0),t(i.touches[0].clientX),l=!1},o=i=>{if(l){const t=i.touches[0].clientX-s,e=i.touches[0].clientY-n;Math.abs(t)>Math.abs(e)?r(i):(window.removeEventListener("touchmove",o),window.removeEventListener("touchend",a))}else i.preventDefault(),t(i.touches[0].clientX)},a=()=>{this._callOnFinishChange(),this._setDraggingStyle(!1),window.removeEventListener("touchmove",o),window.removeEventListener("touchend",a)},h=this._callOnFinishChange.bind(this);let d;this.$slider.addEventListener("mousedown",s=>{this._setDraggingStyle(!0),t(s.clientX),window.addEventListener("mousemove",i),window.addEventListener("mouseup",e)}),this.$slider.addEventListener("touchstart",t=>{t.touches.length>1||(this._hasScrollBar?(s=t.touches[0].clientX,n=t.touches[0].clientY,l=!0):r(t),window.addEventListener("touchmove",o,{passive:!1}),window.addEventListener("touchend",a))},{passive:!1}),this.$slider.addEventListener("wheel",t=>{if(Math.abs(t.deltaX)<Math.abs(t.deltaY)&&this._hasScrollBar)return;t.preventDefault();const i=this._normalizeMouseWheel(t)*this._step;this._snapClampSetValue(this.getValue()+i),this.$input.value=this.getValue(),clearTimeout(d),d=setTimeout(h,400)},{passive:!1})}
```
</details>

### `d._setDraggingStyle(t: any, i: string): void`

**Parameters:**

- **`t`** `any`
- **`i`** `string`

**Returns:** `void`

**Calls:**

- `this.$slider.classList.toggle`
- `document.body.classList.toggle`

<details><summary>Code</summary>

```typescript
_setDraggingStyle(t,i="horizontal"){this.$slider&&this.$slider.classList.toggle("active",t),document.body.classList.toggle("lil-gui-dragging",t),document.body.classList.toggle("lil-gui-"+i,t)}
```
</details>

### `d._getImplicitStep(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
_getImplicitStep(){return this._hasMin&&this._hasMax?(this._max-this._min)/1e3:.1}
```
</details>

### `d._onUpdateMinMax(): void`

**Returns:** `void`

**Calls:**

- `this.step`
- `this._getImplicitStep`
- `this._initSlider`
- `this.updateDisplay`

<details><summary>Code</summary>

```typescript
_onUpdateMinMax(){!this._hasSlider&&this._hasMin&&this._hasMax&&(this._stepExplicit||this.step(this._getImplicitStep(),!1),this._initSlider(),this.updateDisplay())}
```
</details>

### `d._normalizeMouseWheel(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
_normalizeMouseWheel(t){let{deltaX:i,deltaY:e}=t;Math.floor(t.deltaY)!==t.deltaY&&t.wheelDelta&&(i=0,e=-t.wheelDelta/120,e*=this._stepExplicit?1:10);return i+-e}
```
</details>

### `d._arrowKeyMultiplier(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
_arrowKeyMultiplier(t){let i=this._stepExplicit?1:10;return t.shiftKey?i*=10:t.altKey&&(i/=10),i}
```
</details>

### `d._snap(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

**Calls:**

- `Math.round`
- `parseFloat`
- `i.toPrecision`

<details><summary>Code</summary>

```typescript
_snap(t){const i=Math.round(t/this._step)*this._step;return parseFloat(i.toPrecision(15))}
```
</details>

### `d._clamp(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
_clamp(t){return t<this._min&&(t=this._min),t>this._max&&(t=this._max),t}
```
</details>

### `d._snapClampSetValue(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `this.setValue`
- `this._clamp`
- `this._snap`

<details><summary>Code</summary>

```typescript
_snapClampSetValue(t){this.setValue(this._clamp(this._snap(t)))}
```
</details>

### `t(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `parseFloat`
- `isNaN`
- `this._snapClampSetValue`
- `this.getValue`

<details><summary>Code</summary>

```typescript
t=>{const i=parseFloat(this.$input.value);isNaN(i)||(this._snapClampSetValue(i+t),this.$input.value=this.getValue())}
```
</details>

### `o(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `t.preventDefault`
- `this.$input.blur`
- `this._setDraggingStyle`
- `a`
- `this._arrowKeyMultiplier`
- `this._snapClampSetValue`

<details><summary>Code</summary>

```typescript
t=>{if(r){const s=t.clientX-i,n=t.clientY-e;Math.abs(n)>5?(t.preventDefault(),this.$input.blur(),r=!1,this._setDraggingStyle(!0,"vertical")):Math.abs(s)>5&&a()}if(!r){const i=t.clientY-s;l-=i*this._step*this._arrowKeyMultiplier(t),n+l>this._max?l=this._max-n:n+l<this._min&&(l=this._min-n),this._snapClampSetValue(n+l)}s=t.clientY}
```
</details>

### `a(): void`

**Returns:** `void`

**Calls:**

- `this._setDraggingStyle`
- `this._callOnFinishChange`
- `window.removeEventListener`

<details><summary>Code</summary>

```typescript
()=>{this._setDraggingStyle(!1,"vertical"),this._callOnFinishChange(),window.removeEventListener("mousemove",o),window.removeEventListener("mouseup",a)}
```
</details>

### `t(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `this.$slider.getBoundingClientRect`
- `this._snapClampSetValue`

<details><summary>Code</summary>

```typescript
t=>{const i=this.$slider.getBoundingClientRect();let e=(s=t,n=i.left,l=i.right,r=this._min,o=this._max,(s-n)/(l-n)*(o-r)+r);var s,n,l,r,o;this._snapClampSetValue(e)}
```
</details>

### `i(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `t`

<details><summary>Code</summary>

```typescript
i=>{t(i.clientX)}
```
</details>

### `e(): void`

**Returns:** `void`

**Calls:**

- `this._callOnFinishChange`
- `this._setDraggingStyle`
- `window.removeEventListener`

<details><summary>Code</summary>

```typescript
()=>{this._callOnFinishChange(),this._setDraggingStyle(!1),window.removeEventListener("mousemove",i),window.removeEventListener("mouseup",e)}
```
</details>

### `r(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `i.preventDefault`
- `this._setDraggingStyle`
- `t`

<details><summary>Code</summary>

```typescript
i=>{i.preventDefault(),this._setDraggingStyle(!0),t(i.touches[0].clientX),l=!1}
```
</details>

### `o(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `r`
- `window.removeEventListener`
- `i.preventDefault`
- `t`

<details><summary>Code</summary>

```typescript
i=>{if(l){const t=i.touches[0].clientX-s,e=i.touches[0].clientY-n;Math.abs(t)>Math.abs(e)?r(i):(window.removeEventListener("touchmove",o),window.removeEventListener("touchend",a))}else i.preventDefault(),t(i.touches[0].clientX)}
```
</details>

### `a(): void`

**Returns:** `void`

**Calls:**

- `this._callOnFinishChange`
- `this._setDraggingStyle`
- `window.removeEventListener`

<details><summary>Code</summary>

```typescript
()=>{this._callOnFinishChange(),this._setDraggingStyle(!1),window.removeEventListener("touchmove",o),window.removeEventListener("touchend",a)}
```
</details>

### `c.updateDisplay(): this`

**Returns:** `this`

**Calls:**

- `this.getValue`
- `this._values.indexOf`

<details><summary>Code</summary>

```typescript
updateDisplay(){const t=this.getValue(),i=this._values.indexOf(t);return this.$select.selectedIndex=i,this.$display.innerHTML=-1===i?t:this._names[i],this}
```
</details>

### `u.updateDisplay(): this`

**Returns:** `this`

**Calls:**

- `this.getValue`

<details><summary>Code</summary>

```typescript
updateDisplay(){return this.$input.value=this.getValue(),this}
```
</details>

### `g.add(t: any, e: any, s: any, n: any, l: any): i | d | c | u | h`

**Parameters:**

- **`t`** `any`
- **`e`** `any`
- **`s`** `any`
- **`n`** `any`
- **`l`** `any`

**Returns:** `i | d | c | u | h`

**Calls:**

- `Object`
- `console.error`

<details><summary>Code</summary>

```typescript
add(t,e,s,n,l){if(Object(s)===s)return new c(this,t,e,s);const r=t[e];switch(typeof r){case"number":return new d(this,t,e,s,n,l);case"boolean":return new i(this,t,e);case"string":return new u(this,t,e);case"function":return new h(this,t,e)}console.error("gui.add failed\n\tproperty:",e,"\n\tobject:",t,"\n\tvalue:",r)}
```
</details>

### `g.addColor(t: any, i: any, e: number): a`

**Parameters:**

- **`t`** `any`
- **`i`** `any`
- **`e`** `number`

**Returns:** `a`

<details><summary>Code</summary>

```typescript
addColor(t,i,e=1){return new a(this,t,i,e)}
```
</details>

### `g.addFolder(t: any): g`

**Parameters:**

- **`t`** `any`

**Returns:** `g`

<details><summary>Code</summary>

```typescript
addFolder(t){return new g({parent:this,title:t})}
```
</details>

### `g.load(t: any, i: boolean): this`

**Parameters:**

- **`t`** `any`
- **`i`** `boolean`

**Returns:** `this`

**Calls:**

- `this.controllers.forEach`
- `i.load`
- `this.folders.forEach`

<details><summary>Code</summary>

```typescript
load(t,i=!0){return t.controllers&&this.controllers.forEach(i=>{i instanceof h||i._name in t.controllers&&i.load(t.controllers[i._name])}),i&&t.folders&&this.folders.forEach(i=>{i._title in t.folders&&i.load(t.folders[i._title])}),this}
```
</details>

### `g.save(t: boolean): { controllers: {}; folders: {}; }`

**Parameters:**

- **`t`** `boolean`

**Returns:** `{ controllers: {}; folders: {}; }`

**Calls:**

- `this.controllers.forEach`
- `t.save`
- `this.folders.forEach`

<details><summary>Code</summary>

```typescript
save(t=!0){const i={controllers:{},folders:{}};return this.controllers.forEach(t=>{if(!(t instanceof h)){if(t._name in i.controllers)throw new Error(`Cannot save GUI with duplicate property "${t._name}"`);i.controllers[t._name]=t.save()}}),t&&this.folders.forEach(t=>{if(t._title in i.folders)throw new Error(`Cannot save GUI with duplicate folder "${t._title}"`);i.folders[t._title]=t.save()}),i}
```
</details>

### `g.open(t: boolean): this`

**Parameters:**

- **`t`** `boolean`

**Returns:** `this`

**Calls:**

- `this.$title.setAttribute`
- `this.domElement.classList.toggle`

<details><summary>Code</summary>

```typescript
open(t=!0){return this._closed=!t,this.$title.setAttribute("aria-expanded",!this._closed),this.domElement.classList.toggle("closed",this._closed),this}
```
</details>

### `g.close(): this`

**Returns:** `this`

**Calls:**

- `this.open`

<details><summary>Code</summary>

```typescript
close(){return this.open(!1)}
```
</details>

### `g.show(t: boolean): this`

**Parameters:**

- **`t`** `boolean`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
show(t=!0){return this._hidden=!t,this.domElement.style.display=this._hidden?"none":"",this}
```
</details>

### `g.hide(): this`

**Returns:** `this`

**Calls:**

- `this.show`

<details><summary>Code</summary>

```typescript
hide(){return this.show(!1)}
```
</details>

### `g.openAnimated(t: boolean): this`

**Parameters:**

- **`t`** `boolean`

**Returns:** `this`

**Calls:**

- `this.$title.setAttribute`
- `requestAnimationFrame`
- `this.domElement.classList.add`
- `this.domElement.classList.remove`
- `this.$children.removeEventListener`
- `this.$children.addEventListener`
- `this.domElement.classList.toggle`

<details><summary>Code</summary>

```typescript
openAnimated(t=!0){return this._closed=!t,this.$title.setAttribute("aria-expanded",!this._closed),requestAnimationFrame(()=>{const i=this.$children.clientHeight;this.$children.style.height=i+"px",this.domElement.classList.add("transition");const e=t=>{t.target===this.$children&&(this.$children.style.height="",this.domElement.classList.remove("transition"),this.$children.removeEventListener("transitionend",e))};this.$children.addEventListener("transitionend",e);const s=t?this.$children.scrollHeight:0;this.domElement.classList.toggle("closed",!t),requestAnimationFrame(()=>{this.$children.style.height=s+"px"})}),this}
```
</details>

### `g.title(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
title(t){return this._title=t,this.$title.innerHTML=t,this}
```
</details>

### `g.reset(t: boolean): this`

**Parameters:**

- **`t`** `boolean`

**Returns:** `this`

**Calls:**

- `(t?this.controllersRecursive():this.controllers).forEach`
- `this.controllersRecursive`
- `t.reset`

<details><summary>Code</summary>

```typescript
reset(t=!0){return(t?this.controllersRecursive():this.controllers).forEach(t=>t.reset()),this}
```
</details>

### `g.onChange(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
onChange(t){return this._onChange=t,this}
```
</details>

### `g._callOnChange(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `this.parent._callOnChange`
- `this._onChange.call`
- `t.getValue`

<details><summary>Code</summary>

```typescript
_callOnChange(t){this.parent&&this.parent._callOnChange(t),void 0!==this._onChange&&this._onChange.call(this,{object:t.object,property:t.property,value:t.getValue(),controller:t})}
```
</details>

### `g.onFinishChange(t: any): this`

**Parameters:**

- **`t`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
onFinishChange(t){return this._onFinishChange=t,this}
```
</details>

### `g._callOnFinishChange(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `this.parent._callOnFinishChange`
- `this._onFinishChange.call`
- `t.getValue`

<details><summary>Code</summary>

```typescript
_callOnFinishChange(t){this.parent&&this.parent._callOnFinishChange(t),void 0!==this._onFinishChange&&this._onFinishChange.call(this,{object:t.object,property:t.property,value:t.getValue(),controller:t})}
```
</details>

### `g.destroy(): void`

**Returns:** `void`

**Calls:**

- `this.parent.children.splice`
- `this.parent.children.indexOf`
- `this.parent.folders.splice`
- `this.parent.folders.indexOf`
- `this.domElement.parentElement.removeChild`
- `Array.from(this.children).forEach`
- `t.destroy`

<details><summary>Code</summary>

```typescript
destroy(){this.parent&&(this.parent.children.splice(this.parent.children.indexOf(this),1),this.parent.folders.splice(this.parent.folders.indexOf(this),1)),this.domElement.parentElement&&this.domElement.parentElement.removeChild(this.domElement),Array.from(this.children).forEach(t=>t.destroy())}
```
</details>

### `g.controllersRecursive(): any[]`

**Returns:** `any[]`

**Calls:**

- `Array.from`
- `this.folders.forEach`
- `t.concat`
- `i.controllersRecursive`

<details><summary>Code</summary>

```typescript
controllersRecursive(){let t=Array.from(this.controllers);return this.folders.forEach(i=>{t=t.concat(i.controllersRecursive())}),t}
```
</details>

### `g.foldersRecursive(): any[]`

**Returns:** `any[]`

**Calls:**

- `Array.from`
- `this.folders.forEach`
- `t.concat`
- `i.foldersRecursive`

<details><summary>Code</summary>

```typescript
foldersRecursive(){let t=Array.from(this.folders);return this.folders.forEach(i=>{t=t.concat(i.foldersRecursive())}),t}
```
</details>

### `e(t: any): void`

**Parameters:**

- **`t`** `any`

**Returns:** `void`

**Calls:**

- `this.domElement.classList.remove`
- `this.$children.removeEventListener`

<details><summary>Code</summary>

```typescript
t=>{t.target===this.$children&&(this.$children.style.height="",this.domElement.classList.remove("transition"),this.$children.removeEventListener("transitionend",e))}
```
</details>


---

## Classes

### `t`

<details><summary>Class Code</summary>

```ts
class t{constructor(i,e,s,n,l="div"){this.parent=i,this.object=e,this.property=s,this._disabled=!1,this._hidden=!1,this.initialValue=this.getValue(),this.domElement=document.createElement("div"),this.domElement.classList.add("controller"),this.domElement.classList.add(n),this.$name=document.createElement("div"),this.$name.classList.add("name"),t.nextNameID=t.nextNameID||0,this.$name.id="lil-gui-name-"+ ++t.nextNameID,this.$widget=document.createElement(l),this.$widget.classList.add("widget"),this.$disable=this.$widget,this.domElement.appendChild(this.$name),this.domElement.appendChild(this.$widget),this.parent.children.push(this),this.parent.controllers.push(this),this.parent.$children.appendChild(this.domElement),this._listenCallback=this._listenCallback.bind(this),this.name(s)}name(t){return this._name=t,this.$name.innerHTML=t,this}onChange(t){return this._onChange=t,this}_callOnChange(){this.parent._callOnChange(this),void 0!==this._onChange&&this._onChange.call(this,this.getValue()),this._changed=!0}onFinishChange(t){return this._onFinishChange=t,this}_callOnFinishChange(){this._changed&&(this.parent._callOnFinishChange(this),void 0!==this._onFinishChange&&this._onFinishChange.call(this,this.getValue())),this._changed=!1}reset(){return this.setValue(this.initialValue),this._callOnFinishChange(),this}enable(t=!0){return this.disable(!t)}disable(t=!0){return t===this._disabled||(this._disabled=t,this.domElement.classList.toggle("disabled",t),this.$disable.toggleAttribute("disabled",t)),this}show(t=!0){return this._hidden=!t,this.domElement.style.display=this._hidden?"none":"",this}hide(){return this.show(!1)}options(t){const i=this.parent.add(this.object,this.property,t);return i.name(this._name),this.destroy(),i}min(t){return this}max(t){return this}step(t){return this}decimals(t){return this}listen(t=!0){return this._listening=t,void 0!==this._listenCallbackID&&(cancelAnimationFrame(this._listenCallbackID),this._listenCallbackID=void 0),this._listening&&this._listenCallback(),this}_listenCallback(){this._listenCallbackID=requestAnimationFrame(this._listenCallback);const t=this.save();t!==this._listenPrevValue&&this.updateDisplay(),this._listenPrevValue=t}getValue(){return this.object[this.property]}setValue(t){return this.object[this.property]=t,this._callOnChange(),this.updateDisplay(),this}updateDisplay(){return this}load(t){return this.setValue(t),this._callOnFinishChange(),this}save(){return this.getValue()}destroy(){this.listen(!1),this.parent.children.splice(this.parent.children.indexOf(this),1),this.parent.controllers.splice(this.parent.controllers.indexOf(this),1),this.parent.$children.removeChild(this.domElement)}}
```
</details>

#### Methods

##### `name(t: any): this`

<details><summary>Code</summary>

```ts
name(t){return this._name=t,this.$name.innerHTML=t,this}
```
</details>

##### `onChange(t: any): this`

<details><summary>Code</summary>

```ts
onChange(t){return this._onChange=t,this}
```
</details>

##### `_callOnChange(): void`

<details><summary>Code</summary>

```ts
_callOnChange(){this.parent._callOnChange(this),void 0!==this._onChange&&this._onChange.call(this,this.getValue()),this._changed=!0}
```
</details>

##### `onFinishChange(t: any): this`

<details><summary>Code</summary>

```ts
onFinishChange(t){return this._onFinishChange=t,this}
```
</details>

##### `_callOnFinishChange(): void`

<details><summary>Code</summary>

```ts
_callOnFinishChange(){this._changed&&(this.parent._callOnFinishChange(this),void 0!==this._onFinishChange&&this._onFinishChange.call(this,this.getValue())),this._changed=!1}
```
</details>

##### `reset(): this`

<details><summary>Code</summary>

```ts
reset(){return this.setValue(this.initialValue),this._callOnFinishChange(),this}
```
</details>

##### `enable(t: boolean): this`

<details><summary>Code</summary>

```ts
enable(t=!0){return this.disable(!t)}
```
</details>

##### `disable(t: boolean): this`

<details><summary>Code</summary>

```ts
disable(t=!0){return t===this._disabled||(this._disabled=t,this.domElement.classList.toggle("disabled",t),this.$disable.toggleAttribute("disabled",t)),this}
```
</details>

##### `show(t: boolean): this`

<details><summary>Code</summary>

```ts
show(t=!0){return this._hidden=!t,this.domElement.style.display=this._hidden?"none":"",this}
```
</details>

##### `hide(): this`

<details><summary>Code</summary>

```ts
hide(){return this.show(!1)}
```
</details>

##### `options(t: any): any`

<details><summary>Code</summary>

```ts
options(t){const i=this.parent.add(this.object,this.property,t);return i.name(this._name),this.destroy(),i}
```
</details>

##### `min(t: any): this`

<details><summary>Code</summary>

```ts
min(t){return this}
```
</details>

##### `max(t: any): this`

<details><summary>Code</summary>

```ts
max(t){return this}
```
</details>

##### `step(t: any): this`

<details><summary>Code</summary>

```ts
step(t){return this}
```
</details>

##### `decimals(t: any): this`

<details><summary>Code</summary>

```ts
decimals(t){return this}
```
</details>

##### `listen(t: boolean): this`

<details><summary>Code</summary>

```ts
listen(t=!0){return this._listening=t,void 0!==this._listenCallbackID&&(cancelAnimationFrame(this._listenCallbackID),this._listenCallbackID=void 0),this._listening&&this._listenCallback(),this}
```
</details>

##### `_listenCallback(): void`

<details><summary>Code</summary>

```ts
_listenCallback(){this._listenCallbackID=requestAnimationFrame(this._listenCallback);const t=this.save();t!==this._listenPrevValue&&this.updateDisplay(),this._listenPrevValue=t}
```
</details>

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue(){return this.object[this.property]}
```
</details>

##### `setValue(t: any): this`

<details><summary>Code</summary>

```ts
setValue(t){return this.object[this.property]=t,this._callOnChange(),this.updateDisplay(),this}
```
</details>

##### `updateDisplay(): this`

<details><summary>Code</summary>

```ts
updateDisplay(){return this}
```
</details>

##### `load(t: any): this`

<details><summary>Code</summary>

```ts
load(t){return this.setValue(t),this._callOnFinishChange(),this}
```
</details>

##### `save(): any`

<details><summary>Code</summary>

```ts
save(){return this.getValue()}
```
</details>

##### `destroy(): void`

<details><summary>Code</summary>

```ts
destroy(){this.listen(!1),this.parent.children.splice(this.parent.children.indexOf(this),1),this.parent.controllers.splice(this.parent.controllers.indexOf(this),1),this.parent.$children.removeChild(this.domElement)}
```
</details>

### `i`

<details><summary>Class Code</summary>

```ts
class i extends t{constructor(t,i,e){super(t,i,e,"boolean","label"),this.$input=document.createElement("input"),this.$input.setAttribute("type","checkbox"),this.$input.setAttribute("aria-labelledby",this.$name.id),this.$widget.appendChild(this.$input),this.$input.addEventListener("change",()=>{this.setValue(this.$input.checked),this._callOnFinishChange()}),this.$disable=this.$input,this.updateDisplay()}updateDisplay(){return this.$input.checked=this.getValue(),this}}
```
</details>

#### Methods

##### `updateDisplay(): this`

<details><summary>Code</summary>

```ts
updateDisplay(){return this.$input.checked=this.getValue(),this}
```
</details>

### `a`

<details><summary>Class Code</summary>

```ts
class a extends t{constructor(t,i,s,n){var l;super(t,i,s,"color"),this.$input=document.createElement("input"),this.$input.setAttribute("type","color"),this.$input.setAttribute("tabindex",-1),this.$input.setAttribute("aria-labelledby",this.$name.id),this.$text=document.createElement("input"),this.$text.setAttribute("type","text"),this.$text.setAttribute("spellcheck","false"),this.$text.setAttribute("aria-labelledby",this.$name.id),this.$display=document.createElement("div"),this.$display.classList.add("display"),this.$display.appendChild(this.$input),this.$widget.appendChild(this.$display),this.$widget.appendChild(this.$text),this._format=(l=this.initialValue,o.find(t=>t.match(l))),this._rgbScale=n,this._initialValueHexString=this.save(),this._textFocused=!1,this.$input.addEventListener("input",()=>{this._setValueFromHexString(this.$input.value)}),this.$input.addEventListener("blur",()=>{this._callOnFinishChange()}),this.$text.addEventListener("input",()=>{const t=e(this.$text.value);t&&this._setValueFromHexString(t)}),this.$text.addEventListener("focus",()=>{this._textFocused=!0,this.$text.select()}),this.$text.addEventListener("blur",()=>{this._textFocused=!1,this.updateDisplay(),this._callOnFinishChange()}),this.$disable=this.$text,this.updateDisplay()}reset(){return this._setValueFromHexString(this._initialValueHexString),this}_setValueFromHexString(t){if(this._format.isPrimitive){const i=this._format.fromHexString(t);this.setValue(i)}else this._format.fromHexString(t,this.getValue(),this._rgbScale),this._callOnChange(),this.updateDisplay()}save(){return this._format.toHexString(this.getValue(),this._rgbScale)}load(t){return this._setValueFromHexString(t),this._callOnFinishChange(),this}updateDisplay(){return this.$input.value=this._format.toHexString(this.getValue(),this._rgbScale),this._textFocused||(this.$text.value=this.$input.value.substring(1)),this.$display.style.backgroundColor=this.$input.value,this}}
```
</details>

#### Methods

##### `reset(): this`

<details><summary>Code</summary>

```ts
reset(){return this._setValueFromHexString(this._initialValueHexString),this}
```
</details>

##### `_setValueFromHexString(t: any): void`

<details><summary>Code</summary>

```ts
_setValueFromHexString(t){if(this._format.isPrimitive){const i=this._format.fromHexString(t);this.setValue(i)}else this._format.fromHexString(t,this.getValue(),this._rgbScale),this._callOnChange(),this.updateDisplay()}
```
</details>

##### `save(): string`

<details><summary>Code</summary>

```ts
save(){return this._format.toHexString(this.getValue(),this._rgbScale)}
```
</details>

##### `load(t: any): this`

<details><summary>Code</summary>

```ts
load(t){return this._setValueFromHexString(t),this._callOnFinishChange(),this}
```
</details>

##### `updateDisplay(): this`

<details><summary>Code</summary>

```ts
updateDisplay(){return this.$input.value=this._format.toHexString(this.getValue(),this._rgbScale),this._textFocused||(this.$text.value=this.$input.value.substring(1)),this.$display.style.backgroundColor=this.$input.value,this}
```
</details>

### `h`

<details><summary>Class Code</summary>

```ts
class h extends t{constructor(t,i,e){super(t,i,e,"function"),this.$button=document.createElement("button"),this.$button.appendChild(this.$name),this.$widget.appendChild(this.$button),this.$button.addEventListener("click",t=>{t.preventDefault(),this.getValue().call(this.object)}),this.$button.addEventListener("touchstart",()=>{},{passive:!0}),this.$disable=this.$button}}
```
</details>

### `d`

<details><summary>Class Code</summary>

```ts
class d extends t{constructor(t,i,e,s,n,l){super(t,i,e,"number"),this._initInput(),this.min(s),this.max(n);const r=void 0!==l;this.step(r?l:this._getImplicitStep(),r),this.updateDisplay()}decimals(t){return this._decimals=t,this.updateDisplay(),this}min(t){return this._min=t,this._onUpdateMinMax(),this}max(t){return this._max=t,this._onUpdateMinMax(),this}step(t,i=!0){return this._step=t,this._stepExplicit=i,this}updateDisplay(){const t=this.getValue();if(this._hasSlider){let i=(t-this._min)/(this._max-this._min);i=Math.max(0,Math.min(i,1)),this.$fill.style.width=100*i+"%"}return this._inputFocused||(this.$input.value=void 0===this._decimals?t:t.toFixed(this._decimals)),this}_initInput(){this.$input=document.createElement("input"),this.$input.setAttribute("type","number"),this.$input.setAttribute("step","any"),this.$input.setAttribute("aria-labelledby",this.$name.id),this.$widget.appendChild(this.$input),this.$disable=this.$input;const t=t=>{const i=parseFloat(this.$input.value);isNaN(i)||(this._snapClampSetValue(i+t),this.$input.value=this.getValue())};let i,e,s,n,l,r=!1;const o=t=>{if(r){const s=t.clientX-i,n=t.clientY-e;Math.abs(n)>5?(t.preventDefault(),this.$input.blur(),r=!1,this._setDraggingStyle(!0,"vertical")):Math.abs(s)>5&&a()}if(!r){const i=t.clientY-s;l-=i*this._step*this._arrowKeyMultiplier(t),n+l>this._max?l=this._max-n:n+l<this._min&&(l=this._min-n),this._snapClampSetValue(n+l)}s=t.clientY},a=()=>{this._setDraggingStyle(!1,"vertical"),this._callOnFinishChange(),window.removeEventListener("mousemove",o),window.removeEventListener("mouseup",a)};this.$input.addEventListener("input",()=>{let t=parseFloat(this.$input.value);isNaN(t)||(this._stepExplicit&&(t=this._snap(t)),this.setValue(this._clamp(t)))}),this.$input.addEventListener("keydown",i=>{"Enter"===i.code&&this.$input.blur(),"ArrowUp"===i.code&&(i.preventDefault(),t(this._step*this._arrowKeyMultiplier(i))),"ArrowDown"===i.code&&(i.preventDefault(),t(this._step*this._arrowKeyMultiplier(i)*-1))}),this.$input.addEventListener("wheel",i=>{this._inputFocused&&(i.preventDefault(),t(this._step*this._normalizeMouseWheel(i)))},{passive:!1}),this.$input.addEventListener("mousedown",t=>{i=t.clientX,e=s=t.clientY,r=!0,n=this.getValue(),l=0,window.addEventListener("mousemove",o),window.addEventListener("mouseup",a)}),this.$input.addEventListener("focus",()=>{this._inputFocused=!0}),this.$input.addEventListener("blur",()=>{this._inputFocused=!1,this.updateDisplay(),this._callOnFinishChange()})}_initSlider(){this._hasSlider=!0,this.$slider=document.createElement("div"),this.$slider.classList.add("slider"),this.$fill=document.createElement("div"),this.$fill.classList.add("fill"),this.$slider.appendChild(this.$fill),this.$widget.insertBefore(this.$slider,this.$input),this.domElement.classList.add("hasSlider");const t=t=>{const i=this.$slider.getBoundingClientRect();let e=(s=t,n=i.left,l=i.right,r=this._min,o=this._max,(s-n)/(l-n)*(o-r)+r);var s,n,l,r,o;this._snapClampSetValue(e)},i=i=>{t(i.clientX)},e=()=>{this._callOnFinishChange(),this._setDraggingStyle(!1),window.removeEventListener("mousemove",i),window.removeEventListener("mouseup",e)};let s,n,l=!1;const r=i=>{i.preventDefault(),this._setDraggingStyle(!0),t(i.touches[0].clientX),l=!1},o=i=>{if(l){const t=i.touches[0].clientX-s,e=i.touches[0].clientY-n;Math.abs(t)>Math.abs(e)?r(i):(window.removeEventListener("touchmove",o),window.removeEventListener("touchend",a))}else i.preventDefault(),t(i.touches[0].clientX)},a=()=>{this._callOnFinishChange(),this._setDraggingStyle(!1),window.removeEventListener("touchmove",o),window.removeEventListener("touchend",a)},h=this._callOnFinishChange.bind(this);let d;this.$slider.addEventListener("mousedown",s=>{this._setDraggingStyle(!0),t(s.clientX),window.addEventListener("mousemove",i),window.addEventListener("mouseup",e)}),this.$slider.addEventListener("touchstart",t=>{t.touches.length>1||(this._hasScrollBar?(s=t.touches[0].clientX,n=t.touches[0].clientY,l=!0):r(t),window.addEventListener("touchmove",o,{passive:!1}),window.addEventListener("touchend",a))},{passive:!1}),this.$slider.addEventListener("wheel",t=>{if(Math.abs(t.deltaX)<Math.abs(t.deltaY)&&this._hasScrollBar)return;t.preventDefault();const i=this._normalizeMouseWheel(t)*this._step;this._snapClampSetValue(this.getValue()+i),this.$input.value=this.getValue(),clearTimeout(d),d=setTimeout(h,400)},{passive:!1})}_setDraggingStyle(t,i="horizontal"){this.$slider&&this.$slider.classList.toggle("active",t),document.body.classList.toggle("lil-gui-dragging",t),document.body.classList.toggle("lil-gui-"+i,t)}_getImplicitStep(){return this._hasMin&&this._hasMax?(this._max-this._min)/1e3:.1}_onUpdateMinMax(){!this._hasSlider&&this._hasMin&&this._hasMax&&(this._stepExplicit||this.step(this._getImplicitStep(),!1),this._initSlider(),this.updateDisplay())}_normalizeMouseWheel(t){let{deltaX:i,deltaY:e}=t;Math.floor(t.deltaY)!==t.deltaY&&t.wheelDelta&&(i=0,e=-t.wheelDelta/120,e*=this._stepExplicit?1:10);return i+-e}_arrowKeyMultiplier(t){let i=this._stepExplicit?1:10;return t.shiftKey?i*=10:t.altKey&&(i/=10),i}_snap(t){const i=Math.round(t/this._step)*this._step;return parseFloat(i.toPrecision(15))}_clamp(t){return t<this._min&&(t=this._min),t>this._max&&(t=this._max),t}_snapClampSetValue(t){this.setValue(this._clamp(this._snap(t)))}get _hasScrollBar(){const t=this.parent.root.$children;return t.scrollHeight>t.clientHeight}get _hasMin(){return void 0!==this._min}get _hasMax(){return void 0!==this._max}}
```
</details>

#### Methods

##### `decimals(t: any): this`

<details><summary>Code</summary>

```ts
decimals(t){return this._decimals=t,this.updateDisplay(),this}
```
</details>

##### `min(t: any): this`

<details><summary>Code</summary>

```ts
min(t){return this._min=t,this._onUpdateMinMax(),this}
```
</details>

##### `max(t: any): this`

<details><summary>Code</summary>

```ts
max(t){return this._max=t,this._onUpdateMinMax(),this}
```
</details>

##### `step(t: any, i: boolean): this`

<details><summary>Code</summary>

```ts
step(t,i=!0){return this._step=t,this._stepExplicit=i,this}
```
</details>

##### `updateDisplay(): this`

<details><summary>Code</summary>

```ts
updateDisplay(){const t=this.getValue();if(this._hasSlider){let i=(t-this._min)/(this._max-this._min);i=Math.max(0,Math.min(i,1)),this.$fill.style.width=100*i+"%"}return this._inputFocused||(this.$input.value=void 0===this._decimals?t:t.toFixed(this._decimals)),this}
```
</details>

##### `_initInput(): void`

<details><summary>Code</summary>

```ts
_initInput(){this.$input=document.createElement("input"),this.$input.setAttribute("type","number"),this.$input.setAttribute("step","any"),this.$input.setAttribute("aria-labelledby",this.$name.id),this.$widget.appendChild(this.$input),this.$disable=this.$input;const t=t=>{const i=parseFloat(this.$input.value);isNaN(i)||(this._snapClampSetValue(i+t),this.$input.value=this.getValue())};let i,e,s,n,l,r=!1;const o=t=>{if(r){const s=t.clientX-i,n=t.clientY-e;Math.abs(n)>5?(t.preventDefault(),this.$input.blur(),r=!1,this._setDraggingStyle(!0,"vertical")):Math.abs(s)>5&&a()}if(!r){const i=t.clientY-s;l-=i*this._step*this._arrowKeyMultiplier(t),n+l>this._max?l=this._max-n:n+l<this._min&&(l=this._min-n),this._snapClampSetValue(n+l)}s=t.clientY},a=()=>{this._setDraggingStyle(!1,"vertical"),this._callOnFinishChange(),window.removeEventListener("mousemove",o),window.removeEventListener("mouseup",a)};this.$input.addEventListener("input",()=>{let t=parseFloat(this.$input.value);isNaN(t)||(this._stepExplicit&&(t=this._snap(t)),this.setValue(this._clamp(t)))}),this.$input.addEventListener("keydown",i=>{"Enter"===i.code&&this.$input.blur(),"ArrowUp"===i.code&&(i.preventDefault(),t(this._step*this._arrowKeyMultiplier(i))),"ArrowDown"===i.code&&(i.preventDefault(),t(this._step*this._arrowKeyMultiplier(i)*-1))}),this.$input.addEventListener("wheel",i=>{this._inputFocused&&(i.preventDefault(),t(this._step*this._normalizeMouseWheel(i)))},{passive:!1}),this.$input.addEventListener("mousedown",t=>{i=t.clientX,e=s=t.clientY,r=!0,n=this.getValue(),l=0,window.addEventListener("mousemove",o),window.addEventListener("mouseup",a)}),this.$input.addEventListener("focus",()=>{this._inputFocused=!0}),this.$input.addEventListener("blur",()=>{this._inputFocused=!1,this.updateDisplay(),this._callOnFinishChange()})}
```
</details>

##### `_initSlider(): void`

<details><summary>Code</summary>

```ts
_initSlider(){this._hasSlider=!0,this.$slider=document.createElement("div"),this.$slider.classList.add("slider"),this.$fill=document.createElement("div"),this.$fill.classList.add("fill"),this.$slider.appendChild(this.$fill),this.$widget.insertBefore(this.$slider,this.$input),this.domElement.classList.add("hasSlider");const t=t=>{const i=this.$slider.getBoundingClientRect();let e=(s=t,n=i.left,l=i.right,r=this._min,o=this._max,(s-n)/(l-n)*(o-r)+r);var s,n,l,r,o;this._snapClampSetValue(e)},i=i=>{t(i.clientX)},e=()=>{this._callOnFinishChange(),this._setDraggingStyle(!1),window.removeEventListener("mousemove",i),window.removeEventListener("mouseup",e)};let s,n,l=!1;const r=i=>{i.preventDefault(),this._setDraggingStyle(!0),t(i.touches[0].clientX),l=!1},o=i=>{if(l){const t=i.touches[0].clientX-s,e=i.touches[0].clientY-n;Math.abs(t)>Math.abs(e)?r(i):(window.removeEventListener("touchmove",o),window.removeEventListener("touchend",a))}else i.preventDefault(),t(i.touches[0].clientX)},a=()=>{this._callOnFinishChange(),this._setDraggingStyle(!1),window.removeEventListener("touchmove",o),window.removeEventListener("touchend",a)},h=this._callOnFinishChange.bind(this);let d;this.$slider.addEventListener("mousedown",s=>{this._setDraggingStyle(!0),t(s.clientX),window.addEventListener("mousemove",i),window.addEventListener("mouseup",e)}),this.$slider.addEventListener("touchstart",t=>{t.touches.length>1||(this._hasScrollBar?(s=t.touches[0].clientX,n=t.touches[0].clientY,l=!0):r(t),window.addEventListener("touchmove",o,{passive:!1}),window.addEventListener("touchend",a))},{passive:!1}),this.$slider.addEventListener("wheel",t=>{if(Math.abs(t.deltaX)<Math.abs(t.deltaY)&&this._hasScrollBar)return;t.preventDefault();const i=this._normalizeMouseWheel(t)*this._step;this._snapClampSetValue(this.getValue()+i),this.$input.value=this.getValue(),clearTimeout(d),d=setTimeout(h,400)},{passive:!1})}
```
</details>

##### `_setDraggingStyle(t: any, i: string): void`

<details><summary>Code</summary>

```ts
_setDraggingStyle(t,i="horizontal"){this.$slider&&this.$slider.classList.toggle("active",t),document.body.classList.toggle("lil-gui-dragging",t),document.body.classList.toggle("lil-gui-"+i,t)}
```
</details>

##### `_getImplicitStep(): number`

<details><summary>Code</summary>

```ts
_getImplicitStep(){return this._hasMin&&this._hasMax?(this._max-this._min)/1e3:.1}
```
</details>

##### `_onUpdateMinMax(): void`

<details><summary>Code</summary>

```ts
_onUpdateMinMax(){!this._hasSlider&&this._hasMin&&this._hasMax&&(this._stepExplicit||this.step(this._getImplicitStep(),!1),this._initSlider(),this.updateDisplay())}
```
</details>

##### `_normalizeMouseWheel(t: any): any`

<details><summary>Code</summary>

```ts
_normalizeMouseWheel(t){let{deltaX:i,deltaY:e}=t;Math.floor(t.deltaY)!==t.deltaY&&t.wheelDelta&&(i=0,e=-t.wheelDelta/120,e*=this._stepExplicit?1:10);return i+-e}
```
</details>

##### `_arrowKeyMultiplier(t: any): number`

<details><summary>Code</summary>

```ts
_arrowKeyMultiplier(t){let i=this._stepExplicit?1:10;return t.shiftKey?i*=10:t.altKey&&(i/=10),i}
```
</details>

##### `_snap(t: any): number`

<details><summary>Code</summary>

```ts
_snap(t){const i=Math.round(t/this._step)*this._step;return parseFloat(i.toPrecision(15))}
```
</details>

##### `_clamp(t: any): any`

<details><summary>Code</summary>

```ts
_clamp(t){return t<this._min&&(t=this._min),t>this._max&&(t=this._max),t}
```
</details>

##### `_snapClampSetValue(t: any): void`

<details><summary>Code</summary>

```ts
_snapClampSetValue(t){this.setValue(this._clamp(this._snap(t)))}
```
</details>

### `c`

<details><summary>Class Code</summary>

```ts
class c extends t{constructor(t,i,e,s){super(t,i,e,"option"),this.$select=document.createElement("select"),this.$select.setAttribute("aria-labelledby",this.$name.id),this.$display=document.createElement("div"),this.$display.classList.add("display"),this._values=Array.isArray(s)?s:Object.values(s),this._names=Array.isArray(s)?s:Object.keys(s),this._names.forEach(t=>{const i=document.createElement("option");i.innerHTML=t,this.$select.appendChild(i)}),this.$select.addEventListener("change",()=>{this.setValue(this._values[this.$select.selectedIndex]),this._callOnFinishChange()}),this.$select.addEventListener("focus",()=>{this.$display.classList.add("focus")}),this.$select.addEventListener("blur",()=>{this.$display.classList.remove("focus")}),this.$widget.appendChild(this.$select),this.$widget.appendChild(this.$display),this.$disable=this.$select,this.updateDisplay()}updateDisplay(){const t=this.getValue(),i=this._values.indexOf(t);return this.$select.selectedIndex=i,this.$display.innerHTML=-1===i?t:this._names[i],this}}
```
</details>

#### Methods

##### `updateDisplay(): this`

<details><summary>Code</summary>

```ts
updateDisplay(){const t=this.getValue(),i=this._values.indexOf(t);return this.$select.selectedIndex=i,this.$display.innerHTML=-1===i?t:this._names[i],this}
```
</details>

### `u`

<details><summary>Class Code</summary>

```ts
class u extends t{constructor(t,i,e){super(t,i,e,"string"),this.$input=document.createElement("input"),this.$input.setAttribute("type","text"),this.$input.setAttribute("aria-labelledby",this.$name.id),this.$input.addEventListener("input",()=>{this.setValue(this.$input.value)}),this.$input.addEventListener("keydown",t=>{"Enter"===t.code&&this.$input.blur()}),this.$input.addEventListener("blur",()=>{this._callOnFinishChange()}),this.$widget.appendChild(this.$input),this.$disable=this.$input,this.updateDisplay()}updateDisplay(){return this.$input.value=this.getValue(),this}}
```
</details>

#### Methods

##### `updateDisplay(): this`

<details><summary>Code</summary>

```ts
updateDisplay(){return this.$input.value=this.getValue(),this}
```
</details>

### `g`

<details><summary>Class Code</summary>

```ts
class g{constructor({parent:t,autoPlace:i=void 0===t,container:e,width:s,title:n="Controls",injectStyles:l=!0,touchStyles:r=!0}={}){if(this.parent=t,this.root=t?t.root:this,this.children=[],this.controllers=[],this.folders=[],this._closed=!1,this._hidden=!1,this.domElement=document.createElement("div"),this.domElement.classList.add("lil-gui"),this.$title=document.createElement("div"),this.$title.classList.add("title"),this.$title.setAttribute("role","button"),this.$title.setAttribute("aria-expanded",!0),this.$title.setAttribute("tabindex",0),this.$title.addEventListener("click",()=>this.openAnimated(this._closed)),this.$title.addEventListener("keydown",t=>{"Enter"!==t.code&&"Space"!==t.code||(t.preventDefault(),this.$title.click())}),this.$title.addEventListener("touchstart",()=>{},{passive:!0}),this.$children=document.createElement("div"),this.$children.classList.add("children"),this.domElement.appendChild(this.$title),this.domElement.appendChild(this.$children),this.title(n),r&&this.domElement.classList.add("allow-touch-styles"),this.parent)return this.parent.children.push(this),this.parent.folders.push(this),void this.parent.$children.appendChild(this.domElement);this.domElement.classList.add("root"),!p&&l&&(!function(t){const i=document.createElement("style");i.innerHTML=t;const e=document.querySelector("head link[rel=stylesheet], head style");e?document.head.insertBefore(i,e):document.head.appendChild(i)}('.lil-gui{--background-color:#1f1f1f;--text-color:#ebebeb;--title-background-color:#111;--title-text-color:#ebebeb;--widget-color:#424242;--hover-color:#4f4f4f;--focus-color:#595959;--number-color:#2cc9ff;--string-color:#a2db3c;--font-size:11px;--input-font-size:11px;--font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Arial,sans-serif;--font-family-mono:Menlo,Monaco,Consolas,"Droid Sans Mono",monospace;--padding:4px;--spacing:4px;--widget-height:20px;--name-width:45%;--slider-knob-width:2px;--slider-input-width:27%;--color-input-width:27%;--slider-input-min-width:45px;--color-input-min-width:45px;--folder-indent:7px;--widget-padding:0 0 0 3px;--widget-border-radius:2px;--checkbox-size:calc(var(--widget-height)*0.75);--scrollbar-width:5px;background-color:var(--background-color);color:var(--text-color);font-family:var(--font-family);font-size:var(--font-size);font-style:normal;font-weight:400;line-height:1;text-align:left;touch-action:manipulation;user-select:none;-webkit-user-select:none}.lil-gui,.lil-gui *{box-sizing:border-box;margin:0;padding:0}.lil-gui.root{display:flex;flex-direction:column;width:var(--width,245px)}.lil-gui.root>.title{background:var(--title-background-color);color:var(--title-text-color)}.lil-gui.root>.children{overflow-x:hidden;overflow-y:auto}.lil-gui.root>.children::-webkit-scrollbar{background:var(--background-color);height:var(--scrollbar-width);width:var(--scrollbar-width)}.lil-gui.root>.children::-webkit-scrollbar-thumb{background:var(--focus-color);border-radius:var(--scrollbar-width)}.lil-gui.force-touch-styles{--widget-height:28px;--padding:6px;--spacing:6px;--font-size:13px;--input-font-size:16px;--folder-indent:10px;--scrollbar-width:7px;--slider-input-min-width:50px;--color-input-min-width:65px}.lil-gui.autoPlace{max-height:100%;position:fixed;right:15px;top:0;z-index:1001}.lil-gui .controller{align-items:center;display:flex;margin:var(--spacing) 0;padding:0 var(--padding)}.lil-gui .controller.disabled{opacity:.5}.lil-gui .controller.disabled,.lil-gui .controller.disabled *{pointer-events:none!important}.lil-gui .controller>.name{flex-shrink:0;line-height:var(--widget-height);min-width:var(--name-width);padding-right:var(--spacing);white-space:pre}.lil-gui .controller .widget{align-items:center;display:flex;min-height:var(--widget-height);position:relative;width:100%}.lil-gui .controller.string input{color:var(--string-color)}.lil-gui .controller.boolean .widget{cursor:pointer}.lil-gui .controller.color .display{border-radius:var(--widget-border-radius);height:var(--widget-height);position:relative;width:100%}.lil-gui .controller.color input[type=color]{cursor:pointer;height:100%;opacity:0;width:100%}.lil-gui .controller.color input[type=text]{flex-shrink:0;font-family:var(--font-family-mono);margin-left:var(--spacing);min-width:var(--color-input-min-width);width:var(--color-input-width)}.lil-gui .controller.option select{max-width:100%;opacity:0;position:absolute;width:100%}.lil-gui .controller.option .display{background:var(--widget-color);border-radius:var(--widget-border-radius);height:var(--widget-height);line-height:var(--widget-height);max-width:100%;overflow:hidden;padding-left:.55em;padding-right:1.75em;pointer-events:none;position:relative;word-break:break-all}.lil-gui .controller.option .display.active{background:var(--focus-color)}.lil-gui .controller.option .display:after{bottom:0;content:"↕";font-family:lil-gui;padding-right:.375em;position:absolute;right:0;top:0}.lil-gui .controller.option .widget,.lil-gui .controller.option select{cursor:pointer}.lil-gui .controller.number input{color:var(--number-color)}.lil-gui .controller.number.hasSlider input{flex-shrink:0;margin-left:var(--spacing);min-width:var(--slider-input-min-width);width:var(--slider-input-width)}.lil-gui .controller.number .slider{background-color:var(--widget-color);border-radius:var(--widget-border-radius);cursor:ew-resize;height:var(--widget-height);overflow:hidden;padding-right:var(--slider-knob-width);touch-action:pan-y;width:100%}.lil-gui .controller.number .slider.active{background-color:var(--focus-color)}.lil-gui .controller.number .slider.active .fill{opacity:.95}.lil-gui .controller.number .fill{border-right:var(--slider-knob-width) solid var(--number-color);box-sizing:content-box;height:100%}.lil-gui-dragging .lil-gui{--hover-color:var(--widget-color)}.lil-gui-dragging *{cursor:ew-resize!important}.lil-gui-dragging.lil-gui-vertical *{cursor:ns-resize!important}.lil-gui .title{--title-height:calc(var(--widget-height) + var(--spacing)*1.25);-webkit-tap-highlight-color:transparent;text-decoration-skip:objects;cursor:pointer;font-weight:600;height:var(--title-height);line-height:calc(var(--title-height) - 4px);outline:none;padding:0 var(--padding)}.lil-gui .title:before{content:"▾";display:inline-block;font-family:lil-gui;padding-right:2px}.lil-gui .title:active{background:var(--title-background-color);opacity:.75}.lil-gui.root>.title:focus{text-decoration:none!important}.lil-gui.closed>.title:before{content:"▸"}.lil-gui.closed>.children{opacity:0;transform:translateY(-7px)}.lil-gui.closed:not(.transition)>.children{display:none}.lil-gui.transition>.children{overflow:hidden;pointer-events:none;transition-duration:.3s;transition-property:height,opacity,transform;transition-timing-function:cubic-bezier(.2,.6,.35,1)}.lil-gui .children:empty:before{content:"Empty";display:block;font-style:italic;height:var(--widget-height);line-height:var(--widget-height);margin:var(--spacing) 0;opacity:.5;padding:0 var(--padding)}.lil-gui.root>.children>.lil-gui>.title{border-width:0;border-bottom:1px solid var(--widget-color);border-left:0 solid var(--widget-color);border-right:0 solid var(--widget-color);border-top:1px solid var(--widget-color);transition:border-color .3s}.lil-gui.root>.children>.lil-gui.closed>.title{border-bottom-color:transparent}.lil-gui+.controller{border-top:1px solid var(--widget-color);margin-top:0;padding-top:var(--spacing)}.lil-gui .lil-gui .lil-gui>.title{border:none}.lil-gui .lil-gui .lil-gui>.children{border:none;border-left:2px solid var(--widget-color);margin-left:var(--folder-indent)}.lil-gui .lil-gui .controller{border:none}.lil-gui input{-webkit-tap-highlight-color:transparent;background:var(--widget-color);border:0;border-radius:var(--widget-border-radius);color:var(--text-color);font-family:var(--font-family);font-size:var(--input-font-size);height:var(--widget-height);outline:none;width:100%}.lil-gui input:disabled{opacity:1}.lil-gui input[type=number],.lil-gui input[type=text]{padding:var(--widget-padding)}.lil-gui input[type=number]:focus,.lil-gui input[type=text]:focus{background:var(--focus-color)}.lil-gui input::-webkit-inner-spin-button,.lil-gui input::-webkit-outer-spin-button{-webkit-appearance:none;margin:0}.lil-gui input[type=number]{-moz-appearance:textfield}.lil-gui input[type=checkbox]{appearance:none;-webkit-appearance:none;border-radius:var(--widget-border-radius);cursor:pointer;height:var(--checkbox-size);text-align:center;width:var(--checkbox-size)}.lil-gui input[type=checkbox]:checked:before{content:"✓";font-family:lil-gui;font-size:var(--checkbox-size);line-height:var(--checkbox-size)}.lil-gui button{-webkit-tap-highlight-color:transparent;background:var(--widget-color);border:1px solid var(--widget-color);border-radius:var(--widget-border-radius);color:var(--text-color);cursor:pointer;font-family:var(--font-family);font-size:var(--font-size);height:var(--widget-height);line-height:calc(var(--widget-height) - 4px);outline:none;text-align:center;text-transform:none;width:100%}.lil-gui button:active{background:var(--focus-color)}@font-face{font-family:lil-gui;src:url("data:application/font-woff;charset=utf-8;base64,d09GRgABAAAAAAUsAAsAAAAACJwAAQAAAAAAAAAAAAAAAAAAAAAAAAAAAABHU1VCAAABCAAAAH4AAADAImwmYE9TLzIAAAGIAAAAPwAAAGBKqH5SY21hcAAAAcgAAAD0AAACrukyyJBnbHlmAAACvAAAAF8AAACEIZpWH2hlYWQAAAMcAAAAJwAAADZfcj2zaGhlYQAAA0QAAAAYAAAAJAC5AHhobXR4AAADXAAAABAAAABMAZAAAGxvY2EAAANsAAAAFAAAACgCEgIybWF4cAAAA4AAAAAeAAAAIAEfABJuYW1lAAADoAAAASIAAAIK9SUU/XBvc3QAAATEAAAAZgAAAJCTcMc2eJxVjbEOgjAURU+hFRBK1dGRL+ALnAiToyMLEzFpnPz/eAshwSa97517c/MwwJmeB9kwPl+0cf5+uGPZXsqPu4nvZabcSZldZ6kfyWnomFY/eScKqZNWupKJO6kXN3K9uCVoL7iInPr1X5baXs3tjuMqCtzEuagm/AAlzQgPAAB4nGNgYRBlnMDAysDAYM/gBiT5oLQBAwuDJAMDEwMrMwNWEJDmmsJwgCFeXZghBcjlZMgFCzOiKOIFAB71Bb8AeJy1kjFuwkAQRZ+DwRAwBtNQRUGKQ8OdKCAWUhAgKLhIuAsVSpWz5Bbkj3dEgYiUIszqWdpZe+Z7/wB1oCYmIoboiwiLT2WjKl/jscrHfGg/pKdMkyklC5Zs2LEfHYpjcRoPzme9MWWmk3dWbK9ObkWkikOetJ554fWyoEsmdSlt+uR0pCJR34b6t/TVg1SY3sYvdf8vuiKrpyaDXDISiegp17p7579Gp3p++y7HPAiY9pmTibljrr85qSidtlg4+l25GLCaS8e6rRxNBmsnERunKbaOObRz7N72ju5vdAjYpBXHgJylOAVsMseDAPEP8LYoUHicY2BiAAEfhiAGJgZWBgZ7RnFRdnVJELCQlBSRlATJMoLV2DK4glSYs6ubq5vbKrJLSbGrgEmovDuDJVhe3VzcXFwNLCOILB/C4IuQ1xTn5FPilBTj5FPmBAB4WwoqAHicY2BkYGAA4sk1sR/j+W2+MnAzpDBgAyEMQUCSg4EJxAEAwUgFHgB4nGNgZGBgSGFggJMhDIwMqEAYAByHATJ4nGNgAIIUNEwmAABl3AGReJxjYAACIQYlBiMGJ3wQAEcQBEV4nGNgZGBgEGZgY2BiAAEQyQWEDAz/wXwGAAsPATIAAHicXdBNSsNAHAXwl35iA0UQXYnMShfS9GPZA7T7LgIu03SSpkwzYTIt1BN4Ak/gKTyAeCxfw39jZkjymzcvAwmAW/wgwHUEGDb36+jQQ3GXGot79L24jxCP4gHzF/EIr4jEIe7wxhOC3g2TMYy4Q7+Lu/SHuEd/ivt4wJd4wPxbPEKMX3GI5+DJFGaSn4qNzk8mcbKSR6xdXdhSzaOZJGtdapd4vVPbi6rP+cL7TGXOHtXKll4bY1Xl7EGnPtp7Xy2n00zyKLVHfkHBa4IcJ2oD3cgggWvt/V/FbDrUlEUJhTn/0azVWbNTNr0Ens8de1tceK9xZmfB1CPjOmPH4kitmvOubcNpmVTN3oFJyjzCvnmrwhJTzqzVj9jiSX911FjeAAB4nG3HMRKCMBBA0f0giiKi4DU8k0V2GWbIZDOh4PoWWvq6J5V8If9NVNQcaDhyouXMhY4rPTcG7jwYmXhKq8Wz+p762aNaeYXom2n3m2dLTVgsrCgFJ7OTmIkYbwIbC6vIB7WmFfAAAA==") format("woff")}@media (pointer:coarse){.lil-gui.allow-touch-styles{--widget-height:28px;--padding:6px;--spacing:6px;--font-size:13px;--input-font-size:16px;--folder-indent:10px;--scrollbar-width:7px;--slider-input-min-width:50px;--color-input-min-width:65px}}@media (hover:hover){.lil-gui .controller.color .display:hover:before{border:1px solid #fff9;border-radius:var(--widget-border-radius);bottom:0;content:" ";display:block;left:0;position:absolute;right:0;top:0}.lil-gui .controller.option .display.focus{background:var(--focus-color)}.lil-gui .controller.option .widget:hover .display{background:var(--hover-color)}.lil-gui .controller.number .slider:hover{background-color:var(--hover-color)}body:not(.lil-gui-dragging) .lil-gui .title:hover{background:var(--title-background-color);opacity:.85}.lil-gui .title:focus{text-decoration:underline var(--focus-color)}.lil-gui input:hover{background:var(--hover-color)}.lil-gui input:active{background:var(--focus-color)}.lil-gui input[type=checkbox]:focus{box-shadow:inset 0 0 0 1px var(--focus-color)}.lil-gui button:hover{background:var(--hover-color);border-color:var(--hover-color)}.lil-gui button:focus{border-color:var(--focus-color)}}'),p=!0),e?e.appendChild(this.domElement):i&&(this.domElement.classList.add("autoPlace"),document.body.appendChild(this.domElement)),s&&this.domElement.style.setProperty("--width",s+"px"),this.domElement.addEventListener("keydown",t=>t.stopPropagation()),this.domElement.addEventListener("keyup",t=>t.stopPropagation())}add(t,e,s,n,l){if(Object(s)===s)return new c(this,t,e,s);const r=t[e];switch(typeof r){case"number":return new d(this,t,e,s,n,l);case"boolean":return new i(this,t,e);case"string":return new u(this,t,e);case"function":return new h(this,t,e)}console.error("gui.add failed\n\tproperty:",e,"\n\tobject:",t,"\n\tvalue:",r)}addColor(t,i,e=1){return new a(this,t,i,e)}addFolder(t){return new g({parent:this,title:t})}load(t,i=!0){return t.controllers&&this.controllers.forEach(i=>{i instanceof h||i._name in t.controllers&&i.load(t.controllers[i._name])}),i&&t.folders&&this.folders.forEach(i=>{i._title in t.folders&&i.load(t.folders[i._title])}),this}save(t=!0){const i={controllers:{},folders:{}};return this.controllers.forEach(t=>{if(!(t instanceof h)){if(t._name in i.controllers)throw new Error(`Cannot save GUI with duplicate property "${t._name}"`);i.controllers[t._name]=t.save()}}),t&&this.folders.forEach(t=>{if(t._title in i.folders)throw new Error(`Cannot save GUI with duplicate folder "${t._title}"`);i.folders[t._title]=t.save()}),i}open(t=!0){return this._closed=!t,this.$title.setAttribute("aria-expanded",!this._closed),this.domElement.classList.toggle("closed",this._closed),this}close(){return this.open(!1)}show(t=!0){return this._hidden=!t,this.domElement.style.display=this._hidden?"none":"",this}hide(){return this.show(!1)}openAnimated(t=!0){return this._closed=!t,this.$title.setAttribute("aria-expanded",!this._closed),requestAnimationFrame(()=>{const i=this.$children.clientHeight;this.$children.style.height=i+"px",this.domElement.classList.add("transition");const e=t=>{t.target===this.$children&&(this.$children.style.height="",this.domElement.classList.remove("transition"),this.$children.removeEventListener("transitionend",e))};this.$children.addEventListener("transitionend",e);const s=t?this.$children.scrollHeight:0;this.domElement.classList.toggle("closed",!t),requestAnimationFrame(()=>{this.$children.style.height=s+"px"})}),this}title(t){return this._title=t,this.$title.innerHTML=t,this}reset(t=!0){return(t?this.controllersRecursive():this.controllers).forEach(t=>t.reset()),this}onChange(t){return this._onChange=t,this}_callOnChange(t){this.parent&&this.parent._callOnChange(t),void 0!==this._onChange&&this._onChange.call(this,{object:t.object,property:t.property,value:t.getValue(),controller:t})}onFinishChange(t){return this._onFinishChange=t,this}_callOnFinishChange(t){this.parent&&this.parent._callOnFinishChange(t),void 0!==this._onFinishChange&&this._onFinishChange.call(this,{object:t.object,property:t.property,value:t.getValue(),controller:t})}destroy(){this.parent&&(this.parent.children.splice(this.parent.children.indexOf(this),1),this.parent.folders.splice(this.parent.folders.indexOf(this),1)),this.domElement.parentElement&&this.domElement.parentElement.removeChild(this.domElement),Array.from(this.children).forEach(t=>t.destroy())}controllersRecursive(){let t=Array.from(this.controllers);return this.folders.forEach(i=>{t=t.concat(i.controllersRecursive())}),t}foldersRecursive(){let t=Array.from(this.folders);return this.folders.forEach(i=>{t=t.concat(i.foldersRecursive())}),t}}
```
</details>

#### Methods

##### `add(t: any, e: any, s: any, n: any, l: any): i | d | c | u | h`

<details><summary>Code</summary>

```ts
add(t,e,s,n,l){if(Object(s)===s)return new c(this,t,e,s);const r=t[e];switch(typeof r){case"number":return new d(this,t,e,s,n,l);case"boolean":return new i(this,t,e);case"string":return new u(this,t,e);case"function":return new h(this,t,e)}console.error("gui.add failed\n\tproperty:",e,"\n\tobject:",t,"\n\tvalue:",r)}
```
</details>

##### `addColor(t: any, i: any, e: number): a`

<details><summary>Code</summary>

```ts
addColor(t,i,e=1){return new a(this,t,i,e)}
```
</details>

##### `addFolder(t: any): g`

<details><summary>Code</summary>

```ts
addFolder(t){return new g({parent:this,title:t})}
```
</details>

##### `load(t: any, i: boolean): this`

<details><summary>Code</summary>

```ts
load(t,i=!0){return t.controllers&&this.controllers.forEach(i=>{i instanceof h||i._name in t.controllers&&i.load(t.controllers[i._name])}),i&&t.folders&&this.folders.forEach(i=>{i._title in t.folders&&i.load(t.folders[i._title])}),this}
```
</details>

##### `save(t: boolean): { controllers: {}; folders: {}; }`

<details><summary>Code</summary>

```ts
save(t=!0){const i={controllers:{},folders:{}};return this.controllers.forEach(t=>{if(!(t instanceof h)){if(t._name in i.controllers)throw new Error(`Cannot save GUI with duplicate property "${t._name}"`);i.controllers[t._name]=t.save()}}),t&&this.folders.forEach(t=>{if(t._title in i.folders)throw new Error(`Cannot save GUI with duplicate folder "${t._title}"`);i.folders[t._title]=t.save()}),i}
```
</details>

##### `open(t: boolean): this`

<details><summary>Code</summary>

```ts
open(t=!0){return this._closed=!t,this.$title.setAttribute("aria-expanded",!this._closed),this.domElement.classList.toggle("closed",this._closed),this}
```
</details>

##### `close(): this`

<details><summary>Code</summary>

```ts
close(){return this.open(!1)}
```
</details>

##### `show(t: boolean): this`

<details><summary>Code</summary>

```ts
show(t=!0){return this._hidden=!t,this.domElement.style.display=this._hidden?"none":"",this}
```
</details>

##### `hide(): this`

<details><summary>Code</summary>

```ts
hide(){return this.show(!1)}
```
</details>

##### `openAnimated(t: boolean): this`

<details><summary>Code</summary>

```ts
openAnimated(t=!0){return this._closed=!t,this.$title.setAttribute("aria-expanded",!this._closed),requestAnimationFrame(()=>{const i=this.$children.clientHeight;this.$children.style.height=i+"px",this.domElement.classList.add("transition");const e=t=>{t.target===this.$children&&(this.$children.style.height="",this.domElement.classList.remove("transition"),this.$children.removeEventListener("transitionend",e))};this.$children.addEventListener("transitionend",e);const s=t?this.$children.scrollHeight:0;this.domElement.classList.toggle("closed",!t),requestAnimationFrame(()=>{this.$children.style.height=s+"px"})}),this}
```
</details>

##### `title(t: any): this`

<details><summary>Code</summary>

```ts
title(t){return this._title=t,this.$title.innerHTML=t,this}
```
</details>

##### `reset(t: boolean): this`

<details><summary>Code</summary>

```ts
reset(t=!0){return(t?this.controllersRecursive():this.controllers).forEach(t=>t.reset()),this}
```
</details>

##### `onChange(t: any): this`

<details><summary>Code</summary>

```ts
onChange(t){return this._onChange=t,this}
```
</details>

##### `_callOnChange(t: any): void`

<details><summary>Code</summary>

```ts
_callOnChange(t){this.parent&&this.parent._callOnChange(t),void 0!==this._onChange&&this._onChange.call(this,{object:t.object,property:t.property,value:t.getValue(),controller:t})}
```
</details>

##### `onFinishChange(t: any): this`

<details><summary>Code</summary>

```ts
onFinishChange(t){return this._onFinishChange=t,this}
```
</details>

##### `_callOnFinishChange(t: any): void`

<details><summary>Code</summary>

```ts
_callOnFinishChange(t){this.parent&&this.parent._callOnFinishChange(t),void 0!==this._onFinishChange&&this._onFinishChange.call(this,{object:t.object,property:t.property,value:t.getValue(),controller:t})}
```
</details>

##### `destroy(): void`

<details><summary>Code</summary>

```ts
destroy(){this.parent&&(this.parent.children.splice(this.parent.children.indexOf(this),1),this.parent.folders.splice(this.parent.folders.indexOf(this),1)),this.domElement.parentElement&&this.domElement.parentElement.removeChild(this.domElement),Array.from(this.children).forEach(t=>t.destroy())}
```
</details>

##### `controllersRecursive(): any[]`

<details><summary>Code</summary>

```ts
controllersRecursive(){let t=Array.from(this.controllers);return this.folders.forEach(i=>{t=t.concat(i.controllersRecursive())}),t}
```
</details>

##### `foldersRecursive(): any[]`

<details><summary>Code</summary>

```ts
foldersRecursive(){let t=Array.from(this.folders);return this.folders.forEach(i=>{t=t.concat(i.foldersRecursive())}),t}
```
</details>


---