[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NormalMapNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/NormalMapNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `normalView` | `../accessors/Normal.js` |
| `transformNormalToView` | `../accessors/Normal.js` |
| `TBNViewMatrix` | `../accessors/AccessorsUtils.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `TangentSpaceNormalMap` | `../../constants.js` |
| `ObjectSpaceNormalMap` | `../../constants.js` |
| `directionToFaceDirection` | `./FrontFacingNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scale` | `any` | let/var | `scaleNode` | ✗ |
| `output` | `any` | let/var | `null` | ✗ |


---

## Functions

### `NormalMapNode.setup({ material }: any): any`

**Parameters:**

- **`{ material }`** `any`

**Returns:** `any`

**Calls:**

- `this.node.mul( 2.0 ).sub`
- `directionToFaceDirection (from ./FrontFacingNode.js)`
- `vec3 (from ../tsl/TSLBase.js)`
- `normalMap.xy.mul`
- `transformNormalToView (from ../accessors/Normal.js)`
- `TBNViewMatrix.mul( normalMap ).normalize`
- `console.error`

<details><summary>Code</summary>

```typescript
setup( { material } ) {

		const { normalMapType, scaleNode } = this;

		let normalMap = this.node.mul( 2.0 ).sub( 1.0 );

		if ( scaleNode !== null ) {

			let scale = scaleNode;

			if ( material.flatShading === true ) {

				scale = directionToFaceDirection( scale );

			}

			normalMap = vec3( normalMap.xy.mul( scale ), normalMap.z );

		}

		let output = null;

		if ( normalMapType === ObjectSpaceNormalMap ) {

			output = transformNormalToView( normalMap );

		} else if ( normalMapType === TangentSpaceNormalMap ) {

			output = TBNViewMatrix.mul( normalMap ).normalize();

		} else {

			console.error( `THREE.NodeMaterial: Unsupported normal map type: ${ normalMapType }` );

			output = normalView; // Fallback to default normal view

		}

		return output;

	}
```
</details>


---

## Classes

### `NormalMapNode`

<details><summary>Class Code</summary>

```ts
class NormalMapNode extends TempNode {

	static get type() {

		return 'NormalMapNode';

	}

	/**
	 * Constructs a new normal map node.
	 *
	 * @param {Node<vec3>} node - Represents the normal map data.
	 * @param {?Node<vec2>} [scaleNode=null] - Controls the intensity of the effect.
	 */
	constructor( node, scaleNode = null ) {

		super( 'vec3' );

		/**
		 * Represents the normal map data.
		 *
		 * @type {Node<vec3>}
		 */
		this.node = node;

		/**
		 * Controls the intensity of the effect.
		 *
		 * @type {?Node<vec2>}
		 * @default null
		 */
		this.scaleNode = scaleNode;

		/**
		 * The normal map type.
		 *
		 * @type {(TangentSpaceNormalMap|ObjectSpaceNormalMap)}
		 * @default TangentSpaceNormalMap
		 */
		this.normalMapType = TangentSpaceNormalMap;

	}

	setup( { material } ) {

		const { normalMapType, scaleNode } = this;

		let normalMap = this.node.mul( 2.0 ).sub( 1.0 );

		if ( scaleNode !== null ) {

			let scale = scaleNode;

			if ( material.flatShading === true ) {

				scale = directionToFaceDirection( scale );

			}

			normalMap = vec3( normalMap.xy.mul( scale ), normalMap.z );

		}

		let output = null;

		if ( normalMapType === ObjectSpaceNormalMap ) {

			output = transformNormalToView( normalMap );

		} else if ( normalMapType === TangentSpaceNormalMap ) {

			output = TBNViewMatrix.mul( normalMap ).normalize();

		} else {

			console.error( `THREE.NodeMaterial: Unsupported normal map type: ${ normalMapType }` );

			output = normalView; // Fallback to default normal view

		}

		return output;

	}

}
```
</details>

#### Methods

##### `setup({ material }: any): any`

<details><summary>Code</summary>

```ts
setup( { material } ) {

		const { normalMapType, scaleNode } = this;

		let normalMap = this.node.mul( 2.0 ).sub( 1.0 );

		if ( scaleNode !== null ) {

			let scale = scaleNode;

			if ( material.flatShading === true ) {

				scale = directionToFaceDirection( scale );

			}

			normalMap = vec3( normalMap.xy.mul( scale ), normalMap.z );

		}

		let output = null;

		if ( normalMapType === ObjectSpaceNormalMap ) {

			output = transformNormalToView( normalMap );

		} else if ( normalMapType === TangentSpaceNormalMap ) {

			output = TBNViewMatrix.mul( normalMap ).normalize();

		} else {

			console.error( `THREE.NodeMaterial: Unsupported normal map type: ${ normalMapType }` );

			output = normalView; // Fallback to default normal view

		}

		return output;

	}
```
</details>


---