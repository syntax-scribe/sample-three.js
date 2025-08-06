[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `OctreeHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/OctreeHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LineSegments` | `three` |
| `BufferGeometry` | `three` |
| `Float32BufferAttribute` | `three` |
| `LineBasicMaterial` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `min` | `any` | let/var | `tree[ i ].box.min` | ✗ |
| `max` | `any` | let/var | `tree[ i ].box.max` | ✗ |


---

## Functions

### `OctreeHelper.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the helper. This method must be called whenever the Octree's
	 * structure is changed.
	 */
```

**Returns:** `void`

**Calls:**

- `vertices.push`
- `traverse`
- `this.geometry.dispose`
- `this.geometry.setAttribute`

<details><summary>Code</summary>

```typescript
update() {

		const vertices = [];

		function traverse( tree ) {

			for ( let i = 0; i < tree.length; i ++ ) {

				const min = tree[ i ].box.min;
				const max = tree[ i ].box.max;

				vertices.push( max.x, max.y, max.z ); vertices.push( min.x, max.y, max.z ); // 0, 1
				vertices.push( min.x, max.y, max.z ); vertices.push( min.x, min.y, max.z ); // 1, 2
				vertices.push( min.x, min.y, max.z ); vertices.push( max.x, min.y, max.z ); // 2, 3
				vertices.push( max.x, min.y, max.z ); vertices.push( max.x, max.y, max.z ); // 3, 0

				vertices.push( max.x, max.y, min.z ); vertices.push( min.x, max.y, min.z ); // 4, 5
				vertices.push( min.x, max.y, min.z ); vertices.push( min.x, min.y, min.z ); // 5, 6
				vertices.push( min.x, min.y, min.z ); vertices.push( max.x, min.y, min.z ); // 6, 7
				vertices.push( max.x, min.y, min.z ); vertices.push( max.x, max.y, min.z ); // 7, 4

				vertices.push( max.x, max.y, max.z ); vertices.push( max.x, max.y, min.z ); // 0, 4
				vertices.push( min.x, max.y, max.z ); vertices.push( min.x, max.y, min.z ); // 1, 5
				vertices.push( min.x, min.y, max.z ); vertices.push( min.x, min.y, min.z ); // 2, 6
				vertices.push( max.x, min.y, max.z ); vertices.push( max.x, min.y, min.z ); // 3, 7

				traverse( tree[ i ].subTrees );

			}

		}

		traverse( this.octree.subTrees );

		this.geometry.dispose();

		this.geometry = new BufferGeometry();
		this.geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

	}
```
</details>

### `OctreeHelper.dispose(): void`

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
- `this.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>

### `traverse(tree: any): void`

**Parameters:**

- **`tree`** `any`

**Returns:** `void`

**Calls:**

- `vertices.push`
- `traverse`

<details><summary>Code</summary>

```typescript
function traverse( tree ) {

			for ( let i = 0; i < tree.length; i ++ ) {

				const min = tree[ i ].box.min;
				const max = tree[ i ].box.max;

				vertices.push( max.x, max.y, max.z ); vertices.push( min.x, max.y, max.z ); // 0, 1
				vertices.push( min.x, max.y, max.z ); vertices.push( min.x, min.y, max.z ); // 1, 2
				vertices.push( min.x, min.y, max.z ); vertices.push( max.x, min.y, max.z ); // 2, 3
				vertices.push( max.x, min.y, max.z ); vertices.push( max.x, max.y, max.z ); // 3, 0

				vertices.push( max.x, max.y, min.z ); vertices.push( min.x, max.y, min.z ); // 4, 5
				vertices.push( min.x, max.y, min.z ); vertices.push( min.x, min.y, min.z ); // 5, 6
				vertices.push( min.x, min.y, min.z ); vertices.push( max.x, min.y, min.z ); // 6, 7
				vertices.push( max.x, min.y, min.z ); vertices.push( max.x, max.y, min.z ); // 7, 4

				vertices.push( max.x, max.y, max.z ); vertices.push( max.x, max.y, min.z ); // 0, 4
				vertices.push( min.x, max.y, max.z ); vertices.push( min.x, max.y, min.z ); // 1, 5
				vertices.push( min.x, min.y, max.z ); vertices.push( min.x, min.y, min.z ); // 2, 6
				vertices.push( max.x, min.y, max.z ); vertices.push( max.x, min.y, min.z ); // 3, 7

				traverse( tree[ i ].subTrees );

			}

		}
```
</details>


---

## Classes

### `OctreeHelper`

<details><summary>Class Code</summary>

```ts
class OctreeHelper extends LineSegments {

	/**
	 * Constructs a new Octree helper.
	 *
	 * @param {Octree} octree - The octree to visualize.
	 * @param {number|Color|string} [color=0xffff00] - The helper's color.
	 */
	constructor( octree, color = 0xffff00 ) {

		super( new BufferGeometry(), new LineBasicMaterial( { color: color, toneMapped: false } ) );

		/**
		 * The octree to visualize.
		 *
		 * @type {Octree}
		 */
		this.octree = octree;

		/**
		 * The helper's color.
		 *
		 * @type {number|Color|string}
		 */
		this.color = color;

		this.type = 'OctreeHelper';

		this.update();

	}

	/**
	 * Updates the helper. This method must be called whenever the Octree's
	 * structure is changed.
	 */
	update() {

		const vertices = [];

		function traverse( tree ) {

			for ( let i = 0; i < tree.length; i ++ ) {

				const min = tree[ i ].box.min;
				const max = tree[ i ].box.max;

				vertices.push( max.x, max.y, max.z ); vertices.push( min.x, max.y, max.z ); // 0, 1
				vertices.push( min.x, max.y, max.z ); vertices.push( min.x, min.y, max.z ); // 1, 2
				vertices.push( min.x, min.y, max.z ); vertices.push( max.x, min.y, max.z ); // 2, 3
				vertices.push( max.x, min.y, max.z ); vertices.push( max.x, max.y, max.z ); // 3, 0

				vertices.push( max.x, max.y, min.z ); vertices.push( min.x, max.y, min.z ); // 4, 5
				vertices.push( min.x, max.y, min.z ); vertices.push( min.x, min.y, min.z ); // 5, 6
				vertices.push( min.x, min.y, min.z ); vertices.push( max.x, min.y, min.z ); // 6, 7
				vertices.push( max.x, min.y, min.z ); vertices.push( max.x, max.y, min.z ); // 7, 4

				vertices.push( max.x, max.y, max.z ); vertices.push( max.x, max.y, min.z ); // 0, 4
				vertices.push( min.x, max.y, max.z ); vertices.push( min.x, max.y, min.z ); // 1, 5
				vertices.push( min.x, min.y, max.z ); vertices.push( min.x, min.y, min.z ); // 2, 6
				vertices.push( max.x, min.y, max.z ); vertices.push( max.x, min.y, min.z ); // 3, 7

				traverse( tree[ i ].subTrees );

			}

		}

		traverse( this.octree.subTrees );

		this.geometry.dispose();

		this.geometry = new BufferGeometry();
		this.geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}

}
```
</details>

#### Methods

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const vertices = [];

		function traverse( tree ) {

			for ( let i = 0; i < tree.length; i ++ ) {

				const min = tree[ i ].box.min;
				const max = tree[ i ].box.max;

				vertices.push( max.x, max.y, max.z ); vertices.push( min.x, max.y, max.z ); // 0, 1
				vertices.push( min.x, max.y, max.z ); vertices.push( min.x, min.y, max.z ); // 1, 2
				vertices.push( min.x, min.y, max.z ); vertices.push( max.x, min.y, max.z ); // 2, 3
				vertices.push( max.x, min.y, max.z ); vertices.push( max.x, max.y, max.z ); // 3, 0

				vertices.push( max.x, max.y, min.z ); vertices.push( min.x, max.y, min.z ); // 4, 5
				vertices.push( min.x, max.y, min.z ); vertices.push( min.x, min.y, min.z ); // 5, 6
				vertices.push( min.x, min.y, min.z ); vertices.push( max.x, min.y, min.z ); // 6, 7
				vertices.push( max.x, min.y, min.z ); vertices.push( max.x, max.y, min.z ); // 7, 4

				vertices.push( max.x, max.y, max.z ); vertices.push( max.x, max.y, min.z ); // 0, 4
				vertices.push( min.x, max.y, max.z ); vertices.push( min.x, max.y, min.z ); // 1, 5
				vertices.push( min.x, min.y, max.z ); vertices.push( min.x, min.y, min.z ); // 2, 6
				vertices.push( max.x, min.y, max.z ); vertices.push( max.x, min.y, min.z ); // 3, 7

				traverse( tree[ i ].subTrees );

			}

		}

		traverse( this.octree.subTrees );

		this.geometry.dispose();

		this.geometry = new BufferGeometry();
		this.geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>


---