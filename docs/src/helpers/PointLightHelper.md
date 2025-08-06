[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PointLightHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/PointLightHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Mesh` | `../objects/Mesh.js` |
| `MeshBasicMaterial` | `../materials/MeshBasicMaterial.js` |
| `SphereGeometry` | `../geometries/SphereGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometry` | `SphereGeometry` | let/var | `new SphereGeometry( sphereSize, 4, 2 )` | ✗ |
| `material` | `MeshBasicMaterial` | let/var | `new MeshBasicMaterial( { wireframe: true, fog: false, toneMapped: false } )` | ✗ |


---

## Functions

### `PointLightHelper.dispose(): void`

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

<details><summary>Code</summary>

```typescript
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>

### `PointLightHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the helper to match the position of the
	 * light being visualized.
	 */
```

**Returns:** `void`

**Calls:**

- `this.light.updateWorldMatrix`
- `this.material.color.set`
- `this.material.color.copy`

<details><summary>Code</summary>

```typescript
update() {

		this.light.updateWorldMatrix( true, false );

		if ( this.color !== undefined ) {

			this.material.color.set( this.color );

		} else {

			this.material.color.copy( this.light.color );

		}

		/*
		const d = this.light.distance;

		if ( d === 0.0 ) {

			this.lightDistance.visible = false;

		} else {

			this.lightDistance.visible = true;
			this.lightDistance.scale.set( d, d, d );

		}
		*/

	}
```
</details>


---

## Classes

### `PointLightHelper`

<details><summary>Class Code</summary>

```ts
class PointLightHelper extends Mesh {

	/**
	 * Constructs a new point light helper.
	 *
	 * @param {PointLight} light - The light to be visualized.
	 * @param {number} [sphereSize=1] - The size of the sphere helper.
	 * @param {number|Color|string} [color] - The helper's color. If not set, the helper will take
	 * the color of the light.
	 */
	constructor( light, sphereSize, color ) {

		const geometry = new SphereGeometry( sphereSize, 4, 2 );
		const material = new MeshBasicMaterial( { wireframe: true, fog: false, toneMapped: false } );

		super( geometry, material );

		/**
		 * The light being visualized.
		 *
		 * @type {HemisphereLight}
		 */
		this.light = light;

		/**
		 * The color parameter passed in the constructor.
		 * If not set, the helper will take the color of the light.
		 *
		 * @type {number|Color|string}
		 */
		this.color = color;

		this.type = 'PointLightHelper';

		this.matrix = this.light.matrixWorld;
		this.matrixAutoUpdate = false;

		this.update();


		/*
	// TODO: delete this comment?
	const distanceGeometry = new THREE.IcosahedronGeometry( 1, 2 );
	const distanceMaterial = new THREE.MeshBasicMaterial( { color: hexColor, fog: false, wireframe: true, opacity: 0.1, transparent: true } );

	this.lightSphere = new THREE.Mesh( bulbGeometry, bulbMaterial );
	this.lightDistance = new THREE.Mesh( distanceGeometry, distanceMaterial );

	const d = light.distance;

	if ( d === 0.0 ) {

		this.lightDistance.visible = false;

	} else {

		this.lightDistance.scale.set( d, d, d );

	}

	this.add( this.lightDistance );
	*/

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}

	/**
	 * Updates the helper to match the position of the
	 * light being visualized.
	 */
	update() {

		this.light.updateWorldMatrix( true, false );

		if ( this.color !== undefined ) {

			this.material.color.set( this.color );

		} else {

			this.material.color.copy( this.light.color );

		}

		/*
		const d = this.light.distance;

		if ( d === 0.0 ) {

			this.lightDistance.visible = false;

		} else {

			this.lightDistance.visible = true;
			this.lightDistance.scale.set( d, d, d );

		}
		*/

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		this.light.updateWorldMatrix( true, false );

		if ( this.color !== undefined ) {

			this.material.color.set( this.color );

		} else {

			this.material.color.copy( this.light.color );

		}

		/*
		const d = this.light.distance;

		if ( d === 0.0 ) {

			this.lightDistance.visible = false;

		} else {

			this.lightDistance.visible = true;
			this.lightDistance.scale.set( d, d, d );

		}
		*/

	}
```
</details>


---