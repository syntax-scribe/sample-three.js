[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Cylindrical.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Cylindrical.js`**

## Functions

### `Cylindrical.set(radius: number, theta: number, y: number): Cylindrical`

**JSDoc:**
```typescript
/**
	 * Sets the cylindrical components by copying the given values.
	 *
	 * @param {number} radius - The radius.
	 * @param {number} theta - The theta angle.
	 * @param {number} y - The height value.
	 * @return {Cylindrical} A reference to this cylindrical.
	 */
```

**Parameters:**

- **`radius`** `number`
- **`theta`** `number`
- **`y`** `number`

**Returns:** `Cylindrical`

<details><summary>Code</summary>

```typescript
set( radius, theta, y ) {

		this.radius = radius;
		this.theta = theta;
		this.y = y;

		return this;

	}
```
</details>

### `Cylindrical.copy(other: Cylindrical): Cylindrical`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given cylindrical to this instance.
	 *
	 * @param {Cylindrical} other - The cylindrical to copy.
	 * @return {Cylindrical} A reference to this cylindrical.
	 */
```

**Parameters:**

- **`other`** `Cylindrical`

**Returns:** `Cylindrical`

<details><summary>Code</summary>

```typescript
copy( other ) {

		this.radius = other.radius;
		this.theta = other.theta;
		this.y = other.y;

		return this;

	}
```
</details>

### `Cylindrical.setFromVector3(v: Vector3): Cylindrical`

**JSDoc:**
```typescript
/**
	 * Sets the cylindrical components from the given vector which is assumed to hold
	 * Cartesian coordinates.
	 *
	 * @param {Vector3} v - The vector to set.
	 * @return {Cylindrical} A reference to this cylindrical.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Cylindrical`

**Calls:**

- `this.setFromCartesianCoords`

<details><summary>Code</summary>

```typescript
setFromVector3( v ) {

		return this.setFromCartesianCoords( v.x, v.y, v.z );

	}
```
</details>

### `Cylindrical.setFromCartesianCoords(x: number, y: number, z: number): Cylindrical`

**JSDoc:**
```typescript
/**
	 * Sets the cylindrical components from the given Cartesian coordinates.
	 *
	 * @param {number} x - The x value.
	 * @param {number} y - The x value.
	 * @param {number} z - The x value.
	 * @return {Cylindrical} A reference to this cylindrical.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`z`** `number`

**Returns:** `Cylindrical`

**Calls:**

- `Math.sqrt`
- `Math.atan2`

<details><summary>Code</summary>

```typescript
setFromCartesianCoords( x, y, z ) {

		this.radius = Math.sqrt( x * x + z * z );
		this.theta = Math.atan2( x, z );
		this.y = y;

		return this;

	}
```
</details>

### `Cylindrical.clone(): Cylindrical`

**JSDoc:**
```typescript
/**
	 * Returns a new cylindrical with copied values from this instance.
	 *
	 * @return {Cylindrical} A clone of this instance.
	 */
```

**Returns:** `Cylindrical`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---

## Classes

### `Cylindrical`

<details><summary>Class Code</summary>

```ts
class Cylindrical {

	/**
	 * Constructs a new cylindrical.
	 *
	 * @param {number} [radius=1] - The distance from the origin to a point in the x-z plane.
	 * @param {number} [theta=0] - A counterclockwise angle in the x-z plane measured in radians from the positive z-axis.
	 * @param {number} [y=0] - The height above the x-z plane.
	 */
	constructor( radius = 1, theta = 0, y = 0 ) {

		/**
		 * The distance from the origin to a point in the x-z plane.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.radius = radius;

		/**
		 * A counterclockwise angle in the x-z plane measured in radians from the positive z-axis.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.theta = theta;

		/**
		 * The height above the x-z plane.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.y = y;

	}

	/**
	 * Sets the cylindrical components by copying the given values.
	 *
	 * @param {number} radius - The radius.
	 * @param {number} theta - The theta angle.
	 * @param {number} y - The height value.
	 * @return {Cylindrical} A reference to this cylindrical.
	 */
	set( radius, theta, y ) {

		this.radius = radius;
		this.theta = theta;
		this.y = y;

		return this;

	}

	/**
	 * Copies the values of the given cylindrical to this instance.
	 *
	 * @param {Cylindrical} other - The cylindrical to copy.
	 * @return {Cylindrical} A reference to this cylindrical.
	 */
	copy( other ) {

		this.radius = other.radius;
		this.theta = other.theta;
		this.y = other.y;

		return this;

	}

	/**
	 * Sets the cylindrical components from the given vector which is assumed to hold
	 * Cartesian coordinates.
	 *
	 * @param {Vector3} v - The vector to set.
	 * @return {Cylindrical} A reference to this cylindrical.
	 */
	setFromVector3( v ) {

		return this.setFromCartesianCoords( v.x, v.y, v.z );

	}

	/**
	 * Sets the cylindrical components from the given Cartesian coordinates.
	 *
	 * @param {number} x - The x value.
	 * @param {number} y - The x value.
	 * @param {number} z - The x value.
	 * @return {Cylindrical} A reference to this cylindrical.
	 */
	setFromCartesianCoords( x, y, z ) {

		this.radius = Math.sqrt( x * x + z * z );
		this.theta = Math.atan2( x, z );
		this.y = y;

		return this;

	}

	/**
	 * Returns a new cylindrical with copied values from this instance.
	 *
	 * @return {Cylindrical} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

}
```
</details>

#### Methods

##### `set(radius: number, theta: number, y: number): Cylindrical`

<details><summary>Code</summary>

```ts
set( radius, theta, y ) {

		this.radius = radius;
		this.theta = theta;
		this.y = y;

		return this;

	}
```
</details>

##### `copy(other: Cylindrical): Cylindrical`

<details><summary>Code</summary>

```ts
copy( other ) {

		this.radius = other.radius;
		this.theta = other.theta;
		this.y = other.y;

		return this;

	}
```
</details>

##### `setFromVector3(v: Vector3): Cylindrical`

<details><summary>Code</summary>

```ts
setFromVector3( v ) {

		return this.setFromCartesianCoords( v.x, v.y, v.z );

	}
```
</details>

##### `setFromCartesianCoords(x: number, y: number, z: number): Cylindrical`

<details><summary>Code</summary>

```ts
setFromCartesianCoords( x, y, z ) {

		this.radius = Math.sqrt( x * x + z * z );
		this.theta = Math.atan2( x, z );
		this.y = y;

		return this;

	}
```
</details>

##### `clone(): Cylindrical`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---