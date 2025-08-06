[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `VolumetricLightingModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 17 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/functions/VolumetricLightingModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingModel` | `../core/LightingModel.js` |
| `property` | `../core/PropertyNode.js` |
| `float` | `../tsl/TSLBase.js` |
| `If` | `../tsl/TSLBase.js` |
| `uniform` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |
| `positionWorld` | `../accessors/Position.js` |
| `cameraFar` | `../accessors/Camera.js` |
| `cameraNear` | `../accessors/Camera.js` |
| `cameraPosition` | `../accessors/Camera.js` |
| `cameraViewMatrix` | `../accessors/Camera.js` |
| `Loop` | `../utils/LoopNode.js` |
| `linearDepth` | `../display/ViewportDepthNode.js` |
| `viewZToPerspectiveDepth` | `../display/ViewportDepthNode.js` |
| `modelRadius` | `../accessors/ModelNode.js` |
| `LTC_Evaluate_Volume` | `./BSDF/LTC.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `positionViewRay` | `any` | let/var | `cameraViewMatrix.mul( vec4( positionRay, 1 ) ).xyz` | ✗ |
| `scatteringNode` | `any` | let/var | `*not shown*` | ✗ |
| `sceneDepthNode` | `any` | let/var | `builder.context.sceneDepthNode` | ✗ |
| `P` | `any` | let/var | `builder.context.positionView` | ✗ |


---

## Functions

### `VolumetricLightingModel.start(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `property (from ../core/PropertyNode.js)`
- `If( cameraPosition.sub( positionWorld ).length().greaterThan( modelRadius.mul( 2 ) ), () => {

			startPos.assign( cameraPosition );
			endPos.assign( positionWorld );

		} ).Else`
- `startPos.assign`
- `endPos.assign`
- `endPos.sub`
- `uniform( 'int' ).onRenderUpdate`
- `viewVector.length().div( steps ).toVar`
- `viewVector.normalize().toVar`
- `float( 0.0 ).toVar`
- `vec3( 1 ).toVar`
- `distTravelled.addAssign`
- `material.offsetNode.mul`
- `Loop (from ../utils/LoopNode.js)`
- `startPos.add`
- `rayDir.mul`
- `cameraViewMatrix.mul`
- `vec4 (from ../tsl/TSLBase.js)`
- `linearDepthRay.assign`
- `linearDepth (from ../display/ViewportDepthNode.js)`
- `viewZToPerspectiveDepth (from ../display/ViewportDepthNode.js)`
- `linearDepth( material.depthNode ).toVar`
- `scatteringDensity.assign`
- `material.scatteringNode`
- `super.start`
- `scatteringDensity.mulAssign`
- `scatteringDensity.mul( .01 ).negate().mul( stepSize ).exp`
- `transmittance.mulAssign`
- `outgoingRayLight.addAssign`
- `transmittance.saturate().oneMinus`

**Internal Comments:**
```
// This approach dynamically changes the direction of the ray, (x5)
// prioritizing the ray from the camera to the object if it is inside the mesh, and from the object to the camera if it is far away. (x5)
// (x2)
// reduce banding (x4)
// beer's law (x2)
// move along the ray (x4)
```

<details><summary>Code</summary>

```typescript
start( builder ) {

		const { material, context } = builder;

		const startPos = property( 'vec3' );
		const endPos = property( 'vec3' );

		// This approach dynamically changes the direction of the ray,
		// prioritizing the ray from the camera to the object if it is inside the mesh, and from the object to the camera if it is far away.

		If( cameraPosition.sub( positionWorld ).length().greaterThan( modelRadius.mul( 2 ) ), () => {

			startPos.assign( cameraPosition );
			endPos.assign( positionWorld );

		} ).Else( () => {

			startPos.assign( positionWorld );
			endPos.assign( cameraPosition );

		} );

		//

		const viewVector = endPos.sub( startPos );

		const steps = uniform( 'int' ).onRenderUpdate( ( { material } ) => material.steps );
		const stepSize = viewVector.length().div( steps ).toVar();

		const rayDir = viewVector.normalize().toVar(); // TODO: toVar() should be automatic here ( in loop )

		const distTravelled = float( 0.0 ).toVar();
		const transmittance = vec3( 1 ).toVar();

		if ( material.offsetNode ) {

			// reduce banding

			distTravelled.addAssign( material.offsetNode.mul( stepSize ) );

		}

		Loop( steps, () => {

			const positionRay = startPos.add( rayDir.mul( distTravelled ) );
			const positionViewRay = cameraViewMatrix.mul( vec4( positionRay, 1 ) ).xyz;

			if ( material.depthNode !== null ) {

				linearDepthRay.assign( linearDepth( viewZToPerspectiveDepth( positionViewRay.z, cameraNear, cameraFar ) ) );

				context.sceneDepthNode = linearDepth( material.depthNode ).toVar();

			}

			context.positionWorld = positionRay;
			context.shadowPositionWorld = positionRay;
			context.positionView = positionViewRay;

			scatteringDensity.assign( 0 );

			let scatteringNode;

			if ( material.scatteringNode ) {

				scatteringNode = material.scatteringNode( {
					positionRay
				} );

			}

			super.start( builder );

			if ( scatteringNode ) {

				scatteringDensity.mulAssign( scatteringNode );

			}

			// beer's law

			const falloff = scatteringDensity.mul( .01 ).negate().mul( stepSize ).exp();
			transmittance.mulAssign( falloff );

			// move along the ray

			distTravelled.addAssign( stepSize );

		} );

		outgoingRayLight.addAssign( transmittance.saturate().oneMinus() );

	}
```
</details>

### `VolumetricLightingModel.scatteringLight(lightColor: any, builder: any): void`

**Parameters:**

- **`lightColor`** `any`
- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `If (from ../tsl/TSLBase.js)`
- `sceneDepthNode.greaterThanEqual`
- `scatteringDensity.addAssign`

<details><summary>Code</summary>

```typescript
scatteringLight( lightColor, builder ) {

		const sceneDepthNode = builder.context.sceneDepthNode;

		if ( sceneDepthNode ) {

			If( sceneDepthNode.greaterThanEqual( linearDepthRay ), () => {

				scatteringDensity.addAssign( lightColor );

			} );

		} else {

			scatteringDensity.addAssign( lightColor );

		}

	}
```
</details>

### `VolumetricLightingModel.direct({ lightNode, lightColor }: any, builder: any): void`

**Parameters:**

- **`{ lightNode, lightColor }`** `any`
- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `lightColor.xyz.toVar`
- `directLight.mulAssign`
- `this.scatteringLight`

**Internal Comments:**
```
// Ignore lights with infinite distance
// TODO: We need a viewportOpaque*() ( output, depth ) to fit with modern rendering approaches (x2)
```

<details><summary>Code</summary>

```typescript
direct( { lightNode, lightColor }, builder ) {

		// Ignore lights with infinite distance

		if ( lightNode.light.distance === undefined ) return;

		// TODO: We need a viewportOpaque*() ( output, depth ) to fit with modern rendering approaches

		const directLight = lightColor.xyz.toVar();
		directLight.mulAssign( lightNode.shadowNode ); // it no should be necessary if used in the same render pass

		this.scatteringLight( directLight, builder );

	}
```
</details>

### `VolumetricLightingModel.directRectArea({ lightColor, lightPosition, halfWidth, halfHeight }: any, builder: any): void`

**Parameters:**

- **`{ lightColor, lightPosition, halfWidth, halfHeight }`** `any`
- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `lightPosition.add( halfWidth ).sub`
- `lightPosition.sub( halfWidth ).sub`
- `lightPosition.sub( halfWidth ).add`
- `lightPosition.add( halfWidth ).add`
- `lightColor.xyz.mul( LTC_Evaluate_Volume( { P, p0, p1, p2, p3 } ) ).pow`
- `this.scatteringLight`

<details><summary>Code</summary>

```typescript
directRectArea( { lightColor, lightPosition, halfWidth, halfHeight }, builder ) {

		const p0 = lightPosition.add( halfWidth ).sub( halfHeight ); // counterclockwise; light shines in local neg z direction
		const p1 = lightPosition.sub( halfWidth ).sub( halfHeight );
		const p2 = lightPosition.sub( halfWidth ).add( halfHeight );
		const p3 = lightPosition.add( halfWidth ).add( halfHeight );

		const P = builder.context.positionView;

		const directLight = lightColor.xyz.mul( LTC_Evaluate_Volume( { P, p0, p1, p2, p3 } ) ).pow( 1.5 );

		this.scatteringLight( directLight, builder );

	}
```
</details>

### `VolumetricLightingModel.finish(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder.context.outgoingLight.assign`

<details><summary>Code</summary>

```typescript
finish( builder ) {

		builder.context.outgoingLight.assign( outgoingRayLight );

	}
```
</details>


---

## Classes

### `VolumetricLightingModel`

<details><summary>Class Code</summary>

```ts
class VolumetricLightingModel extends LightingModel {

	constructor() {

		super();

	}

	start( builder ) {

		const { material, context } = builder;

		const startPos = property( 'vec3' );
		const endPos = property( 'vec3' );

		// This approach dynamically changes the direction of the ray,
		// prioritizing the ray from the camera to the object if it is inside the mesh, and from the object to the camera if it is far away.

		If( cameraPosition.sub( positionWorld ).length().greaterThan( modelRadius.mul( 2 ) ), () => {

			startPos.assign( cameraPosition );
			endPos.assign( positionWorld );

		} ).Else( () => {

			startPos.assign( positionWorld );
			endPos.assign( cameraPosition );

		} );

		//

		const viewVector = endPos.sub( startPos );

		const steps = uniform( 'int' ).onRenderUpdate( ( { material } ) => material.steps );
		const stepSize = viewVector.length().div( steps ).toVar();

		const rayDir = viewVector.normalize().toVar(); // TODO: toVar() should be automatic here ( in loop )

		const distTravelled = float( 0.0 ).toVar();
		const transmittance = vec3( 1 ).toVar();

		if ( material.offsetNode ) {

			// reduce banding

			distTravelled.addAssign( material.offsetNode.mul( stepSize ) );

		}

		Loop( steps, () => {

			const positionRay = startPos.add( rayDir.mul( distTravelled ) );
			const positionViewRay = cameraViewMatrix.mul( vec4( positionRay, 1 ) ).xyz;

			if ( material.depthNode !== null ) {

				linearDepthRay.assign( linearDepth( viewZToPerspectiveDepth( positionViewRay.z, cameraNear, cameraFar ) ) );

				context.sceneDepthNode = linearDepth( material.depthNode ).toVar();

			}

			context.positionWorld = positionRay;
			context.shadowPositionWorld = positionRay;
			context.positionView = positionViewRay;

			scatteringDensity.assign( 0 );

			let scatteringNode;

			if ( material.scatteringNode ) {

				scatteringNode = material.scatteringNode( {
					positionRay
				} );

			}

			super.start( builder );

			if ( scatteringNode ) {

				scatteringDensity.mulAssign( scatteringNode );

			}

			// beer's law

			const falloff = scatteringDensity.mul( .01 ).negate().mul( stepSize ).exp();
			transmittance.mulAssign( falloff );

			// move along the ray

			distTravelled.addAssign( stepSize );

		} );

		outgoingRayLight.addAssign( transmittance.saturate().oneMinus() );

	}

	scatteringLight( lightColor, builder ) {

		const sceneDepthNode = builder.context.sceneDepthNode;

		if ( sceneDepthNode ) {

			If( sceneDepthNode.greaterThanEqual( linearDepthRay ), () => {

				scatteringDensity.addAssign( lightColor );

			} );

		} else {

			scatteringDensity.addAssign( lightColor );

		}

	}

	direct( { lightNode, lightColor }, builder ) {

		// Ignore lights with infinite distance

		if ( lightNode.light.distance === undefined ) return;

		// TODO: We need a viewportOpaque*() ( output, depth ) to fit with modern rendering approaches

		const directLight = lightColor.xyz.toVar();
		directLight.mulAssign( lightNode.shadowNode ); // it no should be necessary if used in the same render pass

		this.scatteringLight( directLight, builder );

	}

	directRectArea( { lightColor, lightPosition, halfWidth, halfHeight }, builder ) {

		const p0 = lightPosition.add( halfWidth ).sub( halfHeight ); // counterclockwise; light shines in local neg z direction
		const p1 = lightPosition.sub( halfWidth ).sub( halfHeight );
		const p2 = lightPosition.sub( halfWidth ).add( halfHeight );
		const p3 = lightPosition.add( halfWidth ).add( halfHeight );

		const P = builder.context.positionView;

		const directLight = lightColor.xyz.mul( LTC_Evaluate_Volume( { P, p0, p1, p2, p3 } ) ).pow( 1.5 );

		this.scatteringLight( directLight, builder );

	}

	finish( builder ) {

		builder.context.outgoingLight.assign( outgoingRayLight );

	}

}
```
</details>

#### Methods

##### `start(builder: any): void`

<details><summary>Code</summary>

```ts
start( builder ) {

		const { material, context } = builder;

		const startPos = property( 'vec3' );
		const endPos = property( 'vec3' );

		// This approach dynamically changes the direction of the ray,
		// prioritizing the ray from the camera to the object if it is inside the mesh, and from the object to the camera if it is far away.

		If( cameraPosition.sub( positionWorld ).length().greaterThan( modelRadius.mul( 2 ) ), () => {

			startPos.assign( cameraPosition );
			endPos.assign( positionWorld );

		} ).Else( () => {

			startPos.assign( positionWorld );
			endPos.assign( cameraPosition );

		} );

		//

		const viewVector = endPos.sub( startPos );

		const steps = uniform( 'int' ).onRenderUpdate( ( { material } ) => material.steps );
		const stepSize = viewVector.length().div( steps ).toVar();

		const rayDir = viewVector.normalize().toVar(); // TODO: toVar() should be automatic here ( in loop )

		const distTravelled = float( 0.0 ).toVar();
		const transmittance = vec3( 1 ).toVar();

		if ( material.offsetNode ) {

			// reduce banding

			distTravelled.addAssign( material.offsetNode.mul( stepSize ) );

		}

		Loop( steps, () => {

			const positionRay = startPos.add( rayDir.mul( distTravelled ) );
			const positionViewRay = cameraViewMatrix.mul( vec4( positionRay, 1 ) ).xyz;

			if ( material.depthNode !== null ) {

				linearDepthRay.assign( linearDepth( viewZToPerspectiveDepth( positionViewRay.z, cameraNear, cameraFar ) ) );

				context.sceneDepthNode = linearDepth( material.depthNode ).toVar();

			}

			context.positionWorld = positionRay;
			context.shadowPositionWorld = positionRay;
			context.positionView = positionViewRay;

			scatteringDensity.assign( 0 );

			let scatteringNode;

			if ( material.scatteringNode ) {

				scatteringNode = material.scatteringNode( {
					positionRay
				} );

			}

			super.start( builder );

			if ( scatteringNode ) {

				scatteringDensity.mulAssign( scatteringNode );

			}

			// beer's law

			const falloff = scatteringDensity.mul( .01 ).negate().mul( stepSize ).exp();
			transmittance.mulAssign( falloff );

			// move along the ray

			distTravelled.addAssign( stepSize );

		} );

		outgoingRayLight.addAssign( transmittance.saturate().oneMinus() );

	}
```
</details>

##### `scatteringLight(lightColor: any, builder: any): void`

<details><summary>Code</summary>

```ts
scatteringLight( lightColor, builder ) {

		const sceneDepthNode = builder.context.sceneDepthNode;

		if ( sceneDepthNode ) {

			If( sceneDepthNode.greaterThanEqual( linearDepthRay ), () => {

				scatteringDensity.addAssign( lightColor );

			} );

		} else {

			scatteringDensity.addAssign( lightColor );

		}

	}
```
</details>

##### `direct({ lightNode, lightColor }: any, builder: any): void`

<details><summary>Code</summary>

```ts
direct( { lightNode, lightColor }, builder ) {

		// Ignore lights with infinite distance

		if ( lightNode.light.distance === undefined ) return;

		// TODO: We need a viewportOpaque*() ( output, depth ) to fit with modern rendering approaches

		const directLight = lightColor.xyz.toVar();
		directLight.mulAssign( lightNode.shadowNode ); // it no should be necessary if used in the same render pass

		this.scatteringLight( directLight, builder );

	}
```
</details>

##### `directRectArea({ lightColor, lightPosition, halfWidth, halfHeight }: any, builder: any): void`

<details><summary>Code</summary>

```ts
directRectArea( { lightColor, lightPosition, halfWidth, halfHeight }, builder ) {

		const p0 = lightPosition.add( halfWidth ).sub( halfHeight ); // counterclockwise; light shines in local neg z direction
		const p1 = lightPosition.sub( halfWidth ).sub( halfHeight );
		const p2 = lightPosition.sub( halfWidth ).add( halfHeight );
		const p3 = lightPosition.add( halfWidth ).add( halfHeight );

		const P = builder.context.positionView;

		const directLight = lightColor.xyz.mul( LTC_Evaluate_Volume( { P, p0, p1, p2, p3 } ) ).pow( 1.5 );

		this.scatteringLight( directLight, builder );

	}
```
</details>

##### `finish(builder: any): void`

<details><summary>Code</summary>

```ts
finish( builder ) {

		builder.context.outgoingLight.assign( outgoingRayLight );

	}
```
</details>


---