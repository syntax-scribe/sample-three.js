[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SkeletonUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 27 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/utils/SkeletonUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationClip` | `three` |
| `AnimationMixer` | `three` |
| `Matrix4` | `three` |
| `Quaternion` | `three` |
| `QuaternionKeyframeTrack` | `three` |
| `SkeletonHelper` | `three` |
| `Vector3` | `three` |
| `VectorKeyframeTrack` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `quat` | `any` | let/var | `new Quaternion()` | ✗ |
| `scale` | `any` | let/var | `new Vector3()` | ✗ |
| `relativeMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `globalMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `sourceBones` | `any` | let/var | `source.isObject3D ? source.skeleton.bones : getBones( source )` | ✗ |
| `bones` | `any` | let/var | `target.isObject3D ? target.skeleton.bones : getBones( target )` | ✗ |
| `bone` | `any` | let/var | `*not shown*` | ✗ |
| `name` | `any` | let/var | `*not shown*` | ✗ |
| `boneTo` | `any` | let/var | `*not shown*` | ✗ |
| `bonesPosition` | `any` | let/var | `*not shown*` | ✗ |
| `delta` | `number` | let/var | `clip.duration / ( numFrames - 1 )` | ✗ |
| `convertedTracks` | `any[]` | let/var | `[]` | ✗ |
| `mixer` | `any` | let/var | `new AnimationMixer( source )` | ✗ |
| `boneDatas` | `any[]` | let/var | `[]` | ✗ |
| `positionOffset` | `any` | let/var | `*not shown*` | ✗ |
| `bone` | `any` | let/var | `*not shown*` | ✗ |
| `boneTo` | `any` | let/var | `*not shown*` | ✗ |
| `boneData` | `any` | let/var | `*not shown*` | ✗ |
| `name` | `any` | let/var | `*not shown*` | ✗ |
| `start` | `number` | let/var | `0` | ✗ |
| `end` | `number` | let/var | `numFrames` | ✗ |
| `time` | `number` | let/var | `frame * delta` | ✗ |
| `sourceLookup` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `cloneLookup` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `clonedMesh` | `any` | let/var | `node` | ✗ |
| `sourceBones` | `any` | let/var | `sourceMesh.skeleton.bones` | ✗ |
| `source` | `any` | let/var | `new SkeletonHelper( skeleton.bones[ 0 ] )` | ✗ |


---

## Functions

### `getBoneName(bone: any, options: any): any`

**JSDoc:**
```typescript
/**
 * @module SkeletonUtils
 * @three_import import * as SkeletonUtils from 'three/addons/utils/SkeletonUtils.js';
 */
```

**Parameters:**

- **`bone`** `any`
- **`options`** `any`

**Returns:** `any`

**Calls:**

- `options.getBoneName`

<details><summary>Code</summary>

```typescript
function getBoneName( bone, options ) {

	if ( options.getBoneName !== undefined ) {

		return options.getBoneName( bone );

	}

	return options.names[ bone.name ];

}
```
</details>

### `retarget(target: Object3D, source: Object3D, options: any): void`

**JSDoc:**
```typescript
/**
 * Retargets the skeleton from the given source 3D object to the
 * target 3D object.
 *
 * @param {Object3D} target - The target 3D object.
 * @param {Object3D} source - The source 3D object.
 * @param {module:SkeletonUtils~RetargetOptions} options - The options.
 */
```

**Parameters:**

- **`target`** `Object3D`
- **`source`** `Object3D`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `getBones`
- `target.skeleton.pose`
- `bonesPosition.push`
- `bones[ i ].position.clone`
- `target.updateMatrixWorld`
- `target.matrixWorld.identity`
- `target.children[ i ].updateMatrixWorld`
- `getBoneName`
- `getBoneByName`
- `globalMatrix.copy`
- `boneTo.updateMatrixWorld`
- `relativeMatrix.copy`
- `relativeMatrix.copy( target.matrixWorld ).invert`
- `relativeMatrix.multiply`
- `scale.setFromMatrixScale`
- `relativeMatrix.scale`
- `scale.set`
- `globalMatrix.makeRotationFromQuaternion`
- `quat.setFromRotationMatrix`
- `globalMatrix.multiply`
- `globalMatrix.copyPosition`
- `bone.matrix.copy( bone.parent.matrixWorld ).invert`
- `bone.matrix.multiply`
- `bone.matrix.copy`
- `bone.matrix.decompose`
- `bone.updateMatrixWorld`
- `bone.position.copy`

**Internal Comments:**
```
// reset bones
// reset matrix (x4)
// reset children matrix
// ignore scale to extract rotation (x4)
// apply to global matrix (x4)
// restore matrix (x4)
```

<details><summary>Code</summary>

```typescript
function retarget( target, source, options = {} ) {

	const quat = new Quaternion(),
		scale = new Vector3(),
		relativeMatrix = new Matrix4(),
		globalMatrix = new Matrix4();

	options.preserveBoneMatrix = options.preserveBoneMatrix !== undefined ? options.preserveBoneMatrix : true;
	options.preserveBonePositions = options.preserveBonePositions !== undefined ? options.preserveBonePositions : true;
	options.useTargetMatrix = options.useTargetMatrix !== undefined ? options.useTargetMatrix : false;
	options.hip = options.hip !== undefined ? options.hip : 'hip';
	options.hipInfluence = options.hipInfluence !== undefined ? options.hipInfluence : new Vector3( 1, 1, 1 );
	options.scale = options.scale !== undefined ? options.scale : 1;
	options.names = options.names || {};

	const sourceBones = source.isObject3D ? source.skeleton.bones : getBones( source ),
		bones = target.isObject3D ? target.skeleton.bones : getBones( target );

	let bone, name, boneTo,
		bonesPosition;

	// reset bones

	if ( target.isObject3D ) {

		target.skeleton.pose();

	} else {

		options.useTargetMatrix = true;
		options.preserveBoneMatrix = false;

	}

	if ( options.preserveBonePositions ) {

		bonesPosition = [];

		for ( let i = 0; i < bones.length; i ++ ) {

			bonesPosition.push( bones[ i ].position.clone() );

		}

	}

	if ( options.preserveBoneMatrix ) {

		// reset matrix

		target.updateMatrixWorld();

		target.matrixWorld.identity();

		// reset children matrix

		for ( let i = 0; i < target.children.length; ++ i ) {

			target.children[ i ].updateMatrixWorld( true );

		}

	}

	for ( let i = 0; i < bones.length; ++ i ) {

		bone = bones[ i ];
		name = getBoneName( bone, options );

		boneTo = getBoneByName( name, sourceBones );

		globalMatrix.copy( bone.matrixWorld );

		if ( boneTo ) {

			boneTo.updateMatrixWorld();

			if ( options.useTargetMatrix ) {

				relativeMatrix.copy( boneTo.matrixWorld );

			} else {

				relativeMatrix.copy( target.matrixWorld ).invert();
				relativeMatrix.multiply( boneTo.matrixWorld );

			}

			// ignore scale to extract rotation

			scale.setFromMatrixScale( relativeMatrix );
			relativeMatrix.scale( scale.set( 1 / scale.x, 1 / scale.y, 1 / scale.z ) );

			// apply to global matrix

			globalMatrix.makeRotationFromQuaternion( quat.setFromRotationMatrix( relativeMatrix ) );

			if ( target.isObject3D ) {

				if ( options.localOffsets ) {

					if ( options.localOffsets[ bone.name ] ) {

						globalMatrix.multiply( options.localOffsets[ bone.name ] );

					}

				}

			}

			globalMatrix.copyPosition( relativeMatrix );

		}

		if ( name === options.hip ) {

			globalMatrix.elements[ 12 ] *= options.scale * options.hipInfluence.x;
			globalMatrix.elements[ 13 ] *= options.scale * options.hipInfluence.y;
			globalMatrix.elements[ 14 ] *= options.scale * options.hipInfluence.z;

			if ( options.hipPosition !== undefined ) {

				globalMatrix.elements[ 12 ] += options.hipPosition.x * options.scale;
				globalMatrix.elements[ 13 ] += options.hipPosition.y * options.scale;
				globalMatrix.elements[ 14 ] += options.hipPosition.z * options.scale;

			}

		}

		if ( bone.parent ) {

			bone.matrix.copy( bone.parent.matrixWorld ).invert();
			bone.matrix.multiply( globalMatrix );

		} else {

			bone.matrix.copy( globalMatrix );

		}

		bone.matrix.decompose( bone.position, bone.quaternion, bone.scale );

		bone.updateMatrixWorld();

	}

	if ( options.preserveBonePositions ) {

		for ( let i = 0; i < bones.length; ++ i ) {

			bone = bones[ i ];
			name = getBoneName( bone, options ) || bone.name;

			if ( name !== options.hip ) {

				bone.position.copy( bonesPosition[ i ] );

			}

		}

	}

	if ( options.preserveBoneMatrix ) {

		// restore matrix

		target.updateMatrixWorld( true );

	}

}
```
</details>

### `retargetClip(target: Object3D, source: Object3D, clip: AnimationClip, options: any): AnimationClip`

**JSDoc:**
```typescript
/**
 * Retargets the animation clip of the source object to the
 * target 3D object.
 *
 * @param {Object3D} target - The target 3D object.
 * @param {Object3D} source - The source 3D object.
 * @param {AnimationClip} clip - The animation clip.
 * @param {module:SkeletonUtils~RetargetOptions} options - The options.
 * @return {AnimationClip} The retargeted animation clip.
 */
```

**Parameters:**

- **`target`** `Object3D`
- **`source`** `Object3D`
- **`clip`** `AnimationClip`
- **`options`** `any`

**Returns:** `AnimationClip`

**Calls:**

- `Math.max`
- `clip.tracks.map`
- `getHelperFromSkeleton`
- `Math.round`
- `getBones`
- `mixer.clipAction( clip ).play`
- `Math.min`
- `mixer.update`
- `source.updateMatrixWorld`
- `retarget`
- `getBoneName`
- `getBoneByName`
- `bone.position.clone`
- `bone.position.sub`
- `bone.position.toArray`
- `bone.quaternion.toArray`
- `convertedTracks.push`
- `mixer.uncacheAction`

**Internal Comments:**
```
// Calculate the fps from the source clip based on the track with the most frames, unless fps is already provided. (x4)
// trim (x2)
//
// last mixer update before final loop iteration (x4)
// make sure we do not go over or equal to clip duration (x4)
```

<details><summary>Code</summary>

```typescript
function retargetClip( target, source, clip, options = {} ) {

	options.useFirstFramePosition = options.useFirstFramePosition !== undefined ? options.useFirstFramePosition : false;

	// Calculate the fps from the source clip based on the track with the most frames, unless fps is already provided.
	options.fps = options.fps !== undefined ? options.fps : ( Math.max( ...clip.tracks.map( track => track.times.length ) ) / clip.duration );
	options.names = options.names || [];

	if ( ! source.isObject3D ) {

		source = getHelperFromSkeleton( source );

	}

	const numFrames = Math.round( clip.duration * ( options.fps / 1000 ) * 1000 ),
		delta = clip.duration / ( numFrames - 1 ),
		convertedTracks = [],
		mixer = new AnimationMixer( source ),
		bones = getBones( target.skeleton ),
		boneDatas = [];

	let positionOffset,
		bone, boneTo, boneData,
		name;

	mixer.clipAction( clip ).play();

	// trim

	let start = 0, end = numFrames;

	if ( options.trim !== undefined ) {

		start = Math.round( options.trim[ 0 ] * options.fps );
		end = Math.min( Math.round( options.trim[ 1 ] * options.fps ), numFrames ) - start;

		mixer.update( options.trim[ 0 ] );

	} else {

		mixer.update( 0 );

	}

	source.updateMatrixWorld();

	//

	for ( let frame = 0; frame < end; ++ frame ) {

		const time = frame * delta;

		retarget( target, source, options );

		for ( let j = 0; j < bones.length; ++ j ) {

			bone = bones[ j ];
			name = getBoneName( bone, options ) || bone.name;
			boneTo = getBoneByName( name, source.skeleton );

			if ( boneTo ) {

				boneData = boneDatas[ j ] = boneDatas[ j ] || { bone: bone };

				if ( options.hip === name ) {

					if ( ! boneData.pos ) {

						boneData.pos = {
							times: new Float32Array( end ),
							values: new Float32Array( end * 3 )
						};

					}

					if ( options.useFirstFramePosition ) {

						if ( frame === 0 ) {

							positionOffset = bone.position.clone();

						}

						bone.position.sub( positionOffset );

					}

					boneData.pos.times[ frame ] = time;

					bone.position.toArray( boneData.pos.values, frame * 3 );

				}

				if ( ! boneData.quat ) {

					boneData.quat = {
						times: new Float32Array( end ),
						values: new Float32Array( end * 4 )
					};

				}

				boneData.quat.times[ frame ] = time;

				bone.quaternion.toArray( boneData.quat.values, frame * 4 );

			}

		}

		if ( frame === end - 2 ) {

			// last mixer update before final loop iteration
			// make sure we do not go over or equal to clip duration
			mixer.update( delta - 0.0000001 );

		} else {

			mixer.update( delta );

		}

		source.updateMatrixWorld();

	}

	for ( let i = 0; i < boneDatas.length; ++ i ) {

		boneData = boneDatas[ i ];

		if ( boneData ) {

			if ( boneData.pos ) {

				convertedTracks.push( new VectorKeyframeTrack(
					'.bones[' + boneData.bone.name + '].position',
					boneData.pos.times,
					boneData.pos.values
				) );

			}

			convertedTracks.push( new QuaternionKeyframeTrack(
				'.bones[' + boneData.bone.name + '].quaternion',
				boneData.quat.times,
				boneData.quat.values
			) );

		}

	}

	mixer.uncacheAction( clip );

	return new AnimationClip( clip.name, - 1, convertedTracks );

}
```
</details>

### `clone(source: Object3D): Object3D`

**JSDoc:**
```typescript
/**
 * Clones the given 3D object and its descendants, ensuring that any `SkinnedMesh` instances are
 * correctly associated with their bones. Bones are also cloned, and must be descendants of the
 * object passed to this method. Other data, like geometries and materials, are reused by reference.
 *
 * @param {Object3D} source - The 3D object to clone.
 * @return {Object3D} The cloned 3D object.
 */
```

**Parameters:**

- **`source`** `Object3D`

**Returns:** `Object3D`

**Calls:**

- `source.clone`
- `parallelTraverse`
- `sourceLookup.set`
- `cloneLookup.set`
- `clone.traverse`
- `sourceLookup.get`
- `sourceMesh.skeleton.clone`
- `clonedMesh.bindMatrix.copy`
- `sourceBones.map`
- `cloneLookup.get`
- `clonedMesh.bind`

<details><summary>Code</summary>

```typescript
function clone( source ) {

	const sourceLookup = new Map();
	const cloneLookup = new Map();

	const clone = source.clone();

	parallelTraverse( source, clone, function ( sourceNode, clonedNode ) {

		sourceLookup.set( clonedNode, sourceNode );
		cloneLookup.set( sourceNode, clonedNode );

	} );

	clone.traverse( function ( node ) {

		if ( ! node.isSkinnedMesh ) return;

		const clonedMesh = node;
		const sourceMesh = sourceLookup.get( node );
		const sourceBones = sourceMesh.skeleton.bones;

		clonedMesh.skeleton = sourceMesh.skeleton.clone();
		clonedMesh.bindMatrix.copy( sourceMesh.bindMatrix );

		clonedMesh.skeleton.bones = sourceBones.map( function ( bone ) {

			return cloneLookup.get( bone );

		} );

		clonedMesh.bind( clonedMesh.skeleton, clonedMesh.bindMatrix );

	} );

	return clone;

}
```
</details>

### `getBoneByName(name: any, skeleton: any): any`

**Parameters:**

- **`name`** `any`
- **`skeleton`** `any`

**Returns:** `any`

**Calls:**

- `getBones`

<details><summary>Code</summary>

```typescript
function getBoneByName( name, skeleton ) {

	for ( let i = 0, bones = getBones( skeleton ); i < bones.length; i ++ ) {

		if ( name === bones[ i ].name )

			return bones[ i ];

	}

}
```
</details>

### `getBones(skeleton: any): any`

**Parameters:**

- **`skeleton`** `any`

**Returns:** `any`

**Calls:**

- `Array.isArray`

<details><summary>Code</summary>

```typescript
function getBones( skeleton ) {

	return Array.isArray( skeleton ) ? skeleton : skeleton.bones;

}
```
</details>

### `getHelperFromSkeleton(skeleton: any): any`

**Parameters:**

- **`skeleton`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getHelperFromSkeleton( skeleton ) {

	const source = new SkeletonHelper( skeleton.bones[ 0 ] );
	source.skeleton = skeleton;

	return source;

}
```
</details>

### `parallelTraverse(a: any, b: any, callback: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`callback`** `any`

**Returns:** `void`

**Calls:**

- `callback`
- `parallelTraverse`

<details><summary>Code</summary>

```typescript
function parallelTraverse( a, b, callback ) {

	callback( a, b );

	for ( let i = 0; i < a.children.length; i ++ ) {

		parallelTraverse( a.children[ i ], b.children[ i ], callback );

	}

}
```
</details>


---