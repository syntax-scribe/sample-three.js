[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Lights.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/accessors/Lights.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `uniform` | `../core/UniformNode.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `Vector3` | `../../math/Vector3.js` |
| `cameraViewMatrix` | `./Camera.js` |
| `positionWorld` | `./Position.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `uniformsLib` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `getLightData(light: any): any`

**Parameters:**

- **`light`** `any`

**Returns:** `any`

**Calls:**

- `uniformsLib.get`
- `uniformsLib.set`

<details><summary>Code</summary>

```typescript
function getLightData( light ) {

	uniformsLib = uniformsLib || new WeakMap();

	let uniforms = uniformsLib.get( light );

	if ( uniforms === undefined ) uniformsLib.set( light, uniforms = {} );

	return uniforms;

}
```
</details>

### `lightShadowMatrix(light: Light): UniformNode<mat4>`

**JSDoc:**
```typescript
/**
 * TSL function for getting a shadow matrix uniform node for the given light.
 *
 * @tsl
 * @function
 * @param {Light} light -The light source.
 * @returns {UniformNode<mat4>} The shadow matrix uniform node.
 */
```

**Parameters:**

- **`light`** `Light`

**Returns:** `UniformNode<mat4>`

**Calls:**

- `getLightData`
- `uniform( 'mat4' ).setGroup( renderGroup ).onRenderUpdate`
- `light.shadow.updateMatrices`

<details><summary>Code</summary>

```typescript
export function lightShadowMatrix( light ) {

	const data = getLightData( light );

	return data.shadowMatrix || ( data.shadowMatrix = uniform( 'mat4' ).setGroup( renderGroup ).onRenderUpdate( ( frame ) => {

		if ( light.castShadow !== true || frame.renderer.shadowMap.enabled === false ) {

			light.shadow.updateMatrices( light );

		}

		return light.shadow.matrix;

	} ) );

}
```
</details>

### `lightProjectionUV(light: Light, position: any): any`

**JSDoc:**
```typescript
/**
 * TSL function for getting projected uv coordinates for the given light.
 * Relevant when using maps with spot lights.
 *
 * @tsl
 * @function
 * @param {Light} light -The light source.
 * @param {Node<vec3>} [position=positionWorld] -The position to project.
 * @returns {Node<vec3>} The projected uvs.
 */
```

**Parameters:**

- **`light`** `Light`
- **`position`** `any`

**Returns:** `any`

**Calls:**

- `lightShadowMatrix( light ).mul`
- `spotLightCoord.xyz.div`

<details><summary>Code</summary>

```typescript
export function lightProjectionUV( light, position = positionWorld ) {

	const spotLightCoord = lightShadowMatrix( light ).mul( position );
	const projectionUV = spotLightCoord.xyz.div( spotLightCoord.w );

	return projectionUV;

}
```
</details>

### `lightPosition(light: Light): UniformNode<vec3>`

**JSDoc:**
```typescript
/**
 * TSL function for getting the position in world space for the given light.
 *
 * @tsl
 * @function
 * @param {Light} light -The light source.
 * @returns {UniformNode<vec3>} The light's position in world space.
 */
```

**Parameters:**

- **`light`** `Light`

**Returns:** `UniformNode<vec3>`

**Calls:**

- `getLightData`
- `uniform( new Vector3() ).setGroup( renderGroup ).onRenderUpdate`
- `self.value.setFromMatrixPosition`

<details><summary>Code</summary>

```typescript
export function lightPosition( light ) {

	const data = getLightData( light );

	return data.position || ( data.position = uniform( new Vector3() ).setGroup( renderGroup ).onRenderUpdate( ( _, self ) => self.value.setFromMatrixPosition( light.matrixWorld ) ) );

}
```
</details>

### `lightTargetPosition(light: Light): UniformNode<vec3>`

**JSDoc:**
```typescript
/**
 * TSL function for getting the light target position in world space for the given light.
 *
 * @tsl
 * @function
 * @param {Light} light -The light source.
 * @returns {UniformNode<vec3>} The light target position in world space.
 */
```

**Parameters:**

- **`light`** `Light`

**Returns:** `UniformNode<vec3>`

**Calls:**

- `getLightData`
- `uniform( new Vector3() ).setGroup( renderGroup ).onRenderUpdate`
- `self.value.setFromMatrixPosition`

<details><summary>Code</summary>

```typescript
export function lightTargetPosition( light ) {

	const data = getLightData( light );

	return data.targetPosition || ( data.targetPosition = uniform( new Vector3() ).setGroup( renderGroup ).onRenderUpdate( ( _, self ) => self.value.setFromMatrixPosition( light.target.matrixWorld ) ) );

}
```
</details>

### `lightViewPosition(light: Light): UniformNode<vec3>`

**JSDoc:**
```typescript
/**
 * TSL function for getting the position in view space for the given light.
 *
 * @tsl
 * @function
 * @param {Light} light - The light source.
 * @returns {UniformNode<vec3>} The light's position in view space.
 */
```

**Parameters:**

- **`light`** `Light`

**Returns:** `UniformNode<vec3>`

**Calls:**

- `getLightData`
- `uniform( new Vector3() ).setGroup( renderGroup ).onRenderUpdate`
- `self.value.setFromMatrixPosition`
- `self.value.applyMatrix4`

<details><summary>Code</summary>

```typescript
export function lightViewPosition( light ) {

	const data = getLightData( light );

	return data.viewPosition || ( data.viewPosition = uniform( new Vector3() ).setGroup( renderGroup ).onRenderUpdate( ( { camera }, self ) => {

		self.value = self.value || new Vector3();
		self.value.setFromMatrixPosition( light.matrixWorld );

		self.value.applyMatrix4( camera.matrixWorldInverse );

	} ) );

}
```
</details>

### `lightTargetDirection(light: Light): any`

**Parameters:**

- **`light`** `Light`

**Returns:** `any`

**Calls:**

- `cameraViewMatrix.transformDirection`

<details><summary>Code</summary>

```typescript
( light ) => cameraViewMatrix.transformDirection( lightPosition( light ).sub( lightTargetPosition( light ) ) )
```
</details>


---