[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RectAreaLightHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/RectAreaLightHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BackSide` | `three` |
| `BufferGeometry` | `three` |
| `Float32BufferAttribute` | `three` |
| `Line` | `three` |
| `LineBasicMaterial` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `positions` | `number[]` | let/var | `[ 1, 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, - 1, 0, 1, 1, 0 ]` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `any` | let/var | `new LineBasicMaterial( { fog: false } )` | ✗ |
| `positions2` | `number[]` | let/var | `[ 1, 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, 1, 0, - 1, - 1, 0, 1, - 1, 0 ]` | ✗ |
| `geometry2` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `c` | `any` | let/var | `this.material.color` | ✗ |


---

## Functions

### `RectAreaLightHelper.updateMatrixWorld(): void`

**Returns:** `void`

**Calls:**

- `this.scale.set`
- `this.material.color.set`
- `this.children[ 0 ].material.color.set`
- `this.material.color.copy( this.light.color ).multiplyScalar`
- `Math.max`
- `c.multiplyScalar`
- `this.children[ 0 ].material.color.copy`
- `this.matrixWorld.extractRotation( this.light.matrixWorld ).scale( this.scale ).copyPosition`
- `this.children[ 0 ].matrixWorld.copy`

**Internal Comments:**
```
// prevent hue shift (x2)
// ignore world scale on light (x9)
```

<details><summary>Code</summary>

```typescript
updateMatrixWorld() {

		this.scale.set( 0.5 * this.light.width, 0.5 * this.light.height, 1 );

		if ( this.color !== undefined ) {

			this.material.color.set( this.color );
			this.children[ 0 ].material.color.set( this.color );

		} else {

			this.material.color.copy( this.light.color ).multiplyScalar( this.light.intensity );

			// prevent hue shift
			const c = this.material.color;
			const max = Math.max( c.r, c.g, c.b );
			if ( max > 1 ) c.multiplyScalar( 1 / max );

			this.children[ 0 ].material.color.copy( this.material.color );

		}

		// ignore world scale on light
		this.matrixWorld.extractRotation( this.light.matrixWorld ).scale( this.scale ).copyPosition( this.light.matrixWorld );

		this.children[ 0 ].matrixWorld.copy( this.matrixWorld );

	}
```
</details>

### `RectAreaLightHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.geometry.dispose`
- `this.material.dispose`
- `this.children[ 0 ].geometry.dispose`
- `this.children[ 0 ].material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.geometry.dispose();
		this.material.dispose();
		this.children[ 0 ].geometry.dispose();
		this.children[ 0 ].material.dispose();

	}
```
</details>


---

## Classes

### `RectAreaLightHelper`

<details><summary>Class Code</summary>

```ts
class RectAreaLightHelper extends Line {

	/**
	 * Constructs a new rect area light helper.
	 *
	 * @param {RectAreaLight} light - The light to visualize.
	 * @param {number|Color|string} [color] - The helper's color.
	 * If this is not the set, the helper will take the color of the light.
	 */
	constructor( light, color ) {

		const positions = [ 1, 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, - 1, 0, 1, 1, 0 ];

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );
		geometry.computeBoundingSphere();

		const material = new LineBasicMaterial( { fog: false } );

		super( geometry, material );

		/**
		 * The light to visualize.
		 *
		 * @type {RectAreaLight}
		 */
		this.light = light;

		/**
		 * The helper's color. If `undefined`, the helper will take the color of the light.
		 *
		 * @type {number|Color|string|undefined}
		 */
		this.color = color;

		this.type = 'RectAreaLightHelper';

		//

		const positions2 = [ 1, 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, 1, 0, - 1, - 1, 0, 1, - 1, 0 ];

		const geometry2 = new BufferGeometry();
		geometry2.setAttribute( 'position', new Float32BufferAttribute( positions2, 3 ) );
		geometry2.computeBoundingSphere();

		this.add( new Mesh( geometry2, new MeshBasicMaterial( { side: BackSide, fog: false } ) ) );

	}

	updateMatrixWorld() {

		this.scale.set( 0.5 * this.light.width, 0.5 * this.light.height, 1 );

		if ( this.color !== undefined ) {

			this.material.color.set( this.color );
			this.children[ 0 ].material.color.set( this.color );

		} else {

			this.material.color.copy( this.light.color ).multiplyScalar( this.light.intensity );

			// prevent hue shift
			const c = this.material.color;
			const max = Math.max( c.r, c.g, c.b );
			if ( max > 1 ) c.multiplyScalar( 1 / max );

			this.children[ 0 ].material.color.copy( this.material.color );

		}

		// ignore world scale on light
		this.matrixWorld.extractRotation( this.light.matrixWorld ).scale( this.scale ).copyPosition( this.light.matrixWorld );

		this.children[ 0 ].matrixWorld.copy( this.matrixWorld );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.geometry.dispose();
		this.material.dispose();
		this.children[ 0 ].geometry.dispose();
		this.children[ 0 ].material.dispose();

	}

}
```
</details>

#### Methods

##### `updateMatrixWorld(): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld() {

		this.scale.set( 0.5 * this.light.width, 0.5 * this.light.height, 1 );

		if ( this.color !== undefined ) {

			this.material.color.set( this.color );
			this.children[ 0 ].material.color.set( this.color );

		} else {

			this.material.color.copy( this.light.color ).multiplyScalar( this.light.intensity );

			// prevent hue shift
			const c = this.material.color;
			const max = Math.max( c.r, c.g, c.b );
			if ( max > 1 ) c.multiplyScalar( 1 / max );

			this.children[ 0 ].material.color.copy( this.material.color );

		}

		// ignore world scale on light
		this.matrixWorld.extractRotation( this.light.matrixWorld ).scale( this.scale ).copyPosition( this.light.matrixWorld );

		this.children[ 0 ].matrixWorld.copy( this.matrixWorld );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.geometry.dispose();
		this.material.dispose();
		this.children[ 0 ].geometry.dispose();
		this.children[ 0 ].material.dispose();

	}
```
</details>


---