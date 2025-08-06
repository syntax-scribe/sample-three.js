[⬅️ Back to Table of Contents](../../index.md)

# 📄 `InstancedMesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 24 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/InstancedMesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InstancedBufferAttribute` | `../core/InstancedBufferAttribute.js` |
| `Mesh` | `./Mesh.js` |
| `Box3` | `../math/Box3.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Sphere` | `../math/Sphere.js` |
| `DataTexture` | `../textures/DataTexture.js` |
| `FloatType` | `../constants.js` |
| `RedFormat` | `../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_instanceLocalMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_instanceWorldMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_instanceIntersects` | `any[]` | let/var | `[]` | ✗ |
| `_box3` | `Box3` | let/var | `new Box3()` | ✗ |
| `_identity` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_mesh` | `Mesh` | let/var | `new Mesh()` | ✗ |
| `_sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `count` | `number` | let/var | `this.count` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `count` | `number` | let/var | `this.count` | ✗ |
| `objectInfluences` | `number[]` | let/var | `object.morphTargetInfluences` | ✗ |
| `array` | `any` | let/var | `this.morphTexture.source.data.data` | ✗ |
| `len` | `number` | let/var | `objectInfluences.length + 1` | ✗ |
| `dataIndex` | `number` | let/var | `index * len + 1` | ✗ |
| `matrixWorld` | `Matrix4` | let/var | `this.matrixWorld` | ✗ |
| `raycastTimes` | `number` | let/var | `this.count` | ✗ |
| `intersect` | `any` | let/var | `_instanceIntersects[ i ]` | ✗ |
| `objectInfluences` | `number[]` | let/var | `object.morphTargetInfluences` | ✗ |
| `len` | `number` | let/var | `objectInfluences.length + 1` | ✗ |
| `array` | `any` | let/var | `this.morphTexture.source.data.data` | ✗ |
| `morphInfluencesSum` | `number` | let/var | `0` | ✗ |
| `morphBaseInfluence` | `number` | let/var | `this.geometry.morphTargetsRelative ? 1 : 1 - morphInfluencesSum` | ✗ |
| `dataIndex` | `number` | let/var | `len * index` | ✗ |


---

## Functions

### `InstancedMesh.computeBoundingBox(): void`

**JSDoc:**
```typescript
/**
	 * Computes the bounding box of the instanced mesh, and updates {@link InstancedMesh#boundingBox}.
	 * The bounding box is not automatically computed by the engine; this method must be called by your app.
	 * You may need to recompute the bounding box if an instance is transformed via {@link InstancedMesh#setMatrixAt}.
	 */
```

**Returns:** `void`

**Calls:**

- `geometry.computeBoundingBox`
- `this.boundingBox.makeEmpty`
- `this.getMatrixAt`
- `_box3.copy( geometry.boundingBox ).applyMatrix4`
- `this.boundingBox.union`

<details><summary>Code</summary>

```typescript
computeBoundingBox() {

		const geometry = this.geometry;
		const count = this.count;

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		if ( geometry.boundingBox === null ) {

			geometry.computeBoundingBox();

		}

		this.boundingBox.makeEmpty();

		for ( let i = 0; i < count; i ++ ) {

			this.getMatrixAt( i, _instanceLocalMatrix );

			_box3.copy( geometry.boundingBox ).applyMatrix4( _instanceLocalMatrix );

			this.boundingBox.union( _box3 );

		}

	}
```
</details>

### `InstancedMesh.computeBoundingSphere(): void`

**JSDoc:**
```typescript
/**
	 * Computes the bounding sphere of the instanced mesh, and updates {@link InstancedMesh#boundingSphere}
	 * The engine automatically computes the bounding sphere when it is needed, e.g., for ray casting or view frustum culling.
	 * You may need to recompute the bounding sphere if an instance is transformed via {@link InstancedMesh#setMatrixAt}.
	 */
```

**Returns:** `void`

**Calls:**

- `geometry.computeBoundingSphere`
- `this.boundingSphere.makeEmpty`
- `this.getMatrixAt`
- `_sphere.copy( geometry.boundingSphere ).applyMatrix4`
- `this.boundingSphere.union`

