[⬅️ Back to Table of Contents](../../index.md)

# 📄 `CircleGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/CircleGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `Vector3` | `../math/Vector3.js` |
| `Vector2` | `../math/Vector2.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `uv` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `segment` | `number` | let/var | `thetaStart + s / segments * thetaLength` | ✗ |


---

## Functions

### `CircleGeometry.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `Object.assign`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>

### `CircleGeometry.fromJSON(data: any): CircleGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {CircleGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `CircleGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new CircleGeometry( data.radius, data.segments, data.thetaStart, data.thetaLength );

	}
```
</details>


---

## Classes

### `CircleGeometry`

<details><summary>Class Code</summary>

```ts
class CircleGeometry extends BufferGeometry {

	/**
	 * Constructs a new circle geometry.
	 *
	 * @param {number} [radius=1] - Radius of the circle.
	 * @param {number} [segments=32] - Number of segments (triangles), minimum = `3`.
	 * @param {number} [thetaStart=0] - Start angle for first segment in radians.
	 * @param {number} [thetaLength=Math.PI*2] - The central angle, often called theta,
	 * of the circular sector in radians. The default value results in a complete circle.
	 */
	constructor( radius = 1, segments = 32, thetaStart = 0, thetaLength = Math.PI * 2 ) {

		super();

		this.type = 'CircleGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			radius: radius,
			segments: segments,
			thetaStart: thetaStart,
			thetaLength: thetaLength
		};

		segments = Math.max( 3, segments );

		// buffers

		const indices = [];
		const vertices = [];
		const normals = [];
		const uvs = [];

		// helper variables

		const vertex = new Vector3();
		const uv = new Vector2();

		// center point

		vertices.push( 0, 0, 0 );
		normals.push( 0, 0, 1 );
		uvs.push( 0.5, 0.5 );

		for ( let s = 0, i = 3; s <= segments; s ++, i += 3 ) {

			const segment = thetaStart + s / segments * thetaLength;

			// vertex

			vertex.x = radius * Math.cos( segment );
			vertex.y = radius * Math.sin( segment );

			vertices.push( vertex.x, vertex.y, vertex.z );

			// normal

			normals.push( 0, 0, 1 );

			// uvs

			uv.x = ( vertices[ i ] / radius + 1 ) / 2;
			uv.y = ( vertices[ i + 1 ] / radius + 1 ) / 2;

			uvs.push( uv.x, uv.y );

		}

		// indices

		for ( let i = 1; i <= segments; i ++ ) {

			indices.push( i, i + 1, 0 );

		}

		// build geometry

		this.setIndex( indices );
		this.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		this.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

	}

	copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}

	/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {CircleGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new CircleGeometry( data.radius, data.segments, data.thetaStart, data.thetaLength );

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>

##### `fromJSON(data: any): CircleGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new CircleGeometry( data.radius, data.segments, data.thetaStart, data.thetaLength );

	}
```
</details>


---