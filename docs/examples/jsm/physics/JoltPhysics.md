[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `JoltPhysics.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 40 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/physics/JoltPhysics.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Clock` | `three` |
| `Vector3` | `three` |
| `Quaternion` | `three` |
| `Matrix4` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `JOLT_PATH` | `"https://cdn.jsdelivr.net/npm/jolt-ph...` | let/var | `'https://cdn.jsdelivr.net/npm/jolt-physics@0.23.0/dist/jolt-physics.wasm-comp...` | ✗ |
| `frameRate` | `60` | let/var | `60` | ✗ |
| `Jolt` | `any` | let/var | `null` | ✗ |
| `parameters` | `any` | let/var | `geometry.parameters` | ✗ |
| `sx` | `number` | let/var | `parameters.width !== undefined ? parameters.width / 2 : 0.5` | ✗ |
| `sy` | `number` | let/var | `parameters.height !== undefined ? parameters.height / 2 : 0.5` | ✗ |
| `sz` | `number` | let/var | `parameters.depth !== undefined ? parameters.depth / 2 : 0.5` | ✗ |
| `radius` | `any` | let/var | `parameters.radius !== undefined ? parameters.radius : 1` | ✗ |
| `LAYER_NON_MOVING` | `0` | let/var | `0` | ✗ |
| `LAYER_MOVING` | `1` | let/var | `1` | ✗ |
| `NUM_OBJECT_LAYERS` | `2` | let/var | `2` | ✗ |
| `objectFilter` | `any` | let/var | `new Jolt.ObjectLayerPairFilterTable( NUM_OBJECT_LAYERS )` | ✗ |
| `BP_LAYER_NON_MOVING` | `any` | let/var | `new Jolt.BroadPhaseLayer( 0 )` | ✗ |
| `BP_LAYER_MOVING` | `any` | let/var | `new Jolt.BroadPhaseLayer( 1 )` | ✗ |
| `NUM_BROAD_PHASE_LAYERS` | `2` | let/var | `2` | ✗ |
| `bpInterface` | `any` | let/var | `new Jolt.BroadPhaseLayerInterfaceTable( NUM_OBJECT_LAYERS, NUM_BROAD_PHASE_LA...` | ✗ |
| `settings` | `any` | let/var | `new Jolt.JoltSettings()` | ✗ |
| `jolt` | `any` | let/var | `new Jolt.JoltInterface( settings )` | ✗ |
| `meshes` | `any[]` | let/var | `[]` | ✗ |
| `meshMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `_position` | `any` | let/var | `new Vector3()` | ✗ |
| `_quaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `_scale` | `any` | let/var | `new Vector3( 1, 1, 1 )` | ✗ |
| `_matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `physics` | `any` | let/var | `child.userData.physics` | ✗ |
| `body` | `any` | let/var | `mesh.isInstancedMesh ? createInstancedBody( mesh, mass, restitution, shape ) ...` | ✗ |
| `array` | `any` | let/var | `mesh.instanceMatrix.array` | ✗ |
| `bodies` | `any[]` | let/var | `[]` | ✗ |
| `pos` | `any` | let/var | `new Jolt.Vec3( position.x, position.y, position.z )` | ✗ |
| `rot` | `any` | let/var | `new Jolt.Quat( rotation.x, rotation.y, rotation.z, rotation.w )` | ✗ |
| `motion` | `any` | let/var | `mass > 0 ? Jolt.EMotionType_Dynamic : Jolt.EMotionType_Static` | ✗ |
| `layer` | `1 \| 0` | let/var | `mass > 0 ? LAYER_MOVING : LAYER_NON_MOVING` | ✗ |
| `creationSettings` | `any` | let/var | `new Jolt.BodyCreationSettings( shape, pos, rot, motion, layer )` | ✗ |
| `body` | `any` | let/var | `bodies[ index ]` | ✗ |
| `physics` | `any` | let/var | `mesh.userData.physics` | ✗ |
| `clock` | `any` | let/var | `new Clock()` | ✗ |
| `numSteps` | `1 \| 2` | let/var | `deltaTime > 1.0 / 55.0 ? 2 : 1` | ✗ |
| `mesh` | `any` | let/var | `meshes[ i ]` | ✗ |
| `array` | `any` | let/var | `mesh.instanceMatrix.array` | ✗ |
| `body` | `any` | let/var | `bodies[ j ]` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `JoltPhysics` | import( `${JOLT_PATH}` ), initJolt() | *none* |


---

## Functions

### `getShape(geometry: any): any`

**Parameters:**

- **`geometry`** `any`

**Returns:** `any`

**Calls:**

- `Math.min`

**Internal Comments:**
```
// TODO change type to is*
```

<details><summary>Code</summary>

```typescript
function getShape( geometry ) {

	const parameters = geometry.parameters;

	// TODO change type to is*

	if ( geometry.type === 'BoxGeometry' ) {

		const sx = parameters.width !== undefined ? parameters.width / 2 : 0.5;
		const sy = parameters.height !== undefined ? parameters.height / 2 : 0.5;
		const sz = parameters.depth !== undefined ? parameters.depth / 2 : 0.5;

		return new Jolt.BoxShape( new Jolt.Vec3( sx, sy, sz ), 0.05 * Math.min( sx, sy, sz ), null );

	} else if ( geometry.type === 'SphereGeometry' || geometry.type === 'IcosahedronGeometry' ) {

		const radius = parameters.radius !== undefined ? parameters.radius : 1;

		return new Jolt.SphereShape( radius, null );

	}

	return null;

}
```
</details>

### `setupCollisionFiltering(settings: any): void`

**Parameters:**

- **`settings`** `any`

**Returns:** `void`

**Calls:**

- `objectFilter.EnableCollision`
- `bpInterface.MapObjectToBroadPhaseLayer`

<details><summary>Code</summary>

```typescript
function setupCollisionFiltering( settings ) {

	const objectFilter = new Jolt.ObjectLayerPairFilterTable( NUM_OBJECT_LAYERS );
	objectFilter.EnableCollision( LAYER_NON_MOVING, LAYER_MOVING );
	objectFilter.EnableCollision( LAYER_MOVING, LAYER_MOVING );

	const BP_LAYER_NON_MOVING = new Jolt.BroadPhaseLayer( 0 );
	const BP_LAYER_MOVING = new Jolt.BroadPhaseLayer( 1 );
	const NUM_BROAD_PHASE_LAYERS = 2;

	const bpInterface = new Jolt.BroadPhaseLayerInterfaceTable( NUM_OBJECT_LAYERS, NUM_BROAD_PHASE_LAYERS );
	bpInterface.MapObjectToBroadPhaseLayer( LAYER_NON_MOVING, BP_LAYER_NON_MOVING );
	bpInterface.MapObjectToBroadPhaseLayer( LAYER_MOVING, BP_LAYER_MOVING );

	settings.mObjectLayerPairFilter = objectFilter;
	settings.mBroadPhaseLayerInterface = bpInterface;
	settings.mObjectVsBroadPhaseLayerFilter = new Jolt.ObjectVsBroadPhaseLayerFilterTable( settings.mBroadPhaseLayerInterface, NUM_BROAD_PHASE_LAYERS, settings.mObjectLayerPairFilter, NUM_OBJECT_LAYERS );

}
```
</details>

### `JoltPhysics(): Promise<{ addScene: (scene: any) => void; addMesh: (mesh: any, mass?: number, restitution?: number) => void; setMeshPosition: (mesh: any, position: any, index?: number) => void; setMeshVelocity: (mesh: any, velocity: any, index?: number) => void; }>`

**JSDoc:**
```typescript
/**
 * @classdesc Can be used to include Jolt as a Physics engine into
 * `three.js` apps. The API can be initialized via:
 * ```js
 * const physics = await JoltPhysics();
 * ```
 * The component automatically imports Jolt from a CDN so make sure
 * to use the component with an active Internet connection.
 *
 * @name JoltPhysics
 * @class
 * @hideconstructor
 * @three_import import { JoltPhysics } from 'three/addons/physics/JoltPhysics.js';
 */
```

**Returns:** `Promise<{ addScene: (scene: any) => void; addMesh: (mesh: any, mass?: number, restitution?: number) => void; setMeshPosition: (mesh: any, position: any, index?: number) => void; setMeshVelocity: (mesh: any, velocity: any, index?: number) => void; }>`

**Calls:**

- `complex_call_2536`
- `initJolt`
- `setupCollisionFiltering`
- `Jolt.destroy`
- `jolt.GetPhysicsSystem`
- `physicsSystem.GetBodyInterface`
- `scene.traverse`
- `addMesh`
- `getShape`
- `createInstancedBody`
- `createBody`
- `meshes.push`
- `meshMap.set`
- `_position.fromArray`
- `_quaternion.setFromRotationMatrix`
- `_matrix.fromArray`
- `bodies.push`
- `bodyInterface.CreateBody`
- `bodyInterface.AddBody`
- `body.GetID`
- `meshMap.get`
- `bodyInterface.RemoveBody`
- `bodyInterface.DestroyBody`
- `body.GetShape`
- `clock.getDelta`
- `Math.min`
- `jolt.Step`
- `body.GetPosition`
- `body.GetRotation`
- `_position.set`
- `position.GetX`
- `position.GetY`
- `position.GetZ`
- `_quaternion.set`
- `quaternion.GetX`
- `quaternion.GetY`
- `quaternion.GetZ`
- `quaternion.GetW`
- `_matrix.compose( _position, _quaternion, _scale ).toArray`
- `mesh.computeBoundingSphere`
- `mesh.position.set`
- `mesh.quaternion.set`
- `rotation.GetX`
- `rotation.GetY`
- `rotation.GetZ`
- `rotation.GetW`
- `setInterval`

**Internal Comments:**
```
// (x3)
// Don't go below 30 Hz to prevent spiral of death (x3)
// When running below 55 Hz, do 2 steps instead of 1 (x2)
// Step the physics world (x4)
// animate (x3)
/**
		 * Adds the given scene to this physics simulation. Only meshes with a
		 * `physics` object in their {@link Object3D#userData} field will be honored.
		 * The object can be used to store the mass and restitution of the mesh. E.g.:
		 * ```js
		 * box.userData.physics = { mass: 1, restitution: 0 };
		 * ```
		 *
		 * @method
		 * @name JoltPhysics#addScene
		 * @param {Object3D} scene The scene or any type of 3D object to add.
		 */ (x2)
/**
		 * Adds the given mesh to this physics simulation.
		 *
		 * @method
		 * @name JoltPhysics#addMesh
		 * @param {Mesh} mesh The mesh to add.
		 * @param {number} [mass=0] The mass in kg of the mesh.
		 * @param {number} [restitution=0] The restitution/friction of the mesh.
		 */ (x2)
/**
		 * Set the position of the given mesh which is part of the physics simulation. Calling this
		 * method will reset the current simulated velocity of the mesh.
		 *
		 * @method
		 * @name JoltPhysics#setMeshPosition
		 * @param {Mesh} mesh The mesh to update the position for.
		 * @param {Vector3} position - The new position.
		 * @param {number} [index=0] - If the mesh is instanced, the index represents the instanced ID.
		 */ (x2)
// NOOP (x2)
```

<details><summary>Code</summary>

```typescript
async function JoltPhysics() {

	if ( Jolt === null ) {

		const { default: initJolt } = await import( `${JOLT_PATH}` );
		Jolt = await initJolt();

	}

	const settings = new Jolt.JoltSettings();
	setupCollisionFiltering( settings );

	const jolt = new Jolt.JoltInterface( settings );
	Jolt.destroy( settings );

	const physicsSystem = jolt.GetPhysicsSystem();
	const bodyInterface = physicsSystem.GetBodyInterface();

	const meshes = [];
	const meshMap = new WeakMap();

	const _position = new Vector3();
	const _quaternion = new Quaternion();
	const _scale = new Vector3( 1, 1, 1 );

	const _matrix = new Matrix4();

	function addScene( scene ) {

		scene.traverse( function ( child ) {

			if ( child.isMesh ) {

				const physics = child.userData.physics;

				if ( physics ) {

					addMesh( child, physics.mass, physics.restitution );

				}

			}

		} );

	}

	function addMesh( mesh, mass = 0, restitution = 0 ) {

		const shape = getShape( mesh.geometry );

		if ( shape === null ) return;

		const body = mesh.isInstancedMesh
			? createInstancedBody( mesh, mass, restitution, shape )
			: createBody( mesh.position, mesh.quaternion, mass, restitution, shape );

		if ( mass > 0 ) {

			meshes.push( mesh );
			meshMap.set( mesh, body );

		}

	}

	function createInstancedBody( mesh, mass, restitution, shape ) {

		const array = mesh.instanceMatrix.array;

		const bodies = [];

		for ( let i = 0; i < mesh.count; i ++ ) {

			const position = _position.fromArray( array, i * 16 + 12 );
			const quaternion = _quaternion.setFromRotationMatrix( _matrix.fromArray( array, i * 16 ) ); // TODO Copilot did this
			bodies.push( createBody( position, quaternion, mass, restitution, shape ) );

		}

		return bodies;

	}

	function createBody( position, rotation, mass, restitution, shape ) {

		const pos = new Jolt.Vec3( position.x, position.y, position.z );
		const rot = new Jolt.Quat( rotation.x, rotation.y, rotation.z, rotation.w );

		const motion = mass > 0 ? Jolt.EMotionType_Dynamic : Jolt.EMotionType_Static;
		const layer = mass > 0 ? LAYER_MOVING : LAYER_NON_MOVING;

		const creationSettings = new Jolt.BodyCreationSettings( shape, pos, rot, motion, layer );
		creationSettings.mRestitution = restitution;

		const body = bodyInterface.CreateBody( creationSettings );

		bodyInterface.AddBody( body.GetID(), Jolt.EActivation_Activate );

		Jolt.destroy( creationSettings );

		return body;

	}

	function setMeshPosition( mesh, position, index = 0 ) {

		if ( mesh.isInstancedMesh ) {

			const bodies = meshMap.get( mesh );

			const body = bodies[ index ];

			bodyInterface.RemoveBody( body.GetID() );
			bodyInterface.DestroyBody( body.GetID() );

			const physics = mesh.userData.physics;

			const shape = body.GetShape();
			const body2 = createBody( position, { x: 0, y: 0, z: 0, w: 1 }, physics.mass, physics.restitution, shape );

			bodies[ index ] = body2;

		} else {

			// TODO: Implement this

		}

	}

	function setMeshVelocity( mesh, velocity, index = 0 ) {

		/*
		let body = meshMap.get( mesh );

		if ( mesh.isInstancedMesh ) {

			body = body[ index ];

		}

		body.setLinvel( velocity );
		*/

	}

	//

	const clock = new Clock();

	function step() {

		let deltaTime = clock.getDelta();

		// Don't go below 30 Hz to prevent spiral of death
		deltaTime = Math.min( deltaTime, 1.0 / 30.0 );

		// When running below 55 Hz, do 2 steps instead of 1
		const numSteps = deltaTime > 1.0 / 55.0 ? 2 : 1;

		// Step the physics world
		jolt.Step( deltaTime, numSteps );

		//

		for ( let i = 0, l = meshes.length; i < l; i ++ ) {

			const mesh = meshes[ i ];

			if ( mesh.isInstancedMesh ) {

				const array = mesh.instanceMatrix.array;
				const bodies = meshMap.get( mesh );

				for ( let j = 0; j < bodies.length; j ++ ) {

					const body = bodies[ j ];

					const position = body.GetPosition();
					const quaternion = body.GetRotation();

					_position.set( position.GetX(), position.GetY(), position.GetZ() );
					_quaternion.set( quaternion.GetX(), quaternion.GetY(), quaternion.GetZ(), quaternion.GetW() );

					_matrix.compose( _position, _quaternion, _scale ).toArray( array, j * 16 );

				}

				mesh.instanceMatrix.needsUpdate = true;
				mesh.computeBoundingSphere();

			} else {

				const body = meshMap.get( mesh );

				const position = body.GetPosition();
				const rotation = body.GetRotation();

				mesh.position.set( position.GetX(), position.GetY(), position.GetZ() );
				mesh.quaternion.set( rotation.GetX(), rotation.GetY(), rotation.GetZ(), rotation.GetW() );

			}

		}

	}

	// animate

	setInterval( step, 1000 / frameRate );

	return {
		/**
		 * Adds the given scene to this physics simulation. Only meshes with a
		 * `physics` object in their {@link Object3D#userData} field will be honored.
		 * The object can be used to store the mass and restitution of the mesh. E.g.:
		 * ```js
		 * box.userData.physics = { mass: 1, restitution: 0 };
		 * ```
		 *
		 * @method
		 * @name JoltPhysics#addScene
		 * @param {Object3D} scene The scene or any type of 3D object to add.
		 */
		addScene: addScene,

		/**
		 * Adds the given mesh to this physics simulation.
		 *
		 * @method
		 * @name JoltPhysics#addMesh
		 * @param {Mesh} mesh The mesh to add.
		 * @param {number} [mass=0] The mass in kg of the mesh.
		 * @param {number} [restitution=0] The restitution/friction of the mesh.
		 */
		addMesh: addMesh,

		/**
		 * Set the position of the given mesh which is part of the physics simulation. Calling this
		 * method will reset the current simulated velocity of the mesh.
		 *
		 * @method
		 * @name JoltPhysics#setMeshPosition
		 * @param {Mesh} mesh The mesh to update the position for.
		 * @param {Vector3} position - The new position.
		 * @param {number} [index=0] - If the mesh is instanced, the index represents the instanced ID.
		 */
		setMeshPosition: setMeshPosition,

		// NOOP
		setMeshVelocity: setMeshVelocity
	};

}
```
</details>

### `addScene(scene: any): void`

**Parameters:**

- **`scene`** `any`

**Returns:** `void`

**Calls:**

- `scene.traverse`
- `addMesh`

<details><summary>Code</summary>

```typescript
function addScene( scene ) {

		scene.traverse( function ( child ) {

			if ( child.isMesh ) {

				const physics = child.userData.physics;

				if ( physics ) {

					addMesh( child, physics.mass, physics.restitution );

				}

			}

		} );

	}
```
</details>

### `addMesh(mesh: any, mass: number, restitution: number): void`

**Parameters:**

- **`mesh`** `any`
- **`mass`** `number`
- **`restitution`** `number`

**Returns:** `void`

**Calls:**

- `getShape`
- `createInstancedBody`
- `createBody`
- `meshes.push`
- `meshMap.set`

<details><summary>Code</summary>

```typescript
function addMesh( mesh, mass = 0, restitution = 0 ) {

		const shape = getShape( mesh.geometry );

		if ( shape === null ) return;

		const body = mesh.isInstancedMesh
			? createInstancedBody( mesh, mass, restitution, shape )
			: createBody( mesh.position, mesh.quaternion, mass, restitution, shape );

		if ( mass > 0 ) {

			meshes.push( mesh );
			meshMap.set( mesh, body );

		}

	}
```
</details>

### `createInstancedBody(mesh: any, mass: any, restitution: any, shape: any): any[]`

**Parameters:**

- **`mesh`** `any`
- **`mass`** `any`
- **`restitution`** `any`
- **`shape`** `any`

**Returns:** `any[]`

**Calls:**

- `_position.fromArray`
- `_quaternion.setFromRotationMatrix`
- `_matrix.fromArray`
- `bodies.push`
- `createBody`

<details><summary>Code</summary>

```typescript
function createInstancedBody( mesh, mass, restitution, shape ) {

		const array = mesh.instanceMatrix.array;

		const bodies = [];

		for ( let i = 0; i < mesh.count; i ++ ) {

			const position = _position.fromArray( array, i * 16 + 12 );
			const quaternion = _quaternion.setFromRotationMatrix( _matrix.fromArray( array, i * 16 ) ); // TODO Copilot did this
			bodies.push( createBody( position, quaternion, mass, restitution, shape ) );

		}

		return bodies;

	}
```
</details>

### `createBody(position: any, rotation: any, mass: any, restitution: any, shape: any): any`

**Parameters:**

- **`position`** `any`
- **`rotation`** `any`
- **`mass`** `any`
- **`restitution`** `any`
- **`shape`** `any`

**Returns:** `any`

**Calls:**

- `bodyInterface.CreateBody`
- `bodyInterface.AddBody`
- `body.GetID`
- `Jolt.destroy`

<details><summary>Code</summary>

```typescript
function createBody( position, rotation, mass, restitution, shape ) {

		const pos = new Jolt.Vec3( position.x, position.y, position.z );
		const rot = new Jolt.Quat( rotation.x, rotation.y, rotation.z, rotation.w );

		const motion = mass > 0 ? Jolt.EMotionType_Dynamic : Jolt.EMotionType_Static;
		const layer = mass > 0 ? LAYER_MOVING : LAYER_NON_MOVING;

		const creationSettings = new Jolt.BodyCreationSettings( shape, pos, rot, motion, layer );
		creationSettings.mRestitution = restitution;

		const body = bodyInterface.CreateBody( creationSettings );

		bodyInterface.AddBody( body.GetID(), Jolt.EActivation_Activate );

		Jolt.destroy( creationSettings );

		return body;

	}
```
</details>

### `setMeshPosition(mesh: any, position: any, index: number): void`

**Parameters:**

- **`mesh`** `any`
- **`position`** `any`
- **`index`** `number`

**Returns:** `void`

**Calls:**

- `meshMap.get`
- `bodyInterface.RemoveBody`
- `body.GetID`
- `bodyInterface.DestroyBody`
- `body.GetShape`
- `createBody`

<details><summary>Code</summary>

```typescript
function setMeshPosition( mesh, position, index = 0 ) {

		if ( mesh.isInstancedMesh ) {

			const bodies = meshMap.get( mesh );

			const body = bodies[ index ];

			bodyInterface.RemoveBody( body.GetID() );
			bodyInterface.DestroyBody( body.GetID() );

			const physics = mesh.userData.physics;

			const shape = body.GetShape();
			const body2 = createBody( position, { x: 0, y: 0, z: 0, w: 1 }, physics.mass, physics.restitution, shape );

			bodies[ index ] = body2;

		} else {

			// TODO: Implement this

		}

	}
```
</details>

### `setMeshVelocity(mesh: any, velocity: any, index: number): void`

**Parameters:**

- **`mesh`** `any`
- **`velocity`** `any`
- **`index`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setMeshVelocity( mesh, velocity, index = 0 ) {

		/*
		let body = meshMap.get( mesh );

		if ( mesh.isInstancedMesh ) {

			body = body[ index ];

		}

		body.setLinvel( velocity );
		*/

	}
```
</details>

### `step(): void`

**Returns:** `void`

**Calls:**

- `clock.getDelta`
- `Math.min`
- `jolt.Step`
- `meshMap.get`
- `body.GetPosition`
- `body.GetRotation`
- `_position.set`
- `position.GetX`
- `position.GetY`
- `position.GetZ`
- `_quaternion.set`
- `quaternion.GetX`
- `quaternion.GetY`
- `quaternion.GetZ`
- `quaternion.GetW`
- `_matrix.compose( _position, _quaternion, _scale ).toArray`
- `mesh.computeBoundingSphere`
- `mesh.position.set`
- `mesh.quaternion.set`
- `rotation.GetX`
- `rotation.GetY`
- `rotation.GetZ`
- `rotation.GetW`

**Internal Comments:**
```
// Don't go below 30 Hz to prevent spiral of death (x3)
// When running below 55 Hz, do 2 steps instead of 1 (x2)
// Step the physics world (x4)
//
```

<details><summary>Code</summary>

```typescript
function step() {

		let deltaTime = clock.getDelta();

		// Don't go below 30 Hz to prevent spiral of death
		deltaTime = Math.min( deltaTime, 1.0 / 30.0 );

		// When running below 55 Hz, do 2 steps instead of 1
		const numSteps = deltaTime > 1.0 / 55.0 ? 2 : 1;

		// Step the physics world
		jolt.Step( deltaTime, numSteps );

		//

		for ( let i = 0, l = meshes.length; i < l; i ++ ) {

			const mesh = meshes[ i ];

			if ( mesh.isInstancedMesh ) {

				const array = mesh.instanceMatrix.array;
				const bodies = meshMap.get( mesh );

				for ( let j = 0; j < bodies.length; j ++ ) {

					const body = bodies[ j ];

					const position = body.GetPosition();
					const quaternion = body.GetRotation();

					_position.set( position.GetX(), position.GetY(), position.GetZ() );
					_quaternion.set( quaternion.GetX(), quaternion.GetY(), quaternion.GetZ(), quaternion.GetW() );

					_matrix.compose( _position, _quaternion, _scale ).toArray( array, j * 16 );

				}

				mesh.instanceMatrix.needsUpdate = true;
				mesh.computeBoundingSphere();

			} else {

				const body = meshMap.get( mesh );

				const position = body.GetPosition();
				const rotation = body.GetRotation();

				mesh.position.set( position.GetX(), position.GetY(), position.GetZ() );
				mesh.quaternion.set( rotation.GetX(), rotation.GetY(), rotation.GetZ(), rotation.GetW() );

			}

		}

	}
```
</details>


---