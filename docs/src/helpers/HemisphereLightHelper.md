[⬅️ Back to Table of Contents](../../index.md)

# 📄 `HemisphereLightHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/HemisphereLightHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `Color` | `../math/Color.js` |
| `Object3D` | `../core/Object3D.js` |
| `Mesh` | `../objects/Mesh.js` |
| `MeshBasicMaterial` | `../materials/MeshBasicMaterial.js` |
| `OctahedronGeometry` | `../geometries/OctahedronGeometry.js` |
| `BufferAttribute` | `../core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_color1` | `Color` | let/var | `new Color()` | ✗ |
| `_color2` | `Color` | let/var | `new Color()` | ✗ |
| `geometry` | `OctahedronGeometry` | let/var | `new OctahedronGeometry( size )` | ✗ |
| `colors` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( position.count * 3 )` | ✗ |
| `mesh` | `Object3D` | let/var | `this.children[ 0 ]` | ✗ |
| `color` | `Color` | let/var | `( i < ( l / 2 ) ) ? _color1 : _color2` | ✗ |


---

## Functions

### `HemisphereLightHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.children[ 0 ].geometry.dispose`
- `this.children[ 0 ].material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.children[ 0 ].geometry.dispose();
		this.children[ 0 ].material.dispose();

	}
```
</details>

### `HemisphereLightHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the helper to match the position and direction of the
	 * light being visualized.
	 */
```

**Returns:** `void`

**Calls:**

- `this.material.color.set`
- `mesh.geometry.getAttribute`
- `_color1.copy`
- `_color2.copy`
- `colors.setXYZ`
- `this.light.updateWorldMatrix`
- `mesh.lookAt`
- `_vector.setFromMatrixPosition( this.light.matrixWorld ).negate`

<details><summary>Code</summary>

```typescript
update() {

		const mesh = this.children[ 0 ];

		if ( this.color !== undefined ) {

			this.material.color.set( this.color );

		} else {

			const colors = mesh.geometry.getAttribute( 'color' );

			_color1.copy( this.light.color );
			_color2.copy( this.light.groundColor );

			for ( let i = 0, l = colors.count; i < l; i ++ ) {

				const color = ( i < ( l / 2 ) ) ? _color1 : _color2;

				colors.setXYZ( i, color.r, color.g, color.b );

			}

			colors.needsUpdate = true;

		}

		this.light.updateWorldMatrix( true, false );

		mesh.lookAt( _vector.setFromMatrixPosition( this.light.matrixWorld ).negate() );

	}
```
</details>


---

## Classes

### `HemisphereLightHelper`

<details><summary>Class Code</summary>

```ts
class HemisphereLightHelper extends Object3D {

	/**
	 * Constructs a new hemisphere light helper.
	 *
	 * @param {HemisphereLight} light - The light to be visualized.
	 * @param {number} [size=1] - The size of the mesh used to visualize the light.
	 * @param {number|Color|string} [color] - The helper's color. If not set, the helper will take
	 * the color of the light.
	 */
	constructor( light, size, color ) {

		super();

		/**
		 * The light being visualized.
		 *
		 * @type {HemisphereLight}
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

		this.type = 'HemisphereLightHelper';

		const geometry = new OctahedronGeometry( size );
		geometry.rotateY( Math.PI * 0.5 );

		this.material = new MeshBasicMaterial( { wireframe: true, fog: false, toneMapped: false } );
		if ( this.color === undefined ) this.material.vertexColors = true;

		const position = geometry.getAttribute( 'position' );
		const colors = new Float32Array( position.count * 3 );

		geometry.setAttribute( 'color', new BufferAttribute( colors, 3 ) );

		this.add( new Mesh( geometry, this.material ) );

		this.update();

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.children[ 0 ].geometry.dispose();
		this.children[ 0 ].material.dispose();

	}

	/**
	 * Updates the helper to match the position and direction of the
	 * light being visualized.
	 */
	update() {

		const mesh = this.children[ 0 ];

		if ( this.color !== undefined ) {

			this.material.color.set( this.color );

		} else {

			const colors = mesh.geometry.getAttribute( 'color' );

			_color1.copy( this.light.color );
			_color2.copy( this.light.groundColor );

			for ( let i = 0, l = colors.count; i < l; i ++ ) {

				const color = ( i < ( l / 2 ) ) ? _color1 : _color2;

				colors.setXYZ( i, color.r, color.g, color.b );

			}

			colors.needsUpdate = true;

		}

		this.light.updateWorldMatrix( true, false );

		mesh.lookAt( _vector.setFromMatrixPosition( this.light.matrixWorld ).negate() );

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.children[ 0 ].geometry.dispose();
		this.children[ 0 ].material.dispose();

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const mesh = this.children[ 0 ];

		if ( this.color !== undefined ) {

			this.material.color.set( this.color );

		} else {

			const colors = mesh.geometry.getAttribute( 'color' );

			_color1.copy( this.light.color );
			_color2.copy( this.light.groundColor );

			for ( let i = 0, l = colors.count; i < l; i ++ ) {

				const color = ( i < ( l / 2 ) ) ? _color1 : _color2;

				colors.setXYZ( i, color.r, color.g, color.b );

			}

			colors.needsUpdate = true;

		}

		this.light.updateWorldMatrix( true, false );

		mesh.lookAt( _vector.setFromMatrixPosition( this.light.matrixWorld ).negate() );

	}
```
</details>


---