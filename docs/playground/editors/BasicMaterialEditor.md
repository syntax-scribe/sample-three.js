[⬅️ Back to Table of Contents](../../index.md)

# 📄 `BasicMaterialEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/BasicMaterialEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ColorInput` | `flow` |
| `SliderInput` | `flow` |
| `LabelElement` | `flow` |
| `MaterialEditor` | `./MaterialEditor.js` |
| `MeshBasicNodeMaterial` | `three/webgpu` |
| `setInputAestheticsFromType` | `../DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `new MeshBasicNodeMaterial()` | ✗ |
| `transparent` | `boolean` | let/var | `opacity.getLinkedObject() \|\| material.opacity < 1 ? true : false` | ✗ |
| `needsUpdate` | `boolean` | let/var | `transparent !== material.transparent` | ✗ |


---

## Functions

### `BasicMaterialEditor.update(): void`

**Returns:** `void`

**Calls:**

- `color.setEnabledInputs`
- `color.getLinkedObject`
- `opacity.setEnabledInputs`
- `opacity.getLinkedObject`
- `position.getLinkedObject`
- `material.dispose`
- `this.updateTransparent`

<details><summary>Code</summary>

```typescript
update() {

		const { material, color, opacity, position } = this;

		color.setEnabledInputs( ! color.getLinkedObject() );
		opacity.setEnabledInputs( ! opacity.getLinkedObject() );

		material.colorNode = color.getLinkedObject();
		material.opacityNode = opacity.getLinkedObject() || null;

		material.positionNode = position.getLinkedObject() || null;

		material.dispose();

		this.updateTransparent();

	}
```
</details>

### `BasicMaterialEditor.updateTransparent(): void`

**Returns:** `void`

**Calls:**

- `opacity.getLinkedObject`
- `opacity.setIcon`
- `material.dispose`

<details><summary>Code</summary>

```typescript
updateTransparent() {

		const { material, opacity } = this;

		const transparent = opacity.getLinkedObject() || material.opacity < 1 ? true : false;
		const needsUpdate = transparent !== material.transparent;

		material.transparent = transparent;

		opacity.setIcon( material.transparent ? 'ti ti-layers-intersect' : 'ti ti-layers-subtract' );

		if ( needsUpdate === true ) material.dispose();

	}
```
</details>


---

## Classes

### `BasicMaterialEditor`

<details><summary>Class Code</summary>

```ts
export class BasicMaterialEditor extends MaterialEditor {

	constructor() {

		const material = new MeshBasicNodeMaterial();

		super( 'Basic Material', material );

		const color = setInputAestheticsFromType( new LabelElement( 'color' ), 'Color' );
		const opacity = setInputAestheticsFromType( new LabelElement( 'opacity' ), 'Number' );
		const position = setInputAestheticsFromType( new LabelElement( 'position' ), 'Vector3' );

		color.add( new ColorInput( material.color.getHex() ).onChange( ( input ) => {

			material.color.setHex( input.getValue() );

		} ) );

		opacity.add( new SliderInput( material.opacity, 0, 1 ).onChange( ( input ) => {

			material.opacity = input.getValue();

			this.updateTransparent();

		} ) );

		color.onConnect( () => this.update(), true );
		opacity.onConnect( () => this.update(), true );
		position.onConnect( () => this.update(), true );

		this.add( color )
			.add( opacity )
			.add( position );

		this.color = color;
		this.opacity = opacity;
		this.position = position;

		this.update();

	}

	update() {

		const { material, color, opacity, position } = this;

		color.setEnabledInputs( ! color.getLinkedObject() );
		opacity.setEnabledInputs( ! opacity.getLinkedObject() );

		material.colorNode = color.getLinkedObject();
		material.opacityNode = opacity.getLinkedObject() || null;

		material.positionNode = position.getLinkedObject() || null;

		material.dispose();

		this.updateTransparent();

	}

	updateTransparent() {

		const { material, opacity } = this;

		const transparent = opacity.getLinkedObject() || material.opacity < 1 ? true : false;
		const needsUpdate = transparent !== material.transparent;

		material.transparent = transparent;

		opacity.setIcon( material.transparent ? 'ti ti-layers-intersect' : 'ti ti-layers-subtract' );

		if ( needsUpdate === true ) material.dispose();

	}

}
```
</details>

#### Methods

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const { material, color, opacity, position } = this;

		color.setEnabledInputs( ! color.getLinkedObject() );
		opacity.setEnabledInputs( ! opacity.getLinkedObject() );

		material.colorNode = color.getLinkedObject();
		material.opacityNode = opacity.getLinkedObject() || null;

		material.positionNode = position.getLinkedObject() || null;

		material.dispose();

		this.updateTransparent();

	}
```
</details>

##### `updateTransparent(): void`

<details><summary>Code</summary>

```ts
updateTransparent() {

		const { material, opacity } = this;

		const transparent = opacity.getLinkedObject() || material.opacity < 1 ? true : false;
		const needsUpdate = transparent !== material.transparent;

		material.transparent = transparent;

		opacity.setIcon( material.transparent ? 'ti ti-layers-intersect' : 'ti ti-layers-subtract' );

		if ( needsUpdate === true ) material.dispose();

	}
```
</details>


---