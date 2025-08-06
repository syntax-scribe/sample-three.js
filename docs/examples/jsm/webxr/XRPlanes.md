[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `XRPlanes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/webxr/XRPlanes.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BoxGeometry` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `Object3D` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `currentPlanes` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `xr` | `any` | let/var | `renderer.xr` | ✗ |
| `frame` | `any` | let/var | `event.data` | ✗ |
| `planes` | `any` | let/var | `frame.detectedPlanes` | ✗ |
| `planeschanged` | `boolean` | let/var | `false` | ✗ |
| `polygon` | `any` | let/var | `plane.polygon` | ✗ |
| `minX` | `number` | let/var | `Number.MAX_SAFE_INTEGER` | ✗ |
| `maxX` | `number` | let/var | `Number.MIN_SAFE_INTEGER` | ✗ |
| `minZ` | `number` | let/var | `Number.MAX_SAFE_INTEGER` | ✗ |
| `maxZ` | `number` | let/var | `Number.MIN_SAFE_INTEGER` | ✗ |
| `width` | `number` | let/var | `maxX - minX` | ✗ |
| `height` | `number` | let/var | `maxZ - minZ` | ✗ |
| `geometry` | `any` | let/var | `new BoxGeometry( width, 0.01, height )` | ✗ |
| `material` | `any` | let/var | `new MeshBasicMaterial( { color: 0xffffff * Math.random() } )` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( geometry, material )` | ✗ |


---

## Classes

### `XRPlanes`

<details><summary>Class Code</summary>

```ts
class XRPlanes extends Object3D {

	/**
	 * Constructs a new XR plane container.
	 *
	 * @param {WebGLRenderer|WebGPURenderer} renderer - The renderer.
	 */
	constructor( renderer ) {

		super();

		const matrix = new Matrix4();

		const currentPlanes = new Map();

		const xr = renderer.xr;

		xr.addEventListener( 'planesdetected', event => {

			const frame = event.data;
			const planes = frame.detectedPlanes;

			const referenceSpace = xr.getReferenceSpace();

			let planeschanged = false;

			for ( const [ plane, mesh ] of currentPlanes ) {

				if ( planes.has( plane ) === false ) {

					mesh.geometry.dispose();
					mesh.material.dispose();
					this.remove( mesh );

					currentPlanes.delete( plane );

					planeschanged = true;

				}

			}

			for ( const plane of planes ) {

				if ( currentPlanes.has( plane ) === false ) {

					const pose = frame.getPose( plane.planeSpace, referenceSpace );
					matrix.fromArray( pose.transform.matrix );

					const polygon = plane.polygon;

					let minX = Number.MAX_SAFE_INTEGER;
					let maxX = Number.MIN_SAFE_INTEGER;
					let minZ = Number.MAX_SAFE_INTEGER;
					let maxZ = Number.MIN_SAFE_INTEGER;

					for ( const point of polygon ) {

						minX = Math.min( minX, point.x );
						maxX = Math.max( maxX, point.x );
						minZ = Math.min( minZ, point.z );
						maxZ = Math.max( maxZ, point.z );

					}

					const width = maxX - minX;
					const height = maxZ - minZ;

					const geometry = new BoxGeometry( width, 0.01, height );
					const material = new MeshBasicMaterial( { color: 0xffffff * Math.random() } );

					const mesh = new Mesh( geometry, material );
					mesh.position.setFromMatrixPosition( matrix );
					mesh.quaternion.setFromRotationMatrix( matrix );
					this.add( mesh );

					currentPlanes.set( plane, mesh );

					planeschanged = true;

				}

			}

			if ( planeschanged ) {

				this.dispatchEvent( { type: 'planeschanged' } );

			}

		} );

	}

}
```
</details>


---