[⬅️ Back to Table of Contents](../index.md)

# 📄 `NodeEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 25 |
| 🧱 Classes | 1 |
| 📦 Imports | 19 |
| 📊 Variables & Constants | 41 |
| ⚡ Async/Await Patterns | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/NodeEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Canvas` | `flow` |
| `CircleMenu` | `flow` |
| `ButtonInput` | `flow` |
| `StringInput` | `flow` |
| `ContextMenu` | `flow` |
| `Tips` | `flow` |
| `Search` | `flow` |
| `Loader` | `flow` |
| `Node` | `flow` |
| `TreeViewNode` | `flow` |
| `TreeViewInput` | `flow` |
| `Element` | `flow` |
| `FileEditor` | `./editors/FileEditor.js` |
| `exportJSON` | `./NodeEditorUtils.js` |
| `init` | `./NodeEditorLib.js` |
| `ClassLib` | `./NodeEditorLib.js` |
| `getNodeEditorClass` | `./NodeEditorLib.js` |
| `getNodeList` | `./NodeEditorLib.js` |
| `SplitscreenManager` | `./SplitscreenManager.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `canvas` | `any` | let/var | `new Canvas()` | ✗ |
| `canvas` | `any` | let/var | `this.canvas` | ✗ |
| `canvas` | `any` | let/var | `this.canvas` | ✗ |
| `loader` | `any` | let/var | `new Loader( Loader.OBJECTS )` | ✗ |
| `json` | `any` | let/var | `await loader.load( url, ClassLib )` | ✗ |
| `canvas` | `any` | let/var | `this.canvas` | ✗ |
| `canvas` | `any` | let/var | `this.canvas` | ✗ |
| `reader` | `FileReader` | let/var | `new FileReader()` | ✗ |
| `fileEditor` | `FileEditor` | let/var | `new FileEditor( reader.result, file.name )` | ✗ |
| `menu` | `any` | let/var | `new CircleMenu()` | ✗ |
| `previewMenu` | `any` | let/var | `new CircleMenu()` | ✗ |
| `file` | `any` | let/var | `e.target.files[ 0 ]` | ✗ |
| `reader` | `FileReader` | let/var | `new FileReader()` | ✗ |
| `loader` | `any` | let/var | `new Loader( Loader.OBJECTS )` | ✗ |
| `context` | `any` | let/var | `new ContextMenu()` | ✗ |
| `subContext` | `any` | let/var | `new ContextMenu()` | ✗ |
| `key` | `string` | let/var | `e.key` | ✗ |
| `urlParams` | `URLSearchParams` | let/var | `new URLSearchParams( window.location.search )` | ✗ |
| `example` | `string` | let/var | `urlParams.get( 'example' ) \|\| 'basic/teapot'` | ✗ |
| `button` | `any` | let/var | `new ButtonInput( item.name )` | ✗ |
| `nodeClass` | `any` | let/var | `await getNodeEditorClass( item )` | ✗ |
| `node` | `any` | let/var | `new nodeClass()` | ✗ |
| `search` | `any` | let/var | `new Search()` | ✗ |
| `nodeList` | `any` | let/var | `await getNodeList()` | ✗ |
| `isContext` | `boolean` | let/var | `false` | ✗ |
| `contextPosition` | `{}` | let/var | `{}` | ✗ |
| `nodeButtons` | `any[]` | let/var | `[]` | ✗ |
| `nodeButtonsVisible` | `any[]` | let/var | `[]` | ✗ |
| `nodeButtonsIndex` | `number` | let/var | `- 1` | ✗ |
| `node` | `any` | let/var | `new Node()` | ✗ |
| `key` | `any` | let/var | `e.key` | ✗ |
| `previous` | `any` | let/var | `nodeButtonsVisible[ nodeButtonsIndex ]` | ✗ |
| `current` | `any` | let/var | `nodeButtonsVisible[ nodeButtonsIndex = ( nodeButtonsIndex + 1 ) % nodeButtons...` | ✗ |
| `previous` | `any` | let/var | `nodeButtonsVisible[ nodeButtonsIndex ]` | ✗ |
| `current` | `any` | let/var | `nodeButtonsVisible[ nodeButtonsIndex > 0 ? -- nodeButtonsIndex : ( nodeButton...` | ✗ |
| `visible` | `boolean` | let/var | `buttonLabel.indexOf( value ) !== - 1` | ✗ |
| `parent` | `any` | let/var | `button` | ✗ |
| `treeView` | `any` | let/var | `new TreeViewInput()` | ✗ |
| `button` | `any` | let/var | `new TreeViewNode( nodeData.name )` | ✗ |
| `nodeClass` | `any` | let/var | `await getNodeEditorClass( nodeData )` | ✗ |
| `nodeList` | `any` | let/var | `await getNodeList()` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `onClickExample` | *none* | *none* |
| await-expression | `traverseNodeEditors` | getNodeEditorClass( item ) | *none* |
| await-expression | `addNodeEditorElement` | getNodeEditorClass( nodeData ) | *none* |


---

## Functions

### `NodeEditor.setSize(width: any, height: any): this`

**Parameters:**

- **`width`** `any`
- **`height`** `any`

**Returns:** `this`

**Calls:**

- `this.canvas.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this.canvas.setSize( width, height );

		return this;

	}
```
</details>

### `NodeEditor.centralizeNode(node: any): this`

**Parameters:**

- **`node`** `any`

**Returns:** `this`

**Calls:**

- `node.dom.getBoundingClientRect`
- `node.setPosition`

<details><summary>Code</summary>

```typescript
centralizeNode( node ) {

		const canvas = this.canvas;
		const nodeRect = node.dom.getBoundingClientRect();

		node.setPosition(
			( ( canvas.width / 2 ) - canvas.scrollLeft ) - nodeRect.width,
			( ( canvas.height / 2 ) - canvas.scrollTop ) - nodeRect.height
		);

		return this;

	}
```
</details>

### `NodeEditor.add(node: any): this`

**Parameters:**

- **`node`** `any`

**Returns:** `this`

**Calls:**

- `node.removeEventListener`
- `node.setEditor`
- `node.addEventListener`
- `this.canvas.add`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
add( node ) {

		const onRemove = () => {

			node.removeEventListener( 'remove', onRemove );

			node.setEditor( null );

		};

		node.setEditor( this );
		node.addEventListener( 'remove', onRemove );

		this.canvas.add( node );

		this.dispatchEvent( { type: 'add', node } );

		return this;

	}
```
</details>

### `NodeEditor.newProject(): void`

**Returns:** `void`

**Calls:**

- `canvas.clear`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
newProject() {

		const canvas = this.canvas;
		canvas.clear();
		canvas.scrollLeft = 0;
		canvas.scrollTop = 0;
		canvas.zoom = 1;

		this.dispatchEvent( { type: 'new' } );

	}
```
</details>

### `NodeEditor.loadURL(url: any): Promise<void>`

**Parameters:**

- **`url`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `loader.load`
- `this.loadJSON`

<details><summary>Code</summary>

```typescript
async loadURL( url ) {

		const loader = new Loader( Loader.OBJECTS );
		const json = await loader.load( url, ClassLib );

		this.loadJSON( json );

	}
```
</details>

### `NodeEditor.loadJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `canvas.clear`
- `canvas.deserialize`
- `this.add`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
loadJSON( json ) {

		const canvas = this.canvas;

		canvas.clear();

		canvas.deserialize( json );

		for ( const node of canvas.nodes ) {

			this.add( node );

		}

		this.dispatchEvent( { type: 'load' } );

	}
