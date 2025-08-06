[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StringKeyframeTrack.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/animation/tracks/StringKeyframeTrack.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InterpolateDiscrete` | `../../constants.js` |
| `KeyframeTrack` | `../KeyframeTrack.js` |


---

## Classes

### `StringKeyframeTrack`

<details><summary>Class Code</summary>

```ts
class StringKeyframeTrack extends KeyframeTrack {

	/**
	 * Constructs a new string keyframe track.
	 *
	 * This keyframe track type has no `interpolation` parameter because the
	 * interpolation is always discrete.
	 *
	 * @param {string} name - The keyframe track's name.
	 * @param {Array<number>} times - A list of keyframe times.
	 * @param {Array<string>} values - A list of keyframe values.
	 */
	constructor( name, times, values ) {

		super( name, times, values );

	}

}
```
</details>


---