[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SpotLightNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/SpotLightNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnalyticLightNode` | `./AnalyticLightNode.js` |
| `getDistanceAttenuation` | `./LightUtils.js` |
| `uniform` | `../core/UniformNode.js` |
| `smoothstep` | `../math/MathNode.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `lightTargetDirection` | `../accessors/Lights.js` |
| `lightProjectionUV` | `../accessors/Lights.js` |
| `texture` | `../accessors/TextureNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `projectionUV` | `any` | let/var | `properties.projectionUV` | ✗ |
| `projected` | `any` | let/var | `*not shown*` | ✗ |
| `lightCoord` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `SpotLightNode.update(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Overwritten to updated spot light specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `super.update`
- `Math.cos`

<details><summary>Code</summary>

```typescript
update( frame ) {

		super.update( frame );

		const { light } = this;

		this.coneCosNode.value = Math.cos( light.angle );
		this.penumbraCosNode.value = Math.cos( light.angle * ( 1 - light.penumbra ) );

		this.cutoffDistanceNode.value = light.distance;
		this.decayExponentNode.value = light.decay;

	}
```
</details>

### `SpotLightNode.getSpotAttenuation(builder: NodeBuilder, angleCosine: any): any`

**JSDoc:**
```typescript
/**
	 * Computes the spot attenuation for the given angle.
	 *
	 * @param {NodeBuilder} builder - The node builder.
	 * @param {Node<float>} angleCosine - The angle to compute the spot attenuation for.
	 * @return {Node<float>} The spot attenuation.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`angleCosine`** `any`

**Returns:** `any`

**Calls:**

- `smoothstep (from ../math/MathNode.js)`

<details><summary>Code</summary>

```typescript
getSpotAttenuation( builder, angleCosine ) {

		const { coneCosNode, penumbraCosNode } = this;

		return smoothstep( coneCosNode, penumbraCosNode, angleCosine );

	}
```
</details>

### `SpotLightNode.getLightCoord(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `lightProjectionUV (from ../accessors/Lights.js)`

<details><summary>Code</summary>

```typescript
getLightCoord( builder ) {

		const properties = builder.getNodeProperties( this );
		let projectionUV = properties.projectionUV;

		if ( projectionUV === undefined ) {

			projectionUV = lightProjectionUV( this.light, builder.context.positionWorld );

			properties.projectionUV = projectionUV;

		}

		return projectionUV;

	}
```
</details>

### `SpotLightNode.setupDirect(builder: any): { lightColor: any; lightDirection: any; }`

**Parameters:**

- **`builder`** `any`

**Returns:** `{ lightColor: any; lightDirection: any; }`

**Calls:**

- `this.getLightVector`
- `lightVector.normalize`
- `lightDirection.dot`
- `lightTargetDirection (from ../accessors/Lights.js)`
- `this.getSpotAttenuation`
- `lightVector.length`
- `getDistanceAttenuation (from ./LightUtils.js)`
- `colorNode.mul( spotAttenuation ).mul`
- `this.getLightCoord`
- `light.colorNode`
- `texture( light.map, lightCoord.xy ).onRenderUpdate`
- `lightCoord.mul( 2. ).sub( 1. ).abs().lessThan( 1. ).all`
- `inSpotLightMap.select`
- `lightColor.mul`

<details><summary>Code</summary>

```typescript
setupDirect( builder ) {

		const { colorNode, cutoffDistanceNode, decayExponentNode, light } = this;

		const lightVector = this.getLightVector( builder );

		const lightDirection = lightVector.normalize();
		const angleCos = lightDirection.dot( lightTargetDirection( light ) );

		const spotAttenuation = this.getSpotAttenuation( builder, angleCos );

		const lightDistance = lightVector.length();

		const lightAttenuation = getDistanceAttenuation( {
			lightDistance,
			cutoffDistance: cutoffDistanceNode,
			decayExponent: decayExponentNode
		} );

		let lightColor = colorNode.mul( spotAttenuation ).mul( lightAttenuation );

		let projected, lightCoord;

		if ( light.colorNode ) {

			lightCoord = this.getLightCoord( builder );
			projected = light.colorNode( lightCoord );

		} else if ( light.map ) {

			lightCoord = this.getLightCoord( builder );
			projected = texture( light.map, lightCoord.xy ).onRenderUpdate( () => light.map );

		}

		if ( projected ) {

			const inSpotLightMap = lightCoord.mul( 2. ).sub( 1. ).abs().lessThan( 1. ).all();

			lightColor = inSpotLightMap.select( lightColor.mul( projected ), lightColor );

		}

		return { lightColor, lightDirection };

	}
```
</details>


---

## Classes

### `SpotLightNode`

<details><summary>Class Code</summary>

```ts
class SpotLightNode extends AnalyticLightNode {

	static get type() {

		return 'SpotLightNode';

	}

	/**
	 * Constructs a new spot light node.
	 *
	 * @param {?SpotLight} [light=null] - The spot light source.
	 */
	constructor( light = null ) {

		super( light );

		/**
		 * Uniform node representing the cone cosine.
		 *
		 * @type {UniformNode<float>}
		 */
		this.coneCosNode = uniform( 0 ).setGroup( renderGroup );

		/**
		 * Uniform node representing the penumbra cosine.
		 *
		 * @type {UniformNode<float>}
		 */
		this.penumbraCosNode = uniform( 0 ).setGroup( renderGroup );

		/**
		 * Uniform node representing the cutoff distance.
		 *
		 * @type {UniformNode<float>}
		 */
		this.cutoffDistanceNode = uniform( 0 ).setGroup( renderGroup );

		/**
		 * Uniform node representing the decay exponent.
		 *
		 * @type {UniformNode<float>}
		 */
		this.decayExponentNode = uniform( 0 ).setGroup( renderGroup );

		/**
		 * Uniform node representing the light color.
		 *
		 * @type {UniformNode<Color>}
		 */
		this.colorNode = uniform( this.color ).setGroup( renderGroup );

	}

	/**
	 * Overwritten to updated spot light specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( frame ) {

		super.update( frame );

		const { light } = this;

		this.coneCosNode.value = Math.cos( light.angle );
		this.penumbraCosNode.value = Math.cos( light.angle * ( 1 - light.penumbra ) );

		this.cutoffDistanceNode.value = light.distance;
		this.decayExponentNode.value = light.decay;

	}

	/**
	 * Computes the spot attenuation for the given angle.
	 *
	 * @param {NodeBuilder} builder - The node builder.
	 * @param {Node<float>} angleCosine - The angle to compute the spot attenuation for.
	 * @return {Node<float>} The spot attenuation.
	 */
	getSpotAttenuation( builder, angleCosine ) {

		const { coneCosNode, penumbraCosNode } = this;

		return smoothstep( coneCosNode, penumbraCosNode, angleCosine );

	}

	getLightCoord( builder ) {

		const properties = builder.getNodeProperties( this );
		let projectionUV = properties.projectionUV;

		if ( projectionUV === undefined ) {

			projectionUV = lightProjectionUV( this.light, builder.context.positionWorld );

			properties.projectionUV = projectionUV;

		}

		return projectionUV;

	}

	setupDirect( builder ) {

		const { colorNode, cutoffDistanceNode, decayExponentNode, light } = this;

		const lightVector = this.getLightVector( builder );

		const lightDirection = lightVector.normalize();
		const angleCos = lightDirection.dot( lightTargetDirection( light ) );

		const spotAttenuation = this.getSpotAttenuation( builder, angleCos );

		const lightDistance = lightVector.length();

		const lightAttenuation = getDistanceAttenuation( {
			lightDistance,
			cutoffDistance: cutoffDistanceNode,
			decayExponent: decayExponentNode
		} );

		let lightColor = colorNode.mul( spotAttenuation ).mul( lightAttenuation );

		let projected, lightCoord;

		if ( light.colorNode ) {

			lightCoord = this.getLightCoord( builder );
			projected = light.colorNode( lightCoord );

		} else if ( light.map ) {

			lightCoord = this.getLightCoord( builder );
			projected = texture( light.map, lightCoord.xy ).onRenderUpdate( () => light.map );

		}

		if ( projected ) {

			const inSpotLightMap = lightCoord.mul( 2. ).sub( 1. ).abs().lessThan( 1. ).all();

			lightColor = inSpotLightMap.select( lightColor.mul( projected ), lightColor );

		}

		return { lightColor, lightDirection };

	}

}
```
</details>

#### Methods

##### `update(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
update( frame ) {

		super.update( frame );

		const { light } = this;

		this.coneCosNode.value = Math.cos( light.angle );
		this.penumbraCosNode.value = Math.cos( light.angle * ( 1 - light.penumbra ) );

		this.cutoffDistanceNode.value = light.distance;
		this.decayExponentNode.value = light.decay;

	}
```
</details>

##### `getSpotAttenuation(builder: NodeBuilder, angleCosine: any): any`

<details><summary>Code</summary>

```ts
getSpotAttenuation( builder, angleCosine ) {

		const { coneCosNode, penumbraCosNode } = this;

		return smoothstep( coneCosNode, penumbraCosNode, angleCosine );

	}
```
</details>

##### `getLightCoord(builder: any): any`

<details><summary>Code</summary>

```ts
getLightCoord( builder ) {

		const properties = builder.getNodeProperties( this );
		let projectionUV = properties.projectionUV;

		if ( projectionUV === undefined ) {

			projectionUV = lightProjectionUV( this.light, builder.context.positionWorld );

			properties.projectionUV = projectionUV;

		}

		return projectionUV;

	}
```
</details>

##### `setupDirect(builder: any): { lightColor: any; lightDirection: any; }`

<details><summary>Code</summary>

```ts
setupDirect( builder ) {

		const { colorNode, cutoffDistanceNode, decayExponentNode, light } = this;

		const lightVector = this.getLightVector( builder );

		const lightDirection = lightVector.normalize();
		const angleCos = lightDirection.dot( lightTargetDirection( light ) );

		const spotAttenuation = this.getSpotAttenuation( builder, angleCos );

		const lightDistance = lightVector.length();

		const lightAttenuation = getDistanceAttenuation( {
			lightDistance,
			cutoffDistance: cutoffDistanceNode,
			decayExponent: decayExponentNode
		} );

		let lightColor = colorNode.mul( spotAttenuation ).mul( lightAttenuation );

		let projected, lightCoord;

		if ( light.colorNode ) {

			lightCoord = this.getLightCoord( builder );
			projected = light.colorNode( lightCoord );

		} else if ( light.map ) {

			lightCoord = this.getLightCoord( builder );
			projected = texture( light.map, lightCoord.xy ).onRenderUpdate( () => light.map );

		}

		if ( projected ) {

			const inSpotLightMap = lightCoord.mul( 2. ).sub( 1. ).abs().lessThan( 1. ).all();

			lightColor = inSpotLightMap.select( lightColor.mul( projected ), lightColor );

		}

		return { lightColor, lightDirection };

	}
```
</details>


---