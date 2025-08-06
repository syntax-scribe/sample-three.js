[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Pipeline.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Pipeline.js`**

## Classes

### `Pipeline`

<details><summary>Class Code</summary>

```ts
class Pipeline {

	/**
	 * Constructs a new pipeline.
	 *
	 * @param {string} cacheKey - The pipeline's cache key.
	 */
	constructor( cacheKey ) {

		/**
		 * The pipeline's cache key.
		 *
		 * @type {string}
		 */
		this.cacheKey = cacheKey;

		/**
		 * How often the pipeline is currently in use.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.usedTimes = 0;

	}

}
```
</details>


---