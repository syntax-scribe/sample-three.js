[⬅️ Back to Table of Contents](../../../../../index.md)

# 📄 `WebGLExtensions.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/renderers/webgl/WebGLExtensions.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLExtensions` | `../../../../../src/renderers/webgl/WebGLExtensions.js` |
| `CONSOLE_LEVEL` | `../../../utils/console-wrapper.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `gl` | `WebglContextMock` | let/var | `new WebglContextMock()` | ✗ |
| `extensions` | `any` | let/var | `new WebGLExtensions( gl )` | ✗ |
| `gl` | `WebglContextMock` | let/var | `new WebglContextMock( [ 'Extension1', 'Extension2' ] )` | ✗ |
| `extensions` | `any` | let/var | `new WebGLExtensions( gl )` | ✗ |
| `gl` | `WebglContextMock` | let/var | `new WebglContextMock( [ 'WEBKIT_WEBGL_depth_texture' ] )` | ✗ |
| `extensions` | `any` | let/var | `new WebGLExtensions( gl )` | ✗ |
| `gl` | `WebglContextMock` | let/var | `new WebglContextMock( [ 'Extension1', 'Extension2' ] )` | ✗ |
| `extensions` | `any` | let/var | `new WebGLExtensions( gl )` | ✗ |
| `gl` | `WebglContextMock` | let/var | `new WebglContextMock( [ 'WEBKIT_WEBGL_depth_texture' ] )` | ✗ |
| `extensions` | `any` | let/var | `new WebGLExtensions( gl )` | ✗ |


---

## Functions

### `WebglContextMock(supportedExtensions: any): void`

**Parameters:**

- **`supportedExtensions`** `any`

**Returns:** `void`

**Calls:**

- `this.supportedExtensions.indexOf`

<details><summary>Code</summary>

```typescript
function ( supportedExtensions ) {

	this.supportedExtensions = supportedExtensions || [];
	this.getExtension = function ( name ) {

		if ( this.supportedExtensions.indexOf( name ) > - 1 ) {

			return { 'name': name };

		} else {

			return null;

		}

	};

}
```
</details>


---