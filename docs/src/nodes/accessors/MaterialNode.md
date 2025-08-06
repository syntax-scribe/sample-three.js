[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MaterialNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/MaterialNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `reference` | `./ReferenceNode.js` |
| `materialReference` | `./MaterialReferenceNode.js` |
| `normalView` | `./Normal.js` |
| `nodeImmutable` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `mat2` | `../tsl/TSLBase.js` |
| `uniform` | `../core/UniformNode.js` |
| `normalMap` | `../display/NormalMapNode.js` |
| `bumpMap` | `../display/BumpMapNode.js` |
| `Vector2` | `../../math/Vector2.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_propertyCache` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `material` | `any` | let/var | `builder.context.material` | ✗ |
| `scope` | `string` | let/var | `this.scope` | ✗ |
| `node` | `any` | let/var | `null` | ✗ |
| `colorNode` | `any` | let/var | `material.color !== undefined ? this.getColor( scope ) : vec3()` | ✗ |


---

## Functions

### `MaterialNode.getCache(property: string, type: string): MaterialReferenceNode`

**JSDoc:**
```typescript
/**
	 * Returns a cached reference node for the given property and type.
	 *
	 * @param {string} property - The name of the material property.
	 * @param {string} type - The uniform type of the property.
	 * @return {MaterialReferenceNode} A material reference node representing the property access.
	 */
```

**Parameters:**

- **`property`** `string`
- **`type`** `string`

**Returns:** `MaterialReferenceNode`

**Calls:**

- `_propertyCache.get`
- `materialReference (from ./MaterialReferenceNode.js)`
- `_propertyCache.set`

<details><summary>Code</summary>

```typescript
getCache( property, type ) {

		let node = _propertyCache.get( property );

		if ( node === undefined ) {

			node = materialReference( property, type );

			_propertyCache.set( property, node );

		}

		return node;

	}
```
</details>

### `MaterialNode.getFloat(property: string): MaterialReferenceNode<any>`

**JSDoc:**
```typescript
/**
	 * Returns a float-typed material reference node for the given property name.
	 *
	 * @param {string} property - The name of the material property.
	 * @return {MaterialReferenceNode<float>} A material reference node representing the property access.
	 */
```

**Parameters:**

- **`property`** `string`

**Returns:** `MaterialReferenceNode<any>`

**Calls:**

- `this.getCache`

<details><summary>Code</summary>

```typescript
getFloat( property ) {

		return this.getCache( property, 'float' );

	}
```
</details>

### `MaterialNode.getColor(property: string): MaterialReferenceNode<color>`

**JSDoc:**
```typescript
/**
	 * Returns a color-typed material reference node for the given property name.
	 *
	 * @param {string} property - The name of the material property.
	 * @return {MaterialReferenceNode<color>} A material reference node representing the property access.
	 */
```

**Parameters:**

- **`property`** `string`

**Returns:** `MaterialReferenceNode<color>`

**Calls:**

- `this.getCache`

<details><summary>Code</summary>

```typescript
getColor( property ) {

		return this.getCache( property, 'color' );

	}
```
</details>

### `MaterialNode.getTexture(property: string): MaterialReferenceNode`

**JSDoc:**
```typescript
/**
	 * Returns a texture-typed material reference node for the given property name.
	 *
	 * @param {string} property - The name of the material property.
	 * @return {MaterialReferenceNode} A material reference node representing the property access.
	 */
```

**Parameters:**

- **`property`** `string`

**Returns:** `MaterialReferenceNode`

**Calls:**

- `this.getCache`

<details><summary>Code</summary>

```typescript
getTexture( property ) {

		return this.getCache( property === 'map' ? 'map' : property + 'Map', 'texture' );

	}
```
</details>

### `MaterialNode.setup(builder: NodeBuilder): Node`

**JSDoc:**
```typescript
/**
	 * The node setup is done depending on the selected scope. Multiple material properties
	 * might be grouped into a single node composition if they logically belong together.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The node representing the selected scope.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `Node`

**Calls:**

- `this.getColor`
- `vec3 (from ../tsl/TSLBase.js)`
- `colorNode.mul`
- `this.getTexture`
- `this.getFloat`
- `opacityNode.mul`
- `float (from ../tsl/TSLBase.js)`
- `specularIntensityNode.mul`
- `specularColorNode.mul`
- `roughnessNode.mul`
- `metalnessNode.mul`
- `this.getColor( scope ).mul`
- `emissiveNode.mul`
- `normalMap (from ../display/NormalMapNode.js)`
- `this.getCache`
- `bumpMap (from ../display/BumpMapNode.js)`
- `clearcoatNode.mul`
- `clearcoatRoughnessNode.mul`
- `this.getColor( 'sheenColor' ).mul`
- `sheenNode.mul`
- `sheenRoughnessNode.mul`
- `node.clamp`
- `mat2 (from ../tsl/TSLBase.js)`
- `materialAnisotropyVector.y.negate`
- `anisotropyMat.mul`
- `anisotropyPolar.rg.mul( 2.0 ).sub( vec2( 1.0 ) ).normalize().mul`
- `reference (from ./ReferenceNode.js)`
- `iridescenceThicknessMaximum.sub( iridescenceThicknessMinimum ).mul( this.getTexture( scope ).g ).add`
- `transmissionNode.mul`
- `thicknessNode.mul`
- `this.getTexture( scope ).rgb.mul`
- `this.getTexture( scope ).r.sub( 1.0 ).mul( this.getFloat( 'aoMapIntensity' ) ).add`
- `this.getNodeType`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const material = builder.context.material;
		const scope = this.scope;

		let node = null;

		if ( scope === MaterialNode.COLOR ) {

			const colorNode = material.color !== undefined ? this.getColor( scope ) : vec3();

			if ( material.map && material.map.isTexture === true ) {

				node = colorNode.mul( this.getTexture( 'map' ) );

			} else {

				node = colorNode;

			}

		} else if ( scope === MaterialNode.OPACITY ) {

			const opacityNode = this.getFloat( scope );

			if ( material.alphaMap && material.alphaMap.isTexture === true ) {

				node = opacityNode.mul( this.getTexture( 'alpha' ) );

			} else {

				node = opacityNode;

			}

		} else if ( scope === MaterialNode.SPECULAR_STRENGTH ) {

			if ( material.specularMap && material.specularMap.isTexture === true ) {

				node = this.getTexture( 'specular' ).r;

			} else {

				node = float( 1 );

			}

		} else if ( scope === MaterialNode.SPECULAR_INTENSITY ) {

			const specularIntensityNode = this.getFloat( scope );

			if ( material.specularIntensityMap && material.specularIntensityMap.isTexture === true ) {

				node = specularIntensityNode.mul( this.getTexture( scope ).a );

			} else {

				node = specularIntensityNode;

			}

		} else if ( scope === MaterialNode.SPECULAR_COLOR ) {

			const specularColorNode = this.getColor( scope );

			if ( material.specularColorMap && material.specularColorMap.isTexture === true ) {

				node = specularColorNode.mul( this.getTexture( scope ).rgb );

			} else {

				node = specularColorNode;

			}

		} else if ( scope === MaterialNode.ROUGHNESS ) { // TODO: cleanup similar branches

			const roughnessNode = this.getFloat( scope );

			if ( material.roughnessMap && material.roughnessMap.isTexture === true ) {

				node = roughnessNode.mul( this.getTexture( scope ).g );

			} else {

				node = roughnessNode;

			}

		} else if ( scope === MaterialNode.METALNESS ) {

			const metalnessNode = this.getFloat( scope );

			if ( material.metalnessMap && material.metalnessMap.isTexture === true ) {

				node = metalnessNode.mul( this.getTexture( scope ).b );

			} else {

				node = metalnessNode;

			}

		} else if ( scope === MaterialNode.EMISSIVE ) {

			const emissiveIntensityNode = this.getFloat( 'emissiveIntensity' );
			const emissiveNode = this.getColor( scope ).mul( emissiveIntensityNode );

			if ( material.emissiveMap && material.emissiveMap.isTexture === true ) {

				node = emissiveNode.mul( this.getTexture( scope ) );

			} else {

				node = emissiveNode;

			}

		} else if ( scope === MaterialNode.NORMAL ) {

			if ( material.normalMap ) {

				node = normalMap( this.getTexture( 'normal' ), this.getCache( 'normalScale', 'vec2' ) );
				node.normalMapType = material.normalMapType;

			} else if ( material.bumpMap ) {

				node = bumpMap( this.getTexture( 'bump' ).r, this.getFloat( 'bumpScale' ) );

			} else {

				node = normalView;

			}

		} else if ( scope === MaterialNode.CLEARCOAT ) {

			const clearcoatNode = this.getFloat( scope );

			if ( material.clearcoatMap && material.clearcoatMap.isTexture === true ) {

				node = clearcoatNode.mul( this.getTexture( scope ).r );

			} else {

				node = clearcoatNode;

			}

		} else if ( scope === MaterialNode.CLEARCOAT_ROUGHNESS ) {

			const clearcoatRoughnessNode = this.getFloat( scope );

			if ( material.clearcoatRoughnessMap && material.clearcoatRoughnessMap.isTexture === true ) {

				node = clearcoatRoughnessNode.mul( this.getTexture( scope ).r );

			} else {

				node = clearcoatRoughnessNode;

			}

		} else if ( scope === MaterialNode.CLEARCOAT_NORMAL ) {

			if ( material.clearcoatNormalMap ) {

				node = normalMap( this.getTexture( scope ), this.getCache( scope + 'Scale', 'vec2' ) );

			} else {

				node = normalView;

			}

		} else if ( scope === MaterialNode.SHEEN ) {

			const sheenNode = this.getColor( 'sheenColor' ).mul( this.getFloat( 'sheen' ) ); // Move this mul() to CPU

			if ( material.sheenColorMap && material.sheenColorMap.isTexture === true ) {

				node = sheenNode.mul( this.getTexture( 'sheenColor' ).rgb );

			} else {

				node = sheenNode;

			}

		} else if ( scope === MaterialNode.SHEEN_ROUGHNESS ) {

			const sheenRoughnessNode = this.getFloat( scope );

			if ( material.sheenRoughnessMap && material.sheenRoughnessMap.isTexture === true ) {

				node = sheenRoughnessNode.mul( this.getTexture( scope ).a );

			} else {

				node = sheenRoughnessNode;

			}

			node = node.clamp( 0.07, 1.0 );

		} else if ( scope === MaterialNode.ANISOTROPY ) {

			if ( material.anisotropyMap && material.anisotropyMap.isTexture === true ) {

				const anisotropyPolar = this.getTexture( scope );
				const anisotropyMat = mat2( materialAnisotropyVector.x, materialAnisotropyVector.y, materialAnisotropyVector.y.negate(), materialAnisotropyVector.x );

				node = anisotropyMat.mul( anisotropyPolar.rg.mul( 2.0 ).sub( vec2( 1.0 ) ).normalize().mul( anisotropyPolar.b ) );

			} else {

				node = materialAnisotropyVector;

			}

		} else if ( scope === MaterialNode.IRIDESCENCE_THICKNESS ) {

			const iridescenceThicknessMaximum = reference( '1', 'float', material.iridescenceThicknessRange );

			if ( material.iridescenceThicknessMap ) {

				const iridescenceThicknessMinimum = reference( '0', 'float', material.iridescenceThicknessRange );

				node = iridescenceThicknessMaximum.sub( iridescenceThicknessMinimum ).mul( this.getTexture( scope ).g ).add( iridescenceThicknessMinimum );

			} else {

				node = iridescenceThicknessMaximum;

			}

		} else if ( scope === MaterialNode.TRANSMISSION ) {

			const transmissionNode = this.getFloat( scope );

			if ( material.transmissionMap ) {

				node = transmissionNode.mul( this.getTexture( scope ).r );

			} else {

				node = transmissionNode;

			}

		} else if ( scope === MaterialNode.THICKNESS ) {

			const thicknessNode = this.getFloat( scope );

			if ( material.thicknessMap ) {

				node = thicknessNode.mul( this.getTexture( scope ).g );

			} else {

				node = thicknessNode;

			}

		} else if ( scope === MaterialNode.IOR ) {

			node = this.getFloat( scope );

		} else if ( scope === MaterialNode.LIGHT_MAP ) {

			node = this.getTexture( scope ).rgb.mul( this.getFloat( 'lightMapIntensity' ) );

		} else if ( scope === MaterialNode.AO ) {

			node = this.getTexture( scope ).r.sub( 1.0 ).mul( this.getFloat( 'aoMapIntensity' ) ).add( 1.0 );

		} else if ( scope === MaterialNode.LINE_DASH_OFFSET ) {

			node = ( material.dashOffset ) ? this.getFloat( scope ) : float( 0 );

		} else {

			const outputType = this.getNodeType( builder );

			node = this.getCache( scope, outputType );

		}

		return node;

	}
```
</details>


---

## Classes

### `MaterialNode`

<details><summary>Class Code</summary>

```ts
class MaterialNode extends Node {

	static get type() {

		return 'MaterialNode';

	}

	/**
	 * Constructs a new material node.
	 *
	 * @param {string} scope - The scope defines what kind of material property is referred by the node.
	 */
	constructor( scope ) {

		super();

		/**
		 * The scope defines what material property is referred by the node.
		 *
		 * @type {string}
		 */
		this.scope = scope;

	}

	/**
	 * Returns a cached reference node for the given property and type.
	 *
	 * @param {string} property - The name of the material property.
	 * @param {string} type - The uniform type of the property.
	 * @return {MaterialReferenceNode} A material reference node representing the property access.
	 */
	getCache( property, type ) {

		let node = _propertyCache.get( property );

		if ( node === undefined ) {

			node = materialReference( property, type );

			_propertyCache.set( property, node );

		}

		return node;

	}

	/**
	 * Returns a float-typed material reference node for the given property name.
	 *
	 * @param {string} property - The name of the material property.
	 * @return {MaterialReferenceNode<float>} A material reference node representing the property access.
	 */
	getFloat( property ) {

		return this.getCache( property, 'float' );

	}

	/**
	 * Returns a color-typed material reference node for the given property name.
	 *
	 * @param {string} property - The name of the material property.
	 * @return {MaterialReferenceNode<color>} A material reference node representing the property access.
	 */
	getColor( property ) {

		return this.getCache( property, 'color' );

	}

	/**
	 * Returns a texture-typed material reference node for the given property name.
	 *
	 * @param {string} property - The name of the material property.
	 * @return {MaterialReferenceNode} A material reference node representing the property access.
	 */
	getTexture( property ) {

		return this.getCache( property === 'map' ? 'map' : property + 'Map', 'texture' );

	}

	/**
	 * The node setup is done depending on the selected scope. Multiple material properties
	 * might be grouped into a single node composition if they logically belong together.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The node representing the selected scope.
	 */
	setup( builder ) {

		const material = builder.context.material;
		const scope = this.scope;

		let node = null;

		if ( scope === MaterialNode.COLOR ) {

			const colorNode = material.color !== undefined ? this.getColor( scope ) : vec3();

			if ( material.map && material.map.isTexture === true ) {

				node = colorNode.mul( this.getTexture( 'map' ) );

			} else {

				node = colorNode;

			}

		} else if ( scope === MaterialNode.OPACITY ) {

			const opacityNode = this.getFloat( scope );

			if ( material.alphaMap && material.alphaMap.isTexture === true ) {

				node = opacityNode.mul( this.getTexture( 'alpha' ) );

			} else {

				node = opacityNode;

			}

		} else if ( scope === MaterialNode.SPECULAR_STRENGTH ) {

			if ( material.specularMap && material.specularMap.isTexture === true ) {

				node = this.getTexture( 'specular' ).r;

			} else {

				node = float( 1 );

			}

		} else if ( scope === MaterialNode.SPECULAR_INTENSITY ) {

			const specularIntensityNode = this.getFloat( scope );

			if ( material.specularIntensityMap && material.specularIntensityMap.isTexture === true ) {

				node = specularIntensityNode.mul( this.getTexture( scope ).a );

			} else {

				node = specularIntensityNode;

			}

		} else if ( scope === MaterialNode.SPECULAR_COLOR ) {

			const specularColorNode = this.getColor( scope );

			if ( material.specularColorMap && material.specularColorMap.isTexture === true ) {

				node = specularColorNode.mul( this.getTexture( scope ).rgb );

			} else {

				node = specularColorNode;

			}

		} else if ( scope === MaterialNode.ROUGHNESS ) { // TODO: cleanup similar branches

			const roughnessNode = this.getFloat( scope );

			if ( material.roughnessMap && material.roughnessMap.isTexture === true ) {

				node = roughnessNode.mul( this.getTexture( scope ).g );

			} else {

				node = roughnessNode;

			}

		} else if ( scope === MaterialNode.METALNESS ) {

			const metalnessNode = this.getFloat( scope );

			if ( material.metalnessMap && material.metalnessMap.isTexture === true ) {

				node = metalnessNode.mul( this.getTexture( scope ).b );

			} else {

				node = metalnessNode;

			}

		} else if ( scope === MaterialNode.EMISSIVE ) {

			const emissiveIntensityNode = this.getFloat( 'emissiveIntensity' );
			const emissiveNode = this.getColor( scope ).mul( emissiveIntensityNode );

			if ( material.emissiveMap && material.emissiveMap.isTexture === true ) {

				node = emissiveNode.mul( this.getTexture( scope ) );

			} else {

				node = emissiveNode;

			}

		} else if ( scope === MaterialNode.NORMAL ) {

			if ( material.normalMap ) {

				node = normalMap( this.getTexture( 'normal' ), this.getCache( 'normalScale', 'vec2' ) );
				node.normalMapType = material.normalMapType;

			} else if ( material.bumpMap ) {

				node = bumpMap( this.getTexture( 'bump' ).r, this.getFloat( 'bumpScale' ) );

			} else {

				node = normalView;

			}

		} else if ( scope === MaterialNode.CLEARCOAT ) {

			const clearcoatNode = this.getFloat( scope );

			if ( material.clearcoatMap && material.clearcoatMap.isTexture === true ) {

				node = clearcoatNode.mul( this.getTexture( scope ).r );

			} else {

				node = clearcoatNode;

			}

		} else if ( scope === MaterialNode.CLEARCOAT_ROUGHNESS ) {

			const clearcoatRoughnessNode = this.getFloat( scope );

			if ( material.clearcoatRoughnessMap && material.clearcoatRoughnessMap.isTexture === true ) {

				node = clearcoatRoughnessNode.mul( this.getTexture( scope ).r );

			} else {

				node = clearcoatRoughnessNode;

			}

		} else if ( scope === MaterialNode.CLEARCOAT_NORMAL ) {

			if ( material.clearcoatNormalMap ) {

				node = normalMap( this.getTexture( scope ), this.getCache( scope + 'Scale', 'vec2' ) );

			} else {

				node = normalView;

			}

		} else if ( scope === MaterialNode.SHEEN ) {

			const sheenNode = this.getColor( 'sheenColor' ).mul( this.getFloat( 'sheen' ) ); // Move this mul() to CPU

			if ( material.sheenColorMap && material.sheenColorMap.isTexture === true ) {

				node = sheenNode.mul( this.getTexture( 'sheenColor' ).rgb );

			} else {

				node = sheenNode;

			}

		} else if ( scope === MaterialNode.SHEEN_ROUGHNESS ) {

			const sheenRoughnessNode = this.getFloat( scope );

			if ( material.sheenRoughnessMap && material.sheenRoughnessMap.isTexture === true ) {

				node = sheenRoughnessNode.mul( this.getTexture( scope ).a );

			} else {

				node = sheenRoughnessNode;

			}

			node = node.clamp( 0.07, 1.0 );

		} else if ( scope === MaterialNode.ANISOTROPY ) {

			if ( material.anisotropyMap && material.anisotropyMap.isTexture === true ) {

				const anisotropyPolar = this.getTexture( scope );
				const anisotropyMat = mat2( materialAnisotropyVector.x, materialAnisotropyVector.y, materialAnisotropyVector.y.negate(), materialAnisotropyVector.x );

				node = anisotropyMat.mul( anisotropyPolar.rg.mul( 2.0 ).sub( vec2( 1.0 ) ).normalize().mul( anisotropyPolar.b ) );

			} else {

				node = materialAnisotropyVector;

			}

		} else if ( scope === MaterialNode.IRIDESCENCE_THICKNESS ) {

			const iridescenceThicknessMaximum = reference( '1', 'float', material.iridescenceThicknessRange );

			if ( material.iridescenceThicknessMap ) {

				const iridescenceThicknessMinimum = reference( '0', 'float', material.iridescenceThicknessRange );

				node = iridescenceThicknessMaximum.sub( iridescenceThicknessMinimum ).mul( this.getTexture( scope ).g ).add( iridescenceThicknessMinimum );

			} else {

				node = iridescenceThicknessMaximum;

			}

		} else if ( scope === MaterialNode.TRANSMISSION ) {

			const transmissionNode = this.getFloat( scope );

			if ( material.transmissionMap ) {

				node = transmissionNode.mul( this.getTexture( scope ).r );

			} else {

				node = transmissionNode;

			}

		} else if ( scope === MaterialNode.THICKNESS ) {

			const thicknessNode = this.getFloat( scope );

			if ( material.thicknessMap ) {

				node = thicknessNode.mul( this.getTexture( scope ).g );

			} else {

				node = thicknessNode;

			}

		} else if ( scope === MaterialNode.IOR ) {

			node = this.getFloat( scope );

		} else if ( scope === MaterialNode.LIGHT_MAP ) {

			node = this.getTexture( scope ).rgb.mul( this.getFloat( 'lightMapIntensity' ) );

		} else if ( scope === MaterialNode.AO ) {

			node = this.getTexture( scope ).r.sub( 1.0 ).mul( this.getFloat( 'aoMapIntensity' ) ).add( 1.0 );

		} else if ( scope === MaterialNode.LINE_DASH_OFFSET ) {

			node = ( material.dashOffset ) ? this.getFloat( scope ) : float( 0 );

		} else {

			const outputType = this.getNodeType( builder );

			node = this.getCache( scope, outputType );

		}

		return node;

	}

}
```
</details>

#### Methods

##### `getCache(property: string, type: string): MaterialReferenceNode`

<details><summary>Code</summary>

```ts
getCache( property, type ) {

		let node = _propertyCache.get( property );

		if ( node === undefined ) {

			node = materialReference( property, type );

			_propertyCache.set( property, node );

		}

		return node;

	}
```
</details>

##### `getFloat(property: string): MaterialReferenceNode<any>`

<details><summary>Code</summary>

```ts
getFloat( property ) {

		return this.getCache( property, 'float' );

	}
```
</details>

##### `getColor(property: string): MaterialReferenceNode<color>`

<details><summary>Code</summary>

```ts
getColor( property ) {

		return this.getCache( property, 'color' );

	}
```
</details>

##### `getTexture(property: string): MaterialReferenceNode`

<details><summary>Code</summary>

```ts
getTexture( property ) {

		return this.getCache( property === 'map' ? 'map' : property + 'Map', 'texture' );

	}
```
</details>

##### `setup(builder: NodeBuilder): Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const material = builder.context.material;
		const scope = this.scope;

		let node = null;

		if ( scope === MaterialNode.COLOR ) {

			const colorNode = material.color !== undefined ? this.getColor( scope ) : vec3();

			if ( material.map && material.map.isTexture === true ) {

				node = colorNode.mul( this.getTexture( 'map' ) );

			} else {

				node = colorNode;

			}

		} else if ( scope === MaterialNode.OPACITY ) {

			const opacityNode = this.getFloat( scope );

			if ( material.alphaMap && material.alphaMap.isTexture === true ) {

				node = opacityNode.mul( this.getTexture( 'alpha' ) );

			} else {

				node = opacityNode;

			}

		} else if ( scope === MaterialNode.SPECULAR_STRENGTH ) {

			if ( material.specularMap && material.specularMap.isTexture === true ) {

				node = this.getTexture( 'specular' ).r;

			} else {

				node = float( 1 );

			}

		} else if ( scope === MaterialNode.SPECULAR_INTENSITY ) {

			const specularIntensityNode = this.getFloat( scope );

			if ( material.specularIntensityMap && material.specularIntensityMap.isTexture === true ) {

				node = specularIntensityNode.mul( this.getTexture( scope ).a );

			} else {

				node = specularIntensityNode;

			}

		} else if ( scope === MaterialNode.SPECULAR_COLOR ) {

			const specularColorNode = this.getColor( scope );

			if ( material.specularColorMap && material.specularColorMap.isTexture === true ) {

				node = specularColorNode.mul( this.getTexture( scope ).rgb );

			} else {

				node = specularColorNode;

			}

		} else if ( scope === MaterialNode.ROUGHNESS ) { // TODO: cleanup similar branches

			const roughnessNode = this.getFloat( scope );

			if ( material.roughnessMap && material.roughnessMap.isTexture === true ) {

				node = roughnessNode.mul( this.getTexture( scope ).g );

			} else {

				node = roughnessNode;

			}

		} else if ( scope === MaterialNode.METALNESS ) {

			const metalnessNode = this.getFloat( scope );

			if ( material.metalnessMap && material.metalnessMap.isTexture === true ) {

				node = metalnessNode.mul( this.getTexture( scope ).b );

			} else {

				node = metalnessNode;

			}

		} else if ( scope === MaterialNode.EMISSIVE ) {

			const emissiveIntensityNode = this.getFloat( 'emissiveIntensity' );
			const emissiveNode = this.getColor( scope ).mul( emissiveIntensityNode );

			if ( material.emissiveMap && material.emissiveMap.isTexture === true ) {

				node = emissiveNode.mul( this.getTexture( scope ) );

			} else {

				node = emissiveNode;

			}

		} else if ( scope === MaterialNode.NORMAL ) {

			if ( material.normalMap ) {

				node = normalMap( this.getTexture( 'normal' ), this.getCache( 'normalScale', 'vec2' ) );
				node.normalMapType = material.normalMapType;

			} else if ( material.bumpMap ) {

				node = bumpMap( this.getTexture( 'bump' ).r, this.getFloat( 'bumpScale' ) );

			} else {

				node = normalView;

			}

		} else if ( scope === MaterialNode.CLEARCOAT ) {

			const clearcoatNode = this.getFloat( scope );

			if ( material.clearcoatMap && material.clearcoatMap.isTexture === true ) {

				node = clearcoatNode.mul( this.getTexture( scope ).r );

			} else {

				node = clearcoatNode;

			}

		} else if ( scope === MaterialNode.CLEARCOAT_ROUGHNESS ) {

			const clearcoatRoughnessNode = this.getFloat( scope );

			if ( material.clearcoatRoughnessMap && material.clearcoatRoughnessMap.isTexture === true ) {

				node = clearcoatRoughnessNode.mul( this.getTexture( scope ).r );

			} else {

				node = clearcoatRoughnessNode;

			}

		} else if ( scope === MaterialNode.CLEARCOAT_NORMAL ) {

			if ( material.clearcoatNormalMap ) {

				node = normalMap( this.getTexture( scope ), this.getCache( scope + 'Scale', 'vec2' ) );

			} else {

				node = normalView;

			}

		} else if ( scope === MaterialNode.SHEEN ) {

			const sheenNode = this.getColor( 'sheenColor' ).mul( this.getFloat( 'sheen' ) ); // Move this mul() to CPU

			if ( material.sheenColorMap && material.sheenColorMap.isTexture === true ) {

				node = sheenNode.mul( this.getTexture( 'sheenColor' ).rgb );

			} else {

				node = sheenNode;

			}

		} else if ( scope === MaterialNode.SHEEN_ROUGHNESS ) {

			const sheenRoughnessNode = this.getFloat( scope );

			if ( material.sheenRoughnessMap && material.sheenRoughnessMap.isTexture === true ) {

				node = sheenRoughnessNode.mul( this.getTexture( scope ).a );

			} else {

				node = sheenRoughnessNode;

			}

			node = node.clamp( 0.07, 1.0 );

		} else if ( scope === MaterialNode.ANISOTROPY ) {

			if ( material.anisotropyMap && material.anisotropyMap.isTexture === true ) {

				const anisotropyPolar = this.getTexture( scope );
				const anisotropyMat = mat2( materialAnisotropyVector.x, materialAnisotropyVector.y, materialAnisotropyVector.y.negate(), materialAnisotropyVector.x );

				node = anisotropyMat.mul( anisotropyPolar.rg.mul( 2.0 ).sub( vec2( 1.0 ) ).normalize().mul( anisotropyPolar.b ) );

			} else {

				node = materialAnisotropyVector;

			}

		} else if ( scope === MaterialNode.IRIDESCENCE_THICKNESS ) {

			const iridescenceThicknessMaximum = reference( '1', 'float', material.iridescenceThicknessRange );

			if ( material.iridescenceThicknessMap ) {

				const iridescenceThicknessMinimum = reference( '0', 'float', material.iridescenceThicknessRange );

				node = iridescenceThicknessMaximum.sub( iridescenceThicknessMinimum ).mul( this.getTexture( scope ).g ).add( iridescenceThicknessMinimum );

			} else {

				node = iridescenceThicknessMaximum;

			}

		} else if ( scope === MaterialNode.TRANSMISSION ) {

			const transmissionNode = this.getFloat( scope );

			if ( material.transmissionMap ) {

				node = transmissionNode.mul( this.getTexture( scope ).r );

			} else {

				node = transmissionNode;

			}

		} else if ( scope === MaterialNode.THICKNESS ) {

			const thicknessNode = this.getFloat( scope );

			if ( material.thicknessMap ) {

				node = thicknessNode.mul( this.getTexture( scope ).g );

			} else {

				node = thicknessNode;

			}

		} else if ( scope === MaterialNode.IOR ) {

			node = this.getFloat( scope );

		} else if ( scope === MaterialNode.LIGHT_MAP ) {

			node = this.getTexture( scope ).rgb.mul( this.getFloat( 'lightMapIntensity' ) );

		} else if ( scope === MaterialNode.AO ) {

			node = this.getTexture( scope ).r.sub( 1.0 ).mul( this.getFloat( 'aoMapIntensity' ) ).add( 1.0 );

		} else if ( scope === MaterialNode.LINE_DASH_OFFSET ) {

			node = ( material.dashOffset ) ? this.getFloat( scope ) : float( 0 );

		} else {

			const outputType = this.getNodeType( builder );

			node = this.getCache( scope, outputType );

		}

		return node;

	}
```
</details>


---