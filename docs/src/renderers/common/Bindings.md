[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Bindings.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Bindings.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataMap` | `./DataMap.js` |
| `AttributeType` | `./Constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `bindings` | `any` | let/var | `this.nodes.getForCompute( computeNode ).bindings` | ✗ |
| `attribute` | `any` | let/var | `binding.attribute` | ✗ |
| `attributeType` | `number` | let/var | `attribute.isIndirectStorageBufferAttribute ? AttributeType.INDIRECT : Attribu...` | ✗ |
| `needsBindingsUpdate` | `boolean` | let/var | `false` | ✗ |
| `cacheBindings` | `boolean` | let/var | `true` | ✗ |
| `cacheIndex` | `number` | let/var | `0` | ✗ |
| `version` | `number` | let/var | `0` | ✗ |
| `attribute` | `any` | let/var | `binding.attribute` | ✗ |
| `attributeType` | `number` | let/var | `attribute.isIndirectStorageBufferAttribute ? AttributeType.INDIRECT : Attribu...` | ✗ |
| `texture` | `any` | let/var | `binding.texture` | ✗ |


---

## Functions

### `Bindings.getForRender(renderObject: RenderObject): BindGroup[]`

**JSDoc:**
```typescript
/**
	 * Returns the bind groups for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {Array<BindGroup>} The bind groups.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `BindGroup[]`

**Calls:**

- `renderObject.getBindings`
- `this.get`
- `this._init`
- `this.backend.createBindings`

**Internal Comments:**
```
// each object defines an array of bindings (ubos, textures, samplers etc.) (x4)
```

<details><summary>Code</summary>

```typescript
getForRender( renderObject ) {

		const bindings = renderObject.getBindings();

		for ( const bindGroup of bindings ) {

			const groupData = this.get( bindGroup );

			if ( groupData.bindGroup === undefined ) {

				// each object defines an array of bindings (ubos, textures, samplers etc.)

				this._init( bindGroup );

				this.backend.createBindings( bindGroup, bindings, 0 );

				groupData.bindGroup = bindGroup;

			}

		}

		return bindings;

	}
```
</details>

### `Bindings.getForCompute(computeNode: Node): BindGroup[]`

**JSDoc:**
```typescript
/**
	 * Returns the bind groups for the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 * @return {Array<BindGroup>} The bind groups.
	 */
```

**Parameters:**

- **`computeNode`** `Node`

**Returns:** `BindGroup[]`

**Calls:**

- `this.nodes.getForCompute`
- `this.get`
- `this._init`
- `this.backend.createBindings`

<details><summary>Code</summary>

```typescript
getForCompute( computeNode ) {

		const bindings = this.nodes.getForCompute( computeNode ).bindings;

		for ( const bindGroup of bindings ) {

			const groupData = this.get( bindGroup );

			if ( groupData.bindGroup === undefined ) {

				this._init( bindGroup );

				this.backend.createBindings( bindGroup, bindings, 0 );

				groupData.bindGroup = bindGroup;

			}

		}

		return bindings;

	}
```
</details>

### `Bindings.updateForCompute(computeNode: Node): void`

**JSDoc:**
```typescript
/**
	 * Updates the bindings for the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 */
```

**Parameters:**

- **`computeNode`** `Node`

**Returns:** `void`

**Calls:**

- `this._updateBindings`
- `this.getForCompute`

<details><summary>Code</summary>

```typescript
updateForCompute( computeNode ) {

		this._updateBindings( this.getForCompute( computeNode ) );

	}
```
</details>

### `Bindings.updateForRender(renderObject: RenderObject): void`

**JSDoc:**
```typescript
/**
	 * Updates the bindings for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `void`

**Calls:**

- `this._updateBindings`
- `this.getForRender`

<details><summary>Code</summary>

```typescript
updateForRender( renderObject ) {

		this._updateBindings( this.getForRender( renderObject ) );

	}
```
</details>

### `Bindings._updateBindings(bindings: BindGroup[]): void`

**JSDoc:**
```typescript
/**
	 * Updates the given array of bindings.
	 *
	 * @param {Array<BindGroup>} bindings - The bind groups.
	 */
```

**Parameters:**

- **`bindings`** `BindGroup[]`

**Returns:** `void`

**Calls:**

- `this._update`

<details><summary>Code</summary>

```typescript
_updateBindings( bindings ) {

		for ( const bindGroup of bindings ) {

			this._update( bindGroup, bindings );

		}

	}
```
</details>

### `Bindings._init(bindGroup: BindGroup): void`

**JSDoc:**
```typescript
/**
	 * Initializes the given bind group.
	 *
	 * @param {BindGroup} bindGroup - The bind group to initialize.
	 */
```

**Parameters:**

- **`bindGroup`** `BindGroup`

**Returns:** `void`

**Calls:**

- `this.textures.updateTexture`
- `this.attributes.update`

<details><summary>Code</summary>

```typescript
_init( bindGroup ) {

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isSampledTexture ) {

				this.textures.updateTexture( binding.texture );

			} else if ( binding.isStorageBuffer ) {

				const attribute = binding.attribute;
				const attributeType = attribute.isIndirectStorageBufferAttribute ? AttributeType.INDIRECT : AttributeType.STORAGE;

				this.attributes.update( attribute, attributeType );

			}

		}

	}
