[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Command.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/Command.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `output` | `{ type: string; id: number; name: str...` | let/var | `{}` | ✗ |


---

## Functions

### `Command.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = {};
		output.type = this.type;
		output.id = this.id;
		output.name = this.name;
		return output;

	}
```
</details>

### `Command.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		this.inMemory = true;
		this.type = json.type;
		this.id = json.id;
		this.name = json.name;

	}
```
</details>


---

## Classes

### `Command`

<details><summary>Class Code</summary>

```ts
class Command {

	/**
	 * @param {Editor} editor pointer to main editor object used to initialize
	 *        each command object with a reference to the editor
	 * @constructor
	 */
	constructor( editor ) {

		this.id = - 1;
		this.inMemory = false;
		this.updatable = false;
		this.type = '';
		this.name = '';
		this.editor = editor;

	}

	toJSON() {

		const output = {};
		output.type = this.type;
		output.id = this.id;
		output.name = this.name;
		return output;

	}

	fromJSON( json ) {

		this.inMemory = true;
		this.type = json.type;
		this.id = json.id;
		this.name = json.name;

	}

}
```
</details>

#### Methods

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = {};
		output.type = this.type;
		output.id = this.id;
		output.name = this.name;
		return output;

	}
```
</details>

##### `fromJSON(json: any): void`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		this.inMemory = true;
		this.type = json.type;
		this.id = json.id;
		this.name = json.name;

	}
```
</details>


---