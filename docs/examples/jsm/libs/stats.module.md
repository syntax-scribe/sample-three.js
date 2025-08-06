[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `stats.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 17 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/libs/stats.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `mode` | `number` | let/var | `0` | ✗ |
| `prevTime` | `number` | let/var | `beginTime` | ✗ |
| `frames` | `number` | let/var | `0` | ✗ |
| `memory` | `any` | let/var | `performance.memory` | ✗ |
| `min` | `number` | let/var | `Infinity` | ✗ |
| `max` | `number` | let/var | `0` | ✗ |
| `round` | `(x: number) => number` | let/var | `Math.round` | ✗ |
| `WIDTH` | `number` | let/var | `80 * PR` | ✗ |
| `HEIGHT` | `number` | let/var | `48 * PR` | ✗ |
| `TEXT_X` | `number` | let/var | `3 * PR` | ✗ |
| `TEXT_Y` | `number` | let/var | `2 * PR` | ✗ |
| `GRAPH_X` | `number` | let/var | `3 * PR` | ✗ |
| `GRAPH_Y` | `number` | let/var | `15 * PR` | ✗ |
| `GRAPH_WIDTH` | `number` | let/var | `74 * PR` | ✗ |
| `GRAPH_HEIGHT` | `number` | let/var | `30 * PR` | ✗ |


---

## Functions

### `Stats(): { REVISION: number; dom: HTMLDivElement; addPanel: (panel: any) => any; showPanel: (id: any) => void; begin: () => void; end: () => number; update: () => void; domElement: HTMLDivElement; setMode: (id: any) => void; }`

**Returns:** `{ REVISION: number; dom: HTMLDivElement; addPanel: (panel: any) => any; showPanel: (id: any) => void; begin: () => void; end: () => number; update: () => void; domElement: HTMLDivElement; setMode: (id: any) => void; }`

**Calls:**

- `document.createElement`
- `container.addEventListener`
- `event.preventDefault`
- `showPanel`
- `container.appendChild`
- `( performance || Date ).now`
- `addPanel`
- `msPanel.update`
- `fpsPanel.update`
- `memPanel.update`
- `this.end`

**Internal Comments:**
```
// (x3)
// Backwards Compatibility (x2)
```

<details><summary>Code</summary>

```typescript
function () {

	var mode = 0;

	var container = document.createElement( 'div' );
	container.style.cssText = 'position:fixed;top:0;left:0;cursor:pointer;opacity:0.9;z-index:10000';
	container.addEventListener( 'click', function ( event ) {

		event.preventDefault();
		showPanel( ++ mode % container.children.length );

	}, false );

	//

	function addPanel( panel ) {

		container.appendChild( panel.dom );
		return panel;

	}

	function showPanel( id ) {

		for ( var i = 0; i < container.children.length; i ++ ) {

			container.children[ i ].style.display = i === id ? 'block' : 'none';

		}

		mode = id;

	}

	//

	var beginTime = ( performance || Date ).now(), prevTime = beginTime, frames = 0;

	var fpsPanel = addPanel( new Stats.Panel( 'FPS', '#0ff', '#002' ) );
	var msPanel = addPanel( new Stats.Panel( 'MS', '#0f0', '#020' ) );

	if ( self.performance && self.performance.memory ) {

		var memPanel = addPanel( new Stats.Panel( 'MB', '#f08', '#201' ) );

	}

	showPanel( 0 );

	return {

		REVISION: 16,

		dom: container,

		addPanel: addPanel,
		showPanel: showPanel,

		begin: function () {

			beginTime = ( performance || Date ).now();

		},

		end: function () {

			frames ++;

			var time = ( performance || Date ).now();

			msPanel.update( time - beginTime, 200 );

			if ( time >= prevTime + 1000 ) {

				fpsPanel.update( ( frames * 1000 ) / ( time - prevTime ), 100 );

				prevTime = time;
				frames = 0;

				if ( memPanel ) {

					var memory = performance.memory;
					memPanel.update( memory.usedJSHeapSize / 1048576, memory.jsHeapSizeLimit / 1048576 );

				}

			}

			return time;

		},

		update: function () {

			beginTime = this.end();

		},

		// Backwards Compatibility

		domElement: container,
		setMode: showPanel

	};

}
```
</details>

### `addPanel(panel: any): any`

**Parameters:**

- **`panel`** `any`

**Returns:** `any`

**Calls:**

- `container.appendChild`

<details><summary>Code</summary>

```typescript
function addPanel( panel ) {

		container.appendChild( panel.dom );
		return panel;

	}
```
</details>

### `showPanel(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function showPanel( id ) {

		for ( var i = 0; i < container.children.length; i ++ ) {

			container.children[ i ].style.display = i === id ? 'block' : 'none';

		}

		mode = id;

	}
```
</details>

### `begin(): void`

**Returns:** `void`

**Calls:**

- `( performance || Date ).now`

<details><summary>Code</summary>

```typescript
function () {

			beginTime = ( performance || Date ).now();

		}
```
</details>

### `end(): number`

**Returns:** `number`

**Calls:**

- `( performance || Date ).now`
- `msPanel.update`
- `fpsPanel.update`
- `memPanel.update`

<details><summary>Code</summary>

```typescript
function () {

			frames ++;

			var time = ( performance || Date ).now();

			msPanel.update( time - beginTime, 200 );

			if ( time >= prevTime + 1000 ) {

				fpsPanel.update( ( frames * 1000 ) / ( time - prevTime ), 100 );

				prevTime = time;
				frames = 0;

				if ( memPanel ) {

					var memory = performance.memory;
					memPanel.update( memory.usedJSHeapSize / 1048576, memory.jsHeapSizeLimit / 1048576 );

				}

			}

			return time;

		}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `this.end`

<details><summary>Code</summary>

```typescript
function () {

			beginTime = this.end();

		}
```
</details>

### `begin(): void`

**Returns:** `void`

**Calls:**

- `( performance || Date ).now`

<details><summary>Code</summary>

```typescript
function () {

			beginTime = ( performance || Date ).now();

		}
```
</details>

### `end(): number`

**Returns:** `number`

**Calls:**

- `( performance || Date ).now`
- `msPanel.update`
- `fpsPanel.update`
- `memPanel.update`

<details><summary>Code</summary>

```typescript
function () {

			frames ++;

			var time = ( performance || Date ).now();

			msPanel.update( time - beginTime, 200 );

			if ( time >= prevTime + 1000 ) {

				fpsPanel.update( ( frames * 1000 ) / ( time - prevTime ), 100 );

				prevTime = time;
				frames = 0;

				if ( memPanel ) {

					var memory = performance.memory;
					memPanel.update( memory.usedJSHeapSize / 1048576, memory.jsHeapSizeLimit / 1048576 );

				}

			}

			return time;

		}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `this.end`

<details><summary>Code</summary>

```typescript
function () {

			beginTime = this.end();

		}
```
</details>

### `begin(): void`

**Returns:** `void`

**Calls:**

- `( performance || Date ).now`

<details><summary>Code</summary>

```typescript
function () {

			beginTime = ( performance || Date ).now();

		}
```
</details>

### `end(): number`

**Returns:** `number`

**Calls:**

- `( performance || Date ).now`
- `msPanel.update`
- `fpsPanel.update`
- `memPanel.update`

<details><summary>Code</summary>

```typescript
function () {

			frames ++;

			var time = ( performance || Date ).now();

			msPanel.update( time - beginTime, 200 );

			if ( time >= prevTime + 1000 ) {

				fpsPanel.update( ( frames * 1000 ) / ( time - prevTime ), 100 );

				prevTime = time;
				frames = 0;

				if ( memPanel ) {

					var memory = performance.memory;
					memPanel.update( memory.usedJSHeapSize / 1048576, memory.jsHeapSizeLimit / 1048576 );

				}

			}

			return time;

		}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `this.end`

<details><summary>Code</summary>

```typescript
function () {

			beginTime = this.end();

		}
```
</details>

### `begin(): void`

**Returns:** `void`

**Calls:**

- `( performance || Date ).now`

<details><summary>Code</summary>

```typescript
function () {

			beginTime = ( performance || Date ).now();

		}
```
</details>

### `end(): number`

**Returns:** `number`

**Calls:**

- `( performance || Date ).now`
- `msPanel.update`
- `fpsPanel.update`
- `memPanel.update`

<details><summary>Code</summary>

```typescript
function () {

			frames ++;

			var time = ( performance || Date ).now();

			msPanel.update( time - beginTime, 200 );

			if ( time >= prevTime + 1000 ) {

				fpsPanel.update( ( frames * 1000 ) / ( time - prevTime ), 100 );

				prevTime = time;
				frames = 0;

				if ( memPanel ) {

					var memory = performance.memory;
					memPanel.update( memory.usedJSHeapSize / 1048576, memory.jsHeapSizeLimit / 1048576 );

				}

			}

			return time;

		}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `this.end`

<details><summary>Code</summary>

```typescript
function () {

			beginTime = this.end();

		}
```
</details>

### `update(value: any, maxValue: any): void`

**Parameters:**

- **`value`** `any`
- **`maxValue`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`
- `Math.max`
- `context.fillRect`
- `context.fillText`
- `round`
- `context.drawImage`

<details><summary>Code</summary>

```typescript
function ( value, maxValue ) {

			min = Math.min( min, value );
			max = Math.max( max, value );

			context.fillStyle = bg;
			context.globalAlpha = 1;
			context.fillRect( 0, 0, WIDTH, GRAPH_Y );
			context.fillStyle = fg;
			context.fillText( round( value ) + ' ' + name + ' (' + round( min ) + '-' + round( max ) + ')', TEXT_X, TEXT_Y );

			context.drawImage( canvas, GRAPH_X + PR, GRAPH_Y, GRAPH_WIDTH - PR, GRAPH_HEIGHT, GRAPH_X, GRAPH_Y, GRAPH_WIDTH - PR, GRAPH_HEIGHT );

			context.fillRect( GRAPH_X + GRAPH_WIDTH - PR, GRAPH_Y, PR, GRAPH_HEIGHT );

			context.fillStyle = bg;
			context.globalAlpha = 0.9;
			context.fillRect( GRAPH_X + GRAPH_WIDTH - PR, GRAPH_Y, PR, round( ( 1 - ( value / maxValue ) ) * GRAPH_HEIGHT ) );

		}
```
</details>

### `update(value: any, maxValue: any): void`

**Parameters:**

- **`value`** `any`
- **`maxValue`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`
- `Math.max`
- `context.fillRect`
- `context.fillText`
- `round`
- `context.drawImage`

<details><summary>Code</summary>

```typescript
function ( value, maxValue ) {

			min = Math.min( min, value );
			max = Math.max( max, value );

			context.fillStyle = bg;
			context.globalAlpha = 1;
			context.fillRect( 0, 0, WIDTH, GRAPH_Y );
			context.fillStyle = fg;
			context.fillText( round( value ) + ' ' + name + ' (' + round( min ) + '-' + round( max ) + ')', TEXT_X, TEXT_Y );

			context.drawImage( canvas, GRAPH_X + PR, GRAPH_Y, GRAPH_WIDTH - PR, GRAPH_HEIGHT, GRAPH_X, GRAPH_Y, GRAPH_WIDTH - PR, GRAPH_HEIGHT );

			context.fillRect( GRAPH_X + GRAPH_WIDTH - PR, GRAPH_Y, PR, GRAPH_HEIGHT );

			context.fillStyle = bg;
			context.globalAlpha = 0.9;
			context.fillRect( GRAPH_X + GRAPH_WIDTH - PR, GRAPH_Y, PR, round( ( 1 - ( value / maxValue ) ) * GRAPH_HEIGHT ) );

		}
```
</details>


---