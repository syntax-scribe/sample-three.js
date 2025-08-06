[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLShader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |

## 📚 Table of Contents

- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLShader.js`**

## Functions

### `WebGLShader(gl: any, type: any, string: any): any`

**Parameters:**

- **`gl`** `any`
- **`type`** `any`
- **`string`** `any`

**Returns:** `any`

**Calls:**

- `gl.createShader`
- `gl.shaderSource`
- `gl.compileShader`

<details><summary>Code</summary>

```typescript
function WebGLShader( gl, type, string ) {

	const shader = gl.createShader( type );

	gl.shaderSource( shader, string );
	gl.compileShader( shader );

	return shader;

}
```
</details>


---