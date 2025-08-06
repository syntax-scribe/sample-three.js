[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Color.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 5 |
| 📊 Variables & Constants | 94 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`test/unit/src/math/Color.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `../../../../src/math/Color.js` |
| `ColorManagement` | `../../../../src/math/ColorManagement.js` |
| `eps` | `../../utils/math-constants.js` |
| `CONSOLE_LEVEL` | `../../utils/console-wrapper.js` |
| `SRGBColorSpace` | `../../../../src/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `colorManagementEnabled` | `boolean` | let/var | `ColorManagement.enabled` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `a` | `Color` | let/var | `new Color()` | ✗ |
| `b` | `Object` | let/var | `new Object()` | ✗ |
| `a` | `Color` | let/var | `new Color()` | ✗ |
| `b` | `Color` | let/var | `new Color( 0.5, 0, 0 )` | ✗ |
| `c` | `Color` | let/var | `new Color( 0xFF0000 )` | ✗ |
| `d` | `Color` | let/var | `new Color( 0, 1.0, 0 )` | ✗ |
| `e` | `Color` | let/var | `new Color( 0.5, 0.5, 0.5 )` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `hsl` | `{ h: number; s: number; l: number; }` | let/var | `{ h: 0, s: 0, l: 0 }` | ✗ |
| `a` | `Color` | let/var | `new Color()` | ✗ |
| `b` | `Color` | let/var | `new Color( 8 / 255, 25 / 255, 178 / 255 )` | ✗ |
| `hsl` | `{ h: number; s: number; l: number; }` | let/var | `{ h: 0, s: 0, l: 0 }` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color( 'teal' )` | ✗ |
| `a` | `Color` | let/var | `new Color( 'teal' )` | ✗ |
| `b` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c2` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c2` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color( 'red' )` | ✗ |
| `c` | `Color` | let/var | `new Color( 'tomato' )` | ✗ |
| `c` | `Color` | let/var | `new Color( 0x80ffff )` | ✗ |
| `hsl` | `{ h: number; s: number; l: number; }` | let/var | `{ h: 0, s: 0, l: 0 }` | ✗ |
| `c` | `Color` | let/var | `new Color( 'plum' )` | ✗ |
| `t` | `{ r: number; g: number; b: number; }` | let/var | `{ r: 0, g: 0, b: 0 }` | ✗ |
| `c` | `Color` | let/var | `new Color( 'plum' )` | ✗ |
| `a` | `Color` | let/var | `new Color( 'hsl(120,50%,50%)' )` | ✗ |
| `b` | `Color` | let/var | `new Color( 0.36, 0.84, 0.648 )` | ✗ |
| `a` | `Color` | let/var | `new Color( 0x0000FF )` | ✗ |
| `b` | `Color` | let/var | `new Color( 0xFF0000 )` | ✗ |
| `c` | `Color` | let/var | `new Color( 0xFF00FF )` | ✗ |
| `a` | `Color` | let/var | `new Color( 0x0000FF )` | ✗ |
| `b` | `Color` | let/var | `new Color( 0xFF0000 )` | ✗ |
| `c` | `Color` | let/var | `new Color( 0xFF00FF )` | ✗ |
| `d` | `Color` | let/var | `new Color()` | ✗ |
| `a` | `Color` | let/var | `new Color( 0.1, 0.0, 0.0 )` | ✗ |
| `b` | `Color` | let/var | `new Color( 0.6, 0.5, 0.5 )` | ✗ |
| `a` | `Color` | let/var | `new Color( 0x0000CC )` | ✗ |
| `b` | `Color` | let/var | `new Color( 0xFF0000 )` | ✗ |
| `c` | `Color` | let/var | `new Color( 0x0000AA )` | ✗ |
| `a` | `Color` | let/var | `new Color( 1, 0, 0.5 )` | ✗ |
| `b` | `Color` | let/var | `new Color( 0.5, 1, 0.5 )` | ✗ |
| `c` | `Color` | let/var | `new Color( 0.5, 0, 0.25 )` | ✗ |
| `a` | `Color` | let/var | `new Color( 0.25, 0, 0.5 )` | ✗ |
| `b` | `Color` | let/var | `new Color( 0.5, 0, 1 )` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c2` | `Color` | let/var | `new Color()` | ✗ |
| `a` | `Color` | let/var | `new Color( 0.5, 0.0, 1.0 )` | ✗ |
| `b` | `Color` | let/var | `new Color( 0.5, 1.0, 0.0 )` | ✗ |
| `a` | `Color` | let/var | `new Color()` | ✗ |
| `array` | `number[]` | let/var | `[ 0.5, 0.6, 0.7, 0, 1, 0 ]` | ✗ |
| `r` | `0.5` | let/var | `0.5` | ✗ |
| `g` | `1` | let/var | `1.0` | ✗ |
| `b` | `0` | let/var | `0.0` | ✗ |
| `a` | `Color` | let/var | `new Color( r, g, b )` | ✗ |
| `a` | `Color` | let/var | `new Color( 0.0, 0.0, 0.0 )` | ✗ |
| `b` | `Color` | let/var | `new Color( 0.0, 0.5, 0.0 )` | ✗ |
| `c` | `Color` | let/var | `new Color( 1.0, 0.0, 0.0 )` | ✗ |
| `d` | `Color` | let/var | `new Color( 1.0, 1.0, 1.0 )` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c2` | `Color` | let/var | `new Color( 0xF5FFFA )` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c2` | `Color` | let/var | `new Color( 'ivory' )` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color()` | ✗ |
| `c` | `Color` | let/var | `new Color( 0.5, 0.75, 1 )` | ✗ |
| `array` | `number[]` | let/var | `[ ...c ]` | ✗ |


---