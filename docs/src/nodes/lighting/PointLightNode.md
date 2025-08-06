[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PointLightNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/PointLightNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnalyticLightNode` | `./AnalyticLightNode.js` |
| `getDistanceAttenuation` | `./LightUtils.js` |
| `uniform` | `../core/UniformNode.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `pointShadow` | `./PointShadowNode.js` |


---

## Functions

### `directPointLight({ color, lightVector, cutoffDistance, decayExponent }: any): { lightDirection: any; lightColor: any; }`

**Parameters:**

- **`{ color, lightVector, cutoffDistance, decayExponent }`** `any`

**Returns:** `{ lightDirection: any; lightColor: any; }`

**Calls:**

- `lightVector.normalize`
- `lightVector.length`
- `getDistanceAttenuation (from ./LightUtils.js)`
- `color.mul`

<details><summary>Code</summary>

```typescript
( { color, lightVector, cutoffDistance, decayExponent } ) => {

	const lightDirection = lightVector.normalize();
	const lightDistance = lightVector.length();

	const attenuation = getDistanceAttenuation( {
		lightDistance,
		cutoffDistance,
		decayExponent
	} );

	const lightColor = color.mul( attenuation );

	return { lightDirection, lightColor };

}
```
</details>

### `PointLightNode.update(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Overwritten to updated point light specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `super.update`

<details><summary>Code</summary>

```typescript
update( frame ) {

		const { light } = this;

		super.update( frame );

		this.cutoffDistanceNode.value = light.distance;
		this.decayExponentNode.value = light.decay;

	}
```
</details>

### `PointLightNode.setupShadowNode(): PointShadowNode`

**JSDoc:**
```typescript
/**
	 * Overwritten to setup point light specific shadow.
	 *
	 * @return {PointShadowNode}
	 */
```

**Returns:** `PointShadowNode`

**Calls:**

- `pointShadow (from ./PointShadowNode.js)`

<details><summary>Code</summary>

```typescript
setupShadowNode() {

		return pointShadow( this.light );

	}
```
</details>

### `PointLightNode.setupDirect(builder: any): { lightDirection: any; lightColor: any; }`

**Parameters:**

- **`builder`** `any`

**Returns:** `{ lightDirection: any; lightColor: any; }`

**Calls:**

- `directPointLight`
- `this.getLightVector`

<details><summary>Code</summary>

```typescript
setupDirect( builder ) {

		return directPointLight( {
			color: this.colorNode,
			lightVector: this.getLightVector( builder ),
			cutoffDistance: this.cutoffDistanceNode,
			decayExponent: this.decayExponentNode
		} );

	}
```
</details>


---

## Classes

### `PointLightNode`

<details><summary>Class Code</summary>

```ts
class PointLightNode extends AnalyticLightNode {

	static get type() {

		return 'PointLightNode';

	}

	/**
	 * Constructs a new point light node.
	 *
	 * @param {?PointLight} [light=null] - The point light source.
	 */
	constructor( light = null ) {

		super( light );

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
		this.decayExponentNode = uniform( 2 ).setGroup( renderGroup );

	}

	/**
	 * Overwritten to updated point light specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( frame ) {

		const { light } = this;

		super.update( frame );

		this.cutoffDistanceNode.value = light.distance;
		this.decayExponentNode.value = light.decay;

	}

	/**
	 * Overwritten to setup point light specific shadow.
	 *
	 * @return {PointShadowNode}
	 */
	setupShadowNode() {

		return pointShadow( this.light );

	}

	setupDirect( builder ) {

		return directPointLight( {
			color: this.colorNode,
			lightVector: this.getLightVector( builder ),
			cutoffDistance: this.cutoffDistanceNode,
			decayExponent: this.decayExponentNode
		} );

	}

}
```
</details>

#### Methods

##### `update(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
update( frame ) {

		const { light } = this;

		super.update( frame );

		this.cutoffDistanceNode.value = light.distance;
		this.decayExponentNode.value = light.decay;

	}
```
</details>

##### `setupShadowNode(): PointShadowNode`

<details><summary>Code</summary>

```ts
setupShadowNode() {

		return pointShadow( this.light );

	}
```
</details>

##### `setupDirect(builder: any): { lightDirection: any; lightColor: any; }`

<details><summary>Code</summary>

```ts
setupDirect( builder ) {

		return directPointLight( {
			color: this.colorNode,
			lightVector: this.getLightVector( builder ),
			cutoffDistance: this.cutoffDistanceNode,
			decayExponent: this.decayExponentNode
		} );

	}
```
</details>


---