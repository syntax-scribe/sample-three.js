[⬅️ Back to Table of Contents](../../index.md)

# 📄 `offscreencanvas-worker-orbitcontrols.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 2 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`manual/examples/offscreencanvas-worker-orbitcontrols.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `init` | `./shared-orbitcontrols.js` |
| `EventDispatcher` | `https://cdn.skypack.dev/three@0.136.0/build/three.module.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `proxy` | `ElementProxyReceiver` | let/var | `new ElementProxyReceiver()` | ✗ |
| `proxyManager` | `ProxyManager` | let/var | `new ProxyManager()` | ✗ |
| `handlers` | `{ start: (data: any) => void; makePro...` | let/var | `{ start, makeProxy, event: proxyManager.handleEvent, }` | ✗ |
| `fn` | `any` | let/var | `handlers[ e.data.type ]` | ✗ |


---

## Functions

### `noop(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function noop() {
}
```
</details>

### `ElementProxyReceiver.setPointerCapture(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setPointerCapture() { }
```
</details>

### `ElementProxyReceiver.releasePointerCapture(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
releasePointerCapture() { }
```
</details>

### `ElementProxyReceiver.getBoundingClientRect(): { left: any; top: any; width: any; height: any; right: any; bottom: any; }`

**Returns:** `{ left: any; top: any; width: any; height: any; right: any; bottom: any; }`

<details><summary>Code</summary>

```typescript
getBoundingClientRect() {

		return {
			left: this.left,
			top: this.top,
			width: this.width,
			height: this.height,
			right: this.left + this.width,
			bottom: this.top + this.height,
		};

	}
```
</details>

### `ElementProxyReceiver.handleEvent(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
handleEvent( data ) {

		if ( data.type === 'size' ) {

			this.left = data.left;
			this.top = data.top;
			this.width = data.width;
			this.height = data.height;
			return;

		}

		data.preventDefault = noop;
		data.stopPropagation = noop;
		this.dispatchEvent( data );

	}
```
</details>

### `ElementProxyReceiver.focus(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
focus() {
		// no-op
	}
```
</details>

### `ProxyManager.makeProxy(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
makeProxy( data ) {

		const { id } = data;
		const proxy = new ElementProxyReceiver();
		this.targets[ id ] = proxy;

	}
```
</details>

### `ProxyManager.getProxy(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getProxy( id ) {

		return this.targets[ id ];

	}
```
</details>

### `ProxyManager.handleEvent(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.targets[ data.id ].handleEvent`

<details><summary>Code</summary>

```typescript
handleEvent( data ) {

		this.targets[ data.id ].handleEvent( data.data );

	}
```
</details>

### `start(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `proxyManager.getProxy`
- `init (from ./shared-orbitcontrols.js)`

<details><summary>Code</summary>

```typescript
function start( data ) {

	const proxy = proxyManager.getProxy( data.canvasId );
	proxy.ownerDocument = proxy; // HACK!
	self.document = {}; // HACK!
	init( {
		canvas: data.canvas,
		inputElement: proxy,
	} );

}
```
</details>

### `makeProxy(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `proxyManager.makeProxy`

<details><summary>Code</summary>

```typescript
function makeProxy( data ) {

	proxyManager.makeProxy( data );

}
```
</details>


---

## Classes

### `ElementProxyReceiver`

<details><summary>Class Code</summary>

```ts
class ElementProxyReceiver extends EventDispatcher {

	constructor() {

		super();
		// because OrbitControls try to set style.touchAction;
		this.style = {};

	}
	get clientWidth() {

		return this.width;

	}
	get clientHeight() {

		return this.height;

	}
	// OrbitControls call these as of r132. Maybe we should implement them
	setPointerCapture() { }
	releasePointerCapture() { }
	getBoundingClientRect() {

		return {
			left: this.left,
			top: this.top,
			width: this.width,
			height: this.height,
			right: this.left + this.width,
			bottom: this.top + this.height,
		};

	}
	handleEvent( data ) {

		if ( data.type === 'size' ) {

			this.left = data.left;
			this.top = data.top;
			this.width = data.width;
			this.height = data.height;
			return;

		}

		data.preventDefault = noop;
		data.stopPropagation = noop;
		this.dispatchEvent( data );

	}
	focus() {
		// no-op
	}

}
```
</details>

#### Methods

##### `setPointerCapture(): void`

<details><summary>Code</summary>

```ts
setPointerCapture() { }
```
</details>

##### `releasePointerCapture(): void`

<details><summary>Code</summary>

```ts
releasePointerCapture() { }
```
</details>

##### `getBoundingClientRect(): { left: any; top: any; width: any; height: any; right: any; bottom: any; }`

<details><summary>Code</summary>

```ts
getBoundingClientRect() {

		return {
			left: this.left,
			top: this.top,
			width: this.width,
			height: this.height,
			right: this.left + this.width,
			bottom: this.top + this.height,
		};

	}
```
</details>

##### `handleEvent(data: any): void`

<details><summary>Code</summary>

```ts
handleEvent( data ) {

		if ( data.type === 'size' ) {

			this.left = data.left;
			this.top = data.top;
			this.width = data.width;
			this.height = data.height;
			return;

		}

		data.preventDefault = noop;
		data.stopPropagation = noop;
		this.dispatchEvent( data );

	}
```
</details>

##### `focus(): void`

<details><summary>Code</summary>

```ts
focus() {
		// no-op
	}
```
</details>

### `ProxyManager`

<details><summary>Class Code</summary>

```ts
class ProxyManager {

	constructor() {

		this.targets = {};
		this.handleEvent = this.handleEvent.bind( this );

	}
	makeProxy( data ) {

		const { id } = data;
		const proxy = new ElementProxyReceiver();
		this.targets[ id ] = proxy;

	}
	getProxy( id ) {

		return this.targets[ id ];

	}
	handleEvent( data ) {

		this.targets[ data.id ].handleEvent( data.data );

	}

}
```
</details>

#### Methods

##### `makeProxy(data: any): void`

<details><summary>Code</summary>

```ts
makeProxy( data ) {

		const { id } = data;
		const proxy = new ElementProxyReceiver();
		this.targets[ id ] = proxy;

	}
```
</details>

##### `getProxy(id: any): any`

<details><summary>Code</summary>

```ts
getProxy( id ) {

		return this.targets[ id ];

	}
```
</details>

##### `handleEvent(data: any): void`

<details><summary>Code</summary>

```ts
handleEvent( data ) {

		this.targets[ data.id ].handleEvent( data.data );

	}
```
</details>


---