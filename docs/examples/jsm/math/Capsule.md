[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Capsule.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/math/Capsule.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `three` |


---

## Functions

### `Capsule.clone(): Capsule`

**JSDoc:**
```typescript
/**
	 * Returns a new capsule with copied values from this instance.
	 *
	 * @return {Capsule} A clone of this instance.
	 */
```

**Returns:** `Capsule`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

### `Capsule.set(start: Vector3, end: Vector3, radius: number): Capsule`

**JSDoc:**
```typescript
/**
	 * Sets the capsule components to the given values.
	 * Please note that this method only copies the values from the given objects.
	 *
	 * @param {Vector3} start - The start vector.
	 * @param {Vector3} end - The end vector
	 * @param {number} radius - The capsule's radius.
	 * @return {Capsule} A reference to this capsule.
	 */
```

**Parameters:**

- **`start`** `Vector3`
- **`end`** `Vector3`
- **`radius`** `number`

**Returns:** `Capsule`

**Calls:**

- `this.start.copy`
- `this.end.copy`

<details><summary>Code</summary>

```typescript
set( start, end, radius ) {

		this.start.copy( start );
		this.end.copy( end );
		this.radius = radius;

		return this;

	}
```
</details>

### `Capsule.copy(capsule: Capsule): Capsule`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given capsule to this instance.
	 *
	 * @param {Capsule} capsule - The capsule to copy.
	 * @return {Capsule} A reference to this capsule.
	 */
```

**Parameters:**

- **`capsule`** `Capsule`

**Returns:** `Capsule`

**Calls:**

- `this.start.copy`
- `this.end.copy`

<details><summary>Code</summary>

```typescript
copy( capsule ) {

		this.start.copy( capsule.start );
		this.end.copy( capsule.end );
		this.radius = capsule.radius;

		return this;

	}
```
</details>

### `Capsule.getCenter(target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns the center point of this capsule.
	 *
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The center point.
	 */
```

**Parameters:**

- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `target.copy( this.end ).add( this.start ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getCenter( target ) {

		return target.copy( this.end ).add( this.start ).multiplyScalar( 0.5 );

	}
```
</details>

### `Capsule.translate(v: Vector3): Capsule`

**JSDoc:**
```typescript
/**
	 * Adds the given offset to this capsule, effectively moving it in 3D space.
	 *
	 * @param {Vector3} v - The offset that should be used to translate the capsule.
	 * @return {Capsule} A reference to this capsule.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Capsule`

**Calls:**

- `this.start.add`
- `this.end.add`

<details><summary>Code</summary>

```typescript
translate( v ) {

		this.start.add( v );
		this.end.add( v );

		return this;

	}
```
</details>

### `Capsule.intersectsBox(box: Box3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given bounding box intersects with this capsule.
	 *
	 * @param {Box3} box - The bounding box to test.
	 * @return {boolean} Whether the given bounding box intersects with this capsule.
	 */
```

**Parameters:**

- **`box`** `Box3`

**Returns:** `boolean`

**Calls:**

- `checkAABBAxis`

<details><summary>Code</summary>

```typescript
intersectsBox( box ) {

		return (
			checkAABBAxis(
				this.start.x, this.start.y, this.end.x, this.end.y,
				box.min.x, box.max.x, box.min.y, box.max.y,
				this.radius ) &&
			checkAABBAxis(
				this.start.x, this.start.z, this.end.x, this.end.z,
				box.min.x, box.max.x, box.min.z, box.max.z,
				this.radius ) &&
			checkAABBAxis(
				this.start.y, this.start.z, this.end.y, this.end.z,
				box.min.y, box.max.y, box.min.z, box.max.z,
				this.radius )
		);

	}
```
</details>

### `checkAABBAxis(p1x: any, p1y: any, p2x: any, p2y: any, minx: any, maxx: any, miny: any, maxy: any, radius: any): boolean`

**Parameters:**

- **`p1x`** `any`
- **`p1y`** `any`
- **`p2x`** `any`
- **`p2y`** `any`
- **`minx`** `any`
- **`maxx`** `any`
- **`miny`** `any`
- **`maxy`** `any`
- **`radius`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function checkAABBAxis( p1x, p1y, p2x, p2y, minx, maxx, miny, maxy, radius ) {

	return (
		( minx - p1x < radius || minx - p2x < radius ) &&
		( p1x - maxx < radius || p2x - maxx < radius ) &&
		( miny - p1y < radius || miny - p2y < radius ) &&
		( p1y - maxy < radius || p2y - maxy < radius )
	);

}
```
</details>


---

## Classes

### `Capsule`

<details><summary>Class Code</summary>

```ts
class Capsule {

	/**
	 * Constructs a new capsule.
	 *
	 * @param {Vector3} [start] - The start vector.
	 * @param {Vector3} [end] - The end vector.
	 * @param {number} [radius=1] - The capsule's radius.
	 */
	constructor( start = new Vector3( 0, 0, 0 ), end = new Vector3( 0, 1, 0 ), radius = 1 ) {

		/**
		 * The start vector.
		 *
		 * @type {Vector3}
		 */
		this.start = start;

		/**
		 * The end vector.
		 *
		 * @type {Vector3}
		 */
		this.end = end;

		/**
		 * The capsule's radius.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.radius = radius;

	}

	/**
	 * Returns a new capsule with copied values from this instance.
	 *
	 * @return {Capsule} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

	/**
	 * Sets the capsule components to the given values.
	 * Please note that this method only copies the values from the given objects.
	 *
	 * @param {Vector3} start - The start vector.
	 * @param {Vector3} end - The end vector
	 * @param {number} radius - The capsule's radius.
	 * @return {Capsule} A reference to this capsule.
	 */
	set( start, end, radius ) {

		this.start.copy( start );
		this.end.copy( end );
		this.radius = radius;

		return this;

	}

	/**
	 * Copies the values of the given capsule to this instance.
	 *
	 * @param {Capsule} capsule - The capsule to copy.
	 * @return {Capsule} A reference to this capsule.
	 */
	copy( capsule ) {

		this.start.copy( capsule.start );
		this.end.copy( capsule.end );
		this.radius = capsule.radius;

		return this;

	}

	/**
	 * Returns the center point of this capsule.
	 *
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The center point.
	 */
	getCenter( target ) {

		return target.copy( this.end ).add( this.start ).multiplyScalar( 0.5 );

	}

	/**
	 * Adds the given offset to this capsule, effectively moving it in 3D space.
	 *
	 * @param {Vector3} v - The offset that should be used to translate the capsule.
	 * @return {Capsule} A reference to this capsule.
	 */
	translate( v ) {

		this.start.add( v );
		this.end.add( v );

		return this;

	}

	/**
	 * Returns `true` if the given bounding box intersects with this capsule.
	 *
	 * @param {Box3} box - The bounding box to test.
	 * @return {boolean} Whether the given bounding box intersects with this capsule.
	 */
	intersectsBox( box ) {

		return (
			checkAABBAxis(
				this.start.x, this.start.y, this.end.x, this.end.y,
				box.min.x, box.max.x, box.min.y, box.max.y,
				this.radius ) &&
			checkAABBAxis(
				this.start.x, this.start.z, this.end.x, this.end.z,
				box.min.x, box.max.x, box.min.z, box.max.z,
				this.radius ) &&
			checkAABBAxis(
				this.start.y, this.start.z, this.end.y, this.end.z,
				box.min.y, box.max.y, box.min.z, box.max.z,
				this.radius )
		);

	}

}
```
</details>

#### Methods

##### `clone(): Capsule`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

##### `set(start: Vector3, end: Vector3, radius: number): Capsule`

<details><summary>Code</summary>

```ts
set( start, end, radius ) {

		this.start.copy( start );
		this.end.copy( end );
		this.radius = radius;

		return this;

	}
```
</details>

##### `copy(capsule: Capsule): Capsule`

<details><summary>Code</summary>

```ts
copy( capsule ) {

		this.start.copy( capsule.start );
		this.end.copy( capsule.end );
		this.radius = capsule.radius;

		return this;

	}
```
</details>

##### `getCenter(target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getCenter( target ) {

		return target.copy( this.end ).add( this.start ).multiplyScalar( 0.5 );

	}
```
</details>

##### `translate(v: Vector3): Capsule`

<details><summary>Code</summary>

```ts
translate( v ) {

		this.start.add( v );
		this.end.add( v );

		return this;

	}
```
</details>

##### `intersectsBox(box: Box3): boolean`

<details><summary>Code</summary>

```ts
intersectsBox( box ) {

		return (
			checkAABBAxis(
				this.start.x, this.start.y, this.end.x, this.end.y,
				box.min.x, box.max.x, box.min.y, box.max.y,
				this.radius ) &&
			checkAABBAxis(
				this.start.x, this.start.z, this.end.x, this.end.z,
				box.min.x, box.max.x, box.min.z, box.max.z,
				this.radius ) &&
			checkAABBAxis(
				this.start.y, this.start.z, this.end.y, this.end.z,
				box.min.y, box.max.y, box.min.z, box.max.z,
				this.radius )
		);

	}
```
</details>


---