[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ConvexHull.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 40 |
| 🧱 Classes | 5 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 68 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/math/ConvexHull.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Line3` | `three` |
| `Plane` | `three` |
| `Triangle` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `Visible` | `0` | let/var | `0` | ✗ |
| `Deleted` | `1` | let/var | `1` | ✗ |
| `_v1` | `any` | let/var | `new Vector3()` | ✗ |
| `_line3` | `any` | let/var | `new Line3()` | ✗ |
| `_plane` | `any` | let/var | `new Plane()` | ✗ |
| `_closestPoint` | `any` | let/var | `new Vector3()` | ✗ |
| `_triangle` | `any` | let/var | `new Triangle()` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `geometry` | `any` | let/var | `node.geometry` | ✗ |
| `attribute` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `point` | `any` | let/var | `new Vector3()` | ✗ |
| `faces` | `any[]` | let/var | `this.faces` | ✗ |
| `face` | `any` | let/var | `faces[ i ]` | ✗ |
| `faces` | `any[]` | let/var | `this.faces` | ✗ |
| `tNear` | `number` | let/var | `- Infinity` | ✗ |
| `tFar` | `number` | let/var | `Infinity` | ✗ |
| `face` | `any` | let/var | `faces[ i ]` | ✗ |
| `t` | `number` | let/var | `( vD !== 0 ) ? ( - vN / vD ) : 0` | ✗ |
| `start` | `VertexNode` | let/var | `face.outside` | ✗ |
| `end` | `VertexNode` | let/var | `face.outside` | ✗ |
| `vertex` | `VertexNode` | let/var | `faceVertices` | ✗ |
| `nextVertex` | `VertexNode` | let/var | `vertex.next` | ✗ |
| `nextVertex` | `VertexNode` | let/var | `vertex.next` | ✗ |
| `maxDistance` | `number` | let/var | `this.tolerance` | ✗ |
| `maxFace` | `any` | let/var | `null` | ✗ |
| `face` | `Face` | let/var | `newFaces[ i ]` | ✗ |
| `min` | `any` | let/var | `new Vector3()` | ✗ |
| `max` | `any` | let/var | `new Vector3()` | ✗ |
| `minVertices` | `any[]` | let/var | `[]` | ✗ |
| `maxVertices` | `any[]` | let/var | `[]` | ✗ |
| `vertex` | `any` | let/var | `this.vertices[ i ]` | ✗ |
| `point` | `any` | let/var | `vertex.point` | ✗ |
| `vertices` | `any[]` | let/var | `this.vertices` | ✗ |
| `min` | `any` | let/var | `extremes.min` | ✗ |
| `max` | `any` | let/var | `extremes.max` | ✗ |
| `maxDistance` | `number` | let/var | `0` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `distance` | `number` | let/var | `max[ i ].point.getComponent( i ) - min[ i ].point.getComponent( i )` | ✗ |
| `v0` | `any` | let/var | `min[ index ]` | ✗ |
| `v1` | `any` | let/var | `max[ index ]` | ✗ |
| `v2` | `any` | let/var | `*not shown*` | ✗ |
| `v3` | `any` | let/var | `*not shown*` | ✗ |
| `vertex` | `any` | let/var | `vertices[ i ]` | ✗ |
| `vertex` | `any` | let/var | `vertices[ i ]` | ✗ |
| `faces` | `any[]` | let/var | `[]` | ✗ |
| `j` | `number` | let/var | `( i + 1 ) % 3` | ✗ |
| `j` | `number` | let/var | `( i + 1 ) % 3` | ✗ |
| `vertex` | `any` | let/var | `vertices[ i ]` | ✗ |
| `maxFace` | `any` | let/var | `null` | ✗ |
| `activeFaces` | `any[]` | let/var | `[]` | ✗ |
| `face` | `any` | let/var | `this.faces[ i ]` | ✗ |
| `eyeVertex` | `any` | let/var | `*not shown*` | ✗ |
| `maxDistance` | `number` | let/var | `0` | ✗ |
| `eyeFace` | `Face` | let/var | `this.assigned.first().face` | ✗ |
| `vertex` | `VertexNode` | let/var | `eyeFace.outside` | ✗ |
| `edge` | `any` | let/var | `*not shown*` | ✗ |
| `twinEdge` | `HalfEdge` | let/var | `edge.twin` | ✗ |
| `oppositeFace` | `Face` | let/var | `twinEdge.face` | ✗ |
| `firstSideEdge` | `any` | let/var | `null` | ✗ |
| `previousSideEdge` | `any` | let/var | `null` | ✗ |
| `horizonEdge` | `HalfEdge` | let/var | `horizon[ i ]` | ✗ |
| `horizon` | `any[]` | let/var | `[]` | ✗ |
| `vertex` | `any` | let/var | `*not shown*` | ✗ |
| `face` | `Face` | let/var | `new Face()` | ✗ |
| `e0` | `HalfEdge` | let/var | `new HalfEdge( a, face )` | ✗ |
| `e1` | `HalfEdge` | let/var | `new HalfEdge( b, face )` | ✗ |
| `e2` | `HalfEdge` | let/var | `new HalfEdge( c, face )` | ✗ |
| `edge` | `HalfEdge` | let/var | `this.edge` | ✗ |


---

## Functions

### `ConvexHull.setFromPoints(points: Vector3[]): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Computes to convex hull for the given array of points.
	 *
	 * @param {Array<Vector3>} points - The array of points in 3D space.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Parameters:**

- **`points`** `Vector3[]`

**Returns:** `ConvexHull`

**Calls:**

- `this.makeEmpty`
- `this.vertices.push`
- `this._compute`

**Internal Comments:**
```
// The algorithm needs at least four points.
```

<details><summary>Code</summary>

```typescript
setFromPoints( points ) {

		// The algorithm needs at least four points.

		if ( points.length >= 4 ) {

			this.makeEmpty();

			for ( let i = 0, l = points.length; i < l; i ++ ) {

				this.vertices.push( new VertexNode( points[ i ] ) );

			}

			this._compute();

		}

		return this;

	}
```
</details>

### `ConvexHull.setFromObject(object: Object3D): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Computes the convex hull of the given 3D object (including its descendants),
	 * accounting for the world transforms of both the 3D object and its descendants.
	 *
	 * @param {Object3D} object - The 3D object to compute the convex hull for.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Parameters:**

- **`object`** `Object3D`

**Returns:** `ConvexHull`

**Calls:**

- `object.updateMatrixWorld`
- `object.traverse`
- `point.fromBufferAttribute( attribute, i ).applyMatrix4`
- `points.push`
- `this.setFromPoints`

<details><summary>Code</summary>

```typescript
setFromObject( object ) {

		const points = [];

		object.updateMatrixWorld( true );

		object.traverse( function ( node ) {

			const geometry = node.geometry;

			if ( geometry !== undefined ) {

				const attribute = geometry.attributes.position;

				if ( attribute !== undefined ) {

					for ( let i = 0, l = attribute.count; i < l; i ++ ) {

						const point = new Vector3();

						point.fromBufferAttribute( attribute, i ).applyMatrix4( node.matrixWorld );

						points.push( point );

					}

				}

			}

		} );

		return this.setFromPoints( points );

	}
```
</details>

### `ConvexHull.containsPoint(point: Vector3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given point lies in the convex hull.
	 *
	 * @param {Vector3} point - The point to test.
	 * @return {boolean} Whether the given point lies in the convex hull or not.
	 */
```

**Parameters:**

- **`point`** `Vector3`

**Returns:** `boolean`

**Calls:**

- `face.distanceToPoint`

**Internal Comments:**
```
// compute signed distance and check on what half space the point lies
```

<details><summary>Code</summary>

```typescript
containsPoint( point ) {

		const faces = this.faces;

		for ( let i = 0, l = faces.length; i < l; i ++ ) {

			const face = faces[ i ];

			// compute signed distance and check on what half space the point lies

			if ( face.distanceToPoint( point ) > this.tolerance ) return false;

		}

		return true;

	}
```
</details>

### `ConvexHull.intersectRay(ray: Ray, target: Vector3): any`

**JSDoc:**
```typescript
/**
	 * Computes the intersections point of the given ray and this convex hull.
	 *
	 * @param {Ray} ray - The ray to test.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3|null} The intersection point. Returns `null` if not intersection was detected.
	 */
```

**Parameters:**

- **`ray`** `Ray`
- **`target`** `Vector3`

**Returns:** `any`

**Calls:**

- `face.distanceToPoint`
- `face.normal.dot`
- `Math.min`
- `Math.max`
- `ray.at`

**Internal Comments:**
```
// based on "Fast Ray-Convex Polyhedron Intersection" by Eric Haines, GRAPHICS GEMS II (x2)
// interpret faces as planes for the further computation (x2)
// if the origin is on the positive side of a plane (so the plane can "see" the origin) and
// the ray is turned away or parallel to the plane, there is no intersection
// compute the distance from the ray’s origin to the intersection with the plane (x2)
// only proceed if the distance is positive. a negative distance means the intersection point
// lies "behind" the origin
// now categorized plane as front-facing or back-facing
// plane faces away from the ray, so this plane is a back-face (x3)
// front-face (x3)
// if tNear ever is greater than tFar, the ray must miss the convex hull
// evaluate intersection point
// always try tNear first since its the closer intersection point
```

<details><summary>Code</summary>

```typescript
intersectRay( ray, target ) {

		// based on "Fast Ray-Convex Polyhedron Intersection" by Eric Haines, GRAPHICS GEMS II

		const faces = this.faces;

		let tNear = - Infinity;
		let tFar = Infinity;

		for ( let i = 0, l = faces.length; i < l; i ++ ) {

			const face = faces[ i ];

			// interpret faces as planes for the further computation

			const vN = face.distanceToPoint( ray.origin );
			const vD = face.normal.dot( ray.direction );

			// if the origin is on the positive side of a plane (so the plane can "see" the origin) and
			// the ray is turned away or parallel to the plane, there is no intersection

			if ( vN > 0 && vD >= 0 ) return null;

			// compute the distance from the ray’s origin to the intersection with the plane

			const t = ( vD !== 0 ) ? ( - vN / vD ) : 0;

			// only proceed if the distance is positive. a negative distance means the intersection point
			// lies "behind" the origin

			if ( t <= 0 ) continue;

			// now categorized plane as front-facing or back-facing

			if ( vD > 0 ) {

				// plane faces away from the ray, so this plane is a back-face

				tFar = Math.min( t, tFar );

			} else {

				// front-face

				tNear = Math.max( t, tNear );

			}

			if ( tNear > tFar ) {

				// if tNear ever is greater than tFar, the ray must miss the convex hull

				return null;

			}

		}

		// evaluate intersection point

		// always try tNear first since its the closer intersection point

		if ( tNear !== - Infinity ) {

			ray.at( tNear, target );

		} else {

			ray.at( tFar, target );

		}

		return target;

	}
```
</details>

### `ConvexHull.intersectsRay(ray: Ray): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given ray intersects with this convex hull.
	 *
	 * @param {Ray} ray - The ray to test.
	 * @return {boolean} Whether the given ray intersects with this convex hull or not.
	 */
```

**Parameters:**

- **`ray`** `Ray`

**Returns:** `boolean`

**Calls:**

- `this.intersectRay`

<details><summary>Code</summary>

```typescript
intersectsRay( ray ) {

		return this.intersectRay( ray, _v1 ) !== null;

	}
```
</details>

### `ConvexHull.makeEmpty(): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Makes the convex hull empty.
	 *
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Returns:** `ConvexHull`

<details><summary>Code</summary>

```typescript
makeEmpty() {

		this.faces = [];
		this.vertices = [];

		return this;

	}
```
</details>

### `ConvexHull._addVertexToFace(vertex: VertexNode, face: Face): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Adds a vertex to the 'assigned' list of vertices and assigns it to the given face.
	 *
	 * @private
	 * @param {VertexNode} vertex - The vertex to add.
	 * @param {Face} face - The target face.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Parameters:**

- **`vertex`** `VertexNode`
- **`face`** `Face`

**Returns:** `ConvexHull`

**Calls:**

- `this.assigned.append`
- `this.assigned.insertBefore`

<details><summary>Code</summary>

```typescript
_addVertexToFace( vertex, face ) {

		vertex.face = face;

		if ( face.outside === null ) {

			this.assigned.append( vertex );

		} else {

			this.assigned.insertBefore( face.outside, vertex );

		}

		face.outside = vertex;

		return this;

	}
```
</details>

### `ConvexHull._removeVertexFromFace(vertex: VertexNode, face: Face): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Removes a vertex from the 'assigned' list of vertices and from the given face.
	 * It also makes sure that the link from 'face' to the first vertex it sees in 'assigned'
	 * is linked correctly after the removal.
	 *
	 * @private
	 * @param {VertexNode} vertex - The vertex to remove.
	 * @param {Face} face - The target face.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Parameters:**

- **`vertex`** `VertexNode`
- **`face`** `Face`

**Returns:** `ConvexHull`

**Calls:**

- `this.assigned.remove`

**Internal Comments:**
```
// fix face.outside link
// face has at least 2 outside vertices, move the 'outside' reference (x4)
// vertex was the only outside vertex that face had (x4)
```

<details><summary>Code</summary>

```typescript
_removeVertexFromFace( vertex, face ) {

		if ( vertex === face.outside ) {

			// fix face.outside link

			if ( vertex.next !== null && vertex.next.face === face ) {

				// face has at least 2 outside vertices, move the 'outside' reference

				face.outside = vertex.next;

			} else {

				// vertex was the only outside vertex that face had

				face.outside = null;

			}

		}

		this.assigned.remove( vertex );

		return this;

	}
```
</details>

### `ConvexHull._removeAllVerticesFromFace(face: Face): VertexNode`

**JSDoc:**
```typescript
/**
	 * Removes all the visible vertices that a given face is able to see which are stored in
	 * the 'assigned' vertex list.
	 *
	 * @private
	 * @param {Face} face - The target face.
	 * @return {VertexNode|undefined} A reference to this convex hull.
	 */
```

**Parameters:**

- **`face`** `Face`

**Returns:** `VertexNode`

**Calls:**

- `this.assigned.removeSubList`

**Internal Comments:**
```
// reference to the first and last vertex of this face (x2)
// fix references (x4)
```

<details><summary>Code</summary>

```typescript
_removeAllVerticesFromFace( face ) {

		if ( face.outside !== null ) {

			// reference to the first and last vertex of this face

			const start = face.outside;
			let end = face.outside;

			while ( end.next !== null && end.next.face === face ) {

				end = end.next;

			}

			this.assigned.removeSubList( start, end );

			// fix references

			start.prev = end.next = null;
			face.outside = null;

			return start;

		}

	}
```
</details>

### `ConvexHull._deleteFaceVertices(face: Face, absorbingFace: Face): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Removes all the visible vertices that `face` is able to see.
	 *
	 * - If `absorbingFace` doesn't exist, then all the removed vertices will be added to the 'unassigned' vertex list.
	 * - If `absorbingFace` exists, then this method will assign all the vertices of 'face' that can see 'absorbingFace'.
	 * - If a vertex cannot see `absorbingFace`, it's added to the 'unassigned' vertex list.
	 *
	 * @private
	 * @param {Face} face - The given face.
	 * @param {Face} [absorbingFace] - An optional face that tries to absorb the vertices of the first face.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Parameters:**

- **`face`** `Face`
- **`absorbingFace`** `Face`

**Returns:** `ConvexHull`

**Calls:**

- `this._removeAllVerticesFromFace`
- `this.unassigned.appendChain`
- `absorbingFace.distanceToPoint`
- `this._addVertexToFace`
- `this.unassigned.append`

**Internal Comments:**
```
// mark the vertices to be reassigned to some other face (x5)
// if there's an absorbing face try to assign as many vertices as possible to it (x2)
// we need to buffer the subsequent vertex at this point because the 'vertex.next' reference (x2)
// will be changed by upcoming method calls (x2)
// check if 'vertex' is able to see 'absorbingFace'
// now assign next vertex (x3)
```

<details><summary>Code</summary>

```typescript
_deleteFaceVertices( face, absorbingFace ) {

		const faceVertices = this._removeAllVerticesFromFace( face );

		if ( faceVertices !== undefined ) {

			if ( absorbingFace === undefined ) {

				// mark the vertices to be reassigned to some other face

				this.unassigned.appendChain( faceVertices );


			} else {

				// if there's an absorbing face try to assign as many vertices as possible to it

				let vertex = faceVertices;

				do {

					// we need to buffer the subsequent vertex at this point because the 'vertex.next' reference
					// will be changed by upcoming method calls

					const nextVertex = vertex.next;

					const distance = absorbingFace.distanceToPoint( vertex.point );

					// check if 'vertex' is able to see 'absorbingFace'

					if ( distance > this.tolerance ) {

						this._addVertexToFace( vertex, absorbingFace );

					} else {

						this.unassigned.append( vertex );

					}

					// now assign next vertex

					vertex = nextVertex;

				} while ( vertex !== null );

			}

		}

		return this;

	}
```
</details>

### `ConvexHull._resolveUnassignedPoints(newFaces: Face[]): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Reassigns as many vertices as possible from the unassigned list to the new faces.
	 *
	 * @private
	 * @param {Array<Face>} newFaces - The new faces.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Parameters:**

- **`newFaces`** `Face[]`

**Returns:** `ConvexHull`

**Calls:**

- `this.unassigned.isEmpty`
- `this.unassigned.first`
- `face.distanceToPoint`
- `this._addVertexToFace`

**Internal Comments:**
```
// buffer 'next' reference, see ._deleteFaceVertices() (x2)
// 'maxFace' can be null e.g. if there are identical vertices
```

<details><summary>Code</summary>

```typescript
_resolveUnassignedPoints( newFaces ) {

		if ( this.unassigned.isEmpty() === false ) {

			let vertex = this.unassigned.first();

			do {

				// buffer 'next' reference, see ._deleteFaceVertices()

				const nextVertex = vertex.next;

				let maxDistance = this.tolerance;

				let maxFace = null;

				for ( let i = 0; i < newFaces.length; i ++ ) {

					const face = newFaces[ i ];

					if ( face.mark === Visible ) {

						const distance = face.distanceToPoint( vertex.point );

						if ( distance > maxDistance ) {

							maxDistance = distance;
							maxFace = face;

						}

						if ( maxDistance > 1000 * this.tolerance ) break;

					}

				}

				// 'maxFace' can be null e.g. if there are identical vertices

				if ( maxFace !== null ) {

					this._addVertexToFace( vertex, maxFace );

				}

				vertex = nextVertex;

			} while ( vertex !== null );

		}

		return this;

	}
```
</details>

### `ConvexHull._computeExtremes(): any`

**JSDoc:**
```typescript
/**
	 * Computes the extremes values (min/max vectors) which will be used to
	 * compute the initial hull.
	 *
	 * @private
	 * @return {Object} The extremes.
	 */
```

**Returns:** `any`

**Calls:**

- `min.copy`
- `max.copy`
- `point.getComponent`
- `min.getComponent`
- `min.setComponent`
- `max.getComponent`
- `max.setComponent`
- `Math.max`
- `Math.abs`

**Internal Comments:**
```
// initially assume that the first vertex is the min/max
// compute the min/max vertex on all six directions
// update the min coordinates
// update the max coordinates
// use min/max vectors to compute an optimal epsilon (x4)
```

<details><summary>Code</summary>

```typescript
_computeExtremes() {

		const min = new Vector3();
		const max = new Vector3();

		const minVertices = [];
		const maxVertices = [];

		// initially assume that the first vertex is the min/max

		for ( let i = 0; i < 3; i ++ ) {

			minVertices[ i ] = maxVertices[ i ] = this.vertices[ 0 ];

		}

		min.copy( this.vertices[ 0 ].point );
		max.copy( this.vertices[ 0 ].point );

		// compute the min/max vertex on all six directions

		for ( let i = 0, l = this.vertices.length; i < l; i ++ ) {

			const vertex = this.vertices[ i ];
			const point = vertex.point;

			// update the min coordinates

			for ( let j = 0; j < 3; j ++ ) {

				if ( point.getComponent( j ) < min.getComponent( j ) ) {

					min.setComponent( j, point.getComponent( j ) );
					minVertices[ j ] = vertex;

				}

			}

			// update the max coordinates

			for ( let j = 0; j < 3; j ++ ) {

				if ( point.getComponent( j ) > max.getComponent( j ) ) {

					max.setComponent( j, point.getComponent( j ) );
					maxVertices[ j ] = vertex;

				}

			}

		}

		// use min/max vectors to compute an optimal epsilon

		this.tolerance = 3 * Number.EPSILON * (
			Math.max( Math.abs( min.x ), Math.abs( max.x ) ) +
			Math.max( Math.abs( min.y ), Math.abs( max.y ) ) +
			Math.max( Math.abs( min.z ), Math.abs( max.z ) )
		);

		return { min: minVertices, max: maxVertices };

	}
```
</details>

### `ConvexHull._computeInitialHull(): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Computes the initial simplex assigning to its faces all the points that are
	 * candidates to form part of the hull.
	 *
	 * @private
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Returns:** `ConvexHull`

**Calls:**

- `this._computeExtremes`
- `max[ i ].point.getComponent`
- `min[ i ].point.getComponent`
- `_line3.set`
- `_line3.closestPointToPoint`
- `_closestPoint.distanceToSquared`
- `_plane.setFromCoplanarPoints`
- `Math.abs`
- `_plane.distanceToPoint`
- `faces.push`
- `Face.create`
- `faces[ i + 1 ].getEdge( 2 ).setTwin`
- `faces[ 0 ].getEdge`
- `faces[ i + 1 ].getEdge( 1 ).setTwin`
- `faces[ j + 1 ].getEdge`
- `faces[ i + 1 ].getEdge( 0 ).setTwin`
- `this.faces.push`
- `this.faces[ j ].distanceToPoint`
- `this._addVertexToFace`

**Internal Comments:**
```
// 1. Find the two vertices 'v0' and 'v1' with the greatest 1d separation (x2)
// (max.x - min.x) (x2)
// (max.y - min.y) (x2)
// (max.z - min.z) (x2)
// 2. The next vertex 'v2' is the one farthest to the line formed by 'v0' and 'v1' (x3)
// 3. The next vertex 'v3' is the one farthest to the plane 'v0', 'v1', 'v2' (x3)
// the face is not able to see the point so 'plane.normal' is pointing outside the tetrahedron (x4)
// set the twin edge (x2)
// join face[ i ] i > 0, with the first face (x14)
// join face[ i ] with face[ i + 1 ], 1 <= i <= 3 (x7)
// the face is able to see the point so 'plane.normal' is pointing inside the tetrahedron (x4)
// join face[ i ] with face[ i + 1 ] (x7)
// the initial hull is the tetrahedron
// initial assignment of vertices to the faces of the tetrahedron
```

<details><summary>Code</summary>

```typescript
_computeInitialHull() {

		const vertices = this.vertices;
		const extremes = this._computeExtremes();
		const min = extremes.min;
		const max = extremes.max;

		// 1. Find the two vertices 'v0' and 'v1' with the greatest 1d separation
		// (max.x - min.x)
		// (max.y - min.y)
		// (max.z - min.z)

		let maxDistance = 0;
		let index = 0;

		for ( let i = 0; i < 3; i ++ ) {

			const distance = max[ i ].point.getComponent( i ) - min[ i ].point.getComponent( i );

			if ( distance > maxDistance ) {

				maxDistance = distance;
				index = i;

			}

		}

		const v0 = min[ index ];
		const v1 = max[ index ];
		let v2;
		let v3;

		// 2. The next vertex 'v2' is the one farthest to the line formed by 'v0' and 'v1'

		maxDistance = 0;
		_line3.set( v0.point, v1.point );

		for ( let i = 0, l = this.vertices.length; i < l; i ++ ) {

			const vertex = vertices[ i ];

			if ( vertex !== v0 && vertex !== v1 ) {

				_line3.closestPointToPoint( vertex.point, true, _closestPoint );

				const distance = _closestPoint.distanceToSquared( vertex.point );

				if ( distance > maxDistance ) {

					maxDistance = distance;
					v2 = vertex;

				}

			}

		}

		// 3. The next vertex 'v3' is the one farthest to the plane 'v0', 'v1', 'v2'

		maxDistance = - 1;
		_plane.setFromCoplanarPoints( v0.point, v1.point, v2.point );

		for ( let i = 0, l = this.vertices.length; i < l; i ++ ) {

			const vertex = vertices[ i ];

			if ( vertex !== v0 && vertex !== v1 && vertex !== v2 ) {

				const distance = Math.abs( _plane.distanceToPoint( vertex.point ) );

				if ( distance > maxDistance ) {

					maxDistance = distance;
					v3 = vertex;

				}

			}

		}

		const faces = [];

		if ( _plane.distanceToPoint( v3.point ) < 0 ) {

			// the face is not able to see the point so 'plane.normal' is pointing outside the tetrahedron

			faces.push(
				Face.create( v0, v1, v2 ),
				Face.create( v3, v1, v0 ),
				Face.create( v3, v2, v1 ),
				Face.create( v3, v0, v2 )
			);

			// set the twin edge

			for ( let i = 0; i < 3; i ++ ) {

				const j = ( i + 1 ) % 3;

				// join face[ i ] i > 0, with the first face

				faces[ i + 1 ].getEdge( 2 ).setTwin( faces[ 0 ].getEdge( j ) );

				// join face[ i ] with face[ i + 1 ], 1 <= i <= 3

				faces[ i + 1 ].getEdge( 1 ).setTwin( faces[ j + 1 ].getEdge( 0 ) );

			}

		} else {

			// the face is able to see the point so 'plane.normal' is pointing inside the tetrahedron

			faces.push(
				Face.create( v0, v2, v1 ),
				Face.create( v3, v0, v1 ),
				Face.create( v3, v1, v2 ),
				Face.create( v3, v2, v0 )
			);

			// set the twin edge

			for ( let i = 0; i < 3; i ++ ) {

				const j = ( i + 1 ) % 3;

				// join face[ i ] i > 0, with the first face

				faces[ i + 1 ].getEdge( 2 ).setTwin( faces[ 0 ].getEdge( ( 3 - i ) % 3 ) );

				// join face[ i ] with face[ i + 1 ]

				faces[ i + 1 ].getEdge( 0 ).setTwin( faces[ j + 1 ].getEdge( 1 ) );

			}

		}

		// the initial hull is the tetrahedron

		for ( let i = 0; i < 4; i ++ ) {

			this.faces.push( faces[ i ] );

		}

		// initial assignment of vertices to the faces of the tetrahedron

		for ( let i = 0, l = vertices.length; i < l; i ++ ) {

			const vertex = vertices[ i ];

			if ( vertex !== v0 && vertex !== v1 && vertex !== v2 && vertex !== v3 ) {

				maxDistance = this.tolerance;
				let maxFace = null;

				for ( let j = 0; j < 4; j ++ ) {

					const distance = this.faces[ j ].distanceToPoint( vertex.point );

					if ( distance > maxDistance ) {

						maxDistance = distance;
						maxFace = this.faces[ j ];

					}

				}

				if ( maxFace !== null ) {

					this._addVertexToFace( vertex, maxFace );

				}

			}

		}

		return this;

	}
```
</details>

### `ConvexHull._reindexFaces(): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Removes inactive (e.g. deleted) faces from the internal face list.
	 *
	 * @private
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Returns:** `ConvexHull`

**Calls:**

- `activeFaces.push`

<details><summary>Code</summary>

```typescript
_reindexFaces() {

		const activeFaces = [];

		for ( let i = 0; i < this.faces.length; i ++ ) {

			const face = this.faces[ i ];

			if ( face.mark === Visible ) {

				activeFaces.push( face );

			}

		}

		this.faces = activeFaces;

		return this;

	}
```
</details>

### `ConvexHull._nextVertexToAdd(): VertexNode`

**JSDoc:**
```typescript
/**
	 * Finds the next vertex to create faces with the current hull.
	 *
	 * - Let the initial face be the first face existing in the 'assigned' vertex list.
	 * - If a face doesn't exist then return since there're no vertices left.
	 * - Otherwise for each vertex that face sees find the one furthest away from it.
	 *
	 * @private
	 * @return {?VertexNode} The next vertex to add.
	 */
```

**Returns:** `VertexNode`

**Calls:**

- `this.assigned.isEmpty`
- `this.assigned.first`
- `eyeFace.distanceToPoint`

**Internal Comments:**
```
// if the 'assigned' list of vertices is empty, no vertices are left. return with 'undefined'
// grab the first available face and start with the first visible vertex of that face (x2)
// now calculate the farthest vertex that face can see
```

<details><summary>Code</summary>

```typescript
_nextVertexToAdd() {

		// if the 'assigned' list of vertices is empty, no vertices are left. return with 'undefined'

		if ( this.assigned.isEmpty() === false ) {

			let eyeVertex, maxDistance = 0;

			// grab the first available face and start with the first visible vertex of that face

			const eyeFace = this.assigned.first().face;
			let vertex = eyeFace.outside;

			// now calculate the farthest vertex that face can see

			do {

				const distance = eyeFace.distanceToPoint( vertex.point );

				if ( distance > maxDistance ) {

					maxDistance = distance;
					eyeVertex = vertex;

				}

				vertex = vertex.next;

			} while ( vertex !== null && vertex.face === eyeFace );

			return eyeVertex;

		}

	}
```
</details>

### `ConvexHull._computeHorizon(eyePoint: Vector3, crossEdge: HalfEdge, face: Face, horizon: HalfEdge[]): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Computes a chain of half edges in CCW order called the 'horizon'. For an edge
	 * to be part of the horizon it must join a face that can see 'eyePoint' and a face
	 * that cannot see 'eyePoint'.
	 *
	 * @private
	 * @param {Vector3} eyePoint - The 3D-coordinates of a point.
	 * @param {HalfEdge} crossEdge - The edge used to jump to the current face.
	 * @param {Face} face - The current face being tested.
	 * @param {Array<HalfEdge>} horizon - The edges that form part of the horizon in CCW order.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Parameters:**

- **`eyePoint`** `Vector3`
- **`crossEdge`** `HalfEdge`
- **`face`** `Face`
- **`horizon`** `HalfEdge[]`

**Returns:** `ConvexHull`

**Calls:**

- `this._deleteFaceVertices`
- `face.getEdge`
- `oppositeFace.distanceToPoint`
- `this._computeHorizon`
- `horizon.push`

**Internal Comments:**
```
// moves face's vertices to the 'unassigned' vertex list (x4)
// start from the next edge since 'crossEdge' was already analyzed (x3)
// (actually 'crossEdge.twin' was the edge who called this method recursively) (x3)
// the opposite face can see the vertex, so proceed with next edge (x4)
// the opposite face can't see the vertex, so this edge is part of the horizon (x4)
```

<details><summary>Code</summary>

```typescript
_computeHorizon( eyePoint, crossEdge, face, horizon ) {

		// moves face's vertices to the 'unassigned' vertex list

		this._deleteFaceVertices( face );

		face.mark = Deleted;

		let edge;

		if ( crossEdge === null ) {

			edge = crossEdge = face.getEdge( 0 );

		} else {

			// start from the next edge since 'crossEdge' was already analyzed
			// (actually 'crossEdge.twin' was the edge who called this method recursively)

			edge = crossEdge.next;

		}

		do {

			const twinEdge = edge.twin;
			const oppositeFace = twinEdge.face;

			if ( oppositeFace.mark === Visible ) {

				if ( oppositeFace.distanceToPoint( eyePoint ) > this.tolerance ) {

					// the opposite face can see the vertex, so proceed with next edge

					this._computeHorizon( eyePoint, twinEdge, oppositeFace, horizon );

				} else {

					// the opposite face can't see the vertex, so this edge is part of the horizon

					horizon.push( edge );

				}

			}

			edge = edge.next;

		} while ( edge !== crossEdge );

		return this;

	}
```
</details>

### `ConvexHull._addAdjoiningFace(eyeVertex: VertexNode, horizonEdge: HalfEdge): HalfEdge`

**JSDoc:**
```typescript
/**
	 * Creates a face with the vertices 'eyeVertex.point', 'horizonEdge.tail' and 'horizonEdge.head'
	 * in CCW order. All the half edges are created in CCW order thus the face is always pointing
	 * outside the hull.
	 *
	 * @private
	 * @param {VertexNode} eyeVertex - The vertex that is added to the hull.
	 * @param {HalfEdge} horizonEdge - A single edge of the horizon.
	 * @return {HalfEdge} The half edge whose vertex is the eyeVertex.
	 */
```

**Parameters:**

- **`eyeVertex`** `VertexNode`
- **`horizonEdge`** `HalfEdge`

**Returns:** `HalfEdge`

**Calls:**

- `Face.create`
- `horizonEdge.tail`
- `horizonEdge.head`
- `this.faces.push`
- `face.getEdge( - 1 ).setTwin`
- `face.getEdge`

**Internal Comments:**
```
// all the half edges are created in ccw order thus the face is always pointing outside the hull (x2)
// join face.getEdge( - 1 ) with the horizon's opposite edge face.getEdge( - 1 ) = face.getEdge( 2 ) (x6)
```

<details><summary>Code</summary>

```typescript
_addAdjoiningFace( eyeVertex, horizonEdge ) {

		// all the half edges are created in ccw order thus the face is always pointing outside the hull

		const face = Face.create( eyeVertex, horizonEdge.tail(), horizonEdge.head() );

		this.faces.push( face );

		// join face.getEdge( - 1 ) with the horizon's opposite edge face.getEdge( - 1 ) = face.getEdge( 2 )

		face.getEdge( - 1 ).setTwin( horizonEdge.twin );

		return face.getEdge( 0 ); // the half edge whose vertex is the eyeVertex


	}
```
</details>

### `ConvexHull._addNewFaces(eyeVertex: VertexNode, horizon: HalfEdge[]): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Adds 'horizon.length' faces to the hull, each face will be linked with the horizon
	 * opposite face and the face on the left/right.
	 *
	 * @private
	 * @param {VertexNode} eyeVertex - The vertex that is added to the hull.
	 * @param {Array<HalfEdge>} horizon - The horizon.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Parameters:**

- **`eyeVertex`** `VertexNode`
- **`horizon`** `HalfEdge[]`

**Returns:** `ConvexHull`

**Calls:**

- `this._addAdjoiningFace`
- `sideEdge.next.setTwin`
- `this.newFaces.push`
- `firstSideEdge.next.setTwin`

**Internal Comments:**
```
// returns the right side edge (x2)
// joins face.getEdge( 1 ) with previousFace.getEdge( 0 ) (x5)
// perform final join of new faces (x5)
```

<details><summary>Code</summary>

```typescript
_addNewFaces( eyeVertex, horizon ) {

		this.newFaces = [];

		let firstSideEdge = null;
		let previousSideEdge = null;

		for ( let i = 0; i < horizon.length; i ++ ) {

			const horizonEdge = horizon[ i ];

			// returns the right side edge

			const sideEdge = this._addAdjoiningFace( eyeVertex, horizonEdge );

			if ( firstSideEdge === null ) {

				firstSideEdge = sideEdge;

			} else {

				// joins face.getEdge( 1 ) with previousFace.getEdge( 0 )

				sideEdge.next.setTwin( previousSideEdge );

			}

			this.newFaces.push( sideEdge.face );
			previousSideEdge = sideEdge;

		}

		// perform final join of new faces

		firstSideEdge.next.setTwin( previousSideEdge );

		return this;

	}
```
</details>

### `ConvexHull._addVertexToHull(eyeVertex: VertexNode): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Adds a vertex to the hull with the following algorithm:
	 *
	 * - Compute the 'horizon' which is a chain of half edges. For an edge to belong to this group
	 * it must be the edge connecting a face that can see 'eyeVertex' and a face which cannot see 'eyeVertex'.
	 * - All the faces that can see 'eyeVertex' have its visible vertices removed from the assigned vertex list.
	 * - A new set of faces is created with each edge of the 'horizon' and 'eyeVertex'. Each face is connected
	 * with the opposite horizon face and the face on the left/right.
	 * - The vertices removed from all the visible faces are assigned to the new faces if possible.
	 *
	 * @private
	 * @param {VertexNode} eyeVertex - The vertex to add.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Parameters:**

- **`eyeVertex`** `VertexNode`

**Returns:** `ConvexHull`

**Calls:**

- `this.unassigned.clear`
- `this._removeVertexFromFace`
- `this._computeHorizon`
- `this._addNewFaces`
- `this._resolveUnassignedPoints`

**Internal Comments:**
```
// remove 'eyeVertex' from 'eyeVertex.face' so that it can't be added to the 'unassigned' vertex list (x4)
// reassign 'unassigned' vertices to the new faces (x4)
```

<details><summary>Code</summary>

```typescript
_addVertexToHull( eyeVertex ) {

		const horizon = [];

		this.unassigned.clear();

		// remove 'eyeVertex' from 'eyeVertex.face' so that it can't be added to the 'unassigned' vertex list

		this._removeVertexFromFace( eyeVertex, eyeVertex.face );

		this._computeHorizon( eyeVertex.point, null, eyeVertex.face, horizon );

		this._addNewFaces( eyeVertex, horizon );

		// reassign 'unassigned' vertices to the new faces

		this._resolveUnassignedPoints( this.newFaces );

		return	this;

	}
```
</details>

### `ConvexHull._cleanup(): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Cleans up internal properties after computing the convex hull.
	 *
	 * @private
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Returns:** `ConvexHull`

**Calls:**

- `this.assigned.clear`
- `this.unassigned.clear`

<details><summary>Code</summary>

```typescript
_cleanup() {

		this.assigned.clear();
		this.unassigned.clear();
		this.newFaces = [];

		return this;

	}
```
</details>

### `ConvexHull._compute(): ConvexHull`

**JSDoc:**
```typescript
/**
	 * Starts the execution of the quick hull algorithm.
	 *
	 * @private
	 * @return {ConvexHull} A reference to this convex hull.
	 */
```

**Returns:** `ConvexHull`

**Calls:**

- `this._computeInitialHull`
- `this._nextVertexToAdd`
- `this._addVertexToHull`
- `this._reindexFaces`
- `this._cleanup`

**Internal Comments:**
```
// add all available vertices gradually to the hull
```

<details><summary>Code</summary>

```typescript
_compute() {

		let vertex;

		this._computeInitialHull();

		// add all available vertices gradually to the hull

		while ( ( vertex = this._nextVertexToAdd() ) !== undefined ) {

			this._addVertexToHull( vertex );

		}

		this._reindexFaces();

		this._cleanup();

		return this;

	}
```
</details>

### `Face.create(a: VertexNode, b: VertexNode, c: VertexNode): Face`

**JSDoc:**
```typescript
/**
	 * Creates a face from the given vertex nodes.
	 *
	 * @private
	 * @param {VertexNode} a - The first vertex node.
	 * @param {VertexNode} b - The second vertex node.
	 * @param {VertexNode} c - The third vertex node.
	 * @return {Face} The created face.
	 */
```

**Parameters:**

- **`a`** `VertexNode`
- **`b`** `VertexNode`
- **`c`** `VertexNode`

**Returns:** `Face`

**Calls:**

- `face.compute`

**Internal Comments:**
```
// join edges (x4)
// main half edge reference (x4)
```

<details><summary>Code</summary>

```typescript
static create( a, b, c ) {

		const face = new Face();

		const e0 = new HalfEdge( a, face );
		const e1 = new HalfEdge( b, face );
		const e2 = new HalfEdge( c, face );

		// join edges

		e0.next = e2.prev = e1;
		e1.next = e0.prev = e2;
		e2.next = e1.prev = e0;

		// main half edge reference

		face.edge = e0;

		return face.compute();

	}
```
</details>

### `Face.getEdge(i: number): HalfEdge`

**JSDoc:**
```typescript
/**
	 * Returns an edge by the given index.
	 *
	 * @private
	 * @param {number} i - The edge index.
	 * @return {HalfEdge} The edge.
	 */
```

**Parameters:**

- **`i`** `number`

**Returns:** `HalfEdge`

<details><summary>Code</summary>

```typescript
getEdge( i ) {

		let edge = this.edge;

		while ( i > 0 ) {

			edge = edge.next;
			i --;

		}

		while ( i < 0 ) {

			edge = edge.prev;
			i ++;

		}

		return edge;

	}
```
</details>

### `Face.compute(): Face`

**JSDoc:**
```typescript
/**
	 * Computes all properties of the face.
	 *
	 * @private
	 * @return {Face} A reference to this face.
	 */
```

**Returns:** `Face`

**Calls:**

- `this.edge.tail`
- `this.edge.head`
- `this.edge.next.head`
- `_triangle.set`
- `_triangle.getNormal`
- `_triangle.getMidpoint`
- `_triangle.getArea`
- `this.normal.dot`

<details><summary>Code</summary>

```typescript
compute() {

		const a = this.edge.tail();
		const b = this.edge.head();
		const c = this.edge.next.head();

		_triangle.set( a.point, b.point, c.point );

		_triangle.getNormal( this.normal );
		_triangle.getMidpoint( this.midpoint );
		this.area = _triangle.getArea();

		this.constant = this.normal.dot( this.midpoint );

		return this;

	}
```
</details>

### `Face.distanceToPoint(point: Vector3): number`

**JSDoc:**
```typescript
/**
	 * Returns the signed distance from a given point to the plane representation of this face.
	 *
	 * @private
	 * @param {Vector3} point - The point to compute the distance to.
	 * @return {number} The distance.
	 */
```

**Parameters:**

- **`point`** `Vector3`

**Returns:** `number`

**Calls:**

- `this.normal.dot`

<details><summary>Code</summary>

```typescript
distanceToPoint( point ) {

		return this.normal.dot( point ) - this.constant;

	}
```
</details>

### `HalfEdge.head(): VertexNode`

**JSDoc:**
```typescript
/**
	 * Returns the destination vertex.
	 *
	 * @private
	 * @return {VertexNode} The destination vertex.
	 */
```

**Returns:** `VertexNode`

<details><summary>Code</summary>

```typescript
head() {

		return this.vertex;

	}
```
</details>

### `HalfEdge.tail(): VertexNode`

**JSDoc:**
```typescript
/**
	 * Returns the origin vertex.
	 *
	 * @private
	 * @return {VertexNode} The destination vertex.
	 */
```

**Returns:** `VertexNode`

<details><summary>Code</summary>

```typescript
tail() {

		return this.prev ? this.prev.vertex : null;

	}
```
</details>

### `HalfEdge.length(): number`

**JSDoc:**
```typescript
/**
	 * Returns the Euclidean length (straight-line length) of the edge.
	 *
	 * @private
	 * @return {number} The edge's length.
	 */
```

**Returns:** `number`

**Calls:**

- `this.head`
- `this.tail`
- `tail.point.distanceTo`

<details><summary>Code</summary>

```typescript
length() {

		const head = this.head();
		const tail = this.tail();

		if ( tail !== null ) {

			return tail.point.distanceTo( head.point );

		}

		return - 1;

	}
```
</details>

### `HalfEdge.lengthSquared(): number`

**JSDoc:**
```typescript
/**
	 * Returns the square of the Euclidean length (straight-line length) of the edge.
	 *
	 * @private
	 * @return {number} The square of the edge's length.
	 */
```

**Returns:** `number`

**Calls:**

- `this.head`
- `this.tail`
- `tail.point.distanceToSquared`

<details><summary>Code</summary>

```typescript
lengthSquared() {

		const head = this.head();
		const tail = this.tail();

		if ( tail !== null ) {

			return tail.point.distanceToSquared( head.point );

		}

		return - 1;

	}
```
</details>

### `HalfEdge.setTwin(edge: HalfEdge): HalfEdge`

**JSDoc:**
```typescript
/**
	 * Sets the twin edge of this half-edge. It also ensures that the twin reference
	 * of the given half-edge is correctly set.
	 *
	 * @private
	 * @param {HalfEdge} edge - The twin edge to set.
	 * @return {HalfEdge} A reference to this edge.
	 */
```

**Parameters:**

- **`edge`** `HalfEdge`

**Returns:** `HalfEdge`

<details><summary>Code</summary>

```typescript
setTwin( edge ) {

		this.twin = edge;
		edge.twin = this;

		return this;

	}
```
</details>

### `VertexList.first(): VertexNode`

**JSDoc:**
```typescript
/**
	 * Returns the head reference.
	 *
	 * @private
	 * @return {VertexNode} The head reference.
	 */
```

**Returns:** `VertexNode`

<details><summary>Code</summary>

```typescript
first() {

		return this.head;

	}
```
</details>

### `VertexList.last(): VertexNode`

**JSDoc:**
```typescript
/**
	 * Returns the tail reference.
	 *
	 * @private
	 * @return {VertexNode} The tail reference.
	 */
```

**Returns:** `VertexNode`

<details><summary>Code</summary>

```typescript
last() {

		return this.tail;

	}
```
</details>

### `VertexList.clear(): VertexList`

**JSDoc:**
```typescript
/**
	 * Clears the linked list.
	 *
	 * @private
	 * @return {VertexList} A reference to this vertex list.
	 */
```

**Returns:** `VertexList`

<details><summary>Code</summary>

```typescript
clear() {

		this.head = this.tail = null;

		return this;

	}
```
</details>

### `VertexList.insertBefore(target: VertexNode, vertex: VertexNode): VertexList`

**JSDoc:**
```typescript
/**
	 * Inserts a vertex before a target vertex.
	 *
	 * @private
	 * @param {VertexNode} target - The target.
	 * @param {VertexNode} vertex - The vertex to insert.
	 * @return {VertexList} A reference to this vertex list.
	 */
```

**Parameters:**

- **`target`** `VertexNode`
- **`vertex`** `VertexNode`

**Returns:** `VertexList`

<details><summary>Code</summary>

```typescript
insertBefore( target, vertex ) {

		vertex.prev = target.prev;
		vertex.next = target;

		if ( vertex.prev === null ) {

			this.head = vertex;

		} else {

			vertex.prev.next = vertex;

		}

		target.prev = vertex;

		return this;

	}
```
</details>

### `VertexList.insertAfter(target: VertexNode, vertex: VertexNode): VertexList`

**JSDoc:**
```typescript
/**
	 * Inserts a vertex after a target vertex.
	 *
	 * @private
	 * @param {VertexNode} target - The target.
	 * @param {VertexNode} vertex - The vertex to insert.
	 * @return {VertexList} A reference to this vertex list.
	 */
```

**Parameters:**

- **`target`** `VertexNode`
- **`vertex`** `VertexNode`

**Returns:** `VertexList`

<details><summary>Code</summary>

```typescript
insertAfter( target, vertex ) {

		vertex.prev = target;
		vertex.next = target.next;

		if ( vertex.next === null ) {

			this.tail = vertex;

		} else {

			vertex.next.prev = vertex;

		}

		target.next = vertex;

		return this;

	}
```
</details>

### `VertexList.append(vertex: VertexNode): VertexList`

**JSDoc:**
```typescript
/**
	 * Appends a vertex to this vertex list.
	 *
	 * @private
	 * @param {VertexNode} vertex - The vertex to append.
	 * @return {VertexList} A reference to this vertex list.
	 */
```

**Parameters:**

- **`vertex`** `VertexNode`

**Returns:** `VertexList`

<details><summary>Code</summary>

```typescript
append( vertex ) {

		if ( this.head === null ) {

			this.head = vertex;

		} else {

			this.tail.next = vertex;

		}

		vertex.prev = this.tail;
		vertex.next = null; // the tail has no subsequent vertex

		this.tail = vertex;

		return this;

	}
```
</details>

### `VertexList.appendChain(vertex: VertexNode): VertexList`

**JSDoc:**
```typescript
/**
	 * Appends a chain of vertices where the given vertex is the head.
	 *
	 * @private
	 * @param {VertexNode} vertex - The head vertex of a chain of vertices.
	 * @return {VertexList} A reference to this vertex list.
	 */
```

**Parameters:**

- **`vertex`** `VertexNode`

**Returns:** `VertexList`

**Internal Comments:**
```
// ensure that the 'tail' reference points to the last vertex of the chain
```

<details><summary>Code</summary>

```typescript
appendChain( vertex ) {

		if ( this.head === null ) {

			this.head = vertex;

		} else {

			this.tail.next = vertex;

		}

		vertex.prev = this.tail;

		// ensure that the 'tail' reference points to the last vertex of the chain

		while ( vertex.next !== null ) {

			vertex = vertex.next;

		}

		this.tail = vertex;

		return this;

	}
```
</details>

### `VertexList.remove(vertex: VertexNode): VertexList`

**JSDoc:**
```typescript
/**
	 * Removes a vertex from the linked list.
	 *
	 * @private
	 * @param {VertexNode} vertex - The vertex to remove.
	 * @return {VertexList} A reference to this vertex list.
	 */
```

**Parameters:**

- **`vertex`** `VertexNode`

**Returns:** `VertexList`

<details><summary>Code</summary>

```typescript
remove( vertex ) {

		if ( vertex.prev === null ) {

			this.head = vertex.next;

		} else {

			vertex.prev.next = vertex.next;

		}

		if ( vertex.next === null ) {

			this.tail = vertex.prev;

		} else {

			vertex.next.prev = vertex.prev;

		}

		return this;

	}
```
</details>

### `VertexList.removeSubList(a: VertexNode, b: VertexNode): VertexList`

**JSDoc:**
```typescript
/**
	 * Removes a sublist of vertices from the linked list.
	 *
	 * @private
	 * @param {VertexNode} a - The head of the sublist.
	 * @param {VertexNode} b - The tail of the sublist.
	 * @return {VertexList} A reference to this vertex list.
	 */
```

**Parameters:**

- **`a`** `VertexNode`
- **`b`** `VertexNode`

**Returns:** `VertexList`

<details><summary>Code</summary>

```typescript
removeSubList( a, b ) {

		if ( a.prev === null ) {

			this.head = b.next;

		} else {

			a.prev.next = b.next;

		}

		if ( b.next === null ) {

			this.tail = a.prev;

		} else {

			b.next.prev = a.prev;

		}

		return this;

	}
```
</details>

### `VertexList.isEmpty(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the linked list is empty.
	 *
	 * @private
	 * @return {boolean} Whether the linked list is empty or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isEmpty() {

		return this.head === null;

	}
```
</details>


---

## Classes

### `ConvexHull`

<details><summary>Class Code</summary>

```ts
class ConvexHull {

	/**
	 * Constructs a new convex hull.
	 */
	constructor() {

		this.tolerance = - 1;

		this.faces = []; // the generated faces of the convex hull
		this.newFaces = []; // this array holds the faces that are generated within a single iteration

		// the vertex lists work as follows:
		//
		// let 'a' and 'b' be 'Face' instances
		// let 'v' be points wrapped as instance of 'Vertex'
		//
		//     [v, v, ..., v, v, v, ...]
		//      ^             ^
		//      |             |
		//  a.outside     b.outside
		//
		this.assigned = new VertexList();
		this.unassigned = new VertexList();

		this.vertices = []; // vertices of the hull (internal representation of given geometry data)

	}

	/**
	 * Computes to convex hull for the given array of points.
	 *
	 * @param {Array<Vector3>} points - The array of points in 3D space.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	setFromPoints( points ) {

		// The algorithm needs at least four points.

		if ( points.length >= 4 ) {

			this.makeEmpty();

			for ( let i = 0, l = points.length; i < l; i ++ ) {

				this.vertices.push( new VertexNode( points[ i ] ) );

			}

			this._compute();

		}

		return this;

	}

	/**
	 * Computes the convex hull of the given 3D object (including its descendants),
	 * accounting for the world transforms of both the 3D object and its descendants.
	 *
	 * @param {Object3D} object - The 3D object to compute the convex hull for.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	setFromObject( object ) {

		const points = [];

		object.updateMatrixWorld( true );

		object.traverse( function ( node ) {

			const geometry = node.geometry;

			if ( geometry !== undefined ) {

				const attribute = geometry.attributes.position;

				if ( attribute !== undefined ) {

					for ( let i = 0, l = attribute.count; i < l; i ++ ) {

						const point = new Vector3();

						point.fromBufferAttribute( attribute, i ).applyMatrix4( node.matrixWorld );

						points.push( point );

					}

				}

			}

		} );

		return this.setFromPoints( points );

	}

	/**
	 * Returns `true` if the given point lies in the convex hull.
	 *
	 * @param {Vector3} point - The point to test.
	 * @return {boolean} Whether the given point lies in the convex hull or not.
	 */
	containsPoint( point ) {

		const faces = this.faces;

		for ( let i = 0, l = faces.length; i < l; i ++ ) {

			const face = faces[ i ];

			// compute signed distance and check on what half space the point lies

			if ( face.distanceToPoint( point ) > this.tolerance ) return false;

		}

		return true;

	}

	/**
	 * Computes the intersections point of the given ray and this convex hull.
	 *
	 * @param {Ray} ray - The ray to test.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3|null} The intersection point. Returns `null` if not intersection was detected.
	 */
	intersectRay( ray, target ) {

		// based on "Fast Ray-Convex Polyhedron Intersection" by Eric Haines, GRAPHICS GEMS II

		const faces = this.faces;

		let tNear = - Infinity;
		let tFar = Infinity;

		for ( let i = 0, l = faces.length; i < l; i ++ ) {

			const face = faces[ i ];

			// interpret faces as planes for the further computation

			const vN = face.distanceToPoint( ray.origin );
			const vD = face.normal.dot( ray.direction );

			// if the origin is on the positive side of a plane (so the plane can "see" the origin) and
			// the ray is turned away or parallel to the plane, there is no intersection

			if ( vN > 0 && vD >= 0 ) return null;

			// compute the distance from the ray’s origin to the intersection with the plane

			const t = ( vD !== 0 ) ? ( - vN / vD ) : 0;

			// only proceed if the distance is positive. a negative distance means the intersection point
			// lies "behind" the origin

			if ( t <= 0 ) continue;

			// now categorized plane as front-facing or back-facing

			if ( vD > 0 ) {

				// plane faces away from the ray, so this plane is a back-face

				tFar = Math.min( t, tFar );

			} else {

				// front-face

				tNear = Math.max( t, tNear );

			}

			if ( tNear > tFar ) {

				// if tNear ever is greater than tFar, the ray must miss the convex hull

				return null;

			}

		}

		// evaluate intersection point

		// always try tNear first since its the closer intersection point

		if ( tNear !== - Infinity ) {

			ray.at( tNear, target );

		} else {

			ray.at( tFar, target );

		}

		return target;

	}

	/**
	 * Returns `true` if the given ray intersects with this convex hull.
	 *
	 * @param {Ray} ray - The ray to test.
	 * @return {boolean} Whether the given ray intersects with this convex hull or not.
	 */
	intersectsRay( ray ) {

		return this.intersectRay( ray, _v1 ) !== null;

	}

	/**
	 * Makes the convex hull empty.
	 *
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	makeEmpty() {

		this.faces = [];
		this.vertices = [];

		return this;

	}

	// private

	/**
	 * Adds a vertex to the 'assigned' list of vertices and assigns it to the given face.
	 *
	 * @private
	 * @param {VertexNode} vertex - The vertex to add.
	 * @param {Face} face - The target face.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_addVertexToFace( vertex, face ) {

		vertex.face = face;

		if ( face.outside === null ) {

			this.assigned.append( vertex );

		} else {

			this.assigned.insertBefore( face.outside, vertex );

		}

		face.outside = vertex;

		return this;

	}

	/**
	 * Removes a vertex from the 'assigned' list of vertices and from the given face.
	 * It also makes sure that the link from 'face' to the first vertex it sees in 'assigned'
	 * is linked correctly after the removal.
	 *
	 * @private
	 * @param {VertexNode} vertex - The vertex to remove.
	 * @param {Face} face - The target face.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_removeVertexFromFace( vertex, face ) {

		if ( vertex === face.outside ) {

			// fix face.outside link

			if ( vertex.next !== null && vertex.next.face === face ) {

				// face has at least 2 outside vertices, move the 'outside' reference

				face.outside = vertex.next;

			} else {

				// vertex was the only outside vertex that face had

				face.outside = null;

			}

		}

		this.assigned.remove( vertex );

		return this;

	}

	/**
	 * Removes all the visible vertices that a given face is able to see which are stored in
	 * the 'assigned' vertex list.
	 *
	 * @private
	 * @param {Face} face - The target face.
	 * @return {VertexNode|undefined} A reference to this convex hull.
	 */
	_removeAllVerticesFromFace( face ) {

		if ( face.outside !== null ) {

			// reference to the first and last vertex of this face

			const start = face.outside;
			let end = face.outside;

			while ( end.next !== null && end.next.face === face ) {

				end = end.next;

			}

			this.assigned.removeSubList( start, end );

			// fix references

			start.prev = end.next = null;
			face.outside = null;

			return start;

		}

	}

	/**
	 * Removes all the visible vertices that `face` is able to see.
	 *
	 * - If `absorbingFace` doesn't exist, then all the removed vertices will be added to the 'unassigned' vertex list.
	 * - If `absorbingFace` exists, then this method will assign all the vertices of 'face' that can see 'absorbingFace'.
	 * - If a vertex cannot see `absorbingFace`, it's added to the 'unassigned' vertex list.
	 *
	 * @private
	 * @param {Face} face - The given face.
	 * @param {Face} [absorbingFace] - An optional face that tries to absorb the vertices of the first face.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_deleteFaceVertices( face, absorbingFace ) {

		const faceVertices = this._removeAllVerticesFromFace( face );

		if ( faceVertices !== undefined ) {

			if ( absorbingFace === undefined ) {

				// mark the vertices to be reassigned to some other face

				this.unassigned.appendChain( faceVertices );


			} else {

				// if there's an absorbing face try to assign as many vertices as possible to it

				let vertex = faceVertices;

				do {

					// we need to buffer the subsequent vertex at this point because the 'vertex.next' reference
					// will be changed by upcoming method calls

					const nextVertex = vertex.next;

					const distance = absorbingFace.distanceToPoint( vertex.point );

					// check if 'vertex' is able to see 'absorbingFace'

					if ( distance > this.tolerance ) {

						this._addVertexToFace( vertex, absorbingFace );

					} else {

						this.unassigned.append( vertex );

					}

					// now assign next vertex

					vertex = nextVertex;

				} while ( vertex !== null );

			}

		}

		return this;

	}

	/**
	 * Reassigns as many vertices as possible from the unassigned list to the new faces.
	 *
	 * @private
	 * @param {Array<Face>} newFaces - The new faces.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_resolveUnassignedPoints( newFaces ) {

		if ( this.unassigned.isEmpty() === false ) {

			let vertex = this.unassigned.first();

			do {

				// buffer 'next' reference, see ._deleteFaceVertices()

				const nextVertex = vertex.next;

				let maxDistance = this.tolerance;

				let maxFace = null;

				for ( let i = 0; i < newFaces.length; i ++ ) {

					const face = newFaces[ i ];

					if ( face.mark === Visible ) {

						const distance = face.distanceToPoint( vertex.point );

						if ( distance > maxDistance ) {

							maxDistance = distance;
							maxFace = face;

						}

						if ( maxDistance > 1000 * this.tolerance ) break;

					}

				}

				// 'maxFace' can be null e.g. if there are identical vertices

				if ( maxFace !== null ) {

					this._addVertexToFace( vertex, maxFace );

				}

				vertex = nextVertex;

			} while ( vertex !== null );

		}

		return this;

	}

	/**
	 * Computes the extremes values (min/max vectors) which will be used to
	 * compute the initial hull.
	 *
	 * @private
	 * @return {Object} The extremes.
	 */
	_computeExtremes() {

		const min = new Vector3();
		const max = new Vector3();

		const minVertices = [];
		const maxVertices = [];

		// initially assume that the first vertex is the min/max

		for ( let i = 0; i < 3; i ++ ) {

			minVertices[ i ] = maxVertices[ i ] = this.vertices[ 0 ];

		}

		min.copy( this.vertices[ 0 ].point );
		max.copy( this.vertices[ 0 ].point );

		// compute the min/max vertex on all six directions

		for ( let i = 0, l = this.vertices.length; i < l; i ++ ) {

			const vertex = this.vertices[ i ];
			const point = vertex.point;

			// update the min coordinates

			for ( let j = 0; j < 3; j ++ ) {

				if ( point.getComponent( j ) < min.getComponent( j ) ) {

					min.setComponent( j, point.getComponent( j ) );
					minVertices[ j ] = vertex;

				}

			}

			// update the max coordinates

			for ( let j = 0; j < 3; j ++ ) {

				if ( point.getComponent( j ) > max.getComponent( j ) ) {

					max.setComponent( j, point.getComponent( j ) );
					maxVertices[ j ] = vertex;

				}

			}

		}

		// use min/max vectors to compute an optimal epsilon

		this.tolerance = 3 * Number.EPSILON * (
			Math.max( Math.abs( min.x ), Math.abs( max.x ) ) +
			Math.max( Math.abs( min.y ), Math.abs( max.y ) ) +
			Math.max( Math.abs( min.z ), Math.abs( max.z ) )
		);

		return { min: minVertices, max: maxVertices };

	}

	/**
	 * Computes the initial simplex assigning to its faces all the points that are
	 * candidates to form part of the hull.
	 *
	 * @private
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_computeInitialHull() {

		const vertices = this.vertices;
		const extremes = this._computeExtremes();
		const min = extremes.min;
		const max = extremes.max;

		// 1. Find the two vertices 'v0' and 'v1' with the greatest 1d separation
		// (max.x - min.x)
		// (max.y - min.y)
		// (max.z - min.z)

		let maxDistance = 0;
		let index = 0;

		for ( let i = 0; i < 3; i ++ ) {

			const distance = max[ i ].point.getComponent( i ) - min[ i ].point.getComponent( i );

			if ( distance > maxDistance ) {

				maxDistance = distance;
				index = i;

			}

		}

		const v0 = min[ index ];
		const v1 = max[ index ];
		let v2;
		let v3;

		// 2. The next vertex 'v2' is the one farthest to the line formed by 'v0' and 'v1'

		maxDistance = 0;
		_line3.set( v0.point, v1.point );

		for ( let i = 0, l = this.vertices.length; i < l; i ++ ) {

			const vertex = vertices[ i ];

			if ( vertex !== v0 && vertex !== v1 ) {

				_line3.closestPointToPoint( vertex.point, true, _closestPoint );

				const distance = _closestPoint.distanceToSquared( vertex.point );

				if ( distance > maxDistance ) {

					maxDistance = distance;
					v2 = vertex;

				}

			}

		}

		// 3. The next vertex 'v3' is the one farthest to the plane 'v0', 'v1', 'v2'

		maxDistance = - 1;
		_plane.setFromCoplanarPoints( v0.point, v1.point, v2.point );

		for ( let i = 0, l = this.vertices.length; i < l; i ++ ) {

			const vertex = vertices[ i ];

			if ( vertex !== v0 && vertex !== v1 && vertex !== v2 ) {

				const distance = Math.abs( _plane.distanceToPoint( vertex.point ) );

				if ( distance > maxDistance ) {

					maxDistance = distance;
					v3 = vertex;

				}

			}

		}

		const faces = [];

		if ( _plane.distanceToPoint( v3.point ) < 0 ) {

			// the face is not able to see the point so 'plane.normal' is pointing outside the tetrahedron

			faces.push(
				Face.create( v0, v1, v2 ),
				Face.create( v3, v1, v0 ),
				Face.create( v3, v2, v1 ),
				Face.create( v3, v0, v2 )
			);

			// set the twin edge

			for ( let i = 0; i < 3; i ++ ) {

				const j = ( i + 1 ) % 3;

				// join face[ i ] i > 0, with the first face

				faces[ i + 1 ].getEdge( 2 ).setTwin( faces[ 0 ].getEdge( j ) );

				// join face[ i ] with face[ i + 1 ], 1 <= i <= 3

				faces[ i + 1 ].getEdge( 1 ).setTwin( faces[ j + 1 ].getEdge( 0 ) );

			}

		} else {

			// the face is able to see the point so 'plane.normal' is pointing inside the tetrahedron

			faces.push(
				Face.create( v0, v2, v1 ),
				Face.create( v3, v0, v1 ),
				Face.create( v3, v1, v2 ),
				Face.create( v3, v2, v0 )
			);

			// set the twin edge

			for ( let i = 0; i < 3; i ++ ) {

				const j = ( i + 1 ) % 3;

				// join face[ i ] i > 0, with the first face

				faces[ i + 1 ].getEdge( 2 ).setTwin( faces[ 0 ].getEdge( ( 3 - i ) % 3 ) );

				// join face[ i ] with face[ i + 1 ]

				faces[ i + 1 ].getEdge( 0 ).setTwin( faces[ j + 1 ].getEdge( 1 ) );

			}

		}

		// the initial hull is the tetrahedron

		for ( let i = 0; i < 4; i ++ ) {

			this.faces.push( faces[ i ] );

		}

		// initial assignment of vertices to the faces of the tetrahedron

		for ( let i = 0, l = vertices.length; i < l; i ++ ) {

			const vertex = vertices[ i ];

			if ( vertex !== v0 && vertex !== v1 && vertex !== v2 && vertex !== v3 ) {

				maxDistance = this.tolerance;
				let maxFace = null;

				for ( let j = 0; j < 4; j ++ ) {

					const distance = this.faces[ j ].distanceToPoint( vertex.point );

					if ( distance > maxDistance ) {

						maxDistance = distance;
						maxFace = this.faces[ j ];

					}

				}

				if ( maxFace !== null ) {

					this._addVertexToFace( vertex, maxFace );

				}

			}

		}

		return this;

	}

	/**
	 * Removes inactive (e.g. deleted) faces from the internal face list.
	 *
	 * @private
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_reindexFaces() {

		const activeFaces = [];

		for ( let i = 0; i < this.faces.length; i ++ ) {

			const face = this.faces[ i ];

			if ( face.mark === Visible ) {

				activeFaces.push( face );

			}

		}

		this.faces = activeFaces;

		return this;

	}

	/**
	 * Finds the next vertex to create faces with the current hull.
	 *
	 * - Let the initial face be the first face existing in the 'assigned' vertex list.
	 * - If a face doesn't exist then return since there're no vertices left.
	 * - Otherwise for each vertex that face sees find the one furthest away from it.
	 *
	 * @private
	 * @return {?VertexNode} The next vertex to add.
	 */
	_nextVertexToAdd() {

		// if the 'assigned' list of vertices is empty, no vertices are left. return with 'undefined'

		if ( this.assigned.isEmpty() === false ) {

			let eyeVertex, maxDistance = 0;

			// grab the first available face and start with the first visible vertex of that face

			const eyeFace = this.assigned.first().face;
			let vertex = eyeFace.outside;

			// now calculate the farthest vertex that face can see

			do {

				const distance = eyeFace.distanceToPoint( vertex.point );

				if ( distance > maxDistance ) {

					maxDistance = distance;
					eyeVertex = vertex;

				}

				vertex = vertex.next;

			} while ( vertex !== null && vertex.face === eyeFace );

			return eyeVertex;

		}

	}

	/**
	 * Computes a chain of half edges in CCW order called the 'horizon'. For an edge
	 * to be part of the horizon it must join a face that can see 'eyePoint' and a face
	 * that cannot see 'eyePoint'.
	 *
	 * @private
	 * @param {Vector3} eyePoint - The 3D-coordinates of a point.
	 * @param {HalfEdge} crossEdge - The edge used to jump to the current face.
	 * @param {Face} face - The current face being tested.
	 * @param {Array<HalfEdge>} horizon - The edges that form part of the horizon in CCW order.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_computeHorizon( eyePoint, crossEdge, face, horizon ) {

		// moves face's vertices to the 'unassigned' vertex list

		this._deleteFaceVertices( face );

		face.mark = Deleted;

		let edge;

		if ( crossEdge === null ) {

			edge = crossEdge = face.getEdge( 0 );

		} else {

			// start from the next edge since 'crossEdge' was already analyzed
			// (actually 'crossEdge.twin' was the edge who called this method recursively)

			edge = crossEdge.next;

		}

		do {

			const twinEdge = edge.twin;
			const oppositeFace = twinEdge.face;

			if ( oppositeFace.mark === Visible ) {

				if ( oppositeFace.distanceToPoint( eyePoint ) > this.tolerance ) {

					// the opposite face can see the vertex, so proceed with next edge

					this._computeHorizon( eyePoint, twinEdge, oppositeFace, horizon );

				} else {

					// the opposite face can't see the vertex, so this edge is part of the horizon

					horizon.push( edge );

				}

			}

			edge = edge.next;

		} while ( edge !== crossEdge );

		return this;

	}

	/**
	 * Creates a face with the vertices 'eyeVertex.point', 'horizonEdge.tail' and 'horizonEdge.head'
	 * in CCW order. All the half edges are created in CCW order thus the face is always pointing
	 * outside the hull.
	 *
	 * @private
	 * @param {VertexNode} eyeVertex - The vertex that is added to the hull.
	 * @param {HalfEdge} horizonEdge - A single edge of the horizon.
	 * @return {HalfEdge} The half edge whose vertex is the eyeVertex.
	 */
	_addAdjoiningFace( eyeVertex, horizonEdge ) {

		// all the half edges are created in ccw order thus the face is always pointing outside the hull

		const face = Face.create( eyeVertex, horizonEdge.tail(), horizonEdge.head() );

		this.faces.push( face );

		// join face.getEdge( - 1 ) with the horizon's opposite edge face.getEdge( - 1 ) = face.getEdge( 2 )

		face.getEdge( - 1 ).setTwin( horizonEdge.twin );

		return face.getEdge( 0 ); // the half edge whose vertex is the eyeVertex


	}

	/**
	 * Adds 'horizon.length' faces to the hull, each face will be linked with the horizon
	 * opposite face and the face on the left/right.
	 *
	 * @private
	 * @param {VertexNode} eyeVertex - The vertex that is added to the hull.
	 * @param {Array<HalfEdge>} horizon - The horizon.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_addNewFaces( eyeVertex, horizon ) {

		this.newFaces = [];

		let firstSideEdge = null;
		let previousSideEdge = null;

		for ( let i = 0; i < horizon.length; i ++ ) {

			const horizonEdge = horizon[ i ];

			// returns the right side edge

			const sideEdge = this._addAdjoiningFace( eyeVertex, horizonEdge );

			if ( firstSideEdge === null ) {

				firstSideEdge = sideEdge;

			} else {

				// joins face.getEdge( 1 ) with previousFace.getEdge( 0 )

				sideEdge.next.setTwin( previousSideEdge );

			}

			this.newFaces.push( sideEdge.face );
			previousSideEdge = sideEdge;

		}

		// perform final join of new faces

		firstSideEdge.next.setTwin( previousSideEdge );

		return this;

	}

	/**
	 * Adds a vertex to the hull with the following algorithm:
	 *
	 * - Compute the 'horizon' which is a chain of half edges. For an edge to belong to this group
	 * it must be the edge connecting a face that can see 'eyeVertex' and a face which cannot see 'eyeVertex'.
	 * - All the faces that can see 'eyeVertex' have its visible vertices removed from the assigned vertex list.
	 * - A new set of faces is created with each edge of the 'horizon' and 'eyeVertex'. Each face is connected
	 * with the opposite horizon face and the face on the left/right.
	 * - The vertices removed from all the visible faces are assigned to the new faces if possible.
	 *
	 * @private
	 * @param {VertexNode} eyeVertex - The vertex to add.
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_addVertexToHull( eyeVertex ) {

		const horizon = [];

		this.unassigned.clear();

		// remove 'eyeVertex' from 'eyeVertex.face' so that it can't be added to the 'unassigned' vertex list

		this._removeVertexFromFace( eyeVertex, eyeVertex.face );

		this._computeHorizon( eyeVertex.point, null, eyeVertex.face, horizon );

		this._addNewFaces( eyeVertex, horizon );

		// reassign 'unassigned' vertices to the new faces

		this._resolveUnassignedPoints( this.newFaces );

		return	this;

	}

	/**
	 * Cleans up internal properties after computing the convex hull.
	 *
	 * @private
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_cleanup() {

		this.assigned.clear();
		this.unassigned.clear();
		this.newFaces = [];

		return this;

	}

	/**
	 * Starts the execution of the quick hull algorithm.
	 *
	 * @private
	 * @return {ConvexHull} A reference to this convex hull.
	 */
	_compute() {

		let vertex;

		this._computeInitialHull();

		// add all available vertices gradually to the hull

		while ( ( vertex = this._nextVertexToAdd() ) !== undefined ) {

			this._addVertexToHull( vertex );

		}

		this._reindexFaces();

		this._cleanup();

		return this;

	}

}
```
</details>

#### Methods

##### `setFromPoints(points: Vector3[]): ConvexHull`

<details><summary>Code</summary>

```ts
setFromPoints( points ) {

		// The algorithm needs at least four points.

		if ( points.length >= 4 ) {

			this.makeEmpty();

			for ( let i = 0, l = points.length; i < l; i ++ ) {

				this.vertices.push( new VertexNode( points[ i ] ) );

			}

			this._compute();

		}

		return this;

	}
```
</details>

##### `setFromObject(object: Object3D): ConvexHull`

<details><summary>Code</summary>

```ts
setFromObject( object ) {

		const points = [];

		object.updateMatrixWorld( true );

		object.traverse( function ( node ) {

			const geometry = node.geometry;

			if ( geometry !== undefined ) {

				const attribute = geometry.attributes.position;

				if ( attribute !== undefined ) {

					for ( let i = 0, l = attribute.count; i < l; i ++ ) {

						const point = new Vector3();

						point.fromBufferAttribute( attribute, i ).applyMatrix4( node.matrixWorld );

						points.push( point );

					}

				}

			}

		} );

		return this.setFromPoints( points );

	}
```
</details>

##### `containsPoint(point: Vector3): boolean`

<details><summary>Code</summary>

```ts
containsPoint( point ) {

		const faces = this.faces;

		for ( let i = 0, l = faces.length; i < l; i ++ ) {

			const face = faces[ i ];

			// compute signed distance and check on what half space the point lies

			if ( face.distanceToPoint( point ) > this.tolerance ) return false;

		}

		return true;

	}
```
</details>

##### `intersectRay(ray: Ray, target: Vector3): any`

<details><summary>Code</summary>

```ts
intersectRay( ray, target ) {

		// based on "Fast Ray-Convex Polyhedron Intersection" by Eric Haines, GRAPHICS GEMS II

		const faces = this.faces;

		let tNear = - Infinity;
		let tFar = Infinity;

		for ( let i = 0, l = faces.length; i < l; i ++ ) {

			const face = faces[ i ];

			// interpret faces as planes for the further computation

			const vN = face.distanceToPoint( ray.origin );
			const vD = face.normal.dot( ray.direction );

			// if the origin is on the positive side of a plane (so the plane can "see" the origin) and
			// the ray is turned away or parallel to the plane, there is no intersection

			if ( vN > 0 && vD >= 0 ) return null;

			// compute the distance from the ray’s origin to the intersection with the plane

			const t = ( vD !== 0 ) ? ( - vN / vD ) : 0;

			// only proceed if the distance is positive. a negative distance means the intersection point
			// lies "behind" the origin

			if ( t <= 0 ) continue;

			// now categorized plane as front-facing or back-facing

			if ( vD > 0 ) {

				// plane faces away from the ray, so this plane is a back-face

				tFar = Math.min( t, tFar );

			} else {

				// front-face

				tNear = Math.max( t, tNear );

			}

			if ( tNear > tFar ) {

				// if tNear ever is greater than tFar, the ray must miss the convex hull

				return null;

			}

		}

		// evaluate intersection point

		// always try tNear first since its the closer intersection point

		if ( tNear !== - Infinity ) {

			ray.at( tNear, target );

		} else {

			ray.at( tFar, target );

		}

		return target;

	}
```
</details>

##### `intersectsRay(ray: Ray): boolean`

<details><summary>Code</summary>

```ts
intersectsRay( ray ) {

		return this.intersectRay( ray, _v1 ) !== null;

	}
```
</details>

##### `makeEmpty(): ConvexHull`

<details><summary>Code</summary>

```ts
makeEmpty() {

		this.faces = [];
		this.vertices = [];

		return this;

	}
```
</details>

##### `_addVertexToFace(vertex: VertexNode, face: Face): ConvexHull`

<details><summary>Code</summary>

```ts
_addVertexToFace( vertex, face ) {

		vertex.face = face;

		if ( face.outside === null ) {

			this.assigned.append( vertex );

		} else {

			this.assigned.insertBefore( face.outside, vertex );

		}

		face.outside = vertex;

		return this;

	}
```
</details>

##### `_removeVertexFromFace(vertex: VertexNode, face: Face): ConvexHull`

<details><summary>Code</summary>

```ts
_removeVertexFromFace( vertex, face ) {

		if ( vertex === face.outside ) {

			// fix face.outside link

			if ( vertex.next !== null && vertex.next.face === face ) {

				// face has at least 2 outside vertices, move the 'outside' reference

				face.outside = vertex.next;

			} else {

				// vertex was the only outside vertex that face had

				face.outside = null;

			}

		}

		this.assigned.remove( vertex );

		return this;

	}
```
</details>

##### `_removeAllVerticesFromFace(face: Face): VertexNode`

<details><summary>Code</summary>

```ts
_removeAllVerticesFromFace( face ) {

		if ( face.outside !== null ) {

			// reference to the first and last vertex of this face

			const start = face.outside;
			let end = face.outside;

			while ( end.next !== null && end.next.face === face ) {

				end = end.next;

			}

			this.assigned.removeSubList( start, end );

			// fix references

			start.prev = end.next = null;
			face.outside = null;

			return start;

		}

	}
```
</details>

##### `_deleteFaceVertices(face: Face, absorbingFace: Face): ConvexHull`

<details><summary>Code</summary>

```ts
_deleteFaceVertices( face, absorbingFace ) {

		const faceVertices = this._removeAllVerticesFromFace( face );

		if ( faceVertices !== undefined ) {

			if ( absorbingFace === undefined ) {

				// mark the vertices to be reassigned to some other face

				this.unassigned.appendChain( faceVertices );


			} else {

				// if there's an absorbing face try to assign as many vertices as possible to it

				let vertex = faceVertices;

				do {

					// we need to buffer the subsequent vertex at this point because the 'vertex.next' reference
					// will be changed by upcoming method calls

					const nextVertex = vertex.next;

					const distance = absorbingFace.distanceToPoint( vertex.point );

					// check if 'vertex' is able to see 'absorbingFace'

					if ( distance > this.tolerance ) {

						this._addVertexToFace( vertex, absorbingFace );

					} else {

						this.unassigned.append( vertex );

					}

					// now assign next vertex

					vertex = nextVertex;

				} while ( vertex !== null );

			}

		}

		return this;

	}
```
</details>

##### `_resolveUnassignedPoints(newFaces: Face[]): ConvexHull`

<details><summary>Code</summary>

```ts
_resolveUnassignedPoints( newFaces ) {

		if ( this.unassigned.isEmpty() === false ) {

			let vertex = this.unassigned.first();

			do {

				// buffer 'next' reference, see ._deleteFaceVertices()

				const nextVertex = vertex.next;

				let maxDistance = this.tolerance;

				let maxFace = null;

				for ( let i = 0; i < newFaces.length; i ++ ) {

					const face = newFaces[ i ];

					if ( face.mark === Visible ) {

						const distance = face.distanceToPoint( vertex.point );

						if ( distance > maxDistance ) {

							maxDistance = distance;
							maxFace = face;

						}

						if ( maxDistance > 1000 * this.tolerance ) break;

					}

				}

				// 'maxFace' can be null e.g. if there are identical vertices

				if ( maxFace !== null ) {

					this._addVertexToFace( vertex, maxFace );

				}

				vertex = nextVertex;

			} while ( vertex !== null );

		}

		return this;

	}
```
</details>

##### `_computeExtremes(): any`

<details><summary>Code</summary>

```ts
_computeExtremes() {

		const min = new Vector3();
		const max = new Vector3();

		const minVertices = [];
		const maxVertices = [];

		// initially assume that the first vertex is the min/max

		for ( let i = 0; i < 3; i ++ ) {

			minVertices[ i ] = maxVertices[ i ] = this.vertices[ 0 ];

		}

		min.copy( this.vertices[ 0 ].point );
		max.copy( this.vertices[ 0 ].point );

		// compute the min/max vertex on all six directions

		for ( let i = 0, l = this.vertices.length; i < l; i ++ ) {

			const vertex = this.vertices[ i ];
			const point = vertex.point;

			// update the min coordinates

			for ( let j = 0; j < 3; j ++ ) {

				if ( point.getComponent( j ) < min.getComponent( j ) ) {

					min.setComponent( j, point.getComponent( j ) );
					minVertices[ j ] = vertex;

				}

			}

			// update the max coordinates

			for ( let j = 0; j < 3; j ++ ) {

				if ( point.getComponent( j ) > max.getComponent( j ) ) {

					max.setComponent( j, point.getComponent( j ) );
					maxVertices[ j ] = vertex;

				}

			}

		}

		// use min/max vectors to compute an optimal epsilon

		this.tolerance = 3 * Number.EPSILON * (
			Math.max( Math.abs( min.x ), Math.abs( max.x ) ) +
			Math.max( Math.abs( min.y ), Math.abs( max.y ) ) +
			Math.max( Math.abs( min.z ), Math.abs( max.z ) )
		);

		return { min: minVertices, max: maxVertices };

	}
```
</details>

##### `_computeInitialHull(): ConvexHull`

<details><summary>Code</summary>

```ts
_computeInitialHull() {

		const vertices = this.vertices;
		const extremes = this._computeExtremes();
		const min = extremes.min;
		const max = extremes.max;

		// 1. Find the two vertices 'v0' and 'v1' with the greatest 1d separation
		// (max.x - min.x)
		// (max.y - min.y)
		// (max.z - min.z)

		let maxDistance = 0;
		let index = 0;

		for ( let i = 0; i < 3; i ++ ) {

			const distance = max[ i ].point.getComponent( i ) - min[ i ].point.getComponent( i );

			if ( distance > maxDistance ) {

				maxDistance = distance;
				index = i;

			}

		}

		const v0 = min[ index ];
		const v1 = max[ index ];
		let v2;
		let v3;

		// 2. The next vertex 'v2' is the one farthest to the line formed by 'v0' and 'v1'

		maxDistance = 0;
		_line3.set( v0.point, v1.point );

		for ( let i = 0, l = this.vertices.length; i < l; i ++ ) {

			const vertex = vertices[ i ];

			if ( vertex !== v0 && vertex !== v1 ) {

				_line3.closestPointToPoint( vertex.point, true, _closestPoint );

				const distance = _closestPoint.distanceToSquared( vertex.point );

				if ( distance > maxDistance ) {

					maxDistance = distance;
					v2 = vertex;

				}

			}

		}

		// 3. The next vertex 'v3' is the one farthest to the plane 'v0', 'v1', 'v2'

		maxDistance = - 1;
		_plane.setFromCoplanarPoints( v0.point, v1.point, v2.point );

		for ( let i = 0, l = this.vertices.length; i < l; i ++ ) {

			const vertex = vertices[ i ];

			if ( vertex !== v0 && vertex !== v1 && vertex !== v2 ) {

				const distance = Math.abs( _plane.distanceToPoint( vertex.point ) );

				if ( distance > maxDistance ) {

					maxDistance = distance;
					v3 = vertex;

				}

			}

		}

		const faces = [];

		if ( _plane.distanceToPoint( v3.point ) < 0 ) {

			// the face is not able to see the point so 'plane.normal' is pointing outside the tetrahedron

			faces.push(
				Face.create( v0, v1, v2 ),
				Face.create( v3, v1, v0 ),
				Face.create( v3, v2, v1 ),
				Face.create( v3, v0, v2 )
			);

			// set the twin edge

			for ( let i = 0; i < 3; i ++ ) {

				const j = ( i + 1 ) % 3;

				// join face[ i ] i > 0, with the first face

				faces[ i + 1 ].getEdge( 2 ).setTwin( faces[ 0 ].getEdge( j ) );

				// join face[ i ] with face[ i + 1 ], 1 <= i <= 3

				faces[ i + 1 ].getEdge( 1 ).setTwin( faces[ j + 1 ].getEdge( 0 ) );

			}

		} else {

			// the face is able to see the point so 'plane.normal' is pointing inside the tetrahedron

			faces.push(
				Face.create( v0, v2, v1 ),
				Face.create( v3, v0, v1 ),
				Face.create( v3, v1, v2 ),
				Face.create( v3, v2, v0 )
			);

			// set the twin edge

			for ( let i = 0; i < 3; i ++ ) {

				const j = ( i + 1 ) % 3;

				// join face[ i ] i > 0, with the first face

				faces[ i + 1 ].getEdge( 2 ).setTwin( faces[ 0 ].getEdge( ( 3 - i ) % 3 ) );

				// join face[ i ] with face[ i + 1 ]

				faces[ i + 1 ].getEdge( 0 ).setTwin( faces[ j + 1 ].getEdge( 1 ) );

			}

		}

		// the initial hull is the tetrahedron

		for ( let i = 0; i < 4; i ++ ) {

			this.faces.push( faces[ i ] );

		}

		// initial assignment of vertices to the faces of the tetrahedron

		for ( let i = 0, l = vertices.length; i < l; i ++ ) {

			const vertex = vertices[ i ];

			if ( vertex !== v0 && vertex !== v1 && vertex !== v2 && vertex !== v3 ) {

				maxDistance = this.tolerance;
				let maxFace = null;

				for ( let j = 0; j < 4; j ++ ) {

					const distance = this.faces[ j ].distanceToPoint( vertex.point );

					if ( distance > maxDistance ) {

						maxDistance = distance;
						maxFace = this.faces[ j ];

					}

				}

				if ( maxFace !== null ) {

					this._addVertexToFace( vertex, maxFace );

				}

			}

		}

		return this;

	}
```
</details>

##### `_reindexFaces(): ConvexHull`

<details><summary>Code</summary>

```ts
_reindexFaces() {

		const activeFaces = [];

		for ( let i = 0; i < this.faces.length; i ++ ) {

			const face = this.faces[ i ];

			if ( face.mark === Visible ) {

				activeFaces.push( face );

			}

		}

		this.faces = activeFaces;

		return this;

	}
```
</details>

##### `_nextVertexToAdd(): VertexNode`

<details><summary>Code</summary>

```ts
_nextVertexToAdd() {

		// if the 'assigned' list of vertices is empty, no vertices are left. return with 'undefined'

		if ( this.assigned.isEmpty() === false ) {

			let eyeVertex, maxDistance = 0;

			// grab the first available face and start with the first visible vertex of that face

			const eyeFace = this.assigned.first().face;
			let vertex = eyeFace.outside;

			// now calculate the farthest vertex that face can see

			do {

				const distance = eyeFace.distanceToPoint( vertex.point );

				if ( distance > maxDistance ) {

					maxDistance = distance;
					eyeVertex = vertex;

				}

				vertex = vertex.next;

			} while ( vertex !== null && vertex.face === eyeFace );

			return eyeVertex;

		}

	}
```
</details>

##### `_computeHorizon(eyePoint: Vector3, crossEdge: HalfEdge, face: Face, horizon: HalfEdge[]): ConvexHull`

<details><summary>Code</summary>

```ts
_computeHorizon( eyePoint, crossEdge, face, horizon ) {

		// moves face's vertices to the 'unassigned' vertex list

		this._deleteFaceVertices( face );

		face.mark = Deleted;

		let edge;

		if ( crossEdge === null ) {

			edge = crossEdge = face.getEdge( 0 );

		} else {

			// start from the next edge since 'crossEdge' was already analyzed
			// (actually 'crossEdge.twin' was the edge who called this method recursively)

			edge = crossEdge.next;

		}

		do {

			const twinEdge = edge.twin;
			const oppositeFace = twinEdge.face;

			if ( oppositeFace.mark === Visible ) {

				if ( oppositeFace.distanceToPoint( eyePoint ) > this.tolerance ) {

					// the opposite face can see the vertex, so proceed with next edge

					this._computeHorizon( eyePoint, twinEdge, oppositeFace, horizon );

				} else {

					// the opposite face can't see the vertex, so this edge is part of the horizon

					horizon.push( edge );

				}

			}

			edge = edge.next;

		} while ( edge !== crossEdge );

		return this;

	}
```
</details>

##### `_addAdjoiningFace(eyeVertex: VertexNode, horizonEdge: HalfEdge): HalfEdge`

<details><summary>Code</summary>

```ts
_addAdjoiningFace( eyeVertex, horizonEdge ) {

		// all the half edges are created in ccw order thus the face is always pointing outside the hull

		const face = Face.create( eyeVertex, horizonEdge.tail(), horizonEdge.head() );

		this.faces.push( face );

		// join face.getEdge( - 1 ) with the horizon's opposite edge face.getEdge( - 1 ) = face.getEdge( 2 )

		face.getEdge( - 1 ).setTwin( horizonEdge.twin );

		return face.getEdge( 0 ); // the half edge whose vertex is the eyeVertex


	}
```
</details>

##### `_addNewFaces(eyeVertex: VertexNode, horizon: HalfEdge[]): ConvexHull`

<details><summary>Code</summary>

```ts
_addNewFaces( eyeVertex, horizon ) {

		this.newFaces = [];

		let firstSideEdge = null;
		let previousSideEdge = null;

		for ( let i = 0; i < horizon.length; i ++ ) {

			const horizonEdge = horizon[ i ];

			// returns the right side edge

			const sideEdge = this._addAdjoiningFace( eyeVertex, horizonEdge );

			if ( firstSideEdge === null ) {

				firstSideEdge = sideEdge;

			} else {

				// joins face.getEdge( 1 ) with previousFace.getEdge( 0 )

				sideEdge.next.setTwin( previousSideEdge );

			}

			this.newFaces.push( sideEdge.face );
			previousSideEdge = sideEdge;

		}

		// perform final join of new faces

		firstSideEdge.next.setTwin( previousSideEdge );

		return this;

	}
```
</details>

##### `_addVertexToHull(eyeVertex: VertexNode): ConvexHull`

<details><summary>Code</summary>

```ts
_addVertexToHull( eyeVertex ) {

		const horizon = [];

		this.unassigned.clear();

		// remove 'eyeVertex' from 'eyeVertex.face' so that it can't be added to the 'unassigned' vertex list

		this._removeVertexFromFace( eyeVertex, eyeVertex.face );

		this._computeHorizon( eyeVertex.point, null, eyeVertex.face, horizon );

		this._addNewFaces( eyeVertex, horizon );

		// reassign 'unassigned' vertices to the new faces

		this._resolveUnassignedPoints( this.newFaces );

		return	this;

	}
```
</details>

##### `_cleanup(): ConvexHull`

<details><summary>Code</summary>

```ts
_cleanup() {

		this.assigned.clear();
		this.unassigned.clear();
		this.newFaces = [];

		return this;

	}
```
</details>

##### `_compute(): ConvexHull`

<details><summary>Code</summary>

```ts
_compute() {

		let vertex;

		this._computeInitialHull();

		// add all available vertices gradually to the hull

		while ( ( vertex = this._nextVertexToAdd() ) !== undefined ) {

			this._addVertexToHull( vertex );

		}

		this._reindexFaces();

		this._cleanup();

		return this;

	}
```
</details>

### `Face`

<details><summary>Class Code</summary>

```ts
class Face {

	/**
	 * Constructs a new face.
	 */
	constructor() {

		/**
		 * The normal vector of the face.
		 *
		 * @private
		 * @type {Vector3}
		 */
		this.normal = new Vector3();

		/**
		 * The midpoint or centroid of the face.
		 *
		 * @private
		 * @type {Vector3}
		 */
		this.midpoint = new Vector3();

		/**
		 * The area of the face.
		 *
		 * @private
		 * @type {number}
		 * @default 0
		 */
		this.area = 0;

		/**
		 * Signed distance from face to the origin.
		 *
		 * @private
		 * @type {number}
		 * @default 0
		 */
		this.constant = 0;

		/**
		 * Reference to a vertex in a vertex list this face can see.
		 *
		 * @private
		 * @type {?VertexNode}
		 * @default null
		 */
		this.outside = null; // reference to a vertex in a vertex list this face can see
		this.mark = Visible;

		/**
		 * Reference to the base edge of a face. To retrieve all edges, you can use the
		 * `next` reference of the current edge.
		 *
		 * @private
		 * @type {?HalfEdge}
		 * @default null
		 */
		this.edge = null;

	}

	/**
	 * Creates a face from the given vertex nodes.
	 *
	 * @private
	 * @param {VertexNode} a - The first vertex node.
	 * @param {VertexNode} b - The second vertex node.
	 * @param {VertexNode} c - The third vertex node.
	 * @return {Face} The created face.
	 */
	static create( a, b, c ) {

		const face = new Face();

		const e0 = new HalfEdge( a, face );
		const e1 = new HalfEdge( b, face );
		const e2 = new HalfEdge( c, face );

		// join edges

		e0.next = e2.prev = e1;
		e1.next = e0.prev = e2;
		e2.next = e1.prev = e0;

		// main half edge reference

		face.edge = e0;

		return face.compute();

	}

	/**
	 * Returns an edge by the given index.
	 *
	 * @private
	 * @param {number} i - The edge index.
	 * @return {HalfEdge} The edge.
	 */
	getEdge( i ) {

		let edge = this.edge;

		while ( i > 0 ) {

			edge = edge.next;
			i --;

		}

		while ( i < 0 ) {

			edge = edge.prev;
			i ++;

		}

		return edge;

	}

	/**
	 * Computes all properties of the face.
	 *
	 * @private
	 * @return {Face} A reference to this face.
	 */
	compute() {

		const a = this.edge.tail();
		const b = this.edge.head();
		const c = this.edge.next.head();

		_triangle.set( a.point, b.point, c.point );

		_triangle.getNormal( this.normal );
		_triangle.getMidpoint( this.midpoint );
		this.area = _triangle.getArea();

		this.constant = this.normal.dot( this.midpoint );

		return this;

	}

	/**
	 * Returns the signed distance from a given point to the plane representation of this face.
	 *
	 * @private
	 * @param {Vector3} point - The point to compute the distance to.
	 * @return {number} The distance.
	 */
	distanceToPoint( point ) {

		return this.normal.dot( point ) - this.constant;

	}

}
```
</details>

#### Methods

##### `create(a: VertexNode, b: VertexNode, c: VertexNode): Face`

<details><summary>Code</summary>

```ts
static create( a, b, c ) {

		const face = new Face();

		const e0 = new HalfEdge( a, face );
		const e1 = new HalfEdge( b, face );
		const e2 = new HalfEdge( c, face );

		// join edges

		e0.next = e2.prev = e1;
		e1.next = e0.prev = e2;
		e2.next = e1.prev = e0;

		// main half edge reference

		face.edge = e0;

		return face.compute();

	}
```
</details>

##### `getEdge(i: number): HalfEdge`

<details><summary>Code</summary>

```ts
getEdge( i ) {

		let edge = this.edge;

		while ( i > 0 ) {

			edge = edge.next;
			i --;

		}

		while ( i < 0 ) {

			edge = edge.prev;
			i ++;

		}

		return edge;

	}
```
</details>

##### `compute(): Face`

<details><summary>Code</summary>

```ts
compute() {

		const a = this.edge.tail();
		const b = this.edge.head();
		const c = this.edge.next.head();

		_triangle.set( a.point, b.point, c.point );

		_triangle.getNormal( this.normal );
		_triangle.getMidpoint( this.midpoint );
		this.area = _triangle.getArea();

		this.constant = this.normal.dot( this.midpoint );

		return this;

	}
```
</details>

##### `distanceToPoint(point: Vector3): number`

<details><summary>Code</summary>

```ts
distanceToPoint( point ) {

		return this.normal.dot( point ) - this.constant;

	}
```
</details>

### `HalfEdge`

<details><summary>Class Code</summary>

```ts
class HalfEdge {

	/**
	 * Constructs a new half edge.
	 *
	 * @param {VertexNode} vertex - A reference to its destination vertex.
	 * @param {Face} face - A reference to its face.
	 */
	constructor( vertex, face ) {

		/**
		 * A reference to its destination vertex.
		 *
		 * @private
		 * @type {VertexNode}
		 */
		this.vertex = vertex;

		/**
		 * Reference to the previous half-edge of the same face.
		 *
		 * @private
		 * @type {?HalfEdge}
		 * @default null
		 */
		this.prev = null;

		/**
		 * Reference to the next half-edge of the same face.
		 *
		 * @private
		 * @type {?HalfEdge}
		 * @default null
		 */
		this.next = null;

		/**
		 * Reference to the twin half-edge to reach the opposite face.
		 *
		 * @private
		 * @type {?HalfEdge}
		 * @default null
		 */
		this.twin = null;

		/**
		 * A reference to its face.
		 *
		 * @private
		 * @type {Face}
		 */
		this.face = face;

	}

	/**
	 * Returns the destination vertex.
	 *
	 * @private
	 * @return {VertexNode} The destination vertex.
	 */
	head() {

		return this.vertex;

	}

	/**
	 * Returns the origin vertex.
	 *
	 * @private
	 * @return {VertexNode} The destination vertex.
	 */
	tail() {

		return this.prev ? this.prev.vertex : null;

	}

	/**
	 * Returns the Euclidean length (straight-line length) of the edge.
	 *
	 * @private
	 * @return {number} The edge's length.
	 */
	length() {

		const head = this.head();
		const tail = this.tail();

		if ( tail !== null ) {

			return tail.point.distanceTo( head.point );

		}

		return - 1;

	}

	/**
	 * Returns the square of the Euclidean length (straight-line length) of the edge.
	 *
	 * @private
	 * @return {number} The square of the edge's length.
	 */
	lengthSquared() {

		const head = this.head();
		const tail = this.tail();

		if ( tail !== null ) {

			return tail.point.distanceToSquared( head.point );

		}

		return - 1;

	}

	/**
	 * Sets the twin edge of this half-edge. It also ensures that the twin reference
	 * of the given half-edge is correctly set.
	 *
	 * @private
	 * @param {HalfEdge} edge - The twin edge to set.
	 * @return {HalfEdge} A reference to this edge.
	 */
	setTwin( edge ) {

		this.twin = edge;
		edge.twin = this;

		return this;

	}

}
```
</details>

#### Methods

##### `head(): VertexNode`

<details><summary>Code</summary>

```ts
head() {

		return this.vertex;

	}
```
</details>

##### `tail(): VertexNode`

<details><summary>Code</summary>

```ts
tail() {

		return this.prev ? this.prev.vertex : null;

	}
```
</details>

##### `length(): number`

<details><summary>Code</summary>

```ts
length() {

		const head = this.head();
		const tail = this.tail();

		if ( tail !== null ) {

			return tail.point.distanceTo( head.point );

		}

		return - 1;

	}
```
</details>

##### `lengthSquared(): number`

<details><summary>Code</summary>

```ts
lengthSquared() {

		const head = this.head();
		const tail = this.tail();

		if ( tail !== null ) {

			return tail.point.distanceToSquared( head.point );

		}

		return - 1;

	}
```
</details>

##### `setTwin(edge: HalfEdge): HalfEdge`

<details><summary>Code</summary>

```ts
setTwin( edge ) {

		this.twin = edge;
		edge.twin = this;

		return this;

	}
```
</details>

### `VertexNode`

<details><summary>Class Code</summary>

```ts
class VertexNode {

	/**
	 * Constructs a new vertex node.
	 *
	 * @param {Vector3} point - A point in 3D space.
	 */
	constructor( point ) {

		/**
		 * A point in 3D space.
		 *
		 * @private
		 * @type {Vector3}
		 */
		this.point = point;

		/**
		 * Reference to the previous vertex in the double linked list.
		 *
		 * @private
		 * @type {?VertexNode}
		 * @default null
		 */
		this.prev = null;

		/**
		 * Reference to the next vertex in the double linked list.
		 *
		 * @private
		 * @type {?VertexNode}
		 * @default null
		 */
		this.next = null;

		/**
		 * Reference to the face that is able to see this vertex.
		 *
		 * @private
		 * @type {?Face}
		 * @default null
		 */
		this.face = null;

	}

}
```
</details>

### `VertexList`

<details><summary>Class Code</summary>

```ts
class VertexList {

	/**
	 * Constructs a new vertex list.
	 */
	constructor() {

		/**
		 * Reference to the first vertex of the linked list.
		 *
		 * @private
		 * @type {?VertexNode}
		 * @default null
		 */
		this.head = null;

		/**
		 * Reference to the last vertex of the linked list.
		 *
		 * @private
		 * @type {?VertexNode}
		 * @default null
		 */
		this.tail = null;

	}

	/**
	 * Returns the head reference.
	 *
	 * @private
	 * @return {VertexNode} The head reference.
	 */
	first() {

		return this.head;

	}

	/**
	 * Returns the tail reference.
	 *
	 * @private
	 * @return {VertexNode} The tail reference.
	 */
	last() {

		return this.tail;

	}

	/**
	 * Clears the linked list.
	 *
	 * @private
	 * @return {VertexList} A reference to this vertex list.
	 */
	clear() {

		this.head = this.tail = null;

		return this;

	}

	/**
	 * Inserts a vertex before a target vertex.
	 *
	 * @private
	 * @param {VertexNode} target - The target.
	 * @param {VertexNode} vertex - The vertex to insert.
	 * @return {VertexList} A reference to this vertex list.
	 */
	insertBefore( target, vertex ) {

		vertex.prev = target.prev;
		vertex.next = target;

		if ( vertex.prev === null ) {

			this.head = vertex;

		} else {

			vertex.prev.next = vertex;

		}

		target.prev = vertex;

		return this;

	}

	/**
	 * Inserts a vertex after a target vertex.
	 *
	 * @private
	 * @param {VertexNode} target - The target.
	 * @param {VertexNode} vertex - The vertex to insert.
	 * @return {VertexList} A reference to this vertex list.
	 */
	insertAfter( target, vertex ) {

		vertex.prev = target;
		vertex.next = target.next;

		if ( vertex.next === null ) {

			this.tail = vertex;

		} else {

			vertex.next.prev = vertex;

		}

		target.next = vertex;

		return this;

	}

	/**
	 * Appends a vertex to this vertex list.
	 *
	 * @private
	 * @param {VertexNode} vertex - The vertex to append.
	 * @return {VertexList} A reference to this vertex list.
	 */
	append( vertex ) {

		if ( this.head === null ) {

			this.head = vertex;

		} else {

			this.tail.next = vertex;

		}

		vertex.prev = this.tail;
		vertex.next = null; // the tail has no subsequent vertex

		this.tail = vertex;

		return this;

	}

	/**
	 * Appends a chain of vertices where the given vertex is the head.
	 *
	 * @private
	 * @param {VertexNode} vertex - The head vertex of a chain of vertices.
	 * @return {VertexList} A reference to this vertex list.
	 */
	appendChain( vertex ) {

		if ( this.head === null ) {

			this.head = vertex;

		} else {

			this.tail.next = vertex;

		}

		vertex.prev = this.tail;

		// ensure that the 'tail' reference points to the last vertex of the chain

		while ( vertex.next !== null ) {

			vertex = vertex.next;

		}

		this.tail = vertex;

		return this;

	}

	/**
	 * Removes a vertex from the linked list.
	 *
	 * @private
	 * @param {VertexNode} vertex - The vertex to remove.
	 * @return {VertexList} A reference to this vertex list.
	 */
	remove( vertex ) {

		if ( vertex.prev === null ) {

			this.head = vertex.next;

		} else {

			vertex.prev.next = vertex.next;

		}

		if ( vertex.next === null ) {

			this.tail = vertex.prev;

		} else {

			vertex.next.prev = vertex.prev;

		}

		return this;

	}

	/**
	 * Removes a sublist of vertices from the linked list.
	 *
	 * @private
	 * @param {VertexNode} a - The head of the sublist.
	 * @param {VertexNode} b - The tail of the sublist.
	 * @return {VertexList} A reference to this vertex list.
	 */
	removeSubList( a, b ) {

		if ( a.prev === null ) {

			this.head = b.next;

		} else {

			a.prev.next = b.next;

		}

		if ( b.next === null ) {

			this.tail = a.prev;

		} else {

			b.next.prev = a.prev;

		}

		return this;

	}

	/**
	 * Returns `true` if the linked list is empty.
	 *
	 * @private
	 * @return {boolean} Whether the linked list is empty or not.
	 */
	isEmpty() {

		return this.head === null;

	}

}
```
</details>

#### Methods

##### `first(): VertexNode`

<details><summary>Code</summary>

```ts
first() {

		return this.head;

	}
```
</details>

##### `last(): VertexNode`

<details><summary>Code</summary>

```ts
last() {

		return this.tail;

	}
```
</details>

##### `clear(): VertexList`

<details><summary>Code</summary>

```ts
clear() {

		this.head = this.tail = null;

		return this;

	}
```
</details>

##### `insertBefore(target: VertexNode, vertex: VertexNode): VertexList`

<details><summary>Code</summary>

```ts
insertBefore( target, vertex ) {

		vertex.prev = target.prev;
		vertex.next = target;

		if ( vertex.prev === null ) {

			this.head = vertex;

		} else {

			vertex.prev.next = vertex;

		}

		target.prev = vertex;

		return this;

	}
```
</details>

##### `insertAfter(target: VertexNode, vertex: VertexNode): VertexList`

<details><summary>Code</summary>

```ts
insertAfter( target, vertex ) {

		vertex.prev = target;
		vertex.next = target.next;

		if ( vertex.next === null ) {

			this.tail = vertex;

		} else {

			vertex.next.prev = vertex;

		}

		target.next = vertex;

		return this;

	}
```
</details>

##### `append(vertex: VertexNode): VertexList`

<details><summary>Code</summary>

```ts
append( vertex ) {

		if ( this.head === null ) {

			this.head = vertex;

		} else {

			this.tail.next = vertex;

		}

		vertex.prev = this.tail;
		vertex.next = null; // the tail has no subsequent vertex

		this.tail = vertex;

		return this;

	}
```
</details>

##### `appendChain(vertex: VertexNode): VertexList`

<details><summary>Code</summary>

```ts
appendChain( vertex ) {

		if ( this.head === null ) {

			this.head = vertex;

		} else {

			this.tail.next = vertex;

		}

		vertex.prev = this.tail;

		// ensure that the 'tail' reference points to the last vertex of the chain

		while ( vertex.next !== null ) {

			vertex = vertex.next;

		}

		this.tail = vertex;

		return this;

	}
```
</details>

##### `remove(vertex: VertexNode): VertexList`

<details><summary>Code</summary>

```ts
remove( vertex ) {

		if ( vertex.prev === null ) {

			this.head = vertex.next;

		} else {

			vertex.prev.next = vertex.next;

		}

		if ( vertex.next === null ) {

			this.tail = vertex.prev;

		} else {

			vertex.next.prev = vertex.prev;

		}

		return this;

	}
```
</details>

##### `removeSubList(a: VertexNode, b: VertexNode): VertexList`

<details><summary>Code</summary>

```ts
removeSubList( a, b ) {

		if ( a.prev === null ) {

			this.head = b.next;

		} else {

			a.prev.next = b.next;

		}

		if ( b.next === null ) {

			this.tail = a.prev;

		} else {

			b.next.prev = a.prev;

		}

		return this;

	}
```
</details>

##### `isEmpty(): boolean`

<details><summary>Code</summary>

```ts
isEmpty() {

		return this.head === null;

	}
```
</details>


---