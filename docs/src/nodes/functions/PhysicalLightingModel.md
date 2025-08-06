[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PhysicalLightingModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 🧱 Classes | 1 |
| 📦 Imports | 60 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/functions/PhysicalLightingModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BRDF_Lambert` | `./BSDF/BRDF_Lambert.js` |
| `BRDF_GGX` | `./BSDF/BRDF_GGX.js` |
| `DFGApprox` | `./BSDF/DFGApprox.js` |
| `EnvironmentBRDF` | `./BSDF/EnvironmentBRDF.js` |
| `F_Schlick` | `./BSDF/F_Schlick.js` |
| `Schlick_to_F0` | `./BSDF/Schlick_to_F0.js` |
| `BRDF_Sheen` | `./BSDF/BRDF_Sheen.js` |
| `LTC_Evaluate` | `./BSDF/LTC.js` |
| `LTC_Uv` | `./BSDF/LTC.js` |
| `LightingModel` | `../core/LightingModel.js` |
| `diffuseColor` | `../core/PropertyNode.js` |
| `specularColor` | `../core/PropertyNode.js` |
| `specularF90` | `../core/PropertyNode.js` |
| `roughness` | `../core/PropertyNode.js` |
| `clearcoat` | `../core/PropertyNode.js` |
| `clearcoatRoughness` | `../core/PropertyNode.js` |
| `sheen` | `../core/PropertyNode.js` |
| `sheenRoughness` | `../core/PropertyNode.js` |
| `iridescence` | `../core/PropertyNode.js` |
| `iridescenceIOR` | `../core/PropertyNode.js` |
| `iridescenceThickness` | `../core/PropertyNode.js` |
| `ior` | `../core/PropertyNode.js` |
| `thickness` | `../core/PropertyNode.js` |
| `transmission` | `../core/PropertyNode.js` |
| `attenuationDistance` | `../core/PropertyNode.js` |
| `attenuationColor` | `../core/PropertyNode.js` |
| `dispersion` | `../core/PropertyNode.js` |
| `normalView` | `../accessors/Normal.js` |
| `clearcoatNormalView` | `../accessors/Normal.js` |
| `normalWorld` | `../accessors/Normal.js` |
| `positionViewDirection` | `../accessors/Position.js` |
| `positionView` | `../accessors/Position.js` |
| `positionWorld` | `../accessors/Position.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |
| `mat3` | `../tsl/TSLBase.js` |
| `If` | `../tsl/TSLBase.js` |
| `select` | `../math/ConditionalNode.js` |
| `mix` | `../math/MathNode.js` |
| `normalize` | `../math/MathNode.js` |
| `refract` | `../math/MathNode.js` |
| `length` | `../math/MathNode.js` |
| `clamp` | `../math/MathNode.js` |
| `log2` | `../math/MathNode.js` |
| `log` | `../math/MathNode.js` |
| `exp` | `../math/MathNode.js` |
| `smoothstep` | `../math/MathNode.js` |
| `div` | `../math/OperatorNode.js` |
| `cameraPosition` | `../accessors/Camera.js` |
| `cameraProjectionMatrix` | `../accessors/Camera.js` |
| `cameraViewMatrix` | `../accessors/Camera.js` |
| `modelWorldMatrix` | `../accessors/ModelNode.js` |
| `screenSize` | `../display/ScreenNode.js` |
| `viewportMipTexture` | `../display/ViewportTextureNode.js` |
| `textureBicubicLevel` | `../accessors/TextureBicubic.js` |
| `Loop` | `../utils/LoopNode.js` |
| `BackSide` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `vTexture` | `any` | let/var | `material.side === BackSide ? viewportBackSideTexture : viewportFrontSideTexture` | ✗ |
| `transmittedLight` | `any` | let/var | `*not shown*` | ✗ |
| `transmittance` | `any` | let/var | `*not shown*` | ✗ |
| `position` | `VaryingNode<vec3>` | let/var | `positionWorld` | ✗ |
| `n` | `any` | let/var | `normalWorld` | ✗ |
| `context` | `any` | let/var | `builder.context` | ✗ |
| `Fr` | `any` | let/var | `this.iridescenceF0 ? iridescence.mix( specularColor, this.iridescenceF0 ) : s...` | ✗ |
| `N` | `any` | let/var | `normalView` | ✗ |
| `V` | `VaryingNode<vec3>` | let/var | `positionViewDirection` | ✗ |


---

## Functions

### `Fresnel0ToIor(fresnel0: any): any`

**Parameters:**

- **`fresnel0`** `any`

**Returns:** `any`

**Calls:**

- `fresnel0.sqrt`
- `vec3( 1.0 ).add( sqrtF0 ).div`
- `vec3( 1.0 ).sub`

<details><summary>Code</summary>

```typescript
( fresnel0 ) => {

	const sqrtF0 = fresnel0.sqrt();
	return vec3( 1.0 ).add( sqrtF0 ).div( vec3( 1.0 ).sub( sqrtF0 ) );

}
```
</details>

### `IorToFresnel0(transmittedIor: any, incidentIor: any): any`

**Parameters:**

- **`transmittedIor`** `any`
- **`incidentIor`** `any`

**Returns:** `any`

**Calls:**

- `transmittedIor.sub( incidentIor ).div( transmittedIor.add( incidentIor ) ).pow2`

<details><summary>Code</summary>

```typescript
( transmittedIor, incidentIor ) => {

	return transmittedIor.sub( incidentIor ).div( transmittedIor.add( incidentIor ) ).pow2();

}
```
</details>

### `evalSensitivity(OPD: any, shift: any): any`

**Parameters:**

- **`OPD`** `any`
- **`shift`** `any`

**Returns:** `any`

**Calls:**

- `OPD.mul`
- `vec3 (from ../tsl/TSLBase.js)`
- `float( 9.7470e-14 * Math.sqrt( 2.0 * Math.PI * 4.5282e+09 ) ).mul( phase.mul( 2.2399e+06 ).add( shift.x ).cos() ).mul`
- `phase.pow2().mul( - 4.5282e+09 ).exp`
- `val.mul( VAR.mul( 2.0 * Math.PI ).sqrt() ).mul( pos.mul( phase ).add( shift ).cos() ).mul`
- `phase.pow2().negate().mul( VAR ).exp`
- `vec3( xyz.x.add( x ), xyz.y, xyz.z ).div`
- `XYZ_TO_REC709.mul`

<details><summary>Code</summary>

```typescript
( OPD, shift ) => {

	const phase = OPD.mul( 2.0 * Math.PI * 1.0e-9 );
	const val = vec3( 5.4856e-13, 4.4201e-13, 5.2481e-13 );
	const pos = vec3( 1.6810e+06, 1.7953e+06, 2.2084e+06 );
	const VAR = vec3( 4.3278e+09, 9.3046e+09, 6.6121e+09 );

	const x = float( 9.7470e-14 * Math.sqrt( 2.0 * Math.PI * 4.5282e+09 ) ).mul( phase.mul( 2.2399e+06 ).add( shift.x ).cos() ).mul( phase.pow2().mul( - 4.5282e+09 ).exp() );

	let xyz = val.mul( VAR.mul( 2.0 * Math.PI ).sqrt() ).mul( pos.mul( phase ).add( shift ).cos() ).mul( phase.pow2().negate().mul( VAR ).exp() );
	xyz = vec3( xyz.x.add( x ), xyz.y, xyz.z ).div( 1.0685e-7 );

	const rgb = XYZ_TO_REC709.mul( xyz );

	return rgb;

}
```
</details>

### `PhysicalLightingModel.start(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Depending on what features are requested, the method prepares certain node variables
	 * which are later used for lighting computations.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `vec3().toVar`
- `normalView.dot( positionViewDirection ).clamp`
- `evalIridescence`
- `float (from ../tsl/TSLBase.js)`
- `Schlick_to_F0 (from ./BSDF/Schlick_to_F0.js)`
- `cameraPosition.sub( positionWorld ).normalize`
- `getIBLVolumeRefraction`
- `diffuseColor.a.mulAssign`
- `mix (from ../math/MathNode.js)`
- `super.start`

<details><summary>Code</summary>

```typescript
start( builder ) {

		if ( this.clearcoat === true ) {

			this.clearcoatRadiance = vec3().toVar( 'clearcoatRadiance' );
			this.clearcoatSpecularDirect = vec3().toVar( 'clearcoatSpecularDirect' );
			this.clearcoatSpecularIndirect = vec3().toVar( 'clearcoatSpecularIndirect' );

		}

		if ( this.sheen === true ) {

			this.sheenSpecularDirect = vec3().toVar( 'sheenSpecularDirect' );
			this.sheenSpecularIndirect = vec3().toVar( 'sheenSpecularIndirect' );

		}

		if ( this.iridescence === true ) {

			const dotNVi = normalView.dot( positionViewDirection ).clamp();

			this.iridescenceFresnel = evalIridescence( {
				outsideIOR: float( 1.0 ),
				eta2: iridescenceIOR,
				cosTheta1: dotNVi,
				thinFilmThickness: iridescenceThickness,
				baseF0: specularColor
			} );

			this.iridescenceF0 = Schlick_to_F0( { f: this.iridescenceFresnel, f90: 1.0, dotVH: dotNVi } );

		}

		if ( this.transmission === true ) {

			const position = positionWorld;
			const v = cameraPosition.sub( positionWorld ).normalize(); // TODO: Create Node for this, same issue in MaterialX
			const n = normalWorld;

			const context = builder.context;

			context.backdrop = getIBLVolumeRefraction(
				n,
				v,
				roughness,
				diffuseColor,
				specularColor,
				specularF90, // specularF90
				position, // positionWorld
				modelWorldMatrix, // modelMatrix
				cameraViewMatrix, // viewMatrix
				cameraProjectionMatrix, // projMatrix
				ior,
				thickness,
				attenuationColor,
				attenuationDistance,
				this.dispersion ? dispersion : null
			);

			context.backdropAlpha = transmission;

			diffuseColor.a.mulAssign( mix( 1, context.backdrop.a, transmission ) );

		}

		super.start( builder );

	}
```
</details>

### `PhysicalLightingModel.computeMultiscattering(singleScatter: any, multiScatter: any, specularF90: any): void`

**Parameters:**

- **`singleScatter`** `any`
- **`multiScatter`** `any`
- **`specularF90`** `any`

**Returns:** `void`

**Calls:**

- `normalView.dot( positionViewDirection ).clamp`
- `DFGApprox (from ./BSDF/DFGApprox.js)`
- `iridescence.mix`
- `Fr.mul( fab.x ).add`
- `specularF90.mul`
- `fab.x.add`
- `Ess.oneMinus`
- `specularColor.add`
- `specularColor.oneMinus().mul`
- `FssEss.mul( Favg ).div`
- `Ems.mul( Favg ).oneMinus`
- `singleScatter.addAssign`
- `multiScatter.addAssign`
- `Fms.mul`

<details><summary>Code</summary>

```typescript
computeMultiscattering( singleScatter, multiScatter, specularF90 ) {

		const dotNV = normalView.dot( positionViewDirection ).clamp(); // @ TODO: Move to core dotNV

		const fab = DFGApprox( { roughness, dotNV } );

		const Fr = this.iridescenceF0 ? iridescence.mix( specularColor, this.iridescenceF0 ) : specularColor;

		const FssEss = Fr.mul( fab.x ).add( specularF90.mul( fab.y ) );

		const Ess = fab.x.add( fab.y );
		const Ems = Ess.oneMinus();

		const Favg = specularColor.add( specularColor.oneMinus().mul( 0.047619 ) ); // 1/21
		const Fms = FssEss.mul( Favg ).div( Ems.mul( Favg ).oneMinus() );

		singleScatter.addAssign( FssEss );
		multiScatter.addAssign( Fms.mul( Ems ) );

	}
```
</details>

### `PhysicalLightingModel.direct({ lightDirection, lightColor, reflectedLight }: any): void`

**JSDoc:**
```typescript
/**
	 * Implements the direct light.
	 *
	 * @param {Object} lightData - The light data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`{ lightDirection, lightColor, reflectedLight }`** `any`

**Returns:** `void`

**Calls:**

- `normalView.dot( lightDirection ).clamp`
- `dotNL.mul`
- `this.sheenSpecularDirect.addAssign`
- `irradiance.mul`
- `BRDF_Sheen (from ./BSDF/BRDF_Sheen.js)`
- `clearcoatNormalView.dot( lightDirection ).clamp`
- `dotNLcc.mul`
- `this.clearcoatSpecularDirect.addAssign`
- `ccIrradiance.mul`
- `BRDF_GGX (from ./BSDF/BRDF_GGX.js)`
- `reflectedLight.directDiffuse.addAssign`
- `BRDF_Lambert (from ./BSDF/BRDF_Lambert.js)`
- `reflectedLight.directSpecular.addAssign`

<details><summary>Code</summary>

```typescript
direct( { lightDirection, lightColor, reflectedLight }, /* builder */ ) {

		const dotNL = normalView.dot( lightDirection ).clamp();
		const irradiance = dotNL.mul( lightColor );

		if ( this.sheen === true ) {

			this.sheenSpecularDirect.addAssign( irradiance.mul( BRDF_Sheen( { lightDirection } ) ) );

		}

		if ( this.clearcoat === true ) {

			const dotNLcc = clearcoatNormalView.dot( lightDirection ).clamp();
			const ccIrradiance = dotNLcc.mul( lightColor );

			this.clearcoatSpecularDirect.addAssign( ccIrradiance.mul( BRDF_GGX( { lightDirection, f0: clearcoatF0, f90: clearcoatF90, roughness: clearcoatRoughness, normalView: clearcoatNormalView } ) ) );

		}

		reflectedLight.directDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor: diffuseColor.rgb } ) ) );

		reflectedLight.directSpecular.addAssign( irradiance.mul( BRDF_GGX( { lightDirection, f0: specularColor, f90: 1, roughness, iridescence: this.iridescence, f: this.iridescenceFresnel, USE_IRIDESCENCE: this.iridescence, USE_ANISOTROPY: this.anisotropy } ) ) );

	}
