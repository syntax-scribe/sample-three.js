[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Interpolant.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Interpolant.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `pp` | `TypedArray` | let/var | `this.parameterPositions` | ✗ |
| `i1` | `number` | let/var | `this._cachedIndex` | ✗ |
| `t1` | `TypedArray` | let/var | `pp[ i1 ]` | ✗ |
| `t0` | `TypedArray` | let/var | `pp[ i1 - 1 ]` | ✗ |
| `right` | `any` | let/var | `*not shown*` | ✗ |
| `t1global` | `TypedArray` | let/var | `pp[ 1 ]` | ✗ |
| `mid` | `any` | let/var | `( i1 + right ) >>> 1` | ✗ |
| `result` | `TypedArray` | let/var | `this.resultBuffer` | ✗ |
| `values` | `TypedArray` | let/var | `this.sampleValues` | ✗ |
| `stride` | `TypedArray` | let/var | `this.valueSize` | ✗ |
| `offset` | `number` | let/var | `index * stride` | ✗ |


---

## Functions

### `Interpolant.evaluate(t: number): TypedArray`

**JSDoc:**
```typescript
/**
	 * Evaluate the interpolant at position `t`.
	 *
	 * @param {number} t - The interpolation factor.
	 * @return {TypedArray} The result buffer.
	 */
```

**Parameters:**

- **`t`** `number`

**Returns:** `TypedArray`

**Calls:**

- `this.copySampleValue_`
- `this.intervalChanged_`
- `this.interpolate_`

**Internal Comments:**
```
//- See http://jsperf.com/comparison-to-undefined/3 (x2)
//- slower code: (x3)
//- (x2)
//- 				if ( t >= t1 || t1 === undefined ) { (x2)
// after end (x3)
// we have arrived at the sought interval (x2)
// prepare binary search on the right side of the index (x3)
//-					if ( t < t0 || t0 === undefined ) {
// looping? (x2)
// linear reverse scan
// before start (x4)
// prepare binary search on the left side of the index (x3)
// the interval is valid
// binary search
// check boundary cases, again
```

<details><summary>Code</summary>

```typescript
evaluate( t ) {

		const pp = this.parameterPositions;
		let i1 = this._cachedIndex,
			t1 = pp[ i1 ],
			t0 = pp[ i1 - 1 ];

		validate_interval: {

			seek: {

				let right;

				linear_scan: {

					//- See http://jsperf.com/comparison-to-undefined/3
					//- slower code:
					//-
					//- 				if ( t >= t1 || t1 === undefined ) {
					forward_scan: if ( ! ( t < t1 ) ) {

						for ( let giveUpAt = i1 + 2; ; ) {

							if ( t1 === undefined ) {

								if ( t < t0 ) break forward_scan;

								// after end

								i1 = pp.length;
								this._cachedIndex = i1;
								return this.copySampleValue_( i1 - 1 );

							}

							if ( i1 === giveUpAt ) break; // this loop

							t0 = t1;
							t1 = pp[ ++ i1 ];

							if ( t < t1 ) {

								// we have arrived at the sought interval
								break seek;

							}

						}

						// prepare binary search on the right side of the index
						right = pp.length;
						break linear_scan;

					}

					//- slower code:
					//-					if ( t < t0 || t0 === undefined ) {
					if ( ! ( t >= t0 ) ) {

						// looping?

						const t1global = pp[ 1 ];

						if ( t < t1global ) {

							i1 = 2; // + 1, using the scan for the details
							t0 = t1global;

						}

						// linear reverse scan

						for ( let giveUpAt = i1 - 2; ; ) {

							if ( t0 === undefined ) {

								// before start

								this._cachedIndex = 0;
								return this.copySampleValue_( 0 );

							}

							if ( i1 === giveUpAt ) break; // this loop

							t1 = t0;
							t0 = pp[ -- i1 - 1 ];

							if ( t >= t0 ) {

								// we have arrived at the sought interval
								break seek;

							}

						}

						// prepare binary search on the left side of the index
						right = i1;
						i1 = 0;
						break linear_scan;

					}

					// the interval is valid

					break validate_interval;

				} // linear scan

				// binary search

				while ( i1 < right ) {

					const mid = ( i1 + right ) >>> 1;

					if ( t < pp[ mid ] ) {

						right = mid;

					} else {

						i1 = mid + 1;

					}

				}

				t1 = pp[ i1 ];
				t0 = pp[ i1 - 1 ];

				// check boundary cases, again

				if ( t0 === undefined ) {

					this._cachedIndex = 0;
					return this.copySampleValue_( 0 );

				}

				if ( t1 === undefined ) {

					i1 = pp.length;
					this._cachedIndex = i1;
					return this.copySampleValue_( i1 - 1 );

				}

			} // seek

			this._cachedIndex = i1;

			this.intervalChanged_( i1, t0, t1 );

		} // validate_interval

		return this.interpolate_( i1, t0, t, t1 );

	}
```
</details>

### `Interpolant.getSettings_(): any`

**JSDoc:**
```typescript
/**
	 * Returns the interpolation settings.
	 *
	 * @return {Object} The interpolation settings.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getSettings_() {

		return this.settings || this.DefaultSettings_;

	}
```
</details>

### `Interpolant.copySampleValue_(index: number): TypedArray`

**JSDoc:**
```typescript
/**
	 * Copies a sample value to the result buffer.
	 *
	 * @param {number} index - An index into the sample value buffer.
	 * @return {TypedArray} The result buffer.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `TypedArray`

**Internal Comments:**
```
// copies a sample value to the result buffer (x2)
```

<details><summary>Code</summary>

```typescript
copySampleValue_( index ) {

		// copies a sample value to the result buffer

		const result = this.resultBuffer,
			values = this.sampleValues,
			stride = this.valueSize,
			offset = index * stride;

		for ( let i = 0; i !== stride; ++ i ) {

			result[ i ] = values[ offset + i ];

		}

		return result;

	}
```
</details>

### `Interpolant.interpolate_(): TypedArray`

**JSDoc:**
```typescript
/**
	 * Copies a sample value to the result buffer.
	 *
	 * @abstract
	 * @param {number} i1 - An index into the sample value buffer.
	 * @param {number} t0 - The previous interpolation factor.
	 * @param {number} t - The current interpolation factor.
	 * @param {number} t1 - The next interpolation factor.
	 * @return {TypedArray} The result buffer.
	 */
```

**Returns:** `TypedArray`

<details><summary>Code</summary>

```typescript
interpolate_( /* i1, t0, t, t1 */ ) {

		throw new Error( 'call to abstract method' );
		// implementations shall return this.resultBuffer

	}
```
</details>

### `Interpolant.intervalChanged_(): void`

**JSDoc:**
```typescript
/**
	 * Optional method that is executed when the interval has changed.
	 *
	 * @param {number} i1 - An index into the sample value buffer.
	 * @param {number} t0 - The previous interpolation factor.
	 * @param {number} t - The current interpolation factor.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
intervalChanged_( /* i1, t0, t1 */ ) {

		// empty

	}
