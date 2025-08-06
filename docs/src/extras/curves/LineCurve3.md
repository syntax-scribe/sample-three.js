[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LineCurve3.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/curves/LineCurve3.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../../math/Vector3.js` |
| `Curve` | `../core/Curve.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |


---

## Functions

### `LineCurve3.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a point on the line.
	 *
	 * @param {number} t - A interpolation factor representing a position on the line. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the line.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `point.copy`
- `point.copy( this.v2 ).sub`
- `point.multiplyScalar( t ).add`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		if ( t === 1 ) {

			point.copy( this.v2 );

		} else {

			point.copy( this.v2 ).sub( this.v1 );
			point.multiplyScalar( t ).add( this.v1 );

		}

		return point;

	}
```
</details>

### `LineCurve3.getPointAt(u: any, optionalTarget: any): Vector3`

**Parameters:**

- **`u`** `any`
- **`optionalTarget`** `any`

**Returns:** `Vector3`

**Calls:**

- `this.getPoint`

<details><summary>Code</summary>

```typescript
getPointAt( u, optionalTarget ) {

		return this.getPoint( u, optionalTarget );

	}
```
</details>

### `LineCurve3.getTangent(t: any, optionalTarget: Vector3): Vector3`

**Parameters:**

- **`t`** `any`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `optionalTarget.subVectors( this.v2, this.v1 ).normalize`

<details><summary>Code</summary>

```typescript
getTangent( t, optionalTarget = new Vector3() ) {

		return optionalTarget.subVectors( this.v2, this.v1 ).normalize();

	}
```
</details>

### `LineCurve3.getTangentAt(u: any, optionalTarget: any): Vector3`

**Parameters:**

- **`u`** `any`
- **`optionalTarget`** `any`

**Returns:** `Vector3`

**Calls:**

- `this.getTangent`

<details><summary>Code</summary>

```typescript
getTangentAt( u, optionalTarget ) {

		return this.getTangent( u, optionalTarget );

	}
```
</details>

### `LineCurve3.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.v1.copy`
- `this.v2.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.v1.copy( source.v1 );
		this.v2.copy( source.v2 );

		return this;

	}
```
</details>

### `LineCurve3.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `this.v1.toArray`
- `this.v2.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.v1 = this.v1.toArray();
		data.v2 = this.v2.toArray();

		return data;

	}
```
</details>

### `LineCurve3.fromJSON(json: any): this`

**Parameters:**

- **`json`** `any`

**Returns:** `this`

**Calls:**

- `super.fromJSON`
- `this.v1.fromArray`
- `this.v2.fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.v1.fromArray( json.v1 );
		this.v2.fromArray( json.v2 );

		return this;

	}
```
</details>


---

## Classes

### `LineCurve3`

<details><summary>Class Code</summary>

```ts
class LineCurve3 extends Curve {

	/**
	 * Constructs a new line curve.
	 *
	 * @param {Vector3} [v1] - The start point.
	 * @param {Vector3} [v2] - The end point.
	 */
	constructor( v1 = new Vector3(), v2 = new Vector3() ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLineCurve3 = true;

		this.type = 'LineCurve3';

		/**
		 * The start point.
		 *
		 * @type {Vector3}
		 */
		this.v1 = v1;

		/**
		 * The end point.
		 *
		 * @type {Vector2}
		 */
		this.v2 = v2;

	}

	/**
	 * Returns a point on the line.
	 *
	 * @param {number} t - A interpolation factor representing a position on the line. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the line.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		if ( t === 1 ) {

			point.copy( this.v2 );

		} else {

			point.copy( this.v2 ).sub( this.v1 );
			point.multiplyScalar( t ).add( this.v1 );

		}

		return point;

	}

	// Line curve is linear, so we can overwrite default getPointAt
	getPointAt( u, optionalTarget ) {

		return this.getPoint( u, optionalTarget );

	}

	getTangent( t, optionalTarget = new Vector3() ) {

		return optionalTarget.subVectors( this.v2, this.v1 ).normalize();

	}

	getTangentAt( u, optionalTarget ) {

		return this.getTangent( u, optionalTarget );

	}

	copy( source ) {

		super.copy( source );

		this.v1.copy( source.v1 );
		this.v2.copy( source.v2 );

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		data.v1 = this.v1.toArray();
		data.v2 = this.v2.toArray();

		return data;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.v1.fromArray( json.v1 );
		this.v2.fromArray( json.v2 );

		return this;

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		if ( t === 1 ) {

			point.copy( this.v2 );

		} else {

			point.copy( this.v2 ).sub( this.v1 );
			point.multiplyScalar( t ).add( this.v1 );

		}

		return point;

	}
```
</details>

##### `getPointAt(u: any, optionalTarget: any): Vector3`

<details><summary>Code</summary>

```ts
getPointAt( u, optionalTarget ) {

		return this.getPoint( u, optionalTarget );

	}
```
</details>

##### `getTangent(t: any, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getTangent( t, optionalTarget = new Vector3() ) {

		return optionalTarget.subVectors( this.v2, this.v1 ).normalize();

	}
```
</details>

##### `getTangentAt(u: any, optionalTarget: any): Vector3`

<details><summary>Code</summary>

```ts
getTangentAt( u, optionalTarget ) {

		return this.getTangent( u, optionalTarget );

	}
```
</details>

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.v1.copy( source.v1 );
		this.v2.copy( source.v2 );

		return this;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		data.v1 = this.v1.toArray();
		data.v2 = this.v2.toArray();

		return data;

	}
```
</details>

##### `fromJSON(json: any): this`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.v1.fromArray( json.v1 );
		this.v2.fromArray( json.v2 );

		return this;

	}
```
</details>


---