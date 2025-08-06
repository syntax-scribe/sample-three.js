[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Raymarching.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/utils/Raymarching.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `varying` | `three/tsl` |
| `vec4` | `three/tsl` |
| `modelWorldMatrixInverse` | `three/tsl` |
| `cameraPosition` | `three/tsl` |
| `positionGeometry` | `three/tsl` |
| `float` | `three/tsl` |
| `Fn` | `three/tsl` |
| `Loop` | `three/tsl` |
| `max` | `three/tsl` |
| `min` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |


---

## Functions

### `RaymarchingBox(steps: number | Node, callback: any): void`

**Parameters:**

- **`steps`** `number | Node`
- **`callback`** `any`

**Returns:** `void`

**Calls:**

- `varying (from three/tsl)`
- `vec3 (from three/tsl)`
- `modelWorldMatrixInverse.mul`
- `vec4 (from three/tsl)`
- `positionGeometry.sub`
- `vDirection.normalize`
- `vec2( hitBox( { orig: vOrigin, dir: rayDir } ) ).toVar`
- `bounds.x.greaterThan( bounds.y ).discard`
- `bounds.assign`
- `vec2 (from three/tsl)`
- `max (from three/tsl)`
- `vec3( rayDir.abs().reciprocal() ).toVar`
- `float( min( inc.x, min( inc.y, inc.z ) ) ).toVar`
- `delta.divAssign`
- `float (from three/tsl)`
- `vec3( vOrigin.add( bounds.x.mul( rayDir ) ) ).toVar`
- `Loop (from three/tsl)`
- `callback`
- `positionRay.addAssign`
- `rayDir.mul`

<details><summary>Code</summary>

```typescript
( steps, callback ) => {

	const vOrigin = varying( vec3( modelWorldMatrixInverse.mul( vec4( cameraPosition, 1.0 ) ) ) );
	const vDirection = varying( positionGeometry.sub( vOrigin ) );

	const rayDir = vDirection.normalize();
	const bounds = vec2( hitBox( { orig: vOrigin, dir: rayDir } ) ).toVar();

	bounds.x.greaterThan( bounds.y ).discard();

	bounds.assign( vec2( max( bounds.x, 0.0 ), bounds.y ) );

	const inc = vec3( rayDir.abs().reciprocal() ).toVar();
	const delta = float( min( inc.x, min( inc.y, inc.z ) ) ).toVar();

	delta.divAssign( float( steps ) );

	const positionRay = vec3( vOrigin.add( bounds.x.mul( rayDir ) ) ).toVar();

	Loop( { type: 'float', start: bounds.x, end: bounds.y, update: delta }, () => {

		callback( { positionRay } );

		positionRay.addAssign( rayDir.mul( delta ) );

	} );

}
```
</details>


---