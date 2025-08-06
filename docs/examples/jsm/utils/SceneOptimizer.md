[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SceneOptimizer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 25 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/utils/SceneOptimizer.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `hash` | `number` | let/var | `0` | ✗ |
| `uintArray` | `any` | let/var | `*not shown*` | ✗ |
| `byte` | `number` | let/var | `uintArray[ i ]` | ✗ |
| `mapProps` | `string[]` | let/var | `[ 'map', 'alphaMap', 'aoMap', 'bumpMap', 'displacementMap', 'emissiveMap', 'e...` | ✗ |
| `map` | `any` | let/var | `material[ prop ]` | ✗ |
| `emissiveHash` | `any` | let/var | `material.emissive ? material.emissive.getHexString() : 0` | ✗ |
| `attenuationHash` | `any` | let/var | `material.attenuationColor ? material.attenuationColor.getHexString() : 0` | ✗ |
| `sheenColorHash` | `any` | let/var | `material.sheenColor ? material.sheenColor.getHexString() : 0` | ✗ |
| `attribute` | `any` | let/var | `geometry.attributes[ name ]` | ✗ |
| `indexHash` | `number \| "noIndex"` | let/var | `geometry.index ? this._bufferToHash( geometry.index.array ) : 'noIndex'` | ✗ |
| `batchGroups` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `singleGroups` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `uniqueGeometries` | `Set<any>` | let/var | `new Set()` | ✗ |
| `meshesToRemove` | `Set<any>` | let/var | `new Set()` | ✗ |
| `maxGeometries` | `any` | let/var | `group.totalInstances` | ✗ |
| `batchedMaterial` | `any` | let/var | `new group.materialProps.constructor( group.materialProps )` | ✗ |
| `batchedMesh` | `any` | let/var | `new THREE.BatchedMesh( maxGeometries, maxVertices, maxIndices, batchedMaterial )` | ✗ |
| `referenceMesh` | `any` | let/var | `group.meshes[ 0 ]` | ✗ |
| `geometryIds` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `inverseParentMatrix` | `any` | let/var | `new THREE.Matrix4()` | ✗ |
| `localMatrix` | `any` | let/var | `new THREE.Matrix4()` | ✗ |
| `children` | `any[]` | let/var | `[ ...object.children ]` | ✗ |
| `totalOriginalMeshes` | `number` | let/var | `meshesToRemove.size + singleGroups.size` | ✗ |
| `totalFinalMeshes` | `number` | let/var | `batchGroups.size + singleGroups.size` | ✗ |
| `stats` | `{ originalMeshes: number; batchedMesh...` | let/var | `{ originalMeshes: totalOriginalMeshes, batchedMeshes: batchGroups.size, singl...` | ✗ |


---

## Functions

### `SceneOptimizer._bufferToHash(buffer: any): number`

**Parameters:**

- **`buffer`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
_bufferToHash( buffer ) {

		let hash = 0;
		if ( buffer.byteLength !== 0 ) {

			let uintArray;
			if ( buffer.buffer ) {

				uintArray = new Uint8Array(
					buffer.buffer,
					buffer.byteOffset,
					buffer.byteLength
				);

			} else {

				uintArray = new Uint8Array( buffer );

			}

			for ( let i = 0; i < buffer.byteLength; i ++ ) {

				const byte = uintArray[ i ];
				hash = ( hash << 5 ) - hash + byte;
				hash |= 0;

			}

		}

		return hash;

	}
```
</details>

### `SceneOptimizer._getMaterialPropertiesHash(material: any): string`

**Parameters:**

- **`material`** `any`

**Returns:** `string`

**Calls:**

- `mapProps
			.map( ( prop ) => {

				const map = material[ prop ];
				if ( ! map ) return 0;
				return `${map.uuid}_${map.offset.x}_${map.offset.y}_${map.repeat.x}_${map.repeat.y}_${map.rotation}`;

			} )
			.join`
- `[
			'transparent',
			'opacity',
			'alphaTest',
			'alphaToCoverage',
			'side',
			'vertexColors',
			'visible',
			'blending',
			'wireframe',
			'flatShading',
			'premultipliedAlpha',
			'dithering',
			'toneMapped',
			'depthTest',
			'depthWrite',
			'metalness',
			'roughness',
			'clearcoat',
			'clearcoatRoughness',
			'sheen',
			'sheenRoughness',
			'transmission',
			'thickness',
			'attenuationDistance',
			'ior',
			'iridescence',
			'iridescenceIOR',
			'iridescenceThicknessRange',
			'reflectivity',
		]
			.map( ( prop ) => {

				if ( typeof material[ prop ] === 'undefined' ) return 0;
				if ( material[ prop ] === null ) return 0;
				return material[ prop ].toString();

			} )
			.join`
- `material.emissive.getHexString`
- `material.attenuationColor.getHexString`
- `material.sheenColor.getHexString`
- `[
			material.type,
			physicalProps,
			mapHash,
			emissiveHash,
			attenuationHash,
			sheenColorHash,
		].join`

<details><summary>Code</summary>

```typescript
_getMaterialPropertiesHash( material ) {

		const mapProps = [
			'map',
			'alphaMap',
			'aoMap',
			'bumpMap',
			'displacementMap',
			'emissiveMap',
			'envMap',
			'lightMap',
			'metalnessMap',
			'normalMap',
			'roughnessMap',
		];

		const mapHash = mapProps
			.map( ( prop ) => {

				const map = material[ prop ];
				if ( ! map ) return 0;
				return `${map.uuid}_${map.offset.x}_${map.offset.y}_${map.repeat.x}_${map.repeat.y}_${map.rotation}`;

			} )
			.join( '|' );

		const physicalProps = [
			'transparent',
			'opacity',
			'alphaTest',
			'alphaToCoverage',
			'side',
			'vertexColors',
			'visible',
			'blending',
			'wireframe',
			'flatShading',
			'premultipliedAlpha',
			'dithering',
			'toneMapped',
			'depthTest',
			'depthWrite',
			'metalness',
			'roughness',
			'clearcoat',
			'clearcoatRoughness',
			'sheen',
			'sheenRoughness',
			'transmission',
			'thickness',
			'attenuationDistance',
			'ior',
			'iridescence',
			'iridescenceIOR',
			'iridescenceThicknessRange',
			'reflectivity',
		]
			.map( ( prop ) => {

				if ( typeof material[ prop ] === 'undefined' ) return 0;
				if ( material[ prop ] === null ) return 0;
				return material[ prop ].toString();

			} )
			.join( '|' );

		const emissiveHash = material.emissive ? material.emissive.getHexString() : 0;
		const attenuationHash = material.attenuationColor
			? material.attenuationColor.getHexString()
			: 0;
		const sheenColorHash = material.sheenColor
			? material.sheenColor.getHexString()
			: 0;

		return [
			material.type,
			physicalProps,
			mapHash,
			emissiveHash,
			attenuationHash,
			sheenColorHash,
		].join( '_' );

	}
```
</details>

### `SceneOptimizer._getAttributesSignature(geometry: any): string`

**Parameters:**

- **`geometry`** `any`

**Returns:** `string`

**Calls:**

- `Object.keys( geometry.attributes )
			.sort()
			.map( ( name ) => {

				const attribute = geometry.attributes[ name ];
				return `${name}_${attribute.itemSize}_${attribute.normalized}`;

			} )
			.join`

<details><summary>Code</summary>

```typescript
_getAttributesSignature( geometry ) {

		return Object.keys( geometry.attributes )
			.sort()
			.map( ( name ) => {

				const attribute = geometry.attributes[ name ];
				return `${name}_${attribute.itemSize}_${attribute.normalized}`;

			} )
			.join( '|' );

	}
```
</details>

### `SceneOptimizer._getGeometryHash(geometry: any): string`

**Parameters:**

- **`geometry`** `any`

**Returns:** `string`

**Calls:**

- `this._bufferToHash`
- `this._getAttributesSignature`

<details><summary>Code</summary>

```typescript
_getGeometryHash( geometry ) {

		const indexHash = geometry.index
			? this._bufferToHash( geometry.index.array )
			: 'noIndex';
		const positionHash = this._bufferToHash( geometry.attributes.position.array );
		const attributesSignature = this._getAttributesSignature( geometry );
		return `${indexHash}_${positionHash}_${attributesSignature}`;

	}
```
</details>

### `SceneOptimizer._getBatchKey(materialProps: any, attributesSignature: any): string`

**Parameters:**

- **`materialProps`** `any`
- **`attributesSignature`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
_getBatchKey( materialProps, attributesSignature ) {

		return `${materialProps}_${attributesSignature}`;

	}
```
</details>

### `SceneOptimizer._analyzeModel(): { batchGroups: Map<any, any>; singleGroups: Map<any, any>; uniqueGeometries: number; }`

**Returns:** `{ batchGroups: Map<any, any>; singleGroups: Map<any, any>; uniqueGeometries: number; }`

**Calls:**

- `this.scene.updateMatrixWorld`
- `this.scene.traverse`
- `this._getMaterialPropertiesHash`
- `this._getAttributesSignature`
- `this._getBatchKey`
- `this._getGeometryHash`
- `uniqueGeometries.add`
- `batchGroups.has`
- `batchGroups.set`
- `node.material.clone`
- `batchGroups.get`
- `group.meshes.push`
- `group.geometryStats.has`
- `group.geometryStats.set`
- `group.geometryStats.get`
- `singleGroups.set`
- `batchGroups.delete`

**Internal Comments:**
```
// Move single instance groups to singleGroups
```

<details><summary>Code</summary>

```typescript
_analyzeModel() {

		const batchGroups = new Map();
		const singleGroups = new Map();
		const uniqueGeometries = new Set();

		this.scene.updateMatrixWorld( true );
		this.scene.traverse( ( node ) => {

			if ( ! node.isMesh ) return;

			const materialProps = this._getMaterialPropertiesHash( node.material );
			const attributesSignature = this._getAttributesSignature( node.geometry );
			const batchKey = this._getBatchKey( materialProps, attributesSignature );
			const geometryHash = this._getGeometryHash( node.geometry );
			uniqueGeometries.add( geometryHash );

			if ( ! batchGroups.has( batchKey ) ) {

				batchGroups.set( batchKey, {
					meshes: [],
					geometryStats: new Map(),
					totalInstances: 0,
					materialProps: node.material.clone(),
				} );

			}

			const group = batchGroups.get( batchKey );
			group.meshes.push( node );
			group.totalInstances ++;

			if ( ! group.geometryStats.has( geometryHash ) ) {

				group.geometryStats.set( geometryHash, {
					count: 0,
					vertices: node.geometry.attributes.position.count,
					indices: node.geometry.index ? node.geometry.index.count : 0,
					geometry: node.geometry,
				} );

			}

			group.geometryStats.get( geometryHash ).count ++;

		} );

		// Move single instance groups to singleGroups
		for ( const [ batchKey, group ] of batchGroups ) {

			if ( group.totalInstances === 1 ) {

				singleGroups.set( batchKey, group );
				batchGroups.delete( batchKey );

			}

		}

		return { batchGroups, singleGroups, uniqueGeometries: uniqueGeometries.size };

	}
```
</details>

### `SceneOptimizer._createBatchedMeshes(batchGroups: any): Set<any>`

**Parameters:**

- **`batchGroups`** `any`

**Returns:** `Set<any>`

**Calls:**

- `Array.from( group.geometryStats.values() ).reduce`
- `batchedMaterial.color.set`
- `referenceMesh.parent.updateWorldMatrix`
- `inverseParentMatrix.copy( referenceMesh.parent.matrixWorld ).invert`
- `this._getGeometryHash`
- `geometryIds.has`
- `geometryIds.set`
- `batchedMesh.addGeometry`
- `geometryIds.get`
- `batchedMesh.addInstance`
- `mesh.updateWorldMatrix`
- `localMatrix.copy`
- `localMatrix.premultiply`
- `batchedMesh.setMatrixAt`
- `batchedMesh.setColorAt`
- `meshesToRemove.add`
- `referenceMesh.parent.add`

**Internal Comments:**
```
// Reset color to white, color will be set per instance (x5)
```

<details><summary>Code</summary>

```typescript
_createBatchedMeshes( batchGroups ) {

		const meshesToRemove = new Set();

		for ( const [ , group ] of batchGroups ) {

			const maxGeometries = group.totalInstances;
			const maxVertices = Array.from( group.geometryStats.values() ).reduce(
				( sum, stats ) => sum + stats.vertices,
				0
			);
			const maxIndices = Array.from( group.geometryStats.values() ).reduce(
				( sum, stats ) => sum + stats.indices,
				0
			);

			const batchedMaterial = new group.materialProps.constructor( group.materialProps );

			if ( batchedMaterial.color !== undefined ) {

				// Reset color to white, color will be set per instance
				batchedMaterial.color.set( 1, 1, 1 );

			}

			const batchedMesh = new THREE.BatchedMesh(
				maxGeometries,
				maxVertices,
				maxIndices,
				batchedMaterial
			);

			const referenceMesh = group.meshes[ 0 ];
			batchedMesh.name = `${referenceMesh.name}_batch`;

			const geometryIds = new Map();
			const inverseParentMatrix = new THREE.Matrix4();

			if ( referenceMesh.parent ) {

				referenceMesh.parent.updateWorldMatrix( true, false );
				inverseParentMatrix.copy( referenceMesh.parent.matrixWorld ).invert();

			}

			for ( const mesh of group.meshes ) {

				const geometryHash = this._getGeometryHash( mesh.geometry );

				if ( ! geometryIds.has( geometryHash ) ) {

					geometryIds.set( geometryHash, batchedMesh.addGeometry( mesh.geometry ) );

				}

				const geometryId = geometryIds.get( geometryHash );
				const instanceId = batchedMesh.addInstance( geometryId );

				const localMatrix = new THREE.Matrix4();
				mesh.updateWorldMatrix( true, false );
				localMatrix.copy( mesh.matrixWorld );
				if ( referenceMesh.parent ) {

					localMatrix.premultiply( inverseParentMatrix );

				}

				batchedMesh.setMatrixAt( instanceId, localMatrix );
				batchedMesh.setColorAt( instanceId, mesh.material.color );

				meshesToRemove.add( mesh );

			}

			if ( referenceMesh.parent ) {

				referenceMesh.parent.add( batchedMesh );

			}

		}

		return meshesToRemove;

	}
```
</details>

### `SceneOptimizer.removeEmptyNodes(object: Object3D): void`

**JSDoc:**
```typescript
/**
	 * Removes empty nodes from all descendants of the given 3D object.
	 *
	 * @param {Object3D} object - The 3D object to process.
	 */
```

**Parameters:**

- **`object`** `Object3D`

**Returns:** `void`

**Calls:**

- `this.removeEmptyNodes`
- `object.remove`

<details><summary>Code</summary>

```typescript
removeEmptyNodes( object ) {

		const children = [ ...object.children ];

		for ( const child of children ) {

			this.removeEmptyNodes( child );

			if ( ( child instanceof THREE.Group || child.constructor === THREE.Object3D )
                && child.children.length === 0 ) {

				object.remove( child );

			}

		}

	}
```
</details>

### `SceneOptimizer.disposeMeshes(meshesToRemove: Set<Mesh>): void`

**JSDoc:**
```typescript
/**
	 * Removes the given array of meshes from the scene.
	 *
	 * @param {Set<Mesh>} meshesToRemove - The meshes to remove.
	 */
```

**Parameters:**

- **`meshesToRemove`** `Set<Mesh>`

**Returns:** `void`

**Calls:**

- `meshesToRemove.forEach`
- `mesh.parent.remove`
- `mesh.geometry.dispose`
- `Array.isArray`
- `mesh.material.forEach`
- `m.dispose`
- `mesh.material.dispose`

<details><summary>Code</summary>

```typescript
disposeMeshes( meshesToRemove ) {

		meshesToRemove.forEach( ( mesh ) => {

			if ( mesh.parent ) {

				mesh.parent.remove( mesh );

			}

			if ( mesh.geometry ) mesh.geometry.dispose();
			if ( mesh.material ) {

				if ( Array.isArray( mesh.material ) ) {

					mesh.material.forEach( ( m ) => m.dispose() );

				} else {

					mesh.material.dispose();

				}

			}

		} );

	}
```
</details>

### `SceneOptimizer._logDebugInfo(stats: any): void`

**Parameters:**

- **`stats`** `any`

**Returns:** `void`

**Calls:**

- `console.group`
- `console.log`
- `console.groupEnd`

<details><summary>Code</summary>

```typescript
_logDebugInfo( stats ) {

		console.group( 'Scene Optimization Results' );
		console.log( `Original meshes: ${stats.originalMeshes}` );
		console.log( `Batched into: ${stats.batchedMeshes} BatchedMesh` );
		console.log( `Single meshes: ${stats.singleMeshes} Mesh` );
		console.log( `Total draw calls: ${stats.drawCalls}` );
		console.log( `Reduction Ratio: ${stats.reductionRatio}% fewer draw calls` );
		console.groupEnd();

	}
```
</details>

### `SceneOptimizer.toBatchedMesh(): Scene`

**JSDoc:**
```typescript
/**
	 * Performs the auto-baching by identifying groups of meshes in the scene
	 * that can be represented as a single {@link BatchedMesh}. The method modifies
	 * the scene by adding instances of `BatchedMesh` and removing the now redundant
	 * individual meshes.
	 *
	 * @return {Scene} The optimized scene.
	 */
```

**Returns:** `Scene`

**Calls:**

- `this._analyzeModel`
- `this._createBatchedMeshes`
- `this.disposeMeshes`
- `this.removeEmptyNodes`
- `( ( 1 - totalFinalMeshes / totalOriginalMeshes ) * 100 ).toFixed`
- `this._logDebugInfo`

<details><summary>Code</summary>

```typescript
toBatchedMesh() {

		const { batchGroups, singleGroups, uniqueGeometries } = this._analyzeModel();
		const meshesToRemove = this._createBatchedMeshes( batchGroups );

		this.disposeMeshes( meshesToRemove );
		this.removeEmptyNodes( this.scene );

		if ( this.debug ) {

			const totalOriginalMeshes = meshesToRemove.size + singleGroups.size;
			const totalFinalMeshes = batchGroups.size + singleGroups.size;

			const stats = {
				originalMeshes: totalOriginalMeshes,
				batchedMeshes: batchGroups.size,
				singleMeshes: singleGroups.size,
				drawCalls: totalFinalMeshes,
				uniqueGeometries: uniqueGeometries,
				reductionRatio: ( ( 1 - totalFinalMeshes / totalOriginalMeshes ) * 100 ).toFixed( 1 ),
			};

			this._logDebugInfo( stats );

		}

		return this.scene;

	}
```
</details>

### `SceneOptimizer.toInstancingMesh(): Scene`

**JSDoc:**
```typescript
/**
	 * Performs the auto-instancing by identifying groups of meshes in the scene
	 * that can be represented as a single {@link InstancedMesh}. The method modifies
	 * the scene by adding instances of `InstancedMesh` and removing the now redundant
	 * individual meshes.
	 *
	 * This method is not yet implemented.
	 *
	 * @abstract
	 * @return {Scene} The optimized scene.
	 */
```

**Returns:** `Scene`

<details><summary>Code</summary>

```typescript
toInstancingMesh() {

		throw new Error( 'InstancedMesh optimization not implemented yet' );

	}
```
</details>


---

## Classes

### `SceneOptimizer`

<details><summary>Class Code</summary>

```ts
class SceneOptimizer {

	/**
	 * Constructs a new scene optimizer.
	 *
	 * @param {Scene} scene - The scene to optimize.
	 * @param {SceneOptimizer~Options} options - The configuration options.
	 */
	constructor( scene, options = {} ) {

		this.scene = scene;
		this.debug = options.debug || false;

	}

	_bufferToHash( buffer ) {

		let hash = 0;
		if ( buffer.byteLength !== 0 ) {

			let uintArray;
			if ( buffer.buffer ) {

				uintArray = new Uint8Array(
					buffer.buffer,
					buffer.byteOffset,
					buffer.byteLength
				);

			} else {

				uintArray = new Uint8Array( buffer );

			}

			for ( let i = 0; i < buffer.byteLength; i ++ ) {

				const byte = uintArray[ i ];
				hash = ( hash << 5 ) - hash + byte;
				hash |= 0;

			}

		}

		return hash;

	}

	_getMaterialPropertiesHash( material ) {

		const mapProps = [
			'map',
			'alphaMap',
			'aoMap',
			'bumpMap',
			'displacementMap',
			'emissiveMap',
			'envMap',
			'lightMap',
			'metalnessMap',
			'normalMap',
			'roughnessMap',
		];

		const mapHash = mapProps
			.map( ( prop ) => {

				const map = material[ prop ];
				if ( ! map ) return 0;
				return `${map.uuid}_${map.offset.x}_${map.offset.y}_${map.repeat.x}_${map.repeat.y}_${map.rotation}`;

			} )
			.join( '|' );

		const physicalProps = [
			'transparent',
			'opacity',
			'alphaTest',
			'alphaToCoverage',
			'side',
			'vertexColors',
			'visible',
			'blending',
			'wireframe',
			'flatShading',
			'premultipliedAlpha',
			'dithering',
			'toneMapped',
			'depthTest',
			'depthWrite',
			'metalness',
			'roughness',
			'clearcoat',
			'clearcoatRoughness',
			'sheen',
			'sheenRoughness',
			'transmission',
			'thickness',
			'attenuationDistance',
			'ior',
			'iridescence',
			'iridescenceIOR',
			'iridescenceThicknessRange',
			'reflectivity',
		]
			.map( ( prop ) => {

				if ( typeof material[ prop ] === 'undefined' ) return 0;
				if ( material[ prop ] === null ) return 0;
				return material[ prop ].toString();

			} )
			.join( '|' );

		const emissiveHash = material.emissive ? material.emissive.getHexString() : 0;
		const attenuationHash = material.attenuationColor
			? material.attenuationColor.getHexString()
			: 0;
		const sheenColorHash = material.sheenColor
			? material.sheenColor.getHexString()
			: 0;

		return [
			material.type,
			physicalProps,
			mapHash,
			emissiveHash,
			attenuationHash,
			sheenColorHash,
		].join( '_' );

	}

	_getAttributesSignature( geometry ) {

		return Object.keys( geometry.attributes )
			.sort()
			.map( ( name ) => {

				const attribute = geometry.attributes[ name ];
				return `${name}_${attribute.itemSize}_${attribute.normalized}`;

			} )
			.join( '|' );

	}

	_getGeometryHash( geometry ) {

		const indexHash = geometry.index
			? this._bufferToHash( geometry.index.array )
			: 'noIndex';
		const positionHash = this._bufferToHash( geometry.attributes.position.array );
		const attributesSignature = this._getAttributesSignature( geometry );
		return `${indexHash}_${positionHash}_${attributesSignature}`;

	}

	_getBatchKey( materialProps, attributesSignature ) {

		return `${materialProps}_${attributesSignature}`;

	}

	_analyzeModel() {

		const batchGroups = new Map();
		const singleGroups = new Map();
		const uniqueGeometries = new Set();

		this.scene.updateMatrixWorld( true );
		this.scene.traverse( ( node ) => {

			if ( ! node.isMesh ) return;

			const materialProps = this._getMaterialPropertiesHash( node.material );
			const attributesSignature = this._getAttributesSignature( node.geometry );
			const batchKey = this._getBatchKey( materialProps, attributesSignature );
			const geometryHash = this._getGeometryHash( node.geometry );
			uniqueGeometries.add( geometryHash );

			if ( ! batchGroups.has( batchKey ) ) {

				batchGroups.set( batchKey, {
					meshes: [],
					geometryStats: new Map(),
					totalInstances: 0,
					materialProps: node.material.clone(),
				} );

			}

			const group = batchGroups.get( batchKey );
			group.meshes.push( node );
			group.totalInstances ++;

			if ( ! group.geometryStats.has( geometryHash ) ) {

				group.geometryStats.set( geometryHash, {
					count: 0,
					vertices: node.geometry.attributes.position.count,
					indices: node.geometry.index ? node.geometry.index.count : 0,
					geometry: node.geometry,
				} );

			}

			group.geometryStats.get( geometryHash ).count ++;

		} );

		// Move single instance groups to singleGroups
		for ( const [ batchKey, group ] of batchGroups ) {

			if ( group.totalInstances === 1 ) {

				singleGroups.set( batchKey, group );
				batchGroups.delete( batchKey );

			}

		}

		return { batchGroups, singleGroups, uniqueGeometries: uniqueGeometries.size };

	}

	_createBatchedMeshes( batchGroups ) {

		const meshesToRemove = new Set();

		for ( const [ , group ] of batchGroups ) {

			const maxGeometries = group.totalInstances;
			const maxVertices = Array.from( group.geometryStats.values() ).reduce(
				( sum, stats ) => sum + stats.vertices,
				0
			);
			const maxIndices = Array.from( group.geometryStats.values() ).reduce(
				( sum, stats ) => sum + stats.indices,
				0
			);

			const batchedMaterial = new group.materialProps.constructor( group.materialProps );

			if ( batchedMaterial.color !== undefined ) {

				// Reset color to white, color will be set per instance
				batchedMaterial.color.set( 1, 1, 1 );

			}

			const batchedMesh = new THREE.BatchedMesh(
				maxGeometries,
				maxVertices,
				maxIndices,
				batchedMaterial
			);

			const referenceMesh = group.meshes[ 0 ];
			batchedMesh.name = `${referenceMesh.name}_batch`;

			const geometryIds = new Map();
			const inverseParentMatrix = new THREE.Matrix4();

			if ( referenceMesh.parent ) {

				referenceMesh.parent.updateWorldMatrix( true, false );
				inverseParentMatrix.copy( referenceMesh.parent.matrixWorld ).invert();

			}

			for ( const mesh of group.meshes ) {

				const geometryHash = this._getGeometryHash( mesh.geometry );

				if ( ! geometryIds.has( geometryHash ) ) {

					geometryIds.set( geometryHash, batchedMesh.addGeometry( mesh.geometry ) );

				}

				const geometryId = geometryIds.get( geometryHash );
				const instanceId = batchedMesh.addInstance( geometryId );

				const localMatrix = new THREE.Matrix4();
				mesh.updateWorldMatrix( true, false );
				localMatrix.copy( mesh.matrixWorld );
				if ( referenceMesh.parent ) {

					localMatrix.premultiply( inverseParentMatrix );

				}

				batchedMesh.setMatrixAt( instanceId, localMatrix );
				batchedMesh.setColorAt( instanceId, mesh.material.color );

				meshesToRemove.add( mesh );

			}

			if ( referenceMesh.parent ) {

				referenceMesh.parent.add( batchedMesh );

			}

		}

		return meshesToRemove;

	}

	/**
	 * Removes empty nodes from all descendants of the given 3D object.
	 *
	 * @param {Object3D} object - The 3D object to process.
	 */
	removeEmptyNodes( object ) {

		const children = [ ...object.children ];

		for ( const child of children ) {

			this.removeEmptyNodes( child );

			if ( ( child instanceof THREE.Group || child.constructor === THREE.Object3D )
                && child.children.length === 0 ) {

				object.remove( child );

			}

		}

	}

	/**
	 * Removes the given array of meshes from the scene.
	 *
	 * @param {Set<Mesh>} meshesToRemove - The meshes to remove.
	 */
	disposeMeshes( meshesToRemove ) {

		meshesToRemove.forEach( ( mesh ) => {

			if ( mesh.parent ) {

				mesh.parent.remove( mesh );

			}

			if ( mesh.geometry ) mesh.geometry.dispose();
			if ( mesh.material ) {

				if ( Array.isArray( mesh.material ) ) {

					mesh.material.forEach( ( m ) => m.dispose() );

				} else {

					mesh.material.dispose();

				}

			}

		} );

	}

	_logDebugInfo( stats ) {

		console.group( 'Scene Optimization Results' );
		console.log( `Original meshes: ${stats.originalMeshes}` );
		console.log( `Batched into: ${stats.batchedMeshes} BatchedMesh` );
		console.log( `Single meshes: ${stats.singleMeshes} Mesh` );
		console.log( `Total draw calls: ${stats.drawCalls}` );
		console.log( `Reduction Ratio: ${stats.reductionRatio}% fewer draw calls` );
		console.groupEnd();

	}

	/**
	 * Performs the auto-baching by identifying groups of meshes in the scene
	 * that can be represented as a single {@link BatchedMesh}. The method modifies
	 * the scene by adding instances of `BatchedMesh` and removing the now redundant
	 * individual meshes.
	 *
	 * @return {Scene} The optimized scene.
	 */
	toBatchedMesh() {

		const { batchGroups, singleGroups, uniqueGeometries } = this._analyzeModel();
		const meshesToRemove = this._createBatchedMeshes( batchGroups );

		this.disposeMeshes( meshesToRemove );
		this.removeEmptyNodes( this.scene );

		if ( this.debug ) {

			const totalOriginalMeshes = meshesToRemove.size + singleGroups.size;
			const totalFinalMeshes = batchGroups.size + singleGroups.size;

			const stats = {
				originalMeshes: totalOriginalMeshes,
				batchedMeshes: batchGroups.size,
				singleMeshes: singleGroups.size,
				drawCalls: totalFinalMeshes,
				uniqueGeometries: uniqueGeometries,
				reductionRatio: ( ( 1 - totalFinalMeshes / totalOriginalMeshes ) * 100 ).toFixed( 1 ),
			};

			this._logDebugInfo( stats );

		}

		return this.scene;

	}

	/**
	 * Performs the auto-instancing by identifying groups of meshes in the scene
	 * that can be represented as a single {@link InstancedMesh}. The method modifies
	 * the scene by adding instances of `InstancedMesh` and removing the now redundant
	 * individual meshes.
	 *
	 * This method is not yet implemented.
	 *
	 * @abstract
	 * @return {Scene} The optimized scene.
	 */
	toInstancingMesh() {

		throw new Error( 'InstancedMesh optimization not implemented yet' );

	}

}
```
</details>

#### Methods

##### `_bufferToHash(buffer: any): number`

<details><summary>Code</summary>

```ts
_bufferToHash( buffer ) {

		let hash = 0;
		if ( buffer.byteLength !== 0 ) {

			let uintArray;
			if ( buffer.buffer ) {

				uintArray = new Uint8Array(
					buffer.buffer,
					buffer.byteOffset,
					buffer.byteLength
				);

			} else {

				uintArray = new Uint8Array( buffer );

			}

			for ( let i = 0; i < buffer.byteLength; i ++ ) {

				const byte = uintArray[ i ];
				hash = ( hash << 5 ) - hash + byte;
				hash |= 0;

			}

		}

		return hash;

	}
```
</details>

##### `_getMaterialPropertiesHash(material: any): string`

<details><summary>Code</summary>

```ts
_getMaterialPropertiesHash( material ) {

		const mapProps = [
			'map',
			'alphaMap',
			'aoMap',
			'bumpMap',
			'displacementMap',
			'emissiveMap',
			'envMap',
			'lightMap',
			'metalnessMap',
			'normalMap',
			'roughnessMap',
		];

		const mapHash = mapProps
			.map( ( prop ) => {

				const map = material[ prop ];
				if ( ! map ) return 0;
				return `${map.uuid}_${map.offset.x}_${map.offset.y}_${map.repeat.x}_${map.repeat.y}_${map.rotation}`;

			} )
			.join( '|' );

		const physicalProps = [
			'transparent',
			'opacity',
			'alphaTest',
			'alphaToCoverage',
			'side',
			'vertexColors',
			'visible',
			'blending',
			'wireframe',
			'flatShading',
			'premultipliedAlpha',
			'dithering',
			'toneMapped',
			'depthTest',
			'depthWrite',
			'metalness',
			'roughness',
			'clearcoat',
			'clearcoatRoughness',
			'sheen',
			'sheenRoughness',
			'transmission',
			'thickness',
			'attenuationDistance',
			'ior',
			'iridescence',
			'iridescenceIOR',
			'iridescenceThicknessRange',
			'reflectivity',
		]
			.map( ( prop ) => {

				if ( typeof material[ prop ] === 'undefined' ) return 0;
				if ( material[ prop ] === null ) return 0;
				return material[ prop ].toString();

			} )
			.join( '|' );

		const emissiveHash = material.emissive ? material.emissive.getHexString() : 0;
		const attenuationHash = material.attenuationColor
			? material.attenuationColor.getHexString()
			: 0;
		const sheenColorHash = material.sheenColor
			? material.sheenColor.getHexString()
			: 0;

		return [
			material.type,
			physicalProps,
			mapHash,
			emissiveHash,
			attenuationHash,
			sheenColorHash,
		].join( '_' );

	}
```
</details>

##### `_getAttributesSignature(geometry: any): string`

<details><summary>Code</summary>

```ts
_getAttributesSignature( geometry ) {

		return Object.keys( geometry.attributes )
			.sort()
			.map( ( name ) => {

				const attribute = geometry.attributes[ name ];
				return `${name}_${attribute.itemSize}_${attribute.normalized}`;

			} )
			.join( '|' );

	}
```
</details>

##### `_getGeometryHash(geometry: any): string`

<details><summary>Code</summary>

```ts
_getGeometryHash( geometry ) {

		const indexHash = geometry.index
			? this._bufferToHash( geometry.index.array )
			: 'noIndex';
		const positionHash = this._bufferToHash( geometry.attributes.position.array );
		const attributesSignature = this._getAttributesSignature( geometry );
		return `${indexHash}_${positionHash}_${attributesSignature}`;

	}
```
</details>

##### `_getBatchKey(materialProps: any, attributesSignature: any): string`

<details><summary>Code</summary>

```ts
_getBatchKey( materialProps, attributesSignature ) {

		return `${materialProps}_${attributesSignature}`;

	}
```
</details>

##### `_analyzeModel(): { batchGroups: Map<any, any>; singleGroups: Map<any, any>; uniqueGeometries: number; }`

<details><summary>Code</summary>

```ts
_analyzeModel() {

		const batchGroups = new Map();
		const singleGroups = new Map();
		const uniqueGeometries = new Set();

		this.scene.updateMatrixWorld( true );
		this.scene.traverse( ( node ) => {

			if ( ! node.isMesh ) return;

			const materialProps = this._getMaterialPropertiesHash( node.material );
			const attributesSignature = this._getAttributesSignature( node.geometry );
			const batchKey = this._getBatchKey( materialProps, attributesSignature );
			const geometryHash = this._getGeometryHash( node.geometry );
			uniqueGeometries.add( geometryHash );

			if ( ! batchGroups.has( batchKey ) ) {

				batchGroups.set( batchKey, {
					meshes: [],
					geometryStats: new Map(),
					totalInstances: 0,
					materialProps: node.material.clone(),
				} );

			}

			const group = batchGroups.get( batchKey );
			group.meshes.push( node );
			group.totalInstances ++;

			if ( ! group.geometryStats.has( geometryHash ) ) {

				group.geometryStats.set( geometryHash, {
					count: 0,
					vertices: node.geometry.attributes.position.count,
					indices: node.geometry.index ? node.geometry.index.count : 0,
					geometry: node.geometry,
				} );

			}

			group.geometryStats.get( geometryHash ).count ++;

		} );

		// Move single instance groups to singleGroups
		for ( const [ batchKey, group ] of batchGroups ) {

			if ( group.totalInstances === 1 ) {

				singleGroups.set( batchKey, group );
				batchGroups.delete( batchKey );

			}

		}

		return { batchGroups, singleGroups, uniqueGeometries: uniqueGeometries.size };

	}
```
</details>

##### `_createBatchedMeshes(batchGroups: any): Set<any>`

<details><summary>Code</summary>

```ts
_createBatchedMeshes( batchGroups ) {

		const meshesToRemove = new Set();

		for ( const [ , group ] of batchGroups ) {

			const maxGeometries = group.totalInstances;
			const maxVertices = Array.from( group.geometryStats.values() ).reduce(
				( sum, stats ) => sum + stats.vertices,
				0
			);
			const maxIndices = Array.from( group.geometryStats.values() ).reduce(
				( sum, stats ) => sum + stats.indices,
				0
			);

			const batchedMaterial = new group.materialProps.constructor( group.materialProps );

			if ( batchedMaterial.color !== undefined ) {

				// Reset color to white, color will be set per instance
				batchedMaterial.color.set( 1, 1, 1 );

			}

			const batchedMesh = new THREE.BatchedMesh(
				maxGeometries,
				maxVertices,
				maxIndices,
				batchedMaterial
			);

			const referenceMesh = group.meshes[ 0 ];
			batchedMesh.name = `${referenceMesh.name}_batch`;

			const geometryIds = new Map();
			const inverseParentMatrix = new THREE.Matrix4();

			if ( referenceMesh.parent ) {

				referenceMesh.parent.updateWorldMatrix( true, false );
				inverseParentMatrix.copy( referenceMesh.parent.matrixWorld ).invert();

			}

			for ( const mesh of group.meshes ) {

				const geometryHash = this._getGeometryHash( mesh.geometry );

				if ( ! geometryIds.has( geometryHash ) ) {

					geometryIds.set( geometryHash, batchedMesh.addGeometry( mesh.geometry ) );

				}

				const geometryId = geometryIds.get( geometryHash );
				const instanceId = batchedMesh.addInstance( geometryId );

				const localMatrix = new THREE.Matrix4();
				mesh.updateWorldMatrix( true, false );
				localMatrix.copy( mesh.matrixWorld );
				if ( referenceMesh.parent ) {

					localMatrix.premultiply( inverseParentMatrix );

				}

				batchedMesh.setMatrixAt( instanceId, localMatrix );
				batchedMesh.setColorAt( instanceId, mesh.material.color );

				meshesToRemove.add( mesh );

			}

			if ( referenceMesh.parent ) {

				referenceMesh.parent.add( batchedMesh );

			}

		}

		return meshesToRemove;

	}
```
</details>

##### `removeEmptyNodes(object: Object3D): void`

<details><summary>Code</summary>

```ts
removeEmptyNodes( object ) {

		const children = [ ...object.children ];

		for ( const child of children ) {

			this.removeEmptyNodes( child );

			if ( ( child instanceof THREE.Group || child.constructor === THREE.Object3D )
                && child.children.length === 0 ) {

				object.remove( child );

			}

		}

	}
```
</details>

##### `disposeMeshes(meshesToRemove: Set<Mesh>): void`

<details><summary>Code</summary>

```ts
disposeMeshes( meshesToRemove ) {

		meshesToRemove.forEach( ( mesh ) => {

			if ( mesh.parent ) {

				mesh.parent.remove( mesh );

			}

			if ( mesh.geometry ) mesh.geometry.dispose();
			if ( mesh.material ) {

				if ( Array.isArray( mesh.material ) ) {

					mesh.material.forEach( ( m ) => m.dispose() );

				} else {

					mesh.material.dispose();

				}

			}

		} );

	}
```
</details>

##### `_logDebugInfo(stats: any): void`

<details><summary>Code</summary>

```ts
_logDebugInfo( stats ) {

		console.group( 'Scene Optimization Results' );
		console.log( `Original meshes: ${stats.originalMeshes}` );
		console.log( `Batched into: ${stats.batchedMeshes} BatchedMesh` );
		console.log( `Single meshes: ${stats.singleMeshes} Mesh` );
		console.log( `Total draw calls: ${stats.drawCalls}` );
		console.log( `Reduction Ratio: ${stats.reductionRatio}% fewer draw calls` );
		console.groupEnd();

	}
```
</details>

##### `toBatchedMesh(): Scene`

<details><summary>Code</summary>

```ts
toBatchedMesh() {

		const { batchGroups, singleGroups, uniqueGeometries } = this._analyzeModel();
		const meshesToRemove = this._createBatchedMeshes( batchGroups );

		this.disposeMeshes( meshesToRemove );
		this.removeEmptyNodes( this.scene );

		if ( this.debug ) {

			const totalOriginalMeshes = meshesToRemove.size + singleGroups.size;
			const totalFinalMeshes = batchGroups.size + singleGroups.size;

			const stats = {
				originalMeshes: totalOriginalMeshes,
				batchedMeshes: batchGroups.size,
				singleMeshes: singleGroups.size,
				drawCalls: totalFinalMeshes,
				uniqueGeometries: uniqueGeometries,
				reductionRatio: ( ( 1 - totalFinalMeshes / totalOriginalMeshes ) * 100 ).toFixed( 1 ),
			};

			this._logDebugInfo( stats );

		}

		return this.scene;

	}
```
</details>

##### `toInstancingMesh(): Scene`

<details><summary>Code</summary>

```ts
toInstancingMesh() {

		throw new Error( 'InstancedMesh optimization not implemented yet' );

	}
```
</details>


---