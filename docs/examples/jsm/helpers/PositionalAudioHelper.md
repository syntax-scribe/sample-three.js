[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PositionalAudioHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/PositionalAudioHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `BufferAttribute` | `three` |
| `LineBasicMaterial` | `three` |
| `Line` | `three` |
| `MathUtils` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `divisions` | `number` | let/var | `divisionsInnerAngle + divisionsOuterAngle * 2` | ✗ |
| `positions` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( ( divisions * 3 + 3 ) * 3 )` | ✗ |
| `materialInnerAngle` | `any` | let/var | `new LineBasicMaterial( { color: 0x00ff00 } )` | ✗ |
| `materialOuterAngle` | `any` | let/var | `new LineBasicMaterial( { color: 0xffff00 } )` | ✗ |
| `audio` | `PositionalAudio` | let/var | `this.audio` | ✗ |
| `range` | `number` | let/var | `this.range` | ✗ |
| `divisionsInnerAngle` | `number` | let/var | `this.divisionsInnerAngle` | ✗ |
| `divisionsOuterAngle` | `number` | let/var | `this.divisionsOuterAngle` | ✗ |
| `halfConeInnerAngle` | `number` | let/var | `coneInnerAngle / 2` | ✗ |
| `halfConeOuterAngle` | `number` | let/var | `coneOuterAngle / 2` | ✗ |
| `start` | `number` | let/var | `0` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `stride` | `any` | let/var | `*not shown*` | ✗ |
| `geometry` | `any` | let/var | `this.geometry` | ✗ |
| `positionAttribute` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `step` | `number` | let/var | `( to - from ) / divisions` | ✗ |


---

## Functions

### `PositionalAudioHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the helper. This method must be called whenever the directional cone
	 * of the positional audio is changed.
	 */
```

**Returns:** `void`

**Calls:**

- `MathUtils.degToRad`
- `geometry.clearGroups`
- `positionAttribute.setXYZ`
- `Math.sin`
- `Math.cos`
- `Math.min`
- `geometry.addGroup`
- `generateSegment`

**Internal Comments:**
```
// (x8)
```

<details><summary>Code</summary>

```typescript
update() {

		const audio = this.audio;
		const range = this.range;
		const divisionsInnerAngle = this.divisionsInnerAngle;
		const divisionsOuterAngle = this.divisionsOuterAngle;

		const coneInnerAngle = MathUtils.degToRad( audio.panner.coneInnerAngle );
		const coneOuterAngle = MathUtils.degToRad( audio.panner.coneOuterAngle );

		const halfConeInnerAngle = coneInnerAngle / 2;
		const halfConeOuterAngle = coneOuterAngle / 2;

		let start = 0;
		let count = 0;
		let i;
		let stride;

		const geometry = this.geometry;
		const positionAttribute = geometry.attributes.position;

		geometry.clearGroups();

		//

		function generateSegment( from, to, divisions, materialIndex ) {

			const step = ( to - from ) / divisions;

			positionAttribute.setXYZ( start, 0, 0, 0 );
			count ++;

			for ( i = from; i < to; i += step ) {

				stride = start + count;

				positionAttribute.setXYZ( stride, Math.sin( i ) * range, 0, Math.cos( i ) * range );
				positionAttribute.setXYZ( stride + 1, Math.sin( Math.min( i + step, to ) ) * range, 0, Math.cos( Math.min( i + step, to ) ) * range );
				positionAttribute.setXYZ( stride + 2, 0, 0, 0 );

				count += 3;

			}

			geometry.addGroup( start, count, materialIndex );

			start += count;
			count = 0;

		}

		//

		generateSegment( - halfConeOuterAngle, - halfConeInnerAngle, divisionsOuterAngle, 0 );
		generateSegment( - halfConeInnerAngle, halfConeInnerAngle, divisionsInnerAngle, 1 );
		generateSegment( halfConeInnerAngle, halfConeOuterAngle, divisionsOuterAngle, 0 );

		//

		positionAttribute.needsUpdate = true;

		if ( coneInnerAngle === coneOuterAngle ) this.material[ 0 ].visible = false;

	}
```
</details>

### `PositionalAudioHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.geometry.dispose`
- `this.material[ 0 ].dispose`
- `this.material[ 1 ].dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.geometry.dispose();
		this.material[ 0 ].dispose();
		this.material[ 1 ].dispose();

	}
