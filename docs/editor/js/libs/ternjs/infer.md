[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `infer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 502 |
| 📊 Variables & Constants | 155 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/ternjs/infer.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `toString` | `(type: any, maxDepth: any, parent: an...` | let/var | `exports.toString = function(type, maxDepth, parent) { if (!type \|\| type == ...` | ✗ |
| `ANull` | `any` | let/var | `exports.ANull = signal.mixin({ addType: function() {}, propagate: function() ...` | ✗ |
| `WG_DEFAULT` | `number` | let/var | `100` | ✗ |
| `WG_NEW_INSTANCE` | `number` | let/var | `90` | ✗ |
| `WG_MADEUP_PROTO` | `number` | let/var | `10` | ✗ |
| `WG_MULTI_MEMBER` | `number` | let/var | `5` | ✗ |
| `WG_CATCH_ERROR` | `number` | let/var | `5` | ✗ |
| `WG_GLOBAL_THIS` | `number` | let/var | `90` | ✗ |
| `WG_SPECULATIVE_THIS` | `number` | let/var | `2` | ✗ |
| `AVal` | `typeof AVal` | let/var | `exports.AVal = function() { this.types = []; this.forward = null; this.maxWei...` | ✗ |
| `forward` | `any` | let/var | `this.forward` | ✗ |
| `types` | `any` | let/var | `this.types` | ✗ |
| `found` | `any` | let/var | `(this.props \|\| (this.props = Object.create(null)))[prop]` | ✗ |
| `seen` | `any` | let/var | `null` | ✗ |
| `type` | `any` | let/var | `this.types[i]` | ✗ |
| `val` | `any` | let/var | `this.propertyOf.props[prop]` | ✗ |
| `foundProp` | `any` | let/var | `null` | ✗ |
| `matches` | `any[]` | let/var | `[]` | ✗ |
| `obj` | `any` | let/var | `objs[i]` | ✗ |
| `propsA` | `number` | let/var | `0` | ✗ |
| `propsB` | `number` | let/var | `0` | ✗ |
| `same` | `number` | let/var | `0` | ✗ |
| `found` | `any[]` | let/var | `[]` | ✗ |
| `tp` | `any` | let/var | `types[i]` | ✗ |
| `simplifyTypes` | `(types: any) => any[]` | let/var | `exports.simplifyTypes = function(types) { var found = []; outer: for (var i =...` | ✗ |
| `arrays` | `number` | let/var | `0` | ✗ |
| `fns` | `number` | let/var | `0` | ✗ |
| `objs` | `number` | let/var | `0` | ✗ |
| `prim` | `any` | let/var | `null` | ✗ |
| `tp` | `any` | let/var | `types[i]` | ✗ |
| `kinds` | `number` | let/var | `(arrays && 1) + (fns && 1) + (objs && 1) + (prim && 1)` | ✗ |
| `maxScore` | `number` | let/var | `0` | ✗ |
| `maxTp` | `any` | let/var | `null` | ✗ |
| `score` | `number` | let/var | `0` | ✗ |
| `body` | `string` | let/var | `"this.init();"` | ✗ |
| `constraint` | `(props: any, methods: any) => any` | let/var | `exports.constraint = function(props, methods) { var body = "this.init();"; pr...` | ✗ |
| `PropHasSubset` | `any` | let/var | `exports.PropHasSubset = constraint("prop, type, originNode", { addType: funct...` | ✗ |
| `compute` | `any` | let/var | `fn.computeRet` | ✗ |
| `names` | `any[]` | let/var | `[]` | ✗ |
| `IsCallee` | `any` | let/var | `exports.IsCallee = constraint("self, args, argNodes, retval", { init: functio...` | ✗ |
| `callee` | `any` | let/var | `new IsCallee(obj, this.args, this.argNodes, this.retval)` | ✗ |
| `IsCtor` | `any` | let/var | `exports.IsCtor = constraint("target, noReuse", { addType: function(f, weight)...` | ✗ |
| `cur` | `any` | let/var | `obj.instances[i]` | ✗ |
| `instance` | `Obj` | let/var | `new Obj(obj, ctor && ctor.name)` | ✗ |
| `getInstance` | `(obj: any, ctor: any) => any` | let/var | `exports.getInstance = function(obj, ctor) { if (ctor === false) return new Ob...` | ✗ |
| `IsProto` | `any` | let/var | `exports.IsProto = constraint("ctor, target", { addType: function(o, _weight) ...` | ✗ |
| `adder` | `any` | let/var | `new SpeculativeThis(o, this.fn)` | ✗ |
| `IfObj` | `any` | let/var | `exports.IfObj = constraint("target", { addType: function(t, weight) { if (t i...` | ✗ |
| `Type` | `() => void` | let/var | `exports.Type = function() {}` | ✗ |
| `Prim` | `typeof Prim` | let/var | `exports.Prim = function(proto, name) { this.name = name; this.proto = proto; }` | ✗ |
| `Obj` | `typeof Obj` | let/var | `exports.Obj = function(proto, name) { if (!this.props) this.props = Object.cr...` | ✗ |
| `props` | `any[]` | let/var | `[]` | ✗ |
| `etc` | `boolean` | let/var | `false` | ✗ |
| `found` | `any` | let/var | `this.props[prop]` | ✗ |
| `av` | `any` | let/var | `this.maybeProps && this.maybeProps[prop]` | ✗ |
| `found` | `any` | let/var | `this.hasProp(prop, true) \|\| (this.maybeProps && this.maybeProps[prop])` | ✗ |
| `av` | `AVal` | let/var | `this.ensureMaybeProps()[prop] = new AVal` | ✗ |
| `h` | `any` | let/var | `this.onNewProp[i]` | ✗ |
| `maybe` | `any` | let/var | `this.maybeProps && this.maybeProps[prop]` | ✗ |
| `av` | `any` | let/var | `this.props[prop]` | ✗ |
| `Fn` | `typeof Fn` | let/var | `exports.Fn = function(name, self, args, argNames, retval) { Obj.call(this, cx...` | ✗ |
| `str` | `string` | let/var | `"fn("` | ✗ |
| `name` | `any` | let/var | `this.argNames[i]` | ✗ |
| `proto` | `Obj` | let/var | `new Obj(true, this.name && this.name + ".prototype")` | ✗ |
| `Arr` | `(contentType: any) => void` | let/var | `exports.Arr = function(contentType) { Obj.call(this, cx.protos.Array); var co...` | ✗ |
| `data` | `any` | let/var | `cx.props[prop] \|\| (cx.props[prop] = [])` | ✗ |
| `cx` | `any` | let/var | `null` | ✗ |
| `old` | `any` | let/var | `cx` | ✗ |
| `timeout` | `any` | let/var | `*not shown*` | ✗ |
| `end` | `any` | let/var | `+new Date + ms` | ✗ |
| `oldEnd` | `any` | let/var | `timeout` | ✗ |
| `baseMaxWorkDepth` | `number` | let/var | `20` | ✗ |
| `reduceMaxWorkDepth` | `number` | let/var | `0.0001` | ✗ |
| `list` | `any[]` | let/var | `[]` | ✗ |
| `depth` | `number` | let/var | `0` | ✗ |
| `add` | `(type: any, target: any, weight: any)...` | let/var | `cx.workList = function(type, target, weight) { if (depth < baseMaxWorkDepth -...` | ✗ |
| `Scope` | `typeof Scope` | let/var | `exports.Scope = function(prev) { Obj.call(this, prev \|\| true); this.prev = ...` | ✗ |
| `found` | `any` | let/var | `s.props[name]` | ✗ |
| `NotSmaller` | `{}` | let/var | `{}` | ✗ |
| `score` | `any` | let/var | `scope.fnType.instantiateScore` | ✗ |
| `fn` | `any` | let/var | `scope.fnType` | ✗ |
| `oldOrigin` | `any` | let/var | `cx.curOrigin` | ✗ |
| `scopeCopy` | `Scope` | let/var | `new Scope(scope.prev)` | ✗ |
| `argNames` | `any` | let/var | `fn.argNames.length != args.length ? fn.argNames.slice(0, args.length) : fn.ar...` | ✗ |
| `argset` | `AVal` | let/var | `scopeCopy.fnType.arguments = new AVal` | ✗ |
| `fn` | `any` | let/var | `scope.fnType` | ✗ |
| `target` | `any` | let/var | `fn.retval` | ✗ |
| `targetInner` | `any` | let/var | `*not shown*` | ✗ |
| `asArray` | `any` | let/var | `*not shown*` | ✗ |
| `newPath` | `any` | let/var | `path` | ✗ |
| `dest` | `any` | let/var | `*not shown*` | ✗ |
| `p` | `any` | let/var | `new def.TypeParser(foundPath)` | ✗ |
| `inner` | `Scope` | let/var | `node.body.scope = new Scope(scope)` | ✗ |
| `argVals` | `any[]` | let/var | `[]` | ✗ |
| `argNames` | `any[]` | let/var | `[]` | ✗ |
| `param` | `any` | let/var | `node.params[i]` | ✗ |
| `decl` | `boolean` | let/var | `node.type == "FunctionDeclaration"` | ✗ |
| `e5` | `any` | let/var | `cx.definitions.ecma5` | ✗ |
| `decl` | `any` | let/var | `node.declarations[i]` | ✗ |
| `prop` | `any` | let/var | `node.property` | ✗ |
| `eltval` | `AVal` | let/var | `new AVal` | ✗ |
| `elt` | `any` | let/var | `node.elements[i]` | ✗ |
| `obj` | `Obj` | let/var | `node.objType = new Obj(true, name)` | ✗ |
| `prop` | `any` | let/var | `node.properties[i]` | ✗ |
| `key` | `any` | let/var | `prop.key` | ✗ |
| `name` | `any` | let/var | `*not shown*` | ✗ |
| `out` | `any` | let/var | `val` | ✗ |
| `inner` | `any` | let/var | `node.body.scope` | ✗ |
| `fn` | `any` | let/var | `inner.fnType` | ✗ |
| `result` | `AVal` | let/var | `new AVal` | ✗ |
| `rhs` | `any` | let/var | `*not shown*` | ✗ |
| `name` | `any` | let/var | `*not shown*` | ✗ |
| `pName` | `any` | let/var | `*not shown*` | ✗ |
| `v` | `any` | let/var | `node.left.property.name` | ✗ |
| `local` | `any` | let/var | `scope.props[v]` | ✗ |
| `over` | `any` | let/var | `local && local.iteratesOver` | ✗ |
| `fromRight` | `boolean` | let/var | `node.right.type == "MemberExpression" && node.right.computed && node.right.pr...` | ✗ |
| `self` | `AVal` | let/var | `new AVal` | ✗ |
| `inferExprVisitor` | `{ ArrayExpression: (node: any, scope:...` | let/var | `{ ArrayExpression: ret(function(node, scope, c) { var eltval = new AVal; for ...` | ✗ |
| `inner` | `any` | let/var | `node.body.scope` | ✗ |
| `fn` | `any` | let/var | `inner.fnType` | ✗ |
| `decl` | `any` | let/var | `node.declarations[i]` | ✗ |
| `output` | `any` | let/var | `ANull` | ✗ |
| `varName` | `any` | let/var | `*not shown*` | ✗ |
| `arr` | `any` | let/var | `passes && passes[pass]` | ✗ |
| `ast` | `any` | let/var | `*not shown*` | ✗ |
| `parse` | `(text: any, passes: any, options: any...` | let/var | `exports.parse = function(text, passes, options) { var ast; try { ast = acorn....` | ✗ |
| `list` | `any` | let/var | `cx.props[prop]` | ✗ |
| `obj` | `any` | let/var | `list[i]` | ✗ |
| `av` | `any` | let/var | `obj.props[prop]` | ✗ |
| `type` | `any` | let/var | `this.types[i]` | ✗ |
| `f` | `any` | let/var | `this.forward[i]` | ✗ |
| `av` | `any` | let/var | `this.props[p]` | ✗ |
| `eltval` | `AVal` | let/var | `new AVal` | ✗ |
| `elt` | `any` | let/var | `node.elements[i]` | ✗ |
| `proto` | `any` | let/var | `f && f.getProp("prototype").getObjType()` | ✗ |
| `self` | `any` | let/var | `ANull` | ✗ |
| `typeFinder` | `{ ArrayExpression: (node: any, scope:...` | let/var | `{ ArrayExpression: function(node, scope) { var eltval = new AVal; for (var i ...` | ✗ |
| `scope` | `any` | let/var | `node.body.scope` | ✗ |
| `decl` | `any` | let/var | `node.declarations[i]` | ✗ |
| `searchVisitor` | `any` | let/var | `exports.searchVisitor = walk.make({ Function: function(node, _st, c) { var sc...` | ✗ |
| `test` | `any` | let/var | `filter \|\| function(_t, node) { if (node.type == "Identifier" && node.name =...` | ✗ |
| `test` | `any` | let/var | `filter \|\| function(_t, node) { if (start != null && node.start > start) ret...` | ✗ |
| `stack` | `any[]` | let/var | `[]` | ✗ |
| `top` | `any` | let/var | `stack[stack.length - 1]` | ✗ |
| `prop` | `any` | let/var | `node.properties[i]` | ✗ |
| `arg` | `any` | let/var | `parent.arguments[i]` | ✗ |
| `fnType` | `any` | let/var | `fnNode.node.type == "FunctionExpression" ? get(fnNode.node, true).getFunction...` | ✗ |
| `decl` | `any` | let/var | `parent.declarations[i]` | ✗ |
| `findTypeFromContext` | `{ ArrayExpression: (parent: any, _: a...` | let/var | `{ ArrayExpression: function(parent, _, get) { return get(parent, true).getPro...` | ✗ |
| `type` | `any` | let/var | `null` | ✗ |
| `obj` | `{ node: any; state: any; }` | let/var | `{node: node, state: found.state}` | ✗ |
| `tp` | `any` | let/var | `fromContext ? exports.typeFromContext(ast, obj) : exports.expressionType(obj)` | ✗ |
| `guessing` | `boolean` | let/var | `false` | ✗ |
| `scopeAt` | `(ast: any, pos: any, defaultScope: an...` | let/var | `exports.scopeAt = function(ast, pos, defaultScope) { var found = walk.findNod...` | ✗ |


---

## Functions

### `addType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propagate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getProp(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return ANull; }
```
</details>

### `forAllProps(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `hasType(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return false; }
```
</details>

### `isEmpty(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return true; }
```
</details>

### `getFunctionType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getObjType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `gatherProperties(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propagatesTo(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `typeHint(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propHint(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function() { return "?"; }
```
</details>

### `addType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propagate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getProp(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return ANull; }
```
</details>

### `forAllProps(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `hasType(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return false; }
```
</details>

### `isEmpty(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return true; }
```
</details>

### `getFunctionType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getObjType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `gatherProperties(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propagatesTo(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `typeHint(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propHint(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function() { return "?"; }
```
</details>

### `addType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propagate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getProp(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return ANull; }
```
</details>

### `forAllProps(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `hasType(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return false; }
```
</details>

### `isEmpty(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return true; }
```
</details>

### `getFunctionType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getObjType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `gatherProperties(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propagatesTo(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `typeHint(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propHint(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function() { return "?"; }
```
</details>

### `addType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propagate(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getProp(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return ANull; }
```
</details>

### `forAllProps(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `hasType(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return false; }
```
</details>

### `isEmpty(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return true; }
```
</details>

### `getFunctionType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getObjType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `getType(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `gatherProperties(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propagatesTo(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `typeHint(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `propHint(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() {}
```
</details>

### `toString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function() { return "?"; }
```
</details>

### `extend(proto: any, props: any): any`

**Parameters:**

- **`proto`** `any`
- **`props`** `any`

**Returns:** `any`

**Calls:**

- `Object.create`

<details><summary>Code</summary>

```typescript
function extend(proto, props) {
    var obj = Object.create(proto);
    if (props) for (var prop in props) obj[prop] = props[prop];
    return obj;
  }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.types.indexOf`
- `this.signal`
- `this.types.push`
- `withWorklist`
- `add`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      weight = weight || WG_DEFAULT;
      if (this.maxWeight < weight) {
        this.maxWeight = weight;
        if (this.types.length == 1 && this.types[0] == type) return;
        this.types.length = 0;
      } else if (this.maxWeight > weight || this.types.indexOf(type) > -1) {
        return;
      }

      this.signal("addType", type);
      this.types.push(type);
      var forward = this.forward;
      if (forward) withWorklist(function(add) {
        for (var i = 0; i < forward.length; ++i) add(type, forward[i], weight);
      });
    }
```
</details>

### `propagate(target: any, weight: any): void`

**Parameters:**

- **`target`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `(this.forward || (this.forward = [])).push`
- `withWorklist`
- `add`

<details><summary>Code</summary>

```typescript
function(target, weight) {
      if (target == ANull || (target instanceof Type && this.forward && this.forward.length > 2)) return;
      if (weight && weight != WG_DEFAULT) target = new Muffle(target, weight);
      (this.forward || (this.forward = [])).push(target);
      var types = this.types;
      if (types.length) withWorklist(function(add) {
        for (var i = 0; i < types.length; ++i) add(types[i], target, weight);
      });
    }
```
</details>

### `getProp(prop: any): any`

**Parameters:**

- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `Object.create`
- `this.propagate`

<details><summary>Code</summary>

```typescript
function(prop) {
      if (prop == "__proto__" || prop == "✖") return ANull;
      var found = (this.props || (this.props = Object.create(null)))[prop];
      if (!found) {
        found = this.props[prop] = new AVal;
        this.propagate(new PropIsSubset(prop, found));
      }
      return found;
    }
```
</details>

### `forAllProps(c: any): void`

**Parameters:**

- **`c`** `any`

**Returns:** `void`

**Calls:**

- `this.propagate`

<details><summary>Code</summary>

```typescript
function(c) {
      this.propagate(new ForAllProps(c));
    }
```
</details>

### `hasType(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `this.types.indexOf`

<details><summary>Code</summary>

```typescript
function(type) {
      return this.types.indexOf(type) > -1;
    }
```
</details>

### `isEmpty(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return this.types.length === 0; }
```
</details>

### `getFunctionType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
      for (var i = this.types.length - 1; i >= 0; --i)
        if (this.types[i] instanceof Fn) return this.types[i];
    }
```
</details>

### `getObjType(): Obj`

**Returns:** `Obj`

<details><summary>Code</summary>

```typescript
function() {
      var seen = null;
      for (var i = this.types.length - 1; i >= 0; --i) {
        var type = this.types[i];
        if (!(type instanceof Obj)) continue;
        if (type.name) return type;
        if (!seen) seen = type;
      }
      return seen;
    }
```
</details>

### `getType(guess: any): any`

**Parameters:**

- **`guess`** `any`

**Returns:** `any`

**Calls:**

- `this.makeupType`
- `canonicalType`

<details><summary>Code</summary>

```typescript
function(guess) {
      if (this.types.length === 0 && guess !== false) return this.makeupType();
      if (this.types.length === 1) return this.types[0];
      return canonicalType(this.types);
    }
```
</details>

### `toString(maxDepth: any, parent: any): any`

**Parameters:**

- **`maxDepth`** `any`
- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `toString`
- `this.makeupType`
- `simplifyTypes`
- `simplified.map(function(tp) { return toString(tp, maxDepth, parent); }).join`

<details><summary>Code</summary>

```typescript
function(maxDepth, parent) {
      if (this.types.length == 0) return toString(this.makeupType(), maxDepth, parent);
      if (this.types.length == 1) return toString(this.types[0], maxDepth, parent);
      var simplified = simplifyTypes(this.types);
      if (simplified.length > 2) return "?";
      return simplified.map(function(tp) { return toString(tp, maxDepth, parent); }).join("|");
    }
```
</details>

### `computedPropType(): any`

**Returns:** `any`

**Calls:**

- `this.propertyOf.hasProp`
- `this.propertyOf.getProp`
- `computedProp.getType`
- `val.isEmpty`

<details><summary>Code</summary>

```typescript
function() {
      if (!this.propertyOf) return null;
      if (this.propertyOf.hasProp("<i>")) {
        var computedProp = this.propertyOf.getProp("<i>");
        if (computedProp == this) return null;
        return computedProp.getType();
      } else if (this.propertyOf.maybeProps && this.propertyOf.maybeProps["<i>"] == this) {
        for (var prop in this.propertyOf.props) {
          var val = this.propertyOf.props[prop];
          if (!val.isEmpty()) return val;
        }
        return null;
      }
    }
```
</details>

### `makeupType(): any`

**Returns:** `any`

**Calls:**

- `this.computedPropType`
- `this.forward[i].typeHint`
- `hint.isEmpty`
- `Object.create`
- `this.forward[i].propHint`
- `objsWithProp`
- `obj.hasProp`
- `getInstance`
- `matches.push`
- `canonicalType`

<details><summary>Code</summary>

```typescript
function() {
      var computed = this.computedPropType();
      if (computed) return computed;

      if (!this.forward) return null;
      for (var i = this.forward.length - 1; i >= 0; --i) {
        var hint = this.forward[i].typeHint();
        if (hint && !hint.isEmpty()) {guessing = true; return hint;}
      }

      var props = Object.create(null), foundProp = null;
      for (var i = 0; i < this.forward.length; ++i) {
        var prop = this.forward[i].propHint();
        if (prop && prop != "length" && prop != "<i>" && prop != "✖" && prop != cx.completingProperty) {
          props[prop] = true;
          foundProp = prop;
        }
      }
      if (!foundProp) return null;

      var objs = objsWithProp(foundProp);
      if (objs) {
        var matches = [];
        search: for (var i = 0; i < objs.length; ++i) {
          var obj = objs[i];
          for (var prop in props) if (!obj.hasProp(prop)) continue search;
          if (obj.hasCtor) obj = getInstance(obj);
          matches.push(obj);
        }
        var canon = canonicalType(matches);
        if (canon) {guessing = true; return canon;}
      }
    }
```
</details>

### `typeHint(): any`

**Returns:** `any`

**Calls:**

- `this.getType`

<details><summary>Code</summary>

```typescript
function() { return this.types.length ? this.getType() : null; }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `gatherProperties(f: any, depth: any): void`

**Parameters:**

- **`f`** `any`
- **`depth`** `any`

**Returns:** `void`

**Calls:**

- `this.types[i].gatherProperties`

<details><summary>Code</summary>

```typescript
function(f, depth) {
      for (var i = 0; i < this.types.length; ++i)
        this.types[i].gatherProperties(f, depth);
    }
```
</details>

### `guessProperties(f: any): void`

**Parameters:**

- **`f`** `any`

**Returns:** `void`

**Calls:**

- `this.forward[i].propHint`
- `f`
- `this.makeupType`
- `guessed.gatherProperties`

<details><summary>Code</summary>

```typescript
function(f) {
      if (this.forward) for (var i = 0; i < this.forward.length; ++i) {
        var prop = this.forward[i].propHint();
        if (prop) f(prop, null, 0);
      }
      var guessed = this.makeupType();
      if (guessed) guessed.gatherProperties(f);
    }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.types.indexOf`
- `this.signal`
- `this.types.push`
- `withWorklist`
- `add`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      weight = weight || WG_DEFAULT;
      if (this.maxWeight < weight) {
        this.maxWeight = weight;
        if (this.types.length == 1 && this.types[0] == type) return;
        this.types.length = 0;
      } else if (this.maxWeight > weight || this.types.indexOf(type) > -1) {
        return;
      }

      this.signal("addType", type);
      this.types.push(type);
      var forward = this.forward;
      if (forward) withWorklist(function(add) {
        for (var i = 0; i < forward.length; ++i) add(type, forward[i], weight);
      });
    }
```
</details>

### `propagate(target: any, weight: any): void`

**Parameters:**

- **`target`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `(this.forward || (this.forward = [])).push`
- `withWorklist`
- `add`

<details><summary>Code</summary>

```typescript
function(target, weight) {
      if (target == ANull || (target instanceof Type && this.forward && this.forward.length > 2)) return;
      if (weight && weight != WG_DEFAULT) target = new Muffle(target, weight);
      (this.forward || (this.forward = [])).push(target);
      var types = this.types;
      if (types.length) withWorklist(function(add) {
        for (var i = 0; i < types.length; ++i) add(types[i], target, weight);
      });
    }
```
</details>

### `getProp(prop: any): any`

**Parameters:**

- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `Object.create`
- `this.propagate`

<details><summary>Code</summary>

```typescript
function(prop) {
      if (prop == "__proto__" || prop == "✖") return ANull;
      var found = (this.props || (this.props = Object.create(null)))[prop];
      if (!found) {
        found = this.props[prop] = new AVal;
        this.propagate(new PropIsSubset(prop, found));
      }
      return found;
    }
```
</details>

### `forAllProps(c: any): void`

**Parameters:**

- **`c`** `any`

**Returns:** `void`

**Calls:**

- `this.propagate`

<details><summary>Code</summary>

```typescript
function(c) {
      this.propagate(new ForAllProps(c));
    }
```
</details>

### `hasType(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `this.types.indexOf`

<details><summary>Code</summary>

```typescript
function(type) {
      return this.types.indexOf(type) > -1;
    }
```
</details>

### `isEmpty(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return this.types.length === 0; }
```
</details>

### `getFunctionType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
      for (var i = this.types.length - 1; i >= 0; --i)
        if (this.types[i] instanceof Fn) return this.types[i];
    }
```
</details>

### `getObjType(): Obj`

**Returns:** `Obj`

<details><summary>Code</summary>

```typescript
function() {
      var seen = null;
      for (var i = this.types.length - 1; i >= 0; --i) {
        var type = this.types[i];
        if (!(type instanceof Obj)) continue;
        if (type.name) return type;
        if (!seen) seen = type;
      }
      return seen;
    }
```
</details>

### `getType(guess: any): any`

**Parameters:**

- **`guess`** `any`

**Returns:** `any`

**Calls:**

- `this.makeupType`
- `canonicalType`

<details><summary>Code</summary>

```typescript
function(guess) {
      if (this.types.length === 0 && guess !== false) return this.makeupType();
      if (this.types.length === 1) return this.types[0];
      return canonicalType(this.types);
    }
```
</details>

### `toString(maxDepth: any, parent: any): any`

**Parameters:**

- **`maxDepth`** `any`
- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `toString`
- `this.makeupType`
- `simplifyTypes`
- `simplified.map(function(tp) { return toString(tp, maxDepth, parent); }).join`

<details><summary>Code</summary>

```typescript
function(maxDepth, parent) {
      if (this.types.length == 0) return toString(this.makeupType(), maxDepth, parent);
      if (this.types.length == 1) return toString(this.types[0], maxDepth, parent);
      var simplified = simplifyTypes(this.types);
      if (simplified.length > 2) return "?";
      return simplified.map(function(tp) { return toString(tp, maxDepth, parent); }).join("|");
    }
```
</details>

### `computedPropType(): any`

**Returns:** `any`

**Calls:**

- `this.propertyOf.hasProp`
- `this.propertyOf.getProp`
- `computedProp.getType`
- `val.isEmpty`

<details><summary>Code</summary>

```typescript
function() {
      if (!this.propertyOf) return null;
      if (this.propertyOf.hasProp("<i>")) {
        var computedProp = this.propertyOf.getProp("<i>");
        if (computedProp == this) return null;
        return computedProp.getType();
      } else if (this.propertyOf.maybeProps && this.propertyOf.maybeProps["<i>"] == this) {
        for (var prop in this.propertyOf.props) {
          var val = this.propertyOf.props[prop];
          if (!val.isEmpty()) return val;
        }
        return null;
      }
    }
```
</details>

### `makeupType(): any`

**Returns:** `any`

**Calls:**

- `this.computedPropType`
- `this.forward[i].typeHint`
- `hint.isEmpty`
- `Object.create`
- `this.forward[i].propHint`
- `objsWithProp`
- `obj.hasProp`
- `getInstance`
- `matches.push`
- `canonicalType`

<details><summary>Code</summary>

```typescript
function() {
      var computed = this.computedPropType();
      if (computed) return computed;

      if (!this.forward) return null;
      for (var i = this.forward.length - 1; i >= 0; --i) {
        var hint = this.forward[i].typeHint();
        if (hint && !hint.isEmpty()) {guessing = true; return hint;}
      }

      var props = Object.create(null), foundProp = null;
      for (var i = 0; i < this.forward.length; ++i) {
        var prop = this.forward[i].propHint();
        if (prop && prop != "length" && prop != "<i>" && prop != "✖" && prop != cx.completingProperty) {
          props[prop] = true;
          foundProp = prop;
        }
      }
      if (!foundProp) return null;

      var objs = objsWithProp(foundProp);
      if (objs) {
        var matches = [];
        search: for (var i = 0; i < objs.length; ++i) {
          var obj = objs[i];
          for (var prop in props) if (!obj.hasProp(prop)) continue search;
          if (obj.hasCtor) obj = getInstance(obj);
          matches.push(obj);
        }
        var canon = canonicalType(matches);
        if (canon) {guessing = true; return canon;}
      }
    }
```
</details>

### `typeHint(): any`

**Returns:** `any`

**Calls:**

- `this.getType`

<details><summary>Code</summary>

```typescript
function() { return this.types.length ? this.getType() : null; }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `gatherProperties(f: any, depth: any): void`

**Parameters:**

- **`f`** `any`
- **`depth`** `any`

**Returns:** `void`

**Calls:**

- `this.types[i].gatherProperties`

<details><summary>Code</summary>

```typescript
function(f, depth) {
      for (var i = 0; i < this.types.length; ++i)
        this.types[i].gatherProperties(f, depth);
    }
```
</details>

### `guessProperties(f: any): void`

**Parameters:**

- **`f`** `any`

**Returns:** `void`

**Calls:**

- `this.forward[i].propHint`
- `f`
- `this.makeupType`
- `guessed.gatherProperties`

<details><summary>Code</summary>

```typescript
function(f) {
      if (this.forward) for (var i = 0; i < this.forward.length; ++i) {
        var prop = this.forward[i].propHint();
        if (prop) f(prop, null, 0);
      }
      var guessed = this.makeupType();
      if (guessed) guessed.gatherProperties(f);
    }
```
</details>

### `similarAVal(a: any, b: any, depth: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`depth`** `any`

**Returns:** `any`

**Calls:**

- `a.getType`
- `b.getType`
- `similarType`

<details><summary>Code</summary>

```typescript
function similarAVal(a, b, depth) {
    var typeA = a.getType(false), typeB = b.getType(false);
    if (!typeA || !typeB) return true;
    return similarType(typeA, typeB, depth);
  }
```
</details>

### `similarType(a: any, b: any, depth: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`depth`** `any`

**Returns:** `any`

**Calls:**

- `a.getProp("<i>").getType`
- `b.getProp("<i>").getType`
- `similarType`
- `similarAVal`
- `Math.max`
- `a.args.every`

<details><summary>Code</summary>

```typescript
function similarType(a, b, depth) {
    if (!a || depth >= 5) return b;
    if (a == b) return a;
    if (!b) return a;
    if (a.constructor != b.constructor) return false;
    if (a.constructor == Arr) {
      var innerA = a.getProp("<i>").getType(false);
      if (!innerA) return b;
      var innerB = b.getProp("<i>").getType(false);
      if (!innerB || similarType(innerA, innerB, depth + 1)) return b;
    } else if (a.constructor == Obj) {
      var propsA = 0, propsB = 0, same = 0;
      for (var prop in a.props) {
        propsA++;
        if (prop in b.props && similarAVal(a.props[prop], b.props[prop], depth + 1))
          same++;
      }
      for (var prop in b.props) propsB++;
      if (propsA && propsB && same < Math.max(propsA, propsB) / 2) return false;
      return propsA > propsB ? a : b;
    } else if (a.constructor == Fn) {
      if (a.args.length != b.args.length ||
          !a.args.every(function(tp, i) { return similarAVal(tp, b.args[i], depth + 1); }) ||
          !similarAVal(a.retval, b.retval, depth + 1) || !similarAVal(a.self, b.self, depth + 1))
        return false;
      return a;
    } else {
      return false;
    }
  }
```
</details>

### `canonicalType(types: any): any`

**Parameters:**

- **`types`** `any`

**Returns:** `any`

**Calls:**

- `tp.getProp("<i>").isEmpty`
- `tp.args[j].isEmpty`
- `tp.retval.isEmpty`

<details><summary>Code</summary>

```typescript
function canonicalType(types) {
    var arrays = 0, fns = 0, objs = 0, prim = null;
    for (var i = 0; i < types.length; ++i) {
      var tp = types[i];
      if (tp instanceof Arr) ++arrays;
      else if (tp instanceof Fn) ++fns;
      else if (tp instanceof Obj) ++objs;
      else if (tp instanceof Prim) {
        if (prim && tp.name != prim.name) return null;
        prim = tp;
      }
    }
    var kinds = (arrays && 1) + (fns && 1) + (objs && 1) + (prim && 1);
    if (kinds > 1) return null;
    if (prim) return prim;

    var maxScore = 0, maxTp = null;
    for (var i = 0; i < types.length; ++i) {
      var tp = types[i], score = 0;
      if (arrays) {
        score = tp.getProp("<i>").isEmpty() ? 1 : 2;
      } else if (fns) {
        score = 1;
        for (var j = 0; j < tp.args.length; ++j) if (!tp.args[j].isEmpty()) ++score;
        if (!tp.retval.isEmpty()) ++score;
      } else if (objs) {
        score = tp.name ? 100 : 2;
      }
      if (score >= maxScore) { maxScore = score; maxTp = tp; }
    }
    return maxTp;
  }
```
</details>

### `Constraint(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Constraint() {}
```
</details>

### `init(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { this.origin = cx.curOrigin; }
```
</details>

### `init(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { this.origin = cx.curOrigin; }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `type.getProp(this.prop).propagate`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (type.getProp)
        type.getProp(this.prop).propagate(this.target, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.prop; }
```
</details>

### `propagatesTo(): { target: any; pathExt: string; }`

**Returns:** `{ target: any; pathExt: string; }`

**Calls:**

- `/[^\w_]/.test`

<details><summary>Code</summary>

```typescript
function() {
      if (this.prop == "<i>" || !/[^\w_]/.test(this.prop))
        return {target: this.target, pathExt: "." + this.prop};
    }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `type.getProp(this.prop).propagate`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (type.getProp)
        type.getProp(this.prop).propagate(this.target, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.prop; }
```
</details>

### `propagatesTo(): { target: any; pathExt: string; }`

**Returns:** `{ target: any; pathExt: string; }`

**Calls:**

- `/[^\w_]/.test`

<details><summary>Code</summary>

```typescript
function() {
      if (this.prop == "<i>" || !/[^\w_]/.test(this.prop))
        return {target: this.target, pathExt: "." + this.prop};
    }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `type.getProp(this.prop).propagate`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (type.getProp)
        type.getProp(this.prop).propagate(this.target, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.prop; }
```
</details>

### `propagatesTo(): { target: any; pathExt: string; }`

**Returns:** `{ target: any; pathExt: string; }`

**Calls:**

- `/[^\w_]/.test`

<details><summary>Code</summary>

```typescript
function() {
      if (this.prop == "<i>" || !/[^\w_]/.test(this.prop))
        return {target: this.target, pathExt: "." + this.prop};
    }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `type.getProp(this.prop).propagate`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (type.getProp)
        type.getProp(this.prop).propagate(this.target, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.prop; }
```
</details>

### `propagatesTo(): { target: any; pathExt: string; }`

**Returns:** `{ target: any; pathExt: string; }`

**Calls:**

- `/[^\w_]/.test`

<details><summary>Code</summary>

```typescript
function() {
      if (this.prop == "<i>" || !/[^\w_]/.test(this.prop))
        return {target: this.target, pathExt: "." + this.prop};
    }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `type.defProp`
- `this.type.propagate`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (!(type instanceof Obj)) return;
      var prop = type.defProp(this.prop, this.originNode);
      if (!prop.origin) prop.origin = this.origin;
      this.type.propagate(prop, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.prop; }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `type.defProp`
- `this.type.propagate`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (!(type instanceof Obj)) return;
      var prop = type.defProp(this.prop, this.originNode);
      if (!prop.origin) prop.origin = this.origin;
      this.type.propagate(prop, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.prop; }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `type.defProp`
- `this.type.propagate`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (!(type instanceof Obj)) return;
      var prop = type.defProp(this.prop, this.originNode);
      if (!prop.origin) prop.origin = this.origin;
      this.type.propagate(prop, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.prop; }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `type.defProp`
- `this.type.propagate`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (!(type instanceof Obj)) return;
      var prop = type.defProp(this.prop, this.originNode);
      if (!prop.origin) prop.origin = this.origin;
      this.type.propagate(prop, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.prop; }
```
</details>

### `addType(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

**Calls:**

- `type.forAllProps`

<details><summary>Code</summary>

```typescript
function(type) {
      if (!(type instanceof Obj)) return;
      type.forAllProps(this.c);
    }
```
</details>

### `addType(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

**Calls:**

- `type.forAllProps`

<details><summary>Code</summary>

```typescript
function(type) {
      if (!(type instanceof Obj)) return;
      type.forAllProps(this.c);
    }
```
</details>

### `addType(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

**Calls:**

- `type.forAllProps`

<details><summary>Code</summary>

```typescript
function(type) {
      if (!(type instanceof Obj)) return;
      type.forAllProps(this.c);
    }
```
</details>

### `addType(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

**Calls:**

- `type.forAllProps`

<details><summary>Code</summary>

```typescript
function(type) {
      if (!(type instanceof Obj)) return;
      type.forAllProps(this.c);
    }
```
</details>

### `withDisabledComputing(fn: any, body: any): any`

**Parameters:**

- **`fn`** `any`
- **`body`** `any`

**Returns:** `any`

**Calls:**

- `body`

<details><summary>Code</summary>

```typescript
function withDisabledComputing(fn, body) {
    cx.disabledComputing = {fn: fn, prev: cx.disabledComputing};
    try {
      return body();
    } finally {
      cx.disabledComputing = cx.disabledComputing.prev;
    }
  }
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `Constraint.prototype.init.call`

<details><summary>Code</summary>

```typescript
function() {
      Constraint.prototype.init.call(this);
      this.disabled = cx.disabledComputing;
    }
```
</details>

### `addType(fn: any, weight: any): void`

**Parameters:**

- **`fn`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.args[i].propagate`
- `this.self.propagate`
- `compute(this.self, this.args, this.argNodes).propagate`
- `fn.retval.propagate`

<details><summary>Code</summary>

```typescript
function(fn, weight) {
      if (!(fn instanceof Fn)) return;
      for (var i = 0; i < this.args.length; ++i) {
        if (i < fn.args.length) this.args[i].propagate(fn.args[i], weight);
        if (fn.arguments) this.args[i].propagate(fn.arguments, weight);
      }
      this.self.propagate(fn.self, this.self == cx.topScope ? WG_GLOBAL_THIS : weight);
      var compute = fn.computeRet;
      if (compute) for (var d = this.disabled; d; d = d.prev)
        if (d.fn == fn || fn.originNode && d.fn.originNode == fn.originNode) compute = null;
      if (compute)
        compute(this.self, this.args, this.argNodes).propagate(this.retval, weight);
      else
        fn.retval.propagate(this.retval, weight);
    }
```
</details>

### `typeHint(): Fn`

**Returns:** `Fn`

**Calls:**

- `names.push`

<details><summary>Code</summary>

```typescript
function() {
      var names = [];
      for (var i = 0; i < this.args.length; ++i) names.push("?");
      return new Fn(null, this.self, this.args, names, ANull);
    }
```
</details>

### `propagatesTo(): { target: any; pathExt: string; }`

**Returns:** `{ target: any; pathExt: string; }`

<details><summary>Code</summary>

```typescript
function() {
      return {target: this.retval, pathExt: ".!ret"};
    }
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `Constraint.prototype.init.call`

<details><summary>Code</summary>

```typescript
function() {
      Constraint.prototype.init.call(this);
      this.disabled = cx.disabledComputing;
    }
```
</details>

### `addType(fn: any, weight: any): void`

**Parameters:**

- **`fn`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.args[i].propagate`
- `this.self.propagate`
- `compute(this.self, this.args, this.argNodes).propagate`
- `fn.retval.propagate`

<details><summary>Code</summary>

```typescript
function(fn, weight) {
      if (!(fn instanceof Fn)) return;
      for (var i = 0; i < this.args.length; ++i) {
        if (i < fn.args.length) this.args[i].propagate(fn.args[i], weight);
        if (fn.arguments) this.args[i].propagate(fn.arguments, weight);
      }
      this.self.propagate(fn.self, this.self == cx.topScope ? WG_GLOBAL_THIS : weight);
      var compute = fn.computeRet;
      if (compute) for (var d = this.disabled; d; d = d.prev)
        if (d.fn == fn || fn.originNode && d.fn.originNode == fn.originNode) compute = null;
      if (compute)
        compute(this.self, this.args, this.argNodes).propagate(this.retval, weight);
      else
        fn.retval.propagate(this.retval, weight);
    }
```
</details>

### `typeHint(): Fn`

**Returns:** `Fn`

**Calls:**

- `names.push`

<details><summary>Code</summary>

```typescript
function() {
      var names = [];
      for (var i = 0; i < this.args.length; ++i) names.push("?");
      return new Fn(null, this.self, this.args, names, ANull);
    }
```
</details>

### `propagatesTo(): { target: any; pathExt: string; }`

**Returns:** `{ target: any; pathExt: string; }`

<details><summary>Code</summary>

```typescript
function() {
      return {target: this.retval, pathExt: ".!ret"};
    }
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `Constraint.prototype.init.call`

<details><summary>Code</summary>

```typescript
function() {
      Constraint.prototype.init.call(this);
      this.disabled = cx.disabledComputing;
    }
```
</details>

### `addType(fn: any, weight: any): void`

**Parameters:**

- **`fn`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.args[i].propagate`
- `this.self.propagate`
- `compute(this.self, this.args, this.argNodes).propagate`
- `fn.retval.propagate`

<details><summary>Code</summary>

```typescript
function(fn, weight) {
      if (!(fn instanceof Fn)) return;
      for (var i = 0; i < this.args.length; ++i) {
        if (i < fn.args.length) this.args[i].propagate(fn.args[i], weight);
        if (fn.arguments) this.args[i].propagate(fn.arguments, weight);
      }
      this.self.propagate(fn.self, this.self == cx.topScope ? WG_GLOBAL_THIS : weight);
      var compute = fn.computeRet;
      if (compute) for (var d = this.disabled; d; d = d.prev)
        if (d.fn == fn || fn.originNode && d.fn.originNode == fn.originNode) compute = null;
      if (compute)
        compute(this.self, this.args, this.argNodes).propagate(this.retval, weight);
      else
        fn.retval.propagate(this.retval, weight);
    }
```
</details>

### `typeHint(): Fn`

**Returns:** `Fn`

**Calls:**

- `names.push`

<details><summary>Code</summary>

```typescript
function() {
      var names = [];
      for (var i = 0; i < this.args.length; ++i) names.push("?");
      return new Fn(null, this.self, this.args, names, ANull);
    }
```
</details>

### `propagatesTo(): { target: any; pathExt: string; }`

**Returns:** `{ target: any; pathExt: string; }`

<details><summary>Code</summary>

```typescript
function() {
      return {target: this.retval, pathExt: ".!ret"};
    }
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `Constraint.prototype.init.call`

<details><summary>Code</summary>

```typescript
function() {
      Constraint.prototype.init.call(this);
      this.disabled = cx.disabledComputing;
    }
```
</details>

### `addType(fn: any, weight: any): void`

**Parameters:**

- **`fn`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.args[i].propagate`
- `this.self.propagate`
- `compute(this.self, this.args, this.argNodes).propagate`
- `fn.retval.propagate`

<details><summary>Code</summary>

```typescript
function(fn, weight) {
      if (!(fn instanceof Fn)) return;
      for (var i = 0; i < this.args.length; ++i) {
        if (i < fn.args.length) this.args[i].propagate(fn.args[i], weight);
        if (fn.arguments) this.args[i].propagate(fn.arguments, weight);
      }
      this.self.propagate(fn.self, this.self == cx.topScope ? WG_GLOBAL_THIS : weight);
      var compute = fn.computeRet;
      if (compute) for (var d = this.disabled; d; d = d.prev)
        if (d.fn == fn || fn.originNode && d.fn.originNode == fn.originNode) compute = null;
      if (compute)
        compute(this.self, this.args, this.argNodes).propagate(this.retval, weight);
      else
        fn.retval.propagate(this.retval, weight);
    }
```
</details>

### `typeHint(): Fn`

**Returns:** `Fn`

**Calls:**

- `names.push`

<details><summary>Code</summary>

```typescript
function() {
      var names = [];
      for (var i = 0; i < this.args.length; ++i) names.push("?");
      return new Fn(null, this.self, this.args, names, ANull);
    }
```
</details>

### `propagatesTo(): { target: any; pathExt: string; }`

**Returns:** `{ target: any; pathExt: string; }`

<details><summary>Code</summary>

```typescript
function() {
      return {target: this.retval, pathExt: ".!ret"};
    }
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `Constraint.prototype.init.call`

<details><summary>Code</summary>

```typescript
function() {
      Constraint.prototype.init.call(this);
      this.disabled = cx.disabledComputing;
    }
```
</details>

### `addType(obj: any, weight: any): void`

**Parameters:**

- **`obj`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `obj.getProp(this.propName).propagate`

<details><summary>Code</summary>

```typescript
function(obj, weight) {
      var callee = new IsCallee(obj, this.args, this.argNodes, this.retval);
      callee.disabled = this.disabled;
      obj.getProp(this.propName).propagate(callee, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.propName; }
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `Constraint.prototype.init.call`

<details><summary>Code</summary>

```typescript
function() {
      Constraint.prototype.init.call(this);
      this.disabled = cx.disabledComputing;
    }
```
</details>

### `addType(obj: any, weight: any): void`

**Parameters:**

- **`obj`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `obj.getProp(this.propName).propagate`

<details><summary>Code</summary>

```typescript
function(obj, weight) {
      var callee = new IsCallee(obj, this.args, this.argNodes, this.retval);
      callee.disabled = this.disabled;
      obj.getProp(this.propName).propagate(callee, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.propName; }
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `Constraint.prototype.init.call`

<details><summary>Code</summary>

```typescript
function() {
      Constraint.prototype.init.call(this);
      this.disabled = cx.disabledComputing;
    }
```
</details>

### `addType(obj: any, weight: any): void`

**Parameters:**

- **`obj`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `obj.getProp(this.propName).propagate`

<details><summary>Code</summary>

```typescript
function(obj, weight) {
      var callee = new IsCallee(obj, this.args, this.argNodes, this.retval);
      callee.disabled = this.disabled;
      obj.getProp(this.propName).propagate(callee, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.propName; }
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `Constraint.prototype.init.call`

<details><summary>Code</summary>

```typescript
function() {
      Constraint.prototype.init.call(this);
      this.disabled = cx.disabledComputing;
    }
```
</details>

### `addType(obj: any, weight: any): void`

**Parameters:**

- **`obj`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `obj.getProp(this.propName).propagate`

<details><summary>Code</summary>

```typescript
function(obj, weight) {
      var callee = new IsCallee(obj, this.args, this.argNodes, this.retval);
      callee.disabled = this.disabled;
      obj.getProp(this.propName).propagate(callee, weight);
    }
```
</details>

### `propHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.propName; }
```
</details>

### `addType(f: any, weight: any): void`

**Parameters:**

- **`f`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `f.getProp("prototype").propagate`

<details><summary>Code</summary>

```typescript
function(f, weight) {
      if (!(f instanceof Fn)) return;
      if (cx.parent && !cx.parent.options.reuseInstances) this.noReuse = true;
      f.getProp("prototype").propagate(new IsProto(this.noReuse ? false : f, this.target), weight);
    }
```
</details>

### `addType(f: any, weight: any): void`

**Parameters:**

- **`f`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `f.getProp("prototype").propagate`

<details><summary>Code</summary>

```typescript
function(f, weight) {
      if (!(f instanceof Fn)) return;
      if (cx.parent && !cx.parent.options.reuseInstances) this.noReuse = true;
      f.getProp("prototype").propagate(new IsProto(this.noReuse ? false : f, this.target), weight);
    }
```
</details>

### `addType(f: any, weight: any): void`

**Parameters:**

- **`f`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `f.getProp("prototype").propagate`

<details><summary>Code</summary>

```typescript
function(f, weight) {
      if (!(f instanceof Fn)) return;
      if (cx.parent && !cx.parent.options.reuseInstances) this.noReuse = true;
      f.getProp("prototype").propagate(new IsProto(this.noReuse ? false : f, this.target), weight);
    }
```
</details>

### `addType(f: any, weight: any): void`

**Parameters:**

- **`f`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `f.getProp("prototype").propagate`

<details><summary>Code</summary>

```typescript
function(f, weight) {
      if (!(f instanceof Fn)) return;
      if (cx.parent && !cx.parent.options.reuseInstances) this.noReuse = true;
      f.getProp("prototype").propagate(new IsProto(this.noReuse ? false : f, this.target), weight);
    }
```
</details>

### `addType(o: any, _weight: any): void`

**Parameters:**

- **`o`** `any`
- **`_weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(o, _weight) {
      if (!(o instanceof Obj)) return;
      if ((this.count = (this.count || 0) + 1) > 8) return;
      if (o == cx.protos.Array)
        this.target.addType(new Arr);
      else
        this.target.addType(getInstance(o, this.ctor));
    }
```
</details>

### `addType(o: any, _weight: any): void`

**Parameters:**

- **`o`** `any`
- **`_weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(o, _weight) {
      if (!(o instanceof Obj)) return;
      if ((this.count = (this.count || 0) + 1) > 8) return;
      if (o == cx.protos.Array)
        this.target.addType(new Arr);
      else
        this.target.addType(getInstance(o, this.ctor));
    }
```
</details>

### `addType(o: any, _weight: any): void`

**Parameters:**

- **`o`** `any`
- **`_weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(o, _weight) {
      if (!(o instanceof Obj)) return;
      if ((this.count = (this.count || 0) + 1) > 8) return;
      if (o == cx.protos.Array)
        this.target.addType(new Arr);
      else
        this.target.addType(getInstance(o, this.ctor));
    }
```
</details>

### `addType(o: any, _weight: any): void`

**Parameters:**

- **`o`** `any`
- **`_weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(o, _weight) {
      if (!(o instanceof Obj)) return;
      if ((this.count = (this.count || 0) + 1) > 8) return;
      if (o == cx.protos.Array)
        this.target.addType(new Arr);
      else
        this.target.addType(getInstance(o, this.ctor));
    }
```
</details>

### `addType(o: any, _weight: any): void`

**Parameters:**

- **`o`** `any`
- **`_weight`** `any`

**Returns:** `void`

**Calls:**

- `adder.addType`
- `o.forAllProps`
- `val.propagate`

<details><summary>Code</summary>

```typescript
function(o, _weight) {
      if (o instanceof Obj && !o.hasCtor) {
        o.hasCtor = this.fn;
        var adder = new SpeculativeThis(o, this.fn);
        adder.addType(this.fn);
        o.forAllProps(function(_prop, val, local) {
          if (local) val.propagate(adder);
        });
      }
    }
```
</details>

### `addType(o: any, _weight: any): void`

**Parameters:**

- **`o`** `any`
- **`_weight`** `any`

**Returns:** `void`

**Calls:**

- `adder.addType`
- `o.forAllProps`
- `val.propagate`

<details><summary>Code</summary>

```typescript
function(o, _weight) {
      if (o instanceof Obj && !o.hasCtor) {
        o.hasCtor = this.fn;
        var adder = new SpeculativeThis(o, this.fn);
        adder.addType(this.fn);
        o.forAllProps(function(_prop, val, local) {
          if (local) val.propagate(adder);
        });
      }
    }
```
</details>

### `addType(o: any, _weight: any): void`

**Parameters:**

- **`o`** `any`
- **`_weight`** `any`

**Returns:** `void`

**Calls:**

- `adder.addType`
- `o.forAllProps`
- `val.propagate`

<details><summary>Code</summary>

```typescript
function(o, _weight) {
      if (o instanceof Obj && !o.hasCtor) {
        o.hasCtor = this.fn;
        var adder = new SpeculativeThis(o, this.fn);
        adder.addType(this.fn);
        o.forAllProps(function(_prop, val, local) {
          if (local) val.propagate(adder);
        });
      }
    }
```
</details>

### `addType(o: any, _weight: any): void`

**Parameters:**

- **`o`** `any`
- **`_weight`** `any`

**Returns:** `void`

**Calls:**

- `adder.addType`
- `o.forAllProps`
- `val.propagate`

<details><summary>Code</summary>

```typescript
function(o, _weight) {
      if (o instanceof Obj && !o.hasCtor) {
        o.hasCtor = this.fn;
        var adder = new SpeculativeThis(o, this.fn);
        adder.addType(this.fn);
        o.forAllProps(function(_prop, val, local) {
          if (local) val.propagate(adder);
        });
      }
    }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `this.other.hasType`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (type == cx.str)
        this.target.addType(cx.str, weight);
      else if (type == cx.num && this.other.hasType(cx.num))
        this.target.addType(cx.num, weight);
    }
```
</details>

### `typeHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.other; }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `this.other.hasType`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (type == cx.str)
        this.target.addType(cx.str, weight);
      else if (type == cx.num && this.other.hasType(cx.num))
        this.target.addType(cx.num, weight);
    }
```
</details>

### `typeHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.other; }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `this.other.hasType`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (type == cx.str)
        this.target.addType(cx.str, weight);
      else if (type == cx.num && this.other.hasType(cx.num))
        this.target.addType(cx.num, weight);
    }
```
</details>

### `typeHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.other; }
```
</details>

### `addType(type: any, weight: any): void`

**Parameters:**

- **`type`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`
- `this.other.hasType`

<details><summary>Code</summary>

```typescript
function(type, weight) {
      if (type == cx.str)
        this.target.addType(cx.str, weight);
      else if (type == cx.num && this.other.hasType(cx.num))
        this.target.addType(cx.num, weight);
    }
```
</details>

### `typeHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.other; }
```
</details>

### `addType(t: any, weight: any): void`

**Parameters:**

- **`t`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`

<details><summary>Code</summary>

```typescript
function(t, weight) {
      if (t instanceof Obj) this.target.addType(t, weight);
    }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.target; }
```
</details>

### `addType(t: any, weight: any): void`

**Parameters:**

- **`t`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`

<details><summary>Code</summary>

```typescript
function(t, weight) {
      if (t instanceof Obj) this.target.addType(t, weight);
    }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.target; }
```
</details>

### `addType(t: any, weight: any): void`

**Parameters:**

- **`t`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`

<details><summary>Code</summary>

```typescript
function(t, weight) {
      if (t instanceof Obj) this.target.addType(t, weight);
    }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.target; }
```
</details>

### `addType(t: any, weight: any): void`

**Parameters:**

- **`t`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.target.addType`

<details><summary>Code</summary>

```typescript
function(t, weight) {
      if (t instanceof Obj) this.target.addType(t, weight);
    }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.target; }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `tp.self.isEmpty`
- `tp.self.addType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (tp instanceof Fn && tp.self && tp.self.isEmpty())
        tp.self.addType(getInstance(this.obj, this.ctor), WG_SPECULATIVE_THIS);
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `tp.self.isEmpty`
- `tp.self.addType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (tp instanceof Fn && tp.self && tp.self.isEmpty())
        tp.self.addType(getInstance(this.obj, this.ctor), WG_SPECULATIVE_THIS);
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `tp.self.isEmpty`
- `tp.self.addType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (tp instanceof Fn && tp.self && tp.self.isEmpty())
        tp.self.addType(getInstance(this.obj, this.ctor), WG_SPECULATIVE_THIS);
    }
```
</details>

### `addType(tp: any): void`

**Parameters:**

- **`tp`** `any`

**Returns:** `void`

**Calls:**

- `tp.self.isEmpty`
- `tp.self.addType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(tp) {
      if (tp instanceof Fn && tp.self && tp.self.isEmpty())
        tp.self.addType(getInstance(this.obj, this.ctor), WG_SPECULATIVE_THIS);
    }
```
</details>

### `addType(tp: any, weight: any): void`

**Parameters:**

- **`tp`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.inner.addType`
- `Math.min`

<details><summary>Code</summary>

```typescript
function(tp, weight) {
      this.inner.addType(tp, Math.min(weight, this.weight));
    }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

**Calls:**

- `this.inner.propagatesTo`

<details><summary>Code</summary>

```typescript
function() { return this.inner.propagatesTo(); }
```
</details>

### `typeHint(): any`

**Returns:** `any`

**Calls:**

- `this.inner.typeHint`

<details><summary>Code</summary>

```typescript
function() { return this.inner.typeHint(); }
```
</details>

### `propHint(): any`

**Returns:** `any`

**Calls:**

- `this.inner.propHint`

<details><summary>Code</summary>

```typescript
function() { return this.inner.propHint(); }
```
</details>

### `addType(tp: any, weight: any): void`

**Parameters:**

- **`tp`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.inner.addType`
- `Math.min`

<details><summary>Code</summary>

```typescript
function(tp, weight) {
      this.inner.addType(tp, Math.min(weight, this.weight));
    }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

**Calls:**

- `this.inner.propagatesTo`

<details><summary>Code</summary>

```typescript
function() { return this.inner.propagatesTo(); }
```
</details>

### `typeHint(): any`

**Returns:** `any`

**Calls:**

- `this.inner.typeHint`

<details><summary>Code</summary>

```typescript
function() { return this.inner.typeHint(); }
```
</details>

### `propHint(): any`

**Returns:** `any`

**Calls:**

- `this.inner.propHint`

<details><summary>Code</summary>

```typescript
function() { return this.inner.propHint(); }
```
</details>

### `addType(tp: any, weight: any): void`

**Parameters:**

- **`tp`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.inner.addType`
- `Math.min`

<details><summary>Code</summary>

```typescript
function(tp, weight) {
      this.inner.addType(tp, Math.min(weight, this.weight));
    }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

**Calls:**

- `this.inner.propagatesTo`

<details><summary>Code</summary>

```typescript
function() { return this.inner.propagatesTo(); }
```
</details>

### `typeHint(): any`

**Returns:** `any`

**Calls:**

- `this.inner.typeHint`

<details><summary>Code</summary>

```typescript
function() { return this.inner.typeHint(); }
```
</details>

### `propHint(): any`

**Returns:** `any`

**Calls:**

- `this.inner.propHint`

<details><summary>Code</summary>

```typescript
function() { return this.inner.propHint(); }
```
</details>

### `addType(tp: any, weight: any): void`

**Parameters:**

- **`tp`** `any`
- **`weight`** `any`

**Returns:** `void`

**Calls:**

- `this.inner.addType`
- `Math.min`

<details><summary>Code</summary>

```typescript
function(tp, weight) {
      this.inner.addType(tp, Math.min(weight, this.weight));
    }
```
</details>

### `propagatesTo(): any`

**Returns:** `any`

**Calls:**

- `this.inner.propagatesTo`

<details><summary>Code</summary>

```typescript
function() { return this.inner.propagatesTo(); }
```
</details>

### `typeHint(): any`

**Returns:** `any`

**Calls:**

- `this.inner.typeHint`

<details><summary>Code</summary>

```typescript
function() { return this.inner.typeHint(); }
```
</details>

### `propHint(): any`

**Returns:** `any`

**Calls:**

- `this.inner.propHint`

<details><summary>Code</summary>

```typescript
function() { return this.inner.propHint(); }
```
</details>

### `propagate(c: any, w: any): void`

**Parameters:**

- **`c`** `any`
- **`w`** `any`

**Returns:** `void`

**Calls:**

- `c.addType`

<details><summary>Code</summary>

```typescript
function(c, w) { c.addType(this, w); }
```
</details>

### `hasType(other: any): boolean`

**Parameters:**

- **`other`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(other) { return other == this; }
```
</details>

### `isEmpty(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return false; }
```
</details>

### `typeHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `getType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `propagate(c: any, w: any): void`

**Parameters:**

- **`c`** `any`
- **`w`** `any`

**Returns:** `void`

**Calls:**

- `c.addType`

<details><summary>Code</summary>

```typescript
function(c, w) { c.addType(this, w); }
```
</details>

### `hasType(other: any): boolean`

**Parameters:**

- **`other`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(other) { return other == this; }
```
</details>

### `isEmpty(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function() { return false; }
```
</details>

### `typeHint(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `getType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `toString(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.name; }
```
</details>

### `getProp(prop: any): any`

**Parameters:**

- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `this.proto.hasProp`

<details><summary>Code</summary>

```typescript
function(prop) {return this.proto.hasProp(prop) || ANull;}
```
</details>

### `gatherProperties(f: any, depth: any): void`

**Parameters:**

- **`f`** `any`
- **`depth`** `any`

**Returns:** `void`

**Calls:**

- `this.proto.gatherProperties`

<details><summary>Code</summary>

```typescript
function(f, depth) {
      if (this.proto) this.proto.gatherProperties(f, depth);
    }
```
</details>

### `toString(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this.name; }
```
</details>

### `getProp(prop: any): any`

**Parameters:**

- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `this.proto.hasProp`

<details><summary>Code</summary>

```typescript
function(prop) {return this.proto.hasProp(prop) || ANull;}
```
</details>

### `gatherProperties(f: any, depth: any): void`

**Parameters:**

- **`f`** `any`
- **`depth`** `any`

**Returns:** `void`

**Calls:**

- `this.proto.gatherProperties`

<details><summary>Code</summary>

```typescript
function(f, depth) {
      if (this.proto) this.proto.gatherProperties(f, depth);
    }
```
</details>

### `toString(maxDepth: any): any`

**Parameters:**

- **`maxDepth`** `any`

**Returns:** `any`

**Calls:**

- `props.push`
- `toString`
- `props.sort`
- `props.join`

<details><summary>Code</summary>

```typescript
function(maxDepth) {
      if (maxDepth == null) maxDepth = 0;
      if (maxDepth <= 0 && this.name) return this.name;
      var props = [], etc = false;
      for (var prop in this.props) if (prop != "<i>") {
        if (props.length > 5) { etc = true; break; }
        if (maxDepth)
          props.push(prop + ": " + toString(this.props[prop], maxDepth - 1, this));
        else
          props.push(prop);
      }
      props.sort();
      if (etc) props.push("...");
      return "{" + props.join(", ") + "}";
    }
```
</details>

### `hasProp(prop: any, searchProto: any): any`

**Parameters:**

- **`prop`** `any`
- **`searchProto`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(prop, searchProto) {
      var found = this.props[prop];
      if (searchProto !== false)
        for (var p = this.proto; p && !found; p = p.proto) found = p.props[prop];
      return found;
    }
```
</details>

### `defProp(prop: any, originNode: any): any`

**Parameters:**

- **`prop`** `any`
- **`originNode`** `any`

**Returns:** `any`

**Calls:**

- `this.hasProp`
- `this.maybeUnregProtoPropHandler`
- `this.broadcastProp`

<details><summary>Code</summary>

```typescript
function(prop, originNode) {
      var found = this.hasProp(prop, false);
      if (found) {
        if (originNode && !found.originNode) found.originNode = originNode;
        return found;
      }
      if (prop == "__proto__" || prop == "✖") return ANull;

      var av = this.maybeProps && this.maybeProps[prop];
      if (av) {
        delete this.maybeProps[prop];
        this.maybeUnregProtoPropHandler();
      } else {
        av = new AVal;
        av.propertyOf = this;
      }

      this.props[prop] = av;
      av.originNode = originNode;
      av.origin = cx.curOrigin;
      this.broadcastProp(prop, av, true);
      return av;
    }
```
</details>

### `getProp(prop: any): any`

**Parameters:**

- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `this.hasProp`
- `this.ensureMaybeProps`

<details><summary>Code</summary>

```typescript
function(prop) {
      var found = this.hasProp(prop, true) || (this.maybeProps && this.maybeProps[prop]);
      if (found) return found;
      if (prop == "__proto__" || prop == "✖") return ANull;
      var av = this.ensureMaybeProps()[prop] = new AVal;
      av.propertyOf = this;
      return av;
    }
```
</details>

### `broadcastProp(prop: any, val: any, local: any): void`

**Parameters:**

- **`prop`** `any`
- **`val`** `any`
- **`local`** `any`

**Returns:** `void`

**Calls:**

- `this.signal`
- `registerProp`
- `h.onProtoProp`
- `h`

**Internal Comments:**
```
// If this is a scope, it shouldn't be registered
```

<details><summary>Code</summary>

```typescript
function(prop, val, local) {
      if (local) {
        this.signal("addProp", prop, val);
        // If this is a scope, it shouldn't be registered
        if (!(this instanceof Scope)) registerProp(prop, this);
      }

      if (this.onNewProp) for (var i = 0; i < this.onNewProp.length; ++i) {
        var h = this.onNewProp[i];
        h.onProtoProp ? h.onProtoProp(prop, val, local) : h(prop, val, local);
      }
    }
```
</details>

### `onProtoProp(prop: any, val: any, _local: any): void`

**Parameters:**

- **`prop`** `any`
- **`val`** `any`
- **`_local`** `any`

**Returns:** `void`

**Calls:**

- `this.maybeUnregProtoPropHandler`
- `this.proto.getProp(prop).propagate`
- `this.broadcastProp`

<details><summary>Code</summary>

```typescript
function(prop, val, _local) {
      var maybe = this.maybeProps && this.maybeProps[prop];
      if (maybe) {
        delete this.maybeProps[prop];
        this.maybeUnregProtoPropHandler();
        this.proto.getProp(prop).propagate(maybe);
      }
      this.broadcastProp(prop, val, false);
    }
```
</details>

### `ensureMaybeProps(): any`

**Returns:** `any`

**Calls:**

- `this.proto.forAllProps`
- `Object.create`

<details><summary>Code</summary>

```typescript
function() {
      if (!this.maybeProps) {
        if (this.proto) this.proto.forAllProps(this);
        this.maybeProps = Object.create(null);
      }
      return this.maybeProps;
    }
```
</details>

### `removeProp(prop: any): void`

**Parameters:**

- **`prop`** `any`

**Returns:** `void`

**Calls:**

- `this.ensureMaybeProps`

<details><summary>Code</summary>

```typescript
function(prop) {
      var av = this.props[prop];
      delete this.props[prop];
      this.ensureMaybeProps()[prop] = av;
      av.types.length = 0;
    }
```
</details>

### `forAllProps(c: any): void`

**Parameters:**

- **`c`** `any`

**Returns:** `void`

**Calls:**

- `this.proto.forAllProps`
- `this.onNewProp.push`
- `c.onProtoProp`
- `c`

<details><summary>Code</summary>

```typescript
function(c) {
      if (!this.onNewProp) {
        this.onNewProp = [];
        if (this.proto) this.proto.forAllProps(this);
      }
      this.onNewProp.push(c);
      for (var o = this; o; o = o.proto) for (var prop in o.props) {
        if (c.onProtoProp)
          c.onProtoProp(prop, o.props[prop], o == this);
        else
          c(prop, o.props[prop], o == this);
      }
    }
```
</details>

### `maybeUnregProtoPropHandler(): void`

**Returns:** `void`

**Calls:**

- `this.proto.unregPropHandler`

<details><summary>Code</summary>

```typescript
function() {
      if (this.maybeProps) {
        for (var _n in this.maybeProps) return;
        this.maybeProps = null;
      }
      if (!this.proto || this.onNewProp && this.onNewProp.length) return;
      this.proto.unregPropHandler(this);
    }
```
</details>

### `unregPropHandler(handler: any): void`

**Parameters:**

- **`handler`** `any`

**Returns:** `void`

**Calls:**

- `this.onNewProp.splice`
- `this.maybeUnregProtoPropHandler`

<details><summary>Code</summary>

```typescript
function(handler) {
      for (var i = 0; i < this.onNewProp.length; ++i)
        if (this.onNewProp[i] == handler) { this.onNewProp.splice(i, 1); break; }
      this.maybeUnregProtoPropHandler();
    }
```
</details>

### `gatherProperties(f: any, depth: any): void`

**Parameters:**

- **`f`** `any`
- **`depth`** `any`

**Returns:** `void`

**Calls:**

- `f`
- `this.proto.gatherProperties`

<details><summary>Code</summary>

```typescript
function(f, depth) {
      for (var prop in this.props) if (prop != "<i>")
        f(prop, this, depth);
      if (this.proto) this.proto.gatherProperties(f, depth + 1);
    }
```
</details>

### `getObjType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `toString(maxDepth: any): any`

**Parameters:**

- **`maxDepth`** `any`

**Returns:** `any`

**Calls:**

- `props.push`
- `toString`
- `props.sort`
- `props.join`

<details><summary>Code</summary>

```typescript
function(maxDepth) {
      if (maxDepth == null) maxDepth = 0;
      if (maxDepth <= 0 && this.name) return this.name;
      var props = [], etc = false;
      for (var prop in this.props) if (prop != "<i>") {
        if (props.length > 5) { etc = true; break; }
        if (maxDepth)
          props.push(prop + ": " + toString(this.props[prop], maxDepth - 1, this));
        else
          props.push(prop);
      }
      props.sort();
      if (etc) props.push("...");
      return "{" + props.join(", ") + "}";
    }
```
</details>

### `hasProp(prop: any, searchProto: any): any`

**Parameters:**

- **`prop`** `any`
- **`searchProto`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(prop, searchProto) {
      var found = this.props[prop];
      if (searchProto !== false)
        for (var p = this.proto; p && !found; p = p.proto) found = p.props[prop];
      return found;
    }
```
</details>

### `defProp(prop: any, originNode: any): any`

**Parameters:**

- **`prop`** `any`
- **`originNode`** `any`

**Returns:** `any`

**Calls:**

- `this.hasProp`
- `this.maybeUnregProtoPropHandler`
- `this.broadcastProp`

<details><summary>Code</summary>

```typescript
function(prop, originNode) {
      var found = this.hasProp(prop, false);
      if (found) {
        if (originNode && !found.originNode) found.originNode = originNode;
        return found;
      }
      if (prop == "__proto__" || prop == "✖") return ANull;

      var av = this.maybeProps && this.maybeProps[prop];
      if (av) {
        delete this.maybeProps[prop];
        this.maybeUnregProtoPropHandler();
      } else {
        av = new AVal;
        av.propertyOf = this;
      }

      this.props[prop] = av;
      av.originNode = originNode;
      av.origin = cx.curOrigin;
      this.broadcastProp(prop, av, true);
      return av;
    }
```
</details>

### `getProp(prop: any): any`

**Parameters:**

- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `this.hasProp`
- `this.ensureMaybeProps`

<details><summary>Code</summary>

```typescript
function(prop) {
      var found = this.hasProp(prop, true) || (this.maybeProps && this.maybeProps[prop]);
      if (found) return found;
      if (prop == "__proto__" || prop == "✖") return ANull;
      var av = this.ensureMaybeProps()[prop] = new AVal;
      av.propertyOf = this;
      return av;
    }
```
</details>

### `broadcastProp(prop: any, val: any, local: any): void`

**Parameters:**

- **`prop`** `any`
- **`val`** `any`
- **`local`** `any`

**Returns:** `void`

**Calls:**

- `this.signal`
- `registerProp`
- `h.onProtoProp`
- `h`

**Internal Comments:**
```
// If this is a scope, it shouldn't be registered
```

<details><summary>Code</summary>

```typescript
function(prop, val, local) {
      if (local) {
        this.signal("addProp", prop, val);
        // If this is a scope, it shouldn't be registered
        if (!(this instanceof Scope)) registerProp(prop, this);
      }

      if (this.onNewProp) for (var i = 0; i < this.onNewProp.length; ++i) {
        var h = this.onNewProp[i];
        h.onProtoProp ? h.onProtoProp(prop, val, local) : h(prop, val, local);
      }
    }
```
</details>

### `onProtoProp(prop: any, val: any, _local: any): void`

**Parameters:**

- **`prop`** `any`
- **`val`** `any`
- **`_local`** `any`

**Returns:** `void`

**Calls:**

- `this.maybeUnregProtoPropHandler`
- `this.proto.getProp(prop).propagate`
- `this.broadcastProp`

<details><summary>Code</summary>

```typescript
function(prop, val, _local) {
      var maybe = this.maybeProps && this.maybeProps[prop];
      if (maybe) {
        delete this.maybeProps[prop];
        this.maybeUnregProtoPropHandler();
        this.proto.getProp(prop).propagate(maybe);
      }
      this.broadcastProp(prop, val, false);
    }
```
</details>

### `ensureMaybeProps(): any`

**Returns:** `any`

**Calls:**

- `this.proto.forAllProps`
- `Object.create`

<details><summary>Code</summary>

```typescript
function() {
      if (!this.maybeProps) {
        if (this.proto) this.proto.forAllProps(this);
        this.maybeProps = Object.create(null);
      }
      return this.maybeProps;
    }
```
</details>

### `removeProp(prop: any): void`

**Parameters:**

- **`prop`** `any`

**Returns:** `void`

**Calls:**

- `this.ensureMaybeProps`

<details><summary>Code</summary>

```typescript
function(prop) {
      var av = this.props[prop];
      delete this.props[prop];
      this.ensureMaybeProps()[prop] = av;
      av.types.length = 0;
    }
```
</details>

### `forAllProps(c: any): void`

**Parameters:**

- **`c`** `any`

**Returns:** `void`

**Calls:**

- `this.proto.forAllProps`
- `this.onNewProp.push`
- `c.onProtoProp`
- `c`

<details><summary>Code</summary>

```typescript
function(c) {
      if (!this.onNewProp) {
        this.onNewProp = [];
        if (this.proto) this.proto.forAllProps(this);
      }
      this.onNewProp.push(c);
      for (var o = this; o; o = o.proto) for (var prop in o.props) {
        if (c.onProtoProp)
          c.onProtoProp(prop, o.props[prop], o == this);
        else
          c(prop, o.props[prop], o == this);
      }
    }
```
</details>

### `maybeUnregProtoPropHandler(): void`

**Returns:** `void`

**Calls:**

- `this.proto.unregPropHandler`

<details><summary>Code</summary>

```typescript
function() {
      if (this.maybeProps) {
        for (var _n in this.maybeProps) return;
        this.maybeProps = null;
      }
      if (!this.proto || this.onNewProp && this.onNewProp.length) return;
      this.proto.unregPropHandler(this);
    }
```
</details>

### `unregPropHandler(handler: any): void`

**Parameters:**

- **`handler`** `any`

**Returns:** `void`

**Calls:**

- `this.onNewProp.splice`
- `this.maybeUnregProtoPropHandler`

<details><summary>Code</summary>

```typescript
function(handler) {
      for (var i = 0; i < this.onNewProp.length; ++i)
        if (this.onNewProp[i] == handler) { this.onNewProp.splice(i, 1); break; }
      this.maybeUnregProtoPropHandler();
    }
```
</details>

### `gatherProperties(f: any, depth: any): void`

**Parameters:**

- **`f`** `any`
- **`depth`** `any`

**Returns:** `void`

**Calls:**

- `f`
- `this.proto.gatherProperties`

<details><summary>Code</summary>

```typescript
function(f, depth) {
      for (var prop in this.props) if (prop != "<i>")
        f(prop, this, depth);
      if (this.proto) this.proto.gatherProperties(f, depth + 1);
    }
```
</details>

### `getObjType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `toString(maxDepth: any): string`

**Parameters:**

- **`maxDepth`** `any`

**Returns:** `string`

**Calls:**

- `toString`
- `this.retval.isEmpty`

<details><summary>Code</summary>

```typescript
function(maxDepth) {
      if (maxDepth == null) maxDepth = 0;
      var str = "fn(";
      for (var i = 0; i < this.args.length; ++i) {
        if (i) str += ", ";
        var name = this.argNames[i];
        if (name && name != "?") str += name + ": ";
        str += maxDepth > -3 ? toString(this.args[i], maxDepth - 1, this) : "?";
      }
      str += ")";
      if (!this.retval.isEmpty())
        str += " -> " + (maxDepth > -3 ? toString(this.retval, maxDepth - 1, this) : "?");
      return str;
    }
```
</details>

### `getProp(prop: any): any`

**Parameters:**

- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `this.hasProp`
- `this.defProp`
- `known.addType`
- `Obj.prototype.getProp.call`

<details><summary>Code</summary>

```typescript
function(prop) {
      if (prop == "prototype") {
        var known = this.hasProp(prop, false);
        if (!known) {
          known = this.defProp(prop);
          var proto = new Obj(true, this.name && this.name + ".prototype");
          proto.origin = this.origin;
          known.addType(proto, WG_MADEUP_PROTO);
        }
        return known;
      }
      return Obj.prototype.getProp.call(this, prop);
    }
```
</details>

### `defProp(prop: any, originNode: any): any`

**Parameters:**

- **`prop`** `any`
- **`originNode`** `any`

**Returns:** `any`

**Calls:**

- `this.hasProp`
- `Obj.prototype.defProp.call`
- `found.propagate`

<details><summary>Code</summary>

```typescript
function(prop, originNode) {
      if (prop == "prototype") {
        var found = this.hasProp(prop, false);
        if (found) return found;
        found = Obj.prototype.defProp.call(this, prop, originNode);
        found.origin = this.origin;
        found.propagate(new FnPrototype(this));
        return found;
      }
      return Obj.prototype.defProp.call(this, prop, originNode);
    }
```
</details>

### `getFunctionType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `toString(maxDepth: any): string`

**Parameters:**

- **`maxDepth`** `any`

**Returns:** `string`

**Calls:**

- `toString`
- `this.retval.isEmpty`

<details><summary>Code</summary>

```typescript
function(maxDepth) {
      if (maxDepth == null) maxDepth = 0;
      var str = "fn(";
      for (var i = 0; i < this.args.length; ++i) {
        if (i) str += ", ";
        var name = this.argNames[i];
        if (name && name != "?") str += name + ": ";
        str += maxDepth > -3 ? toString(this.args[i], maxDepth - 1, this) : "?";
      }
      str += ")";
      if (!this.retval.isEmpty())
        str += " -> " + (maxDepth > -3 ? toString(this.retval, maxDepth - 1, this) : "?");
      return str;
    }
```
</details>

### `getProp(prop: any): any`

**Parameters:**

- **`prop`** `any`

**Returns:** `any`

**Calls:**

- `this.hasProp`
- `this.defProp`
- `known.addType`
- `Obj.prototype.getProp.call`

<details><summary>Code</summary>

```typescript
function(prop) {
      if (prop == "prototype") {
        var known = this.hasProp(prop, false);
        if (!known) {
          known = this.defProp(prop);
          var proto = new Obj(true, this.name && this.name + ".prototype");
          proto.origin = this.origin;
          known.addType(proto, WG_MADEUP_PROTO);
        }
        return known;
      }
      return Obj.prototype.getProp.call(this, prop);
    }
```
</details>

### `defProp(prop: any, originNode: any): any`

**Parameters:**

- **`prop`** `any`
- **`originNode`** `any`

**Returns:** `any`

**Calls:**

- `this.hasProp`
- `Obj.prototype.defProp.call`
- `found.propagate`

<details><summary>Code</summary>

```typescript
function(prop, originNode) {
      if (prop == "prototype") {
        var found = this.hasProp(prop, false);
        if (found) return found;
        found = Obj.prototype.defProp.call(this, prop, originNode);
        found.origin = this.origin;
        found.propagate(new FnPrototype(this));
        return found;
      }
      return Obj.prototype.defProp.call(this, prop, originNode);
    }
```
</details>

### `getFunctionType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return this; }
```
</details>

### `toString(maxDepth: any): string`

**Parameters:**

- **`maxDepth`** `any`

**Returns:** `string`

**Calls:**

- `toString`
- `this.getProp`

<details><summary>Code</summary>

```typescript
function(maxDepth) {
      if (maxDepth == null) maxDepth = 0;
      return "[" + (maxDepth > -3 ? toString(this.getProp("<i>"), maxDepth - 1, this) : "?") + "]";
    }
```
</details>

### `toString(maxDepth: any): string`

**Parameters:**

- **`maxDepth`** `any`

**Returns:** `string`

**Calls:**

- `toString`
- `this.getProp`

<details><summary>Code</summary>

```typescript
function(maxDepth) {
      if (maxDepth == null) maxDepth = 0;
      return "[" + (maxDepth > -3 ? toString(this.getProp("<i>"), maxDepth - 1, this) : "?") + "]";
    }
```
</details>

### `registerProp(prop: any, obj: any): void`

**Parameters:**

- **`prop`** `any`
- **`obj`** `any`

**Returns:** `void`

**Calls:**

- `data.push`

<details><summary>Code</summary>

```typescript
function registerProp(prop, obj) {
    var data = cx.props[prop] || (cx.props[prop] = []);
    data.push(obj);
  }
```
</details>

### `objsWithProp(prop: any): any`

**Parameters:**

- **`prop`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function objsWithProp(prop) {
    return cx.props[prop];
  }
```
</details>

### `withWorklist(f: any): any`

**Parameters:**

- **`f`** `any`

**Returns:** `any`

**Calls:**

- `f`
- `list.push`
- `list[i + 1].addType`

<details><summary>Code</summary>

```typescript
function withWorklist(f) {
    if (cx.workList) return f(cx.workList);

    var list = [], depth = 0;
    var add = cx.workList = function(type, target, weight) {
      if (depth < baseMaxWorkDepth - reduceMaxWorkDepth * list.length)
        list.push(type, target, weight, depth);
    };
    try {
      var ret = f(add);
      for (var i = 0; i < list.length; i += 4) {
        if (timeout && +new Date >= timeout)
          throw new exports.TimedOut();
        depth = list[i + 3] + 1;
        list[i + 1].addType(list[i], list[i + 2]);
      }
      return ret;
    } finally {
      cx.workList = null;
    }
  }
```
</details>

### `defVar(name: any, originNode: any): any`

**Parameters:**

- **`name`** `any`
- **`originNode`** `any`

**Returns:** `any`

**Calls:**

- `s.defProp`

<details><summary>Code</summary>

```typescript
function(name, originNode) {
      for (var s = this; ; s = s.proto) {
        var found = s.props[name];
        if (found) return found;
        if (!s.prev) return s.defProp(name, originNode);
      }
    }
```
</details>

### `defVar(name: any, originNode: any): any`

**Parameters:**

- **`name`** `any`
- **`originNode`** `any`

**Returns:** `any`

**Calls:**

- `s.defProp`

<details><summary>Code</summary>

```typescript
function(name, originNode) {
      for (var s = this; ; s = s.proto) {
        var found = s.props[name];
        if (found) return found;
        if (!s.prev) return s.defProp(name, originNode);
      }
    }
```
</details>

### `maybeInstantiate(scope: any, score: any): void`

**Parameters:**

- **`scope`** `any`
- **`score`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function maybeInstantiate(scope, score) {
    if (scope.fnType)
      scope.fnType.instantiateScore = (scope.fnType.instantiateScore || 0) + score;
  }
```
</details>

### `nodeSmallerThan(node: any, n: any): boolean`

**Parameters:**

- **`node`** `any`
- **`n`** `any`

**Returns:** `boolean`

**Calls:**

- `walk.simple`

<details><summary>Code</summary>

```typescript
function nodeSmallerThan(node, n) {
    try {
      walk.simple(node, {Expression: function() { if (--n <= 0) throw NotSmaller; }});
      return true;
    } catch(e) {
      if (e == NotSmaller) return false;
      throw e;
    }
  }
```
</details>

### `Expression(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { if (--n <= 0) throw NotSmaller; }
```
</details>

### `Expression(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function() { if (--n <= 0) throw NotSmaller; }
```
</details>

### `maybeTagAsInstantiated(node: any, scope: any): boolean`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `boolean`

**Calls:**

- `nodeSmallerThan`
- `maybeInstantiate`
- `setFunctionInstantiated`

<details><summary>Code</summary>

```typescript
function maybeTagAsInstantiated(node, scope) {
    var score = scope.fnType.instantiateScore;
    if (!cx.disabledComputing && score && scope.fnType.args.length && nodeSmallerThan(node, score * 5)) {
      maybeInstantiate(scope.prev, score / 2);
      setFunctionInstantiated(node, scope);
      return true;
    } else {
      scope.fnType.instantiateScore = null;
    }
  }
```
</details>

### `setFunctionInstantiated(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `withDisabledComputing`
- `scopeCopy.defProp`
- `args[i].propagate`
- `fn.argNames.slice`
- `argNames.push`
- `scopeCopy.defProp("arguments").addType`
- `walk.recursive`

**Internal Comments:**
```
// Disconnect the arg avals, so that we can add info to them without side effects
// Prevent recursion
```

<details><summary>Code</summary>

```typescript
function setFunctionInstantiated(node, scope) {
    var fn = scope.fnType;
    // Disconnect the arg avals, so that we can add info to them without side effects
    for (var i = 0; i < fn.args.length; ++i) fn.args[i] = new AVal;
    fn.self = new AVal;
    fn.computeRet = function(self, args) {
      // Prevent recursion
      return withDisabledComputing(fn, function() {
        var oldOrigin = cx.curOrigin;
        cx.curOrigin = fn.origin;
        var scopeCopy = new Scope(scope.prev);
        scopeCopy.originNode = scope.originNode;
        for (var v in scope.props) {
          var local = scopeCopy.defProp(v, scope.props[v].originNode);
          for (var i = 0; i < args.length; ++i) if (fn.argNames[i] == v && i < args.length)
            args[i].propagate(local);
        }
        var argNames = fn.argNames.length != args.length ? fn.argNames.slice(0, args.length) : fn.argNames;
        while (argNames.length < args.length) argNames.push("?");
        scopeCopy.fnType = new Fn(fn.name, self, args, argNames, ANull);
        scopeCopy.fnType.originNode = fn.originNode;
        if (fn.arguments) {
          var argset = scopeCopy.fnType.arguments = new AVal;
          scopeCopy.defProp("arguments").addType(new Arr(argset));
          for (var i = 0; i < args.length; ++i) args[i].propagate(argset);
        }
        node.body.scope = scopeCopy;
        walk.recursive(node.body, scopeCopy, null, scopeGatherer);
        walk.recursive(node.body, scopeCopy, null, inferWrapper);
        cx.curOrigin = oldOrigin;
        return scopeCopy.fnType.retval;
      });
    };
  }
```
</details>

### `maybeTagAsGeneric(scope: any): boolean`

**Parameters:**

- **`scope`** `any`

**Returns:** `boolean`

**Calls:**

- `target.isEmpty`
- `target.getType`
- `targetInner.getProp`
- `aval.forward[i].propagatesTo`
- `explore`
- `p.parseType`

<details><summary>Code</summary>

```typescript
function maybeTagAsGeneric(scope) {
    var fn = scope.fnType, target = fn.retval;
    if (target == ANull) return;
    var targetInner, asArray;
    if (!target.isEmpty() && (targetInner = target.getType()) instanceof Arr)
      target = asArray = targetInner.getProp("<i>");

    function explore(aval, path, depth) {
      if (depth > 3 || !aval.forward) return;
      for (var i = 0; i < aval.forward.length; ++i) {
        var prop = aval.forward[i].propagatesTo();
        if (!prop) continue;
        var newPath = path, dest;
        if (prop instanceof AVal) {
          dest = prop;
        } else if (prop.target instanceof AVal) {
          newPath += prop.pathExt;
          dest = prop.target;
        } else continue;
        if (dest == target) return newPath;
        var found = explore(dest, newPath, depth + 1);
        if (found) return found;
      }
    }

    var foundPath = explore(fn.self, "!this", 0);
    for (var i = 0; !foundPath && i < fn.args.length; ++i)
      foundPath = explore(fn.args[i], "!" + i, 0);

    if (foundPath) {
      if (asArray) foundPath = "[" + foundPath + "]";
      var p = new def.TypeParser(foundPath);
      var parsed = p.parseType(true);
      fn.computeRet = parsed.apply ? parsed : function() { return parsed; };
      fn.computeRetSource = foundPath;
      return true;
    }
  }
```
</details>

### `explore(aval: any, path: any, depth: any): any`

**Parameters:**

- **`aval`** `any`
- **`path`** `any`
- **`depth`** `any`

**Returns:** `any`

**Calls:**

- `aval.forward[i].propagatesTo`
- `explore`

<details><summary>Code</summary>

```typescript
function explore(aval, path, depth) {
      if (depth > 3 || !aval.forward) return;
      for (var i = 0; i < aval.forward.length; ++i) {
        var prop = aval.forward[i].propagatesTo();
        if (!prop) continue;
        var newPath = path, dest;
        if (prop instanceof AVal) {
          dest = prop;
        } else if (prop.target instanceof AVal) {
          newPath += prop.pathExt;
          dest = prop.target;
        } else continue;
        if (dest == target) return newPath;
        var found = explore(dest, newPath, depth + 1);
        if (found) return found;
      }
    }
```
</details>

### `addVar(scope: any, nameNode: any): any`

**Parameters:**

- **`scope`** `any`
- **`nameNode`** `any`

**Returns:** `any`

**Calls:**

- `scope.defProp`

<details><summary>Code</summary>

```typescript
function addVar(scope, nameNode) {
    return scope.defProp(nameNode.name, nameNode);
  }
```
</details>

### `Function(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `argNames.push`
- `argVals.push`
- `addVar`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var inner = node.body.scope = new Scope(scope);
      inner.originNode = node;
      var argVals = [], argNames = [];
      for (var i = 0; i < node.params.length; ++i) {
        var param = node.params[i];
        argNames.push(param.name);
        argVals.push(addVar(inner, param));
      }
      inner.fnType = new Fn(node.id && node.id.name, new AVal, argVals, argNames, ANull);
      inner.fnType.originNode = node;
      if (node.id) {
        var decl = node.type == "FunctionDeclaration";
        addVar(decl ? scope : inner, node.id);
      }
      c(node.body, inner, "ScopeBody");
    }
```
</details>

### `TryStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `addVar`
- `v.isEmpty`
- `getInstance(e5["Error.prototype"]).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      c(node.block, scope, "Statement");
      if (node.handler) {
        var v = addVar(scope, node.handler.param);
        c(node.handler.body, scope, "ScopeBody");
        var e5 = cx.definitions.ecma5;
        if (e5 && v.isEmpty()) getInstance(e5["Error.prototype"]).propagate(v, WG_CATCH_ERROR);
      }
      if (node.finalizer) c(node.finalizer, scope, "Statement");
    }
```
</details>

### `VariableDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `addVar`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i];
        addVar(scope, decl.id);
        if (decl.init) c(decl.init, scope, "Expression");
      }
    }
```
</details>

### `Function(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `argNames.push`
- `argVals.push`
- `addVar`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var inner = node.body.scope = new Scope(scope);
      inner.originNode = node;
      var argVals = [], argNames = [];
      for (var i = 0; i < node.params.length; ++i) {
        var param = node.params[i];
        argNames.push(param.name);
        argVals.push(addVar(inner, param));
      }
      inner.fnType = new Fn(node.id && node.id.name, new AVal, argVals, argNames, ANull);
      inner.fnType.originNode = node;
      if (node.id) {
        var decl = node.type == "FunctionDeclaration";
        addVar(decl ? scope : inner, node.id);
      }
      c(node.body, inner, "ScopeBody");
    }
```
</details>

### `TryStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `addVar`
- `v.isEmpty`
- `getInstance(e5["Error.prototype"]).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      c(node.block, scope, "Statement");
      if (node.handler) {
        var v = addVar(scope, node.handler.param);
        c(node.handler.body, scope, "ScopeBody");
        var e5 = cx.definitions.ecma5;
        if (e5 && v.isEmpty()) getInstance(e5["Error.prototype"]).propagate(v, WG_CATCH_ERROR);
      }
      if (node.finalizer) c(node.finalizer, scope, "Statement");
    }
```
</details>

### `VariableDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `addVar`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i];
        addVar(scope, decl.id);
        if (decl.init) c(decl.init, scope, "Expression");
      }
    }
```
</details>

### `Function(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `argNames.push`
- `argVals.push`
- `addVar`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var inner = node.body.scope = new Scope(scope);
      inner.originNode = node;
      var argVals = [], argNames = [];
      for (var i = 0; i < node.params.length; ++i) {
        var param = node.params[i];
        argNames.push(param.name);
        argVals.push(addVar(inner, param));
      }
      inner.fnType = new Fn(node.id && node.id.name, new AVal, argVals, argNames, ANull);
      inner.fnType.originNode = node;
      if (node.id) {
        var decl = node.type == "FunctionDeclaration";
        addVar(decl ? scope : inner, node.id);
      }
      c(node.body, inner, "ScopeBody");
    }
```
</details>

### `TryStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `addVar`
- `v.isEmpty`
- `getInstance(e5["Error.prototype"]).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      c(node.block, scope, "Statement");
      if (node.handler) {
        var v = addVar(scope, node.handler.param);
        c(node.handler.body, scope, "ScopeBody");
        var e5 = cx.definitions.ecma5;
        if (e5 && v.isEmpty()) getInstance(e5["Error.prototype"]).propagate(v, WG_CATCH_ERROR);
      }
      if (node.finalizer) c(node.finalizer, scope, "Statement");
    }
```
</details>

### `VariableDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `addVar`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i];
        addVar(scope, decl.id);
        if (decl.init) c(decl.init, scope, "Expression");
      }
    }
```
</details>

### `Function(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `argNames.push`
- `argVals.push`
- `addVar`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var inner = node.body.scope = new Scope(scope);
      inner.originNode = node;
      var argVals = [], argNames = [];
      for (var i = 0; i < node.params.length; ++i) {
        var param = node.params[i];
        argNames.push(param.name);
        argVals.push(addVar(inner, param));
      }
      inner.fnType = new Fn(node.id && node.id.name, new AVal, argVals, argNames, ANull);
      inner.fnType.originNode = node;
      if (node.id) {
        var decl = node.type == "FunctionDeclaration";
        addVar(decl ? scope : inner, node.id);
      }
      c(node.body, inner, "ScopeBody");
    }
```
</details>

### `TryStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `addVar`
- `v.isEmpty`
- `getInstance(e5["Error.prototype"]).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      c(node.block, scope, "Statement");
      if (node.handler) {
        var v = addVar(scope, node.handler.param);
        c(node.handler.body, scope, "ScopeBody");
        var e5 = cx.definitions.ecma5;
        if (e5 && v.isEmpty()) getInstance(e5["Error.prototype"]).propagate(v, WG_CATCH_ERROR);
      }
      if (node.finalizer) c(node.finalizer, scope, "Statement");
    }
```
</details>

### `VariableDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `addVar`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i];
        addVar(scope, decl.id);
        if (decl.init) c(decl.init, scope, "Expression");
      }
    }
```
</details>

### `propName(node: any, scope: any, c: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `any`

**Calls:**

- `infer`

<details><summary>Code</summary>

```typescript
function propName(node, scope, c) {
    var prop = node.property;
    if (!node.computed) return prop.name;
    if (prop.type == "Literal" && typeof prop.value == "string") return prop.value;
    if (c) infer(prop, scope, c, ANull);
    return "<i>";
  }
```
</details>

### `unopResultType(op: any): any`

**Parameters:**

- **`op`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function unopResultType(op) {
    switch (op) {
    case "+": case "-": case "~": return cx.num;
    case "!": return cx.bool;
    case "typeof": return cx.str;
    case "void": case "delete": return ANull;
    }
  }
```
</details>

### `binopIsBoolean(op: any): boolean`

**Parameters:**

- **`op`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function binopIsBoolean(op) {
    switch (op) {
    case "==": case "!=": case "===": case "!==": case "<": case ">": case ">=": case "<=":
    case "in": case "instanceof": return true;
    }
  }
```
</details>

### `literalType(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `getInstance`

<details><summary>Code</summary>

```typescript
function literalType(node) {
    if (node.regex) return getInstance(cx.protos.RegExp);
    switch (typeof node.value) {
    case "boolean": return cx.bool;
    case "number": return cx.num;
    case "string": return cx.str;
    case "object":
    case "function":
      if (!node.value) return ANull;
      return getInstance(cx.protos.RegExp);
    }
  }
```
</details>

### `ret(f: any): (node: any, scope: any, c: any, out: any, name: any) => any`

**Parameters:**

- **`f`** `any`

**Returns:** `(node: any, scope: any, c: any, out: any, name: any) => any`

**Calls:**

- `f`
- `r.propagate`

<details><summary>Code</summary>

```typescript
function ret(f) {
    return function(node, scope, c, out, name) {
      var r = f(node, scope, c, name);
      if (out) r.propagate(out);
      return r;
    };
  }
```
</details>

### `fill(f: any): (node: any, scope: any, c: any, out: any, name: any) => any`

**Parameters:**

- **`f`** `any`

**Returns:** `(node: any, scope: any, c: any, out: any, name: any) => any`

**Calls:**

- `f`

<details><summary>Code</summary>

```typescript
function fill(f) {
    return function(node, scope, c, out, name) {
      if (!out) out = new AVal;
      f(node, scope, c, out, name);
      return out;
    };
  }
```
</details>

### `infer(node: any, scope: any, c: any, out: any, name: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`
- **`out`** `any`
- **`name`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_41244`

<details><summary>Code</summary>

```typescript
function infer(node, scope, c, out, name) {
    return inferExprVisitor[node.type](node, scope, c, out, name);
  }
```
</details>

### `Expression(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      infer(node, scope, c, ANull);
    }
```
</details>

### `FunctionDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `maybeTagAsInstantiated`
- `maybeTagAsGeneric`
- `scope.getProp`
- `prop.addType`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var inner = node.body.scope, fn = inner.fnType;
      c(node.body, scope, "ScopeBody");
      maybeTagAsInstantiated(node, inner) || maybeTagAsGeneric(inner);
      var prop = scope.getProp(node.id.name);
      prop.addType(fn);
    }
```
</details>

### `VariableDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `scope.getProp`
- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i], prop = scope.getProp(decl.id.name);
        if (decl.init)
          infer(decl.init, scope, c, prop, decl.id.name);
      }
    }
```
</details>

### `ReturnStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      if (!node.argument) return;
      var output = ANull;
      if (scope.fnType) {
        if (scope.fnType.retval == ANull) scope.fnType.retval = new AVal;
        output = scope.fnType.retval;
      }
      infer(node.argument, scope, c, output);
    }
```
</details>

### `ForInStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`
- `maybeInstantiate`
- `scope.getProp`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var source = infer(node.right, scope, c);
      if ((node.right.type == "Identifier" && node.right.name in scope.props) ||
          (node.right.type == "MemberExpression" && node.right.property.name == "prototype")) {
        maybeInstantiate(scope, 5);
        var varName;
        if (node.left.type == "Identifier") {
          varName = node.left.name;
        } else if (node.left.type == "VariableDeclaration") {
          varName = node.left.declarations[0].id.name;
        }
        if (varName && varName in scope.props)
          scope.getProp(varName).iteratesOver = source;
      }
      c(node.body, scope, "Statement");
    }
```
</details>

### `ScopeBody(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) { c(node, node.scope || scope); }
```
</details>

### `Expression(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      infer(node, scope, c, ANull);
    }
```
</details>

### `FunctionDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `maybeTagAsInstantiated`
- `maybeTagAsGeneric`
- `scope.getProp`
- `prop.addType`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var inner = node.body.scope, fn = inner.fnType;
      c(node.body, scope, "ScopeBody");
      maybeTagAsInstantiated(node, inner) || maybeTagAsGeneric(inner);
      var prop = scope.getProp(node.id.name);
      prop.addType(fn);
    }
```
</details>

### `VariableDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `scope.getProp`
- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i], prop = scope.getProp(decl.id.name);
        if (decl.init)
          infer(decl.init, scope, c, prop, decl.id.name);
      }
    }
```
</details>

### `ReturnStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      if (!node.argument) return;
      var output = ANull;
      if (scope.fnType) {
        if (scope.fnType.retval == ANull) scope.fnType.retval = new AVal;
        output = scope.fnType.retval;
      }
      infer(node.argument, scope, c, output);
    }
```
</details>

### `ForInStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`
- `maybeInstantiate`
- `scope.getProp`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var source = infer(node.right, scope, c);
      if ((node.right.type == "Identifier" && node.right.name in scope.props) ||
          (node.right.type == "MemberExpression" && node.right.property.name == "prototype")) {
        maybeInstantiate(scope, 5);
        var varName;
        if (node.left.type == "Identifier") {
          varName = node.left.name;
        } else if (node.left.type == "VariableDeclaration") {
          varName = node.left.declarations[0].id.name;
        }
        if (varName && varName in scope.props)
          scope.getProp(varName).iteratesOver = source;
      }
      c(node.body, scope, "Statement");
    }
```
</details>

### `ScopeBody(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) { c(node, node.scope || scope); }
```
</details>

### `Expression(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      infer(node, scope, c, ANull);
    }
```
</details>

### `FunctionDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `maybeTagAsInstantiated`
- `maybeTagAsGeneric`
- `scope.getProp`
- `prop.addType`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var inner = node.body.scope, fn = inner.fnType;
      c(node.body, scope, "ScopeBody");
      maybeTagAsInstantiated(node, inner) || maybeTagAsGeneric(inner);
      var prop = scope.getProp(node.id.name);
      prop.addType(fn);
    }
```
</details>

### `VariableDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `scope.getProp`
- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i], prop = scope.getProp(decl.id.name);
        if (decl.init)
          infer(decl.init, scope, c, prop, decl.id.name);
      }
    }
```
</details>

### `ReturnStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      if (!node.argument) return;
      var output = ANull;
      if (scope.fnType) {
        if (scope.fnType.retval == ANull) scope.fnType.retval = new AVal;
        output = scope.fnType.retval;
      }
      infer(node.argument, scope, c, output);
    }
```
</details>

### `ForInStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`
- `maybeInstantiate`
- `scope.getProp`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var source = infer(node.right, scope, c);
      if ((node.right.type == "Identifier" && node.right.name in scope.props) ||
          (node.right.type == "MemberExpression" && node.right.property.name == "prototype")) {
        maybeInstantiate(scope, 5);
        var varName;
        if (node.left.type == "Identifier") {
          varName = node.left.name;
        } else if (node.left.type == "VariableDeclaration") {
          varName = node.left.declarations[0].id.name;
        }
        if (varName && varName in scope.props)
          scope.getProp(varName).iteratesOver = source;
      }
      c(node.body, scope, "Statement");
    }
```
</details>

### `ScopeBody(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) { c(node, node.scope || scope); }
```
</details>

### `Expression(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      infer(node, scope, c, ANull);
    }
```
</details>

### `FunctionDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `maybeTagAsInstantiated`
- `maybeTagAsGeneric`
- `scope.getProp`
- `prop.addType`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var inner = node.body.scope, fn = inner.fnType;
      c(node.body, scope, "ScopeBody");
      maybeTagAsInstantiated(node, inner) || maybeTagAsGeneric(inner);
      var prop = scope.getProp(node.id.name);
      prop.addType(fn);
    }
```
</details>

### `VariableDeclaration(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `scope.getProp`
- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i], prop = scope.getProp(decl.id.name);
        if (decl.init)
          infer(decl.init, scope, c, prop, decl.id.name);
      }
    }
```
</details>

### `ReturnStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      if (!node.argument) return;
      var output = ANull;
      if (scope.fnType) {
        if (scope.fnType.retval == ANull) scope.fnType.retval = new AVal;
        output = scope.fnType.retval;
      }
      infer(node.argument, scope, c, output);
    }
```
</details>

### `ForInStatement(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `infer`
- `maybeInstantiate`
- `scope.getProp`
- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) {
      var source = infer(node.right, scope, c);
      if ((node.right.type == "Identifier" && node.right.name in scope.props) ||
          (node.right.type == "MemberExpression" && node.right.property.name == "prototype")) {
        maybeInstantiate(scope, 5);
        var varName;
        if (node.left.type == "Identifier") {
          varName = node.left.name;
        } else if (node.left.type == "VariableDeclaration") {
          varName = node.left.declarations[0].id.name;
        }
        if (varName && varName in scope.props)
          scope.getProp(varName).iteratesOver = source;
      }
      c(node.body, scope, "Statement");
    }
```
</details>

### `ScopeBody(node: any, scope: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, scope, c) { c(node, node.scope || scope); }
```
</details>

### `runPasses(passes: any, pass: any): void`

**Parameters:**

- **`passes`** `any`
- **`pass`** `any`

**Returns:** `void`

**Calls:**

- `Array.prototype.slice.call`
- `arr[i].apply`

<details><summary>Code</summary>

```typescript
function runPasses(passes, pass) {
    var arr = passes && passes[pass];
    var args = Array.prototype.slice.call(arguments, 2);
    if (arr) for (var i = 0; i < arr.length; ++i) arr[i].apply(null, args);
  }
```
</details>

### `makePredicate(origins: any, start: any, end: any): (n: any, pos: any) => boolean`

**Parameters:**

- **`origins`** `any`
- **`start`** `any`
- **`end`** `any`

**Returns:** `(n: any, pos: any) => boolean`

**Calls:**

- `Array.isArray`
- `origins.indexOf`

<details><summary>Code</summary>

```typescript
function makePredicate(origins, start, end) {
    var arr = Array.isArray(origins);
    if (arr && origins.length == 1) { origins = origins[0]; arr = false; }
    if (arr) {
      if (end == null) return function(n) { return origins.indexOf(n.origin) > -1; };
      return function(n, pos) { return pos && pos.start >= start && pos.end <= end && origins.indexOf(n.origin) > -1; };
    } else {
      if (end == null) return function(n) { return n.origin == origins; };
      return function(n, pos) { return pos && pos.start >= start && pos.end <= end && n.origin == origins; };
    }
  }
```
</details>

### `findByPropertyName(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `objsWithProp`
- `found[i].getProp`
- `val.isEmpty`

<details><summary>Code</summary>

```typescript
function findByPropertyName(name) {
    guessing = true;
    var found = objsWithProp(name);
    if (found) for (var i = 0; i < found.length; ++i) {
      var val = found[i].getProp(name);
      if (!val.isEmpty()) return val;
    }
    return ANull;
  }
```
</details>

### `ArrayExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(elt, scope).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var eltval = new AVal;
      for (var i = 0; i < node.elements.length; ++i) {
        var elt = node.elements[i];
        if (elt) findType(elt, scope).propagate(eltval);
      }
      return new Arr(eltval);
    }
```
</details>

### `ObjectExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.objType;
    }
```
</details>

### `FunctionExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.body.scope.fnType;
    }
```
</details>

### `SequenceExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.expressions[node.expressions.length-1], scope);
    }
```
</details>

### `UnaryExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(node) {
      return unopResultType(node.operator);
    }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
      return cx.num;
    }
```
</details>

### `BinaryExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`
- `findType`
- `lhs.hasType`
- `rhs.hasType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      if (binopIsBoolean(node.operator)) return cx.bool;
      if (node.operator == "+") {
        var lhs = findType(node.left, scope);
        var rhs = findType(node.right, scope);
        if (lhs.hasType(cx.str) || rhs.hasType(cx.str)) return cx.str;
      }
      return cx.num;
    }
```
</details>

### `AssignmentExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.right, scope);
    }
```
</details>

### `LogicalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.left, scope);
      return lhs.isEmpty() ? findType(node.right, scope) : lhs;
    }
```
</details>

### `ConditionalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.consequent, scope);
      return lhs.isEmpty() ? findType(node.alternate, scope) : lhs;
    }
```
</details>

### `NewExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `f.getProp("prototype").getObjType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      var proto = f && f.getProp("prototype").getObjType();
      if (!proto) return ANull;
      return getInstance(proto, f);
    }
```
</details>

### `CallExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `args.push`
- `findType`
- `f.computeRet`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      if (!f) return ANull;
      if (f.computeRet) {
        for (var i = 0, args = []; i < node.arguments.length; ++i)
          args.push(findType(node.arguments[i], scope));
        var self = ANull;
        if (node.callee.type == "MemberExpression")
          self = findType(node.callee.object, scope);
        return f.computeRet(self, args, node.arguments);
      } else {
        return f.retval;
      }
    }
```
</details>

### `MemberExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `propName`
- `findType(node.object, scope).getType`
- `obj.getProp`
- `findByPropertyName`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var propN = propName(node, scope), obj = findType(node.object, scope).getType();
      if (obj) return obj.getProp(propN);
      if (propN == "<i>") return ANull;
      return findByPropertyName(propN);
    }
```
</details>

### `Identifier(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `scope.hasProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return scope.hasProp(node.name) || ANull;
    }
```
</details>

### `ThisExpression(_node: any, scope: any): any`

**Parameters:**

- **`_node`** `any`
- **`scope`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(_node, scope) {
      return scope.fnType ? scope.fnType.self : cx.topScope;
    }
```
</details>

### `Literal(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `literalType`

<details><summary>Code</summary>

```typescript
function(node) {
      return literalType(node);
    }
```
</details>

### `ArrayExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(elt, scope).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var eltval = new AVal;
      for (var i = 0; i < node.elements.length; ++i) {
        var elt = node.elements[i];
        if (elt) findType(elt, scope).propagate(eltval);
      }
      return new Arr(eltval);
    }
```
</details>

### `ObjectExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.objType;
    }
```
</details>

### `FunctionExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.body.scope.fnType;
    }
```
</details>

### `SequenceExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.expressions[node.expressions.length-1], scope);
    }
```
</details>

### `UnaryExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(node) {
      return unopResultType(node.operator);
    }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
      return cx.num;
    }
```
</details>

### `BinaryExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`
- `findType`
- `lhs.hasType`
- `rhs.hasType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      if (binopIsBoolean(node.operator)) return cx.bool;
      if (node.operator == "+") {
        var lhs = findType(node.left, scope);
        var rhs = findType(node.right, scope);
        if (lhs.hasType(cx.str) || rhs.hasType(cx.str)) return cx.str;
      }
      return cx.num;
    }
```
</details>

### `AssignmentExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.right, scope);
    }
```
</details>

### `LogicalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.left, scope);
      return lhs.isEmpty() ? findType(node.right, scope) : lhs;
    }
```
</details>

### `ConditionalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.consequent, scope);
      return lhs.isEmpty() ? findType(node.alternate, scope) : lhs;
    }
```
</details>

### `NewExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `f.getProp("prototype").getObjType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      var proto = f && f.getProp("prototype").getObjType();
      if (!proto) return ANull;
      return getInstance(proto, f);
    }
```
</details>

### `CallExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `args.push`
- `findType`
- `f.computeRet`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      if (!f) return ANull;
      if (f.computeRet) {
        for (var i = 0, args = []; i < node.arguments.length; ++i)
          args.push(findType(node.arguments[i], scope));
        var self = ANull;
        if (node.callee.type == "MemberExpression")
          self = findType(node.callee.object, scope);
        return f.computeRet(self, args, node.arguments);
      } else {
        return f.retval;
      }
    }
```
</details>

### `MemberExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `propName`
- `findType(node.object, scope).getType`
- `obj.getProp`
- `findByPropertyName`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var propN = propName(node, scope), obj = findType(node.object, scope).getType();
      if (obj) return obj.getProp(propN);
      if (propN == "<i>") return ANull;
      return findByPropertyName(propN);
    }
```
</details>

### `Identifier(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `scope.hasProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return scope.hasProp(node.name) || ANull;
    }
```
</details>

### `ThisExpression(_node: any, scope: any): any`

**Parameters:**

- **`_node`** `any`
- **`scope`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(_node, scope) {
      return scope.fnType ? scope.fnType.self : cx.topScope;
    }
```
</details>

### `Literal(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `literalType`

<details><summary>Code</summary>

```typescript
function(node) {
      return literalType(node);
    }
```
</details>

### `ArrayExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(elt, scope).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var eltval = new AVal;
      for (var i = 0; i < node.elements.length; ++i) {
        var elt = node.elements[i];
        if (elt) findType(elt, scope).propagate(eltval);
      }
      return new Arr(eltval);
    }
```
</details>

### `ObjectExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.objType;
    }
```
</details>

### `FunctionExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.body.scope.fnType;
    }
```
</details>

### `SequenceExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.expressions[node.expressions.length-1], scope);
    }
```
</details>

### `UnaryExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(node) {
      return unopResultType(node.operator);
    }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
      return cx.num;
    }
```
</details>

### `BinaryExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`
- `findType`
- `lhs.hasType`
- `rhs.hasType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      if (binopIsBoolean(node.operator)) return cx.bool;
      if (node.operator == "+") {
        var lhs = findType(node.left, scope);
        var rhs = findType(node.right, scope);
        if (lhs.hasType(cx.str) || rhs.hasType(cx.str)) return cx.str;
      }
      return cx.num;
    }
```
</details>

### `AssignmentExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.right, scope);
    }
```
</details>

### `LogicalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.left, scope);
      return lhs.isEmpty() ? findType(node.right, scope) : lhs;
    }
```
</details>

### `ConditionalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.consequent, scope);
      return lhs.isEmpty() ? findType(node.alternate, scope) : lhs;
    }
```
</details>

### `NewExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `f.getProp("prototype").getObjType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      var proto = f && f.getProp("prototype").getObjType();
      if (!proto) return ANull;
      return getInstance(proto, f);
    }
```
</details>

### `CallExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `args.push`
- `findType`
- `f.computeRet`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      if (!f) return ANull;
      if (f.computeRet) {
        for (var i = 0, args = []; i < node.arguments.length; ++i)
          args.push(findType(node.arguments[i], scope));
        var self = ANull;
        if (node.callee.type == "MemberExpression")
          self = findType(node.callee.object, scope);
        return f.computeRet(self, args, node.arguments);
      } else {
        return f.retval;
      }
    }
```
</details>

### `MemberExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `propName`
- `findType(node.object, scope).getType`
- `obj.getProp`
- `findByPropertyName`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var propN = propName(node, scope), obj = findType(node.object, scope).getType();
      if (obj) return obj.getProp(propN);
      if (propN == "<i>") return ANull;
      return findByPropertyName(propN);
    }
```
</details>

### `Identifier(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `scope.hasProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return scope.hasProp(node.name) || ANull;
    }
```
</details>

### `ThisExpression(_node: any, scope: any): any`

**Parameters:**

- **`_node`** `any`
- **`scope`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(_node, scope) {
      return scope.fnType ? scope.fnType.self : cx.topScope;
    }
```
</details>

### `Literal(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `literalType`

<details><summary>Code</summary>

```typescript
function(node) {
      return literalType(node);
    }
```
</details>

### `ArrayExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(elt, scope).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var eltval = new AVal;
      for (var i = 0; i < node.elements.length; ++i) {
        var elt = node.elements[i];
        if (elt) findType(elt, scope).propagate(eltval);
      }
      return new Arr(eltval);
    }
```
</details>

### `ObjectExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.objType;
    }
```
</details>

### `FunctionExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.body.scope.fnType;
    }
