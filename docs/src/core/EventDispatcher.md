[⬅️ Back to Table of Contents](../../index.md)

# 📄 `EventDispatcher.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/EventDispatcher.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `listeners` | `{}` | let/var | `this._listeners` | ✗ |
| `listeners` | `{}` | let/var | `this._listeners` | ✗ |
| `listeners` | `{}` | let/var | `this._listeners` | ✗ |
| `listenerArray` | `any` | let/var | `listeners[ type ]` | ✗ |
| `listeners` | `{}` | let/var | `this._listeners` | ✗ |
| `listenerArray` | `any` | let/var | `listeners[ event.type ]` | ✗ |


---

## Functions

### `EventDispatcher.addEventListener(type: string, listener: Function): void`

**JSDoc:**
```typescript
/**
	 * Adds the given event listener to the given event type.
	 *
	 * @param {string} type - The type of event to listen to.
	 * @param {Function} listener - The function that gets called when the event is fired.
	 */
```

**Parameters:**

- **`type`** `string`
- **`listener`** `Function`

**Returns:** `void`

**Calls:**

- `listeners[ type ].indexOf`
- `listeners[ type ].push`

<details><summary>Code</summary>

```typescript
addEventListener( type, listener ) {

		if ( this._listeners === undefined ) this._listeners = {};

		const listeners = this._listeners;

		if ( listeners[ type ] === undefined ) {

			listeners[ type ] = [];

		}

		if ( listeners[ type ].indexOf( listener ) === - 1 ) {

			listeners[ type ].push( listener );

		}

	}
```
</details>

### `EventDispatcher.hasEventListener(type: string, listener: Function): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given event listener has been added to the given event type.
	 *
	 * @param {string} type - The type of event.
	 * @param {Function} listener - The listener to check.
	 * @return {boolean} Whether the given event listener has been added to the given event type.
	 */
```

**Parameters:**

- **`type`** `string`
- **`listener`** `Function`

**Returns:** `boolean`

**Calls:**

- `listeners[ type ].indexOf`

<details><summary>Code</summary>

```typescript
hasEventListener( type, listener ) {

		const listeners = this._listeners;

		if ( listeners === undefined ) return false;

		return listeners[ type ] !== undefined && listeners[ type ].indexOf( listener ) !== - 1;

	}
```
</details>

### `EventDispatcher.removeEventListener(type: string, listener: Function): void`

**JSDoc:**
```typescript
/**
	 * Removes the given event listener from the given event type.
	 *
	 * @param {string} type - The type of event.
	 * @param {Function} listener - The listener to remove.
	 */
```

**Parameters:**

- **`type`** `string`
- **`listener`** `Function`

**Returns:** `void`

**Calls:**

- `listenerArray.indexOf`
- `listenerArray.splice`

<details><summary>Code</summary>

```typescript
removeEventListener( type, listener ) {

		const listeners = this._listeners;

		if ( listeners === undefined ) return;

		const listenerArray = listeners[ type ];

		if ( listenerArray !== undefined ) {

			const index = listenerArray.indexOf( listener );

			if ( index !== - 1 ) {

				listenerArray.splice( index, 1 );

			}

		}

	}
```
</details>

### `EventDispatcher.dispatchEvent(event: any): void`

**JSDoc:**
```typescript
/**
	 * Dispatches an event object.
	 *
	 * @param {Object} event - The event that gets fired.
	 */
```

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `listenerArray.slice`
- `array[ i ].call`

**Internal Comments:**
```
// Make a copy, in case listeners are removed while iterating. (x2)
```

<details><summary>Code</summary>

```typescript
dispatchEvent( event ) {

		const listeners = this._listeners;

		if ( listeners === undefined ) return;

		const listenerArray = listeners[ event.type ];

		if ( listenerArray !== undefined ) {

			event.target = this;

			// Make a copy, in case listeners are removed while iterating.
			const array = listenerArray.slice( 0 );

			for ( let i = 0, l = array.length; i < l; i ++ ) {

				array[ i ].call( this, event );

			}

			event.target = null;

		}

	}
