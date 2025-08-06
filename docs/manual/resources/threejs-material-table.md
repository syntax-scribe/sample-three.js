[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-material-table.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/threejs-material-table.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `materials` | `{ name: string; shortName: string; pr...` | let/var | `[ { name: 'MeshBasicMaterial', shortName: 'Basic', properties: [ 'alphaMap', ...` | ✗ |
| `allProperties` | `Set<any>` | let/var | `new Set()` | ✗ |
| `hasProperty` | `boolean` | let/var | `material.properties.indexOf( property ) >= 0` | ✗ |


---

## Functions

### `addElem(type: any, parent: any, content: any): any`

**Parameters:**

- **`type`** `any`
- **`parent`** `any`
- **`content`** `any`

**Returns:** `any`

**Calls:**

- `document.createElement`
- `parent.appendChild`

<details><summary>Code</summary>

```typescript
function addElem( type, parent, content ) {

	const elem = document.createElement( type );
	if ( content ) {

		elem.textContent = content;

	}

	if ( parent ) {

		parent.appendChild( elem );

	}

	return elem;

}
```
</details>


---