```
</details>

### `SequenceExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.expressions[node.expressions.length-1], scope);
    }
```
</details>

### `UnaryExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(node) {
      return unopResultType(node.operator);
    }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
      return cx.num;
    }
```
</details>

### `BinaryExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`
- `findType`
- `lhs.hasType`
- `rhs.hasType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      if (binopIsBoolean(node.operator)) return cx.bool;
      if (node.operator == "+") {
        var lhs = findType(node.left, scope);
        var rhs = findType(node.right, scope);
        if (lhs.hasType(cx.str) || rhs.hasType(cx.str)) return cx.str;
      }
      return cx.num;
    }
```
</details>

### `AssignmentExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.right, scope);
    }
```
</details>

### `LogicalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.left, scope);
      return lhs.isEmpty() ? findType(node.right, scope) : lhs;
    }
```
</details>

### `ConditionalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.consequent, scope);
      return lhs.isEmpty() ? findType(node.alternate, scope) : lhs;
    }
```
</details>

### `NewExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `f.getProp("prototype").getObjType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      var proto = f && f.getProp("prototype").getObjType();
      if (!proto) return ANull;
      return getInstance(proto, f);
    }
```
</details>

### `CallExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `args.push`
- `findType`
- `f.computeRet`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      if (!f) return ANull;
      if (f.computeRet) {
        for (var i = 0, args = []; i < node.arguments.length; ++i)
          args.push(findType(node.arguments[i], scope));
        var self = ANull;
        if (node.callee.type == "MemberExpression")
          self = findType(node.callee.object, scope);
        return f.computeRet(self, args, node.arguments);
      } else {
        return f.retval;
      }
    }
