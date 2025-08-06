[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `DotScreenNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/DotScreenNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `uv` | `three/tsl` |
| `uniform` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `sin` | `three/tsl` |
| `cos` | `three/tsl` |
| `add` | `three/tsl` |
| `vec4` | `three/tsl` |
| `screenSize` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `inputNode` | `Node` | let/var | `this.inputNode` | ✗ |
| `color` | `Node` | let/var | `inputNode` | ✗ |


---

## Functions

### `DotScreenNode.setup(): ShaderCallNodeInternal`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
```

**Returns:** `ShaderCallNodeInternal`

**Calls:**

- `Fn (from three/tsl)`
- `sin (from three/tsl)`
- `cos (from three/tsl)`
- `uv().mul`
- `vec2( c.mul( tex.x ).sub( s.mul( tex.y ) ), s.mul( tex.x ).add( c.mul( tex.y ) ) ).mul`
- `sin( point.x ).mul( sin( point.y ) ).mul`
- `add( color.r, color.g, color.b ).div`
- `vec4 (from three/tsl)`
- `vec3 (from three/tsl)`
- `average.mul( 10 ).sub( 5 ).add`
- `pattern`
- `dotScreen`

<details><summary>Code</summary>

```typescript
setup() {

		const inputNode = this.inputNode;

		const pattern = Fn( () => {

			const s = sin( this.angle );
			const c = cos( this.angle );

			const tex = uv().mul( screenSize );
			const point = vec2( c.mul( tex.x ).sub( s.mul( tex.y ) ), s.mul( tex.x ).add( c.mul( tex.y ) ) ).mul( this.scale );

			return sin( point.x ).mul( sin( point.y ) ).mul( 4 );

		} );

		const dotScreen = Fn( () => {

			const color = inputNode;

			const average = add( color.r, color.g, color.b ).div( 3 );

			return vec4( vec3( average.mul( 10 ).sub( 5 ).add( pattern() ) ), color.a );

		} );

		const outputNode = dotScreen();

		return outputNode;

	}
```
</details>

### `dotScreen(node: any, angle: number, scale: number): DotScreenNode`

**Parameters:**

- **`node`** `any`
- **`angle`** `number`
- **`scale`** `number`

**Returns:** `DotScreenNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, angle, scale ) => nodeObject( new DotScreenNode( nodeObject( node ), angle, scale ) )
```
</details>


---

## Classes

### `DotScreenNode`

<details><summary>Class Code</summary>

```ts
class DotScreenNode extends TempNode {

	static get type() {

		return 'DotScreenNode';

	}

	/**
	 * Constructs a new dot screen node.
	 *
	 * @param {Node} inputNode - The node that represents the input of the effect.
	 * @param {number} [angle=1.57] - The rotation of the effect in radians.
	 * @param {number} [scale=1] - The scale of the effect. A higher value means smaller dots.
	 */
	constructor( inputNode, angle = 1.57, scale = 1 ) {

		super( 'vec4' );

		/**
		 * The node that represents the input of the effect.
		 *
		 * @type {Node}
		 */
		this.inputNode = inputNode;

		/**
		 * A uniform node that represents the rotation of the effect in radians.
		 *
		 * @type {UniformNode<float>}
		 */
		this.angle = uniform( angle );

		/**
		 * A uniform node that represents the scale of the effect. A higher value means smaller dots.
		 *
		 * @type {UniformNode<float>}
		 */
		this.scale = uniform( scale );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
	setup() {

		const inputNode = this.inputNode;

		const pattern = Fn( () => {

			const s = sin( this.angle );
			const c = cos( this.angle );

			const tex = uv().mul( screenSize );
			const point = vec2( c.mul( tex.x ).sub( s.mul( tex.y ) ), s.mul( tex.x ).add( c.mul( tex.y ) ) ).mul( this.scale );

			return sin( point.x ).mul( sin( point.y ) ).mul( 4 );

		} );

		const dotScreen = Fn( () => {

			const color = inputNode;

			const average = add( color.r, color.g, color.b ).div( 3 );

			return vec4( vec3( average.mul( 10 ).sub( 5 ).add( pattern() ) ), color.a );

		} );

		const outputNode = dotScreen();

		return outputNode;

	}

}
```
</details>

#### Methods

##### `setup(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup() {

		const inputNode = this.inputNode;

		const pattern = Fn( () => {

			const s = sin( this.angle );
			const c = cos( this.angle );

			const tex = uv().mul( screenSize );
			const point = vec2( c.mul( tex.x ).sub( s.mul( tex.y ) ), s.mul( tex.x ).add( c.mul( tex.y ) ) ).mul( this.scale );

			return sin( point.x ).mul( sin( point.y ) ).mul( 4 );

		} );

		const dotScreen = Fn( () => {

			const color = inputNode;

			const average = add( color.r, color.g, color.b ).div( 3 );

			return vec4( vec3( average.mul( 10 ).sub( 5 ).add( pattern() ) ), color.a );

		} );

		const outputNode = dotScreen();

		return outputNode;

	}
```
</details>


---