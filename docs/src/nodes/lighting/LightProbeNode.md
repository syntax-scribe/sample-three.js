[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LightProbeNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/LightProbeNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnalyticLightNode` | `./AnalyticLightNode.js` |
| `normalWorld` | `../accessors/Normal.js` |
| `uniformArray` | `../accessors/UniformArrayNode.js` |
| `Vector3` | `../../math/Vector3.js` |
| `getShIrradianceAt` | `../functions/material/getShIrradianceAt.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `array` | `any[]` | let/var | `[]` | ✗ |


---

## Functions

### `LightProbeNode.update(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Overwritten to updated light probe specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `super.update`
- `this.lightProbe.array[ i ].copy( light.sh.coefficients[ i ] ).multiplyScalar`

**Internal Comments:**
```
//
```

<details><summary>Code</summary>

```typescript
update( frame ) {

		const { light } = this;

		super.update( frame );

		//

		for ( let i = 0; i < 9; i ++ ) {

			this.lightProbe.array[ i ].copy( light.sh.coefficients[ i ] ).multiplyScalar( light.intensity );

		}

	}
```
</details>

### `LightProbeNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `getShIrradianceAt (from ../functions/material/getShIrradianceAt.js)`
- `builder.context.irradiance.addAssign`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const irradiance = getShIrradianceAt( normalWorld, this.lightProbe );

		builder.context.irradiance.addAssign( irradiance );

	}
```
</details>


---

## Classes

### `LightProbeNode`

<details><summary>Class Code</summary>

```ts
class LightProbeNode extends AnalyticLightNode {

	static get type() {

		return 'LightProbeNode';

	}

	/**
	 * Constructs a new light probe node.
	 *
	 * @param {?LightProbe} [light=null] - The light probe.
	 */
	constructor( light = null ) {

		super( light );

		const array = [];

		for ( let i = 0; i < 9; i ++ ) array.push( new Vector3() );

		/**
		 * Light probe represented as a uniform of spherical harmonics.
		 *
		 * @type {UniformArrayNode}
		 */
		this.lightProbe = uniformArray( array );

	}

	/**
	 * Overwritten to updated light probe specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( frame ) {

		const { light } = this;

		super.update( frame );

		//

		for ( let i = 0; i < 9; i ++ ) {

			this.lightProbe.array[ i ].copy( light.sh.coefficients[ i ] ).multiplyScalar( light.intensity );

		}

	}

	setup( builder ) {

		const irradiance = getShIrradianceAt( normalWorld, this.lightProbe );

		builder.context.irradiance.addAssign( irradiance );

	}

}
```
</details>

#### Methods

##### `update(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
update( frame ) {

		const { light } = this;

		super.update( frame );

		//

		for ( let i = 0; i < 9; i ++ ) {

			this.lightProbe.array[ i ].copy( light.sh.coefficients[ i ] ).multiplyScalar( light.intensity );

		}

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const irradiance = getShIrradianceAt( normalWorld, this.lightProbe );

		builder.context.irradiance.addAssign( irradiance );

	}
```
</details>


---