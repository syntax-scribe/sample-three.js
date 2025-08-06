[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SimplifyModifier.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 🧱 Classes | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 43 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/modifiers/SimplifyModifier.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `Float32BufferAttribute` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |
| `Vector4` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_cb` | `any` | let/var | `new Vector3()` | ✗ |
| `_ab` | `any` | let/var | `new Vector3()` | ✗ |
| `attributes` | `any` | let/var | `geometry.attributes` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `faces` | `any[]` | let/var | `[]` | ✗ |
| `t` | `any` | let/var | `null` | ✗ |
| `v2` | `any` | let/var | `null` | ✗ |
| `nor` | `any` | let/var | `null` | ✗ |
| `col` | `any` | let/var | `null` | ✗ |
| `vertex` | `Vertex` | let/var | `new Vertex( v, v2, nor, t, col )` | ✗ |
| `triangle` | `Triangle` | let/var | `new Triangle( vertices[ a ], vertices[ b ], vertices[ c ], a, b, c )` | ✗ |
| `a` | `number` | let/var | `i` | ✗ |
| `b` | `number` | let/var | `i + 1` | ✗ |
| `c` | `number` | let/var | `i + 2` | ✗ |
| `triangle` | `Triangle` | let/var | `new Triangle( vertices[ a ], vertices[ b ], vertices[ c ], a, b, c )` | ✗ |
| `nextVertex` | `any` | let/var | `*not shown*` | ✗ |
| `z` | `number` | let/var | `count` | ✗ |
| `simplifiedGeometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `position` | `any[]` | let/var | `[]` | ✗ |
| `uv` | `any[]` | let/var | `[]` | ✗ |
| `normal` | `any[]` | let/var | `[]` | ✗ |
| `tangent` | `any[]` | let/var | `[]` | ✗ |
| `color` | `any[]` | let/var | `[]` | ✗ |
| `vertex` | `Vertex` | let/var | `vertices[ i ]` | ✗ |
| `face` | `Triangle` | let/var | `faces[ i ]` | ✗ |
| `curvature` | `number` | let/var | `0` | ✗ |
| `sideFaces` | `any[]` | let/var | `[]` | ✗ |
| `face` | `any` | let/var | `u.faces[ i ]` | ✗ |
| `minCurvature` | `number` | let/var | `1` | ✗ |
| `face` | `any` | let/var | `u.faces[ i ]` | ✗ |
| `sideFace` | `any` | let/var | `sideFaces[ j ]` | ✗ |
| `borders` | `0` | let/var | `0` | ✗ |
| `amt` | `number` | let/var | `edgelength * curvature + borders` | ✗ |
| `vs` | `any[]` | let/var | `[ f.v1, f.v2, f.v3 ]` | ✗ |
| `v1` | `any` | let/var | `vs[ i ]` | ✗ |
| `v2` | `any` | let/var | `vs[ ( i + 1 ) % 3 ]` | ✗ |
| `tmpVertices` | `any[]` | let/var | `[]` | ✗ |
| `least` | `any` | let/var | `vertices[ 0 ]` | ✗ |
| `vA` | `any` | let/var | `this.v1.position` | ✗ |
| `vB` | `any` | let/var | `this.v2.position` | ✗ |
| `vC` | `any` | let/var | `this.v3.position` | ✗ |
| `neighbors` | `any[]` | let/var | `this.neighbors` | ✗ |
| `faces` | `any[]` | let/var | `this.faces` | ✗ |


---

## Functions

### `SimplifyModifier.modify(geometry: BufferGeometry, count: number): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Returns a new, modified version of the given geometry by applying a simplification.
	 * Please note that the resulting geometry is always non-indexed.
	 *
	 * @param {BufferGeometry} geometry - The geometry to modify.
	 * @param {number} count - The number of vertices to remove.
	 * @return {BufferGeometry} A new, modified geometry.
	 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`
- **`count`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `geometry.clone`
- `geometry.deleteAttribute`
- `BufferGeometryUtils.mergeVertices`
- `geometry.getAttribute`
- `new Vector3().fromBufferAttribute`
- `new Vector2().fromBufferAttribute`
- `new Vector4().fromBufferAttribute`
- `new Color().fromBufferAttribute`
- `vertices.push`
- `geometry.getIndex`
- `index.getX`
- `faces.push`
- `computeEdgeCostAtVertex`
- `minimumCostEdge`
- `console.log`
- `collapse`
- `position.push`
- `uv.push`
- `normal.push`
- `tangent.push`
- `color.push`
- `index.push`
- `simplifiedGeometry.setAttribute`
- `simplifiedGeometry.setIndex`

**Internal Comments:**
```
// currently morphAttributes are not supported (x2)
// this modifier can only process indexed and non-indexed geometries with at least a position attribute
// (x8)
// put data of original geometry in different data structures (x2)
// add vertices (x2)
// add faces (x2)
// compute all edge collapse costs
// cache final index to GREATLY speed up faces reconstruction (x4)
```

<details><summary>Code</summary>

```typescript
modify( geometry, count ) {

		geometry = geometry.clone();

		// currently morphAttributes are not supported
		delete geometry.morphAttributes.position;
		delete geometry.morphAttributes.normal;
		const attributes = geometry.attributes;

		// this modifier can only process indexed and non-indexed geometries with at least a position attribute

		for ( const name in attributes ) {

			if ( name !== 'position' && name !== 'uv' && name !== 'normal' && name !== 'tangent' && name !== 'color' ) geometry.deleteAttribute( name );

		}

		geometry = BufferGeometryUtils.mergeVertices( geometry );

		//
		// put data of original geometry in different data structures
		//

		const vertices = [];
		const faces = [];

		// add vertices

		const positionAttribute = geometry.getAttribute( 'position' );
		const uvAttribute = geometry.getAttribute( 'uv' );
		const normalAttribute = geometry.getAttribute( 'normal' );
		const tangentAttribute = geometry.getAttribute( 'tangent' );
		const colorAttribute = geometry.getAttribute( 'color' );

		let t = null;
		let v2 = null;
		let nor = null;
		let col = null;

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			const v = new Vector3().fromBufferAttribute( positionAttribute, i );
			if ( uvAttribute ) {

				v2 = new Vector2().fromBufferAttribute( uvAttribute, i );

			}

			if ( normalAttribute ) {

				nor = new Vector3().fromBufferAttribute( normalAttribute, i );

			}

			if ( tangentAttribute ) {

				t = new Vector4().fromBufferAttribute( tangentAttribute, i );

			}

			if ( colorAttribute ) {

				col = new Color().fromBufferAttribute( colorAttribute, i );

			}

			const vertex = new Vertex( v, v2, nor, t, col );
			vertices.push( vertex );

		}

		// add faces

		let index = geometry.getIndex();

		if ( index !== null ) {

			for ( let i = 0; i < index.count; i += 3 ) {

				const a = index.getX( i );
				const b = index.getX( i + 1 );
				const c = index.getX( i + 2 );

				const triangle = new Triangle( vertices[ a ], vertices[ b ], vertices[ c ], a, b, c );
				faces.push( triangle );

			}

		} else {

			for ( let i = 0; i < positionAttribute.count; i += 3 ) {

				const a = i;
				const b = i + 1;
				const c = i + 2;

				const triangle = new Triangle( vertices[ a ], vertices[ b ], vertices[ c ], a, b, c );
				faces.push( triangle );

			}

		}

		// compute all edge collapse costs

		for ( let i = 0, il = vertices.length; i < il; i ++ ) {

			computeEdgeCostAtVertex( vertices[ i ] );

		}

		let nextVertex;

		let z = count;

		while ( z -- ) {

			nextVertex = minimumCostEdge( vertices );

			if ( ! nextVertex ) {

				console.log( 'THREE.SimplifyModifier: No next vertex' );
				break;

			}

			collapse( vertices, faces, nextVertex, nextVertex.collapseNeighbor );

		}

		//

		const simplifiedGeometry = new BufferGeometry();
		const position = [];
		const uv = [];
		const normal = [];
		const tangent = [];
		const color = [];

		index = [];

		//

		for ( let i = 0; i < vertices.length; i ++ ) {

			const vertex = vertices[ i ];
			position.push( vertex.position.x, vertex.position.y, vertex.position.z );
			if ( vertex.uv ) {

				uv.push( vertex.uv.x, vertex.uv.y );

			}

			if ( vertex.normal ) {

				normal.push( vertex.normal.x, vertex.normal.y, vertex.normal.z );

			}

			if ( vertex.tangent ) {

				tangent.push( vertex.tangent.x, vertex.tangent.y, vertex.tangent.z, vertex.tangent.w );

			}

			if ( vertex.color ) {

				color.push( vertex.color.r, vertex.color.g, vertex.color.b );

			}


			// cache final index to GREATLY speed up faces reconstruction
			vertex.id = i;

		}

		//

		for ( let i = 0; i < faces.length; i ++ ) {

			const face = faces[ i ];
			index.push( face.v1.id, face.v2.id, face.v3.id );

		}

		simplifiedGeometry.setAttribute( 'position', new Float32BufferAttribute( position, 3 ) );
		if ( uv.length > 0 ) simplifiedGeometry.setAttribute( 'uv', new Float32BufferAttribute( uv, 2 ) );
		if ( normal.length > 0 ) simplifiedGeometry.setAttribute( 'normal', new Float32BufferAttribute( normal, 3 ) );
		if ( tangent.length > 0 ) simplifiedGeometry.setAttribute( 'tangent', new Float32BufferAttribute( tangent, 4 ) );
		if ( color.length > 0 ) simplifiedGeometry.setAttribute( 'color', new Float32BufferAttribute( color, 3 ) );

		simplifiedGeometry.setIndex( index );

		return simplifiedGeometry;

	}
