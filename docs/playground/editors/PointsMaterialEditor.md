[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PointsMaterialEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/PointsMaterialEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ColorInput` | `flow` |
| `ToggleInput` | `flow` |
| `SliderInput` | `flow` |
| `LabelElement` | `flow` |
| `MaterialEditor` | `./MaterialEditor.js` |
| `PointsNodeMaterial` | `three/webgpu` |
| `setInputAestheticsFromType` | `../DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `new PointsNodeMaterial()` | ✗ |


---

## Functions

### `PointsMaterialEditor.update(): void`

**Returns:** `void`

**Calls:**

- `color.setEnabledInputs`
- `color.getLinkedObject`
- `opacity.setEnabledInputs`
- `opacity.getLinkedObject`
- `size.getLinkedObject`
- `position.getLinkedObject`
- `material.dispose`
- `this.updateTransparent`
- `THREE.MathUtils.generateUUID`

**Internal Comments:**
```
// TODO: Fix on NodeMaterial System (x4)
```

<details><summary>Code</summary>

```typescript
update() {

		const { material, color, opacity, size, position } = this;

		color.setEnabledInputs( ! color.getLinkedObject() );
		opacity.setEnabledInputs( ! opacity.getLinkedObject() );

		material.colorNode = color.getLinkedObject();
		material.opacityNode = opacity.getLinkedObject() || null;

		material.sizeNode = size.getLinkedObject() || null;
		material.positionNode = position.getLinkedObject() || null;

		material.dispose();

		this.updateTransparent();

		// TODO: Fix on NodeMaterial System
		material.customProgramCacheKey = () => {

			return THREE.MathUtils.generateUUID();

		};

	}
```
</details>

### `PointsMaterialEditor.updateTransparent(): void`

**Returns:** `void`

**Calls:**

- `opacity.getLinkedObject`
- `opacity.setIcon`

<details><summary>Code</summary>

```typescript
updateTransparent() {

		const { material, opacity } = this;

		material.transparent = opacity.getLinkedObject() || material.opacity < 1 ? true : false;

		opacity.setIcon( material.transparent ? 'ti ti-layers-intersect' : 'ti ti-layers-subtract' );

	}
```
</details>


---

## Classes

### `PointsMaterialEditor`

<details><summary>Class Code</summary>

```ts
export class PointsMaterialEditor extends MaterialEditor {

	constructor() {

		const material = new PointsNodeMaterial();

		super( 'Points Material', material );

		const color = setInputAestheticsFromType( new LabelElement( 'color' ), 'Color' );
		const opacity = setInputAestheticsFromType( new LabelElement( 'opacity' ), 'Number' );
		const size = setInputAestheticsFromType( new LabelElement( 'size' ), 'Number' );
		const position = setInputAestheticsFromType( new LabelElement( 'position' ), 'Vector3' );
		const sizeAttenuation = setInputAestheticsFromType( new LabelElement( 'Size Attenuation' ), 'Number' );

		color.add( new ColorInput( material.color.getHex() ).onChange( ( input ) => {

			material.color.setHex( input.getValue() );

		} ) );

		opacity.add( new SliderInput( material.opacity, 0, 1 ).onChange( ( input ) => {

			material.opacity = input.getValue();

			this.updateTransparent();

		} ) );

		sizeAttenuation.add( new ToggleInput( material.sizeAttenuation ).onClick( ( input ) => {

			material.sizeAttenuation = input.getValue();
			material.dispose();

		} ) );

		color.onConnect( () => this.update(), true );
		opacity.onConnect( () => this.update(), true );
		size.onConnect( () => this.update(), true );
		position.onConnect( () => this.update(), true );

		this.add( color )
			.add( opacity )
			.add( size )
			.add( position )
			.add( sizeAttenuation );

		this.color = color;
		this.opacity = opacity;
		this.size = size;
		this.position = position;
		this.sizeAttenuation = sizeAttenuation;

		this.update();

	}

	update() {

		const { material, color, opacity, size, position } = this;

		color.setEnabledInputs( ! color.getLinkedObject() );
		opacity.setEnabledInputs( ! opacity.getLinkedObject() );

		material.colorNode = color.getLinkedObject();
		material.opacityNode = opacity.getLinkedObject() || null;

		material.sizeNode = size.getLinkedObject() || null;
		material.positionNode = position.getLinkedObject() || null;

		material.dispose();

		this.updateTransparent();

		// TODO: Fix on NodeMaterial System
		material.customProgramCacheKey = () => {

			return THREE.MathUtils.generateUUID();

		};

	}

	updateTransparent() {

		const { material, opacity } = this;

		material.transparent = opacity.getLinkedObject() || material.opacity < 1 ? true : false;

		opacity.setIcon( material.transparent ? 'ti ti-layers-intersect' : 'ti ti-layers-subtract' );

	}

}
```
</details>

#### Methods

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const { material, color, opacity, size, position } = this;

		color.setEnabledInputs( ! color.getLinkedObject() );
		opacity.setEnabledInputs( ! opacity.getLinkedObject() );

		material.colorNode = color.getLinkedObject();
		material.opacityNode = opacity.getLinkedObject() || null;

		material.sizeNode = size.getLinkedObject() || null;
		material.positionNode = position.getLinkedObject() || null;

		material.dispose();

		this.updateTransparent();

		// TODO: Fix on NodeMaterial System
		material.customProgramCacheKey = () => {

			return THREE.MathUtils.generateUUID();

		};

	}
```
</details>

##### `updateTransparent(): void`

<details><summary>Code</summary>

```ts
updateTransparent() {

		const { material, opacity } = this;

		material.transparent = opacity.getLinkedObject() || material.opacity < 1 ? true : false;

		opacity.setIcon( material.transparent ? 'ti ti-layers-intersect' : 'ti ti-layers-subtract' );

	}
```
</details>


---