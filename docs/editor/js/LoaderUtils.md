[⬅️ Back to Table of Contents](../../index.md)

# 📄 `LoaderUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/LoaderUtils.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `map` | `{}` | let/var | `{}` | ✗ |
| `file` | `any` | let/var | `files[ i ]` | ✗ |
| `itemsCount` | `number` | let/var | `0` | ✗ |
| `itemsTotal` | `number` | let/var | `0` | ✗ |
| `files` | `any[]` | let/var | `[]` | ✗ |
| `filesMap` | `{}` | let/var | `{}` | ✗ |
| `item` | `any` | let/var | `items[ i ]` | ✗ |
| `LoaderUtils` | `{ createFilesMap: (files: any) => {};...` | let/var | `{ createFilesMap: function ( files ) { const map = {}; for ( let i = 0; i < f...` | ✗ |


---

## Functions

### `createFilesMap(files: any): {}`

**Parameters:**

- **`files`** `any`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function ( files ) {

		const map = {};

		for ( let i = 0; i < files.length; i ++ ) {

			const file = files[ i ];
			map[ file.name ] = file;

		}

		return map;

	}
```
</details>

### `getFilesFromItemList(items: any, onDone: any): void`

**Parameters:**

- **`items`** `any`
- **`onDone`** `any`

**Returns:** `void`

**Calls:**

- `onDone`
- `entry.createReader`
- `reader.readEntries`
- `handleEntry`
- `onEntryHandled`
- `entry.file`
- `files.push`
- `entry.fullPath.slice`
- `item.webkitGetAsEntry`

**Internal Comments:**
```
// TOFIX: setURLModifier() breaks when the file being loaded is not in root (x2)
```

<details><summary>Code</summary>

```typescript
function ( items, onDone ) {

		// TOFIX: setURLModifier() breaks when the file being loaded is not in root

		let itemsCount = 0;
		let itemsTotal = 0;

		const files = [];
		const filesMap = {};

		function onEntryHandled() {

			itemsCount ++;

			if ( itemsCount === itemsTotal ) {

				onDone( files, filesMap );

			}

		}

		function handleEntry( entry ) {

			if ( entry.isDirectory ) {

				const reader = entry.createReader();
				reader.readEntries( function ( entries ) {

					for ( let i = 0; i < entries.length; i ++ ) {

						handleEntry( entries[ i ] );

					}

					onEntryHandled();

				} );

			} else if ( entry.isFile ) {

				entry.file( function ( file ) {

					files.push( file );

					filesMap[ entry.fullPath.slice( 1 ) ] = file;
					onEntryHandled();

				} );

			}

			itemsTotal ++;

		}

		for ( let i = 0; i < items.length; i ++ ) {

			const item = items[ i ];

			if ( item.kind === 'file' ) {

				handleEntry( item.webkitGetAsEntry() );

			}

		}

	}
```
</details>

### `onEntryHandled(): void`

**Returns:** `void`

**Calls:**

- `onDone`

<details><summary>Code</summary>

```typescript
function onEntryHandled() {

			itemsCount ++;

			if ( itemsCount === itemsTotal ) {

				onDone( files, filesMap );

			}

		}
```
</details>

### `handleEntry(entry: any): void`

**Parameters:**

- **`entry`** `any`

**Returns:** `void`

**Calls:**

- `entry.createReader`
- `reader.readEntries`
- `handleEntry`
- `onEntryHandled`
- `entry.file`
- `files.push`
- `entry.fullPath.slice`

<details><summary>Code</summary>

```typescript
function handleEntry( entry ) {

			if ( entry.isDirectory ) {

				const reader = entry.createReader();
				reader.readEntries( function ( entries ) {

					for ( let i = 0; i < entries.length; i ++ ) {

						handleEntry( entries[ i ] );

					}

					onEntryHandled();

				} );

			} else if ( entry.isFile ) {

				entry.file( function ( file ) {

					files.push( file );

					filesMap[ entry.fullPath.slice( 1 ) ] = file;
					onEntryHandled();

				} );

			}

			itemsTotal ++;

		}
```
</details>

### `createFilesMap(files: any): {}`

**Parameters:**

- **`files`** `any`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function ( files ) {

		const map = {};

		for ( let i = 0; i < files.length; i ++ ) {

			const file = files[ i ];
			map[ file.name ] = file;

		}

		return map;

	}
```
</details>

### `getFilesFromItemList(items: any, onDone: any): void`

**Parameters:**

- **`items`** `any`
- **`onDone`** `any`

**Returns:** `void`

**Calls:**

- `onDone`
- `entry.createReader`
- `reader.readEntries`
- `handleEntry`
- `onEntryHandled`
- `entry.file`
- `files.push`
- `entry.fullPath.slice`
- `item.webkitGetAsEntry`