```
</details>

### `Bindings._update(bindGroup: BindGroup, bindings: BindGroup[]): void`

**JSDoc:**
```typescript
/**
	 * Updates the given bind group.
	 *
	 * @param {BindGroup} bindGroup - The bind group to update.
	 * @param {Array<BindGroup>} bindings - The bind groups.
	 */
```

**Parameters:**

- **`bindGroup`** `BindGroup`
- **`bindings`** `BindGroup[]`

**Returns:** `void`

**Calls:**

- `this.nodes.updateGroup`
- `this.attributes.update`
- `binding.update`
- `backend.updateBinding`
- `this.textures.get`
- `this.textures.updateTexture`
- `backend.get`
- `this.get`
- `this.textures.needsMipmaps`
- `this.backend.generateMipmaps`
- `this.backend.updateBindings`

**Internal Comments:**
```
// iterate over all bindings and check if buffer updates or a new binding group is required
// every uniforms group is a uniform buffer. So if no update is required,
// we move one with the next binding. Otherwise the next if block will update the group.
// get the texture data after the update, to sync the texture reference from node (x2)
// version: update the texture data or create a new one (x5)
// generation: update the bindings if a new texture has been created
```

<details><summary>Code</summary>

```typescript
_update( bindGroup, bindings ) {

		const { backend } = this;

		let needsBindingsUpdate = false;
		let cacheBindings = true;
		let cacheIndex = 0;
		let version = 0;

		// iterate over all bindings and check if buffer updates or a new binding group is required

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isNodeUniformsGroup ) {

				const updated = this.nodes.updateGroup( binding );

				// every uniforms group is a uniform buffer. So if no update is required,
				// we move one with the next binding. Otherwise the next if block will update the group.

				if ( updated === false ) continue;

			}

			if ( binding.isStorageBuffer ) {

				const attribute = binding.attribute;
				const attributeType = attribute.isIndirectStorageBufferAttribute ? AttributeType.INDIRECT : AttributeType.STORAGE;

				this.attributes.update( attribute, attributeType );


			}

			if ( binding.isUniformBuffer ) {

				const updated = binding.update();

				if ( updated ) {

					backend.updateBinding( binding );

				}

			} else if ( binding.isSampledTexture ) {

				const updated = binding.update();

				// get the texture data after the update, to sync the texture reference from node

				const texture = binding.texture;
				const texturesTextureData = this.textures.get( texture );

				if ( updated ) {

					// version: update the texture data or create a new one

					this.textures.updateTexture( texture );

					// generation: update the bindings if a new texture has been created

					if ( binding.generation !== texturesTextureData.generation ) {

						binding.generation = texturesTextureData.generation;

						needsBindingsUpdate = true;

					}

				}

				const textureData = backend.get( texture );

				if ( textureData.externalTexture !== undefined || texturesTextureData.isDefaultTexture ) {

					cacheBindings = false;

				} else {

					cacheIndex = cacheIndex * 10 + texture.id;
					version += texture.version;

				}

				if ( texture.isStorageTexture === true ) {

					const textureData = this.get( texture );

					if ( binding.store === true ) {

						textureData.needsMipmap = true;

					} else if ( this.textures.needsMipmaps( texture ) && textureData.needsMipmap === true ) {

						this.backend.generateMipmaps( texture );

						textureData.needsMipmap = false;

					}

				}

			} else if ( binding.isSampler ) {

				binding.update();

			}

		}

		if ( needsBindingsUpdate === true ) {

			this.backend.updateBindings( bindGroup, bindings, cacheBindings ? cacheIndex : 0, version );

		}

	}
