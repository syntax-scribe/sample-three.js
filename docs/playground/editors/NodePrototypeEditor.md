[⬅️ Back to Table of Contents](../../index.md)

# 📄 `NodePrototypeEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/NodePrototypeEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `JavaScriptEditor` | `./JavaScriptEditor.js` |
| `ScriptableEditor` | `./ScriptableEditor.js` |
| `scriptable` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `defaultCode` | `"// Addition Node Example\n// Enjoy! ...` | let/var | ``// Addition Node Example // Enjoy! :) // layout must be the first variable. ...` | ✗ |
| `nodePrototype` | `this` | let/var | `this` | ✗ |
| `scriptableNode` | `any` | let/var | `this.scriptableNode` | ✗ |
| `editorElement` | `CodeEditorElement` | let/var | `this.editorElement` | ✗ |
| `nodeClass` | `typeof nodeClass` | let/var | `class extends ScriptableEditor { constructor() { super( scriptableNode.codeNo...` | ✗ |


---

## Functions

### `NodePrototypeEditor.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.source = this.source;

	}
```
</details>

### `NodePrototypeEditor.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.source = data.source;

	}
```
</details>

### `NodePrototypeEditor.deserializeLib(data: any, lib: any): void`

**Parameters:**

- **`data`** `any`
- **`lib`** `any`

**Returns:** `void`

**Calls:**

- `super.deserializeLib`
- `this.createPrototype`

<details><summary>Code</summary>

```typescript
deserializeLib( data, lib ) {

		super.deserializeLib( data, lib );

		this.source = data.source;

		const nodePrototype = this.createPrototype();
		lib[ nodePrototype.name ] = nodePrototype.nodeClass;

	}
```
</details>

### `NodePrototypeEditor.setEditor(editor: any): void`

**Parameters:**

- **`editor`** `any`

**Returns:** `void`

**Calls:**

- `this.editor.removeClass`
- `super.setEditor`
- `proto.dispose`
- `this.updatePrototypes`

<details><summary>Code</summary>

```typescript
setEditor( editor ) {

		if ( editor === null && this.editor ) {

			this.editor.removeClass( this._prototype );

		}

		super.setEditor( editor );

		if ( editor === null ) {

			for ( const proto of [ ...this.instances ] ) {

				proto.dispose();

			}

			this.instances = [];

		}

		this.updatePrototypes();

	}
```
</details>

### `NodePrototypeEditor.createPrototype(): { readonly name: any; readonly icon: any; nodeClass: typeof nodeClass; reference: this; editor: any; }`

**Returns:** `{ readonly name: any; readonly icon: any; nodeClass: typeof nodeClass; reference: this; editor: any; }`

**Calls:**

- `complex_call_2142`
- `this.onCode.bind`
- `this.update`
- `super.setEditor`
- `nodePrototype.instances.indexOf`
- `nodePrototype.instances.push`
- `editorElement.addEventListener`
- `nodePrototype.instances.splice`
- `editorElement.removeEventListener`
- `scriptableNode.getLayout`

<details><summary>Code</summary>

```typescript
createPrototype() {

		if ( this._prototype !== null ) return this._prototype;

		const nodePrototype = this;
		const scriptableNode = this.scriptableNode;
		const editorElement = this.editorElement;

		const nodeClass = class extends ScriptableEditor {

			constructor() {

				super( scriptableNode.codeNode, false );

				this.serializePriority = - 1;

				this.onCode = this.onCode.bind( this );

			}

			onCode() {

				this.update();

			}

			setEditor( editor ) {

				super.setEditor( editor );

				const index = nodePrototype.instances.indexOf( this );

				if ( editor ) {

					if ( index === - 1 ) nodePrototype.instances.push( this );

					editorElement.addEventListener( 'change', this.onCode );

				} else {

					if ( index !== - 1 ) nodePrototype.instances.splice( index, 1 );

					editorElement.removeEventListener( 'change', this.onCode );

				}

			}

			get className() {

				return scriptableNode.getLayout().name;

			}

		};

		this._prototype = {
			get name() {

				return scriptableNode.getLayout().name;

			},
			get icon() {

				return scriptableNode.getLayout().icon;

			},
			nodeClass,
			reference: this,
			editor: this.editor
		};

		return this._prototype;

	}
```
</details>

### `NodePrototypeEditor.updatePrototypes(): void`

**Returns:** `void`

**Calls:**

- `this._prototype.editor.removeClass`
- `this.scriptableNode.getLayout`
- `this.editor.addClass`
- `this.createPrototype`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
updatePrototypes() {

		if ( this._prototype !== null && this._prototype.editor !== null ) {

			this._prototype.editor.removeClass( this._prototype );

		}

		//

		const layout = this.scriptableNode.getLayout();

		if ( layout && layout.name ) {

			if ( this.editor ) {

				this.editor.addClass( this.createPrototype() );

			}

		}

	}
```
</details>


---

## Classes

### `NodePrototypeEditor`

<details><summary>Class Code</summary>

