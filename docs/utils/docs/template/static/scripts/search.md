[⬅️ Back to Table of Contents](../../../../../index.md)

# 📄 `search.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 📊 Variables & Constants | 10 |
| ⚡ Async/Await Patterns | 2 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`utils/docs/template/static/scripts/search.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `base` | `string` | let/var | `origin + baseURL` | ✗ |
| `url` | `URL` | let/var | `new URL( 'data/search.json', base )` | ✗ |
| `result` | `Response` | let/var | `await fetch( url )` | ✗ |
| `output` | `string` | let/var | `''` | ✗ |
| `removeHTMLTagsRegExp` | `RegExp` | let/var | `/(<([^>]+)>)/ig` | ✗ |
| `defaultOptions` | `{ shouldSort: boolean; threshold: num...` | let/var | `{ shouldSort: true, threshold: 0.4, location: 0, distance: 100, maxPatternLen...` | ✗ |
| `options` | `{ shouldSort: boolean; threshold: num...` | let/var | `{ ...defaultOptions }` | ✗ |
| `fuse` | `any` | let/var | `new Fuse( list, options, searchIndex )` | ✗ |
| `searchData` | `any` | let/var | `*not shown*` | ✗ |
| `keys` | `string[]` | let/var | `[ 'title', 'description' ]` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `fetchAllData` | fetch( url ), result.json() | *none* |
| async-function | `search` | fetchAllData() | *none* |


---

## Functions

### `hideSearch(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function hideSearch() {

	searchContainer.style.display = 'none';
	contentContainer.style.display = 'block';


}
```
</details>

### `showResultText(text: any): void`

**Parameters:**

- **`text`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function showResultText( text ) {

	resultBox.innerHTML = text;

}
```
</details>

### `showSearch(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function showSearch() {

	searchContainer.style.display = 'block';
	contentContainer.style.display = 'none';

}
```
</details>

### `extractUrlBase(url: any): any`

**Parameters:**

- **`url`** `any`

**Returns:** `any`

**Calls:**

- `url.lastIndexOf`
- `url.slice`

<details><summary>Code</summary>

```typescript
function extractUrlBase( url ) {

	const index = url.lastIndexOf( '/' );

	if ( index === - 1 ) return './';

	return url.slice( 0, index + 1 );

}
```
</details>

### `fetchAllData(): Promise<any>`

**Returns:** `Promise<any>`

**Calls:**

- `extractUrlBase`
- `fetch`
- `result.json`

<details><summary>Code</summary>

```typescript
async function fetchAllData() {

	const { origin, pathname } = location;

	const baseURL = extractUrlBase( pathname );

	const base = origin + baseURL;

	const url = new URL( 'data/search.json', base );
	const result = await fetch( url );
	const { list } = await result.json();

	return list;

}
```
</details>

### `buildSearchResult(result: any): string`

**Parameters:**

- **`result`** `any`

**Returns:** `string`

**Calls:**

- `res.item.link.replace( '<a href="', '' ).replace`
- `title.replace`
- `description.replace`

<details><summary>Code</summary>

```typescript
function buildSearchResult( result ) {

	let output = '';
	const removeHTMLTagsRegExp = /(<([^>]+)>)/ig;

	for ( const res of result ) {

		const { title = '', description = '' } = res.item;

		const _link = res.item.link.replace( '<a href="', '' ).replace( /">.*/, '' );
		const _title = title.replace( removeHTMLTagsRegExp, '' );
		const _description = description.replace( removeHTMLTagsRegExp, '' );

		output += `
    <a href="${_link}" class="search-result-item" onclick="hideSearch()">
      <span class="search-result-item-title">${_title}</span>
      <span class="search-result-item-description">- ${_description || 'No description available.'}</span>
    </a>
    `;

	}

	return output;

}
```
</details>

### `getSearchResult(list: any, keys: any, searchKey: any): any`

**Parameters:**

- **`list`** `any`
- **`keys`** `any`
- **`searchKey`** `any`

**Returns:** `any`

**Calls:**

- `Fuse.createIndex`
- `fuse.search`
- `result.slice`

**Internal Comments:**
```
// eslint-disable-next-line no-undef (x4)
```

<details><summary>Code</summary>

```typescript
function getSearchResult( list, keys, searchKey ) {

	const defaultOptions = {
		shouldSort: true,
		threshold: 0.4,
		location: 0,
		distance: 100,
		maxPatternLength: 32,
		minMatchCharLength: 1,
		keys: keys
	};

	const options = { ...defaultOptions };

	// eslint-disable-next-line no-undef
	const searchIndex = Fuse.createIndex( options.keys, list );

	// eslint-disable-next-line no-undef
	const fuse = new Fuse( list, options, searchIndex );

	const result = fuse.search( searchKey );

	if ( result.length > 20 ) {

		return result.slice( 0, 20 );

	}

	return result;

}
```
</details>

### `search(value: any): Promise<void>`

**Parameters:**

- **`value`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `hideSearch`
- `showSearch`
- `showResultText`
- `fetchAllData`
- `console.log`
- `getSearchResult`
- `buildSearchResult`

<details><summary>Code</summary>

```typescript
async function search( value ) {

	if ( value === '' ) {

		hideSearch();
		return;

	}

	showSearch();

	const keys = [ 'title', 'description' ];

	if ( searchData === undefined ) {

		showResultText( 'Loading...' );

		try {

			searchData = await fetchAllData();

		} catch ( e ) {

			console.log( e );
			showResultText( 'Failed to load result.' );

			return;

		}

	}

	const result = getSearchResult( searchData, keys, value );

	if ( ! result.length ) {

		showResultText( 'No result found! Try some different combination.' );

		return;

	}

	resultBox.innerHTML = buildSearchResult( result );

}
```
</details>


---