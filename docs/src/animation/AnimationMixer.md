[⬅️ Back to Table of Contents](../../index.md)

# 📄 `AnimationMixer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 25 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 110 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/animation/AnimationMixer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationAction` | `./AnimationAction.js` |
| `EventDispatcher` | `../core/EventDispatcher.js` |
| `LinearInterpolant` | `../math/interpolants/LinearInterpolant.js` |
| `PropertyBinding` | `./PropertyBinding.js` |
| `PropertyMixer` | `./PropertyMixer.js` |
| `AnimationClip` | `./AnimationClip.js` |
| `NormalAnimationBlendMode` | `../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_controlInterpolantsResultB...` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 1 )` | ✗ |
| `root` | `any` | let/var | `action._localRoot \|\| this._root` | ✗ |
| `tracks` | `any` | let/var | `action._clip.tracks` | ✗ |
| `nTracks` | `any` | let/var | `tracks.length` | ✗ |
| `bindings` | `any` | let/var | `action._propertyBindings` | ✗ |
| `interpolants` | `any` | let/var | `action._interpolants` | ✗ |
| `rootUuid` | `any` | let/var | `root.uuid` | ✗ |
| `bindingsByRoot` | `{}` | let/var | `this._bindingsByRootAndName` | ✗ |
| `bindingsByName` | `any` | let/var | `bindingsByRoot[ rootUuid ]` | ✗ |
| `track` | `any` | let/var | `tracks[ i ]` | ✗ |
| `trackName` | `any` | let/var | `track.name` | ✗ |
| `binding` | `any` | let/var | `bindingsByName[ trackName ]` | ✗ |
| `path` | `any` | let/var | `prototypeAction && prototypeAction. _propertyBindings[ i ].binding.parsedPath` | ✗ |
| `rootUuid` | `any` | let/var | `( action._localRoot \|\| this._root ).uuid` | ✗ |
| `clipUuid` | `any` | let/var | `action._clip.uuid` | ✗ |
| `actionsForClip` | `any` | let/var | `this._actionsByClip[ clipUuid ]` | ✗ |
| `bindings` | `any` | let/var | `action._propertyBindings` | ✗ |
| `binding` | `any` | let/var | `bindings[ i ]` | ✗ |
| `bindings` | `any` | let/var | `action._propertyBindings` | ✗ |
| `binding` | `any` | let/var | `bindings[ i ]` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `index` | `any` | let/var | `action._cacheIndex` | ✗ |
| `actions` | `any[]` | let/var | `this._actions` | ✗ |
| `actionsByClip` | `{}` | let/var | `this._actionsByClip` | ✗ |
| `actionsForClip` | `any` | let/var | `actionsByClip[ clipUuid ]` | ✗ |
| `knownActions` | `any` | let/var | `actionsForClip.knownActions` | ✗ |
| `actions` | `any[]` | let/var | `this._actions` | ✗ |
| `lastInactiveAction` | `any` | let/var | `actions[ actions.length - 1 ]` | ✗ |
| `cacheIndex` | `any` | let/var | `action._cacheIndex` | ✗ |
| `clipUuid` | `any` | let/var | `action._clip.uuid` | ✗ |
| `actionsByClip` | `{}` | let/var | `this._actionsByClip` | ✗ |
| `actionsForClip` | `any` | let/var | `actionsByClip[ clipUuid ]` | ✗ |
| `knownActionsForClip` | `any` | let/var | `actionsForClip.knownActions` | ✗ |
| `lastKnownAction` | `any` | let/var | `knownActionsForClip[ knownActionsForClip.length - 1 ]` | ✗ |
| `byClipCacheIndex` | `any` | let/var | `action._byClipCacheIndex` | ✗ |
| `actionByRoot` | `any` | let/var | `actionsForClip.actionByRoot` | ✗ |
| `rootUuid` | `any` | let/var | `( action._localRoot \|\| this._root ).uuid` | ✗ |
| `bindings` | `any` | let/var | `action._propertyBindings` | ✗ |
| `binding` | `any` | let/var | `bindings[ i ]` | ✗ |
| `actions` | `any[]` | let/var | `this._actions` | ✗ |
| `prevIndex` | `any` | let/var | `action._cacheIndex` | ✗ |
| `lastActiveIndex` | `number` | let/var | `this._nActiveActions ++` | ✗ |
| `firstInactiveAction` | `any` | let/var | `actions[ lastActiveIndex ]` | ✗ |
| `actions` | `any[]` | let/var | `this._actions` | ✗ |
| `prevIndex` | `any` | let/var | `action._cacheIndex` | ✗ |
| `firstInactiveIndex` | `number` | let/var | `-- this._nActiveActions` | ✗ |
| `lastActiveAction` | `any` | let/var | `actions[ firstInactiveIndex ]` | ✗ |
| `bindingsByRoot` | `{}` | let/var | `this._bindingsByRootAndName` | ✗ |
| `bindings` | `any[]` | let/var | `this._bindings` | ✗ |
| `bindingByName` | `any` | let/var | `bindingsByRoot[ rootUuid ]` | ✗ |
| `bindings` | `any[]` | let/var | `this._bindings` | ✗ |
| `propBinding` | `any` | let/var | `binding.binding` | ✗ |
| `rootUuid` | `any` | let/var | `propBinding.rootNode.uuid` | ✗ |
| `trackName` | `any` | let/var | `propBinding.path` | ✗ |
| `bindingsByRoot` | `{}` | let/var | `this._bindingsByRootAndName` | ✗ |
| `bindingByName` | `any` | let/var | `bindingsByRoot[ rootUuid ]` | ✗ |
| `lastInactiveBinding` | `any` | let/var | `bindings[ bindings.length - 1 ]` | ✗ |
| `cacheIndex` | `any` | let/var | `binding._cacheIndex` | ✗ |
| `bindings` | `any[]` | let/var | `this._bindings` | ✗ |
| `prevIndex` | `any` | let/var | `binding._cacheIndex` | ✗ |
| `lastActiveIndex` | `number` | let/var | `this._nActiveBindings ++` | ✗ |
| `firstInactiveBinding` | `any` | let/var | `bindings[ lastActiveIndex ]` | ✗ |
| `bindings` | `any[]` | let/var | `this._bindings` | ✗ |
| `prevIndex` | `any` | let/var | `binding._cacheIndex` | ✗ |
| `firstInactiveIndex` | `number` | let/var | `-- this._nActiveBindings` | ✗ |
| `lastActiveBinding` | `any` | let/var | `bindings[ firstInactiveIndex ]` | ✗ |
| `interpolants` | `any[]` | let/var | `this._controlInterpolants` | ✗ |
| `lastActiveIndex` | `number` | let/var | `this._nActiveControlInterpolants ++` | ✗ |
| `interpolant` | `any` | let/var | `interpolants[ lastActiveIndex ]` | ✗ |
| `interpolants` | `any[]` | let/var | `this._controlInterpolants` | ✗ |
| `prevIndex` | `any` | let/var | `interpolant.__cacheIndex` | ✗ |
| `firstInactiveIndex` | `number` | let/var | `-- this._nActiveControlInterpolants` | ✗ |
| `lastActiveInterpolant` | `any` | let/var | `interpolants[ firstInactiveIndex ]` | ✗ |
| `root` | `any` | let/var | `optionalRoot \|\| this._root` | ✗ |
| `rootUuid` | `any` | let/var | `root.uuid` | ✗ |
| `clipObject` | `AnimationClip` | let/var | `typeof clip === 'string' ? AnimationClip.findByName( root, clip ) : clip` | ✗ |
| `clipUuid` | `string \| AnimationClip` | let/var | `clipObject !== null ? clipObject.uuid : clip` | ✗ |
| `actionsForClip` | `any` | let/var | `this._actionsByClip[ clipUuid ]` | ✗ |
| `prototypeAction` | `any` | let/var | `null` | ✗ |
| `existingAction` | `any` | let/var | `actionsForClip.actionByRoot[ rootUuid ]` | ✗ |
| `newAction` | `AnimationAction` | let/var | `new AnimationAction( this, clipObject, optionalRoot, blendMode )` | ✗ |
| `root` | `any` | let/var | `optionalRoot \|\| this._root` | ✗ |
| `rootUuid` | `any` | let/var | `root.uuid` | ✗ |
| `clipObject` | `AnimationClip` | let/var | `typeof clip === 'string' ? AnimationClip.findByName( root, clip ) : clip` | ✗ |
| `clipUuid` | `string \| AnimationClip` | let/var | `clipObject ? clipObject.uuid : clip` | ✗ |
| `actionsForClip` | `any` | let/var | `this._actionsByClip[ clipUuid ]` | ✗ |
| `actions` | `any[]` | let/var | `this._actions` | ✗ |
| `nActions` | `number` | let/var | `this._nActiveActions` | ✗ |
| `actions` | `any[]` | let/var | `this._actions` | ✗ |
| `nActions` | `number` | let/var | `this._nActiveActions` | ✗ |
| `time` | `number` | let/var | `this.time += deltaTime` | ✗ |
| `accuIndex` | `number` | let/var | `this._accuIndex ^= 1` | ✗ |
| `action` | `any` | let/var | `actions[ i ]` | ✗ |
| `bindings` | `any[]` | let/var | `this._bindings` | ✗ |
| `nBindings` | `number` | let/var | `this._nActiveBindings` | ✗ |
| `actions` | `any[]` | let/var | `this._actions` | ✗ |
| `clipUuid` | `string` | let/var | `clip.uuid` | ✗ |
| `actionsByClip` | `{}` | let/var | `this._actionsByClip` | ✗ |
| `actionsForClip` | `any` | let/var | `actionsByClip[ clipUuid ]` | ✗ |
| `actionsToRemove` | `any` | let/var | `actionsForClip.knownActions` | ✗ |
| `action` | `any` | let/var | `actionsToRemove[ i ]` | ✗ |
| `cacheIndex` | `any` | let/var | `action._cacheIndex` | ✗ |
| `lastInactiveAction` | `any` | let/var | `actions[ actions.length - 1 ]` | ✗ |
| `rootUuid` | `any` | let/var | `root.uuid` | ✗ |
| `actionsByClip` | `{}` | let/var | `this._actionsByClip` | ✗ |
| `actionByRoot` | `any` | let/var | `actionsByClip[ clipUuid ].actionByRoot` | ✗ |
| `action` | `any` | let/var | `actionByRoot[ rootUuid ]` | ✗ |
| `bindingsByRoot` | `{}` | let/var | `this._bindingsByRootAndName` | ✗ |
| `bindingByName` | `any` | let/var | `bindingsByRoot[ rootUuid ]` | ✗ |
| `binding` | `any` | let/var | `bindingByName[ trackName ]` | ✗ |


---

## Functions

### `AnimationMixer._bindAction(action: any, prototypeAction: any): void`

**Parameters:**

- **`action`** `any`
- **`prototypeAction`** `any`

**Returns:** `void`

**Calls:**

- `this._addInactiveBinding`
- `PropertyBinding.create`
- `track.getValueSize`

**Internal Comments:**
```
// existing binding, make sure the cache knows
```

<details><summary>Code</summary>

```typescript
_bindAction( action, prototypeAction ) {

		const root = action._localRoot || this._root,
			tracks = action._clip.tracks,
			nTracks = tracks.length,
			bindings = action._propertyBindings,
			interpolants = action._interpolants,
			rootUuid = root.uuid,
			bindingsByRoot = this._bindingsByRootAndName;

		let bindingsByName = bindingsByRoot[ rootUuid ];

		if ( bindingsByName === undefined ) {

			bindingsByName = {};
			bindingsByRoot[ rootUuid ] = bindingsByName;

		}

		for ( let i = 0; i !== nTracks; ++ i ) {

			const track = tracks[ i ],
				trackName = track.name;

			let binding = bindingsByName[ trackName ];

			if ( binding !== undefined ) {

				++ binding.referenceCount;
				bindings[ i ] = binding;

			} else {

				binding = bindings[ i ];

				if ( binding !== undefined ) {

					// existing binding, make sure the cache knows

					if ( binding._cacheIndex === null ) {

						++ binding.referenceCount;
						this._addInactiveBinding( binding, rootUuid, trackName );

					}

					continue;

				}

				const path = prototypeAction && prototypeAction.
					_propertyBindings[ i ].binding.parsedPath;

				binding = new PropertyMixer(
					PropertyBinding.create( root, trackName, path ),
					track.ValueTypeName, track.getValueSize() );

				++ binding.referenceCount;
				this._addInactiveBinding( binding, rootUuid, trackName );

				bindings[ i ] = binding;

			}

			interpolants[ i ].resultBuffer = binding.buffer;

		}

	}
