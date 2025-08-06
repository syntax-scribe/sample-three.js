[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CSMHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 48 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/csm/CSMHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Group` | `three` |
| `Mesh` | `three` |
| `LineSegments` | `three` |
| `BufferGeometry` | `three` |
| `LineBasicMaterial` | `three` |
| `Box3Helper` | `three` |
| `Box3` | `three` |
| `PlaneGeometry` | `three` |
| `MeshBasicMaterial` | `three` |
| `BufferAttribute` | `three` |
| `DoubleSide` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indices` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array( [ 0, 1, 1, 2, 2, 3, 3, 0, 4, 5, 5, 6, 6, 7, 7, 4, 0, 4, 1, 5...` | ✗ |
| `positions` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 24 )` | ✗ |
| `frustumGeometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `frustumLines` | `any` | let/var | `new LineSegments( frustumGeometry, new LineBasicMaterial() )` | ✗ |
| `displayFrustum` | `boolean` | let/var | `this.displayFrustum` | ✗ |
| `displayPlanes` | `boolean` | let/var | `this.displayPlanes` | ✗ |
| `displayShadowBounds` | `boolean` | let/var | `this.displayShadowBounds` | ✗ |
| `frustumLines` | `any` | let/var | `this.frustumLines` | ✗ |
| `cascadeLines` | `any[]` | let/var | `this.cascadeLines` | ✗ |
| `cascadePlanes` | `any[]` | let/var | `this.cascadePlanes` | ✗ |
| `shadowLines` | `any[]` | let/var | `this.shadowLines` | ✗ |
| `cascadeLine` | `any` | let/var | `cascadeLines[ i ]` | ✗ |
| `cascadePlane` | `any` | let/var | `cascadePlanes[ i ]` | ✗ |
| `shadowLineGroup` | `any` | let/var | `shadowLines[ i ]` | ✗ |
| `csm` | `any` | let/var | `this.csm` | ✗ |
| `camera` | `any` | let/var | `csm.camera` | ✗ |
| `cascades` | `any` | let/var | `csm.cascades` | ✗ |
| `mainFrustum` | `any` | let/var | `csm.mainFrustum` | ✗ |
| `frustums` | `any` | let/var | `csm.frustums` | ✗ |
| `lights` | `any` | let/var | `csm.lights` | ✗ |
| `frustumLines` | `any` | let/var | `this.frustumLines` | ✗ |
| `cascadeLines` | `any[]` | let/var | `this.cascadeLines` | ✗ |
| `cascadePlanes` | `any[]` | let/var | `this.cascadePlanes` | ✗ |
| `shadowLines` | `any[]` | let/var | `this.shadowLines` | ✗ |
| `cascadeLine` | `any` | let/var | `new Box3Helper( new Box3(), 0xffffff )` | ✗ |
| `planeMat` | `any` | let/var | `new MeshBasicMaterial( { transparent: true, opacity: 0.1, depthWrite: false, ...` | ✗ |
| `cascadePlane` | `any` | let/var | `new Mesh( new PlaneGeometry(), planeMat )` | ✗ |
| `shadowLineGroup` | `any` | let/var | `new Group()` | ✗ |
| `shadowLine` | `any` | let/var | `new Box3Helper( new Box3(), 0xffff00 )` | ✗ |
| `frustum` | `any` | let/var | `frustums[ i ]` | ✗ |
| `light` | `any` | let/var | `lights[ i ]` | ✗ |
| `shadowCam` | `any` | let/var | `light.shadow.camera` | ✗ |
| `farVerts` | `any` | let/var | `frustum.vertices.far` | ✗ |
| `cascadeLine` | `any` | let/var | `cascadeLines[ i ]` | ✗ |
| `cascadePlane` | `any` | let/var | `cascadePlanes[ i ]` | ✗ |
| `shadowLineGroup` | `any` | let/var | `shadowLines[ i ]` | ✗ |
| `shadowLine` | `any` | let/var | `shadowLineGroup.children[ 0 ]` | ✗ |
| `nearVerts` | `any` | let/var | `mainFrustum.vertices.near` | ✗ |
| `farVerts` | `any` | let/var | `mainFrustum.vertices.far` | ✗ |
| `frustumLines` | `any` | let/var | `this.frustumLines` | ✗ |
| `cascadeLines` | `any[]` | let/var | `this.cascadeLines` | ✗ |
| `cascadePlanes` | `any[]` | let/var | `this.cascadePlanes` | ✗ |
| `shadowLines` | `any[]` | let/var | `this.shadowLines` | ✗ |
| `cascades` | `any` | let/var | `this.csm.cascades` | ✗ |
| `cascadeLine` | `any` | let/var | `cascadeLines[ i ]` | ✗ |
| `cascadePlane` | `any` | let/var | `cascadePlanes[ i ]` | ✗ |
| `shadowLineGroup` | `any` | let/var | `shadowLines[ i ]` | ✗ |
| `shadowLine` | `any` | let/var | `shadowLineGroup.children[ 0 ]` | ✗ |


---

## Functions

### `CSMHelper.updateVisibility(): void`

**JSDoc:**
```typescript
/**
	 * This method must be called if one of the `display*` properties is changed at runtime.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateVisibility() {

		const displayFrustum = this.displayFrustum;
		const displayPlanes = this.displayPlanes;
		const displayShadowBounds = this.displayShadowBounds;

		const frustumLines = this.frustumLines;
		const cascadeLines = this.cascadeLines;
		const cascadePlanes = this.cascadePlanes;
		const shadowLines = this.shadowLines;
		for ( let i = 0, l = cascadeLines.length; i < l; i ++ ) {

			const cascadeLine = cascadeLines[ i ];
			const cascadePlane = cascadePlanes[ i ];
			const shadowLineGroup = shadowLines[ i ];

			cascadeLine.visible = displayFrustum;
			cascadePlane.visible = displayFrustum && displayPlanes;
			shadowLineGroup.visible = displayShadowBounds;

		}

		frustumLines.visible = displayFrustum;

	}
```
</details>

### `CSMHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the helper. This method should be called in the app's animation loop.
	 */
```

**Returns:** `void`

**Calls:**

- `frustumLines.geometry.getAttribute`
- `this.position.copy`
- `this.quaternion.copy`
- `this.scale.copy`
- `this.updateMatrixWorld`
- `this.remove`
- `cascadeLines.pop`
- `cascadePlanes.pop`
- `shadowLines.pop`
- `shadowLineGroup.add`
- `this.add`
- `cascadeLines.push`
- `cascadePlanes.push`
- `shadowLines.push`
- `cascadeLine.box.min.copy`
- `cascadeLine.box.max.copy`
- `cascadePlane.position.addVectors`
- `cascadePlane.position.multiplyScalar`
- `cascadePlane.scale.subVectors`
- `shadowLineGroup.position.copy`
- `shadowLineGroup.quaternion.copy`
- `shadowLineGroup.scale.copy`
- `shadowLineGroup.updateMatrixWorld`
- `this.attach`
- `shadowLine.box.min.set`
- `shadowLine.box.max.set`
- `frustumLinePositions.setXYZ`

<details><summary>Code</summary>

```typescript
update() {

		const csm = this.csm;
		const camera = csm.camera;
		const cascades = csm.cascades;
		const mainFrustum = csm.mainFrustum;
		const frustums = csm.frustums;
		const lights = csm.lights;

		const frustumLines = this.frustumLines;
		const frustumLinePositions = frustumLines.geometry.getAttribute( 'position' );
		const cascadeLines = this.cascadeLines;
		const cascadePlanes = this.cascadePlanes;
		const shadowLines = this.shadowLines;

		if ( camera === null ) return;

		this.position.copy( camera.position );
		this.quaternion.copy( camera.quaternion );
		this.scale.copy( camera.scale );
		this.updateMatrixWorld( true );

		while ( cascadeLines.length > cascades ) {

			this.remove( cascadeLines.pop() );
			this.remove( cascadePlanes.pop() );
			this.remove( shadowLines.pop() );

		}

		while ( cascadeLines.length < cascades ) {

			const cascadeLine = new Box3Helper( new Box3(), 0xffffff );
			const planeMat = new MeshBasicMaterial( { transparent: true, opacity: 0.1, depthWrite: false, side: DoubleSide } );
			const cascadePlane = new Mesh( new PlaneGeometry(), planeMat );
			const shadowLineGroup = new Group();
			const shadowLine = new Box3Helper( new Box3(), 0xffff00 );
			shadowLineGroup.add( shadowLine );

			this.add( cascadeLine );
			this.add( cascadePlane );
			this.add( shadowLineGroup );

			cascadeLines.push( cascadeLine );
			cascadePlanes.push( cascadePlane );
			shadowLines.push( shadowLineGroup );

		}

		for ( let i = 0; i < cascades; i ++ ) {

			const frustum = frustums[ i ];
			const light = lights[ i ];
			const shadowCam = light.shadow.camera;
			const farVerts = frustum.vertices.far;

			const cascadeLine = cascadeLines[ i ];
			const cascadePlane = cascadePlanes[ i ];
			const shadowLineGroup = shadowLines[ i ];
			const shadowLine = shadowLineGroup.children[ 0 ];

			cascadeLine.box.min.copy( farVerts[ 2 ] );
			cascadeLine.box.max.copy( farVerts[ 0 ] );
			cascadeLine.box.max.z += 1e-4;

			cascadePlane.position.addVectors( farVerts[ 0 ], farVerts[ 2 ] );
			cascadePlane.position.multiplyScalar( 0.5 );
			cascadePlane.scale.subVectors( farVerts[ 0 ], farVerts[ 2 ] );
			cascadePlane.scale.z = 1e-4;

			this.remove( shadowLineGroup );
			shadowLineGroup.position.copy( shadowCam.position );
			shadowLineGroup.quaternion.copy( shadowCam.quaternion );
			shadowLineGroup.scale.copy( shadowCam.scale );
			shadowLineGroup.updateMatrixWorld( true );
			this.attach( shadowLineGroup );

			shadowLine.box.min.set( shadowCam.bottom, shadowCam.left, - shadowCam.far );
			shadowLine.box.max.set( shadowCam.top, shadowCam.right, - shadowCam.near );

		}

		const nearVerts = mainFrustum.vertices.near;
		const farVerts = mainFrustum.vertices.far;
		frustumLinePositions.setXYZ( 0, farVerts[ 0 ].x, farVerts[ 0 ].y, farVerts[ 0 ].z );
		frustumLinePositions.setXYZ( 1, farVerts[ 3 ].x, farVerts[ 3 ].y, farVerts[ 3 ].z );
		frustumLinePositions.setXYZ( 2, farVerts[ 2 ].x, farVerts[ 2 ].y, farVerts[ 2 ].z );
		frustumLinePositions.setXYZ( 3, farVerts[ 1 ].x, farVerts[ 1 ].y, farVerts[ 1 ].z );

		frustumLinePositions.setXYZ( 4, nearVerts[ 0 ].x, nearVerts[ 0 ].y, nearVerts[ 0 ].z );
		frustumLinePositions.setXYZ( 5, nearVerts[ 3 ].x, nearVerts[ 3 ].y, nearVerts[ 3 ].z );
		frustumLinePositions.setXYZ( 6, nearVerts[ 2 ].x, nearVerts[ 2 ].y, nearVerts[ 2 ].z );
		frustumLinePositions.setXYZ( 7, nearVerts[ 1 ].x, nearVerts[ 1 ].y, nearVerts[ 1 ].z );
		frustumLinePositions.needsUpdate = true;

	}
```
</details>

### `CSMHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `frustumLines.geometry.dispose`
- `frustumLines.material.dispose`
- `cascadeLine.dispose`
- `cascadePlane.geometry.dispose`
- `cascadePlane.material.dispose`
- `shadowLine.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		const frustumLines = this.frustumLines;
		const cascadeLines = this.cascadeLines;
		const cascadePlanes = this.cascadePlanes;
		const shadowLines = this.shadowLines;

		frustumLines.geometry.dispose();
		frustumLines.material.dispose();

		const cascades = this.csm.cascades;

		for ( let i = 0; i < cascades; i ++ ) {

			const cascadeLine = cascadeLines[ i ];
			const cascadePlane = cascadePlanes[ i ];
			const shadowLineGroup = shadowLines[ i ];
			const shadowLine = shadowLineGroup.children[ 0 ];

			cascadeLine.dispose(); // Box3Helper

			cascadePlane.geometry.dispose();
			cascadePlane.material.dispose();

			shadowLine.dispose(); // Box3Helper

		}

	}
```
</details>


---

## Classes

### `CSMHelper`

<details><summary>Class Code</summary>

```ts
class CSMHelper extends Group {

	/**
	 * Constructs a new CSM helper.
	 *
	 * @param {CSM|CSMShadowNode} csm - The CSM instance to visualize.
	 */
	constructor( csm ) {

		super();

		/**
		 * The CSM instance to visualize.
		 *
		 * @type {CSM|CSMShadowNode}
		 */
		this.csm = csm;

		/**
		 * Whether to display the CSM frustum or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.displayFrustum = true;

		/**
		 * Whether to display the cascade planes or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.displayPlanes = true;

		/**
		 * Whether to display the shadow bounds or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.displayShadowBounds = true;

		const indices = new Uint16Array( [ 0, 1, 1, 2, 2, 3, 3, 0, 4, 5, 5, 6, 6, 7, 7, 4, 0, 4, 1, 5, 2, 6, 3, 7 ] );
		const positions = new Float32Array( 24 );
		const frustumGeometry = new BufferGeometry();
		frustumGeometry.setIndex( new BufferAttribute( indices, 1 ) );
		frustumGeometry.setAttribute( 'position', new BufferAttribute( positions, 3, false ) );
		const frustumLines = new LineSegments( frustumGeometry, new LineBasicMaterial() );
		this.add( frustumLines );

		this.frustumLines = frustumLines;
		this.cascadeLines = [];
		this.cascadePlanes = [];
		this.shadowLines = [];

	}

	/**
	 * This method must be called if one of the `display*` properties is changed at runtime.
	 */
	updateVisibility() {

		const displayFrustum = this.displayFrustum;
		const displayPlanes = this.displayPlanes;
		const displayShadowBounds = this.displayShadowBounds;

		const frustumLines = this.frustumLines;
		const cascadeLines = this.cascadeLines;
		const cascadePlanes = this.cascadePlanes;
		const shadowLines = this.shadowLines;
		for ( let i = 0, l = cascadeLines.length; i < l; i ++ ) {

			const cascadeLine = cascadeLines[ i ];
			const cascadePlane = cascadePlanes[ i ];
			const shadowLineGroup = shadowLines[ i ];

			cascadeLine.visible = displayFrustum;
			cascadePlane.visible = displayFrustum && displayPlanes;
			shadowLineGroup.visible = displayShadowBounds;

		}

		frustumLines.visible = displayFrustum;

	}

	/**
	 * Updates the helper. This method should be called in the app's animation loop.
	 */
	update() {

		const csm = this.csm;
		const camera = csm.camera;
		const cascades = csm.cascades;
		const mainFrustum = csm.mainFrustum;
		const frustums = csm.frustums;
		const lights = csm.lights;

		const frustumLines = this.frustumLines;
		const frustumLinePositions = frustumLines.geometry.getAttribute( 'position' );
		const cascadeLines = this.cascadeLines;
		const cascadePlanes = this.cascadePlanes;
		const shadowLines = this.shadowLines;

		if ( camera === null ) return;

		this.position.copy( camera.position );
		this.quaternion.copy( camera.quaternion );
		this.scale.copy( camera.scale );
		this.updateMatrixWorld( true );

		while ( cascadeLines.length > cascades ) {

			this.remove( cascadeLines.pop() );
			this.remove( cascadePlanes.pop() );
			this.remove( shadowLines.pop() );

		}

		while ( cascadeLines.length < cascades ) {

			const cascadeLine = new Box3Helper( new Box3(), 0xffffff );
			const planeMat = new MeshBasicMaterial( { transparent: true, opacity: 0.1, depthWrite: false, side: DoubleSide } );
			const cascadePlane = new Mesh( new PlaneGeometry(), planeMat );
			const shadowLineGroup = new Group();
			const shadowLine = new Box3Helper( new Box3(), 0xffff00 );
			shadowLineGroup.add( shadowLine );

			this.add( cascadeLine );
			this.add( cascadePlane );
			this.add( shadowLineGroup );

			cascadeLines.push( cascadeLine );
			cascadePlanes.push( cascadePlane );
			shadowLines.push( shadowLineGroup );

		}

		for ( let i = 0; i < cascades; i ++ ) {

			const frustum = frustums[ i ];
			const light = lights[ i ];
			const shadowCam = light.shadow.camera;
			const farVerts = frustum.vertices.far;

			const cascadeLine = cascadeLines[ i ];
			const cascadePlane = cascadePlanes[ i ];
			const shadowLineGroup = shadowLines[ i ];
			const shadowLine = shadowLineGroup.children[ 0 ];

			cascadeLine.box.min.copy( farVerts[ 2 ] );
			cascadeLine.box.max.copy( farVerts[ 0 ] );
			cascadeLine.box.max.z += 1e-4;

			cascadePlane.position.addVectors( farVerts[ 0 ], farVerts[ 2 ] );
			cascadePlane.position.multiplyScalar( 0.5 );
			cascadePlane.scale.subVectors( farVerts[ 0 ], farVerts[ 2 ] );
			cascadePlane.scale.z = 1e-4;

			this.remove( shadowLineGroup );
			shadowLineGroup.position.copy( shadowCam.position );
			shadowLineGroup.quaternion.copy( shadowCam.quaternion );
			shadowLineGroup.scale.copy( shadowCam.scale );
			shadowLineGroup.updateMatrixWorld( true );
			this.attach( shadowLineGroup );

			shadowLine.box.min.set( shadowCam.bottom, shadowCam.left, - shadowCam.far );
			shadowLine.box.max.set( shadowCam.top, shadowCam.right, - shadowCam.near );

		}

		const nearVerts = mainFrustum.vertices.near;
		const farVerts = mainFrustum.vertices.far;
		frustumLinePositions.setXYZ( 0, farVerts[ 0 ].x, farVerts[ 0 ].y, farVerts[ 0 ].z );
		frustumLinePositions.setXYZ( 1, farVerts[ 3 ].x, farVerts[ 3 ].y, farVerts[ 3 ].z );
		frustumLinePositions.setXYZ( 2, farVerts[ 2 ].x, farVerts[ 2 ].y, farVerts[ 2 ].z );
		frustumLinePositions.setXYZ( 3, farVerts[ 1 ].x, farVerts[ 1 ].y, farVerts[ 1 ].z );

		frustumLinePositions.setXYZ( 4, nearVerts[ 0 ].x, nearVerts[ 0 ].y, nearVerts[ 0 ].z );
		frustumLinePositions.setXYZ( 5, nearVerts[ 3 ].x, nearVerts[ 3 ].y, nearVerts[ 3 ].z );
		frustumLinePositions.setXYZ( 6, nearVerts[ 2 ].x, nearVerts[ 2 ].y, nearVerts[ 2 ].z );
		frustumLinePositions.setXYZ( 7, nearVerts[ 1 ].x, nearVerts[ 1 ].y, nearVerts[ 1 ].z );
		frustumLinePositions.needsUpdate = true;

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		const frustumLines = this.frustumLines;
		const cascadeLines = this.cascadeLines;
		const cascadePlanes = this.cascadePlanes;
		const shadowLines = this.shadowLines;

		frustumLines.geometry.dispose();
		frustumLines.material.dispose();

		const cascades = this.csm.cascades;

		for ( let i = 0; i < cascades; i ++ ) {

			const cascadeLine = cascadeLines[ i ];
			const cascadePlane = cascadePlanes[ i ];
			const shadowLineGroup = shadowLines[ i ];
			const shadowLine = shadowLineGroup.children[ 0 ];

			cascadeLine.dispose(); // Box3Helper

			cascadePlane.geometry.dispose();
			cascadePlane.material.dispose();

			shadowLine.dispose(); // Box3Helper

		}

	}

}
```
</details>

#### Methods

##### `updateVisibility(): void`

<details><summary>Code</summary>

```ts
updateVisibility() {

		const displayFrustum = this.displayFrustum;
		const displayPlanes = this.displayPlanes;
		const displayShadowBounds = this.displayShadowBounds;

		const frustumLines = this.frustumLines;
		const cascadeLines = this.cascadeLines;
		const cascadePlanes = this.cascadePlanes;
		const shadowLines = this.shadowLines;
		for ( let i = 0, l = cascadeLines.length; i < l; i ++ ) {

			const cascadeLine = cascadeLines[ i ];
			const cascadePlane = cascadePlanes[ i ];
			const shadowLineGroup = shadowLines[ i ];

			cascadeLine.visible = displayFrustum;
			cascadePlane.visible = displayFrustum && displayPlanes;
			shadowLineGroup.visible = displayShadowBounds;

		}

		frustumLines.visible = displayFrustum;

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const csm = this.csm;
		const camera = csm.camera;
		const cascades = csm.cascades;
		const mainFrustum = csm.mainFrustum;
		const frustums = csm.frustums;
		const lights = csm.lights;

		const frustumLines = this.frustumLines;
		const frustumLinePositions = frustumLines.geometry.getAttribute( 'position' );
		const cascadeLines = this.cascadeLines;
		const cascadePlanes = this.cascadePlanes;
		const shadowLines = this.shadowLines;

		if ( camera === null ) return;

		this.position.copy( camera.position );
		this.quaternion.copy( camera.quaternion );
		this.scale.copy( camera.scale );
		this.updateMatrixWorld( true );

		while ( cascadeLines.length > cascades ) {

			this.remove( cascadeLines.pop() );
			this.remove( cascadePlanes.pop() );
			this.remove( shadowLines.pop() );

		}

		while ( cascadeLines.length < cascades ) {

			const cascadeLine = new Box3Helper( new Box3(), 0xffffff );
			const planeMat = new MeshBasicMaterial( { transparent: true, opacity: 0.1, depthWrite: false, side: DoubleSide } );
			const cascadePlane = new Mesh( new PlaneGeometry(), planeMat );
			const shadowLineGroup = new Group();
			const shadowLine = new Box3Helper( new Box3(), 0xffff00 );
			shadowLineGroup.add( shadowLine );

			this.add( cascadeLine );
			this.add( cascadePlane );
			this.add( shadowLineGroup );

			cascadeLines.push( cascadeLine );
			cascadePlanes.push( cascadePlane );
			shadowLines.push( shadowLineGroup );

		}

		for ( let i = 0; i < cascades; i ++ ) {

			const frustum = frustums[ i ];
			const light = lights[ i ];
			const shadowCam = light.shadow.camera;
			const farVerts = frustum.vertices.far;

			const cascadeLine = cascadeLines[ i ];
			const cascadePlane = cascadePlanes[ i ];
			const shadowLineGroup = shadowLines[ i ];
			const shadowLine = shadowLineGroup.children[ 0 ];

			cascadeLine.box.min.copy( farVerts[ 2 ] );
			cascadeLine.box.max.copy( farVerts[ 0 ] );
			cascadeLine.box.max.z += 1e-4;

			cascadePlane.position.addVectors( farVerts[ 0 ], farVerts[ 2 ] );
			cascadePlane.position.multiplyScalar( 0.5 );
			cascadePlane.scale.subVectors( farVerts[ 0 ], farVerts[ 2 ] );
			cascadePlane.scale.z = 1e-4;

			this.remove( shadowLineGroup );
			shadowLineGroup.position.copy( shadowCam.position );
			shadowLineGroup.quaternion.copy( shadowCam.quaternion );
			shadowLineGroup.scale.copy( shadowCam.scale );
			shadowLineGroup.updateMatrixWorld( true );
			this.attach( shadowLineGroup );

			shadowLine.box.min.set( shadowCam.bottom, shadowCam.left, - shadowCam.far );
			shadowLine.box.max.set( shadowCam.top, shadowCam.right, - shadowCam.near );

		}

		const nearVerts = mainFrustum.vertices.near;
		const farVerts = mainFrustum.vertices.far;
		frustumLinePositions.setXYZ( 0, farVerts[ 0 ].x, farVerts[ 0 ].y, farVerts[ 0 ].z );
		frustumLinePositions.setXYZ( 1, farVerts[ 3 ].x, farVerts[ 3 ].y, farVerts[ 3 ].z );
		frustumLinePositions.setXYZ( 2, farVerts[ 2 ].x, farVerts[ 2 ].y, farVerts[ 2 ].z );
		frustumLinePositions.setXYZ( 3, farVerts[ 1 ].x, farVerts[ 1 ].y, farVerts[ 1 ].z );

		frustumLinePositions.setXYZ( 4, nearVerts[ 0 ].x, nearVerts[ 0 ].y, nearVerts[ 0 ].z );
		frustumLinePositions.setXYZ( 5, nearVerts[ 3 ].x, nearVerts[ 3 ].y, nearVerts[ 3 ].z );
		frustumLinePositions.setXYZ( 6, nearVerts[ 2 ].x, nearVerts[ 2 ].y, nearVerts[ 2 ].z );
		frustumLinePositions.setXYZ( 7, nearVerts[ 1 ].x, nearVerts[ 1 ].y, nearVerts[ 1 ].z );
		frustumLinePositions.needsUpdate = true;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		const frustumLines = this.frustumLines;
		const cascadeLines = this.cascadeLines;
		const cascadePlanes = this.cascadePlanes;
		const shadowLines = this.shadowLines;

		frustumLines.geometry.dispose();
		frustumLines.material.dispose();

		const cascades = this.csm.cascades;

		for ( let i = 0; i < cascades; i ++ ) {

			const cascadeLine = cascadeLines[ i ];
			const cascadePlane = cascadePlanes[ i ];
			const shadowLineGroup = shadowLines[ i ];
			const shadowLine = shadowLineGroup.children[ 0 ];

			cascadeLine.dispose(); // Box3Helper

			cascadePlane.geometry.dispose();
			cascadePlane.material.dispose();

			shadowLine.dispose(); // Box3Helper

		}

	}
```
</details>


---