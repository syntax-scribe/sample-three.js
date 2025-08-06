[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `make-geo-picking-texture-ogc.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/tools/geo-picking/make-geo-picking-texture-ogc.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `baseDir` | `string` | let/var | `process.argv[ 2 ]` | ✗ |
| `buf` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( Buffer.from( area.geom, 'base64' ) )` | ✗ |


---

## Functions

### `readJSON(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `JSON.parse`
- `fs.readFileSync`
- `path.join`

<details><summary>Code</summary>

```typescript
function readJSON( name ) {

	return JSON.parse( fs.readFileSync( path.join( baseDir, name ), { encoding: 'utf-8' } ) );

}
```
</details>

### `main(): void`

**Returns:** `void`

**Calls:**

- `readJSON`
- `areas.forEach`
- `console.log`
- `Buffer.from`
- `parseGeom`
- `JSON.stringify`

<details><summary>Code</summary>

```typescript
function main() {

	const areas = readJSON( 'level1.json' );
	areas.forEach( ( area, ndx ) => {

		console.log( ndx );
		try {

			const buf = new Uint8Array( Buffer.from( area.geom, 'base64' ) );
			area.geom = parseGeom( buf );

		} catch ( e ) {

			console.log( 'ERROR:', e );
			console.log( JSON.stringify( area, null, 2 ) );
			throw e;

		}

	} );

	console.log( JSON.stringify( areas, null, 2 ) );

}
```
</details>


---