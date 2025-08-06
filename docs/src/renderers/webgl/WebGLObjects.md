[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLObjects.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLObjects.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `updateMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `frame` | `any` | let/var | `info.render.frame` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `skeleton` | `any` | let/var | `object.skeleton` | ✗ |
| `instancedMesh` | `any` | let/var | `event.target` | ✗ |


---

## Functions

### `WebGLObjects(gl: any, geometries: any, attributes: any, info: any): { update: (object: any) => any; dispose: () => void; }`

**Parameters:**

- **`gl`** `any`
- **`geometries`** `any`
- **`attributes`** `any`
- **`info`** `any`

**Returns:** `{ update: (object: any) => any; dispose: () => void; }`

**Calls:**

- `geometries.get`
- `updateMap.get`
- `geometries.update`
- `updateMap.set`
- `object.hasEventListener`
- `object.addEventListener`
- `attributes.update`
- `skeleton.update`
- `instancedMesh.removeEventListener`
- `attributes.remove`

**Internal Comments:**
```
// Update once per frame
```

<details><summary>Code</summary>

```typescript
function WebGLObjects( gl, geometries, attributes, info ) {

	let updateMap = new WeakMap();

	function update( object ) {

		const frame = info.render.frame;

		const geometry = object.geometry;
		const buffergeometry = geometries.get( object, geometry );

		// Update once per frame

		if ( updateMap.get( buffergeometry ) !== frame ) {

			geometries.update( buffergeometry );

			updateMap.set( buffergeometry, frame );

		}

		if ( object.isInstancedMesh ) {

			if ( object.hasEventListener( 'dispose', onInstancedMeshDispose ) === false ) {

				object.addEventListener( 'dispose', onInstancedMeshDispose );

			}

			if ( updateMap.get( object ) !== frame ) {

				attributes.update( object.instanceMatrix, gl.ARRAY_BUFFER );

				if ( object.instanceColor !== null ) {

					attributes.update( object.instanceColor, gl.ARRAY_BUFFER );

				}

				updateMap.set( object, frame );

			}

		}

		if ( object.isSkinnedMesh ) {

			const skeleton = object.skeleton;

			if ( updateMap.get( skeleton ) !== frame ) {

				skeleton.update();

				updateMap.set( skeleton, frame );

			}

		}

		return buffergeometry;

	}

	function dispose() {

		updateMap = new WeakMap();

	}

	function onInstancedMeshDispose( event ) {

		const instancedMesh = event.target;

		instancedMesh.removeEventListener( 'dispose', onInstancedMeshDispose );

		attributes.remove( instancedMesh.instanceMatrix );

		if ( instancedMesh.instanceColor !== null ) attributes.remove( instancedMesh.instanceColor );

	}

	return {

		update: update,
		dispose: dispose

	};

}
```
</details>

### `update(object: any): any`

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `geometries.get`
- `updateMap.get`
- `geometries.update`
- `updateMap.set`
- `object.hasEventListener`
- `object.addEventListener`
- `attributes.update`
- `skeleton.update`

**Internal Comments:**
```
// Update once per frame
```

<details><summary>Code</summary>

```typescript
function update( object ) {

		const frame = info.render.frame;

		const geometry = object.geometry;
		const buffergeometry = geometries.get( object, geometry );

		// Update once per frame

		if ( updateMap.get( buffergeometry ) !== frame ) {

			geometries.update( buffergeometry );

			updateMap.set( buffergeometry, frame );

		}

		if ( object.isInstancedMesh ) {

			if ( object.hasEventListener( 'dispose', onInstancedMeshDispose ) === false ) {

				object.addEventListener( 'dispose', onInstancedMeshDispose );

			}

			if ( updateMap.get( object ) !== frame ) {

				attributes.update( object.instanceMatrix, gl.ARRAY_BUFFER );

				if ( object.instanceColor !== null ) {

					attributes.update( object.instanceColor, gl.ARRAY_BUFFER );

				}

				updateMap.set( object, frame );

			}

		}

		if ( object.isSkinnedMesh ) {

			const skeleton = object.skeleton;

			if ( updateMap.get( skeleton ) !== frame ) {

				skeleton.update();

				updateMap.set( skeleton, frame );

			}

		}

		return buffergeometry;

	}
```
</details>

### `dispose(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function dispose() {

		updateMap = new WeakMap();

	}
```
</details>

### `onInstancedMeshDispose(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `instancedMesh.removeEventListener`
- `attributes.remove`

<details><summary>Code</summary>

```typescript
function onInstancedMeshDispose( event ) {

		const instancedMesh = event.target;

		instancedMesh.removeEventListener( 'dispose', onInstancedMeshDispose );

		attributes.remove( instancedMesh.instanceMatrix );

		if ( instancedMesh.instanceColor !== null ) attributes.remove( instancedMesh.instanceColor );

	}
```
</details>


---