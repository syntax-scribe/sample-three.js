[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Octree.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 43 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/math/Octree.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box3` | `three` |
| `Line3` | `three` |
| `Plane` | `three` |
| `Sphere` | `three` |
| `Triangle` | `three` |
| `Vector3` | `three` |
| `Layers` | `three` |
| `Capsule` | `../math/Capsule.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_v1` | `any` | let/var | `new Vector3()` | ✗ |
| `_v2` | `any` | let/var | `new Vector3()` | ✗ |
| `_point1` | `any` | let/var | `new Vector3()` | ✗ |
| `_point2` | `any` | let/var | `new Vector3()` | ✗ |
| `_plane` | `any` | let/var | `new Plane()` | ✗ |
| `_line1` | `any` | let/var | `new Line3()` | ✗ |
| `_line2` | `any` | let/var | `new Line3()` | ✗ |
| `_sphere` | `any` | let/var | `new Sphere()` | ✗ |
| `_capsule` | `Capsule` | let/var | `new Capsule()` | ✗ |
| `_temp1` | `any` | let/var | `new Vector3()` | ✗ |
| `_temp2` | `any` | let/var | `new Vector3()` | ✗ |
| `_temp3` | `any` | let/var | `new Vector3()` | ✗ |
| `EPS` | `1e-10` | let/var | `1e-10` | ✗ |
| `t1` | `any` | let/var | `*not shown*` | ✗ |
| `t2` | `any` | let/var | `*not shown*` | ✗ |
| `divisor` | `number` | let/var | `b * c - a * a` | ✗ |
| `d1` | `number` | let/var | `- d / c` | ✗ |
| `d2` | `number` | let/var | `( a - d ) / c` | ✗ |
| `subTrees` | `any[]` | let/var | `[]` | ✗ |
| `box` | `any` | let/var | `new Box3()` | ✗ |
| `triangle` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `number` | let/var | `subTrees[ i ].triangles.length` | ✗ |
| `subTree` | `any` | let/var | `this.subTrees[ i ]` | ✗ |
| `d1` | `number` | let/var | `_plane.distanceToPoint( capsule.start ) - capsule.radius` | ✗ |
| `d2` | `number` | let/var | `_plane.distanceToPoint( capsule.end ) - capsule.radius` | ✗ |
| `r2` | `number` | let/var | `capsule.radius * capsule.radius` | ✗ |
| `lines` | `any[][]` | let/var | `[ [ triangle.a, triangle.b ], [ triangle.b, triangle.c ], [ triangle.c, trian...` | ✗ |
| `r2` | `number` | let/var | `sphere.radius * sphere.radius - depth * depth` | ✗ |
| `lines` | `any[][]` | let/var | `[ [ triangle.a, triangle.b ], [ triangle.b, triangle.c ], [ triangle.c, trian...` | ✗ |
| `subTree` | `any` | let/var | `this.subTrees[ i ]` | ✗ |
| `subTree` | `any` | let/var | `this.subTrees[ i ]` | ✗ |
| `triangles` | `any[]` | let/var | `[]` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `hit` | `boolean` | let/var | `false` | ✗ |
| `triangles` | `any[]` | let/var | `[]` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `hit` | `boolean` | let/var | `false` | ✗ |
| `triangles` | `any[]` | let/var | `[]` | ✗ |
| `triangle` | `any` | let/var | `*not shown*` | ✗ |
| `position` | `any` | let/var | `*not shown*` | ✗ |
| `distance` | `number` | let/var | `1e100` | ✗ |
| `geometry` | `any` | let/var | `*not shown*` | ✗ |
| `isTemp` | `boolean` | let/var | `false` | ✗ |


---

## Functions

### `lineToLineClosestPoints(line1: any, line2: any, target1: any, target2: any): void`

**Parameters:**

- **`line1`** `any`
- **`line2`** `any`
- **`target1`** `any`
- **`target2`** `any`

**Returns:** `void`

**Calls:**

- `_temp1.copy( line1.end ).sub`
- `_temp2.copy( line2.end ).sub`
- `_temp3.copy( line2.start ).sub`
- `r.dot`
- `s.dot`
- `Math.abs`
- `Math.max`
- `Math.min`
- `target1.copy( r ).multiplyScalar( t1 ).add`
- `target2.copy( s ).multiplyScalar( t2 ).add`

<details><summary>Code</summary>

```typescript
function lineToLineClosestPoints( line1, line2, target1 = null, target2 = null ) {

	const r = _temp1.copy( line1.end ).sub( line1.start );
	const s = _temp2.copy( line2.end ).sub( line2.start );
	const w = _temp3.copy( line2.start ).sub( line1.start );

	const a = r.dot( s ),
		b = r.dot( r ),
		c = s.dot( s ),
		d = s.dot( w ),
		e = r.dot( w );

	let t1, t2;
	const divisor = b * c - a * a;

	if ( Math.abs( divisor ) < EPS ) {

		const d1 = - d / c;
		const d2 = ( a - d ) / c;

		if ( Math.abs( d1 - 0.5 ) < Math.abs( d2 - 0.5 ) ) {

			t1 = 0;
			t2 = d1;

		} else {

			t1 = 1;
			t2 = d2;

		}

	} else {

		t1 = ( d * a + e * c ) / divisor;
		t2 = ( t1 * a - d ) / c;

	}

	t2 = Math.max( 0, Math.min( 1, t2 ) );
	t1 = Math.max( 0, Math.min( 1, t1 ) );

	if ( target1 ) {

		target1.copy( r ).multiplyScalar( t1 ).add( line1.start );

	}

	if ( target2 ) {

		target2.copy( s ).multiplyScalar( t2 ).add( line2.start );

	}

}
```
</details>

### `Octree.addTriangle(triangle: Triangle): Octree`

**JSDoc:**
```typescript
/**
	 * Adds the given triangle to the Octree. The triangle vertices are clamped if they exceed
	 * the bounds of the Octree.
	 *
	 * @param {Triangle} triangle - The triangle to add.
	 * @return {Octree} A reference to this Octree.
	 */
```

**Parameters:**

- **`triangle`** `Triangle`

**Returns:** `Octree`

**Calls:**

- `Math.min`
- `Math.max`
- `this.triangles.push`

<details><summary>Code</summary>

```typescript
addTriangle( triangle ) {

		this.bounds.min.x = Math.min( this.bounds.min.x, triangle.a.x, triangle.b.x, triangle.c.x );
		this.bounds.min.y = Math.min( this.bounds.min.y, triangle.a.y, triangle.b.y, triangle.c.y );
		this.bounds.min.z = Math.min( this.bounds.min.z, triangle.a.z, triangle.b.z, triangle.c.z );
		this.bounds.max.x = Math.max( this.bounds.max.x, triangle.a.x, triangle.b.x, triangle.c.x );
		this.bounds.max.y = Math.max( this.bounds.max.y, triangle.a.y, triangle.b.y, triangle.c.y );
		this.bounds.max.z = Math.max( this.bounds.max.z, triangle.a.z, triangle.b.z, triangle.c.z );

		this.triangles.push( triangle );

		return this;

	}
```
</details>

### `Octree.calcBox(): Octree`

**JSDoc:**
```typescript
/**
	 * Prepares {@link Octree#box} for the build.
	 *
	 * @return {Octree} A reference to this Octree.
	 */
```

**Returns:** `Octree`

**Calls:**

- `this.bounds.clone`

**Internal Comments:**
```
// offset small amount to account for regular grid (x6)
```

<details><summary>Code</summary>

```typescript
calcBox() {

		this.box = this.bounds.clone();

		// offset small amount to account for regular grid
		this.box.min.x -= 0.01;
		this.box.min.y -= 0.01;
		this.box.min.z -= 0.01;

		return this;

	}
```
</details>

### `Octree.split(level: number): Octree`

**JSDoc:**
```typescript
/**
	 * Splits the Octree. This method is used recursively when
	 * building the Octree.
	 *
	 * @param {number} level - The current level.
	 * @return {Octree} A reference to this Octree.
	 */
```

**Parameters:**

- **`level`** `number`

**Returns:** `Octree`

**Calls:**

- `_v2.copy( this.box.max ).sub( this.box.min ).multiplyScalar`
- `_v1.set`
- `box.min.copy( this.box.min ).add`
- `v.multiply`
- `box.max.copy( box.min ).add`
- `subTrees.push`
- `this.triangles.pop`
- `subTrees[ i ].box.intersectsTriangle`
- `subTrees[ i ].triangles.push`
- `subTrees[ i ].split`
- `this.subTrees.push`

<details><summary>Code</summary>

```typescript
split( level ) {

		if ( ! this.box ) return;

		const subTrees = [];
		const halfsize = _v2.copy( this.box.max ).sub( this.box.min ).multiplyScalar( 0.5 );

		for ( let x = 0; x < 2; x ++ ) {

			for ( let y = 0; y < 2; y ++ ) {

				for ( let z = 0; z < 2; z ++ ) {

					const box = new Box3();
					const v = _v1.set( x, y, z );

					box.min.copy( this.box.min ).add( v.multiply( halfsize ) );
					box.max.copy( box.min ).add( halfsize );

					subTrees.push( new Octree( box ) );

				}

			}

		}

		let triangle;

		while ( triangle = this.triangles.pop() ) {

			for ( let i = 0; i < subTrees.length; i ++ ) {

				if ( subTrees[ i ].box.intersectsTriangle( triangle ) ) {

					subTrees[ i ].triangles.push( triangle );

				}

			}

		}

		for ( let i = 0; i < subTrees.length; i ++ ) {

			const len = subTrees[ i ].triangles.length;

			if ( len > this.trianglesPerLeaf && level < this.maxLevel ) {

				subTrees[ i ].split( level + 1 );

			}

			if ( len !== 0 ) {

				this.subTrees.push( subTrees[ i ] );

			}

		}

		return this;

	}
```
</details>

### `Octree.build(): Octree`

**JSDoc:**
```typescript
/**
	 * Builds the Octree.
	 *
	 * @return {Octree} A reference to this Octree.
	 */
```

**Returns:** `Octree`

**Calls:**

- `this.calcBox`
- `this.split`

<details><summary>Code</summary>

```typescript
build() {

		this.calcBox();
		this.split( 0 );

		return this;

	}
```
</details>

### `Octree.getRayTriangles(ray: Ray, triangles: Triangle[]): void`

**JSDoc:**
```typescript
/**
	 * Computes the triangles that potentially intersect with the given ray.
	 *
	 * @param {Ray} ray - The ray to test.
	 * @param {Array<Triangle>} triangles - The target array that holds the triangles.
	 */
```

**Parameters:**

- **`ray`** `Ray`
- **`triangles`** `Triangle[]`

**Returns:** `void`

**Calls:**

- `ray.intersectsBox`
- `triangles.indexOf`
- `triangles.push`
- `subTree.getRayTriangles`

<details><summary>Code</summary>

```typescript
getRayTriangles( ray, triangles ) {

		for ( let i = 0; i < this.subTrees.length; i ++ ) {

			const subTree = this.subTrees[ i ];
			if ( ! ray.intersectsBox( subTree.box ) ) continue;

			if ( subTree.triangles.length > 0 ) {

				for ( let j = 0; j < subTree.triangles.length; j ++ ) {

					if ( triangles.indexOf( subTree.triangles[ j ] ) === - 1 ) triangles.push( subTree.triangles[ j ] );

				}

			} else {

				subTree.getRayTriangles( ray, triangles );

			}

		}

	}
```
</details>

### `Octree.triangleCapsuleIntersect(capsule: Capsule, triangle: Triangle): any`

**JSDoc:**
```typescript
/**
	 * Computes the intersection between the given capsule and triangle.
	 *
	 * @param {Capsule} capsule - The capsule to test.
	 * @param {Triangle} triangle - The triangle to test.
	 * @return {Object|false} The intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
```

**Parameters:**

- **`capsule`** `Capsule`
- **`triangle`** `Triangle`

**Returns:** `any`

**Calls:**

- `triangle.getPlane`
- `_plane.distanceToPoint`
- `Math.abs`
- `_v1.copy( capsule.start ).lerp`
- `triangle.containsPoint`
- `_plane.normal.clone`
- `intersectPoint.clone`
- `Math.min`
- `_line1.set`
- `_line2.set`
- `lineToLineClosestPoints`
- `_point1.distanceToSquared`
- `_point1.clone().sub( _point2 ).normalize`
- `_point2.clone`
- `_point1.distanceTo`

<details><summary>Code</summary>

```typescript
triangleCapsuleIntersect( capsule, triangle ) {

		triangle.getPlane( _plane );

		const d1 = _plane.distanceToPoint( capsule.start ) - capsule.radius;
		const d2 = _plane.distanceToPoint( capsule.end ) - capsule.radius;

		if ( ( d1 > 0 && d2 > 0 ) || ( d1 < - capsule.radius && d2 < - capsule.radius ) ) {

			return false;

		}

		const delta = Math.abs( d1 / ( Math.abs( d1 ) + Math.abs( d2 ) ) );
		const intersectPoint = _v1.copy( capsule.start ).lerp( capsule.end, delta );

		if ( triangle.containsPoint( intersectPoint ) ) {

			return { normal: _plane.normal.clone(), point: intersectPoint.clone(), depth: Math.abs( Math.min( d1, d2 ) ) };

		}

		const r2 = capsule.radius * capsule.radius;

		const line1 = _line1.set( capsule.start, capsule.end );

		const lines = [
			[ triangle.a, triangle.b ],
			[ triangle.b, triangle.c ],
			[ triangle.c, triangle.a ]
		];

		for ( let i = 0; i < lines.length; i ++ ) {

			const line2 = _line2.set( lines[ i ][ 0 ], lines[ i ][ 1 ] );

			lineToLineClosestPoints( line1, line2, _point1, _point2 );

			if ( _point1.distanceToSquared( _point2 ) < r2 ) {

				return {
					normal: _point1.clone().sub( _point2 ).normalize(),
					point: _point2.clone(),
					depth: capsule.radius - _point1.distanceTo( _point2 )
				};

			}

		}

		return false;

	}
```
</details>

### `Octree.triangleSphereIntersect(sphere: Sphere, triangle: Triangle): any`

**JSDoc:**
```typescript
/**
	 * Computes the intersection between the given sphere and triangle.
	 *
	 * @param {Sphere} sphere - The sphere to test.
	 * @param {Triangle} triangle - The triangle to test.
	 * @return {Object|false} The intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`
- **`triangle`** `Triangle`

**Returns:** `any`

**Calls:**

- `triangle.getPlane`
- `sphere.intersectsPlane`
- `Math.abs`
- `_plane.distanceToSphere`
- `_plane.projectPoint`
- `triangle.containsPoint`
- `_plane.normal.clone`
- `plainPoint.clone`
- `_line1.set`
- `_line1.closestPointToPoint`
- `_v2.distanceToSquared`
- `sphere.center.clone().sub( _v2 ).normalize`
- `_v2.clone`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
triangleSphereIntersect( sphere, triangle ) {

		triangle.getPlane( _plane );

		if ( ! sphere.intersectsPlane( _plane ) ) return false;

		const depth = Math.abs( _plane.distanceToSphere( sphere ) );
		const r2 = sphere.radius * sphere.radius - depth * depth;

		const plainPoint = _plane.projectPoint( sphere.center, _v1 );

		if ( triangle.containsPoint( sphere.center ) ) {

			return { normal: _plane.normal.clone(), point: plainPoint.clone(), depth: Math.abs( _plane.distanceToSphere( sphere ) ) };

		}

		const lines = [
			[ triangle.a, triangle.b ],
			[ triangle.b, triangle.c ],
			[ triangle.c, triangle.a ]
		];

		for ( let i = 0; i < lines.length; i ++ ) {

			_line1.set( lines[ i ][ 0 ], lines[ i ][ 1 ] );
			_line1.closestPointToPoint( plainPoint, true, _v2 );

			const d = _v2.distanceToSquared( sphere.center );

			if ( d < r2 ) {

				return { normal: sphere.center.clone().sub( _v2 ).normalize(), point: _v2.clone(), depth: sphere.radius - Math.sqrt( d ) };

			}

		}

		return false;

	}
```
</details>

### `Octree.getSphereTriangles(sphere: Sphere, triangles: Triangle[]): void`

**JSDoc:**
```typescript
/**
	 * Computes the triangles that potentially intersect with the given bounding sphere.
	 *
	 * @param {Sphere} sphere - The sphere to test.
	 * @param {Array<Triangle>} triangles - The target array that holds the triangles.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`
- **`triangles`** `Triangle[]`

**Returns:** `void`

**Calls:**

- `sphere.intersectsBox`
- `triangles.indexOf`
- `triangles.push`
- `subTree.getSphereTriangles`

<details><summary>Code</summary>

```typescript
getSphereTriangles( sphere, triangles ) {

		for ( let i = 0; i < this.subTrees.length; i ++ ) {

			const subTree = this.subTrees[ i ];

			if ( ! sphere.intersectsBox( subTree.box ) ) continue;

			if ( subTree.triangles.length > 0 ) {

				for ( let j = 0; j < subTree.triangles.length; j ++ ) {

					if ( triangles.indexOf( subTree.triangles[ j ] ) === - 1 ) triangles.push( subTree.triangles[ j ] );

				}

			} else {

				subTree.getSphereTriangles( sphere, triangles );

			}

		}

	}
```
</details>

### `Octree.getCapsuleTriangles(capsule: Capsule, triangles: Triangle[]): void`

**JSDoc:**
```typescript
/**
	 * Computes the triangles that potentially intersect with the given capsule.
	 *
	 * @param {Capsule} capsule - The capsule to test.
	 * @param {Array<Triangle>} triangles - The target array that holds the triangles.
	 */
```

**Parameters:**

- **`capsule`** `Capsule`
- **`triangles`** `Triangle[]`

**Returns:** `void`

**Calls:**

- `capsule.intersectsBox`
- `triangles.indexOf`
- `triangles.push`
- `subTree.getCapsuleTriangles`

<details><summary>Code</summary>

```typescript
getCapsuleTriangles( capsule, triangles ) {

		for ( let i = 0; i < this.subTrees.length; i ++ ) {

			const subTree = this.subTrees[ i ];

			if ( ! capsule.intersectsBox( subTree.box ) ) continue;

			if ( subTree.triangles.length > 0 ) {

				for ( let j = 0; j < subTree.triangles.length; j ++ ) {

					if ( triangles.indexOf( subTree.triangles[ j ] ) === - 1 ) triangles.push( subTree.triangles[ j ] );

				}

			} else {

				subTree.getCapsuleTriangles( capsule, triangles );

			}

		}

	}
```
</details>

### `Octree.sphereIntersect(sphere: Sphere): any`

**JSDoc:**
```typescript
/**
	 * Performs a bounding sphere intersection test with this Octree.
	 *
	 * @param {Sphere} sphere - The bounding sphere to test.
	 * @return {Object|boolean} The intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`

**Returns:** `any`

**Calls:**

- `_sphere.copy`
- `this.getSphereTriangles`
- `this.triangleSphereIntersect`
- `_sphere.center.add`
- `result.normal.multiplyScalar`
- `_sphere.center.clone().sub`
- `collisionVector.length`
- `collisionVector.normalize`

<details><summary>Code</summary>

```typescript
sphereIntersect( sphere ) {

		_sphere.copy( sphere );

		const triangles = [];
		let result, hit = false;

		this.getSphereTriangles( sphere, triangles );

		for ( let i = 0; i < triangles.length; i ++ ) {

			if ( result = this.triangleSphereIntersect( _sphere, triangles[ i ] ) ) {

				hit = true;

				_sphere.center.add( result.normal.multiplyScalar( result.depth ) );

			}

		}

		if ( hit ) {

			const collisionVector = _sphere.center.clone().sub( sphere.center );
			const depth = collisionVector.length();

			return { normal: collisionVector.normalize(), depth: depth };

		}

		return false;

	}
```
</details>

### `Octree.capsuleIntersect(capsule: Capsule): any`

**JSDoc:**
```typescript
/**
	 * Performs a capsule intersection test with this Octree.
	 *
	 * @param {Capsule} capsule - The capsule to test.
	 * @return {Object|boolean} The intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
```

**Parameters:**

- **`capsule`** `Capsule`

**Returns:** `any`

**Calls:**

- `_capsule.copy`
- `this.getCapsuleTriangles`
- `this.triangleCapsuleIntersect`
- `_capsule.translate`
- `result.normal.multiplyScalar`
- `_capsule.getCenter( new Vector3() ).sub`
- `capsule.getCenter`
- `collisionVector.length`
- `collisionVector.normalize`

<details><summary>Code</summary>

```typescript
capsuleIntersect( capsule ) {

		_capsule.copy( capsule );

		const triangles = [];
		let result, hit = false;

		this.getCapsuleTriangles( _capsule, triangles );

		for ( let i = 0; i < triangles.length; i ++ ) {

			if ( result = this.triangleCapsuleIntersect( _capsule, triangles[ i ] ) ) {

				hit = true;

				_capsule.translate( result.normal.multiplyScalar( result.depth ) );

			}

		}

		if ( hit ) {

			const collisionVector = _capsule.getCenter( new Vector3() ).sub( capsule.getCenter( _v1 ) );
			const depth = collisionVector.length();

			return { normal: collisionVector.normalize(), depth: depth };

		}

		return false;

	}
```
</details>

### `Octree.rayIntersect(ray: Ray): any`

**JSDoc:**
```typescript
/**
	 * Performs a ray intersection test with this Octree.
	 *
	 * @param {Ray} ray - The ray to test.
	 * @return {Object|boolean} The nearest intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
```

**Parameters:**

- **`ray`** `Ray`

**Returns:** `any`

**Calls:**

- `this.getRayTriangles`
- `ray.intersectTriangle`
- `result.sub( ray.origin ).length`
- `result.clone().add`

<details><summary>Code</summary>

```typescript
rayIntersect( ray ) {

		const triangles = [];
		let triangle, position, distance = 1e100;

		this.getRayTriangles( ray, triangles );

		for ( let i = 0; i < triangles.length; i ++ ) {

			const result = ray.intersectTriangle( triangles[ i ].a, triangles[ i ].b, triangles[ i ].c, true, _v1 );

			if ( result ) {

				const newdistance = result.sub( ray.origin ).length();

				if ( distance > newdistance ) {

					position = result.clone().add( ray.origin );
					distance = newdistance;
					triangle = triangles[ i ];

				}

			}

		}

		return distance < 1e100 ? { distance: distance, triangle: triangle, position: position } : false;

	}
```
</details>

### `Octree.fromGraphNode(group: Object3D): Octree`

**JSDoc:**
```typescript
/**
	 * Constructs the Octree from the given 3D object.
	 *
	 * @param {Object3D} group - The scene graph node.
	 * @return {Octree} A reference to this Octree.
	 */
```

**Parameters:**

- **`group`** `Object3D`

**Returns:** `Octree`

**Calls:**

- `group.updateWorldMatrix`
- `group.traverse`
- `this.layers.test`
- `obj.geometry.toNonIndexed`
- `geometry.getAttribute`
- `new Vector3().fromBufferAttribute`
- `v1.applyMatrix4`
- `v2.applyMatrix4`
- `v3.applyMatrix4`
- `this.addTriangle`
- `geometry.dispose`
- `this.build`

<details><summary>Code</summary>

```typescript
fromGraphNode( group ) {

		group.updateWorldMatrix( true, true );

		group.traverse( ( obj ) => {

			if ( obj.isMesh === true ) {

				if ( this.layers.test( obj.layers ) ) {

					let geometry, isTemp = false;

					if ( obj.geometry.index !== null ) {

						isTemp = true;
						geometry = obj.geometry.toNonIndexed();

					} else {

						geometry = obj.geometry;

					}

					const positionAttribute = geometry.getAttribute( 'position' );

					for ( let i = 0; i < positionAttribute.count; i += 3 ) {

						const v1 = new Vector3().fromBufferAttribute( positionAttribute, i );
						const v2 = new Vector3().fromBufferAttribute( positionAttribute, i + 1 );
						const v3 = new Vector3().fromBufferAttribute( positionAttribute, i + 2 );

						v1.applyMatrix4( obj.matrixWorld );
						v2.applyMatrix4( obj.matrixWorld );
						v3.applyMatrix4( obj.matrixWorld );

						this.addTriangle( new Triangle( v1, v2, v3 ) );

					}

					if ( isTemp ) {

						geometry.dispose();

					}

				}

			}

		} );

		this.build();

		return this;

	}
```
</details>

### `Octree.clear(): Octree`

**JSDoc:**
```typescript
/**
	 * Clears the Octree by making it empty.
	 *
	 * @return {Octree} A reference to this Octree.
	 */
```

**Returns:** `Octree`

**Calls:**

- `this.bounds.makeEmpty`

<details><summary>Code</summary>

```typescript
clear() {

		this.box = null;
		this.bounds.makeEmpty();

		this.subTrees.length = 0;
		this.triangles.length = 0;

		return this;

	}
```
</details>


---

## Classes

### `Octree`

<details><summary>Class Code</summary>

```ts
class Octree {

	/**
	 * Constructs a new Octree.
	 *
	 * @param {Box3} [box] - The base box with enclose the entire Octree.
	 */
	constructor( box ) {

		/**
		 * The base box with enclose the entire Octree.
		 *
		 * @type {Box3}
		 */
		this.box = box;

		/**
		 * The bounds of the Octree. Compared to {@link Octree#box}, no
		 * margin is applied.
		 *
		 * @type {Box3}
		 */
		this.bounds = new Box3();

		/**
		 * Can by used for layers configuration for refine testing.
		 *
		 * @type {Layers}
		 */
		this.layers = new Layers();

		/**
		 * The number of triangles a leaf can store before it is split.
		 *
		 * @type {number}
		 * @default 8
		 */
		this.trianglesPerLeaf = 8;

		/**
		 * The maximum level of the Octree. It defines the maximum
		 * hierarchical depth of the data structure.
		 *
		 * @type {number}
		 * @default 16
		 */
		this.maxLevel = 16;

		// private

		this.subTrees = [];
		this.triangles = [];

	}

	/**
	 * Adds the given triangle to the Octree. The triangle vertices are clamped if they exceed
	 * the bounds of the Octree.
	 *
	 * @param {Triangle} triangle - The triangle to add.
	 * @return {Octree} A reference to this Octree.
	 */
	addTriangle( triangle ) {

		this.bounds.min.x = Math.min( this.bounds.min.x, triangle.a.x, triangle.b.x, triangle.c.x );
		this.bounds.min.y = Math.min( this.bounds.min.y, triangle.a.y, triangle.b.y, triangle.c.y );
		this.bounds.min.z = Math.min( this.bounds.min.z, triangle.a.z, triangle.b.z, triangle.c.z );
		this.bounds.max.x = Math.max( this.bounds.max.x, triangle.a.x, triangle.b.x, triangle.c.x );
		this.bounds.max.y = Math.max( this.bounds.max.y, triangle.a.y, triangle.b.y, triangle.c.y );
		this.bounds.max.z = Math.max( this.bounds.max.z, triangle.a.z, triangle.b.z, triangle.c.z );

		this.triangles.push( triangle );

		return this;

	}

	/**
	 * Prepares {@link Octree#box} for the build.
	 *
	 * @return {Octree} A reference to this Octree.
	 */
	calcBox() {

		this.box = this.bounds.clone();

		// offset small amount to account for regular grid
		this.box.min.x -= 0.01;
		this.box.min.y -= 0.01;
		this.box.min.z -= 0.01;

		return this;

	}

	/**
	 * Splits the Octree. This method is used recursively when
	 * building the Octree.
	 *
	 * @param {number} level - The current level.
	 * @return {Octree} A reference to this Octree.
	 */
	split( level ) {

		if ( ! this.box ) return;

		const subTrees = [];
		const halfsize = _v2.copy( this.box.max ).sub( this.box.min ).multiplyScalar( 0.5 );

		for ( let x = 0; x < 2; x ++ ) {

			for ( let y = 0; y < 2; y ++ ) {

				for ( let z = 0; z < 2; z ++ ) {

					const box = new Box3();
					const v = _v1.set( x, y, z );

					box.min.copy( this.box.min ).add( v.multiply( halfsize ) );
					box.max.copy( box.min ).add( halfsize );

					subTrees.push( new Octree( box ) );

				}

			}

		}

		let triangle;

		while ( triangle = this.triangles.pop() ) {

			for ( let i = 0; i < subTrees.length; i ++ ) {

				if ( subTrees[ i ].box.intersectsTriangle( triangle ) ) {

					subTrees[ i ].triangles.push( triangle );

				}

			}

		}

		for ( let i = 0; i < subTrees.length; i ++ ) {

			const len = subTrees[ i ].triangles.length;

			if ( len > this.trianglesPerLeaf && level < this.maxLevel ) {

				subTrees[ i ].split( level + 1 );

			}

			if ( len !== 0 ) {

				this.subTrees.push( subTrees[ i ] );

			}

		}

		return this;

	}

	/**
	 * Builds the Octree.
	 *
	 * @return {Octree} A reference to this Octree.
	 */
	build() {

		this.calcBox();
		this.split( 0 );

		return this;

	}

	/**
	 * Computes the triangles that potentially intersect with the given ray.
	 *
	 * @param {Ray} ray - The ray to test.
	 * @param {Array<Triangle>} triangles - The target array that holds the triangles.
	 */
	getRayTriangles( ray, triangles ) {

		for ( let i = 0; i < this.subTrees.length; i ++ ) {

			const subTree = this.subTrees[ i ];
			if ( ! ray.intersectsBox( subTree.box ) ) continue;

			if ( subTree.triangles.length > 0 ) {

				for ( let j = 0; j < subTree.triangles.length; j ++ ) {

					if ( triangles.indexOf( subTree.triangles[ j ] ) === - 1 ) triangles.push( subTree.triangles[ j ] );

				}

			} else {

				subTree.getRayTriangles( ray, triangles );

			}

		}

	}

	/**
	 * Computes the intersection between the given capsule and triangle.
	 *
	 * @param {Capsule} capsule - The capsule to test.
	 * @param {Triangle} triangle - The triangle to test.
	 * @return {Object|false} The intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
	triangleCapsuleIntersect( capsule, triangle ) {

		triangle.getPlane( _plane );

		const d1 = _plane.distanceToPoint( capsule.start ) - capsule.radius;
		const d2 = _plane.distanceToPoint( capsule.end ) - capsule.radius;

		if ( ( d1 > 0 && d2 > 0 ) || ( d1 < - capsule.radius && d2 < - capsule.radius ) ) {

			return false;

		}

		const delta = Math.abs( d1 / ( Math.abs( d1 ) + Math.abs( d2 ) ) );
		const intersectPoint = _v1.copy( capsule.start ).lerp( capsule.end, delta );

		if ( triangle.containsPoint( intersectPoint ) ) {

			return { normal: _plane.normal.clone(), point: intersectPoint.clone(), depth: Math.abs( Math.min( d1, d2 ) ) };

		}

		const r2 = capsule.radius * capsule.radius;

		const line1 = _line1.set( capsule.start, capsule.end );

		const lines = [
			[ triangle.a, triangle.b ],
			[ triangle.b, triangle.c ],
			[ triangle.c, triangle.a ]
		];

		for ( let i = 0; i < lines.length; i ++ ) {

			const line2 = _line2.set( lines[ i ][ 0 ], lines[ i ][ 1 ] );

			lineToLineClosestPoints( line1, line2, _point1, _point2 );

			if ( _point1.distanceToSquared( _point2 ) < r2 ) {

				return {
					normal: _point1.clone().sub( _point2 ).normalize(),
					point: _point2.clone(),
					depth: capsule.radius - _point1.distanceTo( _point2 )
				};

			}

		}

		return false;

	}

	/**
	 * Computes the intersection between the given sphere and triangle.
	 *
	 * @param {Sphere} sphere - The sphere to test.
	 * @param {Triangle} triangle - The triangle to test.
	 * @return {Object|false} The intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
	triangleSphereIntersect( sphere, triangle ) {

		triangle.getPlane( _plane );

		if ( ! sphere.intersectsPlane( _plane ) ) return false;

		const depth = Math.abs( _plane.distanceToSphere( sphere ) );
		const r2 = sphere.radius * sphere.radius - depth * depth;

		const plainPoint = _plane.projectPoint( sphere.center, _v1 );

		if ( triangle.containsPoint( sphere.center ) ) {

			return { normal: _plane.normal.clone(), point: plainPoint.clone(), depth: Math.abs( _plane.distanceToSphere( sphere ) ) };

		}

		const lines = [
			[ triangle.a, triangle.b ],
			[ triangle.b, triangle.c ],
			[ triangle.c, triangle.a ]
		];

		for ( let i = 0; i < lines.length; i ++ ) {

			_line1.set( lines[ i ][ 0 ], lines[ i ][ 1 ] );
			_line1.closestPointToPoint( plainPoint, true, _v2 );

			const d = _v2.distanceToSquared( sphere.center );

			if ( d < r2 ) {

				return { normal: sphere.center.clone().sub( _v2 ).normalize(), point: _v2.clone(), depth: sphere.radius - Math.sqrt( d ) };

			}

		}

		return false;

	}

	/**
	 * Computes the triangles that potentially intersect with the given bounding sphere.
	 *
	 * @param {Sphere} sphere - The sphere to test.
	 * @param {Array<Triangle>} triangles - The target array that holds the triangles.
	 */
	getSphereTriangles( sphere, triangles ) {

		for ( let i = 0; i < this.subTrees.length; i ++ ) {

			const subTree = this.subTrees[ i ];

			if ( ! sphere.intersectsBox( subTree.box ) ) continue;

			if ( subTree.triangles.length > 0 ) {

				for ( let j = 0; j < subTree.triangles.length; j ++ ) {

					if ( triangles.indexOf( subTree.triangles[ j ] ) === - 1 ) triangles.push( subTree.triangles[ j ] );

				}

			} else {

				subTree.getSphereTriangles( sphere, triangles );

			}

		}

	}

	/**
	 * Computes the triangles that potentially intersect with the given capsule.
	 *
	 * @param {Capsule} capsule - The capsule to test.
	 * @param {Array<Triangle>} triangles - The target array that holds the triangles.
	 */
	getCapsuleTriangles( capsule, triangles ) {

		for ( let i = 0; i < this.subTrees.length; i ++ ) {

			const subTree = this.subTrees[ i ];

			if ( ! capsule.intersectsBox( subTree.box ) ) continue;

			if ( subTree.triangles.length > 0 ) {

				for ( let j = 0; j < subTree.triangles.length; j ++ ) {

					if ( triangles.indexOf( subTree.triangles[ j ] ) === - 1 ) triangles.push( subTree.triangles[ j ] );

				}

			} else {

				subTree.getCapsuleTriangles( capsule, triangles );

			}

		}

	}

	/**
	 * Performs a bounding sphere intersection test with this Octree.
	 *
	 * @param {Sphere} sphere - The bounding sphere to test.
	 * @return {Object|boolean} The intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
	sphereIntersect( sphere ) {

		_sphere.copy( sphere );

		const triangles = [];
		let result, hit = false;

		this.getSphereTriangles( sphere, triangles );

		for ( let i = 0; i < triangles.length; i ++ ) {

			if ( result = this.triangleSphereIntersect( _sphere, triangles[ i ] ) ) {

				hit = true;

				_sphere.center.add( result.normal.multiplyScalar( result.depth ) );

			}

		}

		if ( hit ) {

			const collisionVector = _sphere.center.clone().sub( sphere.center );
			const depth = collisionVector.length();

			return { normal: collisionVector.normalize(), depth: depth };

		}

		return false;

	}

	/**
	 * Performs a capsule intersection test with this Octree.
	 *
	 * @param {Capsule} capsule - The capsule to test.
	 * @return {Object|boolean} The intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
	capsuleIntersect( capsule ) {

		_capsule.copy( capsule );

		const triangles = [];
		let result, hit = false;

		this.getCapsuleTriangles( _capsule, triangles );

		for ( let i = 0; i < triangles.length; i ++ ) {

			if ( result = this.triangleCapsuleIntersect( _capsule, triangles[ i ] ) ) {

				hit = true;

				_capsule.translate( result.normal.multiplyScalar( result.depth ) );

			}

		}

		if ( hit ) {

			const collisionVector = _capsule.getCenter( new Vector3() ).sub( capsule.getCenter( _v1 ) );
			const depth = collisionVector.length();

			return { normal: collisionVector.normalize(), depth: depth };

		}

		return false;

	}

	/**
	 * Performs a ray intersection test with this Octree.
	 *
	 * @param {Ray} ray - The ray to test.
	 * @return {Object|boolean} The nearest intersection object. If no intersection
	 * is detected, the method returns `false`.
	 */
	rayIntersect( ray ) {

		const triangles = [];
		let triangle, position, distance = 1e100;

		this.getRayTriangles( ray, triangles );

		for ( let i = 0; i < triangles.length; i ++ ) {

			const result = ray.intersectTriangle( triangles[ i ].a, triangles[ i ].b, triangles[ i ].c, true, _v1 );

			if ( result ) {

				const newdistance = result.sub( ray.origin ).length();

				if ( distance > newdistance ) {

					position = result.clone().add( ray.origin );
					distance = newdistance;
					triangle = triangles[ i ];

				}

			}

		}

		return distance < 1e100 ? { distance: distance, triangle: triangle, position: position } : false;

	}

	/**
	 * Constructs the Octree from the given 3D object.
	 *
	 * @param {Object3D} group - The scene graph node.
	 * @return {Octree} A reference to this Octree.
	 */
	fromGraphNode( group ) {

		group.updateWorldMatrix( true, true );

		group.traverse( ( obj ) => {

			if ( obj.isMesh === true ) {

				if ( this.layers.test( obj.layers ) ) {

					let geometry, isTemp = false;

					if ( obj.geometry.index !== null ) {

						isTemp = true;
						geometry = obj.geometry.toNonIndexed();

					} else {

						geometry = obj.geometry;

					}

					const positionAttribute = geometry.getAttribute( 'position' );

					for ( let i = 0; i < positionAttribute.count; i += 3 ) {

						const v1 = new Vector3().fromBufferAttribute( positionAttribute, i );
						const v2 = new Vector3().fromBufferAttribute( positionAttribute, i + 1 );
						const v3 = new Vector3().fromBufferAttribute( positionAttribute, i + 2 );

						v1.applyMatrix4( obj.matrixWorld );
						v2.applyMatrix4( obj.matrixWorld );
						v3.applyMatrix4( obj.matrixWorld );

						this.addTriangle( new Triangle( v1, v2, v3 ) );

					}

					if ( isTemp ) {

						geometry.dispose();

					}

				}

			}

		} );

		this.build();

		return this;

	}

	/**
	 * Clears the Octree by making it empty.
	 *
	 * @return {Octree} A reference to this Octree.
	 */
	clear() {

		this.box = null;
		this.bounds.makeEmpty();

		this.subTrees.length = 0;
		this.triangles.length = 0;

		return this;

	}

}
```
</details>

#### Methods

##### `addTriangle(triangle: Triangle): Octree`

<details><summary>Code</summary>

```ts
addTriangle( triangle ) {

		this.bounds.min.x = Math.min( this.bounds.min.x, triangle.a.x, triangle.b.x, triangle.c.x );
		this.bounds.min.y = Math.min( this.bounds.min.y, triangle.a.y, triangle.b.y, triangle.c.y );
		this.bounds.min.z = Math.min( this.bounds.min.z, triangle.a.z, triangle.b.z, triangle.c.z );
		this.bounds.max.x = Math.max( this.bounds.max.x, triangle.a.x, triangle.b.x, triangle.c.x );
		this.bounds.max.y = Math.max( this.bounds.max.y, triangle.a.y, triangle.b.y, triangle.c.y );
		this.bounds.max.z = Math.max( this.bounds.max.z, triangle.a.z, triangle.b.z, triangle.c.z );

		this.triangles.push( triangle );

		return this;

	}
```
</details>

##### `calcBox(): Octree`

<details><summary>Code</summary>

```ts
calcBox() {

		this.box = this.bounds.clone();

		// offset small amount to account for regular grid
		this.box.min.x -= 0.01;
		this.box.min.y -= 0.01;
		this.box.min.z -= 0.01;

		return this;

	}
```
</details>

##### `split(level: number): Octree`

<details><summary>Code</summary>

```ts
split( level ) {

		if ( ! this.box ) return;

		const subTrees = [];
		const halfsize = _v2.copy( this.box.max ).sub( this.box.min ).multiplyScalar( 0.5 );

		for ( let x = 0; x < 2; x ++ ) {

			for ( let y = 0; y < 2; y ++ ) {

				for ( let z = 0; z < 2; z ++ ) {

					const box = new Box3();
					const v = _v1.set( x, y, z );

					box.min.copy( this.box.min ).add( v.multiply( halfsize ) );
					box.max.copy( box.min ).add( halfsize );

					subTrees.push( new Octree( box ) );

				}

			}

		}

		let triangle;

		while ( triangle = this.triangles.pop() ) {

			for ( let i = 0; i < subTrees.length; i ++ ) {

				if ( subTrees[ i ].box.intersectsTriangle( triangle ) ) {

					subTrees[ i ].triangles.push( triangle );

				}

			}

		}

		for ( let i = 0; i < subTrees.length; i ++ ) {

			const len = subTrees[ i ].triangles.length;

			if ( len > this.trianglesPerLeaf && level < this.maxLevel ) {

				subTrees[ i ].split( level + 1 );

			}

			if ( len !== 0 ) {

				this.subTrees.push( subTrees[ i ] );

			}

		}

		return this;

	}
```
</details>

##### `build(): Octree`

<details><summary>Code</summary>

```ts
build() {

		this.calcBox();
		this.split( 0 );

		return this;

	}
```
</details>

##### `getRayTriangles(ray: Ray, triangles: Triangle[]): void`

<details><summary>Code</summary>

```ts
getRayTriangles( ray, triangles ) {

		for ( let i = 0; i < this.subTrees.length; i ++ ) {

			const subTree = this.subTrees[ i ];
			if ( ! ray.intersectsBox( subTree.box ) ) continue;

			if ( subTree.triangles.length > 0 ) {

				for ( let j = 0; j < subTree.triangles.length; j ++ ) {

					if ( triangles.indexOf( subTree.triangles[ j ] ) === - 1 ) triangles.push( subTree.triangles[ j ] );

				}

			} else {

				subTree.getRayTriangles( ray, triangles );

			}

		}

	}
```
</details>

##### `triangleCapsuleIntersect(capsule: Capsule, triangle: Triangle): any`

<details><summary>Code</summary>

```ts
triangleCapsuleIntersect( capsule, triangle ) {

		triangle.getPlane( _plane );

		const d1 = _plane.distanceToPoint( capsule.start ) - capsule.radius;
		const d2 = _plane.distanceToPoint( capsule.end ) - capsule.radius;

		if ( ( d1 > 0 && d2 > 0 ) || ( d1 < - capsule.radius && d2 < - capsule.radius ) ) {

			return false;

		}

		const delta = Math.abs( d1 / ( Math.abs( d1 ) + Math.abs( d2 ) ) );
		const intersectPoint = _v1.copy( capsule.start ).lerp( capsule.end, delta );

		if ( triangle.containsPoint( intersectPoint ) ) {

			return { normal: _plane.normal.clone(), point: intersectPoint.clone(), depth: Math.abs( Math.min( d1, d2 ) ) };

		}

		const r2 = capsule.radius * capsule.radius;

		const line1 = _line1.set( capsule.start, capsule.end );

		const lines = [
			[ triangle.a, triangle.b ],
			[ triangle.b, triangle.c ],
			[ triangle.c, triangle.a ]
		];

		for ( let i = 0; i < lines.length; i ++ ) {

			const line2 = _line2.set( lines[ i ][ 0 ], lines[ i ][ 1 ] );

			lineToLineClosestPoints( line1, line2, _point1, _point2 );

			if ( _point1.distanceToSquared( _point2 ) < r2 ) {

				return {
					normal: _point1.clone().sub( _point2 ).normalize(),
					point: _point2.clone(),
					depth: capsule.radius - _point1.distanceTo( _point2 )
				};

			}

		}

		return false;

	}
```
</details>

##### `triangleSphereIntersect(sphere: Sphere, triangle: Triangle): any`

<details><summary>Code</summary>

```ts
triangleSphereIntersect( sphere, triangle ) {

		triangle.getPlane( _plane );

		if ( ! sphere.intersectsPlane( _plane ) ) return false;

		const depth = Math.abs( _plane.distanceToSphere( sphere ) );
		const r2 = sphere.radius * sphere.radius - depth * depth;

		const plainPoint = _plane.projectPoint( sphere.center, _v1 );

		if ( triangle.containsPoint( sphere.center ) ) {

			return { normal: _plane.normal.clone(), point: plainPoint.clone(), depth: Math.abs( _plane.distanceToSphere( sphere ) ) };

		}

		const lines = [
			[ triangle.a, triangle.b ],
			[ triangle.b, triangle.c ],
			[ triangle.c, triangle.a ]
		];

		for ( let i = 0; i < lines.length; i ++ ) {

			_line1.set( lines[ i ][ 0 ], lines[ i ][ 1 ] );
			_line1.closestPointToPoint( plainPoint, true, _v2 );

			const d = _v2.distanceToSquared( sphere.center );

			if ( d < r2 ) {

				return { normal: sphere.center.clone().sub( _v2 ).normalize(), point: _v2.clone(), depth: sphere.radius - Math.sqrt( d ) };

			}

		}

		return false;

	}
```
</details>

##### `getSphereTriangles(sphere: Sphere, triangles: Triangle[]): void`

<details><summary>Code</summary>

```ts
getSphereTriangles( sphere, triangles ) {

		for ( let i = 0; i < this.subTrees.length; i ++ ) {

			const subTree = this.subTrees[ i ];

			if ( ! sphere.intersectsBox( subTree.box ) ) continue;

			if ( subTree.triangles.length > 0 ) {

				for ( let j = 0; j < subTree.triangles.length; j ++ ) {

					if ( triangles.indexOf( subTree.triangles[ j ] ) === - 1 ) triangles.push( subTree.triangles[ j ] );

				}

			} else {

				subTree.getSphereTriangles( sphere, triangles );

			}

		}

	}
```
</details>

##### `getCapsuleTriangles(capsule: Capsule, triangles: Triangle[]): void`

<details><summary>Code</summary>

```ts
getCapsuleTriangles( capsule, triangles ) {

		for ( let i = 0; i < this.subTrees.length; i ++ ) {

			const subTree = this.subTrees[ i ];

			if ( ! capsule.intersectsBox( subTree.box ) ) continue;

			if ( subTree.triangles.length > 0 ) {

				for ( let j = 0; j < subTree.triangles.length; j ++ ) {

					if ( triangles.indexOf( subTree.triangles[ j ] ) === - 1 ) triangles.push( subTree.triangles[ j ] );

				}

			} else {

				subTree.getCapsuleTriangles( capsule, triangles );

			}

		}

	}
```
</details>

##### `sphereIntersect(sphere: Sphere): any`

<details><summary>Code</summary>

```ts
sphereIntersect( sphere ) {

		_sphere.copy( sphere );

		const triangles = [];
		let result, hit = false;

		this.getSphereTriangles( sphere, triangles );

		for ( let i = 0; i < triangles.length; i ++ ) {

			if ( result = this.triangleSphereIntersect( _sphere, triangles[ i ] ) ) {

				hit = true;

				_sphere.center.add( result.normal.multiplyScalar( result.depth ) );

			}

		}

		if ( hit ) {

			const collisionVector = _sphere.center.clone().sub( sphere.center );
			const depth = collisionVector.length();

			return { normal: collisionVector.normalize(), depth: depth };

		}

		return false;

	}
```
</details>

##### `capsuleIntersect(capsule: Capsule): any`

<details><summary>Code</summary>

```ts
capsuleIntersect( capsule ) {

		_capsule.copy( capsule );

		const triangles = [];
		let result, hit = false;

		this.getCapsuleTriangles( _capsule, triangles );

		for ( let i = 0; i < triangles.length; i ++ ) {

			if ( result = this.triangleCapsuleIntersect( _capsule, triangles[ i ] ) ) {

				hit = true;

				_capsule.translate( result.normal.multiplyScalar( result.depth ) );

			}

		}

		if ( hit ) {

			const collisionVector = _capsule.getCenter( new Vector3() ).sub( capsule.getCenter( _v1 ) );
			const depth = collisionVector.length();

			return { normal: collisionVector.normalize(), depth: depth };

		}

		return false;

	}
```
</details>

##### `rayIntersect(ray: Ray): any`

<details><summary>Code</summary>

```ts
rayIntersect( ray ) {

		const triangles = [];
		let triangle, position, distance = 1e100;

		this.getRayTriangles( ray, triangles );

		for ( let i = 0; i < triangles.length; i ++ ) {

			const result = ray.intersectTriangle( triangles[ i ].a, triangles[ i ].b, triangles[ i ].c, true, _v1 );

			if ( result ) {

				const newdistance = result.sub( ray.origin ).length();

				if ( distance > newdistance ) {

					position = result.clone().add( ray.origin );
					distance = newdistance;
					triangle = triangles[ i ];

				}

			}

		}

		return distance < 1e100 ? { distance: distance, triangle: triangle, position: position } : false;

	}
```
</details>

##### `fromGraphNode(group: Object3D): Octree`

<details><summary>Code</summary>

```ts
fromGraphNode( group ) {

		group.updateWorldMatrix( true, true );

		group.traverse( ( obj ) => {

			if ( obj.isMesh === true ) {

				if ( this.layers.test( obj.layers ) ) {

					let geometry, isTemp = false;

					if ( obj.geometry.index !== null ) {

						isTemp = true;
						geometry = obj.geometry.toNonIndexed();

					} else {

						geometry = obj.geometry;

					}

					const positionAttribute = geometry.getAttribute( 'position' );

					for ( let i = 0; i < positionAttribute.count; i += 3 ) {

						const v1 = new Vector3().fromBufferAttribute( positionAttribute, i );
						const v2 = new Vector3().fromBufferAttribute( positionAttribute, i + 1 );
						const v3 = new Vector3().fromBufferAttribute( positionAttribute, i + 2 );

						v1.applyMatrix4( obj.matrixWorld );
						v2.applyMatrix4( obj.matrixWorld );
						v3.applyMatrix4( obj.matrixWorld );

						this.addTriangle( new Triangle( v1, v2, v3 ) );

					}

					if ( isTemp ) {

						geometry.dispose();

					}

				}

			}

		} );

		this.build();

		return this;

	}
```
</details>

##### `clear(): Octree`

<details><summary>Code</summary>

```ts
clear() {

		this.box = null;
		this.bounds.makeEmpty();

		this.subTrees.length = 0;
		this.triangles.length = 0;

		return this;

	}
```
</details>


---