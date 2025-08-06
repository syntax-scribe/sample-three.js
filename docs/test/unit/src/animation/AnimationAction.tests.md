[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `AnimationAction.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 17 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/animation/AnimationAction.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationAction` | `../../../../src/animation/AnimationAction.js` |
| `AnimationMixer` | `../../../../src/animation/AnimationMixer.js` |
| `AnimationClip` | `../../../../src/animation/AnimationClip.js` |
| `NumberKeyframeTrack` | `../../../../src/animation/tracks/NumberKeyframeTrack.js` |
| `Object3D` | `../../../../src/core/Object3D.js` |
| `LoopOnce` | `../../../../src/constants.js` |
| `LoopRepeat` | `../../../../src/constants.js` |
| `LoopPingPong` | `../../../../src/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `root` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `mixer` | `AnimationMixer` | let/var | `new AnimationMixer( root )` | ✗ |
| `track` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( '.rotation[x]', [ 0, 1000 ], [ 0, 360 ] )` | ✗ |
| `clip` | `AnimationClip` | let/var | `new AnimationClip( 'clip1', 1000, [ track ] )` | ✗ |
| `root` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `mixer` | `AnimationMixer` | let/var | `new AnimationMixer( root )` | ✗ |
| `track` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( '.rotation[x]', [ 0, 1000 ], [ 0, 360 ] )` | ✗ |
| `clip` | `AnimationClip` | let/var | `new AnimationClip( 'clip1', 1000, [ track ] )` | ✗ |
| `track2` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( '.rotation[y]', [ 0, 1000 ], [ 0, 360 ] )` | ✗ |
| `clip2` | `AnimationClip` | let/var | `new AnimationClip( 'clip2', 1000, [ track ] )` | ✗ |
| `mixer` | `AnimationMixer` | let/var | `new AnimationMixer()` | ✗ |
| `clip` | `AnimationClip` | let/var | `new AnimationClip( 'nonname', - 1, [] )` | ✗ |
| `animationAction` | `AnimationAction` | let/var | `new AnimationAction( mixer, clip )` | ✗ |
| `root` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `mixer` | `AnimationMixer` | let/var | `new AnimationMixer( root )` | ✗ |
| `track` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( '.rotation[x]', [ 0, 750 ], [ 0, 270 ] )` | ✗ |
| `clip` | `AnimationClip` | let/var | `new AnimationClip( 'clip1', 750, [ track ] )` | ✗ |


---

## Functions

### `createAnimation(): { root: Object3D; mixer: AnimationMixer; track: NumberKeyframeTrack; clip: AnimationClip; animationAction: AnimationAction; }`

**Returns:** `{ root: Object3D; mixer: AnimationMixer; track: NumberKeyframeTrack; clip: AnimationClip; animationAction: AnimationAction; }`

**Calls:**

- `mixer.clipAction`

<details><summary>Code</summary>

```typescript
function createAnimation() {

	const root = new Object3D();
	const mixer = new AnimationMixer( root );
	const track = new NumberKeyframeTrack( '.rotation[x]', [ 0, 1000 ], [ 0, 360 ] );
	const clip = new AnimationClip( 'clip1', 1000, [ track ] );

	const animationAction = mixer.clipAction( clip );
	return {
		root: root,
		mixer: mixer,
		track: track,
		clip: clip,
		animationAction: animationAction
	};

}
```
</details>

### `createTwoAnimations(): { root: Object3D; mixer: AnimationMixer; track: NumberKeyframeTrack; clip: AnimationClip; animationAction: AnimationAction; track2: NumberKeyframeTrack; clip2: AnimationClip; animationAction2: AnimationAction; }`

**Returns:** `{ root: Object3D; mixer: AnimationMixer; track: NumberKeyframeTrack; clip: AnimationClip; animationAction: AnimationAction; track2: NumberKeyframeTrack; clip2: AnimationClip; animationAction2: AnimationAction; }`

**Calls:**

- `mixer.clipAction`

<details><summary>Code</summary>

```typescript
function createTwoAnimations() {

	const root = new Object3D();
	const mixer = new AnimationMixer( root );
	const track = new NumberKeyframeTrack( '.rotation[x]', [ 0, 1000 ], [ 0, 360 ] );
	const clip = new AnimationClip( 'clip1', 1000, [ track ] );
	const animationAction = mixer.clipAction( clip );

	const track2 = new NumberKeyframeTrack( '.rotation[y]', [ 0, 1000 ], [ 0, 360 ] );
	const clip2 = new AnimationClip( 'clip2', 1000, [ track ] );
	const animationAction2 = mixer.clipAction( clip2 );

	return {
		root: root,
		mixer: mixer,
		track: track,
		clip: clip,
		animationAction: animationAction,
		track2: track2,
		clip2: clip2,
		animationAction2: animationAction2
	};

}
```
</details>

### `UserException(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

				this.message = 'AnimationMixer must activate AnimationAction on play.';

			}
```
</details>

### `UserException(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

				this.message = 'AnimationMixer must deactivate AnimationAction on stop.';

			}
```
</details>


---