```
</details>

### `MemberExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `propName`
- `findType(node.object, scope).getType`
- `obj.getProp`
- `findByPropertyName`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var propN = propName(node, scope), obj = findType(node.object, scope).getType();
      if (obj) return obj.getProp(propN);
      if (propN == "<i>") return ANull;
      return findByPropertyName(propN);
    }
```
</details>

### `Identifier(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `scope.hasProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return scope.hasProp(node.name) || ANull;
    }
```
</details>

### `ThisExpression(_node: any, scope: any): any`

**Parameters:**

- **`_node`** `any`
- **`scope`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(_node, scope) {
      return scope.fnType ? scope.fnType.self : cx.topScope;
    }
```
</details>

### `Literal(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `literalType`

<details><summary>Code</summary>

```typescript
function(node) {
      return literalType(node);
    }
```
</details>

### `ArrayExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(elt, scope).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var eltval = new AVal;
      for (var i = 0; i < node.elements.length; ++i) {
        var elt = node.elements[i];
        if (elt) findType(elt, scope).propagate(eltval);
      }
      return new Arr(eltval);
    }
```
</details>

### `ObjectExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.objType;
    }
```
</details>

### `FunctionExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.body.scope.fnType;
    }
```
</details>

### `SequenceExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.expressions[node.expressions.length-1], scope);
    }
