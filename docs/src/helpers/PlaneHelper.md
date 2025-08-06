[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PlaneHelper.js`

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
📂 **`src/helpers/PlaneHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Line` | `../objects/Line.js` |
| `Mesh` | `../objects/Mesh.js` |
| `LineBasicMaterial` | `../materials/LineBasicMaterial.js` |
| `MeshBasicMaterial` | `../materials/MeshBasicMaterial.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `color` | `any` | let/var | `hex` | ✗ |
| `positions` | `number[]` | let/var | `[ 1, - 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, - 1,...` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `positions2` | `number[]` | let/var | `[ 1, 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, 1, 0, - 1, - 1, 0, 1, - 1, 0 ]` | ✗ |
| `geometry2` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |


---

## Functions

### `PlaneHelper.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `this.position.set`
- `this.scale.set`
- `this.lookAt`
- `this.translateZ`
- `super.updateMatrixWorld`

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		this.position.set( 0, 0, 0 );

		this.scale.set( 0.5 * this.size, 0.5 * this.size, 1 );

		this.lookAt( this.plane.normal );

		this.translateZ( - this.plane.constant );

		super.updateMatrixWorld( force );

	}
```
</details>

### `PlaneHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Updates the helper to match the position and direction of the
	 * light being visualized.
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

### `PlaneHelper`

<details><summary>Class Code</summary>

```ts
class PlaneHelper extends Line {

	/**
	 * Constructs a new plane helper.
	 *
	 * @param {Plane} plane - The plane to be visualized.
	 * @param {number} [size=1] - The side length of plane helper.
	 * @param {number|Color|string} [hex=0xffff00] - The helper's color.
	 */
	constructor( plane, size = 1, hex = 0xffff00 ) {

		const color = hex;

		const positions = [ 1, - 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, - 1, 0, 1, 1, 0 ];

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );
		geometry.computeBoundingSphere();

		super( geometry, new LineBasicMaterial( { color: color, toneMapped: false } ) );

		this.type = 'PlaneHelper';

		/**
		 * The plane being visualized.
		 *
		 * @type {Plane}
		 */
		this.plane = plane;

		/**
		 * The side length of plane helper.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.size = size;

		const positions2 = [ 1, 1, 0, - 1, 1, 0, - 1, - 1, 0, 1, 1, 0, - 1, - 1, 0, 1, - 1, 0 ];

		const geometry2 = new BufferGeometry();
		geometry2.setAttribute( 'position', new Float32BufferAttribute( positions2, 3 ) );
		geometry2.computeBoundingSphere();

		this.add( new Mesh( geometry2, new MeshBasicMaterial( { color: color, opacity: 0.2, transparent: true, depthWrite: false, toneMapped: false } ) ) );

	}

	updateMatrixWorld( force ) {

		this.position.set( 0, 0, 0 );

		this.scale.set( 0.5 * this.size, 0.5 * this.size, 1 );

		this.lookAt( this.plane.normal );

		this.translateZ( - this.plane.constant );

		super.updateMatrixWorld( force );

	}

	/**
	 * Updates the helper to match the position and direction of the
	 * light being visualized.
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

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		this.position.set( 0, 0, 0 );

		this.scale.set( 0.5 * this.size, 0.5 * this.size, 1 );

		this.lookAt( this.plane.normal );

		this.translateZ( - this.plane.constant );

		super.updateMatrixWorld( force );

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