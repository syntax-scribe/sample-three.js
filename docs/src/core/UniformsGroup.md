[⬅️ Back to Table of Contents](../../index.md)

# 📄 `UniformsGroup.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/UniformsGroup.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `EventDispatcher` | `./EventDispatcher.js` |
| `StaticDrawUsage` | `../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |
| `uniformsSource` | `Uniform[]` | let/var | `source.uniforms` | ✗ |
| `uniforms` | `any` | let/var | `Array.isArray( uniformsSource[ i ] ) ? uniformsSource[ i ] : [ uniformsSource...` | ✗ |


---

## Functions

### `UniformsGroup.add(uniform: Uniform): UniformsGroup`

**JSDoc:**
```typescript
/**
	 * Adds the given uniform to this uniforms group.
	 *
	 * @param {Uniform} uniform - The uniform to add.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
```

**Parameters:**

- **`uniform`** `Uniform`

**Returns:** `UniformsGroup`

**Calls:**

- `this.uniforms.push`

<details><summary>Code</summary>

```typescript
add( uniform ) {

		this.uniforms.push( uniform );

		return this;

	}
```
</details>

### `UniformsGroup.remove(uniform: Uniform): UniformsGroup`

**JSDoc:**
```typescript
/**
	 * Removes the given uniform from this uniforms group.
	 *
	 * @param {Uniform} uniform - The uniform to remove.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
```

**Parameters:**

- **`uniform`** `Uniform`

**Returns:** `UniformsGroup`

**Calls:**

- `this.uniforms.indexOf`
- `this.uniforms.splice`

<details><summary>Code</summary>

```typescript
remove( uniform ) {

		const index = this.uniforms.indexOf( uniform );

		if ( index !== - 1 ) this.uniforms.splice( index, 1 );

		return this;

	}
```
</details>

### `UniformsGroup.setName(name: string): UniformsGroup`

**JSDoc:**
```typescript
/**
	 * Sets the name of this uniforms group.
	 *
	 * @param {string} name - The name to set.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `UniformsGroup`

<details><summary>Code</summary>

```typescript
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

### `UniformsGroup.setUsage(value: any): UniformsGroup`

**JSDoc:**
```typescript
/**
	 * Sets the usage of this uniforms group.
	 *
	 * @param {(StaticDrawUsage|DynamicDrawUsage|StreamDrawUsage|StaticReadUsage|DynamicReadUsage|StreamReadUsage|StaticCopyUsage|DynamicCopyUsage|StreamCopyUsage)} value - The usage to set.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `UniformsGroup`

<details><summary>Code</summary>

```typescript
setUsage( value ) {

		this.usage = value;

		return this;

	}
```
</details>

### `UniformsGroup.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 *
	 * @fires Texture#dispose
	 */
```

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}
```
</details>

### `UniformsGroup.copy(source: UniformsGroup): UniformsGroup`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given uniforms group to this instance.
	 *
	 * @param {UniformsGroup} source - The uniforms group to copy.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
```

**Parameters:**

- **`source`** `UniformsGroup`

**Returns:** `UniformsGroup`

**Calls:**

- `Array.isArray`
- `this.uniforms.push`
- `uniforms[ j ].clone`

<details><summary>Code</summary>

```typescript
copy( source ) {

		this.name = source.name;
		this.usage = source.usage;

		const uniformsSource = source.uniforms;

		this.uniforms.length = 0;

		for ( let i = 0, l = uniformsSource.length; i < l; i ++ ) {

			const uniforms = Array.isArray( uniformsSource[ i ] ) ? uniformsSource[ i ] : [ uniformsSource[ i ] ];

			for ( let j = 0; j < uniforms.length; j ++ ) {

				this.uniforms.push( uniforms[ j ].clone() );

			}

		}

		return this;

	}
```
</details>

### `UniformsGroup.clone(): UniformsGroup`

**JSDoc:**
```typescript
/**
	 * Returns a new uniforms group with copied values from this instance.
	 *
	 * @return {UniformsGroup} A clone of this instance.
	 */
```

**Returns:** `UniformsGroup`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---

## Classes

### `UniformsGroup`

<details><summary>Class Code</summary>

```ts
class UniformsGroup extends EventDispatcher {

	/**
	 * Constructs a new uniforms group.
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
		this.isUniformsGroup = true;

		/**
		 * The ID of the 3D object.
		 *
		 * @name UniformsGroup#id
		 * @type {number}
		 * @readonly
		 */
		Object.defineProperty( this, 'id', { value: _id ++ } );

		/**
		 * The name of the uniforms group.
		 *
		 * @type {string}
		 */
		this.name = '';

		/**
		 * The buffer usage.
		 *
		 * @type {(StaticDrawUsage|DynamicDrawUsage|StreamDrawUsage|StaticReadUsage|DynamicReadUsage|StreamReadUsage|StaticCopyUsage|DynamicCopyUsage|StreamCopyUsage)}
		 * @default StaticDrawUsage
		 */
		this.usage = StaticDrawUsage;

		/**
		 * An array holding the uniforms.
		 *
		 * @type {Array<Uniform>}
		 */
		this.uniforms = [];

	}

	/**
	 * Adds the given uniform to this uniforms group.
	 *
	 * @param {Uniform} uniform - The uniform to add.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
	add( uniform ) {

		this.uniforms.push( uniform );

		return this;

	}

	/**
	 * Removes the given uniform from this uniforms group.
	 *
	 * @param {Uniform} uniform - The uniform to remove.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
	remove( uniform ) {

		const index = this.uniforms.indexOf( uniform );

		if ( index !== - 1 ) this.uniforms.splice( index, 1 );

		return this;

	}

	/**
	 * Sets the name of this uniforms group.
	 *
	 * @param {string} name - The name to set.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
	setName( name ) {

		this.name = name;

		return this;

	}

	/**
	 * Sets the usage of this uniforms group.
	 *
	 * @param {(StaticDrawUsage|DynamicDrawUsage|StreamDrawUsage|StaticReadUsage|DynamicReadUsage|StreamReadUsage|StaticCopyUsage|DynamicCopyUsage|StreamCopyUsage)} value - The usage to set.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
	setUsage( value ) {

		this.usage = value;

		return this;

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 *
	 * @fires Texture#dispose
	 */
	dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}

	/**
	 * Copies the values of the given uniforms group to this instance.
	 *
	 * @param {UniformsGroup} source - The uniforms group to copy.
	 * @return {UniformsGroup} A reference to this uniforms group.
	 */
	copy( source ) {

		this.name = source.name;
		this.usage = source.usage;

		const uniformsSource = source.uniforms;

		this.uniforms.length = 0;

		for ( let i = 0, l = uniformsSource.length; i < l; i ++ ) {

			const uniforms = Array.isArray( uniformsSource[ i ] ) ? uniformsSource[ i ] : [ uniformsSource[ i ] ];

			for ( let j = 0; j < uniforms.length; j ++ ) {

				this.uniforms.push( uniforms[ j ].clone() );

			}

		}

		return this;

	}

	/**
	 * Returns a new uniforms group with copied values from this instance.
	 *
	 * @return {UniformsGroup} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

}
```
</details>

#### Methods

##### `add(uniform: Uniform): UniformsGroup`

<details><summary>Code</summary>

```ts
add( uniform ) {

		this.uniforms.push( uniform );

		return this;

	}
```
</details>

##### `remove(uniform: Uniform): UniformsGroup`

<details><summary>Code</summary>

```ts
remove( uniform ) {

		const index = this.uniforms.indexOf( uniform );

		if ( index !== - 1 ) this.uniforms.splice( index, 1 );

		return this;

	}
```
</details>

##### `setName(name: string): UniformsGroup`

<details><summary>Code</summary>

```ts
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

##### `setUsage(value: any): UniformsGroup`

<details><summary>Code</summary>

```ts
setUsage( value ) {

		this.usage = value;

		return this;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}
```
</details>

##### `copy(source: UniformsGroup): UniformsGroup`

<details><summary>Code</summary>

```ts
copy( source ) {

		this.name = source.name;
		this.usage = source.usage;

		const uniformsSource = source.uniforms;

		this.uniforms.length = 0;

		for ( let i = 0, l = uniformsSource.length; i < l; i ++ ) {

			const uniforms = Array.isArray( uniformsSource[ i ] ) ? uniformsSource[ i ] : [ uniformsSource[ i ] ];

			for ( let j = 0; j < uniforms.length; j ++ ) {

				this.uniforms.push( uniforms[ j ].clone() );

			}

		}

		return this;

	}
```
</details>

##### `clone(): UniformsGroup`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---