```ts
export class NodePrototypeEditor extends JavaScriptEditor {

	constructor( source = defaultCode ) {

		super( source );

		this.setName( 'Node Prototype' );

		this.nodeClass = new WeakMap();
		this.scriptableNode = scriptable( this.codeNode );

		this.instances = [];

		this.editorElement.addEventListener( 'change', () => {

			this.updatePrototypes();

		} );

		this._prototype = null;

		this.updatePrototypes();

	}

	serialize( data ) {

		super.serialize( data );

		data.source = this.source;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.source = data.source;

	}

	deserializeLib( data, lib ) {

		super.deserializeLib( data, lib );

		this.source = data.source;

		const nodePrototype = this.createPrototype();
		lib[ nodePrototype.name ] = nodePrototype.nodeClass;

	}

	setEditor( editor ) {

		if ( editor === null && this.editor ) {

			this.editor.removeClass( this._prototype );

		}

		super.setEditor( editor );

		if ( editor === null ) {

			for ( const proto of [ ...this.instances ] ) {

				proto.dispose();

			}

			this.instances = [];

		}

		this.updatePrototypes();

	}

	createPrototype() {

		if ( this._prototype !== null ) return this._prototype;

		const nodePrototype = this;
		const scriptableNode = this.scriptableNode;
		const editorElement = this.editorElement;

		const nodeClass = class extends ScriptableEditor {

			constructor() {

				super( scriptableNode.codeNode, false );

				this.serializePriority = - 1;

				this.onCode = this.onCode.bind( this );

			}

			onCode() {

				this.update();

			}

			setEditor( editor ) {

				super.setEditor( editor );

				const index = nodePrototype.instances.indexOf( this );

				if ( editor ) {

					if ( index === - 1 ) nodePrototype.instances.push( this );

					editorElement.addEventListener( 'change', this.onCode );

				} else {

					if ( index !== - 1 ) nodePrototype.instances.splice( index, 1 );

					editorElement.removeEventListener( 'change', this.onCode );

				}

			}

			get className() {

				return scriptableNode.getLayout().name;

			}

		};

		this._prototype = {
			get name() {

				return scriptableNode.getLayout().name;

			},
			get icon() {

				return scriptableNode.getLayout().icon;

			},
			nodeClass,
			reference: this,
			editor: this.editor
		};

		return this._prototype;

	}

	updatePrototypes() {

		if ( this._prototype !== null && this._prototype.editor !== null ) {

			this._prototype.editor.removeClass( this._prototype );

		}

		//

		const layout = this.scriptableNode.getLayout();

		if ( layout && layout.name ) {

			if ( this.editor ) {

				this.editor.addClass( this.createPrototype() );

			}

		}

	}

}
```
</details>

#### Methods

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.source = this.source;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.source = data.source;

	}
```
</details>

##### `deserializeLib(data: any, lib: any): void`

<details><summary>Code</summary>

```ts
deserializeLib( data, lib ) {

		super.deserializeLib( data, lib );

		this.source = data.source;

		const nodePrototype = this.createPrototype();
		lib[ nodePrototype.name ] = nodePrototype.nodeClass;

	}
```
</details>

##### `setEditor(editor: any): void`

<details><summary>Code</summary>

```ts
setEditor( editor ) {

		if ( editor === null && this.editor ) {

			this.editor.removeClass( this._prototype );

		}

		super.setEditor( editor );

		if ( editor === null ) {

			for ( const proto of [ ...this.instances ] ) {

				proto.dispose();

			}

			this.instances = [];

		}

		this.updatePrototypes();

	}
```
</details>

##### `createPrototype(): { readonly name: any; readonly icon: any; nodeClass: typeof nodeClass; reference: this; editor: any; }`

<details><summary>Code</summary>

```ts
createPrototype() {

		if ( this._prototype !== null ) return this._prototype;

		const nodePrototype = this;
		const scriptableNode = this.scriptableNode;
		const editorElement = this.editorElement;

		const nodeClass = class extends ScriptableEditor {

			constructor() {

				super( scriptableNode.codeNode, false );

				this.serializePriority = - 1;

				this.onCode = this.onCode.bind( this );

			}

			onCode() {

				this.update();

			}

			setEditor( editor ) {

				super.setEditor( editor );

				const index = nodePrototype.instances.indexOf( this );

				if ( editor ) {

					if ( index === - 1 ) nodePrototype.instances.push( this );

					editorElement.addEventListener( 'change', this.onCode );

				} else {

					if ( index !== - 1 ) nodePrototype.instances.splice( index, 1 );

					editorElement.removeEventListener( 'change', this.onCode );

				}

			}

			get className() {

				return scriptableNode.getLayout().name;

			}

		};

		this._prototype = {
			get name() {

				return scriptableNode.getLayout().name;

			},
			get icon() {

				return scriptableNode.getLayout().icon;

			},
			nodeClass,
			reference: this,
			editor: this.editor
		};

		return this._prototype;

	}
```
</details>

##### `updatePrototypes(): void`

<details><summary>Code</summary>

```ts
updatePrototypes() {

		if ( this._prototype !== null && this._prototype.editor !== null ) {

			this._prototype.editor.removeClass( this._prototype );

		}

		//

		const layout = this.scriptableNode.getLayout();

		if ( layout && layout.name ) {

			if ( this.editor ) {

				this.editor.addClass( this.createPrototype() );

			}

		}

	}
```
</details>


---