```
</details>

### `pushIfUnique(array: any, object: any): void`

**Parameters:**

- **`array`** `any`
- **`object`** `any`

**Returns:** `void`

**Calls:**

- `array.indexOf`
- `array.push`

<details><summary>Code</summary>

```typescript
function pushIfUnique( array, object ) {

	if ( array.indexOf( object ) === - 1 ) array.push( object );

}
```
</details>

### `removeFromArray(array: any, object: any): void`

**Parameters:**

- **`array`** `any`
- **`object`** `any`

**Returns:** `void`

**Calls:**

- `array.indexOf`
- `array.splice`

<details><summary>Code</summary>

```typescript
function removeFromArray( array, object ) {

	const k = array.indexOf( object );
	if ( k > - 1 ) array.splice( k, 1 );

}
```
</details>

### `computeEdgeCollapseCost(u: any, v: any): number`

**Parameters:**

- **`u`** `any`
- **`v`** `any`

**Returns:** `number`

**Calls:**

- `v.position.distanceTo`
- `face.hasVertex`
- `sideFaces.push`
- `face.normal.dot`
- `Math.min`
- `Math.max`

**Internal Comments:**
```
// if we collapse edge uv by moving u to v then how (x2)
// much different will the model change, i.e. the "error". (x2)
// find the "sides" triangles that are on the edge uv
// use the triangle facing most away from the sides
// to determine our curvature term
// use dot product of face normals. (x2)
// crude approach in attempt to preserve borders (x2)
// though it seems not to be totally correct (x2)
// we add some arbitrary cost for borders, (x3)
// borders += 10; (x3)
```

<details><summary>Code</summary>

```typescript
function computeEdgeCollapseCost( u, v ) {

	// if we collapse edge uv by moving u to v then how
	// much different will the model change, i.e. the "error".

	const edgelength = v.position.distanceTo( u.position );
	let curvature = 0;

	const sideFaces = [];

	// find the "sides" triangles that are on the edge uv
	for ( let i = 0, il = u.faces.length; i < il; i ++ ) {

		const face = u.faces[ i ];

		if ( face.hasVertex( v ) ) {

			sideFaces.push( face );

		}

	}

	// use the triangle facing most away from the sides
	// to determine our curvature term
	for ( let i = 0, il = u.faces.length; i < il; i ++ ) {

		let minCurvature = 1;
		const face = u.faces[ i ];

		for ( let j = 0; j < sideFaces.length; j ++ ) {

			const sideFace = sideFaces[ j ];
			// use dot product of face normals.
			const dotProd = face.normal.dot( sideFace.normal );
			minCurvature = Math.min( minCurvature, ( 1.001 - dotProd ) / 2 );

		}

		curvature = Math.max( curvature, minCurvature );

	}

	// crude approach in attempt to preserve borders
	// though it seems not to be totally correct
	const borders = 0;

	if ( sideFaces.length < 2 ) {

		// we add some arbitrary cost for borders,
		// borders += 10;
		curvature = 1;

	}

	const amt = edgelength * curvature + borders;

	return amt;

}
```
</details>

### `computeEdgeCostAtVertex(v: any): void`

**Parameters:**

- **`v`** `any`

**Returns:** `void`

**Calls:**

- `computeEdgeCollapseCost`

**Internal Comments:**
```
// compute the edge collapse cost for all edges that start
// from vertex v.  Since we are only interested in reducing
// the object by selecting the min cost edge at each step, we
// only cache the cost of the least cost edge at this vertex
// (in member variable collapse) as well as the value of the
// cost (in member variable collapseCost).
// collapse if no neighbors. (x4)
// search all neighboring edges for "least cost" edge
// we average the cost of collapsing at this vertex (x4)
```

<details><summary>Code</summary>

```typescript
function computeEdgeCostAtVertex( v ) {

	// compute the edge collapse cost for all edges that start
	// from vertex v.  Since we are only interested in reducing
	// the object by selecting the min cost edge at each step, we
	// only cache the cost of the least cost edge at this vertex
	// (in member variable collapse) as well as the value of the
	// cost (in member variable collapseCost).

	if ( v.neighbors.length === 0 ) {

		// collapse if no neighbors.
		v.collapseNeighbor = null;
		v.collapseCost = - 0.01;

		return;

	}

	v.collapseCost = 100000;
	v.collapseNeighbor = null;

	// search all neighboring edges for "least cost" edge
	for ( let i = 0; i < v.neighbors.length; i ++ ) {

		const collapseCost = computeEdgeCollapseCost( v, v.neighbors[ i ] );

		if ( ! v.collapseNeighbor ) {

			v.collapseNeighbor = v.neighbors[ i ];
			v.collapseCost = collapseCost;
			v.minCost = collapseCost;
			v.totalCost = 0;
			v.costCount = 0;

		}

		v.costCount ++;
		v.totalCost += collapseCost;

		if ( collapseCost < v.minCost ) {

			v.collapseNeighbor = v.neighbors[ i ];
			v.minCost = collapseCost;

		}

	}

	// we average the cost of collapsing at this vertex
	v.collapseCost = v.totalCost / v.costCount;
	// v.collapseCost = v.minCost;

}
```
</details>

### `removeVertex(v: any, vertices: any): void`

**Parameters:**

- **`v`** `any`
- **`vertices`** `any`

**Returns:** `void`

**Calls:**

- `console.assert`
- `v.neighbors.pop`
- `removeFromArray`

<details><summary>Code</summary>

```typescript
function removeVertex( v, vertices ) {

	console.assert( v.faces.length === 0 );

	while ( v.neighbors.length ) {

		const n = v.neighbors.pop();
		removeFromArray( n.neighbors, v );

	}

	removeFromArray( vertices, v );

}
```
</details>

### `removeFace(f: any, faces: any): void`

**Parameters:**

- **`f`** `any`
- **`faces`** `any`

**Returns:** `void`

**Calls:**

- `removeFromArray`
- `v1.removeIfNonNeighbor`
- `v2.removeIfNonNeighbor`

**Internal Comments:**
```
// TODO optimize this! (x2)
```

<details><summary>Code</summary>

```typescript
function removeFace( f, faces ) {

	removeFromArray( faces, f );

	if ( f.v1 ) removeFromArray( f.v1.faces, f );
	if ( f.v2 ) removeFromArray( f.v2.faces, f );
	if ( f.v3 ) removeFromArray( f.v3.faces, f );

	// TODO optimize this!
	const vs = [ f.v1, f.v2, f.v3 ];

	for ( let i = 0; i < 3; i ++ ) {

		const v1 = vs[ i ];
		const v2 = vs[ ( i + 1 ) % 3 ];

		if ( ! v1 || ! v2 ) continue;

		v1.removeIfNonNeighbor( v2 );
		v2.removeIfNonNeighbor( v1 );

	}

}
```
</details>

### `collapse(vertices: any, faces: any, u: any, v: any): void`

**Parameters:**

- **`vertices`** `any`
- **`faces`** `any`
- **`u`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `removeVertex`
- `u.uv.copy`
- `v.normal.add( u.normal ).normalize`
- `v.tangent.add( u.tangent ).normalize`
- `tmpVertices.push`
- `u.faces[ i ].hasVertex`
- `removeFace`
- `u.faces[ i ].replaceVertex`
- `computeEdgeCostAtVertex`

**Internal Comments:**
```
// Collapse the edge uv by moving vertex u onto v
// u is a vertex all by itself so just delete it.. (x3)
// delete triangles on edge uv:
// update remaining triangles to have v instead of u
// recompute the edge collapse costs in neighborhood
```

<details><summary>Code</summary>

```typescript
function collapse( vertices, faces, u, v ) {

	// Collapse the edge uv by moving vertex u onto v

	if ( ! v ) {

		// u is a vertex all by itself so just delete it..
		removeVertex( u, vertices );
		return;

	}

	if ( v.uv ) {

		u.uv.copy( v.uv );

	}

	if ( v.normal ) {

		v.normal.add( u.normal ).normalize();

	}

	if ( v.tangent ) {

		v.tangent.add( u.tangent ).normalize();

	}

	const tmpVertices = [];

	for ( let i = 0; i < u.neighbors.length; i ++ ) {

		tmpVertices.push( u.neighbors[ i ] );

	}


	// delete triangles on edge uv:
	for ( let i = u.faces.length - 1; i >= 0; i -- ) {

		if ( u.faces[ i ] && u.faces[ i ].hasVertex( v ) ) {

			removeFace( u.faces[ i ], faces );

		}

	}

	// update remaining triangles to have v instead of u
	for ( let i = u.faces.length - 1; i >= 0; i -- ) {

		u.faces[ i ].replaceVertex( u, v );

	}


	removeVertex( u, vertices );

	// recompute the edge collapse costs in neighborhood
	for ( let i = 0; i < tmpVertices.length; i ++ ) {

		computeEdgeCostAtVertex( tmpVertices[ i ] );

	}

}
```
</details>

### `minimumCostEdge(vertices: any): any`

**Parameters:**

- **`vertices`** `any`

**Returns:** `any`

**Internal Comments:**
```
// O(n * n) approach. TODO optimize this (x2)
```

<details><summary>Code</summary>

```typescript
function minimumCostEdge( vertices ) {

	// O(n * n) approach. TODO optimize this

	let least = vertices[ 0 ];

	for ( let i = 0; i < vertices.length; i ++ ) {

		if ( vertices[ i ].collapseCost < least.collapseCost ) {

			least = vertices[ i ];

		}

	}

	return least;

}
```
</details>

### `Triangle.computeNormal(): void`

**Returns:** `void`

**Calls:**

- `_cb.subVectors`
- `_ab.subVectors`
- `_cb.cross( _ab ).normalize`
- `this.normal.copy`

<details><summary>Code</summary>

```typescript
computeNormal() {

		const vA = this.v1.position;
		const vB = this.v2.position;
		const vC = this.v3.position;

		_cb.subVectors( vC, vB );
		_ab.subVectors( vA, vB );
		_cb.cross( _ab ).normalize();

		this.normal.copy( _cb );

	}
