[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Spherical.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Spherical.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `clamp` | `./MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `EPS` | `0.000001` | let/var | `0.000001` | ✗ |


---

## Functions

### `Spherical.set(radius: number, phi: number, theta: number): Spherical`

**JSDoc:**
```typescript
/**
	 * Sets the spherical components by copying the given values.
	 *
	 * @param {number} radius - The radius.
	 * @param {number} phi - The polar angle.
	 * @param {number} theta - The azimuthal angle.
	 * @return {Spherical} A reference to this spherical.
	 */
```

**Parameters:**

- **`radius`** `number`
- **`phi`** `number`
- **`theta`** `number`

**Returns:** `Spherical`

<details><summary>Code</summary>

```typescript
set( radius, phi, theta ) {

		this.radius = radius;
		this.phi = phi;
		this.theta = theta;

		return this;

	}
```
</details>

### `Spherical.copy(other: Spherical): Spherical`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given spherical to this instance.
	 *
	 * @param {Spherical} other - The spherical to copy.
	 * @return {Spherical} A reference to this spherical.
	 */
```

**Parameters:**

- **`other`** `Spherical`

**Returns:** `Spherical`

<details><summary>Code</summary>

```typescript
copy( other ) {

		this.radius = other.radius;
		this.phi = other.phi;
		this.theta = other.theta;

		return this;

	}
```
</details>

### `Spherical.makeSafe(): Spherical`

**JSDoc:**
```typescript
/**
	 * Restricts the polar angle [page:.phi phi] to be between `0.000001` and pi -
	 * `0.000001`.
	 *
	 * @return {Spherical} A reference to this spherical.
	 */
```

**Returns:** `Spherical`

**Calls:**

- `clamp (from ./MathUtils.js)`

<details><summary>Code</summary>

```typescript
makeSafe() {

		const EPS = 0.000001;
		this.phi = clamp( this.phi, EPS, Math.PI - EPS );

		return this;

	}
```
</details>

### `Spherical.setFromVector3(v: Vector3): Spherical`

**JSDoc:**
```typescript
/**
	 * Sets the spherical components from the given vector which is assumed to hold
	 * Cartesian coordinates.
	 *
	 * @param {Vector3} v - The vector to set.
	 * @return {Spherical} A reference to this spherical.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Spherical`

**Calls:**

- `this.setFromCartesianCoords`

<details><summary>Code</summary>

```typescript
setFromVector3( v ) {

		return this.setFromCartesianCoords( v.x, v.y, v.z );

	}
```
</details>

### `Spherical.setFromCartesianCoords(x: number, y: number, z: number): Spherical`

**JSDoc:**
```typescript
/**
	 * Sets the spherical components from the given Cartesian coordinates.
	 *
	 * @param {number} x - The x value.
	 * @param {number} y - The y value.
	 * @param {number} z - The z value.
	 * @return {Spherical} A reference to this spherical.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`z`** `number`

**Returns:** `Spherical`

**Calls:**

- `Math.sqrt`
- `Math.atan2`
- `Math.acos`
- `clamp (from ./MathUtils.js)`

<details><summary>Code</summary>

```typescript
setFromCartesianCoords( x, y, z ) {

		this.radius = Math.sqrt( x * x + y * y + z * z );

		if ( this.radius === 0 ) {

			this.theta = 0;
			this.phi = 0;

		} else {

			this.theta = Math.atan2( x, z );
			this.phi = Math.acos( clamp( y / this.radius, - 1, 1 ) );

		}

		return this;

	}
```
</details>

### `Spherical.clone(): Spherical`

**JSDoc:**
```typescript
/**
	 * Returns a new spherical with copied values from this instance.
	 *
	 * @return {Spherical} A clone of this instance.
	 */
```

**Returns:** `Spherical`

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

### `Spherical`

<details><summary>Class Code</summary>

```ts
class Spherical {

	/**
	 * Constructs a new spherical.
	 *
	 * @param {number} [radius=1] - The radius, or the Euclidean distance (straight-line distance) from the point to the origin.
	 * @param {number} [phi=0] - The polar angle in radians from the y (up) axis.
	 * @param {number} [theta=0] - The equator/azimuthal angle in radians around the y (up) axis.
	 */
	constructor( radius = 1, phi = 0, theta = 0 ) {

		/**
		 * The radius, or the Euclidean distance (straight-line distance) from the point to the origin.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.radius = radius;

		/**
		 * The polar angle in radians from the y (up) axis.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.phi = phi;

		/**
		 * The equator/azimuthal angle in radians around the y (up) axis.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.theta = theta;

	}

	/**
	 * Sets the spherical components by copying the given values.
	 *
	 * @param {number} radius - The radius.
	 * @param {number} phi - The polar angle.
	 * @param {number} theta - The azimuthal angle.
	 * @return {Spherical} A reference to this spherical.
	 */
	set( radius, phi, theta ) {

		this.radius = radius;
		this.phi = phi;
		this.theta = theta;

		return this;

	}

	/**
	 * Copies the values of the given spherical to this instance.
	 *
	 * @param {Spherical} other - The spherical to copy.
	 * @return {Spherical} A reference to this spherical.
	 */
	copy( other ) {

		this.radius = other.radius;
		this.phi = other.phi;
		this.theta = other.theta;

		return this;

	}

	/**
	 * Restricts the polar angle [page:.phi phi] to be between `0.000001` and pi -
	 * `0.000001`.
	 *
	 * @return {Spherical} A reference to this spherical.
	 */
	makeSafe() {

		const EPS = 0.000001;
		this.phi = clamp( this.phi, EPS, Math.PI - EPS );

		return this;

	}

	/**
	 * Sets the spherical components from the given vector which is assumed to hold
	 * Cartesian coordinates.
	 *
	 * @param {Vector3} v - The vector to set.
	 * @return {Spherical} A reference to this spherical.
	 */
	setFromVector3( v ) {

		return this.setFromCartesianCoords( v.x, v.y, v.z );

	}

	/**
	 * Sets the spherical components from the given Cartesian coordinates.
	 *
	 * @param {number} x - The x value.
	 * @param {number} y - The y value.
	 * @param {number} z - The z value.
	 * @return {Spherical} A reference to this spherical.
	 */
	setFromCartesianCoords( x, y, z ) {

		this.radius = Math.sqrt( x * x + y * y + z * z );

		if ( this.radius === 0 ) {

			this.theta = 0;
			this.phi = 0;

		} else {

			this.theta = Math.atan2( x, z );
			this.phi = Math.acos( clamp( y / this.radius, - 1, 1 ) );

		}

		return this;

	}

	/**
	 * Returns a new spherical with copied values from this instance.
	 *
	 * @return {Spherical} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

}
```
</details>

#### Methods

##### `set(radius: number, phi: number, theta: number): Spherical`

<details><summary>Code</summary>

```ts
set( radius, phi, theta ) {

		this.radius = radius;
		this.phi = phi;
		this.theta = theta;

		return this;

	}
```
</details>

##### `copy(other: Spherical): Spherical`

<details><summary>Code</summary>

```ts
copy( other ) {

		this.radius = other.radius;
		this.phi = other.phi;
		this.theta = other.theta;

		return this;

	}
```
</details>

##### `makeSafe(): Spherical`

<details><summary>Code</summary>

```ts
makeSafe() {

		const EPS = 0.000001;
		this.phi = clamp( this.phi, EPS, Math.PI - EPS );

		return this;

	}
```
</details>

##### `setFromVector3(v: Vector3): Spherical`

<details><summary>Code</summary>

```ts
setFromVector3( v ) {

		return this.setFromCartesianCoords( v.x, v.y, v.z );

	}
```
</details>

##### `setFromCartesianCoords(x: number, y: number, z: number): Spherical`

<details><summary>Code</summary>

```ts
setFromCartesianCoords( x, y, z ) {

		this.radius = Math.sqrt( x * x + y * y + z * z );

		if ( this.radius === 0 ) {

			this.theta = 0;
			this.phi = 0;

		} else {

			this.theta = Math.atan2( x, z );
			this.phi = Math.acos( clamp( y / this.radius, - 1, 1 ) );

		}

		return this;

	}
```
</details>

##### `clone(): Spherical`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---