```
</details>

### `AnimationMixer._activateAction(action: any): void`

**Parameters:**

- **`action`** `any`

**Returns:** `void`

**Calls:**

- `this._isActiveAction`
- `this._bindAction`
- `this._addInactiveAction`
- `this._lendBinding`
- `binding.saveOriginalState`
- `this._lendAction`

**Internal Comments:**
```
// this action has been forgotten by the cache, but the user (x2)
// appears to be still using it -> rebind (x2)
// increment reference counts / sort out state
```

<details><summary>Code</summary>

```typescript
_activateAction( action ) {

		if ( ! this._isActiveAction( action ) ) {

			if ( action._cacheIndex === null ) {

				// this action has been forgotten by the cache, but the user
				// appears to be still using it -> rebind

				const rootUuid = ( action._localRoot || this._root ).uuid,
					clipUuid = action._clip.uuid,
					actionsForClip = this._actionsByClip[ clipUuid ];

				this._bindAction( action,
					actionsForClip && actionsForClip.knownActions[ 0 ] );

				this._addInactiveAction( action, clipUuid, rootUuid );

			}

			const bindings = action._propertyBindings;

			// increment reference counts / sort out state
			for ( let i = 0, n = bindings.length; i !== n; ++ i ) {

				const binding = bindings[ i ];

				if ( binding.useCount ++ === 0 ) {

					this._lendBinding( binding );
					binding.saveOriginalState();

				}

			}

			this._lendAction( action );

		}

	}
```
</details>

### `AnimationMixer._deactivateAction(action: any): void`

**Parameters:**

- **`action`** `any`

**Returns:** `void`

**Calls:**

- `this._isActiveAction`
- `binding.restoreOriginalState`
- `this._takeBackBinding`
- `this._takeBackAction`

**Internal Comments:**
```
// decrement reference counts / sort out state
```

<details><summary>Code</summary>

```typescript
_deactivateAction( action ) {

		if ( this._isActiveAction( action ) ) {

			const bindings = action._propertyBindings;

			// decrement reference counts / sort out state
			for ( let i = 0, n = bindings.length; i !== n; ++ i ) {

				const binding = bindings[ i ];

				if ( -- binding.useCount === 0 ) {

					binding.restoreOriginalState();
					this._takeBackBinding( binding );

				}

			}

			this._takeBackAction( action );

		}

	}
```
</details>

### `AnimationMixer._initMemoryManager(): void`

**Returns:** `void`

**Internal Comments:**
```
// inside: (x4)
// { (x4)
// 	knownActions: Array< AnimationAction > - used as prototypes (x4)
// 	actionByRoot: AnimationAction - lookup (x4)
// } (x4)
```

<details><summary>Code</summary>

```typescript
_initMemoryManager() {

		this._actions = []; // 'nActiveActions' followed by inactive ones
		this._nActiveActions = 0;

		this._actionsByClip = {};
		// inside:
		// {
		// 	knownActions: Array< AnimationAction > - used as prototypes
		// 	actionByRoot: AnimationAction - lookup
		// }


		this._bindings = []; // 'nActiveBindings' followed by inactive ones
		this._nActiveBindings = 0;

		this._bindingsByRootAndName = {}; // inside: Map< name, PropertyMixer >


		this._controlInterpolants = []; // same game as above
		this._nActiveControlInterpolants = 0;

		const scope = this;

		this.stats = {

			actions: {
				get total() {

					return scope._actions.length;

				},
				get inUse() {

					return scope._nActiveActions;

				}
			},
			bindings: {
				get total() {

					return scope._bindings.length;

				},
				get inUse() {

					return scope._nActiveBindings;

				}
			},
			controlInterpolants: {
				get total() {

					return scope._controlInterpolants.length;

				},
				get inUse() {

					return scope._nActiveControlInterpolants;

				}
			}

		};

	}
```
</details>

### `AnimationMixer._isActiveAction(action: any): boolean`

**Parameters:**

- **`action`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
_isActiveAction( action ) {

		const index = action._cacheIndex;
		return index !== null && index < this._nActiveActions;

	}
```
</details>

### `AnimationMixer._addInactiveAction(action: any, clipUuid: any, rootUuid: any): void`

**Parameters:**

- **`action`** `any`
- **`clipUuid`** `any`
- **`rootUuid`** `any`

**Returns:** `void`

**Calls:**

- `knownActions.push`
- `actions.push`

<details><summary>Code</summary>

```typescript
_addInactiveAction( action, clipUuid, rootUuid ) {

		const actions = this._actions,
			actionsByClip = this._actionsByClip;

		let actionsForClip = actionsByClip[ clipUuid ];

		if ( actionsForClip === undefined ) {

			actionsForClip = {

				knownActions: [ action ],
				actionByRoot: {}

			};

			action._byClipCacheIndex = 0;

			actionsByClip[ clipUuid ] = actionsForClip;

		} else {

			const knownActions = actionsForClip.knownActions;

			action._byClipCacheIndex = knownActions.length;
			knownActions.push( action );

		}

		action._cacheIndex = actions.length;
		actions.push( action );

		actionsForClip.actionByRoot[ rootUuid ] = action;

	}
```
</details>

### `AnimationMixer._removeInactiveAction(action: any): void`

**Parameters:**

- **`action`** `any`

**Returns:** `void`

**Calls:**

- `actions.pop`
- `knownActionsForClip.pop`
- `this._removeInactiveBindingsForAction`

<details><summary>Code</summary>

```typescript
_removeInactiveAction( action ) {

		const actions = this._actions,
			lastInactiveAction = actions[ actions.length - 1 ],
			cacheIndex = action._cacheIndex;

		lastInactiveAction._cacheIndex = cacheIndex;
		actions[ cacheIndex ] = lastInactiveAction;
		actions.pop();

		action._cacheIndex = null;


		const clipUuid = action._clip.uuid,
			actionsByClip = this._actionsByClip,
			actionsForClip = actionsByClip[ clipUuid ],
			knownActionsForClip = actionsForClip.knownActions,

			lastKnownAction =
				knownActionsForClip[ knownActionsForClip.length - 1 ],

			byClipCacheIndex = action._byClipCacheIndex;

		lastKnownAction._byClipCacheIndex = byClipCacheIndex;
		knownActionsForClip[ byClipCacheIndex ] = lastKnownAction;
		knownActionsForClip.pop();

		action._byClipCacheIndex = null;


		const actionByRoot = actionsForClip.actionByRoot,
			rootUuid = ( action._localRoot || this._root ).uuid;

		delete actionByRoot[ rootUuid ];

		if ( knownActionsForClip.length === 0 ) {

			delete actionsByClip[ clipUuid ];

		}

		this._removeInactiveBindingsForAction( action );

	}
```
</details>