```
</details>

### `Triangle.hasVertex(v: any): boolean`

**Parameters:**

- **`v`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
hasVertex( v ) {

		return v === this.v1 || v === this.v2 || v === this.v3;

	}
```
</details>

### `Triangle.replaceVertex(oldv: any, newv: any): void`

**Parameters:**

- **`oldv`** `any`
- **`newv`** `any`

**Returns:** `void`

**Calls:**

- `removeFromArray`
- `newv.faces.push`
- `oldv.removeIfNonNeighbor`
- `this.v1.removeIfNonNeighbor`
- `this.v2.removeIfNonNeighbor`
- `this.v3.removeIfNonNeighbor`
- `this.v1.addUniqueNeighbor`
- `this.v2.addUniqueNeighbor`
- `this.v3.addUniqueNeighbor`
- `this.computeNormal`

<details><summary>Code</summary>

```typescript
replaceVertex( oldv, newv ) {

		if ( oldv === this.v1 ) this.v1 = newv;
		else if ( oldv === this.v2 ) this.v2 = newv;
		else if ( oldv === this.v3 ) this.v3 = newv;

		removeFromArray( oldv.faces, this );
		newv.faces.push( this );


		oldv.removeIfNonNeighbor( this.v1 );
		this.v1.removeIfNonNeighbor( oldv );

		oldv.removeIfNonNeighbor( this.v2 );
		this.v2.removeIfNonNeighbor( oldv );

		oldv.removeIfNonNeighbor( this.v3 );
		this.v3.removeIfNonNeighbor( oldv );

		this.v1.addUniqueNeighbor( this.v2 );
		this.v1.addUniqueNeighbor( this.v3 );

		this.v2.addUniqueNeighbor( this.v1 );
		this.v2.addUniqueNeighbor( this.v3 );

		this.v3.addUniqueNeighbor( this.v1 );
		this.v3.addUniqueNeighbor( this.v2 );

		this.computeNormal();

	}
```
</details>