<details><summary>Code</summary>

```typescript
computeBoundingSphere() {

		const geometry = this.geometry;
		const count = this.count;

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		if ( geometry.boundingSphere === null ) {

			geometry.computeBoundingSphere();

		}

		this.boundingSphere.makeEmpty();

		for ( let i = 0; i < count; i ++ ) {

			this.getMatrixAt( i, _instanceLocalMatrix );

			_sphere.copy( geometry.boundingSphere ).applyMatrix4( _instanceLocalMatrix );

			this.boundingSphere.union( _sphere );

		}

	}
```
</details>

### `InstancedMesh.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.instanceMatrix.copy`
- `source.morphTexture.clone`
- `source.instanceColor.clone`
- `source.boundingBox.clone`
- `source.boundingSphere.clone`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.instanceMatrix.copy( source.instanceMatrix );

		if ( source.morphTexture !== null ) this.morphTexture = source.morphTexture.clone();
		if ( source.instanceColor !== null ) this.instanceColor = source.instanceColor.clone();

		this.count = source.count;

		if ( source.boundingBox !== null ) this.boundingBox = source.boundingBox.clone();
		if ( source.boundingSphere !== null ) this.boundingSphere = source.boundingSphere.clone();

		return this;

	}
```
</details>

### `InstancedMesh.getColorAt(index: number, color: Color): void`

**JSDoc:**
```typescript
/**
	 * Gets the color of the defined instance.
	 *
	 * @param {number} index - The instance index.
	 * @param {Color} color - The target object that is used to store the method's result.
	 */
```

**Parameters:**

- **`index`** `number`
- **`color`** `Color`

**Returns:** `void`

**Calls:**

- `color.fromArray`

<details><summary>Code</summary>

```typescript
getColorAt( index, color ) {

		color.fromArray( this.instanceColor.array, index * 3 );

	}
```
</details>

### `InstancedMesh.getMatrixAt(index: number, matrix: Matrix4): void`

**JSDoc:**
```typescript
/**
	 * Gets the local transformation matrix of the defined instance.
	 *
	 * @param {number} index - The instance index.
	 * @param {Matrix4} matrix - The target object that is used to store the method's result.
	 */
```

**Parameters:**

- **`index`** `number`
- **`matrix`** `Matrix4`

**Returns:** `void`

**Calls:**

- `matrix.fromArray`

<details><summary>Code</summary>

```typescript
getMatrixAt( index, matrix ) {

		matrix.fromArray( this.instanceMatrix.array, index * 16 );

	}
```
</details>

### `InstancedMesh.getMorphAt(index: number, object: Mesh): void`

**JSDoc:**
```typescript
/**
	 * Gets the morph target weights of the defined instance.
	 *
	 * @param {number} index - The instance index.
	 * @param {Mesh} object - The target object that is used to store the method's result.
	 */
```

**Parameters:**

- **`index`** `number`
- **`object`** `Mesh`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
getMorphAt( index, object ) {

		const objectInfluences = object.morphTargetInfluences;

		const array = this.morphTexture.source.data.data;

		const len = objectInfluences.length + 1; // All influences + the baseInfluenceSum

		const dataIndex = index * len + 1; // Skip the baseInfluenceSum at the beginning

		for ( let i = 0; i < objectInfluences.length; i ++ ) {

			objectInfluences[ i ] = array[ dataIndex + i ];

		}

	}
```
</details>

### `InstancedMesh.raycast(raycaster: any, intersects: any): void`

**Parameters:**

- **`raycaster`** `any`
- **`intersects`** `any`

**Returns:** `void`

**Calls:**

- `this.computeBoundingSphere`
- `_sphere.copy`
- `_sphere.applyMatrix4`
- `raycaster.ray.intersectsSphere`
- `this.getMatrixAt`
- `_instanceWorldMatrix.multiplyMatrices`
- `_mesh.raycast`
- `intersects.push`

**Internal Comments:**
```
// test with bounding sphere first
// now test each instance
// calculate the world matrix for each instance (x4)
// the mesh represents this single instance (x4)
// process the result of raycast
```