```
</details>

### `PhysicalLightingModel.directRectArea({ lightColor, lightPosition, halfWidth, halfHeight, reflectedLight, ltc_1, ltc_2 }: any): void`

**JSDoc:**
```typescript
/**
	 * This method is intended for implementing the direct light term for
	 * rect area light nodes.
	 *
	 * @param {Object} input - The input data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`{ lightColor, lightPosition, halfWidth, halfHeight, reflectedLight, ltc_1, ltc_2 }`** `any`

**Returns:** `void`

**Calls:**

- `lightPosition.add( halfWidth ).sub`
- `lightPosition.sub( halfWidth ).sub`
- `lightPosition.sub( halfWidth ).add`
- `lightPosition.add( halfWidth ).add`
- `positionView.toVar`
- `LTC_Uv (from ./BSDF/LTC.js)`
- `ltc_1.sample( uv ).toVar`
- `ltc_2.sample( uv ).toVar`
- `mat3(
			vec3( t1.x, 0, t1.y ),
			vec3( 0, 1, 0 ),
			vec3( t1.z, 0, t1.w )
		).toVar`
- `specularColor.mul( t2.x ).add( specularColor.oneMinus().mul( t2.y ) ).toVar`
- `reflectedLight.directSpecular.addAssign`
- `lightColor.mul( fresnel ).mul`
- `LTC_Evaluate (from ./BSDF/LTC.js)`
- `reflectedLight.directDiffuse.addAssign`
- `lightColor.mul( diffuseColor ).mul`
- `mat3 (from ../tsl/TSLBase.js)`

**Internal Comments:**
```
// LTC Fresnel Approximation by Stephen Hill (x2)
// http://blog.selfshadow.com/publications/s2016-advances/s2016_ltc_fresnel.pdf (x2)
```

<details><summary>Code</summary>

```typescript
directRectArea( { lightColor, lightPosition, halfWidth, halfHeight, reflectedLight, ltc_1, ltc_2 }, /* builder */ ) {

		const p0 = lightPosition.add( halfWidth ).sub( halfHeight ); // counterclockwise; light shines in local neg z direction
		const p1 = lightPosition.sub( halfWidth ).sub( halfHeight );
		const p2 = lightPosition.sub( halfWidth ).add( halfHeight );
		const p3 = lightPosition.add( halfWidth ).add( halfHeight );

		const N = normalView;
		const V = positionViewDirection;
		const P = positionView.toVar();

		const uv = LTC_Uv( { N, V, roughness } );

		const t1 = ltc_1.sample( uv ).toVar();
		const t2 = ltc_2.sample( uv ).toVar();

		const mInv = mat3(
			vec3( t1.x, 0, t1.y ),
			vec3( 0, 1, 0 ),
			vec3( t1.z, 0, t1.w )
		).toVar();

		// LTC Fresnel Approximation by Stephen Hill
		// http://blog.selfshadow.com/publications/s2016-advances/s2016_ltc_fresnel.pdf
		const fresnel = specularColor.mul( t2.x ).add( specularColor.oneMinus().mul( t2.y ) ).toVar();

		reflectedLight.directSpecular.addAssign( lightColor.mul( fresnel ).mul( LTC_Evaluate( { N, V, P, mInv, p0, p1, p2, p3 } ) ) );

		reflectedLight.directDiffuse.addAssign( lightColor.mul( diffuseColor ).mul( LTC_Evaluate( { N, V, P, mInv: mat3( 1, 0, 0, 0, 1, 0, 0, 0, 1 ), p0, p1, p2, p3 } ) ) );

	}
