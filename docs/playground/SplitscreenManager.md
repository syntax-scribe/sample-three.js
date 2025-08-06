[⬅️ Back to Table of Contents](../index.md)

# 📄 `SplitscreenManager.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/SplitscreenManager.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `nodeDOM` | `any` | let/var | `this.editor.domElement` | ✗ |
| `rendererContainer` | `any` | let/var | `this.renderer.domElement.parentNode` | ✗ |
| `offset` | `number` | let/var | `this.gutterOffset` | ✗ |


---

## Functions

### `SplitscreenManager.setSplitview(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `this.addGutter`
- `this.removeGutter`

<details><summary>Code</summary>

```typescript
setSplitview( value ) {

		const nodeDOM = this.editor.domElement;
		const rendererContainer = this.renderer.domElement.parentNode;

		if ( value ) {

			this.addGutter( rendererContainer, nodeDOM );

		} else {

			this.removeGutter( rendererContainer, nodeDOM );

		}

	}
```
</details>

### `SplitscreenManager.addGutter(rendererContainer: any, nodeDOM: any): void`

**Parameters:**

- **`rendererContainer`** `any`
- **`nodeDOM`** `any`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `nodeDOM.parentNode.appendChild`
- `this.gutter.addEventListener`
- `document.addEventListener`
- `Math.max`
- `Math.min`
- `onGutterMovement`

<details><summary>Code</summary>

```typescript
addGutter( rendererContainer, nodeDOM ) {

		rendererContainer.style[ 'z-index' ] = 20;

		this.gutter = document.createElement( 'f-gutter' );

		nodeDOM.parentNode.appendChild( this.gutter );

		const onGutterMovement = () => {

			const offset = this.gutterOffset;

			this.gutter.style[ 'left' ] = 100 * offset + '%';
			rendererContainer.style[ 'left' ] = 100 * offset + '%';
			rendererContainer.style[ 'width' ] = 100 * ( 1 - offset ) + '%';
			nodeDOM.style[ 'width' ] = 100 * offset + '%';

		};

		this.gutter.addEventListener( 'mousedown', () => {

			this.gutterMoving = true;

		} );

		document.addEventListener( 'mousemove', ( event ) => {

			if ( this.gutter && this.gutterMoving ) {

				this.gutterOffset = Math.max( 0, Math.min( 1, event.clientX / window.innerWidth ) );
				onGutterMovement();

			}

		} );

		document.addEventListener( 'mouseup', () => {

			this.gutterMoving = false;

		} );

		onGutterMovement();

	}
```
</details>

### `SplitscreenManager.removeGutter(rendererContainer: any, nodeDOM: any): void`

**Parameters:**

- **`rendererContainer`** `any`
- **`nodeDOM`** `any`

**Returns:** `void`

**Calls:**

- `this.gutter.remove`

<details><summary>Code</summary>

```typescript
removeGutter( rendererContainer, nodeDOM ) {

		rendererContainer.style[ 'z-index' ] = 0;

		this.gutter.remove();
		this.gutter = null;

		rendererContainer.style[ 'left' ] = '0%';
		rendererContainer.style[ 'width' ] = '100%';
		nodeDOM.style[ 'width' ] = '100%';

	}
```
</details>

### `onGutterMovement(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {

			const offset = this.gutterOffset;

			this.gutter.style[ 'left' ] = 100 * offset + '%';
			rendererContainer.style[ 'left' ] = 100 * offset + '%';
			rendererContainer.style[ 'width' ] = 100 * ( 1 - offset ) + '%';
			nodeDOM.style[ 'width' ] = 100 * offset + '%';

		}
```
</details>


---

## Classes

### `SplitscreenManager`

<details><summary>Class Code</summary>

```ts
export class SplitscreenManager {

	constructor( editor ) {

		this.editor = editor;
		this.renderer = editor.renderer;
		this.composer = editor.composer;

		this.gutter = null;
		this.gutterMoving = false;
		this.gutterOffset = 0.6;

	}

