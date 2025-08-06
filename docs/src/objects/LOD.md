[⬅️ Back to Table of Contents](../../index.md)

# 📄 `LOD.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 19 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/LOD.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `Object3D` | `../core/Object3D.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_v1` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_v2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `levels` | `any` | let/var | `source.levels` | ✗ |
| `level` | `any` | let/var | `levels[ i ]` | ✗ |
| `levels` | `any` | let/var | `this.levels` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `levels` | `any` | let/var | `this.levels` | ✗ |
| `levels` | `any` | let/var | `this.levels` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `levelDistance` | `any` | let/var | `levels[ i ].distance` | ✗ |
| `levels` | `any` | let/var | `this.levels` | ✗ |
| `levels` | `any` | let/var | `this.levels` | ✗ |
| `distance` | `number` | let/var | `_v1.distanceTo( _v2 ) / camera.zoom` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `levelDistance` | `any` | let/var | `levels[ i ].distance` | ✗ |
| `levels` | `any` | let/var | `this.levels` | ✗ |
| `level` | `any` | let/var | `levels[ i ]` | ✗ |


---

## Functions

### `LOD.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.addLevel`
- `level.object.clone`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source, false );

		const levels = source.levels;

		for ( let i = 0, l = levels.length; i < l; i ++ ) {

			const level = levels[ i ];

			this.addLevel( level.object.clone(), level.distance, level.hysteresis );

		}

		this.autoUpdate = source.autoUpdate;

		return this;

	}
```
</details>

### `LOD.addLevel(object: Object3D, distance: number, hysteresis: number): LOD`

**JSDoc:**
```typescript
/**
	 * Adds a mesh that will display at a certain distance and greater. Typically
	 * the further away the distance, the lower the detail on the mesh.
	 *
	 * @param {Object3D} object - The 3D object to display at this level.
	 * @param {number} [distance=0] - The distance at which to display this level of detail.
	 * @param {number} [hysteresis=0] - Threshold used to avoid flickering at LOD boundaries, as a fraction of distance.
	 * @return {LOD} A reference to this instance.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`distance`** `number`
- **`hysteresis`** `number`

**Returns:** `LOD`

**Calls:**

- `Math.abs`
- `levels.splice`
- `this.add`

<details><summary>Code</summary>

```typescript
addLevel( object, distance = 0, hysteresis = 0 ) {

		distance = Math.abs( distance );

		const levels = this.levels;

		let l;

		for ( l = 0; l < levels.length; l ++ ) {

			if ( distance < levels[ l ].distance ) {

				break;

			}

		}

		levels.splice( l, 0, { distance: distance, hysteresis: hysteresis, object: object } );

		this.add( object );

		return this;

	}
```
</details>

### `LOD.removeLevel(distance: number): boolean`

**JSDoc:**
```typescript
/**
	 * Removes an existing level, based on the distance from the camera.
	 * Returns `true` when the level has been removed. Otherwise `false`.
	 *
	 * @param {number} distance - Distance of the level to remove.
	 * @return {boolean} Whether the level has been removed or not.
	 */
```

**Parameters:**

- **`distance`** `number`

**Returns:** `boolean`

**Calls:**

- `levels.splice`
- `this.remove`

<details><summary>Code</summary>

```typescript
removeLevel( distance ) {

		const levels = this.levels;

		for ( let i = 0; i < levels.length; i ++ ) {

			if ( levels[ i ].distance === distance ) {

				const removedElements = levels.splice( i, 1 );
				this.remove( removedElements[ 0 ].object );

				return true;

			}

		}

		return false;

	}
```
</details>

### `LOD.getCurrentLevel(): number`

**JSDoc:**
```typescript
/**
	 * Returns the currently active LOD level index.
	 *
	 * @return {number} The current active LOD level index.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getCurrentLevel() {

		return this._currentLevel;

	}
```
</details>

### `LOD.getObjectForDistance(distance: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Returns a reference to the first 3D object that is greater than
	 * the given distance.
	 *
	 * @param {number} distance - The LOD distance.
	 * @return {Object3D|null} The found 3D object. `null` if no 3D object has been found.
	 */
