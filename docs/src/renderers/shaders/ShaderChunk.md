[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ShaderChunk.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 107 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`src/renderers/shaders/ShaderChunk.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `alphahash_fragment` | `./ShaderChunk/alphahash_fragment.glsl.js` |
| `alphahash_pars_fragment` | `./ShaderChunk/alphahash_pars_fragment.glsl.js` |
| `alphamap_fragment` | `./ShaderChunk/alphamap_fragment.glsl.js` |
| `alphamap_pars_fragment` | `./ShaderChunk/alphamap_pars_fragment.glsl.js` |
| `alphatest_fragment` | `./ShaderChunk/alphatest_fragment.glsl.js` |
| `alphatest_pars_fragment` | `./ShaderChunk/alphatest_pars_fragment.glsl.js` |
| `aomap_fragment` | `./ShaderChunk/aomap_fragment.glsl.js` |
| `aomap_pars_fragment` | `./ShaderChunk/aomap_pars_fragment.glsl.js` |
| `batching_pars_vertex` | `./ShaderChunk/batching_pars_vertex.glsl.js` |
| `batching_vertex` | `./ShaderChunk/batching_vertex.glsl.js` |
| `begin_vertex` | `./ShaderChunk/begin_vertex.glsl.js` |
| `beginnormal_vertex` | `./ShaderChunk/beginnormal_vertex.glsl.js` |
| `bsdfs` | `./ShaderChunk/bsdfs.glsl.js` |
| `iridescence_fragment` | `./ShaderChunk/iridescence_fragment.glsl.js` |
| `bumpmap_pars_fragment` | `./ShaderChunk/bumpmap_pars_fragment.glsl.js` |
| `clipping_planes_fragment` | `./ShaderChunk/clipping_planes_fragment.glsl.js` |
| `clipping_planes_pars_fragment` | `./ShaderChunk/clipping_planes_pars_fragment.glsl.js` |
| `clipping_planes_pars_vertex` | `./ShaderChunk/clipping_planes_pars_vertex.glsl.js` |
| `clipping_planes_vertex` | `./ShaderChunk/clipping_planes_vertex.glsl.js` |
| `color_fragment` | `./ShaderChunk/color_fragment.glsl.js` |
| `color_pars_fragment` | `./ShaderChunk/color_pars_fragment.glsl.js` |
| `color_pars_vertex` | `./ShaderChunk/color_pars_vertex.glsl.js` |
| `color_vertex` | `./ShaderChunk/color_vertex.glsl.js` |
| `common` | `./ShaderChunk/common.glsl.js` |
| `cube_uv_reflection_fragment` | `./ShaderChunk/cube_uv_reflection_fragment.glsl.js` |
| `defaultnormal_vertex` | `./ShaderChunk/defaultnormal_vertex.glsl.js` |
| `displacementmap_pars_vertex` | `./ShaderChunk/displacementmap_pars_vertex.glsl.js` |
| `displacementmap_vertex` | `./ShaderChunk/displacementmap_vertex.glsl.js` |
| `emissivemap_fragment` | `./ShaderChunk/emissivemap_fragment.glsl.js` |
| `emissivemap_pars_fragment` | `./ShaderChunk/emissivemap_pars_fragment.glsl.js` |
| `colorspace_fragment` | `./ShaderChunk/colorspace_fragment.glsl.js` |
| `colorspace_pars_fragment` | `./ShaderChunk/colorspace_pars_fragment.glsl.js` |
| `envmap_fragment` | `./ShaderChunk/envmap_fragment.glsl.js` |
| `envmap_common_pars_fragment` | `./ShaderChunk/envmap_common_pars_fragment.glsl.js` |
| `envmap_pars_fragment` | `./ShaderChunk/envmap_pars_fragment.glsl.js` |
| `envmap_pars_vertex` | `./ShaderChunk/envmap_pars_vertex.glsl.js` |
| `envmap_vertex` | `./ShaderChunk/envmap_vertex.glsl.js` |
| `fog_vertex` | `./ShaderChunk/fog_vertex.glsl.js` |
| `fog_pars_vertex` | `./ShaderChunk/fog_pars_vertex.glsl.js` |
| `fog_fragment` | `./ShaderChunk/fog_fragment.glsl.js` |
| `fog_pars_fragment` | `./ShaderChunk/fog_pars_fragment.glsl.js` |
| `gradientmap_pars_fragment` | `./ShaderChunk/gradientmap_pars_fragment.glsl.js` |
| `lightmap_pars_fragment` | `./ShaderChunk/lightmap_pars_fragment.glsl.js` |
| `lights_lambert_fragment` | `./ShaderChunk/lights_lambert_fragment.glsl.js` |
| `lights_lambert_pars_fragment` | `./ShaderChunk/lights_lambert_pars_fragment.glsl.js` |
| `lights_pars_begin` | `./ShaderChunk/lights_pars_begin.glsl.js` |
| `envmap_physical_pars_fragment` | `./ShaderChunk/envmap_physical_pars_fragment.glsl.js` |
| `lights_toon_fragment` | `./ShaderChunk/lights_toon_fragment.glsl.js` |
| `lights_toon_pars_fragment` | `./ShaderChunk/lights_toon_pars_fragment.glsl.js` |
| `lights_phong_fragment` | `./ShaderChunk/lights_phong_fragment.glsl.js` |
| `lights_phong_pars_fragment` | `./ShaderChunk/lights_phong_pars_fragment.glsl.js` |
| `lights_physical_fragment` | `./ShaderChunk/lights_physical_fragment.glsl.js` |
| `lights_physical_pars_fragment` | `./ShaderChunk/lights_physical_pars_fragment.glsl.js` |
| `lights_fragment_begin` | `./ShaderChunk/lights_fragment_begin.glsl.js` |
| `lights_fragment_maps` | `./ShaderChunk/lights_fragment_maps.glsl.js` |
| `lights_fragment_end` | `./ShaderChunk/lights_fragment_end.glsl.js` |
| `logdepthbuf_fragment` | `./ShaderChunk/logdepthbuf_fragment.glsl.js` |
| `logdepthbuf_pars_fragment` | `./ShaderChunk/logdepthbuf_pars_fragment.glsl.js` |
| `logdepthbuf_pars_vertex` | `./ShaderChunk/logdepthbuf_pars_vertex.glsl.js` |
| `logdepthbuf_vertex` | `./ShaderChunk/logdepthbuf_vertex.glsl.js` |
| `map_fragment` | `./ShaderChunk/map_fragment.glsl.js` |
| `map_pars_fragment` | `./ShaderChunk/map_pars_fragment.glsl.js` |
| `map_particle_fragment` | `./ShaderChunk/map_particle_fragment.glsl.js` |
| `map_particle_pars_fragment` | `./ShaderChunk/map_particle_pars_fragment.glsl.js` |
| `metalnessmap_fragment` | `./ShaderChunk/metalnessmap_fragment.glsl.js` |
| `metalnessmap_pars_fragment` | `./ShaderChunk/metalnessmap_pars_fragment.glsl.js` |
| `morphinstance_vertex` | `./ShaderChunk/morphinstance_vertex.glsl.js` |
| `morphcolor_vertex` | `./ShaderChunk/morphcolor_vertex.glsl.js` |
| `morphnormal_vertex` | `./ShaderChunk/morphnormal_vertex.glsl.js` |
| `morphtarget_pars_vertex` | `./ShaderChunk/morphtarget_pars_vertex.glsl.js` |
| `morphtarget_vertex` | `./ShaderChunk/morphtarget_vertex.glsl.js` |
| `normal_fragment_begin` | `./ShaderChunk/normal_fragment_begin.glsl.js` |
| `normal_fragment_maps` | `./ShaderChunk/normal_fragment_maps.glsl.js` |
| `normal_pars_fragment` | `./ShaderChunk/normal_pars_fragment.glsl.js` |
| `normal_pars_vertex` | `./ShaderChunk/normal_pars_vertex.glsl.js` |
| `normal_vertex` | `./ShaderChunk/normal_vertex.glsl.js` |
| `normalmap_pars_fragment` | `./ShaderChunk/normalmap_pars_fragment.glsl.js` |
| `clearcoat_normal_fragment_begin` | `./ShaderChunk/clearcoat_normal_fragment_begin.glsl.js` |
| `clearcoat_normal_fragment_maps` | `./ShaderChunk/clearcoat_normal_fragment_maps.glsl.js` |
| `clearcoat_pars_fragment` | `./ShaderChunk/clearcoat_pars_fragment.glsl.js` |
| `iridescence_pars_fragment` | `./ShaderChunk/iridescence_pars_fragment.glsl.js` |
| `opaque_fragment` | `./ShaderChunk/opaque_fragment.glsl.js` |
| `packing` | `./ShaderChunk/packing.glsl.js` |
| `premultiplied_alpha_fragment` | `./ShaderChunk/premultiplied_alpha_fragment.glsl.js` |
| `project_vertex` | `./ShaderChunk/project_vertex.glsl.js` |
| `dithering_fragment` | `./ShaderChunk/dithering_fragment.glsl.js` |
| `dithering_pars_fragment` | `./ShaderChunk/dithering_pars_fragment.glsl.js` |
| `roughnessmap_fragment` | `./ShaderChunk/roughnessmap_fragment.glsl.js` |
| `roughnessmap_pars_fragment` | `./ShaderChunk/roughnessmap_pars_fragment.glsl.js` |
| `shadowmap_pars_fragment` | `./ShaderChunk/shadowmap_pars_fragment.glsl.js` |
| `shadowmap_pars_vertex` | `./ShaderChunk/shadowmap_pars_vertex.glsl.js` |
| `shadowmap_vertex` | `./ShaderChunk/shadowmap_vertex.glsl.js` |
| `shadowmask_pars_fragment` | `./ShaderChunk/shadowmask_pars_fragment.glsl.js` |
| `skinbase_vertex` | `./ShaderChunk/skinbase_vertex.glsl.js` |
| `skinning_pars_vertex` | `./ShaderChunk/skinning_pars_vertex.glsl.js` |
| `skinning_vertex` | `./ShaderChunk/skinning_vertex.glsl.js` |
| `skinnormal_vertex` | `./ShaderChunk/skinnormal_vertex.glsl.js` |
| `specularmap_fragment` | `./ShaderChunk/specularmap_fragment.glsl.js` |
| `specularmap_pars_fragment` | `./ShaderChunk/specularmap_pars_fragment.glsl.js` |
| `tonemapping_fragment` | `./ShaderChunk/tonemapping_fragment.glsl.js` |
| `tonemapping_pars_fragment` | `./ShaderChunk/tonemapping_pars_fragment.glsl.js` |
| `transmission_fragment` | `./ShaderChunk/transmission_fragment.glsl.js` |
| `transmission_pars_fragment` | `./ShaderChunk/transmission_pars_fragment.glsl.js` |
| `uv_pars_fragment` | `./ShaderChunk/uv_pars_fragment.glsl.js` |
| `uv_pars_vertex` | `./ShaderChunk/uv_pars_vertex.glsl.js` |
| `uv_vertex` | `./ShaderChunk/uv_vertex.glsl.js` |
| `worldpos_vertex` | `./ShaderChunk/worldpos_vertex.glsl.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `ShaderChunk` | `{ alphahash_fragment: string; alphaha...` | let/var | `{ alphahash_fragment: alphahash_fragment, alphahash_pars_fragment: alphahash_...` | ✓ |


---