```
</details>


---

## Classes

### `Interpolant`

<details><summary>Class Code</summary>

```ts
class Interpolant {

	/**
	 * Constructs a new interpolant.
	 *
	 * @param {TypedArray} parameterPositions - The parameter positions hold the interpolation factors.
	 * @param {TypedArray} sampleValues - The sample values.
	 * @param {number} sampleSize - The sample size
	 * @param {TypedArray} [resultBuffer] - The result buffer.
	 */
	constructor( parameterPositions, sampleValues, sampleSize, resultBuffer ) {

		/**
		 * The parameter positions.
		 *
		 * @type {TypedArray}
		 */
		this.parameterPositions = parameterPositions;

		/**
		 * A cache index.
		 *
		 * @private
		 * @type {number}
		 * @default 0
		 */
		this._cachedIndex = 0;

		/**
		 * The result buffer.
		 *
		 * @type {TypedArray}
		 */
		this.resultBuffer = resultBuffer !== undefined ? resultBuffer : new sampleValues.constructor( sampleSize );

		/**
		 * The sample values.
		 *
		 * @type {TypedArray}
		 */
		this.sampleValues = sampleValues;

		/**
		 * The value size.
		 *
		 * @type {TypedArray}
		 */
		this.valueSize = sampleSize;

		/**
		 * The interpolation settings.
		 *
		 * @type {?Object}
		 * @default null
		 */
		this.settings = null;

		/**
		 * The default settings object.
		 *
		 * @type {Object}
		 */
		this.DefaultSettings_ = {};

	}

