[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ClippingContext.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/ClippingContext.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix3` | `../../math/Matrix3.js` |
| `Plane` | `../../math/Plane.js` |
| `Vector4` | `../../math/Vector4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_plane` | `Plane` | let/var | `new Plane()` | ✗ |
| `l` | `number` | let/var | `source.length` | ✗ |
| `v` | `Vector4` | let/var | `destination[ offset + i ]` | ✗ |
| `normal` | `Vector3` | let/var | `_plane.normal` | ✗ |
| `update` | `boolean` | let/var | `false` | ✗ |
| `srcClippingPlanes` | `any` | let/var | `clippingGroup.clippingPlanes` | ✗ |
| `l` | `any` | let/var | `srcClippingPlanes.length` | ✗ |
| `dstClippingPlanes` | `any` | let/var | `*not shown*` | ✗ |
| `offset` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `ClippingContext.projectPlanes(source: Plane[], destination: Vector4[], offset: number): void`

**JSDoc:**
```typescript
/**
	 * Projects the given source clipping planes and writes the result into the
	 * destination array.
	 *
	 * @param {Array<Plane>} source - The source clipping planes.
	 * @param {Array<Vector4>} destination - The destination.
	 * @param {number} offset - The offset.
	 */
```

**Parameters:**

- **`source`** `Plane[]`
- **`destination`** `Vector4[]`
- **`offset`** `number`

**Returns:** `void`

**Calls:**

- `_plane.copy( source[ i ] ).applyMatrix4`

<details><summary>Code</summary>

```typescript
projectPlanes( source, destination, offset ) {

		const l = source.length;

		for ( let i = 0; i < l; i ++ ) {

			_plane.copy( source[ i ] ).applyMatrix4( this.viewMatrix, this.viewNormalMatrix );

			const v = destination[ offset + i ];
			const normal = _plane.normal;

			v.x = - normal.x;
			v.y = - normal.y;
			v.z = - normal.z;
			v.w = _plane.constant;

		}

	}
```
</details>

### `ClippingContext.updateGlobal(scene: Scene, camera: Camera): void`

**JSDoc:**
```typescript
/**
	 * Updates the root clipping context of a scene.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 */
```

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`

**Returns:** `void`

**Calls:**

- `this.viewNormalMatrix.getNormalMatrix`

<details><summary>Code</summary>

```typescript
updateGlobal( scene, camera ) {

		this.shadowPass = ( scene.overrideMaterial !== null && scene.overrideMaterial.isShadowPassMaterial );
		this.viewMatrix = camera.matrixWorldInverse;

		this.viewNormalMatrix.getNormalMatrix( this.viewMatrix );

	}
```
</details>

### `ClippingContext.update(parentContext: ClippingContext, clippingGroup: ClippingGroup): void`

**JSDoc:**
```typescript
/**
	 * Updates the clipping context.
	 *
	 * @param {ClippingContext} parentContext - The parent context.
	 * @param {ClippingGroup} clippingGroup - The clipping group this context belongs to.
	 */
```

**Parameters:**

- **`parentContext`** `ClippingContext`
- **`clippingGroup`** `ClippingGroup`

**Returns:** `void`

**Calls:**

- `Array.from`
- `this.projectPlanes`

<details><summary>Code</summary>

```typescript
update( parentContext, clippingGroup ) {

		let update = false;

		if ( parentContext.version !== this.parentVersion ) {

			this.intersectionPlanes = Array.from( parentContext.intersectionPlanes );
			this.unionPlanes = Array.from( parentContext.unionPlanes );
			this.parentVersion = parentContext.version;

		}

		if ( this.clipIntersection !== clippingGroup.clipIntersection ) {

			this.clipIntersection = clippingGroup.clipIntersection;

			if ( this.clipIntersection ) {

				this.unionPlanes.length = parentContext.unionPlanes.length;

			} else {

				this.intersectionPlanes.length = parentContext.intersectionPlanes.length;

			}

		}

		const srcClippingPlanes = clippingGroup.clippingPlanes;
		const l = srcClippingPlanes.length;

		let dstClippingPlanes;
		let offset;

		if ( this.clipIntersection ) {

			dstClippingPlanes = this.intersectionPlanes;
			offset = parentContext.intersectionPlanes.length;

		} else {

			dstClippingPlanes = this.unionPlanes;
			offset = parentContext.unionPlanes.length;

		}

		if ( dstClippingPlanes.length !== offset + l ) {

			dstClippingPlanes.length = offset + l;

			for ( let i = 0; i < l; i ++ ) {

				dstClippingPlanes[ offset + i ] = new Vector4();

			}

			update = true;

		}

		this.projectPlanes( srcClippingPlanes, dstClippingPlanes, offset );

		if ( update ) {

			this.version ++;
			this.cacheKey = `${ this.intersectionPlanes.length }:${ this.unionPlanes.length }`;

		}

	}
```
</details>

### `ClippingContext.getGroupContext(clippingGroup: ClippingGroup): ClippingContext`

**JSDoc:**
```typescript
/**
	 * Returns a clipping context for the given clipping group.
	 *
	 * @param {ClippingGroup} clippingGroup - The clipping group.
	 * @return {ClippingContext} The clipping context.
	 */
```

**Parameters:**

- **`clippingGroup`** `ClippingGroup`

**Returns:** `ClippingContext`

**Calls:**

- `this.clippingGroupContexts.get`
- `this.clippingGroupContexts.set`
- `context.update`

<details><summary>Code</summary>

```typescript
getGroupContext( clippingGroup ) {

		if ( this.shadowPass && ! clippingGroup.clipShadows ) return this;

		let context = this.clippingGroupContexts.get( clippingGroup );

		if ( context === undefined ) {

			context = new ClippingContext( this );
			this.clippingGroupContexts.set( clippingGroup, context );

		}

		context.update( this, clippingGroup );

		return context;

	}
```
</details>


---

## Classes

### `ClippingContext`

<details><summary>Class Code</summary>

```ts
class ClippingContext {

	/**
	 * Constructs a new clipping context.
	 *
	 * @param {?ClippingContext} [parentContext=null] - A reference to the parent clipping context.
	 */
	constructor( parentContext = null ) {

		/**
		 * The clipping context's version.
		 *
		 * @type {number}
		 * @readonly
		 */
		this.version = 0;

		/**
		 * Whether the intersection of the clipping planes is used to clip objects, rather than their union.
		 *
		 * @type {?boolean}
		 * @default null
		 */
		this.clipIntersection = null;

		/**
		 * The clipping context's cache key.
		 *
		 * @type {string}
		 */
		this.cacheKey = '';

		/**
		 * Whether the shadow pass is active or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.shadowPass = false;

		/**
		 * The view normal matrix.
		 *
		 * @type {Matrix3}
		 */
		this.viewNormalMatrix = new Matrix3();

		/**
		 * Internal cache for maintaining clipping contexts.
		 *
		 * @type {WeakMap<ClippingGroup,ClippingContext>}
		 */
		this.clippingGroupContexts = new WeakMap();

		/**
		 * The intersection planes.
		 *
		 * @type {Array<Vector4>}
		 */
		this.intersectionPlanes = [];

		/**
		 * The intersection planes.
		 *
		 * @type {Array<Vector4>}
		 */
		this.unionPlanes = [];

		/**
		 * The version of the clipping context's parent context.
		 *
		 * @type {?number}
		 * @readonly
		 */
		this.parentVersion = null;

		if ( parentContext !== null ) {

			this.viewNormalMatrix = parentContext.viewNormalMatrix;
			this.clippingGroupContexts = parentContext.clippingGroupContexts;

			this.shadowPass = parentContext.shadowPass;
			this.viewMatrix = parentContext.viewMatrix;

		}

	}

	/**
	 * Projects the given source clipping planes and writes the result into the
	 * destination array.
	 *
	 * @param {Array<Plane>} source - The source clipping planes.
	 * @param {Array<Vector4>} destination - The destination.
	 * @param {number} offset - The offset.
	 */
	projectPlanes( source, destination, offset ) {

		const l = source.length;

		for ( let i = 0; i < l; i ++ ) {

			_plane.copy( source[ i ] ).applyMatrix4( this.viewMatrix, this.viewNormalMatrix );

			const v = destination[ offset + i ];
			const normal = _plane.normal;

			v.x = - normal.x;
			v.y = - normal.y;
			v.z = - normal.z;
			v.w = _plane.constant;

		}

	}

	/**
	 * Updates the root clipping context of a scene.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 */
	updateGlobal( scene, camera ) {

		this.shadowPass = ( scene.overrideMaterial !== null && scene.overrideMaterial.isShadowPassMaterial );
		this.viewMatrix = camera.matrixWorldInverse;

		this.viewNormalMatrix.getNormalMatrix( this.viewMatrix );

	}

	/**
	 * Updates the clipping context.
	 *
	 * @param {ClippingContext} parentContext - The parent context.
	 * @param {ClippingGroup} clippingGroup - The clipping group this context belongs to.
	 */
	update( parentContext, clippingGroup ) {

		let update = false;

		if ( parentContext.version !== this.parentVersion ) {

			this.intersectionPlanes = Array.from( parentContext.intersectionPlanes );
			this.unionPlanes = Array.from( parentContext.unionPlanes );
			this.parentVersion = parentContext.version;

		}

		if ( this.clipIntersection !== clippingGroup.clipIntersection ) {

			this.clipIntersection = clippingGroup.clipIntersection;

			if ( this.clipIntersection ) {

				this.unionPlanes.length = parentContext.unionPlanes.length;

			} else {

				this.intersectionPlanes.length = parentContext.intersectionPlanes.length;

			}

		}

		const srcClippingPlanes = clippingGroup.clippingPlanes;
		const l = srcClippingPlanes.length;

		let dstClippingPlanes;
		let offset;

		if ( this.clipIntersection ) {

			dstClippingPlanes = this.intersectionPlanes;
			offset = parentContext.intersectionPlanes.length;

		} else {

			dstClippingPlanes = this.unionPlanes;
			offset = parentContext.unionPlanes.length;

		}

		if ( dstClippingPlanes.length !== offset + l ) {

			dstClippingPlanes.length = offset + l;

			for ( let i = 0; i < l; i ++ ) {

				dstClippingPlanes[ offset + i ] = new Vector4();

			}

			update = true;

		}

		this.projectPlanes( srcClippingPlanes, dstClippingPlanes, offset );

		if ( update ) {

			this.version ++;
			this.cacheKey = `${ this.intersectionPlanes.length }:${ this.unionPlanes.length }`;

		}

	}

	/**
	 * Returns a clipping context for the given clipping group.
	 *
	 * @param {ClippingGroup} clippingGroup - The clipping group.
	 * @return {ClippingContext} The clipping context.
	 */
	getGroupContext( clippingGroup ) {

		if ( this.shadowPass && ! clippingGroup.clipShadows ) return this;

		let context = this.clippingGroupContexts.get( clippingGroup );

		if ( context === undefined ) {

			context = new ClippingContext( this );
			this.clippingGroupContexts.set( clippingGroup, context );

		}

		context.update( this, clippingGroup );

		return context;

	}

	/**
	 * The count of union clipping planes.
	 *
	 * @type {number}
	 * @readonly
	 */
	get unionClippingCount() {

		return this.unionPlanes.length;

	}

}
```
</details>

#### Methods

##### `projectPlanes(source: Plane[], destination: Vector4[], offset: number): void`

<details><summary>Code</summary>

```ts
projectPlanes( source, destination, offset ) {

		const l = source.length;

		for ( let i = 0; i < l; i ++ ) {

			_plane.copy( source[ i ] ).applyMatrix4( this.viewMatrix, this.viewNormalMatrix );

			const v = destination[ offset + i ];
			const normal = _plane.normal;

			v.x = - normal.x;
			v.y = - normal.y;
			v.z = - normal.z;
			v.w = _plane.constant;

		}

	}
```
</details>

##### `updateGlobal(scene: Scene, camera: Camera): void`

<details><summary>Code</summary>

```ts
updateGlobal( scene, camera ) {

		this.shadowPass = ( scene.overrideMaterial !== null && scene.overrideMaterial.isShadowPassMaterial );
		this.viewMatrix = camera.matrixWorldInverse;

		this.viewNormalMatrix.getNormalMatrix( this.viewMatrix );

	}
```
</details>

##### `update(parentContext: ClippingContext, clippingGroup: ClippingGroup): void`

<details><summary>Code</summary>

```ts
update( parentContext, clippingGroup ) {

		let update = false;

		if ( parentContext.version !== this.parentVersion ) {

			this.intersectionPlanes = Array.from( parentContext.intersectionPlanes );
			this.unionPlanes = Array.from( parentContext.unionPlanes );
			this.parentVersion = parentContext.version;

		}

		if ( this.clipIntersection !== clippingGroup.clipIntersection ) {

			this.clipIntersection = clippingGroup.clipIntersection;

			if ( this.clipIntersection ) {

				this.unionPlanes.length = parentContext.unionPlanes.length;

			} else {

				this.intersectionPlanes.length = parentContext.intersectionPlanes.length;

			}

		}

		const srcClippingPlanes = clippingGroup.clippingPlanes;
		const l = srcClippingPlanes.length;

		let dstClippingPlanes;
		let offset;

		if ( this.clipIntersection ) {

			dstClippingPlanes = this.intersectionPlanes;
			offset = parentContext.intersectionPlanes.length;

		} else {

			dstClippingPlanes = this.unionPlanes;
			offset = parentContext.unionPlanes.length;

		}

		if ( dstClippingPlanes.length !== offset + l ) {

			dstClippingPlanes.length = offset + l;

			for ( let i = 0; i < l; i ++ ) {

				dstClippingPlanes[ offset + i ] = new Vector4();

			}

			update = true;

		}

		this.projectPlanes( srcClippingPlanes, dstClippingPlanes, offset );

		if ( update ) {

			this.version ++;
			this.cacheKey = `${ this.intersectionPlanes.length }:${ this.unionPlanes.length }`;

		}

	}
```
</details>

##### `getGroupContext(clippingGroup: ClippingGroup): ClippingContext`

<details><summary>Code</summary>

```ts
getGroupContext( clippingGroup ) {

		if ( this.shadowPass && ! clippingGroup.clipShadows ) return this;

		let context = this.clippingGroupContexts.get( clippingGroup );

		if ( context === undefined ) {

			context = new ClippingContext( this );
			this.clippingGroupContexts.set( clippingGroup, context );

		}

		context.update( this, clippingGroup );

		return context;

	}
```
</details>


---