[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Viewport.Pathtracer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Viewport.Pathtracer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLPathTracer` | `three-gpu-pathtracer` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `pathTracer` | `any` | let/var | `null` | ✗ |


---

## Functions

### `ViewportPathtracer(renderer: any): { init: (scene: any, camera: any) => void; setSize: () => void; setBackground: () => void; setEnvironment: () => void; updateMaterials: () => void; update: () => void; reset: () => void; getSamples: () => any; }`

**Parameters:**

- **`renderer`** `any`

**Returns:** `{ init: (scene: any, camera: any) => void; setSize: () => void; setBackground: () => void; setEnvironment: () => void; updateMaterials: () => void; update: () => void; reset: () => void; getSamples: () => any; }`

**Calls:**

- `pathTracer.setScene`
- `pathTracer.updateCamera`
- `pathTracer.updateEnvironment`
- `pathTracer.updateMaterials`
- `pathTracer.renderSample`

**Internal Comments:**
```
// path tracer size automatically updates based on the canvas (x4)
// update environment settings based on initialized scene fields (x4)
```

<details><summary>Code</summary>

```typescript
function ViewportPathtracer( renderer ) {

	let pathTracer = null;

	function init( scene, camera ) {

		if ( pathTracer === null ) {

			pathTracer = new WebGLPathTracer( renderer );
			pathTracer.filterGlossyFactor = 0.5;

		}

		pathTracer.setScene( scene, camera );

	}

	function setSize( /* width, height */ ) {

		if ( pathTracer === null ) return;

		// path tracer size automatically updates based on the canvas
		pathTracer.updateCamera();

	}

	function setBackground( /* background, blurriness */ ) {

		if ( pathTracer === null ) return;

		// update environment settings based on initialized scene fields
		pathTracer.updateEnvironment();

	}

	function updateMaterials() {

		if ( pathTracer === null ) return;

		pathTracer.updateMaterials();

	}

	function setEnvironment( /* environment */ ) {

		if ( pathTracer === null ) return;

		pathTracer.updateEnvironment();

	}

	function update() {

		if ( pathTracer === null ) return;

		pathTracer.renderSample();

	}

	function reset() {

		if ( pathTracer === null ) return;

		pathTracer.updateCamera();

	}

	function getSamples() {

		if ( pathTracer === null ) return;

		return pathTracer.samples;

	}

	return {
		init: init,
		setSize: setSize,
		setBackground: setBackground,
		setEnvironment: setEnvironment,
		updateMaterials: updateMaterials,
		update: update,
		reset: reset,
		getSamples: getSamples
	};

}
```
</details>

### `init(scene: any, camera: any): void`

**Parameters:**

- **`scene`** `any`
- **`camera`** `any`

**Returns:** `void`

**Calls:**

- `pathTracer.setScene`

<details><summary>Code</summary>

```typescript
function init( scene, camera ) {

		if ( pathTracer === null ) {

			pathTracer = new WebGLPathTracer( renderer );
			pathTracer.filterGlossyFactor = 0.5;

		}

		pathTracer.setScene( scene, camera );

	}
```
</details>

### `setSize(): void`

**Returns:** `void`

**Calls:**

- `pathTracer.updateCamera`

**Internal Comments:**
```
// path tracer size automatically updates based on the canvas (x4)
```

<details><summary>Code</summary>

```typescript
function setSize( /* width, height */ ) {

		if ( pathTracer === null ) return;

		// path tracer size automatically updates based on the canvas
		pathTracer.updateCamera();

	}
```
</details>

### `setBackground(): void`

**Returns:** `void`

**Calls:**

- `pathTracer.updateEnvironment`

**Internal Comments:**
```
// update environment settings based on initialized scene fields (x4)
```

<details><summary>Code</summary>

```typescript
function setBackground( /* background, blurriness */ ) {

		if ( pathTracer === null ) return;

		// update environment settings based on initialized scene fields
		pathTracer.updateEnvironment();

	}
```
</details>

### `updateMaterials(): void`

**Returns:** `void`

**Calls:**

- `pathTracer.updateMaterials`

<details><summary>Code</summary>

```typescript
function updateMaterials() {

		if ( pathTracer === null ) return;

		pathTracer.updateMaterials();

	}
```
</details>

### `setEnvironment(): void`

**Returns:** `void`

**Calls:**

- `pathTracer.updateEnvironment`

<details><summary>Code</summary>

```typescript
function setEnvironment( /* environment */ ) {

		if ( pathTracer === null ) return;

		pathTracer.updateEnvironment();

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `pathTracer.renderSample`

<details><summary>Code</summary>

```typescript
function update() {

		if ( pathTracer === null ) return;

		pathTracer.renderSample();

	}
```
</details>

### `reset(): void`

**Returns:** `void`

**Calls:**

- `pathTracer.updateCamera`

<details><summary>Code</summary>

```typescript
function reset() {

		if ( pathTracer === null ) return;

		pathTracer.updateCamera();

	}
```
</details>

### `getSamples(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getSamples() {

		if ( pathTracer === null ) return;

		return pathTracer.samples;

	}
```
</details>


---