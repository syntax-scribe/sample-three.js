[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `OBJLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 214 |
| 🧱 Classes | 1 |
| 📦 Imports | 15 |
| 📊 Variables & Constants | 69 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/OBJLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Group` | `three` |
| `LineBasicMaterial` | `three` |
| `LineSegments` | `three` |
| `Loader` | `three` |
| `Material` | `three` |
| `Mesh` | `three` |
| `MeshPhongMaterial` | `three` |
| `Points` | `three` |
| `PointsMaterial` | `three` |
| `Vector3` | `three` |
| `Color` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_object_pattern` | `RegExp` | let/var | `/^[og]\s*(.+)?/` | ✗ |
| `_material_library_pattern` | `RegExp` | let/var | `/^mtllib /` | ✗ |
| `_material_use_pattern` | `RegExp` | let/var | `/^usemtl /` | ✗ |
| `_map_use_pattern` | `RegExp` | let/var | `/^usemap /` | ✗ |
| `_face_vertex_data_separator...` | `RegExp` | let/var | `/\s+/` | ✗ |
| `_vA` | `any` | let/var | `new Vector3()` | ✗ |
| `_vB` | `any` | let/var | `new Vector3()` | ✗ |
| `_vC` | `any` | let/var | `new Vector3()` | ✗ |
| `_ab` | `any` | let/var | `new Vector3()` | ✗ |
| `_cb` | `any` | let/var | `new Vector3()` | ✗ |
| `_color` | `any` | let/var | `new Color()` | ✗ |
| `previousMaterial` | `any` | let/var | `( this.object && typeof this.object.currentMaterial === 'function' ? this.obj...` | ✗ |
| `cloned` | `{ index: number; name: any; mtllib: a...` | let/var | `{ index: ( typeof index === 'number' ? index : this.index ), name: this.name,...` | ✗ |
| `material` | `{ index: number; name: any; mtllib: a...` | let/var | `{ index: this.materials.length, name: name \|\| '', mtllib: ( Array.isArray( ...` | ✗ |
| `src` | `any[]` | let/var | `this.vertices` | ✗ |
| `dst` | `any` | let/var | `this.object.geometry.vertices` | ✗ |
| `src` | `any[]` | let/var | `this.vertices` | ✗ |
| `dst` | `any` | let/var | `this.object.geometry.vertices` | ✗ |
| `src` | `any[]` | let/var | `this.vertices` | ✗ |
| `dst` | `any` | let/var | `this.object.geometry.vertices` | ✗ |
| `src` | `any[]` | let/var | `this.normals` | ✗ |
| `dst` | `any` | let/var | `this.object.geometry.normals` | ✗ |
| `src` | `any[]` | let/var | `this.vertices` | ✗ |
| `dst` | `any` | let/var | `this.object.geometry.normals` | ✗ |
| `src` | `any[]` | let/var | `this.colors` | ✗ |
| `dst` | `any` | let/var | `this.object.geometry.colors` | ✗ |
| `src` | `any[]` | let/var | `this.uvs` | ✗ |
| `dst` | `any` | let/var | `this.object.geometry.uvs` | ✗ |
| `dst` | `any` | let/var | `this.object.geometry.uvs` | ✗ |
| `src` | `any[]` | let/var | `this.uvs` | ✗ |
| `dst` | `any` | let/var | `this.object.geometry.uvs` | ✗ |
| `vLen` | `number` | let/var | `this.vertices.length` | ✗ |
| `nLen` | `number` | let/var | `this.normals.length` | ✗ |
| `uvLen` | `number` | let/var | `this.uvs.length` | ✗ |
| `vLen` | `number` | let/var | `this.vertices.length` | ✗ |
| `vLen` | `number` | let/var | `this.vertices.length` | ✗ |
| `uvLen` | `number` | let/var | `this.uvs.length` | ✗ |
| `state` | `{ objects: any[]; object: {}; vertice...` | let/var | `{ objects: [], object: {}, vertices: [], normals: [], colors: [], uvs: [], ma...` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `state` | `any` | let/var | `new ParserState()` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `faceVertices` | `any[]` | let/var | `[]` | ✗ |
| `vertex` | `string` | let/var | `vertexData[ j ]` | ✗ |
| `v1` | `string[]` | let/var | `faceVertices[ 0 ]` | ✗ |
| `v2` | `string[]` | let/var | `faceVertices[ j ]` | ✗ |
| `v3` | `string[]` | let/var | `faceVertices[ j + 1 ]` | ✗ |
| `lineVertices` | `any[]` | let/var | `[]` | ✗ |
| `lineUVs` | `any[]` | let/var | `[]` | ✗ |
| `container` | `any` | let/var | `new Group()` | ✗ |
| `hasPrimitives` | `boolean` | let/var | `! ( state.objects.length === 1 && state.objects[ 0 ].geometry.vertices.length...` | ✗ |
| `object` | `any` | let/var | `state.objects[ i ]` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `materials` | `any` | let/var | `object.materials` | ✗ |
| `isLine` | `boolean` | let/var | `( geometry.type === 'Line' )` | ✗ |
| `isPoints` | `boolean` | let/var | `( geometry.type === 'Points' )` | ✗ |
| `hasVertexColors` | `boolean` | let/var | `false` | ✗ |
| `buffergeometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `createdMaterials` | `any[]` | let/var | `[]` | ✗ |
| `sourceMaterial` | `any` | let/var | `materials[ mi ]` | ✗ |
| `materialHash` | `string` | let/var | `sourceMaterial.name + '_' + sourceMaterial.smooth + '_' + hasVertexColors` | ✗ |
| `material` | `any` | let/var | `state.materials[ materialHash ]` | ✗ |
| `materialLine` | `any` | let/var | `new LineBasicMaterial()` | ✗ |
| `materialPoints` | `any` | let/var | `new PointsMaterial( { size: 10, sizeAttenuation: false } )` | ✗ |
| `mesh` | `any` | let/var | `*not shown*` | ✗ |
| `sourceMaterial` | `any` | let/var | `materials[ mi ]` | ✗ |
| `material` | `any` | let/var | `new PointsMaterial( { size: 1, sizeAttenuation: false } )` | ✗ |
| `buffergeometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `points` | `any` | let/var | `new Points( buffergeometry, material )` | ✗ |


---

## Functions

### `ParserState(): { objects: any[]; object: {}; vertices: any[]; normals: any[]; colors: any[]; uvs: any[]; materials: {}; materialLibraries: any[]; startObject: typeof startObject; finalize: () => void; parseVertexIndex: (value: any, len: any) => number; ... 13 more ...; addLineGeometry: (vertices: any, uvs: any) => void; }`

**Returns:** `{ objects: any[]; object: {}; vertices: any[]; normals: any[]; colors: any[]; uvs: any[]; materials: {}; materialLibraries: any[]; startObject: typeof startObject; finalize: () => void; parseVertexIndex: (value: any, len: any) => number; ... 13 more ...; addLineGeometry: (vertices: any, uvs: any) => void; }`

**Calls:**

- `this.object.currentMaterial`
- `this.object._finalize`
- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`
- `this.currentMaterial`
- `previousMaterial.clone`
- `this.object.materials.push`
- `this.objects.push`
- `parseInt`
- `dst.push`
- `_vA.fromArray`
- `_vB.fromArray`
- `_vC.fromArray`
- `_cb.subVectors`
- `_ab.subVectors`
- `_cb.cross`
- `_cb.normalize`
- `this.parseVertexIndex`
- `this.addVertex`
- `this.addColor`
- `this.parseNormalIndex`
- `this.addNormal`
- `this.addFaceNormal`
- `this.parseUVIndex`
- `this.addUV`
- `this.addDefaultUV`
- `this.addVertexPoint`
- `this.addVertexLine`
- `this.addUVLine`
- `state.startObject`

**Internal Comments:**
```
// If the current object (initial from reset) is not from a g/o declaration in the parsed
// file. We need to use it for the first parsed g/o to keep things in sync.
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
// Inherit previous objects material.
// Spec tells us that a declared material must be set to all objects until a new material is declared.
// If a usemtl declaration is encountered while this new object is being parsed, it will
// overwrite the inherited material. Exception being that there was already face declarations
// to the inherited material, then it will be preserved for proper MultiMaterial continuation.
// normals
// uvs
// add placeholder values (for inconsistent face definitions) (x4)
```

<details><summary>Code</summary>

```typescript
function ParserState() {

	const state = {
		objects: [],
		object: {},

		vertices: [],
		normals: [],
		colors: [],
		uvs: [],

		materials: {},
		materialLibraries: [],

		startObject: function ( name, fromDeclaration ) {

			// If the current object (initial from reset) is not from a g/o declaration in the parsed
			// file. We need to use it for the first parsed g/o to keep things in sync.
			if ( this.object && this.object.fromDeclaration === false ) {

				this.object.name = name;
				this.object.fromDeclaration = ( fromDeclaration !== false );
				return;

			}

			const previousMaterial = ( this.object && typeof this.object.currentMaterial === 'function' ? this.object.currentMaterial() : undefined );

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

			this.object = {
				name: name || '',
				fromDeclaration: ( fromDeclaration !== false ),

				geometry: {
					vertices: [],
					normals: [],
					colors: [],
					uvs: [],
					hasUVIndices: false
				},
				materials: [],
				smooth: true,

				startMaterial: function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				},

				currentMaterial: function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				},

				_finalize: function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
			};

			// Inherit previous objects material.
			// Spec tells us that a declared material must be set to all objects until a new material is declared.
			// If a usemtl declaration is encountered while this new object is being parsed, it will
			// overwrite the inherited material. Exception being that there was already face declarations
			// to the inherited material, then it will be preserved for proper MultiMaterial continuation.

			if ( previousMaterial && previousMaterial.name && typeof previousMaterial.clone === 'function' ) {

				const declared = previousMaterial.clone( 0 );
				declared.inherited = true;
				this.object.materials.push( declared );

			}

			this.objects.push( this.object );

		},

		finalize: function () {

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

		},

		parseVertexIndex: function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		},

		parseNormalIndex: function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		},

		parseUVIndex: function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 2 ) * 2;

		},

		addVertex: function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		},

		addVertexPoint: function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		},

		addVertexLine: function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		},

		addNormal: function ( a, b, c ) {

			const src = this.normals;
			const dst = this.object.geometry.normals;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		},

		addFaceNormal: function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.normals;

			_vA.fromArray( src, a );
			_vB.fromArray( src, b );
			_vC.fromArray( src, c );

			_cb.subVectors( _vC, _vB );
			_ab.subVectors( _vA, _vB );
			_cb.cross( _ab );

			_cb.normalize();

			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );

		},

		addColor: function ( a, b, c ) {

			const src = this.colors;
			const dst = this.object.geometry.colors;

			if ( src[ a ] !== undefined ) dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			if ( src[ b ] !== undefined ) dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			if ( src[ c ] !== undefined ) dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		},

		addUV: function ( a, b, c ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ] );

		},

		addDefaultUV: function () {

			const dst = this.object.geometry.uvs;

			dst.push( 0, 0 );
			dst.push( 0, 0 );
			dst.push( 0, 0 );

		},

		addUVLine: function ( a ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );

		},

		addFace: function ( a, b, c, ua, ub, uc, na, nb, nc ) {

			const vLen = this.vertices.length;

			let ia = this.parseVertexIndex( a, vLen );
			let ib = this.parseVertexIndex( b, vLen );
			let ic = this.parseVertexIndex( c, vLen );

			this.addVertex( ia, ib, ic );
			this.addColor( ia, ib, ic );

			// normals

			if ( na !== undefined && na !== '' ) {

				const nLen = this.normals.length;

				ia = this.parseNormalIndex( na, nLen );
				ib = this.parseNormalIndex( nb, nLen );
				ic = this.parseNormalIndex( nc, nLen );

				this.addNormal( ia, ib, ic );

			} else {

				this.addFaceNormal( ia, ib, ic );

			}

			// uvs

			if ( ua !== undefined && ua !== '' ) {

				const uvLen = this.uvs.length;

				ia = this.parseUVIndex( ua, uvLen );
				ib = this.parseUVIndex( ub, uvLen );
				ic = this.parseUVIndex( uc, uvLen );

				this.addUV( ia, ib, ic );

				this.object.geometry.hasUVIndices = true;

			} else {

				// add placeholder values (for inconsistent face definitions)

				this.addDefaultUV();

			}

		},

		addPointGeometry: function ( vertices ) {

			this.object.geometry.type = 'Points';

			const vLen = this.vertices.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				const index = this.parseVertexIndex( vertices[ vi ], vLen );

				this.addVertexPoint( index );
				this.addColor( index );

			}

		},

		addLineGeometry: function ( vertices, uvs ) {

			this.object.geometry.type = 'Line';

			const vLen = this.vertices.length;
			const uvLen = this.uvs.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				this.addVertexLine( this.parseVertexIndex( vertices[ vi ], vLen ) );

			}

			for ( let uvi = 0, l = uvs.length; uvi < l; uvi ++ ) {

				this.addUVLine( this.parseUVIndex( uvs[ uvi ], uvLen ) );

			}

		}

	};

	state.startObject( '', false );

	return state;

}
```
</details>

### `startObject(name: any, fromDeclaration: any): void`

**Parameters:**

- **`name`** `any`
- **`fromDeclaration`** `any`

**Returns:** `void`

**Calls:**

- `this.object.currentMaterial`
- `this.object._finalize`
- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`
- `this.currentMaterial`
- `previousMaterial.clone`
- `this.object.materials.push`
- `this.objects.push`

**Internal Comments:**
```
// If the current object (initial from reset) is not from a g/o declaration in the parsed
// file. We need to use it for the first parsed g/o to keep things in sync.
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
// Inherit previous objects material.
// Spec tells us that a declared material must be set to all objects until a new material is declared.
// If a usemtl declaration is encountered while this new object is being parsed, it will
// overwrite the inherited material. Exception being that there was already face declarations
// to the inherited material, then it will be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, fromDeclaration ) {

			// If the current object (initial from reset) is not from a g/o declaration in the parsed
			// file. We need to use it for the first parsed g/o to keep things in sync.
			if ( this.object && this.object.fromDeclaration === false ) {

				this.object.name = name;
				this.object.fromDeclaration = ( fromDeclaration !== false );
				return;

			}

			const previousMaterial = ( this.object && typeof this.object.currentMaterial === 'function' ? this.object.currentMaterial() : undefined );

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

			this.object = {
				name: name || '',
				fromDeclaration: ( fromDeclaration !== false ),

				geometry: {
					vertices: [],
					normals: [],
					colors: [],
					uvs: [],
					hasUVIndices: false
				},
				materials: [],
				smooth: true,

				startMaterial: function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				},

				currentMaterial: function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				},

				_finalize: function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
			};

			// Inherit previous objects material.
			// Spec tells us that a declared material must be set to all objects until a new material is declared.
			// If a usemtl declaration is encountered while this new object is being parsed, it will
			// overwrite the inherited material. Exception being that there was already face declarations
			// to the inherited material, then it will be preserved for proper MultiMaterial continuation.

			if ( previousMaterial && previousMaterial.name && typeof previousMaterial.clone === 'function' ) {

				const declared = previousMaterial.clone( 0 );
				declared.inherited = true;
				this.object.materials.push( declared );

			}

			this.objects.push( this.object );

		}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `finalize(): void`

**Returns:** `void`

**Calls:**

- `this.object._finalize`

<details><summary>Code</summary>

```typescript
function () {

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

		}
```
</details>

### `parseVertexIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseNormalIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseUVIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 2 ) * 2;

		}
```
</details>

### `addVertex(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addVertexPoint(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addVertexLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.normals;
			const dst = this.object.geometry.normals;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addFaceNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `_vA.fromArray`
- `_vB.fromArray`
- `_vC.fromArray`
- `_cb.subVectors`
- `_ab.subVectors`
- `_cb.cross`
- `_cb.normalize`
- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.normals;

			_vA.fromArray( src, a );
			_vB.fromArray( src, b );
			_vC.fromArray( src, c );

			_cb.subVectors( _vC, _vB );
			_ab.subVectors( _vA, _vB );
			_cb.cross( _ab );

			_cb.normalize();

			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );

		}
```
</details>

### `addColor(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.colors;
			const dst = this.object.geometry.colors;

			if ( src[ a ] !== undefined ) dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			if ( src[ b ] !== undefined ) dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			if ( src[ c ] !== undefined ) dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addUV(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ] );

		}
```
</details>

### `addDefaultUV(): void`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function () {

			const dst = this.object.geometry.uvs;

			dst.push( 0, 0 );
			dst.push( 0, 0 );
			dst.push( 0, 0 );

		}
```
</details>

### `addUVLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );

		}
```
</details>

### `addFace(a: any, b: any, c: any, ua: any, ub: any, uc: any, na: any, nb: any, nc: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`ua`** `any`
- **`ub`** `any`
- **`uc`** `any`
- **`na`** `any`
- **`nb`** `any`
- **`nc`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertex`
- `this.addColor`
- `this.parseNormalIndex`
- `this.addNormal`
- `this.addFaceNormal`
- `this.parseUVIndex`
- `this.addUV`
- `this.addDefaultUV`

**Internal Comments:**
```
// normals
// uvs
// add placeholder values (for inconsistent face definitions) (x4)
```

<details><summary>Code</summary>

```typescript
function ( a, b, c, ua, ub, uc, na, nb, nc ) {

			const vLen = this.vertices.length;

			let ia = this.parseVertexIndex( a, vLen );
			let ib = this.parseVertexIndex( b, vLen );
			let ic = this.parseVertexIndex( c, vLen );

			this.addVertex( ia, ib, ic );
			this.addColor( ia, ib, ic );

			// normals

			if ( na !== undefined && na !== '' ) {

				const nLen = this.normals.length;

				ia = this.parseNormalIndex( na, nLen );
				ib = this.parseNormalIndex( nb, nLen );
				ic = this.parseNormalIndex( nc, nLen );

				this.addNormal( ia, ib, ic );

			} else {

				this.addFaceNormal( ia, ib, ic );

			}

			// uvs

			if ( ua !== undefined && ua !== '' ) {

				const uvLen = this.uvs.length;

				ia = this.parseUVIndex( ua, uvLen );
				ib = this.parseUVIndex( ub, uvLen );
				ic = this.parseUVIndex( uc, uvLen );

				this.addUV( ia, ib, ic );

				this.object.geometry.hasUVIndices = true;

			} else {

				// add placeholder values (for inconsistent face definitions)

				this.addDefaultUV();

			}

		}
```
</details>

### `addPointGeometry(vertices: any): void`

**Parameters:**

- **`vertices`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertexPoint`
- `this.addColor`

<details><summary>Code</summary>

```typescript
function ( vertices ) {

			this.object.geometry.type = 'Points';

			const vLen = this.vertices.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				const index = this.parseVertexIndex( vertices[ vi ], vLen );

				this.addVertexPoint( index );
				this.addColor( index );

			}

		}
```
</details>

### `addLineGeometry(vertices: any, uvs: any): void`

**Parameters:**

- **`vertices`** `any`
- **`uvs`** `any`

**Returns:** `void`

**Calls:**

- `this.addVertexLine`
- `this.parseVertexIndex`
- `this.addUVLine`
- `this.parseUVIndex`

<details><summary>Code</summary>

```typescript
function ( vertices, uvs ) {

			this.object.geometry.type = 'Line';

			const vLen = this.vertices.length;
			const uvLen = this.uvs.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				this.addVertexLine( this.parseVertexIndex( vertices[ vi ], vLen ) );

			}

			for ( let uvi = 0, l = uvs.length; uvi < l; uvi ++ ) {

				this.addUVLine( this.parseUVIndex( uvs[ uvi ], uvLen ) );

			}

		}
```
</details>

### `startObject(name: any, fromDeclaration: any): void`

**Parameters:**

- **`name`** `any`
- **`fromDeclaration`** `any`

**Returns:** `void`

**Calls:**

- `this.object.currentMaterial`
- `this.object._finalize`
- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`
- `this.currentMaterial`
- `previousMaterial.clone`
- `this.object.materials.push`
- `this.objects.push`

**Internal Comments:**
```
// If the current object (initial from reset) is not from a g/o declaration in the parsed
// file. We need to use it for the first parsed g/o to keep things in sync.
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
// Inherit previous objects material.
// Spec tells us that a declared material must be set to all objects until a new material is declared.
// If a usemtl declaration is encountered while this new object is being parsed, it will
// overwrite the inherited material. Exception being that there was already face declarations
// to the inherited material, then it will be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, fromDeclaration ) {

			// If the current object (initial from reset) is not from a g/o declaration in the parsed
			// file. We need to use it for the first parsed g/o to keep things in sync.
			if ( this.object && this.object.fromDeclaration === false ) {

				this.object.name = name;
				this.object.fromDeclaration = ( fromDeclaration !== false );
				return;

			}

			const previousMaterial = ( this.object && typeof this.object.currentMaterial === 'function' ? this.object.currentMaterial() : undefined );

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

			this.object = {
				name: name || '',
				fromDeclaration: ( fromDeclaration !== false ),

				geometry: {
					vertices: [],
					normals: [],
					colors: [],
					uvs: [],
					hasUVIndices: false
				},
				materials: [],
				smooth: true,

				startMaterial: function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				},

				currentMaterial: function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				},

				_finalize: function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
			};

			// Inherit previous objects material.
			// Spec tells us that a declared material must be set to all objects until a new material is declared.
			// If a usemtl declaration is encountered while this new object is being parsed, it will
			// overwrite the inherited material. Exception being that there was already face declarations
			// to the inherited material, then it will be preserved for proper MultiMaterial continuation.

			if ( previousMaterial && previousMaterial.name && typeof previousMaterial.clone === 'function' ) {

				const declared = previousMaterial.clone( 0 );
				declared.inherited = true;
				this.object.materials.push( declared );

			}

			this.objects.push( this.object );

		}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `finalize(): void`

**Returns:** `void`

**Calls:**

- `this.object._finalize`

<details><summary>Code</summary>

```typescript
function () {

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

		}
```
</details>

### `parseVertexIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseNormalIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseUVIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 2 ) * 2;

		}
```
</details>

### `addVertex(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addVertexPoint(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addVertexLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.normals;
			const dst = this.object.geometry.normals;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addFaceNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `_vA.fromArray`
- `_vB.fromArray`
- `_vC.fromArray`
- `_cb.subVectors`
- `_ab.subVectors`
- `_cb.cross`
- `_cb.normalize`
- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.normals;

			_vA.fromArray( src, a );
			_vB.fromArray( src, b );
			_vC.fromArray( src, c );

			_cb.subVectors( _vC, _vB );
			_ab.subVectors( _vA, _vB );
			_cb.cross( _ab );

			_cb.normalize();

			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );

		}
```
</details>

### `addColor(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.colors;
			const dst = this.object.geometry.colors;

			if ( src[ a ] !== undefined ) dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			if ( src[ b ] !== undefined ) dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			if ( src[ c ] !== undefined ) dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addUV(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ] );

		}
```
</details>

### `addDefaultUV(): void`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function () {

			const dst = this.object.geometry.uvs;

			dst.push( 0, 0 );
			dst.push( 0, 0 );
			dst.push( 0, 0 );

		}
```
</details>

### `addUVLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );

		}
