[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLRenderLists.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLRenderLists.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `renderItems` | `any[]` | let/var | `[]` | ✗ |
| `renderItemsIndex` | `number` | let/var | `0` | ✗ |
| `opaque` | `any[]` | let/var | `[]` | ✗ |
| `transmissive` | `any[]` | let/var | `[]` | ✗ |
| `transparent` | `any[]` | let/var | `[]` | ✗ |
| `renderItem` | `any` | let/var | `renderItems[ renderItemsIndex ]` | ✗ |
| `renderItem` | `any` | let/var | `renderItems[ i ]` | ✗ |
| `lists` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `list` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `painterSortStable(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function painterSortStable( a, b ) {

	if ( a.groupOrder !== b.groupOrder ) {

		return a.groupOrder - b.groupOrder;

	} else if ( a.renderOrder !== b.renderOrder ) {

		return a.renderOrder - b.renderOrder;

	} else if ( a.material.id !== b.material.id ) {

		return a.material.id - b.material.id;

	} else if ( a.z !== b.z ) {

		return a.z - b.z;

	} else {

		return a.id - b.id;

	}

}
```
</details>

### `reversePainterSortStable(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function reversePainterSortStable( a, b ) {

	if ( a.groupOrder !== b.groupOrder ) {

		return a.groupOrder - b.groupOrder;

	} else if ( a.renderOrder !== b.renderOrder ) {

		return a.renderOrder - b.renderOrder;

	} else if ( a.z !== b.z ) {

		return b.z - a.z;

	} else {

		return a.id - b.id;

	}

}
```
</details>

### `WebGLRenderList(): { opaque: any[]; transmissive: any[]; transparent: any[]; init: () => void; push: (object: any, geometry: any, material: any, groupOrder: any, z: any, group: any) => void; unshift: (object: any, geometry: any, material: any, groupOrder: any, z: any, group: any) => void; finish: () => void; sort: (customOpaqueSort: a...`

**Returns:** `{ opaque: any[]; transmissive: any[]; transparent: any[]; init: () => void; push: (object: any, geometry: any, material: any, groupOrder: any, z: any, group: any) => void; unshift: (object: any, geometry: any, material: any, groupOrder: any, z: any, group: any) => void; finish: () => void; sort: (customOpaqueSort: a...`

**Calls:**

- `getNextRenderItem`
- `transmissive.push`
- `transparent.push`
- `opaque.push`
- `transmissive.unshift`
- `transparent.unshift`
- `opaque.unshift`
- `opaque.sort`
- `transmissive.sort`
- `transparent.sort`

**Internal Comments:**
```
// Clear references from inactive renderItems in the list
```

<details><summary>Code</summary>

```typescript
function WebGLRenderList() {

	const renderItems = [];
	let renderItemsIndex = 0;

	const opaque = [];
	const transmissive = [];
	const transparent = [];

	function init() {

		renderItemsIndex = 0;

		opaque.length = 0;
		transmissive.length = 0;
		transparent.length = 0;

	}

	function getNextRenderItem( object, geometry, material, groupOrder, z, group ) {

		let renderItem = renderItems[ renderItemsIndex ];

		if ( renderItem === undefined ) {

			renderItem = {
				id: object.id,
				object: object,
				geometry: geometry,
				material: material,
				groupOrder: groupOrder,
				renderOrder: object.renderOrder,
				z: z,
				group: group
			};

			renderItems[ renderItemsIndex ] = renderItem;

		} else {

			renderItem.id = object.id;
			renderItem.object = object;
			renderItem.geometry = geometry;
			renderItem.material = material;
			renderItem.groupOrder = groupOrder;
			renderItem.renderOrder = object.renderOrder;
			renderItem.z = z;
			renderItem.group = group;

		}

		renderItemsIndex ++;

		return renderItem;

	}

	function push( object, geometry, material, groupOrder, z, group ) {

		const renderItem = getNextRenderItem( object, geometry, material, groupOrder, z, group );

		if ( material.transmission > 0.0 ) {

			transmissive.push( renderItem );

		} else if ( material.transparent === true ) {

			transparent.push( renderItem );

		} else {

			opaque.push( renderItem );

		}

	}

	function unshift( object, geometry, material, groupOrder, z, group ) {

		const renderItem = getNextRenderItem( object, geometry, material, groupOrder, z, group );

		if ( material.transmission > 0.0 ) {

			transmissive.unshift( renderItem );

		} else if ( material.transparent === true ) {

			transparent.unshift( renderItem );

		} else {

			opaque.unshift( renderItem );

		}

	}

	function sort( customOpaqueSort, customTransparentSort ) {

		if ( opaque.length > 1 ) opaque.sort( customOpaqueSort || painterSortStable );
		if ( transmissive.length > 1 ) transmissive.sort( customTransparentSort || reversePainterSortStable );
		if ( transparent.length > 1 ) transparent.sort( customTransparentSort || reversePainterSortStable );

	}

	function finish() {

		// Clear references from inactive renderItems in the list

		for ( let i = renderItemsIndex, il = renderItems.length; i < il; i ++ ) {

			const renderItem = renderItems[ i ];

			if ( renderItem.id === null ) break;

			renderItem.id = null;
			renderItem.object = null;
			renderItem.geometry = null;
			renderItem.material = null;
			renderItem.group = null;

		}

	}

	return {

		opaque: opaque,
		transmissive: transmissive,
		transparent: transparent,

		init: init,
		push: push,
		unshift: unshift,
		finish: finish,

		sort: sort
	};

}
```
</details>

### `init(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function init() {

		renderItemsIndex = 0;

		opaque.length = 0;
		transmissive.length = 0;
		transparent.length = 0;

	}
```
</details>

### `getNextRenderItem(object: any, geometry: any, material: any, groupOrder: any, z: any, group: any): any`

**Parameters:**

- **`object`** `any`
- **`geometry`** `any`
- **`material`** `any`
- **`groupOrder`** `any`
- **`z`** `any`
- **`group`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getNextRenderItem( object, geometry, material, groupOrder, z, group ) {

		let renderItem = renderItems[ renderItemsIndex ];

		if ( renderItem === undefined ) {

			renderItem = {
				id: object.id,
				object: object,
				geometry: geometry,
				material: material,
				groupOrder: groupOrder,
				renderOrder: object.renderOrder,
				z: z,
				group: group
			};

			renderItems[ renderItemsIndex ] = renderItem;

		} else {

			renderItem.id = object.id;
			renderItem.object = object;
			renderItem.geometry = geometry;
			renderItem.material = material;
			renderItem.groupOrder = groupOrder;
			renderItem.renderOrder = object.renderOrder;
			renderItem.z = z;
			renderItem.group = group;

		}

		renderItemsIndex ++;

		return renderItem;

	}
```
</details>

### `push(object: any, geometry: any, material: any, groupOrder: any, z: any, group: any): void`

**Parameters:**

- **`object`** `any`
- **`geometry`** `any`
- **`material`** `any`
- **`groupOrder`** `any`
- **`z`** `any`
- **`group`** `any`

**Returns:** `void`

**Calls:**

- `getNextRenderItem`
- `transmissive.push`
- `transparent.push`
- `opaque.push`

<details><summary>Code</summary>

```typescript
function push( object, geometry, material, groupOrder, z, group ) {

		const renderItem = getNextRenderItem( object, geometry, material, groupOrder, z, group );

		if ( material.transmission > 0.0 ) {

			transmissive.push( renderItem );

		} else if ( material.transparent === true ) {

			transparent.push( renderItem );

		} else {

			opaque.push( renderItem );

		}

	}
```
</details>

### `unshift(object: any, geometry: any, material: any, groupOrder: any, z: any, group: any): void`

**Parameters:**

- **`object`** `any`
- **`geometry`** `any`
- **`material`** `any`
- **`groupOrder`** `any`
- **`z`** `any`
- **`group`** `any`

**Returns:** `void`

**Calls:**

- `getNextRenderItem`
- `transmissive.unshift`
- `transparent.unshift`
- `opaque.unshift`

<details><summary>Code</summary>

```typescript
function unshift( object, geometry, material, groupOrder, z, group ) {

		const renderItem = getNextRenderItem( object, geometry, material, groupOrder, z, group );

		if ( material.transmission > 0.0 ) {

			transmissive.unshift( renderItem );

		} else if ( material.transparent === true ) {

			transparent.unshift( renderItem );

		} else {

			opaque.unshift( renderItem );

		}

	}
```
</details>

### `sort(customOpaqueSort: any, customTransparentSort: any): void`

**Parameters:**

- **`customOpaqueSort`** `any`
- **`customTransparentSort`** `any`

**Returns:** `void`

**Calls:**

- `opaque.sort`
- `transmissive.sort`
- `transparent.sort`

<details><summary>Code</summary>

```typescript
function sort( customOpaqueSort, customTransparentSort ) {

		if ( opaque.length > 1 ) opaque.sort( customOpaqueSort || painterSortStable );
		if ( transmissive.length > 1 ) transmissive.sort( customTransparentSort || reversePainterSortStable );
		if ( transparent.length > 1 ) transparent.sort( customTransparentSort || reversePainterSortStable );

	}
```
</details>

### `finish(): void`

**Returns:** `void`

**Internal Comments:**
```
// Clear references from inactive renderItems in the list
```

<details><summary>Code</summary>

```typescript
function finish() {

		// Clear references from inactive renderItems in the list

		for ( let i = renderItemsIndex, il = renderItems.length; i < il; i ++ ) {

			const renderItem = renderItems[ i ];

			if ( renderItem.id === null ) break;

			renderItem.id = null;
			renderItem.object = null;
			renderItem.geometry = null;
			renderItem.material = null;
			renderItem.group = null;

		}

	}
```
</details>

### `WebGLRenderLists(): { get: (scene: any, renderCallDepth: any) => any; dispose: () => void; }`

**Returns:** `{ get: (scene: any, renderCallDepth: any) => any; dispose: () => void; }`

**Calls:**

- `lists.get`
- `lists.set`
- `listArray.push`

<details><summary>Code</summary>

```typescript
function WebGLRenderLists() {

	let lists = new WeakMap();

	function get( scene, renderCallDepth ) {

		const listArray = lists.get( scene );
		let list;

		if ( listArray === undefined ) {

			list = new WebGLRenderList();
			lists.set( scene, [ list ] );

		} else {

			if ( renderCallDepth >= listArray.length ) {

				list = new WebGLRenderList();
				listArray.push( list );

			} else {

				list = listArray[ renderCallDepth ];

			}

		}

		return list;

	}

	function dispose() {

		lists = new WeakMap();

	}

	return {
		get: get,
		dispose: dispose
	};

}
```
</details>

### `get(scene: any, renderCallDepth: any): any`

**Parameters:**

- **`scene`** `any`
- **`renderCallDepth`** `any`

**Returns:** `any`

**Calls:**

- `lists.get`
- `lists.set`
- `listArray.push`

<details><summary>Code</summary>

```typescript
function get( scene, renderCallDepth ) {

		const listArray = lists.get( scene );
		let list;

		if ( listArray === undefined ) {

			list = new WebGLRenderList();
			lists.set( scene, [ list ] );

		} else {

			if ( renderCallDepth >= listArray.length ) {

				list = new WebGLRenderList();
				listArray.push( list );

			} else {

				list = listArray[ renderCallDepth ];

			}

		}

		return list;

	}
```
</details>

### `dispose(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function dispose() {

		lists = new WeakMap();

	}
```
</details>


---