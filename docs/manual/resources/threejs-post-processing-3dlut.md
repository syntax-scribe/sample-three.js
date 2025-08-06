[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-post-processing-3dlut.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 11 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`manual/resources/threejs-post-processing-3dlut.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `data` | `any` | let/var | `elem.data` | ✗ |
| `waiter` | `Waiter` | let/var | `new Waiter()` | ✗ |
| `svg` | `any` | let/var | `await getSVGDocument( elem )` | ✗ |
| `partsByName` | `{}` | let/var | `{}` | ✗ |
| `ndx` | `number` | let/var | `0` | ✗ |
| `step` | `number` | let/var | `0` | ✗ |
| `delay` | `number` | let/var | `0` | ✗ |
| `part` | `any` | let/var | `parts[ ndx ]` | ✗ |
| `diagrams` | `{ lookup: { init(elem: any): Promise<...` | let/var | `{ lookup: { async init( elem ) { const svg = await getSVGDocument( elem ); co...` | ✗ |
| `name` | `any` | let/var | `base.dataset.diagram` | ✗ |
| `info` | `any` | let/var | `diagrams[ name ]` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `getSVGDocument` | waiter.promise | *none* |


---

## Functions

### `getSVGDocument(elem: any): Promise<any>`

**Parameters:**

- **`elem`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `elem.addEventListener`
- `elem.getSVGDocument`

<details><summary>Code</summary>

```typescript
async function getSVGDocument( elem ) {

		const data = elem.data;
		elem.data = '';
		elem.data = data;
		const waiter = new Waiter();
		elem.addEventListener( 'load', waiter.resolve );
		await waiter.promise;
		return elem.getSVGDocument();

	}
```
</details>

### `createDiagram(base: any): void`

**Parameters:**

- **`base`** `any`

**Returns:** `void`

**Calls:**

- `info.init`

<details><summary>Code</summary>

```typescript
function createDiagram( base ) {

		const name = base.dataset.diagram;
		const info = diagrams[ name ];
		if ( ! info ) {

			throw new Error( `no diagram ${name}` );

		}

		info.init( base );

	}
```
</details>


---

## Classes

### `Waiter`

<details><summary>Class Code</summary>

```ts
class Waiter {

		constructor() {

			this.promise = new Promise( ( resolve ) => {

				this.resolve = resolve;

			} );

		}

	}
```
</details>


---