```
</details>

### `addFace(a: any, b: any, c: any, ua: any, ub: any, uc: any, na: any, nb: any, nc: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`ua`** `any`
- **`ub`** `any`
- **`uc`** `any`
- **`na`** `any`
- **`nb`** `any`
- **`nc`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertex`
- `this.addColor`
- `this.parseNormalIndex`
- `this.addNormal`
- `this.addFaceNormal`
- `this.parseUVIndex`
- `this.addUV`
- `this.addDefaultUV`

**Internal Comments:**
```
// normals
// uvs
// add placeholder values (for inconsistent face definitions) (x4)
```

<details><summary>Code</summary>

```typescript
function ( a, b, c, ua, ub, uc, na, nb, nc ) {

			const vLen = this.vertices.length;

			let ia = this.parseVertexIndex( a, vLen );
			let ib = this.parseVertexIndex( b, vLen );
			let ic = this.parseVertexIndex( c, vLen );

			this.addVertex( ia, ib, ic );
			this.addColor( ia, ib, ic );

			// normals

			if ( na !== undefined && na !== '' ) {

				const nLen = this.normals.length;

				ia = this.parseNormalIndex( na, nLen );
				ib = this.parseNormalIndex( nb, nLen );
				ic = this.parseNormalIndex( nc, nLen );

				this.addNormal( ia, ib, ic );

			} else {

				this.addFaceNormal( ia, ib, ic );

			}

			// uvs

			if ( ua !== undefined && ua !== '' ) {

				const uvLen = this.uvs.length;

				ia = this.parseUVIndex( ua, uvLen );
				ib = this.parseUVIndex( ub, uvLen );
				ic = this.parseUVIndex( uc, uvLen );

				this.addUV( ia, ib, ic );

				this.object.geometry.hasUVIndices = true;

			} else {

				// add placeholder values (for inconsistent face definitions)

				this.addDefaultUV();

			}

		}
```
</details>

### `addPointGeometry(vertices: any): void`

**Parameters:**

- **`vertices`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertexPoint`
- `this.addColor`

<details><summary>Code</summary>

```typescript
function ( vertices ) {

			this.object.geometry.type = 'Points';

			const vLen = this.vertices.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				const index = this.parseVertexIndex( vertices[ vi ], vLen );

				this.addVertexPoint( index );
				this.addColor( index );

			}

		}
```
</details>

### `addLineGeometry(vertices: any, uvs: any): void`

**Parameters:**

- **`vertices`** `any`
- **`uvs`** `any`

**Returns:** `void`

**Calls:**

- `this.addVertexLine`
- `this.parseVertexIndex`
- `this.addUVLine`
- `this.parseUVIndex`

<details><summary>Code</summary>

```typescript
function ( vertices, uvs ) {

			this.object.geometry.type = 'Line';

			const vLen = this.vertices.length;
			const uvLen = this.uvs.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				this.addVertexLine( this.parseVertexIndex( vertices[ vi ], vLen ) );

			}

			for ( let uvi = 0, l = uvs.length; uvi < l; uvi ++ ) {

				this.addUVLine( this.parseUVIndex( uvs[ uvi ], uvLen ) );

			}

		}
```
</details>

### `startObject(name: any, fromDeclaration: any): void`

**Parameters:**

- **`name`** `any`
- **`fromDeclaration`** `any`

**Returns:** `void`

**Calls:**

- `this.object.currentMaterial`
- `this.object._finalize`
- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`
- `this.currentMaterial`
- `previousMaterial.clone`
- `this.object.materials.push`
- `this.objects.push`

**Internal Comments:**
```
// If the current object (initial from reset) is not from a g/o declaration in the parsed
// file. We need to use it for the first parsed g/o to keep things in sync.
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
// Inherit previous objects material.
// Spec tells us that a declared material must be set to all objects until a new material is declared.
// If a usemtl declaration is encountered while this new object is being parsed, it will
// overwrite the inherited material. Exception being that there was already face declarations
// to the inherited material, then it will be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, fromDeclaration ) {

			// If the current object (initial from reset) is not from a g/o declaration in the parsed
			// file. We need to use it for the first parsed g/o to keep things in sync.
			if ( this.object && this.object.fromDeclaration === false ) {

				this.object.name = name;
				this.object.fromDeclaration = ( fromDeclaration !== false );
				return;

			}

			const previousMaterial = ( this.object && typeof this.object.currentMaterial === 'function' ? this.object.currentMaterial() : undefined );

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

			this.object = {
				name: name || '',
				fromDeclaration: ( fromDeclaration !== false ),

				geometry: {
					vertices: [],
					normals: [],
					colors: [],
					uvs: [],
					hasUVIndices: false
				},
				materials: [],
				smooth: true,

				startMaterial: function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				},

				currentMaterial: function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				},

				_finalize: function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
			};

			// Inherit previous objects material.
			// Spec tells us that a declared material must be set to all objects until a new material is declared.
			// If a usemtl declaration is encountered while this new object is being parsed, it will
			// overwrite the inherited material. Exception being that there was already face declarations
			// to the inherited material, then it will be preserved for proper MultiMaterial continuation.

			if ( previousMaterial && previousMaterial.name && typeof previousMaterial.clone === 'function' ) {

				const declared = previousMaterial.clone( 0 );
				declared.inherited = true;
				this.object.materials.push( declared );

			}

			this.objects.push( this.object );

		}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `finalize(): void`

