[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `EventNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/EventNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `nodeObject` | `../tsl/TSLCore.js` |


---

## Functions

### `EventNode.update(frame: any): void`

**Parameters:**

- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `this.callback`

<details><summary>Code</summary>

```typescript
update( frame ) {

		this.callback( frame );

	}
```
</details>

### `createEvent(type: string, callback: Function): EventNode`

**Parameters:**

- **`type`** `string`
- **`callback`** `Function`

**Returns:** `EventNode`

**Calls:**

- `nodeObject( new EventNode( type, callback ) ).toStack`

<details><summary>Code</summary>

```typescript
( type, callback ) => nodeObject( new EventNode( type, callback ) ).toStack()
```
</details>

### `OnObjectUpdate(callback: Function): EventNode`

**Parameters:**

- **`callback`** `Function`

**Returns:** `EventNode`

**Calls:**

- `createEvent`

<details><summary>Code</summary>

```typescript
( callback ) => createEvent( EventNode.OBJECT, callback )
```
</details>

### `OnMaterialUpdate(callback: Function): EventNode`

**Parameters:**

- **`callback`** `Function`

**Returns:** `EventNode`

**Calls:**

- `createEvent`

<details><summary>Code</summary>

```typescript
( callback ) => createEvent( EventNode.MATERIAL, callback )
```
</details>


---

## Classes

### `EventNode`

<details><summary>Class Code</summary>

```ts
class EventNode extends Node {

	static get type() {

		return 'EventNode';

	}

	/**
	 * Creates an EventNode.
	 *
	 * @param {string} eventType - The type of event
	 * @param {Function} callback - The callback to execute on update.
	 */
	constructor( eventType, callback ) {

		super( 'void' );

		this.eventType = eventType;
		this.callback = callback;

		if ( eventType === EventNode.OBJECT ) {

			this.updateType = NodeUpdateType.OBJECT;

		} else if ( eventType === EventNode.MATERIAL ) {

			this.updateType = NodeUpdateType.RENDER;

		}

	}

	update( frame ) {

		this.callback( frame );

	}

}
```
</details>

#### Methods

##### `update(frame: any): void`

<details><summary>Code</summary>

```ts
update( frame ) {

		this.callback( frame );

	}
```
</details>


---