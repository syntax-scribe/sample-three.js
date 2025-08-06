[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PropertyMixer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 31 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/animation/PropertyMixer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Quaternion` | `../math/Quaternion.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `mixFunction` | `any` | let/var | `*not shown*` | ✗ |
| `mixFunctionAdditive` | `any` | let/var | `*not shown*` | ✗ |
| `setIdentity` | `any` | let/var | `*not shown*` | ✗ |
| `buffer` | `any[] \| Float64Array<ArrayBuffer>` | let/var | `this.buffer` | ✗ |
| `stride` | `number` | let/var | `this.valueSize` | ✗ |
| `offset` | `number` | let/var | `accuIndex * stride + stride` | ✗ |
| `currentWeight` | `number` | let/var | `this.cumulativeWeight` | ✗ |
| `mix` | `number` | let/var | `weight / currentWeight` | ✗ |
| `buffer` | `any[] \| Float64Array<ArrayBuffer>` | let/var | `this.buffer` | ✗ |
| `stride` | `number` | let/var | `this.valueSize` | ✗ |
| `offset` | `number` | let/var | `stride * this._addIndex` | ✗ |
| `stride` | `number` | let/var | `this.valueSize` | ✗ |
| `buffer` | `any[] \| Float64Array<ArrayBuffer>` | let/var | `this.buffer` | ✗ |
| `offset` | `number` | let/var | `accuIndex * stride + stride` | ✗ |
| `weight` | `number` | let/var | `this.cumulativeWeight` | ✗ |
| `weightAdditive` | `number` | let/var | `this.cumulativeWeightAdditive` | ✗ |
| `binding` | `PropertyBinding` | let/var | `this.binding` | ✗ |
| `originalValueOffset` | `number` | let/var | `stride * this._origIndex` | ✗ |
| `binding` | `PropertyBinding` | let/var | `this.binding` | ✗ |
| `buffer` | `any[] \| Float64Array<ArrayBuffer>` | let/var | `this.buffer` | ✗ |
| `stride` | `number` | let/var | `this.valueSize` | ✗ |
| `originalValueOffset` | `number` | let/var | `stride * this._origIndex` | ✗ |
| `originalValueOffset` | `number` | let/var | `this.valueSize * 3` | ✗ |
| `startIndex` | `number` | let/var | `this._addIndex * this.valueSize` | ✗ |
| `endIndex` | `number` | let/var | `startIndex + this.valueSize` | ✗ |
| `startIndex` | `number` | let/var | `this._origIndex * this.valueSize` | ✗ |
| `targetIndex` | `number` | let/var | `this._addIndex * this.valueSize` | ✗ |
| `workOffset` | `number` | let/var | `this._workIndex * stride` | ✗ |
| `s` | `number` | let/var | `1 - t` | ✗ |
| `j` | `any` | let/var | `dstOffset + i` | ✗ |
| `j` | `any` | let/var | `dstOffset + i` | ✗ |


---

## Functions

### `PropertyMixer.accumulate(accuIndex: number, weight: number): void`

**JSDoc:**
```typescript
/**
	 * Accumulates data in the `incoming` region into `accu<i>`.
	 *
	 * @param {number} accuIndex - The accumulation index.
	 * @param {number} weight - The weight.
	 */
```

**Parameters:**

- **`accuIndex`** `number`
- **`weight`** `number`

**Returns:** `void`

**Calls:**

- `this._mixBufferRegion`

**Internal Comments:**
```
// note: happily accumulating nothing when weight = 0, the caller knows (x2)
// the weight and shouldn't have made the call in the first place (x2)
// accuN := incoming * weight
// accuN := accuN + incoming * weight (x3)
```

<details><summary>Code</summary>

```typescript
accumulate( accuIndex, weight ) {

		// note: happily accumulating nothing when weight = 0, the caller knows
		// the weight and shouldn't have made the call in the first place

		const buffer = this.buffer,
			stride = this.valueSize,
			offset = accuIndex * stride + stride;

		let currentWeight = this.cumulativeWeight;

		if ( currentWeight === 0 ) {

			// accuN := incoming * weight

			for ( let i = 0; i !== stride; ++ i ) {

				buffer[ offset + i ] = buffer[ i ];

			}

			currentWeight = weight;

		} else {

			// accuN := accuN + incoming * weight

			currentWeight += weight;
			const mix = weight / currentWeight;
			this._mixBufferRegion( buffer, offset, 0, mix, stride );

		}

		this.cumulativeWeight = currentWeight;

	}
```
</details>

### `PropertyMixer.accumulateAdditive(weight: number): void`

**JSDoc:**
```typescript
/**
	 * Accumulates data in the `incoming` region into `add`.
	 *
	 * @param {number} weight - The weight.
	 */
```

**Parameters:**

- **`weight`** `number`

**Returns:** `void`

**Calls:**

- `this._setIdentity`
- `this._mixBufferRegionAdditive`

**Internal Comments:**
```
// add = identity (x4)
// add := add + incoming * weight (x4)
```

<details><summary>Code</summary>

```typescript
accumulateAdditive( weight ) {

		const buffer = this.buffer,
			stride = this.valueSize,
			offset = stride * this._addIndex;

		if ( this.cumulativeWeightAdditive === 0 ) {

			// add = identity

			this._setIdentity();

		}

		// add := add + incoming * weight

		this._mixBufferRegionAdditive( buffer, offset, 0, weight, stride );
		this.cumulativeWeightAdditive += weight;

	}
```
</details>

### `PropertyMixer.apply(accuIndex: number): void`

**JSDoc:**
```typescript
/**
	 * Applies the state of `accu<i>` to the binding when accus differ.
	 *
	 * @param {number} accuIndex - The accumulation index.
	 */
```

**Parameters:**

- **`accuIndex`** `number`

**Returns:** `void`

**Calls:**

- `this._mixBufferRegion`
- `this._mixBufferRegionAdditive`
- `binding.setValue`

**Internal Comments:**
```
// accuN := accuN + original * ( 1 - cumulativeWeight ) (x2)
// accuN := accuN + additive accuN (x4)
// value has changed -> update scene graph (x4)
```

<details><summary>Code</summary>

```typescript
apply( accuIndex ) {

		const stride = this.valueSize,
			buffer = this.buffer,
			offset = accuIndex * stride + stride,

			weight = this.cumulativeWeight,
			weightAdditive = this.cumulativeWeightAdditive,

			binding = this.binding;

		this.cumulativeWeight = 0;
		this.cumulativeWeightAdditive = 0;

		if ( weight < 1 ) {

			// accuN := accuN + original * ( 1 - cumulativeWeight )

			const originalValueOffset = stride * this._origIndex;

			this._mixBufferRegion(
				buffer, offset, originalValueOffset, 1 - weight, stride );

		}

		if ( weightAdditive > 0 ) {

			// accuN := accuN + additive accuN

			this._mixBufferRegionAdditive( buffer, offset, this._addIndex * stride, 1, stride );

		}

		for ( let i = stride, e = stride + stride; i !== e; ++ i ) {

			if ( buffer[ i ] !== buffer[ i + stride ] ) {

				// value has changed -> update scene graph

				binding.setValue( buffer, offset );
				break;

			}

		}

	}
```
</details>

### `PropertyMixer.saveOriginalState(): void`

**JSDoc:**
```typescript
/**
	 * Remembers the state of the bound property and copy it to both accus.
	 */
```

**Returns:** `void`

**Calls:**

- `binding.getValue`
- `this._setIdentity`

**Internal Comments:**
```
// accu[0..1] := orig -- initially detect changes against the original
// Add to identity for additive (x4)
```

<details><summary>Code</summary>

```typescript
saveOriginalState() {

		const binding = this.binding;

		const buffer = this.buffer,
			stride = this.valueSize,

			originalValueOffset = stride * this._origIndex;

		binding.getValue( buffer, originalValueOffset );

		// accu[0..1] := orig -- initially detect changes against the original
		for ( let i = stride, e = originalValueOffset; i !== e; ++ i ) {

			buffer[ i ] = buffer[ originalValueOffset + ( i % stride ) ];

		}

		// Add to identity for additive
		this._setIdentity();

		this.cumulativeWeight = 0;
		this.cumulativeWeightAdditive = 0;

	}
```
</details>

### `PropertyMixer.restoreOriginalState(): void`

**JSDoc:**
```typescript
/**
	 * Applies the state previously taken via {@link PropertyMixer#saveOriginalState} to the binding.
	 */
```

**Returns:** `void`

**Calls:**

- `this.binding.setValue`

<details><summary>Code</summary>

```typescript
restoreOriginalState() {

		const originalValueOffset = this.valueSize * 3;
		this.binding.setValue( this.buffer, originalValueOffset );

	}
```
</details>

### `PropertyMixer._setAdditiveIdentityNumeric(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setAdditiveIdentityNumeric() {

		const startIndex = this._addIndex * this.valueSize;
		const endIndex = startIndex + this.valueSize;

		for ( let i = startIndex; i < endIndex; i ++ ) {

			this.buffer[ i ] = 0;

		}

	}
