[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `FilmNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/FilmNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `three/webgpu` |
| `rand` | `three/tsl` |
| `Fn` | `three/tsl` |
| `fract` | `three/tsl` |
| `time` | `three/tsl` |
| `uv` | `three/tsl` |
| `clamp` | `three/tsl` |
| `mix` | `three/tsl` |
| `vec4` | `three/tsl` |
| `nodeProxy` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `uvNode` | `any` | let/var | `this.uvNode \|\| uv()` | ✗ |
| `base` | `any` | let/var | `this.inputNode.rgb` | ✗ |


---

## Functions

### `FilmNode.setup(): ShaderCallNodeInternal`

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

- `uv (from three/tsl)`
- `Fn (from three/tsl)`
- `rand (from three/tsl)`
- `fract (from three/tsl)`
- `uvNode.add`
- `base.add`
- `base.mul`
- `clamp (from three/tsl)`
- `noise.add`
- `mix (from three/tsl)`
- `vec4 (from three/tsl)`
- `film`

<details><summary>Code</summary>

```typescript
setup( /* builder */ ) {

		const uvNode = this.uvNode || uv();

		const film = Fn( () => {

			const base = this.inputNode.rgb;
			const noise = rand( fract( uvNode.add( time ) ) );

			let color = base.add( base.mul( clamp( noise.add( 0.1 ), 0, 1 ) ) );

			if ( this.intensityNode !== null ) {

				color = mix( base, color, this.intensityNode );

			}

			return vec4( color, this.inputNode.a );

		} );

		const outputNode = film();

		return outputNode;

	}
```
</details>


---

## Classes

### `FilmNode`

<details><summary>Class Code</summary>

```ts
class FilmNode extends TempNode {

	static get type() {

		return 'FilmNode';

	}

	/**
	 * Constructs a new film node.
	 *
	 * @param {Node} inputNode - The node that represents the input of the effect.
	 * @param {?Node<float>} [intensityNode=null] - A node that represents the effect's intensity.
	 * @param {?Node<vec2>} [uvNode=null] - A node that allows to pass custom (e.g. animated) uv data.
	 */
	constructor( inputNode, intensityNode = null, uvNode = null ) {

		super( 'vec4' );

		/**
		 * The node that represents the input of the effect.
		 *
		 * @type {Node}
		 */
		this.inputNode = inputNode;

		/**
		 * A node that represents the effect's intensity.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.intensityNode = intensityNode;

		/**
		 * A node that allows to pass custom (e.g. animated) uv data.
		 *
		 * @type {?Node<vec2>}
		 * @default null
		 */
		this.uvNode = uvNode;

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
	setup( /* builder */ ) {

		const uvNode = this.uvNode || uv();

		const film = Fn( () => {

			const base = this.inputNode.rgb;
			const noise = rand( fract( uvNode.add( time ) ) );

			let color = base.add( base.mul( clamp( noise.add( 0.1 ), 0, 1 ) ) );

			if ( this.intensityNode !== null ) {

				color = mix( base, color, this.intensityNode );

			}

			return vec4( color, this.inputNode.a );

		} );

		const outputNode = film();

		return outputNode;

	}

}
```
</details>

#### Methods

##### `setup(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup( /* builder */ ) {

		const uvNode = this.uvNode || uv();

		const film = Fn( () => {

			const base = this.inputNode.rgb;
			const noise = rand( fract( uvNode.add( time ) ) );

			let color = base.add( base.mul( clamp( noise.add( 0.1 ), 0, 1 ) ) );

			if ( this.intensityNode !== null ) {

				color = mix( base, color, this.intensityNode );

			}

			return vec4( color, this.inputNode.a );

		} );

		const outputNode = film();

		return outputNode;

	}
```
</details>


---