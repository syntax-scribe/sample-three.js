[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ShapeGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/ShapeGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `Shape` | `../extras/core/Shape.js` |
| `ShapeUtils` | `../extras/ShapeUtils.js` |
| `Vector2` | `../math/Vector2.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `groupStart` | `number` | let/var | `0` | ✗ |
| `groupCount` | `number` | let/var | `0` | ✗ |
| `indexOffset` | `number` | let/var | `vertices.length / 3` | ✗ |
| `shapeVertices` | `any` | let/var | `points.shape` | ✗ |
| `shapeHoles` | `any` | let/var | `points.holes` | ✗ |
| `shapeHole` | `any` | let/var | `shapeHoles[ i ]` | ✗ |
| `shapeHole` | `any` | let/var | `shapeHoles[ i ]` | ✗ |
| `vertex` | `any` | let/var | `shapeVertices[ i ]` | ✗ |
| `face` | `number[]` | let/var | `faces[ i ]` | ✗ |
| `a` | `number` | let/var | `face[ 0 ] + indexOffset` | ✗ |
| `b` | `number` | let/var | `face[ 1 ] + indexOffset` | ✗ |
| `c` | `number` | let/var | `face[ 2 ] + indexOffset` | ✗ |
| `shapes` | `any` | let/var | `this.parameters.shapes` | ✗ |
| `geometryShapes` | `any[]` | let/var | `[]` | ✗ |
| `shape` | `Shape` | let/var | `shapes[ data.shapes[ j ] ]` | ✗ |
| `shape` | `any` | let/var | `shapes[ i ]` | ✗ |


---

## Functions

### `ShapeGeometry.copy(source: any): this`

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

### `ShapeGeometry.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		const shapes = this.parameters.shapes;

		return toJSON( shapes, data );

	}
