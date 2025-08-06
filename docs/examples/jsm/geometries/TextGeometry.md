[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TextGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/geometries/TextGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ExtrudeGeometry` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `font` | `any` | let/var | `parameters.font` | ✗ |


---

## Classes

### `TextGeometry`

<details><summary>Class Code</summary>

```ts
class TextGeometry extends ExtrudeGeometry {

	/**
	 * Constructs a new text geometry.
	 *
	 * @param {string} text - The text that should be transformed into a geometry.
	 * @param {TextGeometry~Options} [parameters] - The text settings.
	 */
	constructor( text, parameters = {} ) {

		const font = parameters.font;

		if ( font === undefined ) {

			super(); // generate default extrude geometry

		} else {

			const shapes = font.generateShapes( text, parameters.size );

			// defaults

			if ( parameters.depth === undefined ) parameters.depth = 50;
			if ( parameters.bevelThickness === undefined ) parameters.bevelThickness = 10;
			if ( parameters.bevelSize === undefined ) parameters.bevelSize = 8;
			if ( parameters.bevelEnabled === undefined ) parameters.bevelEnabled = false;

			super( shapes, parameters );

		}

		this.type = 'TextGeometry';

	}

}
```
</details>


---