```
</details>

### `NodeEditor._initSplitview(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_initSplitview() {

		this.splitview = new SplitscreenManager( this );

	}
```
</details>

### `NodeEditor._initUpload(): void`

**Returns:** `void`

**Calls:**

- `canvas.onDrop`
- `item.getAsFile`
- `fileEditor.setPosition`
- `fileEditor.getWidth`
- `this.add`
- `reader.readAsArrayBuffer`

<details><summary>Code</summary>

```typescript
_initUpload() {

		const canvas = this.canvas;

		canvas.onDrop( () => {

			for ( const item of canvas.droppedItems ) {

				const { relativeClientX, relativeClientY } = canvas;

				const file = item.getAsFile();
				const reader = new FileReader();

				reader.onload = () => {

					const fileEditor = new FileEditor( reader.result, file.name );

					fileEditor.setPosition(
						relativeClientX - ( fileEditor.getWidth() / 2 ),
						relativeClientY - 20
					);

					this.add( fileEditor );

				};

				reader.readAsArrayBuffer( file );

			}

		} );

	}
```
</details>

### `NodeEditor._initTips(): void`

**Returns:** `void`

**Calls:**

- `this.domElement.append`

<details><summary>Code</summary>

```typescript
_initTips() {

		this.tips = new Tips();

		this.domElement.append( this.tips.dom );

	}
```
</details>

### `NodeEditor._initMenu(): void`

**Returns:** `void`

**Calls:**

- `menu.setAlign`
- `previewMenu.setAlign`
- `new ButtonInput().setIcon( 'ti ti-brand-threejs' ).setToolTip`
- `new ButtonInput().setIcon( 'ti ti-layout-sidebar-right-expand' ).setToolTip`
- `new ButtonInput().setIcon( 'ti ti-apps' ).setToolTip`
- `new ButtonInput().setIcon( 'ti ti-file-symlink' ).setToolTip`
- `new ButtonInput().setIcon( 'ti ti-file' ).setToolTip`
- `new ButtonInput().setIcon( 'ti ti-upload' ).setToolTip`
- `new ButtonInput().setIcon( 'ti ti-download' ).setToolTip`
- `new ButtonInput().setIcon( 'ti ti-subtask' ).setToolTip`
- `previewButton.onClick`
- `editorButton.onClick`
- `splitscreenButton.onClick`
- `splitscreenButton.setIcon`
- `menuButton.onClick`
- `this.nodesContext.open`
- `examplesButton.onClick`
- `this.examplesContext.open`
- `newButton.onClick`
- `confirm`
- `this.newProject`
- `openButton.onClick`
- `document.createElement`
- `reader.readAsText`
- `loader.parse`
- `JSON.parse`
- `this.loadJSON`
- `input.click`
- `saveButton.onClick`
- `exportJSON (from ./NodeEditorUtils.js)`
- `this.canvas.toJSON`
- `menu.add( previewButton )
			.add( splitscreenButton )
			.add( newButton )
			.add( examplesButton )
			.add( openButton )
			.add( saveButton )
			.add`
- `previewMenu.add`
- `this.domElement.appendChild`

<details><summary>Code</summary>

```typescript
_initMenu() {

		const menu = new CircleMenu();
		const previewMenu = new CircleMenu();

		menu.setAlign( 'top left' );
		previewMenu.setAlign( 'top left' );

		const previewButton = new ButtonInput().setIcon( 'ti ti-brand-threejs' ).setToolTip( 'Preview' );
		const splitscreenButton = new ButtonInput().setIcon( 'ti ti-layout-sidebar-right-expand' ).setToolTip( 'Splitscreen' );
		const menuButton = new ButtonInput().setIcon( 'ti ti-apps' ).setToolTip( 'Add' );
		const examplesButton = new ButtonInput().setIcon( 'ti ti-file-symlink' ).setToolTip( 'Examples' );
		const newButton = new ButtonInput().setIcon( 'ti ti-file' ).setToolTip( 'New' );
		const openButton = new ButtonInput().setIcon( 'ti ti-upload' ).setToolTip( 'Open' );
		const saveButton = new ButtonInput().setIcon( 'ti ti-download' ).setToolTip( 'Save' );

		const editorButton = new ButtonInput().setIcon( 'ti ti-subtask' ).setToolTip( 'Editor' );

		previewButton.onClick( () => this.preview = true );
		editorButton.onClick( () => this.preview = false );

		splitscreenButton.onClick( () => {

			this.splitscreen = ! this.splitscreen;
			splitscreenButton.setIcon( this.splitscreen ? 'ti ti-layout-sidebar-right-collapse' : 'ti ti-layout-sidebar-right-expand' );

		} );

		menuButton.onClick( () => this.nodesContext.open() );
		examplesButton.onClick( () => this.examplesContext.open() );

		newButton.onClick( () => {

			if ( confirm( 'Are you sure?' ) === true ) {

				this.newProject();

			}

		} );

		openButton.onClick( () => {

			const input = document.createElement( 'input' );
			input.type = 'file';

			input.onchange = e => {

				const file = e.target.files[ 0 ];

				const reader = new FileReader();
				reader.readAsText( file, 'UTF-8' );

				reader.onload = readerEvent => {

					const loader = new Loader( Loader.OBJECTS );
					const json = loader.parse( JSON.parse( readerEvent.target.result ), ClassLib );

					this.loadJSON( json );

				};

			};

			input.click();

		} );

		saveButton.onClick( () => {

			exportJSON( this.canvas.toJSON(), 'node_editor' );

		} );

		menu.add( previewButton )
			.add( splitscreenButton )
			.add( newButton )
			.add( examplesButton )
			.add( openButton )
			.add( saveButton )
			.add( menuButton );

		previewMenu.add( editorButton );

		this.domElement.appendChild( menu.dom );

		this.menu = menu;
		this.previewMenu = previewMenu;

	}
```
</details>

### `NodeEditor._initExamplesContext(): void`

**Returns:** `void`

**Calls:**

- `this.examplesContext.hide`
- `button.getExtra`
- `this.loadURL`
- `name.replaceAll( ' ', '-' ).toLowerCase`
- `subContext.add`
- `new ButtonInput( name )
					.setIcon( 'ti ti-file-symlink' )
					.onClick( onClickExample )
					.setExtra`
- `category.toLowerCase`
- `context.add`
- `addExamples`

**Internal Comments:**
```
//**************// (x10)
// MAIN (x2)
// EXAMPLES (x3)
```

<details><summary>Code</summary>

```typescript
_initExamplesContext() {

		const context = new ContextMenu();

		//**************//
		// MAIN
		//**************//

		const onClickExample = async ( button ) => {

			this.examplesContext.hide();

			const filename = button.getExtra();

			this.loadURL( `./examples/${filename}.json` );

		};

		const addExamples = ( category, names ) => {

			const subContext = new ContextMenu();

			for ( const name of names ) {

				const filename = name.replaceAll( ' ', '-' ).toLowerCase();

				subContext.add( new ButtonInput( name )
					.setIcon( 'ti ti-file-symlink' )
					.onClick( onClickExample )
					.setExtra( category.toLowerCase() + '/' + filename )
				);

			}

			context.add( new ButtonInput( category ), subContext );

			return subContext;

		};

		//**************//
		// EXAMPLES
		//**************//

		addExamples( 'Basic', [
			'Teapot',
			'Matcap',
			'Fresnel',
			'Particles'
		] );

		this.examplesContext = context;

	}
```
</details>

### `NodeEditor._initShortcuts(): void`

**Returns:** `void`

**Calls:**

- `document.addEventListener`
- `this.search.inputDOM.focus`
- `e.preventDefault`
- `e.stopImmediatePropagation`
- `this.canvas.selected.dispose`
- `this.canvas.select`

<details><summary>Code</summary>

```typescript
_initShortcuts() {

		document.addEventListener( 'keydown', ( e ) => {

			if ( e.target === document.body ) {

				const key = e.key;

				if ( key === 'Tab' ) {

					this.search.inputDOM.focus();

					e.preventDefault();
					e.stopImmediatePropagation();

				} else if ( key === ' ' ) {

					this.preview = ! this.preview;

				} else if ( key === 'Delete' ) {

					if ( this.canvas.selected ) this.canvas.selected.dispose();

				} else if ( key === 'Escape' ) {

					this.canvas.select( null );

				}

			}

		} );

	}
```
</details>

### `NodeEditor._initParams(): void`

**Returns:** `void`

**Calls:**

- `urlParams.get`
- `this.loadURL`

<details><summary>Code</summary>

```typescript
_initParams() {

		const urlParams = new URLSearchParams( window.location.search );

		const example = urlParams.get( 'example' ) || 'basic/teapot';

		this.loadURL( `./examples/${example}.json` );

	}
```
</details>

### `NodeEditor.addClass(nodeData: any): this`

**Parameters:**

- **`nodeData`** `any`

**Returns:** `this`

**Calls:**

- `this.removeClass`
- `this.nodeClasses.push`

<details><summary>Code</summary>

```typescript
addClass( nodeData ) {

		this.removeClass( nodeData );

		this.nodeClasses.push( nodeData );

		ClassLib[ nodeData.name ] = nodeData.nodeClass;

		return this;

	}
```
</details>

### `NodeEditor.removeClass(nodeData: any): this`

**Parameters:**

- **`nodeData`** `any`

**Returns:** `this`

**Calls:**

- `this.nodeClasses.indexOf`
- `this.nodeClasses.splice`

<details><summary>Code</summary>

```typescript
removeClass( nodeData ) {

		const index = this.nodeClasses.indexOf( nodeData );

		if ( index !== - 1 ) {

			this.nodeClasses.splice( index, 1 );

			delete ClassLib[ nodeData.name ];

		}

		return this;

	}
```
</details>

### `NodeEditor._initSearch(): void`

**Returns:** `void`

**Calls:**

- `traverseNodeEditors`
- `button.setIcon`
- `button.addEventListener`
- `getNodeEditorClass (from ./NodeEditorLib.js)`
- `this.add`
- `this.centralizeNode`
- `this.canvas.select`
- `search.add`
- `search.setTag`
- `search.onFilter`
- `search.clear`
- `getNodeList (from ./NodeEditorLib.js)`
- `search.onSubmit`
- `search.currentFiltered.button.dispatchEvent`
- `this.domElement.append`

<details><summary>Code</summary>

```typescript
_initSearch() {

		const traverseNodeEditors = ( item ) => {

			if ( item.children ) {

				for ( const subItem of item.children ) {

					traverseNodeEditors( subItem );

				}

			} else {

				const button = new ButtonInput( item.name );
				button.setIcon( `ti ti-${item.icon}` );
				button.addEventListener( 'complete', async () => {

					const nodeClass = await getNodeEditorClass( item );

					const node = new nodeClass();

					this.add( node );

					this.centralizeNode( node );
					this.canvas.select( node );

				} );

				search.add( button );

				if ( item.tags !== undefined ) {

					search.setTag( button, item.tags );

				}

			}



		};

		const search = new Search();
		search.forceAutoComplete = true;

		search.onFilter( async () => {

			search.clear();

			const nodeList = await getNodeList();

			for ( const item of nodeList.nodes ) {

				traverseNodeEditors( item );

			}

			for ( const item of this.nodeClasses ) {

				traverseNodeEditors( item );

			}

		} );

		search.onSubmit( () => {

			if ( search.currentFiltered !== null ) {

				search.currentFiltered.button.dispatchEvent( new Event( 'complete' ) );

			}

		} );

		this.search = search;

		this.domElement.append( search.dom );

	}
```
</details>

### `NodeEditor._initNodesContext(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `new ContextMenu( this.canvas.canvas ).setWidth`
- `context.hide`
- `this.add`
- `node.setPosition`
- `Math.round`
- `this.centralizeNode`
- `this.canvas.select`
- `context.onContext`
- `context.addEventListener`
- `reset`
- `focus`
- `requestAnimationFrame`
- `search.inputDOM.focus`
- `search.setValue`
- `button.setOpened( false ).setVisible( true ).setSelected`
- `context.add`
- `new StringInput().setPlaceHolder( 'Search...' ).setIcon`
- `search.inputDOM.addEventListener`
- `previous.setSelected`
- `current.setSelected`
- `e.preventDefault`
- `e.stopImmediatePropagation`
- `nodeButtonsVisible[ nodeButtonsIndex ].dom.click`
- `search.onChange`
- `search.getValue().toLowerCase`
- `button.getLabel().toLowerCase`
- `button.setVisible( false ).setSelected`
- `buttonLabel.indexOf`
- `nodeButtonsVisible.push`
- `parent.setOpened( true ).setVisible`
- `nodeButtonsVisible[ nodeButtonsIndex ].setSelected`
- `node.add`
- `new Element().setHeight( 30 ).add`
- `new Element().setHeight( 200 ).add`
- `button.setIcon`
- `button.onClick`
- `getNodeEditorClass (from ./NodeEditorLib.js)`
- `add`
- `nodeButtons.push`
- `addNodeEditorElement`
- `button.add`
- `getNodeList (from ./NodeEditorLib.js)`
- `treeView.add`

**Internal Comments:**
```
//**************// (x4)
// INPUTS (x2)
// (x2)
```

<details><summary>Code</summary>

```typescript
async _initNodesContext() {

		const context = new ContextMenu( this.canvas.canvas ).setWidth( 300 );

		let isContext = false;
		const contextPosition = {};

		const add = ( node ) => {

			context.hide();

			this.add( node );

			if ( isContext ) {

				node.setPosition(
					Math.round( contextPosition.x ),
					Math.round( contextPosition.y )
				);

			} else {

				this.centralizeNode( node );

			}

			this.canvas.select( node );

			isContext = false;

		};

		context.onContext( () => {

			isContext = true;

			const { relativeClientX, relativeClientY } = this.canvas;

			contextPosition.x = Math.round( relativeClientX );
			contextPosition.y = Math.round( relativeClientY );

		} );

		context.addEventListener( 'show', () => {

			reset();
			focus();

		} );

		//**************//
		// INPUTS
		//**************//

		const nodeButtons = [];

		let nodeButtonsVisible = [];
		let nodeButtonsIndex = - 1;

		const focus = () => requestAnimationFrame( () => search.inputDOM.focus() );
		const reset = () => {

			search.setValue( '', false );

			for ( const button of nodeButtons ) {

				button.setOpened( false ).setVisible( true ).setSelected( false );

			}

		};

		const node = new Node();
		context.add( node );

		const search = new StringInput().setPlaceHolder( 'Search...' ).setIcon( 'ti ti-list-search' );

		search.inputDOM.addEventListener( 'keydown', e => {

			const key = e.key;

			if ( key === 'ArrowDown' ) {

				const previous = nodeButtonsVisible[ nodeButtonsIndex ];
				if ( previous ) previous.setSelected( false );

				const current = nodeButtonsVisible[ nodeButtonsIndex = ( nodeButtonsIndex + 1 ) % nodeButtonsVisible.length ];
				if ( current ) current.setSelected( true );

				e.preventDefault();
				e.stopImmediatePropagation();

			} else if ( key === 'ArrowUp' ) {

				const previous = nodeButtonsVisible[ nodeButtonsIndex ];
				if ( previous ) previous.setSelected( false );

				const current = nodeButtonsVisible[ nodeButtonsIndex > 0 ? -- nodeButtonsIndex : ( nodeButtonsIndex = nodeButtonsVisible.length - 1 ) ];
				if ( current ) current.setSelected( true );

				e.preventDefault();
				e.stopImmediatePropagation();

			} else if ( key === 'Enter' ) {

				if ( nodeButtonsVisible[ nodeButtonsIndex ] !== undefined ) {

					nodeButtonsVisible[ nodeButtonsIndex ].dom.click();

				} else {

					context.hide();

				}

				e.preventDefault();
				e.stopImmediatePropagation();

			} else if ( key === 'Escape' ) {

				context.hide();

			}

		} );

		search.onChange( () => {

			const value = search.getValue().toLowerCase();

			if ( value.length === 0 ) return reset();

			nodeButtonsVisible = [];
			nodeButtonsIndex = 0;

			for ( const button of nodeButtons ) {

				const buttonLabel = button.getLabel().toLowerCase();

				button.setVisible( false ).setSelected( false );

				const visible = buttonLabel.indexOf( value ) !== - 1;

				if ( visible && button.children.length === 0 ) {

					nodeButtonsVisible.push( button );

				}

			}

			for ( const button of nodeButtonsVisible ) {

				let parent = button;

				while ( parent !== null ) {

					parent.setOpened( true ).setVisible( true );

					parent = parent.parent;

				}

			}

			if ( nodeButtonsVisible[ nodeButtonsIndex ] !== undefined ) {

				nodeButtonsVisible[ nodeButtonsIndex ].setSelected( true );

			}

		} );

		const treeView = new TreeViewInput();
		node.add( new Element().setHeight( 30 ).add( search ) );
		node.add( new Element().setHeight( 200 ).add( treeView ) );

		const addNodeEditorElement = ( nodeData ) => {

			const button = new TreeViewNode( nodeData.name );
			button.setIcon( `ti ti-${nodeData.icon}` );

			if ( nodeData.children === undefined ) {

				button.isNodeClass = true;
				button.onClick( async () => {

					const nodeClass = await getNodeEditorClass( nodeData );

					add( new nodeClass() );

				} );

			}

			if ( nodeData.tip ) {

				//button.setToolTip( item.tip );

			}

			nodeButtons.push( button );

			if ( nodeData.children ) {

				for ( const subItem of nodeData.children ) {

					const subButton = addNodeEditorElement( subItem );

					button.add( subButton );

				}

			}

			return button;

		};

		//

		const nodeList = await getNodeList();

		for ( const node of nodeList.nodes ) {

			const button = addNodeEditorElement( node );

			treeView.add( button );

		}

		this.nodesContext = context;

	}
```
</details>

### `onRemove(): void`

**Returns:** `void`

**Calls:**

- `node.removeEventListener`
- `node.setEditor`

<details><summary>Code</summary>

```typescript
() => {

			node.removeEventListener( 'remove', onRemove );

			node.setEditor( null );

		}
```
</details>

### `onClickExample(button: any): Promise<void>`

**Parameters:**

- **`button`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `this.examplesContext.hide`
- `button.getExtra`
- `this.loadURL`

<details><summary>Code</summary>

```typescript
async ( button ) => {

			this.examplesContext.hide();

			const filename = button.getExtra();

			this.loadURL( `./examples/${filename}.json` );

		}
```
</details>

### `addExamples(category: any, names: any): any`

**Parameters:**

- **`category`** `any`
- **`names`** `any`

**Returns:** `any`

**Calls:**

- `name.replaceAll( ' ', '-' ).toLowerCase`
- `subContext.add`
- `new ButtonInput( name )
					.setIcon( 'ti ti-file-symlink' )
					.onClick( onClickExample )
					.setExtra`
- `category.toLowerCase`
- `context.add`

<details><summary>Code</summary>

```typescript
( category, names ) => {

			const subContext = new ContextMenu();

			for ( const name of names ) {

				const filename = name.replaceAll( ' ', '-' ).toLowerCase();

				subContext.add( new ButtonInput( name )
					.setIcon( 'ti ti-file-symlink' )
					.onClick( onClickExample )
					.setExtra( category.toLowerCase() + '/' + filename )
				);

			}

			context.add( new ButtonInput( category ), subContext );

			return subContext;

		}
```
</details>

### `traverseNodeEditors(item: any): void`

**Parameters:**

- **`item`** `any`

**Returns:** `void`

**Calls:**

- `traverseNodeEditors`
- `button.setIcon`
- `button.addEventListener`
- `getNodeEditorClass (from ./NodeEditorLib.js)`
- `this.add`
- `this.centralizeNode`
- `this.canvas.select`
- `search.add`
- `search.setTag`

<details><summary>Code</summary>

```typescript
( item ) => {

			if ( item.children ) {

				for ( const subItem of item.children ) {

					traverseNodeEditors( subItem );

				}

			} else {

				const button = new ButtonInput( item.name );
				button.setIcon( `ti ti-${item.icon}` );
				button.addEventListener( 'complete', async () => {

					const nodeClass = await getNodeEditorClass( item );

					const node = new nodeClass();

					this.add( node );

					this.centralizeNode( node );
					this.canvas.select( node );

				} );

				search.add( button );

				if ( item.tags !== undefined ) {

					search.setTag( button, item.tags );

				}

			}



		}
```
</details>

### `add(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `context.hide`
- `this.add`
- `node.setPosition`
- `Math.round`
- `this.centralizeNode`
- `this.canvas.select`

<details><summary>Code</summary>

```typescript
( node ) => {

			context.hide();

			this.add( node );

			if ( isContext ) {

				node.setPosition(
					Math.round( contextPosition.x ),
					Math.round( contextPosition.y )
				);

			} else {

				this.centralizeNode( node );

			}

			this.canvas.select( node );

			isContext = false;

		}
```
</details>

### `focus(): number`

**Returns:** `number`

**Calls:**

- `requestAnimationFrame`

<details><summary>Code</summary>

```typescript
() => requestAnimationFrame( () => search.inputDOM.focus() )
```
</details>

### `reset(): void`

**Returns:** `void`

**Calls:**

- `search.setValue`
- `button.setOpened( false ).setVisible( true ).setSelected`

<details><summary>Code</summary>

```typescript
() => {

			search.setValue( '', false );

			for ( const button of nodeButtons ) {

				button.setOpened( false ).setVisible( true ).setSelected( false );

			}

		}
```
</details>

### `addNodeEditorElement(nodeData: any): any`

**Parameters:**

- **`nodeData`** `any`

**Returns:** `any`

**Calls:**

- `button.setIcon`
- `button.onClick`
- `getNodeEditorClass (from ./NodeEditorLib.js)`
- `add`
- `nodeButtons.push`
- `addNodeEditorElement`
- `button.add`

<details><summary>Code</summary>

```typescript
( nodeData ) => {

			const button = new TreeViewNode( nodeData.name );
			button.setIcon( `ti ti-${nodeData.icon}` );

			if ( nodeData.children === undefined ) {

				button.isNodeClass = true;
				button.onClick( async () => {

					const nodeClass = await getNodeEditorClass( nodeData );

					add( new nodeClass() );

				} );

			}

			if ( nodeData.tip ) {

				//button.setToolTip( item.tip );

			}

			nodeButtons.push( button );

			if ( nodeData.children ) {

				for ( const subItem of nodeData.children ) {

					const subButton = addNodeEditorElement( subItem );

					button.add( subButton );

				}

			}

			return button;

		}
```
</details>


---

## Classes

### `NodeEditor`

<details><summary>Class Code</summary>

```ts
export class NodeEditor extends THREE.EventDispatcher {

	constructor( scene = null, renderer = null, composer = null ) {

		super();

		const domElement = document.createElement( 'flow' );
		const canvas = new Canvas();

		domElement.append( canvas.dom );

		this.scene = scene;
		this.renderer = renderer;

		const { ScriptableNodeResources } = TSL;

		ScriptableNodeResources.set( 'THREE', THREE );
		ScriptableNodeResources.set( 'TSL', TSL );

		ScriptableNodeResources.set( 'scene', scene );
		ScriptableNodeResources.set( 'renderer', renderer );
		ScriptableNodeResources.set( 'composer', composer );

		this.nodeClasses = [];

		this.canvas = canvas;
		this.domElement = domElement;

		this._preview = false;
		this._splitscreen = false;

		this.search = null;

		this.menu = null;
		this.previewMenu = null;

		this.nodesContext = null;
		this.examplesContext = null;

		this._initSplitview();
		this._initUpload();
		this._initTips();
		this._initMenu();
		this._initSearch();
		this._initNodesContext();
		this._initExamplesContext();
		this._initShortcuts();
		this._initParams();

	}

	setSize( width, height ) {

		this.canvas.setSize( width, height );

		return this;

	}

	centralizeNode( node ) {

		const canvas = this.canvas;
		const nodeRect = node.dom.getBoundingClientRect();

		node.setPosition(
			( ( canvas.width / 2 ) - canvas.scrollLeft ) - nodeRect.width,
			( ( canvas.height / 2 ) - canvas.scrollTop ) - nodeRect.height
		);

		return this;

	}

	add( node ) {

		const onRemove = () => {

			node.removeEventListener( 'remove', onRemove );

			node.setEditor( null );

		};

		node.setEditor( this );
		node.addEventListener( 'remove', onRemove );

		this.canvas.add( node );

		this.dispatchEvent( { type: 'add', node } );

		return this;

	}

	get nodes() {

		return this.canvas.nodes;

	}

	set preview( value ) {

		if ( this._preview === value ) return;

		if ( value ) {

			this._wasSplitscreen = this.splitscreen;

			this.splitscreen = false;

			this.menu.dom.remove();
			this.canvas.dom.remove();
			this.search.dom.remove();

			this.domElement.append( this.previewMenu.dom );

		} else {

			this.canvas.focusSelected = false;

			this.domElement.append( this.menu.dom );
			this.domElement.append( this.canvas.dom );
			this.domElement.append( this.search.dom );

			this.previewMenu.dom.remove();

			if ( this._wasSplitscreen == true ) {

				this.splitscreen = true;

			}

		}

		this._preview = value;

	}

	get preview() {

		return this._preview;

	}

	set splitscreen( value ) {

		if ( this._splitscreen === value ) return;

		this.splitview.setSplitview( value );

		this._splitscreen = value;

	}

	get splitscreen() {

		return this._splitscreen;

	}

	newProject() {

		const canvas = this.canvas;
		canvas.clear();
		canvas.scrollLeft = 0;
		canvas.scrollTop = 0;
		canvas.zoom = 1;

		this.dispatchEvent( { type: 'new' } );

	}

	async loadURL( url ) {

		const loader = new Loader( Loader.OBJECTS );
		const json = await loader.load( url, ClassLib );

		this.loadJSON( json );

	}

	loadJSON( json ) {

		const canvas = this.canvas;

		canvas.clear();

		canvas.deserialize( json );

		for ( const node of canvas.nodes ) {

			this.add( node );

		}

		this.dispatchEvent( { type: 'load' } );

	}

	_initSplitview() {

		this.splitview = new SplitscreenManager( this );

	}

	_initUpload() {

		const canvas = this.canvas;

		canvas.onDrop( () => {

			for ( const item of canvas.droppedItems ) {

				const { relativeClientX, relativeClientY } = canvas;

				const file = item.getAsFile();
				const reader = new FileReader();

				reader.onload = () => {

					const fileEditor = new FileEditor( reader.result, file.name );

					fileEditor.setPosition(
						relativeClientX - ( fileEditor.getWidth() / 2 ),
						relativeClientY - 20
					);

					this.add( fileEditor );

				};

				reader.readAsArrayBuffer( file );

			}

		} );

	}

	_initTips() {

		this.tips = new Tips();

		this.domElement.append( this.tips.dom );

	}

	_initMenu() {

		const menu = new CircleMenu();
		const previewMenu = new CircleMenu();

		menu.setAlign( 'top left' );
		previewMenu.setAlign( 'top left' );

		const previewButton = new ButtonInput().setIcon( 'ti ti-brand-threejs' ).setToolTip( 'Preview' );
		const splitscreenButton = new ButtonInput().setIcon( 'ti ti-layout-sidebar-right-expand' ).setToolTip( 'Splitscreen' );
		const menuButton = new ButtonInput().setIcon( 'ti ti-apps' ).setToolTip( 'Add' );
		const examplesButton = new ButtonInput().setIcon( 'ti ti-file-symlink' ).setToolTip( 'Examples' );
		const newButton = new ButtonInput().setIcon( 'ti ti-file' ).setToolTip( 'New' );
		const openButton = new ButtonInput().setIcon( 'ti ti-upload' ).setToolTip( 'Open' );
		const saveButton = new ButtonInput().setIcon( 'ti ti-download' ).setToolTip( 'Save' );

		const editorButton = new ButtonInput().setIcon( 'ti ti-subtask' ).setToolTip( 'Editor' );

		previewButton.onClick( () => this.preview = true );
		editorButton.onClick( () => this.preview = false );

		splitscreenButton.onClick( () => {

			this.splitscreen = ! this.splitscreen;
			splitscreenButton.setIcon( this.splitscreen ? 'ti ti-layout-sidebar-right-collapse' : 'ti ti-layout-sidebar-right-expand' );

		} );

		menuButton.onClick( () => this.nodesContext.open() );
		examplesButton.onClick( () => this.examplesContext.open() );

		newButton.onClick( () => {

			if ( confirm( 'Are you sure?' ) === true ) {

				this.newProject();

			}

		} );

		openButton.onClick( () => {

			const input = document.createElement( 'input' );
			input.type = 'file';

			input.onchange = e => {

				const file = e.target.files[ 0 ];

				const reader = new FileReader();
				reader.readAsText( file, 'UTF-8' );

				reader.onload = readerEvent => {

					const loader = new Loader( Loader.OBJECTS );
					const json = loader.parse( JSON.parse( readerEvent.target.result ), ClassLib );

					this.loadJSON( json );

				};

			};

			input.click();

		} );

		saveButton.onClick( () => {

			exportJSON( this.canvas.toJSON(), 'node_editor' );

		} );

		menu.add( previewButton )
			.add( splitscreenButton )
			.add( newButton )
			.add( examplesButton )
			.add( openButton )
			.add( saveButton )
			.add( menuButton );

		previewMenu.add( editorButton );

		this.domElement.appendChild( menu.dom );

		this.menu = menu;
		this.previewMenu = previewMenu;

	}

	_initExamplesContext() {

		const context = new ContextMenu();

		//**************//
		// MAIN
		//**************//

		const onClickExample = async ( button ) => {

			this.examplesContext.hide();

			const filename = button.getExtra();

			this.loadURL( `./examples/${filename}.json` );

		};

		const addExamples = ( category, names ) => {

			const subContext = new ContextMenu();

			for ( const name of names ) {

				const filename = name.replaceAll( ' ', '-' ).toLowerCase();

				subContext.add( new ButtonInput( name )
					.setIcon( 'ti ti-file-symlink' )
					.onClick( onClickExample )
					.setExtra( category.toLowerCase() + '/' + filename )
				);

			}

			context.add( new ButtonInput( category ), subContext );

			return subContext;

		};

		//**************//
		// EXAMPLES
		//**************//

		addExamples( 'Basic', [
			'Teapot',
			'Matcap',
			'Fresnel',
			'Particles'
		] );

		this.examplesContext = context;

	}

	_initShortcuts() {

		document.addEventListener( 'keydown', ( e ) => {

			if ( e.target === document.body ) {

				const key = e.key;

				if ( key === 'Tab' ) {

					this.search.inputDOM.focus();

					e.preventDefault();
					e.stopImmediatePropagation();

				} else if ( key === ' ' ) {

					this.preview = ! this.preview;

				} else if ( key === 'Delete' ) {

					if ( this.canvas.selected ) this.canvas.selected.dispose();

				} else if ( key === 'Escape' ) {

					this.canvas.select( null );

				}

			}

		} );

	}

	_initParams() {

		const urlParams = new URLSearchParams( window.location.search );

		const example = urlParams.get( 'example' ) || 'basic/teapot';

		this.loadURL( `./examples/${example}.json` );

	}

	addClass( nodeData ) {

		this.removeClass( nodeData );

		this.nodeClasses.push( nodeData );

		ClassLib[ nodeData.name ] = nodeData.nodeClass;

		return this;

	}

	removeClass( nodeData ) {

		const index = this.nodeClasses.indexOf( nodeData );

		if ( index !== - 1 ) {

			this.nodeClasses.splice( index, 1 );

			delete ClassLib[ nodeData.name ];

		}

		return this;

	}

	_initSearch() {

		const traverseNodeEditors = ( item ) => {

			if ( item.children ) {

				for ( const subItem of item.children ) {

					traverseNodeEditors( subItem );

				}

			} else {

				const button = new ButtonInput( item.name );
				button.setIcon( `ti ti-${item.icon}` );
				button.addEventListener( 'complete', async () => {

					const nodeClass = await getNodeEditorClass( item );

					const node = new nodeClass();

					this.add( node );

					this.centralizeNode( node );
					this.canvas.select( node );

				} );

				search.add( button );

				if ( item.tags !== undefined ) {

					search.setTag( button, item.tags );

				}

			}



		};

		const search = new Search();
		search.forceAutoComplete = true;

		search.onFilter( async () => {

			search.clear();

			const nodeList = await getNodeList();

			for ( const item of nodeList.nodes ) {

				traverseNodeEditors( item );

			}

			for ( const item of this.nodeClasses ) {

				traverseNodeEditors( item );

			}

		} );

		search.onSubmit( () => {

			if ( search.currentFiltered !== null ) {

				search.currentFiltered.button.dispatchEvent( new Event( 'complete' ) );

			}

		} );

		this.search = search;

		this.domElement.append( search.dom );

	}

	async _initNodesContext() {

		const context = new ContextMenu( this.canvas.canvas ).setWidth( 300 );

		let isContext = false;
		const contextPosition = {};

		const add = ( node ) => {

			context.hide();

			this.add( node );

			if ( isContext ) {

				node.setPosition(
					Math.round( contextPosition.x ),
					Math.round( contextPosition.y )
				);

			} else {

				this.centralizeNode( node );

			}

			this.canvas.select( node );

			isContext = false;

		};

		context.onContext( () => {

			isContext = true;

			const { relativeClientX, relativeClientY } = this.canvas;

			contextPosition.x = Math.round( relativeClientX );
			contextPosition.y = Math.round( relativeClientY );

		} );

		context.addEventListener( 'show', () => {

			reset();
			focus();

		} );

		//**************//
		// INPUTS
		//**************//

		const nodeButtons = [];

		let nodeButtonsVisible = [];
		let nodeButtonsIndex = - 1;

		const focus = () => requestAnimationFrame( () => search.inputDOM.focus() );
		const reset = () => {

			search.setValue( '', false );

			for ( const button of nodeButtons ) {

				button.setOpened( false ).setVisible( true ).setSelected( false );

			}

		};

		const node = new Node();
		context.add( node );

		const search = new StringInput().setPlaceHolder( 'Search...' ).setIcon( 'ti ti-list-search' );

		search.inputDOM.addEventListener( 'keydown', e => {

			const key = e.key;

			if ( key === 'ArrowDown' ) {

				const previous = nodeButtonsVisible[ nodeButtonsIndex ];
				if ( previous ) previous.setSelected( false );

				const current = nodeButtonsVisible[ nodeButtonsIndex = ( nodeButtonsIndex + 1 ) % nodeButtonsVisible.length ];
				if ( current ) current.setSelected( true );

				e.preventDefault();
				e.stopImmediatePropagation();

			} else if ( key === 'ArrowUp' ) {

				const previous = nodeButtonsVisible[ nodeButtonsIndex ];
				if ( previous ) previous.setSelected( false );

				const current = nodeButtonsVisible[ nodeButtonsIndex > 0 ? -- nodeButtonsIndex : ( nodeButtonsIndex = nodeButtonsVisible.length - 1 ) ];
				if ( current ) current.setSelected( true );

				e.preventDefault();
				e.stopImmediatePropagation();

			} else if ( key === 'Enter' ) {

				if ( nodeButtonsVisible[ nodeButtonsIndex ] !== undefined ) {

					nodeButtonsVisible[ nodeButtonsIndex ].dom.click();

				} else {

					context.hide();

				}

				e.preventDefault();
				e.stopImmediatePropagation();

			} else if ( key === 'Escape' ) {

				context.hide();

			}

		} );

		search.onChange( () => {

			const value = search.getValue().toLowerCase();

			if ( value.length === 0 ) return reset();

			nodeButtonsVisible = [];
			nodeButtonsIndex = 0;

			for ( const button of nodeButtons ) {

				const buttonLabel = button.getLabel().toLowerCase();

				button.setVisible( false ).setSelected( false );

				const visible = buttonLabel.indexOf( value ) !== - 1;

				if ( visible && button.children.length === 0 ) {

					nodeButtonsVisible.push( button );

				}

			}

			for ( const button of nodeButtonsVisible ) {

				let parent = button;

				while ( parent !== null ) {

					parent.setOpened( true ).setVisible( true );

					parent = parent.parent;

				}

			}

			if ( nodeButtonsVisible[ nodeButtonsIndex ] !== undefined ) {

				nodeButtonsVisible[ nodeButtonsIndex ].setSelected( true );

			}

		} );

		const treeView = new TreeViewInput();
		node.add( new Element().setHeight( 30 ).add( search ) );
		node.add( new Element().setHeight( 200 ).add( treeView ) );

		const addNodeEditorElement = ( nodeData ) => {

			const button = new TreeViewNode( nodeData.name );
			button.setIcon( `ti ti-${nodeData.icon}` );

			if ( nodeData.children === undefined ) {

				button.isNodeClass = true;
				button.onClick( async () => {

					const nodeClass = await getNodeEditorClass( nodeData );

					add( new nodeClass() );

				} );

			}

			if ( nodeData.tip ) {

				//button.setToolTip( item.tip );

			}

			nodeButtons.push( button );

			if ( nodeData.children ) {

				for ( const subItem of nodeData.children ) {

					const subButton = addNodeEditorElement( subItem );

					button.add( subButton );

				}

			}

			return button;

		};

		//

		const nodeList = await getNodeList();

		for ( const node of nodeList.nodes ) {

			const button = addNodeEditorElement( node );

			treeView.add( button );

		}

		this.nodesContext = context;

	}

}
```
</details>

#### Methods

##### `setSize(width: any, height: any): this`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this.canvas.setSize( width, height );

		return this;

	}
```
</details>

##### `centralizeNode(node: any): this`

<details><summary>Code</summary>

```ts
centralizeNode( node ) {

		const canvas = this.canvas;
		const nodeRect = node.dom.getBoundingClientRect();

		node.setPosition(
			( ( canvas.width / 2 ) - canvas.scrollLeft ) - nodeRect.width,
			( ( canvas.height / 2 ) - canvas.scrollTop ) - nodeRect.height
		);

		return this;

	}
```
</details>

##### `add(node: any): this`

<details><summary>Code</summary>

```ts
add( node ) {

		const onRemove = () => {

			node.removeEventListener( 'remove', onRemove );

			node.setEditor( null );

		};

		node.setEditor( this );
		node.addEventListener( 'remove', onRemove );

		this.canvas.add( node );

		this.dispatchEvent( { type: 'add', node } );

		return this;

	}
```
</details>

##### `newProject(): void`

<details><summary>Code</summary>

```ts
newProject() {

		const canvas = this.canvas;
		canvas.clear();
		canvas.scrollLeft = 0;
		canvas.scrollTop = 0;
		canvas.zoom = 1;

		this.dispatchEvent( { type: 'new' } );

	}
```
</details>

##### `loadURL(url: any): Promise<void>`

<details><summary>Code</summary>

```ts
async loadURL( url ) {

		const loader = new Loader( Loader.OBJECTS );
		const json = await loader.load( url, ClassLib );

		this.loadJSON( json );

	}
```
</details>

##### `loadJSON(json: any): void`

<details><summary>Code</summary>

```ts
loadJSON( json ) {

		const canvas = this.canvas;

		canvas.clear();

		canvas.deserialize( json );

		for ( const node of canvas.nodes ) {

			this.add( node );

		}

		this.dispatchEvent( { type: 'load' } );

	}
```
</details>

##### `_initSplitview(): void`

<details><summary>Code</summary>

```ts
_initSplitview() {

		this.splitview = new SplitscreenManager( this );

	}
```
</details>

##### `_initUpload(): void`

<details><summary>Code</summary>

```ts
_initUpload() {

		const canvas = this.canvas;

		canvas.onDrop( () => {

			for ( const item of canvas.droppedItems ) {

				const { relativeClientX, relativeClientY } = canvas;

				const file = item.getAsFile();
				const reader = new FileReader();

				reader.onload = () => {

					const fileEditor = new FileEditor( reader.result, file.name );

					fileEditor.setPosition(
						relativeClientX - ( fileEditor.getWidth() / 2 ),
						relativeClientY - 20
					);

					this.add( fileEditor );

				};

				reader.readAsArrayBuffer( file );

			}

		} );

	}
```
</details>

##### `_initTips(): void`

<details><summary>Code</summary>

```ts
_initTips() {

		this.tips = new Tips();

		this.domElement.append( this.tips.dom );

	}
```
</details>

##### `_initMenu(): void`

<details><summary>Code</summary>

```ts
_initMenu() {

		const menu = new CircleMenu();
		const previewMenu = new CircleMenu();

		menu.setAlign( 'top left' );
		previewMenu.setAlign( 'top left' );

		const previewButton = new ButtonInput().setIcon( 'ti ti-brand-threejs' ).setToolTip( 'Preview' );
		const splitscreenButton = new ButtonInput().setIcon( 'ti ti-layout-sidebar-right-expand' ).setToolTip( 'Splitscreen' );
		const menuButton = new ButtonInput().setIcon( 'ti ti-apps' ).setToolTip( 'Add' );
		const examplesButton = new ButtonInput().setIcon( 'ti ti-file-symlink' ).setToolTip( 'Examples' );
		const newButton = new ButtonInput().setIcon( 'ti ti-file' ).setToolTip( 'New' );
		const openButton = new ButtonInput().setIcon( 'ti ti-upload' ).setToolTip( 'Open' );
		const saveButton = new ButtonInput().setIcon( 'ti ti-download' ).setToolTip( 'Save' );

		const editorButton = new ButtonInput().setIcon( 'ti ti-subtask' ).setToolTip( 'Editor' );

		previewButton.onClick( () => this.preview = true );
		editorButton.onClick( () => this.preview = false );

		splitscreenButton.onClick( () => {

			this.splitscreen = ! this.splitscreen;
			splitscreenButton.setIcon( this.splitscreen ? 'ti ti-layout-sidebar-right-collapse' : 'ti ti-layout-sidebar-right-expand' );

		} );

		menuButton.onClick( () => this.nodesContext.open() );
		examplesButton.onClick( () => this.examplesContext.open() );

		newButton.onClick( () => {

			if ( confirm( 'Are you sure?' ) === true ) {

				this.newProject();

			}

		} );

		openButton.onClick( () => {

			const input = document.createElement( 'input' );
			input.type = 'file';

			input.onchange = e => {

				const file = e.target.files[ 0 ];

				const reader = new FileReader();
				reader.readAsText( file, 'UTF-8' );

				reader.onload = readerEvent => {

					const loader = new Loader( Loader.OBJECTS );
					const json = loader.parse( JSON.parse( readerEvent.target.result ), ClassLib );

					this.loadJSON( json );

				};

			};

			input.click();

		} );

		saveButton.onClick( () => {

			exportJSON( this.canvas.toJSON(), 'node_editor' );

		} );

		menu.add( previewButton )
			.add( splitscreenButton )
			.add( newButton )
			.add( examplesButton )
			.add( openButton )
			.add( saveButton )
			.add( menuButton );

		previewMenu.add( editorButton );

		this.domElement.appendChild( menu.dom );

		this.menu = menu;
		this.previewMenu = previewMenu;

	}
```
</details>

##### `_initExamplesContext(): void`

<details><summary>Code</summary>

```ts
_initExamplesContext() {

		const context = new ContextMenu();

		//**************//
		// MAIN
		//**************//

		const onClickExample = async ( button ) => {

			this.examplesContext.hide();

			const filename = button.getExtra();

			this.loadURL( `./examples/${filename}.json` );

		};

		const addExamples = ( category, names ) => {

			const subContext = new ContextMenu();

			for ( const name of names ) {

				const filename = name.replaceAll( ' ', '-' ).toLowerCase();

				subContext.add( new ButtonInput( name )
					.setIcon( 'ti ti-file-symlink' )
					.onClick( onClickExample )
					.setExtra( category.toLowerCase() + '/' + filename )
				);

			}

			context.add( new ButtonInput( category ), subContext );

			return subContext;

		};

		//**************//
		// EXAMPLES
		//**************//

		addExamples( 'Basic', [
			'Teapot',
			'Matcap',
			'Fresnel',
			'Particles'
		] );

		this.examplesContext = context;

	}
```
</details>

##### `_initShortcuts(): void`

<details><summary>Code</summary>

```ts
_initShortcuts() {

		document.addEventListener( 'keydown', ( e ) => {

			if ( e.target === document.body ) {

				const key = e.key;

				if ( key === 'Tab' ) {

					this.search.inputDOM.focus();

					e.preventDefault();
					e.stopImmediatePropagation();

				} else if ( key === ' ' ) {

					this.preview = ! this.preview;

				} else if ( key === 'Delete' ) {

					if ( this.canvas.selected ) this.canvas.selected.dispose();

				} else if ( key === 'Escape' ) {

					this.canvas.select( null );

				}

			}

		} );

	}
```
</details>

##### `_initParams(): void`

<details><summary>Code</summary>

```ts
_initParams() {

		const urlParams = new URLSearchParams( window.location.search );

		const example = urlParams.get( 'example' ) || 'basic/teapot';

		this.loadURL( `./examples/${example}.json` );

	}
```
</details>

##### `addClass(nodeData: any): this`

<details><summary>Code</summary>

```ts
addClass( nodeData ) {

		this.removeClass( nodeData );

		this.nodeClasses.push( nodeData );

		ClassLib[ nodeData.name ] = nodeData.nodeClass;

		return this;

	}
```
</details>

##### `removeClass(nodeData: any): this`

<details><summary>Code</summary>

```ts
removeClass( nodeData ) {

		const index = this.nodeClasses.indexOf( nodeData );

		if ( index !== - 1 ) {

			this.nodeClasses.splice( index, 1 );

			delete ClassLib[ nodeData.name ];

		}

		return this;

	}
```
</details>

##### `_initSearch(): void`

<details><summary>Code</summary>

```ts
_initSearch() {

		const traverseNodeEditors = ( item ) => {

			if ( item.children ) {

				for ( const subItem of item.children ) {

					traverseNodeEditors( subItem );

				}

			} else {

				const button = new ButtonInput( item.name );
				button.setIcon( `ti ti-${item.icon}` );
				button.addEventListener( 'complete', async () => {

					const nodeClass = await getNodeEditorClass( item );

					const node = new nodeClass();

					this.add( node );

					this.centralizeNode( node );
					this.canvas.select( node );

				} );

				search.add( button );

				if ( item.tags !== undefined ) {

					search.setTag( button, item.tags );

				}

			}



		};

		const search = new Search();
		search.forceAutoComplete = true;

		search.onFilter( async () => {

			search.clear();

			const nodeList = await getNodeList();

			for ( const item of nodeList.nodes ) {

				traverseNodeEditors( item );

			}

			for ( const item of this.nodeClasses ) {

				traverseNodeEditors( item );

			}

		} );

		search.onSubmit( () => {

			if ( search.currentFiltered !== null ) {

				search.currentFiltered.button.dispatchEvent( new Event( 'complete' ) );

			}

		} );

		this.search = search;

		this.domElement.append( search.dom );

	}
```
</details>

##### `_initNodesContext(): Promise<void>`

<details><summary>Code</summary>

```ts
async _initNodesContext() {

		const context = new ContextMenu( this.canvas.canvas ).setWidth( 300 );

		let isContext = false;
		const contextPosition = {};

		const add = ( node ) => {

			context.hide();

			this.add( node );

			if ( isContext ) {

				node.setPosition(
					Math.round( contextPosition.x ),
					Math.round( contextPosition.y )
				);

			} else {

				this.centralizeNode( node );

			}

			this.canvas.select( node );

			isContext = false;

		};

		context.onContext( () => {

			isContext = true;

			const { relativeClientX, relativeClientY } = this.canvas;

			contextPosition.x = Math.round( relativeClientX );
			contextPosition.y = Math.round( relativeClientY );

		} );

		context.addEventListener( 'show', () => {

			reset();
			focus();

		} );

		//**************//
		// INPUTS
		//**************//

		const nodeButtons = [];

		let nodeButtonsVisible = [];
		let nodeButtonsIndex = - 1;

		const focus = () => requestAnimationFrame( () => search.inputDOM.focus() );
		const reset = () => {

			search.setValue( '', false );

			for ( const button of nodeButtons ) {

				button.setOpened( false ).setVisible( true ).setSelected( false );

			}

		};

		const node = new Node();
		context.add( node );

		const search = new StringInput().setPlaceHolder( 'Search...' ).setIcon( 'ti ti-list-search' );

		search.inputDOM.addEventListener( 'keydown', e => {

			const key = e.key;

			if ( key === 'ArrowDown' ) {

				const previous = nodeButtonsVisible[ nodeButtonsIndex ];
				if ( previous ) previous.setSelected( false );

				const current = nodeButtonsVisible[ nodeButtonsIndex = ( nodeButtonsIndex + 1 ) % nodeButtonsVisible.length ];
				if ( current ) current.setSelected( true );

				e.preventDefault();
				e.stopImmediatePropagation();

			} else if ( key === 'ArrowUp' ) {

				const previous = nodeButtonsVisible[ nodeButtonsIndex ];
				if ( previous ) previous.setSelected( false );

				const current = nodeButtonsVisible[ nodeButtonsIndex > 0 ? -- nodeButtonsIndex : ( nodeButtonsIndex = nodeButtonsVisible.length - 1 ) ];
				if ( current ) current.setSelected( true );

				e.preventDefault();
				e.stopImmediatePropagation();

			} else if ( key === 'Enter' ) {

				if ( nodeButtonsVisible[ nodeButtonsIndex ] !== undefined ) {

					nodeButtonsVisible[ nodeButtonsIndex ].dom.click();

				} else {

					context.hide();

				}

				e.preventDefault();
				e.stopImmediatePropagation();

			} else if ( key === 'Escape' ) {

				context.hide();

			}

		} );

		search.onChange( () => {

			const value = search.getValue().toLowerCase();

			if ( value.length === 0 ) return reset();

			nodeButtonsVisible = [];
			nodeButtonsIndex = 0;

			for ( const button of nodeButtons ) {

				const buttonLabel = button.getLabel().toLowerCase();

				button.setVisible( false ).setSelected( false );

				const visible = buttonLabel.indexOf( value ) !== - 1;

				if ( visible && button.children.length === 0 ) {

					nodeButtonsVisible.push( button );

				}

			}

			for ( const button of nodeButtonsVisible ) {

				let parent = button;

				while ( parent !== null ) {

					parent.setOpened( true ).setVisible( true );

					parent = parent.parent;

				}

			}

			if ( nodeButtonsVisible[ nodeButtonsIndex ] !== undefined ) {

				nodeButtonsVisible[ nodeButtonsIndex ].setSelected( true );

			}

		} );

		const treeView = new TreeViewInput();
		node.add( new Element().setHeight( 30 ).add( search ) );
		node.add( new Element().setHeight( 200 ).add( treeView ) );

		const addNodeEditorElement = ( nodeData ) => {

			const button = new TreeViewNode( nodeData.name );
			button.setIcon( `ti ti-${nodeData.icon}` );

			if ( nodeData.children === undefined ) {

				button.isNodeClass = true;
				button.onClick( async () => {

					const nodeClass = await getNodeEditorClass( nodeData );

					add( new nodeClass() );

				} );

			}

			if ( nodeData.tip ) {

				//button.setToolTip( item.tip );

			}

			nodeButtons.push( button );

			if ( nodeData.children ) {

				for ( const subItem of nodeData.children ) {

					const subButton = addNodeEditorElement( subItem );

					button.add( subButton );

				}

			}

			return button;

		};

		//

		const nodeList = await getNodeList();

		for ( const node of nodeList.nodes ) {

			const button = addNodeEditorElement( node );

			treeView.add( button );

		}

		this.nodesContext = context;

	}
```
</details>


---