<details><summary>Code</summary>

```typescript
raycast( raycaster, intersects ) {

		const matrixWorld = this.matrixWorld;
		const raycastTimes = this.count;

		_mesh.geometry = this.geometry;
		_mesh.material = this.material;

		if ( _mesh.material === undefined ) return;

		// test with bounding sphere first

		if ( this.boundingSphere === null ) this.computeBoundingSphere();

		_sphere.copy( this.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );

		if ( raycaster.ray.intersectsSphere( _sphere ) === false ) return;

		// now test each instance

		for ( let instanceId = 0; instanceId < raycastTimes; instanceId ++ ) {

			// calculate the world matrix for each instance

			this.getMatrixAt( instanceId, _instanceLocalMatrix );

			_instanceWorldMatrix.multiplyMatrices( matrixWorld, _instanceLocalMatrix );

			// the mesh represents this single instance

			_mesh.matrixWorld = _instanceWorldMatrix;

			_mesh.raycast( raycaster, _instanceIntersects );

			// process the result of raycast

			for ( let i = 0, l = _instanceIntersects.length; i < l; i ++ ) {

				const intersect = _instanceIntersects[ i ];
				intersect.instanceId = instanceId;
				intersect.object = this;
				intersects.push( intersect );

			}

			_instanceIntersects.length = 0;

		}

	}
```
</details>

### `InstancedMesh.setColorAt(index: number, color: Color): void`

**JSDoc:**
```typescript
/**
	 * Sets the given color to the defined instance. Make sure you set the `needsUpdate` flag of
	 * {@link InstancedMesh#instanceColor} to `true` after updating all the colors.
	 *
	 * @param {number} index - The instance index.
	 * @param {Color} color - The instance color.
	 */
```

**Parameters:**

- **`index`** `number`
- **`color`** `Color`

**Returns:** `void`

**Calls:**

- `new Float32Array( this.instanceMatrix.count * 3 ).fill`
- `color.toArray`

<details><summary>Code</summary>

```typescript
setColorAt( index, color ) {

		if ( this.instanceColor === null ) {

			this.instanceColor = new InstancedBufferAttribute( new Float32Array( this.instanceMatrix.count * 3 ).fill( 1 ), 3 );

		}

		color.toArray( this.instanceColor.array, index * 3 );

	}
```
</details>

### `InstancedMesh.setMatrixAt(index: number, matrix: Matrix4): void`

**JSDoc:**
```typescript
/**
	 * Sets the given local transformation matrix to the defined instance. Make sure you set the `needsUpdate` flag of
	 * {@link InstancedMesh#instanceMatrix} to `true` after updating all the colors.
	 *
	 * @param {number} index - The instance index.
	 * @param {Matrix4} matrix - The local transformation.
	 */
```

**Parameters:**

- **`index`** `number`
- **`matrix`** `Matrix4`

**Returns:** `void`

**Calls:**

- `matrix.toArray`

<details><summary>Code</summary>

```typescript
setMatrixAt( index, matrix ) {

		matrix.toArray( this.instanceMatrix.array, index * 16 );

	}
```
</details>

### `InstancedMesh.setMorphAt(index: number, object: Mesh): void`

**JSDoc:**
```typescript
/**
	 * Sets the morph target weights to the defined instance. Make sure you set the `needsUpdate` flag of
	 * {@link InstancedMesh#morphTexture} to `true` after updating all the influences.
	 *
	 * @param {number} index - The instance index.
	 * @param {Mesh} object -  A mesh which `morphTargetInfluences` property containing the morph target weights
	 * of a single instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`object`** `Mesh`

**Returns:** `void`

**Calls:**

- `array.set`

<details><summary>Code</summary>

```typescript
setMorphAt( index, object ) {

		const objectInfluences = object.morphTargetInfluences;

		const len = objectInfluences.length + 1; // morphBaseInfluence + all influences

		if ( this.morphTexture === null ) {

			this.morphTexture = new DataTexture( new Float32Array( len * this.count ), len, this.count, RedFormat, FloatType );

		}

		const array = this.morphTexture.source.data.data;

		let morphInfluencesSum = 0;

		for ( let i = 0; i < objectInfluences.length; i ++ ) {

			morphInfluencesSum += objectInfluences[ i ];

		}

		const morphBaseInfluence = this.geometry.morphTargetsRelative ? 1 : 1 - morphInfluencesSum;

		const dataIndex = len * index;

		array[ dataIndex ] = morphBaseInfluence;

		array.set( objectInfluences, dataIndex + 1 );

	}
