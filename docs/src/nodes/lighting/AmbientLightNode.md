[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AmbientLightNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/AmbientLightNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnalyticLightNode` | `./AnalyticLightNode.js` |


---

## Functions

### `AmbientLightNode.setup({ context }: any): void`

**Parameters:**

- **`{ context }`** `any`

**Returns:** `void`

**Calls:**

- `context.irradiance.addAssign`

<details><summary>Code</summary>

```typescript
setup( { context } ) {

		context.irradiance.addAssign( this.colorNode );

	}
```
</details>


---

## Classes

### `AmbientLightNode`

<details><summary>Class Code</summary>

```ts
class AmbientLightNode extends AnalyticLightNode {

	static get type() {

		return 'AmbientLightNode';

	}

	/**
	 * Constructs a new ambient light node.
	 *
	 * @param {?AmbientLight} [light=null] - The ambient light source.
	 */
	constructor( light = null ) {

		super( light );

	}

	setup( { context } ) {

		context.irradiance.addAssign( this.colorNode );

	}

}
```
</details>

#### Methods

##### `setup({ context }: any): void`

<details><summary>Code</summary>

```ts
setup( { context } ) {

		context.irradiance.addAssign( this.colorNode );

	}
```
</details>


---