**Returns:** `void`

**Calls:**

- `this.object._finalize`

<details><summary>Code</summary>

```typescript
function () {

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

		}
```
</details>

### `parseVertexIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseNormalIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseUVIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 2 ) * 2;

		}
```
</details>

### `addVertex(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addVertexPoint(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addVertexLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.normals;
			const dst = this.object.geometry.normals;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addFaceNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `_vA.fromArray`
- `_vB.fromArray`
- `_vC.fromArray`
- `_cb.subVectors`
- `_ab.subVectors`
- `_cb.cross`
- `_cb.normalize`
- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.normals;

			_vA.fromArray( src, a );
			_vB.fromArray( src, b );
			_vC.fromArray( src, c );

			_cb.subVectors( _vC, _vB );
			_ab.subVectors( _vA, _vB );
			_cb.cross( _ab );

			_cb.normalize();

			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );

		}
```
</details>

### `addColor(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.colors;
			const dst = this.object.geometry.colors;

			if ( src[ a ] !== undefined ) dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			if ( src[ b ] !== undefined ) dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			if ( src[ c ] !== undefined ) dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addUV(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ] );

		}
```
</details>

### `addDefaultUV(): void`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function () {

			const dst = this.object.geometry.uvs;

			dst.push( 0, 0 );
			dst.push( 0, 0 );
			dst.push( 0, 0 );

		}
```
</details>

### `addUVLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );

		}
```
</details>

### `addFace(a: any, b: any, c: any, ua: any, ub: any, uc: any, na: any, nb: any, nc: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`ua`** `any`
- **`ub`** `any`
- **`uc`** `any`
- **`na`** `any`
- **`nb`** `any`
- **`nc`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertex`
- `this.addColor`
- `this.parseNormalIndex`
- `this.addNormal`
- `this.addFaceNormal`
- `this.parseUVIndex`
- `this.addUV`
- `this.addDefaultUV`

**Internal Comments:**
```
// normals
// uvs
// add placeholder values (for inconsistent face definitions) (x4)
```

<details><summary>Code</summary>

```typescript
function ( a, b, c, ua, ub, uc, na, nb, nc ) {

			const vLen = this.vertices.length;

			let ia = this.parseVertexIndex( a, vLen );
			let ib = this.parseVertexIndex( b, vLen );
			let ic = this.parseVertexIndex( c, vLen );

			this.addVertex( ia, ib, ic );
			this.addColor( ia, ib, ic );

			// normals

			if ( na !== undefined && na !== '' ) {

				const nLen = this.normals.length;

				ia = this.parseNormalIndex( na, nLen );
				ib = this.parseNormalIndex( nb, nLen );
				ic = this.parseNormalIndex( nc, nLen );

				this.addNormal( ia, ib, ic );

			} else {

				this.addFaceNormal( ia, ib, ic );

			}

			// uvs

			if ( ua !== undefined && ua !== '' ) {

				const uvLen = this.uvs.length;

				ia = this.parseUVIndex( ua, uvLen );
				ib = this.parseUVIndex( ub, uvLen );
				ic = this.parseUVIndex( uc, uvLen );

				this.addUV( ia, ib, ic );

				this.object.geometry.hasUVIndices = true;

			} else {

				// add placeholder values (for inconsistent face definitions)

				this.addDefaultUV();

			}

		}
```
</details>

### `addPointGeometry(vertices: any): void`

**Parameters:**

- **`vertices`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertexPoint`
- `this.addColor`

<details><summary>Code</summary>

```typescript
function ( vertices ) {

			this.object.geometry.type = 'Points';

			const vLen = this.vertices.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				const index = this.parseVertexIndex( vertices[ vi ], vLen );

				this.addVertexPoint( index );
				this.addColor( index );

			}

		}
```
</details>

### `addLineGeometry(vertices: any, uvs: any): void`

**Parameters:**

- **`vertices`** `any`
- **`uvs`** `any`

**Returns:** `void`

**Calls:**

- `this.addVertexLine`
- `this.parseVertexIndex`
- `this.addUVLine`
- `this.parseUVIndex`

<details><summary>Code</summary>

```typescript
function ( vertices, uvs ) {

			this.object.geometry.type = 'Line';

			const vLen = this.vertices.length;
			const uvLen = this.uvs.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				this.addVertexLine( this.parseVertexIndex( vertices[ vi ], vLen ) );

			}

			for ( let uvi = 0, l = uvs.length; uvi < l; uvi ++ ) {

				this.addUVLine( this.parseUVIndex( uvs[ uvi ], uvLen ) );

			}

		}
```
</details>

### `startObject(name: any, fromDeclaration: any): void`

**Parameters:**

- **`name`** `any`
- **`fromDeclaration`** `any`

**Returns:** `void`

**Calls:**

- `this.object.currentMaterial`
- `this.object._finalize`
- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`
- `this.currentMaterial`
- `previousMaterial.clone`
- `this.object.materials.push`
- `this.objects.push`

**Internal Comments:**
```
// If the current object (initial from reset) is not from a g/o declaration in the parsed
// file. We need to use it for the first parsed g/o to keep things in sync.
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
// Inherit previous objects material.
// Spec tells us that a declared material must be set to all objects until a new material is declared.
// If a usemtl declaration is encountered while this new object is being parsed, it will
// overwrite the inherited material. Exception being that there was already face declarations
// to the inherited material, then it will be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, fromDeclaration ) {

			// If the current object (initial from reset) is not from a g/o declaration in the parsed
			// file. We need to use it for the first parsed g/o to keep things in sync.
			if ( this.object && this.object.fromDeclaration === false ) {

				this.object.name = name;
				this.object.fromDeclaration = ( fromDeclaration !== false );
				return;

			}

			const previousMaterial = ( this.object && typeof this.object.currentMaterial === 'function' ? this.object.currentMaterial() : undefined );

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

			this.object = {
				name: name || '',
				fromDeclaration: ( fromDeclaration !== false ),

				geometry: {
					vertices: [],
					normals: [],
					colors: [],
					uvs: [],
					hasUVIndices: false
				},
				materials: [],
				smooth: true,

				startMaterial: function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				},

				currentMaterial: function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				},

				_finalize: function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
			};

			// Inherit previous objects material.
			// Spec tells us that a declared material must be set to all objects until a new material is declared.
			// If a usemtl declaration is encountered while this new object is being parsed, it will
			// overwrite the inherited material. Exception being that there was already face declarations
			// to the inherited material, then it will be preserved for proper MultiMaterial continuation.

			if ( previousMaterial && previousMaterial.name && typeof previousMaterial.clone === 'function' ) {

				const declared = previousMaterial.clone( 0 );
				declared.inherited = true;
				this.object.materials.push( declared );

			}

			this.objects.push( this.object );

		}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `finalize(): void`

**Returns:** `void`

**Calls:**

- `this.object._finalize`

<details><summary>Code</summary>

```typescript
function () {

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

		}
```
</details>

### `parseVertexIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseNormalIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseUVIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 2 ) * 2;

		}
```
</details>

### `addVertex(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addVertexPoint(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addVertexLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.normals;
			const dst = this.object.geometry.normals;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addFaceNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `_vA.fromArray`
- `_vB.fromArray`
- `_vC.fromArray`
- `_cb.subVectors`
- `_ab.subVectors`
- `_cb.cross`
- `_cb.normalize`
- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.normals;

			_vA.fromArray( src, a );
			_vB.fromArray( src, b );
			_vC.fromArray( src, c );

			_cb.subVectors( _vC, _vB );
			_ab.subVectors( _vA, _vB );
			_cb.cross( _ab );

			_cb.normalize();

			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );

		}
```
</details>

### `addColor(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.colors;
			const dst = this.object.geometry.colors;

			if ( src[ a ] !== undefined ) dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			if ( src[ b ] !== undefined ) dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			if ( src[ c ] !== undefined ) dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addUV(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ] );

		}
