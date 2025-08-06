[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `formatBytes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/treeshake/utils/formatBytes.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `k` | `1000` | let/var | `1000` | ✗ |
| `dm` | `number` | let/var | `decimals < 0 ? 0 : decimals` | ✗ |
| `sizes` | `string[]` | let/var | `[ 'B', 'kB', 'MB', 'GB' ]` | ✗ |


---

## Functions

### `formatBytes(bytes: any, decimals: number, units: boolean): string`

**Parameters:**

- **`bytes`** `any`
- **`decimals`** `number`
- **`units`** `boolean`

**Returns:** `string`

**Calls:**

- `Math.floor`
- `Math.log`
- `parseFloat`
- `( bytes / Math.pow( k, i ) ).toFixed`
- `Math.pow`

<details><summary>Code</summary>

```typescript
export function formatBytes( bytes, decimals = 1, units = true ) {

	if ( bytes === 0 ) return '0 B';

	const k = 1000;
	const dm = decimals < 0 ? 0 : decimals;
	const sizes = [ 'B', 'kB', 'MB', 'GB' ];

	const i = Math.floor( Math.log( bytes ) / Math.log( k ) );

	return parseFloat( ( bytes / Math.pow( k, i ) ).toFixed( dm ) ) + ( units ? ' ' + sizes[ i ] : '' );

}
```
</details>


---