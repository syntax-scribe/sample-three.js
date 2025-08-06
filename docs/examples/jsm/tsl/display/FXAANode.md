[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `FXAANode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 23 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/FXAANode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `uniformArray` | `three/tsl` |
| `select` | `three/tsl` |
| `float` | `three/tsl` |
| `NodeUpdateType` | `three/tsl` |
| `uv` | `three/tsl` |
| `dot` | `three/tsl` |
| `clamp` | `three/tsl` |
| `uniform` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `smoothstep` | `three/tsl` |
| `bool` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `If` | `three/tsl` |
| `Loop` | `three/tsl` |
| `max` | `three/tsl` |
| `min` | `three/tsl` |
| `Break` | `three/tsl` |
| `abs` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `map` | `any` | let/var | `this.textureNode.value` | ✗ |
| `uvNode` | `any` | let/var | `textureNode.uvNode \|\| uv()` | ✗ |


---

## Functions

### `FXAANode.updateBefore(): void`

**JSDoc:**
```typescript
/**
	 * This method is used to update the effect's uniforms once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Returns:** `void`

**Calls:**

- `this._invSize.value.set`

<details><summary>Code</summary>

```typescript
updateBefore( /* frame */ ) {

		const map = this.textureNode.value;

		this._invSize.value.set( 1 / map.image.width, 1 / map.image.height );

	}
```
</details>

### `FXAANode.setup(): ShaderCallNodeInternal`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
```

**Returns:** `ShaderCallNodeInternal`

**Calls:**

- `this.textureNode.bias`
- `uv (from three/tsl)`
- `float (from three/tsl)`
- `uniformArray (from three/tsl)`
- `Fn (from three/tsl)`
- `textureNode.sample`
- `dot (from three/tsl)`
- `Sample`
- `vec3 (from three/tsl)`
- `uv.add`
- `texSize.mul`
- `vec2 (from three/tsl)`
- `SampleLuminance`
- `max (from three/tsl)`
- `_RelativeThreshold.mul`
- `l.contrast.lessThan`
- `SampleLuminanceOffset`
- `min (from three/tsl)`
- `highest.sub`
- `float( 2.0 ).mul`
- `l.s.add( l.e ).add( l.n ).add`
- `f.add`
- `l.se.add( l.sw ).add( l.ne ).add`
- `f.mul`
- `abs (from three/tsl)`
- `f.sub`
- `clamp (from three/tsl)`
- `f.div`
- `smoothstep (from three/tsl)`
- `blendFactor.mul( blendFactor ).mul`
- `abs( l.s.add( l.n ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add`
- `abs( l.se.add( l.ne ).sub( l.e.mul( 2.0 ) ) ).add`
- `l.sw.add( l.nw ).sub`
- `l.w.mul`
- `abs( l.e.add( l.w ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add`
- `abs( l.se.add( l.sw ).sub( l.s.mul( 2.0 ) ) ).add`
- `l.ne.add( l.nw ).sub`
- `l.n.mul`
- `horizontal.greaterThanEqual`
- `select (from three/tsl)`
- `pLuminance.sub`
- `nLuminance.sub`
- `select( isHorizontal, texSize.y, texSize.x ).toVar`
- `float().toVar`
- `If( pGradient.lessThan( nGradient ), () => {

				pixelStep.assign( pixelStep.negate() );
				oppositeLuminance.assign( nLuminance );
				gradient.assign( nGradient );

			} ).Else`
- `oppositeLuminance.assign`
- `gradient.assign`
- `uv.toVar`
- `vec2().toVar`
- `If( e.isHorizontal, () => {

				uvEdge.y.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( texSize.x, 0.0 ) );

			} ).Else`
- `uvEdge.x.addAssign`
- `e.pixelStep.mul`
- `edgeStep.assign`
- `l.m.add( e.oppositeLuminance ).mul`
- `e.gradient.mul`
- `uvEdge.add( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar`
- `SampleLuminance( puv ).sub( edgeLuminance ).toVar`
- `abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar`
- `Loop (from three/tsl)`
- `If (from three/tsl)`
- `Break (from three/tsl)`
- `puv.addAssign`
- `edgeStep.mul`
- `EDGE_STEPS.element`
- `pLuminanceDelta.assign`
- `SampleLuminance( puv ).sub`
- `pAtEnd.assign`
- `abs( pLuminanceDelta ).greaterThanEqual`
- `pAtEnd.not`
- `uvEdge.sub( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar`
- `SampleLuminance( nuv ).sub( edgeLuminance ).toVar`
- `abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar`
- `nuv.subAssign`
- `nLuminanceDelta.assign`
- `SampleLuminance( nuv ).sub`
- `nAtEnd.assign`
- `abs( nLuminanceDelta ).greaterThanEqual`
- `nAtEnd.not`
- `If( e.isHorizontal, () => {

				pDistance.assign( puv.x.sub( uv.x ) );
				nDistance.assign( uv.x.sub( nuv.x ) );

			} ).Else`
- `pDistance.assign`
- `puv.y.sub`
- `nDistance.assign`
- `uv.y.sub`
- `bool().toVar`
- `If( pDistance.lessThanEqual( nDistance ), () => {

				shortestDistance.assign( pDistance );
				deltaSign.assign( pLuminanceDelta.greaterThanEqual( 0.0 ) );

			} ).Else`
- `shortestDistance.assign`
- `deltaSign.assign`
- `nLuminanceDelta.greaterThanEqual`
- `If( deltaSign.equal( l.m.sub( edgeLuminance ).greaterThanEqual( 0.0 ) ), () => {

				blendFactor.assign( 0.0 );

			} ).Else`
