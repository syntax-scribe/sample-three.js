[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Water2Mesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 2 |
| 📦 Imports | 27 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/Water2Mesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three/webgpu` |
| `Mesh` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `Vector3` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `Fn` | `three/tsl` |
| `vec2` | `three/tsl` |
| `viewportSafeUV` | `three/tsl` |
| `viewportSharedTexture` | `three/tsl` |
| `reflector` | `three/tsl` |
| `pow` | `three/tsl` |
| `float` | `three/tsl` |
| `abs` | `three/tsl` |
| `texture` | `three/tsl` |
| `uniform` | `three/tsl` |
| `vec4` | `three/tsl` |
| `cameraPosition` | `three/tsl` |
| `positionWorld` | `three/tsl` |
| `uv` | `three/tsl` |
| `mix` | `three/tsl` |
| `vec3` | `three/tsl` |
| `normalize` | `three/tsl` |
| `max` | `three/tsl` |
| `dot` | `three/tsl` |
| `screenUV` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `new NodeMaterial()` | ✗ |
| `flowMapOffset0` | `any` | let/var | `this.flowConfig.x` | ✗ |
| `flowMapOffset1` | `any` | let/var | `this.flowConfig.y` | ✗ |
| `halfCycle` | `any` | let/var | `this.flowConfig.z` | ✗ |
| `flow` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `WaterNode.updateFlow(delta: any): void`

**Parameters:**

- **`delta`** `any`

**Returns:** `void`

**Internal Comments:**
```
// Important: The distance between offsets should be always the value of "halfCycle".
// Moreover, both offsets should be in the range of [ 0, cycle ].
// This approach ensures a smooth water flow and avoids "reset" effects.
```

<details><summary>Code</summary>

```typescript
updateFlow( delta ) {

		this.flowConfig.value.x += this.flowSpeed.value * delta; // flowMapOffset0
		this.flowConfig.value.y = this.flowConfig.value.x + this._halfCycle; // flowMapOffset1

		// Important: The distance between offsets should be always the value of "halfCycle".
		// Moreover, both offsets should be in the range of [ 0, cycle ].
		// This approach ensures a smooth water flow and avoids "reset" effects.

		if ( this.flowConfig.value.x >= this._cycle ) {

			this.flowConfig.value.x = 0;
			this.flowConfig.value.y = this._halfCycle;

		} else if ( this.flowConfig.value.y >= this._cycle ) {

			this.flowConfig.value.y = this.flowConfig.value.y - this._cycle;

		}

		this.flowConfig.value.z = this._halfCycle;

	}
```
</details>

### `WaterNode.updateBefore(frame: any): void`

**Parameters:**

- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `this.updateFlow`

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		this.updateFlow( frame.deltaTime );

	}
```
</details>

### `WaterNode.setup(): any`

**Returns:** `any`

**Calls:**

- `complex_call_3302`

**Internal Comments:**
```
// sample normal maps (distort uvs with flowdata) (x2)
// linear interpolate to get the final normal color (x2)
// calculate normal vector (x2)
// calculate the fresnel term to blend reflection and refraction maps (x2)
// reflector, refractor (x2)
// calculate final uv coords
```

<details><summary>Code</summary>

```typescript
setup() {

		const outputNode = Fn( () => {

			const flowMapOffset0 = this.flowConfig.x;
			const flowMapOffset1 = this.flowConfig.y;
			const halfCycle = this.flowConfig.z;

			const toEye = normalize( cameraPosition.sub( positionWorld ) );

			let flow;

			if ( this._USE_FLOW === true ) {

				flow = this.flowMap.rg.mul( 2 ).sub( 1 );

			} else {

				flow = vec2( this.flowDirection.x, this.flowDirection.y );

			}

			flow.x.mulAssign( - 1 );

			// sample normal maps (distort uvs with flowdata)

			const uvs = uv();

			const normalUv0 = uvs.mul( this.scale ).add( flow.mul( flowMapOffset0 ) );
			const normalUv1 = uvs.mul( this.scale ).add( flow.mul( flowMapOffset1 ) );

			const normalColor0 = this.normalMap0.sample( normalUv0 );
			const normalColor1 = this.normalMap1.sample( normalUv1 );

			// linear interpolate to get the final normal color
			const flowLerp = abs( halfCycle.sub( flowMapOffset0 ) ).div( halfCycle );
			const normalColor = mix( normalColor0, normalColor1, flowLerp );

			// calculate normal vector
			const normal = normalize( vec3( normalColor.r.mul( 2 ).sub( 1 ), normalColor.b, normalColor.g.mul( 2 ).sub( 1 ) ) );

			// calculate the fresnel term to blend reflection and refraction maps
			const theta = max( dot( toEye, normal ), 0 );
			const reflectance = pow( float( 1.0 ).sub( theta ), 5.0 ).mul( float( 1.0 ).sub( this.reflectivity ) ).add( this.reflectivity );

			// reflector, refractor

			const offset = normal.xz.mul( 0.05 ).toVar();

			const reflectionSampler = reflector();
			this.waterBody.add( reflectionSampler.target );
			reflectionSampler.uvNode = reflectionSampler.uvNode.add( offset );

			const refractorUV = screenUV.add( offset );
			const refractionSampler = viewportSharedTexture( viewportSafeUV( refractorUV ) );

			// calculate final uv coords

			return vec4( this.color, 1.0 ).mul( mix( refractionSampler, reflectionSampler, reflectance ) );

		} )();

		return outputNode;

	}
```
</details>


---

## Classes

### `WaterMesh`

<details><summary>Class Code</summary>

```ts
class WaterMesh extends Mesh {

	/**
	 * Constructs a new water mesh.
	 *
	 * @param {BufferGeometry} geometry - The water's geometry.
	 * @param {module:Water2~Options} [options] - The configuration options.
	 */
	constructor( geometry, options = {} ) {

		const material = new NodeMaterial();
		material.transparent = true;

		super( geometry, material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWater = true;

		material.colorNode = new WaterNode( options, this );

	}

}
```
</details>

### `WaterNode`

<details><summary>Class Code</summary>

```ts
class WaterNode extends TempNode {

	constructor( options, waterBody ) {

		super( 'vec4' );

		this.waterBody = waterBody;

		this.normalMap0 = texture( options.normalMap0 );
		this.normalMap1 = texture( options.normalMap1 );
		this.flowMap = texture( options.flowMap !== undefined ? options.flowMap : null );

		this.color = uniform( options.color !== undefined ? new Color( options.color ) : new Color( 0xffffff ) );
		this.flowDirection = uniform( options.flowDirection !== undefined ? options.flowDirection : new Vector2( 1, 0 ) );
		this.flowSpeed = uniform( options.flowSpeed !== undefined ? options.flowSpeed : 0.03 );
		this.reflectivity = uniform( options.reflectivity !== undefined ? options.reflectivity : 0.02 );
		this.scale = uniform( options.scale !== undefined ? options.scale : 1 );
		this.flowConfig = uniform( new Vector3() );

		this.updateBeforeType = NodeUpdateType.RENDER;

		this._cycle = 0.15; // a cycle of a flow map phase
		this._halfCycle = this._cycle * 0.5;

		this._USE_FLOW = options.flowMap !== undefined;

	}

	updateFlow( delta ) {

		this.flowConfig.value.x += this.flowSpeed.value * delta; // flowMapOffset0
		this.flowConfig.value.y = this.flowConfig.value.x + this._halfCycle; // flowMapOffset1

		// Important: The distance between offsets should be always the value of "halfCycle".
		// Moreover, both offsets should be in the range of [ 0, cycle ].
		// This approach ensures a smooth water flow and avoids "reset" effects.

		if ( this.flowConfig.value.x >= this._cycle ) {

			this.flowConfig.value.x = 0;
			this.flowConfig.value.y = this._halfCycle;

		} else if ( this.flowConfig.value.y >= this._cycle ) {

			this.flowConfig.value.y = this.flowConfig.value.y - this._cycle;

		}

		this.flowConfig.value.z = this._halfCycle;

	}

	updateBefore( frame ) {

		this.updateFlow( frame.deltaTime );

	}

	setup() {

		const outputNode = Fn( () => {

			const flowMapOffset0 = this.flowConfig.x;
			const flowMapOffset1 = this.flowConfig.y;
			const halfCycle = this.flowConfig.z;

			const toEye = normalize( cameraPosition.sub( positionWorld ) );

			let flow;

			if ( this._USE_FLOW === true ) {

				flow = this.flowMap.rg.mul( 2 ).sub( 1 );

			} else {

				flow = vec2( this.flowDirection.x, this.flowDirection.y );

			}

			flow.x.mulAssign( - 1 );

			// sample normal maps (distort uvs with flowdata)

			const uvs = uv();

			const normalUv0 = uvs.mul( this.scale ).add( flow.mul( flowMapOffset0 ) );
			const normalUv1 = uvs.mul( this.scale ).add( flow.mul( flowMapOffset1 ) );

			const normalColor0 = this.normalMap0.sample( normalUv0 );
			const normalColor1 = this.normalMap1.sample( normalUv1 );

			// linear interpolate to get the final normal color
			const flowLerp = abs( halfCycle.sub( flowMapOffset0 ) ).div( halfCycle );
			const normalColor = mix( normalColor0, normalColor1, flowLerp );

			// calculate normal vector
			const normal = normalize( vec3( normalColor.r.mul( 2 ).sub( 1 ), normalColor.b, normalColor.g.mul( 2 ).sub( 1 ) ) );

			// calculate the fresnel term to blend reflection and refraction maps
			const theta = max( dot( toEye, normal ), 0 );
			const reflectance = pow( float( 1.0 ).sub( theta ), 5.0 ).mul( float( 1.0 ).sub( this.reflectivity ) ).add( this.reflectivity );

			// reflector, refractor

			const offset = normal.xz.mul( 0.05 ).toVar();

			const reflectionSampler = reflector();
			this.waterBody.add( reflectionSampler.target );
			reflectionSampler.uvNode = reflectionSampler.uvNode.add( offset );

			const refractorUV = screenUV.add( offset );
			const refractionSampler = viewportSharedTexture( viewportSafeUV( refractorUV ) );

			// calculate final uv coords

			return vec4( this.color, 1.0 ).mul( mix( refractionSampler, reflectionSampler, reflectance ) );

		} )();

		return outputNode;

	}

}
```
</details>

#### Methods

##### `updateFlow(delta: any): void`

<details><summary>Code</summary>

```ts
updateFlow( delta ) {

		this.flowConfig.value.x += this.flowSpeed.value * delta; // flowMapOffset0
		this.flowConfig.value.y = this.flowConfig.value.x + this._halfCycle; // flowMapOffset1

		// Important: The distance between offsets should be always the value of "halfCycle".
		// Moreover, both offsets should be in the range of [ 0, cycle ].
		// This approach ensures a smooth water flow and avoids "reset" effects.

		if ( this.flowConfig.value.x >= this._cycle ) {

			this.flowConfig.value.x = 0;
			this.flowConfig.value.y = this._halfCycle;

		} else if ( this.flowConfig.value.y >= this._cycle ) {

			this.flowConfig.value.y = this.flowConfig.value.y - this._cycle;

		}

		this.flowConfig.value.z = this._halfCycle;

	}
```
</details>

##### `updateBefore(frame: any): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		this.updateFlow( frame.deltaTime );

	}