```
</details>


---

## Classes

### `Bindings`

<details><summary>Class Code</summary>

```ts
class Bindings extends DataMap {

	/**
	 * Constructs a new bindings management component.
	 *
	 * @param {Backend} backend - The renderer's backend.
	 * @param {Nodes} nodes - Renderer component for managing nodes related logic.
	 * @param {Textures} textures - Renderer component for managing textures.
	 * @param {Attributes} attributes - Renderer component for managing attributes.
	 * @param {Pipelines} pipelines - Renderer component for managing pipelines.
	 * @param {Info} info - Renderer component for managing metrics and monitoring data.
	 */
	constructor( backend, nodes, textures, attributes, pipelines, info ) {

		super();

		/**
		 * The renderer's backend.
		 *
		 * @type {Backend}
		 */
		this.backend = backend;

		/**
		 * Renderer component for managing textures.
		 *
		 * @type {Textures}
		 */
		this.textures = textures;

		/**
		 * Renderer component for managing pipelines.
		 *
		 * @type {Pipelines}
		 */
		this.pipelines = pipelines;

		/**
		 * Renderer component for managing attributes.
		 *
		 * @type {Attributes}
		 */
		this.attributes = attributes;

		/**
		 * Renderer component for managing nodes related logic.
		 *
		 * @type {Nodes}
		 */
		this.nodes = nodes;

		/**
		 * Renderer component for managing metrics and monitoring data.
		 *
		 * @type {Info}
		 */
		this.info = info;

		this.pipelines.bindings = this; // assign bindings to pipelines

	}

	/**
	 * Returns the bind groups for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {Array<BindGroup>} The bind groups.
	 */
	getForRender( renderObject ) {

		const bindings = renderObject.getBindings();

		for ( const bindGroup of bindings ) {

			const groupData = this.get( bindGroup );

			if ( groupData.bindGroup === undefined ) {

				// each object defines an array of bindings (ubos, textures, samplers etc.)

				this._init( bindGroup );

				this.backend.createBindings( bindGroup, bindings, 0 );

				groupData.bindGroup = bindGroup;

			}

		}

		return bindings;

	}

	/**
	 * Returns the bind groups for the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 * @return {Array<BindGroup>} The bind groups.
	 */
	getForCompute( computeNode ) {

		const bindings = this.nodes.getForCompute( computeNode ).bindings;

		for ( const bindGroup of bindings ) {

			const groupData = this.get( bindGroup );

			if ( groupData.bindGroup === undefined ) {

				this._init( bindGroup );

				this.backend.createBindings( bindGroup, bindings, 0 );

				groupData.bindGroup = bindGroup;

			}

		}

		return bindings;

	}

	/**
	 * Updates the bindings for the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 */
	updateForCompute( computeNode ) {

		this._updateBindings( this.getForCompute( computeNode ) );

	}

	/**
	 * Updates the bindings for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
	updateForRender( renderObject ) {

		this._updateBindings( this.getForRender( renderObject ) );

	}

	/**
	 * Updates the given array of bindings.
	 *
	 * @param {Array<BindGroup>} bindings - The bind groups.
	 */
	_updateBindings( bindings ) {

		for ( const bindGroup of bindings ) {

			this._update( bindGroup, bindings );

		}

	}