- `blendFactor.assign`
- `float( 0.5 ).sub`
- `shortestDistance.div`
- `pDistance.add`
- `Fn( ( [ uv, texSize ] ) => {

			const luminance = SampleLuminanceNeighborhood( texSize, uv );
			If( ShouldSkipPixel( luminance ), () => {

				return Sample( uv );

			} );

			const pixelBlend = DeterminePixelBlendFactor( luminance );
			const edge = DetermineEdge( texSize, luminance );
			const edgeBlend = DetermineEdgeBlendFactor( texSize, luminance, edge, uv );

			const finalBlend = max( pixelBlend, edgeBlend );
			const finalUv = uv.toVar();

			If( edge.isHorizontal, () => {

				finalUv.y.addAssign( edge.pixelStep.mul( finalBlend ) );

			} ).Else( () => {

				finalUv.x.addAssign( edge.pixelStep.mul( finalBlend ) );

			} );

			return Sample( finalUv );

		} ).setLayout`
- `ApplyFXAA`
- `fxaa`

<details><summary>Code</summary>

```typescript
setup( /* builder */ ) {

		const textureNode = this.textureNode.bias( - 100 );
		const uvNode = textureNode.uvNode || uv();

		const EDGE_STEP_COUNT = float( 6 );
		const EDGE_GUESS = float( 8.0 );
		const EDGE_STEPS = uniformArray( [ 1.0, 1.5, 2.0, 2.0, 2.0, 4.0 ] );

		const _ContrastThreshold = float( 0.0312 );
		const _RelativeThreshold = float( 0.063 );
		const _SubpixelBlending = float( 1.0 );

		const Sample = Fn( ( [ uv ] ) => {

			return textureNode.sample( uv );

		} );

		const SampleLuminance = Fn( ( [ uv ] ) => {

			return dot( Sample( uv ).rgb, vec3( 0.3, 0.59, 0.11 ) );

		} );

		const SampleLuminanceOffset = Fn( ( [ texSize, uv, uOffset, vOffset ] ) => {

			const shiftedUv = uv.add( texSize.mul( vec2( uOffset, vOffset ) ) );
			return SampleLuminance( shiftedUv );

		} );

		const ShouldSkipPixel = ( l ) => {

			const threshold = max( _ContrastThreshold, _RelativeThreshold.mul( l.highest ) );
			return l.contrast.lessThan( threshold );

		};

		const SampleLuminanceNeighborhood = ( texSize, uv ) => {

			const m = SampleLuminance( uv );

			const n = SampleLuminanceOffset( texSize, uv, 0.0, - 1.0 );
			const e = SampleLuminanceOffset( texSize, uv, 1.0, 0.0 );
			const s = SampleLuminanceOffset( texSize, uv, 0.0, 1.0 );
			const w = SampleLuminanceOffset( texSize, uv, - 1.0, 0.0 );

			const ne = SampleLuminanceOffset( texSize, uv, 1.0, - 1.0 );
			const nw = SampleLuminanceOffset( texSize, uv, - 1.0, - 1.0 );
			const se = SampleLuminanceOffset( texSize, uv, 1.0, 1.0 );
			const sw = SampleLuminanceOffset( texSize, uv, - 1.0, 1.0 );

			const highest = max( s, e, n, w, m );
			const lowest = min( s, e, n, w, m );
			const contrast = highest.sub( lowest );

			return { m, n, e, s, w, ne, nw, se, sw, highest, lowest, contrast };

		};

		const DeterminePixelBlendFactor = ( l ) => {

			let f = float( 2.0 ).mul( l.s.add( l.e ).add( l.n ).add( l.w ) );
			f = f.add( l.se.add( l.sw ).add( l.ne ).add( l.nw ) );
			f = f.mul( 1.0 / 12.0 );
			f = abs( f.sub( l.m ) );
			f = clamp( f.div( max( l.contrast, 0 ) ), 0.0, 1.0 );

			const blendFactor = smoothstep( 0.0, 1.0, f );
			return blendFactor.mul( blendFactor ).mul( _SubpixelBlending );

		};

		const DetermineEdge = ( texSize, l ) => {

			const horizontal =
				abs( l.s.add( l.n ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add(
					abs( l.se.add( l.ne ).sub( l.e.mul( 2.0 ) ) ).add(
						abs( l.sw.add( l.nw ).sub( l.w.mul( 2.0 ) ) )
					)
				);

			const vertical =
				abs( l.e.add( l.w ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add(
					abs( l.se.add( l.sw ).sub( l.s.mul( 2.0 ) ) ).add(
						abs( l.ne.add( l.nw ).sub( l.n.mul( 2.0 ) ) )
					)
				);

			const isHorizontal = horizontal.greaterThanEqual( vertical );

			const pLuminance = select( isHorizontal, l.s, l.e );
			const nLuminance = select( isHorizontal, l.n, l.w );
			const pGradient = abs( pLuminance.sub( l.m ) );
			const nGradient = abs( nLuminance.sub( l.m ) );

			const pixelStep = select( isHorizontal, texSize.y, texSize.x ).toVar();
			const oppositeLuminance = float().toVar();
			const gradient = float().toVar();

			If( pGradient.lessThan( nGradient ), () => {

				pixelStep.assign( pixelStep.negate() );
				oppositeLuminance.assign( nLuminance );
				gradient.assign( nGradient );

			} ).Else( () => {

				oppositeLuminance.assign( pLuminance );
				gradient.assign( pGradient );

			} );

			return { isHorizontal, pixelStep, oppositeLuminance, gradient };

		};

		const DetermineEdgeBlendFactor = ( texSize, l, e, uv ) => {

			const uvEdge = uv.toVar();
			const edgeStep = vec2().toVar();
			If( e.isHorizontal, () => {

				uvEdge.y.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( texSize.x, 0.0 ) );

			} ).Else( () => {

				uvEdge.x.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( 0.0, texSize.y ) );

			} );

			const edgeLuminance = l.m.add( e.oppositeLuminance ).mul( 0.5 );
			const gradientThreshold = e.gradient.mul( 0.25 );

			const puv = uvEdge.add( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar();
			const pLuminanceDelta = SampleLuminance( puv ).sub( edgeLuminance ).toVar();
			const pAtEnd = abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar();

			Loop( { start: 1, end: EDGE_STEP_COUNT }, ( { i } ) => {

				If( pAtEnd, () => {

					Break();

				} );

				puv.addAssign( edgeStep.mul( EDGE_STEPS.element( i ) ) );
				pLuminanceDelta.assign( SampleLuminance( puv ).sub( edgeLuminance ) );
				pAtEnd.assign( abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ) );

			} );

			If( pAtEnd.not(), () => {

				puv.addAssign( edgeStep.mul( EDGE_GUESS ) );

			} );

			const nuv = uvEdge.sub( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar();
			const nLuminanceDelta = SampleLuminance( nuv ).sub( edgeLuminance ).toVar();
			const nAtEnd = abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar();

			Loop( { start: 1, end: EDGE_STEP_COUNT }, ( { i } ) => {

				If( nAtEnd, () => {

					Break();

				} );

				nuv.subAssign( edgeStep.mul( EDGE_STEPS.element( i ) ) );
				nLuminanceDelta.assign( SampleLuminance( nuv ).sub( edgeLuminance ) );
				nAtEnd.assign( abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ) );

			} );

			If( nAtEnd.not(), () => {

				nuv.subAssign( edgeStep.mul( EDGE_GUESS ) );

			} );

			const pDistance = float().toVar();
			const nDistance = float().toVar();

			If( e.isHorizontal, () => {

				pDistance.assign( puv.x.sub( uv.x ) );
				nDistance.assign( uv.x.sub( nuv.x ) );

			} ).Else( () => {

				pDistance.assign( puv.y.sub( uv.y ) );
				nDistance.assign( uv.y.sub( nuv.y ) );

			} );

			const shortestDistance = float().toVar();
			const deltaSign = bool().toVar();

			If( pDistance.lessThanEqual( nDistance ), () => {

				shortestDistance.assign( pDistance );
				deltaSign.assign( pLuminanceDelta.greaterThanEqual( 0.0 ) );

			} ).Else( () => {

				shortestDistance.assign( nDistance );
				deltaSign.assign( nLuminanceDelta.greaterThanEqual( 0.0 ) );

			} );

			const blendFactor = float().toVar();

			If( deltaSign.equal( l.m.sub( edgeLuminance ).greaterThanEqual( 0.0 ) ), () => {

				blendFactor.assign( 0.0 );

			} ).Else( () => {

				blendFactor.assign( float( 0.5 ).sub( shortestDistance.div( pDistance.add( nDistance ) ) ) );

			} );

			return blendFactor;

		};

		const ApplyFXAA = Fn( ( [ uv, texSize ] ) => {

			const luminance = SampleLuminanceNeighborhood( texSize, uv );
			If( ShouldSkipPixel( luminance ), () => {

				return Sample( uv );

			} );

			const pixelBlend = DeterminePixelBlendFactor( luminance );
			const edge = DetermineEdge( texSize, luminance );
			const edgeBlend = DetermineEdgeBlendFactor( texSize, luminance, edge, uv );

			const finalBlend = max( pixelBlend, edgeBlend );
			const finalUv = uv.toVar();

			If( edge.isHorizontal, () => {

				finalUv.y.addAssign( edge.pixelStep.mul( finalBlend ) );

			} ).Else( () => {

				finalUv.x.addAssign( edge.pixelStep.mul( finalBlend ) );

			} );

			return Sample( finalUv );

		} ).setLayout( {
			name: 'FxaaPixelShader',
			type: 'vec4',
			inputs: [
				{ name: 'uv', type: 'vec2' },
				{ name: 'texSize', type: 'vec2' },
			]
		} );

		const fxaa = Fn( () => {

			return ApplyFXAA( uvNode, this._invSize );

		} );

		const outputNode = fxaa();

		return outputNode;

	}
```
</details>

