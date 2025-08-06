[⬅️ Back to Table of Contents](../../index.md)

# 📄 `check-coverage.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/e2e/check-coverage.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `chalk` | `chalk` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `F` | `any[]` | let/var | `[]` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `main` | fs.readdir( 'examples' ), fs.readdir( 'examples/screenshots' ), fs.readFile( 'examples/files.json' ) | *none* |


---

## Functions

### `main(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `( await fs.readdir( 'examples' ) )
		.filter( s => s.endsWith( '.html' ) )
		.map( s => s.slice( 0, s.indexOf( '.' ) ) )
		.filter`
- `( await fs.readdir( 'examples/screenshots' ) )
		.filter( s => s.indexOf( '.' ) !== - 1 )
		.map`
- `s.slice`
- `s.indexOf`
- `JSON.parse`
- `fs.readFile`
- `Object.values`
- `F.push`
- `E.filter`
- `S.includes`
- `S.filter`
- `E.includes`
- `F.includes`
- `F.filter`
- `console.green`
- `console.red`
- `subES.join`
- `subSE.join`
- `subEF.join`
- `subFE.join`
- `process.exit`

**Internal Comments:**
```
// examples (x2)
// screenshots (x2)
// files.js (x2)
```

<details><summary>Code</summary>

```typescript
async function main() {

	// examples
	const E = ( await fs.readdir( 'examples' ) )
		.filter( s => s.endsWith( '.html' ) )
		.map( s => s.slice( 0, s.indexOf( '.' ) ) )
		.filter( f => f !== 'index' );

	// screenshots
	const S = ( await fs.readdir( 'examples/screenshots' ) )
		.filter( s => s.indexOf( '.' ) !== - 1 )
		.map( s => s.slice( 0, s.indexOf( '.' ) ) );

	// files.js
	const F = [];

	const files = JSON.parse( await fs.readFile( 'examples/files.json' ) );

	for ( const section of Object.values( files ) ) {

		F.push( ...section );

	}

	const subES = E.filter( x => ! S.includes( x ) );
	const subSE = S.filter( x => ! E.includes( x ) );
	const subEF = E.filter( x => ! F.includes( x ) );
	const subFE = F.filter( x => ! E.includes( x ) );

	if ( subES.length + subSE.length + subEF.length + subFE.length === 0 ) {

		console.green( 'TEST PASSED! All examples is covered with screenshots and descriptions in files.json!' );

	} else {

		if ( subES.length > 0 ) console.red( 'Make screenshot for example(s): ' + subES.join( ' ' ) );
		if ( subSE.length > 0 ) console.red( 'Remove unnecessary screenshot(s): ' + subSE.join( ' ' ) );
		if ( subEF.length > 0 ) console.red( 'Add description in files.json for example(s): ' + subEF.join( ' ' ) );
		if ( subFE.length > 0 ) console.red( 'Remove description in files.json for example(s): ' + subFE.join( ' ' ) );

		console.red( 'TEST FAILED!' );

		process.exit( 1 );

	}

}
```
</details>


---