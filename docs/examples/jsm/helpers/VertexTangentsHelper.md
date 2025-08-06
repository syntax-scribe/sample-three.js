[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `VertexTangentsHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/VertexTangentsHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Float32BufferAttribute` | `three` |
| `LineSegments` | `three` |
| `LineBasicMaterial` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_v1` | `any` | let/var | `new Vector3()` | ✗ |
| `_v2` | `any` | let/var | `new Vector3()` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `nTangents` | `any` | let/var | `object.geometry.attributes.tangent.count` | ✗ |
| `positions` | `any` | let/var | `new Float32BufferAttribute( nTangents * 2 * 3, 3 )` | ✗ |
| `matrixWorld` | `any` | let/var | `this.object.matrixWorld` | ✗ |
| `position` | `any` | let/var | `this.geometry.attributes.position` | ✗ |
| `objGeometry` | `any` | let/var | `this.object.geometry` | ✗ |
| `objPos` | `any` | let/var | `objGeometry.attributes.position` | ✗ |
| `objTan` | `any` | let/var | `objGeometry.attributes.tangent` | ✗ |
| `idx` | `number` | let/var | `0` | ✗ |


---

## Functions

### `VertexTangentsHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the vertex normals preview based on the object's world transform.
	 */
```

**Returns:** `void`

**Calls:**

- `this.object.updateMatrixWorld`
- `_v1.fromBufferAttribute( objPos, j ).applyMatrix4`
- `_v2.fromBufferAttribute`
- `_v2.transformDirection( matrixWorld ).multiplyScalar( this.size ).add`
- `position.setXYZ`

**Internal Comments:**
```
// (x2)
// for simplicity, ignore index and drawcalls, and render every tangent
```

<details><summary>Code</summary>

```typescript
update() {

		this.object.updateMatrixWorld( true );

		const matrixWorld = this.object.matrixWorld;

		const position = this.geometry.attributes.position;

		//

		const objGeometry = this.object.geometry;

		const objPos = objGeometry.attributes.position;

		const objTan = objGeometry.attributes.tangent;

		let idx = 0;

		// for simplicity, ignore index and drawcalls, and render every tangent

		for ( let j = 0, jl = objPos.count; j < jl; j ++ ) {

			_v1.fromBufferAttribute( objPos, j ).applyMatrix4( matrixWorld );

			_v2.fromBufferAttribute( objTan, j );

			_v2.transformDirection( matrixWorld ).multiplyScalar( this.size ).add( _v1 );

			position.setXYZ( idx, _v1.x, _v1.y, _v1.z );

			idx = idx + 1;

			position.setXYZ( idx, _v2.x, _v2.y, _v2.z );

			idx = idx + 1;

		}

		position.needsUpdate = true;

	}
```
</details>

### `VertexTangentsHelper.dispose(): void`

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


---

## Classes

### `VertexTangentsHelper`

<details><summary>Class Code</summary>

```ts
class VertexTangentsHelper extends LineSegments {

	/**
	 * Constructs a new vertex tangents helper.
	 *
	 * @param {Object3D} object - The object for which to visualize vertex tangents.
	 * @param {number} [size=1] - The helper's size.
	 * @param {number|Color|string} [color=0xff0000] - The helper's color.
	 */
	constructor( object, size = 1, color = 0x00ffff ) {

		const geometry = new BufferGeometry();

		const nTangents = object.geometry.attributes.tangent.count;
		const positions = new Float32BufferAttribute( nTangents * 2 * 3, 3 );

		geometry.setAttribute( 'position', positions );

		super( geometry, new LineBasicMaterial( { color, toneMapped: false } ) );

		/**
		 * The object for which to visualize vertex tangents.
		 *
		 * @type {Object3D}
		 */
		this.object = object;

		/**
		 * The helper's size.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.size = size;

		this.type = 'VertexTangentsHelper';

		/**
		 * Overwritten and set to `false` since the object's world transformation
		 * is encoded in the helper's geometry data.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.matrixAutoUpdate = false;

		this.update();

	}

	/**
	 * Updates the vertex normals preview based on the object's world transform.
	 */
	update() {

		this.object.updateMatrixWorld( true );

		const matrixWorld = this.object.matrixWorld;

		const position = this.geometry.attributes.position;

		//

		const objGeometry = this.object.geometry;

		const objPos = objGeometry.attributes.position;

		const objTan = objGeometry.attributes.tangent;

		let idx = 0;

		// for simplicity, ignore index and drawcalls, and render every tangent

		for ( let j = 0, jl = objPos.count; j < jl; j ++ ) {

			_v1.fromBufferAttribute( objPos, j ).applyMatrix4( matrixWorld );

			_v2.fromBufferAttribute( objTan, j );

			_v2.transformDirection( matrixWorld ).multiplyScalar( this.size ).add( _v1 );

			position.setXYZ( idx, _v1.x, _v1.y, _v1.z );

			idx = idx + 1;

			position.setXYZ( idx, _v2.x, _v2.y, _v2.z );

			idx = idx + 1;

		}

		position.needsUpdate = true;

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

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		this.object.updateMatrixWorld( true );

		const matrixWorld = this.object.matrixWorld;

		const position = this.geometry.attributes.position;

		//

		const objGeometry = this.object.geometry;

		const objPos = objGeometry.attributes.position;

		const objTan = objGeometry.attributes.tangent;

		let idx = 0;

		// for simplicity, ignore index and drawcalls, and render every tangent

		for ( let j = 0, jl = objPos.count; j < jl; j ++ ) {

			_v1.fromBufferAttribute( objPos, j ).applyMatrix4( matrixWorld );

			_v2.fromBufferAttribute( objTan, j );

			_v2.transformDirection( matrixWorld ).multiplyScalar( this.size ).add( _v1 );

			position.setXYZ( idx, _v1.x, _v1.y, _v1.z );

			idx = idx + 1;

			position.setXYZ( idx, _v2.x, _v2.y, _v2.z );

			idx = idx + 1;

		}

		position.needsUpdate = true;

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