```
</details>

### `PhysicalLightingModel.indirect(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Implements the indirect lighting.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `this.indirectDiffuse`
- `this.indirectSpecular`
- `this.ambientOcclusion`

<details><summary>Code</summary>

```typescript
indirect( builder ) {

		this.indirectDiffuse( builder );
		this.indirectSpecular( builder );
		this.ambientOcclusion( builder );

	}
```
</details>

### `PhysicalLightingModel.indirectDiffuse(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Implements the indirect diffuse term.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `reflectedLight.indirectDiffuse.addAssign`
- `irradiance.mul`
- `BRDF_Lambert (from ./BSDF/BRDF_Lambert.js)`

<details><summary>Code</summary>

```typescript
indirectDiffuse( builder ) {

		const { irradiance, reflectedLight } = builder.context;

		reflectedLight.indirectDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor } ) ) );

	}
```
</details>

### `PhysicalLightingModel.indirectSpecular(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Implements the indirect specular term.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `this.sheenSpecularIndirect.addAssign`
- `iblIrradiance.mul`
- `IBLSheenBRDF`
- `clearcoatNormalView.dot( positionViewDirection ).clamp`
- `EnvironmentBRDF (from ./BSDF/EnvironmentBRDF.js)`
- `this.clearcoatSpecularIndirect.addAssign`
- `this.clearcoatRadiance.mul`
- `vec3().toVar`
- `this.computeMultiscattering`
- `singleScattering.add`
- `diffuseColor.mul`
- `totalScattering.r.max( totalScattering.g ).max( totalScattering.b ).oneMinus`
- `reflectedLight.indirectSpecular.addAssign`
- `radiance.mul`
- `multiScattering.mul`
- `reflectedLight.indirectDiffuse.addAssign`
- `diffuse.mul`

**Internal Comments:**
```
// Both indirect specular and indirect diffuse light accumulate here (x2)
```

<details><summary>Code</summary>

```typescript
indirectSpecular( builder ) {

		const { radiance, iblIrradiance, reflectedLight } = builder.context;

		if ( this.sheen === true ) {

			this.sheenSpecularIndirect.addAssign( iblIrradiance.mul(
				sheen,
				IBLSheenBRDF( {
					normal: normalView,
					viewDir: positionViewDirection,
					roughness: sheenRoughness
				} )
			) );

		}

		if ( this.clearcoat === true ) {

			const dotNVcc = clearcoatNormalView.dot( positionViewDirection ).clamp();

			const clearcoatEnv = EnvironmentBRDF( {
				dotNV: dotNVcc,
				specularColor: clearcoatF0,
				specularF90: clearcoatF90,
				roughness: clearcoatRoughness
			} );

			this.clearcoatSpecularIndirect.addAssign( this.clearcoatRadiance.mul( clearcoatEnv ) );

		}

		// Both indirect specular and indirect diffuse light accumulate here

		const singleScattering = vec3().toVar( 'singleScattering' );
		const multiScattering = vec3().toVar( 'multiScattering' );
		const cosineWeightedIrradiance = iblIrradiance.mul( 1 / Math.PI );

		this.computeMultiscattering( singleScattering, multiScattering, specularF90 );

		const totalScattering = singleScattering.add( multiScattering );

		const diffuse = diffuseColor.mul( totalScattering.r.max( totalScattering.g ).max( totalScattering.b ).oneMinus() );

		reflectedLight.indirectSpecular.addAssign( radiance.mul( singleScattering ) );
		reflectedLight.indirectSpecular.addAssign( multiScattering.mul( cosineWeightedIrradiance ) );

		reflectedLight.indirectDiffuse.addAssign( diffuse.mul( cosineWeightedIrradiance ) );

	}
```
</details>

### `PhysicalLightingModel.ambientOcclusion(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Implements the ambient occlusion term.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `normalView.dot( positionViewDirection ).clamp`
- `dotNV.add`
- `roughness.mul( - 16.0 ).oneMinus().negate().exp2`
- `ambientOcclusion.sub( aoNV.pow( aoExp ).oneMinus() ).clamp`
- `this.clearcoatSpecularIndirect.mulAssign`
- `this.sheenSpecularIndirect.mulAssign`
- `reflectedLight.indirectDiffuse.mulAssign`
- `reflectedLight.indirectSpecular.mulAssign`

<details><summary>Code</summary>

```typescript
ambientOcclusion( builder ) {

		const { ambientOcclusion, reflectedLight } = builder.context;

		const dotNV = normalView.dot( positionViewDirection ).clamp(); // @ TODO: Move to core dotNV

		const aoNV = dotNV.add( ambientOcclusion );
		const aoExp = roughness.mul( - 16.0 ).oneMinus().negate().exp2();

		const aoNode = ambientOcclusion.sub( aoNV.pow( aoExp ).oneMinus() ).clamp();

		if ( this.clearcoat === true ) {

			this.clearcoatSpecularIndirect.mulAssign( ambientOcclusion );

		}

		if ( this.sheen === true ) {

			this.sheenSpecularIndirect.mulAssign( ambientOcclusion );

		}

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );
		reflectedLight.indirectSpecular.mulAssign( aoNode );

	}
```
</details>

### `PhysicalLightingModel.finish({ context }: any): void`

**JSDoc:**
```typescript
/**
	 * Used for final lighting accumulations depending on the requested features.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`{ context }`** `any`

**Returns:** `void`

**Calls:**

- `clearcoatNormalView.dot( positionViewDirection ).clamp`
- `F_Schlick (from ./BSDF/F_Schlick.js)`
- `outgoingLight.mul( clearcoat.mul( Fcc ).oneMinus() ).add`
- `this.clearcoatSpecularDirect.add( this.clearcoatSpecularIndirect ).mul`
- `outgoingLight.assign`
- `sheen.r.max( sheen.g ).max( sheen.b ).mul( 0.157 ).oneMinus`
- `outgoingLight.mul( sheenEnergyComp ).add`

<details><summary>Code</summary>

```typescript
finish( { context } ) {

		const { outgoingLight } = context;

		if ( this.clearcoat === true ) {

			const dotNVcc = clearcoatNormalView.dot( positionViewDirection ).clamp();

			const Fcc = F_Schlick( {
				dotVH: dotNVcc,
				f0: clearcoatF0,
				f90: clearcoatF90
			} );

			const clearcoatLight = outgoingLight.mul( clearcoat.mul( Fcc ).oneMinus() ).add( this.clearcoatSpecularDirect.add( this.clearcoatSpecularIndirect ).mul( clearcoat ) );

			outgoingLight.assign( clearcoatLight );

		}

		if ( this.sheen === true ) {

			const sheenEnergyComp = sheen.r.max( sheen.g ).max( sheen.b ).mul( 0.157 ).oneMinus();
			const sheenLight = outgoingLight.mul( sheenEnergyComp ).add( this.sheenSpecularDirect, this.sheenSpecularIndirect );

			outgoingLight.assign( sheenLight );

		}

	}
```
</details>


---

## Classes

### `PhysicalLightingModel`

<details><summary>Class Code</summary>

```ts
class PhysicalLightingModel extends LightingModel {

	/**
	 * Constructs a new physical lighting model.
	 *
	 * @param {boolean} [clearcoat=false] - Whether clearcoat is supported or not.
	 * @param {boolean} [sheen=false] - Whether sheen is supported or not.
	 * @param {boolean} [iridescence=false] - Whether iridescence is supported or not.
	 * @param {boolean} [anisotropy=false] - Whether anisotropy is supported or not.
	 * @param {boolean} [transmission=false] - Whether transmission is supported or not.
	 * @param {boolean} [dispersion=false] - Whether dispersion is supported or not.
	 */
	constructor( clearcoat = false, sheen = false, iridescence = false, anisotropy = false, transmission = false, dispersion = false ) {

		super();

		/**
		 * Whether clearcoat is supported or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.clearcoat = clearcoat;

		/**
		 * Whether sheen is supported or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.sheen = sheen;

		/**
		 * Whether iridescence is supported or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.iridescence = iridescence;

		/**
		 * Whether anisotropy is supported or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.anisotropy = anisotropy;

		/**
		 * Whether transmission is supported or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.transmission = transmission;

		/**
		 * Whether dispersion is supported or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.dispersion = dispersion;

		/**
		 * The clear coat radiance.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.clearcoatRadiance = null;

		/**
		 * The clear coat specular direct.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.clearcoatSpecularDirect = null;

		/**
		 * The clear coat specular indirect.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.clearcoatSpecularIndirect = null;

		/**
		 * The sheen specular direct.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.sheenSpecularDirect = null;

		/**
		 * The sheen specular indirect.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.sheenSpecularIndirect = null;

		/**
		 * The iridescence Fresnel.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.iridescenceFresnel = null;

		/**
		 * The iridescence F0.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.iridescenceF0 = null;

	}

	/**
	 * Depending on what features are requested, the method prepares certain node variables
	 * which are later used for lighting computations.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	start( builder ) {

		if ( this.clearcoat === true ) {

			this.clearcoatRadiance = vec3().toVar( 'clearcoatRadiance' );
			this.clearcoatSpecularDirect = vec3().toVar( 'clearcoatSpecularDirect' );
			this.clearcoatSpecularIndirect = vec3().toVar( 'clearcoatSpecularIndirect' );

		}

		if ( this.sheen === true ) {

			this.sheenSpecularDirect = vec3().toVar( 'sheenSpecularDirect' );
			this.sheenSpecularIndirect = vec3().toVar( 'sheenSpecularIndirect' );

		}

		if ( this.iridescence === true ) {

			const dotNVi = normalView.dot( positionViewDirection ).clamp();

			this.iridescenceFresnel = evalIridescence( {
				outsideIOR: float( 1.0 ),
				eta2: iridescenceIOR,
				cosTheta1: dotNVi,
				thinFilmThickness: iridescenceThickness,
				baseF0: specularColor
			} );

			this.iridescenceF0 = Schlick_to_F0( { f: this.iridescenceFresnel, f90: 1.0, dotVH: dotNVi } );

		}

		if ( this.transmission === true ) {

			const position = positionWorld;
			const v = cameraPosition.sub( positionWorld ).normalize(); // TODO: Create Node for this, same issue in MaterialX
			const n = normalWorld;

			const context = builder.context;

			context.backdrop = getIBLVolumeRefraction(
				n,
				v,
				roughness,
				diffuseColor,
				specularColor,
				specularF90, // specularF90
				position, // positionWorld
				modelWorldMatrix, // modelMatrix
				cameraViewMatrix, // viewMatrix
				cameraProjectionMatrix, // projMatrix
				ior,
				thickness,
				attenuationColor,
				attenuationDistance,
				this.dispersion ? dispersion : null
			);

			context.backdropAlpha = transmission;

			diffuseColor.a.mulAssign( mix( 1, context.backdrop.a, transmission ) );

		}

		super.start( builder );

	}

	// Fdez-Agüera's "Multiple-Scattering Microfacet Model for Real-Time Image Based Lighting"
	// Approximates multi-scattering in order to preserve energy.
	// http://www.jcgt.org/published/0008/01/03/

	computeMultiscattering( singleScatter, multiScatter, specularF90 ) {

		const dotNV = normalView.dot( positionViewDirection ).clamp(); // @ TODO: Move to core dotNV

		const fab = DFGApprox( { roughness, dotNV } );

		const Fr = this.iridescenceF0 ? iridescence.mix( specularColor, this.iridescenceF0 ) : specularColor;

		const FssEss = Fr.mul( fab.x ).add( specularF90.mul( fab.y ) );

		const Ess = fab.x.add( fab.y );
		const Ems = Ess.oneMinus();

		const Favg = specularColor.add( specularColor.oneMinus().mul( 0.047619 ) ); // 1/21
		const Fms = FssEss.mul( Favg ).div( Ems.mul( Favg ).oneMinus() );

		singleScatter.addAssign( FssEss );
		multiScatter.addAssign( Fms.mul( Ems ) );

	}

	/**
	 * Implements the direct light.
	 *
	 * @param {Object} lightData - The light data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	direct( { lightDirection, lightColor, reflectedLight }, /* builder */ ) {

		const dotNL = normalView.dot( lightDirection ).clamp();
		const irradiance = dotNL.mul( lightColor );

		if ( this.sheen === true ) {

			this.sheenSpecularDirect.addAssign( irradiance.mul( BRDF_Sheen( { lightDirection } ) ) );

		}

		if ( this.clearcoat === true ) {

			const dotNLcc = clearcoatNormalView.dot( lightDirection ).clamp();
			const ccIrradiance = dotNLcc.mul( lightColor );

			this.clearcoatSpecularDirect.addAssign( ccIrradiance.mul( BRDF_GGX( { lightDirection, f0: clearcoatF0, f90: clearcoatF90, roughness: clearcoatRoughness, normalView: clearcoatNormalView } ) ) );

		}

		reflectedLight.directDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor: diffuseColor.rgb } ) ) );

		reflectedLight.directSpecular.addAssign( irradiance.mul( BRDF_GGX( { lightDirection, f0: specularColor, f90: 1, roughness, iridescence: this.iridescence, f: this.iridescenceFresnel, USE_IRIDESCENCE: this.iridescence, USE_ANISOTROPY: this.anisotropy } ) ) );

	}

	/**
	 * This method is intended for implementing the direct light term for
	 * rect area light nodes.
	 *
	 * @param {Object} input - The input data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	directRectArea( { lightColor, lightPosition, halfWidth, halfHeight, reflectedLight, ltc_1, ltc_2 }, /* builder */ ) {

		const p0 = lightPosition.add( halfWidth ).sub( halfHeight ); // counterclockwise; light shines in local neg z direction
		const p1 = lightPosition.sub( halfWidth ).sub( halfHeight );
		const p2 = lightPosition.sub( halfWidth ).add( halfHeight );
		const p3 = lightPosition.add( halfWidth ).add( halfHeight );

		const N = normalView;
		const V = positionViewDirection;
		const P = positionView.toVar();

		const uv = LTC_Uv( { N, V, roughness } );

		const t1 = ltc_1.sample( uv ).toVar();
		const t2 = ltc_2.sample( uv ).toVar();

		const mInv = mat3(
			vec3( t1.x, 0, t1.y ),
			vec3( 0, 1, 0 ),
			vec3( t1.z, 0, t1.w )
		).toVar();

		// LTC Fresnel Approximation by Stephen Hill
		// http://blog.selfshadow.com/publications/s2016-advances/s2016_ltc_fresnel.pdf
		const fresnel = specularColor.mul( t2.x ).add( specularColor.oneMinus().mul( t2.y ) ).toVar();

		reflectedLight.directSpecular.addAssign( lightColor.mul( fresnel ).mul( LTC_Evaluate( { N, V, P, mInv, p0, p1, p2, p3 } ) ) );

		reflectedLight.directDiffuse.addAssign( lightColor.mul( diffuseColor ).mul( LTC_Evaluate( { N, V, P, mInv: mat3( 1, 0, 0, 0, 1, 0, 0, 0, 1 ), p0, p1, p2, p3 } ) ) );

	}

	/**
	 * Implements the indirect lighting.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	indirect( builder ) {

		this.indirectDiffuse( builder );
		this.indirectSpecular( builder );
		this.ambientOcclusion( builder );

	}

	/**
	 * Implements the indirect diffuse term.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	indirectDiffuse( builder ) {

		const { irradiance, reflectedLight } = builder.context;

		reflectedLight.indirectDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor } ) ) );

	}

	/**
	 * Implements the indirect specular term.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	indirectSpecular( builder ) {

		const { radiance, iblIrradiance, reflectedLight } = builder.context;

		if ( this.sheen === true ) {

			this.sheenSpecularIndirect.addAssign( iblIrradiance.mul(
				sheen,
				IBLSheenBRDF( {
					normal: normalView,
					viewDir: positionViewDirection,
					roughness: sheenRoughness
				} )
			) );

		}

		if ( this.clearcoat === true ) {

			const dotNVcc = clearcoatNormalView.dot( positionViewDirection ).clamp();

			const clearcoatEnv = EnvironmentBRDF( {
				dotNV: dotNVcc,
				specularColor: clearcoatF0,
				specularF90: clearcoatF90,
				roughness: clearcoatRoughness
			} );

			this.clearcoatSpecularIndirect.addAssign( this.clearcoatRadiance.mul( clearcoatEnv ) );

		}

		// Both indirect specular and indirect diffuse light accumulate here

		const singleScattering = vec3().toVar( 'singleScattering' );
		const multiScattering = vec3().toVar( 'multiScattering' );
		const cosineWeightedIrradiance = iblIrradiance.mul( 1 / Math.PI );

		this.computeMultiscattering( singleScattering, multiScattering, specularF90 );

		const totalScattering = singleScattering.add( multiScattering );

		const diffuse = diffuseColor.mul( totalScattering.r.max( totalScattering.g ).max( totalScattering.b ).oneMinus() );

		reflectedLight.indirectSpecular.addAssign( radiance.mul( singleScattering ) );
		reflectedLight.indirectSpecular.addAssign( multiScattering.mul( cosineWeightedIrradiance ) );

		reflectedLight.indirectDiffuse.addAssign( diffuse.mul( cosineWeightedIrradiance ) );

	}

	/**
	 * Implements the ambient occlusion term.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	ambientOcclusion( builder ) {

		const { ambientOcclusion, reflectedLight } = builder.context;

		const dotNV = normalView.dot( positionViewDirection ).clamp(); // @ TODO: Move to core dotNV

		const aoNV = dotNV.add( ambientOcclusion );
		const aoExp = roughness.mul( - 16.0 ).oneMinus().negate().exp2();

		const aoNode = ambientOcclusion.sub( aoNV.pow( aoExp ).oneMinus() ).clamp();

		if ( this.clearcoat === true ) {

			this.clearcoatSpecularIndirect.mulAssign( ambientOcclusion );

		}

		if ( this.sheen === true ) {

			this.sheenSpecularIndirect.mulAssign( ambientOcclusion );

		}

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );
		reflectedLight.indirectSpecular.mulAssign( aoNode );

	}

	/**
	 * Used for final lighting accumulations depending on the requested features.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	finish( { context } ) {

		const { outgoingLight } = context;

		if ( this.clearcoat === true ) {

			const dotNVcc = clearcoatNormalView.dot( positionViewDirection ).clamp();

			const Fcc = F_Schlick( {
				dotVH: dotNVcc,
				f0: clearcoatF0,
				f90: clearcoatF90
			} );

			const clearcoatLight = outgoingLight.mul( clearcoat.mul( Fcc ).oneMinus() ).add( this.clearcoatSpecularDirect.add( this.clearcoatSpecularIndirect ).mul( clearcoat ) );

			outgoingLight.assign( clearcoatLight );

		}

		if ( this.sheen === true ) {

			const sheenEnergyComp = sheen.r.max( sheen.g ).max( sheen.b ).mul( 0.157 ).oneMinus();
			const sheenLight = outgoingLight.mul( sheenEnergyComp ).add( this.sheenSpecularDirect, this.sheenSpecularIndirect );

			outgoingLight.assign( sheenLight );

		}

	}

}
```
</details>

#### Methods

##### `start(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
start( builder ) {

		if ( this.clearcoat === true ) {

			this.clearcoatRadiance = vec3().toVar( 'clearcoatRadiance' );
			this.clearcoatSpecularDirect = vec3().toVar( 'clearcoatSpecularDirect' );
			this.clearcoatSpecularIndirect = vec3().toVar( 'clearcoatSpecularIndirect' );

		}

		if ( this.sheen === true ) {

			this.sheenSpecularDirect = vec3().toVar( 'sheenSpecularDirect' );
			this.sheenSpecularIndirect = vec3().toVar( 'sheenSpecularIndirect' );

		}

		if ( this.iridescence === true ) {

			const dotNVi = normalView.dot( positionViewDirection ).clamp();

			this.iridescenceFresnel = evalIridescence( {
				outsideIOR: float( 1.0 ),
				eta2: iridescenceIOR,
				cosTheta1: dotNVi,
				thinFilmThickness: iridescenceThickness,
				baseF0: specularColor
			} );

			this.iridescenceF0 = Schlick_to_F0( { f: this.iridescenceFresnel, f90: 1.0, dotVH: dotNVi } );

		}

		if ( this.transmission === true ) {

			const position = positionWorld;
			const v = cameraPosition.sub( positionWorld ).normalize(); // TODO: Create Node for this, same issue in MaterialX
			const n = normalWorld;

			const context = builder.context;

			context.backdrop = getIBLVolumeRefraction(
				n,
				v,
				roughness,
				diffuseColor,
				specularColor,
				specularF90, // specularF90
				position, // positionWorld
				modelWorldMatrix, // modelMatrix
				cameraViewMatrix, // viewMatrix
				cameraProjectionMatrix, // projMatrix
				ior,
				thickness,
				attenuationColor,
				attenuationDistance,
				this.dispersion ? dispersion : null
			);

			context.backdropAlpha = transmission;

			diffuseColor.a.mulAssign( mix( 1, context.backdrop.a, transmission ) );

		}

		super.start( builder );

	}
```
</details>

##### `computeMultiscattering(singleScatter: any, multiScatter: any, specularF90: any): void`

<details><summary>Code</summary>

```ts
computeMultiscattering( singleScatter, multiScatter, specularF90 ) {

		const dotNV = normalView.dot( positionViewDirection ).clamp(); // @ TODO: Move to core dotNV

		const fab = DFGApprox( { roughness, dotNV } );

		const Fr = this.iridescenceF0 ? iridescence.mix( specularColor, this.iridescenceF0 ) : specularColor;

		const FssEss = Fr.mul( fab.x ).add( specularF90.mul( fab.y ) );

		const Ess = fab.x.add( fab.y );
		const Ems = Ess.oneMinus();

		const Favg = specularColor.add( specularColor.oneMinus().mul( 0.047619 ) ); // 1/21
		const Fms = FssEss.mul( Favg ).div( Ems.mul( Favg ).oneMinus() );

		singleScatter.addAssign( FssEss );
		multiScatter.addAssign( Fms.mul( Ems ) );

	}
```
</details>

##### `direct({ lightDirection, lightColor, reflectedLight }: any): void`

<details><summary>Code</summary>

```ts
direct( { lightDirection, lightColor, reflectedLight }, /* builder */ ) {

		const dotNL = normalView.dot( lightDirection ).clamp();
		const irradiance = dotNL.mul( lightColor );

		if ( this.sheen === true ) {

			this.sheenSpecularDirect.addAssign( irradiance.mul( BRDF_Sheen( { lightDirection } ) ) );

		}

		if ( this.clearcoat === true ) {

			const dotNLcc = clearcoatNormalView.dot( lightDirection ).clamp();
			const ccIrradiance = dotNLcc.mul( lightColor );

			this.clearcoatSpecularDirect.addAssign( ccIrradiance.mul( BRDF_GGX( { lightDirection, f0: clearcoatF0, f90: clearcoatF90, roughness: clearcoatRoughness, normalView: clearcoatNormalView } ) ) );

		}

		reflectedLight.directDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor: diffuseColor.rgb } ) ) );

		reflectedLight.directSpecular.addAssign( irradiance.mul( BRDF_GGX( { lightDirection, f0: specularColor, f90: 1, roughness, iridescence: this.iridescence, f: this.iridescenceFresnel, USE_IRIDESCENCE: this.iridescence, USE_ANISOTROPY: this.anisotropy } ) ) );

	}