### `AnimationMixer._removeInactiveBindingsForAction(action: any): void`

**Parameters:**

- **`action`** `any`

**Returns:** `void`

**Calls:**

- `this._removeInactiveBinding`

<details><summary>Code</summary>

```typescript
_removeInactiveBindingsForAction( action ) {

		const bindings = action._propertyBindings;

		for ( let i = 0, n = bindings.length; i !== n; ++ i ) {

			const binding = bindings[ i ];

			if ( -- binding.referenceCount === 0 ) {

				this._removeInactiveBinding( binding );

			}

		}

	}
```
</details>

### `AnimationMixer._lendAction(action: any): void`

**Parameters:**

- **`action`** `any`

**Returns:** `void`

**Internal Comments:**
```
// [ active actions |  inactive actions  ] (x2)
// [  active actions >| inactive actions ] (x2)
//                 s        a (x2)
//                  <-swap-> (x2)
//                 a        s (x2)
```

<details><summary>Code</summary>

```typescript
_lendAction( action ) {

		// [ active actions |  inactive actions  ]
		// [  active actions >| inactive actions ]
		//                 s        a
		//                  <-swap->
		//                 a        s

		const actions = this._actions,
			prevIndex = action._cacheIndex,

			lastActiveIndex = this._nActiveActions ++,

			firstInactiveAction = actions[ lastActiveIndex ];

		action._cacheIndex = lastActiveIndex;
		actions[ lastActiveIndex ] = action;

		firstInactiveAction._cacheIndex = prevIndex;
		actions[ prevIndex ] = firstInactiveAction;

	}
```
</details>

### `AnimationMixer._takeBackAction(action: any): void`

**Parameters:**

- **`action`** `any`

**Returns:** `void`

**Internal Comments:**
```
// [  active actions  | inactive actions ] (x2)
// [ active actions |< inactive actions  ] (x2)
//        a        s (x2)
//         <-swap-> (x2)
//        s        a (x2)
```

<details><summary>Code</summary>

```typescript
_takeBackAction( action ) {

		// [  active actions  | inactive actions ]
		// [ active actions |< inactive actions  ]
		//        a        s
		//         <-swap->
		//        s        a

		const actions = this._actions,
			prevIndex = action._cacheIndex,

			firstInactiveIndex = -- this._nActiveActions,

			lastActiveAction = actions[ firstInactiveIndex ];

		action._cacheIndex = firstInactiveIndex;
		actions[ firstInactiveIndex ] = action;

		lastActiveAction._cacheIndex = prevIndex;
		actions[ prevIndex ] = lastActiveAction;

	}
```
</details>

### `AnimationMixer._addInactiveBinding(binding: any, rootUuid: any, trackName: any): void`

**Parameters:**

- **`binding`** `any`
- **`rootUuid`** `any`
- **`trackName`** `any`

**Returns:** `void`

**Calls:**

- `bindings.push`

<details><summary>Code</summary>

```typescript
_addInactiveBinding( binding, rootUuid, trackName ) {

		const bindingsByRoot = this._bindingsByRootAndName,
			bindings = this._bindings;

		let bindingByName = bindingsByRoot[ rootUuid ];

		if ( bindingByName === undefined ) {

			bindingByName = {};
			bindingsByRoot[ rootUuid ] = bindingByName;

		}

		bindingByName[ trackName ] = binding;

		binding._cacheIndex = bindings.length;
		bindings.push( binding );

	}
```
</details>

### `AnimationMixer._removeInactiveBinding(binding: any): void`

**Parameters:**

- **`binding`** `any`

**Returns:** `void`

**Calls:**

- `bindings.pop`
- `Object.keys`

<details><summary>Code</summary>

```typescript
_removeInactiveBinding( binding ) {

		const bindings = this._bindings,
			propBinding = binding.binding,
			rootUuid = propBinding.rootNode.uuid,
			trackName = propBinding.path,
			bindingsByRoot = this._bindingsByRootAndName,
			bindingByName = bindingsByRoot[ rootUuid ],

			lastInactiveBinding = bindings[ bindings.length - 1 ],
			cacheIndex = binding._cacheIndex;

		lastInactiveBinding._cacheIndex = cacheIndex;
		bindings[ cacheIndex ] = lastInactiveBinding;
		bindings.pop();

		delete bindingByName[ trackName ];

		if ( Object.keys( bindingByName ).length === 0 ) {

			delete bindingsByRoot[ rootUuid ];

		}

	}
```
</details>

### `AnimationMixer._lendBinding(binding: any): void`

**Parameters:**

- **`binding`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_lendBinding( binding ) {

		const bindings = this._bindings,
			prevIndex = binding._cacheIndex,

			lastActiveIndex = this._nActiveBindings ++,

			firstInactiveBinding = bindings[ lastActiveIndex ];

		binding._cacheIndex = lastActiveIndex;
		bindings[ lastActiveIndex ] = binding;

		firstInactiveBinding._cacheIndex = prevIndex;
		bindings[ prevIndex ] = firstInactiveBinding;

	}
```
</details>

### `AnimationMixer._takeBackBinding(binding: any): void`

**Parameters:**

- **`binding`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_takeBackBinding( binding ) {

		const bindings = this._bindings,
			prevIndex = binding._cacheIndex,

			firstInactiveIndex = -- this._nActiveBindings,

			lastActiveBinding = bindings[ firstInactiveIndex ];

		binding._cacheIndex = firstInactiveIndex;
		bindings[ firstInactiveIndex ] = binding;

		lastActiveBinding._cacheIndex = prevIndex;
		bindings[ prevIndex ] = lastActiveBinding;

	}
```
</details>

### `AnimationMixer._lendControlInterpolant(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
_lendControlInterpolant() {

		const interpolants = this._controlInterpolants,
			lastActiveIndex = this._nActiveControlInterpolants ++;

		let interpolant = interpolants[ lastActiveIndex ];

		if ( interpolant === undefined ) {

			interpolant = new LinearInterpolant(
				new Float32Array( 2 ), new Float32Array( 2 ),
				1, _controlInterpolantsResultBuffer );

			interpolant.__cacheIndex = lastActiveIndex;
			interpolants[ lastActiveIndex ] = interpolant;

		}

		return interpolant;

	}
```
</details>

### `AnimationMixer._takeBackControlInterpolant(interpolant: any): void`

**Parameters:**

- **`interpolant`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_takeBackControlInterpolant( interpolant ) {

		const interpolants = this._controlInterpolants,
			prevIndex = interpolant.__cacheIndex,

			firstInactiveIndex = -- this._nActiveControlInterpolants,

			lastActiveInterpolant = interpolants[ firstInactiveIndex ];

		interpolant.__cacheIndex = firstInactiveIndex;
		interpolants[ firstInactiveIndex ] = interpolant;

		lastActiveInterpolant.__cacheIndex = prevIndex;
		interpolants[ prevIndex ] = lastActiveInterpolant;

	}
```
</details>

### `AnimationMixer.clipAction(clip: string | AnimationClip, optionalRoot: Object3D, blendMode: any): AnimationAction`

**JSDoc:**
```typescript
/**
	 * Returns an instance of {@link AnimationAction} for the passed clip.
	 *
	 * If an action fitting the clip and root parameters doesn't yet exist, it
	 * will be created by this method. Calling this method several times with the
	 * same clip and root parameters always returns the same action.
	 *
	 * @param {AnimationClip|string} clip - An animation clip or alternatively the name of the animation clip.
	 * @param {Object3D} [optionalRoot] - An alternative root object.
	 * @param {(NormalAnimationBlendMode|AdditiveAnimationBlendMode)} [blendMode] - The blend mode.
	 * @return {?AnimationAction} The animation action.
	 */
```

**Parameters:**

- **`clip`** `string | AnimationClip`
- **`optionalRoot`** `Object3D`
- **`blendMode`** `any`

**Returns:** `AnimationAction`

**Calls:**

- `AnimationClip.findByName`
- `this._bindAction`
- `this._addInactiveAction`

**Internal Comments:**
```
// we know the clip, so we don't have to parse all (x3)
// the bindings again but can just copy (x3)
// also, take the clip from the prototype action
// clip must be known when specified via string
// allocate all resources required to run it (x2)
// and make the action known to the memory manager (x4)
```

<details><summary>Code</summary>

```typescript
clipAction( clip, optionalRoot, blendMode ) {

		const root = optionalRoot || this._root,
			rootUuid = root.uuid;

		let clipObject = typeof clip === 'string' ? AnimationClip.findByName( root, clip ) : clip;

		const clipUuid = clipObject !== null ? clipObject.uuid : clip;

		const actionsForClip = this._actionsByClip[ clipUuid ];
		let prototypeAction = null;

		if ( blendMode === undefined ) {

			if ( clipObject !== null ) {

				blendMode = clipObject.blendMode;

			} else {

				blendMode = NormalAnimationBlendMode;

			}

		}

		if ( actionsForClip !== undefined ) {

			const existingAction = actionsForClip.actionByRoot[ rootUuid ];

			if ( existingAction !== undefined && existingAction.blendMode === blendMode ) {

				return existingAction;

			}

			// we know the clip, so we don't have to parse all
			// the bindings again but can just copy
			prototypeAction = actionsForClip.knownActions[ 0 ];

			// also, take the clip from the prototype action
			if ( clipObject === null )
				clipObject = prototypeAction._clip;

		}

		// clip must be known when specified via string
		if ( clipObject === null ) return null;

		// allocate all resources required to run it
		const newAction = new AnimationAction( this, clipObject, optionalRoot, blendMode );

		this._bindAction( newAction, prototypeAction );

		// and make the action known to the memory manager
		this._addInactiveAction( newAction, clipUuid, rootUuid );

		return newAction;

	}
```
</details>

