[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `OculusHandPointerModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 16 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 45 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/webxr/OculusHandPointerModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Float32BufferAttribute` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `Object3D` | `three` |
| `Raycaster` | `three` |
| `SphereGeometry` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `PINCH_MAX` | `0.05` | let/var | `0.05` | ✗ |
| `PINCH_THRESHOLD` | `0.02` | let/var | `0.02` | ✗ |
| `PINCH_MIN` | `0.01` | let/var | `0.01` | ✗ |
| `POINTER_ADVANCE_MAX` | `0.02` | let/var | `0.02` | ✗ |
| `POINTER_OPACITY_MAX` | `1` | let/var | `1` | ✗ |
| `POINTER_OPACITY_MIN` | `0.4` | let/var | `0.4` | ✗ |
| `POINTER_FRONT_RADIUS` | `0.002` | let/var | `0.002` | ✗ |
| `POINTER_REAR_RADIUS` | `0.01` | let/var | `0.01` | ✗ |
| `POINTER_REAR_RADIUS_MIN` | `0.003` | let/var | `0.003` | ✗ |
| `POINTER_LENGTH` | `0.035` | let/var | `0.035` | ✗ |
| `POINTER_SEGMENTS` | `16` | let/var | `16` | ✗ |
| `POINTER_RINGS` | `12` | let/var | `12` | ✗ |
| `POINTER_HEMISPHERE_ANGLE` | `110` | let/var | `110` | ✗ |
| `YAXIS` | `any` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `ZAXIS` | `any` | let/var | `new Vector3( 0, 0, 1 )` | ✗ |
| `CURSOR_RADIUS` | `0.02` | let/var | `0.02` | ✗ |
| `CURSOR_MAX_DISTANCE` | `1.5` | let/var | `1.5` | ✗ |
| `xrInputSource` | `any` | let/var | `event.data` | ✗ |
| `vid` | `number` | let/var | `ringIndex * POINTER_SEGMENTS + i` | ✗ |
| `vertices` | `any` | let/var | `this.pointerGeometry.attributes.position.array` | ✗ |
| `frontFaceBase` | `any` | let/var | `new Vector3( POINTER_FRONT_RADIUS, 0, - 1 * ( POINTER_LENGTH - rearRadius ) )` | ✗ |
| `rearBase` | `any` | let/var | `new Vector3( Math.sin( ( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 ) * rearR...` | ✗ |
| `frontCenterIndex` | `number` | let/var | `POINTER_SEGMENTS * ( 1 + POINTER_RINGS )` | ✗ |
| `rearCenterIndex` | `number` | let/var | `POINTER_SEGMENTS * ( 1 + POINTER_RINGS ) + 1` | ✗ |
| `frontCenter` | `any` | let/var | `new Vector3( 0, 0, - 1 * ( POINTER_LENGTH - rearRadius ) )` | ✗ |
| `rearCenter` | `any` | let/var | `new Vector3( 0, 0, rearRadius )` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `frontCenterIndex` | `number` | let/var | `POINTER_SEGMENTS * ( 1 + POINTER_RINGS )` | ✗ |
| `rearCenterIndex` | `number` | let/var | `POINTER_SEGMENTS * ( 1 + POINTER_RINGS ) + 1` | ✗ |
| `material` | `any` | let/var | `new MeshBasicMaterial()` | ✗ |
| `cursorGeometry` | `any` | let/var | `new SphereGeometry( CURSOR_RADIUS, 10, 10 )` | ✗ |
| `cursorMaterial` | `any` | let/var | `new MeshBasicMaterial()` | ✗ |
| `pointerMatrix` | `any` | let/var | `this.pointerObject.matrixWorld` | ✗ |
| `tempMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `indexTip` | `any` | let/var | `this.hand.joints[ 'index-finger-tip' ]` | ✗ |
| `thumbTip` | `any` | let/var | `this.hand.joints[ 'thumb-tip' ]` | ✗ |
| `pinchScale` | `number` | let/var | `( distance - PINCH_MIN ) / ( PINCH_MAX - PINCH_MIN )` | ✗ |
| `focusScale` | `number` | let/var | `( distance - PINCH_MIN ) / ( PINCH_THRESHOLD - PINCH_MIN )` | ✗ |
| `rearRadius` | `number` | let/var | `( POINTER_REAR_RADIUS - POINTER_REAR_RADIUS_MIN ) * pinchScale + POINTER_REAR...` | ✗ |
| `direction` | `any` | let/var | `new Vector3( 0, 0, - 1 )` | ✗ |
| `intersection` | `any` | let/var | `intersections[ 0 ]` | ✗ |
| `distance` | `any` | let/var | `intersection.distance` | ✗ |
| `direction` | `any` | let/var | `new Vector3( 0, 0, - 1 )` | ✗ |


---

## Functions

### `OculusHandPointerModel._onConnected(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this.createPointer`

<details><summary>Code</summary>

```typescript
_onConnected( event ) {

		const xrInputSource = event.data;
		if ( xrInputSource.hand ) {

			this.visible = true;
			this.xrInputSource = xrInputSource;

			this.createPointer();

		}

	}
```
</details>

### `OculusHandPointerModel._onDisconnected(): void`

**Returns:** `void`

**Calls:**

- `this.pointerGeometry.dispose`
- `this.pointerMesh.material.dispose`
- `this.clear`

<details><summary>Code</summary>

```typescript
_onDisconnected() {

		this.visible = false;
		this.xrInputSource = null;

		if ( this.pointerGeometry ) this.pointerGeometry.dispose();
		if ( this.pointerMesh && this.pointerMesh.material ) this.pointerMesh.material.dispose();

		this.clear();

	}
```
</details>

### `OculusHandPointerModel._drawVerticesRing(vertices: any, baseVector: any, ringIndex: any): void`

**Parameters:**

- **`vertices`** `any`
- **`baseVector`** `any`
- **`ringIndex`** `any`

**Returns:** `void`

**Calls:**

- `baseVector.clone`
- `segmentVector.applyAxisAngle`

<details><summary>Code</summary>

```typescript
_drawVerticesRing( vertices, baseVector, ringIndex ) {

		const segmentVector = baseVector.clone();
		for ( let i = 0; i < POINTER_SEGMENTS; i ++ ) {

			segmentVector.applyAxisAngle( ZAXIS, ( Math.PI * 2 ) / POINTER_SEGMENTS );
			const vid = ringIndex * POINTER_SEGMENTS + i;
			vertices[ 3 * vid ] = segmentVector.x;
			vertices[ 3 * vid + 1 ] = segmentVector.y;
			vertices[ 3 * vid + 2 ] = segmentVector.z;

		}

	}
```
</details>

### `OculusHandPointerModel._updatePointerVertices(rearRadius: any): void`

**Parameters:**

- **`rearRadius`** `any`

**Returns:** `void`

**Calls:**

- `this._drawVerticesRing`
- `Math.sin`
- `Math.cos`
- `rearBase.applyAxisAngle`
- `this.pointerGeometry.setAttribute`

**Internal Comments:**
```
// first ring for front face (x2)
// rings for rear hemisphere (x2)
// front and rear face center vertices (x2)
```

<details><summary>Code</summary>

```typescript
_updatePointerVertices( rearRadius ) {

		const vertices = this.pointerGeometry.attributes.position.array;
		// first ring for front face
		const frontFaceBase = new Vector3(
			POINTER_FRONT_RADIUS,
			0,
			- 1 * ( POINTER_LENGTH - rearRadius )
		);
		this._drawVerticesRing( vertices, frontFaceBase, 0 );

		// rings for rear hemisphere
		const rearBase = new Vector3(
			Math.sin( ( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 ) * rearRadius,
			Math.cos( ( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 ) * rearRadius,
			0
		);
		for ( let i = 0; i < POINTER_RINGS; i ++ ) {

			this._drawVerticesRing( vertices, rearBase, i + 1 );
			rearBase.applyAxisAngle(
				YAXIS,
				( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 / ( POINTER_RINGS * - 2 )
			);

		}

		// front and rear face center vertices
		const frontCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS );
		const rearCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS ) + 1;
		const frontCenter = new Vector3(
			0,
			0,
			- 1 * ( POINTER_LENGTH - rearRadius )
		);
		vertices[ frontCenterIndex * 3 ] = frontCenter.x;
		vertices[ frontCenterIndex * 3 + 1 ] = frontCenter.y;
		vertices[ frontCenterIndex * 3 + 2 ] = frontCenter.z;
		const rearCenter = new Vector3( 0, 0, rearRadius );
		vertices[ rearCenterIndex * 3 ] = rearCenter.x;
		vertices[ rearCenterIndex * 3 + 1 ] = rearCenter.y;
		vertices[ rearCenterIndex * 3 + 2 ] = rearCenter.z;

		this.pointerGeometry.setAttribute(
			'position',
			new Float32BufferAttribute( vertices, 3 )
		);
		// verticesNeedUpdate = true;

	}
```
</details>

### `OculusHandPointerModel.createPointer(): void`

**JSDoc:**
```typescript
/**
	 * Creates a pointer mesh and adds it to this model.
	 */
```

**Returns:** `void`

**Calls:**

- `new Array(
			( ( POINTER_RINGS + 1 ) * POINTER_SEGMENTS + 2 ) * 3
		).fill`
- `this.pointerGeometry.setAttribute`
- `this._updatePointerVertices`
- `indices.push`
- `this.pointerGeometry.setIndex`
- `this.pointerMesh.position.set`
- `this.pointerObject.add`
- `this.add`

**Internal Comments:**
```
// const vertices = []; (x2)
// construct faces to connect rings
// construct front and rear face (x2)
// create cursor (x2)
```

<details><summary>Code</summary>

```typescript
createPointer() {

		let i, j;
		const vertices = new Array(
			( ( POINTER_RINGS + 1 ) * POINTER_SEGMENTS + 2 ) * 3
		).fill( 0 );
		// const vertices = [];
		const indices = [];
		this.pointerGeometry = new BufferGeometry();

		this.pointerGeometry.setAttribute(
			'position',
			new Float32BufferAttribute( vertices, 3 )
		);

		this._updatePointerVertices( POINTER_REAR_RADIUS );

		// construct faces to connect rings
		for ( i = 0; i < POINTER_RINGS; i ++ ) {

			for ( j = 0; j < POINTER_SEGMENTS - 1; j ++ ) {

				indices.push(
					i * POINTER_SEGMENTS + j,
					i * POINTER_SEGMENTS + j + 1,
					( i + 1 ) * POINTER_SEGMENTS + j
				);
				indices.push(
					i * POINTER_SEGMENTS + j + 1,
					( i + 1 ) * POINTER_SEGMENTS + j + 1,
					( i + 1 ) * POINTER_SEGMENTS + j
				);

			}

			indices.push(
				( i + 1 ) * POINTER_SEGMENTS - 1,
				i * POINTER_SEGMENTS,
				( i + 2 ) * POINTER_SEGMENTS - 1
			);
			indices.push(
				i * POINTER_SEGMENTS,
				( i + 1 ) * POINTER_SEGMENTS,
				( i + 2 ) * POINTER_SEGMENTS - 1
			);

		}

		// construct front and rear face
		const frontCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS );
		const rearCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS ) + 1;

		for ( i = 0; i < POINTER_SEGMENTS - 1; i ++ ) {

			indices.push( frontCenterIndex, i + 1, i );
			indices.push(
				rearCenterIndex,
				i + POINTER_SEGMENTS * POINTER_RINGS,
				i + POINTER_SEGMENTS * POINTER_RINGS + 1
			);

		}

		indices.push( frontCenterIndex, 0, POINTER_SEGMENTS - 1 );
		indices.push(
			rearCenterIndex,
			POINTER_SEGMENTS * ( POINTER_RINGS + 1 ) - 1,
			POINTER_SEGMENTS * POINTER_RINGS
		);

		const material = new MeshBasicMaterial();
		material.transparent = true;
		material.opacity = POINTER_OPACITY_MIN;

		this.pointerGeometry.setIndex( indices );

		this.pointerMesh = new Mesh( this.pointerGeometry, material );

		this.pointerMesh.position.set( 0, 0, - 1 * POINTER_REAR_RADIUS );
		this.pointerObject = new Object3D();
		this.pointerObject.add( this.pointerMesh );

		this.raycaster = new Raycaster();

		// create cursor
		const cursorGeometry = new SphereGeometry( CURSOR_RADIUS, 10, 10 );
		const cursorMaterial = new MeshBasicMaterial();
		cursorMaterial.transparent = true;
		cursorMaterial.opacity = POINTER_OPACITY_MIN;

		this.cursorObject = new Mesh( cursorGeometry, cursorMaterial );
		this.pointerObject.add( this.cursorObject );

		this.add( this.pointerObject );

	}
```
</details>

### `OculusHandPointerModel._updateRaycaster(): void`

**Returns:** `void`

**Calls:**

- `tempMatrix.identity().extractRotation`
- `this.raycaster.ray.origin.setFromMatrixPosition`
- `this.raycaster.ray.direction.set( 0, 0, - 1 ).applyMatrix4`

<details><summary>Code</summary>

```typescript
_updateRaycaster() {

		if ( this.raycaster ) {

			const pointerMatrix = this.pointerObject.matrixWorld;
			const tempMatrix = new Matrix4();
			tempMatrix.identity().extractRotation( pointerMatrix );
			this.raycaster.ray.origin.setFromMatrixPosition( pointerMatrix );
			this.raycaster.ray.direction.set( 0, 0, - 1 ).applyMatrix4( tempMatrix );

		}

	}
```
</details>

### `OculusHandPointerModel._updatePointer(): void`

**Returns:** `void`

**Calls:**

- `indexTip.position.distanceTo`
- `indexTip.position
			.clone()
			.add( thumbTip.position )
			.multiplyScalar`
- `this.pointerObject.position.copy`
- `this.pointerObject.quaternion.copy`
- `this._updatePointerVertices`
- `this.pointerMesh.position.set`

<details><summary>Code</summary>

```typescript
_updatePointer() {

		this.pointerObject.visible = this.controller.visible;
		const indexTip = this.hand.joints[ 'index-finger-tip' ];
		const thumbTip = this.hand.joints[ 'thumb-tip' ];
		const distance = indexTip.position.distanceTo( thumbTip.position );
		const position = indexTip.position
			.clone()
			.add( thumbTip.position )
			.multiplyScalar( 0.5 );
		this.pointerObject.position.copy( position );
		this.pointerObject.quaternion.copy( this.controller.quaternion );

		this.pinched = distance <= PINCH_THRESHOLD;

		const pinchScale = ( distance - PINCH_MIN ) / ( PINCH_MAX - PINCH_MIN );
		const focusScale = ( distance - PINCH_MIN ) / ( PINCH_THRESHOLD - PINCH_MIN );
		if ( pinchScale > 1 ) {

			this._updatePointerVertices( POINTER_REAR_RADIUS );
			this.pointerMesh.position.set( 0, 0, - 1 * POINTER_REAR_RADIUS );
			this.pointerMesh.material.opacity = POINTER_OPACITY_MIN;

		} else if ( pinchScale > 0 ) {

			const rearRadius =
        ( POINTER_REAR_RADIUS - POINTER_REAR_RADIUS_MIN ) * pinchScale +
        POINTER_REAR_RADIUS_MIN;
			this._updatePointerVertices( rearRadius );
			if ( focusScale < 1 ) {

				this.pointerMesh.position.set(
					0,
					0,
					- 1 * rearRadius - ( 1 - focusScale ) * POINTER_ADVANCE_MAX
				);
				this.pointerMesh.material.opacity =
          POINTER_OPACITY_MIN +
          ( 1 - focusScale ) * ( POINTER_OPACITY_MAX - POINTER_OPACITY_MIN );

			} else {

				this.pointerMesh.position.set( 0, 0, - 1 * rearRadius );
				this.pointerMesh.material.opacity = POINTER_OPACITY_MIN;

			}

		} else {

			this._updatePointerVertices( POINTER_REAR_RADIUS_MIN );
			this.pointerMesh.position.set(
				0,
				0,
				- 1 * POINTER_REAR_RADIUS_MIN - POINTER_ADVANCE_MAX
			);
			this.pointerMesh.material.opacity = POINTER_OPACITY_MAX;

		}

		this.cursorObject.material.opacity = this.pointerMesh.material.opacity;

	}
```
</details>

### `OculusHandPointerModel.updateMatrixWorld(force: boolean): void`

**JSDoc:**
```typescript
/**
	 * Overwritten with a custom implementation. Makes sure the internal pointer and raycaster are updated.
	 *
	 * @param {boolean} [force=false] - When set to `true`, a recomputation of world matrices is forced even
	 * when {@link Object3D#matrixWorldAutoUpdate} is set to `false`.
	 */
```

**Parameters:**

- **`force`** `boolean`

**Returns:** `void`

**Calls:**

- `super.updateMatrixWorld`
- `this._updatePointer`
- `this._updateRaycaster`

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );
		if ( this.pointerGeometry ) {

			this._updatePointer();
			this._updateRaycaster();

		}

	}
```
</details>

### `OculusHandPointerModel.isPinched(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` is the model is pinched.
	 *
	 * @return {boolean} Whether the model is pinched or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isPinched() {

		return this.pinched;

	}
```
</details>

### `OculusHandPointerModel.setAttached(attached: boolean): void`

**JSDoc:**
```typescript
/**
	 * Sets the attached state.
	 *
	 * @param {boolean} attached - Whether the model is attached or not.
	 */
```

**Parameters:**

- **`attached`** `boolean`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setAttached( attached ) {

		this.attached = attached;

	}
```
</details>

### `OculusHandPointerModel.isAttached(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` is the model is attached.
	 *
	 * @return {boolean} Whether the model is attached or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isAttached() {

		return this.attached;

	}
```
</details>

### `OculusHandPointerModel.intersectObject(object: Object3D, recursive: boolean): Raycaster[]`

**JSDoc:**
```typescript
/**
	 * Performs an intersection test with the model's raycaster and the given object.
	 *
	 * @param {Object3D} object - The 3D object to check for intersection with the ray.
	 * @param {boolean} [recursive=true] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 * @return {Array<Raycaster~Intersection>} An array holding the intersection points.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`recursive`** `boolean`

**Returns:** `Raycaster[]`

**Calls:**

- `this.raycaster.intersectObject`

<details><summary>Code</summary>

```typescript
intersectObject( object, recursive = true ) {

		if ( this.raycaster ) {

			return this.raycaster.intersectObject( object, recursive );

		}

	}
```
</details>

### `OculusHandPointerModel.intersectObjects(objects: Object3D[], recursive: boolean): Raycaster[]`

**JSDoc:**
```typescript
/**
	 * Performs an intersection test with the model's raycaster and the given objects.
	 *
	 * @param {Array<Object3D>} objects - The 3D objects to check for intersection with the ray.
	 * @param {boolean} [recursive=true] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 * @return {Array<Raycaster~Intersection>} An array holding the intersection points.
	 */
```

**Parameters:**

- **`objects`** `Object3D[]`
- **`recursive`** `boolean`

**Returns:** `Raycaster[]`

**Calls:**

- `this.raycaster.intersectObjects`

<details><summary>Code</summary>

```typescript
intersectObjects( objects, recursive = true ) {

		if ( this.raycaster ) {

			return this.raycaster.intersectObjects( objects, recursive );

		}

	}
```
</details>

### `OculusHandPointerModel.checkIntersections(objects: Object3D[], recursive: boolean): void`

**JSDoc:**
```typescript
/**
	 * Checks for intersections between the model's raycaster and the given objects. The method
	 * updates the cursor object to the intersection point.
	 *
	 * @param {Array<Object3D>} objects - The 3D objects to check for intersection with the ray.
	 * @param {boolean} [recursive=false] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 */
```

**Parameters:**

- **`objects`** `Object3D[]`
- **`recursive`** `boolean`

**Returns:** `void`

**Calls:**

- `this.raycaster.intersectObjects`
- `this.cursorObject.position.copy`
- `direction.multiplyScalar`

<details><summary>Code</summary>

```typescript
checkIntersections( objects, recursive = false ) {

		if ( this.raycaster && ! this.attached ) {

			const intersections = this.raycaster.intersectObjects( objects, recursive );
			const direction = new Vector3( 0, 0, - 1 );
			if ( intersections.length > 0 ) {

				const intersection = intersections[ 0 ];
				const distance = intersection.distance;
				this.cursorObject.position.copy( direction.multiplyScalar( distance ) );

			} else {

				this.cursorObject.position.copy( direction.multiplyScalar( CURSOR_MAX_DISTANCE ) );

			}

		}

	}
```
</details>

### `OculusHandPointerModel.setCursor(distance: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the cursor to the given distance.
	 *
	 * @param {number} distance - The distance to set the cursor to.
	 */
```

**Parameters:**

- **`distance`** `number`

**Returns:** `void`

**Calls:**

- `this.cursorObject.position.copy`
- `direction.multiplyScalar`

<details><summary>Code</summary>

```typescript
setCursor( distance ) {

		const direction = new Vector3( 0, 0, - 1 );
		if ( this.raycaster && ! this.attached ) {

			this.cursorObject.position.copy( direction.multiplyScalar( distance ) );

		}

	}
```
</details>

### `OculusHandPointerModel.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this._onDisconnected`
- `this.hand.removeEventListener`

<details><summary>Code</summary>

```typescript
dispose() {

		this._onDisconnected();
		this.hand.removeEventListener( 'connected', this._onConnected );
		this.hand.removeEventListener( 'disconnected', this._onDisconnected );

	}
```
</details>


---

## Classes

### `OculusHandPointerModel`

<details><summary>Class Code</summary>

```ts
class OculusHandPointerModel extends Object3D {

	/**
	 * Constructs a new Oculus hand model.
	 *
	 * @param {Group} hand - The hand controller.
	 * @param {Group} controller - The WebXR controller in target ray space.
	 */
	constructor( hand, controller ) {

		super();

		/**
		 * The hand controller.
		 *
		 * @type {Group}
		 */
		this.hand = hand;

		/**
		 * The WebXR controller in target ray space.
		 *
		 * @type {Group}
		 */
		this.controller = controller;

		// Unused
		this.motionController = null;
		this.envMap = null;
		this.mesh = null;

		/**
		 * The pointer geometry.
		 *
		 * @type {?BufferGeometry}
		 * @default null
		 */
		this.pointerGeometry = null;

		/**
		 * The pointer mesh.
		 *
		 * @type {?Mesh}
		 * @default null
		 */
		this.pointerMesh = null;

		/**
		 * The pointer object that holds the pointer mesh.
		 *
		 * @type {?Object3D}
		 * @default null
		 */
		this.pointerObject = null;

		/**
		 * Whether the model is pinched or not.
		 *
		 * @type {?boolean}
		 * @default false
		 */
		this.pinched = false;

		/**
		 * Whether the model is attached or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.attached = false;

		/**
		 * The cursor object.
		 *
		 * @type {?Mesh}
		 * @default null
		 */
		this.cursorObject = null;

		/**
		 * The internal raycaster used for detecting
		 * intersections.
		 *
		 * @type {?Raycaster}
		 * @default null
		 */
		this.raycaster = null;

		this._onConnected = this._onConnected.bind( this );
		this._onDisconnected = this._onDisconnected.bind( this );
		this.hand.addEventListener( 'connected', this._onConnected );
		this.hand.addEventListener( 'disconnected', this._onDisconnected );

	}

	_onConnected( event ) {

		const xrInputSource = event.data;
		if ( xrInputSource.hand ) {

			this.visible = true;
			this.xrInputSource = xrInputSource;

			this.createPointer();

		}

	}

	_onDisconnected() {

		this.visible = false;
		this.xrInputSource = null;

		if ( this.pointerGeometry ) this.pointerGeometry.dispose();
		if ( this.pointerMesh && this.pointerMesh.material ) this.pointerMesh.material.dispose();

		this.clear();

	}

	_drawVerticesRing( vertices, baseVector, ringIndex ) {

		const segmentVector = baseVector.clone();
		for ( let i = 0; i < POINTER_SEGMENTS; i ++ ) {

			segmentVector.applyAxisAngle( ZAXIS, ( Math.PI * 2 ) / POINTER_SEGMENTS );
			const vid = ringIndex * POINTER_SEGMENTS + i;
			vertices[ 3 * vid ] = segmentVector.x;
			vertices[ 3 * vid + 1 ] = segmentVector.y;
			vertices[ 3 * vid + 2 ] = segmentVector.z;

		}

	}

	_updatePointerVertices( rearRadius ) {

		const vertices = this.pointerGeometry.attributes.position.array;
		// first ring for front face
		const frontFaceBase = new Vector3(
			POINTER_FRONT_RADIUS,
			0,
			- 1 * ( POINTER_LENGTH - rearRadius )
		);
		this._drawVerticesRing( vertices, frontFaceBase, 0 );

		// rings for rear hemisphere
		const rearBase = new Vector3(
			Math.sin( ( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 ) * rearRadius,
			Math.cos( ( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 ) * rearRadius,
			0
		);
		for ( let i = 0; i < POINTER_RINGS; i ++ ) {

			this._drawVerticesRing( vertices, rearBase, i + 1 );
			rearBase.applyAxisAngle(
				YAXIS,
				( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 / ( POINTER_RINGS * - 2 )
			);

		}

		// front and rear face center vertices
		const frontCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS );
		const rearCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS ) + 1;
		const frontCenter = new Vector3(
			0,
			0,
			- 1 * ( POINTER_LENGTH - rearRadius )
		);
		vertices[ frontCenterIndex * 3 ] = frontCenter.x;
		vertices[ frontCenterIndex * 3 + 1 ] = frontCenter.y;
		vertices[ frontCenterIndex * 3 + 2 ] = frontCenter.z;
		const rearCenter = new Vector3( 0, 0, rearRadius );
		vertices[ rearCenterIndex * 3 ] = rearCenter.x;
		vertices[ rearCenterIndex * 3 + 1 ] = rearCenter.y;
		vertices[ rearCenterIndex * 3 + 2 ] = rearCenter.z;

		this.pointerGeometry.setAttribute(
			'position',
			new Float32BufferAttribute( vertices, 3 )
		);
		// verticesNeedUpdate = true;

	}

	/**
	 * Creates a pointer mesh and adds it to this model.
	 */
	createPointer() {

		let i, j;
		const vertices = new Array(
			( ( POINTER_RINGS + 1 ) * POINTER_SEGMENTS + 2 ) * 3
		).fill( 0 );
		// const vertices = [];
		const indices = [];
		this.pointerGeometry = new BufferGeometry();

		this.pointerGeometry.setAttribute(
			'position',
			new Float32BufferAttribute( vertices, 3 )
		);

		this._updatePointerVertices( POINTER_REAR_RADIUS );

		// construct faces to connect rings
		for ( i = 0; i < POINTER_RINGS; i ++ ) {

			for ( j = 0; j < POINTER_SEGMENTS - 1; j ++ ) {

				indices.push(
					i * POINTER_SEGMENTS + j,
					i * POINTER_SEGMENTS + j + 1,
					( i + 1 ) * POINTER_SEGMENTS + j
				);
				indices.push(
					i * POINTER_SEGMENTS + j + 1,
					( i + 1 ) * POINTER_SEGMENTS + j + 1,
					( i + 1 ) * POINTER_SEGMENTS + j
				);

			}

			indices.push(
				( i + 1 ) * POINTER_SEGMENTS - 1,
				i * POINTER_SEGMENTS,
				( i + 2 ) * POINTER_SEGMENTS - 1
			);
			indices.push(
				i * POINTER_SEGMENTS,
				( i + 1 ) * POINTER_SEGMENTS,
				( i + 2 ) * POINTER_SEGMENTS - 1
			);

		}

		// construct front and rear face
		const frontCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS );
		const rearCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS ) + 1;

		for ( i = 0; i < POINTER_SEGMENTS - 1; i ++ ) {

			indices.push( frontCenterIndex, i + 1, i );
			indices.push(
				rearCenterIndex,
				i + POINTER_SEGMENTS * POINTER_RINGS,
				i + POINTER_SEGMENTS * POINTER_RINGS + 1
			);

		}

		indices.push( frontCenterIndex, 0, POINTER_SEGMENTS - 1 );
		indices.push(
			rearCenterIndex,
			POINTER_SEGMENTS * ( POINTER_RINGS + 1 ) - 1,
			POINTER_SEGMENTS * POINTER_RINGS
		);

		const material = new MeshBasicMaterial();
		material.transparent = true;
		material.opacity = POINTER_OPACITY_MIN;

		this.pointerGeometry.setIndex( indices );

		this.pointerMesh = new Mesh( this.pointerGeometry, material );

		this.pointerMesh.position.set( 0, 0, - 1 * POINTER_REAR_RADIUS );
		this.pointerObject = new Object3D();
		this.pointerObject.add( this.pointerMesh );

		this.raycaster = new Raycaster();

		// create cursor
		const cursorGeometry = new SphereGeometry( CURSOR_RADIUS, 10, 10 );
		const cursorMaterial = new MeshBasicMaterial();
		cursorMaterial.transparent = true;
		cursorMaterial.opacity = POINTER_OPACITY_MIN;

		this.cursorObject = new Mesh( cursorGeometry, cursorMaterial );
		this.pointerObject.add( this.cursorObject );

		this.add( this.pointerObject );

	}

	_updateRaycaster() {

		if ( this.raycaster ) {

			const pointerMatrix = this.pointerObject.matrixWorld;
			const tempMatrix = new Matrix4();
			tempMatrix.identity().extractRotation( pointerMatrix );
			this.raycaster.ray.origin.setFromMatrixPosition( pointerMatrix );
			this.raycaster.ray.direction.set( 0, 0, - 1 ).applyMatrix4( tempMatrix );

		}

	}

	_updatePointer() {

		this.pointerObject.visible = this.controller.visible;
		const indexTip = this.hand.joints[ 'index-finger-tip' ];
		const thumbTip = this.hand.joints[ 'thumb-tip' ];
		const distance = indexTip.position.distanceTo( thumbTip.position );
		const position = indexTip.position
			.clone()
			.add( thumbTip.position )
			.multiplyScalar( 0.5 );
		this.pointerObject.position.copy( position );
		this.pointerObject.quaternion.copy( this.controller.quaternion );

		this.pinched = distance <= PINCH_THRESHOLD;

		const pinchScale = ( distance - PINCH_MIN ) / ( PINCH_MAX - PINCH_MIN );
		const focusScale = ( distance - PINCH_MIN ) / ( PINCH_THRESHOLD - PINCH_MIN );
		if ( pinchScale > 1 ) {

			this._updatePointerVertices( POINTER_REAR_RADIUS );
			this.pointerMesh.position.set( 0, 0, - 1 * POINTER_REAR_RADIUS );
			this.pointerMesh.material.opacity = POINTER_OPACITY_MIN;

		} else if ( pinchScale > 0 ) {

			const rearRadius =
        ( POINTER_REAR_RADIUS - POINTER_REAR_RADIUS_MIN ) * pinchScale +
        POINTER_REAR_RADIUS_MIN;
			this._updatePointerVertices( rearRadius );
			if ( focusScale < 1 ) {

				this.pointerMesh.position.set(
					0,
					0,
					- 1 * rearRadius - ( 1 - focusScale ) * POINTER_ADVANCE_MAX
				);
				this.pointerMesh.material.opacity =
          POINTER_OPACITY_MIN +
          ( 1 - focusScale ) * ( POINTER_OPACITY_MAX - POINTER_OPACITY_MIN );

			} else {

				this.pointerMesh.position.set( 0, 0, - 1 * rearRadius );
				this.pointerMesh.material.opacity = POINTER_OPACITY_MIN;

			}

		} else {

			this._updatePointerVertices( POINTER_REAR_RADIUS_MIN );
			this.pointerMesh.position.set(
				0,
				0,
				- 1 * POINTER_REAR_RADIUS_MIN - POINTER_ADVANCE_MAX
			);
			this.pointerMesh.material.opacity = POINTER_OPACITY_MAX;

		}

		this.cursorObject.material.opacity = this.pointerMesh.material.opacity;

	}

	/**
	 * Overwritten with a custom implementation. Makes sure the internal pointer and raycaster are updated.
	 *
	 * @param {boolean} [force=false] - When set to `true`, a recomputation of world matrices is forced even
	 * when {@link Object3D#matrixWorldAutoUpdate} is set to `false`.
	 */
	updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );
		if ( this.pointerGeometry ) {

			this._updatePointer();
			this._updateRaycaster();

		}

	}

	/**
	 * Returns `true` is the model is pinched.
	 *
	 * @return {boolean} Whether the model is pinched or not.
	 */
	isPinched() {

		return this.pinched;

	}

	/**
	 * Sets the attached state.
	 *
	 * @param {boolean} attached - Whether the model is attached or not.
	 */
	setAttached( attached ) {

		this.attached = attached;

	}

	/**
	 * Returns `true` is the model is attached.
	 *
	 * @return {boolean} Whether the model is attached or not.
	 */
	isAttached() {

		return this.attached;

	}

	/**
	 * Performs an intersection test with the model's raycaster and the given object.
	 *
	 * @param {Object3D} object - The 3D object to check for intersection with the ray.
	 * @param {boolean} [recursive=true] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 * @return {Array<Raycaster~Intersection>} An array holding the intersection points.
	 */
	intersectObject( object, recursive = true ) {

		if ( this.raycaster ) {

			return this.raycaster.intersectObject( object, recursive );

		}

	}

	/**
	 * Performs an intersection test with the model's raycaster and the given objects.
	 *
	 * @param {Array<Object3D>} objects - The 3D objects to check for intersection with the ray.
	 * @param {boolean} [recursive=true] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 * @return {Array<Raycaster~Intersection>} An array holding the intersection points.
	 */
	intersectObjects( objects, recursive = true ) {

		if ( this.raycaster ) {

			return this.raycaster.intersectObjects( objects, recursive );

		}

	}

	/**
	 * Checks for intersections between the model's raycaster and the given objects. The method
	 * updates the cursor object to the intersection point.
	 *
	 * @param {Array<Object3D>} objects - The 3D objects to check for intersection with the ray.
	 * @param {boolean} [recursive=false] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 */
	checkIntersections( objects, recursive = false ) {

		if ( this.raycaster && ! this.attached ) {

			const intersections = this.raycaster.intersectObjects( objects, recursive );
			const direction = new Vector3( 0, 0, - 1 );
			if ( intersections.length > 0 ) {

				const intersection = intersections[ 0 ];
				const distance = intersection.distance;
				this.cursorObject.position.copy( direction.multiplyScalar( distance ) );

			} else {

				this.cursorObject.position.copy( direction.multiplyScalar( CURSOR_MAX_DISTANCE ) );

			}

		}

	}

	/**
	 * Sets the cursor to the given distance.
	 *
	 * @param {number} distance - The distance to set the cursor to.
	 */
	setCursor( distance ) {

		const direction = new Vector3( 0, 0, - 1 );
		if ( this.raycaster && ! this.attached ) {

			this.cursorObject.position.copy( direction.multiplyScalar( distance ) );

		}

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this._onDisconnected();
		this.hand.removeEventListener( 'connected', this._onConnected );
		this.hand.removeEventListener( 'disconnected', this._onDisconnected );

	}

}
```
</details>

#### Methods

##### `_onConnected(event: any): void`

<details><summary>Code</summary>

```ts
_onConnected( event ) {

		const xrInputSource = event.data;
		if ( xrInputSource.hand ) {

			this.visible = true;
			this.xrInputSource = xrInputSource;

			this.createPointer();

		}

	}