```
</details>

### `UnaryExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(node) {
      return unopResultType(node.operator);
    }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
      return cx.num;
    }
```
</details>

### `BinaryExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`
- `findType`
- `lhs.hasType`
- `rhs.hasType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      if (binopIsBoolean(node.operator)) return cx.bool;
      if (node.operator == "+") {
        var lhs = findType(node.left, scope);
        var rhs = findType(node.right, scope);
        if (lhs.hasType(cx.str) || rhs.hasType(cx.str)) return cx.str;
      }
      return cx.num;
    }
```
</details>

### `AssignmentExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.right, scope);
    }
```
</details>

### `LogicalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.left, scope);
      return lhs.isEmpty() ? findType(node.right, scope) : lhs;
    }
```
</details>

### `ConditionalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.consequent, scope);
      return lhs.isEmpty() ? findType(node.alternate, scope) : lhs;
    }
```
</details>

### `NewExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `f.getProp("prototype").getObjType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      var proto = f && f.getProp("prototype").getObjType();
      if (!proto) return ANull;
      return getInstance(proto, f);
    }
```
</details>

### `CallExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `args.push`
- `findType`
- `f.computeRet`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      if (!f) return ANull;
      if (f.computeRet) {
        for (var i = 0, args = []; i < node.arguments.length; ++i)
          args.push(findType(node.arguments[i], scope));
        var self = ANull;
        if (node.callee.type == "MemberExpression")
          self = findType(node.callee.object, scope);
        return f.computeRet(self, args, node.arguments);
      } else {
        return f.retval;
      }
    }
