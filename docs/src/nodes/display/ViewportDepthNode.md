[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ViewportDepthNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/ViewportDepthNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `float` | `../tsl/TSLBase.js` |
| `log` | `../tsl/TSLBase.js` |
| `log2` | `../tsl/TSLBase.js` |
| `nodeImmutable` | `../tsl/TSLBase.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `cameraNear` | `../accessors/Camera.js` |
| `cameraFar` | `../accessors/Camera.js` |
| `positionView` | `../accessors/Position.js` |
| `viewportDepthTexture` | `./ViewportDepthTextureNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `value` | `Node` | let/var | `this.valueNode` | ✗ |
| `node` | `any` | let/var | `null` | ✗ |


---

## Functions

### `ViewportDepthNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getFragDepth`
- `super.generate`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const { scope } = this;

		if ( scope === ViewportDepthNode.DEPTH_BASE ) {

			return builder.getFragDepth();

		}

		return super.generate( builder );

	}
```
</details>

### `ViewportDepthNode.setup({ camera }: any): any`

**Parameters:**

- **`{ camera }`** `any`

**Returns:** `any`

**Calls:**

- `depthBase().assign`
- `viewZToPerspectiveDepth`
- `viewZToOrthographicDepth`
- `perspectiveDepthToViewZ`

<details><summary>Code</summary>

```typescript
setup( { camera } ) {

		const { scope } = this;
		const value = this.valueNode;

		let node = null;

		if ( scope === ViewportDepthNode.DEPTH_BASE ) {

			if ( value !== null ) {

 				node = depthBase().assign( value );

			}

		} else if ( scope === ViewportDepthNode.DEPTH ) {

			if ( camera.isPerspectiveCamera ) {

				node = viewZToPerspectiveDepth( positionView.z, cameraNear, cameraFar );

			} else {

				node = viewZToOrthographicDepth( positionView.z, cameraNear, cameraFar );

			}

		} else if ( scope === ViewportDepthNode.LINEAR_DEPTH ) {

			if ( value !== null ) {

				if ( camera.isPerspectiveCamera ) {

					const viewZ = perspectiveDepthToViewZ( value, cameraNear, cameraFar );

					node = viewZToOrthographicDepth( viewZ, cameraNear, cameraFar );

				} else {

					node = value;

				}

			} else {

				node = viewZToOrthographicDepth( positionView.z, cameraNear, cameraFar );

			}

		}

		return node;

	}
