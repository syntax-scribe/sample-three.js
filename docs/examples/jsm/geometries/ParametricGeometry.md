[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ParametricGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 17 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/geometries/ParametricGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Float32BufferAttribute` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `EPS` | `0.00001` | let/var | `0.00001` | ✗ |
| `normal` | `any` | let/var | `new Vector3()` | ✗ |
| `p0` | `any` | let/var | `new Vector3()` | ✗ |
| `p1` | `any` | let/var | `new Vector3()` | ✗ |
| `pu` | `any` | let/var | `new Vector3()` | ✗ |
| `pv` | `any` | let/var | `new Vector3()` | ✗ |
| `sliceCount` | `number` | let/var | `slices + 1` | ✗ |
| `v` | `number` | let/var | `i / stacks` | ✗ |
| `u` | `number` | let/var | `j / slices` | ✗ |
| `a` | `number` | let/var | `i * sliceCount + j` | ✗ |
| `b` | `number` | let/var | `i * sliceCount + j + 1` | ✗ |
| `c` | `number` | let/var | `( i + 1 ) * sliceCount + j + 1` | ✗ |
| `d` | `number` | let/var | `( i + 1 ) * sliceCount + j` | ✗ |


---

## Functions

### `ParametricGeometry.copy(source: any): this`

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


---

## Classes

### `ParametricGeometry`

<details><summary>Class Code</summary>

```ts
class ParametricGeometry extends BufferGeometry {

	/**
	 * Constructs a new parametric geometry.
	 *
	 * @param {ParametricGeometry~Func} func - The parametric function. Default is a function that generates a curved plane surface.
	 * @param {number} [slices=8] - The number of slices to use for the parametric function.
	 * @param {number} [stacks=8] - The stacks of slices to use for the parametric function.
	 */
	constructor( func = ( u, v, target ) => target.set( u, v, Math.cos( u ) * Math.sin( v ) ), slices = 8, stacks = 8 ) {

		super();

		this.type = 'ParametricGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			func: func,
			slices: slices,
			stacks: stacks
		};

		// buffers

		const indices = [];
		const vertices = [];
		const normals = [];
		const uvs = [];

		const EPS = 0.00001;

		const normal = new Vector3();

		const p0 = new Vector3(), p1 = new Vector3();
		const pu = new Vector3(), pv = new Vector3();

		// generate vertices, normals and uvs

		const sliceCount = slices + 1;

		for ( let i = 0; i <= stacks; i ++ ) {

			const v = i / stacks;

			for ( let j = 0; j <= slices; j ++ ) {

				const u = j / slices;

				// vertex

				func( u, v, p0 );
				vertices.push( p0.x, p0.y, p0.z );

				// normal

				// approximate tangent vectors via finite differences

				if ( u - EPS >= 0 ) {

					func( u - EPS, v, p1 );
					pu.subVectors( p0, p1 );

				} else {

					func( u + EPS, v, p1 );
					pu.subVectors( p1, p0 );

				}

				if ( v - EPS >= 0 ) {

					func( u, v - EPS, p1 );
					pv.subVectors( p0, p1 );

				} else {

					func( u, v + EPS, p1 );
					pv.subVectors( p1, p0 );

				}

				// cross product of tangent vectors returns surface normal

				normal.crossVectors( pu, pv ).normalize();
				normals.push( normal.x, normal.y, normal.z );

				// uv

				uvs.push( u, v );

			}

		}

		// generate indices

		for ( let i = 0; i < stacks; i ++ ) {

			for ( let j = 0; j < slices; j ++ ) {

				const a = i * sliceCount + j;
				const b = i * sliceCount + j + 1;
				const c = ( i + 1 ) * sliceCount + j + 1;
				const d = ( i + 1 ) * sliceCount + j;

				// faces one and two

				indices.push( a, b, d );
				indices.push( b, c, d );

			}

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


---