```
</details>

### `generateSegment(from: any, to: any, divisions: any, materialIndex: any): void`

**Parameters:**

- **`from`** `any`
- **`to`** `any`
- **`divisions`** `any`
- **`materialIndex`** `any`

**Returns:** `void`

**Calls:**

- `positionAttribute.setXYZ`
- `Math.sin`
- `Math.cos`
- `Math.min`
- `geometry.addGroup`

<details><summary>Code</summary>

```typescript
function generateSegment( from, to, divisions, materialIndex ) {

			const step = ( to - from ) / divisions;

			positionAttribute.setXYZ( start, 0, 0, 0 );
			count ++;

			for ( i = from; i < to; i += step ) {

				stride = start + count;

				positionAttribute.setXYZ( stride, Math.sin( i ) * range, 0, Math.cos( i ) * range );
				positionAttribute.setXYZ( stride + 1, Math.sin( Math.min( i + step, to ) ) * range, 0, Math.cos( Math.min( i + step, to ) ) * range );
				positionAttribute.setXYZ( stride + 2, 0, 0, 0 );

				count += 3;

			}

			geometry.addGroup( start, count, materialIndex );

			start += count;
			count = 0;

		}
```
</details>


---

## Classes

### `PositionalAudioHelper`

<details><summary>Class Code</summary>

```ts
class PositionalAudioHelper extends Line {

	/**
	 * Constructs a new positional audio helper.
	 *
	 * @param {PositionalAudio} audio - The audio to visualize.
	 * @param {number} [range=1] - The range of the directional cone.
	 * @param {number} [divisionsInnerAngle=16] - The number of divisions of the inner part of the directional cone.
	 * @param {number} [divisionsOuterAngle=2] The number of divisions of the outer part of the directional cone.
	 */
	constructor( audio, range = 1, divisionsInnerAngle = 16, divisionsOuterAngle = 2 ) {

		const geometry = new BufferGeometry();
		const divisions = divisionsInnerAngle + divisionsOuterAngle * 2;
		const positions = new Float32Array( ( divisions * 3 + 3 ) * 3 );
		geometry.setAttribute( 'position', new BufferAttribute( positions, 3 ) );

		const materialInnerAngle = new LineBasicMaterial( { color: 0x00ff00 } );
		const materialOuterAngle = new LineBasicMaterial( { color: 0xffff00 } );

		super( geometry, [ materialOuterAngle, materialInnerAngle ] );

		/**
		 * The audio to visualize.
		 *
		 * @type {PositionalAudio}
		 */
		this.audio = audio;

		/**
		 * The range of the directional cone.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.range = range;

		/**
		 * The number of divisions of the inner part of the directional cone.
		 *
		 * @type {number}
		 * @default 16
		 */
		this.divisionsInnerAngle = divisionsInnerAngle;

		/**
		 * The number of divisions of the outer part of the directional cone.
		 *
		 * @type {number}
		 * @default 2
		 */
		this.divisionsOuterAngle = divisionsOuterAngle;

		this.type = 'PositionalAudioHelper';

		this.update();

	}

