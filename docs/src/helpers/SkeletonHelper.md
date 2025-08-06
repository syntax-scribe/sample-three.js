[⬅️ Back to Table of Contents](../../index.md)

# 📄 `SkeletonHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/SkeletonHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LineSegments` | `../objects/LineSegments.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `LineBasicMaterial` | `../materials/LineBasicMaterial.js` |
| `Color` | `../math/Color.js` |
| `Vector3` | `../math/Vector3.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_boneMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_matrixWorldInv` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `colors` | `any[]` | let/var | `[]` | ✗ |
| `bone` | `any` | let/var | `bones[ i ]` | ✗ |
| `material` | `LineBasicMaterial` | let/var | `new LineBasicMaterial( { vertexColors: true, depthTest: false, depthWrite: fa...` | ✗ |
| `color1` | `Color` | let/var | `new Color( 0x0000ff )` | ✗ |
| `color2` | `Color` | let/var | `new Color( 0x00ff00 )` | ✗ |
| `bones` | `Bone[]` | let/var | `this.bones` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `bone` | `Bone` | let/var | `bones[ i ]` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `boneList` | `any[]` | let/var | `[]` | ✗ |


---

## Functions

### `SkeletonHelper.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `geometry.getAttribute`
- `_matrixWorldInv.copy( this.root.matrixWorld ).invert`
- `_boneMatrix.multiplyMatrices`
- `_vector.setFromMatrixPosition`
- `position.setXYZ`
- `super.updateMatrixWorld`

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		const bones = this.bones;

		const geometry = this.geometry;
		const position = geometry.getAttribute( 'position' );

		_matrixWorldInv.copy( this.root.matrixWorld ).invert();

		for ( let i = 0, j = 0; i < bones.length; i ++ ) {

			const bone = bones[ i ];

			if ( bone.parent && bone.parent.isBone ) {

				_boneMatrix.multiplyMatrices( _matrixWorldInv, bone.matrixWorld );
				_vector.setFromMatrixPosition( _boneMatrix );
				position.setXYZ( j, _vector.x, _vector.y, _vector.z );

				_boneMatrix.multiplyMatrices( _matrixWorldInv, bone.parent.matrixWorld );
				_vector.setFromMatrixPosition( _boneMatrix );
				position.setXYZ( j + 1, _vector.x, _vector.y, _vector.z );

				j += 2;

			}

		}

		geometry.getAttribute( 'position' ).needsUpdate = true;

		super.updateMatrixWorld( force );

	}
```
</details>

### `SkeletonHelper.setColors(color1: Color, color2: Color): SkeletonHelper`

**JSDoc:**
```typescript
/**
	 * Defines the colors of the helper.
	 *
	 * @param {Color} color1 - The first line color for each bone.
	 * @param {Color} color2 - The second line color for each bone.
	 * @return {SkeletonHelper} A reference to this helper.
	 */
```

**Parameters:**

- **`color1`** `Color`
- **`color2`** `Color`

**Returns:** `SkeletonHelper`

**Calls:**

- `geometry.getAttribute`
- `colorAttribute.setXYZ`

<details><summary>Code</summary>

```typescript
setColors( color1, color2 ) {

		const geometry = this.geometry;
		const colorAttribute = geometry.getAttribute( 'color' );

		for ( let i = 0; i < colorAttribute.count; i += 2 ) {

			colorAttribute.setXYZ( i, color1.r, color1.g, color1.b );
			colorAttribute.setXYZ( i + 1, color2.r, color2.g, color2.b );

		}

		colorAttribute.needsUpdate = true;

		return this;

	}
```
</details>

### `SkeletonHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.geometry.dispose`
- `this.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>

### `getBoneList(object: any): any`

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `boneList.push`
- `getBoneList`

<details><summary>Code</summary>

```typescript
function getBoneList( object ) {

	const boneList = [];

	if ( object.isBone === true ) {

		boneList.push( object );

	}

	for ( let i = 0; i < object.children.length; i ++ ) {

		boneList.push( ...getBoneList( object.children[ i ] ) );

	}

	return boneList;

}
```
</details>


---

## Classes

### `SkeletonHelper`

<details><summary>Class Code</summary>

