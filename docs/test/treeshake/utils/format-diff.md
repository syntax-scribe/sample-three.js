[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `format-diff.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`test/treeshake/utils/format-diff.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `formatBytes` | `./formatBytes.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `diff` | `number` | let/var | `filesize - filesizeBase` | ✗ |
| `formatted` | `string` | let/var | ``${diff >= 0 ? '+' : '-'}${formatBytes( Math.abs( diff ), 2 )}`` | ✗ |


---