	/**
	 * Updates the helper. This method must be called whenever the directional cone
	 * of the positional audio is changed.
	 */
	update() {

		const audio = this.audio;
		const range = this.range;
		const divisionsInnerAngle = this.divisionsInnerAngle;
		const divisionsOuterAngle = this.divisionsOuterAngle;

		const coneInnerAngle = MathUtils.degToRad( audio.panner.coneInnerAngle );
		const coneOuterAngle = MathUtils.degToRad( audio.panner.coneOuterAngle );

		const halfConeInnerAngle = coneInnerAngle / 2;
		const halfConeOuterAngle = coneOuterAngle / 2;

		let start = 0;
		let count = 0;
		let i;
		let stride;

		const geometry = this.geometry;
		const positionAttribute = geometry.attributes.position;

		geometry.clearGroups();

		//

		function generateSegment( from, to, divisions, materialIndex ) {

			const step = ( to - from ) / divisions;

			positionAttribute.setXYZ( start, 0, 0, 0 );
			count ++;

			for ( i = from; i < to; i += step ) {

				stride = start + count;

				positionAttribute.setXYZ( stride, Math.sin( i ) * range, 0, Math.cos( i ) * range );
				positionAttribute.setXYZ( stride + 1, Math.sin( Math.min( i + step, to ) ) * range, 0, Math.cos( Math.min( i + step, to ) ) * range );
				positionAttribute.setXYZ( stride + 2, 0, 0, 0 );

				count += 3;

			}

			geometry.addGroup( start, count, materialIndex );

			start += count;
			count = 0;

		}

		//

		generateSegment( - halfConeOuterAngle, - halfConeInnerAngle, divisionsOuterAngle, 0 );
		generateSegment( - halfConeInnerAngle, halfConeInnerAngle, divisionsInnerAngle, 1 );
		generateSegment( halfConeInnerAngle, halfConeOuterAngle, divisionsOuterAngle, 0 );

		//

		positionAttribute.needsUpdate = true;

		if ( coneInnerAngle === coneOuterAngle ) this.material[ 0 ].visible = false;

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.geometry.dispose();
		this.material[ 0 ].dispose();
		this.material[ 1 ].dispose();

	}

}
```
</details>

#### Methods

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const audio = this.audio;
		const range = this.range;
		const divisionsInnerAngle = this.divisionsInnerAngle;
		const divisionsOuterAngle = this.divisionsOuterAngle;

		const coneInnerAngle = MathUtils.degToRad( audio.panner.coneInnerAngle );
		const coneOuterAngle = MathUtils.degToRad( audio.panner.coneOuterAngle );

		const halfConeInnerAngle = coneInnerAngle / 2;
		const halfConeOuterAngle = coneOuterAngle / 2;

		let start = 0;
		let count = 0;
		let i;
		let stride;

		const geometry = this.geometry;
		const positionAttribute = geometry.attributes.position;

		geometry.clearGroups();

		//

		function generateSegment( from, to, divisions, materialIndex ) {

			const step = ( to - from ) / divisions;

			positionAttribute.setXYZ( start, 0, 0, 0 );
			count ++;

			for ( i = from; i < to; i += step ) {

				stride = start + count;

				positionAttribute.setXYZ( stride, Math.sin( i ) * range, 0, Math.cos( i ) * range );
				positionAttribute.setXYZ( stride + 1, Math.sin( Math.min( i + step, to ) ) * range, 0, Math.cos( Math.min( i + step, to ) ) * range );
				positionAttribute.setXYZ( stride + 2, 0, 0, 0 );

				count += 3;

			}

			geometry.addGroup( start, count, materialIndex );

			start += count;
			count = 0;

		}

		//

		generateSegment( - halfConeOuterAngle, - halfConeInnerAngle, divisionsOuterAngle, 0 );
		generateSegment( - halfConeInnerAngle, halfConeInnerAngle, divisionsInnerAngle, 1 );
		generateSegment( halfConeInnerAngle, halfConeOuterAngle, divisionsOuterAngle, 0 );

		//

		positionAttribute.needsUpdate = true;

		if ( coneInnerAngle === coneOuterAngle ) this.material[ 0 ].visible = false;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.geometry.dispose();
		this.material[ 0 ].dispose();
		this.material[ 1 ].dispose();

	}
```
</details>


---