```ts
class SkeletonHelper extends LineSegments {

	/**
	 * Constructs a new skeleton helper.
	 *
	 * @param {Object3D} object -  Usually an instance of {@link SkinnedMesh}. However, any 3D object
	 * can be used if it represents a hierarchy of bones (see {@link Bone}).
	 */
	constructor( object ) {

		const bones = getBoneList( object );

		const geometry = new BufferGeometry();

		const vertices = [];
		const colors = [];

		for ( let i = 0; i < bones.length; i ++ ) {

			const bone = bones[ i ];

			if ( bone.parent && bone.parent.isBone ) {

				vertices.push( 0, 0, 0 );
				vertices.push( 0, 0, 0 );
				colors.push( 0, 0, 0 );
				colors.push( 0, 0, 0 );

			}

		}

		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

		const material = new LineBasicMaterial( { vertexColors: true, depthTest: false, depthWrite: false, toneMapped: false, transparent: true } );

		super( geometry, material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSkeletonHelper = true;

		this.type = 'SkeletonHelper';

		/**
		 * The object being visualized.
		 *
		 * @type {Object3D}
		 */
		this.root = object;

		/**
		 * The list of bones that the helper visualizes.
		 *
		 * @type {Array<Bone>}
		 */
		this.bones = bones;

		this.matrix = object.matrixWorld;
		this.matrixAutoUpdate = false;

		// colors

		const color1 = new Color( 0x0000ff );
		const color2 = new Color( 0x00ff00 );

		this.setColors( color1, color2 );

	}

	updateMatrixWorld( force ) {

		const bones = this.bones;

		const geometry = this.geometry;
		const position = geometry.getAttribute( 'position' );

		_matrixWorldInv.copy( this.root.matrixWorld ).invert();

		for ( let i = 0, j = 0; i < bones.length; i ++ ) {

			const bone = bones[ i ];

			if ( bone.parent && bone.parent.isBone ) {

				_boneMatrix.multiplyMatrices( _matrixWorldInv, bone.matrixWorld );
				_vector.setFromMatrixPosition( _boneMatrix );
				position.setXYZ( j, _vector.x, _vector.y, _vector.z );

				_boneMatrix.multiplyMatrices( _matrixWorldInv, bone.parent.matrixWorld );
				_vector.setFromMatrixPosition( _boneMatrix );
				position.setXYZ( j + 1, _vector.x, _vector.y, _vector.z );

				j += 2;

			}

		}

		geometry.getAttribute( 'position' ).needsUpdate = true;

		super.updateMatrixWorld( force );

	}

	/**
	 * Defines the colors of the helper.
	 *
	 * @param {Color} color1 - The first line color for each bone.
	 * @param {Color} color2 - The second line color for each bone.
	 * @return {SkeletonHelper} A reference to this helper.
	 */
	setColors( color1, color2 ) {

		const geometry = this.geometry;
		const colorAttribute = geometry.getAttribute( 'color' );

		for ( let i = 0; i < colorAttribute.count; i += 2 ) {

			colorAttribute.setXYZ( i, color1.r, color1.g, color1.b );
			colorAttribute.setXYZ( i + 1, color2.r, color2.g, color2.b );

		}

		colorAttribute.needsUpdate = true;

		return this;

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}

}
```
</details>

#### Methods

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		const bones = this.bones;

		const geometry = this.geometry;
		const position = geometry.getAttribute( 'position' );

		_matrixWorldInv.copy( this.root.matrixWorld ).invert();

		for ( let i = 0, j = 0; i < bones.length; i ++ ) {

			const bone = bones[ i ];

			if ( bone.parent && bone.parent.isBone ) {

				_boneMatrix.multiplyMatrices( _matrixWorldInv, bone.matrixWorld );
				_vector.setFromMatrixPosition( _boneMatrix );
				position.setXYZ( j, _vector.x, _vector.y, _vector.z );

				_boneMatrix.multiplyMatrices( _matrixWorldInv, bone.parent.matrixWorld );
				_vector.setFromMatrixPosition( _boneMatrix );
				position.setXYZ( j + 1, _vector.x, _vector.y, _vector.z );

				j += 2;

			}

		}

		geometry.getAttribute( 'position' ).needsUpdate = true;

		super.updateMatrixWorld( force );

	}
```
</details>

##### `setColors(color1: Color, color2: Color): SkeletonHelper`

<details><summary>Code</summary>

```ts
setColors( color1, color2 ) {

		const geometry = this.geometry;
		const colorAttribute = geometry.getAttribute( 'color' );

		for ( let i = 0; i < colorAttribute.count; i += 2 ) {

			colorAttribute.setXYZ( i, color1.r, color1.g, color1.b );
			colorAttribute.setXYZ( i + 1, color2.r, color2.g, color2.b );

		}

		colorAttribute.needsUpdate = true;

		return this;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>


---