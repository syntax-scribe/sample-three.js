[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `potpack.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/libs/potpack.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `area` | `number` | let/var | `0` | ✗ |
| `maxWidth` | `number` | let/var | `0` | ✗ |
| `spaces` | `{ x: number; y: number; w: number; h:...` | let/var | `[{x: 0, y: 0, w: startWidth, h: Infinity}]` | ✗ |
| `width` | `number` | let/var | `0` | ✗ |
| `height` | `number` | let/var | `0` | ✗ |
| `space` | `{ x: number; y: number; w: number; h:...` | let/var | `spaces[i]` | ✗ |


---

## Functions

### `potpack(boxes: any): { w: number; h: number; fill: number; }`

**JSDoc:**
```typescript
/**
 * potpack - by [@mourner](https://github.com/mourner)
 * 
 * A tiny JavaScript function for packing 2D rectangles into a near-square container, 
 * which is useful for generating CSS sprites and WebGL textures. Similar to 
 * [shelf-pack](https://github.com/mapbox/shelf-pack), but static (you can't add items 
 * once a layout is generated), and aims for maximal space utilization.
 *
 * A variation of algorithms used in [rectpack2D](https://github.com/TeamHypersomnia/rectpack2D)
 * and [bin-pack](https://github.com/bryanburgers/bin-pack), which are in turn based 
 * on [this article by Blackpawn](http://blackpawn.com/texts/lightmaps/default.html).
 * 
 * @license
 * ISC License
 * 
 * Copyright (c) 2018, Mapbox
 * 
 * Permission to use, copy, modify, and/or distribute this software for any purpose
 * with or without fee is hereby granted, provided that the above copyright notice
 * and this permission notice appear in all copies.
 * 
 * THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH
 * REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND
 * FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT,
 * INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS
 * OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER
 * TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF
 * THIS SOFTWARE.
 */
```

**Parameters:**

- **`boxes`** `any`

**Returns:** `{ w: number; h: number; fill: number; }`

**Calls:**

- `Math.max`
- `boxes.sort`
- `Math.ceil`
- `Math.sqrt`
- `spaces.pop`
- `spaces.push`

**Internal Comments:**
```
// calculate total box area and maximum box width (x2)
// sort the boxes for insertion by height, descending (x4)
// aim for a squarish resulting container, (x2)
// slightly adjusted for sub-100% space utilization (x2)
// start with a single empty space, unbounded at the bottom (x2)
// look through spaces backwards so that we check smaller spaces first
// look for empty spaces that can accommodate the current box
// found the space; add the box to its top-left corner (x4)
// |-------|-------| (x4)
// |  box  |       | (x4)
// |_______|       | (x4)
// |         space | (x4)
// |_______________| (x12)
// space matches the box exactly; remove it (x2)
// space matches the box height; update it accordingly (x4)
// |-------|---------------| (x4)
// |  box  | updated space | (x4)
// |_______|_______________| (x4)
// space matches the box width; update it accordingly (x4)
// |---------------| (x4)
// |      box      | (x4)
// | updated space | (x4)
// otherwise the box splits the space into two spaces (x4)
// |-------|-----------| (x4)
// |  box  | new space | (x4)
// |_______|___________| (x4)
// | updated space     | (x4)
// |___________________| (x4)
```

<details><summary>Code</summary>

```typescript
function potpack(boxes) {

	// calculate total box area and maximum box width
	let area = 0;
	let maxWidth = 0;
	
	for (const box of boxes) {
		area += box.w * box.h;
		maxWidth = Math.max(maxWidth, box.w);
	}
	
	// sort the boxes for insertion by height, descending
	boxes.sort((a, b) => b.h - a.h);
	
	// aim for a squarish resulting container,
	// slightly adjusted for sub-100% space utilization
	const startWidth = Math.max(Math.ceil(Math.sqrt(area / 0.95)), maxWidth);
	
	// start with a single empty space, unbounded at the bottom
	const spaces = [{x: 0, y: 0, w: startWidth, h: Infinity}];
	
	let width = 0;
	let height = 0;
	
	for (const box of boxes) {
		// look through spaces backwards so that we check smaller spaces first
		for (let i = spaces.length - 1; i >= 0; i--) {
			const space = spaces[i];
			
			// look for empty spaces that can accommodate the current box
			if (box.w > space.w || box.h > space.h) continue;
			
			// found the space; add the box to its top-left corner
			// |-------|-------|
			// |  box  |       |
			// |_______|       |
			// |         space |
			// |_______________|
			box.x = space.x;
			box.y = space.y;
			
			height = Math.max(height, box.y + box.h);
			width = Math.max(width, box.x + box.w);
			
			if (box.w === space.w && box.h === space.h) {
				// space matches the box exactly; remove it
				const last = spaces.pop();
				if (i < spaces.length) spaces[i] = last;
			
			} else if (box.h === space.h) {
				// space matches the box height; update it accordingly
				// |-------|---------------|
				// |  box  | updated space |
				// |_______|_______________|
				space.x += box.w;
				space.w -= box.w;
			
			} else if (box.w === space.w) {
				// space matches the box width; update it accordingly
				// |---------------|
				// |      box      |
				// |_______________|
				// | updated space |
				// |_______________|
				space.y += box.h;
				space.h -= box.h;
			
			} else {
				// otherwise the box splits the space into two spaces
				// |-------|-----------|
				// |  box  | new space |
				// |_______|___________|
				// | updated space     |
				// |___________________|
				spaces.push({
					x: space.x + box.w,
					y: space.y,
					w: space.w - box.w,
					h: box.h
				});
				space.y += box.h;
				space.h -= box.h;
			}
			break;
		}
	}
	
	return {
		w: width, // container width
		h: height, // container height
		fill: (area / (width * height)) || 0 // space utilization
	};
}
```
</details>


---