```

**Parameters:**

- **`distance`** `number`

**Returns:** `Object3D`

<details><summary>Code</summary>

```typescript
getObjectForDistance( distance ) {

		const levels = this.levels;

		if ( levels.length > 0 ) {

			let i, l;

			for ( i = 1, l = levels.length; i < l; i ++ ) {

				let levelDistance = levels[ i ].distance;

				if ( levels[ i ].object.visible ) {

					levelDistance -= levelDistance * levels[ i ].hysteresis;

				}

				if ( distance < levelDistance ) {

					break;

				}

			}

			return levels[ i - 1 ].object;

		}

		return null;

	}
```
</details>

### `LOD.raycast(raycaster: Raycaster, intersects: any[]): void`

**JSDoc:**
```typescript
/**
	 * Computes intersection points between a casted ray and this LOD.
	 *
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - The target array that holds the intersection points.
	 */
```

**Parameters:**

- **`raycaster`** `Raycaster`
- **`intersects`** `any[]`

**Returns:** `void`

**Calls:**

- `_v1.setFromMatrixPosition`
- `raycaster.ray.origin.distanceTo`
- `this.getObjectForDistance( distance ).raycast`

<details><summary>Code</summary>

```typescript
raycast( raycaster, intersects ) {

		const levels = this.levels;

		if ( levels.length > 0 ) {

			_v1.setFromMatrixPosition( this.matrixWorld );

			const distance = raycaster.ray.origin.distanceTo( _v1 );

			this.getObjectForDistance( distance ).raycast( raycaster, intersects );

		}

	}
```
</details>

### `LOD.update(camera: Camera): void`

**JSDoc:**
```typescript
/**
	 * Updates the LOD by computing which LOD level should be visible according
	 * to the current distance of the given camera.
	 *
	 * @param {Camera} camera - The camera the scene is rendered with.
	 */
```

**Parameters:**

- **`camera`** `Camera`

**Returns:** `void`

**Calls:**

- `_v1.setFromMatrixPosition`
- `_v2.setFromMatrixPosition`
- `_v1.distanceTo`

<details><summary>Code</summary>

```typescript
update( camera ) {

		const levels = this.levels;

		if ( levels.length > 1 ) {

			_v1.setFromMatrixPosition( camera.matrixWorld );
			_v2.setFromMatrixPosition( this.matrixWorld );

			const distance = _v1.distanceTo( _v2 ) / camera.zoom;

			levels[ 0 ].object.visible = true;

			let i, l;

			for ( i = 1, l = levels.length; i < l; i ++ ) {

				let levelDistance = levels[ i ].distance;

				if ( levels[ i ].object.visible ) {

					levelDistance -= levelDistance * levels[ i ].hysteresis;

				}

				if ( distance >= levelDistance ) {

					levels[ i - 1 ].object.visible = false;
					levels[ i ].object.visible = true;

				} else {

					break;

				}

			}

			this._currentLevel = i - 1;

			for ( ; i < l; i ++ ) {

				levels[ i ].object.visible = false;

			}

		}

	}
```
</details>

### `LOD.toJSON(meta: any): any`

**Parameters:**

- **`meta`** `any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `data.object.levels.push`

<details><summary>Code</summary>

```typescript
toJSON( meta ) {

		const data = super.toJSON( meta );

		if ( this.autoUpdate === false ) data.object.autoUpdate = false;

		data.object.levels = [];

		const levels = this.levels;

		for ( let i = 0, l = levels.length; i < l; i ++ ) {

			const level = levels[ i ];

			data.object.levels.push( {
				object: level.object.uuid,
				distance: level.distance,
				hysteresis: level.hysteresis
			} );

		}

		return data;

	}
```
</details>


---

## Classes

### `LOD`

<details><summary>Class Code</summary>