	/**
	 * Initializes the given bind group.
	 *
	 * @param {BindGroup} bindGroup - The bind group to initialize.
	 */
	_init( bindGroup ) {

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isSampledTexture ) {

				this.textures.updateTexture( binding.texture );

			} else if ( binding.isStorageBuffer ) {

				const attribute = binding.attribute;
				const attributeType = attribute.isIndirectStorageBufferAttribute ? AttributeType.INDIRECT : AttributeType.STORAGE;

				this.attributes.update( attribute, attributeType );

			}

		}

	}

	/**
	 * Updates the given bind group.
	 *
	 * @param {BindGroup} bindGroup - The bind group to update.
	 * @param {Array<BindGroup>} bindings - The bind groups.
	 */
	_update( bindGroup, bindings ) {

		const { backend } = this;

		let needsBindingsUpdate = false;
		let cacheBindings = true;
		let cacheIndex = 0;
		let version = 0;

		// iterate over all bindings and check if buffer updates or a new binding group is required

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isNodeUniformsGroup ) {

				const updated = this.nodes.updateGroup( binding );

				// every uniforms group is a uniform buffer. So if no update is required,
				// we move one with the next binding. Otherwise the next if block will update the group.

				if ( updated === false ) continue;

			}

			if ( binding.isStorageBuffer ) {

				const attribute = binding.attribute;
				const attributeType = attribute.isIndirectStorageBufferAttribute ? AttributeType.INDIRECT : AttributeType.STORAGE;

				this.attributes.update( attribute, attributeType );


			}

			if ( binding.isUniformBuffer ) {

				const updated = binding.update();

				if ( updated ) {

					backend.updateBinding( binding );

				}

			} else if ( binding.isSampledTexture ) {

				const updated = binding.update();

				// get the texture data after the update, to sync the texture reference from node

				const texture = binding.texture;
				const texturesTextureData = this.textures.get( texture );

				if ( updated ) {

					// version: update the texture data or create a new one

					this.textures.updateTexture( texture );

					// generation: update the bindings if a new texture has been created

					if ( binding.generation !== texturesTextureData.generation ) {

						binding.generation = texturesTextureData.generation;

						needsBindingsUpdate = true;

					}

				}

				const textureData = backend.get( texture );

				if ( textureData.externalTexture !== undefined || texturesTextureData.isDefaultTexture ) {

					cacheBindings = false;

				} else {

					cacheIndex = cacheIndex * 10 + texture.id;
					version += texture.version;

				}

				if ( texture.isStorageTexture === true ) {

					const textureData = this.get( texture );

					if ( binding.store === true ) {

						textureData.needsMipmap = true;

					} else if ( this.textures.needsMipmaps( texture ) && textureData.needsMipmap === true ) {

						this.backend.generateMipmaps( texture );

						textureData.needsMipmap = false;

					}

				}

			} else if ( binding.isSampler ) {

				binding.update();

			}

		}

		if ( needsBindingsUpdate === true ) {

			this.backend.updateBindings( bindGroup, bindings, cacheBindings ? cacheIndex : 0, version );

		}

	}

}
```
</details>

#### Methods

##### `getForRender(renderObject: RenderObject): BindGroup[]`

<details><summary>Code</summary>

```ts
getForRender( renderObject ) {

		const bindings = renderObject.getBindings();

		for ( const bindGroup of bindings ) {

			const groupData = this.get( bindGroup );

			if ( groupData.bindGroup === undefined ) {

				// each object defines an array of bindings (ubos, textures, samplers etc.)

				this._init( bindGroup );

				this.backend.createBindings( bindGroup, bindings, 0 );

				groupData.bindGroup = bindGroup;

			}

		}

		return bindings;

	}
