[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `USDAParser.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 16 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 54 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/usd/USDAParser.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `ClampToEdgeWrapping` | `three` |
| `Group` | `three` |
| `NoColorSpace` | `three` |
| `Mesh` | `three` |
| `MeshPhysicalMaterial` | `three` |
| `MirroredRepeatWrapping` | `three` |
| `RepeatWrapping` | `three` |
| `SRGBColorSpace` | `three` |
| `TextureLoader` | `three` |
| `Object3D` | `three` |
| `Vector2` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `root` | `{}` | let/var | `{}` | ✗ |
| `string` | `any` | let/var | `null` | ✗ |
| `target` | `{}` | let/var | `root` | ✗ |
| `stack` | `{}[]` | let/var | `[ root ]` | ✗ |
| `group` | `{}` | let/var | `{}` | ✗ |
| `meta` | `{}` | let/var | `{}` | ✗ |
| `group` | `any` | let/var | `target[ string ] \|\| {}` | ✗ |
| `meta` | `{}` | let/var | `{}` | ✗ |
| `reference` | `any` | let/var | `data[ 'prepend references' ]` | ✗ |
| `def` | `string` | let/var | ``def Mesh "${id}"`` | ✗ |
| `object` | `any` | let/var | `data[ name ]` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `indices` | `any` | let/var | `null` | ✗ |
| `counts` | `any` | let/var | `null` | ✗ |
| `uvs` | `any` | let/var | `null` | ✗ |
| `positionsLength` | `number` | let/var | `- 1` | ✗ |
| `attribute` | `any` | let/var | `new BufferAttribute( new Float32Array( positions ), 3 )` | ✗ |
| `attribute` | `any` | let/var | `new BufferAttribute( new Float32Array( uvs ), 2 )` | ✗ |
| `attribute` | `any` | let/var | `new BufferAttribute( new Float32Array( uvs ), 2 )` | ✗ |
| `attribute` | `any` | let/var | `new BufferAttribute( new Float32Array( normals ), 3 )` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `count` | `any` | let/var | `counts[ i ]` | ✗ |
| `stride` | `number` | let/var | `i * count` | ✗ |
| `a` | `any` | let/var | `rawIndices[ stride + 0 ]` | ✗ |
| `b` | `any` | let/var | `rawIndices[ stride + 1 ]` | ✗ |
| `c` | `any` | let/var | `rawIndices[ stride + 2 ]` | ✗ |
| `a` | `any` | let/var | `rawIndices[ stride + 0 ]` | ✗ |
| `b` | `any` | let/var | `rawIndices[ stride + 1 ]` | ✗ |
| `c` | `any` | let/var | `rawIndices[ stride + 2 ]` | ✗ |
| `d` | `any` | let/var | `rawIndices[ stride + 3 ]` | ✗ |
| `array` | `any` | let/var | `attribute.array` | ✗ |
| `itemSize` | `any` | let/var | `attribute.itemSize` | ✗ |
| `array2` | `any` | let/var | `new array.constructor( indices.length * itemSize )` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `index2` | `number` | let/var | `0` | ✗ |
| `reference` | `any` | let/var | `data[ 'rel material:binding' ]` | ✗ |
| `object` | `any` | let/var | `data[ name ]` | ✗ |
| `material` | `any` | let/var | `new MeshPhysicalMaterial()` | ✗ |
| `surface` | `any` | let/var | `undefined` | ✗ |
| `surfaceConnection` | `any` | let/var | `data[ 'token outputs:surface.connect' ]` | ✗ |
| `surfaceName` | `string` | let/var | `match[ 1 ]` | ✗ |
| `path` | `any` | let/var | `surface[ 'color3f inputs:diffuseColor.connect' ]` | ✗ |
| `path` | `any` | let/var | `surface[ 'color3f inputs:emissiveColor.connect' ]` | ✗ |
| `path` | `any` | let/var | `surface[ 'normal3f inputs:normal.connect' ]` | ✗ |
| `path` | `any` | let/var | `surface[ 'float inputs:roughness.connect' ]` | ✗ |
| `path` | `any` | let/var | `surface[ 'float inputs:metallic.connect' ]` | ✗ |
| `path` | `any` | let/var | `surface[ 'float inputs:clearcoat.connect' ]` | ✗ |
| `path` | `any` | let/var | `surface[ 'float inputs:clearcoatRoughness.connect' ]` | ✗ |
| `path` | `any` | let/var | `surface[ 'float inputs:occlusion.connect' ]` | ✗ |
| `object` | `any` | let/var | `data[ name ]` | ✗ |
| `loader` | `any` | let/var | `new TextureLoader()` | ✗ |
| `map` | `{ '"clamp"': any; '"mirror"': any; '"...` | let/var | `{ '"clamp"': ClampToEdgeWrapping, '"mirror"': MirroredRepeatWrapping, '"repea...` | ✗ |
| `mesh` | `any` | let/var | `geometry ? new Mesh( geometry, material ) : new Object3D()` | ✗ |
| `group` | `any` | let/var | `new Group()` | ✗ |


---

## Functions

### `USDAParser.parseText(text: any): {}`

**Parameters:**

- **`text`** `any`

**Returns:** `{}`

**Calls:**

- `text.split`
- `line.includes`
- `line.split`
- `assignment[ 0 ].trim`
- `assignment[ 1 ].trim`
- `rhs.endsWith`
- `stack.push`
- `rhs.slice`
- `line.endsWith`
- `stack.pop`
- `line.split( '(' )[ 0 ].trim`
- `line.trim`

**Internal Comments:**
```
// Parse USDA file
// console.log( line );
// see #28631 (x2)
```

<details><summary>Code</summary>

```typescript
parseText( text ) {

		const root = {};

		const lines = text.split( '\n' );

		let string = null;
		let target = root;

		const stack = [ root ];

		// Parse USDA file

		for ( const line of lines ) {

			// console.log( line );

			if ( line.includes( '=' ) ) {

				const assignment = line.split( '=' );

				const lhs = assignment[ 0 ].trim();
				const rhs = assignment[ 1 ].trim();

				if ( rhs.endsWith( '{' ) ) {

					const group = {};
					stack.push( group );

					target[ lhs ] = group;
					target = group;

				} else if ( rhs.endsWith( '(' ) ) {

					// see #28631

					const values = rhs.slice( 0, - 1 );
					target[ lhs ] = values;

					const meta = {};
					stack.push( meta );

					target = meta;

				} else {

					target[ lhs ] = rhs;

				}

			} else if ( line.endsWith( '{' ) ) {

				const group = target[ string ] || {};
				stack.push( group );

				target[ string ] = group;
				target = group;

			} else if ( line.endsWith( '}' ) ) {

				stack.pop();

				if ( stack.length === 0 ) continue;

				target = stack[ stack.length - 1 ];

			} else if ( line.endsWith( '(' ) ) {

				const meta = {};
				stack.push( meta );

				string = line.split( '(' )[ 0 ].trim() || string;

				target[ string ] = meta;
				target = meta;

			} else if ( line.endsWith( ')' ) ) {

				stack.pop();

				target = stack[ stack.length - 1 ];

			} else {

				string = line.trim();

			}

		}

		return root;

	}
```
</details>

### `USDAParser.parse(text: any, assets: any): any`

**Parameters:**

- **`text`** `any`
- **`assets`** `any`

**Returns:** `any`

**Calls:**

- `this.parseText`
- `reference.split`
- `parts[ 1 ].replace`
- `parts[ 2 ].replace( /^<\//, '' ).replace`
- `findGeometry`
- `name.startsWith`
- `JSON.parse`
- `toTriangleIndices`
- `data[ 'point3f[] points' ].replace`
- `toFlatBufferAttribute`
- `geometry.setAttribute`
- `data[ 'texCoord2f[] primvars:st' ].replace`
- `data[ 'normal3f[] normals' ].replace`
- `Array.from`
- `Array( normals.length / 3 ).keys`
- `geometry.computeVertexNormals`
- `indices.push`
- `console.warn`
- `reference.replace( /^<\//, '' ).replace`
- `id.split`
- `findMaterial`
- `parseFloat`
- `new Vector2().fromArray`
- `data_value[ 'float2 inputs:scale' ].replace`
- `data_value[ 'float2 inputs:translation' ].replace`
- `/(\w+)\.output/.exec`
- `findTexture`
- `/(\w+).output/.exec`
- `buildTexture`
- `setTextureParams`
- `surface[ 'color3f inputs:diffuseColor' ].replace`
- `material.color.fromArray`
- `material.emissive.set`
- `surface[ 'color3f inputs:emissiveColor' ].replace`
- `material.emissive.fromArray`
- `data[ 'asset inputs:file' ].replace( /@*/g, '' ).trim`
- `loader.load`
- `buildGeometry`
- `findMeshGeometry`
- `buildMaterial`
- `findMeshMaterial`
- `data[ 'matrix4d xformOp:transform' ].replace`
- `mesh.matrix.fromArray`
- `mesh.matrix.decompose`
- `buildHierarchy`
- `buildObject`
- `/def Xform "(\w+)"/.test`
- `/def Xform "(\w+)"/.exec`
- `group.add`
- `buildGroup`

**Internal Comments:**
```
// Build scene graph
// index
// face count
// position
// uv
// custom uv index, overwrite uvs with new data (x2)
// normal
// normals require a special treatment in USD
// raw normal and position data have equal length (like produced by USDZExporter)
// unequal length, normals are independent of faceVertexIndices (x2)
// compute flat vertex normals (x4)
// rotation, scale and translation
```

<details><summary>Code</summary>

```typescript
parse( text, assets ) {

		const root = this.parseText( text );

		// Build scene graph

		function findMeshGeometry( data ) {

			if ( ! data ) return undefined;

			if ( 'prepend references' in data ) {

				const reference = data[ 'prepend references' ];
				const parts = reference.split( '@' );
				const path = parts[ 1 ].replace( /^.\//, '' );
				const id = parts[ 2 ].replace( /^<\//, '' ).replace( />$/, '' );

				return findGeometry( assets[ path ], id );

			}

			return findGeometry( data );

		}

		function findGeometry( data, id ) {

			if ( ! data ) return undefined;

			if ( id !== undefined ) {

				const def = `def Mesh "${id}"`;

				if ( def in data ) {

					return data[ def ];

				}

			}

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( 'def Mesh' ) ) {

					return object;

				}


				if ( typeof object === 'object' ) {

					const geometry = findGeometry( object );

					if ( geometry ) return geometry;

				}

			}

		}

		function buildGeometry( data ) {

			if ( ! data ) return undefined;

			const geometry = new BufferGeometry();
			let indices = null;
			let counts = null;
			let uvs = null;

			let positionsLength = - 1;

			// index

			if ( 'int[] faceVertexIndices' in data ) {

				indices = JSON.parse( data[ 'int[] faceVertexIndices' ] );

			}

			// face count

			if ( 'int[] faceVertexCounts' in data ) {

				counts = JSON.parse( data[ 'int[] faceVertexCounts' ] );
				indices = toTriangleIndices( indices, counts );

			}

			// position

			if ( 'point3f[] points' in data ) {

				const positions = JSON.parse( data[ 'point3f[] points' ].replace( /[()]*/g, '' ) );
				positionsLength = positions.length;
				let attribute = new BufferAttribute( new Float32Array( positions ), 3 );

				if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				geometry.setAttribute( 'position', attribute );

			}

			// uv

			if ( 'float2[] primvars:st' in data ) {

				data[ 'texCoord2f[] primvars:st' ] = data[ 'float2[] primvars:st' ];

			}

			if ( 'texCoord2f[] primvars:st' in data ) {

				uvs = JSON.parse( data[ 'texCoord2f[] primvars:st' ].replace( /[()]*/g, '' ) );
				let attribute = new BufferAttribute( new Float32Array( uvs ), 2 );

				if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				geometry.setAttribute( 'uv', attribute );

			}

			if ( 'int[] primvars:st:indices' in data && uvs !== null ) {

				// custom uv index, overwrite uvs with new data

				const attribute = new BufferAttribute( new Float32Array( uvs ), 2 );
				let indices = JSON.parse( data[ 'int[] primvars:st:indices' ] );
				indices = toTriangleIndices( indices, counts );
				geometry.setAttribute( 'uv', toFlatBufferAttribute( attribute, indices ) );

			}

			// normal

			if ( 'normal3f[] normals' in data ) {

				const normals = JSON.parse( data[ 'normal3f[] normals' ].replace( /[()]*/g, '' ) );
				let attribute = new BufferAttribute( new Float32Array( normals ), 3 );

				// normals require a special treatment in USD

				if ( normals.length === positionsLength ) {

					// raw normal and position data have equal length (like produced by USDZExporter)

					if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				} else {

					// unequal length, normals are independent of faceVertexIndices

					let indices = Array.from( Array( normals.length / 3 ).keys() ); // [ 0, 1, 2, 3 ... ]
					indices = toTriangleIndices( indices, counts );
					attribute = toFlatBufferAttribute( attribute, indices );

				}

				geometry.setAttribute( 'normal', attribute );

			} else {

				// compute flat vertex normals

				geometry.computeVertexNormals();

			}

			return geometry;

		}

		function toTriangleIndices( rawIndices, counts ) {

			const indices = [];

			for ( let i = 0; i < counts.length; i ++ ) {

				const count = counts[ i ];

				const stride = i * count;

				if ( count === 3 ) {

					const a = rawIndices[ stride + 0 ];
					const b = rawIndices[ stride + 1 ];
					const c = rawIndices[ stride + 2 ];

					indices.push( a, b, c );

				} else if ( count === 4 ) {

					const a = rawIndices[ stride + 0 ];
					const b = rawIndices[ stride + 1 ];
					const c = rawIndices[ stride + 2 ];
					const d = rawIndices[ stride + 3 ];

					indices.push( a, b, c );
					indices.push( a, c, d );

				} else {

					console.warn( 'THREE.USDZLoader: Face vertex count of %s unsupported.', count );

				}

			}

			return indices;

		}

		function toFlatBufferAttribute( attribute, indices ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				index = indices[ i ] * itemSize;

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new BufferAttribute( array2, itemSize );

		}

		function findMeshMaterial( data ) {

			if ( ! data ) return undefined;

			if ( 'rel material:binding' in data ) {

				const reference = data[ 'rel material:binding' ];
				const id = reference.replace( /^<\//, '' ).replace( />$/, '' );
				const parts = id.split( '/' );

				return findMaterial( root, ` "${ parts[ 1 ] }"` );

			}

			return findMaterial( data );

		}

		function findMaterial( data, id = '' ) {

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( 'def Material' + id ) ) {

					return object;

				}

				if ( typeof object === 'object' ) {

					const material = findMaterial( object, id );

					if ( material ) return material;

				}

			}

		}

		function setTextureParams( map, data_value ) {

			// rotation, scale and translation

			if ( data_value[ 'float inputs:rotation' ] ) {

				map.rotation = parseFloat( data_value[ 'float inputs:rotation' ] );

			}

			if ( data_value[ 'float2 inputs:scale' ] ) {

				map.repeat = new Vector2().fromArray( JSON.parse( '[' + data_value[ 'float2 inputs:scale' ].replace( /[()]*/g, '' ) + ']' ) );

			}

			if ( data_value[ 'float2 inputs:translation' ] ) {

				map.offset = new Vector2().fromArray( JSON.parse( '[' + data_value[ 'float2 inputs:translation' ].replace( /[()]*/g, '' ) + ']' ) );

			}

		}

		function buildMaterial( data ) {

			const material = new MeshPhysicalMaterial();

			if ( data !== undefined ) {

				let surface = undefined;

				const surfaceConnection = data[ 'token outputs:surface.connect' ];

				if ( surfaceConnection ) {

					const match = /(\w+)\.output/.exec( surfaceConnection );

					if ( match ) {

						const surfaceName = match[ 1 ];
						surface = data[ `def Shader "${surfaceName}"` ];

					}

				}

				if ( surface !== undefined ) {

					if ( 'color3f inputs:diffuseColor.connect' in surface ) {

						const path = surface[ 'color3f inputs:diffuseColor.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.map = buildTexture( sampler );
						material.map.colorSpace = SRGBColorSpace;

						if ( 'def Shader "Transform2d_diffuse"' in data ) {

							setTextureParams( material.map, data[ 'def Shader "Transform2d_diffuse"' ] );

						}

					} else if ( 'color3f inputs:diffuseColor' in surface ) {

						const color = surface[ 'color3f inputs:diffuseColor' ].replace( /[()]*/g, '' );
						material.color.fromArray( JSON.parse( '[' + color + ']' ) );

					}

					if ( 'color3f inputs:emissiveColor.connect' in surface ) {

						const path = surface[ 'color3f inputs:emissiveColor.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.emissiveMap = buildTexture( sampler );
						material.emissiveMap.colorSpace = SRGBColorSpace;
						material.emissive.set( 0xffffff );

						if ( 'def Shader "Transform2d_emissive"' in data ) {

							setTextureParams( material.emissiveMap, data[ 'def Shader "Transform2d_emissive"' ] );

						}

					} else if ( 'color3f inputs:emissiveColor' in surface ) {

						const color = surface[ 'color3f inputs:emissiveColor' ].replace( /[()]*/g, '' );
						material.emissive.fromArray( JSON.parse( '[' + color + ']' ) );

					}

					if ( 'normal3f inputs:normal.connect' in surface ) {

						const path = surface[ 'normal3f inputs:normal.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.normalMap = buildTexture( sampler );
						material.normalMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_normal"' in data ) {

							setTextureParams( material.normalMap, data[ 'def Shader "Transform2d_normal"' ] );

						}

					}

					if ( 'float inputs:roughness.connect' in surface ) {

						const path = surface[ 'float inputs:roughness.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.roughness = 1.0;
						material.roughnessMap = buildTexture( sampler );
						material.roughnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_roughness"' in data ) {

							setTextureParams( material.roughnessMap, data[ 'def Shader "Transform2d_roughness"' ] );

						}

					} else if ( 'float inputs:roughness' in surface ) {

						material.roughness = parseFloat( surface[ 'float inputs:roughness' ] );

					}

					if ( 'float inputs:metallic.connect' in surface ) {

						const path = surface[ 'float inputs:metallic.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.metalness = 1.0;
						material.metalnessMap = buildTexture( sampler );
						material.metalnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_metallic"' in data ) {

							setTextureParams( material.metalnessMap, data[ 'def Shader "Transform2d_metallic"' ] );

						}

					} else if ( 'float inputs:metallic' in surface ) {

						material.metalness = parseFloat( surface[ 'float inputs:metallic' ] );

					}

					if ( 'float inputs:clearcoat.connect' in surface ) {

						const path = surface[ 'float inputs:clearcoat.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.clearcoat = 1.0;
						material.clearcoatMap = buildTexture( sampler );
						material.clearcoatMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_clearcoat"' in data ) {

							setTextureParams( material.clearcoatMap, data[ 'def Shader "Transform2d_clearcoat"' ] );

						}

					} else if ( 'float inputs:clearcoat' in surface ) {

						material.clearcoat = parseFloat( surface[ 'float inputs:clearcoat' ] );

					}

					if ( 'float inputs:clearcoatRoughness.connect' in surface ) {

						const path = surface[ 'float inputs:clearcoatRoughness.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.clearcoatRoughness = 1.0;
						material.clearcoatRoughnessMap = buildTexture( sampler );
						material.clearcoatRoughnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_clearcoatRoughness"' in data ) {

							setTextureParams( material.clearcoatRoughnessMap, data[ 'def Shader "Transform2d_clearcoatRoughness"' ] );

						}

					} else if ( 'float inputs:clearcoatRoughness' in surface ) {

						material.clearcoatRoughness = parseFloat( surface[ 'float inputs:clearcoatRoughness' ] );

					}

					if ( 'float inputs:ior' in surface ) {

						material.ior = parseFloat( surface[ 'float inputs:ior' ] );

					}

					if ( 'float inputs:occlusion.connect' in surface ) {

						const path = surface[ 'float inputs:occlusion.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.aoMap = buildTexture( sampler );
						material.aoMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_occlusion"' in data ) {

							setTextureParams( material.aoMap, data[ 'def Shader "Transform2d_occlusion"' ] );

						}

					}

				}

			}

			return material;

		}

		function findTexture( data, id ) {

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( `def Shader "${ id }"` ) ) {

					return object;

				}

				if ( typeof object === 'object' ) {

					const texture = findTexture( object, id );

					if ( texture ) return texture;

				}

			}

		}

		function buildTexture( data ) {

			if ( 'asset inputs:file' in data ) {

				const path = data[ 'asset inputs:file' ].replace( /@*/g, '' ).trim();

				const loader = new TextureLoader();

				const texture = loader.load( assets[ path ] );

				const map = {
					'"clamp"': ClampToEdgeWrapping,
					'"mirror"': MirroredRepeatWrapping,
					'"repeat"': RepeatWrapping
				};

				if ( 'token inputs:wrapS' in data ) {

					texture.wrapS = map[ data[ 'token inputs:wrapS' ] ];

				}

				if ( 'token inputs:wrapT' in data ) {

					texture.wrapT = map[ data[ 'token inputs:wrapT' ] ];

				}

				return texture;

			}

			return null;

		}

		function buildObject( data ) {

			const geometry = buildGeometry( findMeshGeometry( data ) );
			const material = buildMaterial( findMeshMaterial( data ) );

			const mesh = geometry ? new Mesh( geometry, material ) : new Object3D();

			if ( 'matrix4d xformOp:transform' in data ) {

				const array = JSON.parse( '[' + data[ 'matrix4d xformOp:transform' ].replace( /[()]*/g, '' ) + ']' );

				mesh.matrix.fromArray( array );
				mesh.matrix.decompose( mesh.position, mesh.quaternion, mesh.scale );

			}

			return mesh;

		}

		function buildHierarchy( data, group ) {

			for ( const name in data ) {

				if ( name.startsWith( 'def Scope' ) ) {

					buildHierarchy( data[ name ], group );

				} else if ( name.startsWith( 'def Xform' ) ) {

					const mesh = buildObject( data[ name ] );

					if ( /def Xform "(\w+)"/.test( name ) ) {

						mesh.name = /def Xform "(\w+)"/.exec( name )[ 1 ];

					}

					group.add( mesh );

					buildHierarchy( data[ name ], mesh );

				}

			}

		}

		function buildGroup( data ) {

			const group = new Group();

			buildHierarchy( data, group );

			return group;

		}

		return buildGroup( root );

	}
```
</details>

### `findMeshGeometry(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `reference.split`
- `parts[ 1 ].replace`
- `parts[ 2 ].replace( /^<\//, '' ).replace`
- `findGeometry`

<details><summary>Code</summary>

```typescript
function findMeshGeometry( data ) {

			if ( ! data ) return undefined;

			if ( 'prepend references' in data ) {

				const reference = data[ 'prepend references' ];
				const parts = reference.split( '@' );
				const path = parts[ 1 ].replace( /^.\//, '' );
				const id = parts[ 2 ].replace( /^<\//, '' ).replace( />$/, '' );

				return findGeometry( assets[ path ], id );

			}

			return findGeometry( data );

		}
```
</details>

### `findGeometry(data: any, id: any): any`

**Parameters:**

- **`data`** `any`
- **`id`** `any`

**Returns:** `any`

**Calls:**

- `name.startsWith`
- `findGeometry`

<details><summary>Code</summary>

```typescript
function findGeometry( data, id ) {

			if ( ! data ) return undefined;

			if ( id !== undefined ) {

				const def = `def Mesh "${id}"`;

				if ( def in data ) {

					return data[ def ];

				}

			}

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( 'def Mesh' ) ) {

					return object;

				}


				if ( typeof object === 'object' ) {

					const geometry = findGeometry( object );

					if ( geometry ) return geometry;

				}

			}

		}
```
</details>

### `buildGeometry(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `JSON.parse`
- `toTriangleIndices`
- `data[ 'point3f[] points' ].replace`
- `toFlatBufferAttribute`
- `geometry.setAttribute`
- `data[ 'texCoord2f[] primvars:st' ].replace`
- `data[ 'normal3f[] normals' ].replace`
- `Array.from`
- `Array( normals.length / 3 ).keys`
- `geometry.computeVertexNormals`

**Internal Comments:**
```
// index
// face count
// position
// uv
// custom uv index, overwrite uvs with new data (x2)
// normal
// normals require a special treatment in USD
// raw normal and position data have equal length (like produced by USDZExporter)
// unequal length, normals are independent of faceVertexIndices (x2)
// compute flat vertex normals (x4)
```

<details><summary>Code</summary>

```typescript
function buildGeometry( data ) {

			if ( ! data ) return undefined;

			const geometry = new BufferGeometry();
			let indices = null;
			let counts = null;
			let uvs = null;

			let positionsLength = - 1;

			// index

			if ( 'int[] faceVertexIndices' in data ) {

				indices = JSON.parse( data[ 'int[] faceVertexIndices' ] );

			}

			// face count

			if ( 'int[] faceVertexCounts' in data ) {

				counts = JSON.parse( data[ 'int[] faceVertexCounts' ] );
				indices = toTriangleIndices( indices, counts );

			}

			// position

			if ( 'point3f[] points' in data ) {

				const positions = JSON.parse( data[ 'point3f[] points' ].replace( /[()]*/g, '' ) );
				positionsLength = positions.length;
				let attribute = new BufferAttribute( new Float32Array( positions ), 3 );

				if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				geometry.setAttribute( 'position', attribute );

			}

			// uv

			if ( 'float2[] primvars:st' in data ) {

				data[ 'texCoord2f[] primvars:st' ] = data[ 'float2[] primvars:st' ];

			}

			if ( 'texCoord2f[] primvars:st' in data ) {

				uvs = JSON.parse( data[ 'texCoord2f[] primvars:st' ].replace( /[()]*/g, '' ) );
				let attribute = new BufferAttribute( new Float32Array( uvs ), 2 );

				if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				geometry.setAttribute( 'uv', attribute );

			}

			if ( 'int[] primvars:st:indices' in data && uvs !== null ) {

				// custom uv index, overwrite uvs with new data

				const attribute = new BufferAttribute( new Float32Array( uvs ), 2 );
				let indices = JSON.parse( data[ 'int[] primvars:st:indices' ] );
				indices = toTriangleIndices( indices, counts );
				geometry.setAttribute( 'uv', toFlatBufferAttribute( attribute, indices ) );

			}

			// normal

			if ( 'normal3f[] normals' in data ) {

				const normals = JSON.parse( data[ 'normal3f[] normals' ].replace( /[()]*/g, '' ) );
				let attribute = new BufferAttribute( new Float32Array( normals ), 3 );

				// normals require a special treatment in USD

				if ( normals.length === positionsLength ) {

					// raw normal and position data have equal length (like produced by USDZExporter)

					if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				} else {

					// unequal length, normals are independent of faceVertexIndices

					let indices = Array.from( Array( normals.length / 3 ).keys() ); // [ 0, 1, 2, 3 ... ]
					indices = toTriangleIndices( indices, counts );
					attribute = toFlatBufferAttribute( attribute, indices );

				}

				geometry.setAttribute( 'normal', attribute );

			} else {

				// compute flat vertex normals

				geometry.computeVertexNormals();

			}

			return geometry;

		}
```
</details>

### `toTriangleIndices(rawIndices: any, counts: any): any[]`

**Parameters:**

- **`rawIndices`** `any`
- **`counts`** `any`

**Returns:** `any[]`

**Calls:**

- `indices.push`
- `console.warn`

<details><summary>Code</summary>

```typescript
function toTriangleIndices( rawIndices, counts ) {

			const indices = [];

			for ( let i = 0; i < counts.length; i ++ ) {

				const count = counts[ i ];

				const stride = i * count;

				if ( count === 3 ) {

					const a = rawIndices[ stride + 0 ];
					const b = rawIndices[ stride + 1 ];
					const c = rawIndices[ stride + 2 ];

					indices.push( a, b, c );

				} else if ( count === 4 ) {

					const a = rawIndices[ stride + 0 ];
					const b = rawIndices[ stride + 1 ];
					const c = rawIndices[ stride + 2 ];
					const d = rawIndices[ stride + 3 ];

					indices.push( a, b, c );
					indices.push( a, c, d );

				} else {

					console.warn( 'THREE.USDZLoader: Face vertex count of %s unsupported.', count );

				}

			}

			return indices;

		}
```
</details>

### `toFlatBufferAttribute(attribute: any, indices: any): any`

**Parameters:**

- **`attribute`** `any`
- **`indices`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function toFlatBufferAttribute( attribute, indices ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				index = indices[ i ] * itemSize;

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new BufferAttribute( array2, itemSize );

		}
```
</details>

### `findMeshMaterial(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `reference.replace( /^<\//, '' ).replace`
- `id.split`
- `findMaterial`

<details><summary>Code</summary>

```typescript
function findMeshMaterial( data ) {

			if ( ! data ) return undefined;

			if ( 'rel material:binding' in data ) {

				const reference = data[ 'rel material:binding' ];
				const id = reference.replace( /^<\//, '' ).replace( />$/, '' );
				const parts = id.split( '/' );

				return findMaterial( root, ` "${ parts[ 1 ] }"` );

			}

			return findMaterial( data );

		}
```
</details>

### `findMaterial(data: any, id: string): any`

**Parameters:**

- **`data`** `any`
- **`id`** `string`

**Returns:** `any`

**Calls:**

- `name.startsWith`
- `findMaterial`

<details><summary>Code</summary>

```typescript
function findMaterial( data, id = '' ) {

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( 'def Material' + id ) ) {

					return object;

				}

				if ( typeof object === 'object' ) {

					const material = findMaterial( object, id );

					if ( material ) return material;

				}

			}

		}
```
</details>

### `setTextureParams(map: any, data_value: any): void`

**Parameters:**

- **`map`** `any`
- **`data_value`** `any`

**Returns:** `void`

**Calls:**

- `parseFloat`
- `new Vector2().fromArray`
- `JSON.parse`
- `data_value[ 'float2 inputs:scale' ].replace`
- `data_value[ 'float2 inputs:translation' ].replace`

**Internal Comments:**
```
// rotation, scale and translation
```

<details><summary>Code</summary>

```typescript
function setTextureParams( map, data_value ) {

			// rotation, scale and translation

			if ( data_value[ 'float inputs:rotation' ] ) {

				map.rotation = parseFloat( data_value[ 'float inputs:rotation' ] );

			}

			if ( data_value[ 'float2 inputs:scale' ] ) {

				map.repeat = new Vector2().fromArray( JSON.parse( '[' + data_value[ 'float2 inputs:scale' ].replace( /[()]*/g, '' ) + ']' ) );

			}

			if ( data_value[ 'float2 inputs:translation' ] ) {

				map.offset = new Vector2().fromArray( JSON.parse( '[' + data_value[ 'float2 inputs:translation' ].replace( /[()]*/g, '' ) + ']' ) );

			}

		}
```
</details>

### `buildMaterial(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `/(\w+)\.output/.exec`
- `findTexture`
- `/(\w+).output/.exec`
- `buildTexture`
- `setTextureParams`
- `surface[ 'color3f inputs:diffuseColor' ].replace`
- `material.color.fromArray`
- `JSON.parse`
- `material.emissive.set`
- `surface[ 'color3f inputs:emissiveColor' ].replace`
- `material.emissive.fromArray`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function buildMaterial( data ) {

			const material = new MeshPhysicalMaterial();

			if ( data !== undefined ) {

				let surface = undefined;

				const surfaceConnection = data[ 'token outputs:surface.connect' ];

				if ( surfaceConnection ) {

					const match = /(\w+)\.output/.exec( surfaceConnection );

					if ( match ) {

						const surfaceName = match[ 1 ];
						surface = data[ `def Shader "${surfaceName}"` ];

					}

				}

				if ( surface !== undefined ) {

					if ( 'color3f inputs:diffuseColor.connect' in surface ) {

						const path = surface[ 'color3f inputs:diffuseColor.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.map = buildTexture( sampler );
						material.map.colorSpace = SRGBColorSpace;

						if ( 'def Shader "Transform2d_diffuse"' in data ) {

							setTextureParams( material.map, data[ 'def Shader "Transform2d_diffuse"' ] );

						}

					} else if ( 'color3f inputs:diffuseColor' in surface ) {

						const color = surface[ 'color3f inputs:diffuseColor' ].replace( /[()]*/g, '' );
						material.color.fromArray( JSON.parse( '[' + color + ']' ) );

					}

					if ( 'color3f inputs:emissiveColor.connect' in surface ) {

						const path = surface[ 'color3f inputs:emissiveColor.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.emissiveMap = buildTexture( sampler );
						material.emissiveMap.colorSpace = SRGBColorSpace;
						material.emissive.set( 0xffffff );

						if ( 'def Shader "Transform2d_emissive"' in data ) {

							setTextureParams( material.emissiveMap, data[ 'def Shader "Transform2d_emissive"' ] );

						}

					} else if ( 'color3f inputs:emissiveColor' in surface ) {

						const color = surface[ 'color3f inputs:emissiveColor' ].replace( /[()]*/g, '' );
						material.emissive.fromArray( JSON.parse( '[' + color + ']' ) );

					}

					if ( 'normal3f inputs:normal.connect' in surface ) {

						const path = surface[ 'normal3f inputs:normal.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.normalMap = buildTexture( sampler );
						material.normalMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_normal"' in data ) {

							setTextureParams( material.normalMap, data[ 'def Shader "Transform2d_normal"' ] );

						}

					}

					if ( 'float inputs:roughness.connect' in surface ) {

						const path = surface[ 'float inputs:roughness.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.roughness = 1.0;
						material.roughnessMap = buildTexture( sampler );
						material.roughnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_roughness"' in data ) {

							setTextureParams( material.roughnessMap, data[ 'def Shader "Transform2d_roughness"' ] );

						}

					} else if ( 'float inputs:roughness' in surface ) {

						material.roughness = parseFloat( surface[ 'float inputs:roughness' ] );

					}

					if ( 'float inputs:metallic.connect' in surface ) {

						const path = surface[ 'float inputs:metallic.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.metalness = 1.0;
						material.metalnessMap = buildTexture( sampler );
						material.metalnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_metallic"' in data ) {

							setTextureParams( material.metalnessMap, data[ 'def Shader "Transform2d_metallic"' ] );

						}

					} else if ( 'float inputs:metallic' in surface ) {

						material.metalness = parseFloat( surface[ 'float inputs:metallic' ] );

					}

					if ( 'float inputs:clearcoat.connect' in surface ) {

						const path = surface[ 'float inputs:clearcoat.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.clearcoat = 1.0;
						material.clearcoatMap = buildTexture( sampler );
						material.clearcoatMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_clearcoat"' in data ) {

							setTextureParams( material.clearcoatMap, data[ 'def Shader "Transform2d_clearcoat"' ] );

						}

					} else if ( 'float inputs:clearcoat' in surface ) {

						material.clearcoat = parseFloat( surface[ 'float inputs:clearcoat' ] );

					}

					if ( 'float inputs:clearcoatRoughness.connect' in surface ) {

						const path = surface[ 'float inputs:clearcoatRoughness.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.clearcoatRoughness = 1.0;
						material.clearcoatRoughnessMap = buildTexture( sampler );
						material.clearcoatRoughnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_clearcoatRoughness"' in data ) {

							setTextureParams( material.clearcoatRoughnessMap, data[ 'def Shader "Transform2d_clearcoatRoughness"' ] );

						}

					} else if ( 'float inputs:clearcoatRoughness' in surface ) {

						material.clearcoatRoughness = parseFloat( surface[ 'float inputs:clearcoatRoughness' ] );

					}

					if ( 'float inputs:ior' in surface ) {

						material.ior = parseFloat( surface[ 'float inputs:ior' ] );

					}

					if ( 'float inputs:occlusion.connect' in surface ) {

						const path = surface[ 'float inputs:occlusion.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.aoMap = buildTexture( sampler );
						material.aoMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_occlusion"' in data ) {

							setTextureParams( material.aoMap, data[ 'def Shader "Transform2d_occlusion"' ] );

						}

					}

				}

			}

			return material;

		}
```
</details>

### `findTexture(data: any, id: any): any`

**Parameters:**

- **`data`** `any`
- **`id`** `any`

**Returns:** `any`

**Calls:**

- `name.startsWith`
- `findTexture`

<details><summary>Code</summary>

```typescript
function findTexture( data, id ) {

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( `def Shader "${ id }"` ) ) {

					return object;

				}

				if ( typeof object === 'object' ) {

					const texture = findTexture( object, id );

					if ( texture ) return texture;

				}

			}

		}
```
</details>

### `buildTexture(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `data[ 'asset inputs:file' ].replace( /@*/g, '' ).trim`
- `loader.load`

<details><summary>Code</summary>

```typescript
function buildTexture( data ) {

			if ( 'asset inputs:file' in data ) {

				const path = data[ 'asset inputs:file' ].replace( /@*/g, '' ).trim();

				const loader = new TextureLoader();

				const texture = loader.load( assets[ path ] );

				const map = {
					'"clamp"': ClampToEdgeWrapping,
					'"mirror"': MirroredRepeatWrapping,
					'"repeat"': RepeatWrapping
				};

				if ( 'token inputs:wrapS' in data ) {

					texture.wrapS = map[ data[ 'token inputs:wrapS' ] ];

				}

				if ( 'token inputs:wrapT' in data ) {

					texture.wrapT = map[ data[ 'token inputs:wrapT' ] ];

				}

				return texture;

			}

			return null;

		}
```
</details>

### `buildObject(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `buildGeometry`
- `findMeshGeometry`
- `buildMaterial`
- `findMeshMaterial`
- `JSON.parse`
- `data[ 'matrix4d xformOp:transform' ].replace`
- `mesh.matrix.fromArray`
- `mesh.matrix.decompose`

<details><summary>Code</summary>

```typescript
function buildObject( data ) {

			const geometry = buildGeometry( findMeshGeometry( data ) );
			const material = buildMaterial( findMeshMaterial( data ) );

			const mesh = geometry ? new Mesh( geometry, material ) : new Object3D();

			if ( 'matrix4d xformOp:transform' in data ) {

				const array = JSON.parse( '[' + data[ 'matrix4d xformOp:transform' ].replace( /[()]*/g, '' ) + ']' );

				mesh.matrix.fromArray( array );
				mesh.matrix.decompose( mesh.position, mesh.quaternion, mesh.scale );

			}

			return mesh;

		}
```
</details>

### `buildHierarchy(data: any, group: any): void`

**Parameters:**

- **`data`** `any`
- **`group`** `any`

**Returns:** `void`

**Calls:**

- `name.startsWith`
- `buildHierarchy`
- `buildObject`
- `/def Xform "(\w+)"/.test`
- `/def Xform "(\w+)"/.exec`
- `group.add`

<details><summary>Code</summary>

```typescript
function buildHierarchy( data, group ) {

			for ( const name in data ) {

				if ( name.startsWith( 'def Scope' ) ) {

					buildHierarchy( data[ name ], group );

				} else if ( name.startsWith( 'def Xform' ) ) {

					const mesh = buildObject( data[ name ] );

					if ( /def Xform "(\w+)"/.test( name ) ) {

						mesh.name = /def Xform "(\w+)"/.exec( name )[ 1 ];

					}

					group.add( mesh );

					buildHierarchy( data[ name ], mesh );

				}

			}

		}
```
</details>

### `buildGroup(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `buildHierarchy`

<details><summary>Code</summary>

```typescript
function buildGroup( data ) {

			const group = new Group();

			buildHierarchy( data, group );

			return group;

		}
```
</details>


---

## Classes

### `USDAParser`

<details><summary>Class Code</summary>

```ts
class USDAParser {

	parseText( text ) {

		const root = {};

		const lines = text.split( '\n' );

		let string = null;
		let target = root;

		const stack = [ root ];

		// Parse USDA file

		for ( const line of lines ) {

			// console.log( line );

			if ( line.includes( '=' ) ) {

				const assignment = line.split( '=' );

				const lhs = assignment[ 0 ].trim();
				const rhs = assignment[ 1 ].trim();

				if ( rhs.endsWith( '{' ) ) {

					const group = {};
					stack.push( group );

					target[ lhs ] = group;
					target = group;

				} else if ( rhs.endsWith( '(' ) ) {

					// see #28631

					const values = rhs.slice( 0, - 1 );
					target[ lhs ] = values;

					const meta = {};
					stack.push( meta );

					target = meta;

				} else {

					target[ lhs ] = rhs;

				}

			} else if ( line.endsWith( '{' ) ) {

				const group = target[ string ] || {};
				stack.push( group );

				target[ string ] = group;
				target = group;

			} else if ( line.endsWith( '}' ) ) {

				stack.pop();

				if ( stack.length === 0 ) continue;

				target = stack[ stack.length - 1 ];

			} else if ( line.endsWith( '(' ) ) {

				const meta = {};
				stack.push( meta );

				string = line.split( '(' )[ 0 ].trim() || string;

				target[ string ] = meta;
				target = meta;

			} else if ( line.endsWith( ')' ) ) {

				stack.pop();

				target = stack[ stack.length - 1 ];

			} else {

				string = line.trim();

			}

		}

		return root;

	}

	parse( text, assets ) {

		const root = this.parseText( text );

		// Build scene graph

		function findMeshGeometry( data ) {

			if ( ! data ) return undefined;

			if ( 'prepend references' in data ) {

				const reference = data[ 'prepend references' ];
				const parts = reference.split( '@' );
				const path = parts[ 1 ].replace( /^.\//, '' );
				const id = parts[ 2 ].replace( /^<\//, '' ).replace( />$/, '' );

				return findGeometry( assets[ path ], id );

			}

			return findGeometry( data );

		}

		function findGeometry( data, id ) {

			if ( ! data ) return undefined;

			if ( id !== undefined ) {

				const def = `def Mesh "${id}"`;

				if ( def in data ) {

					return data[ def ];

				}

			}

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( 'def Mesh' ) ) {

					return object;

				}


				if ( typeof object === 'object' ) {

					const geometry = findGeometry( object );

					if ( geometry ) return geometry;

				}

			}

		}

		function buildGeometry( data ) {

			if ( ! data ) return undefined;

			const geometry = new BufferGeometry();
			let indices = null;
			let counts = null;
			let uvs = null;

			let positionsLength = - 1;

			// index

			if ( 'int[] faceVertexIndices' in data ) {

				indices = JSON.parse( data[ 'int[] faceVertexIndices' ] );

			}

			// face count

			if ( 'int[] faceVertexCounts' in data ) {

				counts = JSON.parse( data[ 'int[] faceVertexCounts' ] );
				indices = toTriangleIndices( indices, counts );

			}

			// position

			if ( 'point3f[] points' in data ) {

				const positions = JSON.parse( data[ 'point3f[] points' ].replace( /[()]*/g, '' ) );
				positionsLength = positions.length;
				let attribute = new BufferAttribute( new Float32Array( positions ), 3 );

				if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				geometry.setAttribute( 'position', attribute );

			}

			// uv

			if ( 'float2[] primvars:st' in data ) {

				data[ 'texCoord2f[] primvars:st' ] = data[ 'float2[] primvars:st' ];

			}

			if ( 'texCoord2f[] primvars:st' in data ) {

				uvs = JSON.parse( data[ 'texCoord2f[] primvars:st' ].replace( /[()]*/g, '' ) );
				let attribute = new BufferAttribute( new Float32Array( uvs ), 2 );

				if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				geometry.setAttribute( 'uv', attribute );

			}

			if ( 'int[] primvars:st:indices' in data && uvs !== null ) {

				// custom uv index, overwrite uvs with new data

				const attribute = new BufferAttribute( new Float32Array( uvs ), 2 );
				let indices = JSON.parse( data[ 'int[] primvars:st:indices' ] );
				indices = toTriangleIndices( indices, counts );
				geometry.setAttribute( 'uv', toFlatBufferAttribute( attribute, indices ) );

			}

			// normal

			if ( 'normal3f[] normals' in data ) {

				const normals = JSON.parse( data[ 'normal3f[] normals' ].replace( /[()]*/g, '' ) );
				let attribute = new BufferAttribute( new Float32Array( normals ), 3 );

				// normals require a special treatment in USD

				if ( normals.length === positionsLength ) {

					// raw normal and position data have equal length (like produced by USDZExporter)

					if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				} else {

					// unequal length, normals are independent of faceVertexIndices

					let indices = Array.from( Array( normals.length / 3 ).keys() ); // [ 0, 1, 2, 3 ... ]
					indices = toTriangleIndices( indices, counts );
					attribute = toFlatBufferAttribute( attribute, indices );

				}

				geometry.setAttribute( 'normal', attribute );

			} else {

				// compute flat vertex normals

				geometry.computeVertexNormals();

			}

			return geometry;

		}

		function toTriangleIndices( rawIndices, counts ) {

			const indices = [];

			for ( let i = 0; i < counts.length; i ++ ) {

				const count = counts[ i ];

				const stride = i * count;

				if ( count === 3 ) {

					const a = rawIndices[ stride + 0 ];
					const b = rawIndices[ stride + 1 ];
					const c = rawIndices[ stride + 2 ];

					indices.push( a, b, c );

				} else if ( count === 4 ) {

					const a = rawIndices[ stride + 0 ];
					const b = rawIndices[ stride + 1 ];
					const c = rawIndices[ stride + 2 ];
					const d = rawIndices[ stride + 3 ];

					indices.push( a, b, c );
					indices.push( a, c, d );

				} else {

					console.warn( 'THREE.USDZLoader: Face vertex count of %s unsupported.', count );

				}

			}

			return indices;

		}

		function toFlatBufferAttribute( attribute, indices ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				index = indices[ i ] * itemSize;

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new BufferAttribute( array2, itemSize );

		}

		function findMeshMaterial( data ) {

			if ( ! data ) return undefined;

			if ( 'rel material:binding' in data ) {

				const reference = data[ 'rel material:binding' ];
				const id = reference.replace( /^<\//, '' ).replace( />$/, '' );
				const parts = id.split( '/' );

				return findMaterial( root, ` "${ parts[ 1 ] }"` );

			}

			return findMaterial( data );

		}

		function findMaterial( data, id = '' ) {

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( 'def Material' + id ) ) {

					return object;

				}

				if ( typeof object === 'object' ) {

					const material = findMaterial( object, id );

					if ( material ) return material;

				}

			}

		}

		function setTextureParams( map, data_value ) {

			// rotation, scale and translation

			if ( data_value[ 'float inputs:rotation' ] ) {

				map.rotation = parseFloat( data_value[ 'float inputs:rotation' ] );

			}

			if ( data_value[ 'float2 inputs:scale' ] ) {

				map.repeat = new Vector2().fromArray( JSON.parse( '[' + data_value[ 'float2 inputs:scale' ].replace( /[()]*/g, '' ) + ']' ) );

			}

			if ( data_value[ 'float2 inputs:translation' ] ) {

				map.offset = new Vector2().fromArray( JSON.parse( '[' + data_value[ 'float2 inputs:translation' ].replace( /[()]*/g, '' ) + ']' ) );

			}

		}

		function buildMaterial( data ) {

			const material = new MeshPhysicalMaterial();

			if ( data !== undefined ) {

				let surface = undefined;

				const surfaceConnection = data[ 'token outputs:surface.connect' ];

				if ( surfaceConnection ) {

					const match = /(\w+)\.output/.exec( surfaceConnection );

					if ( match ) {

						const surfaceName = match[ 1 ];
						surface = data[ `def Shader "${surfaceName}"` ];

					}

				}

				if ( surface !== undefined ) {

					if ( 'color3f inputs:diffuseColor.connect' in surface ) {

						const path = surface[ 'color3f inputs:diffuseColor.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.map = buildTexture( sampler );
						material.map.colorSpace = SRGBColorSpace;

						if ( 'def Shader "Transform2d_diffuse"' in data ) {

							setTextureParams( material.map, data[ 'def Shader "Transform2d_diffuse"' ] );

						}

					} else if ( 'color3f inputs:diffuseColor' in surface ) {

						const color = surface[ 'color3f inputs:diffuseColor' ].replace( /[()]*/g, '' );
						material.color.fromArray( JSON.parse( '[' + color + ']' ) );

					}

					if ( 'color3f inputs:emissiveColor.connect' in surface ) {

						const path = surface[ 'color3f inputs:emissiveColor.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.emissiveMap = buildTexture( sampler );
						material.emissiveMap.colorSpace = SRGBColorSpace;
						material.emissive.set( 0xffffff );

						if ( 'def Shader "Transform2d_emissive"' in data ) {

							setTextureParams( material.emissiveMap, data[ 'def Shader "Transform2d_emissive"' ] );

						}

					} else if ( 'color3f inputs:emissiveColor' in surface ) {

						const color = surface[ 'color3f inputs:emissiveColor' ].replace( /[()]*/g, '' );
						material.emissive.fromArray( JSON.parse( '[' + color + ']' ) );

					}

					if ( 'normal3f inputs:normal.connect' in surface ) {

						const path = surface[ 'normal3f inputs:normal.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.normalMap = buildTexture( sampler );
						material.normalMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_normal"' in data ) {

							setTextureParams( material.normalMap, data[ 'def Shader "Transform2d_normal"' ] );

						}

					}

					if ( 'float inputs:roughness.connect' in surface ) {

						const path = surface[ 'float inputs:roughness.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.roughness = 1.0;
						material.roughnessMap = buildTexture( sampler );
						material.roughnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_roughness"' in data ) {

							setTextureParams( material.roughnessMap, data[ 'def Shader "Transform2d_roughness"' ] );

						}

					} else if ( 'float inputs:roughness' in surface ) {

						material.roughness = parseFloat( surface[ 'float inputs:roughness' ] );

					}

					if ( 'float inputs:metallic.connect' in surface ) {

						const path = surface[ 'float inputs:metallic.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.metalness = 1.0;
						material.metalnessMap = buildTexture( sampler );
						material.metalnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_metallic"' in data ) {

							setTextureParams( material.metalnessMap, data[ 'def Shader "Transform2d_metallic"' ] );

						}

					} else if ( 'float inputs:metallic' in surface ) {

						material.metalness = parseFloat( surface[ 'float inputs:metallic' ] );

					}

					if ( 'float inputs:clearcoat.connect' in surface ) {

						const path = surface[ 'float inputs:clearcoat.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.clearcoat = 1.0;
						material.clearcoatMap = buildTexture( sampler );
						material.clearcoatMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_clearcoat"' in data ) {

							setTextureParams( material.clearcoatMap, data[ 'def Shader "Transform2d_clearcoat"' ] );

						}

					} else if ( 'float inputs:clearcoat' in surface ) {

						material.clearcoat = parseFloat( surface[ 'float inputs:clearcoat' ] );

					}

					if ( 'float inputs:clearcoatRoughness.connect' in surface ) {

						const path = surface[ 'float inputs:clearcoatRoughness.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.clearcoatRoughness = 1.0;
						material.clearcoatRoughnessMap = buildTexture( sampler );
						material.clearcoatRoughnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_clearcoatRoughness"' in data ) {

							setTextureParams( material.clearcoatRoughnessMap, data[ 'def Shader "Transform2d_clearcoatRoughness"' ] );

						}

					} else if ( 'float inputs:clearcoatRoughness' in surface ) {

						material.clearcoatRoughness = parseFloat( surface[ 'float inputs:clearcoatRoughness' ] );

					}

					if ( 'float inputs:ior' in surface ) {

						material.ior = parseFloat( surface[ 'float inputs:ior' ] );

					}

					if ( 'float inputs:occlusion.connect' in surface ) {

						const path = surface[ 'float inputs:occlusion.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.aoMap = buildTexture( sampler );
						material.aoMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_occlusion"' in data ) {

							setTextureParams( material.aoMap, data[ 'def Shader "Transform2d_occlusion"' ] );

						}

					}

				}

			}

			return material;

		}

		function findTexture( data, id ) {

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( `def Shader "${ id }"` ) ) {

					return object;

				}

				if ( typeof object === 'object' ) {

					const texture = findTexture( object, id );

					if ( texture ) return texture;

				}

			}

		}

		function buildTexture( data ) {

			if ( 'asset inputs:file' in data ) {

				const path = data[ 'asset inputs:file' ].replace( /@*/g, '' ).trim();

				const loader = new TextureLoader();

				const texture = loader.load( assets[ path ] );

				const map = {
					'"clamp"': ClampToEdgeWrapping,
					'"mirror"': MirroredRepeatWrapping,
					'"repeat"': RepeatWrapping
				};

				if ( 'token inputs:wrapS' in data ) {

					texture.wrapS = map[ data[ 'token inputs:wrapS' ] ];

				}

				if ( 'token inputs:wrapT' in data ) {

					texture.wrapT = map[ data[ 'token inputs:wrapT' ] ];

				}

				return texture;

			}

			return null;

		}

		function buildObject( data ) {

			const geometry = buildGeometry( findMeshGeometry( data ) );
			const material = buildMaterial( findMeshMaterial( data ) );

			const mesh = geometry ? new Mesh( geometry, material ) : new Object3D();

			if ( 'matrix4d xformOp:transform' in data ) {

				const array = JSON.parse( '[' + data[ 'matrix4d xformOp:transform' ].replace( /[()]*/g, '' ) + ']' );

				mesh.matrix.fromArray( array );
				mesh.matrix.decompose( mesh.position, mesh.quaternion, mesh.scale );

			}

			return mesh;

		}

		function buildHierarchy( data, group ) {

			for ( const name in data ) {

				if ( name.startsWith( 'def Scope' ) ) {

					buildHierarchy( data[ name ], group );

				} else if ( name.startsWith( 'def Xform' ) ) {

					const mesh = buildObject( data[ name ] );

					if ( /def Xform "(\w+)"/.test( name ) ) {

						mesh.name = /def Xform "(\w+)"/.exec( name )[ 1 ];

					}

					group.add( mesh );

					buildHierarchy( data[ name ], mesh );

				}

			}

		}

		function buildGroup( data ) {

			const group = new Group();

			buildHierarchy( data, group );

			return group;

		}

		return buildGroup( root );

	}

}
```
</details>

#### Methods

##### `parseText(text: any): {}`

<details><summary>Code</summary>

```ts
parseText( text ) {

		const root = {};

		const lines = text.split( '\n' );

		let string = null;
		let target = root;

		const stack = [ root ];

		// Parse USDA file

		for ( const line of lines ) {

			// console.log( line );

			if ( line.includes( '=' ) ) {

				const assignment = line.split( '=' );

				const lhs = assignment[ 0 ].trim();
				const rhs = assignment[ 1 ].trim();

				if ( rhs.endsWith( '{' ) ) {

					const group = {};
					stack.push( group );

					target[ lhs ] = group;
					target = group;

				} else if ( rhs.endsWith( '(' ) ) {

					// see #28631

					const values = rhs.slice( 0, - 1 );
					target[ lhs ] = values;

					const meta = {};
					stack.push( meta );

					target = meta;

				} else {

					target[ lhs ] = rhs;

				}

			} else if ( line.endsWith( '{' ) ) {

				const group = target[ string ] || {};
				stack.push( group );

				target[ string ] = group;
				target = group;

			} else if ( line.endsWith( '}' ) ) {

				stack.pop();

				if ( stack.length === 0 ) continue;

				target = stack[ stack.length - 1 ];

			} else if ( line.endsWith( '(' ) ) {

				const meta = {};
				stack.push( meta );

				string = line.split( '(' )[ 0 ].trim() || string;

				target[ string ] = meta;
				target = meta;

			} else if ( line.endsWith( ')' ) ) {

				stack.pop();

				target = stack[ stack.length - 1 ];

			} else {

				string = line.trim();

			}

		}

		return root;

	}
```
</details>

##### `parse(text: any, assets: any): any`

<details><summary>Code</summary>

```ts
parse( text, assets ) {

		const root = this.parseText( text );

		// Build scene graph

		function findMeshGeometry( data ) {

			if ( ! data ) return undefined;

			if ( 'prepend references' in data ) {

				const reference = data[ 'prepend references' ];
				const parts = reference.split( '@' );
				const path = parts[ 1 ].replace( /^.\//, '' );
				const id = parts[ 2 ].replace( /^<\//, '' ).replace( />$/, '' );

				return findGeometry( assets[ path ], id );

			}

			return findGeometry( data );

		}

		function findGeometry( data, id ) {

			if ( ! data ) return undefined;

			if ( id !== undefined ) {

				const def = `def Mesh "${id}"`;

				if ( def in data ) {

					return data[ def ];

				}

			}

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( 'def Mesh' ) ) {

					return object;

				}


				if ( typeof object === 'object' ) {

					const geometry = findGeometry( object );

					if ( geometry ) return geometry;

				}

			}

		}

		function buildGeometry( data ) {

			if ( ! data ) return undefined;

			const geometry = new BufferGeometry();
			let indices = null;
			let counts = null;
			let uvs = null;

			let positionsLength = - 1;

			// index

			if ( 'int[] faceVertexIndices' in data ) {

				indices = JSON.parse( data[ 'int[] faceVertexIndices' ] );

			}

			// face count

			if ( 'int[] faceVertexCounts' in data ) {

				counts = JSON.parse( data[ 'int[] faceVertexCounts' ] );
				indices = toTriangleIndices( indices, counts );

			}

			// position

			if ( 'point3f[] points' in data ) {

				const positions = JSON.parse( data[ 'point3f[] points' ].replace( /[()]*/g, '' ) );
				positionsLength = positions.length;
				let attribute = new BufferAttribute( new Float32Array( positions ), 3 );

				if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				geometry.setAttribute( 'position', attribute );

			}

			// uv

			if ( 'float2[] primvars:st' in data ) {

				data[ 'texCoord2f[] primvars:st' ] = data[ 'float2[] primvars:st' ];

			}

			if ( 'texCoord2f[] primvars:st' in data ) {

				uvs = JSON.parse( data[ 'texCoord2f[] primvars:st' ].replace( /[()]*/g, '' ) );
				let attribute = new BufferAttribute( new Float32Array( uvs ), 2 );

				if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				geometry.setAttribute( 'uv', attribute );

			}

			if ( 'int[] primvars:st:indices' in data && uvs !== null ) {

				// custom uv index, overwrite uvs with new data

				const attribute = new BufferAttribute( new Float32Array( uvs ), 2 );
				let indices = JSON.parse( data[ 'int[] primvars:st:indices' ] );
				indices = toTriangleIndices( indices, counts );
				geometry.setAttribute( 'uv', toFlatBufferAttribute( attribute, indices ) );

			}

			// normal

			if ( 'normal3f[] normals' in data ) {

				const normals = JSON.parse( data[ 'normal3f[] normals' ].replace( /[()]*/g, '' ) );
				let attribute = new BufferAttribute( new Float32Array( normals ), 3 );

				// normals require a special treatment in USD

				if ( normals.length === positionsLength ) {

					// raw normal and position data have equal length (like produced by USDZExporter)

					if ( indices !== null ) attribute = toFlatBufferAttribute( attribute, indices );

				} else {

					// unequal length, normals are independent of faceVertexIndices

					let indices = Array.from( Array( normals.length / 3 ).keys() ); // [ 0, 1, 2, 3 ... ]
					indices = toTriangleIndices( indices, counts );
					attribute = toFlatBufferAttribute( attribute, indices );

				}

				geometry.setAttribute( 'normal', attribute );

			} else {

				// compute flat vertex normals

				geometry.computeVertexNormals();

			}

			return geometry;

		}

		function toTriangleIndices( rawIndices, counts ) {

			const indices = [];

			for ( let i = 0; i < counts.length; i ++ ) {

				const count = counts[ i ];

				const stride = i * count;

				if ( count === 3 ) {

					const a = rawIndices[ stride + 0 ];
					const b = rawIndices[ stride + 1 ];
					const c = rawIndices[ stride + 2 ];

					indices.push( a, b, c );

				} else if ( count === 4 ) {

					const a = rawIndices[ stride + 0 ];
					const b = rawIndices[ stride + 1 ];
					const c = rawIndices[ stride + 2 ];
					const d = rawIndices[ stride + 3 ];

					indices.push( a, b, c );
					indices.push( a, c, d );

				} else {

					console.warn( 'THREE.USDZLoader: Face vertex count of %s unsupported.', count );

				}

			}

			return indices;

		}

		function toFlatBufferAttribute( attribute, indices ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				index = indices[ i ] * itemSize;

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new BufferAttribute( array2, itemSize );

		}

		function findMeshMaterial( data ) {

			if ( ! data ) return undefined;

			if ( 'rel material:binding' in data ) {

				const reference = data[ 'rel material:binding' ];
				const id = reference.replace( /^<\//, '' ).replace( />$/, '' );
				const parts = id.split( '/' );

				return findMaterial( root, ` "${ parts[ 1 ] }"` );

			}

			return findMaterial( data );

		}

		function findMaterial( data, id = '' ) {

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( 'def Material' + id ) ) {

					return object;

				}

				if ( typeof object === 'object' ) {

					const material = findMaterial( object, id );

					if ( material ) return material;

				}

			}

		}

		function setTextureParams( map, data_value ) {

			// rotation, scale and translation

			if ( data_value[ 'float inputs:rotation' ] ) {

				map.rotation = parseFloat( data_value[ 'float inputs:rotation' ] );

			}

			if ( data_value[ 'float2 inputs:scale' ] ) {

				map.repeat = new Vector2().fromArray( JSON.parse( '[' + data_value[ 'float2 inputs:scale' ].replace( /[()]*/g, '' ) + ']' ) );

			}

			if ( data_value[ 'float2 inputs:translation' ] ) {

				map.offset = new Vector2().fromArray( JSON.parse( '[' + data_value[ 'float2 inputs:translation' ].replace( /[()]*/g, '' ) + ']' ) );

			}

		}

		function buildMaterial( data ) {

			const material = new MeshPhysicalMaterial();

			if ( data !== undefined ) {

				let surface = undefined;

				const surfaceConnection = data[ 'token outputs:surface.connect' ];

				if ( surfaceConnection ) {

					const match = /(\w+)\.output/.exec( surfaceConnection );

					if ( match ) {

						const surfaceName = match[ 1 ];
						surface = data[ `def Shader "${surfaceName}"` ];

					}

				}

				if ( surface !== undefined ) {

					if ( 'color3f inputs:diffuseColor.connect' in surface ) {

						const path = surface[ 'color3f inputs:diffuseColor.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.map = buildTexture( sampler );
						material.map.colorSpace = SRGBColorSpace;

						if ( 'def Shader "Transform2d_diffuse"' in data ) {

							setTextureParams( material.map, data[ 'def Shader "Transform2d_diffuse"' ] );

						}

					} else if ( 'color3f inputs:diffuseColor' in surface ) {

						const color = surface[ 'color3f inputs:diffuseColor' ].replace( /[()]*/g, '' );
						material.color.fromArray( JSON.parse( '[' + color + ']' ) );

					}

					if ( 'color3f inputs:emissiveColor.connect' in surface ) {

						const path = surface[ 'color3f inputs:emissiveColor.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.emissiveMap = buildTexture( sampler );
						material.emissiveMap.colorSpace = SRGBColorSpace;
						material.emissive.set( 0xffffff );

						if ( 'def Shader "Transform2d_emissive"' in data ) {

							setTextureParams( material.emissiveMap, data[ 'def Shader "Transform2d_emissive"' ] );

						}

					} else if ( 'color3f inputs:emissiveColor' in surface ) {

						const color = surface[ 'color3f inputs:emissiveColor' ].replace( /[()]*/g, '' );
						material.emissive.fromArray( JSON.parse( '[' + color + ']' ) );

					}

					if ( 'normal3f inputs:normal.connect' in surface ) {

						const path = surface[ 'normal3f inputs:normal.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.normalMap = buildTexture( sampler );
						material.normalMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_normal"' in data ) {

							setTextureParams( material.normalMap, data[ 'def Shader "Transform2d_normal"' ] );

						}

					}

					if ( 'float inputs:roughness.connect' in surface ) {

						const path = surface[ 'float inputs:roughness.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.roughness = 1.0;
						material.roughnessMap = buildTexture( sampler );
						material.roughnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_roughness"' in data ) {

							setTextureParams( material.roughnessMap, data[ 'def Shader "Transform2d_roughness"' ] );

						}

					} else if ( 'float inputs:roughness' in surface ) {

						material.roughness = parseFloat( surface[ 'float inputs:roughness' ] );

					}

					if ( 'float inputs:metallic.connect' in surface ) {

						const path = surface[ 'float inputs:metallic.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.metalness = 1.0;
						material.metalnessMap = buildTexture( sampler );
						material.metalnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_metallic"' in data ) {

							setTextureParams( material.metalnessMap, data[ 'def Shader "Transform2d_metallic"' ] );

						}

					} else if ( 'float inputs:metallic' in surface ) {

						material.metalness = parseFloat( surface[ 'float inputs:metallic' ] );

					}

					if ( 'float inputs:clearcoat.connect' in surface ) {

						const path = surface[ 'float inputs:clearcoat.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.clearcoat = 1.0;
						material.clearcoatMap = buildTexture( sampler );
						material.clearcoatMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_clearcoat"' in data ) {

							setTextureParams( material.clearcoatMap, data[ 'def Shader "Transform2d_clearcoat"' ] );

						}

					} else if ( 'float inputs:clearcoat' in surface ) {

						material.clearcoat = parseFloat( surface[ 'float inputs:clearcoat' ] );

					}

					if ( 'float inputs:clearcoatRoughness.connect' in surface ) {

						const path = surface[ 'float inputs:clearcoatRoughness.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.clearcoatRoughness = 1.0;
						material.clearcoatRoughnessMap = buildTexture( sampler );
						material.clearcoatRoughnessMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_clearcoatRoughness"' in data ) {

							setTextureParams( material.clearcoatRoughnessMap, data[ 'def Shader "Transform2d_clearcoatRoughness"' ] );

						}

					} else if ( 'float inputs:clearcoatRoughness' in surface ) {

						material.clearcoatRoughness = parseFloat( surface[ 'float inputs:clearcoatRoughness' ] );

					}

					if ( 'float inputs:ior' in surface ) {

						material.ior = parseFloat( surface[ 'float inputs:ior' ] );

					}

					if ( 'float inputs:occlusion.connect' in surface ) {

						const path = surface[ 'float inputs:occlusion.connect' ];
						const sampler = findTexture( root, /(\w+).output/.exec( path )[ 1 ] );

						material.aoMap = buildTexture( sampler );
						material.aoMap.colorSpace = NoColorSpace;

						if ( 'def Shader "Transform2d_occlusion"' in data ) {

							setTextureParams( material.aoMap, data[ 'def Shader "Transform2d_occlusion"' ] );

						}

					}

				}

			}

			return material;

		}

		function findTexture( data, id ) {

			for ( const name in data ) {

				const object = data[ name ];

				if ( name.startsWith( `def Shader "${ id }"` ) ) {

					return object;

				}

				if ( typeof object === 'object' ) {

					const texture = findTexture( object, id );

					if ( texture ) return texture;

				}

			}

		}

		function buildTexture( data ) {

			if ( 'asset inputs:file' in data ) {

				const path = data[ 'asset inputs:file' ].replace( /@*/g, '' ).trim();

				const loader = new TextureLoader();

				const texture = loader.load( assets[ path ] );

				const map = {
					'"clamp"': ClampToEdgeWrapping,
					'"mirror"': MirroredRepeatWrapping,
					'"repeat"': RepeatWrapping
				};

				if ( 'token inputs:wrapS' in data ) {

					texture.wrapS = map[ data[ 'token inputs:wrapS' ] ];

				}

				if ( 'token inputs:wrapT' in data ) {

					texture.wrapT = map[ data[ 'token inputs:wrapT' ] ];

				}

				return texture;

			}

			return null;

		}

		function buildObject( data ) {

			const geometry = buildGeometry( findMeshGeometry( data ) );
			const material = buildMaterial( findMeshMaterial( data ) );

			const mesh = geometry ? new Mesh( geometry, material ) : new Object3D();

			if ( 'matrix4d xformOp:transform' in data ) {

				const array = JSON.parse( '[' + data[ 'matrix4d xformOp:transform' ].replace( /[()]*/g, '' ) + ']' );

				mesh.matrix.fromArray( array );
				mesh.matrix.decompose( mesh.position, mesh.quaternion, mesh.scale );

			}

			return mesh;

		}

		function buildHierarchy( data, group ) {

			for ( const name in data ) {

				if ( name.startsWith( 'def Scope' ) ) {

					buildHierarchy( data[ name ], group );

				} else if ( name.startsWith( 'def Xform' ) ) {

					const mesh = buildObject( data[ name ] );

					if ( /def Xform "(\w+)"/.test( name ) ) {

						mesh.name = /def Xform "(\w+)"/.exec( name )[ 1 ];

					}

					group.add( mesh );

					buildHierarchy( data[ name ], mesh );

				}

			}

		}

		function buildGroup( data ) {

			const group = new Group();

			buildHierarchy( data, group );

			return group;

		}

		return buildGroup( root );

	}
```
</details>


---