### `AnimationMixer.existingAction(clip: string | AnimationClip, optionalRoot: Object3D): AnimationAction`

**JSDoc:**
```typescript
/**
	 * Returns an existing animation action for the passed clip.
	 *
	 * @param {AnimationClip|string} clip - An animation clip or alternatively the name of the animation clip.
	 * @param {Object3D} [optionalRoot] - An alternative root object.
	 * @return {?AnimationAction} The animation action. Returns `null` if no action was found.
	 */
```

**Parameters:**

- **`clip`** `string | AnimationClip`
- **`optionalRoot`** `Object3D`

**Returns:** `AnimationAction`

**Calls:**

- `AnimationClip.findByName`

<details><summary>Code</summary>

```typescript
existingAction( clip, optionalRoot ) {

		const root = optionalRoot || this._root,
			rootUuid = root.uuid,

			clipObject = typeof clip === 'string' ?
				AnimationClip.findByName( root, clip ) : clip,

			clipUuid = clipObject ? clipObject.uuid : clip,

			actionsForClip = this._actionsByClip[ clipUuid ];

		if ( actionsForClip !== undefined ) {

			return actionsForClip.actionByRoot[ rootUuid ] || null;

		}

		return null;

	}
```
</details>

### `AnimationMixer.stopAllAction(): AnimationMixer`

**JSDoc:**
```typescript
/**
	 * Deactivates all previously scheduled actions on this mixer.
	 *
	 * @return {AnimationMixer} A reference to thi animation mixer.
	 */
```

**Returns:** `AnimationMixer`

**Calls:**

- `actions[ i ].stop`

<details><summary>Code</summary>

```typescript
stopAllAction() {

		const actions = this._actions,
			nActions = this._nActiveActions;

		for ( let i = nActions - 1; i >= 0; -- i ) {

			actions[ i ].stop();

		}

		return this;

	}
```
</details>

### `AnimationMixer.update(deltaTime: number): AnimationMixer`

**JSDoc:**
```typescript
/**
	 * Advances the global mixer time and updates the animation.
	 *
	 * This is usually done in the render loop by passing the delta
	 * time from {@link Clock} or {@link Timer}.
	 *
	 * @param {number} deltaTime - The delta time in seconds.
	 * @return {AnimationMixer} A reference to thi animation mixer.
	 */
```

**Parameters:**

- **`deltaTime`** `number`

**Returns:** `AnimationMixer`

**Calls:**

- `Math.sign`
- `action._update`
- `bindings[ i ].apply`

**Internal Comments:**
```
// run active actions
// update scene graph (x2)
```

<details><summary>Code</summary>

```typescript
update( deltaTime ) {

		deltaTime *= this.timeScale;

		const actions = this._actions,
			nActions = this._nActiveActions,

			time = this.time += deltaTime,
			timeDirection = Math.sign( deltaTime ),

			accuIndex = this._accuIndex ^= 1;

		// run active actions

		for ( let i = 0; i !== nActions; ++ i ) {

			const action = actions[ i ];

			action._update( time, deltaTime, timeDirection, accuIndex );

		}

		// update scene graph

		const bindings = this._bindings,
			nBindings = this._nActiveBindings;

		for ( let i = 0; i !== nBindings; ++ i ) {

			bindings[ i ].apply( accuIndex );

		}

		return this;

	}
```
</details>

### `AnimationMixer.setTime(time: number): AnimationMixer`

**JSDoc:**
```typescript
/**
	 * Sets the global mixer to a specific time and updates the animation accordingly.
	 *
	 * This is useful when you need to jump to an exact time in an animation. The
	 * input parameter will be scaled by {@link AnimationMixer#timeScale}
	 *
	 * @param {number} time - The time to set in seconds.
	 * @return {AnimationMixer} A reference to thi animation mixer.
	 */
```

**Parameters:**

- **`time`** `number`

**Returns:** `AnimationMixer`

**Calls:**

- `this.update`

<details><summary>Code</summary>

```typescript
setTime( time ) {

		this.time = 0; // Zero out time attribute for AnimationMixer object;
		for ( let i = 0; i < this._actions.length; i ++ ) {

			this._actions[ i ].time = 0; // Zero out time attribute for all associated AnimationAction objects.

		}

		return this.update( time ); // Update used to set exact time. Returns "this" AnimationMixer object.

	}
```
</details>

### `AnimationMixer.getRoot(): Object3D`

**JSDoc:**
```typescript
/**
	 * Returns this mixer's root object.
	 *
	 * @return {Object3D} The mixer's root object.
	 */
```

**Returns:** `Object3D`

<details><summary>Code</summary>

```typescript
getRoot() {

		return this._root;

	}
```
</details>

### `AnimationMixer.uncacheClip(clip: AnimationClip): void`

**JSDoc:**
```typescript
/**
	 * Deallocates all memory resources for a clip. Before using this method make
	 * sure to call {@link AnimationAction#stop} for all related actions.
	 *
	 * @param {AnimationClip} clip - The clip to uncache.
	 */
```

**Parameters:**

- **`clip`** `AnimationClip`

**Returns:** `void`

**Calls:**

- `this._deactivateAction`
- `actions.pop`
- `this._removeInactiveBindingsForAction`

**Internal Comments:**
```
// note: just calling _removeInactiveAction would mess up the (x2)
// iteration state and also require updating the state we can (x2)
// just throw away (x2)
```

<details><summary>Code</summary>

```typescript
uncacheClip( clip ) {

		const actions = this._actions,
			clipUuid = clip.uuid,
			actionsByClip = this._actionsByClip,
			actionsForClip = actionsByClip[ clipUuid ];

		if ( actionsForClip !== undefined ) {

			// note: just calling _removeInactiveAction would mess up the
			// iteration state and also require updating the state we can
			// just throw away

			const actionsToRemove = actionsForClip.knownActions;

			for ( let i = 0, n = actionsToRemove.length; i !== n; ++ i ) {

				const action = actionsToRemove[ i ];

				this._deactivateAction( action );

				const cacheIndex = action._cacheIndex,
					lastInactiveAction = actions[ actions.length - 1 ];

				action._cacheIndex = null;
				action._byClipCacheIndex = null;

				lastInactiveAction._cacheIndex = cacheIndex;
				actions[ cacheIndex ] = lastInactiveAction;
				actions.pop();

				this._removeInactiveBindingsForAction( action );

			}

			delete actionsByClip[ clipUuid ];

		}

	}
```
</details>

### `AnimationMixer.uncacheRoot(root: Object3D): void`

**JSDoc:**
```typescript
/**
	 * Deallocates all memory resources for a root object. Before using this
	 * method make sure to call {@link AnimationAction#stop} for all related
	 * actions or alternatively {@link AnimationMixer#stopAllAction} when the
	 * mixer operates on a single root.
	 *
	 * @param {Object3D} root - The root object to uncache.
	 */
```

**Parameters:**

- **`root`** `Object3D`

**Returns:** `void`

**Calls:**

- `this._deactivateAction`
- `this._removeInactiveAction`
- `binding.restoreOriginalState`
- `this._removeInactiveBinding`

<details><summary>Code</summary>

```typescript
uncacheRoot( root ) {

		const rootUuid = root.uuid,
			actionsByClip = this._actionsByClip;

		for ( const clipUuid in actionsByClip ) {

			const actionByRoot = actionsByClip[ clipUuid ].actionByRoot,
				action = actionByRoot[ rootUuid ];

			if ( action !== undefined ) {

				this._deactivateAction( action );
				this._removeInactiveAction( action );

			}

		}

		const bindingsByRoot = this._bindingsByRootAndName,
			bindingByName = bindingsByRoot[ rootUuid ];

		if ( bindingByName !== undefined ) {

			for ( const trackName in bindingByName ) {

				const binding = bindingByName[ trackName ];
				binding.restoreOriginalState();
				this._removeInactiveBinding( binding );

			}

		}

	}
```
</details>

### `AnimationMixer.uncacheAction(clip: string | AnimationClip, optionalRoot: Object3D): void`

**JSDoc:**
```typescript
/**
	 * Deallocates all memory resources for an action. The action is identified by the
	 * given clip and an optional root object. Before using this method make
	 * sure to call {@link AnimationAction#stop} to deactivate the action.
	 *
	 * @param {AnimationClip|string} clip - An animation clip or alternatively the name of the animation clip.
	 * @param {Object3D} [optionalRoot] - An alternative root object.
	 */
```

**Parameters:**

- **`clip`** `string | AnimationClip`
- **`optionalRoot`** `Object3D`

**Returns:** `void`

**Calls:**

- `this.existingAction`
- `this._deactivateAction`
- `this._removeInactiveAction`

<details><summary>Code</summary>

```typescript
uncacheAction( clip, optionalRoot ) {

		const action = this.existingAction( clip, optionalRoot );

		if ( action !== null ) {

			this._deactivateAction( action );
			this._removeInactiveAction( action );

		}

	}
```
</details>


---

## Classes

### `AnimationMixer`

<details><summary>Class Code</summary>

