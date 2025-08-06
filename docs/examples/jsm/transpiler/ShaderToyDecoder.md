[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ShaderToyDecoder.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/transpiler/ShaderToyDecoder.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Return` | `./AST.js` |
| `VariableDeclaration` | `./AST.js` |
| `Accessor` | `./AST.js` |
| `GLSLDecoder` | `./GLSLDecoder.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `fragColor` | `Accessor` | let/var | `new Accessor( 'fragColor' )` | ✗ |


---

## Functions

### `ShaderToyDecoder.parseFunction(): any`

**Returns:** `any`

**Calls:**

- `super.parseFunction`
- `node.body.unshift`
- `node.body.push`

<details><summary>Code</summary>

```typescript
parseFunction() {

		const node = super.parseFunction();

		if ( node.name === 'mainImage' ) {

			node.params = []; // remove default parameters
			node.type = 'vec4';
			node.layout = false; // for now

			const fragColor = new Accessor( 'fragColor' );

			for ( const subNode of node.body ) {

				if ( subNode.isReturn ) {

					subNode.value = fragColor;

				}

			}

			node.body.unshift( new VariableDeclaration( 'vec4', 'fragColor' ) );
			node.body.push( new Return( fragColor ) );

		}

		return node;

	}
```
</details>


---

## Classes

### `ShaderToyDecoder`

<details><summary>Class Code</summary>

```ts
class ShaderToyDecoder extends GLSLDecoder {

	constructor() {

		super();

		this.addPolyfill( 'iTime', 'float iTime = time;' );
		this.addPolyfill( 'iResolution', 'vec2 iResolution = screenSize;' );
		this.addPolyfill( 'fragCoord', 'vec3 fragCoord = vec3( screenCoordinate.x, screenSize.y - screenCoordinate.y, screenCoordinate.z );' );

	}

	parseFunction() {

		const node = super.parseFunction();

		if ( node.name === 'mainImage' ) {

			node.params = []; // remove default parameters
			node.type = 'vec4';
			node.layout = false; // for now

			const fragColor = new Accessor( 'fragColor' );

			for ( const subNode of node.body ) {

				if ( subNode.isReturn ) {

					subNode.value = fragColor;

				}

			}

			node.body.unshift( new VariableDeclaration( 'vec4', 'fragColor' ) );
			node.body.push( new Return( fragColor ) );

		}

		return node;

	}

}
```
</details>

#### Methods

##### `parseFunction(): any`

<details><summary>Code</summary>

```ts
parseFunction() {

		const node = super.parseFunction();

		if ( node.name === 'mainImage' ) {

			node.params = []; // remove default parameters
			node.type = 'vec4';
			node.layout = false; // for now

			const fragColor = new Accessor( 'fragColor' );

			for ( const subNode of node.body ) {

				if ( subNode.isReturn ) {

					subNode.value = fragColor;

				}

			}

			node.body.unshift( new VariableDeclaration( 'vec4', 'fragColor' ) );
			node.body.push( new Return( fragColor ) );

		}

		return node;

	}
```
</details>


---