```
</details>

##### `directRectArea({ lightColor, lightPosition, halfWidth, halfHeight, reflectedLight, ltc_1, ltc_2 }: any): void`

<details><summary>Code</summary>

```ts
directRectArea( { lightColor, lightPosition, halfWidth, halfHeight, reflectedLight, ltc_1, ltc_2 }, /* builder */ ) {

		const p0 = lightPosition.add( halfWidth ).sub( halfHeight ); // counterclockwise; light shines in local neg z direction
		const p1 = lightPosition.sub( halfWidth ).sub( halfHeight );
		const p2 = lightPosition.sub( halfWidth ).add( halfHeight );
		const p3 = lightPosition.add( halfWidth ).add( halfHeight );

		const N = normalView;
		const V = positionViewDirection;
		const P = positionView.toVar();

		const uv = LTC_Uv( { N, V, roughness } );

		const t1 = ltc_1.sample( uv ).toVar();
		const t2 = ltc_2.sample( uv ).toVar();

		const mInv = mat3(
			vec3( t1.x, 0, t1.y ),
			vec3( 0, 1, 0 ),
			vec3( t1.z, 0, t1.w )
		).toVar();

		// LTC Fresnel Approximation by Stephen Hill
		// http://blog.selfshadow.com/publications/s2016-advances/s2016_ltc_fresnel.pdf
		const fresnel = specularColor.mul( t2.x ).add( specularColor.oneMinus().mul( t2.y ) ).toVar();

		reflectedLight.directSpecular.addAssign( lightColor.mul( fresnel ).mul( LTC_Evaluate( { N, V, P, mInv, p0, p1, p2, p3 } ) ) );

		reflectedLight.directDiffuse.addAssign( lightColor.mul( diffuseColor ).mul( LTC_Evaluate( { N, V, P, mInv: mat3( 1, 0, 0, 0, 1, 0, 0, 0, 1 ), p0, p1, p2, p3 } ) ) );

	}
