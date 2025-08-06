[⬅️ Back to Table of Contents](../../index.md)

# 📄 `CustomNodeEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/CustomNodeEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LabelElement` | `flow` |
| `Color` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |
| `Vector4` | `three` |
| `uniform` | `three/tsl` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `createInputLib` | `../NodeEditorUtils.js` |
| `setInputAestheticsFromType` | `../DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `typeToValue` | `{ color: any; vec2: any; vec3: any; v...` | let/var | `{ 'color': Color, 'vec2': Vector2, 'vec3': Vector3, 'vec4': Vector4 }` | ✗ |
| `nodeType` | `any` | let/var | `property.nodeType` | ✗ |
| `label` | `any` | let/var | `property.label` | ✗ |
| `shaderNode` | `any` | let/var | `Nodes[ settings.shaderNode ]` | ✗ |
| `node` | `any` | let/var | `null` | ✗ |
| `elements` | `any[]` | let/var | `[]` | ✗ |


---

## Functions

### `createElementFromProperty(node: any, property: any): any`

**Parameters:**

- **`node`** `any`
- **`property`** `any`

**Returns:** `any`

**Calls:**

- `uniform (from three/tsl)`
- `label.endsWith`
- `label.slice`
- `setInputAestheticsFromType (from ../DataTypeLib.js)`
- `complex_call_1000`
- `element.onConnect`
- `elmt.setEnabledInputs`
- `elmt.getLinkedObject`

<details><summary>Code</summary>

```typescript
( node, property ) => {

	const nodeType = property.nodeType;
	const defaultValue = uniform( typeToValue[ nodeType ] ? new typeToValue[ nodeType ]() : 0 );

	let label = property.label;

	if ( label === undefined ) {

		label = property.name;

		if ( label.endsWith( 'Node' ) === true ) {

			label = label.slice( 0, label.length - 4 );

		}

	}

	node[ property.name ] = defaultValue;

	const element = setInputAestheticsFromType( new LabelElement( label ), nodeType );

	if ( createInputLib[ nodeType ] !== undefined ) {

		createInputLib[ nodeType ]( defaultValue, element );

	}

	element.onConnect( ( elmt ) => {

		elmt.setEnabledInputs( ! elmt.getLinkedObject() );

		node[ property.name ] = elmt.getLinkedObject() || defaultValue;

	} );

	return element;

}
```
</details>


---

## Classes

### `CustomNodeEditor`

<details><summary>Class Code</summary>

```ts
export class CustomNodeEditor extends BaseNodeEditor {

	constructor( settings ) {

		const shaderNode = Nodes[ settings.shaderNode ];

		let node = null;

		const elements = [];

		if ( settings.properties !== undefined ) {

			node = shaderNode();

			for ( const property of settings.properties ) {

				elements.push( createElementFromProperty( node, property ) );

			}

		} else {

			node = shaderNode;

		}

		node.nodeType = node.nodeType || settings.nodeType;

		super( settings.name, node, 300 );

		this.title.setIcon( 'ti ti-' + settings.icon );

		for ( const element of elements ) {

			this.add( element );

		}

	}

}
```
</details>


---