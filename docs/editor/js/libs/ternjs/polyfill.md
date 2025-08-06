[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `polyfill.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📊 Variables & Constants | 72 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/ternjs/polyfill.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `empty` | `any` | let/var | `frame.contentWindow.Object.prototype` | ✗ |
| `AP` | `any[]` | let/var | `Array.prototype` | ✗ |
| `from` | `number` | let/var | `0` | ✗ |
| `to` | `any` | let/var | `this.length` | ✗ |
| `e` | `any` | let/var | `void 0` | ✗ |
| `i` | `boolean` | let/var | `!0` | ✗ |
| `k` | `any` | let/var | `null` | ✗ |
| `l` | `() => string` | let/var | `{}.toString` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `n` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `any` | let/var | `"function"===typeof define&&define.c` | ✗ |
| `q` | `any` | let/var | `!p&&"object"==typeof exports&&exports` | ✗ |
| `r` | `any` | let/var | `*not shown*` | ✗ |
| `t` | `any` | let/var | `*not shown*` | ✗ |
| `u` | `any` | let/var | `*not shown*` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `z` | `any` | let/var | `*not shown*` | ✗ |
| `B` | `any` | let/var | `*not shown*` | ✗ |
| `C` | `any` | let/var | `*not shown*` | ✗ |
| `D` | `any` | let/var | `*not shown*` | ✗ |
| `E` | `any` | let/var | `*not shown*` | ✗ |
| `F` | `any` | let/var | `*not shown*` | ✗ |
| `G` | `any` | let/var | `*not shown*` | ✗ |
| `H` | `any` | let/var | `*not shown*` | ✗ |
| `I` | `any` | let/var | `*not shown*` | ✗ |
| `J` | `Date` | let/var | `new Date(-3509827334573292)` | ✗ |
| `K` | `any` | let/var | `*not shown*` | ✗ |
| `O` | `any` | let/var | `*not shown*` | ✗ |
| `P` | `any` | let/var | `*not shown*` | ✗ |
| `c` | `any` | let/var | `*not shown*` | ✗ |
| `a` | `any` | let/var | `*not shown*` | ✗ |
| `d` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `boolean` | let/var | `b=="json"` | ✗ |
| `c` | `{ __proto__: any; }` | let/var | `{}` | ✗ |
| `a` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `undefined` | let/var | `this.__proto__` | ✗ |
| `a` | `any` | let/var | `a in(this.__proto__=k,this)` | ✗ |
| `c` | `any` | let/var | `(this.constructor\|\|a).prototype` | ✗ |
| `a` | `number` | let/var | `0` | ✗ |
| `d` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `f` | `any` | let/var | `*not shown*` | ✗ |
| `c` | `{}` | let/var | `{}` | ✗ |
| `d` | `boolean` | let/var | `l.call(a)=="[object Function]"` | ✗ |
| `f` | `any` | let/var | `*not shown*` | ✗ |
| `c` | `boolean` | let/var | `l.call(a)=="[object Function]"` | ✗ |
| `d` | `any` | let/var | `*not shown*` | ✗ |
| `f` | `any` | let/var | `*not shown*` | ✗ |
| `c` | `boolean` | let/var | `l.call(a)=="[object Function]"` | ✗ |
| `d` | `any` | let/var | `*not shown*` | ✗ |
| `g` | `any` | let/var | `c[b]` | ✗ |
| `h` | `any` | let/var | `*not shown*` | ✗ |
| `s` | `any` | let/var | `*not shown*` | ✗ |
| `v` | `any` | let/var | `*not shown*` | ✗ |
| `w` | `any` | let/var | `*not shown*` | ✗ |
| `L` | `any` | let/var | `*not shown*` | ✗ |
| `M` | `any` | let/var | `*not shown*` | ✗ |
| `N` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `A` | `any` | let/var | `*not shown*` | ✗ |
| `d` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `f` | `any` | let/var | `*not shown*` | ✗ |
| `o` | `any` | let/var | `*not shown*` | ✗ |
| `g` | `any` | let/var | `*not shown*` | ✗ |
| `h` | `any` | let/var | `*not shown*` | ✗ |
| `c` | `any` | let/var | `*not shown*` | ✗ |
| `a` | `any` | let/var | `*not shown*` | ✗ |
| `d` | `any` | let/var | `b[c]` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `a` | `any` | let/var | `*not shown*` | ✗ |
| `d` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `ctor(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ctor() {}
```
</details>

### `R(b: any): boolean | Date`

**Parameters:**

- **`b`** `any`

**Returns:** `boolean | Date`

**Calls:**

- `q.stringify`
- `q.parse`

<details><summary>Code</summary>

```typescript
function R(b){var c,a,d,j=b=="json";if(j||b=="json-stringify"||b=="json-parse"){if(b=="json-stringify"||j){if(c=typeof q.stringify=="function"&&J){(d=function(){return 1}).toJSON=d;try{c=q.stringify(0)==="0"&&q.stringify(new Number)==="0"&&q.stringify(new String)=='""'&&q.stringify(l)===e&&q.stringify(e)===e&&q.stringify()===e&&q.stringify(d)==="1"&&q.stringify([d])=="[1]"&&q.stringify([e])=="[null]"&&q.stringify(k)=="null"&&q.stringify([e,l,k])=="[null,null,null]"&&q.stringify({A:[d,i,false,k,"\x00\u0008\n\u000c\r\t"]})==
'{"A":[1,true,false,null,"\\u0000\\b\\n\\f\\r\\t"]}'&&q.stringify(k,d)==="1"&&q.stringify([1,2],k,1)=="[\n 1,\n 2\n]"&&q.stringify(new Date(-864E13))=='"-271821-04-20T00:00:00.000Z"'&&q.stringify(new Date(864E13))=='"+275760-09-13T00:00:00.000Z"'&&q.stringify(new Date(-621987552E5))=='"-000001-01-01T00:00:00.000Z"'&&q.stringify(new Date(-1))=='"1969-12-31T23:59:59.999Z"'}catch(f){c=false}}if(!j)return c}if(b=="json-parse"||j){if(typeof q.parse=="function")try{if(q.parse("0")===0&&!q.parse(false)){d=
q.parse('{"A":[1,true,false,null,"\\u0000\\b\\n\\f\\r\\t"]}');if(a=d.a.length==5&&d.a[0]==1){try{a=!q.parse('"\t"')}catch(o){}if(a)try{a=q.parse("01")!=1}catch(g){}}}}catch(h){a=false}if(!j)return a}return c&&a}}
```
</details>


---