```
</details>

##### `_onDisconnected(): void`

<details><summary>Code</summary>

```ts
_onDisconnected() {

		this.visible = false;
		this.xrInputSource = null;

		if ( this.pointerGeometry ) this.pointerGeometry.dispose();
		if ( this.pointerMesh && this.pointerMesh.material ) this.pointerMesh.material.dispose();

		this.clear();

	}
```
</details>

##### `_drawVerticesRing(vertices: any, baseVector: any, ringIndex: any): void`

<details><summary>Code</summary>

```ts
_drawVerticesRing( vertices, baseVector, ringIndex ) {

		const segmentVector = baseVector.clone();
		for ( let i = 0; i < POINTER_SEGMENTS; i ++ ) {

			segmentVector.applyAxisAngle( ZAXIS, ( Math.PI * 2 ) / POINTER_SEGMENTS );
			const vid = ringIndex * POINTER_SEGMENTS + i;
			vertices[ 3 * vid ] = segmentVector.x;
			vertices[ 3 * vid + 1 ] = segmentVector.y;
			vertices[ 3 * vid + 2 ] = segmentVector.z;

		}

	}
```
</details>

##### `_updatePointerVertices(rearRadius: any): void`

<details><summary>Code</summary>

```ts
_updatePointerVertices( rearRadius ) {

		const vertices = this.pointerGeometry.attributes.position.array;
		// first ring for front face
		const frontFaceBase = new Vector3(
			POINTER_FRONT_RADIUS,
			0,
			- 1 * ( POINTER_LENGTH - rearRadius )
		);
		this._drawVerticesRing( vertices, frontFaceBase, 0 );

		// rings for rear hemisphere
		const rearBase = new Vector3(
			Math.sin( ( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 ) * rearRadius,
			Math.cos( ( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 ) * rearRadius,
			0
		);
		for ( let i = 0; i < POINTER_RINGS; i ++ ) {

			this._drawVerticesRing( vertices, rearBase, i + 1 );
			rearBase.applyAxisAngle(
				YAXIS,
				( Math.PI * POINTER_HEMISPHERE_ANGLE ) / 180 / ( POINTER_RINGS * - 2 )
			);

		}

		// front and rear face center vertices
		const frontCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS );
		const rearCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS ) + 1;
		const frontCenter = new Vector3(
			0,
			0,
			- 1 * ( POINTER_LENGTH - rearRadius )
		);
		vertices[ frontCenterIndex * 3 ] = frontCenter.x;
		vertices[ frontCenterIndex * 3 + 1 ] = frontCenter.y;
		vertices[ frontCenterIndex * 3 + 2 ] = frontCenter.z;
		const rearCenter = new Vector3( 0, 0, rearRadius );
		vertices[ rearCenterIndex * 3 ] = rearCenter.x;
		vertices[ rearCenterIndex * 3 + 1 ] = rearCenter.y;
		vertices[ rearCenterIndex * 3 + 2 ] = rearCenter.z;

		this.pointerGeometry.setAttribute(
			'position',
			new Float32BufferAttribute( vertices, 3 )
		);
		// verticesNeedUpdate = true;

	}
