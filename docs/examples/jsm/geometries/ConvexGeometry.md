[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ConvexGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/geometries/ConvexGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Float32BufferAttribute` | `three` |
| `ConvexHull` | `../math/ConvexHull.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `faces` | `any[]` | let/var | `convexHull.faces` | ✗ |
| `face` | `any` | let/var | `faces[ i ]` | ✗ |
| `edge` | `any` | let/var | `face.edge` | ✗ |
| `point` | `any` | let/var | `edge.head().point` | ✗ |


---

## Classes

### `ConvexGeometry`

<details><summary>Class Code</summary>

```ts
class ConvexGeometry extends BufferGeometry {

	/**
	 * Constructs a new convex geometry.
	 *
	 * @param {Array<Vector3>} points - An array of points in 3D space which should be enclosed by the convex hull.
	 */
	constructor( points = [] ) {

		super();

		// buffers

		const vertices = [];
		const normals = [];

		const convexHull = new ConvexHull().setFromPoints( points );

		// generate vertices and normals

		const faces = convexHull.faces;

		for ( let i = 0; i < faces.length; i ++ ) {

			const face = faces[ i ];
			let edge = face.edge;

			// we move along a doubly-connected edge list to access all face points (see HalfEdge docs)

			do {

				const point = edge.head().point;

				vertices.push( point.x, point.y, point.z );
				normals.push( face.normal.x, face.normal.y, face.normal.z );

				edge = edge.next;

			} while ( edge !== face.edge );

		}

		// build geometry

		this.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		this.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

	}

}
```
</details>


---