[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Audio.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 27 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/audio/Audio.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Object3D` | `../core/Object3D.js` |


---

## Functions

### `Audio.getOutput(): GainNode`

**JSDoc:**
```typescript
/**
	 * Returns the output audio node.
	 *
	 * @return {GainNode} The output node.
	 */
```

**Returns:** `GainNode`

<details><summary>Code</summary>

```typescript
getOutput() {

		return this.gain;

	}
```
</details>

### `Audio.setNodeSource(audioNode: AudioNode): Audio`

**JSDoc:**
```typescript
/**
	 * Sets the given audio node as the source of this instance.
	 *
	 * {@link Audio#sourceType} is set to `audioNode` and {@link Audio#hasPlaybackControl} to `false`.
	 *
	 * @param {AudioNode} audioNode - The audio node like an instance of `OscillatorNode`.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`audioNode`** `AudioNode`

**Returns:** `Audio`

**Calls:**

- `this.connect`

<details><summary>Code</summary>

```typescript
setNodeSource( audioNode ) {

		this.hasPlaybackControl = false;
		this.sourceType = 'audioNode';
		this.source = audioNode;
		this.connect();

		return this;

	}
```
</details>

### `Audio.setMediaElementSource(mediaElement: HTMLMediaElement): Audio`

**JSDoc:**
```typescript
/**
	 * Sets the given media element as the source of this instance.
	 *
	 * {@link Audio#sourceType} is set to `mediaNode` and {@link Audio#hasPlaybackControl} to `false`.
	 *
	 * @param {HTMLMediaElement} mediaElement - The media element.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`mediaElement`** `HTMLMediaElement`

**Returns:** `Audio`

**Calls:**

- `this.context.createMediaElementSource`
- `this.connect`

<details><summary>Code</summary>

```typescript
setMediaElementSource( mediaElement ) {

		this.hasPlaybackControl = false;
		this.sourceType = 'mediaNode';
		this.source = this.context.createMediaElementSource( mediaElement );
		this.connect();

		return this;

	}
```
</details>

### `Audio.setMediaStreamSource(mediaStream: MediaStream): Audio`

**JSDoc:**
```typescript
/**
	 * Sets the given media stream as the source of this instance.
	 *
	 * {@link Audio#sourceType} is set to `mediaStreamNode` and {@link Audio#hasPlaybackControl} to `false`.
	 *
	 * @param {MediaStream} mediaStream - The media stream.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`mediaStream`** `MediaStream`

**Returns:** `Audio`

**Calls:**

- `this.context.createMediaStreamSource`
- `this.connect`

<details><summary>Code</summary>

```typescript
setMediaStreamSource( mediaStream ) {

		this.hasPlaybackControl = false;
		this.sourceType = 'mediaStreamNode';
		this.source = this.context.createMediaStreamSource( mediaStream );
		this.connect();

		return this;

	}
```
</details>

### `Audio.setBuffer(audioBuffer: AudioBuffer): Audio`

**JSDoc:**
```typescript
/**
	 * Sets the given audio buffer as the source of this instance.
	 *
	 * {@link Audio#sourceType} is set to `buffer` and {@link Audio#hasPlaybackControl} to `true`.
	 *
	 * @param {AudioBuffer} audioBuffer - The audio buffer.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`audioBuffer`** `AudioBuffer`

**Returns:** `Audio`

**Calls:**

- `this.play`

<details><summary>Code</summary>

```typescript
setBuffer( audioBuffer ) {

		this.buffer = audioBuffer;
		this.sourceType = 'buffer';

		if ( this.autoplay ) this.play();

		return this;

	}
```
</details>

### `Audio.play(delay: number): Audio`

**JSDoc:**
```typescript
/**
	 * Starts the playback of the audio.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @param {number} [delay=0] - The delay, in seconds, at which the audio should start playing.
	 * @return {Audio|undefined} A reference to this instance.
	 */
```

**Parameters:**

- **`delay`** `number`

**Returns:** `Audio`

**Calls:**

- `console.warn`
- `this.context.createBufferSource`
- `this.onEnded.bind`
- `source.start`
- `this.setDetune`
- `this.setPlaybackRate`
- `this.connect`

<details><summary>Code</summary>

```typescript
play( delay = 0 ) {

		if ( this.isPlaying === true ) {

			console.warn( 'THREE.Audio: Audio is already playing.' );
			return;

		}

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this._startedAt = this.context.currentTime + delay;

		const source = this.context.createBufferSource();
		source.buffer = this.buffer;
		source.loop = this.loop;
		source.loopStart = this.loopStart;
		source.loopEnd = this.loopEnd;
		source.onended = this.onEnded.bind( this );
		source.start( this._startedAt, this._progress + this.offset, this.duration );

		this.isPlaying = true;

		this.source = source;

		this.setDetune( this.detune );
		this.setPlaybackRate( this.playbackRate );

		return this.connect();

	}
```
</details>

### `Audio.pause(): Audio`

**JSDoc:**
```typescript
/**
	 * Pauses the playback of the audio.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @return {Audio|undefined} A reference to this instance.
	 */
```

**Returns:** `Audio`

**Calls:**

- `console.warn`
- `Math.max`
- `this.source.stop`

**Internal Comments:**
```
// update current progress (x4)
// ensure _progress does not exceed duration with looped audios (x4)
```

<details><summary>Code</summary>

```typescript
pause() {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		if ( this.isPlaying === true ) {

			// update current progress

			this._progress += Math.max( this.context.currentTime - this._startedAt, 0 ) * this.playbackRate;

			if ( this.loop === true ) {

				// ensure _progress does not exceed duration with looped audios

				this._progress = this._progress % ( this.duration || this.buffer.duration );

			}

			this.source.stop();
			this.source.onended = null;

			this.isPlaying = false;

		}

		return this;

	}
```
</details>

### `Audio.stop(delay: number): Audio`

**JSDoc:**
```typescript
/**
	 * Stops the playback of the audio.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @param {number} [delay=0] - The delay, in seconds, at which the audio should stop playing.
	 * @return {Audio|undefined} A reference to this instance.
	 */
```

**Parameters:**

- **`delay`** `number`

**Returns:** `Audio`

**Calls:**

- `console.warn`
- `this.source.stop`

<details><summary>Code</summary>

```typescript
stop( delay = 0 ) {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this._progress = 0;

		if ( this.source !== null ) {

			this.source.stop( this.context.currentTime + delay );
			this.source.onended = null;

		}

		this.isPlaying = false;

		return this;

	}
```
</details>

### `Audio.connect(): Audio`

**JSDoc:**
```typescript
/**
	 * Connects to the audio source. This is used internally on
	 * initialisation and when setting / removing filters.
	 *
	 * @return {Audio} A reference to this instance.
	 */
```

**Returns:** `Audio`

**Calls:**

- `this.source.connect`
- `this.filters[ i - 1 ].connect`
- `this.filters[ this.filters.length - 1 ].connect`
- `this.getOutput`

<details><summary>Code</summary>

```typescript
connect() {

		if ( this.filters.length > 0 ) {

			this.source.connect( this.filters[ 0 ] );

			for ( let i = 1, l = this.filters.length; i < l; i ++ ) {

				this.filters[ i - 1 ].connect( this.filters[ i ] );

			}

			this.filters[ this.filters.length - 1 ].connect( this.getOutput() );

		} else {

			this.source.connect( this.getOutput() );

		}

		this._connected = true;

		return this;

	}
```
</details>

### `Audio.disconnect(): Audio`

**JSDoc:**
```typescript
/**
	 * Disconnects to the audio source. This is used internally on
	 * initialisation and when setting / removing filters.
	 *
	 * @return {Audio|undefined} A reference to this instance.
	 */
```

**Returns:** `Audio`

**Calls:**

- `this.source.disconnect`
- `this.filters[ i - 1 ].disconnect`
- `this.filters[ this.filters.length - 1 ].disconnect`
- `this.getOutput`

<details><summary>Code</summary>

```typescript
disconnect() {

		if ( this._connected === false ) {

			return;

		}

		if ( this.filters.length > 0 ) {

			this.source.disconnect( this.filters[ 0 ] );

			for ( let i = 1, l = this.filters.length; i < l; i ++ ) {

				this.filters[ i - 1 ].disconnect( this.filters[ i ] );

			}

			this.filters[ this.filters.length - 1 ].disconnect( this.getOutput() );

		} else {

			this.source.disconnect( this.getOutput() );

		}

		this._connected = false;

		return this;

	}
```
</details>

### `Audio.getFilters(): AudioNode[]`

**JSDoc:**
```typescript
/**
	 * Returns the current set filters.
	 *
	 * @return {Array<AudioNode>} The list of filters.
	 */
```

**Returns:** `AudioNode[]`

<details><summary>Code</summary>

```typescript
getFilters() {

		return this.filters;

	}
```
</details>

### `Audio.setFilters(value: AudioNode[]): Audio`

**JSDoc:**
```typescript
/**
	 * Sets an array of filters and connects them with the audio source.
	 *
	 * @param {Array<AudioNode>} [value] - A list of filters.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `AudioNode[]`

**Returns:** `Audio`

**Calls:**

- `this.disconnect`
- `value.slice`
- `this.connect`

<details><summary>Code</summary>

```typescript
setFilters( value ) {

		if ( ! value ) value = [];

		if ( this._connected === true ) {

			this.disconnect();
			this.filters = value.slice();
			this.connect();

		} else {

			this.filters = value.slice();

		}

		return this;

	}
```
</details>

### `Audio.setDetune(value: number): Audio`

**JSDoc:**
```typescript
/**
	 * Defines the detuning of oscillation in cents.
	 *
	 * @param {number} value - The detuning of oscillation in cents.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `Audio`

**Calls:**

- `this.source.detune.setTargetAtTime`

<details><summary>Code</summary>

```typescript
setDetune( value ) {

		this.detune = value;

		if ( this.isPlaying === true && this.source.detune !== undefined ) {

			this.source.detune.setTargetAtTime( this.detune, this.context.currentTime, 0.01 );

		}

		return this;

	}
```
</details>

### `Audio.getDetune(): number`

**JSDoc:**
```typescript
/**
	 * Returns the detuning of oscillation in cents.
	 *
	 * @return {number} The detuning of oscillation in cents.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getDetune() {

		return this.detune;

	}
```
</details>

### `Audio.getFilter(): AudioNode`

**JSDoc:**
```typescript
/**
	 * Returns the first filter in the list of filters.
	 *
	 * @return {AudioNode|undefined} The first filter in the list of filters.
	 */
```

**Returns:** `AudioNode`

**Calls:**

- `this.getFilters`

<details><summary>Code</summary>

```typescript
getFilter() {

		return this.getFilters()[ 0 ];

	}
```
</details>

### `Audio.setFilter(filter: AudioNode): Audio`

**JSDoc:**
```typescript
/**
	 * Applies a single filter node to the audio.
	 *
	 * @param {AudioNode} [filter] - The filter to set.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`filter`** `AudioNode`

**Returns:** `Audio`

**Calls:**

- `this.setFilters`

<details><summary>Code</summary>

```typescript
setFilter( filter ) {

		return this.setFilters( filter ? [ filter ] : [] );

	}
```
</details>

### `Audio.setPlaybackRate(value: number): Audio`

**JSDoc:**
```typescript
/**
	 * Sets the playback rate.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @param {number} [value] - The playback rate to set.
	 * @return {Audio|undefined} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `Audio`

**Calls:**

- `console.warn`
- `this.source.playbackRate.setTargetAtTime`

<details><summary>Code</summary>

```typescript
setPlaybackRate( value ) {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this.playbackRate = value;

		if ( this.isPlaying === true ) {

			this.source.playbackRate.setTargetAtTime( this.playbackRate, this.context.currentTime, 0.01 );

		}

		return this;

	}
```
</details>

### `Audio.getPlaybackRate(): number`

**JSDoc:**
```typescript
/**
	 * Returns the current playback rate.

	 * @return {number} The playback rate.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getPlaybackRate() {

		return this.playbackRate;

	}
```
</details>

### `Audio.onEnded(): void`

**JSDoc:**
```typescript
/**
	 * Automatically called when playback finished.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
onEnded() {

		this.isPlaying = false;
		this._progress = 0;

	}
```
</details>

### `Audio.getLoop(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns the loop flag.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @return {boolean} Whether the audio should loop or not.
	 */
```

**Returns:** `boolean`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getLoop() {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return false;

		}

		return this.loop;

	}
```
</details>

### `Audio.setLoop(value: boolean): Audio`

**JSDoc:**
```typescript
/**
	 * Sets the loop flag.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @param {boolean} value - Whether the audio should loop or not.
	 * @return {Audio|undefined} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `Audio`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
setLoop( value ) {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this.loop = value;

		if ( this.isPlaying === true ) {

			this.source.loop = this.loop;

		}

		return this;

	}
```
</details>

### `Audio.setLoopStart(value: number): Audio`

**JSDoc:**
```typescript
/**
	 * Sets the loop start value which defines where in the audio buffer the replay should
	 * start, in seconds.
	 *
	 * @param {number} value - The loop start value.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `Audio`

<details><summary>Code</summary>

```typescript
setLoopStart( value ) {

		this.loopStart = value;

		return this;

	}
```
</details>

### `Audio.setLoopEnd(value: number): Audio`

**JSDoc:**
```typescript
/**
	 * Sets the loop end value which defines where in the audio buffer the replay should
	 * stop, in seconds.
	 *
	 * @param {number} value - The loop end value.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `Audio`

<details><summary>Code</summary>

```typescript
setLoopEnd( value ) {

		this.loopEnd = value;

		return this;

	}
```
</details>

### `Audio.getVolume(): number`

**JSDoc:**
```typescript
/**
	 * Returns the volume.
	 *
	 * @return {number} The volume.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getVolume() {

		return this.gain.gain.value;

	}
```
</details>

### `Audio.setVolume(value: number): Audio`

**JSDoc:**
```typescript
/**
	 * Sets the volume.
	 *
	 * @param {number} value - The volume to set.
	 * @return {Audio} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `Audio`

**Calls:**

- `this.gain.gain.setTargetAtTime`

<details><summary>Code</summary>

```typescript
setVolume( value ) {

		this.gain.gain.setTargetAtTime( value, this.context.currentTime, 0.01 );

		return this;

	}
```
</details>

### `Audio.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `console.warn`
- `source.filters.slice`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.sourceType !== 'buffer' ) {

			console.warn( 'THREE.Audio: Audio source type cannot be copied.' );

			return this;

		}

		this.autoplay = source.autoplay;

		this.buffer = source.buffer;
		this.detune = source.detune;
		this.loop = source.loop;
		this.loopStart = source.loopStart;
		this.loopEnd = source.loopEnd;
		this.offset = source.offset;
		this.duration = source.duration;
		this.playbackRate = source.playbackRate;
		this.hasPlaybackControl = source.hasPlaybackControl;
		this.sourceType = source.sourceType;

		this.filters = source.filters.slice();

		return this;

	}
```
</details>

### `Audio.clone(recursive: any): any`

**Parameters:**

- **`recursive`** `any`

**Returns:** `any`

**Calls:**

- `new this.constructor( this.listener ).copy`

<details><summary>Code</summary>

```typescript
clone( recursive ) {

		return new this.constructor( this.listener ).copy( this, recursive );

	}
```
</details>


---

## Classes

### `Audio`

<details><summary>Class Code</summary>

```ts
class Audio extends Object3D {

	/**
	 * Constructs a new audio.
	 *
	 * @param {AudioListener} listener - The global audio listener.
	 */
	constructor( listener ) {

		super();

		this.type = 'Audio';

		/**
		 * The global audio listener.
		 *
		 * @type {AudioListener}
		 * @readonly
		 */
		this.listener = listener;

		/**
		 * The audio context.
		 *
		 * @type {AudioContext}
		 * @readonly
		 */
		this.context = listener.context;

		/**
		 * The gain node used for volume control.
		 *
		 * @type {GainNode}
		 * @readonly
		 */
		this.gain = this.context.createGain();
		this.gain.connect( listener.getInput() );

		/**
		 * Whether to start playback automatically or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.autoplay = false;

		/**
		 * A reference to an audio buffer.
		 *
		 * Defined via {@link Audio#setBuffer}.
		 *
		 * @type {?AudioBuffer}
		 * @default null
		 * @readonly
		 */
		this.buffer = null;

		/**
		 * Modify pitch, measured in cents. +/- 100 is a semitone.
		 * +/- 1200 is an octave.
		 *
		 * Defined via {@link Audio#setDetune}.
		 *
		 * @type {number}
		 * @default 0
		 * @readonly
		 */
		this.detune = 0;

		/**
		 * Whether the audio should loop or not.
		 *
		 * Defined via {@link Audio#setLoop}.
		 *
		 * @type {boolean}
		 * @default false
		 * @readonly
		 */
		this.loop = false;

		/**
		 * Defines where in the audio buffer the replay should
		 * start, in seconds.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.loopStart = 0;

		/**
		 * Defines where in the audio buffer the replay should
		 * stop, in seconds.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.loopEnd = 0;

		/**
		 * An offset to the time within the audio buffer the playback
		 * should begin, in seconds.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.offset = 0;

		/**
		 * Overrides the default duration of the audio.
		 *
		 * @type {undefined|number}
		 * @default undefined
		 */
		this.duration = undefined;

		/**
		 * The playback speed.
		 *
		 * Defined via {@link Audio#setPlaybackRate}.
		 *
		 * @type {number}
		 * @readonly
		 * @default 1
		 */
		this.playbackRate = 1;

		/**
		 * Indicates whether the audio is playing or not.
		 *
		 * This flag will be automatically set when using {@link Audio#play},
		 * {@link Audio#pause}, {@link Audio#stop}.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default false
		 */
		this.isPlaying = false;

		/**
		 * Indicates whether the audio playback can be controlled
		 * with method like {@link Audio#play} or {@link Audio#pause}.
		 *
		 * This flag will be automatically set when audio sources are
		 * defined.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.hasPlaybackControl = true;

		/**
		 * Holds a reference to the current audio source.
		 *
		 * The property is automatically by one of the `set*()` methods.
		 *
		 * @type {?AudioNode}
		 * @readonly
		 * @default null
		 */
		this.source = null;

		/**
		 * Defines the source type.
		 *
		 * The property is automatically by one of the `set*()` methods.
		 *
		 * @type {('empty'|'audioNode'|'mediaNode'|'mediaStreamNode'|'buffer')}
		 * @readonly
		 * @default 'empty'
		 */
		this.sourceType = 'empty';

		this._startedAt = 0;
		this._progress = 0;
		this._connected = false;

		/**
		 * Can be used to apply a variety of low-order filters to create
		 * more complex sound effects e.g. via `BiquadFilterNode`.
		 *
		 * The property is automatically set by {@link Audio#setFilters}.
		 *
		 * @type {Array<AudioNode>}
		 * @readonly
		 */
		this.filters = [];

	}

	/**
	 * Returns the output audio node.
	 *
	 * @return {GainNode} The output node.
	 */
	getOutput() {

		return this.gain;

	}

	/**
	 * Sets the given audio node as the source of this instance.
	 *
	 * {@link Audio#sourceType} is set to `audioNode` and {@link Audio#hasPlaybackControl} to `false`.
	 *
	 * @param {AudioNode} audioNode - The audio node like an instance of `OscillatorNode`.
	 * @return {Audio} A reference to this instance.
	 */
	setNodeSource( audioNode ) {

		this.hasPlaybackControl = false;
		this.sourceType = 'audioNode';
		this.source = audioNode;
		this.connect();

		return this;

	}

	/**
	 * Sets the given media element as the source of this instance.
	 *
	 * {@link Audio#sourceType} is set to `mediaNode` and {@link Audio#hasPlaybackControl} to `false`.
	 *
	 * @param {HTMLMediaElement} mediaElement - The media element.
	 * @return {Audio} A reference to this instance.
	 */
	setMediaElementSource( mediaElement ) {

		this.hasPlaybackControl = false;
		this.sourceType = 'mediaNode';
		this.source = this.context.createMediaElementSource( mediaElement );
		this.connect();

		return this;

	}

	/**
	 * Sets the given media stream as the source of this instance.
	 *
	 * {@link Audio#sourceType} is set to `mediaStreamNode` and {@link Audio#hasPlaybackControl} to `false`.
	 *
	 * @param {MediaStream} mediaStream - The media stream.
	 * @return {Audio} A reference to this instance.
	 */
	setMediaStreamSource( mediaStream ) {

		this.hasPlaybackControl = false;
		this.sourceType = 'mediaStreamNode';
		this.source = this.context.createMediaStreamSource( mediaStream );
		this.connect();

		return this;

	}

	/**
	 * Sets the given audio buffer as the source of this instance.
	 *
	 * {@link Audio#sourceType} is set to `buffer` and {@link Audio#hasPlaybackControl} to `true`.
	 *
	 * @param {AudioBuffer} audioBuffer - The audio buffer.
	 * @return {Audio} A reference to this instance.
	 */
	setBuffer( audioBuffer ) {

		this.buffer = audioBuffer;
		this.sourceType = 'buffer';

		if ( this.autoplay ) this.play();

		return this;

	}

	/**
	 * Starts the playback of the audio.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @param {number} [delay=0] - The delay, in seconds, at which the audio should start playing.
	 * @return {Audio|undefined} A reference to this instance.
	 */
	play( delay = 0 ) {

		if ( this.isPlaying === true ) {

			console.warn( 'THREE.Audio: Audio is already playing.' );
			return;

		}

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this._startedAt = this.context.currentTime + delay;

		const source = this.context.createBufferSource();
		source.buffer = this.buffer;
		source.loop = this.loop;
		source.loopStart = this.loopStart;
		source.loopEnd = this.loopEnd;
		source.onended = this.onEnded.bind( this );
		source.start( this._startedAt, this._progress + this.offset, this.duration );

		this.isPlaying = true;

		this.source = source;

		this.setDetune( this.detune );
		this.setPlaybackRate( this.playbackRate );

		return this.connect();

	}

	/**
	 * Pauses the playback of the audio.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @return {Audio|undefined} A reference to this instance.
	 */
	pause() {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		if ( this.isPlaying === true ) {

			// update current progress

			this._progress += Math.max( this.context.currentTime - this._startedAt, 0 ) * this.playbackRate;

			if ( this.loop === true ) {

				// ensure _progress does not exceed duration with looped audios

				this._progress = this._progress % ( this.duration || this.buffer.duration );

			}

			this.source.stop();
			this.source.onended = null;

			this.isPlaying = false;

		}

		return this;

	}

	/**
	 * Stops the playback of the audio.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @param {number} [delay=0] - The delay, in seconds, at which the audio should stop playing.
	 * @return {Audio|undefined} A reference to this instance.
	 */
	stop( delay = 0 ) {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this._progress = 0;

		if ( this.source !== null ) {

			this.source.stop( this.context.currentTime + delay );
			this.source.onended = null;

		}

		this.isPlaying = false;

		return this;

	}

	/**
	 * Connects to the audio source. This is used internally on
	 * initialisation and when setting / removing filters.
	 *
	 * @return {Audio} A reference to this instance.
	 */
	connect() {

		if ( this.filters.length > 0 ) {

			this.source.connect( this.filters[ 0 ] );

			for ( let i = 1, l = this.filters.length; i < l; i ++ ) {

				this.filters[ i - 1 ].connect( this.filters[ i ] );

			}

			this.filters[ this.filters.length - 1 ].connect( this.getOutput() );

		} else {

			this.source.connect( this.getOutput() );

		}

		this._connected = true;

		return this;

	}

	/**
	 * Disconnects to the audio source. This is used internally on
	 * initialisation and when setting / removing filters.
	 *
	 * @return {Audio|undefined} A reference to this instance.
	 */
	disconnect() {

		if ( this._connected === false ) {

			return;

		}

		if ( this.filters.length > 0 ) {

			this.source.disconnect( this.filters[ 0 ] );

			for ( let i = 1, l = this.filters.length; i < l; i ++ ) {

				this.filters[ i - 1 ].disconnect( this.filters[ i ] );

			}

			this.filters[ this.filters.length - 1 ].disconnect( this.getOutput() );

		} else {

			this.source.disconnect( this.getOutput() );

		}

		this._connected = false;

		return this;

	}

	/**
	 * Returns the current set filters.
	 *
	 * @return {Array<AudioNode>} The list of filters.
	 */
	getFilters() {

		return this.filters;

	}

	/**
	 * Sets an array of filters and connects them with the audio source.
	 *
	 * @param {Array<AudioNode>} [value] - A list of filters.
	 * @return {Audio} A reference to this instance.
	 */
	setFilters( value ) {

		if ( ! value ) value = [];

		if ( this._connected === true ) {

			this.disconnect();
			this.filters = value.slice();
			this.connect();

		} else {

			this.filters = value.slice();

		}

		return this;

	}

	/**
	 * Defines the detuning of oscillation in cents.
	 *
	 * @param {number} value - The detuning of oscillation in cents.
	 * @return {Audio} A reference to this instance.
	 */
	setDetune( value ) {

		this.detune = value;

		if ( this.isPlaying === true && this.source.detune !== undefined ) {

			this.source.detune.setTargetAtTime( this.detune, this.context.currentTime, 0.01 );

		}

		return this;

	}

	/**
	 * Returns the detuning of oscillation in cents.
	 *
	 * @return {number} The detuning of oscillation in cents.
	 */
	getDetune() {

		return this.detune;

	}

	/**
	 * Returns the first filter in the list of filters.
	 *
	 * @return {AudioNode|undefined} The first filter in the list of filters.
	 */
	getFilter() {

		return this.getFilters()[ 0 ];

	}

	/**
	 * Applies a single filter node to the audio.
	 *
	 * @param {AudioNode} [filter] - The filter to set.
	 * @return {Audio} A reference to this instance.
	 */
	setFilter( filter ) {

		return this.setFilters( filter ? [ filter ] : [] );

	}

	/**
	 * Sets the playback rate.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @param {number} [value] - The playback rate to set.
	 * @return {Audio|undefined} A reference to this instance.
	 */
	setPlaybackRate( value ) {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this.playbackRate = value;

		if ( this.isPlaying === true ) {

			this.source.playbackRate.setTargetAtTime( this.playbackRate, this.context.currentTime, 0.01 );

		}

		return this;

	}

	/**
	 * Returns the current playback rate.

	 * @return {number} The playback rate.
	 */
	getPlaybackRate() {

		return this.playbackRate;

	}

	/**
	 * Automatically called when playback finished.
	 */
	onEnded() {

		this.isPlaying = false;
		this._progress = 0;

	}

	/**
	 * Returns the loop flag.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @return {boolean} Whether the audio should loop or not.
	 */
	getLoop() {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return false;

		}

		return this.loop;

	}

	/**
	 * Sets the loop flag.
	 *
	 * Can only be used with compatible audio sources that allow playback control.
	 *
	 * @param {boolean} value - Whether the audio should loop or not.
	 * @return {Audio|undefined} A reference to this instance.
	 */
	setLoop( value ) {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this.loop = value;

		if ( this.isPlaying === true ) {

			this.source.loop = this.loop;

		}

		return this;

	}

	/**
	 * Sets the loop start value which defines where in the audio buffer the replay should
	 * start, in seconds.
	 *
	 * @param {number} value - The loop start value.
	 * @return {Audio} A reference to this instance.
	 */
	setLoopStart( value ) {

		this.loopStart = value;

		return this;

	}

	/**
	 * Sets the loop end value which defines where in the audio buffer the replay should
	 * stop, in seconds.
	 *
	 * @param {number} value - The loop end value.
	 * @return {Audio} A reference to this instance.
	 */
	setLoopEnd( value ) {

		this.loopEnd = value;

		return this;

	}

	/**
	 * Returns the volume.
	 *
	 * @return {number} The volume.
	 */
	getVolume() {

		return this.gain.gain.value;

	}

	/**
	 * Sets the volume.
	 *
	 * @param {number} value - The volume to set.
	 * @return {Audio} A reference to this instance.
	 */
	setVolume( value ) {

		this.gain.gain.setTargetAtTime( value, this.context.currentTime, 0.01 );

		return this;

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.sourceType !== 'buffer' ) {

			console.warn( 'THREE.Audio: Audio source type cannot be copied.' );

			return this;

		}

		this.autoplay = source.autoplay;

		this.buffer = source.buffer;
		this.detune = source.detune;
		this.loop = source.loop;
		this.loopStart = source.loopStart;
		this.loopEnd = source.loopEnd;
		this.offset = source.offset;
		this.duration = source.duration;
		this.playbackRate = source.playbackRate;
		this.hasPlaybackControl = source.hasPlaybackControl;
		this.sourceType = source.sourceType;

		this.filters = source.filters.slice();

		return this;

	}

	clone( recursive ) {

		return new this.constructor( this.listener ).copy( this, recursive );

	}

}
```
</details>

#### Methods

##### `getOutput(): GainNode`

<details><summary>Code</summary>

```ts
getOutput() {

		return this.gain;

	}
