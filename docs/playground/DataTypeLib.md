[⬅️ Back to Table of Contents](../index.md)

# 📄 `DataTypeLib.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`playground/DataTypeLib.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `typeToLengthLib` | `{ string: number; float: number; bool...` | let/var | `{ // gpu string: 1, float: 1, bool: 1, vec2: 2, vec3: 3, vec4: 4, color: 3, m...` | ✓ |
| `defaultLength` | `1` | let/var | `1` | ✓ |
| `typeToColorLib` | `{ string: string; float: string; bool...` | let/var | `{ // gpu string: '#ff0000', float: '#eeeeee', bool: '#0060ff', mat2: '#d0dc8b...` | ✓ |


---

## Functions

### `getLengthFromType(type: any): any`

**Parameters:**

- **`type`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
export function getLengthFromType( type ) {

	return typeToLengthLib[ type ] || defaultLength;

}
```
</details>

### `getLengthFromNode(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `getTypeFromNode`
- `getLengthFromType`

<details><summary>Code</summary>

```typescript
export function getLengthFromNode( value ) {

	const type = getTypeFromNode( value );

	return getLengthFromType( type );

}
```
</details>

### `getColorFromType(type: any): any`

**Parameters:**

- **`type`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
export function getColorFromType( type ) {

	return typeToColorLib[ type ] || null;

}
```
</details>

### `getColorFromNode(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `getTypeFromNode`
- `getColorFromType`

<details><summary>Code</summary>

```typescript
export function getColorFromNode( value ) {

	const type = getTypeFromNode( value );

	return getColorFromType( type );

}
```
</details>

### `getTypeFromNode(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `getTypeFromValue`

<details><summary>Code</summary>

```typescript
function getTypeFromNode( value ) {

	if ( value ) {

		if ( value.isMaterial ) return 'Material';

		return value.nodeType === 'ArrayBuffer' ? 'URL' : ( value.nodeType || getTypeFromValue( value.value ) );

	}

}
```
</details>

### `getTypeFromValue(value: any): string`

**Parameters:**

- **`value`** `any`

**Returns:** `string`

**Calls:**

- `Object.keys( typeToLengthLib ).reverse`

<details><summary>Code</summary>

```typescript
function getTypeFromValue( value ) {

	if ( value && value.isScriptableValueNode ) value = value.value;
	if ( ! value ) return;

	if ( value.isNode && value.nodeType === 'string' ) return 'string';
	if ( value.isNode && value.nodeType === 'ArrayBuffer' ) return 'URL';

	for ( const type of Object.keys( typeToLengthLib ).reverse() ) {

		if ( value[ 'is' + type ] === true ) return type;

	}

}
```
</details>

### `setInputAestheticsFromType(element: any, type: any): any`

**Parameters:**

- **`element`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `element.setInput`
- `getLengthFromType`
- `getColorFromType`
- `element.setInputColor`

<details><summary>Code</summary>

```typescript
export function setInputAestheticsFromType( element, type ) {

	element.setInput( getLengthFromType( type ) );

	const color = getColorFromType( type );

	if ( color ) {

		element.setInputColor( color );

	}

	return element;

}
```
</details>

### `setOutputAestheticsFromNode(element: any, node: any): any`

**Parameters:**

- **`element`** `any`
- **`node`** `any`

**Returns:** `any`

**Calls:**

- `element.setOutput`
- `setOutputAestheticsFromType`
- `getTypeFromNode`

<details><summary>Code</summary>

```typescript
export function setOutputAestheticsFromNode( element, node ) {

	if ( ! node ) {

		element.setOutput( 0 );

		return element;

	}

	return setOutputAestheticsFromType( element, getTypeFromNode( node ) );

}
```
</details>

### `setOutputAestheticsFromType(element: any, type: any): any`

**Parameters:**

- **`element`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `element.setOutput`
- `getLengthFromType`
- `getColorFromType`
- `element.setOutputColor`

<details><summary>Code</summary>

```typescript
export function setOutputAestheticsFromType( element, type ) {

	if ( ! type ) {

		element.setOutput( 1 );

		return element;

	}

	if ( type == 'void' ) {

		element.setOutput( 0 );

		return element;

	}

	element.setOutput( getLengthFromType( type ) );

	const color = getColorFromType( type );

	if ( color ) {

		element.setOutputColor( color );

	}

	return element;

}
```
</details>


---