[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ClippingNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/ClippingNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `bool` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `positionView` | `./Position.js` |
| `diffuseColor` | `../core/PropertyNode.js` |
| `Loop` | `../utils/LoopNode.js` |
| `smoothstep` | `../math/MathNode.js` |
| `uniformArray` | `./UniformArrayNode.js` |
| `builtin` | `./BuiltinNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `clippingContext` | `any` | let/var | `builder.clippingContext` | ✗ |
| `numUnionPlanes` | `number` | let/var | `unionPlanes.length` | ✗ |
| `numIntersectionPlanes` | `number` | let/var | `intersectionPlanes.length` | ✗ |
| `numUnionPlanes` | `number` | let/var | `unionPlanes.length` | ✗ |
| `numIntersectionPlanes` | `number` | let/var | `intersectionPlanes.length` | ✗ |
| `numUnionPlanes` | `number` | let/var | `unionPlanes.length` | ✗ |


---

## Functions

### `ClippingNode.setup(builder: NodeBuilder): Node`

**JSDoc:**
```typescript
/**
	 * Setups the node depending on the selected scope.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The result node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `Node`

**Calls:**

- `super.setup`
- `this.setupAlphaToCoverage`
- `this.setupHardwareClipping`
- `this.setupDefault`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		super.setup( builder );

		const clippingContext = builder.clippingContext;
		const { intersectionPlanes, unionPlanes } = clippingContext;

		this.hardwareClipping = builder.material.hardwareClipping;

		if ( this.scope === ClippingNode.ALPHA_TO_COVERAGE ) {

			return this.setupAlphaToCoverage( intersectionPlanes, unionPlanes );

		} else if ( this.scope === ClippingNode.HARDWARE ) {

			return this.setupHardwareClipping( unionPlanes, builder );

		} else {

			return this.setupDefault( intersectionPlanes, unionPlanes );

		}

	}
```
</details>

### `ClippingNode.setupAlphaToCoverage(intersectionPlanes: Vector4[], unionPlanes: Vector4[]): Node`

**JSDoc:**
```typescript
/**
	 * Setups alpha to coverage.
	 *
	 * @param {Array<Vector4>} intersectionPlanes - The intersection planes.
	 * @param {Array<Vector4>} unionPlanes - The union planes.
	 * @return {Node} The result node.
	 */
```

**Parameters:**

- **`intersectionPlanes`** `Vector4[]`
- **`unionPlanes`** `Vector4[]`

**Returns:** `Node`

**Calls:**

- `complex_call_2280`

<details><summary>Code</summary>

```typescript
setupAlphaToCoverage( intersectionPlanes, unionPlanes ) {

		return Fn( () => {

			const distanceToPlane = float().toVar( 'distanceToPlane' );
			const distanceGradient = float().toVar( 'distanceToGradient' );

			const clipOpacity = float( 1 ).toVar( 'clipOpacity' );

			const numUnionPlanes = unionPlanes.length;

			if ( this.hardwareClipping === false && numUnionPlanes > 0 ) {

				const clippingPlanes = uniformArray( unionPlanes );

				Loop( numUnionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );

					distanceToPlane.assign( positionView.dot( plane.xyz ).negate().add( plane.w ) );
					distanceGradient.assign( distanceToPlane.fwidth().div( 2.0 ) );

					clipOpacity.mulAssign( smoothstep( distanceGradient.negate(), distanceGradient, distanceToPlane ) );

				} );

			}

			const numIntersectionPlanes = intersectionPlanes.length;

			if ( numIntersectionPlanes > 0 ) {

				const clippingPlanes = uniformArray( intersectionPlanes );
				const intersectionClipOpacity = float( 1 ).toVar( 'intersectionClipOpacity' );

				Loop( numIntersectionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );

					distanceToPlane.assign( positionView.dot( plane.xyz ).negate().add( plane.w ) );
					distanceGradient.assign( distanceToPlane.fwidth().div( 2.0 ) );

					intersectionClipOpacity.mulAssign( smoothstep( distanceGradient.negate(), distanceGradient, distanceToPlane ).oneMinus() );

				} );

				clipOpacity.mulAssign( intersectionClipOpacity.oneMinus() );

			}

			diffuseColor.a.mulAssign( clipOpacity );

			diffuseColor.a.equal( 0.0 ).discard();

		} )();

	}
