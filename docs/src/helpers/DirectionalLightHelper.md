[⬅️ Back to Table of Contents](../../index.md)

# 📄 `DirectionalLightHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/DirectionalLightHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `Object3D` | `../core/Object3D.js` |
| `Line` | `../objects/Line.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `LineBasicMaterial` | `../materials/LineBasicMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_v1` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_v2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_v3` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `LineBasicMaterial` | let/var | `new LineBasicMaterial( { fog: false, toneMapped: false } )` | ✗ |


---

## Functions

### `DirectionalLightHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.lightPlane.geometry.dispose`
- `this.lightPlane.material.dispose`
- `this.targetLine.geometry.dispose`
- `this.targetLine.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.lightPlane.geometry.dispose();
		this.lightPlane.material.dispose();
		this.targetLine.geometry.dispose();
		this.targetLine.material.dispose();

	}
```
</details>

### `DirectionalLightHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the helper to match the position and direction of the
	 * light being visualized.
	 */
```

**Returns:** `void`

**Calls:**

- `this.light.updateWorldMatrix`
- `this.light.target.updateWorldMatrix`
- `_v1.setFromMatrixPosition`
- `_v2.setFromMatrixPosition`
- `_v3.subVectors`
- `this.lightPlane.lookAt`
- `this.lightPlane.material.color.set`
- `this.targetLine.material.color.set`
- `this.lightPlane.material.color.copy`
- `this.targetLine.material.color.copy`
- `this.targetLine.lookAt`
- `_v3.length`

<details><summary>Code</summary>

```typescript
update() {

		this.light.updateWorldMatrix( true, false );
		this.light.target.updateWorldMatrix( true, false );

		_v1.setFromMatrixPosition( this.light.matrixWorld );
		_v2.setFromMatrixPosition( this.light.target.matrixWorld );
		_v3.subVectors( _v2, _v1 );

		this.lightPlane.lookAt( _v2 );

		if ( this.color !== undefined ) {

			this.lightPlane.material.color.set( this.color );
			this.targetLine.material.color.set( this.color );

		} else {

			this.lightPlane.material.color.copy( this.light.color );
			this.targetLine.material.color.copy( this.light.color );

		}

		this.targetLine.lookAt( _v2 );
		this.targetLine.scale.z = _v3.length();

	}
```
</details>


---

## Classes

### `DirectionalLightHelper`

<details><summary>Class Code</summary>

```ts
class DirectionalLightHelper extends Object3D {

	/**
	 * Constructs a new directional light helper.
	 *
	 * @param {DirectionalLight} light - The light to be visualized.
	 * @param {number} [size=1] - The dimensions of the plane.
	 * @param {number|Color|string} [color] - The helper's color. If not set, the helper will take
	 * the color of the light.
	 */
	constructor( light, size, color ) {

		super();

		/**
		 * The light being visualized.
		 *
		 * @type {DirectionalLight}
		 */
		this.light = light;

		this.matrix = light.matrixWorld;
		this.matrixAutoUpdate = false;

		/**
		 * The color parameter passed in the constructor.
		 * If not set, the helper will take the color of the light.
		 *
		 * @type {number|Color|string}
		 */
		this.color = color;

		this.type = 'DirectionalLightHelper';

		if ( size === undefined ) size = 1;

		let geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( [
			- size, size, 0,
			size, size, 0,
			size, - size, 0,
			- size, - size, 0,
			- size, size, 0
		], 3 ) );

		const material = new LineBasicMaterial( { fog: false, toneMapped: false } );

		/**
		 * Contains the line showing the location of the directional light.
		 *
		 * @type {Line}
		 */
		this.lightPlane = new Line( geometry, material );
		this.add( this.lightPlane );

		geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( [ 0, 0, 0, 0, 0, 1 ], 3 ) );

		/**
		 * Represents the target line of the directional light.
		 *
		 * @type {Line}
		 */
		this.targetLine = new Line( geometry, material );
		this.add( this.targetLine );

		this.update();

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.lightPlane.geometry.dispose();
		this.lightPlane.material.dispose();
		this.targetLine.geometry.dispose();
		this.targetLine.material.dispose();

	}

	/**
	 * Updates the helper to match the position and direction of the
	 * light being visualized.
	 */
	update() {

		this.light.updateWorldMatrix( true, false );
		this.light.target.updateWorldMatrix( true, false );

		_v1.setFromMatrixPosition( this.light.matrixWorld );
		_v2.setFromMatrixPosition( this.light.target.matrixWorld );
		_v3.subVectors( _v2, _v1 );

		this.lightPlane.lookAt( _v2 );

		if ( this.color !== undefined ) {

			this.lightPlane.material.color.set( this.color );
			this.targetLine.material.color.set( this.color );

		} else {

			this.lightPlane.material.color.copy( this.light.color );
			this.targetLine.material.color.copy( this.light.color );

		}

		this.targetLine.lookAt( _v2 );
		this.targetLine.scale.z = _v3.length();

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.lightPlane.geometry.dispose();
		this.lightPlane.material.dispose();
		this.targetLine.geometry.dispose();
		this.targetLine.material.dispose();

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		this.light.updateWorldMatrix( true, false );
		this.light.target.updateWorldMatrix( true, false );

		_v1.setFromMatrixPosition( this.light.matrixWorld );
		_v2.setFromMatrixPosition( this.light.target.matrixWorld );
		_v3.subVectors( _v2, _v1 );

		this.lightPlane.lookAt( _v2 );

		if ( this.color !== undefined ) {

			this.lightPlane.material.color.set( this.color );
			this.targetLine.material.color.set( this.color );

		} else {

			this.lightPlane.material.color.copy( this.light.color );
			this.targetLine.material.color.copy( this.light.color );

		}

		this.targetLine.lookAt( _v2 );
		this.targetLine.scale.z = _v3.length();

	}
```
</details>


---