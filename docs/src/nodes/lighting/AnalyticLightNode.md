[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AnalyticLightNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/AnalyticLightNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingNode` | `./LightingNode.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `uniform` | `../core/UniformNode.js` |
| `Color` | `../../math/Color.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `shadow` | `./ShadowNode.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `lightViewPosition` | `../accessors/Lights.js` |
| `positionView` | `../accessors/Position.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `shadowColorNode` | `Node` | let/var | `this.shadowColorNode` | ✗ |
| `customShadowNode` | `any` | let/var | `this.light.shadow.shadowNode` | ✗ |
| `shadowNode` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `AnalyticLightNode.getHash(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getHash() {

		return this.light.uuid;

	}
```
</details>

### `AnalyticLightNode.getLightVector(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * Returns a node representing a direction vector which points from the current
	 * position in view space to the light's position in view space.
	 *
	 * @param {NodeBuilder} builder - The builder object used for setting up the light.
	 * @return {Node<vec3>} The light vector node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

**Calls:**

- `lightViewPosition( this.light ).sub`

<details><summary>Code</summary>

```typescript
getLightVector( builder ) {

		return lightViewPosition( this.light ).sub( builder.context.positionView || positionView );

	}
```
</details>

### `AnalyticLightNode.setupDirect(): any`

**JSDoc:**
```typescript
/**
	 * Sets up the direct lighting for the analytic light node.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The builder object used for setting up the light.
	 * @return {Object|undefined} The direct light data (color and direction).
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
setupDirect( /*builder*/ ) { }
```
</details>

### `AnalyticLightNode.setupDirectRectArea(): any`

**JSDoc:**
```typescript
/**
	 * Sets up the direct rect area lighting for the analytic light node.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The builder object used for setting up the light.
	 * @return {Object|undefined} The direct rect area light data.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
setupDirectRectArea( /*builder*/ ) { }
```
</details>

### `AnalyticLightNode.setupShadowNode(): ShadowNode`

**JSDoc:**
```typescript
/**
	 * Setups the shadow node for this light. The method exists so concrete light classes
	 * can setup different types of shadow nodes.
	 *
	 * @return {ShadowNode} The created shadow node.
	 */
```

**Returns:** `ShadowNode`

**Calls:**

- `shadow (from ./ShadowNode.js)`

<details><summary>Code</summary>

```typescript
setupShadowNode() {

		return shadow( this.light );

	}
```
</details>

### `AnalyticLightNode.setupShadow(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Setups the shadow for this light. This method is only executed if the light
	 * cast shadows and the current build object receives shadows. It incorporates
	 * shadows into the lighting computation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`
- `this.setupShadowNode`
- `this.colorNode.mul`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
setupShadow( builder ) {

		const { renderer } = builder;

		if ( renderer.shadowMap.enabled === false ) return;

		let shadowColorNode = this.shadowColorNode;

		if ( shadowColorNode === null ) {

			const customShadowNode = this.light.shadow.shadowNode;

			let shadowNode;

			if ( customShadowNode !== undefined ) {

				shadowNode = nodeObject( customShadowNode );

			} else {

				shadowNode = this.setupShadowNode();

			}

			this.shadowNode = shadowNode;

			this.shadowColorNode = shadowColorNode = this.colorNode.mul( shadowNode );

			this.baseColorNode = this.colorNode;

		}

		//

		this.colorNode = shadowColorNode;

	}
```
</details>

### `AnalyticLightNode.setup(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Unlike most other nodes, lighting nodes do not return a output node in {@link Node#setup}.
	 * The main purpose of lighting nodes is to configure the current {@link LightingModel} and/or
	 * invocate the respective interface methods.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `this.setupShadow`
- `this.shadowNode.dispose`
- `this.setupDirect`
- `this.setupDirectRectArea`
- `builder.lightsNode.setupDirectLight`
- `builder.lightsNode.setupDirectRectAreaLight`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		this.colorNode = this.baseColorNode || this.colorNode;

		if ( this.light.castShadow ) {

			if ( builder.object.receiveShadow ) {

				this.setupShadow( builder );

			}

		} else if ( this.shadowNode !== null ) {

			this.shadowNode.dispose();
			this.shadowNode = null;
			this.shadowColorNode = null;

		}

		const directLightData = this.setupDirect( builder );
		const directRectAreaLightData = this.setupDirectRectArea( builder );

		if ( directLightData ) {

			builder.lightsNode.setupDirectLight( builder, this, directLightData );

		}

		if ( directRectAreaLightData ) {

			builder.lightsNode.setupDirectRectAreaLight( builder, this, directRectAreaLightData );

		}

	}
```
</details>

### `AnalyticLightNode.update(): void`

**JSDoc:**
```typescript
/**
	 * The update method is used to update light uniforms per frame.
	 * Potentially overwritten in concrete light nodes to update light
	 * specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Returns:** `void`

**Calls:**

- `this.color.copy( light.color ).multiplyScalar`

<details><summary>Code</summary>

```typescript
update( /*frame*/ ) {

		const { light } = this;

		this.color.copy( light.color ).multiplyScalar( light.intensity );

	}
```
</details>


---

## Classes

### `AnalyticLightNode`

<details><summary>Class Code</summary>

```ts
class AnalyticLightNode extends LightingNode {

	static get type() {

		return 'AnalyticLightNode';

	}

	/**
	 * Constructs a new analytic light node.
	 *
	 * @param {?Light} [light=null] - The light source.
	 */
	constructor( light = null ) {

		super();

		/**
		 * The light source.
		 *
		 * @type {?Light}
		 * @default null
		 */
		this.light = light;

		/**
		 * The light's color value.
		 *
		 * @type {Color}
		 */
		this.color = new Color();

		/**
		 * The light's color node. Points to `colorNode` of the light source, if set. Otherwise
		 * it creates a uniform node based on {@link AnalyticLightNode#color}.
		 *
		 * @type {Node}
		 */
		this.colorNode = ( light && light.colorNode ) || uniform( this.color ).setGroup( renderGroup );

		/**
		 * This property is used to retain a reference to the original value of {@link AnalyticLightNode#colorNode}.
		 * The final color node is represented by a different node when using shadows.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.baseColorNode = null;

		/**
		 * Represents the light's shadow.
		 *
		 * @type {?ShadowNode}
   		 * @default null
		 */
		this.shadowNode = null;

		/**
		 * Represents the light's shadow color.
		 *
		 * @type {?Node}
   		 * @default null
		 */
		this.shadowColorNode = null;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isAnalyticLightNode = true;

		/**
		 * Overwritten since analytic light nodes are updated
		 * once per frame.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateType = NodeUpdateType.FRAME;

	}

	getHash() {

		return this.light.uuid;

	}

	/**
	 * Returns a node representing a direction vector which points from the current
	 * position in view space to the light's position in view space.
	 *
	 * @param {NodeBuilder} builder - The builder object used for setting up the light.
	 * @return {Node<vec3>} The light vector node.
	 */
	getLightVector( builder ) {

		return lightViewPosition( this.light ).sub( builder.context.positionView || positionView );

	}

	/**
	 * Sets up the direct lighting for the analytic light node.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The builder object used for setting up the light.
	 * @return {Object|undefined} The direct light data (color and direction).
	 */
	setupDirect( /*builder*/ ) { }

	/**
	 * Sets up the direct rect area lighting for the analytic light node.
	 *
	 * @abstract
	 * @param {NodeBuilder} builder - The builder object used for setting up the light.
	 * @return {Object|undefined} The direct rect area light data.
	 */
	setupDirectRectArea( /*builder*/ ) { }

	/**
	 * Setups the shadow node for this light. The method exists so concrete light classes
	 * can setup different types of shadow nodes.
	 *
	 * @return {ShadowNode} The created shadow node.
	 */
	setupShadowNode() {

		return shadow( this.light );

	}

	/**
	 * Setups the shadow for this light. This method is only executed if the light
	 * cast shadows and the current build object receives shadows. It incorporates
	 * shadows into the lighting computation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setupShadow( builder ) {

		const { renderer } = builder;

		if ( renderer.shadowMap.enabled === false ) return;

		let shadowColorNode = this.shadowColorNode;

		if ( shadowColorNode === null ) {

			const customShadowNode = this.light.shadow.shadowNode;

			let shadowNode;

			if ( customShadowNode !== undefined ) {

				shadowNode = nodeObject( customShadowNode );

			} else {

				shadowNode = this.setupShadowNode();

			}

			this.shadowNode = shadowNode;

			this.shadowColorNode = shadowColorNode = this.colorNode.mul( shadowNode );

			this.baseColorNode = this.colorNode;

		}

		//

		this.colorNode = shadowColorNode;

	}

	/**
	 * Unlike most other nodes, lighting nodes do not return a output node in {@link Node#setup}.
	 * The main purpose of lighting nodes is to configure the current {@link LightingModel} and/or
	 * invocate the respective interface methods.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setup( builder ) {

		this.colorNode = this.baseColorNode || this.colorNode;

		if ( this.light.castShadow ) {

			if ( builder.object.receiveShadow ) {

				this.setupShadow( builder );

			}

		} else if ( this.shadowNode !== null ) {

			this.shadowNode.dispose();
			this.shadowNode = null;
			this.shadowColorNode = null;

		}

		const directLightData = this.setupDirect( builder );
		const directRectAreaLightData = this.setupDirectRectArea( builder );

		if ( directLightData ) {

			builder.lightsNode.setupDirectLight( builder, this, directLightData );

		}

		if ( directRectAreaLightData ) {

			builder.lightsNode.setupDirectRectAreaLight( builder, this, directRectAreaLightData );

		}

	}

	/**
	 * The update method is used to update light uniforms per frame.
	 * Potentially overwritten in concrete light nodes to update light
	 * specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( /*frame*/ ) {

		const { light } = this;

		this.color.copy( light.color ).multiplyScalar( light.intensity );

	}

}
```
</details>

#### Methods

##### `getHash(): any`

<details><summary>Code</summary>

```ts
getHash() {

		return this.light.uuid;

	}
```
</details>

##### `getLightVector(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
getLightVector( builder ) {

		return lightViewPosition( this.light ).sub( builder.context.positionView || positionView );

	}
```
</details>

##### `setupDirect(): any`

<details><summary>Code</summary>

```ts
setupDirect( /*builder*/ ) { }
```
</details>

##### `setupDirectRectArea(): any`

<details><summary>Code</summary>

```ts
setupDirectRectArea( /*builder*/ ) { }
```
</details>

##### `setupShadowNode(): ShadowNode`

<details><summary>Code</summary>

```ts
setupShadowNode() {

		return shadow( this.light );

	}
```
</details>

##### `setupShadow(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
setupShadow( builder ) {

		const { renderer } = builder;

		if ( renderer.shadowMap.enabled === false ) return;

		let shadowColorNode = this.shadowColorNode;

		if ( shadowColorNode === null ) {

			const customShadowNode = this.light.shadow.shadowNode;

			let shadowNode;

			if ( customShadowNode !== undefined ) {

				shadowNode = nodeObject( customShadowNode );

			} else {

				shadowNode = this.setupShadowNode();

			}

			this.shadowNode = shadowNode;

			this.shadowColorNode = shadowColorNode = this.colorNode.mul( shadowNode );

			this.baseColorNode = this.colorNode;

		}

		//

		this.colorNode = shadowColorNode;

	}
```
</details>

##### `setup(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		this.colorNode = this.baseColorNode || this.colorNode;

		if ( this.light.castShadow ) {

			if ( builder.object.receiveShadow ) {

				this.setupShadow( builder );

			}

		} else if ( this.shadowNode !== null ) {

			this.shadowNode.dispose();
			this.shadowNode = null;
			this.shadowColorNode = null;

		}

		const directLightData = this.setupDirect( builder );
		const directRectAreaLightData = this.setupDirectRectArea( builder );

		if ( directLightData ) {

			builder.lightsNode.setupDirectLight( builder, this, directLightData );

		}

		if ( directRectAreaLightData ) {

			builder.lightsNode.setupDirectRectAreaLight( builder, this, directRectAreaLightData );

		}

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update( /*frame*/ ) {

		const { light } = this;

		this.color.copy( light.color ).multiplyScalar( light.intensity );

	}
```
</details>


---