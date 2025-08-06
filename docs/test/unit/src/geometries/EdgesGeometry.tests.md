[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `EdgesGeometry.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 30 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/geometries/EdgesGeometry.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `EdgesGeometry` | `../../../../src/geometries/EdgesGeometry.js` |
| `BufferGeometry` | `../../../../src/core/BufferGeometry.js` |
| `BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Scene` | `../../../../src/scenes/Scene.js` |
| `Mesh` | `../../../../src/objects/Mesh.js` |
| `LineSegments` | `../../../../src/objects/LineSegments.js` |
| `LineBasicMaterial` | `../../../../src/materials/LineBasicMaterial.js` |
| `WebGLRenderer` | `../../../../src/renderers/WebGLRenderer.js` |
| `PerspectiveCamera` | `../../../../src/cameras/PerspectiveCamera.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geom` | `any` | let/var | `geoms[ i ]` | ✗ |
| `numBefore` | `any` | let/var | `idxList.length` | ✗ |
| `egeom` | `EdgesGeometry` | let/var | `new EdgesGeometry( geom )` | ✗ |
| `geom` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `indexTable` | `any[]` | let/var | `[]` | ✗ |
| `numTris` | `number` | let/var | `idxList.length / 3` | ✗ |
| `numVerts` | `number` | let/var | `0` | ✗ |
| `indices` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( numTris * 3 )` | ✗ |
| `vertices` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( vertList.length * 3 )` | ✗ |
| `idx` | `any` | let/var | `idxList[ 3 * i + j ]` | ✗ |
| `v` | `any` | let/var | `vertList[ idx ]` | ✗ |
| `numTris` | `number` | let/var | `geometry.index.count / 3` | ✗ |
| `start` | `number` | let/var | `i * 3` | ✗ |
| `count` | `3` | let/var | `3` | ✗ |
| `indices` | `any` | let/var | `geom.index` | ✗ |
| `DEBUG` | `false` | let/var | `false` | ✗ |
| `renderer` | `any` | let/var | `*not shown*` | ✗ |
| `camera` | `any` | let/var | `*not shown*` | ✗ |
| `scene` | `Scene` | let/var | `new Scene()` | ✗ |
| `xoffset` | `number` | let/var | `0` | ✗ |
| `mesh` | `Mesh` | let/var | `new Mesh( geom, undefined )` | ✗ |
| `edges` | `LineSegments` | let/var | `new LineSegments( egeom, new LineBasicMaterial( { color: 'black' } ) )` | ✗ |
| `width` | `600` | let/var | `600` | ✗ |
| `height` | `480` | let/var | `480` | ✗ |
| `controls` | `any` | let/var | `new THREE.OrbitControls( camera, renderer.domElement )` | ✗ |
| `vertList` | `Vector3[]` | let/var | `[ new Vector3( 0, 0, 0 ), new Vector3( 1, 0, 0 ), new Vector3( 1, 1, 0 ), new...` | ✗ |
| `object` | `EdgesGeometry` | let/var | `new EdgesGeometry()` | ✗ |
| `object` | `EdgesGeometry` | let/var | `new EdgesGeometry()` | ✗ |
| `object` | `EdgesGeometry` | let/var | `new EdgesGeometry()` | ✗ |
| `vertList` | `Vector3[]` | let/var | `[ new Vector3( 0, 0, 0 ), new Vector3( 1, 0, 0 ), new Vector3( 1, 1, 0 ), new...` | ✗ |


---

## Functions

### `testEdges(vertList: any, idxList: any, numAfter: any, assert: any): void`

**Parameters:**

- **`vertList`** `any`
- **`idxList`** `any`
- **`numAfter`** `any`
- **`assert`** `any`

**Returns:** `void`

**Calls:**

- `createGeometries`
- `assert.equal`
- `countEdges`
- `output`

<details><summary>Code</summary>

```typescript
function testEdges( vertList, idxList, numAfter, assert ) {

	const geoms = createGeometries( vertList, idxList );

	for ( let i = 0; i < geoms.length; i ++ ) {

		const geom = geoms[ i ];

		const numBefore = idxList.length;
		assert.equal( countEdges( geom ), numBefore, 'Edges before!' );

		const egeom = new EdgesGeometry( geom );

		assert.equal( countEdges( egeom ), numAfter, 'Edges after!' );
		output( geom, egeom );

	}

}
```
</details>

### `createGeometries(vertList: any, idxList: any): any[]`

**Parameters:**

- **`vertList`** `any`
- **`idxList`** `any`

**Returns:** `any[]`

**Calls:**

- `createIndexedBufferGeometry`
- `addDrawCalls`
- `geomIB.clone`

<details><summary>Code</summary>

```typescript
function createGeometries( vertList, idxList ) {

	const geomIB = createIndexedBufferGeometry( vertList, idxList );
	const geomDC = addDrawCalls( geomIB.clone() );
	return [ geomIB, geomDC ];

}
```
</details>

### `createIndexedBufferGeometry(vertList: any, idxList: any): BufferGeometry`

**Parameters:**

- **`vertList`** `any`
- **`idxList`** `any`

**Returns:** `BufferGeometry`

**Calls:**

- `vertices.subarray`
- `geom.setIndex`
- `geom.setAttribute`

<details><summary>Code</summary>

```typescript
function createIndexedBufferGeometry( vertList, idxList ) {

	const geom = new BufferGeometry();

	const indexTable = [];
	const numTris = idxList.length / 3;
	let numVerts = 0;

	const indices = new Uint32Array( numTris * 3 );
	let vertices = new Float32Array( vertList.length * 3 );

	for ( let i = 0; i < numTris; i ++ ) {

		for ( let j = 0; j < 3; j ++ ) {

			const idx = idxList[ 3 * i + j ];
			if ( indexTable[ idx ] === undefined ) {

				const v = vertList[ idx ];
				vertices[ 3 * numVerts ] = v.x;
				vertices[ 3 * numVerts + 1 ] = v.y;
				vertices[ 3 * numVerts + 2 ] = v.z;

				indexTable[ idx ] = numVerts;

				numVerts ++;

			}

			indices[ 3 * i + j ] = indexTable[ idx ];

		}

	}

	vertices = vertices.subarray( 0, 3 * numVerts );

	geom.setIndex( new BufferAttribute( indices, 1 ) );
	geom.setAttribute( 'position', new BufferAttribute( vertices, 3 ) );

	return geom;

}
```
</details>

### `addDrawCalls(geometry: any): any`

**Parameters:**

- **`geometry`** `any`

**Returns:** `any`

**Calls:**

- `geometry.addGroup`

<details><summary>Code</summary>

```typescript
function addDrawCalls( geometry ) {

	const numTris = geometry.index.count / 3;

	for ( let i = 0; i < numTris; i ++ ) {

		const start = i * 3;
		const count = 3;

		geometry.addGroup( start, count );

	}

	return geometry;

}
```
</details>

### `countEdges(geom: any): any`

**Parameters:**

- **`geom`** `any`

**Returns:** `any`

**Calls:**

- `geom.getAttribute`

<details><summary>Code</summary>

```typescript
function countEdges( geom ) {

	if ( geom instanceof EdgesGeometry ) {

		return geom.getAttribute( 'position' ).count / 2;

	}

	if ( geom.faces !== undefined ) {

		return geom.faces.length * 3;

	}

	const indices = geom.index;
	if ( indices ) {

		return indices.count;

	}

	return geom.getAttribute( 'position' ).count;

}
```
</details>

### `output(geom: any, egeom: any): void`

**Parameters:**

- **`geom`** `any`
- **`egeom`** `any`

**Returns:** `void`

**Calls:**

- `initDebug`
- `mesh.position.setX`
- `edges.position.setX`
- `scene.add`

<details><summary>Code</summary>

```typescript
function output( geom, egeom ) {

	if ( DEBUG !== true ) return;

	if ( ! renderer ) initDebug();

	const mesh = new Mesh( geom, undefined );
	const edges = new LineSegments( egeom, new LineBasicMaterial( { color: 'black' } ) );

	mesh.position.setX( xoffset );
	edges.position.setX( xoffset ++ );
	scene.add( mesh );
	scene.add( edges );

	if ( scene.children.length % 8 === 0 ) {

		xoffset += 2;

	}

}
```
</details>

### `initDebug(): void`

**Returns:** `void`

**Calls:**

- `renderer.setSize`
- `renderer.setClearColor`
- `camera.lookAt`
- `document.body.appendChild`
- `animate`
- `requestAnimationFrame`
- `controls.update`
- `renderer.render`

<details><summary>Code</summary>

```typescript
function initDebug() {

	renderer = new WebGLRenderer( {

		antialias: true

	} );

	const width = 600;
	const height = 480;

	renderer.setSize( width, height );
	renderer.setClearColor( 0xCCCCCC );

	camera = new PerspectiveCamera( 45, width / height, 1, 100 );
	camera.position.x = 30;
	camera.position.z = 40;
	camera.lookAt( new Vector3( 30, 0, 0 ) );

	document.body.appendChild( renderer.domElement );

	const controls = new THREE.OrbitControls( camera, renderer.domElement ); // TODO: please do somethings for that -_-'
	controls.target = new Vector3( 30, 0, 0 );

	animate();

	function animate() {

		requestAnimationFrame( animate );

		controls.update();

		renderer.render( scene, camera );

	}

}
```
</details>

### `animate(): void`

**Returns:** `void`

**Calls:**

- `requestAnimationFrame`
- `controls.update`
- `renderer.render`

<details><summary>Code</summary>

```typescript
function animate() {

		requestAnimationFrame( animate );

		controls.update();

		renderer.render( scene, camera );

	}
```
</details>


---