```
</details>

### `MemberExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `propName`
- `findType(node.object, scope).getType`
- `obj.getProp`
- `findByPropertyName`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var propN = propName(node, scope), obj = findType(node.object, scope).getType();
      if (obj) return obj.getProp(propN);
      if (propN == "<i>") return ANull;
      return findByPropertyName(propN);
    }
```
</details>

### `Identifier(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `scope.hasProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return scope.hasProp(node.name) || ANull;
    }
```
</details>

### `ThisExpression(_node: any, scope: any): any`

**Parameters:**

- **`_node`** `any`
- **`scope`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(_node, scope) {
      return scope.fnType ? scope.fnType.self : cx.topScope;
    }
```
</details>

### `Literal(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `literalType`

<details><summary>Code</summary>

```typescript
function(node) {
      return literalType(node);
    }
```
</details>

### `ArrayExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(elt, scope).propagate`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var eltval = new AVal;
      for (var i = 0; i < node.elements.length; ++i) {
        var elt = node.elements[i];
        if (elt) findType(elt, scope).propagate(eltval);
      }
      return new Arr(eltval);
    }
```
</details>

### `ObjectExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.objType;
    }
```
</details>

### `FunctionExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(node) {
      return node.body.scope.fnType;
    }
```
</details>

### `SequenceExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.expressions[node.expressions.length-1], scope);
    }
