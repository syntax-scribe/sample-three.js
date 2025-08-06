[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Oscillators.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/utils/Oscillators.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `time` | `./Timer.js` |


---

## Functions

### `oscSine(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `t.add( 0.75 ).mul( Math.PI * 2 ).sin().mul( 0.5 ).add`

<details><summary>Code</summary>

```typescript
( t = time ) => t.add( 0.75 ).mul( Math.PI * 2 ).sin().mul( 0.5 ).add( 0.5 )
```
</details>

### `oscSquare(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `t.fract().round`

<details><summary>Code</summary>

```typescript
( t = time ) => t.fract().round()
```
</details>

### `oscTriangle(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `t.add( 0.5 ).fract().mul( 2 ).sub( 1 ).abs`

<details><summary>Code</summary>

```typescript
( t = time ) => t.add( 0.5 ).fract().mul( 2 ).sub( 1 ).abs()
```
</details>

### `oscSawtooth(t: any): any`

**Parameters:**

- **`t`** `any`

**Returns:** `any`

**Calls:**

- `t.fract`

<details><summary>Code</summary>

```typescript
( t = time ) => t.fract()
```
</details>


---