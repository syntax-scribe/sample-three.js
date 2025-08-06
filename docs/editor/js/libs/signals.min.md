[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `signals.min.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 47 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/signals.min.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `a` | `this` | let/var | `this` | ✗ |
| `b` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `number` | let/var | `this._bindings.length` | ✗ |
| `c` | `number` | let/var | `this._bindings.length` | ✗ |
| `d` | `any` | let/var | `*not shown*` | ✗ |
| `f` | `typeof e` | let/var | `e` | ✗ |


---

## Functions

### `h(a: any, b: any, c: any, d: any, e: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`d`** `any`
- **`e`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function h(a,b,c,d,e){this._listener=b;this._isOnce=c;this.context=d;this._signal=a;this._priority=e||0}
```
</details>

### `g(a: any, b: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `void`

**Calls:**

- `Error`
- `"listener is a required param of {fn}() and should be a Function.".replace`

<details><summary>Code</summary>

```typescript
function g(a,b){if(typeof a!=="function")throw Error("listener is a required param of {fn}() and should be a Function.".replace("{fn}",b));}
```
</details>

### `e(): void`

**Returns:** `void`

**Calls:**

- `e.prototype.dispatch.apply`

<details><summary>Code</summary>

```typescript
function e(){this._bindings=[];this._prevParams=null;var a=this;this.dispatch=function(){e.prototype.dispatch.apply(a,arguments)}}
```
</details>

### `execute(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `this.params.concat`
- `this._listener.apply`
- `this.detach`

<details><summary>Code</summary>

```typescript
function(a){var b;this.active&&this._listener&&(a=this.params?this.params.concat(a):
a,b=this._listener.apply(this.context,a),this._isOnce&&this.detach());return b}
```
</details>

### `detach(): any`

**Returns:** `any`

**Calls:**

- `this.isBound`
- `this._signal.remove`

<details><summary>Code</summary>

```typescript
function(){return this.isBound()?this._signal.remove(this._listener,this.context):null}
```
</details>

### `isBound(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(){return!!this._signal&&!!this._listener}
```
</details>

### `isOnce(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this._isOnce}
```
</details>

### `getListener(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this._listener}
```
</details>

### `getSignal(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this._signal}
```
</details>

### `_destroy(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(){delete this._signal;delete this._listener;delete this.context}
```
</details>

### `toString(): string`

**Returns:** `string`

**Calls:**

- `this.isBound`

<details><summary>Code</summary>

```typescript
function(){return"[SignalBinding isOnce:"+this._isOnce+
", isBound:"+this.isBound()+", active:"+this.active+"]"}
```
</details>

### `execute(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `this.params.concat`
- `this._listener.apply`
- `this.detach`

<details><summary>Code</summary>

```typescript
function(a){var b;this.active&&this._listener&&(a=this.params?this.params.concat(a):
a,b=this._listener.apply(this.context,a),this._isOnce&&this.detach());return b}
```
</details>

### `detach(): any`

**Returns:** `any`

**Calls:**

- `this.isBound`
- `this._signal.remove`

<details><summary>Code</summary>

```typescript
function(){return this.isBound()?this._signal.remove(this._listener,this.context):null}
```
</details>

### `isBound(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(){return!!this._signal&&!!this._listener}
```
</details>

### `isOnce(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this._isOnce}
```
</details>

### `getListener(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this._listener}
```
</details>

### `getSignal(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(){return this._signal}
```
</details>

### `_destroy(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(){delete this._signal;delete this._listener;delete this.context}
```
</details>

### `toString(): string`

**Returns:** `string`

**Calls:**

- `this.isBound`

<details><summary>Code</summary>

```typescript
function(){return"[SignalBinding isOnce:"+this._isOnce+
", isBound:"+this.isBound()+", active:"+this.active+"]"}
```
</details>

### `_registerListener(a: any, b: any, c: any, d: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`d`** `any`

**Returns:** `any`

**Calls:**

- `this._indexOfListener`
- `a.isOnce`
- `Error`
- `this._addBinding`
- `a.execute`

<details><summary>Code</summary>

```typescript
function(a,b,c,d){var e=this._indexOfListener(a,c);if(e!==-1){if(a=this._bindings[e],a.isOnce()!==b)throw Error("You cannot add"+(b?"":"Once")+"() then add"+(!b?"":"Once")+"() the same listener without removing the relationship first.");}else a=new h(this,a,b,c,d),this._addBinding(a);this.memorize&&this._prevParams&&a.execute(this._prevParams);return a}
```
</details>

### `_addBinding(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `this._bindings.splice`

<details><summary>Code</summary>

```typescript
function(a){var b=this._bindings.length;do--b;while(this._bindings[b]&&a._priority<=this._bindings[b]._priority);this._bindings.splice(b+1,0,a)}
```
</details>

### `_indexOfListener(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function(a,b){for(var c=this._bindings.length,d;c--;)if(d=this._bindings[c],d._listener===a&&d.context===b)return c;return-1}
```
</details>

### `has(a: any, b: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `boolean`

**Calls:**

- `this._indexOfListener`

<details><summary>Code</summary>

```typescript
function(a,b){return this._indexOfListener(a,b)!==-1}
```
</details>

### `add(a: any, b: any, c: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `any`

**Calls:**

- `g`
- `this._registerListener`

<details><summary>Code</summary>

```typescript
function(a,b,c){g(a,"add");return this._registerListener(a,!1,b,c)}
```
</details>

### `addOnce(a: any, b: any, c: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `any`

**Calls:**

- `g`
- `this._registerListener`

<details><summary>Code</summary>

```typescript
function(a,b,c){g(a,"addOnce");return this._registerListener(a,
!0,b,c)}
```
</details>

### `remove(a: any, b: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `g`
- `this._indexOfListener`
- `this._bindings[c]._destroy`
- `this._bindings.splice`

<details><summary>Code</summary>

```typescript
function(a,b){g(a,"remove");var c=this._indexOfListener(a,b);c!==-1&&(this._bindings[c]._destroy(),this._bindings.splice(c,1));return a}
```
</details>

### `removeAll(): void`

**Returns:** `void`

**Calls:**

- `this._bindings[a]._destroy`

<details><summary>Code</summary>

```typescript
function(){for(var a=this._bindings.length;a--;)this._bindings[a]._destroy();this._bindings.length=0}
```
</details>

### `getNumListeners(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function(){return this._bindings.length}
```
</details>

### `halt(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(){this._shouldPropagate=!1}
```
</details>

### `dispatch(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `Array.prototype.slice.call`
- `this._bindings.slice`
- `d[c].execute`

<details><summary>Code</summary>

```typescript
function(a){if(this.active){var b=Array.prototype.slice.call(arguments),c=this._bindings.length,d;if(this.memorize)this._prevParams=
b;if(c){d=this._bindings.slice();this._shouldPropagate=!0;do c--;while(d[c]&&this._shouldPropagate&&d[c].execute(b)!==!1)}}}
```
</details>

### `forget(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(){this._prevParams=null}
```
</details>

### `dispose(): void`

**Returns:** `void`

**Calls:**

- `this.removeAll`

<details><summary>Code</summary>

```typescript
function(){this.removeAll();delete this._bindings;delete this._prevParams}
```
</details>

### `toString(): string`

**Returns:** `string`

**Calls:**

- `this.getNumListeners`

<details><summary>Code</summary>

```typescript
function(){return"[Signal active:"+this.active+" numListeners:"+this.getNumListeners()+"]"}
```
</details>

### `_registerListener(a: any, b: any, c: any, d: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`d`** `any`

**Returns:** `any`

**Calls:**

- `this._indexOfListener`
- `a.isOnce`
- `Error`
- `this._addBinding`
- `a.execute`

<details><summary>Code</summary>

```typescript
function(a,b,c,d){var e=this._indexOfListener(a,c);if(e!==-1){if(a=this._bindings[e],a.isOnce()!==b)throw Error("You cannot add"+(b?"":"Once")+"() then add"+(!b?"":"Once")+"() the same listener without removing the relationship first.");}else a=new h(this,a,b,c,d),this._addBinding(a);this.memorize&&this._prevParams&&a.execute(this._prevParams);return a}
```
</details>

### `_addBinding(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `this._bindings.splice`

<details><summary>Code</summary>

```typescript
function(a){var b=this._bindings.length;do--b;while(this._bindings[b]&&a._priority<=this._bindings[b]._priority);this._bindings.splice(b+1,0,a)}
```
</details>

### `_indexOfListener(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function(a,b){for(var c=this._bindings.length,d;c--;)if(d=this._bindings[c],d._listener===a&&d.context===b)return c;return-1}
```
</details>

### `has(a: any, b: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `boolean`

**Calls:**

- `this._indexOfListener`

<details><summary>Code</summary>

```typescript
function(a,b){return this._indexOfListener(a,b)!==-1}
```
</details>

### `add(a: any, b: any, c: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `any`

**Calls:**

- `g`
- `this._registerListener`

<details><summary>Code</summary>

```typescript
function(a,b,c){g(a,"add");return this._registerListener(a,!1,b,c)}
```
</details>

### `addOnce(a: any, b: any, c: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `any`

**Calls:**

- `g`
- `this._registerListener`

<details><summary>Code</summary>

```typescript
function(a,b,c){g(a,"addOnce");return this._registerListener(a,
!0,b,c)}
```
</details>

### `remove(a: any, b: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `g`
- `this._indexOfListener`
- `this._bindings[c]._destroy`
- `this._bindings.splice`

<details><summary>Code</summary>

```typescript
function(a,b){g(a,"remove");var c=this._indexOfListener(a,b);c!==-1&&(this._bindings[c]._destroy(),this._bindings.splice(c,1));return a}
```
</details>

### `removeAll(): void`

**Returns:** `void`

**Calls:**

- `this._bindings[a]._destroy`

<details><summary>Code</summary>

```typescript
function(){for(var a=this._bindings.length;a--;)this._bindings[a]._destroy();this._bindings.length=0}
```
</details>

### `getNumListeners(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function(){return this._bindings.length}
```
</details>

### `halt(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(){this._shouldPropagate=!1}
```
</details>

### `dispatch(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `Array.prototype.slice.call`
- `this._bindings.slice`
- `d[c].execute`

<details><summary>Code</summary>

```typescript
function(a){if(this.active){var b=Array.prototype.slice.call(arguments),c=this._bindings.length,d;if(this.memorize)this._prevParams=
b;if(c){d=this._bindings.slice();this._shouldPropagate=!0;do c--;while(d[c]&&this._shouldPropagate&&d[c].execute(b)!==!1)}}}
```
</details>

### `forget(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function(){this._prevParams=null}
```
</details>

### `dispose(): void`

**Returns:** `void`

**Calls:**

- `this.removeAll`

<details><summary>Code</summary>

```typescript
function(){this.removeAll();delete this._bindings;delete this._prevParams}
```
</details>

### `toString(): string`

**Returns:** `string`

**Calls:**

- `this.getNumListeners`

<details><summary>Code</summary>

```typescript
function(){return"[Signal active:"+this.active+" numListeners:"+this.getNumListeners()+"]"}
```
</details>


---