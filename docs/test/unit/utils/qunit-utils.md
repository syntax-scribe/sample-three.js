[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `qunit-utils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 17 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/utils/qunit-utils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `SmartComparer` | `./SmartComparer.js` |
| `ObjectLoader` | `../../../src/loaders/ObjectLoader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `actual` | `any` | let/var | `obj[ key ]` | ✗ |
| `expected` | `any` | let/var | `ref[ key ]` | ✗ |
| `message` | `string` | let/var | `actual + ' should be equal to ' + expected + ' for key "' + key + '"'` | ✗ |
| `cmp` | `any` | let/var | `new SmartComparer()` | ✗ |
| `msg` | `any` | let/var | `cmp.getDiagnostic() \|\| message` | ✗ |
| `differingProp` | `any` | let/var | `undefined` | ✗ |
| `key` | `string` | let/var | `geometryKeys[ i ]` | ✗ |
| `params` | `any` | let/var | `geom.parameters` | ✗ |
| `notParameters` | `string[]` | let/var | `[ 'metadata', 'uuid', 'type' ]` | ✗ |
| `key` | `string` | let/var | `keys[ i ]` | ✗ |
| `wrap` | `any[]` | let/var | `[ json ]` | ✗ |
| `loader` | `ObjectLoader` | let/var | `new ObjectLoader()` | ✗ |
| `geom` | `any` | let/var | `geometries[ i ]` | ✗ |
| `light` | `any` | let/var | `lights[ i ]` | ✗ |
| `newLight` | `any` | let/var | `new light.constructor( 0xc0ffee )` | ✗ |
| `object` | `any` | let/var | `json.object` | ✗ |
| `loader` | `ObjectLoader` | let/var | `new ObjectLoader()` | ✗ |


---

## Functions

### `checkGeometryClone(geom: any): void`

**Parameters:**

- **`geom`** `any`

**Returns:** `void`

**Calls:**

- `geom.clone`
- `QUnit.assert.notEqual`
- `getDifferingProp`
- `QUnit.assert.ok`
- `checkGeometryJsonRoundtrip`

**Internal Comments:**
```
// Clone (x2)
// json round trip with clone (x3)
```

<details><summary>Code</summary>

```typescript
function checkGeometryClone( geom ) {

	// Clone
	const copy = geom.clone();
	QUnit.assert.notEqual( copy.uuid, geom.uuid, 'clone uuid should differ from original' );
	QUnit.assert.notEqual( copy.id, geom.id, 'clone id should differ from original' );

	let differingProp = getDifferingProp( geom, copy );
	QUnit.assert.ok( differingProp === undefined, 'properties are equal' );

	differingProp = getDifferingProp( copy, geom );
	QUnit.assert.ok( differingProp === undefined, 'properties are equal' );

	// json round trip with clone
	checkGeometryJsonRoundtrip( copy );

}
```
</details>

### `getDifferingProp(geometryA: any, geometryB: any): string`

**Parameters:**

- **`geometryA`** `any`
- **`geometryB`** `any`

**Returns:** `string`

**Calls:**

- `Object.keys`
- `cloneKeys.indexOf`

<details><summary>Code</summary>

```typescript
function getDifferingProp( geometryA, geometryB ) {

	const geometryKeys = Object.keys( geometryA );
	const cloneKeys = Object.keys( geometryB );

	let differingProp = undefined;

	for ( let i = 0, l = geometryKeys.length; i < l; i ++ ) {

		const key = geometryKeys[ i ];

		if ( cloneKeys.indexOf( key ) < 0 ) {

			differingProp = key;
			break;

		}

	}

	return differingProp;

}
```
</details>

### `checkGeometryJsonWriting(geom: any, json: any): void`

**Parameters:**

- **`geom`** `any`
- **`json`** `any`

**Returns:** `void`

**Calls:**

- `QUnit.assert.equal`
- `QUnit.assert.equalKey`
- `Object.keys`
- `notParameters.indexOf`

**Internal Comments:**
```
// All parameters from geometry should be persisted. (x2)
// All parameters from json should be transferred to the geometry. (x2)
// json is flat. Ignore first level json properties that are not parameters. (x2)
```

<details><summary>Code</summary>

```typescript
function checkGeometryJsonWriting( geom, json ) {

	QUnit.assert.equal( json.metadata.version, '4.7', 'check metadata version' );
	QUnit.assert.equalKey( geom, json, 'type' );
	QUnit.assert.equalKey( geom, json, 'uuid' );
	QUnit.assert.equal( json.id, undefined, 'should not persist id' );

	const params = geom.parameters;
	if ( ! params ) {

		return;

	}

	// All parameters from geometry should be persisted.
	let keys = Object.keys( params );
	for ( let i = 0, l = keys.length; i < l; i ++ ) {

		QUnit.assert.equalKey( params, json, keys[ i ] );

	}

	// All parameters from json should be transferred to the geometry.
	// json is flat. Ignore first level json properties that are not parameters.
	const notParameters = [ 'metadata', 'uuid', 'type' ];
	keys = Object.keys( json );
	for ( let i = 0, l = keys.length; i < l; i ++ ) {

		const key = keys[ i ];
		if ( notParameters.indexOf( key ) === - 1 ) QUnit.assert.equalKey( params, json, key );

	}

}
```
</details>

### `checkGeometryJsonReading(json: any, geom: any): void`

**Parameters:**

- **`json`** `any`
- **`geom`** `any`

**Returns:** `void`

**Calls:**

- `loader.parseGeometries`
- `QUnit.assert.ok`
- `getDifferingProp`
- `console.log`

**Internal Comments:**
```
// QUnit.assert.smartEqual( output[ geom.uuid ], geom, 'Reconstruct geometry from ObjectLoader' ); (x2)
```

<details><summary>Code</summary>

```typescript
function checkGeometryJsonReading( json, geom ) {

	const wrap = [ json ];

	const loader = new ObjectLoader();
	const output = loader.parseGeometries( wrap );

	QUnit.assert.ok( output[ geom.uuid ], 'geometry matching source uuid not in output' );
	// QUnit.assert.smartEqual( output[ geom.uuid ], geom, 'Reconstruct geometry from ObjectLoader' );

	const differing = getDifferingProp( output[ geom.uuid ], geom );
	if ( differing ) console.log( differing );

	let differingProp = getDifferingProp( output[ geom.uuid ], geom );
	QUnit.assert.ok( differingProp === undefined, 'properties are equal' );

	differingProp = getDifferingProp( geom, output[ geom.uuid ] );
	QUnit.assert.ok( differingProp === undefined, 'properties are equal' );

}
```
</details>

### `checkGeometryJsonRoundtrip(geom: any): void`

**Parameters:**

- **`geom`** `any`

**Returns:** `void`

**Calls:**

- `geom.toJSON`
- `checkGeometryJsonWriting`
- `checkGeometryJsonReading`

<details><summary>Code</summary>

```typescript
function checkGeometryJsonRoundtrip( geom ) {

	const json = geom.toJSON();
	checkGeometryJsonWriting( geom, json );
	checkGeometryJsonReading( json, geom );

}
```
</details>

### `runStdGeometryTests(assert: any, geometries: any): void`

**Parameters:**

- **`assert`** `any`
- **`geometries`** `any`

**Returns:** `void`

**Calls:**

- `checkGeometryClone`
- `checkGeometryJsonRoundtrip`

**Internal Comments:**
```
// Clone (x3)
// json round trip (x3)
```

<details><summary>Code</summary>

```typescript
function runStdGeometryTests( assert, geometries ) {

	for ( let i = 0, l = geometries.length; i < l; i ++ ) {

		const geom = geometries[ i ];

		// Clone
		checkGeometryClone( geom );

		// json round trip
		checkGeometryJsonRoundtrip( geom );

	}

}
```
</details>

### `runStdLightTests(assert: any, lights: any): void`

**Parameters:**

- **`assert`** `any`
- **`lights`** `any`

**Returns:** `void`

**Calls:**

- `checkLightCopyClone`
- `checkLightJsonRoundtrip`

**Internal Comments:**
```
// copy and clone (x3)
// THREE.Light doesn't get parsed by ObjectLoader as it's only
// used as an abstract base class - so we skip the JSON tests
// json round trip (x3)
```

<details><summary>Code</summary>

```typescript
function runStdLightTests( assert, lights ) {

	for ( let i = 0, l = lights.length; i < l; i ++ ) {

		const light = lights[ i ];

		// copy and clone
		checkLightCopyClone( assert, light );

		// THREE.Light doesn't get parsed by ObjectLoader as it's only
		// used as an abstract base class - so we skip the JSON tests
		if ( light.type !== 'Light' ) {

			// json round trip
			checkLightJsonRoundtrip( assert, light );

		}

	}

}
```
</details>

### `checkLightCopyClone(assert: any, light: any): void`

**Parameters:**

- **`assert`** `any`
- **`light`** `any`

**Returns:** `void`

**Calls:**

- `newLight.copy`
- `QUnit.assert.notEqual`
- `QUnit.assert.smartEqual`
- `newLight.color.setHex`
- `QUnit.assert.notStrictEqual`
- `newLight.color.getHex`
- `light.color.getHex`
- `light.clone`
- `clone.color.setHex`
- `clone.color.getHex`
- `checkLightJsonRoundtrip`

**Internal Comments:**
```
// copy (x2)
// real copy? (x5)
// Clone (x2)
// real clone? (x5)
// json round trip with clone (x3)
```

<details><summary>Code</summary>

```typescript
function checkLightCopyClone( assert, light ) {

	// copy
	const newLight = new light.constructor( 0xc0ffee );
	newLight.copy( light );

	QUnit.assert.notEqual( newLight.uuid, light.uuid, 'Copied light\'s UUID differs from original' );
	QUnit.assert.notEqual( newLight.id, light.id, 'Copied light\'s id differs from original' );
	QUnit.assert.smartEqual( newLight, light, 'Copied light is equal to original' );

	// real copy?
	newLight.color.setHex( 0xc0ffee );
	QUnit.assert.notStrictEqual(
		newLight.color.getHex(), light.color.getHex(), 'Copied light is independent from original'
	);

	// Clone
	const clone = light.clone(); // better get a new clone
	QUnit.assert.notEqual( clone.uuid, light.uuid, 'Cloned light\'s UUID differs from original' );
	QUnit.assert.notEqual( clone.id, light.id, 'Clone light\'s id differs from original' );
	QUnit.assert.smartEqual( clone, light, 'Clone light is equal to original' );

	// real clone?
	clone.color.setHex( 0xc0ffee );
	QUnit.assert.notStrictEqual(
		clone.color.getHex(), light.color.getHex(), 'Clone light is independent from original'
	);

	if ( light.type !== 'Light' ) {

		// json round trip with clone
		checkLightJsonRoundtrip( assert, clone );

	}

}
```
</details>

### `checkLightJsonWriting(assert: any, light: any, json: any): void`

**Parameters:**

- **`assert`** `any`
- **`light`** `any`
- **`json`** `any`

**Returns:** `void`

**Calls:**

- `assert.equal`
- `assert.equalKey`

<details><summary>Code</summary>

```typescript
function checkLightJsonWriting( assert, light, json ) {

	assert.equal( json.metadata.version, '4.7', 'check metadata version' );

	const object = json.object;
	assert.equalKey( light, object, 'type' );
	assert.equalKey( light, object, 'uuid' );
	assert.equal( object.id, undefined, 'should not persist id' );

}
```
</details>

### `checkLightJsonReading(assert: any, json: any, light: any): void`

**Parameters:**

- **`assert`** `any`
- **`json`** `any`
- **`light`** `any`

**Returns:** `void`

**Calls:**

- `loader.parse`
- `assert.smartEqual`

<details><summary>Code</summary>

```typescript
function checkLightJsonReading( assert, json, light ) {

	const loader = new ObjectLoader();
	const outputLight = loader.parse( json );

	assert.smartEqual( outputLight, light, 'Reconstruct Light from ObjectLoader' );

}
```
</details>

### `checkLightJsonRoundtrip(assert: any, light: any): void`

**Parameters:**

- **`assert`** `any`
- **`light`** `any`

**Returns:** `void`

**Calls:**

- `light.toJSON`
- `checkLightJsonWriting`
- `checkLightJsonReading`

<details><summary>Code</summary>

```typescript
function checkLightJsonRoundtrip( assert, light ) {

	const json = light.toJSON();
	checkLightJsonWriting( assert, light, json );
	checkLightJsonReading( assert, json, light );

}
```
</details>


---