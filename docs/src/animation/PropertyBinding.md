[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PropertyBinding.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 31 |
| 🧱 Classes | 2 |
| 📊 Variables & Constants | 29 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/animation/PropertyBinding.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_RESERVED_CHARS_RE` | `"\\[\\]\\.:\\/"` | let/var | `'\\[\\]\\.:\\/'` | ✗ |
| `_reservedRe` | `RegExp` | let/var | `new RegExp( '[' + _RESERVED_CHARS_RE + ']', 'g' )` | ✗ |
| `_wordChar` | `string` | let/var | `'[^' + _RESERVED_CHARS_RE + ']'` | ✗ |
| `_wordCharOrDot` | `string` | let/var | `'[^' + _RESERVED_CHARS_RE.replace( '\\.', '' ) + ']'` | ✗ |
| `_trackRe` | `RegExp` | let/var | `new RegExp( '' + '^' + _directoryRe + _nodeRe + _objectRe + _propertyRe + '$' )` | ✗ |
| `_supportedObjectNames` | `string[]` | let/var | `[ 'material', 'materials', 'bones', 'map' ]` | ✗ |
| `parsedPath` | `any` | let/var | `optionalParsedPath \|\| PropertyBinding.parseTrackName( path )` | ✗ |
| `firstValidIndex` | `any` | let/var | `this._targetGroup.nCachedObjects_` | ✗ |
| `binding` | `any` | let/var | `this._bindings[ firstValidIndex ]` | ✗ |
| `bindings` | `any` | let/var | `this._bindings` | ✗ |
| `bindings` | `any` | let/var | `this._bindings` | ✗ |
| `bindings` | `any` | let/var | `this._bindings` | ✗ |
| `results` | `{ nodeName: string; objectName: strin...` | let/var | `{ // directoryName: matches[ 1 ], // (tschw) currently unused nodeName: match...` | ✗ |
| `lastDot` | `number` | let/var | `results.nodeName && results.nodeName.lastIndexOf( '.' )` | ✗ |
| `childNode` | `any` | let/var | `children[ i ]` | ✗ |
| `source` | `any` | let/var | `this.resolvedProperty` | ✗ |
| `dest` | `any` | let/var | `this.resolvedProperty` | ✗ |
| `dest` | `any` | let/var | `this.resolvedProperty` | ✗ |
| `dest` | `any` | let/var | `this.resolvedProperty` | ✗ |
| `targetObject` | `any` | let/var | `this.node` | ✗ |
| `parsedPath` | `any` | let/var | `this.parsedPath` | ✗ |
| `objectName` | `any` | let/var | `parsedPath.objectName` | ✗ |
| `propertyName` | `any` | let/var | `parsedPath.propertyName` | ✗ |
| `propertyIndex` | `any` | let/var | `parsedPath.propertyIndex` | ✗ |
| `objectIndex` | `any` | let/var | `parsedPath.objectIndex` | ✗ |
| `nodeProperty` | `any` | let/var | `targetObject[ propertyName ]` | ✗ |
| `nodeName` | `any` | let/var | `parsedPath.nodeName` | ✗ |
| `versioning` | `number` | let/var | `this.Versioning.None` | ✗ |
| `bindingType` | `number` | let/var | `this.BindingType.Direct` | ✗ |


---

## Functions

### `Composite.getValue(array: any, offset: any): void`

**Parameters:**

- **`array`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `this.bind`
- `binding.getValue`

**Internal Comments:**
```
// and only call .getValue on the first
```

<details><summary>Code</summary>

```typescript
getValue( array, offset ) {

		this.bind(); // bind all binding

		const firstValidIndex = this._targetGroup.nCachedObjects_,
			binding = this._bindings[ firstValidIndex ];

		// and only call .getValue on the first
		if ( binding !== undefined ) binding.getValue( array, offset );

	}
```
</details>

### `Composite.setValue(array: any, offset: any): void`

**Parameters:**

- **`array`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `bindings[ i ].setValue`

<details><summary>Code</summary>

```typescript
setValue( array, offset ) {

		const bindings = this._bindings;

		for ( let i = this._targetGroup.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

			bindings[ i ].setValue( array, offset );

		}

	}
```
</details>

### `Composite.bind(): void`

**Returns:** `void`

**Calls:**

- `bindings[ i ].bind`

<details><summary>Code</summary>

```typescript
bind() {

		const bindings = this._bindings;

		for ( let i = this._targetGroup.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

			bindings[ i ].bind();

		}

	}
```
</details>

### `Composite.unbind(): void`

**Returns:** `void`

**Calls:**

- `bindings[ i ].unbind`

<details><summary>Code</summary>

```typescript
unbind() {

		const bindings = this._bindings;

		for ( let i = this._targetGroup.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

			bindings[ i ].unbind();

		}

	}
```
</details>

### `PropertyBinding.create(root: any, path: string, parsedPath: any): Composite | PropertyBinding`

**JSDoc:**
```typescript
/**
	 * Factory method for creating a property binding from the given parameters.
	 *
	 * @static
	 * @param {Object} root - The root node.
	 * @param {string} path - The path.
	 * @param {?Object} [parsedPath] - The parsed path.
	 * @return {PropertyBinding|Composite} The created property binding or composite.
	 */
```

**Parameters:**

- **`root`** `any`
- **`path`** `string`
- **`parsedPath`** `any`

**Returns:** `Composite | PropertyBinding`

<details><summary>Code</summary>

```typescript
static create( root, path, parsedPath ) {

		if ( ! ( root && root.isAnimationObjectGroup ) ) {

			return new PropertyBinding( root, path, parsedPath );

		} else {

			return new PropertyBinding.Composite( root, path, parsedPath );

		}

	}
```
</details>

### `PropertyBinding.sanitizeNodeName(name: string): string`

**JSDoc:**
```typescript
/**
	 * Replaces spaces with underscores and removes unsupported characters from
	 * node names, to ensure compatibility with parseTrackName().
	 *
	 * @param {string} name - Node name to be sanitized.
	 * @return {string} The sanitized node name.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `string`

**Calls:**

- `name.replace( /\s/g, '_' ).replace`

<details><summary>Code</summary>

```typescript
static sanitizeNodeName( name ) {

		return name.replace( /\s/g, '_' ).replace( _reservedRe, '' );

	}
```
</details>

### `PropertyBinding.parseTrackName(trackName: string): any`

**JSDoc:**
```typescript
/**
	 * Parses the given track name (an object path to an animated property) and
	 * returns an object with information about the path. Matches strings in the following forms:
	 *
	 * - nodeName.property
	 * - nodeName.property[accessor]
	 * - nodeName.material.property[accessor]
	 * - uuid.property[accessor]
	 * - uuid.objectName[objectIndex].propertyName[propertyIndex]
	 * - parentName/nodeName.property
	 * - parentName/parentName/nodeName.property[index]
	 * - .bone[Armature.DEF_cog].position
	 * - scene:helium_balloon_model:helium_balloon_model.position
	 *
	 * @static
	 * @param {string} trackName - The track name to parse.
	 * @return {Object} The parsed track name as an object.
	 */
```

**Parameters:**

- **`trackName`** `string`

**Returns:** `any`

**Calls:**

- `_trackRe.exec`
- `results.nodeName.lastIndexOf`
- `results.nodeName.substring`
- `_supportedObjectNames.indexOf`

**Internal Comments:**
```
// directoryName: matches[ 1 ], // (tschw) currently unused (x2)
// Object names must be checked against an allowlist. Otherwise, there
// is no way to parse 'foo.bar.baz': 'baz' must be a property, but
// 'bar' could be the objectName, or part of a nodeName (which can
// include '.' characters).
```

<details><summary>Code</summary>

```typescript
static parseTrackName( trackName ) {

		const matches = _trackRe.exec( trackName );

		if ( matches === null ) {

			throw new Error( 'PropertyBinding: Cannot parse trackName: ' + trackName );

		}

		const results = {
			// directoryName: matches[ 1 ], // (tschw) currently unused
			nodeName: matches[ 2 ],
			objectName: matches[ 3 ],
			objectIndex: matches[ 4 ],
			propertyName: matches[ 5 ], // required
			propertyIndex: matches[ 6 ]
		};

		const lastDot = results.nodeName && results.nodeName.lastIndexOf( '.' );

		if ( lastDot !== undefined && lastDot !== - 1 ) {

			const objectName = results.nodeName.substring( lastDot + 1 );

			// Object names must be checked against an allowlist. Otherwise, there
			// is no way to parse 'foo.bar.baz': 'baz' must be a property, but
			// 'bar' could be the objectName, or part of a nodeName (which can
			// include '.' characters).
			if ( _supportedObjectNames.indexOf( objectName ) !== - 1 ) {

				results.nodeName = results.nodeName.substring( 0, lastDot );
				results.objectName = objectName;

			}

		}

		if ( results.propertyName === null || results.propertyName.length === 0 ) {

			throw new Error( 'PropertyBinding: can not parse propertyName from trackName: ' + trackName );

		}

		return results;

	}
```
</details>

### `PropertyBinding.findNode(root: any, nodeName: string | number): any`

**JSDoc:**
```typescript
/**
	 * Searches for a node in the hierarchy of the given root object by the given
	 * node name.
	 *
	 * @static
	 * @param {Object} root - The root object.
	 * @param {string|number} nodeName - The name of the node.
	 * @return {?Object} The found node. Returns `null` if no object was found.
	 */
```

**Parameters:**

- **`root`** `any`
- **`nodeName`** `string | number`

**Returns:** `any`

**Calls:**

- `root.skeleton.getBoneByName`
- `searchNodeSubtree`

**Internal Comments:**
```
// search into skeleton bones.
// search into node subtree.
```

<details><summary>Code</summary>

```typescript
static findNode( root, nodeName ) {

		if ( nodeName === undefined || nodeName === '' || nodeName === '.' || nodeName === - 1 || nodeName === root.name || nodeName === root.uuid ) {

			return root;

		}

		// search into skeleton bones.
		if ( root.skeleton ) {

			const bone = root.skeleton.getBoneByName( nodeName );

			if ( bone !== undefined ) {

				return bone;

			}

		}

		// search into node subtree.
		if ( root.children ) {

			const searchNodeSubtree = function ( children ) {

				for ( let i = 0; i < children.length; i ++ ) {

					const childNode = children[ i ];

					if ( childNode.name === nodeName || childNode.uuid === nodeName ) {

						return childNode;

					}

					const result = searchNodeSubtree( childNode.children );

					if ( result ) return result;

				}

				return null;

			};

			const subTreeNode = searchNodeSubtree( root.children );

			if ( subTreeNode ) {

				return subTreeNode;

			}

		}

		return null;

	}
```
</details>

### `PropertyBinding._getValue_unavailable(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_getValue_unavailable() {}
```
</details>

### `PropertyBinding._setValue_unavailable(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_unavailable() {}
```
</details>

### `PropertyBinding._getValue_direct(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_getValue_direct( buffer, offset ) {

		buffer[ offset ] = this.targetObject[ this.propertyName ];

	}
```
</details>

### `PropertyBinding._getValue_array(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_getValue_array( buffer, offset ) {

		const source = this.resolvedProperty;

		for ( let i = 0, n = source.length; i !== n; ++ i ) {

			buffer[ offset ++ ] = source[ i ];

		}

	}
```
</details>

### `PropertyBinding._getValue_arrayElement(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_getValue_arrayElement( buffer, offset ) {

		buffer[ offset ] = this.resolvedProperty[ this.propertyIndex ];

	}
```
</details>

### `PropertyBinding._getValue_toArray(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `this.resolvedProperty.toArray`

<details><summary>Code</summary>

```typescript
_getValue_toArray( buffer, offset ) {

		this.resolvedProperty.toArray( buffer, offset );

	}
```
</details>

### `PropertyBinding._setValue_direct(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_direct( buffer, offset ) {

		this.targetObject[ this.propertyName ] = buffer[ offset ];

	}
```
</details>

### `PropertyBinding._setValue_direct_setNeedsUpdate(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_direct_setNeedsUpdate( buffer, offset ) {

		this.targetObject[ this.propertyName ] = buffer[ offset ];
		this.targetObject.needsUpdate = true;

	}
```
</details>

### `PropertyBinding._setValue_direct_setMatrixWorldNeedsUpdate(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_direct_setMatrixWorldNeedsUpdate( buffer, offset ) {

		this.targetObject[ this.propertyName ] = buffer[ offset ];
		this.targetObject.matrixWorldNeedsUpdate = true;

	}
```
</details>

### `PropertyBinding._setValue_array(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_array( buffer, offset ) {

		const dest = this.resolvedProperty;

		for ( let i = 0, n = dest.length; i !== n; ++ i ) {

			dest[ i ] = buffer[ offset ++ ];

		}

	}
```
</details>

### `PropertyBinding._setValue_array_setNeedsUpdate(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_array_setNeedsUpdate( buffer, offset ) {

		const dest = this.resolvedProperty;

		for ( let i = 0, n = dest.length; i !== n; ++ i ) {

			dest[ i ] = buffer[ offset ++ ];

		}

		this.targetObject.needsUpdate = true;

	}
```
</details>

### `PropertyBinding._setValue_array_setMatrixWorldNeedsUpdate(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_array_setMatrixWorldNeedsUpdate( buffer, offset ) {

		const dest = this.resolvedProperty;

		for ( let i = 0, n = dest.length; i !== n; ++ i ) {

			dest[ i ] = buffer[ offset ++ ];

		}

		this.targetObject.matrixWorldNeedsUpdate = true;

	}
```
</details>

### `PropertyBinding._setValue_arrayElement(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_arrayElement( buffer, offset ) {

		this.resolvedProperty[ this.propertyIndex ] = buffer[ offset ];

	}
```
</details>

### `PropertyBinding._setValue_arrayElement_setNeedsUpdate(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_arrayElement_setNeedsUpdate( buffer, offset ) {

		this.resolvedProperty[ this.propertyIndex ] = buffer[ offset ];
		this.targetObject.needsUpdate = true;

	}
```
</details>

### `PropertyBinding._setValue_arrayElement_setMatrixWorldNeedsUpdate(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_setValue_arrayElement_setMatrixWorldNeedsUpdate( buffer, offset ) {

		this.resolvedProperty[ this.propertyIndex ] = buffer[ offset ];
		this.targetObject.matrixWorldNeedsUpdate = true;

	}
```
</details>

### `PropertyBinding._setValue_fromArray(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `this.resolvedProperty.fromArray`

<details><summary>Code</summary>

```typescript
_setValue_fromArray( buffer, offset ) {

		this.resolvedProperty.fromArray( buffer, offset );

	}
```
</details>

### `PropertyBinding._setValue_fromArray_setNeedsUpdate(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `this.resolvedProperty.fromArray`

<details><summary>Code</summary>

```typescript
_setValue_fromArray_setNeedsUpdate( buffer, offset ) {

		this.resolvedProperty.fromArray( buffer, offset );
		this.targetObject.needsUpdate = true;

	}
```
</details>

### `PropertyBinding._setValue_fromArray_setMatrixWorldNeedsUpdate(buffer: any, offset: any): void`

**Parameters:**

- **`buffer`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `this.resolvedProperty.fromArray`

<details><summary>Code</summary>

```typescript
_setValue_fromArray_setMatrixWorldNeedsUpdate( buffer, offset ) {

		this.resolvedProperty.fromArray( buffer, offset );
		this.targetObject.matrixWorldNeedsUpdate = true;

	}
```
</details>

### `PropertyBinding._getValue_unbound(targetArray: any, offset: any): void`

**Parameters:**

- **`targetArray`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `this.bind`
- `this.getValue`

<details><summary>Code</summary>

```typescript
_getValue_unbound( targetArray, offset ) {

		this.bind();
		this.getValue( targetArray, offset );

	}
```
</details>

### `PropertyBinding._setValue_unbound(sourceArray: any, offset: any): void`

**Parameters:**

- **`sourceArray`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `this.bind`
- `this.setValue`

<details><summary>Code</summary>

```typescript
_setValue_unbound( sourceArray, offset ) {

		this.bind();
		this.setValue( sourceArray, offset );

	}
```
</details>

### `PropertyBinding.bind(): void`

**JSDoc:**
```typescript
/**
	 * Creates a getter / setter pair for the property tracked by this binding.
	 */
```

**Returns:** `void`

**Calls:**

- `PropertyBinding.findNode`
- `console.warn`
- `console.error`
- `Array.isArray`

**Internal Comments:**
```
// set fail state so we can just 'return' on error (x4)
// ensure there is a value node
// special cases were we need to reach deeper into the hierarchy to get the face materials....
// potential future optimization: skip this if propertyIndex is already an integer (x3)
// and convert the integer string to a true integer. (x3)
// support resolving morphTarget names into indices. (x2)
// resolve property (x2)
// determine versioning scheme (x2)
// determine how the property gets bound (x2)
// access a sub element of the property array (only primitives are supported right now)
// potential optimization, skip this if propertyIndex is already an integer, and convert the integer string to a true integer.
// must use copy for Object3D.Euler/Quaternion (x3)
// select getter / setter (x4)
```

<details><summary>Code</summary>

```typescript
bind() {

		let targetObject = this.node;
		const parsedPath = this.parsedPath;

		const objectName = parsedPath.objectName;
		const propertyName = parsedPath.propertyName;
		let propertyIndex = parsedPath.propertyIndex;

		if ( ! targetObject ) {

			targetObject = PropertyBinding.findNode( this.rootNode, parsedPath.nodeName );

			this.node = targetObject;

		}

		// set fail state so we can just 'return' on error
		this.getValue = this._getValue_unavailable;
		this.setValue = this._setValue_unavailable;

		// ensure there is a value node
		if ( ! targetObject ) {

			console.warn( 'THREE.PropertyBinding: No target node found for track: ' + this.path + '.' );
			return;

		}

		if ( objectName ) {

			let objectIndex = parsedPath.objectIndex;

			// special cases were we need to reach deeper into the hierarchy to get the face materials....
			switch ( objectName ) {

				case 'materials':

					if ( ! targetObject.material ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material as node does not have a material.', this );
						return;

					}

					if ( ! targetObject.material.materials ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material.materials as node.material does not have a materials array.', this );
						return;

					}

					targetObject = targetObject.material.materials;

					break;

				case 'bones':

					if ( ! targetObject.skeleton ) {

						console.error( 'THREE.PropertyBinding: Can not bind to bones as node does not have a skeleton.', this );
						return;

					}

					// potential future optimization: skip this if propertyIndex is already an integer
					// and convert the integer string to a true integer.

					targetObject = targetObject.skeleton.bones;

					// support resolving morphTarget names into indices.
					for ( let i = 0; i < targetObject.length; i ++ ) {

						if ( targetObject[ i ].name === objectIndex ) {

							objectIndex = i;
							break;

						}

					}

					break;

				case 'map':

					if ( 'map' in targetObject ) {

						targetObject = targetObject.map;
						break;

					}

					if ( ! targetObject.material ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material as node does not have a material.', this );
						return;

					}

					if ( ! targetObject.material.map ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material.map as node.material does not have a map.', this );
						return;

					}

					targetObject = targetObject.material.map;
					break;

				default:

					if ( targetObject[ objectName ] === undefined ) {

						console.error( 'THREE.PropertyBinding: Can not bind to objectName of node undefined.', this );
						return;

					}

					targetObject = targetObject[ objectName ];

			}


			if ( objectIndex !== undefined ) {

				if ( targetObject[ objectIndex ] === undefined ) {

					console.error( 'THREE.PropertyBinding: Trying to bind to objectIndex of objectName, but is undefined.', this, targetObject );
					return;

				}

				targetObject = targetObject[ objectIndex ];

			}

		}

		// resolve property
		const nodeProperty = targetObject[ propertyName ];

		if ( nodeProperty === undefined ) {

			const nodeName = parsedPath.nodeName;

			console.error( 'THREE.PropertyBinding: Trying to update property for track: ' + nodeName +
				'.' + propertyName + ' but it wasn\'t found.', targetObject );
			return;

		}

		// determine versioning scheme
		let versioning = this.Versioning.None;

		this.targetObject = targetObject;

		if ( targetObject.isMaterial === true ) {

			versioning = this.Versioning.NeedsUpdate;

		} else if ( targetObject.isObject3D === true ) {

			versioning = this.Versioning.MatrixWorldNeedsUpdate;

		}

		// determine how the property gets bound
		let bindingType = this.BindingType.Direct;

		if ( propertyIndex !== undefined ) {

			// access a sub element of the property array (only primitives are supported right now)

			if ( propertyName === 'morphTargetInfluences' ) {

				// potential optimization, skip this if propertyIndex is already an integer, and convert the integer string to a true integer.

				// support resolving morphTarget names into indices.
				if ( ! targetObject.geometry ) {

					console.error( 'THREE.PropertyBinding: Can not bind to morphTargetInfluences because node does not have a geometry.', this );
					return;

				}

				if ( ! targetObject.geometry.morphAttributes ) {

					console.error( 'THREE.PropertyBinding: Can not bind to morphTargetInfluences because node does not have a geometry.morphAttributes.', this );
					return;

				}

				if ( targetObject.morphTargetDictionary[ propertyIndex ] !== undefined ) {

					propertyIndex = targetObject.morphTargetDictionary[ propertyIndex ];

				}

			}

			bindingType = this.BindingType.ArrayElement;

			this.resolvedProperty = nodeProperty;
			this.propertyIndex = propertyIndex;

		} else if ( nodeProperty.fromArray !== undefined && nodeProperty.toArray !== undefined ) {

			// must use copy for Object3D.Euler/Quaternion

			bindingType = this.BindingType.HasFromToArray;

			this.resolvedProperty = nodeProperty;

		} else if ( Array.isArray( nodeProperty ) ) {

			bindingType = this.BindingType.EntireArray;

			this.resolvedProperty = nodeProperty;

		} else {

			this.propertyName = propertyName;

		}

		// select getter / setter
		this.getValue = this.GetterByBindingType[ bindingType ];
		this.setValue = this.SetterByBindingTypeAndVersioning[ bindingType ][ versioning ];

	}
```
</details>

### `PropertyBinding.unbind(): void`

**JSDoc:**
```typescript
/**
	 * Unbinds the property.
	 */
```

**Returns:** `void`

**Internal Comments:**
```
// back to the prototype version of getValue / setValue (x4)
// note: avoiding to mutate the shape of 'this' via 'delete' (x4)
```

<details><summary>Code</summary>

```typescript
unbind() {

		this.node = null;

		// back to the prototype version of getValue / setValue
		// note: avoiding to mutate the shape of 'this' via 'delete'
		this.getValue = this._getValue_unbound;
		this.setValue = this._setValue_unbound;

	}
```
</details>

### `searchNodeSubtree(children: any): any`

**Parameters:**

- **`children`** `any`

**Returns:** `any`

**Calls:**

- `searchNodeSubtree`

<details><summary>Code</summary>

```typescript
function ( children ) {

				for ( let i = 0; i < children.length; i ++ ) {

					const childNode = children[ i ];

					if ( childNode.name === nodeName || childNode.uuid === nodeName ) {

						return childNode;

					}

					const result = searchNodeSubtree( childNode.children );

					if ( result ) return result;

				}

				return null;

			}
```
</details>


---

## Classes

### `Composite`

<details><summary>Class Code</summary>

```ts
class Composite {

	constructor( targetGroup, path, optionalParsedPath ) {

		const parsedPath = optionalParsedPath || PropertyBinding.parseTrackName( path );

		this._targetGroup = targetGroup;
		this._bindings = targetGroup.subscribe_( path, parsedPath );

	}

	getValue( array, offset ) {

		this.bind(); // bind all binding

		const firstValidIndex = this._targetGroup.nCachedObjects_,
			binding = this._bindings[ firstValidIndex ];

		// and only call .getValue on the first
		if ( binding !== undefined ) binding.getValue( array, offset );

	}

	setValue( array, offset ) {

		const bindings = this._bindings;

		for ( let i = this._targetGroup.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

			bindings[ i ].setValue( array, offset );

		}

	}

	bind() {

		const bindings = this._bindings;

		for ( let i = this._targetGroup.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

			bindings[ i ].bind();

		}

	}

	unbind() {

		const bindings = this._bindings;

		for ( let i = this._targetGroup.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

			bindings[ i ].unbind();

		}

	}

}
```
</details>

#### Methods

##### `getValue(array: any, offset: any): void`

<details><summary>Code</summary>

```ts
getValue( array, offset ) {

		this.bind(); // bind all binding

		const firstValidIndex = this._targetGroup.nCachedObjects_,
			binding = this._bindings[ firstValidIndex ];

		// and only call .getValue on the first
		if ( binding !== undefined ) binding.getValue( array, offset );

	}
```
</details>

##### `setValue(array: any, offset: any): void`

<details><summary>Code</summary>

```ts
setValue( array, offset ) {

		const bindings = this._bindings;

		for ( let i = this._targetGroup.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

			bindings[ i ].setValue( array, offset );

		}

	}
```
</details>

##### `bind(): void`

<details><summary>Code</summary>

```ts
bind() {

		const bindings = this._bindings;

		for ( let i = this._targetGroup.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

			bindings[ i ].bind();

		}

	}
```
</details>

##### `unbind(): void`

<details><summary>Code</summary>

```ts
unbind() {

		const bindings = this._bindings;

		for ( let i = this._targetGroup.nCachedObjects_, n = bindings.length; i !== n; ++ i ) {

			bindings[ i ].unbind();

		}

	}
```
</details>

### `PropertyBinding`

<details><summary>Class Code</summary>

```ts
class PropertyBinding {

	/**
	 * Constructs a new property binding.
	 *
	 * @param {Object} rootNode - The root node.
	 * @param {string} path - The path.
	 * @param {?Object} [parsedPath] - The parsed path.
	 */
	constructor( rootNode, path, parsedPath ) {

		/**
		 * The object path to the animated property.
		 *
		 * @type {string}
		 */
		this.path = path;

		/**
		 * An object holding information about the path.
		 *
		 * @type {Object}
		 */
		this.parsedPath = parsedPath || PropertyBinding.parseTrackName( path );

		/**
		 * The object owns the animated property.
		 *
		 * @type {?Object}
		 */
		this.node = PropertyBinding.findNode( rootNode, this.parsedPath.nodeName );

		/**
		 * The root node.
		 *
		 * @type {Object3D|Skeleton}
		 */
		this.rootNode = rootNode;

		// initial state of these methods that calls 'bind'
		this.getValue = this._getValue_unbound;
		this.setValue = this._setValue_unbound;

	}


	/**
	 * Factory method for creating a property binding from the given parameters.
	 *
	 * @static
	 * @param {Object} root - The root node.
	 * @param {string} path - The path.
	 * @param {?Object} [parsedPath] - The parsed path.
	 * @return {PropertyBinding|Composite} The created property binding or composite.
	 */
	static create( root, path, parsedPath ) {

		if ( ! ( root && root.isAnimationObjectGroup ) ) {

			return new PropertyBinding( root, path, parsedPath );

		} else {

			return new PropertyBinding.Composite( root, path, parsedPath );

		}

	}

	/**
	 * Replaces spaces with underscores and removes unsupported characters from
	 * node names, to ensure compatibility with parseTrackName().
	 *
	 * @param {string} name - Node name to be sanitized.
	 * @return {string} The sanitized node name.
	 */
	static sanitizeNodeName( name ) {

		return name.replace( /\s/g, '_' ).replace( _reservedRe, '' );

	}

	/**
	 * Parses the given track name (an object path to an animated property) and
	 * returns an object with information about the path. Matches strings in the following forms:
	 *
	 * - nodeName.property
	 * - nodeName.property[accessor]
	 * - nodeName.material.property[accessor]
	 * - uuid.property[accessor]
	 * - uuid.objectName[objectIndex].propertyName[propertyIndex]
	 * - parentName/nodeName.property
	 * - parentName/parentName/nodeName.property[index]
	 * - .bone[Armature.DEF_cog].position
	 * - scene:helium_balloon_model:helium_balloon_model.position
	 *
	 * @static
	 * @param {string} trackName - The track name to parse.
	 * @return {Object} The parsed track name as an object.
	 */
	static parseTrackName( trackName ) {

		const matches = _trackRe.exec( trackName );

		if ( matches === null ) {

			throw new Error( 'PropertyBinding: Cannot parse trackName: ' + trackName );

		}

		const results = {
			// directoryName: matches[ 1 ], // (tschw) currently unused
			nodeName: matches[ 2 ],
			objectName: matches[ 3 ],
			objectIndex: matches[ 4 ],
			propertyName: matches[ 5 ], // required
			propertyIndex: matches[ 6 ]
		};

		const lastDot = results.nodeName && results.nodeName.lastIndexOf( '.' );

		if ( lastDot !== undefined && lastDot !== - 1 ) {

			const objectName = results.nodeName.substring( lastDot + 1 );

			// Object names must be checked against an allowlist. Otherwise, there
			// is no way to parse 'foo.bar.baz': 'baz' must be a property, but
			// 'bar' could be the objectName, or part of a nodeName (which can
			// include '.' characters).
			if ( _supportedObjectNames.indexOf( objectName ) !== - 1 ) {

				results.nodeName = results.nodeName.substring( 0, lastDot );
				results.objectName = objectName;

			}

		}

		if ( results.propertyName === null || results.propertyName.length === 0 ) {

			throw new Error( 'PropertyBinding: can not parse propertyName from trackName: ' + trackName );

		}

		return results;

	}

	/**
	 * Searches for a node in the hierarchy of the given root object by the given
	 * node name.
	 *
	 * @static
	 * @param {Object} root - The root object.
	 * @param {string|number} nodeName - The name of the node.
	 * @return {?Object} The found node. Returns `null` if no object was found.
	 */
	static findNode( root, nodeName ) {

		if ( nodeName === undefined || nodeName === '' || nodeName === '.' || nodeName === - 1 || nodeName === root.name || nodeName === root.uuid ) {

			return root;

		}

		// search into skeleton bones.
		if ( root.skeleton ) {

			const bone = root.skeleton.getBoneByName( nodeName );

			if ( bone !== undefined ) {

				return bone;

			}

		}

		// search into node subtree.
		if ( root.children ) {

			const searchNodeSubtree = function ( children ) {

				for ( let i = 0; i < children.length; i ++ ) {

					const childNode = children[ i ];

					if ( childNode.name === nodeName || childNode.uuid === nodeName ) {

						return childNode;

					}

					const result = searchNodeSubtree( childNode.children );

					if ( result ) return result;

				}

				return null;

			};

			const subTreeNode = searchNodeSubtree( root.children );

			if ( subTreeNode ) {

				return subTreeNode;

			}

		}

		return null;

	}

	// these are used to "bind" a nonexistent property
	_getValue_unavailable() {}
	_setValue_unavailable() {}

	// Getters

	_getValue_direct( buffer, offset ) {

		buffer[ offset ] = this.targetObject[ this.propertyName ];

	}

	_getValue_array( buffer, offset ) {

		const source = this.resolvedProperty;

		for ( let i = 0, n = source.length; i !== n; ++ i ) {

			buffer[ offset ++ ] = source[ i ];

		}

	}

	_getValue_arrayElement( buffer, offset ) {

		buffer[ offset ] = this.resolvedProperty[ this.propertyIndex ];

	}

	_getValue_toArray( buffer, offset ) {

		this.resolvedProperty.toArray( buffer, offset );

	}

	// Direct

	_setValue_direct( buffer, offset ) {

		this.targetObject[ this.propertyName ] = buffer[ offset ];

	}

	_setValue_direct_setNeedsUpdate( buffer, offset ) {

		this.targetObject[ this.propertyName ] = buffer[ offset ];
		this.targetObject.needsUpdate = true;

	}

	_setValue_direct_setMatrixWorldNeedsUpdate( buffer, offset ) {

		this.targetObject[ this.propertyName ] = buffer[ offset ];
		this.targetObject.matrixWorldNeedsUpdate = true;

	}

	// EntireArray

	_setValue_array( buffer, offset ) {

		const dest = this.resolvedProperty;

		for ( let i = 0, n = dest.length; i !== n; ++ i ) {

			dest[ i ] = buffer[ offset ++ ];

		}

	}

	_setValue_array_setNeedsUpdate( buffer, offset ) {

		const dest = this.resolvedProperty;

		for ( let i = 0, n = dest.length; i !== n; ++ i ) {

			dest[ i ] = buffer[ offset ++ ];

		}

		this.targetObject.needsUpdate = true;

	}

	_setValue_array_setMatrixWorldNeedsUpdate( buffer, offset ) {

		const dest = this.resolvedProperty;

		for ( let i = 0, n = dest.length; i !== n; ++ i ) {

			dest[ i ] = buffer[ offset ++ ];

		}

		this.targetObject.matrixWorldNeedsUpdate = true;

	}

	// ArrayElement

	_setValue_arrayElement( buffer, offset ) {

		this.resolvedProperty[ this.propertyIndex ] = buffer[ offset ];

	}

	_setValue_arrayElement_setNeedsUpdate( buffer, offset ) {

		this.resolvedProperty[ this.propertyIndex ] = buffer[ offset ];
		this.targetObject.needsUpdate = true;

	}

	_setValue_arrayElement_setMatrixWorldNeedsUpdate( buffer, offset ) {

		this.resolvedProperty[ this.propertyIndex ] = buffer[ offset ];
		this.targetObject.matrixWorldNeedsUpdate = true;

	}

	// HasToFromArray

	_setValue_fromArray( buffer, offset ) {

		this.resolvedProperty.fromArray( buffer, offset );

	}

	_setValue_fromArray_setNeedsUpdate( buffer, offset ) {

		this.resolvedProperty.fromArray( buffer, offset );
		this.targetObject.needsUpdate = true;

	}

	_setValue_fromArray_setMatrixWorldNeedsUpdate( buffer, offset ) {

		this.resolvedProperty.fromArray( buffer, offset );
		this.targetObject.matrixWorldNeedsUpdate = true;

	}

	_getValue_unbound( targetArray, offset ) {

		this.bind();
		this.getValue( targetArray, offset );

	}

	_setValue_unbound( sourceArray, offset ) {

		this.bind();
		this.setValue( sourceArray, offset );

	}

	/**
	 * Creates a getter / setter pair for the property tracked by this binding.
	 */
	bind() {

		let targetObject = this.node;
		const parsedPath = this.parsedPath;

		const objectName = parsedPath.objectName;
		const propertyName = parsedPath.propertyName;
		let propertyIndex = parsedPath.propertyIndex;

		if ( ! targetObject ) {

			targetObject = PropertyBinding.findNode( this.rootNode, parsedPath.nodeName );

			this.node = targetObject;

		}

		// set fail state so we can just 'return' on error
		this.getValue = this._getValue_unavailable;
		this.setValue = this._setValue_unavailable;

		// ensure there is a value node
		if ( ! targetObject ) {

			console.warn( 'THREE.PropertyBinding: No target node found for track: ' + this.path + '.' );
			return;

		}

		if ( objectName ) {

			let objectIndex = parsedPath.objectIndex;

			// special cases were we need to reach deeper into the hierarchy to get the face materials....
			switch ( objectName ) {

				case 'materials':

					if ( ! targetObject.material ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material as node does not have a material.', this );
						return;

					}

					if ( ! targetObject.material.materials ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material.materials as node.material does not have a materials array.', this );
						return;

					}

					targetObject = targetObject.material.materials;

					break;

				case 'bones':

					if ( ! targetObject.skeleton ) {

						console.error( 'THREE.PropertyBinding: Can not bind to bones as node does not have a skeleton.', this );
						return;

					}

					// potential future optimization: skip this if propertyIndex is already an integer
					// and convert the integer string to a true integer.

					targetObject = targetObject.skeleton.bones;

					// support resolving morphTarget names into indices.
					for ( let i = 0; i < targetObject.length; i ++ ) {

						if ( targetObject[ i ].name === objectIndex ) {

							objectIndex = i;
							break;

						}

					}

					break;

				case 'map':

					if ( 'map' in targetObject ) {

						targetObject = targetObject.map;
						break;

					}

					if ( ! targetObject.material ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material as node does not have a material.', this );
						return;

					}

					if ( ! targetObject.material.map ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material.map as node.material does not have a map.', this );
						return;

					}

					targetObject = targetObject.material.map;
					break;

				default:

					if ( targetObject[ objectName ] === undefined ) {

						console.error( 'THREE.PropertyBinding: Can not bind to objectName of node undefined.', this );
						return;

					}

					targetObject = targetObject[ objectName ];

			}


			if ( objectIndex !== undefined ) {

				if ( targetObject[ objectIndex ] === undefined ) {

					console.error( 'THREE.PropertyBinding: Trying to bind to objectIndex of objectName, but is undefined.', this, targetObject );
					return;

				}

				targetObject = targetObject[ objectIndex ];

			}

		}

		// resolve property
		const nodeProperty = targetObject[ propertyName ];

		if ( nodeProperty === undefined ) {

			const nodeName = parsedPath.nodeName;

			console.error( 'THREE.PropertyBinding: Trying to update property for track: ' + nodeName +
				'.' + propertyName + ' but it wasn\'t found.', targetObject );
			return;

		}

		// determine versioning scheme
		let versioning = this.Versioning.None;

		this.targetObject = targetObject;

		if ( targetObject.isMaterial === true ) {

			versioning = this.Versioning.NeedsUpdate;

		} else if ( targetObject.isObject3D === true ) {

			versioning = this.Versioning.MatrixWorldNeedsUpdate;

		}

		// determine how the property gets bound
		let bindingType = this.BindingType.Direct;

		if ( propertyIndex !== undefined ) {

			// access a sub element of the property array (only primitives are supported right now)

			if ( propertyName === 'morphTargetInfluences' ) {

				// potential optimization, skip this if propertyIndex is already an integer, and convert the integer string to a true integer.

				// support resolving morphTarget names into indices.
				if ( ! targetObject.geometry ) {

					console.error( 'THREE.PropertyBinding: Can not bind to morphTargetInfluences because node does not have a geometry.', this );
					return;

				}

				if ( ! targetObject.geometry.morphAttributes ) {

					console.error( 'THREE.PropertyBinding: Can not bind to morphTargetInfluences because node does not have a geometry.morphAttributes.', this );
					return;

				}

				if ( targetObject.morphTargetDictionary[ propertyIndex ] !== undefined ) {

					propertyIndex = targetObject.morphTargetDictionary[ propertyIndex ];

				}

			}

			bindingType = this.BindingType.ArrayElement;

			this.resolvedProperty = nodeProperty;
			this.propertyIndex = propertyIndex;

		} else if ( nodeProperty.fromArray !== undefined && nodeProperty.toArray !== undefined ) {

			// must use copy for Object3D.Euler/Quaternion

			bindingType = this.BindingType.HasFromToArray;

			this.resolvedProperty = nodeProperty;

		} else if ( Array.isArray( nodeProperty ) ) {

			bindingType = this.BindingType.EntireArray;

			this.resolvedProperty = nodeProperty;

		} else {

			this.propertyName = propertyName;

		}

		// select getter / setter
		this.getValue = this.GetterByBindingType[ bindingType ];
		this.setValue = this.SetterByBindingTypeAndVersioning[ bindingType ][ versioning ];

	}

	/**
	 * Unbinds the property.
	 */
	unbind() {

		this.node = null;

		// back to the prototype version of getValue / setValue
		// note: avoiding to mutate the shape of 'this' via 'delete'
		this.getValue = this._getValue_unbound;
		this.setValue = this._setValue_unbound;

	}

}
```
</details>

#### Methods

##### `create(root: any, path: string, parsedPath: any): Composite | PropertyBinding`

<details><summary>Code</summary>

```ts
static create( root, path, parsedPath ) {

		if ( ! ( root && root.isAnimationObjectGroup ) ) {

			return new PropertyBinding( root, path, parsedPath );

		} else {

			return new PropertyBinding.Composite( root, path, parsedPath );

		}

	}
```
</details>

##### `sanitizeNodeName(name: string): string`

<details><summary>Code</summary>

```ts
static sanitizeNodeName( name ) {

		return name.replace( /\s/g, '_' ).replace( _reservedRe, '' );

	}
```
</details>

##### `parseTrackName(trackName: string): any`

<details><summary>Code</summary>

```ts
static parseTrackName( trackName ) {

		const matches = _trackRe.exec( trackName );

		if ( matches === null ) {

			throw new Error( 'PropertyBinding: Cannot parse trackName: ' + trackName );

		}

		const results = {
			// directoryName: matches[ 1 ], // (tschw) currently unused
			nodeName: matches[ 2 ],
			objectName: matches[ 3 ],
			objectIndex: matches[ 4 ],
			propertyName: matches[ 5 ], // required
			propertyIndex: matches[ 6 ]
		};

		const lastDot = results.nodeName && results.nodeName.lastIndexOf( '.' );

		if ( lastDot !== undefined && lastDot !== - 1 ) {

			const objectName = results.nodeName.substring( lastDot + 1 );

			// Object names must be checked against an allowlist. Otherwise, there
			// is no way to parse 'foo.bar.baz': 'baz' must be a property, but
			// 'bar' could be the objectName, or part of a nodeName (which can
			// include '.' characters).
			if ( _supportedObjectNames.indexOf( objectName ) !== - 1 ) {

				results.nodeName = results.nodeName.substring( 0, lastDot );
				results.objectName = objectName;

			}

		}

		if ( results.propertyName === null || results.propertyName.length === 0 ) {

			throw new Error( 'PropertyBinding: can not parse propertyName from trackName: ' + trackName );

		}

		return results;

	}
```
</details>

##### `findNode(root: any, nodeName: string | number): any`

<details><summary>Code</summary>

```ts
static findNode( root, nodeName ) {

		if ( nodeName === undefined || nodeName === '' || nodeName === '.' || nodeName === - 1 || nodeName === root.name || nodeName === root.uuid ) {

			return root;

		}

		// search into skeleton bones.
		if ( root.skeleton ) {

			const bone = root.skeleton.getBoneByName( nodeName );

			if ( bone !== undefined ) {

				return bone;

			}

		}

		// search into node subtree.
		if ( root.children ) {

			const searchNodeSubtree = function ( children ) {

				for ( let i = 0; i < children.length; i ++ ) {

					const childNode = children[ i ];

					if ( childNode.name === nodeName || childNode.uuid === nodeName ) {

						return childNode;

					}

					const result = searchNodeSubtree( childNode.children );

					if ( result ) return result;

				}

				return null;

			};

			const subTreeNode = searchNodeSubtree( root.children );

			if ( subTreeNode ) {

				return subTreeNode;

			}

		}

		return null;

	}
```
</details>

##### `_getValue_unavailable(): void`

<details><summary>Code</summary>

```ts
_getValue_unavailable() {}
```
</details>

##### `_setValue_unavailable(): void`

<details><summary>Code</summary>

```ts
_setValue_unavailable() {}
```
</details>

##### `_getValue_direct(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_getValue_direct( buffer, offset ) {

		buffer[ offset ] = this.targetObject[ this.propertyName ];

	}
```
</details>

##### `_getValue_array(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_getValue_array( buffer, offset ) {

		const source = this.resolvedProperty;

		for ( let i = 0, n = source.length; i !== n; ++ i ) {

			buffer[ offset ++ ] = source[ i ];

		}

	}
```
</details>

##### `_getValue_arrayElement(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_getValue_arrayElement( buffer, offset ) {

		buffer[ offset ] = this.resolvedProperty[ this.propertyIndex ];

	}
```
</details>

##### `_getValue_toArray(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_getValue_toArray( buffer, offset ) {

		this.resolvedProperty.toArray( buffer, offset );

	}
```
</details>

##### `_setValue_direct(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_direct( buffer, offset ) {

		this.targetObject[ this.propertyName ] = buffer[ offset ];

	}
```
</details>

##### `_setValue_direct_setNeedsUpdate(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_direct_setNeedsUpdate( buffer, offset ) {

		this.targetObject[ this.propertyName ] = buffer[ offset ];
		this.targetObject.needsUpdate = true;

	}
```
</details>

##### `_setValue_direct_setMatrixWorldNeedsUpdate(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_direct_setMatrixWorldNeedsUpdate( buffer, offset ) {

		this.targetObject[ this.propertyName ] = buffer[ offset ];
		this.targetObject.matrixWorldNeedsUpdate = true;

	}
```
</details>

##### `_setValue_array(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_array( buffer, offset ) {

		const dest = this.resolvedProperty;

		for ( let i = 0, n = dest.length; i !== n; ++ i ) {

			dest[ i ] = buffer[ offset ++ ];

		}

	}
```
</details>

##### `_setValue_array_setNeedsUpdate(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_array_setNeedsUpdate( buffer, offset ) {

		const dest = this.resolvedProperty;

		for ( let i = 0, n = dest.length; i !== n; ++ i ) {

			dest[ i ] = buffer[ offset ++ ];

		}

		this.targetObject.needsUpdate = true;

	}
```
</details>

##### `_setValue_array_setMatrixWorldNeedsUpdate(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_array_setMatrixWorldNeedsUpdate( buffer, offset ) {

		const dest = this.resolvedProperty;

		for ( let i = 0, n = dest.length; i !== n; ++ i ) {

			dest[ i ] = buffer[ offset ++ ];

		}

		this.targetObject.matrixWorldNeedsUpdate = true;

	}
```
</details>

##### `_setValue_arrayElement(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_arrayElement( buffer, offset ) {

		this.resolvedProperty[ this.propertyIndex ] = buffer[ offset ];

	}
```
</details>

##### `_setValue_arrayElement_setNeedsUpdate(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_arrayElement_setNeedsUpdate( buffer, offset ) {

		this.resolvedProperty[ this.propertyIndex ] = buffer[ offset ];
		this.targetObject.needsUpdate = true;

	}
```
</details>

##### `_setValue_arrayElement_setMatrixWorldNeedsUpdate(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_arrayElement_setMatrixWorldNeedsUpdate( buffer, offset ) {

		this.resolvedProperty[ this.propertyIndex ] = buffer[ offset ];
		this.targetObject.matrixWorldNeedsUpdate = true;

	}
```
</details>

##### `_setValue_fromArray(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_fromArray( buffer, offset ) {

		this.resolvedProperty.fromArray( buffer, offset );

	}
```
</details>

##### `_setValue_fromArray_setNeedsUpdate(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_fromArray_setNeedsUpdate( buffer, offset ) {

		this.resolvedProperty.fromArray( buffer, offset );
		this.targetObject.needsUpdate = true;

	}
```
</details>

##### `_setValue_fromArray_setMatrixWorldNeedsUpdate(buffer: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_fromArray_setMatrixWorldNeedsUpdate( buffer, offset ) {

		this.resolvedProperty.fromArray( buffer, offset );
		this.targetObject.matrixWorldNeedsUpdate = true;

	}
```
</details>

##### `_getValue_unbound(targetArray: any, offset: any): void`

<details><summary>Code</summary>

```ts
_getValue_unbound( targetArray, offset ) {

		this.bind();
		this.getValue( targetArray, offset );

	}
```
</details>

##### `_setValue_unbound(sourceArray: any, offset: any): void`

<details><summary>Code</summary>

```ts
_setValue_unbound( sourceArray, offset ) {

		this.bind();
		this.setValue( sourceArray, offset );

	}
```
</details>

##### `bind(): void`

<details><summary>Code</summary>

```ts
bind() {

		let targetObject = this.node;
		const parsedPath = this.parsedPath;

		const objectName = parsedPath.objectName;
		const propertyName = parsedPath.propertyName;
		let propertyIndex = parsedPath.propertyIndex;

		if ( ! targetObject ) {

			targetObject = PropertyBinding.findNode( this.rootNode, parsedPath.nodeName );

			this.node = targetObject;

		}

		// set fail state so we can just 'return' on error
		this.getValue = this._getValue_unavailable;
		this.setValue = this._setValue_unavailable;

		// ensure there is a value node
		if ( ! targetObject ) {

			console.warn( 'THREE.PropertyBinding: No target node found for track: ' + this.path + '.' );
			return;

		}

		if ( objectName ) {

			let objectIndex = parsedPath.objectIndex;

			// special cases were we need to reach deeper into the hierarchy to get the face materials....
			switch ( objectName ) {

				case 'materials':

					if ( ! targetObject.material ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material as node does not have a material.', this );
						return;

					}

					if ( ! targetObject.material.materials ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material.materials as node.material does not have a materials array.', this );
						return;

					}

					targetObject = targetObject.material.materials;

					break;

				case 'bones':

					if ( ! targetObject.skeleton ) {

						console.error( 'THREE.PropertyBinding: Can not bind to bones as node does not have a skeleton.', this );
						return;

					}

					// potential future optimization: skip this if propertyIndex is already an integer
					// and convert the integer string to a true integer.

					targetObject = targetObject.skeleton.bones;

					// support resolving morphTarget names into indices.
					for ( let i = 0; i < targetObject.length; i ++ ) {

						if ( targetObject[ i ].name === objectIndex ) {

							objectIndex = i;
							break;

						}

					}

					break;

				case 'map':

					if ( 'map' in targetObject ) {

						targetObject = targetObject.map;
						break;

					}

					if ( ! targetObject.material ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material as node does not have a material.', this );
						return;

					}

					if ( ! targetObject.material.map ) {

						console.error( 'THREE.PropertyBinding: Can not bind to material.map as node.material does not have a map.', this );
						return;

					}

					targetObject = targetObject.material.map;
					break;

				default:

					if ( targetObject[ objectName ] === undefined ) {

						console.error( 'THREE.PropertyBinding: Can not bind to objectName of node undefined.', this );
						return;

					}

					targetObject = targetObject[ objectName ];

			}


			if ( objectIndex !== undefined ) {

				if ( targetObject[ objectIndex ] === undefined ) {

					console.error( 'THREE.PropertyBinding: Trying to bind to objectIndex of objectName, but is undefined.', this, targetObject );
					return;

				}

				targetObject = targetObject[ objectIndex ];

			}

		}

		// resolve property
		const nodeProperty = targetObject[ propertyName ];

		if ( nodeProperty === undefined ) {

			const nodeName = parsedPath.nodeName;

			console.error( 'THREE.PropertyBinding: Trying to update property for track: ' + nodeName +
				'.' + propertyName + ' but it wasn\'t found.', targetObject );
			return;

		}

		// determine versioning scheme
		let versioning = this.Versioning.None;

		this.targetObject = targetObject;

		if ( targetObject.isMaterial === true ) {

			versioning = this.Versioning.NeedsUpdate;

		} else if ( targetObject.isObject3D === true ) {

			versioning = this.Versioning.MatrixWorldNeedsUpdate;

		}

		// determine how the property gets bound
		let bindingType = this.BindingType.Direct;

		if ( propertyIndex !== undefined ) {

			// access a sub element of the property array (only primitives are supported right now)

			if ( propertyName === 'morphTargetInfluences' ) {

				// potential optimization, skip this if propertyIndex is already an integer, and convert the integer string to a true integer.

				// support resolving morphTarget names into indices.
				if ( ! targetObject.geometry ) {

					console.error( 'THREE.PropertyBinding: Can not bind to morphTargetInfluences because node does not have a geometry.', this );
					return;

				}

				if ( ! targetObject.geometry.morphAttributes ) {

					console.error( 'THREE.PropertyBinding: Can not bind to morphTargetInfluences because node does not have a geometry.morphAttributes.', this );
					return;

				}

				if ( targetObject.morphTargetDictionary[ propertyIndex ] !== undefined ) {

					propertyIndex = targetObject.morphTargetDictionary[ propertyIndex ];

				}

			}

			bindingType = this.BindingType.ArrayElement;

			this.resolvedProperty = nodeProperty;
			this.propertyIndex = propertyIndex;

		} else if ( nodeProperty.fromArray !== undefined && nodeProperty.toArray !== undefined ) {

			// must use copy for Object3D.Euler/Quaternion

			bindingType = this.BindingType.HasFromToArray;

			this.resolvedProperty = nodeProperty;

		} else if ( Array.isArray( nodeProperty ) ) {

			bindingType = this.BindingType.EntireArray;

			this.resolvedProperty = nodeProperty;

		} else {

			this.propertyName = propertyName;

		}

		// select getter / setter
		this.getValue = this.GetterByBindingType[ bindingType ];
		this.setValue = this.SetterByBindingTypeAndVersioning[ bindingType ][ versioning ];

	}
```
</details>

##### `unbind(): void`

<details><summary>Code</summary>

```ts
unbind() {

		this.node = null;

		// back to the prototype version of getValue / setValue
		// note: avoiding to mutate the shape of 'this' via 'delete'
		this.getValue = this._getValue_unbound;
		this.setValue = this._setValue_unbound;

	}
```
</details>


---