```
</details>

##### `setup(): any`

<details><summary>Code</summary>

```ts
setup() {

		const outputNode = Fn( () => {

			const flowMapOffset0 = this.flowConfig.x;
			const flowMapOffset1 = this.flowConfig.y;
			const halfCycle = this.flowConfig.z;

			const toEye = normalize( cameraPosition.sub( positionWorld ) );

			let flow;

			if ( this._USE_FLOW === true ) {

				flow = this.flowMap.rg.mul( 2 ).sub( 1 );

			} else {

				flow = vec2( this.flowDirection.x, this.flowDirection.y );

			}

			flow.x.mulAssign( - 1 );

			// sample normal maps (distort uvs with flowdata)

			const uvs = uv();

			const normalUv0 = uvs.mul( this.scale ).add( flow.mul( flowMapOffset0 ) );
			const normalUv1 = uvs.mul( this.scale ).add( flow.mul( flowMapOffset1 ) );

			const normalColor0 = this.normalMap0.sample( normalUv0 );
			const normalColor1 = this.normalMap1.sample( normalUv1 );

			// linear interpolate to get the final normal color
			const flowLerp = abs( halfCycle.sub( flowMapOffset0 ) ).div( halfCycle );
			const normalColor = mix( normalColor0, normalColor1, flowLerp );

			// calculate normal vector
			const normal = normalize( vec3( normalColor.r.mul( 2 ).sub( 1 ), normalColor.b, normalColor.g.mul( 2 ).sub( 1 ) ) );

			// calculate the fresnel term to blend reflection and refraction maps
			const theta = max( dot( toEye, normal ), 0 );
			const reflectance = pow( float( 1.0 ).sub( theta ), 5.0 ).mul( float( 1.0 ).sub( this.reflectivity ) ).add( this.reflectivity );

			// reflector, refractor

			const offset = normal.xz.mul( 0.05 ).toVar();

			const reflectionSampler = reflector();
			this.waterBody.add( reflectionSampler.target );
			reflectionSampler.uvNode = reflectionSampler.uvNode.add( offset );

			const refractorUV = screenUV.add( offset );
			const refractionSampler = viewportSharedTexture( viewportSafeUV( refractorUV ) );

			// calculate final uv coords

			return vec4( this.color, 1.0 ).mul( mix( refractionSampler, reflectionSampler, reflectance ) );

		} )();

		return outputNode;

	}
```
</details>


---