```
</details>

### `UnaryExpression(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(node) {
      return unopResultType(node.operator);
    }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() {
      return cx.num;
    }
```
</details>

### `BinaryExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`
- `findType`
- `lhs.hasType`
- `rhs.hasType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      if (binopIsBoolean(node.operator)) return cx.bool;
      if (node.operator == "+") {
        var lhs = findType(node.left, scope);
        var rhs = findType(node.right, scope);
        if (lhs.hasType(cx.str) || rhs.hasType(cx.str)) return cx.str;
      }
      return cx.num;
    }
```
</details>

### `AssignmentExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return findType(node.right, scope);
    }
```
</details>

### `LogicalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.left, scope);
      return lhs.isEmpty() ? findType(node.right, scope) : lhs;
    }
```
</details>

### `ConditionalExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType`
- `lhs.isEmpty`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var lhs = findType(node.consequent, scope);
      return lhs.isEmpty() ? findType(node.alternate, scope) : lhs;
    }
```
</details>

### `NewExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `f.getProp("prototype").getObjType`
- `getInstance`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      var proto = f && f.getProp("prototype").getObjType();
      if (!proto) return ANull;
      return getInstance(proto, f);
    }
```
</details>

### `CallExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `findType(node.callee, scope).getFunctionType`
- `args.push`
- `findType`
- `f.computeRet`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var f = findType(node.callee, scope).getFunctionType();
      if (!f) return ANull;
      if (f.computeRet) {
        for (var i = 0, args = []; i < node.arguments.length; ++i)
          args.push(findType(node.arguments[i], scope));
        var self = ANull;
        if (node.callee.type == "MemberExpression")
          self = findType(node.callee.object, scope);
        return f.computeRet(self, args, node.arguments);
      } else {
        return f.retval;
      }
    }
