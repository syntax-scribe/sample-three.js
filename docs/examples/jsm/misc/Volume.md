[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Volume.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 17 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 26 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/misc/Volume.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix3` | `three` |
| `Matrix4` | `three` |
| `Vector3` | `three` |
| `VolumeSlice` | `../misc/VolumeSlice.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `lowerThreshold` | `number` | let/var | `- Infinity` | ✗ |
| `upperThreshold` | `number` | let/var | `Infinity` | ✗ |
| `x` | `number` | let/var | `index - z * this.yLength * this.xLength - y * this.xLength` | ✗ |
| `length` | `any` | let/var | `this.data.length` | ✗ |
| `firstSpacing` | `any` | let/var | `*not shown*` | ✗ |
| `secondSpacing` | `any` | let/var | `*not shown*` | ✗ |
| `positionOffset` | `any` | let/var | `*not shown*` | ✗ |
| `IJKIndex` | `any` | let/var | `*not shown*` | ✗ |
| `axisInIJK` | `any` | let/var | `new Vector3()` | ✗ |
| `firstDirection` | `any` | let/var | `new Vector3()` | ✗ |
| `secondDirection` | `any` | let/var | `new Vector3()` | ✗ |
| `volume` | `this` | let/var | `this` | ✗ |
| `dimensions` | `any` | let/var | `new Vector3( this.xLength, this.yLength, this.zLength )` | ✗ |
| `base` | `any[]` | let/var | `[ new Vector3( 1, 0, 0 ), new Vector3( 0, 1, 0 ), new Vector3( 0, 0, 1 ) ]` | ✗ |
| `si` | `any` | let/var | `( iDirection === axisInIJK ) ? IJKIndex : ( iDirection.arglet === 'i' ? i : j )` | ✗ |
| `sj` | `any` | let/var | `( jDirection === axisInIJK ) ? IJKIndex : ( jDirection.arglet === 'i' ? i : j )` | ✗ |
| `sk` | `any` | let/var | `( kDirection === axisInIJK ) ? IJKIndex : ( kDirection.arglet === 'i' ? i : j )` | ✗ |
| `accessI` | `any` | let/var | `( iDirection.dot( base[ 0 ] ) > 0 ) ? si : ( volume.xLength - 1 ) - si` | ✗ |
| `accessJ` | `any` | let/var | `( jDirection.dot( base[ 1 ] ) > 0 ) ? sj : ( volume.yLength - 1 ) - sj` | ✗ |
| `accessK` | `any` | let/var | `( kDirection.dot( base[ 2 ] ) > 0 ) ? sk : ( volume.zLength - 1 ) - sk` | ✗ |
| `slice` | `VolumeSlice` | let/var | `new VolumeSlice( this, index, axis )` | ✗ |
| `min` | `number` | let/var | `Infinity` | ✗ |
| `max` | `number` | let/var | `- Infinity` | ✗ |
| `datasize` | `any` | let/var | `this.data.length` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `value` | `TypedArray` | let/var | `this.data[ i ]` | ✗ |


---

## Functions

### `Volume.getData(i: number, j: number, k: number): number`

**JSDoc:**
```typescript
/**
	 * Shortcut for data[access(i,j,k)].
	 *
	 * @param {number} i - First coordinate.
	 * @param {number} j - Second coordinate.
	 * @param {number} k - Third coordinate.
	 * @returns {number} The value in the data array.
	 */
```

**Parameters:**

- **`i`** `number`
- **`j`** `number`
- **`k`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getData( i, j, k ) {

		return this.data[ k * this.xLength * this.yLength + j * this.xLength + i ];

	}
```
</details>

### `Volume.access(i: number, j: number, k: number): number`

**JSDoc:**
```typescript
/**
	 * Compute the index in the data array corresponding to the given coordinates in IJK system.
	 *
	 * @param {number} i - First coordinate.
	 * @param {number} j - Second coordinate.
	 * @param {number} k - Third coordinate.
	 * @returns {number} The index.
	 */
```

**Parameters:**

- **`i`** `number`
- **`j`** `number`
- **`k`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
access( i, j, k ) {

		return k * this.xLength * this.yLength + j * this.xLength + i;

	}
```
</details>

### `Volume.reverseAccess(index: number): number[]`

**JSDoc:**
```typescript
/**
	 * Retrieve the IJK coordinates of the voxel corresponding of the given index in the data.
	 *
	 * @param {number} index - Index of the voxel.
	 * @returns {Array<number>} The IJK coordinates as `[x,y,z]`.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `number[]`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
reverseAccess( index ) {

		const z = Math.floor( index / ( this.yLength * this.xLength ) );
		const y = Math.floor( ( index - z * this.yLength * this.xLength ) / this.xLength );
		const x = index - z * this.yLength * this.xLength - y * this.xLength;
		return [ x, y, z ];

	}
```
</details>

### `Volume.map(functionToMap: Function, context: any): Volume`

**JSDoc:**
```typescript
/**
	 * Apply a function to all the voxels, be careful, the value will be replaced.
	 *
	 * @param {Function} functionToMap A function to apply to every voxel, will be called with the following parameters:
	 * value of the voxel, index of the voxel, the data (TypedArray).
	 * @param {Object} context - You can specify a context in which call the function, default if this Volume.
	 * @returns {Volume} A reference to this instance.
	 */
```

**Parameters:**

- **`functionToMap`** `Function`
- **`context`** `any`

**Returns:** `Volume`

**Calls:**

- `functionToMap.call`

<details><summary>Code</summary>

```typescript
map( functionToMap, context ) {

		const length = this.data.length;
		context = context || this;

		for ( let i = 0; i < length; i ++ ) {

			this.data[ i ] = functionToMap.call( context, this.data[ i ], i, this.data );

		}

		return this;

	}
```
</details>

### `Volume.extractPerpendicularPlane(axis: "x" | "y" | "z", RASIndex: number): any`

**JSDoc:**
```typescript
/**
	 * Compute the orientation of the slice and returns all the information relative to the geometry such as sliceAccess,
	 * the plane matrix (orientation and position in RAS coordinate) and the dimensions of the plane in both coordinate system.
	 *
	 * @param {('x'|'y'|'z')} axis - The normal axis to the slice.
	 * @param {number} RASIndex - The index of the slice.
	 * @returns {Object} An object containing all the useful information on the geometry of the slice.
	 */
```

**Parameters:**

- **`axis`** `"x" | "y" | "z"`
- **`RASIndex`** `number`

**Returns:** `any`

**Calls:**

- `( new Matrix4() ).identity`
- `axisInIJK.set`
- `firstDirection.set`
- `secondDirection.set`
- `this.axisOrder.indexOf`
- `planeMatrix.multiply`
- `( new Matrix4() ).makeRotationY`
- `planeMatrix.setPosition`
- `( new Matrix4() ).makeRotationX`
- `firstDirection.applyMatrix4( volume.inverseMatrix ).normalize`
- `secondDirection.applyMatrix4( volume.inverseMatrix ).normalize`
- `axisInIJK.applyMatrix4( volume.inverseMatrix ).normalize`
- `Math.floor`
- `Math.abs`
- `firstDirection.dot`
- `secondDirection.dot`
- `Math.round`
- `IJKIndex.applyMatrix4( volume.inverseMatrix ).dot`
- `[ firstDirection, secondDirection, axisInIJK ].find`
- `x.dot`
- `iDirection.dot`
- `jDirection.dot`
- `kDirection.dot`
- `volume.access`

**Internal Comments:**
```
// invert indices if necessary (x2)
```

<details><summary>Code</summary>

```typescript
extractPerpendicularPlane( axis, RASIndex ) {

		let firstSpacing,
			secondSpacing,
			positionOffset,
			IJKIndex;

		const axisInIJK = new Vector3(),
			firstDirection = new Vector3(),
			secondDirection = new Vector3(),
			planeMatrix = ( new Matrix4() ).identity(),
			volume = this;

		const dimensions = new Vector3( this.xLength, this.yLength, this.zLength );


		switch ( axis ) {

			case 'x' :
				axisInIJK.set( 1, 0, 0 );
				firstDirection.set( 0, 0, - 1 );
				secondDirection.set( 0, - 1, 0 );
				firstSpacing = this.spacing[ this.axisOrder.indexOf( 'z' ) ];
				secondSpacing = this.spacing[ this.axisOrder.indexOf( 'y' ) ];
				IJKIndex = new Vector3( RASIndex, 0, 0 );

				planeMatrix.multiply( ( new Matrix4() ).makeRotationY( Math.PI / 2 ) );
				positionOffset = ( volume.RASDimensions[ 0 ] - 1 ) / 2;
				planeMatrix.setPosition( new Vector3( RASIndex - positionOffset, 0, 0 ) );
				break;
			case 'y' :
				axisInIJK.set( 0, 1, 0 );
				firstDirection.set( 1, 0, 0 );
				secondDirection.set( 0, 0, 1 );
				firstSpacing = this.spacing[ this.axisOrder.indexOf( 'x' ) ];
				secondSpacing = this.spacing[ this.axisOrder.indexOf( 'z' ) ];
				IJKIndex = new Vector3( 0, RASIndex, 0 );

				planeMatrix.multiply( ( new Matrix4() ).makeRotationX( - Math.PI / 2 ) );
				positionOffset = ( volume.RASDimensions[ 1 ] - 1 ) / 2;
				planeMatrix.setPosition( new Vector3( 0, RASIndex - positionOffset, 0 ) );
				break;
			case 'z' :
			default :
				axisInIJK.set( 0, 0, 1 );
				firstDirection.set( 1, 0, 0 );
				secondDirection.set( 0, - 1, 0 );
				firstSpacing = this.spacing[ this.axisOrder.indexOf( 'x' ) ];
				secondSpacing = this.spacing[ this.axisOrder.indexOf( 'y' ) ];
				IJKIndex = new Vector3( 0, 0, RASIndex );

				positionOffset = ( volume.RASDimensions[ 2 ] - 1 ) / 2;
				planeMatrix.setPosition( new Vector3( 0, 0, RASIndex - positionOffset ) );
				break;

		}

		if ( ! this.segmentation ) {

			firstDirection.applyMatrix4( volume.inverseMatrix ).normalize();
			secondDirection.applyMatrix4( volume.inverseMatrix ).normalize();
			axisInIJK.applyMatrix4( volume.inverseMatrix ).normalize();

		}

		firstDirection.arglet = 'i';
		secondDirection.arglet = 'j';
		const iLength = Math.floor( Math.abs( firstDirection.dot( dimensions ) ) );
		const jLength = Math.floor( Math.abs( secondDirection.dot( dimensions ) ) );
		const planeWidth = Math.abs( iLength * firstSpacing );
		const planeHeight = Math.abs( jLength * secondSpacing );

		IJKIndex = Math.abs( Math.round( IJKIndex.applyMatrix4( volume.inverseMatrix ).dot( axisInIJK ) ) );
		const base = [ new Vector3( 1, 0, 0 ), new Vector3( 0, 1, 0 ), new Vector3( 0, 0, 1 ) ];
		const iDirection = [ firstDirection, secondDirection, axisInIJK ].find( function ( x ) {

			return Math.abs( x.dot( base[ 0 ] ) ) > 0.9;

		} );
		const jDirection = [ firstDirection, secondDirection, axisInIJK ].find( function ( x ) {

			return Math.abs( x.dot( base[ 1 ] ) ) > 0.9;

		} );
		const kDirection = [ firstDirection, secondDirection, axisInIJK ].find( function ( x ) {

			return Math.abs( x.dot( base[ 2 ] ) ) > 0.9;

		} );

		function sliceAccess( i, j ) {

			const si = ( iDirection === axisInIJK ) ? IJKIndex : ( iDirection.arglet === 'i' ? i : j );
			const sj = ( jDirection === axisInIJK ) ? IJKIndex : ( jDirection.arglet === 'i' ? i : j );
			const sk = ( kDirection === axisInIJK ) ? IJKIndex : ( kDirection.arglet === 'i' ? i : j );

			// invert indices if necessary

			const accessI = ( iDirection.dot( base[ 0 ] ) > 0 ) ? si : ( volume.xLength - 1 ) - si;
			const accessJ = ( jDirection.dot( base[ 1 ] ) > 0 ) ? sj : ( volume.yLength - 1 ) - sj;
			const accessK = ( kDirection.dot( base[ 2 ] ) > 0 ) ? sk : ( volume.zLength - 1 ) - sk;

			return volume.access( accessI, accessJ, accessK );

		}

		return {
			iLength: iLength,
			jLength: jLength,
			sliceAccess: sliceAccess,
			matrix: planeMatrix,
			planeWidth: planeWidth,
			planeHeight: planeHeight
		};

	}
```
</details>

### `Volume.extractSlice(axis: "x" | "y" | "z", index: number): VolumeSlice`

**JSDoc:**
```typescript
/**
	 * Returns a slice corresponding to the given axis and index.
	 * The coordinate are given in the Right Anterior Superior coordinate format.
	 *
	 * @param {('x'|'y'|'z')} axis - The normal axis to the slice.
	 * @param {number} index - The index of the slice.
	 * @returns {VolumeSlice} The extracted slice.
	 */
```

**Parameters:**

- **`axis`** `"x" | "y" | "z"`
- **`index`** `number`

**Returns:** `VolumeSlice`

**Calls:**

- `this.sliceList.push`

<details><summary>Code</summary>

```typescript
extractSlice( axis, index ) {

		const slice = new VolumeSlice( this, index, axis );
		this.sliceList.push( slice );
		return slice;

	}
```
</details>

### `Volume.repaintAllSlices(): Volume`

**JSDoc:**
```typescript
/**
	 * Call repaint on all the slices extracted from this volume.
	 *
	 * @see {@link VolumeSlice#repaint}
	 * @returns {Volume} A reference to this volume.
	 */
```

**Returns:** `Volume`

**Calls:**

- `this.sliceList.forEach`
- `slice.repaint`

<details><summary>Code</summary>

```typescript
repaintAllSlices() {

		this.sliceList.forEach( function ( slice ) {

			slice.repaint();

		} );

		return this;

	}
```
</details>

### `Volume.computeMinMax(): number[]`

**JSDoc:**
```typescript
/**
	 * Compute the minimum and the maximum of the data in the volume.
	 *
	 * @returns {Array<number>} The min/max data as `[min,max]`.
	 */
```

**Returns:** `number[]`

**Calls:**

- `isNaN`
- `Math.min`
- `Math.max`

**Internal Comments:**
```
// buffer the length (x2)
```

<details><summary>Code</summary>

```typescript
computeMinMax() {

		let min = Infinity;
		let max = - Infinity;

		// buffer the length
		const datasize = this.data.length;

		let i = 0;

		for ( i = 0; i < datasize; i ++ ) {

			if ( ! isNaN( this.data[ i ] ) ) {

				const value = this.data[ i ];
				min = Math.min( min, value );
				max = Math.max( max, value );

			}

		}

		this.min = min;
		this.max = max;

		return [ min, max ];

	}
```
</details>

### `get(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {

				return lowerThreshold;

			}
