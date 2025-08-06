[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `NodeBuilderState.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/nodes/NodeBuilderState.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BindGroup` | `../BindGroup.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `bindings` | `any[]` | let/var | `[]` | ✗ |
| `shared` | `any` | let/var | `instanceGroup.bindings[ 0 ].groupNode.shared` | ✗ |
| `bindingsGroup` | `BindGroup` | let/var | `new BindGroup( instanceGroup.name, [], instanceGroup.index, instanceGroup )` | ✗ |


---

## Functions

### `NodeBuilderState.createBindings(): BindGroup[]`

**JSDoc:**
```typescript
/**
	 * This method is used to create a array of bind groups based
	 * on the existing bind groups of this state. Shared groups are
	 * not cloned.
	 *
	 * @return {Array<BindGroup>} A array of bind groups.
	 */
```

**Returns:** `BindGroup[]`

**Calls:**

- `bindings.push`
- `bindingsGroup.bindings.push`
- `instanceBinding.clone`

<details><summary>Code</summary>

```typescript
createBindings() {

		const bindings = [];

		for ( const instanceGroup of this.bindings ) {

			const shared = instanceGroup.bindings[ 0 ].groupNode.shared; // All bindings in the group must have the same groupNode.

			if ( shared !== true ) {

				const bindingsGroup = new BindGroup( instanceGroup.name, [], instanceGroup.index, instanceGroup );
				bindings.push( bindingsGroup );

				for ( const instanceBinding of instanceGroup.bindings ) {

					bindingsGroup.bindings.push( instanceBinding.clone() );

				}

			} else {

				bindings.push( instanceGroup );

			}

		}

		return bindings;

	}
```
</details>


---

## Classes

### `NodeBuilderState`

<details><summary>Class Code</summary>

```ts
class NodeBuilderState {

	/**
	 * Constructs a new node builder state.
	 *
	 * @param {string} vertexShader - The native vertex shader code.
	 * @param {string} fragmentShader - The native fragment shader code.
	 * @param {string} computeShader - The native compute shader code.
	 * @param {Array<NodeAttribute>} nodeAttributes - An array of node attributes.
	 * @param {Array<BindGroup>} bindings - An array of bind groups.
	 * @param {Array<Node>} updateNodes - An array of nodes that implement their `update()` method.
	 * @param {Array<Node>} updateBeforeNodes - An array of nodes that implement their `updateBefore()` method.
	 * @param {Array<Node>} updateAfterNodes - An array of nodes that implement their `updateAfter()` method.
	 * @param {NodeMaterialObserver} observer - A node material observer.
	 * @param {Array<Object>} transforms - An array with transform attribute objects. Only relevant when using compute shaders with WebGL 2.
	 */
	constructor( vertexShader, fragmentShader, computeShader, nodeAttributes, bindings, updateNodes, updateBeforeNodes, updateAfterNodes, observer, transforms = [] ) {

		/**
		 * The native vertex shader code.
		 *
		 * @type {string}
		 */
		this.vertexShader = vertexShader;

		/**
		 * The native fragment shader code.
		 *
		 * @type {string}
		 */
		this.fragmentShader = fragmentShader;

		/**
		 * The native compute shader code.
		 *
		 * @type {string}
		 */
		this.computeShader = computeShader;

		/**
		 * An array with transform attribute objects.
		 * Only relevant when using compute shaders with WebGL 2.
		 *
		 * @type {Array<Object>}
		 */
		this.transforms = transforms;

		/**
		 * An array of node attributes representing
		 * the attributes of the shaders.
		 *
		 * @type {Array<NodeAttribute>}
		 */
		this.nodeAttributes = nodeAttributes;

		/**
		 * An array of bind groups representing the uniform or storage
		 * buffers, texture or samplers of the shader.
		 *
		 * @type {Array<BindGroup>}
		 */
		this.bindings = bindings;

		/**
		 * An array of nodes that implement their `update()` method.
		 *
		 * @type {Array<Node>}
		 */
		this.updateNodes = updateNodes;

		/**
		 * An array of nodes that implement their `updateBefore()` method.
		 *
		 * @type {Array<Node>}
		 */
		this.updateBeforeNodes = updateBeforeNodes;

		/**
		 * An array of nodes that implement their `updateAfter()` method.
		 *
		 * @type {Array<Node>}
		 */
		this.updateAfterNodes = updateAfterNodes;

		/**
		 * A node material observer.
		 *
		 * @type {NodeMaterialObserver}
		 */
		this.observer = observer;

		/**
		 * How often this state is used by render objects.
		 *
		 * @type {number}
		 */
		this.usedTimes = 0;

	}

	/**
	 * This method is used to create a array of bind groups based
	 * on the existing bind groups of this state. Shared groups are
	 * not cloned.
	 *
	 * @return {Array<BindGroup>} A array of bind groups.
	 */
	createBindings() {

		const bindings = [];

		for ( const instanceGroup of this.bindings ) {

			const shared = instanceGroup.bindings[ 0 ].groupNode.shared; // All bindings in the group must have the same groupNode.

			if ( shared !== true ) {

				const bindingsGroup = new BindGroup( instanceGroup.name, [], instanceGroup.index, instanceGroup );
				bindings.push( bindingsGroup );

				for ( const instanceBinding of instanceGroup.bindings ) {

					bindingsGroup.bindings.push( instanceBinding.clone() );

				}

			} else {

				bindings.push( instanceGroup );

			}

		}

		return bindings;

	}

}
```
</details>

#### Methods

##### `createBindings(): BindGroup[]`

<details><summary>Code</summary>

```ts
createBindings() {

		const bindings = [];

		for ( const instanceGroup of this.bindings ) {

			const shared = instanceGroup.bindings[ 0 ].groupNode.shared; // All bindings in the group must have the same groupNode.

			if ( shared !== true ) {

				const bindingsGroup = new BindGroup( instanceGroup.name, [], instanceGroup.index, instanceGroup );
				bindings.push( bindingsGroup );

				for ( const instanceBinding of instanceGroup.bindings ) {

					bindingsGroup.bindings.push( instanceBinding.clone() );

				}

			} else {

				bindings.push( instanceGroup );

			}

		}

		return bindings;

	}
```
</details>


---