### `ShouldSkipPixel(l: any): any`

**Parameters:**

- **`l`** `any`

**Returns:** `any`

**Calls:**

- `max (from three/tsl)`
- `_RelativeThreshold.mul`
- `l.contrast.lessThan`

<details><summary>Code</summary>

```typescript
( l ) => {

			const threshold = max( _ContrastThreshold, _RelativeThreshold.mul( l.highest ) );
			return l.contrast.lessThan( threshold );

		}
```
</details>

### `SampleLuminanceNeighborhood(texSize: any, uv: any): { m: any; n: any; e: any; s: any; w: any; ne: any; nw: any; se: any; sw: any; highest: any; lowest: any; contrast: any; }`

**Parameters:**

- **`texSize`** `any`
- **`uv`** `any`

**Returns:** `{ m: any; n: any; e: any; s: any; w: any; ne: any; nw: any; se: any; sw: any; highest: any; lowest: any; contrast: any; }`

**Calls:**

- `SampleLuminance`
- `SampleLuminanceOffset`
- `max (from three/tsl)`
- `min (from three/tsl)`
- `highest.sub`

<details><summary>Code</summary>

```typescript
( texSize, uv ) => {

			const m = SampleLuminance( uv );

			const n = SampleLuminanceOffset( texSize, uv, 0.0, - 1.0 );
			const e = SampleLuminanceOffset( texSize, uv, 1.0, 0.0 );
			const s = SampleLuminanceOffset( texSize, uv, 0.0, 1.0 );
			const w = SampleLuminanceOffset( texSize, uv, - 1.0, 0.0 );

			const ne = SampleLuminanceOffset( texSize, uv, 1.0, - 1.0 );
			const nw = SampleLuminanceOffset( texSize, uv, - 1.0, - 1.0 );
			const se = SampleLuminanceOffset( texSize, uv, 1.0, 1.0 );
			const sw = SampleLuminanceOffset( texSize, uv, - 1.0, 1.0 );

			const highest = max( s, e, n, w, m );
			const lowest = min( s, e, n, w, m );
			const contrast = highest.sub( lowest );

			return { m, n, e, s, w, ne, nw, se, sw, highest, lowest, contrast };

		}
```
</details>

