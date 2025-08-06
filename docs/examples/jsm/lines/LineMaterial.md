[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LineMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/lines/LineMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ShaderLib` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsLib` | `three` |
| `UniformsUtils` | `three` |
| `Vector2` | `three` |


---

## Classes

### `LineMaterial`

<details><summary>Class Code</summary>

```ts
class LineMaterial extends ShaderMaterial {

	/**
	 * Constructs a new line segments geometry.
	 *
	 * @param {Object} [parameters] - An object with one or more properties
	 * defining the material's appearance. Any property of the material
	 * (including any property from inherited materials) can be passed
	 * in here. Color values can be passed any type of value accepted
	 * by {@link Color#set}.
	 */
	constructor( parameters ) {

		super( {

			type: 'LineMaterial',
			uniforms: UniformsUtils.clone( ShaderLib[ 'line' ].uniforms ),

			vertexShader: ShaderLib[ 'line' ].vertexShader,
			fragmentShader: ShaderLib[ 'line' ].fragmentShader,

			clipping: true // required for clipping support

		} );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLineMaterial = true;

		this.setValues( parameters );

	}

	/**
	 * The material's color.
	 *
	 * @type {Color}
	 * @default (1,1,1)
	 */
	get color() {

		return this.uniforms.diffuse.value;

	}

	set color( value ) {

		this.uniforms.diffuse.value = value;

	}

	/**
	 * Whether the material's sizes (width, dash gaps) are in world units.
	 *
	 * @type {boolean}
	 * @default false
	 */
	get worldUnits() {

		return 'WORLD_UNITS' in this.defines;

	}

	set worldUnits( value ) {

		if ( value === true ) {

			this.defines.WORLD_UNITS = '';

		} else {

			delete this.defines.WORLD_UNITS;

		}

	}

	/**
	 * Controls line thickness in CSS pixel units when `worldUnits` is `false` (default),
	 * or in world units when `worldUnits` is `true`.
	 *
	 * @type {number}
	 * @default 1
	 */
	get linewidth() {

		return this.uniforms.linewidth.value;

	}

	set linewidth( value ) {

		if ( ! this.uniforms.linewidth ) return;
		this.uniforms.linewidth.value = value;

	}

	/**
	 * Whether the line is dashed, or solid.
	 *
	 * @type {boolean}
	 * @default false
	 */
	get dashed() {

		return 'USE_DASH' in this.defines;

	}

	set dashed( value ) {

		if ( ( value === true ) !== this.dashed ) {

			this.needsUpdate = true;

		}

		if ( value === true ) {

			this.defines.USE_DASH = '';

		} else {

			delete this.defines.USE_DASH;

		}

	}

	/**
	 * The scale of the dashes and gaps.
	 *
	 * @type {number}
	 * @default 1
	 */
	get dashScale() {

		return this.uniforms.dashScale.value;

	}

	set dashScale( value ) {

		this.uniforms.dashScale.value = value;

	}

	/**
	 * The size of the dash.
	 *
	 * @type {number}
	 * @default 1
	 */
	get dashSize() {

		return this.uniforms.dashSize.value;

	}

	set dashSize( value ) {

		this.uniforms.dashSize.value = value;

	}

	/**
	 * Where in the dash cycle the dash starts.
	 *
	 * @type {number}
	 * @default 0
	 */
	get dashOffset() {

		return this.uniforms.dashOffset.value;

	}

	set dashOffset( value ) {

		this.uniforms.dashOffset.value = value;

	}

	/**
	 * The size of the gap.
	 *
	 * @type {number}
	 * @default 0
	 */
	get gapSize() {

		return this.uniforms.gapSize.value;

	}

	set gapSize( value ) {

		this.uniforms.gapSize.value = value;

	}

	/**
	 * The opacity.
	 *
	 * @type {number}
	 * @default 1
	 */
	get opacity() {

		return this.uniforms.opacity.value;

	}

	set opacity( value ) {

		if ( ! this.uniforms ) return;
		this.uniforms.opacity.value = value;

	}

	/**
	 * The size of the viewport, in screen pixels. This must be kept updated to make
	 * screen-space rendering accurate.The `LineSegments2.onBeforeRender` callback
	 * performs the update for visible objects.
	 *
	 * @type {Vector2}
	 */
	get resolution() {

		return this.uniforms.resolution.value;

	}

	set resolution( value ) {

		this.uniforms.resolution.value.copy( value );

	}

	/**
	 * Whether to use alphaToCoverage or not. When enabled, this can improve the
	 * anti-aliasing of line edges when using MSAA.
	 *
	 * @type {boolean}
	 */
	get alphaToCoverage() {

		return 'USE_ALPHA_TO_COVERAGE' in this.defines;

	}

	set alphaToCoverage( value ) {

		if ( ! this.defines ) return;

		if ( ( value === true ) !== this.alphaToCoverage ) {

			this.needsUpdate = true;

		}

		if ( value === true ) {

			this.defines.USE_ALPHA_TO_COVERAGE = '';

		} else {

			delete this.defines.USE_ALPHA_TO_COVERAGE;

		}

	}

}
```
</details>


---