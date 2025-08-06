[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MarchingCubes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 129 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/MarchingCubes.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `DynamicDrawUsage` | `three` |
| `Mesh` | `three` |
| `Sphere` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `vlist` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 12 * 3 )` | ✗ |
| `nlist` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 12 * 3 )` | ✗ |
| `clist` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 12 * 3 )` | ✗ |
| `maxVertexCount` | `number` | let/var | `maxPolyCount * 3` | ✗ |
| `positionAttribute` | `any` | let/var | `new BufferAttribute( this.positionArray, 3 )` | ✗ |
| `normalAttribute` | `any` | let/var | `new BufferAttribute( this.normalArray, 3 )` | ✗ |
| `uvAttribute` | `any` | let/var | `new BufferAttribute( this.uvArray, 2 )` | ✗ |
| `colorAttribute` | `any` | let/var | `new BufferAttribute( this.colorArray, 3 )` | ✗ |
| `mu` | `number` | let/var | `( isol - valp1 ) / ( valp2 - valp1 )` | ✗ |
| `nc` | `any` | let/var | `scope.normal_cache` | ✗ |
| `mu` | `number` | let/var | `( isol - valp1 ) / ( valp2 - valp1 )` | ✗ |
| `nc` | `any` | let/var | `scope.normal_cache` | ✗ |
| `q2` | `any` | let/var | `q + scope.yd * 3` | ✗ |
| `mu` | `number` | let/var | `( isol - valp1 ) / ( valp2 - valp1 )` | ✗ |
| `nc` | `any` | let/var | `scope.normal_cache` | ✗ |
| `q2` | `any` | let/var | `q + scope.zd * 3` | ✗ |
| `q3` | `number` | let/var | `q * 3` | ✗ |
| `q1` | `any` | let/var | `q + 1` | ✗ |
| `qy` | `any` | let/var | `q + scope.yd` | ✗ |
| `qz` | `any` | let/var | `q + scope.zd` | ✗ |
| `q1y` | `any` | let/var | `q1 + scope.yd` | ✗ |
| `q1z` | `any` | let/var | `q1 + scope.zd` | ✗ |
| `qyz` | `any` | let/var | `q + scope.yd + scope.zd` | ✗ |
| `q1yz` | `any` | let/var | `q1 + scope.yd + scope.zd` | ✗ |
| `cubeindex` | `number` | let/var | `0` | ✗ |
| `field0` | `any` | let/var | `scope.field[ q ]` | ✗ |
| `field1` | `any` | let/var | `scope.field[ q1 ]` | ✗ |
| `field2` | `any` | let/var | `scope.field[ qy ]` | ✗ |
| `field3` | `any` | let/var | `scope.field[ q1y ]` | ✗ |
| `field4` | `any` | let/var | `scope.field[ qz ]` | ✗ |
| `field5` | `any` | let/var | `scope.field[ q1z ]` | ✗ |
| `field6` | `any` | let/var | `scope.field[ qyz ]` | ✗ |
| `field7` | `any` | let/var | `scope.field[ q1yz ]` | ✗ |
| `bits` | `number` | let/var | `edgeTable[ cubeindex ]` | ✗ |
| `d` | `any` | let/var | `scope.delta` | ✗ |
| `fx2` | `any` | let/var | `fx + d` | ✗ |
| `fy2` | `any` | let/var | `fy + d` | ✗ |
| `fz2` | `any` | let/var | `fz + d` | ✗ |
| `o1` | `any` | let/var | `*not shown*` | ✗ |
| `o2` | `any` | let/var | `*not shown*` | ✗ |
| `o3` | `any` | let/var | `*not shown*` | ✗ |
| `numtris` | `number` | let/var | `0` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `c` | `number` | let/var | `scope.count * 3` | ✗ |
| `nx` | `number` | let/var | `( norm[ o1 + 0 ] + norm[ o2 + 0 ] + norm[ o3 + 0 ] ) / 3` | ✗ |
| `ny` | `number` | let/var | `( norm[ o1 + 1 ] + norm[ o2 + 1 ] + norm[ o3 + 1 ] ) / 3` | ✗ |
| `nz` | `number` | let/var | `( norm[ o1 + 2 ] + norm[ o2 + 2 ] + norm[ o3 + 2 ] ) / 3` | ✗ |
| `d` | `number` | let/var | `scope.count * 2` | ✗ |
| `userDefineColor` | `boolean` | let/var | `! ( colors === undefined \|\| colors === null )` | ✗ |
| `ballColor` | `any` | let/var | `new Color( ballx, bally, ballz )` | ✗ |
| `radius` | `number` | let/var | `this.size * Math.sqrt( strength / subtract )` | ✗ |
| `zs` | `number` | let/var | `ballz * this.size` | ✗ |
| `ys` | `number` | let/var | `bally * this.size` | ✗ |
| `xs` | `number` | let/var | `ballx * this.size` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `z` | `any` | let/var | `*not shown*` | ✗ |
| `y_offset` | `any` | let/var | `*not shown*` | ✗ |
| `z_offset` | `any` | let/var | `*not shown*` | ✗ |
| `fx` | `any` | let/var | `*not shown*` | ✗ |
| `fy` | `any` | let/var | `*not shown*` | ✗ |
| `fz` | `any` | let/var | `*not shown*` | ✗ |
| `fz2` | `any` | let/var | `*not shown*` | ✗ |
| `fy2` | `any` | let/var | `*not shown*` | ✗ |
| `val` | `any` | let/var | `*not shown*` | ✗ |
| `ratio` | `number` | let/var | `Math.sqrt( ( x - xs ) * ( x - xs ) + ( y - ys ) * ( y - ys ) + ( z - zs ) * (...` | ✗ |
| `contrib` | `number` | let/var | `1 - ratio * ratio * ratio * ( ratio * ( ratio * 6 - 15 ) + 10 )` | ✗ |
| `size` | `any` | let/var | `this.size` | ✗ |
| `yd` | `any` | let/var | `this.yd` | ✗ |
| `zd` | `any` | let/var | `this.zd` | ✗ |
| `field` | `any` | let/var | `this.field` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `z` | `any` | let/var | `*not shown*` | ✗ |
| `xx` | `any` | let/var | `*not shown*` | ✗ |
| `val` | `any` | let/var | `*not shown*` | ✗ |
| `xdiv` | `any` | let/var | `*not shown*` | ✗ |
| `cxy` | `any` | let/var | `*not shown*` | ✗ |
| `dist` | `number` | let/var | `size * Math.sqrt( strength / subtract )` | ✗ |
| `size` | `any` | let/var | `this.size` | ✗ |
| `yd` | `any` | let/var | `this.yd` | ✗ |
| `zd` | `any` | let/var | `this.zd` | ✗ |
| `field` | `any` | let/var | `this.field` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `z` | `any` | let/var | `*not shown*` | ✗ |
| `yy` | `any` | let/var | `*not shown*` | ✗ |
| `val` | `any` | let/var | `*not shown*` | ✗ |
| `ydiv` | `any` | let/var | `*not shown*` | ✗ |
| `cy` | `any` | let/var | `*not shown*` | ✗ |
| `cxy` | `any` | let/var | `*not shown*` | ✗ |
| `dist` | `number` | let/var | `size * Math.sqrt( strength / subtract )` | ✗ |
| `size` | `any` | let/var | `this.size` | ✗ |
| `yd` | `any` | let/var | `this.yd` | ✗ |
| `zd` | `any` | let/var | `this.zd` | ✗ |
| `field` | `any` | let/var | `this.field` | ✗ |
| `x` | `any` | let/var | `*not shown*` | ✗ |
| `y` | `any` | let/var | `*not shown*` | ✗ |
| `z` | `any` | let/var | `*not shown*` | ✗ |
| `zz` | `any` | let/var | `*not shown*` | ✗ |
| `val` | `any` | let/var | `*not shown*` | ✗ |
| `zdiv` | `any` | let/var | `*not shown*` | ✗ |
| `cz` | `any` | let/var | `*not shown*` | ✗ |
| `cyz` | `any` | let/var | `*not shown*` | ✗ |
| `dist` | `number` | let/var | `size * Math.sqrt( strength / subtract )` | ✗ |
| `index` | `number` | let/var | `this.size2 * z + this.size * y + x` | ✗ |
| `index` | `number` | let/var | `this.size2 * z + this.size * y + x` | ✗ |
| `field` | `any` | let/var | `this.field` | ✗ |
| `size` | `any` | let/var | `this.size` | ✗ |
| `size2` | `any` | let/var | `this.size2` | ✗ |
| `index` | `number` | let/var | `size2 * z + size * y + x` | ✗ |
| `val` | `any` | let/var | `fieldCopy[ index ]` | ✗ |
| `count` | `number` | let/var | `1` | ✗ |
| `x3` | `number` | let/var | `x2 + x` | ✗ |
| `y3` | `number` | let/var | `y2 + y` | ✗ |
| `z3` | `number` | let/var | `z2 + z` | ✗ |
| `index2` | `number` | let/var | `size2 * z3 + size * y3 + x3` | ✗ |
| `val2` | `any` | let/var | `fieldCopy[ index2 ]` | ✗ |
| `smin2` | `number` | let/var | `this.size - 2` | ✗ |
| `z_offset` | `number` | let/var | `this.size2 * z` | ✗ |
| `fz` | `number` | let/var | `( z - this.halfsize ) / this.halfsize` | ✗ |
| `y_offset` | `number` | let/var | `z_offset + this.size * y` | ✗ |
| `fy` | `number` | let/var | `( y - this.halfsize ) / this.halfsize` | ✗ |
| `fx` | `number` | let/var | `( x - this.halfsize ) / this.halfsize` | ✗ |
| `q` | `number` | let/var | `y_offset + x` | ✗ |
| `edgeTable` | `Int32Array<ArrayBuffer>` | let/var | `new Int32Array( [ 0x0, 0x109, 0x203, 0x30a, 0x406, 0x50f, 0x605, 0x70c, 0x80c...` | ✗ |
| `triTable` | `Int32Array<ArrayBuffer>` | let/var | `new Int32Array( [ - 1, - 1, - 1, - 1, - 1, - 1, - 1, - 1, - 1, - 1, - 1, - 1,...` | ✗ |


---

## Functions

### `lerp(a: any, b: any, t: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function lerp( a, b, t ) {

			return a + ( b - a ) * t;

		}
```
</details>

### `VIntX(q: any, offset: any, isol: any, x: any, y: any, z: any, valp1: any, valp2: any, c_offset1: any, c_offset2: any): void`

**Parameters:**

- **`q`** `any`
- **`offset`** `any`
- **`isol`** `any`
- **`x`** `any`
- **`y`** `any`
- **`z`** `any`
- **`valp1`** `any`
- **`valp2`** `any`
- **`c_offset1`** `any`
- **`c_offset2`** `any`

**Returns:** `void`

**Calls:**

- `lerp`

<details><summary>Code</summary>

```typescript
function VIntX( q, offset, isol, x, y, z, valp1, valp2, c_offset1, c_offset2 ) {

			const mu = ( isol - valp1 ) / ( valp2 - valp1 ),
				nc = scope.normal_cache;

			vlist[ offset + 0 ] = x + mu * scope.delta;
			vlist[ offset + 1 ] = y;
			vlist[ offset + 2 ] = z;

			nlist[ offset + 0 ] = lerp( nc[ q + 0 ], nc[ q + 3 ], mu );
			nlist[ offset + 1 ] = lerp( nc[ q + 1 ], nc[ q + 4 ], mu );
			nlist[ offset + 2 ] = lerp( nc[ q + 2 ], nc[ q + 5 ], mu );

			clist[ offset + 0 ] = lerp( scope.palette[ c_offset1 * 3 + 0 ], scope.palette[ c_offset2 * 3 + 0 ], mu );
			clist[ offset + 1 ] = lerp( scope.palette[ c_offset1 * 3 + 1 ], scope.palette[ c_offset2 * 3 + 1 ], mu );
			clist[ offset + 2 ] = lerp( scope.palette[ c_offset1 * 3 + 2 ], scope.palette[ c_offset2 * 3 + 2 ], mu );

		}
```
</details>

### `VIntY(q: any, offset: any, isol: any, x: any, y: any, z: any, valp1: any, valp2: any, c_offset1: any, c_offset2: any): void`

**Parameters:**

- **`q`** `any`
- **`offset`** `any`
- **`isol`** `any`
- **`x`** `any`
- **`y`** `any`
- **`z`** `any`
- **`valp1`** `any`
- **`valp2`** `any`
- **`c_offset1`** `any`
- **`c_offset2`** `any`

**Returns:** `void`

**Calls:**

- `lerp`

<details><summary>Code</summary>

```typescript
function VIntY( q, offset, isol, x, y, z, valp1, valp2, c_offset1, c_offset2 ) {

			const mu = ( isol - valp1 ) / ( valp2 - valp1 ),
				nc = scope.normal_cache;

			vlist[ offset + 0 ] = x;
			vlist[ offset + 1 ] = y + mu * scope.delta;
			vlist[ offset + 2 ] = z;

			const q2 = q + scope.yd * 3;

			nlist[ offset + 0 ] = lerp( nc[ q + 0 ], nc[ q2 + 0 ], mu );
			nlist[ offset + 1 ] = lerp( nc[ q + 1 ], nc[ q2 + 1 ], mu );
			nlist[ offset + 2 ] = lerp( nc[ q + 2 ], nc[ q2 + 2 ], mu );

			clist[ offset + 0 ] = lerp( scope.palette[ c_offset1 * 3 + 0 ], scope.palette[ c_offset2 * 3 + 0 ], mu );
			clist[ offset + 1 ] = lerp( scope.palette[ c_offset1 * 3 + 1 ], scope.palette[ c_offset2 * 3 + 1 ], mu );
			clist[ offset + 2 ] = lerp( scope.palette[ c_offset1 * 3 + 2 ], scope.palette[ c_offset2 * 3 + 2 ], mu );

		}
```
</details>

### `VIntZ(q: any, offset: any, isol: any, x: any, y: any, z: any, valp1: any, valp2: any, c_offset1: any, c_offset2: any): void`

**Parameters:**

- **`q`** `any`
- **`offset`** `any`
- **`isol`** `any`
- **`x`** `any`
- **`y`** `any`
- **`z`** `any`
- **`valp1`** `any`
- **`valp2`** `any`
- **`c_offset1`** `any`
- **`c_offset2`** `any`

**Returns:** `void`

**Calls:**

- `lerp`

<details><summary>Code</summary>

```typescript
function VIntZ( q, offset, isol, x, y, z, valp1, valp2, c_offset1, c_offset2 ) {

			const mu = ( isol - valp1 ) / ( valp2 - valp1 ),
				nc = scope.normal_cache;

			vlist[ offset + 0 ] = x;
			vlist[ offset + 1 ] = y;
			vlist[ offset + 2 ] = z + mu * scope.delta;

			const q2 = q + scope.zd * 3;

			nlist[ offset + 0 ] = lerp( nc[ q + 0 ], nc[ q2 + 0 ], mu );
			nlist[ offset + 1 ] = lerp( nc[ q + 1 ], nc[ q2 + 1 ], mu );
			nlist[ offset + 2 ] = lerp( nc[ q + 2 ], nc[ q2 + 2 ], mu );

			clist[ offset + 0 ] = lerp( scope.palette[ c_offset1 * 3 + 0 ], scope.palette[ c_offset2 * 3 + 0 ], mu );
			clist[ offset + 1 ] = lerp( scope.palette[ c_offset1 * 3 + 1 ], scope.palette[ c_offset2 * 3 + 1 ], mu );
			clist[ offset + 2 ] = lerp( scope.palette[ c_offset1 * 3 + 2 ], scope.palette[ c_offset2 * 3 + 2 ], mu );

		}
```
</details>

### `compNorm(q: any): void`

**Parameters:**

- **`q`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function compNorm( q ) {

			const q3 = q * 3;

			if ( scope.normal_cache[ q3 ] === 0.0 ) {

				scope.normal_cache[ q3 + 0 ] = scope.field[ q - 1 ] - scope.field[ q + 1 ];
				scope.normal_cache[ q3 + 1 ] =
					scope.field[ q - scope.yd ] - scope.field[ q + scope.yd ];
				scope.normal_cache[ q3 + 2 ] =
					scope.field[ q - scope.zd ] - scope.field[ q + scope.zd ];

			}

		}
```
</details>

### `polygonize(fx: any, fy: any, fz: any, q: any, isol: any): number`

**Parameters:**

- **`fx`** `any`
- **`fy`** `any`
- **`fz`** `any`
- **`q`** `any`
- **`isol`** `any`

**Returns:** `number`

**Calls:**

- `compNorm`
- `VIntX`
- `VIntY`
- `VIntZ`
- `posnormtriv`

**Internal Comments:**
```
// cache indices (x2)
// if cube is entirely in/out of the surface - bail, nothing to draw (x2)
// top of the cube
// bottom of the cube
// vertical lines of the cube
// here is where triangles are created
```

<details><summary>Code</summary>

```typescript
function polygonize( fx, fy, fz, q, isol ) {

			// cache indices
			const q1 = q + 1,
				qy = q + scope.yd,
				qz = q + scope.zd,
				q1y = q1 + scope.yd,
				q1z = q1 + scope.zd,
				qyz = q + scope.yd + scope.zd,
				q1yz = q1 + scope.yd + scope.zd;

			let cubeindex = 0;
			const field0 = scope.field[ q ],
				field1 = scope.field[ q1 ],
				field2 = scope.field[ qy ],
				field3 = scope.field[ q1y ],
				field4 = scope.field[ qz ],
				field5 = scope.field[ q1z ],
				field6 = scope.field[ qyz ],
				field7 = scope.field[ q1yz ];

			if ( field0 < isol ) cubeindex |= 1;
			if ( field1 < isol ) cubeindex |= 2;
			if ( field2 < isol ) cubeindex |= 8;
			if ( field3 < isol ) cubeindex |= 4;
			if ( field4 < isol ) cubeindex |= 16;
			if ( field5 < isol ) cubeindex |= 32;
			if ( field6 < isol ) cubeindex |= 128;
			if ( field7 < isol ) cubeindex |= 64;

			// if cube is entirely in/out of the surface - bail, nothing to draw

			const bits = edgeTable[ cubeindex ];
			if ( bits === 0 ) return 0;

			const d = scope.delta,
				fx2 = fx + d,
				fy2 = fy + d,
				fz2 = fz + d;

			// top of the cube

			if ( bits & 1 ) {

				compNorm( q );
				compNorm( q1 );
				VIntX( q * 3, 0, isol, fx, fy, fz, field0, field1, q, q1 );

			}

			if ( bits & 2 ) {

				compNorm( q1 );
				compNorm( q1y );
				VIntY( q1 * 3, 3, isol, fx2, fy, fz, field1, field3, q1, q1y );

			}

			if ( bits & 4 ) {

				compNorm( qy );
				compNorm( q1y );
				VIntX( qy * 3, 6, isol, fx, fy2, fz, field2, field3, qy, q1y );

			}

			if ( bits & 8 ) {

				compNorm( q );
				compNorm( qy );
				VIntY( q * 3, 9, isol, fx, fy, fz, field0, field2, q, qy );

			}

			// bottom of the cube

			if ( bits & 16 ) {

				compNorm( qz );
				compNorm( q1z );
				VIntX( qz * 3, 12, isol, fx, fy, fz2, field4, field5, qz, q1z );

			}

			if ( bits & 32 ) {

				compNorm( q1z );
				compNorm( q1yz );
				VIntY(
					q1z * 3,
					15,
					isol,
					fx2,
					fy,
					fz2,
					field5,
					field7,
					q1z,
					q1yz
				);

			}

			if ( bits & 64 ) {

				compNorm( qyz );
				compNorm( q1yz );
				VIntX(
					qyz * 3,
					18,
					isol,
					fx,
					fy2,
					fz2,
					field6,
					field7,
					qyz,
					q1yz
				);

			}

			if ( bits & 128 ) {

				compNorm( qz );
				compNorm( qyz );
				VIntY( qz * 3, 21, isol, fx, fy, fz2, field4, field6, qz, qyz );

			}

			// vertical lines of the cube
			if ( bits & 256 ) {

				compNorm( q );
				compNorm( qz );
				VIntZ( q * 3, 24, isol, fx, fy, fz, field0, field4, q, qz );

			}

			if ( bits & 512 ) {

				compNorm( q1 );
				compNorm( q1z );
				VIntZ( q1 * 3, 27, isol, fx2, fy, fz, field1, field5, q1, q1z );

			}

			if ( bits & 1024 ) {

				compNorm( q1y );
				compNorm( q1yz );
				VIntZ(
					q1y * 3,
					30,
					isol,
					fx2,
					fy2,
					fz,
					field3,
					field7,
					q1y,
					q1yz
				);

			}

			if ( bits & 2048 ) {

				compNorm( qy );
				compNorm( qyz );
				VIntZ( qy * 3, 33, isol, fx, fy2, fz, field2, field6, qy, qyz );

			}

			cubeindex <<= 4; // re-purpose cubeindex into an offset into triTable

			let o1,
				o2,
				o3,
				numtris = 0,
				i = 0;

			// here is where triangles are created

			while ( triTable[ cubeindex + i ] != - 1 ) {

				o1 = cubeindex + i;
				o2 = o1 + 1;
				o3 = o1 + 2;

				posnormtriv(
					vlist,
					nlist,
					clist,
					3 * triTable[ o1 ],
					3 * triTable[ o2 ],
					3 * triTable[ o3 ]
				);

				i += 3;
				numtris ++;

			}

			return numtris;

		}
```
</details>

### `posnormtriv(pos: any, norm: any, colors: any, o1: any, o2: any, o3: any): void`

**Parameters:**

- **`pos`** `any`
- **`norm`** `any`
- **`colors`** `any`
- **`o1`** `any`
- **`o2`** `any`
- **`o3`** `any`

**Returns:** `void`

**Internal Comments:**
```
// positions (x5)
// normals
// uvs
// colors
```

<details><summary>Code</summary>

```typescript
function posnormtriv( pos, norm, colors, o1, o2, o3 ) {

			const c = scope.count * 3;

			// positions

			scope.positionArray[ c + 0 ] = pos[ o1 ];
			scope.positionArray[ c + 1 ] = pos[ o1 + 1 ];
			scope.positionArray[ c + 2 ] = pos[ o1 + 2 ];

			scope.positionArray[ c + 3 ] = pos[ o2 ];
			scope.positionArray[ c + 4 ] = pos[ o2 + 1 ];
			scope.positionArray[ c + 5 ] = pos[ o2 + 2 ];

			scope.positionArray[ c + 6 ] = pos[ o3 ];
			scope.positionArray[ c + 7 ] = pos[ o3 + 1 ];
			scope.positionArray[ c + 8 ] = pos[ o3 + 2 ];

			// normals

			if ( scope.material.flatShading === true ) {

				const nx = ( norm[ o1 + 0 ] + norm[ o2 + 0 ] + norm[ o3 + 0 ] ) / 3;
				const ny = ( norm[ o1 + 1 ] + norm[ o2 + 1 ] + norm[ o3 + 1 ] ) / 3;
				const nz = ( norm[ o1 + 2 ] + norm[ o2 + 2 ] + norm[ o3 + 2 ] ) / 3;

				scope.normalArray[ c + 0 ] = nx;
				scope.normalArray[ c + 1 ] = ny;
				scope.normalArray[ c + 2 ] = nz;

				scope.normalArray[ c + 3 ] = nx;
				scope.normalArray[ c + 4 ] = ny;
				scope.normalArray[ c + 5 ] = nz;

				scope.normalArray[ c + 6 ] = nx;
				scope.normalArray[ c + 7 ] = ny;
				scope.normalArray[ c + 8 ] = nz;

			} else {

				scope.normalArray[ c + 0 ] = norm[ o1 + 0 ];
				scope.normalArray[ c + 1 ] = norm[ o1 + 1 ];
				scope.normalArray[ c + 2 ] = norm[ o1 + 2 ];

				scope.normalArray[ c + 3 ] = norm[ o2 + 0 ];
				scope.normalArray[ c + 4 ] = norm[ o2 + 1 ];
				scope.normalArray[ c + 5 ] = norm[ o2 + 2 ];

				scope.normalArray[ c + 6 ] = norm[ o3 + 0 ];
				scope.normalArray[ c + 7 ] = norm[ o3 + 1 ];
				scope.normalArray[ c + 8 ] = norm[ o3 + 2 ];

			}

			// uvs

			if ( scope.enableUvs ) {

				const d = scope.count * 2;

				scope.uvArray[ d + 0 ] = pos[ o1 + 0 ];
				scope.uvArray[ d + 1 ] = pos[ o1 + 2 ];

				scope.uvArray[ d + 2 ] = pos[ o2 + 0 ];
				scope.uvArray[ d + 3 ] = pos[ o2 + 2 ];

				scope.uvArray[ d + 4 ] = pos[ o3 + 0 ];
				scope.uvArray[ d + 5 ] = pos[ o3 + 2 ];

			}

			// colors

			if ( scope.enableColors ) {

				scope.colorArray[ c + 0 ] = colors[ o1 + 0 ];
				scope.colorArray[ c + 1 ] = colors[ o1 + 1 ];
				scope.colorArray[ c + 2 ] = colors[ o1 + 2 ];

				scope.colorArray[ c + 3 ] = colors[ o2 + 0 ];
				scope.colorArray[ c + 4 ] = colors[ o2 + 1 ];
				scope.colorArray[ c + 5 ] = colors[ o2 + 2 ];

				scope.colorArray[ c + 6 ] = colors[ o3 + 0 ];
				scope.colorArray[ c + 7 ] = colors[ o3 + 1 ];
				scope.colorArray[ c + 8 ] = colors[ o3 + 2 ];

			}

			scope.count += 3;

		}
```
</details>


---

## Classes

### `MarchingCubes`

<details><summary>Class Code</summary>

```ts
class MarchingCubes extends Mesh {

	/**
	 * Constructs a new marching cubes instance.
	 *
	 * @param {number} resolution - The effect's resolution.
	 * @param {Material} material - The cube's material.
	 * @param {boolean} [enableUvs=false] - Whether texture coordinates should be animated or not.
	 * @param {boolean} [enableColors=false] - Whether colors should be animated or not.
	 * @param {number} [maxPolyCount=10000] - The maximum size of the geometry buffers.
	 */
	constructor( resolution, material, enableUvs = false, enableColors = false, maxPolyCount = 10000 ) {

		const geometry = new BufferGeometry();

		super( geometry, material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMarchingCubes = true;

		const scope = this;

		// temp buffers used in polygonize

		const vlist = new Float32Array( 12 * 3 );
		const nlist = new Float32Array( 12 * 3 );
		const clist = new Float32Array( 12 * 3 );

		/**
		 * Whether texture coordinates should be animated or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.enableUvs = enableUvs;

		/**
		 * Whether colors should be animated or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.enableColors = enableColors;

		// functions have to be object properties
		// prototype functions kill performance
		// (tested and it was 4x slower !!!)

		this.init = function ( resolution ) {

			this.resolution = resolution;

			// parameters

			this.isolation = 80.0;

			// size of field, 32 is pushing it in Javascript :)

			this.size = resolution;
			this.size2 = this.size * this.size;
			this.size3 = this.size2 * this.size;
			this.halfsize = this.size / 2.0;

			// deltas

			this.delta = 2.0 / this.size;
			this.yd = this.size;
			this.zd = this.size2;

			this.field = new Float32Array( this.size3 );
			this.normal_cache = new Float32Array( this.size3 * 3 );
			this.palette = new Float32Array( this.size3 * 3 );

			//

			this.count = 0;

			const maxVertexCount = maxPolyCount * 3;

			this.positionArray = new Float32Array( maxVertexCount * 3 );
			const positionAttribute = new BufferAttribute( this.positionArray, 3 );
			positionAttribute.setUsage( DynamicDrawUsage );
			geometry.setAttribute( 'position', positionAttribute );

			this.normalArray = new Float32Array( maxVertexCount * 3 );
			const normalAttribute = new BufferAttribute( this.normalArray, 3 );
			normalAttribute.setUsage( DynamicDrawUsage );
			geometry.setAttribute( 'normal', normalAttribute );

			if ( this.enableUvs ) {

				this.uvArray = new Float32Array( maxVertexCount * 2 );
				const uvAttribute = new BufferAttribute( this.uvArray, 2 );
				uvAttribute.setUsage( DynamicDrawUsage );
				geometry.setAttribute( 'uv', uvAttribute );

			}

			if ( this.enableColors ) {

				this.colorArray = new Float32Array( maxVertexCount * 3 );
				const colorAttribute = new BufferAttribute( this.colorArray, 3 );
				colorAttribute.setUsage( DynamicDrawUsage );
				geometry.setAttribute( 'color', colorAttribute );

			}

			geometry.boundingSphere = new Sphere( new Vector3(), 1 );

		};

		///////////////////////
		// Polygonization
		///////////////////////

		function lerp( a, b, t ) {

			return a + ( b - a ) * t;

		}

		function VIntX( q, offset, isol, x, y, z, valp1, valp2, c_offset1, c_offset2 ) {

			const mu = ( isol - valp1 ) / ( valp2 - valp1 ),
				nc = scope.normal_cache;

			vlist[ offset + 0 ] = x + mu * scope.delta;
			vlist[ offset + 1 ] = y;
			vlist[ offset + 2 ] = z;

			nlist[ offset + 0 ] = lerp( nc[ q + 0 ], nc[ q + 3 ], mu );
			nlist[ offset + 1 ] = lerp( nc[ q + 1 ], nc[ q + 4 ], mu );
			nlist[ offset + 2 ] = lerp( nc[ q + 2 ], nc[ q + 5 ], mu );

			clist[ offset + 0 ] = lerp( scope.palette[ c_offset1 * 3 + 0 ], scope.palette[ c_offset2 * 3 + 0 ], mu );
			clist[ offset + 1 ] = lerp( scope.palette[ c_offset1 * 3 + 1 ], scope.palette[ c_offset2 * 3 + 1 ], mu );
			clist[ offset + 2 ] = lerp( scope.palette[ c_offset1 * 3 + 2 ], scope.palette[ c_offset2 * 3 + 2 ], mu );

		}

		function VIntY( q, offset, isol, x, y, z, valp1, valp2, c_offset1, c_offset2 ) {

			const mu = ( isol - valp1 ) / ( valp2 - valp1 ),
				nc = scope.normal_cache;

			vlist[ offset + 0 ] = x;
			vlist[ offset + 1 ] = y + mu * scope.delta;
			vlist[ offset + 2 ] = z;

			const q2 = q + scope.yd * 3;

			nlist[ offset + 0 ] = lerp( nc[ q + 0 ], nc[ q2 + 0 ], mu );
			nlist[ offset + 1 ] = lerp( nc[ q + 1 ], nc[ q2 + 1 ], mu );
			nlist[ offset + 2 ] = lerp( nc[ q + 2 ], nc[ q2 + 2 ], mu );

			clist[ offset + 0 ] = lerp( scope.palette[ c_offset1 * 3 + 0 ], scope.palette[ c_offset2 * 3 + 0 ], mu );
			clist[ offset + 1 ] = lerp( scope.palette[ c_offset1 * 3 + 1 ], scope.palette[ c_offset2 * 3 + 1 ], mu );
			clist[ offset + 2 ] = lerp( scope.palette[ c_offset1 * 3 + 2 ], scope.palette[ c_offset2 * 3 + 2 ], mu );

		}

		function VIntZ( q, offset, isol, x, y, z, valp1, valp2, c_offset1, c_offset2 ) {

			const mu = ( isol - valp1 ) / ( valp2 - valp1 ),
				nc = scope.normal_cache;

			vlist[ offset + 0 ] = x;
			vlist[ offset + 1 ] = y;
			vlist[ offset + 2 ] = z + mu * scope.delta;

			const q2 = q + scope.zd * 3;

			nlist[ offset + 0 ] = lerp( nc[ q + 0 ], nc[ q2 + 0 ], mu );
			nlist[ offset + 1 ] = lerp( nc[ q + 1 ], nc[ q2 + 1 ], mu );
			nlist[ offset + 2 ] = lerp( nc[ q + 2 ], nc[ q2 + 2 ], mu );

			clist[ offset + 0 ] = lerp( scope.palette[ c_offset1 * 3 + 0 ], scope.palette[ c_offset2 * 3 + 0 ], mu );
			clist[ offset + 1 ] = lerp( scope.palette[ c_offset1 * 3 + 1 ], scope.palette[ c_offset2 * 3 + 1 ], mu );
			clist[ offset + 2 ] = lerp( scope.palette[ c_offset1 * 3 + 2 ], scope.palette[ c_offset2 * 3 + 2 ], mu );

		}

		function compNorm( q ) {

			const q3 = q * 3;

			if ( scope.normal_cache[ q3 ] === 0.0 ) {

				scope.normal_cache[ q3 + 0 ] = scope.field[ q - 1 ] - scope.field[ q + 1 ];
				scope.normal_cache[ q3 + 1 ] =
					scope.field[ q - scope.yd ] - scope.field[ q + scope.yd ];
				scope.normal_cache[ q3 + 2 ] =
					scope.field[ q - scope.zd ] - scope.field[ q + scope.zd ];

			}

		}

		// Returns total number of triangles. Fills triangles.
		// (this is where most of time is spent - it's inner work of O(n3) loop )

		function polygonize( fx, fy, fz, q, isol ) {

			// cache indices
			const q1 = q + 1,
				qy = q + scope.yd,
				qz = q + scope.zd,
				q1y = q1 + scope.yd,
				q1z = q1 + scope.zd,
				qyz = q + scope.yd + scope.zd,
				q1yz = q1 + scope.yd + scope.zd;

			let cubeindex = 0;
			const field0 = scope.field[ q ],
				field1 = scope.field[ q1 ],
				field2 = scope.field[ qy ],
				field3 = scope.field[ q1y ],
				field4 = scope.field[ qz ],
				field5 = scope.field[ q1z ],
				field6 = scope.field[ qyz ],
				field7 = scope.field[ q1yz ];

			if ( field0 < isol ) cubeindex |= 1;
			if ( field1 < isol ) cubeindex |= 2;
			if ( field2 < isol ) cubeindex |= 8;
			if ( field3 < isol ) cubeindex |= 4;
			if ( field4 < isol ) cubeindex |= 16;
			if ( field5 < isol ) cubeindex |= 32;
			if ( field6 < isol ) cubeindex |= 128;
			if ( field7 < isol ) cubeindex |= 64;

			// if cube is entirely in/out of the surface - bail, nothing to draw

			const bits = edgeTable[ cubeindex ];
			if ( bits === 0 ) return 0;

			const d = scope.delta,
				fx2 = fx + d,
				fy2 = fy + d,
				fz2 = fz + d;

			// top of the cube

			if ( bits & 1 ) {

				compNorm( q );
				compNorm( q1 );
				VIntX( q * 3, 0, isol, fx, fy, fz, field0, field1, q, q1 );

			}

			if ( bits & 2 ) {

				compNorm( q1 );
				compNorm( q1y );
				VIntY( q1 * 3, 3, isol, fx2, fy, fz, field1, field3, q1, q1y );

			}

			if ( bits & 4 ) {

				compNorm( qy );
				compNorm( q1y );
				VIntX( qy * 3, 6, isol, fx, fy2, fz, field2, field3, qy, q1y );

			}

			if ( bits & 8 ) {

				compNorm( q );
				compNorm( qy );
				VIntY( q * 3, 9, isol, fx, fy, fz, field0, field2, q, qy );

			}

			// bottom of the cube

			if ( bits & 16 ) {

				compNorm( qz );
				compNorm( q1z );
				VIntX( qz * 3, 12, isol, fx, fy, fz2, field4, field5, qz, q1z );

			}

			if ( bits & 32 ) {

				compNorm( q1z );
				compNorm( q1yz );
				VIntY(
					q1z * 3,
					15,
					isol,
					fx2,
					fy,
					fz2,
					field5,
					field7,
					q1z,
					q1yz
				);

			}

			if ( bits & 64 ) {

				compNorm( qyz );
				compNorm( q1yz );
				VIntX(
					qyz * 3,
					18,
					isol,
					fx,
					fy2,
					fz2,
					field6,
					field7,
					qyz,
					q1yz
				);

			}

			if ( bits & 128 ) {

				compNorm( qz );
				compNorm( qyz );
				VIntY( qz * 3, 21, isol, fx, fy, fz2, field4, field6, qz, qyz );

			}

			// vertical lines of the cube
			if ( bits & 256 ) {

				compNorm( q );
				compNorm( qz );
				VIntZ( q * 3, 24, isol, fx, fy, fz, field0, field4, q, qz );

			}

			if ( bits & 512 ) {

				compNorm( q1 );
				compNorm( q1z );
				VIntZ( q1 * 3, 27, isol, fx2, fy, fz, field1, field5, q1, q1z );

			}

			if ( bits & 1024 ) {

				compNorm( q1y );
				compNorm( q1yz );
				VIntZ(
					q1y * 3,
					30,
					isol,
					fx2,
					fy2,
					fz,
					field3,
					field7,
					q1y,
					q1yz
				);

			}

			if ( bits & 2048 ) {

				compNorm( qy );
				compNorm( qyz );
				VIntZ( qy * 3, 33, isol, fx, fy2, fz, field2, field6, qy, qyz );

			}

			cubeindex <<= 4; // re-purpose cubeindex into an offset into triTable

			let o1,
				o2,
				o3,
				numtris = 0,
				i = 0;

			// here is where triangles are created

			while ( triTable[ cubeindex + i ] != - 1 ) {

				o1 = cubeindex + i;
				o2 = o1 + 1;
				o3 = o1 + 2;

				posnormtriv(
					vlist,
					nlist,
					clist,
					3 * triTable[ o1 ],
					3 * triTable[ o2 ],
					3 * triTable[ o3 ]
				);

				i += 3;
				numtris ++;

			}

			return numtris;

		}

		function posnormtriv( pos, norm, colors, o1, o2, o3 ) {

			const c = scope.count * 3;

			// positions

			scope.positionArray[ c + 0 ] = pos[ o1 ];
			scope.positionArray[ c + 1 ] = pos[ o1 + 1 ];
			scope.positionArray[ c + 2 ] = pos[ o1 + 2 ];

			scope.positionArray[ c + 3 ] = pos[ o2 ];
			scope.positionArray[ c + 4 ] = pos[ o2 + 1 ];
			scope.positionArray[ c + 5 ] = pos[ o2 + 2 ];

			scope.positionArray[ c + 6 ] = pos[ o3 ];
			scope.positionArray[ c + 7 ] = pos[ o3 + 1 ];
			scope.positionArray[ c + 8 ] = pos[ o3 + 2 ];

			// normals

			if ( scope.material.flatShading === true ) {

				const nx = ( norm[ o1 + 0 ] + norm[ o2 + 0 ] + norm[ o3 + 0 ] ) / 3;
				const ny = ( norm[ o1 + 1 ] + norm[ o2 + 1 ] + norm[ o3 + 1 ] ) / 3;
				const nz = ( norm[ o1 + 2 ] + norm[ o2 + 2 ] + norm[ o3 + 2 ] ) / 3;

				scope.normalArray[ c + 0 ] = nx;
				scope.normalArray[ c + 1 ] = ny;
				scope.normalArray[ c + 2 ] = nz;

				scope.normalArray[ c + 3 ] = nx;
				scope.normalArray[ c + 4 ] = ny;
				scope.normalArray[ c + 5 ] = nz;

				scope.normalArray[ c + 6 ] = nx;
				scope.normalArray[ c + 7 ] = ny;
				scope.normalArray[ c + 8 ] = nz;

			} else {

				scope.normalArray[ c + 0 ] = norm[ o1 + 0 ];
				scope.normalArray[ c + 1 ] = norm[ o1 + 1 ];
				scope.normalArray[ c + 2 ] = norm[ o1 + 2 ];

				scope.normalArray[ c + 3 ] = norm[ o2 + 0 ];
				scope.normalArray[ c + 4 ] = norm[ o2 + 1 ];
				scope.normalArray[ c + 5 ] = norm[ o2 + 2 ];

				scope.normalArray[ c + 6 ] = norm[ o3 + 0 ];
				scope.normalArray[ c + 7 ] = norm[ o3 + 1 ];
				scope.normalArray[ c + 8 ] = norm[ o3 + 2 ];

			}

			// uvs

			if ( scope.enableUvs ) {

				const d = scope.count * 2;

				scope.uvArray[ d + 0 ] = pos[ o1 + 0 ];
				scope.uvArray[ d + 1 ] = pos[ o1 + 2 ];

				scope.uvArray[ d + 2 ] = pos[ o2 + 0 ];
				scope.uvArray[ d + 3 ] = pos[ o2 + 2 ];

				scope.uvArray[ d + 4 ] = pos[ o3 + 0 ];
				scope.uvArray[ d + 5 ] = pos[ o3 + 2 ];

			}

			// colors

			if ( scope.enableColors ) {

				scope.colorArray[ c + 0 ] = colors[ o1 + 0 ];
				scope.colorArray[ c + 1 ] = colors[ o1 + 1 ];
				scope.colorArray[ c + 2 ] = colors[ o1 + 2 ];

				scope.colorArray[ c + 3 ] = colors[ o2 + 0 ];
				scope.colorArray[ c + 4 ] = colors[ o2 + 1 ];
				scope.colorArray[ c + 5 ] = colors[ o2 + 2 ];

				scope.colorArray[ c + 6 ] = colors[ o3 + 0 ];
				scope.colorArray[ c + 7 ] = colors[ o3 + 1 ];
				scope.colorArray[ c + 8 ] = colors[ o3 + 2 ];

			}

			scope.count += 3;

		}

		/////////////////////////////////////
		// Metaballs
		/////////////////////////////////////

		/**
		 * Adds a reciprocal ball (nice and blobby) that, to be fast, fades to zero after
		 * a fixed distance, determined by strength and subtract.
		 *
		 * @param {number} ballx - The x-coordinate of the ball.
		 * @param {number} bally - The y-coordinate of the ball.
		 * @param {number} ballz - The z-coordinate of the ball.
		 * @param {number} strength - The strength factor.
		 * @param {number} subtract - The subtract factor.
		 * @param {Color} colors - The color.
		 */
		this.addBall = function ( ballx, bally, ballz, strength, subtract, colors ) {

			const sign = Math.sign( strength );
			strength = Math.abs( strength );
			const userDefineColor = ! ( colors === undefined || colors === null );
			let ballColor = new Color( ballx, bally, ballz );

			if ( userDefineColor ) {

				try {

					ballColor =
						colors instanceof Color
							? colors
							: Array.isArray( colors )
								? new Color(
									Math.min( Math.abs( colors[ 0 ] ), 1 ),
									Math.min( Math.abs( colors[ 1 ] ), 1 ),
									Math.min( Math.abs( colors[ 2 ] ), 1 )
							  )
								: new Color( colors );

				} catch ( err ) {

					ballColor = new Color( ballx, bally, ballz );

				}

			}

			// Let's solve the equation to find the radius:
			// 1.0 / (0.000001 + radius^2) * strength - subtract = 0
			// strength / (radius^2) = subtract
			// strength = subtract * radius^2
			// radius^2 = strength / subtract
			// radius = sqrt(strength / subtract)

			const radius = this.size * Math.sqrt( strength / subtract ),
				zs = ballz * this.size,
				ys = bally * this.size,
				xs = ballx * this.size;

			let min_z = Math.floor( zs - radius );
			if ( min_z < 1 ) min_z = 1;
			let max_z = Math.floor( zs + radius );
			if ( max_z > this.size - 1 ) max_z = this.size - 1;
			let min_y = Math.floor( ys - radius );
			if ( min_y < 1 ) min_y = 1;
			let max_y = Math.floor( ys + radius );
			if ( max_y > this.size - 1 ) max_y = this.size - 1;
			let min_x = Math.floor( xs - radius );
			if ( min_x < 1 ) min_x = 1;
			let max_x = Math.floor( xs + radius );
			if ( max_x > this.size - 1 ) max_x = this.size - 1;

			// Don't polygonize in the outer layer because normals aren't
			// well-defined there.

			let x, y, z, y_offset, z_offset, fx, fy, fz, fz2, fy2, val;

			for ( z = min_z; z < max_z; z ++ ) {

				z_offset = this.size2 * z;
				fz = z / this.size - ballz;
				fz2 = fz * fz;

				for ( y = min_y; y < max_y; y ++ ) {

					y_offset = z_offset + this.size * y;
					fy = y / this.size - bally;
					fy2 = fy * fy;

					for ( x = min_x; x < max_x; x ++ ) {

						fx = x / this.size - ballx;
						val = strength / ( 0.000001 + fx * fx + fy2 + fz2 ) - subtract;
						if ( val > 0.0 ) {

							this.field[ y_offset + x ] += val * sign;

							// optimization
							// http://www.geisswerks.com/ryan/BLOBS/blobs.html
							const ratio =
								Math.sqrt( ( x - xs ) * ( x - xs ) + ( y - ys ) * ( y - ys ) + ( z - zs ) * ( z - zs ) ) / radius;
							const contrib =
								1 - ratio * ratio * ratio * ( ratio * ( ratio * 6 - 15 ) + 10 );
							this.palette[ ( y_offset + x ) * 3 + 0 ] += ballColor.r * contrib;
							this.palette[ ( y_offset + x ) * 3 + 1 ] += ballColor.g * contrib;
							this.palette[ ( y_offset + x ) * 3 + 2 ] += ballColor.b * contrib;

						}

					}

				}

			}

		};

		/**
		 * Adds a plane along the x-axis.
		 *
		 * @param {number} strength - The strength factor.
		 * @param {number} subtract - The subtract factor.
		 */
		this.addPlaneX = function ( strength, subtract ) {

			// cache attribute lookups
			const size = this.size,
				yd = this.yd,
				zd = this.zd,
				field = this.field;

			let x,
				y,
				z,
				xx,
				val,
				xdiv,
				cxy,
				dist = size * Math.sqrt( strength / subtract );

			if ( dist > size ) dist = size;

			for ( x = 0; x < dist; x ++ ) {

				xdiv = x / size;
				xx = xdiv * xdiv;
				val = strength / ( 0.0001 + xx ) - subtract;

				if ( val > 0.0 ) {

					for ( y = 0; y < size; y ++ ) {

						cxy = x + y * yd;

						for ( z = 0; z < size; z ++ ) {

							field[ zd * z + cxy ] += val;

						}

					}

				}

			}

		};

		/**
		 * Adds a plane along the y-axis.
		 *
		 * @param {number} strength - The strength factor.
		 * @param {number} subtract - The subtract factor.
		 */
		this.addPlaneY = function ( strength, subtract ) {

			// cache attribute lookups
			const size = this.size,
				yd = this.yd,
				zd = this.zd,
				field = this.field;

			let x,
				y,
				z,
				yy,
				val,
				ydiv,
				cy,
				cxy,
				dist = size * Math.sqrt( strength / subtract );

			if ( dist > size ) dist = size;

			for ( y = 0; y < dist; y ++ ) {

				ydiv = y / size;
				yy = ydiv * ydiv;
				val = strength / ( 0.0001 + yy ) - subtract;

				if ( val > 0.0 ) {

					cy = y * yd;

					for ( x = 0; x < size; x ++ ) {

						cxy = cy + x;

						for ( z = 0; z < size; z ++ ) field[ zd * z + cxy ] += val;

					}

				}

			}

		};

		/**
		 * Adds a plane along the z-axis.
		 *
		 * @param {number} strength - The strength factor.
		 * @param {number} subtract - The subtract factor.
		 */
		this.addPlaneZ = function ( strength, subtract ) {

			// cache attribute lookups

			const size = this.size,
				yd = this.yd,
				zd = this.zd,
				field = this.field;

			let x,
				y,
				z,
				zz,
				val,
				zdiv,
				cz,
				cyz,
				dist = size * Math.sqrt( strength / subtract );

			if ( dist > size ) dist = size;

			for ( z = 0; z < dist; z ++ ) {

				zdiv = z / size;
				zz = zdiv * zdiv;
				val = strength / ( 0.0001 + zz ) - subtract;
				if ( val > 0.0 ) {

					cz = zd * z;

					for ( y = 0; y < size; y ++ ) {

						cyz = cz + y * yd;

						for ( x = 0; x < size; x ++ ) field[ cyz + x ] += val;

					}

				}

			}

		};

		/////////////////////////////////////
		// Updates
		/////////////////////////////////////

		/**
		 * Sets the cell value for the given coordinates.
		 *
		 * @param {number} x - The x value.
		 * @param {number} y - The y value.
		 * @param {number} z - The z value.
		 * @param {number} value - The value to set.
		 */
		this.setCell = function ( x, y, z, value ) {

			const index = this.size2 * z + this.size * y + x;
			this.field[ index ] = value;

		};

		/**
		 * Returns the cell value for the given coordinates.
		 *
		 * @param {number} x - The x value.
		 * @param {number} y - The y value.
		 * @param {number} z - The z value.
		 * @return {number} The value.
		 */
		this.getCell = function ( x, y, z ) {

			const index = this.size2 * z + this.size * y + x;
			return this.field[ index ];

		};

		/**
		 * Applies a blur with the given intensity.
		 *
		 * @param {number} [intensity=1] - The intensity of the blur.
		 */
		this.blur = function ( intensity = 1 ) {

			const field = this.field;
			const fieldCopy = field.slice();
			const size = this.size;
			const size2 = this.size2;
			for ( let x = 0; x < size; x ++ ) {

				for ( let y = 0; y < size; y ++ ) {

					for ( let z = 0; z < size; z ++ ) {

						const index = size2 * z + size * y + x;
						let val = fieldCopy[ index ];
						let count = 1;

						for ( let x2 = - 1; x2 <= 1; x2 += 2 ) {

							const x3 = x2 + x;
							if ( x3 < 0 || x3 >= size ) continue;

							for ( let y2 = - 1; y2 <= 1; y2 += 2 ) {

								const y3 = y2 + y;
								if ( y3 < 0 || y3 >= size ) continue;

								for ( let z2 = - 1; z2 <= 1; z2 += 2 ) {

									const z3 = z2 + z;
									if ( z3 < 0 || z3 >= size ) continue;

									const index2 = size2 * z3 + size * y3 + x3;
									const val2 = fieldCopy[ index2 ];

									count ++;
									val += intensity * ( val2 - val ) / count;

								}

							}

						}

						field[ index ] = val;

					}

				}

			}

		};

		/**
		 * Resets the effect.
		 */
		this.reset = function () {

			// wipe the normal cache

			for ( let i = 0; i < this.size3; i ++ ) {

				this.normal_cache[ i * 3 ] = 0.0;
				this.field[ i ] = 0.0;
				this.palette[ i * 3 ] = this.palette[ i * 3 + 1 ] = this.palette[
					i * 3 + 2
				] = 0.0;

			}

		};

		/**
		 * Updates the effect.
		 */
		this.update = function () {

			this.count = 0;

			// Triangulate. Yeah, this is slow.

			const smin2 = this.size - 2;

			for ( let z = 1; z < smin2; z ++ ) {

				const z_offset = this.size2 * z;
				const fz = ( z - this.halfsize ) / this.halfsize; //+ 1

				for ( let y = 1; y < smin2; y ++ ) {

					const y_offset = z_offset + this.size * y;
					const fy = ( y - this.halfsize ) / this.halfsize; //+ 1

					for ( let x = 1; x < smin2; x ++ ) {

						const fx = ( x - this.halfsize ) / this.halfsize; //+ 1
						const q = y_offset + x;

						 polygonize( fx, fy, fz, q, this.isolation );

					}

				}

			}

			// set the draw range to only the processed triangles

			this.geometry.setDrawRange( 0, this.count );

			// update geometry data

			geometry.getAttribute( 'position' ).needsUpdate = true;
			geometry.getAttribute( 'normal' ).needsUpdate = true;

			if ( this.enableUvs ) geometry.getAttribute( 'uv' ).needsUpdate = true;
			if ( this.enableColors ) geometry.getAttribute( 'color' ).needsUpdate = true;

			// safety check

			if ( this.count / 3 > maxPolyCount ) console.warn( 'THREE.MarchingCubes: Geometry buffers too small for rendering. Please create an instance with a higher poly count.' );

		};

		this.init( resolution );

	}

}
```
</details>


---