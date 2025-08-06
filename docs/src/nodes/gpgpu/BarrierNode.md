[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BarrierNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/gpgpu/BarrierNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |


---

## Functions

### `BarrierNode.generate(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder.addFlowCode`
- `builder.addLineFlowCode`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const { scope } = this;
		const { renderer } = builder;

		if ( renderer.backend.isWebGLBackend === true ) {

			builder.addFlowCode( `\t// ${scope}Barrier \n` );

		} else {

			builder.addLineFlowCode( `${scope}Barrier()`, this );

		}

	}
```
</details>

### `workgroupBarrier(): BarrierNode`

**Returns:** `BarrierNode`

**Calls:**

- `barrier( 'workgroup' ).toStack`

<details><summary>Code</summary>

```typescript
() => barrier( 'workgroup' ).toStack()
```
</details>

### `storageBarrier(): BarrierNode`

**Returns:** `BarrierNode`

**Calls:**

- `barrier( 'storage' ).toStack`

<details><summary>Code</summary>

```typescript
() => barrier( 'storage' ).toStack()
```
</details>

### `textureBarrier(): BarrierNode`

**Returns:** `BarrierNode`

**Calls:**

- `barrier( 'texture' ).toStack`

<details><summary>Code</summary>

```typescript
() => barrier( 'texture' ).toStack()
```
</details>


---

## Classes

### `BarrierNode`

<details><summary>Class Code</summary>

```ts
class BarrierNode extends Node {

	/**
	 * Constructs a new barrier node.
	 *
	 * @param {string} scope - The scope defines the behavior of the node.
	 */
	constructor( scope ) {

		super();

		this.scope = scope;

	}

	generate( builder ) {

		const { scope } = this;
		const { renderer } = builder;

		if ( renderer.backend.isWebGLBackend === true ) {

			builder.addFlowCode( `\t// ${scope}Barrier \n` );

		} else {

			builder.addLineFlowCode( `${scope}Barrier()`, this );

		}

	}

}
```
</details>

#### Methods

##### `generate(builder: any): void`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const { scope } = this;
		const { renderer } = builder;

		if ( renderer.backend.isWebGLBackend === true ) {

			builder.addFlowCode( `\t// ${scope}Barrier \n` );

		} else {

			builder.addLineFlowCode( `${scope}Barrier()`, this );

		}

	}
```
</details>


---