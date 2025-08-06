[⬅️ Back to Table of Contents](../../index.md)

# 📄 `index.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/treeshake/index.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `camera` | `any` | let/var | `*not shown*` | ✗ |
| `scene` | `any` | let/var | `*not shown*` | ✗ |
| `renderer` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `init(): void`

**Returns:** `void`

**Calls:**

- `renderer.setSize`
- `renderer.setAnimationLoop`
- `document.body.appendChild`

<details><summary>Code</summary>

```typescript
function init() {

	camera = new THREE.PerspectiveCamera( 70, window.innerWidth / window.innerHeight, 0.01, 10 );

	scene = new THREE.Scene();

	renderer = new THREE.WebGLRenderer( { antialias: true } );
	renderer.setSize( window.innerWidth, window.innerHeight );
	renderer.setAnimationLoop( animation );
	document.body.appendChild( renderer.domElement );

}
```
</details>

### `animation(): void`

**Returns:** `void`

**Calls:**

- `renderer.render`

<details><summary>Code</summary>

```typescript
function animation( ) {

	renderer.render( scene, camera );

}
```
</details>


---