[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BooleanKeyframeTrack.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/animation/tracks/BooleanKeyframeTrack.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InterpolateDiscrete` | `../../constants.js` |
| `KeyframeTrack` | `../KeyframeTrack.js` |


---

## Classes

### `BooleanKeyframeTrack`

<details><summary>Class Code</summary>

```ts
class BooleanKeyframeTrack extends KeyframeTrack {

	/**
	 * Constructs a new boolean keyframe track.
	 *
	 * This keyframe track type has no `interpolation` parameter because the
	 * interpolation is always discrete.
	 *
	 * @param {string} name - The keyframe track's name.
	 * @param {Array<number>} times - A list of keyframe times.
	 * @param {Array<boolean>} values - A list of keyframe values.
	 */
	constructor( name, times, values ) {

		super( name, times, values );

	}

}
```
</details>


---