### `Vertex.addUniqueNeighbor(vertex: any): void`

**Parameters:**

- **`vertex`** `any`

**Returns:** `void`

**Calls:**

- `pushIfUnique`

<details><summary>Code</summary>

```typescript
addUniqueNeighbor( vertex ) {

		pushIfUnique( this.neighbors, vertex );

	}
```
</details>

### `Vertex.removeIfNonNeighbor(n: any): void`

**Parameters:**

- **`n`** `any`

**Returns:** `void`

**Calls:**

- `neighbors.indexOf`
- `faces[ i ].hasVertex`
- `neighbors.splice`

<details><summary>Code</summary>

```typescript
removeIfNonNeighbor( n ) {

		const neighbors = this.neighbors;
		const faces = this.faces;

		const offset = neighbors.indexOf( n );

		if ( offset === - 1 ) return;

		for ( let i = 0; i < faces.length; i ++ ) {

			if ( faces[ i ].hasVertex( n ) ) return;

		}

		neighbors.splice( offset, 1 );

	}
```
</details>


---

## Classes

### `SimplifyModifier`

<details><summary>Class Code</summary>

```ts
class SimplifyModifier {

	/**
	 * Returns a new, modified version of the given geometry by applying a simplification.
	 * Please note that the resulting geometry is always non-indexed.
	 *
	 * @param {BufferGeometry} geometry - The geometry to modify.
	 * @param {number} count - The number of vertices to remove.
	 * @return {BufferGeometry} A new, modified geometry.
	 */
	modify( geometry, count ) {

		geometry = geometry.clone();

		// currently morphAttributes are not supported
		delete geometry.morphAttributes.position;
		delete geometry.morphAttributes.normal;
		const attributes = geometry.attributes;

		// this modifier can only process indexed and non-indexed geometries with at least a position attribute

		for ( const name in attributes ) {

			if ( name !== 'position' && name !== 'uv' && name !== 'normal' && name !== 'tangent' && name !== 'color' ) geometry.deleteAttribute( name );

		}

		geometry = BufferGeometryUtils.mergeVertices( geometry );

		//
		// put data of original geometry in different data structures
		//

		const vertices = [];
		const faces = [];

		// add vertices

		const positionAttribute = geometry.getAttribute( 'position' );
		const uvAttribute = geometry.getAttribute( 'uv' );
		const normalAttribute = geometry.getAttribute( 'normal' );
		const tangentAttribute = geometry.getAttribute( 'tangent' );
		const colorAttribute = geometry.getAttribute( 'color' );

		let t = null;
		let v2 = null;
		let nor = null;
		let col = null;

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			const v = new Vector3().fromBufferAttribute( positionAttribute, i );
			if ( uvAttribute ) {

				v2 = new Vector2().fromBufferAttribute( uvAttribute, i );

			}

			if ( normalAttribute ) {

				nor = new Vector3().fromBufferAttribute( normalAttribute, i );

			}

			if ( tangentAttribute ) {

				t = new Vector4().fromBufferAttribute( tangentAttribute, i );

			}

			if ( colorAttribute ) {

				col = new Color().fromBufferAttribute( colorAttribute, i );

			}

			const vertex = new Vertex( v, v2, nor, t, col );
			vertices.push( vertex );

		}

		// add faces

		let index = geometry.getIndex();

		if ( index !== null ) {

			for ( let i = 0; i < index.count; i += 3 ) {

				const a = index.getX( i );
				const b = index.getX( i + 1 );
				const c = index.getX( i + 2 );

				const triangle = new Triangle( vertices[ a ], vertices[ b ], vertices[ c ], a, b, c );
				faces.push( triangle );

			}

		} else {

			for ( let i = 0; i < positionAttribute.count; i += 3 ) {

				const a = i;
				const b = i + 1;
				const c = i + 2;

				const triangle = new Triangle( vertices[ a ], vertices[ b ], vertices[ c ], a, b, c );
				faces.push( triangle );

			}

		}

		// compute all edge collapse costs

		for ( let i = 0, il = vertices.length; i < il; i ++ ) {

			computeEdgeCostAtVertex( vertices[ i ] );

		}

		let nextVertex;

		let z = count;

		while ( z -- ) {

			nextVertex = minimumCostEdge( vertices );

			if ( ! nextVertex ) {

				console.log( 'THREE.SimplifyModifier: No next vertex' );
				break;

			}

			collapse( vertices, faces, nextVertex, nextVertex.collapseNeighbor );

		}

		//

		const simplifiedGeometry = new BufferGeometry();
		const position = [];
		const uv = [];
		const normal = [];
		const tangent = [];
		const color = [];

		index = [];

		//

		for ( let i = 0; i < vertices.length; i ++ ) {

			const vertex = vertices[ i ];
			position.push( vertex.position.x, vertex.position.y, vertex.position.z );
			if ( vertex.uv ) {

				uv.push( vertex.uv.x, vertex.uv.y );

			}

			if ( vertex.normal ) {

				normal.push( vertex.normal.x, vertex.normal.y, vertex.normal.z );

			}

			if ( vertex.tangent ) {

				tangent.push( vertex.tangent.x, vertex.tangent.y, vertex.tangent.z, vertex.tangent.w );

			}

			if ( vertex.color ) {

				color.push( vertex.color.r, vertex.color.g, vertex.color.b );

			}


			// cache final index to GREATLY speed up faces reconstruction
			vertex.id = i;

		}

		//

		for ( let i = 0; i < faces.length; i ++ ) {

			const face = faces[ i ];
			index.push( face.v1.id, face.v2.id, face.v3.id );

		}

		simplifiedGeometry.setAttribute( 'position', new Float32BufferAttribute( position, 3 ) );
		if ( uv.length > 0 ) simplifiedGeometry.setAttribute( 'uv', new Float32BufferAttribute( uv, 2 ) );
		if ( normal.length > 0 ) simplifiedGeometry.setAttribute( 'normal', new Float32BufferAttribute( normal, 3 ) );
		if ( tangent.length > 0 ) simplifiedGeometry.setAttribute( 'tangent', new Float32BufferAttribute( tangent, 4 ) );
		if ( color.length > 0 ) simplifiedGeometry.setAttribute( 'color', new Float32BufferAttribute( color, 3 ) );

		simplifiedGeometry.setIndex( index );

		return simplifiedGeometry;

	}

}
```
</details>

