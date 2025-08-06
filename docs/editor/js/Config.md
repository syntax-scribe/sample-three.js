[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Config.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Config.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `name` | `"threejs-editor"` | let/var | `'threejs-editor'` | ✗ |
| `userLanguage` | `string` | let/var | `navigator.language.split( '-' )[ 0 ]` | ✗ |
| `suggestedLanguage` | `string` | let/var | `[ 'fr', 'ja', 'zh', 'ko', 'fa' ].includes( userLanguage ) ? userLanguage : 'en'` | ✗ |
| `storage` | `{ language: string; autosave: boolean...` | let/var | `{ 'language': suggestedLanguage, 'autosave': true, 'project/title': '', 'proj...` | ✗ |


---

## Functions

### `Config(): { getKey: (key: any) => any; setKey: (...args: any[]) => void; clear: () => void; }`

**Returns:** `{ getKey: (key: any) => any; setKey: (...args: any[]) => void; clear: () => void; }`

**Calls:**

- `navigator.language.split`
- `[ 'fr', 'ja', 'zh', 'ko', 'fa' ].includes`
- `JSON.stringify`
- `JSON.parse`
- `console.log`
- `/\d\d\:\d\d\:\d\d/.exec`

<details><summary>Code</summary>

```typescript
function Config() {

	const name = 'threejs-editor';

	const userLanguage = navigator.language.split( '-' )[ 0 ];

	const suggestedLanguage = [ 'fr', 'ja', 'zh', 'ko', 'fa' ].includes( userLanguage ) ? userLanguage : 'en';

	const storage = {
		'language': suggestedLanguage,

		'autosave': true,

		'project/title': '',
		'project/editable': false,
		'project/vr': false,

		'project/renderer/antialias': true,
		'project/renderer/shadows': true,
		'project/renderer/shadowType': 1, // PCF
		'project/renderer/toneMapping': 0, // NoToneMapping
		'project/renderer/toneMappingExposure': 1,

		'settings/history': false,

		'settings/shortcuts/translate': 'w',
		'settings/shortcuts/rotate': 'e',
		'settings/shortcuts/scale': 'r',
		'settings/shortcuts/undo': 'z',
		'settings/shortcuts/focus': 'f'
	};

	if ( window.localStorage[ name ] === undefined ) {

		window.localStorage[ name ] = JSON.stringify( storage );

	} else {

		const data = JSON.parse( window.localStorage[ name ] );

		for ( const key in data ) {

			storage[ key ] = data[ key ];

		}

	}

	return {

		getKey: function ( key ) {

			return storage[ key ];

		},

		setKey: function () { // key, value, key, value ...

			for ( let i = 0, l = arguments.length; i < l; i += 2 ) {

				storage[ arguments[ i ] ] = arguments[ i + 1 ];

			}

			window.localStorage[ name ] = JSON.stringify( storage );

			console.log( '[' + /\d\d\:\d\d\:\d\d/.exec( new Date() )[ 0 ] + ']', 'Saved config to LocalStorage.' );

		},

		clear: function () {

			delete window.localStorage[ name ];

		}

	};

}
```
</details>

### `getKey(key: any): any`

**Parameters:**

- **`key`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( key ) {

			return storage[ key ];

		}
```
</details>

### `setKey(): void`

**Returns:** `void`

**Calls:**

- `JSON.stringify`
- `console.log`
- `/\d\d\:\d\d\:\d\d/.exec`

<details><summary>Code</summary>

```typescript
function () { // key, value, key, value ...

			for ( let i = 0, l = arguments.length; i < l; i += 2 ) {

				storage[ arguments[ i ] ] = arguments[ i + 1 ];

			}

			window.localStorage[ name ] = JSON.stringify( storage );

			console.log( '[' + /\d\d\:\d\d\:\d\d/.exec( new Date() )[ 0 ] + ']', 'Saved config to LocalStorage.' );

		}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

			delete window.localStorage[ name ];

		}
```
</details>

### `getKey(key: any): any`

**Parameters:**

- **`key`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( key ) {

			return storage[ key ];

		}
```
</details>

### `setKey(): void`

**Returns:** `void`

**Calls:**

- `JSON.stringify`
- `console.log`
- `/\d\d\:\d\d\:\d\d/.exec`

<details><summary>Code</summary>

```typescript
function () { // key, value, key, value ...

			for ( let i = 0, l = arguments.length; i < l; i += 2 ) {

				storage[ arguments[ i ] ] = arguments[ i + 1 ];

			}

			window.localStorage[ name ] = JSON.stringify( storage );

			console.log( '[' + /\d\d\:\d\d\:\d\d/.exec( new Date() )[ 0 ] + ']', 'Saved config to LocalStorage.' );

		}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

			delete window.localStorage[ name ];

		}
```
</details>


---