[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLRenderStates.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLRenderStates.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLLights` | `./WebGLLights.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `lights` | `any` | let/var | `new WebGLLights( extensions )` | ✗ |
| `lightsArray` | `any[]` | let/var | `[]` | ✗ |
| `shadowsArray` | `any[]` | let/var | `[]` | ✗ |
| `state` | `{ lightsArray: any[]; shadowsArray: a...` | let/var | `{ lightsArray: lightsArray, shadowsArray: shadowsArray, camera: null, lights:...` | ✗ |
| `renderStates` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `renderState` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `WebGLRenderState(extensions: any): { init: (camera: any) => void; state: { lightsArray: any[]; shadowsArray: any[]; camera: any; lights: any; transmissionRenderTarget: {}; }; setupLights: () => void; setupLightsView: (camera: any) => void; pushLight: (light: any) => void; pushShadow: (shadowLight: any) => void; }`

**Parameters:**

- **`extensions`** `any`

**Returns:** `{ init: (camera: any) => void; state: { lightsArray: any[]; shadowsArray: any[]; camera: any; lights: any; transmissionRenderTarget: {}; }; setupLights: () => void; setupLightsView: (camera: any) => void; pushLight: (light: any) => void; pushShadow: (shadowLight: any) => void; }`

**Calls:**

- `lightsArray.push`
- `shadowsArray.push`
- `lights.setup`
- `lights.setupView`

<details><summary>Code</summary>

```typescript
function WebGLRenderState( extensions ) {

	const lights = new WebGLLights( extensions );

	const lightsArray = [];
	const shadowsArray = [];

	function init( camera ) {

		state.camera = camera;

		lightsArray.length = 0;
		shadowsArray.length = 0;

	}

	function pushLight( light ) {

		lightsArray.push( light );

	}

	function pushShadow( shadowLight ) {

		shadowsArray.push( shadowLight );

	}

	function setupLights() {

		lights.setup( lightsArray );

	}

	function setupLightsView( camera ) {

		lights.setupView( lightsArray, camera );

	}

	const state = {
		lightsArray: lightsArray,
		shadowsArray: shadowsArray,

		camera: null,

		lights: lights,

		transmissionRenderTarget: {}
	};

	return {
		init: init,
		state: state,
		setupLights: setupLights,
		setupLightsView: setupLightsView,

		pushLight: pushLight,
		pushShadow: pushShadow
	};

}
```
</details>

### `init(camera: any): void`

**Parameters:**

- **`camera`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function init( camera ) {

		state.camera = camera;

		lightsArray.length = 0;
		shadowsArray.length = 0;

	}
```
</details>

### `pushLight(light: any): void`

**Parameters:**

- **`light`** `any`

**Returns:** `void`

**Calls:**

- `lightsArray.push`

<details><summary>Code</summary>

```typescript
function pushLight( light ) {

		lightsArray.push( light );

	}
```
</details>

### `pushShadow(shadowLight: any): void`

**Parameters:**

- **`shadowLight`** `any`

**Returns:** `void`

**Calls:**

- `shadowsArray.push`

<details><summary>Code</summary>

```typescript
function pushShadow( shadowLight ) {

		shadowsArray.push( shadowLight );

	}
```
</details>

### `setupLights(): void`

**Returns:** `void`

**Calls:**

- `lights.setup`

<details><summary>Code</summary>

```typescript
function setupLights() {

		lights.setup( lightsArray );

	}
```
</details>

### `setupLightsView(camera: any): void`

**Parameters:**

- **`camera`** `any`

**Returns:** `void`

**Calls:**

- `lights.setupView`

<details><summary>Code</summary>

```typescript
function setupLightsView( camera ) {

		lights.setupView( lightsArray, camera );

	}
```
</details>

### `WebGLRenderStates(extensions: any): { get: (scene: any, renderCallDepth?: number) => any; dispose: () => void; }`

**Parameters:**

- **`extensions`** `any`

**Returns:** `{ get: (scene: any, renderCallDepth?: number) => any; dispose: () => void; }`

**Calls:**

- `renderStates.get`
- `renderStates.set`
- `renderStateArray.push`

<details><summary>Code</summary>

```typescript
function WebGLRenderStates( extensions ) {

	let renderStates = new WeakMap();

	function get( scene, renderCallDepth = 0 ) {

		const renderStateArray = renderStates.get( scene );
		let renderState;

		if ( renderStateArray === undefined ) {

			renderState = new WebGLRenderState( extensions );
			renderStates.set( scene, [ renderState ] );

		} else {

			if ( renderCallDepth >= renderStateArray.length ) {

				renderState = new WebGLRenderState( extensions );
				renderStateArray.push( renderState );

			} else {

				renderState = renderStateArray[ renderCallDepth ];

			}

		}

		return renderState;

	}

	function dispose() {

		renderStates = new WeakMap();

	}

	return {
		get: get,
		dispose: dispose
	};

}
```
</details>

### `get(scene: any, renderCallDepth: number): any`

**Parameters:**

- **`scene`** `any`
- **`renderCallDepth`** `number`

**Returns:** `any`

**Calls:**

- `renderStates.get`
- `renderStates.set`
- `renderStateArray.push`

<details><summary>Code</summary>

```typescript
function get( scene, renderCallDepth = 0 ) {

		const renderStateArray = renderStates.get( scene );
		let renderState;

		if ( renderStateArray === undefined ) {

			renderState = new WebGLRenderState( extensions );
			renderStates.set( scene, [ renderState ] );

		} else {

			if ( renderCallDepth >= renderStateArray.length ) {

				renderState = new WebGLRenderState( extensions );
				renderStateArray.push( renderState );

			} else {

				renderState = renderStateArray[ renderCallDepth ];

			}

		}

		return renderState;

	}
```
</details>

### `dispose(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function dispose() {

		renderStates = new WeakMap();

	}
```
</details>


---