```
</details>

##### `createPointer(): void`

<details><summary>Code</summary>

```ts
createPointer() {

		let i, j;
		const vertices = new Array(
			( ( POINTER_RINGS + 1 ) * POINTER_SEGMENTS + 2 ) * 3
		).fill( 0 );
		// const vertices = [];
		const indices = [];
		this.pointerGeometry = new BufferGeometry();

		this.pointerGeometry.setAttribute(
			'position',
			new Float32BufferAttribute( vertices, 3 )
		);

		this._updatePointerVertices( POINTER_REAR_RADIUS );

		// construct faces to connect rings
		for ( i = 0; i < POINTER_RINGS; i ++ ) {

			for ( j = 0; j < POINTER_SEGMENTS - 1; j ++ ) {

				indices.push(
					i * POINTER_SEGMENTS + j,
					i * POINTER_SEGMENTS + j + 1,
					( i + 1 ) * POINTER_SEGMENTS + j
				);
				indices.push(
					i * POINTER_SEGMENTS + j + 1,
					( i + 1 ) * POINTER_SEGMENTS + j + 1,
					( i + 1 ) * POINTER_SEGMENTS + j
				);

			}

			indices.push(
				( i + 1 ) * POINTER_SEGMENTS - 1,
				i * POINTER_SEGMENTS,
				( i + 2 ) * POINTER_SEGMENTS - 1
			);
			indices.push(
				i * POINTER_SEGMENTS,
				( i + 1 ) * POINTER_SEGMENTS,
				( i + 2 ) * POINTER_SEGMENTS - 1
			);

		}

		// construct front and rear face
		const frontCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS );
		const rearCenterIndex = POINTER_SEGMENTS * ( 1 + POINTER_RINGS ) + 1;

		for ( i = 0; i < POINTER_SEGMENTS - 1; i ++ ) {

			indices.push( frontCenterIndex, i + 1, i );
			indices.push(
				rearCenterIndex,
				i + POINTER_SEGMENTS * POINTER_RINGS,
				i + POINTER_SEGMENTS * POINTER_RINGS + 1
			);

		}

		indices.push( frontCenterIndex, 0, POINTER_SEGMENTS - 1 );
		indices.push(
			rearCenterIndex,
			POINTER_SEGMENTS * ( POINTER_RINGS + 1 ) - 1,
			POINTER_SEGMENTS * POINTER_RINGS
		);

		const material = new MeshBasicMaterial();
		material.transparent = true;
		material.opacity = POINTER_OPACITY_MIN;

		this.pointerGeometry.setIndex( indices );

		this.pointerMesh = new Mesh( this.pointerGeometry, material );

		this.pointerMesh.position.set( 0, 0, - 1 * POINTER_REAR_RADIUS );
		this.pointerObject = new Object3D();
		this.pointerObject.add( this.pointerMesh );

		this.raycaster = new Raycaster();

		// create cursor
		const cursorGeometry = new SphereGeometry( CURSOR_RADIUS, 10, 10 );
		const cursorMaterial = new MeshBasicMaterial();
		cursorMaterial.transparent = true;
		cursorMaterial.opacity = POINTER_OPACITY_MIN;

		this.cursorObject = new Mesh( cursorGeometry, cursorMaterial );
		this.pointerObject.add( this.cursorObject );

		this.add( this.pointerObject );

	}
