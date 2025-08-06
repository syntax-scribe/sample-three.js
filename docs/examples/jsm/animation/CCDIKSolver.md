[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CCDIKSolver.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 🧱 Classes | 2 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 60 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/animation/CCDIKSolver.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `Line` | `three` |
| `LineBasicMaterial` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `Object3D` | `three` |
| `Quaternion` | `three` |
| `SphereGeometry` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_quaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `_targetPos` | `any` | let/var | `new Vector3()` | ✗ |
| `_targetVec` | `any` | let/var | `new Vector3()` | ✗ |
| `_effectorPos` | `any` | let/var | `new Vector3()` | ✗ |
| `_effectorVec` | `any` | let/var | `new Vector3()` | ✗ |
| `_linkPos` | `any` | let/var | `new Vector3()` | ✗ |
| `_invLinkQ` | `any` | let/var | `new Quaternion()` | ✗ |
| `_linkScale` | `any` | let/var | `new Vector3()` | ✗ |
| `_axis` | `any` | let/var | `new Vector3()` | ✗ |
| `_vector` | `any` | let/var | `new Vector3()` | ✗ |
| `_matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `chainQuats` | `any[]` | let/var | `[]` | ✗ |
| `iks` | `SkinnedMesh` | let/var | `this.iks` | ✗ |
| `chainBlend` | `any` | let/var | `ik.blendFactor !== undefined ? ik.blendFactor : overrideBlend` | ✗ |
| `bones` | `any` | let/var | `this.mesh.skeleton.bones` | ✗ |
| `initialQuaternions` | `any[]` | let/var | `this._initialQuaternions[ chainIndex ]` | ✗ |
| `math` | `Math` | let/var | `Math` | ✗ |
| `effector` | `any` | let/var | `bones[ ik.effector ]` | ✗ |
| `target` | `any` | let/var | `bones[ ik.target ]` | ✗ |
| `links` | `any` | let/var | `ik.links` | ✗ |
| `iteration` | `any` | let/var | `ik.iteration !== undefined ? ik.iteration : 1` | ✗ |
| `linkIndex` | `any` | let/var | `links[ j ].index` | ✗ |
| `rotated` | `boolean` | let/var | `false` | ✗ |
| `link` | `any` | let/var | `bones[ links[ j ].index ]` | ✗ |
| `limitation` | `any` | let/var | `links[ j ].limitation` | ✗ |
| `rotationMin` | `any` | let/var | `links[ j ].rotationMin` | ✗ |
| `rotationMax` | `any` | let/var | `links[ j ].rotationMax` | ✗ |
| `c` | `any` | let/var | `link.quaternion.w` | ✗ |
| `linkIndex` | `any` | let/var | `links[ j ].index` | ✗ |
| `link` | `any` | let/var | `bones[ linkIndex ]` | ✗ |
| `iks` | `SkinnedMesh` | let/var | `this.iks` | ✗ |
| `bones` | `any` | let/var | `this.mesh.skeleton.bones` | ✗ |
| `ik` | `SkinnedMesh` | let/var | `iks[ i ]` | ✗ |
| `effector` | `any` | let/var | `bones[ ik.effector ]` | ✗ |
| `links` | `any` | let/var | `ik.links` | ✗ |
| `link0` | `any` | let/var | `*not shown*` | ✗ |
| `link1` | `any` | let/var | `*not shown*` | ✗ |
| `mesh` | `SkinnedMesh` | let/var | `this.root` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `iks` | `CCDIKSolver[]` | let/var | `this.iks` | ✗ |
| `bones` | `any` | let/var | `mesh.skeleton.bones` | ✗ |
| `ik` | `CCDIKSolver` | let/var | `iks[ i ]` | ✗ |
| `targetBone` | `any` | let/var | `bones[ ik.target ]` | ✗ |
| `effectorBone` | `any` | let/var | `bones[ ik.effector ]` | ✗ |
| `targetMesh` | `any` | let/var | `this.children[ offset ++ ]` | ✗ |
| `effectorMesh` | `any` | let/var | `this.children[ offset ++ ]` | ✗ |
| `link` | `any` | let/var | `ik.links[ j ]` | ✗ |
| `linkBone` | `any` | let/var | `bones[ link.index ]` | ✗ |
| `linkMesh` | `any` | let/var | `this.children[ offset ++ ]` | ✗ |
| `line` | `any` | let/var | `this.children[ offset ++ ]` | ✗ |
| `array` | `any` | let/var | `line.geometry.attributes.position.array` | ✗ |
| `link` | `any` | let/var | `ik.links[ j ]` | ✗ |
| `linkBone` | `any` | let/var | `bones[ link.index ]` | ✗ |
| `children` | `any` | let/var | `this.children` | ✗ |
| `child` | `any` | let/var | `children[ i ]` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `iks` | `CCDIKSolver[]` | let/var | `this.iks` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `vertices` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( ( 2 + ik.links.length ) * 3 )` | ✗ |
| `ik` | `CCDIKSolver` | let/var | `iks[ i ]` | ✗ |


---

## Functions

### `CCDIKSolver.update(globalBlendFactor: number): CCDIKSolver`

**JSDoc:**
```typescript
/**
	 * Updates all IK bones by solving the CCD algorithm.
	 *
	 * @param {number} [globalBlendFactor=1.0] - Blend factor applied if an IK chain doesn't have its own .blendFactor.
	 * @return {CCDIKSolver} A reference to this instance.
	 */
```

**Parameters:**

- **`globalBlendFactor`** `number`

**Returns:** `CCDIKSolver`

**Calls:**

- `this.updateOne`

<details><summary>Code</summary>

```typescript
update( globalBlendFactor = 1.0 ) {

		const iks = this.iks;

		for ( let i = 0, il = iks.length; i < il; i ++ ) {

			this.updateOne( iks[ i ], globalBlendFactor );

		}

		return this;

	}
```
</details>

### `CCDIKSolver.updateOne(ik: any, overrideBlend: number): CCDIKSolver`

**JSDoc:**
```typescript
/**
	 * Updates one IK bone solving the CCD algorithm.
	 *
	 * @param {CCDIKSolver~IK} ik - The IK to update.
	 * @param {number} [overrideBlend=1.0] - If the IK object does not define `blendFactor`, this value is used.
	 * @return {CCDIKSolver} A reference to this instance.
	 */
```

**Parameters:**

- **`ik`** `any`
- **`overrideBlend`** `number`

**Returns:** `CCDIKSolver`

**Calls:**

- `this.iks.indexOf`
- `_targetPos.setFromMatrixPosition`
- `initialQuaternions[ j ].copy`
- `link.matrixWorld.decompose`
- `_invLinkQ.invert`
- `_effectorPos.setFromMatrixPosition`
- `_effectorVec.subVectors`
- `_effectorVec.applyQuaternion`
- `_effectorVec.normalize`
- `_targetVec.subVectors`
- `_targetVec.applyQuaternion`
- `_targetVec.normalize`
- `_targetVec.dot`
- `math.acos`
- `_axis.crossVectors`
- `_axis.normalize`
- `_quaternion.setFromAxisAngle`
- `link.quaternion.multiply`
- `math.sqrt`
- `link.quaternion.set`
- `link.rotation.setFromVector3`
- `_vector.setFromEuler( link.rotation ).max`
- `_vector.setFromEuler( link.rotation ).min`
- `link.updateMatrixWorld`
- `this._workingQuaternion.copy( initialQuaternions[ j ] ).slerp`
- `link.quaternion.copy`

**Internal Comments:**
```
// for reference overhead reduction in loop (x2)
// don't use getWorldPosition() here for the performance (x4)
// because it calls updateMatrixWorld( true ) inside. (x4)
// skip this link and following links
// don't use getWorldPosition/Quaternion() here for the performance (x5)
// because they call updateMatrixWorld( true ) inside. (x5)
// work in link world (x4)
// skip if changing angle is too small to prevent vibration of bone
// TODO: re-consider the limitation specification
```

<details><summary>Code</summary>

```typescript
updateOne( ik, overrideBlend = 1.0 ) {

		const chainBlend = ik.blendFactor !== undefined ? ik.blendFactor : overrideBlend;
		const bones = this.mesh.skeleton.bones;
		const chainIndex = this.iks.indexOf( ik );
		const initialQuaternions = this._initialQuaternions[ chainIndex ];

		// for reference overhead reduction in loop
		const math = Math;

		const effector = bones[ ik.effector ];
		const target = bones[ ik.target ];

		// don't use getWorldPosition() here for the performance
		// because it calls updateMatrixWorld( true ) inside.
		_targetPos.setFromMatrixPosition( target.matrixWorld );

		const links = ik.links;
		const iteration = ik.iteration !== undefined ? ik.iteration : 1;

		if ( chainBlend < 1.0 ) {

			for ( let j = 0; j < links.length; j ++ ) {

			  const linkIndex = links[ j ].index;
			  initialQuaternions[ j ].copy( bones[ linkIndex ].quaternion );

			}

		}

		for ( let i = 0; i < iteration; i ++ ) {

			let rotated = false;

			for ( let j = 0, jl = links.length; j < jl; j ++ ) {

				const link = bones[ links[ j ].index ];

				// skip this link and following links
				if ( links[ j ].enabled === false ) break;

				const limitation = links[ j ].limitation;
				const rotationMin = links[ j ].rotationMin;
				const rotationMax = links[ j ].rotationMax;

				// don't use getWorldPosition/Quaternion() here for the performance
				// because they call updateMatrixWorld( true ) inside.
				link.matrixWorld.decompose( _linkPos, _invLinkQ, _linkScale );
				_invLinkQ.invert();
				_effectorPos.setFromMatrixPosition( effector.matrixWorld );

				// work in link world
				_effectorVec.subVectors( _effectorPos, _linkPos );
				_effectorVec.applyQuaternion( _invLinkQ );
				_effectorVec.normalize();

				_targetVec.subVectors( _targetPos, _linkPos );
				_targetVec.applyQuaternion( _invLinkQ );
				_targetVec.normalize();

				let angle = _targetVec.dot( _effectorVec );

				if ( angle > 1.0 ) {

					angle = 1.0;

				} else if ( angle < - 1.0 ) {

					angle = - 1.0;

				}

				angle = math.acos( angle );

				// skip if changing angle is too small to prevent vibration of bone
				if ( angle < 1e-5 ) continue;

				if ( ik.minAngle !== undefined && angle < ik.minAngle ) {

					angle = ik.minAngle;

				}

				if ( ik.maxAngle !== undefined && angle > ik.maxAngle ) {

					angle = ik.maxAngle;

				}

				_axis.crossVectors( _effectorVec, _targetVec );
				_axis.normalize();

				_quaternion.setFromAxisAngle( _axis, angle );
				link.quaternion.multiply( _quaternion );

				// TODO: re-consider the limitation specification
				if ( limitation !== undefined ) {

					let c = link.quaternion.w;

					if ( c > 1.0 ) c = 1.0;

					const c2 = math.sqrt( 1 - c * c );
					link.quaternion.set( limitation.x * c2,
					                     limitation.y * c2,
					                     limitation.z * c2,
					                     c );

				}

				if ( rotationMin !== undefined ) {

					link.rotation.setFromVector3( _vector.setFromEuler( link.rotation ).max( rotationMin ) );

				}

				if ( rotationMax !== undefined ) {

					link.rotation.setFromVector3( _vector.setFromEuler( link.rotation ).min( rotationMax ) );

				}

				link.updateMatrixWorld( true );

				rotated = true;

			}

			if ( ! rotated ) break;

		}

		if ( chainBlend < 1.0 ) {

			for ( let j = 0; j < links.length; j ++ ) {

			  const linkIndex = links[ j ].index;
			  const link = bones[ linkIndex ];

			  this._workingQuaternion.copy( initialQuaternions[ j ] ).slerp( link.quaternion, chainBlend );

			  link.quaternion.copy( this._workingQuaternion );
			  link.updateMatrixWorld( true );

			}

		}

		  return this;

	}
```
</details>

### `CCDIKSolver.createHelper(sphereSize: number): CCDIKHelper`

**JSDoc:**
```typescript
/**
	 * Creates a helper for visualizing the CCDIK.
	 *
	 * @param {number} sphereSize - The sphere size.
	 * @return {CCDIKHelper} The created helper.
	 */
```

**Parameters:**

- **`sphereSize`** `number`

**Returns:** `CCDIKHelper`

<details><summary>Code</summary>

```typescript
createHelper( sphereSize ) {

		return new CCDIKHelper( this.mesh, this.iks, sphereSize );

	}
```
</details>

### `CCDIKSolver._valid(): void`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
_valid() {

		const iks = this.iks;
		const bones = this.mesh.skeleton.bones;

		for ( let i = 0, il = iks.length; i < il; i ++ ) {

			const ik = iks[ i ];
			const effector = bones[ ik.effector ];
			const links = ik.links;
			let link0, link1;

			link0 = effector;

			for ( let j = 0, jl = links.length; j < jl; j ++ ) {

				link1 = bones[ links[ j ].index ];

				if ( link0.parent !== link1 ) {

					console.warn( 'THREE.CCDIKSolver: bone ' + link0.name + ' is not the child of bone ' + link1.name );

				}

				link0 = link1;

			}

		}

	}
```
</details>

### `getPosition(bone: any, matrixWorldInv: any): any`

**Parameters:**

- **`bone`** `any`
- **`matrixWorldInv`** `any`

**Returns:** `any`

**Calls:**

- `_vector
		.setFromMatrixPosition( bone.matrixWorld )
		.applyMatrix4`

<details><summary>Code</summary>

```typescript
function getPosition( bone, matrixWorldInv ) {

	return _vector
		.setFromMatrixPosition( bone.matrixWorld )
		.applyMatrix4( matrixWorldInv );

}
```
</details>

### `setPositionOfBoneToAttributeArray(array: any, index: any, bone: any, matrixWorldInv: any): void`

**Parameters:**

- **`array`** `any`
- **`index`** `any`
- **`bone`** `any`
- **`matrixWorldInv`** `any`

**Returns:** `void`

**Calls:**

- `getPosition`

<details><summary>Code</summary>

```typescript
function setPositionOfBoneToAttributeArray( array, index, bone, matrixWorldInv ) {

	const v = getPosition( bone, matrixWorldInv );

	array[ index * 3 + 0 ] = v.x;
	array[ index * 3 + 1 ] = v.y;
	array[ index * 3 + 2 ] = v.z;

}
```
</details>

### `CCDIKHelper.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `_matrix.copy( mesh.matrixWorld ).invert`
- `targetMesh.position.copy`
- `getPosition`
- `effectorMesh.position.copy`
- `linkMesh.position.copy`
- `setPositionOfBoneToAttributeArray`
- `this.matrix.copy`
- `super.updateMatrixWorld`

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		const mesh = this.root;

		if ( this.visible ) {

			let offset = 0;

			const iks = this.iks;
			const bones = mesh.skeleton.bones;

			_matrix.copy( mesh.matrixWorld ).invert();

			for ( let i = 0, il = iks.length; i < il; i ++ ) {

				const ik = iks[ i ];

				const targetBone = bones[ ik.target ];
				const effectorBone = bones[ ik.effector ];

				const targetMesh = this.children[ offset ++ ];
				const effectorMesh = this.children[ offset ++ ];

				targetMesh.position.copy( getPosition( targetBone, _matrix ) );
				effectorMesh.position.copy( getPosition( effectorBone, _matrix ) );

				for ( let j = 0, jl = ik.links.length; j < jl; j ++ ) {

					const link = ik.links[ j ];
					const linkBone = bones[ link.index ];

					const linkMesh = this.children[ offset ++ ];

					linkMesh.position.copy( getPosition( linkBone, _matrix ) );

				}

				const line = this.children[ offset ++ ];
				const array = line.geometry.attributes.position.array;

				setPositionOfBoneToAttributeArray( array, 0, targetBone, _matrix );
				setPositionOfBoneToAttributeArray( array, 1, effectorBone, _matrix );

				for ( let j = 0, jl = ik.links.length; j < jl; j ++ ) {

					const link = ik.links[ j ];
					const linkBone = bones[ link.index ];
					setPositionOfBoneToAttributeArray( array, j + 2, linkBone, _matrix );

				}

				line.geometry.attributes.position.needsUpdate = true;

			}

		}

		this.matrix.copy( mesh.matrixWorld );

		super.updateMatrixWorld( force );

	}