```
</details>

##### `setNodeSource(audioNode: AudioNode): Audio`

<details><summary>Code</summary>

```ts
setNodeSource( audioNode ) {

		this.hasPlaybackControl = false;
		this.sourceType = 'audioNode';
		this.source = audioNode;
		this.connect();

		return this;

	}
```
</details>

##### `setMediaElementSource(mediaElement: HTMLMediaElement): Audio`

<details><summary>Code</summary>

```ts
setMediaElementSource( mediaElement ) {

		this.hasPlaybackControl = false;
		this.sourceType = 'mediaNode';
		this.source = this.context.createMediaElementSource( mediaElement );
		this.connect();

		return this;

	}
```
</details>

##### `setMediaStreamSource(mediaStream: MediaStream): Audio`

<details><summary>Code</summary>

```ts
setMediaStreamSource( mediaStream ) {

		this.hasPlaybackControl = false;
		this.sourceType = 'mediaStreamNode';
		this.source = this.context.createMediaStreamSource( mediaStream );
		this.connect();

		return this;

	}
```
</details>

##### `setBuffer(audioBuffer: AudioBuffer): Audio`

<details><summary>Code</summary>

```ts
setBuffer( audioBuffer ) {

		this.buffer = audioBuffer;
		this.sourceType = 'buffer';

		if ( this.autoplay ) this.play();

		return this;

	}
