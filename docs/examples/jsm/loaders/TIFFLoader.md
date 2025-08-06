[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TIFFLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/TIFFLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataTextureLoader` | `three` |
| `LinearFilter` | `three` |
| `LinearMipmapLinearFilter` | `three` |
| `UTIF` | `../libs/utif.module.js` |


---

## Functions

### `TIFFLoader.parse(buffer: ArrayBuffer): DataTextureLoader`

**JSDoc:**
```typescript
/**
	 * Parses the given TIFF texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @return {DataTextureLoader~TexData} An object representing the parsed texture data.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`

**Returns:** `DataTextureLoader`

**Calls:**

- `UTIF.decode`
- `UTIF.decodeImage`
- `UTIF.toRGBA8`

<details><summary>Code</summary>

```typescript
parse( buffer ) {

		const ifds = UTIF.decode( buffer );
		UTIF.decodeImage( buffer, ifds[ 0 ] );
		const rgba = UTIF.toRGBA8( ifds[ 0 ] );

		return {
			width: ifds[ 0 ].width,
			height: ifds[ 0 ].height,
			data: rgba,
			flipY: true,
			magFilter: LinearFilter,
			minFilter: LinearMipmapLinearFilter
		};

	}
```
</details>


---

## Classes

### `TIFFLoader`

<details><summary>Class Code</summary>

```ts
class TIFFLoader extends DataTextureLoader {

	/**
	 * Constructs a new TIFF loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Parses the given TIFF texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @return {DataTextureLoader~TexData} An object representing the parsed texture data.
	 */
	parse( buffer ) {

		const ifds = UTIF.decode( buffer );
		UTIF.decodeImage( buffer, ifds[ 0 ] );
		const rgba = UTIF.toRGBA8( ifds[ 0 ] );

		return {
			width: ifds[ 0 ].width,
			height: ifds[ 0 ].height,
			data: rgba,
			flipY: true,
			magFilter: LinearFilter,
			minFilter: LinearMipmapLinearFilter
		};

	}

}
```
</details>

#### Methods

##### `parse(buffer: ArrayBuffer): DataTextureLoader`

<details><summary>Code</summary>

```ts
parse( buffer ) {

		const ifds = UTIF.decode( buffer );
		UTIF.decodeImage( buffer, ifds[ 0 ] );
		const rgba = UTIF.toRGBA8( ifds[ 0 ] );

		return {
			width: ifds[ 0 ].width,
			height: ifds[ 0 ].height,
			data: rgba,
			flipY: true,
			magFilter: LinearFilter,
			minFilter: LinearMipmapLinearFilter
		};

	}
```
</details>


---