```
</details>

### `CCDIKHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance.
	 * Call this method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.sphereGeometry.dispose`
- `this.targetSphereMaterial.dispose`
- `this.effectorSphereMaterial.dispose`
- `this.linkSphereMaterial.dispose`
- `this.lineMaterial.dispose`
- `child.geometry.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.sphereGeometry.dispose();

		this.targetSphereMaterial.dispose();
		this.effectorSphereMaterial.dispose();
		this.linkSphereMaterial.dispose();
		this.lineMaterial.dispose();

		const children = this.children;

		for ( let i = 0; i < children.length; i ++ ) {

			const child = children[ i ];

			if ( child.isLine ) child.geometry.dispose();

		}

	}
```
</details>

### `CCDIKHelper._init(): void`

**Returns:** `void`

**Calls:**

- `geometry.setAttribute`
- `createLineGeometry`
- `this.add`
- `createTargetMesh`
- `createEffectorMesh`
- `createLinkMesh`
- `createLine`

<details><summary>Code</summary>

```typescript
_init() {

		const scope = this;
		const iks = this.iks;

		function createLineGeometry( ik ) {

			const geometry = new BufferGeometry();
			const vertices = new Float32Array( ( 2 + ik.links.length ) * 3 );
			geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );

			return geometry;

		}

		function createTargetMesh() {

			return new Mesh( scope.sphereGeometry, scope.targetSphereMaterial );

		}

		function createEffectorMesh() {

			return new Mesh( scope.sphereGeometry, scope.effectorSphereMaterial );

		}

		function createLinkMesh() {

			return new Mesh( scope.sphereGeometry, scope.linkSphereMaterial );

		}

		function createLine( ik ) {

			return new Line( createLineGeometry( ik ), scope.lineMaterial );

		}

		for ( let i = 0, il = iks.length; i < il; i ++ ) {

			const ik = iks[ i ];

			this.add( createTargetMesh() );
			this.add( createEffectorMesh() );

			for ( let j = 0, jl = ik.links.length; j < jl; j ++ ) {

				this.add( createLinkMesh() );

			}

			this.add( createLine( ik ) );

		}

	}