#### Methods

##### `modify(geometry: BufferGeometry, count: number): BufferGeometry`

<details><summary>Code</summary>

```ts
modify( geometry, count ) {

		geometry = geometry.clone();

		// currently morphAttributes are not supported
		delete geometry.morphAttributes.position;
		delete geometry.morphAttributes.normal;
		const attributes = geometry.attributes;

		// this modifier can only process indexed and non-indexed geometries with at least a position attribute

		for ( const name in attributes ) {

			if ( name !== 'position' && name !== 'uv' && name !== 'normal' && name !== 'tangent' && name !== 'color' ) geometry.deleteAttribute( name );

		}

		geometry = BufferGeometryUtils.mergeVertices( geometry );

		//
		// put data of original geometry in different data structures
		//

		const vertices = [];
		const faces = [];

		// add vertices

		const positionAttribute = geometry.getAttribute( 'position' );
		const uvAttribute = geometry.getAttribute( 'uv' );
		const normalAttribute = geometry.getAttribute( 'normal' );
		const tangentAttribute = geometry.getAttribute( 'tangent' );
		const colorAttribute = geometry.getAttribute( 'color' );

		let t = null;
		let v2 = null;
		let nor = null;
		let col = null;

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			const v = new Vector3().fromBufferAttribute( positionAttribute, i );
			if ( uvAttribute ) {

				v2 = new Vector2().fromBufferAttribute( uvAttribute, i );

			}

			if ( normalAttribute ) {

				nor = new Vector3().fromBufferAttribute( normalAttribute, i );

			}

			if ( tangentAttribute ) {

				t = new Vector4().fromBufferAttribute( tangentAttribute, i );

			}

			if ( colorAttribute ) {

				col = new Color().fromBufferAttribute( colorAttribute, i );

			}

			const vertex = new Vertex( v, v2, nor, t, col );
			vertices.push( vertex );

		}

		// add faces

		let index = geometry.getIndex();

		if ( index !== null ) {

			for ( let i = 0; i < index.count; i += 3 ) {

				const a = index.getX( i );
				const b = index.getX( i + 1 );
				const c = index.getX( i + 2 );

				const triangle = new Triangle( vertices[ a ], vertices[ b ], vertices[ c ], a, b, c );
				faces.push( triangle );

			}

		} else {

			for ( let i = 0; i < positionAttribute.count; i += 3 ) {

				const a = i;
				const b = i + 1;
				const c = i + 2;

				const triangle = new Triangle( vertices[ a ], vertices[ b ], vertices[ c ], a, b, c );
				faces.push( triangle );

			}

		}

		// compute all edge collapse costs

		for ( let i = 0, il = vertices.length; i < il; i ++ ) {

			computeEdgeCostAtVertex( vertices[ i ] );

		}

		let nextVertex;

		let z = count;

		while ( z -- ) {

			nextVertex = minimumCostEdge( vertices );

			if ( ! nextVertex ) {

				console.log( 'THREE.SimplifyModifier: No next vertex' );
				break;

			}

			collapse( vertices, faces, nextVertex, nextVertex.collapseNeighbor );

		}

		//

		const simplifiedGeometry = new BufferGeometry();
		const position = [];
		const uv = [];
		const normal = [];
		const tangent = [];
		const color = [];

		index = [];

		//

		for ( let i = 0; i < vertices.length; i ++ ) {

			const vertex = vertices[ i ];
			position.push( vertex.position.x, vertex.position.y, vertex.position.z );
			if ( vertex.uv ) {

				uv.push( vertex.uv.x, vertex.uv.y );

			}

			if ( vertex.normal ) {

				normal.push( vertex.normal.x, vertex.normal.y, vertex.normal.z );

			}

			if ( vertex.tangent ) {

				tangent.push( vertex.tangent.x, vertex.tangent.y, vertex.tangent.z, vertex.tangent.w );

			}

			if ( vertex.color ) {

				color.push( vertex.color.r, vertex.color.g, vertex.color.b );

			}


			// cache final index to GREATLY speed up faces reconstruction
			vertex.id = i;

		}

		//

		for ( let i = 0; i < faces.length; i ++ ) {

			const face = faces[ i ];
			index.push( face.v1.id, face.v2.id, face.v3.id );

		}

		simplifiedGeometry.setAttribute( 'position', new Float32BufferAttribute( position, 3 ) );
		if ( uv.length > 0 ) simplifiedGeometry.setAttribute( 'uv', new Float32BufferAttribute( uv, 2 ) );
		if ( normal.length > 0 ) simplifiedGeometry.setAttribute( 'normal', new Float32BufferAttribute( normal, 3 ) );
		if ( tangent.length > 0 ) simplifiedGeometry.setAttribute( 'tangent', new Float32BufferAttribute( tangent, 4 ) );
		if ( color.length > 0 ) simplifiedGeometry.setAttribute( 'color', new Float32BufferAttribute( color, 3 ) );

		simplifiedGeometry.setIndex( index );

		return simplifiedGeometry;

	}
```
</details>

