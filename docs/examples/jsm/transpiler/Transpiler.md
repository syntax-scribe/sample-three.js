[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Transpiler.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/transpiler/Transpiler.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Linker` | `./Linker.js` |


---

## Functions

### `Transpiler.parse(source: string): string`

**JSDoc:**
```typescript
/**
	 * Parses the given GLSL source and returns TSL syntax.
	 *
	 * @param {string} source - The GLSL source.
	 * @return {string} The TSL code.
	 */
```

**Parameters:**

- **`source`** `string`

**Returns:** `string`

**Calls:**

- `this.decoder.parse`
- `this.linker.process`
- `this.encoder.emit`

**Internal Comments:**
```
// Process the AST to resolve variable and function references and optimizations. (x5)
```

<details><summary>Code</summary>

```typescript
parse( source ) {

		const ast = this.decoder.parse( source );

		// Process the AST to resolve variable and function references and optimizations.
		this.linker.process( ast );

		return this.encoder.emit( ast );

	}
```
</details>


---

## Classes

### `Transpiler`

<details><summary>Class Code</summary>

```ts
class Transpiler {

	/**
	 * Constructs a new transpiler.
	 *
	 * @param {GLSLDecoder} decoder - The GLSL decoder.
	 * @param {TSLEncoder} encoder - The TSL encoder.
	 */
	constructor( decoder, encoder ) {

		/**
		 * The GLSL decoder. This component parse GLSL and produces
		 * a language-independent AST for further processing.
		 *
		 * @type {GLSLDecoder}
		 */
		this.decoder = decoder;

		/**
		 * The TSL encoder. It takes the AST and emits TSL code.
		 *
		 * @type {TSLEncoder}
		 */
		this.encoder = encoder;

		/**
		 * The linker. It processes the AST and resolves
		 * variable and function references, ensuring that all
		 * dependencies are properly linked.
		 *
		 * @type {Linker}
		 */
		this.linker = new Linker();

	}

	/**
	 * Parses the given GLSL source and returns TSL syntax.
	 *
	 * @param {string} source - The GLSL source.
	 * @return {string} The TSL code.
	 */
	parse( source ) {

		const ast = this.decoder.parse( source );

		// Process the AST to resolve variable and function references and optimizations.
		this.linker.process( ast );

		return this.encoder.emit( ast );

	}

}
```
</details>

#### Methods

##### `parse(source: string): string`

<details><summary>Code</summary>

```ts
parse( source ) {

		const ast = this.decoder.parse( source );

		// Process the AST to resolve variable and function references and optimizations.
		this.linker.process( ast );

		return this.encoder.emit( ast );

	}
```
</details>


---