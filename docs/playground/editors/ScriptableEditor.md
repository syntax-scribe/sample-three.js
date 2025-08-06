[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ScriptableEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 17 |
| 🧱 Classes | 1 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/ScriptableEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `CodeEditorElement` | `../elements/CodeEditorElement.js` |
| `disposeScene` | `../NodeEditorUtils.js` |
| `resetScene` | `../NodeEditorUtils.js` |
| `createElementFromJSON` | `../NodeEditorUtils.js` |
| `isGPUNode` | `../NodeEditorUtils.js` |
| `onValidType` | `../NodeEditorUtils.js` |
| `ScriptableNodeResources` | `three/tsl` |
| `scriptable` | `three/tsl` |
| `js` | `three/tsl` |
| `scriptableValue` | `three/tsl` |
| `getColorFromType` | `../DataTypeLib.js` |
| `setInputAestheticsFromType` | `../DataTypeLib.js` |
| `setOutputAestheticsFromType` | `../DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `defaultTitle` | `"Scriptable"` | let/var | `'Scriptable'` | ✗ |
| `defaultWidth` | `500` | let/var | `500` | ✗ |
| `codeNode` | `any` | let/var | `null` | ✗ |
| `scriptableNode` | `any` | let/var | `null` | ✗ |
| `layout` | `any` | let/var | `null` | ✗ |
| `scriptableValueOutput` | `any` | let/var | `null` | ✗ |
| `initCacheKey` | `any` | let/var | `typeof object.init === 'function' ? object.init.toString() : ''` | ✗ |
| `initId` | `number` | let/var | `++ this.initId` | ✗ |
| `editorOutput` | `any` | let/var | `scriptableValueOutput ? scriptableValueOutput.value : null` | ✗ |
| `layout` | `any` | let/var | `this.layout` | ✗ |
| `outputType` | `any` | let/var | `layout.outputType` | ✗ |
| `value` | `any` | let/var | `element.value` | ✗ |
| `paramValue` | `any` | let/var | `value && value.isScriptableValueNode ? value : scriptableValue( value )` | ✗ |
| `needsUpdateWidth` | `boolean` | let/var | `this.hasExternalEditor \|\| this.editorElement === null` | ✗ |


---

## Functions

### `ScriptableEditor.getColor(): string`

**Returns:** `string`

**Calls:**

- `getColorFromType (from ../DataTypeLib.js)`

<details><summary>Code</summary>

```typescript
getColor() {

		const color = getColorFromType( this.layout ? this.layout.outputType : null );

		return color ? color + 'BB' : null;

	}
```
</details>

### `ScriptableEditor.hasJSON(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
hasJSON() {

		return true;

	}
```
</details>

### `ScriptableEditor.exportJSON(): any`

**Returns:** `any`

**Calls:**

- `this.scriptableNode.toJSON`

<details><summary>Code</summary>

```typescript
exportJSON() {

		return this.scriptableNode.toJSON();

	}
```
</details>

### `ScriptableEditor.setSource(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `this.update`

<details><summary>Code</summary>

```typescript
setSource( source ) {

		this.editorCodeNode.code = source;

		this.update();

		return this;

	}
```
</details>

### `ScriptableEditor.update(force: boolean): void`

**Parameters:**

- **`force`** `boolean`

**Returns:** `void`

**Calls:**

- `this.scriptableNode.getObject`
- `this.scriptableNode.getLayout`
- `this.updateLayout`
- `this.scriptableNode.getDefaultOutput`
- `object.init.toString`
- `this.scriptableNode.callAsync( 'init' ).then`
- `this.update`
- `this.editor.tips.message`
- `console.error`
- `this.editor.tips.error`
- `isGPUNode (from ../NodeEditorUtils.js)`
- `this.updateOutputInEditor`
- `this.updateOutputConnection`
- `this.invalidate`

<details><summary>Code</summary>

```typescript
update( force = false ) {

		if ( this._updating === true ) return;

		this._updating = true;

		this.scriptableNode.codeNode = this.codeNode;
		this.scriptableNode.needsUpdate = true;

		let layout = null;
		let scriptableValueOutput = null;

		try {

			const object = this.scriptableNode.getObject();

			layout = this.scriptableNode.getLayout();

			this.updateLayout( layout, force );

			scriptableValueOutput = this.scriptableNode.getDefaultOutput();

			const initCacheKey = typeof object.init === 'function' ? object.init.toString() : '';

			if ( initCacheKey !== this.initCacheKey ) {

				this.initCacheKey = initCacheKey;

				const initId = ++ this.initId;

				this.scriptableNode.callAsync( 'init' ).then( () => {

					if ( initId === this.initId ) {

						this.update();

						if ( this.editor ) this.editor.tips.message( 'ScriptEditor: Initialized.' );

					}

				} );

			}

		} catch ( e ) {

			console.error( e );

			if ( this.editor ) this.editor.tips.error( e.message );

		}

		const editorOutput = scriptableValueOutput ? scriptableValueOutput.value : null;

		this.value = isGPUNode( editorOutput ) ? this.scriptableNode : scriptableValueOutput;
		this.layout = layout;
		this.editorOutput = editorOutput;

		this.updateOutputInEditor();
		this.updateOutputConnection();

		this.invalidate();

		this._updating = false;

	}
```
</details>

### `ScriptableEditor.updateOutputConnection(): void`

**Returns:** `void`

**Calls:**

- `setOutputAestheticsFromType (from ../DataTypeLib.js)`
- `this.title.setOutput`

<details><summary>Code</summary>

```typescript
updateOutputConnection() {

		const layout = this.layout;

		if ( layout ) {

			const outputType = layout.outputType;

			setOutputAestheticsFromType( this.title, outputType );

		} else {

			this.title.setOutput( 0 );

		}

	}
```
</details>

### `ScriptableEditor.updateOutputInEditor(): void`

**Returns:** `void`

**Calls:**

- `ScriptableNodeResources.get`
- `editorOutputAdded.removeFromParent`
- `disposeScene (from ../NodeEditorUtils.js)`
- `resetScene (from ../NodeEditorUtils.js)`
- `composer.removePass`
- `scene.add`
- `composer.addPass`

<details><summary>Code</summary>

```typescript
updateOutputInEditor() {

		const { editor, editorOutput, editorOutputAdded } = this;

		if ( editor && editorOutput === editorOutputAdded ) return;

		const scene = ScriptableNodeResources.get( 'scene' );
		const composer = ScriptableNodeResources.get( 'composer' );

		if ( editor ) {

			if ( editorOutputAdded && editorOutputAdded.isObject3D === true ) {

				editorOutputAdded.removeFromParent();

				disposeScene( editorOutputAdded );

				resetScene( scene );

			} else if ( composer && editorOutputAdded && editorOutputAdded.isPass === true ) {

				composer.removePass( editorOutputAdded );

			}

			if ( editorOutput && editorOutput.isObject3D === true ) {

				scene.add( editorOutput );

			} else if ( composer && editorOutput && editorOutput.isPass === true ) {

				composer.addPass( editorOutput );

			}

			this.editorOutputAdded = editorOutput;

		} else {

			if ( editorOutputAdded && editorOutputAdded.isObject3D === true ) {

				editorOutputAdded.removeFromParent();

				disposeScene( editorOutputAdded );

				resetScene( scene );

			} else if ( composer && editorOutputAdded && editorOutputAdded.isPass === true ) {

				composer.removePass( editorOutputAdded );

			}

			this.editorOutputAdded = null;

		}

	}
```
</details>

### `ScriptableEditor.setEditor(editor: any): void`

**Parameters:**

- **`editor`** `any`

**Returns:** `void`

**Calls:**

- `super.setEditor`
- `this.updateOutputInEditor`

<details><summary>Code</summary>

```typescript
setEditor( editor ) {

		super.setEditor( editor );

		this.updateOutputInEditor();

	}
```
</details>

### `ScriptableEditor.clearParameters(): void`

**Returns:** `void`

**Calls:**

- `this.scriptableNode.clearParameters`
- `this.elements.concat`
- `this.remove`

<details><summary>Code</summary>

```typescript
clearParameters() {

		this.layoutJSON = '';

		this.scriptableNode.clearParameters();

		for ( const element of this.elements.concat() ) {

			if ( element !== this.editorElement && element !== this.title ) {

				this.remove( element );

			}

		}

	}
```
</details>

### `ScriptableEditor.addElementFromJSON(json: any): any`

**Parameters:**

- **`json`** `any`

**Returns:** `any`

**Calls:**

- `createElementFromJSON (from ../NodeEditorUtils.js)`
- `this.add`
- `this.scriptableNode.setParameter`
- `element.setObjectCallback`
- `this.scriptableNode.getOutput`
- `scriptableValue (from three/tsl)`
- `this.update`
- `element.addEventListener`
- `element.onConnect`

**Internal Comments:**
```
// (x2)
//element.onConnect( () => this.getScriptable().call( 'onDeepChange' ), true );
```

<details><summary>Code</summary>

```typescript
addElementFromJSON( json ) {

		const { id, element, inputNode, outputType } = createElementFromJSON( json );

		this.add( element );

		this.scriptableNode.setParameter( id, inputNode );

		if ( outputType ) {

			element.setObjectCallback( () => {

				return this.scriptableNode.getOutput( id );

			} );

		}

		//

		const onUpdate = () => {

			const value = element.value;
			const paramValue = value && value.isScriptableValueNode ? value : scriptableValue( value );

			this.scriptableNode.setParameter( id, paramValue );

			this.update();

		};

		element.addEventListener( 'changeInput', onUpdate );
		element.onConnect( onUpdate, true );

		//element.onConnect( () => this.getScriptable().call( 'onDeepChange' ), true );

		return element;

	}
```
</details>

### `ScriptableEditor.updateLayout(layout: any, force: boolean): void`

**Parameters:**

- **`layout`** `any`
- **`force`** `boolean`

**Returns:** `void`

**Calls:**

- `JSON.stringify`
- `this.setWidth`
- `this.clearParameters`
- `this.setName`
- `this.setIcon`
- `this.addElementFromJSON`
- `this.remove`
- `this.add`
- `this.updateOutputConnection`

<details><summary>Code</summary>

```typescript
updateLayout( layout = null, force = false ) {

		const needsUpdateWidth = this.hasExternalEditor || this.editorElement === null;

		if ( this.waitToLayoutJSON !== null ) {

			if ( this.waitToLayoutJSON === JSON.stringify( layout || '{}' ) ) {

				this.waitToLayoutJSON = null;

				if ( needsUpdateWidth ) this.setWidth( layout.width );

			} else {

				return;

			}

		}

		if ( layout ) {

			const layoutCacheKey = JSON.stringify( layout );

			if ( this.layoutJSON !== layoutCacheKey || force === true ) {

				this.clearParameters();

				if ( layout.name ) {

					this.setName( layout.name );

				}


				if ( layout.icon ) {

					this.setIcon( layout.icon );

				}

				if ( needsUpdateWidth ) {

					if ( layout.width !== undefined ) {

                		this.setWidth( layout.width );

					} else {

						this.setWidth( defaultWidth );

					}

				}

				if ( layout.elements ) {

					for ( const element of layout.elements ) {

						this.addElementFromJSON( element );

					}

					if ( this.editorElement ) {

						this.remove( this.editorElement );
						this.add( this.editorElement );

					}

				}

				this.layoutJSON = layoutCacheKey;

			}

		} else {

			this.setName( defaultTitle );
			this.setIcon( null );
			this.setWidth( defaultWidth );

			this.clearParameters();

		}

		this.updateOutputConnection();

	}
```
</details>

### `ScriptableEditor._initExternalConnection(): void`

**Returns:** `void`

**Calls:**

- `setInputAestheticsFromType( this.title, 'CodeNode' ).onValid( onValidType( 'CodeNode' ) ).onConnect`
- `this._toExternal`
- `this._toInternal`
- `this.update`

<details><summary>Code</summary>

```typescript
_initExternalConnection() {

		setInputAestheticsFromType( this.title, 'CodeNode' ).onValid( onValidType( 'CodeNode' ) ).onConnect( () => {

			this.hasExternalEditor ? this._toExternal() : this._toInternal();

			this.update();

		}, true );

	}
```
</details>

### `ScriptableEditor._toInternal(): void`

**Returns:** `void`

**Calls:**

- `this.editorElement.addEventListener`
- `this.setSource`
- `this.editorElement.focus`
- `this.add`
- `this.setResizable`
- `this.editorElement.setVisible`
- `this.update`

<details><summary>Code</summary>

```typescript
_toInternal() {

		if ( this.hasInternalEditor === true ) return;

		if ( this.editorElement === null ) {

			this.editorElement = new CodeEditorElement( this.editorCodeNode.code );
			this.editorElement.addEventListener( 'change', () => {

				this.setSource( this.editorElement.source );

				this.editorElement.focus();

			} );

			this.add( this.editorElement );

		}

		this.setResizable( true );

		this.editorElement.setVisible( true );

		this.hasInternalEditor = true;

		this.update( /*true*/ );

	}
```
</details>

### `ScriptableEditor._toExternal(): void`

**Returns:** `void`

**Calls:**

- `this.editorElement.setVisible`
- `this.setResizable`
- `this.update`

<details><summary>Code</summary>

```typescript
_toExternal() {

		if ( this.hasInternalEditor === false ) return;

		this.editorElement.setVisible( false );

		this.setResizable( false );

		this.hasInternalEditor = false;

		this.update( /*true*/ );

	}
```
</details>

### `ScriptableEditor.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.layoutJSON = this.layoutJSON;

	}
```
</details>

### `ScriptableEditor.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.updateLayout`
- `JSON.parse`
- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		this.updateLayout( JSON.parse( data.layoutJSON || '{}' ), true );

		this.waitToLayoutJSON = data.layoutJSON;

		super.deserialize( data );

	}
```
</details>

### `onUpdate(): void`

**Returns:** `void`

**Calls:**

- `scriptableValue (from three/tsl)`
- `this.scriptableNode.setParameter`
- `this.update`

<details><summary>Code</summary>

```typescript
() => {

			const value = element.value;
			const paramValue = value && value.isScriptableValueNode ? value : scriptableValue( value );

			this.scriptableNode.setParameter( id, paramValue );

			this.update();

		}
```
</details>


---

## Classes

### `ScriptableEditor`

<details><summary>Class Code</summary>

```ts
export class ScriptableEditor extends BaseNodeEditor {

	constructor( source = null, enableEditor = true ) {

		let codeNode = null;
		let scriptableNode = null;

		if ( source && source.isCodeNode ) {

			codeNode = source;

		} else {

			codeNode = js( source || '' );

		}

		scriptableNode = scriptable( codeNode );

		super( defaultTitle, scriptableNode, defaultWidth );

		this.scriptableNode = scriptableNode;
		this.editorCodeNode = codeNode;
		this.editorOutput = null;
		this.editorOutputAdded = null;

		this.layout = null;
		this.editorElement = null;

		this.layoutJSON = '';
		this.initCacheKey = '';
		this.initId = 0;
		this.waitToLayoutJSON = null;

		this.hasInternalEditor = false;

		this._updating = false;

		this.onValidElement = () => {};

		if ( enableEditor ) {

			this.title.setSerializable( true );

			this._initExternalConnection();

			this._toInternal();

		}

		const defaultOutput = this.scriptableNode.getDefaultOutput();
		defaultOutput.events.addEventListener( 'refresh', () => {

			this.update();

		} );

		this.update();

	}

	getColor() {

		const color = getColorFromType( this.layout ? this.layout.outputType : null );

		return color ? color + 'BB' : null;

	}

	hasJSON() {

		return true;

	}

	exportJSON() {

		return this.scriptableNode.toJSON();

	}

	setSource( source ) {

		this.editorCodeNode.code = source;

		this.update();

		return this;

	}

	update( force = false ) {

		if ( this._updating === true ) return;

		this._updating = true;

		this.scriptableNode.codeNode = this.codeNode;
		this.scriptableNode.needsUpdate = true;

		let layout = null;
		let scriptableValueOutput = null;

		try {

			const object = this.scriptableNode.getObject();

			layout = this.scriptableNode.getLayout();

			this.updateLayout( layout, force );

			scriptableValueOutput = this.scriptableNode.getDefaultOutput();

			const initCacheKey = typeof object.init === 'function' ? object.init.toString() : '';

			if ( initCacheKey !== this.initCacheKey ) {

				this.initCacheKey = initCacheKey;

				const initId = ++ this.initId;

				this.scriptableNode.callAsync( 'init' ).then( () => {

					if ( initId === this.initId ) {

						this.update();

						if ( this.editor ) this.editor.tips.message( 'ScriptEditor: Initialized.' );

					}

				} );

			}

		} catch ( e ) {

			console.error( e );

			if ( this.editor ) this.editor.tips.error( e.message );

		}

		const editorOutput = scriptableValueOutput ? scriptableValueOutput.value : null;

		this.value = isGPUNode( editorOutput ) ? this.scriptableNode : scriptableValueOutput;
		this.layout = layout;
		this.editorOutput = editorOutput;

		this.updateOutputInEditor();
		this.updateOutputConnection();

		this.invalidate();

		this._updating = false;

	}

	updateOutputConnection() {

		const layout = this.layout;

		if ( layout ) {

			const outputType = layout.outputType;

			setOutputAestheticsFromType( this.title, outputType );

		} else {

			this.title.setOutput( 0 );

		}

	}

	updateOutputInEditor() {

		const { editor, editorOutput, editorOutputAdded } = this;

		if ( editor && editorOutput === editorOutputAdded ) return;

		const scene = ScriptableNodeResources.get( 'scene' );
		const composer = ScriptableNodeResources.get( 'composer' );

		if ( editor ) {

			if ( editorOutputAdded && editorOutputAdded.isObject3D === true ) {

				editorOutputAdded.removeFromParent();

				disposeScene( editorOutputAdded );

				resetScene( scene );

			} else if ( composer && editorOutputAdded && editorOutputAdded.isPass === true ) {

				composer.removePass( editorOutputAdded );

			}

			if ( editorOutput && editorOutput.isObject3D === true ) {

				scene.add( editorOutput );

			} else if ( composer && editorOutput && editorOutput.isPass === true ) {

				composer.addPass( editorOutput );

			}

			this.editorOutputAdded = editorOutput;

		} else {

			if ( editorOutputAdded && editorOutputAdded.isObject3D === true ) {

				editorOutputAdded.removeFromParent();

				disposeScene( editorOutputAdded );

				resetScene( scene );

			} else if ( composer && editorOutputAdded && editorOutputAdded.isPass === true ) {

				composer.removePass( editorOutputAdded );

			}

			this.editorOutputAdded = null;

		}

	}

	setEditor( editor ) {

		super.setEditor( editor );

		this.updateOutputInEditor();

	}

	clearParameters() {

		this.layoutJSON = '';

		this.scriptableNode.clearParameters();

		for ( const element of this.elements.concat() ) {

			if ( element !== this.editorElement && element !== this.title ) {

				this.remove( element );

			}

		}

	}

	addElementFromJSON( json ) {

		const { id, element, inputNode, outputType } = createElementFromJSON( json );

		this.add( element );

		this.scriptableNode.setParameter( id, inputNode );

		if ( outputType ) {

			element.setObjectCallback( () => {

				return this.scriptableNode.getOutput( id );

			} );

		}

		//

		const onUpdate = () => {

			const value = element.value;
			const paramValue = value && value.isScriptableValueNode ? value : scriptableValue( value );

			this.scriptableNode.setParameter( id, paramValue );

			this.update();

		};

		element.addEventListener( 'changeInput', onUpdate );
		element.onConnect( onUpdate, true );

		//element.onConnect( () => this.getScriptable().call( 'onDeepChange' ), true );

		return element;

	}

	updateLayout( layout = null, force = false ) {

		const needsUpdateWidth = this.hasExternalEditor || this.editorElement === null;

		if ( this.waitToLayoutJSON !== null ) {

			if ( this.waitToLayoutJSON === JSON.stringify( layout || '{}' ) ) {

				this.waitToLayoutJSON = null;

				if ( needsUpdateWidth ) this.setWidth( layout.width );

			} else {

				return;

			}

		}

		if ( layout ) {

			const layoutCacheKey = JSON.stringify( layout );

			if ( this.layoutJSON !== layoutCacheKey || force === true ) {

				this.clearParameters();

				if ( layout.name ) {

					this.setName( layout.name );

				}


				if ( layout.icon ) {

					this.setIcon( layout.icon );

				}

				if ( needsUpdateWidth ) {

					if ( layout.width !== undefined ) {

                		this.setWidth( layout.width );

					} else {

						this.setWidth( defaultWidth );

					}

				}

				if ( layout.elements ) {

					for ( const element of layout.elements ) {

						this.addElementFromJSON( element );

					}

					if ( this.editorElement ) {

						this.remove( this.editorElement );
						this.add( this.editorElement );

					}

				}

				this.layoutJSON = layoutCacheKey;

			}

		} else {

			this.setName( defaultTitle );
			this.setIcon( null );
			this.setWidth( defaultWidth );

			this.clearParameters();

		}

		this.updateOutputConnection();

	}

	get hasExternalEditor() {

		return this.title.getLinkedObject() !== null;

	}

	get codeNode() {

		return this.hasExternalEditor ? this.title.getLinkedObject() : this.editorCodeNode;

	}

	_initExternalConnection() {

		setInputAestheticsFromType( this.title, 'CodeNode' ).onValid( onValidType( 'CodeNode' ) ).onConnect( () => {

			this.hasExternalEditor ? this._toExternal() : this._toInternal();

			this.update();

		}, true );

	}

	_toInternal() {

		if ( this.hasInternalEditor === true ) return;

		if ( this.editorElement === null ) {

			this.editorElement = new CodeEditorElement( this.editorCodeNode.code );
			this.editorElement.addEventListener( 'change', () => {

				this.setSource( this.editorElement.source );

				this.editorElement.focus();

			} );

			this.add( this.editorElement );

		}

		this.setResizable( true );

		this.editorElement.setVisible( true );

		this.hasInternalEditor = true;

		this.update( /*true*/ );

	}

	_toExternal() {

		if ( this.hasInternalEditor === false ) return;

		this.editorElement.setVisible( false );

		this.setResizable( false );

		this.hasInternalEditor = false;

		this.update( /*true*/ );

	}

	serialize( data ) {

		super.serialize( data );

		data.layoutJSON = this.layoutJSON;

	}

	deserialize( data ) {

		this.updateLayout( JSON.parse( data.layoutJSON || '{}' ), true );

		this.waitToLayoutJSON = data.layoutJSON;

		super.deserialize( data );

	}

}
```
</details>

#### Methods

##### `getColor(): string`

<details><summary>Code</summary>

```ts
getColor() {

		const color = getColorFromType( this.layout ? this.layout.outputType : null );

		return color ? color + 'BB' : null;

	}
```
</details>

##### `hasJSON(): boolean`

<details><summary>Code</summary>

```ts
hasJSON() {

		return true;

	}
```
</details>

##### `exportJSON(): any`

<details><summary>Code</summary>

```ts
exportJSON() {

		return this.scriptableNode.toJSON();

	}
```
</details>

##### `setSource(source: any): this`

<details><summary>Code</summary>

```ts
setSource( source ) {

		this.editorCodeNode.code = source;

		this.update();

		return this;

	}
```
</details>

##### `update(force: boolean): void`

<details><summary>Code</summary>

```ts
update( force = false ) {

		if ( this._updating === true ) return;

		this._updating = true;

		this.scriptableNode.codeNode = this.codeNode;
		this.scriptableNode.needsUpdate = true;

		let layout = null;
		let scriptableValueOutput = null;

		try {

			const object = this.scriptableNode.getObject();

			layout = this.scriptableNode.getLayout();

			this.updateLayout( layout, force );

			scriptableValueOutput = this.scriptableNode.getDefaultOutput();

			const initCacheKey = typeof object.init === 'function' ? object.init.toString() : '';

			if ( initCacheKey !== this.initCacheKey ) {

				this.initCacheKey = initCacheKey;

				const initId = ++ this.initId;

				this.scriptableNode.callAsync( 'init' ).then( () => {

					if ( initId === this.initId ) {

						this.update();

						if ( this.editor ) this.editor.tips.message( 'ScriptEditor: Initialized.' );

					}

				} );

			}

		} catch ( e ) {

			console.error( e );

			if ( this.editor ) this.editor.tips.error( e.message );

		}

		const editorOutput = scriptableValueOutput ? scriptableValueOutput.value : null;

		this.value = isGPUNode( editorOutput ) ? this.scriptableNode : scriptableValueOutput;
		this.layout = layout;
		this.editorOutput = editorOutput;

		this.updateOutputInEditor();
		this.updateOutputConnection();

		this.invalidate();

		this._updating = false;

	}
```
</details>

##### `updateOutputConnection(): void`

<details><summary>Code</summary>

```ts
updateOutputConnection() {

		const layout = this.layout;

		if ( layout ) {

			const outputType = layout.outputType;

			setOutputAestheticsFromType( this.title, outputType );

		} else {

			this.title.setOutput( 0 );

		}

	}
```
</details>

##### `updateOutputInEditor(): void`

<details><summary>Code</summary>

```ts
updateOutputInEditor() {

		const { editor, editorOutput, editorOutputAdded } = this;

		if ( editor && editorOutput === editorOutputAdded ) return;

		const scene = ScriptableNodeResources.get( 'scene' );
		const composer = ScriptableNodeResources.get( 'composer' );

		if ( editor ) {

			if ( editorOutputAdded && editorOutputAdded.isObject3D === true ) {

				editorOutputAdded.removeFromParent();

				disposeScene( editorOutputAdded );

				resetScene( scene );

			} else if ( composer && editorOutputAdded && editorOutputAdded.isPass === true ) {

				composer.removePass( editorOutputAdded );

			}

			if ( editorOutput && editorOutput.isObject3D === true ) {

				scene.add( editorOutput );

			} else if ( composer && editorOutput && editorOutput.isPass === true ) {

				composer.addPass( editorOutput );

			}

			this.editorOutputAdded = editorOutput;

		} else {

			if ( editorOutputAdded && editorOutputAdded.isObject3D === true ) {

				editorOutputAdded.removeFromParent();

				disposeScene( editorOutputAdded );

				resetScene( scene );

			} else if ( composer && editorOutputAdded && editorOutputAdded.isPass === true ) {

				composer.removePass( editorOutputAdded );

			}

			this.editorOutputAdded = null;

		}

	}
```
</details>

##### `setEditor(editor: any): void`

<details><summary>Code</summary>

```ts
setEditor( editor ) {

		super.setEditor( editor );

		this.updateOutputInEditor();

	}
```
</details>

##### `clearParameters(): void`

<details><summary>Code</summary>

```ts
clearParameters() {

		this.layoutJSON = '';

		this.scriptableNode.clearParameters();

		for ( const element of this.elements.concat() ) {

			if ( element !== this.editorElement && element !== this.title ) {

				this.remove( element );

			}

		}

	}
```
</details>

##### `addElementFromJSON(json: any): any`

<details><summary>Code</summary>

```ts
addElementFromJSON( json ) {

		const { id, element, inputNode, outputType } = createElementFromJSON( json );

		this.add( element );

		this.scriptableNode.setParameter( id, inputNode );

		if ( outputType ) {

			element.setObjectCallback( () => {

				return this.scriptableNode.getOutput( id );

			} );

		}

		//

		const onUpdate = () => {

			const value = element.value;
			const paramValue = value && value.isScriptableValueNode ? value : scriptableValue( value );

			this.scriptableNode.setParameter( id, paramValue );

			this.update();

		};

		element.addEventListener( 'changeInput', onUpdate );
		element.onConnect( onUpdate, true );

		//element.onConnect( () => this.getScriptable().call( 'onDeepChange' ), true );

		return element;

	}
```
</details>

##### `updateLayout(layout: any, force: boolean): void`

<details><summary>Code</summary>

```ts
updateLayout( layout = null, force = false ) {

		const needsUpdateWidth = this.hasExternalEditor || this.editorElement === null;

		if ( this.waitToLayoutJSON !== null ) {

			if ( this.waitToLayoutJSON === JSON.stringify( layout || '{}' ) ) {

				this.waitToLayoutJSON = null;

				if ( needsUpdateWidth ) this.setWidth( layout.width );

			} else {

				return;

			}

		}

		if ( layout ) {

			const layoutCacheKey = JSON.stringify( layout );

			if ( this.layoutJSON !== layoutCacheKey || force === true ) {

				this.clearParameters();

				if ( layout.name ) {

					this.setName( layout.name );

				}


				if ( layout.icon ) {

					this.setIcon( layout.icon );

				}

				if ( needsUpdateWidth ) {

					if ( layout.width !== undefined ) {

                		this.setWidth( layout.width );

					} else {

						this.setWidth( defaultWidth );

					}

				}

				if ( layout.elements ) {

					for ( const element of layout.elements ) {

						this.addElementFromJSON( element );

					}

					if ( this.editorElement ) {

						this.remove( this.editorElement );
						this.add( this.editorElement );

					}

				}

				this.layoutJSON = layoutCacheKey;

			}

		} else {

			this.setName( defaultTitle );
			this.setIcon( null );
			this.setWidth( defaultWidth );

			this.clearParameters();

		}

		this.updateOutputConnection();

	}
```
</details>

##### `_initExternalConnection(): void`

<details><summary>Code</summary>

```ts
_initExternalConnection() {

		setInputAestheticsFromType( this.title, 'CodeNode' ).onValid( onValidType( 'CodeNode' ) ).onConnect( () => {

			this.hasExternalEditor ? this._toExternal() : this._toInternal();

			this.update();

		}, true );

	}
```
</details>

##### `_toInternal(): void`

<details><summary>Code</summary>

```ts
_toInternal() {

		if ( this.hasInternalEditor === true ) return;

		if ( this.editorElement === null ) {

			this.editorElement = new CodeEditorElement( this.editorCodeNode.code );
			this.editorElement.addEventListener( 'change', () => {

				this.setSource( this.editorElement.source );

				this.editorElement.focus();

			} );

			this.add( this.editorElement );

		}

		this.setResizable( true );

		this.editorElement.setVisible( true );

		this.hasInternalEditor = true;

		this.update( /*true*/ );

	}
```
</details>

##### `_toExternal(): void`

<details><summary>Code</summary>

```ts
_toExternal() {

		if ( this.hasInternalEditor === false ) return;

		this.editorElement.setVisible( false );

		this.setResizable( false );

		this.hasInternalEditor = false;

		this.update( /*true*/ );

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.layoutJSON = this.layoutJSON;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		this.updateLayout( JSON.parse( data.layoutJSON || '{}' ), true );

		this.waitToLayoutJSON = data.layoutJSON;

		super.deserialize( data );

	}
```
</details>


---