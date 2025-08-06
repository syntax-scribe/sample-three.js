[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `BasicNodeLibrary.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 31 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/nodes/BasicNodeLibrary.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeLibrary` | `../../common/nodes/NodeLibrary.js` |
| `PointLight` | `../../../lights/PointLight.js` |
| `DirectionalLight` | `../../../lights/DirectionalLight.js` |
| `RectAreaLight` | `../../../lights/RectAreaLight.js` |
| `SpotLight` | `../../../lights/SpotLight.js` |
| `AmbientLight` | `../../../lights/AmbientLight.js` |
| `HemisphereLight` | `../../../lights/HemisphereLight.js` |
| `LightProbe` | `../../../lights/LightProbe.js` |
| `IESSpotLight` | `../../../lights/webgpu/IESSpotLight.js` |
| `ProjectorLight` | `../../../lights/webgpu/ProjectorLight.js` |
| `PointLightNode` | `../../../nodes/Nodes.js` |
| `DirectionalLightNode` | `../../../nodes/Nodes.js` |
| `RectAreaLightNode` | `../../../nodes/Nodes.js` |
| `SpotLightNode` | `../../../nodes/Nodes.js` |
| `AmbientLightNode` | `../../../nodes/Nodes.js` |
| `HemisphereLightNode` | `../../../nodes/Nodes.js` |
| `LightProbeNode` | `../../../nodes/Nodes.js` |
| `IESSpotLightNode` | `../../../nodes/Nodes.js` |
| `ProjectorLightNode` | `../../../nodes/Nodes.js` |
| `LinearToneMapping` | `../../../constants.js` |
| `ReinhardToneMapping` | `../../../constants.js` |
| `CineonToneMapping` | `../../../constants.js` |
| `ACESFilmicToneMapping` | `../../../constants.js` |
| `AgXToneMapping` | `../../../constants.js` |
| `NeutralToneMapping` | `../../../constants.js` |
| `linearToneMapping` | `../../../nodes/display/ToneMappingFunctions.js` |
| `reinhardToneMapping` | `../../../nodes/display/ToneMappingFunctions.js` |
| `cineonToneMapping` | `../../../nodes/display/ToneMappingFunctions.js` |
| `acesFilmicToneMapping` | `../../../nodes/display/ToneMappingFunctions.js` |
| `agxToneMapping` | `../../../nodes/display/ToneMappingFunctions.js` |
| `neutralToneMapping` | `../../../nodes/display/ToneMappingFunctions.js` |


---

## Classes

### `BasicNodeLibrary`

<details><summary>Class Code</summary>

```ts
class BasicNodeLibrary extends NodeLibrary {

	/**
	 * Constructs a new basic node library.
	 */
	constructor() {

		super();

		this.addLight( PointLightNode, PointLight );
		this.addLight( DirectionalLightNode, DirectionalLight );
		this.addLight( RectAreaLightNode, RectAreaLight );
		this.addLight( SpotLightNode, SpotLight );
		this.addLight( AmbientLightNode, AmbientLight );
		this.addLight( HemisphereLightNode, HemisphereLight );
		this.addLight( LightProbeNode, LightProbe );
		this.addLight( IESSpotLightNode, IESSpotLight );
		this.addLight( ProjectorLightNode, ProjectorLight );

		this.addToneMapping( linearToneMapping, LinearToneMapping );
		this.addToneMapping( reinhardToneMapping, ReinhardToneMapping );
		this.addToneMapping( cineonToneMapping, CineonToneMapping );
		this.addToneMapping( acesFilmicToneMapping, ACESFilmicToneMapping );
		this.addToneMapping( agxToneMapping, AgXToneMapping );
		this.addToneMapping( neutralToneMapping, NeutralToneMapping );

	}

}
```
</details>


---