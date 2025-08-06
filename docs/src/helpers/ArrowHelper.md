[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ArrowHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/ArrowHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Object3D` | `../core/Object3D.js` |
| `ConeGeometry` | `../geometries/ConeGeometry.js` |
| `MeshBasicMaterial` | `../materials/MeshBasicMaterial.js` |
| `LineBasicMaterial` | `../materials/LineBasicMaterial.js` |
| `Mesh` | `../objects/Mesh.js` |
| `Line` | `../objects/Line.js` |
| `Vector3` | `../math/Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_axis` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_lineGeometry` | `any` | let/var | `*not shown*` | ✗ |
| `_coneGeometry` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `ArrowHelper.setDirection(dir: Vector3): void`

**JSDoc:**
```typescript
/**
	 * Sets the direction of the helper.
	 *
	 * @param {Vector3} dir - The normalized direction vector.
	 */
```

**Parameters:**

- **`dir`** `Vector3`

**Returns:** `void`

**Calls:**

- `this.quaternion.set`
- `_axis.set( dir.z, 0, - dir.x ).normalize`
- `Math.acos`
- `this.quaternion.setFromAxisAngle`

**Internal Comments:**
```
// dir is assumed to be normalized
```

<details><summary>Code</summary>

```typescript
setDirection( dir ) {

		// dir is assumed to be normalized

		if ( dir.y > 0.99999 ) {

			this.quaternion.set( 0, 0, 0, 1 );

		} else if ( dir.y < - 0.99999 ) {

			this.quaternion.set( 1, 0, 0, 0 );

		} else {

			_axis.set( dir.z, 0, - dir.x ).normalize();

			const radians = Math.acos( dir.y );

			this.quaternion.setFromAxisAngle( _axis, radians );

		}

	}
```
</details>

### `ArrowHelper.setLength(length: number, headLength: number, headWidth: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the length of the helper.
	 *
	 * @param {number} length - Length of the arrow in world units.
	 * @param {number} [headLength=length*0.2] - The length of the head of the arrow.
	 * @param {number} [headWidth=headLength*0.2] - The width of the head of the arrow.
	 */
```

**Parameters:**

- **`length`** `number`
- **`headLength`** `number`
- **`headWidth`** `number`

**Returns:** `void`

**Calls:**

- `this.line.scale.set`
- `Math.max`
- `this.line.updateMatrix`
- `this.cone.scale.set`
- `this.cone.updateMatrix`

<details><summary>Code</summary>

```typescript
setLength( length, headLength = length * 0.2, headWidth = headLength * 0.2 ) {

		this.line.scale.set( 1, Math.max( 0.0001, length - headLength ), 1 ); // see #17458
		this.line.updateMatrix();

		this.cone.scale.set( headWidth, headLength, headWidth );
		this.cone.position.y = length;
		this.cone.updateMatrix();

	}
```
</details>

### `ArrowHelper.setColor(color: any): void`

**JSDoc:**
```typescript
/**
	 * Sets the color of the helper.
	 *
	 * @param {number|Color|string} color - The color to set.
	 */
```

**Parameters:**

- **`color`** `any`

**Returns:** `void`

**Calls:**

- `this.line.material.color.set`
- `this.cone.material.color.set`

<details><summary>Code</summary>

```typescript
setColor( color ) {

		this.line.material.color.set( color );
		this.cone.material.color.set( color );

	}
```
</details>

### `ArrowHelper.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.line.copy`
- `this.cone.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source, false );

		this.line.copy( source.line );
		this.cone.copy( source.cone );

		return this;

	}
```
</details>

### `ArrowHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.line.geometry.dispose`
- `this.line.material.dispose`
- `this.cone.geometry.dispose`
- `this.cone.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.line.geometry.dispose();
		this.line.material.dispose();
		this.cone.geometry.dispose();
		this.cone.material.dispose();

	}
```
</details>


---

## Classes

### `ArrowHelper`

<details><summary>Class Code</summary>

```ts
class ArrowHelper extends Object3D {