### `DeterminePixelBlendFactor(l: any): any`

**Parameters:**

- **`l`** `any`

**Returns:** `any`

**Calls:**

- `float( 2.0 ).mul`
- `l.s.add( l.e ).add( l.n ).add`
- `f.add`
- `l.se.add( l.sw ).add( l.ne ).add`
- `f.mul`
- `abs (from three/tsl)`
- `f.sub`
- `clamp (from three/tsl)`
- `f.div`
- `max (from three/tsl)`
- `smoothstep (from three/tsl)`
- `blendFactor.mul( blendFactor ).mul`

<details><summary>Code</summary>

```typescript
( l ) => {

			let f = float( 2.0 ).mul( l.s.add( l.e ).add( l.n ).add( l.w ) );
			f = f.add( l.se.add( l.sw ).add( l.ne ).add( l.nw ) );
			f = f.mul( 1.0 / 12.0 );
			f = abs( f.sub( l.m ) );
			f = clamp( f.div( max( l.contrast, 0 ) ), 0.0, 1.0 );

			const blendFactor = smoothstep( 0.0, 1.0, f );
			return blendFactor.mul( blendFactor ).mul( _SubpixelBlending );

		}
```
</details>

### `DetermineEdge(texSize: any, l: any): { isHorizontal: any; pixelStep: any; oppositeLuminance: any; gradient: any; }`

**Parameters:**

- **`texSize`** `any`
- **`l`** `any`

**Returns:** `{ isHorizontal: any; pixelStep: any; oppositeLuminance: any; gradient: any; }`

**Calls:**

- `abs( l.s.add( l.n ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add`
- `abs( l.se.add( l.ne ).sub( l.e.mul( 2.0 ) ) ).add`
- `abs (from three/tsl)`
- `l.sw.add( l.nw ).sub`
- `l.w.mul`
- `abs( l.e.add( l.w ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add`
- `abs( l.se.add( l.sw ).sub( l.s.mul( 2.0 ) ) ).add`
- `l.ne.add( l.nw ).sub`
- `l.n.mul`
- `horizontal.greaterThanEqual`
- `select (from three/tsl)`
- `pLuminance.sub`
- `nLuminance.sub`
- `select( isHorizontal, texSize.y, texSize.x ).toVar`
- `float().toVar`
- `If( pGradient.lessThan( nGradient ), () => {

				pixelStep.assign( pixelStep.negate() );
				oppositeLuminance.assign( nLuminance );
				gradient.assign( nGradient );

			} ).Else`
- `oppositeLuminance.assign`
- `gradient.assign`

<details><summary>Code</summary>

```typescript
( texSize, l ) => {

			const horizontal =
				abs( l.s.add( l.n ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add(
					abs( l.se.add( l.ne ).sub( l.e.mul( 2.0 ) ) ).add(
						abs( l.sw.add( l.nw ).sub( l.w.mul( 2.0 ) ) )
					)
				);

			const vertical =
				abs( l.e.add( l.w ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add(
					abs( l.se.add( l.sw ).sub( l.s.mul( 2.0 ) ) ).add(
						abs( l.ne.add( l.nw ).sub( l.n.mul( 2.0 ) ) )
					)
				);

			const isHorizontal = horizontal.greaterThanEqual( vertical );

			const pLuminance = select( isHorizontal, l.s, l.e );
			const nLuminance = select( isHorizontal, l.n, l.w );
			const pGradient = abs( pLuminance.sub( l.m ) );
			const nGradient = abs( nLuminance.sub( l.m ) );

			const pixelStep = select( isHorizontal, texSize.y, texSize.x ).toVar();
			const oppositeLuminance = float().toVar();
			const gradient = float().toVar();

			If( pGradient.lessThan( nGradient ), () => {

				pixelStep.assign( pixelStep.negate() );
				oppositeLuminance.assign( nLuminance );
				gradient.assign( nGradient );

			} ).Else( () => {

				oppositeLuminance.assign( pLuminance );
				gradient.assign( pGradient );

			} );

			return { isHorizontal, pixelStep, oppositeLuminance, gradient };

		}
```
</details>

### `DetermineEdgeBlendFactor(texSize: any, l: any, e: any, uv: any): any`

**Parameters:**

- **`texSize`** `any`
- **`l`** `any`
- **`e`** `any`
- **`uv`** `any`

**Returns:** `any`

**Calls:**

- `uv.toVar`
- `vec2().toVar`
- `If( e.isHorizontal, () => {

				uvEdge.y.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( texSize.x, 0.0 ) );

			} ).Else`
- `uvEdge.x.addAssign`
- `e.pixelStep.mul`
- `edgeStep.assign`
- `vec2 (from three/tsl)`
- `l.m.add( e.oppositeLuminance ).mul`
- `e.gradient.mul`
- `uvEdge.add( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar`
- `SampleLuminance( puv ).sub( edgeLuminance ).toVar`
- `abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar`
- `Loop (from three/tsl)`
- `If (from three/tsl)`
- `Break (from three/tsl)`
- `puv.addAssign`
- `edgeStep.mul`
- `EDGE_STEPS.element`
- `pLuminanceDelta.assign`
- `SampleLuminance( puv ).sub`
- `pAtEnd.assign`
- `abs( pLuminanceDelta ).greaterThanEqual`
- `pAtEnd.not`
- `uvEdge.sub( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar`
- `SampleLuminance( nuv ).sub( edgeLuminance ).toVar`
- `abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar`
- `nuv.subAssign`
- `nLuminanceDelta.assign`
- `SampleLuminance( nuv ).sub`
- `nAtEnd.assign`
- `abs( nLuminanceDelta ).greaterThanEqual`
- `nAtEnd.not`
- `float().toVar`
- `If( e.isHorizontal, () => {

				pDistance.assign( puv.x.sub( uv.x ) );
				nDistance.assign( uv.x.sub( nuv.x ) );

			} ).Else`
