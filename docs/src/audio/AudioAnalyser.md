[⬅️ Back to Table of Contents](../../index.md)

# 📄 `AudioAnalyser.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/audio/AudioAnalyser.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `value` | `number` | let/var | `0` | ✗ |


---

## Functions

### `AudioAnalyser.getFrequencyData(): Uint8Array<ArrayBufferLike>`

**JSDoc:**
```typescript
/**
	 * Returns an array with frequency data of the audio.
	 *
	 * Each item in the array represents the decibel value for a specific frequency.
	 * The frequencies are spread linearly from 0 to 1/2 of the sample rate.
	 * For example, for 48000 sample rate, the last item of the array will represent
	 * the decibel value for 24000 Hz.
	 *
	 * @return {Uint8Array} The frequency data.
	 */
```

**Returns:** `Uint8Array<ArrayBufferLike>`

**Calls:**

- `this.analyser.getByteFrequencyData`

<details><summary>Code</summary>

```typescript
getFrequencyData() {

		this.analyser.getByteFrequencyData( this.data );

		return this.data;

	}
```
</details>

### `AudioAnalyser.getAverageFrequency(): number`

**JSDoc:**
```typescript
/**
	 * Returns the average of the frequencies returned by {@link AudioAnalyser#getFrequencyData}.
	 *
	 * @return {number} The average frequency.
	 */
```

**Returns:** `number`

**Calls:**

- `this.getFrequencyData`

<details><summary>Code</summary>

```typescript
getAverageFrequency() {

		let value = 0;
		const data = this.getFrequencyData();

		for ( let i = 0; i < data.length; i ++ ) {

			value += data[ i ];

		}

		return value / data.length;

	}
```
</details>


---

## Classes

### `AudioAnalyser`

<details><summary>Class Code</summary>

```ts
class AudioAnalyser {

	/**
	 * Constructs a new audio analyzer.
	 *
	 * @param {Audio} audio - The audio to analyze.
	 * @param {number} [fftSize=2048] - The window size in samples that is used when performing a Fast Fourier Transform (FFT) to get frequency domain data.
	 */
	constructor( audio, fftSize = 2048 ) {

		/**
		 * The global audio listener.
		 *
		 * @type {AnalyserNode}
		 */
		this.analyser = audio.context.createAnalyser();
		this.analyser.fftSize = fftSize;

		/**
		 * Holds the analyzed data.
		 *
		 * @type {Uint8Array}
		 */
		this.data = new Uint8Array( this.analyser.frequencyBinCount );

		audio.getOutput().connect( this.analyser );

	}

	/**
	 * Returns an array with frequency data of the audio.
	 *
	 * Each item in the array represents the decibel value for a specific frequency.
	 * The frequencies are spread linearly from 0 to 1/2 of the sample rate.
	 * For example, for 48000 sample rate, the last item of the array will represent
	 * the decibel value for 24000 Hz.
	 *
	 * @return {Uint8Array} The frequency data.
	 */
	getFrequencyData() {

		this.analyser.getByteFrequencyData( this.data );

		return this.data;

	}

	/**
	 * Returns the average of the frequencies returned by {@link AudioAnalyser#getFrequencyData}.
	 *
	 * @return {number} The average frequency.
	 */
	getAverageFrequency() {

		let value = 0;
		const data = this.getFrequencyData();

		for ( let i = 0; i < data.length; i ++ ) {

			value += data[ i ];

		}

		return value / data.length;

	}

}
```
</details>

#### Methods

##### `getFrequencyData(): Uint8Array<ArrayBufferLike>`

<details><summary>Code</summary>

```ts
getFrequencyData() {

		this.analyser.getByteFrequencyData( this.data );

		return this.data;

	}
```
</details>

##### `getAverageFrequency(): number`

<details><summary>Code</summary>

```ts
getAverageFrequency() {

		let value = 0;
		const data = this.getFrequencyData();

		for ( let i = 0; i < data.length; i ++ ) {

			value += data[ i ];

		}

		return value / data.length;

	}
```
</details>


---