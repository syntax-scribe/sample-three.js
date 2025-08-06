[⬅️ Back to Table of Contents](../index.md)

# 📄 `NodeEditorLib.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 📦 Imports | 21 |
| 📊 Variables & Constants | 9 |
| ⚡ Async/Await Patterns | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`playground/NodeEditorLib.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodePrototypeEditor` | `./editors/NodePrototypeEditor.js` |
| `ScriptableEditor` | `./editors/ScriptableEditor.js` |
| `BasicMaterialEditor` | `./editors/BasicMaterialEditor.js` |
| `StandardMaterialEditor` | `./editors/StandardMaterialEditor.js` |
| `PointsMaterialEditor` | `./editors/PointsMaterialEditor.js` |
| `FloatEditor` | `./editors/FloatEditor.js` |
| `Vector2Editor` | `./editors/Vector2Editor.js` |
| `Vector3Editor` | `./editors/Vector3Editor.js` |
| `Vector4Editor` | `./editors/Vector4Editor.js` |
| `SliderEditor` | `./editors/SliderEditor.js` |
| `ColorEditor` | `./editors/ColorEditor.js` |
| `TextureEditor` | `./editors/TextureEditor.js` |
| `UVEditor` | `./editors/UVEditor.js` |
| `PreviewEditor` | `./editors/PreviewEditor.js` |
| `TimerEditor` | `./editors/TimerEditor.js` |
| `SplitEditor` | `./editors/SplitEditor.js` |
| `SwizzleEditor` | `./editors/SwizzleEditor.js` |
| `JoinEditor` | `./editors/JoinEditor.js` |
| `StringEditor` | `./editors/StringEditor.js` |
| `FileEditor` | `./editors/FileEditor.js` |
| `CustomNodeEditor` | `./editors/CustomNodeEditor.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `ClassLib` | `{ BasicMaterialEditor: typeof BasicMa...` | let/var | `{ BasicMaterialEditor, StandardMaterialEditor, PointsMaterialEditor, FloatEdi...` | ✓ |
| `nodeList` | `any` | let/var | `null` | ✗ |
| `nodeListLoading` | `boolean` | let/var | `false` | ✗ |
| `response` | `Response` | let/var | `await fetch( './Nodes.json' )` | ✗ |
| `nodeList` | `any` | let/var | `await getNodeList()` | ✗ |
| `editorClass` | `any` | let/var | `nodeData.editorClass \|\| nodeData.name.replace( / /g, '' )` | ✗ |
| `nodeClass` | `any` | let/var | `nodeData.nodeClass \|\| ClassLib[ editorClass ]` | ✗ |
| `moduleEditor` | `any` | let/var | `await import( nodeData.editorURL )` | ✗ |
| `moduleName` | `any` | let/var | `nodeData.editorClass \|\| Object.keys( moduleEditor )[ 0 ]` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `getNodeList` | fetch( './Nodes.json' ), response.json(), new Promise( res => {

				const verifyNodeList = () => {

					if ( nodeList !== null ) {

						res();

					} else {

						window.requestAnimationFrame( verifyNodeList );

					}

				};

				verifyNodeList();

			} ) | new Promise(...) |
| async-function | `init` | getNodeList() | *none* |
| async-function | `getNodeEditorClass` | import( nodeData.editorURL ) | *none* |


---

## Functions

### `getNodeList(): Promise<any>`

**Returns:** `Promise<any>`

**Calls:**

- `fetch`
- `response.json`
- `res`
- `window.requestAnimationFrame`
- `verifyNodeList`

<details><summary>Code</summary>

```typescript
async () => {

	if ( nodeList === null ) {

		if ( nodeListLoading === false ) {

			nodeListLoading = true;

			const response = await fetch( './Nodes.json' );
			nodeList = await response.json();

		} else {

			await new Promise( res => {

				const verifyNodeList = () => {

					if ( nodeList !== null ) {

						res();

					} else {

						window.requestAnimationFrame( verifyNodeList );

					}

				};

				verifyNodeList();

			} );

		}

	}

	return nodeList;

}
```
</details>

### `verifyNodeList(): void`

**Returns:** `void`

**Calls:**

- `res`
- `window.requestAnimationFrame`

<details><summary>Code</summary>

```typescript
() => {

					if ( nodeList !== null ) {

						res();

					} else {

						window.requestAnimationFrame( verifyNodeList );

					}

				}
```
</details>

### `init(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `getNodeList`
- `getNodeEditorClass`
- `Array.isArray`
- `traverseNodeEditors`

<details><summary>Code</summary>

```typescript
async () => {

	const nodeList = await getNodeList();

	const traverseNodeEditors = ( list ) => {

		for ( const node of list ) {

			getNodeEditorClass( node );

			if ( Array.isArray( node.children ) ) {

				traverseNodeEditors( node.children );

			}

		}

	};

	traverseNodeEditors( nodeList.nodes );

}
```
</details>

### `traverseNodeEditors(list: any): void`

**Parameters:**

- **`list`** `any`

**Returns:** `void`

**Calls:**

- `getNodeEditorClass`
- `Array.isArray`
- `traverseNodeEditors`

<details><summary>Code</summary>

```typescript
( list ) => {

		for ( const node of list ) {

			getNodeEditorClass( node );

			if ( Array.isArray( node.children ) ) {

				traverseNodeEditors( node.children );

			}

		}

	}
```
</details>

### `getNodeEditorClass(nodeData: any): Promise<any>`

**Parameters:**

- **`nodeData`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `nodeData.name.replace`
- `complex_call_2963`
- `Object.keys`
- `complex_call_3275`
- `createNodeEditorClass`

**Internal Comments:**
```
// (x3)
```

<details><summary>Code</summary>

```typescript
async ( nodeData ) => {

	const editorClass = nodeData.editorClass || nodeData.name.replace( / /g, '' );

	//

	let nodeClass = nodeData.nodeClass || ClassLib[ editorClass ];

	if ( nodeClass !== undefined ) {

		if ( nodeData.editorClass !== undefined ) {

			nodeClass.prototype.icon = nodeData.icon;

		}

		return nodeClass;

	}

	//

	if ( nodeData.editorURL ) {

		const moduleEditor = await import( nodeData.editorURL );
		const moduleName = nodeData.editorClass || Object.keys( moduleEditor )[ 0 ];

		nodeClass = moduleEditor[ moduleName ];

	} else if ( nodeData.shaderNode ) {

		const createNodeEditorClass = ( nodeData ) => {

			return class extends CustomNodeEditor {

				constructor() {

					super( nodeData );

				}

				get className() {

					return editorClass;

				}

			};

		};

		nodeClass = createNodeEditorClass( nodeData );

	}

	if ( nodeClass !== null ) {

		ClassLib[ editorClass ] = nodeClass;

	}

	return nodeClass;

}
```
</details>

### `createNodeEditorClass(nodeData: any): typeof (Anonymous class)`

**Parameters:**

- **`nodeData`** `any`

**Returns:** `typeof (Anonymous class)`

**Calls:**

- `complex_call_3275`

<details><summary>Code</summary>

```typescript
( nodeData ) => {

			return class extends CustomNodeEditor {

				constructor() {

					super( nodeData );

				}

				get className() {

					return editorClass;

				}

			};

		}
```
</details>


---