- `pDistance.assign`
- `puv.y.sub`
- `nDistance.assign`
- `uv.y.sub`
- `bool().toVar`
- `If( pDistance.lessThanEqual( nDistance ), () => {

				shortestDistance.assign( pDistance );
				deltaSign.assign( pLuminanceDelta.greaterThanEqual( 0.0 ) );

			} ).Else`
- `shortestDistance.assign`
- `deltaSign.assign`
- `nLuminanceDelta.greaterThanEqual`
- `If( deltaSign.equal( l.m.sub( edgeLuminance ).greaterThanEqual( 0.0 ) ), () => {

				blendFactor.assign( 0.0 );

			} ).Else`
- `blendFactor.assign`
- `float( 0.5 ).sub`
- `shortestDistance.div`
- `pDistance.add`

<details><summary>Code</summary>

```typescript
( texSize, l, e, uv ) => {

			const uvEdge = uv.toVar();
			const edgeStep = vec2().toVar();
			If( e.isHorizontal, () => {

				uvEdge.y.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( texSize.x, 0.0 ) );

			} ).Else( () => {

				uvEdge.x.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( 0.0, texSize.y ) );

			} );

			const edgeLuminance = l.m.add( e.oppositeLuminance ).mul( 0.5 );
			const gradientThreshold = e.gradient.mul( 0.25 );

			const puv = uvEdge.add( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar();
			const pLuminanceDelta = SampleLuminance( puv ).sub( edgeLuminance ).toVar();
			const pAtEnd = abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar();

			Loop( { start: 1, end: EDGE_STEP_COUNT }, ( { i } ) => {

				If( pAtEnd, () => {

					Break();

				} );

				puv.addAssign( edgeStep.mul( EDGE_STEPS.element( i ) ) );
				pLuminanceDelta.assign( SampleLuminance( puv ).sub( edgeLuminance ) );
				pAtEnd.assign( abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ) );

			} );

			If( pAtEnd.not(), () => {

				puv.addAssign( edgeStep.mul( EDGE_GUESS ) );

			} );

			const nuv = uvEdge.sub( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar();
			const nLuminanceDelta = SampleLuminance( nuv ).sub( edgeLuminance ).toVar();
			const nAtEnd = abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar();

			Loop( { start: 1, end: EDGE_STEP_COUNT }, ( { i } ) => {

				If( nAtEnd, () => {

					Break();

				} );

				nuv.subAssign( edgeStep.mul( EDGE_STEPS.element( i ) ) );
				nLuminanceDelta.assign( SampleLuminance( nuv ).sub( edgeLuminance ) );
				nAtEnd.assign( abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ) );

			} );

			If( nAtEnd.not(), () => {

				nuv.subAssign( edgeStep.mul( EDGE_GUESS ) );

			} );

			const pDistance = float().toVar();
			const nDistance = float().toVar();

			If( e.isHorizontal, () => {

				pDistance.assign( puv.x.sub( uv.x ) );
				nDistance.assign( uv.x.sub( nuv.x ) );

			} ).Else( () => {

				pDistance.assign( puv.y.sub( uv.y ) );
				nDistance.assign( uv.y.sub( nuv.y ) );

			} );

			const shortestDistance = float().toVar();
			const deltaSign = bool().toVar();

			If( pDistance.lessThanEqual( nDistance ), () => {

				shortestDistance.assign( pDistance );
				deltaSign.assign( pLuminanceDelta.greaterThanEqual( 0.0 ) );

			} ).Else( () => {

				shortestDistance.assign( nDistance );
				deltaSign.assign( nLuminanceDelta.greaterThanEqual( 0.0 ) );

			} );

			const blendFactor = float().toVar();

			If( deltaSign.equal( l.m.sub( edgeLuminance ).greaterThanEqual( 0.0 ) ), () => {

				blendFactor.assign( 0.0 );

			} ).Else( () => {

				blendFactor.assign( float( 0.5 ).sub( shortestDistance.div( pDistance.add( nDistance ) ) ) );

			} );

			return blendFactor;

		}
```
</details>

### `fxaa(node: any): FXAANode`

**Parameters:**

- **`node`** `any`

**Returns:** `FXAANode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node ) => nodeObject( new FXAANode( convertToTexture( node ) ) )
```
</details>


---

## Classes

### `FXAANode`

<details><summary>Class Code</summary>

