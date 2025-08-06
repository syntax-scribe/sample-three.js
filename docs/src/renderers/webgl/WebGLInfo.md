[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLInfo.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLInfo.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `memory` | `{ geometries: number; textures: numbe...` | let/var | `{ geometries: 0, textures: 0 }` | ✗ |
| `render` | `{ frame: number; calls: number; trian...` | let/var | `{ frame: 0, calls: 0, triangles: 0, points: 0, lines: 0 }` | ✗ |


---

## Functions

### `WebGLInfo(gl: any): { memory: { geometries: number; textures: number; }; render: { frame: number; calls: number; triangles: number; points: number; lines: number; }; programs: any; autoReset: boolean; reset: () => void; update: (count: any, mode: any, instanceCount: any) => void; }`

**Parameters:**

- **`gl`** `any`

**Returns:** `{ memory: { geometries: number; textures: number; }; render: { frame: number; calls: number; triangles: number; points: number; lines: number; }; programs: any; autoReset: boolean; reset: () => void; update: (count: any, mode: any, instanceCount: any) => void; }`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
function WebGLInfo( gl ) {

	const memory = {
		geometries: 0,
		textures: 0
	};

	const render = {
		frame: 0,
		calls: 0,
		triangles: 0,
		points: 0,
		lines: 0
	};

	function update( count, mode, instanceCount ) {

		render.calls ++;

		switch ( mode ) {

			case gl.TRIANGLES:
				render.triangles += instanceCount * ( count / 3 );
				break;

			case gl.LINES:
				render.lines += instanceCount * ( count / 2 );
				break;

			case gl.LINE_STRIP:
				render.lines += instanceCount * ( count - 1 );
				break;

			case gl.LINE_LOOP:
				render.lines += instanceCount * count;
				break;

			case gl.POINTS:
				render.points += instanceCount * count;
				break;

			default:
				console.error( 'THREE.WebGLInfo: Unknown draw mode:', mode );
				break;

		}

	}

	function reset() {

		render.calls = 0;
		render.triangles = 0;
		render.points = 0;
		render.lines = 0;

	}

	return {
		memory: memory,
		render: render,
		programs: null,
		autoReset: true,
		reset: reset,
		update: update
	};

}
```
</details>

### `update(count: any, mode: any, instanceCount: any): void`

**Parameters:**

- **`count`** `any`
- **`mode`** `any`
- **`instanceCount`** `any`

**Returns:** `void`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
function update( count, mode, instanceCount ) {

		render.calls ++;

		switch ( mode ) {

			case gl.TRIANGLES:
				render.triangles += instanceCount * ( count / 3 );
				break;

			case gl.LINES:
				render.lines += instanceCount * ( count / 2 );
				break;

			case gl.LINE_STRIP:
				render.lines += instanceCount * ( count - 1 );
				break;

			case gl.LINE_LOOP:
				render.lines += instanceCount * count;
				break;

			case gl.POINTS:
				render.points += instanceCount * count;
				break;

			default:
				console.error( 'THREE.WebGLInfo: Unknown draw mode:', mode );
				break;

		}

	}
```
</details>

### `reset(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function reset() {

		render.calls = 0;
		render.triangles = 0;
		render.points = 0;
		render.lines = 0;

	}
```
</details>


---