```ts
class AnimationMixer extends EventDispatcher {

	/**
	 * Constructs a new animation mixer.
	 *
	 * @param {Object3D} root - The object whose animations shall be played by this mixer.
	 */
	constructor( root ) {

		super();

		this._root = root;
		this._initMemoryManager();
		this._accuIndex = 0;

		/**
		 * The global mixer time (in seconds; starting with `0` on the mixer's creation).
		 *
		 * @type {number}
		 * @default 0
		 */
		this.time = 0;

		/**
		 * A scaling factor for the global time.
		 *
		 * Note: Setting this member to `0` and later back to `1` is a
		 * possibility to pause/unpause all actions that are controlled by this
		 * mixer.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.timeScale = 1.0;

	}

	_bindAction( action, prototypeAction ) {

		const root = action._localRoot || this._root,
			tracks = action._clip.tracks,
			nTracks = tracks.length,
			bindings = action._propertyBindings,
			interpolants = action._interpolants,
			rootUuid = root.uuid,
			bindingsByRoot = this._bindingsByRootAndName;

		let bindingsByName = bindingsByRoot[ rootUuid ];

		if ( bindingsByName === undefined ) {

			bindingsByName = {};
			bindingsByRoot[ rootUuid ] = bindingsByName;

		}

		for ( let i = 0; i !== nTracks; ++ i ) {

			const track = tracks[ i ],
				trackName = track.name;

			let binding = bindingsByName[ trackName ];

			if ( binding !== undefined ) {

				++ binding.referenceCount;
				bindings[ i ] = binding;

			} else {

				binding = bindings[ i ];

				if ( binding !== undefined ) {

					// existing binding, make sure the cache knows

					if ( binding._cacheIndex === null ) {

						++ binding.referenceCount;
						this._addInactiveBinding( binding, rootUuid, trackName );

					}

					continue;

				}

				const path = prototypeAction && prototypeAction.
					_propertyBindings[ i ].binding.parsedPath;

				binding = new PropertyMixer(
					PropertyBinding.create( root, trackName, path ),
					track.ValueTypeName, track.getValueSize() );

				++ binding.referenceCount;
				this._addInactiveBinding( binding, rootUuid, trackName );

				bindings[ i ] = binding;

			}

			interpolants[ i ].resultBuffer = binding.buffer;

		}

	}

	_activateAction( action ) {

		if ( ! this._isActiveAction( action ) ) {

			if ( action._cacheIndex === null ) {

				// this action has been forgotten by the cache, but the user
				// appears to be still using it -> rebind

				const rootUuid = ( action._localRoot || this._root ).uuid,
					clipUuid = action._clip.uuid,
					actionsForClip = this._actionsByClip[ clipUuid ];

				this._bindAction( action,
					actionsForClip && actionsForClip.knownActions[ 0 ] );

				this._addInactiveAction( action, clipUuid, rootUuid );

			}

			const bindings = action._propertyBindings;

			// increment reference counts / sort out state
			for ( let i = 0, n = bindings.length; i !== n; ++ i ) {

				const binding = bindings[ i ];

				if ( binding.useCount ++ === 0 ) {

					this._lendBinding( binding );
					binding.saveOriginalState();

				}

			}

			this._lendAction( action );

		}

	}

	_deactivateAction( action ) {

		if ( this._isActiveAction( action ) ) {

			const bindings = action._propertyBindings;

			// decrement reference counts / sort out state
			for ( let i = 0, n = bindings.length; i !== n; ++ i ) {

				const binding = bindings[ i ];

				if ( -- binding.useCount === 0 ) {

					binding.restoreOriginalState();
					this._takeBackBinding( binding );

				}

			}

			this._takeBackAction( action );

		}

	}

	// Memory manager

	_initMemoryManager() {

		this._actions = []; // 'nActiveActions' followed by inactive ones
		this._nActiveActions = 0;

		this._actionsByClip = {};
		// inside:
		// {
		// 	knownActions: Array< AnimationAction > - used as prototypes
		// 	actionByRoot: AnimationAction - lookup
		// }


		this._bindings = []; // 'nActiveBindings' followed by inactive ones
		this._nActiveBindings = 0;

		this._bindingsByRootAndName = {}; // inside: Map< name, PropertyMixer >


		this._controlInterpolants = []; // same game as above
		this._nActiveControlInterpolants = 0;

		const scope = this;

		this.stats = {

			actions: {
				get total() {

					return scope._actions.length;

				},
				get inUse() {

					return scope._nActiveActions;

				}
			},
			bindings: {
				get total() {

					return scope._bindings.length;

				},
				get inUse() {

					return scope._nActiveBindings;

				}
			},
			controlInterpolants: {
				get total() {

					return scope._controlInterpolants.length;

				},
				get inUse() {

					return scope._nActiveControlInterpolants;

				}
			}

		};

	}

	// Memory management for AnimationAction objects

	_isActiveAction( action ) {

		const index = action._cacheIndex;
		return index !== null && index < this._nActiveActions;

	}

	_addInactiveAction( action, clipUuid, rootUuid ) {

		const actions = this._actions,
			actionsByClip = this._actionsByClip;

		let actionsForClip = actionsByClip[ clipUuid ];

		if ( actionsForClip === undefined ) {

			actionsForClip = {

				knownActions: [ action ],
				actionByRoot: {}

			};

			action._byClipCacheIndex = 0;

			actionsByClip[ clipUuid ] = actionsForClip;

		} else {

			const knownActions = actionsForClip.knownActions;

			action._byClipCacheIndex = knownActions.length;
			knownActions.push( action );

		}

		action._cacheIndex = actions.length;
		actions.push( action );

		actionsForClip.actionByRoot[ rootUuid ] = action;

	}

	_removeInactiveAction( action ) {

		const actions = this._actions,
			lastInactiveAction = actions[ actions.length - 1 ],
			cacheIndex = action._cacheIndex;

		lastInactiveAction._cacheIndex = cacheIndex;
		actions[ cacheIndex ] = lastInactiveAction;
		actions.pop();

		action._cacheIndex = null;


		const clipUuid = action._clip.uuid,
			actionsByClip = this._actionsByClip,
			actionsForClip = actionsByClip[ clipUuid ],
			knownActionsForClip = actionsForClip.knownActions,

			lastKnownAction =
				knownActionsForClip[ knownActionsForClip.length - 1 ],

			byClipCacheIndex = action._byClipCacheIndex;

		lastKnownAction._byClipCacheIndex = byClipCacheIndex;
		knownActionsForClip[ byClipCacheIndex ] = lastKnownAction;
		knownActionsForClip.pop();

		action._byClipCacheIndex = null;


		const actionByRoot = actionsForClip.actionByRoot,
			rootUuid = ( action._localRoot || this._root ).uuid;

		delete actionByRoot[ rootUuid ];

		if ( knownActionsForClip.length === 0 ) {

			delete actionsByClip[ clipUuid ];

		}

		this._removeInactiveBindingsForAction( action );

	}

	_removeInactiveBindingsForAction( action ) {

		const bindings = action._propertyBindings;

		for ( let i = 0, n = bindings.length; i !== n; ++ i ) {

			const binding = bindings[ i ];

			if ( -- binding.referenceCount === 0 ) {

				this._removeInactiveBinding( binding );

			}

		}

	}

	_lendAction( action ) {

		// [ active actions |  inactive actions  ]
		// [  active actions >| inactive actions ]
		//                 s        a
		//                  <-swap->
		//                 a        s

		const actions = this._actions,
			prevIndex = action._cacheIndex,

			lastActiveIndex = this._nActiveActions ++,

			firstInactiveAction = actions[ lastActiveIndex ];

		action._cacheIndex = lastActiveIndex;
		actions[ lastActiveIndex ] = action;

		firstInactiveAction._cacheIndex = prevIndex;
		actions[ prevIndex ] = firstInactiveAction;

	}

	_takeBackAction( action ) {

		// [  active actions  | inactive actions ]
		// [ active actions |< inactive actions  ]
		//        a        s
		//         <-swap->
		//        s        a

		const actions = this._actions,
			prevIndex = action._cacheIndex,

			firstInactiveIndex = -- this._nActiveActions,

			lastActiveAction = actions[ firstInactiveIndex ];

		action._cacheIndex = firstInactiveIndex;
		actions[ firstInactiveIndex ] = action;

		lastActiveAction._cacheIndex = prevIndex;
		actions[ prevIndex ] = lastActiveAction;

	}

	// Memory management for PropertyMixer objects

	_addInactiveBinding( binding, rootUuid, trackName ) {

		const bindingsByRoot = this._bindingsByRootAndName,
			bindings = this._bindings;

		let bindingByName = bindingsByRoot[ rootUuid ];

		if ( bindingByName === undefined ) {

			bindingByName = {};
			bindingsByRoot[ rootUuid ] = bindingByName;

		}

		bindingByName[ trackName ] = binding;

		binding._cacheIndex = bindings.length;
		bindings.push( binding );

	}

	_removeInactiveBinding( binding ) {

		const bindings = this._bindings,
			propBinding = binding.binding,
			rootUuid = propBinding.rootNode.uuid,
			trackName = propBinding.path,
			bindingsByRoot = this._bindingsByRootAndName,
			bindingByName = bindingsByRoot[ rootUuid ],

			lastInactiveBinding = bindings[ bindings.length - 1 ],
			cacheIndex = binding._cacheIndex;

		lastInactiveBinding._cacheIndex = cacheIndex;
		bindings[ cacheIndex ] = lastInactiveBinding;
		bindings.pop();

		delete bindingByName[ trackName ];

		if ( Object.keys( bindingByName ).length === 0 ) {

			delete bindingsByRoot[ rootUuid ];

		}

	}

	_lendBinding( binding ) {

		const bindings = this._bindings,
			prevIndex = binding._cacheIndex,

			lastActiveIndex = this._nActiveBindings ++,

			firstInactiveBinding = bindings[ lastActiveIndex ];

		binding._cacheIndex = lastActiveIndex;
		bindings[ lastActiveIndex ] = binding;

		firstInactiveBinding._cacheIndex = prevIndex;
		bindings[ prevIndex ] = firstInactiveBinding;

	}

	_takeBackBinding( binding ) {

		const bindings = this._bindings,
			prevIndex = binding._cacheIndex,

			firstInactiveIndex = -- this._nActiveBindings,

			lastActiveBinding = bindings[ firstInactiveIndex ];

		binding._cacheIndex = firstInactiveIndex;
		bindings[ firstInactiveIndex ] = binding;

		lastActiveBinding._cacheIndex = prevIndex;
		bindings[ prevIndex ] = lastActiveBinding;

	}


	// Memory management of Interpolants for weight and time scale

	_lendControlInterpolant() {

		const interpolants = this._controlInterpolants,
			lastActiveIndex = this._nActiveControlInterpolants ++;

		let interpolant = interpolants[ lastActiveIndex ];

		if ( interpolant === undefined ) {

			interpolant = new LinearInterpolant(
				new Float32Array( 2 ), new Float32Array( 2 ),
				1, _controlInterpolantsResultBuffer );

			interpolant.__cacheIndex = lastActiveIndex;
			interpolants[ lastActiveIndex ] = interpolant;

		}

		return interpolant;

	}

	_takeBackControlInterpolant( interpolant ) {

		const interpolants = this._controlInterpolants,
			prevIndex = interpolant.__cacheIndex,

			firstInactiveIndex = -- this._nActiveControlInterpolants,

			lastActiveInterpolant = interpolants[ firstInactiveIndex ];

		interpolant.__cacheIndex = firstInactiveIndex;
		interpolants[ firstInactiveIndex ] = interpolant;

		lastActiveInterpolant.__cacheIndex = prevIndex;
		interpolants[ prevIndex ] = lastActiveInterpolant;

	}

	/**
	 * Returns an instance of {@link AnimationAction} for the passed clip.
	 *
	 * If an action fitting the clip and root parameters doesn't yet exist, it
	 * will be created by this method. Calling this method several times with the
	 * same clip and root parameters always returns the same action.
	 *
	 * @param {AnimationClip|string} clip - An animation clip or alternatively the name of the animation clip.
	 * @param {Object3D} [optionalRoot] - An alternative root object.
	 * @param {(NormalAnimationBlendMode|AdditiveAnimationBlendMode)} [blendMode] - The blend mode.
	 * @return {?AnimationAction} The animation action.
	 */
	clipAction( clip, optionalRoot, blendMode ) {

		const root = optionalRoot || this._root,
			rootUuid = root.uuid;

		let clipObject = typeof clip === 'string' ? AnimationClip.findByName( root, clip ) : clip;

		const clipUuid = clipObject !== null ? clipObject.uuid : clip;

		const actionsForClip = this._actionsByClip[ clipUuid ];
		let prototypeAction = null;

		if ( blendMode === undefined ) {

			if ( clipObject !== null ) {

				blendMode = clipObject.blendMode;

			} else {

				blendMode = NormalAnimationBlendMode;

			}

		}

		if ( actionsForClip !== undefined ) {

			const existingAction = actionsForClip.actionByRoot[ rootUuid ];

			if ( existingAction !== undefined && existingAction.blendMode === blendMode ) {

				return existingAction;

			}

			// we know the clip, so we don't have to parse all
			// the bindings again but can just copy
			prototypeAction = actionsForClip.knownActions[ 0 ];

			// also, take the clip from the prototype action
			if ( clipObject === null )
				clipObject = prototypeAction._clip;

		}

		// clip must be known when specified via string
		if ( clipObject === null ) return null;

		// allocate all resources required to run it
		const newAction = new AnimationAction( this, clipObject, optionalRoot, blendMode );

		this._bindAction( newAction, prototypeAction );

		// and make the action known to the memory manager
		this._addInactiveAction( newAction, clipUuid, rootUuid );

		return newAction;

	}

	/**
	 * Returns an existing animation action for the passed clip.
	 *
	 * @param {AnimationClip|string} clip - An animation clip or alternatively the name of the animation clip.
	 * @param {Object3D} [optionalRoot] - An alternative root object.
	 * @return {?AnimationAction} The animation action. Returns `null` if no action was found.
	 */
	existingAction( clip, optionalRoot ) {

		const root = optionalRoot || this._root,
			rootUuid = root.uuid,

			clipObject = typeof clip === 'string' ?
				AnimationClip.findByName( root, clip ) : clip,

			clipUuid = clipObject ? clipObject.uuid : clip,

			actionsForClip = this._actionsByClip[ clipUuid ];

		if ( actionsForClip !== undefined ) {

			return actionsForClip.actionByRoot[ rootUuid ] || null;

		}

		return null;

	}

	/**
	 * Deactivates all previously scheduled actions on this mixer.
	 *
	 * @return {AnimationMixer} A reference to thi animation mixer.
	 */
	stopAllAction() {

		const actions = this._actions,
			nActions = this._nActiveActions;

		for ( let i = nActions - 1; i >= 0; -- i ) {

			actions[ i ].stop();

		}

		return this;

	}

	/**
	 * Advances the global mixer time and updates the animation.
	 *
	 * This is usually done in the render loop by passing the delta
	 * time from {@link Clock} or {@link Timer}.
	 *
	 * @param {number} deltaTime - The delta time in seconds.
	 * @return {AnimationMixer} A reference to thi animation mixer.
	 */
	update( deltaTime ) {

		deltaTime *= this.timeScale;

		const actions = this._actions,
			nActions = this._nActiveActions,

			time = this.time += deltaTime,
			timeDirection = Math.sign( deltaTime ),

			accuIndex = this._accuIndex ^= 1;

		// run active actions

		for ( let i = 0; i !== nActions; ++ i ) {

			const action = actions[ i ];

			action._update( time, deltaTime, timeDirection, accuIndex );

		}

		// update scene graph

		const bindings = this._bindings,
			nBindings = this._nActiveBindings;

		for ( let i = 0; i !== nBindings; ++ i ) {

			bindings[ i ].apply( accuIndex );

		}

		return this;

	}

	/**
	 * Sets the global mixer to a specific time and updates the animation accordingly.
	 *
	 * This is useful when you need to jump to an exact time in an animation. The
	 * input parameter will be scaled by {@link AnimationMixer#timeScale}
	 *
	 * @param {number} time - The time to set in seconds.
	 * @return {AnimationMixer} A reference to thi animation mixer.
	 */
	setTime( time ) {

		this.time = 0; // Zero out time attribute for AnimationMixer object;
		for ( let i = 0; i < this._actions.length; i ++ ) {

			this._actions[ i ].time = 0; // Zero out time attribute for all associated AnimationAction objects.

		}

		return this.update( time ); // Update used to set exact time. Returns "this" AnimationMixer object.

	}

	/**
	 * Returns this mixer's root object.
	 *
	 * @return {Object3D} The mixer's root object.
	 */
	getRoot() {

		return this._root;

	}

	/**
	 * Deallocates all memory resources for a clip. Before using this method make
	 * sure to call {@link AnimationAction#stop} for all related actions.
	 *
	 * @param {AnimationClip} clip - The clip to uncache.
	 */
	uncacheClip( clip ) {

		const actions = this._actions,
			clipUuid = clip.uuid,
			actionsByClip = this._actionsByClip,
			actionsForClip = actionsByClip[ clipUuid ];

		if ( actionsForClip !== undefined ) {

			// note: just calling _removeInactiveAction would mess up the
			// iteration state and also require updating the state we can
			// just throw away

			const actionsToRemove = actionsForClip.knownActions;

			for ( let i = 0, n = actionsToRemove.length; i !== n; ++ i ) {

				const action = actionsToRemove[ i ];

				this._deactivateAction( action );

				const cacheIndex = action._cacheIndex,
					lastInactiveAction = actions[ actions.length - 1 ];

				action._cacheIndex = null;
				action._byClipCacheIndex = null;

				lastInactiveAction._cacheIndex = cacheIndex;
				actions[ cacheIndex ] = lastInactiveAction;
				actions.pop();

				this._removeInactiveBindingsForAction( action );

			}

			delete actionsByClip[ clipUuid ];

		}

	}

	/**
	 * Deallocates all memory resources for a root object. Before using this
	 * method make sure to call {@link AnimationAction#stop} for all related
	 * actions or alternatively {@link AnimationMixer#stopAllAction} when the
	 * mixer operates on a single root.
	 *
	 * @param {Object3D} root - The root object to uncache.
	 */
	uncacheRoot( root ) {

		const rootUuid = root.uuid,
			actionsByClip = this._actionsByClip;

		for ( const clipUuid in actionsByClip ) {

			const actionByRoot = actionsByClip[ clipUuid ].actionByRoot,
				action = actionByRoot[ rootUuid ];

			if ( action !== undefined ) {

				this._deactivateAction( action );
				this._removeInactiveAction( action );

			}

		}

		const bindingsByRoot = this._bindingsByRootAndName,
			bindingByName = bindingsByRoot[ rootUuid ];

		if ( bindingByName !== undefined ) {

			for ( const trackName in bindingByName ) {

				const binding = bindingByName[ trackName ];
				binding.restoreOriginalState();
				this._removeInactiveBinding( binding );

			}

		}

	}

	/**
	 * Deallocates all memory resources for an action. The action is identified by the
	 * given clip and an optional root object. Before using this method make
	 * sure to call {@link AnimationAction#stop} to deactivate the action.
	 *
	 * @param {AnimationClip|string} clip - An animation clip or alternatively the name of the animation clip.
	 * @param {Object3D} [optionalRoot] - An alternative root object.
	 */
	uncacheAction( clip, optionalRoot ) {

		const action = this.existingAction( clip, optionalRoot );

		if ( action !== null ) {

			this._deactivateAction( action );
			this._removeInactiveAction( action );

		}

	}

}
```
</details>

