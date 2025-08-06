[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NumberKeyframeTrack.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/animation/tracks/NumberKeyframeTrack.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `KeyframeTrack` | `../KeyframeTrack.js` |


---

## Classes

### `NumberKeyframeTrack`

<details><summary>Class Code</summary>

```ts
class NumberKeyframeTrack extends KeyframeTrack {

	/**
	 * Constructs a new number keyframe track.
	 *
	 * @param {string} name - The keyframe track's name.
	 * @param {Array<number>} times - A list of keyframe times.
	 * @param {Array<number>} values - A list of keyframe values.
	 * @param {(InterpolateLinear|InterpolateDiscrete|InterpolateSmooth)} [interpolation] - The interpolation type.
	 */
	constructor( name, times, values, interpolation ) {

		super( name, times, values, interpolation );

	}

}
```
</details>


---