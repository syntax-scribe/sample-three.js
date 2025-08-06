[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Script.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 28 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Script.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIElement` | `./libs/ui.js` |
| `UIPanel` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `SetScriptValueCommand` | `./commands/SetScriptValueCommand.js` |
| `SetMaterialValueCommand` | `./commands/SetMaterialValueCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `header` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `close` | `UIElement` | let/var | `new UIElement( buttonSVG )` | ✗ |
| `renderer` | `any` | let/var | `*not shown*` | ✗ |
| `delay` | `any` | let/var | `*not shown*` | ✗ |
| `currentMode` | `any` | let/var | `*not shown*` | ✗ |
| `currentScript` | `any` | let/var | `*not shown*` | ✗ |
| `currentObject` | `any` | let/var | `*not shown*` | ✗ |
| `cmd` | `SetMaterialValueCommand` | let/var | `new SetMaterialValueCommand( editor, currentObject, 'defines', json.defines )` | ✗ |
| `cmd` | `SetMaterialValueCommand` | let/var | `new SetMaterialValueCommand( editor, currentObject, 'uniforms', json.uniforms )` | ✗ |
| `cmd` | `SetMaterialValueCommand` | let/var | `new SetMaterialValueCommand( editor, currentObject, 'attributes', json.attrib...` | ✗ |
| `errorLines` | `any[]` | let/var | `[]` | ✗ |
| `widgets` | `any[]` | let/var | `[]` | ✗ |
| `valid` | `any` | let/var | `*not shown*` | ✗ |
| `errors` | `any[]` | let/var | `[]` | ✗ |
| `error` | `any` | let/var | `errors[ i ]` | ✗ |
| `programs` | `any` | let/var | `renderer.info.programs` | ✗ |
| `parseMessage` | `RegExp` | let/var | `/^(?:ERROR\|WARNING): \d+:(\d+): (.*)/g` | ✗ |
| `diagnostics` | `any` | let/var | `programs[ i ].diagnostics` | ✗ |
| `shaderInfo` | `any` | let/var | `diagnostics[ currentScript ]` | ✗ |
| `lineOffset` | `any` | let/var | `shaderInfo.prefix.split( /\r\n\|\r\|\n/ ).length` | ✗ |
| `error` | `any` | let/var | `errors[ i ]` | ✗ |
| `server` | `any` | let/var | `new CodeMirror.TernServer( { caseInsensitive: true, plugins: { threejs: null ...` | ✗ |
| `mode` | `any` | let/var | `*not shown*` | ✗ |
| `source` | `any` | let/var | `*not shown*` | ✗ |
| `json` | `{ defines: any; uniforms: any; attrib...` | let/var | `{ defines: object.material.defines, uniforms: object.material.uniforms, attri...` | ✗ |


---

## Functions

### `Script(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setId`
- `container.setPosition`
- `container.setBackgroundColor`
- `container.setDisplay`
- `header.setPadding`
- `container.add`
- `new UIText().setColor`
- `header.add`
- `complex_call_673`
- `document.createElementNS`
- `svg.setAttribute`
- `path.setAttribute`
- `svg.appendChild`
- `close.setPosition`
- `close.setTop`
- `close.setRight`
- `close.setCursor`
- `close.onClick`
- `signals.rendererCreated.add`
- `CodeMirror`
- `codemirror.setOption`
- `codemirror.on`
- `clearTimeout`
- `setTimeout`
- `codemirror.getValue`
- `validate`
- `editor.execute`
- `JSON.parse`
- `JSON.stringify`
- `codemirror.getWrapperElement`
- `wrapper.addEventListener`
- `event.stopPropagation`
- `codemirror.operation`
- `codemirror.removeLineClass`
- `errorLines.shift`
- `codemirror.removeLineWidget`
- `widgets.shift`
- `esprima.parse`
- `errors.push`
- `error.message.replace`
- `message.split`
- `jsonlint.parse`
- `signals.materialChanged.dispatch`
- `shaderInfo.prefix.split`
- `parseMessage.exec`
- `document.createElement`
- `Math.max`
- `errorLines.push`
- `codemirror.addLineClass`
- `codemirror.addLineWidget`
- `widgets.push`
- `server.complete`
- `server.showType`
- `server.showDocs`
- `server.jumpToDef`
- `server.jumpBack`
- `server.rename`
- `server.selectName`
- `server.updateArgHints`
- `/[\w\.]/.exec`
- `signals.editorCleared.add`
- `title.setValue`
- `strings.getKey`
- `signals.editScript.add`
- `setTitle`
- `codemirror.setValue`
- `codemirror.clearHistory`
- `signals.scriptRemoved.add`
- `signals.objectChanged.add`
- `[ 'programInfo', 'vertexShader', 'fragmentShader' ].includes`
- `signals.scriptChanged.add`
- `signals.materialChanged.add`

**Internal Comments:**
```
// prevent backspace from deleting objects (x2)
// validate (x2)
// (x6)
// tern js autocomplete (x2)
// TODO: Adds multi-material support (x3)
```

<details><summary>Code</summary>

```typescript
function Script( editor ) {

	const signals = editor.signals;
	const strings = editor.strings;

	const container = new UIPanel();
	container.setId( 'script' );
	container.setPosition( 'absolute' );
	container.setBackgroundColor( '#272822' );
	container.setDisplay( 'none' );

	const header = new UIPanel();
	header.setPadding( '10px' );
	container.add( header );

	const title = new UIText().setColor( '#fff' );
	header.add( title );

	const buttonSVG = ( function () {

		const svg = document.createElementNS( 'http://www.w3.org/2000/svg', 'svg' );
		svg.setAttribute( 'width', 32 );
		svg.setAttribute( 'height', 32 );
		const path = document.createElementNS( 'http://www.w3.org/2000/svg', 'path' );
		path.setAttribute( 'd', 'M 12,12 L 22,22 M 22,12 12,22' );
		path.setAttribute( 'stroke', '#fff' );
		svg.appendChild( path );
		return svg;

	} )();

	const close = new UIElement( buttonSVG );
	close.setPosition( 'absolute' );
	close.setTop( '3px' );
	close.setRight( '1px' );
	close.setCursor( 'pointer' );
	close.onClick( function () {

		container.setDisplay( 'none' );

	} );
	header.add( close );


	let renderer;

	signals.rendererCreated.add( function ( newRenderer ) {

		renderer = newRenderer;

	} );


	let delay;
	let currentMode;
	let currentScript;
	let currentObject;

	const codemirror = CodeMirror( container.dom, {
		value: '',
		lineNumbers: true,
		matchBrackets: true,
		indentWithTabs: true,
		tabSize: 4,
		indentUnit: 4,
		hintOptions: {
			completeSingle: false
		}
	} );
	codemirror.setOption( 'theme', 'monokai' );
	codemirror.on( 'change', function () {

		if ( codemirror.state.focused === false ) return;

		clearTimeout( delay );
		delay = setTimeout( function () {

			const value = codemirror.getValue();

			if ( ! validate( value ) ) return;

			if ( typeof ( currentScript ) === 'object' ) {

				if ( value !== currentScript.source ) {

					editor.execute( new SetScriptValueCommand( editor, currentObject, currentScript, 'source', value ) );

				}

				return;

			}

			if ( currentScript !== 'programInfo' ) return;

			const json = JSON.parse( value );

			if ( JSON.stringify( currentObject.material.defines ) !== JSON.stringify( json.defines ) ) {

				const cmd = new SetMaterialValueCommand( editor, currentObject, 'defines', json.defines );
				cmd.updatable = false;
				editor.execute( cmd );

			}

			if ( JSON.stringify( currentObject.material.uniforms ) !== JSON.stringify( json.uniforms ) ) {

				const cmd = new SetMaterialValueCommand( editor, currentObject, 'uniforms', json.uniforms );
				cmd.updatable = false;
				editor.execute( cmd );

			}

			if ( JSON.stringify( currentObject.material.attributes ) !== JSON.stringify( json.attributes ) ) {

				const cmd = new SetMaterialValueCommand( editor, currentObject, 'attributes', json.attributes );
				cmd.updatable = false;
				editor.execute( cmd );

			}

		}, 300 );

	} );

	// prevent backspace from deleting objects
	const wrapper = codemirror.getWrapperElement();
	wrapper.addEventListener( 'keydown', function ( event ) {

		event.stopPropagation();

	} );

	// validate

	const errorLines = [];
	const widgets = [];

	const validate = function ( string ) {

		let valid;
		let errors = [];

		return codemirror.operation( function () {

			while ( errorLines.length > 0 ) {

				codemirror.removeLineClass( errorLines.shift(), 'background', 'errorLine' );

			}

			while ( widgets.length > 0 ) {

				codemirror.removeLineWidget( widgets.shift() );

			}

			//

			switch ( currentMode ) {

				case 'javascript':

					try {

						const syntax = esprima.parse( string, { tolerant: true } );
						errors = syntax.errors;

					} catch ( error ) {

						errors.push( {

							lineNumber: error.lineNumber - 1,
							message: error.message

						} );

					}

					for ( let i = 0; i < errors.length; i ++ ) {

						const error = errors[ i ];
						error.message = error.message.replace( /Line [0-9]+: /, '' );

					}

					break;

				case 'json':

					errors = [];

					jsonlint.parseError = function ( message, info ) {

						message = message.split( '\n' )[ 3 ];

						errors.push( {

							lineNumber: info.loc.first_line - 1,
							message: message

						} );

					};

					try {

						jsonlint.parse( string );

					} catch ( error ) {

						// ignore failed error recovery

					}

					break;

				case 'glsl':

					currentObject.material[ currentScript ] = string;
					currentObject.material.needsUpdate = true;
					signals.materialChanged.dispatch( currentObject, 0 ); // TODO: Add multi-material support

					const programs = renderer.info.programs;

					valid = true;
					const parseMessage = /^(?:ERROR|WARNING): \d+:(\d+): (.*)/g;

					for ( let i = 0, n = programs.length; i !== n; ++ i ) {

						const diagnostics = programs[ i ].diagnostics;

						if ( diagnostics === undefined ||
								diagnostics.material !== currentObject.material ) continue;

						if ( ! diagnostics.runnable ) valid = false;

						const shaderInfo = diagnostics[ currentScript ];
						const lineOffset = shaderInfo.prefix.split( /\r\n|\r|\n/ ).length;

						while ( true ) {

							const parseResult = parseMessage.exec( shaderInfo.log );
							if ( parseResult === null ) break;

							errors.push( {

								lineNumber: parseResult[ 1 ] - lineOffset,
								message: parseResult[ 2 ]

							} );

						} // messages

						break;

					} // programs

			} // mode switch

			for ( let i = 0; i < errors.length; i ++ ) {

				const error = errors[ i ];

				const message = document.createElement( 'div' );
				message.className = 'esprima-error';
				message.textContent = error.message;

				const lineNumber = Math.max( error.lineNumber, 0 );
				errorLines.push( lineNumber );

				codemirror.addLineClass( lineNumber, 'background', 'errorLine' );

				const widget = codemirror.addLineWidget( lineNumber, message );

				widgets.push( widget );

			}

			return valid !== undefined ? valid : errors.length === 0;

		} );

	};

	// tern js autocomplete

	const server = new CodeMirror.TernServer( {
		caseInsensitive: true,
		plugins: { threejs: null }
	} );

	codemirror.setOption( 'extraKeys', {
		'Ctrl-Space': function ( cm ) {

			server.complete( cm );

		},
		'Ctrl-I': function ( cm ) {

			server.showType( cm );

		},
		'Ctrl-O': function ( cm ) {

			server.showDocs( cm );

		},
		'Alt-.': function ( cm ) {

			server.jumpToDef( cm );

		},
		'Alt-,': function ( cm ) {

			server.jumpBack( cm );

		},
		'Ctrl-Q': function ( cm ) {

			server.rename( cm );

		},
		'Ctrl-.': function ( cm ) {

			server.selectName( cm );

		}
	} );

	codemirror.on( 'cursorActivity', function ( cm ) {

		if ( currentMode !== 'javascript' ) return;
		server.updateArgHints( cm );

	} );

	codemirror.on( 'keypress', function ( cm, kb ) {

		if ( currentMode !== 'javascript' ) return;
		if ( /[\w\.]/.exec( kb.key ) ) {

			server.complete( cm );

		}

	} );


	//

	signals.editorCleared.add( function () {

		container.setDisplay( 'none' );

	} );

	function setTitle( object, script ) {

		if ( typeof script === 'object' ) {

			title.setValue( object.name + ' / ' + script.name );

		} else {

			switch ( script ) {

				case 'vertexShader':

					title.setValue( object.material.name + ' / ' + strings.getKey( 'script/title/vertexShader' ) );
					break;

				case 'fragmentShader':

					title.setValue( object.material.name + ' / ' + strings.getKey( 'script/title/fragmentShader' ) );
					break;

				case 'programInfo':

					title.setValue( object.material.name + ' / ' + strings.getKey( 'script/title/programInfo' ) );
					break;

				default:

					throw new Error( 'setTitle: Unknown script' );

			}

		}

	}

	signals.editScript.add( function ( object, script ) {

		let mode, source;

		if ( typeof ( script ) === 'object' ) {

			mode = 'javascript';
			source = script.source;

		} else {

			switch ( script ) {

				case 'vertexShader':

					mode = 'glsl';
					source = object.material.vertexShader || '';

					break;

				case 'fragmentShader':

					mode = 'glsl';
					source = object.material.fragmentShader || '';

					break;

				case 'programInfo':

					mode = 'json';
					const json = {
						defines: object.material.defines,
						uniforms: object.material.uniforms,
						attributes: object.material.attributes
					};
					source = JSON.stringify( json, null, '\t' );

					break;

				default:

					throw new Error( 'editScript: Unknown script' );

			}

		}

		setTitle( object, script );

		currentMode = mode;
		currentScript = script;
		currentObject = object;

		container.setDisplay( '' );
		codemirror.setValue( source );
		codemirror.clearHistory();
		if ( mode === 'json' ) mode = { name: 'javascript', json: true };
		codemirror.setOption( 'mode', mode );

	} );

	signals.scriptRemoved.add( function ( script ) {

		if ( currentScript === script ) {

			container.setDisplay( 'none' );

		}

	} );

	signals.objectChanged.add( function ( object ) {

		if ( object !== currentObject ) return;

		if ( [ 'programInfo', 'vertexShader', 'fragmentShader' ].includes( currentScript ) ) return;

		setTitle( currentObject, currentScript );

	} );

	signals.scriptChanged.add( function ( script ) {

		if ( script === currentScript ) {

			setTitle( currentObject, currentScript );

		}

	} );

	signals.materialChanged.add( function ( object, slot ) {

		if ( object !== currentObject ) return;

		// TODO: Adds multi-material support

		setTitle( currentObject, currentScript );

	} );

	return container;

}
```
</details>

### `validate(string: any): any`

**Parameters:**

- **`string`** `any`

**Returns:** `any`

**Calls:**

- `codemirror.operation`
- `codemirror.removeLineClass`
- `errorLines.shift`
- `codemirror.removeLineWidget`
- `widgets.shift`
- `esprima.parse`
- `errors.push`
- `error.message.replace`
- `message.split`
- `jsonlint.parse`
- `signals.materialChanged.dispatch`
- `shaderInfo.prefix.split`
- `parseMessage.exec`
- `document.createElement`
- `Math.max`
- `errorLines.push`
- `codemirror.addLineClass`
- `codemirror.addLineWidget`
- `widgets.push`

**Internal Comments:**
```
//
```

<details><summary>Code</summary>

```typescript
function ( string ) {

		let valid;
		let errors = [];

		return codemirror.operation( function () {

			while ( errorLines.length > 0 ) {

				codemirror.removeLineClass( errorLines.shift(), 'background', 'errorLine' );

			}

			while ( widgets.length > 0 ) {

				codemirror.removeLineWidget( widgets.shift() );

			}

			//

			switch ( currentMode ) {

				case 'javascript':

					try {

						const syntax = esprima.parse( string, { tolerant: true } );
						errors = syntax.errors;

					} catch ( error ) {

						errors.push( {

							lineNumber: error.lineNumber - 1,
							message: error.message

						} );

					}

					for ( let i = 0; i < errors.length; i ++ ) {

						const error = errors[ i ];
						error.message = error.message.replace( /Line [0-9]+: /, '' );

					}

					break;

				case 'json':

					errors = [];

					jsonlint.parseError = function ( message, info ) {

						message = message.split( '\n' )[ 3 ];

						errors.push( {

							lineNumber: info.loc.first_line - 1,
							message: message

						} );

					};

					try {

						jsonlint.parse( string );

					} catch ( error ) {

						// ignore failed error recovery

					}

					break;

				case 'glsl':

					currentObject.material[ currentScript ] = string;
					currentObject.material.needsUpdate = true;
					signals.materialChanged.dispatch( currentObject, 0 ); // TODO: Add multi-material support

					const programs = renderer.info.programs;

					valid = true;
					const parseMessage = /^(?:ERROR|WARNING): \d+:(\d+): (.*)/g;

					for ( let i = 0, n = programs.length; i !== n; ++ i ) {

						const diagnostics = programs[ i ].diagnostics;

						if ( diagnostics === undefined ||
								diagnostics.material !== currentObject.material ) continue;

						if ( ! diagnostics.runnable ) valid = false;

						const shaderInfo = diagnostics[ currentScript ];
						const lineOffset = shaderInfo.prefix.split( /\r\n|\r|\n/ ).length;

						while ( true ) {

							const parseResult = parseMessage.exec( shaderInfo.log );
							if ( parseResult === null ) break;

							errors.push( {

								lineNumber: parseResult[ 1 ] - lineOffset,
								message: parseResult[ 2 ]

							} );

						} // messages

						break;

					} // programs

			} // mode switch

			for ( let i = 0; i < errors.length; i ++ ) {

				const error = errors[ i ];

				const message = document.createElement( 'div' );
				message.className = 'esprima-error';
				message.textContent = error.message;

				const lineNumber = Math.max( error.lineNumber, 0 );
				errorLines.push( lineNumber );

				codemirror.addLineClass( lineNumber, 'background', 'errorLine' );

				const widget = codemirror.addLineWidget( lineNumber, message );

				widgets.push( widget );

			}

			return valid !== undefined ? valid : errors.length === 0;

		} );

	}
```
</details>

### `setTitle(object: any, script: any): void`

**Parameters:**

- **`object`** `any`
- **`script`** `any`

**Returns:** `void`

**Calls:**

- `title.setValue`
- `strings.getKey`

<details><summary>Code</summary>

```typescript
function setTitle( object, script ) {

		if ( typeof script === 'object' ) {

			title.setValue( object.name + ' / ' + script.name );

		} else {

			switch ( script ) {

				case 'vertexShader':

					title.setValue( object.material.name + ' / ' + strings.getKey( 'script/title/vertexShader' ) );
					break;

				case 'fragmentShader':

					title.setValue( object.material.name + ' / ' + strings.getKey( 'script/title/fragmentShader' ) );
					break;

				case 'programInfo':

					title.setValue( object.material.name + ' / ' + strings.getKey( 'script/title/programInfo' ) );
					break;

				default:

					throw new Error( 'setTitle: Unknown script' );

			}

		}

	}
```
</details>


---