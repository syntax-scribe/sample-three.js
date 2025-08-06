[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `KeyframeTrack.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 3 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`test/unit/src/animation/KeyframeTrack.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NumberKeyframeTrack` | `../../../../src/animation/tracks/NumberKeyframeTrack.js` |
| `KeyframeTrack` | `../../../../src/animation/KeyframeTrack.js` |
| `CONSOLE_LEVEL` | `../../utils/console-wrapper.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `parameters` | `{ name: string; times: number[]; valu...` | let/var | `{ name: '.material.opacity', times: [ 0, 1 ], values: [ 0, 0.5 ], interpolati...` | ✗ |
| `object` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( parameters.name, parameters.times, parameters.values )` | ✗ |
| `object` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( parameters.name, parameters.times, parameters.values )` | ✗ |
| `object_all` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( parameters.name, parameters.times, parameters.values...` | ✗ |
| `validTrack` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( '.material.opacity', [ 0, 1 ], [ 0, 0.5 ] )` | ✗ |
| `invalidTrack` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( '.material.opacity', [ 0, 1 ], [ 0, NaN ] )` | ✗ |
| `track` | `NumberKeyframeTrack` | let/var | `new NumberKeyframeTrack( '.material.opacity', [ 0, 1, 2, 3, 4 ], [ 0, 0, 0, 0...` | ✗ |


---