[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `basis_transcoder.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 351 |
| 🧱 Classes | 2 |
| 📊 Variables & Constants | 220 |
| ⚡ Async/Await Patterns | 4 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/libs/basis/basis_transcoder.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_scriptName` | `any` | let/var | `typeof document != 'undefined' ? document.currentScript?.src : undefined` | ✗ |
| `moduleRtn` | `any` | let/var | `*not shown*` | ✗ |
| `Module` | `{}` | let/var | `moduleArg` | ✗ |
| `readyPromiseResolve` | `any` | let/var | `*not shown*` | ✗ |
| `readyPromiseReject` | `any` | let/var | `*not shown*` | ✗ |
| `readyPromise` | `Promise<any>` | let/var | `new Promise((resolve,reject)=>{readyPromiseResolve=resolve;readyPromiseReject...` | ✗ |
| `ENVIRONMENT_IS_WEB` | `boolean` | let/var | `typeof window=="object"` | ✗ |
| `ENVIRONMENT_IS_WORKER` | `boolean` | let/var | `typeof importScripts=="function"` | ✗ |
| `ENVIRONMENT_IS_NODE` | `boolean` | let/var | `typeof process=="object"&&typeof process.versions=="object"&&typeof process.v...` | ✗ |
| `arguments_` | `any[]` | let/var | `[]` | ✗ |
| `thisProgram` | `string` | let/var | `"./this.program"` | ✗ |
| `scriptDirectory` | `string` | let/var | `""` | ✗ |
| `readAsync` | `any` | let/var | `*not shown*` | ✗ |
| `readBinary` | `any` | let/var | `*not shown*` | ✗ |
| `xhr` | `XMLHttpRequest` | let/var | `new XMLHttpRequest` | ✗ |
| `xhr` | `XMLHttpRequest` | let/var | `new XMLHttpRequest` | ✗ |
| `out` | `any` | let/var | `Module["print"]\|\|console.log.bind(console)` | ✗ |
| `err` | `any` | let/var | `Module["printErr"]\|\|console.error.bind(console)` | ✗ |
| `wasmBinary` | `any` | let/var | `*not shown*` | ✗ |
| `wasmMemory` | `any` | let/var | `*not shown*` | ✗ |
| `ABORT` | `boolean` | let/var | `false` | ✗ |
| `EXITSTATUS` | `any` | let/var | `*not shown*` | ✗ |
| `HEAP8` | `any` | let/var | `*not shown*` | ✗ |
| `HEAPU8` | `any` | let/var | `*not shown*` | ✗ |
| `HEAP16` | `any` | let/var | `*not shown*` | ✗ |
| `HEAPU16` | `any` | let/var | `*not shown*` | ✗ |
| `HEAP32` | `any` | let/var | `*not shown*` | ✗ |
| `HEAPU32` | `any` | let/var | `*not shown*` | ✗ |
| `HEAPF32` | `any` | let/var | `*not shown*` | ✗ |
| `HEAPF64` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `any` | let/var | `wasmMemory.buffer` | ✗ |
| `__ATPRERUN__` | `any[]` | let/var | `[]` | ✗ |
| `__ATINIT__` | `any[]` | let/var | `[]` | ✗ |
| `__ATPOSTRUN__` | `any[]` | let/var | `[]` | ✗ |
| `runtimeInitialized` | `boolean` | let/var | `false` | ✗ |
| `runDependencies` | `number` | let/var | `0` | ✗ |
| `runDependencyWatcher` | `any` | let/var | `null` | ✗ |
| `dependenciesFulfilled` | `any` | let/var | `null` | ✗ |
| `callback` | `any` | let/var | `dependenciesFulfilled` | ✗ |
| `e` | `RuntimeError` | let/var | `new WebAssembly.RuntimeError(what)` | ✗ |
| `dataURIPrefix` | `string` | let/var | `"data:application/octet-stream;base64,"` | ✗ |
| `f` | `string` | let/var | `"basis_transcoder.wasm"` | ✗ |
| `wasmBinaryFile` | `any` | let/var | `*not shown*` | ✗ |
| `noExitRuntime` | `any` | let/var | `Module["noExitRuntime"]\|\|true` | ✗ |
| `exceptionLast` | `number` | let/var | `0` | ✗ |
| `uncaughtExceptionCount` | `number` | let/var | `0` | ✗ |
| `info` | `ExceptionInfo` | let/var | `new ExceptionInfo(ptr)` | ✗ |
| `structRegistrations` | `{}` | let/var | `{}` | ✗ |
| `awaitingDependencies` | `{}` | let/var | `{}` | ✗ |
| `registeredTypes` | `{}` | let/var | `{}` | ✗ |
| `typeDependencies` | `{}` | let/var | `{}` | ✗ |
| `InternalError` | `any` | let/var | `*not shown*` | ✗ |
| `typeConverters` | `any[]` | let/var | `new Array(dependentTypes.length)` | ✗ |
| `unregisteredTypes` | `any[]` | let/var | `[]` | ✗ |
| `registered` | `number` | let/var | `0` | ✗ |
| `reg` | `any` | let/var | `structRegistrations[structType]` | ✗ |
| `rawConstructor` | `any` | let/var | `reg.rawConstructor` | ✗ |
| `rawDestructor` | `any` | let/var | `reg.rawDestructor` | ✗ |
| `fieldRecords` | `any` | let/var | `reg.fields` | ✗ |
| `fields` | `{}` | let/var | `{}` | ✗ |
| `fieldName` | `any` | let/var | `field.fieldName` | ✗ |
| `getterReturnType` | `any` | let/var | `fieldTypes[i]` | ✗ |
| `getter` | `any` | let/var | `field.getter` | ✗ |
| `getterContext` | `any` | let/var | `field.getterContext` | ✗ |
| `setterArgumentType` | `any` | let/var | `fieldTypes[i+fieldRecords.length]` | ✗ |
| `setter` | `any` | let/var | `field.setter` | ✗ |
| `setterContext` | `any` | let/var | `field.setterContext` | ✗ |
| `destructors` | `any[]` | let/var | `[]` | ✗ |
| `rv` | `{}` | let/var | `{}` | ✗ |
| `codes` | `any[]` | let/var | `new Array(256)` | ✗ |
| `embind_charCodes` | `any` | let/var | `*not shown*` | ✗ |
| `ret` | `string` | let/var | `""` | ✗ |
| `c` | `any` | let/var | `ptr` | ✗ |
| `BindingError` | `any` | let/var | `*not shown*` | ✗ |
| `name` | `any` | let/var | `registeredInstance.name` | ✗ |
| `callbacks` | `any` | let/var | `awaitingDependencies[rawType]` | ✗ |
| `GenericWireTypeSize` | `number` | let/var | `8` | ✗ |
| `finalizationRegistry` | `boolean` | let/var | `false` | ✗ |
| `toDelete` | `boolean` | let/var | `0===$$.count.value` | ✗ |
| `registeredPointers` | `{}` | let/var | `{}` | ✗ |
| `rv` | `any[]` | let/var | `[]` | ✗ |
| `deletionQueue` | `any[]` | let/var | `[]` | ✗ |
| `delayFunction` | `any` | let/var | `*not shown*` | ✗ |
| `registeredInstances` | `{}` | let/var | `{}` | ✗ |
| `hasSmartPtrType` | `boolean` | let/var | `!!record.smartPtrType` | ✗ |
| `hasSmartPtr` | `boolean` | let/var | `!!record.smartPtr` | ✗ |
| `registeredPointerRecord` | `any` | let/var | `registeredPointers[actualType]` | ✗ |
| `toType` | `any` | let/var | `*not shown*` | ✗ |
| `$$` | `any` | let/var | `handle.$$` | ✗ |
| `hasSmartPtr` | `boolean` | let/var | `!!$$.smartPtr` | ✗ |
| `info` | `{ $$: any; }` | let/var | `{$$:$$}` | ✗ |
| `leftClass` | `any` | let/var | `this.$$.ptrType.registeredClass` | ✗ |
| `left` | `any` | let/var | `this.$$.ptr` | ✗ |
| `rightClass` | `any` | let/var | `other.$$.ptrType.registeredClass` | ✗ |
| `right` | `any` | let/var | `other.$$.ptr` | ✗ |
| `prevFunc` | `any` | let/var | `proto[methodName]` | ✗ |
| `char_0` | `number` | let/var | `48` | ✗ |
| `char_9` | `number` | let/var | `57` | ✗ |
| `handleClass` | `any` | let/var | `handle.$$.ptrType.registeredClass` | ✗ |
| `ptr` | `any` | let/var | `*not shown*` | ✗ |
| `handleClass` | `any` | let/var | `handle.$$.ptrType.registeredClass` | ✗ |
| `handleClass` | `any` | let/var | `handle.$$.ptrType.registeredClass` | ✗ |
| `f` | `any` | let/var | `Module["dynCall_"+sig]` | ✗ |
| `wasmTableMirror` | `any[]` | let/var | `[]` | ✗ |
| `wasmTable` | `any` | let/var | `*not shown*` | ✗ |
| `func` | `any` | let/var | `wasmTableMirror[funcPtr]` | ✗ |
| `stack` | `string` | let/var | `new Error(message).stack` | ✗ |
| `UnboundTypeError` | `any` | let/var | `*not shown*` | ✗ |
| `unboundTypes` | `any[]` | let/var | `[]` | ✗ |
| `seen` | `{}` | let/var | `{}` | ✗ |
| `baseClass` | `any` | let/var | `*not shown*` | ✗ |
| `basePrototype` | `any` | let/var | `*not shown*` | ✗ |
| `body` | `any` | let/var | `registeredClass.constructor_body[args.length]` | ✗ |
| `registeredClass` | `RegisteredClass` | let/var | `new RegisteredClass(name,constructor,instancePrototype,rawDestructor,baseClas...` | ✗ |
| `referenceConverter` | `RegisteredPointer` | let/var | `new RegisteredPointer(name,registeredClass,true,false,false)` | ✗ |
| `pointerConverter` | `RegisteredPointer` | let/var | `new RegisteredPointer(name+"*",registeredClass,false,false,false)` | ✗ |
| `constPointerConverter` | `RegisteredPointer` | let/var | `new RegisteredPointer(name+" const*",registeredClass,false,true,false)` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `obj` | `any` | let/var | `new dummy` | ✗ |
| `argCount` | `any` | let/var | `argTypes.length` | ✗ |
| `argsList` | `string` | let/var | `""` | ✗ |
| `argsListWired` | `string` | let/var | `""` | ✗ |
| `invokerFnBody` | `string` | let/var | ``\n return function (${argsList}) {\n if (arguments.length !== ${argCount-2})...` | ✗ |
| `dtorStack` | `string` | let/var | `needsDestructorStack?"destructors":"null"` | ✗ |
| `args1` | `string[]` | let/var | `["humanName","throwBindingError","invoker","fn","runDestructors","retType","c...` | ✗ |
| `paramName` | `string` | let/var | `i===1?"thisWired":"arg"+(i-2)+"Wired"` | ✗ |
| `argCount` | `any` | let/var | `argTypes.length` | ✗ |
| `isClassMethodFunc` | `boolean` | let/var | `argTypes[1]!==null&&classType!==null` | ✗ |
| `returns` | `boolean` | let/var | `argTypes[0].name!=="void"` | ✗ |
| `closureArgs` | `any[]` | let/var | `[humanName,throwBindingError,cppInvokerFunc,cppTargetFunc,runDestructors,argT...` | ✗ |
| `humanName` | `string` | let/var | ``constructor ${classType.name}`` | ✗ |
| `humanName` | `string` | let/var | ``${classType.name}.${methodName}`` | ✗ |
| `proto` | `any` | let/var | `classType.registeredClass.instancePrototype` | ✗ |
| `method` | `any` | let/var | `proto[methodName]` | ✗ |
| `emval_freelist` | `any[]` | let/var | `[]` | ✗ |
| `emval_handles` | `any[]` | let/var | `[]` | ✗ |
| `handle` | `any` | let/var | `emval_freelist.pop()\|\|emval_handles.length` | ✗ |
| `Emval` | `{ toValue: (handle: any) => any; toHa...` | let/var | `{toValue:handle=>{if(!handle){throwBindingError("Cannot use deleted val. hand...` | ✗ |
| `EmValType` | `{ name: string; fromWireType: (handle...` | let/var | `{name:"emscripten::val",fromWireType:handle=>{var rv=Emval.toValue(handle);__...` | ✗ |
| `impl` | `any` | let/var | `registeredTypes[rawType]` | ✗ |
| `Enum` | `any` | let/var | `enumType.constructor` | ✗ |
| `t` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof v` | ✗ |
| `bitshift` | `number` | let/var | `32-8*size` | ✗ |
| `toWireType` | `any` | let/var | `*not shown*` | ✗ |
| `typeMapping` | `(Int8ArrayConstructor \| Uint8ArrayCo...` | let/var | `[Int8Array,Uint8Array,Int16Array,Uint16Array,Int32Array,Uint32Array,Float32Ar...` | ✗ |
| `TA` | `Int8ArrayConstructor \| Uint8ArrayCon...` | let/var | `typeMapping[dataTypeIndex]` | ✗ |
| `size` | `any` | let/var | `HEAPU32[handle>>2]` | ✗ |
| `data` | `any` | let/var | `HEAPU32[handle+4>>2]` | ✗ |
| `startIdx` | `any` | let/var | `outIdx` | ✗ |
| `endIdx` | `number` | let/var | `outIdx+maxBytesToWrite-1` | ✗ |
| `len` | `number` | let/var | `0` | ✗ |
| `UTF8Decoder` | `TextDecoder` | let/var | `typeof TextDecoder!="undefined"?new TextDecoder:undefined` | ✗ |
| `endIdx` | `any` | let/var | `idx+maxBytesToRead` | ✗ |
| `endPtr` | `any` | let/var | `idx` | ✗ |
| `str` | `string` | let/var | `""` | ✗ |
| `u0` | `any` | let/var | `heapOrArray[idx++]` | ✗ |
| `u1` | `number` | let/var | `heapOrArray[idx++]&63` | ✗ |
| `u2` | `number` | let/var | `heapOrArray[idx++]&63` | ✗ |
| `ch` | `number` | let/var | `u0-65536` | ✗ |
| `stdStringIsUTF8` | `boolean` | let/var | `name==="std::string"` | ✗ |
| `length` | `any` | let/var | `HEAPU32[value>>2]` | ✗ |
| `payload` | `any` | let/var | `value+4` | ✗ |
| `str` | `any` | let/var | `*not shown*` | ✗ |
| `decodeStartPtr` | `any` | let/var | `payload` | ✗ |
| `currentBytePtr` | `any` | let/var | `payload+i` | ✗ |
| `maxRead` | `number` | let/var | `currentBytePtr-decodeStartPtr` | ✗ |
| `a` | `any[]` | let/var | `new Array(length)` | ✗ |
| `length` | `any` | let/var | `*not shown*` | ✗ |
| `valueIsOfTypeString` | `boolean` | let/var | `typeof value=="string"` | ✗ |
| `ptr` | `any` | let/var | `base+4` | ✗ |
| `UTF16Decoder` | `TextDecoder` | let/var | `typeof TextDecoder!="undefined"?new TextDecoder("utf-16le"):undefined` | ✗ |
| `endPtr` | `any` | let/var | `ptr` | ✗ |
| `idx` | `number` | let/var | `endPtr>>1` | ✗ |
| `maxIdx` | `number` | let/var | `idx+maxBytesToRead/2` | ✗ |
| `str` | `string` | let/var | `""` | ✗ |
| `codeUnit` | `any` | let/var | `HEAP16[ptr+i*2>>1]` | ✗ |
| `startPtr` | `any` | let/var | `outPtr` | ✗ |
| `numCharsToWrite` | `any` | let/var | `maxBytesToWrite<str.length*2?maxBytesToWrite/2:str.length` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `str` | `string` | let/var | `""` | ✗ |
| `utf32` | `any` | let/var | `HEAP32[ptr+i*4>>2]` | ✗ |
| `ch` | `number` | let/var | `utf32-65536` | ✗ |
| `startPtr` | `any` | let/var | `outPtr` | ✗ |
| `endPtr` | `number` | let/var | `startPtr+maxBytesToWrite-4` | ✗ |
| `len` | `number` | let/var | `0` | ✗ |
| `decodeString` | `any` | let/var | `*not shown*` | ✗ |
| `encodeString` | `any` | let/var | `*not shown*` | ✗ |
| `readCharAt` | `any` | let/var | `*not shown*` | ✗ |
| `lengthBytesUTF` | `any` | let/var | `*not shown*` | ✗ |
| `length` | `any` | let/var | `HEAPU32[value>>2]` | ✗ |
| `str` | `any` | let/var | `*not shown*` | ✗ |
| `decodeStartPtr` | `any` | let/var | `value+4` | ✗ |
| `currentBytePtr` | `any` | let/var | `value+4+i*charSize` | ✗ |
| `maxReadBytes` | `number` | let/var | `currentBytePtr-decodeStartPtr` | ✗ |
| `destructors` | `any[]` | let/var | `[]` | ✗ |
| `emval_methodCallers` | `any[]` | let/var | `[]` | ✗ |
| `emval_symbols` | `{}` | let/var | `{}` | ✗ |
| `symbol` | `any` | let/var | `emval_symbols[address]` | ✗ |
| `id` | `number` | let/var | `emval_methodCallers.length` | ✗ |
| `a` | `any[]` | let/var | `new Array(argCount)` | ✗ |
| `reflectConstruct` | `{ <A extends readonly any[], R>(targe...` | let/var | `Reflect.construct` | ✗ |
| `functionBody` | `string` | let/var | ``return function (obj, func, destructorsRef, args) {\n`` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `argsList` | `any[]` | let/var | `[]` | ✗ |
| `params` | `string[]` | let/var | `["retType"]` | ✗ |
| `args` | `any[]` | let/var | `[retType]` | ✗ |
| `invoker` | `string` | let/var | `kind===1?"new func":"func.call"` | ✗ |
| `functionName` | `string` | let/var | ``methodCaller<(${types.map(t=>t.name).join(", ")}) => ${retType.name}>`` | ✗ |
| `b` | `any` | let/var | `wasmMemory.buffer` | ✗ |
| `pages` | `number` | let/var | `(size-b.byteLength+65535)/65536` | ✗ |
| `oldSize` | `any` | let/var | `HEAPU8.length` | ✗ |
| `overGrownHeapSize` | `number` | let/var | `oldSize*(1+.2/cutDown)` | ✗ |
| `printCharBuffers` | `any[][]` | let/var | `[null,[],[]]` | ✗ |
| `buffer` | `any[]` | let/var | `printCharBuffers[stream]` | ✗ |
| `num` | `number` | let/var | `0` | ✗ |
| `ptr` | `any` | let/var | `HEAPU32[iov>>2]` | ✗ |
| `len` | `any` | let/var | `HEAPU32[iov+4>>2]` | ✗ |
| `wasmImports` | `{ K: (ptr: any, type: any, destructor...` | let/var | `{K:___cxa_throw,G:__abort_js,s:__embind_finalize_value_object,C:__embind_regi...` | ✗ |
| `dynCall_jiji` | `(a0: any, a1: any, a2: any, a3: any, ...` | let/var | `Module["dynCall_jiji"]=(a0,a1,a2,a3,a4)=>(dynCall_jiji=Module["dynCall_jiji"]...` | ✗ |
| `calledRun` | `any` | let/var | `*not shown*` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `getBinaryPromise` | *none* | readAsync(binaryFile).then, Promise.resolve().then, Promise.resolve |
| promise-chain | `instantiateArrayBuffer` | *none* | getBinaryPromise(binaryFile).then(binary=>WebAssembly.instantiate(binary,imports)).then, getBinaryPromise(binaryFile).then |
| promise-chain | `instantiateAsync` | *none* | fetch(binaryFile,{credentials:"same-origin"}).then, result.then |
| promise-chain | `createWasm` | *none* | instantiateAsync(wasmBinary,wasmBinaryFile,info,receiveInstantiationResult).catch |


---

## Functions

### `quit_(status: any, toThrow: any): never`

**Parameters:**

- **`status`** `any`
- **`toThrow`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
(status,toThrow)=>{throw toThrow}
```
</details>

### `locateFile(path: any): any`

**Parameters:**

- **`path`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_884`

<details><summary>Code</summary>

```typescript
function locateFile(path){if(Module["locateFile"]){return Module["locateFile"](path,scriptDirectory)}return scriptDirectory+path}
```
</details>

### `updateMemoryViews(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function updateMemoryViews(){var b=wasmMemory.buffer;Module["HEAP8"]=HEAP8=new Int8Array(b);Module["HEAP16"]=HEAP16=new Int16Array(b);Module["HEAPU8"]=HEAPU8=new Uint8Array(b);Module["HEAPU16"]=HEAPU16=new Uint16Array(b);Module["HEAP32"]=HEAP32=new Int32Array(b);Module["HEAPU32"]=HEAPU32=new Uint32Array(b);Module["HEAPF32"]=HEAPF32=new Float32Array(b);Module["HEAPF64"]=HEAPF64=new Float64Array(b)}
```
</details>

### `preRun(): void`

**Returns:** `void`

**Calls:**

- `addOnPreRun`
- `Module["preRun"].shift`
- `callRuntimeCallbacks`

<details><summary>Code</summary>

```typescript
function preRun(){if(Module["preRun"]){if(typeof Module["preRun"]=="function")Module["preRun"]=[Module["preRun"]];while(Module["preRun"].length){addOnPreRun(Module["preRun"].shift())}}callRuntimeCallbacks(__ATPRERUN__)}
```
</details>

### `initRuntime(): void`

**Returns:** `void`

**Calls:**

- `callRuntimeCallbacks`

<details><summary>Code</summary>

```typescript
function initRuntime(){runtimeInitialized=true;callRuntimeCallbacks(__ATINIT__)}
```
</details>

### `postRun(): void`

**Returns:** `void`

**Calls:**

- `addOnPostRun`
- `Module["postRun"].shift`
- `callRuntimeCallbacks`

<details><summary>Code</summary>

```typescript
function postRun(){if(Module["postRun"]){if(typeof Module["postRun"]=="function")Module["postRun"]=[Module["postRun"]];while(Module["postRun"].length){addOnPostRun(Module["postRun"].shift())}}callRuntimeCallbacks(__ATPOSTRUN__)}
```
</details>

### `addOnPreRun(cb: any): void`

**Parameters:**

- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `__ATPRERUN__.unshift`

<details><summary>Code</summary>

```typescript
function addOnPreRun(cb){__ATPRERUN__.unshift(cb)}
```
</details>

### `addOnInit(cb: any): void`

**Parameters:**

- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `__ATINIT__.unshift`

<details><summary>Code</summary>

```typescript
function addOnInit(cb){__ATINIT__.unshift(cb)}
```
</details>

### `addOnPostRun(cb: any): void`

**Parameters:**

- **`cb`** `any`

**Returns:** `void`

**Calls:**

- `__ATPOSTRUN__.unshift`

<details><summary>Code</summary>

```typescript
function addOnPostRun(cb){__ATPOSTRUN__.unshift(cb)}
```
</details>

### `addRunDependency(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_4572`

<details><summary>Code</summary>

```typescript
function addRunDependency(id){runDependencies++;Module["monitorRunDependencies"]?.(runDependencies)}
```
</details>

### `removeRunDependency(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_4675`
- `clearInterval`
- `callback`

<details><summary>Code</summary>

```typescript
function removeRunDependency(id){runDependencies--;Module["monitorRunDependencies"]?.(runDependencies);if(runDependencies==0){if(runDependencyWatcher!==null){clearInterval(runDependencyWatcher);runDependencyWatcher=null}if(dependenciesFulfilled){var callback=dependenciesFulfilled;dependenciesFulfilled=null;callback()}}}
```
</details>

### `abort(what: any): void`

**Parameters:**

- **`what`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_4966`
- `err`
- `readyPromiseReject`

<details><summary>Code</summary>

```typescript
function abort(what){Module["onAbort"]?.(what);what="Aborted("+what+")";err(what);ABORT=true;EXITSTATUS=1;what+=". Build with -sASSERTIONS for more info.";var e=new WebAssembly.RuntimeError(what);readyPromiseReject(e);throw e}
```
</details>

### `isDataURI(filename: any): any`

**Parameters:**

- **`filename`** `any`

**Returns:** `any`

**Calls:**

- `filename.startsWith`

<details><summary>Code</summary>

```typescript
filename=>filename.startsWith(dataURIPrefix)
```
</details>

### `isFileURI(filename: any): any`

**Parameters:**

- **`filename`** `any`

**Returns:** `any`

**Calls:**

- `filename.startsWith`

<details><summary>Code</summary>

```typescript
filename=>filename.startsWith("file://")
```
</details>

### `findWasmBinary(): any`

**Returns:** `any`

**Calls:**

- `isDataURI`
- `locateFile`

<details><summary>Code</summary>

```typescript
function findWasmBinary(){var f="basis_transcoder.wasm";if(!isDataURI(f)){return locateFile(f)}return f}
```
</details>

### `getBinarySync(file: any): any`

**Parameters:**

- **`file`** `any`

**Returns:** `any`

**Calls:**

- `readBinary`

<details><summary>Code</summary>

```typescript
function getBinarySync(file){if(file==wasmBinaryFile&&wasmBinary){return new Uint8Array(wasmBinary)}if(readBinary){return readBinary(file)}throw"both async and sync fetching of the wasm failed"}
```
</details>

### `getBinaryPromise(binaryFile: any): any`

**Parameters:**

- **`binaryFile`** `any`

**Returns:** `any`

**Calls:**

- `readAsync(binaryFile).then`
- `getBinarySync`
- `Promise.resolve().then`

<details><summary>Code</summary>

```typescript
function getBinaryPromise(binaryFile){if(!wasmBinary){return readAsync(binaryFile).then(response=>new Uint8Array(response),()=>getBinarySync(binaryFile))}return Promise.resolve().then(()=>getBinarySync(binaryFile))}
```
</details>

### `instantiateArrayBuffer(binaryFile: any, imports: any, receiver: any): any`

**Parameters:**

- **`binaryFile`** `any`
- **`imports`** `any`
- **`receiver`** `any`

**Returns:** `any`

**Calls:**

- `getBinaryPromise(binaryFile).then(binary=>WebAssembly.instantiate(binary,imports)).then`
- `err`
- `abort`

<details><summary>Code</summary>

```typescript
function instantiateArrayBuffer(binaryFile,imports,receiver){return getBinaryPromise(binaryFile).then(binary=>WebAssembly.instantiate(binary,imports)).then(receiver,reason=>{err(`failed to asynchronously prepare wasm: ${reason}`);abort(reason)})}
```
</details>

### `instantiateAsync(binary: any, binaryFile: any, imports: any, callback: any): any`

**Parameters:**

- **`binary`** `any`
- **`binaryFile`** `any`
- **`imports`** `any`
- **`callback`** `any`

**Returns:** `any`

**Calls:**

- `isDataURI`
- `isFileURI`
- `fetch(binaryFile,{credentials:"same-origin"}).then`
- `WebAssembly.instantiateStreaming`
- `result.then`
- `err`
- `instantiateArrayBuffer`

<details><summary>Code</summary>

```typescript
function instantiateAsync(binary,binaryFile,imports,callback){if(!binary&&typeof WebAssembly.instantiateStreaming=="function"&&!isDataURI(binaryFile)&&!isFileURI(binaryFile)&&!ENVIRONMENT_IS_NODE&&typeof fetch=="function"){return fetch(binaryFile,{credentials:"same-origin"}).then(response=>{var result=WebAssembly.instantiateStreaming(response,imports);return result.then(callback,function(reason){err(`wasm streaming compile failed: ${reason}`);err("falling back to ArrayBuffer instantiation");return instantiateArrayBuffer(binaryFile,imports,callback)})})}return instantiateArrayBuffer(binaryFile,imports,callback)}
```
</details>

### `getWasmImports(): { a: { K: (ptr: any, type: any, destructor: any) => never; G: () => void; s: (structType: any) => void; C: (primitiveType: any, name: any, size: any, minRange: any, maxRange: any) => void; I: (rawType: any, name: any, trueValue: any, falseValue: any) => void; ... 31 more ...; y: (fd: any, iov: any, iovcnt: any, pnum...`

**Returns:** `{ a: { K: (ptr: any, type: any, destructor: any) => never; G: () => void; s: (structType: any) => void; C: (primitiveType: any, name: any, size: any, minRange: any, maxRange: any) => void; I: (rawType: any, name: any, trueValue: any, falseValue: any) => void; ... 31 more ...; y: (fd: any, iov: any, iovcnt: any, pnum...`

<details><summary>Code</summary>

```typescript
function getWasmImports(){return{a:wasmImports}}
```
</details>

### `createWasm(): any`

**Returns:** `any`

**Calls:**

- `getWasmImports`
- `updateMemoryViews`
- `addOnInit`
- `removeRunDependency`
- `addRunDependency`
- `receiveInstance`
- `complex_call_7226`
- `err`
- `readyPromiseReject`
- `findWasmBinary`
- `instantiateAsync(wasmBinary,wasmBinaryFile,info,receiveInstantiationResult).catch`

<details><summary>Code</summary>

```typescript
function createWasm(){var info=getWasmImports();function receiveInstance(instance,module){wasmExports=instance.exports;wasmMemory=wasmExports["L"];updateMemoryViews();wasmTable=wasmExports["P"];addOnInit(wasmExports["M"]);removeRunDependency("wasm-instantiate");return wasmExports}addRunDependency("wasm-instantiate");function receiveInstantiationResult(result){receiveInstance(result["instance"])}if(Module["instantiateWasm"]){try{return Module["instantiateWasm"](info,receiveInstance)}catch(e){err(`Module.instantiateWasm callback failed with error: ${e}`);readyPromiseReject(e)}}if(!wasmBinaryFile)wasmBinaryFile=findWasmBinary();instantiateAsync(wasmBinary,wasmBinaryFile,info,receiveInstantiationResult).catch(readyPromiseReject);return{}}
```
</details>

### `receiveInstance(instance: any, module: any): any`

**Parameters:**

- **`instance`** `any`
- **`module`** `any`

**Returns:** `any`

**Calls:**

- `updateMemoryViews`
- `addOnInit`
- `removeRunDependency`

<details><summary>Code</summary>

```typescript
function receiveInstance(instance,module){wasmExports=instance.exports;wasmMemory=wasmExports["L"];updateMemoryViews();wasmTable=wasmExports["P"];addOnInit(wasmExports["M"]);removeRunDependency("wasm-instantiate");return wasmExports}
```
</details>

### `receiveInstantiationResult(result: any): void`

**Parameters:**

- **`result`** `any`

**Returns:** `void`

**Calls:**

- `receiveInstance`

<details><summary>Code</summary>

```typescript
function receiveInstantiationResult(result){receiveInstance(result["instance"])}
```
</details>

### `callRuntimeCallbacks(callbacks: any): void`

**Parameters:**

- **`callbacks`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_7594`

<details><summary>Code</summary>

```typescript
callbacks=>{while(callbacks.length>0){callbacks.shift()(Module)}}
```
</details>

### `ExceptionInfo.set_type(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_type(type){HEAPU32[this.ptr+4>>2]=type}
```
</details>

### `ExceptionInfo.get_type(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
get_type(){return HEAPU32[this.ptr+4>>2]}
```
</details>

### `ExceptionInfo.set_destructor(destructor: any): void`

**Parameters:**

- **`destructor`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_destructor(destructor){HEAPU32[this.ptr+8>>2]=destructor}
```
</details>

### `ExceptionInfo.get_destructor(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
get_destructor(){return HEAPU32[this.ptr+8>>2]}
```
</details>

### `ExceptionInfo.set_caught(caught: any): void`

**Parameters:**

- **`caught`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_caught(caught){caught=caught?1:0;HEAP8[this.ptr+12]=caught}
```
</details>

### `ExceptionInfo.get_caught(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
get_caught(){return HEAP8[this.ptr+12]!=0}
```
</details>

### `ExceptionInfo.set_rethrown(rethrown: any): void`

**Parameters:**

- **`rethrown`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_rethrown(rethrown){rethrown=rethrown?1:0;HEAP8[this.ptr+13]=rethrown}
```
</details>

### `ExceptionInfo.get_rethrown(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
get_rethrown(){return HEAP8[this.ptr+13]!=0}
```
</details>

### `ExceptionInfo.init(type: any, destructor: any): void`

**Parameters:**

- **`type`** `any`
- **`destructor`** `any`

**Returns:** `void`

**Calls:**

- `this.set_adjusted_ptr`
- `this.set_type`
- `this.set_destructor`

<details><summary>Code</summary>

```typescript
init(type,destructor){this.set_adjusted_ptr(0);this.set_type(type);this.set_destructor(destructor)}
```
</details>

### `ExceptionInfo.set_adjusted_ptr(adjustedPtr: any): void`

**Parameters:**

- **`adjustedPtr`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_adjusted_ptr(adjustedPtr){HEAPU32[this.ptr+16>>2]=adjustedPtr}
```
</details>

### `ExceptionInfo.get_adjusted_ptr(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
get_adjusted_ptr(){return HEAPU32[this.ptr+16>>2]}
```
</details>

### `ExceptionInfo.get_exception_ptr(): any`

**Returns:** `any`

**Calls:**

- `___cxa_is_pointer_type`
- `this.get_type`
- `this.get_adjusted_ptr`

<details><summary>Code</summary>

```typescript
get_exception_ptr(){var isPointer=___cxa_is_pointer_type(this.get_type());if(isPointer){return HEAPU32[this.excPtr>>2]}var adjusted=this.get_adjusted_ptr();if(adjusted!==0)return adjusted;return this.excPtr}
```
</details>

### `___cxa_throw(ptr: any, type: any, destructor: any): never`

**Parameters:**

- **`ptr`** `any`
- **`type`** `any`
- **`destructor`** `any`

**Returns:** `never`

**Calls:**

- `info.init`

<details><summary>Code</summary>

```typescript
(ptr,type,destructor)=>{var info=new ExceptionInfo(ptr);info.init(type,destructor);exceptionLast=ptr;uncaughtExceptionCount++;throw exceptionLast}
```
</details>

### `__abort_js(): void`

**Returns:** `void`

**Calls:**

- `abort`

<details><summary>Code</summary>

```typescript
()=>{abort("")}
```
</details>

### `runDestructors(destructors: any): void`

**Parameters:**

- **`destructors`** `any`

**Returns:** `void`

**Calls:**

- `destructors.pop`
- `del`

<details><summary>Code</summary>

```typescript
destructors=>{while(destructors.length){var ptr=destructors.pop();var del=destructors.pop();del(ptr)}}
```
</details>

### `readPointer(pointer: any): any`

**Parameters:**

- **`pointer`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_9015`

<details><summary>Code</summary>

```typescript
function readPointer(pointer){return this["fromWireType"](HEAPU32[pointer>>2])}
```
</details>

### `throwInternalError(message: any): never`

**Parameters:**

- **`message`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
message=>{throw new InternalError(message)}
```
</details>

### `whenDependentTypesAreResolved(myTypes: any, dependentTypes: any, getTypeConverters: any): void`

**Parameters:**

- **`myTypes`** `any`
- **`dependentTypes`** `any`
- **`getTypeConverters`** `any`

**Returns:** `void`

**Calls:**

- `myTypes.forEach`
- `getTypeConverters`
- `throwInternalError`
- `registerType`
- `dependentTypes.forEach`
- `registeredTypes.hasOwnProperty`
- `unregisteredTypes.push`
- `awaitingDependencies.hasOwnProperty`
- `awaitingDependencies[dt].push`
- `onComplete`

<details><summary>Code</summary>

```typescript
(myTypes,dependentTypes,getTypeConverters)=>{myTypes.forEach(function(type){typeDependencies[type]=dependentTypes});function onComplete(typeConverters){var myTypeConverters=getTypeConverters(typeConverters);if(myTypeConverters.length!==myTypes.length){throwInternalError("Mismatched type converter count")}for(var i=0;i<myTypes.length;++i){registerType(myTypes[i],myTypeConverters[i])}}var typeConverters=new Array(dependentTypes.length);var unregisteredTypes=[];var registered=0;dependentTypes.forEach((dt,i)=>{if(registeredTypes.hasOwnProperty(dt)){typeConverters[i]=registeredTypes[dt]}else{unregisteredTypes.push(dt);if(!awaitingDependencies.hasOwnProperty(dt)){awaitingDependencies[dt]=[]}awaitingDependencies[dt].push(()=>{typeConverters[i]=registeredTypes[dt];++registered;if(registered===unregisteredTypes.length){onComplete(typeConverters)}})}});if(0===unregisteredTypes.length){onComplete(typeConverters)}}
```
</details>

### `onComplete(typeConverters: any): void`

**Parameters:**

- **`typeConverters`** `any`

**Returns:** `void`

**Calls:**

- `getTypeConverters`
- `throwInternalError`
- `registerType`

<details><summary>Code</summary>

```typescript
function onComplete(typeConverters){var myTypeConverters=getTypeConverters(typeConverters);if(myTypeConverters.length!==myTypes.length){throwInternalError("Mismatched type converter count")}for(var i=0;i<myTypes.length;++i){registerType(myTypes[i],myTypeConverters[i])}}
```
</details>

### `__embind_finalize_value_object(structType: any): void`

**Parameters:**

- **`structType`** `any`

**Returns:** `void`

**Calls:**

- `fieldRecords.map(field=>field.getterReturnType).concat`
- `fieldRecords.map`
- `whenDependentTypesAreResolved`
- `fieldRecords.forEach`
- `complex_call_10907`
- `getter`
- `setter`
- `complex_call_11027`
- `runDestructors`
- `fields[i].read`
- `rawDestructor`
- `rawConstructor`
- `fields[fieldName].write`
- `destructors.push`

<details><summary>Code</summary>

```typescript
structType=>{var reg=structRegistrations[structType];delete structRegistrations[structType];var rawConstructor=reg.rawConstructor;var rawDestructor=reg.rawDestructor;var fieldRecords=reg.fields;var fieldTypes=fieldRecords.map(field=>field.getterReturnType).concat(fieldRecords.map(field=>field.setterArgumentType));whenDependentTypesAreResolved([structType],fieldTypes,fieldTypes=>{var fields={};fieldRecords.forEach((field,i)=>{var fieldName=field.fieldName;var getterReturnType=fieldTypes[i];var getter=field.getter;var getterContext=field.getterContext;var setterArgumentType=fieldTypes[i+fieldRecords.length];var setter=field.setter;var setterContext=field.setterContext;fields[fieldName]={read:ptr=>getterReturnType["fromWireType"](getter(getterContext,ptr)),write:(ptr,o)=>{var destructors=[];setter(setterContext,ptr,setterArgumentType["toWireType"](destructors,o));runDestructors(destructors)}}});return[{name:reg.name,fromWireType:ptr=>{var rv={};for(var i in fields){rv[i]=fields[i].read(ptr)}rawDestructor(ptr);return rv},toWireType:(destructors,o)=>{for(var fieldName in fields){if(!(fieldName in o)){throw new TypeError(`Missing field: "${fieldName}"`)}}var ptr=rawConstructor();for(fieldName in fields){fields[fieldName].write(ptr,o[fieldName])}if(destructors!==null){destructors.push(rawDestructor,ptr)}return ptr},argPackAdvance:GenericWireTypeSize,readValueFromPointer:readPointer,destructorFunction:rawDestructor}]})}
```
</details>

### `read(ptr: any): any`

**Parameters:**

- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_10907`

<details><summary>Code</summary>

```typescript
ptr=>getterReturnType["fromWireType"](getter(getterContext,ptr))
```
</details>

### `write(ptr: any, o: any): void`

**Parameters:**

- **`ptr`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `setter`
- `complex_call_11027`
- `runDestructors`

<details><summary>Code</summary>

```typescript
(ptr,o)=>{var destructors=[];setter(setterContext,ptr,setterArgumentType["toWireType"](destructors,o));runDestructors(destructors)}
```
</details>

### `read(ptr: any): any`

**Parameters:**

- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_10907`

<details><summary>Code</summary>

```typescript
ptr=>getterReturnType["fromWireType"](getter(getterContext,ptr))
```
</details>

### `write(ptr: any, o: any): void`

**Parameters:**

- **`ptr`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `setter`
- `complex_call_11027`
- `runDestructors`

<details><summary>Code</summary>

```typescript
(ptr,o)=>{var destructors=[];setter(setterContext,ptr,setterArgumentType["toWireType"](destructors,o));runDestructors(destructors)}
```
</details>

### `fromWireType(ptr: any): {}`

**Parameters:**

- **`ptr`** `any`

**Returns:** `{}`

**Calls:**

- `fields[i].read`
- `rawDestructor`

<details><summary>Code</summary>

```typescript
ptr=>{var rv={};for(var i in fields){rv[i]=fields[i].read(ptr)}rawDestructor(ptr);return rv}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

**Calls:**

- `rawConstructor`
- `fields[fieldName].write`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,o)=>{for(var fieldName in fields){if(!(fieldName in o)){throw new TypeError(`Missing field: "${fieldName}"`)}}var ptr=rawConstructor();for(fieldName in fields){fields[fieldName].write(ptr,o[fieldName])}if(destructors!==null){destructors.push(rawDestructor,ptr)}return ptr}
```
</details>

### `fromWireType(ptr: any): {}`

**Parameters:**

- **`ptr`** `any`

**Returns:** `{}`

**Calls:**

- `fields[i].read`
- `rawDestructor`

<details><summary>Code</summary>

```typescript
ptr=>{var rv={};for(var i in fields){rv[i]=fields[i].read(ptr)}rawDestructor(ptr);return rv}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

**Calls:**

- `rawConstructor`
- `fields[fieldName].write`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,o)=>{for(var fieldName in fields){if(!(fieldName in o)){throw new TypeError(`Missing field: "${fieldName}"`)}}var ptr=rawConstructor();for(fieldName in fields){fields[fieldName].write(ptr,o[fieldName])}if(destructors!==null){destructors.push(rawDestructor,ptr)}return ptr}
```
</details>

### `read(ptr: any): any`

**Parameters:**

- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_10907`

<details><summary>Code</summary>

```typescript
ptr=>getterReturnType["fromWireType"](getter(getterContext,ptr))
```
</details>

### `write(ptr: any, o: any): void`

**Parameters:**

- **`ptr`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `setter`
- `complex_call_11027`
- `runDestructors`

<details><summary>Code</summary>

```typescript
(ptr,o)=>{var destructors=[];setter(setterContext,ptr,setterArgumentType["toWireType"](destructors,o));runDestructors(destructors)}
```
</details>

### `read(ptr: any): any`

**Parameters:**

- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_10907`

<details><summary>Code</summary>

```typescript
ptr=>getterReturnType["fromWireType"](getter(getterContext,ptr))
```
</details>

### `write(ptr: any, o: any): void`

**Parameters:**

- **`ptr`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `setter`
- `complex_call_11027`
- `runDestructors`

<details><summary>Code</summary>

```typescript
(ptr,o)=>{var destructors=[];setter(setterContext,ptr,setterArgumentType["toWireType"](destructors,o));runDestructors(destructors)}
```
</details>

### `fromWireType(ptr: any): {}`

**Parameters:**

- **`ptr`** `any`

**Returns:** `{}`

**Calls:**

- `fields[i].read`
- `rawDestructor`

<details><summary>Code</summary>

```typescript
ptr=>{var rv={};for(var i in fields){rv[i]=fields[i].read(ptr)}rawDestructor(ptr);return rv}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

**Calls:**

- `rawConstructor`
- `fields[fieldName].write`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,o)=>{for(var fieldName in fields){if(!(fieldName in o)){throw new TypeError(`Missing field: "${fieldName}"`)}}var ptr=rawConstructor();for(fieldName in fields){fields[fieldName].write(ptr,o[fieldName])}if(destructors!==null){destructors.push(rawDestructor,ptr)}return ptr}
```
</details>

### `fromWireType(ptr: any): {}`

**Parameters:**

- **`ptr`** `any`

**Returns:** `{}`

**Calls:**

- `fields[i].read`
- `rawDestructor`

<details><summary>Code</summary>

```typescript
ptr=>{var rv={};for(var i in fields){rv[i]=fields[i].read(ptr)}rawDestructor(ptr);return rv}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

**Calls:**

- `rawConstructor`
- `fields[fieldName].write`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,o)=>{for(var fieldName in fields){if(!(fieldName in o)){throw new TypeError(`Missing field: "${fieldName}"`)}}var ptr=rawConstructor();for(fieldName in fields){fields[fieldName].write(ptr,o[fieldName])}if(destructors!==null){destructors.push(rawDestructor,ptr)}return ptr}
```
</details>

### `__embind_register_bigint(primitiveType: any, name: any, size: any, minRange: any, maxRange: any): void`

**Parameters:**

- **`primitiveType`** `any`
- **`name`** `any`
- **`size`** `any`
- **`minRange`** `any`
- **`maxRange`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
(primitiveType,name,size,minRange,maxRange)=>{}
```
</details>

### `embind_init_charCodes(): void`

**Returns:** `void`

**Calls:**

- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
()=>{var codes=new Array(256);for(var i=0;i<256;++i){codes[i]=String.fromCharCode(i)}embind_charCodes=codes}
```
</details>

### `readLatin1String(ptr: any): string`

**Parameters:**

- **`ptr`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
ptr=>{var ret="";var c=ptr;while(HEAPU8[c]){ret+=embind_charCodes[HEAPU8[c++]]}return ret}
```
</details>

### `throwBindingError(message: any): never`

**Parameters:**

- **`message`** `any`

**Returns:** `never`

<details><summary>Code</summary>

```typescript
message=>{throw new BindingError(message)}
```
</details>

### `sharedRegisterType(rawType: any, registeredInstance: any, options: {}): void`

**Parameters:**

- **`rawType`** `any`
- **`registeredInstance`** `any`
- **`options`** `{}`

**Returns:** `void`

**Calls:**

- `throwBindingError`
- `registeredTypes.hasOwnProperty`
- `awaitingDependencies.hasOwnProperty`
- `callbacks.forEach`
- `cb`

<details><summary>Code</summary>

```typescript
function sharedRegisterType(rawType,registeredInstance,options={}){var name=registeredInstance.name;if(!rawType){throwBindingError(`type "${name}" must have a positive integer typeid pointer`)}if(registeredTypes.hasOwnProperty(rawType)){if(options.ignoreDuplicateRegistrations){return}else{throwBindingError(`Cannot register type '${name}' twice`)}}registeredTypes[rawType]=registeredInstance;delete typeDependencies[rawType];if(awaitingDependencies.hasOwnProperty(rawType)){var callbacks=awaitingDependencies[rawType];delete awaitingDependencies[rawType];callbacks.forEach(cb=>cb())}}
```
</details>

### `registerType(rawType: any, registeredInstance: any, options: {}): void`

**Parameters:**

- **`rawType`** `any`
- **`registeredInstance`** `any`
- **`options`** `{}`

**Returns:** `void`

**Calls:**

- `sharedRegisterType`

<details><summary>Code</summary>

```typescript
function registerType(rawType,registeredInstance,options={}){if(!("argPackAdvance"in registeredInstance)){throw new TypeError("registerType registeredInstance requires argPackAdvance")}return sharedRegisterType(rawType,registeredInstance,options)}
```
</details>

### `__embind_register_bool(rawType: any, name: any, trueValue: any, falseValue: any): void`

**Parameters:**

- **`rawType`** `any`
- **`name`** `any`
- **`trueValue`** `any`
- **`falseValue`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `registerType`
- `complex_call_13234`

<details><summary>Code</summary>

```typescript
(rawType,name,trueValue,falseValue)=>{name=readLatin1String(name);registerType(rawType,{name:name,fromWireType:function(wt){return!!wt},toWireType:function(destructors,o){return o?trueValue:falseValue},argPackAdvance:GenericWireTypeSize,readValueFromPointer:function(pointer){return this["fromWireType"](HEAPU8[pointer])},destructorFunction:null})}
```
</details>

### `fromWireType(wt: any): boolean`

**Parameters:**

- **`wt`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(wt){return!!wt}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(destructors,o){return o?trueValue:falseValue}
```
</details>

### `readValueFromPointer(pointer: any): any`

**Parameters:**

- **`pointer`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_13234`

<details><summary>Code</summary>

```typescript
function(pointer){return this["fromWireType"](HEAPU8[pointer])}
```
</details>

### `fromWireType(wt: any): boolean`

**Parameters:**

- **`wt`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(wt){return!!wt}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(destructors,o){return o?trueValue:falseValue}
```
</details>

### `readValueFromPointer(pointer: any): any`

**Parameters:**

- **`pointer`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_13234`

<details><summary>Code</summary>

```typescript
function(pointer){return this["fromWireType"](HEAPU8[pointer])}
```
</details>

### `fromWireType(wt: any): boolean`

**Parameters:**

- **`wt`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(wt){return!!wt}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(destructors,o){return o?trueValue:falseValue}
```
</details>

### `readValueFromPointer(pointer: any): any`

**Parameters:**

- **`pointer`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_13234`

<details><summary>Code</summary>

```typescript
function(pointer){return this["fromWireType"](HEAPU8[pointer])}
```
</details>

### `fromWireType(wt: any): boolean`

**Parameters:**

- **`wt`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(wt){return!!wt}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(destructors,o){return o?trueValue:falseValue}
```
</details>

### `readValueFromPointer(pointer: any): any`

**Parameters:**

- **`pointer`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_13234`

<details><summary>Code</summary>

```typescript
function(pointer){return this["fromWireType"](HEAPU8[pointer])}
```
</details>

### `shallowCopyInternalPointer(o: any): { count: any; deleteScheduled: any; preservePointerOnDelete: any; ptr: any; ptrType: any; smartPtr: any; smartPtrType: any; }`

**Parameters:**

- **`o`** `any`

**Returns:** `{ count: any; deleteScheduled: any; preservePointerOnDelete: any; ptr: any; ptrType: any; smartPtr: any; smartPtrType: any; }`

<details><summary>Code</summary>

```typescript
o=>({count:o.count,deleteScheduled:o.deleteScheduled,preservePointerOnDelete:o.preservePointerOnDelete,ptr:o.ptr,ptrType:o.ptrType,smartPtr:o.smartPtr,smartPtrType:o.smartPtrType})
```
</details>

### `throwInstanceAlreadyDeleted(obj: any): void`

**Parameters:**

- **`obj`** `any`

**Returns:** `void`

**Calls:**

- `throwBindingError`
- `getInstanceTypeName`

<details><summary>Code</summary>

```typescript
obj=>{function getInstanceTypeName(handle){return handle.$$.ptrType.registeredClass.name}throwBindingError(getInstanceTypeName(obj)+" instance already deleted")}
```
</details>

### `getInstanceTypeName(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getInstanceTypeName(handle){return handle.$$.ptrType.registeredClass.name}
```
</details>

### `detachFinalizer(handle: any): void`

**Parameters:**

- **`handle`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
handle=>{}
```
</details>

### `runDestructor($$: any): void`

**Parameters:**

- **`$$`** `any`

**Returns:** `void`

**Calls:**

- `$$.smartPtrType.rawDestructor`
- `$$.ptrType.registeredClass.rawDestructor`

<details><summary>Code</summary>

```typescript
$$=>{if($$.smartPtr){$$.smartPtrType.rawDestructor($$.smartPtr)}else{$$.ptrType.registeredClass.rawDestructor($$.ptr)}}
```
</details>

### `releaseClassHandle($$: any): void`

**Parameters:**

- **`$$`** `any`

**Returns:** `void`

**Calls:**

- `runDestructor`

<details><summary>Code</summary>

```typescript
$$=>{$$.count.value-=1;var toDelete=0===$$.count.value;if(toDelete){runDestructor($$)}}
```
</details>

### `downcastPointer(ptr: any, ptrClass: any, desiredClass: any): any`

**Parameters:**

- **`ptr`** `any`
- **`ptrClass`** `any`
- **`desiredClass`** `any`

**Returns:** `any`

**Calls:**

- `downcastPointer`
- `desiredClass.downcast`

<details><summary>Code</summary>

```typescript
(ptr,ptrClass,desiredClass)=>{if(ptrClass===desiredClass){return ptr}if(undefined===desiredClass.baseClass){return null}var rv=downcastPointer(ptr,ptrClass,desiredClass.baseClass);if(rv===null){return null}return desiredClass.downcast(rv)}
```
</details>

### `getInheritedInstanceCount(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
()=>Object.keys(registeredInstances).length
```
</details>

### `getLiveInheritedInstances(): any[]`

**Returns:** `any[]`

**Calls:**

- `registeredInstances.hasOwnProperty`
- `rv.push`

<details><summary>Code</summary>

```typescript
()=>{var rv=[];for(var k in registeredInstances){if(registeredInstances.hasOwnProperty(k)){rv.push(registeredInstances[k])}}return rv}
```
</details>

### `flushPendingDeletes(): void`

**Returns:** `void`

**Calls:**

- `deletionQueue.pop`
- `complex_call_14677`

<details><summary>Code</summary>

```typescript
()=>{while(deletionQueue.length){var obj=deletionQueue.pop();obj.$$.deleteScheduled=false;obj["delete"]()}}
```
</details>

### `setDelayFunction(fn: any): void`

**Parameters:**

- **`fn`** `any`

**Returns:** `void`

**Calls:**

- `delayFunction`

<details><summary>Code</summary>

```typescript
fn=>{delayFunction=fn;if(deletionQueue.length&&delayFunction){delayFunction(flushPendingDeletes)}}
```
</details>

### `init_embind(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
()=>{Module["getInheritedInstanceCount"]=getInheritedInstanceCount;Module["getLiveInheritedInstances"]=getLiveInheritedInstances;Module["flushPendingDeletes"]=flushPendingDeletes;Module["setDelayFunction"]=setDelayFunction}
```
</details>

### `getBasestPointer(class_: any, ptr: any): any`

**Parameters:**

- **`class_`** `any`
- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `class_.upcast`

<details><summary>Code</summary>

```typescript
(class_,ptr)=>{if(ptr===undefined){throwBindingError("ptr should not be undefined")}while(class_.baseClass){ptr=class_.upcast(ptr);class_=class_.baseClass}return ptr}
```
</details>

### `getInheritedInstance(class_: any, ptr: any): any`

**Parameters:**

- **`class_`** `any`
- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `getBasestPointer`

<details><summary>Code</summary>

```typescript
(class_,ptr)=>{ptr=getBasestPointer(class_,ptr);return registeredInstances[ptr]}
```
</details>

### `makeClassHandle(prototype: any, record: any): any`

**Parameters:**

- **`prototype`** `any`
- **`record`** `any`

**Returns:** `any`

**Calls:**

- `throwInternalError`
- `attachFinalizer`
- `Object.create`

<details><summary>Code</summary>

```typescript
(prototype,record)=>{if(!record.ptrType||!record.ptr){throwInternalError("makeClassHandle requires ptr and ptrType")}var hasSmartPtrType=!!record.smartPtrType;var hasSmartPtr=!!record.smartPtr;if(hasSmartPtrType!==hasSmartPtr){throwInternalError("Both smartPtrType and smartPtr must be specified")}record.count={value:1};return attachFinalizer(Object.create(prototype,{$$:{value:record,writable:true}}))}
```
</details>

### `RegisteredPointer_fromWireType(ptr: any): any`

**Parameters:**

- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `this.getPointee`
- `this.destructor`
- `getInheritedInstance`
- `complex_call_16182`
- `complex_call_16224`
- `makeClassHandle`
- `this.registeredClass.getActualType`
- `makeDefaultHandle.call`
- `downcastPointer`

<details><summary>Code</summary>

```typescript
function RegisteredPointer_fromWireType(ptr){var rawPointer=this.getPointee(ptr);if(!rawPointer){this.destructor(ptr);return null}var registeredInstance=getInheritedInstance(this.registeredClass,rawPointer);if(undefined!==registeredInstance){if(0===registeredInstance.$$.count.value){registeredInstance.$$.ptr=rawPointer;registeredInstance.$$.smartPtr=ptr;return registeredInstance["clone"]()}else{var rv=registeredInstance["clone"]();this.destructor(ptr);return rv}}function makeDefaultHandle(){if(this.isSmartPointer){return makeClassHandle(this.registeredClass.instancePrototype,{ptrType:this.pointeeType,ptr:rawPointer,smartPtrType:this,smartPtr:ptr})}else{return makeClassHandle(this.registeredClass.instancePrototype,{ptrType:this,ptr:ptr})}}var actualType=this.registeredClass.getActualType(rawPointer);var registeredPointerRecord=registeredPointers[actualType];if(!registeredPointerRecord){return makeDefaultHandle.call(this)}var toType;if(this.isConst){toType=registeredPointerRecord.constPointerType}else{toType=registeredPointerRecord.pointerType}var dp=downcastPointer(rawPointer,this.registeredClass,toType.registeredClass);if(dp===null){return makeDefaultHandle.call(this)}if(this.isSmartPointer){return makeClassHandle(toType.registeredClass.instancePrototype,{ptrType:toType,ptr:dp,smartPtrType:this,smartPtr:ptr})}else{return makeClassHandle(toType.registeredClass.instancePrototype,{ptrType:toType,ptr:dp})}}
```
</details>

### `makeDefaultHandle(): any`

**Returns:** `any`

**Calls:**

- `makeClassHandle`

<details><summary>Code</summary>

```typescript
function makeDefaultHandle(){if(this.isSmartPointer){return makeClassHandle(this.registeredClass.instancePrototype,{ptrType:this.pointeeType,ptr:rawPointer,smartPtrType:this,smartPtr:ptr})}else{return makeClassHandle(this.registeredClass.instancePrototype,{ptrType:this,ptr:ptr})}}
```
</details>

### `attachFinalizer(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `releaseClassHandle`
- `finalizationRegistry.register`
- `finalizationRegistry.unregister`
- `attachFinalizer`

<details><summary>Code</summary>

```typescript
handle=>{if("undefined"===typeof FinalizationRegistry){attachFinalizer=handle=>handle;return handle}finalizationRegistry=new FinalizationRegistry(info=>{releaseClassHandle(info.$$)});attachFinalizer=handle=>{var $$=handle.$$;var hasSmartPtr=!!$$.smartPtr;if(hasSmartPtr){var info={$$:$$};finalizationRegistry.register(handle,info,handle)}return handle};detachFinalizer=handle=>finalizationRegistry.unregister(handle);return attachFinalizer(handle)}
```
</details>

### `init_ClassHandle(): void`

**Returns:** `void`

**Calls:**

- `Object.assign`
- `leftClass.upcast`
- `rightClass.upcast`
- `throwInstanceAlreadyDeleted`
- `attachFinalizer`
- `Object.create`
- `Object.getPrototypeOf`
- `shallowCopyInternalPointer`
- `throwBindingError`
- `detachFinalizer`
- `releaseClassHandle`
- `deletionQueue.push`
- `delayFunction`

<details><summary>Code</summary>

```typescript
()=>{Object.assign(ClassHandle.prototype,{isAliasOf(other){if(!(this instanceof ClassHandle)){return false}if(!(other instanceof ClassHandle)){return false}var leftClass=this.$$.ptrType.registeredClass;var left=this.$$.ptr;other.$$=other.$$;var rightClass=other.$$.ptrType.registeredClass;var right=other.$$.ptr;while(leftClass.baseClass){left=leftClass.upcast(left);leftClass=leftClass.baseClass}while(rightClass.baseClass){right=rightClass.upcast(right);rightClass=rightClass.baseClass}return leftClass===rightClass&&left===right},clone(){if(!this.$$.ptr){throwInstanceAlreadyDeleted(this)}if(this.$$.preservePointerOnDelete){this.$$.count.value+=1;return this}else{var clone=attachFinalizer(Object.create(Object.getPrototypeOf(this),{$$:{value:shallowCopyInternalPointer(this.$$)}}));clone.$$.count.value+=1;clone.$$.deleteScheduled=false;return clone}},delete(){if(!this.$$.ptr){throwInstanceAlreadyDeleted(this)}if(this.$$.deleteScheduled&&!this.$$.preservePointerOnDelete){throwBindingError("Object already scheduled for deletion")}detachFinalizer(this);releaseClassHandle(this.$$);if(!this.$$.preservePointerOnDelete){this.$$.smartPtr=undefined;this.$$.ptr=undefined}},isDeleted(){return!this.$$.ptr},deleteLater(){if(!this.$$.ptr){throwInstanceAlreadyDeleted(this)}if(this.$$.deleteScheduled&&!this.$$.preservePointerOnDelete){throwBindingError("Object already scheduled for deletion")}deletionQueue.push(this);if(deletionQueue.length===1&&delayFunction){delayFunction(flushPendingDeletes)}this.$$.deleteScheduled=true;return this}})}
```
</details>

### `ClassHandle(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ClassHandle(){}
```
</details>

### `createNamedFunction(name: any, body: any): any`

**Parameters:**

- **`name`** `any`
- **`body`** `any`

**Returns:** `any`

**Calls:**

- `Object.defineProperty`

<details><summary>Code</summary>

```typescript
(name,body)=>Object.defineProperty(body,"name",{value:name})
```
</details>

### `ensureOverloadTable(proto: any, methodName: any, humanName: any): void`

**Parameters:**

- **`proto`** `any`
- **`methodName`** `any`
- **`humanName`** `any`

**Returns:** `void`

**Calls:**

- `proto[methodName].overloadTable.hasOwnProperty`
- `throwBindingError`
- `proto[methodName].overloadTable[args.length].apply`

<details><summary>Code</summary>

```typescript
(proto,methodName,humanName)=>{if(undefined===proto[methodName].overloadTable){var prevFunc=proto[methodName];proto[methodName]=function(...args){if(!proto[methodName].overloadTable.hasOwnProperty(args.length)){throwBindingError(`Function '${humanName}' called with an invalid number of arguments (${args.length}) - expects one of (${proto[methodName].overloadTable})!`)}return proto[methodName].overloadTable[args.length].apply(this,args)};proto[methodName].overloadTable=[];proto[methodName].overloadTable[prevFunc.argCount]=prevFunc}}
```
</details>

### `exposePublicSymbol(name: any, value: any, numArguments: any): void`

**Parameters:**

- **`name`** `any`
- **`value`** `any`
- **`numArguments`** `any`

**Returns:** `void`

**Calls:**

- `Module.hasOwnProperty`
- `throwBindingError`
- `ensureOverloadTable`

<details><summary>Code</summary>

```typescript
(name,value,numArguments)=>{if(Module.hasOwnProperty(name)){if(undefined===numArguments||undefined!==Module[name].overloadTable&&undefined!==Module[name].overloadTable[numArguments]){throwBindingError(`Cannot register public name '${name}' twice`)}ensureOverloadTable(Module,name,name);if(Module.hasOwnProperty(numArguments)){throwBindingError(`Cannot register multiple overloads of a function with the same number of arguments (${numArguments})!`)}Module[name].overloadTable[numArguments]=value}else{Module[name]=value;if(undefined!==numArguments){Module[name].numArguments=numArguments}}}
```
</details>

### `makeLegalFunctionName(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `name.replace`
- `name.charCodeAt`

<details><summary>Code</summary>

```typescript
name=>{if(undefined===name){return"_unknown"}name=name.replace(/[^a-zA-Z0-9_]/g,"$");var f=name.charCodeAt(0);if(f>=char_0&&f<=char_9){return`_${name}`}return name}
```
</details>

### `RegisteredClass(name: any, constructor: any, instancePrototype: any, rawDestructor: any, baseClass: any, getActualType: any, upcast: any, downcast: any): void`

**Parameters:**

- **`name`** `any`
- **`constructor`** `any`
- **`instancePrototype`** `any`
- **`rawDestructor`** `any`
- **`baseClass`** `any`
- **`getActualType`** `any`
- **`upcast`** `any`
- **`downcast`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function RegisteredClass(name,constructor,instancePrototype,rawDestructor,baseClass,getActualType,upcast,downcast){this.name=name;this.constructor=constructor;this.instancePrototype=instancePrototype;this.rawDestructor=rawDestructor;this.baseClass=baseClass;this.getActualType=getActualType;this.upcast=upcast;this.downcast=downcast;this.pureVirtualFunctions=[]}
```
</details>

### `upcastPointer(ptr: any, ptrClass: any, desiredClass: any): any`

**Parameters:**

- **`ptr`** `any`
- **`ptrClass`** `any`
- **`desiredClass`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `ptrClass.upcast`

<details><summary>Code</summary>

```typescript
(ptr,ptrClass,desiredClass)=>{while(ptrClass!==desiredClass){if(!ptrClass.upcast){throwBindingError(`Expected null or instance of ${desiredClass.name}, got an instance of ${ptrClass.name}`)}ptr=ptrClass.upcast(ptr);ptrClass=ptrClass.baseClass}return ptr}
```
</details>

### `constNoSmartPtrRawPointerToWireType(destructors: any, handle: any): any`

**Parameters:**

- **`destructors`** `any`
- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `embindRepr`
- `upcastPointer`

<details><summary>Code</summary>

```typescript
function constNoSmartPtrRawPointerToWireType(destructors,handle){if(handle===null){if(this.isReference){throwBindingError(`null is not a valid ${this.name}`)}return 0}if(!handle.$$){throwBindingError(`Cannot pass "${embindRepr(handle)}" as a ${this.name}`)}if(!handle.$$.ptr){throwBindingError(`Cannot pass deleted object as a pointer of type ${this.name}`)}var handleClass=handle.$$.ptrType.registeredClass;var ptr=upcastPointer(handle.$$.ptr,handleClass,this.registeredClass);return ptr}
```
</details>

### `genericPointerToWireType(destructors: any, handle: any): any`

**Parameters:**

- **`destructors`** `any`
- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `this.rawConstructor`
- `destructors.push`
- `embindRepr`
- `upcastPointer`
- `complex_call_23236`
- `this.rawShare`
- `Emval.toHandle`
- `complex_call_23295`

<details><summary>Code</summary>

```typescript
function genericPointerToWireType(destructors,handle){var ptr;if(handle===null){if(this.isReference){throwBindingError(`null is not a valid ${this.name}`)}if(this.isSmartPointer){ptr=this.rawConstructor();if(destructors!==null){destructors.push(this.rawDestructor,ptr)}return ptr}else{return 0}}if(!handle||!handle.$$){throwBindingError(`Cannot pass "${embindRepr(handle)}" as a ${this.name}`)}if(!handle.$$.ptr){throwBindingError(`Cannot pass deleted object as a pointer of type ${this.name}`)}if(!this.isConst&&handle.$$.ptrType.isConst){throwBindingError(`Cannot convert argument of type ${handle.$$.smartPtrType?handle.$$.smartPtrType.name:handle.$$.ptrType.name} to parameter type ${this.name}`)}var handleClass=handle.$$.ptrType.registeredClass;ptr=upcastPointer(handle.$$.ptr,handleClass,this.registeredClass);if(this.isSmartPointer){if(undefined===handle.$$.smartPtr){throwBindingError("Passing raw pointer to smart pointer is illegal")}switch(this.sharingPolicy){case 0:if(handle.$$.smartPtrType===this){ptr=handle.$$.smartPtr}else{throwBindingError(`Cannot convert argument of type ${handle.$$.smartPtrType?handle.$$.smartPtrType.name:handle.$$.ptrType.name} to parameter type ${this.name}`)}break;case 1:ptr=handle.$$.smartPtr;break;case 2:if(handle.$$.smartPtrType===this){ptr=handle.$$.smartPtr}else{var clonedHandle=handle["clone"]();ptr=this.rawShare(ptr,Emval.toHandle(()=>clonedHandle["delete"]()));if(destructors!==null){destructors.push(this.rawDestructor,ptr)}}break;default:throwBindingError("Unsupporting sharing policy")}}return ptr}
```
</details>

### `nonConstNoSmartPtrRawPointerToWireType(destructors: any, handle: any): any`

**Parameters:**

- **`destructors`** `any`
- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `embindRepr`
- `upcastPointer`

<details><summary>Code</summary>

```typescript
function nonConstNoSmartPtrRawPointerToWireType(destructors,handle){if(handle===null){if(this.isReference){throwBindingError(`null is not a valid ${this.name}`)}return 0}if(!handle.$$){throwBindingError(`Cannot pass "${embindRepr(handle)}" as a ${this.name}`)}if(!handle.$$.ptr){throwBindingError(`Cannot pass deleted object as a pointer of type ${this.name}`)}if(handle.$$.ptrType.isConst){throwBindingError(`Cannot convert argument of type ${handle.$$.ptrType.name} to parameter type ${this.name}`)}var handleClass=handle.$$.ptrType.registeredClass;var ptr=upcastPointer(handle.$$.ptr,handleClass,this.registeredClass);return ptr}
```
</details>

### `init_RegisteredPointer(): void`

**Returns:** `void`

**Calls:**

- `Object.assign`
- `this.rawGetPointee`
- `this.rawDestructor`

<details><summary>Code</summary>

```typescript
()=>{Object.assign(RegisteredPointer.prototype,{getPointee(ptr){if(this.rawGetPointee){ptr=this.rawGetPointee(ptr)}return ptr},destructor(ptr){this.rawDestructor?.(ptr)},argPackAdvance:GenericWireTypeSize,readValueFromPointer:readPointer,fromWireType:RegisteredPointer_fromWireType})}
```
</details>

### `RegisteredPointer(name: any, registeredClass: any, isReference: any, isConst: any, isSmartPointer: any, pointeeType: any, sharingPolicy: any, rawGetPointee: any, rawConstructor: any, rawShare: any, rawDestructor: any): void`

**Parameters:**

- **`name`** `any`
- **`registeredClass`** `any`
- **`isReference`** `any`
- **`isConst`** `any`
- **`isSmartPointer`** `any`
- **`pointeeType`** `any`
- **`sharingPolicy`** `any`
- **`rawGetPointee`** `any`
- **`rawConstructor`** `any`
- **`rawShare`** `any`
- **`rawDestructor`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function RegisteredPointer(name,registeredClass,isReference,isConst,isSmartPointer,pointeeType,sharingPolicy,rawGetPointee,rawConstructor,rawShare,rawDestructor){this.name=name;this.registeredClass=registeredClass;this.isReference=isReference;this.isConst=isConst;this.isSmartPointer=isSmartPointer;this.pointeeType=pointeeType;this.sharingPolicy=sharingPolicy;this.rawGetPointee=rawGetPointee;this.rawConstructor=rawConstructor;this.rawShare=rawShare;this.rawDestructor=rawDestructor;if(!isSmartPointer&&registeredClass.baseClass===undefined){if(isConst){this["toWireType"]=constNoSmartPtrRawPointerToWireType;this.destructorFunction=null}else{this["toWireType"]=nonConstNoSmartPtrRawPointerToWireType;this.destructorFunction=null}}else{this["toWireType"]=genericPointerToWireType}}
```
</details>

### `replacePublicSymbol(name: any, value: any, numArguments: any): void`

**Parameters:**

- **`name`** `any`
- **`value`** `any`
- **`numArguments`** `any`

**Returns:** `void`

**Calls:**

- `Module.hasOwnProperty`
- `throwInternalError`

<details><summary>Code</summary>

```typescript
(name,value,numArguments)=>{if(!Module.hasOwnProperty(name)){throwInternalError("Replacing nonexistent public symbol")}if(undefined!==Module[name].overloadTable&&undefined!==numArguments){Module[name].overloadTable[numArguments]=value}else{Module[name]=value;Module[name].argCount=numArguments}}
```
</details>

### `dynCallLegacy(sig: any, ptr: any, args: any): any`

**Parameters:**

- **`sig`** `any`
- **`ptr`** `any`
- **`args`** `any`

**Returns:** `any`

**Calls:**

- `sig.replace`
- `f`

<details><summary>Code</summary>

```typescript
(sig,ptr,args)=>{sig=sig.replace(/p/g,"i");var f=Module["dynCall_"+sig];return f(ptr,...args)}
```
</details>

### `getWasmTableEntry(funcPtr: any): any`

**Parameters:**

- **`funcPtr`** `any`

**Returns:** `any`

**Calls:**

- `wasmTable.get`

<details><summary>Code</summary>

```typescript
funcPtr=>{var func=wasmTableMirror[funcPtr];if(!func){if(funcPtr>=wasmTableMirror.length)wasmTableMirror.length=funcPtr+1;wasmTableMirror[funcPtr]=func=wasmTable.get(funcPtr)}return func}
```
</details>

### `dynCall(sig: any, ptr: any, args: any[]): any`

**Parameters:**

- **`sig`** `any`
- **`ptr`** `any`
- **`args`** `any[]`

**Returns:** `any`

**Calls:**

- `sig.includes`
- `dynCallLegacy`
- `complex_call_25966`

<details><summary>Code</summary>

```typescript
(sig,ptr,args=[])=>{if(sig.includes("j")){return dynCallLegacy(sig,ptr,args)}var rtn=getWasmTableEntry(ptr)(...args);return rtn}
```
</details>

### `getDynCaller(sig: any, ptr: any): (...args: any[]) => any`

**Parameters:**

- **`sig`** `any`
- **`ptr`** `any`

**Returns:** `(...args: any[]) => any`

<details><summary>Code</summary>

```typescript
(sig,ptr)=>(...args)=>dynCall(sig,ptr,args)
```
</details>

### `embind__requireFunction(signature: any, rawFunction: any): any`

**Parameters:**

- **`signature`** `any`
- **`rawFunction`** `any`

**Returns:** `any`

**Calls:**

- `readLatin1String`
- `signature.includes`
- `getDynCaller`
- `getWasmTableEntry`
- `makeDynCaller`
- `throwBindingError`

<details><summary>Code</summary>

```typescript
(signature,rawFunction)=>{signature=readLatin1String(signature);function makeDynCaller(){if(signature.includes("j")){return getDynCaller(signature,rawFunction)}return getWasmTableEntry(rawFunction)}var fp=makeDynCaller();if(typeof fp!="function"){throwBindingError(`unknown function pointer with signature ${signature}: ${rawFunction}`)}return fp}
```
</details>

### `makeDynCaller(): any`

**Returns:** `any`

**Calls:**

- `signature.includes`
- `getDynCaller`
- `getWasmTableEntry`

<details><summary>Code</summary>

```typescript
function makeDynCaller(){if(signature.includes("j")){return getDynCaller(signature,rawFunction)}return getWasmTableEntry(rawFunction)}
```
</details>

### `extendError(baseErrorType: any, errorName: any): any`

**Parameters:**

- **`baseErrorType`** `any`
- **`errorName`** `any`

**Returns:** `any`

**Calls:**

- `createNamedFunction`
- `this.toString`
- `stack.replace`
- `Object.create`

<details><summary>Code</summary>

```typescript
(baseErrorType,errorName)=>{var errorClass=createNamedFunction(errorName,function(message){this.name=errorName;this.message=message;var stack=new Error(message).stack;if(stack!==undefined){this.stack=this.toString()+"\n"+stack.replace(/^Error(:[^\n]*)?\n/,"")}});errorClass.prototype=Object.create(baseErrorType.prototype);errorClass.prototype.constructor=errorClass;errorClass.prototype.toString=function(){if(this.message===undefined){return this.name}else{return`${this.name}: ${this.message}`}};return errorClass}
```
</details>

### `getTypeName(type: any): string`

**Parameters:**

- **`type`** `any`

**Returns:** `string`

**Calls:**

- `___getTypeName`
- `readLatin1String`
- `_free`

<details><summary>Code</summary>

```typescript
type=>{var ptr=___getTypeName(type);var rv=readLatin1String(ptr);_free(ptr);return rv}
```
</details>

### `throwUnboundTypeError(message: any, types: any): never`

**Parameters:**

- **`message`** `any`
- **`types`** `any`

**Returns:** `never`

**Calls:**

- `typeDependencies[type].forEach`
- `unboundTypes.push`
- `types.forEach`
- `unboundTypes.map(getTypeName).join`

<details><summary>Code</summary>

```typescript
(message,types)=>{var unboundTypes=[];var seen={};function visit(type){if(seen[type]){return}if(registeredTypes[type]){return}if(typeDependencies[type]){typeDependencies[type].forEach(visit);return}unboundTypes.push(type);seen[type]=true}types.forEach(visit);throw new UnboundTypeError(`${message}: `+unboundTypes.map(getTypeName).join([", "]))}
```
</details>

### `visit(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

**Calls:**

- `typeDependencies[type].forEach`
- `unboundTypes.push`

<details><summary>Code</summary>

```typescript
function visit(type){if(seen[type]){return}if(registeredTypes[type]){return}if(typeDependencies[type]){typeDependencies[type].forEach(visit);return}unboundTypes.push(type);seen[type]=true}
```
</details>

### `__embind_register_class(rawType: any, rawPointerType: any, rawConstPointerType: any, baseClassRawType: any, getActualTypeSignature: any, getActualType: any, upcastSignature: any, upcast: any, downcastSignature: any, downcast: any, name: any, destructorSignature: any, rawDestructor: any): void`

**Parameters:**

- **`rawType`** `any`
- **`rawPointerType`** `any`
- **`rawConstPointerType`** `any`
- **`baseClassRawType`** `any`
- **`getActualTypeSignature`** `any`
- **`getActualType`** `any`
- **`upcastSignature`** `any`
- **`upcast`** `any`
- **`downcastSignature`** `any`
- **`downcast`** `any`
- **`name`** `any`
- **`destructorSignature`** `any`
- **`rawDestructor`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `embind__requireFunction`
- `makeLegalFunctionName`
- `exposePublicSymbol`
- `throwUnboundTypeError`
- `whenDependentTypesAreResolved`
- `createNamedFunction`
- `Object.getPrototypeOf`
- `Object.keys(registeredClass.constructor_body).toString`
- `body.apply`
- `Object.create`
- `registeredClass.baseClass.__derivedClasses.push`
- `replacePublicSymbol`

<details><summary>Code</summary>

```typescript
(rawType,rawPointerType,rawConstPointerType,baseClassRawType,getActualTypeSignature,getActualType,upcastSignature,upcast,downcastSignature,downcast,name,destructorSignature,rawDestructor)=>{name=readLatin1String(name);getActualType=embind__requireFunction(getActualTypeSignature,getActualType);upcast&&=embind__requireFunction(upcastSignature,upcast);downcast&&=embind__requireFunction(downcastSignature,downcast);rawDestructor=embind__requireFunction(destructorSignature,rawDestructor);var legalFunctionName=makeLegalFunctionName(name);exposePublicSymbol(legalFunctionName,function(){throwUnboundTypeError(`Cannot construct ${name} due to unbound types`,[baseClassRawType])});whenDependentTypesAreResolved([rawType,rawPointerType,rawConstPointerType],baseClassRawType?[baseClassRawType]:[],base=>{base=base[0];var baseClass;var basePrototype;if(baseClassRawType){baseClass=base.registeredClass;basePrototype=baseClass.instancePrototype}else{basePrototype=ClassHandle.prototype}var constructor=createNamedFunction(name,function(...args){if(Object.getPrototypeOf(this)!==instancePrototype){throw new BindingError("Use 'new' to construct "+name)}if(undefined===registeredClass.constructor_body){throw new BindingError(name+" has no accessible constructor")}var body=registeredClass.constructor_body[args.length];if(undefined===body){throw new BindingError(`Tried to invoke ctor of ${name} with invalid number of parameters (${args.length}) - expected (${Object.keys(registeredClass.constructor_body).toString()}) parameters instead!`)}return body.apply(this,args)});var instancePrototype=Object.create(basePrototype,{constructor:{value:constructor}});constructor.prototype=instancePrototype;var registeredClass=new RegisteredClass(name,constructor,instancePrototype,rawDestructor,baseClass,getActualType,upcast,downcast);if(registeredClass.baseClass){registeredClass.baseClass.__derivedClasses??=[];registeredClass.baseClass.__derivedClasses.push(registeredClass)}var referenceConverter=new RegisteredPointer(name,registeredClass,true,false,false);var pointerConverter=new RegisteredPointer(name+"*",registeredClass,false,false,false);var constPointerConverter=new RegisteredPointer(name+" const*",registeredClass,false,true,false);registeredPointers[rawType]={pointerType:pointerConverter,constPointerType:constPointerConverter};replacePublicSymbol(legalFunctionName,constructor);return[referenceConverter,pointerConverter,constPointerConverter]})}
```
</details>

### `heap32VectorToArray(count: any, firstElement: any): any[]`

**Parameters:**

- **`count`** `any`
- **`firstElement`** `any`

**Returns:** `any[]`

**Calls:**

- `array.push`

<details><summary>Code</summary>

```typescript
(count,firstElement)=>{var array=[];for(var i=0;i<count;i++){array.push(HEAPU32[firstElement+i*4>>2])}return array}
```
</details>

### `usesDestructorStack(argTypes: any): boolean`

**Parameters:**

- **`argTypes`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function usesDestructorStack(argTypes){for(var i=1;i<argTypes.length;++i){if(argTypes[i]!==null&&argTypes[i].destructorFunction===undefined){return true}}return false}
```
</details>

### `newFunc(constructor: any, argumentList: any): any`

**Parameters:**

- **`constructor`** `any`
- **`argumentList`** `any`

**Returns:** `any`

**Calls:**

- `createNamedFunction`
- `constructor.apply`

<details><summary>Code</summary>

```typescript
function newFunc(constructor,argumentList){if(!(constructor instanceof Function)){throw new TypeError(`new_ called with constructor type ${typeof constructor} which is not a function`)}var dummy=createNamedFunction(constructor.name||"unknownFunctionName",function(){});dummy.prototype=constructor.prototype;var obj=new dummy;var r=constructor.apply(obj,argumentList);return r instanceof Object?r:obj}
```
</details>

### `createJsInvoker(argTypes: any, isClassMethodFunc: any, returns: any, isAsync: any): (string | string[])[]`

**Parameters:**

- **`argTypes`** `any`
- **`isClassMethodFunc`** `any`
- **`returns`** `any`
- **`isAsync`** `any`

**Returns:** `(string | string[])[]`

**Calls:**

- `usesDestructorStack`
- `args1.push`

<details><summary>Code</summary>

```typescript
function createJsInvoker(argTypes,isClassMethodFunc,returns,isAsync){var needsDestructorStack=usesDestructorStack(argTypes);var argCount=argTypes.length;var argsList="";var argsListWired="";for(var i=0;i<argCount-2;++i){argsList+=(i!==0?", ":"")+"arg"+i;argsListWired+=(i!==0?", ":"")+"arg"+i+"Wired"}var invokerFnBody=`\n        return function (${argsList}) {\n        if (arguments.length !== ${argCount-2}) {\n          throwBindingError('function ' + humanName + ' called with ' + arguments.length + ' arguments, expected ${argCount-2}');\n        }`;if(needsDestructorStack){invokerFnBody+="var destructors = [];\n"}var dtorStack=needsDestructorStack?"destructors":"null";var args1=["humanName","throwBindingError","invoker","fn","runDestructors","retType","classParam"];if(isClassMethodFunc){invokerFnBody+="var thisWired = classParam['toWireType']("+dtorStack+", this);\n"}for(var i=0;i<argCount-2;++i){invokerFnBody+="var arg"+i+"Wired = argType"+i+"['toWireType']("+dtorStack+", arg"+i+");\n";args1.push("argType"+i)}if(isClassMethodFunc){argsListWired="thisWired"+(argsListWired.length>0?", ":"")+argsListWired}invokerFnBody+=(returns||isAsync?"var rv = ":"")+"invoker(fn"+(argsListWired.length>0?", ":"")+argsListWired+");\n";if(needsDestructorStack){invokerFnBody+="runDestructors(destructors);\n"}else{for(var i=isClassMethodFunc?1:2;i<argTypes.length;++i){var paramName=i===1?"thisWired":"arg"+(i-2)+"Wired";if(argTypes[i].destructorFunction!==null){invokerFnBody+=`${paramName}_dtor(${paramName});\n`;args1.push(`${paramName}_dtor`)}}}if(returns){invokerFnBody+="var ret = retType['fromWireType'](rv);\n"+"return ret;\n"}else{}invokerFnBody+="}\n";return[args1,invokerFnBody]}
```
</details>

### `craftInvokerFunction(humanName: any, argTypes: any, classType: any, cppInvokerFunc: any, cppTargetFunc: any, isAsync: any): any`

**Parameters:**

- **`humanName`** `any`
- **`argTypes`** `any`
- **`classType`** `any`
- **`cppInvokerFunc`** `any`
- **`cppTargetFunc`** `any`
- **`isAsync`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `usesDestructorStack`
- `closureArgs.push`
- `createJsInvoker`
- `args.push`
- `complex_call_33218`
- `createNamedFunction`

<details><summary>Code</summary>

```typescript
function craftInvokerFunction(humanName,argTypes,classType,cppInvokerFunc,cppTargetFunc,isAsync){var argCount=argTypes.length;if(argCount<2){throwBindingError("argTypes array size mismatch! Must at least get return value and 'this' types!")}var isClassMethodFunc=argTypes[1]!==null&&classType!==null;var needsDestructorStack=usesDestructorStack(argTypes);var returns=argTypes[0].name!=="void";var closureArgs=[humanName,throwBindingError,cppInvokerFunc,cppTargetFunc,runDestructors,argTypes[0],argTypes[1]];for(var i=0;i<argCount-2;++i){closureArgs.push(argTypes[i+2])}if(!needsDestructorStack){for(var i=isClassMethodFunc?1:2;i<argTypes.length;++i){if(argTypes[i].destructorFunction!==null){closureArgs.push(argTypes[i].destructorFunction)}}}let[args,invokerFnBody]=createJsInvoker(argTypes,isClassMethodFunc,returns,isAsync);args.push(invokerFnBody);var invokerFn=newFunc(Function,args)(...closureArgs);return createNamedFunction(humanName,invokerFn)}
```
</details>

### `__embind_register_class_constructor(rawClassType: any, argCount: any, rawArgTypesAddr: any, invokerSignature: any, invoker: any, rawConstructor: any): void`

**Parameters:**

- **`rawClassType`** `any`
- **`argCount`** `any`
- **`rawArgTypesAddr`** `any`
- **`invokerSignature`** `any`
- **`invoker`** `any`
- **`rawConstructor`** `any`

**Returns:** `void`

**Calls:**

- `heap32VectorToArray`
- `embind__requireFunction`
- `whenDependentTypesAreResolved`
- `throwUnboundTypeError`
- `argTypes.splice`
- `craftInvokerFunction`

<details><summary>Code</summary>

```typescript
(rawClassType,argCount,rawArgTypesAddr,invokerSignature,invoker,rawConstructor)=>{var rawArgTypes=heap32VectorToArray(argCount,rawArgTypesAddr);invoker=embind__requireFunction(invokerSignature,invoker);whenDependentTypesAreResolved([],[rawClassType],classType=>{classType=classType[0];var humanName=`constructor ${classType.name}`;if(undefined===classType.registeredClass.constructor_body){classType.registeredClass.constructor_body=[]}if(undefined!==classType.registeredClass.constructor_body[argCount-1]){throw new BindingError(`Cannot register multiple constructors with identical number of parameters (${argCount-1}) for class '${classType.name}'! Overload resolution is currently only performed using the parameter count, not actual type info!`)}classType.registeredClass.constructor_body[argCount-1]=()=>{throwUnboundTypeError(`Cannot construct ${classType.name} due to unbound types`,rawArgTypes)};whenDependentTypesAreResolved([],rawArgTypes,argTypes=>{argTypes.splice(1,0,null);classType.registeredClass.constructor_body[argCount-1]=craftInvokerFunction(humanName,argTypes,null,invoker,rawConstructor);return[]});return[]})}
```
</details>

### `getFunctionName(signature: any): any`

**Parameters:**

- **`signature`** `any`

**Returns:** `any`

**Calls:**

- `signature.trim`
- `signature.indexOf`
- `signature.substr`

<details><summary>Code</summary>

```typescript
signature=>{signature=signature.trim();const argsIndex=signature.indexOf("(");if(argsIndex!==-1){return signature.substr(0,argsIndex)}else{return signature}}
```
</details>

### `__embind_register_class_function(rawClassType: any, methodName: any, argCount: any, rawArgTypesAddr: any, invokerSignature: any, rawInvoker: any, context: any, isPureVirtual: any, isAsync: any): void`

**Parameters:**

- **`rawClassType`** `any`
- **`methodName`** `any`
- **`argCount`** `any`
- **`rawArgTypesAddr`** `any`
- **`invokerSignature`** `any`
- **`rawInvoker`** `any`
- **`context`** `any`
- **`isPureVirtual`** `any`
- **`isAsync`** `any`

**Returns:** `void`

**Calls:**

- `heap32VectorToArray`
- `readLatin1String`
- `getFunctionName`
- `embind__requireFunction`
- `whenDependentTypesAreResolved`
- `methodName.startsWith`
- `methodName.substring`
- `classType.registeredClass.pureVirtualFunctions.push`
- `throwUnboundTypeError`
- `ensureOverloadTable`
- `craftInvokerFunction`

<details><summary>Code</summary>

```typescript
(rawClassType,methodName,argCount,rawArgTypesAddr,invokerSignature,rawInvoker,context,isPureVirtual,isAsync)=>{var rawArgTypes=heap32VectorToArray(argCount,rawArgTypesAddr);methodName=readLatin1String(methodName);methodName=getFunctionName(methodName);rawInvoker=embind__requireFunction(invokerSignature,rawInvoker);whenDependentTypesAreResolved([],[rawClassType],classType=>{classType=classType[0];var humanName=`${classType.name}.${methodName}`;if(methodName.startsWith("@@")){methodName=Symbol[methodName.substring(2)]}if(isPureVirtual){classType.registeredClass.pureVirtualFunctions.push(methodName)}function unboundTypesHandler(){throwUnboundTypeError(`Cannot call ${humanName} due to unbound types`,rawArgTypes)}var proto=classType.registeredClass.instancePrototype;var method=proto[methodName];if(undefined===method||undefined===method.overloadTable&&method.className!==classType.name&&method.argCount===argCount-2){unboundTypesHandler.argCount=argCount-2;unboundTypesHandler.className=classType.name;proto[methodName]=unboundTypesHandler}else{ensureOverloadTable(proto,methodName,humanName);proto[methodName].overloadTable[argCount-2]=unboundTypesHandler}whenDependentTypesAreResolved([],rawArgTypes,argTypes=>{var memberFunction=craftInvokerFunction(humanName,argTypes,classType,rawInvoker,context,isAsync);if(undefined===proto[methodName].overloadTable){memberFunction.argCount=argCount-2;proto[methodName]=memberFunction}else{proto[methodName].overloadTable[argCount-2]=memberFunction}return[]});return[]})}
```
</details>

### `unboundTypesHandler(): void`

**Returns:** `void`

**Calls:**

- `throwUnboundTypeError`

<details><summary>Code</summary>

```typescript
function unboundTypesHandler(){throwUnboundTypeError(`Cannot call ${humanName} due to unbound types`,rawArgTypes)}
```
</details>

### `__embind_register_constant(name: any, type: any, value: any): void`

**Parameters:**

- **`name`** `any`
- **`type`** `any`
- **`value`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `whenDependentTypesAreResolved`
- `complex_call_36365`

<details><summary>Code</summary>

```typescript
(name,type,value)=>{name=readLatin1String(name);whenDependentTypesAreResolved([],[type],type=>{type=type[0];Module[name]=type["fromWireType"](value);return[]})}
```
</details>

### `__emval_decref(handle: any): void`

**Parameters:**

- **`handle`** `any`

**Returns:** `void`

**Calls:**

- `emval_freelist.push`

<details><summary>Code</summary>

```typescript
handle=>{if(handle>9&&0===--emval_handles[handle+1]){emval_handles[handle]=undefined;emval_freelist.push(handle)}}
```
</details>

### `count_emval_handles(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
()=>emval_handles.length/2-5-emval_freelist.length
```
</details>

### `init_emval(): void`

**Returns:** `void`

**Calls:**

- `emval_handles.push`

<details><summary>Code</summary>

```typescript
()=>{emval_handles.push(0,1,undefined,1,null,1,true,1,false,1);Module["count_emval_handles"]=count_emval_handles}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `__embind_register_emval(rawType: any): void`

**Parameters:**

- **`rawType`** `any`

**Returns:** `void`

**Calls:**

- `registerType`

<details><summary>Code</summary>

```typescript
rawType=>registerType(rawType,EmValType)
```
</details>

### `enumReadValueFromPointer(name: any, width: any, signed: any): (pointer: any) => any`

**Parameters:**

- **`name`** `any`
- **`width`** `any`
- **`signed`** `any`

**Returns:** `(pointer: any) => any`

**Calls:**

- `complex_call_37618`
- `complex_call_37681`
- `complex_call_37766`
- `complex_call_37833`
- `complex_call_37922`
- `complex_call_37989`

<details><summary>Code</summary>

```typescript
(name,width,signed)=>{switch(width){case 1:return signed?function(pointer){return this["fromWireType"](HEAP8[pointer])}:function(pointer){return this["fromWireType"](HEAPU8[pointer])};case 2:return signed?function(pointer){return this["fromWireType"](HEAP16[pointer>>1])}:function(pointer){return this["fromWireType"](HEAPU16[pointer>>1])};case 4:return signed?function(pointer){return this["fromWireType"](HEAP32[pointer>>2])}:function(pointer){return this["fromWireType"](HEAPU32[pointer>>2])};default:throw new TypeError(`invalid integer width (${width}): ${name}`)}}
```
</details>

### `__embind_register_enum(rawType: any, name: any, size: any, isSigned: any): void`

**Parameters:**

- **`rawType`** `any`
- **`name`** `any`
- **`size`** `any`
- **`isSigned`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `registerType`
- `enumReadValueFromPointer`
- `exposePublicSymbol`

<details><summary>Code</summary>

```typescript
(rawType,name,size,isSigned)=>{name=readLatin1String(name);function ctor(){}ctor.values={};registerType(rawType,{name:name,constructor:ctor,fromWireType:function(c){return this.constructor.values[c]},toWireType:(destructors,c)=>c.value,argPackAdvance:GenericWireTypeSize,readValueFromPointer:enumReadValueFromPointer(name,size,isSigned),destructorFunction:null});exposePublicSymbol(name,ctor)}
```
</details>

### `ctor(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ctor(){}
```
</details>

### `fromWireType(c: any): any`

**Parameters:**

- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(c){return this.constructor.values[c]}
```
</details>

### `toWireType(destructors: any, c: any): any`

**Parameters:**

- **`destructors`** `any`
- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,c)=>c.value
```
</details>

### `fromWireType(c: any): any`

**Parameters:**

- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(c){return this.constructor.values[c]}
```
</details>

### `toWireType(destructors: any, c: any): any`

**Parameters:**

- **`destructors`** `any`
- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,c)=>c.value
```
</details>

### `fromWireType(c: any): any`

**Parameters:**

- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(c){return this.constructor.values[c]}
```
</details>

### `toWireType(destructors: any, c: any): any`

**Parameters:**

- **`destructors`** `any`
- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,c)=>c.value
```
</details>

### `fromWireType(c: any): any`

**Parameters:**

- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(c){return this.constructor.values[c]}
```
</details>

### `toWireType(destructors: any, c: any): any`

**Parameters:**

- **`destructors`** `any`
- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,c)=>c.value
```
</details>

### `requireRegisteredType(rawType: any, humanName: any): any`

**Parameters:**

- **`rawType`** `any`
- **`humanName`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `getTypeName`

<details><summary>Code</summary>

```typescript
(rawType,humanName)=>{var impl=registeredTypes[rawType];if(undefined===impl){throwBindingError(`${humanName} has unknown type ${getTypeName(rawType)}`)}return impl}
```
</details>

### `__embind_register_enum_value(rawEnumType: any, name: any, enumValue: any): void`

**Parameters:**

- **`rawEnumType`** `any`
- **`name`** `any`
- **`enumValue`** `any`

**Returns:** `void`

**Calls:**

- `requireRegisteredType`
- `readLatin1String`
- `Object.create`
- `createNamedFunction`

<details><summary>Code</summary>

```typescript
(rawEnumType,name,enumValue)=>{var enumType=requireRegisteredType(rawEnumType,"enum");name=readLatin1String(name);var Enum=enumType.constructor;var Value=Object.create(enumType.constructor.prototype,{value:{value:enumValue},constructor:{value:createNamedFunction(`${enumType.name}_${name}`,function(){})}});Enum.values[enumValue]=Value;Enum[name]=Value}
```
</details>

### `embindRepr(v: any): any`

**Parameters:**

- **`v`** `any`

**Returns:** `any`

**Calls:**

- `v.toString`

<details><summary>Code</summary>

```typescript
v=>{if(v===null){return"null"}var t=typeof v;if(t==="object"||t==="array"||t==="function"){return v.toString()}else{return""+v}}
```
</details>

### `floatReadValueFromPointer(name: any, width: any): (pointer: any) => any`

**Parameters:**

- **`name`** `any`
- **`width`** `any`

**Returns:** `(pointer: any) => any`

**Calls:**

- `complex_call_39348`
- `complex_call_39430`

<details><summary>Code</summary>

```typescript
(name,width)=>{switch(width){case 4:return function(pointer){return this["fromWireType"](HEAPF32[pointer>>2])};case 8:return function(pointer){return this["fromWireType"](HEAPF64[pointer>>3])};default:throw new TypeError(`invalid float width (${width}): ${name}`)}}
```
</details>

### `__embind_register_float(rawType: any, name: any, size: any): void`

**Parameters:**

- **`rawType`** `any`
- **`name`** `any`
- **`size`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `registerType`
- `floatReadValueFromPointer`

<details><summary>Code</summary>

```typescript
(rawType,name,size)=>{name=readLatin1String(name);registerType(rawType,{name:name,fromWireType:value=>value,toWireType:(destructors,value)=>value,argPackAdvance:GenericWireTypeSize,readValueFromPointer:floatReadValueFromPointer(name,size),destructorFunction:null})}
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
value=>value
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,value)=>value
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
value=>value
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,value)=>value
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
value=>value
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,value)=>value
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
value=>value
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,value)=>value
```
</details>

### `__embind_register_function(name: any, argCount: any, rawArgTypesAddr: any, signature: any, rawInvoker: any, fn: any, isAsync: any): void`

**Parameters:**

- **`name`** `any`
- **`argCount`** `any`
- **`rawArgTypesAddr`** `any`
- **`signature`** `any`
- **`rawInvoker`** `any`
- **`fn`** `any`
- **`isAsync`** `any`

**Returns:** `void`

**Calls:**

- `heap32VectorToArray`
- `readLatin1String`
- `getFunctionName`
- `embind__requireFunction`
- `exposePublicSymbol`
- `throwUnboundTypeError`
- `whenDependentTypesAreResolved`
- `[argTypes[0],null].concat`
- `argTypes.slice`
- `replacePublicSymbol`
- `craftInvokerFunction`

<details><summary>Code</summary>

```typescript
(name,argCount,rawArgTypesAddr,signature,rawInvoker,fn,isAsync)=>{var argTypes=heap32VectorToArray(argCount,rawArgTypesAddr);name=readLatin1String(name);name=getFunctionName(name);rawInvoker=embind__requireFunction(signature,rawInvoker);exposePublicSymbol(name,function(){throwUnboundTypeError(`Cannot call ${name} due to unbound types`,argTypes)},argCount-1);whenDependentTypesAreResolved([],argTypes,argTypes=>{var invokerArgsArray=[argTypes[0],null].concat(argTypes.slice(1));replacePublicSymbol(name,craftInvokerFunction(name,invokerArgsArray,null,rawInvoker,fn,isAsync),argCount-1);return[]})}
```
</details>

### `integerReadValueFromPointer(name: any, width: any, signed: any): (pointer: any) => any`

**Parameters:**

- **`name`** `any`
- **`width`** `any`
- **`signed`** `any`

**Returns:** `(pointer: any) => any`

<details><summary>Code</summary>

```typescript
(name,width,signed)=>{switch(width){case 1:return signed?pointer=>HEAP8[pointer]:pointer=>HEAPU8[pointer];case 2:return signed?pointer=>HEAP16[pointer>>1]:pointer=>HEAPU16[pointer>>1];case 4:return signed?pointer=>HEAP32[pointer>>2]:pointer=>HEAPU32[pointer>>2];default:throw new TypeError(`invalid integer width (${width}): ${name}`)}}
```
</details>

### `__embind_register_integer(primitiveType: any, name: any, size: any, minRange: any, maxRange: any): void`

**Parameters:**

- **`primitiveType`** `any`
- **`name`** `any`
- **`size`** `any`
- **`minRange`** `any`
- **`maxRange`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `name.includes`
- `checkAssertions`
- `registerType`
- `integerReadValueFromPointer`

<details><summary>Code</summary>

```typescript
(primitiveType,name,size,minRange,maxRange)=>{name=readLatin1String(name);if(maxRange===-1){maxRange=4294967295}var fromWireType=value=>value;if(minRange===0){var bitshift=32-8*size;fromWireType=value=>value<<bitshift>>>bitshift}var isUnsignedType=name.includes("unsigned");var checkAssertions=(value,toTypeName)=>{};var toWireType;if(isUnsignedType){toWireType=function(destructors,value){checkAssertions(value,this.name);return value>>>0}}else{toWireType=function(destructors,value){checkAssertions(value,this.name);return value}}registerType(primitiveType,{name:name,fromWireType:fromWireType,toWireType:toWireType,argPackAdvance:GenericWireTypeSize,readValueFromPointer:integerReadValueFromPointer(name,size,minRange!==0),destructorFunction:null})}
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
value=>value
```
</details>

### `checkAssertions(value: any, toTypeName: any): void`

**Parameters:**

- **`value`** `any`
- **`toTypeName`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
(value,toTypeName)=>{}
```
</details>

### `__embind_register_memory_view(rawType: any, dataTypeIndex: any, name: any): void`

**Parameters:**

- **`rawType`** `any`
- **`dataTypeIndex`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `registerType`

<details><summary>Code</summary>

```typescript
(rawType,dataTypeIndex,name)=>{var typeMapping=[Int8Array,Uint8Array,Int16Array,Uint16Array,Int32Array,Uint32Array,Float32Array,Float64Array];var TA=typeMapping[dataTypeIndex];function decodeMemoryView(handle){var size=HEAPU32[handle>>2];var data=HEAPU32[handle+4>>2];return new TA(HEAP8.buffer,data,size)}name=readLatin1String(name);registerType(rawType,{name:name,fromWireType:decodeMemoryView,argPackAdvance:GenericWireTypeSize,readValueFromPointer:decodeMemoryView},{ignoreDuplicateRegistrations:true})}
```
</details>

### `decodeMemoryView(handle: any): Float32Array<ArrayBuffer> | Uint32Array<ArrayBuffer> | Int32Array<ArrayBuffer> | Uint16Array<ArrayBuffer> | Float64Array<...> | Uint8Array<...> | Int8Array<...> | Int16Array<...>`

**Parameters:**

- **`handle`** `any`

**Returns:** `Float32Array<ArrayBuffer> | Uint32Array<ArrayBuffer> | Int32Array<ArrayBuffer> | Uint16Array<ArrayBuffer> | Float64Array<...> | Uint8Array<...> | Int8Array<...> | Int16Array<...>`

<details><summary>Code</summary>

```typescript
function decodeMemoryView(handle){var size=HEAPU32[handle>>2];var data=HEAPU32[handle+4>>2];return new TA(HEAP8.buffer,data,size)}
```
</details>

### `stringToUTF8Array(str: any, heap: any, outIdx: any, maxBytesToWrite: any): number`

**Parameters:**

- **`str`** `any`
- **`heap`** `any`
- **`outIdx`** `any`
- **`maxBytesToWrite`** `any`

**Returns:** `number`

**Calls:**

- `str.charCodeAt`

<details><summary>Code</summary>

```typescript
(str,heap,outIdx,maxBytesToWrite)=>{if(!(maxBytesToWrite>0))return 0;var startIdx=outIdx;var endIdx=outIdx+maxBytesToWrite-1;for(var i=0;i<str.length;++i){var u=str.charCodeAt(i);if(u>=55296&&u<=57343){var u1=str.charCodeAt(++i);u=65536+((u&1023)<<10)|u1&1023}if(u<=127){if(outIdx>=endIdx)break;heap[outIdx++]=u}else if(u<=2047){if(outIdx+1>=endIdx)break;heap[outIdx++]=192|u>>6;heap[outIdx++]=128|u&63}else if(u<=65535){if(outIdx+2>=endIdx)break;heap[outIdx++]=224|u>>12;heap[outIdx++]=128|u>>6&63;heap[outIdx++]=128|u&63}else{if(outIdx+3>=endIdx)break;heap[outIdx++]=240|u>>18;heap[outIdx++]=128|u>>12&63;heap[outIdx++]=128|u>>6&63;heap[outIdx++]=128|u&63}}heap[outIdx]=0;return outIdx-startIdx}
```
</details>

### `stringToUTF8(str: any, outPtr: any, maxBytesToWrite: any): number`

**Parameters:**

- **`str`** `any`
- **`outPtr`** `any`
- **`maxBytesToWrite`** `any`

**Returns:** `number`

**Calls:**

- `stringToUTF8Array`

<details><summary>Code</summary>

```typescript
(str,outPtr,maxBytesToWrite)=>stringToUTF8Array(str,HEAPU8,outPtr,maxBytesToWrite)
```
</details>

### `lengthBytesUTF8(str: any): number`

**Parameters:**

- **`str`** `any`

**Returns:** `number`

**Calls:**

- `str.charCodeAt`

<details><summary>Code</summary>

```typescript
str=>{var len=0;for(var i=0;i<str.length;++i){var c=str.charCodeAt(i);if(c<=127){len++}else if(c<=2047){len+=2}else if(c>=55296&&c<=57343){len+=4;++i}else{len+=3}}return len}
```
</details>

### `UTF8ArrayToString(heapOrArray: any, idx: any, maxBytesToRead: any): string`

**Parameters:**

- **`heapOrArray`** `any`
- **`idx`** `any`
- **`maxBytesToRead`** `any`

**Returns:** `string`

**Calls:**

- `UTF8Decoder.decode`
- `heapOrArray.subarray`
- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
(heapOrArray,idx,maxBytesToRead)=>{var endIdx=idx+maxBytesToRead;var endPtr=idx;while(heapOrArray[endPtr]&&!(endPtr>=endIdx))++endPtr;if(endPtr-idx>16&&heapOrArray.buffer&&UTF8Decoder){return UTF8Decoder.decode(heapOrArray.subarray(idx,endPtr))}var str="";while(idx<endPtr){var u0=heapOrArray[idx++];if(!(u0&128)){str+=String.fromCharCode(u0);continue}var u1=heapOrArray[idx++]&63;if((u0&224)==192){str+=String.fromCharCode((u0&31)<<6|u1);continue}var u2=heapOrArray[idx++]&63;if((u0&240)==224){u0=(u0&15)<<12|u1<<6|u2}else{u0=(u0&7)<<18|u1<<12|u2<<6|heapOrArray[idx++]&63}if(u0<65536){str+=String.fromCharCode(u0)}else{var ch=u0-65536;str+=String.fromCharCode(55296|ch>>10,56320|ch&1023)}}return str}
```
</details>

### `UTF8ToString(ptr: any, maxBytesToRead: any): string`

**Parameters:**

- **`ptr`** `any`
- **`maxBytesToRead`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
(ptr,maxBytesToRead)=>ptr?UTF8ArrayToString(HEAPU8,ptr,maxBytesToRead):""
```
</details>

### `__embind_register_std_string(rawType: any, name: any): void`

**Parameters:**

- **`rawType`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `registerType`
- `UTF8ToString`
- `String.fromCharCode`
- `a.join`
- `_free`
- `throwBindingError`
- `lengthBytesUTF8`
- `_malloc`
- `stringToUTF8`
- `value.charCodeAt`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(rawType,name)=>{name=readLatin1String(name);var stdStringIsUTF8=name==="std::string";registerType(rawType,{name:name,fromWireType(value){var length=HEAPU32[value>>2];var payload=value+4;var str;if(stdStringIsUTF8){var decodeStartPtr=payload;for(var i=0;i<=length;++i){var currentBytePtr=payload+i;if(i==length||HEAPU8[currentBytePtr]==0){var maxRead=currentBytePtr-decodeStartPtr;var stringSegment=UTF8ToString(decodeStartPtr,maxRead);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+1}}}else{var a=new Array(length);for(var i=0;i<length;++i){a[i]=String.fromCharCode(HEAPU8[payload+i])}str=a.join("")}_free(value);return str},toWireType(destructors,value){if(value instanceof ArrayBuffer){value=new Uint8Array(value)}var length;var valueIsOfTypeString=typeof value=="string";if(!(valueIsOfTypeString||value instanceof Uint8Array||value instanceof Uint8ClampedArray||value instanceof Int8Array)){throwBindingError("Cannot pass non-string to std::string")}if(stdStringIsUTF8&&valueIsOfTypeString){length=lengthBytesUTF8(value)}else{length=value.length}var base=_malloc(4+length+1);var ptr=base+4;HEAPU32[base>>2]=length;if(stdStringIsUTF8&&valueIsOfTypeString){stringToUTF8(value,ptr,length+1)}else{if(valueIsOfTypeString){for(var i=0;i<length;++i){var charCode=value.charCodeAt(i);if(charCode>255){_free(ptr);throwBindingError("String has UTF-16 code units that do not fit in 8 bits")}HEAPU8[ptr+i]=charCode}}else{for(var i=0;i<length;++i){HEAPU8[ptr+i]=value[i]}}}if(destructors!==null){destructors.push(_free,base)}return base},argPackAdvance:GenericWireTypeSize,readValueFromPointer:readPointer,destructorFunction(ptr){_free(ptr)}})}
```
</details>

### `UTF16ToString(ptr: any, maxBytesToRead: any): string`

**Parameters:**

- **`ptr`** `any`
- **`maxBytesToRead`** `any`

**Returns:** `string`

**Calls:**

- `UTF16Decoder.decode`
- `HEAPU8.subarray`
- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
(ptr,maxBytesToRead)=>{var endPtr=ptr;var idx=endPtr>>1;var maxIdx=idx+maxBytesToRead/2;while(!(idx>=maxIdx)&&HEAPU16[idx])++idx;endPtr=idx<<1;if(endPtr-ptr>32&&UTF16Decoder)return UTF16Decoder.decode(HEAPU8.subarray(ptr,endPtr));var str="";for(var i=0;!(i>=maxBytesToRead/2);++i){var codeUnit=HEAP16[ptr+i*2>>1];if(codeUnit==0)break;str+=String.fromCharCode(codeUnit)}return str}
```
</details>

### `stringToUTF16(str: any, outPtr: any, maxBytesToWrite: any): number`

**Parameters:**

- **`str`** `any`
- **`outPtr`** `any`
- **`maxBytesToWrite`** `any`

**Returns:** `number`

**Calls:**

- `str.charCodeAt`

<details><summary>Code</summary>

```typescript
(str,outPtr,maxBytesToWrite)=>{maxBytesToWrite??=2147483647;if(maxBytesToWrite<2)return 0;maxBytesToWrite-=2;var startPtr=outPtr;var numCharsToWrite=maxBytesToWrite<str.length*2?maxBytesToWrite/2:str.length;for(var i=0;i<numCharsToWrite;++i){var codeUnit=str.charCodeAt(i);HEAP16[outPtr>>1]=codeUnit;outPtr+=2}HEAP16[outPtr>>1]=0;return outPtr-startPtr}
```
</details>

### `lengthBytesUTF16(str: any): number`

**Parameters:**

- **`str`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
str=>str.length*2
```
</details>

### `UTF32ToString(ptr: any, maxBytesToRead: any): string`

**Parameters:**

- **`ptr`** `any`
- **`maxBytesToRead`** `any`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
(ptr,maxBytesToRead)=>{var i=0;var str="";while(!(i>=maxBytesToRead/4)){var utf32=HEAP32[ptr+i*4>>2];if(utf32==0)break;++i;if(utf32>=65536){var ch=utf32-65536;str+=String.fromCharCode(55296|ch>>10,56320|ch&1023)}else{str+=String.fromCharCode(utf32)}}return str}
```
</details>

### `stringToUTF32(str: any, outPtr: any, maxBytesToWrite: any): number`

**Parameters:**

- **`str`** `any`
- **`outPtr`** `any`
- **`maxBytesToWrite`** `any`

**Returns:** `number`

**Calls:**

- `str.charCodeAt`

<details><summary>Code</summary>

```typescript
(str,outPtr,maxBytesToWrite)=>{maxBytesToWrite??=2147483647;if(maxBytesToWrite<4)return 0;var startPtr=outPtr;var endPtr=startPtr+maxBytesToWrite-4;for(var i=0;i<str.length;++i){var codeUnit=str.charCodeAt(i);if(codeUnit>=55296&&codeUnit<=57343){var trailSurrogate=str.charCodeAt(++i);codeUnit=65536+((codeUnit&1023)<<10)|trailSurrogate&1023}HEAP32[outPtr>>2]=codeUnit;outPtr+=4;if(outPtr+4>endPtr)break}HEAP32[outPtr>>2]=0;return outPtr-startPtr}
```
</details>

### `lengthBytesUTF32(str: any): number`

**Parameters:**

- **`str`** `any`

**Returns:** `number`

**Calls:**

- `str.charCodeAt`

<details><summary>Code</summary>

```typescript
str=>{var len=0;for(var i=0;i<str.length;++i){var codeUnit=str.charCodeAt(i);if(codeUnit>=55296&&codeUnit<=57343)++i;len+=4}return len}
```
</details>

### `__embind_register_std_wstring(rawType: any, charSize: any, name: any): void`

**Parameters:**

- **`rawType`** `any`
- **`charSize`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `registerType`
- `readCharAt`
- `decodeString`
- `String.fromCharCode`
- `_free`
- `throwBindingError`
- `lengthBytesUTF`
- `_malloc`
- `encodeString`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(rawType,charSize,name)=>{name=readLatin1String(name);var decodeString,encodeString,readCharAt,lengthBytesUTF;if(charSize===2){decodeString=UTF16ToString;encodeString=stringToUTF16;lengthBytesUTF=lengthBytesUTF16;readCharAt=pointer=>HEAPU16[pointer>>1]}else if(charSize===4){decodeString=UTF32ToString;encodeString=stringToUTF32;lengthBytesUTF=lengthBytesUTF32;readCharAt=pointer=>HEAPU32[pointer>>2]}registerType(rawType,{name:name,fromWireType:value=>{var length=HEAPU32[value>>2];var str;var decodeStartPtr=value+4;for(var i=0;i<=length;++i){var currentBytePtr=value+4+i*charSize;if(i==length||readCharAt(currentBytePtr)==0){var maxReadBytes=currentBytePtr-decodeStartPtr;var stringSegment=decodeString(decodeStartPtr,maxReadBytes);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+charSize}}_free(value);return str},toWireType:(destructors,value)=>{if(!(typeof value=="string")){throwBindingError(`Cannot pass non-string to C++ string type ${name}`)}var length=lengthBytesUTF(value);var ptr=_malloc(4+length+charSize);HEAPU32[ptr>>2]=length/charSize;encodeString(value,ptr+4,length+charSize);if(destructors!==null){destructors.push(_free,ptr)}return ptr},argPackAdvance:GenericWireTypeSize,readValueFromPointer:readPointer,destructorFunction(ptr){_free(ptr)}})}
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `readCharAt`
- `decodeString`
- `String.fromCharCode`
- `_free`

<details><summary>Code</summary>

```typescript
value=>{var length=HEAPU32[value>>2];var str;var decodeStartPtr=value+4;for(var i=0;i<=length;++i){var currentBytePtr=value+4+i*charSize;if(i==length||readCharAt(currentBytePtr)==0){var maxReadBytes=currentBytePtr-decodeStartPtr;var stringSegment=decodeString(decodeStartPtr,maxReadBytes);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+charSize}}_free(value);return str}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `lengthBytesUTF`
- `_malloc`
- `encodeString`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,value)=>{if(!(typeof value=="string")){throwBindingError(`Cannot pass non-string to C++ string type ${name}`)}var length=lengthBytesUTF(value);var ptr=_malloc(4+length+charSize);HEAPU32[ptr>>2]=length/charSize;encodeString(value,ptr+4,length+charSize);if(destructors!==null){destructors.push(_free,ptr)}return ptr}
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `readCharAt`
- `decodeString`
- `String.fromCharCode`
- `_free`

<details><summary>Code</summary>

```typescript
value=>{var length=HEAPU32[value>>2];var str;var decodeStartPtr=value+4;for(var i=0;i<=length;++i){var currentBytePtr=value+4+i*charSize;if(i==length||readCharAt(currentBytePtr)==0){var maxReadBytes=currentBytePtr-decodeStartPtr;var stringSegment=decodeString(decodeStartPtr,maxReadBytes);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+charSize}}_free(value);return str}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `lengthBytesUTF`
- `_malloc`
- `encodeString`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,value)=>{if(!(typeof value=="string")){throwBindingError(`Cannot pass non-string to C++ string type ${name}`)}var length=lengthBytesUTF(value);var ptr=_malloc(4+length+charSize);HEAPU32[ptr>>2]=length/charSize;encodeString(value,ptr+4,length+charSize);if(destructors!==null){destructors.push(_free,ptr)}return ptr}
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `readCharAt`
- `decodeString`
- `String.fromCharCode`
- `_free`

<details><summary>Code</summary>

```typescript
value=>{var length=HEAPU32[value>>2];var str;var decodeStartPtr=value+4;for(var i=0;i<=length;++i){var currentBytePtr=value+4+i*charSize;if(i==length||readCharAt(currentBytePtr)==0){var maxReadBytes=currentBytePtr-decodeStartPtr;var stringSegment=decodeString(decodeStartPtr,maxReadBytes);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+charSize}}_free(value);return str}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `lengthBytesUTF`
- `_malloc`
- `encodeString`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,value)=>{if(!(typeof value=="string")){throwBindingError(`Cannot pass non-string to C++ string type ${name}`)}var length=lengthBytesUTF(value);var ptr=_malloc(4+length+charSize);HEAPU32[ptr>>2]=length/charSize;encodeString(value,ptr+4,length+charSize);if(destructors!==null){destructors.push(_free,ptr)}return ptr}
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `readCharAt`
- `decodeString`
- `String.fromCharCode`
- `_free`

<details><summary>Code</summary>

```typescript
value=>{var length=HEAPU32[value>>2];var str;var decodeStartPtr=value+4;for(var i=0;i<=length;++i){var currentBytePtr=value+4+i*charSize;if(i==length||readCharAt(currentBytePtr)==0){var maxReadBytes=currentBytePtr-decodeStartPtr;var stringSegment=decodeString(decodeStartPtr,maxReadBytes);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+charSize}}_free(value);return str}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `lengthBytesUTF`
- `_malloc`
- `encodeString`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,value)=>{if(!(typeof value=="string")){throwBindingError(`Cannot pass non-string to C++ string type ${name}`)}var length=lengthBytesUTF(value);var ptr=_malloc(4+length+charSize);HEAPU32[ptr>>2]=length/charSize;encodeString(value,ptr+4,length+charSize);if(destructors!==null){destructors.push(_free,ptr)}return ptr}
```
</details>

### `__embind_register_value_object(rawType: any, name: any, constructorSignature: any, rawConstructor: any, destructorSignature: any, rawDestructor: any): void`

**Parameters:**

- **`rawType`** `any`
- **`name`** `any`
- **`constructorSignature`** `any`
- **`rawConstructor`** `any`
- **`destructorSignature`** `any`
- **`rawDestructor`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `embind__requireFunction`

<details><summary>Code</summary>

```typescript
(rawType,name,constructorSignature,rawConstructor,destructorSignature,rawDestructor)=>{structRegistrations[rawType]={name:readLatin1String(name),rawConstructor:embind__requireFunction(constructorSignature,rawConstructor),rawDestructor:embind__requireFunction(destructorSignature,rawDestructor),fields:[]}}
```
</details>

### `__embind_register_value_object_field(structType: any, fieldName: any, getterReturnType: any, getterSignature: any, getter: any, getterContext: any, setterArgumentType: any, setterSignature: any, setter: any, setterContext: any): void`

**Parameters:**

- **`structType`** `any`
- **`fieldName`** `any`
- **`getterReturnType`** `any`
- **`getterSignature`** `any`
- **`getter`** `any`
- **`getterContext`** `any`
- **`setterArgumentType`** `any`
- **`setterSignature`** `any`
- **`setter`** `any`
- **`setterContext`** `any`

**Returns:** `void`

**Calls:**

- `structRegistrations[structType].fields.push`
- `readLatin1String`
- `embind__requireFunction`

<details><summary>Code</summary>

```typescript
(structType,fieldName,getterReturnType,getterSignature,getter,getterContext,setterArgumentType,setterSignature,setter,setterContext)=>{structRegistrations[structType].fields.push({fieldName:readLatin1String(fieldName),getterReturnType:getterReturnType,getter:embind__requireFunction(getterSignature,getter),getterContext:getterContext,setterArgumentType:setterArgumentType,setter:embind__requireFunction(setterSignature,setter),setterContext:setterContext})}
```
</details>

### `__embind_register_void(rawType: any, name: any): void`

**Parameters:**

- **`rawType`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `readLatin1String`
- `registerType`

<details><summary>Code</summary>

```typescript
(rawType,name)=>{name=readLatin1String(name);registerType(rawType,{isVoid:true,name:name,argPackAdvance:0,fromWireType:()=>undefined,toWireType:(destructors,o)=>undefined})}
```
</details>

### `fromWireType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
()=>undefined
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,o)=>undefined
```
</details>

### `fromWireType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
()=>undefined
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,o)=>undefined
```
</details>

### `fromWireType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
()=>undefined
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,o)=>undefined
```
</details>

### `fromWireType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
()=>undefined
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,o)=>undefined
```
</details>

### `__emscripten_memcpy_js(dest: any, src: any, num: any): any`

**Parameters:**

- **`dest`** `any`
- **`src`** `any`
- **`num`** `any`

**Returns:** `any`

**Calls:**

- `HEAPU8.copyWithin`

<details><summary>Code</summary>

```typescript
(dest,src,num)=>HEAPU8.copyWithin(dest,src,src+num)
```
</details>

### `emval_returnValue(returnType: any, destructorsRef: any, handle: any): any`

**Parameters:**

- **`returnType`** `any`
- **`destructorsRef`** `any`
- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_50190`
- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(returnType,destructorsRef,handle)=>{var destructors=[];var result=returnType["toWireType"](destructors,handle);if(destructors.length){HEAPU32[destructorsRef>>2]=Emval.toHandle(destructors)}return result}
```
</details>

### `__emval_as(handle: any, returnType: any, destructorsRef: any): any`

**Parameters:**

- **`handle`** `any`
- **`returnType`** `any`
- **`destructorsRef`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `requireRegisteredType`
- `emval_returnValue`

<details><summary>Code</summary>

```typescript
(handle,returnType,destructorsRef)=>{handle=Emval.toValue(handle);returnType=requireRegisteredType(returnType,"emval::as");return emval_returnValue(returnType,destructorsRef,handle)}
```
</details>

### `__emval_call(caller: any, handle: any, destructorsRef: any, args: any): any`

**Parameters:**

- **`caller`** `any`
- **`handle`** `any`
- **`destructorsRef`** `any`
- **`args`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `caller`

<details><summary>Code</summary>

```typescript
(caller,handle,destructorsRef,args)=>{caller=emval_methodCallers[caller];handle=Emval.toValue(handle);return caller(null,handle,destructorsRef,args)}
```
</details>

### `getStringOrSymbol(address: any): any`

**Parameters:**

- **`address`** `any`

**Returns:** `any`

**Calls:**

- `readLatin1String`

<details><summary>Code</summary>

```typescript
address=>{var symbol=emval_symbols[address];if(symbol===undefined){return readLatin1String(address)}return symbol}
```
</details>

### `__emval_call_method(caller: any, objHandle: any, methodName: any, destructorsRef: any, args: any): any`

**Parameters:**

- **`caller`** `any`
- **`objHandle`** `any`
- **`methodName`** `any`
- **`destructorsRef`** `any`
- **`args`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `getStringOrSymbol`
- `caller`

<details><summary>Code</summary>

```typescript
(caller,objHandle,methodName,destructorsRef,args)=>{caller=emval_methodCallers[caller];objHandle=Emval.toValue(objHandle);methodName=getStringOrSymbol(methodName);return caller(objHandle,objHandle[methodName],destructorsRef,args)}
```
</details>

### `emval_get_global(): any`

**Returns:** `any`

**Calls:**

- `complex_call_51216`

<details><summary>Code</summary>

```typescript
()=>{if(typeof globalThis=="object"){return globalThis}return function(){return Function}()("return this")()}
```
</details>

### `__emval_get_global(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`
- `emval_get_global`
- `getStringOrSymbol`

<details><summary>Code</summary>

```typescript
name=>{if(name===0){return Emval.toHandle(emval_get_global())}else{name=getStringOrSymbol(name);return Emval.toHandle(emval_get_global()[name])}}
```
</details>

### `emval_addMethodCaller(caller: any): number`

**Parameters:**

- **`caller`** `any`

**Returns:** `number`

**Calls:**

- `emval_methodCallers.push`

<details><summary>Code</summary>

```typescript
caller=>{var id=emval_methodCallers.length;emval_methodCallers.push(caller);return id}
```
</details>

### `emval_lookupTypes(argCount: any, argTypes: any): any[]`

**Parameters:**

- **`argCount`** `any`
- **`argTypes`** `any`

**Returns:** `any[]`

**Calls:**

- `requireRegisteredType`

<details><summary>Code</summary>

```typescript
(argCount,argTypes)=>{var a=new Array(argCount);for(var i=0;i<argCount;++i){a[i]=requireRegisteredType(HEAPU32[argTypes+i*4>>2],"parameter "+i)}return a}
```
</details>

### `__emval_get_method_caller(argCount: any, argTypes: any, kind: any): number`

**Parameters:**

- **`argCount`** `any`
- **`argTypes`** `any`
- **`kind`** `any`

**Returns:** `number`

**Calls:**

- `emval_lookupTypes`
- `types.shift`
- `argsList.push`
- `params.push`
- `args.push`
- `argsList.join`
- `complex_call_52641`
- `types.map(t=>t.name).join`
- `emval_addMethodCaller`
- `createNamedFunction`

<details><summary>Code</summary>

```typescript
(argCount,argTypes,kind)=>{var types=emval_lookupTypes(argCount,argTypes);var retType=types.shift();argCount--;var functionBody=`return function (obj, func, destructorsRef, args) {\n`;var offset=0;var argsList=[];if(kind===0){argsList.push("obj")}var params=["retType"];var args=[retType];for(var i=0;i<argCount;++i){argsList.push("arg"+i);params.push("argType"+i);args.push(types[i]);functionBody+=`  var arg${i} = argType${i}.readValueFromPointer(args${offset?"+"+offset:""});\n`;offset+=types[i]["argPackAdvance"]}var invoker=kind===1?"new func":"func.call";functionBody+=`  var rv = ${invoker}(${argsList.join(", ")});\n`;if(!retType.isVoid){params.push("emval_returnValue");args.push(emval_returnValue);functionBody+="  return emval_returnValue(retType, destructorsRef, rv);\n"}functionBody+="};\n";params.push(functionBody);var invokerFunction=newFunc(Function,params)(...args);var functionName=`methodCaller<(${types.map(t=>t.name).join(", ")}) => ${retType.name}>`;return emval_addMethodCaller(createNamedFunction(functionName,invokerFunction))}
```
</details>

### `__emval_get_module_property(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `getStringOrSymbol`
- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
name=>{name=getStringOrSymbol(name);return Emval.toHandle(Module[name])}
```
</details>

### `__emval_get_property(handle: any, key: any): any`

**Parameters:**

- **`handle`** `any`
- **`key`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(handle,key)=>{handle=Emval.toValue(handle);key=Emval.toValue(key);return Emval.toHandle(handle[key])}
```
</details>

### `__emval_incref(handle: any): void`

**Parameters:**

- **`handle`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
handle=>{if(handle>9){emval_handles[handle+1]+=1}}
```
</details>

### `__emval_new_cstring(v: any): any`

**Parameters:**

- **`v`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
v=>Emval.toHandle(getStringOrSymbol(v))
```
</details>

### `__emval_run_destructors(handle: any): void`

**Parameters:**

- **`handle`** `any`

**Returns:** `void`

**Calls:**

- `Emval.toValue`
- `runDestructors`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var destructors=Emval.toValue(handle);runDestructors(destructors);__emval_decref(handle)}
```
</details>

### `getHeapMax(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
()=>2147483648
```
</details>

### `growMemory(size: any): number`

**Parameters:**

- **`size`** `any`

**Returns:** `number`

**Calls:**

- `wasmMemory.grow`
- `updateMemoryViews`

<details><summary>Code</summary>

```typescript
size=>{var b=wasmMemory.buffer;var pages=(size-b.byteLength+65535)/65536;try{wasmMemory.grow(pages);updateMemoryViews();return 1}catch(e){}}
```
</details>

### `_emscripten_resize_heap(requestedSize: any): boolean`

**Parameters:**

- **`requestedSize`** `any`

**Returns:** `boolean`

**Calls:**

- `getHeapMax`
- `Math.min`
- `alignUp`
- `Math.max`
- `growMemory`

<details><summary>Code</summary>

```typescript
requestedSize=>{var oldSize=HEAPU8.length;requestedSize>>>=0;var maxHeapSize=getHeapMax();if(requestedSize>maxHeapSize){return false}var alignUp=(x,multiple)=>x+(multiple-x%multiple)%multiple;for(var cutDown=1;cutDown<=4;cutDown*=2){var overGrownHeapSize=oldSize*(1+.2/cutDown);overGrownHeapSize=Math.min(overGrownHeapSize,requestedSize+100663296);var newSize=Math.min(maxHeapSize,alignUp(Math.max(requestedSize,overGrownHeapSize),65536));var replacement=growMemory(newSize);if(replacement){return true}}return false}
```
</details>

### `alignUp(x: any, multiple: any): any`

**Parameters:**

- **`x`** `any`
- **`multiple`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(x,multiple)=>x+(multiple-x%multiple)%multiple
```
</details>

### `_fd_close(fd: any): number`

**Parameters:**

- **`fd`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
fd=>52
```
</details>

### `convertI32PairToI53Checked(lo: any, hi: any): number`

**Parameters:**

- **`lo`** `any`
- **`hi`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
(lo,hi)=>hi+2097152>>>0<4194305-!!lo?(lo>>>0)+hi*4294967296:NaN
```
</details>

### `_fd_seek(fd: any, offset_low: any, offset_high: any, whence: any, newOffset: any): number`

**Parameters:**

- **`fd`** `any`
- **`offset_low`** `any`
- **`offset_high`** `any`
- **`whence`** `any`
- **`newOffset`** `any`

**Returns:** `number`

**Calls:**

- `convertI32PairToI53Checked`

<details><summary>Code</summary>

```typescript
function _fd_seek(fd,offset_low,offset_high,whence,newOffset){var offset=convertI32PairToI53Checked(offset_low,offset_high);return 70}
```
</details>

### `printChar(stream: any, curr: any): void`

**Parameters:**

- **`stream`** `any`
- **`curr`** `any`

**Returns:** `void`

**Calls:**

- `complex_call_54445`
- `UTF8ArrayToString`
- `buffer.push`

<details><summary>Code</summary>

```typescript
(stream,curr)=>{var buffer=printCharBuffers[stream];if(curr===0||curr===10){(stream===1?out:err)(UTF8ArrayToString(buffer,0));buffer.length=0}else{buffer.push(curr)}}
```
</details>

### `_fd_write(fd: any, iov: any, iovcnt: any, pnum: any): number`

**Parameters:**

- **`fd`** `any`
- **`iov`** `any`
- **`iovcnt`** `any`
- **`pnum`** `any`

**Returns:** `number`

**Calls:**

- `printChar`

<details><summary>Code</summary>

```typescript
(fd,iov,iovcnt,pnum)=>{var num=0;for(var i=0;i<iovcnt;i++){var ptr=HEAPU32[iov>>2];var len=HEAPU32[iov+4>>2];iov+=8;for(var j=0;j<len;j++){printChar(fd,HEAPU8[ptr+j])}num+=len}HEAPU32[pnum>>2]=num;return 0}
```
</details>

### `___wasm_call_ctors(): any`

**Returns:** `any`

**Calls:**

- `complex_call_56194`

<details><summary>Code</summary>

```typescript
()=>(___wasm_call_ctors=wasmExports["M"])()
```
</details>

### `___getTypeName(a0: any): any`

**Parameters:**

- **`a0`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_56257`

<details><summary>Code</summary>

```typescript
a0=>(___getTypeName=wasmExports["N"])(a0)
```
</details>

### `_malloc(a0: any): any`

**Parameters:**

- **`a0`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_56311`

<details><summary>Code</summary>

```typescript
a0=>(_malloc=wasmExports["O"])(a0)
```
</details>

### `_free(a0: any): any`

**Parameters:**

- **`a0`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_56356`

<details><summary>Code</summary>

```typescript
a0=>(_free=wasmExports["Q"])(a0)
```
</details>

### `___cxa_is_pointer_type(a0: any): any`

**Parameters:**

- **`a0`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_56416`

<details><summary>Code</summary>

```typescript
a0=>(___cxa_is_pointer_type=wasmExports["R"])(a0)
```
</details>

### `run(): void`

**Returns:** `void`

**Calls:**

- `preRun`
- `initRuntime`
- `readyPromiseResolve`
- `complex_call_56932`
- `postRun`
- `complex_call_57001`
- `setTimeout`
- `complex_call_57079`
- `doRun`

<details><summary>Code</summary>

```typescript
function run(){if(runDependencies>0){return}preRun();if(runDependencies>0){return}function doRun(){if(calledRun)return;calledRun=true;Module["calledRun"]=true;if(ABORT)return;initRuntime();readyPromiseResolve(Module);Module["onRuntimeInitialized"]?.();postRun()}if(Module["setStatus"]){Module["setStatus"]("Running...");setTimeout(function(){setTimeout(function(){Module["setStatus"]("")},1);doRun()},1)}else{doRun()}}
```
</details>

### `doRun(): void`

**Returns:** `void`

**Calls:**

- `initRuntime`
- `readyPromiseResolve`
- `complex_call_56932`
- `postRun`

<details><summary>Code</summary>

```typescript
function doRun(){if(calledRun)return;calledRun=true;Module["calledRun"]=true;if(ABORT)return;initRuntime();readyPromiseResolve(Module);Module["onRuntimeInitialized"]?.();postRun()}
```
</details>

### `ExceptionInfo.set_type(type: any): void`

**Parameters:**

- **`type`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_type(type){HEAPU32[this.ptr+4>>2]=type}
```
</details>

### `ExceptionInfo.get_type(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
get_type(){return HEAPU32[this.ptr+4>>2]}
```
</details>

### `ExceptionInfo.set_destructor(destructor: any): void`

**Parameters:**

- **`destructor`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_destructor(destructor){HEAPU32[this.ptr+8>>2]=destructor}
```
</details>

### `ExceptionInfo.get_destructor(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
get_destructor(){return HEAPU32[this.ptr+8>>2]}
```
</details>

### `ExceptionInfo.set_caught(caught: any): void`

**Parameters:**

- **`caught`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_caught(caught){caught=caught?1:0;HEAP8[this.ptr+12]=caught}
```
</details>

### `ExceptionInfo.get_caught(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
get_caught(){return HEAP8[this.ptr+12]!=0}
```
</details>

### `ExceptionInfo.set_rethrown(rethrown: any): void`

**Parameters:**

- **`rethrown`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_rethrown(rethrown){rethrown=rethrown?1:0;HEAP8[this.ptr+13]=rethrown}
```
</details>

### `ExceptionInfo.get_rethrown(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
get_rethrown(){return HEAP8[this.ptr+13]!=0}
```
</details>

### `ExceptionInfo.init(type: any, destructor: any): void`

**Parameters:**

- **`type`** `any`
- **`destructor`** `any`

**Returns:** `void`

**Calls:**

- `this.set_adjusted_ptr`
- `this.set_type`
- `this.set_destructor`

<details><summary>Code</summary>

```typescript
init(type,destructor){this.set_adjusted_ptr(0);this.set_type(type);this.set_destructor(destructor)}
```
</details>

### `ExceptionInfo.set_adjusted_ptr(adjustedPtr: any): void`

**Parameters:**

- **`adjustedPtr`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
set_adjusted_ptr(adjustedPtr){HEAPU32[this.ptr+16>>2]=adjustedPtr}
```
</details>

### `ExceptionInfo.get_adjusted_ptr(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
get_adjusted_ptr(){return HEAPU32[this.ptr+16>>2]}
```
</details>

### `ExceptionInfo.get_exception_ptr(): any`

**Returns:** `any`

**Calls:**

- `___cxa_is_pointer_type`
- `this.get_type`
- `this.get_adjusted_ptr`

<details><summary>Code</summary>

```typescript
get_exception_ptr(){var isPointer=___cxa_is_pointer_type(this.get_type());if(isPointer){return HEAPU32[this.excPtr>>2]}var adjusted=this.get_adjusted_ptr();if(adjusted!==0)return adjusted;return this.excPtr}
```
</details>

### `read(ptr: any): any`

**Parameters:**

- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_10907`

<details><summary>Code</summary>

```typescript
ptr=>getterReturnType["fromWireType"](getter(getterContext,ptr))
```
</details>

### `write(ptr: any, o: any): void`

**Parameters:**

- **`ptr`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `setter`
- `complex_call_11027`
- `runDestructors`

<details><summary>Code</summary>

```typescript
(ptr,o)=>{var destructors=[];setter(setterContext,ptr,setterArgumentType["toWireType"](destructors,o));runDestructors(destructors)}
```
</details>

### `read(ptr: any): any`

**Parameters:**

- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_10907`

<details><summary>Code</summary>

```typescript
ptr=>getterReturnType["fromWireType"](getter(getterContext,ptr))
```
</details>

### `write(ptr: any, o: any): void`

**Parameters:**

- **`ptr`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `setter`
- `complex_call_11027`
- `runDestructors`

<details><summary>Code</summary>

```typescript
(ptr,o)=>{var destructors=[];setter(setterContext,ptr,setterArgumentType["toWireType"](destructors,o));runDestructors(destructors)}
```
</details>

### `fromWireType(ptr: any): {}`

**Parameters:**

- **`ptr`** `any`

**Returns:** `{}`

**Calls:**

- `fields[i].read`
- `rawDestructor`

<details><summary>Code</summary>

```typescript
ptr=>{var rv={};for(var i in fields){rv[i]=fields[i].read(ptr)}rawDestructor(ptr);return rv}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

**Calls:**

- `rawConstructor`
- `fields[fieldName].write`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,o)=>{for(var fieldName in fields){if(!(fieldName in o)){throw new TypeError(`Missing field: "${fieldName}"`)}}var ptr=rawConstructor();for(fieldName in fields){fields[fieldName].write(ptr,o[fieldName])}if(destructors!==null){destructors.push(rawDestructor,ptr)}return ptr}
```
</details>

### `fromWireType(ptr: any): {}`

**Parameters:**

- **`ptr`** `any`

**Returns:** `{}`

**Calls:**

- `fields[i].read`
- `rawDestructor`

<details><summary>Code</summary>

```typescript
ptr=>{var rv={};for(var i in fields){rv[i]=fields[i].read(ptr)}rawDestructor(ptr);return rv}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

**Calls:**

- `rawConstructor`
- `fields[fieldName].write`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,o)=>{for(var fieldName in fields){if(!(fieldName in o)){throw new TypeError(`Missing field: "${fieldName}"`)}}var ptr=rawConstructor();for(fieldName in fields){fields[fieldName].write(ptr,o[fieldName])}if(destructors!==null){destructors.push(rawDestructor,ptr)}return ptr}
```
</details>

### `read(ptr: any): any`

**Parameters:**

- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_10907`

<details><summary>Code</summary>

```typescript
ptr=>getterReturnType["fromWireType"](getter(getterContext,ptr))
```
</details>

### `write(ptr: any, o: any): void`

**Parameters:**

- **`ptr`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `setter`
- `complex_call_11027`
- `runDestructors`

<details><summary>Code</summary>

```typescript
(ptr,o)=>{var destructors=[];setter(setterContext,ptr,setterArgumentType["toWireType"](destructors,o));runDestructors(destructors)}
```
</details>

### `read(ptr: any): any`

**Parameters:**

- **`ptr`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_10907`

<details><summary>Code</summary>

```typescript
ptr=>getterReturnType["fromWireType"](getter(getterContext,ptr))
```
</details>

### `write(ptr: any, o: any): void`

**Parameters:**

- **`ptr`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `setter`
- `complex_call_11027`
- `runDestructors`

<details><summary>Code</summary>

```typescript
(ptr,o)=>{var destructors=[];setter(setterContext,ptr,setterArgumentType["toWireType"](destructors,o));runDestructors(destructors)}
```
</details>

### `fromWireType(ptr: any): {}`

**Parameters:**

- **`ptr`** `any`

**Returns:** `{}`

**Calls:**

- `fields[i].read`
- `rawDestructor`

<details><summary>Code</summary>

```typescript
ptr=>{var rv={};for(var i in fields){rv[i]=fields[i].read(ptr)}rawDestructor(ptr);return rv}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

**Calls:**

- `rawConstructor`
- `fields[fieldName].write`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,o)=>{for(var fieldName in fields){if(!(fieldName in o)){throw new TypeError(`Missing field: "${fieldName}"`)}}var ptr=rawConstructor();for(fieldName in fields){fields[fieldName].write(ptr,o[fieldName])}if(destructors!==null){destructors.push(rawDestructor,ptr)}return ptr}
```
</details>

### `fromWireType(ptr: any): {}`

**Parameters:**

- **`ptr`** `any`

**Returns:** `{}`

**Calls:**

- `fields[i].read`
- `rawDestructor`

<details><summary>Code</summary>

```typescript
ptr=>{var rv={};for(var i in fields){rv[i]=fields[i].read(ptr)}rawDestructor(ptr);return rv}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

**Calls:**

- `rawConstructor`
- `fields[fieldName].write`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,o)=>{for(var fieldName in fields){if(!(fieldName in o)){throw new TypeError(`Missing field: "${fieldName}"`)}}var ptr=rawConstructor();for(fieldName in fields){fields[fieldName].write(ptr,o[fieldName])}if(destructors!==null){destructors.push(rawDestructor,ptr)}return ptr}
```
</details>

### `fromWireType(wt: any): boolean`

**Parameters:**

- **`wt`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(wt){return!!wt}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(destructors,o){return o?trueValue:falseValue}
```
</details>

### `readValueFromPointer(pointer: any): any`

**Parameters:**

- **`pointer`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_13234`

<details><summary>Code</summary>

```typescript
function(pointer){return this["fromWireType"](HEAPU8[pointer])}
```
</details>

### `fromWireType(wt: any): boolean`

**Parameters:**

- **`wt`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(wt){return!!wt}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(destructors,o){return o?trueValue:falseValue}
```
</details>

### `readValueFromPointer(pointer: any): any`

**Parameters:**

- **`pointer`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_13234`

<details><summary>Code</summary>

```typescript
function(pointer){return this["fromWireType"](HEAPU8[pointer])}
```
</details>

### `fromWireType(wt: any): boolean`

**Parameters:**

- **`wt`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(wt){return!!wt}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(destructors,o){return o?trueValue:falseValue}
```
</details>

### `readValueFromPointer(pointer: any): any`

**Parameters:**

- **`pointer`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_13234`

<details><summary>Code</summary>

```typescript
function(pointer){return this["fromWireType"](HEAPU8[pointer])}
```
</details>

### `fromWireType(wt: any): boolean`

**Parameters:**

- **`wt`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function(wt){return!!wt}
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(destructors,o){return o?trueValue:falseValue}
```
</details>

### `readValueFromPointer(pointer: any): any`

**Parameters:**

- **`pointer`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_13234`

<details><summary>Code</summary>

```typescript
function(pointer){return this["fromWireType"](HEAPU8[pointer])}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `toValue(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`

<details><summary>Code</summary>

```typescript
handle=>{if(!handle){throwBindingError("Cannot use deleted val. handle = "+handle)}return emval_handles[handle]}
```
</details>

### `toHandle(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `emval_freelist.pop`

<details><summary>Code</summary>

```typescript
value=>{switch(value){case undefined:return 2;case null:return 4;case true:return 6;case false:return 8;default:{const handle=emval_freelist.pop()||emval_handles.length;emval_handles[handle]=value;emval_handles[handle+1]=1;return handle}}}
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(handle: any): any`

**Parameters:**

- **`handle`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toValue`
- `__emval_decref`

<details><summary>Code</summary>

```typescript
handle=>{var rv=Emval.toValue(handle);__emval_decref(handle);return rv}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `Emval.toHandle`

<details><summary>Code</summary>

```typescript
(destructors,value)=>Emval.toHandle(value)
```
</details>

### `fromWireType(c: any): any`

**Parameters:**

- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(c){return this.constructor.values[c]}
```
</details>

### `toWireType(destructors: any, c: any): any`

**Parameters:**

- **`destructors`** `any`
- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,c)=>c.value
```
</details>

### `fromWireType(c: any): any`

**Parameters:**

- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(c){return this.constructor.values[c]}
```
</details>

### `toWireType(destructors: any, c: any): any`

**Parameters:**

- **`destructors`** `any`
- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,c)=>c.value
```
</details>

### `fromWireType(c: any): any`

**Parameters:**

- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(c){return this.constructor.values[c]}
```
</details>

### `toWireType(destructors: any, c: any): any`

**Parameters:**

- **`destructors`** `any`
- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,c)=>c.value
```
</details>

### `fromWireType(c: any): any`

**Parameters:**

- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function(c){return this.constructor.values[c]}
```
</details>

### `toWireType(destructors: any, c: any): any`

**Parameters:**

- **`destructors`** `any`
- **`c`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,c)=>c.value
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
value=>value
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,value)=>value
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
value=>value
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,value)=>value
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
value=>value
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,value)=>value
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
value=>value
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,value)=>value
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `readCharAt`
- `decodeString`
- `String.fromCharCode`
- `_free`

<details><summary>Code</summary>

```typescript
value=>{var length=HEAPU32[value>>2];var str;var decodeStartPtr=value+4;for(var i=0;i<=length;++i){var currentBytePtr=value+4+i*charSize;if(i==length||readCharAt(currentBytePtr)==0){var maxReadBytes=currentBytePtr-decodeStartPtr;var stringSegment=decodeString(decodeStartPtr,maxReadBytes);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+charSize}}_free(value);return str}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `lengthBytesUTF`
- `_malloc`
- `encodeString`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,value)=>{if(!(typeof value=="string")){throwBindingError(`Cannot pass non-string to C++ string type ${name}`)}var length=lengthBytesUTF(value);var ptr=_malloc(4+length+charSize);HEAPU32[ptr>>2]=length/charSize;encodeString(value,ptr+4,length+charSize);if(destructors!==null){destructors.push(_free,ptr)}return ptr}
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `readCharAt`
- `decodeString`
- `String.fromCharCode`
- `_free`

<details><summary>Code</summary>

```typescript
value=>{var length=HEAPU32[value>>2];var str;var decodeStartPtr=value+4;for(var i=0;i<=length;++i){var currentBytePtr=value+4+i*charSize;if(i==length||readCharAt(currentBytePtr)==0){var maxReadBytes=currentBytePtr-decodeStartPtr;var stringSegment=decodeString(decodeStartPtr,maxReadBytes);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+charSize}}_free(value);return str}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `lengthBytesUTF`
- `_malloc`
- `encodeString`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,value)=>{if(!(typeof value=="string")){throwBindingError(`Cannot pass non-string to C++ string type ${name}`)}var length=lengthBytesUTF(value);var ptr=_malloc(4+length+charSize);HEAPU32[ptr>>2]=length/charSize;encodeString(value,ptr+4,length+charSize);if(destructors!==null){destructors.push(_free,ptr)}return ptr}
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `readCharAt`
- `decodeString`
- `String.fromCharCode`
- `_free`

<details><summary>Code</summary>

```typescript
value=>{var length=HEAPU32[value>>2];var str;var decodeStartPtr=value+4;for(var i=0;i<=length;++i){var currentBytePtr=value+4+i*charSize;if(i==length||readCharAt(currentBytePtr)==0){var maxReadBytes=currentBytePtr-decodeStartPtr;var stringSegment=decodeString(decodeStartPtr,maxReadBytes);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+charSize}}_free(value);return str}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `lengthBytesUTF`
- `_malloc`
- `encodeString`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,value)=>{if(!(typeof value=="string")){throwBindingError(`Cannot pass non-string to C++ string type ${name}`)}var length=lengthBytesUTF(value);var ptr=_malloc(4+length+charSize);HEAPU32[ptr>>2]=length/charSize;encodeString(value,ptr+4,length+charSize);if(destructors!==null){destructors.push(_free,ptr)}return ptr}
```
</details>

### `fromWireType(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `readCharAt`
- `decodeString`
- `String.fromCharCode`
- `_free`

<details><summary>Code</summary>

```typescript
value=>{var length=HEAPU32[value>>2];var str;var decodeStartPtr=value+4;for(var i=0;i<=length;++i){var currentBytePtr=value+4+i*charSize;if(i==length||readCharAt(currentBytePtr)==0){var maxReadBytes=currentBytePtr-decodeStartPtr;var stringSegment=decodeString(decodeStartPtr,maxReadBytes);if(str===undefined){str=stringSegment}else{str+=String.fromCharCode(0);str+=stringSegment}decodeStartPtr=currentBytePtr+charSize}}_free(value);return str}
```
</details>

### `toWireType(destructors: any, value: any): any`

**Parameters:**

- **`destructors`** `any`
- **`value`** `any`

**Returns:** `any`

**Calls:**

- `throwBindingError`
- `lengthBytesUTF`
- `_malloc`
- `encodeString`
- `destructors.push`

<details><summary>Code</summary>

```typescript
(destructors,value)=>{if(!(typeof value=="string")){throwBindingError(`Cannot pass non-string to C++ string type ${name}`)}var length=lengthBytesUTF(value);var ptr=_malloc(4+length+charSize);HEAPU32[ptr>>2]=length/charSize;encodeString(value,ptr+4,length+charSize);if(destructors!==null){destructors.push(_free,ptr)}return ptr}
```
</details>

### `fromWireType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
()=>undefined
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,o)=>undefined
```
</details>

### `fromWireType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
()=>undefined
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,o)=>undefined
```
</details>

### `fromWireType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
()=>undefined
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,o)=>undefined
```
</details>

### `fromWireType(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
()=>undefined
```
</details>

### `toWireType(destructors: any, o: any): any`

**Parameters:**

- **`destructors`** `any`
- **`o`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(destructors,o)=>undefined
```
</details>


---

## Classes

### `ExceptionInfo`

<details><summary>Class Code</summary>

```ts
class ExceptionInfo{constructor(excPtr){this.excPtr=excPtr;this.ptr=excPtr-24}set_type(type){HEAPU32[this.ptr+4>>2]=type}get_type(){return HEAPU32[this.ptr+4>>2]}set_destructor(destructor){HEAPU32[this.ptr+8>>2]=destructor}get_destructor(){return HEAPU32[this.ptr+8>>2]}set_caught(caught){caught=caught?1:0;HEAP8[this.ptr+12]=caught}get_caught(){return HEAP8[this.ptr+12]!=0}set_rethrown(rethrown){rethrown=rethrown?1:0;HEAP8[this.ptr+13]=rethrown}get_rethrown(){return HEAP8[this.ptr+13]!=0}init(type,destructor){this.set_adjusted_ptr(0);this.set_type(type);this.set_destructor(destructor)}set_adjusted_ptr(adjustedPtr){HEAPU32[this.ptr+16>>2]=adjustedPtr}get_adjusted_ptr(){return HEAPU32[this.ptr+16>>2]}get_exception_ptr(){var isPointer=___cxa_is_pointer_type(this.get_type());if(isPointer){return HEAPU32[this.excPtr>>2]}var adjusted=this.get_adjusted_ptr();if(adjusted!==0)return adjusted;return this.excPtr}}
```
</details>

#### Methods

##### `set_type(type: any): void`

<details><summary>Code</summary>

```ts
set_type(type){HEAPU32[this.ptr+4>>2]=type}
```
</details>

##### `get_type(): any`

<details><summary>Code</summary>

```ts
get_type(){return HEAPU32[this.ptr+4>>2]}
```
</details>

##### `set_destructor(destructor: any): void`

<details><summary>Code</summary>

```ts
set_destructor(destructor){HEAPU32[this.ptr+8>>2]=destructor}
```
</details>

##### `get_destructor(): any`

<details><summary>Code</summary>

```ts
get_destructor(){return HEAPU32[this.ptr+8>>2]}
```
</details>

##### `set_caught(caught: any): void`

<details><summary>Code</summary>

```ts
set_caught(caught){caught=caught?1:0;HEAP8[this.ptr+12]=caught}
```
</details>

##### `get_caught(): boolean`

<details><summary>Code</summary>

```ts
get_caught(){return HEAP8[this.ptr+12]!=0}
```
</details>

##### `set_rethrown(rethrown: any): void`

<details><summary>Code</summary>

```ts
set_rethrown(rethrown){rethrown=rethrown?1:0;HEAP8[this.ptr+13]=rethrown}
```
</details>

##### `get_rethrown(): boolean`

<details><summary>Code</summary>

```ts
get_rethrown(){return HEAP8[this.ptr+13]!=0}
```
</details>

##### `init(type: any, destructor: any): void`

<details><summary>Code</summary>

```ts
init(type,destructor){this.set_adjusted_ptr(0);this.set_type(type);this.set_destructor(destructor)}
```
</details>

##### `set_adjusted_ptr(adjustedPtr: any): void`

<details><summary>Code</summary>

```ts
set_adjusted_ptr(adjustedPtr){HEAPU32[this.ptr+16>>2]=adjustedPtr}
```
</details>

##### `get_adjusted_ptr(): any`

<details><summary>Code</summary>

```ts
get_adjusted_ptr(){return HEAPU32[this.ptr+16>>2]}
```
</details>

##### `get_exception_ptr(): any`

<details><summary>Code</summary>

```ts
get_exception_ptr(){var isPointer=___cxa_is_pointer_type(this.get_type());if(isPointer){return HEAPU32[this.excPtr>>2]}var adjusted=this.get_adjusted_ptr();if(adjusted!==0)return adjusted;return this.excPtr}
```
</details>

### `ExceptionInfo`

<details><summary>Class Code</summary>

```ts
class ExceptionInfo{constructor(excPtr){this.excPtr=excPtr;this.ptr=excPtr-24}set_type(type){HEAPU32[this.ptr+4>>2]=type}get_type(){return HEAPU32[this.ptr+4>>2]}set_destructor(destructor){HEAPU32[this.ptr+8>>2]=destructor}get_destructor(){return HEAPU32[this.ptr+8>>2]}set_caught(caught){caught=caught?1:0;HEAP8[this.ptr+12]=caught}get_caught(){return HEAP8[this.ptr+12]!=0}set_rethrown(rethrown){rethrown=rethrown?1:0;HEAP8[this.ptr+13]=rethrown}get_rethrown(){return HEAP8[this.ptr+13]!=0}init(type,destructor){this.set_adjusted_ptr(0);this.set_type(type);this.set_destructor(destructor)}set_adjusted_ptr(adjustedPtr){HEAPU32[this.ptr+16>>2]=adjustedPtr}get_adjusted_ptr(){return HEAPU32[this.ptr+16>>2]}get_exception_ptr(){var isPointer=___cxa_is_pointer_type(this.get_type());if(isPointer){return HEAPU32[this.excPtr>>2]}var adjusted=this.get_adjusted_ptr();if(adjusted!==0)return adjusted;return this.excPtr}}
```
</details>

#### Methods

##### `set_type(type: any): void`

<details><summary>Code</summary>

```ts
set_type(type){HEAPU32[this.ptr+4>>2]=type}
```
</details>

##### `get_type(): any`

<details><summary>Code</summary>

```ts
get_type(){return HEAPU32[this.ptr+4>>2]}
```
</details>

##### `set_destructor(destructor: any): void`

<details><summary>Code</summary>

```ts
set_destructor(destructor){HEAPU32[this.ptr+8>>2]=destructor}
```
</details>

##### `get_destructor(): any`

<details><summary>Code</summary>

```ts
get_destructor(){return HEAPU32[this.ptr+8>>2]}
```
</details>

##### `set_caught(caught: any): void`

<details><summary>Code</summary>

```ts
set_caught(caught){caught=caught?1:0;HEAP8[this.ptr+12]=caught}
```
</details>

##### `get_caught(): boolean`

<details><summary>Code</summary>

```ts
get_caught(){return HEAP8[this.ptr+12]!=0}
```
</details>

##### `set_rethrown(rethrown: any): void`

<details><summary>Code</summary>

```ts
set_rethrown(rethrown){rethrown=rethrown?1:0;HEAP8[this.ptr+13]=rethrown}
```
</details>

##### `get_rethrown(): boolean`

<details><summary>Code</summary>

```ts
get_rethrown(){return HEAP8[this.ptr+13]!=0}
```
</details>

##### `init(type: any, destructor: any): void`

<details><summary>Code</summary>

```ts
init(type,destructor){this.set_adjusted_ptr(0);this.set_type(type);this.set_destructor(destructor)}
```
</details>

##### `set_adjusted_ptr(adjustedPtr: any): void`

<details><summary>Code</summary>

```ts
set_adjusted_ptr(adjustedPtr){HEAPU32[this.ptr+16>>2]=adjustedPtr}
```
</details>

##### `get_adjusted_ptr(): any`

<details><summary>Code</summary>

```ts
get_adjusted_ptr(){return HEAPU32[this.ptr+16>>2]}
```
</details>

##### `get_exception_ptr(): any`

<details><summary>Code</summary>

```ts
get_exception_ptr(){var isPointer=___cxa_is_pointer_type(this.get_type());if(isPointer){return HEAPU32[this.excPtr>>2]}var adjusted=this.get_adjusted_ptr();if(adjusted!==0)return adjusted;return this.excPtr}
```
</details>


---