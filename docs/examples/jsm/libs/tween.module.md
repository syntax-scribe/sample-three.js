[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `tween.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 359 |
| 📊 Variables & Constants | 54 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/libs/tween.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `s` | `number` | let/var | `1.70158` | ✗ |
| `s` | `number` | let/var | `1.70158` | ✗ |
| `s` | `number` | let/var | `1.70158 * 1.525` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `tween` | `any` | let/var | `this._tweens[tweenIds[i]]` | ✗ |
| `autoStart` | `boolean` | let/var | `!preserve` | ✗ |
| `Group` | `typeof Group` | let/var | `(function () { function Group() { this._tweens = {}; this._tweensAddedDuringU...` | ✗ |
| `m` | `number` | let/var | `v.length - 1` | ✗ |
| `f` | `number` | let/var | `m * k` | ✗ |
| `fn` | `(p0: any, p1: any, t: any) => any` | let/var | `Interpolation.Utils.Linear` | ✗ |
| `b` | `number` | let/var | `0` | ✗ |
| `n` | `number` | let/var | `v.length - 1` | ✗ |
| `pw` | `(x: number, y: number) => number` | let/var | `Math.pow` | ✗ |
| `bn` | `(n: any, i: any) => number` | let/var | `Interpolation.Utils.Bernstein` | ✗ |
| `m` | `number` | let/var | `v.length - 1` | ✗ |
| `f` | `number` | let/var | `m * k` | ✗ |
| `fn` | `(p0: any, p1: any, p2: any, p3: any, ...` | let/var | `Interpolation.Utils.CatmullRom` | ✗ |
| `fc` | `(n: any) => number` | let/var | `Interpolation.Utils.Factorial` | ✗ |
| `a` | `number[]` | let/var | `[1]` | ✗ |
| `s` | `number` | let/var | `1` | ✗ |
| `v0` | `number` | let/var | `(p2 - p0) * 0.5` | ✗ |
| `v1` | `number` | let/var | `(p3 - p1) * 0.5` | ✗ |
| `t2` | `number` | let/var | `t * t` | ✗ |
| `t3` | `number` | let/var | `t * t2` | ✗ |
| `Interpolation` | `{ Linear: (v: any, k: any) => any; Be...` | let/var | `{ Linear: function (v, k) { var m = v.length - 1; var f = m * k; var i = Math...` | ✗ |
| `Sequence` | `{ (): void; nextId(): number; _nextId...` | let/var | `(function () { function Sequence() { } Sequence.nextId = function () { return...` | ✗ |
| `mainGroup` | `Group` | let/var | `new Group()` | ✗ |
| `tmp` | `{}` | let/var | `{}` | ✗ |
| `startValue` | `any` | let/var | `_object[property]` | ✗ |
| `propType` | `string` | let/var | `startValueIsArray ? 'array' : typeof startValue` | ✗ |
| `isInterpolationList` | `boolean` | let/var | `!startValueIsArray && Array.isArray(_valuesEnd[property])` | ✗ |
| `endValues` | `any` | let/var | `_valuesEnd[property]` | ✗ |
| `temp` | `any[]` | let/var | `[startValue]` | ✗ |
| `nestedObject` | `any` | let/var | `startValue` | ✗ |
| `tmp` | `{}` | let/var | `{}` | ✗ |
| `tweens` | `any[]` | let/var | `[]` | ✗ |
| `_this` | `this` | let/var | `this` | ✗ |
| `_a` | `any` | let/var | `*not shown*` | ✗ |
| `property` | `any` | let/var | `*not shown*` | ✗ |
| `endTime` | `number` | let/var | `this._startTime + this._duration` | ✗ |
| `elapsedTime` | `number` | let/var | `time - this._startTime` | ✗ |
| `durationAndDelay` | `any` | let/var | `this._duration + ((_a = this._repeatDelayTime) !== null && _a !== void 0 ? _a...` | ✗ |
| `totalTime` | `number` | let/var | `this._duration + this._repeat * durationAndDelay` | ✗ |
| `timeIntoCurrentRepeat` | `number` | let/var | `elapsedTime - timesRepeated * durationAndDelay` | ✗ |
| `start` | `any` | let/var | `_valuesStart[property] \|\| 0` | ✗ |
| `end` | `any` | let/var | `_valuesEnd[property]` | ✗ |
| `isInterpolationList` | `boolean` | let/var | `!startIsArray && endIsArray` | ✗ |
| `tmp` | `any` | let/var | `this._valuesStartRepeat[property]` | ✗ |
| `endValue` | `any` | let/var | `this._valuesEnd[property]` | ✗ |
| `Tween` | `typeof Tween` | let/var | `(function () { function Tween(_object, _group) { if (_group === void 0) { _gr...` | ✗ |
| `VERSION` | `string` | let/var | `'23.1.1'` | ✗ |
| `nextId` | `() => number` | let/var | `Sequence.nextId` | ✗ |
| `TWEEN` | `Group` | let/var | `mainGroup` | ✗ |
| `exports` | `{ Easing: Readonly<{ Linear: Readonly...` | let/var | `{ Easing: Easing, Group: Group, Interpolation: Interpolation, now: now, Seque...` | ✗ |


---

## Functions

### `None(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount;
        }
```
</details>

### `In(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `Out(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `InOut(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `None(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount;
        }
```
</details>

### `In(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `Out(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `InOut(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * (2 - amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount;
            }
            return -0.5 * (--amount * (amount - 2) - 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * (2 - amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount;
            }
            return -0.5 * (--amount * (amount - 2) - 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - --amount * amount * amount * amount;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount;
            }
            return -0.5 * ((amount -= 2) * amount * amount * amount - 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - --amount * amount * amount * amount;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount;
            }
            return -0.5 * ((amount -= 2) * amount * amount * amount - 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sin(((1.0 - amount) * Math.PI) / 2);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sin((amount * Math.PI) / 2);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 0.5 * (1 - Math.sin(Math.PI * (0.5 - amount)));
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sin(((1.0 - amount) * Math.PI) / 2);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sin((amount * Math.PI) / 2);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 0.5 * (1 - Math.sin(Math.PI * (0.5 - amount)));
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 0 ? 0 : Math.pow(1024, amount - 1);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 1 ? 1 : 1 - Math.pow(2, -10 * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            if ((amount *= 2) < 1) {
                return 0.5 * Math.pow(1024, amount - 1);
            }
            return 0.5 * (-Math.pow(2, -10 * (amount - 1)) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 0 ? 0 : Math.pow(1024, amount - 1);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 1 ? 1 : 1 - Math.pow(2, -10 * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            if ((amount *= 2) < 1) {
                return 0.5 * Math.pow(1024, amount - 1);
            }
            return 0.5 * (-Math.pow(2, -10 * (amount - 1)) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sqrt(1 - amount * amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sqrt(1 - --amount * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return -0.5 * (Math.sqrt(1 - amount * amount) - 1);
            }
            return 0.5 * (Math.sqrt(1 - (amount -= 2) * amount) + 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sqrt(1 - amount * amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sqrt(1 - --amount * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return -0.5 * (Math.sqrt(1 - amount * amount) - 1);
            }
            return 0.5 * (Math.sqrt(1 - (amount -= 2) * amount) + 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return -Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return Math.pow(2, -10 * amount) * Math.sin((amount - 0.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            amount *= 2;
            if (amount < 1) {
                return -0.5 * Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
            }
            return 0.5 * Math.pow(2, -10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return -Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return Math.pow(2, -10 * amount) * Math.sin((amount - 0.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            amount *= 2;
            if (amount < 1) {
                return -0.5 * Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
            }
            return 0.5 * Math.pow(2, -10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 1 ? 1 : amount * amount * ((s + 1) * amount - s);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 0 ? 0 : --amount * amount * ((s + 1) * amount + s) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158 * 1.525;
            if ((amount *= 2) < 1) {
                return 0.5 * (amount * amount * ((s + 1) * amount - s));
            }
            return 0.5 * ((amount -= 2) * amount * ((s + 1) * amount + s) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 1 ? 1 : amount * amount * ((s + 1) * amount - s);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 0 ? 0 : --amount * amount * ((s + 1) * amount + s) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158 * 1.525;
            if ((amount *= 2) < 1) {
                return 0.5 * (amount * amount * ((s + 1) * amount - s));
            }
            return 0.5 * ((amount -= 2) * amount * ((s + 1) * amount + s) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Easing.Bounce.Out(1 - amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 1 / 2.75) {
                return 7.5625 * amount * amount;
            }
            else if (amount < 2 / 2.75) {
                return 7.5625 * (amount -= 1.5 / 2.75) * amount + 0.75;
            }
            else if (amount < 2.5 / 2.75) {
                return 7.5625 * (amount -= 2.25 / 2.75) * amount + 0.9375;
            }
            else {
                return 7.5625 * (amount -= 2.625 / 2.75) * amount + 0.984375;
            }
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.In`
- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 0.5) {
                return Easing.Bounce.In(amount * 2) * 0.5;
            }
            return Easing.Bounce.Out(amount * 2 - 1) * 0.5 + 0.5;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Easing.Bounce.Out(1 - amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 1 / 2.75) {
                return 7.5625 * amount * amount;
            }
            else if (amount < 2 / 2.75) {
                return 7.5625 * (amount -= 1.5 / 2.75) * amount + 0.75;
            }
            else if (amount < 2.5 / 2.75) {
                return 7.5625 * (amount -= 2.25 / 2.75) * amount + 0.9375;
            }
            else {
                return 7.5625 * (amount -= 2.625 / 2.75) * amount + 0.984375;
            }
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.In`
- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 0.5) {
                return Easing.Bounce.In(amount * 2) * 0.5;
            }
            return Easing.Bounce.Out(amount * 2 - 1) * 0.5 + 0.5;
        }
```
</details>

### `generatePow(power: any): { In: (amount: any) => number; Out: (amount: any) => number; InOut: (amount: any) => number; }`

**Parameters:**

- **`power`** `any`

**Returns:** `{ In: (amount: any) => number; Out: (amount: any) => number; InOut: (amount: any) => number; }`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (power) {
        if (power === void 0) { power = 4; }
        power = power < Number.EPSILON ? Number.EPSILON : power;
        power = power > 10000 ? 10000 : power;
        return {
            In: function (amount) {
                return Math.pow(amount, power);
            },
            Out: function (amount) {
                return 1 - Math.pow((1 - amount), power);
            },
            InOut: function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            },
        };
    }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return Math.pow(amount, power);
            }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return 1 - Math.pow((1 - amount), power);
            }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return Math.pow(amount, power);
            }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return 1 - Math.pow((1 - amount), power);
            }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            }
```
</details>

### `None(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount;
        }
```
</details>

### `In(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `Out(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `InOut(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `None(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount;
        }
```
</details>

### `In(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `Out(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `InOut(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * (2 - amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount;
            }
            return -0.5 * (--amount * (amount - 2) - 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * (2 - amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount;
            }
            return -0.5 * (--amount * (amount - 2) - 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - --amount * amount * amount * amount;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount;
            }
            return -0.5 * ((amount -= 2) * amount * amount * amount - 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - --amount * amount * amount * amount;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount;
            }
            return -0.5 * ((amount -= 2) * amount * amount * amount - 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sin(((1.0 - amount) * Math.PI) / 2);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sin((amount * Math.PI) / 2);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 0.5 * (1 - Math.sin(Math.PI * (0.5 - amount)));
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sin(((1.0 - amount) * Math.PI) / 2);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sin((amount * Math.PI) / 2);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 0.5 * (1 - Math.sin(Math.PI * (0.5 - amount)));
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 0 ? 0 : Math.pow(1024, amount - 1);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 1 ? 1 : 1 - Math.pow(2, -10 * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            if ((amount *= 2) < 1) {
                return 0.5 * Math.pow(1024, amount - 1);
            }
            return 0.5 * (-Math.pow(2, -10 * (amount - 1)) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 0 ? 0 : Math.pow(1024, amount - 1);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 1 ? 1 : 1 - Math.pow(2, -10 * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            if ((amount *= 2) < 1) {
                return 0.5 * Math.pow(1024, amount - 1);
            }
            return 0.5 * (-Math.pow(2, -10 * (amount - 1)) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sqrt(1 - amount * amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sqrt(1 - --amount * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return -0.5 * (Math.sqrt(1 - amount * amount) - 1);
            }
            return 0.5 * (Math.sqrt(1 - (amount -= 2) * amount) + 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sqrt(1 - amount * amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sqrt(1 - --amount * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return -0.5 * (Math.sqrt(1 - amount * amount) - 1);
            }
            return 0.5 * (Math.sqrt(1 - (amount -= 2) * amount) + 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return -Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return Math.pow(2, -10 * amount) * Math.sin((amount - 0.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            amount *= 2;
            if (amount < 1) {
                return -0.5 * Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
            }
            return 0.5 * Math.pow(2, -10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return -Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return Math.pow(2, -10 * amount) * Math.sin((amount - 0.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            amount *= 2;
            if (amount < 1) {
                return -0.5 * Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
            }
            return 0.5 * Math.pow(2, -10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 1 ? 1 : amount * amount * ((s + 1) * amount - s);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 0 ? 0 : --amount * amount * ((s + 1) * amount + s) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158 * 1.525;
            if ((amount *= 2) < 1) {
                return 0.5 * (amount * amount * ((s + 1) * amount - s));
            }
            return 0.5 * ((amount -= 2) * amount * ((s + 1) * amount + s) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 1 ? 1 : amount * amount * ((s + 1) * amount - s);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 0 ? 0 : --amount * amount * ((s + 1) * amount + s) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158 * 1.525;
            if ((amount *= 2) < 1) {
                return 0.5 * (amount * amount * ((s + 1) * amount - s));
            }
            return 0.5 * ((amount -= 2) * amount * ((s + 1) * amount + s) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Easing.Bounce.Out(1 - amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 1 / 2.75) {
                return 7.5625 * amount * amount;
            }
            else if (amount < 2 / 2.75) {
                return 7.5625 * (amount -= 1.5 / 2.75) * amount + 0.75;
            }
            else if (amount < 2.5 / 2.75) {
                return 7.5625 * (amount -= 2.25 / 2.75) * amount + 0.9375;
            }
            else {
                return 7.5625 * (amount -= 2.625 / 2.75) * amount + 0.984375;
            }
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.In`
- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 0.5) {
                return Easing.Bounce.In(amount * 2) * 0.5;
            }
            return Easing.Bounce.Out(amount * 2 - 1) * 0.5 + 0.5;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Easing.Bounce.Out(1 - amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 1 / 2.75) {
                return 7.5625 * amount * amount;
            }
            else if (amount < 2 / 2.75) {
                return 7.5625 * (amount -= 1.5 / 2.75) * amount + 0.75;
            }
            else if (amount < 2.5 / 2.75) {
                return 7.5625 * (amount -= 2.25 / 2.75) * amount + 0.9375;
            }
            else {
                return 7.5625 * (amount -= 2.625 / 2.75) * amount + 0.984375;
            }
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.In`
- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 0.5) {
                return Easing.Bounce.In(amount * 2) * 0.5;
            }
            return Easing.Bounce.Out(amount * 2 - 1) * 0.5 + 0.5;
        }
```
</details>

### `generatePow(power: any): { In: (amount: any) => number; Out: (amount: any) => number; InOut: (amount: any) => number; }`

**Parameters:**

- **`power`** `any`

**Returns:** `{ In: (amount: any) => number; Out: (amount: any) => number; InOut: (amount: any) => number; }`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (power) {
        if (power === void 0) { power = 4; }
        power = power < Number.EPSILON ? Number.EPSILON : power;
        power = power > 10000 ? 10000 : power;
        return {
            In: function (amount) {
                return Math.pow(amount, power);
            },
            Out: function (amount) {
                return 1 - Math.pow((1 - amount), power);
            },
            InOut: function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            },
        };
    }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return Math.pow(amount, power);
            }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return 1 - Math.pow((1 - amount), power);
            }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return Math.pow(amount, power);
            }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return 1 - Math.pow((1 - amount), power);
            }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            }
```
</details>

### `None(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount;
        }
```
</details>

### `In(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `Out(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `InOut(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `None(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount;
        }
```
</details>

### `In(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `Out(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `InOut(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * (2 - amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount;
            }
            return -0.5 * (--amount * (amount - 2) - 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * (2 - amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount;
            }
            return -0.5 * (--amount * (amount - 2) - 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - --amount * amount * amount * amount;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount;
            }
            return -0.5 * ((amount -= 2) * amount * amount * amount - 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - --amount * amount * amount * amount;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount;
            }
            return -0.5 * ((amount -= 2) * amount * amount * amount - 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sin(((1.0 - amount) * Math.PI) / 2);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sin((amount * Math.PI) / 2);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 0.5 * (1 - Math.sin(Math.PI * (0.5 - amount)));
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sin(((1.0 - amount) * Math.PI) / 2);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sin((amount * Math.PI) / 2);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 0.5 * (1 - Math.sin(Math.PI * (0.5 - amount)));
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 0 ? 0 : Math.pow(1024, amount - 1);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 1 ? 1 : 1 - Math.pow(2, -10 * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            if ((amount *= 2) < 1) {
                return 0.5 * Math.pow(1024, amount - 1);
            }
            return 0.5 * (-Math.pow(2, -10 * (amount - 1)) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 0 ? 0 : Math.pow(1024, amount - 1);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 1 ? 1 : 1 - Math.pow(2, -10 * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            if ((amount *= 2) < 1) {
                return 0.5 * Math.pow(1024, amount - 1);
            }
            return 0.5 * (-Math.pow(2, -10 * (amount - 1)) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sqrt(1 - amount * amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sqrt(1 - --amount * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return -0.5 * (Math.sqrt(1 - amount * amount) - 1);
            }
            return 0.5 * (Math.sqrt(1 - (amount -= 2) * amount) + 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sqrt(1 - amount * amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sqrt(1 - --amount * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return -0.5 * (Math.sqrt(1 - amount * amount) - 1);
            }
            return 0.5 * (Math.sqrt(1 - (amount -= 2) * amount) + 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return -Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return Math.pow(2, -10 * amount) * Math.sin((amount - 0.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            amount *= 2;
            if (amount < 1) {
                return -0.5 * Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
            }
            return 0.5 * Math.pow(2, -10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return -Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return Math.pow(2, -10 * amount) * Math.sin((amount - 0.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            amount *= 2;
            if (amount < 1) {
                return -0.5 * Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
            }
            return 0.5 * Math.pow(2, -10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 1 ? 1 : amount * amount * ((s + 1) * amount - s);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 0 ? 0 : --amount * amount * ((s + 1) * amount + s) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158 * 1.525;
            if ((amount *= 2) < 1) {
                return 0.5 * (amount * amount * ((s + 1) * amount - s));
            }
            return 0.5 * ((amount -= 2) * amount * ((s + 1) * amount + s) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 1 ? 1 : amount * amount * ((s + 1) * amount - s);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 0 ? 0 : --amount * amount * ((s + 1) * amount + s) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158 * 1.525;
            if ((amount *= 2) < 1) {
                return 0.5 * (amount * amount * ((s + 1) * amount - s));
            }
            return 0.5 * ((amount -= 2) * amount * ((s + 1) * amount + s) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Easing.Bounce.Out(1 - amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 1 / 2.75) {
                return 7.5625 * amount * amount;
            }
            else if (amount < 2 / 2.75) {
                return 7.5625 * (amount -= 1.5 / 2.75) * amount + 0.75;
            }
            else if (amount < 2.5 / 2.75) {
                return 7.5625 * (amount -= 2.25 / 2.75) * amount + 0.9375;
            }
            else {
                return 7.5625 * (amount -= 2.625 / 2.75) * amount + 0.984375;
            }
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.In`
- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 0.5) {
                return Easing.Bounce.In(amount * 2) * 0.5;
            }
            return Easing.Bounce.Out(amount * 2 - 1) * 0.5 + 0.5;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Easing.Bounce.Out(1 - amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 1 / 2.75) {
                return 7.5625 * amount * amount;
            }
            else if (amount < 2 / 2.75) {
                return 7.5625 * (amount -= 1.5 / 2.75) * amount + 0.75;
            }
            else if (amount < 2.5 / 2.75) {
                return 7.5625 * (amount -= 2.25 / 2.75) * amount + 0.9375;
            }
            else {
                return 7.5625 * (amount -= 2.625 / 2.75) * amount + 0.984375;
            }
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.In`
- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 0.5) {
                return Easing.Bounce.In(amount * 2) * 0.5;
            }
            return Easing.Bounce.Out(amount * 2 - 1) * 0.5 + 0.5;
        }
```
</details>

### `generatePow(power: any): { In: (amount: any) => number; Out: (amount: any) => number; InOut: (amount: any) => number; }`

**Parameters:**

- **`power`** `any`

**Returns:** `{ In: (amount: any) => number; Out: (amount: any) => number; InOut: (amount: any) => number; }`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (power) {
        if (power === void 0) { power = 4; }
        power = power < Number.EPSILON ? Number.EPSILON : power;
        power = power > 10000 ? 10000 : power;
        return {
            In: function (amount) {
                return Math.pow(amount, power);
            },
            Out: function (amount) {
                return 1 - Math.pow((1 - amount), power);
            },
            InOut: function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            },
        };
    }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return Math.pow(amount, power);
            }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return 1 - Math.pow((1 - amount), power);
            }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return Math.pow(amount, power);
            }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return 1 - Math.pow((1 - amount), power);
            }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            }
```
</details>

### `None(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount;
        }
```
</details>

### `In(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `Out(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `InOut(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `None(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount;
        }
```
</details>

### `In(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `Out(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `InOut(amount: any): any`

**Parameters:**

- **`amount`** `any`

**Returns:** `any`

**Calls:**

- `this.None`

<details><summary>Code</summary>

```typescript
function (amount) {
            return this.None(amount);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * (2 - amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount;
            }
            return -0.5 * (--amount * (amount - 2) - 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * (2 - amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount;
            }
            return -0.5 * (--amount * (amount - 2) - 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - --amount * amount * amount * amount;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount;
            }
            return -0.5 * ((amount -= 2) * amount * amount * amount - 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - --amount * amount * amount * amount;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount;
            }
            return -0.5 * ((amount -= 2) * amount * amount * amount - 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount * amount * amount * amount * amount;
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            return --amount * amount * amount * amount * amount + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return 0.5 * amount * amount * amount * amount * amount;
            }
            return 0.5 * ((amount -= 2) * amount * amount * amount * amount + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sin(((1.0 - amount) * Math.PI) / 2);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sin((amount * Math.PI) / 2);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 0.5 * (1 - Math.sin(Math.PI * (0.5 - amount)));
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sin(((1.0 - amount) * Math.PI) / 2);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sin((amount * Math.PI) / 2);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 0.5 * (1 - Math.sin(Math.PI * (0.5 - amount)));
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 0 ? 0 : Math.pow(1024, amount - 1);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 1 ? 1 : 1 - Math.pow(2, -10 * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            if ((amount *= 2) < 1) {
                return 0.5 * Math.pow(1024, amount - 1);
            }
            return 0.5 * (-Math.pow(2, -10 * (amount - 1)) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 0 ? 0 : Math.pow(1024, amount - 1);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            return amount === 1 ? 1 : 1 - Math.pow(2, -10 * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            if ((amount *= 2) < 1) {
                return 0.5 * Math.pow(1024, amount - 1);
            }
            return 0.5 * (-Math.pow(2, -10 * (amount - 1)) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sqrt(1 - amount * amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sqrt(1 - --amount * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return -0.5 * (Math.sqrt(1 - amount * amount) - 1);
            }
            return 0.5 * (Math.sqrt(1 - (amount -= 2) * amount) + 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Math.sqrt(1 - amount * amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            return Math.sqrt(1 - --amount * amount);
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function (amount) {
            if ((amount *= 2) < 1) {
                return -0.5 * (Math.sqrt(1 - amount * amount) - 1);
            }
            return 0.5 * (Math.sqrt(1 - (amount -= 2) * amount) + 1);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return -Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return Math.pow(2, -10 * amount) * Math.sin((amount - 0.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            amount *= 2;
            if (amount < 1) {
                return -0.5 * Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
            }
            return 0.5 * Math.pow(2, -10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return -Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            return Math.pow(2, -10 * amount) * Math.sin((amount - 0.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount === 0) {
                return 0;
            }
            if (amount === 1) {
                return 1;
            }
            amount *= 2;
            if (amount < 1) {
                return -0.5 * Math.pow(2, 10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI);
            }
            return 0.5 * Math.pow(2, -10 * (amount - 1)) * Math.sin((amount - 1.1) * 5 * Math.PI) + 1;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 1 ? 1 : amount * amount * ((s + 1) * amount - s);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 0 ? 0 : --amount * amount * ((s + 1) * amount + s) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158 * 1.525;
            if ((amount *= 2) < 1) {
                return 0.5 * (amount * amount * ((s + 1) * amount - s));
            }
            return 0.5 * ((amount -= 2) * amount * ((s + 1) * amount + s) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 1 ? 1 : amount * amount * ((s + 1) * amount - s);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158;
            return amount === 0 ? 0 : --amount * amount * ((s + 1) * amount + s) + 1;
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            var s = 1.70158 * 1.525;
            if ((amount *= 2) < 1) {
                return 0.5 * (amount * amount * ((s + 1) * amount - s));
            }
            return 0.5 * ((amount -= 2) * amount * ((s + 1) * amount + s) + 2);
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Easing.Bounce.Out(1 - amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 1 / 2.75) {
                return 7.5625 * amount * amount;
            }
            else if (amount < 2 / 2.75) {
                return 7.5625 * (amount -= 1.5 / 2.75) * amount + 0.75;
            }
            else if (amount < 2.5 / 2.75) {
                return 7.5625 * (amount -= 2.25 / 2.75) * amount + 0.9375;
            }
            else {
                return 7.5625 * (amount -= 2.625 / 2.75) * amount + 0.984375;
            }
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.In`
- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 0.5) {
                return Easing.Bounce.In(amount * 2) * 0.5;
            }
            return Easing.Bounce.Out(amount * 2 - 1) * 0.5 + 0.5;
        }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            return 1 - Easing.Bounce.Out(1 - amount);
        }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 1 / 2.75) {
                return 7.5625 * amount * amount;
            }
            else if (amount < 2 / 2.75) {
                return 7.5625 * (amount -= 1.5 / 2.75) * amount + 0.75;
            }
            else if (amount < 2.5 / 2.75) {
                return 7.5625 * (amount -= 2.25 / 2.75) * amount + 0.9375;
            }
            else {
                return 7.5625 * (amount -= 2.625 / 2.75) * amount + 0.984375;
            }
        }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Easing.Bounce.In`
- `Easing.Bounce.Out`

<details><summary>Code</summary>

```typescript
function (amount) {
            if (amount < 0.5) {
                return Easing.Bounce.In(amount * 2) * 0.5;
            }
            return Easing.Bounce.Out(amount * 2 - 1) * 0.5 + 0.5;
        }
```
</details>

### `generatePow(power: any): { In: (amount: any) => number; Out: (amount: any) => number; InOut: (amount: any) => number; }`

**Parameters:**

- **`power`** `any`

**Returns:** `{ In: (amount: any) => number; Out: (amount: any) => number; InOut: (amount: any) => number; }`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (power) {
        if (power === void 0) { power = 4; }
        power = power < Number.EPSILON ? Number.EPSILON : power;
        power = power > 10000 ? 10000 : power;
        return {
            In: function (amount) {
                return Math.pow(amount, power);
            },
            Out: function (amount) {
                return 1 - Math.pow((1 - amount), power);
            },
            InOut: function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            },
        };
    }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return Math.pow(amount, power);
            }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return 1 - Math.pow((1 - amount), power);
            }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            }
```
</details>

### `In(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return Math.pow(amount, power);
            }
```
</details>

### `Out(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                return 1 - Math.pow((1 - amount), power);
            }
```
</details>

### `InOut(amount: any): number`

**Parameters:**

- **`amount`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function (amount) {
                if (amount < 0.5) {
                    return Math.pow((amount * 2), power) / 2;
                }
                return (1 - Math.pow((2 - amount * 2), power)) / 2 + 0.5;
            }
```
</details>

### `now(): number`

**Returns:** `number`

**Calls:**

- `performance.now`

<details><summary>Code</summary>

```typescript
function () { return performance.now(); }
```
</details>

### `Group(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Group() {
        this._tweens = {};
        this._tweensAddedDuringUpdate = {};
    }
```
</details>

### `Linear(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.Linear;
        if (k < 0) {
            return fn(v[0], v[1], f);
        }
        if (k > 1) {
            return fn(v[m], v[m - 1], m - f);
        }
        return fn(v[i], v[i + 1 > m ? m : i + 1], f - i);
    }
```
</details>

### `Bezier(v: any, k: any): number`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `number`

**Calls:**

- `pw`
- `bn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var b = 0;
        var n = v.length - 1;
        var pw = Math.pow;
        var bn = Interpolation.Utils.Bernstein;
        for (var i = 0; i <= n; i++) {
            b += pw(1 - k, n - i) * pw(k, i) * v[i] * bn(n, i);
        }
        return b;
    }
```
</details>

### `CatmullRom(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.CatmullRom;
        if (v[0] === v[m]) {
            if (k < 0) {
                i = Math.floor((f = m * (1 + k)));
            }
            return fn(v[(i - 1 + m) % m], v[i], v[(i + 1) % m], v[(i + 2) % m], f - i);
        }
        else {
            if (k < 0) {
                return v[0] - (fn(v[0], v[0], v[1], v[1], -f) - v[0]);
            }
            if (k > 1) {
                return v[m] - (fn(v[m], v[m], v[m - 1], v[m - 1], f - m) - v[m]);
            }
            return fn(v[i ? i - 1 : 0], v[i], v[m < i + 1 ? m : i + 1], v[m < i + 2 ? m : i + 2], f - i);
        }
    }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.Linear;
        if (k < 0) {
            return fn(v[0], v[1], f);
        }
        if (k > 1) {
            return fn(v[m], v[m - 1], m - f);
        }
        return fn(v[i], v[i + 1 > m ? m : i + 1], f - i);
    }
```
</details>

### `Bezier(v: any, k: any): number`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `number`

**Calls:**

- `pw`
- `bn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var b = 0;
        var n = v.length - 1;
        var pw = Math.pow;
        var bn = Interpolation.Utils.Bernstein;
        for (var i = 0; i <= n; i++) {
            b += pw(1 - k, n - i) * pw(k, i) * v[i] * bn(n, i);
        }
        return b;
    }
```
</details>

### `CatmullRom(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.CatmullRom;
        if (v[0] === v[m]) {
            if (k < 0) {
                i = Math.floor((f = m * (1 + k)));
            }
            return fn(v[(i - 1 + m) % m], v[i], v[(i + 1) % m], v[(i + 2) % m], f - i);
        }
        else {
            if (k < 0) {
                return v[0] - (fn(v[0], v[0], v[1], v[1], -f) - v[0]);
            }
            if (k > 1) {
                return v[m] - (fn(v[m], v[m], v[m - 1], v[m - 1], f - m) - v[m]);
            }
            return fn(v[i ? i - 1 : 0], v[i], v[m < i + 1 ? m : i + 1], v[m < i + 2 ? m : i + 2], f - i);
        }
    }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.Linear;
        if (k < 0) {
            return fn(v[0], v[1], f);
        }
        if (k > 1) {
            return fn(v[m], v[m - 1], m - f);
        }
        return fn(v[i], v[i + 1 > m ? m : i + 1], f - i);
    }
```
</details>

### `Bezier(v: any, k: any): number`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `number`

**Calls:**

- `pw`
- `bn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var b = 0;
        var n = v.length - 1;
        var pw = Math.pow;
        var bn = Interpolation.Utils.Bernstein;
        for (var i = 0; i <= n; i++) {
            b += pw(1 - k, n - i) * pw(k, i) * v[i] * bn(n, i);
        }
        return b;
    }
```
</details>

### `CatmullRom(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.CatmullRom;
        if (v[0] === v[m]) {
            if (k < 0) {
                i = Math.floor((f = m * (1 + k)));
            }
            return fn(v[(i - 1 + m) % m], v[i], v[(i + 1) % m], v[(i + 2) % m], f - i);
        }
        else {
            if (k < 0) {
                return v[0] - (fn(v[0], v[0], v[1], v[1], -f) - v[0]);
            }
            if (k > 1) {
                return v[m] - (fn(v[m], v[m], v[m - 1], v[m - 1], f - m) - v[m]);
            }
            return fn(v[i ? i - 1 : 0], v[i], v[m < i + 1 ? m : i + 1], v[m < i + 2 ? m : i + 2], f - i);
        }
    }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.Linear;
        if (k < 0) {
            return fn(v[0], v[1], f);
        }
        if (k > 1) {
            return fn(v[m], v[m - 1], m - f);
        }
        return fn(v[i], v[i + 1 > m ? m : i + 1], f - i);
    }
```
</details>

### `Bezier(v: any, k: any): number`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `number`

**Calls:**

- `pw`
- `bn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var b = 0;
        var n = v.length - 1;
        var pw = Math.pow;
        var bn = Interpolation.Utils.Bernstein;
        for (var i = 0; i <= n; i++) {
            b += pw(1 - k, n - i) * pw(k, i) * v[i] * bn(n, i);
        }
        return b;
    }
```
</details>

### `CatmullRom(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.CatmullRom;
        if (v[0] === v[m]) {
            if (k < 0) {
                i = Math.floor((f = m * (1 + k)));
            }
            return fn(v[(i - 1 + m) % m], v[i], v[(i + 1) % m], v[(i + 2) % m], f - i);
        }
        else {
            if (k < 0) {
                return v[0] - (fn(v[0], v[0], v[1], v[1], -f) - v[0]);
            }
            if (k > 1) {
                return v[m] - (fn(v[m], v[m], v[m - 1], v[m - 1], f - m) - v[m]);
            }
            return fn(v[i ? i - 1 : 0], v[i], v[m < i + 1 ? m : i + 1], v[m < i + 2 ? m : i + 2], f - i);
        }
    }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.Linear;
        if (k < 0) {
            return fn(v[0], v[1], f);
        }
        if (k > 1) {
            return fn(v[m], v[m - 1], m - f);
        }
        return fn(v[i], v[i + 1 > m ? m : i + 1], f - i);
    }
```
</details>

### `Bezier(v: any, k: any): number`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `number`

**Calls:**

- `pw`
- `bn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var b = 0;
        var n = v.length - 1;
        var pw = Math.pow;
        var bn = Interpolation.Utils.Bernstein;
        for (var i = 0; i <= n; i++) {
            b += pw(1 - k, n - i) * pw(k, i) * v[i] * bn(n, i);
        }
        return b;
    }
```
</details>

### `CatmullRom(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.CatmullRom;
        if (v[0] === v[m]) {
            if (k < 0) {
                i = Math.floor((f = m * (1 + k)));
            }
            return fn(v[(i - 1 + m) % m], v[i], v[(i + 1) % m], v[(i + 2) % m], f - i);
        }
        else {
            if (k < 0) {
                return v[0] - (fn(v[0], v[0], v[1], v[1], -f) - v[0]);
            }
            if (k > 1) {
                return v[m] - (fn(v[m], v[m], v[m - 1], v[m - 1], f - m) - v[m]);
            }
            return fn(v[i ? i - 1 : 0], v[i], v[m < i + 1 ? m : i + 1], v[m < i + 2 ? m : i + 2], f - i);
        }
    }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.Linear;
        if (k < 0) {
            return fn(v[0], v[1], f);
        }
        if (k > 1) {
            return fn(v[m], v[m - 1], m - f);
        }
        return fn(v[i], v[i + 1 > m ? m : i + 1], f - i);
    }
```
</details>

### `Bezier(v: any, k: any): number`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `number`

**Calls:**

- `pw`
- `bn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var b = 0;
        var n = v.length - 1;
        var pw = Math.pow;
        var bn = Interpolation.Utils.Bernstein;
        for (var i = 0; i <= n; i++) {
            b += pw(1 - k, n - i) * pw(k, i) * v[i] * bn(n, i);
        }
        return b;
    }
```
</details>

### `CatmullRom(v: any, k: any): any`

**Parameters:**

- **`v`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `Math.floor`
- `fn`

<details><summary>Code</summary>

```typescript
function (v, k) {
        var m = v.length - 1;
        var f = m * k;
        var i = Math.floor(f);
        var fn = Interpolation.Utils.CatmullRom;
        if (v[0] === v[m]) {
            if (k < 0) {
                i = Math.floor((f = m * (1 + k)));
            }
            return fn(v[(i - 1 + m) % m], v[i], v[(i + 1) % m], v[(i + 2) % m], f - i);
        }
        else {
            if (k < 0) {
                return v[0] - (fn(v[0], v[0], v[1], v[1], -f) - v[0]);
            }
            if (k > 1) {
                return v[m] - (fn(v[m], v[m], v[m - 1], v[m - 1], f - m) - v[m]);
            }
            return fn(v[i ? i - 1 : 0], v[i], v[m < i + 1 ? m : i + 1], v[m < i + 2 ? m : i + 2], f - i);
        }
    }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Linear(p0: any, p1: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, t) {
            return (p1 - p0) * t + p0;
        }
```
</details>

### `Bernstein(n: any, i: any): number`

**Parameters:**

- **`n`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `fc`

<details><summary>Code</summary>

```typescript
function (n, i) {
            var fc = Interpolation.Utils.Factorial;
            return fc(n) / fc(i) / fc(n - i);
        }
```
</details>

### `CatmullRom(p0: any, p1: any, p2: any, p3: any, t: any): any`

**Parameters:**

- **`p0`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`p3`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function (p0, p1, p2, p3, t) {
            var v0 = (p2 - p0) * 0.5;
            var v1 = (p3 - p1) * 0.5;
            var t2 = t * t;
            var t3 = t * t2;
            return (2 * p1 - 2 * p2 + v0 + v1) * t3 + (-3 * p1 + 3 * p2 - 2 * v0 - v1) * t2 + v0 * t + p1;
        }
```
</details>

### `Sequence(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function Sequence() {
    }
```
</details>

### `Tween(_object: any, _group: any): void`

**Parameters:**

- **`_object`** `any`
- **`_group`** `any`

**Returns:** `void`

**Calls:**

- `Sequence.nextId`

**Internal Comments:**
```
// eslint-disable-next-line (x4)
```

<details><summary>Code</summary>

```typescript
function Tween(_object, _group) {
        if (_group === void 0) { _group = mainGroup; }
        this._object = _object;
        this._group = _group;
        this._isPaused = false;
        this._pauseStart = 0;
        this._valuesStart = {};
        this._valuesEnd = {};
        this._valuesStartRepeat = {};
        this._duration = 1000;
        this._isDynamic = false;
        this._initialRepeat = 0;
        this._repeat = 0;
        this._yoyo = false;
        this._isPlaying = false;
        this._reversed = false;
        this._delayTime = 0;
        this._startTime = 0;
        this._easingFunction = Easing.Linear.None;
        this._interpolationFunction = Interpolation.Linear;
        // eslint-disable-next-line
        this._chainedTweens = [];
        this._onStartCallbackFired = false;
        this._onEveryStartCallbackFired = false;
        this._id = Sequence.nextId();
        this._isChainStopped = false;
        this._propertiesAreSetUp = false;
        this._goToEnd = false;
    }
```
</details>

### `calculateElapsedPortion(): number`

**Returns:** `number`

**Calls:**

- `Math.trunc`
- `Math.min`

**Internal Comments:**
```
// TODO use %? (x2)
// const timeIntoCurrentRepeat = elapsedTime % durationAndDelay (x2)
```

<details><summary>Code</summary>

```typescript
function () {
            if (_this._duration === 0)
                return 1;
            if (elapsedTime > totalTime) {
                return 1;
            }
            var timesRepeated = Math.trunc(elapsedTime / durationAndDelay);
            var timeIntoCurrentRepeat = elapsedTime - timesRepeated * durationAndDelay;
            // TODO use %?
            // const timeIntoCurrentRepeat = elapsedTime % durationAndDelay
            var portion = Math.min(timeIntoCurrentRepeat / _this._duration, 1);
            if (portion === 0 && elapsedTime === _this._duration) {
                return 1;
            }
            return portion;
        }
```
</details>


---