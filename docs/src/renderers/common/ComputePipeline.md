[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ComputePipeline.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/ComputePipeline.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Pipeline` | `./Pipeline.js` |


---

## Classes

### `ComputePipeline`

<details><summary>Class Code</summary>

```ts
class ComputePipeline extends Pipeline {

	/**
	 * Constructs a new render pipeline.
	 *
	 * @param {string} cacheKey - The pipeline's cache key.
	 * @param {ProgrammableStage} computeProgram - The pipeline's compute shader.
	 */
	constructor( cacheKey, computeProgram ) {

		super( cacheKey );

		/**
		 * The pipeline's compute shader.
		 *
		 * @type {ProgrammableStage}
		 */
		this.computeProgram = computeProgram;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isComputePipeline = true;

	}

}
```
</details>


---