```ts
class FXAANode extends TempNode {

	static get type() {

		return 'FXAANode';

	}

	/**
	 * Constructs a new FXAA node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the input of the effect.
	 */
	constructor( textureNode ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the input of the effect.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node updates
		 * its internal uniforms once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

		/**
		 * A uniform node holding the inverse resolution value.
		 *
		 * @private
		 * @type {UniformNode<vec2>}
		 */
		this._invSize = uniform( new Vector2() );

	}

	/**
	 * This method is used to update the effect's uniforms once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( /* frame */ ) {

		const map = this.textureNode.value;

		this._invSize.value.set( 1 / map.image.width, 1 / map.image.height );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
	setup( /* builder */ ) {

		const textureNode = this.textureNode.bias( - 100 );
		const uvNode = textureNode.uvNode || uv();

		const EDGE_STEP_COUNT = float( 6 );
		const EDGE_GUESS = float( 8.0 );
		const EDGE_STEPS = uniformArray( [ 1.0, 1.5, 2.0, 2.0, 2.0, 4.0 ] );

		const _ContrastThreshold = float( 0.0312 );
		const _RelativeThreshold = float( 0.063 );
		const _SubpixelBlending = float( 1.0 );

		const Sample = Fn( ( [ uv ] ) => {

			return textureNode.sample( uv );

		} );

		const SampleLuminance = Fn( ( [ uv ] ) => {

			return dot( Sample( uv ).rgb, vec3( 0.3, 0.59, 0.11 ) );

		} );

		const SampleLuminanceOffset = Fn( ( [ texSize, uv, uOffset, vOffset ] ) => {

			const shiftedUv = uv.add( texSize.mul( vec2( uOffset, vOffset ) ) );
			return SampleLuminance( shiftedUv );

		} );

		const ShouldSkipPixel = ( l ) => {

			const threshold = max( _ContrastThreshold, _RelativeThreshold.mul( l.highest ) );
			return l.contrast.lessThan( threshold );

		};

		const SampleLuminanceNeighborhood = ( texSize, uv ) => {

			const m = SampleLuminance( uv );

			const n = SampleLuminanceOffset( texSize, uv, 0.0, - 1.0 );
			const e = SampleLuminanceOffset( texSize, uv, 1.0, 0.0 );
			const s = SampleLuminanceOffset( texSize, uv, 0.0, 1.0 );
			const w = SampleLuminanceOffset( texSize, uv, - 1.0, 0.0 );

			const ne = SampleLuminanceOffset( texSize, uv, 1.0, - 1.0 );
			const nw = SampleLuminanceOffset( texSize, uv, - 1.0, - 1.0 );
			const se = SampleLuminanceOffset( texSize, uv, 1.0, 1.0 );
			const sw = SampleLuminanceOffset( texSize, uv, - 1.0, 1.0 );

			const highest = max( s, e, n, w, m );
			const lowest = min( s, e, n, w, m );
			const contrast = highest.sub( lowest );

			return { m, n, e, s, w, ne, nw, se, sw, highest, lowest, contrast };

		};

		const DeterminePixelBlendFactor = ( l ) => {

			let f = float( 2.0 ).mul( l.s.add( l.e ).add( l.n ).add( l.w ) );
			f = f.add( l.se.add( l.sw ).add( l.ne ).add( l.nw ) );
			f = f.mul( 1.0 / 12.0 );
			f = abs( f.sub( l.m ) );
			f = clamp( f.div( max( l.contrast, 0 ) ), 0.0, 1.0 );

			const blendFactor = smoothstep( 0.0, 1.0, f );
			return blendFactor.mul( blendFactor ).mul( _SubpixelBlending );

		};

		const DetermineEdge = ( texSize, l ) => {

			const horizontal =
				abs( l.s.add( l.n ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add(
					abs( l.se.add( l.ne ).sub( l.e.mul( 2.0 ) ) ).add(
						abs( l.sw.add( l.nw ).sub( l.w.mul( 2.0 ) ) )
					)
				);

			const vertical =
				abs( l.e.add( l.w ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add(
					abs( l.se.add( l.sw ).sub( l.s.mul( 2.0 ) ) ).add(
						abs( l.ne.add( l.nw ).sub( l.n.mul( 2.0 ) ) )
					)
				);

			const isHorizontal = horizontal.greaterThanEqual( vertical );

			const pLuminance = select( isHorizontal, l.s, l.e );
			const nLuminance = select( isHorizontal, l.n, l.w );
			const pGradient = abs( pLuminance.sub( l.m ) );
			const nGradient = abs( nLuminance.sub( l.m ) );

			const pixelStep = select( isHorizontal, texSize.y, texSize.x ).toVar();
			const oppositeLuminance = float().toVar();
			const gradient = float().toVar();

			If( pGradient.lessThan( nGradient ), () => {

				pixelStep.assign( pixelStep.negate() );
				oppositeLuminance.assign( nLuminance );
				gradient.assign( nGradient );

			} ).Else( () => {

				oppositeLuminance.assign( pLuminance );
				gradient.assign( pGradient );

			} );

			return { isHorizontal, pixelStep, oppositeLuminance, gradient };

		};

		const DetermineEdgeBlendFactor = ( texSize, l, e, uv ) => {

			const uvEdge = uv.toVar();
			const edgeStep = vec2().toVar();
			If( e.isHorizontal, () => {

				uvEdge.y.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( texSize.x, 0.0 ) );

			} ).Else( () => {

				uvEdge.x.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( 0.0, texSize.y ) );

			} );

			const edgeLuminance = l.m.add( e.oppositeLuminance ).mul( 0.5 );
			const gradientThreshold = e.gradient.mul( 0.25 );

			const puv = uvEdge.add( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar();
			const pLuminanceDelta = SampleLuminance( puv ).sub( edgeLuminance ).toVar();
			const pAtEnd = abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar();

			Loop( { start: 1, end: EDGE_STEP_COUNT }, ( { i } ) => {

				If( pAtEnd, () => {

					Break();

				} );

				puv.addAssign( edgeStep.mul( EDGE_STEPS.element( i ) ) );
				pLuminanceDelta.assign( SampleLuminance( puv ).sub( edgeLuminance ) );
				pAtEnd.assign( abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ) );

			} );

			If( pAtEnd.not(), () => {

				puv.addAssign( edgeStep.mul( EDGE_GUESS ) );

			} );

			const nuv = uvEdge.sub( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar();
			const nLuminanceDelta = SampleLuminance( nuv ).sub( edgeLuminance ).toVar();
			const nAtEnd = abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar();

			Loop( { start: 1, end: EDGE_STEP_COUNT }, ( { i } ) => {

				If( nAtEnd, () => {

					Break();

				} );

				nuv.subAssign( edgeStep.mul( EDGE_STEPS.element( i ) ) );
				nLuminanceDelta.assign( SampleLuminance( nuv ).sub( edgeLuminance ) );
				nAtEnd.assign( abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ) );

			} );

			If( nAtEnd.not(), () => {

				nuv.subAssign( edgeStep.mul( EDGE_GUESS ) );

			} );

			const pDistance = float().toVar();
			const nDistance = float().toVar();

			If( e.isHorizontal, () => {

				pDistance.assign( puv.x.sub( uv.x ) );
				nDistance.assign( uv.x.sub( nuv.x ) );

			} ).Else( () => {

				pDistance.assign( puv.y.sub( uv.y ) );
				nDistance.assign( uv.y.sub( nuv.y ) );

			} );

			const shortestDistance = float().toVar();
			const deltaSign = bool().toVar();

			If( pDistance.lessThanEqual( nDistance ), () => {

				shortestDistance.assign( pDistance );
				deltaSign.assign( pLuminanceDelta.greaterThanEqual( 0.0 ) );

			} ).Else( () => {

				shortestDistance.assign( nDistance );
				deltaSign.assign( nLuminanceDelta.greaterThanEqual( 0.0 ) );

			} );

			const blendFactor = float().toVar();

			If( deltaSign.equal( l.m.sub( edgeLuminance ).greaterThanEqual( 0.0 ) ), () => {

				blendFactor.assign( 0.0 );

			} ).Else( () => {

				blendFactor.assign( float( 0.5 ).sub( shortestDistance.div( pDistance.add( nDistance ) ) ) );

			} );

			return blendFactor;

		};

		const ApplyFXAA = Fn( ( [ uv, texSize ] ) => {

			const luminance = SampleLuminanceNeighborhood( texSize, uv );
			If( ShouldSkipPixel( luminance ), () => {

				return Sample( uv );

			} );

			const pixelBlend = DeterminePixelBlendFactor( luminance );
			const edge = DetermineEdge( texSize, luminance );
			const edgeBlend = DetermineEdgeBlendFactor( texSize, luminance, edge, uv );

			const finalBlend = max( pixelBlend, edgeBlend );
			const finalUv = uv.toVar();

			If( edge.isHorizontal, () => {

				finalUv.y.addAssign( edge.pixelStep.mul( finalBlend ) );

			} ).Else( () => {

				finalUv.x.addAssign( edge.pixelStep.mul( finalBlend ) );

			} );

			return Sample( finalUv );

		} ).setLayout( {
			name: 'FxaaPixelShader',
			type: 'vec4',
			inputs: [
				{ name: 'uv', type: 'vec2' },
				{ name: 'texSize', type: 'vec2' },
			]
		} );

		const fxaa = Fn( () => {

			return ApplyFXAA( uvNode, this._invSize );

		} );

		const outputNode = fxaa();

		return outputNode;

	}

}
```
</details>