```
</details>


---

## Classes

### `EventDispatcher`

<details><summary>Class Code</summary>

```ts
class EventDispatcher {

	/**
	 * Adds the given event listener to the given event type.
	 *
	 * @param {string} type - The type of event to listen to.
	 * @param {Function} listener - The function that gets called when the event is fired.
	 */
	addEventListener( type, listener ) {

		if ( this._listeners === undefined ) this._listeners = {};

		const listeners = this._listeners;

		if ( listeners[ type ] === undefined ) {

			listeners[ type ] = [];

		}

		if ( listeners[ type ].indexOf( listener ) === - 1 ) {

			listeners[ type ].push( listener );

		}

	}

	/**
	 * Returns `true` if the given event listener has been added to the given event type.
	 *
	 * @param {string} type - The type of event.
	 * @param {Function} listener - The listener to check.
	 * @return {boolean} Whether the given event listener has been added to the given event type.
	 */
	hasEventListener( type, listener ) {

		const listeners = this._listeners;

		if ( listeners === undefined ) return false;

		return listeners[ type ] !== undefined && listeners[ type ].indexOf( listener ) !== - 1;

	}

	/**
	 * Removes the given event listener from the given event type.
	 *
	 * @param {string} type - The type of event.
	 * @param {Function} listener - The listener to remove.
	 */
	removeEventListener( type, listener ) {

		const listeners = this._listeners;

		if ( listeners === undefined ) return;

		const listenerArray = listeners[ type ];

		if ( listenerArray !== undefined ) {

			const index = listenerArray.indexOf( listener );

			if ( index !== - 1 ) {

				listenerArray.splice( index, 1 );

			}

		}

	}

	/**
	 * Dispatches an event object.
	 *
	 * @param {Object} event - The event that gets fired.
	 */
	dispatchEvent( event ) {

		const listeners = this._listeners;

		if ( listeners === undefined ) return;

		const listenerArray = listeners[ event.type ];

		if ( listenerArray !== undefined ) {

			event.target = this;

			// Make a copy, in case listeners are removed while iterating.
			const array = listenerArray.slice( 0 );

			for ( let i = 0, l = array.length; i < l; i ++ ) {

				array[ i ].call( this, event );

			}

			event.target = null;

		}

	}

}
```
</details>

#### Methods

##### `addEventListener(type: string, listener: Function): void`

<details><summary>Code</summary>

```ts
addEventListener( type, listener ) {

		if ( this._listeners === undefined ) this._listeners = {};

		const listeners = this._listeners;

		if ( listeners[ type ] === undefined ) {

			listeners[ type ] = [];

		}

		if ( listeners[ type ].indexOf( listener ) === - 1 ) {

			listeners[ type ].push( listener );

		}

	}
```
</details>

##### `hasEventListener(type: string, listener: Function): boolean`

<details><summary>Code</summary>

```ts
hasEventListener( type, listener ) {

		const listeners = this._listeners;

		if ( listeners === undefined ) return false;

		return listeners[ type ] !== undefined && listeners[ type ].indexOf( listener ) !== - 1;

	}
```
</details>

##### `removeEventListener(type: string, listener: Function): void`

<details><summary>Code</summary>

```ts
removeEventListener( type, listener ) {

		const listeners = this._listeners;

		if ( listeners === undefined ) return;

		const listenerArray = listeners[ type ];

		if ( listenerArray !== undefined ) {

			const index = listenerArray.indexOf( listener );

			if ( index !== - 1 ) {

				listenerArray.splice( index, 1 );

			}

		}

	}
```
</details>

##### `dispatchEvent(event: any): void`

<details><summary>Code</summary>

```ts
dispatchEvent( event ) {

		const listeners = this._listeners;

		if ( listeners === undefined ) return;

		const listenerArray = listeners[ event.type ];

		if ( listenerArray !== undefined ) {

			event.target = this;

			// Make a copy, in case listeners are removed while iterating.
			const array = listenerArray.slice( 0 );

			for ( let i = 0, l = array.length; i < l; i ++ ) {

				array[ i ].call( this, event );

			}

			event.target = null;

		}

	}
```
</details>


---