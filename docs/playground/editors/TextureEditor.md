[⬅️ Back to Table of Contents](../../index.md)

# 📄 `TextureEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/TextureEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LabelElement` | `flow` |
| `ToggleInput` | `flow` |
| `SelectInput` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `onValidNode` | `../NodeEditorUtils.js` |
| `onValidType` | `../NodeEditorUtils.js` |
| `texture` | `three/tsl` |
| `uv` | `three/tsl` |
| `Texture` | `three` |
| `TextureLoader` | `three` |
| `RepeatWrapping` | `three` |
| `ClampToEdgeWrapping` | `three` |
| `MirroredRepeatWrapping` | `three` |
| `setInputAestheticsFromType` | `../DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `textureLoader` | `any` | let/var | `new TextureLoader()` | ✗ |
| `defaultTexture` | `any` | let/var | `new Texture()` | ✗ |
| `defaultUV` | `any` | let/var | `null` | ✗ |
| `textureNode` | `any` | let/var | `this.value` | ✗ |
| `node` | `any` | let/var | `this.value` | ✗ |
| `texture` | `any` | let/var | `this.texture` | ✗ |


---

## Functions

### `getTexture(url: any): any`

**Parameters:**

- **`url`** `any`

**Returns:** `any`

**Calls:**

- `textureLoader.load`

<details><summary>Code</summary>

```typescript
( url ) => {

	return textureLoader.load( url );

}
```
</details>

### `TextureEditor._initFile(): void`

**Returns:** `void`

**Calls:**

- `setInputAestheticsFromType (from ../DataTypeLib.js)`
- `fileElement.onValid( onValidType( 'URL' ) ).onConnect`
- `fileElement.getLinkedElement`
- `getTexture`
- `fileEditorElement.node.getURL`
- `this.update`
- `this.add`

<details><summary>Code</summary>

```typescript
_initFile() {

		const fileElement = setInputAestheticsFromType( new LabelElement( 'File' ), 'URL' );

		fileElement.onValid( onValidType( 'URL' ) ).onConnect( () => {

			const textureNode = this.value;
			const fileEditorElement = fileElement.getLinkedElement();

			this.texture = fileEditorElement ? getTexture( fileEditorElement.node.getURL() ) : null;

			textureNode.value = this.texture || defaultTexture;

			this.update();

		}, true );

		this.add( fileElement );

	}
```
</details>

### `TextureEditor._initParams(): void`

**Returns:** `void`

**Calls:**

- `setInputAestheticsFromType (from ../DataTypeLib.js)`
- `uvField.onValid( onValidNode ).onConnect`
- `uvField.getLinkedObject`
- `uv (from three/tsl)`
- `new SelectInput( [
			{ name: 'Repeat Wrapping', value: RepeatWrapping },
			{ name: 'Clamp To Edge Wrapping', value: ClampToEdgeWrapping },
			{ name: 'Mirrored Repeat Wrapping', value: MirroredRepeatWrapping }
		], RepeatWrapping ).onChange`
- `this.update`
- `new ToggleInput( false ).onChange`
- `this.add( uvField )
			.add( new LabelElement( 'Wrap S' ).add( this.wrapSInput ) )
			.add( new LabelElement( 'Wrap T' ).add( this.wrapTInput ) )
			.add`
- `new LabelElement( 'Flip Y' ).add`

<details><summary>Code</summary>

```typescript
_initParams() {

		const uvField = setInputAestheticsFromType( new LabelElement( 'UV' ), 'Vector2' );

		uvField.onValid( onValidNode ).onConnect( () => {

			const node = this.value;

			node.uvNode = uvField.getLinkedObject() || defaultUV || ( defaultUV = uv() );

		} );

		this.wrapSInput = new SelectInput( [
			{ name: 'Repeat Wrapping', value: RepeatWrapping },
			{ name: 'Clamp To Edge Wrapping', value: ClampToEdgeWrapping },
			{ name: 'Mirrored Repeat Wrapping', value: MirroredRepeatWrapping }
		], RepeatWrapping ).onChange( () => {

			this.update();

		} );

		this.wrapTInput = new SelectInput( [
			{ name: 'Repeat Wrapping', value: RepeatWrapping },
			{ name: 'Clamp To Edge Wrapping', value: ClampToEdgeWrapping },
			{ name: 'Mirrored Repeat Wrapping', value: MirroredRepeatWrapping }
		], RepeatWrapping ).onChange( () => {

			this.update();

		} );

		this.flipYInput = new ToggleInput( false ).onChange( () => {

			this.update();

		} );

		this.add( uvField )
			.add( new LabelElement( 'Wrap S' ).add( this.wrapSInput ) )
			.add( new LabelElement( 'Wrap T' ).add( this.wrapTInput ) )
			.add( new LabelElement( 'Flip Y' ).add( this.flipYInput ) );

	}
```
</details>

### `TextureEditor.update(): void`

**Returns:** `void`

**Calls:**

- `Number`
- `this.wrapSInput.getValue`
- `this.wrapTInput.getValue`
- `this.flipYInput.getValue`
- `texture.dispose`
- `this.invalidate`

<details><summary>Code</summary>

```typescript
update() {

		const texture = this.texture;

		if ( texture ) {

			texture.wrapS = Number( this.wrapSInput.getValue() );
			texture.wrapT = Number( this.wrapTInput.getValue() );
			texture.flipY = this.flipYInput.getValue();
			texture.dispose();

			this.invalidate();

		}

	}