```
</details>

##### `play(delay: number): Audio`

<details><summary>Code</summary>

```ts
play( delay = 0 ) {

		if ( this.isPlaying === true ) {

			console.warn( 'THREE.Audio: Audio is already playing.' );
			return;

		}

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this._startedAt = this.context.currentTime + delay;

		const source = this.context.createBufferSource();
		source.buffer = this.buffer;
		source.loop = this.loop;
		source.loopStart = this.loopStart;
		source.loopEnd = this.loopEnd;
		source.onended = this.onEnded.bind( this );
		source.start( this._startedAt, this._progress + this.offset, this.duration );

		this.isPlaying = true;

		this.source = source;

		this.setDetune( this.detune );
		this.setPlaybackRate( this.playbackRate );

		return this.connect();

	}
```
</details>

##### `pause(): Audio`

<details><summary>Code</summary>

```ts
pause() {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		if ( this.isPlaying === true ) {

			// update current progress

			this._progress += Math.max( this.context.currentTime - this._startedAt, 0 ) * this.playbackRate;

			if ( this.loop === true ) {

				// ensure _progress does not exceed duration with looped audios

				this._progress = this._progress % ( this.duration || this.buffer.duration );

			}

			this.source.stop();
			this.source.onended = null;

			this.isPlaying = false;

		}

		return this;

	}
