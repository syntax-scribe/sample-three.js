[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Source.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/textures/Source.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ImageUtils` | `../extras/ImageUtils.js` |
| `generateUUID` | `../math/MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_sourceId` | `number` | let/var | `0` | ✗ |
| `data` | `any` | let/var | `this.data` | ✗ |
| `isRootObject` | `boolean` | let/var | `( meta === undefined \|\| typeof meta === 'string' )` | ✗ |
| `output` | `{ uuid: string; url: string; }` | let/var | `{ uuid: this.uuid, url: '' }` | ✗ |
| `data` | `any` | let/var | `this.data` | ✗ |
| `url` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `Source.getSize(target: any): any`

**JSDoc:**
```typescript
/**
	 * Returns the dimensions of the source into the given target vector.
	 *
	 * @param {(Vector2|Vector3)} target - The target object the result is written into.
	 * @return {(Vector2|Vector3)} The dimensions of the source.
	 */
```

**Parameters:**

- **`target`** `any`

**Returns:** `any`

**Calls:**

- `target.set`

<details><summary>Code</summary>

```typescript
getSize( target ) {

		const data = this.data;

		if ( data instanceof HTMLVideoElement ) {

			target.set( data.videoWidth, data.videoHeight, 0 );

		} else if ( data instanceof VideoFrame ) {

			target.set( data.displayHeight, data.displayWidth, 0 );

		} else if ( data !== null ) {

			target.set( data.width, data.height, data.depth || 0 );

		} else {

			target.set( 0, 0, 0 );

		}

		return target;

	}
```
</details>

### `Source.toJSON(meta: any): any`

**JSDoc:**
```typescript
/**
	 * Serializes the source into JSON.
	 *
	 * @param {?(Object|string)} meta - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized source.
	 * @see {@link ObjectLoader#parse}
	 */
```

**Parameters:**

- **`meta`** `any`

**Returns:** `any`

**Calls:**

- `Array.isArray`
- `url.push`
- `serializeImage`

**Internal Comments:**
```
// cube texture (x3)
// texture (x3)
```

<details><summary>Code</summary>

```typescript
toJSON( meta ) {

		const isRootObject = ( meta === undefined || typeof meta === 'string' );

		if ( ! isRootObject && meta.images[ this.uuid ] !== undefined ) {

			return meta.images[ this.uuid ];

		}

		const output = {
			uuid: this.uuid,
			url: ''
		};

		const data = this.data;

		if ( data !== null ) {

			let url;

			if ( Array.isArray( data ) ) {

				// cube texture

				url = [];

				for ( let i = 0, l = data.length; i < l; i ++ ) {

					if ( data[ i ].isDataTexture ) {

						url.push( serializeImage( data[ i ].image ) );

					} else {

						url.push( serializeImage( data[ i ] ) );

					}

				}

			} else {

				// texture

				url = serializeImage( data );

			}

			output.url = url;

		}

		if ( ! isRootObject ) {

			meta.images[ this.uuid ] = output;

		}

		return output;

	}
```
</details>

### `serializeImage(image: any): string | { data: any[]; width: any; height: any; type: any; } | { data?: undefined; width?: undefined; height?: undefined; type?: undefined; }`

**Parameters:**

- **`image`** `any`

**Returns:** `string | { data: any[]; width: any; height: any; type: any; } | { data?: undefined; width?: undefined; height?: undefined; type?: undefined; }`

**Calls:**

- `ImageUtils.getDataURL`
- `Array.from`
- `console.warn`

**Internal Comments:**
```
// default images
// images of DataTexture
```

<details><summary>Code</summary>

```typescript
function serializeImage( image ) {

	if ( ( typeof HTMLImageElement !== 'undefined' && image instanceof HTMLImageElement ) ||
		( typeof HTMLCanvasElement !== 'undefined' && image instanceof HTMLCanvasElement ) ||
		( typeof ImageBitmap !== 'undefined' && image instanceof ImageBitmap ) ) {

		// default images

		return ImageUtils.getDataURL( image );

	} else {

		if ( image.data ) {

			// images of DataTexture

			return {
				data: Array.from( image.data ),
				width: image.width,
				height: image.height,
				type: image.data.constructor.name
			};

		} else {

			console.warn( 'THREE.Texture: Unable to serialize Texture.' );
			return {};

		}

	}

}
```
</details>


---

## Classes

### `Source`

<details><summary>Class Code</summary>

```ts
class Source {

	/**
	 * Constructs a new video texture.
	 *
	 * @param {any} [data=null] - The data definition of a texture.
	 */
	constructor( data = null ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSource = true;

		/**
		 * The ID of the source.
		 *
		 * @name Source#id
		 * @type {number}
		 * @readonly
		 */
		Object.defineProperty( this, 'id', { value: _sourceId ++ } );

		/**
		 * The UUID of the source.
		 *
		 * @type {string}
		 * @readonly
		 */
		this.uuid = generateUUID();

		/**
		 * The data definition of a texture.
		 *
		 * @type {any}
		 */
		this.data = data;

		/**
		 * This property is only relevant when {@link Source#needsUpdate} is set to `true` and
		 * provides more control on how texture data should be processed. When `dataReady` is set
		 * to `false`, the engine performs the memory allocation (if necessary) but does not transfer
		 * the data into the GPU memory.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.dataReady = true;

		/**
		 * This starts at `0` and counts how many times {@link Source#needsUpdate} is set to `true`.
		 *
		 * @type {number}
		 * @readonly
		 * @default 0
		 */
		this.version = 0;

	}

	/**
	 * Returns the dimensions of the source into the given target vector.
	 *
	 * @param {(Vector2|Vector3)} target - The target object the result is written into.
	 * @return {(Vector2|Vector3)} The dimensions of the source.
	 */
	getSize( target ) {

		const data = this.data;

		if ( data instanceof HTMLVideoElement ) {

			target.set( data.videoWidth, data.videoHeight, 0 );

		} else if ( data instanceof VideoFrame ) {

			target.set( data.displayHeight, data.displayWidth, 0 );

		} else if ( data !== null ) {

			target.set( data.width, data.height, data.depth || 0 );

		} else {

			target.set( 0, 0, 0 );

		}

		return target;

	}

	/**
	 * When the property is set to `true`, the engine allocates the memory
	 * for the texture (if necessary) and triggers the actual texture upload
	 * to the GPU next time the source is used.
	 *
	 * @type {boolean}
	 * @default false
	 * @param {boolean} value
	 */
	set needsUpdate( value ) {

		if ( value === true ) this.version ++;

	}

	/**
	 * Serializes the source into JSON.
	 *
	 * @param {?(Object|string)} meta - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized source.
	 * @see {@link ObjectLoader#parse}
	 */
	toJSON( meta ) {

		const isRootObject = ( meta === undefined || typeof meta === 'string' );

		if ( ! isRootObject && meta.images[ this.uuid ] !== undefined ) {

			return meta.images[ this.uuid ];

		}

		const output = {
			uuid: this.uuid,
			url: ''
		};

		const data = this.data;

		if ( data !== null ) {

			let url;

			if ( Array.isArray( data ) ) {

				// cube texture

				url = [];

				for ( let i = 0, l = data.length; i < l; i ++ ) {

					if ( data[ i ].isDataTexture ) {

						url.push( serializeImage( data[ i ].image ) );

					} else {

						url.push( serializeImage( data[ i ] ) );

					}

				}

			} else {

				// texture

				url = serializeImage( data );

			}

			output.url = url;

		}

		if ( ! isRootObject ) {

			meta.images[ this.uuid ] = output;

		}

		return output;

	}

}
```
</details>

#### Methods

##### `getSize(target: any): any`

<details><summary>Code</summary>

```ts
getSize( target ) {

		const data = this.data;

		if ( data instanceof HTMLVideoElement ) {

			target.set( data.videoWidth, data.videoHeight, 0 );

		} else if ( data instanceof VideoFrame ) {

			target.set( data.displayHeight, data.displayWidth, 0 );

		} else if ( data !== null ) {

			target.set( data.width, data.height, data.depth || 0 );

		} else {

			target.set( 0, 0, 0 );

		}

		return target;

	}
```
</details>

##### `toJSON(meta: any): any`

<details><summary>Code</summary>

```ts
toJSON( meta ) {

		const isRootObject = ( meta === undefined || typeof meta === 'string' );

		if ( ! isRootObject && meta.images[ this.uuid ] !== undefined ) {

			return meta.images[ this.uuid ];

		}

		const output = {
			uuid: this.uuid,
			url: ''
		};

		const data = this.data;

		if ( data !== null ) {

			let url;

			if ( Array.isArray( data ) ) {

				// cube texture

				url = [];

				for ( let i = 0, l = data.length; i < l; i ++ ) {

					if ( data[ i ].isDataTexture ) {

						url.push( serializeImage( data[ i ].image ) );

					} else {

						url.push( serializeImage( data[ i ] ) );

					}

				}

			} else {

				// texture

				url = serializeImage( data );

			}

			output.url = url;

		}

		if ( ! isRootObject ) {

			meta.images[ this.uuid ] = output;

		}

		return output;

	}
```
</details>


---