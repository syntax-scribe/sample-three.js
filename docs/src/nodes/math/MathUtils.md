[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MathUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/math/MathUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `sub` | `./OperatorNode.js` |
| `mul` | `./OperatorNode.js` |
| `div` | `./OperatorNode.js` |
| `add` | `./OperatorNode.js` |
| `PI` | `./MathNode.js` |
| `pow` | `./MathNode.js` |
| `sin` | `./MathNode.js` |


---

## Functions

### `parabola(x: any, k: any): any`

**Parameters:**

- **`x`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `pow (from ./MathNode.js)`

<details><summary>Code</summary>

```typescript
( x, k ) => pow( mul( 4.0, x.mul( sub( 1.0, x ) ) ), k )
```
</details>

### `gain(x: any, k: any): any`

**Parameters:**

- **`x`** `any`
- **`k`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( x, k ) => x.lessThan( 0.5 ) ? parabola( x.mul( 2.0 ), k ).div( 2.0 ) : sub( 1.0, parabola( mul( sub( 1.0, x ), 2.0 ), k ).div( 2.0 ) )
```
</details>

### `pcurve(x: any, a: any, b: any): any`

**Parameters:**

- **`x`** `any`
- **`a`** `any`
- **`b`** `any`

**Returns:** `any`

**Calls:**

- `pow (from ./MathNode.js)`

<details><summary>Code</summary>

```typescript
( x, a, b ) => pow( div( pow( x, a ), add( pow( x, a ), pow( sub( 1.0, x ), b ) ) ), 1.0 / a )
```
</details>

### `sinc(x: any, k: any): any`

**Parameters:**

- **`x`** `any`
- **`k`** `any`

**Returns:** `any`

**Calls:**

- `sin( PI.mul( k.mul( x ).sub( 1.0 ) ) ).div`

<details><summary>Code</summary>

```typescript
( x, k ) => sin( PI.mul( k.mul( x ).sub( 1.0 ) ) ).div( PI.mul( k.mul( x ).sub( 1.0 ) ) )
```
</details>


---