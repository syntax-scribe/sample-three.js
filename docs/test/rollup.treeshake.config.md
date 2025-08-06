[⬅️ Back to Table of Contents](../index.md)

# 📄 `rollup.treeshake.config.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/rollup.treeshake.config.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `path` | `path` |
| `resolve` | `@rollup/plugin-node-resolve` |
| `filesize` | `rollup-plugin-filesize` |
| `terser` | `@rollup/plugin-terser` |
| `visualizer` | `rollup-plugin-visualizer` |
| `glsl` | `../utils/build/rollup.config.js` |
| `chalk` | `chalk` |


---

## Functions

### `logStatsFile(): { writeBundle(): void; }`

**Returns:** `{ writeBundle(): void; }`

**Calls:**

- `console.log`
- `chalk.blue.bold.underline`

<details><summary>Code</summary>

```typescript
function logStatsFile() {

	return {
		writeBundle() {

			console.log();
			console.log( 'Open the following url in a browser to analyze the tree-shaken bundle.' );
			console.log( chalk.blue.bold.underline( statsFile ) );
			console.log();

		}
	};

}
```
</details>


---