[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WaterMesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 26 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/WaterMesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three/webgpu` |
| `Mesh` | `three/webgpu` |
| `Vector3` | `three/webgpu` |
| `MeshLambertNodeMaterial` | `three/webgpu` |
| `Fn` | `three/tsl` |
| `add` | `three/tsl` |
| `cameraPosition` | `three/tsl` |
| `div` | `three/tsl` |
| `normalize` | `three/tsl` |
| `positionWorld` | `three/tsl` |
| `sub` | `three/tsl` |
| `time` | `three/tsl` |
| `texture` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `max` | `three/tsl` |
| `dot` | `three/tsl` |
| `reflect` | `three/tsl` |
| `pow` | `three/tsl` |
| `length` | `three/tsl` |
| `float` | `three/tsl` |
| `uniform` | `three/tsl` |
| `reflector` | `three/tsl` |
| `mul` | `three/tsl` |
| `mix` | `three/tsl` |
| `diffuseColor` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `new MeshLambertNodeMaterial()` | ✗ |
| `offset` | `any` | let/var | `time` | ✗ |


---

## Classes

### `WaterMesh`

<details><summary>Class Code</summary>

```ts
class WaterMesh extends Mesh {

	/**
	 * Constructs a new water mesh.
	 *
	 * @param {BufferGeometry} geometry - The water mesh's geometry.
	 * @param {WaterMesh~Options} [options] - The configuration options.
	 */
	constructor( geometry, options ) {

		const material = new MeshLambertNodeMaterial();

		super( geometry, material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWaterMesh = true;

		/**
		 * The effect's resolution scale.
		 *
		 * @type {number}
		 * @default 0.5
		 */
		this.resolution = options.resolution !== undefined ? options.resolution : 0.5;

		// Uniforms

		/**
		 * The water's normal map.
		 *
		 * @type {TextureNode}
		 */
		this.waterNormals = texture( options.waterNormals );

		/**
		 * The alpha value.
		 *
		 * @type {UniformNode<float>}
		 * @default 1
		 */
		this.alpha = uniform( options.alpha !== undefined ? options.alpha : 1.0 );

		/**
		 * The size value.
		 *
		 * @type {UniformNode<float>}
		 * @default 1
		 */
		this.size = uniform( options.size !== undefined ? options.size : 1.0 );

		/**
		 * The sun color.
		 *
		 * @type {UniformNode<color>}
		 * @default 0xffffff
		 */
		this.sunColor = uniform( new Color( options.sunColor !== undefined ? options.sunColor : 0xffffff ) );

		/**
		 * The sun direction.
		 *
		 * @type {UniformNode<vec3>}
		 * @default (0.70707,0.70707,0.0)
		 */
		this.sunDirection = uniform( options.sunDirection !== undefined ? options.sunDirection : new Vector3( 0.70707, 0.70707, 0.0 ) );

		/**
		 * The water color.
		 *
		 * @type {UniformNode<color>}
		 * @default 0x7f7f7f
		 */
		this.waterColor = uniform( new Color( options.waterColor !== undefined ? options.waterColor : 0x7f7f7f ) );

		/**
		 * The distortion scale.
		 *
		 * @type {UniformNode<float>}
		 * @default 20
		 */
		this.distortionScale = uniform( options.distortionScale !== undefined ? options.distortionScale : 20.0 );

		// TSL

		const getNoise = Fn( ( [ uv ] ) => {

			const offset = time;

			const uv0 = add( div( uv, 103 ), vec2( div( offset, 17 ), div( offset, 29 ) ) ).toVar();
			const uv1 = div( uv, 107 ).sub( vec2( div( offset, - 19 ), div( offset, 31 ) ) ).toVar();
			const uv2 = add( div( uv, vec2( 8907.0, 9803.0 ) ), vec2( div( offset, 101 ), div( offset, 97 ) ) ).toVar();
			const uv3 = sub( div( uv, vec2( 1091.0, 1027.0 ) ), vec2( div( offset, 109 ), div( offset, - 113 ) ) ).toVar();

			const sample0 = this.waterNormals.sample( uv0 );
			const sample1 = this.waterNormals.sample( uv1 );
			const sample2 = this.waterNormals.sample( uv2 );
			const sample3 = this.waterNormals.sample( uv3 );

			const noise = sample0.add( sample1 ).add( sample2 ).add( sample3 );

			return noise.mul( 0.5 ).sub( 1 );

		} );

		const noise = getNoise( positionWorld.xz.mul( this.size ) );
		const surfaceNormal = normalize( noise.xzy.mul( 1.5, 1.0, 1.5 ) );

		const worldToEye = cameraPosition.sub( positionWorld );
		const eyeDirection = normalize( worldToEye );

		const reflection = normalize( reflect( this.sunDirection.negate(), surfaceNormal ) );
		const direction = max( 0.0, dot( eyeDirection, reflection ) );
		const specularLight = pow( direction, 100 ).mul( this.sunColor ).mul( 2.0 );
		const diffuseLight = max( dot( this.sunDirection, surfaceNormal ), 0.0 ).mul( this.sunColor ).mul( 0.5 );

		const distance = length( worldToEye );

		const distortion = surfaceNormal.xz.mul( float( 0.001 ).add( float( 1.0 ).div( distance ) ) ).mul( this.distortionScale );

		// Material

		material.transparent = true;

		material.opacityNode = this.alpha;

		material.receivedShadowPositionNode = positionWorld.add( distortion );

		material.setupOutgoingLight = () => diffuseColor.rgb; // backwards compatibility

		material.colorNode = Fn( () => {

			const mirrorSampler = reflector();
			mirrorSampler.uvNode = mirrorSampler.uvNode.add( distortion );
			mirrorSampler.resolution = this.resolution;

			this.add( mirrorSampler.target );

			const theta = max( dot( eyeDirection, surfaceNormal ), 0.0 );
			const rf0 = float( 0.3 );
			const reflectance = mul( pow( float( 1.0 ).sub( theta ), 5.0 ), float( 1.0 ).sub( rf0 ) ).add( rf0 );
			const scatter = max( 0.0, dot( surfaceNormal, eyeDirection ) ).mul( this.waterColor );
			const albedo = mix( this.sunColor.mul( diffuseLight ).mul( 0.3 ).add( scatter ), mirrorSampler.rgb.mul( specularLight ).add( mirrorSampler.rgb.mul( 0.9 ) ).add( vec3( 0.1 ) ), reflectance );

			return albedo;

		} )();

	}

}
```
</details>


---