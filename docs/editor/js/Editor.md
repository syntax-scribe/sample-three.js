[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Editor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 75 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 22 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Editor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Config` | `./Config.js` |
| `Loader` | `./Loader.js` |
| `_History` | `./History.js` |
| `Strings` | `./Strings.js` |
| `_Storage` | `./Storage.js` |
| `Selector` | `./Selector.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_DEFAULT_CAMERA` | `any` | let/var | `new THREE.PerspectiveCamera( 50, 1, 0.01, 1000 )` | ✗ |
| `Signal` | `any` | let/var | `signals.Signal` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `materialsRefCounter` | `Map<any, any>` | let/var | `this.materialsRefCounter` | ✗ |
| `materialsRefCounter` | `Map<any, any>` | let/var | `this.materialsRefCounter` | ✗ |
| `material` | `any` | let/var | `*not shown*` | ✗ |
| `geometry` | `any` | let/var | `new THREE.SphereGeometry( 2, 4, 2 )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshBasicMaterial( { color: 0xff0000, visible: false } )` | ✗ |
| `picker` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `helper` | `any` | let/var | `this.helpers[ object.id ]` | ✗ |
| `material` | `any` | let/var | `object.material` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `objects` | `any` | let/var | `this.scene.children` | ✗ |
| `loader` | `any` | let/var | `new THREE.ObjectLoader()` | ✗ |
| `camera` | `any` | let/var | `await loader.parseAsync( json.camera )` | ✗ |
| `existingUuid` | `any` | let/var | `this.camera.uuid` | ✗ |
| `incomingUuid` | `any` | let/var | `camera.uuid` | ✗ |
| `scene` | `any` | let/var | `this.scene` | ✗ |
| `scripts` | `{}` | let/var | `this.scripts` | ✗ |
| `script` | `any` | let/var | `scripts[ key ]` | ✗ |
| `environment` | `any` | let/var | `null` | ✗ |


---

## Functions

### `Editor(): void`

**Returns:** `void`

**Calls:**

- `_DEFAULT_CAMERA.clone`
- `this.sceneHelpers.add`
- `this.addCamera`

**Internal Comments:**
```
// script (x2)
// player (x2)
// xr (x2)
// notifications (x2)
```

<details><summary>Code</summary>

```typescript
function Editor() {

	const Signal = signals.Signal; // eslint-disable-line no-undef

	this.signals = {

		// script

		editScript: new Signal(),

		// player

		startPlayer: new Signal(),
		stopPlayer: new Signal(),

		// xr

		enterXR: new Signal(),
		offerXR: new Signal(),
		leaveXR: new Signal(),

		// notifications

		editorCleared: new Signal(),

		savingStarted: new Signal(),
		savingFinished: new Signal(),

		transformModeChanged: new Signal(),
		snapChanged: new Signal(),
		spaceChanged: new Signal(),
		rendererCreated: new Signal(),
		rendererUpdated: new Signal(),
		rendererDetectKTX2Support: new Signal(),

		sceneBackgroundChanged: new Signal(),
		sceneEnvironmentChanged: new Signal(),
		sceneFogChanged: new Signal(),
		sceneFogSettingsChanged: new Signal(),
		sceneGraphChanged: new Signal(),
		sceneRendered: new Signal(),

		cameraChanged: new Signal(),
		cameraResetted: new Signal(),

		geometryChanged: new Signal(),

		objectSelected: new Signal(),
		objectFocused: new Signal(),

		objectAdded: new Signal(),
		objectChanged: new Signal(),
		objectRemoved: new Signal(),

		cameraAdded: new Signal(),
		cameraRemoved: new Signal(),

		helperAdded: new Signal(),
		helperRemoved: new Signal(),

		materialAdded: new Signal(),
		materialChanged: new Signal(),
		materialRemoved: new Signal(),

		scriptAdded: new Signal(),
		scriptChanged: new Signal(),
		scriptRemoved: new Signal(),

		windowResize: new Signal(),

		showHelpersChanged: new Signal(),
		refreshSidebarObject3D: new Signal(),
		refreshSidebarEnvironment: new Signal(),
		historyChanged: new Signal(),

		viewportCameraChanged: new Signal(),
		viewportShadingChanged: new Signal(),

		intersectionsDetected: new Signal(),

		pathTracerUpdated: new Signal(),

	};

	this.config = new Config();
	this.history = new _History( this );
	this.selector = new Selector( this );
	this.storage = new _Storage();
	this.strings = new Strings( this.config );

	this.loader = new Loader( this );

	this.camera = _DEFAULT_CAMERA.clone();

	this.scene = new THREE.Scene();
	this.scene.name = 'Scene';

	this.sceneHelpers = new THREE.Scene();
	this.sceneHelpers.add( new THREE.HemisphereLight( 0xffffff, 0x888888, 2 ) );

	this.object = {};
	this.geometries = {};
	this.materials = {};
	this.textures = {};
	this.scripts = {};

	this.materialsRefCounter = new Map(); // tracks how often is a material used by a 3D object

	this.mixer = new THREE.AnimationMixer( this.scene );

	this.selected = null;
	this.helpers = {};

	this.cameras = {};

	this.viewportCamera = this.camera;
	this.viewportShading = 'default';

	this.addCamera( this.camera );

}
```
</details>

### `setScene(scene: any): void`

**Parameters:**

- **`scene`** `any`

**Returns:** `void`

**Calls:**

- `JSON.parse`
- `JSON.stringify`
- `this.addObject`
- `this.signals.sceneGraphChanged.dispatch`

**Internal Comments:**
```
// avoid render per object (x6)
```

<details><summary>Code</summary>

```typescript
function ( scene ) {

		this.scene.uuid = scene.uuid;
		this.scene.name = scene.name;

		this.scene.background = scene.background;
		this.scene.environment = scene.environment;
		this.scene.fog = scene.fog;
		this.scene.backgroundBlurriness = scene.backgroundBlurriness;
		this.scene.backgroundIntensity = scene.backgroundIntensity;

		this.scene.userData = JSON.parse( JSON.stringify( scene.userData ) );

		// avoid render per object

		this.signals.sceneGraphChanged.active = false;

		while ( scene.children.length > 0 ) {

			this.addObject( scene.children[ 0 ] );

		}

		this.signals.sceneGraphChanged.active = true;
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `addObject(object: any, parent: any, index: any): void`

**Parameters:**

- **`object`** `any`
- **`parent`** `any`
- **`index`** `any`

**Returns:** `void`

**Calls:**

- `object.traverse`
- `scope.addGeometry`
- `scope.addMaterial`
- `scope.addCamera`
- `scope.addHelper`
- `this.scene.add`
- `parent.children.splice`
- `this.signals.objectAdded.dispatch`
- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( object, parent, index ) {

		var scope = this;

		object.traverse( function ( child ) {

			if ( child.geometry !== undefined ) scope.addGeometry( child.geometry );
			if ( child.material !== undefined ) scope.addMaterial( child.material );

			scope.addCamera( child );
			scope.addHelper( child );

		} );

		if ( parent === undefined ) {

			this.scene.add( object );

		} else {

			parent.children.splice( index, 0, object );
			object.parent = parent;

		}

		this.signals.objectAdded.dispatch( object );
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `nameObject(object: any, name: any): void`

**Parameters:**

- **`object`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( object, name ) {

		object.name = name;
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `removeObject(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `object.traverse`
- `scope.removeCamera`
- `scope.removeHelper`
- `scope.removeMaterial`
- `object.parent.remove`
- `this.signals.objectRemoved.dispatch`
- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( object ) {

		if ( object.parent === null ) return; // avoid deleting the camera or scene

		var scope = this;

		object.traverse( function ( child ) {

			scope.removeCamera( child );
			scope.removeHelper( child );

			if ( child.material !== undefined ) scope.removeMaterial( child.material );

		} );

		object.parent.remove( object );

		this.signals.objectRemoved.dispatch( object );
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `addGeometry(geometry: any): void`

**Parameters:**

- **`geometry`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( geometry ) {

		this.geometries[ geometry.uuid ] = geometry;

	}
```
</details>

### `setGeometryName(geometry: any, name: any): void`

**Parameters:**

- **`geometry`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( geometry, name ) {

		geometry.name = name;
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `addMaterial(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `this.addMaterialToRefCounter`
- `this.signals.materialAdded.dispatch`

<details><summary>Code</summary>

```typescript
function ( material ) {

		if ( Array.isArray( material ) ) {

			for ( var i = 0, l = material.length; i < l; i ++ ) {

				this.addMaterialToRefCounter( material[ i ] );

			}

		} else {

			this.addMaterialToRefCounter( material );

		}

		this.signals.materialAdded.dispatch();

	}
```
</details>

### `addMaterialToRefCounter(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `materialsRefCounter.get`
- `materialsRefCounter.set`

<details><summary>Code</summary>

```typescript
function ( material ) {

		var materialsRefCounter = this.materialsRefCounter;

		var count = materialsRefCounter.get( material );

		if ( count === undefined ) {

			materialsRefCounter.set( material, 1 );
			this.materials[ material.uuid ] = material;

		} else {

			count ++;
			materialsRefCounter.set( material, count );

		}

	}
```
</details>

### `removeMaterial(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `this.removeMaterialFromRefCounter`
- `this.signals.materialRemoved.dispatch`

<details><summary>Code</summary>

```typescript
function ( material ) {

		if ( Array.isArray( material ) ) {

			for ( var i = 0, l = material.length; i < l; i ++ ) {

				this.removeMaterialFromRefCounter( material[ i ] );

			}

		} else {

			this.removeMaterialFromRefCounter( material );

		}

		this.signals.materialRemoved.dispatch();

	}
```
</details>

### `removeMaterialFromRefCounter(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `materialsRefCounter.get`
- `materialsRefCounter.delete`
- `materialsRefCounter.set`

<details><summary>Code</summary>

```typescript
function ( material ) {

		var materialsRefCounter = this.materialsRefCounter;

		var count = materialsRefCounter.get( material );
		count --;

		if ( count === 0 ) {

			materialsRefCounter.delete( material );
			delete this.materials[ material.uuid ];

		} else {

			materialsRefCounter.set( material, count );

		}

	}
```
</details>

### `getMaterialById(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `Object.values`

<details><summary>Code</summary>

```typescript
function ( id ) {

		var material;
		var materials = Object.values( this.materials );

		for ( var i = 0; i < materials.length; i ++ ) {

			if ( materials[ i ].id === id ) {

				material = materials[ i ];
				break;

			}

		}

		return material;

	}
```
</details>

### `setMaterialName(material: any, name: any): void`

**Parameters:**

- **`material`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( material, name ) {

		material.name = name;
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `addTexture(texture: any): void`

**Parameters:**

- **`texture`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( texture ) {

		this.textures[ texture.uuid ] = texture;

	}
```
</details>

### `addCamera(camera: any): void`

**Parameters:**

- **`camera`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.cameraAdded.dispatch`

<details><summary>Code</summary>

```typescript
function ( camera ) {

		if ( camera.isCamera ) {

			this.cameras[ camera.uuid ] = camera;

			this.signals.cameraAdded.dispatch( camera );

		}

	}
```
</details>

### `removeCamera(camera: any): void`

**Parameters:**

- **`camera`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.cameraRemoved.dispatch`

<details><summary>Code</summary>

```typescript
function ( camera ) {

		if ( this.cameras[ camera.uuid ] !== undefined ) {

			delete this.cameras[ camera.uuid ];

			this.signals.cameraRemoved.dispatch( camera );

		}

	}
```
</details>

### `removeHelper(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `helper.parent.remove`
- `helper.dispose`
- `this.signals.helperRemoved.dispatch`

<details><summary>Code</summary>

```typescript
function ( object ) {

		if ( this.helpers[ object.id ] !== undefined ) {

			var helper = this.helpers[ object.id ];
			helper.parent.remove( helper );
			helper.dispose();

			delete this.helpers[ object.id ];

			this.signals.helperRemoved.dispatch( helper );

		}

	}
```
</details>

### `addScript(object: any, script: any): void`

**Parameters:**

- **`object`** `any`
- **`script`** `any`

**Returns:** `void`

**Calls:**

- `this.scripts[ object.uuid ].push`
- `this.signals.scriptAdded.dispatch`

<details><summary>Code</summary>

```typescript
function ( object, script ) {

		if ( this.scripts[ object.uuid ] === undefined ) {

			this.scripts[ object.uuid ] = [];

		}

		this.scripts[ object.uuid ].push( script );

		this.signals.scriptAdded.dispatch( script );

	}
```
</details>

### `removeScript(object: any, script: any): void`

**Parameters:**

- **`object`** `any`
- **`script`** `any`

**Returns:** `void`

**Calls:**

- `this.scripts[ object.uuid ].indexOf`
- `this.scripts[ object.uuid ].splice`
- `this.signals.scriptRemoved.dispatch`

<details><summary>Code</summary>

```typescript
function ( object, script ) {

		if ( this.scripts[ object.uuid ] === undefined ) return;

		var index = this.scripts[ object.uuid ].indexOf( script );

		if ( index !== - 1 ) {

			this.scripts[ object.uuid ].splice( index, 1 );

		}

		this.signals.scriptRemoved.dispatch( script );

	}
```
</details>

### `getObjectMaterial(object: any, slot: any): any`

**Parameters:**

- **`object`** `any`
- **`slot`** `any`

**Returns:** `any`

**Calls:**

- `Array.isArray`

<details><summary>Code</summary>

```typescript
function ( object, slot ) {

		var material = object.material;

		if ( Array.isArray( material ) && slot !== undefined ) {

			material = material[ slot ];

		}

		return material;

	}
```
</details>

### `setObjectMaterial(object: any, slot: any, newMaterial: any): void`

**Parameters:**

- **`object`** `any`
- **`slot`** `any`
- **`newMaterial`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`

<details><summary>Code</summary>

```typescript
function ( object, slot, newMaterial ) {

		if ( Array.isArray( object.material ) && slot !== undefined ) {

			object.material[ slot ] = newMaterial;

		} else {

			object.material = newMaterial;

		}

	}
```
</details>

### `setViewportCamera(uuid: any): void`

**Parameters:**

- **`uuid`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.viewportCameraChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( uuid ) {

		this.viewportCamera = this.cameras[ uuid ];
		this.signals.viewportCameraChanged.dispatch();

	}
```
</details>

### `setViewportShading(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.viewportShadingChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( value ) {

		this.viewportShading = value;
		this.signals.viewportShadingChanged.dispatch();

	}
```
</details>

### `select(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `this.selector.select`

<details><summary>Code</summary>

```typescript
function ( object ) {

		this.selector.select( object );

	}
```
</details>

### `selectById(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `this.select`
- `this.scene.getObjectById`

<details><summary>Code</summary>

```typescript
function ( id ) {

		if ( id === this.camera.id ) {

			this.select( this.camera );
			return;

		}

		this.select( this.scene.getObjectById( id ) );

	}
```
</details>

### `selectByUuid(uuid: any): void`

**Parameters:**

- **`uuid`** `any`

**Returns:** `void`

**Calls:**

- `this.scene.traverse`
- `scope.select`

<details><summary>Code</summary>

```typescript
function ( uuid ) {

		var scope = this;

		this.scene.traverse( function ( child ) {

			if ( child.uuid === uuid ) {

				scope.select( child );

			}

		} );

	}
```
</details>

### `deselect(): void`

**Returns:** `void`

**Calls:**

- `this.selector.deselect`

<details><summary>Code</summary>

```typescript
function () {

		this.selector.deselect();

	}
```
</details>

### `focus(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.objectFocused.dispatch`

<details><summary>Code</summary>

```typescript
function ( object ) {

		if ( object !== undefined ) {

			this.signals.objectFocused.dispatch( object );

		}

	}
```
</details>

### `focusById(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `this.focus`
- `this.scene.getObjectById`

<details><summary>Code</summary>

```typescript
function ( id ) {

		this.focus( this.scene.getObjectById( id ) );

	}
```
</details>

### `clear(): void`

**Returns:** `void`

**Calls:**

- `this.history.clear`
- `this.storage.clear`
- `this.camera.copy`
- `this.signals.cameraResetted.dispatch`
- `this.removeObject`
- `this.materialsRefCounter.clear`
- `this.mixer.stopAllAction`
- `this.deselect`
- `this.signals.editorCleared.dispatch`

<details><summary>Code</summary>

```typescript
function () {

		this.history.clear();
		this.storage.clear();

		this.camera.copy( _DEFAULT_CAMERA );
		this.signals.cameraResetted.dispatch();

		this.scene.name = 'Scene';
		this.scene.userData = {};
		this.scene.background = null;
		this.scene.environment = null;
		this.scene.fog = null;

		var objects = this.scene.children;

		this.signals.sceneGraphChanged.active = false;

		while ( objects.length > 0 ) {

			this.removeObject( objects[ 0 ] );

		}

		this.signals.sceneGraphChanged.active = true;

		this.geometries = {};
		this.materials = {};
		this.textures = {};
		this.scripts = {};

		this.materialsRefCounter.clear();

		this.animations = {};
		this.mixer.stopAllAction();

		this.deselect();

		this.signals.editorCleared.dispatch();

	}
```
</details>

### `fromJSON(json: any): Promise<void>`

**Parameters:**

- **`json`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `loader.parseAsync`
- `this.camera.copy`
- `this.signals.cameraResetted.dispatch`
- `this.history.fromJSON`
- `this.setScene`
- `this.signals.sceneEnvironmentChanged.dispatch`
- `this.signals.refreshSidebarEnvironment.dispatch`

**Internal Comments:**
```
// copy all properties, including uuid (x5)
```

<details><summary>Code</summary>

```typescript
async function ( json ) {

		var loader = new THREE.ObjectLoader();
		var camera = await loader.parseAsync( json.camera );

		const existingUuid = this.camera.uuid;
		const incomingUuid = camera.uuid;

		// copy all properties, including uuid
		this.camera.copy( camera );
		this.camera.uuid = incomingUuid;

		delete this.cameras[ existingUuid ]; // remove old entry [existingUuid, this.camera]
		this.cameras[ incomingUuid ] = this.camera; // add new entry [incomingUuid, this.camera]

		this.signals.cameraResetted.dispatch();

		this.history.fromJSON( json.history );
		this.scripts = json.scripts;

		this.setScene( await loader.parseAsync( json.scene ) );

		if ( json.environment === 'Room' ||
			 json.environment === 'ModelViewer' /* DEPRECATED */ ) {

			this.signals.sceneEnvironmentChanged.dispatch( json.environment );
			this.signals.refreshSidebarEnvironment.dispatch();

		}

	}
```
</details>

### `toJSON(): { metadata: {}; project: { shadows: any; shadowType: any; toneMapping: any; toneMappingExposure: any; }; camera: any; scene: any; scripts: {}; history: { undos: any[]; redos: any[]; }; environment: string; }`

**Returns:** `{ metadata: {}; project: { shadows: any; shadowType: any; toneMapping: any; toneMappingExposure: any; }; camera: any; scene: any; scripts: {}; history: { undos: any[]; redos: any[]; }; environment: string; }`

**Calls:**

- `scene.getObjectByProperty`
- `this.config.getKey`
- `this.viewportCamera.toJSON`
- `this.scene.toJSON`
- `this.history.toJSON`

**Internal Comments:**
```
// scripts clean up (x2)
// honor neutral environment (x2)
//
```

<details><summary>Code</summary>

```typescript
function () {

		// scripts clean up

		var scene = this.scene;
		var scripts = this.scripts;

		for ( var key in scripts ) {

			var script = scripts[ key ];

			if ( script.length === 0 || scene.getObjectByProperty( 'uuid', key ) === undefined ) {

				delete scripts[ key ];

			}

		}

		// honor neutral environment

		let environment = null;

		if ( this.scene.environment !== null && this.scene.environment.isRenderTargetTexture === true ) {

			environment = 'Room';

		}

		//

		return {

			metadata: {},
			project: {
				shadows: this.config.getKey( 'project/renderer/shadows' ),
				shadowType: this.config.getKey( 'project/renderer/shadowType' ),
				toneMapping: this.config.getKey( 'project/renderer/toneMapping' ),
				toneMappingExposure: this.config.getKey( 'project/renderer/toneMappingExposure' )
			},
			camera: this.viewportCamera.toJSON(),
			scene: this.scene.toJSON(),
			scripts: this.scripts,
			history: this.history.toJSON(),
			environment: environment

		};

	}
```
</details>

### `objectByUuid(uuid: any): any`

**Parameters:**

- **`uuid`** `any`

**Returns:** `any`

**Calls:**

- `this.scene.getObjectByProperty`

<details><summary>Code</summary>

```typescript
function ( uuid ) {

		return this.scene.getObjectByProperty( 'uuid', uuid, true );

	}
```
</details>

### `execute(cmd: any, optionalName: any): void`

**Parameters:**

- **`cmd`** `any`
- **`optionalName`** `any`

**Returns:** `void`

**Calls:**

- `this.history.execute`

<details><summary>Code</summary>

```typescript
function ( cmd, optionalName ) {

		this.history.execute( cmd, optionalName );

	}
```
</details>

### `undo(): void`

**Returns:** `void`

**Calls:**

- `this.history.undo`

<details><summary>Code</summary>

```typescript
function () {

		this.history.undo();

	}
```
</details>

### `redo(): void`

**Returns:** `void`

**Calls:**

- `this.history.redo`

<details><summary>Code</summary>

```typescript
function () {

		this.history.redo();

	}
```
</details>

### `setScene(scene: any): void`

**Parameters:**

- **`scene`** `any`

**Returns:** `void`

**Calls:**

- `JSON.parse`
- `JSON.stringify`
- `this.addObject`
- `this.signals.sceneGraphChanged.dispatch`

**Internal Comments:**
```
// avoid render per object (x6)
```

<details><summary>Code</summary>

```typescript
function ( scene ) {

		this.scene.uuid = scene.uuid;
		this.scene.name = scene.name;

		this.scene.background = scene.background;
		this.scene.environment = scene.environment;
		this.scene.fog = scene.fog;
		this.scene.backgroundBlurriness = scene.backgroundBlurriness;
		this.scene.backgroundIntensity = scene.backgroundIntensity;

		this.scene.userData = JSON.parse( JSON.stringify( scene.userData ) );

		// avoid render per object

		this.signals.sceneGraphChanged.active = false;

		while ( scene.children.length > 0 ) {

			this.addObject( scene.children[ 0 ] );

		}

		this.signals.sceneGraphChanged.active = true;
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `addObject(object: any, parent: any, index: any): void`

**Parameters:**

- **`object`** `any`
- **`parent`** `any`
- **`index`** `any`

**Returns:** `void`

**Calls:**

- `object.traverse`
- `scope.addGeometry`
- `scope.addMaterial`
- `scope.addCamera`
- `scope.addHelper`
- `this.scene.add`
- `parent.children.splice`
- `this.signals.objectAdded.dispatch`
- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( object, parent, index ) {

		var scope = this;

		object.traverse( function ( child ) {

			if ( child.geometry !== undefined ) scope.addGeometry( child.geometry );
			if ( child.material !== undefined ) scope.addMaterial( child.material );

			scope.addCamera( child );
			scope.addHelper( child );

		} );

		if ( parent === undefined ) {

			this.scene.add( object );

		} else {

			parent.children.splice( index, 0, object );
			object.parent = parent;

		}

		this.signals.objectAdded.dispatch( object );
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `nameObject(object: any, name: any): void`

**Parameters:**

- **`object`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( object, name ) {

		object.name = name;
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `removeObject(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `object.traverse`
- `scope.removeCamera`
- `scope.removeHelper`
- `scope.removeMaterial`
- `object.parent.remove`
- `this.signals.objectRemoved.dispatch`
- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( object ) {

		if ( object.parent === null ) return; // avoid deleting the camera or scene

		var scope = this;

		object.traverse( function ( child ) {

			scope.removeCamera( child );
			scope.removeHelper( child );

			if ( child.material !== undefined ) scope.removeMaterial( child.material );

		} );

		object.parent.remove( object );

		this.signals.objectRemoved.dispatch( object );
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `addGeometry(geometry: any): void`

**Parameters:**

- **`geometry`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( geometry ) {

		this.geometries[ geometry.uuid ] = geometry;

	}
```
</details>

### `setGeometryName(geometry: any, name: any): void`

**Parameters:**

- **`geometry`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( geometry, name ) {

		geometry.name = name;
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `addMaterial(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `this.addMaterialToRefCounter`
- `this.signals.materialAdded.dispatch`

<details><summary>Code</summary>

```typescript
function ( material ) {

		if ( Array.isArray( material ) ) {

			for ( var i = 0, l = material.length; i < l; i ++ ) {

				this.addMaterialToRefCounter( material[ i ] );

			}

		} else {

			this.addMaterialToRefCounter( material );

		}

		this.signals.materialAdded.dispatch();

	}
```
</details>

### `addMaterialToRefCounter(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `materialsRefCounter.get`
- `materialsRefCounter.set`

<details><summary>Code</summary>

```typescript
function ( material ) {

		var materialsRefCounter = this.materialsRefCounter;

		var count = materialsRefCounter.get( material );

		if ( count === undefined ) {

			materialsRefCounter.set( material, 1 );
			this.materials[ material.uuid ] = material;

		} else {

			count ++;
			materialsRefCounter.set( material, count );

		}

	}
```
</details>

### `removeMaterial(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `this.removeMaterialFromRefCounter`
- `this.signals.materialRemoved.dispatch`

<details><summary>Code</summary>

```typescript
function ( material ) {

		if ( Array.isArray( material ) ) {

			for ( var i = 0, l = material.length; i < l; i ++ ) {

				this.removeMaterialFromRefCounter( material[ i ] );

			}

		} else {

			this.removeMaterialFromRefCounter( material );

		}

		this.signals.materialRemoved.dispatch();

	}
```
</details>

### `removeMaterialFromRefCounter(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `materialsRefCounter.get`
- `materialsRefCounter.delete`
- `materialsRefCounter.set`

<details><summary>Code</summary>

```typescript
function ( material ) {

		var materialsRefCounter = this.materialsRefCounter;

		var count = materialsRefCounter.get( material );
		count --;

		if ( count === 0 ) {

			materialsRefCounter.delete( material );
			delete this.materials[ material.uuid ];

		} else {

			materialsRefCounter.set( material, count );

		}

	}
```
</details>

### `getMaterialById(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `Object.values`

<details><summary>Code</summary>

```typescript
function ( id ) {

		var material;
		var materials = Object.values( this.materials );

		for ( var i = 0; i < materials.length; i ++ ) {

			if ( materials[ i ].id === id ) {

				material = materials[ i ];
				break;

			}

		}

		return material;

	}
```
</details>

### `setMaterialName(material: any, name: any): void`

**Parameters:**

- **`material`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( material, name ) {

		material.name = name;
		this.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `addTexture(texture: any): void`

**Parameters:**

- **`texture`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( texture ) {

		this.textures[ texture.uuid ] = texture;

	}
```
</details>

### `addCamera(camera: any): void`

**Parameters:**

- **`camera`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.cameraAdded.dispatch`

<details><summary>Code</summary>

```typescript
function ( camera ) {

		if ( camera.isCamera ) {

			this.cameras[ camera.uuid ] = camera;

			this.signals.cameraAdded.dispatch( camera );

		}

	}
```
</details>

### `removeCamera(camera: any): void`

**Parameters:**

- **`camera`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.cameraRemoved.dispatch`

<details><summary>Code</summary>

```typescript
function ( camera ) {

		if ( this.cameras[ camera.uuid ] !== undefined ) {

			delete this.cameras[ camera.uuid ];

			this.signals.cameraRemoved.dispatch( camera );

		}

	}
```
</details>

### `removeHelper(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `helper.parent.remove`
- `helper.dispose`
- `this.signals.helperRemoved.dispatch`

<details><summary>Code</summary>

```typescript
function ( object ) {

		if ( this.helpers[ object.id ] !== undefined ) {

			var helper = this.helpers[ object.id ];
			helper.parent.remove( helper );
			helper.dispose();

			delete this.helpers[ object.id ];

			this.signals.helperRemoved.dispatch( helper );

		}

	}
```
</details>

### `addScript(object: any, script: any): void`

**Parameters:**

- **`object`** `any`
- **`script`** `any`

**Returns:** `void`

**Calls:**

- `this.scripts[ object.uuid ].push`
- `this.signals.scriptAdded.dispatch`

<details><summary>Code</summary>

```typescript
function ( object, script ) {

		if ( this.scripts[ object.uuid ] === undefined ) {

			this.scripts[ object.uuid ] = [];

		}

		this.scripts[ object.uuid ].push( script );

		this.signals.scriptAdded.dispatch( script );

	}
```
</details>

### `removeScript(object: any, script: any): void`

**Parameters:**

- **`object`** `any`
- **`script`** `any`

**Returns:** `void`

**Calls:**

- `this.scripts[ object.uuid ].indexOf`
- `this.scripts[ object.uuid ].splice`
- `this.signals.scriptRemoved.dispatch`

<details><summary>Code</summary>

```typescript
function ( object, script ) {

		if ( this.scripts[ object.uuid ] === undefined ) return;

		var index = this.scripts[ object.uuid ].indexOf( script );

		if ( index !== - 1 ) {

			this.scripts[ object.uuid ].splice( index, 1 );

		}

		this.signals.scriptRemoved.dispatch( script );

	}
```
</details>

### `getObjectMaterial(object: any, slot: any): any`

**Parameters:**

- **`object`** `any`
- **`slot`** `any`

**Returns:** `any`

**Calls:**

- `Array.isArray`

<details><summary>Code</summary>

```typescript
function ( object, slot ) {

		var material = object.material;

		if ( Array.isArray( material ) && slot !== undefined ) {

			material = material[ slot ];

		}

		return material;

	}
```
</details>

### `setObjectMaterial(object: any, slot: any, newMaterial: any): void`

**Parameters:**

- **`object`** `any`
- **`slot`** `any`
- **`newMaterial`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`

<details><summary>Code</summary>

```typescript
function ( object, slot, newMaterial ) {

		if ( Array.isArray( object.material ) && slot !== undefined ) {

			object.material[ slot ] = newMaterial;

		} else {

			object.material = newMaterial;

		}

	}
```
</details>

### `setViewportCamera(uuid: any): void`

**Parameters:**

- **`uuid`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.viewportCameraChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( uuid ) {

		this.viewportCamera = this.cameras[ uuid ];
		this.signals.viewportCameraChanged.dispatch();

	}
```
</details>

### `setViewportShading(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.viewportShadingChanged.dispatch`

<details><summary>Code</summary>

```typescript
function ( value ) {

		this.viewportShading = value;
		this.signals.viewportShadingChanged.dispatch();

	}
```
</details>

### `select(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `this.selector.select`

<details><summary>Code</summary>

```typescript
function ( object ) {

		this.selector.select( object );

	}
```
</details>

### `selectById(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `this.select`
- `this.scene.getObjectById`

<details><summary>Code</summary>

```typescript
function ( id ) {

		if ( id === this.camera.id ) {

			this.select( this.camera );
			return;

		}

		this.select( this.scene.getObjectById( id ) );

	}
```
</details>

### `selectByUuid(uuid: any): void`

**Parameters:**

- **`uuid`** `any`

**Returns:** `void`

**Calls:**

- `this.scene.traverse`
- `scope.select`

<details><summary>Code</summary>

```typescript
function ( uuid ) {

		var scope = this;

		this.scene.traverse( function ( child ) {

			if ( child.uuid === uuid ) {

				scope.select( child );

			}

		} );

	}
```
</details>

### `deselect(): void`

**Returns:** `void`

**Calls:**

- `this.selector.deselect`

<details><summary>Code</summary>

```typescript
function () {

		this.selector.deselect();

	}
```
</details>

### `focus(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `this.signals.objectFocused.dispatch`

<details><summary>Code</summary>

```typescript
function ( object ) {

		if ( object !== undefined ) {

			this.signals.objectFocused.dispatch( object );

		}

	}
```
</details>

### `focusById(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `this.focus`
- `this.scene.getObjectById`

<details><summary>Code</summary>

```typescript
function ( id ) {

		this.focus( this.scene.getObjectById( id ) );

	}
```
</details>

### `clear(): void`

**Returns:** `void`

**Calls:**

- `this.history.clear`
- `this.storage.clear`
- `this.camera.copy`
- `this.signals.cameraResetted.dispatch`
- `this.removeObject`
- `this.materialsRefCounter.clear`
- `this.mixer.stopAllAction`
- `this.deselect`
- `this.signals.editorCleared.dispatch`

<details><summary>Code</summary>

```typescript
function () {

		this.history.clear();
		this.storage.clear();

		this.camera.copy( _DEFAULT_CAMERA );
		this.signals.cameraResetted.dispatch();

		this.scene.name = 'Scene';
		this.scene.userData = {};
		this.scene.background = null;
		this.scene.environment = null;
		this.scene.fog = null;

		var objects = this.scene.children;

		this.signals.sceneGraphChanged.active = false;

		while ( objects.length > 0 ) {

			this.removeObject( objects[ 0 ] );

		}

		this.signals.sceneGraphChanged.active = true;

		this.geometries = {};
		this.materials = {};
		this.textures = {};
		this.scripts = {};

		this.materialsRefCounter.clear();

		this.animations = {};
		this.mixer.stopAllAction();

		this.deselect();

		this.signals.editorCleared.dispatch();

	}
```
</details>

### `fromJSON(json: any): Promise<void>`

**Parameters:**

- **`json`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `loader.parseAsync`
- `this.camera.copy`
- `this.signals.cameraResetted.dispatch`
- `this.history.fromJSON`
- `this.setScene`
- `this.signals.sceneEnvironmentChanged.dispatch`
- `this.signals.refreshSidebarEnvironment.dispatch`

**Internal Comments:**
```
// copy all properties, including uuid (x5)
```

<details><summary>Code</summary>

```typescript
async function ( json ) {

		var loader = new THREE.ObjectLoader();
		var camera = await loader.parseAsync( json.camera );

		const existingUuid = this.camera.uuid;
		const incomingUuid = camera.uuid;

		// copy all properties, including uuid
		this.camera.copy( camera );
		this.camera.uuid = incomingUuid;

		delete this.cameras[ existingUuid ]; // remove old entry [existingUuid, this.camera]
		this.cameras[ incomingUuid ] = this.camera; // add new entry [incomingUuid, this.camera]

		this.signals.cameraResetted.dispatch();

		this.history.fromJSON( json.history );
		this.scripts = json.scripts;

		this.setScene( await loader.parseAsync( json.scene ) );

		if ( json.environment === 'Room' ||
			 json.environment === 'ModelViewer' /* DEPRECATED */ ) {

			this.signals.sceneEnvironmentChanged.dispatch( json.environment );
			this.signals.refreshSidebarEnvironment.dispatch();

		}

	}
```
</details>

### `toJSON(): { metadata: {}; project: { shadows: any; shadowType: any; toneMapping: any; toneMappingExposure: any; }; camera: any; scene: any; scripts: {}; history: { undos: any[]; redos: any[]; }; environment: string; }`

**Returns:** `{ metadata: {}; project: { shadows: any; shadowType: any; toneMapping: any; toneMappingExposure: any; }; camera: any; scene: any; scripts: {}; history: { undos: any[]; redos: any[]; }; environment: string; }`

**Calls:**

- `scene.getObjectByProperty`
- `this.config.getKey`
- `this.viewportCamera.toJSON`
- `this.scene.toJSON`
- `this.history.toJSON`

**Internal Comments:**
```
// scripts clean up (x2)
// honor neutral environment (x2)
//
```

<details><summary>Code</summary>

```typescript
function () {

		// scripts clean up

		var scene = this.scene;
		var scripts = this.scripts;

		for ( var key in scripts ) {

			var script = scripts[ key ];

			if ( script.length === 0 || scene.getObjectByProperty( 'uuid', key ) === undefined ) {

				delete scripts[ key ];

			}

		}

		// honor neutral environment

		let environment = null;

		if ( this.scene.environment !== null && this.scene.environment.isRenderTargetTexture === true ) {

			environment = 'Room';

		}

		//

		return {

			metadata: {},
			project: {
				shadows: this.config.getKey( 'project/renderer/shadows' ),
				shadowType: this.config.getKey( 'project/renderer/shadowType' ),
				toneMapping: this.config.getKey( 'project/renderer/toneMapping' ),
				toneMappingExposure: this.config.getKey( 'project/renderer/toneMappingExposure' )
			},
			camera: this.viewportCamera.toJSON(),
			scene: this.scene.toJSON(),
			scripts: this.scripts,
			history: this.history.toJSON(),
			environment: environment

		};

	}
```
</details>

### `objectByUuid(uuid: any): any`

**Parameters:**

- **`uuid`** `any`

**Returns:** `any`

**Calls:**

- `this.scene.getObjectByProperty`

<details><summary>Code</summary>

```typescript
function ( uuid ) {

		return this.scene.getObjectByProperty( 'uuid', uuid, true );

	}
```
</details>

### `execute(cmd: any, optionalName: any): void`

**Parameters:**

- **`cmd`** `any`
- **`optionalName`** `any`

**Returns:** `void`

**Calls:**

- `this.history.execute`

<details><summary>Code</summary>

```typescript
function ( cmd, optionalName ) {

		this.history.execute( cmd, optionalName );

	}
```
</details>

### `undo(): void`

**Returns:** `void`

**Calls:**

- `this.history.undo`

<details><summary>Code</summary>

```typescript
function () {

		this.history.undo();

	}
```
</details>

### `redo(): void`

**Returns:** `void`

**Calls:**

- `this.history.redo`

<details><summary>Code</summary>

```typescript
function () {

		this.history.redo();

	}
```
</details>

### `save(blob: any, filename: any): void`

**Parameters:**

- **`blob`** `any`
- **`filename`** `any`

**Returns:** `void`

**Calls:**

- `URL.revokeObjectURL`
- `URL.createObjectURL`
- `link.dispatchEvent`

<details><summary>Code</summary>

```typescript
function save( blob, filename ) {

	if ( link.href ) {

		URL.revokeObjectURL( link.href );

	}

	link.href = URL.createObjectURL( blob );
	link.download = filename || 'data.json';
	link.dispatchEvent( new MouseEvent( 'click' ) );

}
```
</details>

### `saveArrayBuffer(buffer: any, filename: any): void`

**Parameters:**

- **`buffer`** `any`
- **`filename`** `any`

**Returns:** `void`

**Calls:**

- `save`

<details><summary>Code</summary>

```typescript
function saveArrayBuffer( buffer, filename ) {

	save( new Blob( [ buffer ], { type: 'application/octet-stream' } ), filename );

}
```
</details>

### `saveString(text: any, filename: any): void`

**Parameters:**

- **`text`** `any`
- **`filename`** `any`

**Returns:** `void`

**Calls:**

- `save`

<details><summary>Code</summary>

```typescript
function saveString( text, filename ) {

	save( new Blob( [ text ], { type: 'text/plain' } ), filename );

}
```
</details>

### `formatNumber(number: any): string`

**Parameters:**

- **`number`** `any`

**Returns:** `string`

**Calls:**

- `new Intl.NumberFormat( 'en-us', { useGrouping: true } ).format`

<details><summary>Code</summary>

```typescript
function formatNumber( number ) {

	return new Intl.NumberFormat( 'en-us', { useGrouping: true } ).format( number );

}
```
</details>


---