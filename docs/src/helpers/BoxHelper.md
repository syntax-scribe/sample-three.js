[⬅️ Back to Table of Contents](../../index.md)

# 📄 `BoxHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/BoxHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box3` | `../math/Box3.js` |
| `LineSegments` | `../objects/LineSegments.js` |
| `LineBasicMaterial` | `../materials/LineBasicMaterial.js` |
| `BufferAttribute` | `../core/BufferAttribute.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_box` | `Box3` | let/var | `new Box3()` | ✗ |
| `indices` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array( [ 0, 1, 1, 2, 2, 3, 3, 0, 4, 5, 5, 6, 6, 7, 7, 4, 0, 4, 1, 5...` | ✗ |
| `positions` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 8 * 3 )` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `min` | `Vector3` | let/var | `_box.min` | ✗ |
| `max` | `Vector3` | let/var | `_box.max` | ✗ |
| `position` | `any` | let/var | `this.geometry.attributes.position` | ✗ |
| `array` | `any` | let/var | `position.array` | ✗ |


---

## Functions

### `BoxHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the helper's geometry to match the dimensions of the object,
	 * including any children.
	 */
```

**Returns:** `void`

**Calls:**

- `_box.setFromObject`
- `_box.isEmpty`
- `this.geometry.computeBoundingSphere`

**Internal Comments:**
```
/*
			5____4
		1/___0/|
		| 6__|_7
		2/___3/

		0: max.x, max.y, max.z
		1: min.x, max.y, max.z
		2: min.x, min.y, max.z
		3: max.x, min.y, max.z
		4: max.x, max.y, min.z
		5: min.x, max.y, min.z
		6: min.x, min.y, min.z
		7: max.x, min.y, min.z
		*/ (x2)
```

<details><summary>Code</summary>

```typescript
update() {

		if ( this.object !== undefined ) {

			_box.setFromObject( this.object );

		}

		if ( _box.isEmpty() ) return;

		const min = _box.min;
		const max = _box.max;

		/*
			5____4
		1/___0/|
		| 6__|_7
		2/___3/

		0: max.x, max.y, max.z
		1: min.x, max.y, max.z
		2: min.x, min.y, max.z
		3: max.x, min.y, max.z
		4: max.x, max.y, min.z
		5: min.x, max.y, min.z
		6: min.x, min.y, min.z
		7: max.x, min.y, min.z
		*/

		const position = this.geometry.attributes.position;
		const array = position.array;

		array[ 0 ] = max.x; array[ 1 ] = max.y; array[ 2 ] = max.z;
		array[ 3 ] = min.x; array[ 4 ] = max.y; array[ 5 ] = max.z;
		array[ 6 ] = min.x; array[ 7 ] = min.y; array[ 8 ] = max.z;
		array[ 9 ] = max.x; array[ 10 ] = min.y; array[ 11 ] = max.z;
		array[ 12 ] = max.x; array[ 13 ] = max.y; array[ 14 ] = min.z;
		array[ 15 ] = min.x; array[ 16 ] = max.y; array[ 17 ] = min.z;
		array[ 18 ] = min.x; array[ 19 ] = min.y; array[ 20 ] = min.z;
		array[ 21 ] = max.x; array[ 22 ] = min.y; array[ 23 ] = min.z;

		position.needsUpdate = true;

		this.geometry.computeBoundingSphere();

	}
```
</details>

### `BoxHelper.setFromObject(object: Object3D): BoxHelper`

**JSDoc:**
```typescript
/**
	 * Updates the wireframe box for the passed object.
	 *
	 * @param {Object3D} object - The 3D object to create the helper for.
	 * @return {BoxHelper} A reference to this instance.
	 */
```

**Parameters:**

- **`object`** `Object3D`

**Returns:** `BoxHelper`

**Calls:**

- `this.update`

<details><summary>Code</summary>

```typescript
setFromObject( object ) {

		this.object = object;
		this.update();

		return this;

	}
```
</details>

### `BoxHelper.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.object = source.object;

		return this;

	}
```
</details>

### `BoxHelper.dispose(): void`

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

### `BoxHelper`

<details><summary>Class Code</summary>

```ts
class BoxHelper extends LineSegments {

	/**
	 * Constructs a new box helper.
	 *
	 * @param {Object3D} [object] - The 3D object to show the world-axis-aligned bounding box.
	 * @param {number|Color|string} [color=0xffff00] - The box's color.
	 */
	constructor( object, color = 0xffff00 ) {

		const indices = new Uint16Array( [ 0, 1, 1, 2, 2, 3, 3, 0, 4, 5, 5, 6, 6, 7, 7, 4, 0, 4, 1, 5, 2, 6, 3, 7 ] );
		const positions = new Float32Array( 8 * 3 );

		const geometry = new BufferGeometry();
		geometry.setIndex( new BufferAttribute( indices, 1 ) );
		geometry.setAttribute( 'position', new BufferAttribute( positions, 3 ) );

		super( geometry, new LineBasicMaterial( { color: color, toneMapped: false } ) );

		/**
		 * The 3D object being visualized.
		 *
		 * @type {Object3D}
		 */
		this.object = object;
		this.type = 'BoxHelper';

		this.matrixAutoUpdate = false;

		this.update();

	}

	/**
	 * Updates the helper's geometry to match the dimensions of the object,
	 * including any children.
	 */
	update() {

		if ( this.object !== undefined ) {

			_box.setFromObject( this.object );

		}

		if ( _box.isEmpty() ) return;

		const min = _box.min;
		const max = _box.max;

		/*
			5____4
		1/___0/|
		| 6__|_7
		2/___3/

		0: max.x, max.y, max.z
		1: min.x, max.y, max.z
		2: min.x, min.y, max.z
		3: max.x, min.y, max.z
		4: max.x, max.y, min.z
		5: min.x, max.y, min.z
		6: min.x, min.y, min.z
		7: max.x, min.y, min.z
		*/

		const position = this.geometry.attributes.position;
		const array = position.array;

		array[ 0 ] = max.x; array[ 1 ] = max.y; array[ 2 ] = max.z;
		array[ 3 ] = min.x; array[ 4 ] = max.y; array[ 5 ] = max.z;
		array[ 6 ] = min.x; array[ 7 ] = min.y; array[ 8 ] = max.z;
		array[ 9 ] = max.x; array[ 10 ] = min.y; array[ 11 ] = max.z;
		array[ 12 ] = max.x; array[ 13 ] = max.y; array[ 14 ] = min.z;
		array[ 15 ] = min.x; array[ 16 ] = max.y; array[ 17 ] = min.z;
		array[ 18 ] = min.x; array[ 19 ] = min.y; array[ 20 ] = min.z;
		array[ 21 ] = max.x; array[ 22 ] = min.y; array[ 23 ] = min.z;

		position.needsUpdate = true;

		this.geometry.computeBoundingSphere();

	}

	/**
	 * Updates the wireframe box for the passed object.
	 *
	 * @param {Object3D} object - The 3D object to create the helper for.
	 * @return {BoxHelper} A reference to this instance.
	 */
	setFromObject( object ) {

		this.object = object;
		this.update();

		return this;

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.object = source.object;

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

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		if ( this.object !== undefined ) {

			_box.setFromObject( this.object );

		}

		if ( _box.isEmpty() ) return;

		const min = _box.min;
		const max = _box.max;

		/*
			5____4
		1/___0/|
		| 6__|_7
		2/___3/

		0: max.x, max.y, max.z
		1: min.x, max.y, max.z
		2: min.x, min.y, max.z
		3: max.x, min.y, max.z
		4: max.x, max.y, min.z
		5: min.x, max.y, min.z
		6: min.x, min.y, min.z
		7: max.x, min.y, min.z
		*/

		const position = this.geometry.attributes.position;
		const array = position.array;

		array[ 0 ] = max.x; array[ 1 ] = max.y; array[ 2 ] = max.z;
		array[ 3 ] = min.x; array[ 4 ] = max.y; array[ 5 ] = max.z;
		array[ 6 ] = min.x; array[ 7 ] = min.y; array[ 8 ] = max.z;
		array[ 9 ] = max.x; array[ 10 ] = min.y; array[ 11 ] = max.z;
		array[ 12 ] = max.x; array[ 13 ] = max.y; array[ 14 ] = min.z;
		array[ 15 ] = min.x; array[ 16 ] = max.y; array[ 17 ] = min.z;
		array[ 18 ] = min.x; array[ 19 ] = min.y; array[ 20 ] = min.z;
		array[ 21 ] = max.x; array[ 22 ] = min.y; array[ 23 ] = min.z;

		position.needsUpdate = true;

		this.geometry.computeBoundingSphere();

	}
```
</details>

##### `setFromObject(object: Object3D): BoxHelper`

<details><summary>Code</summary>

```ts
setFromObject( object ) {

		this.object = object;
		this.update();

		return this;

	}
```
</details>

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		this.object = source.object;

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