#### Methods

##### `_bindAction(action: any, prototypeAction: any): void`

<details><summary>Code</summary>

```ts
_bindAction( action, prototypeAction ) {

		const root = action._localRoot || this._root,
			tracks = action._clip.tracks,
			nTracks = tracks.length,
			bindings = action._propertyBindings,
			interpolants = action._interpolants,
			rootUuid = root.uuid,
			bindingsByRoot = this._bindingsByRootAndName;

		let bindingsByName = bindingsByRoot[ rootUuid ];

		if ( bindingsByName === undefined ) {

			bindingsByName = {};
			bindingsByRoot[ rootUuid ] = bindingsByName;

		}

		for ( let i = 0; i !== nTracks; ++ i ) {

			const track = tracks[ i ],
				trackName = track.name;

			let binding = bindingsByName[ trackName ];

			if ( binding !== undefined ) {

				++ binding.referenceCount;
				bindings[ i ] = binding;

			} else {

				binding = bindings[ i ];

				if ( binding !== undefined ) {

					// existing binding, make sure the cache knows

					if ( binding._cacheIndex === null ) {

						++ binding.referenceCount;
						this._addInactiveBinding( binding, rootUuid, trackName );

					}

					continue;

				}

				const path = prototypeAction && prototypeAction.
					_propertyBindings[ i ].binding.parsedPath;

				binding = new PropertyMixer(
					PropertyBinding.create( root, trackName, path ),
					track.ValueTypeName, track.getValueSize() );

				++ binding.referenceCount;
				this._addInactiveBinding( binding, rootUuid, trackName );

				bindings[ i ] = binding;

			}

			interpolants[ i ].resultBuffer = binding.buffer;

		}

	}
```
</details>

