[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MorphBlendMesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 30 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/misc/MorphBlendMesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `MathUtils` | `three` |
| `Mesh` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `numFrames` | `number` | let/var | `Object.keys( this.morphTargetDictionary ).length` | ✗ |
| `name` | `"__default"` | let/var | `'__default'` | ✗ |
| `startFrame` | `0` | let/var | `0` | ✗ |
| `endFrame` | `number` | let/var | `numFrames - 1` | ✗ |
| `fps` | `number` | let/var | `numFrames / 1` | ✗ |
| `animation` | `{ start: number; end: number; length:...` | let/var | `{ start: start, end: end, length: end - start + 1, fps: fps, duration: ( end ...` | ✗ |
| `pattern` | `RegExp` | let/var | `/([a-z]+)_?(\d+)/i` | ✗ |
| `firstAnimation` | `any` | let/var | `*not shown*` | ✗ |
| `frameRanges` | `{}` | let/var | `{}` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `name` | `string` | let/var | `chunks[ 1 ]` | ✗ |
| `range` | `any` | let/var | `frameRanges[ name ]` | ✗ |
| `range` | `any` | let/var | `frameRanges[ name ]` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `time` | `number` | let/var | `0` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `duration` | `number` | let/var | `- 1` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `animation` | `any` | let/var | `this.animationsMap[ name ]` | ✗ |
| `animation` | `any` | let/var | `this.animationsList[ i ]` | ✗ |
| `frameTime` | `number` | let/var | `animation.duration / animation.length` | ✗ |
| `keyframe` | `any` | let/var | `animation.start + MathUtils.clamp( Math.floor( animation.time / frameTime ), ...` | ✗ |
| `weight` | `any` | let/var | `animation.weight` | ✗ |
| `mix` | `number` | let/var | `( animation.time % frameTime ) / frameTime` | ✗ |


---

## Functions

### `MorphBlendMesh.createAnimation(name: string, start: number, end: number, fps: number): void`

**JSDoc:**
```typescript
/**
	 * Creates a new animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} start - The start time.
	 * @param {number} end - The end time.
	 * @param {number} fps - The FPS.
	 */
```

**Parameters:**

- **`name`** `string`
- **`start`** `number`
- **`end`** `number`
- **`fps`** `number`

**Returns:** `void`

**Calls:**

- `this.animationsList.push`

<details><summary>Code</summary>

```typescript
createAnimation( name, start, end, fps ) {

		const animation = {

			start: start,
			end: end,

			length: end - start + 1,

			fps: fps,
			duration: ( end - start ) / fps,

			lastFrame: 0,
			currentFrame: 0,

			active: false,

			time: 0,
			direction: 1,
			weight: 1,

			directionBackwards: false,
			mirroredLoop: false

		};

		this.animationsMap[ name ] = animation;
		this.animationsList.push( animation );

	}
```
</details>

### `MorphBlendMesh.autoCreateAnimations(fps: number): void`

**JSDoc:**
```typescript
/**
	 * Automatically creates animations based on the values in
	 * {@link Mesh#morphTargetDictionary}.
	 *
	 * @param {number} fps - The FPS of all animations.
	 */
```

**Parameters:**

- **`fps`** `number`

**Returns:** `void`

**Calls:**

- `key.match`
- `this.createAnimation`

<details><summary>Code</summary>

```typescript
autoCreateAnimations( fps ) {

		const pattern = /([a-z]+)_?(\d+)/i;

		let firstAnimation;

		const frameRanges = {};

		let i = 0;

		for ( const key in this.morphTargetDictionary ) {

			const chunks = key.match( pattern );

			if ( chunks && chunks.length > 1 ) {

				const name = chunks[ 1 ];

				if ( ! frameRanges[ name ] ) frameRanges[ name ] = { start: Infinity, end: - Infinity };

				const range = frameRanges[ name ];

				if ( i < range.start ) range.start = i;
				if ( i > range.end ) range.end = i;

				if ( ! firstAnimation ) firstAnimation = name;

			}

			i ++;

		}

		for ( const name in frameRanges ) {

			const range = frameRanges[ name ];
			this.createAnimation( name, range.start, range.end, fps );

		}

		this.firstAnimation = firstAnimation;

	}
```
</details>

### `MorphBlendMesh.setAnimationDirectionForward(name: string): void`

**JSDoc:**
```typescript
/**
	 * Sets the animation playback direction to "forward" for the
	 * defined animation.
	 *
	 * @param {string} name - The animation name.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setAnimationDirectionForward( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.direction = 1;
			animation.directionBackwards = false;

		}

	}
```
</details>

### `MorphBlendMesh.setAnimationDirectionBackward(name: string): void`

**JSDoc:**
```typescript
/**
	 * Sets the animation playback direction to "backward" for the
	 * defined animation.
	 *
	 * @param {string} name - The animation name.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setAnimationDirectionBackward( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.direction = - 1;
			animation.directionBackwards = true;

		}

	}
```
</details>

### `MorphBlendMesh.setAnimationFPS(name: string, fps: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the FPS to the given value for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} fps - The FPS to set.
	 */
```

**Parameters:**

- **`name`** `string`
- **`fps`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setAnimationFPS( name, fps ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.fps = fps;
			animation.duration = ( animation.end - animation.start ) / animation.fps;

		}

	}
```
</details>

### `MorphBlendMesh.setAnimationDuration(name: string, duration: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the duration to the given value for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} duration - The duration to set.
	 */
```

**Parameters:**

- **`name`** `string`
- **`duration`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setAnimationDuration( name, duration ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.duration = duration;
			animation.fps = ( animation.end - animation.start ) / animation.duration;

		}

	}
```
</details>

### `MorphBlendMesh.setAnimationWeight(name: string, weight: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the weight to the given value for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} weight - The weight to set.
	 */
```

**Parameters:**

- **`name`** `string`
- **`weight`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setAnimationWeight( name, weight ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.weight = weight;

		}

	}
```
</details>

### `MorphBlendMesh.setAnimationTime(name: string, time: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the time to the given value for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} time - The time to set.
	 */
```

**Parameters:**

- **`name`** `string`
- **`time`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setAnimationTime( name, time ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.time = time;

		}

	}
```
</details>

### `MorphBlendMesh.getAnimationTime(name: string): number`

**JSDoc:**
```typescript
/**
	 * Returns the time for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @return {number} The time.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getAnimationTime( name ) {

		let time = 0;

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			time = animation.time;

		}

		return time;

	}
```
</details>

### `MorphBlendMesh.getAnimationDuration(name: string): number`

**JSDoc:**
```typescript
/**
	 * Returns the duration for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @return {number} The duration.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getAnimationDuration( name ) {

		let duration = - 1;

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			duration = animation.duration;

		}

		return duration;

	}
```
</details>

### `MorphBlendMesh.playAnimation(name: string): void`

**JSDoc:**
```typescript
/**
	 * Plays the defined animation.
	 *
	 * @param {string} name - The animation name.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
playAnimation( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.time = 0;
			animation.active = true;

		} else {

			console.warn( 'THREE.MorphBlendMesh: animation[' + name + '] undefined in .playAnimation()' );

		}

	}
```
</details>

### `MorphBlendMesh.stopAnimation(name: string): void`

**JSDoc:**
```typescript
/**
	 * Stops the defined animation.
	 *
	 * @param {string} name - The animation name.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
stopAnimation( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.active = false;

		}

	}
```
</details>

### `MorphBlendMesh.update(delta: number): void`

**JSDoc:**
```typescript
/**
	 * Updates the animations of the mesh.
	 *
	 * @param {number} delta - The delta time in seconds.
	 */
```

**Parameters:**

- **`delta`** `number`

**Returns:** `void`

**Calls:**

- `MathUtils.clamp`
- `Math.floor`

<details><summary>Code</summary>

```typescript
update( delta ) {

		for ( let i = 0, il = this.animationsList.length; i < il; i ++ ) {

			const animation = this.animationsList[ i ];

			if ( ! animation.active ) continue;

			const frameTime = animation.duration / animation.length;

			animation.time += animation.direction * delta;

			if ( animation.mirroredLoop ) {

				if ( animation.time > animation.duration || animation.time < 0 ) {

					animation.direction *= - 1;

					if ( animation.time > animation.duration ) {

						animation.time = animation.duration;
						animation.directionBackwards = true;

					}

					if ( animation.time < 0 ) {

						animation.time = 0;
						animation.directionBackwards = false;

					}

				}

			} else {

				animation.time = animation.time % animation.duration;

				if ( animation.time < 0 ) animation.time += animation.duration;

			}

			const keyframe = animation.start + MathUtils.clamp( Math.floor( animation.time / frameTime ), 0, animation.length - 1 );
			const weight = animation.weight;

			if ( keyframe !== animation.currentFrame ) {

				this.morphTargetInfluences[ animation.lastFrame ] = 0;
				this.morphTargetInfluences[ animation.currentFrame ] = 1 * weight;

				this.morphTargetInfluences[ keyframe ] = 0;

				animation.lastFrame = animation.currentFrame;
				animation.currentFrame = keyframe;

			}

			let mix = ( animation.time % frameTime ) / frameTime;

			if ( animation.directionBackwards ) mix = 1 - mix;

			if ( animation.currentFrame !== animation.lastFrame ) {

				this.morphTargetInfluences[ animation.currentFrame ] = mix * weight;
				this.morphTargetInfluences[ animation.lastFrame ] = ( 1 - mix ) * weight;

			} else {

				this.morphTargetInfluences[ animation.currentFrame ] = weight;

			}

		}

	}
```
</details>


---

## Classes

### `MorphBlendMesh`

<details><summary>Class Code</summary>

```ts
class MorphBlendMesh extends Mesh {

	/**
	 * Constructs a new morph blend mesh.
	 *
	 * @param {BufferGeometry} [geometry] - The mesh geometry.
	 * @param {Material|Array<Material>} [material] - The mesh material.
	 */
	constructor( geometry, material ) {

		super( geometry, material );

		/**
		 * A dictionary of animations.
		 *
		 * @type {Object<string,Object>}
		 */
		this.animationsMap = {};

		/**
		 * A list of animations.
		 *
		 * @type {Array<Object>}
		 */
		this.animationsList = [];

		// prepare default animation
		// (all frames played together in 1 second)

		const numFrames = Object.keys( this.morphTargetDictionary ).length;

		const name = '__default';

		const startFrame = 0;
		const endFrame = numFrames - 1;

		const fps = numFrames / 1;

		this.createAnimation( name, startFrame, endFrame, fps );
		this.setAnimationWeight( name, 1 );

	}

	/**
	 * Creates a new animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} start - The start time.
	 * @param {number} end - The end time.
	 * @param {number} fps - The FPS.
	 */
	createAnimation( name, start, end, fps ) {

		const animation = {

			start: start,
			end: end,

			length: end - start + 1,

			fps: fps,
			duration: ( end - start ) / fps,

			lastFrame: 0,
			currentFrame: 0,

			active: false,

			time: 0,
			direction: 1,
			weight: 1,

			directionBackwards: false,
			mirroredLoop: false

		};

		this.animationsMap[ name ] = animation;
		this.animationsList.push( animation );

	}

	/**
	 * Automatically creates animations based on the values in
	 * {@link Mesh#morphTargetDictionary}.
	 *
	 * @param {number} fps - The FPS of all animations.
	 */
	autoCreateAnimations( fps ) {

		const pattern = /([a-z]+)_?(\d+)/i;

		let firstAnimation;

		const frameRanges = {};

		let i = 0;

		for ( const key in this.morphTargetDictionary ) {

			const chunks = key.match( pattern );

			if ( chunks && chunks.length > 1 ) {

				const name = chunks[ 1 ];

				if ( ! frameRanges[ name ] ) frameRanges[ name ] = { start: Infinity, end: - Infinity };

				const range = frameRanges[ name ];

				if ( i < range.start ) range.start = i;
				if ( i > range.end ) range.end = i;

				if ( ! firstAnimation ) firstAnimation = name;

			}

			i ++;

		}

		for ( const name in frameRanges ) {

			const range = frameRanges[ name ];
			this.createAnimation( name, range.start, range.end, fps );

		}

		this.firstAnimation = firstAnimation;

	}

	/**
	 * Sets the animation playback direction to "forward" for the
	 * defined animation.
	 *
	 * @param {string} name - The animation name.
	 */
	setAnimationDirectionForward( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.direction = 1;
			animation.directionBackwards = false;

		}

	}

	/**
	 * Sets the animation playback direction to "backward" for the
	 * defined animation.
	 *
	 * @param {string} name - The animation name.
	 */
	setAnimationDirectionBackward( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.direction = - 1;
			animation.directionBackwards = true;

		}

	}

	/**
	 * Sets the FPS to the given value for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} fps - The FPS to set.
	 */
	setAnimationFPS( name, fps ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.fps = fps;
			animation.duration = ( animation.end - animation.start ) / animation.fps;

		}

	}

	/**
	 * Sets the duration to the given value for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} duration - The duration to set.
	 */
	setAnimationDuration( name, duration ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.duration = duration;
			animation.fps = ( animation.end - animation.start ) / animation.duration;

		}

	}

	/**
	 * Sets the weight to the given value for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} weight - The weight to set.
	 */
	setAnimationWeight( name, weight ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.weight = weight;

		}

	}

	/**
	 * Sets the time to the given value for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @param {number} time - The time to set.
	 */
	setAnimationTime( name, time ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.time = time;

		}

	}

	/**
	 * Returns the time for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @return {number} The time.
	 */
	getAnimationTime( name ) {

		let time = 0;

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			time = animation.time;

		}

		return time;

	}

	/**
	 * Returns the duration for the defined animation.
	 *
	 * @param {string} name - The animation name.
	 * @return {number} The duration.
	 */
	getAnimationDuration( name ) {

		let duration = - 1;

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			duration = animation.duration;

		}

		return duration;

	}

	/**
	 * Plays the defined animation.
	 *
	 * @param {string} name - The animation name.
	 */
	playAnimation( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.time = 0;
			animation.active = true;

		} else {

			console.warn( 'THREE.MorphBlendMesh: animation[' + name + '] undefined in .playAnimation()' );

		}

	}

	/**
	 * Stops the defined animation.
	 *
	 * @param {string} name - The animation name.
	 */
	stopAnimation( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.active = false;

		}

	}

	/**
	 * Updates the animations of the mesh.
	 *
	 * @param {number} delta - The delta time in seconds.
	 */
	update( delta ) {

		for ( let i = 0, il = this.animationsList.length; i < il; i ++ ) {

			const animation = this.animationsList[ i ];

			if ( ! animation.active ) continue;

			const frameTime = animation.duration / animation.length;

			animation.time += animation.direction * delta;

			if ( animation.mirroredLoop ) {

				if ( animation.time > animation.duration || animation.time < 0 ) {

					animation.direction *= - 1;

					if ( animation.time > animation.duration ) {

						animation.time = animation.duration;
						animation.directionBackwards = true;

					}

					if ( animation.time < 0 ) {

						animation.time = 0;
						animation.directionBackwards = false;

					}

				}

			} else {

				animation.time = animation.time % animation.duration;

				if ( animation.time < 0 ) animation.time += animation.duration;

			}

			const keyframe = animation.start + MathUtils.clamp( Math.floor( animation.time / frameTime ), 0, animation.length - 1 );
			const weight = animation.weight;

			if ( keyframe !== animation.currentFrame ) {

				this.morphTargetInfluences[ animation.lastFrame ] = 0;
				this.morphTargetInfluences[ animation.currentFrame ] = 1 * weight;

				this.morphTargetInfluences[ keyframe ] = 0;

				animation.lastFrame = animation.currentFrame;
				animation.currentFrame = keyframe;

			}

			let mix = ( animation.time % frameTime ) / frameTime;

			if ( animation.directionBackwards ) mix = 1 - mix;

			if ( animation.currentFrame !== animation.lastFrame ) {

				this.morphTargetInfluences[ animation.currentFrame ] = mix * weight;
				this.morphTargetInfluences[ animation.lastFrame ] = ( 1 - mix ) * weight;

			} else {

				this.morphTargetInfluences[ animation.currentFrame ] = weight;

			}

		}

	}

}
```
</details>

#### Methods

##### `createAnimation(name: string, start: number, end: number, fps: number): void`

<details><summary>Code</summary>

```ts
createAnimation( name, start, end, fps ) {

		const animation = {

			start: start,
			end: end,

			length: end - start + 1,

			fps: fps,
			duration: ( end - start ) / fps,

			lastFrame: 0,
			currentFrame: 0,

			active: false,

			time: 0,
			direction: 1,
			weight: 1,

			directionBackwards: false,
			mirroredLoop: false

		};

		this.animationsMap[ name ] = animation;
		this.animationsList.push( animation );

	}
```
</details>

##### `autoCreateAnimations(fps: number): void`

<details><summary>Code</summary>

```ts
autoCreateAnimations( fps ) {

		const pattern = /([a-z]+)_?(\d+)/i;

		let firstAnimation;

		const frameRanges = {};

		let i = 0;

		for ( const key in this.morphTargetDictionary ) {

			const chunks = key.match( pattern );

			if ( chunks && chunks.length > 1 ) {

				const name = chunks[ 1 ];

				if ( ! frameRanges[ name ] ) frameRanges[ name ] = { start: Infinity, end: - Infinity };

				const range = frameRanges[ name ];

				if ( i < range.start ) range.start = i;
				if ( i > range.end ) range.end = i;

				if ( ! firstAnimation ) firstAnimation = name;

			}

			i ++;

		}

		for ( const name in frameRanges ) {

			const range = frameRanges[ name ];
			this.createAnimation( name, range.start, range.end, fps );

		}

		this.firstAnimation = firstAnimation;

	}
```
</details>

##### `setAnimationDirectionForward(name: string): void`

<details><summary>Code</summary>

```ts
setAnimationDirectionForward( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.direction = 1;
			animation.directionBackwards = false;

		}

	}
```
</details>

##### `setAnimationDirectionBackward(name: string): void`

<details><summary>Code</summary>

```ts
setAnimationDirectionBackward( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.direction = - 1;
			animation.directionBackwards = true;

		}

	}
```
</details>

##### `setAnimationFPS(name: string, fps: number): void`

<details><summary>Code</summary>

```ts
setAnimationFPS( name, fps ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.fps = fps;
			animation.duration = ( animation.end - animation.start ) / animation.fps;

		}

	}
```
</details>

##### `setAnimationDuration(name: string, duration: number): void`

<details><summary>Code</summary>

```ts
setAnimationDuration( name, duration ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.duration = duration;
			animation.fps = ( animation.end - animation.start ) / animation.duration;

		}

	}
```
</details>

##### `setAnimationWeight(name: string, weight: number): void`

<details><summary>Code</summary>

```ts
setAnimationWeight( name, weight ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.weight = weight;

		}

	}
```
</details>

##### `setAnimationTime(name: string, time: number): void`

<details><summary>Code</summary>

```ts
setAnimationTime( name, time ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.time = time;

		}

	}
```
</details>

##### `getAnimationTime(name: string): number`

<details><summary>Code</summary>

```ts
getAnimationTime( name ) {

		let time = 0;

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			time = animation.time;

		}

		return time;

	}
```
</details>

##### `getAnimationDuration(name: string): number`

<details><summary>Code</summary>

```ts
getAnimationDuration( name ) {

		let duration = - 1;

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			duration = animation.duration;

		}

		return duration;

	}
```
</details>

##### `playAnimation(name: string): void`

<details><summary>Code</summary>

```ts
playAnimation( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.time = 0;
			animation.active = true;

		} else {

			console.warn( 'THREE.MorphBlendMesh: animation[' + name + '] undefined in .playAnimation()' );

		}

	}
```
</details>

##### `stopAnimation(name: string): void`

<details><summary>Code</summary>

```ts
stopAnimation( name ) {

		const animation = this.animationsMap[ name ];

		if ( animation ) {

			animation.active = false;

		}

	}
```
</details>

##### `update(delta: number): void`

<details><summary>Code</summary>

```ts
update( delta ) {

		for ( let i = 0, il = this.animationsList.length; i < il; i ++ ) {

			const animation = this.animationsList[ i ];

			if ( ! animation.active ) continue;

			const frameTime = animation.duration / animation.length;

			animation.time += animation.direction * delta;

			if ( animation.mirroredLoop ) {

				if ( animation.time > animation.duration || animation.time < 0 ) {

					animation.direction *= - 1;

					if ( animation.time > animation.duration ) {

						animation.time = animation.duration;
						animation.directionBackwards = true;

					}

					if ( animation.time < 0 ) {

						animation.time = 0;
						animation.directionBackwards = false;

					}

				}

			} else {

				animation.time = animation.time % animation.duration;

				if ( animation.time < 0 ) animation.time += animation.duration;

			}

			const keyframe = animation.start + MathUtils.clamp( Math.floor( animation.time / frameTime ), 0, animation.length - 1 );
			const weight = animation.weight;

			if ( keyframe !== animation.currentFrame ) {

				this.morphTargetInfluences[ animation.lastFrame ] = 0;
				this.morphTargetInfluences[ animation.currentFrame ] = 1 * weight;

				this.morphTargetInfluences[ keyframe ] = 0;

				animation.lastFrame = animation.currentFrame;
				animation.currentFrame = keyframe;

			}

			let mix = ( animation.time % frameTime ) / frameTime;

			if ( animation.directionBackwards ) mix = 1 - mix;

			if ( animation.currentFrame !== animation.lastFrame ) {

				this.morphTargetInfluences[ animation.currentFrame ] = mix * weight;
				this.morphTargetInfluences[ animation.lastFrame ] = ( 1 - mix ) * weight;

			} else {

				this.morphTargetInfluences[ animation.currentFrame ] = weight;

			}

		}

	}
```
</details>


---