```
</details>

### `ClippingNode.setupDefault(intersectionPlanes: Vector4[], unionPlanes: Vector4[]): Node`

**JSDoc:**
```typescript
/**
	 * Setups the default clipping.
	 *
	 * @param {Array<Vector4>} intersectionPlanes - The intersection planes.
	 * @param {Array<Vector4>} unionPlanes - The union planes.
	 * @return {Node} The result node.
	 */
```

**Parameters:**

- **`intersectionPlanes`** `Vector4[]`
- **`unionPlanes`** `Vector4[]`

**Returns:** `Node`

**Calls:**

- `complex_call_4117`

<details><summary>Code</summary>

```typescript
setupDefault( intersectionPlanes, unionPlanes ) {

		return Fn( () => {

			const numUnionPlanes = unionPlanes.length;

			if ( this.hardwareClipping === false && numUnionPlanes > 0 ) {

				const clippingPlanes = uniformArray( unionPlanes );

				Loop( numUnionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );
					positionView.dot( plane.xyz ).greaterThan( plane.w ).discard();

				} );

			}

			const numIntersectionPlanes = intersectionPlanes.length;

			if ( numIntersectionPlanes > 0 ) {

				const clippingPlanes = uniformArray( intersectionPlanes );
				const clipped = bool( true ).toVar( 'clipped' );

				Loop( numIntersectionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );
					clipped.assign( positionView.dot( plane.xyz ).greaterThan( plane.w ).and( clipped ) );

				} );

				clipped.discard();

			}

		} )();

	}
```
</details>

### `ClippingNode.setupHardwareClipping(unionPlanes: Vector4[], builder: NodeBuilder): Node`

**JSDoc:**
```typescript
/**
	 * Setups hardware clipping.
	 *
	 * @param {Array<Vector4>} unionPlanes - The union planes.
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The result node.
	 */
```

**Parameters:**

- **`unionPlanes`** `Vector4[]`
- **`builder`** `NodeBuilder`

**Returns:** `Node`

**Calls:**

- `builder.enableHardwareClipping`
- `complex_call_5297`

<details><summary>Code</summary>

```typescript
setupHardwareClipping( unionPlanes, builder ) {

		const numUnionPlanes = unionPlanes.length;

		builder.enableHardwareClipping( numUnionPlanes );

		return Fn( () => {

			const clippingPlanes = uniformArray( unionPlanes );
			const hw_clip_distances = builtin( builder.getClipDistance() );

			Loop( numUnionPlanes, ( { i } ) => {

				const plane = clippingPlanes.element( i );

				const distance = positionView.dot( plane.xyz ).sub( plane.w ).negate();
				hw_clip_distances.element( i ).assign( distance );

			} );

		} )();

	}
```
</details>

### `clipping(): ClippingNode`

**Returns:** `ClippingNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
() => nodeObject( new ClippingNode() )
```
</details>

### `clippingAlpha(): ClippingNode`

**Returns:** `ClippingNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
() => nodeObject( new ClippingNode( ClippingNode.ALPHA_TO_COVERAGE ) )
```
</details>

### `hardwareClipping(): ClippingNode`

**Returns:** `ClippingNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
() => nodeObject( new ClippingNode( ClippingNode.HARDWARE ) )
```
</details>


---

## Classes

### `ClippingNode`

<details><summary>Class Code</summary>

```ts
class ClippingNode extends Node {

	static get type() {

		return 'ClippingNode';

	}

	/**
	 * Constructs a new clipping node.
	 *
	 * @param {('default'|'hardware'|'alphaToCoverage')} [scope='default'] - The node's scope. Similar to other nodes,
	 * the selected scope influences the behavior of the node and what type of code is generated.
	 */
	constructor( scope = ClippingNode.DEFAULT ) {

		super();

		/**
		 * The node's scope. Similar to other nodes, the selected scope influences
		 * the behavior of the node and what type of code is generated.
		 *
		 * @type {('default'|'hardware'|'alphaToCoverage')}
		 */
		this.scope = scope;

	}

	/**
	 * Setups the node depending on the selected scope.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The result node.
	 */
	setup( builder ) {

		super.setup( builder );

		const clippingContext = builder.clippingContext;
		const { intersectionPlanes, unionPlanes } = clippingContext;

		this.hardwareClipping = builder.material.hardwareClipping;

		if ( this.scope === ClippingNode.ALPHA_TO_COVERAGE ) {

			return this.setupAlphaToCoverage( intersectionPlanes, unionPlanes );

		} else if ( this.scope === ClippingNode.HARDWARE ) {

			return this.setupHardwareClipping( unionPlanes, builder );

		} else {

			return this.setupDefault( intersectionPlanes, unionPlanes );

		}

	}