```
</details>

##### `stop(delay: number): Audio`

<details><summary>Code</summary>

```ts
stop( delay = 0 ) {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this._progress = 0;

		if ( this.source !== null ) {

			this.source.stop( this.context.currentTime + delay );
			this.source.onended = null;

		}

		this.isPlaying = false;

		return this;

	}
```
</details>

##### `connect(): Audio`

<details><summary>Code</summary>

```ts
connect() {

		if ( this.filters.length > 0 ) {

			this.source.connect( this.filters[ 0 ] );

			for ( let i = 1, l = this.filters.length; i < l; i ++ ) {

				this.filters[ i - 1 ].connect( this.filters[ i ] );

			}

			this.filters[ this.filters.length - 1 ].connect( this.getOutput() );

		} else {

			this.source.connect( this.getOutput() );

		}

		this._connected = true;

		return this;

	}
```
</details>

##### `disconnect(): Audio`

<details><summary>Code</summary>

```ts
disconnect() {

		if ( this._connected === false ) {

			return;

		}

		if ( this.filters.length > 0 ) {

			this.source.disconnect( this.filters[ 0 ] );

			for ( let i = 1, l = this.filters.length; i < l; i ++ ) {

				this.filters[ i - 1 ].disconnect( this.filters[ i ] );

			}

			this.filters[ this.filters.length - 1 ].disconnect( this.getOutput() );

		} else {

			this.source.disconnect( this.getOutput() );

		}

		this._connected = false;

		return this;

	}
