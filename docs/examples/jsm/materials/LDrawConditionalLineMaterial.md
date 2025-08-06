[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LDrawConditionalLineMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/materials/LDrawConditionalLineMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsLib` | `three` |
| `UniformsUtils` | `three` |


---

## Functions

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms.opacity.value;

				}
```
</details>

### `set(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( value ) {

					this.uniforms.opacity.value = value;

				}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms.opacity.value;

				}
```
</details>

### `set(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( value ) {

					this.uniforms.opacity.value = value;

				}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms.diffuse.value;

				}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms.diffuse.value;

				}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms.opacity.value;

				}
```
</details>

### `set(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( value ) {

					this.uniforms.opacity.value = value;

				}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms.opacity.value;

				}
```
</details>

### `set(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( value ) {

					this.uniforms.opacity.value = value;

				}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms.diffuse.value;

				}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return this.uniforms.diffuse.value;

				}
```
</details>


---

## Classes

### `LDrawConditionalLineMaterial`

<details><summary>Class Code</summary>

```ts
class LDrawConditionalLineMaterial extends ShaderMaterial {

	static get type() {

		return 'LDrawConditionalLineMaterial';

	}

	/**
	 * Constructs a new conditional line material.
	 *
	 * @param {Object} [parameters] - An object with one or more properties
	 * defining the material's appearance. Any property of the material
	 * (including any property from inherited materials) can be passed
	 * in here. Color values can be passed any type of value accepted
	 * by {@link Color#set}.
	 */
	constructor( parameters ) {

		super( {

			uniforms: UniformsUtils.merge( [
				UniformsLib.fog,
				{
					diffuse: {
						value: new Color()
					},
					opacity: {
						value: 1.0
					}
				}
			] ),

			vertexShader: /* glsl */`
				attribute vec3 control0;
				attribute vec3 control1;
				attribute vec3 direction;
				varying float discardFlag;

				#include <common>
				#include <color_pars_vertex>
				#include <fog_pars_vertex>
				#include <logdepthbuf_pars_vertex>
				#include <clipping_planes_pars_vertex>
				void main() {
					#include <color_vertex>

					vec4 mvPosition = modelViewMatrix * vec4( position, 1.0 );
					gl_Position = projectionMatrix * mvPosition;

					// Transform the line segment ends and control points into camera clip space
					vec4 c0 = projectionMatrix * modelViewMatrix * vec4( control0, 1.0 );
					vec4 c1 = projectionMatrix * modelViewMatrix * vec4( control1, 1.0 );
					vec4 p0 = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );
					vec4 p1 = projectionMatrix * modelViewMatrix * vec4( position + direction, 1.0 );

					c0.xy /= c0.w;
					c1.xy /= c1.w;
					p0.xy /= p0.w;
					p1.xy /= p1.w;

					// Get the direction of the segment and an orthogonal vector
					vec2 dir = p1.xy - p0.xy;
					vec2 norm = vec2( -dir.y, dir.x );

					// Get control point directions from the line
					vec2 c0dir = c0.xy - p1.xy;
					vec2 c1dir = c1.xy - p1.xy;

					// If the vectors to the controls points are pointed in different directions away
					// from the line segment then the line should not be drawn.
					float d0 = dot( normalize( norm ), normalize( c0dir ) );
					float d1 = dot( normalize( norm ), normalize( c1dir ) );
					discardFlag = float( sign( d0 ) != sign( d1 ) );

					#include <logdepthbuf_vertex>
					#include <clipping_planes_vertex>
					#include <fog_vertex>
				}
			`,

			fragmentShader: /* glsl */`
			uniform vec3 diffuse;
			uniform float opacity;
			varying float discardFlag;

			#include <common>
			#include <color_pars_fragment>
			#include <fog_pars_fragment>
			#include <logdepthbuf_pars_fragment>
			#include <clipping_planes_pars_fragment>
			void main() {

				if ( discardFlag > 0.5 ) discard;

				#include <clipping_planes_fragment>
				vec3 outgoingLight = vec3( 0.0 );
				vec4 diffuseColor = vec4( diffuse, opacity );
				#include <logdepthbuf_fragment>
				#include <color_fragment>
				outgoingLight = diffuseColor.rgb; // simple shader
				gl_FragColor = vec4( outgoingLight, diffuseColor.a );
				#include <tonemapping_fragment>
				#include <colorspace_fragment>
				#include <fog_fragment>
				#include <premultiplied_alpha_fragment>
			}
			`,

		} );

		Object.defineProperties( this, {

			/**
			 * The material's opacity.
			 *
			 * @name LDrawConditionalLineMaterial#opacity
			 * @type {number}
			 * @default 1
			 */
			opacity: {
				get: function () {

					return this.uniforms.opacity.value;

				},

				set: function ( value ) {

					this.uniforms.opacity.value = value;

				}
			},

			/**
			 * The material's color.
			 *
			 * @name LDrawConditionalLineMaterial#color
			 * @type {Color}
			 * @default (1,1,1)
			 */
			color: {
				get: function () {

					return this.uniforms.diffuse.value;

				}
			}

		} );

		this.setValues( parameters );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLDrawConditionalLineMaterial = true;

	}

}
```
</details>


---