	/**
	 * Constructs a new arrow helper.
	 *
	 * @param {Vector3} [dir=(0, 0, 1)] - The (normalized) direction vector.
	 * @param {Vector3} [origin=(0, 0, 0)] - Point at which the arrow starts.
	 * @param {number} [length=1] - Length of the arrow in world units.
	 * @param {(number|Color|string)} [color=0xffff00] - Color of the arrow.
	 * @param {number} [headLength=length*0.2] - The length of the head of the arrow.
	 * @param {number} [headWidth=headLength*0.2] - The width of the head of the arrow.
	 */
	constructor( dir = new Vector3( 0, 0, 1 ), origin = new Vector3( 0, 0, 0 ), length = 1, color = 0xffff00, headLength = length * 0.2, headWidth = headLength * 0.2 ) {

		super();

		this.type = 'ArrowHelper';

		if ( _lineGeometry === undefined ) {

			_lineGeometry = new BufferGeometry();
			_lineGeometry.setAttribute( 'position', new Float32BufferAttribute( [ 0, 0, 0, 0, 1, 0 ], 3 ) );

			_coneGeometry = new ConeGeometry( 0.5, 1, 5, 1 );
			_coneGeometry.translate( 0, - 0.5, 0 );

		}

		this.position.copy( origin );

		/**
		 * The line part of the arrow helper.
		 *
		 * @type {Line}
		 */
		this.line = new Line( _lineGeometry, new LineBasicMaterial( { color: color, toneMapped: false } ) );
		this.line.matrixAutoUpdate = false;
		this.add( this.line );

		/**
		 * The cone part of the arrow helper.
		 *
		 * @type {Mesh}
		 */
		this.cone = new Mesh( _coneGeometry, new MeshBasicMaterial( { color: color, toneMapped: false } ) );
		this.cone.matrixAutoUpdate = false;
		this.add( this.cone );

		this.setDirection( dir );
		this.setLength( length, headLength, headWidth );

	}

	/**
	 * Sets the direction of the helper.
	 *
	 * @param {Vector3} dir - The normalized direction vector.
	 */
	setDirection( dir ) {

		// dir is assumed to be normalized

		if ( dir.y > 0.99999 ) {

			this.quaternion.set( 0, 0, 0, 1 );

		} else if ( dir.y < - 0.99999 ) {

			this.quaternion.set( 1, 0, 0, 0 );

		} else {

			_axis.set( dir.z, 0, - dir.x ).normalize();

			const radians = Math.acos( dir.y );

			this.quaternion.setFromAxisAngle( _axis, radians );

		}

	}

	/**
	 * Sets the length of the helper.
	 *
	 * @param {number} length - Length of the arrow in world units.
	 * @param {number} [headLength=length*0.2] - The length of the head of the arrow.
	 * @param {number} [headWidth=headLength*0.2] - The width of the head of the arrow.
	 */
	setLength( length, headLength = length * 0.2, headWidth = headLength * 0.2 ) {

		this.line.scale.set( 1, Math.max( 0.0001, length - headLength ), 1 ); // see #17458
		this.line.updateMatrix();

		this.cone.scale.set( headWidth, headLength, headWidth );
		this.cone.position.y = length;
		this.cone.updateMatrix();

	}

	/**
	 * Sets the color of the helper.
	 *
	 * @param {number|Color|string} color - The color to set.
	 */
	setColor( color ) {

		this.line.material.color.set( color );
		this.cone.material.color.set( color );

	}

	copy( source ) {

		super.copy( source, false );

		this.line.copy( source.line );
		this.cone.copy( source.cone );

		return this;

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.line.geometry.dispose();
		this.line.material.dispose();
		this.cone.geometry.dispose();
		this.cone.material.dispose();

	}

}
```
</details>

#### Methods

##### `setDirection(dir: Vector3): void`

<details><summary>Code</summary>

```ts
setDirection( dir ) {

		// dir is assumed to be normalized

		if ( dir.y > 0.99999 ) {

			this.quaternion.set( 0, 0, 0, 1 );

		} else if ( dir.y < - 0.99999 ) {

			this.quaternion.set( 1, 0, 0, 0 );

		} else {

			_axis.set( dir.z, 0, - dir.x ).normalize();

			const radians = Math.acos( dir.y );

			this.quaternion.setFromAxisAngle( _axis, radians );

		}

	}
```
</details>

##### `setLength(length: number, headLength: number, headWidth: number): void`

<details><summary>Code</summary>

```ts
setLength( length, headLength = length * 0.2, headWidth = headLength * 0.2 ) {

		this.line.scale.set( 1, Math.max( 0.0001, length - headLength ), 1 ); // see #17458
		this.line.updateMatrix();

		this.cone.scale.set( headWidth, headLength, headWidth );
		this.cone.position.y = length;
		this.cone.updateMatrix();

	}
```
</details>

##### `setColor(color: any): void`

<details><summary>Code</summary>

```ts
setColor( color ) {

		this.line.material.color.set( color );
		this.cone.material.color.set( color );

	}
```
</details>

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source, false );

		this.line.copy( source.line );
		this.cone.copy( source.cone );

		return this;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.line.geometry.dispose();
		this.line.material.dispose();
		this.cone.geometry.dispose();
		this.cone.material.dispose();

	}
```
</details>


---