[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `HemisphereLightNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/HemisphereLightNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnalyticLightNode` | `./AnalyticLightNode.js` |
| `uniform` | `../core/UniformNode.js` |
| `mix` | `../math/MathNode.js` |
| `normalWorld` | `../accessors/Normal.js` |
| `lightPosition` | `../accessors/Lights.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `Color` | `../../math/Color.js` |


---

## Functions

### `HemisphereLightNode.update(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Overwritten to updated hemisphere light specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `super.update`
- `this.groundColorNode.value.copy( light.groundColor ).multiplyScalar`

<details><summary>Code</summary>

```typescript
update( frame ) {

		const { light } = this;

		super.update( frame );

		this.lightPositionNode.object3d = light;

		this.groundColorNode.value.copy( light.groundColor ).multiplyScalar( light.intensity );

	}
```
</details>

### `HemisphereLightNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `normalWorld.dot`
- `dotNL.mul( 0.5 ).add`
- `mix (from ../math/MathNode.js)`
- `builder.context.irradiance.addAssign`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const { colorNode, groundColorNode, lightDirectionNode } = this;

		const dotNL = normalWorld.dot( lightDirectionNode );
		const hemiDiffuseWeight = dotNL.mul( 0.5 ).add( 0.5 );

		const irradiance = mix( groundColorNode, colorNode, hemiDiffuseWeight );

		builder.context.irradiance.addAssign( irradiance );

	}
```
</details>


---

## Classes

### `HemisphereLightNode`

<details><summary>Class Code</summary>

```ts
class HemisphereLightNode extends AnalyticLightNode {

	static get type() {

		return 'HemisphereLightNode';

	}

	/**
	 * Constructs a new hemisphere light node.
	 *
	 * @param {?HemisphereLight} [light=null] - The hemisphere light source.
	 */
	constructor( light = null ) {

		super( light );

		/**
		 * Uniform node representing the light's position.
		 *
		 * @type {UniformNode<vec3>}
		 */
		this.lightPositionNode = lightPosition( light );

		/**
		 * A node representing the light's direction.
		 *
		 * @type {Node<vec3>}
		 */
		this.lightDirectionNode = this.lightPositionNode.normalize();

		/**
		 * Uniform node representing the light's ground color.
		 *
		 * @type {UniformNode<vec3>}
		 */
		this.groundColorNode = uniform( new Color() ).setGroup( renderGroup );

	}

	/**
	 * Overwritten to updated hemisphere light specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( frame ) {

		const { light } = this;

		super.update( frame );

		this.lightPositionNode.object3d = light;

		this.groundColorNode.value.copy( light.groundColor ).multiplyScalar( light.intensity );

	}

	setup( builder ) {

		const { colorNode, groundColorNode, lightDirectionNode } = this;

		const dotNL = normalWorld.dot( lightDirectionNode );
		const hemiDiffuseWeight = dotNL.mul( 0.5 ).add( 0.5 );

		const irradiance = mix( groundColorNode, colorNode, hemiDiffuseWeight );

		builder.context.irradiance.addAssign( irradiance );

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

		this.lightPositionNode.object3d = light;

		this.groundColorNode.value.copy( light.groundColor ).multiplyScalar( light.intensity );

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const { colorNode, groundColorNode, lightDirectionNode } = this;

		const dotNL = normalWorld.dot( lightDirectionNode );
		const hemiDiffuseWeight = dotNL.mul( 0.5 ).add( 0.5 );

		const irradiance = mix( groundColorNode, colorNode, hemiDiffuseWeight );

		builder.context.irradiance.addAssign( irradiance );

	}
```
</details>


---