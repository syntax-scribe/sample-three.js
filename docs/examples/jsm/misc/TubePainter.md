[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TubePainter.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 29 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/misc/TubePainter.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `DynamicDrawUsage` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshStandardMaterial` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `BUFFER_SIZE` | `number` | let/var | `1000000 * 3` | ✗ |
| `positions` | `any` | let/var | `new BufferAttribute( new Float32Array( BUFFER_SIZE ), 3 )` | ✗ |
| `normals` | `any` | let/var | `new BufferAttribute( new Float32Array( BUFFER_SIZE ), 3 )` | ✗ |
| `colors` | `any` | let/var | `new BufferAttribute( new Float32Array( BUFFER_SIZE ), 3 )` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `any` | let/var | `new MeshStandardMaterial( { vertexColors: true } )` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( geometry, material )` | ✗ |
| `PI2` | `number` | let/var | `Math.PI * 2` | ✗ |
| `sides` | `10` | let/var | `10` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `radius` | `number` | let/var | `0.01 * size` | ✗ |
| `angle` | `number` | let/var | `( i / sides ) * PI2` | ✗ |
| `vector1` | `any` | let/var | `new Vector3()` | ✗ |
| `vector2` | `any` | let/var | `new Vector3()` | ✗ |
| `vector3` | `any` | let/var | `new Vector3()` | ✗ |
| `vector4` | `any` | let/var | `new Vector3()` | ✗ |
| `color` | `any` | let/var | `new Color( 0xffffff )` | ✗ |
| `size` | `number` | let/var | `1` | ✗ |
| `count` | `any` | let/var | `geometry.drawRange.count` | ✗ |
| `vertex1` | `any` | let/var | `points[ i ]` | ✗ |
| `vertex2` | `any` | let/var | `points[ ( i + 1 ) % il ]` | ✗ |
| `up` | `any` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `point1` | `any` | let/var | `new Vector3()` | ✗ |
| `point2` | `any` | let/var | `new Vector3()` | ✗ |
| `matrix1` | `any` | let/var | `new Matrix4()` | ✗ |
| `matrix2` | `any` | let/var | `new Matrix4()` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `start` | `number` | let/var | `count` | ✗ |
| `end` | `any` | let/var | `geometry.drawRange.count` | ✗ |


---

## Functions

### `TubePainter(): { mesh: Mesh; moveTo: (position: any) => void; lineTo: (position: any) => void; setSize: (value: any) => void; update: () => void; }`

**JSDoc:**
```typescript
/**
 * @classdesc This module can be used to paint tube-like meshes
 * along a sequence of points. This module is used in a XR
 * painter demo.
 *
 * ```js
 * const painter = new TubePainter();
 * scene.add( painter.mesh );
 * ```
 *
 * @name TubePainter
 * @class
 * @three_import import { TubePainter } from 'three/addons/misc/TubePainter.js';
 */
```

**Returns:** `{ mesh: Mesh; moveTo: (position: any) => void; lineTo: (position: any) => void; setSize: (value: any) => void; update: () => void; }`

**Calls:**

- `geometry.setAttribute`
- `array.push`
- `Math.sin`
- `Math.cos`
- `position1.distanceToSquared`
- `getPoints`
- `vector1.copy( vertex1 ).applyMatrix4( matrix2 ).add`
- `vector2.copy( vertex2 ).applyMatrix4( matrix2 ).add`
- `vector3.copy( vertex2 ).applyMatrix4( matrix1 ).add`
- `vector4.copy( vertex1 ).applyMatrix4( matrix1 ).add`
- `vector1.toArray`
- `vector2.toArray`
- `vector4.toArray`
- `vector3.toArray`
- `vector1.copy( vertex1 ).applyMatrix4( matrix2 ).normalize`
- `vector2.copy( vertex2 ).applyMatrix4( matrix2 ).normalize`
- `vector3.copy( vertex2 ).applyMatrix4( matrix1 ).normalize`
- `vector4.copy( vertex1 ).applyMatrix4( matrix1 ).normalize`
- `color.toArray`
- `point1.copy`
- `matrix1.lookAt`
- `point2.copy`
- `matrix2.copy`
- `stroke`
- `positions.addUpdateRange`
- `normals.addUpdateRange`
- `colors.addUpdateRange`

**Internal Comments:**
```
// (x7)
// positions (x8)
// normals (x8)
// colors (x4)
/**
		 * The "painted" tube mesh. Must be added to the scene.
		 *
		 * @name TubePainter#mesh
		 * @type {Mesh}
		 */ (x2)
/**
		 * Moves the current painting position to the given value.
		 *
		 * @method
		 * @name TubePainter#moveTo
		 * @param {Vector3} position The new painting position.
		 */ (x2)
/**
		 * Draw a stroke from the current position to the given one.
		 * This method extends the tube while drawing with the XR
		 * controllers.
		 *
		 * @method
		 * @name TubePainter#lineTo
		 * @param {Vector3} position The destination position.
		 */ (x2)
/**
		 * Sets the size of newly rendered tube segments.
		 *
		 * @method
		 * @name TubePainter#setSize
		 * @param {number} size The size.
		 */ (x2)
/**
		 * Updates the internal geometry buffers so the new painted
		 * segments are rendered.
		 *
		 * @method
		 * @name TubePainter#update
		 */ (x2)
```

<details><summary>Code</summary>

```typescript
function TubePainter() {

	const BUFFER_SIZE = 1000000 * 3;

	const positions = new BufferAttribute( new Float32Array( BUFFER_SIZE ), 3 );
	positions.usage = DynamicDrawUsage;

	const normals = new BufferAttribute( new Float32Array( BUFFER_SIZE ), 3 );
	normals.usage = DynamicDrawUsage;

	const colors = new BufferAttribute( new Float32Array( BUFFER_SIZE ), 3 );
	colors.usage = DynamicDrawUsage;

	const geometry = new BufferGeometry();
	geometry.setAttribute( 'position', positions );
	geometry.setAttribute( 'normal', normals );
	geometry.setAttribute( 'color', colors );
	geometry.drawRange.count = 0;

	const material = new MeshStandardMaterial( {
		vertexColors: true
	} );

	const mesh = new Mesh( geometry, material );
	mesh.frustumCulled = false;

	//

	function getPoints( size ) {

		const PI2 = Math.PI * 2;

		const sides = 10;
		const array = [];
		const radius = 0.01 * size;

		for ( let i = 0; i < sides; i ++ ) {

			const angle = ( i / sides ) * PI2;
			array.push( new Vector3( Math.sin( angle ) * radius, Math.cos( angle ) * radius, 0 ) );

		}

		return array;

	}

	//

	const vector1 = new Vector3();
	const vector2 = new Vector3();
	const vector3 = new Vector3();
	const vector4 = new Vector3();

	const color = new Color( 0xffffff );
	let size = 1;

	function stroke( position1, position2, matrix1, matrix2 ) {

		if ( position1.distanceToSquared( position2 ) === 0 ) return;

		let count = geometry.drawRange.count;

		const points = getPoints( size );

		for ( let i = 0, il = points.length; i < il; i ++ ) {

			const vertex1 = points[ i ];
			const vertex2 = points[ ( i + 1 ) % il ];

			// positions

			vector1.copy( vertex1 ).applyMatrix4( matrix2 ).add( position2 );
			vector2.copy( vertex2 ).applyMatrix4( matrix2 ).add( position2 );
			vector3.copy( vertex2 ).applyMatrix4( matrix1 ).add( position1 );
			vector4.copy( vertex1 ).applyMatrix4( matrix1 ).add( position1 );

			vector1.toArray( positions.array, ( count + 0 ) * 3 );
			vector2.toArray( positions.array, ( count + 1 ) * 3 );
			vector4.toArray( positions.array, ( count + 2 ) * 3 );

			vector2.toArray( positions.array, ( count + 3 ) * 3 );
			vector3.toArray( positions.array, ( count + 4 ) * 3 );
			vector4.toArray( positions.array, ( count + 5 ) * 3 );

			// normals

			vector1.copy( vertex1 ).applyMatrix4( matrix2 ).normalize();
			vector2.copy( vertex2 ).applyMatrix4( matrix2 ).normalize();
			vector3.copy( vertex2 ).applyMatrix4( matrix1 ).normalize();
			vector4.copy( vertex1 ).applyMatrix4( matrix1 ).normalize();

			vector1.toArray( normals.array, ( count + 0 ) * 3 );
			vector2.toArray( normals.array, ( count + 1 ) * 3 );
			vector4.toArray( normals.array, ( count + 2 ) * 3 );

			vector2.toArray( normals.array, ( count + 3 ) * 3 );
			vector3.toArray( normals.array, ( count + 4 ) * 3 );
			vector4.toArray( normals.array, ( count + 5 ) * 3 );

			// colors

			color.toArray( colors.array, ( count + 0 ) * 3 );
			color.toArray( colors.array, ( count + 1 ) * 3 );
			color.toArray( colors.array, ( count + 2 ) * 3 );

			color.toArray( colors.array, ( count + 3 ) * 3 );
			color.toArray( colors.array, ( count + 4 ) * 3 );
			color.toArray( colors.array, ( count + 5 ) * 3 );

			count += 6;

		}

		geometry.drawRange.count = count;

	}

	//

	const up = new Vector3( 0, 1, 0 );

	const point1 = new Vector3();
	const point2 = new Vector3();

	const matrix1 = new Matrix4();
	const matrix2 = new Matrix4();

	function moveTo( position ) {

		point1.copy( position );
		matrix1.lookAt( point2, point1, up );

		point2.copy( position );
		matrix2.copy( matrix1 );

	}

	function lineTo( position ) {

		point1.copy( position );
		matrix1.lookAt( point2, point1, up );

		stroke( point1, point2, matrix1, matrix2 );

		point2.copy( point1 );
		matrix2.copy( matrix1 );

	}

	function setSize( value ) {

		size = value;

	}

	//

	let count = 0;

	function update() {

		const start = count;
		const end = geometry.drawRange.count;

		if ( start === end ) return;

		positions.addUpdateRange( start * 3, ( end - start ) * 3 );
		positions.needsUpdate = true;

		normals.addUpdateRange( start * 3, ( end - start ) * 3 );
		normals.needsUpdate = true;

		colors.addUpdateRange( start * 3, ( end - start ) * 3 );
		colors.needsUpdate = true;

		count = geometry.drawRange.count;

	}

	return {
		/**
		 * The "painted" tube mesh. Must be added to the scene.
		 *
		 * @name TubePainter#mesh
		 * @type {Mesh}
		 */
		mesh: mesh,

		/**
		 * Moves the current painting position to the given value.
		 *
		 * @method
		 * @name TubePainter#moveTo
		 * @param {Vector3} position The new painting position.
		 */
		moveTo: moveTo,

		/**
		 * Draw a stroke from the current position to the given one.
		 * This method extends the tube while drawing with the XR
		 * controllers.
		 *
		 * @method
		 * @name TubePainter#lineTo
		 * @param {Vector3} position The destination position.
		 */
		lineTo: lineTo,

		/**
		 * Sets the size of newly rendered tube segments.
		 *
		 * @method
		 * @name TubePainter#setSize
		 * @param {number} size The size.
		 */
		setSize: setSize,

		/**
		 * Updates the internal geometry buffers so the new painted
		 * segments are rendered.
		 *
		 * @method
		 * @name TubePainter#update
		 */
		update: update
	};

}
```
</details>

### `getPoints(size: any): any[]`

**Parameters:**

- **`size`** `any`

**Returns:** `any[]`

**Calls:**

- `array.push`
- `Math.sin`
- `Math.cos`

<details><summary>Code</summary>

```typescript
function getPoints( size ) {

		const PI2 = Math.PI * 2;

		const sides = 10;
		const array = [];
		const radius = 0.01 * size;

		for ( let i = 0; i < sides; i ++ ) {

			const angle = ( i / sides ) * PI2;
			array.push( new Vector3( Math.sin( angle ) * radius, Math.cos( angle ) * radius, 0 ) );

		}

		return array;

	}
```
</details>

### `stroke(position1: any, position2: any, matrix1: any, matrix2: any): void`

**Parameters:**

- **`position1`** `any`
- **`position2`** `any`
- **`matrix1`** `any`
- **`matrix2`** `any`

**Returns:** `void`

**Calls:**

- `position1.distanceToSquared`
- `getPoints`
- `vector1.copy( vertex1 ).applyMatrix4( matrix2 ).add`
- `vector2.copy( vertex2 ).applyMatrix4( matrix2 ).add`
- `vector3.copy( vertex2 ).applyMatrix4( matrix1 ).add`
- `vector4.copy( vertex1 ).applyMatrix4( matrix1 ).add`
- `vector1.toArray`
- `vector2.toArray`
- `vector4.toArray`
- `vector3.toArray`
- `vector1.copy( vertex1 ).applyMatrix4( matrix2 ).normalize`
- `vector2.copy( vertex2 ).applyMatrix4( matrix2 ).normalize`
- `vector3.copy( vertex2 ).applyMatrix4( matrix1 ).normalize`
- `vector4.copy( vertex1 ).applyMatrix4( matrix1 ).normalize`
- `color.toArray`

**Internal Comments:**
```
// positions (x8)
// normals (x8)
// colors (x4)
```

<details><summary>Code</summary>

```typescript
function stroke( position1, position2, matrix1, matrix2 ) {

		if ( position1.distanceToSquared( position2 ) === 0 ) return;

		let count = geometry.drawRange.count;

		const points = getPoints( size );

		for ( let i = 0, il = points.length; i < il; i ++ ) {

			const vertex1 = points[ i ];
			const vertex2 = points[ ( i + 1 ) % il ];

			// positions

			vector1.copy( vertex1 ).applyMatrix4( matrix2 ).add( position2 );
			vector2.copy( vertex2 ).applyMatrix4( matrix2 ).add( position2 );
			vector3.copy( vertex2 ).applyMatrix4( matrix1 ).add( position1 );
			vector4.copy( vertex1 ).applyMatrix4( matrix1 ).add( position1 );

			vector1.toArray( positions.array, ( count + 0 ) * 3 );
			vector2.toArray( positions.array, ( count + 1 ) * 3 );
			vector4.toArray( positions.array, ( count + 2 ) * 3 );

			vector2.toArray( positions.array, ( count + 3 ) * 3 );
			vector3.toArray( positions.array, ( count + 4 ) * 3 );
			vector4.toArray( positions.array, ( count + 5 ) * 3 );

			// normals

			vector1.copy( vertex1 ).applyMatrix4( matrix2 ).normalize();
			vector2.copy( vertex2 ).applyMatrix4( matrix2 ).normalize();
			vector3.copy( vertex2 ).applyMatrix4( matrix1 ).normalize();
			vector4.copy( vertex1 ).applyMatrix4( matrix1 ).normalize();

			vector1.toArray( normals.array, ( count + 0 ) * 3 );
			vector2.toArray( normals.array, ( count + 1 ) * 3 );
			vector4.toArray( normals.array, ( count + 2 ) * 3 );

			vector2.toArray( normals.array, ( count + 3 ) * 3 );
			vector3.toArray( normals.array, ( count + 4 ) * 3 );
			vector4.toArray( normals.array, ( count + 5 ) * 3 );

			// colors

			color.toArray( colors.array, ( count + 0 ) * 3 );
			color.toArray( colors.array, ( count + 1 ) * 3 );
			color.toArray( colors.array, ( count + 2 ) * 3 );

			color.toArray( colors.array, ( count + 3 ) * 3 );
			color.toArray( colors.array, ( count + 4 ) * 3 );
			color.toArray( colors.array, ( count + 5 ) * 3 );

			count += 6;

		}

		geometry.drawRange.count = count;

	}
```
</details>

### `moveTo(position: any): void`

**Parameters:**

- **`position`** `any`

**Returns:** `void`

**Calls:**

- `point1.copy`
- `matrix1.lookAt`
- `point2.copy`
- `matrix2.copy`

<details><summary>Code</summary>

```typescript
function moveTo( position ) {

		point1.copy( position );
		matrix1.lookAt( point2, point1, up );

		point2.copy( position );
		matrix2.copy( matrix1 );

	}
```
</details>

### `lineTo(position: any): void`

**Parameters:**

- **`position`** `any`

**Returns:** `void`

**Calls:**

- `point1.copy`
- `matrix1.lookAt`
- `stroke`
- `point2.copy`
- `matrix2.copy`

<details><summary>Code</summary>

```typescript
function lineTo( position ) {

		point1.copy( position );
		matrix1.lookAt( point2, point1, up );

		stroke( point1, point2, matrix1, matrix2 );

		point2.copy( point1 );
		matrix2.copy( matrix1 );

	}
```
</details>

### `setSize(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setSize( value ) {

		size = value;

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `positions.addUpdateRange`
- `normals.addUpdateRange`
- `colors.addUpdateRange`

<details><summary>Code</summary>

```typescript
function update() {

		const start = count;
		const end = geometry.drawRange.count;

		if ( start === end ) return;

		positions.addUpdateRange( start * 3, ( end - start ) * 3 );
		positions.needsUpdate = true;

		normals.addUpdateRange( start * 3, ( end - start ) * 3 );
		normals.needsUpdate = true;

		colors.addUpdateRange( start * 3, ( end - start ) * 3 );
		colors.needsUpdate = true;

		count = geometry.drawRange.count;

	}
```
</details>


---