[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MDDLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/MDDLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationClip` | `three` |
| `BufferAttribute` | `three` |
| `FileLoader` | `three` |
| `Loader` | `three` |
| `NumberKeyframeTrack` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `view` | `DataView<ArrayBuffer>` | let/var | `new DataView( data )` | ✗ |
| `offset` | `number` | let/var | `8` | ✗ |
| `times` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( totalFrames )` | ✗ |
| `track` | `any` | let/var | `new NumberKeyframeTrack( '.morphTargetInfluences', times, values )` | ✗ |
| `clip` | `any` | let/var | `new AnimationClip( 'default', times[ times.length - 1 ], [ track ] )` | ✗ |
| `morphTargets` | `any[]` | let/var | `[]` | ✗ |
| `morphTarget` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( totalPoints * 3 )` | ✗ |
| `stride` | `number` | let/var | `( j * 3 )` | ✗ |
| `attribute` | `any` | let/var | `new BufferAttribute( morphTarget, 3 )` | ✗ |


---

## Functions

### `MDDLoader.load(url: string, onLoad: (arg0: { clip: AnimationClip; morphTargets: BufferAttribute[]; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded MDD asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({clip:AnimationClip, morphTargets:Array<BufferAttribute>})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { clip: AnimationClip; morphTargets: BufferAttribute[]; }) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setResponseType`
- `loader.load`
- `onLoad`
- `scope.parse`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.load( url, function ( data ) {

			onLoad( scope.parse( data ) );

		}, onProgress, onError );

	}
```
</details>

### `MDDLoader.parse(data: ArrayBuffer): { clip: AnimationClip; morphTargets: BufferAttribute[]; }`

**JSDoc:**
```typescript
/**
	 * Parses the given MDD data and returns an object holding the animation clip and the respective
	 * morph targets.
	 *
	 * @param {ArrayBuffer} data - The raw XYZ data as an array buffer.
	 * @return {{clip:AnimationClip, morphTargets:Array<BufferAttribute>}} The result object.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`

**Returns:** `{ clip: AnimationClip; morphTargets: BufferAttribute[]; }`

**Calls:**

- `view.getUint32`
- `new Float32Array( totalFrames * totalFrames ).fill`
- `view.getFloat32`
- `morphTargets.push`

**Internal Comments:**
```
// animation clip (x2)
// morph targets (x2)
```

<details><summary>Code</summary>

```typescript
parse( data ) {

		const view = new DataView( data );

		const totalFrames = view.getUint32( 0 );
		const totalPoints = view.getUint32( 4 );

		let offset = 8;

		// animation clip

		const times = new Float32Array( totalFrames );
		const values = new Float32Array( totalFrames * totalFrames ).fill( 0 );

		for ( let i = 0; i < totalFrames; i ++ ) {

			times[ i ] = view.getFloat32( offset ); offset += 4;
			values[ ( totalFrames * i ) + i ] = 1;

		}

		const track = new NumberKeyframeTrack( '.morphTargetInfluences', times, values );
		const clip = new AnimationClip( 'default', times[ times.length - 1 ], [ track ] );

		// morph targets

		const morphTargets = [];

		for ( let i = 0; i < totalFrames; i ++ ) {

			const morphTarget = new Float32Array( totalPoints * 3 );

			for ( let j = 0; j < totalPoints; j ++ ) {

				const stride = ( j * 3 );

				morphTarget[ stride + 0 ] = view.getFloat32( offset ); offset += 4; // x
				morphTarget[ stride + 1 ] = view.getFloat32( offset ); offset += 4; // y
				morphTarget[ stride + 2 ] = view.getFloat32( offset ); offset += 4; // z

			}

			const attribute = new BufferAttribute( morphTarget, 3 );
			attribute.name = 'morph_' + i;

			morphTargets.push( attribute );

		}

		return {
			morphTargets: morphTargets,
			clip: clip
		};

	}
```
</details>


---

## Classes

### `MDDLoader`

<details><summary>Class Code</summary>

```ts
class MDDLoader extends Loader {

	/**
	 * Constructs a new MDD loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded MDD asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({clip:AnimationClip, morphTargets:Array<BufferAttribute>})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.load( url, function ( data ) {

			onLoad( scope.parse( data ) );

		}, onProgress, onError );

	}

	/**
	 * Parses the given MDD data and returns an object holding the animation clip and the respective
	 * morph targets.
	 *
	 * @param {ArrayBuffer} data - The raw XYZ data as an array buffer.
	 * @return {{clip:AnimationClip, morphTargets:Array<BufferAttribute>}} The result object.
	 */
	parse( data ) {

		const view = new DataView( data );

		const totalFrames = view.getUint32( 0 );
		const totalPoints = view.getUint32( 4 );

		let offset = 8;

		// animation clip

		const times = new Float32Array( totalFrames );
		const values = new Float32Array( totalFrames * totalFrames ).fill( 0 );

		for ( let i = 0; i < totalFrames; i ++ ) {

			times[ i ] = view.getFloat32( offset ); offset += 4;
			values[ ( totalFrames * i ) + i ] = 1;

		}

		const track = new NumberKeyframeTrack( '.morphTargetInfluences', times, values );
		const clip = new AnimationClip( 'default', times[ times.length - 1 ], [ track ] );

		// morph targets

		const morphTargets = [];

		for ( let i = 0; i < totalFrames; i ++ ) {

			const morphTarget = new Float32Array( totalPoints * 3 );

			for ( let j = 0; j < totalPoints; j ++ ) {

				const stride = ( j * 3 );

				morphTarget[ stride + 0 ] = view.getFloat32( offset ); offset += 4; // x
				morphTarget[ stride + 1 ] = view.getFloat32( offset ); offset += 4; // y
				morphTarget[ stride + 2 ] = view.getFloat32( offset ); offset += 4; // z

			}

			const attribute = new BufferAttribute( morphTarget, 3 );
			attribute.name = 'morph_' + i;

			morphTargets.push( attribute );

		}

		return {
			morphTargets: morphTargets,
			clip: clip
		};

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: { clip: AnimationClip; morphTargets: BufferAttribute[]; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.load( url, function ( data ) {

			onLoad( scope.parse( data ) );

		}, onProgress, onError );

	}
```
</details>

##### `parse(data: ArrayBuffer): { clip: AnimationClip; morphTargets: BufferAttribute[]; }`

<details><summary>Code</summary>

```ts
parse( data ) {

		const view = new DataView( data );

		const totalFrames = view.getUint32( 0 );
		const totalPoints = view.getUint32( 4 );

		let offset = 8;

		// animation clip

		const times = new Float32Array( totalFrames );
		const values = new Float32Array( totalFrames * totalFrames ).fill( 0 );

		for ( let i = 0; i < totalFrames; i ++ ) {

			times[ i ] = view.getFloat32( offset ); offset += 4;
			values[ ( totalFrames * i ) + i ] = 1;

		}

		const track = new NumberKeyframeTrack( '.morphTargetInfluences', times, values );
		const clip = new AnimationClip( 'default', times[ times.length - 1 ], [ track ] );

		// morph targets

		const morphTargets = [];

		for ( let i = 0; i < totalFrames; i ++ ) {

			const morphTarget = new Float32Array( totalPoints * 3 );

			for ( let j = 0; j < totalPoints; j ++ ) {

				const stride = ( j * 3 );

				morphTarget[ stride + 0 ] = view.getFloat32( offset ); offset += 4; // x
				morphTarget[ stride + 1 ] = view.getFloat32( offset ); offset += 4; // y
				morphTarget[ stride + 2 ] = view.getFloat32( offset ); offset += 4; // z

			}

			const attribute = new BufferAttribute( morphTarget, 3 );
			attribute.name = 'morph_' + i;

			morphTargets.push( attribute );

		}

		return {
			morphTargets: morphTargets,
			clip: clip
		};

	}
```
</details>


---