```
</details>

##### `_updateRaycaster(): void`

<details><summary>Code</summary>

```ts
_updateRaycaster() {

		if ( this.raycaster ) {

			const pointerMatrix = this.pointerObject.matrixWorld;
			const tempMatrix = new Matrix4();
			tempMatrix.identity().extractRotation( pointerMatrix );
			this.raycaster.ray.origin.setFromMatrixPosition( pointerMatrix );
			this.raycaster.ray.direction.set( 0, 0, - 1 ).applyMatrix4( tempMatrix );

		}

	}
```
</details>

##### `_updatePointer(): void`

<details><summary>Code</summary>

```ts
_updatePointer() {

		this.pointerObject.visible = this.controller.visible;
		const indexTip = this.hand.joints[ 'index-finger-tip' ];
		const thumbTip = this.hand.joints[ 'thumb-tip' ];
		const distance = indexTip.position.distanceTo( thumbTip.position );
		const position = indexTip.position
			.clone()
			.add( thumbTip.position )
			.multiplyScalar( 0.5 );
		this.pointerObject.position.copy( position );
		this.pointerObject.quaternion.copy( this.controller.quaternion );

		this.pinched = distance <= PINCH_THRESHOLD;

		const pinchScale = ( distance - PINCH_MIN ) / ( PINCH_MAX - PINCH_MIN );
		const focusScale = ( distance - PINCH_MIN ) / ( PINCH_THRESHOLD - PINCH_MIN );
		if ( pinchScale > 1 ) {

			this._updatePointerVertices( POINTER_REAR_RADIUS );
			this.pointerMesh.position.set( 0, 0, - 1 * POINTER_REAR_RADIUS );
			this.pointerMesh.material.opacity = POINTER_OPACITY_MIN;

		} else if ( pinchScale > 0 ) {

			const rearRadius =
        ( POINTER_REAR_RADIUS - POINTER_REAR_RADIUS_MIN ) * pinchScale +
        POINTER_REAR_RADIUS_MIN;
			this._updatePointerVertices( rearRadius );
			if ( focusScale < 1 ) {

				this.pointerMesh.position.set(
					0,
					0,
					- 1 * rearRadius - ( 1 - focusScale ) * POINTER_ADVANCE_MAX
				);
				this.pointerMesh.material.opacity =
          POINTER_OPACITY_MIN +
          ( 1 - focusScale ) * ( POINTER_OPACITY_MAX - POINTER_OPACITY_MIN );

			} else {

				this.pointerMesh.position.set( 0, 0, - 1 * rearRadius );
				this.pointerMesh.material.opacity = POINTER_OPACITY_MIN;

			}

		} else {

			this._updatePointerVertices( POINTER_REAR_RADIUS_MIN );
			this.pointerMesh.position.set(
				0,
				0,
				- 1 * POINTER_REAR_RADIUS_MIN - POINTER_ADVANCE_MAX
			);
			this.pointerMesh.material.opacity = POINTER_OPACITY_MAX;

		}

		this.cursorObject.material.opacity = this.pointerMesh.material.opacity;

	}