```
</details>

##### `getFilters(): AudioNode[]`

<details><summary>Code</summary>

```ts
getFilters() {

		return this.filters;

	}
```
</details>

##### `setFilters(value: AudioNode[]): Audio`

<details><summary>Code</summary>

```ts
setFilters( value ) {

		if ( ! value ) value = [];

		if ( this._connected === true ) {

			this.disconnect();
			this.filters = value.slice();
			this.connect();

		} else {

			this.filters = value.slice();

		}

		return this;

	}
```
</details>

##### `setDetune(value: number): Audio`

<details><summary>Code</summary>

```ts
setDetune( value ) {

		this.detune = value;

		if ( this.isPlaying === true && this.source.detune !== undefined ) {

			this.source.detune.setTargetAtTime( this.detune, this.context.currentTime, 0.01 );

		}

		return this;

	}
```
</details>

##### `getDetune(): number`

<details><summary>Code</summary>

```ts
getDetune() {

		return this.detune;

	}
```
</details>

##### `getFilter(): AudioNode`

<details><summary>Code</summary>

```ts
getFilter() {

		return this.getFilters()[ 0 ];

	}
```
</details>

##### `setFilter(filter: AudioNode): Audio`

<details><summary>Code</summary>

```ts
setFilter( filter ) {

		return this.setFilters( filter ? [ filter ] : [] );

	}
