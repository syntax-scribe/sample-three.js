[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLClipping.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 19 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLClipping.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix3` | `../../math/Matrix3.js` |
| `Plane` | `../../math/Plane.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `globalState` | `any` | let/var | `null` | ✗ |
| `numGlobalPlanes` | `number` | let/var | `0` | ✗ |
| `localClippingEnabled` | `boolean` | let/var | `false` | ✗ |
| `renderingShadows` | `boolean` | let/var | `false` | ✗ |
| `plane` | `Plane` | let/var | `new Plane()` | ✗ |
| `viewNormalMatrix` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `uniform` | `{ value: any; needsUpdate: boolean; }` | let/var | `{ value: null, needsUpdate: false }` | ✗ |
| `enabled` | `any` | let/var | `planes.length !== 0 \|\| enableLocalClipping \|\| // enable state of previous...` | ✗ |
| `planes` | `any` | let/var | `material.clippingPlanes` | ✗ |
| `clipIntersection` | `any` | let/var | `material.clipIntersection` | ✗ |
| `clipShadows` | `any` | let/var | `material.clipShadows` | ✗ |
| `nGlobal` | `number` | let/var | `renderingShadows ? 0 : numGlobalPlanes` | ✗ |
| `lGlobal` | `number` | let/var | `nGlobal * 4` | ✗ |
| `dstArray` | `any` | let/var | `materialProperties.clippingState \|\| null` | ✗ |
| `nPlanes` | `any` | let/var | `planes !== null ? planes.length : 0` | ✗ |
| `dstArray` | `any` | let/var | `null` | ✗ |
| `flatSize` | `any` | let/var | `dstOffset + nPlanes * 4` | ✗ |
| `viewMatrix` | `any` | let/var | `camera.matrixWorldInverse` | ✗ |


---

## Functions

### `WebGLClipping(properties: any): void`

**Parameters:**

- **`properties`** `any`

**Returns:** `void`

**Calls:**

- `projectPlanes`
- `properties.get`
- `resetGlobalState`
- `viewNormalMatrix.getNormalMatrix`
- `plane.copy( planes[ i ] ).applyMatrix4`
- `plane.normal.toArray`

**Internal Comments:**
```
// enable state of previous frame - the clipping code has to (x2)
// run another frame in order to reset the state: (x2)
// there's no local clipping
// there's no global clipping (x3)
```

<details><summary>Code</summary>

```typescript
function WebGLClipping( properties ) {

	const scope = this;

	let globalState = null,
		numGlobalPlanes = 0,
		localClippingEnabled = false,
		renderingShadows = false;

	const plane = new Plane(),
		viewNormalMatrix = new Matrix3(),

		uniform = { value: null, needsUpdate: false };

	this.uniform = uniform;
	this.numPlanes = 0;
	this.numIntersection = 0;

	this.init = function ( planes, enableLocalClipping ) {

		const enabled =
			planes.length !== 0 ||
			enableLocalClipping ||
			// enable state of previous frame - the clipping code has to
			// run another frame in order to reset the state:
			numGlobalPlanes !== 0 ||
			localClippingEnabled;

		localClippingEnabled = enableLocalClipping;

		numGlobalPlanes = planes.length;

		return enabled;

	};

	this.beginShadows = function () {

		renderingShadows = true;
		projectPlanes( null );

	};

	this.endShadows = function () {

		renderingShadows = false;

	};

	this.setGlobalState = function ( planes, camera ) {

		globalState = projectPlanes( planes, camera, 0 );

	};

	this.setState = function ( material, camera, useCache ) {

		const planes = material.clippingPlanes,
			clipIntersection = material.clipIntersection,
			clipShadows = material.clipShadows;

		const materialProperties = properties.get( material );

		if ( ! localClippingEnabled || planes === null || planes.length === 0 || renderingShadows && ! clipShadows ) {

			// there's no local clipping

			if ( renderingShadows ) {

				// there's no global clipping

				projectPlanes( null );

			} else {

				resetGlobalState();

			}

		} else {

			const nGlobal = renderingShadows ? 0 : numGlobalPlanes,
				lGlobal = nGlobal * 4;

			let dstArray = materialProperties.clippingState || null;

			uniform.value = dstArray; // ensure unique state

			dstArray = projectPlanes( planes, camera, lGlobal, useCache );

			for ( let i = 0; i !== lGlobal; ++ i ) {

				dstArray[ i ] = globalState[ i ];

			}

			materialProperties.clippingState = dstArray;
			this.numIntersection = clipIntersection ? this.numPlanes : 0;
			this.numPlanes += nGlobal;

		}


	};

	function resetGlobalState() {

		if ( uniform.value !== globalState ) {

			uniform.value = globalState;
			uniform.needsUpdate = numGlobalPlanes > 0;

		}

		scope.numPlanes = numGlobalPlanes;
		scope.numIntersection = 0;

	}

	function projectPlanes( planes, camera, dstOffset, skipTransform ) {

		const nPlanes = planes !== null ? planes.length : 0;
		let dstArray = null;

		if ( nPlanes !== 0 ) {

			dstArray = uniform.value;

			if ( skipTransform !== true || dstArray === null ) {

				const flatSize = dstOffset + nPlanes * 4,
					viewMatrix = camera.matrixWorldInverse;

				viewNormalMatrix.getNormalMatrix( viewMatrix );

				if ( dstArray === null || dstArray.length < flatSize ) {

					dstArray = new Float32Array( flatSize );

				}

				for ( let i = 0, i4 = dstOffset; i !== nPlanes; ++ i, i4 += 4 ) {

					plane.copy( planes[ i ] ).applyMatrix4( viewMatrix, viewNormalMatrix );

					plane.normal.toArray( dstArray, i4 );
					dstArray[ i4 + 3 ] = plane.constant;

				}

			}

			uniform.value = dstArray;
			uniform.needsUpdate = true;

		}

		scope.numPlanes = nPlanes;
		scope.numIntersection = 0;

		return dstArray;

	}

}
```
</details>

### `resetGlobalState(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function resetGlobalState() {

		if ( uniform.value !== globalState ) {

			uniform.value = globalState;
			uniform.needsUpdate = numGlobalPlanes > 0;

		}

		scope.numPlanes = numGlobalPlanes;
		scope.numIntersection = 0;

	}