**Internal Comments:**
```
// TOFIX: setURLModifier() breaks when the file being loaded is not in root (x2)
```

<details><summary>Code</summary>

```typescript
function ( items, onDone ) {

		// TOFIX: setURLModifier() breaks when the file being loaded is not in root

		let itemsCount = 0;
		let itemsTotal = 0;

		const files = [];
		const filesMap = {};

		function onEntryHandled() {

			itemsCount ++;

			if ( itemsCount === itemsTotal ) {

				onDone( files, filesMap );

			}

		}

		function handleEntry( entry ) {

			if ( entry.isDirectory ) {

				const reader = entry.createReader();
				reader.readEntries( function ( entries ) {

					for ( let i = 0; i < entries.length; i ++ ) {

						handleEntry( entries[ i ] );

					}

					onEntryHandled();

				} );

			} else if ( entry.isFile ) {

				entry.file( function ( file ) {

					files.push( file );

					filesMap[ entry.fullPath.slice( 1 ) ] = file;
					onEntryHandled();

				} );

			}

			itemsTotal ++;

		}

		for ( let i = 0; i < items.length; i ++ ) {

			const item = items[ i ];

			if ( item.kind === 'file' ) {

				handleEntry( item.webkitGetAsEntry() );

			}

		}

	}
```
</details>

### `createFilesMap(files: any): {}`

**Parameters:**

- **`files`** `any`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function ( files ) {

		const map = {};

		for ( let i = 0; i < files.length; i ++ ) {

			const file = files[ i ];
			map[ file.name ] = file;

		}

		return map;

	}
```
</details>

### `getFilesFromItemList(items: any, onDone: any): void`

**Parameters:**

- **`items`** `any`
- **`onDone`** `any`

**Returns:** `void`

**Calls:**

- `onDone`
- `entry.createReader`
- `reader.readEntries`
- `handleEntry`
- `onEntryHandled`
- `entry.file`
- `files.push`
- `entry.fullPath.slice`
- `item.webkitGetAsEntry`

**Internal Comments:**
```
// TOFIX: setURLModifier() breaks when the file being loaded is not in root (x2)
```

<details><summary>Code</summary>

```typescript
function ( items, onDone ) {

		// TOFIX: setURLModifier() breaks when the file being loaded is not in root

		let itemsCount = 0;
		let itemsTotal = 0;

		const files = [];
		const filesMap = {};

		function onEntryHandled() {

			itemsCount ++;

			if ( itemsCount === itemsTotal ) {

				onDone( files, filesMap );

			}

		}

		function handleEntry( entry ) {

			if ( entry.isDirectory ) {

				const reader = entry.createReader();
				reader.readEntries( function ( entries ) {

					for ( let i = 0; i < entries.length; i ++ ) {

						handleEntry( entries[ i ] );

					}

					onEntryHandled();

				} );

			} else if ( entry.isFile ) {

				entry.file( function ( file ) {

					files.push( file );

					filesMap[ entry.fullPath.slice( 1 ) ] = file;
					onEntryHandled();

				} );

			}

			itemsTotal ++;

		}

		for ( let i = 0; i < items.length; i ++ ) {

			const item = items[ i ];

			if ( item.kind === 'file' ) {

				handleEntry( item.webkitGetAsEntry() );

			}

		}

	}
```
</details>

### `createFilesMap(files: any): {}`

**Parameters:**

- **`files`** `any`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function ( files ) {

		const map = {};

		for ( let i = 0; i < files.length; i ++ ) {

			const file = files[ i ];
			map[ file.name ] = file;

		}

		return map;

	}
```
</details>

### `getFilesFromItemList(items: any, onDone: any): void`

**Parameters:**

- **`items`** `any`
- **`onDone`** `any`

**Returns:** `void`

**Calls:**

- `onDone`
- `entry.createReader`
- `reader.readEntries`
- `handleEntry`
- `onEntryHandled`
- `entry.file`
- `files.push`
- `entry.fullPath.slice`
- `item.webkitGetAsEntry`

**Internal Comments:**
```
// TOFIX: setURLModifier() breaks when the file being loaded is not in root (x2)
```

<details><summary>Code</summary>

