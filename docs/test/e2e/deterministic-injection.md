[⬅️ Back to Table of Contents](../../index.md)

# 📄 `deterministic-injection.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/e2e/deterministic-injection.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `seed` | `number` | let/var | `Math.PI / 4` | ✗ |
| `x` | `number` | let/var | `Math.sin( seed ++ ) * 10000` | ✗ |
| `frameId` | `number` | let/var | `0` | ✗ |
| `RAF` | `((callback: FrameRequestCallback) => ...` | let/var | `window.requestAnimationFrame` | ✗ |
| `maxFrameId` | `2` | let/var | `2` | ✗ |
| `play` | `() => Promise<void>` | let/var | `HTMLVideoElement.prototype.play` | ✗ |


---

## Functions

### `now(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
() => frameId * 16
```
</details>

### `renew(): void`

**Returns:** `void`

**Calls:**

- `this.load`
- `play.call`
- `RAF`

<details><summary>Code</summary>

```typescript
function renew() {

			this.load();
			play.call( this );
			RAF( renew );

		}
```
</details>


---