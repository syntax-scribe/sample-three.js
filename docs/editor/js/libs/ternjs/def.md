[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `def.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 47 |
| 📊 Variables & Constants | 71 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/ternjs/def.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `TypeParser` | `typeof TypeParser` | let/var | `exports.TypeParser = function(spec, start, base, forceNew) { this.pos = start...` | ✗ |
| `rv` | `any` | let/var | `new infer.AVal` | ✗ |
| `realArgs` | `any[]` | let/var | `[]` | ✗ |
| `union` | `any` | let/var | `new infer.AVal` | ✗ |
| `word` | `string` | let/var | `""` | ✗ |
| `ch` | `any` | let/var | `*not shown*` | ✗ |
| `re` | `any` | let/var | `re \|\| /[\w$]/` | ✗ |
| `args` | `any[]` | let/var | `[]` | ✗ |
| `names` | `any[]` | let/var | `[]` | ✗ |
| `computed` | `boolean` | let/var | `false` | ✗ |
| `argname` | `any` | let/var | `*not shown*` | ✗ |
| `retType` | `any` | let/var | `*not shown*` | ✗ |
| `computeRet` | `any` | let/var | `*not shown*` | ✗ |
| `computeRetStart` | `any` | let/var | `*not shown*` | ✗ |
| `fn` | `any` | let/var | `*not shown*` | ✗ |
| `retStart` | `any` | let/var | `this.pos` | ✗ |
| `types` | `any[]` | let/var | `[main]` | ✗ |
| `computed` | `any` | let/var | `main.call` | ✗ |
| `union` | `any` | let/var | `new infer.AVal` | ✗ |
| `propName` | `any` | let/var | `this.word(/[\w<>$!]/) \|\| this.error()` | ✗ |
| `propName` | `string` | let/var | `"<i>"` | ✗ |
| `match` | `any` | let/var | `*not shown*` | ✗ |
| `arg` | `any` | let/var | `type.args[i]` | ✗ |
| `fArg` | `any` | let/var | `fArgs[i]` | ✗ |
| `oldCmp` | `any` | let/var | `fn.computeRet` | ✗ |
| `rv` | `any` | let/var | `fn.retval` | ✗ |
| `old` | `any` | let/var | `oldCmp ? oldCmp(self, args, argNodes) : rv` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `TypeParser` | let/var | `new TypeParser(effect, 10)` | ✗ |
| `andRet` | `boolean` | let/var | `effect.indexOf("and return ", 5) == 5` | ✗ |
| `getSelf` | `any` | let/var | `null` | ✗ |
| `getArgs` | `any[]` | let/var | `[]` | ✗ |
| `slf` | `any` | let/var | `getSelf ? unwrapType(getSelf, self, args) : infer.ANull` | ✗ |
| `as` | `any[]` | let/var | `[]` | ✗ |
| `result` | `any` | let/var | `andRet ? new infer.AVal : infer.ANull` | ✗ |
| `customFunc` | `any` | let/var | `customFunctions[m[1]]` | ✗ |
| `parseEffect` | `(effect: any, fn: any) => void` | let/var | `exports.parseEffect = function(effect, fn) { var m; if (effect.indexOf("propa...` | ✗ |
| `currentTopScope` | `any` | let/var | `*not shown*` | ✗ |
| `cached` | `any` | let/var | `cx.paths[path]` | ✗ |
| `origPath` | `any` | let/var | `path` | ✗ |
| `base` | `any` | let/var | `scope \|\| currentTopScope \|\| cx.topScope` | ✗ |
| `prop` | `any` | let/var | `parts[i]` | ✗ |
| `arg` | `any` | let/var | `fn.args && fn.args[Number(prop.slice(1))]` | ✗ |
| `propVal` | `any` | let/var | `(prop == "prototype" && base instanceof infer.Fn) ? base.getProp(prop) : base...` | ✗ |
| `parsePath` | `(path: any, scope: any) => any` | let/var | `exports.parsePath = function(path, scope) { var cx = infer.cx(), cached = cx....` | ✗ |
| `tp` | `any` | let/var | `spec["!type"]` | ✗ |
| `inner` | `any` | let/var | `spec[name]` | ✗ |
| `tp` | `any` | let/var | `spec["!type"]` | ✗ |
| `proto` | `any` | let/var | `spec["!proto"] && parseType(spec["!proto"])` | ✗ |
| `effects` | `any` | let/var | `spec["!effects"]` | ✗ |
| `inner` | `any` | let/var | `spec[name]` | ✗ |
| `innerPath` | `string` | let/var | `path ? path + "." + name : name` | ✗ |
| `parent` | `any` | let/var | `infer.cx().parent` | ✗ |
| `pass` | `any` | let/var | `parent && parent.passes && parent.passes[type]` | ✗ |
| `def` | `any` | let/var | `data["!define"]` | ✗ |
| `spec` | `any` | let/var | `def[name]` | ✗ |
| `oldScope` | `any` | let/var | `currentTopScope` | ✗ |
| `derived` | `any` | let/var | `new infer.Obj(tp)` | ✗ |
| `spec` | `any` | let/var | `this.spec` | ✗ |
| `cur` | `any` | let/var | `spec.props[prop].types[0]` | ✗ |
| `result` | `any` | let/var | `new infer.AVal` | ✗ |
| `obj` | `any` | let/var | `args[0]` | ✗ |
| `connect` | `any` | let/var | `new infer.AVal` | ✗ |
| `obj` | `any` | let/var | `args[0]` | ✗ |
| `connect` | `any` | let/var | `new infer.AVal` | ✗ |
| `result` | `any` | let/var | `new infer.AVal` | ✗ |
| `arr` | `any` | let/var | `new infer.Arr` | ✗ |
| `self` | `any` | let/var | `new infer.Obj(infer.cx().definitions.ecma6["Promise.prototype"])` | ✗ |
| `valArg` | `any` | let/var | `new infer.AVal` | ✗ |
| `exec` | `any` | let/var | `new infer.Fn("execute", infer.ANull, [valArg], ["value"], infer.ANull)` | ✗ |
| `reject` | `any` | let/var | `infer.cx().definitions.ecma6.promiseReject` | ✗ |


---

## Functions

### `hop(obj: any, prop: any): any`

**Parameters:**

- **`obj`** `any`
- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `Object.prototype.hasOwnProperty.call`

<details><summary>Code</summary>

```typescript
function hop(obj, prop) {
    return Object.prototype.hasOwnProperty.call(obj, prop);
  }
```
</details>

### `unwrapType(type: any, self: any, args: any): any`

**Parameters:**

- **`type`** `any`
- **`self`** `any`
- **`args`** `any`

**Returns:** `any`

**Calls:**

- `type`

<details><summary>Code</summary>

```typescript
function unwrapType(type, self, args) {
    return type.call ? type(self, args) : type;
  }
```
</details>

### `extractProp(type: any, prop: any): any`

**Parameters:**

- **`type`** `any`
- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `type.propagate`
- `type.getProp`

<details><summary>Code</summary>

```typescript
function extractProp(type, prop) {
    if (prop == "!ret") {
      if (type.retval) return type.retval;
      var rv = new infer.AVal;
      type.propagate(new infer.IsCallee(infer.ANull, [], null, rv));
      return rv;
    } else {
      return type.getProp(prop);
    }
  }
```
</details>

### `computedFunc(args: any, retType: any): (self: any, cArgs: any) => any`

**Parameters:**

- **`args`** `any`
- **`retType`** `any`

**Returns:** `(self: any, cArgs: any) => any`

**Calls:**

- `realArgs.push`
- `unwrapType`

<details><summary>Code</summary>

```typescript
function computedFunc(args, retType) {
    return function(self, cArgs) {
      var realArgs = [];
      for (var i = 0; i < args.length; i++) realArgs.push(unwrapType(args[i], self, cArgs));
      return new infer.Fn(name, infer.ANull, realArgs, unwrapType(retType, self, cArgs));
    };
  }
```
</details>

### `computedUnion(types: any): (self: any, args: any) => any`

**Parameters:**

- **`types`** `any`

**Returns:** `(self: any, args: any) => any`

**Calls:**

- `unwrapType(types[i], self, args).propagate`

<details><summary>Code</summary>

```typescript
function computedUnion(types) {
    return function(self, args) {
      var union = new infer.AVal;
      for (var i = 0; i < types.length; i++) unwrapType(types[i], self, args).propagate(union);
      return union;
    };
  }
```
</details>

### `computedArray(inner: any): (self: any, args: any) => any`

**Parameters:**

- **`inner`** `any`

**Returns:** `(self: any, args: any) => any`

**Calls:**

- `inner`

<details><summary>Code</summary>

```typescript
function computedArray(inner) {
    return function(self, args) {
      return new infer.Arr(inner(self, args));
    };
  }
```
</details>

### `eat(str: any): boolean`

**Parameters:**

- **`str`** `any`

**Returns:** `boolean`

**Calls:**

- `this.spec.charAt`
- `this.spec.indexOf`

<details><summary>Code</summary>

```typescript
function(str) {
      if (str.length == 1 ? this.spec.charAt(this.pos) == str : this.spec.indexOf(str, this.pos) == this.pos) {
        this.pos += str.length;
        return true;
      }
    }
```
</details>

### `word(re: any): string`

**Parameters:**

- **`re`** `any`

**Returns:** `string`

**Calls:**

- `this.spec.charAt`
- `re.test`

<details><summary>Code</summary>

```typescript
function(re) {
      var word = "", ch, re = re || /[\w$]/;
      while ((ch = this.spec.charAt(this.pos)) && re.test(ch)) { word += ch; ++this.pos; }
      return word;
    }
```
</details>

### `error(): never`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function() {
      throw new Error("Unrecognized type spec: " + this.spec + " (at " + this.pos + ")");
    }
```
</details>

### `parseFnType(comp: any, name: any, top: any): any`

**Parameters:**

- **`comp`** `any`
- **`name`** `any`
- **`top`** `any`

**Returns:** `any`

**Calls:**

- `this.eat`
- `this.spec.indexOf`
- `this.spec.slice`
- `/^[$\w?]+$/.test`
- `names.push`
- `this.parseType`
- `args.push`
- `this.error`
- `computedFunc`
- `infer.Fn.call`

<details><summary>Code</summary>

```typescript
function(comp, name, top) {
      var args = [], names = [], computed = false;
      if (!this.eat(")")) for (var i = 0; ; ++i) {
        var colon = this.spec.indexOf(": ", this.pos), argname;
        if (colon != -1) {
          argname = this.spec.slice(this.pos, colon);
          if (/^[$\w?]+$/.test(argname))
            this.pos = colon + 2;
          else
            argname = null;
        }
        names.push(argname);
        var argType = this.parseType(comp);
        if (argType.call) computed = true;
        args.push(argType);
        if (!this.eat(", ")) {
          this.eat(")") || this.error();
          break;
        }
      }
      var retType, computeRet, computeRetStart, fn;
      if (this.eat(" -> ")) {
        var retStart = this.pos;
        retType = this.parseType(true);
        if (retType.call) {
          if (top) {
            computeRet = retType;
            retType = infer.ANull;
            computeRetStart = retStart;
          } else {
            computed = true;
          }
        }
      } else {
        retType = infer.ANull;
      }
      if (computed) return computedFunc(args, retType);

      if (top && (fn = this.base))
        infer.Fn.call(this.base, name, infer.ANull, args, names, retType);
      else
        fn = new infer.Fn(name, infer.ANull, args, names, retType);
      if (computeRet) fn.computeRet = computeRet;
      if (computeRetStart != null) fn.computeRetSource = this.spec.slice(computeRetStart, this.pos);
      return fn;
    }
```
</details>

### `parseType(comp: any, name: any, top: any): any`

**Parameters:**

- **`comp`** `any`
- **`name`** `any`
- **`top`** `any`

**Returns:** `any`

**Calls:**

- `this.parseTypeMaybeProp`
- `this.eat`
- `types.push`
- `computedUnion`
- `types[i].propagate`

<details><summary>Code</summary>

```typescript
function(comp, name, top) {
      var main = this.parseTypeMaybeProp(comp, name, top);
      if (!this.eat("|")) return main;
      var types = [main], computed = main.call;
      for (;;) {
        var next = this.parseTypeMaybeProp(comp, name, top);
        types.push(next);
        if (next.call) computed = true;
        if (!this.eat("|")) break;
      }
      if (computed) return computedUnion(types);
      var union = new infer.AVal;
      for (var i = 0; i < types.length; i++) types[i].propagate(union);
      return union;
    }
```
</details>

### `parseTypeMaybeProp(comp: any, name: any, top: any): any`

**Parameters:**

- **`comp`** `any`
- **`name`** `any`
- **`top`** `any`

**Returns:** `any`

**Calls:**

- `this.parseTypeInner`
- `this.eat`
- `this.extendWithProp`

<details><summary>Code</summary>

```typescript
function(comp, name, top) {
      var result = this.parseTypeInner(comp, name, top);
      while (comp && this.eat(".")) result = this.extendWithProp(result);
      return result;
    }
```
</details>

### `extendWithProp(base: any): any`

**Parameters:**

- **`base`** `any`

**Returns:** `any`

**Calls:**

- `this.word`
- `this.error`
- `extractProp`
- `base`

<details><summary>Code</summary>

```typescript
function(base) {
      var propName = this.word(/[\w<>$!]/) || this.error();
      if (base.apply) return function(self, args) {
        return extractProp(base(self, args), propName);
      };
      return extractProp(base, propName);
    }
```
</details>

### `parseTypeInner(comp: any, name: any, top: any): any`

**Parameters:**

- **`comp`** `any`
- **`name`** `any`
- **`top`** `any`

**Returns:** `any`

**Calls:**

- `this.eat`
- `this.parseFnType`
- `this.parseType`
- `this.error`
- `computedArray`
- `infer.Arr.call`
- `this.word`
- `parsePath`
- `this.parsePoly`
- `infer.getInstance`
- `Number`
- `this.fromWord`

<details><summary>Code</summary>

```typescript
function(comp, name, top) {
      if (this.eat("fn(")) {
        return this.parseFnType(comp, name, top);
      } else if (this.eat("[")) {
        var inner = this.parseType(comp);
        this.eat("]") || this.error();
        if (inner.call) return computedArray(inner);
        if (top && this.base) {
          infer.Arr.call(this.base, inner);
          return this.base;
        }
        return new infer.Arr(inner);
      } else if (this.eat("+")) {
        var path = this.word(/[\w$<>\.!]/);
        var base = parsePath(path + ".prototype");
        if (!(base instanceof infer.Obj)) base = parsePath(path);
        if (!(base instanceof infer.Obj)) return base;
        if (comp && this.eat("[")) return this.parsePoly(base);
        if (top && this.forceNew) return new infer.Obj(base);
        return infer.getInstance(base);
      } else if (comp && this.eat("!")) {
        var arg = this.word(/\d/);
        if (arg) {
          arg = Number(arg);
          return function(_self, args) {return args[arg] || infer.ANull;};
        } else if (this.eat("this")) {
          return function(self) {return self;};
        } else if (this.eat("custom:")) {
          var fname = this.word(/[\w$]/);
          return customFunctions[fname] || function() { return infer.ANull; };
        } else {
          return this.fromWord("!" + this.word(/[\w$<>\.!]/));
        }
      } else if (this.eat("?")) {
        return infer.ANull;
      } else {
        return this.fromWord(this.word(/[\w$<>\.!`]/));
      }
    }
```
</details>

### `fromWord(spec: any): any`

**Parameters:**

- **`spec`** `any`

**Returns:** `any`

**Calls:**

- `infer.cx`
- `parsePath`

<details><summary>Code</summary>

```typescript
function(spec) {
      var cx = infer.cx();
      switch (spec) {
      case "number": return cx.num;
      case "string": return cx.str;
      case "bool": return cx.bool;
      case "<top>": return cx.topScope;
      }
      if (cx.localDefs && spec in cx.localDefs) return cx.localDefs[spec];
      return parsePath(spec);
    }
```
</details>

### `parsePoly(base: any): any`

**Parameters:**

- **`base`** `any`

**Returns:** `any`

**Calls:**

- `this.spec.slice(this.pos).match`
- `this.parseType`
- `this.eat`
- `this.error`
- `infer.getInstance`
- `value(self, args).propagate`
- `instance.defProp`
- `value.propagate`

<details><summary>Code</summary>

```typescript
function(base) {
      var propName = "<i>", match;
      if (match = this.spec.slice(this.pos).match(/^\s*(\w+)\s*=\s*/)) {
        propName = match[1];
        this.pos += match[0].length;
      }
      var value = this.parseType(true);
      if (!this.eat("]")) this.error();
      if (value.call) return function(self, args) {
        var instance = infer.getInstance(base);
        value(self, args).propagate(instance.defProp(propName));
        return instance;
      };
      var instance = infer.getInstance(base);
      value.propagate(instance.defProp(propName));
      return instance;
    }
```
</details>

### `eat(str: any): boolean`

**Parameters:**

- **`str`** `any`

**Returns:** `boolean`

**Calls:**

- `this.spec.charAt`
- `this.spec.indexOf`

<details><summary>Code</summary>

```typescript
function(str) {
      if (str.length == 1 ? this.spec.charAt(this.pos) == str : this.spec.indexOf(str, this.pos) == this.pos) {
        this.pos += str.length;
        return true;
      }
    }
```
</details>

### `word(re: any): string`

**Parameters:**

- **`re`** `any`

**Returns:** `string`

**Calls:**

- `this.spec.charAt`
- `re.test`

<details><summary>Code</summary>

```typescript
function(re) {
      var word = "", ch, re = re || /[\w$]/;
      while ((ch = this.spec.charAt(this.pos)) && re.test(ch)) { word += ch; ++this.pos; }
      return word;
    }
```
</details>

### `error(): never`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
function() {
      throw new Error("Unrecognized type spec: " + this.spec + " (at " + this.pos + ")");
    }
```
</details>

### `parseFnType(comp: any, name: any, top: any): any`

**Parameters:**

- **`comp`** `any`
- **`name`** `any`
- **`top`** `any`

**Returns:** `any`

**Calls:**

- `this.eat`
- `this.spec.indexOf`
- `this.spec.slice`
- `/^[$\w?]+$/.test`
- `names.push`
- `this.parseType`
- `args.push`
- `this.error`
- `computedFunc`
- `infer.Fn.call`

<details><summary>Code</summary>

```typescript
function(comp, name, top) {
      var args = [], names = [], computed = false;
      if (!this.eat(")")) for (var i = 0; ; ++i) {
        var colon = this.spec.indexOf(": ", this.pos), argname;
        if (colon != -1) {
          argname = this.spec.slice(this.pos, colon);
          if (/^[$\w?]+$/.test(argname))
            this.pos = colon + 2;
          else
            argname = null;
        }
        names.push(argname);
        var argType = this.parseType(comp);
        if (argType.call) computed = true;
        args.push(argType);
        if (!this.eat(", ")) {
          this.eat(")") || this.error();
          break;
        }
      }
      var retType, computeRet, computeRetStart, fn;
      if (this.eat(" -> ")) {
        var retStart = this.pos;
        retType = this.parseType(true);
        if (retType.call) {
          if (top) {
            computeRet = retType;
            retType = infer.ANull;
            computeRetStart = retStart;
          } else {
            computed = true;
          }
        }
      } else {
        retType = infer.ANull;
      }
      if (computed) return computedFunc(args, retType);

      if (top && (fn = this.base))
        infer.Fn.call(this.base, name, infer.ANull, args, names, retType);
      else
        fn = new infer.Fn(name, infer.ANull, args, names, retType);
      if (computeRet) fn.computeRet = computeRet;
      if (computeRetStart != null) fn.computeRetSource = this.spec.slice(computeRetStart, this.pos);
      return fn;
    }
```
</details>

### `parseType(comp: any, name: any, top: any): any`

**Parameters:**

- **`comp`** `any`
- **`name`** `any`
- **`top`** `any`

**Returns:** `any`

**Calls:**

- `this.parseTypeMaybeProp`
- `this.eat`
- `types.push`
- `computedUnion`
- `types[i].propagate`

<details><summary>Code</summary>

```typescript
function(comp, name, top) {
      var main = this.parseTypeMaybeProp(comp, name, top);
      if (!this.eat("|")) return main;
      var types = [main], computed = main.call;
      for (;;) {
        var next = this.parseTypeMaybeProp(comp, name, top);
        types.push(next);
        if (next.call) computed = true;
        if (!this.eat("|")) break;
      }
      if (computed) return computedUnion(types);
      var union = new infer.AVal;
      for (var i = 0; i < types.length; i++) types[i].propagate(union);
      return union;
    }
```
</details>

### `parseTypeMaybeProp(comp: any, name: any, top: any): any`

**Parameters:**

- **`comp`** `any`
- **`name`** `any`
- **`top`** `any`

**Returns:** `any`

**Calls:**

- `this.parseTypeInner`
- `this.eat`
- `this.extendWithProp`

<details><summary>Code</summary>

```typescript
function(comp, name, top) {
      var result = this.parseTypeInner(comp, name, top);
      while (comp && this.eat(".")) result = this.extendWithProp(result);
      return result;
    }
```
</details>

### `extendWithProp(base: any): any`

**Parameters:**

- **`base`** `any`

**Returns:** `any`

**Calls:**

- `this.word`
- `this.error`
- `extractProp`
- `base`

<details><summary>Code</summary>

```typescript
function(base) {
      var propName = this.word(/[\w<>$!]/) || this.error();
      if (base.apply) return function(self, args) {
        return extractProp(base(self, args), propName);
      };
      return extractProp(base, propName);
    }
```
</details>

### `parseTypeInner(comp: any, name: any, top: any): any`

**Parameters:**

- **`comp`** `any`
- **`name`** `any`
- **`top`** `any`

**Returns:** `any`

**Calls:**

- `this.eat`
- `this.parseFnType`
- `this.parseType`
- `this.error`
- `computedArray`
- `infer.Arr.call`
- `this.word`
- `parsePath`
- `this.parsePoly`
- `infer.getInstance`
- `Number`
- `this.fromWord`

<details><summary>Code</summary>

```typescript
function(comp, name, top) {
      if (this.eat("fn(")) {
        return this.parseFnType(comp, name, top);
      } else if (this.eat("[")) {
        var inner = this.parseType(comp);
        this.eat("]") || this.error();
        if (inner.call) return computedArray(inner);
        if (top && this.base) {
          infer.Arr.call(this.base, inner);
          return this.base;
        }
        return new infer.Arr(inner);
      } else if (this.eat("+")) {
        var path = this.word(/[\w$<>\.!]/);
        var base = parsePath(path + ".prototype");
        if (!(base instanceof infer.Obj)) base = parsePath(path);
        if (!(base instanceof infer.Obj)) return base;
        if (comp && this.eat("[")) return this.parsePoly(base);
        if (top && this.forceNew) return new infer.Obj(base);
        return infer.getInstance(base);
      } else if (comp && this.eat("!")) {
        var arg = this.word(/\d/);
        if (arg) {
          arg = Number(arg);
          return function(_self, args) {return args[arg] || infer.ANull;};
        } else if (this.eat("this")) {
          return function(self) {return self;};
        } else if (this.eat("custom:")) {
          var fname = this.word(/[\w$]/);
          return customFunctions[fname] || function() { return infer.ANull; };
        } else {
          return this.fromWord("!" + this.word(/[\w$<>\.!]/));
        }
      } else if (this.eat("?")) {
        return infer.ANull;
      } else {
        return this.fromWord(this.word(/[\w$<>\.!`]/));
      }
    }
```
</details>

### `fromWord(spec: any): any`

**Parameters:**

- **`spec`** `any`

**Returns:** `any`

**Calls:**

- `infer.cx`
- `parsePath`

<details><summary>Code</summary>

```typescript
function(spec) {
      var cx = infer.cx();
      switch (spec) {
      case "number": return cx.num;
      case "string": return cx.str;
      case "bool": return cx.bool;
      case "<top>": return cx.topScope;
      }
      if (cx.localDefs && spec in cx.localDefs) return cx.localDefs[spec];
      return parsePath(spec);
    }
```
</details>

### `parsePoly(base: any): any`

**Parameters:**

- **`base`** `any`

**Returns:** `any`

**Calls:**

- `this.spec.slice(this.pos).match`
- `this.parseType`
- `this.eat`
- `this.error`
- `infer.getInstance`
- `value(self, args).propagate`
- `instance.defProp`
- `value.propagate`

<details><summary>Code</summary>

```typescript
function(base) {
      var propName = "<i>", match;
      if (match = this.spec.slice(this.pos).match(/^\s*(\w+)\s*=\s*/)) {
        propName = match[1];
        this.pos += match[0].length;
      }
      var value = this.parseType(true);
      if (!this.eat("]")) this.error();
      if (value.call) return function(self, args) {
        var instance = infer.getInstance(base);
        value(self, args).propagate(instance.defProp(propName));
        return instance;
      };
      var instance = infer.getInstance(base);
      value.propagate(instance.defProp(propName));
      return instance;
    }
```
</details>

### `parseType(spec: any, name: any, base: any, forceNew: any): any`

**Parameters:**

- **`spec`** `any`
- **`name`** `any`
- **`base`** `any`
- **`forceNew`** `any`

**Returns:** `any`

**Calls:**

- `new TypeParser(spec, null, base, forceNew).parseType`
- `/^fn\(/.test`
- `complex_call_7690`
- `addEffect`
- `fArg.propagate`
- `infer.cx`

<details><summary>Code</summary>

```typescript
function parseType(spec, name, base, forceNew) {
    var type = new TypeParser(spec, null, base, forceNew).parseType(false, name, true);
    if (/^fn\(/.test(spec)) for (var i = 0; i < type.args.length; ++i) (function(i) {
      var arg = type.args[i];
      if (arg instanceof infer.Fn && arg.args && arg.args.length) addEffect(type, function(_self, fArgs) {
        var fArg = fArgs[i];
        if (fArg) fArg.propagate(new infer.IsCallee(infer.cx().topScope, arg.args, null, infer.ANull));
      });
    })(i);
    return type;
  }
```
</details>

### `addEffect(fn: any, handler: any, replaceRet: any): void`

**Parameters:**

- **`fn`** `any`
- **`handler`** `any`
- **`replaceRet`** `any`

**Returns:** `void`

**Calls:**

- `handler`
- `oldCmp`

<details><summary>Code</summary>

```typescript
function addEffect(fn, handler, replaceRet) {
    var oldCmp = fn.computeRet, rv = fn.retval;
    fn.computeRet = function(self, args, argNodes) {
      var handled = handler(self, args, argNodes);
      var old = oldCmp ? oldCmp(self, args, argNodes) : rv;
      return replaceRet ? handled : old;
    };
  }
```
</details>

### `emptyObj(ctor: any): any`

**Parameters:**

- **`ctor`** `any`

**Returns:** `any`

**Calls:**

- `Object.create`

<details><summary>Code</summary>

```typescript
function emptyObj(ctor) {
    var empty = Object.create(ctor.prototype);
    empty.props = Object.create(null);
    empty.isShell = true;
    return empty;
  }
```
</details>

### `isSimpleAnnotation(spec: any): boolean`

**Parameters:**

- **`spec`** `any`

**Returns:** `boolean`

**Calls:**

- `/^(fn\(|\[)/.test`

<details><summary>Code</summary>

```typescript
function isSimpleAnnotation(spec) {
    if (!spec["!type"] || /^(fn\(|\[)/.test(spec["!type"])) return false;
    for (var prop in spec)
      if (prop != "!type" && prop != "!doc" && prop != "!url" && prop != "!span" && prop != "!data")
        return false;
    return true;
  }
```
</details>

### `passOne(base: any, spec: any, path: any): any`

**Parameters:**

- **`base`** `any`
- **`spec`** `any`
- **`path`** `any`

**Returns:** `any`

**Calls:**

- `/^fn\(/.test`
- `emptyObj`
- `tp.charAt`
- `infer.cx`
- `hop`
- `name.charCodeAt`
- `isSimpleAnnotation`
- `base.defProp`
- `passOne(prop.getObjType(), inner, path ? path + "." + name : name).propagate`

<details><summary>Code</summary>

```typescript
function passOne(base, spec, path) {
    if (!base) {
      var tp = spec["!type"];
      if (tp) {
        if (/^fn\(/.test(tp)) base = emptyObj(infer.Fn);
        else if (tp.charAt(0) == "[") base = emptyObj(infer.Arr);
        else throw new Error("Invalid !type spec: " + tp);
      } else if (spec["!stdProto"]) {
        base = infer.cx().protos[spec["!stdProto"]];
      } else {
        base = emptyObj(infer.Obj);
      }
      base.name = path;
    }

    for (var name in spec) if (hop(spec, name) && name.charCodeAt(0) != 33) {
      var inner = spec[name];
      if (typeof inner == "string" || isSimpleAnnotation(inner)) continue;
      var prop = base.defProp(name);
      passOne(prop.getObjType(), inner, path ? path + "." + name : name).propagate(prop);
    }
    return base;
  }
```
</details>

### `passTwo(base: any, spec: any, path: any): any`

**Parameters:**

- **`base`** `any`
- **`spec`** `any`
- **`path`** `any`

**Returns:** `any`

**Calls:**

- `parseType`
- `infer.Obj.call`
- `parseEffect`
- `copyInfo`
- `hop`
- `name.charCodeAt`
- `base.defProp`
- `known.isEmpty`
- `parseType(inner, innerPath).propagate`
- `isSimpleAnnotation`
- `passTwo`
- `known.getObjType`
- `parseType(inner["!type"], innerPath, null, true).propagate`

<details><summary>Code</summary>

```typescript
function passTwo(base, spec, path) {
    if (base.isShell) {
      delete base.isShell;
      var tp = spec["!type"];
      if (tp) {
        parseType(tp, path, base);
      } else {
        var proto = spec["!proto"] && parseType(spec["!proto"]);
        infer.Obj.call(base, proto instanceof infer.Obj ? proto : true, path);
      }
    }

    var effects = spec["!effects"];
    if (effects && base instanceof infer.Fn) for (var i = 0; i < effects.length; ++i)
      parseEffect(effects[i], base);
    copyInfo(spec, base);

    for (var name in spec) if (hop(spec, name) && name.charCodeAt(0) != 33) {
      var inner = spec[name], known = base.defProp(name), innerPath = path ? path + "." + name : name;
      if (typeof inner == "string") {
        if (known.isEmpty()) parseType(inner, innerPath).propagate(known);
      } else {
        if (!isSimpleAnnotation(inner))
          passTwo(known.getObjType(), inner, innerPath);
        else if (known.isEmpty())
          parseType(inner["!type"], innerPath, null, true).propagate(known);
        else
          continue;
        if (inner["!doc"]) known.doc = inner["!doc"];
        if (inner["!url"]) known.url = inner["!url"];
        if (inner["!span"]) known.span = inner["!span"];
      }
    }
    return base;
  }
```
</details>

### `copyInfo(spec: any, type: any): void`

**Parameters:**

- **`spec`** `any`
- **`type`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function copyInfo(spec, type) {
    if (spec["!doc"]) type.doc = spec["!doc"];
    if (spec["!url"]) type.url = spec["!url"];
    if (spec["!span"]) type.span = spec["!span"];
    if (spec["!data"]) type.metaData = spec["!data"];
  }
```
</details>

### `runPasses(type: any, arg: any): void`

**Parameters:**

- **`type`** `any`
- **`arg`** `any`

**Returns:** `void`

**Calls:**

- `infer.cx`
- `complex_call_15060`

<details><summary>Code</summary>

```typescript
function runPasses(type, arg) {
    var parent = infer.cx().parent, pass = parent && parent.passes && parent.passes[type];
    if (pass) for (var i = 0; i < pass.length; i++) pass[i](arg);
  }
```
</details>

### `doLoadEnvironment(data: any, scope: any): void`

**Parameters:**

- **`data`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `infer.cx`
- `infer.addOrigin`
- `Object.create`
- `runPasses`
- `passOne`
- `parsePath`
- `passTwo`

<details><summary>Code</summary>

```typescript
function doLoadEnvironment(data, scope) {
    var cx = infer.cx();

    infer.addOrigin(cx.curOrigin = data["!name"] || "env#" + cx.origins.length);
    cx.localDefs = cx.definitions[cx.curOrigin] = Object.create(null);

    runPasses("preLoadDef", data);

    passOne(scope, data);

    var def = data["!define"];
    if (def) {
      for (var name in def) {
        var spec = def[name];
        cx.localDefs[name] = typeof spec == "string" ? parsePath(spec) : passOne(null, spec, name);
      }
      for (var name in def) {
        var spec = def[name];
        if (typeof spec != "string") passTwo(cx.localDefs[name], def[name], name);
      }
    }

    passTwo(scope, data);

    runPasses("postLoadDef", data);

    cx.curOrigin = cx.localDefs = null;
  }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `spec.getObjType`
- `derived.defProp`
- `cur.props.value.getType`
- `p.addType`
- `this.target.addType`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (tp instanceof infer.Obj && this.created++ < 5) {
        var derived = new infer.Obj(tp), spec = this.spec;
        if (spec instanceof infer.AVal) spec = spec.getObjType(false);
        if (spec instanceof infer.Obj) for (var prop in spec.props) {
          var cur = spec.props[prop].types[0];
          var p = derived.defProp(prop);
          if (cur && cur instanceof infer.Obj && cur.props.value) {
            var vtp = cur.props.value.getType(false);
            if (vtp) p.addType(vtp);
          }
        }
        this.target.addType(derived);
      }
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `spec.getObjType`
- `derived.defProp`
- `cur.props.value.getType`
- `p.addType`
- `this.target.addType`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (tp instanceof infer.Obj && this.created++ < 5) {
        var derived = new infer.Obj(tp), spec = this.spec;
        if (spec instanceof infer.AVal) spec = spec.getObjType(false);
        if (spec instanceof infer.Obj) for (var prop in spec.props) {
          var cur = spec.props[prop].types[0];
          var p = derived.defProp(prop);
          if (cur && cur instanceof infer.Obj && cur.props.value) {
            var vtp = cur.props.value.getType(false);
            if (vtp) p.addType(vtp);
          }
        }
        this.target.addType(derived);
      }
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `spec.getObjType`
- `derived.defProp`
- `cur.props.value.getType`
- `p.addType`
- `this.target.addType`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (tp instanceof infer.Obj && this.created++ < 5) {
        var derived = new infer.Obj(tp), spec = this.spec;
        if (spec instanceof infer.AVal) spec = spec.getObjType(false);
        if (spec instanceof infer.Obj) for (var prop in spec.props) {
          var cur = spec.props[prop].types[0];
          var p = derived.defProp(prop);
          if (cur && cur instanceof infer.Obj && cur.props.value) {
            var vtp = cur.props.value.getType(false);
            if (vtp) p.addType(vtp);
          }
        }
        this.target.addType(derived);
      }
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `spec.getObjType`
- `derived.defProp`
- `cur.props.value.getType`
- `p.addType`
- `this.target.addType`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (tp instanceof infer.Obj && this.created++ < 5) {
        var derived = new infer.Obj(tp), spec = this.spec;
        if (spec instanceof infer.AVal) spec = spec.getObjType(false);
        if (spec instanceof infer.Obj) for (var prop in spec.props) {
          var cur = spec.props[prop].types[0];
          var p = derived.defProp(prop);
          if (cur && cur instanceof infer.Obj && cur.props.value) {
            var vtp = cur.props.value.getType(false);
            if (vtp) p.addType(vtp);
          }
        }
        this.target.addType(derived);
      }
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `tp.hasProp`
- `tp.getProp("value").propagate`
- `tp.getProp("get").propagate`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (!(tp instanceof infer.Obj)) return;
      if (tp.hasProp("value"))
        tp.getProp("value").propagate(this.target);
      else if (tp.hasProp("get"))
        tp.getProp("get").propagate(new infer.IsCallee(infer.ANull, [], null, this.target));
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `tp.hasProp`
- `tp.getProp("value").propagate`
- `tp.getProp("get").propagate`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (!(tp instanceof infer.Obj)) return;
      if (tp.hasProp("value"))
        tp.getProp("value").propagate(this.target);
      else if (tp.hasProp("get"))
        tp.getProp("get").propagate(new infer.IsCallee(infer.ANull, [], null, this.target));
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `tp.hasProp`
- `tp.getProp("value").propagate`
- `tp.getProp("get").propagate`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (!(tp instanceof infer.Obj)) return;
      if (tp.hasProp("value"))
        tp.getProp("value").propagate(this.target);
      else if (tp.hasProp("get"))
        tp.getProp("get").propagate(new infer.IsCallee(infer.ANull, [], null, this.target));
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `tp.hasProp`
- `tp.getProp("value").propagate`
- `tp.getProp("get").propagate`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (!(tp instanceof infer.Obj)) return;
      if (tp.hasProp("value"))
        tp.getProp("value").propagate(this.target);
      else if (tp.hasProp("get"))
        tp.getProp("get").propagate(new infer.IsCallee(infer.ANull, [], null, this.target));
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `tp.args.slice`
- `tp.argNames.slice`
- `this.self.propagate`
- `Math.min`
- `this.args[i].propagate`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (!(tp instanceof infer.Fn)) return;
      this.target.addType(new infer.Fn(tp.name, infer.ANull, tp.args.slice(this.args.length),
                                       tp.argNames.slice(this.args.length), tp.retval));
      this.self.propagate(tp.self);
      for (var i = 0; i < Math.min(tp.args.length, this.args.length); ++i)
        this.args[i].propagate(tp.args[i]);
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `tp.args.slice`
- `tp.argNames.slice`
- `this.self.propagate`
- `Math.min`
- `this.args[i].propagate`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (!(tp instanceof infer.Fn)) return;
      this.target.addType(new infer.Fn(tp.name, infer.ANull, tp.args.slice(this.args.length),
                                       tp.argNames.slice(this.args.length), tp.retval));
      this.self.propagate(tp.self);
      for (var i = 0; i < Math.min(tp.args.length, this.args.length); ++i)
        this.args[i].propagate(tp.args[i]);
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `tp.args.slice`
- `tp.argNames.slice`
- `this.self.propagate`
- `Math.min`
- `this.args[i].propagate`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (!(tp instanceof infer.Fn)) return;
      this.target.addType(new infer.Fn(tp.name, infer.ANull, tp.args.slice(this.args.length),
                                       tp.argNames.slice(this.args.length), tp.retval));
      this.self.propagate(tp.self);
      for (var i = 0; i < Math.min(tp.args.length, this.args.length); ++i)
        this.args[i].propagate(tp.args[i]);
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `tp.args.slice`
- `tp.argNames.slice`
- `this.self.propagate`
- `Math.min`
- `this.args[i].propagate`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (!(tp instanceof infer.Fn)) return;
      this.target.addType(new infer.Fn(tp.name, infer.ANull, tp.args.slice(this.args.length),
                                       tp.argNames.slice(this.args.length), tp.retval));
      this.self.propagate(tp.self);
      for (var i = 0; i < Math.min(tp.args.length, this.args.length); ++i)
        this.args[i].propagate(tp.args[i]);
    }
```
</details>


---