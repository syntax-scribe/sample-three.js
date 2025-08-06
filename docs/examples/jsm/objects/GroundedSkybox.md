[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `GroundedSkybox.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/GroundedSkybox.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `SphereGeometry` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometry` | `any` | let/var | `new SphereGeometry( radius, 2 * resolution, resolution )` | ✗ |
| `tmp` | `any` | let/var | `new Vector3()` | ✗ |
| `y1` | `number` | let/var | `- height * 3 / 2` | ✗ |
| `f` | `number` | let/var | `tmp.y < y1 ? - height / tmp.y : ( 1 - tmp.y * tmp.y / ( 3 * y1 * y1 ) )` | ✗ |


---

## Classes

### `GroundedSkybox`

<details><summary>Class Code</summary>

```ts
class GroundedSkybox extends Mesh {

	/**
	 * Constructs a new ground-projected skybox.
	 *
	 * @param {Texture} map - The environment map to use.
	 * @param {number} height - The height is how far the camera that took the photo was above the ground.
	 * A larger value will magnify the downward part of the image.
	 * @param {number} radius - The radius of the skybox. Must be large enough to ensure the scene's camera stays inside.
	 * @param {number} [resolution=128] - The geometry resolution of the skybox.
	 */
	constructor( map, height, radius, resolution = 128 ) {

		if ( height <= 0 || radius <= 0 || resolution <= 0 ) {

			throw new Error( 'GroundedSkybox height, radius, and resolution must be positive.' );

		}

		const geometry = new SphereGeometry( radius, 2 * resolution, resolution );
		geometry.scale( 1, 1, - 1 );

		const pos = geometry.getAttribute( 'position' );
		const tmp = new Vector3();

		for ( let i = 0; i < pos.count; ++ i ) {

			tmp.fromBufferAttribute( pos, i );
			if ( tmp.y < 0 ) {

				// Smooth out the transition from flat floor to sphere:
				const y1 = - height * 3 / 2;
				const f =
						tmp.y < y1 ? - height / tmp.y : ( 1 - tmp.y * tmp.y / ( 3 * y1 * y1 ) );
				tmp.multiplyScalar( f );
				tmp.toArray( pos.array, 3 * i );

			}

		}

		pos.needsUpdate = true;

		super( geometry, new MeshBasicMaterial( { map, depthWrite: false } ) );

	}

}
```
</details>


---