```
</details>

### `addDefaultUV(): void`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function () {

			const dst = this.object.geometry.uvs;

			dst.push( 0, 0 );
			dst.push( 0, 0 );
			dst.push( 0, 0 );

		}
```
</details>

### `addUVLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );

		}
```
</details>

### `addFace(a: any, b: any, c: any, ua: any, ub: any, uc: any, na: any, nb: any, nc: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`ua`** `any`
- **`ub`** `any`
- **`uc`** `any`
- **`na`** `any`
- **`nb`** `any`
- **`nc`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertex`
- `this.addColor`
- `this.parseNormalIndex`
- `this.addNormal`
- `this.addFaceNormal`
- `this.parseUVIndex`
- `this.addUV`
- `this.addDefaultUV`

**Internal Comments:**
```
// normals
// uvs
// add placeholder values (for inconsistent face definitions) (x4)
```

<details><summary>Code</summary>

```typescript
function ( a, b, c, ua, ub, uc, na, nb, nc ) {

			const vLen = this.vertices.length;

			let ia = this.parseVertexIndex( a, vLen );
			let ib = this.parseVertexIndex( b, vLen );
			let ic = this.parseVertexIndex( c, vLen );

			this.addVertex( ia, ib, ic );
			this.addColor( ia, ib, ic );

			// normals

			if ( na !== undefined && na !== '' ) {

				const nLen = this.normals.length;

				ia = this.parseNormalIndex( na, nLen );
				ib = this.parseNormalIndex( nb, nLen );
				ic = this.parseNormalIndex( nc, nLen );

				this.addNormal( ia, ib, ic );

			} else {

				this.addFaceNormal( ia, ib, ic );

			}

			// uvs

			if ( ua !== undefined && ua !== '' ) {

				const uvLen = this.uvs.length;

				ia = this.parseUVIndex( ua, uvLen );
				ib = this.parseUVIndex( ub, uvLen );
				ic = this.parseUVIndex( uc, uvLen );

				this.addUV( ia, ib, ic );

				this.object.geometry.hasUVIndices = true;

			} else {

				// add placeholder values (for inconsistent face definitions)

				this.addDefaultUV();

			}

		}
```
</details>

### `addPointGeometry(vertices: any): void`

**Parameters:**

- **`vertices`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertexPoint`
- `this.addColor`

<details><summary>Code</summary>

```typescript
function ( vertices ) {

			this.object.geometry.type = 'Points';

			const vLen = this.vertices.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				const index = this.parseVertexIndex( vertices[ vi ], vLen );

				this.addVertexPoint( index );
				this.addColor( index );

			}

		}
```
</details>

### `addLineGeometry(vertices: any, uvs: any): void`

**Parameters:**

- **`vertices`** `any`
- **`uvs`** `any`

**Returns:** `void`

**Calls:**

- `this.addVertexLine`
- `this.parseVertexIndex`
- `this.addUVLine`
- `this.parseUVIndex`

<details><summary>Code</summary>

```typescript
function ( vertices, uvs ) {

			this.object.geometry.type = 'Line';

			const vLen = this.vertices.length;
			const uvLen = this.uvs.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				this.addVertexLine( this.parseVertexIndex( vertices[ vi ], vLen ) );

			}

			for ( let uvi = 0, l = uvs.length; uvi < l; uvi ++ ) {

				this.addUVLine( this.parseUVIndex( uvs[ uvi ], uvLen ) );

			}

		}
```
</details>

### `startObject(name: any, fromDeclaration: any): void`

**Parameters:**

- **`name`** `any`
- **`fromDeclaration`** `any`

**Returns:** `void`

**Calls:**

- `this.object.currentMaterial`
- `this.object._finalize`
- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`
- `this.currentMaterial`
- `previousMaterial.clone`
- `this.object.materials.push`
- `this.objects.push`

**Internal Comments:**
```
// If the current object (initial from reset) is not from a g/o declaration in the parsed
// file. We need to use it for the first parsed g/o to keep things in sync.
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
// Inherit previous objects material.
// Spec tells us that a declared material must be set to all objects until a new material is declared.
// If a usemtl declaration is encountered while this new object is being parsed, it will
// overwrite the inherited material. Exception being that there was already face declarations
// to the inherited material, then it will be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, fromDeclaration ) {

			// If the current object (initial from reset) is not from a g/o declaration in the parsed
			// file. We need to use it for the first parsed g/o to keep things in sync.
			if ( this.object && this.object.fromDeclaration === false ) {

				this.object.name = name;
				this.object.fromDeclaration = ( fromDeclaration !== false );
				return;

			}

			const previousMaterial = ( this.object && typeof this.object.currentMaterial === 'function' ? this.object.currentMaterial() : undefined );

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

			this.object = {
				name: name || '',
				fromDeclaration: ( fromDeclaration !== false ),

				geometry: {
					vertices: [],
					normals: [],
					colors: [],
					uvs: [],
					hasUVIndices: false
				},
				materials: [],
				smooth: true,

				startMaterial: function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				},

				currentMaterial: function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				},

				_finalize: function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
			};

			// Inherit previous objects material.
			// Spec tells us that a declared material must be set to all objects until a new material is declared.
			// If a usemtl declaration is encountered while this new object is being parsed, it will
			// overwrite the inherited material. Exception being that there was already face declarations
			// to the inherited material, then it will be preserved for proper MultiMaterial continuation.

			if ( previousMaterial && previousMaterial.name && typeof previousMaterial.clone === 'function' ) {

				const declared = previousMaterial.clone( 0 );
				declared.inherited = true;
				this.object.materials.push( declared );

			}

			this.objects.push( this.object );

		}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `finalize(): void`

**Returns:** `void`

**Calls:**

- `this.object._finalize`

<details><summary>Code</summary>

```typescript
function () {

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

		}
```
</details>

### `parseVertexIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseNormalIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseUVIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 2 ) * 2;

		}
```
</details>

### `addVertex(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addVertexPoint(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addVertexLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.normals;
			const dst = this.object.geometry.normals;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addFaceNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `_vA.fromArray`
- `_vB.fromArray`
- `_vC.fromArray`
- `_cb.subVectors`
- `_ab.subVectors`
- `_cb.cross`
- `_cb.normalize`
- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.normals;

			_vA.fromArray( src, a );
			_vB.fromArray( src, b );
			_vC.fromArray( src, c );

			_cb.subVectors( _vC, _vB );
			_ab.subVectors( _vA, _vB );
			_cb.cross( _ab );

			_cb.normalize();

			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );

		}
```
</details>

### `addColor(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.colors;
			const dst = this.object.geometry.colors;

			if ( src[ a ] !== undefined ) dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			if ( src[ b ] !== undefined ) dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			if ( src[ c ] !== undefined ) dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addUV(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ] );

		}
```
</details>

### `addDefaultUV(): void`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function () {

			const dst = this.object.geometry.uvs;

			dst.push( 0, 0 );
			dst.push( 0, 0 );
			dst.push( 0, 0 );

		}
```
</details>

### `addUVLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );

		}
```
</details>

### `addFace(a: any, b: any, c: any, ua: any, ub: any, uc: any, na: any, nb: any, nc: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`ua`** `any`
- **`ub`** `any`
- **`uc`** `any`
- **`na`** `any`
- **`nb`** `any`
- **`nc`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertex`
- `this.addColor`
- `this.parseNormalIndex`
- `this.addNormal`
- `this.addFaceNormal`
- `this.parseUVIndex`
- `this.addUV`
- `this.addDefaultUV`

**Internal Comments:**
```
// normals
// uvs
// add placeholder values (for inconsistent face definitions) (x4)
```

<details><summary>Code</summary>

```typescript
function ( a, b, c, ua, ub, uc, na, nb, nc ) {

			const vLen = this.vertices.length;

			let ia = this.parseVertexIndex( a, vLen );
			let ib = this.parseVertexIndex( b, vLen );
			let ic = this.parseVertexIndex( c, vLen );

			this.addVertex( ia, ib, ic );
			this.addColor( ia, ib, ic );

			// normals

			if ( na !== undefined && na !== '' ) {

				const nLen = this.normals.length;

				ia = this.parseNormalIndex( na, nLen );
				ib = this.parseNormalIndex( nb, nLen );
				ic = this.parseNormalIndex( nc, nLen );

				this.addNormal( ia, ib, ic );

			} else {

				this.addFaceNormal( ia, ib, ic );

			}

			// uvs

			if ( ua !== undefined && ua !== '' ) {

				const uvLen = this.uvs.length;

				ia = this.parseUVIndex( ua, uvLen );
				ib = this.parseUVIndex( ub, uvLen );
				ic = this.parseUVIndex( uc, uvLen );

				this.addUV( ia, ib, ic );

				this.object.geometry.hasUVIndices = true;

			} else {

				// add placeholder values (for inconsistent face definitions)

				this.addDefaultUV();

			}

		}
```
</details>

### `addPointGeometry(vertices: any): void`

**Parameters:**

- **`vertices`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertexPoint`
- `this.addColor`

<details><summary>Code</summary>

```typescript
function ( vertices ) {

			this.object.geometry.type = 'Points';

			const vLen = this.vertices.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				const index = this.parseVertexIndex( vertices[ vi ], vLen );

				this.addVertexPoint( index );
				this.addColor( index );

			}

		}
```
</details>

### `addLineGeometry(vertices: any, uvs: any): void`

**Parameters:**

- **`vertices`** `any`
- **`uvs`** `any`

**Returns:** `void`

**Calls:**

- `this.addVertexLine`
- `this.parseVertexIndex`
- `this.addUVLine`
- `this.parseUVIndex`

<details><summary>Code</summary>

```typescript
function ( vertices, uvs ) {

			this.object.geometry.type = 'Line';

			const vLen = this.vertices.length;
			const uvLen = this.uvs.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				this.addVertexLine( this.parseVertexIndex( vertices[ vi ], vLen ) );

			}

			for ( let uvi = 0, l = uvs.length; uvi < l; uvi ++ ) {

				this.addUVLine( this.parseUVIndex( uvs[ uvi ], uvLen ) );

			}

		}
```
</details>

### `startObject(name: any, fromDeclaration: any): void`

**Parameters:**

- **`name`** `any`
- **`fromDeclaration`** `any`

**Returns:** `void`

**Calls:**

- `this.object.currentMaterial`
- `this.object._finalize`
- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`
- `this.currentMaterial`
- `previousMaterial.clone`
- `this.object.materials.push`
- `this.objects.push`

**Internal Comments:**
```
// If the current object (initial from reset) is not from a g/o declaration in the parsed
// file. We need to use it for the first parsed g/o to keep things in sync.
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
// Inherit previous objects material.
// Spec tells us that a declared material must be set to all objects until a new material is declared.
// If a usemtl declaration is encountered while this new object is being parsed, it will
// overwrite the inherited material. Exception being that there was already face declarations
// to the inherited material, then it will be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, fromDeclaration ) {

			// If the current object (initial from reset) is not from a g/o declaration in the parsed
			// file. We need to use it for the first parsed g/o to keep things in sync.
			if ( this.object && this.object.fromDeclaration === false ) {

				this.object.name = name;
				this.object.fromDeclaration = ( fromDeclaration !== false );
				return;

			}

			const previousMaterial = ( this.object && typeof this.object.currentMaterial === 'function' ? this.object.currentMaterial() : undefined );

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

			this.object = {
				name: name || '',
				fromDeclaration: ( fromDeclaration !== false ),

				geometry: {
					vertices: [],
					normals: [],
					colors: [],
					uvs: [],
					hasUVIndices: false
				},
				materials: [],
				smooth: true,

				startMaterial: function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				},

				currentMaterial: function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				},

				_finalize: function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
			};

			// Inherit previous objects material.
			// Spec tells us that a declared material must be set to all objects until a new material is declared.
			// If a usemtl declaration is encountered while this new object is being parsed, it will
			// overwrite the inherited material. Exception being that there was already face declarations
			// to the inherited material, then it will be preserved for proper MultiMaterial continuation.

			if ( previousMaterial && previousMaterial.name && typeof previousMaterial.clone === 'function' ) {

				const declared = previousMaterial.clone( 0 );
				declared.inherited = true;
				this.object.materials.push( declared );

			}

			this.objects.push( this.object );

		}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `startMaterial(name: any, libraries: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Parameters:**

- **`name`** `any`
- **`libraries`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: any; groupEnd: number; groupCount: number; inherited: boolean; clone: (index: any) => { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }; }`

