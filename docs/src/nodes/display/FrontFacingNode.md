[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FrontFacingNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/FrontFacingNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeImmutable` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `BackSide` | `../../constants.js` |
| `DoubleSide` | `../../constants.js` |
| `WebGLCoordinateSystem` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `side` | `any` | let/var | `material.side` | ✗ |


---

## Functions

### `FrontFacingNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getFrontFacing`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
generate( builder ) {

		if ( builder.shaderStage !== 'fragment' ) return 'true';

		//

		const { renderer, material } = builder;

		if ( renderer.coordinateSystem === WebGLCoordinateSystem ) {

			if ( material.side === BackSide ) {

				return 'false';

			}

		}

		return builder.getFrontFacing();

	}
```
</details>


---

## Classes

### `FrontFacingNode`

<details><summary>Class Code</summary>

```ts
class FrontFacingNode extends Node {

	static get type() {

		return 'FrontFacingNode';

	}

	/**
	 * Constructs a new front facing node.
	 */
	constructor() {

		super( 'bool' );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isFrontFacingNode = true;

	}

	generate( builder ) {

		if ( builder.shaderStage !== 'fragment' ) return 'true';

		//

		const { renderer, material } = builder;

		if ( renderer.coordinateSystem === WebGLCoordinateSystem ) {

			if ( material.side === BackSide ) {

				return 'false';

			}

		}

		return builder.getFrontFacing();

	}

}
```
</details>

#### Methods

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		if ( builder.shaderStage !== 'fragment' ) return 'true';

		//

		const { renderer, material } = builder;

		if ( renderer.coordinateSystem === WebGLCoordinateSystem ) {

			if ( material.side === BackSide ) {

				return 'false';

			}

		}

		return builder.getFrontFacing();

	}
```
</details>


---