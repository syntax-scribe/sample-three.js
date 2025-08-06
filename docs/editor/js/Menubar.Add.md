[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Menubar.Add.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 62 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Menubar.Add.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `AddObjectCommand` | `./commands/AddObjectCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `title` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `options` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `option` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Group()` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( 1, 1, 1, 1, 1, 1 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.CapsuleGeometry( 1, 1, 4, 8, 1 )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshStandardMaterial()` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.CircleGeometry( 1, 32, 0, Math.PI * 2 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.CylinderGeometry( 1, 1, 1, 32, 1, false, 0, Math.PI * 2 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.DodecahedronGeometry( 1, 0 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.IcosahedronGeometry( 1, 0 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.LatheGeometry()` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial( { side: THREE.Doubl...` | ✗ |
| `geometry` | `any` | let/var | `new THREE.OctahedronGeometry( 1, 0 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.PlaneGeometry( 1, 1, 1, 1 )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshStandardMaterial()` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.RingGeometry( 0.5, 1, 32, 1, 0, Math.PI * 2 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.SphereGeometry( 1, 32, 16, 0, Math.PI * 2, 0, Math.PI )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `sprite` | `any` | let/var | `new THREE.Sprite( new THREE.SpriteMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.TetrahedronGeometry( 1, 0 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.TorusGeometry( 1, 0.4, 12, 48, Math.PI * 2 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.TorusKnotGeometry( 1, 0.4, 64, 8, 2, 3 )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `path` | `any` | let/var | `new THREE.CatmullRomCurve3( [ new THREE.Vector3( 2, 2, - 2 ), new THREE.Vecto...` | ✗ |
| `geometry` | `any` | let/var | `new THREE.TubeGeometry( path, 64, 1, 8, false )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() )` | ✗ |
| `color` | `2236962` | let/var | `0x222222` | ✗ |
| `light` | `any` | let/var | `new THREE.AmbientLight( color )` | ✗ |
| `color` | `16777215` | let/var | `0xffffff` | ✗ |
| `intensity` | `1` | let/var | `1` | ✗ |
| `light` | `any` | let/var | `new THREE.DirectionalLight( color, intensity )` | ✗ |
| `skyColor` | `43775` | let/var | `0x00aaff` | ✗ |
| `groundColor` | `16755200` | let/var | `0xffaa00` | ✗ |
| `intensity` | `1` | let/var | `1` | ✗ |
| `light` | `any` | let/var | `new THREE.HemisphereLight( skyColor, groundColor, intensity )` | ✗ |
| `color` | `16777215` | let/var | `0xffffff` | ✗ |
| `intensity` | `1` | let/var | `1` | ✗ |
| `distance` | `0` | let/var | `0` | ✗ |
| `light` | `any` | let/var | `new THREE.PointLight( color, intensity, distance )` | ✗ |
| `color` | `16777215` | let/var | `0xffffff` | ✗ |
| `intensity` | `1` | let/var | `1` | ✗ |
| `distance` | `0` | let/var | `0` | ✗ |
| `angle` | `number` | let/var | `Math.PI * 0.1` | ✗ |
| `penumbra` | `0` | let/var | `0` | ✗ |
| `light` | `any` | let/var | `new THREE.SpotLight( color, intensity, distance, angle, penumbra )` | ✗ |
| `aspect` | `any` | let/var | `editor.camera.aspect` | ✗ |
| `camera` | `any` | let/var | `new THREE.OrthographicCamera( - aspect, aspect )` | ✗ |
| `camera` | `any` | let/var | `new THREE.PerspectiveCamera()` | ✗ |


---

## Functions

### `MenubarAdd(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setClass`
- `title.setClass`
- `title.setTextContent`
- `strings.getKey`
- `container.add`
- `options.setClass`
- `option.setClass`
- `option.setTextContent`
- `option.onClick`
- `editor.execute`
- `options.add`
- `new UIRow().setTextContent( strings.getKey( 'menubar/add/mesh' ) ).addClass( 'option' ).addClass`
- `meshSubmenuTitle.onMouseOver`
- `meshSubmenuTitle.dom.getBoundingClientRect`
- `getComputedStyle`
- `meshSubmenu.setLeft`
- `meshSubmenu.setTop`
- `parseFloat`
- `meshSubmenu.setStyle`
- `meshSubmenu.setDisplay`
- `meshSubmenuTitle.onMouseOut`
- `new UIPanel().setPosition( 'fixed' ).addClass( 'options' ).setDisplay`
- `meshSubmenuTitle.add`
- `meshSubmenu.add`
- `new UIRow().setTextContent( strings.getKey( 'menubar/add/light' ) ).addClass( 'option' ).addClass`
- `lightSubmenuTitle.onMouseOver`
- `lightSubmenuTitle.dom.getBoundingClientRect`
- `lightSubmenu.setLeft`
- `lightSubmenu.setTop`
- `lightSubmenu.setStyle`
- `lightSubmenu.setDisplay`
- `lightSubmenuTitle.onMouseOut`
- `lightSubmenuTitle.add`
- `lightSubmenu.add`
- `light.position.set`
- `new UIRow().setTextContent( strings.getKey( 'menubar/add/camera' ) ).addClass( 'option' ).addClass`
- `cameraSubmenuTitle.onMouseOver`
- `cameraSubmenuTitle.dom.getBoundingClientRect`
- `cameraSubmenu.setLeft`
- `cameraSubmenu.setTop`
- `cameraSubmenu.setStyle`
- `cameraSubmenu.setDisplay`
- `cameraSubmenuTitle.onMouseOut`
- `cameraSubmenuTitle.add`
- `cameraSubmenu.add`

**Internal Comments:**
```
// Group (x2)
// Mesh (x2)
// Mesh / Box (x3)
// Mesh / Capsule (x3)
// Mesh / Circle (x3)
// Mesh / Cylinder (x3)
// Mesh / Dodecahedron (x3)
// Mesh / Icosahedron (x3)
// Mesh / Lathe (x3)
// Mesh / Octahedron (x3)
// Mesh / Plane (x3)
// Mesh / Ring (x3)
// Mesh / Sphere (x3)
// Mesh / Sprite (x3)
// Mesh / Tetrahedron (x3)
// Mesh / Torus (x3)
// Mesh / TorusKnot (x3)
// Mesh / Tube (x3)
// Light (x2)
// Light / Ambient (x3)
// Light / Directional (x3)
// Light / Hemisphere (x3)
// Light / Point (x3)
// Light / Spot (x3)
// Camera (x2)
// Camera / Orthographic (x3)
// Camera / Perspective (x3)
```

<details><summary>Code</summary>

```typescript
function MenubarAdd( editor ) {

	const strings = editor.strings;

	const container = new UIPanel();
	container.setClass( 'menu' );

	const title = new UIPanel();
	title.setClass( 'title' );
	title.setTextContent( strings.getKey( 'menubar/add' ) );
	container.add( title );

	const options = new UIPanel();
	options.setClass( 'options' );
	container.add( options );

	// Group

	let option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/group' ) );
	option.onClick( function () {

		const mesh = new THREE.Group();
		mesh.name = 'Group';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	options.add( option );

	// Mesh

	const meshSubmenuTitle = new UIRow().setTextContent( strings.getKey( 'menubar/add/mesh' ) ).addClass( 'option' ).addClass( 'submenu-title' );
	meshSubmenuTitle.onMouseOver( function () {

		const { top, right } = meshSubmenuTitle.dom.getBoundingClientRect();
		const { paddingTop } = getComputedStyle( this.dom );
		meshSubmenu.setLeft( right + 'px' );
		meshSubmenu.setTop( top - parseFloat( paddingTop ) + 'px' );
		meshSubmenu.setStyle( 'max-height', [ `calc( 100vh - ${top}px )` ] );
		meshSubmenu.setDisplay( 'block' );

	} );
	meshSubmenuTitle.onMouseOut( function () {

		meshSubmenu.setDisplay( 'none' );

	} );
	options.add( meshSubmenuTitle );

	const meshSubmenu = new UIPanel().setPosition( 'fixed' ).addClass( 'options' ).setDisplay( 'none' );
	meshSubmenuTitle.add( meshSubmenu );

	// Mesh / Box

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/box' ) );
	option.onClick( function () {

		const geometry = new THREE.BoxGeometry( 1, 1, 1, 1, 1, 1 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Box';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Capsule

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/capsule' ) );
	option.onClick( function () {

		const geometry = new THREE.CapsuleGeometry( 1, 1, 4, 8, 1 );
		const material = new THREE.MeshStandardMaterial();
		const mesh = new THREE.Mesh( geometry, material );
		mesh.name = 'Capsule';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Circle

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/circle' ) );
	option.onClick( function () {

		const geometry = new THREE.CircleGeometry( 1, 32, 0, Math.PI * 2 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Circle';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Cylinder

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/cylinder' ) );
	option.onClick( function () {

		const geometry = new THREE.CylinderGeometry( 1, 1, 1, 32, 1, false, 0, Math.PI * 2 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Cylinder';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Dodecahedron

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/dodecahedron' ) );
	option.onClick( function () {

		const geometry = new THREE.DodecahedronGeometry( 1, 0 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Dodecahedron';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Icosahedron

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/icosahedron' ) );
	option.onClick( function () {

		const geometry = new THREE.IcosahedronGeometry( 1, 0 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Icosahedron';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Lathe

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/lathe' ) );
	option.onClick( function () {

		const geometry = new THREE.LatheGeometry();
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial( { side: THREE.DoubleSide } ) );
		mesh.name = 'Lathe';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Octahedron

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/octahedron' ) );
	option.onClick( function () {

		const geometry = new THREE.OctahedronGeometry( 1, 0 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Octahedron';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Plane

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/plane' ) );
	option.onClick( function () {

		const geometry = new THREE.PlaneGeometry( 1, 1, 1, 1 );
		const material = new THREE.MeshStandardMaterial();
		const mesh = new THREE.Mesh( geometry, material );
		mesh.name = 'Plane';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Ring

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/ring' ) );
	option.onClick( function () {

		const geometry = new THREE.RingGeometry( 0.5, 1, 32, 1, 0, Math.PI * 2 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Ring';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Sphere

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/sphere' ) );
	option.onClick( function () {

		const geometry = new THREE.SphereGeometry( 1, 32, 16, 0, Math.PI * 2, 0, Math.PI );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Sphere';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Sprite

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/sprite' ) );
	option.onClick( function () {

		const sprite = new THREE.Sprite( new THREE.SpriteMaterial() );
		sprite.name = 'Sprite';

		editor.execute( new AddObjectCommand( editor, sprite ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Tetrahedron

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/tetrahedron' ) );
	option.onClick( function () {

		const geometry = new THREE.TetrahedronGeometry( 1, 0 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Tetrahedron';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Torus

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/torus' ) );
	option.onClick( function () {

		const geometry = new THREE.TorusGeometry( 1, 0.4, 12, 48, Math.PI * 2 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Torus';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / TorusKnot

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/torusknot' ) );
	option.onClick( function () {

		const geometry = new THREE.TorusKnotGeometry( 1, 0.4, 64, 8, 2, 3 );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'TorusKnot';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Mesh / Tube

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/mesh/tube' ) );
	option.onClick( function () {

		const path = new THREE.CatmullRomCurve3( [
			new THREE.Vector3( 2, 2, - 2 ),
			new THREE.Vector3( 2, - 2, - 0.6666666666666667 ),
			new THREE.Vector3( - 2, - 2, 0.6666666666666667 ),
			new THREE.Vector3( - 2, 2, 2 )
		] );

		const geometry = new THREE.TubeGeometry( path, 64, 1, 8, false );
		const mesh = new THREE.Mesh( geometry, new THREE.MeshStandardMaterial() );
		mesh.name = 'Tube';

		editor.execute( new AddObjectCommand( editor, mesh ) );

	} );
	meshSubmenu.add( option );

	// Light

	const lightSubmenuTitle = new UIRow().setTextContent( strings.getKey( 'menubar/add/light' ) ).addClass( 'option' ).addClass( 'submenu-title' );
	lightSubmenuTitle.onMouseOver( function () {

		const { top, right } = lightSubmenuTitle.dom.getBoundingClientRect();
		const { paddingTop } = getComputedStyle( this.dom );

		lightSubmenu.setLeft( right + 'px' );
		lightSubmenu.setTop( top - parseFloat( paddingTop ) + 'px' );
		lightSubmenu.setStyle( 'max-height', [ `calc( 100vh - ${top}px )` ] );
		lightSubmenu.setDisplay( 'block' );

	} );
	lightSubmenuTitle.onMouseOut( function () {

		lightSubmenu.setDisplay( 'none' );

	} );
	options.add( lightSubmenuTitle );

	const lightSubmenu = new UIPanel().setPosition( 'fixed' ).addClass( 'options' ).setDisplay( 'none' );
	lightSubmenuTitle.add( lightSubmenu );

	// Light / Ambient

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/light/ambient' ) );
	option.onClick( function () {

		const color = 0x222222;

		const light = new THREE.AmbientLight( color );
		light.name = 'AmbientLight';

		editor.execute( new AddObjectCommand( editor, light ) );

	} );
	lightSubmenu.add( option );

	// Light / Directional

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/light/directional' ) );
	option.onClick( function () {

		const color = 0xffffff;
		const intensity = 1;

		const light = new THREE.DirectionalLight( color, intensity );
		light.name = 'DirectionalLight';
		light.target.name = 'DirectionalLight Target';

		light.position.set( 5, 10, 7.5 );

		editor.execute( new AddObjectCommand( editor, light ) );

	} );
	lightSubmenu.add( option );

	// Light / Hemisphere

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/light/hemisphere' ) );
	option.onClick( function () {

		const skyColor = 0x00aaff;
		const groundColor = 0xffaa00;
		const intensity = 1;

		const light = new THREE.HemisphereLight( skyColor, groundColor, intensity );
		light.name = 'HemisphereLight';

		light.position.set( 0, 10, 0 );

		editor.execute( new AddObjectCommand( editor, light ) );

	} );
	lightSubmenu.add( option );

	// Light / Point

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/light/point' ) );
	option.onClick( function () {

		const color = 0xffffff;
		const intensity = 1;
		const distance = 0;

		const light = new THREE.PointLight( color, intensity, distance );
		light.name = 'PointLight';

		editor.execute( new AddObjectCommand( editor, light ) );

	} );
	lightSubmenu.add( option );

	// Light / Spot

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/light/spot' ) );
	option.onClick( function () {

		const color = 0xffffff;
		const intensity = 1;
		const distance = 0;
		const angle = Math.PI * 0.1;
		const penumbra = 0;

		const light = new THREE.SpotLight( color, intensity, distance, angle, penumbra );
		light.name = 'SpotLight';
		light.target.name = 'SpotLight Target';

		light.position.set( 5, 10, 7.5 );

		editor.execute( new AddObjectCommand( editor, light ) );

	} );
	lightSubmenu.add( option );

	// Camera

	const cameraSubmenuTitle = new UIRow().setTextContent( strings.getKey( 'menubar/add/camera' ) ).addClass( 'option' ).addClass( 'submenu-title' );
	cameraSubmenuTitle.onMouseOver( function () {

		const { top, right } = cameraSubmenuTitle.dom.getBoundingClientRect();
		const { paddingTop } = getComputedStyle( this.dom );

		cameraSubmenu.setLeft( right + 'px' );
		cameraSubmenu.setTop( top - parseFloat( paddingTop ) + 'px' );
		cameraSubmenu.setStyle( 'max-height', [ `calc( 100vh - ${top}px )` ] );
		cameraSubmenu.setDisplay( 'block' );

	} );
	cameraSubmenuTitle.onMouseOut( function () {

		cameraSubmenu.setDisplay( 'none' );

	} );
	options.add( cameraSubmenuTitle );

	const cameraSubmenu = new UIPanel().setPosition( 'fixed' ).addClass( 'options' ).setDisplay( 'none' );
	cameraSubmenuTitle.add( cameraSubmenu );

	// Camera / Orthographic

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/camera/orthographic' ) );
	option.onClick( function () {

		const aspect = editor.camera.aspect;
		const camera = new THREE.OrthographicCamera( - aspect, aspect );
		camera.name = 'OrthographicCamera';

		editor.execute( new AddObjectCommand( editor, camera ) );

	} );
	cameraSubmenu.add( option );

	// Camera / Perspective

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/add/camera/perspective' ) );
	option.onClick( function () {

		const camera = new THREE.PerspectiveCamera();
		camera.name = 'PerspectiveCamera';

		editor.execute( new AddObjectCommand( editor, camera ) );

	} );
	cameraSubmenu.add( option );

	return container;

}
```
</details>


---