**Calls:**

- `this._finalize`
- `this.materials.splice`
- `Array.isArray`
- `this.clone.bind`
- `this.materials.push`

**Internal Comments:**
```
// New usemtl declaration overwrites an inherited material, except if faces were declared
// after the material, then it must be preserved for proper MultiMaterial continuation.
```

<details><summary>Code</summary>

```typescript
function ( name, libraries ) {

					const previous = this._finalize( false );

					// New usemtl declaration overwrites an inherited material, except if faces were declared
					// after the material, then it must be preserved for proper MultiMaterial continuation.
					if ( previous && ( previous.inherited || previous.groupCount <= 0 ) ) {

						this.materials.splice( previous.index, 1 );

					}

					const material = {
						index: this.materials.length,
						name: name || '',
						mtllib: ( Array.isArray( libraries ) && libraries.length > 0 ? libraries[ libraries.length - 1 ] : '' ),
						smooth: ( previous !== undefined ? previous.smooth : this.smooth ),
						groupStart: ( previous !== undefined ? previous.groupEnd : 0 ),
						groupEnd: - 1,
						groupCount: - 1,
						inherited: false,

						clone: function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
					};

					this.materials.push( material );

					return material;

				}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `clone(index: any): { index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Parameters:**

- **`index`** `any`

**Returns:** `{ index: number; name: any; mtllib: any; smooth: any; groupStart: number; groupEnd: number; groupCount: number; inherited: boolean; }`

**Calls:**

- `this.clone.bind`

<details><summary>Code</summary>

```typescript
function ( index ) {

							const cloned = {
								index: ( typeof index === 'number' ? index : this.index ),
								name: this.name,
								mtllib: this.mtllib,
								smooth: this.smooth,
								groupStart: 0,
								groupEnd: - 1,
								groupCount: - 1,
								inherited: false
							};
							cloned.clone = this.clone.bind( cloned );
							return cloned;

						}
```
</details>

### `currentMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					if ( this.materials.length > 0 ) {

						return this.materials[ this.materials.length - 1 ];

					}

					return undefined;

				}
```
</details>

### `_finalize(end: any): any`

**Parameters:**

- **`end`** `any`

**Returns:** `any`

**Calls:**

- `this.currentMaterial`
- `this.materials.splice`
- `this.materials.push`

**Internal Comments:**
```
// Ignore objects tail materials if no face declarations followed them before a new o/g started.
// Guarantee at least one empty material, this makes the creation later more straight forward.
```

<details><summary>Code</summary>

```typescript
function ( end ) {

					const lastMultiMaterial = this.currentMaterial();
					if ( lastMultiMaterial && lastMultiMaterial.groupEnd === - 1 ) {

						lastMultiMaterial.groupEnd = this.geometry.vertices.length / 3;
						lastMultiMaterial.groupCount = lastMultiMaterial.groupEnd - lastMultiMaterial.groupStart;
						lastMultiMaterial.inherited = false;

					}

					// Ignore objects tail materials if no face declarations followed them before a new o/g started.
					if ( end && this.materials.length > 1 ) {

						for ( let mi = this.materials.length - 1; mi >= 0; mi -- ) {

							if ( this.materials[ mi ].groupCount <= 0 ) {

								this.materials.splice( mi, 1 );

							}

						}

					}

					// Guarantee at least one empty material, this makes the creation later more straight forward.
					if ( end && this.materials.length === 0 ) {

						this.materials.push( {
							name: '',
							smooth: this.smooth
						} );

					}

					return lastMultiMaterial;

				}
```
</details>

### `finalize(): void`

**Returns:** `void`

**Calls:**

- `this.object._finalize`

<details><summary>Code</summary>

```typescript
function () {

			if ( this.object && typeof this.object._finalize === 'function' ) {

				this.object._finalize( true );

			}

		}
```
</details>

### `parseVertexIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseNormalIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 3 ) * 3;

		}
```
</details>

### `parseUVIndex(value: any, len: any): number`

**Parameters:**

- **`value`** `any`
- **`len`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( value, len ) {

			const index = parseInt( value, 10 );
			return ( index >= 0 ? index - 1 : index + len / 2 ) * 2;

		}
```
</details>

### `addVertex(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addVertexPoint(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addVertexLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.vertices;
			const dst = this.object.geometry.vertices;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );

		}
```
</details>

### `addNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.normals;
			const dst = this.object.geometry.normals;

			dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addFaceNormal(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `_vA.fromArray`
- `_vB.fromArray`
- `_vC.fromArray`
- `_cb.subVectors`
- `_ab.subVectors`
- `_cb.cross`
- `_cb.normalize`
- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.vertices;
			const dst = this.object.geometry.normals;

			_vA.fromArray( src, a );
			_vB.fromArray( src, b );
			_vC.fromArray( src, c );

			_cb.subVectors( _vC, _vB );
			_ab.subVectors( _vA, _vB );
			_cb.cross( _ab );

			_cb.normalize();

			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );
			dst.push( _cb.x, _cb.y, _cb.z );

		}
```
</details>

### `addColor(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.colors;
			const dst = this.object.geometry.colors;

			if ( src[ a ] !== undefined ) dst.push( src[ a + 0 ], src[ a + 1 ], src[ a + 2 ] );
			if ( src[ b ] !== undefined ) dst.push( src[ b + 0 ], src[ b + 1 ], src[ b + 2 ] );
			if ( src[ c ] !== undefined ) dst.push( src[ c + 0 ], src[ c + 1 ], src[ c + 2 ] );

		}
```
</details>

### `addUV(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a, b, c ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );
			dst.push( src[ b + 0 ], src[ b + 1 ] );
			dst.push( src[ c + 0 ], src[ c + 1 ] );

		}
```
</details>

### `addDefaultUV(): void`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function () {

			const dst = this.object.geometry.uvs;

			dst.push( 0, 0 );
			dst.push( 0, 0 );
			dst.push( 0, 0 );

		}
```
</details>

### `addUVLine(a: any): void`

**Parameters:**

- **`a`** `any`

**Returns:** `void`

**Calls:**

- `dst.push`

<details><summary>Code</summary>

```typescript
function ( a ) {

			const src = this.uvs;
			const dst = this.object.geometry.uvs;

			dst.push( src[ a + 0 ], src[ a + 1 ] );

		}
```
</details>

### `addFace(a: any, b: any, c: any, ua: any, ub: any, uc: any, na: any, nb: any, nc: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`ua`** `any`
- **`ub`** `any`
- **`uc`** `any`
- **`na`** `any`
- **`nb`** `any`
- **`nc`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertex`
- `this.addColor`
- `this.parseNormalIndex`
- `this.addNormal`
- `this.addFaceNormal`
- `this.parseUVIndex`
- `this.addUV`
- `this.addDefaultUV`

**Internal Comments:**
```
// normals
// uvs
// add placeholder values (for inconsistent face definitions) (x4)
```

<details><summary>Code</summary>

```typescript
function ( a, b, c, ua, ub, uc, na, nb, nc ) {

			const vLen = this.vertices.length;

			let ia = this.parseVertexIndex( a, vLen );
			let ib = this.parseVertexIndex( b, vLen );
			let ic = this.parseVertexIndex( c, vLen );

			this.addVertex( ia, ib, ic );
			this.addColor( ia, ib, ic );

			// normals

			if ( na !== undefined && na !== '' ) {

				const nLen = this.normals.length;

				ia = this.parseNormalIndex( na, nLen );
				ib = this.parseNormalIndex( nb, nLen );
				ic = this.parseNormalIndex( nc, nLen );

				this.addNormal( ia, ib, ic );

			} else {

				this.addFaceNormal( ia, ib, ic );

			}

			// uvs

			if ( ua !== undefined && ua !== '' ) {

				const uvLen = this.uvs.length;

				ia = this.parseUVIndex( ua, uvLen );
				ib = this.parseUVIndex( ub, uvLen );
				ic = this.parseUVIndex( uc, uvLen );

				this.addUV( ia, ib, ic );

				this.object.geometry.hasUVIndices = true;

			} else {

				// add placeholder values (for inconsistent face definitions)

				this.addDefaultUV();

			}

		}
```
</details>

### `addPointGeometry(vertices: any): void`

**Parameters:**

- **`vertices`** `any`

**Returns:** `void`

**Calls:**

- `this.parseVertexIndex`
- `this.addVertexPoint`
- `this.addColor`

<details><summary>Code</summary>

```typescript
function ( vertices ) {

			this.object.geometry.type = 'Points';

			const vLen = this.vertices.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				const index = this.parseVertexIndex( vertices[ vi ], vLen );

				this.addVertexPoint( index );
				this.addColor( index );

			}

		}
```
</details>

### `addLineGeometry(vertices: any, uvs: any): void`

**Parameters:**

- **`vertices`** `any`
- **`uvs`** `any`

**Returns:** `void`

**Calls:**

- `this.addVertexLine`
- `this.parseVertexIndex`
- `this.addUVLine`
- `this.parseUVIndex`

<details><summary>Code</summary>

```typescript
function ( vertices, uvs ) {

			this.object.geometry.type = 'Line';

			const vLen = this.vertices.length;
			const uvLen = this.uvs.length;

			for ( let vi = 0, l = vertices.length; vi < l; vi ++ ) {

				this.addVertexLine( this.parseVertexIndex( vertices[ vi ], vLen ) );

			}

			for ( let uvi = 0, l = uvs.length; uvi < l; uvi ++ ) {

				this.addUVLine( this.parseUVIndex( uvs[ uvi ], uvLen ) );

			}

		}
```
</details>

### `OBJLoader.load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded OBJ asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Group) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `onLoad`
- `scope.parse`
- `onError`
- `console.error`
- `scope.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `OBJLoader.setMaterials(materials: MaterialCreator): OBJLoader`

**JSDoc:**
```typescript
/**
	 * Sets the material creator for this OBJ. This object is loaded via {@link MTLLoader}.
	 *
	 * @param {MaterialCreator} materials - An object that creates the materials for this OBJ.
	 * @return {OBJLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`materials`** `MaterialCreator`

**Returns:** `OBJLoader`

<details><summary>Code</summary>

```typescript
setMaterials( materials ) {

		this.materials = materials;

		return this;

	}
```
</details>

### `OBJLoader.parse(text: string): Group`

**JSDoc:**
```typescript
/**
	 * Parses the given OBJ data and returns the resulting group.
	 *
	 * @param {string} text - The raw OBJ data as a string.
	 * @return {Group} The parsed OBJ.
	 */