```ts
class LOD extends Object3D {

	/**
	 * Constructs a new LOD.
	 */
	constructor() {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLOD = true;

		/**
		 * The current LOD index.
		 *
		 * @private
		 * @type {number}
		 * @default 0
		 */
		this._currentLevel = 0;

		this.type = 'LOD';

		Object.defineProperties( this, {
			/**
			 * This array holds the LOD levels.
			 *
			 * @name LOD#levels
			 * @type {Array<{object:Object3D,distance:number,hysteresis:number}>}
			 */
			levels: {
				enumerable: true,
				value: []
			}
		} );

		/**
		 * Whether the LOD object is updated automatically by the renderer per frame
		 * or not. If set to `false`, you have to call {@link LOD#update} in the
		 * render loop by yourself.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.autoUpdate = true;

	}

	copy( source ) {

		super.copy( source, false );

		const levels = source.levels;

		for ( let i = 0, l = levels.length; i < l; i ++ ) {

			const level = levels[ i ];

			this.addLevel( level.object.clone(), level.distance, level.hysteresis );

		}

		this.autoUpdate = source.autoUpdate;

		return this;

	}

	/**
	 * Adds a mesh that will display at a certain distance and greater. Typically
	 * the further away the distance, the lower the detail on the mesh.
	 *
	 * @param {Object3D} object - The 3D object to display at this level.
	 * @param {number} [distance=0] - The distance at which to display this level of detail.
	 * @param {number} [hysteresis=0] - Threshold used to avoid flickering at LOD boundaries, as a fraction of distance.
	 * @return {LOD} A reference to this instance.
	 */
	addLevel( object, distance = 0, hysteresis = 0 ) {

		distance = Math.abs( distance );

		const levels = this.levels;

		let l;

		for ( l = 0; l < levels.length; l ++ ) {

			if ( distance < levels[ l ].distance ) {

				break;

			}

		}

		levels.splice( l, 0, { distance: distance, hysteresis: hysteresis, object: object } );

		this.add( object );

		return this;

	}

	/**
	 * Removes an existing level, based on the distance from the camera.
	 * Returns `true` when the level has been removed. Otherwise `false`.
	 *
	 * @param {number} distance - Distance of the level to remove.
	 * @return {boolean} Whether the level has been removed or not.
	 */
	removeLevel( distance ) {

		const levels = this.levels;

		for ( let i = 0; i < levels.length; i ++ ) {

			if ( levels[ i ].distance === distance ) {

				const removedElements = levels.splice( i, 1 );
				this.remove( removedElements[ 0 ].object );

				return true;

			}

		}

		return false;

	}

	/**
	 * Returns the currently active LOD level index.
	 *
	 * @return {number} The current active LOD level index.
	 */
	getCurrentLevel() {

		return this._currentLevel;

	}

	/**
	 * Returns a reference to the first 3D object that is greater than
	 * the given distance.
	 *
	 * @param {number} distance - The LOD distance.
	 * @return {Object3D|null} The found 3D object. `null` if no 3D object has been found.
	 */
	getObjectForDistance( distance ) {

		const levels = this.levels;

		if ( levels.length > 0 ) {

			let i, l;

			for ( i = 1, l = levels.length; i < l; i ++ ) {

				let levelDistance = levels[ i ].distance;

				if ( levels[ i ].object.visible ) {

					levelDistance -= levelDistance * levels[ i ].hysteresis;

				}

				if ( distance < levelDistance ) {

					break;

				}

			}

			return levels[ i - 1 ].object;

		}

		return null;

	}

	/**
	 * Computes intersection points between a casted ray and this LOD.
	 *
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - The target array that holds the intersection points.
	 */
	raycast( raycaster, intersects ) {

		const levels = this.levels;

		if ( levels.length > 0 ) {

			_v1.setFromMatrixPosition( this.matrixWorld );

			const distance = raycaster.ray.origin.distanceTo( _v1 );

			this.getObjectForDistance( distance ).raycast( raycaster, intersects );

		}

	}

	/**
	 * Updates the LOD by computing which LOD level should be visible according
	 * to the current distance of the given camera.
	 *
	 * @param {Camera} camera - The camera the scene is rendered with.
	 */
	update( camera ) {

		const levels = this.levels;

		if ( levels.length > 1 ) {

			_v1.setFromMatrixPosition( camera.matrixWorld );
			_v2.setFromMatrixPosition( this.matrixWorld );

			const distance = _v1.distanceTo( _v2 ) / camera.zoom;

			levels[ 0 ].object.visible = true;

			let i, l;

			for ( i = 1, l = levels.length; i < l; i ++ ) {

				let levelDistance = levels[ i ].distance;

				if ( levels[ i ].object.visible ) {

					levelDistance -= levelDistance * levels[ i ].hysteresis;

				}

				if ( distance >= levelDistance ) {

					levels[ i - 1 ].object.visible = false;
					levels[ i ].object.visible = true;

				} else {

					break;

				}

			}

			this._currentLevel = i - 1;

			for ( ; i < l; i ++ ) {

				levels[ i ].object.visible = false;

			}

		}

	}

	toJSON( meta ) {

		const data = super.toJSON( meta );

		if ( this.autoUpdate === false ) data.object.autoUpdate = false;

		data.object.levels = [];

		const levels = this.levels;

		for ( let i = 0, l = levels.length; i < l; i ++ ) {

			const level = levels[ i ];

			data.object.levels.push( {
				object: level.object.uuid,
				distance: level.distance,
				hysteresis: level.hysteresis
			} );

		}

		return data;

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source, false );

		const levels = source.levels;

		for ( let i = 0, l = levels.length; i < l; i ++ ) {

			const level = levels[ i ];

			this.addLevel( level.object.clone(), level.distance, level.hysteresis );

		}

		this.autoUpdate = source.autoUpdate;

		return this;

	}
```
</details>