```
</details>

### `viewZToOrthographicDepth(viewZ: any, near: any, far: any): any`

**Parameters:**

- **`viewZ`** `any`
- **`near`** `any`
- **`far`** `any`

**Returns:** `any`

**Calls:**

- `viewZ.add( near ).div`

<details><summary>Code</summary>

```typescript
( viewZ, near, far ) => viewZ.add( near ).div( near.sub( far ) )
```
</details>

### `orthographicDepthToViewZ(depth: any, near: any, far: any): any`

**Parameters:**

- **`depth`** `any`
- **`near`** `any`
- **`far`** `any`

**Returns:** `any`

**Calls:**

- `near.sub( far ).mul( depth ).sub`

<details><summary>Code</summary>

```typescript
( depth, near, far ) => near.sub( far ).mul( depth ).sub( near )
```
</details>

### `viewZToPerspectiveDepth(viewZ: any, near: any, far: any): any`

**Parameters:**

- **`viewZ`** `any`
- **`near`** `any`
- **`far`** `any`

**Returns:** `any`

**Calls:**

- `near.add( viewZ ).mul( far ).div`

<details><summary>Code</summary>

```typescript
( viewZ, near, far ) => near.add( viewZ ).mul( far ).div( far.sub( near ).mul( viewZ ) )
```
</details>

### `perspectiveDepthToViewZ(depth: any, near: any, far: any): any`

**Parameters:**

- **`depth`** `any`
- **`near`** `any`
- **`far`** `any`

**Returns:** `any`

**Calls:**

- `near.mul( far ).div`

<details><summary>Code</summary>

```typescript
( depth, near, far ) => near.mul( far ).div( far.sub( near ).mul( depth ).sub( far ) )
```
</details>

### `viewZToLogarithmicDepth(viewZ: any, near: any, far: any): any`

**Parameters:**

- **`viewZ`** `any`
- **`near`** `any`
- **`far`** `any`

**Returns:** `any`

**Calls:**

- `near.max( 1e-6 ).toVar`
- `log2 (from ../tsl/TSLBase.js)`
- `viewZ.negate().div`
- `far.div`
- `numerator.div`

**Internal Comments:**
```
// NOTE: viewZ must be negative--see explanation at the end of this comment block. (x3)
// The final logarithmic depth formula used here is adapted from one described in an (x3)
// article by Thatcher Ulrich (see http://tulrich.com/geekstuff/log_depth_buffer.txt), (x3)
// which was an improvement upon an earlier formula one described in an (x3)
// Outerra article (https://outerra.blogspot.com/2009/08/logarithmic-z-buffer.html). (x3)
// Ulrich's formula is the following: (x3)
//     z = K * log( w / cameraNear ) / log( cameraFar / cameraNear ) (x3)
//     where K = 2^k - 1, and k is the number of bits in the depth buffer. (x3)
// The Outerra variant ignored the camera near plane (it assumed it was 0) and instead (x3)
// opted for a "C-constant" for resolution adjustment of objects near the camera. (x3)
// Outerra states: "Notice that the 'C' variant doesn’t use a near plane distance, it has it (x3)
// set at 0" (quote from https://outerra.blogspot.com/2012/11/maximizing-depth-buffer-range-and.html). (x3)
// Ulrich's variant has the benefit of constant relative precision over the whole near-far range. (x3)
// It was debated here whether Outerra's "C-constant" or Ulrich's "near plane" variant should (x3)
// be used, and ultimately Ulrich's "near plane" version was chosen. (x3)
// Outerra eventually made another improvement to their original "C-constant" variant, (x3)
// but it still does not incorporate the camera near plane (for this version, (x3)
// see https://outerra.blogspot.com/2013/07/logarithmic-depth-buffer-optimizations.html). (x3)
// Here we make 4 changes to Ulrich's formula: (x3)
// 1. Clamp the camera near plane so we don't divide by 0. (x3)
// 2. Use log2 instead of log to avoid an extra multiply (shaders implement log using log2). (x3)
// 3. Assume K is 1 (K = maximum value in depth buffer; see Ulrich's formula above). (x3)
// 4. To maintain consistency with the functions "viewZToOrthographicDepth" and "viewZToPerspectiveDepth", (x3)
//    we modify the formula here to use 'viewZ' instead of 'w'. The other functions expect a negative viewZ, (x3)
//    so we do the same here, hence the 'viewZ.negate()' call. (x3)
// For visual representation of this depth curve, see https://www.desmos.com/calculator/uyqk0vex1u (x3)
```

<details><summary>Code</summary>

```typescript
( viewZ, near, far ) => {

	// NOTE: viewZ must be negative--see explanation at the end of this comment block.
	// The final logarithmic depth formula used here is adapted from one described in an
	// article by Thatcher Ulrich (see http://tulrich.com/geekstuff/log_depth_buffer.txt),
	// which was an improvement upon an earlier formula one described in an
	// Outerra article (https://outerra.blogspot.com/2009/08/logarithmic-z-buffer.html).
	// Ulrich's formula is the following:
	//     z = K * log( w / cameraNear ) / log( cameraFar / cameraNear )
	//     where K = 2^k - 1, and k is the number of bits in the depth buffer.
	// The Outerra variant ignored the camera near plane (it assumed it was 0) and instead
	// opted for a "C-constant" for resolution adjustment of objects near the camera.
	// Outerra states: "Notice that the 'C' variant doesn’t use a near plane distance, it has it
	// set at 0" (quote from https://outerra.blogspot.com/2012/11/maximizing-depth-buffer-range-and.html).
	// Ulrich's variant has the benefit of constant relative precision over the whole near-far range.
	// It was debated here whether Outerra's "C-constant" or Ulrich's "near plane" variant should
	// be used, and ultimately Ulrich's "near plane" version was chosen.
	// Outerra eventually made another improvement to their original "C-constant" variant,
	// but it still does not incorporate the camera near plane (for this version,
	// see https://outerra.blogspot.com/2013/07/logarithmic-depth-buffer-optimizations.html).
	// Here we make 4 changes to Ulrich's formula:
	// 1. Clamp the camera near plane so we don't divide by 0.
	// 2. Use log2 instead of log to avoid an extra multiply (shaders implement log using log2).
	// 3. Assume K is 1 (K = maximum value in depth buffer; see Ulrich's formula above).
	// 4. To maintain consistency with the functions "viewZToOrthographicDepth" and "viewZToPerspectiveDepth",
	//    we modify the formula here to use 'viewZ' instead of 'w'. The other functions expect a negative viewZ,
	//    so we do the same here, hence the 'viewZ.negate()' call.
	// For visual representation of this depth curve, see https://www.desmos.com/calculator/uyqk0vex1u
	near = near.max( 1e-6 ).toVar();
	const numerator = log2( viewZ.negate().div( near ) );
	const denominator = log2( far.div( near ) );
	return numerator.div( denominator );

}
```
</details>

### `logarithmicDepthToViewZ(depth: any, near: any, far: any): any`

**Parameters:**

- **`depth`** `any`
- **`near`** `any`
- **`far`** `any`

**Returns:** `any`

**Calls:**

- `depth.mul`
- `log (from ../tsl/TSLBase.js)`
- `far.div`
- `float( Math.E ).pow( exponent ).mul( near ).negate`

**Internal Comments:**
```
// NOTE: we add a 'negate()' call to the return value here to maintain consistency with (x2)
// the functions "orthographicDepthToViewZ" and "perspectiveDepthToViewZ" (they return (x2)
// a negative viewZ). (x2)
```

<details><summary>Code</summary>

```typescript
( depth, near, far ) => {

	// NOTE: we add a 'negate()' call to the return value here to maintain consistency with
	// the functions "orthographicDepthToViewZ" and "perspectiveDepthToViewZ" (they return
	// a negative viewZ).
	const exponent = depth.mul( log( far.div( near ) ) );
	return float( Math.E ).pow( exponent ).mul( near ).negate();

}
```
</details>


---

## Classes

### `ViewportDepthNode`

<details><summary>Class Code</summary>

```ts
class ViewportDepthNode extends Node {

