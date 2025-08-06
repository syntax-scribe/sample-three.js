[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `BufferGeometry.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 58 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/core/BufferGeometry.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../../../../src/core/BufferGeometry.js` |
| `BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Float16BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Uint16BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Uint32BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `Quaternion` | `../../../../src/math/Quaternion.js` |
| `Sphere` | `../../../../src/math/Sphere.js` |
| `x` | `../../utils/math-constants.js` |
| `y` | `../../utils/math-constants.js` |
| `z` | `../../utils/math-constants.js` |
| `EventDispatcher` | `../../../../src/core/EventDispatcher.js` |
| `toHalfFloat` | `../../../../src/extras/DataUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `DegToRad` | `number` | let/var | `Math.PI / 180` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `object` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `object` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `object` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `object` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `a` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `uint16` | `number[]` | let/var | `[ 1, 2, 3 ]` | ✗ |
| `uint32` | `number[]` | let/var | `[ 65535, 65536, 65537 ]` | ✗ |
| `str` | `"foo"` | let/var | `'foo'` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `attributeName` | `"position"` | let/var | `'position'` | ✗ |
| `a` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `expected` | `{ start: number; count: number; mater...` | let/var | `[ { start: 0, count: 1, materialIndex: 0 }, { start: 1, count: 2, materialInd...` | ✗ |
| `a` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `position` | `any` | let/var | `geometry.attributes.position.array` | ✗ |
| `m` | `number[]` | let/var | `matrix.elements` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `q` | `Quaternion` | let/var | `new Quaternion( 0.5, 0.5, 0.5, 0.5 )` | ✗ |
| `pos` | `any` | let/var | `geometry.attributes.position.array` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `pos` | `any` | let/var | `geometry.attributes.position.array` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `pos` | `any` | let/var | `geometry.attributes.position.array` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `pos` | `any` | let/var | `geometry.attributes.position.array` | ✗ |
| `a` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `vertices` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ - 1.0, - 1.0, 1.0, 1.0, - 1.0, 1.0, 1.0, 1.0, 1.0, 1.0, 1...` | ✗ |
| `expected` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1, 0, - sqrt, - 1, 0, - sqrt, - 1, s...` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `pos` | `any` | let/var | `geometry.attributes.position.array` | ✗ |
| `f16Array` | `Uint16Array<any>` | let/var | `new Uint16Array( f32Array.length )` | ✗ |
| `vertices` | `number[]` | let/var | `[ - 1, - 2, - 3, 13, - 2, - 3.5, - 1, - 20, 0, - 4, 5, 6 ]` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `bb` | `Box3` | let/var | `geometry.boundingBox` | ✗ |
| `vertices` | `number[]` | let/var | `[ - 10, 0, 0, 10, 0, 0 ]` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `bs` | `Sphere` | let/var | `geometry.boundingSphere` | ✗ |
| `sqrt` | `number` | let/var | `0.5 * Math.sqrt( 2 )` | ✗ |
| `normal` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ - 1, 0, 0, - 1, 0, 0, - 1, 0, 0, sqr...` | ✗ |
| `position` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 0.5, 0.5, 0.5, 0.5, 0.5, - 0.5, 0.5,...` | ✗ |
| `index` | `BufferAttribute` | let/var | `new BufferAttribute( new Uint16Array( [ 0, 2, 1, 3, 5, 4 ] ), 1 )` | ✗ |
| `a` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `vertices` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 0.5, 0.5, 0.5, 0.5, 0.5, - 0.5, 0.5, - 0.5, 0.5, 0.5, - 0...` | ✗ |
| `index` | `BufferAttribute` | let/var | `new BufferAttribute( new Uint16Array( [ 0, 2, 1, 2, 3, 1 ] ) )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 0.5, 0.5, 0.5, 0.5, - 0.5, 0.5, 0.5, 0.5, - 0.5, 0.5, - 0...` | ✗ |
| `index` | `BufferAttribute` | let/var | `new BufferAttribute( new Uint16Array( [ 0, 1, 2, 3 ] ), 1 )` | ✗ |
| `attribute1` | `BufferAttribute` | let/var | `new BufferAttribute( new Uint16Array( [ 1, 3, 5, 7 ] ), 1 )` | ✗ |
| `a` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `gold` | `{ metadata: { version: number; type: ...` | let/var | `{ 'metadata': { 'version': 4.7, 'type': 'BufferGeometry', 'generator': 'Buffe...` | ✗ |
| `a` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `attribute` | `any` | let/var | `geometry.attributes[ key ]` | ✗ |
| `object` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |


---

## Functions

### `bufferAttributeEquals(a: any, b: any, tolerance: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`tolerance`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function bufferAttributeEquals( a, b, tolerance ) {

	tolerance = tolerance || 0.0001;

	if ( a.count !== b.count || a.itemSize !== b.itemSize ) {

		return false;

	}

	for ( let i = 0, il = a.count * a.itemSize; i < il; i ++ ) {

		const delta = Math.abs( a.array[ i ] - b.array[ i ] );
		if ( delta > tolerance ) {

			return false;

		}

	}

	return true;

}
```
</details>

### `getBBForVertices(vertices: any): Box3`

**Parameters:**

- **`vertices`** `any`

**Returns:** `Box3`

**Calls:**

- `geometry.setAttribute`
- `geometry.computeBoundingBox`

<details><summary>Code</summary>

```typescript
function getBBForVertices( vertices ) {

	const geometry = new BufferGeometry();

	geometry.setAttribute( 'position', new BufferAttribute( new Float32Array( vertices ), 3 ) );
	geometry.computeBoundingBox();

	return geometry.boundingBox;

}
```
</details>

### `getBSForVertices(vertices: any): Sphere`

**Parameters:**

- **`vertices`** `any`

**Returns:** `Sphere`

**Calls:**

- `geometry.setAttribute`
- `geometry.computeBoundingSphere`

<details><summary>Code</summary>

```typescript
function getBSForVertices( vertices ) {

	const geometry = new BufferGeometry();

	geometry.setAttribute( 'position', new BufferAttribute( new Float32Array( vertices ), 3 ) );
	geometry.computeBoundingSphere();

	return geometry.boundingSphere;

}
```
</details>

### `getNormalsForVertices(vertices: any, assert: any): any`

**Parameters:**

- **`vertices`** `any`
- **`assert`** `any`

**Returns:** `any`

**Calls:**

- `geometry.setAttribute`
- `geometry.computeVertexNormals`
- `assert.ok`

<details><summary>Code</summary>

```typescript
function getNormalsForVertices( vertices, assert ) {

	const geometry = new BufferGeometry();

	geometry.setAttribute( 'position', new BufferAttribute( new Float32Array( vertices ), 3 ) );

	geometry.computeVertexNormals();

	assert.ok( geometry.attributes.normal !== undefined, 'normal attribute was created' );

	return geometry.attributes.normal.array;

}
```
</details>

### `toHalfFloatArray(f32Array: any): Uint16Array<any>`

**Parameters:**

- **`f32Array`** `any`

**Returns:** `Uint16Array<any>`

**Calls:**

- `toHalfFloat (from ../../../../src/extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
( f32Array ) => {

			const f16Array = new Uint16Array( f32Array.length );
			for ( let i = 0, n = f32Array.length; i < n; ++ i ) {

				f16Array[ i ] = toHalfFloat( f32Array[ i ] );

			}

			return f16Array;

		}
```
</details>


---