	/**
	 * Setups alpha to coverage.
	 *
	 * @param {Array<Vector4>} intersectionPlanes - The intersection planes.
	 * @param {Array<Vector4>} unionPlanes - The union planes.
	 * @return {Node} The result node.
	 */
	setupAlphaToCoverage( intersectionPlanes, unionPlanes ) {

		return Fn( () => {

			const distanceToPlane = float().toVar( 'distanceToPlane' );
			const distanceGradient = float().toVar( 'distanceToGradient' );

			const clipOpacity = float( 1 ).toVar( 'clipOpacity' );

			const numUnionPlanes = unionPlanes.length;

			if ( this.hardwareClipping === false && numUnionPlanes > 0 ) {

				const clippingPlanes = uniformArray( unionPlanes );

				Loop( numUnionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );

					distanceToPlane.assign( positionView.dot( plane.xyz ).negate().add( plane.w ) );
					distanceGradient.assign( distanceToPlane.fwidth().div( 2.0 ) );

					clipOpacity.mulAssign( smoothstep( distanceGradient.negate(), distanceGradient, distanceToPlane ) );

				} );

			}

			const numIntersectionPlanes = intersectionPlanes.length;

			if ( numIntersectionPlanes > 0 ) {

				const clippingPlanes = uniformArray( intersectionPlanes );
				const intersectionClipOpacity = float( 1 ).toVar( 'intersectionClipOpacity' );

				Loop( numIntersectionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );

					distanceToPlane.assign( positionView.dot( plane.xyz ).negate().add( plane.w ) );
					distanceGradient.assign( distanceToPlane.fwidth().div( 2.0 ) );

					intersectionClipOpacity.mulAssign( smoothstep( distanceGradient.negate(), distanceGradient, distanceToPlane ).oneMinus() );

				} );

				clipOpacity.mulAssign( intersectionClipOpacity.oneMinus() );

			}

			diffuseColor.a.mulAssign( clipOpacity );

			diffuseColor.a.equal( 0.0 ).discard();

		} )();

	}

	/**
	 * Setups the default clipping.
	 *
	 * @param {Array<Vector4>} intersectionPlanes - The intersection planes.
	 * @param {Array<Vector4>} unionPlanes - The union planes.
	 * @return {Node} The result node.
	 */
	setupDefault( intersectionPlanes, unionPlanes ) {

		return Fn( () => {

			const numUnionPlanes = unionPlanes.length;

			if ( this.hardwareClipping === false && numUnionPlanes > 0 ) {

				const clippingPlanes = uniformArray( unionPlanes );

				Loop( numUnionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );
					positionView.dot( plane.xyz ).greaterThan( plane.w ).discard();

				} );

			}

			const numIntersectionPlanes = intersectionPlanes.length;

			if ( numIntersectionPlanes > 0 ) {

				const clippingPlanes = uniformArray( intersectionPlanes );
				const clipped = bool( true ).toVar( 'clipped' );

				Loop( numIntersectionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );
					clipped.assign( positionView.dot( plane.xyz ).greaterThan( plane.w ).and( clipped ) );

				} );

				clipped.discard();

			}

		} )();

	}

	/**
	 * Setups hardware clipping.
	 *
	 * @param {Array<Vector4>} unionPlanes - The union planes.
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The result node.
	 */
	setupHardwareClipping( unionPlanes, builder ) {

		const numUnionPlanes = unionPlanes.length;

		builder.enableHardwareClipping( numUnionPlanes );

		return Fn( () => {

			const clippingPlanes = uniformArray( unionPlanes );
			const hw_clip_distances = builtin( builder.getClipDistance() );

			Loop( numUnionPlanes, ( { i } ) => {

				const plane = clippingPlanes.element( i );

				const distance = positionView.dot( plane.xyz ).sub( plane.w ).negate();
				hw_clip_distances.element( i ).assign( distance );

			} );

		} )();

	}

}
```
</details>

#### Methods

##### `setup(builder: NodeBuilder): Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		super.setup( builder );

		const clippingContext = builder.clippingContext;
		const { intersectionPlanes, unionPlanes } = clippingContext;

		this.hardwareClipping = builder.material.hardwareClipping;

		if ( this.scope === ClippingNode.ALPHA_TO_COVERAGE ) {

			return this.setupAlphaToCoverage( intersectionPlanes, unionPlanes );

		} else if ( this.scope === ClippingNode.HARDWARE ) {

			return this.setupHardwareClipping( unionPlanes, builder );

		} else {

			return this.setupDefault( intersectionPlanes, unionPlanes );

		}

	}
