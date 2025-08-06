[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `IESLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 33 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/IESLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataTexture` | `three` |
| `FileLoader` | `three` |
| `FloatType` | `three` |
| `RedFormat` | `three` |
| `MathUtils` | `three` |
| `Loader` | `three` |
| `UnsignedByteType` | `three` |
| `LinearFilter` | `three` |
| `HalfFloatType` | `three` |
| `DataUtils` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `width` | `360` | let/var | `360` | ✗ |
| `height` | `180` | let/var | `180` | ✗ |
| `size` | `number` | let/var | `width * height` | ✗ |
| `data` | `any[]` | let/var | `new Array( size )` | ✗ |
| `phiIndex` | `number` | let/var | `0` | ✗ |
| `thetaIndex` | `number` | let/var | `0` | ✗ |
| `startTheta` | `number` | let/var | `0` | ✗ |
| `endTheta` | `number` | let/var | `0` | ✗ |
| `startPhi` | `number` | let/var | `0` | ✗ |
| `endPhi` | `number` | let/var | `0` | ✗ |
| `deltaTheta` | `number` | let/var | `endTheta - startTheta` | ✗ |
| `deltaPhi` | `number` | let/var | `endPhi - startPhi` | ✗ |
| `t1` | `number` | let/var | `deltaTheta === 0 ? 0 : ( theta - startTheta ) / deltaTheta` | ✗ |
| `t2` | `number` | let/var | `( phi - startPhi ) / deltaPhi` | ✗ |
| `nextThetaIndex` | `number` | let/var | `deltaTheta === 0 ? thetaIndex : thetaIndex + 1` | ✗ |
| `startTheta` | `any` | let/var | `iesLamp.horAngles[ 0 ]` | ✗ |
| `endTheta` | `any` | let/var | `iesLamp.horAngles[ iesLamp.numHorAngles - 1 ]` | ✗ |
| `theta` | `number` | let/var | `i % width` | ✗ |
| `result` | `any` | let/var | `null` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `type` | `any` | let/var | `this.type` | ✗ |
| `iesLamp` | `IESLamp` | let/var | `new IESLamp( text )` | ✗ |
| `texture` | `any` | let/var | `new DataTexture( data, 180, 1, RedFormat, type )` | ✗ |
| `_self` | `this` | let/var | `this` | ✗ |
| `lineNumber` | `number` | let/var | `0` | ✗ |
| `line` | `any` | let/var | `*not shown*` | ✗ |
| `line` | `any` | let/var | `textArray[ lineNumber ++ ]` | ✗ |
| `line` | `any` | let/var | `textArray[ lineNumber ++ ]` | ✗ |
| `values` | `any[]` | let/var | `[ ]` | ✗ |
| `values` | `any[]` | let/var | `[ ]` | ✗ |
| `maxVal` | `number` | let/var | `- 1` | ✗ |
| `value` | `any` | let/var | `_self.candelaValues[ i ][ j ]` | ✗ |
| `bNormalize` | `true` | let/var | `true` | ✗ |


---

## Functions

### `IESLoader._getIESValues(iesLamp: any, type: any): Float32Array<ArrayBuffer> | Uint16Array<ArrayBuffer> | Uint8Array<ArrayBuffer>`

**Parameters:**

- **`iesLamp`** `any`
- **`type`** `any`

**Returns:** `Float32Array<ArrayBuffer> | Uint16Array<ArrayBuffer> | Uint8Array<ArrayBuffer>`

**Calls:**

- `MathUtils.lerp`
- `Math.floor`
- `interpolateCandelaValues`
- `Uint8Array.from`
- `data.map`
- `Math.min`
- `Uint16Array.from`
- `DataUtils.toHalfFloat`
- `Float32Array.from`
- `console.error`

<details><summary>Code</summary>

```typescript
_getIESValues( iesLamp, type ) {

		const width = 360;
		const height = 180;
		const size = width * height;

		const data = new Array( size );

		function interpolateCandelaValues( phi, theta ) {

			let phiIndex = 0, thetaIndex = 0;
			let startTheta = 0, endTheta = 0, startPhi = 0, endPhi = 0;

			for ( let i = 0; i < iesLamp.numHorAngles - 1; ++ i ) { // numHorAngles = horAngles.length-1 because of extra padding, so this wont cause an out of bounds error

				if ( theta < iesLamp.horAngles[ i + 1 ] || i == iesLamp.numHorAngles - 2 ) {

					thetaIndex = i;
					startTheta = iesLamp.horAngles[ i ];
					endTheta = iesLamp.horAngles[ i + 1 ];

					break;

				}

			}

			for ( let i = 0; i < iesLamp.numVerAngles - 1; ++ i ) {

				if ( phi < iesLamp.verAngles[ i + 1 ] || i == iesLamp.numVerAngles - 2 ) {

					phiIndex = i;
					startPhi = iesLamp.verAngles[ i ];
					endPhi = iesLamp.verAngles[ i + 1 ];

					break;

				}

			}

			const deltaTheta = endTheta - startTheta;
			const deltaPhi = endPhi - startPhi;

			if ( deltaPhi === 0 ) // Outside range
				return 0;

			const t1 = deltaTheta === 0 ? 0 : ( theta - startTheta ) / deltaTheta;
			const t2 = ( phi - startPhi ) / deltaPhi;

			const nextThetaIndex = deltaTheta === 0 ? thetaIndex : thetaIndex + 1;

			const v1 = MathUtils.lerp( iesLamp.candelaValues[ thetaIndex ][ phiIndex ], iesLamp.candelaValues[ nextThetaIndex ][ phiIndex ], t1 );
			const v2 = MathUtils.lerp( iesLamp.candelaValues[ thetaIndex ][ phiIndex + 1 ], iesLamp.candelaValues[ nextThetaIndex ][ phiIndex + 1 ], t1 );
			const v = MathUtils.lerp( v1, v2, t2 );

			return v;

		}

		const startTheta = iesLamp.horAngles[ 0 ], endTheta = iesLamp.horAngles[ iesLamp.numHorAngles - 1 ];

		for ( let i = 0; i < size; ++ i ) {

			let theta = i % width;
			const phi = Math.floor( i / width );

			if ( endTheta - startTheta !== 0 && ( theta < startTheta || theta >= endTheta ) ) { // Handle symmetry for hor angles

				theta %= endTheta * 2;

				if ( theta > endTheta )
					theta = endTheta * 2 - theta;

			}

			data[ phi + theta * height ] = interpolateCandelaValues( phi, theta );

		}

		let result = null;

		if ( type === UnsignedByteType ) result = Uint8Array.from( data.map( v => Math.min( v * 0xFF, 0xFF ) ) );
		else if ( type === HalfFloatType ) result = Uint16Array.from( data.map( v => DataUtils.toHalfFloat( v ) ) );
		else if ( type === FloatType ) result = Float32Array.from( data );
		else console.error( 'IESLoader: Unsupported type:', type );

		return result;

	}
```
</details>

### `IESLoader.load(url: string, onLoad: (arg0: DataTexture) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded IES texture
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(DataTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: DataTexture) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setResponseType`
- `loader.setCrossOrigin`
- `loader.setWithCredentials`
- `loader.setPath`
- `loader.setRequestHeader`
- `loader.load`
- `onLoad`
- `this.parse`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );
		loader.setResponseType( 'text' );
		loader.setCrossOrigin( this.crossOrigin );
		loader.setWithCredentials( this.withCredentials );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );

		loader.load( url, text => {

			onLoad( this.parse( text ) );

		}, onProgress, onError );

	}
```
</details>

### `IESLoader.parse(text: string): DataTexture`

**JSDoc:**
```typescript
/**
	 * Parses the given IES data.
	 *
	 * @param {string} text - The raw IES data.
	 * @return {DataTexture} THE IES data as a texture.
	 */
```

**Parameters:**

- **`text`** `string`

**Returns:** `DataTexture`

**Calls:**

- `this._getIESValues`

<details><summary>Code</summary>

```typescript
parse( text ) {

		const type = this.type;

		const iesLamp = new IESLamp( text );
		const data = this._getIESValues( iesLamp, type );

		const texture = new DataTexture( data, 180, 1, RedFormat, type );
		texture.minFilter = LinearFilter;
		texture.magFilter = LinearFilter;
		texture.needsUpdate = true;

		return texture;

	}
```
</details>

### `interpolateCandelaValues(phi: any, theta: any): any`

**Parameters:**

- **`phi`** `any`
- **`theta`** `any`

**Returns:** `any`

**Calls:**

- `MathUtils.lerp`

<details><summary>Code</summary>

```typescript
function interpolateCandelaValues( phi, theta ) {

			let phiIndex = 0, thetaIndex = 0;
			let startTheta = 0, endTheta = 0, startPhi = 0, endPhi = 0;

			for ( let i = 0; i < iesLamp.numHorAngles - 1; ++ i ) { // numHorAngles = horAngles.length-1 because of extra padding, so this wont cause an out of bounds error

				if ( theta < iesLamp.horAngles[ i + 1 ] || i == iesLamp.numHorAngles - 2 ) {

					thetaIndex = i;
					startTheta = iesLamp.horAngles[ i ];
					endTheta = iesLamp.horAngles[ i + 1 ];

					break;

				}

			}

			for ( let i = 0; i < iesLamp.numVerAngles - 1; ++ i ) {

				if ( phi < iesLamp.verAngles[ i + 1 ] || i == iesLamp.numVerAngles - 2 ) {

					phiIndex = i;
					startPhi = iesLamp.verAngles[ i ];
					endPhi = iesLamp.verAngles[ i + 1 ];

					break;

				}

			}

			const deltaTheta = endTheta - startTheta;
			const deltaPhi = endPhi - startPhi;

			if ( deltaPhi === 0 ) // Outside range
				return 0;

			const t1 = deltaTheta === 0 ? 0 : ( theta - startTheta ) / deltaTheta;
			const t2 = ( phi - startPhi ) / deltaPhi;

			const nextThetaIndex = deltaTheta === 0 ? thetaIndex : thetaIndex + 1;

			const v1 = MathUtils.lerp( iesLamp.candelaValues[ thetaIndex ][ phiIndex ], iesLamp.candelaValues[ nextThetaIndex ][ phiIndex ], t1 );
			const v2 = MathUtils.lerp( iesLamp.candelaValues[ thetaIndex ][ phiIndex + 1 ], iesLamp.candelaValues[ nextThetaIndex ][ phiIndex + 1 ], t1 );
			const v = MathUtils.lerp( v1, v2, t2 );

			return v;

		}
```
</details>

### `IESLamp(text: any): void`

**Parameters:**

- **`text`** `any`

**Returns:** `void`

**Calls:**

- `text.split`
- `text.replace`
- `textToArray`
- `array.push`
- `Number`
- `readArray`
- `line.includes`
- `readTilt`
- `readLampValues`
- `readLampFactors`
- `_self.candelaValues.push`

**Internal Comments:**
```
// Initialize candela value array
// Parse Angles (x3)
// Parse Candela values
// Calculate actual candela values, and normalize.
```

<details><summary>Code</summary>

```typescript
function IESLamp( text ) {

	const _self = this;

	const textArray = text.split( '\n' );

	let lineNumber = 0;
	let line;

	_self.verAngles = [ ];
	_self.horAngles = [ ];

	_self.candelaValues = [ ];

	_self.tiltData = { };
	_self.tiltData.angles = [ ];
	_self.tiltData.mulFactors = [ ];

	function textToArray( text ) {

		text = text.replace( /^\s+|\s+$/g, '' ); // remove leading or trailing spaces
		text = text.replace( /,/g, ' ' ); // replace commas with spaces
		text = text.replace( /\s\s+/g, ' ' ); // replace white space/tabs etc by single whitespace

		const array = text.split( ' ' );

		return array;

	}

	function readArray( count, array ) {

		while ( true ) {

			const line = textArray[ lineNumber ++ ];
			const lineData = textToArray( line );

			for ( let i = 0; i < lineData.length; ++ i ) {

				array.push( Number( lineData[ i ] ) );

			}

			if ( array.length === count )
				break;

		}

	}

	function readTilt() {

		let line = textArray[ lineNumber ++ ];
		let lineData = textToArray( line );

		_self.tiltData.lampToLumGeometry = Number( lineData[ 0 ] );

		line = textArray[ lineNumber ++ ];
		lineData = textToArray( line );

		_self.tiltData.numAngles = Number( lineData[ 0 ] );

		readArray( _self.tiltData.numAngles, _self.tiltData.angles );
		readArray( _self.tiltData.numAngles, _self.tiltData.mulFactors );

	}

	function readLampValues() {

		const values = [ ];
		readArray( 10, values );

		_self.count = Number( values[ 0 ] );
		_self.lumens = Number( values[ 1 ] );
		_self.multiplier = Number( values[ 2 ] );
		_self.numVerAngles = Number( values[ 3 ] );
		_self.numHorAngles = Number( values[ 4 ] );
		_self.gonioType = Number( values[ 5 ] );
		_self.units = Number( values[ 6 ] );
		_self.width = Number( values[ 7 ] );
		_self.length = Number( values[ 8 ] );
		_self.height = Number( values[ 9 ] );

	}

	function readLampFactors() {

		const values = [ ];
		readArray( 3, values );

		_self.ballFactor = Number( values[ 0 ] );
		_self.blpFactor = Number( values[ 1 ] );
		_self.inputWatts = Number( values[ 2 ] );

	}

	while ( true ) {

		line = textArray[ lineNumber ++ ];

		if ( line.includes( 'TILT' ) ) {

			break;

		}

	}

	if ( ! line.includes( 'NONE' ) ) {

		if ( line.includes( 'INCLUDE' ) ) {

			readTilt();

		} else {

			// TODO:: Read tilt data from a file

		}

	}

	readLampValues();

	readLampFactors();

	// Initialize candela value array
	for ( let i = 0; i < _self.numHorAngles; ++ i ) {

		_self.candelaValues.push( [ ] );

	}

	// Parse Angles
	readArray( _self.numVerAngles, _self.verAngles );
	readArray( _self.numHorAngles, _self.horAngles );

	// Parse Candela values
	for ( let i = 0; i < _self.numHorAngles; ++ i ) {

		readArray( _self.numVerAngles, _self.candelaValues[ i ] );

	}

	// Calculate actual candela values, and normalize.
	for ( let i = 0; i < _self.numHorAngles; ++ i ) {

		for ( let j = 0; j < _self.numVerAngles; ++ j ) {

			_self.candelaValues[ i ][ j ] *= _self.candelaValues[ i ][ j ] * _self.multiplier
				* _self.ballFactor * _self.blpFactor;

		}

	}

	let maxVal = - 1;
	for ( let i = 0; i < _self.numHorAngles; ++ i ) {

		for ( let j = 0; j < _self.numVerAngles; ++ j ) {

			const value = _self.candelaValues[ i ][ j ];
			maxVal = maxVal < value ? value : maxVal;

		}

	}

	const bNormalize = true;
	if ( bNormalize && maxVal > 0 ) {

		for ( let i = 0; i < _self.numHorAngles; ++ i ) {

			for ( let j = 0; j < _self.numVerAngles; ++ j ) {

				_self.candelaValues[ i ][ j ] /= maxVal;

			}

		}

	}

}
```
</details>

### `textToArray(text: any): any`

**Parameters:**

- **`text`** `any`

**Returns:** `any`

**Calls:**

- `text.replace`
- `text.split`

<details><summary>Code</summary>

```typescript
function textToArray( text ) {

		text = text.replace( /^\s+|\s+$/g, '' ); // remove leading or trailing spaces
		text = text.replace( /,/g, ' ' ); // replace commas with spaces
		text = text.replace( /\s\s+/g, ' ' ); // replace white space/tabs etc by single whitespace

		const array = text.split( ' ' );

		return array;

	}
```
</details>

### `readArray(count: any, array: any): void`

**Parameters:**

- **`count`** `any`
- **`array`** `any`

**Returns:** `void`

**Calls:**

- `textToArray`
- `array.push`
- `Number`

<details><summary>Code</summary>

```typescript
function readArray( count, array ) {

		while ( true ) {

			const line = textArray[ lineNumber ++ ];
			const lineData = textToArray( line );

			for ( let i = 0; i < lineData.length; ++ i ) {

				array.push( Number( lineData[ i ] ) );

			}

			if ( array.length === count )
				break;

		}

	}
```
</details>

### `readTilt(): void`

**Returns:** `void`

**Calls:**

- `textToArray`
- `Number`
- `readArray`

<details><summary>Code</summary>

```typescript
function readTilt() {

		let line = textArray[ lineNumber ++ ];
		let lineData = textToArray( line );

		_self.tiltData.lampToLumGeometry = Number( lineData[ 0 ] );

		line = textArray[ lineNumber ++ ];
		lineData = textToArray( line );

		_self.tiltData.numAngles = Number( lineData[ 0 ] );

		readArray( _self.tiltData.numAngles, _self.tiltData.angles );
		readArray( _self.tiltData.numAngles, _self.tiltData.mulFactors );

	}
```
</details>

### `readLampValues(): void`

**Returns:** `void`

**Calls:**

- `readArray`
- `Number`

<details><summary>Code</summary>

```typescript
function readLampValues() {

		const values = [ ];
		readArray( 10, values );

		_self.count = Number( values[ 0 ] );
		_self.lumens = Number( values[ 1 ] );
		_self.multiplier = Number( values[ 2 ] );
		_self.numVerAngles = Number( values[ 3 ] );
		_self.numHorAngles = Number( values[ 4 ] );
		_self.gonioType = Number( values[ 5 ] );
		_self.units = Number( values[ 6 ] );
		_self.width = Number( values[ 7 ] );
		_self.length = Number( values[ 8 ] );
		_self.height = Number( values[ 9 ] );

	}
```
</details>

### `readLampFactors(): void`

**Returns:** `void`

**Calls:**

- `readArray`
- `Number`

<details><summary>Code</summary>

```typescript
function readLampFactors() {

		const values = [ ];
		readArray( 3, values );

		_self.ballFactor = Number( values[ 0 ] );
		_self.blpFactor = Number( values[ 1 ] );
		_self.inputWatts = Number( values[ 2 ] );

	}
```
</details>


---

## Classes

### `IESLoader`

<details><summary>Class Code</summary>

```ts
class IESLoader extends Loader {

	/**
	 * Constructs a new IES loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * The texture type.
		 *
		 * @type {(HalfFloatType|FloatType)}
		 * @default HalfFloatType
		 */
		this.type = HalfFloatType;

	}

	_getIESValues( iesLamp, type ) {

		const width = 360;
		const height = 180;
		const size = width * height;

		const data = new Array( size );

		function interpolateCandelaValues( phi, theta ) {

			let phiIndex = 0, thetaIndex = 0;
			let startTheta = 0, endTheta = 0, startPhi = 0, endPhi = 0;

			for ( let i = 0; i < iesLamp.numHorAngles - 1; ++ i ) { // numHorAngles = horAngles.length-1 because of extra padding, so this wont cause an out of bounds error

				if ( theta < iesLamp.horAngles[ i + 1 ] || i == iesLamp.numHorAngles - 2 ) {

					thetaIndex = i;
					startTheta = iesLamp.horAngles[ i ];
					endTheta = iesLamp.horAngles[ i + 1 ];

					break;

				}

			}

			for ( let i = 0; i < iesLamp.numVerAngles - 1; ++ i ) {

				if ( phi < iesLamp.verAngles[ i + 1 ] || i == iesLamp.numVerAngles - 2 ) {

					phiIndex = i;
					startPhi = iesLamp.verAngles[ i ];
					endPhi = iesLamp.verAngles[ i + 1 ];

					break;

				}

			}

			const deltaTheta = endTheta - startTheta;
			const deltaPhi = endPhi - startPhi;

			if ( deltaPhi === 0 ) // Outside range
				return 0;

			const t1 = deltaTheta === 0 ? 0 : ( theta - startTheta ) / deltaTheta;
			const t2 = ( phi - startPhi ) / deltaPhi;

			const nextThetaIndex = deltaTheta === 0 ? thetaIndex : thetaIndex + 1;

			const v1 = MathUtils.lerp( iesLamp.candelaValues[ thetaIndex ][ phiIndex ], iesLamp.candelaValues[ nextThetaIndex ][ phiIndex ], t1 );
			const v2 = MathUtils.lerp( iesLamp.candelaValues[ thetaIndex ][ phiIndex + 1 ], iesLamp.candelaValues[ nextThetaIndex ][ phiIndex + 1 ], t1 );
			const v = MathUtils.lerp( v1, v2, t2 );

			return v;

		}

		const startTheta = iesLamp.horAngles[ 0 ], endTheta = iesLamp.horAngles[ iesLamp.numHorAngles - 1 ];

		for ( let i = 0; i < size; ++ i ) {

			let theta = i % width;
			const phi = Math.floor( i / width );

			if ( endTheta - startTheta !== 0 && ( theta < startTheta || theta >= endTheta ) ) { // Handle symmetry for hor angles

				theta %= endTheta * 2;

				if ( theta > endTheta )
					theta = endTheta * 2 - theta;

			}

			data[ phi + theta * height ] = interpolateCandelaValues( phi, theta );

		}

		let result = null;

		if ( type === UnsignedByteType ) result = Uint8Array.from( data.map( v => Math.min( v * 0xFF, 0xFF ) ) );
		else if ( type === HalfFloatType ) result = Uint16Array.from( data.map( v => DataUtils.toHalfFloat( v ) ) );
		else if ( type === FloatType ) result = Float32Array.from( data );
		else console.error( 'IESLoader: Unsupported type:', type );

		return result;

	}

	/**
	 * Starts loading from the given URL and passes the loaded IES texture
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(DataTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );
		loader.setResponseType( 'text' );
		loader.setCrossOrigin( this.crossOrigin );
		loader.setWithCredentials( this.withCredentials );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );

		loader.load( url, text => {

			onLoad( this.parse( text ) );

		}, onProgress, onError );

	}

	/**
	 * Parses the given IES data.
	 *
	 * @param {string} text - The raw IES data.
	 * @return {DataTexture} THE IES data as a texture.
	 */
	parse( text ) {

		const type = this.type;

		const iesLamp = new IESLamp( text );
		const data = this._getIESValues( iesLamp, type );

		const texture = new DataTexture( data, 180, 1, RedFormat, type );
		texture.minFilter = LinearFilter;
		texture.magFilter = LinearFilter;
		texture.needsUpdate = true;

		return texture;

	}

}
```
</details>

#### Methods

##### `_getIESValues(iesLamp: any, type: any): Float32Array<ArrayBuffer> | Uint16Array<ArrayBuffer> | Uint8Array<ArrayBuffer>`

<details><summary>Code</summary>

```ts
_getIESValues( iesLamp, type ) {

		const width = 360;
		const height = 180;
		const size = width * height;

		const data = new Array( size );

		function interpolateCandelaValues( phi, theta ) {

			let phiIndex = 0, thetaIndex = 0;
			let startTheta = 0, endTheta = 0, startPhi = 0, endPhi = 0;

			for ( let i = 0; i < iesLamp.numHorAngles - 1; ++ i ) { // numHorAngles = horAngles.length-1 because of extra padding, so this wont cause an out of bounds error

				if ( theta < iesLamp.horAngles[ i + 1 ] || i == iesLamp.numHorAngles - 2 ) {

					thetaIndex = i;
					startTheta = iesLamp.horAngles[ i ];
					endTheta = iesLamp.horAngles[ i + 1 ];

					break;

				}

			}

			for ( let i = 0; i < iesLamp.numVerAngles - 1; ++ i ) {

				if ( phi < iesLamp.verAngles[ i + 1 ] || i == iesLamp.numVerAngles - 2 ) {

					phiIndex = i;
					startPhi = iesLamp.verAngles[ i ];
					endPhi = iesLamp.verAngles[ i + 1 ];

					break;

				}

			}

			const deltaTheta = endTheta - startTheta;
			const deltaPhi = endPhi - startPhi;

			if ( deltaPhi === 0 ) // Outside range
				return 0;

			const t1 = deltaTheta === 0 ? 0 : ( theta - startTheta ) / deltaTheta;
			const t2 = ( phi - startPhi ) / deltaPhi;

			const nextThetaIndex = deltaTheta === 0 ? thetaIndex : thetaIndex + 1;

			const v1 = MathUtils.lerp( iesLamp.candelaValues[ thetaIndex ][ phiIndex ], iesLamp.candelaValues[ nextThetaIndex ][ phiIndex ], t1 );
			const v2 = MathUtils.lerp( iesLamp.candelaValues[ thetaIndex ][ phiIndex + 1 ], iesLamp.candelaValues[ nextThetaIndex ][ phiIndex + 1 ], t1 );
			const v = MathUtils.lerp( v1, v2, t2 );

			return v;

		}

		const startTheta = iesLamp.horAngles[ 0 ], endTheta = iesLamp.horAngles[ iesLamp.numHorAngles - 1 ];

		for ( let i = 0; i < size; ++ i ) {

			let theta = i % width;
			const phi = Math.floor( i / width );

			if ( endTheta - startTheta !== 0 && ( theta < startTheta || theta >= endTheta ) ) { // Handle symmetry for hor angles

				theta %= endTheta * 2;

				if ( theta > endTheta )
					theta = endTheta * 2 - theta;

			}

			data[ phi + theta * height ] = interpolateCandelaValues( phi, theta );

		}

		let result = null;

		if ( type === UnsignedByteType ) result = Uint8Array.from( data.map( v => Math.min( v * 0xFF, 0xFF ) ) );
		else if ( type === HalfFloatType ) result = Uint16Array.from( data.map( v => DataUtils.toHalfFloat( v ) ) );
		else if ( type === FloatType ) result = Float32Array.from( data );
		else console.error( 'IESLoader: Unsupported type:', type );

		return result;

	}
```
</details>

##### `load(url: string, onLoad: (arg0: DataTexture) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );
		loader.setResponseType( 'text' );
		loader.setCrossOrigin( this.crossOrigin );
		loader.setWithCredentials( this.withCredentials );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );

		loader.load( url, text => {

			onLoad( this.parse( text ) );

		}, onProgress, onError );

	}
```
</details>

##### `parse(text: string): DataTexture`

<details><summary>Code</summary>

```ts
parse( text ) {

		const type = this.type;

		const iesLamp = new IESLamp( text );
		const data = this._getIESValues( iesLamp, type );

		const texture = new DataTexture( data, 180, 1, RedFormat, type );
		texture.minFilter = LinearFilter;
		texture.magFilter = LinearFilter;
		texture.needsUpdate = true;

		return texture;

	}
```
</details>


---