```
</details>

### `ShapeGeometry.fromJSON(data: any, shapes: Shape[]): ShapeGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @param {Array<Shape>} shapes - An array of shapes.
	 * @return {ShapeGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`
- **`shapes`** `Shape[]`

**Returns:** `ShapeGeometry`

**Calls:**

- `geometryShapes.push`

<details><summary>Code</summary>

```typescript
static fromJSON( data, shapes ) {

		const geometryShapes = [];

		for ( let j = 0, jl = data.shapes.length; j < jl; j ++ ) {

			const shape = shapes[ data.shapes[ j ] ];

			geometryShapes.push( shape );

		}

		return new ShapeGeometry( geometryShapes, data.curveSegments );

	}
```
</details>

### `addShape(shape: any): void`

**Parameters:**

- **`shape`** `any`

**Returns:** `void`

**Calls:**

- `shape.extractPoints`
- `ShapeUtils.isClockWise`
- `shapeVertices.reverse`
- `shapeHole.reverse`
- `ShapeUtils.triangulateShape`
- `shapeVertices.concat`
- `vertices.push`
- `normals.push`
- `uvs.push`
- `indices.push`

**Internal Comments:**
```
// check direction of vertices
// join vertices of inner and outer paths to a single array
// vertices, normals, uvs
// indices
```

<details><summary>Code</summary>

```typescript
function addShape( shape ) {

			const indexOffset = vertices.length / 3;
			const points = shape.extractPoints( curveSegments );

			let shapeVertices = points.shape;
			const shapeHoles = points.holes;

			// check direction of vertices

			if ( ShapeUtils.isClockWise( shapeVertices ) === false ) {

				shapeVertices = shapeVertices.reverse();

			}

			for ( let i = 0, l = shapeHoles.length; i < l; i ++ ) {

				const shapeHole = shapeHoles[ i ];

				if ( ShapeUtils.isClockWise( shapeHole ) === true ) {

					shapeHoles[ i ] = shapeHole.reverse();

				}

			}

			const faces = ShapeUtils.triangulateShape( shapeVertices, shapeHoles );

			// join vertices of inner and outer paths to a single array

			for ( let i = 0, l = shapeHoles.length; i < l; i ++ ) {

				const shapeHole = shapeHoles[ i ];
				shapeVertices = shapeVertices.concat( shapeHole );

			}

			// vertices, normals, uvs

			for ( let i = 0, l = shapeVertices.length; i < l; i ++ ) {

				const vertex = shapeVertices[ i ];

				vertices.push( vertex.x, vertex.y, 0 );
				normals.push( 0, 0, 1 );
				uvs.push( vertex.x, vertex.y ); // world uvs

			}

			// indices

			for ( let i = 0, l = faces.length; i < l; i ++ ) {

				const face = faces[ i ];

				const a = face[ 0 ] + indexOffset;
				const b = face[ 1 ] + indexOffset;
				const c = face[ 2 ] + indexOffset;

				indices.push( a, b, c );
				groupCount += 3;

			}

		}
```
</details>

### `toJSON(shapes: any, data: any): any`

**Parameters:**

- **`shapes`** `any`
- **`data`** `any`

**Returns:** `any`

**Calls:**

- `Array.isArray`
- `data.shapes.push`

<details><summary>Code</summary>

```typescript
function toJSON( shapes, data ) {

	data.shapes = [];

	if ( Array.isArray( shapes ) ) {

		for ( let i = 0, l = shapes.length; i < l; i ++ ) {

			const shape = shapes[ i ];

			data.shapes.push( shape.uuid );

		}

	} else {

		data.shapes.push( shapes.uuid );

	}

	return data;

}
```
</details>


---

## Classes

### `ShapeGeometry`

<details><summary>Class Code</summary>

```ts
class ShapeGeometry extends BufferGeometry {

	/**
	 * Constructs a new shape geometry.
	 *
	 * @param {Shape|Array<Shape>} [shapes] - A shape or an array of shapes.
	 * @param {number} [curveSegments=12] - Number of segments per shape.
	 */
	constructor( shapes = new Shape( [ new Vector2( 0, 0.5 ), new Vector2( - 0.5, - 0.5 ), new Vector2( 0.5, - 0.5 ) ] ), curveSegments = 12 ) {

		super();

		this.type = 'ShapeGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			shapes: shapes,
			curveSegments: curveSegments
		};

		// buffers

		const indices = [];
		const vertices = [];
		const normals = [];
		const uvs = [];

		// helper variables

		let groupStart = 0;
		let groupCount = 0;

		// allow single and array values for "shapes" parameter

		if ( Array.isArray( shapes ) === false ) {

			addShape( shapes );

		} else {

			for ( let i = 0; i < shapes.length; i ++ ) {

				addShape( shapes[ i ] );

				this.addGroup( groupStart, groupCount, i ); // enables MultiMaterial support

				groupStart += groupCount;
				groupCount = 0;

			}

		}

		// build geometry

		this.setIndex( indices );
		this.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		this.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );


		// helper functions

		function addShape( shape ) {

			const indexOffset = vertices.length / 3;
			const points = shape.extractPoints( curveSegments );

			let shapeVertices = points.shape;
			const shapeHoles = points.holes;

			// check direction of vertices

			if ( ShapeUtils.isClockWise( shapeVertices ) === false ) {

				shapeVertices = shapeVertices.reverse();

			}

			for ( let i = 0, l = shapeHoles.length; i < l; i ++ ) {

				const shapeHole = shapeHoles[ i ];

				if ( ShapeUtils.isClockWise( shapeHole ) === true ) {

					shapeHoles[ i ] = shapeHole.reverse();

				}

			}

			const faces = ShapeUtils.triangulateShape( shapeVertices, shapeHoles );

			// join vertices of inner and outer paths to a single array

			for ( let i = 0, l = shapeHoles.length; i < l; i ++ ) {

				const shapeHole = shapeHoles[ i ];
				shapeVertices = shapeVertices.concat( shapeHole );

			}

			// vertices, normals, uvs

			for ( let i = 0, l = shapeVertices.length; i < l; i ++ ) {

				const vertex = shapeVertices[ i ];

				vertices.push( vertex.x, vertex.y, 0 );
				normals.push( 0, 0, 1 );
				uvs.push( vertex.x, vertex.y ); // world uvs

			}

			// indices

			for ( let i = 0, l = faces.length; i < l; i ++ ) {

				const face = faces[ i ];

				const a = face[ 0 ] + indexOffset;
				const b = face[ 1 ] + indexOffset;
				const c = face[ 2 ] + indexOffset;

				indices.push( a, b, c );
				groupCount += 3;

			}

		}

	}

	copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		const shapes = this.parameters.shapes;

		return toJSON( shapes, data );

	}

	/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @param {Array<Shape>} shapes - An array of shapes.
	 * @return {ShapeGeometry} A new instance.
	 */
	static fromJSON( data, shapes ) {

		const geometryShapes = [];

		for ( let j = 0, jl = data.shapes.length; j < jl; j ++ ) {

			const shape = shapes[ data.shapes[ j ] ];

			geometryShapes.push( shape );

		}

		return new ShapeGeometry( geometryShapes, data.curveSegments );

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

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		const shapes = this.parameters.shapes;

		return toJSON( shapes, data );

	}
```
</details>

##### `fromJSON(data: any, shapes: Shape[]): ShapeGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data, shapes ) {

		const geometryShapes = [];

		for ( let j = 0, jl = data.shapes.length; j < jl; j ++ ) {

			const shape = shapes[ data.shapes[ j ] ];

			geometryShapes.push( shape );

		}

		return new ShapeGeometry( geometryShapes, data.curveSegments );

	}
```
</details>


---