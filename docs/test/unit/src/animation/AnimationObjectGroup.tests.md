[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `AnimationObjectGroup.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 13 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/animation/AnimationObjectGroup.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationObjectGroup` | `../../../../src/animation/AnimationObjectGroup.js` |
| `Object3D` | `../../../../src/core/Object3D.js` |
| `PropertyBinding` | `../../../../src/animation/PropertyBinding.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `ObjectA` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `ObjectB` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `ObjectC` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `PathA` | `"object.position"` | let/var | `'object.position'` | ✗ |
| `PathB` | `"object.rotation"` | let/var | `'object.rotation'` | ✗ |
| `PathC` | `"object.scale"` | let/var | `'object.scale'` | ✗ |
| `groupA` | `AnimationObjectGroup` | let/var | `new AnimationObjectGroup()` | ✗ |
| `object` | `AnimationObjectGroup` | let/var | `new AnimationObjectGroup()` | ✗ |
| `rootNodes` | `any[]` | let/var | `[]` | ✗ |
| `pathsOk` | `boolean` | let/var | `true` | ✗ |
| `nodesOk` | `boolean` | let/var | `true` | ✗ |
| `groupA` | `AnimationObjectGroup` | let/var | `new AnimationObjectGroup()` | ✗ |
| `groupB` | `AnimationObjectGroup` | let/var | `new AnimationObjectGroup( ObjectA, ObjectB )` | ✗ |


---

## Functions

### `expect(testIndex: any, group: any, bindings: any, path: any, cached: any, roots: any): void`

**Parameters:**

- **`testIndex`** `any`
- **`group`** `any`
- **`bindings`** `any`
- **`path`** `any`
- **`cached`** `any`
- **`roots`** `any`

**Returns:** `void`

**Calls:**

- `rootNodes.push`
- `rootNodes.indexOf`
- `assert.ok`

<details><summary>Code</summary>

```typescript
function expect( testIndex, group, bindings, path, cached, roots ) {

				var rootNodes = [], pathsOk = true, nodesOk = true;

				for ( var i = group.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

					if ( bindings[ i ].path !== path ) pathsOk = false;
					rootNodes.push( bindings[ i ].rootNode );

				}

				for ( var i = 0, n = roots.length; i !== n; ++ i ) {

					if ( rootNodes.indexOf( roots[ i ] ) === - 1 ) nodesOk = false;

				}

				assert.ok( pathsOk, QUnit.testIndex + ' paths' );
				assert.ok( nodesOk, QUnit.testIndex + ' nodes' );
				assert.ok( group.nCachedObjects_ === cached, QUnit.testIndex + ' cache size' );
				assert.ok( bindings.length - group.nCachedObjects_ === roots.length, QUnit.testIndex + ' object count' );

			}
```
</details>


---