	/**
	 * Evaluate the interpolant at position `t`.
	 *
	 * @param {number} t - The interpolation factor.
	 * @return {TypedArray} The result buffer.
	 */
	evaluate( t ) {

		const pp = this.parameterPositions;
		let i1 = this._cachedIndex,
			t1 = pp[ i1 ],
			t0 = pp[ i1 - 1 ];

		validate_interval: {

			seek: {

				let right;

				linear_scan: {

					//- See http://jsperf.com/comparison-to-undefined/3
					//- slower code:
					//-
					//- 				if ( t >= t1 || t1 === undefined ) {
					forward_scan: if ( ! ( t < t1 ) ) {

						for ( let giveUpAt = i1 + 2; ; ) {

							if ( t1 === undefined ) {

								if ( t < t0 ) break forward_scan;

								// after end

								i1 = pp.length;
								this._cachedIndex = i1;
								return this.copySampleValue_( i1 - 1 );

							}

							if ( i1 === giveUpAt ) break; // this loop

							t0 = t1;
							t1 = pp[ ++ i1 ];

							if ( t < t1 ) {

								// we have arrived at the sought interval
								break seek;

							}

						}

						// prepare binary search on the right side of the index
						right = pp.length;
						break linear_scan;

					}

					//- slower code:
					//-					if ( t < t0 || t0 === undefined ) {
					if ( ! ( t >= t0 ) ) {

						// looping?

						const t1global = pp[ 1 ];

						if ( t < t1global ) {

							i1 = 2; // + 1, using the scan for the details
							t0 = t1global;

						}

						// linear reverse scan

						for ( let giveUpAt = i1 - 2; ; ) {

							if ( t0 === undefined ) {

								// before start

								this._cachedIndex = 0;
								return this.copySampleValue_( 0 );

							}

							if ( i1 === giveUpAt ) break; // this loop

							t1 = t0;
							t0 = pp[ -- i1 - 1 ];

							if ( t >= t0 ) {

								// we have arrived at the sought interval
								break seek;

							}

						}

						// prepare binary search on the left side of the index
						right = i1;
						i1 = 0;
						break linear_scan;

					}

					// the interval is valid

					break validate_interval;

				} // linear scan

				// binary search

				while ( i1 < right ) {

					const mid = ( i1 + right ) >>> 1;

					if ( t < pp[ mid ] ) {

						right = mid;

					} else {

						i1 = mid + 1;

					}

				}

				t1 = pp[ i1 ];
				t0 = pp[ i1 - 1 ];

				// check boundary cases, again

				if ( t0 === undefined ) {

					this._cachedIndex = 0;
					return this.copySampleValue_( 0 );

				}

				if ( t1 === undefined ) {

					i1 = pp.length;
					this._cachedIndex = i1;
					return this.copySampleValue_( i1 - 1 );

				}

			} // seek

			this._cachedIndex = i1;

			this.intervalChanged_( i1, t0, t1 );

		} // validate_interval

		return this.interpolate_( i1, t0, t, t1 );

	}

	/**
	 * Returns the interpolation settings.
	 *
	 * @return {Object} The interpolation settings.
	 */
	getSettings_() {

		return this.settings || this.DefaultSettings_;

	}

	/**
	 * Copies a sample value to the result buffer.
	 *
	 * @param {number} index - An index into the sample value buffer.
	 * @return {TypedArray} The result buffer.
	 */
	copySampleValue_( index ) {

		// copies a sample value to the result buffer

		const result = this.resultBuffer,
			values = this.sampleValues,
			stride = this.valueSize,
			offset = index * stride;

		for ( let i = 0; i !== stride; ++ i ) {

			result[ i ] = values[ offset + i ];

		}

		return result;

	}

	/**
	 * Copies a sample value to the result buffer.
	 *
	 * @abstract
	 * @param {number} i1 - An index into the sample value buffer.
	 * @param {number} t0 - The previous interpolation factor.
	 * @param {number} t - The current interpolation factor.
	 * @param {number} t1 - The next interpolation factor.
	 * @return {TypedArray} The result buffer.
	 */
	interpolate_( /* i1, t0, t, t1 */ ) {

		throw new Error( 'call to abstract method' );
		// implementations shall return this.resultBuffer

	}

