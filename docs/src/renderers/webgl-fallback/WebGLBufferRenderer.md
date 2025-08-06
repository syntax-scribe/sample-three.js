[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLBufferRenderer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl-fallback/WebGLBufferRenderer.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `elementCount` | `number` | let/var | `0` | ✗ |
| `elementCount` | `number` | let/var | `0` | ✗ |


---

## Functions

### `WebGLBufferRenderer.render(start: any, count: any): void`

**Parameters:**

- **`start`** `any`
- **`count`** `any`

**Returns:** `void`

**Calls:**

- `gl.drawElements`
- `gl.drawArrays`
- `info.update`

<details><summary>Code</summary>

```typescript
render( start, count ) {

		const { gl, mode, object, type, info, index } = this;

		if ( index !== 0 ) {

			gl.drawElements( mode, count, type, start );

		} else {

			gl.drawArrays( mode, start, count );

		}

		info.update( object, count, 1 );

	}
```
</details>

### `WebGLBufferRenderer.renderInstances(start: any, count: any, primcount: any): void`

**Parameters:**

- **`start`** `any`
- **`count`** `any`
- **`primcount`** `any`

**Returns:** `void`

**Calls:**

- `gl.drawElementsInstanced`
- `gl.drawArraysInstanced`
- `info.update`

<details><summary>Code</summary>

```typescript
renderInstances( start, count, primcount ) {

		const { gl, mode, type, index, object, info } = this;

		if ( primcount === 0 ) return;

		if ( index !== 0 ) {

			gl.drawElementsInstanced( mode, count, type, start, primcount );

		} else {

			gl.drawArraysInstanced( mode, start, count, primcount );

		}

		info.update( object, count, primcount );

	}
```
</details>

### `WebGLBufferRenderer.renderMultiDraw(starts: any, counts: any, drawCount: any): void`

**Parameters:**

- **`starts`** `any`
- **`counts`** `any`
- **`drawCount`** `any`

**Returns:** `void`

**Calls:**

- `extensions.get`
- `this.render`
- `extension.multiDrawElementsWEBGL`
- `extension.multiDrawArraysWEBGL`
- `info.update`

<details><summary>Code</summary>

```typescript
renderMultiDraw( starts, counts, drawCount ) {

		const { extensions, mode, object, info } = this;

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );

		if ( extension === null ) {

			for ( let i = 0; i < drawCount; i ++ ) {

				this.render( starts[ i ], counts[ i ] );

			}

		} else {

			if ( this.index !== 0 ) {

				extension.multiDrawElementsWEBGL( mode, counts, 0, this.type, starts, 0, drawCount );

			} else {

				extension.multiDrawArraysWEBGL( mode, starts, 0, counts, 0, drawCount );

			}

			let elementCount = 0;
			for ( let i = 0; i < drawCount; i ++ ) {

				elementCount += counts[ i ];

			}

			info.update( object, elementCount, 1 );

		}

	}
```
</details>

### `WebGLBufferRenderer.renderMultiDrawInstances(starts: any, counts: any, drawCount: any, primcount: any): void`

**Parameters:**

- **`starts`** `any`
- **`counts`** `any`
- **`drawCount`** `any`
- **`primcount`** `any`

**Returns:** `void`

**Calls:**

- `extensions.get`
- `this.renderInstances`
- `extension.multiDrawElementsInstancedWEBGL`
- `extension.multiDrawArraysInstancedWEBGL`
- `info.update`

<details><summary>Code</summary>

```typescript
renderMultiDrawInstances( starts, counts, drawCount, primcount ) {

		const { extensions, mode, object, info } = this;

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );

		if ( extension === null ) {

			for ( let i = 0; i < drawCount; i ++ ) {

				this.renderInstances( starts[ i ], counts[ i ], primcount[ i ] );

			}

		} else {

			if ( this.index !== 0 ) {

				extension.multiDrawElementsInstancedWEBGL( mode, counts, 0, this.type, starts, 0, primcount, 0, drawCount );

			} else {

				extension.multiDrawArraysInstancedWEBGL( mode, starts, 0, counts, 0, primcount, 0, drawCount );

			}

			let elementCount = 0;
			for ( let i = 0; i < drawCount; i ++ ) {

				elementCount += counts[ i ] * primcount[ i ];

			}

			info.update( object, elementCount, 1 );

		}

	}
```
</details>


---

## Classes

### `WebGLBufferRenderer`

<details><summary>Class Code</summary>

```ts
class WebGLBufferRenderer {

	constructor( backend ) {

		this.gl = backend.gl;
		this.extensions = backend.extensions;
		this.info = backend.renderer.info;
		this.mode = null;
		this.index = 0;
		this.type = null;
		this.object = null;

	}

	render( start, count ) {

		const { gl, mode, object, type, info, index } = this;

		if ( index !== 0 ) {

			gl.drawElements( mode, count, type, start );

		} else {

			gl.drawArrays( mode, start, count );

		}

		info.update( object, count, 1 );

	}

	renderInstances( start, count, primcount ) {

		const { gl, mode, type, index, object, info } = this;

		if ( primcount === 0 ) return;

		if ( index !== 0 ) {

			gl.drawElementsInstanced( mode, count, type, start, primcount );

		} else {

			gl.drawArraysInstanced( mode, start, count, primcount );

		}

		info.update( object, count, primcount );

	}

	renderMultiDraw( starts, counts, drawCount ) {

		const { extensions, mode, object, info } = this;

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );

		if ( extension === null ) {

			for ( let i = 0; i < drawCount; i ++ ) {

				this.render( starts[ i ], counts[ i ] );

			}

		} else {

			if ( this.index !== 0 ) {

				extension.multiDrawElementsWEBGL( mode, counts, 0, this.type, starts, 0, drawCount );

			} else {

				extension.multiDrawArraysWEBGL( mode, starts, 0, counts, 0, drawCount );

			}

			let elementCount = 0;
			for ( let i = 0; i < drawCount; i ++ ) {

				elementCount += counts[ i ];

			}

			info.update( object, elementCount, 1 );

		}

	}

	renderMultiDrawInstances( starts, counts, drawCount, primcount ) {

		const { extensions, mode, object, info } = this;

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );

		if ( extension === null ) {

			for ( let i = 0; i < drawCount; i ++ ) {

				this.renderInstances( starts[ i ], counts[ i ], primcount[ i ] );

			}

		} else {

			if ( this.index !== 0 ) {

				extension.multiDrawElementsInstancedWEBGL( mode, counts, 0, this.type, starts, 0, primcount, 0, drawCount );

			} else {

				extension.multiDrawArraysInstancedWEBGL( mode, starts, 0, counts, 0, primcount, 0, drawCount );

			}

			let elementCount = 0;
			for ( let i = 0; i < drawCount; i ++ ) {

				elementCount += counts[ i ] * primcount[ i ];

			}

			info.update( object, elementCount, 1 );

		}

	}

	//

}
```
</details>

#### Methods

##### `render(start: any, count: any): void`

<details><summary>Code</summary>

```ts
render( start, count ) {

		const { gl, mode, object, type, info, index } = this;

		if ( index !== 0 ) {

			gl.drawElements( mode, count, type, start );

		} else {

			gl.drawArrays( mode, start, count );

		}

		info.update( object, count, 1 );

	}
```
</details>

##### `renderInstances(start: any, count: any, primcount: any): void`

<details><summary>Code</summary>

```ts
renderInstances( start, count, primcount ) {

		const { gl, mode, type, index, object, info } = this;

		if ( primcount === 0 ) return;

		if ( index !== 0 ) {

			gl.drawElementsInstanced( mode, count, type, start, primcount );

		} else {

			gl.drawArraysInstanced( mode, start, count, primcount );

		}

		info.update( object, count, primcount );

	}
```
</details>

##### `renderMultiDraw(starts: any, counts: any, drawCount: any): void`

<details><summary>Code</summary>

```ts
renderMultiDraw( starts, counts, drawCount ) {

		const { extensions, mode, object, info } = this;

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );

		if ( extension === null ) {

			for ( let i = 0; i < drawCount; i ++ ) {

				this.render( starts[ i ], counts[ i ] );

			}

		} else {

			if ( this.index !== 0 ) {

				extension.multiDrawElementsWEBGL( mode, counts, 0, this.type, starts, 0, drawCount );

			} else {

				extension.multiDrawArraysWEBGL( mode, starts, 0, counts, 0, drawCount );

			}

			let elementCount = 0;
			for ( let i = 0; i < drawCount; i ++ ) {

				elementCount += counts[ i ];

			}

			info.update( object, elementCount, 1 );

		}

	}
```
</details>

##### `renderMultiDrawInstances(starts: any, counts: any, drawCount: any, primcount: any): void`

<details><summary>Code</summary>

```ts
renderMultiDrawInstances( starts, counts, drawCount, primcount ) {

		const { extensions, mode, object, info } = this;

		if ( drawCount === 0 ) return;

		const extension = extensions.get( 'WEBGL_multi_draw' );

		if ( extension === null ) {

			for ( let i = 0; i < drawCount; i ++ ) {

				this.renderInstances( starts[ i ], counts[ i ], primcount[ i ] );

			}

		} else {

			if ( this.index !== 0 ) {

				extension.multiDrawElementsInstancedWEBGL( mode, counts, 0, this.type, starts, 0, primcount, 0, drawCount );

			} else {

				extension.multiDrawArraysInstancedWEBGL( mode, starts, 0, counts, 0, primcount, 0, drawCount );

			}

			let elementCount = 0;
			for ( let i = 0; i < drawCount; i ++ ) {

				elementCount += counts[ i ] * primcount[ i ];

			}

			info.update( object, elementCount, 1 );

		}

	}
```
</details>


---