##### `_activateAction(action: any): void`

<details><summary>Code</summary>

```ts
_activateAction( action ) {

		if ( ! this._isActiveAction( action ) ) {

			if ( action._cacheIndex === null ) {

				// this action has been forgotten by the cache, but the user
				// appears to be still using it -> rebind

				const rootUuid = ( action._localRoot || this._root ).uuid,
					clipUuid = action._clip.uuid,
					actionsForClip = this._actionsByClip[ clipUuid ];

				this._bindAction( action,
					actionsForClip && actionsForClip.knownActions[ 0 ] );

				this._addInactiveAction( action, clipUuid, rootUuid );

			}

			const bindings = action._propertyBindings;

			// increment reference counts / sort out state
			for ( let i = 0, n = bindings.length; i !== n; ++ i ) {

				const binding = bindings[ i ];

				if ( binding.useCount ++ === 0 ) {

					this._lendBinding( binding );
					binding.saveOriginalState();

				}

			}

			this._lendAction( action );

		}

	}
```
</details>

##### `_deactivateAction(action: any): void`

<details><summary>Code</summary>

```ts
_deactivateAction( action ) {

		if ( this._isActiveAction( action ) ) {

			const bindings = action._propertyBindings;

			// decrement reference counts / sort out state
			for ( let i = 0, n = bindings.length; i !== n; ++ i ) {

				const binding = bindings[ i ];

				if ( -- binding.useCount === 0 ) {

					binding.restoreOriginalState();
					this._takeBackBinding( binding );

				}

			}

			this._takeBackAction( action );

		}

	}
```
</details>

##### `_initMemoryManager(): void`

<details><summary>Code</summary>

```ts
_initMemoryManager() {

		this._actions = []; // 'nActiveActions' followed by inactive ones
		this._nActiveActions = 0;

		this._actionsByClip = {};
		// inside:
		// {
		// 	knownActions: Array< AnimationAction > - used as prototypes
		// 	actionByRoot: AnimationAction - lookup
		// }


		this._bindings = []; // 'nActiveBindings' followed by inactive ones
		this._nActiveBindings = 0;

		this._bindingsByRootAndName = {}; // inside: Map< name, PropertyMixer >


		this._controlInterpolants = []; // same game as above
		this._nActiveControlInterpolants = 0;

		const scope = this;

		this.stats = {

			actions: {
				get total() {

					return scope._actions.length;

				},
				get inUse() {

					return scope._nActiveActions;

				}
			},
			bindings: {
				get total() {

					return scope._bindings.length;

				},
				get inUse() {

					return scope._nActiveBindings;

				}
			},
			controlInterpolants: {
				get total() {

					return scope._controlInterpolants.length;

				},
				get inUse() {

					return scope._nActiveControlInterpolants;

				}
			}

		};

	}
```
</details>

##### `_isActiveAction(action: any): boolean`

<details><summary>Code</summary>

```ts
_isActiveAction( action ) {

		const index = action._cacheIndex;
		return index !== null && index < this._nActiveActions;

	}
```
</details>

##### `_addInactiveAction(action: any, clipUuid: any, rootUuid: any): void`

<details><summary>Code</summary>

```ts
_addInactiveAction( action, clipUuid, rootUuid ) {

		const actions = this._actions,
			actionsByClip = this._actionsByClip;

		let actionsForClip = actionsByClip[ clipUuid ];

		if ( actionsForClip === undefined ) {

			actionsForClip = {

				knownActions: [ action ],
				actionByRoot: {}

			};

			action._byClipCacheIndex = 0;

			actionsByClip[ clipUuid ] = actionsForClip;

		} else {

			const knownActions = actionsForClip.knownActions;

			action._byClipCacheIndex = knownActions.length;
			knownActions.push( action );

		}

		action._cacheIndex = actions.length;
		actions.push( action );

		actionsForClip.actionByRoot[ rootUuid ] = action;

	}
```
</details>

##### `_removeInactiveAction(action: any): void`

<details><summary>Code</summary>

```ts
_removeInactiveAction( action ) {

		const actions = this._actions,
			lastInactiveAction = actions[ actions.length - 1 ],
			cacheIndex = action._cacheIndex;

		lastInactiveAction._cacheIndex = cacheIndex;
		actions[ cacheIndex ] = lastInactiveAction;
		actions.pop();

		action._cacheIndex = null;


		const clipUuid = action._clip.uuid,
			actionsByClip = this._actionsByClip,
			actionsForClip = actionsByClip[ clipUuid ],
			knownActionsForClip = actionsForClip.knownActions,

			lastKnownAction =
				knownActionsForClip[ knownActionsForClip.length - 1 ],

			byClipCacheIndex = action._byClipCacheIndex;

		lastKnownAction._byClipCacheIndex = byClipCacheIndex;
		knownActionsForClip[ byClipCacheIndex ] = lastKnownAction;
		knownActionsForClip.pop();

		action._byClipCacheIndex = null;


		const actionByRoot = actionsForClip.actionByRoot,
			rootUuid = ( action._localRoot || this._root ).uuid;

		delete actionByRoot[ rootUuid ];

		if ( knownActionsForClip.length === 0 ) {

			delete actionsByClip[ clipUuid ];

		}

		this._removeInactiveBindingsForAction( action );

	}
```
</details>

##### `_removeInactiveBindingsForAction(action: any): void`

<details><summary>Code</summary>

```ts
_removeInactiveBindingsForAction( action ) {

		const bindings = action._propertyBindings;

		for ( let i = 0, n = bindings.length; i !== n; ++ i ) {

			const binding = bindings[ i ];

			if ( -- binding.referenceCount === 0 ) {

				this._removeInactiveBinding( binding );

			}

		}

	}
```
</details>

##### `_lendAction(action: any): void`

<details><summary>Code</summary>

```ts
_lendAction( action ) {

		// [ active actions |  inactive actions  ]
		// [  active actions >| inactive actions ]
		//                 s        a
		//                  <-swap->
		//                 a        s

		const actions = this._actions,
			prevIndex = action._cacheIndex,

			lastActiveIndex = this._nActiveActions ++,

			firstInactiveAction = actions[ lastActiveIndex ];

		action._cacheIndex = lastActiveIndex;
		actions[ lastActiveIndex ] = action;

		firstInactiveAction._cacheIndex = prevIndex;
		actions[ prevIndex ] = firstInactiveAction;

	}
```
</details>

##### `_takeBackAction(action: any): void`

<details><summary>Code</summary>

```ts
_takeBackAction( action ) {

		// [  active actions  | inactive actions ]
		// [ active actions |< inactive actions  ]
		//        a        s
		//         <-swap->
		//        s        a

		const actions = this._actions,
			prevIndex = action._cacheIndex,

			firstInactiveIndex = -- this._nActiveActions,

			lastActiveAction = actions[ firstInactiveIndex ];

		action._cacheIndex = firstInactiveIndex;
		actions[ firstInactiveIndex ] = action;

		lastActiveAction._cacheIndex = prevIndex;
		actions[ prevIndex ] = lastActiveAction;

	}
```
</details>

##### `_addInactiveBinding(binding: any, rootUuid: any, trackName: any): void`

<details><summary>Code</summary>

```ts
_addInactiveBinding( binding, rootUuid, trackName ) {

		const bindingsByRoot = this._bindingsByRootAndName,
			bindings = this._bindings;

		let bindingByName = bindingsByRoot[ rootUuid ];

		if ( bindingByName === undefined ) {

			bindingByName = {};
			bindingsByRoot[ rootUuid ] = bindingByName;

		}

		bindingByName[ trackName ] = binding;

		binding._cacheIndex = bindings.length;
		bindings.push( binding );

	}
```
</details>

##### `_removeInactiveBinding(binding: any): void`