	static get type() {

		return 'ViewportDepthNode';

	}

	/**
	 * Constructs a new viewport depth node.
	 *
	 * @param {('depth'|'depthBase'|'linearDepth')} scope - The node's scope.
	 * @param {?Node} [valueNode=null] - The value node.
	 */
	constructor( scope, valueNode = null ) {

		super( 'float' );

		/**
		 * The node behaves differently depending on which scope is selected.
		 *
		 * - `ViewportDepthNode.DEPTH_BASE`: Allows to define a value for the current fragment's depth.
		 * - `ViewportDepthNode.DEPTH`: Represents the depth value for the current fragment (`valueNode` is ignored).
		 * - `ViewportDepthNode.LINEAR_DEPTH`: Represents the linear (orthographic) depth value of the current fragment.
		 * If a `valueNode` is set, the scope can be used to convert perspective depth data to linear data.
		 *
		 * @type {('depth'|'depthBase'|'linearDepth')}
		 */
		this.scope = scope;

		/**
		 * Can be used to define a custom depth value.
		 * The property is ignored in the `ViewportDepthNode.DEPTH` scope.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.valueNode = valueNode;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isViewportDepthNode = true;

	}

	generate( builder ) {

		const { scope } = this;

		if ( scope === ViewportDepthNode.DEPTH_BASE ) {

			return builder.getFragDepth();

		}

		return super.generate( builder );

	}

	setup( { camera } ) {

		const { scope } = this;
		const value = this.valueNode;

		let node = null;

		if ( scope === ViewportDepthNode.DEPTH_BASE ) {

			if ( value !== null ) {

 				node = depthBase().assign( value );

			}

		} else if ( scope === ViewportDepthNode.DEPTH ) {

			if ( camera.isPerspectiveCamera ) {

				node = viewZToPerspectiveDepth( positionView.z, cameraNear, cameraFar );

			} else {

				node = viewZToOrthographicDepth( positionView.z, cameraNear, cameraFar );

			}

		} else if ( scope === ViewportDepthNode.LINEAR_DEPTH ) {

			if ( value !== null ) {

				if ( camera.isPerspectiveCamera ) {

					const viewZ = perspectiveDepthToViewZ( value, cameraNear, cameraFar );

					node = viewZToOrthographicDepth( viewZ, cameraNear, cameraFar );

				} else {

					node = value;

				}

			} else {

				node = viewZToOrthographicDepth( positionView.z, cameraNear, cameraFar );

			}

		}

		return node;

	}

}
```
</details>

#### Methods

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const { scope } = this;

		if ( scope === ViewportDepthNode.DEPTH_BASE ) {

			return builder.getFragDepth();

		}

		return super.generate( builder );

	}
```
</details>

##### `setup({ camera }: any): any`

<details><summary>Code</summary>

```ts
setup( { camera } ) {

		const { scope } = this;
		const value = this.valueNode;

		let node = null;

		if ( scope === ViewportDepthNode.DEPTH_BASE ) {

			if ( value !== null ) {

 				node = depthBase().assign( value );

			}

		} else if ( scope === ViewportDepthNode.DEPTH ) {

			if ( camera.isPerspectiveCamera ) {

				node = viewZToPerspectiveDepth( positionView.z, cameraNear, cameraFar );

			} else {

				node = viewZToOrthographicDepth( positionView.z, cameraNear, cameraFar );

			}

		} else if ( scope === ViewportDepthNode.LINEAR_DEPTH ) {

			if ( value !== null ) {

				if ( camera.isPerspectiveCamera ) {

					const viewZ = perspectiveDepthToViewZ( value, cameraNear, cameraFar );

					node = viewZToOrthographicDepth( viewZ, cameraNear, cameraFar );

				} else {

					node = value;

				}

			} else {

				node = viewZToOrthographicDepth( positionView.z, cameraNear, cameraFar );

			}

		}

		return node;

	}
```
</details>


---