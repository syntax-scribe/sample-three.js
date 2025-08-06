[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LineCurve.js`

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
📂 **`src/extras/curves/LineCurve.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `../../math/Vector2.js` |
| `Curve` | `../core/Curve.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `point` | `Vector2` | let/var | `optionalTarget` | ✗ |


---

## Functions

### `LineCurve.getPoint(t: number, optionalTarget: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Returns a point on the line.
	 *
	 * @param {number} t - A interpolation factor representing a position on the line. Must be in the range `[0,1]`.
	 * @param {Vector2} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector2} The position on the line.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `point.copy`
- `point.copy( this.v2 ).sub`
- `point.multiplyScalar( t ).add`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector2() ) {

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

### `LineCurve.getPointAt(u: any, optionalTarget: any): Vector2`

**Parameters:**

- **`u`** `any`
- **`optionalTarget`** `any`

**Returns:** `Vector2`

**Calls:**

- `this.getPoint`

<details><summary>Code</summary>

```typescript
getPointAt( u, optionalTarget ) {

		return this.getPoint( u, optionalTarget );

	}
```
</details>

### `LineCurve.getTangent(t: any, optionalTarget: Vector2): Vector2`

**Parameters:**

- **`t`** `any`
- **`optionalTarget`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `optionalTarget.subVectors( this.v2, this.v1 ).normalize`

<details><summary>Code</summary>

```typescript
getTangent( t, optionalTarget = new Vector2() ) {

		return optionalTarget.subVectors( this.v2, this.v1 ).normalize();

	}
```
</details>

### `LineCurve.getTangentAt(u: any, optionalTarget: any): Vector2`

**Parameters:**

- **`u`** `any`
- **`optionalTarget`** `any`

**Returns:** `Vector2`

**Calls:**

- `this.getTangent`

<details><summary>Code</summary>

```typescript
getTangentAt( u, optionalTarget ) {

		return this.getTangent( u, optionalTarget );

	}
```
</details>

### `LineCurve.copy(source: any): this`

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

### `LineCurve.toJSON(): any`

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

### `LineCurve.fromJSON(json: any): this`

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

### `LineCurve`

<details><summary>Class Code</summary>

```ts
class LineCurve extends Curve {

	/**
	 * Constructs a new line curve.
	 *
	 * @param {Vector2} [v1] - The start point.
	 * @param {Vector2} [v2] - The end point.
	 */
	constructor( v1 = new Vector2(), v2 = new Vector2() ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLineCurve = true;

		this.type = 'LineCurve';

		/**
		 * The start point.
		 *
		 * @type {Vector2}
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
	 * @param {Vector2} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector2} The position on the line.
	 */
	getPoint( t, optionalTarget = new Vector2() ) {

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

	getTangent( t, optionalTarget = new Vector2() ) {

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

##### `getPoint(t: number, optionalTarget: Vector2): Vector2`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector2() ) {

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

##### `getPointAt(u: any, optionalTarget: any): Vector2`

<details><summary>Code</summary>

```ts
getPointAt( u, optionalTarget ) {

		return this.getPoint( u, optionalTarget );

	}
```
</details>

##### `getTangent(t: any, optionalTarget: Vector2): Vector2`

<details><summary>Code</summary>

```ts
getTangent( t, optionalTarget = new Vector2() ) {

		return optionalTarget.subVectors( this.v2, this.v1 ).normalize();

	}
```
</details>

##### `getTangentAt(u: any, optionalTarget: any): Vector2`

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