<details><summary>Code</summary>

```ts
_removeInactiveBinding( binding ) {

		const bindings = this._bindings,
			propBinding = binding.binding,
			rootUuid = propBinding.rootNode.uuid,
			trackName = propBinding.path,
			bindingsByRoot = this._bindingsByRootAndName,
			bindingByName = bindingsByRoot[ rootUuid ],

			lastInactiveBinding = bindings[ bindings.length - 1 ],
			cacheIndex = binding._cacheIndex;

		lastInactiveBinding._cacheIndex = cacheIndex;
		bindings[ cacheIndex ] = lastInactiveBinding;
		bindings.pop();

		delete bindingByName[ trackName ];

		if ( Object.keys( bindingByName ).length === 0 ) {

			delete bindingsByRoot[ rootUuid ];

		}

	}
```
</details>

##### `_lendBinding(binding: any): void`

<details><summary>Code</summary>

```ts
_lendBinding( binding ) {

		const bindings = this._bindings,
			prevIndex = binding._cacheIndex,

			lastActiveIndex = this._nActiveBindings ++,

			firstInactiveBinding = bindings[ lastActiveIndex ];

		binding._cacheIndex = lastActiveIndex;
		bindings[ lastActiveIndex ] = binding;

		firstInactiveBinding._cacheIndex = prevIndex;
		bindings[ prevIndex ] = firstInactiveBinding;

	}
```
</details>

##### `_takeBackBinding(binding: any): void`

<details><summary>Code</summary>

```ts
_takeBackBinding( binding ) {

		const bindings = this._bindings,
			prevIndex = binding._cacheIndex,

			firstInactiveIndex = -- this._nActiveBindings,

			lastActiveBinding = bindings[ firstInactiveIndex ];

		binding._cacheIndex = firstInactiveIndex;
		bindings[ firstInactiveIndex ] = binding;

		lastActiveBinding._cacheIndex = prevIndex;
		bindings[ prevIndex ] = lastActiveBinding;

	}
```
</details>

##### `_lendControlInterpolant(): any`

<details><summary>Code</summary>

```ts
_lendControlInterpolant() {

		const interpolants = this._controlInterpolants,
			lastActiveIndex = this._nActiveControlInterpolants ++;

		let interpolant = interpolants[ lastActiveIndex ];

		if ( interpolant === undefined ) {

			interpolant = new LinearInterpolant(
				new Float32Array( 2 ), new Float32Array( 2 ),
				1, _controlInterpolantsResultBuffer );

			interpolant.__cacheIndex = lastActiveIndex;
			interpolants[ lastActiveIndex ] = interpolant;

		}

		return interpolant;

	}
```
</details>

##### `_takeBackControlInterpolant(interpolant: any): void`

<details><summary>Code</summary>

```ts
_takeBackControlInterpolant( interpolant ) {

		const interpolants = this._controlInterpolants,
			prevIndex = interpolant.__cacheIndex,

			firstInactiveIndex = -- this._nActiveControlInterpolants,

			lastActiveInterpolant = interpolants[ firstInactiveIndex ];

		interpolant.__cacheIndex = firstInactiveIndex;
		interpolants[ firstInactiveIndex ] = interpolant;

		lastActiveInterpolant.__cacheIndex = prevIndex;
		interpolants[ prevIndex ] = lastActiveInterpolant;

	}
```
</details>

##### `clipAction(clip: string | AnimationClip, optionalRoot: Object3D, blendMode: any): AnimationAction`

<details><summary>Code</summary>

```ts
clipAction( clip, optionalRoot, blendMode ) {

		const root = optionalRoot || this._root,
			rootUuid = root.uuid;

		let clipObject = typeof clip === 'string' ? AnimationClip.findByName( root, clip ) : clip;

		const clipUuid = clipObject !== null ? clipObject.uuid : clip;

		const actionsForClip = this._actionsByClip[ clipUuid ];
		let prototypeAction = null;

		if ( blendMode === undefined ) {

			if ( clipObject !== null ) {

				blendMode = clipObject.blendMode;

			} else {

				blendMode = NormalAnimationBlendMode;

			}

		}

		if ( actionsForClip !== undefined ) {

			const existingAction = actionsForClip.actionByRoot[ rootUuid ];

			if ( existingAction !== undefined && existingAction.blendMode === blendMode ) {

				return existingAction;

			}

			// we know the clip, so we don't have to parse all
			// the bindings again but can just copy
			prototypeAction = actionsForClip.knownActions[ 0 ];

			// also, take the clip from the prototype action
			if ( clipObject === null )
				clipObject = prototypeAction._clip;

		}

		// clip must be known when specified via string
		if ( clipObject === null ) return null;

		// allocate all resources required to run it
		const newAction = new AnimationAction( this, clipObject, optionalRoot, blendMode );

		this._bindAction( newAction, prototypeAction );

		// and make the action known to the memory manager
		this._addInactiveAction( newAction, clipUuid, rootUuid );

		return newAction;

	}
```
</details>

##### `existingAction(clip: string | AnimationClip, optionalRoot: Object3D): AnimationAction`

<details><summary>Code</summary>

```ts
existingAction( clip, optionalRoot ) {

		const root = optionalRoot || this._root,
			rootUuid = root.uuid,

			clipObject = typeof clip === 'string' ?
				AnimationClip.findByName( root, clip ) : clip,

			clipUuid = clipObject ? clipObject.uuid : clip,

			actionsForClip = this._actionsByClip[ clipUuid ];

		if ( actionsForClip !== undefined ) {

			return actionsForClip.actionByRoot[ rootUuid ] || null;

		}

		return null;

	}
```
</details>

##### `stopAllAction(): AnimationMixer`

<details><summary>Code</summary>

```ts
stopAllAction() {

		const actions = this._actions,
			nActions = this._nActiveActions;

		for ( let i = nActions - 1; i >= 0; -- i ) {

			actions[ i ].stop();

		}

		return this;

	}
```
</details>

##### `update(deltaTime: number): AnimationMixer`

<details><summary>Code</summary>

```ts
update( deltaTime ) {

		deltaTime *= this.timeScale;

		const actions = this._actions,
			nActions = this._nActiveActions,

			time = this.time += deltaTime,
			timeDirection = Math.sign( deltaTime ),

			accuIndex = this._accuIndex ^= 1;

		// run active actions

		for ( let i = 0; i !== nActions; ++ i ) {

			const action = actions[ i ];

			action._update( time, deltaTime, timeDirection, accuIndex );

		}

		// update scene graph

		const bindings = this._bindings,
			nBindings = this._nActiveBindings;

		for ( let i = 0; i !== nBindings; ++ i ) {

			bindings[ i ].apply( accuIndex );

		}

		return this;

	}
```
</details>

##### `setTime(time: number): AnimationMixer`

<details><summary>Code</summary>

```ts
setTime( time ) {

		this.time = 0; // Zero out time attribute for AnimationMixer object;
		for ( let i = 0; i < this._actions.length; i ++ ) {

			this._actions[ i ].time = 0; // Zero out time attribute for all associated AnimationAction objects.

		}

		return this.update( time ); // Update used to set exact time. Returns "this" AnimationMixer object.

	}
```
</details>

##### `getRoot(): Object3D`

<details><summary>Code</summary>

```ts
getRoot() {

		return this._root;

	}
```
</details>

##### `uncacheClip(clip: AnimationClip): void`

<details><summary>Code</summary>

```ts
uncacheClip( clip ) {

		const actions = this._actions,
			clipUuid = clip.uuid,
			actionsByClip = this._actionsByClip,
			actionsForClip = actionsByClip[ clipUuid ];

		if ( actionsForClip !== undefined ) {

			// note: just calling _removeInactiveAction would mess up the
			// iteration state and also require updating the state we can
			// just throw away

			const actionsToRemove = actionsForClip.knownActions;

			for ( let i = 0, n = actionsToRemove.length; i !== n; ++ i ) {

				const action = actionsToRemove[ i ];

				this._deactivateAction( action );

				const cacheIndex = action._cacheIndex,
					lastInactiveAction = actions[ actions.length - 1 ];

				action._cacheIndex = null;
				action._byClipCacheIndex = null;

				lastInactiveAction._cacheIndex = cacheIndex;
				actions[ cacheIndex ] = lastInactiveAction;
				actions.pop();

				this._removeInactiveBindingsForAction( action );

			}

			delete actionsByClip[ clipUuid ];

		}

	}
```
</details>

##### `uncacheRoot(root: Object3D): void`

<details><summary>Code</summary>

```ts
uncacheRoot( root ) {

		const rootUuid = root.uuid,
			actionsByClip = this._actionsByClip;

		for ( const clipUuid in actionsByClip ) {

			const actionByRoot = actionsByClip[ clipUuid ].actionByRoot,
				action = actionByRoot[ rootUuid ];

			if ( action !== undefined ) {

				this._deactivateAction( action );
				this._removeInactiveAction( action );

			}

		}

		const bindingsByRoot = this._bindingsByRootAndName,
			bindingByName = bindingsByRoot[ rootUuid ];

		if ( bindingByName !== undefined ) {

			for ( const trackName in bindingByName ) {

				const binding = bindingByName[ trackName ];
				binding.restoreOriginalState();
				this._removeInactiveBinding( binding );

			}

		}

	}
```
</details>

##### `uncacheAction(clip: string | AnimationClip, optionalRoot: Object3D): void`

<details><summary>Code</summary>

```ts
uncacheAction( clip, optionalRoot ) {

		const action = this.existingAction( clip, optionalRoot );

		if ( action !== null ) {

			this._deactivateAction( action );
			this._removeInactiveAction( action );

		}

	}
```
</details>


---