#### Methods

##### `updateBefore(): void`

<details><summary>Code</summary>

```ts
updateBefore( /* frame */ ) {

		const map = this.textureNode.value;

		this._invSize.value.set( 1 / map.image.width, 1 / map.image.height );

	}
```
</details>

##### `setup(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup( /* builder */ ) {

		const textureNode = this.textureNode.bias( - 100 );
		const uvNode = textureNode.uvNode || uv();

		const EDGE_STEP_COUNT = float( 6 );
		const EDGE_GUESS = float( 8.0 );
		const EDGE_STEPS = uniformArray( [ 1.0, 1.5, 2.0, 2.0, 2.0, 4.0 ] );

		const _ContrastThreshold = float( 0.0312 );
		const _RelativeThreshold = float( 0.063 );
		const _SubpixelBlending = float( 1.0 );

		const Sample = Fn( ( [ uv ] ) => {

			return textureNode.sample( uv );

		} );

		const SampleLuminance = Fn( ( [ uv ] ) => {

			return dot( Sample( uv ).rgb, vec3( 0.3, 0.59, 0.11 ) );

		} );

		const SampleLuminanceOffset = Fn( ( [ texSize, uv, uOffset, vOffset ] ) => {

			const shiftedUv = uv.add( texSize.mul( vec2( uOffset, vOffset ) ) );
			return SampleLuminance( shiftedUv );

		} );

		const ShouldSkipPixel = ( l ) => {

			const threshold = max( _ContrastThreshold, _RelativeThreshold.mul( l.highest ) );
			return l.contrast.lessThan( threshold );

		};

		const SampleLuminanceNeighborhood = ( texSize, uv ) => {

			const m = SampleLuminance( uv );

			const n = SampleLuminanceOffset( texSize, uv, 0.0, - 1.0 );
			const e = SampleLuminanceOffset( texSize, uv, 1.0, 0.0 );
			const s = SampleLuminanceOffset( texSize, uv, 0.0, 1.0 );
			const w = SampleLuminanceOffset( texSize, uv, - 1.0, 0.0 );

			const ne = SampleLuminanceOffset( texSize, uv, 1.0, - 1.0 );
			const nw = SampleLuminanceOffset( texSize, uv, - 1.0, - 1.0 );
			const se = SampleLuminanceOffset( texSize, uv, 1.0, 1.0 );
			const sw = SampleLuminanceOffset( texSize, uv, - 1.0, 1.0 );

			const highest = max( s, e, n, w, m );
			const lowest = min( s, e, n, w, m );
			const contrast = highest.sub( lowest );

			return { m, n, e, s, w, ne, nw, se, sw, highest, lowest, contrast };

		};

		const DeterminePixelBlendFactor = ( l ) => {

			let f = float( 2.0 ).mul( l.s.add( l.e ).add( l.n ).add( l.w ) );
			f = f.add( l.se.add( l.sw ).add( l.ne ).add( l.nw ) );
			f = f.mul( 1.0 / 12.0 );
			f = abs( f.sub( l.m ) );
			f = clamp( f.div( max( l.contrast, 0 ) ), 0.0, 1.0 );

			const blendFactor = smoothstep( 0.0, 1.0, f );
			return blendFactor.mul( blendFactor ).mul( _SubpixelBlending );

		};

		const DetermineEdge = ( texSize, l ) => {

			const horizontal =
				abs( l.s.add( l.n ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add(
					abs( l.se.add( l.ne ).sub( l.e.mul( 2.0 ) ) ).add(
						abs( l.sw.add( l.nw ).sub( l.w.mul( 2.0 ) ) )
					)
				);

			const vertical =
				abs( l.e.add( l.w ).sub( l.m.mul( 2.0 ) ) ).mul( 2.0 ).add(
					abs( l.se.add( l.sw ).sub( l.s.mul( 2.0 ) ) ).add(
						abs( l.ne.add( l.nw ).sub( l.n.mul( 2.0 ) ) )
					)
				);

			const isHorizontal = horizontal.greaterThanEqual( vertical );

			const pLuminance = select( isHorizontal, l.s, l.e );
			const nLuminance = select( isHorizontal, l.n, l.w );
			const pGradient = abs( pLuminance.sub( l.m ) );
			const nGradient = abs( nLuminance.sub( l.m ) );

			const pixelStep = select( isHorizontal, texSize.y, texSize.x ).toVar();
			const oppositeLuminance = float().toVar();
			const gradient = float().toVar();

			If( pGradient.lessThan( nGradient ), () => {

				pixelStep.assign( pixelStep.negate() );
				oppositeLuminance.assign( nLuminance );
				gradient.assign( nGradient );

			} ).Else( () => {

				oppositeLuminance.assign( pLuminance );
				gradient.assign( pGradient );

			} );

			return { isHorizontal, pixelStep, oppositeLuminance, gradient };

		};

		const DetermineEdgeBlendFactor = ( texSize, l, e, uv ) => {

			const uvEdge = uv.toVar();
			const edgeStep = vec2().toVar();
			If( e.isHorizontal, () => {

				uvEdge.y.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( texSize.x, 0.0 ) );

			} ).Else( () => {

				uvEdge.x.addAssign( e.pixelStep.mul( 0.5 ) );
				edgeStep.assign( vec2( 0.0, texSize.y ) );

			} );

			const edgeLuminance = l.m.add( e.oppositeLuminance ).mul( 0.5 );
			const gradientThreshold = e.gradient.mul( 0.25 );

			const puv = uvEdge.add( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar();
			const pLuminanceDelta = SampleLuminance( puv ).sub( edgeLuminance ).toVar();
			const pAtEnd = abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar();

			Loop( { start: 1, end: EDGE_STEP_COUNT }, ( { i } ) => {

				If( pAtEnd, () => {

					Break();

				} );

				puv.addAssign( edgeStep.mul( EDGE_STEPS.element( i ) ) );
				pLuminanceDelta.assign( SampleLuminance( puv ).sub( edgeLuminance ) );
				pAtEnd.assign( abs( pLuminanceDelta ).greaterThanEqual( gradientThreshold ) );

			} );

			If( pAtEnd.not(), () => {

				puv.addAssign( edgeStep.mul( EDGE_GUESS ) );

			} );

			const nuv = uvEdge.sub( edgeStep.mul( EDGE_STEPS.element( 0 ) ) ).toVar();
			const nLuminanceDelta = SampleLuminance( nuv ).sub( edgeLuminance ).toVar();
			const nAtEnd = abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ).toVar();

			Loop( { start: 1, end: EDGE_STEP_COUNT }, ( { i } ) => {

				If( nAtEnd, () => {

					Break();

				} );

				nuv.subAssign( edgeStep.mul( EDGE_STEPS.element( i ) ) );
				nLuminanceDelta.assign( SampleLuminance( nuv ).sub( edgeLuminance ) );
				nAtEnd.assign( abs( nLuminanceDelta ).greaterThanEqual( gradientThreshold ) );

			} );

			If( nAtEnd.not(), () => {

				nuv.subAssign( edgeStep.mul( EDGE_GUESS ) );

			} );

			const pDistance = float().toVar();
			const nDistance = float().toVar();

			If( e.isHorizontal, () => {

				pDistance.assign( puv.x.sub( uv.x ) );
				nDistance.assign( uv.x.sub( nuv.x ) );

			} ).Else( () => {

				pDistance.assign( puv.y.sub( uv.y ) );
				nDistance.assign( uv.y.sub( nuv.y ) );

			} );

			const shortestDistance = float().toVar();
			const deltaSign = bool().toVar();

			If( pDistance.lessThanEqual( nDistance ), () => {

				shortestDistance.assign( pDistance );
				deltaSign.assign( pLuminanceDelta.greaterThanEqual( 0.0 ) );

			} ).Else( () => {

				shortestDistance.assign( nDistance );
				deltaSign.assign( nLuminanceDelta.greaterThanEqual( 0.0 ) );

			} );

			const blendFactor = float().toVar();

			If( deltaSign.equal( l.m.sub( edgeLuminance ).greaterThanEqual( 0.0 ) ), () => {

				blendFactor.assign( 0.0 );

			} ).Else( () => {

				blendFactor.assign( float( 0.5 ).sub( shortestDistance.div( pDistance.add( nDistance ) ) ) );

			} );

			return blendFactor;

		};

		const ApplyFXAA = Fn( ( [ uv, texSize ] ) => {

			const luminance = SampleLuminanceNeighborhood( texSize, uv );
			If( ShouldSkipPixel( luminance ), () => {

				return Sample( uv );

			} );

			const pixelBlend = DeterminePixelBlendFactor( luminance );
			const edge = DetermineEdge( texSize, luminance );
			const edgeBlend = DetermineEdgeBlendFactor( texSize, luminance, edge, uv );

			const finalBlend = max( pixelBlend, edgeBlend );
			const finalUv = uv.toVar();

			If( edge.isHorizontal, () => {

				finalUv.y.addAssign( edge.pixelStep.mul( finalBlend ) );

			} ).Else( () => {

				finalUv.x.addAssign( edge.pixelStep.mul( finalBlend ) );

			} );

			return Sample( finalUv );

		} ).setLayout( {
			name: 'FxaaPixelShader',
			type: 'vec4',
			inputs: [
				{ name: 'uv', type: 'vec2' },
				{ name: 'texSize', type: 'vec2' },
			]
		} );

		const fxaa = Fn( () => {

			return ApplyFXAA( uvNode, this._invSize );

		} );

		const outputNode = fxaa();

		return outputNode;

	}
```
</details>


---