##### `addLevel(object: Object3D, distance: number, hysteresis: number): LOD`

<details><summary>Code</summary>

```ts
addLevel( object, distance = 0, hysteresis = 0 ) {

		distance = Math.abs( distance );

		const levels = this.levels;

		let l;

		for ( l = 0; l < levels.length; l ++ ) {

			if ( distance < levels[ l ].distance ) {

				break;

			}

		}

		levels.splice( l, 0, { distance: distance, hysteresis: hysteresis, object: object } );

		this.add( object );

		return this;

	}
```
</details>

##### `removeLevel(distance: number): boolean`

<details><summary>Code</summary>

```ts
removeLevel( distance ) {

		const levels = this.levels;

		for ( let i = 0; i < levels.length; i ++ ) {

			if ( levels[ i ].distance === distance ) {

				const removedElements = levels.splice( i, 1 );
				this.remove( removedElements[ 0 ].object );

				return true;

			}

		}

		return false;

	}
```
</details>

##### `getCurrentLevel(): number`

<details><summary>Code</summary>

```ts
getCurrentLevel() {

		return this._currentLevel;

	}
```
</details>

##### `getObjectForDistance(distance: number): Object3D`

<details><summary>Code</summary>

```ts
getObjectForDistance( distance ) {

		const levels = this.levels;

		if ( levels.length > 0 ) {

			let i, l;

			for ( i = 1, l = levels.length; i < l; i ++ ) {

				let levelDistance = levels[ i ].distance;

				if ( levels[ i ].object.visible ) {

					levelDistance -= levelDistance * levels[ i ].hysteresis;

				}

				if ( distance < levelDistance ) {

					break;

				}

			}

			return levels[ i - 1 ].object;

		}

		return null;

	}
```
</details>

##### `raycast(raycaster: Raycaster, intersects: any[]): void`

<details><summary>Code</summary>

```ts
raycast( raycaster, intersects ) {

		const levels = this.levels;

		if ( levels.length > 0 ) {

			_v1.setFromMatrixPosition( this.matrixWorld );

			const distance = raycaster.ray.origin.distanceTo( _v1 );

			this.getObjectForDistance( distance ).raycast( raycaster, intersects );

		}

	}
```
</details>

##### `update(camera: Camera): void`

<details><summary>Code</summary>

```ts
update( camera ) {

		const levels = this.levels;

		if ( levels.length > 1 ) {

			_v1.setFromMatrixPosition( camera.matrixWorld );
			_v2.setFromMatrixPosition( this.matrixWorld );

			const distance = _v1.distanceTo( _v2 ) / camera.zoom;

			levels[ 0 ].object.visible = true;

			let i, l;

			for ( i = 1, l = levels.length; i < l; i ++ ) {

				let levelDistance = levels[ i ].distance;

				if ( levels[ i ].object.visible ) {

					levelDistance -= levelDistance * levels[ i ].hysteresis;

				}

				if ( distance >= levelDistance ) {

					levels[ i - 1 ].object.visible = false;
					levels[ i ].object.visible = true;

				} else {

					break;

				}

			}

			this._currentLevel = i - 1;

			for ( ; i < l; i ++ ) {

				levels[ i ].object.visible = false;

			}

		}

	}
```
</details>

##### `toJSON(meta: any): any`

<details><summary>Code</summary>

```ts
toJSON( meta ) {

		const data = super.toJSON( meta );

		if ( this.autoUpdate === false ) data.object.autoUpdate = false;

		data.object.levels = [];

		const levels = this.levels;

		for ( let i = 0, l = levels.length; i < l; i ++ ) {

			const level = levels[ i ];

			data.object.levels.push( {
				object: level.object.uuid,
				distance: level.distance,
				hysteresis: level.hysteresis
			} );

		}

		return data;

	}
```
</details>


---