```
</details>

### `MemberExpression(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `propName`
- `findType(node.object, scope).getType`
- `obj.getProp`
- `findByPropertyName`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      var propN = propName(node, scope), obj = findType(node.object, scope).getType();
      if (obj) return obj.getProp(propN);
      if (propN == "<i>") return ANull;
      return findByPropertyName(propN);
    }
```
</details>

### `Identifier(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `scope.hasProp`

<details><summary>Code</summary>

```typescript
function(node, scope) {
      return scope.hasProp(node.name) || ANull;
    }
```
</details>

### `ThisExpression(_node: any, scope: any): any`

**Parameters:**

- **`_node`** `any`
- **`scope`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(_node, scope) {
      return scope.fnType ? scope.fnType.self : cx.topScope;
    }
```
</details>

### `Literal(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `literalType`

<details><summary>Code</summary>

```typescript
function(node) {
      return literalType(node);
    }
```
</details>

### `findType(node: any, scope: any): any`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_49409`

<details><summary>Code</summary>

```typescript
function findType(node, scope) {
    return typeFinder[node.type](node, scope);
  }
```
</details>

### `Function(node: any, _st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`_st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, _st, c) {
      var scope = node.body.scope;
      if (node.id) c(node.id, scope);
      for (var i = 0; i < node.params.length; ++i)
        c(node.params[i], scope);
      c(node.body, scope, "ScopeBody");
    }
```
</details>

### `TryStatement(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `walk.base.TryStatement`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      if (node.handler)
        c(node.handler.param, st);
      walk.base.TryStatement(node, st, c);
    }
```
</details>

### `VariableDeclaration(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i];
        c(decl.id, st);
        if (decl.init) c(decl.init, st, "Expression");
      }
    }
