[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-align-html-elements-to-3d.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 28 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`manual/resources/threejs-align-html-elements-to-3d.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GUI` | `../../examples/jsm/libs/lil-gui.module.min.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `dx` | `number` | let/var | `x1 - x2` | ✗ |
| `dy` | `number` | let/var | `y1 - y2` | ✗ |
| `rot` | `number` | let/var | `- Math.atan2( dx, dy )` | ✗ |
| `THREE` | `{ MathUtils: { radToDeg(rad: any): nu...` | let/var | `{ MathUtils: { radToDeg( rad ) { return rad * 180 / Math.PI; }, degToRad( deg...` | ✗ |
| `dx` | `number` | let/var | `x1 - x2` | ✗ |
| `dy` | `number` | let/var | `y1 - y2` | ✗ |
| `width` | `number` | let/var | `canvas.clientWidth * pixelRatio \| 0` | ✗ |
| `height` | `number` | let/var | `canvas.clientHeight * pixelRatio \| 0` | ✗ |
| `needResize` | `boolean` | let/var | `canvas.width !== width \|\| canvas.height !== height` | ✗ |
| `settings` | `{ rotation: number; }` | let/var | `{ rotation: 0.3, }` | ✗ |
| `gui` | `g` | let/var | `new GUI( { autoPlace: false } )` | ✗ |
| `darkColors` | `{ globe: string; camera: string; base...` | let/var | `{ globe: 'green', camera: '#AAA', base: '#DDD', label: '#0FF', }` | ✗ |
| `lightColors` | `{ globe: string; camera: string; base...` | let/var | `{ globe: '#0C0', camera: 'black', base: '#000', label: 'blue', }` | ✗ |
| `isDarkMode` | `boolean` | let/var | `darkMatcher.matches` | ✗ |
| `colors` | `{ globe: string; camera: string; base...` | let/var | `isDarkMode ? darkColors : lightColors` | ✗ |
| `pixelRatio` | `number` | let/var | `window.devicePixelRatio` | ✗ |
| `width` | `number` | let/var | `ctx.canvas.width / pixelRatio` | ✗ |
| `height` | `number` | let/var | `ctx.canvas.height / pixelRatio` | ✗ |
| `half` | `number` | let/var | `min / 2` | ✗ |
| `r` | `number` | let/var | `half * 0.4` | ✗ |
| `x` | `number` | let/var | `r * Math.sin( - rotation )` | ✗ |
| `y` | `number` | let/var | `r * Math.cos( - rotation )` | ✗ |
| `camDX` | `number` | let/var | `x - 0` | ✗ |
| `camDY` | `number` | let/var | `y - ( half - 40 )` | ✗ |
| `textColor` | `string` | let/var | `dp < 0 ? colors.base : 'red'` | ✗ |
| `diagrams` | `{ dotProduct: { create(info: any): vo...` | let/var | `{ dotProduct: { create( info ) { const { elem } = info; const div = document....` | ✗ |
| `name` | `any` | let/var | `base.dataset.diagram` | ✗ |
| `info` | `any` | let/var | `diagrams[ name ]` | ✗ |


---

## Functions

### `outlineText(ctx: any, msg: any, x: any, y: any): void`

**Parameters:**

- **`ctx`** `any`
- **`msg`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `void`

**Calls:**

- `ctx.strokeText`
- `ctx.fillText`

<details><summary>Code</summary>

```typescript
function outlineText( ctx, msg, x, y ) {

		ctx.strokeText( msg, x, y );
		ctx.fillText( msg, x, y );

	}
```
</details>

### `arrow(ctx: any, x1: any, y1: any, x2: any, y2: any, start: any, end: any, size: any): void`

**Parameters:**

- **`ctx`** `any`
- **`x1`** `any`
- **`y1`** `any`
- **`x2`** `any`
- **`y2`** `any`
- **`start`** `any`
- **`end`** `any`
- **`size`** `any`

**Returns:** `void`

**Calls:**

- `Math.atan2`
- `Math.sqrt`
- `ctx.save`
- `ctx.translate`
- `ctx.rotate`
- `ctx.beginPath`
- `ctx.moveTo`
- `ctx.lineTo`
- `ctx.stroke`
- `ctx.restore`
- `arrowHead`

<details><summary>Code</summary>

```typescript
function arrow( ctx, x1, y1, x2, y2, start, end, size ) {

		size = size || 1;
		const dx = x1 - x2;
		const dy = y1 - y2;
		const rot = - Math.atan2( dx, dy );
		const len = Math.sqrt( dx * dx + dy * dy );
		ctx.save();
		{

			ctx.translate( x1, y1 );
			ctx.rotate( rot );
			ctx.beginPath();
			ctx.moveTo( 0, 0 );
			ctx.lineTo( 0, - ( len - 10 * size ) );
			ctx.stroke();

		}

		ctx.restore();
		if ( start ) {

			arrowHead( ctx, x1, y1, rot, size );

		}

		if ( end ) {

			arrowHead( ctx, x2, y2, rot + Math.PI, size );

		}

	}
```
</details>

### `arrowHead(ctx: any, x: any, y: any, rot: any, size: any): void`

**Parameters:**

- **`ctx`** `any`
- **`x`** `any`
- **`y`** `any`
- **`rot`** `any`
- **`size`** `any`

**Returns:** `void`

**Calls:**

- `ctx.save`
- `ctx.translate`
- `ctx.rotate`
- `ctx.scale`
- `ctx.beginPath`
- `ctx.moveTo`
- `ctx.lineTo`
- `ctx.closePath`
- `ctx.fill`
- `ctx.restore`

<details><summary>Code</summary>

```typescript
function arrowHead( ctx, x, y, rot, size ) {

		ctx.save();
		{

			ctx.translate( x, y );
			ctx.rotate( rot );
			ctx.scale( size, size );
			ctx.translate( 0, - 10 );
			ctx.beginPath();
			ctx.moveTo( 0, 0 );
			ctx.lineTo( - 5, - 2 );
			ctx.lineTo( 0, 10 );
			ctx.lineTo( 5, - 2 );
			ctx.closePath();
			ctx.fill();

		}

		ctx.restore();

	}
```
</details>

### `dot(x1: any, y1: any, x2: any, y2: any): number`

**Parameters:**

- **`x1`** `any`
- **`y1`** `any`
- **`x2`** `any`
- **`y2`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function dot( x1, y1, x2, y2 ) {

		return x1 * x2 + y1 * y2;

	}
```
</details>

### `distance(x1: any, y1: any, x2: any, y2: any): number`

**Parameters:**

- **`x1`** `any`
- **`y1`** `any`
- **`x2`** `any`
- **`y2`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function distance( x1, y1, x2, y2 ) {

		const dx = x1 - x2;
		const dy = y1 - y2;
		return Math.sqrt( dx * dx + dy * dy );

	}
```
</details>

### `normalize(x: any, y: any): number[]`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `number[]`

**Calls:**

- `distance`

<details><summary>Code</summary>

```typescript
function normalize( x, y ) {

		const l = distance( 0, 0, x, y );
		if ( l > 0.00001 ) {

			return [ x / l, y / l ];

		} else {

			return [ 0, 0 ];

		}

	}
```
</details>

### `resizeCanvasToDisplaySize(canvas: any, pixelRatio: number): boolean`

**Parameters:**

- **`canvas`** `any`
- **`pixelRatio`** `number`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function resizeCanvasToDisplaySize( canvas, pixelRatio = 1 ) {

		const width = canvas.clientWidth * pixelRatio | 0;
		const height = canvas.clientHeight * pixelRatio | 0;
		const needResize = canvas.width !== width || canvas.height !== height;
		if ( needResize ) {

			canvas.width = width;
			canvas.height = height;

		}

		return needResize;

	}
```
</details>

### `render(): void`

**Returns:** `void`

**Calls:**

- `resizeCanvasToDisplaySize`
- `ctx.clearRect`
- `ctx.save`
- `Math.min`
- `Math.sin`
- `Math.cos`
- `normalize`
- `dot`
- `ctx.scale`
- `ctx.translate`
- `ctx.beginPath`
- `ctx.arc`
- `ctx.fill`
- `ctx.fillRect`
- `ctx.moveTo`
- `ctx.lineTo`
- `ctx.closePath`
- `ctx.restore`
- `arrow`
- `outlineText`
- `advanceText`
- `ctx.rotate`
- `Math.atan2`
- `dp.toFixed`

<details><summary>Code</summary>

```typescript
function render() {

					const { rotation } = settings;
					const isDarkMode = darkMatcher.matches;
					const colors = isDarkMode ? darkColors : lightColors;

					const pixelRatio = window.devicePixelRatio;
					resizeCanvasToDisplaySize( ctx.canvas, pixelRatio );

					ctx.clearRect( 0, 0, ctx.canvas.width, ctx.canvas.height );
					ctx.save();
					{

						const width = ctx.canvas.width / pixelRatio;
						const height = ctx.canvas.height / pixelRatio;
						const min = Math.min( width, height );
						const half = min / 2;

						const r = half * 0.4;
						const x = r * Math.sin( - rotation );
						const y = r * Math.cos( - rotation );

						const camDX = x - 0;
						const camDY = y - ( half - 40 );

						const labelDir = normalize( x, y );
						const camToLabelDir = normalize( camDX, camDY );

						const dp = dot( ...camToLabelDir, ...labelDir );

						ctx.scale( pixelRatio, pixelRatio );
						ctx.save();
						{

							{

								ctx.translate( width / 2, height / 2 );
								ctx.beginPath();
								ctx.arc( 0, 0, half * 0.4, 0, Math.PI * 2 );
								ctx.fillStyle = colors.globe;
								ctx.fill();

								ctx.save();
								{

									ctx.fillStyle = colors.camera;
									ctx.translate( 0, half );
									ctx.fillRect( - 15, - 30, 30, 30 );
									ctx.beginPath();
									ctx.moveTo( 0, - 25 );
									ctx.lineTo( - 25, - 50 );
									ctx.lineTo( 25, - 50 );
									ctx.closePath();
									ctx.fill();

								}

								ctx.restore();

								ctx.save();
								{

									ctx.lineWidth = 4;
									ctx.strokeStyle = colors.camera;
									ctx.fillStyle = colors.camera;
									arrow( ctx, 0, half - 40, x, y, false, true, 2 );

									ctx.save();
									{

										ctx.strokeStyle = colors.label;
										ctx.fillStyle = colors.label;
										arrow( ctx, 0, 0, x, y, false, true, 2 );

									}

									ctx.restore();

									{

										ctx.lineWidth = 3;
										ctx.strokeStyle = 'black';
										ctx.fillStyle = dp < 0 ? 'white' : 'red';
										ctx.font = '20px sans-serif';
										ctx.textAlign = 'center';
										ctx.textBaseline = 'middle';
										outlineText( ctx, 'label', x, y );

									}

								}

								ctx.restore();

							}

							ctx.restore();

						}

						ctx.lineWidth = 3;
						ctx.font = '24px sans-serif';
						ctx.strokeStyle = 'black';
						ctx.textAlign = 'left';
						ctx.textBaseline = 'middle';
						ctx.save();
						{

							ctx.translate( width / 4, 80 );
							const textColor = dp < 0 ? colors.base : 'red';
							advanceText( ctx, textColor, 'dot( ' );
							ctx.save();
							{

								ctx.fillStyle = colors.camera;
								ctx.strokeStyle = colors.camera;
								ctx.rotate( Math.atan2( camDY, camDX ) );
								arrow( ctx, - 8, 0, 8, 0, false, true, 1 );

							}

							ctx.restore();
							advanceText( ctx, textColor, ' ,  ' );
							ctx.save();
							{

								ctx.fillStyle = colors.label;
								ctx.strokeStyle = colors.label;
								ctx.rotate( rotation + Math.PI * 0.5 );
								arrow( ctx, - 8, 0, 8, 0, false, true, 1 );

							}

							ctx.restore();
							advanceText( ctx, textColor, ` ) = ${dp.toFixed( 2 )}` );

						}

						ctx.restore();

					}

					ctx.restore();

				}
```
</details>

### `advanceText(ctx: any, color: any, str: any): void`

**Parameters:**

- **`ctx`** `any`
- **`color`** `any`
- **`str`** `any`

**Returns:** `void`

**Calls:**

- `ctx.fillText`
- `ctx.translate`
- `ctx.measureText`

<details><summary>Code</summary>

```typescript
function advanceText( ctx, color, str ) {

		ctx.fillStyle = color;
		ctx.fillText( str, 0, 0 );
		ctx.translate( ctx.measureText( str ).width, 0 );

	}
```
</details>

### `createDiagram(base: any): void`

**Parameters:**

- **`base`** `any`

**Returns:** `void`

**Calls:**

- `info.create`

<details><summary>Code</summary>

```typescript
function createDiagram( base ) {

		const name = base.dataset.diagram;
		const info = diagrams[ name ];
		if ( ! info ) {

			throw new Error( `no diagram ${name}` );

		}

		info.create( { elem: base } );

	}
```
</details>


---

## Classes

### `DegRadHelper`

<details><summary>Class Code</summary>

```ts
class DegRadHelper {

		constructor( obj, prop ) {

			this.obj = obj;
			this.prop = prop;

		}
		get value() {

			return THREE.MathUtils.radToDeg( this.obj[ this.prop ] );

		}
		set value( v ) {

			this.obj[ this.prop ] = THREE.MathUtils.degToRad( v );

		}

	}
```
</details>


---