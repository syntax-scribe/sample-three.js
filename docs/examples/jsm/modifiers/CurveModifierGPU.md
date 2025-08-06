[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CurveModifierGPU.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 20 |
| 📊 Variables & Constants | 17 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/modifiers/CurveModifierGPU.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataTexture` | `three` |
| `DataUtils` | `three` |
| `RGBAFormat` | `three` |
| `HalfFloatType` | `three` |
| `RepeatWrapping` | `three` |
| `Mesh` | `three` |
| `InstancedMesh` | `three` |
| `LinearFilter` | `three` |
| `modelWorldMatrix` | `three/tsl` |
| `normalLocal` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `vec4` | `three/tsl` |
| `mat3` | `three/tsl` |
| `varyingProperty` | `three/tsl` |
| `texture` | `three/tsl` |
| `reference` | `three/tsl` |
| `Fn` | `three/tsl` |
| `select` | `three/tsl` |
| `positionLocal` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `CHANNELS` | `4` | let/var | `4` | ✗ |
| `TEXTURE_WIDTH` | `1024` | let/var | `1024` | ✗ |
| `TEXTURE_HEIGHT` | `4` | let/var | `4` | ✗ |
| `dataArray` | `Uint16Array<ArrayBuffer>` | let/var | `new Uint16Array( TEXTURE_WIDTH * TEXTURE_HEIGHT * numberOfCurves * CHANNELS )` | ✗ |
| `dataTexture` | `any` | let/var | `new DataTexture( dataArray, TEXTURE_WIDTH, TEXTURE_HEIGHT * numberOfCurves, R...` | ✗ |
| `rowIndex` | `number` | let/var | `i % TEXTURE_WIDTH` | ✗ |
| `pt` | `any` | let/var | `points[ i ]` | ✗ |
| `image` | `any` | let/var | `texture.image` | ✗ |
| `i` | `number` | let/var | `CHANNELS * TEXTURE_WIDTH * o` | ✗ |
| `spineTexture` | `any` | let/var | `uniforms.spineTexture` | ✗ |
| `textureStacks` | `number` | let/var | `TEXTURE_HEIGHT / 4` | ✗ |
| `textureScale` | `number` | let/var | `TEXTURE_HEIGHT * numberOfCurves` | ✗ |
| `spinePos` | `any` | let/var | `texture( spineTexture, vec2( mt, rowOffset.add( 0.5 ).div( textureScale ) ) )...` | ✗ |
| `a` | `any` | let/var | `texture( spineTexture, vec2( mt, rowOffset.add( 1.5 ).div( textureScale ) ) )...` | ✗ |
| `b` | `any` | let/var | `texture( spineTexture, vec2( mt, rowOffset.add( 2.5 ).div( textureScale ) ) )...` | ✗ |
| `c` | `any` | let/var | `texture( spineTexture, vec2( mt, rowOffset.add( 3.5 ).div( textureScale ) ) )...` | ✗ |
| `materials` | `any[]` | let/var | `[]` | ✗ |


---

## Functions

### `initSplineTexture(numberOfCurves: number): DataTexture`

**JSDoc:**
```typescript
/**
 * Make a new DataTexture to store the descriptions of the curves.
 *
 * @private
 * @param {number} [numberOfCurves=1] - The number of curves needed to be described by this texture.
 * @returns  {DataTexture} The new data texture.
 */
```

**Parameters:**

- **`numberOfCurves`** `number`

**Returns:** `DataTexture`

<details><summary>Code</summary>

```typescript
function initSplineTexture( numberOfCurves = 1 ) {

	const dataArray = new Uint16Array( TEXTURE_WIDTH * TEXTURE_HEIGHT * numberOfCurves * CHANNELS );
	const dataTexture = new DataTexture(
		dataArray,
		TEXTURE_WIDTH,
		TEXTURE_HEIGHT * numberOfCurves,
		RGBAFormat,
		HalfFloatType
	);

	dataTexture.wrapS = RepeatWrapping;
	dataTexture.wrapY = RepeatWrapping;
	dataTexture.magFilter = LinearFilter;
	dataTexture.minFilter = LinearFilter;
	dataTexture.needsUpdate = true;

	return dataTexture;

}
```
</details>

### `updateSplineTexture(texture: DataTexture, splineCurve: Curve, offset: number): void`

**JSDoc:**
```typescript
/**
 * Write the curve description to the data texture.
 *
 * @private
 * @param {DataTexture} texture - The data texture to write to.
 * @param {Curve} splineCurve - The curve to describe.
 * @param {number} [offset=0] - Which curve slot to write to.
 */
```

**Parameters:**

- **`texture`** `DataTexture`
- **`splineCurve`** `Curve`
- **`offset`** `number`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `splineCurve.updateArcLengths`
- `splineCurve.getSpacedPoints`
- `splineCurve.computeFrenetFrames`
- `setTextureValue`

<details><summary>Code</summary>

```typescript
function updateSplineTexture( texture, splineCurve, offset = 0 ) {

	const numberOfPoints = Math.floor( TEXTURE_WIDTH * ( TEXTURE_HEIGHT / 4 ) );
	splineCurve.arcLengthDivisions = numberOfPoints / 2;
	splineCurve.updateArcLengths();
	const points = splineCurve.getSpacedPoints( numberOfPoints );
	const frenetFrames = splineCurve.computeFrenetFrames( numberOfPoints, true );

	for ( let i = 0; i < numberOfPoints; i ++ ) {

		const rowOffset = Math.floor( i / TEXTURE_WIDTH );
		const rowIndex = i % TEXTURE_WIDTH;

		let pt = points[ i ];
		setTextureValue( texture, rowIndex, pt.x, pt.y, pt.z, 0 + rowOffset + ( TEXTURE_HEIGHT * offset ) );
		pt = frenetFrames.tangents[ i ];
		setTextureValue( texture, rowIndex, pt.x, pt.y, pt.z, 1 + rowOffset + ( TEXTURE_HEIGHT * offset ) );
		pt = frenetFrames.normals[ i ];
		setTextureValue( texture, rowIndex, pt.x, pt.y, pt.z, 2 + rowOffset + ( TEXTURE_HEIGHT * offset ) );
		pt = frenetFrames.binormals[ i ];
		setTextureValue( texture, rowIndex, pt.x, pt.y, pt.z, 3 + rowOffset + ( TEXTURE_HEIGHT * offset ) );

	}

	texture.needsUpdate = true;

}
```
</details>

### `setTextureValue(texture: any, index: any, x: any, y: any, z: any, o: any): void`

**Parameters:**

- **`texture`** `any`
- **`index`** `any`
- **`x`** `any`
- **`y`** `any`
- **`z`** `any`
- **`o`** `any`

**Returns:** `void`

**Calls:**

- `DataUtils.toHalfFloat`

<details><summary>Code</summary>

```typescript
function setTextureValue( texture, index, x, y, z, o ) {

	const image = texture.image;
	const { data } = image;
	const i = CHANNELS * TEXTURE_WIDTH * o; // Row Offset

	data[ index * CHANNELS + i + 0 ] = DataUtils.toHalfFloat( x );
	data[ index * CHANNELS + i + 1 ] = DataUtils.toHalfFloat( y );
	data[ index * CHANNELS + i + 2 ] = DataUtils.toHalfFloat( z );
	data[ index * CHANNELS + i + 3 ] = DataUtils.toHalfFloat( 1 );

}
```
</details>

### `getUniforms(splineTexture: DataTexture): any`

**JSDoc:**
```typescript
/**
 * Create a new set of uniforms for describing the curve modifier.
 *
 * @private
 * @param {DataTexture} splineTexture - Which holds the curve description.
 * @returns {Object} The uniforms object.
 */
```

**Parameters:**

- **`splineTexture`** `DataTexture`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getUniforms( splineTexture ) {

	return {
		spineTexture: splineTexture,
		pathOffset: 0, // time of path curve
		pathSegment: 1, // fractional length of path
		spineOffset: 161,
		spineLength: 400,
		flow: 1, // int
	};

}
```
</details>

### `modifyShader(material: any, uniforms: any, numberOfCurves: any): void`

**Parameters:**

- **`material`** `any`
- **`uniforms`** `any`
- **`numberOfCurves`** `any`

**Returns:** `void`

**Calls:**

- `reference (from three/tsl)`
- `complex_call_3837`
- `varyingProperty (from three/tsl)`

<details><summary>Code</summary>

```typescript
function modifyShader( material, uniforms, numberOfCurves ) {

	const spineTexture = uniforms.spineTexture;

	const pathOffset = reference( 'pathOffset', 'float', uniforms );
	const pathSegment = reference( 'pathSegment', 'float', uniforms );
	const spineOffset = reference( 'spineOffset', 'float', uniforms );
	const spineLength = reference( 'spineLength', 'float', uniforms );
	const flow = reference( 'flow', 'float', uniforms );

	material.positionNode = Fn( () => {

		const textureStacks = TEXTURE_HEIGHT / 4;
		const textureScale = TEXTURE_HEIGHT * numberOfCurves;

		const worldPos = modelWorldMatrix.mul( vec4( positionLocal, 1 ) ).toVar();

		const bend = flow.greaterThan( 0 ).toVar();
		const xWeight = select( bend, 0, 1 ).toVar();

		const spinePortion = select( bend, worldPos.x.add( spineOffset ).div( spineLength ), 0 );
		const mt = spinePortion.mul( pathSegment ).add( pathOffset ).mul( textureStacks ).toVar();

		mt.assign( mt.mod( textureStacks ) );

		const rowOffset = mt.floor().toVar();

		const spinePos = texture( spineTexture, vec2( mt, rowOffset.add( 0.5 ).div( textureScale ) ) ).xyz;

		const a = texture( spineTexture, vec2( mt, rowOffset.add( 1.5 ).div( textureScale ) ) ).xyz;
		const b = texture( spineTexture, vec2( mt, rowOffset.add( 2.5 ).div( textureScale ) ) ).xyz;
		const c = texture( spineTexture, vec2( mt, rowOffset.add( 3.5 ).div( textureScale ) ) ).xyz;

		const basis = mat3( a, b, c ).toVar();

		varyingProperty( 'vec3', 'curveNormal' ).assign( basis.mul( normalLocal ) );

		return basis.mul( vec3( worldPos.x.mul( xWeight ), worldPos.y, worldPos.z ) ).add( spinePos );

	} )();

	material.normalNode = varyingProperty( 'vec3', 'curveNormal' );

}
```
</details>

### `Flow.updateCurve(index: number, curve: Curve): void`

**JSDoc:**
```typescript
/**
	 * Updates the curve for the given curve index.
	 *
	 * @param {number} index - The curve index.
	 * @param {Curve} curve - The curve that should be used to bend the mesh.
	 */
```

**Parameters:**

- **`index`** `number`
- **`curve`** `Curve`

**Returns:** `void`

**Calls:**

- `Error`
- `curve.getLength`
- `updateSplineTexture`

<details><summary>Code</summary>

```typescript
updateCurve( index, curve ) {

		if ( index >= this.curveArray.length ) throw Error( 'Flow: Index out of range.' );

		const curveLength = curve.getLength();

		this.uniforms.spineLength = curveLength;
		this.curveLengthArray[ index ] = curveLength;
		this.curveArray[ index ] = curve;

		updateSplineTexture( this.splineTexture, curve, index );

	}
```
</details>

### `Flow.moveAlongCurve(amount: number): void`

**JSDoc:**
```typescript
/**
	 * Moves the mesh along the curve.
	 *
	 * @param {number} amount - The offset.
	 */
```

**Parameters:**

- **`amount`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
moveAlongCurve( amount ) {

		this.uniforms.pathOffset += amount;

	}
```
</details>


---

## Classes

### `Flow`

<details><summary>Class Code</summary>

```ts
export class Flow {

	/**
	 * Constructs a new Flow instance.
	 *
	 * @param {Mesh} mesh - The mesh to clone and modify to bend around the curve.
	 * @param {number} numberOfCurves - The amount of space that should preallocated for additional curves.
	 */
	constructor( mesh, numberOfCurves = 1 ) {

		const obj3D = mesh.clone();
		const splineTexture = initSplineTexture( numberOfCurves );
		const uniforms = getUniforms( splineTexture );

		obj3D.traverse( function ( child ) {

			if (
				child instanceof Mesh ||
				child instanceof InstancedMesh
			) {

				if ( Array.isArray( child.material ) ) {

					const materials = [];

					for ( const material of child.material ) {

						const newMaterial = material.clone();
						modifyShader( newMaterial, uniforms, numberOfCurves );
						materials.push( newMaterial );

					}

					child.material = materials;

				} else {

					child.material = child.material.clone();
					modifyShader( child.material, uniforms, numberOfCurves );

				}

			}

		} );

		this.curveArray = new Array( numberOfCurves );
		this.curveLengthArray = new Array( numberOfCurves );

		this.object3D = obj3D;
		this.splineTexture = splineTexture;
		this.uniforms = uniforms;

	}

	/**
	 * Updates the curve for the given curve index.
	 *
	 * @param {number} index - The curve index.
	 * @param {Curve} curve - The curve that should be used to bend the mesh.
	 */
	updateCurve( index, curve ) {

		if ( index >= this.curveArray.length ) throw Error( 'Flow: Index out of range.' );

		const curveLength = curve.getLength();

		this.uniforms.spineLength = curveLength;
		this.curveLengthArray[ index ] = curveLength;
		this.curveArray[ index ] = curve;

		updateSplineTexture( this.splineTexture, curve, index );

	}

	/**
	 * Moves the mesh along the curve.
	 *
	 * @param {number} amount - The offset.
	 */
	moveAlongCurve( amount ) {

		this.uniforms.pathOffset += amount;

	}

}
```
</details>

#### Methods

##### `updateCurve(index: number, curve: Curve): void`

<details><summary>Code</summary>

```ts
updateCurve( index, curve ) {

		if ( index >= this.curveArray.length ) throw Error( 'Flow: Index out of range.' );

		const curveLength = curve.getLength();

		this.uniforms.spineLength = curveLength;
		this.curveLengthArray[ index ] = curveLength;
		this.curveArray[ index ] = curve;

		updateSplineTexture( this.splineTexture, curve, index );

	}
```
</details>

##### `moveAlongCurve(amount: number): void`

<details><summary>Code</summary>

```ts
moveAlongCurve( amount ) {

		this.uniforms.pathOffset += amount;

	}
```
</details>


---