```
</details>

##### `getForCompute(computeNode: Node): BindGroup[]`

<details><summary>Code</summary>

```ts
getForCompute( computeNode ) {

		const bindings = this.nodes.getForCompute( computeNode ).bindings;

		for ( const bindGroup of bindings ) {

			const groupData = this.get( bindGroup );

			if ( groupData.bindGroup === undefined ) {

				this._init( bindGroup );

				this.backend.createBindings( bindGroup, bindings, 0 );

				groupData.bindGroup = bindGroup;

			}

		}

		return bindings;

	}
```
</details>

##### `updateForCompute(computeNode: Node): void`

<details><summary>Code</summary>

```ts
updateForCompute( computeNode ) {

		this._updateBindings( this.getForCompute( computeNode ) );

	}
```
</details>

##### `updateForRender(renderObject: RenderObject): void`

<details><summary>Code</summary>

```ts
updateForRender( renderObject ) {

		this._updateBindings( this.getForRender( renderObject ) );

	}
```
</details>

##### `_updateBindings(bindings: BindGroup[]): void`

<details><summary>Code</summary>

```ts
_updateBindings( bindings ) {

		for ( const bindGroup of bindings ) {

			this._update( bindGroup, bindings );

		}

	}
```
</details>

##### `_init(bindGroup: BindGroup): void`

<details><summary>Code</summary>

```ts
_init( bindGroup ) {

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isSampledTexture ) {

				this.textures.updateTexture( binding.texture );

			} else if ( binding.isStorageBuffer ) {

				const attribute = binding.attribute;
				const attributeType = attribute.isIndirectStorageBufferAttribute ? AttributeType.INDIRECT : AttributeType.STORAGE;

				this.attributes.update( attribute, attributeType );

			}

		}

	}
```
</details>

##### `_update(bindGroup: BindGroup, bindings: BindGroup[]): void`

<details><summary>Code</summary>

```ts
_update( bindGroup, bindings ) {

		const { backend } = this;

		let needsBindingsUpdate = false;
		let cacheBindings = true;
		let cacheIndex = 0;
		let version = 0;

		// iterate over all bindings and check if buffer updates or a new binding group is required

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isNodeUniformsGroup ) {

				const updated = this.nodes.updateGroup( binding );

				// every uniforms group is a uniform buffer. So if no update is required,
				// we move one with the next binding. Otherwise the next if block will update the group.

				if ( updated === false ) continue;

			}

			if ( binding.isStorageBuffer ) {

				const attribute = binding.attribute;
				const attributeType = attribute.isIndirectStorageBufferAttribute ? AttributeType.INDIRECT : AttributeType.STORAGE;

				this.attributes.update( attribute, attributeType );


			}

			if ( binding.isUniformBuffer ) {

				const updated = binding.update();

				if ( updated ) {

					backend.updateBinding( binding );

				}

			} else if ( binding.isSampledTexture ) {

				const updated = binding.update();

				// get the texture data after the update, to sync the texture reference from node

				const texture = binding.texture;
				const texturesTextureData = this.textures.get( texture );

				if ( updated ) {

					// version: update the texture data or create a new one

					this.textures.updateTexture( texture );

					// generation: update the bindings if a new texture has been created

					if ( binding.generation !== texturesTextureData.generation ) {

						binding.generation = texturesTextureData.generation;

						needsBindingsUpdate = true;

					}

				}

				const textureData = backend.get( texture );

				if ( textureData.externalTexture !== undefined || texturesTextureData.isDefaultTexture ) {

					cacheBindings = false;

				} else {

					cacheIndex = cacheIndex * 10 + texture.id;
					version += texture.version;

				}

				if ( texture.isStorageTexture === true ) {

					const textureData = this.get( texture );

					if ( binding.store === true ) {

						textureData.needsMipmap = true;

					} else if ( this.textures.needsMipmaps( texture ) && textureData.needsMipmap === true ) {

						this.backend.generateMipmaps( texture );

						textureData.needsMipmap = false;

					}

				}

			} else if ( binding.isSampler ) {

				binding.update();

			}

		}

		if ( needsBindingsUpdate === true ) {

			this.backend.updateBindings( bindGroup, bindings, cacheBindings ? cacheIndex : 0, version );

		}

	}
```
</details>


---