```

**Parameters:**

- **`text`** `string`

**Returns:** `Group`

**Calls:**

- `text.indexOf`
- `text.replace`
- `text.split`
- `lines[ i ].trimStart`
- `line.charAt`
- `line.split`
- `state.vertices.push`
- `parseFloat`
- `_color.setRGB`
- `state.colors.push`
- `state.normals.push`
- `state.uvs.push`
- `line.slice( 1 ).trim`
- `lineData.split`
- `vertex.split`
- `faceVertices.push`
- `state.addFace`
- `line.substring( 1 ).trim().split`
- `line.indexOf`
- `lineParts[ li ].split`
- `lineVertices.push`
- `lineUVs.push`
- `state.addLineGeometry`
- `state.addPointGeometry`
- `_object_pattern.exec`
- `( ' ' + result[ 0 ].slice( 1 ).trim() ).slice`
- `result[ 0 ].slice( 1 ).trim`
- `state.startObject`
- `_material_use_pattern.test`
- `state.object.startMaterial`
- `line.substring( 7 ).trim`
- `_material_library_pattern.test`
- `state.materialLibraries.push`
- `_map_use_pattern.test`
- `console.warn`
- `result[ 1 ].trim().toLowerCase`
- `state.object.currentMaterial`
- `state.finalize`
- `[].concat`
- `buffergeometry.setAttribute`
- `this.materials.create`
- `Material.prototype.copy.call`
- `materialLine.color.copy`
- `materialPoints.color.copy`
- `createdMaterials.push`
- `buffergeometry.addGroup`
- `container.add`

**Internal Comments:**
```
// This is faster than String.split with regex that splits on both (x3)
// join lines separated by a line continuation character (\) (x3)
// @todo invoke passed in handler if any
// if no colors are defined, add placeholders so color and vertex indices match (x5)
// Parse the face vertex data into an easy to work with format
// Draw an edge between the first vertex and all subsequent vertices to form an n-gon (x2)
// o object_name (x2)
// or (x2)
// g group_name (x2)
// WORKAROUND: https://bugs.chromium.org/p/v8/issues/detail?id=2869 (x2)
// let name = result[ 0 ].slice( 1 ).trim(); (x2)
// material (x5)
// mtl file (x5)
// the line is parsed but ignored since the loader assumes textures are defined MTL files (x4)
// (according to https://www.okino.com/conv/imp_wave.htm, 'usemap' is the old-style Wavefront texture reference method) (x4)
// smooth shading
// @todo Handle files that have varying smooth values for a set of faces inside one geometry,
// but does not define a usemtl for each face set.
// This should be detected and a dummy material created (later MultiMaterial and geometry groups).
// This requires some care to not create extra material on each smooth value for "normal" obj files.
// where explicit usemtl defines geometry groups.
// Example asset: examples/models/obj/cerberus/Cerberus.obj
/*
					 * http://paulbourke.net/dataformats/obj/
					 *
					 * From chapter "Grouping" Syntax explanation "s group_number":
					 * "group_number is the smoothing group number. To turn off smoothing groups, use a value of 0 or off.
					 * Polygonal elements use group numbers to put elements in different smoothing groups. For free-form
					 * surfaces, smoothing groups are either turned on or off; there is no difference between values greater
					 * than 0."
					 */
// ZBrush can produce "s" lines #11707 (x5)
// Handle null terminated files without exception
// Skip o/g line declarations that did not follow with any faces
// Create materials (x2)
// mtl etc. loaders probably can't create line materials correctly, copy properties to a line material.
// Create mesh (x2)
// if there is only the default parser state object with no geometry data, interpret data as point cloud
```

<details><summary>Code</summary>

```typescript
parse( text ) {

		const state = new ParserState();

		if ( text.indexOf( '\r\n' ) !== - 1 ) {

			// This is faster than String.split with regex that splits on both
			text = text.replace( /\r\n/g, '\n' );

		}

		if ( text.indexOf( '\\\n' ) !== - 1 ) {

			// join lines separated by a line continuation character (\)
			text = text.replace( /\\\n/g, '' );

		}

		const lines = text.split( '\n' );
		let result = [];

		for ( let i = 0, l = lines.length; i < l; i ++ ) {

			const line = lines[ i ].trimStart();

			if ( line.length === 0 ) continue;

			const lineFirstChar = line.charAt( 0 );

			// @todo invoke passed in handler if any
			if ( lineFirstChar === '#' ) continue; // skip comments

			if ( lineFirstChar === 'v' ) {

				const data = line.split( _face_vertex_data_separator_pattern );

				switch ( data[ 0 ] ) {

					case 'v':
						state.vertices.push(
							parseFloat( data[ 1 ] ),
							parseFloat( data[ 2 ] ),
							parseFloat( data[ 3 ] )
						);
						if ( data.length >= 7 ) {

							_color.setRGB(
								parseFloat( data[ 4 ] ),
								parseFloat( data[ 5 ] ),
								parseFloat( data[ 6 ] ),
								SRGBColorSpace
							);

							state.colors.push( _color.r, _color.g, _color.b );

						} else {

							// if no colors are defined, add placeholders so color and vertex indices match

							state.colors.push( undefined, undefined, undefined );

						}

						break;
					case 'vn':
						state.normals.push(
							parseFloat( data[ 1 ] ),
							parseFloat( data[ 2 ] ),
							parseFloat( data[ 3 ] )
						);
						break;
					case 'vt':
						state.uvs.push(
							parseFloat( data[ 1 ] ),
							parseFloat( data[ 2 ] )
						);
						break;

				}

			} else if ( lineFirstChar === 'f' ) {

				const lineData = line.slice( 1 ).trim();
				const vertexData = lineData.split( _face_vertex_data_separator_pattern );
				const faceVertices = [];

				// Parse the face vertex data into an easy to work with format

				for ( let j = 0, jl = vertexData.length; j < jl; j ++ ) {

					const vertex = vertexData[ j ];

					if ( vertex.length > 0 ) {

						const vertexParts = vertex.split( '/' );
						faceVertices.push( vertexParts );

					}

				}

				// Draw an edge between the first vertex and all subsequent vertices to form an n-gon

				const v1 = faceVertices[ 0 ];

				for ( let j = 1, jl = faceVertices.length - 1; j < jl; j ++ ) {

					const v2 = faceVertices[ j ];
					const v3 = faceVertices[ j + 1 ];

					state.addFace(
						v1[ 0 ], v2[ 0 ], v3[ 0 ],
						v1[ 1 ], v2[ 1 ], v3[ 1 ],
						v1[ 2 ], v2[ 2 ], v3[ 2 ]
					);

				}

			} else if ( lineFirstChar === 'l' ) {

				const lineParts = line.substring( 1 ).trim().split( ' ' );
				let lineVertices = [];
				const lineUVs = [];

				if ( line.indexOf( '/' ) === - 1 ) {

					lineVertices = lineParts;

				} else {

					for ( let li = 0, llen = lineParts.length; li < llen; li ++ ) {

						const parts = lineParts[ li ].split( '/' );

						if ( parts[ 0 ] !== '' ) lineVertices.push( parts[ 0 ] );
						if ( parts[ 1 ] !== '' ) lineUVs.push( parts[ 1 ] );

					}

				}

				state.addLineGeometry( lineVertices, lineUVs );

			} else if ( lineFirstChar === 'p' ) {

				const lineData = line.slice( 1 ).trim();
				const pointData = lineData.split( ' ' );

				state.addPointGeometry( pointData );

			} else if ( ( result = _object_pattern.exec( line ) ) !== null ) {

				// o object_name
				// or
				// g group_name

				// WORKAROUND: https://bugs.chromium.org/p/v8/issues/detail?id=2869
				// let name = result[ 0 ].slice( 1 ).trim();
				const name = ( ' ' + result[ 0 ].slice( 1 ).trim() ).slice( 1 );

				state.startObject( name );

			} else if ( _material_use_pattern.test( line ) ) {

				// material

				state.object.startMaterial( line.substring( 7 ).trim(), state.materialLibraries );

			} else if ( _material_library_pattern.test( line ) ) {

				// mtl file

				state.materialLibraries.push( line.substring( 7 ).trim() );

			} else if ( _map_use_pattern.test( line ) ) {

				// the line is parsed but ignored since the loader assumes textures are defined MTL files
				// (according to https://www.okino.com/conv/imp_wave.htm, 'usemap' is the old-style Wavefront texture reference method)

				console.warn( 'THREE.OBJLoader: Rendering identifier "usemap" not supported. Textures must be defined in MTL files.' );

			} else if ( lineFirstChar === 's' ) {

				result = line.split( ' ' );

				// smooth shading

				// @todo Handle files that have varying smooth values for a set of faces inside one geometry,
				// but does not define a usemtl for each face set.
				// This should be detected and a dummy material created (later MultiMaterial and geometry groups).
				// This requires some care to not create extra material on each smooth value for "normal" obj files.
				// where explicit usemtl defines geometry groups.
				// Example asset: examples/models/obj/cerberus/Cerberus.obj

				/*
					 * http://paulbourke.net/dataformats/obj/
					 *
					 * From chapter "Grouping" Syntax explanation "s group_number":
					 * "group_number is the smoothing group number. To turn off smoothing groups, use a value of 0 or off.
					 * Polygonal elements use group numbers to put elements in different smoothing groups. For free-form
					 * surfaces, smoothing groups are either turned on or off; there is no difference between values greater
					 * than 0."
					 */
				if ( result.length > 1 ) {

					const value = result[ 1 ].trim().toLowerCase();
					state.object.smooth = ( value !== '0' && value !== 'off' );

				} else {

					// ZBrush can produce "s" lines #11707
					state.object.smooth = true;

				}

				const material = state.object.currentMaterial();
				if ( material ) material.smooth = state.object.smooth;

			} else {

				// Handle null terminated files without exception
				if ( line === '\0' ) continue;

				console.warn( 'THREE.OBJLoader: Unexpected line: "' + line + '"' );

			}

		}

		state.finalize();

		const container = new Group();
		container.materialLibraries = [].concat( state.materialLibraries );

		const hasPrimitives = ! ( state.objects.length === 1 && state.objects[ 0 ].geometry.vertices.length === 0 );

		if ( hasPrimitives === true ) {

			for ( let i = 0, l = state.objects.length; i < l; i ++ ) {

				const object = state.objects[ i ];
				const geometry = object.geometry;
				const materials = object.materials;
				const isLine = ( geometry.type === 'Line' );
				const isPoints = ( geometry.type === 'Points' );
				let hasVertexColors = false;

				// Skip o/g line declarations that did not follow with any faces
				if ( geometry.vertices.length === 0 ) continue;

				const buffergeometry = new BufferGeometry();

				buffergeometry.setAttribute( 'position', new Float32BufferAttribute( geometry.vertices, 3 ) );

				if ( geometry.normals.length > 0 ) {

					buffergeometry.setAttribute( 'normal', new Float32BufferAttribute( geometry.normals, 3 ) );

				}

				if ( geometry.colors.length > 0 ) {

					hasVertexColors = true;
					buffergeometry.setAttribute( 'color', new Float32BufferAttribute( geometry.colors, 3 ) );

				}

				if ( geometry.hasUVIndices === true ) {

					buffergeometry.setAttribute( 'uv', new Float32BufferAttribute( geometry.uvs, 2 ) );

				}

				// Create materials

				const createdMaterials = [];

				for ( let mi = 0, miLen = materials.length; mi < miLen; mi ++ ) {

					const sourceMaterial = materials[ mi ];
					const materialHash = sourceMaterial.name + '_' + sourceMaterial.smooth + '_' + hasVertexColors;
					let material = state.materials[ materialHash ];

					if ( this.materials !== null ) {

						material = this.materials.create( sourceMaterial.name );

						// mtl etc. loaders probably can't create line materials correctly, copy properties to a line material.
						if ( isLine && material && ! ( material instanceof LineBasicMaterial ) ) {

							const materialLine = new LineBasicMaterial();
							Material.prototype.copy.call( materialLine, material );
							materialLine.color.copy( material.color );
							material = materialLine;

						} else if ( isPoints && material && ! ( material instanceof PointsMaterial ) ) {

							const materialPoints = new PointsMaterial( { size: 10, sizeAttenuation: false } );
							Material.prototype.copy.call( materialPoints, material );
							materialPoints.color.copy( material.color );
							materialPoints.map = material.map;
							material = materialPoints;

						}

					}

					if ( material === undefined ) {

						if ( isLine ) {

							material = new LineBasicMaterial();

						} else if ( isPoints ) {

							material = new PointsMaterial( { size: 1, sizeAttenuation: false } );

						} else {

							material = new MeshPhongMaterial();

						}

						material.name = sourceMaterial.name;
						material.flatShading = sourceMaterial.smooth ? false : true;
						material.vertexColors = hasVertexColors;

						state.materials[ materialHash ] = material;

					}

					createdMaterials.push( material );

				}

				// Create mesh

				let mesh;

				if ( createdMaterials.length > 1 ) {

					for ( let mi = 0, miLen = materials.length; mi < miLen; mi ++ ) {

						const sourceMaterial = materials[ mi ];
						buffergeometry.addGroup( sourceMaterial.groupStart, sourceMaterial.groupCount, mi );

					}

					if ( isLine ) {

						mesh = new LineSegments( buffergeometry, createdMaterials );

					} else if ( isPoints ) {

						mesh = new Points( buffergeometry, createdMaterials );

					} else {

						mesh = new Mesh( buffergeometry, createdMaterials );

					}

				} else {

					if ( isLine ) {

						mesh = new LineSegments( buffergeometry, createdMaterials[ 0 ] );

					} else if ( isPoints ) {

						mesh = new Points( buffergeometry, createdMaterials[ 0 ] );

					} else {

						mesh = new Mesh( buffergeometry, createdMaterials[ 0 ] );

					}

				}

				mesh.name = object.name;

				container.add( mesh );

			}

		} else {

			// if there is only the default parser state object with no geometry data, interpret data as point cloud

			if ( state.vertices.length > 0 ) {

				const material = new PointsMaterial( { size: 1, sizeAttenuation: false } );

				const buffergeometry = new BufferGeometry();

				buffergeometry.setAttribute( 'position', new Float32BufferAttribute( state.vertices, 3 ) );

				if ( state.colors.length > 0 && state.colors[ 0 ] !== undefined ) {

					buffergeometry.setAttribute( 'color', new Float32BufferAttribute( state.colors, 3 ) );
					material.vertexColors = true;

				}

				const points = new Points( buffergeometry, material );
				container.add( points );

			}

		}

		return container;

	}