	setSplitview( value ) {

		const nodeDOM = this.editor.domElement;
		const rendererContainer = this.renderer.domElement.parentNode;

		if ( value ) {

			this.addGutter( rendererContainer, nodeDOM );

		} else {

			this.removeGutter( rendererContainer, nodeDOM );

		}

	}

	addGutter( rendererContainer, nodeDOM ) {

		rendererContainer.style[ 'z-index' ] = 20;

		this.gutter = document.createElement( 'f-gutter' );

		nodeDOM.parentNode.appendChild( this.gutter );

		const onGutterMovement = () => {

			const offset = this.gutterOffset;

			this.gutter.style[ 'left' ] = 100 * offset + '%';
			rendererContainer.style[ 'left' ] = 100 * offset + '%';
			rendererContainer.style[ 'width' ] = 100 * ( 1 - offset ) + '%';
			nodeDOM.style[ 'width' ] = 100 * offset + '%';

		};

		this.gutter.addEventListener( 'mousedown', () => {

			this.gutterMoving = true;

		} );

		document.addEventListener( 'mousemove', ( event ) => {

			if ( this.gutter && this.gutterMoving ) {

				this.gutterOffset = Math.max( 0, Math.min( 1, event.clientX / window.innerWidth ) );
				onGutterMovement();

			}

		} );

		document.addEventListener( 'mouseup', () => {

			this.gutterMoving = false;

		} );

		onGutterMovement();

	}

	removeGutter( rendererContainer, nodeDOM ) {

		rendererContainer.style[ 'z-index' ] = 0;

		this.gutter.remove();
		this.gutter = null;

		rendererContainer.style[ 'left' ] = '0%';
		rendererContainer.style[ 'width' ] = '100%';
		nodeDOM.style[ 'width' ] = '100%';

	}

}
```
</details>

#### Methods

##### `setSplitview(value: any): void`

<details><summary>Code</summary>

```ts
setSplitview( value ) {

		const nodeDOM = this.editor.domElement;
		const rendererContainer = this.renderer.domElement.parentNode;

		if ( value ) {

			this.addGutter( rendererContainer, nodeDOM );

		} else {

			this.removeGutter( rendererContainer, nodeDOM );

		}

	}
```
</details>

##### `addGutter(rendererContainer: any, nodeDOM: any): void`

<details><summary>Code</summary>

```ts
addGutter( rendererContainer, nodeDOM ) {

		rendererContainer.style[ 'z-index' ] = 20;

		this.gutter = document.createElement( 'f-gutter' );

		nodeDOM.parentNode.appendChild( this.gutter );

		const onGutterMovement = () => {

			const offset = this.gutterOffset;

			this.gutter.style[ 'left' ] = 100 * offset + '%';
			rendererContainer.style[ 'left' ] = 100 * offset + '%';
			rendererContainer.style[ 'width' ] = 100 * ( 1 - offset ) + '%';
			nodeDOM.style[ 'width' ] = 100 * offset + '%';

		};

		this.gutter.addEventListener( 'mousedown', () => {

			this.gutterMoving = true;

		} );

		document.addEventListener( 'mousemove', ( event ) => {

			if ( this.gutter && this.gutterMoving ) {

				this.gutterOffset = Math.max( 0, Math.min( 1, event.clientX / window.innerWidth ) );
				onGutterMovement();

			}

		} );

		document.addEventListener( 'mouseup', () => {

			this.gutterMoving = false;

		} );

		onGutterMovement();

	}
```
</details>

##### `removeGutter(rendererContainer: any, nodeDOM: any): void`

<details><summary>Code</summary>

```ts
removeGutter( rendererContainer, nodeDOM ) {

		rendererContainer.style[ 'z-index' ] = 0;

		this.gutter.remove();
		this.gutter = null;

		rendererContainer.style[ 'left' ] = '0%';
		rendererContainer.style[ 'width' ] = '100%';
		nodeDOM.style[ 'width' ] = '100%';

	}
```
</details>


---