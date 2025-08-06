[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Line2NodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 28 |
| 📊 Variables & Constants | 13 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/Line2NodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `dashSize` | `../../nodes/core/PropertyNode.js` |
| `gapSize` | `../../nodes/core/PropertyNode.js` |
| `varyingProperty` | `../../nodes/core/PropertyNode.js` |
| `attribute` | `../../nodes/core/AttributeNode.js` |
| `cameraProjectionMatrix` | `../../nodes/accessors/Camera.js` |
| `materialColor` | `../../nodes/accessors/MaterialNode.js` |
| `materialLineScale` | `../../nodes/accessors/MaterialNode.js` |
| `materialLineDashSize` | `../../nodes/accessors/MaterialNode.js` |
| `materialLineGapSize` | `../../nodes/accessors/MaterialNode.js` |
| `materialLineDashOffset` | `../../nodes/accessors/MaterialNode.js` |
| `materialLineWidth` | `../../nodes/accessors/MaterialNode.js` |
| `materialOpacity` | `../../nodes/accessors/MaterialNode.js` |
| `modelViewMatrix` | `../../nodes/accessors/ModelNode.js` |
| `positionGeometry` | `../../nodes/accessors/Position.js` |
| `mix` | `../../nodes/math/MathNode.js` |
| `smoothstep` | `../../nodes/math/MathNode.js` |
| `Fn` | `../../nodes/tsl/TSLBase.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `vec2` | `../../nodes/tsl/TSLBase.js` |
| `vec3` | `../../nodes/tsl/TSLBase.js` |
| `vec4` | `../../nodes/tsl/TSLBase.js` |
| `If` | `../../nodes/tsl/TSLBase.js` |
| `uv` | `../../nodes/accessors/UV.js` |
| `viewport` | `../../nodes/display/ScreenNode.js` |
| `viewportSharedTexture` | `../../nodes/display/ViewportSharedTextureNode.js` |
| `LineDashedMaterial` | `../LineDashedMaterial.js` |
| `NoBlending` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `LineDashedMaterial` | let/var | `new LineDashedMaterial()` | ✗ |
| `useAlphaToCoverage` | `boolean` | let/var | `this._useAlphaToCoverage` | ✗ |
| `useColor` | `boolean` | let/var | `this.useColor` | ✗ |
| `useDash` | `any` | let/var | `this._useDash` | ✗ |
| `useWorldUnits` | `boolean` | let/var | `this._useWorldUnits` | ✗ |
| `dashScaleNode` | `any` | let/var | `this.dashScaleNode ? float( this.dashScaleNode ) : materialLineScale` | ✗ |
| `offsetNode` | `any` | let/var | `this.offsetNode ? float( this.offsetNode ) : materialLineDashOffset` | ✗ |
| `dashSizeNode` | `any` | let/var | `this.dashSizeNode ? float( this.dashSizeNode ) : materialLineDashSize` | ✗ |
| `gapSizeNode` | `any` | let/var | `this.gapSizeNode ? float( this.gapSizeNode ) : materialLineGapSize` | ✗ |
| `a` | `any` | let/var | `vUv.x` | ✗ |
| `a` | `any` | let/var | `vUv.x` | ✗ |
| `lineColorNode` | `any` | let/var | `*not shown*` | ✗ |
| `opacityNode` | `any` | let/var | `this.opacityNode ? float( this.opacityNode ) : materialOpacity` | ✗ |


---

## Functions

### `Line2NodeMaterial.setup(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Setups the vertex and fragment stage of this node material.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `Fn( ( { start, end } ) => {

			const a = cameraProjectionMatrix.element( 2 ).element( 2 ); // 3nd entry in 3th column
			const b = cameraProjectionMatrix.element( 3 ).element( 2 ); // 3nd entry in 4th column
			const nearEstimate = b.mul( - 0.5 ).div( a );

			const alpha = nearEstimate.sub( start.z ).div( end.z.sub( start.z ) );

			return vec4( mix( start.xyz, end.xyz, alpha ), end.w );

		} ).setLayout`
- `complex_call_3881`
- `Fn (from ../../nodes/tsl/TSLBase.js)`
- `p1.sub`
- `p4.sub`
- `p2.sub`
- `p13.dot`
- `p43.dot`
- `p21.dot`
- `d2121.mul( d4343 ).sub`
- `d4321.mul`
- `d1343.mul( d4321 ).sub`
- `d1321.mul`
- `numer.div( denom ).clamp`
- `d1343.add( d4321.mul( mua ) ).div( d4343 ).clamp`
- `vec2 (from ../../nodes/tsl/TSLBase.js)`
- `complex_call_9591`
- `float (from ../../nodes/tsl/TSLBase.js)`
- `vec4 (from ../../nodes/tsl/TSLBase.js)`
- `this.colorNode.rgb.mul( opacityNode ).add`
- `viewportSharedTexture().rgb.mul`
- `opacityNode.oneMinus`
- `super.setup`

**Internal Comments:**
```
// camera space (x2)
// special case for perspective projection, and segments that terminate either in, or behind, the camera plane (x2)
// clearly the gpu firmware has a way of addressing this issue when projecting into ndc space (x2)
// but we need to perform ndc-space calculations in the shader, so we must address this issue directly (x2)
// perhaps there is a more elegant solution -- WestLangley (x2)
// clip space (x2)
// ndc space (x2)
// direction (x2)
// account for clip-space aspect ratio (x5)
// get the offset direction as perpendicular to the view vector (x2)
// height offset (x2)
// don't extend the line if we're rendering dashes because we
// won't be rendering the endcaps
// cap extension (x4)
// add width to the box (x4)
// endcaps (x8)
// project the worldpos (x4)
// shift the depth of the projected points so the line (x2)
// segments overlap neatly (x2)
// undo aspect ratio adjustment (x5)
// sign flip (x4)
// adjust for linewidth (x4)
// adjust for clip-space to screen-space conversion // maybe resolution should be based on viewport ... (x4)
// select end (x4)
// back to clip space (x4)
// Find the closest points on the view ray and the line segment (x2)
// round endcaps
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const { renderer } = builder;

		const useAlphaToCoverage = this._useAlphaToCoverage;
		const useColor = this.useColor;
		const useDash = this._useDash;
		const useWorldUnits = this._useWorldUnits;

		const trimSegment = Fn( ( { start, end } ) => {

			const a = cameraProjectionMatrix.element( 2 ).element( 2 ); // 3nd entry in 3th column
			const b = cameraProjectionMatrix.element( 3 ).element( 2 ); // 3nd entry in 4th column
			const nearEstimate = b.mul( - 0.5 ).div( a );

			const alpha = nearEstimate.sub( start.z ).div( end.z.sub( start.z ) );

			return vec4( mix( start.xyz, end.xyz, alpha ), end.w );

		} ).setLayout( {
			name: 'trimSegment',
			type: 'vec4',
			inputs: [
				{ name: 'start', type: 'vec4' },
				{ name: 'end', type: 'vec4' }
			]
		} );

		this.vertexNode = Fn( () => {

			const instanceStart = attribute( 'instanceStart' );
			const instanceEnd = attribute( 'instanceEnd' );

			// camera space

			const start = vec4( modelViewMatrix.mul( vec4( instanceStart, 1.0 ) ) ).toVar( 'start' );
			const end = vec4( modelViewMatrix.mul( vec4( instanceEnd, 1.0 ) ) ).toVar( 'end' );

			if ( useDash ) {

				const dashScaleNode = this.dashScaleNode ? float( this.dashScaleNode ) : materialLineScale;
				const offsetNode = this.offsetNode ? float( this.offsetNode ) : materialLineDashOffset;

				const instanceDistanceStart = attribute( 'instanceDistanceStart' );
				const instanceDistanceEnd = attribute( 'instanceDistanceEnd' );

				let lineDistance = positionGeometry.y.lessThan( 0.5 ).select( dashScaleNode.mul( instanceDistanceStart ), dashScaleNode.mul( instanceDistanceEnd ) );
				lineDistance = lineDistance.add( offsetNode );

				varyingProperty( 'float', 'lineDistance' ).assign( lineDistance );

			}

			if ( useWorldUnits ) {

				varyingProperty( 'vec3', 'worldStart' ).assign( start.xyz );
				varyingProperty( 'vec3', 'worldEnd' ).assign( end.xyz );

			}

			const aspect = viewport.z.div( viewport.w );

			// special case for perspective projection, and segments that terminate either in, or behind, the camera plane
			// clearly the gpu firmware has a way of addressing this issue when projecting into ndc space
			// but we need to perform ndc-space calculations in the shader, so we must address this issue directly
			// perhaps there is a more elegant solution -- WestLangley

			const perspective = cameraProjectionMatrix.element( 2 ).element( 3 ).equal( - 1.0 ); // 4th entry in the 3rd column

			If( perspective, () => {

				If( start.z.lessThan( 0.0 ).and( end.z.greaterThan( 0.0 ) ), () => {

					end.assign( trimSegment( { start: start, end: end } ) );

				} ).ElseIf( end.z.lessThan( 0.0 ).and( start.z.greaterThanEqual( 0.0 ) ), () => {

					start.assign( trimSegment( { start: end, end: start } ) );

			 	} );

			} );

			// clip space
			const clipStart = cameraProjectionMatrix.mul( start );
			const clipEnd = cameraProjectionMatrix.mul( end );

			// ndc space
			const ndcStart = clipStart.xyz.div( clipStart.w );
			const ndcEnd = clipEnd.xyz.div( clipEnd.w );

			// direction
			const dir = ndcEnd.xy.sub( ndcStart.xy ).toVar();

			// account for clip-space aspect ratio
			dir.x.assign( dir.x.mul( aspect ) );
			dir.assign( dir.normalize() );

			const clip = vec4().toVar();

			if ( useWorldUnits ) {

				// get the offset direction as perpendicular to the view vector

				const worldDir = end.xyz.sub( start.xyz ).normalize();
				const tmpFwd = mix( start.xyz, end.xyz, 0.5 ).normalize();
				const worldUp = worldDir.cross( tmpFwd ).normalize();
				const worldFwd = worldDir.cross( worldUp );

				const worldPos = varyingProperty( 'vec4', 'worldPos' );

				worldPos.assign( positionGeometry.y.lessThan( 0.5 ).select( start, end ) );

				// height offset
				const hw = materialLineWidth.mul( 0.5 );
				worldPos.addAssign( vec4( positionGeometry.x.lessThan( 0.0 ).select( worldUp.mul( hw ), worldUp.mul( hw ).negate() ), 0 ) );

				// don't extend the line if we're rendering dashes because we
				// won't be rendering the endcaps
				if ( ! useDash ) {

					// cap extension
					worldPos.addAssign( vec4( positionGeometry.y.lessThan( 0.5 ).select( worldDir.mul( hw ).negate(), worldDir.mul( hw ) ), 0 ) );

					// add width to the box
					worldPos.addAssign( vec4( worldFwd.mul( hw ), 0 ) );

					// endcaps
					If( positionGeometry.y.greaterThan( 1.0 ).or( positionGeometry.y.lessThan( 0.0 ) ), () => {

						worldPos.subAssign( vec4( worldFwd.mul( 2.0 ).mul( hw ), 0 ) );

					} );

				}

				// project the worldpos
				clip.assign( cameraProjectionMatrix.mul( worldPos ) );

				// shift the depth of the projected points so the line
				// segments overlap neatly
				const clipPose = vec3().toVar();

				clipPose.assign( positionGeometry.y.lessThan( 0.5 ).select( ndcStart, ndcEnd ) );
				clip.z.assign( clipPose.z.mul( clip.w ) );

			} else {

				const offset = vec2( dir.y, dir.x.negate() ).toVar( 'offset' );

				// undo aspect ratio adjustment
				dir.x.assign( dir.x.div( aspect ) );
				offset.x.assign( offset.x.div( aspect ) );

				// sign flip
				offset.assign( positionGeometry.x.lessThan( 0.0 ).select( offset.negate(), offset ) );

				// endcaps
				If( positionGeometry.y.lessThan( 0.0 ), () => {

					offset.assign( offset.sub( dir ) );

				} ).ElseIf( positionGeometry.y.greaterThan( 1.0 ), () => {

					offset.assign( offset.add( dir ) );

				} );

				// adjust for linewidth
				offset.assign( offset.mul( materialLineWidth ) );

				// adjust for clip-space to screen-space conversion // maybe resolution should be based on viewport ...
				offset.assign( offset.div( viewport.w ) );

				// select end
				clip.assign( positionGeometry.y.lessThan( 0.5 ).select( clipStart, clipEnd ) );

				// back to clip space
				offset.assign( offset.mul( clip.w ) );

				clip.assign( clip.add( vec4( offset, 0, 0 ) ) );

			}

			return clip;

		} )();

		const closestLineToLine = Fn( ( { p1, p2, p3, p4 } ) => {

			const p13 = p1.sub( p3 );
			const p43 = p4.sub( p3 );

			const p21 = p2.sub( p1 );

			const d1343 = p13.dot( p43 );
			const d4321 = p43.dot( p21 );
			const d1321 = p13.dot( p21 );
			const d4343 = p43.dot( p43 );
			const d2121 = p21.dot( p21 );

			const denom = d2121.mul( d4343 ).sub( d4321.mul( d4321 ) );
			const numer = d1343.mul( d4321 ).sub( d1321.mul( d4343 ) );

			const mua = numer.div( denom ).clamp();
			const mub = d1343.add( d4321.mul( mua ) ).div( d4343 ).clamp();

			return vec2( mua, mub );

		} );

		this.colorNode = Fn( () => {

			const vUv = uv();

			if ( useDash ) {

				const dashSizeNode = this.dashSizeNode ? float( this.dashSizeNode ) : materialLineDashSize;
				const gapSizeNode = this.gapSizeNode ? float( this.gapSizeNode ) : materialLineGapSize;

				dashSize.assign( dashSizeNode );
				gapSize.assign( gapSizeNode );

				const vLineDistance = varyingProperty( 'float', 'lineDistance' );

				vUv.y.lessThan( - 1.0 ).or( vUv.y.greaterThan( 1.0 ) ).discard(); // discard endcaps
				vLineDistance.mod( dashSize.add( gapSize ) ).greaterThan( dashSize ).discard(); // todo - FIX

			}

			const alpha = float( 1 ).toVar( 'alpha' );

			if ( useWorldUnits ) {

				const worldStart = varyingProperty( 'vec3', 'worldStart' );
				const worldEnd = varyingProperty( 'vec3', 'worldEnd' );

				// Find the closest points on the view ray and the line segment
				const rayEnd = varyingProperty( 'vec4', 'worldPos' ).xyz.normalize().mul( 1e5 );
				const lineDir = worldEnd.sub( worldStart );
				const params = closestLineToLine( { p1: worldStart, p2: worldEnd, p3: vec3( 0.0, 0.0, 0.0 ), p4: rayEnd } );

				const p1 = worldStart.add( lineDir.mul( params.x ) );
				const p2 = rayEnd.mul( params.y );
				const delta = p1.sub( p2 );
				const len = delta.length();
				const norm = len.div( materialLineWidth );

				if ( ! useDash ) {

					if ( useAlphaToCoverage && renderer.samples > 1 ) {

						const dnorm = norm.fwidth();
						alpha.assign( smoothstep( dnorm.negate().add( 0.5 ), dnorm.add( 0.5 ), norm ).oneMinus() );

					} else {

						norm.greaterThan( 0.5 ).discard();

					}

				}

			} else {

				// round endcaps

				if ( useAlphaToCoverage && renderer.samples > 1 ) {

					const a = vUv.x;
					const b = vUv.y.greaterThan( 0.0 ).select( vUv.y.sub( 1.0 ), vUv.y.add( 1.0 ) );

					const len2 = a.mul( a ).add( b.mul( b ) );

					const dlen = float( len2.fwidth() ).toVar( 'dlen' );

					If( vUv.y.abs().greaterThan( 1.0 ), () => {

						alpha.assign( smoothstep( dlen.oneMinus(), dlen.add( 1 ), len2 ).oneMinus() );

					} );

				} else {

					If( vUv.y.abs().greaterThan( 1.0 ), () => {

						const a = vUv.x;
						const b = vUv.y.greaterThan( 0.0 ).select( vUv.y.sub( 1.0 ), vUv.y.add( 1.0 ) );
						const len2 = a.mul( a ).add( b.mul( b ) );

						len2.greaterThan( 1.0 ).discard();

					} );

				}

			}

			let lineColorNode;

			if ( this.lineColorNode ) {

				lineColorNode = this.lineColorNode;

			} else {

				if ( useColor ) {

					const instanceColorStart = attribute( 'instanceColorStart' );
					const instanceColorEnd = attribute( 'instanceColorEnd' );

					const instanceColor = positionGeometry.y.lessThan( 0.5 ).select( instanceColorStart, instanceColorEnd );

					lineColorNode = instanceColor.mul( materialColor );

				} else {

					lineColorNode = materialColor;

				}

			}

			return vec4( lineColorNode, alpha );

		} )();

		if ( this.transparent ) {

			const opacityNode = this.opacityNode ? float( this.opacityNode ) : materialOpacity;

			this.outputNode = vec4( this.colorNode.rgb.mul( opacityNode ).add( viewportSharedTexture().rgb.mul( opacityNode.oneMinus() ) ), this.colorNode.a );

		}

		super.setup( builder );

	}
```
</details>


---

## Classes

### `Line2NodeMaterial`

<details><summary>Class Code</summary>

```ts
class Line2NodeMaterial extends NodeMaterial {

	static get type() {

		return 'Line2NodeMaterial';

	}

	/**
	 * Constructs a new node material for wide line rendering.
	 *
	 * @param {Object} [parameters={}] - The configuration parameter.
	 */
	constructor( parameters = {} ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLine2NodeMaterial = true;

		this.setDefaultValues( _defaultValues );

		/**
		 * Whether vertex colors should be used or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.useColor = parameters.vertexColors;

		/**
		 * The dash offset.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.dashOffset = 0;

		/**
		 * Defines the lines color.
		 *
		 * @type {?Node<vec3>}
		 * @default null
		 */
		this.lineColorNode = null;

		/**
		 * Defines the offset.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.offsetNode = null;

		/**
		 * Defines the dash scale.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.dashScaleNode = null;

		/**
		 * Defines the dash size.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.dashSizeNode = null;

		/**
		 * Defines the gap size.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.gapSizeNode = null;

		/**
		 * Blending is set to `NoBlending` since transparency
		 * is not supported, yet.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.blending = NoBlending;

		this._useDash = parameters.dashed;
		this._useAlphaToCoverage = true;
		this._useWorldUnits = false;

		this.setValues( parameters );

	}

	/**
	 * Setups the vertex and fragment stage of this node material.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setup( builder ) {

		const { renderer } = builder;

		const useAlphaToCoverage = this._useAlphaToCoverage;
		const useColor = this.useColor;
		const useDash = this._useDash;
		const useWorldUnits = this._useWorldUnits;

		const trimSegment = Fn( ( { start, end } ) => {

			const a = cameraProjectionMatrix.element( 2 ).element( 2 ); // 3nd entry in 3th column
			const b = cameraProjectionMatrix.element( 3 ).element( 2 ); // 3nd entry in 4th column
			const nearEstimate = b.mul( - 0.5 ).div( a );

			const alpha = nearEstimate.sub( start.z ).div( end.z.sub( start.z ) );

			return vec4( mix( start.xyz, end.xyz, alpha ), end.w );

		} ).setLayout( {
			name: 'trimSegment',
			type: 'vec4',
			inputs: [
				{ name: 'start', type: 'vec4' },
				{ name: 'end', type: 'vec4' }
			]
		} );

		this.vertexNode = Fn( () => {

			const instanceStart = attribute( 'instanceStart' );
			const instanceEnd = attribute( 'instanceEnd' );

			// camera space

			const start = vec4( modelViewMatrix.mul( vec4( instanceStart, 1.0 ) ) ).toVar( 'start' );
			const end = vec4( modelViewMatrix.mul( vec4( instanceEnd, 1.0 ) ) ).toVar( 'end' );

			if ( useDash ) {

				const dashScaleNode = this.dashScaleNode ? float( this.dashScaleNode ) : materialLineScale;
				const offsetNode = this.offsetNode ? float( this.offsetNode ) : materialLineDashOffset;

				const instanceDistanceStart = attribute( 'instanceDistanceStart' );
				const instanceDistanceEnd = attribute( 'instanceDistanceEnd' );

				let lineDistance = positionGeometry.y.lessThan( 0.5 ).select( dashScaleNode.mul( instanceDistanceStart ), dashScaleNode.mul( instanceDistanceEnd ) );
				lineDistance = lineDistance.add( offsetNode );

				varyingProperty( 'float', 'lineDistance' ).assign( lineDistance );

			}

			if ( useWorldUnits ) {

				varyingProperty( 'vec3', 'worldStart' ).assign( start.xyz );
				varyingProperty( 'vec3', 'worldEnd' ).assign( end.xyz );

			}

			const aspect = viewport.z.div( viewport.w );

			// special case for perspective projection, and segments that terminate either in, or behind, the camera plane
			// clearly the gpu firmware has a way of addressing this issue when projecting into ndc space
			// but we need to perform ndc-space calculations in the shader, so we must address this issue directly
			// perhaps there is a more elegant solution -- WestLangley

			const perspective = cameraProjectionMatrix.element( 2 ).element( 3 ).equal( - 1.0 ); // 4th entry in the 3rd column

			If( perspective, () => {

				If( start.z.lessThan( 0.0 ).and( end.z.greaterThan( 0.0 ) ), () => {

					end.assign( trimSegment( { start: start, end: end } ) );

				} ).ElseIf( end.z.lessThan( 0.0 ).and( start.z.greaterThanEqual( 0.0 ) ), () => {

					start.assign( trimSegment( { start: end, end: start } ) );

			 	} );

			} );

			// clip space
			const clipStart = cameraProjectionMatrix.mul( start );
			const clipEnd = cameraProjectionMatrix.mul( end );

			// ndc space
			const ndcStart = clipStart.xyz.div( clipStart.w );
			const ndcEnd = clipEnd.xyz.div( clipEnd.w );

			// direction
			const dir = ndcEnd.xy.sub( ndcStart.xy ).toVar();

			// account for clip-space aspect ratio
			dir.x.assign( dir.x.mul( aspect ) );
			dir.assign( dir.normalize() );

			const clip = vec4().toVar();

			if ( useWorldUnits ) {

				// get the offset direction as perpendicular to the view vector

				const worldDir = end.xyz.sub( start.xyz ).normalize();
				const tmpFwd = mix( start.xyz, end.xyz, 0.5 ).normalize();
				const worldUp = worldDir.cross( tmpFwd ).normalize();
				const worldFwd = worldDir.cross( worldUp );

				const worldPos = varyingProperty( 'vec4', 'worldPos' );

				worldPos.assign( positionGeometry.y.lessThan( 0.5 ).select( start, end ) );

				// height offset
				const hw = materialLineWidth.mul( 0.5 );
				worldPos.addAssign( vec4( positionGeometry.x.lessThan( 0.0 ).select( worldUp.mul( hw ), worldUp.mul( hw ).negate() ), 0 ) );

				// don't extend the line if we're rendering dashes because we
				// won't be rendering the endcaps
				if ( ! useDash ) {

					// cap extension
					worldPos.addAssign( vec4( positionGeometry.y.lessThan( 0.5 ).select( worldDir.mul( hw ).negate(), worldDir.mul( hw ) ), 0 ) );

					// add width to the box
					worldPos.addAssign( vec4( worldFwd.mul( hw ), 0 ) );

					// endcaps
					If( positionGeometry.y.greaterThan( 1.0 ).or( positionGeometry.y.lessThan( 0.0 ) ), () => {

						worldPos.subAssign( vec4( worldFwd.mul( 2.0 ).mul( hw ), 0 ) );

					} );

				}

				// project the worldpos
				clip.assign( cameraProjectionMatrix.mul( worldPos ) );

				// shift the depth of the projected points so the line
				// segments overlap neatly
				const clipPose = vec3().toVar();

				clipPose.assign( positionGeometry.y.lessThan( 0.5 ).select( ndcStart, ndcEnd ) );
				clip.z.assign( clipPose.z.mul( clip.w ) );

			} else {

				const offset = vec2( dir.y, dir.x.negate() ).toVar( 'offset' );

				// undo aspect ratio adjustment
				dir.x.assign( dir.x.div( aspect ) );
				offset.x.assign( offset.x.div( aspect ) );

				// sign flip
				offset.assign( positionGeometry.x.lessThan( 0.0 ).select( offset.negate(), offset ) );

				// endcaps
				If( positionGeometry.y.lessThan( 0.0 ), () => {

					offset.assign( offset.sub( dir ) );

				} ).ElseIf( positionGeometry.y.greaterThan( 1.0 ), () => {

					offset.assign( offset.add( dir ) );

				} );

				// adjust for linewidth
				offset.assign( offset.mul( materialLineWidth ) );

				// adjust for clip-space to screen-space conversion // maybe resolution should be based on viewport ...
				offset.assign( offset.div( viewport.w ) );

				// select end
				clip.assign( positionGeometry.y.lessThan( 0.5 ).select( clipStart, clipEnd ) );

				// back to clip space
				offset.assign( offset.mul( clip.w ) );

				clip.assign( clip.add( vec4( offset, 0, 0 ) ) );

			}

			return clip;

		} )();

		const closestLineToLine = Fn( ( { p1, p2, p3, p4 } ) => {

			const p13 = p1.sub( p3 );
			const p43 = p4.sub( p3 );

			const p21 = p2.sub( p1 );

			const d1343 = p13.dot( p43 );
			const d4321 = p43.dot( p21 );
			const d1321 = p13.dot( p21 );
			const d4343 = p43.dot( p43 );
			const d2121 = p21.dot( p21 );

			const denom = d2121.mul( d4343 ).sub( d4321.mul( d4321 ) );
			const numer = d1343.mul( d4321 ).sub( d1321.mul( d4343 ) );

			const mua = numer.div( denom ).clamp();
			const mub = d1343.add( d4321.mul( mua ) ).div( d4343 ).clamp();

			return vec2( mua, mub );

		} );

		this.colorNode = Fn( () => {

			const vUv = uv();

			if ( useDash ) {

				const dashSizeNode = this.dashSizeNode ? float( this.dashSizeNode ) : materialLineDashSize;
				const gapSizeNode = this.gapSizeNode ? float( this.gapSizeNode ) : materialLineGapSize;

				dashSize.assign( dashSizeNode );
				gapSize.assign( gapSizeNode );

				const vLineDistance = varyingProperty( 'float', 'lineDistance' );

				vUv.y.lessThan( - 1.0 ).or( vUv.y.greaterThan( 1.0 ) ).discard(); // discard endcaps
				vLineDistance.mod( dashSize.add( gapSize ) ).greaterThan( dashSize ).discard(); // todo - FIX

			}

			const alpha = float( 1 ).toVar( 'alpha' );

			if ( useWorldUnits ) {

				const worldStart = varyingProperty( 'vec3', 'worldStart' );
				const worldEnd = varyingProperty( 'vec3', 'worldEnd' );

				// Find the closest points on the view ray and the line segment
				const rayEnd = varyingProperty( 'vec4', 'worldPos' ).xyz.normalize().mul( 1e5 );
				const lineDir = worldEnd.sub( worldStart );
				const params = closestLineToLine( { p1: worldStart, p2: worldEnd, p3: vec3( 0.0, 0.0, 0.0 ), p4: rayEnd } );

				const p1 = worldStart.add( lineDir.mul( params.x ) );
				const p2 = rayEnd.mul( params.y );
				const delta = p1.sub( p2 );
				const len = delta.length();
				const norm = len.div( materialLineWidth );

				if ( ! useDash ) {

					if ( useAlphaToCoverage && renderer.samples > 1 ) {

						const dnorm = norm.fwidth();
						alpha.assign( smoothstep( dnorm.negate().add( 0.5 ), dnorm.add( 0.5 ), norm ).oneMinus() );

					} else {

						norm.greaterThan( 0.5 ).discard();

					}

				}

			} else {

				// round endcaps

				if ( useAlphaToCoverage && renderer.samples > 1 ) {

					const a = vUv.x;
					const b = vUv.y.greaterThan( 0.0 ).select( vUv.y.sub( 1.0 ), vUv.y.add( 1.0 ) );

					const len2 = a.mul( a ).add( b.mul( b ) );

					const dlen = float( len2.fwidth() ).toVar( 'dlen' );

					If( vUv.y.abs().greaterThan( 1.0 ), () => {

						alpha.assign( smoothstep( dlen.oneMinus(), dlen.add( 1 ), len2 ).oneMinus() );

					} );

				} else {

					If( vUv.y.abs().greaterThan( 1.0 ), () => {

						const a = vUv.x;
						const b = vUv.y.greaterThan( 0.0 ).select( vUv.y.sub( 1.0 ), vUv.y.add( 1.0 ) );
						const len2 = a.mul( a ).add( b.mul( b ) );

						len2.greaterThan( 1.0 ).discard();

					} );

				}

			}

			let lineColorNode;

			if ( this.lineColorNode ) {

				lineColorNode = this.lineColorNode;

			} else {

				if ( useColor ) {

					const instanceColorStart = attribute( 'instanceColorStart' );
					const instanceColorEnd = attribute( 'instanceColorEnd' );

					const instanceColor = positionGeometry.y.lessThan( 0.5 ).select( instanceColorStart, instanceColorEnd );

					lineColorNode = instanceColor.mul( materialColor );

				} else {

					lineColorNode = materialColor;

				}

			}

			return vec4( lineColorNode, alpha );

		} )();

		if ( this.transparent ) {

			const opacityNode = this.opacityNode ? float( this.opacityNode ) : materialOpacity;

			this.outputNode = vec4( this.colorNode.rgb.mul( opacityNode ).add( viewportSharedTexture().rgb.mul( opacityNode.oneMinus() ) ), this.colorNode.a );

		}

		super.setup( builder );

	}

	/**
	 * Whether the lines should sized in world units or not.
	 * When set to `false` the unit is pixel.
	 *
	 * @type {boolean}
	 * @default false
	 */
	get worldUnits() {

		return this._useWorldUnits;

	}

	set worldUnits( value ) {

		if ( this._useWorldUnits !== value ) {

			this._useWorldUnits = value;
			this.needsUpdate = true;

		}

	}

	/**
	 * Whether the lines should be dashed or not.
	 *
	 * @type {boolean}
	 * @default false
	 */
	get dashed() {

		return this._useDash;

	}

	set dashed( value ) {

		if ( this._useDash !== value ) {

			this._useDash = value;
			this.needsUpdate = true;

		}

	}

	/**
	 * Whether alpha to coverage should be used or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get alphaToCoverage() {

		return this._useAlphaToCoverage;

	}

	set alphaToCoverage( value ) {

		if ( this._useAlphaToCoverage !== value ) {

			this._useAlphaToCoverage = value;
			this.needsUpdate = true;

		}

	}

}
```
</details>

#### Methods

##### `setup(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const { renderer } = builder;

		const useAlphaToCoverage = this._useAlphaToCoverage;
		const useColor = this.useColor;
		const useDash = this._useDash;
		const useWorldUnits = this._useWorldUnits;

		const trimSegment = Fn( ( { start, end } ) => {

			const a = cameraProjectionMatrix.element( 2 ).element( 2 ); // 3nd entry in 3th column
			const b = cameraProjectionMatrix.element( 3 ).element( 2 ); // 3nd entry in 4th column
			const nearEstimate = b.mul( - 0.5 ).div( a );

			const alpha = nearEstimate.sub( start.z ).div( end.z.sub( start.z ) );

			return vec4( mix( start.xyz, end.xyz, alpha ), end.w );

		} ).setLayout( {
			name: 'trimSegment',
			type: 'vec4',
			inputs: [
				{ name: 'start', type: 'vec4' },
				{ name: 'end', type: 'vec4' }
			]
		} );

		this.vertexNode = Fn( () => {

			const instanceStart = attribute( 'instanceStart' );
			const instanceEnd = attribute( 'instanceEnd' );

			// camera space

			const start = vec4( modelViewMatrix.mul( vec4( instanceStart, 1.0 ) ) ).toVar( 'start' );
			const end = vec4( modelViewMatrix.mul( vec4( instanceEnd, 1.0 ) ) ).toVar( 'end' );

			if ( useDash ) {

				const dashScaleNode = this.dashScaleNode ? float( this.dashScaleNode ) : materialLineScale;
				const offsetNode = this.offsetNode ? float( this.offsetNode ) : materialLineDashOffset;

				const instanceDistanceStart = attribute( 'instanceDistanceStart' );
				const instanceDistanceEnd = attribute( 'instanceDistanceEnd' );

				let lineDistance = positionGeometry.y.lessThan( 0.5 ).select( dashScaleNode.mul( instanceDistanceStart ), dashScaleNode.mul( instanceDistanceEnd ) );
				lineDistance = lineDistance.add( offsetNode );

				varyingProperty( 'float', 'lineDistance' ).assign( lineDistance );

			}

			if ( useWorldUnits ) {

				varyingProperty( 'vec3', 'worldStart' ).assign( start.xyz );
				varyingProperty( 'vec3', 'worldEnd' ).assign( end.xyz );

			}

			const aspect = viewport.z.div( viewport.w );

			// special case for perspective projection, and segments that terminate either in, or behind, the camera plane
			// clearly the gpu firmware has a way of addressing this issue when projecting into ndc space
			// but we need to perform ndc-space calculations in the shader, so we must address this issue directly
			// perhaps there is a more elegant solution -- WestLangley

			const perspective = cameraProjectionMatrix.element( 2 ).element( 3 ).equal( - 1.0 ); // 4th entry in the 3rd column

			If( perspective, () => {

				If( start.z.lessThan( 0.0 ).and( end.z.greaterThan( 0.0 ) ), () => {

					end.assign( trimSegment( { start: start, end: end } ) );

				} ).ElseIf( end.z.lessThan( 0.0 ).and( start.z.greaterThanEqual( 0.0 ) ), () => {

					start.assign( trimSegment( { start: end, end: start } ) );

			 	} );

			} );

			// clip space
			const clipStart = cameraProjectionMatrix.mul( start );
			const clipEnd = cameraProjectionMatrix.mul( end );

			// ndc space
			const ndcStart = clipStart.xyz.div( clipStart.w );
			const ndcEnd = clipEnd.xyz.div( clipEnd.w );

			// direction
			const dir = ndcEnd.xy.sub( ndcStart.xy ).toVar();

			// account for clip-space aspect ratio
			dir.x.assign( dir.x.mul( aspect ) );
			dir.assign( dir.normalize() );

			const clip = vec4().toVar();

			if ( useWorldUnits ) {

				// get the offset direction as perpendicular to the view vector

				const worldDir = end.xyz.sub( start.xyz ).normalize();
				const tmpFwd = mix( start.xyz, end.xyz, 0.5 ).normalize();
				const worldUp = worldDir.cross( tmpFwd ).normalize();
				const worldFwd = worldDir.cross( worldUp );

				const worldPos = varyingProperty( 'vec4', 'worldPos' );

				worldPos.assign( positionGeometry.y.lessThan( 0.5 ).select( start, end ) );

				// height offset
				const hw = materialLineWidth.mul( 0.5 );
				worldPos.addAssign( vec4( positionGeometry.x.lessThan( 0.0 ).select( worldUp.mul( hw ), worldUp.mul( hw ).negate() ), 0 ) );

				// don't extend the line if we're rendering dashes because we
				// won't be rendering the endcaps
				if ( ! useDash ) {

					// cap extension
					worldPos.addAssign( vec4( positionGeometry.y.lessThan( 0.5 ).select( worldDir.mul( hw ).negate(), worldDir.mul( hw ) ), 0 ) );

					// add width to the box
					worldPos.addAssign( vec4( worldFwd.mul( hw ), 0 ) );

					// endcaps
					If( positionGeometry.y.greaterThan( 1.0 ).or( positionGeometry.y.lessThan( 0.0 ) ), () => {

						worldPos.subAssign( vec4( worldFwd.mul( 2.0 ).mul( hw ), 0 ) );

					} );

				}

				// project the worldpos
				clip.assign( cameraProjectionMatrix.mul( worldPos ) );

				// shift the depth of the projected points so the line
				// segments overlap neatly
				const clipPose = vec3().toVar();

				clipPose.assign( positionGeometry.y.lessThan( 0.5 ).select( ndcStart, ndcEnd ) );
				clip.z.assign( clipPose.z.mul( clip.w ) );

			} else {

				const offset = vec2( dir.y, dir.x.negate() ).toVar( 'offset' );

				// undo aspect ratio adjustment
				dir.x.assign( dir.x.div( aspect ) );
				offset.x.assign( offset.x.div( aspect ) );

				// sign flip
				offset.assign( positionGeometry.x.lessThan( 0.0 ).select( offset.negate(), offset ) );

				// endcaps
				If( positionGeometry.y.lessThan( 0.0 ), () => {

					offset.assign( offset.sub( dir ) );

				} ).ElseIf( positionGeometry.y.greaterThan( 1.0 ), () => {

					offset.assign( offset.add( dir ) );

				} );

				// adjust for linewidth
				offset.assign( offset.mul( materialLineWidth ) );

				// adjust for clip-space to screen-space conversion // maybe resolution should be based on viewport ...
				offset.assign( offset.div( viewport.w ) );

				// select end
				clip.assign( positionGeometry.y.lessThan( 0.5 ).select( clipStart, clipEnd ) );

				// back to clip space
				offset.assign( offset.mul( clip.w ) );

				clip.assign( clip.add( vec4( offset, 0, 0 ) ) );

			}

			return clip;

		} )();

		const closestLineToLine = Fn( ( { p1, p2, p3, p4 } ) => {

			const p13 = p1.sub( p3 );
			const p43 = p4.sub( p3 );

			const p21 = p2.sub( p1 );

			const d1343 = p13.dot( p43 );
			const d4321 = p43.dot( p21 );
			const d1321 = p13.dot( p21 );
			const d4343 = p43.dot( p43 );
			const d2121 = p21.dot( p21 );

			const denom = d2121.mul( d4343 ).sub( d4321.mul( d4321 ) );
			const numer = d1343.mul( d4321 ).sub( d1321.mul( d4343 ) );

			const mua = numer.div( denom ).clamp();
			const mub = d1343.add( d4321.mul( mua ) ).div( d4343 ).clamp();

			return vec2( mua, mub );

		} );

		this.colorNode = Fn( () => {

			const vUv = uv();

			if ( useDash ) {

				const dashSizeNode = this.dashSizeNode ? float( this.dashSizeNode ) : materialLineDashSize;
				const gapSizeNode = this.gapSizeNode ? float( this.gapSizeNode ) : materialLineGapSize;

				dashSize.assign( dashSizeNode );
				gapSize.assign( gapSizeNode );

				const vLineDistance = varyingProperty( 'float', 'lineDistance' );

				vUv.y.lessThan( - 1.0 ).or( vUv.y.greaterThan( 1.0 ) ).discard(); // discard endcaps
				vLineDistance.mod( dashSize.add( gapSize ) ).greaterThan( dashSize ).discard(); // todo - FIX

			}

			const alpha = float( 1 ).toVar( 'alpha' );

			if ( useWorldUnits ) {

				const worldStart = varyingProperty( 'vec3', 'worldStart' );
				const worldEnd = varyingProperty( 'vec3', 'worldEnd' );

				// Find the closest points on the view ray and the line segment
				const rayEnd = varyingProperty( 'vec4', 'worldPos' ).xyz.normalize().mul( 1e5 );
				const lineDir = worldEnd.sub( worldStart );
				const params = closestLineToLine( { p1: worldStart, p2: worldEnd, p3: vec3( 0.0, 0.0, 0.0 ), p4: rayEnd } );

				const p1 = worldStart.add( lineDir.mul( params.x ) );
				const p2 = rayEnd.mul( params.y );
				const delta = p1.sub( p2 );
				const len = delta.length();
				const norm = len.div( materialLineWidth );

				if ( ! useDash ) {

					if ( useAlphaToCoverage && renderer.samples > 1 ) {

						const dnorm = norm.fwidth();
						alpha.assign( smoothstep( dnorm.negate().add( 0.5 ), dnorm.add( 0.5 ), norm ).oneMinus() );

					} else {

						norm.greaterThan( 0.5 ).discard();

					}

				}

			} else {

				// round endcaps

				if ( useAlphaToCoverage && renderer.samples > 1 ) {

					const a = vUv.x;
					const b = vUv.y.greaterThan( 0.0 ).select( vUv.y.sub( 1.0 ), vUv.y.add( 1.0 ) );

					const len2 = a.mul( a ).add( b.mul( b ) );

					const dlen = float( len2.fwidth() ).toVar( 'dlen' );

					If( vUv.y.abs().greaterThan( 1.0 ), () => {

						alpha.assign( smoothstep( dlen.oneMinus(), dlen.add( 1 ), len2 ).oneMinus() );

					} );

				} else {

					If( vUv.y.abs().greaterThan( 1.0 ), () => {

						const a = vUv.x;
						const b = vUv.y.greaterThan( 0.0 ).select( vUv.y.sub( 1.0 ), vUv.y.add( 1.0 ) );
						const len2 = a.mul( a ).add( b.mul( b ) );

						len2.greaterThan( 1.0 ).discard();

					} );

				}

			}

			let lineColorNode;

			if ( this.lineColorNode ) {

				lineColorNode = this.lineColorNode;

			} else {

				if ( useColor ) {

					const instanceColorStart = attribute( 'instanceColorStart' );
					const instanceColorEnd = attribute( 'instanceColorEnd' );

					const instanceColor = positionGeometry.y.lessThan( 0.5 ).select( instanceColorStart, instanceColorEnd );

					lineColorNode = instanceColor.mul( materialColor );

				} else {

					lineColorNode = materialColor;

				}

			}

			return vec4( lineColorNode, alpha );

		} )();

		if ( this.transparent ) {

			const opacityNode = this.opacityNode ? float( this.opacityNode ) : materialOpacity;

			this.outputNode = vec4( this.colorNode.rgb.mul( opacityNode ).add( viewportSharedTexture().rgb.mul( opacityNode.oneMinus() ) ), this.colorNode.a );

		}

		super.setup( builder );

	}
```
</details>


---