### `Triangle`

<details><summary>Class Code</summary>

```ts
class Triangle {

	constructor( v1, v2, v3, a, b, c ) {

		this.a = a;
		this.b = b;
		this.c = c;

		this.v1 = v1;
		this.v2 = v2;
		this.v3 = v3;

		this.normal = new Vector3();

		this.computeNormal();

		v1.faces.push( this );
		v1.addUniqueNeighbor( v2 );
		v1.addUniqueNeighbor( v3 );

		v2.faces.push( this );
		v2.addUniqueNeighbor( v1 );
		v2.addUniqueNeighbor( v3 );


		v3.faces.push( this );
		v3.addUniqueNeighbor( v1 );
		v3.addUniqueNeighbor( v2 );

	}

	computeNormal() {

		const vA = this.v1.position;
		const vB = this.v2.position;
		const vC = this.v3.position;

		_cb.subVectors( vC, vB );
		_ab.subVectors( vA, vB );
		_cb.cross( _ab ).normalize();

		this.normal.copy( _cb );

	}

	hasVertex( v ) {

		return v === this.v1 || v === this.v2 || v === this.v3;

	}

	replaceVertex( oldv, newv ) {

		if ( oldv === this.v1 ) this.v1 = newv;
		else if ( oldv === this.v2 ) this.v2 = newv;
		else if ( oldv === this.v3 ) this.v3 = newv;

		removeFromArray( oldv.faces, this );
		newv.faces.push( this );


		oldv.removeIfNonNeighbor( this.v1 );
		this.v1.removeIfNonNeighbor( oldv );

		oldv.removeIfNonNeighbor( this.v2 );
		this.v2.removeIfNonNeighbor( oldv );

		oldv.removeIfNonNeighbor( this.v3 );
		this.v3.removeIfNonNeighbor( oldv );

		this.v1.addUniqueNeighbor( this.v2 );
		this.v1.addUniqueNeighbor( this.v3 );

		this.v2.addUniqueNeighbor( this.v1 );
		this.v2.addUniqueNeighbor( this.v3 );

		this.v3.addUniqueNeighbor( this.v1 );
		this.v3.addUniqueNeighbor( this.v2 );

		this.computeNormal();

	}

}
```
</details>