```
</details>


---

## Classes

### `TextureEditor`

<details><summary>Class Code</summary>

```ts
export class TextureEditor extends BaseNodeEditor {

	constructor() {

		const node = texture( defaultTexture );

		super( 'Texture', node, 250 );

		this.texture = null;

		this._initFile();
		this._initParams();

		this.onValidElement = () => {};

	}

	_initFile() {

		const fileElement = setInputAestheticsFromType( new LabelElement( 'File' ), 'URL' );

		fileElement.onValid( onValidType( 'URL' ) ).onConnect( () => {

			const textureNode = this.value;
			const fileEditorElement = fileElement.getLinkedElement();

			this.texture = fileEditorElement ? getTexture( fileEditorElement.node.getURL() ) : null;

			textureNode.value = this.texture || defaultTexture;

			this.update();

		}, true );

		this.add( fileElement );

	}

	_initParams() {

		const uvField = setInputAestheticsFromType( new LabelElement( 'UV' ), 'Vector2' );

		uvField.onValid( onValidNode ).onConnect( () => {

			const node = this.value;

			node.uvNode = uvField.getLinkedObject() || defaultUV || ( defaultUV = uv() );

		} );

		this.wrapSInput = new SelectInput( [
			{ name: 'Repeat Wrapping', value: RepeatWrapping },
			{ name: 'Clamp To Edge Wrapping', value: ClampToEdgeWrapping },
			{ name: 'Mirrored Repeat Wrapping', value: MirroredRepeatWrapping }
		], RepeatWrapping ).onChange( () => {

			this.update();

		} );

		this.wrapTInput = new SelectInput( [
			{ name: 'Repeat Wrapping', value: RepeatWrapping },
			{ name: 'Clamp To Edge Wrapping', value: ClampToEdgeWrapping },
			{ name: 'Mirrored Repeat Wrapping', value: MirroredRepeatWrapping }
		], RepeatWrapping ).onChange( () => {

			this.update();

		} );

		this.flipYInput = new ToggleInput( false ).onChange( () => {

			this.update();

		} );

		this.add( uvField )
			.add( new LabelElement( 'Wrap S' ).add( this.wrapSInput ) )
			.add( new LabelElement( 'Wrap T' ).add( this.wrapTInput ) )
			.add( new LabelElement( 'Flip Y' ).add( this.flipYInput ) );

	}

	update() {

		const texture = this.texture;

		if ( texture ) {

			texture.wrapS = Number( this.wrapSInput.getValue() );
			texture.wrapT = Number( this.wrapTInput.getValue() );
			texture.flipY = this.flipYInput.getValue();
			texture.dispose();

			this.invalidate();

		}

	}

}
```
</details>

#### Methods

##### `_initFile(): void`

<details><summary>Code</summary>

```ts
_initFile() {

		const fileElement = setInputAestheticsFromType( new LabelElement( 'File' ), 'URL' );

		fileElement.onValid( onValidType( 'URL' ) ).onConnect( () => {

			const textureNode = this.value;
			const fileEditorElement = fileElement.getLinkedElement();

			this.texture = fileEditorElement ? getTexture( fileEditorElement.node.getURL() ) : null;

			textureNode.value = this.texture || defaultTexture;

			this.update();

		}, true );

		this.add( fileElement );

	}
```
</details>

##### `_initParams(): void`

<details><summary>Code</summary>

```ts
_initParams() {

		const uvField = setInputAestheticsFromType( new LabelElement( 'UV' ), 'Vector2' );

		uvField.onValid( onValidNode ).onConnect( () => {

			const node = this.value;

			node.uvNode = uvField.getLinkedObject() || defaultUV || ( defaultUV = uv() );

		} );

		this.wrapSInput = new SelectInput( [
			{ name: 'Repeat Wrapping', value: RepeatWrapping },
			{ name: 'Clamp To Edge Wrapping', value: ClampToEdgeWrapping },
			{ name: 'Mirrored Repeat Wrapping', value: MirroredRepeatWrapping }
		], RepeatWrapping ).onChange( () => {

			this.update();

		} );

		this.wrapTInput = new SelectInput( [
			{ name: 'Repeat Wrapping', value: RepeatWrapping },
			{ name: 'Clamp To Edge Wrapping', value: ClampToEdgeWrapping },
			{ name: 'Mirrored Repeat Wrapping', value: MirroredRepeatWrapping }
		], RepeatWrapping ).onChange( () => {

			this.update();

		} );

		this.flipYInput = new ToggleInput( false ).onChange( () => {

			this.update();

		} );

		this.add( uvField )
			.add( new LabelElement( 'Wrap S' ).add( this.wrapSInput ) )
			.add( new LabelElement( 'Wrap T' ).add( this.wrapTInput ) )
			.add( new LabelElement( 'Flip Y' ).add( this.flipYInput ) );

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const texture = this.texture;

		if ( texture ) {

			texture.wrapS = Number( this.wrapSInput.getValue() );
			texture.wrapT = Number( this.wrapTInput.getValue() );
			texture.flipY = this.flipYInput.getValue();
			texture.dispose();

			this.invalidate();

		}

	}
```
</details>


---