```
</details>


---

## Classes

### `OBJLoader`

<details><summary>Class Code</summary>

```ts
class OBJLoader extends Loader {

	/**
	 * Constructs a new OBJ loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * A reference to a material creator.
		 *
		 * @type {?MaterialCreator}
		 * @default null
		 */
		this.materials = null;

	}

	/**
	 * Starts loading from the given URL and passes the loaded OBJ asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Sets the material creator for this OBJ. This object is loaded via {@link MTLLoader}.
	 *
	 * @param {MaterialCreator} materials - An object that creates the materials for this OBJ.
	 * @return {OBJLoader} A reference to this loader.
	 */
	setMaterials( materials ) {

		this.materials = materials;

		return this;

	}

	/**
	 * Parses the given OBJ data and returns the resulting group.
	 *
	 * @param {string} text - The raw OBJ data as a string.
	 * @return {Group} The parsed OBJ.
	 */
	parse( text ) {

		const state = new ParserState();

		if ( text.indexOf( '\r\n' ) !== - 1 ) {

			// This is faster than String.split with regex that splits on both
			text = text.replace( /\r\n/g, '\n' );

		}

		if ( text.indexOf( '\\\n' ) !== - 1 ) {

			// join lines separated by a line continuation character (\)
			text = text.replace( /\\\n/g, '' );

		}

		const lines = text.split( '\n' );
		let result = [];

		for ( let i = 0, l = lines.length; i < l; i ++ ) {

			const line = lines[ i ].trimStart();

			if ( line.length === 0 ) continue;

			const lineFirstChar = line.charAt( 0 );

			// @todo invoke passed in handler if any
			if ( lineFirstChar === '#' ) continue; // skip comments

			if ( lineFirstChar === 'v' ) {

				const data = line.split( _face_vertex_data_separator_pattern );

				switch ( data[ 0 ] ) {

					case 'v':
						state.vertices.push(
							parseFloat( data[ 1 ] ),
							parseFloat( data[ 2 ] ),
							parseFloat( data[ 3 ] )
						);
						if ( data.length >= 7 ) {

							_color.setRGB(
								parseFloat( data[ 4 ] ),
								parseFloat( data[ 5 ] ),
								parseFloat( data[ 6 ] ),
								SRGBColorSpace
							);

							state.colors.push( _color.r, _color.g, _color.b );

						} else {

							// if no colors are defined, add placeholders so color and vertex indices match

							state.colors.push( undefined, undefined, undefined );

						}

						break;
					case 'vn':
						state.normals.push(
							parseFloat( data[ 1 ] ),
							parseFloat( data[ 2 ] ),
							parseFloat( data[ 3 ] )
						);
						break;
					case 'vt':
						state.uvs.push(
							parseFloat( data[ 1 ] ),
							parseFloat( data[ 2 ] )
						);
						break;

				}

			} else if ( lineFirstChar === 'f' ) {

				const lineData = line.slice( 1 ).trim();
				const vertexData = lineData.split( _face_vertex_data_separator_pattern );
				const faceVertices = [];

				// Parse the face vertex data into an easy to work with format

				for ( let j = 0, jl = vertexData.length; j < jl; j ++ ) {

					const vertex = vertexData[ j ];

					if ( vertex.length > 0 ) {

						const vertexParts = vertex.split( '/' );
						faceVertices.push( vertexParts );

					}

				}

				// Draw an edge between the first vertex and all subsequent vertices to form an n-gon

				const v1 = faceVertices[ 0 ];

				for ( let j = 1, jl = faceVertices.length - 1; j < jl; j ++ ) {

					const v2 = faceVertices[ j ];
					const v3 = faceVertices[ j + 1 ];

					state.addFace(
						v1[ 0 ], v2[ 0 ], v3[ 0 ],
						v1[ 1 ], v2[ 1 ], v3[ 1 ],
						v1[ 2 ], v2[ 2 ], v3[ 2 ]
					);

				}

			} else if ( lineFirstChar === 'l' ) {

				const lineParts = line.substring( 1 ).trim().split( ' ' );
				let lineVertices = [];
				const lineUVs = [];

				if ( line.indexOf( '/' ) === - 1 ) {

					lineVertices = lineParts;

				} else {

					for ( let li = 0, llen = lineParts.length; li < llen; li ++ ) {

						const parts = lineParts[ li ].split( '/' );

						if ( parts[ 0 ] !== '' ) lineVertices.push( parts[ 0 ] );
						if ( parts[ 1 ] !== '' ) lineUVs.push( parts[ 1 ] );

					}

				}

				state.addLineGeometry( lineVertices, lineUVs );

			} else if ( lineFirstChar === 'p' ) {

				const lineData = line.slice( 1 ).trim();
				const pointData = lineData.split( ' ' );

				state.addPointGeometry( pointData );

			} else if ( ( result = _object_pattern.exec( line ) ) !== null ) {

				// o object_name
				// or
				// g group_name

				// WORKAROUND: https://bugs.chromium.org/p/v8/issues/detail?id=2869
				// let name = result[ 0 ].slice( 1 ).trim();
				const name = ( ' ' + result[ 0 ].slice( 1 ).trim() ).slice( 1 );

				state.startObject( name );

			} else if ( _material_use_pattern.test( line ) ) {

				// material

				state.object.startMaterial( line.substring( 7 ).trim(), state.materialLibraries );

			} else if ( _material_library_pattern.test( line ) ) {

				// mtl file

				state.materialLibraries.push( line.substring( 7 ).trim() );

			} else if ( _map_use_pattern.test( line ) ) {

				// the line is parsed but ignored since the loader assumes textures are defined MTL files
				// (according to https://www.okino.com/conv/imp_wave.htm, 'usemap' is the old-style Wavefront texture reference method)

				console.warn( 'THREE.OBJLoader: Rendering identifier "usemap" not supported. Textures must be defined in MTL files.' );

			} else if ( lineFirstChar === 's' ) {

				result = line.split( ' ' );

				// smooth shading

				// @todo Handle files that have varying smooth values for a set of faces inside one geometry,
				// but does not define a usemtl for each face set.
				// This should be detected and a dummy material created (later MultiMaterial and geometry groups).
				// This requires some care to not create extra material on each smooth value for "normal" obj files.
				// where explicit usemtl defines geometry groups.
				// Example asset: examples/models/obj/cerberus/Cerberus.obj

				/*
					 * http://paulbourke.net/dataformats/obj/
					 *
					 * From chapter "Grouping" Syntax explanation "s group_number":
					 * "group_number is the smoothing group number. To turn off smoothing groups, use a value of 0 or off.
					 * Polygonal elements use group numbers to put elements in different smoothing groups. For free-form
					 * surfaces, smoothing groups are either turned on or off; there is no difference between values greater
					 * than 0."
					 */
				if ( result.length > 1 ) {

					const value = result[ 1 ].trim().toLowerCase();
					state.object.smooth = ( value !== '0' && value !== 'off' );

				} else {

					// ZBrush can produce "s" lines #11707
					state.object.smooth = true;

				}

				const material = state.object.currentMaterial();
				if ( material ) material.smooth = state.object.smooth;

			} else {

				// Handle null terminated files without exception
				if ( line === '\0' ) continue;

				console.warn( 'THREE.OBJLoader: Unexpected line: "' + line + '"' );

			}

		}

		state.finalize();

		const container = new Group();
		container.materialLibraries = [].concat( state.materialLibraries );

		const hasPrimitives = ! ( state.objects.length === 1 && state.objects[ 0 ].geometry.vertices.length === 0 );

		if ( hasPrimitives === true ) {

			for ( let i = 0, l = state.objects.length; i < l; i ++ ) {

				const object = state.objects[ i ];
				const geometry = object.geometry;
				const materials = object.materials;
				const isLine = ( geometry.type === 'Line' );
				const isPoints = ( geometry.type === 'Points' );
				let hasVertexColors = false;

				// Skip o/g line declarations that did not follow with any faces
				if ( geometry.vertices.length === 0 ) continue;

				const buffergeometry = new BufferGeometry();

				buffergeometry.setAttribute( 'position', new Float32BufferAttribute( geometry.vertices, 3 ) );

				if ( geometry.normals.length > 0 ) {

					buffergeometry.setAttribute( 'normal', new Float32BufferAttribute( geometry.normals, 3 ) );

				}

				if ( geometry.colors.length > 0 ) {

					hasVertexColors = true;
					buffergeometry.setAttribute( 'color', new Float32BufferAttribute( geometry.colors, 3 ) );

				}

				if ( geometry.hasUVIndices === true ) {

					buffergeometry.setAttribute( 'uv', new Float32BufferAttribute( geometry.uvs, 2 ) );

				}

				// Create materials

				const createdMaterials = [];

				for ( let mi = 0, miLen = materials.length; mi < miLen; mi ++ ) {

					const sourceMaterial = materials[ mi ];
					const materialHash = sourceMaterial.name + '_' + sourceMaterial.smooth + '_' + hasVertexColors;
					let material = state.materials[ materialHash ];

					if ( this.materials !== null ) {

						material = this.materials.create( sourceMaterial.name );

						// mtl etc. loaders probably can't create line materials correctly, copy properties to a line material.
						if ( isLine && material && ! ( material instanceof LineBasicMaterial ) ) {

							const materialLine = new LineBasicMaterial();
							Material.prototype.copy.call( materialLine, material );
							materialLine.color.copy( material.color );
							material = materialLine;

						} else if ( isPoints && material && ! ( material instanceof PointsMaterial ) ) {

							const materialPoints = new PointsMaterial( { size: 10, sizeAttenuation: false } );
							Material.prototype.copy.call( materialPoints, material );
							materialPoints.color.copy( material.color );
							materialPoints.map = material.map;
							material = materialPoints;

						}

					}

					if ( material === undefined ) {

						if ( isLine ) {

							material = new LineBasicMaterial();

						} else if ( isPoints ) {

							material = new PointsMaterial( { size: 1, sizeAttenuation: false } );

						} else {

							material = new MeshPhongMaterial();

						}

						material.name = sourceMaterial.name;
						material.flatShading = sourceMaterial.smooth ? false : true;
						material.vertexColors = hasVertexColors;

						state.materials[ materialHash ] = material;

					}

					createdMaterials.push( material );

				}

				// Create mesh

				let mesh;

				if ( createdMaterials.length > 1 ) {

					for ( let mi = 0, miLen = materials.length; mi < miLen; mi ++ ) {

						const sourceMaterial = materials[ mi ];
						buffergeometry.addGroup( sourceMaterial.groupStart, sourceMaterial.groupCount, mi );

					}

					if ( isLine ) {

						mesh = new LineSegments( buffergeometry, createdMaterials );

					} else if ( isPoints ) {

						mesh = new Points( buffergeometry, createdMaterials );

					} else {

						mesh = new Mesh( buffergeometry, createdMaterials );

					}

				} else {

					if ( isLine ) {

						mesh = new LineSegments( buffergeometry, createdMaterials[ 0 ] );

					} else if ( isPoints ) {

						mesh = new Points( buffergeometry, createdMaterials[ 0 ] );

					} else {

						mesh = new Mesh( buffergeometry, createdMaterials[ 0 ] );

					}

				}

				mesh.name = object.name;

				container.add( mesh );

			}

		} else {

			// if there is only the default parser state object with no geometry data, interpret data as point cloud

			if ( state.vertices.length > 0 ) {

				const material = new PointsMaterial( { size: 1, sizeAttenuation: false } );

				const buffergeometry = new BufferGeometry();

				buffergeometry.setAttribute( 'position', new Float32BufferAttribute( state.vertices, 3 ) );

				if ( state.colors.length > 0 && state.colors[ 0 ] !== undefined ) {

					buffergeometry.setAttribute( 'color', new Float32BufferAttribute( state.colors, 3 ) );
					material.vertexColors = true;

				}

				const points = new Points( buffergeometry, material );
				container.add( points );

			}

		}

		return container;

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `setMaterials(materials: MaterialCreator): OBJLoader`

<details><summary>Code</summary>

```ts
setMaterials( materials ) {

		this.materials = materials;

		return this;

	}
```
</details>

##### `parse(text: string): Group`

<details><summary>Code</summary>

```ts
parse( text ) {

		const state = new ParserState();

		if ( text.indexOf( '\r\n' ) !== - 1 ) {

			// This is faster than String.split with regex that splits on both
			text = text.replace( /\r\n/g, '\n' );

		}

		if ( text.indexOf( '\\\n' ) !== - 1 ) {

			// join lines separated by a line continuation character (\)
			text = text.replace( /\\\n/g, '' );

		}

		const lines = text.split( '\n' );
		let result = [];

		for ( let i = 0, l = lines.length; i < l; i ++ ) {

			const line = lines[ i ].trimStart();

			if ( line.length === 0 ) continue;

			const lineFirstChar = line.charAt( 0 );

			// @todo invoke passed in handler if any
			if ( lineFirstChar === '#' ) continue; // skip comments

			if ( lineFirstChar === 'v' ) {

				const data = line.split( _face_vertex_data_separator_pattern );

				switch ( data[ 0 ] ) {

					case 'v':
						state.vertices.push(
							parseFloat( data[ 1 ] ),
							parseFloat( data[ 2 ] ),
							parseFloat( data[ 3 ] )
						);
						if ( data.length >= 7 ) {

							_color.setRGB(
								parseFloat( data[ 4 ] ),
								parseFloat( data[ 5 ] ),
								parseFloat( data[ 6 ] ),
								SRGBColorSpace
							);

							state.colors.push( _color.r, _color.g, _color.b );

						} else {

							// if no colors are defined, add placeholders so color and vertex indices match

							state.colors.push( undefined, undefined, undefined );

						}

						break;
					case 'vn':
						state.normals.push(
							parseFloat( data[ 1 ] ),
							parseFloat( data[ 2 ] ),
							parseFloat( data[ 3 ] )
						);
						break;
					case 'vt':
						state.uvs.push(
							parseFloat( data[ 1 ] ),
							parseFloat( data[ 2 ] )
						);
						break;

				}

			} else if ( lineFirstChar === 'f' ) {

				const lineData = line.slice( 1 ).trim();
				const vertexData = lineData.split( _face_vertex_data_separator_pattern );
				const faceVertices = [];

				// Parse the face vertex data into an easy to work with format

				for ( let j = 0, jl = vertexData.length; j < jl; j ++ ) {

					const vertex = vertexData[ j ];

					if ( vertex.length > 0 ) {

						const vertexParts = vertex.split( '/' );
						faceVertices.push( vertexParts );

					}

				}

				// Draw an edge between the first vertex and all subsequent vertices to form an n-gon

				const v1 = faceVertices[ 0 ];

				for ( let j = 1, jl = faceVertices.length - 1; j < jl; j ++ ) {

					const v2 = faceVertices[ j ];
					const v3 = faceVertices[ j + 1 ];

					state.addFace(
						v1[ 0 ], v2[ 0 ], v3[ 0 ],
						v1[ 1 ], v2[ 1 ], v3[ 1 ],
						v1[ 2 ], v2[ 2 ], v3[ 2 ]
					);

				}

			} else if ( lineFirstChar === 'l' ) {

				const lineParts = line.substring( 1 ).trim().split( ' ' );
				let lineVertices = [];
				const lineUVs = [];

				if ( line.indexOf( '/' ) === - 1 ) {

					lineVertices = lineParts;

				} else {

					for ( let li = 0, llen = lineParts.length; li < llen; li ++ ) {

						const parts = lineParts[ li ].split( '/' );

						if ( parts[ 0 ] !== '' ) lineVertices.push( parts[ 0 ] );
						if ( parts[ 1 ] !== '' ) lineUVs.push( parts[ 1 ] );

					}

				}

				state.addLineGeometry( lineVertices, lineUVs );

			} else if ( lineFirstChar === 'p' ) {

				const lineData = line.slice( 1 ).trim();
				const pointData = lineData.split( ' ' );

				state.addPointGeometry( pointData );

			} else if ( ( result = _object_pattern.exec( line ) ) !== null ) {

				// o object_name
				// or
				// g group_name

				// WORKAROUND: https://bugs.chromium.org/p/v8/issues/detail?id=2869
				// let name = result[ 0 ].slice( 1 ).trim();
				const name = ( ' ' + result[ 0 ].slice( 1 ).trim() ).slice( 1 );

				state.startObject( name );

			} else if ( _material_use_pattern.test( line ) ) {

				// material

				state.object.startMaterial( line.substring( 7 ).trim(), state.materialLibraries );

			} else if ( _material_library_pattern.test( line ) ) {

				// mtl file

				state.materialLibraries.push( line.substring( 7 ).trim() );

			} else if ( _map_use_pattern.test( line ) ) {

				// the line is parsed but ignored since the loader assumes textures are defined MTL files
				// (according to https://www.okino.com/conv/imp_wave.htm, 'usemap' is the old-style Wavefront texture reference method)

				console.warn( 'THREE.OBJLoader: Rendering identifier "usemap" not supported. Textures must be defined in MTL files.' );

			} else if ( lineFirstChar === 's' ) {

				result = line.split( ' ' );

				// smooth shading

				// @todo Handle files that have varying smooth values for a set of faces inside one geometry,
				// but does not define a usemtl for each face set.
				// This should be detected and a dummy material created (later MultiMaterial and geometry groups).
				// This requires some care to not create extra material on each smooth value for "normal" obj files.
				// where explicit usemtl defines geometry groups.
				// Example asset: examples/models/obj/cerberus/Cerberus.obj

				/*
					 * http://paulbourke.net/dataformats/obj/
					 *
					 * From chapter "Grouping" Syntax explanation "s group_number":
					 * "group_number is the smoothing group number. To turn off smoothing groups, use a value of 0 or off.
					 * Polygonal elements use group numbers to put elements in different smoothing groups. For free-form
					 * surfaces, smoothing groups are either turned on or off; there is no difference between values greater
					 * than 0."
					 */
				if ( result.length > 1 ) {

					const value = result[ 1 ].trim().toLowerCase();
					state.object.smooth = ( value !== '0' && value !== 'off' );

				} else {

					// ZBrush can produce "s" lines #11707
					state.object.smooth = true;

				}

				const material = state.object.currentMaterial();
				if ( material ) material.smooth = state.object.smooth;

			} else {

				// Handle null terminated files without exception
				if ( line === '\0' ) continue;

				console.warn( 'THREE.OBJLoader: Unexpected line: "' + line + '"' );

			}

		}

		state.finalize();

		const container = new Group();
		container.materialLibraries = [].concat( state.materialLibraries );

		const hasPrimitives = ! ( state.objects.length === 1 && state.objects[ 0 ].geometry.vertices.length === 0 );

		if ( hasPrimitives === true ) {

			for ( let i = 0, l = state.objects.length; i < l; i ++ ) {

				const object = state.objects[ i ];
				const geometry = object.geometry;
				const materials = object.materials;
				const isLine = ( geometry.type === 'Line' );
				const isPoints = ( geometry.type === 'Points' );
				let hasVertexColors = false;

				// Skip o/g line declarations that did not follow with any faces
				if ( geometry.vertices.length === 0 ) continue;

				const buffergeometry = new BufferGeometry();

				buffergeometry.setAttribute( 'position', new Float32BufferAttribute( geometry.vertices, 3 ) );

				if ( geometry.normals.length > 0 ) {

					buffergeometry.setAttribute( 'normal', new Float32BufferAttribute( geometry.normals, 3 ) );

				}

				if ( geometry.colors.length > 0 ) {

					hasVertexColors = true;
					buffergeometry.setAttribute( 'color', new Float32BufferAttribute( geometry.colors, 3 ) );

				}

				if ( geometry.hasUVIndices === true ) {

					buffergeometry.setAttribute( 'uv', new Float32BufferAttribute( geometry.uvs, 2 ) );

				}

				// Create materials

				const createdMaterials = [];

				for ( let mi = 0, miLen = materials.length; mi < miLen; mi ++ ) {

					const sourceMaterial = materials[ mi ];
					const materialHash = sourceMaterial.name + '_' + sourceMaterial.smooth + '_' + hasVertexColors;
					let material = state.materials[ materialHash ];

					if ( this.materials !== null ) {

						material = this.materials.create( sourceMaterial.name );

						// mtl etc. loaders probably can't create line materials correctly, copy properties to a line material.
						if ( isLine && material && ! ( material instanceof LineBasicMaterial ) ) {

							const materialLine = new LineBasicMaterial();
							Material.prototype.copy.call( materialLine, material );
							materialLine.color.copy( material.color );
							material = materialLine;

						} else if ( isPoints && material && ! ( material instanceof PointsMaterial ) ) {

							const materialPoints = new PointsMaterial( { size: 10, sizeAttenuation: false } );
							Material.prototype.copy.call( materialPoints, material );
							materialPoints.color.copy( material.color );
							materialPoints.map = material.map;
							material = materialPoints;

						}

					}

					if ( material === undefined ) {

						if ( isLine ) {

							material = new LineBasicMaterial();

						} else if ( isPoints ) {

							material = new PointsMaterial( { size: 1, sizeAttenuation: false } );

						} else {

							material = new MeshPhongMaterial();

						}

						material.name = sourceMaterial.name;
						material.flatShading = sourceMaterial.smooth ? false : true;
						material.vertexColors = hasVertexColors;

						state.materials[ materialHash ] = material;

					}

					createdMaterials.push( material );

				}

				// Create mesh

				let mesh;

				if ( createdMaterials.length > 1 ) {

					for ( let mi = 0, miLen = materials.length; mi < miLen; mi ++ ) {

						const sourceMaterial = materials[ mi ];
						buffergeometry.addGroup( sourceMaterial.groupStart, sourceMaterial.groupCount, mi );

					}

					if ( isLine ) {

						mesh = new LineSegments( buffergeometry, createdMaterials );

					} else if ( isPoints ) {

						mesh = new Points( buffergeometry, createdMaterials );

					} else {

						mesh = new Mesh( buffergeometry, createdMaterials );

					}

				} else {

					if ( isLine ) {

						mesh = new LineSegments( buffergeometry, createdMaterials[ 0 ] );

					} else if ( isPoints ) {

						mesh = new Points( buffergeometry, createdMaterials[ 0 ] );

					} else {

						mesh = new Mesh( buffergeometry, createdMaterials[ 0 ] );

					}

				}

				mesh.name = object.name;

				container.add( mesh );

			}

		} else {

			// if there is only the default parser state object with no geometry data, interpret data as point cloud

			if ( state.vertices.length > 0 ) {

				const material = new PointsMaterial( { size: 1, sizeAttenuation: false } );

				const buffergeometry = new BufferGeometry();

				buffergeometry.setAttribute( 'position', new Float32BufferAttribute( state.vertices, 3 ) );

				if ( state.colors.length > 0 && state.colors[ 0 ] !== undefined ) {

					buffergeometry.setAttribute( 'color', new Float32BufferAttribute( state.colors, 3 ) );
					material.vertexColors = true;

				}

				const points = new Points( buffergeometry, material );
				container.add( points );

			}

		}

		return container;

	}
```
</details>


---