```
</details>

##### `setPlaybackRate(value: number): Audio`

<details><summary>Code</summary>

```ts
setPlaybackRate( value ) {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this.playbackRate = value;

		if ( this.isPlaying === true ) {

			this.source.playbackRate.setTargetAtTime( this.playbackRate, this.context.currentTime, 0.01 );

		}

		return this;

	}
```
</details>

##### `getPlaybackRate(): number`

<details><summary>Code</summary>

```ts
getPlaybackRate() {

		return this.playbackRate;

	}
```
</details>

##### `onEnded(): void`

<details><summary>Code</summary>

```ts
onEnded() {

		this.isPlaying = false;
		this._progress = 0;

	}
```
</details>

##### `getLoop(): boolean`

<details><summary>Code</summary>

```ts
getLoop() {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return false;

		}

		return this.loop;

	}
```
</details>

##### `setLoop(value: boolean): Audio`

<details><summary>Code</summary>

```ts
setLoop( value ) {

		if ( this.hasPlaybackControl === false ) {

			console.warn( 'THREE.Audio: this Audio has no playback control.' );
			return;

		}

		this.loop = value;

		if ( this.isPlaying === true ) {

			this.source.loop = this.loop;

		}

		return this;

	}
```
</details>

##### `setLoopStart(value: number): Audio`

<details><summary>Code</summary>

```ts
setLoopStart( value ) {

		this.loopStart = value;

		return this;

	}
