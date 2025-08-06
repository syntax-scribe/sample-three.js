[⬅️ Back to Table of Contents](../../index.md)

# 📄 `SpotLightHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/SpotLightHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `Object3D` | `../core/Object3D.js` |
| `LineSegments` | `../objects/LineSegments.js` |
| `LineBasicMaterial` | `../materials/LineBasicMaterial.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `positions` | `number[]` | let/var | `[ 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 0, 0, - 1, 0, 1, 0, 0, 0, 0, 1, 1, 0...` | ✗ |
| `p1` | `number` | let/var | `( i / l ) * Math.PI * 2` | ✗ |
| `p2` | `number` | let/var | `( j / l ) * Math.PI * 2` | ✗ |
| `material` | `LineBasicMaterial` | let/var | `new LineBasicMaterial( { fog: false, toneMapped: false } )` | ✗ |
| `coneLength` | `any` | let/var | `this.light.distance ? this.light.distance : 1000` | ✗ |
| `coneWidth` | `number` | let/var | `coneLength * Math.tan( this.light.angle )` | ✗ |


---

## Functions

### `SpotLightHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.cone.geometry.dispose`
- `this.cone.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.cone.geometry.dispose();
		this.cone.material.dispose();

	}
```
</details>

### `SpotLightHelper.update(): void`

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
- `this.parent.updateWorldMatrix`
- `this.matrix
				.copy( this.parent.matrixWorld )
				.invert()
				.multiply`
- `this.matrix.copy`
- `this.matrixWorld.copy`
- `Math.tan`
- `this.cone.scale.set`
- `_vector.setFromMatrixPosition`
- `this.cone.lookAt`
- `this.cone.material.color.set`
- `this.cone.material.color.copy`

**Internal Comments:**
```
// update the local matrix based on the parent and light target transforms
```

<details><summary>Code</summary>

```typescript
update() {

		this.light.updateWorldMatrix( true, false );
		this.light.target.updateWorldMatrix( true, false );

		// update the local matrix based on the parent and light target transforms
		if ( this.parent ) {

			this.parent.updateWorldMatrix( true );

			this.matrix
				.copy( this.parent.matrixWorld )
				.invert()
				.multiply( this.light.matrixWorld );

		} else {

			this.matrix.copy( this.light.matrixWorld );

		}

		this.matrixWorld.copy( this.light.matrixWorld );

		const coneLength = this.light.distance ? this.light.distance : 1000;
		const coneWidth = coneLength * Math.tan( this.light.angle );

		this.cone.scale.set( coneWidth, coneWidth, coneLength );

		_vector.setFromMatrixPosition( this.light.target.matrixWorld );

		this.cone.lookAt( _vector );

		if ( this.color !== undefined ) {

			this.cone.material.color.set( this.color );

		} else {

			this.cone.material.color.copy( this.light.color );

		}

	}
```
</details>


---

## Classes

### `SpotLightHelper`

<details><summary>Class Code</summary>

```ts
class SpotLightHelper extends Object3D {

	/**
	 * Constructs a new spot light helper.
	 *
	 * @param {HemisphereLight} light - The light to be visualized.
	 * @param {number|Color|string} [color] - The helper's color. If not set, the helper will take
	 * the color of the light.
	 */
	constructor( light, color ) {

		super();

		/**
		 * The light being visualized.
		 *
		 * @type {SpotLight}
		 */
		this.light = light;

		this.matrixAutoUpdate = false;

		/**
		 * The color parameter passed in the constructor.
		 * If not set, the helper will take the color of the light.
		 *
		 * @type {number|Color|string}
		 */
		this.color = color;

		this.type = 'SpotLightHelper';

		const geometry = new BufferGeometry();

		const positions = [
			0, 0, 0, 	0, 0, 1,
			0, 0, 0, 	1, 0, 1,
			0, 0, 0,	- 1, 0, 1,
			0, 0, 0, 	0, 1, 1,
			0, 0, 0, 	0, - 1, 1
		];

		for ( let i = 0, j = 1, l = 32; i < l; i ++, j ++ ) {

			const p1 = ( i / l ) * Math.PI * 2;
			const p2 = ( j / l ) * Math.PI * 2;

			positions.push(
				Math.cos( p1 ), Math.sin( p1 ), 1,
				Math.cos( p2 ), Math.sin( p2 ), 1
			);

		}

		geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );

		const material = new LineBasicMaterial( { fog: false, toneMapped: false } );

		this.cone = new LineSegments( geometry, material );
		this.add( this.cone );

		this.update();

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.cone.geometry.dispose();
		this.cone.material.dispose();

	}

	/**
	 * Updates the helper to match the position and direction of the
	 * light being visualized.
	 */
	update() {

		this.light.updateWorldMatrix( true, false );
		this.light.target.updateWorldMatrix( true, false );

		// update the local matrix based on the parent and light target transforms
		if ( this.parent ) {

			this.parent.updateWorldMatrix( true );

			this.matrix
				.copy( this.parent.matrixWorld )
				.invert()
				.multiply( this.light.matrixWorld );

		} else {

			this.matrix.copy( this.light.matrixWorld );

		}

		this.matrixWorld.copy( this.light.matrixWorld );

		const coneLength = this.light.distance ? this.light.distance : 1000;
		const coneWidth = coneLength * Math.tan( this.light.angle );

		this.cone.scale.set( coneWidth, coneWidth, coneLength );

		_vector.setFromMatrixPosition( this.light.target.matrixWorld );

		this.cone.lookAt( _vector );

		if ( this.color !== undefined ) {

			this.cone.material.color.set( this.color );

		} else {

			this.cone.material.color.copy( this.light.color );

		}

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.cone.geometry.dispose();
		this.cone.material.dispose();

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		this.light.updateWorldMatrix( true, false );
		this.light.target.updateWorldMatrix( true, false );

		// update the local matrix based on the parent and light target transforms
		if ( this.parent ) {

			this.parent.updateWorldMatrix( true );

			this.matrix
				.copy( this.parent.matrixWorld )
				.invert()
				.multiply( this.light.matrixWorld );

		} else {

			this.matrix.copy( this.light.matrixWorld );

		}

		this.matrixWorld.copy( this.light.matrixWorld );

		const coneLength = this.light.distance ? this.light.distance : 1000;
		const coneWidth = coneLength * Math.tan( this.light.angle );

		this.cone.scale.set( coneWidth, coneWidth, coneLength );

		_vector.setFromMatrixPosition( this.light.target.matrixWorld );

		this.cone.lookAt( _vector );

		if ( this.color !== undefined ) {

			this.cone.material.color.set( this.color );

		} else {

			this.cone.material.color.copy( this.light.color );

		}

	}
```
</details>


---