```
</details>

##### `updateMatrixWorld(force: boolean): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );
		if ( this.pointerGeometry ) {

			this._updatePointer();
			this._updateRaycaster();

		}

	}
```
</details>

##### `isPinched(): boolean`

<details><summary>Code</summary>

```ts
isPinched() {

		return this.pinched;

	}
```
</details>

##### `setAttached(attached: boolean): void`

<details><summary>Code</summary>

```ts
setAttached( attached ) {

		this.attached = attached;

	}
```
</details>

##### `isAttached(): boolean`

<details><summary>Code</summary>

```ts
isAttached() {

		return this.attached;

	}
```
</details>

##### `intersectObject(object: Object3D, recursive: boolean): Raycaster[]`

<details><summary>Code</summary>

```ts
intersectObject( object, recursive = true ) {

		if ( this.raycaster ) {

			return this.raycaster.intersectObject( object, recursive );

		}

	}
```
</details>

##### `intersectObjects(objects: Object3D[], recursive: boolean): Raycaster[]`

<details><summary>Code</summary>

```ts
intersectObjects( objects, recursive = true ) {

		if ( this.raycaster ) {

			return this.raycaster.intersectObjects( objects, recursive );

		}

	}
```
</details>

##### `checkIntersections(objects: Object3D[], recursive: boolean): void`

<details><summary>Code</summary>

```ts
checkIntersections( objects, recursive = false ) {

		if ( this.raycaster && ! this.attached ) {

			const intersections = this.raycaster.intersectObjects( objects, recursive );
			const direction = new Vector3( 0, 0, - 1 );
			if ( intersections.length > 0 ) {

				const intersection = intersections[ 0 ];
				const distance = intersection.distance;
				this.cursorObject.position.copy( direction.multiplyScalar( distance ) );

			} else {

				this.cursorObject.position.copy( direction.multiplyScalar( CURSOR_MAX_DISTANCE ) );

			}

		}

	}
```
</details>

##### `setCursor(distance: number): void`

<details><summary>Code</summary>

```ts
setCursor( distance ) {

		const direction = new Vector3( 0, 0, - 1 );
		if ( this.raycaster && ! this.attached ) {

			this.cursorObject.position.copy( direction.multiplyScalar( distance ) );

		}

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._onDisconnected();
		this.hand.removeEventListener( 'connected', this._onConnected );
		this.hand.removeEventListener( 'disconnected', this._onDisconnected );

	}
```
</details>


---