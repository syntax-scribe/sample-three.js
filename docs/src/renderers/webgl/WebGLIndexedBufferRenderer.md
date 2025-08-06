[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLIndexedBufferRenderer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLIndexedBufferRenderer.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `mode` | `any` | let/var | `*not shown*` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `bytesPerElement` | `any` | let/var | `*not shown*` | ✗ |
| `elementCount` | `number` | let/var | `0` | ✗ |
| `elementCount` | `number` | let/var | `0` | ✗ |


---

## Functions

### `WebGLIndexedBufferRenderer(gl: any, extensions: any, info: any): void`

**Parameters:**

- **`gl`** `any`
- **`extensions`** `any`
- **`info`** `any`

**Returns:** `void`

**Calls:**

- `gl.drawElements`
- `info.update`
- `gl.drawElementsInstanced`
- `extensions.get`
- `extension.multiDrawElementsWEBGL`
- `renderInstances`
- `extension.multiDrawElementsInstancedWEBGL`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
function WebGLIndexedBufferRenderer( gl, extensions, info ) {

	let mode;

	function setMode( value ) {

		mode = value;

	}

	let type, bytesPerElement;

	function setIndex( value ) {

		type = value.type;
		bytesPerElement = value.bytesPerElement;

	}

	function render( start, count ) {

		gl.drawElements( mode, count, type, start * bytesPerElement );

		info.update( count, mode, 1 );

	}

	function renderInstances( start, count, primcount ) {

		if ( primcount === 0 ) return;

		gl.drawElementsInstanced( mode, count, type, start * bytesPerElement, primcount );

		info.update( count, mode, primcount );

	}

	function renderMultiDraw( starts, counts, drawCount ) {

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );
		extension.multiDrawElementsWEBGL( mode, counts, 0, type, starts, 0, drawCount );

		let elementCount = 0;
		for ( let i = 0; i < drawCount; i ++ ) {

			elementCount += counts[ i ];

		}

		info.update( elementCount, mode, 1 );


	}

	function renderMultiDrawInstances( starts, counts, drawCount, primcount ) {

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );

		if ( extension === null ) {

			for ( let i = 0; i < starts.length; i ++ ) {

				renderInstances( starts[ i ] / bytesPerElement, counts[ i ], primcount[ i ] );

			}

		} else {

			extension.multiDrawElementsInstancedWEBGL( mode, counts, 0, type, starts, 0, primcount, 0, drawCount );

			let elementCount = 0;
			for ( let i = 0; i < drawCount; i ++ ) {

				elementCount += counts[ i ] * primcount[ i ];

			}

			info.update( elementCount, mode, 1 );

		}

	}

	//

	this.setMode = setMode;
	this.setIndex = setIndex;
	this.render = render;
	this.renderInstances = renderInstances;
	this.renderMultiDraw = renderMultiDraw;
	this.renderMultiDrawInstances = renderMultiDrawInstances;

}
```
</details>

### `setMode(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setMode( value ) {

		mode = value;

	}
```
</details>

### `setIndex(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setIndex( value ) {

		type = value.type;
		bytesPerElement = value.bytesPerElement;

	}
```
</details>

### `render(start: any, count: any): void`

**Parameters:**

- **`start`** `any`
- **`count`** `any`

**Returns:** `void`

**Calls:**

- `gl.drawElements`
- `info.update`

<details><summary>Code</summary>

```typescript
function render( start, count ) {

		gl.drawElements( mode, count, type, start * bytesPerElement );

		info.update( count, mode, 1 );

	}
```
</details>

### `renderInstances(start: any, count: any, primcount: any): void`

**Parameters:**

- **`start`** `any`
- **`count`** `any`
- **`primcount`** `any`

**Returns:** `void`

**Calls:**

- `gl.drawElementsInstanced`
- `info.update`

<details><summary>Code</summary>

```typescript
function renderInstances( start, count, primcount ) {

		if ( primcount === 0 ) return;

		gl.drawElementsInstanced( mode, count, type, start * bytesPerElement, primcount );

		info.update( count, mode, primcount );

	}
```
</details>

### `renderMultiDraw(starts: any, counts: any, drawCount: any): void`

**Parameters:**

- **`starts`** `any`
- **`counts`** `any`
- **`drawCount`** `any`

**Returns:** `void`

**Calls:**

- `extensions.get`
- `extension.multiDrawElementsWEBGL`
- `info.update`

<details><summary>Code</summary>

```typescript
function renderMultiDraw( starts, counts, drawCount ) {

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );
		extension.multiDrawElementsWEBGL( mode, counts, 0, type, starts, 0, drawCount );

		let elementCount = 0;
		for ( let i = 0; i < drawCount; i ++ ) {

			elementCount += counts[ i ];

		}

		info.update( elementCount, mode, 1 );


	}
```
</details>

### `renderMultiDrawInstances(starts: any, counts: any, drawCount: any, primcount: any): void`

**Parameters:**

- **`starts`** `any`
- **`counts`** `any`
- **`drawCount`** `any`
- **`primcount`** `any`

**Returns:** `void`

**Calls:**

- `extensions.get`
- `renderInstances`
- `extension.multiDrawElementsInstancedWEBGL`
- `info.update`

<details><summary>Code</summary>

```typescript
function renderMultiDrawInstances( starts, counts, drawCount, primcount ) {

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );

		if ( extension === null ) {

			for ( let i = 0; i < starts.length; i ++ ) {

				renderInstances( starts[ i ] / bytesPerElement, counts[ i ], primcount[ i ] );

			}

		} else {

			extension.multiDrawElementsInstancedWEBGL( mode, counts, 0, type, starts, 0, primcount, 0, drawCount );

			let elementCount = 0;
			for ( let i = 0; i < drawCount; i ++ ) {

				elementCount += counts[ i ] * primcount[ i ];

			}

			info.update( elementCount, mode, 1 );

		}

	}
```
</details>


---