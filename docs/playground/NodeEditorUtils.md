[⬅️ Back to Table of Contents](../index.md)

# 📄 `NodeEditorUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 17 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`playground/NodeEditorUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `StringInput` | `flow` |
| `NumberInput` | `flow` |
| `ColorInput` | `flow` |
| `Element` | `flow` |
| `LabelElement` | `flow` |
| `string` | `three/tsl` |
| `float` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `vec4` | `three/tsl` |
| `color` | `three/tsl` |
| `Color` | `three` |
| `setInputAestheticsFromType` | `./DataTypeLib.js` |
| `setOutputAestheticsFromType` | `./DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `file` | `Blob` | let/var | `new Blob( [ json ], { type: 'text/plain' } )` | ✗ |
| `value` | `any` | let/var | `material[ key ]` | ✗ |
| `createInputLib` | `{ string: (node: any, element: any, s...` | let/var | `{ // gpu string: createStringInput, float: createFloatInput, vec2: createVect...` | ✓ |
| `inputNodeLib` | `{ string: any; float: any; vec2: any;...` | let/var | `{ // gpu string, float, vec2, vec3, vec4, color, // cpu Number: float, String...` | ✓ |
| `id` | `any` | let/var | `json.id \|\| json.name` | ✗ |
| `element` | `any` | let/var | `json.name ? new LabelElement( json.name ) : new Element()` | ✗ |
| `field` | `boolean` | let/var | `nullable !== true && json.field !== false` | ✗ |
| `inputNode` | `any` | let/var | `null` | ✗ |
| `object` | `any` | let/var | `targetObject` | ✗ |
| `isValid` | `boolean` | let/var | `false` | ✗ |


---

## Functions

### `exportJSON(object: any, name: any): void`

**Parameters:**

- **`object`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `JSON.stringify`
- `document.createElement`
- `URL.createObjectURL`
- `a.click`

<details><summary>Code</summary>

```typescript
export function exportJSON( object, name ) {

	const json = JSON.stringify( object );

	const a = document.createElement( 'a' );
	const file = new Blob( [ json ], { type: 'text/plain' } );

	a.href = URL.createObjectURL( file );
	a.download = name + '.json';
	a.click();

}
```
</details>

### `disposeScene(scene: any): void`

**Parameters:**

- **`scene`** `any`

**Returns:** `void`

**Calls:**

- `scene.traverse`
- `object.geometry.dispose`
- `disposeMaterial`

<details><summary>Code</summary>

```typescript
export function disposeScene( scene ) {

	scene.traverse( object => {

		if ( ! object.isMesh ) return;

		object.geometry.dispose();

		if ( object.material.isMaterial ) {

			disposeMaterial( object.material );

		} else {

			for ( const material of object.material ) {

				disposeMaterial( material );

			}

		}

	} );

}
```
</details>

### `resetScene(scene: any): void`

**Parameters:**

- **`scene`** `any`

**Returns:** `void`

**Calls:**

- `scene.environment.dispose`
- `scene.background.dispose`

<details><summary>Code</summary>

```typescript
export function resetScene( scene ) {

	if ( scene.environment !== null ) {

		scene.environment.dispose();
		scene.environment = null;

	}

	if ( scene.background !== null ) {

		if ( scene.background.isTexture ) scene.background.dispose();

	}

	scene.background = new Color( 0x333333 );

}
```
</details>

### `disposeMaterial(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `material.dispose`
- `Object.keys`
- `value.dispose`

<details><summary>Code</summary>

```typescript
export function disposeMaterial( material )	{

	material.dispose();

	for ( const key of Object.keys( material ) ) {

		const value = material[ key ];

		if ( value && typeof value === 'object' && typeof value.dispose === 'function' ) {

			value.dispose();

		}

	}

}
```
</details>

### `createColorInput(node: any, element: any): void`

**Parameters:**

- **`node`** `any`
- **`element`** `any`

**Returns:** `void`

**Calls:**

- `new ColorInput().onChange`
- `node.value.setHex`
- `input.getValue`
- `element.dispatchEvent`
- `element.add`

<details><summary>Code</summary>

```typescript
( node, element ) => {

	const input = new ColorInput().onChange( () => {

		node.value.setHex( input.getValue() );

		element.dispatchEvent( new Event( 'changeInput' ) );

	} );

	element.add( input );

}
```
</details>

### `createFloatInput(node: any, element: any): void`

**Parameters:**

- **`node`** `any`
- **`element`** `any`

**Returns:** `void`

**Calls:**

- `new NumberInput().onChange`
- `input.getValue`
- `element.dispatchEvent`
- `element.add`

<details><summary>Code</summary>

```typescript
( node, element ) => {

	const input = new NumberInput().onChange( () => {

		node.value = input.getValue();

		element.dispatchEvent( new Event( 'changeInput' ) );

	} );

	element.add( input );

}
```
</details>

### `createStringInput(node: any, element: any, settings: {}): void`

**Parameters:**

- **`node`** `any`
- **`element`** `any`
- **`settings`** `{}`

**Returns:** `void`

**Calls:**

- `new StringInput().onChange`
- `input.getValue`
- `value.toLowerCase`
- `value.toUpperCase`
- `element.dispatchEvent`
- `element.add`
- `input.addOption`
- `input.getInput`
- `field.addEventListener`
- `field.value.replace`

<details><summary>Code</summary>

```typescript
( node, element, settings = {} ) => {

	const input = new StringInput().onChange( () => {

		let value = input.getValue();

		if ( settings.transform === 'lowercase' ) value = value.toLowerCase();
		else if ( settings.transform === 'uppercase' ) value = value.toUpperCase();

		node.value = value;

		element.dispatchEvent( new Event( 'changeInput' ) );

	} );

	element.add( input );

	if ( settings.options ) {

		for ( const option of settings.options ) {

			input.addOption( option );

		}

	}

	const field = input.getInput();

	if ( settings.allows ) field.addEventListener( 'input', () => field.value = field.value.replace( new RegExp( '[^\\s' + settings.allows + ']', 'gi' ), '' ) );
	if ( settings.maxLength ) field.maxLength = settings.maxLength;
	if ( settings.transform ) field.style[ 'text-transform' ] = settings.transform;

}
```
</details>

### `createVector2Input(node: any, element: any): void`

**Parameters:**

- **`node`** `any`
- **`element`** `any`

**Returns:** `void`

**Calls:**

- `fieldX.getValue`
- `fieldY.getValue`
- `element.dispatchEvent`
- `new NumberInput().setTagColor( 'red' ).onChange`
- `new NumberInput().setTagColor( 'green' ).onChange`
- `element.add( fieldX ).add`

<details><summary>Code</summary>

```typescript
( node, element ) => {

	const onUpdate = () => {

		node.value.x = fieldX.getValue();
		node.value.y = fieldY.getValue();

		element.dispatchEvent( new Event( 'changeInput' ) );

	};

	const fieldX = new NumberInput().setTagColor( 'red' ).onChange( onUpdate );
	const fieldY = new NumberInput().setTagColor( 'green' ).onChange( onUpdate );

	element.add( fieldX ).add( fieldY );

}
```
</details>

### `onUpdate(): void`

**Returns:** `void`

**Calls:**

- `fieldX.getValue`
- `fieldY.getValue`
- `element.dispatchEvent`

<details><summary>Code</summary>

```typescript
() => {

		node.value.x = fieldX.getValue();
		node.value.y = fieldY.getValue();

		element.dispatchEvent( new Event( 'changeInput' ) );

	}
```
</details>

### `createVector3Input(node: any, element: any): void`

**Parameters:**

- **`node`** `any`
- **`element`** `any`

**Returns:** `void`

**Calls:**

- `fieldX.getValue`
- `fieldY.getValue`
- `fieldZ.getValue`
- `element.dispatchEvent`
- `new NumberInput().setTagColor( 'red' ).onChange`
- `new NumberInput().setTagColor( 'green' ).onChange`
- `new NumberInput().setTagColor( 'blue' ).onChange`
- `element.add( fieldX ).add( fieldY ).add`

<details><summary>Code</summary>

```typescript
( node, element ) => {

	const onUpdate = () => {

		node.value.x = fieldX.getValue();
		node.value.y = fieldY.getValue();
		node.value.z = fieldZ.getValue();

		element.dispatchEvent( new Event( 'changeInput' ) );

	};

	const fieldX = new NumberInput().setTagColor( 'red' ).onChange( onUpdate );
	const fieldY = new NumberInput().setTagColor( 'green' ).onChange( onUpdate );
	const fieldZ = new NumberInput().setTagColor( 'blue' ).onChange( onUpdate );

	element.add( fieldX ).add( fieldY ).add( fieldZ );

}
```
</details>

### `onUpdate(): void`

**Returns:** `void`

**Calls:**

- `fieldX.getValue`
- `fieldY.getValue`
- `fieldZ.getValue`
- `element.dispatchEvent`

<details><summary>Code</summary>

```typescript
() => {

		node.value.x = fieldX.getValue();
		node.value.y = fieldY.getValue();
		node.value.z = fieldZ.getValue();

		element.dispatchEvent( new Event( 'changeInput' ) );

	}
```
</details>

### `createVector4Input(node: any, element: any): void`

**Parameters:**

- **`node`** `any`
- **`element`** `any`

**Returns:** `void`

**Calls:**

- `fieldX.getValue`
- `fieldY.getValue`
- `fieldZ.getValue`
- `element.dispatchEvent`
- `new NumberInput().setTagColor( 'red' ).onChange`
- `new NumberInput().setTagColor( 'green' ).onChange`
- `new NumberInput().setTagColor( 'blue' ).onChange`
- `new NumberInput( 1 ).setTagColor( 'white' ).onChange`
- `element.add( fieldX ).add( fieldY ).add( fieldZ ).add`

<details><summary>Code</summary>

```typescript
( node, element ) => {

	const onUpdate = () => {

		node.value.x = fieldX.getValue();
		node.value.y = fieldY.getValue();
		node.value.z = fieldZ.getValue();
		node.value.w = fieldZ.getValue();

		element.dispatchEvent( new Event( 'changeInput' ) );

	};

	const fieldX = new NumberInput().setTagColor( 'red' ).onChange( onUpdate );
	const fieldY = new NumberInput().setTagColor( 'green' ).onChange( onUpdate );
	const fieldZ = new NumberInput().setTagColor( 'blue' ).onChange( onUpdate );
	const fieldW = new NumberInput( 1 ).setTagColor( 'white' ).onChange( onUpdate );

	element.add( fieldX ).add( fieldY ).add( fieldZ ).add( fieldW );

}
```
</details>

### `onUpdate(): void`

**Returns:** `void`

**Calls:**

- `fieldX.getValue`
- `fieldY.getValue`
- `fieldZ.getValue`
- `element.dispatchEvent`

<details><summary>Code</summary>

```typescript
() => {

		node.value.x = fieldX.getValue();
		node.value.y = fieldY.getValue();
		node.value.z = fieldZ.getValue();
		node.value.w = fieldZ.getValue();

		element.dispatchEvent( new Event( 'changeInput' ) );

	}
```
</details>

### `createElementFromJSON(json: any): { id: any; element: any; inputNode: any; inputType: any; outputType: any; }`

**Parameters:**

- **`json`** `any`

**Returns:** `{ id: any; element: any; inputNode: any; inputType: any; outputType: any; }`

**Calls:**

- `complex_call_5400`
- `element.setHeight`
- `complex_call_5596`
- `element.onConnect`
- `element.getLinkedObject`
- `element.setEnabledInputs`
- `setInputAestheticsFromType (from ./DataTypeLib.js)`
- `element.onValid`
- `onValidType`
- `setOutputAestheticsFromType (from ./DataTypeLib.js)`

**Internal Comments:**
```
// (x4)
//element.setInputStyle( 'dotted' ); // 'border-style: dotted;' (x4)
```

<details><summary>Code</summary>

```typescript
export function createElementFromJSON( json ) {

	const { inputType, outputType, nullable } = json;

	const id = json.id || json.name;
	const element = json.name ? new LabelElement( json.name ) : new Element();
	const field = nullable !== true && json.field !== false;

	//

	let inputNode = null;

	if ( nullable !== true && inputNodeLib[ inputType ] !== undefined ) {

		inputNode = inputNodeLib[ inputType ]();

	}

	element.value = inputNode;

	//

	if ( json.height ) element.setHeight( json.height );

	if ( inputType ) {

		if ( field && createInputLib[ inputType ] ) {

			createInputLib[ inputType ]( inputNode, element, json );

		}

		element.onConnect( () => {

			const externalNode = element.getLinkedObject();

			element.setEnabledInputs( externalNode === null );

			element.value = externalNode || inputNode;

		} );

	}

	//

	if ( inputType && json.inputConnection !== false ) {

		setInputAestheticsFromType( element, inputType );
		//element.setInputStyle( 'dotted' ); // 'border-style: dotted;'

		element.onValid( onValidType( inputType ) );

	}

	if ( outputType ) {

		setOutputAestheticsFromType( element, outputType );
		//element.setInputStyle( 'dotted' ); // 'border-style: dotted;'

	}

	return { id, element, inputNode, inputType, outputType };

}
```
</details>

### `isGPUNode(object: any): boolean`

**Parameters:**

- **`object`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
export function isGPUNode( object ) {

	return object && object.isNode === true && object.isCodeNode !== true && object.nodeType !== 'string' && object.nodeType !== 'ArrayBuffer';

}
```
</details>

### `isValidTypeToType(sourceType: any, targetType: any): boolean`

**Parameters:**

- **`sourceType`** `any`
- **`targetType`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
export function isValidTypeToType( sourceType, targetType ) {

	if ( sourceType === targetType ) return true;

	return false;

}
```
</details>

### `onValidType(types: string, node: any): (source: any, target: any, stage: any) => boolean`

**Parameters:**

- **`types`** `string`
- **`node`** `any`

**Returns:** `(source: any, target: any, stage: any) => boolean`

**Calls:**

- `target.getObject`
- `types.split`
- `isValidTypeToType`
- `isGPUNode`
- `target.node.getName`
- `node.editor.tips.error`

<details><summary>Code</summary>

```typescript
export function onValidType( types = 'node', node = null ) {

	return ( source, target, stage ) => {

		const targetObject = target.getObject();

		if ( targetObject ) {

			for ( const type of types.split( '|' ) ) {

				let object = targetObject;

				if ( object.isScriptableValueNode ) {

					if ( object.outputType ) {

						if ( isValidTypeToType( object.outputType, type ) ) {

							return true;

						}

					}

					object = object.value;

				}

				if ( object === null || object === undefined ) continue;

				let isValid = false;

				if ( type === 'any' ) {

					isValid = true;

				} else if ( type === 'node' ) {

					isValid = isGPUNode( object );

				} else if ( type === 'string' || type === 'String' ) {

					isValid = object.nodeType === 'string';

				} else if ( type === 'Number' ) {

					isValid = object.isInputNode && typeof object.value === 'number';

				} else if ( type === 'URL' ) {

					isValid = object.nodeType === 'string' || object.nodeType === 'ArrayBuffer';

				} else if ( object[ 'is' + type ] === true ) {

					isValid = true;

				}

				if ( isValid ) return true;

			}

			if ( node !== null && stage === 'dragged' ) {

				const name = target.node.getName();

				node.editor.tips.error( `"${name}" is not a "${types}".` );

			}

			return false;

		}

	};

}
```
</details>


---