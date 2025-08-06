[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AmmoPhysics.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 📊 Variables & Constants | 51 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/physics/AmmoPhysics.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `AmmoLib` | `any` | let/var | `await Ammo()` | ✗ |
| `frameRate` | `60` | let/var | `60` | ✗ |
| `collisionConfiguration` | `any` | let/var | `new AmmoLib.btDefaultCollisionConfiguration()` | ✗ |
| `dispatcher` | `any` | let/var | `new AmmoLib.btCollisionDispatcher( collisionConfiguration )` | ✗ |
| `broadphase` | `any` | let/var | `new AmmoLib.btDbvtBroadphase()` | ✗ |
| `solver` | `any` | let/var | `new AmmoLib.btSequentialImpulseConstraintSolver()` | ✗ |
| `world` | `any` | let/var | `new AmmoLib.btDiscreteDynamicsWorld( dispatcher, broadphase, solver, collisio...` | ✗ |
| `worldTransform` | `any` | let/var | `new AmmoLib.btTransform()` | ✗ |
| `parameters` | `any` | let/var | `geometry.parameters` | ✗ |
| `sx` | `number` | let/var | `parameters.width !== undefined ? parameters.width / 2 : 0.5` | ✗ |
| `sy` | `number` | let/var | `parameters.height !== undefined ? parameters.height / 2 : 0.5` | ✗ |
| `sz` | `number` | let/var | `parameters.depth !== undefined ? parameters.depth / 2 : 0.5` | ✗ |
| `shape` | `any` | let/var | `new AmmoLib.btBoxShape( new AmmoLib.btVector3( sx, sy, sz ) )` | ✗ |
| `radius` | `any` | let/var | `parameters.radius !== undefined ? parameters.radius : 1` | ✗ |
| `shape` | `any` | let/var | `new AmmoLib.btSphereShape( radius )` | ✗ |
| `meshes` | `any[]` | let/var | `[]` | ✗ |
| `meshMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `physics` | `any` | let/var | `child.userData.physics` | ✗ |
| `position` | `any` | let/var | `mesh.position` | ✗ |
| `quaternion` | `any` | let/var | `mesh.quaternion` | ✗ |
| `transform` | `any` | let/var | `new AmmoLib.btTransform()` | ✗ |
| `motionState` | `any` | let/var | `new AmmoLib.btDefaultMotionState( transform )` | ✗ |
| `localInertia` | `any` | let/var | `new AmmoLib.btVector3( 0, 0, 0 )` | ✗ |
| `rbInfo` | `any` | let/var | `new AmmoLib.btRigidBodyConstructionInfo( mass, motionState, shape, localInert...` | ✗ |
| `body` | `any` | let/var | `new AmmoLib.btRigidBody( rbInfo )` | ✗ |
| `array` | `any` | let/var | `mesh.instanceMatrix.array` | ✗ |
| `bodies` | `any[]` | let/var | `[]` | ✗ |
| `index` | `number` | let/var | `i * 16` | ✗ |
| `transform` | `any` | let/var | `new AmmoLib.btTransform()` | ✗ |
| `motionState` | `any` | let/var | `new AmmoLib.btDefaultMotionState( transform )` | ✗ |
| `localInertia` | `any` | let/var | `new AmmoLib.btVector3( 0, 0, 0 )` | ✗ |
| `rbInfo` | `any` | let/var | `new AmmoLib.btRigidBodyConstructionInfo( mass, motionState, shape, localInert...` | ✗ |
| `body` | `any` | let/var | `new AmmoLib.btRigidBody( rbInfo )` | ✗ |
| `body` | `any` | let/var | `bodies[ index ]` | ✗ |
| `lastTime` | `number` | let/var | `0` | ✗ |
| `delta` | `number` | let/var | `( time - lastTime ) / 1000` | ✗ |
| `mesh` | `any` | let/var | `meshes[ i ]` | ✗ |
| `array` | `any` | let/var | `mesh.instanceMatrix.array` | ✗ |
| `body` | `any` | let/var | `bodies[ j ]` | ✗ |
| `x2` | `any` | let/var | `x + x` | ✗ |
| `y2` | `any` | let/var | `y + y` | ✗ |
| `z2` | `any` | let/var | `z + z` | ✗ |
| `xx` | `number` | let/var | `x * x2` | ✗ |
| `xy` | `number` | let/var | `x * y2` | ✗ |
| `xz` | `number` | let/var | `x * z2` | ✗ |
| `yy` | `number` | let/var | `y * y2` | ✗ |
| `yz` | `number` | let/var | `y * z2` | ✗ |
| `zz` | `number` | let/var | `z * z2` | ✗ |
| `wx` | `number` | let/var | `w * x2` | ✗ |
| `wy` | `number` | let/var | `w * y2` | ✗ |
| `wz` | `number` | let/var | `w * z2` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `AmmoPhysics` | Ammo() | *none* |


---

## Functions

### `AmmoPhysics(): Promise<{ addScene: (scene: any) => void; addMesh: (mesh: any, mass?: number) => void; setMeshPosition: (mesh: any, position: any, index?: number) => void; }>`

**JSDoc:**
```typescript
/**
 * @classdesc Can be used to include Ammo.js as a Physics engine into
 * `three.js` apps. Make sure to include `ammo.wasm.js` first:
 * ```
 * <script src="jsm/libs/ammo.wasm.js"></script>
 * ```
 * It is then possible to initialize the API via:
 * ```js
 * const physics = await AmmoPhysics();
 * ```
 *
 * @name AmmoPhysics
 * @class
 * @hideconstructor
 * @three_import import { AmmoPhysics } from 'three/addons/physics/AmmoPhysics.js';
 */
```

**Returns:** `Promise<{ addScene: (scene: any) => void; addMesh: (mesh: any, mass?: number) => void; setMeshPosition: (mesh: any, position: any, index?: number) => void; }>`

**Calls:**

- `console.error`
- `Ammo`
- `world.setGravity`
- `shape.setMargin`
- `scene.traverse`
- `addMesh`
- `getShape`
- `handleInstancedMesh`
- `handleMesh`
- `transform.setIdentity`
- `transform.setOrigin`
- `transform.setRotation`
- `shape.calculateLocalInertia`
- `world.addRigidBody`
- `meshes.push`
- `meshMap.set`
- `transform.setFromOpenGLMatrix`
- `array.slice`
- `bodies.push`
- `meshMap.get`
- `body.setAngularVelocity`
- `body.setLinearVelocity`
- `worldTransform.setIdentity`
- `worldTransform.setOrigin`
- `body.setWorldTransform`
- `performance.now`
- `world.stepSimulation`
- `body.getMotionState`
- `motionState.getWorldTransform`
- `worldTransform.getOrigin`
- `worldTransform.getRotation`
- `compose`
- `mesh.computeBoundingSphere`
- `mesh.position.set`
- `position.x`
- `position.y`
- `position.z`
- `mesh.quaternion.set`
- `quaternion.x`
- `quaternion.y`
- `quaternion.z`
- `quaternion.w`
- `setInterval`

**Internal Comments:**
```
// (x5)
// TODO change type to is*
// body.setFriction( 4 ); (x4)
// animate (x3)
/**
		 * Adds the given scene to this physics simulation. Only meshes with a
		 * `physics` object in their {@link Object3D#userData} field will be honored.
		 * The object can be used to store the mass of the mesh. E.g.:
		 * ```js
		 * box.userData.physics = { mass: 1 };
		 * ```
		 *
		 * @method
		 * @name AmmoPhysics#addScene
		 * @param {Object3D} scene The scene or any type of 3D object to add.
		 */ (x2)
/**
		 * Adds the given mesh to this physics simulation.
		 *
		 * @method
		 * @name AmmoPhysics#addMesh
		 * @param {Mesh} mesh The mesh to add.
		 * @param {number} [mass=0] The mass in kg of the mesh.
		 */ (x2)
/**
		 * Set the position of the given mesh which is part of the physics simulation. Calling this
		 * method will reset the current simulated velocity of the mesh.
		 *
		 * @method
		 * @name AmmoPhysics#setMeshPosition
		 * @param {Mesh} mesh The mesh to update the position for.
		 * @param {Vector3} position - The new position.
		 * @param {number} [index=0] - If the mesh is instanced, the index represents the instanced ID.
		 */ (x2)
```

<details><summary>Code</summary>

```typescript
async function AmmoPhysics() {

	if ( 'Ammo' in window === false ) {

		console.error( 'AmmoPhysics: Couldn\'t find Ammo.js' );
		return;

	}

	const AmmoLib = await Ammo(); // eslint-disable-line no-undef

	const frameRate = 60;

	const collisionConfiguration = new AmmoLib.btDefaultCollisionConfiguration();
	const dispatcher = new AmmoLib.btCollisionDispatcher( collisionConfiguration );
	const broadphase = new AmmoLib.btDbvtBroadphase();
	const solver = new AmmoLib.btSequentialImpulseConstraintSolver();
	const world = new AmmoLib.btDiscreteDynamicsWorld( dispatcher, broadphase, solver, collisionConfiguration );
	world.setGravity( new AmmoLib.btVector3( 0, - 9.8, 0 ) );

	const worldTransform = new AmmoLib.btTransform();

	//

	function getShape( geometry ) {

		const parameters = geometry.parameters;

		// TODO change type to is*

		if ( geometry.type === 'BoxGeometry' ) {

			const sx = parameters.width !== undefined ? parameters.width / 2 : 0.5;
			const sy = parameters.height !== undefined ? parameters.height / 2 : 0.5;
			const sz = parameters.depth !== undefined ? parameters.depth / 2 : 0.5;

			const shape = new AmmoLib.btBoxShape( new AmmoLib.btVector3( sx, sy, sz ) );
			shape.setMargin( 0.05 );

			return shape;

		} else if ( geometry.type === 'SphereGeometry' || geometry.type === 'IcosahedronGeometry' ) {

			const radius = parameters.radius !== undefined ? parameters.radius : 1;

			const shape = new AmmoLib.btSphereShape( radius );
			shape.setMargin( 0.05 );

			return shape;

		}

		return null;

	}

	const meshes = [];
	const meshMap = new WeakMap();

	function addScene( scene ) {

		scene.traverse( function ( child ) {

			if ( child.isMesh ) {

				const physics = child.userData.physics;

				if ( physics ) {

					addMesh( child, physics.mass );

				}

			}

		} );

	}

	function addMesh( mesh, mass = 0 ) {

		const shape = getShape( mesh.geometry );

		if ( shape !== null ) {

			if ( mesh.isInstancedMesh ) {

				handleInstancedMesh( mesh, mass, shape );

			} else if ( mesh.isMesh ) {

				handleMesh( mesh, mass, shape );

			}

		}

	}

	function handleMesh( mesh, mass, shape ) {

		const position = mesh.position;
		const quaternion = mesh.quaternion;

		const transform = new AmmoLib.btTransform();
		transform.setIdentity();
		transform.setOrigin( new AmmoLib.btVector3( position.x, position.y, position.z ) );
		transform.setRotation( new AmmoLib.btQuaternion( quaternion.x, quaternion.y, quaternion.z, quaternion.w ) );

		const motionState = new AmmoLib.btDefaultMotionState( transform );

		const localInertia = new AmmoLib.btVector3( 0, 0, 0 );
		shape.calculateLocalInertia( mass, localInertia );

		const rbInfo = new AmmoLib.btRigidBodyConstructionInfo( mass, motionState, shape, localInertia );

		const body = new AmmoLib.btRigidBody( rbInfo );
		// body.setFriction( 4 );
		world.addRigidBody( body );

		if ( mass > 0 ) {

			meshes.push( mesh );
			meshMap.set( mesh, body );

		}


	}

	function handleInstancedMesh( mesh, mass, shape ) {

		const array = mesh.instanceMatrix.array;

		const bodies = [];

		for ( let i = 0; i < mesh.count; i ++ ) {

			const index = i * 16;

			const transform = new AmmoLib.btTransform();
			transform.setFromOpenGLMatrix( array.slice( index, index + 16 ) );

			const motionState = new AmmoLib.btDefaultMotionState( transform );

			const localInertia = new AmmoLib.btVector3( 0, 0, 0 );
			shape.calculateLocalInertia( mass, localInertia );

			const rbInfo = new AmmoLib.btRigidBodyConstructionInfo( mass, motionState, shape, localInertia );

			const body = new AmmoLib.btRigidBody( rbInfo );
			world.addRigidBody( body );

			bodies.push( body );

		}

		if ( mass > 0 ) {

			meshes.push( mesh );

			meshMap.set( mesh, bodies );

		}

	}

	//

	function setMeshPosition( mesh, position, index = 0 ) {

		if ( mesh.isInstancedMesh ) {

			const bodies = meshMap.get( mesh );
			const body = bodies[ index ];

			body.setAngularVelocity( new AmmoLib.btVector3( 0, 0, 0 ) );
			body.setLinearVelocity( new AmmoLib.btVector3( 0, 0, 0 ) );

			worldTransform.setIdentity();
			worldTransform.setOrigin( new AmmoLib.btVector3( position.x, position.y, position.z ) );
			body.setWorldTransform( worldTransform );

		} else if ( mesh.isMesh ) {

			const body = meshMap.get( mesh );

			body.setAngularVelocity( new AmmoLib.btVector3( 0, 0, 0 ) );
			body.setLinearVelocity( new AmmoLib.btVector3( 0, 0, 0 ) );

			worldTransform.setIdentity();
			worldTransform.setOrigin( new AmmoLib.btVector3( position.x, position.y, position.z ) );
			body.setWorldTransform( worldTransform );

		}

	}

	//

	let lastTime = 0;

	function step() {

		const time = performance.now();

		if ( lastTime > 0 ) {

			const delta = ( time - lastTime ) / 1000;

			world.stepSimulation( delta, 10 );

			//

			for ( let i = 0, l = meshes.length; i < l; i ++ ) {

				const mesh = meshes[ i ];

				if ( mesh.isInstancedMesh ) {

					const array = mesh.instanceMatrix.array;
					const bodies = meshMap.get( mesh );

					for ( let j = 0; j < bodies.length; j ++ ) {

						const body = bodies[ j ];

						const motionState = body.getMotionState();
						motionState.getWorldTransform( worldTransform );

						const position = worldTransform.getOrigin();
						const quaternion = worldTransform.getRotation();

						compose( position, quaternion, array, j * 16 );

					}

					mesh.instanceMatrix.needsUpdate = true;
					mesh.computeBoundingSphere();

				} else if ( mesh.isMesh ) {

					const body = meshMap.get( mesh );

					const motionState = body.getMotionState();
					motionState.getWorldTransform( worldTransform );

					const position = worldTransform.getOrigin();
					const quaternion = worldTransform.getRotation();
					mesh.position.set( position.x(), position.y(), position.z() );
					mesh.quaternion.set( quaternion.x(), quaternion.y(), quaternion.z(), quaternion.w() );

				}

			}

		}

		lastTime = time;

	}

	// animate

	setInterval( step, 1000 / frameRate );

	return {
		/**
		 * Adds the given scene to this physics simulation. Only meshes with a
		 * `physics` object in their {@link Object3D#userData} field will be honored.
		 * The object can be used to store the mass of the mesh. E.g.:
		 * ```js
		 * box.userData.physics = { mass: 1 };
		 * ```
		 *
		 * @method
		 * @name AmmoPhysics#addScene
		 * @param {Object3D} scene The scene or any type of 3D object to add.
		 */
		addScene: addScene,

		/**
		 * Adds the given mesh to this physics simulation.
		 *
		 * @method
		 * @name AmmoPhysics#addMesh
		 * @param {Mesh} mesh The mesh to add.
		 * @param {number} [mass=0] The mass in kg of the mesh.
		 */
		addMesh: addMesh,

		/**
		 * Set the position of the given mesh which is part of the physics simulation. Calling this
		 * method will reset the current simulated velocity of the mesh.
		 *
		 * @method
		 * @name AmmoPhysics#setMeshPosition
		 * @param {Mesh} mesh The mesh to update the position for.
		 * @param {Vector3} position - The new position.
		 * @param {number} [index=0] - If the mesh is instanced, the index represents the instanced ID.
		 */
		setMeshPosition: setMeshPosition
		// addCompoundMesh
	};

}
```
</details>

### `getShape(geometry: any): any`

**Parameters:**

- **`geometry`** `any`

**Returns:** `any`

**Calls:**

- `shape.setMargin`

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

			const shape = new AmmoLib.btBoxShape( new AmmoLib.btVector3( sx, sy, sz ) );
			shape.setMargin( 0.05 );

			return shape;

		} else if ( geometry.type === 'SphereGeometry' || geometry.type === 'IcosahedronGeometry' ) {

			const radius = parameters.radius !== undefined ? parameters.radius : 1;

			const shape = new AmmoLib.btSphereShape( radius );
			shape.setMargin( 0.05 );

			return shape;

		}

		return null;

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

					addMesh( child, physics.mass );

				}

			}

		} );

	}
```
</details>

### `addMesh(mesh: any, mass: number): void`

**Parameters:**

- **`mesh`** `any`
- **`mass`** `number`

**Returns:** `void`

**Calls:**

- `getShape`
- `handleInstancedMesh`
- `handleMesh`

<details><summary>Code</summary>

```typescript
function addMesh( mesh, mass = 0 ) {

		const shape = getShape( mesh.geometry );

		if ( shape !== null ) {

			if ( mesh.isInstancedMesh ) {

				handleInstancedMesh( mesh, mass, shape );

			} else if ( mesh.isMesh ) {

				handleMesh( mesh, mass, shape );

			}

		}

	}
```
</details>

### `handleMesh(mesh: any, mass: any, shape: any): void`

**Parameters:**

- **`mesh`** `any`
- **`mass`** `any`
- **`shape`** `any`

**Returns:** `void`

**Calls:**

- `transform.setIdentity`
- `transform.setOrigin`
- `transform.setRotation`
- `shape.calculateLocalInertia`
- `world.addRigidBody`
- `meshes.push`
- `meshMap.set`

**Internal Comments:**
```
// body.setFriction( 4 ); (x4)
```

<details><summary>Code</summary>

```typescript
function handleMesh( mesh, mass, shape ) {

		const position = mesh.position;
		const quaternion = mesh.quaternion;

		const transform = new AmmoLib.btTransform();
		transform.setIdentity();
		transform.setOrigin( new AmmoLib.btVector3( position.x, position.y, position.z ) );
		transform.setRotation( new AmmoLib.btQuaternion( quaternion.x, quaternion.y, quaternion.z, quaternion.w ) );

		const motionState = new AmmoLib.btDefaultMotionState( transform );

		const localInertia = new AmmoLib.btVector3( 0, 0, 0 );
		shape.calculateLocalInertia( mass, localInertia );

		const rbInfo = new AmmoLib.btRigidBodyConstructionInfo( mass, motionState, shape, localInertia );

		const body = new AmmoLib.btRigidBody( rbInfo );
		// body.setFriction( 4 );
		world.addRigidBody( body );

		if ( mass > 0 ) {

			meshes.push( mesh );
			meshMap.set( mesh, body );

		}


	}
```
</details>

### `handleInstancedMesh(mesh: any, mass: any, shape: any): void`

**Parameters:**

- **`mesh`** `any`
- **`mass`** `any`
- **`shape`** `any`

**Returns:** `void`

**Calls:**

- `transform.setFromOpenGLMatrix`
- `array.slice`
- `shape.calculateLocalInertia`
- `world.addRigidBody`
- `bodies.push`
- `meshes.push`
- `meshMap.set`

<details><summary>Code</summary>

```typescript
function handleInstancedMesh( mesh, mass, shape ) {

		const array = mesh.instanceMatrix.array;

		const bodies = [];

		for ( let i = 0; i < mesh.count; i ++ ) {

			const index = i * 16;

			const transform = new AmmoLib.btTransform();
			transform.setFromOpenGLMatrix( array.slice( index, index + 16 ) );

			const motionState = new AmmoLib.btDefaultMotionState( transform );

			const localInertia = new AmmoLib.btVector3( 0, 0, 0 );
			shape.calculateLocalInertia( mass, localInertia );

			const rbInfo = new AmmoLib.btRigidBodyConstructionInfo( mass, motionState, shape, localInertia );

			const body = new AmmoLib.btRigidBody( rbInfo );
			world.addRigidBody( body );

			bodies.push( body );

		}

		if ( mass > 0 ) {

			meshes.push( mesh );

			meshMap.set( mesh, bodies );

		}

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
- `body.setAngularVelocity`
- `body.setLinearVelocity`
- `worldTransform.setIdentity`
- `worldTransform.setOrigin`
- `body.setWorldTransform`

<details><summary>Code</summary>

```typescript
function setMeshPosition( mesh, position, index = 0 ) {

		if ( mesh.isInstancedMesh ) {

			const bodies = meshMap.get( mesh );
			const body = bodies[ index ];

			body.setAngularVelocity( new AmmoLib.btVector3( 0, 0, 0 ) );
			body.setLinearVelocity( new AmmoLib.btVector3( 0, 0, 0 ) );

			worldTransform.setIdentity();
			worldTransform.setOrigin( new AmmoLib.btVector3( position.x, position.y, position.z ) );
			body.setWorldTransform( worldTransform );

		} else if ( mesh.isMesh ) {

			const body = meshMap.get( mesh );

			body.setAngularVelocity( new AmmoLib.btVector3( 0, 0, 0 ) );
			body.setLinearVelocity( new AmmoLib.btVector3( 0, 0, 0 ) );

			worldTransform.setIdentity();
			worldTransform.setOrigin( new AmmoLib.btVector3( position.x, position.y, position.z ) );
			body.setWorldTransform( worldTransform );

		}

	}
```
</details>

### `step(): void`

**Returns:** `void`

**Calls:**

- `performance.now`
- `world.stepSimulation`
- `meshMap.get`
- `body.getMotionState`
- `motionState.getWorldTransform`
- `worldTransform.getOrigin`
- `worldTransform.getRotation`
- `compose`
- `mesh.computeBoundingSphere`
- `mesh.position.set`
- `position.x`
- `position.y`
- `position.z`
- `mesh.quaternion.set`
- `quaternion.x`
- `quaternion.y`
- `quaternion.z`
- `quaternion.w`

**Internal Comments:**
```
//
```

<details><summary>Code</summary>

```typescript
function step() {

		const time = performance.now();

		if ( lastTime > 0 ) {

			const delta = ( time - lastTime ) / 1000;

			world.stepSimulation( delta, 10 );

			//

			for ( let i = 0, l = meshes.length; i < l; i ++ ) {

				const mesh = meshes[ i ];

				if ( mesh.isInstancedMesh ) {

					const array = mesh.instanceMatrix.array;
					const bodies = meshMap.get( mesh );

					for ( let j = 0; j < bodies.length; j ++ ) {

						const body = bodies[ j ];

						const motionState = body.getMotionState();
						motionState.getWorldTransform( worldTransform );

						const position = worldTransform.getOrigin();
						const quaternion = worldTransform.getRotation();

						compose( position, quaternion, array, j * 16 );

					}

					mesh.instanceMatrix.needsUpdate = true;
					mesh.computeBoundingSphere();

				} else if ( mesh.isMesh ) {

					const body = meshMap.get( mesh );

					const motionState = body.getMotionState();
					motionState.getWorldTransform( worldTransform );

					const position = worldTransform.getOrigin();
					const quaternion = worldTransform.getRotation();
					mesh.position.set( position.x(), position.y(), position.z() );
					mesh.quaternion.set( quaternion.x(), quaternion.y(), quaternion.z(), quaternion.w() );

				}

			}

		}

		lastTime = time;

	}
```
</details>

### `compose(position: any, quaternion: any, array: any, index: any): void`

**Parameters:**

- **`position`** `any`
- **`quaternion`** `any`
- **`array`** `any`
- **`index`** `any`

**Returns:** `void`

**Calls:**

- `quaternion.x`
- `quaternion.y`
- `quaternion.z`
- `quaternion.w`
- `position.x`
- `position.y`
- `position.z`

<details><summary>Code</summary>

```typescript
function compose( position, quaternion, array, index ) {

	const x = quaternion.x(), y = quaternion.y(), z = quaternion.z(), w = quaternion.w();
	const x2 = x + x, y2 = y + y, z2 = z + z;
	const xx = x * x2, xy = x * y2, xz = x * z2;
	const yy = y * y2, yz = y * z2, zz = z * z2;
	const wx = w * x2, wy = w * y2, wz = w * z2;

	array[ index + 0 ] = ( 1 - ( yy + zz ) );
	array[ index + 1 ] = ( xy + wz );
	array[ index + 2 ] = ( xz - wy );
	array[ index + 3 ] = 0;

	array[ index + 4 ] = ( xy - wz );
	array[ index + 5 ] = ( 1 - ( xx + zz ) );
	array[ index + 6 ] = ( yz + wx );
	array[ index + 7 ] = 0;

	array[ index + 8 ] = ( xz + wy );
	array[ index + 9 ] = ( yz - wx );
	array[ index + 10 ] = ( 1 - ( xx + yy ) );
	array[ index + 11 ] = 0;

	array[ index + 12 ] = position.x();
	array[ index + 13 ] = position.y();
	array[ index + 14 ] = position.z();
	array[ index + 15 ] = 1;

}
```
</details>


---