```
</details>

### `InstancedMesh.updateMorphTargets(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateMorphTargets() {

	}
```
</details>

### `InstancedMesh.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`
- `this.morphTexture.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

		if ( this.morphTexture !== null ) {

			this.morphTexture.dispose();
			this.morphTexture = null;

		}

	}
```
</details>


---

## Classes

### `InstancedMesh`

<details><summary>Class Code</summary>

```ts
class InstancedMesh extends Mesh {

	/**
	 * Constructs a new instanced mesh.
	 *
	 * @param {BufferGeometry} [geometry] - The mesh geometry.
	 * @param {Material|Array<Material>} [material] - The mesh material.
	 * @param {number} count - The number of instances.
	 */
	constructor( geometry, material, count ) {

		super( geometry, material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isInstancedMesh = true;

		/**
		 * Represents the local transformation of all instances. You have to set its
		 * {@link BufferAttribute#needsUpdate} flag to true if you modify instanced data
		 * via {@link InstancedMesh#setMatrixAt}.
		 *
		 * @type {InstancedBufferAttribute}
		 */
		this.instanceMatrix = new InstancedBufferAttribute( new Float32Array( count * 16 ), 16 );

		/**
		 * Represents the color of all instances. You have to set its
		 * {@link BufferAttribute#needsUpdate} flag to true if you modify instanced data
		 * via {@link InstancedMesh#setColorAt}.
		 *
		 * @type {?InstancedBufferAttribute}
		 * @default null
		 */
		this.instanceColor = null;

		/**
		 * Represents the morph target weights of all instances. You have to set its
		 * {@link Texture#needsUpdate} flag to true if you modify instanced data
		 * via {@link InstancedMesh#setMorphAt}.
		 *
		 * @type {?DataTexture}
		 * @default null
		 */
		this.morphTexture = null;

		/**
		 * The number of instances.
		 *
		 * @type {number}
		 */
		this.count = count;

		/**
		 * The bounding box of the instanced mesh. Can be computed via {@link InstancedMesh#computeBoundingBox}.
		 *
		 * @type {?Box3}
		 * @default null
		 */
		this.boundingBox = null;

		/**
		 * The bounding sphere of the instanced mesh. Can be computed via {@link InstancedMesh#computeBoundingSphere}.
		 *
		 * @type {?Sphere}
		 * @default null
		 */
		this.boundingSphere = null;

		for ( let i = 0; i < count; i ++ ) {

			this.setMatrixAt( i, _identity );

		}

	}

	/**
	 * Computes the bounding box of the instanced mesh, and updates {@link InstancedMesh#boundingBox}.
	 * The bounding box is not automatically computed by the engine; this method must be called by your app.
	 * You may need to recompute the bounding box if an instance is transformed via {@link InstancedMesh#setMatrixAt}.
	 */
	computeBoundingBox() {

		const geometry = this.geometry;
		const count = this.count;

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		if ( geometry.boundingBox === null ) {

			geometry.computeBoundingBox();

		}

		this.boundingBox.makeEmpty();

		for ( let i = 0; i < count; i ++ ) {

			this.getMatrixAt( i, _instanceLocalMatrix );

			_box3.copy( geometry.boundingBox ).applyMatrix4( _instanceLocalMatrix );

			this.boundingBox.union( _box3 );

		}

	}

	/**
	 * Computes the bounding sphere of the instanced mesh, and updates {@link InstancedMesh#boundingSphere}
	 * The engine automatically computes the bounding sphere when it is needed, e.g., for ray casting or view frustum culling.
	 * You may need to recompute the bounding sphere if an instance is transformed via {@link InstancedMesh#setMatrixAt}.
	 */
	computeBoundingSphere() {

		const geometry = this.geometry;
		const count = this.count;

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		if ( geometry.boundingSphere === null ) {

			geometry.computeBoundingSphere();

		}

		this.boundingSphere.makeEmpty();

		for ( let i = 0; i < count; i ++ ) {

			this.getMatrixAt( i, _instanceLocalMatrix );

			_sphere.copy( geometry.boundingSphere ).applyMatrix4( _instanceLocalMatrix );

			this.boundingSphere.union( _sphere );

		}

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.instanceMatrix.copy( source.instanceMatrix );

		if ( source.morphTexture !== null ) this.morphTexture = source.morphTexture.clone();
		if ( source.instanceColor !== null ) this.instanceColor = source.instanceColor.clone();

		this.count = source.count;

		if ( source.boundingBox !== null ) this.boundingBox = source.boundingBox.clone();
		if ( source.boundingSphere !== null ) this.boundingSphere = source.boundingSphere.clone();

		return this;

	}

	/**
	 * Gets the color of the defined instance.
	 *
	 * @param {number} index - The instance index.
	 * @param {Color} color - The target object that is used to store the method's result.
	 */
	getColorAt( index, color ) {

		color.fromArray( this.instanceColor.array, index * 3 );

	}

	/**
	 * Gets the local transformation matrix of the defined instance.
	 *
	 * @param {number} index - The instance index.
	 * @param {Matrix4} matrix - The target object that is used to store the method's result.
	 */
	getMatrixAt( index, matrix ) {

		matrix.fromArray( this.instanceMatrix.array, index * 16 );

	}

	/**
	 * Gets the morph target weights of the defined instance.
	 *
	 * @param {number} index - The instance index.
	 * @param {Mesh} object - The target object that is used to store the method's result.
	 */
	getMorphAt( index, object ) {

		const objectInfluences = object.morphTargetInfluences;

		const array = this.morphTexture.source.data.data;

		const len = objectInfluences.length + 1; // All influences + the baseInfluenceSum

		const dataIndex = index * len + 1; // Skip the baseInfluenceSum at the beginning

		for ( let i = 0; i < objectInfluences.length; i ++ ) {

			objectInfluences[ i ] = array[ dataIndex + i ];

		}

	}

	raycast( raycaster, intersects ) {

		const matrixWorld = this.matrixWorld;
		const raycastTimes = this.count;

		_mesh.geometry = this.geometry;
		_mesh.material = this.material;

		if ( _mesh.material === undefined ) return;

		// test with bounding sphere first

		if ( this.boundingSphere === null ) this.computeBoundingSphere();

		_sphere.copy( this.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );

		if ( raycaster.ray.intersectsSphere( _sphere ) === false ) return;

		// now test each instance

		for ( let instanceId = 0; instanceId < raycastTimes; instanceId ++ ) {

			// calculate the world matrix for each instance

			this.getMatrixAt( instanceId, _instanceLocalMatrix );

			_instanceWorldMatrix.multiplyMatrices( matrixWorld, _instanceLocalMatrix );

			// the mesh represents this single instance

			_mesh.matrixWorld = _instanceWorldMatrix;

			_mesh.raycast( raycaster, _instanceIntersects );

			// process the result of raycast

			for ( let i = 0, l = _instanceIntersects.length; i < l; i ++ ) {

				const intersect = _instanceIntersects[ i ];
				intersect.instanceId = instanceId;
				intersect.object = this;
				intersects.push( intersect );

			}

			_instanceIntersects.length = 0;

		}

	}

	/**
	 * Sets the given color to the defined instance. Make sure you set the `needsUpdate` flag of
	 * {@link InstancedMesh#instanceColor} to `true` after updating all the colors.
	 *
	 * @param {number} index - The instance index.
	 * @param {Color} color - The instance color.
	 */
	setColorAt( index, color ) {

		if ( this.instanceColor === null ) {

			this.instanceColor = new InstancedBufferAttribute( new Float32Array( this.instanceMatrix.count * 3 ).fill( 1 ), 3 );

		}

		color.toArray( this.instanceColor.array, index * 3 );

	}

	/**
	 * Sets the given local transformation matrix to the defined instance. Make sure you set the `needsUpdate` flag of
	 * {@link InstancedMesh#instanceMatrix} to `true` after updating all the colors.
	 *
	 * @param {number} index - The instance index.
	 * @param {Matrix4} matrix - The local transformation.
	 */
	setMatrixAt( index, matrix ) {

		matrix.toArray( this.instanceMatrix.array, index * 16 );

	}

	/**
	 * Sets the morph target weights to the defined instance. Make sure you set the `needsUpdate` flag of
	 * {@link InstancedMesh#morphTexture} to `true` after updating all the influences.
	 *
	 * @param {number} index - The instance index.
	 * @param {Mesh} object -  A mesh which `morphTargetInfluences` property containing the morph target weights
	 * of a single instance.
	 */
	setMorphAt( index, object ) {

		const objectInfluences = object.morphTargetInfluences;

		const len = objectInfluences.length + 1; // morphBaseInfluence + all influences

		if ( this.morphTexture === null ) {

			this.morphTexture = new DataTexture( new Float32Array( len * this.count ), len, this.count, RedFormat, FloatType );

		}

		const array = this.morphTexture.source.data.data;

		let morphInfluencesSum = 0;

		for ( let i = 0; i < objectInfluences.length; i ++ ) {

			morphInfluencesSum += objectInfluences[ i ];

		}

		const morphBaseInfluence = this.geometry.morphTargetsRelative ? 1 : 1 - morphInfluencesSum;

		const dataIndex = len * index;

		array[ dataIndex ] = morphBaseInfluence;

		array.set( objectInfluences, dataIndex + 1 );

	}

	updateMorphTargets() {

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.dispatchEvent( { type: 'dispose' } );

		if ( this.morphTexture !== null ) {

			this.morphTexture.dispose();
			this.morphTexture = null;

		}

	}

}
```
</details>

#### Methods

##### `computeBoundingBox(): void`

<details><summary>Code</summary>

```ts
computeBoundingBox() {

		const geometry = this.geometry;
		const count = this.count;

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		if ( geometry.boundingBox === null ) {

			geometry.computeBoundingBox();

		}

		this.boundingBox.makeEmpty();

		for ( let i = 0; i < count; i ++ ) {

			this.getMatrixAt( i, _instanceLocalMatrix );

			_box3.copy( geometry.boundingBox ).applyMatrix4( _instanceLocalMatrix );

			this.boundingBox.union( _box3 );

		}

	}
```
</details>

##### `computeBoundingSphere(): void`

<details><summary>Code</summary>

```ts
computeBoundingSphere() {

		const geometry = this.geometry;
		const count = this.count;

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		if ( geometry.boundingSphere === null ) {

			geometry.computeBoundingSphere();

		}

		this.boundingSphere.makeEmpty();

		for ( let i = 0; i < count; i ++ ) {

			this.getMatrixAt( i, _instanceLocalMatrix );

			_sphere.copy( geometry.boundingSphere ).applyMatrix4( _instanceLocalMatrix );

			this.boundingSphere.union( _sphere );

		}

	}
```
</details>

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		this.instanceMatrix.copy( source.instanceMatrix );

		if ( source.morphTexture !== null ) this.morphTexture = source.morphTexture.clone();
		if ( source.instanceColor !== null ) this.instanceColor = source.instanceColor.clone();

		this.count = source.count;

		if ( source.boundingBox !== null ) this.boundingBox = source.boundingBox.clone();
		if ( source.boundingSphere !== null ) this.boundingSphere = source.boundingSphere.clone();

		return this;

	}
```
</details>

##### `getColorAt(index: number, color: Color): void`

<details><summary>Code</summary>

```ts
getColorAt( index, color ) {

		color.fromArray( this.instanceColor.array, index * 3 );

	}
```
</details>

##### `getMatrixAt(index: number, matrix: Matrix4): void`

<details><summary>Code</summary>

```ts
getMatrixAt( index, matrix ) {

		matrix.fromArray( this.instanceMatrix.array, index * 16 );

	}
```
</details>

##### `getMorphAt(index: number, object: Mesh): void`

<details><summary>Code</summary>

```ts
getMorphAt( index, object ) {

		const objectInfluences = object.morphTargetInfluences;

		const array = this.morphTexture.source.data.data;

		const len = objectInfluences.length + 1; // All influences + the baseInfluenceSum

		const dataIndex = index * len + 1; // Skip the baseInfluenceSum at the beginning

		for ( let i = 0; i < objectInfluences.length; i ++ ) {

			objectInfluences[ i ] = array[ dataIndex + i ];

		}

	}
```
</details>

##### `raycast(raycaster: any, intersects: any): void`

<details><summary>Code</summary>

```ts
raycast( raycaster, intersects ) {

		const matrixWorld = this.matrixWorld;
		const raycastTimes = this.count;

		_mesh.geometry = this.geometry;
		_mesh.material = this.material;

		if ( _mesh.material === undefined ) return;

		// test with bounding sphere first

		if ( this.boundingSphere === null ) this.computeBoundingSphere();

		_sphere.copy( this.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );

		if ( raycaster.ray.intersectsSphere( _sphere ) === false ) return;

		// now test each instance

		for ( let instanceId = 0; instanceId < raycastTimes; instanceId ++ ) {

			// calculate the world matrix for each instance

			this.getMatrixAt( instanceId, _instanceLocalMatrix );

			_instanceWorldMatrix.multiplyMatrices( matrixWorld, _instanceLocalMatrix );

			// the mesh represents this single instance

			_mesh.matrixWorld = _instanceWorldMatrix;

			_mesh.raycast( raycaster, _instanceIntersects );

			// process the result of raycast

			for ( let i = 0, l = _instanceIntersects.length; i < l; i ++ ) {

				const intersect = _instanceIntersects[ i ];
				intersect.instanceId = instanceId;
				intersect.object = this;
				intersects.push( intersect );

			}

			_instanceIntersects.length = 0;

		}

	}
```
</details>

##### `setColorAt(index: number, color: Color): void`

<details><summary>Code</summary>

```ts
setColorAt( index, color ) {

		if ( this.instanceColor === null ) {

			this.instanceColor = new InstancedBufferAttribute( new Float32Array( this.instanceMatrix.count * 3 ).fill( 1 ), 3 );

		}

		color.toArray( this.instanceColor.array, index * 3 );

	}
```
</details>

##### `setMatrixAt(index: number, matrix: Matrix4): void`

<details><summary>Code</summary>

```ts
setMatrixAt( index, matrix ) {

		matrix.toArray( this.instanceMatrix.array, index * 16 );

	}
```
</details>

##### `setMorphAt(index: number, object: Mesh): void`

<details><summary>Code</summary>

```ts
setMorphAt( index, object ) {

		const objectInfluences = object.morphTargetInfluences;

		const len = objectInfluences.length + 1; // morphBaseInfluence + all influences

		if ( this.morphTexture === null ) {

			this.morphTexture = new DataTexture( new Float32Array( len * this.count ), len, this.count, RedFormat, FloatType );

		}

		const array = this.morphTexture.source.data.data;

		let morphInfluencesSum = 0;

		for ( let i = 0; i < objectInfluences.length; i ++ ) {

			morphInfluencesSum += objectInfluences[ i ];

		}

		const morphBaseInfluence = this.geometry.morphTargetsRelative ? 1 : 1 - morphInfluencesSum;

		const dataIndex = len * index;

		array[ dataIndex ] = morphBaseInfluence;

		array.set( objectInfluences, dataIndex + 1 );

	}
```
</details>

##### `updateMorphTargets(): void`

<details><summary>Code</summary>

```ts
updateMorphTargets() {

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

		if ( this.morphTexture !== null ) {

			this.morphTexture.dispose();
			this.morphTexture = null;

		}

	}
```
</details>


---