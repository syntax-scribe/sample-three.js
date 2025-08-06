[⬅️ Back to Table of Contents](../../index.md)

# 📄 `rollup.config.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`utils/build/rollup.config.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `terser` | `@rollup/plugin-terser` |
| `MagicString` | `magic-string` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `builds` | `any[]` | let/var | `[ { input: { 'three.core.js': 'src/Three.Core.js', 'three.webgpu.nodes.js': '...` | ✗ |


---

## Functions

### `glsl(): { transform(code: any, id: any): { code: any; map: any; }; }`

**Returns:** `{ transform(code: any, id: any): { code: any; map: any; }; }`

**Calls:**

- `/\.glsl.js$/.test`
- `code.replace`
- `JSON.stringify`
- `p1
						.trim()
						.replace( /\r/g, '' )
						.replace( /[ \t]*\/\/.*\n/g, '' ) // remove //
						.replace( /[ \t]*\/\*[\s\S]*?\*\//g, '' ) // remove /* */
						.replace`
- `code.toString`
- `code.generateMap`

<details><summary>Code</summary>

```typescript
export function glsl() {

	return {

		transform( code, id ) {

			if ( /\.glsl.js$/.test( id ) === false ) return;

			code = new MagicString( code );

			code.replace( /\/\* glsl \*\/\`(.*?)\`/sg, function ( match, p1 ) {

				return JSON.stringify(
					p1
						.trim()
						.replace( /\r/g, '' )
						.replace( /[ \t]*\/\/.*\n/g, '' ) // remove //
						.replace( /[ \t]*\/\*[\s\S]*?\*\//g, '' ) // remove /* */
						.replace( /\n{2,}/g, '\n' ) // # \n+ to \n
				);

			} );

			return {
				code: code.toString(),
				map: code.generateMap()
			};

		}

	};

}
```
</details>

### `header(): { renderChunk(code: any): { code: any; map: any; }; }`

**Returns:** `{ renderChunk(code: any): { code: any; map: any; }; }`

**Calls:**

- `code.prepend`
- `code.toString`
- `code.generateMap`

<details><summary>Code</summary>

```typescript
function header() {

	return {

		renderChunk( code ) {

			code = new MagicString( code );

			code.prepend( `/**
 * @license
 * Copyright 2010-2025 Three.js Authors
 * SPDX-License-Identifier: MIT
 */\n` );

			return {
				code: code.toString(),
				map: code.generateMap()
			};

		}

	};

}
```
</details>

### `default_export_function(args: any): any[]`

**Parameters:**

- **`args`** `any`

**Returns:** `any[]`

<details><summary>Code</summary>

```typescript
( args ) => args.configOnlyModule ? builds.slice( 0, 4 ) : builds
```
</details>


---