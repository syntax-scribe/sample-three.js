[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ProjectorLightNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/ProjectorLightNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `SpotLightNode` | `./SpotLightNode.js` |
| `float` | `../tsl/TSLCore.js` |
| `Fn` | `../tsl/TSLCore.js` |
| `If` | `../tsl/TSLCore.js` |
| `vec2` | `../tsl/TSLCore.js` |
| `length` | `../math/MathNode.js` |
| `min` | `../math/MathNode.js` |
| `max` | `../math/MathNode.js` |
| `saturate` | `../math/MathNode.js` |
| `acos` | `../math/MathNode.js` |
| `div` | `../math/OperatorNode.js` |
| `sub` | `../math/OperatorNode.js` |
| `lightShadowMatrix` | `../accessors/Lights.js` |
| `positionWorld` | `../accessors/Position.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `light` | `Light` | let/var | `this.light` | ✗ |
| `aspect` | `number` | let/var | `1` | ✗ |
| `penumbraCos` | `UniformNode<float>` | let/var | `this.penumbraCosNode` | ✗ |


---

## Functions

### `ProjectorLightNode.update(frame: any): void`

**Parameters:**

- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `super.update`
- `Math.min`
- `Math.cos`

<details><summary>Code</summary>

```typescript
update( frame ) {

		super.update( frame );

		const light = this.light;

		this.penumbraCosNode.value = Math.min( Math.cos( light.angle * ( 1 - light.penumbra ) ), .99999 );

		if ( light.aspect === null ) {

			let aspect = 1;

			if ( light.map !== null ) {

				aspect = light.map.width / light.map.height;

			}

			light.shadow.aspect = aspect;

		} else {

			light.shadow.aspect = light.aspect;

		}

	}
```
</details>

### `ProjectorLightNode.getSpotAttenuation(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to compute projection attenuation.
	 *
	 * @param {NodeBuilder} builder - The node builder.
	 * @return {Node<float>} The spot attenuation.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

**Calls:**

- `float (from ../tsl/TSLCore.js)`
- `lightShadowMatrix( this.light ).mul`
- `If (from ../tsl/TSLCore.js)`
- `spotLightCoord.w.greaterThan`
- `spotLightCoord.xyz.div`
- `sdBox`
- `projectionUV.xy.sub`
- `vec2 (from ../tsl/TSLCore.js)`
- `div (from ../math/OperatorNode.js)`
- `sub( 1.0, acos( penumbraCos ) ).sub`
- `attenuation.assign`
- `saturate (from ../math/MathNode.js)`
- `boxDist.mul( - 2.0 ).mul`

**Internal Comments:**
```
// compute the fragment's position in the light's clip space (x2)
// the sign of w determines whether the current fragment is in front or behind the light. (x3)
// to avoid a back-projection, it's important to only compute an attenuation if w is positive (x3)
```

<details><summary>Code</summary>

```typescript
getSpotAttenuation( builder ) {

		const attenuation = float( 0 );
		const penumbraCos = this.penumbraCosNode;

		// compute the fragment's position in the light's clip space

		const spotLightCoord = lightShadowMatrix( this.light ).mul( builder.context.positionWorld || positionWorld );

		// the sign of w determines whether the current fragment is in front or behind the light.
		// to avoid a back-projection, it's important to only compute an attenuation if w is positive

		If( spotLightCoord.w.greaterThan( 0 ), () => {

			const projectionUV = spotLightCoord.xyz.div( spotLightCoord.w );
			const boxDist = sdBox( projectionUV.xy.sub( vec2( 0.5 ) ), vec2( 0.5 ) );
			const angleFactor = div( - 1.0, sub( 1.0, acos( penumbraCos ) ).sub( 1.0 ) );
			attenuation.assign( saturate( boxDist.mul( - 2.0 ).mul( angleFactor ) ) );

		} );

		return attenuation;

	}
```
</details>


---

## Classes

### `ProjectorLightNode`

<details><summary>Class Code</summary>

```ts
class ProjectorLightNode extends SpotLightNode {

	static get type() {

		return 'ProjectorLightNode';

	}

	update( frame ) {

		super.update( frame );

		const light = this.light;

		this.penumbraCosNode.value = Math.min( Math.cos( light.angle * ( 1 - light.penumbra ) ), .99999 );

		if ( light.aspect === null ) {

			let aspect = 1;

			if ( light.map !== null ) {

				aspect = light.map.width / light.map.height;

			}

			light.shadow.aspect = aspect;

		} else {

			light.shadow.aspect = light.aspect;

		}

	}

	/**
	 * Overwrites the default implementation to compute projection attenuation.
	 *
	 * @param {NodeBuilder} builder - The node builder.
	 * @return {Node<float>} The spot attenuation.
	 */
	getSpotAttenuation( builder ) {

		const attenuation = float( 0 );
		const penumbraCos = this.penumbraCosNode;

		// compute the fragment's position in the light's clip space

		const spotLightCoord = lightShadowMatrix( this.light ).mul( builder.context.positionWorld || positionWorld );

		// the sign of w determines whether the current fragment is in front or behind the light.
		// to avoid a back-projection, it's important to only compute an attenuation if w is positive

		If( spotLightCoord.w.greaterThan( 0 ), () => {

			const projectionUV = spotLightCoord.xyz.div( spotLightCoord.w );
			const boxDist = sdBox( projectionUV.xy.sub( vec2( 0.5 ) ), vec2( 0.5 ) );
			const angleFactor = div( - 1.0, sub( 1.0, acos( penumbraCos ) ).sub( 1.0 ) );
			attenuation.assign( saturate( boxDist.mul( - 2.0 ).mul( angleFactor ) ) );

		} );

		return attenuation;

	}

}
```
</details>

#### Methods

##### `update(frame: any): void`

<details><summary>Code</summary>

```ts
update( frame ) {

		super.update( frame );

		const light = this.light;

		this.penumbraCosNode.value = Math.min( Math.cos( light.angle * ( 1 - light.penumbra ) ), .99999 );

		if ( light.aspect === null ) {

			let aspect = 1;

			if ( light.map !== null ) {

				aspect = light.map.width / light.map.height;

			}

			light.shadow.aspect = aspect;

		} else {

			light.shadow.aspect = light.aspect;

		}

	}
```
</details>

##### `getSpotAttenuation(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
getSpotAttenuation( builder ) {

		const attenuation = float( 0 );
		const penumbraCos = this.penumbraCosNode;

		// compute the fragment's position in the light's clip space

		const spotLightCoord = lightShadowMatrix( this.light ).mul( builder.context.positionWorld || positionWorld );

		// the sign of w determines whether the current fragment is in front or behind the light.
		// to avoid a back-projection, it's important to only compute an attenuation if w is positive

		If( spotLightCoord.w.greaterThan( 0 ), () => {

			const projectionUV = spotLightCoord.xyz.div( spotLightCoord.w );
			const boxDist = sdBox( projectionUV.xy.sub( vec2( 0.5 ) ), vec2( 0.5 ) );
			const angleFactor = div( - 1.0, sub( 1.0, acos( penumbraCos ) ).sub( 1.0 ) );
			attenuation.assign( saturate( boxDist.mul( - 2.0 ).mul( angleFactor ) ) );

		} );

		return attenuation;

	}
```
</details>


---