```
</details>

##### `setupAlphaToCoverage(intersectionPlanes: Vector4[], unionPlanes: Vector4[]): Node`

<details><summary>Code</summary>

```ts
setupAlphaToCoverage( intersectionPlanes, unionPlanes ) {

		return Fn( () => {

			const distanceToPlane = float().toVar( 'distanceToPlane' );
			const distanceGradient = float().toVar( 'distanceToGradient' );

			const clipOpacity = float( 1 ).toVar( 'clipOpacity' );

			const numUnionPlanes = unionPlanes.length;

			if ( this.hardwareClipping === false && numUnionPlanes > 0 ) {

				const clippingPlanes = uniformArray( unionPlanes );

				Loop( numUnionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );

					distanceToPlane.assign( positionView.dot( plane.xyz ).negate().add( plane.w ) );
					distanceGradient.assign( distanceToPlane.fwidth().div( 2.0 ) );

					clipOpacity.mulAssign( smoothstep( distanceGradient.negate(), distanceGradient, distanceToPlane ) );

				} );

			}

			const numIntersectionPlanes = intersectionPlanes.length;

			if ( numIntersectionPlanes > 0 ) {

				const clippingPlanes = uniformArray( intersectionPlanes );
				const intersectionClipOpacity = float( 1 ).toVar( 'intersectionClipOpacity' );

				Loop( numIntersectionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );

					distanceToPlane.assign( positionView.dot( plane.xyz ).negate().add( plane.w ) );
					distanceGradient.assign( distanceToPlane.fwidth().div( 2.0 ) );

					intersectionClipOpacity.mulAssign( smoothstep( distanceGradient.negate(), distanceGradient, distanceToPlane ).oneMinus() );

				} );

				clipOpacity.mulAssign( intersectionClipOpacity.oneMinus() );

			}

			diffuseColor.a.mulAssign( clipOpacity );

			diffuseColor.a.equal( 0.0 ).discard();

		} )();

	}
```
</details>

##### `setupDefault(intersectionPlanes: Vector4[], unionPlanes: Vector4[]): Node`

<details><summary>Code</summary>

```ts
setupDefault( intersectionPlanes, unionPlanes ) {

		return Fn( () => {

			const numUnionPlanes = unionPlanes.length;

			if ( this.hardwareClipping === false && numUnionPlanes > 0 ) {

				const clippingPlanes = uniformArray( unionPlanes );

				Loop( numUnionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );
					positionView.dot( plane.xyz ).greaterThan( plane.w ).discard();

				} );

			}

			const numIntersectionPlanes = intersectionPlanes.length;

			if ( numIntersectionPlanes > 0 ) {

				const clippingPlanes = uniformArray( intersectionPlanes );
				const clipped = bool( true ).toVar( 'clipped' );

				Loop( numIntersectionPlanes, ( { i } ) => {

					const plane = clippingPlanes.element( i );
					clipped.assign( positionView.dot( plane.xyz ).greaterThan( plane.w ).and( clipped ) );

				} );

				clipped.discard();

			}

		} )();

	}
```
</details>

##### `setupHardwareClipping(unionPlanes: Vector4[], builder: NodeBuilder): Node`

<details><summary>Code</summary>

```ts
setupHardwareClipping( unionPlanes, builder ) {

		const numUnionPlanes = unionPlanes.length;

		builder.enableHardwareClipping( numUnionPlanes );

		return Fn( () => {

			const clippingPlanes = uniformArray( unionPlanes );
			const hw_clip_distances = builtin( builder.getClipDistance() );

			Loop( numUnionPlanes, ( { i } ) => {

				const plane = clippingPlanes.element( i );

				const distance = positionView.dot( plane.xyz ).sub( plane.w ).negate();
				hw_clip_distances.element( i ).assign( distance );

			} );

		} )();

	}
```
</details>


---