#### Methods

##### `computeNormal(): void`

<details><summary>Code</summary>

```ts
computeNormal() {

		const vA = this.v1.position;
		const vB = this.v2.position;
		const vC = this.v3.position;

		_cb.subVectors( vC, vB );
		_ab.subVectors( vA, vB );
		_cb.cross( _ab ).normalize();

		this.normal.copy( _cb );

	}
```
</details>

##### `hasVertex(v: any): boolean`

<details><summary>Code</summary>

```ts
hasVertex( v ) {

		return v === this.v1 || v === this.v2 || v === this.v3;

	}
```
</details>

##### `replaceVertex(oldv: any, newv: any): void`

<details><summary>Code</summary>

```ts
replaceVertex( oldv, newv ) {

		if ( oldv === this.v1 ) this.v1 = newv;
		else if ( oldv === this.v2 ) this.v2 = newv;
		else if ( oldv === this.v3 ) this.v3 = newv;

		removeFromArray( oldv.faces, this );
		newv.faces.push( this );


		oldv.removeIfNonNeighbor( this.v1 );
		this.v1.removeIfNonNeighbor( oldv );

		oldv.removeIfNonNeighbor( this.v2 );
		this.v2.removeIfNonNeighbor( oldv );

		oldv.removeIfNonNeighbor( this.v3 );
		this.v3.removeIfNonNeighbor( oldv );

		this.v1.addUniqueNeighbor( this.v2 );
		this.v1.addUniqueNeighbor( this.v3 );

		this.v2.addUniqueNeighbor( this.v1 );
		this.v2.addUniqueNeighbor( this.v3 );

		this.v3.addUniqueNeighbor( this.v1 );
		this.v3.addUniqueNeighbor( this.v2 );

		this.computeNormal();

	}
```
</details>