```
</details>

##### `indirect(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
indirect( builder ) {

		this.indirectDiffuse( builder );
		this.indirectSpecular( builder );
		this.ambientOcclusion( builder );

	}
```
</details>

##### `indirectDiffuse(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
indirectDiffuse( builder ) {

		const { irradiance, reflectedLight } = builder.context;

		reflectedLight.indirectDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor } ) ) );

	}
```
</details>

##### `indirectSpecular(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
indirectSpecular( builder ) {

		const { radiance, iblIrradiance, reflectedLight } = builder.context;

		if ( this.sheen === true ) {

			this.sheenSpecularIndirect.addAssign( iblIrradiance.mul(
				sheen,
				IBLSheenBRDF( {
					normal: normalView,
					viewDir: positionViewDirection,
					roughness: sheenRoughness
				} )
			) );

		}

		if ( this.clearcoat === true ) {

			const dotNVcc = clearcoatNormalView.dot( positionViewDirection ).clamp();

			const clearcoatEnv = EnvironmentBRDF( {
				dotNV: dotNVcc,
				specularColor: clearcoatF0,
				specularF90: clearcoatF90,
				roughness: clearcoatRoughness
			} );

			this.clearcoatSpecularIndirect.addAssign( this.clearcoatRadiance.mul( clearcoatEnv ) );

		}

		// Both indirect specular and indirect diffuse light accumulate here

		const singleScattering = vec3().toVar( 'singleScattering' );
		const multiScattering = vec3().toVar( 'multiScattering' );
		const cosineWeightedIrradiance = iblIrradiance.mul( 1 / Math.PI );

		this.computeMultiscattering( singleScattering, multiScattering, specularF90 );

		const totalScattering = singleScattering.add( multiScattering );

		const diffuse = diffuseColor.mul( totalScattering.r.max( totalScattering.g ).max( totalScattering.b ).oneMinus() );

		reflectedLight.indirectSpecular.addAssign( radiance.mul( singleScattering ) );
		reflectedLight.indirectSpecular.addAssign( multiScattering.mul( cosineWeightedIrradiance ) );

		reflectedLight.indirectDiffuse.addAssign( diffuse.mul( cosineWeightedIrradiance ) );

	}
```
</details>

##### `ambientOcclusion(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
ambientOcclusion( builder ) {

		const { ambientOcclusion, reflectedLight } = builder.context;

		const dotNV = normalView.dot( positionViewDirection ).clamp(); // @ TODO: Move to core dotNV

		const aoNV = dotNV.add( ambientOcclusion );
		const aoExp = roughness.mul( - 16.0 ).oneMinus().negate().exp2();

		const aoNode = ambientOcclusion.sub( aoNV.pow( aoExp ).oneMinus() ).clamp();

		if ( this.clearcoat === true ) {

			this.clearcoatSpecularIndirect.mulAssign( ambientOcclusion );

		}

		if ( this.sheen === true ) {

			this.sheenSpecularIndirect.mulAssign( ambientOcclusion );

		}

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );
		reflectedLight.indirectSpecular.mulAssign( aoNode );

	}
```
</details>

##### `finish({ context }: any): void`

<details><summary>Code</summary>

```ts
finish( { context } ) {

		const { outgoingLight } = context;

		if ( this.clearcoat === true ) {

			const dotNVcc = clearcoatNormalView.dot( positionViewDirection ).clamp();

			const Fcc = F_Schlick( {
				dotVH: dotNVcc,
				f0: clearcoatF0,
				f90: clearcoatF90
			} );

			const clearcoatLight = outgoingLight.mul( clearcoat.mul( Fcc ).oneMinus() ).add( this.clearcoatSpecularDirect.add( this.clearcoatSpecularIndirect ).mul( clearcoat ) );

			outgoingLight.assign( clearcoatLight );

		}

		if ( this.sheen === true ) {

			const sheenEnergyComp = sheen.r.max( sheen.g ).max( sheen.b ).mul( 0.157 ).oneMinus();
			const sheenLight = outgoingLight.mul( sheenEnergyComp ).add( this.sheenSpecularDirect, this.sheenSpecularIndirect );

			outgoingLight.assign( sheenLight );

		}

	}
```
</details>


---