```
</details>

### `projectPlanes(planes: any, camera: any, dstOffset: any, skipTransform: any): any`

**Parameters:**

- **`planes`** `any`
- **`camera`** `any`
- **`dstOffset`** `any`
- **`skipTransform`** `any`

**Returns:** `any`

**Calls:**

- `viewNormalMatrix.getNormalMatrix`
- `plane.copy( planes[ i ] ).applyMatrix4`
- `plane.normal.toArray`

<details><summary>Code</summary>

```typescript
function projectPlanes( planes, camera, dstOffset, skipTransform ) {

		const nPlanes = planes !== null ? planes.length : 0;
		let dstArray = null;

		if ( nPlanes !== 0 ) {

			dstArray = uniform.value;

			if ( skipTransform !== true || dstArray === null ) {

				const flatSize = dstOffset + nPlanes * 4,
					viewMatrix = camera.matrixWorldInverse;

				viewNormalMatrix.getNormalMatrix( viewMatrix );

				if ( dstArray === null || dstArray.length < flatSize ) {

					dstArray = new Float32Array( flatSize );

				}

				for ( let i = 0, i4 = dstOffset; i !== nPlanes; ++ i, i4 += 4 ) {

					plane.copy( planes[ i ] ).applyMatrix4( viewMatrix, viewNormalMatrix );

					plane.normal.toArray( dstArray, i4 );
					dstArray[ i4 + 3 ] = plane.constant;

				}

			}

			uniform.value = dstArray;
			uniform.needsUpdate = true;

		}

		scope.numPlanes = nPlanes;
		scope.numIntersection = 0;

		return dstArray;

	}
```
</details>


---