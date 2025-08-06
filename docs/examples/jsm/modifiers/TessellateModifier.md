[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TessellateModifier.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 60 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/modifiers/TessellateModifier.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `Float32BufferAttribute` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `maxIterations` | `number` | let/var | `this.maxIterations` | ✗ |
| `maxEdgeLengthSquared` | `number` | let/var | `this.maxEdgeLength * this.maxEdgeLength` | ✗ |
| `va` | `any` | let/var | `new Vector3()` | ✗ |
| `vb` | `any` | let/var | `new Vector3()` | ✗ |
| `vc` | `any` | let/var | `new Vector3()` | ✗ |
| `vm` | `any` | let/var | `new Vector3()` | ✗ |
| `vs` | `any[]` | let/var | `[ va, vb, vc, vm ]` | ✗ |
| `na` | `any` | let/var | `new Vector3()` | ✗ |
| `nb` | `any` | let/var | `new Vector3()` | ✗ |
| `nc` | `any` | let/var | `new Vector3()` | ✗ |
| `nm` | `any` | let/var | `new Vector3()` | ✗ |
| `ns` | `any[]` | let/var | `[ na, nb, nc, nm ]` | ✗ |
| `ca` | `any` | let/var | `new Color()` | ✗ |
| `cb` | `any` | let/var | `new Color()` | ✗ |
| `cc` | `any` | let/var | `new Color()` | ✗ |
| `cm` | `any` | let/var | `new Color()` | ✗ |
| `cs` | `any[]` | let/var | `[ ca, cb, cc, cm ]` | ✗ |
| `ua` | `any` | let/var | `new Vector2()` | ✗ |
| `ub` | `any` | let/var | `new Vector2()` | ✗ |
| `uc` | `any` | let/var | `new Vector2()` | ✗ |
| `um` | `any` | let/var | `new Vector2()` | ✗ |
| `us` | `any[]` | let/var | `[ ua, ub, uc, um ]` | ✗ |
| `u2a` | `any` | let/var | `new Vector2()` | ✗ |
| `u2b` | `any` | let/var | `new Vector2()` | ✗ |
| `u2c` | `any` | let/var | `new Vector2()` | ✗ |
| `u2m` | `any` | let/var | `new Vector2()` | ✗ |
| `u2s` | `any[]` | let/var | `[ u2a, u2b, u2c, u2m ]` | ✗ |
| `attributes` | `any` | let/var | `geometry.attributes` | ✗ |
| `hasNormals` | `boolean` | let/var | `attributes.normal !== undefined` | ✗ |
| `hasColors` | `boolean` | let/var | `attributes.color !== undefined` | ✗ |
| `hasUVs` | `boolean` | let/var | `attributes.uv !== undefined` | ✗ |
| `hasUV1s` | `boolean` | let/var | `attributes.uv1 !== undefined` | ✗ |
| `positions` | `any` | let/var | `attributes.position.array` | ✗ |
| `normals` | `any` | let/var | `hasNormals ? attributes.normal.array : null` | ✗ |
| `colors` | `any` | let/var | `hasColors ? attributes.color.array : null` | ✗ |
| `uvs` | `any` | let/var | `hasUVs ? attributes.uv.array : null` | ✗ |
| `uv1s` | `any` | let/var | `hasUV1s ? attributes.uv1.array : null` | ✗ |
| `positions2` | `any` | let/var | `positions` | ✗ |
| `normals2` | `any` | let/var | `normals` | ✗ |
| `colors2` | `any` | let/var | `colors` | ✗ |
| `uvs2` | `any` | let/var | `uvs` | ✗ |
| `uv1s2` | `any` | let/var | `uv1s` | ✗ |
| `iteration` | `number` | let/var | `0` | ✗ |
| `tessellating` | `boolean` | let/var | `true` | ✗ |
| `v1` | `any` | let/var | `vs[ a ]` | ✗ |
| `v2` | `any` | let/var | `vs[ b ]` | ✗ |
| `v3` | `any` | let/var | `vs[ c ]` | ✗ |
| `n1` | `any` | let/var | `ns[ a ]` | ✗ |
| `n2` | `any` | let/var | `ns[ b ]` | ✗ |
| `n3` | `any` | let/var | `ns[ c ]` | ✗ |
| `c1` | `any` | let/var | `cs[ a ]` | ✗ |
| `c2` | `any` | let/var | `cs[ b ]` | ✗ |
| `c3` | `any` | let/var | `cs[ c ]` | ✗ |
| `u1` | `any` | let/var | `us[ a ]` | ✗ |
| `u2` | `any` | let/var | `us[ b ]` | ✗ |
| `u3` | `any` | let/var | `us[ c ]` | ✗ |
| `u21` | `any` | let/var | `u2s[ a ]` | ✗ |
| `u22` | `any` | let/var | `u2s[ b ]` | ✗ |
| `u23` | `any` | let/var | `u2s[ c ]` | ✗ |
| `geometry2` | `any` | let/var | `new BufferGeometry()` | ✗ |


---

## Functions

### `TessellateModifier.modify(geometry: BufferGeometry): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Returns a new, modified version of the given geometry by applying a tesselation.
	 * Please note that the resulting geometry is always non-indexed.
	 *
	 * @param {BufferGeometry} geometry - The geometry to modify.
	 * @return {BufferGeometry} A new, modified geometry.
	 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`

**Returns:** `BufferGeometry`

**Calls:**

- `geometry.toNonIndexed`
- `positions2.push`
- `normals2.push`
- `colors2.push`
- `uvs2.push`
- `uv1s2.push`
- `va.fromArray`
- `vb.fromArray`
- `vc.fromArray`
- `na.fromArray`
- `nb.fromArray`
- `nc.fromArray`
- `ca.fromArray`
- `cb.fromArray`
- `cc.fromArray`
- `ua.fromArray`
- `ub.fromArray`
- `uc.fromArray`
- `u2a.fromArray`
- `u2b.fromArray`
- `u2c.fromArray`
- `va.distanceToSquared`
- `vb.distanceToSquared`
- `vm.lerpVectors`
- `nm.lerpVectors`
- `cm.lerpColors`
- `um.lerpVectors`
- `u2m.lerpVectors`
- `addTriangle`
- `geometry2.setAttribute`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
modify( geometry ) {

		if ( geometry.index !== null ) {

			geometry = geometry.toNonIndexed();

		}

		//

		const maxIterations = this.maxIterations;
		const maxEdgeLengthSquared = this.maxEdgeLength * this.maxEdgeLength;

		const va = new Vector3();
		const vb = new Vector3();
		const vc = new Vector3();
		const vm = new Vector3();
		const vs = [ va, vb, vc, vm ];

		const na = new Vector3();
		const nb = new Vector3();
		const nc = new Vector3();
		const nm = new Vector3();
		const ns = [ na, nb, nc, nm ];

		const ca = new Color();
		const cb = new Color();
		const cc = new Color();
		const cm = new Color();
		const cs = [ ca, cb, cc, cm ];

		const ua = new Vector2();
		const ub = new Vector2();
		const uc = new Vector2();
		const um = new Vector2();
		const us = [ ua, ub, uc, um ];

		const u2a = new Vector2();
		const u2b = new Vector2();
		const u2c = new Vector2();
		const u2m = new Vector2();
		const u2s = [ u2a, u2b, u2c, u2m ];

		const attributes = geometry.attributes;
		const hasNormals = attributes.normal !== undefined;
		const hasColors = attributes.color !== undefined;
		const hasUVs = attributes.uv !== undefined;
		const hasUV1s = attributes.uv1 !== undefined;

		let positions = attributes.position.array;
		let normals = hasNormals ? attributes.normal.array : null;
		let colors = hasColors ? attributes.color.array : null;
		let uvs = hasUVs ? attributes.uv.array : null;
		let uv1s = hasUV1s ? attributes.uv1.array : null;

		let positions2 = positions;
		let normals2 = normals;
		let colors2 = colors;
		let uvs2 = uvs;
		let uv1s2 = uv1s;

		let iteration = 0;
		let tessellating = true;

		function addTriangle( a, b, c ) {

			const v1 = vs[ a ];
			const v2 = vs[ b ];
			const v3 = vs[ c ];

			positions2.push( v1.x, v1.y, v1.z );
			positions2.push( v2.x, v2.y, v2.z );
			positions2.push( v3.x, v3.y, v3.z );

			if ( hasNormals ) {

				const n1 = ns[ a ];
				const n2 = ns[ b ];
				const n3 = ns[ c ];

				normals2.push( n1.x, n1.y, n1.z );
				normals2.push( n2.x, n2.y, n2.z );
				normals2.push( n3.x, n3.y, n3.z );

			}

			if ( hasColors ) {

				const c1 = cs[ a ];
				const c2 = cs[ b ];
				const c3 = cs[ c ];

				colors2.push( c1.r, c1.g, c1.b );
				colors2.push( c2.r, c2.g, c2.b );
				colors2.push( c3.r, c3.g, c3.b );

			}

			if ( hasUVs ) {

				const u1 = us[ a ];
				const u2 = us[ b ];
				const u3 = us[ c ];

				uvs2.push( u1.x, u1.y );
				uvs2.push( u2.x, u2.y );
				uvs2.push( u3.x, u3.y );

			}

			if ( hasUV1s ) {

				const u21 = u2s[ a ];
				const u22 = u2s[ b ];
				const u23 = u2s[ c ];

				uv1s2.push( u21.x, u21.y );
				uv1s2.push( u22.x, u22.y );
				uv1s2.push( u23.x, u23.y );

			}

		}

		while ( tessellating && iteration < maxIterations ) {

			iteration ++;
			tessellating = false;

			positions = positions2;
			positions2 = [];

			if ( hasNormals ) {

				normals = normals2;
				normals2 = [];

			}

			if ( hasColors ) {

				colors = colors2;
				colors2 = [];

			}

			if ( hasUVs ) {

				uvs = uvs2;
				uvs2 = [];

			}

			if ( hasUV1s ) {

				uv1s = uv1s2;
				uv1s2 = [];

			}

			for ( let i = 0, i2 = 0, il = positions.length; i < il; i += 9, i2 += 6 ) {

				va.fromArray( positions, i + 0 );
				vb.fromArray( positions, i + 3 );
				vc.fromArray( positions, i + 6 );

				if ( hasNormals ) {

					na.fromArray( normals, i + 0 );
					nb.fromArray( normals, i + 3 );
					nc.fromArray( normals, i + 6 );

				}

				if ( hasColors ) {

					ca.fromArray( colors, i + 0 );
					cb.fromArray( colors, i + 3 );
					cc.fromArray( colors, i + 6 );

				}

				if ( hasUVs ) {

					ua.fromArray( uvs, i2 + 0 );
					ub.fromArray( uvs, i2 + 2 );
					uc.fromArray( uvs, i2 + 4 );

				}

				if ( hasUV1s ) {

					u2a.fromArray( uv1s, i2 + 0 );
					u2b.fromArray( uv1s, i2 + 2 );
					u2c.fromArray( uv1s, i2 + 4 );

				}

				const dab = va.distanceToSquared( vb );
				const dbc = vb.distanceToSquared( vc );
				const dac = va.distanceToSquared( vc );

				if ( dab > maxEdgeLengthSquared || dbc > maxEdgeLengthSquared || dac > maxEdgeLengthSquared ) {

					tessellating = true;

					if ( dab >= dbc && dab >= dac ) {

						vm.lerpVectors( va, vb, 0.5 );
						if ( hasNormals ) nm.lerpVectors( na, nb, 0.5 );
						if ( hasColors ) cm.lerpColors( ca, cb, 0.5 );
						if ( hasUVs ) um.lerpVectors( ua, ub, 0.5 );
						if ( hasUV1s ) u2m.lerpVectors( u2a, u2b, 0.5 );

						addTriangle( 0, 3, 2 );
						addTriangle( 3, 1, 2 );

					} else if ( dbc >= dab && dbc >= dac ) {

						vm.lerpVectors( vb, vc, 0.5 );
						if ( hasNormals ) nm.lerpVectors( nb, nc, 0.5 );
						if ( hasColors ) cm.lerpColors( cb, cc, 0.5 );
						if ( hasUVs ) um.lerpVectors( ub, uc, 0.5 );
						if ( hasUV1s ) u2m.lerpVectors( u2b, u2c, 0.5 );

						addTriangle( 0, 1, 3 );
						addTriangle( 3, 2, 0 );

					} else {

						vm.lerpVectors( va, vc, 0.5 );
						if ( hasNormals ) nm.lerpVectors( na, nc, 0.5 );
						if ( hasColors ) cm.lerpColors( ca, cc, 0.5 );
						if ( hasUVs ) um.lerpVectors( ua, uc, 0.5 );
						if ( hasUV1s ) u2m.lerpVectors( u2a, u2c, 0.5 );

						addTriangle( 0, 1, 3 );
						addTriangle( 3, 1, 2 );

					}

				} else {

					addTriangle( 0, 1, 2 );

				}

			}

		}

		const geometry2 = new BufferGeometry();

		geometry2.setAttribute( 'position', new Float32BufferAttribute( positions2, 3 ) );

		if ( hasNormals ) {

			geometry2.setAttribute( 'normal', new Float32BufferAttribute( normals2, 3 ) );

		}

		if ( hasColors ) {

			geometry2.setAttribute( 'color', new Float32BufferAttribute( colors2, 3 ) );

		}

		if ( hasUVs ) {

			geometry2.setAttribute( 'uv', new Float32BufferAttribute( uvs2, 2 ) );

		}

		if ( hasUV1s ) {

			geometry2.setAttribute( 'uv1', new Float32BufferAttribute( uv1s2, 2 ) );

		}

		return geometry2;

	}
```
</details>

### `addTriangle(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `positions2.push`
- `normals2.push`
- `colors2.push`
- `uvs2.push`
- `uv1s2.push`

<details><summary>Code</summary>

```typescript
function addTriangle( a, b, c ) {

			const v1 = vs[ a ];
			const v2 = vs[ b ];
			const v3 = vs[ c ];

			positions2.push( v1.x, v1.y, v1.z );
			positions2.push( v2.x, v2.y, v2.z );
			positions2.push( v3.x, v3.y, v3.z );

			if ( hasNormals ) {

				const n1 = ns[ a ];
				const n2 = ns[ b ];
				const n3 = ns[ c ];

				normals2.push( n1.x, n1.y, n1.z );
				normals2.push( n2.x, n2.y, n2.z );
				normals2.push( n3.x, n3.y, n3.z );

			}

			if ( hasColors ) {

				const c1 = cs[ a ];
				const c2 = cs[ b ];
				const c3 = cs[ c ];

				colors2.push( c1.r, c1.g, c1.b );
				colors2.push( c2.r, c2.g, c2.b );
				colors2.push( c3.r, c3.g, c3.b );

			}

			if ( hasUVs ) {

				const u1 = us[ a ];
				const u2 = us[ b ];
				const u3 = us[ c ];

				uvs2.push( u1.x, u1.y );
				uvs2.push( u2.x, u2.y );
				uvs2.push( u3.x, u3.y );

			}

			if ( hasUV1s ) {

				const u21 = u2s[ a ];
				const u22 = u2s[ b ];
				const u23 = u2s[ c ];

				uv1s2.push( u21.x, u21.y );
				uv1s2.push( u22.x, u22.y );
				uv1s2.push( u23.x, u23.y );

			}

		}
```
</details>


---

## Classes

### `TessellateModifier`

<details><summary>Class Code</summary>

```ts
class TessellateModifier {

	/**
	 * Constructs a new Tessellate modifier.
	 *
	 * @param {number} [maxEdgeLength=0.1] - The maximum edge length.
	 * @param {number} [maxIterations=6] - The number of iterations.
	 */
	constructor( maxEdgeLength = 0.1, maxIterations = 6 ) {

		/**
		 * The maximum edge length.
		 *
		 * @type {number}
		 * @default 0.1
		 */
		this.maxEdgeLength = maxEdgeLength;

		/**
		 * The maximum edge length.
		 *
		 * @type {number}
		 * @default 0.1
		 */
		this.maxIterations = maxIterations;

	}

	/**
	 * Returns a new, modified version of the given geometry by applying a tesselation.
	 * Please note that the resulting geometry is always non-indexed.
	 *
	 * @param {BufferGeometry} geometry - The geometry to modify.
	 * @return {BufferGeometry} A new, modified geometry.
	 */
	modify( geometry ) {

		if ( geometry.index !== null ) {

			geometry = geometry.toNonIndexed();

		}

		//

		const maxIterations = this.maxIterations;
		const maxEdgeLengthSquared = this.maxEdgeLength * this.maxEdgeLength;

		const va = new Vector3();
		const vb = new Vector3();
		const vc = new Vector3();
		const vm = new Vector3();
		const vs = [ va, vb, vc, vm ];

		const na = new Vector3();
		const nb = new Vector3();
		const nc = new Vector3();
		const nm = new Vector3();
		const ns = [ na, nb, nc, nm ];

		const ca = new Color();
		const cb = new Color();
		const cc = new Color();
		const cm = new Color();
		const cs = [ ca, cb, cc, cm ];

		const ua = new Vector2();
		const ub = new Vector2();
		const uc = new Vector2();
		const um = new Vector2();
		const us = [ ua, ub, uc, um ];

		const u2a = new Vector2();
		const u2b = new Vector2();
		const u2c = new Vector2();
		const u2m = new Vector2();
		const u2s = [ u2a, u2b, u2c, u2m ];

		const attributes = geometry.attributes;
		const hasNormals = attributes.normal !== undefined;
		const hasColors = attributes.color !== undefined;
		const hasUVs = attributes.uv !== undefined;
		const hasUV1s = attributes.uv1 !== undefined;

		let positions = attributes.position.array;
		let normals = hasNormals ? attributes.normal.array : null;
		let colors = hasColors ? attributes.color.array : null;
		let uvs = hasUVs ? attributes.uv.array : null;
		let uv1s = hasUV1s ? attributes.uv1.array : null;

		let positions2 = positions;
		let normals2 = normals;
		let colors2 = colors;
		let uvs2 = uvs;
		let uv1s2 = uv1s;

		let iteration = 0;
		let tessellating = true;

		function addTriangle( a, b, c ) {

			const v1 = vs[ a ];
			const v2 = vs[ b ];
			const v3 = vs[ c ];

			positions2.push( v1.x, v1.y, v1.z );
			positions2.push( v2.x, v2.y, v2.z );
			positions2.push( v3.x, v3.y, v3.z );

			if ( hasNormals ) {

				const n1 = ns[ a ];
				const n2 = ns[ b ];
				const n3 = ns[ c ];

				normals2.push( n1.x, n1.y, n1.z );
				normals2.push( n2.x, n2.y, n2.z );
				normals2.push( n3.x, n3.y, n3.z );

			}

			if ( hasColors ) {

				const c1 = cs[ a ];
				const c2 = cs[ b ];
				const c3 = cs[ c ];

				colors2.push( c1.r, c1.g, c1.b );
				colors2.push( c2.r, c2.g, c2.b );
				colors2.push( c3.r, c3.g, c3.b );

			}

			if ( hasUVs ) {

				const u1 = us[ a ];
				const u2 = us[ b ];
				const u3 = us[ c ];

				uvs2.push( u1.x, u1.y );
				uvs2.push( u2.x, u2.y );
				uvs2.push( u3.x, u3.y );

			}

			if ( hasUV1s ) {

				const u21 = u2s[ a ];
				const u22 = u2s[ b ];
				const u23 = u2s[ c ];

				uv1s2.push( u21.x, u21.y );
				uv1s2.push( u22.x, u22.y );
				uv1s2.push( u23.x, u23.y );

			}

		}

		while ( tessellating && iteration < maxIterations ) {

			iteration ++;
			tessellating = false;

			positions = positions2;
			positions2 = [];

			if ( hasNormals ) {

				normals = normals2;
				normals2 = [];

			}

			if ( hasColors ) {

				colors = colors2;
				colors2 = [];

			}

			if ( hasUVs ) {

				uvs = uvs2;
				uvs2 = [];

			}

			if ( hasUV1s ) {

				uv1s = uv1s2;
				uv1s2 = [];

			}

			for ( let i = 0, i2 = 0, il = positions.length; i < il; i += 9, i2 += 6 ) {

				va.fromArray( positions, i + 0 );
				vb.fromArray( positions, i + 3 );
				vc.fromArray( positions, i + 6 );

				if ( hasNormals ) {

					na.fromArray( normals, i + 0 );
					nb.fromArray( normals, i + 3 );
					nc.fromArray( normals, i + 6 );

				}

				if ( hasColors ) {

					ca.fromArray( colors, i + 0 );
					cb.fromArray( colors, i + 3 );
					cc.fromArray( colors, i + 6 );

				}

				if ( hasUVs ) {

					ua.fromArray( uvs, i2 + 0 );
					ub.fromArray( uvs, i2 + 2 );
					uc.fromArray( uvs, i2 + 4 );

				}

				if ( hasUV1s ) {

					u2a.fromArray( uv1s, i2 + 0 );
					u2b.fromArray( uv1s, i2 + 2 );
					u2c.fromArray( uv1s, i2 + 4 );

				}

				const dab = va.distanceToSquared( vb );
				const dbc = vb.distanceToSquared( vc );
				const dac = va.distanceToSquared( vc );

				if ( dab > maxEdgeLengthSquared || dbc > maxEdgeLengthSquared || dac > maxEdgeLengthSquared ) {

					tessellating = true;

					if ( dab >= dbc && dab >= dac ) {

						vm.lerpVectors( va, vb, 0.5 );
						if ( hasNormals ) nm.lerpVectors( na, nb, 0.5 );
						if ( hasColors ) cm.lerpColors( ca, cb, 0.5 );
						if ( hasUVs ) um.lerpVectors( ua, ub, 0.5 );
						if ( hasUV1s ) u2m.lerpVectors( u2a, u2b, 0.5 );

						addTriangle( 0, 3, 2 );
						addTriangle( 3, 1, 2 );

					} else if ( dbc >= dab && dbc >= dac ) {

						vm.lerpVectors( vb, vc, 0.5 );
						if ( hasNormals ) nm.lerpVectors( nb, nc, 0.5 );
						if ( hasColors ) cm.lerpColors( cb, cc, 0.5 );
						if ( hasUVs ) um.lerpVectors( ub, uc, 0.5 );
						if ( hasUV1s ) u2m.lerpVectors( u2b, u2c, 0.5 );

						addTriangle( 0, 1, 3 );
						addTriangle( 3, 2, 0 );

					} else {

						vm.lerpVectors( va, vc, 0.5 );
						if ( hasNormals ) nm.lerpVectors( na, nc, 0.5 );
						if ( hasColors ) cm.lerpColors( ca, cc, 0.5 );
						if ( hasUVs ) um.lerpVectors( ua, uc, 0.5 );
						if ( hasUV1s ) u2m.lerpVectors( u2a, u2c, 0.5 );

						addTriangle( 0, 1, 3 );
						addTriangle( 3, 1, 2 );

					}

				} else {

					addTriangle( 0, 1, 2 );

				}

			}

		}

		const geometry2 = new BufferGeometry();

		geometry2.setAttribute( 'position', new Float32BufferAttribute( positions2, 3 ) );

		if ( hasNormals ) {

			geometry2.setAttribute( 'normal', new Float32BufferAttribute( normals2, 3 ) );

		}

		if ( hasColors ) {

			geometry2.setAttribute( 'color', new Float32BufferAttribute( colors2, 3 ) );

		}

		if ( hasUVs ) {

			geometry2.setAttribute( 'uv', new Float32BufferAttribute( uvs2, 2 ) );

		}

		if ( hasUV1s ) {

			geometry2.setAttribute( 'uv1', new Float32BufferAttribute( uv1s2, 2 ) );

		}

		return geometry2;

	}

}
```
</details>

#### Methods

##### `modify(geometry: BufferGeometry): BufferGeometry`

<details><summary>Code</summary>

```ts
modify( geometry ) {

		if ( geometry.index !== null ) {

			geometry = geometry.toNonIndexed();

		}

		//

		const maxIterations = this.maxIterations;
		const maxEdgeLengthSquared = this.maxEdgeLength * this.maxEdgeLength;

		const va = new Vector3();
		const vb = new Vector3();
		const vc = new Vector3();
		const vm = new Vector3();
		const vs = [ va, vb, vc, vm ];

		const na = new Vector3();
		const nb = new Vector3();
		const nc = new Vector3();
		const nm = new Vector3();
		const ns = [ na, nb, nc, nm ];

		const ca = new Color();
		const cb = new Color();
		const cc = new Color();
		const cm = new Color();
		const cs = [ ca, cb, cc, cm ];

		const ua = new Vector2();
		const ub = new Vector2();
		const uc = new Vector2();
		const um = new Vector2();
		const us = [ ua, ub, uc, um ];

		const u2a = new Vector2();
		const u2b = new Vector2();
		const u2c = new Vector2();
		const u2m = new Vector2();
		const u2s = [ u2a, u2b, u2c, u2m ];

		const attributes = geometry.attributes;
		const hasNormals = attributes.normal !== undefined;
		const hasColors = attributes.color !== undefined;
		const hasUVs = attributes.uv !== undefined;
		const hasUV1s = attributes.uv1 !== undefined;

		let positions = attributes.position.array;
		let normals = hasNormals ? attributes.normal.array : null;
		let colors = hasColors ? attributes.color.array : null;
		let uvs = hasUVs ? attributes.uv.array : null;
		let uv1s = hasUV1s ? attributes.uv1.array : null;

		let positions2 = positions;
		let normals2 = normals;
		let colors2 = colors;
		let uvs2 = uvs;
		let uv1s2 = uv1s;

		let iteration = 0;
		let tessellating = true;

		function addTriangle( a, b, c ) {

			const v1 = vs[ a ];
			const v2 = vs[ b ];
			const v3 = vs[ c ];

			positions2.push( v1.x, v1.y, v1.z );
			positions2.push( v2.x, v2.y, v2.z );
			positions2.push( v3.x, v3.y, v3.z );

			if ( hasNormals ) {

				const n1 = ns[ a ];
				const n2 = ns[ b ];
				const n3 = ns[ c ];

				normals2.push( n1.x, n1.y, n1.z );
				normals2.push( n2.x, n2.y, n2.z );
				normals2.push( n3.x, n3.y, n3.z );

			}

			if ( hasColors ) {

				const c1 = cs[ a ];
				const c2 = cs[ b ];
				const c3 = cs[ c ];

				colors2.push( c1.r, c1.g, c1.b );
				colors2.push( c2.r, c2.g, c2.b );
				colors2.push( c3.r, c3.g, c3.b );

			}

			if ( hasUVs ) {

				const u1 = us[ a ];
				const u2 = us[ b ];
				const u3 = us[ c ];

				uvs2.push( u1.x, u1.y );
				uvs2.push( u2.x, u2.y );
				uvs2.push( u3.x, u3.y );

			}

			if ( hasUV1s ) {

				const u21 = u2s[ a ];
				const u22 = u2s[ b ];
				const u23 = u2s[ c ];

				uv1s2.push( u21.x, u21.y );
				uv1s2.push( u22.x, u22.y );
				uv1s2.push( u23.x, u23.y );

			}

		}

		while ( tessellating && iteration < maxIterations ) {

			iteration ++;
			tessellating = false;

			positions = positions2;
			positions2 = [];

			if ( hasNormals ) {

				normals = normals2;
				normals2 = [];

			}

			if ( hasColors ) {

				colors = colors2;
				colors2 = [];

			}

			if ( hasUVs ) {

				uvs = uvs2;
				uvs2 = [];

			}

			if ( hasUV1s ) {

				uv1s = uv1s2;
				uv1s2 = [];

			}

			for ( let i = 0, i2 = 0, il = positions.length; i < il; i += 9, i2 += 6 ) {

				va.fromArray( positions, i + 0 );
				vb.fromArray( positions, i + 3 );
				vc.fromArray( positions, i + 6 );

				if ( hasNormals ) {

					na.fromArray( normals, i + 0 );
					nb.fromArray( normals, i + 3 );
					nc.fromArray( normals, i + 6 );

				}

				if ( hasColors ) {

					ca.fromArray( colors, i + 0 );
					cb.fromArray( colors, i + 3 );
					cc.fromArray( colors, i + 6 );

				}

				if ( hasUVs ) {

					ua.fromArray( uvs, i2 + 0 );
					ub.fromArray( uvs, i2 + 2 );
					uc.fromArray( uvs, i2 + 4 );

				}

				if ( hasUV1s ) {

					u2a.fromArray( uv1s, i2 + 0 );
					u2b.fromArray( uv1s, i2 + 2 );
					u2c.fromArray( uv1s, i2 + 4 );

				}

				const dab = va.distanceToSquared( vb );
				const dbc = vb.distanceToSquared( vc );
				const dac = va.distanceToSquared( vc );

				if ( dab > maxEdgeLengthSquared || dbc > maxEdgeLengthSquared || dac > maxEdgeLengthSquared ) {

					tessellating = true;

					if ( dab >= dbc && dab >= dac ) {

						vm.lerpVectors( va, vb, 0.5 );
						if ( hasNormals ) nm.lerpVectors( na, nb, 0.5 );
						if ( hasColors ) cm.lerpColors( ca, cb, 0.5 );
						if ( hasUVs ) um.lerpVectors( ua, ub, 0.5 );
						if ( hasUV1s ) u2m.lerpVectors( u2a, u2b, 0.5 );

						addTriangle( 0, 3, 2 );
						addTriangle( 3, 1, 2 );

					} else if ( dbc >= dab && dbc >= dac ) {

						vm.lerpVectors( vb, vc, 0.5 );
						if ( hasNormals ) nm.lerpVectors( nb, nc, 0.5 );
						if ( hasColors ) cm.lerpColors( cb, cc, 0.5 );
						if ( hasUVs ) um.lerpVectors( ub, uc, 0.5 );
						if ( hasUV1s ) u2m.lerpVectors( u2b, u2c, 0.5 );

						addTriangle( 0, 1, 3 );
						addTriangle( 3, 2, 0 );

					} else {

						vm.lerpVectors( va, vc, 0.5 );
						if ( hasNormals ) nm.lerpVectors( na, nc, 0.5 );
						if ( hasColors ) cm.lerpColors( ca, cc, 0.5 );
						if ( hasUVs ) um.lerpVectors( ua, uc, 0.5 );
						if ( hasUV1s ) u2m.lerpVectors( u2a, u2c, 0.5 );

						addTriangle( 0, 1, 3 );
						addTriangle( 3, 1, 2 );

					}

				} else {

					addTriangle( 0, 1, 2 );

				}

			}

		}

		const geometry2 = new BufferGeometry();

		geometry2.setAttribute( 'position', new Float32BufferAttribute( positions2, 3 ) );

		if ( hasNormals ) {

			geometry2.setAttribute( 'normal', new Float32BufferAttribute( normals2, 3 ) );

		}

		if ( hasColors ) {

			geometry2.setAttribute( 'color', new Float32BufferAttribute( colors2, 3 ) );

		}

		if ( hasUVs ) {

			geometry2.setAttribute( 'uv', new Float32BufferAttribute( uvs2, 2 ) );

		}

		if ( hasUV1s ) {

			geometry2.setAttribute( 'uv1', new Float32BufferAttribute( uv1s2, 2 ) );

		}

		return geometry2;

	}
```
</details>


---