```
</details>

### `set(value: number): void`

**Parameters:**

- **`value`** `number`

**Returns:** `void`

**Calls:**

- `this.sliceList.forEach`

<details><summary>Code</summary>

```typescript
function ( value ) {

				lowerThreshold = value;
				this.sliceList.forEach( function ( slice ) {

					slice.geometryNeedsUpdate = true;

				} );

			}
```
</details>

### `get(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {

				return lowerThreshold;

			}
```
</details>

### `set(value: number): void`

**Parameters:**

- **`value`** `number`

**Returns:** `void`

**Calls:**

- `this.sliceList.forEach`

<details><summary>Code</summary>

```typescript
function ( value ) {

				lowerThreshold = value;
				this.sliceList.forEach( function ( slice ) {

					slice.geometryNeedsUpdate = true;

				} );

			}
```
</details>

### `get(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {

				return upperThreshold;

			}
```
</details>

### `set(value: number): void`

**Parameters:**

- **`value`** `number`

**Returns:** `void`

**Calls:**

- `this.sliceList.forEach`

<details><summary>Code</summary>

```typescript
function ( value ) {

				upperThreshold = value;
				this.sliceList.forEach( function ( slice ) {

					slice.geometryNeedsUpdate = true;

				} );

			}
```
</details>

### `get(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {

				return upperThreshold;

			}
```
</details>

### `set(value: number): void`

**Parameters:**

- **`value`** `number`

**Returns:** `void`

**Calls:**

- `this.sliceList.forEach`

<details><summary>Code</summary>

```typescript
function ( value ) {

				upperThreshold = value;
				this.sliceList.forEach( function ( slice ) {

					slice.geometryNeedsUpdate = true;

				} );

			}
```
</details>

### `sliceAccess(i: any, j: any): number`

**Parameters:**

- **`i`** `any`
- **`j`** `any`

**Returns:** `number`

**Calls:**

- `iDirection.dot`
- `jDirection.dot`
- `kDirection.dot`
- `volume.access`

**Internal Comments:**
```
// invert indices if necessary (x2)
```

<details><summary>Code</summary>

```typescript
function sliceAccess( i, j ) {

			const si = ( iDirection === axisInIJK ) ? IJKIndex : ( iDirection.arglet === 'i' ? i : j );
			const sj = ( jDirection === axisInIJK ) ? IJKIndex : ( jDirection.arglet === 'i' ? i : j );
			const sk = ( kDirection === axisInIJK ) ? IJKIndex : ( kDirection.arglet === 'i' ? i : j );

			// invert indices if necessary

			const accessI = ( iDirection.dot( base[ 0 ] ) > 0 ) ? si : ( volume.xLength - 1 ) - si;
			const accessJ = ( jDirection.dot( base[ 1 ] ) > 0 ) ? sj : ( volume.yLength - 1 ) - sj;
			const accessK = ( kDirection.dot( base[ 2 ] ) > 0 ) ? sk : ( volume.zLength - 1 ) - sk;

			return volume.access( accessI, accessJ, accessK );

		}
```
</details>


---

## Classes

### `Volume`

<details><summary>Class Code</summary>

```ts
class Volume {

	/**
	 * Constructs a new volume.
	 *
	 * @param {number} [xLength] - Width of the volume.
	 * @param {number} [yLength] - Length of the volume.
	 * @param {number} [zLength] - Depth of the volume.
	 * @param {string} [type] - The type of data (uint8, uint16, ...).
	 * @param {ArrayBuffer} [arrayBuffer] - The buffer with volume data.
	 */
	constructor( xLength, yLength, zLength, type, arrayBuffer ) {

		if ( xLength !== undefined ) {

			/**
			 * Width of the volume in the IJK coordinate system.
			 *
			 * @type {number}
			 * @default 1
			 */
			this.xLength = Number( xLength ) || 1;

			/**
			 * Height of the volume in the IJK coordinate system.
			 *
			 * @type {number}
			 * @default 1
			 */
			this.yLength = Number( yLength ) || 1;

			/**
			 * Depth of the volume in the IJK coordinate system.
			 *
			 * @type {number}
			 * @default 1
			 */
			this.zLength = Number( zLength ) || 1;

			/**
			 * The order of the Axis dictated by the NRRD header
			 *
			 * @type {Array<string>}
			 */
			this.axisOrder = [ 'x', 'y', 'z' ];

			/**
			 * The data of the volume.
			 *
			 * @type {TypedArray}
			 */
			this.data;

			switch ( type ) {

				case 'Uint8' :
				case 'uint8' :
				case 'uchar' :
				case 'unsigned char' :
				case 'uint8_t' :
					this.data = new Uint8Array( arrayBuffer );
					break;
				case 'Int8' :
				case 'int8' :
				case 'signed char' :
				case 'int8_t' :
					this.data = new Int8Array( arrayBuffer );
					break;
				case 'Int16' :
				case 'int16' :
				case 'short' :
				case 'short int' :
				case 'signed short' :
				case 'signed short int' :
				case 'int16_t' :
					this.data = new Int16Array( arrayBuffer );
					break;
				case 'Uint16' :
				case 'uint16' :
				case 'ushort' :
				case 'unsigned short' :
				case 'unsigned short int' :
				case 'uint16_t' :
					this.data = new Uint16Array( arrayBuffer );
					break;
				case 'Int32' :
				case 'int32' :
				case 'int' :
				case 'signed int' :
				case 'int32_t' :
					this.data = new Int32Array( arrayBuffer );
					break;
				case 'Uint32' :
				case 'uint32' :
				case 'uint' :
				case 'unsigned int' :
				case 'uint32_t' :
					this.data = new Uint32Array( arrayBuffer );
					break;
				case 'longlong' :
				case 'long long' :
				case 'long long int' :
				case 'signed long long' :
				case 'signed long long int' :
				case 'int64' :
				case 'int64_t' :
				case 'ulonglong' :
				case 'unsigned long long' :
				case 'unsigned long long int' :
				case 'uint64' :
				case 'uint64_t' :
					throw new Error( 'Error in Volume constructor : this type is not supported in JavaScript' );
					break;
				case 'Float32' :
				case 'float32' :
				case 'float' :
					this.data = new Float32Array( arrayBuffer );
					break;
				case 'Float64' :
				case 'float64' :
				case 'double' :
					this.data = new Float64Array( arrayBuffer );
					break;
				default :
					this.data = new Uint8Array( arrayBuffer );

			}

			if ( this.data.length !== this.xLength * this.yLength * this.zLength ) {

				throw new Error( 'Error in Volume constructor, lengths are not matching arrayBuffer size' );

			}

		}

		/**
		 * Spacing to apply to the volume from IJK to RAS coordinate system
		 *
		 * @type {Array<number>}
		 */
		this.spacing = [ 1, 1, 1 ];

		/**
		 * Offset of the volume in the RAS coordinate system
		 *
		 * @type {Array<number>}
		 */
		this.offset = [ 0, 0, 0 ];

		/**
		 * The IJK to RAS matrix.
		 *
		 * @type {Martrix3}
		 */
		this.matrix = new Matrix3();
		this.matrix.identity();

		/**
		 * The RAS to IJK matrix.
		 *
		 * @type {Martrix3}
		 */
		this.inverseMatrix = new Matrix3();

		let lowerThreshold = - Infinity;
		Object.defineProperty( this, 'lowerThreshold', {
			get: function () {

				return lowerThreshold;

			},
			/**
			 * The voxels with values under this threshold won't appear in the slices.
			 * If changed, geometryNeedsUpdate is automatically set to true on all the slices associated to this volume.
			 *
			 * @name Volume#lowerThreshold
			 * @type {number}
			 * @param {number} value
			 */
			set: function ( value ) {

				lowerThreshold = value;
				this.sliceList.forEach( function ( slice ) {

					slice.geometryNeedsUpdate = true;

				} );

			}
		} );

		let upperThreshold = Infinity;
		Object.defineProperty( this, 'upperThreshold', {
			get: function () {

				return upperThreshold;

			},
			/**
			 * The voxels with values over this threshold won't appear in the slices.
			 * If changed, geometryNeedsUpdate is automatically set to true on all the slices associated to this volume
			 *
			 * @name Volume#upperThreshold
			 * @type {number}
			 * @param {number} value
			 */
			set: function ( value ) {

				upperThreshold = value;
				this.sliceList.forEach( function ( slice ) {

					slice.geometryNeedsUpdate = true;

				} );

			}
		} );


		/**
		 * The list of all the slices associated to this volume
		 *
		 * @type {Array}
		 */
		this.sliceList = [];

		/**
		 * Whether to use segmentation mode or not.
		 * It can load 16-bits nrrds correctly.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.segmentation = false;


		/**
		 * This array holds the dimensions of the volume in the RAS space
		 *
		 * @type {Array<number>}
		 */
		this.RASDimensions = [];

	}

	/**
	 * Shortcut for data[access(i,j,k)].
	 *
	 * @param {number} i - First coordinate.
	 * @param {number} j - Second coordinate.
	 * @param {number} k - Third coordinate.
	 * @returns {number} The value in the data array.
	 */
	getData( i, j, k ) {

		return this.data[ k * this.xLength * this.yLength + j * this.xLength + i ];

	}

	/**
	 * Compute the index in the data array corresponding to the given coordinates in IJK system.
	 *
	 * @param {number} i - First coordinate.
	 * @param {number} j - Second coordinate.
	 * @param {number} k - Third coordinate.
	 * @returns {number} The index.
	 */
	access( i, j, k ) {

		return k * this.xLength * this.yLength + j * this.xLength + i;

	}

	/**
	 * Retrieve the IJK coordinates of the voxel corresponding of the given index in the data.
	 *
	 * @param {number} index - Index of the voxel.
	 * @returns {Array<number>} The IJK coordinates as `[x,y,z]`.
	 */
	reverseAccess( index ) {

		const z = Math.floor( index / ( this.yLength * this.xLength ) );
		const y = Math.floor( ( index - z * this.yLength * this.xLength ) / this.xLength );
		const x = index - z * this.yLength * this.xLength - y * this.xLength;
		return [ x, y, z ];

	}

	/**
	 * Apply a function to all the voxels, be careful, the value will be replaced.
	 *
	 * @param {Function} functionToMap A function to apply to every voxel, will be called with the following parameters:
	 * value of the voxel, index of the voxel, the data (TypedArray).
	 * @param {Object} context - You can specify a context in which call the function, default if this Volume.
	 * @returns {Volume} A reference to this instance.
	 */
	map( functionToMap, context ) {

		const length = this.data.length;
		context = context || this;

		for ( let i = 0; i < length; i ++ ) {

			this.data[ i ] = functionToMap.call( context, this.data[ i ], i, this.data );

		}

		return this;

	}

	/**
	 * Compute the orientation of the slice and returns all the information relative to the geometry such as sliceAccess,
	 * the plane matrix (orientation and position in RAS coordinate) and the dimensions of the plane in both coordinate system.
	 *
	 * @param {('x'|'y'|'z')} axis - The normal axis to the slice.
	 * @param {number} RASIndex - The index of the slice.
	 * @returns {Object} An object containing all the useful information on the geometry of the slice.
	 */
	extractPerpendicularPlane( axis, RASIndex ) {

		let firstSpacing,
			secondSpacing,
			positionOffset,
			IJKIndex;

		const axisInIJK = new Vector3(),
			firstDirection = new Vector3(),
			secondDirection = new Vector3(),
			planeMatrix = ( new Matrix4() ).identity(),
			volume = this;

		const dimensions = new Vector3( this.xLength, this.yLength, this.zLength );


		switch ( axis ) {

			case 'x' :
				axisInIJK.set( 1, 0, 0 );
				firstDirection.set( 0, 0, - 1 );
				secondDirection.set( 0, - 1, 0 );
				firstSpacing = this.spacing[ this.axisOrder.indexOf( 'z' ) ];
				secondSpacing = this.spacing[ this.axisOrder.indexOf( 'y' ) ];
				IJKIndex = new Vector3( RASIndex, 0, 0 );

				planeMatrix.multiply( ( new Matrix4() ).makeRotationY( Math.PI / 2 ) );
				positionOffset = ( volume.RASDimensions[ 0 ] - 1 ) / 2;
				planeMatrix.setPosition( new Vector3( RASIndex - positionOffset, 0, 0 ) );
				break;
			case 'y' :
				axisInIJK.set( 0, 1, 0 );
				firstDirection.set( 1, 0, 0 );
				secondDirection.set( 0, 0, 1 );
				firstSpacing = this.spacing[ this.axisOrder.indexOf( 'x' ) ];
				secondSpacing = this.spacing[ this.axisOrder.indexOf( 'z' ) ];
				IJKIndex = new Vector3( 0, RASIndex, 0 );

				planeMatrix.multiply( ( new Matrix4() ).makeRotationX( - Math.PI / 2 ) );
				positionOffset = ( volume.RASDimensions[ 1 ] - 1 ) / 2;
				planeMatrix.setPosition( new Vector3( 0, RASIndex - positionOffset, 0 ) );
				break;
			case 'z' :
			default :
				axisInIJK.set( 0, 0, 1 );
				firstDirection.set( 1, 0, 0 );
				secondDirection.set( 0, - 1, 0 );
				firstSpacing = this.spacing[ this.axisOrder.indexOf( 'x' ) ];
				secondSpacing = this.spacing[ this.axisOrder.indexOf( 'y' ) ];
				IJKIndex = new Vector3( 0, 0, RASIndex );

				positionOffset = ( volume.RASDimensions[ 2 ] - 1 ) / 2;
				planeMatrix.setPosition( new Vector3( 0, 0, RASIndex - positionOffset ) );
				break;

		}

		if ( ! this.segmentation ) {

			firstDirection.applyMatrix4( volume.inverseMatrix ).normalize();
			secondDirection.applyMatrix4( volume.inverseMatrix ).normalize();
			axisInIJK.applyMatrix4( volume.inverseMatrix ).normalize();

		}

		firstDirection.arglet = 'i';
		secondDirection.arglet = 'j';
		const iLength = Math.floor( Math.abs( firstDirection.dot( dimensions ) ) );
		const jLength = Math.floor( Math.abs( secondDirection.dot( dimensions ) ) );
		const planeWidth = Math.abs( iLength * firstSpacing );
		const planeHeight = Math.abs( jLength * secondSpacing );

		IJKIndex = Math.abs( Math.round( IJKIndex.applyMatrix4( volume.inverseMatrix ).dot( axisInIJK ) ) );
		const base = [ new Vector3( 1, 0, 0 ), new Vector3( 0, 1, 0 ), new Vector3( 0, 0, 1 ) ];
		const iDirection = [ firstDirection, secondDirection, axisInIJK ].find( function ( x ) {

			return Math.abs( x.dot( base[ 0 ] ) ) > 0.9;

		} );
		const jDirection = [ firstDirection, secondDirection, axisInIJK ].find( function ( x ) {

			return Math.abs( x.dot( base[ 1 ] ) ) > 0.9;

		} );
		const kDirection = [ firstDirection, secondDirection, axisInIJK ].find( function ( x ) {

			return Math.abs( x.dot( base[ 2 ] ) ) > 0.9;

		} );

		function sliceAccess( i, j ) {

			const si = ( iDirection === axisInIJK ) ? IJKIndex : ( iDirection.arglet === 'i' ? i : j );
			const sj = ( jDirection === axisInIJK ) ? IJKIndex : ( jDirection.arglet === 'i' ? i : j );
			const sk = ( kDirection === axisInIJK ) ? IJKIndex : ( kDirection.arglet === 'i' ? i : j );

			// invert indices if necessary

			const accessI = ( iDirection.dot( base[ 0 ] ) > 0 ) ? si : ( volume.xLength - 1 ) - si;
			const accessJ = ( jDirection.dot( base[ 1 ] ) > 0 ) ? sj : ( volume.yLength - 1 ) - sj;
			const accessK = ( kDirection.dot( base[ 2 ] ) > 0 ) ? sk : ( volume.zLength - 1 ) - sk;

			return volume.access( accessI, accessJ, accessK );

		}

		return {
			iLength: iLength,
			jLength: jLength,
			sliceAccess: sliceAccess,
			matrix: planeMatrix,
			planeWidth: planeWidth,
			planeHeight: planeHeight
		};

	}

	/**
	 * Returns a slice corresponding to the given axis and index.
	 * The coordinate are given in the Right Anterior Superior coordinate format.
	 *
	 * @param {('x'|'y'|'z')} axis - The normal axis to the slice.
	 * @param {number} index - The index of the slice.
	 * @returns {VolumeSlice} The extracted slice.
	 */
	extractSlice( axis, index ) {

		const slice = new VolumeSlice( this, index, axis );
		this.sliceList.push( slice );
		return slice;

	}

	/**
	 * Call repaint on all the slices extracted from this volume.
	 *
	 * @see {@link VolumeSlice#repaint}
	 * @returns {Volume} A reference to this volume.
	 */
	repaintAllSlices() {

		this.sliceList.forEach( function ( slice ) {

			slice.repaint();

		} );

		return this;

	}

	/**
	 * Compute the minimum and the maximum of the data in the volume.
	 *
	 * @returns {Array<number>} The min/max data as `[min,max]`.
	 */
	computeMinMax() {

		let min = Infinity;
		let max = - Infinity;

		// buffer the length
		const datasize = this.data.length;

		let i = 0;

		for ( i = 0; i < datasize; i ++ ) {

			if ( ! isNaN( this.data[ i ] ) ) {

				const value = this.data[ i ];
				min = Math.min( min, value );
				max = Math.max( max, value );

			}

		}

		this.min = min;
		this.max = max;

		return [ min, max ];

	}

}
```
</details>

#### Methods

##### `getData(i: number, j: number, k: number): number`

<details><summary>Code</summary>

```ts
getData( i, j, k ) {

		return this.data[ k * this.xLength * this.yLength + j * this.xLength + i ];

	}
```
</details>

##### `access(i: number, j: number, k: number): number`

<details><summary>Code</summary>

```ts
access( i, j, k ) {

		return k * this.xLength * this.yLength + j * this.xLength + i;

	}
```
</details>

##### `reverseAccess(index: number): number[]`

<details><summary>Code</summary>

```ts
reverseAccess( index ) {

		const z = Math.floor( index / ( this.yLength * this.xLength ) );
		const y = Math.floor( ( index - z * this.yLength * this.xLength ) / this.xLength );
		const x = index - z * this.yLength * this.xLength - y * this.xLength;
		return [ x, y, z ];

	}
```
</details>

##### `map(functionToMap: Function, context: any): Volume`

<details><summary>Code</summary>

```ts
map( functionToMap, context ) {

		const length = this.data.length;
		context = context || this;

		for ( let i = 0; i < length; i ++ ) {

			this.data[ i ] = functionToMap.call( context, this.data[ i ], i, this.data );

		}

		return this;

	}
```
</details>

##### `extractPerpendicularPlane(axis: "x" | "y" | "z", RASIndex: number): any`

<details><summary>Code</summary>

```ts
extractPerpendicularPlane( axis, RASIndex ) {

		let firstSpacing,
			secondSpacing,
			positionOffset,
			IJKIndex;

		const axisInIJK = new Vector3(),
			firstDirection = new Vector3(),
			secondDirection = new Vector3(),
			planeMatrix = ( new Matrix4() ).identity(),
			volume = this;

		const dimensions = new Vector3( this.xLength, this.yLength, this.zLength );


		switch ( axis ) {

			case 'x' :
				axisInIJK.set( 1, 0, 0 );
				firstDirection.set( 0, 0, - 1 );
				secondDirection.set( 0, - 1, 0 );
				firstSpacing = this.spacing[ this.axisOrder.indexOf( 'z' ) ];
				secondSpacing = this.spacing[ this.axisOrder.indexOf( 'y' ) ];
				IJKIndex = new Vector3( RASIndex, 0, 0 );

				planeMatrix.multiply( ( new Matrix4() ).makeRotationY( Math.PI / 2 ) );
				positionOffset = ( volume.RASDimensions[ 0 ] - 1 ) / 2;
				planeMatrix.setPosition( new Vector3( RASIndex - positionOffset, 0, 0 ) );
				break;
			case 'y' :
				axisInIJK.set( 0, 1, 0 );
				firstDirection.set( 1, 0, 0 );
				secondDirection.set( 0, 0, 1 );
				firstSpacing = this.spacing[ this.axisOrder.indexOf( 'x' ) ];
				secondSpacing = this.spacing[ this.axisOrder.indexOf( 'z' ) ];
				IJKIndex = new Vector3( 0, RASIndex, 0 );

				planeMatrix.multiply( ( new Matrix4() ).makeRotationX( - Math.PI / 2 ) );
				positionOffset = ( volume.RASDimensions[ 1 ] - 1 ) / 2;
				planeMatrix.setPosition( new Vector3( 0, RASIndex - positionOffset, 0 ) );
				break;
			case 'z' :
			default :
				axisInIJK.set( 0, 0, 1 );
				firstDirection.set( 1, 0, 0 );
				secondDirection.set( 0, - 1, 0 );
				firstSpacing = this.spacing[ this.axisOrder.indexOf( 'x' ) ];
				secondSpacing = this.spacing[ this.axisOrder.indexOf( 'y' ) ];
				IJKIndex = new Vector3( 0, 0, RASIndex );

				positionOffset = ( volume.RASDimensions[ 2 ] - 1 ) / 2;
				planeMatrix.setPosition( new Vector3( 0, 0, RASIndex - positionOffset ) );
				break;

		}

		if ( ! this.segmentation ) {

			firstDirection.applyMatrix4( volume.inverseMatrix ).normalize();
			secondDirection.applyMatrix4( volume.inverseMatrix ).normalize();
			axisInIJK.applyMatrix4( volume.inverseMatrix ).normalize();

		}

		firstDirection.arglet = 'i';
		secondDirection.arglet = 'j';
		const iLength = Math.floor( Math.abs( firstDirection.dot( dimensions ) ) );
		const jLength = Math.floor( Math.abs( secondDirection.dot( dimensions ) ) );
		const planeWidth = Math.abs( iLength * firstSpacing );
		const planeHeight = Math.abs( jLength * secondSpacing );

		IJKIndex = Math.abs( Math.round( IJKIndex.applyMatrix4( volume.inverseMatrix ).dot( axisInIJK ) ) );
		const base = [ new Vector3( 1, 0, 0 ), new Vector3( 0, 1, 0 ), new Vector3( 0, 0, 1 ) ];
		const iDirection = [ firstDirection, secondDirection, axisInIJK ].find( function ( x ) {

			return Math.abs( x.dot( base[ 0 ] ) ) > 0.9;

		} );
		const jDirection = [ firstDirection, secondDirection, axisInIJK ].find( function ( x ) {

			return Math.abs( x.dot( base[ 1 ] ) ) > 0.9;

		} );
		const kDirection = [ firstDirection, secondDirection, axisInIJK ].find( function ( x ) {

			return Math.abs( x.dot( base[ 2 ] ) ) > 0.9;

		} );

		function sliceAccess( i, j ) {

			const si = ( iDirection === axisInIJK ) ? IJKIndex : ( iDirection.arglet === 'i' ? i : j );
			const sj = ( jDirection === axisInIJK ) ? IJKIndex : ( jDirection.arglet === 'i' ? i : j );
			const sk = ( kDirection === axisInIJK ) ? IJKIndex : ( kDirection.arglet === 'i' ? i : j );

			// invert indices if necessary

			const accessI = ( iDirection.dot( base[ 0 ] ) > 0 ) ? si : ( volume.xLength - 1 ) - si;
			const accessJ = ( jDirection.dot( base[ 1 ] ) > 0 ) ? sj : ( volume.yLength - 1 ) - sj;
			const accessK = ( kDirection.dot( base[ 2 ] ) > 0 ) ? sk : ( volume.zLength - 1 ) - sk;

			return volume.access( accessI, accessJ, accessK );

		}

		return {
			iLength: iLength,
			jLength: jLength,
			sliceAccess: sliceAccess,
			matrix: planeMatrix,
			planeWidth: planeWidth,
			planeHeight: planeHeight
		};

	}
```
</details>

##### `extractSlice(axis: "x" | "y" | "z", index: number): VolumeSlice`

<details><summary>Code</summary>

```ts
extractSlice( axis, index ) {

		const slice = new VolumeSlice( this, index, axis );
		this.sliceList.push( slice );
		return slice;

	}
```
</details>

##### `repaintAllSlices(): Volume`

<details><summary>Code</summary>

```ts
repaintAllSlices() {

		this.sliceList.forEach( function ( slice ) {

			slice.repaint();

		} );

		return this;

	}
```
</details>

##### `computeMinMax(): number[]`

<details><summary>Code</summary>

```ts
computeMinMax() {

		let min = Infinity;
		let max = - Infinity;

		// buffer the length
		const datasize = this.data.length;

		let i = 0;

		for ( i = 0; i < datasize; i ++ ) {

			if ( ! isNaN( this.data[ i ] ) ) {

				const value = this.data[ i ];
				min = Math.min( min, value );
				max = Math.max( max, value );

			}

		}

		this.min = min;
		this.max = max;

		return [ min, max ];

	}
```
</details>


---