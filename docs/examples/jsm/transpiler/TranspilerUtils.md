[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TranspilerUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |

## 📚 Table of Contents

- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/transpiler/TranspilerUtils.js`**

## Functions

### `isExpression(st: any): boolean`

**Parameters:**

- **`st`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
export function isExpression( st ) {

	return st.isFunctionDeclaration !== true && st.isFor !== true && st.isWhile !== true && st.isConditional !== true && st.isSwitch !== true;

}
```
</details>

### `isPrimitive(value: any): boolean`

**Parameters:**

- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `/^(true|false|-?(\d|\.\d))/.test`

<details><summary>Code</summary>

```typescript
export function isPrimitive( value ) {

	return /^(true|false|-?(\d|\.\d))/.test( value );

}
```
</details>

### `isType(str: any): boolean`

**Parameters:**

- **`str`** `any`

**Returns:** `boolean`

**Calls:**

- `/void|bool|float|u?int|mat[234]|mat[234]x[234]|(u|i|b)?vec[234]/.test`

<details><summary>Code</summary>

```typescript
export function isType( str ) {

	return /void|bool|float|u?int|mat[234]|mat[234]x[234]|(u|i|b)?vec[234]/.test( str );

}
```
</details>

### `toFloatType(type: any): any`

**Parameters:**

- **`type`** `any`

**Returns:** `any`

**Calls:**

- `/^(i?int)$/.test`
- `/^(i|u)?vec([234])$/.exec`

<details><summary>Code</summary>

```typescript
export function toFloatType( type ) {

	if ( /^(i?int)$/.test( type ) ) return 'float';

	const vecMatch = /^(i|u)?vec([234])$/.exec( type );

	if ( vecMatch ) return 'vec' + vecMatch[ 2 ];

	return type;

}
```
</details>


---