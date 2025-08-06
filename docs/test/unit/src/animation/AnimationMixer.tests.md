[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `AnimationMixer.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/animation/AnimationMixer.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationMixer` | `../../../../src/animation/AnimationMixer.js` |
| `EventDispatcher` | `../../../../src/core/EventDispatcher.js` |
| `AnimationClip` | `../../../../src/animation/AnimationClip.js` |
| `VectorKeyframeTrack` | `../../../../src/animation/tracks/VectorKeyframeTrack.js` |
| `Object3D` | `../../../../src/core/Object3D.js` |
| `zero3` | `../../utils/math-constants.js` |
| `one3` | `../../utils/math-constants.js` |
| `two3` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `clips` | `any[]` | let/var | `[]` | ✗ |
| `track` | `VectorKeyframeTrack` | let/var | `new VectorKeyframeTrack( '.scale', [ 0, dur ], [ scale1.x, scale1.y, scale1.z...` | ✗ |
| `object` | `AnimationMixer` | let/var | `new AnimationMixer()` | ✗ |
| `object` | `AnimationMixer` | let/var | `new AnimationMixer()` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `animMixer` | `AnimationMixer` | let/var | `new AnimationMixer( obj )` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `animMixer` | `AnimationMixer` | let/var | `new AnimationMixer( obj )` | ✗ |


---

## Functions

### `getClips(pos1: any, pos2: any, scale1: any, scale2: any, dur: any): AnimationClip[]`

**Parameters:**

- **`pos1`** `any`
- **`pos2`** `any`
- **`scale1`** `any`
- **`scale2`** `any`
- **`dur`** `any`

**Returns:** `AnimationClip[]`

**Calls:**

- `clips.push`

<details><summary>Code</summary>

```typescript
function getClips( pos1, pos2, scale1, scale2, dur ) {

	const clips = [];

	let track = new VectorKeyframeTrack( '.scale', [ 0, dur ], [ scale1.x, scale1.y, scale1.z, scale2.x, scale2.y, scale2.z ] );
	clips.push( new AnimationClip( 'scale', dur, [ track ] ) );

	track = new VectorKeyframeTrack( '.position', [ 0, dur ], [ pos1.x, pos1.y, pos1.z, pos2.x, pos2.y, pos2.z ] );
	clips.push( new AnimationClip( 'position', dur, [ track ] ) );

	return clips;

}
```
</details>


---