```
</details>

### `createLineGeometry(ik: any): any`

**Parameters:**

- **`ik`** `any`

**Returns:** `any`

**Calls:**

- `geometry.setAttribute`

<details><summary>Code</summary>

```typescript
function createLineGeometry( ik ) {

			const geometry = new BufferGeometry();
			const vertices = new Float32Array( ( 2 + ik.links.length ) * 3 );
			geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );

			return geometry;

		}
```
</details>

### `createTargetMesh(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function createTargetMesh() {

			return new Mesh( scope.sphereGeometry, scope.targetSphereMaterial );

		}
```
</details>

### `createEffectorMesh(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function createEffectorMesh() {

			return new Mesh( scope.sphereGeometry, scope.effectorSphereMaterial );

		}
```
</details>

### `createLinkMesh(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function createLinkMesh() {

			return new Mesh( scope.sphereGeometry, scope.linkSphereMaterial );

		}
```
</details>

### `createLine(ik: any): any`

**Parameters:**

- **`ik`** `any`

**Returns:** `any`

**Calls:**

- `createLineGeometry`

<details><summary>Code</summary>

```typescript
function createLine( ik ) {

			return new Line( createLineGeometry( ik ), scope.lineMaterial );

		}
```
</details>


---

## Classes

### `CCDIKSolver`

<details><summary>Class Code</summary>

```ts
class CCDIKSolver {

	/**
	 * @param {SkinnedMesh} mesh - The skinned mesh.
	 * @param {Array<CCDIKSolver~IK>} [iks=[]] - The IK objects.
	 */
	constructor( mesh, iks = [] ) {

		/**
		 * The skinned mesh.
		 *
		 * @type {SkinnedMesh}
		 */
		this.mesh = mesh;

		/**
		 * The IK objects.
		 *
		 * @type {SkinnedMesh}
		 */
		this.iks = iks;

		this._initialQuaternions = [];
		this._workingQuaternion = new Quaternion();

		for ( const ik of iks ) {

			const chainQuats = [];
			for ( let i = 0; i < ik.links.length; i ++ ) {

			  chainQuats.push( new Quaternion() );

			}

			this._initialQuaternions.push( chainQuats );

		}

		this._valid();

	}

	/**
	 * Updates all IK bones by solving the CCD algorithm.
	 *
	 * @param {number} [globalBlendFactor=1.0] - Blend factor applied if an IK chain doesn't have its own .blendFactor.
	 * @return {CCDIKSolver} A reference to this instance.
	 */
	update( globalBlendFactor = 1.0 ) {

		const iks = this.iks;

		for ( let i = 0, il = iks.length; i < il; i ++ ) {

			this.updateOne( iks[ i ], globalBlendFactor );

		}

		return this;

	}

	/**
	 * Updates one IK bone solving the CCD algorithm.
	 *
	 * @param {CCDIKSolver~IK} ik - The IK to update.
	 * @param {number} [overrideBlend=1.0] - If the IK object does not define `blendFactor`, this value is used.
	 * @return {CCDIKSolver} A reference to this instance.
	 */
	updateOne( ik, overrideBlend = 1.0 ) {

		const chainBlend = ik.blendFactor !== undefined ? ik.blendFactor : overrideBlend;
		const bones = this.mesh.skeleton.bones;
		const chainIndex = this.iks.indexOf( ik );
		const initialQuaternions = this._initialQuaternions[ chainIndex ];

		// for reference overhead reduction in loop
		const math = Math;

		const effector = bones[ ik.effector ];
		const target = bones[ ik.target ];

		// don't use getWorldPosition() here for the performance
		// because it calls updateMatrixWorld( true ) inside.
		_targetPos.setFromMatrixPosition( target.matrixWorld );

		const links = ik.links;
		const iteration = ik.iteration !== undefined ? ik.iteration : 1;

		if ( chainBlend < 1.0 ) {

			for ( let j = 0; j < links.length; j ++ ) {

			  const linkIndex = links[ j ].index;
			  initialQuaternions[ j ].copy( bones[ linkIndex ].quaternion );

			}

		}

		for ( let i = 0; i < iteration; i ++ ) {

			let rotated = false;

			for ( let j = 0, jl = links.length; j < jl; j ++ ) {

				const link = bones[ links[ j ].index ];

				// skip this link and following links
				if ( links[ j ].enabled === false ) break;

				const limitation = links[ j ].limitation;
				const rotationMin = links[ j ].rotationMin;
				const rotationMax = links[ j ].rotationMax;

				// don't use getWorldPosition/Quaternion() here for the performance
				// because they call updateMatrixWorld( true ) inside.
				link.matrixWorld.decompose( _linkPos, _invLinkQ, _linkScale );
				_invLinkQ.invert();
				_effectorPos.setFromMatrixPosition( effector.matrixWorld );

				// work in link world
				_effectorVec.subVectors( _effectorPos, _linkPos );
				_effectorVec.applyQuaternion( _invLinkQ );
				_effectorVec.normalize();

				_targetVec.subVectors( _targetPos, _linkPos );
				_targetVec.applyQuaternion( _invLinkQ );
				_targetVec.normalize();

				let angle = _targetVec.dot( _effectorVec );

				if ( angle > 1.0 ) {

					angle = 1.0;

				} else if ( angle < - 1.0 ) {

					angle = - 1.0;

				}

				angle = math.acos( angle );

				// skip if changing angle is too small to prevent vibration of bone
				if ( angle < 1e-5 ) continue;

				if ( ik.minAngle !== undefined && angle < ik.minAngle ) {

					angle = ik.minAngle;

				}

				if ( ik.maxAngle !== undefined && angle > ik.maxAngle ) {

					angle = ik.maxAngle;

				}

				_axis.crossVectors( _effectorVec, _targetVec );
				_axis.normalize();

				_quaternion.setFromAxisAngle( _axis, angle );
				link.quaternion.multiply( _quaternion );

				// TODO: re-consider the limitation specification
				if ( limitation !== undefined ) {

					let c = link.quaternion.w;

					if ( c > 1.0 ) c = 1.0;

					const c2 = math.sqrt( 1 - c * c );
					link.quaternion.set( limitation.x * c2,
					                     limitation.y * c2,
					                     limitation.z * c2,
					                     c );

				}

				if ( rotationMin !== undefined ) {

					link.rotation.setFromVector3( _vector.setFromEuler( link.rotation ).max( rotationMin ) );

				}

				if ( rotationMax !== undefined ) {

					link.rotation.setFromVector3( _vector.setFromEuler( link.rotation ).min( rotationMax ) );

				}

				link.updateMatrixWorld( true );

				rotated = true;

			}

			if ( ! rotated ) break;

		}

		if ( chainBlend < 1.0 ) {

			for ( let j = 0; j < links.length; j ++ ) {

			  const linkIndex = links[ j ].index;
			  const link = bones[ linkIndex ];

			  this._workingQuaternion.copy( initialQuaternions[ j ] ).slerp( link.quaternion, chainBlend );

			  link.quaternion.copy( this._workingQuaternion );
			  link.updateMatrixWorld( true );

			}

		}

		  return this;

	}

	/**
	 * Creates a helper for visualizing the CCDIK.
	 *
	 * @param {number} sphereSize - The sphere size.
	 * @return {CCDIKHelper} The created helper.
	 */
	createHelper( sphereSize ) {

		return new CCDIKHelper( this.mesh, this.iks, sphereSize );

	}

	// private methods

	_valid() {

		const iks = this.iks;
		const bones = this.mesh.skeleton.bones;

		for ( let i = 0, il = iks.length; i < il; i ++ ) {

			const ik = iks[ i ];
			const effector = bones[ ik.effector ];
			const links = ik.links;
			let link0, link1;

			link0 = effector;

			for ( let j = 0, jl = links.length; j < jl; j ++ ) {

				link1 = bones[ links[ j ].index ];

				if ( link0.parent !== link1 ) {

					console.warn( 'THREE.CCDIKSolver: bone ' + link0.name + ' is not the child of bone ' + link1.name );

				}

				link0 = link1;

			}

		}

	}

}
```
</details>

#### Methods

##### `update(globalBlendFactor: number): CCDIKSolver`

<details><summary>Code</summary>

```ts
update( globalBlendFactor = 1.0 ) {

		const iks = this.iks;

		for ( let i = 0, il = iks.length; i < il; i ++ ) {

			this.updateOne( iks[ i ], globalBlendFactor );

		}

		return this;

	}
```
</details>

##### `updateOne(ik: any, overrideBlend: number): CCDIKSolver`

<details><summary>Code</summary>

```ts
updateOne( ik, overrideBlend = 1.0 ) {

		const chainBlend = ik.blendFactor !== undefined ? ik.blendFactor : overrideBlend;
		const bones = this.mesh.skeleton.bones;
		const chainIndex = this.iks.indexOf( ik );
		const initialQuaternions = this._initialQuaternions[ chainIndex ];

		// for reference overhead reduction in loop
		const math = Math;

		const effector = bones[ ik.effector ];
		const target = bones[ ik.target ];

		// don't use getWorldPosition() here for the performance
		// because it calls updateMatrixWorld( true ) inside.
		_targetPos.setFromMatrixPosition( target.matrixWorld );

		const links = ik.links;
		const iteration = ik.iteration !== undefined ? ik.iteration : 1;

		if ( chainBlend < 1.0 ) {

			for ( let j = 0; j < links.length; j ++ ) {

			  const linkIndex = links[ j ].index;
			  initialQuaternions[ j ].copy( bones[ linkIndex ].quaternion );

			}

		}

		for ( let i = 0; i < iteration; i ++ ) {

			let rotated = false;

			for ( let j = 0, jl = links.length; j < jl; j ++ ) {

				const link = bones[ links[ j ].index ];

				// skip this link and following links
				if ( links[ j ].enabled === false ) break;

				const limitation = links[ j ].limitation;
				const rotationMin = links[ j ].rotationMin;
				const rotationMax = links[ j ].rotationMax;

				// don't use getWorldPosition/Quaternion() here for the performance
				// because they call updateMatrixWorld( true ) inside.
				link.matrixWorld.decompose( _linkPos, _invLinkQ, _linkScale );
				_invLinkQ.invert();
				_effectorPos.setFromMatrixPosition( effector.matrixWorld );

				// work in link world
				_effectorVec.subVectors( _effectorPos, _linkPos );
				_effectorVec.applyQuaternion( _invLinkQ );
				_effectorVec.normalize();

				_targetVec.subVectors( _targetPos, _linkPos );
				_targetVec.applyQuaternion( _invLinkQ );
				_targetVec.normalize();

				let angle = _targetVec.dot( _effectorVec );

				if ( angle > 1.0 ) {

					angle = 1.0;

				} else if ( angle < - 1.0 ) {

					angle = - 1.0;

				}

				angle = math.acos( angle );

				// skip if changing angle is too small to prevent vibration of bone
				if ( angle < 1e-5 ) continue;

				if ( ik.minAngle !== undefined && angle < ik.minAngle ) {

					angle = ik.minAngle;

				}

				if ( ik.maxAngle !== undefined && angle > ik.maxAngle ) {

					angle = ik.maxAngle;

				}

				_axis.crossVectors( _effectorVec, _targetVec );
				_axis.normalize();

				_quaternion.setFromAxisAngle( _axis, angle );
				link.quaternion.multiply( _quaternion );

				// TODO: re-consider the limitation specification
				if ( limitation !== undefined ) {

					let c = link.quaternion.w;

					if ( c > 1.0 ) c = 1.0;

					const c2 = math.sqrt( 1 - c * c );
					link.quaternion.set( limitation.x * c2,
					                     limitation.y * c2,
					                     limitation.z * c2,
					                     c );

				}

				if ( rotationMin !== undefined ) {

					link.rotation.setFromVector3( _vector.setFromEuler( link.rotation ).max( rotationMin ) );

				}

				if ( rotationMax !== undefined ) {

					link.rotation.setFromVector3( _vector.setFromEuler( link.rotation ).min( rotationMax ) );

				}

				link.updateMatrixWorld( true );

				rotated = true;

			}

			if ( ! rotated ) break;

		}

		if ( chainBlend < 1.0 ) {

			for ( let j = 0; j < links.length; j ++ ) {

			  const linkIndex = links[ j ].index;
			  const link = bones[ linkIndex ];

			  this._workingQuaternion.copy( initialQuaternions[ j ] ).slerp( link.quaternion, chainBlend );

			  link.quaternion.copy( this._workingQuaternion );
			  link.updateMatrixWorld( true );

			}

		}

		  return this;

	}
```
</details>

##### `createHelper(sphereSize: number): CCDIKHelper`

<details><summary>Code</summary>

```ts
createHelper( sphereSize ) {

		return new CCDIKHelper( this.mesh, this.iks, sphereSize );

	}
```
</details>

##### `_valid(): void`

<details><summary>Code</summary>

```ts
_valid() {

		const iks = this.iks;
		const bones = this.mesh.skeleton.bones;

		for ( let i = 0, il = iks.length; i < il; i ++ ) {

			const ik = iks[ i ];
			const effector = bones[ ik.effector ];
			const links = ik.links;
			let link0, link1;

			link0 = effector;

			for ( let j = 0, jl = links.length; j < jl; j ++ ) {

				link1 = bones[ links[ j ].index ];

				if ( link0.parent !== link1 ) {

					console.warn( 'THREE.CCDIKSolver: bone ' + link0.name + ' is not the child of bone ' + link1.name );

				}

				link0 = link1;

			}

		}

	}
```
</details>

### `CCDIKHelper`

<details><summary>Class Code</summary>

```ts
class CCDIKHelper extends Object3D {

	/**
	 * @param {SkinnedMesh} mesh - The skinned mesh.
 	 * @param {Array<CCDIKSolver~IK>} [iks=[]] - The IK objects.
 	 * @param {number} [sphereSize=0.25] - The sphere size.
	 */
	constructor( mesh, iks = [], sphereSize = 0.25 ) {

		super();

		/**
		 * The skinned mesh this helper refers to.
		 *
		 * @type {SkinnedMesh}
		 */
		this.root = mesh;

		/**
		 * The IK objects.
		 *
		 * @type {Array<CCDIKSolver~IK>}
		 */
		this.iks = iks;

		this.matrix.copy( mesh.matrixWorld );
		this.matrixAutoUpdate = false;

		/**
		 * The helpers sphere geometry.
		 *
		 * @type {SkinnedMesh}
		 */
		this.sphereGeometry = new SphereGeometry( sphereSize, 16, 8 );

		/**
		 * The material for the target spheres.
		 *
		 * @type {MeshBasicMaterial}
		 */
		this.targetSphereMaterial = new MeshBasicMaterial( {
			color: new Color( 0xff8888 ),
			depthTest: false,
			depthWrite: false,
			transparent: true
		} );

		/**
		 * The material for the effector spheres.
		 *
		 * @type {MeshBasicMaterial}
		 */
		this.effectorSphereMaterial = new MeshBasicMaterial( {
			color: new Color( 0x88ff88 ),
			depthTest: false,
			depthWrite: false,
			transparent: true
		} );

		/**
		 * The material for the link spheres.
		 *
		 * @type {MeshBasicMaterial}
		 */
		this.linkSphereMaterial = new MeshBasicMaterial( {
			color: new Color( 0x8888ff ),
			depthTest: false,
			depthWrite: false,
			transparent: true
		} );

		/**
		 * A global line material.
		 *
		 * @type {LineBasicMaterial}
		 */
		this.lineMaterial = new LineBasicMaterial( {
			color: new Color( 0xff0000 ),
			depthTest: false,
			depthWrite: false,
			transparent: true
		} );

		this._init();

	}

	updateMatrixWorld( force ) {

		const mesh = this.root;

		if ( this.visible ) {

			let offset = 0;

			const iks = this.iks;
			const bones = mesh.skeleton.bones;

			_matrix.copy( mesh.matrixWorld ).invert();

			for ( let i = 0, il = iks.length; i < il; i ++ ) {

				const ik = iks[ i ];

				const targetBone = bones[ ik.target ];
				const effectorBone = bones[ ik.effector ];

				const targetMesh = this.children[ offset ++ ];
				const effectorMesh = this.children[ offset ++ ];

				targetMesh.position.copy( getPosition( targetBone, _matrix ) );
				effectorMesh.position.copy( getPosition( effectorBone, _matrix ) );

				for ( let j = 0, jl = ik.links.length; j < jl; j ++ ) {

					const link = ik.links[ j ];
					const linkBone = bones[ link.index ];

					const linkMesh = this.children[ offset ++ ];

					linkMesh.position.copy( getPosition( linkBone, _matrix ) );

				}

				const line = this.children[ offset ++ ];
				const array = line.geometry.attributes.position.array;

				setPositionOfBoneToAttributeArray( array, 0, targetBone, _matrix );
				setPositionOfBoneToAttributeArray( array, 1, effectorBone, _matrix );

				for ( let j = 0, jl = ik.links.length; j < jl; j ++ ) {

					const link = ik.links[ j ];
					const linkBone = bones[ link.index ];
					setPositionOfBoneToAttributeArray( array, j + 2, linkBone, _matrix );

				}

				line.geometry.attributes.position.needsUpdate = true;

			}

		}

		this.matrix.copy( mesh.matrixWorld );

		super.updateMatrixWorld( force );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance.
	 * Call this method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.sphereGeometry.dispose();

		this.targetSphereMaterial.dispose();
		this.effectorSphereMaterial.dispose();
		this.linkSphereMaterial.dispose();
		this.lineMaterial.dispose();

		const children = this.children;

		for ( let i = 0; i < children.length; i ++ ) {

			const child = children[ i ];

			if ( child.isLine ) child.geometry.dispose();

		}

	}

	// private method

	_init() {

		const scope = this;
		const iks = this.iks;

		function createLineGeometry( ik ) {

			const geometry = new BufferGeometry();
			const vertices = new Float32Array( ( 2 + ik.links.length ) * 3 );
			geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );

			return geometry;

		}

		function createTargetMesh() {

			return new Mesh( scope.sphereGeometry, scope.targetSphereMaterial );

		}

		function createEffectorMesh() {

			return new Mesh( scope.sphereGeometry, scope.effectorSphereMaterial );

		}

		function createLinkMesh() {

			return new Mesh( scope.sphereGeometry, scope.linkSphereMaterial );

		}

		function createLine( ik ) {

			return new Line( createLineGeometry( ik ), scope.lineMaterial );

		}

		for ( let i = 0, il = iks.length; i < il; i ++ ) {

			const ik = iks[ i ];

			this.add( createTargetMesh() );
			this.add( createEffectorMesh() );

			for ( let j = 0, jl = ik.links.length; j < jl; j ++ ) {

				this.add( createLinkMesh() );

			}

			this.add( createLine( ik ) );

		}

	}

}
```
</details>

#### Methods

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		const mesh = this.root;

		if ( this.visible ) {

			let offset = 0;

			const iks = this.iks;
			const bones = mesh.skeleton.bones;

			_matrix.copy( mesh.matrixWorld ).invert();

			for ( let i = 0, il = iks.length; i < il; i ++ ) {

				const ik = iks[ i ];

				const targetBone = bones[ ik.target ];
				const effectorBone = bones[ ik.effector ];

				const targetMesh = this.children[ offset ++ ];
				const effectorMesh = this.children[ offset ++ ];

				targetMesh.position.copy( getPosition( targetBone, _matrix ) );
				effectorMesh.position.copy( getPosition( effectorBone, _matrix ) );

				for ( let j = 0, jl = ik.links.length; j < jl; j ++ ) {

					const link = ik.links[ j ];
					const linkBone = bones[ link.index ];

					const linkMesh = this.children[ offset ++ ];

					linkMesh.position.copy( getPosition( linkBone, _matrix ) );

				}

				const line = this.children[ offset ++ ];
				const array = line.geometry.attributes.position.array;

				setPositionOfBoneToAttributeArray( array, 0, targetBone, _matrix );
				setPositionOfBoneToAttributeArray( array, 1, effectorBone, _matrix );

				for ( let j = 0, jl = ik.links.length; j < jl; j ++ ) {

					const link = ik.links[ j ];
					const linkBone = bones[ link.index ];
					setPositionOfBoneToAttributeArray( array, j + 2, linkBone, _matrix );

				}

				line.geometry.attributes.position.needsUpdate = true;

			}

		}

		this.matrix.copy( mesh.matrixWorld );

		super.updateMatrixWorld( force );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.sphereGeometry.dispose();

		this.targetSphereMaterial.dispose();
		this.effectorSphereMaterial.dispose();
		this.linkSphereMaterial.dispose();
		this.lineMaterial.dispose();

		const children = this.children;

		for ( let i = 0; i < children.length; i ++ ) {

			const child = children[ i ];

			if ( child.isLine ) child.geometry.dispose();

		}

	}
```
</details>

##### `_init(): void`

<details><summary>Code</summary>

```ts
_init() {

		const scope = this;
		const iks = this.iks;

		function createLineGeometry( ik ) {

			const geometry = new BufferGeometry();
			const vertices = new Float32Array( ( 2 + ik.links.length ) * 3 );
			geometry.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );

			return geometry;

		}

		function createTargetMesh() {

			return new Mesh( scope.sphereGeometry, scope.targetSphereMaterial );

		}

		function createEffectorMesh() {

			return new Mesh( scope.sphereGeometry, scope.effectorSphereMaterial );

		}

		function createLinkMesh() {

			return new Mesh( scope.sphereGeometry, scope.linkSphereMaterial );

		}

		function createLine( ik ) {

			return new Line( createLineGeometry( ik ), scope.lineMaterial );

		}

		for ( let i = 0, il = iks.length; i < il; i ++ ) {

			const ik = iks[ i ];

			this.add( createTargetMesh() );
			this.add( createEffectorMesh() );

			for ( let j = 0, jl = ik.links.length; j < jl; j ++ ) {

				this.add( createLinkMesh() );

			}

			this.add( createLine( ik ) );

		}

	}
```
</details>


---