	/**
	 * Optional method that is executed when the interval has changed.
	 *
	 * @param {number} i1 - An index into the sample value buffer.
	 * @param {number} t0 - The previous interpolation factor.
	 * @param {number} t - The current interpolation factor.
	 */
	intervalChanged_( /* i1, t0, t1 */ ) {

		// empty

	}

}
```
</details>

#### Methods

##### `evaluate(t: number): TypedArray`

<details><summary>Code</summary>

```ts
evaluate( t ) {

		const pp = this.parameterPositions;
		let i1 = this._cachedIndex,
			t1 = pp[ i1 ],
			t0 = pp[ i1 - 1 ];

		validate_interval: {

			seek: {

				let right;

				linear_scan: {

					//- See http://jsperf.com/comparison-to-undefined/3
					//- slower code:
					//-
					//- 				if ( t >= t1 || t1 === undefined ) {
					forward_scan: if ( ! ( t < t1 ) ) {

						for ( let giveUpAt = i1 + 2; ; ) {

							if ( t1 === undefined ) {

								if ( t < t0 ) break forward_scan;

								// after end

								i1 = pp.length;
								this._cachedIndex = i1;
								return this.copySampleValue_( i1 - 1 );

							}

							if ( i1 === giveUpAt ) break; // this loop

							t0 = t1;
							t1 = pp[ ++ i1 ];

							if ( t < t1 ) {

								// we have arrived at the sought interval
								break seek;

							}

						}

						// prepare binary search on the right side of the index
						right = pp.length;
						break linear_scan;

					}

					//- slower code:
					//-					if ( t < t0 || t0 === undefined ) {
					if ( ! ( t >= t0 ) ) {

						// looping?

						const t1global = pp[ 1 ];

						if ( t < t1global ) {

							i1 = 2; // + 1, using the scan for the details
							t0 = t1global;

						}

						// linear reverse scan

						for ( let giveUpAt = i1 - 2; ; ) {

							if ( t0 === undefined ) {

								// before start

								this._cachedIndex = 0;
								return this.copySampleValue_( 0 );

							}

							if ( i1 === giveUpAt ) break; // this loop

							t1 = t0;
							t0 = pp[ -- i1 - 1 ];

							if ( t >= t0 ) {

								// we have arrived at the sought interval
								break seek;

							}

						}

						// prepare binary search on the left side of the index
						right = i1;
						i1 = 0;
						break linear_scan;

					}

					// the interval is valid

					break validate_interval;

				} // linear scan

				// binary search

				while ( i1 < right ) {

					const mid = ( i1 + right ) >>> 1;

					if ( t < pp[ mid ] ) {

						right = mid;

					} else {

						i1 = mid + 1;

					}

				}

				t1 = pp[ i1 ];
				t0 = pp[ i1 - 1 ];

				// check boundary cases, again

				if ( t0 === undefined ) {

					this._cachedIndex = 0;
					return this.copySampleValue_( 0 );

				}

				if ( t1 === undefined ) {

					i1 = pp.length;
					this._cachedIndex = i1;
					return this.copySampleValue_( i1 - 1 );

				}

			} // seek

			this._cachedIndex = i1;

			this.intervalChanged_( i1, t0, t1 );

		} // validate_interval

		return this.interpolate_( i1, t0, t, t1 );

	}
```
</details>

##### `getSettings_(): any`

<details><summary>Code</summary>

```ts
getSettings_() {

		return this.settings || this.DefaultSettings_;

	}
```
</details>

##### `copySampleValue_(index: number): TypedArray`

<details><summary>Code</summary>

```ts
copySampleValue_( index ) {

		// copies a sample value to the result buffer

		const result = this.resultBuffer,
			values = this.sampleValues,
			stride = this.valueSize,
			offset = index * stride;

		for ( let i = 0; i !== stride; ++ i ) {

			result[ i ] = values[ offset + i ];

		}

		return result;

	}
```
</details>

##### `interpolate_(): TypedArray`

<details><summary>Code</summary>

```ts
interpolate_( /* i1, t0, t, t1 */ ) {

		throw new Error( 'call to abstract method' );
		// implementations shall return this.resultBuffer

	}
```
</details>

##### `intervalChanged_(): void`

<details><summary>Code</summary>

```ts
intervalChanged_( /* i1, t0, t1 */ ) {

		// empty

	}
```
</details>


---