```
</details>

### `Function(node: any, _st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`_st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, _st, c) {
      var scope = node.body.scope;
      if (node.id) c(node.id, scope);
      for (var i = 0; i < node.params.length; ++i)
        c(node.params[i], scope);
      c(node.body, scope, "ScopeBody");
    }
```
</details>

### `TryStatement(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `walk.base.TryStatement`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      if (node.handler)
        c(node.handler.param, st);
      walk.base.TryStatement(node, st, c);
    }
```
</details>

### `VariableDeclaration(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i];
        c(decl.id, st);
        if (decl.init) c(decl.init, st, "Expression");
      }
    }
```
</details>

### `Function(node: any, _st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`_st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, _st, c) {
      var scope = node.body.scope;
      if (node.id) c(node.id, scope);
      for (var i = 0; i < node.params.length; ++i)
        c(node.params[i], scope);
      c(node.body, scope, "ScopeBody");
    }
```
</details>

### `TryStatement(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `walk.base.TryStatement`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      if (node.handler)
        c(node.handler.param, st);
      walk.base.TryStatement(node, st, c);
    }
```
</details>

### `VariableDeclaration(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i];
        c(decl.id, st);
        if (decl.init) c(decl.init, st, "Expression");
      }
    }
```
</details>

### `Function(node: any, _st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`_st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, _st, c) {
      var scope = node.body.scope;
      if (node.id) c(node.id, scope);
      for (var i = 0; i < node.params.length; ++i)
        c(node.params[i], scope);
      c(node.body, scope, "ScopeBody");
    }
```
</details>

### `TryStatement(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`
- `walk.base.TryStatement`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      if (node.handler)
        c(node.handler.param, st);
      walk.base.TryStatement(node, st, c);
    }
```
</details>

### `VariableDeclaration(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      for (var i = 0; i < node.declarations.length; ++i) {
        var decl = node.declarations[i];
        c(decl.id, st);
        if (decl.init) c(decl.init, st, "Expression");
      }
    }
```
</details>

### `MemberExpression(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      c(node.object, st, "Expression");
      c(node.property, st, node.computed ? "Expression" : null);
    }
```
</details>

### `ObjectExpression(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      for (var i = 0; i < node.properties.length; ++i) {
        c(node.properties[i].value, st, "Expression");
        c(node.properties[i].key, st);
      }
    }
```
</details>

### `MemberExpression(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      c(node.object, st, "Expression");
      c(node.property, st, node.computed ? "Expression" : null);
    }
```
</details>

### `ObjectExpression(node: any, st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, st, c) {
      for (var i = 0; i < node.properties.length; ++i) {
        c(node.properties[i].value, st, "Expression");
        c(node.properties[i].key, st);
      }
    }
```
</details>

### `c(node: any, st: any, override: any): void`

**Parameters:**

- **`node`** `any`
- **`st`** `any`
- **`override`** `any`

**Returns:** `void`

**Calls:**

- `stack.push`
- `complex_call_51814`
- `stack.pop`

<details><summary>Code</summary>

```typescript
function c(node, st, override) {
      if (node.start <= child.start && node.end >= child.end) {
        var top = stack[stack.length - 1];
        if (node == child) throw {found: top};
        if (top != node) stack.push(node);
        walk.base[override || node.type](node, st, c);
        if (top != node) stack.pop();
      }
    }
```
</details>

### `ArrayExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true).getProp("<i>"); }
```
</details>

### `ObjectExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.properties.length; ++i) {
        var prop = node.properties[i];
        if (prop.value == node)
          return get(parent, true).getProp(prop.key.name);
      }
    }
```
</details>

### `UnaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(parent) { return unopResultType(parent.operator); }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return cx.num; }
```
</details>

### `BinaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`

<details><summary>Code</summary>

```typescript
function(parent) { return binopIsBoolean(parent.operator) ? cx.bool : cx.num; }
```
</details>

### `AssignmentExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent.left); }
```
</details>

### `LogicalExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true); }
```
</details>

### `ConditionalExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      if (parent.consequent == node || parent.alternate == node) return get(parent, true);
    }
```
</details>

### `NewExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `this.CallExpression`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      return this.CallExpression(parent, node, get);
    }
```
</details>

### `CallExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent.callee).getFunctionType`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.arguments.length; i++) {
        var arg = parent.arguments[i];
        if (arg == node) {
          var calleeType = get(parent.callee).getFunctionType();
          if (calleeType instanceof Fn)
            return calleeType.args[i];
          break;
        }
      }
    }
```
</details>

### `ReturnStatement(_parent: any, node: any, get: any): any`

**Parameters:**

- **`_parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `walk.findNodeAround`
- `get(fnNode.node, true).getFunctionType`
- `fnType.retval.getType`

<details><summary>Code</summary>

```typescript
function(_parent, node, get) {
      var fnNode = walk.findNodeAround(node.sourceFile.ast, node.start, "Function");
      if (fnNode) {
        var fnType = fnNode.node.type == "FunctionExpression"
          ? get(fnNode.node, true).getFunctionType()
          : fnNode.node.body.scope.fnType;
        if (fnType) return fnType.retval.getType();
      }
    }
```
</details>

### `VariableDeclaration(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.declarations.length; i++) {
        var decl = parent.declarations[i];
        if (decl.init == node) return get(decl.id);
      }
    }
```
</details>

### `ArrayExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true).getProp("<i>"); }
```
</details>

### `ObjectExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.properties.length; ++i) {
        var prop = node.properties[i];
        if (prop.value == node)
          return get(parent, true).getProp(prop.key.name);
      }
    }
```
</details>

### `UnaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(parent) { return unopResultType(parent.operator); }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return cx.num; }
```
</details>

### `BinaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`

<details><summary>Code</summary>

```typescript
function(parent) { return binopIsBoolean(parent.operator) ? cx.bool : cx.num; }
```
</details>

### `AssignmentExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent.left); }
```
</details>

### `LogicalExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true); }
```
</details>

### `ConditionalExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      if (parent.consequent == node || parent.alternate == node) return get(parent, true);
    }
```
</details>

### `NewExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `this.CallExpression`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      return this.CallExpression(parent, node, get);
    }
```
</details>

### `CallExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent.callee).getFunctionType`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.arguments.length; i++) {
        var arg = parent.arguments[i];
        if (arg == node) {
          var calleeType = get(parent.callee).getFunctionType();
          if (calleeType instanceof Fn)
            return calleeType.args[i];
          break;
        }
      }
    }
```
</details>

### `ReturnStatement(_parent: any, node: any, get: any): any`

**Parameters:**

- **`_parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `walk.findNodeAround`
- `get(fnNode.node, true).getFunctionType`
- `fnType.retval.getType`

<details><summary>Code</summary>

```typescript
function(_parent, node, get) {
      var fnNode = walk.findNodeAround(node.sourceFile.ast, node.start, "Function");
      if (fnNode) {
        var fnType = fnNode.node.type == "FunctionExpression"
          ? get(fnNode.node, true).getFunctionType()
          : fnNode.node.body.scope.fnType;
        if (fnType) return fnType.retval.getType();
      }
    }
```
</details>

### `VariableDeclaration(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.declarations.length; i++) {
        var decl = parent.declarations[i];
        if (decl.init == node) return get(decl.id);
      }
    }
```
</details>

### `ArrayExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true).getProp("<i>"); }
```
</details>

### `ObjectExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.properties.length; ++i) {
        var prop = node.properties[i];
        if (prop.value == node)
          return get(parent, true).getProp(prop.key.name);
      }
    }
```
</details>

### `UnaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(parent) { return unopResultType(parent.operator); }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return cx.num; }
```
</details>

### `BinaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`

<details><summary>Code</summary>

```typescript
function(parent) { return binopIsBoolean(parent.operator) ? cx.bool : cx.num; }
```
</details>

### `AssignmentExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent.left); }
```
</details>

### `LogicalExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true); }
```
</details>

### `ConditionalExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      if (parent.consequent == node || parent.alternate == node) return get(parent, true);
    }
```
</details>

### `NewExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `this.CallExpression`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      return this.CallExpression(parent, node, get);
    }
```
</details>

### `CallExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent.callee).getFunctionType`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.arguments.length; i++) {
        var arg = parent.arguments[i];
        if (arg == node) {
          var calleeType = get(parent.callee).getFunctionType();
          if (calleeType instanceof Fn)
            return calleeType.args[i];
          break;
        }
      }
    }
```
</details>

### `ReturnStatement(_parent: any, node: any, get: any): any`

**Parameters:**

- **`_parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `walk.findNodeAround`
- `get(fnNode.node, true).getFunctionType`
- `fnType.retval.getType`

<details><summary>Code</summary>

```typescript
function(_parent, node, get) {
      var fnNode = walk.findNodeAround(node.sourceFile.ast, node.start, "Function");
      if (fnNode) {
        var fnType = fnNode.node.type == "FunctionExpression"
          ? get(fnNode.node, true).getFunctionType()
          : fnNode.node.body.scope.fnType;
        if (fnType) return fnType.retval.getType();
      }
    }
```
</details>

### `VariableDeclaration(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.declarations.length; i++) {
        var decl = parent.declarations[i];
        if (decl.init == node) return get(decl.id);
      }
    }
```
</details>

### `ArrayExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true).getProp("<i>"); }
```
</details>

### `ObjectExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.properties.length; ++i) {
        var prop = node.properties[i];
        if (prop.value == node)
          return get(parent, true).getProp(prop.key.name);
      }
    }
```
</details>

### `UnaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(parent) { return unopResultType(parent.operator); }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return cx.num; }
```
</details>

### `BinaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`

<details><summary>Code</summary>

```typescript
function(parent) { return binopIsBoolean(parent.operator) ? cx.bool : cx.num; }
```
</details>

### `AssignmentExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent.left); }
```
</details>

### `LogicalExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true); }
```
</details>

### `ConditionalExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      if (parent.consequent == node || parent.alternate == node) return get(parent, true);
    }
```
</details>

### `NewExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `this.CallExpression`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      return this.CallExpression(parent, node, get);
    }
```
</details>

### `CallExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent.callee).getFunctionType`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.arguments.length; i++) {
        var arg = parent.arguments[i];
        if (arg == node) {
          var calleeType = get(parent.callee).getFunctionType();
          if (calleeType instanceof Fn)
            return calleeType.args[i];
          break;
        }
      }
    }
```
</details>

### `ReturnStatement(_parent: any, node: any, get: any): any`

**Parameters:**

- **`_parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `walk.findNodeAround`
- `get(fnNode.node, true).getFunctionType`
- `fnType.retval.getType`

<details><summary>Code</summary>

```typescript
function(_parent, node, get) {
      var fnNode = walk.findNodeAround(node.sourceFile.ast, node.start, "Function");
      if (fnNode) {
        var fnType = fnNode.node.type == "FunctionExpression"
          ? get(fnNode.node, true).getFunctionType()
          : fnNode.node.body.scope.fnType;
        if (fnType) return fnType.retval.getType();
      }
    }
```
</details>

### `VariableDeclaration(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.declarations.length; i++) {
        var decl = parent.declarations[i];
        if (decl.init == node) return get(decl.id);
      }
    }
```
</details>

### `ArrayExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true).getProp("<i>"); }
```
</details>

### `ObjectExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.properties.length; ++i) {
        var prop = node.properties[i];
        if (prop.value == node)
          return get(parent, true).getProp(prop.key.name);
      }
    }
```
</details>

### `UnaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(parent) { return unopResultType(parent.operator); }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return cx.num; }
```
</details>

### `BinaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`

<details><summary>Code</summary>

```typescript
function(parent) { return binopIsBoolean(parent.operator) ? cx.bool : cx.num; }
```
</details>

### `AssignmentExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent.left); }
```
</details>

### `LogicalExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true); }
```
</details>

### `ConditionalExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      if (parent.consequent == node || parent.alternate == node) return get(parent, true);
    }
```
</details>

### `NewExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `this.CallExpression`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      return this.CallExpression(parent, node, get);
    }
```
</details>

### `CallExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent.callee).getFunctionType`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.arguments.length; i++) {
        var arg = parent.arguments[i];
        if (arg == node) {
          var calleeType = get(parent.callee).getFunctionType();
          if (calleeType instanceof Fn)
            return calleeType.args[i];
          break;
        }
      }
    }
```
</details>

### `ReturnStatement(_parent: any, node: any, get: any): any`

**Parameters:**

- **`_parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `walk.findNodeAround`
- `get(fnNode.node, true).getFunctionType`
- `fnType.retval.getType`

<details><summary>Code</summary>

```typescript
function(_parent, node, get) {
      var fnNode = walk.findNodeAround(node.sourceFile.ast, node.start, "Function");
      if (fnNode) {
        var fnType = fnNode.node.type == "FunctionExpression"
          ? get(fnNode.node, true).getFunctionType()
          : fnNode.node.body.scope.fnType;
        if (fnType) return fnType.retval.getType();
      }
    }
```
</details>

### `VariableDeclaration(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.declarations.length; i++) {
        var decl = parent.declarations[i];
        if (decl.init == node) return get(decl.id);
      }
    }
```
</details>

### `ArrayExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true).getProp("<i>"); }
```
</details>

### `ObjectExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent, true).getProp`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.properties.length; ++i) {
        var prop = node.properties[i];
        if (prop.value == node)
          return get(parent, true).getProp(prop.key.name);
      }
    }
```
</details>

### `UnaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `unopResultType`

<details><summary>Code</summary>

```typescript
function(parent) { return unopResultType(parent.operator); }
```
</details>

### `UpdateExpression(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function() { return cx.num; }
```
</details>

### `BinaryExpression(parent: any): any`

**Parameters:**

- **`parent`** `any`

**Returns:** `any`

**Calls:**

- `binopIsBoolean`

<details><summary>Code</summary>

```typescript
function(parent) { return binopIsBoolean(parent.operator) ? cx.bool : cx.num; }
```
</details>

### `AssignmentExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent.left); }
```
</details>

### `LogicalExpression(parent: any, _: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`_`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, _, get) { return get(parent, true); }
```
</details>

### `ConditionalExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      if (parent.consequent == node || parent.alternate == node) return get(parent, true);
    }
```
</details>

### `NewExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `this.CallExpression`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      return this.CallExpression(parent, node, get);
    }
```
</details>

### `CallExpression(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get(parent.callee).getFunctionType`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.arguments.length; i++) {
        var arg = parent.arguments[i];
        if (arg == node) {
          var calleeType = get(parent.callee).getFunctionType();
          if (calleeType instanceof Fn)
            return calleeType.args[i];
          break;
        }
      }
    }
```
</details>

### `ReturnStatement(_parent: any, node: any, get: any): any`

**Parameters:**

- **`_parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `walk.findNodeAround`
- `get(fnNode.node, true).getFunctionType`
- `fnType.retval.getType`

<details><summary>Code</summary>

```typescript
function(_parent, node, get) {
      var fnNode = walk.findNodeAround(node.sourceFile.ast, node.start, "Function");
      if (fnNode) {
        var fnType = fnNode.node.type == "FunctionExpression"
          ? get(fnNode.node, true).getFunctionType()
          : fnNode.node.body.scope.fnType;
        if (fnType) return fnType.retval.getType();
      }
    }
```
</details>

### `VariableDeclaration(parent: any, node: any, get: any): any`

**Parameters:**

- **`parent`** `any`
- **`node`** `any`
- **`get`** `any`

**Returns:** `any`

**Calls:**

- `get`

<details><summary>Code</summary>

```typescript
function(parent, node, get) {
      for (var i = 0; i < parent.declarations.length; i++) {
        var decl = parent.declarations[i];
        if (decl.init == node) return get(decl.id);
      }
    }
```
</details>

### `Function(node: any, _st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`_st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, _st, c) { c(node.body, node.body.scope, "ScopeBody"); }
```
</details>

### `Function(node: any, _st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`_st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, _st, c) { c(node.body, node.body.scope, "ScopeBody"); }
```
</details>

### `Function(node: any, _st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`_st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, _st, c) { c(node.body, node.body.scope, "ScopeBody"); }
```
</details>

### `Function(node: any, _st: any, c: any): void`

**Parameters:**

- **`node`** `any`
- **`_st`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `c`

<details><summary>Code</summary>

```typescript
function(node, _st, c) { c(node.body, node.body.scope, "ScopeBody"); }
```
</details>

### `MemberExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `findType(node.object, scope).getType`
- `f`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.computed || node.property.name != propName) return;
        if (findType(node.object, scope).getType() == objType) f(node.property);
      }
```
</details>

### `ObjectExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `findType(node, scope).getType`
- `f`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (findType(node, scope).getType() != objType) return;
        for (var i = 0; i < node.properties.length; ++i)
          if (node.properties[i].key.name == propName) f(node.properties[i].key);
      }
```
</details>

### `MemberExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `findType(node.object, scope).getType`
- `f`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (node.computed || node.property.name != propName) return;
        if (findType(node.object, scope).getType() == objType) f(node.property);
      }
```
</details>

### `ObjectExpression(node: any, scope: any): void`

**Parameters:**

- **`node`** `any`
- **`scope`** `any`

**Returns:** `void`

**Calls:**

- `findType(node, scope).getType`
- `f`

<details><summary>Code</summary>

```typescript
function(node, scope) {
        if (findType(node, scope).getType() != objType) return;
        for (var i = 0; i < node.properties.length; ++i)
          if (node.properties[i].key.name == propName) f(node.properties[i].key);
      }
```
</details>


---