```
</details>

### `PropertyMixer._setAdditiveIdentityQuaternion(): void`

**Returns:** `void`

**Calls:**

- `this._setAdditiveIdentityNumeric`

<details><summary>Code</summary>

```typescript
_setAdditiveIdentityQuaternion() {

		this._setAdditiveIdentityNumeric();
		this.buffer[ this._addIndex * this.valueSize + 3 ] = 1;

	}
```
</details>

### `PropertyMixer._setAdditiveIdentityOther(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setAdditiveIdentityOther() {

		const startIndex = this._origIndex * this.valueSize;
		const targetIndex = this._addIndex * this.valueSize;

		for ( let i = 0; i < this.valueSize; i ++ ) {

			this.buffer[ targetIndex + i ] = this.buffer[ startIndex + i ];

		}

	}
```
</details>

### `PropertyMixer._select(buffer: any, dstOffset: any, srcOffset: any, t: any, stride: any): void`

**Parameters:**

- **`buffer`** `any`
- **`dstOffset`** `any`
- **`srcOffset`** `any`
- **`t`** `any`
- **`stride`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_select( buffer, dstOffset, srcOffset, t, stride ) {

		if ( t >= 0.5 ) {

			for ( let i = 0; i !== stride; ++ i ) {

				buffer[ dstOffset + i ] = buffer[ srcOffset + i ];

			}

		}

	}
```
</details>

### `PropertyMixer._slerp(buffer: any, dstOffset: any, srcOffset: any, t: any): void`

**Parameters:**

- **`buffer`** `any`
- **`dstOffset`** `any`
- **`srcOffset`** `any`
- **`t`** `any`

**Returns:** `void`

**Calls:**

- `Quaternion.slerpFlat`

<details><summary>Code</summary>

```typescript
_slerp( buffer, dstOffset, srcOffset, t ) {

		Quaternion.slerpFlat( buffer, dstOffset, buffer, dstOffset, buffer, srcOffset, t );

	}
```
</details>

### `PropertyMixer._slerpAdditive(buffer: any, dstOffset: any, srcOffset: any, t: any, stride: any): void`

**Parameters:**

- **`buffer`** `any`
- **`dstOffset`** `any`
- **`srcOffset`** `any`
- **`t`** `any`
- **`stride`** `any`

**Returns:** `void`

**Calls:**

- `Quaternion.multiplyQuaternionsFlat`
- `Quaternion.slerpFlat`

**Internal Comments:**
```
// Store result in intermediate buffer offset (x4)
// Slerp to the intermediate result (x4)
```

<details><summary>Code</summary>

```typescript
_slerpAdditive( buffer, dstOffset, srcOffset, t, stride ) {

		const workOffset = this._workIndex * stride;

		// Store result in intermediate buffer offset
		Quaternion.multiplyQuaternionsFlat( buffer, workOffset, buffer, dstOffset, buffer, srcOffset );

		// Slerp to the intermediate result
		Quaternion.slerpFlat( buffer, dstOffset, buffer, dstOffset, buffer, workOffset, t );

	}
```
</details>

### `PropertyMixer._lerp(buffer: any, dstOffset: any, srcOffset: any, t: any, stride: any): void`

**Parameters:**

- **`buffer`** `any`
- **`dstOffset`** `any`
- **`srcOffset`** `any`
- **`t`** `any`
- **`stride`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_lerp( buffer, dstOffset, srcOffset, t, stride ) {

		const s = 1 - t;

		for ( let i = 0; i !== stride; ++ i ) {

			const j = dstOffset + i;

			buffer[ j ] = buffer[ j ] * s + buffer[ srcOffset + i ] * t;

		}

	}
```
</details>

### `PropertyMixer._lerpAdditive(buffer: any, dstOffset: any, srcOffset: any, t: any, stride: any): void`

**Parameters:**

- **`buffer`** `any`
- **`dstOffset`** `any`
- **`srcOffset`** `any`
- **`t`** `any`
- **`stride`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_lerpAdditive( buffer, dstOffset, srcOffset, t, stride ) {

		for ( let i = 0; i !== stride; ++ i ) {

			const j = dstOffset + i;

			buffer[ j ] = buffer[ j ] + buffer[ srcOffset + i ] * t;

		}

	}
```
</details>


---

## Classes

### `PropertyMixer`

<details><summary>Class Code</summary>

```ts
class PropertyMixer {

	/**
	 * Constructs a new property mixer.
	 *
	 * @param {PropertyBinding} binding - The property binding.
	 * @param {string} typeName - The keyframe track type name.
	 * @param {number} valueSize - The keyframe track value size.
	 */
	constructor( binding, typeName, valueSize ) {

		/**
		 * The property binding.
		 *
		 * @type {PropertyBinding}
		 */
		this.binding = binding;

		/**
		 * The keyframe track value size.
		 *
		 * @type {number}
		 */
		this.valueSize = valueSize;

		let mixFunction,
			mixFunctionAdditive,
			setIdentity;

		// buffer layout: [ incoming | accu0 | accu1 | orig | addAccu | (optional work) ]
		//
		// interpolators can use .buffer as their .result
		// the data then goes to 'incoming'
		//
		// 'accu0' and 'accu1' are used frame-interleaved for
		// the cumulative result and are compared to detect
		// changes
		//
		// 'orig' stores the original state of the property
		//
		// 'add' is used for additive cumulative results
		//
		// 'work' is optional and is only present for quaternion types. It is used
		// to store intermediate quaternion multiplication results

		switch ( typeName ) {

			case 'quaternion':
				mixFunction = this._slerp;
				mixFunctionAdditive = this._slerpAdditive;
				setIdentity = this._setAdditiveIdentityQuaternion;

				this.buffer = new Float64Array( valueSize * 6 );
				this._workIndex = 5;
				break;

			case 'string':
			case 'bool':
				mixFunction = this._select;

				// Use the regular mix function and for additive on these types,
				// additive is not relevant for non-numeric types
				mixFunctionAdditive = this._select;

				setIdentity = this._setAdditiveIdentityOther;

				this.buffer = new Array( valueSize * 5 );
				break;

			default:
				mixFunction = this._lerp;
				mixFunctionAdditive = this._lerpAdditive;
				setIdentity = this._setAdditiveIdentityNumeric;

				this.buffer = new Float64Array( valueSize * 5 );

		}

		this._mixBufferRegion = mixFunction;
		this._mixBufferRegionAdditive = mixFunctionAdditive;
		this._setIdentity = setIdentity;
		this._origIndex = 3;
		this._addIndex = 4;

		/**
		 * TODO
		 *
		 * @type {number}
		 * @default 0
		 */
		this.cumulativeWeight = 0;

		/**
		 * TODO
		 *
		 * @type {number}
		 * @default 0
		 */
		this.cumulativeWeightAdditive = 0;

		/**
		 * TODO
		 *
		 * @type {number}
		 * @default 0
		 */
		this.useCount = 0;

		/**
		 * TODO
		 *
		 * @type {number}
		 * @default 0
		 */
		this.referenceCount = 0;

	}

	/**
	 * Accumulates data in the `incoming` region into `accu<i>`.
	 *
	 * @param {number} accuIndex - The accumulation index.
	 * @param {number} weight - The weight.
	 */
	accumulate( accuIndex, weight ) {

		// note: happily accumulating nothing when weight = 0, the caller knows
		// the weight and shouldn't have made the call in the first place

		const buffer = this.buffer,
			stride = this.valueSize,
			offset = accuIndex * stride + stride;

		let currentWeight = this.cumulativeWeight;

		if ( currentWeight === 0 ) {

			// accuN := incoming * weight

			for ( let i = 0; i !== stride; ++ i ) {

				buffer[ offset + i ] = buffer[ i ];

			}

			currentWeight = weight;

		} else {

			// accuN := accuN + incoming * weight

			currentWeight += weight;
			const mix = weight / currentWeight;
			this._mixBufferRegion( buffer, offset, 0, mix, stride );

		}

		this.cumulativeWeight = currentWeight;

	}

	/**
	 * Accumulates data in the `incoming` region into `add`.
	 *
	 * @param {number} weight - The weight.
	 */
	accumulateAdditive( weight ) {

		const buffer = this.buffer,
			stride = this.valueSize,
			offset = stride * this._addIndex;

		if ( this.cumulativeWeightAdditive === 0 ) {

			// add = identity

			this._setIdentity();

		}

		// add := add + incoming * weight

		this._mixBufferRegionAdditive( buffer, offset, 0, weight, stride );
		this.cumulativeWeightAdditive += weight;

	}

	/**
	 * Applies the state of `accu<i>` to the binding when accus differ.
	 *
	 * @param {number} accuIndex - The accumulation index.
	 */
	apply( accuIndex ) {

		const stride = this.valueSize,
			buffer = this.buffer,
			offset = accuIndex * stride + stride,

			weight = this.cumulativeWeight,
			weightAdditive = this.cumulativeWeightAdditive,

			binding = this.binding;

		this.cumulativeWeight = 0;
		this.cumulativeWeightAdditive = 0;

		if ( weight < 1 ) {

			// accuN := accuN + original * ( 1 - cumulativeWeight )

			const originalValueOffset = stride * this._origIndex;

			this._mixBufferRegion(
				buffer, offset, originalValueOffset, 1 - weight, stride );

		}

		if ( weightAdditive > 0 ) {

			// accuN := accuN + additive accuN

			this._mixBufferRegionAdditive( buffer, offset, this._addIndex * stride, 1, stride );

		}

		for ( let i = stride, e = stride + stride; i !== e; ++ i ) {

			if ( buffer[ i ] !== buffer[ i + stride ] ) {

				// value has changed -> update scene graph

				binding.setValue( buffer, offset );
				break;

			}

		}

	}


	/**
	 * Remembers the state of the bound property and copy it to both accus.
	 */
	saveOriginalState() {

		const binding = this.binding;

		const buffer = this.buffer,
			stride = this.valueSize,

			originalValueOffset = stride * this._origIndex;

		binding.getValue( buffer, originalValueOffset );

		// accu[0..1] := orig -- initially detect changes against the original
		for ( let i = stride, e = originalValueOffset; i !== e; ++ i ) {

			buffer[ i ] = buffer[ originalValueOffset + ( i % stride ) ];

		}

		// Add to identity for additive
		this._setIdentity();

		this.cumulativeWeight = 0;
		this.cumulativeWeightAdditive = 0;

	}

	/**
	 * Applies the state previously taken via {@link PropertyMixer#saveOriginalState} to the binding.
	 */
	restoreOriginalState() {

		const originalValueOffset = this.valueSize * 3;
		this.binding.setValue( this.buffer, originalValueOffset );

	}

	// internals

	_setAdditiveIdentityNumeric() {

		const startIndex = this._addIndex * this.valueSize;
		const endIndex = startIndex + this.valueSize;

		for ( let i = startIndex; i < endIndex; i ++ ) {

			this.buffer[ i ] = 0;

		}

	}

	_setAdditiveIdentityQuaternion() {

		this._setAdditiveIdentityNumeric();
		this.buffer[ this._addIndex * this.valueSize + 3 ] = 1;

	}

	_setAdditiveIdentityOther() {

		const startIndex = this._origIndex * this.valueSize;
		const targetIndex = this._addIndex * this.valueSize;

		for ( let i = 0; i < this.valueSize; i ++ ) {

			this.buffer[ targetIndex + i ] = this.buffer[ startIndex + i ];

		}

	}


	// mix functions

	_select( buffer, dstOffset, srcOffset, t, stride ) {

		if ( t >= 0.5 ) {

			for ( let i = 0; i !== stride; ++ i ) {

				buffer[ dstOffset + i ] = buffer[ srcOffset + i ];

			}

		}

	}

	_slerp( buffer, dstOffset, srcOffset, t ) {

		Quaternion.slerpFlat( buffer, dstOffset, buffer, dstOffset, buffer, srcOffset, t );

	}

	_slerpAdditive( buffer, dstOffset, srcOffset, t, stride ) {

		const workOffset = this._workIndex * stride;

		// Store result in intermediate buffer offset
		Quaternion.multiplyQuaternionsFlat( buffer, workOffset, buffer, dstOffset, buffer, srcOffset );

		// Slerp to the intermediate result
		Quaternion.slerpFlat( buffer, dstOffset, buffer, dstOffset, buffer, workOffset, t );

	}

	_lerp( buffer, dstOffset, srcOffset, t, stride ) {

		const s = 1 - t;

		for ( let i = 0; i !== stride; ++ i ) {

			const j = dstOffset + i;

			buffer[ j ] = buffer[ j ] * s + buffer[ srcOffset + i ] * t;

		}

	}

	_lerpAdditive( buffer, dstOffset, srcOffset, t, stride ) {

		for ( let i = 0; i !== stride; ++ i ) {

			const j = dstOffset + i;

			buffer[ j ] = buffer[ j ] + buffer[ srcOffset + i ] * t;

		}

	}

}
```
</details>

#### Methods

##### `accumulate(accuIndex: number, weight: number): void`

<details><summary>Code</summary>

```ts
accumulate( accuIndex, weight ) {

		// note: happily accumulating nothing when weight = 0, the caller knows
		// the weight and shouldn't have made the call in the first place

		const buffer = this.buffer,
			stride = this.valueSize,
			offset = accuIndex * stride + stride;

		let currentWeight = this.cumulativeWeight;

		if ( currentWeight === 0 ) {

			// accuN := incoming * weight

			for ( let i = 0; i !== stride; ++ i ) {

				buffer[ offset + i ] = buffer[ i ];

			}

			currentWeight = weight;

		} else {

			// accuN := accuN + incoming * weight

			currentWeight += weight;
			const mix = weight / currentWeight;
			this._mixBufferRegion( buffer, offset, 0, mix, stride );

		}

		this.cumulativeWeight = currentWeight;

	}
```
</details>

##### `accumulateAdditive(weight: number): void`

<details><summary>Code</summary>

```ts
accumulateAdditive( weight ) {

		const buffer = this.buffer,
			stride = this.valueSize,
			offset = stride * this._addIndex;

		if ( this.cumulativeWeightAdditive === 0 ) {

			// add = identity

			this._setIdentity();

		}

		// add := add + incoming * weight

		this._mixBufferRegionAdditive( buffer, offset, 0, weight, stride );
		this.cumulativeWeightAdditive += weight;

	}
```
</details>

##### `apply(accuIndex: number): void`

<details><summary>Code</summary>

```ts
apply( accuIndex ) {

		const stride = this.valueSize,
			buffer = this.buffer,
			offset = accuIndex * stride + stride,

			weight = this.cumulativeWeight,
			weightAdditive = this.cumulativeWeightAdditive,

			binding = this.binding;

		this.cumulativeWeight = 0;
		this.cumulativeWeightAdditive = 0;

		if ( weight < 1 ) {

			// accuN := accuN + original * ( 1 - cumulativeWeight )

			const originalValueOffset = stride * this._origIndex;

			this._mixBufferRegion(
				buffer, offset, originalValueOffset, 1 - weight, stride );

		}

		if ( weightAdditive > 0 ) {

			// accuN := accuN + additive accuN

			this._mixBufferRegionAdditive( buffer, offset, this._addIndex * stride, 1, stride );

		}

		for ( let i = stride, e = stride + stride; i !== e; ++ i ) {

			if ( buffer[ i ] !== buffer[ i + stride ] ) {

				// value has changed -> update scene graph

				binding.setValue( buffer, offset );
				break;

			}

		}

	}
```
</details>

##### `saveOriginalState(): void`

<details><summary>Code</summary>

```ts
saveOriginalState() {

		const binding = this.binding;

		const buffer = this.buffer,
			stride = this.valueSize,

			originalValueOffset = stride * this._origIndex;

		binding.getValue( buffer, originalValueOffset );

		// accu[0..1] := orig -- initially detect changes against the original
		for ( let i = stride, e = originalValueOffset; i !== e; ++ i ) {

			buffer[ i ] = buffer[ originalValueOffset + ( i % stride ) ];

		}

		// Add to identity for additive
		this._setIdentity();

		this.cumulativeWeight = 0;
		this.cumulativeWeightAdditive = 0;

	}
```
</details>

##### `restoreOriginalState(): void`

<details><summary>Code</summary>

```ts
restoreOriginalState() {

		const originalValueOffset = this.valueSize * 3;
		this.binding.setValue( this.buffer, originalValueOffset );

	}
```
</details>

##### `_setAdditiveIdentityNumeric(): void`

<details><summary>Code</summary>

```ts
_setAdditiveIdentityNumeric() {

		const startIndex = this._addIndex * this.valueSize;
		const endIndex = startIndex + this.valueSize;

		for ( let i = startIndex; i < endIndex; i ++ ) {

			this.buffer[ i ] = 0;

		}

	}
```
</details>

##### `_setAdditiveIdentityQuaternion(): void`

<details><summary>Code</summary>

```ts
_setAdditiveIdentityQuaternion() {

		this._setAdditiveIdentityNumeric();
		this.buffer[ this._addIndex * this.valueSize + 3 ] = 1;

	}
```
</details>

##### `_setAdditiveIdentityOther(): void`

<details><summary>Code</summary>

```ts
_setAdditiveIdentityOther() {

		const startIndex = this._origIndex * this.valueSize;
		const targetIndex = this._addIndex * this.valueSize;

		for ( let i = 0; i < this.valueSize; i ++ ) {

			this.buffer[ targetIndex + i ] = this.buffer[ startIndex + i ];

		}

	}
```
</details>

##### `_select(buffer: any, dstOffset: any, srcOffset: any, t: any, stride: any): void`

<details><summary>Code</summary>

```ts
_select( buffer, dstOffset, srcOffset, t, stride ) {

		if ( t >= 0.5 ) {

			for ( let i = 0; i !== stride; ++ i ) {

				buffer[ dstOffset + i ] = buffer[ srcOffset + i ];

			}

		}

	}
```
</details>

##### `_slerp(buffer: any, dstOffset: any, srcOffset: any, t: any): void`

<details><summary>Code</summary>

```ts
_slerp( buffer, dstOffset, srcOffset, t ) {

		Quaternion.slerpFlat( buffer, dstOffset, buffer, dstOffset, buffer, srcOffset, t );

	}
```
</details>

##### `_slerpAdditive(buffer: any, dstOffset: any, srcOffset: any, t: any, stride: any): void`

<details><summary>Code</summary>

```ts
_slerpAdditive( buffer, dstOffset, srcOffset, t, stride ) {

		const workOffset = this._workIndex * stride;

		// Store result in intermediate buffer offset
		Quaternion.multiplyQuaternionsFlat( buffer, workOffset, buffer, dstOffset, buffer, srcOffset );

		// Slerp to the intermediate result
		Quaternion.slerpFlat( buffer, dstOffset, buffer, dstOffset, buffer, workOffset, t );

	}
```
</details>

##### `_lerp(buffer: any, dstOffset: any, srcOffset: any, t: any, stride: any): void`

<details><summary>Code</summary>

```ts
_lerp( buffer, dstOffset, srcOffset, t, stride ) {

		const s = 1 - t;

		for ( let i = 0; i !== stride; ++ i ) {

			const j = dstOffset + i;

			buffer[ j ] = buffer[ j ] * s + buffer[ srcOffset + i ] * t;

		}

	}
```
</details>

##### `_lerpAdditive(buffer: any, dstOffset: any, srcOffset: any, t: any, stride: any): void`

<details><summary>Code</summary>

```ts
_lerpAdditive( buffer, dstOffset, srcOffset, t, stride ) {

		for ( let i = 0; i !== stride; ++ i ) {

			const j = dstOffset + i;

			buffer[ j ] = buffer[ j ] + buffer[ srcOffset + i ] * t;

		}

	}
```
</details>


---