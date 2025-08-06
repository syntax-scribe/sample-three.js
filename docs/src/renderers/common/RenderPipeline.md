[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderPipeline.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/RenderPipeline.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Pipeline` | `./Pipeline.js` |


---

## Classes

### `RenderPipeline`

<details><summary>Class Code</summary>

```ts
class RenderPipeline extends Pipeline {

	/**
	 * Constructs a new render pipeline.
	 *
	 * @param {string} cacheKey - The pipeline's cache key.
	 * @param {ProgrammableStage} vertexProgram - The pipeline's vertex shader.
	 * @param {ProgrammableStage} fragmentProgram - The pipeline's fragment shader.
	 */
	constructor( cacheKey, vertexProgram, fragmentProgram ) {

		super( cacheKey );

		/**
		 * The pipeline's vertex shader.
		 *
		 * @type {ProgrammableStage}
		 */
		this.vertexProgram = vertexProgram;

		/**
		 * The pipeline's fragment shader.
		 *
		 * @type {ProgrammableStage}
		 */
		this.fragmentProgram = fragmentProgram;

	}

}
```
</details>


---