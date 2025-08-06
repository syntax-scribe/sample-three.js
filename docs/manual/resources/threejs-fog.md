[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-fog.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 36 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/threejs-fog.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GLTFLoader` | `../../examples/jsm/loaders/GLTFLoader.js` |
| `threejsLessonUtils` | `./threejs-lesson-utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `darkColors` | `{ background: string; }` | let/var | `{ background: '#333', }` | ✗ |
| `lightColors` | `{ background: string; }` | let/var | `{ background: '#FFF', }` | ✗ |
| `width` | `4` | let/var | `4` | ✗ |
| `height` | `3` | let/var | `3` | ✗ |
| `depth` | `10` | let/var | `10` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( width, height, depth )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshPhongMaterial( { color: 'hsl(130,50%,50%)' } )` | ✗ |
| `loader` | `GLTFLoader` | let/var | `new GLTFLoader()` | ✗ |
| `settings` | `{ shininess: number; roughness: numbe...` | let/var | `{ shininess: 0, roughness: 1, metalness: 0, }` | ✗ |
| `hackGeometry` | `any` | let/var | `new THREE.CircleGeometry( 0.5, 32 )` | ✗ |
| `box` | `any` | let/var | `new THREE.Box3()` | ✗ |
| `size` | `any` | let/var | `new THREE.Vector3()` | ✗ |
| `center` | `any` | let/var | `new THREE.Vector3()` | ✗ |
| `materials` | `Set<any>` | let/var | `new Set()` | ✗ |
| `material` | `any` | let/var | `node.material` | ✗ |
| `hackMesh` | `any` | let/var | `new THREE.Mesh( hackGeometry, node.material )` | ✗ |
| `color` | `16777215` | let/var | `0xFFFFFF` | ✗ |
| `near` | `1.5` | let/var | `1.5` | ✗ |
| `far` | `5` | let/var | `5` | ✗ |
| `light` | `any` | let/var | `new THREE.PointLight( 0xFFFFFF, 1 )` | ✗ |
| `target` | `number[]` | let/var | `[ 1, 1, 0.7 ]` | ✗ |
| `isDarkMode` | `boolean` | let/var | `darkMatcher.matches` | ✗ |
| `colors` | `{ background: string; }` | let/var | `isDarkMode ? darkColors : lightColors` | ✗ |
| `color` | `16777215` | let/var | `0xFFFFFF` | ✗ |
| `near` | `12` | let/var | `12` | ✗ |
| `far` | `18` | let/var | `18` | ✗ |
| `fog` | `any` | let/var | `new THREE.Fog( color, near, far )` | ✗ |
| `color` | `16777215` | let/var | `0xFFFFFF` | ✗ |
| `density` | `0.1` | let/var | `0.1` | ✗ |
| `fog` | `any` | let/var | `new THREE.FogExp2( color, density )` | ✗ |
| `color` | `"#00F"` | let/var | `'#00F'` | ✗ |
| `near` | `12` | let/var | `12` | ✗ |
| `far` | `18` | let/var | `18` | ✗ |
| `color` | `"#00F"` | let/var | `'#00F'` | ✗ |
| `near` | `12` | let/var | `12` | ✗ |
| `far` | `18` | let/var | `18` | ✗ |


---

## Functions

### `fogExample(scene: any, fog: any, update: any): { obj3D: any; update: any; }`

**Parameters:**

- **`scene`** `any`
- **`fog`** `any`
- **`update`** `any`

**Returns:** `{ obj3D: any; update: any; }`

<details><summary>Code</summary>

```typescript
function fogExample( scene, fog, update ) {

		scene.fog = fog;
		const width = 4;
		const height = 3;
		const depth = 10;
		const geometry = new THREE.BoxGeometry( width, height, depth );
		const material = new THREE.MeshPhongMaterial( { color: 'hsl(130,50%,50%)' } );
		return {
			obj3D: new THREE.Mesh( geometry, material ),
			update,
		};

	}
```
</details>

### `houseScene(props: any, fogInHouse: any): { trackball: boolean; obj3D: any; update: (time: any) => void; }`

**Parameters:**

- **`props`** `any`
- **`fogInHouse`** `any`

**Returns:** `{ trackball: boolean; obj3D: any; update: (time: any) => void; }`

**Calls:**

- `loader.load`
- `gltf.scene.traverse`
- `node.updateWorldMatrix`
- `box.setFromObject`
- `box.getSize`
- `box.getCenter`
- `scene.add`
- `hackMesh.position.copy`
- `hackMesh.scale.set`
- `( Array.isArray( material ) ? material : [ material ] ).forEach`
- `Array.isArray`
- `materials.has`
- `materials.add`
- `Object.entries`
- `material.name.startsWith`
- `camera.position.set`
- `camera.lookAt`
- `light.position.copy`
- `Math.sin`

**Internal Comments:**
```
// hack in the bottom of the trees since I don't have
// the model file
```

<details><summary>Code</summary>

```typescript
function houseScene( props, fogInHouse ) {

		const { scene, camera } = props;
		scene.background = new THREE.Color( '#FFF' );
		camera.far = 200;
		const loader = new GLTFLoader();
		const settings = {
			shininess: 0,
			roughness: 1,
			metalness: 0,
		};
		loader.load( '/manual/examples/resources/models/simple_house_scene/scene.gltf', ( gltf ) => {

			const hackGeometry = new THREE.CircleGeometry( 0.5, 32 );
			const box = new THREE.Box3();
			const size = new THREE.Vector3();
			const center = new THREE.Vector3();
			const materials = new Set();
			gltf.scene.traverse( ( node ) => {

				const material = node.material;
				if ( material ) {

					// hack in the bottom of the trees since I don't have
					// the model file
					if ( node.name === 'mesh_11' || node.name === 'mesh_6' ) {

						node.updateWorldMatrix( true, false );
						box.setFromObject( node );
						box.getSize( size );
						box.getCenter( center );
						const hackMesh = new THREE.Mesh( hackGeometry, node.material );
						scene.add( hackMesh );
						hackMesh.position.copy( center );
						hackMesh.rotation.x = Math.PI * 0.5;
						hackMesh.position.y -= size.y / 2;
						hackMesh.scale.set( size.x, size.z, 1 );

					}

					( Array.isArray( material ) ? material : [ material ] ).forEach( ( material ) => {

						if ( ! materials.has( material ) ) {

							materials.add( material );
							for ( const [ key, value ] of Object.entries( settings ) ) {

								if ( material[ key ] !== undefined ) {

									material[ key ] = value;

								}

							}

							if ( ! fogInHouse && material.name.startsWith( 'fogless' ) ) {

								material.fog = false;

							}

						}

					} );

				}

			} );
			scene.add( gltf.scene );

		} );

		camera.fov = 45;
		camera.position.set( 0.4, 1, 1.7 );
		camera.lookAt( 1, 1, 0.7 );

		const color = 0xFFFFFF;
		const near = 1.5;
		const far = 5;
		scene.fog = new THREE.Fog( color, near, far );

		const light = new THREE.PointLight( 0xFFFFFF, 1 );
		light.position.copy( camera.position );
		light.position.y += 0.2;
		scene.add( light );

		const target = [ 1, 1, 0.7 ];
		return {
			trackball: false,
			obj3D: new THREE.Object3D(),
			update: ( time ) => {

				camera.lookAt( target[ 0 ] + Math.sin( time * .25 ) * .5, target[ 1 ], target[ 2 ] );

			},
		};

	}
```
</details>

### `update(time: any): void`

**Parameters:**

- **`time`** `any`

**Returns:** `void`

**Calls:**

- `camera.lookAt`
- `Math.sin`

<details><summary>Code</summary>

```typescript
( time ) => {

				camera.lookAt( target[ 0 ] + Math.sin( time * .25 ) * .5, target[ 1 ], target[ 2 ] );

			}
```
</details>

### `update(time: any): void`

**Parameters:**

- **`time`** `any`

**Returns:** `void`

**Calls:**

- `camera.lookAt`
- `Math.sin`

<details><summary>Code</summary>

```typescript
( time ) => {

				camera.lookAt( target[ 0 ] + Math.sin( time * .25 ) * .5, target[ 1 ], target[ 2 ] );

			}
```
</details>

### `createLightDarkFogUpdater(fog: any): () => void`

**Parameters:**

- **`fog`** `any`

**Returns:** `() => void`

**Calls:**

- `fog.color.set`

<details><summary>Code</summary>

```typescript
function createLightDarkFogUpdater( fog ) {

		return function () {

			const isDarkMode = darkMatcher.matches;
			const colors = isDarkMode ? darkColors : lightColors;
			fog.color.set( colors.background );

		};

	}
```
</details>


---