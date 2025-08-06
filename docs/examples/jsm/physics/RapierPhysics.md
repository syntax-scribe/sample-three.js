[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RapierPhysics.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 39 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/physics/RapierPhysics.js`**

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
| `RAPIER_PATH` | `"https://cdn.skypack.dev/@dimforge/ra...` | let/var | `'https://cdn.skypack.dev/@dimforge/rapier3d-compat@0.17.3'` | ✗ |
| `frameRate` | `60` | let/var | `60` | ✗ |
| `_scale` | `any` | let/var | `new Vector3( 1, 1, 1 )` | ✗ |
| `ZERO` | `any` | let/var | `new Vector3()` | ✗ |
| `RAPIER` | `any` | let/var | `null` | ✗ |
| `parameters` | `any` | let/var | `geometry.parameters` | ✗ |
| `sx` | `number` | let/var | `parameters.width !== undefined ? parameters.width / 2 : 0.5` | ✗ |
| `sy` | `number` | let/var | `parameters.height !== undefined ? parameters.height / 2 : 0.5` | ✗ |
| `sz` | `number` | let/var | `parameters.depth !== undefined ? parameters.depth / 2 : 0.5` | ✗ |
| `radius` | `any` | let/var | `parameters.radius !== undefined ? parameters.radius : 0.1` | ✗ |
| `sx` | `number` | let/var | `parameters.width !== undefined ? parameters.width / 2 : 0.5` | ✗ |
| `sy` | `number` | let/var | `parameters.height !== undefined ? parameters.height / 2 : 0.5` | ✗ |
| `sz` | `number` | let/var | `parameters.depth !== undefined ? parameters.depth / 2 : 0.5` | ✗ |
| `radius` | `any` | let/var | `parameters.radius !== undefined ? parameters.radius : 1` | ✗ |
| `radius` | `any` | let/var | `parameters.radiusBottom !== undefined ? parameters.radiusBottom : 0.5` | ✗ |
| `length` | `any` | let/var | `parameters.height !== undefined ? parameters.height : 0.5` | ✗ |
| `radius` | `any` | let/var | `parameters.radius !== undefined ? parameters.radius : 0.5` | ✗ |
| `length` | `any` | let/var | `parameters.height !== undefined ? parameters.height : 0.5` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `vertex` | `any` | let/var | `new Vector3()` | ✗ |
| `indices` | `any` | let/var | `geometry.getIndex() === null ? Uint32Array.from( Array( parseInt( vertices.le...` | ✗ |
| `gravity` | `any` | let/var | `new Vector3( 0.0, - 9.81, 0.0 )` | ✗ |
| `world` | `any` | let/var | `new RAPIER.World( gravity )` | ✗ |
| `meshes` | `any[]` | let/var | `[]` | ✗ |
| `meshMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `_vector` | `any` | let/var | `new Vector3()` | ✗ |
| `_quaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `_matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `physics` | `any` | let/var | `child.userData.physics` | ✗ |
| `body` | `any` | let/var | `mesh.userData.physics.body` | ✗ |
| `collider` | `any` | let/var | `mesh.userData.physics.collider` | ✗ |
| `array` | `any` | let/var | `mesh.instanceMatrix.array` | ✗ |
| `bodies` | `any[]` | let/var | `[]` | ✗ |
| `colliders` | `any[]` | let/var | `[]` | ✗ |
| `desc` | `any` | let/var | `mass > 0 ? RAPIER.RigidBodyDesc.dynamic() : RAPIER.RigidBodyDesc.fixed()` | ✗ |
| `clock` | `any` | let/var | `new Clock()` | ✗ |
| `mesh` | `any` | let/var | `meshes[ i ]` | ✗ |
| `array` | `any` | let/var | `mesh.instanceMatrix.array` | ✗ |
| `body` | `any` | let/var | `bodies[ j ]` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `RapierPhysics` | import( `${RAPIER_PATH}` ), RAPIER.init() | *none* |


---

## Functions

### `getShape(geometry: any): any`

**Parameters:**

- **`geometry`** `any`

**Returns:** `any`

**Calls:**

- `RAPIER.ColliderDesc.roundCuboid`
- `RAPIER.ColliderDesc.cuboid`
- `RAPIER.ColliderDesc.ball`
- `RAPIER.ColliderDesc.cylinder`
- `RAPIER.ColliderDesc.capsule`
- `geometry.getAttribute`
- `vertex.fromBufferAttribute`
- `vertices.push`
- `geometry.getIndex`
- `Uint32Array.from`
- `Array( parseInt( vertices.length / 3 ) ).keys`
- `RAPIER.ColliderDesc.trimesh`

**Internal Comments:**
```
// TODO change type to is*
// if the buffer is non-indexed, generate an index buffer (x2)
```

<details><summary>Code</summary>

```typescript
function getShape( geometry ) {

	const parameters = geometry.parameters;

	// TODO change type to is*

	if ( geometry.type === 'RoundedBoxGeometry' ) {

		const sx = parameters.width !== undefined ? parameters.width / 2 : 0.5;
		const sy = parameters.height !== undefined ? parameters.height / 2 : 0.5;
		const sz = parameters.depth !== undefined ? parameters.depth / 2 : 0.5;
		const radius = parameters.radius !== undefined ? parameters.radius : 0.1;

		return RAPIER.ColliderDesc.roundCuboid( sx - radius, sy - radius, sz - radius, radius );

	} else if ( geometry.type === 'BoxGeometry' ) {

		const sx = parameters.width !== undefined ? parameters.width / 2 : 0.5;
		const sy = parameters.height !== undefined ? parameters.height / 2 : 0.5;
		const sz = parameters.depth !== undefined ? parameters.depth / 2 : 0.5;

		return RAPIER.ColliderDesc.cuboid( sx, sy, sz );

	} else if ( geometry.type === 'SphereGeometry' || geometry.type === 'IcosahedronGeometry' ) {

		const radius = parameters.radius !== undefined ? parameters.radius : 1;
		return RAPIER.ColliderDesc.ball( radius );

	} else if ( geometry.type === 'CylinderGeometry' ) {

		const radius = parameters.radiusBottom !== undefined ? parameters.radiusBottom : 0.5;
		const length = parameters.height !== undefined ? parameters.height : 0.5;

		return RAPIER.ColliderDesc.cylinder( length / 2, radius );

	} else if ( geometry.type === 'CapsuleGeometry' ) {

		const radius = parameters.radius !== undefined ? parameters.radius : 0.5;
		const length = parameters.height !== undefined ? parameters.height : 0.5;

		return RAPIER.ColliderDesc.capsule( length / 2, radius );

	} else if ( geometry.type === 'BufferGeometry' ) {

		const vertices = [];
		const vertex = new Vector3();
		const position = geometry.getAttribute( 'position' );

		for ( let i = 0; i < position.count; i ++ ) {

			vertex.fromBufferAttribute( position, i );
			vertices.push( vertex.x, vertex.y, vertex.z );

		}

		// if the buffer is non-indexed, generate an index buffer
		const indices = geometry.getIndex() === null
			? Uint32Array.from( Array( parseInt( vertices.length / 3 ) ).keys() )
			: geometry.getIndex().array;

		return RAPIER.ColliderDesc.trimesh( vertices, indices );

	}

	return null;

}
```
</details>

### `RapierPhysics(): Promise<{ RAPIER: any; world: any; addScene: (scene: any) => void; addMesh: (mesh: any, mass?: number, restitution?: number) => void; removeMesh: (mesh: any) => void; setMeshPosition: (mesh: any, position: any, index?: number) => void; setMeshVelocity: (mesh: any, velocity: any, index?: number) => void; addHeightfie...`

**JSDoc:**
```typescript
/**
 * @classdesc Can be used to include Rapier as a Physics engine into
 * `three.js` apps. The API can be initialized via:
 * ```js
 * const physics = await RapierPhysics();
 * ```
 * The component automatically imports Rapier from a CDN so make sure
 * to use the component with an active Internet connection.
 *
 * @name RapierPhysics
 * @class
 * @hideconstructor
 * @three_import import { RapierPhysics } from 'three/addons/physics/RapierPhysics.js';
 */
```

**Returns:** `Promise<{ RAPIER: any; world: any; addScene: (scene: any) => void; addMesh: (mesh: any, mass?: number, restitution?: number) => void; removeMesh: (mesh: any) => void; setMeshPosition: (mesh: any, position: any, index?: number) => void; setMeshVelocity: (mesh: any, velocity: any, index?: number) => void; addHeightfie...`

**Calls:**

- `complex_call_3044`
- `RAPIER.init`
- `scene.traverse`
- `addMesh`
- `getShape`
- `shape.setMass`
- `shape.setRestitution`
- `createInstancedBody`
- `createBody`
- `meshes.push`
- `meshMap.set`
- `meshes.indexOf`
- `meshes.splice`
- `meshMap.delete`
- `removeBody`
- `removeCollider`
- `_vector.fromArray`
- `bodies.push`
- `colliders.push`
- `RAPIER.RigidBodyDesc.dynamic`
- `RAPIER.RigidBodyDesc.fixed`
- `desc.setTranslation`
- `desc.setRotation`
- `world.createRigidBody`
- `world.createCollider`
- `Array.isArray`
- `world.removeRigidBody`
- `world.removeCollider`
- `meshMap.get`
- `body.setAngvel`
- `body.setLinvel`
- `body.setTranslation`
- `RAPIER.ColliderDesc.heightfield`
- `bodyDesc.setTranslation`
- `bodyDesc.setRotation`
- `clock.getDelta`
- `world.step`
- `body.translation`
- `_quaternion.copy`
- `body.rotation`
- `_matrix.compose( position, _quaternion, _scale ).toArray`
- `mesh.computeBoundingSphere`
- `mesh.position.copy`
- `mesh.quaternion.copy`
- `setInterval`

**Internal Comments:**
```
// Docs: https://rapier.rs/docs/api/javascript/JavaScript3D/ (x2)
// (x3)
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
		 * @name RapierPhysics#addScene
		 * @param {Object3D} scene The scene or any type of 3D object to add.
		 */ (x2)
/**
		 * Adds the given mesh to this physics simulation.
		 *
		 * @method
		 * @name RapierPhysics#addMesh
		 * @param {Mesh} mesh The mesh to add.
		 * @param {number} [mass=0] The mass in kg of the mesh.
		 * @param {number} [restitution=0] The restitution/friction of the mesh.
		 */ (x2)
/**
		 * Removes the given mesh from this physics simulation.
		 *
		 * @method
		 * @name RapierPhysics#removeMesh
		 * @param {Mesh} mesh The mesh to remove.
		 */ (x2)
/**
		 * Set the position of the given mesh which is part of the physics simulation. Calling this
		 * method will reset the current simulated velocity of the mesh.
		 *
		 * @method
		 * @name RapierPhysics#setMeshPosition
		 * @param {Mesh} mesh The mesh to update the position for.
		 * @param {Vector3} position - The new position.
		 * @param {number} [index=0] - If the mesh is instanced, the index represents the instanced ID.
		 */ (x2)
/**
		 * Set the velocity of the given mesh which is part of the physics simulation.
		 *
		 * @method
		 * @name RapierPhysics#setMeshVelocity
		 * @param {Mesh} mesh The mesh to update the velocity for.
		 * @param {Vector3} velocity - The new velocity.
		 * @param {number} [index=0] - If the mesh is instanced, the index represents the instanced ID.
		 */ (x2)
/**
		 * Adds a heightfield terrain to the physics simulation.
		 * 
		 * @method
		 * @name RapierPhysics#addHeightfield
		 * @param {Mesh} mesh - The Three.js mesh representing the terrain.
		 * @param {number} width - The number of vertices along the width (x-axis) of the heightfield.
		 * @param {number} depth - The number of vertices along the depth (z-axis) of the heightfield.
		 * @param {Float32Array} heights - Array of height values for each vertex in the heightfield.
		 * @param {Object} scale - Scale factors for the heightfield dimensions.
		 * @param {number} scale.x - Scale factor for width.
		 * @param {number} scale.y - Scale factor for height.
		 * @param {number} scale.z - Scale factor for depth.
		 * @returns {RigidBody} The created Rapier rigid body for the heightfield.
		 */ (x2)
```

<details><summary>Code</summary>

```typescript
async function RapierPhysics() {

	if ( RAPIER === null ) {

		RAPIER = await import( `${RAPIER_PATH}` );
		await RAPIER.init();

	}

	// Docs: https://rapier.rs/docs/api/javascript/JavaScript3D/

	const gravity = new Vector3( 0.0, - 9.81, 0.0 );
	const world = new RAPIER.World( gravity );

	const meshes = [];
	const meshMap = new WeakMap();

	const _vector = new Vector3();
	const _quaternion = new Quaternion();
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

		shape.setMass( mass );
		shape.setRestitution( restitution );

		const { body, collider } = mesh.isInstancedMesh
			? createInstancedBody( mesh, mass, shape )
			: createBody( mesh.position, mesh.quaternion, mass, shape );

		if ( ! mesh.userData.physics ) mesh.userData.physics = {};

		mesh.userData.physics.body = body;
		mesh.userData.physics.collider = collider;

		if ( mass > 0 ) {

			meshes.push( mesh );
			meshMap.set( mesh, { body, collider } );

		}

	}

	function removeMesh( mesh ) {

		const index = meshes.indexOf( mesh );

		if ( index !== - 1 ) {

			meshes.splice( index, 1 );
			meshMap.delete( mesh );

			if ( ! mesh.userData.physics ) return;

			const body = mesh.userData.physics.body;
			const collider = mesh.userData.physics.collider;

			if ( body ) removeBody( body );
			if ( collider ) removeCollider( collider );

		}

	}

	function createInstancedBody( mesh, mass, shape ) {

		const array = mesh.instanceMatrix.array;

		const bodies = [];
		const colliders = [];

		for ( let i = 0; i < mesh.count; i ++ ) {

			const position = _vector.fromArray( array, i * 16 + 12 );
			const { body, collider } = createBody( position, null, mass, shape );
			bodies.push( body );
			colliders.push( collider );

		}

		return { body: bodies, collider: colliders };

	}

	function createBody( position, quaternion, mass, shape ) {

		const desc = mass > 0 ? RAPIER.RigidBodyDesc.dynamic() : RAPIER.RigidBodyDesc.fixed();
		desc.setTranslation( ...position );
		if ( quaternion !== null ) desc.setRotation( quaternion );

		const body = world.createRigidBody( desc );
		const collider = world.createCollider( shape, body );

		return { body, collider };

	}

	function removeBody( body ) {

		if ( Array.isArray( body ) ) {

			for ( let i = 0; i < body.length; i ++ ) {

				world.removeRigidBody( body[ i ] );

			}

		} else {

			world.removeRigidBody( body );

		}

	}

	function removeCollider( collider ) {

		if ( Array.isArray( collider ) ) {

			for ( let i = 0; i < collider.length; i ++ ) {

				world.removeCollider( collider[ i ] );

			}

		} else {

			world.removeCollider( collider );

		}

	}

	function setMeshPosition( mesh, position, index = 0 ) {

		let { body } = meshMap.get( mesh );

		if ( mesh.isInstancedMesh ) {

			body = body[ index ];

		}

		body.setAngvel( ZERO );
		body.setLinvel( ZERO );
		body.setTranslation( position );

	}

	function setMeshVelocity( mesh, velocity, index = 0 ) {

		let { body } = meshMap.get( mesh );

		if ( mesh.isInstancedMesh ) {

			body = body[ index ];

		}

		body.setLinvel( velocity );

	}

	function addHeightfield( mesh, width, depth, heights, scale ) {

		const shape = RAPIER.ColliderDesc.heightfield( width, depth, heights, scale );

		const bodyDesc = RAPIER.RigidBodyDesc.fixed();
		bodyDesc.setTranslation( mesh.position.x, mesh.position.y, mesh.position.z );
		bodyDesc.setRotation( mesh.quaternion );

		const body = world.createRigidBody( bodyDesc );
		world.createCollider( shape, body );

		if ( ! mesh.userData.physics ) mesh.userData.physics = {};
		mesh.userData.physics.body = body;

		return body;

	}

	//

	const clock = new Clock();

	function step() {

		world.timestep = clock.getDelta();
		world.step();

		//

		for ( let i = 0, l = meshes.length; i < l; i ++ ) {

			const mesh = meshes[ i ];

			if ( mesh.isInstancedMesh ) {

				const array = mesh.instanceMatrix.array;
				const { body: bodies } = meshMap.get( mesh );

				for ( let j = 0; j < bodies.length; j ++ ) {

					const body = bodies[ j ];

					const position = body.translation();
					_quaternion.copy( body.rotation() );

					_matrix.compose( position, _quaternion, _scale ).toArray( array, j * 16 );

				}

				mesh.instanceMatrix.needsUpdate = true;
				mesh.computeBoundingSphere();

			} else {

				const { body } = meshMap.get( mesh );

				mesh.position.copy( body.translation() );
				mesh.quaternion.copy( body.rotation() );

			}

		}

	}

	// animate

	setInterval( step, 1000 / frameRate );

	return {
		RAPIER,
		world,
		/**
		 * Adds the given scene to this physics simulation. Only meshes with a
		 * `physics` object in their {@link Object3D#userData} field will be honored.
		 * The object can be used to store the mass and restitution of the mesh. E.g.:
		 * ```js
		 * box.userData.physics = { mass: 1, restitution: 0 };
		 * ```
		 *
		 * @method
		 * @name RapierPhysics#addScene
		 * @param {Object3D} scene The scene or any type of 3D object to add.
		 */
		addScene: addScene,

		/**
		 * Adds the given mesh to this physics simulation.
		 *
		 * @method
		 * @name RapierPhysics#addMesh
		 * @param {Mesh} mesh The mesh to add.
		 * @param {number} [mass=0] The mass in kg of the mesh.
		 * @param {number} [restitution=0] The restitution/friction of the mesh.
		 */
		addMesh: addMesh,

		/**
		 * Removes the given mesh from this physics simulation.
		 *
		 * @method
		 * @name RapierPhysics#removeMesh
		 * @param {Mesh} mesh The mesh to remove.
		 */
		removeMesh: removeMesh,

		/**
		 * Set the position of the given mesh which is part of the physics simulation. Calling this
		 * method will reset the current simulated velocity of the mesh.
		 *
		 * @method
		 * @name RapierPhysics#setMeshPosition
		 * @param {Mesh} mesh The mesh to update the position for.
		 * @param {Vector3} position - The new position.
		 * @param {number} [index=0] - If the mesh is instanced, the index represents the instanced ID.
		 */
		setMeshPosition: setMeshPosition,

		/**
		 * Set the velocity of the given mesh which is part of the physics simulation.
		 *
		 * @method
		 * @name RapierPhysics#setMeshVelocity
		 * @param {Mesh} mesh The mesh to update the velocity for.
		 * @param {Vector3} velocity - The new velocity.
		 * @param {number} [index=0] - If the mesh is instanced, the index represents the instanced ID.
		 */
		setMeshVelocity: setMeshVelocity,

		/**
		 * Adds a heightfield terrain to the physics simulation.
		 * 
		 * @method
		 * @name RapierPhysics#addHeightfield
		 * @param {Mesh} mesh - The Three.js mesh representing the terrain.
		 * @param {number} width - The number of vertices along the width (x-axis) of the heightfield.
		 * @param {number} depth - The number of vertices along the depth (z-axis) of the heightfield.
		 * @param {Float32Array} heights - Array of height values for each vertex in the heightfield.
		 * @param {Object} scale - Scale factors for the heightfield dimensions.
		 * @param {number} scale.x - Scale factor for width.
		 * @param {number} scale.y - Scale factor for height.
		 * @param {number} scale.z - Scale factor for depth.
		 * @returns {RigidBody} The created Rapier rigid body for the heightfield.
		 */
		addHeightfield: addHeightfield

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
- `shape.setMass`
- `shape.setRestitution`
- `createInstancedBody`
- `createBody`
- `meshes.push`
- `meshMap.set`

<details><summary>Code</summary>

```typescript
function addMesh( mesh, mass = 0, restitution = 0 ) {

		const shape = getShape( mesh.geometry );

		if ( shape === null ) return;

		shape.setMass( mass );
		shape.setRestitution( restitution );

		const { body, collider } = mesh.isInstancedMesh
			? createInstancedBody( mesh, mass, shape )
			: createBody( mesh.position, mesh.quaternion, mass, shape );

		if ( ! mesh.userData.physics ) mesh.userData.physics = {};

		mesh.userData.physics.body = body;
		mesh.userData.physics.collider = collider;

		if ( mass > 0 ) {

			meshes.push( mesh );
			meshMap.set( mesh, { body, collider } );

		}

	}
```
</details>

### `removeMesh(mesh: any): void`

**Parameters:**

- **`mesh`** `any`

**Returns:** `void`

**Calls:**

- `meshes.indexOf`
- `meshes.splice`
- `meshMap.delete`
- `removeBody`
- `removeCollider`

<details><summary>Code</summary>

```typescript
function removeMesh( mesh ) {

		const index = meshes.indexOf( mesh );

		if ( index !== - 1 ) {

			meshes.splice( index, 1 );
			meshMap.delete( mesh );

			if ( ! mesh.userData.physics ) return;

			const body = mesh.userData.physics.body;
			const collider = mesh.userData.physics.collider;

			if ( body ) removeBody( body );
			if ( collider ) removeCollider( collider );

		}

	}
```
</details>

### `createInstancedBody(mesh: any, mass: any, shape: any): { body: any[]; collider: any[]; }`

**Parameters:**

- **`mesh`** `any`
- **`mass`** `any`
- **`shape`** `any`

**Returns:** `{ body: any[]; collider: any[]; }`

**Calls:**

- `_vector.fromArray`
- `createBody`
- `bodies.push`
- `colliders.push`

<details><summary>Code</summary>

```typescript
function createInstancedBody( mesh, mass, shape ) {

		const array = mesh.instanceMatrix.array;

		const bodies = [];
		const colliders = [];

		for ( let i = 0; i < mesh.count; i ++ ) {

			const position = _vector.fromArray( array, i * 16 + 12 );
			const { body, collider } = createBody( position, null, mass, shape );
			bodies.push( body );
			colliders.push( collider );

		}

		return { body: bodies, collider: colliders };

	}
```
</details>

### `createBody(position: any, quaternion: any, mass: any, shape: any): { body: any; collider: any; }`

**Parameters:**

- **`position`** `any`
- **`quaternion`** `any`
- **`mass`** `any`
- **`shape`** `any`

**Returns:** `{ body: any; collider: any; }`

**Calls:**

- `RAPIER.RigidBodyDesc.dynamic`
- `RAPIER.RigidBodyDesc.fixed`
- `desc.setTranslation`
- `desc.setRotation`
- `world.createRigidBody`
- `world.createCollider`

<details><summary>Code</summary>

```typescript
function createBody( position, quaternion, mass, shape ) {

		const desc = mass > 0 ? RAPIER.RigidBodyDesc.dynamic() : RAPIER.RigidBodyDesc.fixed();
		desc.setTranslation( ...position );
		if ( quaternion !== null ) desc.setRotation( quaternion );

		const body = world.createRigidBody( desc );
		const collider = world.createCollider( shape, body );

		return { body, collider };

	}
```
</details>

### `removeBody(body: any): void`

**Parameters:**

- **`body`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `world.removeRigidBody`

<details><summary>Code</summary>

```typescript
function removeBody( body ) {

		if ( Array.isArray( body ) ) {

			for ( let i = 0; i < body.length; i ++ ) {

				world.removeRigidBody( body[ i ] );

			}

		} else {

			world.removeRigidBody( body );

		}

	}
```
</details>

### `removeCollider(collider: any): void`

**Parameters:**

- **`collider`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `world.removeCollider`

<details><summary>Code</summary>

```typescript
function removeCollider( collider ) {

		if ( Array.isArray( collider ) ) {

			for ( let i = 0; i < collider.length; i ++ ) {

				world.removeCollider( collider[ i ] );

			}

		} else {

			world.removeCollider( collider );

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
- `body.setAngvel`
- `body.setLinvel`
- `body.setTranslation`

<details><summary>Code</summary>

```typescript
function setMeshPosition( mesh, position, index = 0 ) {

		let { body } = meshMap.get( mesh );

		if ( mesh.isInstancedMesh ) {

			body = body[ index ];

		}

		body.setAngvel( ZERO );
		body.setLinvel( ZERO );
		body.setTranslation( position );

	}
```
</details>

### `setMeshVelocity(mesh: any, velocity: any, index: number): void`

**Parameters:**

- **`mesh`** `any`
- **`velocity`** `any`
- **`index`** `number`

**Returns:** `void`

**Calls:**

- `meshMap.get`
- `body.setLinvel`

<details><summary>Code</summary>

```typescript
function setMeshVelocity( mesh, velocity, index = 0 ) {

		let { body } = meshMap.get( mesh );

		if ( mesh.isInstancedMesh ) {

			body = body[ index ];

		}

		body.setLinvel( velocity );

	}
```
</details>

### `addHeightfield(mesh: any, width: any, depth: any, heights: any, scale: any): any`

**Parameters:**

- **`mesh`** `any`
- **`width`** `any`
- **`depth`** `any`
- **`heights`** `any`
- **`scale`** `any`

**Returns:** `any`

**Calls:**

- `RAPIER.ColliderDesc.heightfield`
- `RAPIER.RigidBodyDesc.fixed`
- `bodyDesc.setTranslation`
- `bodyDesc.setRotation`
- `world.createRigidBody`
- `world.createCollider`

<details><summary>Code</summary>

```typescript
function addHeightfield( mesh, width, depth, heights, scale ) {

		const shape = RAPIER.ColliderDesc.heightfield( width, depth, heights, scale );

		const bodyDesc = RAPIER.RigidBodyDesc.fixed();
		bodyDesc.setTranslation( mesh.position.x, mesh.position.y, mesh.position.z );
		bodyDesc.setRotation( mesh.quaternion );

		const body = world.createRigidBody( bodyDesc );
		world.createCollider( shape, body );

		if ( ! mesh.userData.physics ) mesh.userData.physics = {};
		mesh.userData.physics.body = body;

		return body;

	}
```
</details>

### `step(): void`

**Returns:** `void`

**Calls:**

- `clock.getDelta`
- `world.step`
- `meshMap.get`
- `body.translation`
- `_quaternion.copy`
- `body.rotation`
- `_matrix.compose( position, _quaternion, _scale ).toArray`
- `mesh.computeBoundingSphere`
- `mesh.position.copy`
- `mesh.quaternion.copy`

**Internal Comments:**
```
//
```

<details><summary>Code</summary>

```typescript
function step() {

		world.timestep = clock.getDelta();
		world.step();

		//

		for ( let i = 0, l = meshes.length; i < l; i ++ ) {

			const mesh = meshes[ i ];

			if ( mesh.isInstancedMesh ) {

				const array = mesh.instanceMatrix.array;
				const { body: bodies } = meshMap.get( mesh );

				for ( let j = 0; j < bodies.length; j ++ ) {

					const body = bodies[ j ];

					const position = body.translation();
					_quaternion.copy( body.rotation() );

					_matrix.compose( position, _quaternion, _scale ).toArray( array, j * 16 );

				}

				mesh.instanceMatrix.needsUpdate = true;
				mesh.computeBoundingSphere();

			} else {

				const { body } = meshMap.get( mesh );

				mesh.position.copy( body.translation() );
				mesh.quaternion.copy( body.rotation() );

			}

		}

	}
```
</details>


---