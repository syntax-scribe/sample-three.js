[⬅️ Back to Table of Contents](../../index.md)

# 📄 `canvas-wrapper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/canvas-wrapper.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `d` | `DOMMatrix` | let/var | `new window.DOMMatrix()` | ✗ |
| `stack` | `any[]` | let/var | `[]` | ✗ |
| `m` | `DOMMatrix` | let/var | `new DOMMatrix()` | ✗ |
| `d` | `any` | let/var | `ctx.currentTransform` | ✗ |


---

## Functions

### `duplicate(src: any): DOMMatrix`

**Parameters:**

- **`src`** `any`

**Returns:** `DOMMatrix`

<details><summary>Code</summary>

```typescript
function duplicate( src ) {

		const d = new window.DOMMatrix();
		d.a = src.a;
		d.b = src.b;
		d.c = src.c;
		d.d = src.d;
		d.e = src.e;
		d.f = src.f;
		return d;

	}
```
</details>

### `patchCurrentTransform(ctx: any): any`

**Parameters:**

- **`ctx`** `any`

**Returns:** `any`

**Calls:**

- `complex_call_2259`
- `ctx.currentTransform.scaleSelf`
- `scale`
- `ctx.scale.bind`
- `complex_call_2429`
- `ctx.currentTransform.rotateSelf`
- `rotate`
- `ctx.rotate.bind`
- `complex_call_2613`
- `ctx.currentTransform.translateSelf`
- `translate`
- `ctx.translate.bind`
- `complex_call_2797`
- `stack.push`
- `duplicate`
- `save`
- `ctx.save.bind`
- `complex_call_2962`
- `stack.pop`
- `restore`
- `ctx.restore.bind`
- `complex_call_3227`
- `ctx.currentTransform.multiplySelf`
- `transform`
- `ctx.transform.bind`
- `complex_call_3578`
- `setTransform`
- `ctx.setTransform.bind`

<details><summary>Code</summary>

```typescript
function patchCurrentTransform( ctx ) {

		if ( ctx.currentTransform ) {

			return ctx;

		}

		const stack = [];

		ctx.scale = function ( scale ) {

			return function ( x, y ) {

				ctx.currentTransform.scaleSelf( x, y );
				scale( x, y );

			};

		}( ctx.scale.bind( ctx ) );

		ctx.rotate = function ( rotate ) {

			return function ( r ) {

				ctx.currentTransform.rotateSelf( r * 180 / Math.PI );
				rotate( r );

			};

		}( ctx.rotate.bind( ctx ) );

		ctx.translate = function ( translate ) {

			return function ( x, y ) {

				ctx.currentTransform.translateSelf( x, y );
				translate( x, y );

			};

		}( ctx.translate.bind( ctx ) );

		ctx.save = function ( save ) {

			return function () {

				stack.push( duplicate( ctx.currentTransform ) );
				save();

			};

		}( ctx.save.bind( ctx ) );

		ctx.restore = function ( restore ) {

			return function () {

				if ( stack.length ) {

					ctx.currentTransform = stack.pop();

				} else {

					throw new Error( '"transform stack empty!' );

				}

				restore();

			};

		}( ctx.restore.bind( ctx ) );

		ctx.transform = function ( transform ) {

			return function ( m11, m12, m21, m22, dx, dy ) {

				const m = new DOMMatrix();
				m.a = m11;
				m.b = m12;
				m.c = m21;
				m.d = m22;
				m.e = dx;
				m.f = dy;
				ctx.currentTransform.multiplySelf( m );
				transform( m11, m12, m21, m22, dx, dy );

			};

		}( ctx.transform.bind( ctx ) );

		ctx.setTransform = function ( setTransform ) {

			return function ( m11, m12, m21, m22, dx, dy ) {

				const d = ctx.currentTransform;
				d.a = m11;
				d.b = m12;
				d.c = m21;
				d.d = m22;
				d.e = dx;
				d.f = dy;
				setTransform( m11, m12, m21, m22, dx, dy );

			};

		}( ctx.setTransform.bind( ctx ) );

		ctx.currentTransform = new DOMMatrix();

		ctx.validateTransformStack = function () {

			if ( stack.length !== 0 ) {

				throw new Error( 'transform stack not 0' );

			}

		};

		return ctx;

	}
```
</details>

### `wrap(ctx: any): any`

**Parameters:**

- **`ctx`** `any`

**Returns:** `any`

**Calls:**

- `patchCurrentTransform`

**Internal Comments:**
```
//patchDOMMatrix();
```

<details><summary>Code</summary>

```typescript
function wrap( ctx ) {

		//patchDOMMatrix();
		return patchCurrentTransform( ctx );

	}
```
</details>


---