```typescript
function ( items, onDone ) {

		// TOFIX: setURLModifier() breaks when the file being loaded is not in root

		let itemsCount = 0;
		let itemsTotal = 0;

		const files = [];
		const filesMap = {};

		function onEntryHandled() {

			itemsCount ++;

			if ( itemsCount === itemsTotal ) {

				onDone( files, filesMap );

			}

		}

		function handleEntry( entry ) {

			if ( entry.isDirectory ) {

				const reader = entry.createReader();
				reader.readEntries( function ( entries ) {

					for ( let i = 0; i < entries.length; i ++ ) {

						handleEntry( entries[ i ] );

					}

					onEntryHandled();

				} );

			} else if ( entry.isFile ) {

				entry.file( function ( file ) {

					files.push( file );

					filesMap[ entry.fullPath.slice( 1 ) ] = file;
					onEntryHandled();

				} );

			}

			itemsTotal ++;

		}

		for ( let i = 0; i < items.length; i ++ ) {

			const item = items[ i ];

			if ( item.kind === 'file' ) {

				handleEntry( item.webkitGetAsEntry() );

			}

		}

	}
```
</details>

### `createFilesMap(files: any): {}`

**Parameters:**

- **`files`** `any`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function ( files ) {

		const map = {};

		for ( let i = 0; i < files.length; i ++ ) {

			const file = files[ i ];
			map[ file.name ] = file;

		}

		return map;

	}
```
</details>

### `getFilesFromItemList(items: any, onDone: any): void`

**Parameters:**

- **`items`** `any`
- **`onDone`** `any`

**Returns:** `void`

**Calls:**

- `onDone`
- `entry.createReader`
- `reader.readEntries`
- `handleEntry`
- `onEntryHandled`
- `entry.file`
- `files.push`
- `entry.fullPath.slice`
- `item.webkitGetAsEntry`

**Internal Comments:**
```
// TOFIX: setURLModifier() breaks when the file being loaded is not in root (x2)
```

<details><summary>Code</summary>

```typescript
function ( items, onDone ) {

		// TOFIX: setURLModifier() breaks when the file being loaded is not in root

		let itemsCount = 0;
		let itemsTotal = 0;

		const files = [];
		const filesMap = {};

		function onEntryHandled() {

			itemsCount ++;

			if ( itemsCount === itemsTotal ) {

				onDone( files, filesMap );

			}

		}

		function handleEntry( entry ) {

			if ( entry.isDirectory ) {

				const reader = entry.createReader();
				reader.readEntries( function ( entries ) {

					for ( let i = 0; i < entries.length; i ++ ) {

						handleEntry( entries[ i ] );

					}

					onEntryHandled();

				} );

			} else if ( entry.isFile ) {

				entry.file( function ( file ) {

					files.push( file );

					filesMap[ entry.fullPath.slice( 1 ) ] = file;
					onEntryHandled();

				} );

			}

			itemsTotal ++;

		}

		for ( let i = 0; i < items.length; i ++ ) {

			const item = items[ i ];

			if ( item.kind === 'file' ) {

				handleEntry( item.webkitGetAsEntry() );

			}

		}

	}
```
</details>

### `createFilesMap(files: any): {}`

**Parameters:**

- **`files`** `any`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
function ( files ) {

		const map = {};

		for ( let i = 0; i < files.length; i ++ ) {

			const file = files[ i ];
			map[ file.name ] = file;

		}

		return map;

	}
```
</details>

### `getFilesFromItemList(items: any, onDone: any): void`

**Parameters:**

- **`items`** `any`
- **`onDone`** `any`

**Returns:** `void`

**Calls:**

- `onDone`
- `entry.createReader`
- `reader.readEntries`
- `handleEntry`
- `onEntryHandled`
- `entry.file`
- `files.push`
- `entry.fullPath.slice`
- `item.webkitGetAsEntry`

**Internal Comments:**
```
// TOFIX: setURLModifier() breaks when the file being loaded is not in root (x2)
```

<details><summary>Code</summary>

```typescript
function ( items, onDone ) {

		// TOFIX: setURLModifier() breaks when the file being loaded is not in root

		let itemsCount = 0;
		let itemsTotal = 0;

		const files = [];
		const filesMap = {};

		function onEntryHandled() {

			itemsCount ++;

			if ( itemsCount === itemsTotal ) {

				onDone( files, filesMap );

			}

		}

		function handleEntry( entry ) {

			if ( entry.isDirectory ) {

				const reader = entry.createReader();
				reader.readEntries( function ( entries ) {

					for ( let i = 0; i < entries.length; i ++ ) {

						handleEntry( entries[ i ] );

					}

					onEntryHandled();

				} );

			} else if ( entry.isFile ) {

				entry.file( function ( file ) {

					files.push( file );

					filesMap[ entry.fullPath.slice( 1 ) ] = file;
					onEntryHandled();

				} );

			}

			itemsTotal ++;

		}

		for ( let i = 0; i < items.length; i ++ ) {

			const item = items[ i ];

			if ( item.kind === 'file' ) {

				handleEntry( item.webkitGetAsEntry() );

			}

		}

	}
```
</details>


---