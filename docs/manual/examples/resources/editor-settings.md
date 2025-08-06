[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `editor-settings.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 📊 Variables & Constants | 20 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/examples/resources/editor-settings.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `u` | `URL` | let/var | `new URL( url, window.location.href )` | ✗ |
| `prefix` | `string` | let/var | `u.origin + dirname( u.pathname )` | ✗ |
| `u` | `URL` | let/var | `new URL( url, window.location.href )` | ✗ |
| `srcRE` | `RegExp` | let/var | `/(src=)(")(.*?)(")()/g` | ✗ |
| `linkRE` | `RegExp` | let/var | `/(href=)(")(.*?)(")()/g` | ✗ |
| `imageSrcRE` | `RegExp` | let/var | `/((?:image\|img)\.src = )(")(.*?)(")()/g` | ✗ |
| `loaderLoadRE` | `RegExp` | let/var | `/(loader\.load[a-z]*\s*\(\s*)('\|")(.*?)('\|")/ig` | ✗ |
| `loaderArrayLoadRE` | `RegExp` | let/var | `/(loader\.load[a-z]*\(\s*\[)([\s\S]*?)(\])/ig` | ✗ |
| `loadFileRE` | `RegExp` | let/var | `/(loadFile\s*\(\s*)('\|")(.*?)('\|")/ig` | ✗ |
| `threejsUrlRE` | `RegExp` | let/var | `/(.*?)('\|")([^"']*?)('\|")([^'"]*?)(\/\*\s+threejs.org:\s+url\s+\*\/)/ig` | ✗ |
| `arrayLineRE` | `RegExp` | let/var | `/^(\s*["\|'])([\s\S]*?)(["\|']*$)/` | ✗ |
| `urlPropRE` | `RegExp` | let/var | `/(url:\s*)('\|")(.*?)('\|")/g` | ✗ |
| `workerRE` | `RegExp` | let/var | `/(new\s+Worker\s*\(\s*)('\|")(.*?)('\|")/g` | ✗ |
| `importScriptsRE` | `RegExp` | let/var | `/(importScripts\s*\(\s*)('\|")(.*?)('\|")/g` | ✗ |
| `moduleRE` | `RegExp` | let/var | `/(import.*?)('\|")(.*?)('\|")/g` | ✗ |
| `version` | `any` | let/var | `*not shown*` | ✗ |
| `moduleRE` | `RegExp` | let/var | `/(import.*?)('\|")(.*?)('\|")/g` | ✗ |
| `res` | `Response` | let/var | `await fetch( 'https://raw.githubusercontent.com/mrdoob/three.js/master/packag...` | ✗ |
| `json` | `any` | let/var | `await res.json()` | ✗ |
| `url` | `URL` | let/var | `new URL( href )` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `fixJSForCodeSite` | fetch( 'https://raw.githubusercontent.com/mrdoob/three.js/master/package.json' ), res.json() | *none* |


---

## Functions

### `dirname(path: any): any`

**Parameters:**

- **`path`** `any`

**Returns:** `any`

**Calls:**

- `path.lastIndexOf`
- `path.substring`

<details><summary>Code</summary>

```typescript
function dirname( path ) {

		const ndx = path.lastIndexOf( '/' );
		return path.substring( 0, ndx + 1 );

	}
```
</details>

### `getPrefix(url: any): string`

**Parameters:**

- **`url`** `any`

**Returns:** `string`

**Calls:**

- `dirname`

<details><summary>Code</summary>

```typescript
function getPrefix( url ) {

		const u = new URL( url, window.location.href );
		const prefix = u.origin + dirname( u.pathname );
		return prefix;

	}
```
</details>

### `getRootPrefix(url: any): string`

**Parameters:**

- **`url`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function getRootPrefix( url ) {

		const u = new URL( url, window.location.href );
		return u.origin;

	}
```
</details>

### `removeDotDotSlash(url: any): any`

**Parameters:**

- **`url`** `any`

**Returns:** `any`

**Calls:**

- `url.split`
- `parts.indexOf`
- `parts.splice`
- `parts.join`

**Internal Comments:**
```
// assumes a well formed URL. In other words: 'https://..//foo.html" is a bad URL and this code would fail. (x2)
```

<details><summary>Code</summary>

```typescript
function removeDotDotSlash( url ) {

		// assumes a well formed URL. In other words: 'https://..//foo.html" is a bad URL and this code would fail.
		const parts = url.split( '/' );
		for ( ;; ) {

			const dotDotNdx = parts.indexOf( '..' );
			if ( dotDotNdx < 0 ) {

				break;

			}

			parts.splice( dotDotNdx - 1, 2 );

		}

		const newUrl = parts.join( '/' );
		return newUrl;

	}
```
</details>

### `fixSourceLinks(url: string, source: string): string`

**JSDoc:**
```typescript
/**
 * Fix any local URLs into fully qualified urls.
 *
 * Examples:
 *    resources/image.jpg ->  https://domain.org/webgl/resouces/image.jpg
 *    /3rdparty/lib.js    ->  https://domain.org/3rdparty/lib.js
 *
 * The reason is (a) we're running the code as via blobUrl and nothing is relative to a blob.
 * (b) we can upload to jsfiddle/codepen and so need to link back to the files.
 *
 * This is all kind of hacky in that it's just a bunch of regular expressions looking
 * for matches.
 *
 * @param {string} url The URL of the file source.
 * @param {string} source An HTML file or JavaScript file
 * @returns {string} the source after having urls fixed.
 */
```

**Parameters:**

- **`url`** `string`
- **`source`** `string`

**Returns:** `string`

**Calls:**

- `getPrefix`
- `getRootPrefix`
- `url.startsWith`
- `removeDotDotSlash`
- `( prefix + url ).replace`
- `url.indexOf`
- `addCorrectPrefix`
- `addPrefix`
- `arrayStr.split( ',' ).map`
- `arrayLineRE.exec`
- `lines.join`
- `source.replace`

**Internal Comments:**
```
// modules require relative paths or fully qualified, otherwise they are module names
```

<details><summary>Code</summary>

```typescript
function fixSourceLinks( url, source ) {

		const srcRE = /(src=)(")(.*?)(")()/g;
		const linkRE = /(href=)(")(.*?)(")()/g;
		const imageSrcRE = /((?:image|img)\.src = )(")(.*?)(")()/g;
		const loaderLoadRE = /(loader\.load[a-z]*\s*\(\s*)('|")(.*?)('|")/ig;
		const loaderArrayLoadRE = /(loader\.load[a-z]*\(\s*\[)([\s\S]*?)(\])/ig;
		const loadFileRE = /(loadFile\s*\(\s*)('|")(.*?)('|")/ig;
		const threejsUrlRE = /(.*?)('|")([^"']*?)('|")([^'"]*?)(\/\*\s+threejs.org:\s+url\s+\*\/)/ig;
		const arrayLineRE = /^(\s*["|'])([\s\S]*?)(["|']*$)/;
		const urlPropRE = /(url:\s*)('|")(.*?)('|")/g;
		const workerRE = /(new\s+Worker\s*\(\s*)('|")(.*?)('|")/g;
		const importScriptsRE = /(importScripts\s*\(\s*)('|")(.*?)('|")/g;
		const moduleRE = /(import.*?)('|")(.*?)('|")/g;
		const prefix = getPrefix( url );
		const rootPrefix = getRootPrefix( url );

		function addCorrectPrefix( url ) {

			return ( url.startsWith( '/' ) )
				? `${rootPrefix}${url}`
				: removeDotDotSlash( ( prefix + url ).replace( /\/.\//g, '/' ) );

		}

		function addPrefix( url ) {

			return url.indexOf( '://' ) < 0 && ! url.startsWith( 'data:' ) && url[ 0 ] !== '?'
				? removeDotDotSlash( addCorrectPrefix( url ) )
				: url;

		}

		function makeLinkFDedQuotes( match, fn, q1, url, q2 ) {

			return fn + q1 + addPrefix( url ) + q2;

		}

		function makeTaggedFDedQuotes( match, start, q1, url, q2, suffix ) {

			return start + q1 + addPrefix( url ) + q2 + suffix;

		}

		function makeFDedQuotesModule( match, start, q1, url, q2 ) {

			// modules require relative paths or fully qualified, otherwise they are module names
			return `${start}${q1}${url.startsWith( '.' ) ? addPrefix( url ) : url}${q2}`;

		}

		function makeArrayLinksFDed( match, prefix, arrayStr, suffix ) {

			const lines = arrayStr.split( ',' ).map( ( line ) => {

				const m = arrayLineRE.exec( line );
				return m
					? `${m[ 1 ]}${addPrefix( m[ 2 ] )}${m[ 3 ]}`
					: line;

			} );
			return `${prefix}${lines.join( ',' )}${suffix}`;

		}

		source = source.replace( srcRE, makeTaggedFDedQuotes );
		source = source.replace( linkRE, makeTaggedFDedQuotes );
		source = source.replace( imageSrcRE, makeTaggedFDedQuotes );
		source = source.replace( urlPropRE, makeLinkFDedQuotes );
		source = source.replace( loadFileRE, makeLinkFDedQuotes );
		source = source.replace( loaderLoadRE, makeLinkFDedQuotes );
		source = source.replace( workerRE, makeLinkFDedQuotes );
		source = source.replace( importScriptsRE, makeLinkFDedQuotes );
		source = source.replace( loaderArrayLoadRE, makeArrayLinksFDed );
		source = source.replace( threejsUrlRE, makeTaggedFDedQuotes );
		source = source.replace( moduleRE, makeFDedQuotesModule );

		return source;

	}
```
</details>

### `addCorrectPrefix(url: any): any`

**Parameters:**

- **`url`** `any`

**Returns:** `any`

**Calls:**

- `url.startsWith`
- `removeDotDotSlash`
- `( prefix + url ).replace`

<details><summary>Code</summary>

```typescript
function addCorrectPrefix( url ) {

			return ( url.startsWith( '/' ) )
				? `${rootPrefix}${url}`
				: removeDotDotSlash( ( prefix + url ).replace( /\/.\//g, '/' ) );

		}
```
</details>

### `addPrefix(url: any): any`

**Parameters:**

- **`url`** `any`

**Returns:** `any`

**Calls:**

- `url.indexOf`
- `url.startsWith`
- `removeDotDotSlash`
- `addCorrectPrefix`

<details><summary>Code</summary>

```typescript
function addPrefix( url ) {

			return url.indexOf( '://' ) < 0 && ! url.startsWith( 'data:' ) && url[ 0 ] !== '?'
				? removeDotDotSlash( addCorrectPrefix( url ) )
				: url;

		}
```
</details>

### `makeLinkFDedQuotes(match: any, fn: any, q1: any, url: any, q2: any): any`

**Parameters:**

- **`match`** `any`
- **`fn`** `any`
- **`q1`** `any`
- **`url`** `any`
- **`q2`** `any`

**Returns:** `any`

**Calls:**

- `addPrefix`

<details><summary>Code</summary>

```typescript
function makeLinkFDedQuotes( match, fn, q1, url, q2 ) {

			return fn + q1 + addPrefix( url ) + q2;

		}
```
</details>

### `makeTaggedFDedQuotes(match: any, start: any, q1: any, url: any, q2: any, suffix: any): any`

**Parameters:**

- **`match`** `any`
- **`start`** `any`
- **`q1`** `any`
- **`url`** `any`
- **`q2`** `any`
- **`suffix`** `any`

**Returns:** `any`

**Calls:**

- `addPrefix`

<details><summary>Code</summary>

```typescript
function makeTaggedFDedQuotes( match, start, q1, url, q2, suffix ) {

			return start + q1 + addPrefix( url ) + q2 + suffix;

		}
```
</details>

### `makeFDedQuotesModule(match: any, start: any, q1: any, url: any, q2: any): string`

**Parameters:**

- **`match`** `any`
- **`start`** `any`
- **`q1`** `any`
- **`url`** `any`
- **`q2`** `any`

**Returns:** `string`

**Calls:**

- `url.startsWith`
- `addPrefix`

**Internal Comments:**
```
// modules require relative paths or fully qualified, otherwise they are module names
```

<details><summary>Code</summary>

```typescript
function makeFDedQuotesModule( match, start, q1, url, q2 ) {

			// modules require relative paths or fully qualified, otherwise they are module names
			return `${start}${q1}${url.startsWith( '.' ) ? addPrefix( url ) : url}${q2}`;

		}
```
</details>

### `makeArrayLinksFDed(match: any, prefix: any, arrayStr: any, suffix: any): string`

**Parameters:**

- **`match`** `any`
- **`prefix`** `any`
- **`arrayStr`** `any`
- **`suffix`** `any`

**Returns:** `string`

**Calls:**

- `arrayStr.split( ',' ).map`
- `arrayLineRE.exec`
- `addPrefix`
- `lines.join`

<details><summary>Code</summary>

```typescript
function makeArrayLinksFDed( match, prefix, arrayStr, suffix ) {

			const lines = arrayStr.split( ',' ).map( ( line ) => {

				const m = arrayLineRE.exec( line );
				return m
					? `${m[ 1 ]}${addPrefix( m[ 2 ] )}${m[ 3 ]}`
					: line;

			} );
			return `${prefix}${lines.join( ',' )}${suffix}`;

		}
```
</details>

### `extraHTMLParsing(html: string): string`

**JSDoc:**
```typescript
/**
 * Called after parsing to give a change to update htmlParts
 * @param {string} html The main page html turned into a template with the <style>, <script> and <body> parts extracted
 * @param {Object<string, HTMLPart>} htmlParts All the extracted parts
 * @return {string} The modified html template
 */
```

**Parameters:**

- **`html`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function extraHTMLParsing( html /* , htmlParts */ ) {

		return html;

	}
```
</details>

### `fixJSForCodeSite(js: any): Promise<any>`

**Parameters:**

- **`js`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `fetch`
- `res.json`
- `console.error`
- `href.startsWith`
- `href.includes`
- `addVersion`
- `js.replace`

**Internal Comments:**
```
// convert https://threejs.org/build/three.module.js -> https://cdn.jsdelivr.net/npm/three@<version>
// convert https://threejs.org/examples/jsm/.?? -> https://cdn.jsdelivr.net/npm/three@<version>/examples/jsm/.??
```

<details><summary>Code</summary>

```typescript
async function fixJSForCodeSite( js ) {

		const moduleRE = /(import.*?)('|")(.*?)('|")/g;

		// convert https://threejs.org/build/three.module.js -> https://cdn.jsdelivr.net/npm/three@<version>
		// convert https://threejs.org/examples/jsm/.?? -> https://cdn.jsdelivr.net/npm/three@<version>/examples/jsm/.??

		if ( ! version ) {

			try {

				const res = await fetch( 'https://raw.githubusercontent.com/mrdoob/three.js/master/package.json' );
				const json = await res.json();
				version = json.version;

			} catch ( e ) {

				console.error( e );

			}

		}

		function addVersion( href ) {

			if ( href.startsWith( window.location.origin ) ) {

				if ( href.includes( '/build/three.module.js' ) ) {

					return `https://cdn.jsdelivr.net/npm/three@${version}`;

				} else if ( href.includes( '/examples/jsm/' ) ) {

					const url = new URL( href );
					return `https://cdn.jsdelivr.net/npm/three@${version}${url.pathname}${url.search}${url.hash}`;

				}

			}

			return href;

		}

		function addVersionToURL( match, start, q1, url, q2 ) {

			return start + q1 + addVersion( url ) + q2;

		}

		if ( version !== undefined ) {

			js = js.replace( moduleRE, addVersionToURL );

		}

		return js;

	}
```
</details>

### `addVersion(href: any): any`

**Parameters:**

- **`href`** `any`

**Returns:** `any`

**Calls:**

- `href.startsWith`
- `href.includes`

<details><summary>Code</summary>

```typescript
function addVersion( href ) {

			if ( href.startsWith( window.location.origin ) ) {

				if ( href.includes( '/build/three.module.js' ) ) {

					return `https://cdn.jsdelivr.net/npm/three@${version}`;

				} else if ( href.includes( '/examples/jsm/' ) ) {

					const url = new URL( href );
					return `https://cdn.jsdelivr.net/npm/three@${version}${url.pathname}${url.search}${url.hash}`;

				}

			}

			return href;

		}
```
</details>

### `addVersionToURL(match: any, start: any, q1: any, url: any, q2: any): any`

**Parameters:**

- **`match`** `any`
- **`start`** `any`
- **`q1`** `any`
- **`url`** `any`
- **`q2`** `any`

**Returns:** `any`

**Calls:**

- `addVersion`

<details><summary>Code</summary>

```typescript
function addVersionToURL( match, start, q1, url, q2 ) {

			return start + q1 + addVersion( url ) + q2;

		}
```
</details>


---