### `Vertex`

<details><summary>Class Code</summary>

```ts
class Vertex {

	constructor( v, uv, normal, tangent, color ) {

		this.position = v;
		this.uv = uv;
		this.normal = normal;
		this.tangent = tangent;
		this.color = color;

		this.id = - 1; // external use position in vertices list (for e.g. face generation)

		this.faces = []; // faces vertex is connected
		this.neighbors = []; // neighbouring vertices aka "adjacentVertices"

		// these will be computed in computeEdgeCostAtVertex()
		this.collapseCost = 0; // cost of collapsing this vertex, the less the better. aka objdist
		this.collapseNeighbor = null; // best candidate for collapsing

	}

	addUniqueNeighbor( vertex ) {

		pushIfUnique( this.neighbors, vertex );

	}

	removeIfNonNeighbor( n ) {

		const neighbors = this.neighbors;
		const faces = this.faces;

		const offset = neighbors.indexOf( n );

		if ( offset === - 1 ) return;

		for ( let i = 0; i < faces.length; i ++ ) {

			if ( faces[ i ].hasVertex( n ) ) return;

		}

		neighbors.splice( offset, 1 );

	}

}
```
</details>

#### Methods

##### `addUniqueNeighbor(vertex: any): void`

<details><summary>Code</summary>

```ts
addUniqueNeighbor( vertex ) {

		pushIfUnique( this.neighbors, vertex );

	}
```
</details>

##### `removeIfNonNeighbor(n: any): void`

<details><summary>Code</summary>

```ts
removeIfNonNeighbor( n ) {

		const neighbors = this.neighbors;
		const faces = this.faces;

		const offset = neighbors.indexOf( n );

		if ( offset === - 1 ) return;

		for ( let i = 0; i < faces.length; i ++ ) {

			if ( faces[ i ].hasVertex( n ) ) return;

		}

		neighbors.splice( offset, 1 );

	}
```
</details>


---