```
</details>

##### `setLoopEnd(value: number): Audio`

<details><summary>Code</summary>

```ts
setLoopEnd( value ) {

		this.loopEnd = value;

		return this;

	}
```
</details>

##### `getVolume(): number`

<details><summary>Code</summary>

```ts
getVolume() {

		return this.gain.gain.value;

	}
```
</details>

##### `setVolume(value: number): Audio`

<details><summary>Code</summary>

```ts
setVolume( value ) {

		this.gain.gain.setTargetAtTime( value, this.context.currentTime, 0.01 );

		return this;

	}
```
</details>

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.sourceType !== 'buffer' ) {

			console.warn( 'THREE.Audio: Audio source type cannot be copied.' );

			return this;

		}

		this.autoplay = source.autoplay;

		this.buffer = source.buffer;
		this.detune = source.detune;
		this.loop = source.loop;
		this.loopStart = source.loopStart;
		this.loopEnd = source.loopEnd;
		this.offset = source.offset;
		this.duration = source.duration;
		this.playbackRate = source.playbackRate;
		this.hasPlaybackControl = source.hasPlaybackControl;
		this.sourceType = source.sourceType;

		this.filters = source.filters.slice();

		return this;

	}
```
</details>

##### `clone(recursive: any): any`

<details><summary>Code</summary>

```ts
clone( recursive ) {

		return new this.constructor( this.listener ).copy( this, recursive );

	}
```
</details>


---